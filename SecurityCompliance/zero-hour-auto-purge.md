---
title: 零時差自動清除 - 防範垃圾郵件和惡意程式碼
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 12/05/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
description: 零時差自動清除 (ZAP) 是偵測到郵件與垃圾郵件或惡意程式碼中已被傳送到使用者的收件匣，電子郵件保護功能，並再呈現無害惡意內容。 如何 ZAP 執行此動作，則偵測到的惡意內容類型而定。
ms.openlocfilehash: b28de1b05843e3f5b0f6e7fc905c96f094c277f9
ms.sourcegitcommit: 74ad22a5c6c3c9d9324f0f97070909e323a4e9cf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/11/2019
ms.locfileid: "30524017"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a><span data-ttu-id="906a9-104">零時差自動清除 - 防範垃圾郵件和惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="906a9-104">Zero-hour auto purge - protection against spam and malware</span></span>

## <a name="overview"></a><span data-ttu-id="906a9-105">概觀</span><span class="sxs-lookup"><span data-stu-id="906a9-105">Overview</span></span>

<span data-ttu-id="906a9-106">零時差自動清除 (ZAP) 是偵測到的郵件釣魚程式、 垃圾郵件或惡意程式碼中已被傳送到使用者的收件匣，電子郵件保護功能，並再呈現無害惡意內容。</span><span class="sxs-lookup"><span data-stu-id="906a9-106">Zero-hour auto purge (ZAP) is an email protection feature that detects messages with phish, spam, or malware that have already been delivered to your users' inboxes, and then renders the malicious content harmless.</span></span> <span data-ttu-id="906a9-107">ZAP 如何這取決於偵測到; 惡意內容類型郵件可以 zapped 由於郵件內容、 Url 或附件。</span><span class="sxs-lookup"><span data-stu-id="906a9-107">How ZAP does this depends on the type of malicious content detected; mail can be zapped due to mail content, URLs, or attachments.</span></span>
  
<span data-ttu-id="906a9-108">ZAP 是隨附於預設隨附於任何 Office 365 訂用帳戶，包含 Exchange Online 信箱的 Exchange Online Protection。</span><span class="sxs-lookup"><span data-stu-id="906a9-108">ZAP is available with the default Exchange Online Protection that is included with any Office 365 subscription that contains Exchange Online mailboxes.</span></span>

<span data-ttu-id="906a9-109">ZAP 已開啟根據預設，但必須符合下列條件：</span><span class="sxs-lookup"><span data-stu-id="906a9-109">ZAP is turned on by default, but the following conditions must be met:</span></span>
  
- <span data-ttu-id="906a9-110">**垃圾郵件動作**設為**移至垃圾郵件] 資料夾的郵件**。</span><span class="sxs-lookup"><span data-stu-id="906a9-110">**Spam action** is set to **Move message to Junk Email folder**.</span></span> <br/><span data-ttu-id="906a9-111">您也可以建立僅適用於一群使用者如果您不想所有信箱移轉至雲端過濾的 ZAP 新垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="906a9-111">You can also create a new spam filter policy that applies only to a set of users if you don't want all mailboxes to be screened by ZAP.</span></span>

