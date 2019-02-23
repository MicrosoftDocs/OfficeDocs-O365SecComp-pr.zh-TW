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
# <a name="search-and-tagging"></a><span data-ttu-id="2b55b-104">搜尋與標記</span><span class="sxs-lookup"><span data-stu-id="2b55b-104">Search and Tagging</span></span>

<span data-ttu-id="2b55b-p102">進階 eDiscovery 中搜尋和標記模組可讓您搜尋、 預覽，並將組織中您案例的文件。目前的本單元處於 beta。搜尋及標記的簡短示範，請參閱[管理您的資料與進階 eDiscovery](https://www.youtube.com/watch?v=VaPYL3DHP6I)影片。</span><span class="sxs-lookup"><span data-stu-id="2b55b-p102">In Advanced eDiscovery, the Search and Tagging module enables you to search, preview, and organize the documents in your case. Currently, this module is in beta. For a brief demonstration of searching and tagging, see the [Manage your data with Advanced eDiscovery](https://www.youtube.com/watch?v=VaPYL3DHP6I) video.</span></span>

> [!NOTE]
> <span data-ttu-id="2b55b-p103">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="2b55b-p103">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="search-the-documents-in-your-case"></a><span data-ttu-id="2b55b-110">在您的案例中搜尋文件</span><span class="sxs-lookup"><span data-stu-id="2b55b-110">Search the documents in your case</span></span>

<span data-ttu-id="2b55b-p104">您已處理文件中的進階的 eDiscovery 案例 （並選擇性地執行分析或相關性模組之後），您可以使用搜尋及標記搜尋文件並再將它們組織套用特定案例的標籤 （也稱為標籤）。您可以定義搜尋查詢使用所提供的條件卡或使用 KQL 類似的查詢語言中的關鍵字條件卡片。一般 KQL 語法，例如 AND、 OR、 NOT、 NEAR(n) 且支援，以及行尾的多重字元萬用字元 （\*）。</span><span class="sxs-lookup"><span data-stu-id="2b55b-p104">After you have processed documents in an Advanced eDiscovery case (and optionally run the Analyze or Relevance module), you can use the Search and Tagging to search documents and then organize them by applying case-specific tags (also called labels). You can define a search query using the provided condition cards or by using a KQL-like query language in the Keywords condition card. Common KQL syntax, such as AND, OR, NOT, and NEAR(n) are supported, as well as trailing multi-character wildcard (\*).</span></span> 

<span data-ttu-id="2b55b-p105">下表列出您可以搜尋使用 KQL 關鍵字查詢的屬性。或者，您可以使用進階的 eDiscovery 搜尋工具中的條件卡片新增至搜尋查詢的條件 （適用於選取的內容）。</span><span class="sxs-lookup"><span data-stu-id="2b55b-p105">The following table lists the properties that you can search for using a KQL keyword query. Alternatively, you can use a condition card for in the Advanced eDiscovery Search tool to add a condition (for selected properties) to a search query.</span></span>

|<span data-ttu-id="2b55b-116">**屬性**</span><span class="sxs-lookup"><span data-stu-id="2b55b-116">**Property**</span></span>|<span data-ttu-id="2b55b-117">**描述**</span><span class="sxs-lookup"><span data-stu-id="2b55b-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2b55b-118">**caselabel**</span><span class="sxs-lookup"><span data-stu-id="2b55b-118">**caselabel**</span></span> <br/> | <span data-ttu-id="2b55b-119">建立/時套用標記的文件的標記名稱。</span><span class="sxs-lookup"><span data-stu-id="2b55b-119">The name of the tag created/applied when a document is tagged.</span></span> <br/> |
|<span data-ttu-id="2b55b-120">**okay**</span><span class="sxs-lookup"><span data-stu-id="2b55b-120">**custodian**</span></span> <br/> | <span data-ttu-id="2b55b-121">文件 ； 相關聯 okay主旨來限制。</span><span class="sxs-lookup"><span data-stu-id="2b55b-121">The custodian associated with a document; subject to limitations.</span></span> <br/> |
|<span data-ttu-id="2b55b-122">**日期**</span><span class="sxs-lookup"><span data-stu-id="2b55b-122">**date**</span></span> <br/> | <span data-ttu-id="2b55b-123">傳送電子郵件 ； 日期網站文件的修改的日期。</span><span class="sxs-lookup"><span data-stu-id="2b55b-123">Sent date for email; the modified date for site documents.</span></span> <br/> |
|<span data-ttu-id="2b55b-124">**所 fileid**</span><span class="sxs-lookup"><span data-stu-id="2b55b-124">**fileid**</span></span> <br/> | <span data-ttu-id="2b55b-125">檔案中的識別碼大小寫。</span><span class="sxs-lookup"><span data-stu-id="2b55b-125">The File ID within the case.</span></span> <br/> |
|<span data-ttu-id="2b55b-126">**filetype**</span><span class="sxs-lookup"><span data-stu-id="2b55b-126">**filetype**</span></span> <br/> | <span data-ttu-id="2b55b-127">原生副檔名。</span><span class="sxs-lookup"><span data-stu-id="2b55b-127">The native file extension.</span></span> <br/> |
|<span data-ttu-id="2b55b-128">**fileclass**</span><span class="sxs-lookup"><span data-stu-id="2b55b-128">**fileclass**</span></span> <br/> | <span data-ttu-id="2b55b-129">電子郵件、 文件或附件。</span><span class="sxs-lookup"><span data-stu-id="2b55b-129">Email, document, or attachment.</span></span> <br/> |
|<span data-ttu-id="2b55b-130">**senderauthor**</span><span class="sxs-lookup"><span data-stu-id="2b55b-130">**senderauthor**</span></span> <br/> | <span data-ttu-id="2b55b-131">寄件者的電子郵件 ；網站文件的作者。</span><span class="sxs-lookup"><span data-stu-id="2b55b-131">The sender for email; the author for site documents.</span></span> <br/> |
|<span data-ttu-id="2b55b-132">**大小**</span><span class="sxs-lookup"><span data-stu-id="2b55b-132">**size**</span></span> <br/> | <span data-ttu-id="2b55b-133">Kb 的檔案大小。</span><span class="sxs-lookup"><span data-stu-id="2b55b-133">The size of the file in KB.</span></span> <br/> |
|<span data-ttu-id="2b55b-134">**subjecttitle**</span><span class="sxs-lookup"><span data-stu-id="2b55b-134">**subjecttitle**</span></span> <br/> | <span data-ttu-id="2b55b-135">電子郵件 ； 主旨網站文件的標題。</span><span class="sxs-lookup"><span data-stu-id="2b55b-135">The subject for email; the title for site documents.</span></span> <br/> |
|<span data-ttu-id="2b55b-136">**bcc**</span><span class="sxs-lookup"><span data-stu-id="2b55b-136">**bcc**</span></span> <br/> | <span data-ttu-id="2b55b-137">電子郵件的密件副本] 欄位。</span><span class="sxs-lookup"><span data-stu-id="2b55b-137">The Bcc field of an email.</span></span> <br/> |
|<span data-ttu-id="2b55b-138">**cc**</span><span class="sxs-lookup"><span data-stu-id="2b55b-138">**cc**</span></span> <br/> | <span data-ttu-id="2b55b-139">電子郵件的 [副本] 欄位。</span><span class="sxs-lookup"><span data-stu-id="2b55b-139">The Cc field of an email.</span></span> <br/> |
|<span data-ttu-id="2b55b-140">**參與者**</span><span class="sxs-lookup"><span data-stu-id="2b55b-140">**participants**</span></span> <br/> | <span data-ttu-id="2b55b-141">所有參與者的電子郵件執行緒，其中包含連結遺漏的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="2b55b-141">The email address of all participants in an email thread, including for missing links.</span></span> <br/> |
|<span data-ttu-id="2b55b-142">**接收**</span><span class="sxs-lookup"><span data-stu-id="2b55b-142">**received**</span></span> <br/> | <span data-ttu-id="2b55b-143">接收的電子郵件的日期。</span><span class="sxs-lookup"><span data-stu-id="2b55b-143">The date an email was received.</span></span> <br/> |
|<span data-ttu-id="2b55b-144">**收件者**</span><span class="sxs-lookup"><span data-stu-id="2b55b-144">**recipients**</span></span> <br/> | <span data-ttu-id="2b55b-145">收件者電子郵件中包含 [收件者]、 [副本] 或 [密件副本] 欄位。</span><span class="sxs-lookup"><span data-stu-id="2b55b-145">Recipients of an email, included on the To, Cc, or Bcc fields.</span></span> <br/> |
|<span data-ttu-id="2b55b-146">**sender**</span><span class="sxs-lookup"><span data-stu-id="2b55b-146">**sender**</span></span> <br/> | <span data-ttu-id="2b55b-147">電子郵件的寄件者。</span><span class="sxs-lookup"><span data-stu-id="2b55b-147">The sender of an email.</span></span> <br/> |
|<span data-ttu-id="2b55b-148">**lastmodifieddate**</span><span class="sxs-lookup"><span data-stu-id="2b55b-148">**lastmodifieddate**</span></span> <br/> | <span data-ttu-id="2b55b-149">上次修改日期的網站文件。</span><span class="sxs-lookup"><span data-stu-id="2b55b-149">The last modified date of a site document.</span></span> <br/> |
|<span data-ttu-id="2b55b-150">**傳送**</span><span class="sxs-lookup"><span data-stu-id="2b55b-150">**sent**</span></span> <br/> | <span data-ttu-id="2b55b-151">傳送電子郵件的日期。</span><span class="sxs-lookup"><span data-stu-id="2b55b-151">The sent date of an email.</span></span> <br/> |
|<span data-ttu-id="2b55b-152">**若要**</span><span class="sxs-lookup"><span data-stu-id="2b55b-152">**to**</span></span> <br/> | <span data-ttu-id="2b55b-153">電子郵件] 欄位中所列的收件者。</span><span class="sxs-lookup"><span data-stu-id="2b55b-153">The recipient listed in the To field of an email.</span></span> <br/> |
|<span data-ttu-id="2b55b-154">**作者**</span><span class="sxs-lookup"><span data-stu-id="2b55b-154">**author**</span></span> <br/> | <span data-ttu-id="2b55b-155">網站文件的作者。</span><span class="sxs-lookup"><span data-stu-id="2b55b-155">The author of a site document.</span></span> <br/> |
|<span data-ttu-id="2b55b-156">**標題**</span><span class="sxs-lookup"><span data-stu-id="2b55b-156">**title**</span></span> <br/> | <span data-ttu-id="2b55b-157">網站文件的標題。</span><span class="sxs-lookup"><span data-stu-id="2b55b-157">The title of a site document.</span></span> <br/> |
|<span data-ttu-id="2b55b-158">**dominanttheme**\*</span><span class="sxs-lookup"><span data-stu-id="2b55b-158">**dominanttheme**\*</span></span> <br/> | <span data-ttu-id="2b55b-159">項目主佈景主題。</span><span class="sxs-lookup"><span data-stu-id="2b55b-159">The dominant theme of an item.</span></span> <br/> |
|<span data-ttu-id="2b55b-160">**themeslist**\*</span><span class="sxs-lookup"><span data-stu-id="2b55b-160">**themeslist**\*</span></span> <br/> | <span data-ttu-id="2b55b-161">與項目相關聯的佈景主題。</span><span class="sxs-lookup"><span data-stu-id="2b55b-161">Themes that are associated with an item.</span></span> <br/> |
|<span data-ttu-id="2b55b-162">**readpercentile_ [issuenum]**\*\*</span><span class="sxs-lookup"><span data-stu-id="2b55b-162">**readpercentile_[issuenum]**\*\*</span></span> <br/> | <span data-ttu-id="2b55b-163">讀取百分位數的項目，如 [issuenum] 所定義的問題。</span><span class="sxs-lookup"><span data-stu-id="2b55b-163">The read percentile of an item, for the issue defined by [issuenum].</span></span> <br/> |
|<span data-ttu-id="2b55b-164">**relevancescore_ [issuenum]**\*\*</span><span class="sxs-lookup"><span data-stu-id="2b55b-164">**relevancescore_[issuenum]**\*\*</span></span> <br/> | <span data-ttu-id="2b55b-165">[Issuenum] 所定義的問題項目、 相關性分數。</span><span class="sxs-lookup"><span data-stu-id="2b55b-165">The relevance score of an item, for the issue defined by [issuenum].</span></span> <br/> |
|<span data-ttu-id="2b55b-166">**relevancetag_ [tagname]**\*\*</span><span class="sxs-lookup"><span data-stu-id="2b55b-166">**relevancetag_[tagname]**\*\*</span></span> <br/> | <span data-ttu-id="2b55b-167">如果項目有手動已標記為 [tagname] 所定義之標籤的相關性。</span><span class="sxs-lookup"><span data-stu-id="2b55b-167">If an item has been manually tagged for relevance, the tag defined by  [tagname].</span></span> <br/> |
|||

