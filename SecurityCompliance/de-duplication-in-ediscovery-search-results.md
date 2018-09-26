---
title: 電子文件探索搜尋結果中的重複資料刪除
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/21/2016
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid: MOE150
ms.assetid: 5af334b6-a15d-4f73-97f8-1423457d9f6b
description: 您必須取消重複以便只有一個電子郵件的副本匯出即使多個執行個體相同訊息可能會有不同的信箱中找到都要匯出的 eDiscovery 搜尋結果的選項。
ms.openlocfilehash: 5e54f0e5841fdbd29d1ab8b6b9509ff06e827920
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038006"
---
# <a name="de-duplication-in-ediscovery-search-results"></a>電子文件探索搜尋結果中的重複資料刪除

本文說明如何重複資料刪除 eDiscovery 搜尋結果的運作方式，以及說明重複資料刪除演算法的限制。
  
使用 Office 365 eDiscovery 工具來匯出 eDiscovery 搜尋結果，必須取消重複都要匯出結果的選項。這代表什麼意義？當您啟用重複資料刪除 （根據預設，重複資料刪除不啟用），只有一個電子郵件的副本匯出即使多個執行個體相同的訊息可能會有已搜尋的信箱中找到。重複資料刪除可協助您降低您已檢閱和分析後搜尋結果都要匯出的項目數，以節省時間。但是請務必瞭解重複資料刪除的運作方式與要知道有可能導致一個唯一的項目匯出程序期間標示為重複的演算法的限制。
  
## <a name="how-duplicate-messages-are-identified"></a>如何重複的郵件會被識別

Office 365 eDiscovery 工具可用於判斷訊息是否重複下列電子郵件屬性的組合：
  
- **InternetMessageId**這個屬性會指定電子郵件訊息，即是指特定郵件的特定版本的全域唯一識別碼的網際網路郵件識別碼。此識別碼會產生由寄件者的電子郵件用戶端程式或主機可將郵件傳送的電子郵件系統。如果人員將訊息傳送給多個收件者、 網際網路訊息識別碼都會相同之郵件的每個執行個體。原始郵件的後續修訂就會得到的不同郵件識別碼。 
    
- **ConversationTopic**其屬性指定的訊息之交談記錄的主旨。**ConversationTopic**屬性的值是說明交談的整體主題的字串。保育所組成的初始訊息及回覆傳送給初始訊息的所有郵件。相同交談中的郵件都有**ConversationTopic**屬性相同的值。此屬性的值通常是從初始產生交談的郵件主旨行。 
    
- **BodyTagInfo** -這是內部 Exchange 儲存區屬性。此屬性的值會計算檢查郵件內文中的各種屬性。此屬性用來找出的郵件內文中的差異。 
    
EDiscovery 匯出程序期間符合搜尋準則每封郵件比較這三個屬性。如果這些屬性相同的兩個 （或多個） 的郵件，那些郵件會決定要重複項目和結果是啟用重複資料刪除時將匯出的只有一個郵件的副本。匯出郵件稱為"來源 item"。包含在匯出的搜尋結果**Results.csv**和**Manifest.xml**報告包含重複的郵件的相關資訊。在**Results.csv**檔案並將重複的郵件可識別的**重複項目**] 欄中有一個值。此資料行中的值會比對先前已匯出之郵件的 [**項目身分識別**] 欄中的值。 
  
下列圖形顯示如何重複訊息**Results.csv**和**Manifest.xml**報表匯出與搜尋結果中顯示。這些報告不包含電子郵件屬性先前所述，使用中的重複資料刪除演算法。而是報告包含指派給項目依據] Exchange 儲存區的**項目 Identity**屬性。 
  
 ### <a name="resultscsv-report-viewed-in-excel"></a>Results.csv 報表 （在 Excel 中檢視）
  
![檢視 Results.csv 報表中的重複項目相關的資訊](media/e3d64004-3b91-4cba-b6f3-934b46cbdcdb.png)
  
 ### <a name="manifestxml-report-viewed-in-excel"></a>Manifest.xml 報表 （在 Excel 中檢視）
  
![Manifest.xml 報告中檢視重複的項目相關的資訊](media/69aa4786-9883-46ff-bcae-b35e0daf4a6d.png)
  
此外，匯出報告中所包含重複的郵件來自其他屬性。這包括重複的訊息位於，已將郵件傳送至通訊群組，以及是否郵件已將 [副本] 或 [密件副本位置的分散式另一位使用者的信箱。
  
## <a name="limitations-of-the-de-duplication-algorithm"></a>重複資料刪除演算法的限制

有已知的限制可能會導致取得標示重複的值為唯一項目重複資料刪除演算法。請務必了解這些限制讓您可以決定要使用選用的重複資料刪除功能。
  
有一種情況下其中重複資料刪除功能可能會遭找出郵件為複本並不將它匯出 （但仍引用為匯出報告中重複）。這些是使用者編輯但不會傳送的郵件。例如，假設使用者在 Outlook 中選取一則訊息、 複製郵件的內容並再將其貼在新的郵件。然後使用者移除或新增附件，或變更的主旨或本文本身有變更其中一個複本。如果這兩個訊息符合 eDiscovery 搜尋的查詢，搜尋結果都要匯出啟用重複資料刪除時要匯出的郵件僅需一個。所以即使變更原始郵件或複製的郵件、 先前的修訂郵件已傳送與因此**InternetMessageId**、 **ConversationTopic**及**BodyTagInfo**屬性的值未更新。但如先前所述，這兩個訊息將會列在匯出報表 
  
請注意唯一的訊息可以也標示為重複項目寫入時複製 」 頁面保護功能啟用時，要設為訴訟暫止或就地保留信箱的大小寫相同。寫入時複製功能原始郵件會複製 （並將它儲存在使用者的 [可復原的項目] 資料夾的 [版本] 資料夾中） 儲存原始項目來修訂版之前。在此例中的修訂的複本與原始郵件 （在 [可復原的項目] 資料夾中） 可能會被視為重複的郵件與因此僅有一個會匯出。
  
> [!IMPORTANT]
> 如果重複資料刪除演算法的限制可能會影響搜尋結果的品質，您不應該啟用重複資料刪除項目匯出時。若本節所述的情況可能互不因素在搜尋結果中，且您想要減少很有可能是重複的項目數，則應考慮啟用重複資料刪除。 
  
## <a name="more-information"></a>詳細資訊

- 匯出使用下列的 eDiscovery 工具之一的搜尋結果時適用本文中的資訊：
    
  - Office 365 安全性內容搜尋&amp;規範中心
    
  - Exchange Online 中的就地 eDiscovery
    
  - SharePoint Online 中的 eDiscovery 中心
    
- 如需匯出搜尋結果的詳細資訊，請參閱：
    
  - [從 Office 365 安全性匯出搜尋結果&amp;規範中心](export-search-results.md)
    
  - [從 Office 365 安全性匯出內容搜尋報表&amp;規範中心](export-a-content-search-report.md)
    
  - [匯出就地 eDiscovery 搜尋結果的 PST 檔案](https://go.microsoft.com/fwlink/p/?linkid=832671)
    
  - [在 eDiscovery 中心匯出內容及建立報告](https://support.office.com/article/7b2ea190-5f9b-4876-86e5-4440354c381a)
