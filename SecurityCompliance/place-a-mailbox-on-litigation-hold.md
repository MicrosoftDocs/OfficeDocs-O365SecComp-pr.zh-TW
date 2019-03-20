---
title: 將信箱設為訴訟暫止
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/18/2016
ms.audience: End User
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid: ''
ms.assetid: adee4621-3626-4aec-aa53-00b35ff0d0b0
description: '將信箱置於訴訟暫止來保留所有信箱內容，包括已刪除的項目和已修改項目的原始版本。 '
ms.openlocfilehash: a4d0939ffed32a8442b4b705bd15804b9f3eb7ea
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693122"
---
# <a name="place-a-mailbox-on-litigation-hold"></a><span data-ttu-id="d7f62-103">將信箱設為訴訟暫止</span><span class="sxs-lookup"><span data-stu-id="d7f62-103">Place a mailbox on Litigation Hold</span></span>
 
<span data-ttu-id="d7f62-104">將信箱置於訴訟暫止來保留所有信箱內容，包括已刪除的項目和已修改項目的原始版本。</span><span class="sxs-lookup"><span data-stu-id="d7f62-104">Place a mailbox on Litigation Hold to preserve all mailbox content, including deleted items and original versions of modified items.</span></span> <span data-ttu-id="d7f62-105">當您將使用者 ' 信箱訴訟暫止中使用者的封存信箱 （如果已啟用） 的內容也會處於暫止。</span><span class="sxs-lookup"><span data-stu-id="d7f62-105">When you place a user' mailbox on Litigation Hold, content in the user's archive mailbox (if it's enabled) is also placed on hold.</span></span> <span data-ttu-id="d7f62-106">已刪除和修改過的項目會保留一段指定的期間，或直到信箱退出「訴訟暫止」狀態為止。</span><span class="sxs-lookup"><span data-stu-id="d7f62-106">Deleted and modified items are preserved for a specified period, or until you remove the mailbox from Litigation Hold.</span></span> <span data-ttu-id="d7f62-107">[就地 eDiscovery](http://technet.microsoft.com/library/6377cb7a-3416-4e15-8571-c45d2160fc6f.aspx)搜尋時會傳回這類信箱項目。</span><span class="sxs-lookup"><span data-stu-id="d7f62-107">All such mailbox items are returned in an [In-Place eDiscovery](http://technet.microsoft.com/library/6377cb7a-3416-4e15-8571-c45d2160fc6f.aspx) search.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="d7f62-108">訴訟暫止會保留使用者信箱 [可復原的項目] 資料夾中的項目。</span><span class="sxs-lookup"><span data-stu-id="d7f62-108">Litigation Hold preserves items in the Recoverable Items folder in the user's mailbox.</span></span> <span data-ttu-id="d7f62-109">根據刪除或修改的項目數量和大小，信箱 [可復原的項目] 資料夾的大小可能會快速增加。</span><span class="sxs-lookup"><span data-stu-id="d7f62-109">Depending on number and size of items deleted or modified, the size of the Recoverable Items folder of the mailbox may increase quickly.</span></span> <span data-ttu-id="d7f62-110">[可復原的項目] 資料夾預設以高配額設定。</span><span class="sxs-lookup"><span data-stu-id="d7f62-110">The Recoverable Items folder is configured with a high quota by default.</span></span> <span data-ttu-id="d7f62-111">在 Exchange Online 中，將信箱置於訴訟暫止時，自動會增加此配額。</span><span class="sxs-lookup"><span data-stu-id="d7f62-111">In Exchange Online, this quota is automatically increased when you place a mailbox on Litigation Hold.</span></span> <span data-ttu-id="d7f62-112">在 Exchange Server 2013，我們建議您監控處於訴訟暫止週以確保它們不會達到 [可復原的項目配額的限制的信箱。</span><span class="sxs-lookup"><span data-stu-id="d7f62-112">In Exchange Server 2013, we recommend that you monitor mailboxes that are placed on Litigation Hold on a weekly basis to ensure they don't reach the limits of the Recoverable Items quotas.</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d7f62-113">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="d7f62-113">What do you need to know before you begin?</span></span>
<span data-ttu-id="d7f62-114"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="d7f62-114"></span></span>

- <span data-ttu-id="d7f62-115">預估完成時間：5 分鐘</span><span class="sxs-lookup"><span data-stu-id="d7f62-115">Estimated time to complete: 5 minutes</span></span>
    
- <span data-ttu-id="d7f62-116">訴訟暫止設定可能需要最多 60 分鐘才會生效。</span><span class="sxs-lookup"><span data-stu-id="d7f62-116">The Litigation Hold setting may take up to 60 minutes to take effect.</span></span>
    
- <span data-ttu-id="d7f62-117">您必須已獲指派權限，才能執行此程序或這些程序。</span><span class="sxs-lookup"><span data-stu-id="d7f62-117">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="d7f62-118">若要查看您需要的權限，請參閱[通訊原則及符合性權限](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx)主題中的 「 就地保留 」 項目。</span><span class="sxs-lookup"><span data-stu-id="d7f62-118">To see what permissions you need, see the "In-Place Hold" entry in the [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) topic.</span></span> 
    
- <span data-ttu-id="d7f62-119">若要啟用 Exchange Online 信箱訴訟暫止，它必須指派 Exchange Online (Plan 2) 授權。</span><span class="sxs-lookup"><span data-stu-id="d7f62-119">To place an Exchange Online mailbox on Litigation Hold, it must be assigned an Exchange Online (Plan 2) license.</span></span> <span data-ttu-id="d7f62-120">如果信箱指派 Exchange Online (方案 1) 的授權，您必須指派不同 Exchange Online Archiving 授權，才能將它放在保留它。</span><span class="sxs-lookup"><span data-stu-id="d7f62-120">If a mailbox is assigned an Exchange Online (Plan 1) license, you would have to assign it a separate Exchange Online Archiving license to place it on hold.</span></span>
    
- <span data-ttu-id="d7f62-121">如先前所述，當您將使用者的信箱上的 [訴訟暫止中使用者的封存信箱的內容也會處於暫止。</span><span class="sxs-lookup"><span data-stu-id="d7f62-121">As previously explained, when you place a Litigation Hold on a user's mailbox, content in the user's archive mailbox is also placed on hold.</span></span> <span data-ttu-id="d7f62-122">如果您訴訟暫止保留上放置在 Exchange 混合式部署中內部部署主要信箱，雲端式封存信箱 （若啟用） 也會處於保留狀態。</span><span class="sxs-lookup"><span data-stu-id="d7f62-122">If you place a Litigation Hold on an on-premises primary mailbox in an Exchange hybrid deployment, the cloud-based archive mailbox (if enabled) is also placed on hold.</span></span>
    
- <span data-ttu-id="d7f62-123">在 Exchange Online 中，[可復原的項目] 資料夾的配額會自動增加到 100GB 當您將信箱置於訴訟暫止。</span><span class="sxs-lookup"><span data-stu-id="d7f62-123">In Exchange Online, the quota for the Recoverable Items folder is automatically increased to 100 GB when you place a mailbox on Litigation Hold.</span></span> <span data-ttu-id="d7f62-124">此資料夾的預設大小為 30 GB。</span><span class="sxs-lookup"><span data-stu-id="d7f62-124">The default size of this folder is 30 GB.</span></span>
    
- <span data-ttu-id="d7f62-125">訴訟暫止狀態會保留刪除的項目，也會保留已修改項目的原始版本，直到移除暫止狀態為止。</span><span class="sxs-lookup"><span data-stu-id="d7f62-125">Litigation Hold preserves deleted items and also preserves original versions of modified items until the hold is removed.</span></span> <span data-ttu-id="d7f62-126">您可以選擇指定保留期間，這會使信箱項目保留一段指定的時間週期。</span><span class="sxs-lookup"><span data-stu-id="d7f62-126">You can optionally specify a hold duration, which preserves a mailbox item for the specified duration period.</span></span> <span data-ttu-id="d7f62-127">若您指定暫止持續時間，則將自接收訊息或建立信箱項目的日期開始計算。</span><span class="sxs-lookup"><span data-stu-id="d7f62-127">If you specify a hold duration period, it's calculated from the date a message is received or a mailbox item is created.</span></span> <span data-ttu-id="d7f62-128">若要保留符合指定的準則的項目，請使用就地保留來建立查詢式保留。</span><span class="sxs-lookup"><span data-stu-id="d7f62-128">To preserve items that meet your specified criteria, use an In-Place Hold to create a query-based hold.</span></span> <span data-ttu-id="d7f62-129">如需詳細資訊，請參閱[建立或移除就地保留](http://technet.microsoft.com/library/9d5d8d37-a053-4830-9cb1-6e1ede25e963.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d7f62-129">For details, see [Create or Remove an In-Place Hold](http://technet.microsoft.com/library/9d5d8d37-a053-4830-9cb1-6e1ede25e963.aspx).</span></span>
    
- <span data-ttu-id="d7f62-130">若要使用命令介面將 Exchange Online 信箱置於保留，您必須使用 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d7f62-130">To use the Shell to place an Exchange Online mailbox on hold, you have to use Exchange Online PowerShell.</span></span> <span data-ttu-id="d7f62-131">如需詳細資訊，請參閱[使用遠端 PowerShell 連線到 Exchange Online](http://technet.microsoft.com/library/c8bea338-6c1a-4bdf-8de0-7895d427ee5b.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d7f62-131">For more information, see [Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/c8bea338-6c1a-4bdf-8de0-7895d427ee5b.aspx).</span></span>
    
- <span data-ttu-id="d7f62-132">將 [公用資料夾信箱置於 [訴訟暫止不支援。</span><span class="sxs-lookup"><span data-stu-id="d7f62-132">Placing a Litigation Hold on a public folder mailbox isn't supported.</span></span> <span data-ttu-id="d7f62-133">您必須使用就地保留功能來保留公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="d7f62-133">You have to use In-Place Hold to place a hold on public folders.</span></span>
    
## <a name="use-the-eac-to-place-a-mailbox-on-litigation-hold"></a><span data-ttu-id="d7f62-134">使用 EAC 將信箱設為訴訟暫止</span><span class="sxs-lookup"><span data-stu-id="d7f62-134">Use the EAC to place a mailbox on Litigation Hold</span></span>
<span data-ttu-id="d7f62-135"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="d7f62-135"></span></span>

1. <span data-ttu-id="d7f62-136">前往 [**收件者** \> **信箱**。</span><span class="sxs-lookup"><span data-stu-id="d7f62-136">Go to **Recipients** \> **Mailboxes**.</span></span>
    
2. <span data-ttu-id="d7f62-137">在使用者信箱清單中，按一下您想要放置訴訟暫止的信箱，然後按一下 [**編輯**![編輯圖示](media/ITPro-EAC-EditIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="d7f62-137">In the list of user mailboxes, click the mailbox that you want to place on Litigation Hold, and then click **Edit** ![Edit icon](media/ITPro-EAC-EditIcon.gif).</span></span>
    
3. <span data-ttu-id="d7f62-138">在信箱內容頁面上，按一下 [**的信箱功能。**</span><span class="sxs-lookup"><span data-stu-id="d7f62-138">On the mailbox properties page, click **Mailbox features.**</span></span>
    
4. <span data-ttu-id="d7f62-139">[**訴訟暫止： 停用**，按一下 [**啟用**]，以讓信箱處於訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="d7f62-139">Under **Litigation hold: Disabled**, click **Enable** to place the mailbox on Litigation Hold.</span></span> 
    
5. <span data-ttu-id="d7f62-140">在 [**訴訟暫止**] 頁面上，輸入下列選擇性資訊：</span><span class="sxs-lookup"><span data-stu-id="d7f62-140">On the **Litigation Hold** page, enter the following optional information:</span></span> 
    
  - <span data-ttu-id="d7f62-141">**訴訟暫止持續時間 （天）** 使用此方塊來指定當信箱處於訴訟暫止的信箱項目保留多久。</span><span class="sxs-lookup"><span data-stu-id="d7f62-141">**Litigation hold duration (days)** Use this box to specify how long mailbox items are held when the mailbox is placed on Litigation Hold.</span></span> <span data-ttu-id="d7f62-142">持續時間自接收或建立信箱項目的日期開始計算。</span><span class="sxs-lookup"><span data-stu-id="d7f62-142">The duration is calculated from the date a mailbox item is received or created.</span></span> <span data-ttu-id="d7f62-143">如果您將此方塊保留空白，則會無限期保留項目，或將項目保留到移除保留為止。</span><span class="sxs-lookup"><span data-stu-id="d7f62-143">If you leave this box blank, items are held indefinitely or until the hold is removed.</span></span> <span data-ttu-id="d7f62-144">請使用天數為單位來指定持續時間。</span><span class="sxs-lookup"><span data-stu-id="d7f62-144">Use days to specify the duration.</span></span> 
    
  - <span data-ttu-id="d7f62-145">**附註**使用此方塊告知使用者他們的信箱處於訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="d7f62-145">**Note** Use this box to inform the user their mailbox is on Litigation Hold.</span></span> <span data-ttu-id="d7f62-146">附註將會出現在使用者的信箱中，如果他們使用 Outlook 2010 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="d7f62-146">The note will appear in the user's mailbox if they're using Outlook 2010 or later.</span></span> 
    
  - <span data-ttu-id="d7f62-147">**URL**使用此方塊可將使用者導向至網站，使其訴訟暫止狀態的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="d7f62-147">**URL** Use this box to direct the user to a website for more information about Litigation Hold.</span></span> <span data-ttu-id="d7f62-148">如果他們使用 Outlook 2010 或更新版本，此 URL 會出現在使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="d7f62-148">This URL appears in the user's mailbox if they are using Outlook 2010 or later.</span></span> 
    
6. <span data-ttu-id="d7f62-149">在 [**訴訟暫止**] 頁面上，按一下 [**儲存**，然後按一下 [信箱內容] 頁面上的 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="d7f62-149">Click **Save** on the **Litigation Hold** page, and then click **Save** on the mailbox properties page.</span></span> 
  
## <a name="use-the-shell-to-place-a-mailbox-on-litigation-hold-indefinitely"></a><span data-ttu-id="d7f62-150">使用命令介面來啟用信箱無限期訴訟暫止</span><span class="sxs-lookup"><span data-stu-id="d7f62-150">Use the Shell to place a mailbox on Litigation Hold indefinitely</span></span>
<span data-ttu-id="d7f62-151"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="d7f62-151"></span></span>

<span data-ttu-id="d7f62-p113">本範例會將信箱 bsuneja@contoso.com 設為訴訟暫止。系統會無限期保留信箱中的項目，或將項目保留到移除保留為止。</span><span class="sxs-lookup"><span data-stu-id="d7f62-p113">This example places the mailbox bsuneja@contoso.com on Litigation Hold. Items in the mailbox are held indefinitely or until the hold is removed.</span></span>
  
```
Set-Mailbox bsuneja@contoso.com -LitigationHoldEnabled $true
```

> [!NOTE]
> <span data-ttu-id="d7f62-154">當您將信箱設為無限期訴訟暫止狀態 (藉由不指定時間週期)， _LitigationHoldDuration_ 屬性信箱的值會設為  `Unlimited`。</span><span class="sxs-lookup"><span data-stu-id="d7f62-154">When you place a mailbox on Litigation Hold indefinitely (by not specifying a duration period), the value for the  _LitigationHoldDuration_ property mailbox is set to  `Unlimited`.</span></span> 
  
## <a name="use-the-shell-to-place-a-mailbox-on-litigation-hold-and-preserve-items-for-a-specified-duration"></a><span data-ttu-id="d7f62-155">使用命令介面將信箱設為訴訟暫止，並於指定期間內保留項目</span><span class="sxs-lookup"><span data-stu-id="d7f62-155">Use the Shell to place a mailbox on Litigation Hold and preserve items for a specified duration</span></span>
<span data-ttu-id="d7f62-156"><a name="sectionSection3"> </a></span><span class="sxs-lookup"><span data-stu-id="d7f62-156"></span></span>

<span data-ttu-id="d7f62-157">本範例會將信箱 bsuneja@contoso.com 設為訴訟暫止，並保留項目 2555 天 (約 7 年)。</span><span class="sxs-lookup"><span data-stu-id="d7f62-157">This example places the mailbox bsuneja@contoso.com on Litigation Hold and preserves items for 2555 days (approximately 7 years).</span></span> 
  
```
Set-Mailbox bsuneja@contoso.com -LitigationHoldEnabled $true -LitigationHoldDuration 2555
```

## <a name="use-the-shell-to-place-all-mailboxes-on-litigation-hold-for-a-specified-duration"></a><span data-ttu-id="d7f62-158">使用命令介面來啟用所有信箱訴訟暫止於指定期間內</span><span class="sxs-lookup"><span data-stu-id="d7f62-158">Use the Shell to place all mailboxes on Litigation Hold for a specified duration</span></span>
<span data-ttu-id="d7f62-159"><a name="sectionSection4"> </a></span><span class="sxs-lookup"><span data-stu-id="d7f62-159"></span></span>

<span data-ttu-id="d7f62-160">您的組織可能需要一段特定時間，保留所有信箱資料。</span><span class="sxs-lookup"><span data-stu-id="d7f62-160">Your organization may require that all mailbox data be preserved for a specific period of time.</span></span> <span data-ttu-id="d7f62-161">您將所有信箱置於訴訟暫止組織之前，請考慮下列項目：</span><span class="sxs-lookup"><span data-stu-id="d7f62-161">Before you place all mailboxes in an organization on Litigation Hold, consider the following:</span></span>
  
<span data-ttu-id="d7f62-162">本範例會將一年 （365 天） 的訴訟暫止組織中的所有使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="d7f62-162">This example places all user mailboxes in the organization on Litigation Hold for one year (365 days).</span></span>
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -LitigationHoldEnabled $true -LitigationHoldDuration 365
```

<span data-ttu-id="d7f62-163">此範例使用[Get-mailbox](http://technet.microsoft.com/library/8a5a6eb9-4a75-47f9-ae3b-a3ba251cf9a8.aspx)指令程式來擷取組織中的所有信箱、 指定收件者篩選器，包括所有的使用者信箱，並再以管線傳輸至[Set-mailbox](http://technet.microsoft.com/library/a0d413b9-d949-4df6-ba96-ac0906dedae2.aspx)指令程式，以啟用訴訟暫止的信箱清單和保留持續時間。</span><span class="sxs-lookup"><span data-stu-id="d7f62-163">The example uses the [Get-Mailbox](http://technet.microsoft.com/library/8a5a6eb9-4a75-47f9-ae3b-a3ba251cf9a8.aspx) cmdlet to retrieve all mailboxes in the organization, specifies a recipient filter to include all user mailboxes, and then pipes the list of mailboxes to the [Set-Mailbox](http://technet.microsoft.com/library/a0d413b9-d949-4df6-ba96-ac0906dedae2.aspx) cmdlet to enable the Litigation Hold and hold duration.</span></span> 
  
<span data-ttu-id="d7f62-164">若要將所有使用者信箱設為無限期保留，執行上一個命令，但不要包含  _LitigationHoldDuration_ 參數。</span><span class="sxs-lookup"><span data-stu-id="d7f62-164">To place all user mailboxes on an indefinite hold, run the previous command but don't include the  _LitigationHoldDuration_ parameter.</span></span> 
  
<span data-ttu-id="d7f62-165">請參閱[詳細資訊](#moreinfo.md)一節，以查看使用篩選器中的其他收件者屬性來包含或排除一或多個信箱的範例。</span><span class="sxs-lookup"><span data-stu-id="d7f62-165">See the [More information](#moreinfo.md) section for examples of using other recipient properties in a filter to include or exclude one or more mailboxes.</span></span> 
  
## <a name="use-the-shell-to-remove-a-mailbox-from-litigation-hold"></a><span data-ttu-id="d7f62-166">使用命令介面從訴訟暫止移除信箱</span><span class="sxs-lookup"><span data-stu-id="d7f62-166">Use the Shell to remove a mailbox from Litigation Hold</span></span>
<span data-ttu-id="d7f62-167"><a name="sectionSection5"> </a></span><span class="sxs-lookup"><span data-stu-id="d7f62-167"></span></span>

<span data-ttu-id="d7f62-168">本範例會從訴訟暫止移除信箱 bsuneja@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="d7f62-168">This example removes the mailbox bsuneja@contoso.com from Litigation Hold.</span></span>
  
```
Set-Mailbox bsuneja@contoso.com -LitigationHoldEnabled $false
```

<span data-ttu-id="d7f62-169">P</span><span class="sxs-lookup"><span data-stu-id="d7f62-169">P</span></span>
## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="d7f62-170">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="d7f62-170">How do you know this worked?</span></span>
<span data-ttu-id="d7f62-171"><a name="sectionSection6"> </a></span><span class="sxs-lookup"><span data-stu-id="d7f62-171"></span></span>

<span data-ttu-id="d7f62-172">若要確認是否已成功將信箱設為訴訟暫止，請進行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="d7f62-172">To verify that you have successfully placed a mailbox on Litigation Hold, do the one of the following:</span></span>
  
- <span data-ttu-id="d7f62-173">在 EAC 中：</span><span class="sxs-lookup"><span data-stu-id="d7f62-173">In the EAC:</span></span>
    
1. <span data-ttu-id="d7f62-174">前往 [**收件者** \> **信箱**。</span><span class="sxs-lookup"><span data-stu-id="d7f62-174">Go to **Recipients** \> **Mailboxes**.</span></span>
    
2. <span data-ttu-id="d7f62-175">在使用者信箱清單中，按一下您想確認訴訟暫止設定的信箱，然後按一下 [**編輯**![編輯圖示](media/ITPro-EAC-EditIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="d7f62-175">In the list of user mailboxes, click the mailbox that you want to verify Litigation Hold settings for, and then click **Edit** ![Edit icon](media/ITPro-EAC-EditIcon.gif).</span></span>
    
3. <span data-ttu-id="d7f62-176">在信箱內容頁面上，按一下 [**的信箱功能。**</span><span class="sxs-lookup"><span data-stu-id="d7f62-176">On the mailbox properties page, click **Mailbox features.**</span></span>
    
4. <span data-ttu-id="d7f62-177">在 [**訴訟暫止狀態**，確認已啟用保留。</span><span class="sxs-lookup"><span data-stu-id="d7f62-177">Under **Litigation hold**, verify that hold is enabled.</span></span>
    
5. <span data-ttu-id="d7f62-178">按一下 [**檢視詳細資料]** 來確認信箱已處於訴訟暫止及由誰。</span><span class="sxs-lookup"><span data-stu-id="d7f62-178">Click **View details** to verify when the mailbox was placed on Litigation Hold and by whom.</span></span> <span data-ttu-id="d7f62-179">您也可以確認或變更的值在選擇性**訴訟暫止持續時間 （天）**，**附註**，以及**URL** ] 方塊。</span><span class="sxs-lookup"><span data-stu-id="d7f62-179">You can also verify or change the values in the optional **Litigation hold duration (days)**, **Note**, and **URL** boxes.</span></span> 
    
- <span data-ttu-id="d7f62-180">在命令介面中執行下列其中一個下列命令：</span><span class="sxs-lookup"><span data-stu-id="d7f62-180">In the Shell, run one of the following commands:</span></span>
    
  ```
  Get-Mailbox <name of mailbox> | FL LitigationHold*
  ```

    <span data-ttu-id="d7f62-181">或</span><span class="sxs-lookup"><span data-stu-id="d7f62-181">or</span></span>
    
  ```
  Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | FL Name,LitigationHold*
  ```

    <span data-ttu-id="d7f62-182">若信箱設為無限期訴訟暫止狀態， _LitigationHoldDuration_ 屬性信箱的值會設為  `Unlimited`。</span><span class="sxs-lookup"><span data-stu-id="d7f62-182">If a mailbox is placed on Litigation Hold indefinitely, the value for the  _LitigationHoldDuration_ property mailbox is set to  `Unlimited`.</span></span>
    
## <a name="more-information"></a><span data-ttu-id="d7f62-183">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="d7f62-183">More information</span></span>
<span data-ttu-id="d7f62-184"><a name="moreinfo"> </a></span><span class="sxs-lookup"><span data-stu-id="d7f62-184"></span></span>

- <span data-ttu-id="d7f62-185">如果貴組織要求所有信箱資料必須保留一段特定時間，在您將組織中的所有信箱設為訴訟暫止之前，請考慮下列事項。</span><span class="sxs-lookup"><span data-stu-id="d7f62-185">If your organization requires that all mailbox data has to preserved for a specific period of time, consider the following before you place all mailboxes in an organization on Litigation Hold.</span></span>
    
  - <span data-ttu-id="d7f62-p116">當您使用上一個命令來保留組織的所有信箱 (或符合指定收件者篩選器的部分信箱)，只有在您執行命令時存在的信箱會被保留。如果您後來建立新的信箱，您必須再次執行此命令來保留新信箱。如果您經常建立新的信箱，您可以將命令當做排程工作，依需要而經常執行。</span><span class="sxs-lookup"><span data-stu-id="d7f62-p116">When you use the previous command to place a hold on all mailboxes in an organization (or a subset of mailboxes matching a specified recipient filter) only mailboxes that exist at the time that you run the command are placed on hold. If you create new mailboxes later, you have to run the command again to place the new mailboxes on hold. If you create new mailboxes often, you can run the command as a scheduled task as frequently as required.</span></span>
    
  - <span data-ttu-id="d7f62-189">將所有信箱設為訴訟暫止可能對信箱大小造成重大影響。</span><span class="sxs-lookup"><span data-stu-id="d7f62-189">Placing all mailboxes on Litigation Hold can significantly impact mailbox sizes.</span></span> <span data-ttu-id="d7f62-190">在 Exchange Server 2013 組織中，請規劃足夠的儲存空間，以符合組織的保留需求。</span><span class="sxs-lookup"><span data-stu-id="d7f62-190">In an Exchange Server 2013 organization, plan for adequate storage to meet your organization's preservation requirements.</span></span>
    
  - <span data-ttu-id="d7f62-191">[可復原的項目] 資料夾本身有其儲存限制，所以資料夾中的項目不計入信箱儲存限制中。</span><span class="sxs-lookup"><span data-stu-id="d7f62-191">The Recoverable Items folder has its own storage limit, so items in the folder don't count towards the mailbox storage limit.</span></span> <span data-ttu-id="d7f62-192">如同先前所解說，長時間保留信箱資料會導致使用者信箱和封存中 [可復原的項目] 資料夾的大小增加。</span><span class="sxs-lookup"><span data-stu-id="d7f62-192">As previously explained, preserving mailbox data for a long period of time will result in growth of the Recoverable Items folder in a user's mailbox and archive.</span></span> <span data-ttu-id="d7f62-193">若要容納此增加在 Exchange Online，[可復原的項目] 資料夾的配額會自動增加從 30 GB 至 100 GB 將信箱置於訴訟暫止時。</span><span class="sxs-lookup"><span data-stu-id="d7f62-193">To accommodate for this increase in Exchange Online, the quota for the Recoverable Items folder is automatically increased from 30 GB to 100 GB when you place a mailbox on Litigation Hold.</span></span> 
    
    <span data-ttu-id="d7f62-194">在 Exchange Server 2013 中，[可復原的項目] 資料夾的預設儲存量限制也是 30 GB。</span><span class="sxs-lookup"><span data-stu-id="d7f62-194">In Exchange Server 2013, the default storage limit for the Recoverable Items folder is also 30 GB.</span></span> <span data-ttu-id="d7f62-195">建議您定期監視此資料夾大小，以確保未達到限制。</span><span class="sxs-lookup"><span data-stu-id="d7f62-195">We recommend that you periodically monitor the size of this folder to ensure it doesn't reach the limit.</span></span> <span data-ttu-id="d7f62-196">如需詳細資訊，請參閱 < <b0>Recoverable Items Folder</b0>。</span><span class="sxs-lookup"><span data-stu-id="d7f62-196">For more information, see [Recoverable Items Folder](http://technet.microsoft.com/library/efc48fb4-2ed8-4d05-93af-f3505fbc389d.aspx).</span></span>
    
- <span data-ttu-id="d7f62-197">要保留所有信箱的前一個命令，是使用會傳回所有使用者信箱的收件者篩選器。</span><span class="sxs-lookup"><span data-stu-id="d7f62-197">The previous command to place a hold on all mailboxes uses a recipient filter that returns all user mailboxes.</span></span> <span data-ttu-id="d7f62-198">您可以使用其他收件者的屬性以傳回您然後輸送至**Set-mailbox** cmdlet 以將這些信箱上的 [訴訟暫止狀態的特定信箱的清單。</span><span class="sxs-lookup"><span data-stu-id="d7f62-198">You can use other recipient properties to return a list of specific mailboxes that you can then pipe to the **Set-Mailbox** cmdlet to place a Litigation Hold on those mailboxes.</span></span> 
    
    <span data-ttu-id="d7f62-199">以下是一些使用**Get-mailbox**和**Get-recipient**指令程式可傳回根據一般使用者或信箱內容的信箱子集的範例。</span><span class="sxs-lookup"><span data-stu-id="d7f62-199">Here are some examples of using the **Get-Mailbox** and **Get-Recipient** cmdlets to return a subset of mailboxes based on common user or mailbox properties.</span></span> <span data-ttu-id="d7f62-200">這些範例假設相關的信箱屬性 (例如  _CustomAttributeN_ 或  _Department_) 皆已填入。</span><span class="sxs-lookup"><span data-stu-id="d7f62-200">These examples assume that relevant mailbox properties (such as  _CustomAttributeN_ or  _Department_) have been populated.</span></span>
    
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

    <span data-ttu-id="d7f62-p122">您可以在篩選器中使用其他使用者信箱屬性來包含或排除信箱。如需詳細資訊，請參閱[Filterable Properties for the -Filter Parameter](http://technet.microsoft.com/library/b02b0005-2fb6-4bc2-8815-305259fa5432.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d7f62-p122">You can use other user mailbox properties in a filter to include or exclude mailboxes. For details, see [Filterable Properties for the -Filter Parameter](http://technet.microsoft.com/library/b02b0005-2fb6-4bc2-8815-305259fa5432.aspx).</span></span>
    

