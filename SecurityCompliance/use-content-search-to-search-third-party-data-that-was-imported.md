---
title: 使用內容搜尋來搜尋已匯入 Office 365 的協力廠商資料
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/27/2017
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: ec2677ff-c4d7-4363-a9e7-22c80e015688
description: 內容搜尋 eDiscovery 工具可用於搜尋的從協力廠商資料來源匯入至 Office 365 中的信箱項目。您可以建立搜尋匯入的所有項目或建立特定協力廠商資料類型的搜尋查詢的查詢。本文列出您可以使用關鍵字查詢中搜尋可匯入至 Office 365 的協力廠商資料類型的值。
ms.openlocfilehash: 793024f765aa1d016f7a043d14eb75ca6c2435c3
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214873"
---
# <a name="use-content-search-to-search-third-party-data-that-was-imported-to-office-365"></a><span data-ttu-id="e0d66-105">使用內容搜尋來搜尋已匯入 Office 365 的協力廠商資料</span><span class="sxs-lookup"><span data-stu-id="e0d66-105">Use Content Search to search third-party data that was imported to Office 365</span></span>

<span data-ttu-id="e0d66-p102">您可以使用 「[內容搜尋 eDiscovery 工具](content-search.md)在 Office 365 安全性&amp;規範中心來搜尋的項目已匯入 Office 365 中的信箱與協力廠商的資料來源。您可以建立搜尋所有匯入的協力廠商資料項目的查詢或您可以建立唯一的搜尋查詢與協力廠商的特定資料的項目。此外，您也可以建立查詢為基礎的保留原則或查詢為基礎的 eDiscovery 保留要保留 Office 365 中的第三方資料。</span><span class="sxs-lookup"><span data-stu-id="e0d66-p102">You can use the [Content Search eDiscovery tool](content-search.md) in the Office 365 Security &amp; Compliance Center to search for items that were imported to mailboxes in Office 365 from a third-party data source. You can create a query to search all imported third-party data items or you can create a query to only search specific third-party data items. Additionally, you can also create a query-based Preservation Policy or a query-based eDiscovery hold to preserve third-party data in Office 365.</span></span> 
  
<span data-ttu-id="e0d66-109">如需匯入協力廠商資料與可匯入至 Office 365 的協力廠商資料類型清單的詳細資訊，請參閱[Office 365 中的封存與協力廠商資料](archiving-third-party-data.md)。</span><span class="sxs-lookup"><span data-stu-id="e0d66-109">For more information about importing third-party data and a list of the third-party data types that can be imported to Office 365, see [Archiving third-party data in Office 365](archiving-third-party-data.md).</span></span> 
  
## <a name="creating-a-query-to-search-all-third-party-data"></a><span data-ttu-id="e0d66-110">建立搜尋協力廠商的所有資料查詢</span><span class="sxs-lookup"><span data-stu-id="e0d66-110">Creating a query to search all third-party data</span></span>

<span data-ttu-id="e0d66-p103">搜尋 （或就地保留） 您是否已匯入至 Office 365 的協力廠商任何的資料類型，可以可以使用`kind:externaldata`郵件中 [關鍵字] 方塊中的屬性值對內容的搜尋或建立查詢式保留時。例如，搜尋從任何協力廠商資料來源匯入的項目並匯入的項目之主旨屬性中包含單字"contoso"，會使用下列查詢：</span><span class="sxs-lookup"><span data-stu-id="e0d66-p103">To search (or place on hold) any type of third-party data that you've imported to Office 365, you can you can use the  `kind:externaldata` message property-value pair in the keyword box for a Content Search or when creating a query-based hold. For example, to search for items that were imported from any third-party data source and contain the word "contoso" in the Subject property of the imported item, you would use the following query:</span></span> 
  
```
kind:externaldata AND subject:contoso
```

