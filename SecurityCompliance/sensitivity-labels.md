---
title: 敏感度標籤概觀
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 使用敏感度標籤，您可以分類並協助保護敏感內容，同時確保人員的生產力與共同作業能力不會受到阻礙。您可以使用敏感度標籤在標記的內容上強制執行保護設定，例如加密或浮水印。
ms.openlocfilehash: ce05fe8062cb0f651edc74101b11877c091eb6fb
ms.sourcegitcommit: fd3db13cd4fc71cd2cb164fd702007acba3e7399
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/04/2019
ms.locfileid: "36717703"
---
# <a name="overview-of-sensitivity-labels"></a><span data-ttu-id="b0406-104">敏感度標籤概觀</span><span class="sxs-lookup"><span data-stu-id="b0406-104">Overview of sensitivity labels</span></span>

<span data-ttu-id="b0406-p102">若要完成工作，組織中的人員需要與組織內外的其他人員共同合作。這表示內容不總是在防火牆後，它會漫遊在裝置、應用程式和服務的各處。您希望內容以安全、受保護的方式漫遊，以符合組織的商務及法規遵循原則。</span><span class="sxs-lookup"><span data-stu-id="b0406-p102">To get their work done, people in your organization need to collaborate with others both inside and outside the organization. This means that content no longer stays behind a firewall – it roams everywhere, across devices, apps, and services. And when it roams, you want it to do so in a secure, protected way that meets your organization’s business and compliance policies.</span></span>

<span data-ttu-id="b0406-108">使用敏感度標籤，您可以分類並協助保護敏感內容，同時確保人員的生產力與共同作業能力不會受到阻礙。</span><span class="sxs-lookup"><span data-stu-id="b0406-108">With sensitivity labels, you can classify and help protect your sensitive content, while making sure that your people’s productivity and ability to collaborate isn’t hindered.</span></span>

![Excel 功能區和狀態列上的敏感度標籤](media/Sensitivity-label-in-Excel.png)

<span data-ttu-id="b0406-110">您可以使用敏感度標籤來：</span><span class="sxs-lookup"><span data-stu-id="b0406-110">You can use sensitivity labels to:</span></span>
  
- <span data-ttu-id="b0406-p103">**在標記的內容上強制執行保護設定，例如加密或浮水印。** 例如，使用者可以將「機密」標籤套用至文件或電子郵件，該標籤即可加密內容，並套用「機密」浮水印。</span><span class="sxs-lookup"><span data-stu-id="b0406-p103">**Enforce protection settings such as encryption or watermarks on labeled content.** For example, your users can apply a Confidential label to a document or email, and that label can encrypt the content and apply a Confidential watermark.</span></span>    

- <span data-ttu-id="b0406-p104">**在不同平台和裝置上保護 Office 應用程式中的內容。** 敏感度標籤可在 Windows、Mac、iOS 和 Android 的 Office 應用程式中使用。即將推出 Office Web 應用程式的支援。</span><span class="sxs-lookup"><span data-stu-id="b0406-p104">**Protect content in Office apps across different platforms and devices.** Sensitivity labels work in Office apps on Windows, Mac, iOS, and Android. Support for Office web apps is coming soon.</span></span>
    
- <span data-ttu-id="b0406-p105">**防止敏感內容離開組織執行 Windows 的裝置**，方式是使用 Microsoft Intune 的端點保護。敏感度標籤套用至位於 Windows 裝置上的內容後，端點保護可以防止該內容複製到協力廠商應用程式，例如 Twitter 或 Gmail，或複製到卸除式儲存空間，如 USB 磁碟機。</span><span class="sxs-lookup"><span data-stu-id="b0406-p105">**Prevent sensitive content from leaving your organization on devices running Windows**, by using endpoint protection in Microsoft Intune. After a sensitivity label has been applied to content that resides on a Windows device, endpoint protection can prevent that content from being copied to a third-party app, such as Twitter or Gmail, or being copied to removable storage, such as a USB drive.</span></span>

- <span data-ttu-id="b0406-118">**使用 Microsoft Cloud App Security 保護協力廠商應用程式和服務中的內容。**</span><span class="sxs-lookup"><span data-stu-id="b0406-118">**Protect content in third-party apps and services**, by using Microsoft Cloud App Security.</span></span> <span data-ttu-id="b0406-119">使用 Cloud App Security，您可以偵測、分類、標記並保護協力廠商應用程式和服務中的內容，例如 SalesForce、Box 或 DropBox，即使協力廠商應用程式或服務無法讀取或支援敏感度標籤亦然。</span><span class="sxs-lookup"><span data-stu-id="b0406-119">With Cloud App Security, you can detect, classify, label, and protect content in third-party apps and services, such as SalesForce, Box, or DropBox, even if the third-party app or service does not read or support sensitivity labels.</span></span>

- <span data-ttu-id="b0406-p107">**將敏感度標籤擴充至協力廠商應用程式和服務。** 使用 Microsoft 資訊保護 SDK，Windows、Mac 和 Linux 上的協力廠商應用程式可以讀取敏感度標籤，並且套用保護設定。iOS 和 Android 應用程式的支援即將推出。</span><span class="sxs-lookup"><span data-stu-id="b0406-p107">**Extend sensitivity labels to third-party apps and services.** With the Microsoft Information Protection SDK, third-party apps on Windows, Mac, and Linux can read sensitivity labels and apply protection settings. Support for apps on iOS and Android is coming soon.</span></span>

- <span data-ttu-id="b0406-p108">**將內容分類而不需使用任何保護設定。** 您只要將分類指派至內容 (就像貼紙)，分類就會在使用及共用內容時保留並跟隨內容。您可以使用此分類產生使用狀況報告，並查看敏感內容的活動資料。根據這項資訊，稍後您可以隨時選擇套用保護設定。</span><span class="sxs-lookup"><span data-stu-id="b0406-p108">**Classify content without using any protection settings.** You can also simply assign a classification to content (like a sticker) that persists and roams with the content as it's used and shared. You can use this classification to generate usage reports and see activity data for your sensitive content. Based on this information, you can always choose at a later time to apply protection settings.</span></span>
    
<span data-ttu-id="b0406-p109">在這些案例中，Office 365 中的敏感度標籤可以幫助您對正確的內容採取正確的動作。使用敏感度標籤，您可以分類整個組織中的資料，並根據該分類強制執行保護設定。</span><span class="sxs-lookup"><span data-stu-id="b0406-p109">In all of these cases, sensitivity labels in Office 365 can help you take the right actions on the right content. With sensitivity labels, you can classify data across your organization and enforce protection settings based on that classification.</span></span>
  
<span data-ttu-id="b0406-p110">您可以在 Microsoft 365 合規性中心、Microsoft 365 安全性中心，或 Office 365 安全性與合規性中心中建立敏感度標籤。Azure 資訊保護、Office App 和 Office 365 服務可以使用這些敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="b0406-p110">You create sensitivity labels in the Microsoft 365 compliance center, Microsoft 365 security center, or Office 365 Security & Compliance Center. These sensitivity labels can be used by Azure Information Protection, Office apps, and Office 365 services.</span></span>

