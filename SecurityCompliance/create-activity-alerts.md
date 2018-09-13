---
title: 建立 Office 365 安全性活動提醒&amp;規範中心
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/7/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- BCS160
- MET150
ms.assetid: 72bbad69-035b-4d33-b8f4-549a2743e97d
description: 新增及管理安全性的活動提醒&amp;當使用者執行特定 Office 365 中的規範中心讓 Office 365 將會傳送給您電子郵件通知。
ms.openlocfilehash: 409c1ff4c7fdd0d2d071bdb2eab08ec49357ed8a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22527146"
---
# <a name="create-activity-alerts-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="57b70-103">建立 Office 365 安全性活動提醒&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="57b70-103">Create activity alerts in the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="57b70-p101">您可以建立會傳送給您的電子郵件通知使用者在執行特定活動在 Office 365 時的活動提醒。活動提醒類似於搜尋 Office 365 稽核記錄中的事件，不同之處在於您要傳送電子郵件訊息時您已建立的提醒活動的事件發生的情況。</span><span class="sxs-lookup"><span data-stu-id="57b70-p101">You can create an activity alert that will send you an email notification when users perform specific activities in Office 365. Activity alerts are similar to searching for events in the Office 365 audit log, except that you'll be sent an email message when an event for an activity that you've created an alert for happens.</span></span> 
  
 <span data-ttu-id="57b70-p102">**為何，而不是搜尋稽核記錄中使用活動提醒？** 可能會有某種活動或真正想要知道的特定使用者所執行的活動。而不必搜尋這些活動的稽核記錄，請記得您可以讓使用者在執行這些活動時傳送電子郵件訊息給您的 Office 365 使用活動提醒。例如，您可以建立活動提醒通知您的使用者會刪除在 SharePoint 中的檔案或您可以建立的提醒通知您從他們的信箱使用者永久刪除的郵件。傳送給您的電子郵件通知包含執行哪些活動和執行該使用者的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="57b70-p102">**Why use activity alerts instead of searching the audit log?** There might be certain kinds of activity or activity performed by specific users that you really want to know about. Instead of having to remember to search the audit log for those activities, you can use activity alerts to have Office 365 send you an email message when users perform those activities. For example, you can create an activity alert to notify you when a user deletes files in SharePoint or you can create an alert to notify you when a user permanently deletes messages from their mailbox. The email notification sent to you includes information about which activity was performed and the user who performed it.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="57b70-111">開始之前</span><span class="sxs-lookup"><span data-stu-id="57b70-111">Before you begin</span></span>

