---
title: 尋找並調查惡意 （Office 365 威脅調查及回應已傳送的電子郵件
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
description: 了解如何使用威脅調查及回應功能來尋找並調查惡意電子郵件。
ms.openlocfilehash: 7e2cef742339e54c094cfb0c3b32fbf596896a3d
ms.sourcegitcommit: 2b46fba650df8d252b1dd2b3c3f080a383183a06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/23/2019
ms.locfileid: "34408298"
---
# <a name="find-and-investigate-malicious-email-that-was-delivered-office-365-advanced-threat-protection-plan-2"></a><span data-ttu-id="609da-103">尋找並調查惡意電子郵件已傳遞 (Office 365 進階威脅防護計劃 2)</span><span class="sxs-lookup"><span data-stu-id="609da-103">Find and investigate malicious email that was delivered (Office 365 Advanced Threat Protection Plan 2)</span></span>

<span data-ttu-id="609da-104">[Office 365 進階威脅防護](office-365-atp.md)可讓您調查，將您的使用者放在風險，並採取動作來保護您的組織活動。</span><span class="sxs-lookup"><span data-stu-id="609da-104">[Office 365 Advanced Threat Protection](office-365-atp.md) enables you to investigate activities that put your users at risk and take action to protect your organization.</span></span> <span data-ttu-id="609da-105">例如，如果您是貴組織的安全性小組的一部分，您可以尋找和調查可疑的電子郵件已傳遞至您的使用者。</span><span class="sxs-lookup"><span data-stu-id="609da-105">For example, if you are part of your organization's security team, you can find and investigate suspicious email messages that were delivered to your users.</span></span> <span data-ttu-id="609da-106">您可以使用[威脅總管 （或即時偵測的資訊）](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="609da-106">You can do this by using [Threat Explorer (or real-time detections)](threat-explorer.md).</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="609da-107">開始之前...]</span><span class="sxs-lookup"><span data-stu-id="609da-107">Before you begin...</span></span>

<span data-ttu-id="609da-108">請確定符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="609da-108">Make sure that the following requirements are met:</span></span>
  
