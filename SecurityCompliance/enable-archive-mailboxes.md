---
title: 在安全性 & 規範中心啟用封存信箱
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
description: 使用安全性 & 在 Office 365 規範中心啟用封存信箱以支援您的組織郵件保留、 eDiscovery 和保留需求。
ms.openlocfilehash: d363943910d970576976d8386196b450dd5694f3
ms.sourcegitcommit: f0e3c9de0b545081a4d264f74559b941f6c71410
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2019
ms.locfileid: "31958304"
---
# <a name="enable-archive-mailboxes-in-the-security--compliance-center"></a><span data-ttu-id="eaf27-103">在安全性 & 規範中心啟用封存信箱</span><span class="sxs-lookup"><span data-stu-id="eaf27-103">Enable archive mailboxes in the Security & Compliance Center</span></span>
  
<span data-ttu-id="eaf27-104">封存 （也稱為 「 就地封存） 的 Office 365 中提供使用者額外信箱儲存空間。</span><span class="sxs-lookup"><span data-stu-id="eaf27-104">Archiving in Office 365 (also called In-Place Archiving) provides users with additional mailbox storage space.</span></span> <span data-ttu-id="eaf27-105">開啟封存信箱之後，使用者可以存取，並使用 Microsoft Outlook 和 Outlook 網頁 （原先稱為 Outlook Web App） 上的，將郵件儲存在他們的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="eaf27-105">After you turn on archive mailboxes, users can access and store messages in their archive mailboxes by using Microsoft Outlook and Outlook on the web (formerly known as Outlook Web App).</span></span> <span data-ttu-id="eaf27-106">使用者也可以移動或複製其主要信箱和封存信箱之間的郵件。</span><span class="sxs-lookup"><span data-stu-id="eaf27-106">Users can also move or copy messages between their primary mailbox and their archive mailbox.</span></span> <span data-ttu-id="eaf27-107">他們也可以使用 「 復原刪除的項目 」 工具，從其封存信箱中的 [可復原的項目] 資料夾復原刪除的項目。</span><span class="sxs-lookup"><span data-stu-id="eaf27-107">They can also recover deleted items from the Recoverable Items folder in their archive mailbox by using the Recover Deleted Items tool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="eaf27-108">Office 365 提供無限制的封存儲存與自動展開封存功能數量。</span><span class="sxs-lookup"><span data-stu-id="eaf27-108">Office 365 provides an unlimited amount of archive storage with the auto-expanding archiving feature.</span></span> <span data-ttu-id="eaf27-109">當自動展開封存已開啟，且然後達到使用者的封存信箱中的儲存配額時，Office 365 會自動加入額外的儲存空間。</span><span class="sxs-lookup"><span data-stu-id="eaf27-109">When auto-expanding archiving is turned on, and then the initial storage quota in a user's archive mailbox is reached, Office 365 automatically adds additional storage space.</span></span> <span data-ttu-id="eaf27-110">這表示，使用者將不會執行信箱儲存空間不足，並不會有任何項目最初管理後啟用封存信箱，並開啟自動展開封存為您的組織。</span><span class="sxs-lookup"><span data-stu-id="eaf27-110">This means that users won't run out of mailbox storage space and you won't have to manage anything after you initially enable the archive mailbox and turn on auto-expanding archiving for your organization.</span></span> <span data-ttu-id="eaf27-111">如需詳細資訊，請參閱 [在 Office 365 中的無限制封存的概觀](unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="eaf27-111">For more information, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="eaf27-112">開始之前</span><span class="sxs-lookup"><span data-stu-id="eaf27-112">Before you begin</span></span>

