---
title: 尋找並調查已傳遞 Office 365 中的惡意電子郵件
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 08/07/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection:
- M365-security-compliance
description: 了解如何使用威脅調查及回應功能來尋找並調查惡意電子郵件。
ms.openlocfilehash: 1f558614d77577408a824b3c6181aae22753ab0f
ms.sourcegitcommit: 7a0cb7e1da39fc485fc29e7325b843d16b9808af
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36230557"
---
# <a name="find-and-investigate-malicious-email-that-was-delivered-in-office-365"></a><span data-ttu-id="3c79f-103">尋找並調查已傳遞 Office 365 中的惡意電子郵件</span><span class="sxs-lookup"><span data-stu-id="3c79f-103">Find and investigate malicious email that was delivered in Office 365</span></span>

<span data-ttu-id="3c79f-104">[Office 365 進階威脅防護](office-365-atp.md)可讓您調查，將您的使用者放在風險，並採取動作來保護您的組織活動。</span><span class="sxs-lookup"><span data-stu-id="3c79f-104">[Office 365 Advanced Threat Protection](office-365-atp.md) enables you to investigate activities that put your users at risk and take action to protect your organization.</span></span> <span data-ttu-id="3c79f-105">例如，如果您是貴組織的安全性小組的一部分，您可以尋找和調查可疑的電子郵件已傳遞至您的使用者。</span><span class="sxs-lookup"><span data-stu-id="3c79f-105">For example, if you are part of your organization's security team, you can find and investigate suspicious email messages that were delivered to your users.</span></span> <span data-ttu-id="3c79f-106">您可以使用[威脅總管 （或即時偵測的資訊）](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="3c79f-106">You can do this by using [Threat Explorer (or real-time detections)](threat-explorer.md).</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="3c79f-107">開始之前...]</span><span class="sxs-lookup"><span data-stu-id="3c79f-107">Before you begin...</span></span>

<span data-ttu-id="3c79f-108">請確定符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="3c79f-108">Make sure that the following requirements are met:</span></span>
  
- <span data-ttu-id="3c79f-109">您的組織有[Office 365 進階威脅防護](office-365-atp.md)，並[將授權指派給使用者](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="3c79f-109">Your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) and [licenses are assigned to users](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users).</span></span>
    
- <span data-ttu-id="3c79f-110">[Office 365 稽核記錄](turn-audit-log-search-on-or-off.md)已為您的組織。</span><span class="sxs-lookup"><span data-stu-id="3c79f-110">[Office 365 audit logging](turn-audit-log-search-on-or-off.md) is turned on for your organization.</span></span> 
    
