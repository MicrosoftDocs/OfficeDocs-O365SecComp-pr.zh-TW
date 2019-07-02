---
title: 針對 DLP 原則傳送電子郵件通知並顯示原則提示
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/14/2019
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleNotifyUser
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: '原則提示是當有人使用與 DLP 原則衝突的內容時, 所出現的通知或警告。 您可以使用電子郵件通知和原則提示來增加知名度, 並協助人們瞭解組織的原則。 您也可以讓人員選擇覆寫原則, 讓他們在有有效的業務需求或原則偵測到假肯定時, 不會封鎖。 '
ms.openlocfilehash: 4de22c8ad8a45cf1489e72516d30f078889774e3
ms.sourcegitcommit: 9df5bf99c1860ace0c5cc90647733d075be412ad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2019
ms.locfileid: "34948901"
---
# <a name="send-email-notifications-and-show-policy-tips-for-dlp-policies"></a><span data-ttu-id="66860-105">針對 DLP 原則傳送電子郵件通知並顯示原則提示</span><span class="sxs-lookup"><span data-stu-id="66860-105">Send email notifications and show policy tips for DLP policies</span></span>

<span data-ttu-id="66860-106">您可以使用資料遺失防護 (DLP) 原則來識別、監視和保護 Office 365 之間的機密資訊。</span><span class="sxs-lookup"><span data-stu-id="66860-106">You can use a data loss prevention (DLP) policy to identify, monitor, and protect sensitive information across Office 365.</span></span> <span data-ttu-id="66860-107">您想要讓組織中使用此敏感資訊的人員遵守您的 DLP 原則, 但您不想要封鎖它們, 就無法讓他們完成工作。</span><span class="sxs-lookup"><span data-stu-id="66860-107">You want people in your organization who work with this sensitive information to stay compliant with your DLP policies, but you don't want to block them unnecessarily from getting their work done.</span></span> <span data-ttu-id="66860-108">這是電子郵件通知和原則提示可以協助的地方。</span><span class="sxs-lookup"><span data-stu-id="66860-108">This is where email notifications and policy tips can help.</span></span>
  
![訊息列會顯示 Excel 2016 中的原則提示](media/7002ff54-1656-4a6c-993f-37427d6508c8.png)
  
<span data-ttu-id="66860-110">原則提示是當有人使用與 DLP 原則衝突的內容時出現的通知或警告, 例如, 像是個人身分識別資訊 (PII) 的商務用 OneDrive 網站上的 Excel 活頁簿等內容, 也就是與外部使用者共用。</span><span class="sxs-lookup"><span data-stu-id="66860-110">A policy tip is a notification or warning that appears when someone is working with content that conflicts with a DLP policy—for example, content like an Excel workbook on a OneDrive for Business site that contains personally identifiable information (PII) and is shared with an external user.</span></span>
  
<span data-ttu-id="66860-111">您可以使用電子郵件通知和原則提示來增加知名度, 並協助人們瞭解組織的原則。</span><span class="sxs-lookup"><span data-stu-id="66860-111">You can use email notifications and policy tips to increase awareness and help educate people about your organization's policies.</span></span> <span data-ttu-id="66860-112">您也可以讓人員選擇覆寫原則, 讓他們在有有效的業務需求或原則偵測到假肯定時, 不會封鎖。</span><span class="sxs-lookup"><span data-stu-id="66860-112">You can also give people the option to override the policy, so that they're not blocked if they have a valid business need or if the policy is detecting a false positive.</span></span>
  
<span data-ttu-id="66860-113">在 Office 365 安全&amp;規範中心中, 當您建立 DLP 原則時, 您可以將使用者通知設定為:</span><span class="sxs-lookup"><span data-stu-id="66860-113">In the Office 365 Security &amp; Compliance Center, when you create a DLP policy, you can configure the user notifications to:</span></span>
  
- <span data-ttu-id="66860-114">傳送電子郵件通知給您選擇以描述問題的人員。</span><span class="sxs-lookup"><span data-stu-id="66860-114">Send an email notification to the people you choose that describes the issue.</span></span>
    
- <span data-ttu-id="66860-115">顯示與 DLP 原則衝突之內容的原則提示:</span><span class="sxs-lookup"><span data-stu-id="66860-115">Display a policy tip for content that conflicts with the DLP policy:</span></span>
    
  - <span data-ttu-id="66860-116">針對 Outlook 網頁版和 Outlook 2013 及更新版本中的電子郵件, 在撰寫郵件時, 郵件的頂端會出現原則提示。</span><span class="sxs-lookup"><span data-stu-id="66860-116">For email in Outlook on the web and Outlook 2013 and later, the policy tip appears at the top of a message above the recipients while the message is being composed.</span></span>
    
  - <span data-ttu-id="66860-117">對於商務用 OneDrive 帳戶或 SharePoint Online 網站中的檔, 原則提示會以出現在專案上的警告圖示來表示。</span><span class="sxs-lookup"><span data-stu-id="66860-117">For documents in a OneDrive for Business account or SharePoint Online site, the policy tip is indicated by a warning icon that appears on the item.</span></span> <span data-ttu-id="66860-118">若要查看詳細資訊, 您可以選取專案, 然後在\*\*\*\* ![頁面的右上角](media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png)選擇 [資訊資訊窗格] 圖示, 以開啟 [詳細資料] 窗格。</span><span class="sxs-lookup"><span data-stu-id="66860-118">To view more information, you can select an item and then choose **Information** ![Information pane icon](media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) in the upper-right corner of the page to open the details pane.</span></span> 
    
  - <span data-ttu-id="66860-119">如果是儲存在 DLP 原則所包含的商務用 OneDrive 網站或 SharePoint Online 網站上的 Excel、PowerPoint 及 Word 檔, 則原則提示會出現在訊息列和 Backstage 檢視 ([檔案] 功能表\*\*\*\* \> **資訊**) 上。</span><span class="sxs-lookup"><span data-stu-id="66860-119">For Excel, PowerPoint, and Word documents that are stored on a OneDrive for Business site or SharePoint Online site that's included in the DLP policy, the policy tip appears on the Message Bar and the Backstage view ( **File** menu \> **Info**).</span></span>
    
## <a name="add-user-notifications-to-a-dlp-policy"></a><span data-ttu-id="66860-120">將使用者通知新增至 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="66860-120">Add user notifications to a DLP policy</span></span>

<span data-ttu-id="66860-121">當您建立 DLP 原則時, 電子郵件通知和原則提示都會是 [**使用者通知**] 一節中的一部分。</span><span class="sxs-lookup"><span data-stu-id="66860-121">When you create a DLP policy, both email notifications and policy tips are part of the **User notifications** section.</span></span> 
  
1. <span data-ttu-id="66860-122">移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="66860-122">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="66860-123">使用公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="66860-123">Sign in to Office 365 using your work or school account.</span></span> <span data-ttu-id="66860-124">您現在是在 Office 365 安全性&amp;與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="66860-124">You're now in the Office 365 Security &amp; Compliance Center.</span></span>
    
