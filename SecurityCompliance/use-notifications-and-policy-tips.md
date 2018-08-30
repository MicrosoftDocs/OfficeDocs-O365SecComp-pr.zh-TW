---
title: 傳送電子郵件通知，並顯示 DLP 原則的原則提示
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 3/21/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleNotifyUser
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 87496bc5-9601-4473-8021-cb05c71369c1
description: '原則提示是通知或當有人會處理內容與 DLP 原則該發生衝突時出現的警告。您可以使用電子郵件通知及原則提示增加傳達及協助貴組織的原則相關的人員對教育訓練。您也可以的讓人員覆寫原則，以便他們不會封鎖如果有有效的商業選項需要或原則會偵測誤判。 '
ms.openlocfilehash: a24afe6dd1203af4dc1f0f21468e828751bc5f3b
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22527361"
---
# <a name="send-email-notifications-and-show-policy-tips-for-dlp-policies"></a><span data-ttu-id="cc5b0-105">傳送電子郵件通知，並顯示 DLP 原則的原則提示</span><span class="sxs-lookup"><span data-stu-id="cc5b0-105">Send email notifications and show policy tips for DLP policies</span></span>

<span data-ttu-id="cc5b0-p102">您可用於識別、 監視和跨 Office 365 保護敏感資訊的資料遺失防護 (DLP) 原則。您想要在組織中使用保持在最符合 DLP 原則，使敏感資訊的人員，但不想要從快速完成其工作整天封鎖。這是電子郵件通知及原則提示可以協助位置。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-p102">You can use a data loss prevention (DLP) policy to identify, monitor, and protect sensitive information across Office 365. You want people in your organization who work with this sensitive information to stay compliant with your DLP policies, but you don't want to block them unnecessarily from getting their work done. This is where email notifications and policy tips can help.</span></span>
  
![訊息列會顯示 Excel 2016 中的原則提示](media/7002ff54-1656-4a6c-993f-37427d6508c8.png)
  
<span data-ttu-id="cc5b0-110">原則提示會通知或當有人會使用與 DLP 原則相衝突的內容時出現的警告 — 例如 Excel 活頁簿上 OneDrive for Business 網站含有個人識別資訊 (PII) 都是類似的內容與外部使用者共用。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-110">A policy tip is a notification or warning that appears when someone is working with content that conflicts with a DLP policy—for example, content like an Excel workbook on a OneDrive for Business site that contains personally identifiable information (PII) and is shared with an external user.</span></span>
  
<span data-ttu-id="cc5b0-p103">您可以使用電子郵件通知及原則提示增加傳達及協助貴組織的原則相關的人員對教育訓練。您也可以的讓人員覆寫原則，以便他們不會封鎖如果有有效的商業選項需要或原則會偵測誤判。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-p103">You can use email notifications and policy tips to increase awareness and help educate people about your organization's policies. You can also give people the option to override the policy, so that they're not blocked if they have a valid business need or if the policy is detecting a false positive.</span></span>
  
<span data-ttu-id="cc5b0-113">Office 365 安全性&amp;規範中心，當您建立的 DLP 原則時，您可以設定使用者通知：</span><span class="sxs-lookup"><span data-stu-id="cc5b0-113">In the Office 365 Security &amp; Compliance Center, when you create a DLP policy, you can configure the user notifications to:</span></span>
  
- <span data-ttu-id="cc5b0-114">傳送電子郵件通知給人您選擇的說明問題。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-114">Send an email notification to the people you choose that describes the issue.</span></span>
    
- <span data-ttu-id="cc5b0-115">顯示原則提示的 DLP 原則與衝突的內容：</span><span class="sxs-lookup"><span data-stu-id="cc5b0-115">Display a policy tip for content that conflicts with the DLP policy:</span></span>
    
  - <span data-ttu-id="cc5b0-116">在網頁伺服器和 Outlook 2013 及更新版本的 Outlook 中的電子郵件、 的原則提示上方會顯示上方收件者的訊息時所組成的郵件。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-116">For email in Outlook on the web and Outlook 2013 and later, the policy tip appears at the top of a message above the recipients while the message is being composed.</span></span>
    
  - <span data-ttu-id="cc5b0-p104">OneDrive for Business 帳戶或 SharePoint Online 網站中的文件、 原則提示會以項目出現的警告圖示。若要檢視的詳細資訊，您可以選取項目並再選擇 [**資訊**![資訊窗格圖示](media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png)要開啟詳細資料窗格中的頁面右上角。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-p104">For documents in a OneDrive for Business account or SharePoint Online site, the policy tip is indicated by a warning icon that appears on the item. To view more information, you can select an item and then choose **Information**![Information pane icon](media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) in the upper-right corner of the page to open the details pane.</span></span> 
    
  - <span data-ttu-id="cc5b0-119">Excel 2016、 PowerPoint 2016 及儲存在 OneDrive for Business 站台或隨附的 DLP 原則中的 SharePoint Online 網站的 Word 2016 文件、 原則提示出現在訊息列] 和 [Backstage 檢視 ([**檔案**] 功能表\> **Info**)。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-119">For Excel 2016, PowerPoint 2016, and Word 2016 documents that are stored on a OneDrive for Business site or SharePoint Online site that's included in the DLP policy, the policy tip appears on the Message Bar and the Backstage view ( **File** menu \> **Info**).</span></span>
    
## <a name="add-user-notifications-to-a-dlp-policy"></a><span data-ttu-id="cc5b0-120">新增至 DLP 原則的使用者通知</span><span class="sxs-lookup"><span data-stu-id="cc5b0-120">Add user notifications to a DLP policy</span></span>

<span data-ttu-id="cc5b0-121">當您建立的 DLP 原則時、 電子郵件通知及原則提示屬於**使用者通知**] 區段。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-121">When you create a DLP policy, both email notifications and policy tips are part of the **User notifications** section.</span></span> 
  
