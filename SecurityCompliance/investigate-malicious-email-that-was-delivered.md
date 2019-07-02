---
title: 尋找並調查已傳遞的惡意電子郵件 (Office 365 威脅調查和回應
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/19/2019
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
description: 瞭解如何使用威脅調查和回應功能來尋找並調查惡意電子郵件。
ms.openlocfilehash: febcf6704b1ba9dc23bf4e698715fb4b929b998b
ms.sourcegitcommit: d3b2bffa8af5f19d97fe9771068c80705b890e85
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/01/2019
ms.locfileid: "35414803"
---
# <a name="find-and-investigate-malicious-email-that-was-delivered-office-365-advanced-threat-protection-plan-2"></a><span data-ttu-id="ff80a-103">尋找並調查已傳遞的惡意電子郵件 (Office 365 高級威脅防護方案 2)</span><span class="sxs-lookup"><span data-stu-id="ff80a-103">Find and investigate malicious email that was delivered (Office 365 Advanced Threat Protection Plan 2)</span></span>

<span data-ttu-id="ff80a-104">[Office 365 高級威脅防護](office-365-atp.md)可讓您調查讓使用者面臨風險的活動, 並採取行動以保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="ff80a-104">[Office 365 Advanced Threat Protection](office-365-atp.md) lets you to investigate activities that put your users at risk and take action to protect your organization.</span></span> <span data-ttu-id="ff80a-105">例如, 如果您是組織的安全小組的一部分, 您可以尋找並調查已傳遞給使用者的可疑電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="ff80a-105">For example, if you are part of your organization's security team, you can find and investigate suspicious email messages that were delivered to your users.</span></span> <span data-ttu-id="ff80a-106">您可以使用[威脅瀏覽器 (或即時偵測)](threat-explorer.md)來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="ff80a-106">You can do this by using [Threat Explorer (or real-time detections)](threat-explorer.md).</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="ff80a-107">開始之前 .。。</span><span class="sxs-lookup"><span data-stu-id="ff80a-107">Before you begin...</span></span>

<span data-ttu-id="ff80a-108">請確定符合下列需求:</span><span class="sxs-lookup"><span data-stu-id="ff80a-108">Make sure that the following requirements are met:</span></span>
  
- <span data-ttu-id="ff80a-109">您的組織有[Office 365 Advanced 威脅防護](office-365-atp.md)(plan 1 或 plan 2) 和[授權已指派給使用者](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="ff80a-109">Your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (Plan 1 or Plan 2) and [licenses are assigned to users](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users).</span></span>
    
- <span data-ttu-id="ff80a-110">您的組織已開啟[Office 365 的 audit 記錄](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="ff80a-110">[Office 365 audit logging](turn-audit-log-search-on-or-off.md) is turned on for your organization.</span></span> 
    
- <span data-ttu-id="ff80a-111">您的組織有針對反垃圾郵件、反惡意程式碼、反網路釣魚等所定義的原則。</span><span class="sxs-lookup"><span data-stu-id="ff80a-111">Your organization has policies defined for anti-spam, anti-malware, anti-phishing, and so on.</span></span> <span data-ttu-id="ff80a-112">請參閱[防範 Office 365 中的威脅](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="ff80a-112">See [Protect against threats in Office 365](protect-against-threats.md).</span></span>
    
- <span data-ttu-id="ff80a-113">您是 Office 365 全域系統管理員, 或您擁有安全性系統管理員或在安全性&amp;與合規性中心中指派的搜尋和清除角色。</span><span class="sxs-lookup"><span data-stu-id="ff80a-113">You are an Office 365 global administrator, or you have either the Security Administrator or the Search and Purge role assigned in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="ff80a-114">請參閱[Office 365 安全性&amp;與合規性中心的許可權](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="ff80a-114">See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    
## <a name="dealing-with-suspicious-emails"></a><span data-ttu-id="ff80a-115">處理可疑的電子郵件</span><span class="sxs-lookup"><span data-stu-id="ff80a-115">Dealing with suspicious emails</span></span>

<span data-ttu-id="ff80a-116">惡意攻擊者可能會將郵件傳送給您的使用者, 以嘗試和詐騙其認證, 並取得公司機密的存取權!</span><span class="sxs-lookup"><span data-stu-id="ff80a-116">Malicious attackers may be sending mail to your users to try and phish their credentials and gain access to your corporate secrets!</span></span> <span data-ttu-id="ff80a-117">若要避免這種情況, 您應該使用 Office 365 中的威脅防護服務, 包括[Exchange Online protection](eop/exchange-online-protection-overview.md)和[高級威脅防護](office-365-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="ff80a-117">To prevent this, you should use the threat protection services in Office 365, including [Exchange Online Protection](eop/exchange-online-protection-overview.md) and [Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="ff80a-118">不過, 在某些情況下, 攻擊者可以傳送郵件給您的使用者包含 URL, 而只是稍後再讓該 URL 指向惡意內容 (惡意程式碼等等)。</span><span class="sxs-lookup"><span data-stu-id="ff80a-118">However, there are times when an attacker could send mail to your users containing a URL and only later on make that URL point to malicious content (malware, etc.).</span></span> <span data-ttu-id="ff80a-119">或者, 您可能會發現組織中的使用者已遭到破壞, 而且該使用者遭到破壞時, 攻擊者會使用該帳戶, 將電子郵件傳送給公司中的其他使用者。</span><span class="sxs-lookup"><span data-stu-id="ff80a-119">Alternately, you may realize too late that a user in your organization has been compromised, and while that user was compromised, an attacker used that account to send email to other users in your company.</span></span> <span data-ttu-id="ff80a-120">在這兩種情況下, 您可能會想要移除使用者收件匣中的電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="ff80a-120">As part of cleaning up both of these scenarios, you may want to remove email messages from user inboxes.</span></span> <span data-ttu-id="ff80a-121">在這類情況下, 您可以利用[威脅瀏覽器 (或即時偵測)](threat-explorer.md)來尋找並移除這些電子郵件!</span><span class="sxs-lookup"><span data-stu-id="ff80a-121">In situations like these, you can leverage [Threat Explorer (or real-time detections)](threat-explorer.md) to find and remove those email messages!</span></span>

## <a name="where-re-routed-emails-are-located-after-actions-are-taken"></a><span data-ttu-id="ff80a-122">在採取動作後, 重新路由傳送電子郵件的位置</span><span class="sxs-lookup"><span data-stu-id="ff80a-122">Where re-routed emails are located after actions are taken</span></span>

<span data-ttu-id="ff80a-123">威脅 Explorer 即時偵測已新增 [傳遞動作] 和 [傳遞位置] 欄位的 [傳遞] 狀態。</span><span class="sxs-lookup"><span data-stu-id="ff80a-123">Threat Explorer real-time detections has added the Delivery Action and Delivery Location fields in the place of Delivery Status.</span></span> <span data-ttu-id="ff80a-124">這會使您在電子郵件中的位置產生更完整的圖片。</span><span class="sxs-lookup"><span data-stu-id="ff80a-124">This results in a more complete picture of where your emails land.</span></span> <span data-ttu-id="ff80a-125">此變更的其中一部分是讓搜尋更容易進行安全性操作人員, 但是 net 結果是一眼就知道問題電子郵件的位置。</span><span class="sxs-lookup"><span data-stu-id="ff80a-125">Part of the goal of this change is to make hunting easier for Security Ops people, but the net result is knowing the location of problem emails at a glance.</span></span>

<span data-ttu-id="ff80a-126">傳遞狀態現在會分成兩欄:</span><span class="sxs-lookup"><span data-stu-id="ff80a-126">Delivery Status is now broken out into two columns:</span></span>

- <span data-ttu-id="ff80a-127">**傳遞動作**-此電子郵件的狀態為何？</span><span class="sxs-lookup"><span data-stu-id="ff80a-127">**Delivery Action** - What is the status of this email?</span></span>
- <span data-ttu-id="ff80a-128">**傳遞位置**-這封電子郵件會做為結果的路由？</span><span class="sxs-lookup"><span data-stu-id="ff80a-128">**Delivery Location** - Where was this email routed as a result?</span></span>

<span data-ttu-id="ff80a-129">傳遞動作是由於現有的原則或偵測而對電子郵件採取的動作。</span><span class="sxs-lookup"><span data-stu-id="ff80a-129">Delivery Action is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="ff80a-130">以下是電子郵件可能採取的動作:</span><span class="sxs-lookup"><span data-stu-id="ff80a-130">Here are the possible actions an email can take:</span></span>

1. <span data-ttu-id="ff80a-131">**傳遞**–電子郵件已傳遞至使用者的收件匣或資料夾, 而且使用者可以直接存取它。</span><span class="sxs-lookup"><span data-stu-id="ff80a-131">**Delivered** – email was delivered to inbox or folder of a user and the user can directly access it.</span></span>
2. <span data-ttu-id="ff80a-132">**Junked** –電子郵件會傳送至使用者的 [垃圾郵件] 資料夾或 [已刪除的資料夾], 而且使用者可以存取其垃圾郵件或已刪除的資料夾中的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="ff80a-132">**Junked** – email was sent to either user’s junk folder or deleted folder, and the user has access to emails in their Junk or Deleted folder.</span></span>
3. <span data-ttu-id="ff80a-133">**封鎖**–隔離、失敗或已捨棄的任何電子郵件。</span><span class="sxs-lookup"><span data-stu-id="ff80a-133">**Blocked** – any emails that's quarantined, that  failed, or was dropped.</span></span> <span data-ttu-id="ff80a-134">使用者完全無法存取此功能!</span><span class="sxs-lookup"><span data-stu-id="ff80a-134">This is completely inaccessible by the user!</span></span>
4. <span data-ttu-id="ff80a-135">**已更換**–任何惡意附件都由 .txt 檔案取代, 以指出附件是惡意的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="ff80a-135">**Replaced** – any email where malicious attachments are replaced by .txt files that state the attachment was malicious.</span></span>
 
<span data-ttu-id="ff80a-136">[傳遞位置] 顯示執行傳遞後的原則和偵測結果。</span><span class="sxs-lookup"><span data-stu-id="ff80a-136">Delivery location shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="ff80a-137">它會連結至傳遞動作。</span><span class="sxs-lookup"><span data-stu-id="ff80a-137">It's linked to a Delivery Action.</span></span> <span data-ttu-id="ff80a-138">新增此欄位是為了深入瞭解當發現問題郵件時所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="ff80a-138">This field was added to give insight into the action taken when a problem mail is found.</span></span> <span data-ttu-id="ff80a-139">以下是傳遞位置的可能值:</span><span class="sxs-lookup"><span data-stu-id="ff80a-139">Here are the possible values of delivery location:</span></span>

1. <span data-ttu-id="ff80a-140">**收件匣或資料夾**-電子郵件位於 [收件匣] 或 [資料夾 (根據您的電子郵件規則)。</span><span class="sxs-lookup"><span data-stu-id="ff80a-140">**Inbox or folder** – The email is in inbox or a folder (according to your email rules).</span></span>
2. <span data-ttu-id="ff80a-141">**部署或外部**–信箱不存在於雲端上, 但在內部部署。</span><span class="sxs-lookup"><span data-stu-id="ff80a-141">**On-prem or external** – The mailbox doesn’t exist on cloud but is on -premises.</span></span>
3. <span data-ttu-id="ff80a-142">**垃圾郵件資料夾**–在使用者的 [垃圾郵件] 資料夾中的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="ff80a-142">**Junk folder** – The email in in the Junk folder of a user.</span></span>
4. <span data-ttu-id="ff80a-143">[**刪除的郵件] 資料夾**–使用者的 [刪除的郵件] 資料夾中的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="ff80a-143">**Deleted items folder** – The email in the Deleted items folder of a user.</span></span>
5. <span data-ttu-id="ff80a-144">**隔離**–隔離中的電子郵件, 且不在使用者的信箱中。</span><span class="sxs-lookup"><span data-stu-id="ff80a-144">**Quarantine** – The email in quarantine, and is not in a user’s mailbox.</span></span>
6. <span data-ttu-id="ff80a-145">**失敗**–電子郵件無法送達信箱。</span><span class="sxs-lookup"><span data-stu-id="ff80a-145">**Failed** – The email failed to reach the mailbox.</span></span>
7. <span data-ttu-id="ff80a-146">\*\*\*\* 捨棄–電子郵件會在郵件流程中的某處遺失。</span><span class="sxs-lookup"><span data-stu-id="ff80a-146">**Dropped** – The email gets lost somewhere in the Mailflow.</span></span>
  
## <a name="find-and-delete-suspicious-email-that-was-delivered"></a><span data-ttu-id="ff80a-147">尋找並刪除已傳遞的可疑電子郵件</span><span class="sxs-lookup"><span data-stu-id="ff80a-147">Find and delete suspicious email that was delivered</span></span>

> [!TIP]
> <span data-ttu-id="ff80a-148">威脅瀏覽器 (有時稱為 Explorer) 是一種功能強大的報表, 可用於多種用途, 例如尋找和刪除郵件、識別惡意電子郵件寄件者的 IP 位址, 或啟動事件以進一步進行調查。</span><span class="sxs-lookup"><span data-stu-id="ff80a-148">Threat Explorer (sometimes called Explorer), is a powerful report that can serve multiple purposes, such as finding and deleting messages, identifying the IP address of a malicious email sender, or starting an incident for further investigation.</span></span> <span data-ttu-id="ff80a-149">下列程式著重于使用 Explorer 來尋找和刪除收件者信箱中的惡意電子郵件。</span><span class="sxs-lookup"><span data-stu-id="ff80a-149">The following procedure focuses on using Explorer to find and delete malicious email from recipients mailboxes.</span></span>

<span data-ttu-id="ff80a-150">若要查看對前一個傳遞狀態欄位所做的變更 (現在是傳遞動作和傳遞位置):</span><span class="sxs-lookup"><span data-stu-id="ff80a-150">To see the changes to the former Delivery Status field (now Delivery Action and Delivery Location):</span></span> 

1. <span data-ttu-id="ff80a-151">請移[https://protection.office.com](https://protection.office.com)至並使用您的公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="ff80a-151">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365.</span></span> <span data-ttu-id="ff80a-152">這會將您帶到&amp;安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="ff80a-152">This takes you to the Security &amp; Compliance Center.</span></span> 
    
2. <span data-ttu-id="ff80a-153">在左側導覽中, 選擇 [**威脅管理** \> **瀏覽器**]。</span><span class="sxs-lookup"><span data-stu-id="ff80a-153">In the left navigation, choose **Threat management** \> **Explorer**.</span></span>
<!--Comment>
![Threat Explorer with Delivery Action and Delivery Location fields.](media/ThreatExFields.PNG)

    
3. In the View menu, choose **All email**.<br/>![Use the View menu to choose between Email and Content reports](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)
  
4. Notice the labels that appear in the report, such as **Delivered**, **Unknown**, or **Delivered to junk**.<br/>![Threat Explorer showing data for all email](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)<br/>(Depending on the actions that were taken on email messages for your organization, you might see additional labels, such as **Blocked** or **Replaced**.)
    
5. In the report, choose **Delivered** to view only emails that ended up in users' inboxes.<br/>![Clicking "Delivered to junk" removes that data from view](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)
  
6. Below the chart, review the **Email** list below the chart.<br/>![Below the chart, view a list of email messages that were detected](media/dfb60590-1236-499d-97da-86c68621e2bc.png)
  
7. In the list, choose an item to view more details about that email message. For example, you can click the subject line to view information about the sender, recipients, attachments, and other similar email messages.<br/>![You can view additional information about an item, including details and any attachments](media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
8. After viewing information about email messages, select one or more items in the list to activate **+ Actions**.
    
9. Use the **+ Actions** list to apply an action, such as **Move to deleted** items. This will delete the selected messages from the recipients' mailboxes.<br/>![When you select one or more email messages, you can choose from several available actions](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)
  
-->
## <a name="related-topics"></a><span data-ttu-id="ff80a-154">相關主題</span><span class="sxs-lookup"><span data-stu-id="ff80a-154">Related topics</span></span>

[<span data-ttu-id="ff80a-155">Office 365 高級威脅防護方案2</span><span class="sxs-lookup"><span data-stu-id="ff80a-155">Office 365 Advanced Threat Protection Plan 2</span></span>](office-365-ti.md)
  
[<span data-ttu-id="ff80a-156">防止 Office 365 中的威脅</span><span class="sxs-lookup"><span data-stu-id="ff80a-156">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="ff80a-157">查看 Office 365 的報告高級威脅防護</span><span class="sxs-lookup"><span data-stu-id="ff80a-157">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  

