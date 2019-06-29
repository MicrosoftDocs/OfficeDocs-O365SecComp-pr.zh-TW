---
title: 威脅瀏覽器 (和即時偵測)
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/20/2019
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
description: 深入瞭解安全性&amp;與規範中心中的 Explorer (和即時偵測)。
ms.openlocfilehash: 3d2eab30b97655b692ed1bfe089b6a79834fd110
ms.sourcegitcommit: 011bfa60cafdf47900aadf96a17eb275efa877c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2019
ms.locfileid: "35394348"
---
# <a name="threat-explorer-and-real-time-detections"></a><span data-ttu-id="caa28-103">威脅瀏覽器 (和即時偵測)</span><span class="sxs-lookup"><span data-stu-id="caa28-103">Threat Explorer (and real-time detections)</span></span>

<span data-ttu-id="caa28-104">如果您的組織有[office 365 高級威脅防護](office-365-atp.md)(OFFICE 365 ATP), 而且您有[必要的許可權](#required-licenses-and-permissions), 您可以使用**Explorer**或**即時**偵測 (先前稱為*即時報告*),[請參閱新功能](#new-features-in-real-time-detections)!</span><span class="sxs-lookup"><span data-stu-id="caa28-104">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (Office 365 ATP), and you have the [necessary permissions](#required-licenses-and-permissions), you have either **Explorer** or **real-time detections** (formerly *real-time reports* — [see what's new](#new-features-in-real-time-detections)!).</span></span> <span data-ttu-id="caa28-105">在 [安全性 & 規範中心] 中, 移至 [**威脅管理**], 然後選擇 [ **Explorer** ] 或 [**即時**偵測]。</span><span class="sxs-lookup"><span data-stu-id="caa28-105">In the Security & Compliance Center, go to **Threat management**, and then choose **Explorer** OR **Real-time detections**.</span></span> 

|<span data-ttu-id="caa28-106">使用 ATP 方案2時, 您會看到:</span><span class="sxs-lookup"><span data-stu-id="caa28-106">With ATP Plan 2, you see:</span></span>  |<span data-ttu-id="caa28-107">使用 ATP 方案1時, 您會看到:</span><span class="sxs-lookup"><span data-stu-id="caa28-107">With ATP Plan 1, you see:</span></span>  |
|---------|---------|
|![威脅瀏覽器](media/threatmgmt-explorer.png)      |![即時偵測](media/threatmgmt-realtimedetections.png)         |

<span data-ttu-id="caa28-110">使用 Explorer (或即時偵測) 時, 您有一個功能強大的報告, 可讓您的安全性作業小組有效且有效地調查和回應威脅, 其方式如下:</span><span class="sxs-lookup"><span data-stu-id="caa28-110">With Explorer (or real-time detections), you have a powerful report that enables your Security Operations team to investigate and respond to threats effectively and efficiently, and it resembles the following image:</span></span> 

![移至 [威脅\>管理瀏覽器]](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="caa28-112">您可以使用此報告, 進行下列作業:</span><span class="sxs-lookup"><span data-stu-id="caa28-112">With this report, you can:</span></span>
- [<span data-ttu-id="caa28-113">查看 Office 365 安全性功能偵測到的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="caa28-113">See malware detected by Office 365 security features</span></span>](#see-malware-detected-in-email-by-technology)
- <span data-ttu-id="caa28-114">[查看仿冒 Url 的資料, 然後按一下 [判定]](#view-data-about-phishing-urls-and-click-verdict)</span><span class="sxs-lookup"><span data-stu-id="caa28-114">[View data about phishing URLs and click verdict](#view-data-about-phishing-urls-and-click-verdict)</span></span>
- <span data-ttu-id="caa28-115">[從瀏覽器中的視圖開始自動調查和回應](#start-automated-investigation-and-response)程式(僅限 ATP 方案 2)</span><span class="sxs-lookup"><span data-stu-id="caa28-115">[Start an automated investigation and response process from a view in Explorer](#start-automated-investigation-and-response) (ATP Plan 2 only)</span></span>
- <span data-ttu-id="caa28-116">...[調查惡意電子郵件和更多內容](#more-ways-to-use-explorer-or-real-time-detections)!</span><span class="sxs-lookup"><span data-stu-id="caa28-116">... [Investigate malicious email, and more](#more-ways-to-use-explorer-or-real-time-detections)!</span></span>

## <a name="new-features-in-real-time-detections"></a><span data-ttu-id="caa28-117">即時偵測中的新功能</span><span class="sxs-lookup"><span data-stu-id="caa28-117">New features in real-time detections</span></span>

<span data-ttu-id="caa28-118">Explorer/即時偵測會新增新的新欄位, 以提供更完整的電子郵件領域。</span><span class="sxs-lookup"><span data-stu-id="caa28-118">Explorer / real-time detections adds fresh new fields designed to give you a more complete picture of where your emails land.</span></span> <span data-ttu-id="caa28-119">此變更的其中一部分是讓搜尋更容易進行安全性操作人員, 但是 net 結果是一眼就知道問題電子郵件的位置。</span><span class="sxs-lookup"><span data-stu-id="caa28-119">Part of the goal of this change is to make hunting easier for Security Ops people, but the net result is knowing the location of problem emails at a glance.</span></span>

<span data-ttu-id="caa28-120">這是如何完成？</span><span class="sxs-lookup"><span data-stu-id="caa28-120">How is this done?</span></span> <span data-ttu-id="caa28-121">傳遞狀態現在會分成兩欄:</span><span class="sxs-lookup"><span data-stu-id="caa28-121">Delivery Status is now broken out into two columns:</span></span>

- <span data-ttu-id="caa28-122">傳遞動作-此電子郵件的狀態為何？</span><span class="sxs-lookup"><span data-stu-id="caa28-122">Delivery Action - What is the status of this email?</span></span>
- <span data-ttu-id="caa28-123">傳遞位置-這封電子郵件會做為結果的路由？</span><span class="sxs-lookup"><span data-stu-id="caa28-123">Delivery Location - Where was this email routed as a result?</span></span>

<span data-ttu-id="caa28-124">傳遞動作是由於現有的原則或偵測而對電子郵件採取的動作。</span><span class="sxs-lookup"><span data-stu-id="caa28-124">Delivery Action is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="caa28-125">以下是電子郵件可能採取的動作:</span><span class="sxs-lookup"><span data-stu-id="caa28-125">Here are the possible actions an email can take:</span></span>

|<span data-ttu-id="caa28-126">送貨</span><span class="sxs-lookup"><span data-stu-id="caa28-126">Delivered</span></span>  |<span data-ttu-id="caa28-127">Junked</span><span class="sxs-lookup"><span data-stu-id="caa28-127">Junked</span></span>  |<span data-ttu-id="caa28-128">凍結</span><span class="sxs-lookup"><span data-stu-id="caa28-128">Blocked</span></span>  |<span data-ttu-id="caa28-129">代替</span><span class="sxs-lookup"><span data-stu-id="caa28-129">Replaced</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="caa28-130">電子郵件已傳遞至使用者的收件匣或資料夾, 而且使用者可以直接存取它。</span><span class="sxs-lookup"><span data-stu-id="caa28-130">Email was delivered to Inbox or folder of a user and the user can directly access it.</span></span>    | <span data-ttu-id="caa28-131">電子郵件已傳送至使用者的垃圾郵件資料夾或已刪除的資料夾, 且使用者可以存取這些資料夾中的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="caa28-131">Email was sent to either user’s Junk folder or Deleted folder, and the user has access to emails in those folders.</span></span>       | <span data-ttu-id="caa28-132">任何被隔離、失敗或被捨棄的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="caa28-132">Any emails that are quarantined, that  failed, or were dropped.</span></span> <span data-ttu-id="caa28-133">使用者完全無法存取此功能!</span><span class="sxs-lookup"><span data-stu-id="caa28-133">This is completely inaccessible by the user!</span></span>     | <span data-ttu-id="caa28-134">任何電子郵件, 其中惡意附件會由指出附件惡意的 .txt 檔案所取代。</span><span class="sxs-lookup"><span data-stu-id="caa28-134">Any email where malicious attachments are replaced by .txt files that state the attachment was malicious.</span></span>     |

<span data-ttu-id="caa28-135">以下是使用者可以看到的內容, 以及無法執行的動作:</span><span class="sxs-lookup"><span data-stu-id="caa28-135">And here is what the user can see, and what they can't:</span></span>

|<span data-ttu-id="caa28-136">可供使用者存取</span><span class="sxs-lookup"><span data-stu-id="caa28-136">Accessible to end users</span></span>  |<span data-ttu-id="caa28-137">無法存取使用者</span><span class="sxs-lookup"><span data-stu-id="caa28-137">Inaccessible to end users</span></span>  |
|---------|---------|
|<span data-ttu-id="caa28-138">送貨</span><span class="sxs-lookup"><span data-stu-id="caa28-138">Delivered</span></span>     | <span data-ttu-id="caa28-139">凍結</span><span class="sxs-lookup"><span data-stu-id="caa28-139">Blocked</span></span>        |
|<span data-ttu-id="caa28-140">Junked</span><span class="sxs-lookup"><span data-stu-id="caa28-140">Junked</span></span>     | <span data-ttu-id="caa28-141">代替</span><span class="sxs-lookup"><span data-stu-id="caa28-141">Replaced</span></span>        |

<span data-ttu-id="caa28-142">[傳遞位置] 顯示執行傳遞後的原則和偵測結果。</span><span class="sxs-lookup"><span data-stu-id="caa28-142">Delivery location shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="caa28-143">它會連結至傳遞動作。</span><span class="sxs-lookup"><span data-stu-id="caa28-143">It's linked to a Delivery Action.</span></span> <span data-ttu-id="caa28-144">新增此欄位是為了深入瞭解當發現問題郵件時所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="caa28-144">This field was added to give insight into the action taken when a problem mail is found.</span></span> <span data-ttu-id="caa28-145">以下是 [傳遞位置] 的 possilbe 值:</span><span class="sxs-lookup"><span data-stu-id="caa28-145">Here are the possilbe values of delivery location:</span></span>

1. <span data-ttu-id="caa28-146">收件匣或資料夾-電子郵件位於 [收件匣] 或 [資料夾 (根據您的電子郵件規則)。</span><span class="sxs-lookup"><span data-stu-id="caa28-146">Inbox or folder – The email is in inbox or a folder (according to your email rules).</span></span>
2. <span data-ttu-id="caa28-147">部署或外部–信箱不存在於雲端上, 但在內部部署。</span><span class="sxs-lookup"><span data-stu-id="caa28-147">On-prem or external – The mailbox doesn’t exist on cloud but is on-premises.</span></span>
3. <span data-ttu-id="caa28-148">垃圾郵件資料夾–在使用者的 [垃圾郵件] 資料夾中的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="caa28-148">Junk folder – The email in in the Junk folder of a user.</span></span>
4. <span data-ttu-id="caa28-149">[刪除的郵件] 資料夾–使用者的 [刪除的郵件] 資料夾中的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="caa28-149">Deleted items folder – The email in the Deleted items folder of a user.</span></span>
5. <span data-ttu-id="caa28-150">隔離–隔離中的電子郵件, 且不在使用者的信箱中。</span><span class="sxs-lookup"><span data-stu-id="caa28-150">Quarantine – The email in quarantine, and is not in a user’s mailbox.</span></span>
6. <span data-ttu-id="caa28-151">失敗–電子郵件無法送達信箱。</span><span class="sxs-lookup"><span data-stu-id="caa28-151">Failed – The email failed to reach the mailbox.</span></span>
7. <span data-ttu-id="caa28-152">捨棄–電子郵件會在郵件流程中的某處遺失。</span><span class="sxs-lookup"><span data-stu-id="caa28-152">Dropped – The email gets lost somewhere in the Mailflow.</span></span>

## <a name="see-malware-detected-in-email-by-technology"></a><span data-ttu-id="caa28-153">查看透過技術在電子郵件中偵測到的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="caa28-153">See malware detected in email by technology</span></span>

<span data-ttu-id="caa28-154">假設您想要查看以 Office 365 技術在電子郵件中偵測到惡意程式碼的情況。</span><span class="sxs-lookup"><span data-stu-id="caa28-154">Suppose you want to see malware detected in email, by Office 365 technology.</span></span> <span data-ttu-id="caa28-155">若要執行這項操作, 請使用瀏覽器 (或即時偵測) 的[電子郵件 > 惡意](threat-explorer-views.md#email--malware)代碼視圖。</span><span class="sxs-lookup"><span data-stu-id="caa28-155">To do this, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="caa28-156">在 [安全性 & 規範中心 ([https://protection.office.com](https://protection.office.com))] 中, 選擇 [**威脅管理** > **瀏覽器**] (或 [**即時**偵測])。</span><span class="sxs-lookup"><span data-stu-id="caa28-156">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="caa28-157">(此範例會使用 Explorer)。</span><span class="sxs-lookup"><span data-stu-id="caa28-157">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="caa28-158">在 [**視圖**] 功能表中, 選擇 [**電子郵件** > **惡意**代碼]。</span><span class="sxs-lookup"><span data-stu-id="caa28-158">In the **View** menu, choose **Email** > **Malware**.</span></span><br/><span data-ttu-id="caa28-159">![瀏覽器的 [視圖] 功能表](media/ExplorerViewEmailMalwareMenu.png)</span><span class="sxs-lookup"><span data-stu-id="caa28-159">![View menu for Explorer](media/ExplorerViewEmailMalwareMenu.png)</span></span><br/>

3. <span data-ttu-id="caa28-160">按一下 [**寄件者**], 然後選擇 [**基本** > **偵測技術**]。</span><span class="sxs-lookup"><span data-stu-id="caa28-160">Click **Sender**, and then choose **Basic** > **Detection technology**.</span></span><br/><span data-ttu-id="caa28-161">您的偵測技術現在可做為報告的篩選器。</span><span class="sxs-lookup"><span data-stu-id="caa28-161">Your detection technologies are now available as filters for the report.</span></span><br/><span data-ttu-id="caa28-162">![惡意軟體偵測技術](media/ExplorerEmailMalwareDetectionTech.png)</span><span class="sxs-lookup"><span data-stu-id="caa28-162">![Malware detection technologies](media/ExplorerEmailMalwareDetectionTech.png)</span></span><br/> 

4. <span data-ttu-id="caa28-163">選取 [選項], 然後按一下 [ \*\*\*\* 重新整理] 按鈕套用該篩選。</span><span class="sxs-lookup"><span data-stu-id="caa28-163">Select an option, and then click the **Refresh** button to apply that filter.</span></span><br/><span data-ttu-id="caa28-164">![選取偵測技術](media/ExplorerEmailMalwareDetectionTechATP.png)</span><span class="sxs-lookup"><span data-stu-id="caa28-164">![Selected detection technology](media/ExplorerEmailMalwareDetectionTechATP.png)</span></span><br/> 

<span data-ttu-id="caa28-165">報表會重新整理以顯示使用您選取的技術選項, 在電子郵件中偵測到惡意程式碼的結果。</span><span class="sxs-lookup"><span data-stu-id="caa28-165">The report refreshes to show the results malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="caa28-166">您可以從這裡進行進一步的分析。</span><span class="sxs-lookup"><span data-stu-id="caa28-166">From here, you can conduct further analysis.</span></span>

## <a name="view-data-about-phishing-urls-and-click-verdict"></a><span data-ttu-id="caa28-167">查看仿冒 Url 的資料, 然後按一下 [判定]</span><span class="sxs-lookup"><span data-stu-id="caa28-167">View data about phishing URLs and click verdict</span></span>

<span data-ttu-id="caa28-168">假設您想要透過電子郵件中的 Url 查看網路釣魚嘗試, 包括允許、封鎖及覆寫的 Url 清單。</span><span class="sxs-lookup"><span data-stu-id="caa28-168">Suppose that you want to see phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="caa28-169">識別所按一下的 Url 需要設定[ATP 安全連結](atp-safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="caa28-169">Identifying URLs that were clicked requires [ATP Safe links](atp-safe-links.md) to be configured.</span></span> <span data-ttu-id="caa28-170">請確定您已設定[Atp 安全連結原則](set-up-atp-safe-links-policies.md), 以在按一下 [保護] 和 [記錄] 時, 按一下 [Atp 安全連結] 的 [verdicts]。</span><span class="sxs-lookup"><span data-stu-id="caa28-170">Make sure that you have set up [ATP Safe Links policies](set-up-atp-safe-links-policies.md) for time-of-click protection and logging of click verdicts by ATP Safe Links.</span></span> 

<span data-ttu-id="caa28-171">若要查看郵件中的釣魚程式 Url, 並按一下網路釣魚郵件中的 Url, 請使用瀏覽器 (或即時偵測) 的[電子郵件 > 釣魚](threat-explorer-views.md#email--phish)者視圖。</span><span class="sxs-lookup"><span data-stu-id="caa28-171">To review phish URLs in messages and clicks on URLs in phish messages, use the [Email > Phish](threat-explorer-views.md#email--phish) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="caa28-172">在 [安全性 & 規範中心 ([https://protection.office.com](https://protection.office.com))] 中, 選擇 [**威脅管理** > **瀏覽器**] (或 [**即時**偵測])。</span><span class="sxs-lookup"><span data-stu-id="caa28-172">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="caa28-173">(此範例會使用 Explorer)。</span><span class="sxs-lookup"><span data-stu-id="caa28-173">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="caa28-174">在 [**視圖**] 功能表中, 選擇 [**電子郵件** > **釣魚詐騙**]。</span><span class="sxs-lookup"><span data-stu-id="caa28-174">In the **View** menu, choose **Email** > **Phish**.</span></span><br/><span data-ttu-id="caa28-175">![瀏覽器的 [視圖] 功能表](media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="caa28-175">![View menu for Explorer](media/ExplorerViewEmailPhishMenu.png)</span></span><br/>

3. <span data-ttu-id="caa28-176">按一下 [**寄件者**], 然後選擇 [ **url** > ]**按一下 [判定**]。</span><span class="sxs-lookup"><span data-stu-id="caa28-176">Click **Sender**, and then choose **URLs** > **Click verdict**.</span></span>

4. <span data-ttu-id="caa28-177">選取一或多個選項, 例如 [**封鎖**] 和 [封鎖已覆**寫**], 然後按一下位於同一行上的 [重新整理] 按鈕, 作為套用該篩選的選項。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="caa28-177">Select one or more options, such as **Blocked** and **Block overridden**, and then click the **Refresh** button that is on the same line as the options to apply that filter.</span></span> <span data-ttu-id="caa28-178">(不要重新整理瀏覽器視窗。)</span><span class="sxs-lookup"><span data-stu-id="caa28-178">(Don't refresh your browser window.)</span></span><br/><span data-ttu-id="caa28-179">![Url, 然後按一下 [verdicts]](media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span><span class="sxs-lookup"><span data-stu-id="caa28-179">![URLs and click verdicts](media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span></span><br/>

    <span data-ttu-id="caa28-180">報表會重新整理, 以在報表下的 [URL] 索引標籤上顯示兩個不同的 URL 表格:</span><span class="sxs-lookup"><span data-stu-id="caa28-180">The report refreshes to show two different URL tables on the URL tab under the report:</span></span>

   1. <span data-ttu-id="caa28-181">**Top url**是所篩選郵件中所包含的 url, 以及每個 URL 的電子郵件傳遞動作計數。</span><span class="sxs-lookup"><span data-stu-id="caa28-181">**Top URLs** are the URLs contained in the messages you have filtered down to, and the email delivery action counts for each URL.</span></span> <span data-ttu-id="caa28-182">在 [詐騙者電子郵件] 視圖中, 此清單通常會包含合法的 Url。</span><span class="sxs-lookup"><span data-stu-id="caa28-182">In the phish email view, this list typically will contain legitimate URLs.</span></span> <span data-ttu-id="caa28-183">攻擊者會在其郵件中混合使用良好且不良的 Url, 以嘗試傳遞這些 Url, 但他們會讓使用者更感興趣的惡意連結。</span><span class="sxs-lookup"><span data-stu-id="caa28-183">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they will make the malicious links more interesting for the user to click.</span></span> <span data-ttu-id="caa28-184">Url 的資料表是依電子郵件總數排序 (注意: 此欄不會顯示以簡化視圖)。</span><span class="sxs-lookup"><span data-stu-id="caa28-184">The table of URLs is sorted by total email count (NOTE: This column is not shown to simplify the view).</span></span>

   2. <span data-ttu-id="caa28-185">[**上一次按一下**] 是所按一下的安全連結包裝的 url, 依總按一下次數排序 (此欄也不會顯示以簡化視圖)。</span><span class="sxs-lookup"><span data-stu-id="caa28-185">**Top clicks** are the Safe Links wrapped URLs that were clicked, sorted by total click count (this column is also not shown to simplify the view).</span></span> <span data-ttu-id="caa28-186">[總計依據] 欄表示安全連結按一下每個按下 URL 的 [判定計數]。</span><span class="sxs-lookup"><span data-stu-id="caa28-186">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="caa28-187">在 [詐騙器電子郵件] 視圖中, 這些是較常見的可疑 Url, 但可能包含網路釣魚郵件中的清除 Url。</span><span class="sxs-lookup"><span data-stu-id="caa28-187">In the phish email view, these are more often suspicious or malicious URLs, but could include clean URLs that are in phish messages.</span></span> <span data-ttu-id="caa28-188">在此處不會顯示已開啟連結的 URL。</span><span class="sxs-lookup"><span data-stu-id="caa28-188">URL clicks on unwrapped links will not show up here.</span></span>
   
   <span data-ttu-id="caa28-189">這兩個 Url 表格會透過傳遞動作和位置來顯示網路釣魚電子郵件中的主要 Url, 並顯示已封鎖的 URL 按一下 (無論是在警告情況下進行存取), 以便您瞭解使用者所收到的潛在不良連結, 以及使用者所進行的互動。</span><span class="sxs-lookup"><span data-stu-id="caa28-189">The two URLs tables show top URLs in phishing emails by delivery action and location, and they show URL clicks that were blocked (or visited despite a warning) so that you can understand what potential bad links were received by users and interacted with by users.</span></span> <span data-ttu-id="caa28-190">您可以從這裡進行進一步的分析。</span><span class="sxs-lookup"><span data-stu-id="caa28-190">From here, you can conduct further analysis.</span></span> <span data-ttu-id="caa28-191">例如, 在圖表下方, 您可以在組織的環境中看到已封鎖的電子郵件中的最高 Url。</span><span class="sxs-lookup"><span data-stu-id="caa28-191">For example, below the chart, you can see the top URLs in emails that were blocked in your organization's environment.</span></span>
   
   ![已封鎖的 Explorer Url](media/ExplorerPhishClickVerdictURLs.png)
   
   <span data-ttu-id="caa28-193">選取 URL 以查看更詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="caa28-193">Select a URL to view more detailed information.</span></span> <span data-ttu-id="caa28-194">請注意, 在 [URL 飛入] 對話方塊中, 會移除在電子郵件上的篩選, 以顯示您的環境中 URL 公開的完整視圖。</span><span class="sxs-lookup"><span data-stu-id="caa28-194">Note that in the URL flyout dialog, the filtering on emails is removed to show you the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="caa28-195">這可讓您將瀏覽器中的電子郵件篩選為您關心的問題、找出潛在威脅的特定 Url, 然後展開您對環境中 URL 曝露的瞭解 (透過 URL 詳細資料對話方塊), 而不需要將 URL 篩選新增至資源管理器視圖本身。</span><span class="sxs-lookup"><span data-stu-id="caa28-195">This lets you filter down emails in Explorer to ones you are concerned about, find specific URLs that are potential threats, then expand your understanding of the URL exposure in your environment (via the URL details dialog) without having to add URL filters to the Explorer view itself.</span></span>

## <a name="review-email-messages-reported-by-users"></a><span data-ttu-id="caa28-196">查看使用者所報告的電子郵件訊息</span><span class="sxs-lookup"><span data-stu-id="caa28-196">Review email messages reported by users</span></span>

<span data-ttu-id="caa28-197">假設您想要查看組織中的使用者已報告為垃圾郵件、非垃圾郵件或網路釣魚的電子郵件, 方法是使用[Outlook 和 outlook 網頁版的報告訊息增益集](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="caa28-197">Suppose that you want to see email messages that users in your organization have reported as Junk, Not Junk, or Phishing by using the [Report Message add-in for Outlook and Outlook on the web](enable-the-report-message-add-in.md).</span></span> <span data-ttu-id="caa28-198">若要這麼做, 請使用瀏覽器 (或即時偵測) 的[使用者報告 > 的電子郵件](threat-explorer-views.md#email--user-reported)。</span><span class="sxs-lookup"><span data-stu-id="caa28-198">To do this, use the [Email > User-reported](threat-explorer-views.md#email--user-reported) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="caa28-199">在 [安全性 & 規範中心 ([https://protection.office.com](https://protection.office.com))] 中, 選擇 [**威脅管理** > **瀏覽器**] (或 [**即時**偵測])。</span><span class="sxs-lookup"><span data-stu-id="caa28-199">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="caa28-200">(此範例會使用 Explorer)。</span><span class="sxs-lookup"><span data-stu-id="caa28-200">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="caa28-201">在 [**視圖**] 功能表中, 選擇 [**電子郵件** > **使用者-已報告**]。</span><span class="sxs-lookup"><span data-stu-id="caa28-201">In the **View** menu, choose **Email** > **User-reported**.</span></span><br/><span data-ttu-id="caa28-202">![瀏覽器的 [視圖] 功能表](media/ExplorerViewMenuEmailUserReported.png)</span><span class="sxs-lookup"><span data-stu-id="caa28-202">![View menu for Explorer](media/ExplorerViewMenuEmailUserReported.png)</span></span><br/>

3. <span data-ttu-id="caa28-203">按一下 [**寄件者**], 然後選擇 [**基本** > **報告類型**]。</span><span class="sxs-lookup"><span data-stu-id="caa28-203">Click **Sender**, and then choose **Basic** > **Report type**.</span></span>

4. <span data-ttu-id="caa28-204">選取一個選項, 例如 [**網路釣魚**者], 然後\*\*\*\* 按一下 [重新整理] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="caa28-204">Select an option, such as **Phish**, and then click the **Refresh** button.</span></span> <br/><span data-ttu-id="caa28-205">![使用者報告的網路釣魚](media/EmailUserReportedReportType.png)</span><span class="sxs-lookup"><span data-stu-id="caa28-205">![User-reported phish](media/EmailUserReportedReportType.png)</span></span><br/> 

<span data-ttu-id="caa28-206">報表會重新整理, 以顯示組織中的人員已報告為網路釣魚嘗試的電子郵件訊息相關資料。</span><span class="sxs-lookup"><span data-stu-id="caa28-206">The report refreshes to show data about email messages that people in your organization have reported as a phishing attempt.</span></span> <span data-ttu-id="caa28-207">您可以使用此資訊進行進一步的分析, 並視需要調整[ATP 反網路釣魚原則](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="caa28-207">You can use this information to conduct further analysis, and if necessary, adjust your [ATP anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="caa28-208">啟動自動調查和回應</span><span class="sxs-lookup"><span data-stu-id="caa28-208">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="caa28-209">**Office 365 ATP Plan 2**和**Office 365 E5**提供自動化的調查和回應功能。</span><span class="sxs-lookup"><span data-stu-id="caa28-209">Automated investigation and response capabilities are available in **Office 365 ATP Plan 2** and **Office 365 E5**.</span></span>

<span data-ttu-id="caa28-210">(新!)[自動化調查和回應](automated-investigation-response-office.md)可將您的安全性作業小組儲存在調查和降低網路攻擊的時間和精力。</span><span class="sxs-lookup"><span data-stu-id="caa28-210">(NEW!) [Automated investigation and response](automated-investigation-response-office.md) can save your security operations team much time and effort in investigating and mitigating cyber attacks.</span></span> <span data-ttu-id="caa28-211">除了設定可觸發安全性行動手冊的警示之外, 您還可以從瀏覽器中的視圖開始自動調查和回應程式。</span><span class="sxs-lookup"><span data-stu-id="caa28-211">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span> 

<span data-ttu-id="caa28-212">如需這種情況的詳細資訊, 請參閱[範例: 安全性系統管理員會觸發從瀏覽器進行的調查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="caa28-212">For details on this, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="more-ways-to-use-explorer-or-real-time-detections"></a><span data-ttu-id="caa28-213">更多使用瀏覽器的方法 (或即時偵測)</span><span class="sxs-lookup"><span data-stu-id="caa28-213">More ways to use Explorer (or real-time detections)</span></span>

<span data-ttu-id="caa28-214">除了本文所述的案例之外, 您還可以使用瀏覽器 (或即時偵測) 提供的更多報告選項。</span><span class="sxs-lookup"><span data-stu-id="caa28-214">In addition to the scenarios outlined in this article, you have many more reporting options available with Explorer (or real-time detections).</span></span> 
- [<span data-ttu-id="caa28-215">尋找並調查傳送的惡意電子郵件</span><span class="sxs-lookup"><span data-stu-id="caa28-215">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="caa28-216">查看 SharePoint Online、OneDrive 和 Microsoft 團隊中偵測到的惡意檔案</span><span class="sxs-lookup"><span data-stu-id="caa28-216">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
- [<span data-ttu-id="caa28-217">取得威脅瀏覽器中的視圖 (和即時偵測) 的總覽</span><span class="sxs-lookup"><span data-stu-id="caa28-217">Get an overview of the views in Threat Explorer (and real-time detections)</span></span>](threat-explorer-views.md)

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="caa28-218">必要的授權和許可權</span><span class="sxs-lookup"><span data-stu-id="caa28-218">Required licenses and permissions</span></span>

<span data-ttu-id="caa28-219">您必須擁有[Office 365 ATP](office-365-atp.md) , 才能取得 Explorer 或即時偵測。</span><span class="sxs-lookup"><span data-stu-id="caa28-219">You must have [Office 365 ATP](office-365-atp.md) to get Explorer or real-time detections.</span></span>
- <span data-ttu-id="caa28-220">Explorer 包含在 Office 365 ATP 方案2中。</span><span class="sxs-lookup"><span data-stu-id="caa28-220">Explorer is included in Office 365 ATP Plan 2.</span></span> 
- <span data-ttu-id="caa28-221">即時偵測報告包含在 Office 365 ATP 方案1中。</span><span class="sxs-lookup"><span data-stu-id="caa28-221">The real-time detections report is included in Office 365 ATP Plan 1.</span></span>
- <span data-ttu-id="caa28-222">規劃為應由 ATP 保護的所有使用者指派授權。</span><span class="sxs-lookup"><span data-stu-id="caa28-222">Plan to assign licenses for all users who should be protected by ATP.</span></span> <span data-ttu-id="caa28-223">(Explorer 或即時偵測會顯示已授權使用者的偵測資料。)</span><span class="sxs-lookup"><span data-stu-id="caa28-223">(Explorer or real-time detections will show detection data for licensed users.)</span></span>

<span data-ttu-id="caa28-224">若要查看和使用瀏覽器或即時偵測, 您必須具有適當的許可權, 例如授與安全性系統管理員或安全性讀取者的許可權。</span><span class="sxs-lookup"><span data-stu-id="caa28-224">To view and use Explorer or real-time detections, you must have appropriate permissions, such as those granted to a security administrator or security reader.</span></span> 

- <span data-ttu-id="caa28-225">針對安全性&amp;合規性中心, 您必須已指派下列其中一個角色:</span><span class="sxs-lookup"><span data-stu-id="caa28-225">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="caa28-226">組織管理</span><span class="sxs-lookup"><span data-stu-id="caa28-226">Organization Management</span></span>
    - <span data-ttu-id="caa28-227">安全性系統管理員 (可在 Azure Active Directory 系統管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com)) 中指派)</span><span class="sxs-lookup"><span data-stu-id="caa28-227">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
    - <span data-ttu-id="caa28-228">安全性讀取器</span><span class="sxs-lookup"><span data-stu-id="caa28-228">Security Reader</span></span>

- <span data-ttu-id="caa28-229">若為 Exchange Online, 您必須在 Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) 或 PowerShell Cmdlet 中指派下列其中一個角色 (請參閱[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span><span class="sxs-lookup"><span data-stu-id="caa28-229">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span></span>
    - <span data-ttu-id="caa28-230">組織管理</span><span class="sxs-lookup"><span data-stu-id="caa28-230">Organization Management</span></span>
    - <span data-ttu-id="caa28-231">僅檢視組織管理</span><span class="sxs-lookup"><span data-stu-id="caa28-231">View-only Organization Management</span></span>
    - <span data-ttu-id="caa28-232">僅檢視收件者角色</span><span class="sxs-lookup"><span data-stu-id="caa28-232">View-Only Recipients role</span></span>
    - <span data-ttu-id="caa28-233">合規性管理</span><span class="sxs-lookup"><span data-stu-id="caa28-233">Compliance Management</span></span>

<span data-ttu-id="caa28-234">若要深入瞭解角色和許可權, 請參閱下列資源:</span><span class="sxs-lookup"><span data-stu-id="caa28-234">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="caa28-235">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="caa28-235">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="caa28-236">Exchange Online 中的功能權限</span><span class="sxs-lookup"><span data-stu-id="caa28-236">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
  
