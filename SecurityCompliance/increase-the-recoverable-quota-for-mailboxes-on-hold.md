---
title: 增加保留信箱的可復原項目配額
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a8bdcbdd-9298-462f-b889-df26037a990c
description: '啟用封存信箱，並開啟自動展開封存增加的 Office 365 中的信箱 [可復原的項目] 資料夾的大小。 '
ms.openlocfilehash: 4c2e36dae3c8677579569d55a9c5b88efb5c54e5
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154235"
---
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a><span data-ttu-id="10183-103">增加保留信箱的可復原項目配額</span><span class="sxs-lookup"><span data-stu-id="10183-103">Increase the Recoverable Items quota for mailboxes on hold</span></span>

<span data-ttu-id="10183-104">預設保留原則 — 名為 「 預設 MRM 原則，也就是 Exchange Online 中的自動套用至新的信箱包含名為 [可復原的項目 14 天移至封存的保留標記。</span><span class="sxs-lookup"><span data-stu-id="10183-104">The default retention policy—named Default MRM Policy—that is automatically applied to new mailboxes in Exchange Online contains a retention tag named Recoverable Items 14 days move to archive.</span></span> <span data-ttu-id="10183-105">此保留標記移動項目從使用者的主要信箱中的 [可復原的項目] 資料夾至使用者的封存信箱中可復原的項目資料夾後的 14 天保留期間到期的項目。</span><span class="sxs-lookup"><span data-stu-id="10183-105">This retention tag moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox after the 14-day retention period expires for an item.</span></span> <span data-ttu-id="10183-106">針對此動作，必須啟用使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="10183-106">For this to happen, the user's archive mailbox must be enabled.</span></span> <span data-ttu-id="10183-107">如果未啟用封存信箱，會不採取任何動作，這表示中可復原的項目資料夾上的信箱保留, 的項目不會將移至封存信箱後的 14 天保留期間到期。</span><span class="sxs-lookup"><span data-stu-id="10183-107">If the archive mailbox isn't enabled, no action is taken, which means that items in the Recoverable Items folder for a mailbox on hold aren't moved to the archive mailbox after the 14-day retention period expires.</span></span> <span data-ttu-id="10183-108">因為不會刪除保留狀態的信箱中，有可能，可能會超過 [可復原的項目] 資料夾的儲存配額，尤其是如果未啟用使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="10183-108">Because nothing is deleted from a mailbox on hold, it's possible that the storage quota for the Recoverable Items folder might be exceeded, especially if the user's archive mailbox isn't enabled.</span></span> 
  
<span data-ttu-id="10183-109">若要協助減少超過此限制，[可復原的項目] 資料夾的儲存配額會自動增加從 30 GB 至 100 GB 時保留信箱在 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="10183-109">To help reduce the chance of exceeding this limit, the storage quota for the Recoverable Items folder is automatically increased from 30 GB to 100 GB when a hold is placed on a mailbox in Exchange Online.</span></span> <span data-ttu-id="10183-110">如果啟用封存信箱時，封存信箱中 [可復原的項目] 資料夾的儲存配額是也從 30 GB 增加到 100GB。</span><span class="sxs-lookup"><span data-stu-id="10183-110">If the archive mailbox is enabled, the storage quota for the Recoverable Items folder in the archive mailbox is also increased from 30 GB to 100 GB.</span></span> <span data-ttu-id="10183-111">如果自動展開封存中可用的功能在 Exchange Online 已啟用，在使用者的封存中 [可復原的項目] 資料夾的儲存配額會無限制。</span><span class="sxs-lookup"><span data-stu-id="10183-111">If the auto-expanding archiving feature in Exchange Online is enabled, the storage quota for the Recoverable Items folder in the user's archive will be unlimited.</span></span>
  
 <span data-ttu-id="10183-112">下表摘要說明 [可復原的項目] 資料夾的儲存配額。</span><span class="sxs-lookup"><span data-stu-id="10183-112">The following table summarizes the storage quota for the Recoverable Items folder.</span></span> 
  
|<span data-ttu-id="10183-113">**可復原的項目] 資料夾的位置**</span><span class="sxs-lookup"><span data-stu-id="10183-113">**Location of Recoverable Items folder**</span></span>|<span data-ttu-id="10183-114">**不保留的信箱**</span><span class="sxs-lookup"><span data-stu-id="10183-114">**Mailboxes not on hold**</span></span>|<span data-ttu-id="10183-115">**保留的信箱**</span><span class="sxs-lookup"><span data-stu-id="10183-115">**Mailboxes on hold**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="10183-116">主要信箱</span><span class="sxs-lookup"><span data-stu-id="10183-116">Primary mailbox</span></span>  <br/> |<span data-ttu-id="10183-117">30 GB</span><span class="sxs-lookup"><span data-stu-id="10183-117">30 GB</span></span>  <br/> |<span data-ttu-id="10183-118">100 GB</span><span class="sxs-lookup"><span data-stu-id="10183-118">100 GB</span></span>  <br/> |
|<span data-ttu-id="10183-119">封存信箱<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="10183-119">Archive mailbox<sup>\*</sup></span></span> <br/> |<span data-ttu-id="10183-120">無限制</span><span class="sxs-lookup"><span data-stu-id="10183-120">Unlimited</span></span>  <br/> |<span data-ttu-id="10183-121">無限制</span><span class="sxs-lookup"><span data-stu-id="10183-121">Unlimited</span></span>  <br/> |
|<span data-ttu-id="10183-122">**[可復原的項目] 資料夾的總儲存配額**</span><span class="sxs-lookup"><span data-stu-id="10183-122">**Total storage quota for the Recoverable Items folder**</span></span> <br/> |<span data-ttu-id="10183-123">無限制</span><span class="sxs-lookup"><span data-stu-id="10183-123">Unlimited</span></span>  <br/> |<span data-ttu-id="10183-124">無限制</span><span class="sxs-lookup"><span data-stu-id="10183-124">Unlimited</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="10183-125"><sup>\*</sup>封存信箱的儲存配額為 100 GB 的使用者使用 Exchange Online (Plan 2) 授權。</span><span class="sxs-lookup"><span data-stu-id="10183-125"><sup>\*</sup> The initial storage quota for the archive mailbox is 100 GB for users with an Exchange Online (Plan 2) license.</span></span> <span data-ttu-id="10183-126">不過，自動展開封存開啟時保留的信箱，封存信箱和可復原的項目] 資料夾的儲存配額增加為 110 GB。</span><span class="sxs-lookup"><span data-stu-id="10183-126">However, when auto-expanding archiving is turned on for mailboxes on hold, the storage quota for both the archive mailbox and the Recoverable Items folder is increased to 110 GB.</span></span> <span data-ttu-id="10183-127">必要時，將會佈建額外的封存儲存空間這會導致不受限制的封存儲存空間量。</span><span class="sxs-lookup"><span data-stu-id="10183-127">Additional archive storage space will be provisioned when necessary which results in an unlimited amount of archive storage.</span></span> <span data-ttu-id="10183-128">如需自動展開封存，請參閱[在 Office 365 中的無限制封存概觀](unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="10183-128">For more information about auto-expanding archiving, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span> 
  
<span data-ttu-id="10183-129">當主要信箱的保留狀態的信箱中的 [可復原的項目] 資料夾的儲存配額接近限制時，您可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="10183-129">When the storage quota for the Recoverable Items folder in the primary mailbox of a mailbox on hold is close to reaching its limit, you can do the following things:</span></span>
  
- <span data-ttu-id="10183-130">**啟用封存信箱，並開啟自動展開封存**-您可以啟用 [可復原的項目] 資料夾不受限制的儲存容量只要啟用封存信箱，並再開啟自動展開封存功能在 Exchange 中線上。</span><span class="sxs-lookup"><span data-stu-id="10183-130">**Enable the archive mailbox and turn on auto-expanding archiving** - You can enable an unlimited storage capacity for the Recoverable Items folder simply by enabling the archive mailbox and then turning on the auto-expanding archiving feature in Exchange Online.</span></span> <span data-ttu-id="10183-131">這會導致 110 GB 的主要信箱和使用者的封存中的 [可復原的項目] 資料夾的儲存容量無限的量中可復原的項目] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="10183-131">This results in 110 GB for the Recoverable Items folder in the primary mailbox and an unlimited amount of storage capacity for the Recoverable Items folder in the user's archive.</span></span> <span data-ttu-id="10183-132">請參閱如何：[啟用封存信箱中的安全性 & 合規性中心](enable-archive-mailboxes.md)，並[啟用 Office 365 中的無限制封存](enable-unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="10183-132">See how: [Enable archive mailboxes in the Security & Compliance Center](enable-archive-mailboxes.md) and [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="10183-133">啟用接近超出可復原的項目] 資料夾的儲存配額的信箱的封存後，您可能想要執行受管理的資料夾助理員來手動觸發助理員，以處理信箱，以便過期的項目都會移封存信箱中 [可復原項目] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="10183-133">After you enable the archive for a mailbox that's close to exceeding the storage quota for the Recoverable Items folder, you might want to run the Managed Folder Assistant to manually trigger the assistant to process the mailbox so that expired items are moved the Recoverable Items folder in the archive mailbox.</span></span> <span data-ttu-id="10183-134">如需相關指示，請參閱 「[步驟 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) 」。</span><span class="sxs-lookup"><span data-stu-id="10183-134">See [Step 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) for instructions.</span></span> <span data-ttu-id="10183-135">請注意其他使用者的信箱中的項目，可能會移至新的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="10183-135">Note that other items in the user's mailbox might be moved to the new archive mailbox.</span></span> <span data-ttu-id="10183-136">請考慮告知使用者，可能會發生此之後啟用封存信箱。</span><span class="sxs-lookup"><span data-stu-id="10183-136">Consider telling the user that this may happen after you enable the archive mailbox.</span></span> 
  
