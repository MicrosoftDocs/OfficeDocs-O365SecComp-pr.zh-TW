---
title: 啟用 Office 365中的信箱稽核
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: aaca8987-5b62-458b-9882-c28476a66918
description: 在 Office 365 中，您可以開啟信箱稽核記錄來依信箱擁有者、 委派及系統管理員記錄信箱存取。根據預設，Office 365 中的信箱稽核無法開啟。啟用信箱稽核記錄功能信箱之後，您可以搜尋活動在信箱上執行的 Office 365 稽核記錄。
ms.openlocfilehash: bb110e95d27feb8ae82b62803d218a2b38528692
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214603"
---
# <a name="enable-mailbox-auditing-in-office-365"></a><span data-ttu-id="e2a96-105">啟用 Office 365中的信箱稽核</span><span class="sxs-lookup"><span data-stu-id="e2a96-105">Enable mailbox auditing in Office 365</span></span>
  
<span data-ttu-id="e2a96-p102">在 Office 365 中，您可以開啟信箱稽核記錄來依信箱擁有者、 委派及系統管理員記錄信箱存取。根據預設，Office 365 中的信箱稽核無法開啟。這表示信箱稽核事件將不會出現在結果搜尋信箱活動的 Office 365 稽核記錄時。但是您開啟信箱稽核記錄功能的使用者信箱後，您可以搜尋信箱活動的稽核記錄。此外，當信箱稽核記錄已啟動，由系統管理員、 委派、 執行某些動作及預設會記錄擁有者。記錄 （及然後搜尋） 其他動作，請參閱步驟 3。</span><span class="sxs-lookup"><span data-stu-id="e2a96-p102">In Office 365, you can turn on mailbox audit logging to log mailbox access by mailbox owners, delegates, and administrators. By default, mailbox auditing in Office 365 isn't turned on. That means mailbox auditing events won't appear in the results when you search the Office 365 audit log for mailbox activity. But after you turn on mailbox audit logging for a user mailbox, you can search the audit log for mailbox activity. Additionally, when mailbox audit logging is turned on, some actions performed by administrators, delegates, and owners are logged by default. To log (and then search for) additional actions, see Step 3.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e2a96-112">開始之前</span><span class="sxs-lookup"><span data-stu-id="e2a96-112">Before you begin</span></span>
  
- <span data-ttu-id="e2a96-p103">您必須使用 Exchange Online PowerShell 來啟用信箱稽核記錄。您不能使用 Office 365 安全性&amp;規範中心 」 或 「 Exchange 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="e2a96-p103">You have to use Exchange Online PowerShell to enable mailbox audit logging. You can't use the Office 365 Security &amp; Compliance Center or the Exchange admin center.</span></span>
    
- <span data-ttu-id="e2a96-115">您無法啟用信箱稽核記錄與 Office 365 群組或小組中的 Microsoft 小組關聯的信箱。</span><span class="sxs-lookup"><span data-stu-id="e2a96-115">You can't enable mailbox audit logging for the mailbox that's associated with an Office 365 Group or a team in Microsoft Teams.</span></span>
    
- <span data-ttu-id="e2a96-116">獲指派使用者信箱「完整存取」權限的系統管理員會被視為委派使用者。</span><span class="sxs-lookup"><span data-stu-id="e2a96-116">An administrator who has been assigned the Full Access permission to a user's mailbox is considered a delegate user.</span></span>
  
## <a name="step-1-connect-to-exchange-online-powershell"></a><span data-ttu-id="e2a96-117">步驟 1： 連線至 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2a96-117">Step 1: Connect to Exchange Online PowerShell</span></span>

1. <span data-ttu-id="e2a96-118">在您的本機電腦上開啟 Windows PowerShell，並執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="e2a96-118">On your local computer, open Windows PowerShell and run the following command.</span></span>
   
    ```
    $UserCredential = Get-Credential
    ```

2. <span data-ttu-id="e2a96-119">在**Windows PowerShell 認證要求**] 對話方塊中，輸入使用者名稱與 Office 365 全域管理員帳戶密碼，並再按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="e2a96-119">In the **Windows PowerShell Credential Request** dialog box, type user name and password for an Office 365 global admin account, and then click **OK**.</span></span>
    
3. <span data-ttu-id="e2a96-120">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="e2a96-120">Run the following command:</span></span>
    
    ```
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    ```

3. <span data-ttu-id="e2a96-121">執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="e2a96-121">Run the following command.</span></span>

    ```
    Import-PSSession $Session
    ```
   
4. <span data-ttu-id="e2a96-122">若要確認您已連線至 Exchange Online 組織，執行下列命令以取得貴組織中所有信箱的清單：</span><span class="sxs-lookup"><span data-stu-id="e2a96-122">To verify that you're connected to your Exchange Online organization, run the following command to get a list of all the mailboxes in your organization.</span></span>
    
    ```
    Get-Mailbox
    ```
  
<span data-ttu-id="e2a96-123">如需詳細資訊或如果您無法連線到您的 Exchange Online 組織，請參閱[使用遠端 PowerShell 連線到 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=517283)。</span><span class="sxs-lookup"><span data-stu-id="e2a96-123">For more information or if you have problems connecting to your Exchange Online organization, see [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283).</span></span>
  
