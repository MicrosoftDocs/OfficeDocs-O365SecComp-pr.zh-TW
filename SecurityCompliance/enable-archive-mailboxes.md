---
title: 啟用封存信箱在 Office 365 安全性&amp;規範中心
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ArchivingHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 268a109e-7843-405b-bb3d-b9393b2342ce
description: 使用 Office 365 安全性&amp;規範中心啟用封存信箱來支援您的組織訊息保留 eDiscovery 和保留需求。
ms.openlocfilehash: 763097925ed0910fe9a66e5c556b8a2995df74e6
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296056"
---
# <a name="enable-archive-mailboxes-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="9159d-103">啟用封存信箱在 Office 365 安全性&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="9159d-103">Enable archive mailboxes in the Office 365 Security &amp; Compliance Center</span></span>
  
<span data-ttu-id="9159d-p101">Office 365 （也稱為就地封存） 中的封存提供使用者與其他信箱的儲存空間。開啟封存信箱之後，使用者可以存取和使用 Microsoft Outlook 和 Outlook web （前身為 Outlook Web App） 上的儲存其封存信箱中的郵件。使用者也可以移動或複製主要信箱和封存信箱之間的郵件。他們也可以從其封存信箱中的 [可復原的項目] 資料夾復原刪除的項目使用復原刪除的項目工具。</span><span class="sxs-lookup"><span data-stu-id="9159d-p101">Archiving in Office 365 (also called In-Place Archiving) provides users with additional mailbox storage space. After you turn on archive mailboxes, users can access and store messages in their archive mailboxes by using Microsoft Outlook and Outlook on the web (formerly known as Outlook Web App). Users can also move or copy messages between their primary mailbox and their archive mailbox. They can also recover deleted items from the Recoverable Items folder in their archive mailbox by using the Recover Deleted Items tool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="9159d-p102">Office 365 提供封存存放區與 「 自動展開的封存功能的數量不受限制。如果自動展開封存已開啟，然後到達使用者的封存信箱中的初始儲存配額，Office 365 會自動新增額外儲存空間。這表示使用者不會執行移出信箱的儲存空間和您不必最初管理的任何項目之後啟用封存信箱並開啟自動展開您的組織的封存。如需詳細資訊，請參閱 ＜ [Overview of Office 365 中沒有限制之封存](unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="9159d-p102">Office 365 provides an unlimited amount of archive storage with the auto-expanding archiving feature. When auto-expanding archiving is turned on, and then the initial storage quota in a user's archive mailbox is reached, Office 365 automatically adds additional storage space. This means that users won't run out of mailbox storage space and you won't have to manage anything after you initially enable the archive mailbox and turn on auto-expanding archiving for your organization. For more information, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="9159d-112">開始之前</span><span class="sxs-lookup"><span data-stu-id="9159d-112">Before you begin</span></span>

<span data-ttu-id="9159d-p103">您必須指派 「 郵件收件者 」 角色在 Exchange Online 啟用或停用封存信箱。根據預設，此角色指派給 Exchange 系統管理中心的 [**權限**] 頁面上的收件者管理及組織管理角色群組。如果您沒有看到 [**封存**] 頁面上的 [安全性]&amp;規範中心，詢問您要指派必要權限的管理員。</span><span class="sxs-lookup"><span data-stu-id="9159d-p103">You have to be assigned the Mail Recipients role in Exchange Online to enable or disable archive mailboxes. By default, this role is assigned to the Recipient Management and Organization Management role groups on the **Permissions** page in the Exchange admin center. If you don't see the **Archive** page in the Security &amp; Compliance Center, ask your administrator to assign you the necessary permissions.</span></span> 
  
## <a name="enable-an-archive-mailbox"></a><span data-ttu-id="9159d-116">啟用封存信箱</span><span class="sxs-lookup"><span data-stu-id="9159d-116">Enable an archive mailbox</span></span>
  
1. <span data-ttu-id="9159d-117">移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="9159d-117">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="9159d-118">使用公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="9159d-118">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="9159d-119">在 [安全性] 的左窗格中&amp;規範中心，按一下 [**資料控管** \> **封存**。</span><span class="sxs-lookup"><span data-stu-id="9159d-119">In the left pane of the Security &amp; Compliance Center, click **Data governance** \> **Archive**.</span></span>
    
    <span data-ttu-id="9159d-p104">會顯示 [**封存**] 頁面。**封存信箱**] 欄會指出是否啟用或停用每個使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="9159d-p104">The **Archive** page is displayed. The **Archive mailbox** column indicates whether an archive mailbox is enabled or disabled for each user.</span></span> 
    
4. <span data-ttu-id="9159d-122">在信箱清單中，選取要為其啟用封存信箱的使用者。</span><span class="sxs-lookup"><span data-stu-id="9159d-122">In the list of mailboxes, select the user that you want to enable the archive mailbox for.</span></span>
    
    ![若要啟用封存信箱所選使用者的詳細資料窗格中按一下 [啟用]](media/8b53cdec-d5c9-4c28-af11-611f95c37b34.png)
  
5. <span data-ttu-id="9159d-124">在所選使用者的詳細資料窗格中，按一下 [**啟用**]。</span><span class="sxs-lookup"><span data-stu-id="9159d-124">In the details pane for the selected user, click **Enable**.</span></span> 
    
    <span data-ttu-id="9159d-p105">顯示一則警告訊息表示是否您啟用封存信箱，在使用者的信箱超過指派給信箱的封存原則的項目要移至新的封存信箱。預設封存原則指派給 Exchange Online 信箱的保留原則屬於將項目移至封存信箱項目已傳遞至信箱或使用者所建立的日期之後的兩個年度。如需詳細資訊，請參閱本文中的 [**詳細資訊**] 區段。</span><span class="sxs-lookup"><span data-stu-id="9159d-p105">A warning is displayed saying that if you enable the archive mailbox, items in the user's mailbox that are older than the archiving policy assigned to the mailbox will be moved to the new archive mailbox. The default archive policy that is part of the retention policy assigned to Exchange Online mailboxes moves items to the archive mailbox two years after the date the item was delivered to the mailbox or created by the user. For more information, see the **More info** section in this article.</span></span> 
    
6. <span data-ttu-id="9159d-128">按一下 [**是]** 以啟用封存信箱。</span><span class="sxs-lookup"><span data-stu-id="9159d-128">Click **Yes** to enable the archive mailbox.</span></span> 
    
    <span data-ttu-id="9159d-p106">可能需要一些時間建立封存信箱。建立、 後**封存信箱： 已啟用**會顯示所選使用者的詳細資料] 窗格中。您可能必須按一下 [**重新整理**![重新整理] 圖示](media/O365-MDM-Policy-RefreshIcon.gif)要更新的詳細資料窗格中的資訊。</span><span class="sxs-lookup"><span data-stu-id="9159d-p106">It might take a few moments to create the archive mailbox. When it's created, **Archive mailbox: enabled** is displayed in the details pane for the selected user. You might have to click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