1. <span data-ttu-id="cc5b0-122">移至 [ [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-122">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="cc5b0-p105">登入 Office 365 中，使用您工作或學校的帳戶。您現在是 Office 365 安全性&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-p105">Sign in to Office 365 using your work or school account. You're now in the Office 365 Security &amp; Compliance Center.</span></span>
    
3. <span data-ttu-id="cc5b0-125">安全性&amp;規範中心\>左導覽\>**資料外洩防護** \> **原則** \> **+ 建立原則**。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-125">In the Security &amp; Compliance Center \> left navigation \> **Data loss prevention** \> **Policy** \> **+ Create a policy**.</span></span>
    
    ![建立原則] 按鈕](media/b1e48a08-92e2-47ca-abdc-4341694ddc7c.png)
  
4. <span data-ttu-id="cc5b0-127">選擇會保護您需要的敏感資訊類型的 DLP 原則範本\>**下一步**。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-127">Choose the DLP policy template that protects the types of sensitive information that you need \> **Next**.</span></span>
    
    <span data-ttu-id="cc5b0-128">若要開始使用空的範本，選擇 [**自訂** \> **自訂原則** \> **下一步**。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-128">To start with an empty template, choose **Custom** \> **Custom policy** \> **Next**.</span></span>
    
5. <span data-ttu-id="cc5b0-129">命名原則\>**下一步**。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-129">Name the policy \> **Next**.</span></span>
    
6. <span data-ttu-id="cc5b0-130">若要選擇您想要保護的 DLP 原則的位置，請執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="cc5b0-130">To choose the locations that you want the DLP policy to protect, do one of the following:</span></span>
    
  - <span data-ttu-id="cc5b0-131">選擇**Office 365 中的所有位置** \> **下一步**。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-131">Choose **All locations in Office 365** \> **Next**.</span></span>
    
  - <span data-ttu-id="cc5b0-132">選擇 [**讓我選擇特定位置** \> **下一步**。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-132">Choose **Let me choose specific locations** \> **Next**.</span></span>
    
    <span data-ttu-id="cc5b0-133">若要包含或排除整個位置例如所有的 Exchange 電子郵件或 OneDrive 的所有帳戶，請開啟或關閉切換該位置的**狀態**。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-133">To include or exclude an entire location such as all Exchange email or all OneDrive accounts, switch the **Status** of that location on or off.</span></span> 
    
    <span data-ttu-id="cc5b0-134">若要加上只有特定的 SharePoint 網站或 OneDrive 帳戶，切換至**狀態**，和 [連結底下**加入**選擇特定網站或帳戶。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-134">To include only specific SharePoint sites or OneDrive accounts, switch the **Status** to on, and then click the links under **Include** to choose specific sites or accounts.</span></span> 
    
7. <span data-ttu-id="cc5b0-135">選擇 [**進階設定，可使用** \> **下一步**。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-135">Choose **Use advanced settings** \> **Next**.</span></span>
    
8. <span data-ttu-id="cc5b0-136">選擇 [ **+ 新增規則**]。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-136">Choose **+ New rule**.</span></span>
    
9. <span data-ttu-id="cc5b0-137">在**使用者通知**] 下的規則編輯器切換狀態。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-137">In the rule editor, under **User notifications**, switch the status on.</span></span>
    
    ![使用者通知] 區段中的規則編輯器](media/47705927-c60b-4054-a072-ab914f33d15d.png)
  
## <a name="options-for-configuring-email-notifications"></a><span data-ttu-id="cc5b0-139">設定電子郵件通知的選項</span><span class="sxs-lookup"><span data-stu-id="cc5b0-139">Options for configuring email notifications</span></span>

<span data-ttu-id="cc5b0-140">每個規則的 DLP 原則中，您可以：</span><span class="sxs-lookup"><span data-stu-id="cc5b0-140">For each rule in a DLP policy, you can:</span></span>
  
- <span data-ttu-id="cc5b0-p106">傳送通知給您選擇的人員。可能的人員包括內容擁有者、上次修改內容的人員、內容儲存所在網站的擁有者，或特定使用者。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-p106">Send the notification to the people you choose. These people can include the owner of the content, the person who last modified the content, the owner of the site where the content is stored, or a specific user.</span></span>
    
- <span data-ttu-id="cc5b0-p107">自訂使用 HTML 或權杖通知中包含的文字。請參閱下方] 區段中的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-p107">Customize the text that's included in the notification by using HTML or tokens. See the section below for more information.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="cc5b0-p108">僅為個別的收件者可以傳送電子郵件通知 — 不群組或通訊群組清單。> 新內容只會觸發的電子郵件通知。編輯現有的內容會觸發原則提示，但不是的電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-p108">Email notifications can be sent only to individual recipients—not groups or distribution lists. >  Only new content will trigger an email notification. Editing existing content will trigger policy tips but not an email notification.</span></span> 
  
![電子郵件通知選項](media/4e7b9500-2a78-44e6-9067-09f4bfd50301.png)
  
### <a name="default-email-notification"></a><span data-ttu-id="cc5b0-149">預設電子郵件通知</span><span class="sxs-lookup"><span data-stu-id="cc5b0-149">Default email notification</span></span>

<span data-ttu-id="cc5b0-p109">通知會有電子郵件、 或 「 存取封鎖 」 的文件的主旨行以所採取的動作，例如 「 通知 」"封鎖郵件"為開頭。關於文件通知時，通知郵件內文包含帶您至其中的文件的儲存和開啟文件、 原則提示的網站的連結其中您可以解決任何問題 （請參閱關於原則提示下的一節）。關於一則訊息通知時，通知包括附件形式郵件符合 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-p109">Notifications have a Subject line that begins with the action taken, such as "Notification", "Message Blocked" for email, or "Access Blocked" for documents. If the notification is about a document, the notification message body includes a link that takes you to the site where the document's stored and opens the policy tip for the document, where you can resolve any issues (see the section below about policy tips). If the notification is about a message, the notification includes as an attachment the message that matches a DLP policy.</span></span>
  
![通知訊息](media/35813d40-5fd8-425f-9624-55655e74fa6b.png)
  
<span data-ttu-id="cc5b0-p110">根據預設，通知會針對網站上的項目顯示如下文字。每條規則的通知文字都是分開設定的，因此顯示的文字將依其對應的規則而有所不同。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-p110">By default, notifications display text similar to the following for an item on a site. The notification text is configured separately for each rule, so the text that's displayed differs depending on which rule is matched.</span></span>
  
<span data-ttu-id="cc5b0-156">| |</span><span class="sxs-lookup"><span data-stu-id="cc5b0-156"></span></span>
|<span data-ttu-id="cc5b0-157">**如果 DLP 原則規則執行此動作...**</span><span class="sxs-lookup"><span data-stu-id="cc5b0-157">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="cc5b0-158">**然後 SharePoint 或 OneDrive for Business 文件的預設通知指出此...]**</span><span class="sxs-lookup"><span data-stu-id="cc5b0-158">**Then the default notification for SharePoint or OneDrive for Business documents says this…**</span></span>|<span data-ttu-id="cc5b0-159">**然後預設通知 for Outlook 訊息會指出這個...]**</span><span class="sxs-lookup"><span data-stu-id="cc5b0-159">**Then the default notification for Outlook messages says this…**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cc5b0-160">傳送通知，但不允許覆寫</span><span class="sxs-lookup"><span data-stu-id="cc5b0-160">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="cc5b0-161">此項目與您組織中的原則衝突。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-161">This item conflicts with a policy in your organization.</span></span>  <br/> |<span data-ttu-id="cc5b0-162">您的組織中的原則與您電子郵件訊息發生衝突。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-162">Your email message conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="cc5b0-163">封鎖存取、傳送通知，並允許覆寫</span><span class="sxs-lookup"><span data-stu-id="cc5b0-163">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="cc5b0-p111">您的組織中的原則與這個項目發生衝突。如果您未解決這個衝突，存取此檔案可能會遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-p111">This item conflicts with a policy in your organization. If you don't resolve this conflict, access to this file might be blocked.</span></span>  <br/> |<span data-ttu-id="cc5b0-p112">您的組織中的原則與您電子郵件訊息發生衝突。郵件未傳送給所有收件人。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-p112">Your email message conflicts with a policy in your organization. The message wasn't delivered to all recipients.</span></span>  <br/> |
|<span data-ttu-id="cc5b0-168">封鎖存取並傳送通知</span><span class="sxs-lookup"><span data-stu-id="cc5b0-168">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="cc5b0-p113">此項目與您組織中的原則衝突。封鎖除了項目擁有者、最後修改者和主要網站集合管理員以外的所有人對此項目的存取。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-p113">This item conflicts with a policy in your organization. Access to this item is blocked for everyone except its owner, last modifier, and the primary site collection administrator.</span></span>  <br/> |<span data-ttu-id="cc5b0-p114">您的組織中的原則與您電子郵件訊息發生衝突。郵件未傳送給所有收件人。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-p114">Your email message conflicts with a policy in your organization. The message wasn't delivered to all recipients.</span></span>  <br/> |
   