## <a name="step-2-enable-mailbox-audit-logging"></a><span data-ttu-id="e2a96-124">步驟 2：啟用信箱稽核記錄</span><span class="sxs-lookup"><span data-stu-id="e2a96-124">Step 2: Enable mailbox audit logging</span></span>

<span data-ttu-id="e2a96-p104">連線至 Exchange Online 組織之後，使用 PowerShell 針對信箱啟用信箱稽核記錄。或者，您可以啟用信箱稽核貴組織中的所有信箱。</span><span class="sxs-lookup"><span data-stu-id="e2a96-p104">After you connect to your Exchange Online organization, use PowerShell to enable mailbox audit logging for a mailbox. Alternatively, you can enable mailbox auditing for all mailboxes in your organization.</span></span>
  
<span data-ttu-id="e2a96-127">本範例啟用信箱稽核記錄 Pilar Pinilla 信箱。</span><span class="sxs-lookup"><span data-stu-id="e2a96-127">This example enables mailbox audit logging for Pilar Pinilla's mailbox.</span></span>
  
```
Set-Mailbox -Identity "Pilar Pinilla" -AuditEnabled $true
```

<span data-ttu-id="e2a96-128">此範例會啟用組織中所有使用者信箱的信箱稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="e2a96-128">This example enables mailbox audit logging for all user mailboxes in your organization.</span></span>
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -AuditEnabled $true
```
  
## <a name="step-3-specify-owner-actions-to-audit"></a><span data-ttu-id="e2a96-129">步驟 3：指定要稽核的擁有者動作</span><span class="sxs-lookup"><span data-stu-id="e2a96-129">Step 3: Specify owner actions to audit</span></span>

<span data-ttu-id="e2a96-p105">當您啟用信箱稽核時，預設稽核信箱擁有者執行某些動作。您必須指定稽核其他擁有者動作。請參閱在[信箱稽核動作](#mailbox-auditing-actions)] 區段中的清單和說明會記錄預設的擁有者動作及其他要稽核的動作的表格。</span><span class="sxs-lookup"><span data-stu-id="e2a96-p105">When you enable auditing for a mailbox, some actions performed by the mailbox owner are audited by default. You have to specify other owner actions to audit. See the table in the [Mailbox auditing actions](#mailbox-auditing-actions) section for a list and description of owner actions that are logged by default and the other actions that can be audited.</span></span> 
  
<span data-ttu-id="e2a96-p106">本範例會新增到信箱的 Pilar Pinilla 信箱稽核**MailboxLogin**和**HardDelete**擁有者動作。本範例會假設該信箱稽核已經啟用此信箱。</span><span class="sxs-lookup"><span data-stu-id="e2a96-p106">This example adds the **MailboxLogin** and **HardDelete** owner actions to mailbox auditing for Pilar Pinilla's mailbox. This example assumes that mailbox auditing has already been enabled for this mailbox.</span></span> 

```
Set-Mailbox "Pilar Pinilla" -AuditOwner @{Add="MailboxLogin","HardDelete"}
```

<span data-ttu-id="e2a96-p107">本範例個 Don 館信箱啟用信箱稽核記錄並指定僅信箱擁有者執行**MailboxLogin**動作都將被記錄。請注意此範例會覆寫預設 UpdateFolderPermissions 巨集指令。</span><span class="sxs-lookup"><span data-stu-id="e2a96-p107">This example enables mailbox audit logging for Don Hall's mailbox and specifies that only the **MailboxLogin** action performed by the mailbox owner will be logged. Note that this example overwrites the default UpdateFolderPermissions action.</span></span> 
  
```
Set-Mailbox "Don Hall" -AuditEnabled $true -AuditOwner MailboxLogin
```
   
<span data-ttu-id="e2a96-p108">本範例會將**MailboxLogin**、 **HardDelete**和**SoftDelete**擁有者動作新增至組織中的所有信箱。本範例會假設該信箱稽核已經啟用的所有信箱。</span><span class="sxs-lookup"><span data-stu-id="e2a96-p108">This example adds the **MailboxLogin**, **HardDelete**, and **SoftDelete** owner actions to all mailboxes in the organization. This example assumes that mailbox auditing has already been enabled for all mailboxes.</span></span> 
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -AuditOwner @{Add="MailboxLogin","HardDelete","SoftDelete"}
```
  
## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="e2a96-139">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="e2a96-139">How do you know this worked?</span></span>

<span data-ttu-id="e2a96-140">若要確認您已成功啟用信箱的信箱稽核記錄，請使用 **Get-Mailbox** Cmdlet 來擷取該信箱的稽核設定。</span><span class="sxs-lookup"><span data-stu-id="e2a96-140">To verify that you have successfully enabled mailbox audit logging for a mailbox, use the **Get-Mailbox** cmdlet to retrieve the auditing settings for that mailbox.</span></span> 
  
<span data-ttu-id="e2a96-141">此範例會擷取 Pilar Pinilla 的稽核設定。</span><span class="sxs-lookup"><span data-stu-id="e2a96-141">This example retrieves the auditing settings for Pilar Pinilla.</span></span>

