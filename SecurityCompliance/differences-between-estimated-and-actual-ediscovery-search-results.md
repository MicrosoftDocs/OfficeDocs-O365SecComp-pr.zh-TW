---
title: Office 365 中的評估及實際的 eDiscovery 搜尋結果之間的差異
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/13/2017
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- SPO160
- MOE150
ms.assetid: 8f20ca4f-a908-46ec-99e6-9890d269ecf2
description: '了解為何評估及實際的搜尋結果可能會有不同的 Office 365 中的 eDiscovery 工具以執行搜尋。 '
ms.openlocfilehash: d3edc73d94d51c2582b6ef2077c5e4c834d1ff82
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296116"
---
# <a name="differences-between-estimated-and-actual-ediscovery-search-results-in-office-365"></a><span data-ttu-id="3a1ef-103">Office 365 中的評估及實際的 eDiscovery 搜尋結果之間的差異</span><span class="sxs-lookup"><span data-stu-id="3a1ef-103">Differences between estimated and actual eDiscovery search results in Office 365</span></span>

<span data-ttu-id="3a1ef-104">本主題適用於您可以使用下列的 Microsoft eDiscovery 工具之一來執行的搜尋：</span><span class="sxs-lookup"><span data-stu-id="3a1ef-104">This topic applies to searches that you can run using one of the following Microsoft eDiscovery tools:</span></span>  <br/>  
- <span data-ttu-id="3a1ef-105">內容搜尋 Office 365 安全性&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="3a1ef-105">Content Search in the Office 365 Security &amp; Compliance Center</span></span>  <br/>  
- <span data-ttu-id="3a1ef-106">在 Exchange 系統管理中心 (EAC) 中的就地 eDiscovery</span><span class="sxs-lookup"><span data-stu-id="3a1ef-106">In-Place eDiscovery in the Exchange admin center (EAC)</span></span>  <br/>  
- <span data-ttu-id="3a1ef-107">SharePoint Online 中的 eDiscovery 中心</span><span class="sxs-lookup"><span data-stu-id="3a1ef-107">The eDiscovery Center in SharePoint Online</span></span>  <br/> 
   
<span data-ttu-id="3a1ef-p101">當您執行的 eDiscovery 搜尋時，您使用此工具會傳回符合搜尋準則評估會有的項目數 （和其大小總計）。例如，當您執行搜尋安全性&amp;規範中心、 預估搜尋結果的顯示所選搜尋的詳細資料窗格中。</span><span class="sxs-lookup"><span data-stu-id="3a1ef-p101">When you run an eDiscovery search, the tool you're using will return an estimate of the number of items (and their total size) that meet the search criteria. For example, when you run a search in the Security &amp; Compliance Center, the estimated search results are displayed in the details pane for the selected search.</span></span>
  
![顯示在已選取搜尋詳細資料窗格中的預估結果](media/74e4ce83-40be-41a9-b60f-5ad447e79fe4.png)
  
<span data-ttu-id="3a1ef-111">這是相同的估計值的總大小和 ediscovery 匯出工具當您將結果匯出至本機電腦和下載及搜尋結果匯出摘要報告中所顯示的項目數。</span><span class="sxs-lookup"><span data-stu-id="3a1ef-111">This is the same estimate of total size and number of items that is displayed in the eDiscovery Export Tool when you export results to a local computer and in the Export Summary report that's downloaded with the search results.</span></span>
  
<span data-ttu-id="3a1ef-112">**EDiscovery 匯出工具中的評估的結果**</span><span class="sxs-lookup"><span data-stu-id="3a1ef-112">**Estimated results in the eDiscovery Export Tool**</span></span>

![eDiscovery 匯出工具中的預估結果](media/d34312a5-0ee6-49aa-9460-7ea0015a6e66.png)
  
