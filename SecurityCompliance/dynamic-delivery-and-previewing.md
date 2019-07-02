---
title: 使用 Office 365 ATP 安全附件的動態傳遞和預覽
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 04/19/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
ms.collection:
- M365-security-compliance
description: 當您設定 ATP 安全附件原則時, 您可以選擇 [動態傳遞] 以避免郵件延遲, 並讓使用者預覽所掃描的附件。
ms.openlocfilehash: 5d04593dd0884b21deefc202485aee27f60d1a5f
ms.sourcegitcommit: 0d5a863f48914eeaaf29f7d2a2022618de186247
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2019
ms.locfileid: "34077829"
---
# <a name="dynamic-delivery-and-previewing-with-office-365-atp-safe-attachments"></a><span data-ttu-id="bf400-103">使用 Office 365 ATP 安全附件的動態傳遞和預覽</span><span class="sxs-lookup"><span data-stu-id="bf400-103">Dynamic Delivery and previewing with Office 365 ATP Safe Attachments</span></span>

## <a name="overview"></a><span data-ttu-id="bf400-104">概觀</span><span class="sxs-lookup"><span data-stu-id="bf400-104">Overview</span></span>

<span data-ttu-id="bf400-105">[動態傳遞] 是可為[ATP 安全附件](atp-safe-attachments.md)選取的選項。</span><span class="sxs-lookup"><span data-stu-id="bf400-105">Dynamic Delivery is an option that can be selected for [ATP Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="bf400-106">請閱讀本文以瞭解[Office 365 中的 ATP 安全附件](atp-safe-attachments.md)中的動態傳遞和附件預覽功能。</span><span class="sxs-lookup"><span data-stu-id="bf400-106">Read this article to learn about Dynamic Delivery and attachment preview capabilities in [ATP Safe Attachments in Office 365](atp-safe-attachments.md).</span></span>

<span data-ttu-id="bf400-107">為您的組織[設定 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)時, 有數個選項可讓您處理電子郵件附件。</span><span class="sxs-lookup"><span data-stu-id="bf400-107">When [ATP Safe Attachments policies are set up](set-up-atp-safe-attachments-policies.md) for your organization, there are several options for how email attachments are handled.</span></span> <span data-ttu-id="bf400-108">其中包括**區塊**、**取代**和**動態傳遞**。</span><span class="sxs-lookup"><span data-stu-id="bf400-108">These include **Block**, **Replace**, and **Dynamic Delivery**.</span></span> <span data-ttu-id="bf400-109">根據如何設定 ATP 安全附件原則, 電子郵件收件者可能會在掃描附件時, 在電子郵件傳遞期間遇到輕微延遲。</span><span class="sxs-lookup"><span data-stu-id="bf400-109">Depending on how ATP Safe Attachments policies are configured, email recipients might experience a minor delay in email delivery while their attachments are scanned.</span></span> <span data-ttu-id="bf400-110">若要避免郵件延遲, 請選擇 [**動態傳遞**]。</span><span class="sxs-lookup"><span data-stu-id="bf400-110">To avoid message delays, choose **Dynamic Delivery**.</span></span>
  
## <a name="how-dynamic-delivery-works"></a><span data-ttu-id="bf400-111">動態傳遞的運作方式</span><span class="sxs-lookup"><span data-stu-id="bf400-111">How Dynamic Delivery works</span></span>
  
<span data-ttu-id="bf400-112">動態傳遞會將電子郵件的本文與每個電子郵件附件的預留位置傳送給收件者, 以避免電子郵件延遲。</span><span class="sxs-lookup"><span data-stu-id="bf400-112">Dynamic Delivery eliminates email delays by sending the body of an email message through to the recipient with a placeholder for each email attachment.</span></span> <span data-ttu-id="bf400-113">在掃描附件的複本之前, 會保留預留位置, 並將其判定為安全的[ATP 安全附件](atp-safe-attachments.md)。</span><span class="sxs-lookup"><span data-stu-id="bf400-113">The placeholder remains until a copy of the attachment is scanned and determined to be safe by [ATP Safe Attachments](atp-safe-attachments.md).</span></span> 

- <span data-ttu-id="bf400-114">一旦清除每個附件, 就可以開啟或下載。</span><span class="sxs-lookup"><span data-stu-id="bf400-114">As each attachment is cleared, it is available to open or download.</span></span> 

- <span data-ttu-id="bf400-115">如果將附件決定為惡意, 則會將其傳送至隔離區, 您組織的安全小組 (例如 Office 365 全域管理員或安全性系統管理員) 可以在[office 365 中管理隔離的郵件](manage-quarantined-messages-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="bf400-115">If an attachment is determined to be malicious, it is sent to quarantine, where someone on your organization's security team (such as an Office 365 global administrator or security administrator) can [manage quarantined messages in Office 365](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="bf400-116">大部分的 Pdf 和 Office 檔都可以在安全模式中預覽, 同時進行 ATP 掃描。</span><span class="sxs-lookup"><span data-stu-id="bf400-116">Most PDFs and Office documents can be previewed in safe mode while ATP scanning is underway.</span></span> <span data-ttu-id="bf400-117">如果附件與動態傳遞預覽程式不相容, 則電子郵件收件者會看到附件預留位置, 直到已完成 ATP 安全附件掃描。</span><span class="sxs-lookup"><span data-stu-id="bf400-117">If an attachment is not compatible with the Dynamic Delivery previewer, email recipients see an attachment placeholder until ATP Safe Attachments scanning is complete.</span></span>

> [!TIP]
> <span data-ttu-id="bf400-118">如果您使用的是行動裝置, 且 Pdf 不是先在動態傳遞預覽程式中轉譯, 請嘗試使用行動裝置瀏覽器登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="bf400-118">If you're using a mobile device, and PDFs are not rendering in Dynamic Delivery previewer at first, try signing into Office 365 using your mobile browser.</span></span>

<span data-ttu-id="bf400-119">透過動態傳遞, 使用者可以立即讀取和回復電子郵件, 同時也會分析其附件。</span><span class="sxs-lookup"><span data-stu-id="bf400-119">With Dynamic Delivery, people can read and respond to their email messages right away, while their attachments are being analyzed.</span></span> 

<span data-ttu-id="bf400-120">ATP 安全附件掃描會在您的 Office 365 資料所在的同一個區域中進行。</span><span class="sxs-lookup"><span data-stu-id="bf400-120">ATP Safe Attachments scanning takes place in the same region where your Office 365 data resides.</span></span> <span data-ttu-id="bf400-121">如需資料中心地理位置的詳細資訊, 請參閱[您的資料位於何處？](https://products.office.com/where-is-your-data-located?geo=All)</span><span class="sxs-lookup"><span data-stu-id="bf400-121">For more information about data center geography, see [Where is your data located?](https://products.office.com/where-is-your-data-located?geo=All)</span></span> 
  
## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a><span data-ttu-id="bf400-122">當某人轉寄包含附件的電子郵件時會發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="bf400-122">What happens when someone forwards an email that contains an attachment?</span></span>

<span data-ttu-id="bf400-123">假設組織使用的是其[ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)的動態傳遞, 而某人收到包含附件的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="bf400-123">Suppose that an organization is using Dynamic Delivery for their [ATP Safe Attachments policy](set-up-atp-safe-attachments-policies.md), and someone receives an email that contains an attachment.</span></span> <span data-ttu-id="bf400-124">現在假設人員將電子郵件轉寄給其他人。</span><span class="sxs-lookup"><span data-stu-id="bf400-124">Now suppose that person forwards the email message to someone else.</span></span> <span data-ttu-id="bf400-125">會發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="bf400-125">What happens?</span></span> <span data-ttu-id="bf400-126">這取決於是否在 ATP 安全附件原則中包含其他收件者。</span><span class="sxs-lookup"><span data-stu-id="bf400-126">It depends on whether the additional recipients are included in ATP Safe Attachments policies.</span></span>
  
- <span data-ttu-id="bf400-127">如果使用動態傳遞選項的 ATP 安全附件原則所涵蓋的收件者, 則收件者會看到該預留位置, 並具備預覽相容檔案的能力。</span><span class="sxs-lookup"><span data-stu-id="bf400-127">If a recipient is covered by an ATP Safe Attachments policy using the Dynamic Delivery option, then the recipient sees the placeholder, with the ability to preview compatible files.</span></span>
    
- <span data-ttu-id="bf400-128">如果不是 ATP 安全附件原則所涵蓋的收件者, 則電子郵件和附件會經過, 不含任何 ATP 安全附件掃描或附件預留位置。</span><span class="sxs-lookup"><span data-stu-id="bf400-128">If a recipient is not covered by an ATP Safe Attachments policy, then the email and attachment will go through, without any ATP Safe Attachments scanning or attachment placeholders.</span></span>
    
## <a name="whats-required-for-dynamic-delivery-to-work"></a><span data-ttu-id="bf400-129">進行動態傳遞所需的作業為何？</span><span class="sxs-lookup"><span data-stu-id="bf400-129">What's required for Dynamic Delivery to work?</span></span>

- <span data-ttu-id="bf400-130">您的組織必須有[Office 365 高級威脅防護](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="bf400-130">Your organization must have [Office 365 Advanced Threat Protection](office-365-atp.md)</span></span>
    
- <span data-ttu-id="bf400-131">您必須使用動態傳遞選項來定義 ATP 安全附件的原則 (請參閱[在 Office 365 中設定 Atp 安全附件原則](set-up-atp-safe-attachments-policies.md))</span><span class="sxs-lookup"><span data-stu-id="bf400-131">Policies must be defined for ATP Safe Attachments using the Dynamic Delivery option (See [Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md))</span></span>
    
- <span data-ttu-id="bf400-132">您組織的電子郵件必須主控于 Office 365。</span><span class="sxs-lookup"><span data-stu-id="bf400-132">Your organization's email must be hosted in Office 365.</span></span> <span data-ttu-id="bf400-133">雖然[office 365 的高級威脅防護可以搭配任何 SMTP 郵件傳輸代理程式使用](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#requirements-for-office-365-advanced-threat-protection-atp)(例如 Exchange Server), 但 ATP 安全附件的動態傳遞選項需要組織的電子郵件位於 Office 365。</span><span class="sxs-lookup"><span data-stu-id="bf400-133">Although [Office 365 Advanced Threat Protection can be used with any SMTP mail transfer agent](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#requirements-for-office-365-advanced-threat-protection-atp) (such as Exchange Server), the Dynamic Delivery option for ATP Safe Attachments requires that your organization's email be hosted in Office 365.</span></span> <span data-ttu-id="bf400-134">如果您的電子郵件不是在 Office 365 中主控, 請選擇不同的[ATP 安全附件原則選項](set-up-atp-safe-attachments-policies.md#step-3-learn-about-atp-safe-attachments-policy-options), 例如**區塊**。</span><span class="sxs-lookup"><span data-stu-id="bf400-134">If your email is not hosted in Office 365, choose a different [ATP Safe Attachments policy option](set-up-atp-safe-attachments-policies.md#step-3-learn-about-atp-safe-attachments-policy-options), such as **Block**.</span></span>
    
## <a name="additional-considerations"></a><span data-ttu-id="bf400-135">其他附註</span><span class="sxs-lookup"><span data-stu-id="bf400-135">Additional considerations</span></span>

<span data-ttu-id="bf400-136">在某些情況下, 不支援動態傳遞。</span><span class="sxs-lookup"><span data-stu-id="bf400-136">There are certain scenarios in which Dynamic Delivery is not supported.</span></span> <span data-ttu-id="bf400-137">包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="bf400-137">These include the following:</span></span>
  
- <span data-ttu-id="bf400-138">公用資料夾中的電子郵件</span><span class="sxs-lookup"><span data-stu-id="bf400-138">Email messages that are in public folders</span></span>
    
- <span data-ttu-id="bf400-139">使用自訂規則, 然後再移至使用者信箱的電子郵件</span><span class="sxs-lookup"><span data-stu-id="bf400-139">Email messages that are routed out of and then back into the user's mailbox using custom rules</span></span>
    
- <span data-ttu-id="bf400-140">移動 (自動或手動) 從裝載的信箱移至其他位置 (包括封存資料夾) 的電子郵件訊息</span><span class="sxs-lookup"><span data-stu-id="bf400-140">Email messages that are moved (automatically or manually) out of the hosted mailbox and into other locations, including archive folders</span></span>
    
- <span data-ttu-id="bf400-141">已刪除的電子郵件</span><span class="sxs-lookup"><span data-stu-id="bf400-141">Email messages that are deleted</span></span>
    
- <span data-ttu-id="bf400-142">處於錯誤狀態的使用者信箱搜尋資料夾</span><span class="sxs-lookup"><span data-stu-id="bf400-142">A user's mailbox search folder that is in an error state</span></span>
    
- <span data-ttu-id="bf400-143">Exchange Online 系統管理員已啟用 Exclaimer 的環境。</span><span class="sxs-lookup"><span data-stu-id="bf400-143">Environments in which an Exchange Online admin has enabled Exclaimer.</span></span> <span data-ttu-id="bf400-144">若要解決此問題, 請參閱[使用 ATP 動態傳遞和 Exclaimer 時, 不會傳遞含有附件的郵件](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)</span><span class="sxs-lookup"><span data-stu-id="bf400-144">To resolve this, see [Messages with attachments are not delivered when ATP Dynamic Delivery and Exclaimer are used](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)</span></span>

- <span data-ttu-id="bf400-145">使用[安全/多用途網際網路郵件延伸 (S/MIME)](s-mime-for-message-signing-and-encryption.md)加密的郵件</span><span class="sxs-lookup"><span data-stu-id="bf400-145">Messages encrypted with [Secure/Multipurpose Internet Mail Extensions (S/MIME)](s-mime-for-message-signing-and-encryption.md))</span></span>

- <span data-ttu-id="bf400-146">在不支援動態傳遞的情況下, ATP 安全附件將不會掃描電子郵件。</span><span class="sxs-lookup"><span data-stu-id="bf400-146">In cases where Dynamic Delivery is not supported, ATP Safe Attachments will not scan email messages.</span></span> <span data-ttu-id="bf400-147">不過, 根據您的[ATP 安全連結原則](set-up-atp-safe-links-policies.md)的設定方式, 會檢查傳送包含 url 附件的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="bf400-147">However, delivering email messages with attachments that contain URLs will be checked, depending on how your [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured.</span></span> <span data-ttu-id="bf400-148">在這些情況下, 會檢查電子郵件訊息和 Office 檔案中的 Url。</span><span class="sxs-lookup"><span data-stu-id="bf400-148">In these cases, URLs in email messages and Office files are checked.</span></span>