<span data-ttu-id="b0406-131">針對 Azure 資訊保護客戶，您可以使用其他系統管理中心的 Azure 資訊保護標籤，而如果您選擇執行額外或進階組態，標籤就會與 Azure 入口網站同步處理。</span><span class="sxs-lookup"><span data-stu-id="b0406-131">For Azure Information Protection customers, you can use your Azure Information Protection labels in the other admin centers, and your labels will be synced with the Azure portal in case you choose to perform additional or advanced configuration.</span></span> <span data-ttu-id="b0406-132">**Azure 資訊保護標籤與 Office 365 敏感度標籤完全彼此相容。**</span><span class="sxs-lookup"><span data-stu-id="b0406-132">**Azure Information Protection labels and Office 365 sensitivity labels are fully compatible with each other.**</span></span> <span data-ttu-id="b0406-133">這表示，比方說，如果您有使用 Azure 資訊保護加上標籤的內容，則不需將內容重新分類或重新加上標籤。</span><span class="sxs-lookup"><span data-stu-id="b0406-133">This means, for example, if you have content labeled by Azure Information Protection, you won’t need to reclassify or relabel your content.</span></span>

## <a name="what-a-sensitivity-label-is"></a><span data-ttu-id="b0406-134">敏感度標籤是什麼</span><span class="sxs-lookup"><span data-stu-id="b0406-134">What a sensitivity label is</span></span>

<span data-ttu-id="b0406-135">當您將敏感度標籤指派至文件或電子郵件，它就像標記：</span><span class="sxs-lookup"><span data-stu-id="b0406-135">When you assign a sensitivity label to a document or email, it’s simply like a tag that is:</span></span>

- <span data-ttu-id="b0406-p112">**可自訂。** 您可以為組織中不同等級的敏感內容建立類別，例如個人、公用、一般、機密、高度機密。</span><span class="sxs-lookup"><span data-stu-id="b0406-p112">**Customizable.** You can create categories for different levels of sensitive content in your organization, such as Personal, Public, General, Confidential, and Highly Confidential.</span></span>

- <span data-ttu-id="b0406-p113">**純文字。** 因為標籤是純文字，協力廠商應用程式和服務可以套用保護措施至已標示的內容。</span><span class="sxs-lookup"><span data-stu-id="b0406-p113">**Clear text.** Because the label is in clear text, it’s available for third-party apps and services to apply protective actions to labeled content.</span></span>

- <span data-ttu-id="b0406-p114">**持續性。** 敏感度標籤套用至內容後，會保留在該電子郵件或文件的中繼資料內。這表示標籤會跟隨內容，包括保護設定，並成為套用和強制執行原則的基礎。</span><span class="sxs-lookup"><span data-stu-id="b0406-p114">**Persistent.** After a sensitivity label is applied to content, it persists in the metadata of that email or document. This means the label roams with the content, including the protection settings, and becomes the basis for applying and enforcing policies.</span></span>

<span data-ttu-id="b0406-143">在 Office 應用程式中，敏感度標籤在電子郵件或文件上只會顯示為標記。</span><span class="sxs-lookup"><span data-stu-id="b0406-143">In the Office apps, a sensitivity label simply appears as a tag on an email or document.</span></span>

<span data-ttu-id="b0406-p115">內容中的每個項目皆可套用單一敏感度標籤。但請注意，項目可以同時套用單一敏感度標籤和單一[保留標籤](labels.md)。</span><span class="sxs-lookup"><span data-stu-id="b0406-p115">Each item of content can have a single sensitivity label applied to it. But note that an item can have both a single sensitivity label and a single [retention label](labels.md) applied to it.</span></span>

![套用至電子郵件的敏感度標籤](media/Sensitivity-label-on-email.png)

## <a name="what-sensitivity-labels-can-do"></a><span data-ttu-id="b0406-147">敏感度標籤的功能</span><span class="sxs-lookup"><span data-stu-id="b0406-147">What sensitivity labels can do</span></span>

<span data-ttu-id="b0406-p116">敏感度標籤套用至電子郵件或文件後，會對內容強制執行該標籤的保護設定。使用敏感度標籤，您可以：</span><span class="sxs-lookup"><span data-stu-id="b0406-p116">After a sensitivity label is applied to an email or document, the protection settings for that label are enforced on the content. With a sensitivity label, you can:</span></span>

- <span data-ttu-id="b0406-p117">僅**加密**電子郵件，或同時加密電子郵件與文件。您可以選擇哪些使用者或群組擁有權限執行哪些動作和執行時間。比方說，您可以選擇讓組織外特定網域中的使用者僅在內容標示後的 7 天擁有權限檢閱內容。或者，您可以允許使用者在套用標籤時指派內容的權限，而不是由您指派權限。如需詳細資訊，請參閱[使用敏感度標籤中的加密來限制內容的存取](encryption-sensitivity-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="b0406-p117">**Encrypt** email only or both email and documents. You can choose which users or group have permissions to perform which actions and for how long. For example, you can choose to allow users in a specific domain outside your organization to have permissions to review the content for only 7 days after the content is labeled. For more information, see [Restrict access to content by using encryption in sensitivity labels](encryption-sensitivity-labels.md).</span></span>

- <span data-ttu-id="b0406-p118">**標記內容**的方法為在電子郵件或已套用標籤的文件上新增自訂浮水印、頁首或頁尾。請注意，浮水印僅適用於文件，不適用於電子郵件，並且限制為 255 個字元。此外，頁首和頁尾的限制為 1024 個字元 (除了在 Excel 中的限制為 255 個字元或更少，根據文件是否包含其他頁首或頁尾或其他因素而定。)</span><span class="sxs-lookup"><span data-stu-id="b0406-p118">**Mark the content** by adding custom watermarks, headers, or footers to email or documents that have the label applied. Note that watermarks are applied only to documents, not email, and they're limited to 255 characters. Also, headers and footers are limited to 1024 characters (except in Excel, where they're limited to 255 characters or fewer, depending on whether the document contains other headers or footers and other factors.)</span></span>

    ![套用至文件的浮水印和頁首](media/Sensitivity-label-watermark-header.png)

- <span data-ttu-id="b0406-p119">**防止資料遺失**，方法是在 Intune 中開啟端點保護。如果下載了敏感內容，您可協助防止 Windows 裝置的資料遺失。比方說，您無法將已標示的內容複製到 Dropbox、Gmail 或 USB 磁碟機。在敏感度標籤可使用 Windows 資訊保護 (WIP) 之前，您需要先在 Azure 入口網站中建立應用程式保護原則。如需詳細資訊，請參閱 [Windows 資訊保護如何保護具有敏感度標籤的檔案](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/how-wip-works-with-labels?branch=vsts17546553)。</span><span class="sxs-lookup"><span data-stu-id="b0406-p119">**Prevent data loss** by turning on endpoint protection in Intune. If sensitive content gets downloaded, you can help prevent the loss of data from Windows devices. For example, you can’t copy labeled content into Dropbox, Gmail, or USB drive. Before your sensitivity labels can use Windows Information Protection (WIP), you first need to create an app protection policy in the Azure portal. For more information, see [How Windows Information Protection protects files with a sensitivity label](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/how-wip-works-with-labels?branch=vsts17546553).</span></span>

- <span data-ttu-id="b0406-p120">**自動將標籤套用到包含敏感性資訊的內容。** 您可以選擇想要將標籤套用到哪些類型的敏感性資訊，以及自動套用標籤或您建議使用者套用標籤的提示。如果您有建議的標籤，提示會顯示您選擇的任何文字。如需詳細資訊，請參閱[自動將敏感度標籤套用到內容](apply-sensitivity-label-automatically.md)。</span><span class="sxs-lookup"><span data-stu-id="b0406-p120">**Apply the label automatically to content that contains sensitive information.** You can choose what types of sensitive information that you want labeled, and the label can either be applied automatically, or you can prompt users to apply the label that you recommend. If you recommend a label, the prompt displays whatever text you choose. For more information, see [Apply a sensitivity label to content automatically](apply-sensitivity-label-automatically.md).</span></span>

    ![指派必要標籤的提示](media/Sensitivity-label-Prompt-for-required-label.png)