<span data-ttu-id="3a1ef-114">**評估的結果匯出摘要報告**</span><span class="sxs-lookup"><span data-stu-id="3a1ef-114">**Estimated results in Export Summary report**</span></span>

![估計的搜尋結果會包含在匯出摘要報告中](media/44b579da-86c2-4f33-81b5-84d604003eda.png)
  
<span data-ttu-id="3a1ef-116">不過，當您將會注意到匯出摘要報告的舊的螢幕擷取畫面中的大小及實際下載的實際的搜尋結果數目的方式不同比的大小和預估的搜尋結果數目。</span><span class="sxs-lookup"><span data-stu-id="3a1ef-116">However, as you'll notice in the previous screenshot of the Export Summary report, the size and number of actual search results that are actually downloaded are different than the size and number of estimated search results.</span></span> 
  
![預估和下載的搜尋結果之間差異](media/84aef318-230f-430d-9d9e-02f21342d364.png)
  
<span data-ttu-id="3a1ef-118">以下是一些原因的這些差異：</span><span class="sxs-lookup"><span data-stu-id="3a1ef-118">Here are some reasons for these differences:</span></span>
  
- <span data-ttu-id="3a1ef-p102">**讓結果預估**-評估會有搜尋結果都便是這麼做，符合搜尋查詢條件的項目評估 （並不實際計數）。若要編譯 Exchange 項目的評估、 郵件符合搜尋準則的識別碼的清單是從 Exchange 資料庫要求您使用 eDiscovery 工具。但是當您匯出搜尋結果時，重新執行搜尋和實際的郵件會從 Exchange 資料庫擷取。讓這些差異可能會造成因如何決定估計的項目數和實際的項目數。</span><span class="sxs-lookup"><span data-stu-id="3a1ef-p102">**The way results are estimated** - An estimate of the search results are just that, an estimate (and not an actual count) of the items that meet the search query criteria. To compile the estimate of Exchange items, a list of the message IDs that meet the search criteria is requested from the Exchange database by the eDiscovery tool you're using. But when you export the search results, the search is re-run and the actual messages are retrieved from the Exchange database. So these differences might result because of how the estimated number of items and the actual number of items are determined.</span></span> 
    
- <span data-ttu-id="3a1ef-p103">**會發生時評估及匯出搜尋結果的時間之間的變更**-匯出搜尋結果時，搜尋是收集搜尋索引中符合搜尋準則的最新項目重新啟動。可能有其他所建立的項目、 在預估的搜尋結果時收集及搜尋結果所匯出時的間隔時間送出，或收到符合搜尋準則。它也有可能的交易時所預估搜尋結果的搜尋索引的項目已不再有因為已從內容的位置中清除之前會匯出搜尋結果。降低此問題的其中一個方法是指定日期範圍的 eDiscovery 搜尋。另一種方法會使項目已受保護而無法清除保留置於內容的位置。</span><span class="sxs-lookup"><span data-stu-id="3a1ef-p103">**Changes that happen between the time when estimating and exporting search results** - When you export search results, the search is re-started to collect that most recent items in the search index that meet the search criteria. It's possible there are additional items were created, sent, or received that meet the search criteria in the time between when the estimated search results were collected and when the search results were exported. It's also possible that items that were in the search index when the search results were estimated are no longer there because they were purged from the content location before the search results are exported. One way to mitigate this issue is to specify a date range for an eDiscovery search. Another way is to place a hold on content locations so that items are preserved and can't be purged.</span></span> 
    
