---
title: 啟用 Office 365 安全性中的封存信箱&amp;合規性中心
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
description: 使用 Office 365 安全性&amp;合規性中心，以啟用封存信箱，以支援您的組織郵件保留、 eDiscovery 和保留需求。
ms.openlocfilehash: 39cd5fd8d7991b787d95e39e4994dc9b0786522c
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341794"
---
# <a name="enable-archive-mailboxes-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="7e324-103">啟用 Office 365 安全性中的封存信箱&amp;合規性中心</span><span class="sxs-lookup"><span data-stu-id="7e324-103">Enable archive mailboxes in the Office 365 Security &amp; Compliance Center</span></span>
  
<span data-ttu-id="7e324-p101">封存 （也稱為 「 就地封存） 的 Office 365 中提供使用者額外信箱儲存空間。開啟封存信箱之後，使用者可以存取，並使用 Microsoft Outlook 和 Outlook 網頁 （原先稱為 Outlook Web App） 上的，將郵件儲存在他們的封存信箱。使用者也可以移動或複製其主要信箱和封存信箱之間的郵件。他們也可以使用 「 復原刪除的項目 」 工具，從其封存信箱中的 [可復原的項目] 資料夾復原刪除的項目。</span><span class="sxs-lookup"><span data-stu-id="7e324-p101">Archiving in Office 365 (also called In-Place Archiving) provides users with additional mailbox storage space. After you turn on archive mailboxes, users can access and store messages in their archive mailboxes by using Microsoft Outlook and Outlook on the web (formerly known as Outlook Web App). Users can also move or copy messages between their primary mailbox and their archive mailbox. They can also recover deleted items from the Recoverable Items folder in their archive mailbox by using the Recover Deleted Items tool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="7e324-p102">Office 365 提供無限制的封存儲存與自動展開封存功能數量。當自動展開封存已開啟，且然後達到使用者的封存信箱中的儲存配額時，Office 365 會自動加入額外的儲存空間。這表示，使用者將不會執行信箱儲存空間不足，並不會有任何項目最初管理後啟用封存信箱，並開啟自動展開封存為您的組織。如需詳細資訊，請參閱[在 Office 365 中的無限制封存概觀](unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="7e324-p102">Office 365 provides an unlimited amount of archive storage with the auto-expanding archiving feature. When auto-expanding archiving is turned on, and then the initial storage quota in a user's archive mailbox is reached, Office 365 automatically adds additional storage space. This means that users won't run out of mailbox storage space and you won't have to manage anything after you initially enable the archive mailbox and turn on auto-expanding archiving for your organization. For more information, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="7e324-112">開始之前</span><span class="sxs-lookup"><span data-stu-id="7e324-112">Before you begin</span></span>

<span data-ttu-id="7e324-p103">您必須獲指派 「 郵件收件者角色在 Exchange Online 來啟用或停用封存信箱。根據預設，此角色被指派給在 Exchange 系統管理中心中的**權限**] 頁面上的收件者管理與組織管理角色群組。如果您沒有看到 [**封存**] 頁面上，安全性&amp;合規性中心，要求您的系統管理員指派必要權限。</span><span class="sxs-lookup"><span data-stu-id="7e324-p103">You have to be assigned the Mail Recipients role in Exchange Online to enable or disable archive mailboxes. By default, this role is assigned to the Recipient Management and Organization Management role groups on the **Permissions** page in the Exchange admin center. If you don't see the **Archive** page in the Security &amp; Compliance Center, ask your administrator to assign you the necessary permissions.</span></span> 
  
## <a name="enable-an-archive-mailbox"></a><span data-ttu-id="7e324-116">啟用封存信箱</span><span class="sxs-lookup"><span data-stu-id="7e324-116">Enable an archive mailbox</span></span>
  
