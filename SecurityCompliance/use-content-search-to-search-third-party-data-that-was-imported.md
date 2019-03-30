---
title: 使用內容搜尋來搜尋協力廠商資料匯入至 Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/27/2017
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid: MOE150
ms.assetid: ec2677ff-c4d7-4363-a9e7-22c80e015688
description: 使用內容搜尋電子文件探索工具來搜尋的項目都已從協力廠商資料來源匯入至 Office 365 中的信箱。 您可以建立查詢以搜尋所有匯入的項目，或是建立查詢以搜尋特定的協力廠商資料類型。 本文列出您可以使用關鍵字查詢來搜尋可匯入至 Office 365 的協力廠商資料類型的值。
ms.openlocfilehash: 361ead435d397464452c5b58ecf251a7322ced05
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2019
ms.locfileid: "30999706"
---
# <a name="use-content-search-to-search-third-party-data-that-was-imported-to-office-365"></a><span data-ttu-id="84200-105">使用內容搜尋來搜尋協力廠商資料匯入至 Office 365</span><span class="sxs-lookup"><span data-stu-id="84200-105">Use Content Search to search third-party data that was imported to Office 365</span></span>

<span data-ttu-id="84200-106">您可以使用安全性 & 合規性中心中的 「[內容搜尋電子文件探索工具](content-search.md)來搜尋協力廠商資料來源匯入至 Office 365 中的信箱項目。</span><span class="sxs-lookup"><span data-stu-id="84200-106">You can use the [Content Search eDiscovery tool](content-search.md) in the Security & Compliance Center to search for items that were imported to mailboxes in Office 365 from a third-party data source.</span></span> <span data-ttu-id="84200-107">您可以建立查詢以搜尋所有匯入的協力廠商資料的項目，或者您可以建立將查詢傳送至只搜尋特定的協力廠商資料的項目。</span><span class="sxs-lookup"><span data-stu-id="84200-107">You can create a query to search all imported third-party data items or you can create a query to only search specific third-party data items.</span></span> <span data-ttu-id="84200-108">此外，您也可以建立查詢式保留原則，或查詢為基礎的 eDiscovery 保留來保留在 Office 365 中的協力廠商資料。</span><span class="sxs-lookup"><span data-stu-id="84200-108">Additionally, you can also create a query-based Preservation Policy or a query-based eDiscovery hold to preserve third-party data in Office 365.</span></span> 
  
<span data-ttu-id="84200-109">如需有關匯入協力廠商資料與可匯入至 Office 365 的協力廠商資料類型清單的詳細資訊，請參閱[Office 365 中的封存協力廠商資料](archiving-third-party-data.md)。</span><span class="sxs-lookup"><span data-stu-id="84200-109">For more information about importing third-party data and a list of the third-party data types that can be imported to Office 365, see [Archiving third-party data in Office 365](archiving-third-party-data.md).</span></span> 
  
## <a name="creating-a-query-to-search-all-third-party-data"></a><span data-ttu-id="84200-110">建立查詢以搜尋所有協力廠商資料</span><span class="sxs-lookup"><span data-stu-id="84200-110">Creating a query to search all third-party data</span></span>

<span data-ttu-id="84200-111">搜尋 （或就地保留狀態） 的任何協力廠商資料類型，當您匯入至 Office 365，您可以可以使用`kind:externaldata`郵件 [關鍵字] 方塊中的屬性值配對的內容搜尋，或建立查詢式保留時。</span><span class="sxs-lookup"><span data-stu-id="84200-111">To search (or place on hold) any type of third-party data that you've imported to Office 365, you can you can use the  `kind:externaldata` message property-value pair in the keyword box for a Content Search or when creating a query-based hold.</span></span> <span data-ttu-id="84200-112">例如，若要搜尋的項目都已匯入任何協力廠商資料來源，並匯入的項目之主旨屬性中包含 「 contoso 」 字樣，您會使用下列查詢：</span><span class="sxs-lookup"><span data-stu-id="84200-112">For example, to search for items that were imported from any third-party data source and contain the word "contoso" in the Subject property of the imported item, you would use the following query:</span></span> 
  
```
kind:externaldata AND subject:contoso
```