### <a name="custom-email-notification"></a><span data-ttu-id="cc5b0-173">自訂電子郵件通知</span><span class="sxs-lookup"><span data-stu-id="cc5b0-173">Custom email notification</span></span>

<span data-ttu-id="cc5b0-p115">您可以建立自訂電子郵件通知，而不是預設的電子郵件通知傳送給您的使用者或系統管理員。自訂電子郵件通知支援 HTML 和有 5000 個字元的限制。您可以使用 HTML 包含影像、 格式及其他商標通知中。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-p115">You can create a custom email notification instead of sending the default email notification to your end users or admins. The custom email notification supports HTML and has a 5,000-character limit. You can use HTML to include images, formatting, and other branding in the notification.</span></span>
  
<span data-ttu-id="cc5b0-p116">您也可以使用下列語彙基元來協助自訂電子郵件通知。這些語彙基元是由傳送通知中的特定資訊所取代的變數。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-p116">You can also use the following tokens to help customize the email notification. These tokens are variables that are replaced by specific information in the notification that's sent.</span></span>
  
<span data-ttu-id="cc5b0-179">| |</span><span class="sxs-lookup"><span data-stu-id="cc5b0-179"></span></span>
|<span data-ttu-id="cc5b0-180">**Token**</span><span class="sxs-lookup"><span data-stu-id="cc5b0-180">**Token**</span></span>|<span data-ttu-id="cc5b0-181">**描述**</span><span class="sxs-lookup"><span data-stu-id="cc5b0-181">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cc5b0-182">%%Appliedactions %%</span><span class="sxs-lookup"><span data-stu-id="cc5b0-182">%%AppliedActions%%</span></span>  <br/> |<span data-ttu-id="cc5b0-183">套用至內容動作。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-183">The actions applied to the content.</span></span>  <br/> |
|<span data-ttu-id="cc5b0-184">%%Contenturl %%</span><span class="sxs-lookup"><span data-stu-id="cc5b0-184">%%ContentURL%%</span></span>  <br/> |<span data-ttu-id="cc5b0-185">在 SharePoint Online 網站或 OneDrive 文件以供商務網站的 URL。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-185">The URL of the document on the SharePoint Online site or OneDrive for Business site.</span></span>  <br/> |
|<span data-ttu-id="cc5b0-186">%%Matchedconditions %%</span><span class="sxs-lookup"><span data-stu-id="cc5b0-186">%%MatchedConditions%%</span></span>  <br/> |<span data-ttu-id="cc5b0-p117">已符合內容的條件。使用此 token 來通知人的內容可能的問題。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-p117">The conditions that were matched by the content. Use this token to inform people of possible issues with the content.</span></span>  <br/> |
   