- <span data-ttu-id="3c79f-111">貴組織的原則定義的反垃圾郵件、 反惡意程式碼、 反網路釣魚，依此類推。</span><span class="sxs-lookup"><span data-stu-id="3c79f-111">Your organization has policies defined for anti-spam, anti-malware, anti-phishing, and so on.</span></span> <span data-ttu-id="3c79f-112">請參閱[針對 Office 365 中的威脅保護](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="3c79f-112">See [Protect against threats in Office 365](protect-against-threats.md).</span></span>
    
- <span data-ttu-id="3c79f-113">您是 Office 365 全域管理員，或具有安全性系統管理員或 「 搜尋及清除角色指派安全性&amp;合規性中心。</span><span class="sxs-lookup"><span data-stu-id="3c79f-113">You are an Office 365 global administrator, or you have either the Security Administrator or the Search and Purge role assigned in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="3c79f-114">請參閱[中的 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="3c79f-114">See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    
## <a name="dealing-with-suspicious-emails"></a><span data-ttu-id="3c79f-115">處理可疑的電子郵件</span><span class="sxs-lookup"><span data-stu-id="3c79f-115">Dealing with suspicious emails</span></span>

<span data-ttu-id="3c79f-116">惡意攻擊者可能會將郵件傳送至您的使用者嘗試與釣魚程式其認證，並存取您公司的機密資料 ！</span><span class="sxs-lookup"><span data-stu-id="3c79f-116">Malicious attackers may be sending mail to your users to try and phish their credentials and gain access to your corporate secrets!</span></span> <span data-ttu-id="3c79f-117">若要避免這種情況，您應該使用在 Office 365 中，包括[Exchange Online Protection](eop/exchange-online-protection-overview.md)和[進階威脅防護](office-365-atp.md)的威脅保護服務。</span><span class="sxs-lookup"><span data-stu-id="3c79f-117">To prevent this, you should use the threat protection services in Office 365, including [Exchange Online Protection](eop/exchange-online-protection-overview.md) and [Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="3c79f-118">不過，有的時間攻擊者時將郵件傳送給使用者的 url 然後僅更新版本上將該 URL 點對惡意內容 （惡意程式碼等）。</span><span class="sxs-lookup"><span data-stu-id="3c79f-118">However, there are times when an attacker could send mail to your users containing a URL and only later on make that URL point to malicious content (malware, etc.).</span></span> <span data-ttu-id="3c79f-119">或者，您可能會發現太晚而遭入侵您組織中的使用者，以及攻擊時遭到盜用了該使用者，使用該帳戶傳送電子郵件給您公司中的其他使用者。</span><span class="sxs-lookup"><span data-stu-id="3c79f-119">Alternately, you may realize too late that a user in your organization has been compromised, and while that user was compromised, an attacker used that account to send email to other users in your company.</span></span> <span data-ttu-id="3c79f-120">一部分 < cleaning up 這兩種情況，您可能想要移除使用者收件匣的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="3c79f-120">As part of cleaning up both of these scenarios, you may want to remove email messages from user inboxes.</span></span> <span data-ttu-id="3c79f-121">在這類的情況下，您可以利用[威脅總管 （或即時偵測）](threat-explorer.md)來尋找和移除這些電子郵件訊息 ！</span><span class="sxs-lookup"><span data-stu-id="3c79f-121">In situations like these, you can leverage [Threat Explorer (or real-time detections)](threat-explorer.md) to find and remove those email messages!</span></span>

## <a name="where-re-routed-emails-are-located-after-actions-are-taken"></a><span data-ttu-id="3c79f-122">重新路由傳送的電子郵件的所在位置後採取的動作</span><span class="sxs-lookup"><span data-stu-id="3c79f-122">Where re-routed emails are located after actions are taken</span></span>

<span data-ttu-id="3c79f-123">威脅總管即時偵測已新增取代傳遞狀態的傳遞巨集指令並傳遞位置欄位。</span><span class="sxs-lookup"><span data-stu-id="3c79f-123">Threat Explorer real-time detections has added the Delivery Action and Delivery Location fields in the place of Delivery Status.</span></span> <span data-ttu-id="3c79f-124">這會導致您的電子郵件的登陸其中的更完整圖片。</span><span class="sxs-lookup"><span data-stu-id="3c79f-124">This results in a more complete picture of where your emails land.</span></span> <span data-ttu-id="3c79f-125">這項變更的目標的一部分是狩獵更輕鬆地進行安全性 Ops 的人員，但最終結果知道一眼問題電子郵件的位置。</span><span class="sxs-lookup"><span data-stu-id="3c79f-125">Part of the goal of this change is to make hunting easier for Security Ops people, but the net result is knowing the location of problem emails at a glance.</span></span>

<span data-ttu-id="3c79f-126">傳遞狀態現在劃分為兩個資料行：</span><span class="sxs-lookup"><span data-stu-id="3c79f-126">Delivery Status is now broken out into two columns:</span></span>

- <span data-ttu-id="3c79f-127">**傳遞動作**-這封電子郵件的狀態為何？</span><span class="sxs-lookup"><span data-stu-id="3c79f-127">**Delivery action** - What is the status of this email?</span></span>
- <span data-ttu-id="3c79f-128">**傳遞位置**-其中這封電子郵件路由傳送結果？</span><span class="sxs-lookup"><span data-stu-id="3c79f-128">**Delivery location** - Where was this email routed as a result?</span></span>

<span data-ttu-id="3c79f-129">傳遞動作是因為現有的原則或偵測電子郵件所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="3c79f-129">Delivery action is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="3c79f-130">以下是可能一封電子郵件可以採取的動作：</span><span class="sxs-lookup"><span data-stu-id="3c79f-130">Here are the possible actions an email can take:</span></span>

- <span data-ttu-id="3c79f-131">**已傳遞**– 電子郵件已傳遞至收件匣或資料夾的使用者和該使用者可以直接存取。</span><span class="sxs-lookup"><span data-stu-id="3c79f-131">**Delivered** – email was delivered to inbox or folder of a user and the user can directly access it.</span></span>
- <span data-ttu-id="3c79f-132">**Junked** – 電子郵件已傳送至任一使用者的垃圾郵件] 資料夾，或刪除資料夾，且使用者在其 [垃圾郵件或刪除的郵件] 資料夾中具有存取電子郵件。</span><span class="sxs-lookup"><span data-stu-id="3c79f-132">**Junked** – email was sent to either user’s junk folder or deleted folder, and the user has access to emails in their Junk or Deleted folder.</span></span>
- <span data-ttu-id="3c79f-133">**封鎖**– 任何電子郵件，會受到隔離，失敗，或已卸除。</span><span class="sxs-lookup"><span data-stu-id="3c79f-133">**Blocked** – any emails that's quarantined, that  failed, or was dropped.</span></span> <span data-ttu-id="3c79f-134">這是完全無法存取之使用者所 ！</span><span class="sxs-lookup"><span data-stu-id="3c79f-134">This is completely inaccessible by the user!</span></span>
- <span data-ttu-id="3c79f-135">**取代**– 惡意附件由 state 附件的.txt 檔案所取代其中任何電子郵件程式惡意。</span><span class="sxs-lookup"><span data-stu-id="3c79f-135">**Replaced** – any email where malicious attachments are replaced by .txt files that state the attachment was malicious.</span></span>
 
<span data-ttu-id="3c79f-136">傳遞位置顯示原則，以及執行後續傳遞的偵測的結果。</span><span class="sxs-lookup"><span data-stu-id="3c79f-136">Delivery location shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="3c79f-137">它會連結到傳遞巨集指令。</span><span class="sxs-lookup"><span data-stu-id="3c79f-137">It's linked to a Delivery Action.</span></span> <span data-ttu-id="3c79f-138">此欄位已新增至提供深入時找到問題郵件採取的動作。</span><span class="sxs-lookup"><span data-stu-id="3c79f-138">This field was added to give insight into the action taken when a problem mail is found.</span></span> <span data-ttu-id="3c79f-139">以下是傳遞位置的可能值：</span><span class="sxs-lookup"><span data-stu-id="3c79f-139">Here are the possible values of delivery location:</span></span>

- <span data-ttu-id="3c79f-140">**收件匣或資料夾**– 電子郵件是在收件匣或資料夾中 （根據您的電子郵件的規則）。</span><span class="sxs-lookup"><span data-stu-id="3c79f-140">**Inbox or folder** – The email is in inbox or a folder (according to your email rules).</span></span>
- <span data-ttu-id="3c79f-141">**在內部或外部**– 信箱不存在於雲端上，但在-內部部署。</span><span class="sxs-lookup"><span data-stu-id="3c79f-141">**On-prem or external** – The mailbox doesn’t exist on cloud but is on -premises.</span></span>
- <span data-ttu-id="3c79f-142">**垃圾郵件資料夾**– 中之使用者的 [垃圾郵件] 資料夾中的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="3c79f-142">**Junk folder** – The email in in the Junk folder of a user.</span></span>
- <span data-ttu-id="3c79f-143">**刪除的項目] 資料夾**– 之使用者的已刪除項目] 資料夾中的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="3c79f-143">**Deleted items folder** – The email in the Deleted items folder of a user.</span></span>
- <span data-ttu-id="3c79f-144">**隔離**-隔離中的電子郵件以及不在使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="3c79f-144">**Quarantine** – The email in quarantine, and is not in a user’s mailbox.</span></span>
- <span data-ttu-id="3c79f-145">**失敗**– 電子郵件無法連到信箱。</span><span class="sxs-lookup"><span data-stu-id="3c79f-145">**Failed** – The email failed to reach the mailbox.</span></span>
- <span data-ttu-id="3c79f-146">**丟棄**– 電子郵件會取得某處遺失，在 [郵件流程。</span><span class="sxs-lookup"><span data-stu-id="3c79f-146">**Dropped** – The email gets lost somewhere in the Mailflow.</span></span>
  
## <a name="find-and-delete-suspicious-email-that-was-delivered"></a><span data-ttu-id="3c79f-147">尋找並刪除可疑的電子郵件的郵件傳遞</span><span class="sxs-lookup"><span data-stu-id="3c79f-147">Find and delete suspicious email that was delivered</span></span>

> [!TIP]
> <span data-ttu-id="3c79f-148">威脅總管 （有時稱為總管），是功能強大的報表，可以有多個用途，例如尋找及刪除的郵件，用來識別惡意電子郵件寄件者的 IP 位址或開始進一步調查的事件。</span><span class="sxs-lookup"><span data-stu-id="3c79f-148">Threat Explorer (sometimes called Explorer), is a powerful report that can serve multiple purposes, such as finding and deleting messages, identifying the IP address of a malicious email sender, or starting an incident for further investigation.</span></span> <span data-ttu-id="3c79f-149">下列程序著重於使用 Explorer 來尋找並從收件者信箱刪除惡意電子郵件。</span><span class="sxs-lookup"><span data-stu-id="3c79f-149">The following procedure focuses on using Explorer to find and delete malicious email from recipients mailboxes.</span></span>

<span data-ttu-id="3c79f-150">若要查看變更先前的傳遞狀態欄位 （現在傳遞巨集指令與傳遞位置）：</span><span class="sxs-lookup"><span data-stu-id="3c79f-150">To see the changes to the former Delivery Status field (now Delivery Action and Delivery Location):</span></span> 

1. <span data-ttu-id="3c79f-151">移至 [[https://protection.office.com](https://protection.office.com)和 Office 365 使用公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="3c79f-151">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365.</span></span> <span data-ttu-id="3c79f-152">這會帶您前往安全性&amp;合規性中心。</span><span class="sxs-lookup"><span data-stu-id="3c79f-152">This takes you to the Security &amp; Compliance Center.</span></span> 
    
2. <span data-ttu-id="3c79f-153">在左側導覽中，選擇 [**威脅管理，** \> **總管**。</span><span class="sxs-lookup"><span data-stu-id="3c79f-153">In the left navigation, choose **Threat management** \> **Explorer**.</span></span>


![威脅總管] 的傳遞巨集指令與傳遞位置欄位。](media/ThreatExFields.PNG)

<span data-ttu-id="3c79f-155">您可能會發現此圖形中新的 ['特殊動作'] 欄。</span><span class="sxs-lookup"><span data-stu-id="3c79f-155">You may notice the new 'Special actions' column in this graphic.</span></span> <span data-ttu-id="3c79f-156">這項功能的目標是告訴系統管理員處理電子郵件的結果。</span><span class="sxs-lookup"><span data-stu-id="3c79f-156">This feature is aimed at telling admins the outcome of processing an email.</span></span> <span data-ttu-id="3c79f-157">特殊動作可能會更新威脅總管] 中的*電子郵件時間表*，這是針對在系統管理員更妥善地進行狩獵體驗新功能的結尾。</span><span class="sxs-lookup"><span data-stu-id="3c79f-157">Special actions may be updated at the end of Threat Explorer's *email timeline*, which is a new feature aimed at making the hunting experience better for admins.</span></span>

<span data-ttu-id="3c79f-158">電子郵件時間表剪下向下上隨機化因為較少的時間所花費的嘗試了解事件發生於由於電子郵件抵達檢查不同的位置。</span><span class="sxs-lookup"><span data-stu-id="3c79f-158">Email timeline cuts down on randomization because there is less time spent checking different locations to try to understand events that happened since the email arrived.</span></span> <span data-ttu-id="3c79f-159">當多個事件會發生，在或接近，同時在一封電子郵件時，這些事件會顯示在 [時間表] 檢視中。</span><span class="sxs-lookup"><span data-stu-id="3c79f-159">When multiple events happen at, or close to, the same time on an email, those events will show up in a timeline view.</span></span> <span data-ttu-id="3c79f-160">某些後續傳遞至您的郵件，即會發生的事件將會擷取 '特殊動作] 欄中。</span><span class="sxs-lookup"><span data-stu-id="3c79f-160">Some events that happen post-delivery to your mail will be captured in the 'Special actions' column.</span></span> <span data-ttu-id="3c79f-161">在後續傳遞郵件所採取的*特殊動作*與組合在一起，郵件從*時間表的電子郵件*的資訊會提供系統管理員深入解析到其原則的運作方式，其中最後已路由傳送郵件，並在某些情況下，哪些最後一評估為。</span><span class="sxs-lookup"><span data-stu-id="3c79f-161">Combining the information from the *email timeline* of that mail with the *Special actions* taken on the mail post-delivery will give admins insight into how their policies work, where the mail was finally routed, and, in some cases, what the final assessment was.</span></span> <span data-ttu-id="3c79f-162">特殊動作] 欄可以在中傳遞巨集指令並傳遞位置，但若要查看電子郵件時間表的相同位置存取：</span><span class="sxs-lookup"><span data-stu-id="3c79f-162">The Special actions column can be accessed in the same place as Delivery action and Delivery location, but to see an email timeline:</span></span>

1. <span data-ttu-id="3c79f-163">按一下電子郵件的主旨。</span><span class="sxs-lookup"><span data-stu-id="3c79f-163">Click on the subject of the email.</span></span>
2. <span data-ttu-id="3c79f-164">在出現面板中，按一下 [*電子郵件時間表*。</span><span class="sxs-lookup"><span data-stu-id="3c79f-164">On the panel that appears, click *Email timeline*.</span></span> <span data-ttu-id="3c79f-165">(將出現在像是 '摘要' 或 '詳述'] 面板上的其他標題之間 et cetera。)</span><span class="sxs-lookup"><span data-stu-id="3c79f-165">(It will appear among other headings on the panel like 'Summary' or 'Details', et cetera.)</span></span>

<span data-ttu-id="3c79f-166">一旦您開啟電子郵件時間表，您應該會看到會告訴您在該郵件的後續傳遞事件的資料表或在電子郵件沒有進一步事件，您應該會看到將狀態的結果，例如*封鎖*的原始傳遞的單一事件使用*釣魚程式*類似的結論。</span><span class="sxs-lookup"><span data-stu-id="3c79f-166">Once you've opened the email timeline, you should see a table that tells you the post-delivery events for that mail, or, in the case of no further events for the email, you should see a single event for the original delivery that will state a result like *Blocked* with a verdict like *Phish*.</span></span> <span data-ttu-id="3c79f-167">] 索引標籤也會有 [匯出完整的電子郵件時間表，] 選項，這會匯出] 索引標籤上的所有詳細資料和電子郵件 （像是主旨、 寄件者、 收件者、 網路和訊息識別碼） 的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="3c79f-167">The tab also has the option to export the entire email timeline, and this will export all the details on the tab and details on the email (things like Subject, Sender, Recipient, Network, and Message ID).</span></span>

3. <span data-ttu-id="3c79f-168">在 [檢視] 功能表中，選擇 [**所有電子郵件**。</span><span class="sxs-lookup"><span data-stu-id="3c79f-168">In the View menu, choose **All email**.</span></span><br/><span data-ttu-id="3c79f-169">![使用 [檢視] 功能表的電子郵件和內容的報告之間選擇](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)</span><span class="sxs-lookup"><span data-stu-id="3c79f-169">![Use the View menu to choose between Email and Content reports](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)</span></span>
  
4. <span data-ttu-id="3c79f-170">請注意報表，例如**已傳遞**、**未知**，或**傳遞至垃圾郵件**中顯示的標籤。</span><span class="sxs-lookup"><span data-stu-id="3c79f-170">Notice the labels that appear in the report, such as **Delivered**, **Unknown**, or **Delivered to junk**.</span></span><br/><span data-ttu-id="3c79f-171">![顯示所有的電子郵件資料的威脅總管](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)</span><span class="sxs-lookup"><span data-stu-id="3c79f-171">![Threat Explorer showing data for all email](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)</span></span><br/><span data-ttu-id="3c79f-172">（根據對貴組織的電子郵件所採取的動作，您可能會看到其他標籤，例如**封鎖**或**取代**）。</span><span class="sxs-lookup"><span data-stu-id="3c79f-172">(Depending on the actions that were taken on email messages for your organization, you might see additional labels, such as **Blocked** or **Replaced**.)</span></span>
    
5. <span data-ttu-id="3c79f-173">在報告中，選擇 [**已傳遞**的以檢視僅最後出現在使用者的收件匣的電子郵件]。</span><span class="sxs-lookup"><span data-stu-id="3c79f-173">In the report, choose **Delivered** to view only emails that ended up in users' inboxes.</span></span><br/><span data-ttu-id="3c79f-174">![按一下 「 傳遞至垃圾郵件 」 從檢視中移除該資料](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)</span><span class="sxs-lookup"><span data-stu-id="3c79f-174">![Clicking "Delivered to junk" removes that data from view](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)</span></span>
  
6. <span data-ttu-id="3c79f-175">下方圖表中，檢閱圖表下方的**電子郵件**清單。</span><span class="sxs-lookup"><span data-stu-id="3c79f-175">Below the chart, review the **Email** list below the chart.</span></span><br/><span data-ttu-id="3c79f-176">![下方圖表中，檢視已偵測到的電子郵件的清單](media/dfb60590-1236-499d-97da-86c68621e2bc.png)</span><span class="sxs-lookup"><span data-stu-id="3c79f-176">![Below the chart, view a list of email messages that were detected](media/dfb60590-1236-499d-97da-86c68621e2bc.png)</span></span>
  
7. <span data-ttu-id="3c79f-177">在清單中，選擇 [項目來檢視電子郵件訊息的相關詳細資料]。</span><span class="sxs-lookup"><span data-stu-id="3c79f-177">In the list, choose an item to view more details about that email message.</span></span> <span data-ttu-id="3c79f-178">例如，您可以按一下 [檢視資訊寄件者、 收件者、 附件及其他類似的電子郵件的主旨行。</span><span class="sxs-lookup"><span data-stu-id="3c79f-178">For example, you can click the subject line to view information about the sender, recipients, attachments, and other similar email messages.</span></span><br/>![您可以檢視項目，包括詳細資料和任何附件相關的其他資訊](media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
8. <span data-ttu-id="3c79f-180">之後檢視電子郵件的相關資訊，請啟動 **+ 動作**清單中選取一或多個項目。</span><span class="sxs-lookup"><span data-stu-id="3c79f-180">After viewing information about email messages, select one or more items in the list to activate **+ Actions**.</span></span>
    
9. <span data-ttu-id="3c79f-181">使用 **+ 動作**清單將套用的動作，例如**將移至刪除**的項目。</span><span class="sxs-lookup"><span data-stu-id="3c79f-181">Use the **+ Actions** list to apply an action, such as **Move to deleted** items.</span></span> <span data-ttu-id="3c79f-182">這會從收件者的信箱刪除選取的郵件。</span><span class="sxs-lookup"><span data-stu-id="3c79f-182">This will delete the selected messages from the recipients' mailboxes.</span></span><br/><span data-ttu-id="3c79f-183">![當您選取一或多個電子郵件時，您可以選擇從數個可用的動作](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)</span><span class="sxs-lookup"><span data-stu-id="3c79f-183">![When you select one or more email messages, you can choose from several available actions](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="3c79f-184">相關主題</span><span class="sxs-lookup"><span data-stu-id="3c79f-184">Related topics</span></span>

[<span data-ttu-id="3c79f-185">Office 365 進階的威脅保護計劃 2</span><span class="sxs-lookup"><span data-stu-id="3c79f-185">Office 365 Advanced Threat Protection Plan 2</span></span>](office-365-ti.md)
  
[<span data-ttu-id="3c79f-186">防範 Office 365 中的威脅</span><span class="sxs-lookup"><span data-stu-id="3c79f-186">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="3c79f-187">檢視 Office 365 進階威脅防護報告</span><span class="sxs-lookup"><span data-stu-id="3c79f-187">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  