- <span data-ttu-id="10183-137">**建立自訂保留原則的信箱保留**-除了啟用封存信箱及自動展開封存信箱的訴訟暫止或就地保留，您可能也想要建立自訂保留原則的信箱上保留。</span><span class="sxs-lookup"><span data-stu-id="10183-137">**Create a custom retention policy for mailboxes on hold** - In addition to enabling the archive mailbox and auto-expanding archiving for mailboxes on Litigation Hold or In-Place Hold, you might also want to create a custom retention policy for mailboxes on hold.</span></span> <span data-ttu-id="10183-138">這讓我們您保留原則套用至預設 MRM 原則套用至不保留的信箱與不同的保留的信箱。</span><span class="sxs-lookup"><span data-stu-id="10183-138">This let's you apply a retention policy to mailboxes on hold that's different from the Default MRM Policy that's applied to mailboxes that aren't on hold.</span></span> <span data-ttu-id="10183-139">這可讓您可以套用專為保留信箱的保留標記。</span><span class="sxs-lookup"><span data-stu-id="10183-139">This lets you to apply retention tags that are specifically designed for mailboxes on hold.</span></span> <span data-ttu-id="10183-140">這包括建立新的保留標記可復原的項目] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="10183-140">This includes creating a new retention tag for the Recoverable Items folder.</span></span> 
    