3. <span data-ttu-id="66860-125">在&amp;安全性與合規性\>中心左側導覽\> **資料遺失防護** \> **原則** \> **+ 建立原則**。</span><span class="sxs-lookup"><span data-stu-id="66860-125">In the Security &amp; Compliance Center \> left navigation \> **Data loss prevention** \> **Policy** \> **+ Create a policy**.</span></span>
    
    ![[建立原則] 按鈕](media/b1e48a08-92e2-47ca-abdc-4341694ddc7c.png)
  
4. <span data-ttu-id="66860-127">選擇保護您\> **接下來**所需之敏感資訊類型的 DLP 原則範本。</span><span class="sxs-lookup"><span data-stu-id="66860-127">Choose the DLP policy template that protects the types of sensitive information that you need \> **Next**.</span></span>
    
    <span data-ttu-id="66860-128">若要以空白範本開始, 請選擇 [**自** \> **定義原則** \> **] [下一步]**。</span><span class="sxs-lookup"><span data-stu-id="66860-128">To start with an empty template, choose **Custom** \> **Custom policy** \> **Next**.</span></span>
    
5. <span data-ttu-id="66860-129">將原則\>命名為 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="66860-129">Name the policy \> **Next**.</span></span>
    
6. <span data-ttu-id="66860-130">若要選擇您想要讓 DLP 原則保護的位置, 請執行下列其中一項操作:</span><span class="sxs-lookup"><span data-stu-id="66860-130">To choose the locations that you want the DLP policy to protect, do one of the following:</span></span>
    
  - <span data-ttu-id="66860-131">選擇 [ \> **下一步]\*\*\*\*的 Office 365 中的所有位置**。</span><span class="sxs-lookup"><span data-stu-id="66860-131">Choose **All locations in Office 365** \> **Next**.</span></span>
    
  - <span data-ttu-id="66860-132">選擇 [**下一步]**。 \*\*\*\* \></span><span class="sxs-lookup"><span data-stu-id="66860-132">Choose **Let me choose specific locations** \> **Next**.</span></span>
    
    <span data-ttu-id="66860-133">若要包含或排除整個位置 (例如所有 Exchange 電子郵件或所有 OneDrive 帳戶), 請開啟或關閉該位置的**狀態**。</span><span class="sxs-lookup"><span data-stu-id="66860-133">To include or exclude an entire location such as all Exchange email or all OneDrive accounts, switch the **Status** of that location on or off.</span></span> 
    
    <span data-ttu-id="66860-134">若要只包含特定的 SharePoint 網站或 OneDrive 帳戶, 請將**狀態**切換為 [開啟], 然後按一下 [**包含**] 下的連結, 選擇 [特定網站] 或 [帳戶]。</span><span class="sxs-lookup"><span data-stu-id="66860-134">To include only specific SharePoint sites or OneDrive accounts, switch the **Status** to on, and then click the links under **Include** to choose specific sites or accounts.</span></span> 
    
7. <span data-ttu-id="66860-135">選擇 [**使用高級設定** \> **] [下一步]**。</span><span class="sxs-lookup"><span data-stu-id="66860-135">Choose **Use advanced settings** \> **Next**.</span></span>
    
8. <span data-ttu-id="66860-136">選擇 [ **+ 新增規則**]。</span><span class="sxs-lookup"><span data-stu-id="66860-136">Choose **+ New rule**.</span></span>
    
9. <span data-ttu-id="66860-137">在規則編輯器的 [**使用者通知**] 下, 切換 [開啟] 狀態。</span><span class="sxs-lookup"><span data-stu-id="66860-137">In the rule editor, under **User notifications**, switch the status on.</span></span>
    
    ![規則編輯器的使用者通知區段](media/47705927-c60b-4054-a072-ab914f33d15d.png)

> [!NOTE]
> <span data-ttu-id="66860-139">DLP 原則適用于符合原則的所有檔, 不論這些檔是新的或現有的。</span><span class="sxs-lookup"><span data-stu-id="66860-139">DLP policies apply to all documents that match the policy, whether those documents are new or existing.</span></span> <span data-ttu-id="66860-140">不過, 只有當新的內容符合現有的 DLP 原則時, 才會產生電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="66860-140">However, an email notification is only generated when new content matches an existing DLP policy.</span></span> <span data-ttu-id="66860-141">現有的內容受到保護, 但不會透過電子郵件產生使用者通知。</span><span class="sxs-lookup"><span data-stu-id="66860-141">Existing content is protected, but will not generate a user notification via email.</span></span>
  
## <a name="options-for-configuring-email-notifications"></a><span data-ttu-id="66860-142">設定電子郵件通知的選項</span><span class="sxs-lookup"><span data-stu-id="66860-142">Options for configuring email notifications</span></span>

<span data-ttu-id="66860-143">對於 DLP 原則中的每個規則, 您可以:</span><span class="sxs-lookup"><span data-stu-id="66860-143">For each rule in a DLP policy, you can:</span></span>
  
- <span data-ttu-id="66860-144">將通知傳送給您選擇的人員。</span><span class="sxs-lookup"><span data-stu-id="66860-144">Send the notification to the people you choose.</span></span> <span data-ttu-id="66860-145">這些人員可以包含內容的擁有者、上次修改內容的人員、儲存內容的網站擁有者, 或特定使用者。</span><span class="sxs-lookup"><span data-stu-id="66860-145">These people can include the owner of the content, the person who last modified the content, the owner of the site where the content is stored, or a specific user.</span></span>
    
- <span data-ttu-id="66860-146">使用 HTML 或標記自訂通知中所包含的文字。</span><span class="sxs-lookup"><span data-stu-id="66860-146">Customize the text that's included in the notification by using HTML or tokens.</span></span> <span data-ttu-id="66860-147">如需詳細資訊, 請參閱下文的章節。</span><span class="sxs-lookup"><span data-stu-id="66860-147">See the section below for more information.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="66860-148">電子郵件通知只能傳送給個別收件者, 而不是群組或通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="66860-148">Email notifications can be sent only to individual recipients—not groups or distribution lists.</span></span> <span data-ttu-id="66860-149">只有新的內容會觸發電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="66860-149">Only new content will trigger an email notification.</span></span> <span data-ttu-id="66860-150">編輯現有的內容將會觸發原則提示, 但不會觸發電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="66860-150">Editing existing content will trigger policy tips, but not an email notification.</span></span> 
  
![電子郵件通知選項](media/4e7b9500-2a78-44e6-9067-09f4bfd50301.png)
  
### <a name="default-email-notification"></a><span data-ttu-id="66860-152">預設電子郵件通知</span><span class="sxs-lookup"><span data-stu-id="66860-152">Default email notification</span></span>