<span data-ttu-id="b0406-169">在您建立敏感度標籤時，這所有選項都可供使用。</span><span class="sxs-lookup"><span data-stu-id="b0406-169">All of these options are available when you create a sensitivity label.</span></span>

![建立敏感度標籤的選項](media/Sensitivity-label-create-options.png)

### <a name="label-priority-order-matters"></a><span data-ttu-id="b0406-171">標籤優先順序 (順序很重要)</span><span class="sxs-lookup"><span data-stu-id="b0406-171">Label priority (order matters)</span></span>

<span data-ttu-id="b0406-172">建立敏感度標籤時，它們會顯示在 [標籤]\*\*\*\* 頁面的 [敏感度]\*\*\*\* 索引標籤上的清單中。</span><span class="sxs-lookup"><span data-stu-id="b0406-172">When you create your sensitivity labels, they appear in a list on the **Sensitivity** tab on the **Labels** page.</span></span> <span data-ttu-id="b0406-173">在此清單中，標籤的順序很重要，因為它反映的是其優先順序。</span><span class="sxs-lookup"><span data-stu-id="b0406-173">In this list, the order of the labels is important because it reflects their priority.</span></span> <span data-ttu-id="b0406-174">您想要讓最具限制性的敏感度標籤，例如 [高度機密性]，顯示在清單的最**底端**，以及最不具限制性的敏感度標籤，例如公用，顯示在最**上方**。</span><span class="sxs-lookup"><span data-stu-id="b0406-174">You want your most restrictive sensitivity label, such as Highly Confidential, to appear at the **bottom** of the list, and your least restrictive sensitivity label, such as Public, to appear at the **top**.</span></span>

<span data-ttu-id="b0406-p122">文件或電子郵件只能套用單一敏感度標籤。如果您要求使用者提供將標籤變更為較低分類的理由，這份清單的順序可決定什麼是較低的分類。</span><span class="sxs-lookup"><span data-stu-id="b0406-p122">A document or email can have only a single sensitivity label applied to it. If you require your users to provide a justification for changing the label to a lower classification, the order of this list determines what's a lower classification.</span></span>

![建立子標籤的選項](media/Sensitivity-label-sublabel-options.png)

