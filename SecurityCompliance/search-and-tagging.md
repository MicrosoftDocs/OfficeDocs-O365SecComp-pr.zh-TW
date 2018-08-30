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
# <a name="search-and-tagging"></a><span data-ttu-id="511cc-104">搜尋與標記</span><span class="sxs-lookup"><span data-stu-id="511cc-104">Search and Tagging</span></span>

<span data-ttu-id="511cc-p102">進階 eDiscovery 中搜尋和標記模組可讓您搜尋、 預覽，並將組織中您案例的文件。目前的本單元處於 beta。</span><span class="sxs-lookup"><span data-stu-id="511cc-p102">In Advanced eDiscovery, the Search and Tagging module enables you to search, preview, and organize the documents in your case. Currently, this module is in beta.</span></span>

> [!NOTE]
> <span data-ttu-id="511cc-p103">進階的 eDiscovery 需要您組織與進階規範附加元件或 E5 訂閱 Office 365 E3。如果您不具有該對應並想要嘗試進階的 eDiscovery，您還可以[註冊 Office 365 企業版 E5 的試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="511cc-p103">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="search-the-documents-in-your-case"></a><span data-ttu-id="511cc-109">在您的案例中搜尋文件</span><span class="sxs-lookup"><span data-stu-id="511cc-109">Search the documents in your case</span></span>

<span data-ttu-id="511cc-p104">一旦您已處理文件中的進階 eDiscovery 並選擇性地執行分析模組或相關性模組，您可以使用搜尋和標記搜尋透過案例中的文件並將它們組織使用特定案例的標籤。您可以定義您使用所提供的條件卡的查詢或透過 KQL 類似的查詢語言中的關鍵字條件卡片。一般 KQL 語法，例如 AND、 OR、 NOT、 NEAR(n) 且支援，以及行尾的多重字元萬用字元 （\*）。這些屬性所支援的查詢語言屬性名稱：</span><span class="sxs-lookup"><span data-stu-id="511cc-p104">Once you have processed documents in Advanced eDiscovery and optionally run the Analyze module or the Relevance module, you can use Search and Tagging to search through the documents in the case and organize them using case-specific tags. You can define your queries using the provided condition cards, or through a KQL-like query language in the Keywords condition card. Common KQL syntax, such as AND, OR, NOT, and NEAR(n) are supported, as well as trailing multi-character wildcard (\*). These properties are supported in the query language property name:</span></span>

- <span data-ttu-id="511cc-114">caselabel： 建立/套用標記中搜尋和標記針對此案例</span><span class="sxs-lookup"><span data-stu-id="511cc-114">caselabel: tags created/applied in Search and Tagging for this case</span></span> 
- <span data-ttu-id="511cc-115">custodians: custodians 指派的情況下-受限於限制</span><span class="sxs-lookup"><span data-stu-id="511cc-115">custodians: custodians assigned in the case - subject to limitations</span></span>
- <span data-ttu-id="511cc-116">日期： 傳送電子郵件的日期、 修改日期為文件</span><span class="sxs-lookup"><span data-stu-id="511cc-116">date: sent date for email, modified date for documents</span></span>
- <span data-ttu-id="511cc-117">所 fileid： 檔案內大小寫的識別碼</span><span class="sxs-lookup"><span data-stu-id="511cc-117">fileid: file ID within the case</span></span>
- <span data-ttu-id="511cc-118">filetype： 原生副檔名</span><span class="sxs-lookup"><span data-stu-id="511cc-118">filetype: native file extension</span></span>
- <span data-ttu-id="511cc-119">fileclass： 電子郵件、 文件或附件</span><span class="sxs-lookup"><span data-stu-id="511cc-119">fileclass: email, document, or attachment</span></span>
- <span data-ttu-id="511cc-120">senderauthor： 寄件者的電子郵件、 文件的作者</span><span class="sxs-lookup"><span data-stu-id="511cc-120">senderauthor: sender for emails, author for documents</span></span>
- <span data-ttu-id="511cc-121">大小： KB 的檔案大小</span><span class="sxs-lookup"><span data-stu-id="511cc-121">size: size of the file in KB</span></span>
- <span data-ttu-id="511cc-122">subjecttitle： 主旨的電子郵件、 文件的標題</span><span class="sxs-lookup"><span data-stu-id="511cc-122">subjecttitle: subject for emails, title for documents</span></span>
- <span data-ttu-id="511cc-123">bcc</span><span class="sxs-lookup"><span data-stu-id="511cc-123">bcc</span></span>
- <span data-ttu-id="511cc-124">cc</span><span class="sxs-lookup"><span data-stu-id="511cc-124">cc</span></span>
- <span data-ttu-id="511cc-125">參與者： 電子郵件地址的電子郵件執行緒，包括的連結遺漏中的所有參與者</span><span class="sxs-lookup"><span data-stu-id="511cc-125">participants: Email addresses of all participants in an email thread, including for missing links</span></span>
- <span data-ttu-id="511cc-126">收到： 接收日期</span><span class="sxs-lookup"><span data-stu-id="511cc-126">received: received date</span></span>
- <span data-ttu-id="511cc-127">收件者： 電子郵件收件者的名稱或位址 （、 [副本]、 [密件副本)</span><span class="sxs-lookup"><span data-stu-id="511cc-127">recipients: email recipient names or addresses (to, cc, bcc)</span></span>
- <span data-ttu-id="511cc-128">sender</span><span class="sxs-lookup"><span data-stu-id="511cc-128">sender</span></span>
- <span data-ttu-id="511cc-129">lastmodifieddate： 上次修改日期的文件</span><span class="sxs-lookup"><span data-stu-id="511cc-129">lastmodifieddate: last modified date of a document</span></span>
- <span data-ttu-id="511cc-130">傳送： 傳送電子郵件的日期</span><span class="sxs-lookup"><span data-stu-id="511cc-130">sent: sent date of an email</span></span>
- <span data-ttu-id="511cc-131">到</span><span class="sxs-lookup"><span data-stu-id="511cc-131">to</span></span>
- <span data-ttu-id="511cc-132">作者： 作者的電子郵件</span><span class="sxs-lookup"><span data-stu-id="511cc-132">author: author of an email</span></span>
- <span data-ttu-id="511cc-133">標題： 文件標題</span><span class="sxs-lookup"><span data-stu-id="511cc-133">title: title of a document</span></span>
- <span data-ttu-id="511cc-134">dominanttheme： 主佈景主題的項目\*</span><span class="sxs-lookup"><span data-stu-id="511cc-134">dominanttheme: dominant theme of an item\*</span></span>
- <span data-ttu-id="511cc-135">themeslist： 與項目相關聯的佈景主題\*</span><span class="sxs-lookup"><span data-stu-id="511cc-135">themeslist: themes that are associated with an item\*</span></span>
- <span data-ttu-id="511cc-136">readpercentile_ [issuenum]： 閱讀百分位數的問題 [issuenum] 項目\*\*</span><span class="sxs-lookup"><span data-stu-id="511cc-136">readpercentile_[issuenum]: read percentile of an item for issue [issuenum]\*\*</span></span>
- <span data-ttu-id="511cc-137">relevancescore_ [issuenum]: 問題 [issuenum] 項目的相關性分數\*\*</span><span class="sxs-lookup"><span data-stu-id="511cc-137">relevancescore_[issuenum]: relevance score of an item for issue [issuenum]\*\*</span></span>
- <span data-ttu-id="511cc-138">relevancetag_ [issuenum]： 如果項目已手動標記的相關性，其標籤的 [issuenum]\*\*</span><span class="sxs-lookup"><span data-stu-id="511cc-138">relevancetag_[issuenum]: if an item has been manually tagged for relevance, its tag for [issuenum]\*\*</span></span>

<span data-ttu-id="511cc-139">\*如果已經執行 [佈景主題] 模組的唯一可用\*\*只能如果已經執行 [相關性] 模組</span><span class="sxs-lookup"><span data-stu-id="511cc-139">\* Only available if the Themes module has been run \*\* Only available if the Relevance module has been run</span></span>
  
## <a name="see-also"></a><span data-ttu-id="511cc-140">另請參閱</span><span class="sxs-lookup"><span data-stu-id="511cc-140">See also</span></span>

[<span data-ttu-id="511cc-141">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="511cc-141">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="511cc-142">了解評估的相關性</span><span class="sxs-lookup"><span data-stu-id="511cc-142">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="511cc-143">標記及評估</span><span class="sxs-lookup"><span data-stu-id="511cc-143">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="511cc-144">標記及相關性訓練</span><span class="sxs-lookup"><span data-stu-id="511cc-144">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="511cc-145">追蹤相關性分析</span><span class="sxs-lookup"><span data-stu-id="511cc-145">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="511cc-146">決定所得的結果</span><span class="sxs-lookup"><span data-stu-id="511cc-146">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="511cc-147">測試相關性分析</span><span class="sxs-lookup"><span data-stu-id="511cc-147">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

