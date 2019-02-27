---
title: 刪除項目可復原的項目] 資料夾中的雲端架構信箱保留-Admin 說明
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
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
description: 系統管理員： 即使該信箱處於合法持有刪除 Exchange Online 的信箱使用者的可復原的項目] 資料夾中的項目。這是有效的方式刪除已意外溢出至 Office 365 的資料。
ms.openlocfilehash: 4b7b12b33a2364d76b5d7dab6c7e94dc8f00d151
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296176"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold---admin-help"></a><span data-ttu-id="1838a-104">刪除項目可復原的項目] 資料夾中的雲端架構信箱保留-Admin 說明</span><span class="sxs-lookup"><span data-stu-id="1838a-104">Delete items in the Recoverable Items folder of cloud-based mailboxes on hold - Admin Help</span></span>

<span data-ttu-id="1838a-p102">若要防止意外或惡意刪除存在於 Exchange Online 信箱 [可復原的項目] 資料夾。它也用來儲存都會保留且存取 Office 365 規範功能，例如保留和 eDiscovery 搜尋的項目。不過，在某些情況下組織可能會有已不小心保留在他們必須刪除 [可復原的項目] 資料夾中的資料。例如，使用者可能不知情的情況下傳送或轉寄電子郵件包含敏感資訊或可能會有嚴重商務後果的資訊。即使永久刪除郵件，則可能會保留無限期因為合法持有放置在信箱。此案例中稱為資料 spillage 因為資料不小心溢出至 Office 365。在下列情況下，您可以刪除 Exchange Online 的信箱使用者的可復原的項目] 資料夾中的項目即使該信箱處於保留狀態使用其中一個 Office 365 中的不同保留功能。這些類型的保留包括訴訟保留、 就地保留、 eDiscovery 保留及 Office 365 保留原則建立 Office 365 安全性&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="1838a-p102">The Recoverable Items folder for an Exchange Online mailbox exists to protect from accidental or malicious deletions. It's also used to store items that are retained and accessed by Office 365 compliance features, such as holds and eDiscovery searches. However, in some situations organizations might have data that's been unintentionally retained in the Recoverable Items folder that they must delete. For example, a user might unknowingly send or forward an email message that contains sensitive information or information that may have serious business consequences. Even if the message is permanently deleted, it might be retained indefinitely because a legal hold has been placed on the mailbox. This scenario is known as data spillage because data has been unintentionally spilled into Office 365. In these situations, you can delete items in a user's Recoverable Items folder for an Exchange Online mailbox, even if that mailbox is placed on hold with one of the different hold features in Office 365. These types of holds include Litigation Holds, In-Place Holds, eDiscovery holds, and Office 365 retention policies created in the Office 365 Security &amp; Compliance Center.</span></span> 
  
 <span data-ttu-id="1838a-p103">本文說明如何從所保留的雲端架構信箱 [可復原的項目] 資料夾刪除項目。此程序包括停用信箱的存取權和停用單一項目復原，停用受管理的資料夾助理員處理信箱、 暫時移除保留，從 [可復原的項目] 資料夾刪除項目及再回復以其先前的設定信箱。以下是程序：</span><span class="sxs-lookup"><span data-stu-id="1838a-p103">This article explains how to delete items from the Recoverable Items folder for cloud-based mailboxes that are on hold. This procedure involves disabling access to the mailbox and disabling single item recovery, disabling the Managed Folder Assistant from processing the mailbox, temporarily removing the hold, deleting items from the Recoverable Items folder, and then reverting the mailbox to its previous configuration. Here's the process:</span></span> 
  