- <span data-ttu-id="906a9-112">使用者有保留其預設垃圾郵件設定]，且已不會關閉垃圾郵件保護。</span><span class="sxs-lookup"><span data-stu-id="906a9-112">Users have kept their default junk mail settings, and have not turned off junk email protection.</span></span> <span data-ttu-id="906a9-113">（如需在 Outlook 中的使用者選項的詳細資訊，請參閱[變更的垃圾郵件篩選器中的保護層級](https://support.office.com/article/change-the-level-of-protection-in-the-junk-email-filter-e89c12d8-9d61-4320-8c57-d982c8d52f6b)）。</span><span class="sxs-lookup"><span data-stu-id="906a9-113">(See [Change the level of protection in the Junk Email Filter](https://support.office.com/article/change-the-level-of-protection-in-the-junk-email-filter-e89c12d8-9d61-4320-8c57-d982c8d52f6b) for details about user options in Outlook.)</span></span> 
  
## <a name="how-does-zap-work"></a><span data-ttu-id="906a9-114">ZAP 的運作方式？</span><span class="sxs-lookup"><span data-stu-id="906a9-114">How does ZAP work?</span></span>

<span data-ttu-id="906a9-115">Office 365 更新反垃圾郵件引擎和惡意程式碼中的簽章即時每日。</span><span class="sxs-lookup"><span data-stu-id="906a9-115">Office 365 updates anti-spam engine and malware signatures in real-time on a daily basis.</span></span> <span data-ttu-id="906a9-116">不過，您的使用者仍可能會收到惡意的郵件傳遞到不同的原因，包括內容 weaponized 之後會傳遞至使用者的收件匣。</span><span class="sxs-lookup"><span data-stu-id="906a9-116">However, your users might still get malicious messages delivered to their inboxes for a variety of reasons, including if content is weaponized after being delivered to users.</span></span> <span data-ttu-id="906a9-117">ZAP 解決此問題持續監視更新的 Office 365 垃圾郵件和惡意程式碼簽章。</span><span class="sxs-lookup"><span data-stu-id="906a9-117">ZAP addresses this by continually monitoring updates to the Office 365 spam and malware signatures.</span></span> <span data-ttu-id="906a9-118">ZAP 可以找出並移除先前已傳遞的郵件已在使用者的收件匣中。</span><span class="sxs-lookup"><span data-stu-id="906a9-118">ZAP can find and remove previously delivered messages that are already in users' inboxes.</span></span> 

- <span data-ttu-id="906a9-119">識別為垃圾郵件的郵件，ZAP 會將未閱讀的郵件移至使用者的垃圾郵件資料夾。</span><span class="sxs-lookup"><span data-stu-id="906a9-119">For mail that is identified as spam, ZAP moves unread messages to users' Junk mail folder.</span></span> 

- <span data-ttu-id="906a9-120">識別為釣魚程式的郵件，ZAP 會將郵件移至使用者的垃圾郵件] 資料夾，不論是否已讀取電子郵件。</span><span class="sxs-lookup"><span data-stu-id="906a9-120">For mail that is identified as phish, ZAP moves messages to users' Junk mail folder, regardless of whether the email has been read.</span></span>

- <span data-ttu-id="906a9-121">新偵測到惡意程式碼，ZAP 會移除電子郵件，不論是否已讀取電子郵件附件。</span><span class="sxs-lookup"><span data-stu-id="906a9-121">For newly detected malware, ZAP removes attachments from email messages, regardless of whether the email has been read.</span></span> 
  
<span data-ttu-id="906a9-122">ZAP 動作是很完美的信箱使用者資訊。如果移動電子郵件訊息時，它們不會通知。</span><span class="sxs-lookup"><span data-stu-id="906a9-122">The ZAP action is seamless for the mailbox user; they are not notified if an email message is moved.</span></span>
  