<span data-ttu-id="84200-113">先前的關鍵字查詢範例包含 subject 屬性。</span><span class="sxs-lookup"><span data-stu-id="84200-113">The previous keyword query example includes the subject property.</span></span> <span data-ttu-id="84200-114">如需協力廠商資料的其他屬性的清單項目，可以包含關鍵字查詢中，請參閱[Office 365 中的封存協力廠商資料](archiving-third-party-data.md#more-information)」 的詳細資訊 」 一節。</span><span class="sxs-lookup"><span data-stu-id="84200-114">For a list of other properties for third-party data items that can included in a keyword query, see the "More information" section in [Archiving third-party data in Office 365](archiving-third-party-data.md#more-information).</span></span>
  
<span data-ttu-id="84200-115">建立查詢以搜尋並保留協力廠商資料時，您也可以使用條件縮小搜尋結果的範圍。</span><span class="sxs-lookup"><span data-stu-id="84200-115">When creating queries to search and hold third-party data, you can also use conditions to narrow the search results.</span></span> <span data-ttu-id="84200-116">如需建立內容搜尋查詢的詳細資訊，請參閱[關鍵字查詢和搜尋條件的內容搜尋](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="84200-116">For more information about creating Content Search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a><span data-ttu-id="84200-117">建立查詢以搜尋特定類型的協力廠商資料</span><span class="sxs-lookup"><span data-stu-id="84200-117">Creating a query to search specific types of third-party data</span></span>

<span data-ttu-id="84200-118">而不是搜尋所有類型的協力廠商資料，您可以建立查詢指定類型的協力廠商資料只搜尋使用內容搜尋關鍵字] 方塊中的下列郵件屬性值組：</span><span class="sxs-lookup"><span data-stu-id="84200-118">Instead of searching all types of third-party data, you can create queries that only search for a specify type of third-party data by using the following message property-value pair in the keyword box for a Content Search:</span></span>
  
```
itemclass:ipm.externaldata.<third-party data type>* 
```

<span data-ttu-id="84200-119">例如，若要只搜尋包含主旨屬性中的 「 contoso 」 字樣的 Facebook 資料，您會使用下列查詢：</span><span class="sxs-lookup"><span data-stu-id="84200-119">For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the following query:</span></span>
  
```
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

<span data-ttu-id="84200-120">下表列出您可以搜尋，協力廠商資料類型和值用於`itemclass:`message 特別搜尋協力廠商資料類型的屬性。</span><span class="sxs-lookup"><span data-stu-id="84200-120">The following table lists the third-party data types that you can search, and the value to use for the  `itemclass:` message property to specifically search for that type of third-party data.</span></span> <span data-ttu-id="84200-121">請注意，查詢語法不區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="84200-121">Note that the query syntax isn't case sensitive.</span></span> 
  
|<span data-ttu-id="84200-122">**協力廠商資料類型**</span><span class="sxs-lookup"><span data-stu-id="84200-122">**Third-party data type**</span></span>|<span data-ttu-id="84200-123">**值`itemclass:`屬性**</span><span class="sxs-lookup"><span data-stu-id="84200-123">**Value for  `itemclass:` property**</span></span>|
|:-----|:-----|
|<span data-ttu-id="84200-124">目標</span><span class="sxs-lookup"><span data-stu-id="84200-124">AIM</span></span>  <br/> | `ipm.externaldata.AIM*` <br/> |
|<span data-ttu-id="84200-125">American Idol</span><span class="sxs-lookup"><span data-stu-id="84200-125">American Idol</span></span>  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|<span data-ttu-id="84200-126">含樞紐分析用戶端的 AOL</span><span class="sxs-lookup"><span data-stu-id="84200-126">AOL with Pivot Client</span></span>  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|<span data-ttu-id="84200-127">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="84200-127">Apple Juice</span></span>  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|<span data-ttu-id="84200-128">阿瑞斯</span><span class="sxs-lookup"><span data-stu-id="84200-128">Ares</span></span>  <br/> | `ipm.externaldata.Ares*` <br/> |
|<span data-ttu-id="84200-129">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="84200-129">Axs Encrypted</span></span>  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|<span data-ttu-id="84200-130">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="84200-130">Axs Exchange</span></span>  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|<span data-ttu-id="84200-131">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="84200-131">Axs Local Archive</span></span>  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|<span data-ttu-id="84200-132">Axs 版面配置區</span><span class="sxs-lookup"><span data-stu-id="84200-132">Axs Placeholder</span></span>  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|<span data-ttu-id="84200-133">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="84200-133">Axs Signed</span></span>  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|<span data-ttu-id="84200-134">Bazaarvoice</span><span class="sxs-lookup"><span data-stu-id="84200-134">Bazaarvoice</span></span>  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|<span data-ttu-id="84200-135">Bearshare</span><span class="sxs-lookup"><span data-stu-id="84200-135">Bearshare</span></span>  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|<span data-ttu-id="84200-136">BitTorrent</span><span class="sxs-lookup"><span data-stu-id="84200-136">BitTorrent</span></span>  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|<span data-ttu-id="84200-137">Blackberry</span><span class="sxs-lookup"><span data-stu-id="84200-137">Blackberry</span></span>  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|<span data-ttu-id="84200-138">BlackBerry Call Logs</span><span class="sxs-lookup"><span data-stu-id="84200-138">BlackBerry Call Logs</span></span>  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|<span data-ttu-id="84200-139">BlackBerry Messenger</span><span class="sxs-lookup"><span data-stu-id="84200-139">BlackBerry Messenger</span></span>  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|<span data-ttu-id="84200-140">BlackBerry pin 碼</span><span class="sxs-lookup"><span data-stu-id="84200-140">BlackBerry PIN</span></span>  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|<span data-ttu-id="84200-141">BlackBerry SMS</span><span class="sxs-lookup"><span data-stu-id="84200-141">BlackBerry SMS</span></span>  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|<span data-ttu-id="84200-142">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="84200-142">Bloomberg</span></span>  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|<span data-ttu-id="84200-143">Bloomberg 郵件</span><span class="sxs-lookup"><span data-stu-id="84200-143">Bloomberg Mail</span></span>  <br/> | `ipm.externaldata.BloombergMail*` <br/> |
|<span data-ttu-id="84200-144">Bloomberg 郵件</span><span class="sxs-lookup"><span data-stu-id="84200-144">Bloomberg Messaging</span></span>  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|<span data-ttu-id="84200-145">Box</span><span class="sxs-lookup"><span data-stu-id="84200-145">Box</span></span>  <br/> | `ipm.externaldata.Box*` <br/> |
|<span data-ttu-id="84200-146">Cisco IM &amp; Presence Server</span><span class="sxs-lookup"><span data-stu-id="84200-146">Cisco IM &amp; Presence Server</span></span>  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|<span data-ttu-id="84200-147">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="84200-147">Cisco Jabber</span></span>  <br/> | `ipm.externaldata.Jabber*` <br/> |
|<span data-ttu-id="84200-148">CipherCloud for Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="84200-148">CipherCloud for Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|<span data-ttu-id="84200-149">Direct Connect</span><span class="sxs-lookup"><span data-stu-id="84200-149">Direct Connect</span></span>  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|<span data-ttu-id="84200-150">Facebook</span><span class="sxs-lookup"><span data-stu-id="84200-150">Facebook</span></span>  <br/> | `ipm.externaldata.Facebook*` <br/> |
|<span data-ttu-id="84200-151">FastTrack</span><span class="sxs-lookup"><span data-stu-id="84200-151">FastTrack</span></span>  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|<span data-ttu-id="84200-152">FXConnect</span><span class="sxs-lookup"><span data-stu-id="84200-152">FXConnect</span></span>  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|<span data-ttu-id="84200-153">Flickr</span><span class="sxs-lookup"><span data-stu-id="84200-153">Flickr</span></span>  <br/> | `ipm.externaldata.Flickr*` <br/> |
|<span data-ttu-id="84200-154">Gnutella</span><span class="sxs-lookup"><span data-stu-id="84200-154">Gnutella</span></span>  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|<span data-ttu-id="84200-155">Google +</span><span class="sxs-lookup"><span data-stu-id="84200-155">Google+</span></span>  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|<span data-ttu-id="84200-156">Google Talk</span><span class="sxs-lookup"><span data-stu-id="84200-156">Google Talk</span></span>  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|<span data-ttu-id="84200-157">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="84200-157">GoToMyPC</span></span>  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|<span data-ttu-id="84200-158">HipChat</span><span class="sxs-lookup"><span data-stu-id="84200-158">HipChat</span></span>  <br/> | `ipm.externaldata.HipChat*` <br/> |
|<span data-ttu-id="84200-159">Hopster</span><span class="sxs-lookup"><span data-stu-id="84200-159">Hopster</span></span>  <br/> | `ipm.externaldata.Hopster*` <br/> |
|<span data-ttu-id="84200-160">HubConnex</span><span class="sxs-lookup"><span data-stu-id="84200-160">HubConnex</span></span>  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|<span data-ttu-id="84200-161">IBM Connections</span><span class="sxs-lookup"><span data-stu-id="84200-161">IBM Connections</span></span>  <br/> | `ipm.externaldata.Connections*` <br/> |
|<span data-ttu-id="84200-162">IBM SameTime</span><span class="sxs-lookup"><span data-stu-id="84200-162">IBM SameTime</span></span>  <br/> | `ipm.externaldata.Sametime*` <br/> |
|<span data-ttu-id="84200-163">冰聊天室</span><span class="sxs-lookup"><span data-stu-id="84200-163">ICE Chat</span></span>  <br/> | `ipm.externaldata.ICEChat.Chat` <br/> |
|<span data-ttu-id="84200-164">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="84200-164">Indii Messenger</span></span>  <br/> | `ipm.externaldata.Indii*` <br/> |
|<span data-ttu-id="84200-165">Instagram</span><span class="sxs-lookup"><span data-stu-id="84200-165">Instagram</span></span>  <br/> | `ipm.externaldata.Instagram*` <br/> |
|<span data-ttu-id="84200-166">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="84200-166">Instant Bloomberg</span></span>  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|<span data-ttu-id="84200-167">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="84200-167">InvestEdge</span></span>  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|<span data-ttu-id="84200-168">IRC</span><span class="sxs-lookup"><span data-stu-id="84200-168">IRC</span></span>  <br/> | `ipm.externaldata.IRC*` <br/> |
|<span data-ttu-id="84200-169">Jive</span><span class="sxs-lookup"><span data-stu-id="84200-169">Jive</span></span>  <br/> | `ipm.externaldata.Jive*` <br/> |
|<span data-ttu-id="84200-170">JiveApiRetention</span><span class="sxs-lookup"><span data-stu-id="84200-170">JiveApiRetention</span></span>  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|<span data-ttu-id="84200-171">JXTA</span><span class="sxs-lookup"><span data-stu-id="84200-171">JXTA</span></span>  <br/> | `ipm.externaldata.JXTA*` <br/> |
|<span data-ttu-id="84200-172">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="84200-172">LinkedIn</span></span>  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|<span data-ttu-id="84200-173">MFTP</span><span class="sxs-lookup"><span data-stu-id="84200-173">MFTP</span></span>  <br/> | `ipm.externaldata.MFTP*` <br/> |
|<span data-ttu-id="84200-174">Microsoft UC</span><span class="sxs-lookup"><span data-stu-id="84200-174">Microsoft UC</span></span>  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|<span data-ttu-id="84200-175">注意對齊</span><span class="sxs-lookup"><span data-stu-id="84200-175">Mind Align</span></span>  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|<span data-ttu-id="84200-176">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="84200-176">Mobile Guard</span></span>  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|<span data-ttu-id="84200-177">MSN</span><span class="sxs-lookup"><span data-stu-id="84200-177">MSN</span></span>  <br/> | `ipm.externaldata.MSN*` <br/> |
|<span data-ttu-id="84200-178">分享空間</span><span class="sxs-lookup"><span data-stu-id="84200-178">MySpace</span></span>  <br/> | `ipm.externaldata.MySpace*` <br/> |
|<span data-ttu-id="84200-179">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="84200-179">NEONetwork</span></span>  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|<span data-ttu-id="84200-180">OpenNap</span><span class="sxs-lookup"><span data-stu-id="84200-180">OpenNap</span></span>  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|<span data-ttu-id="84200-181">Pinterest</span><span class="sxs-lookup"><span data-stu-id="84200-181">Pinterest</span></span>  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|<span data-ttu-id="84200-182">樞紐</span><span class="sxs-lookup"><span data-stu-id="84200-182">Pivot</span></span>  <br/> | `ipm.externaldata.Pivot*` <br/> |
|<span data-ttu-id="84200-183">QQ</span><span class="sxs-lookup"><span data-stu-id="84200-183">QQ</span></span>  <br/> | `ipm.externaldata.QQ*` <br/> |
|<span data-ttu-id="84200-184">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="84200-184">Microsoft SharePoint</span></span>  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|<span data-ttu-id="84200-185">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="84200-185">Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter*` <br/> |
|<span data-ttu-id="84200-186">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="84200-186">Skype for Business</span></span>  <br/> | `ipm.externaldata.Skype*` <br/> |
|<span data-ttu-id="84200-187">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="84200-187">Slack Enterprise Grid</span></span>  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|<span data-ttu-id="84200-188">SoftEther</span><span class="sxs-lookup"><span data-stu-id="84200-188">SoftEther</span></span>  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|<span data-ttu-id="84200-189">Squawker</span><span class="sxs-lookup"><span data-stu-id="84200-189">Squawker</span></span>  <br/> | `ipm.externaldata.Squawker*` <br/> |
|<span data-ttu-id="84200-190">號交響曲</span><span class="sxs-lookup"><span data-stu-id="84200-190">Symphony</span></span>  <br/> | `ipm.externaldata.Symphony*` <br/> |
|<span data-ttu-id="84200-191">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="84200-191">Thomson Reuters</span></span>  <br/> | `ipm.externaldata.Reuters*` <br/> |
| <span data-ttu-id="84200-192">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="84200-192">Thomson Reuters Eikon Messenger</span></span>  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|<span data-ttu-id="84200-193">Tor</span><span class="sxs-lookup"><span data-stu-id="84200-193">Tor</span></span>  <br/> | `ipm.externaldata.Tor*` <br/> |
|<span data-ttu-id="84200-194">TTT</span><span class="sxs-lookup"><span data-stu-id="84200-194">TTT</span></span>  <br/> | `ipm.externaldata.TTT*` <br/> |
|<span data-ttu-id="84200-195">在 twitter</span><span class="sxs-lookup"><span data-stu-id="84200-195">Twitter</span></span>  <br/> | `ipm.externaldata.Twitter*` <br/> |
|<span data-ttu-id="84200-196">UBS Chat</span><span class="sxs-lookup"><span data-stu-id="84200-196">UBS Chat</span></span>  <br/> | `ipm.externaldata.UBS*` <br/> |
|<span data-ttu-id="84200-197">Vimeo</span><span class="sxs-lookup"><span data-stu-id="84200-197">Vimeo</span></span>  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|<span data-ttu-id="84200-198">WinMX</span><span class="sxs-lookup"><span data-stu-id="84200-198">WinMX</span></span>  <br/> | `ipm.externaldata.WinMX*` <br/> |
|<span data-ttu-id="84200-199">Winny</span><span class="sxs-lookup"><span data-stu-id="84200-199">Winny</span></span>  <br/> | `ipm.externaldata.Winny*` <br/> |
|<span data-ttu-id="84200-200">Yahoo ！</span><span class="sxs-lookup"><span data-stu-id="84200-200">Yahoo!</span></span>  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|<span data-ttu-id="84200-201">Yammer</span><span class="sxs-lookup"><span data-stu-id="84200-201">Yammer</span></span>  <br/> | `ipm.externaldata.Yammer*` <br/> |
|<span data-ttu-id="84200-202">YellowJacket</span><span class="sxs-lookup"><span data-stu-id="84200-202">YellowJacket</span></span>  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|<span data-ttu-id="84200-203">YouTube</span><span class="sxs-lookup"><span data-stu-id="84200-203">YouTube</span></span>  <br/> | `ipm.externaldata.YouTube*` <br/> |