[<span data-ttu-id="1838a-116">步驟 1： 收集信箱的相關資訊</span><span class="sxs-lookup"><span data-stu-id="1838a-116">Step 1: Collect information about the mailbox</span></span>](#step-1-collect-information-about-the-mailbox)

[<span data-ttu-id="1838a-117">步驟 2： 準備信箱</span><span class="sxs-lookup"><span data-stu-id="1838a-117">Step 2: Prepare the mailbox</span></span>](#step-2-prepare-the-mailbox)

[<span data-ttu-id="1838a-118">步驟 3： 從信箱移除所有保留</span><span class="sxs-lookup"><span data-stu-id="1838a-118">Step 3: Remove all holds from the mailbox</span></span>](#step-3-remove-all-holds-from-the-mailbox)

[<span data-ttu-id="1838a-119">步驟 4： 從信箱移除延遲保留</span><span class="sxs-lookup"><span data-stu-id="1838a-119">Step 4: Remove the delay hold from the mailbox</span></span>](#step-4-remove-the-delay-hold-from-the-mailbox)

<span data-ttu-id="1838a-120">[步驟 5： 刪除 [可復原的項目] 資料夾中的項目](#step-5-delete-items-in-the-recoverable-items-folder)</span><span class="sxs-lookup"><span data-stu-id="1838a-120">[Step 5: Delete items in the Recoverable Items folder](#step-5-delete-items-in-the-recoverable-items-folder)</span></span>

[<span data-ttu-id="1838a-121">步驟 6： 還原成先前狀態的信箱</span><span class="sxs-lookup"><span data-stu-id="1838a-121">Step 6: Revert the mailbox to its previous state</span></span>](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> <span data-ttu-id="1838a-p104">本文所述的程序會導致資料要永久刪除 （清除） 從 Exchange Online 信箱。這表示您從 [可復原的項目] 資料夾中刪除的郵件無法復原並不會供法律調查或其他規範用途之用。如果您想要刪除的訴訟暫止狀態、 就地保留功能，一部分處於保留狀態的信箱的郵件 eDiscovery 保留，或 Office 365 保留原則建立 Office 365 安全性&amp;規範中心、 記錄管理或法務的核取然後再移除保留的部門。您的組織可能已定義是否在信箱保留原則或建立資料 spillage 事件採用優先順序。</span><span class="sxs-lookup"><span data-stu-id="1838a-p104">The procedures outlined in this article will result in data being permanently deleted (purged) from an Exchange Online mailbox. That means messages that you delete from the Recoverable Items folder can't be recovered and won't be available for legal discovery or other compliance purposes. If you want to delete messages from a mailbox that's placed on hold as part of a Litigation Hold, In-Place Hold, eDiscovery hold, or Office 365 retention policy created in the Office 365 Security &amp; Compliance Center, check with your records management or legal departments before removing the hold. Your organization might have a policy that defines whether a mailbox on hold or a data spillage incident takes priority.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="1838a-126">開始之前</span><span class="sxs-lookup"><span data-stu-id="1838a-126">Before you begin</span></span>

- <span data-ttu-id="1838a-127">您必須指派兩個以下的管理角色在 Exchange Online 來搜尋並刪除 [可復原的項目] 資料夾中之步驟 5 中的郵件。</span><span class="sxs-lookup"><span data-stu-id="1838a-127">You have to be assigned both of the following management roles in Exchange Online to search for and delete messages from the Recoverable Items folder in Step 5.</span></span>
    
  - <span data-ttu-id="1838a-p105">**信箱搜尋**此角色可讓您在組織中搜尋信箱。Exchange 系統管理員未指派此角色預設。若要將自己指派此角色，新增您自己探索管理角色群組的成員身分在 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="1838a-p105">**Mailbox Search** - This role lets you to search mailboxes in your organization. Exchange administrators aren't assigned this role by default. To assign yourself this role, add yourself as a member of the Discovery Management role group in Exchange Online.</span></span> 
    
  - <span data-ttu-id="1838a-p106">**信箱匯入 / 匯出**-此角色可讓您刪除使用者信箱的郵件。根據預設，此角色不被指派給任何角色群組。若要刪除的郵件從使用者的信箱，您可以新增信箱匯入 / 匯出角色至組織管理角色群組在 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="1838a-p106">**Mailbox Import Export** - This role lets you to delete messages from a user's mailbox. By default, this role isn't assigned to any role group. To delete messages from users' mailboxes, you can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> 
    
- <span data-ttu-id="1838a-p107">本文所述的程序不支援的非使用中的信箱。那是因為您無法重新套用保留 （或 Office 365 保留原則） 不在作用中的信箱後您移除。當您從非使用中信箱移除保留時，它會變更為 [正常的虛刪除信箱並會永久刪除從您的組織之後的受管理的資料夾助理員處理。</span><span class="sxs-lookup"><span data-stu-id="1838a-p107">The procedure described in this article isn't supported for inactive mailboxes. That's because you can't re-apply a hold (or Office 365 retention policy) to an inactive mailbox after you remove it. When you remove a hold from an inactive mailbox, it's changed to a normal soft-deleted mailbox and will be permanently deleted from your organization after it's processed by the Managed Folder Assistant.</span></span>
    
- <span data-ttu-id="1838a-p108">您無法執行此程序已指派給已遭鎖定保留鎖定與 Office 365 保留原則的信箱。那是因為保留鎖定會防止您從移除或從 Office 365 保留原則及停用受管理的資料夾助理員信箱中排除信箱。如需鎖定保留原則的詳細資訊，請參閱[鎖定保留原則](retention-policies.md#locking-a-retention-policy)。</span><span class="sxs-lookup"><span data-stu-id="1838a-p108">You can't perform this procedure for a mailbox that has been assigned to an Office 365 retention policy that's been locked with a Preservation Lock. That's because a Preservation Lock prevents you from removing or excluding the mailbox from the Office 365 retention policy and from disabling the Managed Folder Assistant on the mailbox. For more information about locking retention policies, see [Locking a retention policy](retention-policies.md#locking-a-retention-policy).</span></span>
    
- <span data-ttu-id="1838a-p109">如果信箱不處於保留狀態] （或都不會有已啟用單一項目復原） 則您只可以從 [可復原的項目] 資料夾刪除項目。如需如何執行這項作業的詳細資訊，請參閱[搜尋和刪除郵件](https://go.microsoft.com/fwlink/?linkid=852453)。</span><span class="sxs-lookup"><span data-stu-id="1838a-p109">If a mailbox isn't placed on hold (or doesn't have single item recovery enabled), you can simply delete the items from the Recoverable Items folder. For more information about how to do this, see [Search for and delete messages ](https://go.microsoft.com/fwlink/?linkid=852453).</span></span>
  
## <a name="step-1-collect-information-about-the-mailbox"></a><span data-ttu-id="1838a-142">步驟 1： 收集信箱的相關資訊</span><span class="sxs-lookup"><span data-stu-id="1838a-142">Step 1: Collect information about the mailbox</span></span>

<span data-ttu-id="1838a-p110">此第一個步驟是從目標信箱會影響此程序收集所選的屬性。請務必寫下這些設定或儲存至的文字檔案，因為在將變更這些屬性的一些且當您從 [可復原的項目] 資料夾刪除項目之後還原回到步驟 6 中的原始值。以下是您需要收集的信箱內容的清單。</span><span class="sxs-lookup"><span data-stu-id="1838a-p110">This first step is to collect selected properties from the target mailbox that will affect this procedure. Be sure to write down these settings or save them to a text file because you'll change some of these properties and then revert back to the original values in Step 6, after you delete items from the Recoverable Items folder. Here's a list of the mailbox properties you need to collect.</span></span>
  
-  <span data-ttu-id="1838a-146">*SingleItemRecoveryEnabled*和*RetainDeletedItemsFor* ;若有需要，您將會停用單一復原並增加步驟 3 中的已刪除的項目保留期間。</span><span class="sxs-lookup"><span data-stu-id="1838a-146">*SingleItemRecoveryEnabled*  and  *RetainDeletedItemsFor*  ; if necessary, you'll disable single recovery and increase the deleted items retention period in Step 3.</span></span> 
    
-  <span data-ttu-id="1838a-p111">*LitigationHoldEnabled*和*InPlaceHolds* ;您必須識別放置信箱上以便可以暫時移除這些步驟 3 中的所有保留。請參閱如需如何識別可能會被放置在信箱的類型保留的提示[的詳細資訊](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#moreinfo)] 區段。</span><span class="sxs-lookup"><span data-stu-id="1838a-p111">*LitigationHoldEnabled*  and  *InPlaceHolds*  ; you need to identify all the holds placed on the mailbox so that you can temporarily remove them in Step 3. See the [More information](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#moreinfo) section for tips about how to identify the type hold that might be placed on a mailbox.</span></span> 
    
<span data-ttu-id="1838a-p112">此外，您需要取得信箱用戶端存取設定讓您可以暫時停用它們，讓其擁有人 （或其他使用者） 無法在此程序期間存取信箱。最後，您可以在 [可復原的項目] 資料夾中取得目前的大小和項目數。刪除 [可復原的項目] 資料夾中之步驟 5 中的項目之後，您將使用此資訊來確認已真正移除項目。</span><span class="sxs-lookup"><span data-stu-id="1838a-p112">Additionally, you need to get the mailbox client access settings so you can temporarily disable them so the owner (or other users) can't access the mailbox during this procedure. Finally, you can get the current size and number of items in the Recoverable Items folder. After you delete items in the Recoverable Items folder in Step 5, you'll use this information to verify that items were actually removed.</span></span>
  
1. <span data-ttu-id="1838a-p113">[連線到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554)。請務必使用已指派 Exchange Online 中的適當的管理角色的系統管理員帳戶的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="1838a-p113">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554). Be sure to use a user name and password for an administrator account that's been assigned the appropriate management roles in Exchange Online.</span></span> 
    
2. <span data-ttu-id="1838a-154">執行下列命令以取得單一項目復原已刪除的項目保留期間的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="1838a-154">Run the following command to get information about single item recovery and the deleted item retention period.</span></span>

    ```
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   <span data-ttu-id="1838a-p114">如果已啟用單一項目復原，您必須加以停用在步驟 2。如果已刪除的項目保留期間未設定為 30 天 （Exchange Online 中的最大值），則您可增加其在步驟 2。</span><span class="sxs-lookup"><span data-stu-id="1838a-p114">If single item recovery is enabled, you'll have to disable it in Step 2. If the deleted item retention period isn't set for 30 days (the maximum value in Exchange Online), then you can increase it in Step 2.</span></span> 
    
3. <span data-ttu-id="1838a-157">執行下列命令以取得信箱的信箱的存取設定。</span><span class="sxs-lookup"><span data-stu-id="1838a-157">Run the following command to get the mailbox access settings for the mailbox.</span></span> 
    
    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   <span data-ttu-id="1838a-158">您將會停用所有的這些步驟 2 中的存取方法。</span><span class="sxs-lookup"><span data-stu-id="1838a-158">You'll disable all of these access methods in Step 2.</span></span>
    
4. <span data-ttu-id="1838a-159">執行下列命令以取得保留及 Office 365 保留原則套用至信箱的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="1838a-159">Run the following command to get information about the holds and Office 365 retention policies applied to the mailbox.</span></span>
    
    ```
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```


   > [!TIP]
    > <span data-ttu-id="1838a-160">如果*InPlaceHolds*屬性中有太多值並不是所有的顯示，則可以執行`Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds`命令以顯示每個值以一行。</span><span class="sxs-lookup"><span data-stu-id="1838a-160">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span> 
  
5. <span data-ttu-id="1838a-161">執行下列命令來取得任何整個組織的 Office 365 保留原則的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="1838a-161">Run the following command to get information about any organization-wide Office 365 retention policies.</span></span> 

    ```
    Get-OrganizationConfig | FL InPlaceHolds
    ```
   <span data-ttu-id="1838a-162">如果您的組織有任何整個組織的 Office 365 的保留原則，您必須從步驟 3 中的這些原則中排除信箱。</span><span class="sxs-lookup"><span data-stu-id="1838a-162">If your organization has any organization-wide Office 365 retention policies, you'll have to exclude the mailbox from these policies in Step 3.</span></span>

   > [!TIP]
    > <span data-ttu-id="1838a-163">如果*InPlaceHolds*屬性中有太多值並不是所有的顯示，則可以執行`Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`命令以顯示每個值以一行。</span><span class="sxs-lookup"><span data-stu-id="1838a-163">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span> 
  
6. <span data-ttu-id="1838a-164">執行下列命令以取得目前的大小和項目總數資料夾和使用者的主要信箱中 [可復原的項目] 資料夾中的子資料夾中。</span><span class="sxs-lookup"><span data-stu-id="1838a-164">Run the following command to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span> 

    ```
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="1838a-165">如果已啟用使用者的封存信箱，執行下列命令以取得資料夾和封存信箱中 [可復原的項目] 資料夾中的子資料夾中的大小和項目總數。</span><span class="sxs-lookup"><span data-stu-id="1838a-165">If the user's archive mailbox is enabled, run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in their archive mailbox.</span></span> 

    ```s
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="1838a-p115">當您刪除項目在步驟 5 中時，您可以選擇刪除或刪除使用者的主要封存信箱中 [可復原的項目] 資料夾中的項目。請注意是否啟用自動展開封存信箱，將不會被刪除輔助封存信箱中的項目。</span><span class="sxs-lookup"><span data-stu-id="1838a-p115">When you delete items in Step 5, you can choose to delete or not delete items in the Recoverable Items folder in the user's primary archive mailbox. Note that if auto-expanding archiving is enabled for the mailbox, items in an auxiliary archive mailbox won't be deleted.</span></span>
  
## <a name="step-2-prepare-the-mailbox"></a><span data-ttu-id="1838a-168">步驟 2： 準備信箱</span><span class="sxs-lookup"><span data-stu-id="1838a-168">Step 2: Prepare the mailbox</span></span>

<span data-ttu-id="1838a-169">收集並之後儲存信箱的相關資訊下, 一步是執行下列工作以準備信箱：</span><span class="sxs-lookup"><span data-stu-id="1838a-169">After collecting and saving information about the mailbox, the next step is to prepare the mailbox by performing the following tasks:</span></span> 
  
- <span data-ttu-id="1838a-170">**停用信箱的用戶端存取**信箱擁有者無法存取其信箱和信箱資料進行任何變更此程序期間。</span><span class="sxs-lookup"><span data-stu-id="1838a-170">**Disable client access to mailbox** so that the mailbox owner can't access their mailbox and make any changes to the mailbox data during this procedure.</span></span> 
    
- <span data-ttu-id="1838a-171">**提高刪除項目保留期間**為 30 天 （Exchange Online 中的最大值），讓才能刪除這些步驟 5 中將項目未從 [可復原的項目] 資料夾清除。</span><span class="sxs-lookup"><span data-stu-id="1838a-171">**Increase the deleted item retention period** to 30 days (the maximum value in Exchange Online) so that items aren't purged from the Recoverable Items folder before you can delete them in Step 5.</span></span> 
    
- <span data-ttu-id="1838a-172">**停用單一項目復原**的項目因此將不會保留 （適用於已刪除的項目保留期間的持續期間） 之後您刪除 [可復原的項目] 資料夾中之步驟 5。</span><span class="sxs-lookup"><span data-stu-id="1838a-172">**Disable single Item recovery** so that items won't be retained (for the duration of the deleted item retention period) after you delete them from the Recoverable Items folder in Step 5.</span></span> 
    
- <span data-ttu-id="1838a-173">**停用受管理的資料夾助理員**，讓它不會處理的信箱並保留您在步驟 5 中刪除的項目。</span><span class="sxs-lookup"><span data-stu-id="1838a-173">**Disable the Managed Folder Assistant** so that it doesn't process the mailbox and retain the items that you delete in Step 5.</span></span> 
    
<span data-ttu-id="1838a-174">在 Exchange Online PowerShell 中執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="1838a-174">Perform the following steps in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="1838a-p116">執行下列命令以停用所有的用戶端存取信箱。命令語法假設所有用戶端存取方法已啟用信箱。</span><span class="sxs-lookup"><span data-stu-id="1838a-p116">Run the following command to disable all client access to the mailbox. The command syntax assumes that all client access methods were enabled on the mailbox.</span></span>

    ```   
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```
   
   > [!NOTE]
    > <span data-ttu-id="1838a-p117">可能需要停用信箱的所有用戶端存取方法最多 60 分鐘。請注意停用這些存取方法不會中斷連線信箱擁有者他們目前登入。如果擁有者無法登入，然後將不會加以能夠存取其信箱之後已停用這些存取方法。</span><span class="sxs-lookup"><span data-stu-id="1838a-p117">It might take up to 60 minutes to disable all client access methods to the mailbox. Note that disabling these access methods won't disconnect the mailbox owner they're currently signed in. If the owner isn't signed in, then they won't be able to access their mailbox after these access methods are disabled.</span></span> 
  
2. <span data-ttu-id="1838a-p118">執行下列命令，以提高刪除項目保留期間的 30 天的最大值。這是假設目前的設定是早於 30 天。</span><span class="sxs-lookup"><span data-stu-id="1838a-p118">Run the following command to increase the deleted item retention period the maximum of 30 days. This assumes that the current setting is less than 30 days.</span></span> 

    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. <span data-ttu-id="1838a-182">執行下列命令以停用單一項目復原。</span><span class="sxs-lookup"><span data-stu-id="1838a-182">Run the following command to disable single item recovery.</span></span>
    
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

   > [!NOTE]
    > <span data-ttu-id="1838a-p119">可能需要停用單一項目復原最多 60 分鐘。等到此期間經過不刪除 [可復原的項目] 資料夾中的項目。</span><span class="sxs-lookup"><span data-stu-id="1838a-p119">It might take up to 60 minutes to disable single item recovery. Don't delete items in the Recoverable Items folder until this period has elapsed.</span></span> 
  
4. <span data-ttu-id="1838a-p120">執行下列命令，以防止受管理的資料夾助理員處理信箱。如先前所述，您可以停用受管理的資料夾助理員只有當保留鎖定 Office 365 保留原則不會套用至信箱。</span><span class="sxs-lookup"><span data-stu-id="1838a-p120">Run the following command to prevent the Managed Folder Assistant from processing the mailbox. As previously explained, you can disable the Managed Folder Assistant only if an Office 365 retention policy with a Preservation Lock is not applied to the mailbox.</span></span> 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a><span data-ttu-id="1838a-187">步驟 3： 從信箱移除所有保留</span><span class="sxs-lookup"><span data-stu-id="1838a-187">Step 3: Remove all holds from the mailbox</span></span>

<span data-ttu-id="1838a-p121">您可以從 [可復原的項目] 資料夾刪除項目之前的最後一個步驟是要移除所有保留 （即您在步驟 1 中識別） 信箱。如此當您從 [可復原的項目] 資料夾刪除之後將不會保留項目必須移除所有保留。下列各節包含移除不同類型的保留在信箱上的相關資訊。請參閱如需如何識別可能會被放置在信箱的類型保留的提示[的詳細資訊](#more-information)] 區段。如需詳細資訊，請參閱[如何識別的類型保留放在 Exchange Online 信箱](identify-a-hold-on-an-exchange-online-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="1838a-p121">The last step before you can delete items from the Recoverable Items folder is to remove all holds (that you identified in Step 1) placed on the mailbox. All holds must be removed so that items won't be retained after you delete them from the Recoverable Items folder. The following sections contain information about removing different types of holds on a mailbox. See the [More information](#more-information) section for tips about how to identify the type hold that might be placed on a mailbox. For additional information, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="1838a-193">先前所述，取出與記錄管理或法務部門才可從信箱移除保留。</span><span class="sxs-lookup"><span data-stu-id="1838a-193">As previously stated, check with your records management or legal departments before removing a hold from a mailbox.</span></span> 
  
 ### <a name="litigation-hold"></a><span data-ttu-id="1838a-194">訴訟暫止</span><span class="sxs-lookup"><span data-stu-id="1838a-194">Litigation Hold</span></span>
  
<span data-ttu-id="1838a-195">執行下列命令在 Exchange Online PowerShell 從信箱移除訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="1838a-195">Run the following command in Exchange Online PowerShell to remove a Litigation Hold from the mailbox.</span></span>

```
Set-Mailbox <username> -LitigationHoldEnabled $false
```

   
> [!NOTE]
> <span data-ttu-id="1838a-p122">類似停用用戶端存取方法和單一項目復原，則可能需要最多 60 分鐘移除訴訟暫止狀態。直到經過此期間從 [可復原的項目] 資料夾不刪除項目。</span><span class="sxs-lookup"><span data-stu-id="1838a-p122">Similar to disabling the client access methods and single item recovery, it might take up to 60 minutes to remove the Litigation Hold. Don't delete items from the Recoverable Items folder until this period has elapsed.</span></span> 
  
 ### <a name="in-place-hold"></a><span data-ttu-id="1838a-198">原有範圍暫止</span><span class="sxs-lookup"><span data-stu-id="1838a-198">In-Place Hold</span></span>
  
<span data-ttu-id="1838a-p123">執行下列命令在 Exchange Online PowerShell 來識別信箱處於就地保留。使用您在步驟 1 中識別為 「 就地保留 GUID。</span><span class="sxs-lookup"><span data-stu-id="1838a-p123">Run the following command in Exchange Online PowerShell to identify the In-Place Hold that's placed on the mailbox. Use the GUID for the In-Place Hold that you identified in Step 1.</span></span> 

```
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```
   
<span data-ttu-id="1838a-p124">在識別為 「 就地保留之後，您可以使用 Exchange 系統管理中心 (EAC) 或 Exchange Online PowerShell 從保留移除信箱。如需詳細資訊，請參閱[建立或移除就地保留](https://go.microsoft.com/fwlink/?linkid=852668)。</span><span class="sxs-lookup"><span data-stu-id="1838a-p124">After you identify the In-Place Hold, you can use the Exchange admin center (EAC) or Exchange Online PowerShell to remove the mailbox from the hold. For more information, see [Create or remove an In-Place Hold](https://go.microsoft.com/fwlink/?linkid=852668).</span></span>
  
 ### <a name="office-365-retention-policies-applied-to-specific-mailboxes"></a><span data-ttu-id="1838a-203">Office 365 的保留原則套用至特定信箱</span><span class="sxs-lookup"><span data-stu-id="1838a-203">Office 365 retention policies applied to specific mailboxes</span></span>
  
<span data-ttu-id="1838a-p125">執行下列命令[Office 365 安全性&amp;規範中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)識別 Office 365 保留原則套用至信箱。使用 GUID (不包括`mbx`或`skp`字首) 您在步驟 1 中所識別的保留原則。</span><span class="sxs-lookup"><span data-stu-id="1838a-p125">Run the following command in [Office 365 Security &amp; Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the Office 365 retention policy that is applied to the mailbox. Use the GUID (not including the  `mbx` or  `skp` prefix) for the retention policy that you identified in Step 1.</span></span> 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```
   
<span data-ttu-id="1838a-206">識別保留原則之後，請移至**日期控管** \> **保留**] 頁面的 [安全性] 中&amp;規範中心編輯您在上一個步驟中識別的保留原則及移除清單中的信箱收件者所包含的保留原則。</span><span class="sxs-lookup"><span data-stu-id="1838a-206">After you identify the retention policy, go to the **Date governance** \> **Retention** page in the Security &amp; Compliance Center, edit the retention policy that you identified in the previous step, and remove the mailbox from the list of recipients that are included in the retention policy.</span></span> 
  
 ### <a name="organization-wide-office-365-retention-policies"></a><span data-ttu-id="1838a-207">Office 365 全組織的保留原則</span><span class="sxs-lookup"><span data-stu-id="1838a-207">Organization-wide Office 365 retention policies</span></span>
  
<span data-ttu-id="1838a-p126">全組織與 Exchange 全 Office 365 的保留原則套用至組織中每個信箱。他們在組織層級 （而不是信箱層級） 套用，且當您在步驟 1 中執行**Get-organizationconfig**指令程式會傳回。執行下列命令[安全性&amp;規範中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)識別全組織的 Office 365 保留原則。使用 GUID (不包括`mbx`字首) 您在步驟 1 中識別之整個組織的保留原則。</span><span class="sxs-lookup"><span data-stu-id="1838a-p126">Organization-wide and Exchange-wide Office 365 retention policies are applied to every mailbox in the organization. They are applied at the organization level (not the mailbox level) and are returned when you run the **Get-OrganizationConfig** cmdlet in Step 1. Run the following command in [Security &amp; Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the organization-wide Office 365 retention policies. Use the GUID (not including the  `mbx` prefix) for the organization-wide retention policies that you identified in Step 1.</span></span> 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

<span data-ttu-id="1838a-p127">識別全組織的 Office 365 保留原則之後，請移至**日期控管** \> **保留**] 頁面的 [安全性] 中&amp;規範中心編輯中識別的每個整個組織的保留原則上一個步驟，並將信箱新增至已排除的收件者的清單。執行此動作會從保留原則中移除使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="1838a-p127">After you identify the organization-wide Office 365 retention policies, go to the **Date governance** \> **Retention** page in the Security &amp; Compliance Center, edit each organization-wide retention policy that you identified in the previous step, and add the mailbox to the list of excluded recipients. Doing this will remove the user's mailbox from the retention policy.</span></span> 

### <a name="office-365-retention-labels"></a><span data-ttu-id="1838a-214">Office 365 保留標籤</span><span class="sxs-lookup"><span data-stu-id="1838a-214">Office 365 retention labels</span></span>

<span data-ttu-id="1838a-p128">每當使用者套用設定成保留內容或保留與再刪除任何資料夾或信箱中的項目內容的標籤、 *ComplianceTagHoldApplied*信箱屬性是設定為**True**。在這種情況下，信箱會被視為在保留，就如同它已處於訴訟暫止狀態或指派給 Office 365 保留原則。</span><span class="sxs-lookup"><span data-stu-id="1838a-p128">Whenever a user applies a label that's configured to retain content or retain and then delete content to any folder or item in their mailbox, the *ComplianceTagHoldApplied* mailbox property is set to **True**. When this happens, the mailbox is considered to be on hold, just as if it was placed on Litigation Hold or assigned to an Office 365 retention policy.</span></span>

<span data-ttu-id="1838a-217">若要檢視*ComplianceTagHoldApplied*屬性的值，請在 Exchange Online PowerShell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="1838a-217">To view the value of the *ComplianceTagHoldApplied* property, run the following command in Exchange Online PowerShell:</span></span>

```
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

<span data-ttu-id="1838a-p129">您已識別信箱是保留因為保留標籤套用到資料夾或項目之後，您可以使用安全性 & 規範中心中的內容搜尋工具來使用 ComplianceTag 搜尋條件來搜尋已標記的項目。如需詳細資訊，請參閱 「 搜尋條件 」 一節[關鍵字查詢](keyword-queries-and-search-conditions.md#conditions-for-common-properties)和搜尋條件的內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="1838a-p129">After you've identified that a mailbox is on hold because a retention label is applied to a folder or item, you can use the Content Search tool in the Security & Compliance Center to search for labeled items by using the ComplianceTag search condition. For more information, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md#conditions-for-common-properties).</span></span>

<span data-ttu-id="1838a-220">如需標籤的詳細資訊，請參閱[Office 365 概觀 （英文) 標籤](labels.md)。</span><span class="sxs-lookup"><span data-stu-id="1838a-220">For more information about labels, see [Overview of Office 365 labels](labels.md).</span></span>

 ### <a name="ediscovery-case-holds"></a><span data-ttu-id="1838a-221">保留 eDiscovery 案例</span><span class="sxs-lookup"><span data-stu-id="1838a-221">eDiscovery case holds</span></span>
  
<span data-ttu-id="1838a-p130">執行下列命令[安全性&amp;規範中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)識別保留套用到信箱的 eDiscovery 案例相關聯。使用 GUID (不包括`UniH`前置詞) 的 ediscovery （英文） 保留您在步驟 1 中識別。請注意第二個命令會顯示保留相關聯; eDiscovery 案例的名稱第三個命令會顯示的保留名稱。</span><span class="sxs-lookup"><span data-stu-id="1838a-p130">Run the following commands in [Security &amp; Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the hold associated with an eDiscovery case that's applied to the mailbox. Use the GUID (not including the  `UniH` prefix) for the eDiscovery hold that you identified in Step 1. Note that the second command displays the name of the eDiscovery case the hold is associated with; the third command displays the name of the hold.</span></span> 
  
```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```
$CaseHold.Name
```

<span data-ttu-id="1838a-p131">您已識別的 eDiscovery 案例及保留名稱之後，請移至**搜尋&amp;調查** \> **eDiscovery**頁面的 [安全性]&amp;規範中心開啟情況下，並從保留移除信箱。如需詳細資訊，請參閱[管理 Office 365 安全性的 eDiscovery 案例&amp;規範中心](manage-ediscovery-cases.md)。</span><span class="sxs-lookup"><span data-stu-id="1838a-p131">After you've identified the name of the eDiscovery case and the hold, go to the **Search &amp; investigation** \> **eDiscovery** page in the Security &amp; Compliance Center, open the case, and remove the mailbox from the hold. For more information, see [Manage eDiscovery cases in the Office 365 Security &amp; Compliance Center](manage-ediscovery-cases.md).</span></span>
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a><span data-ttu-id="1838a-227">步驟 4： 從信箱移除延遲保留</span><span class="sxs-lookup"><span data-stu-id="1838a-227">Step 4: Remove the delay hold from the mailbox</span></span>

<span data-ttu-id="1838a-p132">從信箱移除任何類型的保留之後， *DelayHoldApplied*信箱屬性的值是設定為**True**。發生此情況下一次受管理的資料夾助理員處理的信箱並偵測已移除保留。這會呼叫*延遲按住*並表示保留的實際移除延遲防止資料會永久刪除信箱的 30 天。（延遲保留的用途是提供系統管理員有機會搜尋或復原之後移除保留為止，將清除的信箱項目）。 當信箱處於延遲保留時，信箱會仍被視為不受限制的持續期間保留為信箱是否在訴訟暫止狀態。30 天後延遲保留過期，及 Office 365 將會自動嘗試移除 （由*DelayHoldApplied*屬性設**為 False**） 的延遲保留使真正移除保留為止。</span><span class="sxs-lookup"><span data-stu-id="1838a-p132">After any type of hold is removed from a mailbox, the value of the *DelayHoldApplied* mailbox property is set to **True**. This occurs the next time the Managed Folder Assistant processes the mailbox and detects that a hold has been removed. This is called a *delay hold* and means the actual removal of the hold is delayed for 30 days to prevent data from being permanently deleted from the mailbox. (The purpose of a delay hold is to give admins an opportunity to search for or recover mailbox items that will be purged after a hold is removed.)  When a delay hold is placed on the mailbox, the mailbox is still considered to be on hold for an unlimited duration, as if the mailbox was on Litigation Hold. After 30 days, the delay hold expires, and Office 365 will automatically attempt to remove the delay hold (by setting the *DelayHoldApplied* property to **False**) so that the hold is actually removed.</span></span> 

<span data-ttu-id="1838a-p133">您可以刪除步驟 5 中的項目之前，您必須從信箱移除延遲保留。首先，決定是否延遲保留套用至信箱在 Exchange Online PowerShell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="1838a-p133">Before you can delete items in Step 5, you have to remove the delay hold from the mailbox. First, determine if the delay hold is applied to the mailbox by running the following command in Exchange Online PowerShell:</span></span>

```
Get-Mailbox <username> | FL DelayHoldApplied
```

<span data-ttu-id="1838a-p134">如果*DelayHoldApplied*屬性的值設為**False**，延遲保留尚未放在信箱上。您可以前往 [步驟 5 和刪除 [可復原的項目] 資料夾中的項目。</span><span class="sxs-lookup"><span data-stu-id="1838a-p134">If the value of the *DelayHoldApplied* property is set to **False**, a delay hold has not been placed on the mailbox. You can go to Step 5 and delete items in the Recoverable Items folder.</span></span>

<span data-ttu-id="1838a-237">如果*DelayHoldApplied*屬性的值設為**True**，執行下列命令以移除延遲保留：</span><span class="sxs-lookup"><span data-stu-id="1838a-237">If the value of the *DelayHoldApplied* property is set to **True**, run the following command to remove the delay hold:</span></span>

```
Set-Mailbox <username> -RemoveDelayHoldApplied
```
<span data-ttu-id="1838a-238">請注意您必須具有的法律保留角色在 Exchange Online 使用*RemoveDelayHoldApplied*參數。</span><span class="sxs-lookup"><span data-stu-id="1838a-238">Note that you must be assigned the Legal Hold role in Exchange Online to use the *RemoveDelayHoldApplied* parameter.</span></span>

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a><span data-ttu-id="1838a-239">步驟 5： 刪除 [可復原的項目] 資料夾中的項目</span><span class="sxs-lookup"><span data-stu-id="1838a-239">Step 5: Delete items in the Recoverable Items folder</span></span>

<span data-ttu-id="1838a-p135">現在您已經準備好實際使用[Search-mailbox](https://go.microsoft.com/fwlink/?linkid=852595)指令程式在 Exchange Online PowerShell 中刪除 [可復原的項目] 資料夾中的項目。時執行**搜尋信箱**指令程式會有三個選項。</span><span class="sxs-lookup"><span data-stu-id="1838a-p135">Now you're ready to actually delete items in the Recoverable Items folder by using the [Search-Mailbox](https://go.microsoft.com/fwlink/?linkid=852595) cmdlet in Exchange Online PowerShell. You have three options when running the **Search-Mailbox** cmdlet.</span></span> 
  
- <span data-ttu-id="1838a-242">刪除之前，讓您可以檢閱項目，必要時，才能刪除這些將項目複製到目標信箱。</span><span class="sxs-lookup"><span data-stu-id="1838a-242">Copy items to a target mailbox before you delete them so that you can review the items, if necessary, before you delete them.</span></span>
    
- <span data-ttu-id="1838a-243">將項目複製到目標信箱並刪除這些同一個命令中。</span><span class="sxs-lookup"><span data-stu-id="1838a-243">Copy items to a target mailbox and delete them in the same command.</span></span>
    
- <span data-ttu-id="1838a-244">刪除項目而不將其複製到目標信箱。</span><span class="sxs-lookup"><span data-stu-id="1838a-244">Delete items without copying them to a target mailbox.</span></span> 
    
<span data-ttu-id="1838a-p136">請注意在使用者的主要封存信箱 [可復原的項目] 資料夾中的項目也都會刪除時執行**搜尋信箱**指令程式。若要避免此問題，您可以包含*DoNotIncludeArchive*參數。與先前所述，如果自動展開封存啟用信箱、 \* \* Search-mailbox \* \* 指令程式不會刪除輔助封存信箱中的項目。如需關於自動展開封存，請參閱 ＜ [Overview of Office 365 中沒有限制之封存](unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="1838a-p136">Note that items in the Recoverable Items folder in the user's primary archive mailbox will also be deleted when you run the **Search-Mailbox** cmdlet. To prevent this, you can include the  *DoNotIncludeArchive*  switch. And as previously stated, if auto-expanding archiving is enabled for the mailbox, the \*\* Search-Mailbox \*\* cmdlet doesn't deleted items in an auxiliary archive mailbox. For more information about auto-expanding archive, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1838a-p137">如果您包括在搜尋查詢 （使用*SearchQuery*參數）， **Search-mailbox**指令程式會在搜尋結果中傳回最大值為 10000 個項目。因此如果您包括在搜尋查詢時，您可能必須執行**搜尋信箱**命令多次刪除 10000 個以上的項目。</span><span class="sxs-lookup"><span data-stu-id="1838a-p137">If you include a search query (by using the  *SearchQuery*  parameter), the **Search-Mailbox** cmdlet will return a maximum of 10,000 items in the search results. Therefore if you include a search query, you might have to run the **Search-Mailbox** command multiple times to delete more than 10,000 items.</span></span> 
  
<span data-ttu-id="1838a-p138">下列範例會顯示這些選項的每個命令語法。下列範例使用`-SearchQuery size>0`參數值，從 [可復原的項目] 資料夾中的所有子資料夾中刪除所有項目。如果您需要刪除符合特定條件的項目，您也可以使用*SearchQuery*參數來指定其他條件，例如日期範圍或郵件的主旨。請參閱[使用 SearchQuery 參數的其他範例](#other-examples-of-using-the-searchquery-parameter)下面的。</span><span class="sxs-lookup"><span data-stu-id="1838a-p138">The following examples show the command syntax for each of these options. These examples use the  `-SearchQuery size>0` parameter value, which deletes all items from all subfolders in the Recoverable Items folder. If you need to delete only items that match specific conditions, you can also use the  *SearchQuery*  parameter to specify other conditions, such as the subject of a message or a date range. See the [other examples of using the SearchQuery parameter](#other-examples-of-using-the-searchquery-parameter) below.</span></span> 
  
### <a name="example-1"></a><span data-ttu-id="1838a-255">範例 1</span><span class="sxs-lookup"><span data-stu-id="1838a-255">Example 1</span></span>

<span data-ttu-id="1838a-p139">此範例會在使用者的 [可復原的項目] 資料夾中的所有項目複製至您的組織探索搜尋信箱中的資料夾。這可讓您永久刪除之前檢閱項目。</span><span class="sxs-lookup"><span data-stu-id="1838a-p139">This example copies all items in the user's Recoverable Items folder to a folder in your organization's Discovery Search Mailbox. This lets you review the items before you permanently delete them.</span></span>

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>"
```

<span data-ttu-id="1838a-p140">在上述範例中，則不需要將項目複製到 [探索搜尋信箱。您可以將郵件複製到任何目標信箱。不過，若要防止敏感性信箱資料存取，建議將郵件複製到已授權的人員限制存取的信箱。根據預設，預設探索搜尋信箱會限制存取至探索管理角色群組的成員在 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="1838a-p140">In the previous example, it isn't required to copy items to the Discovery Search Mailbox. You can copy messages to any target mailbox. However, to prevent access to potentially sensitive mailbox data, we recommend copying messages to a mailbox that has access restricted to authorized personnel. By default, access to the default Discovery Search Mailbox is restricted to members of the Discovery Management role group in Exchange Online.</span></span> 
  
### <a name="example-2"></a><span data-ttu-id="1838a-262">範例 2</span><span class="sxs-lookup"><span data-stu-id="1838a-262">Example 2</span></span>

<span data-ttu-id="1838a-263">本範例會在使用者的 [可復原的項目] 資料夾中的所有項目複製到貴組織的探索搜尋信箱中的資料夾，然後從使用者的 [可復原的項目] 資料夾刪除項目。</span><span class="sxs-lookup"><span data-stu-id="1838a-263">This example copies all items in the user's Recoverable Items folder to a folder in your organization's Discovery Search Mailbox and then deletes the items from the user's Recoverable Items folder.</span></span>

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>" -DeleteContent
```
 
### <a name="example-3"></a><span data-ttu-id="1838a-264">範例 3</span><span class="sxs-lookup"><span data-stu-id="1838a-264">Example 3</span></span>

<span data-ttu-id="1838a-265">此範例會在使用者的可復原的項目] 資料夾中的所有項目刪除而不將其複製到目標信箱。</span><span class="sxs-lookup"><span data-stu-id="1838a-265">This example deletes all items in the user's Recoverable Items folder, without copying them to a target mailbox.</span></span> 

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -DeleteContent
```

### <a name="other-examples-of-using-the-searchquery-parameter"></a><span data-ttu-id="1838a-266">使用 SearchQuery 參數的其他範例</span><span class="sxs-lookup"><span data-stu-id="1838a-266">Other examples of using the SearchQuery parameter</span></span>

<span data-ttu-id="1838a-p141">以下是一些範例使用*SearchQuery*參數來尋找特定的郵件。如果您使用*SearchQuery*參數來搜尋特定的項目，請考慮將搜尋結果複製到目標信箱，讓您可以檢閱搜尋結果並再修改查詢視之前刪除的搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="1838a-p141">Here are a few examples of using the  *SearchQuery*  parameter to find specific messages. If you use the  *SearchQuery*  parameter to search for specific items, consider copying the search results to a target mailbox so that you can review the search results and then revise the query if necessary before you delete the results of a search.</span></span> 
  
<span data-ttu-id="1838a-269">此範例會傳回包含 [主旨] 欄位中的特定片語的郵件。</span><span class="sxs-lookup"><span data-stu-id="1838a-269">This example returns messages that contain a specific phrase in the Subject field.</span></span>
  
```
SearchQuery 'subject:"MAIL_BOX VALIDATION/UPGRADE!!!"' 
```

<span data-ttu-id="1838a-270">此範例會傳回指定的日期範圍內所傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="1838a-270">This example returns messages that were sent within the specified date range.</span></span>
  
```
SearchQuery 'sent>=06/01/2016 AND sent<=09/01/2016'
```
 
<span data-ttu-id="1838a-271">此範例會傳回至指定的人員所傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="1838a-271">This example returns messages that were sent to the specified person.</span></span>

```
SearchQuery 'to:garthf@alpinehouse.com'
```
   
### <a name="verify-that-items-were-deleted"></a><span data-ttu-id="1838a-272">確認已刪除的項目</span><span class="sxs-lookup"><span data-stu-id="1838a-272">Verify that items were deleted</span></span>

<span data-ttu-id="1838a-p142">若要確認您是否已成功刪除的項目從 [可復原的項目] 資料夾的信箱，使用**Get-mailboxfolderstatistics 指令**指令程式在 Exchange Online PowerShell 檢查的大小和可復原的項目] 資料夾中的項目數。您可以比較與您在步驟 1 中收集的過這些統計資料。</span><span class="sxs-lookup"><span data-stu-id="1838a-p142">To verify that you've successfully deleted items from the Recoverable Items folder of a mailbox, use **Get-MailboxFolderStatistics** cmdlet in Exchange Online PowerShell to check the size and number of items in Recoverable Items folder. You can compare these statistics with the ones you collected in Step 1.</span></span> 
  
<span data-ttu-id="1838a-275">執行下列命令以取得目前的大小和項目總數資料夾和使用者的主要信箱中 [可復原的項目] 資料夾中的子資料夾中。</span><span class="sxs-lookup"><span data-stu-id="1838a-275">Run the following command in to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span> 
  
```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
   
<span data-ttu-id="1838a-276">執行下列命令以取得中資料夾與使用者的封存信箱中 [可復原的項目] 資料夾中的子資料夾的大小和項目總數。</span><span class="sxs-lookup"><span data-stu-id="1838a-276">Run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in the user's archive mailbox.</span></span> 

```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
  
## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a><span data-ttu-id="1838a-277">步驟 6： 還原成先前狀態的信箱</span><span class="sxs-lookup"><span data-stu-id="1838a-277">Step 6: Revert the mailbox to its previous state</span></span>

<span data-ttu-id="1838a-p143">最後一個步驟是要還原的信箱回到先前的設定。這表示您在步驟 2 中變更的屬性重設並重新套用您在步驟 3 中移除保留。這包括：</span><span class="sxs-lookup"><span data-stu-id="1838a-p143">The final step is to revert the mailbox back to its previous configuration. This means resetting the properties that you changed in Step 2 and re-applying the holds that you removed in Step 3. This includes:</span></span>
  
- <span data-ttu-id="1838a-p144">變更刪除項目保留期間回到先前的值。或者，您可以只保留這設為 30 天內，最大值在 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="1838a-p144">Changing the deleted item retention period back to its previous value. Alternatively, you can just leave this set to 30 days, the maximum value in Exchange Online.</span></span>
    
- <span data-ttu-id="1838a-283">重新啟用單一項目復原。</span><span class="sxs-lookup"><span data-stu-id="1838a-283">Re-enabling single Item recovery.</span></span>
    
- <span data-ttu-id="1838a-284">重新啟用用戶端存取方法使其擁有人可以存取他們的信箱。</span><span class="sxs-lookup"><span data-stu-id="1838a-284">Re-enabling the client access methods so that the owner can access their mailbox.</span></span>
    
- <span data-ttu-id="1838a-285">重新套用保留與您移除的 Office 365 保留原則。</span><span class="sxs-lookup"><span data-stu-id="1838a-285">Re-applying the holds and Office 365 retention policies that you removed.</span></span>
    
- <span data-ttu-id="1838a-286">重新啟用受管理的資料夾助理員處理的信箱。</span><span class="sxs-lookup"><span data-stu-id="1838a-286">Re-enabling the Managed Folder Assistant to process the mailbox.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="1838a-287">我們建議您等待 24 小時之後重新套用保留或 Office 365 保留原則 （並確認已備妥） 重新啟用受管理的資料夾助理員處理信箱之前。</span><span class="sxs-lookup"><span data-stu-id="1838a-287">We recommend that you wait 24 hours after re-applying a hold or Office 365 retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant to process the mailbox.</span></span> 
  
<span data-ttu-id="1838a-288">在 Exchange Online PowerShell 中執行下列步驟 （依照指定的順序）。</span><span class="sxs-lookup"><span data-stu-id="1838a-288">Perform the following steps (in the specified sequence) in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="1838a-p145">執行下列命令以變更刪除項目保留期間回到原來的數值。本範例假設先前設定為早於 30 天;例如 14 天。</span><span class="sxs-lookup"><span data-stu-id="1838a-p145">Run the following command to change the deleted item retention period back to its original value. This assumes that the previous setting is less than 30 days; for example 14 days.</span></span> 
    
    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```
   
2. <span data-ttu-id="1838a-291">執行下列命令來重新啟用單一項目復原。</span><span class="sxs-lookup"><span data-stu-id="1838a-291">Run the following command to re-enable single item recovery.</span></span>
   
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. <span data-ttu-id="1838a-292">執行下列命令來重新啟用信箱的所有用戶端存取方法。</span><span class="sxs-lookup"><span data-stu-id="1838a-292">Run the following command to re-enable all client access methods to the mailbox.</span></span>
    
    ```
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```
   
4. <span data-ttu-id="1838a-p146">重新套用您在步驟 3 中移除保留。根據保留的類型，使用下列程序之一。</span><span class="sxs-lookup"><span data-stu-id="1838a-p146">Re-apply the holds that you removed in Step 3. Depending on the type of hold, use one of the following procedures.</span></span>
    
    <span data-ttu-id="1838a-295">**訴訟暫止**</span><span class="sxs-lookup"><span data-stu-id="1838a-295">**Litigation Hold**</span></span>
    
    <span data-ttu-id="1838a-296">執行下列命令來重新啟用信箱的訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="1838a-296">Run the following command to re-enable a Litigation Hold for the mailbox.</span></span>
    
    ```
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    <span data-ttu-id="1838a-297">**原有範圍暫止**</span><span class="sxs-lookup"><span data-stu-id="1838a-297">**In-Place Hold**</span></span>
    
    <span data-ttu-id="1838a-298">使用 EAC （或 Exchange Online PowerShell） 新增信箱回到就地保留。</span><span class="sxs-lookup"><span data-stu-id="1838a-298">Use the EAC (or Exchange Online PowerShell) to add the mailbox back to the In-Place Hold.</span></span> 
    
    <span data-ttu-id="1838a-299">**Office 365 的保留原則套用至特定信箱**</span><span class="sxs-lookup"><span data-stu-id="1838a-299">**Office 365 retention policies applied to specific mailboxes**</span></span>
    
    <span data-ttu-id="1838a-p147">使用安全性&amp;規範中心將信箱回復至 Office 365 保留原則。移至 [**日期控管** \> **保留**] 頁面的 [安全性] 中&amp;規範中心編輯保留原則，並回到 [保留原則套用至收件者] 清單中新增的信箱。</span><span class="sxs-lookup"><span data-stu-id="1838a-p147">Use the Security &amp; Compliance Center to add the mailbox back to the Office 365 retention policy. Go to the **Date governance** \> **Retention** page in the Security &amp; Compliance Center, edit the retention policy, and add the mailbox back to the list of recipients that the retention policy is applied to.</span></span> 
    
    <span data-ttu-id="1838a-302">**Office 365 全組織的保留原則**</span><span class="sxs-lookup"><span data-stu-id="1838a-302">**Organization-wide Office 365 retention policies**</span></span>
    
    <span data-ttu-id="1838a-p148">如果您排除從原則移除整個組織或 Exchange 全保留原則，然後使用 [安全性]&amp;規範中心以從清單中移除信箱排除的使用者。移至 [**日期控管** \> **保留**] 頁面的 [安全性] 中&amp;規範中心編輯整個組織的保留原則，並移除已排除的收件者清單中的信箱。執行此動作會重新保留原則套用至使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="1838a-p148">If you removed an organization-wide or Exchange-wide retention policy by excluding it from the policy, then use the Security &amp; Compliance Center to remove the mailbox from the list of excluded users. Go to the **Date governance** \> **Retention** page in the Security &amp; Compliance Center, edit the organization-wide retention policy, and remove the mailbox from the list of excluded recipients. Doing this will re-apply the retention policy to the user's mailbox.</span></span> 
    
    <span data-ttu-id="1838a-306">**保留 eDiscovery 案例**</span><span class="sxs-lookup"><span data-stu-id="1838a-306">**eDiscovery case holds**</span></span>
    
    <span data-ttu-id="1838a-p149">使用安全性&amp;規範中心新增信箱後保留與 eDiscovery 案例相關聯。移至 [**搜尋&amp;調查** \> **eDiscovery**頁面的 [安全性]&amp;規範中心開啟情況下，並新增回至保留的信箱。</span><span class="sxs-lookup"><span data-stu-id="1838a-p149">Use the Security &amp; Compliance Center to add the mailbox back the hold that's associated with an eDiscovery case. Go to the **Search &amp; investigation** \> **eDiscovery** page in the Security &amp; Compliance Center, open the case, and add the mailbox back to the hold.</span></span> 
    
5. <span data-ttu-id="1838a-p150">執行下列命令，以允許在受管理的資料夾助理員處理一次的信箱。如先前所述，我們建議您等待 24 小時之後重新套用保留或 Office 365 保留原則 （並確認已備妥） 重新啟用受管理的資料夾助理員之前。</span><span class="sxs-lookup"><span data-stu-id="1838a-p150">Run the following command to allow the Managed Folder Assistant to process the mailbox again. As previously stated, we recommend that you wait 24 hours after re-applying a hold or Office 365 retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant.</span></span> 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```
   
6. <span data-ttu-id="1838a-311">若要確認信箱具有已會回到先前的設定，您可以執行下列命令並再比較過您收集在步驟 1 中的設定。</span><span class="sxs-lookup"><span data-stu-id="1838a-311">To verify that the mailbox has been reverted back to its previous configuration, you can run the following commands and then compare the settings to the ones that you collected in Step 1.</span></span>

    ```
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```
  
## <a name="more-information"></a><span data-ttu-id="1838a-312">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="1838a-312">More information</span></span>

<span data-ttu-id="1838a-p151">以下是描述如何識別不同類型的保留當您執行**Get-mailbox**或**Get-organizationconfig**指令程式根據*InPlaceHolds*屬性中的值的表格。如需詳細資訊，請參閱[如何識別的類型保留放在 Exchange Online 信箱](identify-a-hold-on-an-exchange-online-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="1838a-p151">Here's a table that describes how to identify different types of holds based on the values in the  *InPlaceHolds*  property when you run the **Get-Mailbox** or **Get-OrganizationConfig** cmdlets. For more detailed information, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>

<span data-ttu-id="1838a-315">如先前清楚，您必須移除所有保留與 Office 365 之前信箱的保留原則可以成功地刪除 [可復原的項目] 資料夾中的項目。</span><span class="sxs-lookup"><span data-stu-id="1838a-315">As previously explained, you have to remove all holds and Office 365 retention policies from a mailbox before you can successfully delete items in the Recoverable Items folder.</span></span> 
  
|<span data-ttu-id="1838a-316">**保留類型**</span><span class="sxs-lookup"><span data-stu-id="1838a-316">**Hold type**</span></span>|<span data-ttu-id="1838a-317">**範例值**</span><span class="sxs-lookup"><span data-stu-id="1838a-317">**Example value**</span></span>|<span data-ttu-id="1838a-318">**如何識別保留**</span><span class="sxs-lookup"><span data-stu-id="1838a-318">**How to identify the hold**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1838a-319">訴訟暫止</span><span class="sxs-lookup"><span data-stu-id="1838a-319">Litigation Hold</span></span>  <br/> | `True` <br/> |<span data-ttu-id="1838a-320">*LitigationHoldEnabled*屬性設為`True`。</span><span class="sxs-lookup"><span data-stu-id="1838a-320">The  *LitigationHoldEnabled*  property is set to  `True`.</span></span>  <br/> |
|<span data-ttu-id="1838a-321">原有範圍暫止</span><span class="sxs-lookup"><span data-stu-id="1838a-321">In-Place Hold</span></span>  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |<span data-ttu-id="1838a-p152">*InPlaceHolds*屬性會包含信箱處於就地保留 GUID。您可以分清這是就地保留由於 GUID 不會開始使用前置詞。</span><span class="sxs-lookup"><span data-stu-id="1838a-p152">The  *InPlaceHolds*  property contains the GUID of the In-Place Hold that's placed on the mailbox. You can tell this is an In-Place Hold because the GUID doesn't start with a prefix.  </span></span><br/> <span data-ttu-id="1838a-324">您可以使用`Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL`取得資訊就地保留信箱上的 Exchange Online PowerShell 中的命令。</span><span class="sxs-lookup"><span data-stu-id="1838a-324">You can use the  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` command in Exchange Online PowerShell to get information about the In-Place Hold on the mailbox.</span></span>  <br/> |
| <span data-ttu-id="1838a-325">在 [安全性] 中的 office 365 保留原則&amp;規範中心套用至特定信箱</span><span class="sxs-lookup"><span data-stu-id="1838a-325">Office 365 retention policies in the Security &amp; Compliance Center applied to specific mailboxes</span></span>  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> <span data-ttu-id="1838a-326">或</span><span class="sxs-lookup"><span data-stu-id="1838a-326">or</span></span>  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |<span data-ttu-id="1838a-p153">當您執行**Get-mailbox**指令程式時， *InPlaceHolds*屬性也會包含 Office 365 Guid 保留原則套用至信箱。您可以識別保留原則因為 GUID 開頭`mbx`前置詞。請注意，如果保留原則的 GUID 開頭`skp`前置詞表示保留原則套用至 Skype 商務交談。</span><span class="sxs-lookup"><span data-stu-id="1838a-p153">When you run the **Get-Mailbox** cmdlet, the  *InPlaceHolds*  property also contains GUIDs of Office 365 retention policies applied to the mailbox. You can identify retention policies because the GUID starts with the  `mbx` prefix. Note that if the GUID of the retention policy starts with the  `skp` prefix, that indicates that the retention policy is applied to Skype for Business conversations.  </span></span><br/> <span data-ttu-id="1838a-330">到 Office 365 身分識別保留原則套用至信箱執行下列命令安全性&amp;規範中心 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="1838a-330">To identity the Office 365 retention policy that's applied to the mailbox, run the following command in Security &amp; Compliance Center PowerShell:</span></span> <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/><span data-ttu-id="1838a-331">請務必移除`mbx`或`skp`prefix 當您執行此命令。</span><span class="sxs-lookup"><span data-stu-id="1838a-331">Be sure to remove the  `mbx` or  `skp` prefix when you run this command.</span></span>  <br/> |
|<span data-ttu-id="1838a-332">整個組織的 Office 365 中安全性的保留原則&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="1838a-332">Organization-wide Office 365 retention policies in the Security &amp; Compliance Center</span></span>  <br/> |<span data-ttu-id="1838a-333">沒有值</span><span class="sxs-lookup"><span data-stu-id="1838a-333">No value</span></span>  <br/> <span data-ttu-id="1838a-334">或</span><span class="sxs-lookup"><span data-stu-id="1838a-334">or</span></span>  <br/>  <span data-ttu-id="1838a-335">`-mbxe9b52bf7ab3b46a286308ecb29624696`（表示信箱不排除全組織的原則）</span><span class="sxs-lookup"><span data-stu-id="1838a-335">`-mbxe9b52bf7ab3b46a286308ecb29624696` (indicates that the mailbox is excluded from an organization-wide policy)</span></span>  <br/> |<span data-ttu-id="1838a-336">即使當您執行**Get-mailbox**指令程式*InPlaceHolds*屬性是空的還是可能有一或多個整個組織的 Office 365 保留原則套用至信箱。</span><span class="sxs-lookup"><span data-stu-id="1838a-336">Even if the  *InPlaceHolds*  property is empty when you run the **Get-Mailbox** cmdlet, there still might be one or more organization-wide Office 365 retention policies applied to the mailbox.</span></span>  <br/> <span data-ttu-id="1838a-p154">若要確認此，您可以執行`Get-OrganizationConfig | FL InPlaceHolds`命令在 Exchange Online PowerShell 取得整個組織的 Office 365 保留原則之 Guid 的清單。整個組織的保留原則套用至 Exchange 信箱開始 GUID`mbx`首碼 ；例如`mbxa3056bb15562480fadb46ce523ff7b02`。</span><span class="sxs-lookup"><span data-stu-id="1838a-p154">To verify this, you can run the  `Get-OrganizationConfig | FL InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Office 365 retention policies. The GUID for organization-wide retention policies applied to Exchange mailboxes start with the  `mbx` prefix; for example  `mbxa3056bb15562480fadb46ce523ff7b02`.  </span></span><br/> <span data-ttu-id="1838a-339">身分識別整個組織的 Office 365 保留原則套用至信箱，請執行下列命令安全性&amp;規範中心 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="1838a-339">To identity the organization-wide Office 365 retention policy that's applied to the mailbox, run the following command in Security &amp; Compliance Center PowerShell:</span></span> <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/><span data-ttu-id="1838a-340">請注意是否信箱排除在整個組織的 Office 365 保留原則、 保留原則的 GUID 顯示在使用者信箱的*InPlaceHolds*屬性當您執行**Get-mailbox**指令程式 ；識別前置字元`-mbx`;例如，`-mbxe9b52bf7ab3b46a286308ecb29624696`</span><span class="sxs-lookup"><span data-stu-id="1838a-340">Note that if a mailbox is excluded from an organization-wide Office 365 retention policy, the GUID for the retention policy is displayed in the  *InPlaceHolds*  property of the user's mailbox when you run the **Get-Mailbox** cmdlet; it's identified by the prefix  `-mbx`; for example,  `-mbxe9b52bf7ab3b46a286308ecb29624696`</span></span> <br/> |
|<span data-ttu-id="1838a-341">eDiscovery 案例保留安全性&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="1838a-341">eDiscovery case hold in the Security &amp; Compliance Center</span></span>  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |<span data-ttu-id="1838a-p155">*InPlaceHolds*屬性也會包含任何保留 eDiscovery 案例安全性相關聯的 GUID&amp;可能會被放置在信箱的規範中心。您可以分清這是因為 GUID 開頭的 eDiscovery 案件保留`UniH`前置詞。</span><span class="sxs-lookup"><span data-stu-id="1838a-p155">The  *InPlaceHolds*  property also contains the GUID of any hold associated with an eDiscovery case in the Security &amp; Compliance Center that might be placed on the mailbox. You can tell this is an eDiscovery case hold because the GUID starts with the  `UniH` prefix.  </span></span><br/> <span data-ttu-id="1838a-p156">您可以使用`Get-CaseHoldPolicy`指令程式的安全性&amp;規範中心 PowerShell 取得信箱保留相關聯的 eDiscovery 案例的相關資訊。例如，您可以執行此命令`Get-CaseHoldPolicy <hold GUID without prefix> | FL Name`顯示上信箱的大小寫保留的名稱。請務必移除`UniH`prefix 當您執行此命令。</span><span class="sxs-lookup"><span data-stu-id="1838a-p156">You can use the  `Get-CaseHoldPolicy` cmdlet in Security &amp; Compliance Center PowerShell to get information about the eDiscovery case that the hold on the mailbox is associated with. For example, you can run the command  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` to display the name of the case hold that's on the mailbox. Be sure to remove the  `UniH` prefix when you run this command.  </span></span><br/><br/> <span data-ttu-id="1838a-347">身分識別與關聯信箱的保留 eDiscovery 案例中，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="1838a-347">To identity the eDiscovery case that the hold on the mailbox is associated with, run the following commands:</span></span><br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`


