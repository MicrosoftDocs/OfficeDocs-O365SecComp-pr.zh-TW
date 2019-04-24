---
title: Office 365 搜尋中的 office 365 租用戶隔離
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 摘要： 在 Office 365 搜尋中的租用戶隔離的說明。
ms.openlocfilehash: 5254ffe2e6b92c6ba100a9e45b35b456ead1b000
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262595"
---
# <a name="tenant-isolation-in-office-365-search"></a>Office 365 搜尋中的租用戶隔離
SharePoint Online 搜尋使用平衡含有防範資訊洩漏租用戶之間的共用的資料結構的效率租用戶區隔模型。 與此模型中，我們會防止從搜尋功能：
- 傳回包含來自其他租用戶的文件的查詢結果
- 公開且熟練的使用者無法推斷其他租用戶的資訊在查詢結果中有足夠的資訊
- 顯示結構描述或從另一個租用戶設定
- 混用分析處理租用戶或錯誤的租用戶中的儲存區結果之間的資訊
- 使用從另一個租用戶的字典項目

每種類型的租用戶資料中，我們使用一或多個層級保護在程式碼來避免意外遺漏的資訊。 最重要的資料有以確保單一缺失不會導致實際或認知資訊外洩防護的大部分層次。

## <a name="tenant-separation-for-the-search-index"></a>搜尋索引的租用戶區隔
搜尋索引儲存在磁碟中裝載索引元件的伺服器上，則這些承租人共用索引檔案。 租用戶的已編製索引的文件會顯示僅適用於該租用戶的查詢。 三個獨立的機制防止資訊外洩：
- 租用戶識別碼篩選
- 租用戶識別碼字詞前面加上
- ACL 檢查

所有三個機制會有失敗的搜尋以返回錯誤的租用戶中的文件。

## <a name="tenant-id-filtering-and-tenant-id-term-prefixing"></a>租用戶識別碼篩選和租用戶識別碼字詞前面加上
搜尋前置詞在具有租用戶識別碼的全文檢索索引編製索引的每個字詞 例如，「*foo*」 一詞租用戶識別碼為"*123*"編製索引，全文檢索索引中的項目時，"*123foo。*」

每個查詢會轉換為包含使用稱為租用戶識別碼篩選程序的租用戶識別碼。 例如，查詢 」*foo*「 轉換 」 <*guid*>。*foo*和*tenantID*: <*guid*>"，其中 <*guid*> 代表執行查詢的租用戶。 每個索引節點內會發生此查詢轉換和查詢 」 和 「 內容 」 都不處理可能會影響其。 租用戶識別碼會新增至每個查詢，因為在其他租用戶中字詞的頻率無法推斷藉由尋找最佳排名一個租用戶中的相符項目。

租用戶識別碼字詞前面加上只會發生在全文檢索索引。 欄位的搜尋，例如 「*標題： foo*」，請移至的綜合搜尋索引其中字詞不在前面加上租用戶識別碼。 相反地，欄位的搜尋被以欄位名稱。 例如，「*標題： foo*」 的查詢轉換成 「*fields.title:foo AND fields.tenantID*: <*guid*>。 」 因為字詞的頻率不會影響排名的點擊綜合搜尋索引中，便不需要的租用戶的字詞前面加上的區隔。 例如 「*標題： foo*」 欄位搜尋，租用戶內容分隔取決於查詢轉換所篩選的租用戶識別碼。

## <a name="document-access-control-list-checks"></a>文件存取控制清單檢查
搜尋控制透過儲存搜尋索引中的 Acl 的文件的存取。 每個項目是特殊的 ACL 欄位中的字詞集編製索引。 ACL 欄位包含每個群組或使用者，可以檢視文件的一個字詞。 每個查詢進一步強化的存取控制項目 (ACE) 條款，另一個用於每個已驗證的使用者所屬的群組清單。

例如，「 <*guid*> 類似查詢。*foo AND tenantID*: <*guid*>"會變成: 「 <*guid*>。*foo AND tenantID*: <*guid*> *AND* (*docACL:*<*ace1*> *OR docACL*: <*ace2*> *OR docACL*: <*ace3*> *...*)"

因為使用者和群組識別碼並因此 Ace 都是唯一的這會提供額外的僅部分使用者可見的文件的租用戶之間的安全性層級。 相同的情況是特殊 「 所有人外部使用者以外 」 授與存取權的租用戶中的一般使用者的 ACE。 但是公用文件的租用戶分隔 Ace 「 所有人 」 是相同的所有承租人，因為取決於租用戶識別碼篩選。 拒絕 Ace 都支援。 查詢增強新增的子句會拒絕 ACE 相符時，結果中移除文件。

在 Exchange Online 的搜尋索引分割上個別使用者的信箱，而不是如同 SharePoint Online 租用戶識別碼 （訂閱識別碼） 的信箱識別碼。 磁碟分割的機制相當於 SharePoint Online 中，但沒有任何 ACL 篩選。
