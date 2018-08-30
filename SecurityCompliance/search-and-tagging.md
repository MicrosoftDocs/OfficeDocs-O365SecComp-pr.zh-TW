---
title: 搜尋與標記
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 22f5adad-1bc0-460d-94a9-8732929f5b99
description: 進階 eDiscovery 中搜尋和標記模組可讓您搜尋、 預覽，並將組織中您案例的文件。目前的本單元處於 beta。
ms.openlocfilehash: fde887e496e9a40aa88d841053a0c66e48f04200
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526833"
---
# <a name="search-and-tagging"></a>搜尋與標記

進階 eDiscovery 中搜尋和標記模組可讓您搜尋、 預覽，並將組織中您案例的文件。目前的本單元處於 beta。

> [!NOTE]
> 進階的 eDiscovery 需要您組織與進階規範附加元件或 E5 訂閱 Office 365 E3。如果您不具有該對應並想要嘗試進階的 eDiscovery，您還可以[註冊 Office 365 企業版 E5 的試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
## <a name="search-the-documents-in-your-case"></a>在您的案例中搜尋文件

一旦您已處理文件中的進階 eDiscovery 並選擇性地執行分析模組或相關性模組，您可以使用搜尋和標記搜尋透過案例中的文件並將它們組織使用特定案例的標籤。您可以定義您使用所提供的條件卡的查詢或透過 KQL 類似的查詢語言中的關鍵字條件卡片。一般 KQL 語法，例如 AND、 OR、 NOT、 NEAR(n) 且支援，以及行尾的多重字元萬用字元 （*）。這些屬性所支援的查詢語言屬性名稱：

- caselabel： 建立/套用標記中搜尋和標記針對此案例 
- custodians: custodians 指派的情況下-受限於限制
- 日期： 傳送電子郵件的日期、 修改日期為文件
- 所 fileid： 檔案內大小寫的識別碼
- filetype： 原生副檔名
- fileclass： 電子郵件、 文件或附件
- senderauthor： 寄件者的電子郵件、 文件的作者
- 大小： KB 的檔案大小
- subjecttitle： 主旨的電子郵件、 文件的標題
- bcc
- cc
- 參與者： 電子郵件地址的電子郵件執行緒，包括的連結遺漏中的所有參與者
- 收到： 接收日期
- 收件者： 電子郵件收件者的名稱或位址 （、 [副本]、 [密件副本)
- sender
- lastmodifieddate： 上次修改日期的文件
- 傳送： 傳送電子郵件的日期
- 到
- 作者： 作者的電子郵件
- 標題： 文件標題
- dominanttheme： 主佈景主題的項目\*
- themeslist： 與項目相關聯的佈景主題\*
- readpercentile_ [issuenum]： 閱讀百分位數的問題 [issuenum] 項目\*\*
- relevancescore_ [issuenum]: 問題 [issuenum] 項目的相關性分數\*\*
- relevancetag_ [issuenum]： 如果項目已手動標記的相關性，其標籤的 [issuenum]\*\*

\*如果已經執行 [佈景主題] 模組的唯一可用\*\*只能如果已經執行 [相關性] 模組
  
## <a name="see-also"></a>另請參閱

[Office 365 進階電子文件探索](office-365-advanced-ediscovery.md)
  
[了解評估的相關性](assessment-in-relevance-in-advanced-ediscovery.md)
  
[標記及評估](tagging-and-assessment-in-advanced-ediscovery.md)
  
[標記及相關性訓練](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[追蹤相關性分析](track-relevance-analysis-in-advanced-ediscovery.md)
  
[決定所得的結果](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[測試相關性分析](test-relevance-analysis-in-advanced-ediscovery.md)