- <span data-ttu-id="609da-109">您的組織有[Office 365 進階威脅防護](office-365-atp.md)（方案 1 或計劃 2） 並[將授權指派給使用者](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="609da-109">Your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (Plan 1 or Plan 2) and [licenses are assigned to users](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users).</span></span>
    
- <span data-ttu-id="609da-110">[Office 365 稽核記錄](turn-audit-log-search-on-or-off.md)已為您的組織。</span><span class="sxs-lookup"><span data-stu-id="609da-110">[Office 365 audit logging](turn-audit-log-search-on-or-off.md) is turned on for your organization.</span></span> 
    
- <span data-ttu-id="609da-111">貴組織的原則定義的反垃圾郵件、 反惡意程式碼、 反網路釣魚，依此類推。</span><span class="sxs-lookup"><span data-stu-id="609da-111">Your organization has policies defined for anti-spam, anti-malware, anti-phishing, and so on.</span></span> <span data-ttu-id="609da-112">請參閱[針對 Office 365 中的威脅保護](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="609da-112">See [Protect against threats in Office 365](protect-against-threats.md).</span></span>
    
- <span data-ttu-id="609da-113">您是 Office 365 全域管理員，或具有安全性系統管理員或 「 搜尋及清除角色指派安全性&amp;合規性中心。</span><span class="sxs-lookup"><span data-stu-id="609da-113">You are an Office 365 global administrator, or you have either the Security Administrator or the Search and Purge role assigned in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="609da-114">請參閱[中的 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="609da-114">See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    
## <a name="dealing-with-suspicious-emails"></a><span data-ttu-id="609da-115">處理可疑的電子郵件</span><span class="sxs-lookup"><span data-stu-id="609da-115">Dealing with suspicious emails</span></span>

<span data-ttu-id="609da-116">惡意攻擊者可能會將郵件傳送至您的使用者嘗試與釣魚程式其認證，並存取您公司的機密資料 ！</span><span class="sxs-lookup"><span data-stu-id="609da-116">Malicious attackers may be sending mail to your users to try and phish their credentials and gain access to your corporate secrets!</span></span> <span data-ttu-id="609da-117">若要避免這個問題，您應該使用提供的 Office 365，包括[Exchange Online Protection](eop/exchange-online-protection-overview.md)和[進階威脅防護](office-365-atp.md)的威脅保護服務。</span><span class="sxs-lookup"><span data-stu-id="609da-117">In order to prevent this, you should use the threat protection services offered by Office 365, including [Exchange Online Protection](eop/exchange-online-protection-overview.md) and [Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="609da-118">不過，有的時間攻擊者時將郵件傳送給使用者的 url 然後僅更新版本上將該 URL 點對惡意內容 （惡意程式碼等）。</span><span class="sxs-lookup"><span data-stu-id="609da-118">However, there are times when an attacker could send mail to your users containing a URL and only later on make that URL point to malicious content (malware, etc.).</span></span> <span data-ttu-id="609da-119">或者，您可能會發現太晚而遭入侵您組織中的使用者，以及攻擊時遭到盜用了該使用者，使用該帳戶傳送電子郵件給您公司中的其他使用者。</span><span class="sxs-lookup"><span data-stu-id="609da-119">Alternatively, you may realize too late that a user in your organization has been compromised, and while that user was compromised, an attacker used that account to send email to other users in your company.</span></span> <span data-ttu-id="609da-120">一部分 < cleaning up 這兩種情況，您可能想要移除使用者收件匣的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="609da-120">As part of cleaning up both of these scenarios, you may want to remove email messages from user inboxes.</span></span> <span data-ttu-id="609da-121">在這類的情況下，您可以利用[威脅總管 （或即時偵測）](threat-explorer.md)來尋找和移除這些電子郵件訊息 ！</span><span class="sxs-lookup"><span data-stu-id="609da-121">In situations like these, you can leverage [Threat Explorer (or real-time detections)](threat-explorer.md) to find and remove those email messages!</span></span>
  
## <a name="find-and-delete-suspicious-email-that-was-delivered"></a><span data-ttu-id="609da-122">尋找並刪除可疑的電子郵件的郵件傳遞</span><span class="sxs-lookup"><span data-stu-id="609da-122">Find and delete suspicious email that was delivered</span></span>

> [!TIP]
> <span data-ttu-id="609da-123">威脅總管 （也稱為 「 檔案總管 」），是功能強大的報表，可以有多個用途，例如尋找及刪除的郵件，用來識別惡意電子郵件寄件者的 IP 位址或開始進一步調查的事件。</span><span class="sxs-lookup"><span data-stu-id="609da-123">Threat Explorer (also referred to as Explorer), is a powerful report that can serve multiple purposes, such as finding and deleting messages, identifying the IP address of a malicious email sender, or starting an incident for further investigation.</span></span> <span data-ttu-id="609da-124">下列程序著重於使用 Explorer 來尋找並從收件者信箱刪除惡意電子郵件。</span><span class="sxs-lookup"><span data-stu-id="609da-124">The following procedure focuses on using Explorer to find and delete malicious email from recipients mailboxes.</span></span> 
  
1. <span data-ttu-id="609da-125">移至 [[https://protection.office.com](https://protection.office.com)和 Office 365 使用公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="609da-125">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365.</span></span> <span data-ttu-id="609da-126">這會帶您前往安全性&amp;合規性中心。</span><span class="sxs-lookup"><span data-stu-id="609da-126">This takes you to the Security &amp; Compliance Center.</span></span> 
    
2. <span data-ttu-id="609da-127">在左側導覽中，選擇 [**威脅管理，** \> **總管**。</span><span class="sxs-lookup"><span data-stu-id="609da-127">In the left navigation, choose **Threat management** \> **Explorer**.</span></span>
    
3. <span data-ttu-id="609da-128">在 [檢視] 功能表中，選擇 [**所有電子郵件**。</span><span class="sxs-lookup"><span data-stu-id="609da-128">In the View menu, choose **All email**.</span></span><br/><span data-ttu-id="609da-129">![使用 [檢視] 功能表的電子郵件和內容的報告之間選擇](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)</span><span class="sxs-lookup"><span data-stu-id="609da-129">![Use the View menu to choose between Email and Content reports](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)</span></span>
  
4. <span data-ttu-id="609da-130">請注意報表，例如**已傳遞**、**未知**，或**傳遞至垃圾郵件**中顯示的標籤。</span><span class="sxs-lookup"><span data-stu-id="609da-130">Notice the labels that appear in the report, such as **Delivered**, **Unknown**, or **Delivered to junk**.</span></span><br/><span data-ttu-id="609da-131">![顯示所有的電子郵件資料的威脅總管](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)</span><span class="sxs-lookup"><span data-stu-id="609da-131">![Threat Explorer showing data for all email](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)</span></span><br/><span data-ttu-id="609da-132">（根據對貴組織的電子郵件所採取的動作，您可能會看到其他標籤，例如**封鎖**或**取代**）。</span><span class="sxs-lookup"><span data-stu-id="609da-132">(Depending on the actions that were taken on email messages for your organization, you might see additional labels, such as **Blocked** or **Replaced**.)</span></span>
    
5. <span data-ttu-id="609da-133">在報告中，選擇 [**已傳遞**的以檢視僅最後出現在使用者的收件匣的電子郵件]。</span><span class="sxs-lookup"><span data-stu-id="609da-133">In the report, choose **Delivered** to view only emails that ended up in users' inboxes.</span></span><br/><span data-ttu-id="609da-134">![按一下 「 傳遞至垃圾郵件 」 從檢視中移除該資料](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)</span><span class="sxs-lookup"><span data-stu-id="609da-134">![Clicking "Delivered to junk" removes that data from view](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)</span></span>
  
6. <span data-ttu-id="609da-135">下方圖表中，檢閱圖表下方的**電子郵件**清單。</span><span class="sxs-lookup"><span data-stu-id="609da-135">Below the chart, review the **Email** list below the chart.</span></span><br/><span data-ttu-id="609da-136">![下方圖表中，檢視已偵測到的電子郵件的清單](media/dfb60590-1236-499d-97da-86c68621e2bc.png)</span><span class="sxs-lookup"><span data-stu-id="609da-136">![Below the chart, view a list of email messages that were detected](media/dfb60590-1236-499d-97da-86c68621e2bc.png)</span></span>
  
7. <span data-ttu-id="609da-137">在清單中，選擇 [項目來檢視電子郵件訊息的相關詳細資料]。</span><span class="sxs-lookup"><span data-stu-id="609da-137">In the list, choose an item to view more details about that email message.</span></span> <span data-ttu-id="609da-138">例如，您可以按一下 [檢視資訊寄件者、 收件者、 附件及其他類似的電子郵件的主旨行。</span><span class="sxs-lookup"><span data-stu-id="609da-138">For example, you can click the subject line to view information about the sender, recipients, attachments, and other similar email messages.</span></span><br/>![您可以檢視項目，包括詳細資料和任何附件相關的其他資訊](media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
8. <span data-ttu-id="609da-140">之後檢視電子郵件的相關資訊，請啟動 **+ 動作**清單中選取一或多個項目。</span><span class="sxs-lookup"><span data-stu-id="609da-140">After viewing information about email messages, select one or more items in the list to activate **+ Actions**.</span></span>
    
9. <span data-ttu-id="609da-141">使用 **+ 動作**清單將套用的動作，例如**將移至刪除**的項目。</span><span class="sxs-lookup"><span data-stu-id="609da-141">Use the **+ Actions** list to apply an action, such as **Move to deleted** items.</span></span> <span data-ttu-id="609da-142">這會從收件者的信箱刪除選取的郵件。</span><span class="sxs-lookup"><span data-stu-id="609da-142">This will delete the selected messages from the recipients' mailboxes.</span></span><br/><span data-ttu-id="609da-143">![當您選取一或多個電子郵件時，您可以選擇從數個可用的動作](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)</span><span class="sxs-lookup"><span data-stu-id="609da-143">![When you select one or more email messages, you can choose from several available actions](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="609da-144">相關主題</span><span class="sxs-lookup"><span data-stu-id="609da-144">Related topics</span></span>

[<span data-ttu-id="609da-145">Office 365 進階的威脅保護計劃 2</span><span class="sxs-lookup"><span data-stu-id="609da-145">Office 365 Advanced Threat Protection Plan 2</span></span>](office-365-ti.md)
  
[<span data-ttu-id="609da-146">防範 Office 365 中的威脅</span><span class="sxs-lookup"><span data-stu-id="609da-146">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="609da-147">檢視 Office 365 進階威脅防護報告</span><span class="sxs-lookup"><span data-stu-id="609da-147">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  

