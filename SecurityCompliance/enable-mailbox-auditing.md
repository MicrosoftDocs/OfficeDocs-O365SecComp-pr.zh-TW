---
title: 啟用 Office 365中的信箱稽核
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: aaca8987-5b62-458b-9882-c28476a66918
description: 在 Office 365 中，您可以開啟信箱稽核記錄來依信箱擁有者、 委派及系統管理員記錄信箱存取。根據預設，Office 365 中的信箱稽核無法開啟。啟用信箱稽核記錄功能信箱之後，您可以搜尋活動在信箱上執行的 Office 365 稽核記錄。
ms.openlocfilehash: 9952cc94fe48e289e6eaf8de665a82cb3da4746d
ms.sourcegitcommit: b6473cd6ba3f9ac79dc6a2040fc148020dfbe464
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/02/2018
ms.locfileid: "25358382"
---
# <a name="enable-mailbox-auditing-in-office-365"></a><span data-ttu-id="475e7-105">啟用 Office 365中的信箱稽核</span><span class="sxs-lookup"><span data-stu-id="475e7-105">Enable mailbox auditing in Office 365</span></span>
  
<span data-ttu-id="475e7-p102">在 Office 365 中，您可以開啟信箱稽核記錄來依信箱擁有者、 委派及系統管理員記錄信箱存取。根據預設，Office 365 中的信箱稽核無法開啟。這表示信箱稽核事件將不會出現在結果搜尋信箱活動的 Office 365 稽核記錄時。但是您開啟信箱稽核記錄功能的使用者信箱後，您可以搜尋信箱活動的稽核記錄。此外，當信箱稽核記錄已啟動，由系統管理員、 委派、 執行某些動作及預設會記錄擁有者。記錄 （及然後搜尋） 其他動作，請參閱步驟 3。</span><span class="sxs-lookup"><span data-stu-id="475e7-p102">In Office 365, you can turn on mailbox audit logging to log mailbox access by mailbox owners, delegates, and administrators. By default, mailbox auditing in Office 365 isn't turned on. That means mailbox auditing events won't appear in the results when you search the Office 365 audit log for mailbox activity. But after you turn on mailbox audit logging for a user mailbox, you can search the audit log for mailbox activity. Additionally, when mailbox audit logging is turned on, some actions performed by administrators, delegates, and owners are logged by default. To log (and then search for) additional actions, see Step 3.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="475e7-112">開始之前</span><span class="sxs-lookup"><span data-stu-id="475e7-112">Before you begin</span></span>
  
- <span data-ttu-id="475e7-p103">您必須使用 Exchange Online PowerShell 來啟用信箱稽核記錄。您不能使用 Office 365 安全性&amp;規範中心 」 或 「 Exchange 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="475e7-p103">You have to use Exchange Online PowerShell to enable mailbox audit logging. You can't use the Office 365 Security &amp; Compliance Center or the Exchange admin center.</span></span>
    
- <span data-ttu-id="475e7-p104">啟用信箱稽核記錄功能信箱之後，存取權的信箱與特定管理員和委派動作會記錄預設。若要記錄信箱擁有者所採取的動作，您必須指定所要稽核的擁有者動作。請參閱啟用信箱稽核記錄之後的動作清單，以及哪些動作都可供每種類型的使用者登入"更多資訊 」 一節。</span><span class="sxs-lookup"><span data-stu-id="475e7-p104">After you enable mailbox audit logging for a mailbox, access to the mailbox and certain admin and delegate actions are logged by default. To log actions taken by the mailbox owner, you must specify which owner actions to audit. See the "More info" section to see a list of actions that are logged after mailbox audit logging is enabled, and which actions are available for each type of user logon.</span></span>
    
- <span data-ttu-id="475e7-118">您無法啟用信箱稽核記錄與 Office 365 群組或小組中的 Microsoft 小組關聯的信箱。</span><span class="sxs-lookup"><span data-stu-id="475e7-118">You can't enable mailbox audit logging for the mailbox that's associated with an Office 365 Group or a team in Microsoft Teams.</span></span>
    
- <span data-ttu-id="475e7-119">獲指派使用者信箱「完整存取」權限的系統管理員會被視為委派使用者。</span><span class="sxs-lookup"><span data-stu-id="475e7-119">An administrator who has been assigned the Full Access permission to a user's mailbox is considered a delegate user.</span></span>
  
## <a name="step-1-connect-to-exchange-online-powershell"></a><span data-ttu-id="475e7-120">步驟 1： 連線至 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="475e7-120">Step 1: Connect to Exchange Online PowerShell</span></span>

1. <span data-ttu-id="475e7-121">在您的本機電腦上開啟 Windows PowerShell，並執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="475e7-121">On your local computer, open Windows PowerShell and run the following command.</span></span>
   
    ```
    $UserCredential = Get-Credential
    ```

2. <span data-ttu-id="475e7-122">在**Windows PowerShell 認證要求**] 對話方塊中，輸入使用者名稱與 Office 365 全域管理員帳戶密碼，並再按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="475e7-122">In the **Windows PowerShell Credential Request** dialog box, type user name and password for an Office 365 global admin account, and then click **OK**.</span></span>
    
