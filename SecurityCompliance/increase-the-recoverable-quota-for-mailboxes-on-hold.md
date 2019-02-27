---
title: 增加保留信箱的「可復原的項目」配額
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a8bdcbdd-9298-462f-b889-df26037a990c
description: '啟用封存信箱並開啟自動展開封存增加的 Office 365 中的信箱 [可復原的項目] 資料夾的大小。 '
ms.openlocfilehash: 701821074294441525315c3db77daeccd5700935
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296536"
---
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a><span data-ttu-id="d4033-103">增加保留信箱的「可復原的項目」配額</span><span class="sxs-lookup"><span data-stu-id="d4033-103">Increase the Recoverable Items quota for mailboxes on hold</span></span>

<span data-ttu-id="d4033-p101">預設保留原則-名為預設 MRM 原則--亦即會自動套用至新的信箱在 Exchange Online 中包含名為可復原的項目 14 天移至封存其保留標記。此保留標記移動項目從使用者的主要信箱中的 [可復原的項目] 資料夾至使用者的封存信箱中 [可復原的項目] 資料夾後的 14 天保留期間到期的項目。這會發生，必須啟用使用者的封存信箱。如果未啟用封存信箱，會不採取任何動作，這表示可復原的項目保留信箱上的資料夾中的項目都移到封存信箱後的 14 天保留期間到期。Nothing 從保留信箱中刪除，因為有可能可能會超過儲存配額可復原的項目] 資料夾，特別是如果未啟用使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="d4033-p101">The default retention policy—named Default MRM Policy—that is automatically applied to new mailboxes in Exchange Online contains a retention tag named Recoverable Items 14 days move to archive. This retention tag moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox after the 14-day retention period expires for an item. For this to happen, the user's archive mailbox must be enabled. If the archive mailbox isn't enabled, no action is taken, which means that items in the Recoverable Items folder for a mailbox on hold aren't moved to the archive mailbox after the 14-day retention period expires. Because nothing is deleted from a mailbox on hold, it's possible that the storage quota for the Recoverable Items folder might be exceeded, especially if the user's archive mailbox isn't enabled.</span></span> 
  
<span data-ttu-id="d4033-p102">若要協助減少超過此限制的機會、 儲存配額可復原的項目] 資料夾是自動從增加 30 GB 100 gb 保留處於時為信箱在 Exchange Online。如果已啟用封存信箱，封存信箱中的 [可復原的項目] 資料夾的存放區配額也增加從 30 GB 100 gb。如果自動展開封存功能在 Exchange Online 已啟用、 [可復原的項目] 資料夾中使用者的封存儲存配額將不受限制。</span><span class="sxs-lookup"><span data-stu-id="d4033-p102">To help reduce the chance of exceeding this limit, the storage quota for the Recoverable Items folder is automatically increased from 30 GB to 100 GB when a hold is placed on a mailbox in Exchange Online. If the archive mailbox is enabled, the storage quota for the Recoverable Items folder in the archive mailbox is also increased from 30 GB to 100 GB. If the auto-expanding archiving feature in Exchange Online is enabled, the storage quota for the Recoverable Items folder in the user's archive will be unlimited.</span></span>
  
 <span data-ttu-id="d4033-112"> 下表摘要說明 [可復原的項目] 資料夾的儲存配額。</span><span class="sxs-lookup"><span data-stu-id="d4033-112">The following table summarizes the storage quota for the Recoverable Items folder.</span></span> 
  
