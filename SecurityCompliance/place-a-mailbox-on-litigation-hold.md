---
title: 將信箱設為訴訟暫止
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/18/2016
ms.audience: End User
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid: ''
ms.assetid: adee4621-3626-4aec-aa53-00b35ff0d0b0
description: '將信箱置於訴訟暫止狀態以保留所有信箱內容，包括已刪除的項目和已修改項目的原始版本。 '
ms.openlocfilehash: b2d2a60fddb51aa310d01a765c1ebbbf127ecd19
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296976"
---
# <a name="place-a-mailbox-on-litigation-hold"></a><span data-ttu-id="49f30-103">將信箱設為訴訟暫止</span><span class="sxs-lookup"><span data-stu-id="49f30-103">Place a mailbox on Litigation Hold</span></span>
 
<span data-ttu-id="49f30-p101">將信箱設為訴訟暫止狀態以保留所有信箱內容，包括已刪除的項目和已修改項目的原始版本。當您將使用者的信箱設為訴訟暫止，使用者封存信箱 (若已啟用) 中的內容也會處於暫止狀態。已刪除和修改過的項目會保留一段指定的期間，或直到信箱退出「訴訟暫止」狀態為止。[In-Place eDiscovery](http://technet.microsoft.com/library/6377cb7a-3416-4e15-8571-c45d2160fc6f.aspx) 搜尋時會傳回這類信箱項目。</span><span class="sxs-lookup"><span data-stu-id="49f30-p101">Place a mailbox on Litigation Hold to preserve all mailbox content, including deleted items and original versions of modified items. When you place a user' mailbox on Litigation Hold, content in the user's archive mailbox (if it's enabled) is also placed on hold. Deleted and modified items are preserved for a specified period, or until you remove the mailbox from Litigation Hold. All such mailbox items are returned in an [In-Place eDiscovery](http://technet.microsoft.com/library/6377cb7a-3416-4e15-8571-c45d2160fc6f.aspx) search.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="49f30-p102">訴訟資料暫留會保留在使用者的信箱 [可復原的項目] 資料夾中的項目。根據數量和大小的項目刪除或經過修改，可能會快速增加信箱 [可復原的項目] 資料夾的大小。可復原的項目] 資料夾是預設設定高配額。在 Exchange Online 中，此配額自動增加當您將信箱置於訴訟暫止狀態。在 Exchange Server 2013，我們建議您監視會放在訴訟暫止狀態以確保未達到的可復原的項目配額限制每週為基礎的信箱。</span><span class="sxs-lookup"><span data-stu-id="49f30-p102">Litigation Hold preserves items in the Recoverable Items folder in the user's mailbox. Depending on number and size of items deleted or modified, the size of the Recoverable Items folder of the mailbox may increase quickly. The Recoverable Items folder is configured with a high quota by default. In Exchange Online, this quota is automatically increased when you place a mailbox on Litigation Hold. In Exchange Server 2013, we recommend that you monitor mailboxes that are placed on Litigation Hold on a weekly basis to ensure they don't reach the limits of the Recoverable Items quotas.</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="49f30-113">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="49f30-113">What do you need to know before you begin?</span></span>
<span data-ttu-id="49f30-114"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="49f30-114"></span></span>

- <span data-ttu-id="49f30-115">預估完成時間：5 分鐘</span><span class="sxs-lookup"><span data-stu-id="49f30-115">Estimated time to complete: 5 minutes</span></span>
    
- <span data-ttu-id="49f30-116">訴訟暫止設定可能需要最多 60 分鐘才會生效。</span><span class="sxs-lookup"><span data-stu-id="49f30-116">The Litigation Hold setting may take up to 60 minutes to take effect.</span></span>
    
- <span data-ttu-id="49f30-p103">您必須獲得權限才能執行此程序或程序。若您需要哪些權限，請參閱[訊息原則及符合性權限](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx)主題中的 「 就地保留 」 項目。</span><span class="sxs-lookup"><span data-stu-id="49f30-p103">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "In-Place Hold" entry in the [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) topic.</span></span> 
    
- <span data-ttu-id="49f30-p104">Exchange Online 的信箱置於訴訟暫止狀態，它必須被指派 Exchange Online (Plan 2) 授權。如果信箱指派 Exchange Online (計劃 1) 的授權，您必須將其放入個別 Exchange Online 封存授權保留指派。</span><span class="sxs-lookup"><span data-stu-id="49f30-p104">To place an Exchange Online mailbox on Litigation Hold, it must be assigned an Exchange Online (Plan 2) license. If a mailbox is assigned an Exchange Online (Plan 1) license, you would have to assign it a separate Exchange Online Archiving license to place it on hold.</span></span>
    
- <span data-ttu-id="49f30-p105">如先前所述，當您置於訴訟保留使用者的信箱使用者的封存信箱中的內容也處於保留狀態。如果在 Exchange 混合部署的內部部署主要信箱上放置訴訟暫止狀態、 雲端式封存信箱 （若啟用） 也被處於保留狀態。</span><span class="sxs-lookup"><span data-stu-id="49f30-p105">As previously explained, when you place a Litigation Hold on a user's mailbox, content in the user's archive mailbox is also placed on hold. If you place a Litigation Hold on an on-premises primary mailbox in an Exchange hybrid deployment, the cloud-based archive mailbox (if enabled) is also placed on hold.</span></span>
    
- <span data-ttu-id="49f30-p106">在 Exchange Online 中，[可復原的項目] 資料夾的配額自動增加為 100 GB 當您將信箱置於訴訟暫止狀態。此資料夾的預設大小為 30 GB。</span><span class="sxs-lookup"><span data-stu-id="49f30-p106">In Exchange Online, the quota for the Recoverable Items folder is automatically increased to 100 GB when you place a mailbox on Litigation Hold. The default size of this folder is 30 GB.</span></span>
    
- <span data-ttu-id="49f30-p107">訴訟資料暫留保留已刪除的項目和也會直到撤除保留已修改項目的原始版本。您可以選擇指定保留期間指定的時間期間內保留信箱項目。如果您指定保留持續時間期間，它會計算日期接收郵件或建立信箱項目。若要保留符合您所指定之的準則的項目，請使用就地保留來建立查詢式保留。如需詳細資訊，請參閱[建立或移除就地保留](http://technet.microsoft.com/library/9d5d8d37-a053-4830-9cb1-6e1ede25e963.aspx)。</span><span class="sxs-lookup"><span data-stu-id="49f30-p107">Litigation Hold preserves deleted items and also preserves original versions of modified items until the hold is removed. You can optionally specify a hold duration, which preserves a mailbox item for the specified duration period. If you specify a hold duration period, it's calculated from the date a message is received or a mailbox item is created. To preserve items that meet your specified criteria, use an In-Place Hold to create a query-based hold. For details, see [Create or Remove an In-Place Hold](http://technet.microsoft.com/library/9d5d8d37-a053-4830-9cb1-6e1ede25e963.aspx).</span></span>
    
- <span data-ttu-id="49f30-p108">若要使用命令介面來保留上放置 Exchange Online 信箱，您必須使用 Exchange Online PowerShell。如需詳細資訊，請參閱[Connect to Exchange Online Using Remote PowerShell。](http://technet.microsoft.com/library/c8bea338-6c1a-4bdf-8de0-7895d427ee5b.aspx)</span><span class="sxs-lookup"><span data-stu-id="49f30-p108">To use the Shell to place an Exchange Online mailbox on hold, you have to use Exchange Online PowerShell. For more information, see [Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/c8bea338-6c1a-4bdf-8de0-7895d427ee5b.aspx).</span></span>
    
- <span data-ttu-id="49f30-p109">不支援將公用資料夾信箱設為訴訟暫止。您必須使用就地保留來保留公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="49f30-p109">Placing a Litigation Hold on a public folder mailbox isn't supported. You have to use In-Place Hold to place a hold on public folders.</span></span>
    
## <a name="use-the-eac-to-place-a-mailbox-on-litigation-hold"></a><span data-ttu-id="49f30-134">使用 EAC 將信箱設為訴訟暫止</span><span class="sxs-lookup"><span data-stu-id="49f30-134">Use the EAC to place a mailbox on Litigation Hold</span></span>
<span data-ttu-id="49f30-135"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="49f30-135"></span></span>

1. <span data-ttu-id="49f30-136">移至 [**收件者** \> **信箱**。</span><span class="sxs-lookup"><span data-stu-id="49f30-136">Go to **Recipients** \> **Mailboxes**.</span></span>
    
2. <span data-ttu-id="49f30-137">在使用者信箱清單中，按一下您想要置於訴訟暫止狀態、 信箱和 [**編輯**![編輯圖示](media/ITPro-EAC-EditIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="49f30-137">In the list of user mailboxes, click the mailbox that you want to place on Litigation Hold, and then click **Edit** ![Edit icon](media/ITPro-EAC-EditIcon.gif).</span></span>
    
3. <span data-ttu-id="49f30-138">在信箱內容頁面上，按一下 [**信箱功能。**</span><span class="sxs-lookup"><span data-stu-id="49f30-138">On the mailbox properties page, click **Mailbox features.**</span></span>
    
4. <span data-ttu-id="49f30-139">下**訴訟暫止狀態： 已停用**，按一下 [**啟用**信箱置於訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="49f30-139">Under **Litigation hold: Disabled**, click **Enable** to place the mailbox on Litigation Hold.</span></span> 
    
5. <span data-ttu-id="49f30-140">在**訴訟暫止狀態**] 頁面上輸入下列選用資訊：</span><span class="sxs-lookup"><span data-stu-id="49f30-140">On the **Litigation Hold** page, enter the following optional information:</span></span> 
    
  - <span data-ttu-id="49f30-p110">**訴訟保留持續時間 （天）** 使用此方塊可指定信箱處於訴訟暫止狀態時，長保留信箱項目。信箱項目會接收或建立日期被計算持續時間。如果您保留此方塊空白，項目會保留無限期或直到移除保留為止。用於持續時間指定天數。</span><span class="sxs-lookup"><span data-stu-id="49f30-p110">**Litigation hold duration (days)** Use this box to specify how long mailbox items are held when the mailbox is placed on Litigation Hold. The duration is calculated from the date a mailbox item is received or created. If you leave this box blank, items are held indefinitely or until the hold is removed. Use days to specify the duration.</span></span> 
    
  - <span data-ttu-id="49f30-p111">**附註**使用此方塊來通知他們的信箱處於訴訟暫止狀態的使用者。附註如果將會出現在使用者的信箱他們正在使用 Outlook 2010 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="49f30-p111">**Note** Use this box to inform the user their mailbox is on Litigation Hold. The note will appear in the user's mailbox if they're using Outlook 2010 or later.</span></span> 
    
  - <span data-ttu-id="49f30-p112">**URL**使用此方塊可將使用者導向至訴訟暫止狀態的詳細資訊的網站。如果其於使用 Outlook 2010 或更新版本，此 URL 會出現在使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="49f30-p112">**URL** Use this box to direct the user to a website for more information about Litigation Hold. This URL appears in the user's mailbox if they are using Outlook 2010 or later.</span></span> 
    
6. <span data-ttu-id="49f30-149">**訴訟暫止狀態**] 頁面上按一下 [**儲存**，然後按一下 [**儲存**] 信箱內容頁。</span><span class="sxs-lookup"><span data-stu-id="49f30-149">Click **Save** on the **Litigation Hold** page, and then click **Save** on the mailbox properties page.</span></span> 
  
## <a name="use-the-shell-to-place-a-mailbox-on-litigation-hold-indefinitely"></a><span data-ttu-id="49f30-150">使用命令介面將信箱設為無限期訴訟暫止</span><span class="sxs-lookup"><span data-stu-id="49f30-150">Use the Shell to place a mailbox on Litigation Hold indefinitely</span></span>
<span data-ttu-id="49f30-151"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="49f30-151"></span></span>

<span data-ttu-id="49f30-p113">本範例會將信箱 bsuneja@contoso.com 設為訴訟暫止。系統會無限期保留信箱中的項目，或將項目保留到移除保留為止。</span><span class="sxs-lookup"><span data-stu-id="49f30-p113">This example places the mailbox bsuneja@contoso.com on Litigation Hold. Items in the mailbox are held indefinitely or until the hold is removed.</span></span>
  
```
Set-Mailbox bsuneja@contoso.com -LitigationHoldEnabled $true
```

> [!NOTE]
> <span data-ttu-id="49f30-154">當您將信箱設為無限期訴訟暫止狀態 (藉由不指定時間週期)， _LitigationHoldDuration_ 屬性信箱的值會設為  `Unlimited`。</span><span class="sxs-lookup"><span data-stu-id="49f30-154">When you place a mailbox on Litigation Hold indefinitely (by not specifying a duration period), the value for the  _LitigationHoldDuration_ property mailbox is set to  `Unlimited`.</span></span> 
  
## <a name="use-the-shell-to-place-a-mailbox-on-litigation-hold-and-preserve-items-for-a-specified-duration"></a><span data-ttu-id="49f30-155">使用命令介面將信箱設為訴訟暫止，並在指定的期間保留項目</span><span class="sxs-lookup"><span data-stu-id="49f30-155">Use the Shell to place a mailbox on Litigation Hold and preserve items for a specified duration</span></span>
<span data-ttu-id="49f30-156"><a name="sectionSection3"> </a></span><span class="sxs-lookup"><span data-stu-id="49f30-156"></span></span>

<span data-ttu-id="49f30-157">本範例會將信箱 bsuneja@contoso.com 設為訴訟暫止，並保留項目 2555 天 (約 7 年)。</span><span class="sxs-lookup"><span data-stu-id="49f30-157">This example places the mailbox bsuneja@contoso.com on Litigation Hold and preserves items for 2555 days (approximately 7 years).</span></span> 
  
```
Set-Mailbox bsuneja@contoso.com -LitigationHoldEnabled $true -LitigationHoldDuration 2555
```

## <a name="use-the-shell-to-place-all-mailboxes-on-litigation-hold-for-a-specified-duration"></a><span data-ttu-id="49f30-158">使用命令介面將所有信箱針對指定的期間設為訴訟暫止</span><span class="sxs-lookup"><span data-stu-id="49f30-158">Use the Shell to place all mailboxes on Litigation Hold for a specified duration</span></span>
<span data-ttu-id="49f30-159"><a name="sectionSection4"> </a></span><span class="sxs-lookup"><span data-stu-id="49f30-159"></span></span>

<span data-ttu-id="49f30-p114">您的組織可能需要將所有信箱資料保留一段特定時間。將組織中的所有信箱設為訴訟暫止狀態之前，請考慮下列事項：</span><span class="sxs-lookup"><span data-stu-id="49f30-p114">Your organization may require that all mailbox data be preserved for a specific period of time. Before you place all mailboxes in an organization on Litigation Hold, consider the following:</span></span>
  
<span data-ttu-id="49f30-162">本範例會將組織中的所有使用者信箱設為一年 (365 天) 的訴訟暫止。</span><span class="sxs-lookup"><span data-stu-id="49f30-162">This example places all user mailboxes in the organization on Litigation Hold for one year (365 days).</span></span>
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -LitigationHoldEnabled $true -LitigationHoldDuration 365
```

<span data-ttu-id="49f30-163">範例使用 [Get-Mailbox](http://technet.microsoft.com/library/8a5a6eb9-4a75-47f9-ae3b-a3ba251cf9a8.aspx) Cmdlet 來擷取組織中的所有信箱，指定收件者篩選器來包含所有使用者信箱，然後將信箱清單傳給 [Set-Mailbox](http://technet.microsoft.com/library/a0d413b9-d949-4df6-ba96-ac0906dedae2.aspx) Cmdlet 以啟用訴訟暫止及保留期間。 </span><span class="sxs-lookup"><span data-stu-id="49f30-163">The example uses the [Get-Mailbox](http://technet.microsoft.com/library/8a5a6eb9-4a75-47f9-ae3b-a3ba251cf9a8.aspx) cmdlet to retrieve all mailboxes in the organization, specifies a recipient filter to include all user mailboxes, and then pipes the list of mailboxes to the [Set-Mailbox](http://technet.microsoft.com/library/a0d413b9-d949-4df6-ba96-ac0906dedae2.aspx) cmdlet to enable the Litigation Hold and hold duration.</span></span> 
  
<span data-ttu-id="49f30-164">若要將所有使用者信箱設為無限期保留，執行上一個命令，但不要包含  _LitigationHoldDuration_ 參數。</span><span class="sxs-lookup"><span data-stu-id="49f30-164">To place all user mailboxes on an indefinite hold, run the previous command but don't include the  _LitigationHoldDuration_ parameter.</span></span> 
  
<span data-ttu-id="49f30-165">請參閱[詳細資訊](#moreinfo.md)一節，以查看使用篩選器中的其他收件者屬性來包含或排除一或多個信箱的範例。</span><span class="sxs-lookup"><span data-stu-id="49f30-165">See the [More information](#moreinfo.md) section for examples of using other recipient properties in a filter to include or exclude one or more mailboxes.</span></span> 
  
## <a name="use-the-shell-to-remove-a-mailbox-from-litigation-hold"></a><span data-ttu-id="49f30-166">使用命令介面從訴訟暫止中移除信箱</span><span class="sxs-lookup"><span data-stu-id="49f30-166">Use the Shell to remove a mailbox from Litigation Hold</span></span>
<span data-ttu-id="49f30-167"><a name="sectionSection5"> </a></span><span class="sxs-lookup"><span data-stu-id="49f30-167"></span></span>

<span data-ttu-id="49f30-168">本範例會從訴訟暫止移除信箱 bsuneja@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="49f30-168">This example removes the mailbox bsuneja@contoso.com from Litigation Hold.</span></span>
  
```
Set-Mailbox bsuneja@contoso.com -LitigationHoldEnabled $false
```

<span data-ttu-id="49f30-169">P</span><span class="sxs-lookup"><span data-stu-id="49f30-169">P</span></span>
## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="49f30-170">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="49f30-170">How do you know this worked?</span></span>
<span data-ttu-id="49f30-171"><a name="sectionSection6"> </a></span><span class="sxs-lookup"><span data-stu-id="49f30-171"></span></span>

<span data-ttu-id="49f30-172">若要確認是否已成功將信箱設為訴訟暫止，請進行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="49f30-172">To verify that you have successfully placed a mailbox on Litigation Hold, do the one of the following:</span></span>
  
- <span data-ttu-id="49f30-173">在 EAC 中：</span><span class="sxs-lookup"><span data-stu-id="49f30-173">In the EAC:</span></span>
    
1. <span data-ttu-id="49f30-174">移至 [**收件者** \> **信箱**。</span><span class="sxs-lookup"><span data-stu-id="49f30-174">Go to **Recipients** \> **Mailboxes**.</span></span>
    
2. <span data-ttu-id="49f30-175">在使用者信箱清單中，按一下您想要確認的訴訟暫止狀態設定的信箱和 [**編輯**![編輯圖示](media/ITPro-EAC-EditIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="49f30-175">In the list of user mailboxes, click the mailbox that you want to verify Litigation Hold settings for, and then click **Edit** ![Edit icon](media/ITPro-EAC-EditIcon.gif).</span></span>
    
3. <span data-ttu-id="49f30-176">在信箱內容頁面上，按一下 [**信箱功能。**</span><span class="sxs-lookup"><span data-stu-id="49f30-176">On the mailbox properties page, click **Mailbox features.**</span></span>
    
4. <span data-ttu-id="49f30-177">在 [**訴訟暫止狀態**，確認已啟用保留。</span><span class="sxs-lookup"><span data-stu-id="49f30-177">Under **Litigation hold**, verify that hold is enabled.</span></span>
    
5. <span data-ttu-id="49f30-p115">按一下 [**檢視詳細資料]** 以確認信箱已放置在訴訟暫止狀態以及由誰時。您也可以確認或變更的選用值**訴訟保留持續時間 （天）**，**請注意**及**URL** ] 方塊。</span><span class="sxs-lookup"><span data-stu-id="49f30-p115">Click **View details** to verify when the mailbox was placed on Litigation Hold and by whom. You can also verify or change the values in the optional **Litigation hold duration (days)**, **Note**, and **URL** boxes.</span></span> 
    
- <span data-ttu-id="49f30-180">在命令介面中，執行下列任一命令：</span><span class="sxs-lookup"><span data-stu-id="49f30-180">In the Shell, run one of the following commands:</span></span>
    
  ```
  Get-Mailbox <name of mailbox> | FL LitigationHold*
  ```

    <span data-ttu-id="49f30-181">或</span><span class="sxs-lookup"><span data-stu-id="49f30-181">or</span></span>
    
  ```
  Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | FL Name,LitigationHold*
  ```

    <span data-ttu-id="49f30-182">若信箱設為無限期訴訟暫止狀態， _LitigationHoldDuration_ 屬性信箱的值會設為  `Unlimited`。</span><span class="sxs-lookup"><span data-stu-id="49f30-182">If a mailbox is placed on Litigation Hold indefinitely, the value for the  _LitigationHoldDuration_ property mailbox is set to  `Unlimited`.</span></span>
    
## <a name="more-information"></a><span data-ttu-id="49f30-183">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="49f30-183">More information</span></span>
<span data-ttu-id="49f30-184"><a name="moreinfo"> </a></span><span class="sxs-lookup"><span data-stu-id="49f30-184"></span></span>

- <span data-ttu-id="49f30-185">如果貴組織要求所有信箱資料必須保留一段特定時間，在您將組織中的所有信箱設為訴訟暫止之前，請考慮下列事項。</span><span class="sxs-lookup"><span data-stu-id="49f30-185">If your organization requires that all mailbox data has to preserved for a specific period of time, consider the following before you place all mailboxes in an organization on Litigation Hold.</span></span>
    
  - <span data-ttu-id="49f30-p116">當您使用上一個命令來保留組織的所有信箱 (或符合指定收件者篩選器的部分信箱)，只有在您執行命令時存在的信箱會被保留。如果您後來建立新的信箱，您必須再次執行此命令來保留新信箱。如果您經常建立新的信箱，您可以將命令當做排程工作，依需要而經常執行。</span><span class="sxs-lookup"><span data-stu-id="49f30-p116">When you use the previous command to place a hold on all mailboxes in an organization (or a subset of mailboxes matching a specified recipient filter) only mailboxes that exist at the time that you run the command are placed on hold. If you create new mailboxes later, you have to run the command again to place the new mailboxes on hold. If you create new mailboxes often, you can run the command as a scheduled task as frequently as required.</span></span>
    
  - <span data-ttu-id="49f30-p117">將所有信箱都放置在訴訟暫止狀態可能大幅影響信箱大小。在 Exchange Server 2013 部署組織中規劃足夠的儲存以符合您的組織保留需求。</span><span class="sxs-lookup"><span data-stu-id="49f30-p117">Placing all mailboxes on Litigation Hold can significantly impact mailbox sizes. In an Exchange Server 2013 organization, plan for adequate storage to meet your organization's preservation requirements.</span></span>
    
  - <span data-ttu-id="49f30-p118">可復原的項目] 資料夾有其專屬的儲存量限制，因此在資料夾中的項目不計算至接近信箱儲存限制。如先前所述的一段時間保留信箱資料將會產生使用者的信箱中 [可復原的項目] 資料夾的成長和封存。為了容納此增加的 Exchange Online，可復原的項目] 資料夾的配額自動從增加 30 GB 為 100 GB 當您將信箱置於訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="49f30-p118">The Recoverable Items folder has its own storage limit, so items in the folder don't count towards the mailbox storage limit. As previously explained, preserving mailbox data for a long period of time will result in growth of the Recoverable Items folder in a user's mailbox and archive. To accommodate for this increase in Exchange Online, the quota for the Recoverable Items folder is automatically increased from 30 GB to 100 GB when you place a mailbox on Litigation Hold.</span></span> 
    
    <span data-ttu-id="49f30-p119">在 Exchange Server 2013]、 [可復原的項目] 資料夾的預設儲存量限制也是 30 GB。我們建議您定期監視以確定它不會到達此限制此資料夾的大小。如需詳細資訊，請參閱 ＜ [Recoverable Items Folder](http://technet.microsoft.com/library/efc48fb4-2ed8-4d05-93af-f3505fbc389d.aspx)。</span><span class="sxs-lookup"><span data-stu-id="49f30-p119">In Exchange Server 2013, the default storage limit for the Recoverable Items folder is also 30 GB. We recommend that you periodically monitor the size of this folder to ensure it doesn't reach the limit. For more information, see [Recoverable Items Folder](http://technet.microsoft.com/library/efc48fb4-2ed8-4d05-93af-f3505fbc389d.aspx).</span></span>
    
- <span data-ttu-id="49f30-p120">要保留所有信箱的上一個命令會使用會傳回所有使用者信箱的收件者篩選。您可以使用其他收件者的屬性來傳回您可以再透過管線傳到**Set-mailbox**指令程式置於訴訟保留這些信箱的特定信箱的清單。</span><span class="sxs-lookup"><span data-stu-id="49f30-p120">The previous command to place a hold on all mailboxes uses a recipient filter that returns all user mailboxes. You can use other recipient properties to return a list of specific mailboxes that you can then pipe to the **Set-Mailbox** cmdlet to place a Litigation Hold on those mailboxes.</span></span> 
    
    <span data-ttu-id="49f30-p121">以下是一些範例使用**Get-mailbox**與**Get-recipient**指令程式來傳回常見的使用者或信箱內容為基礎的信箱的子集。下列範例會假設相關信箱內容 （例如_CustomAttributeN_或_部門_） 已填入。</span><span class="sxs-lookup"><span data-stu-id="49f30-p121">Here are some examples of using the **Get-Mailbox** and **Get-Recipient** cmdlets to return a subset of mailboxes based on common user or mailbox properties. These examples assume that relevant mailbox properties (such as  _CustomAttributeN_ or  _Department_) have been populated.</span></span>
    
  ```
  Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'CustomAttribute15 -eq "OneYearLitigationHold"'
  ```

  ```
  Get-Recipient -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'Department -eq "HR"'
  ```

  ```
  Get-Recipient -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'PostalCode -eq "98052"'
  ```

  ```
  Get-Recipient -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'StateOrProvince -eq "WA"'
  ```

  ```
  Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -ne "DiscoveryMailbox"}
  ```

    <span data-ttu-id="49f30-p122">您可以在篩選器中使用其他使用者信箱屬性來包含或排除信箱。如需詳細資訊，請參閱[Filterable Properties for the -Filter Parameter](http://technet.microsoft.com/library/b02b0005-2fb6-4bc2-8815-305259fa5432.aspx)。</span><span class="sxs-lookup"><span data-stu-id="49f30-p122">You can use other user mailbox properties in a filter to include or exclude mailboxes. For details, see [Filterable Properties for the -Filter Parameter](http://technet.microsoft.com/library/b02b0005-2fb6-4bc2-8815-305259fa5432.aspx).</span></span>
    