- <span data-ttu-id="57b70-p103">您必須指派組織組態角色安全性&amp;規範中心管理活動提醒。根據預設，此角色指派給規範系統管理員和組織管理角色群組。如需新增成員至角色群組的詳細資訊，請參閱[授與使用者存取 Office 365 安全性&amp;規範中心](grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="57b70-p103">You must be assigned the Organization Configuration role in the Security &amp; Compliance Center to manage activity alerts. By default, this role is assigned to the Compliance Administrator and Organization Management role groups. For more information about adding members to role groups, see [Give users access to the Office 365 Security &amp; Compliance Center](grant-access-to-the-security-and-compliance-center.md).</span></span>
    
- <span data-ttu-id="57b70-p104">您 （或另一個系統管理員） 必須先開啟稽核記錄您的組織才能開始使用活動提醒。為達成此目的，只要按一下**開始錄製使用者和系統活動****活動提醒**] 頁面。（如果您沒有看到此連結，稽核已經已開啟您的組織。）您也可以開啟稽核安全性**稽核記錄搜尋**] 頁面上&amp;規範中心 (移至 [**搜尋&amp;調查** \> **稽核記錄搜尋**)。您只能有這樣一次您的組織。</span><span class="sxs-lookup"><span data-stu-id="57b70-p104">You (or another admin) must first turn on audit logging for your organization before you can start using activity alerts. To do this, just click **Start recording user and admin activity** on the **Activity alerts** page. (If you don't see this link, auditing has already been turned on for your organization.) You can also turn on auditing on the **Audit log search** page in the Security &amp; Compliance Center (go to **Search &amp; investigation** \> **Audit log search**). You only have to do this once for your organization.</span></span>
    
- <span data-ttu-id="57b70-p105">您可以使用 [**提醒**] 頁面上的 [安全性]&amp;規範中心以建立僅適用於貴組織的通訊錄中所列之使用者所執行的活動的提醒。您無法使用此頁面來建立外部使用者所執行的活動的提醒。</span><span class="sxs-lookup"><span data-stu-id="57b70-p105">You can use the **Alerts** page in the Security &amp; Compliance Center to create alerts only for activity performed by users who are listed in your organization's address book. You can't use this page to create alerts for activity performed by external users.</span></span> 
    
- <span data-ttu-id="57b70-121">請參閱的[詳細資訊](#more-information)] 區段的常見案例 （及監視特定的活動） 的清單中您可以建立的提醒。</span><span class="sxs-lookup"><span data-stu-id="57b70-121">See the [More information](#more-information) section for a list of common scenarios (and the specific activity to monitor) that you can create alerts for.</span></span> 
    
- <span data-ttu-id="57b70-122">您可以建立您可在 Office 365 稽核記錄檔中搜尋的相同活動的提醒。</span><span class="sxs-lookup"><span data-stu-id="57b70-122">You can create alerts for the same activities that you can search for in the Office 365 audit log.</span></span> 
    
## <a name="create-an-activity-alert"></a><span data-ttu-id="57b70-123">建立活動通知</span><span class="sxs-lookup"><span data-stu-id="57b70-123">Create an activity alert</span></span>

1. <span data-ttu-id="57b70-124">移至 [ [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="57b70-124">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="57b70-125">登入 Office 365 中，使用您工作或學校的帳戶。</span><span class="sxs-lookup"><span data-stu-id="57b70-125">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="57b70-126">在左窗格中，按一下 [**提醒**] 和 [**管理提醒**。</span><span class="sxs-lookup"><span data-stu-id="57b70-126">In the left pane, click **Alerts**, and then click **Manage alerts**.</span></span>
    
4. <span data-ttu-id="57b70-127">在 [**活動提醒**] 頁面上，按一下 [**新增提醒**。</span><span class="sxs-lookup"><span data-stu-id="57b70-127">On the **Activity alerts** page, click **Add an alert**.</span></span>
    
    ![新增活動通知](media/53888bd5-9fa2-4398-8ccc-1a9dc72517ac.png)
  
5. <span data-ttu-id="57b70-129">完成下列欄位來建立的提醒：</span><span class="sxs-lookup"><span data-stu-id="57b70-129">Complete the following fields to create an alert:</span></span>
    
    <span data-ttu-id="57b70-p106">a.**名稱**-輸入警示的名稱。警示名稱必須是唯一組織內。</span><span class="sxs-lookup"><span data-stu-id="57b70-p106">a. **Name** - Type a name for the alert. Alert names must be unique within your organization.</span></span>
    
    <span data-ttu-id="57b70-p107">b.「**描述**（選擇性）-說明此通知，例如活動與使用者所追蹤並來傳送電子郵件通知使用者。說明提供快速又簡單的方式來描述此通知，其他系統管理員的用途。</span><span class="sxs-lookup"><span data-stu-id="57b70-p107">b. **Description** (Optional) - Describe the alert, such as the activities and users being tracked, and the users that email notifications are sent to. Descriptions provide a quick and easy way to describe the purpose of the alert to other admins.</span></span>
    
    <span data-ttu-id="57b70-p108">c.**傳送此提醒時**按一下 [**傳送此警示何時**然後設定下列兩個欄位：</span><span class="sxs-lookup"><span data-stu-id="57b70-p108">c. **Send this alert when** - Click **Send this alert when** and then configure these two fields:</span></span>
    
    - <span data-ttu-id="57b70-p109">**活動**-按一下下拉式清單以顯示您可以建立的提醒的活動。這是搜尋 Office 365 稽核記錄時顯示相同活動清單。您可以選取一或多個特定活動或您可以按一下 [選取群組中的所有活動的活動群組名稱。如需這些活動的說明，請參閱"稽核活動 」 區段中的[搜尋稽核記錄中的 Office 365 安全性 & 規範中心](search-the-audit-log-in-security-and-compliance.md#audited-activities)。當使用者執行任何已新增至警示的活動時，就會傳送電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="57b70-p109">**Activities** - Click the drop-down list to display the activities that you can create an alert for. This is the same activities list that's displayed when you search the Office 365 audit log. You can select one or more specific activities or you can click the activity group name to select all activities in the group. For a description of these activities, see the "Audited activities" section in [Search the audit log in the Office 365 Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#audited-activities). When a user performs any of the activities that you've added to the alert, an email notification is sent.</span></span> 
    
     - <span data-ttu-id="57b70-p110">**使用者**-按一下此方塊，然後選取 [一或多個使用者。如果使用者在此方塊中的執行您加入至 [**活動**] 方塊中，將傳送通知。保留 [**使用者**] 方塊為空白時要傳送提醒您組織中的任何使用者執行此通知所指定的活動。</span><span class="sxs-lookup"><span data-stu-id="57b70-p110">**Users** - Click this box and then select one or more users. If the users in this box perform the activities that you added to the **Activities** box, an alert will be sent. Leave the **Users** box blank to send an alert when any user in your organization performs the activities specified by the alert.</span></span> 
    
    <span data-ttu-id="57b70-p111">**傳送到此警示**-d 按一下 [**傳送此提醒**] 然後按一下 [**收件者**] 方塊並輸入要新增 （在 [**使用者**] 方塊中指定） 在使用者執行活動時將會收到的電子郵件通知的使用者名稱 (中所指定的**活動**方塊）。請注意您被新增到 [收件者] 清單的預設值。您可以從這個清單移除您的名稱。</span><span class="sxs-lookup"><span data-stu-id="57b70-p111">d. **Send this alert to** - Click **Send this alert**, and then click in the **Recipients** box and type a name to add a users who will receive an email notification when a user (specified in the **Users** box) performs an activity (specified in the **Activities** box). Note that you are added to the list of recipients by default. You can remove your name from this list.</span></span>
    
6. <span data-ttu-id="57b70-150">按一下 [**儲存**] 以建立警示。</span><span class="sxs-lookup"><span data-stu-id="57b70-150">Click **Save** to create the alert.</span></span> 
    
    <span data-ttu-id="57b70-151">在 [**活動提醒**] 頁面上的清單中顯示新提醒。</span><span class="sxs-lookup"><span data-stu-id="57b70-151">The new alert is displayed in the list on the **Activity alerts** page.</span></span> 
    
    ![提醒清單隨即顯示在 [安全性] 活動提醒] 頁面上&amp;規範中心](media/02b774f2-1719-41de-bbc9-5e5b7576f335.png)
  
    <span data-ttu-id="57b70-p112">警示的狀態設為**上**。請注意也列出的收件者傳送提醒時將會收到的電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="57b70-p112">The status of the alert is set to **On**. Note that the recipients who will received an email notification when an alert is sent are also listed.</span></span> 
  
## <a name="turn-off-an-activity-alert"></a><span data-ttu-id="57b70-155">關閉活動通知</span><span class="sxs-lookup"><span data-stu-id="57b70-155">Turn off an activity alert</span></span>

<span data-ttu-id="57b70-p113">您可以關閉活動通知，讓就不會傳送的電子郵件通知。關閉活動警示之後，它仍然會顯示清單中的活動提醒您的組織與您仍然可以檢視其內容。</span><span class="sxs-lookup"><span data-stu-id="57b70-p113">You can turn off an activity alert so that an email notification isn't sent. After you turn off the activity alert, it's still displayed in the list of activity alerts for your organization, and you can still view its properties.</span></span>
  
1. <span data-ttu-id="57b70-158">移至 [ [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="57b70-158">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="57b70-159">登入 Office 365 中，使用您工作或學校的帳戶。</span><span class="sxs-lookup"><span data-stu-id="57b70-159">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="57b70-160">在左窗格中，按一下 [**提醒**] 和 [**管理活動提醒**。</span><span class="sxs-lookup"><span data-stu-id="57b70-160">In the left pane, click **Alerts**, and then click **Manage activity alerts**.</span></span>
    
4. <span data-ttu-id="57b70-161">在提醒您的組織清單中，按一下您想要關閉的警示。</span><span class="sxs-lookup"><span data-stu-id="57b70-161">In the list of alerts for your organization, click the alert that you want to turn off.</span></span>
    
5. <span data-ttu-id="57b70-162">在**編輯提醒**] 頁面上按一下 [**上**切換切換到狀態變更為 [**關閉**] 和 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="57b70-162">On the **Edit alert** page, click the **On** toggle switch to change the status to **Off**, and then click **Save**.</span></span>
    
    <span data-ttu-id="57b70-163">活動提醒頁面上的提醒的狀態設為**關閉**。</span><span class="sxs-lookup"><span data-stu-id="57b70-163">The status of the alert on the Activity alerts pages is set to **Off**.</span></span> 
    
<span data-ttu-id="57b70-164">打開活動通知，剛重複這些步驟，然後按一下 [**關閉**切換參數，可將狀態變更為**上**。</span><span class="sxs-lookup"><span data-stu-id="57b70-164">To turn an activity alert back on, just repeat these steps and click the **Off** toggle switch to change the status to **On**.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="57b70-165">其他資訊</span><span class="sxs-lookup"><span data-stu-id="57b70-165">More information</span></span>

- <span data-ttu-id="57b70-166">以下是範例電子郵件通知傳送給寄件者欄位 （及**活動提醒**] 頁面上的下所列的**的收件者**） 安全性此警示中所指定的使用者&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="57b70-166">Here's an example of the email notification that is sent to the users that are specified in the Sent this alert to field (and listed under **Recipients** on the **Activity alerts** page ) in the Security &amp; Compliance Center.</span></span> 
    
    ![活動通知傳送給電子郵件 notifcation 的範例](media/a5f91611-fae6-4fe9-82f5-58521a2e2541.png)
  
- <span data-ttu-id="57b70-p114">以下是一些常見文件和電子郵件的活動您可以建立活動的提醒。表格說明活動、 建立提醒活動的名稱及活動會列在下 [**活動**] 下拉式清單中的 [活動] 群組的名稱。若要查看您可以建立的活動提醒的活動的完整清單，請參閱[的搜尋稽核記錄中的 Office 365 安全性 & 規範中心](search-the-audit-log-in-security-and-compliance.md#audited-activities)」 稽核活動"區段。</span><span class="sxs-lookup"><span data-stu-id="57b70-p114">Here's are some common document and email activities that you can create an activity alerts for. The tables describes the activity, the name of the activity to create an alert for, and the name of the activity group that the activity is listed under in the **Activities** drop-down list. To see a complete list of the activities that you can create activity alerts for, see the "Audited activities" section in [Search the audit log in the Office 365 Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#audited-activities).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="57b70-p115">您可能會想要建立只是一個活動所執行的任何使用者活動提醒。或是要建立追蹤多個活動由下列一或完了執行活動通知使用者。</span><span class="sxs-lookup"><span data-stu-id="57b70-p115">You might want to create an activity alert for just one activity that's performed by any user. Or you might want to create an activity alert that track multiple activities performed by one or mores users.</span></span> 
  
    <span data-ttu-id="57b70-173">下表列出一些常見文件相關的活動 SharePoint 或 OneDrive for Business。</span><span class="sxs-lookup"><span data-stu-id="57b70-173">The following table lists some common document-related activities in SharePoint or OneDrive for Business.</span></span>
    
    |<span data-ttu-id="57b70-174">**當使用者執行此動作...]**</span><span class="sxs-lookup"><span data-stu-id="57b70-174">**When a user does this...**</span></span>|<span data-ttu-id="57b70-175">**建立此活動的提醒**</span><span class="sxs-lookup"><span data-stu-id="57b70-175">**Create an alert for this activity**</span></span>|<span data-ttu-id="57b70-176">**活動群組**</span><span class="sxs-lookup"><span data-stu-id="57b70-176">**Activity group**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="57b70-177">檢視網站的文件。</span><span class="sxs-lookup"><span data-stu-id="57b70-177">Views a document on a site.</span></span>  <br/> |<span data-ttu-id="57b70-178">存取過之檔案</span><span class="sxs-lookup"><span data-stu-id="57b70-178">Accessed file</span></span>  <br/> |<span data-ttu-id="57b70-179">檔案及資料夾的活動</span><span class="sxs-lookup"><span data-stu-id="57b70-179">File and folder activities</span></span>  <br/> |
    |<span data-ttu-id="57b70-180">編輯或變更文件。</span><span class="sxs-lookup"><span data-stu-id="57b70-180">Edits or changes a document.</span></span>  <br/> |<span data-ttu-id="57b70-181">修改的檔案</span><span class="sxs-lookup"><span data-stu-id="57b70-181">Modified file</span></span>  <br/> |<span data-ttu-id="57b70-182">檔案及資料夾的活動</span><span class="sxs-lookup"><span data-stu-id="57b70-182">File and folder activities</span></span>  <br/> |
    |<span data-ttu-id="57b70-183">與組織外的使用者共用文件。</span><span class="sxs-lookup"><span data-stu-id="57b70-183">Shares a document with a user outside of your organization.</span></span>  <br/> |<span data-ttu-id="57b70-184">共用檔案、 資料夾或網站</span><span class="sxs-lookup"><span data-stu-id="57b70-184">Share file, folder, or site</span></span>  <br/> <span data-ttu-id="57b70-185">且</span><span class="sxs-lookup"><span data-stu-id="57b70-185">And</span></span>  <br/> <span data-ttu-id="57b70-186">建立共用邀請</span><span class="sxs-lookup"><span data-stu-id="57b70-186">Created sharing invitation</span></span>  <br/> <span data-ttu-id="57b70-187">如需詳細資訊，請參閱[使用共用的 Office 365 稽核記錄中的稽核](use-sharing-auditing.md)。</span><span class="sxs-lookup"><span data-stu-id="57b70-187">For more information, see [Use sharing auditing in the Office 365 audit log](use-sharing-auditing.md).</span></span>  <br/> |<span data-ttu-id="57b70-188">共用和存取要求活動</span><span class="sxs-lookup"><span data-stu-id="57b70-188">Sharing and access request activities</span></span>  <br/> |
    |<span data-ttu-id="57b70-189">上傳或下載文件。</span><span class="sxs-lookup"><span data-stu-id="57b70-189">Uploads or downloads a document.</span></span>  <br/> |<span data-ttu-id="57b70-190">上傳的檔案</span><span class="sxs-lookup"><span data-stu-id="57b70-190">Uploaded file</span></span>  <br/> <span data-ttu-id="57b70-191">及 （或)</span><span class="sxs-lookup"><span data-stu-id="57b70-191">And/or</span></span>  <br/> <span data-ttu-id="57b70-192">下載的檔案</span><span class="sxs-lookup"><span data-stu-id="57b70-192">Downloaded file</span></span>  <br/> |<span data-ttu-id="57b70-193">檔案及資料夾的活動</span><span class="sxs-lookup"><span data-stu-id="57b70-193">File and folder activities</span></span>  <br/> |
    |<span data-ttu-id="57b70-194">變更網站的存取權限。</span><span class="sxs-lookup"><span data-stu-id="57b70-194">Changes the access permissions to a site.</span></span>  <br/> |<span data-ttu-id="57b70-195">修改的網站權限</span><span class="sxs-lookup"><span data-stu-id="57b70-195">Modified site permissions</span></span>  <br/> |<span data-ttu-id="57b70-196">網站管理活動</span><span class="sxs-lookup"><span data-stu-id="57b70-196">Site administration activities</span></span>  <br/> |

    <span data-ttu-id="57b70-197">下表列出在 Exchange Online 中的一些常見電子郵件相關活動。</span><span class="sxs-lookup"><span data-stu-id="57b70-197">The following table lists some common email-related activities in Exchange Online.</span></span>

    |<span data-ttu-id="57b70-198">**當使用者執行此動作...]**</span><span class="sxs-lookup"><span data-stu-id="57b70-198">**When a user does this...**</span></span>|<span data-ttu-id="57b70-199">**建立此活動的提醒**</span><span class="sxs-lookup"><span data-stu-id="57b70-199">**Create an alert for this activity**</span></span>|<span data-ttu-id="57b70-200">**活動群組**</span><span class="sxs-lookup"><span data-stu-id="57b70-200">**Activity group**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="57b70-201">永久刪除 （清除） 電子郵件訊息從他們的信箱。</span><span class="sxs-lookup"><span data-stu-id="57b70-201">Permanently deletes (purges) an email message from their mailbox.</span></span>  <br/> |<span data-ttu-id="57b70-202">從 [信箱清除的郵件</span><span class="sxs-lookup"><span data-stu-id="57b70-202">Purged messages from mailbox</span></span>  <br/> | <span data-ttu-id="57b70-203">Exchange 信箱的活動</span><span class="sxs-lookup"><span data-stu-id="57b70-203">Exchange mailbox activities</span></span>  <br/> |
    |<span data-ttu-id="57b70-204">從共用信箱傳送電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="57b70-204">Sends an email message from a shared mailbox.</span></span>  <br/> |<span data-ttu-id="57b70-205">傳送郵件使用下列傳送] 權限</span><span class="sxs-lookup"><span data-stu-id="57b70-205">Sent message using Send As permissions</span></span>  <br/> <span data-ttu-id="57b70-206">且</span><span class="sxs-lookup"><span data-stu-id="57b70-206">And</span></span>  <br/> <span data-ttu-id="57b70-207">傳送郵件使用傳送代理者權限</span><span class="sxs-lookup"><span data-stu-id="57b70-207">Sent message using Send On Behalf permissions</span></span>  <br/> | <span data-ttu-id="57b70-208">Exchange 信箱的活動</span><span class="sxs-lookup"><span data-stu-id="57b70-208">Exchange mailbox activities</span></span>  <br/> |
   
- <span data-ttu-id="57b70-p116">您也可以使用**New ActivityAlert**和**設定 ActivityAlert**指令程式的安全性&amp;規範中心 PowerShell 來建立及編輯活動提醒。如果您使用這些 cmdlet 來建立或編輯活動提醒，請記住下列事項：</span><span class="sxs-lookup"><span data-stu-id="57b70-p116">You can also use the **New-ActivityAlert** and **Set-ActivityAlert** cmdlets in Security &amp; Compliance Center PowerShell to create and edit activity alerts. Keep the following things in mind if you use these cmdlets to create or edit activity alerts:</span></span> 
    
  - <span data-ttu-id="57b70-211">如果您使用指令程式將活動新增至 [**活動**] 下拉式清單中未列出提醒、 訊息以顯示在 [屬性] 頁面上的提醒，「 此警示中有沒有列在選擇器中的自訂作業 」。</span><span class="sxs-lookup"><span data-stu-id="57b70-211">If you use a cmdlet to add an activity to the alert that isn't listed in the **Activities** drop-down list, a message is displayed in on the property page for the alert that says, "This alert has custom operations not listed in the picker."</span></span> 
    
  - <span data-ttu-id="57b70-p117">若要使用 cmdlet 來建立或編輯活動通知良好的原因是傳送電子郵件通知給組織外的某個人。此外部使用者將會列在清單中的收件者的通知。如果您從警示移除此外部的使用者，該使用者不能重新加入至警示安全性中使用**編輯提醒**] 頁面上，但是&amp;規範中心。您將必須重新新增外部使用者使用此**組 ActivityAlert**指令程式，或使用**新 ActivityAlert**指令程式將同一個 （或不同） 的外部使用者新增至新的提醒。</span><span class="sxs-lookup"><span data-stu-id="57b70-p117">A good reason to use the cmdlets to create or edit an activity alert is to send email notifications to someone outside of your organization. This external user will be listed in the list of recipients for the alert. But if you remove this external user from the alert, that user can't be re-added to the alert by using **Edit alert** page in the Security &amp; Compliance Center. You'll have to re-add the external user using the **Set-ActivityAlert** cmdlet, or use the **New-ActivityAlert** cmdlet to add the same (or different) external user to a new alert.</span></span> 
    
  
