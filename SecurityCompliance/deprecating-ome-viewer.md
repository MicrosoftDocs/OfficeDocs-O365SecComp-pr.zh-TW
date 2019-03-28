---
title: 不再 Office 365 郵件加密檢視器應用程式
ms.author: krowley
author: kccross
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6336cabb-b06e-402f-9e85-8bb9eb4ce68f
ms.collection:
- M365-security-compliance
description: 2018 年 8 月 15 日，我們將會被移除的 Office 365 郵件加密 (OME) 檢視器行動應用程式 Android 和 Apple 存放區。 Office 365 郵件加密 Viewer 行動應用程式已讀取電子郵件和附件已加密與 OME Apple 和 Android 手機上的先前版本所需。 不同於移除 OME 檢視器應用程式，我們不會進行任何變更為 OME 的舊版本。
ms.openlocfilehash: 0aa8ef0f2610284c1e897290c3f337804d78185b
ms.sourcegitcommit: 8a65a29aa3bfe5dcad0ff152a7cd795e02877dd9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/28/2019
ms.locfileid: "30936673"
---
# <a name="deprecating-office-365-message-encryption-viewer-app"></a><span data-ttu-id="7792d-105">不再 Office 365 郵件加密檢視器應用程式</span><span class="sxs-lookup"><span data-stu-id="7792d-105">Deprecating Office 365 Message Encryption Viewer App</span></span>

<span data-ttu-id="7792d-106">2018 年 8 月 15 日，我們將會被移除的 Office 365 郵件加密 (OME) 檢視器行動應用程式 Android 和 Apple 存放區。</span><span class="sxs-lookup"><span data-stu-id="7792d-106">On August 15, 2018, we will be removing the Office 365 Message Encryption (OME) Viewer mobile app from Android and Apple stores.</span></span> <span data-ttu-id="7792d-107">Office 365 郵件加密 Viewer 行動應用程式已讀取電子郵件和附件已加密與 OME Apple 和 Android 手機上的先前版本所需。</span><span class="sxs-lookup"><span data-stu-id="7792d-107">The Office 365 Message Encryption Viewer mobile app was required to read email messages and attachments that were encrypted with the previous version of OME on Apple and Android phones.</span></span> <span data-ttu-id="7792d-108">不同於移除 OME 檢視器應用程式，我們不會進行任何變更為 OME 的舊版本。</span><span class="sxs-lookup"><span data-stu-id="7792d-108">Apart from removing the OME Viewer app, we are not making any other changes to the previous version of OME.</span></span>
  
## <a name="changes-beginning-august-2018"></a><span data-ttu-id="7792d-109">開始 2018 年 8 月的變更</span><span class="sxs-lookup"><span data-stu-id="7792d-109">Changes beginning August 2018</span></span>

