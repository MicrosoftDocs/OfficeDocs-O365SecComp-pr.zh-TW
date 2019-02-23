---
title: 搜尋與標記
ms.author: chrfox
author: chrfox
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 22f5adad-1bc0-460d-94a9-8732929f5b99
description: 進階 eDiscovery 中搜尋和標記模組可讓您搜尋、 預覽，並將組織中您案例的文件。目前的本單元處於 beta。
ms.openlocfilehash: 58913a01f30b4169470592f5fc271e3ce785ac5d
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30222962"
---
# <a name="search-and-tagging"></a>搜尋與標記

進階 eDiscovery 中搜尋和標記模組可讓您搜尋、 預覽，並將組織中您案例的文件。目前的本單元處於 beta。搜尋及標記的簡短示範，請參閱[管理您的資料與進階 eDiscovery](https://www.youtube.com/watch?v=VaPYL3DHP6I)影片。

> [!NOTE]
> 進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
## <a name="search-the-documents-in-your-case"></a>在您的案例中搜尋文件

您已處理文件中的進階的 eDiscovery 案例 （並選擇性地執行分析或相關性模組之後），您可以使用搜尋及標記搜尋文件並再將它們組織套用特定案例的標籤 （也稱為標籤）。您可以定義搜尋查詢使用所提供的條件卡或使用 KQL 類似的查詢語言中的關鍵字條件卡片。一般 KQL 語法，例如 AND、 OR、 NOT、 NEAR(n) 且支援，以及行尾的多重字元萬用字元 （*）。 

下表列出您可以搜尋使用 KQL 關鍵字查詢的屬性。或者，您可以使用進階的 eDiscovery 搜尋工具中的條件卡片新增至搜尋查詢的條件 （適用於選取的內容）。

|**屬性**|**描述**|
|:-----|:-----|
|**caselabel** <br/> | 建立/時套用標記的文件的標記名稱。 <br/> |
|**okay** <br/> | 文件 ； 相關聯 okay主旨來限制。 <br/> |
|**日期** <br/> | 傳送電子郵件 ； 日期網站文件的修改的日期。 <br/> |
|**所 fileid** <br/> | 檔案中的識別碼大小寫。 <br/> |
|**filetype** <br/> | 原生副檔名。 <br/> |
|**fileclass** <br/> | 電子郵件、 文件或附件。 <br/> |
|**senderauthor** <br/> | 寄件者的電子郵件 ；網站文件的作者。 <br/> |
|**大小** <br/> | Kb 的檔案大小。 <br/> |
|**subjecttitle** <br/> | 電子郵件 ； 主旨網站文件的標題。 <br/> |
|**bcc** <br/> | 電子郵件的密件副本] 欄位。 <br/> |
|**cc** <br/> | 電子郵件的 [副本] 欄位。 <br/> |
|**參與者** <br/> | 所有參與者的電子郵件執行緒，其中包含連結遺漏的電子郵件地址。 <br/> |
|**接收** <br/> | 接收的電子郵件的日期。 <br/> |
|**收件者** <br/> | 收件者電子郵件中包含 [收件者]、 [副本] 或 [密件副本] 欄位。 <br/> |
|**sender** <br/> | 電子郵件的寄件者。 <br/> |
|**lastmodifieddate** <br/> | 上次修改日期的網站文件。 <br/> |
|**傳送** <br/> | 傳送電子郵件的日期。 <br/> |
|**若要** <br/> | 電子郵件] 欄位中所列的收件者。 <br/> |
|**作者** <br/> | 網站文件的作者。 <br/> |
|**標題** <br/> | 網站文件的標題。 <br/> |
|**dominanttheme**\* <br/> | 項目主佈景主題。 <br/> |
|**themeslist**\* <br/> | 與項目相關聯的佈景主題。 <br/> |
|**readpercentile_ [issuenum]**\*\* <br/> | 讀取百分位數的項目，如 [issuenum] 所定義的問題。 <br/> |
|**relevancescore_ [issuenum]**\*\* <br/> | [Issuenum] 所定義的問題項目、 相關性分數。 <br/> |
|**relevancetag_ [tagname]**\*\* <br/> | 如果項目有手動已標記為 [tagname] 所定義之標籤的相關性。 <br/> |
|||

\*如果已經執行 [佈景主題模組只提供。

\*\*如果已經執行 [相關性] 模組只提供。

或者，您可以使用進階的 eDiscovery 搜尋工具中的條件卡新增至搜尋查詢的條件 （適用於選取的內容）。下列螢幕擷取畫面顯示可以新增至查詢的條件。[**群組**] 欄會指出是否將屬性套用至電子郵件、 網站文件或這兩者 （以*通用*值）。此欄也會識別之後執行相關性模組都是可用的可搜尋屬性。

![進階的 eDiscovery 搜尋工具中的搜尋條件](media/AeDSearchConditions.png)

如需可搜尋的內容的詳細資訊，請參閱[關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。
  
## <a name="see-also"></a>另請參閱

[Office 365 進階電子文件探索](office-365-advanced-ediscovery.md)
  
[了解評估的相關性](assessment-in-relevance-in-advanced-ediscovery.md)
  
[標記及評估](tagging-and-assessment-in-advanced-ediscovery.md)
  
[標記及相關性訓練](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[追蹤相關性分析](track-relevance-analysis-in-advanced-ediscovery.md)
  
[決定所得的結果](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[測試相關性分析](test-relevance-analysis-in-advanced-ediscovery.md)

