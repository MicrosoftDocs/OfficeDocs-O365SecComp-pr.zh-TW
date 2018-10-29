---
title: 敏感度標籤概觀
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/22/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: af398293-c69d-465e-a249-d74561552d30
description: 使用 Office 365 的敏感度標籤，您可以分類並協助保護敏感內容，同時確保人員的生產力與共同作業能力不會受到阻礙。您可以使用敏感度標籤在標記的內容上強制執行保護設定，例如加密或浮水印。
ms.openlocfilehash: d08f0e630aeec185ac36998e611fa11ba5c5e007
ms.sourcegitcommit: 3ac6452ab77a761d06122c35c5f4a76da4472990
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2018
ms.locfileid: "25769902"
---
# <a name="overview-of-sensitivity-labels"></a><span data-ttu-id="51d4a-104">敏感度標籤概觀</span><span class="sxs-lookup"><span data-stu-id="51d4a-104">Overview of sensitivity labels</span></span>

<span data-ttu-id="51d4a-p102">若要完成工作，組織中的人員需要與組織內外的其他人員共同合作。這表示內容不總是在防火牆後，它會漫遊在裝置、應用程式和服務的各處。您希望內容以安全、受保護的方式漫遊，以符合組織的商務及法規遵循原則。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p102">To get their work done, people in your organization need to collaborate with others both inside and outside the organization. This means that content no longer stays behind a firewall – it roams everywhere, across devices, apps, and services. And when it roams, you want it to do so in a secure, protected way that meets your organization’s business and compliance policies.</span></span>

<span data-ttu-id="51d4a-108">使用 Office 365 的敏感度標籤，您可以分類並協助保護敏感內容，同時確保人員的生產力與共同作業能力不會受到阻礙。</span><span class="sxs-lookup"><span data-stu-id="51d4a-108">With sensitivity labels in Office 365, you can classify and help protect your sensitive content, while making sure that your people’s productivity and ability to collaborate isn’t hindered.</span></span>

![Excel 功能區和狀態列上的敏感度標籤](media/Sensitivity_label_in_Excel.png)

<span data-ttu-id="51d4a-110">您可以使用敏感度標籤來：</span><span class="sxs-lookup"><span data-stu-id="51d4a-110">You can use sensitivity labels to:</span></span>
  
- <span data-ttu-id="51d4a-p103">**在標記的內容上強制執行保護設定，例如加密或浮水印。** 例如，使用者可以將「機密」標籤套用至文件或電子郵件，該標籤即可加密內容，並套用「機密」浮水印。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p103">**Enforce protection settings such as encryption or watermarks on labeled content.** For example, your users can apply a Confidential label to a document or email, and that label can encrypt the content and apply a Confidential watermark.</span></span>    

- <span data-ttu-id="51d4a-p104">**在不同平台和裝置上保護 Office 應用程式中的內容。** 敏感度標籤可在 Windows、Mac、iOS 和 Android 的 Office 應用程式中使用。即將推出 Office Web 應用程式的支援。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p104">**Protect content in Office apps across different platforms and devices.** Sensitivity labels work in Office apps on Windows, Mac, iOS, and Android. Support for Office web apps is coming soon.</span></span>
    
- <span data-ttu-id="51d4a-p105">**防止敏感內容離開組織執行 Windows 的裝置**，方式是使用 Microsoft Intune 的端點保護。敏感度標籤套用至位於 Windows 裝置上的內容後，端點保護可以防止該內容複製到協力廠商應用程式，例如 Twitter 或 Gmail，或複製到卸除式儲存空間，如 USB 磁碟機。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p105">**Prevent sensitive content from leaving your organization on devices running Windows**, by using endpoint protection in Microsoft Intune. After a sensitivity label has been applied to content that resides on a Windows device, endpoint protection can prevent that content from being copied to a third-party app, such as Twitter or Gmail, or being copied to removable storage, such as a USB drive.</span></span>

- <span data-ttu-id="51d4a-p106">**將敏感度標籤擴充至協力廠商應用程式和服務。** 使用 Microsoft 資訊保護 SDK，Windows、Mac 和 Linux 上的協力廠商應用程式可以讀取敏感度標籤，並且套用保護設定。iOS 和 Android 應用程式的支援即將推出。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p106">**Extend sensitivity labels to third-party apps and services.** With the Microsoft Information Protection SDK, third-party apps on Windows, Mac, and Linux can read sensitivity labels and apply protection settings. Support for apps on iOS and Android is coming soon.</span></span>

- <span data-ttu-id="51d4a-p107">**將內容分類而不需使用任何保護設定。** 您只要將分類指派至內容 (就像貼紙)，分類就會在使用及共用內容時保留並跟隨內容。您可以使用此分類產生使用狀況報告，並查看敏感內容的活動資料。根據這項資訊，稍後您可以隨時選擇套用保護設定。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p107">**Classify content without using any protection settings.** You can also simply assign a classification to content (like a sticker) that persists and roams with the content as it's used and shared. You can use this classification to generate usage reports and see activity data for your sensitive content. Based on this information, you can always choose at a later time to apply protection settings.</span></span>
    
<span data-ttu-id="51d4a-p108">在這些案例中，Office 365 中的敏感度標籤可以幫助您對正確的內容採取正確的動作。使用敏感度標籤，您可以分類整個組織中的資料，並根據該分類強制執行保護設定。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p108">In all of these cases, sensitivity labels in Office 365 can help you take the right actions on the right content. With sensitivity labels, you can classify data across your organization and enforce protection settings based on that classification.</span></span>
  