![通知訊息顯示出現在 token 的位置](media/cd3f36b3-40db-4f30-99e4-190750bd1955.png)
  
## <a name="options-for-configuring-policy-tips"></a><span data-ttu-id="cc5b0-190">設定原則提示的選項</span><span class="sxs-lookup"><span data-stu-id="cc5b0-190">Options for configuring policy tips</span></span>

<span data-ttu-id="cc5b0-191">對於 DLP 原則中的每個規則，您可以設定原則提示，以：</span><span class="sxs-lookup"><span data-stu-id="cc5b0-191">For each rule in a DLP policy, you can configure policy tips to:</span></span>
  
- <span data-ttu-id="cc5b0-p118">只是通知之人員的內容相衝突與 DLP 原則，以便他們可以採取動作以解決衝突。您可以使用的預設文字 （請參閱下表） 或輸入您的組織特定原則相關的自訂文字。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-p118">Simply notify the person that the content conflicts with a DLP policy, so that they can take action to resolve the conflict. You can use the default text (see the tables below) or enter custom text about your organization's specific policies.</span></span>
    
- <span data-ttu-id="cc5b0-p119">允許人員覆寫 DLP 原則。(選擇性) 您可以：</span><span class="sxs-lookup"><span data-stu-id="cc5b0-p119">Allow the person to override the DLP policy. Optionally, you can:</span></span>
    
  - <span data-ttu-id="cc5b0-p120">需要受邀者輸入來覆寫原則業務上的理由。記錄此資訊及以便在 [**報告**] 區段中的安全性 DLP 報告中檢視&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-p120">Require the person to enter a business justification for overriding the policy. This information is logged and you can view it in the DLP reports in the **Reports** section of the Security &amp; Compliance Center.</span></span> 
    
  - <span data-ttu-id="cc5b0-p121">允許人員回報誤判並覆寫 DLP 原則。這項資訊也會記錄在報告中，以便您使用誤判來微調您的規則。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-p121">Allow the person to report a false positive and override the DLP policy. This information is also logged for reporting, so that you can use false positives to fine tune your rules.</span></span>
    
![原則提示選項](media/0d2f2c68-028a-4900-afe6-1d9fce5303ef.png)
  
<span data-ttu-id="cc5b0-201">例如，您可能需要偵測個人識別資訊 (PII) 的 DLP 原則套用至 OneDrive for Business 的網站與此原則有三個規則：</span><span class="sxs-lookup"><span data-stu-id="cc5b0-201">For example, you may have a DLP policy applied to OneDrive for Business sites that detects personally identifiable information (PII), and this policy has three rules:</span></span>
  
1. <span data-ttu-id="cc5b0-p122">先規則： 如果在文件中偵測到的機密資訊少於五個執行個體與組織內的人員共用文件，**將通知傳送**巨集指令會顯示原則提示。原則提示不覆寫選項都因為此規則會只通知人與未封鎖存取。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-p122">First rule: If fewer than five instances of this sensitive information are detected in a document, and the document is shared with people inside the organization, the **Send a notification** action displays a policy tip. For policy tips, no override options are necessary because this rule is simply notifying people and not blocking access.</span></span> 
    
2. <span data-ttu-id="cc5b0-p123">第二個規則： 如果大於文件中偵測到的機密資訊的五個執行個體和文件共用與組織內的人員，**封鎖內容的存取權**巨集指令會限制檔案和**的權限將通知傳送**巨集指令可讓使用者以提供業務上理由，來覆寫此規則的動作。貴組織的業務有時需要內部人員共用 PII 資料，而且不想您要封鎖這項工作的 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-p123">Second rule: If greater than five instances of this sensitive information are detected in a document, and the document is shared with people inside the organization, the **Block access to content** action restricts the permissions for the file, and the **Send a notification** action allows people to override the actions in this rule by providing a business justification. Your organization's business sometimes requires internal people to share PII data, and you don't want your DLP policy to block this work.</span></span> 
    
3. <span data-ttu-id="cc5b0-p124">第三規則： 如果大於文件中偵測到的機密資訊的五個執行個體和與組織外部人員共用文件、**封鎖內容的存取權**巨集指令會限制檔案和**的權限將通知傳送**巨集指令不允許覆寫此規則的動作因為外部共用資訊的人員。在任何情況下應該在組織中的人員允許共用組織外的 PII 資料。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-p124">Third rule: If greater than five instances of this sensitive information are detected in a document, and the document is shared with people outside the organization, the **Block access to content** action restricts the permissions for the file, and the **Send a notification** action does not allow people to override the actions in this rule because the information is shared externally. Under no circumstances should people in your organization be allowed to share PII data outside the organization.</span></span> 
    