<span data-ttu-id="b0406-178">請注意，除了標籤的優先順序，標籤原則的順序也很重要 - 請參閱[標籤原則優先順序 (順序很重要)](#label-policy-priority-order-matters)。</span><span class="sxs-lookup"><span data-stu-id="b0406-178">Note that in addition to label priority, the order of the label policies also matters - see [Label policy priority (order matters)](#label-policy-priority-order-matters).</span></span>

### <a name="sublabels-grouping-labels"></a><span data-ttu-id="b0406-179">子標籤 (分組標籤)</span><span class="sxs-lookup"><span data-stu-id="b0406-179">Sublabels (grouping labels)</span></span>

<span data-ttu-id="b0406-180">您可以使用子標籤將一或多個標籤分組在 Office 應用程式中的使用者可看到的上層標籤之下。</span><span class="sxs-lookup"><span data-stu-id="b0406-180">With sublabels, you can group one or more labels below a parent label that a user sees in an Office app.</span></span> <span data-ttu-id="b0406-181">例如，在 [機密文件] 下，您的組織可能會使用不同的標籤來標示該分類的特定類型。</span><span class="sxs-lookup"><span data-stu-id="b0406-181">For example, under Confidential, your organization might use several different labels for specific types of that classification.</span></span> <span data-ttu-id="b0406-182">在此範例中，上層標籤 [機密文件] 只是沒有任何保護設定的文字標籤，且因為它有子標籤，所以無法套用至內容。</span><span class="sxs-lookup"><span data-stu-id="b0406-182">In this example, the parent label Confidential is simply a text label with no protection settings, and because it has sublabels, it can’t be applied to content.</span></span> <span data-ttu-id="b0406-183">相反地，使用者必須選擇 [機密文件] 來查看子標籤，然後再選擇要套用到內容的子標籤。</span><span class="sxs-lookup"><span data-stu-id="b0406-183">Instead, users must choose Confidential to view the sublabels, and then they can choose a sublabel to apply to content.</span></span>

<span data-ttu-id="b0406-184">子標籤是以邏輯群組方式向使用者呈現標籤的一個簡單方式。</span><span class="sxs-lookup"><span data-stu-id="b0406-184">Sublabels are simply a way to present labels to users in logical groups.</span></span> <span data-ttu-id="b0406-185">子標籤不繼承其上層標籤的任何設定。</span><span class="sxs-lookup"><span data-stu-id="b0406-185">Sublabels don’t inherit any settings from their parent label.</span></span> <span data-ttu-id="b0406-186">子標籤可套用至內容；但上層標籤不行。</span><span class="sxs-lookup"><span data-stu-id="b0406-186">Sublabels can be applied to content; parent labels cannot.</span></span>

<span data-ttu-id="b0406-187">(此外，您不應選擇上層標籤作為預設標籤 (請參閱下一節)，或將上層標籤設定為自動套用或建議選項，因為上層標籤無法套用到使用 Azure 資訊保護統一標籤用戶端的 Office 應用程式中的內容。)</span><span class="sxs-lookup"><span data-stu-id="b0406-187">(Also, you should not choose a parent label as the default label (see next section), or configure a parent label to be auto-applied or recommended, because the parent label won't be applied to content in Office apps that use the Azure Information Protection unified labeling client.)</span></span>

![功能區上分組的子標籤](media/Sensitivity-label-grouped-labels.png)

### <a name="editing-or-deleting-a-sensitivity-label"></a><span data-ttu-id="b0406-189">編輯或刪除敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="b0406-189">Editing or deleting a sensitivity label</span></span>

<span data-ttu-id="b0406-190">如果您刪除敏感度標籤，請注意，標籤並未從內容中移除，且所有保護設定會繼續對內容強制執行。</span><span class="sxs-lookup"><span data-stu-id="b0406-190">If you delete a sensitivity label, note that the label is not removed from content, and any protection settings continue to be enforced on the content.</span></span>

<span data-ttu-id="b0406-191">如果您編輯敏感度標籤，則會對內容強制執行當初套用至內容的標籤版本。</span><span class="sxs-lookup"><span data-stu-id="b0406-191">If you edit a sensitivity label, the version of the label that was applied to content is what’s enforced on that content.</span></span>

## <a name="what-label-policies-can-do"></a><span data-ttu-id="b0406-192">標籤原則的功能</span><span class="sxs-lookup"><span data-stu-id="b0406-192">What label policies can do</span></span>

<span data-ttu-id="b0406-p125">建立敏感度標籤後，您需要發佈標籤，以供組織中的人員使用，這些人員可以接著將標籤套用至內容。與發佈到位置 (例如所有 Exchange 信箱) 的保留標籤不同，敏感度標籤會發佈給使用者或群組。敏感度標籤接著會為這些使用者和群組顯示在 Office 應用程式中。</span><span class="sxs-lookup"><span data-stu-id="b0406-p125">After you create your sensitivity labels, you need to publish them, to make them available to people in your organization, who can then apply the labels to content. Unlike retention labels, which are published to locations, such as all Exchange mailboxes, sensitivity labels are published to users or groups. Sensitivity labels then appear in Office apps for those users and groups.</span></span>

<span data-ttu-id="b0406-196">使用標籤原則，您可以：</span><span class="sxs-lookup"><span data-stu-id="b0406-196">With a label policy, you can:</span></span>

- <span data-ttu-id="b0406-p126">**選擇哪些使用者和群組可以看見標籤。** 標籤可以發佈到任何電子郵件啟用的安全性群組、通訊群組、Office 365 群組或動態通訊群組。</span><span class="sxs-lookup"><span data-stu-id="b0406-p126">**Choose which users and groups see the labels.** Labels can be published to any email-enabled security group, distribution group, Office 365 group, or dynamic distribution group.</span></span>

- <span data-ttu-id="b0406-p127">**套用預設標籤**至所有新文件和電子郵件，這些是由標籤原則中包含的使用者和群組所建立。此預設標籤可以設定您想要套用到所有內容的基礎層級保護設定。</span><span class="sxs-lookup"><span data-stu-id="b0406-p127">**Apply a default label** to all new documents and email created by the users and groups included in the label policy. This default label can set a base level of protection settings that you want applied to all your content.</span></span>

- <span data-ttu-id="b0406-p128">**變更標籤需要理由。** 如果內容標示為「機密」，而使用者想要移除該標籤，或取代為較低的分類，如「公用」標籤，則您可以要求使用者在執行此動作時提供理由。這些理由可供系統管理員檢閱。我們目前正在處理系統管理員可在其中檢視使用者理由的報告。</span><span class="sxs-lookup"><span data-stu-id="b0406-p128">**Require a justification for changing a label.** If content is marked Confidential and a user wants to remove that label or replace it with a lower classification, such as a label named Public, you can require that the user provide a justification when performing this action. These justifications will be available for the admin to review. We’re currently working on a report where admins can view the user justifications.</span></span>

    ![提示使用者輸入理由](media/Sensitivity-label-justification-required.png)

- <span data-ttu-id="b0406-p129">**要求使用者將標籤套用到他們的電子郵件和文件。** 如果您想要將所有使用者的內容套用標籤，您可以要求必須將標籤套用到所有已儲存的文件和傳送的電子郵件。基於自動或預設 (預設標籤選項如上所述) 指派的條件，使用者可以手動指派標籤。當使用者需要指派標籤時，Outlook 中會顯示提示。</span><span class="sxs-lookup"><span data-stu-id="b0406-p129">**Require users to apply a label to their email and documents.** If you want all of a user's content to be labeled, you can require that a label must be applied to all of their saved documents and sent emails. The label can be assigned manually by the user, automatically as a result of a condition, or be assigned by default (the default label option described above). Here's the prompt shown in Outlook when a user is required to assign a label.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b0406-p130">強制標籤功能需要有 Azure 資訊保護訂閱。若要使用此功能，您必須下載並安裝 [Azure 資訊保護用戶端](https://www.microsoft.com/download/details.aspx?id=53018)或更新的[ Azure 資訊保護統一標籤用戶端](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app)。我們正在努力在 Office 應用程式中提供此功能的原生支援，讓此功能不需要 Azure 資訊保護用戶端。此外，用戶端只能在 Windows 上執行，因此 Mac、iOS 和 Android 尚未支援此功能。</span><span class="sxs-lookup"><span data-stu-id="b0406-p130">Mandatory labeling requires an Azure Information Protection subscription. To use this feature, you must download and install either the [Azure Information Protection client](https://www.microsoft.com/download/details.aspx?id=53018) or the later [Azure Information Protection unified labeling client](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app). We're working on native support for this feature in Office apps, so that it won't require the Azure Information Protection client. Also, the client runs only on Windows, so this feature is not yet supported on Mac, iOS, and Android.</span></span>

    ![Outlook 中詢問使用者套用必要標籤的提示](media/sensitivity-labels-mandatory-prompt-aipv2-outlook.PNG)

- <span data-ttu-id="b0406-p131">**提供說明連結至自訂說明頁面。** 如果使用者不確定敏感度標籤代表的意義或使用方式，您可以提供「深入了解」URL，其顯示在 Office 應用程式中 [敏感度] 標籤功能表的底部。</span><span class="sxs-lookup"><span data-stu-id="b0406-p131">**Provide help link to a custom help page.** If your users aren’t sure what your sensitivity labels mean or how they should be used, you can provide a Learn More URL that appears at the bottom of the Sensitivity label menu in the Office apps.</span></span>

    ![功能區中 [敏感度] 按鈕上的「深入了解」連結](media/Sensitivity-label-learn-more.png)

<span data-ttu-id="b0406-218">建立標籤原則並將敏感度標籤指派給使用者和群組之後，這些人會在一小時內在 Office 應用程式中看到這些標籤。</span><span class="sxs-lookup"><span data-stu-id="b0406-218">After you create a label policy and assign sensitivity labels to users and groups, those people will see those labels available in the Office apps in an hour or less.</span></span>

### <a name="label-policy-priority-order-matters"></a><span data-ttu-id="b0406-219">標籤原則優先順序 (順序很重要)</span><span class="sxs-lookup"><span data-stu-id="b0406-219">Label priority (order matters)</span></span>

<span data-ttu-id="b0406-220">您會在敏感度標籤原則中發佈敏感度標籤，以將其提供給使用者使用，而標籤會顯示在 **[標籤原則]** 頁面上 **[敏感度原則]** 索引標籤的清單中。</span><span class="sxs-lookup"><span data-stu-id="b0406-220">You make your sensitivity labels available to users by publishing them in a sensitivity label policy, which appears in a list on the **Sensitivity policies** tab on the **Label policies** page.</span></span> <span data-ttu-id="b0406-221">正如同敏感度標籤 (請參閱上方的[標籤原則優先順序 (順序很重要)](#label-priority-order-matters)小節)，敏感度標籤原則的順序非常重要，因為順序反映的是優先順序。</span><span class="sxs-lookup"><span data-stu-id="b0406-221">Just like sensitivity labels (see the above section [Label priority (order matters)](#label-priority-order-matters)), the order of the sensitivity label policies is important because it reflects their priority.</span></span> <span data-ttu-id="b0406-222">優先順序最低的標籤原則會顯示在**上方**，而優先順序最高的標籤原則會顯示在**下方**。</span><span class="sxs-lookup"><span data-stu-id="b0406-222">The label policy with lowest priority is shown at the **top**, and label policy with the highest priority is shown at the **bottom**.</span></span>

<span data-ttu-id="b0406-223">標籤原則包含：</span><span class="sxs-lookup"><span data-stu-id="b0406-223">A label policy consists of:</span></span>

- <span data-ttu-id="b0406-224">一組標籤。</span><span class="sxs-lookup"><span data-stu-id="b0406-224">A set of modules.</span></span>
- <span data-ttu-id="b0406-225">標籤原則的範圍，表示原則中包含的使用者和群組。</span><span class="sxs-lookup"><span data-stu-id="b0406-225">The scope of the label policy, meaning the users and groups included in the policy.</span></span>
- <span data-ttu-id="b0406-226">以上所述標籤原則的設定 (預設標籤、對齊、強制標籤和說明連結)。</span><span class="sxs-lookup"><span data-stu-id="b0406-226">The settings of the label policy described above (default label, justification, mandatory label, and help link).</span></span>

<span data-ttu-id="b0406-227">您可以將使用者包含在多個標籤原則中，該使用者即會看到來自這些原則的所有敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="b0406-227">You can include a user in multiple label policies, and the user will see all of the sensitivity labels from those policies.</span></span> <span data-ttu-id="b0406-228">不過，使用者只會看到來自具有最高優先順序標籤原則的原則設定。</span><span class="sxs-lookup"><span data-stu-id="b0406-228">However, a user will see the policy settings from only the label policy with the highest priority.</span></span>

<span data-ttu-id="b0406-229">如果您的組織中的使用者或群組看不到您需要的標籤原則中的選項，例如預設標籤或強制標籤，請檢查敏感度標籤原則的順序。</span><span class="sxs-lookup"><span data-stu-id="b0406-229">If a user or group in your organization is not seeing an option in the label policy that you intended, such as a default or mandatory label, check the order of the sensitivity label policies.</span></span> <span data-ttu-id="b0406-230">若要重新排序標籤原則，請選取 [敏感度標籤原則 > 選擇右側的省略符號 > [下移]\*\*\*\* 或 [上移]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b0406-230">To re-order the label policies, select a sensitivity label policy > choose the ellipsis on the right > **Move down** or **Move up**.</span></span>

![敏感度標籤原則頁面上的移動選項](media/sensitivity-label-policy-priority.png)

<span data-ttu-id="b0406-232">請注意，雖然敏感度標籤原則的優先順序很重要，對保留標籤原則而言，它卻**不**重要。</span><span class="sxs-lookup"><span data-stu-id="b0406-232">Note that while priority matters for sensitivity label policies, it does **not** matter for retention label policies.</span></span> <span data-ttu-id="b0406-233">如[系統會優先處理保留原則嗎？](labels.md#the-principles-of-retention-or-what-takes-precedence)中所述，內容可能會受限於多個保留原則。</span><span class="sxs-lookup"><span data-stu-id="b0406-233">As explained in [The principles of retention, or what takes precedence?](labels.md#the-principles-of-retention-or-what-takes-precedence), content can be subject to multiple retention policies.</span></span>

## <a name="how-to-get-started"></a><span data-ttu-id="b0406-234">如何開始使用</span><span class="sxs-lookup"><span data-stu-id="b0406-234">How to get started</span></span>

<span data-ttu-id="b0406-235">開始使用敏感度標籤的程序很快：</span><span class="sxs-lookup"><span data-stu-id="b0406-235">Getting started with sensitivity labels is a quick process:</span></span>

1. <span data-ttu-id="b0406-p136">**定義標籤。** 首先，您需要建立分類法，以用來定義不同層級的敏感內容。您應使用一般名稱或字詞，以便使用者了解。比方說，您可以從個人、公用、一般、機密，和高度機密等標籤開始。您可以使用子標籤依類別將相似的標籤分組。此外，建立標籤時，工具提示是必要的，當使用者將滑鼠指標停留在功能區上的標籤選項，提示會顯示在 Office 應用程式中。</span><span class="sxs-lookup"><span data-stu-id="b0406-p136">**Define the labels.** First, you want to establish your taxonomy for defining different levels of sensitive content. You should use common names or terms that make sense to your users. For example, you can start with labels such as Personal, Public, General, Confidential, and Highly Confidential. You can use sublabels to group similar labels by category. Also, when you create a label, a tool tip is required, which appears in the Office apps when a user hovers over a label option on the Ribbon.</span></span>

1. <span data-ttu-id="b0406-p137">**定義每個標籤的功能。** 然後設定與每個標籤相關聯的保護設定。比方說，較低的敏感度內容 (「一般」標籤) 可能只有套用頁首或頁尾，而較高敏感度內容 (「機密」標籤) 可能會套用浮水印、加密及 WIP，以協助確保只有特殊權限使用者可以存取。</span><span class="sxs-lookup"><span data-stu-id="b0406-p137">**Define what each label can do.** Then, configure the protection settings you want associated with each label. For example, lower sensitivity content (a “General” label) might simply have a header or footer applied to it, while higher sensitivity content (a “Confidential” label) may have a watermark, encryption, and WIP applied to it, to help ensure that only privileged users can access it.</span></span>
 
1. <span data-ttu-id="b0406-p138">**定義誰可以看到標籤。** 定義組織的標籤後，您會在標籤原則中發佈標籤，此原則可控制哪些使用者和群組會看到這些標籤。單一標籤可重複使用 – 定義一次後，即可將標籤包含在指派給不同使用者的數個標籤原則中。但為了讓標籤可指派給內容，您必須先發佈該標籤，才能在 Office 應用程式及其他服務中使用。剛開始時，您可以先指定給一小部分人員以試驗您的敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="b0406-p138">**Define who gets the labels.** After you define your organization’s labels, you publish them in a label policy that controls which users and groups see those labels. A single label is reusable – you define it once, and then you can include it in several label policies assigned to different users. But in order for a label to be assigned to content, you must first publish that label so that it’s available in Office apps and other services. When just starting out, you can pilot your sensitivity labels by assigning them to just a few people.</span></span>

<span data-ttu-id="b0406-250">以下是系統管理員、使用者和 Office 應用程式執行項目以讓敏感度標籤運作的基本流程。</span><span class="sxs-lookup"><span data-stu-id="b0406-250">Here’s the basic flow of what the admin, user, and Office app do to make sensitivity labels work.</span></span>

![敏感度標籤的工作流程圖](media/Sensitivity-label-flow.png)

## <a name="where-sensitivity-labels-can-appear"></a><span data-ttu-id="b0406-252">敏感度標籤會顯示的位置</span><span class="sxs-lookup"><span data-stu-id="b0406-252">Where sensitivity labels can appear</span></span>

<span data-ttu-id="b0406-p139">敏感度標籤會顯示在 Office 應用程式的 UI 中。若要檢視針對特定應用程式與平台目前的可用性，請參閱**[目前提供此功能的位置？](https://support.office.com/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9?ad=US&ui=en-US&rs=en-US#bkmk_whereavailable)**</span><span class="sxs-lookup"><span data-stu-id="b0406-p139">Sensitivity labels appear in the UI of Office apps. To view the current availability for specific apps and platforms, see **[Where is the feature available today?](https://support.office.com/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9?ad=US&ui=en-US&rs=en-US#bkmk_whereavailable)**</span></span>

### <a name="office-apps-on-windows"></a><span data-ttu-id="b0406-255">Windows 上的 Office 應用程式</span><span class="sxs-lookup"><span data-stu-id="b0406-255">Office apps on Windows</span></span>

<span data-ttu-id="b0406-p140">在執行 Windows 的裝置上 Office 應用程式中，敏感度標籤會顯示在功能區上 [常用]\*\*\*\* 索引標籤的 [敏感度]\*\*\*\* 按鈕中。套用的標籤也會顯示在視窗底部的狀態列中。</span><span class="sxs-lookup"><span data-stu-id="b0406-p140">In Office apps on devices running Windows, sensitivity labels appear on the **Sensitivity** button, on the **Home** tab on the Ribbon. The label applied also appears in the Status bar at the bottom of the window.</span></span>

<span data-ttu-id="b0406-258">即將推出 Windows 中 Office 應用程式敏感度標籤的原生支援。</span><span class="sxs-lookup"><span data-stu-id="b0406-258">Coming soon is native support for sensitivity labels in Office apps on Windows.</span></span>

<span data-ttu-id="b0406-p141">如果您是現有的 Azure 資訊保護客戶，您可以部署 Azure 資訊保護整合標籤用戶端，其支援敏感度標籤。如需下載用戶端的詳細資訊，請參閱 [Azure 資訊保護統一標籤客戶端：版本發行資訊](https://docs.microsoft.com/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)。我們目前正在處理 Windows 中 Office 應用程式敏感度標籤的原生支援，將不再需要 Azure 資訊保護整合標籤用戶端。</span><span class="sxs-lookup"><span data-stu-id="b0406-p141">If you're an existing Azure Information Protection customer, you can deploy the Azure Information Protection unified labeling client, which supports sensitivity labels. For more information about downloading the client, see [Azure Information Protection unified labeling client: Version release information](https://docs.microsoft.com/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history). We’re currently working on native support for sensitivity labels in Office apps on Windows, so that the Azure Information Protection unified labeling client will no longer be required.</span></span>

![Windows 中 Excel 功能區上的敏感度按鈕](media/Sensitivity-label-Sensitivity-button.png)

### <a name="office-apps-on-mac"></a><span data-ttu-id="b0406-263">Mac 上的 Office 應用程式</span><span class="sxs-lookup"><span data-stu-id="b0406-263">Office apps on Mac</span></span>

<span data-ttu-id="b0406-p142">在 Mac 裝置上的 Office 應用程式中，敏感度標籤會顯示在功能區上 [常用]\*\*\*\* 索引標籤的 [敏感度]\*\*\*\* 按鈕中。套用的標籤也會顯示在視窗底部的狀態列中。</span><span class="sxs-lookup"><span data-stu-id="b0406-p142">In Office apps on Mac devices, sensitivity labels appear on the **Sensitivity** button, on the **Home** tab on the Ribbon. The label applied also appears in the Status bar at the bottom of the window.</span></span>

![Mac 中 Office 功能區上的敏感度按鈕](media/Sensitivity-label-on-Mac.png)

### <a name="office-apps-on-ios"></a><span data-ttu-id="b0406-267">iOS 上的 Office 應用程式</span><span class="sxs-lookup"><span data-stu-id="b0406-267">Office apps on iOS</span></span>

<span data-ttu-id="b0406-p143">在 iOS 裝置上的 Office 應用程式中，敏感度標籤會顯示在功能區上 [常用]\*\*\*\* 索引標籤的 [敏感度]\*\*\*\* 按鈕中。套用的標籤也會顯示在視窗底部的狀態列中。</span><span class="sxs-lookup"><span data-stu-id="b0406-p143">In Office apps on iOS devices, sensitivity labels appear on the **Sensitivity** button, on the **Home** tab on the Ribbon. The label applied also appears in the Status bar at the bottom of the window.</span></span>

![iOS 中 Office 功能區上的敏感度按鈕](media/Sensitivity-label-on-iOS.png)

### <a name="office-apps-on-android"></a><span data-ttu-id="b0406-271">Android 上的 Office 應用程式</span><span class="sxs-lookup"><span data-stu-id="b0406-271">Office apps on Android</span></span>

<span data-ttu-id="b0406-p144">在 Android 裝置上的 Office 應用程式中，敏感度標籤會顯示在功能區上 [常用]\*\*\*\* 索引標籤的 [敏感度]\*\*\*\* 按鈕中。套用的標籤也會顯示在視窗底部的狀態列中。</span><span class="sxs-lookup"><span data-stu-id="b0406-p144">In Office apps on Android devices, sensitivity labels appear on the **Sensitivity** button, on the **Home** tab on the Ribbon. The label applied also appears in the Status bar at the bottom of the window.</span></span>

![Android 中 Office 功能區上的敏感度按鈕](media/Sensitivity-label-on-Android.png)

### <a name="more-information-on-sensitivity-labels-in-office-apps"></a><span data-ttu-id="b0406-275">Office 應用程式中敏感度標籤的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="b0406-275">More information on sensitivity labels in Office apps</span></span>

- [<span data-ttu-id="b0406-276">在 Office 中將敏感度標籤套用至您的文件和電子郵件</span><span class="sxs-lookup"><span data-stu-id="b0406-276">Apply sensitivity labels to your documents and email within Office</span></span>](https://support.office.com/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
- [<span data-ttu-id="b0406-277">將敏感度標籤套用至 Office 檔案的已知問題</span><span class="sxs-lookup"><span data-stu-id="b0406-277">Known issues when you apply sensitivity labels to your Office files</span></span>](https://support.office.com/article/known-issues-when-you-apply-sensitivity-labels-to-your-office-files-b169d687-2bbd-4e21-a440-7da1b2743edc)

## <a name="how-sensitivity-labels-work-with-existing-azure-information-protection-labels"></a><span data-ttu-id="b0406-278">敏感度標籤如何搭配使用現有的 Azure 資訊保護標籤</span><span class="sxs-lookup"><span data-stu-id="b0406-278">How sensitivity labels work with existing Azure Information Protection labels</span></span>

<span data-ttu-id="b0406-p145">Azure 資訊保護使用者目前可藉由使用 Azure 資訊保護整合標籤用戶端，在 Windows 上分類和標記內容。現有的 Azure 資訊保護標籤與新的敏感度標籤可順利搭配運作。這表示您可以：</span><span class="sxs-lookup"><span data-stu-id="b0406-p145">Azure Information Protection users are currently able to classify and label content on Windows by using the Azure Information Protection unified labeling client. Existing Azure Information Protection labels work seamlessly with new sensitivity labels. This means you can:</span></span>

- <span data-ttu-id="b0406-282">在文件和電子郵件上保留現有的 Azure 資訊保護標籤。</span><span class="sxs-lookup"><span data-stu-id="b0406-282">Keep your existing Azure Information Protection labels on documents and email.</span></span>
- <span data-ttu-id="b0406-283">保留現有的 Azure 資訊保護標籤設定。</span><span class="sxs-lookup"><span data-stu-id="b0406-283">Keep your existing Azure Information Protection label configuration.</span></span>

<span data-ttu-id="b0406-284">如果您使用 Azure 資訊保護標籤，目前建議您避免在其他系統管理中心建立新的標籤，直到完成移轉為止。</span><span class="sxs-lookup"><span data-stu-id="b0406-284">If you are using Azure Information Protection labels, for now we recommend that you avoid creating new labels in other admin centers until after you’ve completed your migration.</span></span> <span data-ttu-id="b0406-285">[Azure 資訊保護移轉主題](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)提供重要的資訊和一些特定的警告。</span><span class="sxs-lookup"><span data-stu-id="b0406-285">The [Azure Information Protection migration topic](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels) has important information and some specific caveats.</span></span> <span data-ttu-id="b0406-286">如果您尚未準備好要將您的生產環境租用戶移轉到敏感度標籤，則無需擔心：目前，您的使用者可以繼續使用 Azure 資訊保護用戶端，而系統管理員可以繼續使用 Azure 入口網站來進行管理。</span><span class="sxs-lookup"><span data-stu-id="b0406-286">If you are not yet ready to migrate your production tenants to sensitivity labels, there is no cause for concern: for the moment, your users can continue using the Azure Information Protection client, and admins can continue using the Azure portal for management.</span></span>

## <a name="protect-content-on-windows-devices-by-using-endpoint-protection-in-microsoft-intune"></a><span data-ttu-id="b0406-287">使用 Microsoft Intune 中的端點保護來保護 Windows 裝置上的內容</span><span class="sxs-lookup"><span data-stu-id="b0406-287">Protect content on Windows devices by using endpoint protection in Microsoft Intune</span></span>

<span data-ttu-id="b0406-p147">建立敏感度標籤時，您可以告知 Windows 具有此標籤的檔案為敏感且儲存在 Windows 裝置上時需要防止資料外洩。此選項可協助確保具有此標籤的內容只能共用或複製到批准的位置，即使是儲存在端點上。基本上，開啟敏感度標籤的此選項會告訴 Windows 這是非常重要的資料，並保證其他的使用限制。</span><span class="sxs-lookup"><span data-stu-id="b0406-p147">When you create a sensitivity label, you have the option to tell Windows that files with this label are sensitive and need to be protected against data leakage when stored on Windows devices. This option can help ensure that content with this label can be shared or copied only to sanctioned locations, even when it’s stored on an endpoint. In essence, turning on this option for a sensitivity label tells Windows that this is extra critical data that warrants additional usage constraints.</span></span>

<span data-ttu-id="b0406-p148">當您開啟此選項，Windows 可以讀取、了解及對文件中的敏感度標籤採取動作，並自動對內容套用 Windows 資訊保護 (WIP)，不論其如何觸及受管理的 Windows 裝置。在無論是否套用加密的情況下，這有助於防止標記的檔案發生意外洩漏。</span><span class="sxs-lookup"><span data-stu-id="b0406-p148">When you turn on this option, Windows can read, understand, and act on sensitivity labels in documents and automatically apply Windows Information Protection (WIP) on content, no matter how it reaches a managed Windows device. This helps protect labeled files from accidental leakage, with or without applying encryption.</span></span>

<span data-ttu-id="b0406-293">比方說，Windows 可了解位於使用者電腦上的 Word 文件已套用「機密」標籤，且 WIP 可套用應用程式保護原則，以避免將資料複製或共用到該裝置的任何非工作位置 (例如個人 OneDrive、個人電子郵件帳戶、社群媒體或 USB 磁碟機)。</span><span class="sxs-lookup"><span data-stu-id="b0406-293">For example, Windows can understand that a Word document residing on a user’s machine has a Confidential label applied to it, and WIP can apply an app protection policy to prevent the copying or sharing of the data to any non-work location from that device (such as a personal OneDrive, personal email accounts, social media, or USB drives).</span></span>

<span data-ttu-id="b0406-294">如果使用者嘗試將已標記的內容上傳到個人 Gmail 帳戶，他們會看到這則訊息。</span><span class="sxs-lookup"><span data-stu-id="b0406-294">If a user attempts to upload labeled content to a personal Gmail account, they see this message.</span></span>

![已標記內容的訊息無法複製到 Gmail](media/Sensitivity-label-WIP-Gmail.png)

<span data-ttu-id="b0406-296">如果使用者嘗試將已標記的內容儲存到 USB 磁碟機，他們會看到這則訊息。</span><span class="sxs-lookup"><span data-stu-id="b0406-296">And if a user attempts to save labeled content to a USB drive, they see this message.</span></span>

![已標記內容的訊息無法複製到 USB 磁碟機](media/Sensitivity-label-WIP-USB-drive.png)

### <a name="important-prerequisites"></a><span data-ttu-id="b0406-298">重要的先決條件</span><span class="sxs-lookup"><span data-stu-id="b0406-298">Important prerequisites</span></span>

<span data-ttu-id="b0406-p149">在敏感度標籤可使用 WIP 之前，您必須先執行下文所述的先決條件：[Windows 資訊保護如何保護具有敏感度標籤的檔案](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/how-wip-works-with-labels?branch=vsts17546553)。本主題將說明下列先決條件：</span><span class="sxs-lookup"><span data-stu-id="b0406-p149">Before your sensitivity labels can use WIP, you first need to do the prerequisites described here: [How Windows Information Protection protects files with a sensitivity label](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/how-wip-works-with-labels?branch=vsts17546553). This topic describes the following prerequisites:</span></span>

- <span data-ttu-id="b0406-301">請確定您執行的是 Windows 10，版本 1809 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="b0406-301">Make sure you're running Windows 10, version 1809 or later.</span></span>
- <span data-ttu-id="b0406-302">[設定 Microsoft Defender 進階威脅防護 (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/)，這會掃描標籤內容，並套用對應的 WIP 保護。</span><span class="sxs-lookup"><span data-stu-id="b0406-302">[Set up Windows Defender Advanced Threat Protection (WDATP)](https://docs.microsoft.com/windows/security/threat-protection/), which scans content for a label and applies the corresponding WIP protection. ATP performs some actions independently from WIP, such as reporting anomalies.</span></span> <span data-ttu-id="b0406-303">ATP 執行某些獨立於 WIP 的動作，例如報告異常狀況。</span><span class="sxs-lookup"><span data-stu-id="b0406-303">ATP performs some actions independently from WIP, such as reporting anomalies.</span></span>
- <span data-ttu-id="b0406-p151">建立可套用至端點裝置的 Windows 資訊保護 (WIP) 原則。您可以在下列任何位置執行此作業：</span><span class="sxs-lookup"><span data-stu-id="b0406-p151">Create a Windows Information Protection (WIP) policy that applies to endpoint devices. You can do this in either of these locations:</span></span>
    - [<span data-ttu-id="b0406-306">為 Microsoft Intune 使用 Azure 入口網站透過 MDM 建立 Windows 資訊保護 (WIP) 原則</span><span class="sxs-lookup"><span data-stu-id="b0406-306">Create a Windows Information Protection (WIP) policy with MDM using the Azure portal for Microsoft Intune</span></span>](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure)
    - [<span data-ttu-id="b0406-307">使用 System Center Configuration Manager 建立及部署 Windows 資訊保護 (WIP) 原則</span><span class="sxs-lookup"><span data-stu-id="b0406-307">Create and deploy a Windows Information Protection (WIP) policy using System Center Configuration Manager</span></span>](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-sccm)

## <a name="protect-content-in-third-party-apps-and-services-by-using-microsoft-cloud-app-security"></a><span data-ttu-id="b0406-308">使用 Microsoft Cloud App Security 保護協力廠商應用程式和服務中的內容</span><span class="sxs-lookup"><span data-stu-id="b0406-308">Protect content in third-party apps and services by using Microsoft Cloud App Security</span></span>

<span data-ttu-id="b0406-309">使用 Cloud App Security (CAS) 保護協力廠商應用程式和服務中的內容。</span><span class="sxs-lookup"><span data-stu-id="b0406-309">Protect content in third-party apps and services by using Cloud App Security (CAS).</span></span> <span data-ttu-id="b0406-310">您可以使用 CAS 來偵測、分類、加標籤，以及保護內容的第三方服務和應用程式 (例如 SalesForce、Box 或 Dropbox) 中的內容。</span><span class="sxs-lookup"><span data-stu-id="b0406-310">With CAS, you can detect, classify, label, and protect content in third-party services and apps, such as SalesForce, Box, or Dropbox.</span></span> <span data-ttu-id="b0406-311">例如，Dropbox 可能無法了解敏感度標籤，但 CAS 可以取得並保護該位置中加標籤的內容。</span><span class="sxs-lookup"><span data-stu-id="b0406-311">For example, Dropbox might not understand a sensitivity label, but CAS can reach out and protect labeled content in that location.</span></span>

<span data-ttu-id="b0406-312">如需詳細資訊，請參閱[自動套用 Azure 資訊保護分類標籤](https://docs.microsoft.com/cloud-app-security/use-case-information-protection)。</span><span class="sxs-lookup"><span data-stu-id="b0406-312">For more information, see [Automatically apply Azure Information Protection classification labels](https://docs.microsoft.com/cloud-app-security/use-case-information-protection).</span></span>

### <a name="important-prerequisites"></a><span data-ttu-id="b0406-313">重要的先決條件</span><span class="sxs-lookup"><span data-stu-id="b0406-313">Important prerequisites</span></span>

<span data-ttu-id="b0406-314">在敏感度標籤可使用 CAS 之前，您必須先執行下文所述的先決條件：[自動套用 Azure 資訊保護分類標籤](https://docs.microsoft.com/cloud-app-security/use-case-information-protection)。</span><span class="sxs-lookup"><span data-stu-id="b0406-314">Before your sensitivity labels can use CAS, you first need to do the prerequisites described here: [Automatically apply Azure Information Protection classification labels](https://docs.microsoft.com/cloud-app-security/use-case-information-protection).</span></span> <span data-ttu-id="b0406-315">本主題說明下列先決條件：</span><span class="sxs-lookup"><span data-stu-id="b0406-315">This topic describes the following prerequisites:</span></span>

- <span data-ttu-id="b0406-316">為您的租用戶[啟用 Cloud App Security 和 Azure 資訊保護](https://docs.microsoft.com/cloud-app-security/azip-integration)。</span><span class="sxs-lookup"><span data-stu-id="b0406-316">[Enable Cloud App Security and Azure Information Protection](https://docs.microsoft.com/cloud-app-security/azip-integration) for your tenant.</span></span>
- <span data-ttu-id="b0406-317">[將應用程式連線](https://docs.microsoft.com/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps)至 Cloud App Security。</span><span class="sxs-lookup"><span data-stu-id="b0406-317">[Connect the app](https://docs.microsoft.com/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps) to Cloud App Security.</span></span>

## <a name="extend-sensitivity-labels-to-third-party-apps-and-services-by-using-the-microsoft-information-protection-sdk"></a><span data-ttu-id="b0406-318">使用 Microsoft 資訊保護 SDK 將敏感度標籤擴充至協力廠商應用程式和服務</span><span class="sxs-lookup"><span data-stu-id="b0406-318">Extend sensitivity labels to third-party apps and services by using the Microsoft Information Protection SDK</span></span>

<span data-ttu-id="b0406-p154">由於敏感度標籤在文件的中繼資料內保存為純文字，協力廠商應用程式和服務可以選擇支援識別及保護含有這類標籤的內容。其他應用程式和服務的支援已展開。</span><span class="sxs-lookup"><span data-stu-id="b0406-p154">Because a sensitivity label is persisted as clear text in the metadata of a document, third-party apps and services can choose to support identifying and protecting content that contains such a label. Support in other apps and services is always expanding.</span></span>

<span data-ttu-id="b0406-p155">使用 [Microsoft 資訊保護 SDK](https://docs.microsoft.com/information-protection/develop/)，協力廠商應用程式和服務可以讀取並將敏感度標籤和保護套用至文件。SDK 支援 Windows、Mac 和 Linux 上的應用程式。iOS 和 Android 應用程式的支援即將推出。</span><span class="sxs-lookup"><span data-stu-id="b0406-p155">With the [Microsoft Information Protection SDK](https://docs.microsoft.com/information-protection/develop/), third-party apps and services can read and apply sensitivity labels and protection to documents. The SDK supports apps on Windows, Mac, and Linux. Coming soon is support for apps on iOS and Android.</span></span>

<span data-ttu-id="b0406-p156">使用 SDK，您可以標記及保護內容，並搭配其他 Microsoft 資訊保護應用程式和服務，如 Office 應用程式、Office 365 服務、Azure 資訊保護掃描器、Microsoft Cloud App Security，以及多種其他的合作夥伴解決方案。例如，深入了解 [Adobe Acrobat 中敏感度標籤的支援](https://techcommunity.microsoft.com/t5/Azure-Information-Protection/Starting-October-use-Adobe-Acrobat-Reader-for-PDFs-protected-by/ba-p/262738)。</span><span class="sxs-lookup"><span data-stu-id="b0406-p156">Using the SDK, you can label and protect content in a way that works with other Microsoft Information Protection apps and services, such as Office apps, Office 365 services, the Azure Information Protection scanner, Microsoft Cloud App Security, and several other partner solutions. For example, learn more about [support for sensitivity labels in Adobe Acrobat](https://techcommunity.microsoft.com/t5/Azure-Information-Protection/Starting-October-use-Adobe-Acrobat-Reader-for-PDFs-protected-by/ba-p/262738).</span></span>

<span data-ttu-id="b0406-p157">若要深入了解 Microsoft 資訊保護 SDK，請參閱[技術社群部落格上的公告](https://techcommunity.microsoft.com/t5/Microsoft-Information-Protection/Microsoft-Information-Protection-SDK-Now-Generally-Available/ba-p/263144)。您也可以了解[與 Microsoft 資訊保護整合的合作夥伴解決方案](https://techcommunity.microsoft.com/t5/Azure-Information-Protection/Microsoft-Information-Protection-showcases-integrated-partner/ba-p/262657)。</span><span class="sxs-lookup"><span data-stu-id="b0406-p157">To learn more about the Microsoft Information Protection SDK, see the [announcement on the Tech Community blog](https://techcommunity.microsoft.com/t5/Microsoft-Information-Protection/Microsoft-Information-Protection-SDK-Now-Generally-Available/ba-p/263144). You can also learn about [partner solutions that are integrated with Microsoft Information Protection](https://techcommunity.microsoft.com/t5/Azure-Information-Protection/Microsoft-Information-Protection-showcases-integrated-partner/ba-p/262657).</span></span>

## <a name="permissions"></a><span data-ttu-id="b0406-328">權限</span><span class="sxs-lookup"><span data-stu-id="b0406-328">Permissions</span></span>

<span data-ttu-id="b0406-329">合規性小組成員會建立敏感度標籤，這些成員需要 Microsoft 365 合規性中心、Microsoft 365 安全性中心或 Office 365 安全性與合規性中心的權限。</span><span class="sxs-lookup"><span data-stu-id="b0406-329">Members of your compliance team who will create sensitivity labels need permissions to the Microsoft 365 compliance center, Microsoft 365 security center, or Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="b0406-330">根據預設，您的租用戶系統管理員可以存取這些系統管理中心，並且授與法務人員和其他人員存取權限，而不需授與他們租用戶系統管理員的所有權限。若要這麼做，我們建議您移至其中一個系統管理中心的**權限**頁面，然後將成員新增至**合規性系統管理員**或**安全性系統系統管理員**角色群組。</span><span class="sxs-lookup"><span data-stu-id="b0406-330">Members of your compliance team who will create retention policies need permissions to the Security  Compliance Center. By default, your tenant admin will have access to this location and can give compliance officers and other people access to the Security  Compliance Center, without giving them all of the permissions of a tenant admin. To do this, we recommend that you go to the Permissions page of the Security  Compliance Center, edit the Compliance Administrator role group, and add members to that role group.</span></span>

<span data-ttu-id="b0406-331">如需詳細資訊，請參閱[授與使用者存取 Office 365 安全性與合規性中心的權限](grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="b0406-331">For more information, see [Give users access to the Office 365 Security & Compliance Center](grant-access-to-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="b0406-p159">需要這些權限才能建立及套用標籤和標籤原則。原則強制執行不需要內容的存取權。</span><span class="sxs-lookup"><span data-stu-id="b0406-p159">These permissions are required only to create and apply labels and a label policy. Policy enforcement does not require access to the content.</span></span>