<span data-ttu-id="906a9-123">允許清單、[郵件流程規則](https://go.microsoft.com/fwlink/p/?LinkId=722755)及使用者規則或其他篩選器會優先於 ZAP。</span><span class="sxs-lookup"><span data-stu-id="906a9-123">Allow lists, [mail flow rules](https://go.microsoft.com/fwlink/p/?LinkId=722755), and end user rules or additional filters take precedence over ZAP.</span></span>
  
## <a name="to-review-or-set-up-a-spam-filter-policy"></a><span data-ttu-id="906a9-124">若要檢視或設定的垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="906a9-124">To review or set up a spam filter policy</span></span>
  
1. <span data-ttu-id="906a9-125">移至 [[https://protection.office.com](https://protection.office.com)和 Office 365 使用公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="906a9-125">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365.</span></span>

2. <span data-ttu-id="906a9-126">**威脅管理**] 下選擇 [**反垃圾郵件**]。</span><span class="sxs-lookup"><span data-stu-id="906a9-126">Under **Threat management**, choose **Anti-spam**.</span></span>

3. <span data-ttu-id="906a9-127">檢閱標準設定。</span><span class="sxs-lookup"><span data-stu-id="906a9-127">Review the standard settings.</span></span> 

4. <span data-ttu-id="906a9-128">如果您想要自訂您的設定，選取 [**自訂**] 索引標籤，並開啟 [**自訂設定**。</span><span class="sxs-lookup"><span data-stu-id="906a9-128">If you want to customize your settings, select the **Custom** tab, and turn on **Custom settings**.</span></span> <span data-ttu-id="906a9-129">編輯您的設定，如果您想，選擇 [ **+ 建立原則**來新增新的原則。</span><span class="sxs-lookup"><span data-stu-id="906a9-129">Edit your settings and if you want, choose **+ Create a policy** to add a new policy.</span></span> 
    
## <a name="to-see-if-zap-moved-your-message"></a><span data-ttu-id="906a9-130">若要查看 ZAP 是否移動郵件</span><span class="sxs-lookup"><span data-stu-id="906a9-130">To see if ZAP moved your message</span></span>

<span data-ttu-id="906a9-131">如果您想要看到 ZAP 如果移動您的郵件，您可以使用[威脅保護狀態報表](view-email-security-reports.md#threat-protection-status-report)（或[威脅總管](use-explorer-in-security-and-compliance.md)）。</span><span class="sxs-lookup"><span data-stu-id="906a9-131">If you want to see if ZAP moved your message, you can use either the [Threat Protection Status report](view-email-security-reports.md#threat-protection-status-report) (or [Threat Explorer](use-explorer-in-security-and-compliance.md)).</span></span>
    
## <a name="to-disable-zap"></a><span data-ttu-id="906a9-132">若要停用 ZAP</span><span class="sxs-lookup"><span data-stu-id="906a9-132">To disable ZAP</span></span>
  
<span data-ttu-id="906a9-133">如果您想要停用您 Office 365 租用戶時能量光束或一組使用者，使用[Set-hostedcontentfilterpolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758)，EOP 指令程式的**ZapEnabled**參數。</span><span class="sxs-lookup"><span data-stu-id="906a9-133">If you want to disable ZAP for your Office 365 tenant, or a set of users, use the **ZapEnabled** parameter of [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758), an EOP cmdlet.</span></span>
    
<span data-ttu-id="906a9-134">在下列範例中，ZAP 已停用名為"Test"的內容篩選原則。</span><span class="sxs-lookup"><span data-stu-id="906a9-134">In the following example, ZAP is disabled for a content filter policy named "Test".</span></span>
    
```
  Set-HostedContentFilterPolicy -Identity Test -ZapEnabled $false
```

## <a name="faq"></a><span data-ttu-id="906a9-135">常見問題集</span><span class="sxs-lookup"><span data-stu-id="906a9-135">FAQ</span></span>

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a><span data-ttu-id="906a9-136">如果合法郵件移至 [垃圾郵件] 資料夾，會發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="906a9-136">What happens if a legitimate message is moved to the junk mail folder?</span></span>
  
<span data-ttu-id="906a9-137">您應該遵循誤判正常的報告程的序。</span><span class="sxs-lookup"><span data-stu-id="906a9-137">You should follow the normal reporting process for false-positives.</span></span> <span data-ttu-id="906a9-138">郵件會從收件匣移至 [垃圾郵件] 資料夾的唯一原因可能因為服務已決定郵件是垃圾郵件或惡意。</span><span class="sxs-lookup"><span data-stu-id="906a9-138">The only reason the message would be moved from the inbox to the junk mail folder would be because the service has determined that the message was spam or malicious.</span></span>
  
### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a><span data-ttu-id="906a9-139">如果使用 Office 365 隔離而不是垃圾郵件資料夾？</span><span class="sxs-lookup"><span data-stu-id="906a9-139">What if I use the Office 365 quarantine instead of the junk mail folder?</span></span>
  
<span data-ttu-id="906a9-140">ZAP 不會將郵件移至隔離區從收件匣這一次。</span><span class="sxs-lookup"><span data-stu-id="906a9-140">ZAP doesn't move messages into quarantine from the Inbox at this time.</span></span>
  
### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a><span data-ttu-id="906a9-141">如果我有自訂郵件流程規則 （封鎖 / 允許規則）？</span><span class="sxs-lookup"><span data-stu-id="906a9-141">What If I have a custom mail flow rule (Block/ Allow Rule)?</span></span>
  
<span data-ttu-id="906a9-142">建立由系統管理員 （郵件流程規則）] 或 [封鎖] 和 [允許規則的規則的優先順序。</span><span class="sxs-lookup"><span data-stu-id="906a9-142">Rules created by admins (mail flow rules) or Block and Allow rules take precedence.</span></span> <span data-ttu-id="906a9-143">這類郵件會排除功能準則。</span><span class="sxs-lookup"><span data-stu-id="906a9-143">Such messages are excluded from the feature criteria.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="906a9-144">相關主題</span><span class="sxs-lookup"><span data-stu-id="906a9-144">Related Topics</span></span>

[<span data-ttu-id="906a9-145">Office 365 電子郵件的反垃圾郵件保護</span><span class="sxs-lookup"><span data-stu-id="906a9-145">Office 365 Email Anti-Spam Protection</span></span>](anti-spam-protection.md)
  
[<span data-ttu-id="906a9-146">利用 Office 365 垃圾郵件篩選器封鎖電子郵件垃圾郵件以避免誤判正常</span><span class="sxs-lookup"><span data-stu-id="906a9-146">Block email spam with the Office 365 spam filter to prevent false negative issues</span></span>](reduce-spam-email.md)
  

