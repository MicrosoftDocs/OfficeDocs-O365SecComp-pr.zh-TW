---
title: 動態傳遞和 Office 365 ATP 安全附件預覽
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/28/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
description: 當您設定好您 ATP 安全附件原則時，您選擇以避免郵件延遲，並啟用人員預覽會掃描附件的動態傳遞。
ms.openlocfilehash: 23017f4f995dfe6a90479d83af9522531d7bf96b
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526158"
---
# <a name="dynamic-delivery-and-previewing-with-office-365-atp-safe-attachments"></a><span data-ttu-id="70a76-103">動態傳遞和 Office 365 ATP 安全附件預覽</span><span class="sxs-lookup"><span data-stu-id="70a76-103">Dynamic delivery and previewing with Office 365 ATP Safe Attachments</span></span>

<span data-ttu-id="70a76-p101">動態傳遞則可以針對選取此選項。請閱讀本篇文章以深入了解動態傳遞，在[Office 365 中的 ATP 安全附件](atp-safe-attachments.md)的附件預覽功能。</span><span class="sxs-lookup"><span data-stu-id="70a76-p101">Dynamic delivery is an option that can be selected for . Read this article to learn about dynamic delivery and attachment preview capabilities in [ATP Safe Attachments in Office 365](atp-safe-attachments.md).</span></span>
  
## <a name="how-dynamic-delivery-works"></a><span data-ttu-id="70a76-106">如何動態傳遞運作</span><span class="sxs-lookup"><span data-stu-id="70a76-106">How dynamic delivery works</span></span>