<span data-ttu-id="e0d66-p104">先前的關鍵字查詢範例包含 subject 屬性。如需協力廠商資料的其他屬性的清單項目可以包含關鍵字查詢中，請參閱 「 詳細資訊 」] 區段中的[Office 365 中的封存與協力廠商資料](archiving-third-party-data.md#more-information)。</span><span class="sxs-lookup"><span data-stu-id="e0d66-p104">The previous keyword query example includes the subject property. For a list of other properties for third-party data items that can included in a keyword query, see the "More information" section in [Archiving third-party data in Office 365](archiving-third-party-data.md#more-information).</span></span>
  
<span data-ttu-id="e0d66-p105">建立搜尋並保留協力廠商資料的查詢，您也可以使用條件來縮小搜尋結果。如需建立內容的搜尋查詢的詳細資訊，請參閱[關鍵字查詢和搜尋條件的內容搜尋](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="e0d66-p105">When creating queries to search and hold third-party data, you can also use conditions to narrow the search results. For more information about creating Content Search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a><span data-ttu-id="e0d66-117">建立搜尋特定類型的協力廠商資料查詢</span><span class="sxs-lookup"><span data-stu-id="e0d66-117">Creating a query to search specific types of third-party data</span></span>

<span data-ttu-id="e0d66-118">而不是搜尋所有類型的協力廠商資料，您可以建立查詢只搜尋指定類型的協力廠商資料可以使用下列的郵件屬性值配對 [關鍵字] 方塊中內容的搜尋：</span><span class="sxs-lookup"><span data-stu-id="e0d66-118">Instead of searching all types of third-party data, you can create queries that only search for a specify type of third-party data by using the following message property-value pair in the keyword box for a Content Search:</span></span>
  
```
itemclass:ipm.externaldata.<third-party data type>* 
```

<span data-ttu-id="e0d66-119">例如，若要只搜尋 Facebook 資料包含單字"contoso"主旨屬性中，會使用下列查詢：</span><span class="sxs-lookup"><span data-stu-id="e0d66-119">For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the following query:</span></span>
  
```
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

<span data-ttu-id="e0d66-p106">下表列出您可以搜尋、 協力廠商資料類型和值用於`itemclass:`message 特別搜尋該類型的協力廠商資料的屬性。請注意查詢語法不區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="e0d66-p106">The following table lists the third-party data types that you can search, and the value to use for the  `itemclass:` message property to specifically search for that type of third-party data. Note that the query syntax isn't case sensitive.</span></span> 
  
|<span data-ttu-id="e0d66-122">**協力廠商資料類型**</span><span class="sxs-lookup"><span data-stu-id="e0d66-122">**Third-party data type**</span></span>|<span data-ttu-id="e0d66-123">**值`itemclass:`屬性**</span><span class="sxs-lookup"><span data-stu-id="e0d66-123">**Value for  `itemclass:` property**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e0d66-124">AIM</span><span class="sxs-lookup"><span data-stu-id="e0d66-124">AIM</span></span>  <br/> | `ipm.externaldata.AIM*` <br/> |
|<span data-ttu-id="e0d66-125">American Idol</span><span class="sxs-lookup"><span data-stu-id="e0d66-125">American Idol</span></span>  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|<span data-ttu-id="e0d66-126">含樞紐分析用戶端的 AOL</span><span class="sxs-lookup"><span data-stu-id="e0d66-126">AOL with Pivot Client</span></span>  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|<span data-ttu-id="e0d66-127">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="e0d66-127">Apple Juice</span></span>  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|<span data-ttu-id="e0d66-128">Ares</span><span class="sxs-lookup"><span data-stu-id="e0d66-128">Ares</span></span>  <br/> | `ipm.externaldata.Ares*` <br/> |
|<span data-ttu-id="e0d66-129">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="e0d66-129">Axs Encrypted</span></span>  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|<span data-ttu-id="e0d66-130">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="e0d66-130">Axs Exchange</span></span>  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|<span data-ttu-id="e0d66-131">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="e0d66-131">Axs Local Archive</span></span>  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|<span data-ttu-id="e0d66-132">Axs 預留位置</span><span class="sxs-lookup"><span data-stu-id="e0d66-132">Axs Placeholder</span></span>  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|<span data-ttu-id="e0d66-133">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="e0d66-133">Axs Signed</span></span>  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|<span data-ttu-id="e0d66-134">Bazaarvoice</span><span class="sxs-lookup"><span data-stu-id="e0d66-134">Bazaarvoice</span></span>  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|<span data-ttu-id="e0d66-135">Bearshare</span><span class="sxs-lookup"><span data-stu-id="e0d66-135">Bearshare</span></span>  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|<span data-ttu-id="e0d66-136">BitTorrent</span><span class="sxs-lookup"><span data-stu-id="e0d66-136">BitTorrent</span></span>  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|<span data-ttu-id="e0d66-137">Blackberry</span><span class="sxs-lookup"><span data-stu-id="e0d66-137">Blackberry</span></span>  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|<span data-ttu-id="e0d66-138">BlackBerry 通話記錄</span><span class="sxs-lookup"><span data-stu-id="e0d66-138">BlackBerry Call Logs</span></span>  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|<span data-ttu-id="e0d66-139">BlackBerry Messenger</span><span class="sxs-lookup"><span data-stu-id="e0d66-139">BlackBerry Messenger</span></span>  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|<span data-ttu-id="e0d66-140">BlackBerry PIN</span><span class="sxs-lookup"><span data-stu-id="e0d66-140">BlackBerry PIN</span></span>  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|<span data-ttu-id="e0d66-141">BlackBerry SMS</span><span class="sxs-lookup"><span data-stu-id="e0d66-141">BlackBerry SMS</span></span>  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|<span data-ttu-id="e0d66-142">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="e0d66-142">Bloomberg</span></span>  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|<span data-ttu-id="e0d66-143">Bloomberg 郵件
</span><span class="sxs-lookup"><span data-stu-id="e0d66-143">Bloomberg Mail</span></span>  <br/> | `ipm.externaldata.BloombergMail*` <br/> |
|<span data-ttu-id="e0d66-144">Bloomberg 通訊</span><span class="sxs-lookup"><span data-stu-id="e0d66-144">Bloomberg Messaging</span></span>  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|<span data-ttu-id="e0d66-145">Box</span><span class="sxs-lookup"><span data-stu-id="e0d66-145">Box</span></span>  <br/> | `ipm.externaldata.Box*` <br/> |
|<span data-ttu-id="e0d66-146">Cisco IM&amp;平台服務伺服器</span><span class="sxs-lookup"><span data-stu-id="e0d66-146">Cisco IM &amp; Presence Server</span></span>  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|<span data-ttu-id="e0d66-147">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="e0d66-147">Cisco Jabber</span></span>  <br/> | `ipm.externaldata.Jabber*` <br/> |
|<span data-ttu-id="e0d66-148">CipherCloud for Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="e0d66-148">CipherCloud for Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|<span data-ttu-id="e0d66-149">Direct Connect</span><span class="sxs-lookup"><span data-stu-id="e0d66-149">Direct Connect</span></span>  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|<span data-ttu-id="e0d66-150">Facebook</span><span class="sxs-lookup"><span data-stu-id="e0d66-150">Facebook</span></span>  <br/> | `ipm.externaldata.Facebook*` <br/> |
|<span data-ttu-id="e0d66-151">FastTrack</span><span class="sxs-lookup"><span data-stu-id="e0d66-151">FastTrack</span></span>  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|<span data-ttu-id="e0d66-152">FXConnect</span><span class="sxs-lookup"><span data-stu-id="e0d66-152">FXConnect</span></span>  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|<span data-ttu-id="e0d66-153">Flickr
</span><span class="sxs-lookup"><span data-stu-id="e0d66-153">Flickr</span></span>  <br/> | `ipm.externaldata.Flickr*` <br/> |
|<span data-ttu-id="e0d66-154">Gnutella</span><span class="sxs-lookup"><span data-stu-id="e0d66-154">Gnutella</span></span>  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|<span data-ttu-id="e0d66-155">Google+
</span><span class="sxs-lookup"><span data-stu-id="e0d66-155">Google+</span></span>  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|<span data-ttu-id="e0d66-156">Google Talk</span><span class="sxs-lookup"><span data-stu-id="e0d66-156">Google Talk</span></span>  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|<span data-ttu-id="e0d66-157">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="e0d66-157">GoToMyPC</span></span>  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|<span data-ttu-id="e0d66-158">HipChat</span><span class="sxs-lookup"><span data-stu-id="e0d66-158">HipChat</span></span>  <br/> | `ipm.externaldata.HipChat*` <br/> |
|<span data-ttu-id="e0d66-159">Hopster</span><span class="sxs-lookup"><span data-stu-id="e0d66-159">Hopster</span></span>  <br/> | `ipm.externaldata.Hopster*` <br/> |
|<span data-ttu-id="e0d66-160">HubConnex</span><span class="sxs-lookup"><span data-stu-id="e0d66-160">HubConnex</span></span>  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|<span data-ttu-id="e0d66-161">IBM 連線</span><span class="sxs-lookup"><span data-stu-id="e0d66-161">IBM Connections</span></span>  <br/> | `ipm.externaldata.Connections*` <br/> |
|<span data-ttu-id="e0d66-162">IBM SameTime</span><span class="sxs-lookup"><span data-stu-id="e0d66-162">IBM SameTime</span></span>  <br/> | `ipm.externaldata.Sametime*` <br/> |
|<span data-ttu-id="e0d66-163">ICE 聊天室</span><span class="sxs-lookup"><span data-stu-id="e0d66-163">ICE Chat</span></span>  <br/> | `ipm.externaldata.ICEChat.Chat` <br/> |
|<span data-ttu-id="e0d66-164">Indii Messenger
</span><span class="sxs-lookup"><span data-stu-id="e0d66-164">Indii Messenger</span></span>  <br/> | `ipm.externaldata.Indii*` <br/> |
|<span data-ttu-id="e0d66-165">Instagram
</span><span class="sxs-lookup"><span data-stu-id="e0d66-165">Instagram</span></span>  <br/> | `ipm.externaldata.Instagram*` <br/> |
|<span data-ttu-id="e0d66-166">Instant Bloomberg
</span><span class="sxs-lookup"><span data-stu-id="e0d66-166">Instant Bloomberg</span></span>  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|<span data-ttu-id="e0d66-167">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="e0d66-167">InvestEdge</span></span>  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|<span data-ttu-id="e0d66-168">IRC</span><span class="sxs-lookup"><span data-stu-id="e0d66-168">IRC</span></span>  <br/> | `ipm.externaldata.IRC*` <br/> |
|<span data-ttu-id="e0d66-169">Jive
</span><span class="sxs-lookup"><span data-stu-id="e0d66-169">Jive</span></span>  <br/> | `ipm.externaldata.Jive*` <br/> |
|<span data-ttu-id="e0d66-170">JiveApiRetention</span><span class="sxs-lookup"><span data-stu-id="e0d66-170">JiveApiRetention</span></span>  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|<span data-ttu-id="e0d66-171">JXTA</span><span class="sxs-lookup"><span data-stu-id="e0d66-171">JXTA</span></span>  <br/> | `ipm.externaldata.JXTA*` <br/> |
|<span data-ttu-id="e0d66-172">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="e0d66-172">LinkedIn</span></span>  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|<span data-ttu-id="e0d66-173">MFTP</span><span class="sxs-lookup"><span data-stu-id="e0d66-173">MFTP</span></span>  <br/> | `ipm.externaldata.MFTP*` <br/> |
|<span data-ttu-id="e0d66-174">Microsoft UC</span><span class="sxs-lookup"><span data-stu-id="e0d66-174">Microsoft UC</span></span>  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|<span data-ttu-id="e0d66-175">注意對齊</span><span class="sxs-lookup"><span data-stu-id="e0d66-175">Mind Align</span></span>  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|<span data-ttu-id="e0d66-176">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="e0d66-176">Mobile Guard</span></span>  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|<span data-ttu-id="e0d66-177">MSN</span><span class="sxs-lookup"><span data-stu-id="e0d66-177">MSN</span></span>  <br/> | `ipm.externaldata.MSN*` <br/> |
|<span data-ttu-id="e0d66-178">分享空間</span><span class="sxs-lookup"><span data-stu-id="e0d66-178">MySpace</span></span>  <br/> | `ipm.externaldata.MySpace*` <br/> |
|<span data-ttu-id="e0d66-179">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="e0d66-179">NEONetwork</span></span>  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|<span data-ttu-id="e0d66-180">OpenNap</span><span class="sxs-lookup"><span data-stu-id="e0d66-180">OpenNap</span></span>  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|<span data-ttu-id="e0d66-181">Pinterest</span><span class="sxs-lookup"><span data-stu-id="e0d66-181">Pinterest</span></span>  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|<span data-ttu-id="e0d66-182">Pivot</span><span class="sxs-lookup"><span data-stu-id="e0d66-182">Pivot</span></span>  <br/> | `ipm.externaldata.Pivot*` <br/> |
|<span data-ttu-id="e0d66-183">QQ</span><span class="sxs-lookup"><span data-stu-id="e0d66-183">QQ</span></span>  <br/> | `ipm.externaldata.QQ*` <br/> |
|<span data-ttu-id="e0d66-184">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="e0d66-184">Microsoft SharePoint</span></span>  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|<span data-ttu-id="e0d66-185">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="e0d66-185">Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter*` <br/> |
|<span data-ttu-id="e0d66-186">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="e0d66-186">Skype for Business</span></span>  <br/> | `ipm.externaldata.Skype*` <br/> |
|<span data-ttu-id="e0d66-187">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="e0d66-187">Slack Enterprise Grid</span></span>  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|<span data-ttu-id="e0d66-188">SoftEther</span><span class="sxs-lookup"><span data-stu-id="e0d66-188">SoftEther</span></span>  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|<span data-ttu-id="e0d66-189">
Squawker
</span><span class="sxs-lookup"><span data-stu-id="e0d66-189">Squawker</span></span>  <br/> | `ipm.externaldata.Squawker*` <br/> |
|<span data-ttu-id="e0d66-190">Symphony
</span><span class="sxs-lookup"><span data-stu-id="e0d66-190">Symphony</span></span>  <br/> | `ipm.externaldata.Symphony*` <br/> |
|<span data-ttu-id="e0d66-191">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="e0d66-191">Thomson Reuters</span></span>  <br/> | `ipm.externaldata.Reuters*` <br/> |
| <span data-ttu-id="e0d66-192">Thomson Reuters Eikon Messenger
</span><span class="sxs-lookup"><span data-stu-id="e0d66-192">Thomson Reuters Eikon Messenger</span></span>  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|<span data-ttu-id="e0d66-193">Tor</span><span class="sxs-lookup"><span data-stu-id="e0d66-193">Tor</span></span>  <br/> | `ipm.externaldata.Tor*` <br/> |
|<span data-ttu-id="e0d66-194">TTT</span><span class="sxs-lookup"><span data-stu-id="e0d66-194">TTT</span></span>  <br/> | `ipm.externaldata.TTT*` <br/> |
|<span data-ttu-id="e0d66-195">Twitter</span><span class="sxs-lookup"><span data-stu-id="e0d66-195">Twitter</span></span>  <br/> | `ipm.externaldata.Twitter*` <br/> |
|<span data-ttu-id="e0d66-196">UBS Chat
</span><span class="sxs-lookup"><span data-stu-id="e0d66-196">UBS Chat</span></span>  <br/> | `ipm.externaldata.UBS*` <br/> |
|<span data-ttu-id="e0d66-197">Vimeo</span><span class="sxs-lookup"><span data-stu-id="e0d66-197">Vimeo</span></span>  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|<span data-ttu-id="e0d66-198">WinMX</span><span class="sxs-lookup"><span data-stu-id="e0d66-198">WinMX</span></span>  <br/> | `ipm.externaldata.WinMX*` <br/> |
|<span data-ttu-id="e0d66-199">Winny</span><span class="sxs-lookup"><span data-stu-id="e0d66-199">Winny</span></span>  <br/> | `ipm.externaldata.Winny*` <br/> |
|<span data-ttu-id="e0d66-200">Yahoo!</span><span class="sxs-lookup"><span data-stu-id="e0d66-200">Yahoo!</span></span>  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|<span data-ttu-id="e0d66-201">Yammer</span><span class="sxs-lookup"><span data-stu-id="e0d66-201">Yammer</span></span>  <br/> | `ipm.externaldata.Yammer*` <br/> |
|<span data-ttu-id="e0d66-202">YellowJacket</span><span class="sxs-lookup"><span data-stu-id="e0d66-202">YellowJacket</span></span>  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|<span data-ttu-id="e0d66-203">YouTube</span><span class="sxs-lookup"><span data-stu-id="e0d66-203">YouTube</span></span>  <br/> | `ipm.externaldata.YouTube*` <br/> |
