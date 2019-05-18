---
title: 啟用 Office 365-系統管理說明中的無限制封存
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
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
ms.assetid: e2a789f2-9962-4960-9fd4-a00aa063559e
description: 系統管理員： 了解如何啟用自動展開封存在 Office 365 中，可提供您的使用者與不受限制的儲存區，讓其 Exchange Online 信箱。 您可以啟用自動展開封存的整個組織或只是針對特定使用者。
ms.openlocfilehash: a6f1e0e43854372b2c7b93c22c1160a7c555a95f
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154745"
---
# <a name="enable-unlimited-archiving-in-office-365---admin-help"></a><span data-ttu-id="4c87b-104">啟用 Office 365-系統管理說明中的無限制封存</span><span class="sxs-lookup"><span data-stu-id="4c87b-104">Enable unlimited archiving in Office 365 - Admin Help</span></span>

<span data-ttu-id="4c87b-105">若要啟用封存信箱的無限制的儲存空間，您可以在 Office 365 中使用的 Exchange Online 自動展開封存功能。</span><span class="sxs-lookup"><span data-stu-id="4c87b-105">You can use the Exchange Online auto-expanding archiving feature in Office 365 to enable unlimited storage space for archive mailboxes.</span></span> <span data-ttu-id="4c87b-106">自動展開封存開啟時，會自動新增額外的儲存空間至使用者的封存信箱時它逼近儲存量限制。</span><span class="sxs-lookup"><span data-stu-id="4c87b-106">When auto-expanding archiving is turned on, additional storage space is automatically added to a user's archive mailbox when it approaches the storage limit.</span></span> <span data-ttu-id="4c87b-107">結果是不受限制的信箱儲存容量。</span><span class="sxs-lookup"><span data-stu-id="4c87b-107">The result is unlimited mailbox storage capacity.</span></span> <span data-ttu-id="4c87b-108">您可以開啟自動展開封存組織中的每個人，或只是針對特定使用者。</span><span class="sxs-lookup"><span data-stu-id="4c87b-108">You can turn on auto-expanding archiving for everyone in your organization or just for specific users.</span></span> <span data-ttu-id="4c87b-109">如需自動展開封存，請參閱[在 Office 365 中的無限制封存概觀](unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="4c87b-109">For more information about auto-expanding archiving, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="4c87b-110">開始之前</span><span class="sxs-lookup"><span data-stu-id="4c87b-110">Before you begin</span></span>

- <span data-ttu-id="4c87b-111">您必須是全域系統管理員在 Office 365 組織或 Exchange Online 組織中啟用自動展開封存的整個組織或針對特定使用者的組織管理角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="4c87b-111">You have to be a global administrator in your Office 365 organization or a member of the Organization Management role group in your Exchange Online organization to enable auto-expanding archiving for your entire organization or for specific users.</span></span> <span data-ttu-id="4c87b-112">或者，您必須是已指派 「 郵件收件者角色，才能啟用自動展開封存針對特定使用者的角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="4c87b-112">Alternately, you have to be a member of a role group that's assigned the Mail Recipients role to enable auto-expanding archiving for specific users.</span></span>
    
- <span data-ttu-id="4c87b-113">使用者的封存信箱具有您可以啟用自動展開封存之前，先啟用。</span><span class="sxs-lookup"><span data-stu-id="4c87b-113">A user's archive mailbox has to be enabled before you can enable auto-expanding archiving.</span></span> <span data-ttu-id="4c87b-114">使用者必須被指派 Exchange Online Plan 2 授權，才能啟用封存信箱。</span><span class="sxs-lookup"><span data-stu-id="4c87b-114">A user must be assigned an Exchange Online Plan 2 license to enable the archive mailbox.</span></span> <span data-ttu-id="4c87b-115">如果 Exchange Online Plan 1 授權指派給使用者，您必須將它們指派不同 Exchange Online Archiving 授權，才能啟用封存信箱。</span><span class="sxs-lookup"><span data-stu-id="4c87b-115">If a user is assigned an Exchange Online Plan 1 license, you would have to assign them a separate Exchange Online Archiving license to enable their archive mailbox.</span></span> <span data-ttu-id="4c87b-116">請參閱[啟用封存信箱中的安全性 & 合規性中心](enable-archive-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="4c87b-116">See [Enable archive mailboxes in the Security & Compliance Center](enable-archive-mailboxes.md).</span></span>
    