<span data-ttu-id="eaf27-113">您必須獲指派 「 郵件收件者角色在 Exchange Online 來啟用或停用封存信箱。</span><span class="sxs-lookup"><span data-stu-id="eaf27-113">You have to be assigned the Mail Recipients role in Exchange Online to enable or disable archive mailboxes.</span></span> <span data-ttu-id="eaf27-114">根據預設，此角色被指派給在 Exchange 系統管理中心中的**權限**] 頁面上的收件者管理與組織管理角色群組。</span><span class="sxs-lookup"><span data-stu-id="eaf27-114">By default, this role is assigned to the Recipient Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="eaf27-115">如果您沒有看到安全性 & 合規性中心中的 [**封存**] 頁面上，要求您的系統管理員指派必要權限。</span><span class="sxs-lookup"><span data-stu-id="eaf27-115">If you don't see the **Archive** page in the Security & Compliance Center, ask your administrator to assign you the necessary permissions.</span></span> 
  
## <a name="enable-an-archive-mailbox"></a><span data-ttu-id="eaf27-116">啟用封存信箱</span><span class="sxs-lookup"><span data-stu-id="eaf27-116">Enable an archive mailbox</span></span>
  
1. <span data-ttu-id="eaf27-117">移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="eaf27-117">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="eaf27-118">使用公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="eaf27-118">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="eaf27-119">在 [安全性 & 合規性中心的左窗格中，按一下 [**資料控管** \> **封存**。</span><span class="sxs-lookup"><span data-stu-id="eaf27-119">In the left pane of the Security & Compliance Center, click **Data governance** \> **Archive**.</span></span>
    
    <span data-ttu-id="eaf27-120">[封存]\*\*\*\* 頁面隨即出現。</span><span class="sxs-lookup"><span data-stu-id="eaf27-120">The **Archive** page is displayed.</span></span> <span data-ttu-id="eaf27-121">[封存信箱] \*\*\*\* 欄會指出每個使用者的封存信箱是啟用還是停用。</span><span class="sxs-lookup"><span data-stu-id="eaf27-121">The **Archive mailbox** column indicates whether an archive mailbox is enabled or disabled for each user.</span></span> 
    
4. <span data-ttu-id="eaf27-122">在信箱清單中，選取要為其啟用封存信箱的使用者。</span><span class="sxs-lookup"><span data-stu-id="eaf27-122">In the list of mailboxes, select the user that you want to enable the archive mailbox for.</span></span>
    
    ![若要啟用封存信箱所選使用者的詳細資料窗格中按一下 [啟用](media/8b53cdec-d5c9-4c28-af11-611f95c37b34.png)
  
5. <span data-ttu-id="eaf27-124">在所選使用者詳細資料窗格中，按一下 [**啟用**]。</span><span class="sxs-lookup"><span data-stu-id="eaf27-124">In the details pane for the selected user, click **Enable**.</span></span> 
    
    <span data-ttu-id="eaf27-125">說，是否您啟用封存信箱，在使用者的信箱會超過封存原則指派給信箱的項目要移至新的封存信箱會顯示警告。</span><span class="sxs-lookup"><span data-stu-id="eaf27-125">A warning is displayed saying that if you enable the archive mailbox, items in the user's mailbox that are older than the archiving policy assigned to the mailbox will be moved to the new archive mailbox.</span></span> <span data-ttu-id="eaf27-126">預設封存原則指派給 Exchange Online 信箱的保留原則的一部分，將項目移至封存信箱兩年後的項目已傳遞至信箱或使用者所建立的日期。</span><span class="sxs-lookup"><span data-stu-id="eaf27-126">The default archive policy that is part of the retention policy assigned to Exchange Online mailboxes moves items to the archive mailbox two years after the date the item was delivered to the mailbox or created by the user.</span></span> <span data-ttu-id="eaf27-127">如需詳細資訊，請參閱這篇文章中的**詳細資訊**一節。</span><span class="sxs-lookup"><span data-stu-id="eaf27-127">For more information, see the **More info** section in this article.</span></span> 
    
6. <span data-ttu-id="eaf27-128">按一下 [是]\*\*\*\* 啟用封存信箱。</span><span class="sxs-lookup"><span data-stu-id="eaf27-128">Click **Yes** to enable the archive mailbox.</span></span> 
    
    <span data-ttu-id="eaf27-129">可能需要一些時間才能建立封存信箱。</span><span class="sxs-lookup"><span data-stu-id="eaf27-129">It might take a few moments to create the archive mailbox.</span></span> <span data-ttu-id="eaf27-130">建立時，**封存信箱： 啟用**會顯示在詳細資料窗格中選取的使用者。</span><span class="sxs-lookup"><span data-stu-id="eaf27-130">When it's created, **Archive mailbox: enabled** is displayed in the details pane for the selected user.</span></span> <span data-ttu-id="eaf27-131">您可能需要按一下 [**重新整理**![重新整理圖示](media/O365-MDM-Policy-RefreshIcon.gif)以更新詳細資料窗格中的資訊。</span><span class="sxs-lookup"><span data-stu-id="eaf27-131">You might have to click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
> [!TIP]
> <span data-ttu-id="eaf27-p107">您也可以選取多個信箱 (使用 Shift 或 Ctrl 鍵) 來大量啟用封存。選取多個信箱後，按一下詳細資料窗格中的 [啟用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="eaf27-p107">You can also bulk-enable archive mailboxes by selecting multiple users with disabled archive mailboxes (use the Shift or Ctrl keys). After selecting multiple mailboxes, click **Enable** in the details pane.</span></span> 
  
## <a name="disable-an-archive-mailbox"></a><span data-ttu-id="eaf27-134">停用封存信箱</span><span class="sxs-lookup"><span data-stu-id="eaf27-134">Disable an archive mailbox</span></span>
  
<span data-ttu-id="eaf27-135">您也可以使用安全性 & 合規性中心中的 [**封存**] 頁面上，停用使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="eaf27-135">You can also use the **Archive** page in the Security & Compliance Center to disable a user's archive mailbox.</span></span> <span data-ttu-id="eaf27-136">停用封存信箱之後，可以在停用它的 30 天內重新連線至使用者的主要信箱。</span><span class="sxs-lookup"><span data-stu-id="eaf27-136">After you disable an archive mailbox, you can reconnect it to the user's primary mailbox within 30 days of disabling it.</span></span> <span data-ttu-id="eaf27-137">在此情況下，系統會還原封存信箱的原始內容。</span><span class="sxs-lookup"><span data-stu-id="eaf27-137">In this case, the original contents of the archive mailbox are restored.</span></span> <span data-ttu-id="eaf27-138">30 天後，便會永久刪除原始封存信箱的內容，無法再復原。</span><span class="sxs-lookup"><span data-stu-id="eaf27-138">After 30 days, the contents of the original archive mailbox are permanently deleted and can't be recovered.</span></span> <span data-ttu-id="eaf27-139">因此，如果您在停用封存超過 30 天之後才重新啟用它，系統會建立新的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="eaf27-139">So if you re-enable the archive more than 30 days after disabling it, a new archive mailbox is created.</span></span> 
  
<span data-ttu-id="eaf27-140">請注意，預設封存原則指派給使用者的信箱移至封存信箱的項目兩年的日期之後的項目會傳遞。</span><span class="sxs-lookup"><span data-stu-id="eaf27-140">Note that the default archive policy assigned to users' mailboxes moves items to the archive mailbox two years after the date the item is delivered.</span></span> <span data-ttu-id="eaf27-141">如果您停用使用者的封存信箱，將會對信箱項目採取任何動作，他們會一直保留在使用者的主要信箱。</span><span class="sxs-lookup"><span data-stu-id="eaf27-141">If you disable a user's archive mailbox, no action will be taken on mailbox items and they will remain in the user's primary mailbox.</span></span>
  
<span data-ttu-id="eaf27-142">若要停用封存信箱：</span><span class="sxs-lookup"><span data-stu-id="eaf27-142">To disable an archive mailbox:</span></span>
  
1. <span data-ttu-id="eaf27-143">移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="eaf27-143">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="eaf27-144">使用公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="eaf27-144">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="eaf27-145">在 [安全性 & 合規性中心的左窗格中，按一下 [**資料控管** \> **封存**。</span><span class="sxs-lookup"><span data-stu-id="eaf27-145">In the left pane of the Security & Compliance Center, click **Data governance** \> **Archive**.</span></span>
    
    <span data-ttu-id="eaf27-p110">[封存]\*\*\*\* 頁面隨即出現。[封存信箱] \*\*\*\* 欄會指出每個使用者的封存信箱是啟用還是停用。</span><span class="sxs-lookup"><span data-stu-id="eaf27-p110">The **Archive** page is displayed. The **Archive mailbox** column indicates whether an archive mailbox is enabled or disabled for each user.</span></span> 
    
4. <span data-ttu-id="eaf27-148">在信箱清單中，選取要為其停用封存信箱的使用者。</span><span class="sxs-lookup"><span data-stu-id="eaf27-148">In the list of mailboxes, select the user that you want to disable the archive mailbox for.</span></span>
    
5. <span data-ttu-id="eaf27-149">在詳細資料窗格中，按一下 [停用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="eaf27-149">In the details pane, click **Disable**.</span></span> 
    
    <span data-ttu-id="eaf27-150">會顯示警告訊息，指出您有 30 天的時間可以重新啟用封存信箱，並，30 天後，在封存中的所有資訊將會永久都刪除。</span><span class="sxs-lookup"><span data-stu-id="eaf27-150">A warning message is displayed saying that you'll have 30 days to re-enable the archive mailbox, and that after 30 days, all information in the archive will be permanently deleted.</span></span> 
    
6. <span data-ttu-id="eaf27-151">按一下 [是]\*\*\*\* 停用封存信箱。</span><span class="sxs-lookup"><span data-stu-id="eaf27-151">Click **Yes** to disable the archive mailbox.</span></span> 
    
    <span data-ttu-id="eaf27-152">可能需要一些時間才能停用封存信箱。</span><span class="sxs-lookup"><span data-stu-id="eaf27-152">It might take a few moments to disable the archive mailbox.</span></span> <span data-ttu-id="eaf27-153">停用它時，**封存信箱： 停用**會顯示在詳細資料窗格中選取的使用者。</span><span class="sxs-lookup"><span data-stu-id="eaf27-153">When it's disabled, **Archive mailbox: disabled** is displayed in the details pane for the selected user.</span></span> <span data-ttu-id="eaf27-154">您可能需要按一下 [**重新整理**![重新整理圖示](media/O365-MDM-Policy-RefreshIcon.gif)以更新詳細資料窗格中的資訊。</span><span class="sxs-lookup"><span data-stu-id="eaf27-154">You might have to click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
> [!TIP]
> <span data-ttu-id="eaf27-p112">您也可以選取多個已啟用封存信箱的使用者 (使用 Shift 或 Ctrl 鍵) 來大量停用封存信箱。選取多個信箱後，按一下詳細資料窗格中的 [停用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="eaf27-p112">You can also bulk-disable archive mailboxes by selecting multiple users with enabled archive mailboxes (use the Shift or Ctrl keys). After selecting multiple mailboxes, click **Disable** in the details pane.</span></span> 
  
## <a name="use-exchange-online-powershell-to-enable-or-disable-archive-mailboxes"></a><span data-ttu-id="eaf27-157">使用 Exchange Online PowerShell 來啟用或停用封存信箱</span><span class="sxs-lookup"><span data-stu-id="eaf27-157">Use Exchange Online PowerShell to enable or disable archive mailboxes</span></span>

<span data-ttu-id="eaf27-158">您也可以使用 Exchange Online PowerShell 來啟用封存信箱。</span><span class="sxs-lookup"><span data-stu-id="eaf27-158">You can also use Exchange Online PowerShell to enable archive mailboxes.</span></span> <span data-ttu-id="eaf27-159">若要使用 PowerShell 的主要原因是，您可以快速貴組織中啟用所有使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="eaf27-159">The primary reason to use PowerShell is that you can quickly enable the archive mailbox for all users in your organization.</span></span>

<span data-ttu-id="eaf27-160">第一個步驟是連線至 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="eaf27-160">The first step is to connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="eaf27-161">如需相關指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。</span><span class="sxs-lookup"><span data-stu-id="eaf27-161">For instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="eaf27-162">在您連線至 Exchange Online 之後，您可以在以下小節以啟用或停用封存信箱中執行命令。</span><span class="sxs-lookup"><span data-stu-id="eaf27-162">After you're connected to Exchange Online, you can run the commands in the following sections to enable or disable archive mailboxes.</span></span>

### <a name="enable-archive-mailboxes"></a><span data-ttu-id="eaf27-163">啟用封存信箱</span><span class="sxs-lookup"><span data-stu-id="eaf27-163">Enable archive mailboxes</span></span>

<span data-ttu-id="eaf27-164">執行下列命令，以啟用單一使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="eaf27-164">Run the following command to enable the archive mailbox for a single user.</span></span>
    
  ```
  Enable-Mailbox -Identity <username> -Archive
  ```

<span data-ttu-id="eaf27-165">執行下列命令，以啟用的組織 （其封存信箱目前未啟用） 中的所有使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="eaf27-165">Run the following command to enable the archive mailbox for all users in your organization (whose archive mailbox is currently not enabled).</span></span>
    
  ```
  Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
  ```
  
### <a name="disable-archive-mailboxes"></a><span data-ttu-id="eaf27-166">停用封存信箱</span><span class="sxs-lookup"><span data-stu-id="eaf27-166">Disable archive mailboxes</span></span>

<span data-ttu-id="eaf27-167">執行下列命令，以停用單一使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="eaf27-167">Run the following command to disable the archive mailbox for a single user.</span></span>
    
  ```
  Disable-Mailbox -Identity <username> -Archive
  ```

<span data-ttu-id="eaf27-168">執行下列命令，以停用的組織 （目前已啟用封存信箱） 中的所有使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="eaf27-168">Run the following command to disable the archive mailbox for all users in your organization (whose archive mailbox is currently enabled).</span></span>
    
  ```
  Get-Mailbox -Filter {ArchiveStatus -Eq "Active" -AND RecipientTypeDetails -eq "UserMailbox"} | Disable-Mailbox -Archive
  ```

## <a name="more-information"></a><span data-ttu-id="eaf27-169">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="eaf27-169">More information</span></span>
  
- <span data-ttu-id="eaf27-170">封存信箱幫助您和您的使用者以符合您的組織保留、 eDiscovery 和保留需求。</span><span class="sxs-lookup"><span data-stu-id="eaf27-170">Archive mailboxes help you and your users to meet your organization's retention, eDiscovery, and hold requirements.</span></span> <span data-ttu-id="eaf27-171">例如，您可以使用您組織的 Exchange 保留原則，將信箱內容移至使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="eaf27-171">For example, you can use your organization's Exchange retention policy to move mailbox content to users' archive mailbox.</span></span> <span data-ttu-id="eaf27-172">當您使用安全性 & 合規性中心中的 「 內容搜尋 」 工具來搜尋特定內容的使用者的信箱時，也會搜尋使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="eaf27-172">When you use the Content Search tool in the Security & Compliance Center to search a user's mailbox for specific content, the user's archive mailbox will also be searched.</span></span> <span data-ttu-id="eaf27-173">然後放置訴訟暫止狀態或 Office 365 保留原則套用至使用者的信箱時，也會保留在封存信箱中的項目。</span><span class="sxs-lookup"><span data-stu-id="eaf27-173">And, when you place a Litigation Hold or apply an Office 365 retention policy to a user's mailbox, items in the archive mailbox are also retained.</span></span>
  
- <span data-ttu-id="eaf27-174">啟用封存信箱時，使用者可以將郵件儲存在其封存信箱。</span><span class="sxs-lookup"><span data-stu-id="eaf27-174">When an archive mailbox is enabled, users can store messages in their archive mailbox.</span></span> <span data-ttu-id="eaf27-175">使用者可以使用 Microsoft Outlook 和網頁型 Outlook 來存取他們的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="eaf27-175">Users can access their archive mailboxes by using Microsoft Outlook and Outlook on the web.</span></span> <span data-ttu-id="eaf27-176">只要使用這些用戶端應用程式，使用者就能檢視其封存信箱中的郵件，並且在其主要信箱與其封存信箱之間移動或複製郵件。</span><span class="sxs-lookup"><span data-stu-id="eaf27-176">Using either of these client applications, users can view messages in their archive mailbox and move or copy messages between their primary mailbox and their archive mailbox.</span></span> <span data-ttu-id="eaf27-177">使用者也可以使用「復原刪除的郵件」工具復原其封存信箱的 [可復原的項目] 資料夾中的已刪除郵件。</span><span class="sxs-lookup"><span data-stu-id="eaf27-177">Users can also recover deleted items from the Recoverable Items folder in their archive mailbox by using the Recover Deleted Items tool.</span></span> 
  
- <span data-ttu-id="eaf27-178">在啟用信箱的封存之後, 您的組織可以利用之預設 Exchange 保留原則 （也稱為 「 通訊記錄管理 」 或 「 MRM 原則 」） 會自動指派給每個信箱。</span><span class="sxs-lookup"><span data-stu-id="eaf27-178">After archive mailboxes are enabled, your organization can take advantage of the default Exchange retention policy (also called Messaging Records Management or MRM policy) that is automatically assigned to every mailbox.</span></span> <span data-ttu-id="eaf27-179">啟用封存信箱時，預設 Exchange 保留原則自動會執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="eaf27-179">When an archive mailbox is enabled, the default Exchange retention policy automatically does the following:</span></span> 
  
    - <span data-ttu-id="eaf27-180">將使用者主要信箱中兩年以上的郵件移到其封存信箱。</span><span class="sxs-lookup"><span data-stu-id="eaf27-180">Moves items that are two years or older from a user's primary mailbox to their archive mailbox.</span></span> 
    
    - <span data-ttu-id="eaf27-181">將使用者主要信箱的 [可復原的項目] 資料夾中 14 天以上的郵件移至其封存信箱的 [可復原的項目] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="eaf27-181">Moves items that are 14 days or older from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in their archive mailbox.</span></span>
    
- <span data-ttu-id="eaf27-182">如需有關封存信箱和 Exchange 保留原則的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="eaf27-182">For more information about archive mailboxes and Exchange retention policies, see:</span></span>
    
  - [<span data-ttu-id="eaf27-183">保留標記和保留原則</span><span class="sxs-lookup"><span data-stu-id="eaf27-183">Retention tags and retention policies</span></span>](https://go.microsoft.com/fwlink/?LinkId=404424)
    
  - [<span data-ttu-id="eaf27-184">預設保留原則在 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="eaf27-184">Default Retention Policy in Exchange Online </span></span>](https://go.microsoft.com/fwlink/?linkid=839418)
    
  - [<span data-ttu-id="eaf27-185">設定 Office 365 組織中信箱的封存和刪除原則</span><span class="sxs-lookup"><span data-stu-id="eaf27-185">Set up an archive and deletion policy for mailboxes in your Office 365 organization</span></span>](set-up-an-archive-and-deletion-policy-for-mailboxes.md)
