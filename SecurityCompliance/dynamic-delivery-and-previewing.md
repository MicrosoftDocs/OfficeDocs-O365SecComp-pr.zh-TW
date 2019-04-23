---
title: 動態傳遞和預覽與 Office 365 ATP 安全附件
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 04/19/2019
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
ms.collection:
- M365-security-compliance
description: 當您設定 ATP 安全附件原則時，您可以選擇以避免郵件延遲，並讓使用者在預覽所掃描的附件動態傳遞。
ms.openlocfilehash: 567b5f0c5bc75123169073bf5dc33de191187846
ms.sourcegitcommit: f0e3c9de0b545081a4d264f74559b941f6c71410
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2019
ms.locfileid: "31958564"
---
# <a name="dynamic-delivery-and-previewing-with-office-365-atp-safe-attachments"></a><span data-ttu-id="363ba-103">動態傳遞和預覽與 Office 365 ATP 安全附件</span><span class="sxs-lookup"><span data-stu-id="363ba-103">Dynamic Delivery and previewing with Office 365 ATP Safe Attachments</span></span>

## <a name="overview"></a><span data-ttu-id="363ba-104">概觀</span><span class="sxs-lookup"><span data-stu-id="363ba-104">Overview</span></span>

<span data-ttu-id="363ba-105">動態傳遞是可選取用於[ATP 安全附件](atp-safe-attachments.md)的選項。</span><span class="sxs-lookup"><span data-stu-id="363ba-105">Dynamic Delivery is an option that can be selected for [ATP Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="363ba-106">閱讀本篇文章以了解動態傳遞和在[Office 365 中的 ATP 安全附件](atp-safe-attachments.md)的附件預覽功能。</span><span class="sxs-lookup"><span data-stu-id="363ba-106">Read this article to learn about Dynamic Delivery and attachment preview capabilities in [ATP Safe Attachments in Office 365](atp-safe-attachments.md).</span></span>

<span data-ttu-id="363ba-107">當[ATP 安全附件原則設定](set-up-atp-safe-attachments-policies.md)為您的組織，提供了幾種方式處理電子郵件附件。</span><span class="sxs-lookup"><span data-stu-id="363ba-107">When [ATP Safe Attachments policies are set up](set-up-atp-safe-attachments-policies.md) for your organization, there are several options for how email attachments are handled.</span></span> <span data-ttu-id="363ba-108">這些包括**封鎖**、**取代**和**動態傳遞**。</span><span class="sxs-lookup"><span data-stu-id="363ba-108">These include **Block**, **Replace**, and **Dynamic Delivery**.</span></span> <span data-ttu-id="363ba-109">根據 ATP 安全附件原則設定的方式，雖然其附件掃描電子郵件收件者時，可能會遇到次要電子郵件傳遞延遲。</span><span class="sxs-lookup"><span data-stu-id="363ba-109">Depending on how ATP Safe Attachments policies are configured, email recipients might experience a minor delay in email delivery while their attachments are scanned.</span></span> <span data-ttu-id="363ba-110">若要避免郵件延遲，選擇 [**動態傳遞**]。</span><span class="sxs-lookup"><span data-stu-id="363ba-110">To avoid message delays, choose **Dynamic Delivery**.</span></span>
  
## <a name="how-dynamic-delivery-works"></a><span data-ttu-id="363ba-111">動態傳遞的運作方式</span><span class="sxs-lookup"><span data-stu-id="363ba-111">How Dynamic Delivery works</span></span>
  
<span data-ttu-id="363ba-112">動態傳遞會透過電子郵件延遲藉由將透過電子郵件訊息的本文傳送給收件者的每個電子郵件附件的預留位置。</span><span class="sxs-lookup"><span data-stu-id="363ba-112">Dynamic Delivery eliminates email delays by sending the body of an email message through to the recipient with a placeholder for each email attachment.</span></span> <span data-ttu-id="363ba-113">一份附件會掃描，並為安全取決於[ATP 安全附件](atp-safe-attachments.md)之前，仍會保留版面配置區。</span><span class="sxs-lookup"><span data-stu-id="363ba-113">The placeholder remains until a copy of the attachment is scanned and determined to be safe by [ATP Safe Attachments](atp-safe-attachments.md).</span></span> 

- <span data-ttu-id="363ba-114">清除 [每個附件時，它是可用來開啟或下載。</span><span class="sxs-lookup"><span data-stu-id="363ba-114">As each attachment is cleared, it is available to open or download.</span></span> 

- <span data-ttu-id="363ba-115">如果判斷附件為惡意，就會傳送至隔離區，某人在貴組織的安全性小組 （例如 Office 365 全域系統管理員或安全性系統管理員） 可以[管理 Office 365 中的隔離的郵件](manage-quarantined-messages-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="363ba-115">If an attachment is determined to be malicious, it is sent to quarantine, where someone on your organization's security team (such as an Office 365 global administrator or security administrator) can [manage quarantined messages in Office 365](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="363ba-116">大部分的 Pdf 和 Office ATP 掃描正在進行中時，可以在安全模式中預覽文件。</span><span class="sxs-lookup"><span data-stu-id="363ba-116">Most PDFs and Office documents can be previewed in safe mode while ATP scanning is underway.</span></span> <span data-ttu-id="363ba-117">如果附件不相容於動態傳遞預覽程式，電子郵件收件者會看到附件版面配置區，直到 ATP 安全附件掃描已完成。</span><span class="sxs-lookup"><span data-stu-id="363ba-117">If an attachment is not compatible with the Dynamic Delivery previewer, email recipients see an attachment placeholder until ATP Safe Attachments scanning is complete.</span></span>

> [!TIP]
> <span data-ttu-id="363ba-118">如果您使用的行動裝置，並且 Pdf 無法呈現在第一次的動態傳遞預覽程式，請嘗試登入 Office 365 中，使用您行動裝置瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="363ba-118">If you're using a mobile device, and PDFs are not rendering in Dynamic Delivery previewer at first, try signing into Office 365 using your mobile browser.</span></span>

<span data-ttu-id="363ba-119">動態傳遞的人員可以閱讀和回覆其電子郵件立即時正在分析其附件。</span><span class="sxs-lookup"><span data-stu-id="363ba-119">With Dynamic Delivery, people can read and respond to their email messages right away, while their attachments are being analyzed.</span></span> 

<span data-ttu-id="363ba-120">ATP 安全附件掃描採取放在您的 Office 365 資料所在的相同區域中。</span><span class="sxs-lookup"><span data-stu-id="363ba-120">ATP Safe Attachments scanning takes place in the same region where your Office 365 data resides.</span></span> <span data-ttu-id="363ba-121">如需有關資料中心地理位置的詳細資訊，請參閱 <<c0>其中是位於您資料？</span><span class="sxs-lookup"><span data-stu-id="363ba-121">For more information about data center geography, see [Where is your data located?](https://products.office.com/where-is-your-data-located?geo=All)</span></span> 
  
## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a><span data-ttu-id="363ba-122">當有人轉寄電子郵件，會發生什麼事包含附件？</span><span class="sxs-lookup"><span data-stu-id="363ba-122">What happens when someone forwards an email that contains an attachment?</span></span>

<span data-ttu-id="363ba-123">假設組織會使用動態傳遞其[ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)中，而人員會收到包含附件的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="363ba-123">Suppose that an organization is using Dynamic Delivery for their [ATP Safe Attachments policy](set-up-atp-safe-attachments-policies.md), and someone receives an email that contains an attachment.</span></span> <span data-ttu-id="363ba-124">現在假設該人員將電子郵件轉寄給其他人。</span><span class="sxs-lookup"><span data-stu-id="363ba-124">Now suppose that person forwards the email message to someone else.</span></span> <span data-ttu-id="363ba-125">會發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="363ba-125">What happens?</span></span> <span data-ttu-id="363ba-126">這取決於是否 ATP 安全附件原則中隨附的其他收件者。</span><span class="sxs-lookup"><span data-stu-id="363ba-126">It depends on whether the additional recipients are included in ATP Safe Attachments policies.</span></span>
  
- <span data-ttu-id="363ba-127">如果收件者使用 [動態傳遞] 選項的 ATP 安全附件原則所涵蓋，收件者會看到版面配置區，來預覽相容檔案的能力。</span><span class="sxs-lookup"><span data-stu-id="363ba-127">If a recipient is covered by an ATP Safe Attachments policy using the Dynamic Delivery option, then the recipient sees the placeholder, with the ability to preview compatible files.</span></span>
    
- <span data-ttu-id="363ba-128">如果收件者未涵蓋的 ATP 安全附件原則，然後電子郵件和附件就會通過經歷，而不需要任何 ATP 安全附件掃描或附件版面配置區。</span><span class="sxs-lookup"><span data-stu-id="363ba-128">If a recipient is not covered by an ATP Safe Attachments policy, then the email and attachment will go through, without any ATP Safe Attachments scanning or attachment placeholders.</span></span>
    
## <a name="whats-required-for-dynamic-delivery-to-work"></a><span data-ttu-id="363ba-129">項目具有所需的動態傳遞至運作？</span><span class="sxs-lookup"><span data-stu-id="363ba-129">What's required for Dynamic Delivery to work?</span></span>

- <span data-ttu-id="363ba-130">您的組織必須有[Office 365 進階威脅防護](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="363ba-130">Your organization must have [Office 365 Advanced Threat Protection](office-365-atp.md)</span></span>
    
- <span data-ttu-id="363ba-131">您必須定義使用動態傳遞選項 （請參閱 < <b0>Set up Office 365 中的 ATP 安全附件原則</b0>） 的 ATP 安全附件原則</span><span class="sxs-lookup"><span data-stu-id="363ba-131">Policies must be defined for ATP Safe Attachments using the Dynamic Delivery option (See [Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md))</span></span>
    
- <span data-ttu-id="363ba-132">貴組織的電子郵件必須裝載於 Office 365。</span><span class="sxs-lookup"><span data-stu-id="363ba-132">Your organization's email must be hosted in Office 365.</span></span> <span data-ttu-id="363ba-133">雖然[Office 365 進階威脅防護可以搭配任何 SMTP 郵件傳輸代理程式](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#requirements-for-office-365-advanced-threat-protection-atp)（例如 Exchange Server)、 動態傳遞選項 ATP 安全附件會需要您組織的電子郵件裝載於 Office 365。</span><span class="sxs-lookup"><span data-stu-id="363ba-133">Although [Office 365 Advanced Threat Protection can be used with any SMTP mail transfer agent](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#requirements-for-office-365-advanced-threat-protection-atp) (such as Exchange Server), the Dynamic Delivery option for ATP Safe Attachments requires that your organization's email be hosted in Office 365.</span></span> <span data-ttu-id="363ba-134">如果您的電子郵件不架設在 Office 365 中，選擇不同的[ATP 安全附件原則] 選項](set-up-atp-safe-attachments-policies.md#step-3-learn-about-atp-safe-attachments-policy-options)，例如**區塊**。</span><span class="sxs-lookup"><span data-stu-id="363ba-134">If your email is not hosted in Office 365, choose a different [ATP Safe Attachments policy option](set-up-atp-safe-attachments-policies.md#step-3-learn-about-atp-safe-attachments-policy-options), such as **Block**.</span></span>
    
## <a name="additional-considerations"></a><span data-ttu-id="363ba-135">其他附註</span><span class="sxs-lookup"><span data-stu-id="363ba-135">Additional considerations</span></span>

<span data-ttu-id="363ba-136">有不支援動態傳遞是特定案例。</span><span class="sxs-lookup"><span data-stu-id="363ba-136">There are certain scenarios in which Dynamic Delivery is not supported.</span></span> <span data-ttu-id="363ba-137">包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="363ba-137">These include the following:</span></span>
  
- <span data-ttu-id="363ba-138">公用資料夾中的電子郵件</span><span class="sxs-lookup"><span data-stu-id="363ba-138">Email messages that are in public folders</span></span>
    
- <span data-ttu-id="363ba-139">且不會路由傳送的電子郵件，再重新到使用者的信箱使用自訂規則</span><span class="sxs-lookup"><span data-stu-id="363ba-139">Email messages that are routed out of and then back into the user's mailbox using custom rules</span></span>
    
- <span data-ttu-id="363ba-140">是 （自動或手動） 遭到託管信箱將及移到其他位置，包括封存資料夾的電子郵件</span><span class="sxs-lookup"><span data-stu-id="363ba-140">Email messages that are moved (automatically or manually) out of the hosted mailbox and into other locations, including archive folders</span></span>
    
- <span data-ttu-id="363ba-141">會刪除的電子郵件</span><span class="sxs-lookup"><span data-stu-id="363ba-141">Email messages that are deleted</span></span>
    
- <span data-ttu-id="363ba-142">處於錯誤狀態的使用者的信箱搜尋資料夾</span><span class="sxs-lookup"><span data-stu-id="363ba-142">A user's mailbox search folder that is in an error state</span></span>
    
- <span data-ttu-id="363ba-143">採用 Exchange Online 的系統管理員已啟用 Exclaimer 的環境。</span><span class="sxs-lookup"><span data-stu-id="363ba-143">Environments in which an Exchange Online admin has enabled Exclaimer.</span></span> <span data-ttu-id="363ba-144">若要解決此問題，請參閱[時所使用 ATP 動態傳遞和 Exclaimer 含附件的郵件未傳送](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)</span><span class="sxs-lookup"><span data-stu-id="363ba-144">To resolve this, see [Messages with attachments are not delivered when ATP Dynamic Delivery and Exclaimer are used](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)</span></span>

- <span data-ttu-id="363ba-145">使用[安全/多用途網際網路郵件延伸 (S/MIME)](s-mime-for-message-signing-and-encryption.md)加密的郵件）</span><span class="sxs-lookup"><span data-stu-id="363ba-145">Messages encrypted with [Secure/Multipurpose Internet Mail Extensions (S/MIME)](s-mime-for-message-signing-and-encryption.md))</span></span>

- <span data-ttu-id="363ba-146">在動態傳遞不受支援所在的情況下，ATP 安全附件會掃描電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="363ba-146">In cases where Dynamic Delivery is not supported, ATP Safe Attachments will not scan email messages.</span></span> <span data-ttu-id="363ba-147">不過，傳遞電子郵件訊息附件包含 Url 就會檢查，根據您的[ATP 安全連結原則](set-up-atp-safe-links-policies.md)設定的方式。</span><span class="sxs-lookup"><span data-stu-id="363ba-147">However, delivering email messages with attachments that contain URLs will be checked, depending on how your [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured.</span></span> <span data-ttu-id="363ba-148">在這些情況下，就會檢查電子郵件和 Office 檔案中的 Url。</span><span class="sxs-lookup"><span data-stu-id="363ba-148">In these cases, URLs in email messages and Office files are checked.</span></span>