<span data-ttu-id="2b55b-168">\*如果已經執行 [佈景主題模組只提供。</span><span class="sxs-lookup"><span data-stu-id="2b55b-168">\* Only available if the Themes module has been run.</span></span>

<span data-ttu-id="2b55b-169">\*\*如果已經執行 [相關性] 模組只提供。</span><span class="sxs-lookup"><span data-stu-id="2b55b-169">\*\* Only available if the Relevance module has been run.</span></span>

<span data-ttu-id="2b55b-p106">或者，您可以使用進階的 eDiscovery 搜尋工具中的條件卡新增至搜尋查詢的條件 （適用於選取的內容）。下列螢幕擷取畫面顯示可以新增至查詢的條件。[**群組**] 欄會指出是否將屬性套用至電子郵件、 網站文件或這兩者 （以*通用*值）。此欄也會識別之後執行相關性模組都是可用的可搜尋屬性。</span><span class="sxs-lookup"><span data-stu-id="2b55b-p106">Alternatively, you can use a condition card in the Advanced eDiscovery Search tool to add a condition (for selected properties) to a search query. The following screenshot shows the conditions that can be added to a query. The **Group** column indicates whether the property applies to email, site documents, or both (indicated by the value *Common*). This column also identifies the searchable properties that are available after you run the Relevance module.</span></span>

![進階的 eDiscovery 搜尋工具中的搜尋條件](media/AeDSearchConditions.png)

<span data-ttu-id="2b55b-175">如需可搜尋的內容的詳細資訊，請參閱[關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="2b55b-175">For more information about searchable properties, see [Keyword queries and search conditions](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2b55b-176">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2b55b-176">See also</span></span>

[<span data-ttu-id="2b55b-177">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="2b55b-177">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="2b55b-178">了解評估的相關性</span><span class="sxs-lookup"><span data-stu-id="2b55b-178">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2b55b-179">標記及評估</span><span class="sxs-lookup"><span data-stu-id="2b55b-179">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2b55b-180">標記及相關性訓練</span><span class="sxs-lookup"><span data-stu-id="2b55b-180">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2b55b-181">追蹤相關性分析</span><span class="sxs-lookup"><span data-stu-id="2b55b-181">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2b55b-182">決定所得的結果</span><span class="sxs-lookup"><span data-stu-id="2b55b-182">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2b55b-183">測試相關性分析</span><span class="sxs-lookup"><span data-stu-id="2b55b-183">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