|<span data-ttu-id="d4033-113">**[可復原的項目] 資料夾的位置**</span><span class="sxs-lookup"><span data-stu-id="d4033-113">**Location of Recoverable Items folder**</span></span>|<span data-ttu-id="d4033-114">**未保留的信箱**</span><span class="sxs-lookup"><span data-stu-id="d4033-114">**Mailboxes not on hold**</span></span>|<span data-ttu-id="d4033-115">**保留的信箱**</span><span class="sxs-lookup"><span data-stu-id="d4033-115">**Mailboxes on hold**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d4033-116">主要信箱</span><span class="sxs-lookup"><span data-stu-id="d4033-116">Primary mailbox</span></span>  <br/> |<span data-ttu-id="d4033-117">30 GB</span><span class="sxs-lookup"><span data-stu-id="d4033-117">30 GB</span></span>  <br/> |<span data-ttu-id="d4033-118">100 GB</span><span class="sxs-lookup"><span data-stu-id="d4033-118">100 GB</span></span>  <br/> |
|<span data-ttu-id="d4033-119">封存信箱<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d4033-119">Archive mailbox<sup>\*</sup></span></span> <br/> |<span data-ttu-id="d4033-120">無限制</span><span class="sxs-lookup"><span data-stu-id="d4033-120">Unlimited</span></span>  <br/> |<span data-ttu-id="d4033-121">無限制</span><span class="sxs-lookup"><span data-stu-id="d4033-121">Unlimited</span></span>  <br/> |
|<span data-ttu-id="d4033-122">**[可復原的項目] 資料夾的儲存配額總計**</span><span class="sxs-lookup"><span data-stu-id="d4033-122">**Total storage quota for the Recoverable Items folder**</span></span> <br/> |<span data-ttu-id="d4033-123">無限制</span><span class="sxs-lookup"><span data-stu-id="d4033-123">Unlimited</span></span>  <br/> |<span data-ttu-id="d4033-124">無限制</span><span class="sxs-lookup"><span data-stu-id="d4033-124">Unlimited</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="d4033-p103"><sup>\*</sup>封存信箱的初始儲存配額為 100 GB 具有 Exchange Online (Plan 2) 授權的使用者。但是，自動展開封存開啟時上保留信箱、 封存信箱與 [可復原的項目] 資料夾的存放區配額增加為 110 GB。額外的封存儲存空間在佈建時所需結果中封存儲存區中不受限制的數量。如需關於自動展開封存，請參閱[Overview of Office 365 中沒有限制之封存](unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="d4033-p103"><sup>\*</sup> The initial storage quota for the archive mailbox is 100 GB for users with an Exchange Online (Plan 2) license. However, when auto-expanding archiving is turned on for mailboxes on hold, the storage quota for both the archive mailbox and the Recoverable Items folder is increased to 110 GB. Additional archive storage space will be provisioned when necessary which results in an unlimited amount of archive storage. For more information about auto-expanding archiving, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span> 
  
<span data-ttu-id="d4033-129">在保留信箱的主要信箱中，當 [可復原的項目] 資料夾的儲存配額接近限制時，您可以執行下列動作︰</span><span class="sxs-lookup"><span data-stu-id="d4033-129">When the storage quota for the Recoverable Items folder in the primary mailbox of a mailbox on hold is close to reaching its limit, you can do the following things:</span></span>
  
- <span data-ttu-id="d4033-p104">**啟用封存信箱並開啟自動展開封存**-您可以只是透過啟用封存信箱並再開啟自動展開封存功能 Exchange 中啟用 [可復原的項目] 資料夾不受限制的儲存容量線上。這會產生 110 GB 主要信箱與使用者的封存中的 [可復原的項目] 資料夾的儲存容量不受限制的數量的可復原的項目] 資料夾。請參閱如何：[啟用封存信箱在 Office 365 安全性&amp;規範中心](enable-archive-mailboxes.md)並[啟用 Office 365 中沒有限制之封存](enable-unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="d4033-p104">**Enable the archive mailbox and turn on auto-expanding archiving** - You can enable an unlimited storage capacity for the Recoverable Items folder simply by enabling the archive mailbox and then turning on the auto-expanding archiving feature in Exchange Online. This results in 110 GB for the Recoverable Items folder in the primary mailbox and an unlimited amount of storage capacity for the Recoverable Items folder in the user's archive. See how: [Enable archive mailboxes in the Office 365 Security &amp; Compliance Center](enable-archive-mailboxes.md) and [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d4033-p105">啟用封存信箱的接近超過儲存配額可復原的項目] 資料夾以之後，您可能會想要執行受管理的資料夾助理員以手動觸發的移到期的項目處理的信箱助理員封存信箱中的可復原的項目資料夾。請參閱指示的[步驟 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) 。請注意其他使用者的信箱中的項目可能會移至新的封存信箱。請考慮告知使用者這可能會發生之後您啟用封存信箱。</span><span class="sxs-lookup"><span data-stu-id="d4033-p105">After you enable the archive for a mailbox that's close to exceeding the storage quota for the Recoverable Items folder, you might want to run the Managed Folder Assistant to manually trigger the assistant to process the mailbox so that expired items are moved the Recoverable Items folder in the archive mailbox. See [Step 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) for instructions. Note that other items in the user's mailbox might be moved to the new archive mailbox. Consider telling the user that this may happen after you enable the archive mailbox.</span></span> 
  
- <span data-ttu-id="d4033-p106">**建立自訂的保留原則的信箱上保留**-啟用封存信箱與自動展開封存信箱訴訟暫止或就地保留功能，以及可能也想要在建立自訂的保留原則的信箱保留。這讓我們您保留原則套用至預設 MRM 原則套用至不保留的信箱與不同的保留信箱。這可讓您可以套用特別設計上保留信箱的保留標記。這包括建立新的保留標記可復原的項目] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="d4033-p106">**Create a custom retention policy for mailboxes on hold** - In addition to enabling the archive mailbox and auto-expanding archiving for mailboxes on Litigation Hold or In-Place Hold, you might also want to create a custom retention policy for mailboxes on hold. This let's you apply a retention policy to mailboxes on hold that's different from the Default MRM Policy that's applied to mailboxes that aren't on hold. This lets you to apply retention tags that are specifically designed for mailboxes on hold. This includes creating a new retention tag for the Recoverable Items folder.</span></span> 
    
