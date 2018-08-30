---
title: 調查 Office 365 電子文件探索中已局部編製索引的項目
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/26/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 4e8ff113-6361-41e2-915a-6338a7e2a1ed
description: 部分編製索引的項目 （也是呼叫未建立索引項目） 的 Exchange 信箱項目和 SharePoint 的文件和 OneDrive 網站的因任何原因未完全編製索引內容的搜尋。針對本文中了解為何無法編製索引的搜尋項目，以及部分已編製索引的項目所傳回、 識別搜尋錯誤的部分已編製索引的項目，並使用 PowerShell 指令碼來判斷您的組織衝擊部分已編製索引的電子郵件項目。
ms.openlocfilehash: 4e8e8c31e6c5450a9b84a1240c2ae8d891c1bd6f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22527300"
---
# <a name="investigating-partially-indexed-items-in-office-365-ediscovery"></a><span data-ttu-id="a6e68-104">調查 Office 365 電子文件探索中已局部編製索引的項目</span><span class="sxs-lookup"><span data-stu-id="a6e68-104">Investigating partially indexed items in Office 365 eDiscovery</span></span>

<span data-ttu-id="a6e68-p102">您執行從 Office 365 安全性內容搜尋&amp;規範中心自動包含部分已編製索引的項目中預估的搜尋結果時執行搜尋。部分已編製索引的項目是 Exchange 信箱項目及 SharePoint 和 OneDrive 上的商務網站因任何原因未完全編入搜尋索引的文件。大部分的電子郵件與網站的文件已成功編製索引因為其落在[編製索引的電子郵件的限制](limits-for-content-search.md#indexinglimits)內。不過，某些項目超過這些索引的限制，並將部分編製索引。以下是其他項目為何無法編製索引的搜尋及部分已編製索引的項目執行內容的搜尋時所傳回的原因：</span><span class="sxs-lookup"><span data-stu-id="a6e68-p102">A Content Search that you run from the Office 365 Security &amp; Compliance Center automatically includes partially indexed items in the estimated search results when you run a search. Partially indexed items are Exchange mailbox items and documents on SharePoint and OneDrive for Business sites that for some reason weren't completely indexed for search. Most email messages and site documents are successfully indexed because they fall within the [Indexing limits for email messages](limits-for-content-search.md#indexinglimits). However, some items may exceed these indexing limits, and will be partially indexed. Here are other reasons why items can't be indexed for search and are returned as partially indexed items when you run a Content Search:</span></span>
  
- <span data-ttu-id="a6e68-110">電子郵件已附加的檔案不能索引 ； 的檔案類型在大多數情況下，此檔案類型是[無法辨識或不支援為編製索引](partially-indexed-items-in-content-search.md#file-types-not-indexed-for-search)</span><span class="sxs-lookup"><span data-stu-id="a6e68-110">Email messages have an attached file of a file type that can't be indexed; in most cases, the file type is [unrecognized or unsupported for indexing](partially-indexed-items-in-content-search.md#file-types-not-indexed-for-search)</span></span>
    
- <span data-ttu-id="a6e68-111">電子郵件已如圖像檔 ； 有效的處理常式中，而附加的檔案這是部分已編製索引的電子郵件項目的最常見原因</span><span class="sxs-lookup"><span data-stu-id="a6e68-111">Email messages have an attached file without a valid handler, such as image files; this is the most common cause of partially indexed email items</span></span>
    
- <span data-ttu-id="a6e68-112">太多檔案附加至電子郵件訊息</span><span class="sxs-lookup"><span data-stu-id="a6e68-112">Too many files attached to an email message</span></span>
    
- <span data-ttu-id="a6e68-113">附加至電子郵件訊息的檔案會太大</span><span class="sxs-lookup"><span data-stu-id="a6e68-113">A file attached to an email message is too large</span></span>
    
- <span data-ttu-id="a6e68-114">支援的檔案類型編製索引，但在編製時發生錯誤的特定檔案</span><span class="sxs-lookup"><span data-stu-id="a6e68-114">The file type is supported for indexing but an indexing error occurred for a specific file</span></span>
    
<span data-ttu-id="a6e68-p103">雖然它而異，大部分的 Office 365 組織客戶的內容低於 1%大量，擁有的內容低於 12%以部分編製索引的大小。大小與大量之間的差異的原因是較大的檔案具有較高的機率的含有不能完全索引的內容。</span><span class="sxs-lookup"><span data-stu-id="a6e68-p103">Although it varies, most Office 365 organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed. The reason for the difference between the volume versus size is that larger files have a higher probability of containing content that can't be completely indexed.</span></span>
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a><span data-ttu-id="a6e68-117">部分已編製索引的項目計數為何變更搜尋？</span><span class="sxs-lookup"><span data-stu-id="a6e68-117">Why does the partially indexed item count change for a search?</span></span>

<span data-ttu-id="a6e68-p104">Office 365 安全性執行內容的搜尋之後&amp;規範中心、 總數及大小的部分已編製索引的項目所搜尋的位置中列出的詳細統計資料中顯示的搜尋結果統計資料搜尋]。請注意這些稱為*編製索引的項目*中的搜尋統計資料。以下是會影響搜尋結果中傳回的部分已編製索引項目數的一些事項：</span><span class="sxs-lookup"><span data-stu-id="a6e68-p104">After you run a Content Search in the Office 365 Security &amp; Compliance Center, the total number and size of partially indexed items in the locations that were searched are listed in the search result statistics that are displayed in the detailed statistics for the search. Note these are called  *unindexed items*  in the search statistics. Here are a few things that will affect the number of partially indexed items that are returned in the search results:</span></span> 
  
- <span data-ttu-id="a6e68-p105">如果項目部分編製索引和搜尋查詢會比對，它會包含在計數 （和大小） 的搜尋結果項目和部分已編製索引的項目。不過，該相同結果所匯出，項目是搜尋的只包含在搜尋結果; 集它具有不包含為部分已編製索引的項目。</span><span class="sxs-lookup"><span data-stu-id="a6e68-p105">If an item is partially indexed and matches the search query, it's included in both the count (and size) of search result items and partially indexed items. However, when the results of that same search are exported, the item is included only with set of search results; it's not included as a partially indexed item.</span></span>
    
- <span data-ttu-id="a6e68-p106">如果您指定日期範圍的搜尋查詢 （包括其關鍵字查詢中） 或使用一項條件，不符合日期範圍內的任何部分已編製索引項目不包含在部分已編製索引項目的計數。只有部分已編製索引項目屬於日期範圍內已包含在部分已編製索引的項目計數。</span><span class="sxs-lookup"><span data-stu-id="a6e68-p106">If you specify a date range for a search query (by including it in the keyword query or by using a condition), any partially indexed item that doesn't match the date range isn't included in the count of partially indexed items. Only the partially indexed items that fall within date range are included in the count of partially indexed items.</span></span>
    
 <span data-ttu-id="a6e68-p107">**附註：** 部分已編製索引的項目位於 SharePoint 與 OneDrive 網站*不*包含在搜尋的詳細統計資料中所顯示的部分已編製索引的項目評估。不過，當您將匯出的內容的搜尋結果可以匯出部分已編製索引的項目。例如，如果您只搜尋網站內容的搜尋評估的數字中部分已編製索引的項目會為零。</span><span class="sxs-lookup"><span data-stu-id="a6e68-p107">**Note:** Partially indexed items located in SharePoint and OneDrive sites  *are not*  included in the estimate of partially indexed items that's displayed in the detailed statistics for the search. However, partially indexed items can be exported when you export the results of a Content Search. For example, if you only search sites in a Content Search, the estimated number partially indexed items will be zero.</span></span> 
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a><span data-ttu-id="a6e68-128">計算的部分已編製索引的項目在組織中的比率</span><span class="sxs-lookup"><span data-stu-id="a6e68-128">Calculating the ratio of partially indexed items in your organization</span></span>

<span data-ttu-id="a6e68-p108">若要了解您的組織衝擊至部分已編製索引的項目，您可以執行的所有信箱搜尋的所有內容 （使用空白的關鍵字查詢）。在下面的下列範例中，有 56,208 (4,830 MB) 完全編製索引項目和 470 (316 MB) 部分編製索引的項目。</span><span class="sxs-lookup"><span data-stu-id="a6e68-p108">To understand your organization's exposure to partially indexed items, you can run a search for all content in all mailboxes (by using a blank keyword query). In the following example below, there are 56,208 (4,830 MB) fully indexed items and 470 (316 MB) partially indexed items.</span></span>
  
![搜尋統計資料顯示的範例部分編製索引的項目](media/0f6a5cf7-4c98-44a0-a0dd-5aed67124641.png)
  
<span data-ttu-id="a6e68-132">您可以使用下列計算判斷部分已編製索引的項目百分比。</span><span class="sxs-lookup"><span data-stu-id="a6e68-132">You can determine the percentage of partially indexed items by using the following calculations.</span></span>
  
 <span data-ttu-id="a6e68-133">**若要計算的比例的組織中的部分已編製索引項目：**</span><span class="sxs-lookup"><span data-stu-id="a6e68-133">**To calculate the ratio of partially indexed items in your organization:**</span></span>

`(Total number of partially indexed items/Total number of items) x 100`


`(470/56,208) x 100 = 0.84%`
 
<span data-ttu-id="a6e68-134">使用上述範例中，從搜尋結果。 84%的所有信箱項目部分編製索引。</span><span class="sxs-lookup"><span data-stu-id="a6e68-134">By using the search results from the previous example, .84% of all mailboxes items are partially indexed.</span></span>
  
 <span data-ttu-id="a6e68-135">**若要計算您組織中的部分已編製索引項目的大小的百分比：**</span><span class="sxs-lookup"><span data-stu-id="a6e68-135">**To calculate the percentage of the size of partially indexed items in your organization:**</span></span>

`(Size of all partially indexed items/Size of all items) x 100`

`(316 MB/4830 MB) x 100 = 6.54%`

<span data-ttu-id="a6e68-p109">因此在上述範例中，6.54] %的信箱項目總大小是來自部分已編製索引的項目。如先前所述，大部分客戶的內容低於 1%磁碟區，擁有的內容低於 12%以部分編製索引的大小的 Office 365 組織。</span><span class="sxs-lookup"><span data-stu-id="a6e68-p109">So in the previous example, 6.54% of the total size of mailbox items are from partially indexed items. As previously stated, most Office 365 organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span>