<span data-ttu-id="10183-141">本主題的其餘部分說明建立自訂保留原則的信箱保留的逐步程序。</span><span class="sxs-lookup"><span data-stu-id="10183-141">The remainder of this topic describes the step-by-step procedures to create a custom retention policy for mailboxes on hold.</span></span>
  
<span data-ttu-id="10183-142">[步驟 1： 建立自訂保留標籤的 [可復原的項目] 資料夾](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)</span><span class="sxs-lookup"><span data-stu-id="10183-142">[Step 1: Create a custom retention tag for the Recoverable Items folder](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)</span></span>

<span data-ttu-id="10183-143">[[步驟 2： 建立新的保留原則的信箱保留](#step-2-create-a-new-retention-policy-for-mailboxes-on-hold)</span><span class="sxs-lookup"><span data-stu-id="10183-143">[[Step 2: Create a new retention policy for mailboxes on hold](#step-2-create-a-new-retention-policy-for-mailboxes-on-hold)</span></span>

[<span data-ttu-id="10183-144">步驟 3： 將新的保留原則套用至保留的信箱</span><span class="sxs-lookup"><span data-stu-id="10183-144">Step 3: Apply the new retention policy to mailboxes on hold</span></span>](#step-3-apply-the-new-retention-policy-to-mailboxes-on-hold)

[<span data-ttu-id="10183-145">（選用）步驟 4： 執行受管理的資料夾助理員套用新的保留設定</span><span class="sxs-lookup"><span data-stu-id="10183-145">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)
  
## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a><span data-ttu-id="10183-146">步驟 1： 建立自訂保留標籤的 [可復原的項目] 資料夾</span><span class="sxs-lookup"><span data-stu-id="10183-146">Step 1: Create a custom retention tag for the Recoverable Items folder</span></span>

<span data-ttu-id="10183-147">第一個步驟是建立自訂保留標籤 （稱為 「 保留原則標記或 RPT） 的 [可復原的項目] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="10183-147">The first step is to create a custom retention tag (called a retention policy tag or RPT) for the Recoverable Items folder.</span></span> <span data-ttu-id="10183-148">如先前所述，此 RPT 會移動項目，從使用者的主要信箱中的 [可復原的項目] 資料夾至使用者的封存信箱中 [可復原的項目] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="10183-148">As previously explained, this RPT moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox.</span></span> <span data-ttu-id="10183-149">您必須使用 PowerShell 來建立 rpt，適用於 [可復原的項目] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="10183-149">You have to use PowerShell to create an RPT for the Recoverable Items folder.</span></span> <span data-ttu-id="10183-150">您無法使用 Exchange 系統管理中心 (EAC)。</span><span class="sxs-lookup"><span data-stu-id="10183-150">You can't use the Exchange admin center (EAC).</span></span> 
  
1. [<span data-ttu-id="10183-151">使用遠端 PowerShell 連線到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="10183-151">Connect to Exchange Online using remote PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=517283)
    
2. <span data-ttu-id="10183-152">執行下列命令，以建立新的 RPT，[可復原的項目] 資料夾：</span><span class="sxs-lookup"><span data-stu-id="10183-152">Run the following command to create a new RPT for the Recoverable Items folder:</span></span> 
    
    ```
    New-RetentionPolicyTag -Name <Name of RPT> -Type RecoverableItems -AgeLimitForRetention <Number of days> -RetentionAction MoveToArchive
    ```

    <span data-ttu-id="10183-153">例如，下列命令會建立 rpt，適用於名為 「 可復原的項目上的信箱 30 天保留 」，為 30 天保留期間使用的可復原的項目] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="10183-153">For example, the following command creates a RPT for the Recoverable Items folder named "Recoverable Items 30 days for mailboxes on hold", with a retention period of 30 days.</span></span> <span data-ttu-id="10183-154">這表示，項目中 [可復原的項目] 資料夾 30 天之後，它將會移至使用者的封存信箱中 [可復原的項目] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="10183-154">This means that after an item has been in the Recoverable Items folder for 30 days, it will be moved to the Recoverable Items folder in the user's archive mailbox.</span></span>
    
    ```
    New-RetentionPolicyTag -Name "Recoverable Items 30 days for mailboxes on hold" -Type RecoverableItems -AgeLimitForRetention 30 -RetentionAction MoveToArchive
    ```

    > [!TIP]
    > <span data-ttu-id="10183-155">我們建議可復原的項目 RPT 的保留期間 （ _AgeLimitForRetention_參數所定義） 會印會套用至信箱的刪除項目保留期間相同。</span><span class="sxs-lookup"><span data-stu-id="10183-155">We recommend that the retention period (defined by the  _AgeLimitForRetention_ parameter) for the Recoverable Items RPT is the same as the deleted item retention period for the mailboxes that the RPT will be applied to.</span></span> <span data-ttu-id="10183-156">這可讓使用者的整個已刪除的項目保留期間它們移至封存信箱之前，復原刪除的項目。</span><span class="sxs-lookup"><span data-stu-id="10183-156">This allows a user the entire deleted item retention period to recover deleted items before they are moved to the archive mailbox.</span></span> <span data-ttu-id="10183-157">在前一個範例中，保留期間設為根據信箱已刪除的項目保留期間同時也是 30 天的 30 天。</span><span class="sxs-lookup"><span data-stu-id="10183-157">In the previous example, the retention period was set to 30 days based on the assumption that the deleted item retention period for mailboxes is also 30 days.</span></span> <span data-ttu-id="10183-158">Exchange Online 信箱預設會將刪除的項目保留 14 天。</span><span class="sxs-lookup"><span data-stu-id="10183-158">An Exchange Online mailbox is configured to retain deleted items for 14 days, by default.</span></span> <span data-ttu-id="10183-159">但您可以變更此設定最大值為 30 天。</span><span class="sxs-lookup"><span data-stu-id="10183-159">But you can change this setting to a maximum of 30 days.</span></span> <span data-ttu-id="10183-160">如需詳細資訊，請參閱[變更 Exchange Online 信箱的刪除項目保留期間](https://go.microsoft.com/fwlink/p/?LinkId=286940)。</span><span class="sxs-lookup"><span data-stu-id="10183-160">For more information, see [Change the deleted item retention period for a mailbox in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286940).</span></span> 
  
## <a name="step-2-create-a-new-retention-policy-for-mailboxes-on-hold"></a><span data-ttu-id="10183-161">步驟 2： 建立新的保留原則的信箱保留</span><span class="sxs-lookup"><span data-stu-id="10183-161">Step 2: Create a new retention policy for mailboxes on hold</span></span>

<span data-ttu-id="10183-162">下一步是建立新的保留原則，並將保留標記新增至，包括可復原的項目 RPT，您在步驟 1 中建立。</span><span class="sxs-lookup"><span data-stu-id="10183-162">The next step is to create a new retention policy and add retention tags to it, including the Recoverable Items RPT that you created in Step 1.</span></span> <span data-ttu-id="10183-163">此新原則會套用至下一個步驟中保留的信箱。</span><span class="sxs-lookup"><span data-stu-id="10183-163">This new policy will be applied to mailboxes on hold in the next step.</span></span> 
  
<span data-ttu-id="10183-164">建立新的保留原則之前，請決定您想要新增其他保留標記。</span><span class="sxs-lookup"><span data-stu-id="10183-164">Before you create the new retention policy, determine the additional retention tags that you want to add.</span></span> <span data-ttu-id="10183-165">如需保留標記新增至預設 MRM 原則的清單，以及建立新的保留標記的相關資訊，請參閱下列各項：</span><span class="sxs-lookup"><span data-stu-id="10183-165">For a list of the retention tags that are added to the Default MRM Policy and for information about creating new retention tags, see the following:</span></span>
  
- [<span data-ttu-id="10183-166">預設保留原則在 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="10183-166">Default Retention Policy in Exchange Online </span></span>](https://go.microsoft.com/fwlink/p/?LinkId=746954)
    
- [<span data-ttu-id="10183-167">支援保留原則標記的預設資料夾</span><span class="sxs-lookup"><span data-stu-id="10183-167">Default folders that support Retention Policy Tags</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=746957)
    
- <span data-ttu-id="10183-168">「 建立保留標記 」 一節主題中的 < <b0>Create a Retention Policy</b0> 。</span><span class="sxs-lookup"><span data-stu-id="10183-168">The "Create a retention tag" section in the [Create a Retention Policy](https://go.microsoft.com/fwlink/p/?LinkId=404422) topic.</span></span>
    
<span data-ttu-id="10183-169">您可以使用 EAC 或 Exchange Online PowerShell 來建立保留原則。</span><span class="sxs-lookup"><span data-stu-id="10183-169">You can use the EAC or Exchange Online PowerShell to create a retention policy.</span></span>
  
### <a name="use-the-eac-to-create-a-retention-policy"></a><span data-ttu-id="10183-170">使用 EAC 來建立保留原則</span><span class="sxs-lookup"><span data-stu-id="10183-170">Use the EAC to create a retention policy</span></span>
  
1. <span data-ttu-id="10183-171">在 EAC 中，移至 [**規範管理** \> **保留原則**，然後按一下 [**新增**![加入圖示](media/ITPro-EAC-AddIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="10183-171">In the EAC, go to **Compliance management** \> **Retention policies**, and then click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif).</span></span>
    
2. <span data-ttu-id="10183-172">在**新的保留原則**] 頁面的 [**名稱**] 中，輸入描述用途的保留原則; 的名稱例如， **MRM Policy for 保留的信箱**。</span><span class="sxs-lookup"><span data-stu-id="10183-172">On the **New retention policy** page, under **Name**, type a name that describes the purpose of the retention policy; for example, **MRM Policy for Mailboxes on Hold**.</span></span> 
    
3. <span data-ttu-id="10183-173">[**保留標記**，按一下 [**新增**![加入圖示](media/ITPro-EAC-AddIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="10183-173">Under **Retention tags**, click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="10183-174">在清單中的保留標記，選取 [可復原的項目 RPT，您在步驟 1 中建立，然後按一下 [**新增]**。</span><span class="sxs-lookup"><span data-stu-id="10183-174">In the list of retention tags, select the Recoverable Items RPT that you created in Step 1, and then click **Add**.</span></span>
    
    ![選取自訂的 [可復原的項目] 保留標記](media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)
  
5. <span data-ttu-id="10183-176">選取要新增至保留原則的其他保留標記。</span><span class="sxs-lookup"><span data-stu-id="10183-176">Select additional retention tags to add to the retention policy.</span></span> <span data-ttu-id="10183-177">例如，您可能要新增相同的標籤，包含在預設 MRM 原則。</span><span class="sxs-lookup"><span data-stu-id="10183-177">For example, you might want to add the same tags that are included in the Default MRM Policy.</span></span>
    
6. <span data-ttu-id="10183-178">當您完成新增保留標記時，按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="10183-178">When you're finished adding retention tags, click **OK**.</span></span>
    
7. <span data-ttu-id="10183-179">按一下 [**儲存**] 以建立新的保留原則。</span><span class="sxs-lookup"><span data-stu-id="10183-179">Click **Save** to create the new retention policy.</span></span> 
    
    <span data-ttu-id="10183-180">請注意，連結至保留原則的保留標記會顯示在詳細資料窗格中。</span><span class="sxs-lookup"><span data-stu-id="10183-180">Notice that the retention tags linked to the retention policy are displayed in the details pane.</span></span>
    
    ![連結到保留原則的保留標記，會顯示在詳細資料窗格中](media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)
  
### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a><span data-ttu-id="10183-182">使用 Exchange Online PowerShell 來建立保留原則</span><span class="sxs-lookup"><span data-stu-id="10183-182">Use Exchange Online PowerShell to create a retention policy</span></span>
  
<span data-ttu-id="10183-183">執行下列命令，以建立新的保留原則的信箱保留。</span><span class="sxs-lookup"><span data-stu-id="10183-183">Run the following command to create new retention policy for mailboxes on hold.</span></span> 
  
```
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>

```

<span data-ttu-id="10183-184">例如，下列命令會建立在上圖中顯示的連結的保留標記與保留原則。</span><span class="sxs-lookup"><span data-stu-id="10183-184">For example, the following command creates the retention policy and linked retention tags that is displayed in the previous illustration.</span></span>
  
```
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```
  
## <a name="step-3-apply-the-new-retention-policy-to-mailboxes-on-hold"></a><span data-ttu-id="10183-185">步驟 3： 將新的保留原則套用至保留的信箱</span><span class="sxs-lookup"><span data-stu-id="10183-185">Step 3: Apply the new retention policy to mailboxes on hold</span></span>

<span data-ttu-id="10183-186">最後一個步驟是套用您在步驟 2 中要保留的信箱在組織中建立的新保留原則。</span><span class="sxs-lookup"><span data-stu-id="10183-186">The last step is to apply the new retention policy that you created in Step 2 to mailboxes on hold in your organization.</span></span> <span data-ttu-id="10183-187">若要將保留原則套用至單一信箱或多個信箱，您可以使用 EAC 或 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="10183-187">You can use the EAC or Exchange Online PowerShell to apply the retention policy to a single mailbox or to multiple mailboxes.</span></span> 
  
### <a name="use-the-eac-to-apply-the-new-retention-policy"></a><span data-ttu-id="10183-188">使用 EAC 套用新的保留原則</span><span class="sxs-lookup"><span data-stu-id="10183-188">Use the EAC to apply the new retention policy</span></span>
  
1. <span data-ttu-id="10183-189">前往 [**收件者** \> **信箱**。</span><span class="sxs-lookup"><span data-stu-id="10183-189">Go to **Recipients** \> **Mailboxes**.</span></span>
    
2. <span data-ttu-id="10183-190">在清單檢視中，選取您想要套用保留原則的信箱，然後按一下 [**編輯**![編輯圖示](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。</span><span class="sxs-lookup"><span data-stu-id="10183-190">In the list view, select the mailbox you want to apply the retention policy to, and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
3. <span data-ttu-id="10183-191">在 [**使用者信箱**] 頁面上，按一下 [**信箱功能**]。</span><span class="sxs-lookup"><span data-stu-id="10183-191">On the **User Mailbox** page, click **Mailbox features**.</span></span>
    
4. <span data-ttu-id="10183-192">[**保留原則**] 中，選取您在步驟 2 中建立的保留原則，然後按一下 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="10183-192">Under **Retention policy**, select the retention policy that you created in Step 2, and then click **Save**.</span></span>
    
<span data-ttu-id="10183-193">您也可以使用 EAC 將保留原則套用至多個信箱。</span><span class="sxs-lookup"><span data-stu-id="10183-193">You can also use the EAC to apply the retention policy to multiple mailboxes.</span></span>
  
1. <span data-ttu-id="10183-194">前往 [**收件者** \> **信箱**。</span><span class="sxs-lookup"><span data-stu-id="10183-194">Go to **Recipients** \> **Mailboxes**.</span></span>
    
2. <span data-ttu-id="10183-195">在清單檢視中，使用 Shift 鍵或 Ctrl 鍵來選取多個信箱。</span><span class="sxs-lookup"><span data-stu-id="10183-195">In the list view, use the Shift or Ctrl keys to select multiple mailboxes.</span></span>
    
3. <span data-ttu-id="10183-196">在詳細資料窗格中，按一下 [其他選項]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="10183-196">In the details pane, click **More options**.</span></span>
    
4. <span data-ttu-id="10183-197">在 [保留原則]\*\*\*\* 下方，按一下 [更新]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="10183-197">Under **Retention Policy**, click **Update**.</span></span>
    
5. <span data-ttu-id="10183-198">在 [**大量指派保留原則**] 頁面上，選取您在步驟 2 中建立的保留原則，然後按一下 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="10183-198">On the **Bulk assign retention policy** page, select the retention policy that you created in Step 2, and then click **Save**.</span></span> 
    
### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a><span data-ttu-id="10183-199">使用 Exchange Online PowerShell 來套用新的保留原則</span><span class="sxs-lookup"><span data-stu-id="10183-199">Use Exchange Online PowerShell to apply the new retention policy</span></span>
  
<span data-ttu-id="10183-200">您可以使用 Exchange Online PowerShell 將新的保留原則套用至單一信箱。</span><span class="sxs-lookup"><span data-stu-id="10183-200">You can use Exchange Online PowerShell to apply a new retention policy to a single mailbox.</span></span> <span data-ttu-id="10183-201">但的 PowerShell 係數力量，您可以使用它來快速找出所有您組織中的信箱訴訟暫止，或在原有範圍暫止，並在再將新的保留原則套用到所有信箱保留在單一命令。</span><span class="sxs-lookup"><span data-stu-id="10183-201">But the real power of PowerShell is that you can use it to quickly identify all the mailboxes in your organization that are on either Litigation Hold or In-Place Hold, and then apply the new retention policy to all mailboxes on hold in a single command.</span></span> <span data-ttu-id="10183-202">以下是一些使用 Exchange PowerShell 將保留原則套用至一或多個信箱的範例。</span><span class="sxs-lookup"><span data-stu-id="10183-202">Here are some examples of using Exchange PowerShell to apply a retention policy to one or more mailboxes.</span></span> <span data-ttu-id="10183-203">在步驟 2 中建立保留原則套用的所有範例。</span><span class="sxs-lookup"><span data-stu-id="10183-203">All of the examples apply the retention policy that was created in Step 2.</span></span>
  
<span data-ttu-id="10183-204">此範例會將新的保留原則套用到 Pilar Pinilla 的信箱。</span><span class="sxs-lookup"><span data-stu-id="10183-204">This example applies the new retention policy to Pilar Pinilla's mailbox.</span></span>
  
```
Set-Mailbox "Pilar Pinilla" -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="10183-205">此範例會將新的保留原則套用至組織中的訴訟暫止的所有信箱。</span><span class="sxs-lookup"><span data-stu-id="10183-205">This example applies the new retention policy to all mailboxes in the organization that are on Litigation Hold.</span></span>
  
```
$LitigationHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'}
```

```
$LitigationHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="10183-206">本範例會將新的保留原則套用於組織中所有位於原有範圍暫止的信箱。</span><span class="sxs-lookup"><span data-stu-id="10183-206">This example applies the new retention policy to all mailboxes in the organization that are on In-Place Hold.</span></span>
  
```
$InPlaceHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null}
```

```
$InPlaceHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="10183-207">若要確認已套用新的保留原則，您可以使用**Get-mailbox**指令程式。</span><span class="sxs-lookup"><span data-stu-id="10183-207">You can use the **Get-Mailbox** cmdlet to verify that the new retention policy was applied.</span></span> 
  
<span data-ttu-id="10183-208">以下是一些範例，以確認在上述範例中的命令會套用到信箱訴訟暫止和就地保留 」 狀態的信箱的 「 MRM 原則的信箱上保留 」 的保留原則。</span><span class="sxs-lookup"><span data-stu-id="10183-208">Here are some examples to verify that the commands in the previous examples applied the "MRM Policy for Mailboxes on Hold" retention policy to mailboxes on Litigation Hold and mailboxes on In-Place Hold.</span></span>
  
```
Get-Mailbox "Pilar Pinilla" | Select RetentionPolicy
```

```
Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'} | FT DisplayName,RetentionPolicy -Auto
```

```
Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null} | FT DisplayName,RetentionPolicy -Auto
```
  
## <a name="optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings"></a><span data-ttu-id="10183-209">（選用）步驟 4： 執行受管理的資料夾助理員套用新的保留設定</span><span class="sxs-lookup"><span data-stu-id="10183-209">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>

<span data-ttu-id="10183-210">您將新的保留原則套用至保留的信箱之後，它可能需要多達 7 天在 Exchange Online 的受管理的資料夾助理員處理程序使用新的保留原則中設定這些信箱。</span><span class="sxs-lookup"><span data-stu-id="10183-210">After you apply the new retention policy to mailboxes on hold, it can take up to 7 days in Exchange Online for the Managed Folder Assistant to process these mailboxes using the settings in the new retention policy.</span></span> <span data-ttu-id="10183-211">而不是等待受管理的資料夾助理員執行，您可以使用**Start-managedfolderassistant** cmdlet 手動觸發助理員，以處理已套用至新的保留原則的信箱。</span><span class="sxs-lookup"><span data-stu-id="10183-211">Instead of waiting for the Managed Folder Assistant to run, you can use the **Start-ManagedFolderAssistant** cmdlet to manually trigger the assistant to process the mailboxes that you applied the new retention policy to.</span></span> 
  
<span data-ttu-id="10183-212">執行下列命令，以啟動受管理的資料夾助理員 Pilar Pinilla 的信箱。</span><span class="sxs-lookup"><span data-stu-id="10183-212">Run the following command to start the Managed Folder Assistant for Pilar Pinilla's mailbox.</span></span>
  
```
Start-ManagedFolderAssistant "Pilar Pinilla"
```

<span data-ttu-id="10183-213">執行下列命令，以啟動受管理的資料夾助理員的所有信箱保留。</span><span class="sxs-lookup"><span data-stu-id="10183-213">Run the following commands to start the Managed Folder Assistant for all mailboxes on hold.</span></span>
  
```
$MailboxesOnHold = Get-Mailbox -ResultSize unlimited | Where-Object {($_.InPlaceHolds -ne $null) -or ($_.LitigationHoldEnabled -eq "True")}
```

```
$MailboxesOnHold.DistinguishedName | Start-ManagedFolderAssistant
```

## <a name="more-information"></a><span data-ttu-id="10183-214">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="10183-214">More information</span></span>

- <span data-ttu-id="10183-215">啟用使用者的封存信箱之後，請考慮告知使用者他們的信箱 （不只是 [可復原的項目] 資料夾中項目） 中的其他項目可能會移至封存信箱。</span><span class="sxs-lookup"><span data-stu-id="10183-215">After you enable a user's archive mailbox, consider telling the user that other items in their mailbox (not just items in the Recoverable Items folder) might be moved to the archive mailbox.</span></span> <span data-ttu-id="10183-216">這是因為預設 MRM 原則指派給 Exchange Online 信箱包含兩個年度的項目已傳遞至信箱或所建立的日期之後將項目移至封存信箱的保留標記 （名為 Default 2 年移至封存）使用者。</span><span class="sxs-lookup"><span data-stu-id="10183-216">This is because the Default MRM Policy that's assigned to Exchange Online mailboxes contains a retention tag (named Default 2 years move to archive) that moves items to the archive mailbox two years after the date the item was delivered to the mailbox or created by the user.</span></span> <span data-ttu-id="10183-217">如需詳細資訊，請參閱[Exchange Online 中的預設保留原則](https://go.microsoft.com/fwlink/p/?LinkId=746954)</span><span class="sxs-lookup"><span data-stu-id="10183-217">For more information, see [Default Retention Policy in Exchange Online ](https://go.microsoft.com/fwlink/p/?LinkId=746954)</span></span>
    
- <span data-ttu-id="10183-218">啟用使用者的封存信箱之後，也可能會告訴使用者，他們可以復原刪除的項目在其封存信箱中 [可復原的項目] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="10183-218">After you enable a user's archive mailbox, you might also tell the user that they can recover deleted items in the Recoverable Items folder in their archive mailbox.</span></span> <span data-ttu-id="10183-219">他們可以在 Outlook 中執行這在封存信箱中，選取 [**刪除的項目**] 資料夾，然後按一下 [**首頁**] 索引標籤上的 [**復原刪除的項目從伺服器**。如需有關復原已刪除的項目的詳細資訊，請參閱[復原已刪除的 Outlook for Windows 中的項目](https://go.microsoft.com/fwlink/p/?LinkId=624829)。</span><span class="sxs-lookup"><span data-stu-id="10183-219">They can do this in Outlook by selecting the **Deleted Items** folder in the archive mailbox, and then clicking **Recover Deleted Items from Server** on the **Home** tab. For more information about recovering deleted items, see [Recover deleted items in Outlook for Windows](https://go.microsoft.com/fwlink/p/?LinkId=624829).</span></span> 