<span data-ttu-id="70a76-p102">當您[設定 Office 365 中的 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)，您可以選擇從**封鎖**」、 「**取代**，與 「**動態傳遞**數個選項。根據您的原則設定的方式，電子郵件收件者可以體驗次要中電子郵件傳遞延遲時掃描其附件。若要避免郵件延遲回應，請選擇 [**動態傳遞**。</span><span class="sxs-lookup"><span data-stu-id="70a76-p102">When you [set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md), you can choose from several options, such as **Block**, **Replace**, and **Dynamic Delivery**. Depending on how your policies are configured, email recipients can experience a minor delay in email delivery while their attachments are scanned. To avoid message delays, choose **Dynamic Delivery**.</span></span>
  
<span data-ttu-id="70a76-p103">動態的傳遞選項不傳送具有版面配置區的每個電子郵件附件透過電子郵件訊息的本文以電子郵件延遲。附件掃描的[Office 365 中的 ATP 安全附件](atp-safe-attachments.md)之前，保持版面配置區。電子郵件收件者可讀取及回應其電子郵件訊息向右離開知道正在分析 [其附件。</span><span class="sxs-lookup"><span data-stu-id="70a76-p103">The dynamic delivery option eliminates email delays by sending the body of an email message through with a placeholder for each email attachment. The placeholder remains until the attachment is scanned by [ATP Safe Attachments in Office 365](atp-safe-attachments.md). Email recipients can read and respond to their email messages right away, knowing that their attachments are being analyzed.</span></span>
  
<span data-ttu-id="70a76-p104">大部分的 Pdf 和 Office 可以在安全模式中預覽文件時 ATP 掃描正在進行中。如果附件不相容的動態傳遞預覽程式，直到完成 ATP 安全附件掃描電子郵件收件者請參閱附件版面配置區。</span><span class="sxs-lookup"><span data-stu-id="70a76-p104">Most PDFs and Office documents can be previewed in safe mode while ATP scanning is underway. If an attachment is not compatible with the dynamic delivery previewer, email recipients see the attachment placeholder until ATP Safe Attachments scanning is complete.</span></span>
  
<span data-ttu-id="70a76-p105">清除 [每個附件時，它會自動重新附加到原始的電子郵件。如果設為惡意決定附件，它傳送至隔離某人在貴組織的安全性小組 （例如 Office 365 全域管理員或安全性管理員） 可以[管理 Office 365 中隔離的郵件](manage-quarantined-messages-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="70a76-p105">As each attachment is cleared, it is automatically reattached to the original email message. If an attachment is determined to be malicious, it is sent to quarantine, where someone on your organization's security team (such as an Office 365 global administrator or security administrator) can [manage quarantined messages in Office 365](manage-quarantined-messages-and-files.md).</span></span>
  
## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a><span data-ttu-id="70a76-117">當某人將轉送電子郵件的什麼包含附件？</span><span class="sxs-lookup"><span data-stu-id="70a76-117">What happens when someone forwards an email that contains an attachment?</span></span>

<span data-ttu-id="70a76-p106">假設組織會使用動態傳遞其[ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)」 與某人接收電子郵件含有附件。現在假設該名人員會在電子郵件轉寄給其他人。會發生什麼事？ATP 安全附件原則中是否包含其他收件者而定。</span><span class="sxs-lookup"><span data-stu-id="70a76-p106">Suppose that an organization is using dynamic delivery for their [ATP Safe Attachments policy](set-up-atp-safe-attachments-policies.md), and someone receives an email that contains an attachment. Now suppose that person is about to forward the email message to someone else. What happens? It depends on whether the additional recipients are included in ATP Safe Attachments policies.</span></span>
  
- <span data-ttu-id="70a76-122">如果收件者使用動態的傳遞選項 ATP 安全附件原則所涵蓋、 收件者會看見版面配置區與能夠預覽相容的檔案。</span><span class="sxs-lookup"><span data-stu-id="70a76-122">If a recipient is covered by an ATP Safe Attachments policy using the dynamic delivery option, then the recipient sees the placeholder, with the ability to preview compatible files.</span></span>
    
- <span data-ttu-id="70a76-123">如果收件者未涵蓋 ATP 安全附件原則，然後電子郵件和附件都會通過，而不掃描 ATP 安全附件或附件版面配置區。</span><span class="sxs-lookup"><span data-stu-id="70a76-123">If a recipient is not covered by an ATP Safe Attachments policy, then the email and attachment will go through, without ATP Safe Attachments scanning or attachment placeholders.</span></span>
    
## <a name="whats-required-for-dynamic-delivery-to-work"></a><span data-ttu-id="70a76-124">如何才能以動態傳遞給運作？</span><span class="sxs-lookup"><span data-stu-id="70a76-124">What's required for dynamic delivery to work?</span></span>

- <span data-ttu-id="70a76-125">您的組織必須具有[Office 365 進階威脅保護](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="70a76-125">Your organization must have [Office 365 Advanced Threat Protection](office-365-atp.md)</span></span>
    
- <span data-ttu-id="70a76-126">必須使用動態的傳遞選項 （請參閱[Set up Office 365 中的 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)） ATP 安全附件定義原則</span><span class="sxs-lookup"><span data-stu-id="70a76-126">Policies must be defined for ATP Safe Attachments using the dynamic delivery option (See [Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md))</span></span>
    
- <span data-ttu-id="70a76-127">Office 365 中必須主控貴組織的電子郵件</span><span class="sxs-lookup"><span data-stu-id="70a76-127">Your organization's email must be hosted in Office 365</span></span>
    
## <a name="are-there-scenarios-for-which-dynamic-delivery-is-not-available"></a><span data-ttu-id="70a76-128">是否有不提供動態傳遞案例吗？</span><span class="sxs-lookup"><span data-stu-id="70a76-128">Are there scenarios for which dynamic delivery is not available?</span></span>

<span data-ttu-id="70a76-p107">以下是不會支援動態傳遞為特定案例。這些包括下列：</span><span class="sxs-lookup"><span data-stu-id="70a76-p107">There are certain scenarios in which dynamic delivery is not supported. These include the following:</span></span>
  
- <span data-ttu-id="70a76-131">公用資料夾中的電子郵件</span><span class="sxs-lookup"><span data-stu-id="70a76-131">Email messages that are in public folders</span></span>
    
- <span data-ttu-id="70a76-132">不會路由傳送然後回來成使用自訂規則的使用者信箱的電子郵件</span><span class="sxs-lookup"><span data-stu-id="70a76-132">Email messages that are routed out of and then back into the user's mailbox using custom rules</span></span>
    
- <span data-ttu-id="70a76-133">會移動 （自動或手動） 不在主控信箱並將其他位置，包括封存資料夾的郵件</span><span class="sxs-lookup"><span data-stu-id="70a76-133">Messages that are moved (automatically or manually) out of the hosted mailbox and into other locations, including archive folders</span></span>
    
- <span data-ttu-id="70a76-134">會刪除的郵件</span><span class="sxs-lookup"><span data-stu-id="70a76-134">Messages that are deleted</span></span>
    
- <span data-ttu-id="70a76-135">處於錯誤狀態的使用者的信箱搜尋資料夾</span><span class="sxs-lookup"><span data-stu-id="70a76-135">A user's mailbox search folder that is in an error state</span></span>
    
- <span data-ttu-id="70a76-p108">Exchange Online 系統管理員已啟用 Exclaimer 的環境。（請參閱[附件的郵件不會傳遞 ATP 動態傳遞和 Exclaimer 可用時](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)）</span><span class="sxs-lookup"><span data-stu-id="70a76-p108">Environments in which an Exchange Online admin has enabled Exclaimer. (See [Messages with attachments are not delivered when ATP Dynamic Delivery and Exclaimer are used](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery))</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="70a76-138">相關主題</span><span class="sxs-lookup"><span data-stu-id="70a76-138">Related topics</span></span>

[<span data-ttu-id="70a76-139">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="70a76-139">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="70a76-140">Office 365 中的 ATP 安全附件</span><span class="sxs-lookup"><span data-stu-id="70a76-140">ATP Safe Attachments in Office 365</span></span>](atp-safe-attachments.md)
  
[<span data-ttu-id="70a76-141">設定 Office 365 中的 ATP 安全附件原則</span><span class="sxs-lookup"><span data-stu-id="70a76-141">Set up ATP Safe Attachments policies in Office 365</span></span>](set-up-atp-safe-attachments-policies.md)
  
[<span data-ttu-id="70a76-142">Office 365 中的 ATP 安全連結</span><span class="sxs-lookup"><span data-stu-id="70a76-142">ATP Safe Links in Office 365</span></span>](atp-safe-links.md)

[<span data-ttu-id="70a76-143">Office 365 安全性權限&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="70a76-143">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  