<span data-ttu-id="cc5b0-208">以下提供一些細節，幫助您瞭解如何使用原則提示來覆寫規則：</span><span class="sxs-lookup"><span data-stu-id="cc5b0-208">Here are some fine points to understand about using a policy tip to override a rule:</span></span>
  
- <span data-ttu-id="cc5b0-209">若要覆寫的選項是每個規則，並會覆寫所有在 （除了傳送的通知，不能覆寫） 的規則動作。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-209">The option to override is per rule, and it overrides all of the actions in the rule (except sending a notification, which can't be overridden).</span></span>
    
- <span data-ttu-id="cc5b0-p125">是以符合的 DLP 原則中數個規則的內容，但只限制最大、 最高優先順序規則從原則提示將會顯示。例如，原則提示從會透過直接傳送通知的規則從原則提示顯示組塊內容的存取權的規則。這可防止看到重疊顯示原則提示的人員。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-p125">It's possible for content to match several rules in a DLP policy, but only the policy tip from the most restrictive, highest-priority rule will be shown. For example, a policy tip from a rule that blocks access to content will be shown over a policy tip from a rule that simply sends a notification. This prevents people from seeing a cascade of policy tips.</span></span>
    
- <span data-ttu-id="cc5b0-213">如果最嚴格規則中的原則提示允許人員覆寫規則，則覆寫此規則也將會覆寫內容符合的任何其他規則。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-213">If the policy tips in the most restrictive rule allow people to override the rule, then overriding this rule also overrides any other rules that the content matched.</span></span>
    
## <a name="policy-tips-on-onedrive-for-business-sites-and-sharepoint-online-sites"></a><span data-ttu-id="cc5b0-214">商務用 OneDrive 網站和 SharePoint Online 網站上的原則提示</span><span class="sxs-lookup"><span data-stu-id="cc5b0-214">Policy tips on OneDrive for Business sites and SharePoint Online sites</span></span>

<span data-ttu-id="cc5b0-215">當 OneDrive for Business 站台或 SharePoint Online 網站上的文件符合的 DLP 原則的規則，該規則使用原則提示時，原則提示就會顯示特殊圖示文件：</span><span class="sxs-lookup"><span data-stu-id="cc5b0-215">When a document on a OneDrive for Business site or SharePoint Online site matches a rule in a DLP policy, and that rule uses policy tips, the policy tips display special icons on the document:</span></span>
  
1. <span data-ttu-id="cc5b0-216">如果規則傳送檔案的相關通知，將會出現警告圖示。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-216">If the rule sends a notification about the file, the warning icon appears.</span></span>
    
2. <span data-ttu-id="cc5b0-217">如果規則封鎖對文件的存取，則會出現封鎖圖示。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-217">If the rule blocks access to the document, the blocked icon appears.</span></span>
    
![在文件中的 OneDrive 帳戶的原則提示圖示](media/d3e9f772-03f9-4d28-82f8-3064784332a2.png)
  
<span data-ttu-id="cc5b0-219">文件上執行動作，您可以選取項目\>選擇**資訊**![資訊窗格圖示](media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png)要開啟詳細資料窗格中的頁面右上角\>**檢視原則提示**。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-219">To take action on a document, you can select an item \> choose **Information**![Information pane icon](media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) in the upper-right corner of the page to open the details pane \> **View policy tip**.</span></span>
  
<span data-ttu-id="cc5b0-220">原則提示列出內容、 問題以及如果原則提示來設定這些選項，您可以選擇**解析**，然後**會覆寫**原則提示或**報告**為誤判。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-220">The policy tip lists the issues with the content, and if the policy tips are configured with these options, you can choose **Resolve**, and then **Override** the policy tip or **Report** a false positive.</span></span> 
  
![資訊窗格顯示原則提示](media/0a191e70-80f0-4702-90f4-7a5b7aabcaab.png)
  
![具有覆寫選項的原則提示](media/e250bff9-41d5-4ce4-82ea-1dc2d043fab1.png)
  
<span data-ttu-id="cc5b0-p126">DLP 原則會同步處理至網站，以便定期以非同步方式根據它們來評估內容，因此從您建立 DLP 原則，到您開始看見原則提示，其間可能會有短暫的延遲。從您解決或覆寫原則提示，到網站上的文件圖示消失，其間也可能會有類似的延遲。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-p126">DLP policies are synced to sites and contented is evaluated against them periodically and asynchronously, so there may be a short delay between the time you create the DLP policy and the time you begin to see policy tips. There may be a similar delay from when you resolve or override a policy tip to when the icon on the document on the site goes away.</span></span>
  
### <a name="default-text-for-policy-tips-on-sites"></a><span data-ttu-id="cc5b0-225">網站上的預設原則提示文字</span><span class="sxs-lookup"><span data-stu-id="cc5b0-225">Default text for policy tips on sites</span></span>

<span data-ttu-id="cc5b0-p127">根據預設，原則提示會針對網站上的項目顯示如下文字。每條規則的通知文字都是分開設定的，因此顯示的文字將依其對應的規則而有所不同。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-p127">By default, policy tips display text similar to the following for an item on a site. The notification text is configured separately for each rule, so the text that's displayed differs depending on which rule is matched.</span></span>
  