<span data-ttu-id="66860-153">通知具有以所採取動作為開頭的主旨行, 例如「通知」、「郵件被封鎖」, 或針對檔的「拒絕存取」。</span><span class="sxs-lookup"><span data-stu-id="66860-153">Notifications have a Subject line that begins with the action taken, such as "Notification", "Message Blocked" for email, or "Access Blocked" for documents.</span></span> <span data-ttu-id="66860-154">如果通知是關於檔, 通知訊息內文會包含連結, 會帶您前往儲存檔的網站, 並開啟檔的原則提示, 您可以在其中解決任何問題 (請參閱下一節關於原則提示)。</span><span class="sxs-lookup"><span data-stu-id="66860-154">If the notification is about a document, the notification message body includes a link that takes you to the site where the document's stored and opens the policy tip for the document, where you can resolve any issues (see the section below about policy tips).</span></span> <span data-ttu-id="66860-155">如果通知是關於郵件, 通知會將符合 DLP 原則的郵件加入附件。</span><span class="sxs-lookup"><span data-stu-id="66860-155">If the notification is about a message, the notification includes as an attachment the message that matches a DLP policy.</span></span>
  
![通知訊息](media/35813d40-5fd8-425f-9624-55655e74fa6b.png)
  
<span data-ttu-id="66860-157">根據預設, 通知會針對網站上的專案顯示類似下列的文字。</span><span class="sxs-lookup"><span data-stu-id="66860-157">By default, notifications display text similar to the following for an item on a site.</span></span> <span data-ttu-id="66860-158">每個規則都會分別設定通知文字, 因此顯示的文字會因相符的規則而有所不同。</span><span class="sxs-lookup"><span data-stu-id="66860-158">The notification text is configured separately for each rule, so the text that's displayed differs depending on which rule is matched.</span></span>

|<span data-ttu-id="66860-159">**如果 DLP 原則規則執行此動作 .。。**</span><span class="sxs-lookup"><span data-stu-id="66860-159">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="66860-160">**如果是 SharePoint 或商務用 OneDrive 檔的預設通知, 就會指出 .。。**</span><span class="sxs-lookup"><span data-stu-id="66860-160">**Then the default notification for SharePoint or OneDrive for Business documents says this…**</span></span>|<span data-ttu-id="66860-161">**然後, Outlook 郵件的預設通知會指出 .。。**</span><span class="sxs-lookup"><span data-stu-id="66860-161">**Then the default notification for Outlook messages says this…**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="66860-162">傳送通知, 但不允許覆寫</span><span class="sxs-lookup"><span data-stu-id="66860-162">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="66860-163">此專案與您組織中的原則相衝突。</span><span class="sxs-lookup"><span data-stu-id="66860-163">This item conflicts with a policy in your organization.</span></span>  <br/> |<span data-ttu-id="66860-164">您的電子郵件與您組織中的原則衝突。</span><span class="sxs-lookup"><span data-stu-id="66860-164">Your email message conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="66860-165">封鎖存取、傳送通知, 並允許覆寫</span><span class="sxs-lookup"><span data-stu-id="66860-165">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="66860-166">此專案與您組織中的原則相衝突。</span><span class="sxs-lookup"><span data-stu-id="66860-166">This item conflicts with a policy in your organization.</span></span> <span data-ttu-id="66860-167">如果您未解決此衝突, 則可能會封鎖對此檔案的存取。</span><span class="sxs-lookup"><span data-stu-id="66860-167">If you don't resolve this conflict, access to this file might be blocked.</span></span>  <br/> |<span data-ttu-id="66860-168">您的電子郵件與您組織中的原則衝突。</span><span class="sxs-lookup"><span data-stu-id="66860-168">Your email message conflicts with a policy in your organization.</span></span> <span data-ttu-id="66860-169">郵件不會傳遞給所有收件者。</span><span class="sxs-lookup"><span data-stu-id="66860-169">The message wasn't delivered to all recipients.</span></span>  <br/> |
|<span data-ttu-id="66860-170">封鎖存取並傳送通知</span><span class="sxs-lookup"><span data-stu-id="66860-170">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="66860-171">此專案與您組織中的原則相衝突。</span><span class="sxs-lookup"><span data-stu-id="66860-171">This item conflicts with a policy in your organization.</span></span> <span data-ttu-id="66860-172">除了其擁有者、最後一個修改者和主要網站集合管理員之外, 所有人都可以存取此專案。</span><span class="sxs-lookup"><span data-stu-id="66860-172">Access to this item is blocked for everyone except its owner, last modifier, and the primary site collection administrator.</span></span>  <br/> |<span data-ttu-id="66860-173">您的電子郵件與您組織中的原則衝突。</span><span class="sxs-lookup"><span data-stu-id="66860-173">Your email message conflicts with a policy in your organization.</span></span> <span data-ttu-id="66860-174">郵件不會傳遞給所有收件者。</span><span class="sxs-lookup"><span data-stu-id="66860-174">The message wasn't delivered to all recipients.</span></span>  <br/> |
   
### <a name="custom-email-notification"></a><span data-ttu-id="66860-175">自訂電子郵件通知</span><span class="sxs-lookup"><span data-stu-id="66860-175">Custom email notification</span></span>

<span data-ttu-id="66860-176">您可以建立自訂電子郵件通知, 而不是傳送預設的電子郵件通知給您的使用者或系統管理員。</span><span class="sxs-lookup"><span data-stu-id="66860-176">You can create a custom email notification instead of sending the default email notification to your end users or admins.</span></span> <span data-ttu-id="66860-177">自訂電子郵件通知支援 HTML, 且具有5000個字元的限制。</span><span class="sxs-lookup"><span data-stu-id="66860-177">The custom email notification supports HTML and has a 5,000-character limit.</span></span> <span data-ttu-id="66860-178">您可以使用 HTML 在通知中包含圖像、格式及其他品牌。</span><span class="sxs-lookup"><span data-stu-id="66860-178">You can use HTML to include images, formatting, and other branding in the notification.</span></span>
  
<span data-ttu-id="66860-179">您也可以使用下列權杖來協助自訂電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="66860-179">You can also use the following tokens to help customize the email notification.</span></span> <span data-ttu-id="66860-180">這些 token 是由所傳送通知中的特定資訊所取代的變數。</span><span class="sxs-lookup"><span data-stu-id="66860-180">These tokens are variables that are replaced by specific information in the notification that's sent.</span></span>

|<span data-ttu-id="66860-181">**標記**</span><span class="sxs-lookup"><span data-stu-id="66860-181">**Token**</span></span>|<span data-ttu-id="66860-182">**描述**</span><span class="sxs-lookup"><span data-stu-id="66860-182">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="66860-183">%% AppliedActions%%</span><span class="sxs-lookup"><span data-stu-id="66860-183">%%AppliedActions%%</span></span>  <br/> |<span data-ttu-id="66860-184">套用至內容的動作。</span><span class="sxs-lookup"><span data-stu-id="66860-184">The actions applied to the content.</span></span>  <br/> |
|<span data-ttu-id="66860-185">%% ContentURL%%</span><span class="sxs-lookup"><span data-stu-id="66860-185">%%ContentURL%%</span></span>  <br/> |<span data-ttu-id="66860-186">SharePoint Online 網站或商務用 OneDrive 網站上檔的 URL。</span><span class="sxs-lookup"><span data-stu-id="66860-186">The URL of the document on the SharePoint Online site or OneDrive for Business site.</span></span>  <br/> |
|<span data-ttu-id="66860-187">%%MatchedConditions%%</span><span class="sxs-lookup"><span data-stu-id="66860-187">%%MatchedConditions%%</span></span>  <br/> |<span data-ttu-id="66860-188">內容所符合的條件。</span><span class="sxs-lookup"><span data-stu-id="66860-188">The conditions that were matched by the content.</span></span> <span data-ttu-id="66860-189">使用此權杖通知人員可能發生的內容問題。</span><span class="sxs-lookup"><span data-stu-id="66860-189">Use this token to inform people of possible issues with the content.</span></span>  <br/> |
   
