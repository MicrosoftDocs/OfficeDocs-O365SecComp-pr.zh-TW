---
title: 刪除 [可復原的項目] 資料夾中項目保留狀態的雲端式信箱的系統管理說明
ms.author: markjjo
author: markjjo
manager: laurawi
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
ms.assetid: a85e1c87-a48e-4715-bfa9-d5275cde67b0
description: 系統管理員： 刪除 Exchange Online 信箱，使用者可復原的項目] 資料夾中的項目，即使該信箱處於合法持有。 這是有效的方法來刪除已不小心溢出至 Office 365 的資料。
ms.openlocfilehash: 9da469af900c2610762338029aa80d31c7f10363
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34150405"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold---admin-help"></a><span data-ttu-id="44899-104">刪除 [可復原的項目] 資料夾中項目保留狀態的雲端式信箱的系統管理說明</span><span class="sxs-lookup"><span data-stu-id="44899-104">Delete items in the Recoverable Items folder of cloud-based mailboxes on hold - Admin Help</span></span>

<span data-ttu-id="44899-105">若要防止意外或惡意刪除存在於 Exchange Online 信箱 [可復原的項目] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="44899-105">The Recoverable Items folder for an Exchange Online mailbox exists to protect from accidental or malicious deletions.</span></span> <span data-ttu-id="44899-106">它也用來儲存項目會保留並存取 Office 365 合規性功能，例如保留和 eDiscovery 搜尋。</span><span class="sxs-lookup"><span data-stu-id="44899-106">It's also used to store items that are retained and accessed by Office 365 compliance features, such as holds and eDiscovery searches.</span></span> <span data-ttu-id="44899-107">不過，在某些情況下的組織可能必須在他們必須刪除 [可復原的項目] 資料夾中已不小心保留的資料。</span><span class="sxs-lookup"><span data-stu-id="44899-107">However, in some situations organizations might have data that's been unintentionally retained in the Recoverable Items folder that they must delete.</span></span> <span data-ttu-id="44899-108">例如，使用者可能不知情的情況下傳送或轉寄電子郵件包含敏感資訊或可能會有嚴重的商務後果的資訊。</span><span class="sxs-lookup"><span data-stu-id="44899-108">For example, a user might unknowingly send or forward an email message that contains sensitive information or information that may have serious business consequences.</span></span> <span data-ttu-id="44899-109">即使永久刪除的郵件，它可能對其會無限期保留，因為合法持有已放在信箱上。</span><span class="sxs-lookup"><span data-stu-id="44899-109">Even if the message is permanently deleted, it might be retained indefinitely because a legal hold has been placed on the mailbox.</span></span> <span data-ttu-id="44899-110">此案例中稱為資料外洩，因為資料不小心溢出至 Office 365。</span><span class="sxs-lookup"><span data-stu-id="44899-110">This scenario is known as data spillage because data has been unintentionally spilled into Office 365.</span></span> <span data-ttu-id="44899-111">在這些情況下，您可以刪除 Exchange Online 信箱，使用者可復原的項目] 資料夾中的項目，即使該信箱處於保留狀態，以其中一個 Office 365 中的不同的保留功能。</span><span class="sxs-lookup"><span data-stu-id="44899-111">In these situations, you can delete items in a user's Recoverable Items folder for an Exchange Online mailbox, even if that mailbox is placed on hold with one of the different hold features in Office 365.</span></span> <span data-ttu-id="44899-112">這些類型的保留包含訴訟保留、 就地保留、 eDiscovery 保留及建立在 Office 365 或 Microsoft 365 安全性與合規性中心] 中的 Office 365 保留原則。</span><span class="sxs-lookup"><span data-stu-id="44899-112">These types of holds include Litigation Holds, In-Place Holds, eDiscovery holds, and Office 365 retention policies created in the security and compliance center in Office 365 or Microsoft 365.</span></span>
  
 <span data-ttu-id="44899-113">本文說明如何從保留的雲端架構信箱 [可復原的項目] 資料夾刪除項目。</span><span class="sxs-lookup"><span data-stu-id="44899-113">This article explains how to delete items from the Recoverable Items folder for cloud-based mailboxes that are on hold.</span></span> <span data-ttu-id="44899-114">此程序牽涉到停用信箱存取權，以及停用單一項目復原，停用受管理的資料夾助理員處理信箱暫時移除保留、 從可復原的項目] 資料夾刪除項目，然後還原信箱以其先前的設定。</span><span class="sxs-lookup"><span data-stu-id="44899-114">This procedure involves disabling access to the mailbox and disabling single item recovery, disabling the Managed Folder Assistant from processing the mailbox, temporarily removing the hold, deleting items from the Recoverable Items folder, and then reverting the mailbox to its previous configuration.</span></span> <span data-ttu-id="44899-115">以下是程序：</span><span class="sxs-lookup"><span data-stu-id="44899-115">Here's the process:</span></span> 
  