<span data-ttu-id="cc5b0-228">| |</span><span class="sxs-lookup"><span data-stu-id="cc5b0-228"></span></span>
|<span data-ttu-id="cc5b0-229">**如果 DLP 原則規則執行此動作...**</span><span class="sxs-lookup"><span data-stu-id="cc5b0-229">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="cc5b0-230">**預設原則提示就會指出...**</span><span class="sxs-lookup"><span data-stu-id="cc5b0-230">**Then the default policy tip says this…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cc5b0-231">傳送通知，但不允許覆寫</span><span class="sxs-lookup"><span data-stu-id="cc5b0-231">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="cc5b0-232">此項目與您組織中的原則衝突。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-232">This item conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="cc5b0-233">封鎖存取、傳送通知，並允許覆寫</span><span class="sxs-lookup"><span data-stu-id="cc5b0-233">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="cc5b0-p128">您的組織中的原則與這個項目發生衝突。如果您未解決這個衝突，存取此檔案可能會遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-p128">This item conflicts with a policy in your organization. If you don't resolve this conflict, access to this file might be blocked.</span></span>  <br/> |
|<span data-ttu-id="cc5b0-236">封鎖存取並傳送通知</span><span class="sxs-lookup"><span data-stu-id="cc5b0-236">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="cc5b0-p129">此項目與您組織中的原則衝突。封鎖除了項目擁有者、最後修改者和主要網站集合管理員以外的所有人對此項目的存取。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-p129">This item conflicts with a policy in your organization. Access to this item is blocked for everyone except its owner, last modifier, and the primary site collection administrator.</span></span>  <br/> |
   
### <a name="custom-text-for-policy-tips-on-sites"></a><span data-ttu-id="cc5b0-239">自訂的網站上的原則提示文字</span><span class="sxs-lookup"><span data-stu-id="cc5b0-239">Custom text for policy tips on sites</span></span>

<span data-ttu-id="cc5b0-p130">您可以自訂分開的電子郵件通知的原則提示的文字。不同的電子郵件通知 （如上一節） 的自訂文字、 自訂原則提示文字不接受 HTML 或權杖。而是自訂原則提示的文字是純文字只是 256 個字元限制。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-p130">You can customize the text for policy tips separately from the email notification. Unlike custom text for email notifications (see above section), custom text for policy tips does not accept HTML or tokens. Instead, custom text for policy tips is plain text only with a 256-character limit.</span></span>
  
## <a name="policy-tips-in-outlook-on-the-web-and-outlook-2013-and-later"></a><span data-ttu-id="cc5b0-243">在 web 上的 Outlook 和 Outlook 2013 及更新版本中的原則提示</span><span class="sxs-lookup"><span data-stu-id="cc5b0-243">Policy tips in Outlook on the web and Outlook 2013 and later</span></span>

<span data-ttu-id="cc5b0-p131">當您在撰寫網站上的 Outlook 和 Outlook 2013 中的新電子郵件之後，如果將會看到原則提示新增符合的 DLP 原則的規則之內容的但該規則使用原則提示。時所包含之郵件的郵件收件者] 上方會顯示原則提示。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-p131">When you compose a new email in Outlook on the web and Outlook 2013 and later, you'll see a policy tip if you add content that matches a rule in a DLP policy, and that rule uses policy tips. The policy tip appears at the top of the message, above the recipients, while the message is being composed.</span></span>
  
![上方的所組成的郵件原則提示](media/9b3b6b74-17c5-4562-82d5-d17ecaaa8d95.png)
  
<span data-ttu-id="cc5b0-247">原則提示的工作是否如下所示的機密資訊會出現在郵件內文、 主旨行或甚至是為郵件附件。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-247">Policy tips work whether the sensitive information appears in the message body, subject line, or even a message attachment as shown here.</span></span>
  
![顯示附件相衝突與 DLP 原則的原則提示](media/59ae6655-215f-47d9-ad1d-39c0d1e61740.png)
  
<span data-ttu-id="cc5b0-249">如果原則提示設定為允許覆寫，您可以選擇 [**顯示詳細資料** \> **覆寫**\>輸入業務上理由或報告為誤判\>**覆寫**。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-249">If the policy tips are configured to allow override, you can choose **Show Details** \> **Override** \> enter a business justification or report a false positive \> **Override**.</span></span>
  
![展開顯示覆寫] 選項的郵件原則提示](media/28bfb997-48a6-41f0-8682-d5e62488458a.png)
  
![您將可以覆寫原則提示的原則提示] 對話方塊](media/f97e836c-04bd-44b4-aec6-ed9526ea31f8.png)
  
<span data-ttu-id="cc5b0-252">請注意當您將機密資訊新增至電子郵件時，有可能是新增的機密資訊時與該原則提示出現時之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-252">Note that when you add sensitive information to an email, there may be latency between when the sensitive information is added and when the policy tip appears.</span></span>
  
### <a name="policy-tips-in-the-exchange-admin-center-vs-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="cc5b0-253">原則提示的 Exchange 系統管理中心和 Office 365 安全性比較&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="cc5b0-253">Policy tips in the Exchange Admin Center vs. the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="cc5b0-p132">原則提示可以搭配使用其中一個與 DLP 原則及郵件流程規則建立在 Exchange 系統管理中心，或建立的 Office 365 安全性 DLP 原則&amp;規範中心，但不可同時。這是因為這些原則會儲存在不同的位置，但只能從單一位置可繪製原則提示。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-p132">Policy tips can work either with DLP policies and mail flow rules created in the Exchange Admin Center, or with DLP policies created in the Office 365 Security &amp; Compliance Center, but not both. This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="cc5b0-p133">如果您已在 Exchange 系統管理中心，任何您在 Office 365 安全性設定的原則提示設定原則提示&amp;規範中心就不會出現在網路上的 Outlook 和 Outlook 2013 及更新版本直到您關閉 Exchange 中的提示中的使用者系統管理中心。這可確保您目前的 Exchange 傳輸規則會繼續運作直到您選擇切換至 Office 365 安全性&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-p133">If you've configured policy tips in the Exchange Admin Center, any policy tips that you configure in the Office 365 Security &amp; Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange Admin Center. This ensures that your current Exchange transport rules will continue to work until you choose to switch over to the Office 365 Security &amp; Compliance Center.</span></span>
  