<span data-ttu-id="d4033-141">本主題的其餘部分說明為保留信箱建立自訂保留原則的逐步程序。</span><span class="sxs-lookup"><span data-stu-id="d4033-141">The remainder of this topic describes the step-by-step procedures to create a custom retention policy for mailboxes on hold.</span></span>
  
<span data-ttu-id="d4033-142">[步驟 1：為 [可復原的項目] 資料夾建立自訂保留標籤](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)</span><span class="sxs-lookup"><span data-stu-id="d4033-142">[Step 1: Create a custom retention tag for the Recoverable Items folder](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)</span></span>

<span data-ttu-id="d4033-143">[[步驟 2： 建立新的保留原則的信箱保留](#step-2-create-a-new-retention-policy-for-mailboxes-on-hold)</span><span class="sxs-lookup"><span data-stu-id="d4033-143">[[Step 2: Create a new retention policy for mailboxes on hold](#step-2-create-a-new-retention-policy-for-mailboxes-on-hold)</span></span>

[<span data-ttu-id="d4033-144">步驟 3：將新的保留原則套用至保留信箱</span><span class="sxs-lookup"><span data-stu-id="d4033-144">Step 3: Apply the new retention policy to mailboxes on hold</span></span>](#step-3-apply-the-new-retention-policy-to-mailboxes-on-hold)

[<span data-ttu-id="d4033-145">(選用) 步驟 4：執行受管理的資料夾助理員套用新的保留設定</span><span class="sxs-lookup"><span data-stu-id="d4033-145">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)
  
## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a><span data-ttu-id="d4033-146">步驟 1：為 [可復原的項目] 資料夾建立自訂保留標籤</span><span class="sxs-lookup"><span data-stu-id="d4033-146">Step 1: Create a custom retention tag for the Recoverable Items folder</span></span>

<span data-ttu-id="d4033-p107">第一個步驟是建立自訂保留標記 （稱為 「 保留原則標記或印） 可復原的項目] 資料夾。如先前所述，此印會移動項目至使用者的封存信箱中 [可復原的項目] 資料夾從使用者的主要信箱中的 [可復原的項目] 資料夾。您必須使用 PowerShell 建立印可復原的項目] 資料夾。您無法使用 Exchange 系統管理中心 (EAC)。</span><span class="sxs-lookup"><span data-stu-id="d4033-p107">The first step is to create a custom retention tag (called a retention policy tag or RPT) for the Recoverable Items folder. As previously explained, this RPT moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox. You have to use PowerShell to create an RPT for the Recoverable Items folder. You can't use the Exchange admin center (EAC).</span></span> 
  
1. [<span data-ttu-id="d4033-151">使用遠端 PowerShell 連線到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d4033-151">Connect to Exchange Online using remote PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=517283)
    
2. <span data-ttu-id="d4033-152">執行下列命令為 [可復原的項目] 資料夾建立新的 RPT： </span><span class="sxs-lookup"><span data-stu-id="d4033-152">Run the following command to create a new RPT for the Recoverable Items folder:</span></span> 
    
    ```
    New-RetentionPolicyTag -Name <Name of RPT> -Type RecoverableItems -AgeLimitForRetention <Number of days> -RetentionAction MoveToArchive
    ```

    <span data-ttu-id="d4033-p108">例如，下列命令會為 [可復原的項目] 資料夾建立名為 「保留信箱可復原的項目 30 天」的 RPT，保留期限為 30 天。這表示當項目在 [可復原的項目] 資料夾中停留 30 天後，將會移至使用者封存信箱中的 [可復原的項目] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="d4033-p108">For example, the following command creates a RPT for the Recoverable Items folder named "Recoverable Items 30 days for mailboxes on hold", with a retention period of 30 days. This means that after an item has been in the Recoverable Items folder for 30 days, it will be moved to the Recoverable Items folder in the user's archive mailbox.</span></span>
    
    ```
    New-RetentionPolicyTag -Name "Recoverable Items 30 days for mailboxes on hold" -Type RecoverableItems -AgeLimitForRetention 30 -RetentionAction MoveToArchive
    ```

    > [!TIP]
    > <span data-ttu-id="d4033-p109">建議您保留期間 （ _AgeLimitForRetention_參數所定義） 的可復原的項目印會印會套用至信箱已刪除的項目保留期間相同。這可讓使用者整個刪除項目保留期間復原已刪除的項目之前他們會移到封存信箱。在上述範例中，保留期間設為 30 天的信箱已刪除的項目保留期間也是 30 天的假設情況為基礎。Exchange Online 信箱會依預設設定為 14 天內，保留已刪除的項目。但是您可以變更此設定最大值為 30 天。如需詳細資訊，請參閱[變更 Exchange Online 信箱的刪除項目保留期間](https://go.microsoft.com/fwlink/p/?LinkId=286940)。</span><span class="sxs-lookup"><span data-stu-id="d4033-p109">We recommend that the retention period (defined by the  _AgeLimitForRetention_ parameter) for the Recoverable Items RPT is the same as the deleted item retention period for the mailboxes that the RPT will be applied to. This allows a user the entire deleted item retention period to recover deleted items before they are moved to the archive mailbox. In the previous example, the retention period was set to 30 days based on the assumption that the deleted item retention period for mailboxes is also 30 days. An Exchange Online mailbox is configured to retain deleted items for 14 days, by default. But you can change this setting to a maximum of 30 days. For more information, see [Change the deleted item retention period for a mailbox in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286940).</span></span> 
  
## <a name="step-2-create-a-new-retention-policy-for-mailboxes-on-hold"></a><span data-ttu-id="d4033-161">步驟 2：為保留信箱建立新的保留原則</span><span class="sxs-lookup"><span data-stu-id="d4033-161">Step 2: Create a new retention policy for mailboxes on hold</span></span>

<span data-ttu-id="d4033-p110">下一個步驟是建立新的保留原則，並在其中新增保留標記，包括您在步驟 1 中建立的可復原的項目 RPT。下一個步驟會將這個新的原則會套用至保留信箱。 </span><span class="sxs-lookup"><span data-stu-id="d4033-p110">The next step is to create a new retention policy and add retention tags to it, including the Recoverable Items RPT that you created in Step 1. This new policy will be applied to mailboxes on hold in the next step.</span></span> 
  
<span data-ttu-id="d4033-p111">在建立新的保留原則之前，請決定您想要新增的其他保留標記。如需有關新增至預設 MRM 原則的保留標記清單及建立新保留標籤的資訊，請參閱下列資源︰</span><span class="sxs-lookup"><span data-stu-id="d4033-p111">Before you create the new retention policy, determine the additional retention tags that you want to add. For a list of the retention tags that are added to the Default MRM Policy and for information about creating new retention tags, see the following:</span></span>
  
- [<span data-ttu-id="d4033-166">預設的保留原則 in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d4033-166">Default Retention Policy in Exchange Online </span></span>](https://go.microsoft.com/fwlink/p/?LinkId=746954)
    
- [<span data-ttu-id="d4033-167">支援保留原則標記的預設資料夾</span><span class="sxs-lookup"><span data-stu-id="d4033-167">Default folders that support Retention Policy Tags</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=746957)
    
- <span data-ttu-id="d4033-168">[Create a Retention Policy](https://go.microsoft.com/fwlink/p/?LinkId=404422)主題中 「 建立保留標記 」 小節。</span><span class="sxs-lookup"><span data-stu-id="d4033-168">The "Create a retention tag" section in the [Create a Retention Policy](https://go.microsoft.com/fwlink/p/?LinkId=404422) topic.</span></span>
    
<span data-ttu-id="d4033-169">您可以使用 EAC 或 Exchange Online PowerShell 來建立保留原則。</span><span class="sxs-lookup"><span data-stu-id="d4033-169">You can use the EAC or Exchange Online PowerShell to create a retention policy.</span></span>
  
### <a name="use-the-eac-to-create-a-retention-policy"></a><span data-ttu-id="d4033-170">使用 EAC 建立保留原則</span><span class="sxs-lookup"><span data-stu-id="d4033-170">Use the EAC to create a retention policy</span></span>
  
1. <span data-ttu-id="d4033-171">在 EAC 中，移至 [**規範管理** \> **保留原則**，然後按一下 [**新增**![新增圖示](media/ITPro-EAC-AddIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="d4033-171">In the EAC, go to **Compliance management** \> **Retention policies**, and then click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif).</span></span>
    
2. <span data-ttu-id="d4033-172">在 [**新的保留原則**] 頁面上的 [**名稱**] 下輸入描述用途的保留原則的名稱例如**MRM 原則保留的信箱**。</span><span class="sxs-lookup"><span data-stu-id="d4033-172">On the **New retention policy** page, under **Name**, type a name that describes the purpose of the retention policy; for example, **MRM Policy for Mailboxes on Hold**.</span></span> 
    
3. <span data-ttu-id="d4033-173">[**保留標記**，按一下 [**新增**![新增圖示](media/ITPro-EAC-AddIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="d4033-173">Under **Retention tags**, click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="d4033-174">在清單中的保留標記，選取 [可復原的項目印您在步驟 1 中建立並再按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="d4033-174">In the list of retention tags, select the Recoverable Items RPT that you created in Step 1, and then click **Add**.</span></span>
    
    ![選取自訂的 [可復原的項目] 保留標記](media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)
  
5. <span data-ttu-id="d4033-p112">選取其他要新增至保留原則的保留標記。例如，您可能想要新增預設 MRM 原則包含的相同標記。</span><span class="sxs-lookup"><span data-stu-id="d4033-p112">Select additional retention tags to add to the retention policy. For example, you might want to add the same tags that are included in the Default MRM Policy.</span></span>
    
6. <span data-ttu-id="d4033-178">新增保留標記完成後，按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="d4033-178">When you're finished adding retention tags, click **OK**.</span></span>
    
7. <span data-ttu-id="d4033-179">按一下 [**儲存**] 以建立新的保留原則。</span><span class="sxs-lookup"><span data-stu-id="d4033-179">Click **Save** to create the new retention policy.</span></span> 
    
    <span data-ttu-id="d4033-180">請注意，連結至保留原則的保留標記會顯示在詳細資料窗格中。</span><span class="sxs-lookup"><span data-stu-id="d4033-180">Notice that the retention tags linked to the retention policy are displayed in the details pane.</span></span>
    
    ![連結到保留原則的保留標記，會顯示在詳細資料窗格中](media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)
  
### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a><span data-ttu-id="d4033-182">使用 Exchange Online PowerShell 來建立保留原則</span><span class="sxs-lookup"><span data-stu-id="d4033-182">Use Exchange Online PowerShell to create a retention policy</span></span>
  
<span data-ttu-id="d4033-183">執行下列命令為保留信箱建立新的保留原則。 </span><span class="sxs-lookup"><span data-stu-id="d4033-183">Run the following command to create new retention policy for mailboxes on hold.</span></span> 
  
```
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>

```

<span data-ttu-id="d4033-184">例如，下列命令會建立保留原則和上圖所示的連結保留標記。</span><span class="sxs-lookup"><span data-stu-id="d4033-184">For example, the following command creates the retention policy and linked retention tags that is displayed in the previous illustration.</span></span>
  
```
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```
  
## <a name="step-3-apply-the-new-retention-policy-to-mailboxes-on-hold"></a><span data-ttu-id="d4033-185">步驟 3：將新的保留原則套用至保留信箱</span><span class="sxs-lookup"><span data-stu-id="d4033-185">Step 3: Apply the new retention policy to mailboxes on hold</span></span>

<span data-ttu-id="d4033-p113">最後一個步驟是您在步驟 2 到信箱保留組織中建立新保留原則套用。您可以使用 EAC 或 Exchange Online PowerShell 將保留原則套用至單一信箱或多個信箱。</span><span class="sxs-lookup"><span data-stu-id="d4033-p113">The last step is to apply the new retention policy that you created in Step 2 to mailboxes on hold in your organization. You can use the EAC or Exchange Online PowerShell to apply the retention policy to a single mailbox or to multiple mailboxes.</span></span> 
  
### <a name="use-the-eac-to-apply-the-new-retention-policy"></a><span data-ttu-id="d4033-188">使用 EAC 套用新的保留原則</span><span class="sxs-lookup"><span data-stu-id="d4033-188">Use the EAC to apply the new retention policy</span></span>
  
1. <span data-ttu-id="d4033-189">移至 [**收件者** \> **信箱**。</span><span class="sxs-lookup"><span data-stu-id="d4033-189">Go to **Recipients** \> **Mailboxes**.</span></span>
    
2. <span data-ttu-id="d4033-190">在清單檢視中，選取您想要套用保留原則]、 的信箱] 和 [**編輯**![編輯圖示](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。</span><span class="sxs-lookup"><span data-stu-id="d4033-190">In the list view, select the mailbox you want to apply the retention policy to, and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
3. <span data-ttu-id="d4033-191">在 [**使用者信箱**] 頁面上按一下 [**信箱功能**]。</span><span class="sxs-lookup"><span data-stu-id="d4033-191">On the **User Mailbox** page, click **Mailbox features**.</span></span>
    
4. <span data-ttu-id="d4033-192">[**保留原則**] 下選取您在步驟 2 中建立的保留原則] 和 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="d4033-192">Under **Retention policy**, select the retention policy that you created in Step 2, and then click **Save**.</span></span>
    
<span data-ttu-id="d4033-193">您也可以使用 EAC 將保留原則套用至多個信箱。</span><span class="sxs-lookup"><span data-stu-id="d4033-193">You can also use the EAC to apply the retention policy to multiple mailboxes.</span></span>
  
1. <span data-ttu-id="d4033-194">移至 [**收件者** \> **信箱**。</span><span class="sxs-lookup"><span data-stu-id="d4033-194">Go to **Recipients** \> **Mailboxes**.</span></span>
    
2. <span data-ttu-id="d4033-195">在清單檢視中，使用 Shift 鍵或 Ctrl 鍵來選取多個信箱。</span><span class="sxs-lookup"><span data-stu-id="d4033-195">In the list view, use the Shift or Ctrl keys to select multiple mailboxes.</span></span>
    
3. <span data-ttu-id="d4033-196">在 [詳細資料] 窗格中，按一下 [**更多選項]**。</span><span class="sxs-lookup"><span data-stu-id="d4033-196">In the details pane, click **More options**.</span></span>
    
4. <span data-ttu-id="d4033-197">[**保留原則**] 下按一下 [**更新**]。</span><span class="sxs-lookup"><span data-stu-id="d4033-197">Under **Retention Policy**, click **Update**.</span></span>
    
5. <span data-ttu-id="d4033-198">在 **[大量指派保留原則]** 頁面上，選取您在步驟 2 建立的保留原則，然後按一下 **[儲存]**。 </span><span class="sxs-lookup"><span data-stu-id="d4033-198">On the **Bulk assign retention policy** page, select the retention policy that you created in Step 2, and then click **Save**.</span></span> 
    
### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a><span data-ttu-id="d4033-199">使用 Exchange Online PowerShell 套用新的保留原則</span><span class="sxs-lookup"><span data-stu-id="d4033-199">Use Exchange Online PowerShell to apply the new retention policy</span></span>
  
<span data-ttu-id="d4033-p114">您可以使用 Exchange Online PowerShell 將新的保留原則套用至單一信箱。但實際的 PowerShell 電源可以使用可快速識別所有訴訟暫止狀態或就地保留功能，並再新保留原則套用至所有的信箱在組織中信箱保留在單一命令中。以下是一些使用 Exchange PowerShell 將保留原則套用至一或多個信箱的範例。步驟 2 中建立保留原則套用的所有範例。</span><span class="sxs-lookup"><span data-stu-id="d4033-p114">You can use Exchange Online PowerShell to apply a new retention policy to a single mailbox. But the real power of PowerShell is that you can use it to quickly identify all the mailboxes in your organization that are on either Litigation Hold or In-Place Hold, and then apply the new retention policy to all mailboxes on hold in a single command. Here are some examples of using Exchange PowerShell to apply a retention policy to one or more mailboxes. All of the examples apply the retention policy that was created in Step 2.</span></span>
  
<span data-ttu-id="d4033-204">此範例將新的保留原則套用至 Pilar Pinilla 的信箱。</span><span class="sxs-lookup"><span data-stu-id="d4033-204">This example applies the new retention policy to Pilar Pinilla's mailbox.</span></span>
  
```
Set-Mailbox "Pilar Pinilla" -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="d4033-205">此範例將新的保留原則套用至組織中的所有訴訟資料暫留信箱。</span><span class="sxs-lookup"><span data-stu-id="d4033-205">This example applies the new retention policy to all mailboxes in the organization that are on Litigation Hold.</span></span>
  
```
$LitigationHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'}
```

```
$LitigationHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="d4033-206">此範例將新的保留原則套用至組織中的所有就地保留信箱。</span><span class="sxs-lookup"><span data-stu-id="d4033-206">This example applies the new retention policy to all mailboxes in the organization that are on In-Place Hold.</span></span>
  
```
$InPlaceHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null}
```

```
$InPlaceHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="d4033-207">您可以使用 **Get-Mailbox** Cmdlet 來確認已套用新的保留原則。</span><span class="sxs-lookup"><span data-stu-id="d4033-207">You can use the **Get-Mailbox** cmdlet to verify that the new retention policy was applied.</span></span> 
  
<span data-ttu-id="d4033-208">以下這些範例可確認先前範例中的命令已將「保留信箱的 MRM 原則」保留原則，套用至訴訟資料暫留的信箱和就地保留的信箱。</span><span class="sxs-lookup"><span data-stu-id="d4033-208">Here are some examples to verify that the commands in the previous examples applied the "MRM Policy for Mailboxes on Hold" retention policy to mailboxes on Litigation Hold and mailboxes on In-Place Hold.</span></span>
  
```
Get-Mailbox "Pilar Pinilla" | Select RetentionPolicy
```

```
Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'} | FT DisplayName,RetentionPolicy -Auto
```

```
Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null} | FT DisplayName,RetentionPolicy -Auto
```
  
## <a name="optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings"></a><span data-ttu-id="d4033-209">(選用) 步驟 4：執行受管理的資料夾助理員套用新的保留設定</span><span class="sxs-lookup"><span data-stu-id="d4033-209">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>

<span data-ttu-id="d4033-p115">您將新的保留原則套用至信箱保留之後，可能很多達 7 天在 Exchange Online 的受管理的資料夾助理員處理使用新的保留原則中設定這些信箱。而非等候受管理的資料夾助理員執行，您可以使用**Start-managedfolderassistant**指令程式來手動觸發處理套用至新的保留原則的信箱助理員。</span><span class="sxs-lookup"><span data-stu-id="d4033-p115">After you apply the new retention policy to mailboxes on hold, it can take up to 7 days in Exchange Online for the Managed Folder Assistant to process these mailboxes using the settings in the new retention policy. Instead of waiting for the Managed Folder Assistant to run, you can use the **Start-ManagedFolderAssistant** cmdlet to manually trigger the assistant to process the mailboxes that you applied the new retention policy to.</span></span> 
  
<span data-ttu-id="d4033-212">執行下列命令，對 Pilar Pinilla 的信箱啟動受管理的資料夾助理員。</span><span class="sxs-lookup"><span data-stu-id="d4033-212">Run the following command to start the Managed Folder Assistant for Pilar Pinilla's mailbox.</span></span>
  
```
Start-ManagedFolderAssistant "Pilar Pinilla"
```

<span data-ttu-id="d4033-213">執行下列命令，對所有保留信箱啟動受管理的資料夾助理員。</span><span class="sxs-lookup"><span data-stu-id="d4033-213">Run the following commands to start the Managed Folder Assistant for all mailboxes on hold.</span></span>
  
```
$MailboxesOnHold = Get-Mailbox -ResultSize unlimited | Where-Object {($_.InPlaceHolds -ne $null) -or ($_.LitigationHoldEnabled -eq "True")}
```

```
$MailboxesOnHold.DistinguishedName | Start-ManagedFolderAssistant
```

## <a name="more-information"></a><span data-ttu-id="d4033-214">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="d4033-214">More information</span></span>

- <span data-ttu-id="d4033-p116">啟用使用者的封存信箱之後，請考慮告知他們的信箱 （而不只可復原的項目] 資料夾中項目） 中的其他項目可能會移至封存信箱的使用者。這是因為預設 MRM 原則指派給 Exchange Online 信箱包含將項目移至封存信箱項目已傳遞至信箱或所建立的日期之後的兩個年度其保留標記 （具名的預設 2 年移至封存）使用者。如需詳細資訊，請參閱[Exchange Online 中的預設保留原則](https://go.microsoft.com/fwlink/p/?LinkId=746954)</span><span class="sxs-lookup"><span data-stu-id="d4033-p116">After you enable a user's archive mailbox, consider telling the user that other items in their mailbox (not just items in the Recoverable Items folder) might be moved to the archive mailbox. This is because the Default MRM Policy that's assigned to Exchange Online mailboxes contains a retention tag (named Default 2 years move to archive) that moves items to the archive mailbox two years after the date the item was delivered to the mailbox or created by the user. For more information, see [Default Retention Policy in Exchange Online ](https://go.microsoft.com/fwlink/p/?LinkId=746954)</span></span>
    
- <span data-ttu-id="d4033-p117">啟用使用者的封存信箱之後，可能會告訴使用者，他們可以復原已刪除封存信箱中 [可復原的項目] 資料夾中的項目。他們可以這麼做在 Outlook 中選取 [**刪除的郵件**] 資料夾中的封存信箱，然後按一下 [**首頁**] 索引標籤上的 [**復原刪除的項目從伺服器**。如需復原刪除的項目的詳細資訊，請參閱[復原已刪除的 Outlook for Windows 中的項目](https://go.microsoft.com/fwlink/p/?LinkId=624829)。</span><span class="sxs-lookup"><span data-stu-id="d4033-p117">After you enable a user's archive mailbox, you might also tell the user that they can recover deleted items in the Recoverable Items folder in their archive mailbox. They can do this in Outlook by selecting the **Deleted Items** folder in the archive mailbox, and then clicking **Recover Deleted Items from Server** on the **Home** tab. For more information about recovering deleted items, see [Recover deleted items in Outlook for Windows](https://go.microsoft.com/fwlink/p/?LinkId=624829).</span></span> 