## <a name="working-with-partially-indexed-items"></a><span data-ttu-id="a6e68-138">部分使用編製索引的項目</span><span class="sxs-lookup"><span data-stu-id="a6e68-138">Working with partially indexed items</span></span>

<span data-ttu-id="a6e68-p110">在的情況下您要檢查部分來驗證這些不包含下列相關資訊，您可以[將內容搜尋報表匯出](export-a-content-search-report.md)的項目包含部分已編製索引項目的相關資訊。當您將匯出的內容搜尋報告時，請務必選擇其中一個包含部分已編製索引的項目匯出選項。</span><span class="sxs-lookup"><span data-stu-id="a6e68-p110">In cases when you need to examine partially items to validate that they don't contain relevant information, you can [export a content search report](export-a-content-search-report.md) that contains information about partially indexed items. When you export a content search report, be sure to choose one of the export options that includes partially indexed items.</span></span> 
  
![選擇部分已編製索引的項目匯出的第二個或第三個選項](media/624a62b4-78f7-4329-ab5d-e62e3b369885.png)
  
<span data-ttu-id="a6e68-p111">當您匯出內容的搜尋結果或使用其中一個選項內容的搜尋報告時，匯出包含名為花很多 Items.csv 報表。這份報告包含大部分的資訊與 ResultsLog.csv 檔案 ； 相同但是花很多 Items.csv 檔案也包含兩個部分已編製索引項目的相關的欄位：**錯誤標記**和**錯誤屬性**。這些欄位包含每個部分已編製索引項目的索引錯誤的資訊。使用這兩個欄位中的資訊可協助您決定針對特定索引錯誤影響您調查。若是如此，您可以執行目標內容搜尋與匯出及擷取特定的電子郵件訊息與 SharePoint 或 OneDrive 文件，讓您可以檢查其決定是否它們與您正在調查相關。如需逐步說明，請參閱 ＜ [Prepare for Office 365 中的目標內容搜尋 CSV 檔案](csv-file-for-an-id-list-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="a6e68-p111">When you export content search results or a content search report using one of these options, the export includes a report named Unindexed Items.csv. This report includes most of the same information as the ResultsLog.csv file; however, the Unindexed Items.csv file also includes two fields related to partially indexed items: **Error Tags** and **Error Properties**. These fields contain information about the indexing error for each partially indexed item. Using the information in these two fields can help you determine whether or not the indexing error for a particular impacts your investigation. If it does, you can perform a targeted content search and retrieve and export specific email messages and SharePoint or OneDrive documents so that you can examine them to determine if they're relevant to your investigation. For step-by-step instructions, see [Prepare a CSV file for a targeted Content Search in Office 365](csv-file-for-an-id-list-content-search.md).</span></span>
  
 <span data-ttu-id="a6e68-p112">**附註：** 編製索引的 Items.csv 檔案還包含名為**錯誤類型**和**錯誤訊息**的欄位。這些是舊版欄位包含**錯誤標記**和**錯誤屬性**欄位中，但具有較少的詳細資訊的資訊類似的資訊。您可以放心地忽略這些舊版的欄位。</span><span class="sxs-lookup"><span data-stu-id="a6e68-p112">**Note:** The Unindexed Items.csv file also contains fields named **Error Type** and **Error Message**. These are legacy fields that contain information that is similar to the information in the **Error Tags** and **Error Properties** fields, but with less detailed information. You can safely ignore these legacy fields.</span></span> 
  
## <a name="errors-related-to-partially-indexed-items"></a><span data-ttu-id="a6e68-151">與部分已編製索引的項目相關的錯誤</span><span class="sxs-lookup"><span data-stu-id="a6e68-151">Errors related to partially indexed items</span></span>

<span data-ttu-id="a6e68-p113">錯誤標記所組成的資訊、 錯誤和檔案類型的兩個部分。例如，在此錯誤/filetype 配對：</span><span class="sxs-lookup"><span data-stu-id="a6e68-p113">Error tags are made up of two pieces of information, the error and the file type. For example, in this error/filetype pair:</span></span>

```
 parseroutputsize_xls
```

   
 <span data-ttu-id="a6e68-p114">`parseroutputsize`錯誤與`xls`是發生錯誤之檔案的檔案類型。案例皆未辨識的檔案類型或檔案類型不帶不會套用到錯誤，您會看到值`noformat`取代此檔案類型。</span><span class="sxs-lookup"><span data-stu-id="a6e68-p114">`parseroutputsize` is the error and  `xls` is the file type of the file the error occurred on. In cases were the file type wasn't recognized or the file type was doesn't apply to the error, you will see the value  `noformat` in place of the file type.</span></span> 
  
<span data-ttu-id="a6e68-156">以下是原因的編製索引的錯誤和錯誤的可能描述的清單。</span><span class="sxs-lookup"><span data-stu-id="a6e68-156">The following is a list of indexing errors and a description of the possible cause of the error.</span></span>
  
|<span data-ttu-id="a6e68-157">**錯誤標記**</span><span class="sxs-lookup"><span data-stu-id="a6e68-157">**Error tag**</span></span>|<span data-ttu-id="a6e68-158">**描述**</span><span class="sxs-lookup"><span data-stu-id="a6e68-158">**Description**</span></span>|
|:-----|:-----|
| `attachmentcount` <br/> |<span data-ttu-id="a6e68-159">電子郵件有太多的附件，以及這些附件的一些未處理。</span><span class="sxs-lookup"><span data-stu-id="a6e68-159">An email message had too many attachments, and some of these attachments weren't processed.</span></span>  <br/> |
| `attachmentdepth` <br/> |<span data-ttu-id="a6e68-p115">內容擷取器和文件剖析器找到太多層的巢狀其他附件的附件。這些附件的一些不處理。</span><span class="sxs-lookup"><span data-stu-id="a6e68-p115">The content retriever and document parser found too many levels of attachments nested inside other attachments. Some of these attachments were not processed.</span></span>  <br/> |
| `attachmentrms` <br/> |<span data-ttu-id="a6e68-162">附件失敗解碼因為與其受 RMS 保護。</span><span class="sxs-lookup"><span data-stu-id="a6e68-162">An attachment failed decoding because it was RMS-protected.</span></span>  <br/> |
| `attachmentsize` <br/> |<span data-ttu-id="a6e68-163">附加至電子郵件訊息檔太大及無法處理。</span><span class="sxs-lookup"><span data-stu-id="a6e68-163">A file attached to an email message was too large and couldn't be processed.</span></span>  <br/> |
| `indexingtruncated` <br/> |<span data-ttu-id="a6e68-p116">當撰寫之已處理的電子郵件至索引，其中一個索引的屬性太大而且已被截斷。截斷的屬性列示於錯誤屬性欄位。</span><span class="sxs-lookup"><span data-stu-id="a6e68-p116">When writing the processed email message to the index, one of the indexable properties was too large and was truncated. The truncated properties are listed in Error Properties field.</span></span>  <br/> |
| `invalidunicode` <br/> |<span data-ttu-id="a6e68-p117">電子郵件訊息中包含無法處理為有效的 Unicode 文字。這個項目編製索引可能不完整。</span><span class="sxs-lookup"><span data-stu-id="a6e68-p117">An email message contained text that couldn't be processed as valid Unicode. Indexing for this item may be incomplete.</span></span>  <br/> |
| `parserencrypted` <br/> |<span data-ttu-id="a6e68-168">加密附件或電子郵件的內容，和 Office 365 無法建立解碼內容。</span><span class="sxs-lookup"><span data-stu-id="a6e68-168">The content of attachment or email message is encrypted, and Office 365 couldn't decode the content.</span></span>  <br/> |
| `parsererror` <br/> |<span data-ttu-id="a6e68-p118">分析處理時發生未知的錯誤。這通常會產生軟體錯誤或服務損毀。</span><span class="sxs-lookup"><span data-stu-id="a6e68-p118">An unknown error occurred during parsing. This typically results from a software bug or a service crash.</span></span>  <br/> |
| `parserinputsize` <br/> |<span data-ttu-id="a6e68-171">會在附件已太大剖析器處理，以及該附件的剖析沒有發生或未完成。</span><span class="sxs-lookup"><span data-stu-id="a6e68-171">An attachment was too large for the parser to handle, and the parsing of that attachment didn't happen or wasn't completed.</span></span>  <br/> |
| `parsermalformed` <br/> |<span data-ttu-id="a6e68-p119">附件格式不正確，而且無法剖析器所處理。此結果從可以舊檔案格式相容軟體或病毒假冒設為某個項目比其他宣告所建立的檔案。</span><span class="sxs-lookup"><span data-stu-id="a6e68-p119">An attachment was malformed and couldn't be handled by the parser. This result from can old file formats, files created by incompatible software, or viruses pretending to be something other than claimed.</span></span>  <br/> |
| `parseroutputsize` <br/> |<span data-ttu-id="a6e68-174">附件的剖析的輸出太大而必須將會遭到截斷。</span><span class="sxs-lookup"><span data-stu-id="a6e68-174">The output from the parsing of an attachment was too large and had to be truncated.</span></span>  <br/> |
| `parserunknowntype` <br/> |<span data-ttu-id="a6e68-175">會在附件有 Office 365 無法偵測的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="a6e68-175">An attachment had a file type that Office 365 couldn't detect.</span></span>  <br/> |
| `parserunsupportedtype` <br/> |<span data-ttu-id="a6e68-176">會在附件有 Office 365could 偵測，但剖析該檔案類型不支援的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="a6e68-176">An attachment had a file type that Office 365could detect, but parsing that file type isn't supported.</span></span>  <br/> |
| `propertytoobig` <br/> |<span data-ttu-id="a6e68-p120">電子郵件屬性的值在 Exchange 儲存區已經太大而無法擷取並無法處理郵件。這通常只會以電子郵件訊息的本文屬性。</span><span class="sxs-lookup"><span data-stu-id="a6e68-p120">The value of an email property in Exchange Store was too large to be retrieved and the message couldn't be processed. This typically only happens to the body property of an email message.</span></span>  <br/> |
| `retrieverrms` <br/> |<span data-ttu-id="a6e68-179">內容擷取器無法解碼 RMS 受保護的郵件。</span><span class="sxs-lookup"><span data-stu-id="a6e68-179">The content retriever failed to decode an RMS-protected message.</span></span>  <br/> |
| `wordbreakertruncated` <br/> |<span data-ttu-id="a6e68-p121">太多字已編製索引期間識別文件中。到達限制時停止處理屬性與屬性會遭到截斷。</span><span class="sxs-lookup"><span data-stu-id="a6e68-p121">Too many words were identified in the document during indexing. Processing of the property stopped when reaching the limit, and the property is truncated.</span></span>  <br/> |
   
<span data-ttu-id="a6e68-p122">錯誤欄位說明哪些欄位受到錯誤標記] 欄位中所列之處理錯誤。如果您例如搜尋屬性`subject`或`participants`，錯誤訊息的本文中將不會影響您的搜尋結果。這有助於決定完全哪些您可能需要進一步調查的部分已編製索引項目時。</span><span class="sxs-lookup"><span data-stu-id="a6e68-p122">Error fields describe which fields are affected by the processing error listed in the Error Tags field. If you're searching a property such as  `subject` or  `participants`, errors in the body of the message won't impact the results of your search. This can be useful when determining exactly which partially indexed items you might need to further investigate.</span></span>
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a><span data-ttu-id="a6e68-185">若要判斷您的組織衝擊部分已編製索引的電子郵件項目的使用 PowerShell 指令碼</span><span class="sxs-lookup"><span data-stu-id="a6e68-185">Using a PowerShell script to determine your organization's exposure to partially indexed email items</span></span>