<span data-ttu-id="cc5b0-258">請注意，雖然只從單一位置可繪製原則提示的電子郵件通知一律傳送，即使您在 Office 365 安全性使用 DLP 原則&amp;規範中心及 Exchange 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-258">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Office 365 Security &amp; Compliance Center and the Exchange Admin Center.</span></span>
  
### <a name="default-text-for-policy-tips-in-email"></a><span data-ttu-id="cc5b0-259">預設的電子郵件中的原則提示的文字</span><span class="sxs-lookup"><span data-stu-id="cc5b0-259">Default text for policy tips in email</span></span>

<span data-ttu-id="cc5b0-260">預設原則提示會顯示類似下列的電子郵件的文字。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-260">By default, policy tips display text similar to the following for email.</span></span>
  
<span data-ttu-id="cc5b0-261">| |</span><span class="sxs-lookup"><span data-stu-id="cc5b0-261"></span></span>
|<span data-ttu-id="cc5b0-262">**如果 DLP 原則規則執行此動作...**</span><span class="sxs-lookup"><span data-stu-id="cc5b0-262">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="cc5b0-263">**預設原則提示就會指出...**</span><span class="sxs-lookup"><span data-stu-id="cc5b0-263">**Then the default policy tip says this…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cc5b0-264">傳送通知，但不允許覆寫</span><span class="sxs-lookup"><span data-stu-id="cc5b0-264">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="cc5b0-265">您電子郵件與衝突貴組織中的原則。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-265">Your email conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="cc5b0-266">封鎖存取、傳送通知，並允許覆寫</span><span class="sxs-lookup"><span data-stu-id="cc5b0-266">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="cc5b0-267">您電子郵件與衝突貴組織中的原則。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-267">Your email conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="cc5b0-268">封鎖存取並傳送通知</span><span class="sxs-lookup"><span data-stu-id="cc5b0-268">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="cc5b0-269">您電子郵件與衝突貴組織中的原則。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-269">Your email conflicts with a policy in your organization.</span></span>  <br/> |
   
## <a name="policy-tips-in-excel-2016-powerpoint-2016-and-word-2016"></a><span data-ttu-id="cc5b0-270">Excel 2016、PowerPoint 2016 和 Word 2016 中的原則提示</span><span class="sxs-lookup"><span data-stu-id="cc5b0-270">Policy tips in Excel 2016, PowerPoint 2016, and Word 2016</span></span>

<span data-ttu-id="cc5b0-p134">當人員在桌面版的 Excel 2016、PowerPoint 2016 和 Word 2016 上使用敏感內容時，原則提示可在內容違反 DLP 原則時即時通知他們。這需要：</span><span class="sxs-lookup"><span data-stu-id="cc5b0-p134">When people work with sensitive content in the desktop versions of Excel 2016, PowerPoint 2016, and Word 2016, policy tips can notify them in real time that the content conflicts with a DLP policy. This requires that:</span></span>
  
- <span data-ttu-id="cc5b0-273">Office 文件儲存在商務用 OneDrive 網站或 SharePoint Online 網站上。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-273">The Office document is stored on a OneDrive for Business site or SharePoint Online site.</span></span>
    
- <span data-ttu-id="cc5b0-274">設定為使用原則提示的 DLP 原則隨附的網站。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-274">The site is included in a DLP policy that's configured to use policy tips.</span></span>
    
<span data-ttu-id="cc5b0-275">這些 Office 2016 桌上型程式自動同步處理直接從 Office 365 的 DLP 原則並再掃描文件以確保它們未與 DLP 原則衝突以及即時顯示原則提示。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-275">These Office 2016 desktop programs automatically sync DLP policies directly from Office 365, and then scan your documents to ensure that they don't conflict with your DLP policies and display policy tips in real time.</span></span>
  
<span data-ttu-id="cc5b0-276">根據您在 DLP 原則中設定原則提示的方式，人員可以選擇直接略過原則提示、在具備或未具備業務理由的情況下覆寫原則，或回報誤判。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-276">Depending on how you configure the policy tips in the DLP policy, people can choose to simply ignore the policy tip, override the policy with or without a business justification, or report a false positive.</span></span>
  
<span data-ttu-id="cc5b0-277">原則提示會出現在訊息列上。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-277">Policy tips appear on the Message Bar.</span></span>
  
![訊息列會顯示 Excel 2016 中的原則提示](media/7002ff54-1656-4a6c-993f-37427d6508c8.png)
  
<span data-ttu-id="cc5b0-279">和原則提示也會出現在 Backstage 檢視 （在 [**檔案**] 索引標籤）。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-279">And policy tips also appear in the Backstage view (on the **File** tab).</span></span> 
  
![Backstage 會顯示 Excel 2016 中的原則提示](media/44c561f6-8f3f-4878-b1b0-b7543f8a4120.png)
  
<span data-ttu-id="cc5b0-281">如果原則秘訣 （英文） 的 DLP 原則來設定這些選項，您可以選擇**解決****覆寫**原則提示或**報告**為誤判。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-281">If policy tips in the DLP policy are configured with these options, you can choose **Resolve** to **Override** a policy tip or **Report** a false positive.</span></span> 
  