![顯示權杖顯示位置的通知訊息](media/cd3f36b3-40db-4f30-99e4-190750bd1955.png)
  
## <a name="options-for-configuring-policy-tips"></a><span data-ttu-id="66860-191">設定原則提示的選項</span><span class="sxs-lookup"><span data-stu-id="66860-191">Options for configuring policy tips</span></span>

<span data-ttu-id="66860-192">對於 DLP 原則中的每個規則, 您可以設定原則提示:</span><span class="sxs-lookup"><span data-stu-id="66860-192">For each rule in a DLP policy, you can configure policy tips to:</span></span>
  
- <span data-ttu-id="66860-193">只要通知人員內容與 DLP 原則衝突, 就能採取動作來解決衝突。</span><span class="sxs-lookup"><span data-stu-id="66860-193">Simply notify the person that the content conflicts with a DLP policy, so that they can take action to resolve the conflict.</span></span> <span data-ttu-id="66860-194">您可以使用預設文字 (請參閱下表) 或輸入您組織的特定原則的自訂文字。</span><span class="sxs-lookup"><span data-stu-id="66860-194">You can use the default text (see the tables below) or enter custom text about your organization's specific policies.</span></span>
    
- <span data-ttu-id="66860-195">允許使用者覆寫 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="66860-195">Allow the person to override the DLP policy.</span></span> <span data-ttu-id="66860-196">您可以選擇:</span><span class="sxs-lookup"><span data-stu-id="66860-196">Optionally, you can:</span></span>
    
  - <span data-ttu-id="66860-197">需要人員輸入業務理由以覆寫原則。</span><span class="sxs-lookup"><span data-stu-id="66860-197">Require the person to enter a business justification for overriding the policy.</span></span> <span data-ttu-id="66860-198">將會記錄此資訊, 您可以在安全性&amp;與合規性中心的 [**報告**] 區段中, 于 [DLP 報告] 中加以查看。</span><span class="sxs-lookup"><span data-stu-id="66860-198">This information is logged and you can view it in the DLP reports in the **Reports** section of the Security &amp; Compliance Center.</span></span> 
    
  - <span data-ttu-id="66860-199">允許人員報告 false 正值, 並覆寫 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="66860-199">Allow the person to report a false positive and override the DLP policy.</span></span> <span data-ttu-id="66860-200">此資訊也會記錄報告, 因此您可以使用假正值來微調您的規則。</span><span class="sxs-lookup"><span data-stu-id="66860-200">This information is also logged for reporting, so that you can use false positives to fine tune your rules.</span></span>
    
![原則提示選項](media/0d2f2c68-028a-4900-afe6-1d9fce5303ef.png)
  
<span data-ttu-id="66860-202">例如, 您可能會將 DLP 原則套用至商務用 OneDrive 網站, 以偵測個人身分識別資訊 (PII), 且此原則具有三個規則:</span><span class="sxs-lookup"><span data-stu-id="66860-202">For example, you may have a DLP policy applied to OneDrive for Business sites that detects personally identifiable information (PII), and this policy has three rules:</span></span>
  
1. <span data-ttu-id="66860-203">第一個規則: 如果在檔中偵測到的這個敏感資訊的實例少於五個, 且該檔與組織內的人員共用, 則 [**傳送通知**] 動作會顯示原則提示。</span><span class="sxs-lookup"><span data-stu-id="66860-203">First rule: If fewer than five instances of this sensitive information are detected in a document, and the document is shared with people inside the organization, the **Send a notification** action displays a policy tip.</span></span> <span data-ttu-id="66860-204">針對原則提示, 不需要覆寫選項, 因為此規則只是通知人員, 而不會封鎖存取。</span><span class="sxs-lookup"><span data-stu-id="66860-204">For policy tips, no override options are necessary because this rule is simply notifying people and not blocking access.</span></span> 
    
2. <span data-ttu-id="66860-205">第二個規則: 如果在檔中偵測到此機密資訊有五個以上的實例, 且該檔與組織內的人員共用, 則 [**封鎖存取內容**] 動作會限制檔案的許可權, 而 **[傳送通知**] 動作可讓人員提供業務理由, 以覆寫此規則中的動作。</span><span class="sxs-lookup"><span data-stu-id="66860-205">Second rule: If greater than five instances of this sensitive information are detected in a document, and the document is shared with people inside the organization, the **Block access to content** action restricts the permissions for the file, and the **Send a notification** action allows people to override the actions in this rule by providing a business justification.</span></span> <span data-ttu-id="66860-206">您組織的業務有時會要求內部人員共用 PII 資料, 而您不想讓 DLP 原則封鎖此工作。</span><span class="sxs-lookup"><span data-stu-id="66860-206">Your organization's business sometimes requires internal people to share PII data, and you don't want your DLP policy to block this work.</span></span> 
    
3. <span data-ttu-id="66860-207">第三個規則: 如果在檔中偵測到此敏感資訊有五個以上的實例, 而且該檔與組織外部的人員共用, 則 [**封鎖存取內容**] 動作會限制檔案的許可權, 而 **[傳送通知**] 動作不允許使用者覆寫此規則中的動作, 因為資訊是從外部共用。</span><span class="sxs-lookup"><span data-stu-id="66860-207">Third rule: If greater than five instances of this sensitive information are detected in a document, and the document is shared with people outside the organization, the **Block access to content** action restricts the permissions for the file, and the **Send a notification** action does not allow people to override the actions in this rule because the information is shared externally.</span></span> <span data-ttu-id="66860-208">在任何情況下, 您的組織中的人員都不應該允許共用組織外部的 PII 資料。</span><span class="sxs-lookup"><span data-stu-id="66860-208">Under no circumstances should people in your organization be allowed to share PII data outside the organization.</span></span> 
    
<span data-ttu-id="66860-209">以下是瞭解如何使用原則提示來覆寫規則的一些要點:</span><span class="sxs-lookup"><span data-stu-id="66860-209">Here are some fine points to understand about using a policy tip to override a rule:</span></span>
  