3. <span data-ttu-id="475e7-123">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="475e7-123">Run the following command:</span></span>
    
    ```
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    ```

3. <span data-ttu-id="475e7-124">執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="475e7-124">Run the following command.</span></span>

    ```
    Import-PSSession $Session
    ```
   
4. <span data-ttu-id="475e7-125">若要確認您已連線至 Exchange Online 組織，執行下列命令以取得貴組織中所有信箱的清單：</span><span class="sxs-lookup"><span data-stu-id="475e7-125">To verify that you're connected to your Exchange Online organization, run the following command to get a list of all the mailboxes in your organization.</span></span>
    
    ```
    Get-Mailbox
    ```
  
<span data-ttu-id="475e7-126">如需詳細資訊或如果您無法連線到您的 Exchange Online 組織，請參閱[使用遠端 PowerShell 連線到 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=517283)。</span><span class="sxs-lookup"><span data-stu-id="475e7-126">For more information or if you have problems connecting to your Exchange Online organization, see [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283).</span></span>
  
## <a name="step-2-enable-mailbox-audit-logging"></a><span data-ttu-id="475e7-127">步驟 2：啟用信箱稽核記錄</span><span class="sxs-lookup"><span data-stu-id="475e7-127">Step 2: Enable mailbox audit logging</span></span>

<span data-ttu-id="475e7-p105">連線至 Exchange Online 組織之後，使用 PowerShell 針對信箱啟用信箱稽核記錄。或者，您可以啟用信箱稽核貴組織中的所有信箱。</span><span class="sxs-lookup"><span data-stu-id="475e7-p105">After you connect to your Exchange Online organization, use PowerShell to enable mailbox audit logging for a mailbox. Alternatively, you can enable mailbox auditing for all mailboxes in your organization.</span></span>
  
<span data-ttu-id="475e7-130">本範例啟用信箱稽核記錄 Pilar Pinilla 信箱。</span><span class="sxs-lookup"><span data-stu-id="475e7-130">This example enables mailbox audit logging for Pilar Pinilla's mailbox.</span></span>
  
```
Set-Mailbox -Identity "Pilar Pinilla" -AuditEnabled $true
```

<span data-ttu-id="475e7-131">此範例會啟用組織中所有使用者信箱的信箱稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="475e7-131">This example enables mailbox audit logging for all user mailboxes in your organization.</span></span>
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -AuditEnabled $true
```
  
## <a name="step-3-specify-owner-actions-to-audit"></a><span data-ttu-id="475e7-132">步驟 3：指定要稽核的擁有者動作</span><span class="sxs-lookup"><span data-stu-id="475e7-132">Step 3: Specify owner actions to audit</span></span>

<span data-ttu-id="475e7-p106">當您啟用信箱稽核時，只有一個巨集指令 ( **UpdateFolderPermissions** ) 信箱擁有者執行是依預設稽核。您必須指定稽核其他擁有者動作。請參閱清單及描述要稽核的擁有者動作"信箱動作 」 一節中的表格。</span><span class="sxs-lookup"><span data-stu-id="475e7-p106">When you enable auditing for a mailbox, only one action ( **UpdateFolderPermissions** ) performed by the mailbox owner is audited by default. You have to specify other owner actions to audit. See the table in the "Mailbox actions" section for a list and description of owner actions that can be audited.</span></span> 
  
<span data-ttu-id="475e7-p107">本範例會新增到信箱的 Pilar Pinilla 信箱稽核**MailboxLogin**和**HardDelete**擁有者動作。本範例會假設該信箱稽核已經啟用此信箱。</span><span class="sxs-lookup"><span data-stu-id="475e7-p107">This example adds the **MailboxLogin** and **HardDelete** owner actions to mailbox auditing for Pilar Pinilla's mailbox. This example assumes that mailbox auditing has already been enabled for this mailbox.</span></span> 

```
Set-Mailbox "Pilar Pinilla" -AuditOwner @{Add="MailboxLogin","HardDelete"}
```

<span data-ttu-id="475e7-p108">本範例個 Don 館信箱啟用信箱稽核記錄並指定僅信箱擁有者執行**MailboxLogin**動作都將被記錄。請注意此範例會覆寫預設 UpdateFolderPermissions 巨集指令。</span><span class="sxs-lookup"><span data-stu-id="475e7-p108">This example enables mailbox audit logging for Don Hall's mailbox and specifies that only the **MailboxLogin** action performed by the mailbox owner will be logged. Note that this example overwrites the default UpdateFolderPermissions action.</span></span> 
  
```
Set-Mailbox "Don Hall" -AuditEnabled $true -AuditOwner MailboxLogin
```
   
<span data-ttu-id="475e7-p109">本範例會將**MailboxLogin**、 **HardDelete**和**SoftDelete**擁有者動作新增至組織中的所有信箱。本範例會假設該信箱稽核已經啟用的所有信箱。</span><span class="sxs-lookup"><span data-stu-id="475e7-p109">This example adds the **MailboxLogin**, **HardDelete**, and **SoftDelete** owner actions to all mailboxes in the organization. This example assumes that mailbox auditing has already been enabled for all mailboxes.</span></span> 
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -AuditOwner @{Add="MailboxLogin","HardDelete","SoftDelete"}
```
  
## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="475e7-142">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="475e7-142">How do you know this worked?</span></span>

<span data-ttu-id="475e7-143">若要確認您已成功啟用信箱的信箱稽核記錄，請使用 **Get-Mailbox** Cmdlet 來擷取該信箱的稽核設定。</span><span class="sxs-lookup"><span data-stu-id="475e7-143">To verify that you have successfully enabled mailbox audit logging for a mailbox, use the **Get-Mailbox** cmdlet to retrieve the auditing settings for that mailbox.</span></span> 
  
<span data-ttu-id="475e7-144">此範例會擷取 Pilar Pinilla 的稽核設定。</span><span class="sxs-lookup"><span data-stu-id="475e7-144">This example retrieves the auditing settings for Pilar Pinilla.</span></span>

```
Get-Mailbox "Pilar Pinilla"| FL Audit*
```
   
<span data-ttu-id="475e7-145">此範例會擷取您組織中所有使用者信箱的稽核設定。</span><span class="sxs-lookup"><span data-stu-id="475e7-145">This example retrieves the auditing settings for all user mailboxes in your organization.</span></span>

```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | FL Name,Audit*
```
   
<span data-ttu-id="475e7-146">提供驗證**AuditEnabled**屬性信箱的**則為 True**值該信箱稽核記錄已啟用。</span><span class="sxs-lookup"><span data-stu-id="475e7-146">A value of **True** for the **AuditEnabled** property verifies that mailbox audit logging is enabled.</span></span> 
    
## <a name="mailbox-auditing-actions"></a><span data-ttu-id="475e7-147">信箱稽核的動作</span><span class="sxs-lookup"><span data-stu-id="475e7-147">Mailbox auditing actions</span></span>
  