- <span data-ttu-id="3a1ef-p104">**編製索引的項目**相關的搜尋編製索引的項目可能會造成評估及實際的搜尋結果之間的差異。例如，Exchange 和 SharePoint 中的 eDiscovery 中心中的就地 eDiscovery 不包括編製索引的項目 （不符合搜尋準則） 當您執行預估搜尋結果的搜尋。但是您可以在匯出搜尋結果時加入編製索引的項目。如果您包括編製索引的項目匯出搜尋結果時，可能會有多個都要匯出的項目。這會使估計和匯出搜尋結果之間的差異。</span><span class="sxs-lookup"><span data-stu-id="3a1ef-p104">**Unindexed items** - Items that are unindexed for search can cause differences between estimated and actual search results. For example, In-Place eDiscovery in Exchange and the eDiscovery Center in SharePoint don't include unindexed items (that don't meet the search criteria) when you run a search to estimate the search results. But you can include unindexed items when you export the search results. If you include unindexed items when exporting search results, there might be more items that are exported. This will cause a difference between the estimated and exported search results.</span></span> 
    
    <span data-ttu-id="3a1ef-p105">在 [安全性] 中使用 「 內容搜尋工具時&amp;規範中心可選擇包含搜尋評估中編製索引的項目。搜尋傳回編製索引的項目數會列在詳細資料窗格中與其他預估的搜尋結果。任何編製索引的項目也會包含在預估的搜尋結果的總大小。當您匯出搜尋結果時，您必須以包含或不包含編製索引的項目] 選項。如何設定這些選項可能會導致差異之間評估及實際的搜尋結果的下載。</span><span class="sxs-lookup"><span data-stu-id="3a1ef-p105">When using the Content Search tool in the Security &amp; Compliance Center, you have the option to include unindexed items in the search estimate. The number of unindexed items returned by the search is listed in the details pane together with the other estimated search results. Any unindexed items would also be included in the total size of the estimated search results. When you export search results, you have the option to include or not include unindexed items. How you configure these options might result in differences between estimated and the actual search results that are downloaded.</span></span> 
    
- <span data-ttu-id="3a1ef-p106">**匯出搜尋結果的內容包含所有的內容位置**-如果您要匯出結果的搜尋是您的組織，則只有編製索引項目中包含的內容位置中的所有內容位置的搜尋將匯出符合搜尋準則的項目。換句話說，如果沒有搜尋結果中的信箱或站台，然後該信箱或網站的任何編製索引項目將不會匯出。不過，編製索引的項目從所有內容的位置 （即使這些且不含符合搜尋查詢的項目） 將會包含在預估的搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="3a1ef-p106">**Exporting the results of a Content Search that includes all content locations** - If the search that you're exporting results from was a search of all content locations in your organization, then only the unindexed items from content locations that contain items that match the search criteria will be exported. In other words, if no search results are found in a mailbox or site, then any unindexed items in that mailbox or site won't be exported. However, unindexed items from all content locations (even those that don't contain items that match the search query) will be included in the estimated search results.</span></span> 
    
    <span data-ttu-id="3a1ef-p107">或者，如果您要匯出結果的搜尋包含特定內容的位置，然後編製索引的項目 （不排除的搜尋準則） 從搜尋中指定的所有內容位置會匯出。在此例中編製索引的項目數評估及實際匯出編製索引的項目數應相同。</span><span class="sxs-lookup"><span data-stu-id="3a1ef-p107">Alternatively, if the search that you're exporting results from included specific content locations, then unindexed items (that aren't excluded by the search criteria) from all the content locations specified in the search will be exported. In this case, the estimated number of unindexed items and the number of unindexed items actually exported should be the same.</span></span>
    
    <span data-ttu-id="3a1ef-143">無法匯出編製索引的項目從組織中的每個位置的原因是因為它可能會增加匯出錯誤的機率並增加匯出及下載的搜尋結果所花費的時間。</span><span class="sxs-lookup"><span data-stu-id="3a1ef-143">The reason for not exporting unindexed items from every location in the organization is because it might increase the likelihood of export errors and increase the time it takes to export and download the search results.</span></span>
    