<span data-ttu-id="a6e68-p123">下列步驟顯示如何執行 PowerShell 指令碼會搜尋所有的 Exchange 信箱中的所有項目和 （依計數以及由大小） 將會產生您組織的比例的部分已編製索引的電子郵件項目有關的報表並顯示的項目數 （和其檔案類型） 的每個索引所發生的錯誤。使用在前一節中的錯誤標記描述來識別索引的錯誤。</span><span class="sxs-lookup"><span data-stu-id="a6e68-p123">The following steps show you how to run a PowerShell script that searches for all items in all Exchange mailboxes, and then generates a report about your organization's ratio of partially indexed email items (by count and by size) and displays the number of items (and their file type) for each indexing error that occurs. Use the error tag descriptions in the previous section to identify the indexing error.</span></span>
  
1. <span data-ttu-id="a6e68-188">使用.ps1; filename 尾碼將下列文字儲存到 Windows PowerShell 指令碼檔案例如， `PartiallyIndexedItems.ps1`。</span><span class="sxs-lookup"><span data-stu-id="a6e68-188">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `PartiallyIndexedItems.ps1`.</span></span>

```
  write-host "**************************************************"
  write-host "     Office 365 Security &amp; Compliance Center      " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "   eDiscovery Partially Indexed Item Statistics   " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "**************************************************"
  " " 
  # Create a search with Error Tags Refinders enabled
  Remove-ComplianceSearch "RefinerTest" -Confirm:$false -ErrorAction 'SilentlyContinue'
  New-ComplianceSearch -Name "RefinerTest" -ContentMatchQuery "size>0" -RefinerNames ErrorTags -ExchangeLocation ALL
  Start-ComplianceSearch "RefinerTest"
  # Loop while search is in progress
  do{
      Write-host "Waiting for search to complete..."
      Start-Sleep -s 5
      $complianceSearch = Get-ComplianceSearch "RefinerTest"
  }while ($complianceSearch.Status -ne 'Completed')
  $refiners = $complianceSearch.Refiners | ConvertFrom-Json
  $errorTagProperties = $refiners.Entries | Get-Member -MemberType NoteProperty
  $partiallyIndexedRatio = $complianceSearch.UnindexedItems / $complianceSearch.Items
  $partiallyIndexedSizeRatio = $complianceSearch.UnindexedSize / $complianceSearch.Size
  " "
  "===== Partially indexed items ====="
  "         Total          Ratio"
  "Count    {0:N0}{1:P2}" -f $complianceSearch.Items.ToString("N0").PadRight(15, " "), $partiallyIndexedRatio
  "Size(GB) {0:N2}{1:P2}" -f ($complianceSearch.Size / 1GB).ToString("N2").PadRight(15, " "), $partiallyIndexedSizeRatio
  " "
  Write-Host ===== Reasons for partially indexed items =====
  foreach($errorTagProperty in $errorTagProperties)
  {
      $name = $refiners.Entries.($errorTagProperty.Name).Name
      $count = $refiners.Entries.($errorTagProperty.Name).TotalCount
      $frag = $name.Split("{_}")
      $errorTag = $frag[0]
      $fileType = $frag[1]
      if ($errorTag -ne $lastErrorTag)
      {
          $errorTag
      }
      "    " + $fileType + " => " + $count
      $lastErrorTag = $errorTag
  }
  
```
   