<span data-ttu-id="51d4a-p109">您在 Office 365 安全性 &amp; 合規性中心建立敏感度標籤。安全性與合規性中心目前是在 Azure 資訊保護和 Office 365 中設定敏感度標籤和原則的單一位置。這些敏感度標籤可供 Azure 資訊保護、Office 應用程式和 Office 365 服務使用。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p109">You create sensitivity labels in the Office 365 Security &amp; Compliance Center. The Security & Compliance Center is now the single place to configure sensitivity labels and policies across Azure Information Protection and Office 365. These sensitivity labels can be used by Azure Information Protection, Office apps, and Office 365 services.</span></span>

<span data-ttu-id="51d4a-p110">針對 Azure 資訊保護客戶，您可以使用安全性與合規性中心的 Azure 資訊保護標籤，且您的標籤會在 Azure 入口網站同步處理，以防您選擇執行額外或進階的設定。**Azure 資訊保護標籤和 Office 365 敏感度標籤完全互相相容。** 這表示，比方說，如果 Azure 資訊保護已標示內容，則您不需要重新分類或重新標示內容。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p110">For Azure Information Protection customers, you can use your Azure Information Protection labels in the Security & Compliance center, and your labels will be synced with the Azure portal in case you choose to perform additional or advanced configuration. **Azure Information Protection labels and Office 365 sensitivity labels are fully compatible with each other.** This means, for example, if you have content labeled by Azure Information Protection, you won’t need to reclassify or relabel your content.</span></span>

![安全性與合規性中心的 [標籤] 頁面上的 [敏感度] 索引標籤](media/Sensitivity_label_tab_on_Labels_page.png)

## <a name="what-a-sensitivity-label-is"></a><span data-ttu-id="51d4a-134">敏感度標籤是什麼</span><span class="sxs-lookup"><span data-stu-id="51d4a-134">What a sensitivity label is</span></span>

<span data-ttu-id="51d4a-135">當您將敏感度標籤指派至文件或電子郵件，它就像標記：</span><span class="sxs-lookup"><span data-stu-id="51d4a-135">When you assign a sensitivity label to a document or email, it’s simply like a tag that is:</span></span>

- <span data-ttu-id="51d4a-p111">**可自訂。** 您可以為組織中不同等級的敏感內容建立類別，例如個人、公用、一般、機密、高度機密。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p111">**Customizable.** You can create categories for different levels of sensitive content in your organization, such as Personal, Public, General, Confidential, and Highly Confidential.</span></span>

- <span data-ttu-id="51d4a-p112">**純文字。** 因為標籤是純文字，協力廠商應用程式和服務可以套用保護措施至已標示的內容。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p112">**Clear text.** Because the label is in clear text, it’s available for third-party apps and services to apply protective actions to labeled content.</span></span>

- <span data-ttu-id="51d4a-p113">**持續性。** 敏感度標籤套用至內容後，會保留在該電子郵件或文件的中繼資料內。這表示標籤會跟隨內容，包括保護設定，並成為套用和強制執行原則的基礎。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p113">**Persistent.** After a sensitivity label is applied to content, it persists in the metadata of that email or document. This means the label roams with the content, including the protection settings, and becomes the basis for applying and enforcing policies.</span></span>

<span data-ttu-id="51d4a-143">在 Office 應用程式中，敏感度標籤在電子郵件或文件上只會顯示為標記。</span><span class="sxs-lookup"><span data-stu-id="51d4a-143">In the Office apps, a sensitivity label simply appears as a tag on an email or document.</span></span>

<span data-ttu-id="51d4a-p114">內容中的每個項目皆可套用單一敏感度標籤。但請注意，項目可以同時套用單一敏感度標籤和單一[保留標籤](labels.md)。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p114">Each item of content can have a single sensitivity label applied to it. But note that an item can have both a single sensitivity label and a single [retention label](labels.md) applied to it.</span></span>

![套用至電子郵件的敏感度標籤](media/Sensitivity_label_on_email.png)

## <a name="what-sensitivity-labels-can-do"></a><span data-ttu-id="51d4a-147">敏感度標籤的功能</span><span class="sxs-lookup"><span data-stu-id="51d4a-147">What sensitivity labels can do</span></span>

<span data-ttu-id="51d4a-p115">敏感度標籤套用至電子郵件或文件後，會對內容強制執行該標籤的保護設定。使用敏感度標籤，您可以：</span><span class="sxs-lookup"><span data-stu-id="51d4a-p115">After a sensitivity label is applied to an email or document, the protection settings for that label are enforced on the content. With a sensitivity label, you can:</span></span>

- <span data-ttu-id="51d4a-p116">僅**加密**電子郵件，或同時加密電子郵件與文件。您可以選擇哪些使用者或群組擁有權限執行哪些動作和執行時間。比方說，您可以選擇讓組織外特定網域中的使用者僅在內容標示後的 7 天擁有權限檢閱內容。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p116">**Encrypt** email only or both email and documents. You can choose which users or group have permissions to perform which actions and for how long. For example, you can choose to allow users in a specific domain outside your organization to have permissions to review the content for only 7 days after the content is labeled.</span></span>

- <span data-ttu-id="51d4a-p117">**標記內容**的方法為在電子郵件或已套用標籤的文件上新增自訂浮水印、頁首或頁尾。請注意，浮水印僅適用於文件，不適用於電子郵件，並且限制為 255 個字元。此外，頁首和頁尾的限制為 1024 個字元 (除了在 Excel 中的限制為 255 個字元或更少，根據文件是否包含其他頁首或頁尾或其他因素而定。)</span><span class="sxs-lookup"><span data-stu-id="51d4a-p117">**Mark the content** by adding custom watermarks, headers, or footers to email or documents that have the label applied. Note that watermarks are applied only to documents, not email, and they're limited to 255 characters. Also, headers and footers are limited to 1024 characters (except in Excel, where they're limited to 255 characters or fewer, depending on whether the document contains other headers or footers and other factors.)</span></span>

    ![套用至文件的浮水印和頁首](media/Sensitivity_label_watermark_header.png)