![Excel 2016 的 Backstage 中的原則提示選項](media/5b3857ba-907e-456e-ae43-888b594c049c.png)
  
<span data-ttu-id="cc5b0-p135">在每個這些 Office 2016 桌上型程式，可以選擇人員關閉原則提示。如果已關閉，是簡單通知的原則提示不會出現 [訊息列或 Backstage] 檢視 （在 [**檔案**] 索引標籤）。不過，仍會顯示關於封鎖和覆寫原則提示，並他們仍會收到電子郵件通知。此外，關閉 [原則提示不會不去除從任何已套用至其的 DLP 原則的文件。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-p135">In each of these Office 2016 desktop programs, people can choose to turn off policy tips. If turned off, policy tips that are simple notifications will not appear on the Message Bar or Backstage view (on the **File** tab). However, policy tips about blocking and overriding will still appear, and they will still receive the email notification. In addition, turning off policy tips does not exempt the document from any DLP policies that have been applied to it.</span></span> 
  
### <a name="default-text-for-policy-tips-in-excel-2016-powerpoint-2016-and-word-2016"></a><span data-ttu-id="cc5b0-287">Excel 2016、PowerPoint 2016 和 Word 2016 中的預設原則提示文字</span><span class="sxs-lookup"><span data-stu-id="cc5b0-287">Default text for policy tips in Excel 2016, PowerPoint 2016, and Word 2016</span></span>

<span data-ttu-id="cc5b0-p136">根據預設，原則提示會在已開啟文件的訊息列和 Backstage 檢視上顯示如下文字。每條規則的通知文字都是分開設定的，因此顯示的文字將依其對應的規則而有所不同。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-p136">By default, policy tips display text similar to the following on the Message Bar and Backstage view of an open document. The notification text is configured separately for each rule, so the text that's displayed differs depending on which rule is matched.</span></span>
  
<span data-ttu-id="cc5b0-290">| |</span><span class="sxs-lookup"><span data-stu-id="cc5b0-290"></span></span>
|<span data-ttu-id="cc5b0-291">**如果 DLP 原則規則執行此動作...**</span><span class="sxs-lookup"><span data-stu-id="cc5b0-291">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="cc5b0-292">**預設原則提示就會指出...**</span><span class="sxs-lookup"><span data-stu-id="cc5b0-292">**Then the default policy tip says this…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cc5b0-293">傳送通知，但不允許覆寫</span><span class="sxs-lookup"><span data-stu-id="cc5b0-293">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="cc5b0-p137">此檔案與衝突貴組織中的原則。移至 [**檔案**] 功能表中的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-p137">This file conflicts with a policy in your organization. Go to the **File** menu for more information.  </span></span><br/> |
|<span data-ttu-id="cc5b0-296">封鎖存取、傳送通知，並允許覆寫</span><span class="sxs-lookup"><span data-stu-id="cc5b0-296">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="cc5b0-p138">此檔案與衝突貴組織中的原則。如果您未解決這個衝突，存取此檔案可能會遭到封鎖。移至 [**檔案**] 功能表中的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-p138">This file conflicts with a policy in your organization. If you don't resolve this conflict, access to this file might be blocked. Go to the **File** menu for more information.  </span></span><br/> |
|<span data-ttu-id="cc5b0-300">封鎖存取並傳送通知</span><span class="sxs-lookup"><span data-stu-id="cc5b0-300">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="cc5b0-p139">此檔案與衝突貴組織中的原則。如果您未解決這個衝突，存取此檔案可能會遭到封鎖。移至 [**檔案**] 功能表中的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-p139">This file conflicts with a policy in your organization. If you don't resolve this conflict, access to this file might be blocked. Go to the **File** menu for more information.  </span></span><br/> |
   
### <a name="custom-text-for-policy-tips-in-excel-2016-powerpoint-2016-and-word-2016"></a><span data-ttu-id="cc5b0-304">Excel 2016、 PowerPoint 2016 和 Word 2016 中的自訂文字原則提示</span><span class="sxs-lookup"><span data-stu-id="cc5b0-304">Custom text for policy tips in Excel 2016, PowerPoint 2016, and Word 2016</span></span>

<span data-ttu-id="cc5b0-p140">您可以自訂分開的電子郵件通知的原則提示的文字。不同的電子郵件通知 （如上一節） 的自訂文字、 自訂原則提示文字不接受 HTML 或權杖。而是自訂原則提示的文字是純文字只是 256 個字元限制。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-p140">You can customize the text for policy tips separately from the email notification. Unlike custom text for email notifications (see above section), custom text for policy tips does not accept HTML or tokens. Instead, custom text for policy tips is plain text only with a 256-character limit.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="cc5b0-308">其他資訊</span><span class="sxs-lookup"><span data-stu-id="cc5b0-308">More information</span></span>

- [<span data-ttu-id="cc5b0-309">資料外洩防護原則概觀</span><span class="sxs-lookup"><span data-stu-id="cc5b0-309">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)
    
- [<span data-ttu-id="cc5b0-310">從範本建立 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="cc5b0-310">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
    
- [<span data-ttu-id="cc5b0-311">建立 DLP 原則來保護具有 FCI 或其他屬性的文件</span><span class="sxs-lookup"><span data-stu-id="cc5b0-311">Create a DLP policy to protect documents with FCI or other properties</span></span>](protect-documents-that-have-fci-or-other-properties.md)
    
- [<span data-ttu-id="cc5b0-312">DLP 原則範本包含哪些內容</span><span class="sxs-lookup"><span data-stu-id="cc5b0-312">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="cc5b0-313">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="cc5b0-313">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
    