```
Get-Mailbox "Pilar Pinilla"| FL Audit*
```
   
<span data-ttu-id="e2a96-142">此範例會擷取您組織中所有使用者信箱的稽核設定。</span><span class="sxs-lookup"><span data-stu-id="e2a96-142">This example retrieves the auditing settings for all user mailboxes in your organization.</span></span>

```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | FL Name,Audit*
```
   
<span data-ttu-id="e2a96-143">提供驗證**AuditEnabled**屬性信箱的**則為 True**值該信箱稽核記錄已啟用。</span><span class="sxs-lookup"><span data-stu-id="e2a96-143">A value of **True** for the **AuditEnabled** property verifies that mailbox audit logging is enabled.</span></span> 
    
## <a name="mailbox-auditing-actions"></a><span data-ttu-id="e2a96-144">信箱稽核的動作</span><span class="sxs-lookup"><span data-stu-id="e2a96-144">Mailbox auditing actions</span></span>
  
<span data-ttu-id="e2a96-p109">下表列出可以信箱所記錄的動作稽核記錄。表格包含可針對不同的使用者登入類型記錄的動作。在表格中，**無**表示巨集指令不會記錄以登入類型。星號 ( **\*** ) 會指出動作會記錄預設時信箱稽核記錄已啟用信箱。</span><span class="sxs-lookup"><span data-stu-id="e2a96-p109">The following table lists the actions that can be logged by mailbox audit logging. The table includes which action can be logged for the different user logon types. In the table, a **No** indicates that an action can't be logged for that logon type. An asterisk ( **\*** ) indicates that the action is logged by default when mailbox audit logging is enabled for the mailbox.</span></span> 
  
