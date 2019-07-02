---
title: 高級 eDiscovery 限制
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 深入瞭解 Microsoft 365 中的高級 eDiscovery 解決方案的作用限制。 這包括案例限制、索引限制, 以及使用搜尋工具收集案例資料時的搜尋限制。
ms.openlocfilehash: 622d2669457a2a1e84909aadae9b653ca37684ce
ms.sourcegitcommit: 803baca9f99a6691fb41a3308e799752e4d8f20c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2019
ms.locfileid: "35222287"
---
# <a name="limits-in-advanced-ediscovery"></a><span data-ttu-id="915fd-104">進階電子文件探索的限制</span><span class="sxs-lookup"><span data-stu-id="915fd-104">Limits in Advanced eDiscovery</span></span>

<span data-ttu-id="915fd-105">本文說明 Microsoft 365 中的高級 eDiscovery 解決方案的限制。</span><span class="sxs-lookup"><span data-stu-id="915fd-105">This article describes the limits in the Advanced eDiscovery solution in Microsoft 365.</span></span>

## <a name="case-limits"></a><span data-ttu-id="915fd-106">案例限制</span><span class="sxs-lookup"><span data-stu-id="915fd-106">Case limits</span></span>

<span data-ttu-id="915fd-107">下表列出高級 eDiscovery 中案例的限制。</span><span class="sxs-lookup"><span data-stu-id="915fd-107">The following table lists the limits for cases in Advanced eDiscovery.</span></span>

|<span data-ttu-id="915fd-108">**限制的描述**</span><span class="sxs-lookup"><span data-stu-id="915fd-108">**Description of limit**</span></span>|<span data-ttu-id="915fd-109">**限制**</span><span class="sxs-lookup"><span data-stu-id="915fd-109">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="915fd-110">可以新增至案例的檔總數 (針對案例中的所有審閱集)。</span><span class="sxs-lookup"><span data-stu-id="915fd-110">Total number of documents that can be added to a case (for all review sets in a case).</span></span>  <br/> |<span data-ttu-id="915fd-111">1 百萬</span><span class="sxs-lookup"><span data-stu-id="915fd-111">1 million</span></span>  <br/> |
|<span data-ttu-id="915fd-112">每個負載集的總檔案大小。</span><span class="sxs-lookup"><span data-stu-id="915fd-112">Total file size per load set.</span></span>  <br/> |<span data-ttu-id="915fd-113">100 GB</span><span class="sxs-lookup"><span data-stu-id="915fd-113">100 GB</span></span>  <br/> |
|<span data-ttu-id="915fd-114">每日載入至案例的資料總量。</span><span class="sxs-lookup"><span data-stu-id="915fd-114">Total amount of data loaded into a case per day.</span></span><br/> |<span data-ttu-id="915fd-115">2 TB</span><span class="sxs-lookup"><span data-stu-id="915fd-115">2 TB</span></span> <br/> |
|<span data-ttu-id="915fd-116">每個案例的載入集數目上限。</span><span class="sxs-lookup"><span data-stu-id="915fd-116">Maximum number of loads sets per case.</span></span>  <br/> |<span data-ttu-id="915fd-117">15 </span><span class="sxs-lookup"><span data-stu-id="915fd-117">15</span></span> <br/> |
|<span data-ttu-id="915fd-118">每個案例的審閱集數目上限。</span><span class="sxs-lookup"><span data-stu-id="915fd-118">Maximum number of review sets per case.</span></span>  <br/> |<span data-ttu-id="915fd-119">名</span><span class="sxs-lookup"><span data-stu-id="915fd-119">20</span></span> <br/> |
|||

## <a name="indexing-limits"></a><span data-ttu-id="915fd-120">索引限制</span><span class="sxs-lookup"><span data-stu-id="915fd-120">Indexing limits</span></span>

<span data-ttu-id="915fd-121">下表列出高級 eDiscovery 中的索引限制。</span><span class="sxs-lookup"><span data-stu-id="915fd-121">The following table lists the indexing limits in Advanced eDiscovery.</span></span>

