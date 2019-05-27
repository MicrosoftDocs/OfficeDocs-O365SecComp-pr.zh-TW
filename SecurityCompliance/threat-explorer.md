---
title: 威脅總管 （和即時偵測的資訊）
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 05/22/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
description: 了解 Explorer （並即時偵測） 安全性&amp;合規性中心。
ms.openlocfilehash: 62ba70cb62b0c92cf65d77dfaf3eb7306e93fa98
ms.sourcegitcommit: 2b46fba650df8d252b1dd2b3c3f080a383183a06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/23/2019
ms.locfileid: "34415713"
---
# <a name="threat-explorer-and-real-time-detections"></a><span data-ttu-id="f64df-103">威脅總管 （和即時偵測的資訊）</span><span class="sxs-lookup"><span data-stu-id="f64df-103">Threat Explorer (and real-time detections)</span></span>

<span data-ttu-id="f64df-104">如果貴組織有[Office 365 進階威脅防護](office-365-atp.md)(Office 365 ATP)，而且您具有[必要權限](#required-licenses-and-permissions)，您必須**Explorer**或**即時偵測**(先前稱為即時報告 —[請參閱 what's new](#new-features-in-real-time-detections)!).</span><span class="sxs-lookup"><span data-stu-id="f64df-104">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (Office 365 ATP), and you have the [necessary permissions](#required-licenses-and-permissions), you have either **Explorer** or **real-time detections** (formerly real-time reports — [see what's new](#new-features-in-real-time-detections)!).</span></span> <span data-ttu-id="f64df-105">在安全性 & 合規性中心，移至**威脅管理**，然後再選擇 [**檔案總管**] 或 [**即時偵測的資訊**。</span><span class="sxs-lookup"><span data-stu-id="f64df-105">In the Security & Compliance Center, go to **Threat management**, and then choose **Explorer** OR **Real-time detections**.</span></span> 

|<span data-ttu-id="f64df-106">ATP 計劃 2，您會看到：</span><span class="sxs-lookup"><span data-stu-id="f64df-106">With ATP Plan 2, you see:</span></span>  |<span data-ttu-id="f64df-107">ATP 計劃 1，您會看到：</span><span class="sxs-lookup"><span data-stu-id="f64df-107">With ATP Plan 1, you see:</span></span>  |
|---------|---------|
|![威脅總管](media/threatmgmt-explorer.png)      |![即時偵測](media/threatmgmt-realtimedetections.png)         |

<span data-ttu-id="f64df-110">必須使用檔案總管] （或即時偵測的資訊） 的功能強大的報告，可讓您的安全性操作小組，以調查及回應威脅有效的方式，並看起來像下列影像：</span><span class="sxs-lookup"><span data-stu-id="f64df-110">With Explorer (or real-time detections), you have a powerful report that enables your Security Operations team to investigate and respond to threats effectively and efficiently, and it resembles the following image:</span></span> 