- <span data-ttu-id="66860-210">要覆寫的選項是每個規則, 而且會覆寫規則中的所有動作 (傳送無法覆寫的通知除外)。</span><span class="sxs-lookup"><span data-stu-id="66860-210">The option to override is per rule, and it overrides all of the actions in the rule (except sending a notification, which can't be overridden).</span></span>
    
- <span data-ttu-id="66860-211">內容可以比對 DLP 原則中的數個規則, 但只會顯示最嚴格的原則提示和最高優先順序的規則。</span><span class="sxs-lookup"><span data-stu-id="66860-211">It's possible for content to match several rules in a DLP policy, but only the policy tip from the most restrictive, highest-priority rule will be shown.</span></span> <span data-ttu-id="66860-212">例如, 從規則來封鎖內容存取的原則提示, 會從只傳送通知的規則的原則提示中顯示。</span><span class="sxs-lookup"><span data-stu-id="66860-212">For example, a policy tip from a rule that blocks access to content will be shown over a policy tip from a rule that simply sends a notification.</span></span> <span data-ttu-id="66860-213">這可防止人們看到層疊的原則提示。</span><span class="sxs-lookup"><span data-stu-id="66860-213">This prevents people from seeing a cascade of policy tips.</span></span>
    
- <span data-ttu-id="66860-214">如果最嚴格規則中的原則提示允許使用者覆寫規則, 則覆寫此規則也會覆寫內容符合的任何其他規則。</span><span class="sxs-lookup"><span data-stu-id="66860-214">If the policy tips in the most restrictive rule allow people to override the rule, then overriding this rule also overrides any other rules that the content matched.</span></span>
    
## <a name="policy-tips-on-onedrive-for-business-sites-and-sharepoint-online-sites"></a><span data-ttu-id="66860-215">商務用 OneDrive 網站和 SharePoint Online 網站上的原則提示</span><span class="sxs-lookup"><span data-stu-id="66860-215">Policy tips on OneDrive for Business sites and SharePoint Online sites</span></span>

<span data-ttu-id="66860-216">當商務用 OneDrive 網站或 SharePoint Online 網站上的檔符合 DLP 原則中的規則, 且該規則使用原則提示時, 原則提示會在檔上顯示特殊的圖示:</span><span class="sxs-lookup"><span data-stu-id="66860-216">When a document on a OneDrive for Business site or SharePoint Online site matches a rule in a DLP policy, and that rule uses policy tips, the policy tips display special icons on the document:</span></span>
  
1. <span data-ttu-id="66860-217">如果規則傳送有關檔案的通知, 就會出現警告圖示。</span><span class="sxs-lookup"><span data-stu-id="66860-217">If the rule sends a notification about the file, the warning icon appears.</span></span>
    
2. <span data-ttu-id="66860-218">如果規則會封鎖對檔的存取, 會顯示封鎖的圖示。</span><span class="sxs-lookup"><span data-stu-id="66860-218">If the rule blocks access to the document, the blocked icon appears.</span></span>
    
![OneDrive 帳戶中檔的原則提示圖示](media/d3e9f772-03f9-4d28-82f8-3064784332a2.png)
  
<span data-ttu-id="66860-220">若要在檔上採取動作, 您可以選取專案\>的右上角的 [](media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) **資訊** ![資訊窗格] 圖示, 以開啟 [詳細資料] 窗格的\> [**原則提示**]。</span><span class="sxs-lookup"><span data-stu-id="66860-220">To take action on a document, you can select an item \> choose **Information** ![Information pane icon](media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) in the upper-right corner of the page to open the details pane \> **View policy tip**.</span></span>
  
<span data-ttu-id="66860-221">原則提示會列出內容的問題, 如果使用這些選項設定原則提示, 您可以選擇 [**解決**], 然後覆**寫**原則提示或**報告**false 正值。</span><span class="sxs-lookup"><span data-stu-id="66860-221">The policy tip lists the issues with the content, and if the policy tips are configured with these options, you can choose **Resolve**, and then **Override** the policy tip or **Report** a false positive.</span></span> 
  
![顯示原則提示的資訊窗格](media/0a191e70-80f0-4702-90f4-7a5b7aabcaab.png)
  
![具有覆寫選項的原則提示](media/e250bff9-41d5-4ce4-82ea-1dc2d043fab1.png)
  
<span data-ttu-id="66860-224">DLP 原則會同步處理至網站, 而且 contented 會定期或以非同步方式評估, 因此您在建立 DLP 原則的時間與開始查看原則提示的時間之間可能會有短暫的延遲。</span><span class="sxs-lookup"><span data-stu-id="66860-224">DLP policies are synced to sites and contented is evaluated against them periodically and asynchronously, so there may be a short delay between the time you create the DLP policy and the time you begin to see policy tips.</span></span> <span data-ttu-id="66860-225">當您解決或覆寫網站上檔上的圖示時, 可能會發生類似的延遲。</span><span class="sxs-lookup"><span data-stu-id="66860-225">There may be a similar delay from when you resolve or override a policy tip to when the icon on the document on the site goes away.</span></span>
  
### <a name="default-text-for-policy-tips-on-sites"></a><span data-ttu-id="66860-226">網站上的原則提示的預設文字</span><span class="sxs-lookup"><span data-stu-id="66860-226">Default text for policy tips on sites</span></span>

<span data-ttu-id="66860-227">根據預設, 原則提示會針對網站上的專案顯示類似下列的文字。</span><span class="sxs-lookup"><span data-stu-id="66860-227">By default, policy tips display text similar to the following for an item on a site.</span></span> <span data-ttu-id="66860-228">每個規則都會分別設定通知文字, 因此顯示的文字會因相符的規則而有所不同。</span><span class="sxs-lookup"><span data-stu-id="66860-228">The notification text is configured separately for each rule, so the text that's displayed differs depending on which rule is matched.</span></span>

|<span data-ttu-id="66860-229">**如果 DLP 原則規則執行此動作 .。。**</span><span class="sxs-lookup"><span data-stu-id="66860-229">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="66860-230">**預設原則提示會指出 .。。**</span><span class="sxs-lookup"><span data-stu-id="66860-230">**Then the default policy tip says this…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="66860-231">傳送通知, 但不允許覆寫</span><span class="sxs-lookup"><span data-stu-id="66860-231">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="66860-232">此專案與您組織中的原則相衝突。</span><span class="sxs-lookup"><span data-stu-id="66860-232">This item conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="66860-233">封鎖存取、傳送通知, 並允許覆寫</span><span class="sxs-lookup"><span data-stu-id="66860-233">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="66860-234">此專案與您組織中的原則相衝突。</span><span class="sxs-lookup"><span data-stu-id="66860-234">This item conflicts with a policy in your organization.</span></span> <span data-ttu-id="66860-235">如果您未解決此衝突, 則可能會封鎖對此檔案的存取。</span><span class="sxs-lookup"><span data-stu-id="66860-235">If you don't resolve this conflict, access to this file might be blocked.</span></span>  <br/> |
|<span data-ttu-id="66860-236">封鎖存取並傳送通知</span><span class="sxs-lookup"><span data-stu-id="66860-236">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="66860-237">此專案與您組織中的原則相衝突。</span><span class="sxs-lookup"><span data-stu-id="66860-237">This item conflicts with a policy in your organization.</span></span> <span data-ttu-id="66860-238">除了其擁有者、最後一個修改者和主要網站集合管理員之外, 所有人都可以存取此專案。</span><span class="sxs-lookup"><span data-stu-id="66860-238">Access to this item is blocked for everyone except its owner, last modifier, and the primary site collection administrator.</span></span>  <br/> |
   
### <a name="custom-text-for-policy-tips-on-sites"></a><span data-ttu-id="66860-239">網站上的原則提示的自訂文字</span><span class="sxs-lookup"><span data-stu-id="66860-239">Custom text for policy tips on sites</span></span>

<span data-ttu-id="66860-240">您可以從電子郵件通知自訂原則提示的文字。</span><span class="sxs-lookup"><span data-stu-id="66860-240">You can customize the text for policy tips separately from the email notification.</span></span> <span data-ttu-id="66860-241">不同于電子郵件通知的自訂文字 (請參閱上述章節), 原則提示的自訂文字不接受 HTML 或標記。</span><span class="sxs-lookup"><span data-stu-id="66860-241">Unlike custom text for email notifications (see above section), custom text for policy tips does not accept HTML or tokens.</span></span> <span data-ttu-id="66860-242">相反地, 原則提示的自訂文字是純文字, 僅含256字元的限制。</span><span class="sxs-lookup"><span data-stu-id="66860-242">Instead, custom text for policy tips is plain text only with a 256-character limit.</span></span>
  
## <a name="policy-tips-in-outlook-on-the-web-and-outlook-2013-and-later"></a><span data-ttu-id="66860-243">Outlook 網頁版和 Outlook 2013 及更新版本中的原則提示</span><span class="sxs-lookup"><span data-stu-id="66860-243">Policy tips in Outlook on the web and Outlook 2013 and later</span></span>

<span data-ttu-id="66860-244">當您在網頁版 Outlook 和 Outlook 2013 和更新版本中撰寫新的電子郵件時, 如果您新增的內容符合 DLP 原則中的規則, 而該規則使用原則提示, 就會看到原則提示。</span><span class="sxs-lookup"><span data-stu-id="66860-244">When you compose a new email in Outlook on the web and Outlook 2013 and later, you'll see a policy tip if you add content that matches a rule in a DLP policy, and that rule uses policy tips.</span></span> <span data-ttu-id="66860-245">原則提示會出現在郵件上方的收件者上方, 同時撰寫郵件時。</span><span class="sxs-lookup"><span data-stu-id="66860-245">The policy tip appears at the top of the message, above the recipients, while the message is being composed.</span></span>
  
![撰寫郵件頂端的原則提示](media/9b3b6b74-17c5-4562-82d5-d17ecaaa8d95.png)
  
<span data-ttu-id="66860-247">原則提示可供敏感資訊顯示在郵件內文、主旨行, 甚至是郵件附件, 如下所示。</span><span class="sxs-lookup"><span data-stu-id="66860-247">Policy tips work whether the sensitive information appears in the message body, subject line, or even a message attachment as shown here.</span></span>
  
![顯示附件與 DLP 原則衝突的原則提示](media/59ae6655-215f-47d9-ad1d-39c0d1e61740.png)
  
<span data-ttu-id="66860-249">如果原則提示設定為允許覆寫, 您可以選擇 [**顯示詳細資料** \> \*\*\*\* \> \> \*\* \*\*]。</span><span class="sxs-lookup"><span data-stu-id="66860-249">If the policy tips are configured to allow override, you can choose **Show Details** \> **Override** \> enter a business justification or report a false positive \> **Override**.</span></span>
  
![郵件展開為顯示覆寫選項的原則提示](media/28bfb997-48a6-41f0-8682-d5e62488458a.png)
  
![[原則提示] 對話方塊, 您可以在其中覆寫原則提示](media/f97e836c-04bd-44b4-aec6-ed9526ea31f8.png)
  
<span data-ttu-id="66860-252">請注意, 當您將機密資訊新增至電子郵件時, 在新增敏感資訊和顯示原則提示時, 可能會有延遲。</span><span class="sxs-lookup"><span data-stu-id="66860-252">Note that when you add sensitive information to an email, there may be latency between when the sensitive information is added and when the policy tip appears.</span></span>

### <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions"></a><span data-ttu-id="66860-253">Outlook 2013 和更新版本支援顯示僅限某些條件的原則提示</span><span class="sxs-lookup"><span data-stu-id="66860-253">Outlook 2013 and later supports showing policy tips for only some conditions</span></span>

<span data-ttu-id="66860-254">目前, Outlook 2013 和更新版本支援只顯示這些條件的原則提示:</span><span class="sxs-lookup"><span data-stu-id="66860-254">Currently, Outlook 2013 and later supports showing policy tips only for these conditions:</span></span>

- <span data-ttu-id="66860-255">內容包含</span><span class="sxs-lookup"><span data-stu-id="66860-255">Content contains</span></span>
- <span data-ttu-id="66860-256">共用內容</span><span class="sxs-lookup"><span data-stu-id="66860-256">Content is shared</span></span>

<span data-ttu-id="66860-257">我們目前正在處理支援, 以顯示其他條件的原則提示。</span><span class="sxs-lookup"><span data-stu-id="66860-257">We're currently working on support for showing policy tips for additional conditions.</span></span> <span data-ttu-id="66860-258">這些包括：</span><span class="sxs-lookup"><span data-stu-id="66860-258">These include:</span></span>

- <span data-ttu-id="66860-259">無法掃描任何電子郵件附件的內容</span><span class="sxs-lookup"><span data-stu-id="66860-259">Any email attachment's content could not be scanned</span></span>
- <span data-ttu-id="66860-260">任何電子郵件附件的內容未完成掃描</span><span class="sxs-lookup"><span data-stu-id="66860-260">Any email attachment's content didn't complete scanning</span></span>
- <span data-ttu-id="66860-261">附件副檔名為</span><span class="sxs-lookup"><span data-stu-id="66860-261">Attachment file extension is</span></span>
- <span data-ttu-id="66860-262">附件受密碼保護</span><span class="sxs-lookup"><span data-stu-id="66860-262">Attachment is password protected</span></span>
- <span data-ttu-id="66860-263">Document 屬性為</span><span class="sxs-lookup"><span data-stu-id="66860-263">Document property is</span></span>
- <span data-ttu-id="66860-264">收件者網域是</span><span class="sxs-lookup"><span data-stu-id="66860-264">Recipient domain is</span></span>
- <span data-ttu-id="66860-265">寄件者 IP 位址為</span><span class="sxs-lookup"><span data-stu-id="66860-265">Sender IP address is</span></span>

<span data-ttu-id="66860-266">請注意, 所有這些條件都能在 Outlook 中運作, 在其中會比對內容並對內容強制執行保護動作。</span><span class="sxs-lookup"><span data-stu-id="66860-266">Note that all of these conditions work in Outlook, where they will match content and enforce protective actions on content.</span></span> <span data-ttu-id="66860-267">但尚未支援使用者顯示原則提示。</span><span class="sxs-lookup"><span data-stu-id="66860-267">But showing policy tips to users is not yet supported.</span></span>
  
### <a name="policy-tips-in-the-exchange-admin-center-vs-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="66860-268">Exchange 系統管理中心與 Office 365 安全性&amp;與合規性中心中的原則提示</span><span class="sxs-lookup"><span data-stu-id="66860-268">Policy tips in the Exchange admin center vs. the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="66860-269">原則提示可以使用在 Exchange 系統管理中心建立的 DLP 原則和郵件流程規則, 或使用 Office 365 安全性&amp;與規範中心建立的 dlp 原則, 但不能同時使用這兩者。</span><span class="sxs-lookup"><span data-stu-id="66860-269">Policy tips can work either with DLP policies and mail flow rules created in the Exchange admin center, or with DLP policies created in the Office 365 Security &amp; Compliance Center, but not both.</span></span> <span data-ttu-id="66860-270">這是因為這些原則會儲存在不同的位置, 但原則提示只能從單一位置進行繪製。</span><span class="sxs-lookup"><span data-stu-id="66860-270">This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="66860-271">如果您已在 Exchange 系統管理中心中設定原則提示, 您在 Office 365 安全性&amp;與合規性中心中設定的任何原則提示, 將不會對 outlook 網頁版或 outlook 2013 和更新版本中的使用者顯示, 直到您關閉 Exchange 中的秘訣。系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="66860-271">If you've configured policy tips in the Exchange admin center, any policy tips that you configure in the Office 365 Security &amp; Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange admin center.</span></span> <span data-ttu-id="66860-272">這可確保您目前的 Exchange 郵件流程規則 (也稱為傳輸規則) 可繼續運作, 直到您選擇切換到 Office 365 安全性&amp;與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="66860-272">This ensures that your current Exchange mail flow rules (also known as transport rules) will continue to work until you choose to switch over to the Office 365 Security &amp; Compliance Center.</span></span>
  
<span data-ttu-id="66860-273">請注意, 雖然原則提示只能從單一位置進行繪製, 但即使您在 Office 365 安全性&amp;合規性中心和 Exchange 系統管理中心使用 DLP 原則, 仍會傳送電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="66860-273">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Office 365 Security &amp; Compliance Center and the Exchange admin center.</span></span>
  
### <a name="default-text-for-policy-tips-in-email"></a><span data-ttu-id="66860-274">電子郵件中原則提示的預設文字</span><span class="sxs-lookup"><span data-stu-id="66860-274">Default text for policy tips in email</span></span>

<span data-ttu-id="66860-275">原則提示預設會顯示類似下列電子郵件的文字。</span><span class="sxs-lookup"><span data-stu-id="66860-275">By default, policy tips display text similar to the following for email.</span></span>

|<span data-ttu-id="66860-276">**如果 DLP 原則規則執行此動作 .。。**</span><span class="sxs-lookup"><span data-stu-id="66860-276">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="66860-277">**預設原則提示會指出 .。。**</span><span class="sxs-lookup"><span data-stu-id="66860-277">**Then the default policy tip says this…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="66860-278">傳送通知, 但不允許覆寫</span><span class="sxs-lookup"><span data-stu-id="66860-278">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="66860-279">您的電子郵件與您組織中的原則相衝突。</span><span class="sxs-lookup"><span data-stu-id="66860-279">Your email conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="66860-280">封鎖存取、傳送通知, 並允許覆寫</span><span class="sxs-lookup"><span data-stu-id="66860-280">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="66860-281">您的電子郵件與您組織中的原則相衝突。</span><span class="sxs-lookup"><span data-stu-id="66860-281">Your email conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="66860-282">封鎖存取並傳送通知</span><span class="sxs-lookup"><span data-stu-id="66860-282">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="66860-283">您的電子郵件與您組織中的原則相衝突。</span><span class="sxs-lookup"><span data-stu-id="66860-283">Your email conflicts with a policy in your organization.</span></span>  <br/> |
   
## <a name="policy-tips-in-excel-powerpoint-and-word"></a><span data-ttu-id="66860-284">Excel、PowerPoint 和 Word 中的原則提示</span><span class="sxs-lookup"><span data-stu-id="66860-284">Policy tips in Excel, PowerPoint, and Word</span></span>

<span data-ttu-id="66860-285">當人員在 Excel、PowerPoint 及 Word 的桌上出版本中使用機密內容時, 原則提示可以即時通知內容與 DLP 原則相衝突。</span><span class="sxs-lookup"><span data-stu-id="66860-285">When people work with sensitive content in the desktop versions of Excel, PowerPoint, and Word, policy tips can notify them in real time that the content conflicts with a DLP policy.</span></span> <span data-ttu-id="66860-286">這需要:</span><span class="sxs-lookup"><span data-stu-id="66860-286">This requires that:</span></span>
  
- <span data-ttu-id="66860-287">Office 檔儲存在商務用 OneDrive 網站或 SharePoint Online 網站上。</span><span class="sxs-lookup"><span data-stu-id="66860-287">The Office document is stored on a OneDrive for Business site or SharePoint Online site.</span></span>
    
- <span data-ttu-id="66860-288">此網站包含在設定為使用原則提示的 DLP 原則中。</span><span class="sxs-lookup"><span data-stu-id="66860-288">The site is included in a DLP policy that's configured to use policy tips.</span></span>
    
<span data-ttu-id="66860-289">Office 桌面程式會自動從 Office 365 自動同步處理 DLP 原則, 然後掃描您的檔, 以確保它們不會與您的 DLP 原則衝突, 並即時顯示原則提示。</span><span class="sxs-lookup"><span data-stu-id="66860-289">Office desktop programs automatically sync DLP policies directly from Office 365, and then scan your documents to ensure that they don't conflict with your DLP policies and display policy tips in real time.</span></span>
  
<span data-ttu-id="66860-290">根據您在 DLP 原則中設定原則提示的方式, 使用者可以選擇直接忽略原則提示、使用或不使用業務理由覆寫原則, 或報告為 false 正值。</span><span class="sxs-lookup"><span data-stu-id="66860-290">Depending on how you configure the policy tips in the DLP policy, people can choose to simply ignore the policy tip, override the policy with or without a business justification, or report a false positive.</span></span>
  
<span data-ttu-id="66860-291">原則提示會出現在訊息列上。</span><span class="sxs-lookup"><span data-stu-id="66860-291">Policy tips appear on the Message Bar.</span></span>
  
![訊息列會顯示 Excel 2016 中的原則提示](media/7002ff54-1656-4a6c-993f-37427d6508c8.png)
  
<span data-ttu-id="66860-293">原則提示也會出現在 Backstage 檢視中 (在 [ \*\*\*\* 檔案] 索引標籤上)。</span><span class="sxs-lookup"><span data-stu-id="66860-293">And policy tips also appear in the Backstage view (on the **File** tab).</span></span> 
  
![Backstage 會顯示 Excel 2016 中的原則提示](media/44c561f6-8f3f-4878-b1b0-b7543f8a4120.png)
  
<span data-ttu-id="66860-295">如果已使用這些選項設定 DLP 原則中的原則提示, 您可以選擇 [**解決**], 以覆**寫**原則提示或**報告**false 正值。</span><span class="sxs-lookup"><span data-stu-id="66860-295">If policy tips in the DLP policy are configured with these options, you can choose **Resolve** to **Override** a policy tip or **Report** a false positive.</span></span> 
  
![Excel 2016 的 Backstage 中的原則提示選項](media/5b3857ba-907e-456e-ae43-888b594c049c.png)
  
<span data-ttu-id="66860-297">在每個 Office 桌面程式中, 使用者可以選擇關閉原則提示。</span><span class="sxs-lookup"><span data-stu-id="66860-297">In each of these Office desktop programs, people can choose to turn off policy tips.</span></span> <span data-ttu-id="66860-298">如果關閉, 則簡單通知的原則提示將不會出現在訊息列或 Backstage 檢視上 (在 [ \*\*\*\* 檔案] 索引標籤上)。</span><span class="sxs-lookup"><span data-stu-id="66860-298">If turned off, policy tips that are simple notifications will not appear on the Message Bar or Backstage view (on the **File** tab).</span></span> <span data-ttu-id="66860-299">不過, 有關封鎖和覆寫的原則提示仍會出現, 而且他們仍然會收到電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="66860-299">However, policy tips about blocking and overriding will still appear, and they will still receive the email notification.</span></span> <span data-ttu-id="66860-300">此外, 關閉原則提示不會將檔從已套用的任何 DLP 原則中排除。</span><span class="sxs-lookup"><span data-stu-id="66860-300">In addition, turning off policy tips does not exempt the document from any DLP policies that have been applied to it.</span></span> 
  
### <a name="default-text-for-policy-tips-in-excel-2016-powerpoint-2016-and-word-2016"></a><span data-ttu-id="66860-301">Excel 2016、PowerPoint 2016 和 Word 2016 中的原則提示的預設文字</span><span class="sxs-lookup"><span data-stu-id="66860-301">Default text for policy tips in Excel 2016, PowerPoint 2016, and Word 2016</span></span>

<span data-ttu-id="66860-302">根據預設, 原則提示會在已開啟檔的訊息列和 Backstage 檢視上顯示類似下列的文字。</span><span class="sxs-lookup"><span data-stu-id="66860-302">By default, policy tips display text similar to the following on the Message Bar and Backstage view of an open document.</span></span> <span data-ttu-id="66860-303">每個規則都會分別設定通知文字, 因此顯示的文字會因相符的規則而有所不同。</span><span class="sxs-lookup"><span data-stu-id="66860-303">The notification text is configured separately for each rule, so the text that's displayed differs depending on which rule is matched.</span></span>

|<span data-ttu-id="66860-304">**如果 DLP 原則規則執行此動作 .。。**</span><span class="sxs-lookup"><span data-stu-id="66860-304">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="66860-305">**預設原則提示會指出 .。。**</span><span class="sxs-lookup"><span data-stu-id="66860-305">**Then the default policy tip says this…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="66860-306">傳送通知, 但不允許覆寫</span><span class="sxs-lookup"><span data-stu-id="66860-306">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="66860-307">此檔案與您組織中的原則相衝突。</span><span class="sxs-lookup"><span data-stu-id="66860-307">This file conflicts with a policy in your organization.</span></span> <span data-ttu-id="66860-308">如需詳細\*\*\*\* 資訊, 請移至 [檔案] 功能表。</span><span class="sxs-lookup"><span data-stu-id="66860-308">Go to the **File** menu for more information.</span></span>  <br/> |
|<span data-ttu-id="66860-309">封鎖存取、傳送通知, 並允許覆寫</span><span class="sxs-lookup"><span data-stu-id="66860-309">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="66860-310">此檔案與您組織中的原則相衝突。</span><span class="sxs-lookup"><span data-stu-id="66860-310">This file conflicts with a policy in your organization.</span></span> <span data-ttu-id="66860-311">如果您未解決此衝突, 則可能會封鎖對此檔案的存取。</span><span class="sxs-lookup"><span data-stu-id="66860-311">If you don't resolve this conflict, access to this file might be blocked.</span></span> <span data-ttu-id="66860-312">如需詳細\*\*\*\* 資訊, 請移至 [檔案] 功能表。</span><span class="sxs-lookup"><span data-stu-id="66860-312">Go to the **File** menu for more information.</span></span>  <br/> |
|<span data-ttu-id="66860-313">封鎖存取並傳送通知</span><span class="sxs-lookup"><span data-stu-id="66860-313">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="66860-314">此檔案與您組織中的原則相衝突。</span><span class="sxs-lookup"><span data-stu-id="66860-314">This file conflicts with a policy in your organization.</span></span> <span data-ttu-id="66860-315">如果您未解決此衝突, 則可能會封鎖對此檔案的存取。</span><span class="sxs-lookup"><span data-stu-id="66860-315">If you don't resolve this conflict, access to this file might be blocked.</span></span> <span data-ttu-id="66860-316">如需詳細\*\*\*\* 資訊, 請移至 [檔案] 功能表。</span><span class="sxs-lookup"><span data-stu-id="66860-316">Go to the **File** menu for more information.</span></span>  <br/> |
   
### <a name="custom-text-for-policy-tips-in-excel-powerpoint-and-word"></a><span data-ttu-id="66860-317">Excel、PowerPoint 和 Word 中的原則提示的自訂文字</span><span class="sxs-lookup"><span data-stu-id="66860-317">Custom text for policy tips in Excel, PowerPoint, and Word</span></span>

<span data-ttu-id="66860-318">您可以從電子郵件通知自訂原則提示的文字。</span><span class="sxs-lookup"><span data-stu-id="66860-318">You can customize the text for policy tips separately from the email notification.</span></span> <span data-ttu-id="66860-319">不同于電子郵件通知的自訂文字 (請參閱上述章節), 原則提示的自訂文字不接受 HTML 或標記。</span><span class="sxs-lookup"><span data-stu-id="66860-319">Unlike custom text for email notifications (see above section), custom text for policy tips does not accept HTML or tokens.</span></span> <span data-ttu-id="66860-320">相反地, 原則提示的自訂文字是純文字, 僅含256字元的限制。</span><span class="sxs-lookup"><span data-stu-id="66860-320">Instead, custom text for policy tips is plain text only with a 256-character limit.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="66860-321">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="66860-321">More information</span></span>

- [<span data-ttu-id="66860-322">資料外洩防護原則概觀</span><span class="sxs-lookup"><span data-stu-id="66860-322">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)
    
- [<span data-ttu-id="66860-323">從範本建立 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="66860-323">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
    
- [<span data-ttu-id="66860-324">建立 DLP 原則來保護具有 FCI 或其他屬性的文件</span><span class="sxs-lookup"><span data-stu-id="66860-324">Create a DLP policy to protect documents with FCI or other properties</span></span>](protect-documents-that-have-fci-or-other-properties.md)
    
- [<span data-ttu-id="66860-325">DLP 原則範本包含哪些內容</span><span class="sxs-lookup"><span data-stu-id="66860-325">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="66860-326">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="66860-326">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
    