- <span data-ttu-id="51d4a-p118">
  \*\*防止資料遺失\*\*，方法是在 Intune 中開啟端點保護。如果下載了敏感內容，您可協助防止 Windows 裝置的資料遺失。比方說，您無法將已標示的內容複製到 Dropbox、Gmail 或 USB 磁碟機。在敏感度標籤可使用 Windows 資訊保護 (WIP) 之前，您需要先在 Azure 入口網站中建立應用程式保護原則。如需詳細資訊，請參閱 [Windows 資訊保護如何保護具有敏感度標籤的檔案](https://docs.microsoft.com/en-us/windows/security/information-protection/windows-information-protection/how-wip-works-with-labels?branch=vsts17546553)。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p118">**Prevent data loss** by turning on endpoint protection in Intune. If sensitive content gets downloaded, you can help prevent the loss of data from Windows devices. For example, you can’t copy labeled content into Dropbox, Gmail, or USB drive. Before your sensitivity labels can use Windows Information Protection (WIP), you first need to create an app protection policy in the Azure portal. For more information, see [How Windows Information Protection protects files with a sensitivity label](https://docs.microsoft.com/en-us/windows/security/information-protection/windows-information-protection/how-wip-works-with-labels?branch=vsts17546553).</span></span>

<span data-ttu-id="51d4a-162">在安全性與合規性中心建立標籤時，這些選項皆可使用。</span><span class="sxs-lookup"><span data-stu-id="51d4a-162">All of these options are available when you create a label in the Security & Compliance Center.</span></span>

![建立敏感度標籤的選項](media/Sensitivity_label_create_options.png)

### <a name="label-priority-order-matters"></a><span data-ttu-id="51d4a-164">標籤優先順序 (順序很重要)</span><span class="sxs-lookup"><span data-stu-id="51d4a-164">Label priority (order matters)</span></span>

<span data-ttu-id="51d4a-p119">在安全性與合規性中心建立敏感度標籤時，會顯示在 [標籤]\*\*\*\* 頁面上 [敏感度]\*\*\*\* 索引標籤中的清單。在此清單中，標籤的順序非常重要，因為它會反映其優先順序。您可以讓限制最嚴苛的敏感度標籤，如「高度機密」，顯示在清單**底部**，限制最寬鬆的敏感度標籤，如「公用」，顯示在**頂端**。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p119">When you create your sensitivity labels in the Security & Compliance Center, they appear in a list on the **Sensitivity** tab on the **Labels** page. In this list, the order of the labels is important because it reflects their priority. You want your most restrictive sensitivity label, such as Highly Confidential, to appear at the **bottom** of the list, and your least restrictive sensitivity label, such as Public, to appear at the **top**.</span></span>

<span data-ttu-id="51d4a-p120">文件或電子郵件只能套用單一敏感度標籤。如果您要求使用者提供將標籤變更為較低分類的理由，這份清單的順序可決定什麼是較低的分類。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p120">A document or email can have only a single sensitivity label applied to it. If you require your users to provide a justification for changing the label to a lower classification, the order of this list determines what's a lower classification.</span></span>

![建立子標籤的選項](media/Sensitivity_label_sublabel_options.png)

### <a name="sublabels-grouping-labels"></a><span data-ttu-id="51d4a-171">子標籤 (分組標籤)</span><span class="sxs-lookup"><span data-stu-id="51d4a-171">Sublabels (grouping labels)</span></span>

<span data-ttu-id="51d4a-p121">使用子標籤，您可以將使用者在 Office 應用程式中看到的標題下一或多個標籤分組。比方說，在「機密」下方，您的組織可能針對該分類的特定類型使用數種不同標籤。在此範例中，標籤「機密」只是文字標籤而沒有保護設定，且因為其具有子標籤，所以不能套用至內容。使用者必須改為選擇「機密」才能檢視子標籤，接著可選擇子標籤套用至內容。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p121">With sublabels, you can group one or more labels below a header that a user sees in an Office app. For example, under Confidential, your organization might use several different labels for specific types of that classification. In this example, the label Confidential is simply a text label with no protection settings, and because it has sublabels, it can’t be applied to content. Instead, users must choose Confidential to view the sublabels, and then they can choose a sublabel to apply to content.</span></span>

<span data-ttu-id="51d4a-p122">子標籤只是在邏輯群組中向使用者顯示標籤的方式。子標籤並不會繼承其上方標籤的任何設定。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p122">Sublabels are simply a way to present labels to users in logical groups. Sublabels don’t inherit any settings from the label they’re under.</span></span>

![功能區上分組的子標籤](media/Sensitivity_label_grouped_labels.png)

### <a name="editing-or-deleting-a-sensitivity-label"></a><span data-ttu-id="51d4a-179">編輯或刪除敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="51d4a-179">Editing or deleting a sensitivity label</span></span>

<span data-ttu-id="51d4a-180">如果您在安全性與合規性中心刪除敏感度標籤，請注意，標籤並未從內容中移除，且所有保護設定會繼續在內容上強制執行。</span><span class="sxs-lookup"><span data-stu-id="51d4a-180">If you delete a sensitivity label in the Security & Compliance Center, note that the label is not removed from content, and any protection settings continue to be enforced on the content.</span></span>

<span data-ttu-id="51d4a-181">如果您在安全性與合規性中心編輯敏感度標籤，則當初套用至內容的標籤版本會在內容上強制執行。</span><span class="sxs-lookup"><span data-stu-id="51d4a-181">If you edit a sensitivity label in the Security & Compliance Center, the version of the label that was applied to content is what’s enforced on that content.</span></span>

## <a name="what-label-policies-can-do"></a><span data-ttu-id="51d4a-182">標籤原則的功能</span><span class="sxs-lookup"><span data-stu-id="51d4a-182">What label policies can do</span></span>

<span data-ttu-id="51d4a-p123">建立敏感度標籤後，您需要發佈標籤，以供組織中的人員使用，這些人員可以接著將標籤套用至內容。與發佈到位置 (例如所有 Exchange 信箱) 的保留標籤不同，敏感度標籤會發佈給使用者或群組。敏感度標籤接著會為這些使用者和群組顯示在 Office 應用程式中。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p123">After you create your sensitivity labels, you need to publish them, to make them available to people in your organization, who can then apply the labels to content. Unlike retention labels, which are published to locations, such as all Exchange mailboxes, sensitivity labels are published to users or groups. Sensitivity labels then appear in Office apps for those users and groups.</span></span>

<span data-ttu-id="51d4a-186">使用標籤原則，您可以：</span><span class="sxs-lookup"><span data-stu-id="51d4a-186">With a label policy, you can:</span></span>

- <span data-ttu-id="51d4a-p124">**選擇哪些使用者和群組可以看見標籤。** 標籤可以發佈到任何電子郵件啟用的安全性群組、通訊群組、Office 365 群組或動態通訊群組。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p124">**Choose which users and groups see the labels.** Labels can be published to any email-enabled security group, distribution group, Office 365 group, or dynamic distribution group.</span></span>

- <span data-ttu-id="51d4a-p125">**套用預設標籤**至所有新文件和電子郵件，這些是由標籤原則中包含的使用者和群組所建立。此預設標籤可以設定您想要套用到所有內容的基礎層級保護設定。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p125">**Apply a default label** to all new documents and email created by the users and groups included in the label policy. This default label can set a base level of protection settings that you want applied to all your content.</span></span>

- <span data-ttu-id="51d4a-p126">**變更標籤需要理由。** 如果內容標示為「機密」，而使用者想要移除該標籤，或取代為較低的分類，如「公用」標籤，則您可以要求使用者在執行此動作時提供理由。這些理由可供系統管理員檢閱。我們目前正在處理系統管理員可在其中檢視使用者理由的報告。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p126">**Require a justification for changing a label.** If content is marked Confidential and a user wants to remove that label or replace it with a lower classification, such as a label named Public, you can require that the user provide a justification when performing this action. These justifications will be available for the admin to review. We’re currently working on a report where admins can view the user justifications.</span></span>

    ![提示使用者輸入理由](media/Sensitivity_label_justification_required.png)

- <span data-ttu-id="51d4a-p127">**提供說明連結至自訂說明頁面。** 如果使用者不確定敏感度標籤代表的意義或使用方式，您可以提供「深入了解」URL，其顯示在 Office 應用程式中 [敏感度] 標籤功能表的底部。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p127">**Provide help link to a custom help page.** If your users aren’t sure what your sensitivity labels mean or how they should be used, you can provide a Learn More URL that appears at the bottom of the Sensitivity label menu in the Office apps.</span></span>

    ![功能區中 [敏感度] 按鈕上的「深入了解」連結](media/Sensitivity_label_learn_more.png)

<span data-ttu-id="51d4a-199">建立標籤原則並將敏感度標籤指派給使用者和群組之後，這些人會在一小時內在 Office 應用程式中看到這些標籤。</span><span class="sxs-lookup"><span data-stu-id="51d4a-199">After you create a label policy and assign sensitivity labels to users and groups, those people will see those labels available in the Office apps in an hour or less.</span></span>

## <a name="how-to-get-started"></a><span data-ttu-id="51d4a-200">如何開始使用</span><span class="sxs-lookup"><span data-stu-id="51d4a-200">How to get started</span></span>

<span data-ttu-id="51d4a-201">開始使用敏感度標籤的程序很快：</span><span class="sxs-lookup"><span data-stu-id="51d4a-201">Getting started with sensitivity labels is a quick process:</span></span>

1. <span data-ttu-id="51d4a-p128">**定義標籤。** 首先，您需要建立分類法，以用來定義不同層級的敏感內容。您應使用一般名稱或字詞，以便使用者了解。比方說，您可以從個人、公用、一般、機密，和高度機密等標籤開始。您可以使用子標籤依類別將相似的標籤分組。此外，建立標籤時，工具提示是必要的，當使用者將滑鼠指標停留在功能區上的標籤選項，提示會顯示在 Office 應用程式中。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p128">**Define the labels.** First, you want to establish your taxonomy for defining different levels of sensitive content. You should use common names or terms that make sense to your users. For example, you can start with labels such as Personal, Public, General, Confidential, and Highly Confidential. You can use sublabels to group similar labels by category. Also, when you create a label, a tool tip is required, which appears in the Office apps when a user hovers over a label option on the Ribbon.</span></span>

1. <span data-ttu-id="51d4a-p129">**定義每個標籤的功能。** 然後設定與每個標籤相關聯的保護設定。比方說，較低的敏感度內容 (「一般」標籤) 可能只有套用頁首或頁尾，而較高敏感度內容 (「機密」標籤) 可能會套用浮水印、加密及 WIP，以協助確保只有特殊權限使用者可以存取。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p129">**Define what each label can do.** Then, configure the protection settings you want associated with each label. For example, lower sensitivity content (a “General” label) might simply have a header or footer applied to it, while higher sensitivity content (a “Confidential” label) may have a watermark, encryption, and WIP applied to it, to help ensure that only privileged users can access it.</span></span>
 
1. <span data-ttu-id="51d4a-p130">**定義誰可以看到標籤。** 定義組織的標籤後，您會在標籤原則中發佈標籤，此原則可控制哪些使用者和群組會看到這些標籤。單一標籤可重複使用 – 定義一次後，即可將標籤包含在指派給不同使用者的數個標籤原則中。但為了讓標籤可指派給內容，您必須先發佈該標籤，才能在 Office 應用程式及其他服務中使用。剛開始時，您可以先指定給一小部分人員以試驗您的敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p130">**Define who gets the labels.** After you define your organization’s labels, you publish them in a label policy that controls which users and groups see those labels. A single label is reusable – you define it once, and then you can include it in several label policies assigned to different users. But in order for a label to be assigned to content, you must first publish that label so that it’s available in Office apps and other services. When just starting out, you can pilot your sensitivity labels by assigning them to just a few people.</span></span>

<span data-ttu-id="51d4a-216">以下是系統管理員、使用者和 Office 應用程式執行項目以讓敏感度標籤運作的基本流程。</span><span class="sxs-lookup"><span data-stu-id="51d4a-216">Here’s the basic flow of what the admin, user, and Office app do to make sensitivity labels work.</span></span>

![敏感度標籤的工作流程圖](media/Sensitivity_label_flow.png)

## <a name="where-sensitivity-labels-can-appear"></a><span data-ttu-id="51d4a-218">敏感度標籤會顯示的位置</span><span class="sxs-lookup"><span data-stu-id="51d4a-218">Where sensitivity labels can appear</span></span>

<span data-ttu-id="51d4a-p131">敏感度標籤會顯示在 Office 應用程式的 UI 中。若要檢視針對特定應用程式與平台目前的可用性，請參閱**[目前提供此功能的位置？](https://support.office.com/zh-TW/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9?ad=US&ui=en-US&rs=en-US#bkmk_whereavailable)**</span><span class="sxs-lookup"><span data-stu-id="51d4a-p131">Sensitivity labels appear in the UI of Office apps. To view the current availability for specific apps and platforms, see **[Where is the feature available today?](https://support.office.com/zh-TW/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9?ad=US&ui=en-US&rs=en-US#bkmk_whereavailable)**</span></span>

### <a name="office-apps-on-windows"></a><span data-ttu-id="51d4a-221">Windows 上的 Office 應用程式</span><span class="sxs-lookup"><span data-stu-id="51d4a-221">Office apps on Windows</span></span>

<span data-ttu-id="51d4a-p132">在執行 Windows 的裝置上 Office 應用程式中，敏感度標籤會顯示在功能區上 [常用]\*\*\*\* 索引標籤的 [敏感度]\*\*\*\* 按鈕中。套用的標籤也會顯示在視窗底部的狀態列中。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p132">In Office apps on devices running Windows, sensitivity labels appear on the **Sensitivity** button, on the **Home** tab on the Ribbon. The label applied also appears in the Status bar at the bottom of the window.</span></span>

<span data-ttu-id="51d4a-224">即將推出 Windows 中 Office 應用程式敏感度標籤的原生支援。</span><span class="sxs-lookup"><span data-stu-id="51d4a-224">Coming soon is native support for sensitivty labels in Office apps on Windows.</span></span>

<span data-ttu-id="51d4a-p133">如果您是現有的 Azure 資訊保護客戶，您可以部署 Azure 資訊保護整合標籤用戶端，其支援敏感度標籤。如需下載用戶端的詳細資訊，請參閱 [Azure 資訊保護統一標籤客戶端：版本發行資訊](https://docs.microsoft.com/zh-TW/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)。我們目前正在處理 Windows 中 Office 應用程式敏感度標籤的原生支援，將不再需要 Azure 資訊保護整合標籤用戶端。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p133">If you're an existing Azure Information Protection customer, you can deploy the Azure Information Protection unified labeling client, which supports sensitivity labels. For more information about downloading the client, see [Azure Information Protection unified labeling client: Version release information](https://docs.microsoft.com/zh-TW/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history). We’re currently working on native support for sensitivity labels in Office apps on Windows, so that the Azure Information Protection unified labeling client will no longer be required.</span></span>

![Windows 中 Excel 功能區上的敏感度按鈕](media/Sensitivity_label_Sensitivity_button.png)

### <a name="office-apps-on-mac"></a><span data-ttu-id="51d4a-229">Mac 上的 Office 應用程式</span><span class="sxs-lookup"><span data-stu-id="51d4a-229">Office apps on Mac</span></span>

<span data-ttu-id="51d4a-p134">在 Mac 裝置上的 Office 應用程式中，敏感度標籤會顯示在功能區上 [常用]\*\*\*\* 索引標籤的 [敏感度]\*\*\*\* 按鈕中。套用的標籤也會顯示在視窗底部的狀態列中。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p134">In Office apps on Mac devices, sensitivity labels appear on the **Sensitivity** button, on the **Home** tab on the Ribbon. The label applied also appears in the Status bar at the bottom of the window.</span></span>

![Mac 中 Office 功能區上的敏感度按鈕](media/Sensitivity_label_on_Mac.png)

### <a name="office-apps-on-ios"></a><span data-ttu-id="51d4a-233">iOS 上的 Office 應用程式</span><span class="sxs-lookup"><span data-stu-id="51d4a-233">Office apps on iOS</span></span>

<span data-ttu-id="51d4a-p135">在 iOS 裝置上的 Office 應用程式中，敏感度標籤會顯示在功能區上 [常用]\*\*\*\* 索引標籤的 [敏感度]\*\*\*\* 按鈕中。套用的標籤也會顯示在視窗底部的狀態列中。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p135">In Office apps on iOS devices, sensitivity labels appear on the **Sensitivity** button, on the **Home** tab on the Ribbon. The label applied also appears in the Status bar at the bottom of the window.</span></span>

![iOS 中 Office 功能區上的敏感度按鈕](media/Sensitivity_label_on_iOS.png)

### <a name="office-apps-on-android"></a><span data-ttu-id="51d4a-237">Android 上的 Office 應用程式</span><span class="sxs-lookup"><span data-stu-id="51d4a-237">Office apps on Android</span></span>

<span data-ttu-id="51d4a-p136">在 Android 裝置上的 Office 應用程式中，敏感度標籤會顯示在功能區上 [常用]\*\*\*\* 索引標籤的 [敏感度]\*\*\*\* 按鈕中。套用的標籤也會顯示在視窗底部的狀態列中。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p136">In Office apps on Android devices, sensitivity labels appear on the **Sensitivity** button, on the **Home** tab on the Ribbon. The label applied also appears in the Status bar at the bottom of the window.</span></span>

![Android 中 Office 功能區上的敏感度按鈕](media/Sensitivity_label_on_Android.png)

### <a name="more-information-on-sensitivity-labels-in-office-apps"></a><span data-ttu-id="51d4a-241">Office 應用程式中敏感度標籤的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="51d4a-241">More information on sensitivity labels in Office apps</span></span>

- [<span data-ttu-id="51d4a-242">在 Office 中將敏感度標籤套用至您的文件和電子郵件</span><span class="sxs-lookup"><span data-stu-id="51d4a-242">Apply sensitivity labels to your documents and email within Office</span></span>](https://support.office.com/zh-TW/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
- [<span data-ttu-id="51d4a-243">將敏感度標籤套用至 Office 檔案的已知問題</span><span class="sxs-lookup"><span data-stu-id="51d4a-243">Known issues when you apply sensitivity labels to your Office files</span></span>](https://support.office.com/zh-TW/article/known-issues-when-you-apply-sensitivity-labels-to-your-office-files-b169d687-2bbd-4e21-a440-7da1b2743edc)

## <a name="how-sensitivity-labels-work-with-existing-azure-information-protection-labels"></a><span data-ttu-id="51d4a-244">敏感度標籤如何搭配使用現有的 Azure 資訊保護標籤</span><span class="sxs-lookup"><span data-stu-id="51d4a-244">How sensitivity labels work with existing Azure Information Protection labels</span></span>

<span data-ttu-id="51d4a-p137">Azure 資訊保護使用者目前可藉由使用 Azure 資訊保護整合標籤用戶端，在 Windows 上分類和標記內容。現有的 Azure 資訊保護標籤與新的敏感度標籤可順利搭配運作。這表示您可以：</span><span class="sxs-lookup"><span data-stu-id="51d4a-p137">Azure Information Protection users are currently able to classify and label content on Windows by using the Azure Information Protection unified labeling client. Existing Azure Information Protection labels work seamlessly with new sensitivity labels. This means you can:</span></span>

- <span data-ttu-id="51d4a-248">在文件和電子郵件上保留現有的 Azure 資訊保護標籤。</span><span class="sxs-lookup"><span data-stu-id="51d4a-248">Keep your existing Azure Information Protection labels on documents and email.</span></span>
- <span data-ttu-id="51d4a-249">保留現有的 Azure 資訊保護標籤設定。</span><span class="sxs-lookup"><span data-stu-id="51d4a-249">Keep your existing Azure Information Protection label configuration.</span></span>

<span data-ttu-id="51d4a-p138">如果您使用 Azure 資訊保護標籤，現在我們建議您避免在安全性與合規性中心建立新的標籤，直到您完成移轉。[Azure 資訊保護移轉主題](https://docs.microsoft.com/zh-TW/azure/information-protection/configure-policy-migrate-labels)提供重要的資訊和一些特定警告。如果您尚未準備好移轉您的生產環境租用戶至敏感度標籤，您不須擔心：目前使用者可以繼續使用 Azure 資訊保護用戶端，且系統管理員可以繼續使用 Azure 入口網站進行管理。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p138">If you are using Azure Information Protection labels, for now we recommend that you avoid creating new labels in Security & Compliance Center until after you’ve completed your migration. The [Azure Information Protection migration topic](https://docs.microsoft.com/zh-TW/azure/information-protection/configure-policy-migrate-labels) has important information and some specific caveats. If you are not yet ready to migrate your production tenants to sensitivity labels, there is no cause for concern: for the moment, your users can continue using the Azure Information Protection client, and admins can continue using the Azure portal for management.</span></span>

## <a name="protect-content-on-windows-devices-by-using-endpoint-protection-in-microsoft-intune"></a><span data-ttu-id="51d4a-253">使用 Microsoft Intune 中的端點保護來保護 Windows 裝置上的內容</span><span class="sxs-lookup"><span data-stu-id="51d4a-253">Protect content on Windows devices by using endpoint protection in Microsoft Intune</span></span>

<span data-ttu-id="51d4a-p139">建立敏感度標籤時，您可以告知 Windows 具有此標籤的檔案為敏感且儲存在 Windows 裝置上時需要防止資料外洩。此選項可協助確保具有此標籤的內容只能共用或複製到批准的位置，即使是儲存在端點上。基本上，開啟敏感度標籤的此選項會告訴 Windows 這是非常重要的資料，並保證其他的使用限制。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p139">When you create a sensitivity label, you have the option to tell Windows that files with this label are sensitive and need to be protected against data leakage when stored on Windows devices. This option can help ensure that content with this label can be shared or copied only to sanctioned locations, even when it’s stored on an endpoint. In essence, turning on this option for a sensitivity label tells Windows that this is extra critical data that warrants additional usage constraints.</span></span>

<span data-ttu-id="51d4a-p140">當您開啟此選項，Windows 可以讀取、了解及對文件中的敏感度標籤採取動作，並自動對內容套用 Windows 資訊保護 (WIP)，不論其如何觸及受管理的 Windows 裝置。在無論是否套用加密的情況下，這有助於防止標記的檔案發生意外洩漏。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p140">When you turn on this option, Windows can read, understand, and act on sensitivity labels in documents and automatically apply Windows Information Protection (WIP) on content, no matter how it reaches a managed Windows device. This helps protect labeled files from accidental leakage, with or without applying encryption.</span></span>

<span data-ttu-id="51d4a-259">比方說，Windows 可了解位於使用者電腦上的 Word 文件已套用「機密」標籤，且 WIP 可套用應用程式保護原則，以避免將資料複製或共用到該裝置的任何非工作位置 (例如個人 OneDrive、個人電子郵件帳戶、社群媒體或 USB 磁碟機)。</span><span class="sxs-lookup"><span data-stu-id="51d4a-259">For example, Windows can understand that a Word document residing on a user’s machine has a Confidential label applied to it, and WIP can apply an app protection policy to prevent the copying or sharing of the data to any non-work location from that device (such as a personal ONeDrive, personal email accounts, social media, or USB drives).</span></span>

<span data-ttu-id="51d4a-260">如果使用者嘗試將已標記的內容上傳到個人 Gmail 帳戶，他們會看到這則訊息。</span><span class="sxs-lookup"><span data-stu-id="51d4a-260">If a user attempts to upload labeled content to a personal Gmail account, they see this message.</span></span>

![已標記內容的訊息無法複製到 Gmail](media/Sensitivity_label_WIP_Gmail.png)

<span data-ttu-id="51d4a-262">如果使用者嘗試將已標記的內容儲存到 USB 磁碟機，他們會看到這則訊息。</span><span class="sxs-lookup"><span data-stu-id="51d4a-262">And if a user attempts to save labeled content to a USB drive, they see this message.</span></span>

![已標記內容的訊息無法複製到 USB 磁碟機](media/Sensitivity_label_WIP_USB_drive.png)

### <a name="important-prerequisites"></a><span data-ttu-id="51d4a-264">重要的先決條件</span><span class="sxs-lookup"><span data-stu-id="51d4a-264">Important prerequisites</span></span>

<span data-ttu-id="51d4a-p141">在敏感度標籤可使用 WIP 之前，您必須先執行下文所述的先決條件：[Windows 資訊保護如何保護具有敏感度標籤的檔案](https://docs.microsoft.com/en-us/windows/security/information-protection/windows-information-protection/how-wip-works-with-labels?branch=vsts17546553)。本主題將說明下列先決條件：</span><span class="sxs-lookup"><span data-stu-id="51d4a-p141">Before your sensitivity labels can use WIP, you first need to do the prerequisites described here: [How Windows Information Protection protects files with a sensitivity label](https://docs.microsoft.com/en-us/windows/security/information-protection/windows-information-protection/how-wip-works-with-labels?branch=vsts17546553). This topic describes the following prerequisites:</span></span>

- <span data-ttu-id="51d4a-267">請確定您執行的是 Windows 10，版本 1809 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="51d4a-267">Make sure you're running Windows 10, version 1809 or later.</span></span>
- <span data-ttu-id="51d4a-p142">[設定 Windows Defender 進階威脅防護 (WDATP)](https://docs.microsoft.com/zh-TW/windows/security/threat-protection/windows-defender-atp/get-started)，這會掃描內容以找出標籤，並套用對應的 WIP 保護。ATP 會在 WIP 之外獨立執行某些動作，例如報告異常狀況。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p142">[Set up Windows Defender Advanced Threat Protection (WDATP)](https://docs.microsoft.com/zh-TW/windows/security/threat-protection/windows-defender-atp/get-started), which scans content for a label and applies the corresponding WIP protection. ATP performs some actions independently from WIP, such as reporting anomalies.</span></span>
- <span data-ttu-id="51d4a-p143">建立可套用至端點裝置的 Windows 資訊保護 (WIP) 原則。您可以在下列任何位置執行此作業：</span><span class="sxs-lookup"><span data-stu-id="51d4a-p143">Create a Windows Information Protection (WIP) policy that applies to endpoint devices. You can do this in either of these locations:</span></span>
    - [<span data-ttu-id="51d4a-272">為 Microsoft Intune 使用 Azure 入口網站透過 MDM 建立 Windows 資訊保護 (WIP) 原則</span><span class="sxs-lookup"><span data-stu-id="51d4a-272">Create a Windows Information Protection (WIP) policy with MDM using the Azure portal for Microsoft Intune</span></span>](https://docs.microsoft.com/zh-TW/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure)
    - [<span data-ttu-id="51d4a-273">使用 System Center Configuration Manager 建立及部署 Windows 資訊保護 (WIP) 原則</span><span class="sxs-lookup"><span data-stu-id="51d4a-273">Create and deploy a Windows Information Protection (WIP) policy using System Center Configuration Manager</span></span>](https://docs.microsoft.com/zh-TW/windows/security/information-protection/windows-information-protection/create-wip-policy-using-sccm)

## <a name="extend-sensitivity-labels-to-third-party-apps-and-services-by-using-the-microsoft-information-protection-sdk"></a><span data-ttu-id="51d4a-274">使用 Microsoft 資訊保護 SDK 將敏感度標籤擴充至協力廠商應用程式和服務</span><span class="sxs-lookup"><span data-stu-id="51d4a-274">Extend sensitivity labels to third-party apps and services by using the Microsoft Information Protection SDK</span></span>

<span data-ttu-id="51d4a-p144">由於敏感度標籤在文件的中繼資料內保存為純文字，協力廠商應用程式和服務可以選擇支援識別及保護含有這類標籤的內容。其他應用程式和服務的支援已展開。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p144">Because a sensitivity label is persisted as clear text in the metadata of a document, third-party apps and services can choose to support identifying and protecting content that contains such a label. Support in other apps and services is always expanding.</span></span>

<span data-ttu-id="51d4a-p145">使用 [Microsoft 資訊保護 SDK](https://docs.microsoft.com/zh-TW/information-protection/develop/)，協力廠商應用程式和服務可以讀取並將敏感度標籤和保護套用至文件。SDK 支援 Windows、Mac 和 Linux 上的應用程式。iOS 和 Android 應用程式的支援即將推出。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p145">With the [Microsoft Information Protection SDK](https://docs.microsoft.com/zh-TW/information-protection/develop/), third-party apps and services can read and apply sensitivity labels and protection to documents. The SDK supports apps on Windows, Mac, and Linux. Coming soon is support for apps on iOS and Android.</span></span>

<span data-ttu-id="51d4a-p146">使用 SDK，您可以標記及保護內容，並搭配其他 Microsoft 資訊保護應用程式和服務，如 Office 應用程式、Office 365 服務、Azure 資訊保護掃描器、Microsoft Cloud App Security，以及多種其他的合作夥伴解決方案。例如，深入了解 [Adobe Acrobat 中敏感度標籤的支援](https://techcommunity.microsoft.com/t5/Azure-Information-Protection/Starting-October-use-Adobe-Acrobat-Reader-for-PDFs-protected-by/ba-p/262738)。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p146">Using the SDK, you can label and protect content in a way that works with other Microsoft Information Protection apps and services, such as Office apps, Office 365 services, the Azure Information Protection scanner, Microsoft Cloud App Security, and several other partner solutions. For example, learn more about [support for sensitivity labels in Adobe Acrobat](https://techcommunity.microsoft.com/t5/Azure-Information-Protection/Starting-October-use-Adobe-Acrobat-Reader-for-PDFs-protected-by/ba-p/262738).</span></span>

<span data-ttu-id="51d4a-p147">若要深入了解 Microsoft 資訊保護 SDK，請參閱[技術社群部落格上的公告](https://techcommunity.microsoft.com/t5/Microsoft-Information-Protection/Microsoft-Information-Protection-SDK-Now-Generally-Available/ba-p/263144)。您也可以了解[與 Microsoft 資訊保護整合的合作夥伴解決方案](https://techcommunity.microsoft.com/t5/Azure-Information-Protection/Microsoft-Information-Protection-showcases-integrated-partner/ba-p/262657)。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p147">To learn more about the Microsoft Information Protection SDK, see the [announcement on the Tech Community blog](https://techcommunity.microsoft.com/t5/Microsoft-Information-Protection/Microsoft-Information-Protection-SDK-Now-Generally-Available/ba-p/263144). You can also learn about [partner solutions that are integrated with Microsoft Information Protection](https://techcommunity.microsoft.com/t5/Azure-Information-Protection/Microsoft-Information-Protection-showcases-integrated-partner/ba-p/262657).</span></span>

## <a name="permissions"></a><span data-ttu-id="51d4a-284">權限</span><span class="sxs-lookup"><span data-stu-id="51d4a-284">Permissions</span></span>

<span data-ttu-id="51d4a-p148">您的法務小組中將建立敏感度標籤的成員必須具備安全性與合規性中心的權限。根據預設，租用戶管理員將可存取此位置，並且可直接讓法務人員與其他人存取安全性與合規性中心，而不需要為其提供租用戶管理員的所有權限。若要這麼做，我們建議您：移至安全性與合規性中心的 [權限]\*\*\*\* 頁面，編輯 [規範管理員]\*\*\*\* 角色群組，將該成員加入此角色群組。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p148">Members of your compliance team who will create sensitivity labels need permissions to the Security & Compliance Center. By default, your tenant admin will have access to this location and can give compliance officers and other people access to the Security & Compliance Center, without giving them all of the permissions of a tenant admin. To do this, we recommend that you go to the **Permissions** page of the Security & Compliance Center, edit the **Compliance Administrator** role group, and add members to that role group.</span></span>

<span data-ttu-id="51d4a-287">如需詳細資訊，請參閱授與使用者存取 Office 365 安全性與合規性中心的權限。</span><span class="sxs-lookup"><span data-stu-id="51d4a-287">For more information, see Give users access to the Office 365 Security & Compliance Center.</span></span>

<span data-ttu-id="51d4a-p149">需要這些權限才能建立及套用標籤和標籤原則。原則強制執行不需要內容的存取權。</span><span class="sxs-lookup"><span data-stu-id="51d4a-p149">These permissions are required only to create and apply labels and a label policy. Policy enforcement does not require access to the content.</span></span>
