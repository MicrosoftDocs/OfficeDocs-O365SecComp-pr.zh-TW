---
title: 管理信箱稽核
ms.author: chrisda
author: chrisda
manager: serdars
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: aaca8987-5b62-458b-9882-c28476a66918
description: 預設會在 Microsoft 365 (也稱為預設信箱審核或信箱審核) 上開啟信箱審核記錄。 這表示信箱擁有者、代理人和系統管理員所執行的特定動作會自動記錄在信箱審核記錄檔中, 您可以在此搜尋信箱上執行的活動。
ms.openlocfilehash: f100fa1eb8244aeaea463440025ee489ec019406
ms.sourcegitcommit: ef2657e4221296be7032191f2d91e8ff727523c6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/21/2019
ms.locfileid: "35117688"
---
# <a name="manage-mailbox-auditing"></a><span data-ttu-id="86621-104">管理信箱稽核</span><span class="sxs-lookup"><span data-stu-id="86621-104">Manage mailbox auditing</span></span>

<span data-ttu-id="86621-105">從2019年1月開始, Microsoft 目前針對所有 Microsoft 365 組織開啟信箱審核記錄功能。</span><span class="sxs-lookup"><span data-stu-id="86621-105">Starting in January 2019, Microsoft is turning on mailbox audit logging by default for all Microsoft 365 organizations.</span></span> <span data-ttu-id="86621-106">這表示信箱擁有者、代理人和系統管理員所執行的特定動作會自動記錄, 當您在信箱審核記錄檔中進行搜尋時, 會有對應的信箱 audit 記錄可供使用。</span><span class="sxs-lookup"><span data-stu-id="86621-106">This means that certain actions performed by mailbox owners, delegates, and admins are automatically logged, and the corresponding mailbox audit records will be available when you search for them in the mailbox audit log.</span></span> <span data-ttu-id="86621-107">在信箱審核預設為開啟之前, 您必須針對組織中的每個使用者信箱手動啟用它。</span><span class="sxs-lookup"><span data-stu-id="86621-107">Before mailbox auditing was turned on by default, you had to manually enable it for every user mailbox in your organization.</span></span>

<span data-ttu-id="86621-108">以下是信箱審核預設的一些優點:</span><span class="sxs-lookup"><span data-stu-id="86621-108">Here are some benefits of mailbox auditing on by default:</span></span>

- <span data-ttu-id="86621-109">當您建立新的信箱時, 系統會自動啟用審核。</span><span class="sxs-lookup"><span data-stu-id="86621-109">Auditing is automatically enabled when you create a new mailbox.</span></span> <span data-ttu-id="86621-110">您不需要為新使用者手動啟用它。</span><span class="sxs-lookup"><span data-stu-id="86621-110">You don't need to manually enable it for new users.</span></span>

- <span data-ttu-id="86621-111">您不需要管理已審核的信箱動作。</span><span class="sxs-lookup"><span data-stu-id="86621-111">You don't need to manage the mailbox actions that are audited.</span></span> <span data-ttu-id="86621-112">每個登入類型 (系統管理員、代理人和擁有者) 預設會審核一組預先定義的信箱動作。</span><span class="sxs-lookup"><span data-stu-id="86621-112">A predefined set of mailbox actions are audited by default for each logon type (Admin, Delegate, and Owner).</span></span>

- <span data-ttu-id="86621-113">當 Microsoft 發行新的信箱動作時 (特別有助於保護您的組織並協助您進行鑒證調查的動作), 會自動將該動作新增至依預設進行審核的信箱動作清單中。</span><span class="sxs-lookup"><span data-stu-id="86621-113">When Microsoft releases a new mailbox action (particularly actions that help protect your organization and help with forensic investigations), the action is automatically added to the list of mailbox actions that are audited by default.</span></span> <span data-ttu-id="86621-114">這表示您不需要在信箱上監視新增的動作。</span><span class="sxs-lookup"><span data-stu-id="86621-114">This means you don't need to monitor add new actions on mailboxes.</span></span>

- <span data-ttu-id="86621-115">您的整個組織都擁有一致的信箱審核原則 (因為您正在為所有信箱進行相同的動作)。</span><span class="sxs-lookup"><span data-stu-id="86621-115">You have a consistent mailbox auditing policy across your organization (because you're auditing the same actions for all mailboxes).</span></span>

> [!TIP]
> <span data-ttu-id="86621-116">關於預設的信箱審核版本, 請記住: 您不需要執行任何動作即可管理信箱審核。</span><span class="sxs-lookup"><span data-stu-id="86621-116">The important thing to remember about the release of mailbox auditing on by default is: you don't need to do anything to manage mailbox auditing.</span></span> <span data-ttu-id="86621-117">不過, 若要深入瞭解, 請從預設設定自訂信箱審核, 或完全關閉它, 本主題可協助您。</span><span class="sxs-lookup"><span data-stu-id="86621-117">However, to learn more, customize mailbox auditing from the default settings, or turn it off altogether, this topic can help you.</span></span>

## <a name="verify-mailbox-auditing-on-by-default-is-turned-on"></a><span data-ttu-id="86621-118">[確認預設會啟用信箱審核]</span><span class="sxs-lookup"><span data-stu-id="86621-118">Verify mailbox auditing on by default is turned on</span></span>

<span data-ttu-id="86621-119">若要確認您的組織預設已啟用信箱審核, 請在[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)中執行下列命令:</span><span class="sxs-lookup"><span data-stu-id="86621-119">To verify that mailbox auditing on by default is turned on for your organization, run the following command in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell):</span></span>

```
Get-OrganizationConfig | Format-List AuditDisabled
```

<span data-ttu-id="86621-120">值**False**表示組織的預設啟用信箱審核。</span><span class="sxs-lookup"><span data-stu-id="86621-120">The value **False** indicates that mailbox auditing on by default is enabled for the organization.</span></span> <span data-ttu-id="86621-121">根據預設, 組織值會覆寫特定信箱上的信箱審核設定。</span><span class="sxs-lookup"><span data-stu-id="86621-121">This on by default organizational value overrides the mailbox auditing setting on specific mailboxes.</span></span> <span data-ttu-id="86621-122">例如, 如果已停用信箱的信箱審核 (信箱上的*AuditEnabled*屬性為**False** ), 則信箱的預設信箱動作仍會針對信箱進行審核, 因為預設會啟用信箱審核公司.</span><span class="sxs-lookup"><span data-stu-id="86621-122">For example, if mailbox auditing is disabled for a mailbox (the *AuditEnabled* property is **False** on the mailbox), the default mailbox actions will still be audited for the mailbox, because mailbox auditing on by default is enabled for the organization.</span></span>