- <span data-ttu-id="3a1ef-p108">使用原始的 Exchange 郵件大小計算**與匯出的檔案格式的原始的檔案格式**-For Exchange 的項目，在搜尋結果的估計大小。不過，電子郵件訊息會匯出在 PST 檔案中或以個別的郵件 （這格式化為 EML 檔）。這兩個這些匯出選項使用不同的檔案格式所評估的檔案大小與不同的總匯出的檔案大小會導致該原始交換訊息。</span><span class="sxs-lookup"><span data-stu-id="3a1ef-p108">**Raw file formats versus exported file formats** - For Exchange items, the estimated size of the search results is calculated by using the raw Exchange message sizes. However, email messages are exported in a PST file or as individual messages (which are formatted as EML files). Both of these export options use a different file format that raw Exchange messages, which results in the total exported file size being different than the estimated file size.</span></span> 
    
- <span data-ttu-id="3a1ef-p109">預估的搜尋結果中不要包括**文件版本**-如 SharePoint 文件、 多個版本的文件。但是可能會造成所有文件版本時所要包含匯出搜尋結果中會增加匯出的文件的實際號碼 （與總大小） 選項。</span><span class="sxs-lookup"><span data-stu-id="3a1ef-p109">**Document versions** - For SharePoint documents, multiple versions of a document aren't included in the estimated search results. But you have the option to include all document versions when you export the search results, which will increase the actual number (and total size) of the exported documents.</span></span> 
    
- <span data-ttu-id="3a1ef-p110">**重複資料刪除**-For Exchange 的項目、 重複資料刪除減少都要匯出的項目數。您必須將它們匯出時取消複製搜尋結果] 選項。Exchange 訊息，這表示匯出單一執行個體的訊息是的即使該郵件可能位於多個信箱。預估的搜尋結果包括每個執行個體的訊息。因此，如果您選擇 [重複] 選項匯出搜尋結果時，都要匯出的項目數實際可能許多小於估計項目數。</span><span class="sxs-lookup"><span data-stu-id="3a1ef-p110">**De-duplication** - For Exchange items, de-duplication reduces the number of items that are exported. You have the option to de-duplicate the search results when you export them. For Exchange messages, this means that only a single instance of a message is exported, even though that message might be found in multiple mailboxes. The estimated search results include every instance of a message. So if you choose the de-duplication option when exporting search results, the actual number of items that are exported might be considerably less than the estimated number of items.</span></span> 
    
    <span data-ttu-id="3a1ef-p111">如果您選擇 [重複] 選項應該牢記的另一項重點是 Exchange 的所有項目都要匯出單一的 PST 檔案中並不保留從來源信箱的資料夾結構。匯出的 PST 檔案只包含電子郵件項目。不過，搜尋結果報表會包含每個匯出識別訊息所在的來源信箱的郵件項目。這可協助您找出所有包含重複的郵件的信箱。如果您不要啟用重複資料刪除，個別的 PST 檔案匯出包含在搜尋中每個信箱。</span><span class="sxs-lookup"><span data-stu-id="3a1ef-p111">Another thing to keep in mind if you choose the de-duplication option is that all Exchange items are exported in a single PST file and the folder structure from the source mailboxes isn't preserved. The exported PST file just contains the email items. However, a search results report contains an entry for each exported message that identifies the source mailbox where the message is located. This helps you identify all mailboxes that contain a duplicate message. If you don't enable de-duplication, a separate PST file is exported for each mailbox included in the search.</span></span> 
    
## <a name="exporting-unindexed-items-from-the-ediscovery-center-in-sharepoint-online"></a><span data-ttu-id="3a1ef-159">從 SharePoint Online 中的 eDiscovery 中心匯出編製索引的項目</span><span class="sxs-lookup"><span data-stu-id="3a1ef-159">Exporting unindexed items from the eDiscovery Center in SharePoint Online</span></span>