|<span data-ttu-id="915fd-122">**限制的描述**</span><span class="sxs-lookup"><span data-stu-id="915fd-122">**Description of limit**</span></span>|<span data-ttu-id="915fd-123">**限制**</span><span class="sxs-lookup"><span data-stu-id="915fd-123">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="915fd-124">從單一檔案解壓縮的字元數上限。</span><span class="sxs-lookup"><span data-stu-id="915fd-124">Maximum number of characters extracted from a single file.</span></span>  <br/> |<span data-ttu-id="915fd-125">10000000<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="915fd-125">10 million<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="915fd-126">單一檔案的大小上限。</span><span class="sxs-lookup"><span data-stu-id="915fd-126">Maximum size of a single file.</span></span>   <br/> |<span data-ttu-id="915fd-127">100 MB<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="915fd-127">100 MB<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="915fd-128">檔中內嵌專案的最大深度。</span><span class="sxs-lookup"><span data-stu-id="915fd-128">Maximum depth of embedded items in a document.</span></span>  <br/> |<span data-ttu-id="915fd-129">25<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="915fd-129">25<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="915fd-130">光學字元辨識 (OCR) 所處理的檔案大小上限。</span><span class="sxs-lookup"><span data-stu-id="915fd-130">Maximum size of file processed by Optical Character Recognition (OCR).</span></span>  <br/> |<span data-ttu-id="915fd-131">24 MB<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="915fd-131">24 MB<sup>1</sup></span></span> <br/> |  
|||

## <a name="search-limits"></a><span data-ttu-id="915fd-132">搜尋限制</span><span class="sxs-lookup"><span data-stu-id="915fd-132">Search limits</span></span>