<span data-ttu-id="86621-123">若要讓特定信箱停用信箱審核, 您可以針對信箱擁有者和其他已被委派存取信箱之使用者的信箱, 設定信箱審核略過。</span><span class="sxs-lookup"><span data-stu-id="86621-123">To keep mailbox auditing disabled for specific mailboxes, you configure mailbox auditing bypass for the mailbox owner and other users who have been delegated access to the mailbox.</span></span> <span data-ttu-id="86621-124">如需詳細資訊, 請參閱本主題中的[略過信箱審核記錄](#bypass-mailbox-audit-logging)一節。</span><span class="sxs-lookup"><span data-stu-id="86621-124">For more information, see the [Bypass mailbox audit logging](#bypass-mailbox-audit-logging) section in this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="86621-125">針對組織的預設啟用信箱審核時, 受影響信箱的*AuditEnabled*屬性不會從**False**變更為**True**。</span><span class="sxs-lookup"><span data-stu-id="86621-125">When mailbox auditing on by default is turned on for the organization, the *AuditEnabled* property for affected mailboxes won't be changed from **False** to **True**.</span></span> <span data-ttu-id="86621-126">換句話說, 預設的信箱審核會忽略信箱上的*AuditEnabled*屬性。</span><span class="sxs-lookup"><span data-stu-id="86621-126">In other words, mailbox auditing on by default ignores the *AuditEnabled* property on mailboxes.</span></span>

## <a name="supported-mailbox-types"></a><span data-ttu-id="86621-127">支援的信箱類型</span><span class="sxs-lookup"><span data-stu-id="86621-127">Supported mailbox types</span></span>

<span data-ttu-id="86621-128">下表顯示預設會由信箱審核支援的信箱類型。</span><span class="sxs-lookup"><span data-stu-id="86621-128">The following table shows the mailbox types that are currently supported by mailbox auditing on by default:</span></span>

|<span data-ttu-id="86621-129">**信箱類型**</span><span class="sxs-lookup"><span data-stu-id="86621-129">**Mailbox type**</span></span>|<span data-ttu-id="86621-130">**支援**</span><span class="sxs-lookup"><span data-stu-id="86621-130">**Supported**</span></span>|<span data-ttu-id="86621-131">**不支援**</span><span class="sxs-lookup"><span data-stu-id="86621-131">**Not supported**</span></span>|
|:---------|:---------:|:---------:|
|<span data-ttu-id="86621-132">使用者信箱</span><span class="sxs-lookup"><span data-stu-id="86621-132">User mailboxes</span></span>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|<span data-ttu-id="86621-134">共用信箱</span><span class="sxs-lookup"><span data-stu-id="86621-134">Shared mailboxes</span></span>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|<span data-ttu-id="86621-136">Office 365 群組信箱</span><span class="sxs-lookup"><span data-stu-id="86621-136">Office 365 Group mailboxes</span></span>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|<span data-ttu-id="86621-138">資源信箱</span><span class="sxs-lookup"><span data-stu-id="86621-138">Resource mailboxes</span></span>||![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="86621-140">公用資料夾信箱</span><span class="sxs-lookup"><span data-stu-id="86621-140">Public folder mailboxes</span></span>||![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|

## <a name="logon-types-and-mailbox-actions"></a><span data-ttu-id="86621-142">登入類型和信箱動作</span><span class="sxs-lookup"><span data-stu-id="86621-142">Logon types and mailbox actions</span></span>

<span data-ttu-id="86621-143">登入類型會分類已在信箱上進行審核動作的使用者。</span><span class="sxs-lookup"><span data-stu-id="86621-143">Logon types classify the user that did the audited actions on the mailbox.</span></span> <span data-ttu-id="86621-144">下列清單說明用於信箱審核記錄的登入類型:</span><span class="sxs-lookup"><span data-stu-id="86621-144">The following list describes the logon types that are used in mailbox audit logging:</span></span>

- <span data-ttu-id="86621-145">**擁有**者: 信箱擁有者 (與信箱相關聯的帳戶)。</span><span class="sxs-lookup"><span data-stu-id="86621-145">**Owner**: The mailbox owner (the account that's associated with the mailbox).</span></span>

- <span data-ttu-id="86621-146">**代理人**:</span><span class="sxs-lookup"><span data-stu-id="86621-146">**Delegate**:</span></span>

  - <span data-ttu-id="86621-147">已將 SendAs、SendOnBehalf 或 FullAccess 許可權指派給其他信箱的使用者。</span><span class="sxs-lookup"><span data-stu-id="86621-147">A user who's been assigned the SendAs, SendOnBehalf, or FullAccess permission to another mailbox.</span></span>

  - <span data-ttu-id="86621-148">獲指派 FullAccess 許可權給使用者信箱的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="86621-148">An admin who's been assigned the FullAccess permission to a user's mailbox.</span></span>

- <span data-ttu-id="86621-149">系統**管理**:</span><span class="sxs-lookup"><span data-stu-id="86621-149">**Admin**:</span></span>

  - <span data-ttu-id="86621-150">使用下列其中一個 Microsoft eDiscovery 工具來搜尋信箱:</span><span class="sxs-lookup"><span data-stu-id="86621-150">The mailbox is searched with one of the following Microsoft eDiscovery tools:</span></span>

    - <span data-ttu-id="86621-151">規範中心內的內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="86621-151">Content Search in the Compliance center.</span></span>

    - <span data-ttu-id="86621-152">規範中心的 eDiscovery 或高級 eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="86621-152">eDiscovery or Advanced eDiscovery in the Compliance center.</span></span>

    - <span data-ttu-id="86621-153">Exchange Online 中的就地 eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="86621-153">In-Place eDiscovery in Exchange Online.</span></span>

  - <span data-ttu-id="86621-154">信箱是使用[Microsoft Exchange SERVER MAPI 編輯器](https://go.microsoft.com/fwlink/p/?linkId=204086)來存取。</span><span class="sxs-lookup"><span data-stu-id="86621-154">The mailbox is accessed by using the [Microsoft Exchange Server MAPI Editor](https://go.microsoft.com/fwlink/p/?linkId=204086).</span></span>

### <a name="mailbox-actions-for-user-mailboxes-and-shared-mailboxes"></a><span data-ttu-id="86621-155">使用者信箱和共用信箱的信箱動作</span><span class="sxs-lookup"><span data-stu-id="86621-155">Mailbox actions for user mailboxes and shared mailboxes</span></span>

<span data-ttu-id="86621-156">下表說明使用者信箱和共用信箱的信箱審核記錄中可用的信箱動作。</span><span class="sxs-lookup"><span data-stu-id="86621-156">The following table describes the mailbox actions that are available in mailbox audit logging for user mailboxes and shared mailboxes.</span></span>

- <span data-ttu-id="86621-157">核取記號 (</span><span class="sxs-lookup"><span data-stu-id="86621-157">A check mark (</span></span> ![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<span data-ttu-id="86621-159">) 表示可記錄登入類型的信箱動作 (並非所有動作都適用于所有的登入類型)。</span><span class="sxs-lookup"><span data-stu-id="86621-159">) indicates the mailbox action can be logged for the logon type (not all actions are available for all logon types).</span></span>

- <span data-ttu-id="86621-160">核取記號後<sup>\*</sup>的星號 () 表示登入類型預設會記錄信箱動作。</span><span class="sxs-lookup"><span data-stu-id="86621-160">An asterisk ( <sup>\*</sup> ) after the check mark indicates the mailbox action is logged by default for the logon type.</span></span>

- <span data-ttu-id="86621-161">請記住, 擁有信箱完整存取權限的系統管理員會被視為代理人。</span><span class="sxs-lookup"><span data-stu-id="86621-161">Remember, an admin with Full Access permission to a mailbox is considered a delegate.</span></span>

|<span data-ttu-id="86621-162">**信箱動作**</span><span class="sxs-lookup"><span data-stu-id="86621-162">**Mailbox action**</span></span>|<span data-ttu-id="86621-163">**描述**</span><span class="sxs-lookup"><span data-stu-id="86621-163">**Description**</span></span>|<span data-ttu-id="86621-164">**Admin**</span><span class="sxs-lookup"><span data-stu-id="86621-164">**Admin**</span></span>|<span data-ttu-id="86621-165">**代理人**</span><span class="sxs-lookup"><span data-stu-id="86621-165">**Delegate**</span></span>|<span data-ttu-id="86621-166">**Owner**</span><span class="sxs-lookup"><span data-stu-id="86621-166">**Owner**</span></span>|
|:---------|:---------|:---------:|:---------:|:---------:|
|<span data-ttu-id="86621-167">**AddFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="86621-167">**AddFolderPermissions**</span></span>|<span data-ttu-id="86621-168">**附注**: 雖然此值接受為信箱動作, 但它已包含在**UpdateFolderPermissions**動作中, 而且不會個別審核。</span><span class="sxs-lookup"><span data-stu-id="86621-168">**Note**: Although this value is accepted as a mailbox action, it's already included in the **UpdateFolderPermissions** action and isn't audited separately.</span></span> <span data-ttu-id="86621-169">換句話說, 請勿使用此值。</span><span class="sxs-lookup"><span data-stu-id="86621-169">In other words, don't use this value.</span></span>||||
|<span data-ttu-id="86621-170">**ApplyRecord**</span><span class="sxs-lookup"><span data-stu-id="86621-170">**ApplyRecord**</span></span>|<span data-ttu-id="86621-171">專案已標示為記錄。</span><span class="sxs-lookup"><span data-stu-id="86621-171">An item is labeled as a record.</span></span>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="86621-175">**Copy**</span><span class="sxs-lookup"><span data-stu-id="86621-175">**Copy**</span></span>|<span data-ttu-id="86621-176">郵件已複製到另一個資料夾。</span><span class="sxs-lookup"><span data-stu-id="86621-176">A message was copied to another folder.</span></span>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|<span data-ttu-id="86621-178">**Create**</span><span class="sxs-lookup"><span data-stu-id="86621-178">**Create**</span></span>|<span data-ttu-id="86621-179">已在信箱的 [行事曆]、[連絡人]、[記事] 或 [任務] 資料夾中建立專案 (例如, 建立新的會議邀請)。</span><span class="sxs-lookup"><span data-stu-id="86621-179">An item was created in the Calendar, Contacts, Notes, or Tasks folder in the mailbox (for example, a new meeting request is created).</span></span> <span data-ttu-id="86621-180">請注意, 不會審核建立、傳送或接收郵件。</span><span class="sxs-lookup"><span data-stu-id="86621-180">Note that creating, sending, or receiving a message isn't audited.</span></span> <span data-ttu-id="86621-181">此外, 也不會審核建立信箱資料夾。</span><span class="sxs-lookup"><span data-stu-id="86621-181">Also, creating a mailbox folder is not audited.</span></span>|<span data-ttu-id="86621-182">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-182">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="86621-183">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-183">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="86621-185">**FolderBind**</span><span class="sxs-lookup"><span data-stu-id="86621-185">**FolderBind**</span></span>|<span data-ttu-id="86621-186">已存取信箱資料夾。</span><span class="sxs-lookup"><span data-stu-id="86621-186">A mailbox folder was accessed.</span></span> <span data-ttu-id="86621-187">當系統管理員或代理人開啟信箱時, 也會記錄此動作。</span><span class="sxs-lookup"><span data-stu-id="86621-187">This action is also logged when the admin or delegate opens the mailbox.</span></span> <br/><br/> <span data-ttu-id="86621-188">**附注**: 合併委派所執行之資料夾系結動作的審計記錄。</span><span class="sxs-lookup"><span data-stu-id="86621-188">**Note**: Audit records for folder bind actions performed by delegates are consolidated.</span></span> <span data-ttu-id="86621-189">為24小時期間內的個別資料夾存取產生一個審計記錄。</span><span class="sxs-lookup"><span data-stu-id="86621-189">One audit record is generated for individual folder access within 24 hour period.</span></span>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|<span data-ttu-id="86621-192">**HardDelete**</span><span class="sxs-lookup"><span data-stu-id="86621-192">**HardDelete**</span></span>|<span data-ttu-id="86621-193">已從 [可復原的專案] 資料夾中清除郵件。</span><span class="sxs-lookup"><span data-stu-id="86621-193">A message was purged from the Recoverable Items folder.</span></span>|<span data-ttu-id="86621-194">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-194">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="86621-195">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-195">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="86621-196">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-196">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="86621-197">**MailboxLogin**</span><span class="sxs-lookup"><span data-stu-id="86621-197">**MailboxLogin**</span></span>|<span data-ttu-id="86621-198">使用者已登入其信箱。</span><span class="sxs-lookup"><span data-stu-id="86621-198">The user signed into their mailbox.</span></span> |||![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="86621-200">**MessageBind**</span><span class="sxs-lookup"><span data-stu-id="86621-200">**MessageBind**</span></span>|<span data-ttu-id="86621-201">已在預覽窗格中查看或開啟郵件。</span><span class="sxs-lookup"><span data-stu-id="86621-201">A message was viewed in the preview pane or opened.</span></span>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|<span data-ttu-id="86621-203">**ModifyFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="86621-203">**ModifyFolderPermissions**</span></span>|<span data-ttu-id="86621-204">**附注**: 雖然此值接受為信箱動作, 但它已包含在**UpdateFolderPermissions**動作中, 而且不會個別審核。</span><span class="sxs-lookup"><span data-stu-id="86621-204">**Note**: Although this value is accepted as a mailbox action, it's already included in the **UpdateFolderPermissions** action and isn't audited separately.</span></span> <span data-ttu-id="86621-205">換句話說, 請勿使用此值。</span><span class="sxs-lookup"><span data-stu-id="86621-205">In other words, don't use this value.</span></span>||||
|<span data-ttu-id="86621-206">**Move**</span><span class="sxs-lookup"><span data-stu-id="86621-206">**Move**</span></span>|<span data-ttu-id="86621-207">郵件已移至另一個資料夾。</span><span class="sxs-lookup"><span data-stu-id="86621-207">A message was moved to another folder.</span></span>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="86621-211">**MoveToDeletedItems**</span><span class="sxs-lookup"><span data-stu-id="86621-211">**MoveToDeletedItems**</span></span>|<span data-ttu-id="86621-212">郵件已刪除並移至 [刪除的郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="86621-212">A message was deleted and moved to the Deleted Items folder.</span></span>|<span data-ttu-id="86621-213">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-213">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="86621-214">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-214">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="86621-215">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-215">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="86621-216">**RecordDelete**</span><span class="sxs-lookup"><span data-stu-id="86621-216">**RecordDelete**</span></span>|<span data-ttu-id="86621-217">標示為記錄的專案已虛刪除 (移至 [可復原的專案] 資料夾)。</span><span class="sxs-lookup"><span data-stu-id="86621-217">An item that's labeled as a record was soft-deleted (moved to the Recoverable Items folder).</span></span> <span data-ttu-id="86621-218">標記為記錄的專案無法永久刪除 (從 [可復原的專案] 資料夾中清除)。</span><span class="sxs-lookup"><span data-stu-id="86621-218">Items labeled as records can't be permanently deleted (purged from the Recoverable Items folder).</span></span>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="86621-222">**RemoveFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="86621-222">**RemoveFolderPermissions**</span></span>|<span data-ttu-id="86621-223">**附注**: 雖然此值接受為信箱動作, 但它已包含在**UpdateFolderPermissions**動作中, 而且不會個別審核。</span><span class="sxs-lookup"><span data-stu-id="86621-223">**Note**: Although this value is accepted as a mailbox action, it's already included in the **UpdateFolderPermissions** action and isn't audited separately.</span></span> <span data-ttu-id="86621-224">換句話說, 請勿使用此值。</span><span class="sxs-lookup"><span data-stu-id="86621-224">In other words, don't use this value.</span></span>||||
|<span data-ttu-id="86621-225">**SendAs**</span><span class="sxs-lookup"><span data-stu-id="86621-225">**SendAs**</span></span>|<span data-ttu-id="86621-226">使用 SendAs 許可權傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="86621-226">A message was sent using the SendAs permission.</span></span> <span data-ttu-id="86621-227">這表示另一位使用者傳送郵件的方式, 就好像它來自信箱擁有者一樣。</span><span class="sxs-lookup"><span data-stu-id="86621-227">This means another user sent the message as though it came from the mailbox owner.</span></span>|<span data-ttu-id="86621-228">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-228">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="86621-229">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-229">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="86621-230">**SendOnBehalf**</span><span class="sxs-lookup"><span data-stu-id="86621-230">**SendOnBehalf**</span></span>|<span data-ttu-id="86621-231">使用 SendOnBehalf 許可權傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="86621-231">A message was sent using the SendOnBehalf permission.</span></span> <span data-ttu-id="86621-232">這表示另一位使用者會代表信箱擁有者傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="86621-232">This means another user sent the message on behalf of the mailbox owner.</span></span> <span data-ttu-id="86621-233">此訊息會指出郵件的收件者是代表傳送郵件, 以及實際傳送郵件的寄件者。</span><span class="sxs-lookup"><span data-stu-id="86621-233">The message indicates to the recipient who the message was sent on behalf of and who actually sent the message.</span></span>|<span data-ttu-id="86621-234">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-234">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="86621-235">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-235">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="86621-236">**SoftDelete**</span><span class="sxs-lookup"><span data-stu-id="86621-236">**SoftDelete**</span></span>|<span data-ttu-id="86621-237">從 [刪除的郵件] 資料夾中永久刪除或刪除郵件。</span><span class="sxs-lookup"><span data-stu-id="86621-237">A message was permanently deleted or deleted from the Deleted Items folder.</span></span> <span data-ttu-id="86621-238">虛刪除的專案會移至 [可復原的專案] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="86621-238">Soft-deleted items are moved to the Recoverable Items folder.</span></span>|<span data-ttu-id="86621-239">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-239">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="86621-240">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-240">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="86621-241">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-241">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="86621-242">**Update**</span><span class="sxs-lookup"><span data-stu-id="86621-242">**Update**</span></span>|<span data-ttu-id="86621-243">已變更郵件或其屬性。</span><span class="sxs-lookup"><span data-stu-id="86621-243">A message or its properties was changed.</span></span>|<span data-ttu-id="86621-244">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-244">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="86621-245">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-245">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="86621-246">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-246">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="86621-247">**UpdateCalendarDelegation**</span><span class="sxs-lookup"><span data-stu-id="86621-247">**UpdateCalendarDelegation**</span></span>|<span data-ttu-id="86621-248">已將行事曆委派指派給信箱。</span><span class="sxs-lookup"><span data-stu-id="86621-248">A calendar delegation was assigned to a mailbox.</span></span> <span data-ttu-id="86621-249">行事曆委派可讓相同組織中的其他人管理信箱擁有者的行事曆。</span><span class="sxs-lookup"><span data-stu-id="86621-249">Calendar delegation gives someone else in the same organization permissions to manage the mailbox owner's calendar.</span></span>|<span data-ttu-id="86621-250">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-250">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>||<span data-ttu-id="86621-251">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-251">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="86621-252">**UpdateFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="86621-252">**UpdateFolderPermissions**</span></span>|<span data-ttu-id="86621-253">已變更資料夾許可權。</span><span class="sxs-lookup"><span data-stu-id="86621-253">A folder permission was changed.</span></span> <span data-ttu-id="86621-254">資料夾許可權控制您組織中的哪些使用者可以存取信箱中的資料夾, 以及位於這些資料夾中的郵件。</span><span class="sxs-lookup"><span data-stu-id="86621-254">Folder permissions control which users in your organization can access folders in a mailbox and the messages located in those folders.</span></span>|<span data-ttu-id="86621-255">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-255">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="86621-256">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-256">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="86621-257">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-257">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="86621-258">**UpdateInboxRules**</span><span class="sxs-lookup"><span data-stu-id="86621-258">**UpdateInboxRules**</span></span>|<span data-ttu-id="86621-259">新增、移除或變更收件匣規則。</span><span class="sxs-lookup"><span data-stu-id="86621-259">An inbox rule was added, removed, or changed.</span></span> <span data-ttu-id="86621-260">收件匣規則用來根據指定的條件處理使用者收件匣中的郵件, 並在符合規則條件時採取動作, 例如將郵件移至指定的資料夾或刪除郵件。</span><span class="sxs-lookup"><span data-stu-id="86621-260">Inbox rules are used to process messages in the user's Inbox based on the specified conditions and take actions when the conditions of a rule are met, such as moving a message to a specified folder or deleting a message.</span></span>|<span data-ttu-id="86621-261">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-261">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="86621-262">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-262">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="86621-263">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-263">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|

> [!IMPORTANT]
> <span data-ttu-id="86621-264">如果您已在組織中針對預設啟用信箱審核而\*\* 自訂要對任何登入類型進行審核的信箱動作, 則自訂設定會保留在信箱上, 而且預設信箱動作不會覆寫該自訂設定。本節所述。</span><span class="sxs-lookup"><span data-stu-id="86621-264">If you customized the mailbox actions to audit for any logon type *before* mailbox auditing on by default was enabled in your organization, the customized settings are preserved on the mailbox and aren't overwritten by the default mailbox actions as described in this section.</span></span> <span data-ttu-id="86621-265">若要將審核信箱動作還原成其預設值 (您可以隨時執行), 請參閱本主題稍後的[還原預設信箱動作](#restore-the-default-mailbox-actions)一節。</span><span class="sxs-lookup"><span data-stu-id="86621-265">To revert the audit mailbox actions to their default values (which you can do at any time), see the [Restore the default mailbox actions](#restore-the-default-mailbox-actions) section later in this topic.</span></span>

### <a name="mailbox-actions-for-office-365-group-mailboxes"></a><span data-ttu-id="86621-266">Office 365 群組信箱的信箱動作</span><span class="sxs-lookup"><span data-stu-id="86621-266">Mailbox actions for Office 365 Group mailboxes</span></span>

<span data-ttu-id="86621-267">信箱的審核預設會將信箱審核記錄帶入 Office 365 群組信箱, 但您無法自訂要記錄的內容 (您無法新增或移除針對任何登入類型記錄的信箱動作)。</span><span class="sxs-lookup"><span data-stu-id="86621-267">Mailbox auditing on by default brings mailbox audit logging to Office 365 Group mailboxes, but you can't customize what's being logged (you can't add or remove mailbox actions that are logged for any logon type).</span></span>

<span data-ttu-id="86621-268">下表說明每個登入類型的 Office 365 群組信箱上預設記錄的信箱動作。</span><span class="sxs-lookup"><span data-stu-id="86621-268">The following table describes the mailbox actions that are logged by default on Office 365 Group mailboxes for each logon type.</span></span>

<span data-ttu-id="86621-269">請記住, 擁有 Office 365 群組信箱完整存取權限的系統管理員會被視為代理人。</span><span class="sxs-lookup"><span data-stu-id="86621-269">Remember, an admin with Full Access permission to an Office 365 Group mailbox is considered a delegate.</span></span>

|<span data-ttu-id="86621-270">**信箱動作**</span><span class="sxs-lookup"><span data-stu-id="86621-270">**Mailbox action**</span></span>|<span data-ttu-id="86621-271">**描述**</span><span class="sxs-lookup"><span data-stu-id="86621-271">**Description**</span></span>|<span data-ttu-id="86621-272">**Admin**</span><span class="sxs-lookup"><span data-stu-id="86621-272">**Admin**</span></span>|<span data-ttu-id="86621-273">**代理人**</span><span class="sxs-lookup"><span data-stu-id="86621-273">**Delegate**</span></span>|<span data-ttu-id="86621-274">**Owner**</span><span class="sxs-lookup"><span data-stu-id="86621-274">**Owner**</span></span>|
|:---------|:---------|:---------:|:---------:|:---------:|
|<span data-ttu-id="86621-275">**Create**</span><span class="sxs-lookup"><span data-stu-id="86621-275">**Create**</span></span>|<span data-ttu-id="86621-276">建立行事曆專案。</span><span class="sxs-lookup"><span data-stu-id="86621-276">Creation of a calendar Item.</span></span> <span data-ttu-id="86621-277">請注意, 不會審核建立、傳送或接收郵件。</span><span class="sxs-lookup"><span data-stu-id="86621-277">Note that creating, sending, or receiving a message isn't audited.</span></span>|<span data-ttu-id="86621-278">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-278">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="86621-279">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-279">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="86621-280">**HardDelete**</span><span class="sxs-lookup"><span data-stu-id="86621-280">**HardDelete**</span></span>|<span data-ttu-id="86621-281">已從 [可復原的專案] 資料夾中清除郵件。</span><span class="sxs-lookup"><span data-stu-id="86621-281">A message was purged from the Recoverable Items folder.</span></span>|<span data-ttu-id="86621-282">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-282">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="86621-283">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-283">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="86621-284">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-284">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="86621-285">**MoveToDeletedItems**</span><span class="sxs-lookup"><span data-stu-id="86621-285">**MoveToDeletedItems**</span></span>|<span data-ttu-id="86621-286">郵件已刪除並移至 [刪除的郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="86621-286">A message was deleted and moved to the Deleted Items folder.</span></span>|<span data-ttu-id="86621-287">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-287">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="86621-288">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-288">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="86621-289">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-289">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="86621-290">**SendAs**</span><span class="sxs-lookup"><span data-stu-id="86621-290">**SendAs**</span></span>|<span data-ttu-id="86621-291">使用 SendAs 許可權傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="86621-291">A message was sent using the SendAs permission.</span></span>|<span data-ttu-id="86621-292">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-292">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="86621-293">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-293">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="86621-294">**SendOnBehalf**</span><span class="sxs-lookup"><span data-stu-id="86621-294">**SendOnBehalf**</span></span>|<span data-ttu-id="86621-295">使用 SendOnBehalf 許可權傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="86621-295">A message was sent using the SendOnBehalf permission.</span></span> |<span data-ttu-id="86621-296">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-296">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="86621-297">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-297">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="86621-298">**SoftDelete**</span><span class="sxs-lookup"><span data-stu-id="86621-298">**SoftDelete**</span></span>|<span data-ttu-id="86621-299">從 [刪除的郵件] 資料夾中永久刪除或刪除郵件。</span><span class="sxs-lookup"><span data-stu-id="86621-299">A message was permanently deleted or deleted from the Deleted Items folder.</span></span> <span data-ttu-id="86621-300">虛刪除的專案會移至 [可復原的專案] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="86621-300">Soft-deleted items are moved to the Recoverable Items folder.</span></span>|<span data-ttu-id="86621-301">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-301">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="86621-302">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-302">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="86621-303">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-303">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="86621-304">**Update**</span><span class="sxs-lookup"><span data-stu-id="86621-304">**Update**</span></span>|<span data-ttu-id="86621-305">已變更郵件或其屬性。</span><span class="sxs-lookup"><span data-stu-id="86621-305">A message or its properties was changed.</span></span>|<span data-ttu-id="86621-306">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-306">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="86621-307">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-307">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="86621-308">![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86621-308">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|

### <a name="verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type"></a><span data-ttu-id="86621-309">確認每個登入類型都要記錄預設信箱動作</span><span class="sxs-lookup"><span data-stu-id="86621-309">Verify that default mailbox actions are being logged for each logon type</span></span>

<span data-ttu-id="86621-310">信箱審核依據預設值會將新的*DefaultAuditSet*屬性新增至所有信箱。</span><span class="sxs-lookup"><span data-stu-id="86621-310">Mailbox auditing on by defaults adds a new *DefaultAuditSet* property to all mailboxes.</span></span> <span data-ttu-id="86621-311">此屬性的值會指出是否要在信箱上審核預設信箱動作 (由 Microsoft 管理)。</span><span class="sxs-lookup"><span data-stu-id="86621-311">The value of this property indicates whether the default mailbox actions (managed by Microsoft) are being audited on the mailbox.</span></span>

<span data-ttu-id="86621-312">若要在使用者信箱或共用信箱上顯示值, \<請\>將 mailboxidentity 為信箱取代為信箱的名稱、別名、電子郵件地址或使用者主要名稱 (username), 並在 Exchange Online PowerShell 中執行下列命令:</span><span class="sxs-lookup"><span data-stu-id="86621-312">To display the value on user mailboxes or shared mailboxes, replace \<MailboxIdentity\> with the name, alias, email address, or user principal name (username) of the mailbox and run the following command in Exchange Online PowerShell:</span></span>

```
Get-Mailbox -Identity <MailboxIdentity> | Format-List DefaultAuditSet
```

<span data-ttu-id="86621-313">若要在 Office 365 群組信箱上顯示值, \<請\>將 mailboxidentity 為信箱取代為共用信箱的名稱、別名或電子郵件地址, 並在 Exchange Online PowerShell 中執行下列命令:</span><span class="sxs-lookup"><span data-stu-id="86621-313">To display the value on Office 365 group mailboxes, replace \<MailboxIdentity\> with the name, alias, or email address of the shared mailbox and run the following command in Exchange Online PowerShell:</span></span>

```
Get-Mailbox -Identity <MailboxIdentity> -GroupMailbox | Format-List DefaultAuditSet
```

<span data-ttu-id="86621-314">此值`Admin, Delegate, Owner`表示:</span><span class="sxs-lookup"><span data-stu-id="86621-314">The value `Admin, Delegate, Owner` indicates:</span></span>

- <span data-ttu-id="86621-315">所有三種登入類型的預設信箱動作都會受到審核。</span><span class="sxs-lookup"><span data-stu-id="86621-315">The default mailbox actions for all three logon types are being audited.</span></span> <span data-ttu-id="86621-316">請注意, 這是您在 Office 365 群組信箱上看到的唯一值。</span><span class="sxs-lookup"><span data-stu-id="86621-316">Note that this is the only value you'll see on Office 365 Group mailboxes.</span></span>

- <span data-ttu-id="86621-317">系統管理員*未*變更使用者信箱或共用信箱上任何登入類型的已審核信箱動作。</span><span class="sxs-lookup"><span data-stu-id="86621-317">An admin *has not* changed the audited mailbox actions for any logon type on a user mailbox or a shared mailbox.</span></span> <span data-ttu-id="86621-318">附注: 這是最初在您的組織中開啟信箱審核之後的預設狀態。</span><span class="sxs-lookup"><span data-stu-id="86621-318">Note this is the default state after mailbox auditing on by default is initially turned on in your organization.</span></span>

<span data-ttu-id="86621-319">如果系統管理員曾經變更過使用*AuditAdmin*、 *AuditDelegate*或*AuditOwner*參數的登**入**類型所審核的信箱動作, 則此屬性值會不同。</span><span class="sxs-lookup"><span data-stu-id="86621-319">If an admin has ever changed the mailbox actions that are audited for a logon type (by using the *AuditAdmin*, *AuditDelegate*, or *AuditOwner* parameters on the **Set-Mailbox** cmdlet), the property value will be different.</span></span>

<span data-ttu-id="86621-320">例如, 使用者信箱或`Owner`共用信箱上的*DefaultAuditSet*屬性值會指出:</span><span class="sxs-lookup"><span data-stu-id="86621-320">For example, the value `Owner` for the *DefaultAuditSet* property on a user mailbox or shared mailbox indicates:</span></span>

- <span data-ttu-id="86621-321">審核信箱擁有者的預設信箱動作。</span><span class="sxs-lookup"><span data-stu-id="86621-321">The default mailbox actions for the mailbox owner are being audited.</span></span>

- <span data-ttu-id="86621-322">[] 和`Delegate` `Admin` [登入] 類型的已審核信箱動作已變更為預設動作。</span><span class="sxs-lookup"><span data-stu-id="86621-322">The audited mailbox actions for the `Delegate` and `Admin` logon types have been changed from the default actions.</span></span>

<span data-ttu-id="86621-323">*DefaultAuditSet*屬性的空白值會指出在使用者信箱或共用信箱上, 所有三種登入類型的信箱動作都已變更。</span><span class="sxs-lookup"><span data-stu-id="86621-323">A blank value for the *DefaultAuditSet* property indicates the mailbox actions for all three logon types have been changed on the user mailbox or a shared mailbox.</span></span>

<span data-ttu-id="86621-324">如需詳細資訊, 請參閱本主題中的 [[變更或還原依預設記錄的信箱動作](#change-or-restore-mailbox-actions-logged-by-default)] 一節</span><span class="sxs-lookup"><span data-stu-id="86621-324">For more information, see the [Change or restore mailbox actions logged by default](#change-or-restore-mailbox-actions-logged-by-default) section in this topic</span></span>

### <a name="display-the-mailbox-actions-that-are-being-logged-on-mailboxes"></a><span data-ttu-id="86621-325">顯示正在登入信箱的信箱動作</span><span class="sxs-lookup"><span data-stu-id="86621-325">Display the mailbox actions that are being logged on mailboxes</span></span>

<span data-ttu-id="86621-326">若要查看目前登入使用者信箱或共用信箱的信箱動作, 請將 mailboxidentity 為信箱\< \>取代為信箱的名稱、別名、電子郵件地址或使用者主要名稱 (username), 並執行下列一或多項作業:Exchange Online PowerShell 中的命令。</span><span class="sxs-lookup"><span data-stu-id="86621-326">To see the mailbox actions that are currently being logged on user mailboxes or shared mailboxes, replace \<MailboxIdentity\> with the name, alias, email address, or user principal name (username) of the mailbox, and run one or more of the following commands in Exchange Online PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="86621-327">雖然您可以將此`-GroupMailbox`參數新增至 Office 365 群組信箱的下列**取得信箱**命令, 但不相信您看到的值。</span><span class="sxs-lookup"><span data-stu-id="86621-327">Although you can add the `-GroupMailbox` switch to the following **Get-Mailbox** commands for Office 365 Group mailboxes, don't believe the values you see.</span></span> <span data-ttu-id="86621-328">在本主題稍早的[office 365 群組信箱的信箱動作](#mailbox-actions-for-office-365-group-mailboxes)中, 會說明針對 Office 365 群組信箱所審核的預設和靜態信箱動作。</span><span class="sxs-lookup"><span data-stu-id="86621-328">The default and static mailbox actions that are audited for Office 365 Group mailboxes are described in the [Mailbox actions for Office 365 Group mailboxes](#mailbox-actions-for-office-365-group-mailboxes) section earlier in this topic.</span></span>

#### <a name="owner-actions"></a><span data-ttu-id="86621-329">擁有者動作</span><span class="sxs-lookup"><span data-stu-id="86621-329">Owner actions</span></span>

```
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditOwner
```

#### <a name="delegate-actions"></a><span data-ttu-id="86621-330">委派動作</span><span class="sxs-lookup"><span data-stu-id="86621-330">Delegate actions</span></span>

```
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditDelegate
```

#### <a name="admin-actions"></a><span data-ttu-id="86621-331">系統管理動作</span><span class="sxs-lookup"><span data-stu-id="86621-331">Admin actions</span></span>

```
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditAdmin
```

## <a name="change-or-restore-mailbox-actions-logged-by-default"></a><span data-ttu-id="86621-332">變更或還原依預設記錄的信箱動作</span><span class="sxs-lookup"><span data-stu-id="86621-332">Change or restore mailbox actions logged by default</span></span>

<span data-ttu-id="86621-333">如先前所述, 預設會啟用信箱審核的其中一個主要優點是: 您不需要管理已審核的信箱動作。</span><span class="sxs-lookup"><span data-stu-id="86621-333">As previously explained, one of the key benefits of having mailbox auditing on by default is: you don't need to manage the mailboxes actions that are audited.</span></span> <span data-ttu-id="86621-334">Microsoft 為您執行這一作業, 我們會在發佈時自動新增要進行審核的新信箱動作。</span><span class="sxs-lookup"><span data-stu-id="86621-334">Microsoft does this for you and we'll automatically add new mailbox actions to be audited by default as they're released.</span></span>

<span data-ttu-id="86621-335">不過, 您的組織可能需要為使用者信箱和共用信箱審計一組不同的信箱動作。</span><span class="sxs-lookup"><span data-stu-id="86621-335">However, your organization might be required to audit a different set of mailbox actions for user mailboxes and shared mailboxes.</span></span> <span data-ttu-id="86621-336">本節中的程式將示範如何變更針對每個登入類型進行審核的信箱動作, 以及如何回復至 Microsoft 受管理的預設動作。</span><span class="sxs-lookup"><span data-stu-id="86621-336">The procedures in this section show you how to change the mailbox actions that are audited for each logon type, and how to revert back to the Microsoft-managed default actions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="86621-337">如果您使用下列程式來自訂使用者信箱或共用信箱上所記錄的信箱動作, 則不會在這些信箱上自動進行任何 Microsoft 發行的預設信箱動作。</span><span class="sxs-lookup"><span data-stu-id="86621-337">If you use the following procedures to customize the mailbox actions that are logged on user mailboxes or shared mailboxes, any new default mailbox actions released by Microsoft will not be automatically audited on those mailboxes.</span></span> <span data-ttu-id="86621-338">您必須手動將任何新的信箱動作新增至自訂的動作清單中。</span><span class="sxs-lookup"><span data-stu-id="86621-338">You'll need to manually add any new mailbox actions to your customized list of actions.</span></span>

### <a name="change-the-mailbox-actions-to-audit"></a><span data-ttu-id="86621-339">變更要審核的信箱動作</span><span class="sxs-lookup"><span data-stu-id="86621-339">Change the mailbox actions to audit</span></span>

<span data-ttu-id="86621-340">您可以在**設定信箱**Cmdlet 上使用*AuditAdmin*、 *AuditDelegate*或*AuditOwner*參數, 以變更針對使用者信箱和共用信箱所審核的信箱動作 (Office 365 群組的已審核動作)無法自訂信箱)。</span><span class="sxs-lookup"><span data-stu-id="86621-340">You can use the *AuditAdmin*, *AuditDelegate*, or *AuditOwner* parameters on the **Set-Mailbox** cmdlet to change the mailbox actions that are audited for user mailboxes and shared mailboxes (audited actions for Office 365 group mailboxes can't be customized).</span></span>

<span data-ttu-id="86621-341">您可以使用兩種不同的方法來指定信箱動作:</span><span class="sxs-lookup"><span data-stu-id="86621-341">You can use two different methods to specify the mailbox actions:</span></span>

- <span data-ttu-id="86621-342">*Replace*(使用下列語法, 覆寫) 現有的信箱動作`action1,action2,...actionN`:。</span><span class="sxs-lookup"><span data-stu-id="86621-342">*Replace* (overwrite) the existing mailbox actions by using this syntax: `action1,action2,...actionN`.</span></span>

- <span data-ttu-id="86621-343">使用下列語法,*新增或移除*信箱動作, 而不影響其他現有`@{Add="action1","action2",..."actionN"}`的`@{Remove="action1","action2",..."actionN"}`值: 或。</span><span class="sxs-lookup"><span data-stu-id="86621-343">*Add or remove* mailbox actions without affecting other existing values by using this syntax: `@{Add="action1","action2",..."actionN"}` or `@{Remove="action1","action2",..."actionN"}`.</span></span>

<span data-ttu-id="86621-344">此範例會使用 SoftDelete 和 HardDelete 覆寫預設動作, 以變更名為 "Gabriela Laureano" 之信箱的系統管理員信箱動作。</span><span class="sxs-lookup"><span data-stu-id="86621-344">This example changes the admin mailbox actions for the mailbox named "Gabriela Laureano" by overwriting the default actions with SoftDelete and HardDelete.</span></span>

```
Set-Mailbox -Identity "Gabriela Laureano" -AuditAdmin HardDelete,SoftDelete
```

<span data-ttu-id="86621-345">此範例會將 MailboxLogin 擁有者動作新增至信箱 laura@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="86621-345">This example adds the MailboxLogin owner action to the mailbox laura@contoso.onmicrosoft.com.</span></span>

```
Set-Mailbox -Identity laura@contoso.onmicrosoft.com -AuditOwner @{Add="MailboxLogin"}
```

<span data-ttu-id="86621-346">本範例會移除小組討論信箱的 MoveToDeletedItems 委派動作。</span><span class="sxs-lookup"><span data-stu-id="86621-346">This example removes the MoveToDeletedItems delegate action for the Team Discussion mailbox.</span></span>

```
Set-Mailbox -Identity "Team Discussion" -AuditDelegate @{Remove="MoveToDeletedItems"}
```

<span data-ttu-id="86621-347">不論您使用的是何種方法, 自訂使用者信箱或共用信箱上的已審核信箱動作都有下列結果:</span><span class="sxs-lookup"><span data-stu-id="86621-347">Regardless of the method you use, customizing the audited mailbox actions on user mailboxes or shared mailboxes has the following results:</span></span>

- <span data-ttu-id="86621-348">對於您自訂的登入類型, 已不再由 Microsoft 管理已審核的信箱動作。</span><span class="sxs-lookup"><span data-stu-id="86621-348">For the logon type that you customized, the audited mailbox actions are no longer managed by Microsoft.</span></span>

- <span data-ttu-id="86621-349">您自訂的登入類型不再顯示在信箱的*DefaultAuditSet*屬性值中, 如[先前所述](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type)。</span><span class="sxs-lookup"><span data-stu-id="86621-349">The logon type that you customized is no longer displayed in the *DefaultAuditSet* property value for the mailbox as [previously described](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type).</span></span>

### <a name="restore-the-default-mailbox-actions"></a><span data-ttu-id="86621-350">還原預設信箱動作</span><span class="sxs-lookup"><span data-stu-id="86621-350">Restore the default mailbox actions</span></span>

<span data-ttu-id="86621-351">如果您自訂在使用者信箱或共用信箱上進行審核的信箱動作, 您可以使用下列語法來還原一或所有登入類型的預設信箱動作:</span><span class="sxs-lookup"><span data-stu-id="86621-351">If you customized the mailbox actions that are audited on a user mailbox or a shared mailbox, you can restore the default mailbox actions for one or all logon types by using this syntax:</span></span>

```
Set-Mailbox -Identity <MailboxIdentity> -DefaultAuditSet <Admin | Delegate | Owner>
```

<span data-ttu-id="86621-352">您可以指定多個以逗號分隔的*DefaultAuditSet*值</span><span class="sxs-lookup"><span data-stu-id="86621-352">You can specify multiple *DefaultAuditSet* values separated by commas</span></span>

<span data-ttu-id="86621-353">**附注**: 下列程式不適用於 Office 365 群組信箱 (其限制為預設動作, 如下所述)。 [](#mailbox-actions-for-office-365-group-mailboxes)</span><span class="sxs-lookup"><span data-stu-id="86621-353">**Note**: The following procedures don't apply to Office 365 Group mailboxes (they're limited to the default actions as described [here](#mailbox-actions-for-office-365-group-mailboxes)).</span></span>

<span data-ttu-id="86621-354">此範例會針對信箱 mark@contoso.onmicrosoft.com 上的所有登入類型, 還原預設的已審核信箱動作。</span><span class="sxs-lookup"><span data-stu-id="86621-354">This example restores the default audited mailbox actions for all logon types on the mailbox mark@contoso.onmicrosoft.com.</span></span>

```
Set-Mailbox -Identity mark@contoso.onmicrosoft.com -DefaultAuditSet Admin,Delegate,Owner
```

<span data-ttu-id="86621-355">此範例會針對信箱 chris@contoso.onmicrosoft.com 上的系統管理員登入類型還原預設的已審核信箱動作, 但會保留委派和擁有者登入類型的自訂已審核信箱動作。</span><span class="sxs-lookup"><span data-stu-id="86621-355">This example restores the default audited mailbox actions for the Admin logon type on the mailbox chris@contoso.onmicrosoft.com, but leaves the customized audited mailbox actions for the Delegate and Owner logon types.</span></span>

```
Set-Mailbox -Identity chris@contoso.onmicrosoft.com -DefaultAuditSet Admin
```

<span data-ttu-id="86621-356">還原登入類型的預設已審核信箱動作有下列結果:</span><span class="sxs-lookup"><span data-stu-id="86621-356">Restoring he default audited mailbox actions for a logon type has the following results:</span></span>

- <span data-ttu-id="86621-357">目前的信箱動作清單會取代為登入類型的預設信箱動作。</span><span class="sxs-lookup"><span data-stu-id="86621-357">The current list of mailbox actions is replaced with the default mailbox actions for the logon type.</span></span>

- <span data-ttu-id="86621-358">任何由 Microsoft 發行的新信箱動作都會自動新增至登入類型的已審核動作清單中。</span><span class="sxs-lookup"><span data-stu-id="86621-358">Any new mailbox actions that are released by Microsoft are automatically added to the list of audited actions for the logon type.</span></span>

- <span data-ttu-id="86621-359">信箱的*DefaultAuditSet*屬性值會更新為包含還原的登入類型。</span><span class="sxs-lookup"><span data-stu-id="86621-359">The *DefaultAuditSet* property value for the mailbox is updated to include the restored logon type.</span></span>

## <a name="turn-off-mailbox-auditing-on-by-default-for-your-organization"></a><span data-ttu-id="86621-360">針對貴組織預設關閉信箱審核</span><span class="sxs-lookup"><span data-stu-id="86621-360">Turn off mailbox auditing on by default for your organization</span></span>

<span data-ttu-id="86621-361">您可以在 Exchange Online PowerShell 中執行下列命令, 關閉整個組織的預設信箱審核:</span><span class="sxs-lookup"><span data-stu-id="86621-361">You can turn off mailbox auditing on by default for your entire organization by running the following command in Exchange Online PowerShell:</span></span>

```
Set-OrganizationConfig -AuditDisabled $true
```

<span data-ttu-id="86621-362">根據預設, 關閉信箱審計的結果如下:</span><span class="sxs-lookup"><span data-stu-id="86621-362">Turning off mailbox auditing on by default has the following results:</span></span>

- <span data-ttu-id="86621-363">您的組織已停用信箱審核。</span><span class="sxs-lookup"><span data-stu-id="86621-363">Mailbox auditing is disabled for your organization.</span></span>

- <span data-ttu-id="86621-364">從您停用信箱審核時, 預設不會審核任何信箱動作 (即使信箱上的*AuditEnabled*屬性為**True**)。</span><span class="sxs-lookup"><span data-stu-id="86621-364">From the time you disabled mailbox auditing on by default, no mailbox actions are audited, even if auditing is enabled on a mailbox (the *AuditEnabled* property on the mailbox is **True**).</span></span>

- <span data-ttu-id="86621-365">信箱審核未啟用新信箱, 並將新的或現有的信箱上的*AuditEnabled*屬性設定為**True**將會被忽略。</span><span class="sxs-lookup"><span data-stu-id="86621-365">Mailbox auditing is not enabled for new mailboxes and setting the *AuditEnabled* property on a new or existing mailbox to **True** will be ignored.</span></span>

- <span data-ttu-id="86621-366">會忽略任何信箱審核略過的關聯設定 (使用 Set-mailboxauditbypassassociation 指令程式**設定**)。</span><span class="sxs-lookup"><span data-stu-id="86621-366">Any mailbox audit bypass association settings (configured by using the **Set-MailboxAuditBypassAssociation** cmdlet) are ignored.</span></span>

- <span data-ttu-id="86621-367">現有的信箱審計記錄會保留, 直到記錄的審核記錄保留限制到期為止。</span><span class="sxs-lookup"><span data-stu-id="86621-367">Existing mailbox audit records are retained until the audit log age limit for the the record expires.</span></span>

### <a name="turn-on-mailbox-auditing-on-by-default"></a><span data-ttu-id="86621-368">依預設開啟信箱審計</span><span class="sxs-lookup"><span data-stu-id="86621-368">Turn on mailbox auditing on by default</span></span>

<span data-ttu-id="86621-369">若要為您的組織開啟信箱審核, 請在 Exchange Online PowerShell 中執行下列命令:</span><span class="sxs-lookup"><span data-stu-id="86621-369">To turn mailbox auditing back on for your organization, run the following command in Exchange Online PowerShell:</span></span>

```
Set-OrganizationConfig -AuditDisabled $false
```

## <a name="bypass-mailbox-audit-logging"></a><span data-ttu-id="86621-370">略過信箱審核記錄</span><span class="sxs-lookup"><span data-stu-id="86621-370">Bypass mailbox audit logging</span></span>

<span data-ttu-id="86621-371">目前您的組織中開啟信箱審核時, 您無法停用特定信箱的信箱審核。</span><span class="sxs-lookup"><span data-stu-id="86621-371">Currently, you can't disable mailbox auditing for specific mailboxes when mailbox auditing on by default is turned on in your organization.</span></span> <span data-ttu-id="86621-372">例如, 會忽略將*AuditEnabled*信箱屬性設為**False** 。</span><span class="sxs-lookup"><span data-stu-id="86621-372">For example, setting the *AuditEnabled* mailbox property to **False** is ignored.</span></span>

<span data-ttu-id="86621-373">不過, 您仍然可以在 Exchange Online PowerShell 中使用**set-mailboxauditbypassassociation 指令程式**, 以防止指定使用者記錄*任何*信箱動作, 而不論動作發生的位置為何。</span><span class="sxs-lookup"><span data-stu-id="86621-373">However, you can still use the **Set-MailboxAuditBypassAssociation** cmdlet in Exchange Online PowerShell to prevent *any and all* mailbox actions by the specified users from being logged, regardless where the actions occur.</span></span> <span data-ttu-id="86621-374">例如：</span><span class="sxs-lookup"><span data-stu-id="86621-374">For example:</span></span>

- <span data-ttu-id="86621-375">略過的使用者所執行的信箱擁有者動作不會登入。</span><span class="sxs-lookup"><span data-stu-id="86621-375">Mailbox owner actions performed by the bypassed users aren't logged.</span></span>

- <span data-ttu-id="86621-376">委派使用者信箱 (包括共用信箱) 上略過的使用者所執行的動作不會被記錄。</span><span class="sxs-lookup"><span data-stu-id="86621-376">Delegate actions performed by the bypassed users on other users' mailboxes (including shared mailboxes) aren't logged.</span></span>

- <span data-ttu-id="86621-377">由略過的使用者執行的系統管理動作不會記錄。</span><span class="sxs-lookup"><span data-stu-id="86621-377">Admin actions performed by the bypassed users aren't logged.</span></span>

<span data-ttu-id="86621-378">若要略過特定使用者的信箱審核記錄, \<請\>將 mailboxidentity 為信箱取代為使用者的名稱、電子郵件地址、別名或使用者主要名稱 (username), 並執行下列命令:</span><span class="sxs-lookup"><span data-stu-id="86621-378">To bypass mailbox audit logging for a specific user, replace \<MailboxIdentity\> with the name, email address, alias, or user principal name (username) of the user and run the following command:</span></span>

```
Set-MailboxAuditBypassAssociation -Identity <MailboxIdentity> -AuditByPassEnabled $true
```

<span data-ttu-id="86621-379">若要確認是否略過指定使用者的審核, 請執行下列命令:</span><span class="sxs-lookup"><span data-stu-id="86621-379">To verify that auditing is bypassed for the specified user, run the following command:</span></span>

```
Get-MailboxAuditBypassAssociation -Identity <MailboxIdentity> | Format-List AuditByPassEnabled
```

<span data-ttu-id="86621-380">**True**值表示使用者的信箱審核記錄被略過。</span><span class="sxs-lookup"><span data-stu-id="86621-380">The value **True** indicates that mailbox audit logging is bypassed for the user.</span></span>

## <a name="more-information"></a><span data-ttu-id="86621-381">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="86621-381">More information</span></span>

- <span data-ttu-id="86621-382">依預設, 信箱審核記錄記錄會在刪除之前保留90天。</span><span class="sxs-lookup"><span data-stu-id="86621-382">By default, mailbox audit log records are retained for 90 days before they're deleted.</span></span> <span data-ttu-id="86621-383">您可以使用 Exchange Online PowerShell 中**設定信箱**指令程式上的*AuditLogAgeLimit*參數, 來變更 audit log 記錄的保留限制。</span><span class="sxs-lookup"><span data-stu-id="86621-383">You can change the age limit for audit log records by using the *AuditLogAgeLimit* parameter on the **Set-Mailbox** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="86621-384">不過, 增加此值並不會讓您在 Microsoft 365 audit 記錄檔中搜尋超過90天的事件。</span><span class="sxs-lookup"><span data-stu-id="86621-384">However, increasing this value doesn't allow you to search for events that are older than 90 days in the Microsoft 365 audit log.</span></span>

  <span data-ttu-id="86621-385">如果您增加保留時間限制, 您必須在 Exchange Online PowerShell 中使用[search-mailboxauditlog examples 指令程式](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog), 以搜尋超過90天之記錄的使用者信箱 audit 記錄檔。</span><span class="sxs-lookup"><span data-stu-id="86621-385">If you increase the age limit, you need to use the [Search-MailboxAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog) cmdlet in Exchange Online PowerShell to search the user's mailbox audit log for records that are older than 90 days.</span></span>

- <span data-ttu-id="86621-386">如果您已在信箱審核之前將信箱的*AuditLogAgeLimit*屬性變更為 [組織], 則信箱的現有審核記錄保留時間限制不會變更。</span><span class="sxs-lookup"><span data-stu-id="86621-386">If you've changed the *AuditLogAgeLimit* property for a mailbox prior to mailbox auditing on by default being turned on for organization, the mailbox's existing audit log age limit isn't changed.</span></span> <span data-ttu-id="86621-387">換句話說, 預設的信箱審核不會影響信箱審計記錄的目前保留限制。</span><span class="sxs-lookup"><span data-stu-id="86621-387">In other words, mailbox auditing on by default doesn't effect the current age limit for mailbox audit records.</span></span>

- <span data-ttu-id="86621-388">若要變更 Office 365 群組信箱上的*AuditLogAgeLimit*值, 您必須將該`-GroupMailbox`參數包含在 [**設定信箱**] 命令中。</span><span class="sxs-lookup"><span data-stu-id="86621-388">To change the *AuditLogAgeLimit* value on an Office 365 Group mailbox, you need to include the `-GroupMailbox` switch in the **Set-Mailbox** command.</span></span>

- <span data-ttu-id="86621-389">信箱 audit log 記錄會儲存在每個使用者信箱\*\* 的 [可復原的專案] 資料夾中的子資料夾 (名為 audit)。</span><span class="sxs-lookup"><span data-stu-id="86621-389">Mailbox audit log records are stored in a subfolder (named *Audits*) in the Recoverable Items folder in each user's mailbox.</span></span> <span data-ttu-id="86621-390">請記住下列有關信箱審計記錄和 [可復原的專案] 資料夾的事項:</span><span class="sxs-lookup"><span data-stu-id="86621-390">Keep the following things in mind about mailbox audit records and the Recoverable Items folder:</span></span>

  - <span data-ttu-id="86621-391">信箱審計記錄會依據 [可復原的專案] 資料夾的儲存配額來計算, 預設值為 30GB (警告配額為 20 GB)。</span><span class="sxs-lookup"><span data-stu-id="86621-391">Mailbox audit records count against the storage quota of the Recoverable Items folder, which is 30GB by default (the warning quota is 20 GB).</span></span> <span data-ttu-id="86621-392">在下列情況中, 儲存配額會自動增加為 100 GB (含 90 GB 警告配額):</span><span class="sxs-lookup"><span data-stu-id="86621-392">The storage quota is automatically increased to 100 GB (with a 90 GB warning quota) when:</span></span>

    - <span data-ttu-id="86621-393">保留在信箱上。</span><span class="sxs-lookup"><span data-stu-id="86621-393">A hold is placed on a mailbox.</span></span>

    - <span data-ttu-id="86621-394">信箱會指派給規範中心的保留原則。</span><span class="sxs-lookup"><span data-stu-id="86621-394">The mailbox is assigned to a retention policy in the Compliance Center.</span></span>

  - <span data-ttu-id="86621-395">信箱審計記錄也會依據[[可復原的專案] 資料夾的資料夾限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits)計數。</span><span class="sxs-lookup"><span data-stu-id="86621-395">Mailbox audit records also count against the [folder limit for the Recoverable Items folder](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits).</span></span> <span data-ttu-id="86621-396">[Audit] 子資料夾中最多可儲存3000000個專案 (審計記錄)。</span><span class="sxs-lookup"><span data-stu-id="86621-396">A maximum of 3 million items (audit records) can be stored in the Audits subfolder.</span></span>

    > [!NOTE]
    > <span data-ttu-id="86621-397">依預設, 信箱審核不太可能會影響儲存配額或 [可復原的專案] 資料夾的資料夾限制。</span><span class="sxs-lookup"><span data-stu-id="86621-397">It's unlikely that mailbox auditing on by default will impact the storage quota or the folder limit for the Recoverable Items folder.</span></span>

    - <span data-ttu-id="86621-398">您可以在 Exchange Online PowerShell 中執行下列命令, 以在 [可復原的專案] 資料夾的 [核查] 子資料夾中顯示專案的大小和數目:</span><span class="sxs-lookup"><span data-stu-id="86621-398">You can run the following command in Exchange Online PowerShell to display the size and number of items in the Audits subfolder in the Recoverable Items folder:</span></span>

      ```
      Get-MailboxFolderStatistics -Identity <MailboxIdentity> -FolderScope RecoverableItems | Where-Object {$_.Name -eq 'Audits'} | Format-List FolderPath,FolderSize,ItemsInFolder
      ```

    - <span data-ttu-id="86621-399">您無法直接存取 [可復原的專案] 資料夾中的審計記錄記錄;相反地, 您可以使用**search-mailboxauditlog examples 指令程式**, 或搜尋 Microsoft 365 audit log 來尋找並查看信箱審計記錄。</span><span class="sxs-lookup"><span data-stu-id="86621-399">You can't directly access an audit log record in the Recoverable Items folder; instead, you use the **Search-MailboxAuditLog** cmdlet or search the Microsoft 365 audit log to find and view mailbox audit records.</span></span>

- <span data-ttu-id="86621-400">如果信箱處於暫止狀態, 或指派給規範中心的保留原則, 則在信箱的*AuditLogAgeLimit*屬性 (預設值為90天) 內所定義的期間仍會保留 audit log 記錄。</span><span class="sxs-lookup"><span data-stu-id="86621-400">If a mailbox is placed on hold or assigned to a retention policy in the Compliance Center, audit log records are still retained for the duration that's defined by the mailbox's *AuditLogAgeLimit* property (90 days by default).</span></span> <span data-ttu-id="86621-401">若要保留長時間保留信箱的審計記錄檔, 您需要增加信箱的*AuditLogAgeLimit*值。</span><span class="sxs-lookup"><span data-stu-id="86621-401">To retain audit log records longer for mailboxes on hold, you need to increase mailbox's *AuditLogAgeLimit* value.</span></span>