- <span data-ttu-id="4c87b-117">您也可以使用 PowerShell 來啟用封存信箱。</span><span class="sxs-lookup"><span data-stu-id="4c87b-117">You can also use PowerShell to enable archive mailboxes.</span></span> <span data-ttu-id="4c87b-118">請參閱 <<c0>的詳細資訊] 區段中，您可以使用啟用您的組織中的所有使用者的封存信箱的 PowerShell 命令的範例。</span><span class="sxs-lookup"><span data-stu-id="4c87b-118">See the [More information](#more-information) section for an example of the PowerShell command that you can use to enable archive mailboxes for all users in your organization.</span></span> 
    
- <span data-ttu-id="4c87b-119">自動展開封存也支援共用信箱。</span><span class="sxs-lookup"><span data-stu-id="4c87b-119">Auto-expanding archiving also supports shared mailboxes.</span></span> <span data-ttu-id="4c87b-120">若要啟用信箱的共用信箱的封存，Exchange Online Plan 2 授權或具有 Exchange Online Archiving 授權的 Exchange Online Plan 1 授權就需要。</span><span class="sxs-lookup"><span data-stu-id="4c87b-120">To enable the archive for a shared mailbox, an Exchange Online Plan 2 license or an Exchange Online Plan 1 license with an Exchange Online Archiving license is required.</span></span>
    
- <span data-ttu-id="4c87b-121">若要啟用自動展開封存，您無法使用 Exchange 系統管理中心或安全性 & 合規性中心。</span><span class="sxs-lookup"><span data-stu-id="4c87b-121">You can't use the Exchange admin center or the Security & Compliance Center to enable auto-expanding archiving.</span></span> <span data-ttu-id="4c87b-122">您必須使用 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="4c87b-122">You have to use Exchange Online PowerShell.</span></span> <span data-ttu-id="4c87b-123">若要連接至您 Exchange Online 組織中使用遠端 PowerShell，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。</span><span class="sxs-lookup"><span data-stu-id="4c87b-123">To connect to your Exchange Online organization using remote PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
  
## <a name="enable-auto-expanding-archiving-for-your-entire-organization"></a><span data-ttu-id="4c87b-124">啟用整個組織的自動展開封存</span><span class="sxs-lookup"><span data-stu-id="4c87b-124">Enable auto-expanding archiving for your entire organization</span></span>

<span data-ttu-id="4c87b-125">您可以啟用自動展開封存的整個組織。</span><span class="sxs-lookup"><span data-stu-id="4c87b-125">You can enable auto-expanding archiving for your entire organization.</span></span> <span data-ttu-id="4c87b-126">您開啟之後，自動展開封存會啟用現有使用者信箱，以及所建立的新使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="4c87b-126">After you turn it on, auto-expanding archiving will be enabled for existing user mailboxes and for new user mailboxes that are created.</span></span> <span data-ttu-id="4c87b-127">當您建立新的使用者信箱時，請務必啟用使用者的主要的封存信箱，以便自動展開封存功能適用於新的使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="4c87b-127">When you create new user mailboxes, be sure to enable the user's main archive mailbox so the auto-expanding archiving feature will work for the new user mailbox.</span></span>
  
1. [<span data-ttu-id="4c87b-128">連線到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c87b-128">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. <span data-ttu-id="4c87b-129">若要啟用自動展開封存整個組織的 Exchange Online PowerShell 中執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="4c87b-129">Run the following command in Exchange Online PowerShell to enable auto-expanding archiving for your entire organization.</span></span>

    ```
    Set-OrganizationConfig -AutoExpandingArchive
    ```
  
## <a name="enable-auto-expanding-archiving-for-specific-users"></a><span data-ttu-id="4c87b-130">啟用自動展開封存針對特定使用者</span><span class="sxs-lookup"><span data-stu-id="4c87b-130">Enable auto-expanding archiving for specific users</span></span>

<span data-ttu-id="4c87b-131">而不是啟用自動展開封存的組織中每位使用者，您可以只啟用它針對特定使用者。</span><span class="sxs-lookup"><span data-stu-id="4c87b-131">Instead of enabling auto-expanding archiving for every user in your organization, you can just enable it for specific users.</span></span> <span data-ttu-id="4c87b-132">因為只將部分使用者可能需要非常大型的封存儲存空間，您可以這麼做。</span><span class="sxs-lookup"><span data-stu-id="4c87b-132">You might do this because only some users might have a need for a very large archive storage.</span></span>
  
<span data-ttu-id="4c87b-133">當您啟用特定使用者的自動展開封存和保留上的使用者信箱中或指派給 Office 365 保留原則，會進行下列兩種組態變更：</span><span class="sxs-lookup"><span data-stu-id="4c87b-133">When you enable auto-expanding archiving for a specific user and the user's mailbox in on hold or assigned to an Office 365 retention policy, the following two configurations changes are made:</span></span>
  
- <span data-ttu-id="4c87b-134">使用者的主要的封存信箱的儲存配額增加 10 GB （從為 110 GB 的 100 GB)。</span><span class="sxs-lookup"><span data-stu-id="4c87b-134">The storage quota for the user's primary archive mailbox is increased by 10 GB (from 100 GB to 110 GB).</span></span> <span data-ttu-id="4c87b-135">封存警告配額也增加 10 GB （從 90 GB，以 100 GB)。</span><span class="sxs-lookup"><span data-stu-id="4c87b-135">The archive warning quota is also increased by 10 GB (from 90 GB to 100 GB).</span></span>
    
- <span data-ttu-id="4c87b-136">使用者的主要信箱中的 [可復原的項目] 資料夾的儲存配額增加 10 GB （也從為 110 GB 的 100 GB)。</span><span class="sxs-lookup"><span data-stu-id="4c87b-136">The storage quota for the Recoverable Items folder in the user's primary mailbox is increased by 10 GB (also from 100 GB to 110 GB).</span></span> <span data-ttu-id="4c87b-137">10 GB （從 90 GB，以 100 GB) 也增加可復原的項目警告配額。</span><span class="sxs-lookup"><span data-stu-id="4c87b-137">The Recoverable Items warning quota is also increased by 10 GB (from 90 GB to 100 GB).</span></span> <span data-ttu-id="4c87b-138">只有當上的信箱中保留或指派給 Office 365 保留原則，這些變更皆適用。</span><span class="sxs-lookup"><span data-stu-id="4c87b-138">These changes are applicable only if the mailbox in on hold or assigned to an Office 365 retention policy.</span></span>
    