<span data-ttu-id="915fd-133">本節所述的限制與使用 [**搜尋**] 索引標籤上的 [搜尋工具] 來收集案例的資料有關。</span><span class="sxs-lookup"><span data-stu-id="915fd-133">The limits described in this section are related to using the search tool on the **Searches** tab to collect data for a case.</span></span> <span data-ttu-id="915fd-134">如需詳細資訊, 請參閱[在高級 eDiscovery 中收集案例的資料](collecting-data-for-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="915fd-134">For more information, see [Collect data for a case in Advanced eDiscovery](collecting-data-for-ediscovery.md).</span></span>

|<span data-ttu-id="915fd-135">**限制的描述**</span><span class="sxs-lookup"><span data-stu-id="915fd-135">**Description of limit**</span></span>|<span data-ttu-id="915fd-136">**限制**</span><span class="sxs-lookup"><span data-stu-id="915fd-136">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="915fd-137">可在單一搜尋中搜尋的信箱或網站數目上限。</span><span class="sxs-lookup"><span data-stu-id="915fd-137">Maximum number of mailboxes or sites that can be searched in a single search.</span></span>  <br/> |<span data-ttu-id="915fd-138">無限制</span><span class="sxs-lookup"><span data-stu-id="915fd-138">No limit</span></span>  <br/> |
|<span data-ttu-id="915fd-139">可以同時執行的最大搜尋數目。</span><span class="sxs-lookup"><span data-stu-id="915fd-139">Maximum number of searches that can run at the same time.</span></span>  <br/> |<span data-ttu-id="915fd-140">無限制</span><span class="sxs-lookup"><span data-stu-id="915fd-140">No limit</span></span>  <br/> | 
|<span data-ttu-id="915fd-141">單一使用者可以同時開始的最大搜尋數目。</span><span class="sxs-lookup"><span data-stu-id="915fd-141">Maximum number of searches that a single user can start at the same time.</span></span>  <br/> |<span data-ttu-id="915fd-142">10 </span><span class="sxs-lookup"><span data-stu-id="915fd-142">10</span></span>  <br/> | 
|<span data-ttu-id="915fd-143">搜尋查詢的最大字元數 (包括運算子和條件)。</span><span class="sxs-lookup"><span data-stu-id="915fd-143">Maximum number of characters for a search query (including operators and conditions).</span></span>  <br/> |<span data-ttu-id="915fd-144">**信箱**: 10000</span><span class="sxs-lookup"><span data-stu-id="915fd-144">**Mailboxes**: 10,000</span></span><br/><span data-ttu-id="915fd-145">**網站**: 4000 搜尋所有網站或2000時, 搜尋最多20個網站<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="915fd-145">**Sites**: 4,000 when searching all sites or 2,000 when searching up to 20 sites <sup>2</sup></span></span> <br/> |
|<span data-ttu-id="915fd-146">前置詞萬用字元的最小 Alpha 字元數。例如,**一\* **或**設定\***。</span><span class="sxs-lookup"><span data-stu-id="915fd-146">Minimum number of alpha characters for prefix wildcards; for example **one\*** or **set\***.</span></span> <br/> |<span data-ttu-id="915fd-147">萬</span><span class="sxs-lookup"><span data-stu-id="915fd-147">3</span></span>  <br/> |  
|<span data-ttu-id="915fd-148">使用前置字元萬用字元來搜尋精確的片語, 或使用前置字元萬用字元和**NEAR**或**ONEAR**布林運算子時, 所傳回的最大變化。</span><span class="sxs-lookup"><span data-stu-id="915fd-148">Maximum variants returned when using prefix wildcard to search for an exact phrase or when using a prefix wildcard and the **NEAR** or **ONEAR** Boolean operator.</span></span>  <br/> |<span data-ttu-id="915fd-149">10000 <sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="915fd-149">10,000 <sup>3</sup></span></span> <br/> |
|<span data-ttu-id="915fd-150">搜尋的預覽頁面上顯示的每個使用者信箱的專案數上限。</span><span class="sxs-lookup"><span data-stu-id="915fd-150">Maximum number of items per user mailbox that are displayed on preview page for searches.</span></span> <span data-ttu-id="915fd-151">隨即會顯示最新的專案。</span><span class="sxs-lookup"><span data-stu-id="915fd-151">The newest items are displayed.</span></span>   <br/> |<span data-ttu-id="915fd-152">100</span><span class="sxs-lookup"><span data-stu-id="915fd-152">100</span></span>  <br/> |
|<span data-ttu-id="915fd-153">預覽頁面上顯示的所有信箱中的專案數上限。</span><span class="sxs-lookup"><span data-stu-id="915fd-153">Maximum number of items from all mailboxes displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="915fd-154">1,000</span><span class="sxs-lookup"><span data-stu-id="915fd-154">1,000</span></span>  <br/> |
|<span data-ttu-id="915fd-155">可預覽搜尋結果的信箱數目上限。</span><span class="sxs-lookup"><span data-stu-id="915fd-155">Maximum number of mailboxes that can be previewed for search results.</span></span>  <span data-ttu-id="915fd-156">如果有超過1000個信箱包含符合搜尋查詢的專案, 則預覽時只可使用具有最多結果的前1000個信箱。</span><span class="sxs-lookup"><span data-stu-id="915fd-156">If there are more than 1000 mailboxes that contain items that match the search query, only the top 1,000 mailboxes with the most results are available for preview.</span></span><br/> |<span data-ttu-id="915fd-157">1,000</span><span class="sxs-lookup"><span data-stu-id="915fd-157">1,000</span></span>  <br/> |
|<span data-ttu-id="915fd-158">在預覽頁面上顯示的 SharePoint 和商務用 OneDrive 網站中的專案數上限。</span><span class="sxs-lookup"><span data-stu-id="915fd-158">Maximum number of items from SharePoint and OneDrive for Business sites displayed on preview page for searches.</span></span> <span data-ttu-id="915fd-159">隨即會顯示最新的專案。</span><span class="sxs-lookup"><span data-stu-id="915fd-159">The newest items are displayed.</span></span>  <br/> |<span data-ttu-id="915fd-160">200</span><span class="sxs-lookup"><span data-stu-id="915fd-160">200</span></span>  <br/> |
|<span data-ttu-id="915fd-161">可預覽搜尋結果的 SharePoint 和商務用 OneDrive 網站數目上限。</span><span class="sxs-lookup"><span data-stu-id="915fd-161">Maximum number of SharePoint and OneDrive for Business sites that can be previewed for search results.</span></span> <span data-ttu-id="915fd-162">如果有超過200個網站包含符合搜尋查詢的專案, 則預覽中只能有最多包含最多結果的200網站。</span><span class="sxs-lookup"><span data-stu-id="915fd-162">If there are more than 200 sites that contain items that match the search query, only the top 200 sites with the most results are available for preview.</span></span>  <br/> |<span data-ttu-id="915fd-163">200</span><span class="sxs-lookup"><span data-stu-id="915fd-163">200</span></span>  <br/> |
|<span data-ttu-id="915fd-164">在預覽頁面上針對搜尋顯示的每個公用資料夾信箱的專案數上限。</span><span class="sxs-lookup"><span data-stu-id="915fd-164">Maximum number of items per public folder mailbox displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="915fd-165">100</span><span class="sxs-lookup"><span data-stu-id="915fd-165">100</span></span>  <br/> |
|<span data-ttu-id="915fd-166">在預覽頁面上顯示的搜尋的所有公用資料夾信箱專案中找到的專案數上限。</span><span class="sxs-lookup"><span data-stu-id="915fd-166">Maximum number of items found in all public folder mailbox items displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="915fd-167">200</span><span class="sxs-lookup"><span data-stu-id="915fd-167">200</span></span>  <br/> |
|<span data-ttu-id="915fd-168">可以預覽搜尋結果的公用資料夾信箱數目上限。</span><span class="sxs-lookup"><span data-stu-id="915fd-168">Maximum number of public folder mailboxes that can be previewed for search results.</span></span> <span data-ttu-id="915fd-169">如果有500個以上的公用資料夾信箱包含符合搜尋查詢的專案, 則預覽時只可使用具有最多結果的前500個信箱。</span><span class="sxs-lookup"><span data-stu-id="915fd-169">If there are more than 500 public folder mailboxes that contain items that match the search query, only the top 500 mailboxes with the most results are available for preview.</span></span>  <br/> |<span data-ttu-id="915fd-170">500</span><span class="sxs-lookup"><span data-stu-id="915fd-170">500</span></span>  <br/> |
|||

## <a name="viewer-limits"></a><span data-ttu-id="915fd-171">檢視器限制</span><span class="sxs-lookup"><span data-stu-id="915fd-171">Viewer limits</span></span>

|<span data-ttu-id="915fd-172">**限制的描述**</span><span class="sxs-lookup"><span data-stu-id="915fd-172">**Description of limit**</span></span>|<span data-ttu-id="915fd-173">**限制**</span><span class="sxs-lookup"><span data-stu-id="915fd-173">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="915fd-174">可在原生檢視器中查看的 Excel 檔案大小上限。</span><span class="sxs-lookup"><span data-stu-id="915fd-174">Maximum size of Excel file that can be viewed in the native viewer.</span></span>  <br/> |<span data-ttu-id="915fd-175">4 MB</span><span class="sxs-lookup"><span data-stu-id="915fd-175">4 MB</span></span>  <br/> |
|||

## <a name="review-set-download-limits"></a><span data-ttu-id="915fd-176">審閱設定的下載限制</span><span class="sxs-lookup"><span data-stu-id="915fd-176">Review set download limits</span></span>

|<span data-ttu-id="915fd-177">**限制的描述**</span><span class="sxs-lookup"><span data-stu-id="915fd-177">**Description of limit**</span></span>|<span data-ttu-id="915fd-178">**限制**</span><span class="sxs-lookup"><span data-stu-id="915fd-178">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="915fd-179">從審閱集下載的檔案大小總計或檔數目上限。</span><span class="sxs-lookup"><span data-stu-id="915fd-179">Total file size or maximum number of documents downloaded from a review set.</span></span>  <br/> |<span data-ttu-id="915fd-180">3 MB 或50檔<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="915fd-180">3 MB or 50 documents <sup>4</sup></span></span>|
|||

<br/>
<br/>

> [!NOTE]
> <span data-ttu-id="915fd-181"><sup>1</sup>任何超過單一檔案限制的專案都會顯示為處理錯誤。</span><span class="sxs-lookup"><span data-stu-id="915fd-181"><sup>1</sup> Any item that exceeds a single file limit will show up as a processing error.</span></span><br/>
> <span data-ttu-id="915fd-182"><sup>2</sup>當搜尋 SharePoint 和商務用 OneDrive 位置時, 所搜尋之網站 url 中的字元會受到此限制。</span><span class="sxs-lookup"><span data-stu-id="915fd-182"><sup>2</sup> When searching SharePoint and OneDrive for Business locations, the characters in the URLs of the sites being searched count against this limit.</span></span><br/>
> <span data-ttu-id="915fd-183"><sup>3</sup>若為非片語查詢 (不使用雙引號的關鍵字值), 我們會使用特殊的前置詞索引。</span><span class="sxs-lookup"><span data-stu-id="915fd-183"><sup>3</sup> For non-phrase queries (a keyword value that doesn't use double quotation marks) we use a special prefix index.</span></span> <span data-ttu-id="915fd-184">這會告訴我們檔中有一個字, 而不是在檔中發生的位置。</span><span class="sxs-lookup"><span data-stu-id="915fd-184">This tells us that a word occurs in a document, but not where it occurs in the document.</span></span> <span data-ttu-id="915fd-185">若要執行片語查詢 (使用雙引號的關鍵字值), 我們需要比較檔中的文字在檔中的位置。</span><span class="sxs-lookup"><span data-stu-id="915fd-185">To do a phrase query (a keyword value with double quotation marks), we need to compare the position within the document for the words in the phrase.</span></span> <span data-ttu-id="915fd-186">這表示我們無法使用前置字元索引做為片語查詢。</span><span class="sxs-lookup"><span data-stu-id="915fd-186">This means that we can't use the prefix index for phrase queries.</span></span> <span data-ttu-id="915fd-187">在這種情況下, 我們會在內部使用首碼所擴充的所有可能文字來展開查詢;例如, \*\*time\* \*\*可以展開為 **"time or timer or time or time or timex or timeboxed or ..."**。</span><span class="sxs-lookup"><span data-stu-id="915fd-187">In this case, we internally expand the query with all possible words that the prefix expands to; for example,  **time\*** can expand to  **"time OR timer OR times OR timex OR timeboxed OR …"**.</span></span> <span data-ttu-id="915fd-188">10000的限制是 word 可擴充的變化數目上限, 而不是符合查詢的檔數目上限。</span><span class="sxs-lookup"><span data-stu-id="915fd-188">The limit of 10,000 is the maximum number of variants the word can expand to, not the number of documents matching the query.</span></span> <span data-ttu-id="915fd-189">非片語字詞沒有上限。</span><span class="sxs-lookup"><span data-stu-id="915fd-189">There is no upper limit for non-phrase terms.</span></span><br/>
> <span data-ttu-id="915fd-190"><sup>4</sup>此限制適用于從審閱集中下載選取的檔。</span><span class="sxs-lookup"><span data-stu-id="915fd-190"><sup>4</sup> This limit applies to downloading selected documents from a review set.</span></span> <span data-ttu-id="915fd-191">它不會套用到從審閱集中匯出檔。</span><span class="sxs-lookup"><span data-stu-id="915fd-191">It doesn't apply to exporting documents from a review set.</span></span> <span data-ttu-id="915fd-192">如需下載及匯出檔的詳細資訊, 請參閱[在高級 eDiscovery 中匯出事例資料](exporting-data-ediscover20.md)。</span><span class="sxs-lookup"><span data-stu-id="915fd-192">For more information about downloading and exporting documents, see [Export case data in Advanced eDiscovery](exporting-data-ediscover20.md).</span></span> <br/>

