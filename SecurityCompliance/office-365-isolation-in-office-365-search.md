---
title: Office 365 租用戶隔離中的 Office 365 搜尋
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 摘要： 在 Office 365 搜尋的租用戶隔離說明。
ms.openlocfilehash: cc73f3c157ffd20b3891a6b7c58e7d0b2adf4e55
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526151"
---
# <a name="tenant-isolation-in-office-365-search"></a>Office 365 搜尋中的租用戶隔離
SharePoint Online 搜尋使用平衡與理想的資訊洩漏租用戶之間的共用的資料結構的效率的租用戶分離模型。使用此模型中，我們會防止從搜尋功能：
- 傳回查詢結果包含來自其他租用戶的文件
- 公開查詢結果中足夠資訊可讓積極且熟練的使用者無法推斷其他租用戶的相關資訊
- 顯示結構描述] 或 [從另一個承租人的設定
- 混用分析處理承租人或錯誤的租用戶中的儲存區結果之間的資訊
- 使用來自另一個承租人的字典項目

針對每種承租人資料類型，我們使用一或多個圖層的保護在程式碼來避免意外遺漏的資訊。最重要的資料有大部分的以確保單一缺失不會導致實際或視為資訊外洩保護層級。

## <a name="tenant-separation-for-the-search-index"></a>搜尋索引的租用戶分離
在裝載索引元件的伺服器的磁碟上儲存的搜尋索引及承租人共用索引檔案。租用戶編製索引文件都可以看到僅針對該租用戶的查詢。三個獨立的機制防止資訊洩漏：
- 租用戶識別碼篩選
- 租用戶識別碼字詞前面加上
- ACL 檢查

所有三個機制必須搜尋以返回了錯誤的租用戶中的文件的失敗。

## <a name="tenant-id-filtering-and-tenant-id-term-prefixing"></a>租用戶識別碼篩選與租用戶識別碼字詞前面加上
搜尋的前置詞索引與租用戶識別碼全文檢索索引中每個字詞例如，當詞"*foo*"租用戶識別碼為"*123*"編製索引，全文檢索索引中的項目是"*123foo。*"

每個查詢會轉換成包含租用戶識別碼呼叫租用戶識別碼篩選程序。例如，"*foo*"的查詢會轉換為"<*guid*>。*foo*和*tenantID*: <*guid*>"，其中 <*guid*> 代表承租人執行查詢。此查詢轉換此時間內每個索引節點及查詢皆內容處理影響它。租用戶識別碼為新增至每個查詢，因為無法推斷其他租用戶中某個字詞的頻率來尋找在最佳排名一個租用戶中比對。

租用戶識別碼字詞前面加上發生只能在全文檢索索引。擁有搜尋，例如"*標題： foo*"移至 [綜合搜尋索引不租用戶識別碼所前面上字詞而是擁有搜尋被以欄位名稱。例如，"*標題： foo*"的查詢轉換成"*fields.title:foo AND fields.tenantID*: <*guid*>。 」由於字詞的頻率不會影響排名的拜訪人次綜合搜尋索引中，有不需要由字詞前面加上的租用戶分離。Like"*標題： foo*"fielded 搜尋承租人內容分隔取決於查詢轉換所篩選的租用戶識別碼。

## <a name="document-access-control-list-checks"></a>文件存取控制清單檢查
搜尋控制項存取透過儲存在搜尋索引中的 Acl 的文件。每個項目會包含一組字詞的特殊的 ACL] 欄位中編製索引。ACL] 欄位包含群組或使用者可以檢視文件的每一個字詞。每個查詢進一步強化存取控制項目 (ACE) 條款，另一個適用於已驗證的使用者所屬的每個群組的清單。

例如，查詢 like"<*guid*>。*foo AND tenantID*: <*guid*>"會變成："<*guid*>。*foo AND tenantID*: <*guid*> *AND* (*docACL：*<*ace1*> *OR docACL*: <*ace2*> *OR docACL*: <*ace3*> *...*)"

因為使用者和群組識別碼及稱做 Ace 是唯一的這提供額外的僅限某些使用者看到的文件的租用戶之間的安全性層級。是相同的特殊 「 所有人以外的外部使用者 」 案例授與存取權的租用戶中的一般使用者的 ACE。但因為 Ace 針對 「 所有人 」 之所有租用戶相同，公用文件的租用戶分離取決於租用戶識別碼篩選。拒絕 Ace 也支援。查詢增強將會移除文件結果拒絕 ACE 相符時的子句。

在 Exchange Online 搜尋索引會分割上的個別使用者的信箱，而不是如同 SharePoint Online 的租用戶識別碼 （訂閱識別碼） 的信箱識別碼。分隔機制相當於 SharePoint Online、 但沒有任何 ACL 篩選。