<span data-ttu-id="4c87b-139">此額外的空間會新增至避免可能發生之前已佈建自動展開封存的任何儲存問題。</span><span class="sxs-lookup"><span data-stu-id="4c87b-139">This additional space is added to prevent any storage issues that may occur before the auto-expanding archive is provisioned.</span></span> <span data-ttu-id="4c87b-140">請注意該額外儲存空間*不是*當您啟用整個組織，在上一節中所述的自動展開封存時，加入。</span><span class="sxs-lookup"><span data-stu-id="4c87b-140">Note that additional storage space  *is not*  added when you enable auto-expanding archiving for your entire organization, as described in the previous section.</span></span> 
  
1. [<span data-ttu-id="4c87b-141">連線到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c87b-141">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. <span data-ttu-id="4c87b-142">若要啟用自動展開封存的特定使用者的 Exchange Online PowerShell 中執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="4c87b-142">Run the following command in Exchange Online PowerShell to enable auto-expanding archiving for a specific user.</span></span> <span data-ttu-id="4c87b-143">如先前所述，必須先您可以開啟自動展開封存的使用者啟用使用者的封存信箱 （主要封存）。</span><span class="sxs-lookup"><span data-stu-id="4c87b-143">As previously explained, the user's archive mailbox (main archive) must be enabled before you can turn on auto-expanding archiving for that user.</span></span>
    
    ```
    Enable-Mailbox <user mailbox> -AutoExpandingArchive
    ```


> [!IMPORTANT]
> <span data-ttu-id="4c87b-144">在 Exchange 混合式部署中，您無法使用**Enable-mailbox AutoExpandingArchive**命令來啟用自動展開封存的特定使用者主要信箱位於內部部署和其封存信箱是以雲端為基礎。</span><span class="sxs-lookup"><span data-stu-id="4c87b-144">In an Exchange hybrid deployment, you can't use the **Enable-Mailbox -AutoExpandingArchive** command to enable auto-expanding archiving for specific a user whose primary mailbox is on premises and their archive mailbox is cloud-based.</span></span> <span data-ttu-id="4c87b-145">若要啟用自動展開封存在 Exchange 混合式部署中的雲端式封存信箱，您必須**Set-organizationconfig AutoExpandingArchive**命令在 Exchange Online PowerShell 中執行若要啟用自動展開封存整個組織中。</span><span class="sxs-lookup"><span data-stu-id="4c87b-145">To enable auto-expanding archiving for cloud-based archive mailboxes in an Exchange hybrid deployment, you have to run the **Set-OrganizationConfig -AutoExpandingArchive** command in Exchange Online PowerShell to enable auto-expanding archiving for the entire organization.</span></span> <span data-ttu-id="4c87b-146">如果使用者的主要和封存信箱的雲端式兩者，然後您可以使用**Enable-mailbox AutoExpandingArchive**命令啟用該特定使用者的自動展開封存。</span><span class="sxs-lookup"><span data-stu-id="4c87b-146">If a user's primary and archive mailboxes are both cloud-based, then you can use the **Enable-Mailbox -AutoExpandingArchive** command to enable auto-expanding archiving for that specific user.</span></span> 
  
## <a name="verify-that-auto-expanding-archiving-is-enabled"></a><span data-ttu-id="4c87b-147">確認已啟用 [自動展開封存</span><span class="sxs-lookup"><span data-stu-id="4c87b-147">Verify that auto-expanding archiving is enabled</span></span>

<span data-ttu-id="4c87b-148">若要確認為您的組織中啟用自動展開封存，請在 Exchange Online PowerShell 中執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="4c87b-148">To verify that auto-expanding archiving is enabled for your organization, run the following command in Exchange Online PowerShell.</span></span>

```
Get-OrganizationConfig | FL AutoExpandingArchiveEnabled
```

<span data-ttu-id="4c87b-149">值為`True`指出的組織已啟用自動展開封存。</span><span class="sxs-lookup"><span data-stu-id="4c87b-149">A value of  `True` indicates that auto-expanding archiving is enabled for the organization.</span></span> 
  
<span data-ttu-id="4c87b-150">若要確認自動展開封存已啟用特定使用者，請在 Exchange Online PowerShell 中執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="4c87b-150">To verify that auto-expanding archiving is enable for a specific user, run the following command in Exchange Online PowerShell.</span></span>
  
```
Get-Mailbox <user mailbox> | FL AutoExpandingArchiveEnabled
```
<span data-ttu-id="4c87b-151">值為`True`表示使用者已啟用自動展開封存。</span><span class="sxs-lookup"><span data-stu-id="4c87b-151">A value of  `True` indicates that auto-expanding archiving is enabled for the user.</span></span> 
  
<span data-ttu-id="4c87b-152">之後您啟用自動展開封存，請謹記下列事項：</span><span class="sxs-lookup"><span data-stu-id="4c87b-152">Keep the following things in mind after you enable auto-expanding archiving:</span></span>
  
- <span data-ttu-id="4c87b-153">如果您執行**Set-organizationconfig AutoExpandingArchive**命令，以啟用您組織的自動展開封存時，您不需要個別的信箱上執行**Enable-mailbox AutoExpandingArchive** 。</span><span class="sxs-lookup"><span data-stu-id="4c87b-153">If you run the **Set-OrganizationConfig -AutoExpandingArchive** command to enable auto-expanding archiving for your organization, you don't have to run the **Enable-Mailbox -AutoExpandingArchive** on individual mailboxes.</span></span> <span data-ttu-id="4c87b-154">請注意該執行的**Set-organizationconfig**指令程式來啟用自動展開封存的組織並不會變更使用者信箱上的*AutoExpandingArchiveEnabled*屬性`True`。</span><span class="sxs-lookup"><span data-stu-id="4c87b-154">Note that running the **Set-OrganizationConfig** cmdlet to enable auto-expanding archiving for your organization doesn't change the  *AutoExpandingArchiveEnabled*  property on user mailboxes to  `True`.</span></span>
    
- <span data-ttu-id="4c87b-155">同樣地，當您啟用自動展開封存時，不變更*ArchiveQuota*和*ArchiveWarningQuota*信箱內容的值。</span><span class="sxs-lookup"><span data-stu-id="4c87b-155">Similarly, the values for the  *ArchiveQuota*  and  *ArchiveWarningQuota*  mailbox properties aren't changed when you enable auto-expanding archiving.</span></span> <span data-ttu-id="4c87b-156">事實上，當您啟用自動展開封存的使用者信箱和*AutoExpandingArchiveEnabled*屬性設為`True`，只會略過的*ArchiveQuota*和*ArchiveWarningQuota*屬性。</span><span class="sxs-lookup"><span data-stu-id="4c87b-156">In fact, when you enable auto-expanding archiving for a user mailbox and the  *AutoExpandingArchiveEnabled*  property is set to  `True`, the  *ArchiveQuota*  and  *ArchiveWarningQuota*  properties are just ignored.</span></span> <span data-ttu-id="4c87b-157">以下是這些信箱屬性的範例之後自動展開封存的使用者信箱已啟用。</span><span class="sxs-lookup"><span data-stu-id="4c87b-157">Here's an example of these mailbox properties after auto-expanding archiving is enabled for a user's mailbox.</span></span> 
    
    ![啟用自動展開封存後，會略過 ArchiveQuota 和 ArchiveWarningQuota 屬性](media/6a1c1b69-5c4c-4267-aac8-53577667f03e.png)

  
## <a name="more-information"></a><span data-ttu-id="4c87b-159">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="4c87b-159">More information</span></span>

- <span data-ttu-id="4c87b-160">您也可以使用 PowerShell 來啟用封存信箱。</span><span class="sxs-lookup"><span data-stu-id="4c87b-160">You can also use PowerShell to enable archive mailboxes.</span></span> <span data-ttu-id="4c87b-161">例如，您可以執行下列命令在 Exchange Online PowerShell 來啟用尚未啟用封存信箱的所有使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="4c87b-161">For example, you can run the following command in Exchange Online PowerShell to enable archive mailboxes for all users whose archive mailbox isn't already enabled.</span></span>

    ```
    Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
    ```

- <span data-ttu-id="4c87b-162">開啟自動展開封存為您的組織或特定使用者之後，封存信箱會轉換為自動展開封存，當封存信箱 （包括 [可復原的項目] 資料夾） 達到 90 GB。</span><span class="sxs-lookup"><span data-stu-id="4c87b-162">After you turn on auto-expanding archiving for your organization or for a specific user, an archive mailbox is converted to an auto-expanding archive when the archive mailbox (including the Recoverable Items folder) reaches 90 GB.</span></span> <span data-ttu-id="4c87b-163">可能需要最多 30 天的額外儲存空間來佈建。</span><span class="sxs-lookup"><span data-stu-id="4c87b-163">It can take up to 30 days for the additional storage space to be provisioned.</span></span>
    
- <span data-ttu-id="4c87b-164">開啟自動展開封存之後，它不能關閉。</span><span class="sxs-lookup"><span data-stu-id="4c87b-164">After you turn on auto-expanding archiving, it can't be turned off.</span></span>
    
- <span data-ttu-id="4c87b-165">自動展開封存支援雲端式封存信箱在 Exchange 混合式部署中具有內部部署主要信箱的使用者。</span><span class="sxs-lookup"><span data-stu-id="4c87b-165">Auto-expanding archiving is supported for cloud-based archive mailboxes in an Exchange hybrid deployment for users who have an on-premises primary mailbox.</span></span> <span data-ttu-id="4c87b-166">不過，自動展開封存啟用雲端式封存信箱之後，您不能委任回至內部部署 Exchange 組織的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="4c87b-166">However, after auto-expanding archiving is enabled for a cloud-based archive mailbox, you can't off-board that archive mailbox back to the on-premises Exchange organization.</span></span> <span data-ttu-id="4c87b-167">請注意，自動展開封存不支援在 Exchange Server 2010 中的內部部署信箱。</span><span class="sxs-lookup"><span data-stu-id="4c87b-167">Note that auto-expanding archiving isn't supported for on-premises mailboxes in Exchange Server 2010.</span></span>
    
- <span data-ttu-id="4c87b-168">Outlook 用戶端，使用者可用來存取其封存信箱中的其他儲存區中的項目清單，請參閱 「 Outlook 需求來存取自動展開封存中的項目 > 一節中[Office 365 中封存的無限制的概觀](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive).</span><span class="sxs-lookup"><span data-stu-id="4c87b-168">For a list of Outlook clients that users can use to access items in the additional storage area in their archive mailbox, see the "Outlook requirements for accessing items in an auto-expanded archive" section in [Overview of unlimited archiving in Office 365](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive).</span></span>
    
- <span data-ttu-id="4c87b-169">如先前所述，10 GB 新增至使用者的主要的封存信箱儲存配額 （按住不放到 [可復原的項目] 資料夾如果信箱處於） 當您執行**Enable-mailbox AutoExpandingArchive**命令。</span><span class="sxs-lookup"><span data-stu-id="4c87b-169">As previously explained, 10 GB is added to the storage quota of the user's primary archive mailbox (and to the Recoverable Items folder if the mailbox is on hold) when you run the **Enable-Mailbox -AutoExpandingArchive** command.</span></span> <span data-ttu-id="4c87b-170">直到自動展開儲存空間佈建 （這可能需要長達 30 天），這會提供額外的儲存空間。</span><span class="sxs-lookup"><span data-stu-id="4c87b-170">This provides additional storage until the auto-expanded storage space is provisioned (which can take up to 30 days).</span></span> <span data-ttu-id="4c87b-171">當您執行**Set-organizationconfig AutoExpandingArchive**若要啟用組織中的所有信箱的自動展開都封存時，不會新增此額外儲存空間。</span><span class="sxs-lookup"><span data-stu-id="4c87b-171">This additional storage space isn't added when you run the **Set-OrganizationConfig -AutoExpandingArchive** to enable auto-expanding archiving for all mailboxes in your organization.</span></span> <span data-ttu-id="4c87b-172">如果您啟用自動展開封存的整個組織中，但需要新增額外的 10 GB 的特定使用者的儲存空間，您可以在該信箱上執行**Enable-mailbox AutoExpandingArchive**命令。</span><span class="sxs-lookup"><span data-stu-id="4c87b-172">If you enabled auto-expanding archiving for the entire organization, but need to add the additional 10 GB of storage space for a specific user, you can run the **Enable-Mailbox -AutoExpandingArchive** command on that mailbox.</span></span> <span data-ttu-id="4c87b-173">請注意，您會收到錯誤，指出已啟用自動展開封存，但的額外儲存空間會新增至信箱。</span><span class="sxs-lookup"><span data-stu-id="4c87b-173">Note that you will receive an error saying that auto-expanding archiving has already been enabled, but the additional storage space will be added to the mailbox.</span></span> 

- <span data-ttu-id="4c87b-174">系統管理員無法調整儲存空間配額。</span><span class="sxs-lookup"><span data-stu-id="4c87b-174">Administrators can't adjust the storage quota.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4c87b-175">僅支援自動展開封存，如用於個別使用者的信箱或共用信箱不會超過 1 GB，每天的成長率。</span><span class="sxs-lookup"><span data-stu-id="4c87b-175">Auto-expanding archiving is only supported for mailboxes used for individual users or shared mailboxes with a growth rate that doesn't exceed 1 GB per day.</span></span> <span data-ttu-id="4c87b-176">不允許使用日誌、 傳輸規則或自動轉寄規則將郵件複製到封存信箱，如進行封存。</span><span class="sxs-lookup"><span data-stu-id="4c87b-176">Using journaling, transport rules, or auto-forwarding rules to copy messages to an archive mailbox for the purposes of archiving is not permitted.</span></span> <span data-ttu-id="4c87b-177">使用者的封存信箱僅供該使用者使用。</span><span class="sxs-lookup"><span data-stu-id="4c87b-177">A user's archive mailbox is intended for just that user.</span></span> <span data-ttu-id="4c87b-178">Microsoft 保留在使用者封存信箱中用來儲存其他使用者之封存資料的執行個體中拒絕不受限封存的權限。</span><span class="sxs-lookup"><span data-stu-id="4c87b-178">Microsoft reserves the right to deny unlimited archiving in instances where a user's archive mailbox is used to store archive data for other users.</span></span>