<span data-ttu-id="7792d-110">為宣佈最後一年 9 月，我們已發行新版本的[Office 365 郵件加密](https://aka.ms/ome2017)，讓使用者可以傳送加密和保護給任何人的行動應用程式的需求而組織內部或外部的郵件。</span><span class="sxs-lookup"><span data-stu-id="7792d-110">As announced last September, we have released a new version of [Office 365 Message Encryption](https://aka.ms/ome2017) so that users can send encrypted and protected messages to anyone inside or outside the organization without the requirement of the mobile app.</span></span> <span data-ttu-id="7792d-111">此後，我們已新增額外的功能：</span><span class="sxs-lookup"><span data-stu-id="7792d-111">Since then, we've added additional capabilities:</span></span> 
  
- [<span data-ttu-id="7792d-112">僅加密的範本</span><span class="sxs-lookup"><span data-stu-id="7792d-112">Encrypt-only template</span></span>](https://aka.ms/encryptonly)
    
- [<span data-ttu-id="7792d-113">解密附件控制項</span><span class="sxs-lookup"><span data-stu-id="7792d-113">Control to decrypt attachments</span></span>](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Admin-control-for-attachments-now-available-in-Office-365/ba-p/204007)
    
<span data-ttu-id="7792d-114">使用這項變更，使用者將無法再能夠下載 Office 365 郵件加密 Viewer 行動應用程式開始年 8 月 1。</span><span class="sxs-lookup"><span data-stu-id="7792d-114">With this change, users will no longer be able to download the Office 365 Message Encryption Viewer mobile app beginning August 1.</span></span> <span data-ttu-id="7792d-115">如此一來，郵件收件者可能無法讀取舊版 OME 某些 Android 和 Apple 行動裝置上使用加密的郵件。</span><span class="sxs-lookup"><span data-stu-id="7792d-115">As a result, mail recipients may not be able to read messages encrypted with the previous version of OME on some Android and Apple mobile devices.</span></span> <span data-ttu-id="7792d-116">不過，他們仍然能夠讀取這些郵件 （透過桌面瀏覽器） 的個人電腦上。</span><span class="sxs-lookup"><span data-stu-id="7792d-116">However, they will still be able to read these messages on personal computers (via desktop browsers).</span></span> <span data-ttu-id="7792d-117">已經下載應用程式的使用者仍無法使用它。</span><span class="sxs-lookup"><span data-stu-id="7792d-117">Users who have already downloaded the app will continue to be able to use it.</span></span>
  
## <a name="why-this-change-was-made"></a><span data-ttu-id="7792d-118">為什麼要進行這項變更</span><span class="sxs-lookup"><span data-stu-id="7792d-118">Why this change was made</span></span>

<span data-ttu-id="7792d-119">新版本的 OME 不再需要讀取受保護的電子郵件訊息和附件的行動應用程式。</span><span class="sxs-lookup"><span data-stu-id="7792d-119">The new version of OME no longer requires a mobile app to read protected email messages and attachments.</span></span> <span data-ttu-id="7792d-120">Office 365 客戶使用新的 OME 功能可以檢視受保護的郵件在 Outlook mobile 中和非 Office 365 客戶可以檢視受保護的瀏覽器中的訊息。</span><span class="sxs-lookup"><span data-stu-id="7792d-120">Office 365 customers using the new OME capabilities can view the protected message in Outlook mobile and non-Office 365 customers can view protected messages in a browser.</span></span>
  
<span data-ttu-id="7792d-121">需要使用者下載行動應用程式是另一個障礙的客戶來檢視受保護的郵件。</span><span class="sxs-lookup"><span data-stu-id="7792d-121">Requiring users to download a mobile app is another hurdle for customers to view protected messages.</span></span> <span data-ttu-id="7792d-122">新的 Office 365 郵件加密功能提供較佳的行動經驗。</span><span class="sxs-lookup"><span data-stu-id="7792d-122">The new Office 365 Message Encryption capabilities provide a better mobile experience.</span></span>
  
## <a name="can-i-still-use-the-previous-version-of-office-365-message-encryption"></a><span data-ttu-id="7792d-123">仍然可以使用舊版的 Office 365 郵件加密</span><span class="sxs-lookup"><span data-stu-id="7792d-123">Can I still use the previous version of Office 365 Message Encryption</span></span>

<span data-ttu-id="7792d-124">舊版的 Office 365 郵件加密將不會過時現階段，不過，我們做了重大的改進新版本的 Office 365 郵件加密，這讓您更容易加密和保護機密資料給任何人的權限和在任何裝置-包括讀取受保護的郵件直接在 Outlook 中的 Office 365 使用者的功能 (桌面、 行動電話和 web)。</span><span class="sxs-lookup"><span data-stu-id="7792d-124">The previous version of Office 365 Message Encryption will not be deprecated at this time, however, we have made significant enhancements to the new version of Office 365 Message Encryption, which make it easier to encrypt and rights protect sensitive data to anyone and on any device - including the ability for Office 365 users to read protected messages directly in Outlook (desktop, mobile, and web).</span></span> 
  
## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a><span data-ttu-id="7792d-125">需要什麼準備，這項變更</span><span class="sxs-lookup"><span data-stu-id="7792d-125">What do I need to do to prepare for this change</span></span>

<span data-ttu-id="7792d-126">如果您的組織目前傳送給收件者需要 OME 檢視器應用程式的加密的附件，您應該更新文件和訓練資源。</span><span class="sxs-lookup"><span data-stu-id="7792d-126">If your organization currently sends encrypted attachments to recipients that require the OME Viewer app, you should update your documentation and training resources.</span></span>
  
<span data-ttu-id="7792d-127">我們建議您更新現有 Exchange 郵件流程規則，來使用 OME 的目前版本，讓您的組織可以利用新增和改善功能。</span><span class="sxs-lookup"><span data-stu-id="7792d-127">We recommend updating existing Exchange mail flow rules to use the current version of OME so that your organization can take advantage of the new and improved capabilities.</span></span> <span data-ttu-id="7792d-128">一旦您已設定全新的 OME 功能，收件者不需要以讀取加密的郵件在行動裝置上 OME 檢視器應用程式。</span><span class="sxs-lookup"><span data-stu-id="7792d-128">Once you have set up the new OME capabilities, recipients won't need the OME Viewer app to read encrypted messages on mobile devices.</span></span>
  
<span data-ttu-id="7792d-129">Microsoft 建議您先將移至全新的 OME 功能，只要是合理的貴組織的計劃。</span><span class="sxs-lookup"><span data-stu-id="7792d-129">Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization.</span></span> <span data-ttu-id="7792d-130">如需相關指示，請參閱 <<c0>設定新的 Office 365 郵件加密功能。</span><span class="sxs-lookup"><span data-stu-id="7792d-130">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="7792d-131">如果您想要深入了解新功能的運作方式第一次，請參閱[Office 365 郵件加密](ome.md)。</span><span class="sxs-lookup"><span data-stu-id="7792d-131">If you want to find out more about how the new capabilities work first, see [Office 365 Message Encryption](ome.md).</span></span>
  