> [!TIP]
> <span data-ttu-id="9159d-p107">您可以也大量-啟用封存信箱中選取多位使用者與停用封存信箱 （使用 shift 鍵或 Ctrl 鍵）。選取多個信箱、 之後按一下 [詳細資料窗格中的 [**啟用**]。</span><span class="sxs-lookup"><span data-stu-id="9159d-p107">You can also bulk-enable archive mailboxes by selecting multiple users with disabled archive mailboxes (use the Shift or Ctrl keys). After selecting multiple mailboxes, click **Enable** in the details pane.</span></span> 
  
## <a name="disable-an-archive-mailbox"></a><span data-ttu-id="9159d-134">停用封存信箱</span><span class="sxs-lookup"><span data-stu-id="9159d-134">Disable an archive mailbox</span></span>
  
<span data-ttu-id="9159d-p108">您也可以使用 [**封存**] 頁面上的 [安全性]&amp;規範中心來停用使用者的封存信箱。停用封存信箱後，您可以將其重新連結至使用者的主要信箱停用它的 30 天內。在此例中，會還原封存信箱的原始內容。30 天後原始的封存信箱的內容會永久刪除和無法復原。因此，如果您重新啟用封存超過 30 天後停用它，會建立新的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="9159d-p108">You can also use the **Archive** page in the Security &amp; Compliance Center to disable a user's archive mailbox. After you disable an archive mailbox, you can reconnect it to the user's primary mailbox within 30 days of disabling it. In this case, the original contents of the archive mailbox are restored. After 30 days, the contents of the original archive mailbox are permanently deleted and can't be recovered. So if you re-enable the archive more than 30 days after disabling it, a new archive mailbox is created.</span></span> 
  
<span data-ttu-id="9159d-p109">請注意預設封存原則指派給使用者的信箱移至封存信箱的項目日期之後的兩個年度項目被傳遞。如果您停用使用者的封存信箱，信箱項目將會採取任何動作與他們將保留於使用者的主要信箱。</span><span class="sxs-lookup"><span data-stu-id="9159d-p109">Note that the default archive policy assigned to users' mailboxes moves items to the archive mailbox two years after the date the item is delivered. If you disable a user's archive mailbox, no action will be taken on mailbox items and they will remain in the user's primary mailbox.</span></span>
  
<span data-ttu-id="9159d-142">若要停用封存信箱：</span><span class="sxs-lookup"><span data-stu-id="9159d-142">To disable an archive mailbox:</span></span>
  
1. <span data-ttu-id="9159d-143">移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="9159d-143">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="9159d-144">使用公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="9159d-144">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="9159d-145">在 [安全性] 的左窗格中&amp;規範中心，按一下 [**資料控管** \> **封存**。</span><span class="sxs-lookup"><span data-stu-id="9159d-145">In the left pane of the Security &amp; Compliance Center, click **Data governance** \> **Archive**.</span></span>
    
    <span data-ttu-id="9159d-p110">會顯示 [**封存**] 頁面。**封存信箱**] 欄會指出是否啟用或停用每個使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="9159d-p110">The **Archive** page is displayed. The **Archive mailbox** column indicates whether an archive mailbox is enabled or disabled for each user.</span></span> 
    
4. <span data-ttu-id="9159d-148">在信箱清單中，選取要為其停用封存信箱的使用者。</span><span class="sxs-lookup"><span data-stu-id="9159d-148">In the list of mailboxes, select the user that you want to disable the archive mailbox for.</span></span>
    
5. <span data-ttu-id="9159d-149">在 [詳細資料] 窗格中，按一下 [**停用**]。</span><span class="sxs-lookup"><span data-stu-id="9159d-149">In the details pane, click **Disable**.</span></span> 
    
    <span data-ttu-id="9159d-150">警告訊息會顯示預警您必須重新啟用封存信箱的 30 天的 30 天後封存中的所有資訊會永久都刪除。</span><span class="sxs-lookup"><span data-stu-id="9159d-150">A warning message is displayed saying that you'll have 30 days to re-enable the archive mailbox, and that after 30 days, all information in the archive will be permanently deleted.</span></span> 
    
6. <span data-ttu-id="9159d-151">按一下 [**是]** 以停用封存信箱。</span><span class="sxs-lookup"><span data-stu-id="9159d-151">Click **Yes** to disable the archive mailbox.</span></span> 
    
    <span data-ttu-id="9159d-p111">可能需要一些時間來停用封存信箱。當停用時，**封存信箱： 已停用**會顯示所選使用者的詳細資料] 窗格中。您可能必須按一下 [**重新整理**![重新整理] 圖示](media/O365-MDM-Policy-RefreshIcon.gif)要更新的詳細資料窗格中的資訊。</span><span class="sxs-lookup"><span data-stu-id="9159d-p111">It might take a few moments to disable the archive mailbox. When it's disabled, **Archive mailbox: disabled** is displayed in the details pane for the selected user. You might have to click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