1. <span data-ttu-id="7e324-117">移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="7e324-117">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="7e324-118">使用公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="7e324-118">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="7e324-119">在左窗格中的安全性&amp;合規性中心，按一下 [**資料控管** \> **封存**。</span><span class="sxs-lookup"><span data-stu-id="7e324-119">In the left pane of the Security &amp; Compliance Center, click **Data governance** \> **Archive**.</span></span>
    
    <span data-ttu-id="7e324-p104">會顯示 [**封存**] 頁面。**封存信箱**] 欄位會指出是否啟用或停用每個使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="7e324-p104">The **Archive** page is displayed. The **Archive mailbox** column indicates whether an archive mailbox is enabled or disabled for each user.</span></span> 
    
4. <span data-ttu-id="7e324-122">在信箱清單中，選取要為其啟用封存信箱的使用者。</span><span class="sxs-lookup"><span data-stu-id="7e324-122">In the list of mailboxes, select the user that you want to enable the archive mailbox for.</span></span>
    
    ![若要啟用封存信箱所選使用者的詳細資料窗格中按一下 [啟用](media/8b53cdec-d5c9-4c28-af11-611f95c37b34.png)
  
5. <span data-ttu-id="7e324-124">在所選使用者詳細資料窗格中，按一下 [**啟用**]。</span><span class="sxs-lookup"><span data-stu-id="7e324-124">In the details pane for the selected user, click **Enable**.</span></span> 
    
    <span data-ttu-id="7e324-p105">說，是否您啟用封存信箱，在使用者的信箱會超過封存原則指派給信箱的項目要移至新的封存信箱會顯示警告。預設封存原則指派給 Exchange Online 信箱的保留原則的一部分，將項目移至封存信箱兩年後的項目已傳遞至信箱或使用者所建立的日期。如需詳細資訊，請參閱這篇文章中的**詳細資訊**一節。</span><span class="sxs-lookup"><span data-stu-id="7e324-p105">A warning is displayed saying that if you enable the archive mailbox, items in the user's mailbox that are older than the archiving policy assigned to the mailbox will be moved to the new archive mailbox. The default archive policy that is part of the retention policy assigned to Exchange Online mailboxes moves items to the archive mailbox two years after the date the item was delivered to the mailbox or created by the user. For more information, see the **More info** section in this article.</span></span> 
    
6. <span data-ttu-id="7e324-128">按一下 [ **]** 以啟用封存信箱。</span><span class="sxs-lookup"><span data-stu-id="7e324-128">Click **Yes** to enable the archive mailbox.</span></span> 
    
    <span data-ttu-id="7e324-p106">可能需要一些時間才能建立封存信箱。建立時，**封存信箱： 啟用**會顯示在詳細資料窗格中選取的使用者。您可能需要按一下 [**重新整理**![重新整理圖示](media/O365-MDM-Policy-RefreshIcon.gif)以更新詳細資料窗格中的資訊。</span><span class="sxs-lookup"><span data-stu-id="7e324-p106">It might take a few moments to create the archive mailbox. When it's created, **Archive mailbox: enabled** is displayed in the details pane for the selected user. You might have to click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
> [!TIP]
> <span data-ttu-id="7e324-p107">您可以也大量啟用封存信箱選取具有多個使用者停用封存信箱 （使用 Shift 或 Ctrl 鍵）。選取多個信箱後, 按一下 [詳細資料窗格中的 [**啟用**]。</span><span class="sxs-lookup"><span data-stu-id="7e324-p107">You can also bulk-enable archive mailboxes by selecting multiple users with disabled archive mailboxes (use the Shift or Ctrl keys). After selecting multiple mailboxes, click **Enable** in the details pane.</span></span> 
  
## <a name="disable-an-archive-mailbox"></a><span data-ttu-id="7e324-134">停用封存信箱</span><span class="sxs-lookup"><span data-stu-id="7e324-134">Disable an archive mailbox</span></span>
  
<span data-ttu-id="7e324-p108">您也可以使用 [**封存**] 頁面上，安全性&amp;合規性中心，以停用使用者的封存信箱。停用封存信箱之後，您可以重新連線至使用者的主要信箱的停用它的 30 天內。在此情況下，就會還原封存信箱的原始內容。30 天後，原始的封存信箱的內容會永久刪除，而且無法復原。因此如果您重新啟用封存超過 30 天之後停用它，會建立新的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="7e324-p108">You can also use the **Archive** page in the Security &amp; Compliance Center to disable a user's archive mailbox. After you disable an archive mailbox, you can reconnect it to the user's primary mailbox within 30 days of disabling it. In this case, the original contents of the archive mailbox are restored. After 30 days, the contents of the original archive mailbox are permanently deleted and can't be recovered. So if you re-enable the archive more than 30 days after disabling it, a new archive mailbox is created.</span></span> 
  
<span data-ttu-id="7e324-p109">請注意，預設封存原則指派給使用者的信箱移至封存信箱的項目兩年的日期之後的項目會傳遞。如果您停用使用者的封存信箱，將會對信箱項目採取任何動作，他們會一直保留在使用者的主要信箱。</span><span class="sxs-lookup"><span data-stu-id="7e324-p109">Note that the default archive policy assigned to users' mailboxes moves items to the archive mailbox two years after the date the item is delivered. If you disable a user's archive mailbox, no action will be taken on mailbox items and they will remain in the user's primary mailbox.</span></span>
  
<span data-ttu-id="7e324-142">若要停用封存信箱：</span><span class="sxs-lookup"><span data-stu-id="7e324-142">To disable an archive mailbox:</span></span>
  
1. <span data-ttu-id="7e324-143">移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="7e324-143">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="7e324-144">使用公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="7e324-144">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="7e324-145">在左窗格中的安全性&amp;合規性中心，按一下 [**資料控管** \> **封存**。</span><span class="sxs-lookup"><span data-stu-id="7e324-145">In the left pane of the Security &amp; Compliance Center, click **Data governance** \> **Archive**.</span></span>
    
    <span data-ttu-id="7e324-p110">會顯示 [**封存**] 頁面。**封存信箱**] 欄位會指出是否啟用或停用每個使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="7e324-p110">The **Archive** page is displayed. The **Archive mailbox** column indicates whether an archive mailbox is enabled or disabled for each user.</span></span> 
    
4. <span data-ttu-id="7e324-148">在信箱清單中，選取要為其停用封存信箱的使用者。</span><span class="sxs-lookup"><span data-stu-id="7e324-148">In the list of mailboxes, select the user that you want to disable the archive mailbox for.</span></span>
    
5. <span data-ttu-id="7e324-149">在 [詳細資料] 窗格中，按一下 [**停用**。</span><span class="sxs-lookup"><span data-stu-id="7e324-149">In the details pane, click **Disable**.</span></span> 
    
    <span data-ttu-id="7e324-150">會顯示警告訊息，指出您有 30 天的時間可以重新啟用封存信箱，並，30 天後，在封存中的所有資訊將會永久都刪除。</span><span class="sxs-lookup"><span data-stu-id="7e324-150">A warning message is displayed saying that you'll have 30 days to re-enable the archive mailbox, and that after 30 days, all information in the archive will be permanently deleted.</span></span> 
    
6. <span data-ttu-id="7e324-151">按一下 [ **]** 以停用封存信箱。</span><span class="sxs-lookup"><span data-stu-id="7e324-151">Click **Yes** to disable the archive mailbox.</span></span> 
    
    <span data-ttu-id="7e324-p111">它可能需要幾分鐘才會停用封存信箱。停用它時，**封存信箱： 停用**會顯示在詳細資料窗格中選取的使用者。您可能需要按一下 [**重新整理**![重新整理圖示](media/O365-MDM-Policy-RefreshIcon.gif)以更新詳細資料窗格中的資訊。</span><span class="sxs-lookup"><span data-stu-id="7e324-p111">It might take a few moments to disable the archive mailbox. When it's disabled, **Archive mailbox: disabled** is displayed in the details pane for the selected user. You might have to click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
> [!TIP]
> <span data-ttu-id="7e324-p112">您可以也大量停用來選取與已啟用的封存信箱 （使用 Shift 或 Ctrl 鍵） 的多個使用者封存信箱。選取多個信箱後, 按一下 [**停用**詳細資料窗格中。</span><span class="sxs-lookup"><span data-stu-id="7e324-p112">You can also bulk-disable archive mailboxes by selecting multiple users with enabled archive mailboxes (use the Shift or Ctrl keys). After selecting multiple mailboxes, click **Disable** in the details pane.</span></span> 
  
## <a name="use-exchange-online-powershell-to-enable-or-disable-archive-mailboxes"></a><span data-ttu-id="7e324-157">使用 Exchange Online PowerShell 來啟用或停用封存信箱</span><span class="sxs-lookup"><span data-stu-id="7e324-157">Use Exchange Online PowerShell to enable or disable archive mailboxes</span></span>

<span data-ttu-id="7e324-p113">您也可以使用 Exchange Online PowerShell 來啟用封存信箱。若要使用 PowerShell 的主要原因是，您可以快速貴組織中啟用所有使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="7e324-p113">You can also use Exchange Online PowerShell to enable archive mailboxes. The primary reason to use PowerShell is that you can quickly enable the archive mailbox for all users in your organization.</span></span>

<span data-ttu-id="7e324-p114">第一個步驟是連線至 Exchange Online PowerShell。如需相關指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。</span><span class="sxs-lookup"><span data-stu-id="7e324-p114">The first step is to connect to Exchange Online PowerShell. For instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="7e324-162">在您連線至 Exchange Online 之後，您可以在以下小節以啟用或停用封存信箱中執行命令。</span><span class="sxs-lookup"><span data-stu-id="7e324-162">After you're connected to Exchange Online, you can run the commands in the following sections to enable or disable archive mailboxes.</span></span>

### <a name="enable-archive-mailboxes"></a><span data-ttu-id="7e324-163">啟用封存信箱</span><span class="sxs-lookup"><span data-stu-id="7e324-163">Enable archive mailboxes</span></span>

<span data-ttu-id="7e324-164">執行下列命令，以啟用單一使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="7e324-164">Run the following command to enable the archive mailbox for a single user.</span></span>
    
  ```
  Enable-Mailbox -Identity <username> -Archive
  ```

<span data-ttu-id="7e324-165">執行下列命令，以啟用的組織 （其封存信箱目前未啟用） 中的所有使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="7e324-165">Run the following command to enable the archive mailbox for all users in your organization (whose archive mailbox is currently not enabled).</span></span>
    
  ```
  Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
  ```
  
### <a name="disable-archive-mailboxes"></a><span data-ttu-id="7e324-166">停用封存信箱</span><span class="sxs-lookup"><span data-stu-id="7e324-166">Disable archive mailboxes</span></span>

<span data-ttu-id="7e324-167">執行下列命令，以停用單一使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="7e324-167">Run the following command to disable the archive mailbox for a single user.</span></span>
    
  ```
  Disable-Mailbox -Identity <username> -Archive
  ```

<span data-ttu-id="7e324-168">執行下列命令，以停用的組織 （目前已啟用封存信箱） 中的所有使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="7e324-168">Run the following command to disable the archive mailbox for all users in your organization (whose archive mailbox is currently enabled).</span></span>
    
  ```
  Get-Mailbox -Filter {ArchiveStatus -Eq "Active" -AND RecipientTypeDetails -eq "UserMailbox"} | Disable-Mailbox -Archive
  ```

## <a name="more-information"></a><span data-ttu-id="7e324-169">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="7e324-169">More information</span></span>
  
- <span data-ttu-id="7e324-p115">封存信箱幫助您和您的使用者以符合您的組織保留、 eDiscovery 和保留需求。例如，您可以使用您組織的 Exchange 保留原則，將信箱內容移至使用者的封存信箱。當您使用 「 內容搜尋 」 工具安全性&amp;也可搜尋合規性中心，以搜尋特定的內容，使用者的封存信箱的使用者的信箱。然後放置訴訟暫止狀態或 Office 365 保留原則套用至使用者的信箱時，也會保留在封存信箱中的項目。</span><span class="sxs-lookup"><span data-stu-id="7e324-p115">Archive mailboxes help you and your users to meet your organization's retention, eDiscovery, and hold requirements. For example, you can use your organization's Exchange retention policy to move mailbox content to users' archive mailbox. When you use the Content Search tool in the Security &amp; Compliance Center to search a user's mailbox for specific content, the user's archive mailbox will also be searched. And, when you place a Litigation Hold or apply an Office 365 retention policy to a user's mailbox, items in the archive mailbox are also retained.</span></span>
  
- <span data-ttu-id="7e324-p116">啟用封存信箱時，使用者可以將郵件儲存在其封存信箱。使用者可以使用 Microsoft Outlook 和網頁型 Outlook 來存取他們的封存信箱。只要使用這些用戶端應用程式，使用者可以檢視其封存信箱中的郵件和移動或複製其主要信箱和封存信箱之間的郵件。使用者可以也復原刪除的項目從其封存信箱中的 [可復原的項目] 資料夾復原刪除的項目 」 工具。</span><span class="sxs-lookup"><span data-stu-id="7e324-p116">When an archive mailbox is enabled, users can store messages in their archive mailbox. Users can access their archive mailboxes by using Microsoft Outlook and Outlook on the web. Using either of these client applications, users can view messages in their archive mailbox and move or copy messages between their primary mailbox and their archive mailbox. Users can also recover deleted items from the Recoverable Items folder in their archive mailbox by using the Recover Deleted Items tool.</span></span> 
  
- <span data-ttu-id="7e324-p117">在啟用信箱的封存之後, 您的組織可以利用之預設 Exchange 保留原則 （也稱為 「 通訊記錄管理 」 或 「 MRM 原則 」） 會自動指派給每個信箱。啟用封存信箱時，預設 Exchange 保留原則自動會執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="7e324-p117">After archive mailboxes are enabled, your organization can take advantage of the default Exchange retention policy (also called Messaging Records Management or MRM policy) that is automatically assigned to every mailbox. When an archive mailbox is enabled, the default Exchange retention policy automatically does the following:</span></span> 
  
    - <span data-ttu-id="7e324-180">將使用者主要信箱中兩年以上的郵件移到其封存信箱。</span><span class="sxs-lookup"><span data-stu-id="7e324-180">Moves items that are two years or older from a user's primary mailbox to their archive mailbox.</span></span> 
    
    - <span data-ttu-id="7e324-181">將使用者主要信箱的 [可復原的項目] 資料夾中 14 天以上的郵件移至其封存信箱的 [可復原的項目] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="7e324-181">Moves items that are 14 days or older from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in their archive mailbox.</span></span>
    
- <span data-ttu-id="7e324-182">如需有關封存信箱和 Exchange 保留原則的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="7e324-182">For more information about archive mailboxes and Exchange retention policies, see:</span></span>
    
  - [<span data-ttu-id="7e324-183">保留標記和保留原則</span><span class="sxs-lookup"><span data-stu-id="7e324-183">Retention tags and retention policies</span></span>](https://go.microsoft.com/fwlink/?LinkId=404424)
    
  - [<span data-ttu-id="7e324-184">預設保留原則在 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7e324-184">Default Retention Policy in Exchange Online </span></span>](https://go.microsoft.com/fwlink/?linkid=839418)
    
  - [<span data-ttu-id="7e324-185">設定 Office 365 組織中信箱的封存和刪除原則</span><span class="sxs-lookup"><span data-stu-id="7e324-185">Set up an archive and deletion policy for mailboxes in your Office 365 organization</span></span>](set-up-an-archive-and-deletion-policy-for-mailboxes.md)