|<span data-ttu-id="e2a96-149">**動作**</span><span class="sxs-lookup"><span data-stu-id="e2a96-149">**Action**</span></span>|<span data-ttu-id="e2a96-150">**描述**</span><span class="sxs-lookup"><span data-stu-id="e2a96-150">**Description**</span></span>|<span data-ttu-id="e2a96-151">**Admin**</span><span class="sxs-lookup"><span data-stu-id="e2a96-151">**Admin**</span></span>|<span data-ttu-id="e2a96-152">**委派\*\*\***</span><span class="sxs-lookup"><span data-stu-id="e2a96-152">**Delegate\*\*\***</span></span>|<span data-ttu-id="e2a96-153">**擁有者**</span><span class="sxs-lookup"><span data-stu-id="e2a96-153">**Owner**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e2a96-154">**Copy**</span><span class="sxs-lookup"><span data-stu-id="e2a96-154">**Copy**</span></span> <br/> |<span data-ttu-id="e2a96-155">郵件已複製到另一個資料夾。</span><span class="sxs-lookup"><span data-stu-id="e2a96-155">A message was copied to another folder.</span></span>  <br/> |<span data-ttu-id="e2a96-156">是</span><span class="sxs-lookup"><span data-stu-id="e2a96-156">Yes</span></span>  <br/> |<span data-ttu-id="e2a96-157">否 </span><span class="sxs-lookup"><span data-stu-id="e2a96-157">No</span></span>  <br/> |<span data-ttu-id="e2a96-158">否</span><span class="sxs-lookup"><span data-stu-id="e2a96-158">No</span></span>  <br/> |
|<span data-ttu-id="e2a96-159">**Create**</span><span class="sxs-lookup"><span data-stu-id="e2a96-159">**Create**</span></span> <br/> |<span data-ttu-id="e2a96-p110">在信箱 ； 中的 [行事曆、 連絡人、 備忘稿或工作] 資料夾中建立項目例如，會建立新的會議邀請。請注意不稽核建立、 傳送或接收郵件。此外，不稽核建立信箱資料夾。</span><span class="sxs-lookup"><span data-stu-id="e2a96-p110">An item is created in the Calendar, Contacts, Notes, or Tasks folder in the mailbox; for example, a new meeting request is created. Note that creating, sending, or receiving a message isn't audited. Also, creating a mailbox folder is not audited.</span></span>  <br/> |<span data-ttu-id="e2a96-163">是\*</span><span class="sxs-lookup"><span data-stu-id="e2a96-163">Yes\*</span></span>  <br/> |<span data-ttu-id="e2a96-164">是\*</span><span class="sxs-lookup"><span data-stu-id="e2a96-164">Yes\*</span></span>  <br/> |<span data-ttu-id="e2a96-165">是</span><span class="sxs-lookup"><span data-stu-id="e2a96-165">Yes</span></span>  <br/> |
|<span data-ttu-id="e2a96-166">**FolderBind**</span><span class="sxs-lookup"><span data-stu-id="e2a96-166">**FolderBind**</span></span> <br/> |<span data-ttu-id="e2a96-p111">已存取信箱資料夾。系統管理員或代理人開啟信箱時也會記錄此動作。</span><span class="sxs-lookup"><span data-stu-id="e2a96-p111">A mailbox folder was accessed. This action is also logged when the admin or delegate opens the mailbox.</span></span>  <br/> |<span data-ttu-id="e2a96-169">是</span><span class="sxs-lookup"><span data-stu-id="e2a96-169">Yes</span></span>  <br/> |<span data-ttu-id="e2a96-170">[是]\*\*</span><span class="sxs-lookup"><span data-stu-id="e2a96-170">Yes\*\*</span></span>  <br/> |<span data-ttu-id="e2a96-171">否</span><span class="sxs-lookup"><span data-stu-id="e2a96-171">No</span></span>  <br/> |
|<span data-ttu-id="e2a96-172">**HardDelete**</span><span class="sxs-lookup"><span data-stu-id="e2a96-172">**HardDelete**</span></span> <br/> |<span data-ttu-id="e2a96-173">郵件已經從 [可復原的項目] 資料夾清除。</span><span class="sxs-lookup"><span data-stu-id="e2a96-173">A message was purged from the Recoverable Items folder.</span></span>  <br/> |<span data-ttu-id="e2a96-174">是\*</span><span class="sxs-lookup"><span data-stu-id="e2a96-174">Yes\*</span></span>  <br/> |<span data-ttu-id="e2a96-175">是\*</span><span class="sxs-lookup"><span data-stu-id="e2a96-175">Yes\*</span></span>  <br/> |<span data-ttu-id="e2a96-176">是</span><span class="sxs-lookup"><span data-stu-id="e2a96-176">Yes</span></span>  <br/> |
|<span data-ttu-id="e2a96-177">**MailboxLogin**</span><span class="sxs-lookup"><span data-stu-id="e2a96-177">**MailboxLogin**</span></span> <br/> |<span data-ttu-id="e2a96-178">使用者已登入其信箱。</span><span class="sxs-lookup"><span data-stu-id="e2a96-178">The user signed in to their mailbox.</span></span>  <br/> |<span data-ttu-id="e2a96-179">否</span><span class="sxs-lookup"><span data-stu-id="e2a96-179">No</span></span>  <br/> |<span data-ttu-id="e2a96-180">否</span><span class="sxs-lookup"><span data-stu-id="e2a96-180">No</span></span>  <br/> |<span data-ttu-id="e2a96-181">是</span><span class="sxs-lookup"><span data-stu-id="e2a96-181">Yes</span></span>  <br/> |
|<span data-ttu-id="e2a96-182">**MessageBind**</span><span class="sxs-lookup"><span data-stu-id="e2a96-182">**MessageBind**</span></span> <br/> |<span data-ttu-id="e2a96-183">在預覽窗格中檢視郵件或將它開啟。</span><span class="sxs-lookup"><span data-stu-id="e2a96-183">A message was viewed in the preview pane or opened.</span></span>  <br/> |<span data-ttu-id="e2a96-184">是</span><span class="sxs-lookup"><span data-stu-id="e2a96-184">Yes</span></span>  <br/> |<span data-ttu-id="e2a96-185">否 </span><span class="sxs-lookup"><span data-stu-id="e2a96-185">No</span></span>  <br/> |<span data-ttu-id="e2a96-186">否</span><span class="sxs-lookup"><span data-stu-id="e2a96-186">No</span></span>  <br/> |
|<span data-ttu-id="e2a96-187">**Move**</span><span class="sxs-lookup"><span data-stu-id="e2a96-187">**Move**</span></span> <br/> |<span data-ttu-id="e2a96-188">郵件已移到另一個資料夾。</span><span class="sxs-lookup"><span data-stu-id="e2a96-188">A message was moved to another folder.</span></span>  <br/> |<span data-ttu-id="e2a96-189">是</span><span class="sxs-lookup"><span data-stu-id="e2a96-189">Yes</span></span>  <br/> |<span data-ttu-id="e2a96-190">是 </span><span class="sxs-lookup"><span data-stu-id="e2a96-190">Yes</span></span>  <br/> |<span data-ttu-id="e2a96-191">可以</span><span class="sxs-lookup"><span data-stu-id="e2a96-191">Yes</span></span>  <br/> |
|<span data-ttu-id="e2a96-192">**MoveToDeletedItems**</span><span class="sxs-lookup"><span data-stu-id="e2a96-192">**MoveToDeletedItems**</span></span> <br/> |<span data-ttu-id="e2a96-193">郵件已遭刪除並移至 [刪除的郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="e2a96-193">A message was deleted and moved to the Deleted Items folder.</span></span>  <br/> |<span data-ttu-id="e2a96-194">是\*</span><span class="sxs-lookup"><span data-stu-id="e2a96-194">Yes\*</span></span>  <br/> |<span data-ttu-id="e2a96-195">是\*</span><span class="sxs-lookup"><span data-stu-id="e2a96-195">Yes\*</span></span>  <br/> |<span data-ttu-id="e2a96-196">是</span><span class="sxs-lookup"><span data-stu-id="e2a96-196">Yes</span></span>  <br/> |
|<span data-ttu-id="e2a96-197">**SendAs**</span><span class="sxs-lookup"><span data-stu-id="e2a96-197">**SendAs**</span></span> <br/> |<span data-ttu-id="e2a96-p112">已使用 SendAs 權限傳送郵件。這表示，另一個使用者已傳送郵件，就像此郵件是來自信箱擁有者一樣。</span><span class="sxs-lookup"><span data-stu-id="e2a96-p112">A message was sent using the SendAs permission. This means another user sent the message as though it came from the mailbox owner.</span></span>  <br/> |<span data-ttu-id="e2a96-200">是\*</span><span class="sxs-lookup"><span data-stu-id="e2a96-200">Yes\*</span></span>  <br/> |<span data-ttu-id="e2a96-201">是\*</span><span class="sxs-lookup"><span data-stu-id="e2a96-201">Yes\*</span></span>  <br/> |<span data-ttu-id="e2a96-202">否</span><span class="sxs-lookup"><span data-stu-id="e2a96-202">No</span></span>  <br/> |
|<span data-ttu-id="e2a96-203">**SendOnBehalf**</span><span class="sxs-lookup"><span data-stu-id="e2a96-203">**SendOnBehalf**</span></span> <br/> |<span data-ttu-id="e2a96-p113">已使用 SendOnBehalf 權限傳送郵件。這表示，另一個使用者已代表信箱擁有者傳送郵件。此郵件會向收件者指示，此郵件是代表誰傳送，以及實際傳送郵件的人是誰。</span><span class="sxs-lookup"><span data-stu-id="e2a96-p113">A message was sent using the SendOnBehalf permission. This means another user sent the message on behalf of the mailbox owner. The message indicates to the recipient who the message was sent on behalf of and who actually sent the message.</span></span>  <br/> |<span data-ttu-id="e2a96-207">是\*</span><span class="sxs-lookup"><span data-stu-id="e2a96-207">Yes\*</span></span>  <br/> |<span data-ttu-id="e2a96-208">是\*</span><span class="sxs-lookup"><span data-stu-id="e2a96-208">Yes\*</span></span>  <br/> |<span data-ttu-id="e2a96-209">否</span><span class="sxs-lookup"><span data-stu-id="e2a96-209">No</span></span>  <br/> |
|<span data-ttu-id="e2a96-210">**SoftDelete**</span><span class="sxs-lookup"><span data-stu-id="e2a96-210">**SoftDelete**</span></span> <br/> |<span data-ttu-id="e2a96-p114">郵件已永久刪除或從 [刪除的郵件] 資料夾刪除。虛刪除的項目會移至 [可復原的項目] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="e2a96-p114">A message was permanently deleted or deleted from the Deleted Items folder. Soft-deleted items are moved to the Recoverable Items folder.</span></span>  <br/> |<span data-ttu-id="e2a96-213">是\*</span><span class="sxs-lookup"><span data-stu-id="e2a96-213">Yes\*</span></span>  <br/> |<span data-ttu-id="e2a96-214">是\*</span><span class="sxs-lookup"><span data-stu-id="e2a96-214">Yes\*</span></span>  <br/> |<span data-ttu-id="e2a96-215">是</span><span class="sxs-lookup"><span data-stu-id="e2a96-215">Yes</span></span>  <br/> |
|<span data-ttu-id="e2a96-216">**更新**</span><span class="sxs-lookup"><span data-stu-id="e2a96-216">**Update**</span></span> <br/> |<span data-ttu-id="e2a96-217">郵件或其屬性已變更。</span><span class="sxs-lookup"><span data-stu-id="e2a96-217">A message or its properties was changed.</span></span>  <br/> |<span data-ttu-id="e2a96-218">是\*</span><span class="sxs-lookup"><span data-stu-id="e2a96-218">Yes\*</span></span>  <br/> |<span data-ttu-id="e2a96-219">是\*</span><span class="sxs-lookup"><span data-stu-id="e2a96-219">Yes\*</span></span>  <br/> |<span data-ttu-id="e2a96-220">是</span><span class="sxs-lookup"><span data-stu-id="e2a96-220">Yes</span></span>  <br/> |
|<span data-ttu-id="e2a96-221">**UpdateCalendarDelegation**</span><span class="sxs-lookup"><span data-stu-id="e2a96-221">**UpdateCalendarDelegation**</span></span> <br/> |<span data-ttu-id="e2a96-p115">行事曆委派已指派給信箱。行事曆委派可讓其他人在相同的組織權限管理信箱擁有者的行事曆。</span><span class="sxs-lookup"><span data-stu-id="e2a96-p115">A calendar delegation was assigned to a mailbox. Calendar delegation gives someone else in the same organization permissions to manage the mailbox owner's calendar.</span></span>  <br/> |<span data-ttu-id="e2a96-224">是\*</span><span class="sxs-lookup"><span data-stu-id="e2a96-224">Yes\*</span></span>  <br/> |<span data-ttu-id="e2a96-225">否</span><span class="sxs-lookup"><span data-stu-id="e2a96-225">No</span></span>  <br/> |<span data-ttu-id="e2a96-226">是\*</span><span class="sxs-lookup"><span data-stu-id="e2a96-226">Yes\*</span></span>  <br/> |
|<span data-ttu-id="e2a96-227">**UpdateFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="e2a96-227">**UpdateFolderPermissions**</span></span> <br/> |<span data-ttu-id="e2a96-p116">已變更的資料夾權限。資料夾的權限控制您組織中的使用者可以存取信箱和那些資料夾中的郵件中的資料夾。</span><span class="sxs-lookup"><span data-stu-id="e2a96-p116">A folder permission was changed. Folder permissions control which users in your organization can access folders in a mailbox and the messages located in those folders.</span></span>  <br/> |<span data-ttu-id="e2a96-230">是\*</span><span class="sxs-lookup"><span data-stu-id="e2a96-230">Yes\*</span></span>  <br/> |<span data-ttu-id="e2a96-231">是\*</span><span class="sxs-lookup"><span data-stu-id="e2a96-231">Yes\*</span></span>  <br/> |<span data-ttu-id="e2a96-232">是\*</span><span class="sxs-lookup"><span data-stu-id="e2a96-232">Yes\*</span></span>  <br/> |
|<span data-ttu-id="e2a96-233">**UpdateInboxRules**</span><span class="sxs-lookup"><span data-stu-id="e2a96-233">**UpdateInboxRules**</span></span> <br/> |<span data-ttu-id="e2a96-p117">收件匣規則已新增、 移除或變更。收件匣規則可用來處理郵件的收件匣根據指定的條件和符合規則的條件，例如將郵件移至指定的資料夾或刪除郵件時採取的動作。</span><span class="sxs-lookup"><span data-stu-id="e2a96-p117">An inbox rule has been added, removed, or changed. Inbox rules are used to process messages in the user's Inbox based on the specified conditions and take actions when the conditions of a rule are met, such as moving a message to a specified folder or deleting a message.</span></span>  <br/> |<span data-ttu-id="e2a96-236">是\*</span><span class="sxs-lookup"><span data-stu-id="e2a96-236">Yes\*</span></span>  <br/> |<span data-ttu-id="e2a96-237">是\*</span><span class="sxs-lookup"><span data-stu-id="e2a96-237">Yes\*</span></span>  <br/> |<span data-ttu-id="e2a96-238">是\*</span><span class="sxs-lookup"><span data-stu-id="e2a96-238">Yes\*</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="e2a96-239"><sup>\*</sup>如果已啟用信箱，稽核預設。</span><span class="sxs-lookup"><span data-stu-id="e2a96-239"><sup>\*</sup> Audited by default if auditing is enabled for a mailbox.</span></span><br/><br/>  <span data-ttu-id="e2a96-p118"><sup>\*\*</sup>合併資料夾繫結動作委派所執行的項目。24 小時的時間範圍內的個別資料夾存取產生一個日誌項目。</span><span class="sxs-lookup"><span data-stu-id="e2a96-p118"><sup>\*\*</sup> Entries for folder bind actions performed by delegates are consolidated. One log entry is generated for individual folder access within a time span of 24 hours.</span></span><br/><br/><span data-ttu-id="e2a96-242"><sup>\*\*\*</sup>已指派完整存取權給使用者的信箱的系統管理員會被視為委派使用者。</span><span class="sxs-lookup"><span data-stu-id="e2a96-242"><sup>\*\*\*</sup> An administrator who has been assigned the Full Access permission to a user's mailbox is considered a delegate user.</span></span> 
  
<span data-ttu-id="e2a96-p119">如果您不再需要特定類型的信箱稽核的動作，您應修改停用這些動作的信箱稽核記錄設定。直到達到稽核記錄項目保留時間限制未清除現有的記錄項目。如需稽核記錄項目保留期間的詳細資訊，請參閱 ＜[的搜尋稽核登入 Office 365 安全性 & 規範中心](search-the-audit-log-in-security-and-compliance.md#before-you-begin)的 「 之前 」 一節。</span><span class="sxs-lookup"><span data-stu-id="e2a96-p119">If you no longer require certain types of mailbox actions to be audited, you should modify the mailbox's audit logging configuration to disable those actions. Existing log entries aren't purged until the retention age limit for audit log entries is reached. For more information about the retention age for audit log entries, see the "Before you begin" section in [Search the audit log in the Office 365 Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#before-you-begin).</span></span>
  
## <a name="more-infotab"></a>[<span data-ttu-id="e2a96-246">其他資訊</span><span class="sxs-lookup"><span data-stu-id="e2a96-246">More info</span></span>](#tab/)
  
- <span data-ttu-id="e2a96-p120">使用 Office 365 稽核記錄來搜尋信箱活動已登入。您可以搜尋特定的使用者信箱的活動。下列螢幕擷取畫面顯示您可以在 Office 365 稽核記錄檔中搜尋的信箱活動清單。請注意這些活動本主題的 「 信箱稽核動作 」 一節所述的相同動作。</span><span class="sxs-lookup"><span data-stu-id="e2a96-p120">Use the Office 365 audit log to search for mailbox activity that have been logged. You can search for activity for a specific user mailbox. The following screenshot shows a list of mailbox activities that you can search for in the Office 365 audit log. Note that these activities are the same actions that are described in the "Mailbox auditing actions" section in this topic.</span></span>
    
    ![您可以搜尋信箱稽核動作的 Office 365 稽核記錄中的活動] 下拉式清單中選取 ["的 Exchange 信箱活動"](media/fadc34f8-9de2-4688-8b1a-bc5540e69a23.png)
  
    <span data-ttu-id="e2a96-252">下表說明每個信箱活動您可以搜尋並顯示對應的信箱稽核巨集指令。</span><span class="sxs-lookup"><span data-stu-id="e2a96-252">The following table describes each mailbox activity that you can search for and shows the corresponding mailbox auditing action.</span></span>
    
    |<span data-ttu-id="e2a96-253">**在稽核記錄中的活動**</span><span class="sxs-lookup"><span data-stu-id="e2a96-253">**Activity in the audit log**</span></span>|<span data-ttu-id="e2a96-254">**信箱稽核巨集指令**</span><span class="sxs-lookup"><span data-stu-id="e2a96-254">**Mailbox auditing action**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="e2a96-255">建立的信箱項目</span><span class="sxs-lookup"><span data-stu-id="e2a96-255">Created mailbox item</span></span>  <br/> |<span data-ttu-id="e2a96-256">建立</span><span class="sxs-lookup"><span data-stu-id="e2a96-256">Create</span></span>  <br/> |
    |<span data-ttu-id="e2a96-257">複製到另一個資料夾的郵件</span><span class="sxs-lookup"><span data-stu-id="e2a96-257">Copied messages to another folder</span></span>  <br/> |<span data-ttu-id="e2a96-258">複製</span><span class="sxs-lookup"><span data-stu-id="e2a96-258">Copy</span></span>  <br/> |
    |<span data-ttu-id="e2a96-259">使用者登入信箱</span><span class="sxs-lookup"><span data-stu-id="e2a96-259">User signed in to mailbox</span></span>  <br/> |<span data-ttu-id="e2a96-260">MailboxLogin</span><span class="sxs-lookup"><span data-stu-id="e2a96-260">MailboxLogin</span></span>  <br/> |
    |<span data-ttu-id="e2a96-261">傳送郵件使用傳送代理者權限</span><span class="sxs-lookup"><span data-stu-id="e2a96-261">Sent message using Send On Behalf permissions</span></span>  <br/> |<span data-ttu-id="e2a96-262">SendOnBehalf</span><span class="sxs-lookup"><span data-stu-id="e2a96-262">SendOnBehalf</span></span>  <br/> |
    |<span data-ttu-id="e2a96-263">從信箱清除的郵件</span><span class="sxs-lookup"><span data-stu-id="e2a96-263">Purged messages from the mailbox</span></span>  <br/> |<span data-ttu-id="e2a96-264">HardDelete</span><span class="sxs-lookup"><span data-stu-id="e2a96-264">HardDelete</span></span>  <br/> |
    |<span data-ttu-id="e2a96-265">移至刪除的郵件] 資料夾的郵件</span><span class="sxs-lookup"><span data-stu-id="e2a96-265">Moved messages to Deleted Items folder</span></span>  <br/> |<span data-ttu-id="e2a96-266">MoveToDeletedItems</span><span class="sxs-lookup"><span data-stu-id="e2a96-266">MoveToDeletedItems</span></span>  <br/> |
    |<span data-ttu-id="e2a96-267">移至另一個資料夾的郵件</span><span class="sxs-lookup"><span data-stu-id="e2a96-267">Moved messages to another folder</span></span>  <br/> |<span data-ttu-id="e2a96-268">Move</span><span class="sxs-lookup"><span data-stu-id="e2a96-268">Move</span></span>  <br/> |
    |<span data-ttu-id="e2a96-269">傳送郵件使用下列傳送] 權限</span><span class="sxs-lookup"><span data-stu-id="e2a96-269">Sent message using Send As permissions</span></span>  <br/> |<span data-ttu-id="e2a96-270">SendAs</span><span class="sxs-lookup"><span data-stu-id="e2a96-270">SendAs</span></span>  <br/> |
    |<span data-ttu-id="e2a96-271">更新的郵件</span><span class="sxs-lookup"><span data-stu-id="e2a96-271">Updated message</span></span>  <br/> |<span data-ttu-id="e2a96-272">更新</span><span class="sxs-lookup"><span data-stu-id="e2a96-272">Update</span></span>  <br/> |
    |<span data-ttu-id="e2a96-273">從 [刪除的郵件] 資料夾刪除的郵件</span><span class="sxs-lookup"><span data-stu-id="e2a96-273">Deleted messages from Deleted Items folder</span></span>  <br/> |<span data-ttu-id="e2a96-274">SoftDelete</span><span class="sxs-lookup"><span data-stu-id="e2a96-274">SoftDelete</span></span>  <br/> |
    |<span data-ttu-id="e2a96-275">新增至資料夾的權限</span><span class="sxs-lookup"><span data-stu-id="e2a96-275">Added permissions to folder</span></span>  <br/> |<span data-ttu-id="e2a96-276">UpdateFolderPermissions</span><span class="sxs-lookup"><span data-stu-id="e2a96-276">UpdateFolderPermissions</span></span>  <br/> |
    |<span data-ttu-id="e2a96-277">已修改的權限的資料夾</span><span class="sxs-lookup"><span data-stu-id="e2a96-277">Modified permissions of folder</span></span>  <br/> |<span data-ttu-id="e2a96-278">UpdateFolderPermissions</span><span class="sxs-lookup"><span data-stu-id="e2a96-278">UpdateFolderPermissions</span></span>  <br/> |
    |<span data-ttu-id="e2a96-279">已移除從資料夾的權限</span><span class="sxs-lookup"><span data-stu-id="e2a96-279">Removed permissions from folder</span></span>  <br/> |<span data-ttu-id="e2a96-280">UpdateFolderPermissions</span><span class="sxs-lookup"><span data-stu-id="e2a96-280">UpdateFolderPermissions</span></span>  <br/> |
    |<span data-ttu-id="e2a96-281">新增或移除使用者行事曆] 資料夾的代理人存取權</span><span class="sxs-lookup"><span data-stu-id="e2a96-281">Added or removed user with delegate access to calendar folder</span></span>  <br/> |<span data-ttu-id="e2a96-282">UpdateCalendarDelegation</span><span class="sxs-lookup"><span data-stu-id="e2a96-282">UpdateCalendarDelegation</span></span>  <br/> |
   
    <span data-ttu-id="e2a96-p121">請注意上述的螢幕擷取畫面所示的**已新增委派信箱權限**與**已移除委派信箱權限**活動不相關信箱稽核的動作。這些指示是否以系統管理員指派或移除的 FullAccess 信箱權限。</span><span class="sxs-lookup"><span data-stu-id="e2a96-p121">Note that the **Added delegate mailbox permissions** and **Removed delegate mailbox permissions** activities shown in the previous screenshot aren't related to mailbox auditing actions. They indicate whether an administrator assigned or removed the FullAccess mailbox permission.</span></span> 
    
    <span data-ttu-id="e2a96-285">Office 365 稽核記錄的相關資訊，請參閱[Office 365 安全性搜尋稽核記錄&amp;規範中心](search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="e2a96-285">For information about the Office 365 audit log, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
    
- <span data-ttu-id="e2a96-286">在下列案例中，信箱會被視為只能由系統管理員存取：</span><span class="sxs-lookup"><span data-stu-id="e2a96-286">Mailboxes are considered to be accessed by an administrator only in the following scenarios:</span></span>
    
  - <span data-ttu-id="e2a96-287">在 Exchange Online 或 Office 365 中的內容搜尋中的就地 eDiscovery 來搜尋信箱。</span><span class="sxs-lookup"><span data-stu-id="e2a96-287">In-Place eDiscovery in Exchange Online or Content Search in Office 365 is used to search a mailbox.</span></span>
    
  - <span data-ttu-id="e2a96-288">[Microsoft Exchange Server MAPI Editor](https://go.microsoft.com/fwlink/p/?linkId=204086) 用來存取信箱。</span><span class="sxs-lookup"><span data-stu-id="e2a96-288">[Microsoft Exchange Server MAPI Editor](https://go.microsoft.com/fwlink/p/?linkId=204086) is used to access the mailbox.</span></span> 
    
- <span data-ttu-id="e2a96-289">啟用信箱的稽核記錄時，也可指定針對各個登入類型 (系統管理員、代理人或擁有者) 將記錄哪些使用者動作 (例如存取、移動或刪除郵件)。 </span><span class="sxs-lookup"><span data-stu-id="e2a96-289">When you enable audit logging for a mailbox, you can also specify which user actions (for example, accessing, moving, or deleting a message) will be logged for each logon type (admin, delegate, or owner).</span></span>
    
- <span data-ttu-id="e2a96-290">若要停用信箱稽核記錄，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="e2a96-290">To disable mailbox audit logging, run the following command:</span></span>

  ```
  Set-Mailbox -Identity <identity of mailbox> -AuditEnabled $false
   ```

- <span data-ttu-id="e2a96-p122">當您執行**Get-mailbox**指令程式時不顯示各類型的使用者稽核的動作。但是您可以執行下列命令以顯示特定使用者登入類型的所有稽核的動作。</span><span class="sxs-lookup"><span data-stu-id="e2a96-p122">The actions that are audited for each type of user aren't displayed when you run the **Get-Mailbox** cmdlet. But you can run the following commands to display all the audited actions for a specific user logon type.</span></span> 

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditAdmin
    ```

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditDelegate
    ```

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditOwner
    ```

- <span data-ttu-id="e2a96-p123">您也可以匯出信箱稽核記錄，並指定要包含的一或多個使用者的項目。報告和稽核記錄中的每個項目包含有關誰執行巨集指令與時所執行的動作，以及動作是否成功的資訊。如需詳細資訊，請參閱[匯出信箱稽核記錄](https://go.microsoft.com/fwlink/p/?LinkID=404104)。</span><span class="sxs-lookup"><span data-stu-id="e2a96-p123">You can also export a mailbox audit log and specify the entries to include for one or more users. Each entry in the report and the audit log includes information about who performed the action and when, the action performed , and whether the action was successful. For more information, see [Export mailbox audit logs](https://go.microsoft.com/fwlink/p/?LinkID=404104).</span></span>