> [!TIP]
> <span data-ttu-id="9159d-p112">您可以也大量-停用封存信箱中選取多位使用者以啟用的封存信箱 （使用 shift 鍵或 Ctrl 鍵）。選取多個信箱、 之後按一下 [詳細資料窗格中**停用**。</span><span class="sxs-lookup"><span data-stu-id="9159d-p112">You can also bulk-disable archive mailboxes by selecting multiple users with enabled archive mailboxes (use the Shift or Ctrl keys). After selecting multiple mailboxes, click **Disable** in the details pane.</span></span> 
  
## <a name="use-exchange-online-powershell-to-enable-or-disable-archive-mailboxes"></a><span data-ttu-id="9159d-157">使用 Exchange Online PowerShell 來啟用或停用封存信箱</span><span class="sxs-lookup"><span data-stu-id="9159d-157">Use Exchange Online PowerShell to enable or disable archive mailboxes</span></span>

<span data-ttu-id="9159d-p113">您也可以使用 Exchange Online PowerShell 啟用封存信箱。若要使用 PowerShell 的主要原因是您快速可以啟用封存信箱的所有使用者在組織中。</span><span class="sxs-lookup"><span data-stu-id="9159d-p113">You can also use Exchange Online PowerShell to enable archive mailboxes. The primary reason to use PowerShell is that you can quickly enable the archive mailbox for all users in your organization.</span></span>

<span data-ttu-id="9159d-p114">第一個步驟是連線至 Exchange Online PowerShell。指示，請參閱[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="9159d-p114">The first step is to connect to Exchange Online PowerShell. For instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="9159d-162">您連線至 Exchange Online 後，您可以執行下列各節中啟用或停用封存信箱的命令。</span><span class="sxs-lookup"><span data-stu-id="9159d-162">After you're connected to Exchange Online, you can run the commands in the following sections to enable or disable archive mailboxes.</span></span>

### <a name="enable-archive-mailboxes"></a><span data-ttu-id="9159d-163">啟用封存信箱</span><span class="sxs-lookup"><span data-stu-id="9159d-163">Enable archive mailboxes</span></span>

<span data-ttu-id="9159d-164">執行下列命令以啟用單一使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="9159d-164">Run the following command to enable the archive mailbox for a single user.</span></span>
    
  ```
  Enable-Mailbox -Identity <username> -Archive
  ```

<span data-ttu-id="9159d-165">執行下列命令以啟用 （封存信箱目前未啟用） 您組織中的所有使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="9159d-165">Run the following command to enable the archive mailbox for all users in your organization (whose archive mailbox is currently not enabled).</span></span>
    
  ```
  Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
  ```
  
### <a name="disable-archive-mailboxes"></a><span data-ttu-id="9159d-166">停用封存信箱</span><span class="sxs-lookup"><span data-stu-id="9159d-166">Disable archive mailboxes</span></span>

<span data-ttu-id="9159d-167">執行下列命令以停用單一使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="9159d-167">Run the following command to disable the archive mailbox for a single user.</span></span>
    
  ```
  Disable-Mailbox -Identity <username> -Archive
  ```

<span data-ttu-id="9159d-168">執行下列命令以停用 （目前啟用封存信箱） 您組織中的所有使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="9159d-168">Run the following command to disable the archive mailbox for all users in your organization (whose archive mailbox is currently enabled).</span></span>
    
  ```
  Get-Mailbox -Filter {ArchiveStatus -Eq "Active" -AND RecipientTypeDetails -eq "UserMailbox"} | Disable-Mailbox -Archive
  ```

## <a name="more-information"></a><span data-ttu-id="9159d-169">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="9159d-169">More information</span></span>
  
- <span data-ttu-id="9159d-p115">封存信箱協助您和使用者以符合您的組織保留 eDiscovery 和保留需求。例如，您可用於您組織的 Exchange 保留原則信箱內容移至使用者的封存信箱。當您使用 「 內容搜尋工具安全性&amp;也可搜尋規範中心來搜尋特定的內容、 使用者的封存信箱的使用者的信箱。並放置訴訟暫止狀態或 Office 365 保留原則套用至使用者的信箱、 時也會保留在封存信箱中的項目。</span><span class="sxs-lookup"><span data-stu-id="9159d-p115">Archive mailboxes help you and your users to meet your organization's retention, eDiscovery, and hold requirements. For example, you can use your organization's Exchange retention policy to move mailbox content to users' archive mailbox. When you use the Content Search tool in the Security &amp; Compliance Center to search a user's mailbox for specific content, the user's archive mailbox will also be searched. And, when you place a Litigation Hold or apply an Office 365 retention policy to a user's mailbox, items in the archive mailbox are also retained.</span></span>
  
- <span data-ttu-id="9159d-p116">啟用封存信箱時，使用者可以封存信箱中儲存的郵件。使用者可以使用 Microsoft Outlook 與 web 上的 Outlook 來存取封存信箱。使用下列任一這些用戶端應用程式，使用者可以檢視他們的封存信箱中的郵件及移動或複製主要信箱和封存信箱之間的郵件。使用者可以復原刪除的項目從其封存信箱中的 [可復原的項目] 資料夾使用復原刪除的項目工具。</span><span class="sxs-lookup"><span data-stu-id="9159d-p116">When an archive mailbox is enabled, users can store messages in their archive mailbox. Users can access their archive mailboxes by using Microsoft Outlook and Outlook on the web. Using either of these client applications, users can view messages in their archive mailbox and move or copy messages between their primary mailbox and their archive mailbox. Users can also recover deleted items from the Recoverable Items folder in their archive mailbox by using the Recover Deleted Items tool.</span></span> 
  
- <span data-ttu-id="9159d-p117">啟用信箱的封存之後, 您的組織可以利用預設 Exchange 保留原則的 （也稱為 「 郵件記錄管理或 MRM 原則 」） 會自動指派給每個信箱。啟用封存信箱時，預設 Exchange 保留原則會自動執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="9159d-p117">After archive mailboxes are enabled, your organization can take advantage of the default Exchange retention policy (also called Messaging Records Management or MRM policy) that is automatically assigned to every mailbox. When an archive mailbox is enabled, the default Exchange retention policy automatically does the following:</span></span> 
  
    - <span data-ttu-id="9159d-180">將使用者主要信箱中兩年以上的郵件移到其封存信箱。</span><span class="sxs-lookup"><span data-stu-id="9159d-180">Moves items that are two years or older from a user's primary mailbox to their archive mailbox.</span></span> 
    
    - <span data-ttu-id="9159d-181">將使用者主要信箱的 [可復原的項目] 資料夾中 14 天以上的郵件移至其封存信箱的 [可復原的項目] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="9159d-181">Moves items that are 14 days or older from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in their archive mailbox.</span></span>
    
- <span data-ttu-id="9159d-182">如需封存信箱及 Exchange 保留原則的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="9159d-182">For more information about archive mailboxes and Exchange retention policies, see:</span></span>
  
    
  - [<span data-ttu-id="9159d-183">保留標記和保留原則</span><span class="sxs-lookup"><span data-stu-id="9159d-183">Retention tags and retention policies</span></span>](https://go.microsoft.com/fwlink/?LinkId=404424)
    
  - [<span data-ttu-id="9159d-184">預設的保留原則 in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9159d-184">Default Retention Policy in Exchange Online </span></span>](https://go.microsoft.com/fwlink/?linkid=839418)
    
  - [<span data-ttu-id="9159d-185">設定 Office 365 組織中信箱的封存及刪除原則</span><span class="sxs-lookup"><span data-stu-id="9159d-185">Set up an archive and deletion policy for mailboxes in your Office 365 organization</span></span>](set-up-an-archive-and-deletion-policy-for-mailboxes.md)