2. <span data-ttu-id="a6e68-189">[連線至 Office 365 安全性&amp;規範中心 PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627084)。</span><span class="sxs-lookup"><span data-stu-id="a6e68-189">[Connect to Office 365 Security &amp; Compliance Center PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627084).</span></span>
    
3. <span data-ttu-id="a6e68-190">安全性&amp;規範中心 PowerShell 中移至您在步驟 1 中，儲存指令碼的資料夾，然後執行指令碼 ；例如：</span><span class="sxs-lookup"><span data-stu-id="a6e68-190">In Security &amp; Compliance Center PowerShell, go to the folder where you saved the script in step 1, and then run the script; for example:</span></span>

    ```
    .\PartiallyIndexedItems.ps1
    ```
   
<span data-ttu-id="a6e68-191">以下是範例於指令碼所傳回的輸出。</span><span class="sxs-lookup"><span data-stu-id="a6e68-191">Here's an example fo the output returned by the script.</span></span>
  
![從指令碼所產生您組織的曝光度至部分已編製索引的電子郵件項目上的報表輸出範例](media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)
  
<span data-ttu-id="a6e68-193">注意下列事項：</span><span class="sxs-lookup"><span data-stu-id="a6e68-193">Note the following:</span></span>
  
1. <span data-ttu-id="a6e68-194">總人數及的電子郵件項目大小與您的組織比例的部分已編製索引的電子郵件項目 （依計數以及由大小）</span><span class="sxs-lookup"><span data-stu-id="a6e68-194">The total number and size of email items, and your organization's ratio of partially indexed email items (by count and by size)</span></span>
    
2. <span data-ttu-id="a6e68-195">清單錯誤標記及對應的檔案類型發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="a6e68-195">A list error tags and the corresponding file types for which the error occurred.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a6e68-196">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a6e68-196">See also</span></span>

[<span data-ttu-id="a6e68-197">位於 Office 365 中內容搜尋的已局部編製索引項目</span><span class="sxs-lookup"><span data-stu-id="a6e68-197">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)