[<span data-ttu-id="44899-116">步驟 1： 收集信箱的相關資訊</span><span class="sxs-lookup"><span data-stu-id="44899-116">Step 1: Collect information about the mailbox</span></span>](#step-1-collect-information-about-the-mailbox)

[<span data-ttu-id="44899-117">步驟 2： 準備信箱</span><span class="sxs-lookup"><span data-stu-id="44899-117">Step 2: Prepare the mailbox</span></span>](#step-2-prepare-the-mailbox)

[<span data-ttu-id="44899-118">步驟 3： 從信箱移除所有保留</span><span class="sxs-lookup"><span data-stu-id="44899-118">Step 3: Remove all holds from the mailbox</span></span>](#step-3-remove-all-holds-from-the-mailbox)

[<span data-ttu-id="44899-119">步驟 4： 從信箱移除延遲保留</span><span class="sxs-lookup"><span data-stu-id="44899-119">Step 4: Remove the delay hold from the mailbox</span></span>](#step-4-remove-the-delay-hold-from-the-mailbox)

<span data-ttu-id="44899-120">[步驟 5： 刪除 [可復原的項目] 資料夾中的項目](#step-5-delete-items-in-the-recoverable-items-folder)</span><span class="sxs-lookup"><span data-stu-id="44899-120">[Step 5: Delete items in the Recoverable Items folder](#step-5-delete-items-in-the-recoverable-items-folder)</span></span>

[<span data-ttu-id="44899-121">步驟 6： 將回復到之前的狀態的信箱</span><span class="sxs-lookup"><span data-stu-id="44899-121">Step 6: Revert the mailbox to its previous state</span></span>](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> <span data-ttu-id="44899-122">本文所述的程序會導致資料被永久刪除 （清除） 從 Exchange Online 信箱。</span><span class="sxs-lookup"><span data-stu-id="44899-122">The procedures outlined in this article will result in data being permanently deleted (purged) from an Exchange Online mailbox.</span></span> <span data-ttu-id="44899-123">這表示您從 [可復原的項目] 資料夾中刪除的郵件無法復原，而且不會為可供法律或其他規範用途。</span><span class="sxs-lookup"><span data-stu-id="44899-123">That means messages that you delete from the Recoverable Items folder can't be recovered and won't be available for legal discovery or other compliance purposes.</span></span> <span data-ttu-id="44899-124">如果您想要從所在的信箱的郵件保留為訴訟暫止狀態，原有範圍暫止，電子文件探索的一部分保留、 刪除或建立在安全性與合規性中心的 Office 365 保留原則，，請洽詢您的記錄管理或法務部門之前先移除保留。</span><span class="sxs-lookup"><span data-stu-id="44899-124">If you want to delete messages from a mailbox that's placed on hold as part of a Litigation Hold, In-Place Hold, eDiscovery hold, or Office 365 retention policy created in the security and compliance center, check with your records management or legal departments before removing the hold.</span></span> <span data-ttu-id="44899-125">您的組織可能會有一個原則來定義是否要保留的信箱上或資料外洩事件會優先採用。</span><span class="sxs-lookup"><span data-stu-id="44899-125">Your organization might have a policy that defines whether a mailbox on hold or a data spillage incident takes priority.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="44899-126">開始之前</span><span class="sxs-lookup"><span data-stu-id="44899-126">Before you begin</span></span>

- <span data-ttu-id="44899-127">您必須同時被指派下列管理角色，在 Exchange Online 來搜尋並刪除在步驟 5 中的 [可復原的項目] 資料夾中的郵件。</span><span class="sxs-lookup"><span data-stu-id="44899-127">You have to be assigned both of the following management roles in Exchange Online to search for and delete messages from the Recoverable Items folder in Step 5.</span></span>
    
  - <span data-ttu-id="44899-128">**信箱搜尋**-此角色可讓您搜尋您的組織中的信箱。</span><span class="sxs-lookup"><span data-stu-id="44899-128">**Mailbox Search** - This role lets you to search mailboxes in your organization.</span></span> <span data-ttu-id="44899-129">根據預設，Exchange 系統管理員未指派此角色。</span><span class="sxs-lookup"><span data-stu-id="44899-129">Exchange administrators aren't assigned this role by default.</span></span> <span data-ttu-id="44899-130">若要自行指派此角色，將自己新增為 「 探索管理角色群組的成員在 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="44899-130">To assign yourself this role, add yourself as a member of the Discovery Management role group in Exchange Online.</span></span> 
    
  - <span data-ttu-id="44899-131">**信箱匯入 / 匯出**-此角色可讓您從使用者的信箱刪除郵件。</span><span class="sxs-lookup"><span data-stu-id="44899-131">**Mailbox Import Export** - This role lets you to delete messages from a user's mailbox.</span></span> <span data-ttu-id="44899-132">根據預設，此角色不指派給任何角色群組。</span><span class="sxs-lookup"><span data-stu-id="44899-132">By default, this role isn't assigned to any role group.</span></span> <span data-ttu-id="44899-133">若要從使用者的信箱刪除郵件，您可以新增 「 信箱匯入 / 匯出 」 角色給組織管理角色群組在 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="44899-133">To delete messages from users' mailboxes, you can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> 
    
- <span data-ttu-id="44899-134">本文所述的程序不支援的非使用中信箱。</span><span class="sxs-lookup"><span data-stu-id="44899-134">The procedure described in this article isn't supported for inactive mailboxes.</span></span> <span data-ttu-id="44899-135">這是因為您無法重新套用保留 （或 Office 365 保留原則） 給非使用中信箱後移除它。</span><span class="sxs-lookup"><span data-stu-id="44899-135">That's because you can't re-apply a hold (or Office 365 retention policy) to an inactive mailbox after you remove it.</span></span> <span data-ttu-id="44899-136">當您從非使用中的信箱移除保留時，它會變更為一般的虛刪除信箱，並將從您的組織永久刪除之後就會受管理的資料夾助理員所處理。</span><span class="sxs-lookup"><span data-stu-id="44899-136">When you remove a hold from an inactive mailbox, it's changed to a normal soft-deleted mailbox and will be permanently deleted from your organization after it's processed by the Managed Folder Assistant.</span></span>
    
- <span data-ttu-id="44899-137">您無法執行此程序的各個信箱。 已指派給已鎖定保留鎖定與 Office 365 保留原則。</span><span class="sxs-lookup"><span data-stu-id="44899-137">You can't perform this procedure for a mailbox that has been assigned to an Office 365 retention policy that's been locked with a Preservation Lock.</span></span> <span data-ttu-id="44899-138">這是因為保留鎖定可防止您無法移除或從 Office 365 保留原則和停用受管理的資料夾助理員在信箱中排除信箱。</span><span class="sxs-lookup"><span data-stu-id="44899-138">That's because a Preservation Lock prevents you from removing or excluding the mailbox from the Office 365 retention policy and from disabling the Managed Folder Assistant on the mailbox.</span></span> <span data-ttu-id="44899-139">如需鎖定保留原則的詳細資訊，請參閱[鎖定保留原則](retention-policies.md#locking-a-retention-policy)。</span><span class="sxs-lookup"><span data-stu-id="44899-139">For more information about locking retention policies, see [Locking a retention policy](retention-policies.md#locking-a-retention-policy).</span></span>
    
- <span data-ttu-id="44899-140">如果信箱未處於暫止狀態 （或都不會有已啟用單一項目復原），您只可以從 [可復原的項目] 資料夾刪除項目。</span><span class="sxs-lookup"><span data-stu-id="44899-140">If a mailbox isn't placed on hold (or doesn't have single item recovery enabled), you can simply delete the items from the Recoverable Items folder.</span></span> <span data-ttu-id="44899-141">如需如何執行這項操作的詳細資訊，請參閱[搜尋並刪除郵件](https://go.microsoft.com/fwlink/?linkid=852453)。</span><span class="sxs-lookup"><span data-stu-id="44899-141">For more information about how to do this, see [Search for and delete messages ](https://go.microsoft.com/fwlink/?linkid=852453).</span></span>
  
## <a name="step-1-collect-information-about-the-mailbox"></a><span data-ttu-id="44899-142">步驟 1： 收集信箱的相關資訊</span><span class="sxs-lookup"><span data-stu-id="44899-142">Step 1: Collect information about the mailbox</span></span>

<span data-ttu-id="44899-143">此第一個步驟是從目標信箱，將會影響此程序收集選取的內容。</span><span class="sxs-lookup"><span data-stu-id="44899-143">This first step is to collect selected properties from the target mailbox that will affect this procedure.</span></span> <span data-ttu-id="44899-144">請務必記下這些設定，或將它們儲存到文字檔，因為您將會變更其中某些屬性，並從 [可復原的項目] 資料夾刪除項目之後，再回復為步驟 6 中的原始值。</span><span class="sxs-lookup"><span data-stu-id="44899-144">Be sure to write down these settings or save them to a text file because you'll change some of these properties and then revert back to the original values in Step 6, after you delete items from the Recoverable Items folder.</span></span> <span data-ttu-id="44899-145">以下是您需要收集的信箱內容清單。</span><span class="sxs-lookup"><span data-stu-id="44899-145">Here's a list of the mailbox properties you need to collect.</span></span>
  
-  <span data-ttu-id="44899-146">*SingleItemRecoveryEnabled*和*RetainDeletedItemsFor* ;如有必要，您將會停用單一復原，並增加在步驟 3 中的已刪除的項目保留期間。</span><span class="sxs-lookup"><span data-stu-id="44899-146">*SingleItemRecoveryEnabled*  and  *RetainDeletedItemsFor*  ; if necessary, you'll disable single recovery and increase the deleted items retention period in Step 3.</span></span> 
    
-  <span data-ttu-id="44899-147">*LitigationHoldEnabled*和*InPlaceHolds* ;您需要識別所有保留在信箱上，讓您可以在步驟 3 中，暫時移除它們。</span><span class="sxs-lookup"><span data-stu-id="44899-147">*LitigationHoldEnabled*  and  *InPlaceHolds*  ; you need to identify all the holds placed on the mailbox so that you can temporarily remove them in Step 3.</span></span> <span data-ttu-id="44899-148">請參閱如何識別可能置於信箱類型保留秘訣[的詳細資訊](#more-information)一節。</span><span class="sxs-lookup"><span data-stu-id="44899-148">See the [More information](#more-information) section for tips about how to identify the type hold that might be placed on a mailbox.</span></span> 
    
<span data-ttu-id="44899-149">此外，您需要取得信箱用戶端存取設定，以便您可以暫時停用它們讓其擁有人 （或其他使用者） 無法在此程序期間存取信箱。</span><span class="sxs-lookup"><span data-stu-id="44899-149">Additionally, you need to get the mailbox client access settings so you can temporarily disable them so the owner (or other users) can't access the mailbox during this procedure.</span></span> <span data-ttu-id="44899-150">最後，您可以在 [可復原的項目] 資料夾中取得目前的大小和項目數。</span><span class="sxs-lookup"><span data-stu-id="44899-150">Finally, you can get the current size and number of items in the Recoverable Items folder.</span></span> <span data-ttu-id="44899-151">刪除在步驟 5 中的 [可復原的項目] 資料夾中的項目之後，您將使用這項資訊來確認已確實移除項目。</span><span class="sxs-lookup"><span data-stu-id="44899-151">After you delete items in the Recoverable Items folder in Step 5, you'll use this information to verify that items were actually removed.</span></span>
  
1. <span data-ttu-id="44899-152">[連線至 Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="44899-152">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span></span> <span data-ttu-id="44899-153">請務必使用已被指派 Exchange Online 中的適當的管理角色的系統管理員帳戶的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="44899-153">Be sure to use a user name and password for an administrator account that's been assigned the appropriate management roles in Exchange Online.</span></span> 
    
2. <span data-ttu-id="44899-154">執行下列命令，以取得單一項目復原和刪除項目保留期間的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="44899-154">Run the following command to get information about single item recovery and the deleted item retention period.</span></span>

    ```
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   <span data-ttu-id="44899-155">如果已啟用單一項目復原，您必須停用它在步驟 2 中。</span><span class="sxs-lookup"><span data-stu-id="44899-155">If single item recovery is enabled, you'll have to disable it in Step 2.</span></span> <span data-ttu-id="44899-156">如果已刪除的項目保留期間未設定為 30 天 （Exchange Online 中的最大值），然後您可以增加其在步驟 2 中。</span><span class="sxs-lookup"><span data-stu-id="44899-156">If the deleted item retention period isn't set for 30 days (the maximum value in Exchange Online), then you can increase it in Step 2.</span></span> 
    
3. <span data-ttu-id="44899-157">執行下列命令，以取得信箱存取信箱的設定。</span><span class="sxs-lookup"><span data-stu-id="44899-157">Run the following command to get the mailbox access settings for the mailbox.</span></span> 
    
    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   <span data-ttu-id="44899-158">您將會停用所有的這些存取方法，在 [步驟 2。</span><span class="sxs-lookup"><span data-stu-id="44899-158">You'll disable all of these access methods in Step 2.</span></span>
    
4. <span data-ttu-id="44899-159">執行下列命令，以取得保留和 Office 365 保留原則套用到信箱的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="44899-159">Run the following command to get information about the holds and Office 365 retention policies applied to the mailbox.</span></span>
    
    ```
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```


   > [!TIP]
    > <span data-ttu-id="44899-160">如果*InPlaceHolds*屬性中有太多的值，而且並非所有的顯示，您可以執行`Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds`命令，以顯示的個別行上的每個值。</span><span class="sxs-lookup"><span data-stu-id="44899-160">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span> 
  
5. <span data-ttu-id="44899-161">執行下列命令，以取得任何全組織的 Office 365 保留原則的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="44899-161">Run the following command to get information about any organization-wide Office 365 retention policies.</span></span> 

    ```
    Get-OrganizationConfig | FL InPlaceHolds
    ```
   <span data-ttu-id="44899-162">如果您的組織有任何全組織的 Office 365 保留原則，您必須從步驟 3 中的這些原則中排除信箱。</span><span class="sxs-lookup"><span data-stu-id="44899-162">If your organization has any organization-wide Office 365 retention policies, you'll have to exclude the mailbox from these policies in Step 3.</span></span>

   > [!TIP]
    > <span data-ttu-id="44899-163">如果*InPlaceHolds*屬性中有太多的值，而且並非所有的顯示，您可以執行`Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`命令，以顯示的個別行上的每個值。</span><span class="sxs-lookup"><span data-stu-id="44899-163">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span> 
  
6. <span data-ttu-id="44899-164">執行下列命令，以取得目前的大小和項目數總計資料夾與使用者的主要信箱中 [可復原的項目] 資料夾中的子資料夾中。</span><span class="sxs-lookup"><span data-stu-id="44899-164">Run the following command to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span> 

    ```
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="44899-165">如果啟用使用者的封存信箱時，執行下列命令，以取得的大小和項目數總計資料夾和其封存信箱中 [可復原的項目] 資料夾中的子資料夾中。</span><span class="sxs-lookup"><span data-stu-id="44899-165">If the user's archive mailbox is enabled, run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in their archive mailbox.</span></span> 

    ```s
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="44899-166">當您刪除在步驟 5 中的項目時，您可以選擇要刪除或無法刪除使用者的主要的封存信箱中的 [可復原的項目] 資料夾中的項目。</span><span class="sxs-lookup"><span data-stu-id="44899-166">When you delete items in Step 5, you can choose to delete or not delete items in the Recoverable Items folder in the user's primary archive mailbox.</span></span> <span data-ttu-id="44899-167">請注意是否自動展開封存的信箱已啟用，將不會刪除輔助封存信箱中的項目。</span><span class="sxs-lookup"><span data-stu-id="44899-167">Note that if auto-expanding archiving is enabled for the mailbox, items in an auxiliary archive mailbox won't be deleted.</span></span>
  
## <a name="step-2-prepare-the-mailbox"></a><span data-ttu-id="44899-168">步驟 2： 準備信箱</span><span class="sxs-lookup"><span data-stu-id="44899-168">Step 2: Prepare the mailbox</span></span>

<span data-ttu-id="44899-169">收集和儲存信箱的相關資訊之後, 下一個步驟是準備信箱藉由執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="44899-169">After collecting and saving information about the mailbox, the next step is to prepare the mailbox by performing the following tasks:</span></span> 
  
- <span data-ttu-id="44899-170">**停用用戶端存取信箱**，使信箱擁有者無法存取其信箱和信箱資料進行任何變更，在此程序期間。</span><span class="sxs-lookup"><span data-stu-id="44899-170">**Disable client access to mailbox** so that the mailbox owner can't access their mailbox and make any changes to the mailbox data during this procedure.</span></span> 
    
- <span data-ttu-id="44899-171">**增加的已刪除的項目保留期間**為 30 天 （Exchange Online 中的最大值），讓項目，不會清除從 [可復原的項目] 資料夾之前在步驟 5 中予以刪除。</span><span class="sxs-lookup"><span data-stu-id="44899-171">**Increase the deleted item retention period** to 30 days (the maximum value in Exchange Online) so that items aren't purged from the Recoverable Items folder before you can delete them in Step 5.</span></span> 
    
- <span data-ttu-id="44899-172">**停用單一項目復原**的項目，不會保留 （適用於已刪除的項目保留期間的持續時間） 之後您刪除在步驟 5 中的 [可復原的項目] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="44899-172">**Disable single Item recovery** so that items won't be retained (for the duration of the deleted item retention period) after you delete them from the Recoverable Items folder in Step 5.</span></span> 
    
- <span data-ttu-id="44899-173">**停用受管理的資料夾助理員**讓它不會處理信箱並保留您在步驟 5 中刪除的項目。</span><span class="sxs-lookup"><span data-stu-id="44899-173">**Disable the Managed Folder Assistant** so that it doesn't process the mailbox and retain the items that you delete in Step 5.</span></span> 
    
<span data-ttu-id="44899-174">在 Exchange Online PowerShell 中執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="44899-174">Perform the following steps in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="44899-175">執行下列命令，以停用信箱的所有用戶端存取。</span><span class="sxs-lookup"><span data-stu-id="44899-175">Run the following command to disable all client access to the mailbox.</span></span> <span data-ttu-id="44899-176">命令語法假設信箱上已啟用所有的用戶端存取方法。</span><span class="sxs-lookup"><span data-stu-id="44899-176">The command syntax assumes that all client access methods were enabled on the mailbox.</span></span>

    ```   
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```
   
   > [!NOTE]
    > <span data-ttu-id="44899-177">可能需要 60 分鐘的時間將停用信箱的所有用戶端存取方法。</span><span class="sxs-lookup"><span data-stu-id="44899-177">It might take up to 60 minutes to disable all client access methods to the mailbox.</span></span> <span data-ttu-id="44899-178">請注意，停用這些存取方法不會中斷連線他們目前登入信箱擁有者。</span><span class="sxs-lookup"><span data-stu-id="44899-178">Note that disabling these access methods won't disconnect the mailbox owner they're currently signed in.</span></span> <span data-ttu-id="44899-179">如果擁有者未登入，然後他們將無法存取其信箱之後這些存取方法都會停用。</span><span class="sxs-lookup"><span data-stu-id="44899-179">If the owner isn't signed in, then they won't be able to access their mailbox after these access methods are disabled.</span></span> 
  
2. <span data-ttu-id="44899-180">執行下列命令，以提高刪除項目保留期間的最大值為 30 天。</span><span class="sxs-lookup"><span data-stu-id="44899-180">Run the following command to increase the deleted item retention period the maximum of 30 days.</span></span> <span data-ttu-id="44899-181">這會假設目前的設定是小於 30 天。</span><span class="sxs-lookup"><span data-stu-id="44899-181">This assumes that the current setting is less than 30 days.</span></span> 

    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. <span data-ttu-id="44899-182">執行下列命令，以停用單一項目復原。</span><span class="sxs-lookup"><span data-stu-id="44899-182">Run the following command to disable single item recovery.</span></span>
    
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

   > [!NOTE]
    > <span data-ttu-id="44899-183">可能需要 60 分鐘的時間將停用單一項目復原。</span><span class="sxs-lookup"><span data-stu-id="44899-183">It might take up to 60 minutes to disable single item recovery.</span></span> <span data-ttu-id="44899-184">不要刪除 [可復原的項目] 資料夾中的項目，直到在經過這段期間。</span><span class="sxs-lookup"><span data-stu-id="44899-184">Don't delete items in the Recoverable Items folder until this period has elapsed.</span></span> 
  
4. <span data-ttu-id="44899-185">執行下列命令，以防止受管理的資料夾助理員處理信箱。</span><span class="sxs-lookup"><span data-stu-id="44899-185">Run the following command to prevent the Managed Folder Assistant from processing the mailbox.</span></span> <span data-ttu-id="44899-186">如先前所述，您可以停用受管理的資料夾助理員只有當使用保留鎖定的 Office 365 保留原則不會套用到信箱。</span><span class="sxs-lookup"><span data-stu-id="44899-186">As previously explained, you can disable the Managed Folder Assistant only if an Office 365 retention policy with a Preservation Lock is not applied to the mailbox.</span></span> 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a><span data-ttu-id="44899-187">步驟 3： 從信箱移除所有保留</span><span class="sxs-lookup"><span data-stu-id="44899-187">Step 3: Remove all holds from the mailbox</span></span>

<span data-ttu-id="44899-188">您可以從 [可復原的項目] 資料夾刪除項目之前的最後一個步驟是移除所有保留 （您在步驟 1 中識別） 放置在信箱上。</span><span class="sxs-lookup"><span data-stu-id="44899-188">The last step before you can delete items from the Recoverable Items folder is to remove all holds (that you identified in Step 1) placed on the mailbox.</span></span> <span data-ttu-id="44899-189">如此將不會保留項目，當您從 [可復原的項目] 資料夾刪除之後，必須先移除所有保留。</span><span class="sxs-lookup"><span data-stu-id="44899-189">All holds must be removed so that items won't be retained after you delete them from the Recoverable Items folder.</span></span> <span data-ttu-id="44899-190">下列各節包含不同類型的保留在信箱上的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="44899-190">The following sections contain information about removing different types of holds on a mailbox.</span></span> <span data-ttu-id="44899-191">請參閱如何識別可能置於信箱類型保留秘訣[的詳細資訊](#more-information)一節。</span><span class="sxs-lookup"><span data-stu-id="44899-191">See the [More information](#more-information) section for tips about how to identify the type hold that might be placed on a mailbox.</span></span> <span data-ttu-id="44899-192">如需詳細資訊，請參閱 <<c0>如何識別的型別保留放在 Exchange Online 信箱。</span><span class="sxs-lookup"><span data-stu-id="44899-192">For additional information, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="44899-193">如先前所述，請洽詢您的記錄管理或法務部門之前先從信箱移除保留。</span><span class="sxs-lookup"><span data-stu-id="44899-193">As previously stated, check with your records management or legal departments before removing a hold from a mailbox.</span></span> 
  
 ### <a name="litigation-hold"></a><span data-ttu-id="44899-194">訴訟資料暫留</span><span class="sxs-lookup"><span data-stu-id="44899-194">Litigation Hold</span></span>
  
<span data-ttu-id="44899-195">下列命令在 Exchange Online PowerShell 中執行從信箱移除訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="44899-195">Run the following command in Exchange Online PowerShell to remove a Litigation Hold from the mailbox.</span></span>

```
Set-Mailbox <username> -LitigationHoldEnabled $false
```

   
> [!NOTE]
> <span data-ttu-id="44899-196">類似於停用單一項目復原與用戶端存取方法，它可能需要 60 分鐘的時間將移除訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="44899-196">Similar to disabling the client access methods and single item recovery, it might take up to 60 minutes to remove the Litigation Hold.</span></span> <span data-ttu-id="44899-197">不要從 [可復原的項目] 資料夾刪除項目，直到經過這段期間。</span><span class="sxs-lookup"><span data-stu-id="44899-197">Don't delete items from the Recoverable Items folder until this period has elapsed.</span></span> 
  
 ### <a name="in-place-hold"></a><span data-ttu-id="44899-198">原有範圍暫止</span><span class="sxs-lookup"><span data-stu-id="44899-198">In-Place Hold</span></span>
  
<span data-ttu-id="44899-199">PowerShell 中執行下列命令在 Exchange Online 來識別信箱處於就地保留。</span><span class="sxs-lookup"><span data-stu-id="44899-199">Run the following command in Exchange Online PowerShell to identify the In-Place Hold that's placed on the mailbox.</span></span> <span data-ttu-id="44899-200">針對您在步驟 1 中識別為 「 就地保留使用 GUID。</span><span class="sxs-lookup"><span data-stu-id="44899-200">Use the GUID for the In-Place Hold that you identified in Step 1.</span></span> 

```
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```
   
<span data-ttu-id="44899-201">識別 「 就地保留 」 狀態之後，您可以使用 Exchange 系統管理中心 (EAC) 或 Exchange Online PowerShell，從保留移除信箱。</span><span class="sxs-lookup"><span data-stu-id="44899-201">After you identify the In-Place Hold, you can use the Exchange admin center (EAC) or Exchange Online PowerShell to remove the mailbox from the hold.</span></span> <span data-ttu-id="44899-202">如需詳細資訊，請參閱[建立或移除就地保留](https://go.microsoft.com/fwlink/?linkid=852668)。</span><span class="sxs-lookup"><span data-stu-id="44899-202">For more information, see [Create or remove an In-Place Hold](https://go.microsoft.com/fwlink/?linkid=852668).</span></span>
  
 ### <a name="office-365-retention-policies-applied-to-specific-mailboxes"></a><span data-ttu-id="44899-203">Office 365 保留原則套用至特定信箱</span><span class="sxs-lookup"><span data-stu-id="44899-203">Office 365 retention policies applied to specific mailboxes</span></span>
  
<span data-ttu-id="44899-204">若要找出 Office 365 保留原則套用到信箱的[安全性 & 合規性中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)中執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="44899-204">Run the following command in [Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the Office 365 retention policy that is applied to the mailbox.</span></span> <span data-ttu-id="44899-205">使用的 GUID (不包括`mbx`或`skp`字首) 您在步驟 1 中識別的保留原則。</span><span class="sxs-lookup"><span data-stu-id="44899-205">Use the GUID (not including the  `mbx` or  `skp` prefix) for the retention policy that you identified in Step 1.</span></span> 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```
   
<span data-ttu-id="44899-206">識別的保留原則之後，請移至**日期控管**\>安全性 & 合規性中心內的**保留**頁面編輯您在上一個步驟中識別的保留原則，並從清單中移除信箱如果收件者包含在保留原則。</span><span class="sxs-lookup"><span data-stu-id="44899-206">After you identify the retention policy, go to the **Date governance** \> **Retention** page in the Security & Compliance Center, edit the retention policy that you identified in the previous step, and remove the mailbox from the list of recipients that are included in the retention policy.</span></span> 
  
 ### <a name="organization-wide-office-365-retention-policies"></a><span data-ttu-id="44899-207">整個組織的 Office 365 保留原則</span><span class="sxs-lookup"><span data-stu-id="44899-207">Organization-wide Office 365 retention policies</span></span>
  
<span data-ttu-id="44899-208">全組織和 Exchange 整個 Office 365 保留原則會套用至組織中的每個信箱。</span><span class="sxs-lookup"><span data-stu-id="44899-208">Organization-wide and Exchange-wide Office 365 retention policies are applied to every mailbox in the organization.</span></span> <span data-ttu-id="44899-209">它們會套用在組織層級 （而不是信箱層級），當您在步驟 1 中執行**Get-organizationconfig** cmdlet 會傳回。</span><span class="sxs-lookup"><span data-stu-id="44899-209">They are applied at the organization level (not the mailbox level) and are returned when you run the **Get-OrganizationConfig** cmdlet in Step 1.</span></span> <span data-ttu-id="44899-210">若要找出整個組織的 Office 365 保留原則的[安全性 & 合規性中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)中執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="44899-210">Run the following command in [Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the organization-wide Office 365 retention policies.</span></span> <span data-ttu-id="44899-211">使用的 GUID (不包括`mbx`字首) 針對您在步驟 1 中識別的全組織保留原則。</span><span class="sxs-lookup"><span data-stu-id="44899-211">Use the GUID (not including the  `mbx` prefix) for the organization-wide retention policies that you identified in Step 1.</span></span> 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

<span data-ttu-id="44899-212">找出整個組織的 Office 365 保留原則之後，請移至**日期控管**\>安全性 & 合規性中心內的**保留**頁面編輯中識別每個全組織保留原則上一個步驟，並將信箱新增至排除的收件者清單。</span><span class="sxs-lookup"><span data-stu-id="44899-212">After you identify the organization-wide Office 365 retention policies, go to the **Date governance** \> **Retention** page in the Security & Compliance Center, edit each organization-wide retention policy that you identified in the previous step, and add the mailbox to the list of excluded recipients.</span></span> <span data-ttu-id="44899-213">執行此動作會從保留原則中移除使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="44899-213">Doing this will remove the user's mailbox from the retention policy.</span></span> 

### <a name="office-365-retention-labels"></a><span data-ttu-id="44899-214">Office 365 保留標籤</span><span class="sxs-lookup"><span data-stu-id="44899-214">Office 365 retention labels</span></span>

<span data-ttu-id="44899-215">每當使用者套用設定為保留內容或保留，然後刪除任何資料夾或其信箱中的項目內容的標籤， *ComplianceTagHoldApplied*信箱屬性設為**True**。</span><span class="sxs-lookup"><span data-stu-id="44899-215">Whenever a user applies a label that's configured to retain content or retain and then delete content to any folder or item in their mailbox, the *ComplianceTagHoldApplied* mailbox property is set to **True**.</span></span> <span data-ttu-id="44899-216">發生這種情況，信箱會被視為在保存時，就如同它已處於訴訟暫止狀態或指派給 Office 365 保留原則。</span><span class="sxs-lookup"><span data-stu-id="44899-216">When this happens, the mailbox is considered to be on hold, just as if it was placed on Litigation Hold or assigned to an Office 365 retention policy.</span></span>

<span data-ttu-id="44899-217">若要檢視*ComplianceTagHoldApplied*屬性的值，請在 Exchange Online PowerShell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="44899-217">To view the value of the *ComplianceTagHoldApplied* property, run the following command in Exchange Online PowerShell:</span></span>

```
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

<span data-ttu-id="44899-218">您已識別信箱處於之後保留因為保留標籤套用至資料夾或項目，您可以使用 「 內容搜尋 」 工具中的安全性與合規性中心來搜尋標示使用 ComplianceTag 搜尋條件的項目。</span><span class="sxs-lookup"><span data-stu-id="44899-218">After you've identified that a mailbox is on hold because a retention label is applied to a folder or item, you can use the Content Search tool in the security and compliance center to search for labeled items by using the ComplianceTag search condition.</span></span> <span data-ttu-id="44899-219">如需詳細資訊，請參閱 「 搜尋條件 」 一節中[關鍵字查詢和搜尋條件的內容搜尋](keyword-queries-and-search-conditions.md#conditions-for-common-properties)。</span><span class="sxs-lookup"><span data-stu-id="44899-219">For more information, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md#conditions-for-common-properties).</span></span>

<span data-ttu-id="44899-220">如需標籤的詳細資訊，請參閱 <<c0>概觀的 Office 365 標籤。</span><span class="sxs-lookup"><span data-stu-id="44899-220">For more information about labels, see [Overview of Office 365 labels](labels.md).</span></span>

 ### <a name="ediscovery-case-holds"></a><span data-ttu-id="44899-221">eDiscovery 案件保留</span><span class="sxs-lookup"><span data-stu-id="44899-221">eDiscovery case holds</span></span>
  
<span data-ttu-id="44899-222">若要找出保留套用到信箱的 eDiscovery 案例相關聯的[安全性 & 合規性中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)中執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="44899-222">Run the following commands in [Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the hold associated with an eDiscovery case that's applied to the mailbox.</span></span> <span data-ttu-id="44899-223">使用的 GUID (不包括`UniH`字首) ediscovery 保留您在步驟 1 中識別。</span><span class="sxs-lookup"><span data-stu-id="44899-223">Use the GUID (not including the  `UniH` prefix) for the eDiscovery hold that you identified in Step 1.</span></span> <span data-ttu-id="44899-224">請注意，第二個命令會顯示保留相關聯; 的 eDiscovery 案例的名稱第三個命令會顯示的保留名稱。</span><span class="sxs-lookup"><span data-stu-id="44899-224">Note that the second command displays the name of the eDiscovery case the hold is associated with; the third command displays the name of the hold.</span></span> 
  
```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```
$CaseHold.Name
```

<span data-ttu-id="44899-225">您已識別的名稱的 eDiscovery 案例及保留之後，請移至**eDiscovery** \> **eDiscovery** ] 頁面上規範中心，開啟的情況下，然後從保留移除信箱。</span><span class="sxs-lookup"><span data-stu-id="44899-225">After you've identified the name of the eDiscovery case and the hold, go to the **eDiscovery** \> **eDiscovery** page in the compliance center, open the case, and remove the mailbox from the hold.</span></span> <span data-ttu-id="44899-226">如需詳細資訊，請參閱 < <b0>eDiscovery 案例</b0>。</span><span class="sxs-lookup"><span data-stu-id="44899-226">For more information, see [eDiscovery cases](ediscovery-cases.md).</span></span>
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a><span data-ttu-id="44899-227">步驟 4： 從信箱移除延遲保留</span><span class="sxs-lookup"><span data-stu-id="44899-227">Step 4: Remove the delay hold from the mailbox</span></span>

<span data-ttu-id="44899-228">從信箱移除任何類型的保留後， *DelayHoldApplied*信箱屬性的值設為**True**。</span><span class="sxs-lookup"><span data-stu-id="44899-228">After any type of hold is removed from a mailbox, the value of the *DelayHoldApplied* mailbox property is set to **True**.</span></span> <span data-ttu-id="44899-229">發生此情況下一次受管理的資料夾助理員處理信箱，並會偵測已移除保留。</span><span class="sxs-lookup"><span data-stu-id="44899-229">This occurs the next time the Managed Folder Assistant processes the mailbox and detects that a hold has been removed.</span></span> <span data-ttu-id="44899-230">這稱為*延遲保留*，表示實際移除保留延遲，以防止資料會永久刪除信箱的 30 天。</span><span class="sxs-lookup"><span data-stu-id="44899-230">This is called a *delay hold* and means the actual removal of the hold is delayed for 30 days to prevent data from being permanently deleted from the mailbox.</span></span> <span data-ttu-id="44899-231">（延遲保留的用途是讓系統管理員機會搜尋或復原之後移除保留為止，將清除的信箱項目）。 當延遲暫留時保留該信箱時，信箱會仍被視為不受限制的持續期間，保留為信箱是否訴訟暫止。</span><span class="sxs-lookup"><span data-stu-id="44899-231">(The purpose of a delay hold is to give admins an opportunity to search for or recover mailbox items that will be purged after a hold is removed.)  When a delay hold is placed on the mailbox, the mailbox is still considered to be on hold for an unlimited duration, as if the mailbox was on Litigation Hold.</span></span> <span data-ttu-id="44899-232">30 天後，延遲保留到期，與 Office 365 會自動嘗試移除延遲保留 （ *DelayHoldApplied*屬性設定為**False**），讓實際移除保留為止。</span><span class="sxs-lookup"><span data-stu-id="44899-232">After 30 days, the delay hold expires, and Office 365 will automatically attempt to remove the delay hold (by setting the *DelayHoldApplied* property to **False**) so that the hold is actually removed.</span></span> 

<span data-ttu-id="44899-233">您可以刪除在步驟 5 中的項目之前，您必須從信箱移除延遲保留。</span><span class="sxs-lookup"><span data-stu-id="44899-233">Before you can delete items in Step 5, you have to remove the delay hold from the mailbox.</span></span> <span data-ttu-id="44899-234">首先，決定是否延遲保留套用至信箱的 Exchange Online PowerShell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="44899-234">First, determine if the delay hold is applied to the mailbox by running the following command in Exchange Online PowerShell:</span></span>

```
Get-Mailbox <username> | FL DelayHoldApplied
```

<span data-ttu-id="44899-235">如果*DelayHoldApplied*屬性的值設為**False**，延遲有不被暫留保留信箱。</span><span class="sxs-lookup"><span data-stu-id="44899-235">If the value of the *DelayHoldApplied* property is set to **False**, a delay hold has not been placed on the mailbox.</span></span> <span data-ttu-id="44899-236">您可以移至步驟 5，並刪除 [可復原的項目] 資料夾中的項目。</span><span class="sxs-lookup"><span data-stu-id="44899-236">You can go to Step 5 and delete items in the Recoverable Items folder.</span></span>

<span data-ttu-id="44899-237">如果*DelayHoldApplied*屬性的值設為**True**，執行下列命令，以移除延遲保留：</span><span class="sxs-lookup"><span data-stu-id="44899-237">If the value of the *DelayHoldApplied* property is set to **True**, run the following command to remove the delay hold:</span></span>

```
Set-Mailbox <username> -RemoveDelayHoldApplied
```
<span data-ttu-id="44899-238">請注意，您必須獲指派法律保留角色在 Exchange Online 使用*RemoveDelayHoldApplied*參數。</span><span class="sxs-lookup"><span data-stu-id="44899-238">Note that you must be assigned the Legal Hold role in Exchange Online to use the *RemoveDelayHoldApplied* parameter.</span></span>

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a><span data-ttu-id="44899-239">步驟 5： 刪除 [可復原的項目] 資料夾中的項目</span><span class="sxs-lookup"><span data-stu-id="44899-239">Step 5: Delete items in the Recoverable Items folder</span></span>

<span data-ttu-id="44899-240">現在，您已準備實際使用[Search-mailbox](https://go.microsoft.com/fwlink/?linkid=852595)指令程式在 Exchange Online PowerShell 中刪除 [可復原的項目] 資料夾中的項目。</span><span class="sxs-lookup"><span data-stu-id="44899-240">Now you're ready to actually delete items in the Recoverable Items folder by using the [Search-Mailbox](https://go.microsoft.com/fwlink/?linkid=852595) cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="44899-241">執行**搜尋信箱**指令程式時，您會有三個選項。</span><span class="sxs-lookup"><span data-stu-id="44899-241">You have three options when running the **Search-Mailbox** cmdlet.</span></span> 
  
- <span data-ttu-id="44899-242">刪除之前，您可以檢查的項目，如有必要，刪除之前，請將項目複製到目標信箱。</span><span class="sxs-lookup"><span data-stu-id="44899-242">Copy items to a target mailbox before you delete them so that you can review the items, if necessary, before you delete them.</span></span>
    
- <span data-ttu-id="44899-243">將項目複製到目標信箱，並在同一個命令中刪除。</span><span class="sxs-lookup"><span data-stu-id="44899-243">Copy items to a target mailbox and delete them in the same command.</span></span>
    
- <span data-ttu-id="44899-244">刪除項目，而不將它們複製到目標信箱。</span><span class="sxs-lookup"><span data-stu-id="44899-244">Delete items without copying them to a target mailbox.</span></span> 
    
<span data-ttu-id="44899-245">請注意，當您執行**Search-mailbox**指令程式時，也會刪除使用者的主要的封存信箱中的 [可復原的項目] 資料夾中的項目。</span><span class="sxs-lookup"><span data-stu-id="44899-245">Note that items in the Recoverable Items folder in the user's primary archive mailbox will also be deleted when you run the **Search-Mailbox** cmdlet.</span></span> <span data-ttu-id="44899-246">若要避免這種情況，您可以包含*DoNotIncludeArchive*參數。</span><span class="sxs-lookup"><span data-stu-id="44899-246">To prevent this, you can include the  *DoNotIncludeArchive*  switch.</span></span> <span data-ttu-id="44899-247">如先前所述，如果自動展開封存會啟用信箱，並 \* \* 搜尋信箱 \* \* 指令程式不會刪除輔助封存信箱中的項目。</span><span class="sxs-lookup"><span data-stu-id="44899-247">And as previously stated, if auto-expanding archiving is enabled for the mailbox, the \*\* Search-Mailbox \*\* cmdlet doesn't deleted items in an auxiliary archive mailbox.</span></span> <span data-ttu-id="44899-248">如需自動展開封存，請參閱[在 Office 365 中的無限制封存概觀](unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="44899-248">For more information about auto-expanding archive, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="44899-249">如果您使用包含在搜尋查詢 （ *SearchQuery*參數），此**Search-mailbox** cmdlet 會傳回最大值為 10000 個項目在搜尋結果中。</span><span class="sxs-lookup"><span data-stu-id="44899-249">If you include a search query (by using the  *SearchQuery*  parameter), the **Search-Mailbox** cmdlet will return a maximum of 10,000 items in the search results.</span></span> <span data-ttu-id="44899-250">因此如果您包含在搜尋查詢，您可能必須執行**Search-mailbox**命令多次，以刪除 10000 個以上的項目。</span><span class="sxs-lookup"><span data-stu-id="44899-250">Therefore if you include a search query, you might have to run the **Search-Mailbox** command multiple times to delete more than 10,000 items.</span></span> 
  
<span data-ttu-id="44899-251">下列範例會顯示命令語法為每個這些選項。</span><span class="sxs-lookup"><span data-stu-id="44899-251">The following examples show the command syntax for each of these options.</span></span> <span data-ttu-id="44899-252">這些範例使用`-SearchQuery size>0`參數值，從 [可復原的項目] 資料夾中的所有子資料夾中刪除所有項目。</span><span class="sxs-lookup"><span data-stu-id="44899-252">These examples use the  `-SearchQuery size>0` parameter value, which deletes all items from all subfolders in the Recoverable Items folder.</span></span> <span data-ttu-id="44899-253">如果您需要刪除符合特定條件的項目，您也可以使用*SearchQuery*參數來指定其他種條件，例如一則訊息或日期範圍的主旨。</span><span class="sxs-lookup"><span data-stu-id="44899-253">If you need to delete only items that match specific conditions, you can also use the  *SearchQuery*  parameter to specify other conditions, such as the subject of a message or a date range.</span></span> <span data-ttu-id="44899-254">請參閱下列的[其他使用 SearchQuery 參數的範例](#other-examples-of-using-the-searchquery-parameter)。</span><span class="sxs-lookup"><span data-stu-id="44899-254">See the [other examples of using the SearchQuery parameter](#other-examples-of-using-the-searchquery-parameter) below.</span></span> 
  
### <a name="example-1"></a><span data-ttu-id="44899-255">範例 1</span><span class="sxs-lookup"><span data-stu-id="44899-255">Example 1</span></span>

<span data-ttu-id="44899-256">本範例會在使用者的 [可復原的項目] 資料夾中的所有項目複製至貴組織的探索搜尋信箱中的資料夾。</span><span class="sxs-lookup"><span data-stu-id="44899-256">This example copies all items in the user's Recoverable Items folder to a folder in your organization's Discovery Search Mailbox.</span></span> <span data-ttu-id="44899-257">這可讓您永久刪除之前，先檢閱項目。</span><span class="sxs-lookup"><span data-stu-id="44899-257">This lets you review the items before you permanently delete them.</span></span>

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>"
```

<span data-ttu-id="44899-258">在前一個範例中，不需要將項目複製到 [探索搜尋信箱。</span><span class="sxs-lookup"><span data-stu-id="44899-258">In the previous example, it isn't required to copy items to the Discovery Search Mailbox.</span></span> <span data-ttu-id="44899-259">您可以將郵件複製到任何目標信箱。</span><span class="sxs-lookup"><span data-stu-id="44899-259">You can copy messages to any target mailbox.</span></span> <span data-ttu-id="44899-260">不過，若要避免潛在機密的信箱資料存取，建議將郵件複製到存取限制 [已授權的人員的信箱。</span><span class="sxs-lookup"><span data-stu-id="44899-260">However, to prevent access to potentially sensitive mailbox data, we recommend copying messages to a mailbox that has access restricted to authorized personnel.</span></span> <span data-ttu-id="44899-261">根據預設，探索搜尋信箱的預設值會限制存取探索管理角色群組的成員在 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="44899-261">By default, access to the default Discovery Search Mailbox is restricted to members of the Discovery Management role group in Exchange Online.</span></span> 
  
### <a name="example-2"></a><span data-ttu-id="44899-262">範例 2</span><span class="sxs-lookup"><span data-stu-id="44899-262">Example 2</span></span>

<span data-ttu-id="44899-263">本範例會在使用者的 [可復原的項目] 資料夾中的所有項目複製到貴組織的探索搜尋信箱中的資料夾，並再刪除使用者的 [可復原的項目] 資料夾中的項目。</span><span class="sxs-lookup"><span data-stu-id="44899-263">This example copies all items in the user's Recoverable Items folder to a folder in your organization's Discovery Search Mailbox and then deletes the items from the user's Recoverable Items folder.</span></span>

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>" -DeleteContent
```
 
### <a name="example-3"></a><span data-ttu-id="44899-264">範例 3</span><span class="sxs-lookup"><span data-stu-id="44899-264">Example 3</span></span>

<span data-ttu-id="44899-265">本範例會刪除使用者的 [可復原的項目] 資料夾中的所有項目，而不將它們複製到目標信箱。</span><span class="sxs-lookup"><span data-stu-id="44899-265">This example deletes all items in the user's Recoverable Items folder, without copying them to a target mailbox.</span></span> 

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -DeleteContent
```

### <a name="other-examples-of-using-the-searchquery-parameter"></a><span data-ttu-id="44899-266">使用 SearchQuery 參數的其他範例</span><span class="sxs-lookup"><span data-stu-id="44899-266">Other examples of using the SearchQuery parameter</span></span>

<span data-ttu-id="44899-267">以下是一些使用*SearchQuery*參數來找出特定郵件的範例。</span><span class="sxs-lookup"><span data-stu-id="44899-267">Here are a few examples of using the  *SearchQuery*  parameter to find specific messages.</span></span> <span data-ttu-id="44899-268">如果您使用*SearchQuery*參數來搜尋特定項目，請考慮將搜尋結果複製到目標信箱，以便您可以檢閱搜尋結果，然後修訂巨集查詢視之前刪除的搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="44899-268">If you use the  *SearchQuery*  parameter to search for specific items, consider copying the search results to a target mailbox so that you can review the search results and then revise the query if necessary before you delete the results of a search.</span></span> 
  
<span data-ttu-id="44899-269">此範例會傳回包含 [主旨] 欄位中的特定片語的郵件。</span><span class="sxs-lookup"><span data-stu-id="44899-269">This example returns messages that contain a specific phrase in the Subject field.</span></span>
  
```
SearchQuery 'subject:"MAIL_BOX VALIDATION/UPGRADE!!!"' 
```

<span data-ttu-id="44899-270">此範例會傳回在指定的日期範圍內所傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="44899-270">This example returns messages that were sent within the specified date range.</span></span>
  
```
SearchQuery 'sent>=06/01/2016 AND sent<=09/01/2016'
```
 
<span data-ttu-id="44899-271">此範例會傳回至指定的人員所傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="44899-271">This example returns messages that were sent to the specified person.</span></span>

```
SearchQuery 'to:garthf@alpinehouse.com'
```
   
### <a name="verify-that-items-were-deleted"></a><span data-ttu-id="44899-272">確認已刪除項目</span><span class="sxs-lookup"><span data-stu-id="44899-272">Verify that items were deleted</span></span>

<span data-ttu-id="44899-273">若要確認您已成功刪除的項目從信箱 [可復原的項目] 資料夾，使用**Get-mailboxfolderstatistics**指令程式在 Exchange Online PowerShell 來檢查的大小和可復原的項目] 資料夾中的項目數。</span><span class="sxs-lookup"><span data-stu-id="44899-273">To verify that you've successfully deleted items from the Recoverable Items folder of a mailbox, use **Get-MailboxFolderStatistics** cmdlet in Exchange Online PowerShell to check the size and number of items in Recoverable Items folder.</span></span> <span data-ttu-id="44899-274">您可以比較以您在步驟 1 中所收集的這些統計資料。</span><span class="sxs-lookup"><span data-stu-id="44899-274">You can compare these statistics with the ones you collected in Step 1.</span></span> 
  
<span data-ttu-id="44899-275">在 [執行下列命令，以取得目前的大小和項目數總計資料夾與使用者的主要信箱中 [可復原的項目] 資料夾中的子資料夾中。</span><span class="sxs-lookup"><span data-stu-id="44899-275">Run the following command in to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span> 
  
```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
   
<span data-ttu-id="44899-276">執行下列命令，以取得的大小和項目數總計資料夾與使用者的封存信箱中 [可復原的項目] 資料夾中的子資料夾中。</span><span class="sxs-lookup"><span data-stu-id="44899-276">Run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in the user's archive mailbox.</span></span> 

```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
  
## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a><span data-ttu-id="44899-277">步驟 6： 將回復到之前的狀態的信箱</span><span class="sxs-lookup"><span data-stu-id="44899-277">Step 6: Revert the mailbox to its previous state</span></span>

<span data-ttu-id="44899-278">最後一個步驟是要還原的信箱回到其先前的設定。</span><span class="sxs-lookup"><span data-stu-id="44899-278">The final step is to revert the mailbox back to its previous configuration.</span></span> <span data-ttu-id="44899-279">這表示重設您在步驟 2 中已變更的內容，並重新套用您在步驟 3 中移除保留。</span><span class="sxs-lookup"><span data-stu-id="44899-279">This means resetting the properties that you changed in Step 2 and re-applying the holds that you removed in Step 3.</span></span> <span data-ttu-id="44899-280">其中包括：</span><span class="sxs-lookup"><span data-stu-id="44899-280">This includes:</span></span>
  
- <span data-ttu-id="44899-281">變更刪除項目保留期間回到其先前的值。</span><span class="sxs-lookup"><span data-stu-id="44899-281">Changing the deleted item retention period back to its previous value.</span></span> <span data-ttu-id="44899-282">或者，您可以只保留在 [Exchange 設定為 30 天，最大值這線上。</span><span class="sxs-lookup"><span data-stu-id="44899-282">Alternatively, you can just leave this set to 30 days, the maximum value in Exchange Online.</span></span>
    
- <span data-ttu-id="44899-283">重新啟用單一項目復原。</span><span class="sxs-lookup"><span data-stu-id="44899-283">Re-enabling single Item recovery.</span></span>
    
- <span data-ttu-id="44899-284">重新啟用用戶端存取方法，讓其擁有人可以存取其信箱。</span><span class="sxs-lookup"><span data-stu-id="44899-284">Re-enabling the client access methods so that the owner can access their mailbox.</span></span>
    
- <span data-ttu-id="44899-285">重新套用保留和您所移除的 Office 365 保留原則。</span><span class="sxs-lookup"><span data-stu-id="44899-285">Re-applying the holds and Office 365 retention policies that you removed.</span></span>
    
- <span data-ttu-id="44899-286">重新啟用受管理的資料夾助理員處理信箱。</span><span class="sxs-lookup"><span data-stu-id="44899-286">Re-enabling the Managed Folder Assistant to process the mailbox.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="44899-287">我們建議您等候 24 小時後重新套用保留或 Office 365 保留原則 （並確認它已經準備就緒） 重新啟用受管理的資料夾助理員處理信箱之前。</span><span class="sxs-lookup"><span data-stu-id="44899-287">We recommend that you wait 24 hours after re-applying a hold or Office 365 retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant to process the mailbox.</span></span> 
  
<span data-ttu-id="44899-288">在 Exchange Online PowerShell 中執行下列步驟 （指定的順序）。</span><span class="sxs-lookup"><span data-stu-id="44899-288">Perform the following steps (in the specified sequence) in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="44899-289">執行下列命令，以變更刪除項目保留期間回到原來的數值。</span><span class="sxs-lookup"><span data-stu-id="44899-289">Run the following command to change the deleted item retention period back to its original value.</span></span> <span data-ttu-id="44899-290">這會假設先前的設定為小於 30 天的資料;例如 14 天。</span><span class="sxs-lookup"><span data-stu-id="44899-290">This assumes that the previous setting is less than 30 days; for example 14 days.</span></span> 
    
    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```
   
2. <span data-ttu-id="44899-291">執行下列命令，以重新啟用單一項目復原。</span><span class="sxs-lookup"><span data-stu-id="44899-291">Run the following command to re-enable single item recovery.</span></span>
   
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. <span data-ttu-id="44899-292">執行下列命令，以重新啟用信箱的所有用戶端存取方法。</span><span class="sxs-lookup"><span data-stu-id="44899-292">Run the following command to re-enable all client access methods to the mailbox.</span></span>
    
    ```
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```
   
4. <span data-ttu-id="44899-293">重新套用您在步驟 3 中移除保留。</span><span class="sxs-lookup"><span data-stu-id="44899-293">Re-apply the holds that you removed in Step 3.</span></span> <span data-ttu-id="44899-294">根據保留的類型，使用下列程序之一。</span><span class="sxs-lookup"><span data-stu-id="44899-294">Depending on the type of hold, use one of the following procedures.</span></span>
    
    <span data-ttu-id="44899-295">**訴訟資料暫留**</span><span class="sxs-lookup"><span data-stu-id="44899-295">**Litigation Hold**</span></span>
    
    <span data-ttu-id="44899-296">執行下列命令，以重新啟用 [訴訟暫止的信箱。</span><span class="sxs-lookup"><span data-stu-id="44899-296">Run the following command to re-enable a Litigation Hold for the mailbox.</span></span>
    
    ```
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    <span data-ttu-id="44899-297">**原有範圍暫止**</span><span class="sxs-lookup"><span data-stu-id="44899-297">**In-Place Hold**</span></span>
    
    <span data-ttu-id="44899-298">使用 EAC （或 Exchange Online PowerShell），若要將信箱新增至 「 就地保留 」 狀態。</span><span class="sxs-lookup"><span data-stu-id="44899-298">Use the EAC (or Exchange Online PowerShell) to add the mailbox back to the In-Place Hold.</span></span> 
    
    <span data-ttu-id="44899-299">**Office 365 保留原則套用至特定信箱**</span><span class="sxs-lookup"><span data-stu-id="44899-299">**Office 365 retention policies applied to specific mailboxes**</span></span>
    
    <span data-ttu-id="44899-300">若要將信箱新增至保留原則使用安全性 & 合規性中心。</span><span class="sxs-lookup"><span data-stu-id="44899-300">Use the Security & Compliance Center to add the mailbox back to the retention policy.</span></span> <span data-ttu-id="44899-301">移至**日期控管**\>安全性 & 合規性中心內的**保留**頁面編輯保留原則，並將信箱新增至保留原則套用至收件者清單。</span><span class="sxs-lookup"><span data-stu-id="44899-301">Go to the **Date governance** \> **Retention** page in the Security & Compliance Center, edit the retention policy, and add the mailbox back to the list of recipients that the retention policy is applied to.</span></span> 
    
    <span data-ttu-id="44899-302">**整個組織的 Office 365 保留原則**</span><span class="sxs-lookup"><span data-stu-id="44899-302">**Organization-wide Office 365 retention policies**</span></span>
    
    <span data-ttu-id="44899-303">如果您藉由排除從原則移除整個組織或 Exchange 全保留原則，然後使用安全性 & 規範中心移除排除的使用者清單中的信箱。</span><span class="sxs-lookup"><span data-stu-id="44899-303">If you removed an organization-wide or Exchange-wide retention policy by excluding it from the policy, then use the Security & Compliance Center to remove the mailbox from the list of excluded users.</span></span> <span data-ttu-id="44899-304">移至**日期控管**\>安全性 & 合規性中心內的**保留**頁面編輯全組織保留原則，並從排除的收件者清單中移除信箱。</span><span class="sxs-lookup"><span data-stu-id="44899-304">Go to the **Date governance** \> **Retention** page in the Security & Compliance Center, edit the organization-wide retention policy, and remove the mailbox from the list of excluded recipients.</span></span> <span data-ttu-id="44899-305">執行此動作將會重新將保留原則套用至使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="44899-305">Doing this will re-apply the retention policy to the user's mailbox.</span></span> 
    
    <span data-ttu-id="44899-306">**eDiscovery 案件保留**</span><span class="sxs-lookup"><span data-stu-id="44899-306">**eDiscovery case holds**</span></span>
    
    <span data-ttu-id="44899-307">使用安全性 & 合規性中心新增信箱後保留與 eDiscovery 案例相關聯。</span><span class="sxs-lookup"><span data-stu-id="44899-307">Use the Security & Compliance Center to add the mailbox back the hold that's associated with an eDiscovery case.</span></span> <span data-ttu-id="44899-308">移至**電子文件探索** \> **eDiscovery** ] 頁面上，開啟案例，並將信箱新增至保留。</span><span class="sxs-lookup"><span data-stu-id="44899-308">Go to the **eDiscovery** \> **eDiscovery** page, open the case, and add the mailbox back to the hold.</span></span> 
    
5. <span data-ttu-id="44899-309">執行下列命令，以允許受管理的資料夾助理員處理信箱一次。</span><span class="sxs-lookup"><span data-stu-id="44899-309">Run the following command to allow the Managed Folder Assistant to process the mailbox again.</span></span> <span data-ttu-id="44899-310">如先前所述，我們建議您等候 24 小時後重新套用保留或 Office 365 保留原則 （並確認它已經準備就緒） 重新啟用受管理的資料夾助理員之前。</span><span class="sxs-lookup"><span data-stu-id="44899-310">As previously stated, we recommend that you wait 24 hours after re-applying a hold or Office 365 retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant.</span></span> 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```
   
6. <span data-ttu-id="44899-311">若要確認信箱已要還原為其先前的設定，您可以執行下列命令，並再比較到您在步驟 1 中所收集的設定。</span><span class="sxs-lookup"><span data-stu-id="44899-311">To verify that the mailbox has been reverted back to its previous configuration, you can run the following commands and then compare the settings to the ones that you collected in Step 1.</span></span>

    ```
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```
  
## <a name="more-information"></a><span data-ttu-id="44899-312">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="44899-312">More information</span></span>

<span data-ttu-id="44899-313">以下是描述如何識別不同類型的保留根據*InPlaceHolds*屬性中的值，當您執行**Get-mailbox**或**Get-organizationconfig**指令程式時的資料表。</span><span class="sxs-lookup"><span data-stu-id="44899-313">Here's a table that describes how to identify different types of holds based on the values in the  *InPlaceHolds*  property when you run the **Get-Mailbox** or **Get-OrganizationConfig** cmdlets.</span></span> <span data-ttu-id="44899-314">如需詳細資訊，請參閱 <<c0>如何識別的型別保留放在 Exchange Online 信箱。</span><span class="sxs-lookup"><span data-stu-id="44899-314">For more detailed information, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>

<span data-ttu-id="44899-315">如先前所述，您必須移除所有保留，並從信箱之前的 Office 365 保留原則可以成功刪除 [可復原的項目] 資料夾中的項目。</span><span class="sxs-lookup"><span data-stu-id="44899-315">As previously explained, you have to remove all holds and Office 365 retention policies from a mailbox before you can successfully delete items in the Recoverable Items folder.</span></span> 
  
|<span data-ttu-id="44899-316">**保留類型**</span><span class="sxs-lookup"><span data-stu-id="44899-316">**Hold type**</span></span>|<span data-ttu-id="44899-317">**範例值**</span><span class="sxs-lookup"><span data-stu-id="44899-317">**Example value**</span></span>|<span data-ttu-id="44899-318">**如何找出保留**</span><span class="sxs-lookup"><span data-stu-id="44899-318">**How to identify the hold**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="44899-319">訴訟資料暫留</span><span class="sxs-lookup"><span data-stu-id="44899-319">Litigation Hold</span></span>  <br/> | `True` <br/> |<span data-ttu-id="44899-320">*LitigationHoldEnabled*屬性設為`True`。</span><span class="sxs-lookup"><span data-stu-id="44899-320">The  *LitigationHoldEnabled*  property is set to  `True`.</span></span>  <br/> |
|<span data-ttu-id="44899-321">原有範圍暫止</span><span class="sxs-lookup"><span data-stu-id="44899-321">In-Place Hold</span></span>  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |<span data-ttu-id="44899-322">*InPlaceHolds*屬性包含信箱處於就地保留的 GUID。</span><span class="sxs-lookup"><span data-stu-id="44899-322">The  *InPlaceHolds*  property contains the GUID of the In-Place Hold that's placed on the mailbox.</span></span> <span data-ttu-id="44899-323">您可以告訴這是在原有範圍暫止因為 GUID 不會啟動與前置詞。</span><span class="sxs-lookup"><span data-stu-id="44899-323">You can tell this is an In-Place Hold because the GUID doesn't start with a prefix.</span></span>  <br/> <span data-ttu-id="44899-324">您可以使用`Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL`以取得有關 「 就地保留 」 狀態的資訊在信箱上的 Exchange Online PowerShell 中的命令。</span><span class="sxs-lookup"><span data-stu-id="44899-324">You can use the  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` command in Exchange Online PowerShell to get information about the In-Place Hold on the mailbox.</span></span>  <br/> |
| <span data-ttu-id="44899-325">安全性 & 合規性中心中的 office 365 保留原則套用至特定信箱</span><span class="sxs-lookup"><span data-stu-id="44899-325">Office 365 retention policies in the Security & Compliance Center applied to specific mailboxes</span></span>  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> <span data-ttu-id="44899-326">或</span><span class="sxs-lookup"><span data-stu-id="44899-326">or</span></span>  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |<span data-ttu-id="44899-327">當您執行**Get-mailbox**指令程式時， *InPlaceHolds*屬性也會包含 Guid 的 Office 365 保留原則套用到信箱。</span><span class="sxs-lookup"><span data-stu-id="44899-327">When you run the **Get-Mailbox** cmdlet, the  *InPlaceHolds*  property also contains GUIDs of Office 365 retention policies applied to the mailbox.</span></span> <span data-ttu-id="44899-328">您可以識別保留原則，因為 GUID 開頭`mbx`前置詞。</span><span class="sxs-lookup"><span data-stu-id="44899-328">You can identify retention policies because the GUID starts with the  `mbx` prefix.</span></span> <span data-ttu-id="44899-329">請注意，如果保留原則的 GUID 開頭`skp`前置詞，表示保留原則套用至 Skype for Business 交談。</span><span class="sxs-lookup"><span data-stu-id="44899-329">Note that if the GUID of the retention policy starts with the  `skp` prefix, that indicates that the retention policy is applied to Skype for Business conversations.</span></span>  <br/> <span data-ttu-id="44899-330">套用到信箱的身分識別 Office 365 保留原則，請在安全性 & 合規性中心 PowerShell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="44899-330">To identity the Office 365 retention policy that's applied to the mailbox, run the following command in Security & Compliance Center PowerShell:</span></span> <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/><span data-ttu-id="44899-331">請務必移除`mbx`或`skp`當您執行此命令的前置詞。</span><span class="sxs-lookup"><span data-stu-id="44899-331">Be sure to remove the  `mbx` or  `skp` prefix when you run this command.</span></span>  <br/> |
|<span data-ttu-id="44899-332">安全性 & 合規性中心中的全組織的 Office 365 保留原則</span><span class="sxs-lookup"><span data-stu-id="44899-332">Organization-wide Office 365 retention policies in the Security & Compliance Center</span></span>  <br/> |<span data-ttu-id="44899-333">沒有值</span><span class="sxs-lookup"><span data-stu-id="44899-333">No value</span></span>  <br/> <span data-ttu-id="44899-334">或</span><span class="sxs-lookup"><span data-stu-id="44899-334">or</span></span>  <br/>  <span data-ttu-id="44899-335">`-mbxe9b52bf7ab3b46a286308ecb29624696`（表示信箱已排除的全組織原則）</span><span class="sxs-lookup"><span data-stu-id="44899-335">`-mbxe9b52bf7ab3b46a286308ecb29624696` (indicates that the mailbox is excluded from an organization-wide policy)</span></span>  <br/> |<span data-ttu-id="44899-336">即使*InPlaceHolds*屬性是空的當您執行**Get-mailbox**指令程式時，仍可能有一或多個全組織的 Office 365 保留原則套用到信箱。</span><span class="sxs-lookup"><span data-stu-id="44899-336">Even if the  *InPlaceHolds*  property is empty when you run the **Get-Mailbox** cmdlet, there still might be one or more organization-wide Office 365 retention policies applied to the mailbox.</span></span>  <br/> <span data-ttu-id="44899-337">若要確認此，您可以執行`Get-OrganizationConfig | FL InPlaceHolds`命令在 Exchange Online PowerShell，以取得整個組織的 Office 365 保留原則 Guid 的清單。</span><span class="sxs-lookup"><span data-stu-id="44899-337">To verify this, you can run the  `Get-OrganizationConfig | FL InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Office 365 retention policies.</span></span> <span data-ttu-id="44899-338">整個組織的保留原則套用至 Exchange 信箱的開頭的 GUID`mbx`字首;例如`mbxa3056bb15562480fadb46ce523ff7b02`。</span><span class="sxs-lookup"><span data-stu-id="44899-338">The GUID for organization-wide retention policies applied to Exchange mailboxes start with the  `mbx` prefix; for example  `mbxa3056bb15562480fadb46ce523ff7b02`.</span></span>  <br/> <span data-ttu-id="44899-339">身分識別全組織的 Office 365 保留原則套用到信箱，請在安全性 & 合規性中心 PowerShell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="44899-339">To identity the organization-wide Office 365 retention policy that's applied to the mailbox, run the following command in Security & Compliance Center PowerShell:</span></span> <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/><span data-ttu-id="44899-340">請注意，是否從整個組織的 Office 365 保留原則中排除信箱，保留原則的 GUID 會顯示在使用者信箱的*InPlaceHolds*屬性當您執行**Get-mailbox**指令程式;它由前置詞`-mbx`;例如，`-mbxe9b52bf7ab3b46a286308ecb29624696`</span><span class="sxs-lookup"><span data-stu-id="44899-340">Note that if a mailbox is excluded from an organization-wide Office 365 retention policy, the GUID for the retention policy is displayed in the  *InPlaceHolds*  property of the user's mailbox when you run the **Get-Mailbox** cmdlet; it's identified by the prefix  `-mbx`; for example,  `-mbxe9b52bf7ab3b46a286308ecb29624696`</span></span> <br/> |
|<span data-ttu-id="44899-341">安全性 & 合規性中心中保留電子文件探索案例</span><span class="sxs-lookup"><span data-stu-id="44899-341">eDiscovery case hold in the Security & Compliance Center</span></span>  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |<span data-ttu-id="44899-342">*InPlaceHolds*屬性也會包含任何保留在 [安全性 & 也可能會放置在信箱的合規性中心 eDiscovery 案例相關聯的 GUID。</span><span class="sxs-lookup"><span data-stu-id="44899-342">The  *InPlaceHolds*  property also contains the GUID of any hold associated with an eDiscovery case in the Security & Compliance Center that might be placed on the mailbox.</span></span> <span data-ttu-id="44899-343">您可以分清這是 eDiscovery 案例保留，因為 GUID 開頭`UniH`前置詞。</span><span class="sxs-lookup"><span data-stu-id="44899-343">You can tell this is an eDiscovery case hold because the GUID starts with the  `UniH` prefix.</span></span>  <br/> <span data-ttu-id="44899-344">您可以使用`Get-CaseHoldPolicy`安全性 & 來取得信箱上的保留相關聯的 eDiscovery 案例的相關資訊的合規性中心 PowerShell 中的指令程式。</span><span class="sxs-lookup"><span data-stu-id="44899-344">You can use the  `Get-CaseHoldPolicy` cmdlet in Security & Compliance Center PowerShell to get information about the eDiscovery case that the hold on the mailbox is associated with.</span></span> <span data-ttu-id="44899-345">例如，您可以執行此命令`Get-CaseHoldPolicy <hold GUID without prefix> | FL Name`來顯示在信箱上的案例保留的名稱。</span><span class="sxs-lookup"><span data-stu-id="44899-345">For example, you can run the command  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` to display the name of the case hold that's on the mailbox.</span></span> <span data-ttu-id="44899-346">請務必移除`UniH`當您執行此命令的前置詞。</span><span class="sxs-lookup"><span data-stu-id="44899-346">Be sure to remove the  `UniH` prefix when you run this command.</span></span>  <br/><br/> <span data-ttu-id="44899-347">身分識別與相關聯的信箱上保留的 eDiscovery 案例中，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="44899-347">To identity the eDiscovery case that the hold on the mailbox is associated with, run the following commands:</span></span><br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`