![移至威脅管理，\>總管](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="f64df-112">這份報告，您可以進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="f64df-112">With this report, you can:</span></span>
- [<span data-ttu-id="f64df-113">請參閱 Office 365 安全性功能所偵測到的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="f64df-113">See malware detected by Office 365 security features</span></span>](#see-malware-detected-in-email-by-technology)
- [<span data-ttu-id="f64df-114">檢視網路釣魚 Url 相關資料，並按一下 verdict</span><span class="sxs-lookup"><span data-stu-id="f64df-114">View data about phishing URLs and click verdict</span></span>](#view-data-about-phishing-urls-and-click-verdict)
- <span data-ttu-id="f64df-115">[啟動自動化的調查及回應程序，從 [在檔案總管檢視](#start-automated-investigation-and-response)（ATP 計劃 2 只）</span><span class="sxs-lookup"><span data-stu-id="f64df-115">[Start an automated investigation and response process from a view in Explorer](#start-automated-investigation-and-response) (ATP Plan 2 only)</span></span>
- <span data-ttu-id="f64df-116">...[調查惡意電子郵件，以及更多](#more-ways-to-use-explorer-or-real-time-detections)！</span><span class="sxs-lookup"><span data-stu-id="f64df-116">... [Investigate malicious email, and more](#more-ways-to-use-explorer-or-real-time-detections)!</span></span>

## <a name="new-features-in-real-time-detections"></a><span data-ttu-id="f64df-117">在 [即時偵測的新功能</span><span class="sxs-lookup"><span data-stu-id="f64df-117">New features in real-time detections</span></span>

<span data-ttu-id="f64df-118">Office 365 ATP 計劃 1 的客戶，[*即時偵測*] 報告是先前稱為*即時報告*。</span><span class="sxs-lookup"><span data-stu-id="f64df-118">For Office 365 ATP Plan 1 customers, the *real-time detections* report was previously referred to as *real-time reports*.</span></span> <span data-ttu-id="f64df-119">除了名稱變更] 中，幾個新功能和增強功能已推出：</span><span class="sxs-lookup"><span data-stu-id="f64df-119">In addition to the name change, several new features and enhancements are rolling out:</span></span>

- <span data-ttu-id="f64df-120">在 Phish 檢視中，您可以查看詳細偵測到透過[ATP 安全連結](atp-safe-links.md)的 Url。</span><span class="sxs-lookup"><span data-stu-id="f64df-120">In the Phish view, you can see more details about detected URLs through [ATP Safe Links](atp-safe-links.md).</span></span> <span data-ttu-id="f64df-121">新的詳細資訊和功能包括：</span><span class="sxs-lookup"><span data-stu-id="f64df-121">New details and capabilities include:</span></span>
  - <span data-ttu-id="f64df-122">電子郵件訊息中的 Url</span><span class="sxs-lookup"><span data-stu-id="f64df-122">URLs in email messages</span></span>
  - <span data-ttu-id="f64df-123">篩選根據 URL 的資訊</span><span class="sxs-lookup"><span data-stu-id="f64df-123">Filtering based on URL information</span></span>
  - <span data-ttu-id="f64df-124">資料圖形中顯示的 URL 資訊</span><span class="sxs-lookup"><span data-stu-id="f64df-124">URL information displayed in data graphs</span></span>
  - <span data-ttu-id="f64df-125">有關按一下郵件中按一下 [時間資料</span><span class="sxs-lookup"><span data-stu-id="f64df-125">Time-of-click data about clicks in messages</span></span>

- <span data-ttu-id="f64df-126">每當發生變更時在 URL 中按一下 [verdict，您會看到警示。</span><span class="sxs-lookup"><span data-stu-id="f64df-126">Whenever there's a change in a URL click verdict, you'll see an alert.</span></span> <span data-ttu-id="f64df-127">當 URL 信譽變更後的爆炸，或是當受保護的 ATP 安全連結的使用者，可以變更結果的 URL 按一下會覆寫[ATP 安全連結警告](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="f64df-127">URL click verdicts can change when a URL’s reputation changes post-detonation, or when a user who's protected by ATP Safe Links overrides an [ATP Safe Links warning](atp-safe-links-warning-pages.md).</span></span>  
 
<span data-ttu-id="f64df-128">這些增強功能可讓您組織的安全性系統管理員可以檢視的詳細資訊比之前。</span><span class="sxs-lookup"><span data-stu-id="f64df-128">These enhancements enable your organization's security administrators to view more details than before.</span></span> <span data-ttu-id="f64df-129">安全性系統管理員可以檢視資訊相關的 URL 網域] 中，未接的 Url，按一下結果，以及更多]，並再適當地調整 Office 365 ATP 原則。</span><span class="sxs-lookup"><span data-stu-id="f64df-129">Security administrators can view information about URL domains, missed URLs, click verdicts, and more, and then adjust Office 365 ATP policies appropriately.</span></span>

> [!NOTE]
> <span data-ttu-id="f64df-130">雖然這些功能是在預覽，URL 資料將會提供有限數量的天數。</span><span class="sxs-lookup"><span data-stu-id="f64df-130">While these features are in preview, URL data will be available for a limited number of days.</span></span> 

## <a name="see-malware-detected-in-email-by-technology"></a><span data-ttu-id="f64df-131">請參閱技術電子郵件中偵測到的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="f64df-131">See malware detected in email by technology</span></span>

<span data-ttu-id="f64df-132">假設您想要查看 Office 365 技術的電子郵件中偵測到的惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="f64df-132">Suppose you want to see malware detected in email, by Office 365 technology.</span></span> <span data-ttu-id="f64df-133">若要這麼做，請使用檔案總管] （或即時偵測的資訊） 的[電子郵件 > 惡意程式碼](threat-explorer-views.md#email--malware)檢視。</span><span class="sxs-lookup"><span data-stu-id="f64df-133">To do this, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="f64df-134">在安全性 & 合規性中心 ([https://protection.office.com](https://protection.office.com))，選擇 [**威脅管理** > **檔案總管]** （或**即時偵測**）。</span><span class="sxs-lookup"><span data-stu-id="f64df-134">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="f64df-135">（此範例會使用檔案總管）。</span><span class="sxs-lookup"><span data-stu-id="f64df-135">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="f64df-136">在 [**檢視**] 功能表中，選擇 [**電子郵件** > **惡意程式碼**。</span><span class="sxs-lookup"><span data-stu-id="f64df-136">In the **View** menu, choose **Email** > **Malware**.</span></span><br/><span data-ttu-id="f64df-137">![瀏覽器的 [檢視] 功能表](media/ExplorerViewEmailMalwareMenu.png)</span><span class="sxs-lookup"><span data-stu-id="f64df-137">![View menu for Explorer](media/ExplorerViewEmailMalwareMenu.png)</span></span><br/>

3. <span data-ttu-id="f64df-138">按一下 [**寄件者**，，然後選擇 [**基本** > **偵測技術**。</span><span class="sxs-lookup"><span data-stu-id="f64df-138">Click **Sender**, and then choose **Basic** > **Detection technology**.</span></span><br/><span data-ttu-id="f64df-139">偵測技術現在可做為報表的篩選。</span><span class="sxs-lookup"><span data-stu-id="f64df-139">Your detection technologies are now available as filters for the report.</span></span><br/><span data-ttu-id="f64df-140">![惡意程式碼偵測技術](media/ExplorerEmailMalwareDetectionTech.png)</span><span class="sxs-lookup"><span data-stu-id="f64df-140">![Malware detection technologies](media/ExplorerEmailMalwareDetectionTech.png)</span></span><br/> 

4. <span data-ttu-id="f64df-141">選取一個選項，然後按一下 [**重新整理**] 按鈕，以套用該篩選器。</span><span class="sxs-lookup"><span data-stu-id="f64df-141">Select an option, and then click the **Refresh** button to apply that filter.</span></span><br/><span data-ttu-id="f64df-142">![選取的偵測技術](media/ExplorerEmailMalwareDetectionTechATP.png)</span><span class="sxs-lookup"><span data-stu-id="f64df-142">![Selected detection technology](media/ExplorerEmailMalwareDetectionTechATP.png)</span></span><br/> 

<span data-ttu-id="f64df-143">若要顯示在電子郵件，使用您所選取的技術選項中偵測到的結果惡意程式碼會重新整理報表。</span><span class="sxs-lookup"><span data-stu-id="f64df-143">The report refreshes to show the results malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="f64df-144">從這裡開始，您可以進行進一步分析。</span><span class="sxs-lookup"><span data-stu-id="f64df-144">From here, you can conduct further analysis.</span></span>

## <a name="view-data-about-phishing-urls-and-click-verdict"></a><span data-ttu-id="f64df-145">檢視網路釣魚 Url 相關資料，並按一下 verdict</span><span class="sxs-lookup"><span data-stu-id="f64df-145">View data about phishing URLs and click verdict</span></span>

<span data-ttu-id="f64df-146">假設您想要查看網路釣魚電子郵件，包括允許、 封鎖，並覆寫的 Url 清單中嘗試透過 Url。</span><span class="sxs-lookup"><span data-stu-id="f64df-146">Suppose that you want to see phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="f64df-147">識別已按下的 Url 需要設定[ATP 安全連結](atp-safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="f64df-147">Identifying URLs that were clicked requires [ATP Safe links](atp-safe-links.md) to be configured.</span></span> <span data-ttu-id="f64df-148">請確定已設定[ATP 安全連結原則](set-up-atp-safe-links-policies.md)的時間按一下 [保護和記錄按一下由 ATP 安全連結的結果。</span><span class="sxs-lookup"><span data-stu-id="f64df-148">Make sure that you have set up [ATP Safe Links policies](set-up-atp-safe-links-policies.md) for time-of-click protection and logging of click verdicts by ATP Safe Links.</span></span> 

<span data-ttu-id="f64df-149">若要檢閱郵件及釣魚程式訊息中的按 Url 中的釣魚程式 Url，請使用檔案總管] （或即時偵測的資訊） 的[電子郵件 > 釣魚程式](threat-explorer-views.md#email--phish)檢視。</span><span class="sxs-lookup"><span data-stu-id="f64df-149">To review phish URLs in messages and clicks on URLs in phish messages, use the [Email > Phish](threat-explorer-views.md#email--phish) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="f64df-150">在安全性 & 合規性中心 ([https://protection.office.com](https://protection.office.com))，選擇 [**威脅管理** > **檔案總管]** （或**即時偵測**）。</span><span class="sxs-lookup"><span data-stu-id="f64df-150">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="f64df-151">（此範例會使用檔案總管）。</span><span class="sxs-lookup"><span data-stu-id="f64df-151">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="f64df-152">在 [**檢視**] 功能表中，選擇 [**電子郵件** > **釣魚程式**。</span><span class="sxs-lookup"><span data-stu-id="f64df-152">In the **View** menu, choose **Email** > **Phish**.</span></span><br/><span data-ttu-id="f64df-153">![瀏覽器的 [檢視] 功能表](media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="f64df-153">![View menu for Explorer](media/ExplorerViewEmailPhishMenu.png)</span></span><br/>

3. <span data-ttu-id="f64df-154">按一下 [**寄件者**，，然後選擇 [ **Url** > **按一下 verdict**。</span><span class="sxs-lookup"><span data-stu-id="f64df-154">Click **Sender**, and then choose **URLs** > **Click verdict**.</span></span>

4. <span data-ttu-id="f64df-155">選取一或多個選項，例如**封鎖**及**封鎖覆寫**]，然後按一下 [套用該篩選選項的同一行上的 [**重新整理**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="f64df-155">Select one or more options, such as **Blocked** and **Block overridden**, and then click the **Refresh** button that is on the same line as the options to apply that filter.</span></span> <span data-ttu-id="f64df-156">（未重新整理瀏覽器視窗。）</span><span class="sxs-lookup"><span data-stu-id="f64df-156">(Don't refresh your browser window.)</span></span><br/><span data-ttu-id="f64df-157">![Url 並按一下 [結果](media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span><span class="sxs-lookup"><span data-stu-id="f64df-157">![URLs and click verdicts](media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span></span><br/>

    <span data-ttu-id="f64df-158">若要顯示在 [報告] 下的 [URL] 索引標籤上的兩個不同的 URL 資料表重新整理報表：</span><span class="sxs-lookup"><span data-stu-id="f64df-158">The report refreshes to show two different URL tables on the URL tab under the report:</span></span>

   1. <span data-ttu-id="f64df-159">**Top Url**是 Url 包含在郵件中您有篩選向下，和電子郵件傳遞巨集指令會計算每個 URL。</span><span class="sxs-lookup"><span data-stu-id="f64df-159">**Top URLs** are the URLs contained in the messages you have filtered down to, and the email delivery action counts for each URL.</span></span> <span data-ttu-id="f64df-160">在釣魚程式的電子郵件檢視中，這份清單通常會包含合法的 Url。</span><span class="sxs-lookup"><span data-stu-id="f64df-160">In the phish email view, this list typically will contain legitimate URLs.</span></span> <span data-ttu-id="f64df-161">攻擊者嘗試以協助他們傳遞，其郵件中包括混合的良好且不正確的 Url，但會進行更有趣的使用者按一下惡意連結。</span><span class="sxs-lookup"><span data-stu-id="f64df-161">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they will make the malicious links more interesting for the user to click.</span></span> <span data-ttu-id="f64df-162">總數的電子郵件計數排序表格的 Url (請注意： 此資料行不會顯示以簡化檢視)。</span><span class="sxs-lookup"><span data-stu-id="f64df-162">The table of URLs is sorted by total email count (NOTE: This column is not shown to simplify the view).</span></span>

   2. <span data-ttu-id="f64df-163">**按一下頂端**是安全連結進行三重包裝 Url 所按下，排序總計按一下的計數 （此資料行也不會顯示以簡化檢視）。</span><span class="sxs-lookup"><span data-stu-id="f64df-163">**Top clicks** are the Safe Links wrapped URLs that were clicked, sorted by total click count (this column is also not shown to simplify the view).</span></span> <span data-ttu-id="f64df-164">依欄的總計數指出安全連結按一下 verdict 計數的每個已按選的 URL。</span><span class="sxs-lookup"><span data-stu-id="f64df-164">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="f64df-165">在 [釣魚程式的電子郵件] 檢視中，這些更多的通常可疑或惡意 Url，但可能包括釣魚程式的郵件中的全新 Url。</span><span class="sxs-lookup"><span data-stu-id="f64df-165">In the phish email view, these are more often suspicious or malicious URLs, but could include clean URLs that are in phish messages.</span></span> <span data-ttu-id="f64df-166">這裡不會顯示 URL 按包裝的連結。</span><span class="sxs-lookup"><span data-stu-id="f64df-166">URL clicks on unwrapped links will not show up here.</span></span>
   
   <span data-ttu-id="f64df-167">兩個 Url 資料表傳遞巨集指令並位置、 網路釣魚電子郵件中顯示上方的 Url，它們會顯示已封鎖 （或瀏覽儘管警告） URL 點選連結，讓您可以了解哪些可能會損毀使用者收到且使用者互動。</span><span class="sxs-lookup"><span data-stu-id="f64df-167">The two URLs tables show top URLs in phishing emails by delivery action and location, and they show URL clicks that were blocked (or visited despite a warning) so that you can understand what potential bad links were received by users and interacted with by users.</span></span> <span data-ttu-id="f64df-168">從這裡開始，您可以進行進一步分析。</span><span class="sxs-lookup"><span data-stu-id="f64df-168">From here, you can conduct further analysis.</span></span> <span data-ttu-id="f64df-169">比方說，下方圖表，您可以看到已封鎖您組織的環境中的電子郵件中的頂端 Url。</span><span class="sxs-lookup"><span data-stu-id="f64df-169">For example, below the chart, you can see the top URLs in emails that were blocked in your organization's environment.</span></span>
   
   ![已封鎖的檔案總管 Url](media/ExplorerPhishClickVerdictURLs.png)
   
   <span data-ttu-id="f64df-171">選取要檢視的詳細的資訊的 URL。</span><span class="sxs-lookup"><span data-stu-id="f64df-171">Select a URL to view more detailed information.</span></span> <span data-ttu-id="f64df-172">請注意，在 URL 彈出式視窗] 對話方塊中，若要顯示在您的環境中的 URL 的曝光度的完整檢視會移除在電子郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="f64df-172">Note that in the URL flyout dialog, the filtering on emails is removed to show you the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="f64df-173">這可讓您篩選下電子郵件中檔案總管和擔心，找出潛在威脅，然後展開 （透過 URL 的詳細資料] 對話方塊） 環境中的 URL 公開您了解，而不必新增 URL 篩選器以特定 Url總管檢視本身。</span><span class="sxs-lookup"><span data-stu-id="f64df-173">This lets you filter down emails in Explorer to ones you are concerned about, find specific URLs that are potential threats, then expand your understanding of the URL exposure in your environment (via the URL details dialog) without having to add URL filters to the Explorer view itself.</span></span>

## <a name="review-email-messages-reported-by-users"></a><span data-ttu-id="f64df-174">檢閱報告的使用者的電子郵件訊息</span><span class="sxs-lookup"><span data-stu-id="f64df-174">Review email messages reported by users</span></span>

<span data-ttu-id="f64df-175">假設您想要請參閱 < 在您的組織中的使用者會回報的電子郵件為垃圾郵件、 不是垃圾郵件或網路釣魚使用<b0>報告訊息增益集以進行 Outlook 和 outlook 網頁版</b0>。</span><span class="sxs-lookup"><span data-stu-id="f64df-175">Suppose that you want to see email messages that users in your organization have reported as Junk, Not Junk, or Phishing by using the [Report Message add-in for Outlook and Outlook on the web](enable-the-report-message-add-in.md).</span></span> <span data-ttu-id="f64df-176">若要這麼做，請使用[電子郵件 > 使用者回報](threat-explorer-views.md#email--user-reported)Explorer （或即時偵測的資訊） 的檢視。</span><span class="sxs-lookup"><span data-stu-id="f64df-176">To do this, use the [Email > User-reported](threat-explorer-views.md#email--user-reported) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="f64df-177">在安全性 & 合規性中心 ([https://protection.office.com](https://protection.office.com))，選擇 [**威脅管理** > **檔案總管]** （或**即時偵測**）。</span><span class="sxs-lookup"><span data-stu-id="f64df-177">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="f64df-178">（此範例會使用檔案總管）。</span><span class="sxs-lookup"><span data-stu-id="f64df-178">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="f64df-179">在 [**檢視**] 功能表中，選擇 [**電子郵件** > **使用者報告**。</span><span class="sxs-lookup"><span data-stu-id="f64df-179">In the **View** menu, choose **Email** > **User-reported**.</span></span><br/><span data-ttu-id="f64df-180">![瀏覽器的 [檢視] 功能表](media/ExplorerViewMenuEmailUserReported.png)</span><span class="sxs-lookup"><span data-stu-id="f64df-180">![View menu for Explorer](media/ExplorerViewMenuEmailUserReported.png)</span></span><br/>

3. <span data-ttu-id="f64df-181">按一下 [**寄件者**，，然後選擇 [**基本** > **報表類型**。</span><span class="sxs-lookup"><span data-stu-id="f64df-181">Click **Sender**, and then choose **Basic** > **Report type**.</span></span>

4. <span data-ttu-id="f64df-182">選取一個選項，例如**釣魚程式**，，然後按一下 [**重新整理**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="f64df-182">Select an option, such as **Phish**, and then click the **Refresh** button.</span></span> <br/><span data-ttu-id="f64df-183">![使用者報告的釣魚程式](media/EmailUserReportedReportType.png)</span><span class="sxs-lookup"><span data-stu-id="f64df-183">![User-reported phish](media/EmailUserReportedReportType.png)</span></span><br/> 

<span data-ttu-id="f64df-184">報表會重新整理以顯示您組織中的人員已回報為網路釣魚嘗試的電子郵件的相關資料。</span><span class="sxs-lookup"><span data-stu-id="f64df-184">The report refreshes to show data about email messages that people in your organization have reported as a phishing attempt.</span></span> <span data-ttu-id="f64df-185">您可以使用此資訊來進一步進行分析，並如有必要，調整您的[ATP 防網路釣魚原則](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="f64df-185">You can use this information to conduct further analysis, and if necessary, adjust your [ATP anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="f64df-186">啟動自動化的調查及回應</span><span class="sxs-lookup"><span data-stu-id="f64df-186">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="f64df-187">自動化的調查及回應功能都可以在**Office 365 ATP 計劃 2**和**Office 365 E5**。</span><span class="sxs-lookup"><span data-stu-id="f64df-187">Automated investigation and response capabilities are available in **Office 365 ATP Plan 2** and **Office 365 E5**.</span></span>

<span data-ttu-id="f64df-188">（新 ！）[自動化調查及回應](automated-investigation-response-office.md)可以儲存您的安全性作業小組多時間和精力調查，並減輕網路攻擊。</span><span class="sxs-lookup"><span data-stu-id="f64df-188">(NEW!) [Automated investigation and response](automated-investigation-response-office.md) can save your security operations team much time and effort in investigating and mitigating cyber attacks.</span></span> <span data-ttu-id="f64df-189">除了設定可以觸發安全性 playbook 的提醒，您可以從瀏覽器中檢視啟動自動的調查及回應程序。</span><span class="sxs-lookup"><span data-stu-id="f64df-189">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span> 

<span data-ttu-id="f64df-190">如需這的詳細資訊，請參閱[範例： 安全性系統管理員會觸發從 Explorer 調查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="f64df-190">For details on this, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="more-ways-to-use-explorer-or-real-time-detections"></a><span data-ttu-id="f64df-191">若要使用檔案總管] （或即時偵測的資訊） 的更多方法</span><span class="sxs-lookup"><span data-stu-id="f64df-191">More ways to use Explorer (or real-time detections)</span></span>

<span data-ttu-id="f64df-192">除了本文中所述的案例，您有許多詳細報告可用選項與檔案總管] （或即時偵測的資訊）。</span><span class="sxs-lookup"><span data-stu-id="f64df-192">In addition to the scenarios outlined in this article, you have many more reporting options available with Explorer (or real-time detections).</span></span> 
- [<span data-ttu-id="f64df-193">尋找並調查傳送的惡意電子郵件</span><span class="sxs-lookup"><span data-stu-id="f64df-193">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="f64df-194">檢視 SharePoint Online、 OneDrive 及 Microsoft Teams 中偵測到的惡意檔案</span><span class="sxs-lookup"><span data-stu-id="f64df-194">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
- [<span data-ttu-id="f64df-195">概略了解威脅總管 （和即時偵測的資訊） 中的檢視</span><span class="sxs-lookup"><span data-stu-id="f64df-195">Get an overview of the views in Threat Explorer (and real-time detections)</span></span>](threat-explorer-views.md)

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="f64df-196">所需的授權和權限</span><span class="sxs-lookup"><span data-stu-id="f64df-196">Required licenses and permissions</span></span>

<span data-ttu-id="f64df-197">您必須擁有[Office 365 ATP](office-365-atp.md)若要取得檔案總管] 或 [即時偵測的資訊。</span><span class="sxs-lookup"><span data-stu-id="f64df-197">You must have [Office 365 ATP](office-365-atp.md) to get Explorer or real-time detections.</span></span>
- <span data-ttu-id="f64df-198">Explorer 隨附於 Office 365 ATP 計劃 2。</span><span class="sxs-lookup"><span data-stu-id="f64df-198">Explorer is included in Office 365 ATP Plan 2.</span></span> 
- <span data-ttu-id="f64df-199">[即時偵測] 報告隨附於 Office 365 ATP 計劃 1。</span><span class="sxs-lookup"><span data-stu-id="f64df-199">The real-time detections report is included in Office 365 ATP Plan 1.</span></span>

<span data-ttu-id="f64df-200">若要檢視並使用檔案總管] 或 [即時的偵測，您必須使用適當的權限，例如授與安全性系統管理員或安全性讀取者。</span><span class="sxs-lookup"><span data-stu-id="f64df-200">To view and use Explorer or real-time detections, you must have appropriate permissions, such as those granted to a security administrator or security reader.</span></span> 

- <span data-ttu-id="f64df-201">Security&amp;合規性中心，您必須有一個指派的下列角色：</span><span class="sxs-lookup"><span data-stu-id="f64df-201">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="f64df-202">組織管理</span><span class="sxs-lookup"><span data-stu-id="f64df-202">Organization Management</span></span>
    - <span data-ttu-id="f64df-203">安全性系統管理員 (這可以在 Azure Active Directory 系統管理中心中指派 ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span><span class="sxs-lookup"><span data-stu-id="f64df-203">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
    - <span data-ttu-id="f64df-204">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="f64df-204">Security Reader</span></span>

- <span data-ttu-id="f64df-205">若是 Exchange Online 中，您必須安裝下列其中一個在 Exchange 系統管理中心中指派下列角色 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) 或使用 PowerShell cmdlet (請參閱[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span><span class="sxs-lookup"><span data-stu-id="f64df-205">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span></span>
    - <span data-ttu-id="f64df-206">組織管理</span><span class="sxs-lookup"><span data-stu-id="f64df-206">Organization Management</span></span>
    - <span data-ttu-id="f64df-207">僅檢視組織管理</span><span class="sxs-lookup"><span data-stu-id="f64df-207">View-only Organization Management</span></span>
    - <span data-ttu-id="f64df-208">僅檢視收件者角色</span><span class="sxs-lookup"><span data-stu-id="f64df-208">View-Only Recipients role</span></span>
    - <span data-ttu-id="f64df-209">合規性管理</span><span class="sxs-lookup"><span data-stu-id="f64df-209">Compliance Management</span></span>

<span data-ttu-id="f64df-210">若要深入了解角色和權限，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="f64df-210">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="f64df-211">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="f64df-211">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="f64df-212">Exchange Online 中的功能權限</span><span class="sxs-lookup"><span data-stu-id="f64df-212">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
  