<span data-ttu-id="475e7-p110">下表列出可以信箱所記錄的動作稽核記錄。表格包含可針對不同的使用者登入類型記錄的動作。在表格中，**無**表示巨集指令不會記錄以登入類型。星號 ( **\*** ) 會指出動作會記錄預設時信箱稽核記錄已啟用信箱。先前所述，當您開啟信箱的稽核時依預設稽核只擁有者動作是 UpdateFolderPermissions。若要記錄其他信箱擁有者所採取的動作，您必須指定其他的擁有者稽核的動作。若要這樣做，請參閱本主題中的[步驟 3](#step-3-specify-owner-actions-to-audit) 。</span><span class="sxs-lookup"><span data-stu-id="475e7-p110">The following table lists the actions that can be logged by mailbox audit logging. The table includes which action can be logged for the different user logon types. In the table, a **No** indicates that an action can't be logged for that logon type. An asterisk ( **\*** ) indicates that the action is logged by default when mailbox audit logging is enabled for the mailbox. As previously stated, the only owner action audited by default when you turn on mailbox auditing is UpdateFolderPermissions. To log other actions taken by the mailbox owner, you must specify additional owner actions to audit. To do this, see [Step 3](#step-3-specify-owner-actions-to-audit) in this topic.</span></span> 
  
|<span data-ttu-id="475e7-155">**動作**</span><span class="sxs-lookup"><span data-stu-id="475e7-155">**Action**</span></span>|<span data-ttu-id="475e7-156">**描述**</span><span class="sxs-lookup"><span data-stu-id="475e7-156">**Description**</span></span>|<span data-ttu-id="475e7-157">**Admin**</span><span class="sxs-lookup"><span data-stu-id="475e7-157">**Admin**</span></span>|<span data-ttu-id="475e7-158">**委派\*\*\***</span><span class="sxs-lookup"><span data-stu-id="475e7-158">**Delegate\*\*\***</span></span>|<span data-ttu-id="475e7-159">**擁有者**</span><span class="sxs-lookup"><span data-stu-id="475e7-159">**Owner**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="475e7-160">**Copy**</span><span class="sxs-lookup"><span data-stu-id="475e7-160">**Copy**</span></span> <br/> |<span data-ttu-id="475e7-161">郵件已複製到另一個資料夾。</span><span class="sxs-lookup"><span data-stu-id="475e7-161">A message was copied to another folder.</span></span>  <br/> |<span data-ttu-id="475e7-162">是</span><span class="sxs-lookup"><span data-stu-id="475e7-162">Yes</span></span>  <br/> |<span data-ttu-id="475e7-163">否</span><span class="sxs-lookup"><span data-stu-id="475e7-163">No</span></span>  <br/> |<span data-ttu-id="475e7-164">否</span><span class="sxs-lookup"><span data-stu-id="475e7-164">No</span></span>  <br/> |
|<span data-ttu-id="475e7-165">**Create**</span><span class="sxs-lookup"><span data-stu-id="475e7-165">**Create**</span></span> <br/> |<span data-ttu-id="475e7-p111">在信箱 ； 中的 [行事曆、 連絡人、 備忘稿或工作] 資料夾中建立項目例如，會建立新的會議邀請。請注意不稽核建立、 傳送或接收郵件。此外，不稽核建立信箱資料夾。</span><span class="sxs-lookup"><span data-stu-id="475e7-p111">An item is created in the Calendar, Contacts, Notes, or Tasks folder in the mailbox; for example, a new meeting request is created. Note that creating, sending, or receiving a message isn't audited. Also, creating a mailbox folder is not audited.</span></span>  <br/> |<span data-ttu-id="475e7-169">是\*</span><span class="sxs-lookup"><span data-stu-id="475e7-169">Yes\*</span></span>  <br/> |<span data-ttu-id="475e7-170">是\*</span><span class="sxs-lookup"><span data-stu-id="475e7-170">Yes\*</span></span>  <br/> |<span data-ttu-id="475e7-171">是</span><span class="sxs-lookup"><span data-stu-id="475e7-171">Yes</span></span>  <br/> |
|<span data-ttu-id="475e7-172">**FolderBind**</span><span class="sxs-lookup"><span data-stu-id="475e7-172">**FolderBind**</span></span> <br/> |<span data-ttu-id="475e7-p112">已存取信箱資料夾。系統管理員或代理人開啟信箱時也會記錄此動作。</span><span class="sxs-lookup"><span data-stu-id="475e7-p112">A mailbox folder was accessed. This action is also logged when the admin or delegate opens the mailbox.</span></span>  <br/> |<span data-ttu-id="475e7-175">是</span><span class="sxs-lookup"><span data-stu-id="475e7-175">Yes</span></span>  <br/> |<span data-ttu-id="475e7-176">[是]\*\*</span><span class="sxs-lookup"><span data-stu-id="475e7-176">Yes\*\*</span></span>  <br/> |<span data-ttu-id="475e7-177">否</span><span class="sxs-lookup"><span data-stu-id="475e7-177">No</span></span>  <br/> |
|<span data-ttu-id="475e7-178">**HardDelete**</span><span class="sxs-lookup"><span data-stu-id="475e7-178">**HardDelete**</span></span> <br/> |<span data-ttu-id="475e7-179">郵件已經從 [可復原的項目] 資料夾清除。</span><span class="sxs-lookup"><span data-stu-id="475e7-179">A message was purged from the Recoverable Items folder.</span></span>  <br/> |<span data-ttu-id="475e7-180">是\*</span><span class="sxs-lookup"><span data-stu-id="475e7-180">Yes\*</span></span>  <br/> |<span data-ttu-id="475e7-181">是\*</span><span class="sxs-lookup"><span data-stu-id="475e7-181">Yes\*</span></span>  <br/> |<span data-ttu-id="475e7-182">是</span><span class="sxs-lookup"><span data-stu-id="475e7-182">Yes</span></span>  <br/> |
|<span data-ttu-id="475e7-183">**MailboxLogin**</span><span class="sxs-lookup"><span data-stu-id="475e7-183">**MailboxLogin**</span></span> <br/> |<span data-ttu-id="475e7-184">使用者已登入其信箱。</span><span class="sxs-lookup"><span data-stu-id="475e7-184">The user signed in to their mailbox.</span></span>  <br/> |<span data-ttu-id="475e7-185">否</span><span class="sxs-lookup"><span data-stu-id="475e7-185">No</span></span>  <br/> |<span data-ttu-id="475e7-186">否</span><span class="sxs-lookup"><span data-stu-id="475e7-186">No</span></span>  <br/> |<span data-ttu-id="475e7-187">是</span><span class="sxs-lookup"><span data-stu-id="475e7-187">Yes</span></span>  <br/> |
|<span data-ttu-id="475e7-188">**MessageBind**</span><span class="sxs-lookup"><span data-stu-id="475e7-188">**MessageBind**</span></span> <br/> |<span data-ttu-id="475e7-189">在預覽窗格中檢視郵件或將它開啟。</span><span class="sxs-lookup"><span data-stu-id="475e7-189">A message was viewed in the preview pane or opened.</span></span>  <br/> |<span data-ttu-id="475e7-190">是</span><span class="sxs-lookup"><span data-stu-id="475e7-190">Yes</span></span>  <br/> |<span data-ttu-id="475e7-191">否</span><span class="sxs-lookup"><span data-stu-id="475e7-191">No</span></span>  <br/> |<span data-ttu-id="475e7-192">否</span><span class="sxs-lookup"><span data-stu-id="475e7-192">No</span></span>  <br/> |
|<span data-ttu-id="475e7-193">**Move**</span><span class="sxs-lookup"><span data-stu-id="475e7-193">**Move**</span></span> <br/> |<span data-ttu-id="475e7-194">郵件已移到另一個資料夾。</span><span class="sxs-lookup"><span data-stu-id="475e7-194">A message was moved to another folder.</span></span>  <br/> |<span data-ttu-id="475e7-195">是</span><span class="sxs-lookup"><span data-stu-id="475e7-195">Yes</span></span>  <br/> |<span data-ttu-id="475e7-196">是</span><span class="sxs-lookup"><span data-stu-id="475e7-196">Yes</span></span>  <br/> |<span data-ttu-id="475e7-197">是</span><span class="sxs-lookup"><span data-stu-id="475e7-197">Yes</span></span>  <br/> |
|<span data-ttu-id="475e7-198">**MoveToDeletedItems**</span><span class="sxs-lookup"><span data-stu-id="475e7-198">**MoveToDeletedItems**</span></span> <br/> |<span data-ttu-id="475e7-199">郵件已遭刪除並移至 [刪除的郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="475e7-199">A message was deleted and moved to the Deleted Items folder.</span></span>  <br/> |<span data-ttu-id="475e7-200">[是]\*</span><span class="sxs-lookup"><span data-stu-id="475e7-200">Yes\*</span></span>  <br/> |<span data-ttu-id="475e7-201">是\*</span><span class="sxs-lookup"><span data-stu-id="475e7-201">Yes\*</span></span>  <br/> |<span data-ttu-id="475e7-202">是</span><span class="sxs-lookup"><span data-stu-id="475e7-202">Yes</span></span>  <br/> |
|<span data-ttu-id="475e7-203">**SendAs**</span><span class="sxs-lookup"><span data-stu-id="475e7-203">**SendAs**</span></span> <br/> |<span data-ttu-id="475e7-p113">已使用 SendAs 權限傳送郵件。這表示，另一個使用者已傳送郵件，就像此郵件是來自信箱擁有者一樣。</span><span class="sxs-lookup"><span data-stu-id="475e7-p113">A message was sent using the SendAs permission. This means another user sent the message as though it came from the mailbox owner.</span></span>  <br/> |<span data-ttu-id="475e7-206">[是]\*</span><span class="sxs-lookup"><span data-stu-id="475e7-206">Yes\*</span></span>  <br/> |<span data-ttu-id="475e7-207">是\*</span><span class="sxs-lookup"><span data-stu-id="475e7-207">Yes\*</span></span>  <br/> |<span data-ttu-id="475e7-208">否</span><span class="sxs-lookup"><span data-stu-id="475e7-208">No</span></span>  <br/> |
|<span data-ttu-id="475e7-209">**SendOnBehalf**</span><span class="sxs-lookup"><span data-stu-id="475e7-209">**SendOnBehalf**</span></span> <br/> |<span data-ttu-id="475e7-p114">已使用 SendOnBehalf 權限傳送郵件。這表示，另一個使用者已代表信箱擁有者傳送郵件。此郵件會向收件者指示，此郵件是代表誰傳送，以及實際傳送郵件的人是誰。</span><span class="sxs-lookup"><span data-stu-id="475e7-p114">A message was sent using the SendOnBehalf permission. This means another user sent the message on behalf of the mailbox owner. The message indicates to the recipient who the message was sent on behalf of and who actually sent the message.</span></span>  <br/> |<span data-ttu-id="475e7-213">[是]\*</span><span class="sxs-lookup"><span data-stu-id="475e7-213">Yes\*</span></span>  <br/> |<span data-ttu-id="475e7-214">是\*</span><span class="sxs-lookup"><span data-stu-id="475e7-214">Yes\*</span></span>  <br/> |<span data-ttu-id="475e7-215">否</span><span class="sxs-lookup"><span data-stu-id="475e7-215">No</span></span>  <br/> |
|<span data-ttu-id="475e7-216">**SoftDelete**</span><span class="sxs-lookup"><span data-stu-id="475e7-216">**SoftDelete**</span></span> <br/> |<span data-ttu-id="475e7-p115">郵件已永久刪除或從 [刪除的郵件] 資料夾刪除。虛刪除的項目會移至 [可復原的項目] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="475e7-p115">A message was permanently deleted or deleted from the Deleted Items folder. Soft-deleted items are moved to the Recoverable Items folder.</span></span>  <br/> |<span data-ttu-id="475e7-219">[是]\*</span><span class="sxs-lookup"><span data-stu-id="475e7-219">Yes\*</span></span>  <br/> |<span data-ttu-id="475e7-220">是\*</span><span class="sxs-lookup"><span data-stu-id="475e7-220">Yes\*</span></span>  <br/> |<span data-ttu-id="475e7-221">是</span><span class="sxs-lookup"><span data-stu-id="475e7-221">Yes</span></span>  <br/> |
|<span data-ttu-id="475e7-222">**更新**</span><span class="sxs-lookup"><span data-stu-id="475e7-222">**Update**</span></span> <br/> |<span data-ttu-id="475e7-223">郵件或其屬性已變更。</span><span class="sxs-lookup"><span data-stu-id="475e7-223">A message or its properties was changed.</span></span>  <br/> |<span data-ttu-id="475e7-224">[是]\*</span><span class="sxs-lookup"><span data-stu-id="475e7-224">Yes\*</span></span>  <br/> |<span data-ttu-id="475e7-225">是\*</span><span class="sxs-lookup"><span data-stu-id="475e7-225">Yes\*</span></span>  <br/> |<span data-ttu-id="475e7-226">是</span><span class="sxs-lookup"><span data-stu-id="475e7-226">Yes</span></span>  <br/> |
|<span data-ttu-id="475e7-227">**UpdateCalendarDelegation**</span><span class="sxs-lookup"><span data-stu-id="475e7-227">**UpdateCalendarDelegation**</span></span> <br/> |<span data-ttu-id="475e7-p116">行事曆委派已指派給信箱。行事曆委派可讓其他人在相同的組織權限管理信箱擁有者的行事曆。</span><span class="sxs-lookup"><span data-stu-id="475e7-p116">A calendar delegation was assigned to a mailbox. Calendar delegation gives someone else in the same organization permissions to manage the mailbox owner's calendar.</span></span>  <br/> |<span data-ttu-id="475e7-230">是\*</span><span class="sxs-lookup"><span data-stu-id="475e7-230">Yes\*</span></span>  <br/> |<span data-ttu-id="475e7-231">否</span><span class="sxs-lookup"><span data-stu-id="475e7-231">No</span></span>  <br/> |<span data-ttu-id="475e7-232">是\*</span><span class="sxs-lookup"><span data-stu-id="475e7-232">Yes\*</span></span>  <br/> |
|<span data-ttu-id="475e7-233">**UpdateFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="475e7-233">**UpdateFolderPermissions**</span></span> <br/> |<span data-ttu-id="475e7-p117">已變更的資料夾權限。資料夾的權限控制您組織中的使用者可以存取信箱和那些資料夾中的郵件中的資料夾。</span><span class="sxs-lookup"><span data-stu-id="475e7-p117">A folder permission was changed. Folder permissions control which users in your organization can access folders in a mailbox and the messages located in those folders.</span></span>  <br/> |<span data-ttu-id="475e7-236">是\*</span><span class="sxs-lookup"><span data-stu-id="475e7-236">Yes\*</span></span>  <br/> |<span data-ttu-id="475e7-237">是\*</span><span class="sxs-lookup"><span data-stu-id="475e7-237">Yes\*</span></span>  <br/> |<span data-ttu-id="475e7-238">是\*</span><span class="sxs-lookup"><span data-stu-id="475e7-238">Yes\*</span></span>  <br/> |
|<span data-ttu-id="475e7-239">**UpdateInboxRules**</span><span class="sxs-lookup"><span data-stu-id="475e7-239">**UpdateInboxRules**</span></span> <br/> |<span data-ttu-id="475e7-p118">收件匣規則已新增、 移除或變更。收件匣規則可用來處理郵件的收件匣根據指定的條件和符合規則的條件，例如將郵件移至指定的資料夾或刪除郵件時採取的動作。</span><span class="sxs-lookup"><span data-stu-id="475e7-p118">An inbox rule has been added, removed, or changed. Inbox rules are used to process messages in the user's Inbox based on the specified conditions and take actions when the conditions of a rule are met, such as moving a message to a specified folder or deleting a message.</span></span>  <br/> |<span data-ttu-id="475e7-242">是\*</span><span class="sxs-lookup"><span data-stu-id="475e7-242">Yes\*</span></span>  <br/> |<span data-ttu-id="475e7-243">是\*</span><span class="sxs-lookup"><span data-stu-id="475e7-243">Yes\*</span></span>  <br/> |<span data-ttu-id="475e7-244">是\*</span><span class="sxs-lookup"><span data-stu-id="475e7-244">Yes\*</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="475e7-245"><sup>\*</sup>如果已啟用信箱，稽核預設。</span><span class="sxs-lookup"><span data-stu-id="475e7-245"><sup>\*</sup> Audited by default if auditing is enabled for a mailbox.</span></span><br/><br/>  <span data-ttu-id="475e7-p119"><sup>\*\*</sup>合併資料夾繫結動作委派所執行的項目。24 小時的時間範圍內的個別資料夾存取產生一個日誌項目。</span><span class="sxs-lookup"><span data-stu-id="475e7-p119"><sup>\*\*</sup> Entries for folder bind actions performed by delegates are consolidated. One log entry is generated for individual folder access within a time span of 24 hours.</span></span><br/><br/><span data-ttu-id="475e7-248"><sup>\*\*\*</sup>已指派完整存取權給使用者的信箱的系統管理員會被視為委派使用者。</span><span class="sxs-lookup"><span data-stu-id="475e7-248"><sup>\*\*\*</sup> An administrator who has been assigned the Full Access permission to a user's mailbox is considered a delegate user.</span></span> 
  
<span data-ttu-id="475e7-p120">如果您不再需要特定類型的信箱稽核的動作，您應修改停用這些動作的信箱稽核記錄設定。現有的記錄項目未清除直到達到 90 天的存留期限制稽核記錄項目。</span><span class="sxs-lookup"><span data-stu-id="475e7-p120">If you no longer require certain types of mailbox actions to be audited, you should modify the mailbox's audit logging configuration to disable those actions. Existing log entries aren't purged until the 90-day age limit for audit log entries is reached.</span></span>
  
## <a name="more-infotab"></a>[<span data-ttu-id="475e7-251">更多資訊</span><span class="sxs-lookup"><span data-stu-id="475e7-251">More info</span></span>](#tab/)
  
- <span data-ttu-id="475e7-p121">使用 Office 365 稽核記錄來搜尋信箱活動已登入。您可以搜尋特定的使用者信箱的活動。下列螢幕擷取畫面顯示您可以在 Office 365 稽核記錄檔中搜尋的信箱活動清單。請注意這些活動本主題的 「 信箱稽核動作 」 一節所述的相同動作。</span><span class="sxs-lookup"><span data-stu-id="475e7-p121">Use the Office 365 audit log to search for mailbox activity that have been logged. You can search for activity for a specific user mailbox. The following screenshot shows a list of mailbox activities that you can search for in the Office 365 audit log. Note that these activities are the same actions that are described in the "Mailbox auditing actions" section in this topic.</span></span>
    
    ![您可以搜尋信箱稽核動作的 Office 365 稽核記錄中的活動] 下拉式清單中選取 ["的 Exchange 信箱活動"](media/fadc34f8-9de2-4688-8b1a-bc5540e69a23.png)
  
    <span data-ttu-id="475e7-257">下表說明每個信箱活動您可以搜尋並顯示對應的信箱稽核巨集指令。</span><span class="sxs-lookup"><span data-stu-id="475e7-257">The following table describes each mailbox activity that you can search for and shows the corresponding mailbox auditing action.</span></span>
    
    |<span data-ttu-id="475e7-258">**在稽核記錄中的活動**</span><span class="sxs-lookup"><span data-stu-id="475e7-258">**Activity in the audit log**</span></span>|<span data-ttu-id="475e7-259">**信箱稽核巨集指令**</span><span class="sxs-lookup"><span data-stu-id="475e7-259">**Mailbox auditing action**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="475e7-260">建立的信箱項目</span><span class="sxs-lookup"><span data-stu-id="475e7-260">Created mailbox item</span></span>  <br/> |<span data-ttu-id="475e7-261">建立</span><span class="sxs-lookup"><span data-stu-id="475e7-261">Create</span></span>  <br/> |
    |<span data-ttu-id="475e7-262">複製到另一個資料夾的郵件</span><span class="sxs-lookup"><span data-stu-id="475e7-262">Copied messages to another folder</span></span>  <br/> |<span data-ttu-id="475e7-263">複製</span><span class="sxs-lookup"><span data-stu-id="475e7-263">Copy</span></span>  <br/> |
    |<span data-ttu-id="475e7-264">使用者登入信箱</span><span class="sxs-lookup"><span data-stu-id="475e7-264">User signed in to mailbox</span></span>  <br/> |<span data-ttu-id="475e7-265">MailboxLogin</span><span class="sxs-lookup"><span data-stu-id="475e7-265">MailboxLogin</span></span>  <br/> |
    |<span data-ttu-id="475e7-266">傳送郵件使用傳送代理者權限</span><span class="sxs-lookup"><span data-stu-id="475e7-266">Sent message using Send On Behalf permissions</span></span>  <br/> |<span data-ttu-id="475e7-267">SendOnBehalf</span><span class="sxs-lookup"><span data-stu-id="475e7-267">SendOnBehalf</span></span>  <br/> |
    |<span data-ttu-id="475e7-268">從信箱清除的郵件</span><span class="sxs-lookup"><span data-stu-id="475e7-268">Purged messages from the mailbox</span></span>  <br/> |<span data-ttu-id="475e7-269">HardDelete</span><span class="sxs-lookup"><span data-stu-id="475e7-269">HardDelete</span></span>  <br/> |
    |<span data-ttu-id="475e7-270">移至刪除的郵件] 資料夾的郵件</span><span class="sxs-lookup"><span data-stu-id="475e7-270">Moved messages to Deleted Items folder</span></span>  <br/> |<span data-ttu-id="475e7-271">MoveToDeletedItems</span><span class="sxs-lookup"><span data-stu-id="475e7-271">MoveToDeletedItems</span></span>  <br/> |
    |<span data-ttu-id="475e7-272">移至另一個資料夾的郵件</span><span class="sxs-lookup"><span data-stu-id="475e7-272">Moved messages to another folder</span></span>  <br/> |<span data-ttu-id="475e7-273">Move</span><span class="sxs-lookup"><span data-stu-id="475e7-273">Move</span></span>  <br/> |
    |<span data-ttu-id="475e7-274">傳送郵件使用下列傳送] 權限</span><span class="sxs-lookup"><span data-stu-id="475e7-274">Sent message using Send As permissions</span></span>  <br/> |<span data-ttu-id="475e7-275">SendAs</span><span class="sxs-lookup"><span data-stu-id="475e7-275">SendAs</span></span>  <br/> |
    |<span data-ttu-id="475e7-276">更新的郵件</span><span class="sxs-lookup"><span data-stu-id="475e7-276">Updated message</span></span>  <br/> |<span data-ttu-id="475e7-277">更新</span><span class="sxs-lookup"><span data-stu-id="475e7-277">Update</span></span>  <br/> |
    |<span data-ttu-id="475e7-278">從 [刪除的郵件] 資料夾刪除的郵件</span><span class="sxs-lookup"><span data-stu-id="475e7-278">Deleted messages from Deleted Items folder</span></span>  <br/> |<span data-ttu-id="475e7-279">SoftDelete</span><span class="sxs-lookup"><span data-stu-id="475e7-279">SoftDelete</span></span>  <br/> |
    |<span data-ttu-id="475e7-280">新增至資料夾的權限</span><span class="sxs-lookup"><span data-stu-id="475e7-280">Added permissions to folder</span></span>  <br/> |<span data-ttu-id="475e7-281">UpdateFolderPermissions</span><span class="sxs-lookup"><span data-stu-id="475e7-281">UpdateFolderPermissions</span></span>  <br/> |
    |<span data-ttu-id="475e7-282">已修改的權限的資料夾</span><span class="sxs-lookup"><span data-stu-id="475e7-282">Modified permissions of folder</span></span>  <br/> |<span data-ttu-id="475e7-283">UpdateFolderPermissions</span><span class="sxs-lookup"><span data-stu-id="475e7-283">UpdateFolderPermissions</span></span>  <br/> |
    |<span data-ttu-id="475e7-284">已移除從資料夾的權限</span><span class="sxs-lookup"><span data-stu-id="475e7-284">Removed permissions from folder</span></span>  <br/> |<span data-ttu-id="475e7-285">UpdateFolderPermissions</span><span class="sxs-lookup"><span data-stu-id="475e7-285">UpdateFolderPermissions</span></span>  <br/> |
    |<span data-ttu-id="475e7-286">新增或移除使用者行事曆] 資料夾的代理人存取權</span><span class="sxs-lookup"><span data-stu-id="475e7-286">Added or removed user with delegate access to calendar folder</span></span>  <br/> |<span data-ttu-id="475e7-287">UpdateCalendarDelegation</span><span class="sxs-lookup"><span data-stu-id="475e7-287">UpdateCalendarDelegation</span></span>  <br/> |
   
    <span data-ttu-id="475e7-p122">請注意上述的螢幕擷取畫面所示的**已新增委派信箱權限**與**已移除委派信箱權限**活動不相關信箱稽核的動作。這些指示是否以系統管理員指派或移除的 FullAccess 信箱權限。</span><span class="sxs-lookup"><span data-stu-id="475e7-p122">Note that the **Added delegate mailbox permissions** and **Removed delegate mailbox permissions** activities shown in the previous screenshot aren't related to mailbox auditing actions. They indicate whether an administrator assigned or removed the FullAccess mailbox permission.</span></span> 
    
    <span data-ttu-id="475e7-290">Office 365 稽核記錄的相關資訊，請參閱[Office 365 安全性搜尋稽核記錄&amp;規範中心](search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="475e7-290">For information about the Office 365 audit log, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
    
- <span data-ttu-id="475e7-291">在下列案例中，信箱會被視為只能由系統管理員存取：</span><span class="sxs-lookup"><span data-stu-id="475e7-291">Mailboxes are considered to be accessed by an administrator only in the following scenarios:</span></span>
    
  - <span data-ttu-id="475e7-292">在 Exchange Online 或 Office 365 中的內容搜尋中的就地 eDiscovery 來搜尋信箱。</span><span class="sxs-lookup"><span data-stu-id="475e7-292">In-Place eDiscovery in Exchange Online or Content Search in Office 365 is used to search a mailbox.</span></span>
    
  - <span data-ttu-id="475e7-293">[Microsoft Exchange Server MAPI Editor](https://go.microsoft.com/fwlink/p/?linkId=204086) 用來存取信箱。</span><span class="sxs-lookup"><span data-stu-id="475e7-293">[Microsoft Exchange Server MAPI Editor](https://go.microsoft.com/fwlink/p/?linkId=204086) is used to access the mailbox.</span></span> 
    
- <span data-ttu-id="475e7-294">啟用信箱的稽核記錄時，也可指定針對各個登入類型 (系統管理員、代理人或擁有者) 將記錄哪些使用者動作 (例如存取、移動或刪除郵件)。 </span><span class="sxs-lookup"><span data-stu-id="475e7-294">When you enable audit logging for a mailbox, you can also specify which user actions (for example, accessing, moving, or deleting a message) will be logged for each logon type (admin, delegate, or owner).</span></span>
    
- <span data-ttu-id="475e7-295">若要停用信箱稽核記錄，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="475e7-295">To disable mailbox audit logging, run the following command:</span></span>

  ```
  Set-Mailbox -Identity <identity of mailbox> -AuditEnabled $false
   ```

- <span data-ttu-id="475e7-p123">當您執行**Get-mailbox**指令程式時不顯示各類型的使用者稽核的動作。但是您可以執行下列命令以顯示特定使用者登入類型的所有稽核的動作。</span><span class="sxs-lookup"><span data-stu-id="475e7-p123">The actions that are audited for each type of user aren't displayed when you run the **Get-Mailbox** cmdlet. But you can run the following commands to display all the audited actions for a specific user logon type.</span></span> 

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditAdmin
    ```

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditDelegate
    ```

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditOwner
    ```

- <span data-ttu-id="475e7-p124">您也可以匯出信箱稽核記錄，並指定要包含的一或多個使用者的項目。報告和稽核記錄中的每個項目包含有關誰執行巨集指令與時所執行的動作，以及動作是否成功的資訊。如需詳細資訊，請參閱[匯出信箱稽核記錄](https://go.microsoft.com/fwlink/p/?LinkID=404104)。</span><span class="sxs-lookup"><span data-stu-id="475e7-p124">You can also export a mailbox audit log and specify the entries to include for one or more users. Each entry in the report and the audit log includes information about who performed the action and when, the action performed , and whether the action was successful. For more information, see [Export mailbox audit logs](https://go.microsoft.com/fwlink/p/?LinkID=404104).</span></span>