<span data-ttu-id="3a1ef-p112">在 SharePoint Online 的 eDiscovery 中心，您可選擇只包含編製索引的內容 （Exchange 和 SharePoint） 當您將匯出的 eDiscovery 搜尋結果。選取 [**包含項目找出要加密或已無法辨識的格式**] 選項，以達成此目的。編製索引的項目 （也稱為 uncrawlable SharePoint 中） 是在 Exchange 和 SharePoint 的因任何原因未編製索引的搜尋的項目。編製索引的 Exchange 項目會列在已包含當您將搜尋結果匯出**Exchange 索引錯誤**報告。同樣地，編製索引的 SharePoint 項目會列於**SharePoint 索引錯誤**報告。當您匯出編製索引的項目時，他們正在下載至名為**Uncrawlable**的資料夾。PST 檔案 ； 中隨附編製索引的 Exchange 項目從 SharePoint 每花很多份文件是太下載。編製索引的項目 （如果有的話） 的數目會列在每個索引錯誤報告。在報表中的編製索引項目數應符合下載編製索引項目數。</span><span class="sxs-lookup"><span data-stu-id="3a1ef-p112">In the eDiscovery Center in SharePoint Online, you have the option to include unindexed content (from Exchange and SharePoint) when you export the results of an eDiscovery search. You do this by selecting the **Include items that are encrypted or have an unrecognized format** option. Unindexed items (also called uncrawlable in SharePoint) are items in Exchange and SharePoint that for some reason weren't indexed for search. Unindexed Exchange items are listed in the **Exchange Index Errors** report that's included when you export search results. Similarly, unindexed SharePoint items are listed in **SharePoint Index Errors** report. When you export unindexed items, they're downloaded to a folder named **Uncrawlable**. Unindexed Exchange items are included in a PST file; each unindexed document from SharePoint is downloaded too. The number of unindexed items (if there are any) are listed in each index errors report. The number of unindexed items in the reports should match the number of unindexed items that are downloaded.</span></span> 
  
 <span data-ttu-id="3a1ef-p113">**為何原因如果匯出編製索引的項目數不符合索引錯誤報告中的項目數吗？** 如先前所述，很可能的項目有搜尋評估所執行的時間和搜尋結果所匯出的時間之間清除來自 Office 365。編製索引的項目即會發生類似的不一致。例如，搜尋索引可能出匯出搜尋結果時的日期。這表示該編製索引項目匯出與搜尋結果可能中未列出索引錯誤報告因為此項目未編製索引在搜尋結果所匯出的時間。這會導致更多花很多比索引錯誤報告列出要匯出的項目。同樣地，索引錯誤報告中所列的編製索引項目可能有已清除來自 Office 365 之前已更新的搜尋索引。這會產生較少比索引錯誤報告列出要匯出的編製索引項目。</span><span class="sxs-lookup"><span data-stu-id="3a1ef-p113">**What are some reasons if the number of exported unindexed items don't match the number of items in the index error report?** As previously explained, it's possible that items have been purged from Office 365 between the time the search estimate was run and the time the search results were exported. A similar discrepancy can occur for unindexed items. For example, the search index might be out date when search results are exported. This would mean that an unindexed item that was exported with the search results might not be listed in the index errors report because the item wasn't indexed at the time the search results were exported. This would result in more unindexed items being export than are listed in the index error report. Similarly, an unindexed item listed in the index error report could have been purged from Office 365 before the search index was updated. This would result in fewer unindexed items being export than are listed in the index error report.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="3a1ef-p114">如果您不選取 [**包含項目找出要加密或已無法辨識的格式**] 選項時您匯出搜尋結果或只下載報告、 下載索引錯誤報告但沒有任何項目。這並不代表沒有任何索引的錯誤。它只是表示未列在匯出的編製索引的項目。</span><span class="sxs-lookup"><span data-stu-id="3a1ef-p114">If you don't select the **Include items that are encrypted or have an unrecognized format** option when you export search results or just download the reports, the index error reports are downloaded but they don't have any entries. This doesn't mean there aren't any indexing errors. It just means that unindexed items weren't included in the export.</span></span> 
  

