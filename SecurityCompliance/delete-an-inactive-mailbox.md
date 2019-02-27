---
title: 刪除非作用中的信箱在 Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
description: 當您不再需要保留的 Office 365 不在作用中信箱內容時，您可以藉由移除保留永久刪除非使用中的信箱。之後移除保留，非使用中信箱標記為待刪除，然後會永久刪除之後會處理。
ms.openlocfilehash: 6af107face519ac18d5b072d675e76f70dc4c4a6
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295736"
---
# <a name="delete-an-inactive-mailbox-in-office-365"></a><span data-ttu-id="ee5e8-104">刪除非作用中的信箱在 Office 365</span><span class="sxs-lookup"><span data-stu-id="ee5e8-104">Delete an inactive mailbox in Office 365</span></span>

<span data-ttu-id="ee5e8-p102">非使用中的信箱用來保留先前員工的電子郵件之後他離開貴組織。當您不再需要保留非使用中信箱的內容時，您可以藉由移除保留永久刪除非使用中的信箱。此外，很可能多個保留可能會被放置在非使用中的信箱。例如，非使用中的信箱可能放置訴訟暫止狀態以及一或多個就地保留。此外，Office 365 保留原則 (建立 Office 365 安全性&amp;規範中心) 可能會套用至非使用中的信箱。您必須將它刪除非使用中信箱中移除所有的保留與 Office 365 的保留原則。移除保留和保留原則之後，非使用中信箱標記為待刪除並永久刪除之後會處理。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-p102">An inactive mailbox is used to preserve a former employee's email after he or she leaves your organization. When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold. Also, it's possible that multiple holds might be placed on an inactive mailbox. For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds. Additionally, an Office 365 retention policy (created in the Office 365 Security &amp; Compliance Center) might be applied to the inactive mailbox. You have to remove all holds and Office 365 retention policies from an inactive mailbox to delete it. After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ee5e8-p103">我們已將 2017 年 7 月 1 日的期限延後，以建立新的「就地保留」來建立非使用中的信箱。但到今年年底或明年年初，您將無法在 Exchange Online 中建立新的「就地保留」。到時，只有「訴訟資料暫留」和 Office 365 保留原則可以用來建立非使用中的信箱。不過，仍會支援「就地保留」上現有的非使用中信箱，並且您可以繼續管理非使用信箱上的「就地保留」。這包括變更「就地保留」期間，以及透過移除「就地保留」永久刪除非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-p103">We've postponed the July 1, 2017 deadline for creating new In-Place Holds to make a mailbox inactive. But later this year or early next year, you won't be able to create new In-Place Holds in Exchange Online. At that time, only Litigation Holds and Office 365 retention policies can be used to create an inactive mailbox. However, existing inactive mailboxes that are on In-Place Hold will still be supported, and you can continue to manage the In-Place Holds on inactive mailboxes. This includes changing the duration of an In-Place Hold and permanently deleting an inactive mailbox by removing the In-Place Hold.</span></span> 
  
<span data-ttu-id="ee5e8-117">請參閱[的詳細資訊](delete-an-inactive-mailbox.md#moreinfo)] 區段中的什麼之後保留已從非使用中信箱的描述。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-117">See the [More information](delete-an-inactive-mailbox.md#moreinfo) section for a description of what happens after holds are removed from an inactive mailbox.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="ee5e8-118">開始之前</span><span class="sxs-lookup"><span data-stu-id="ee5e8-118">Before you begin</span></span>

- <span data-ttu-id="ee5e8-p104">您必須使用 Exchange Online PowerShell 來移除訴訟暫止狀態不在作用中的信箱。您無法使用 Exchange 系統管理中心 (EAC)。如需逐步說明，請參閱[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554)。您可以使用 Exchange Online PowerShell 或 EAC 來移除就地保留非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-p104">You have to use Exchange Online PowerShell to remove a Litigation Hold from an inactive mailbox. You can't use the Exchange admin center (EAC). For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554). You can use Exchange Online PowerShell or the EAC to remove an In-Place Hold from an inactive mailbox.</span></span> 
    
- <span data-ttu-id="ee5e8-p105">您可以將非使用中信箱的內容複製到另一個信箱之前移除保留及刪除非作用中的信箱。如需詳細資訊，請參閱[還原 Office 365 中的非使用中信箱](restore-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-p105">You can copy the contents of an inactive mailbox to another mailbox before you remove the hold and delete an inactive mailbox. For details, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="ee5e8-p106">如果您移除保留或 Office 365 保留原則不在作用中信箱和虛刪除信箱保留期間內的信箱已過期，將會永久刪除信箱。會在刪除後，它無法復原。移除保留之前，請確定您不再需要信箱中的內容。如果您想要重新啟動 [非使用中的信箱，您就可以進行復原。如需詳細資訊，請參閱[Office 365 中的不在作用中信箱復原](recover-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-p106">If you remove the hold or Office 365 retention policy from an inactive mailbox and the soft-deleted mailbox retention period for the mailbox has expired, the mailbox will be permanently deleted. After it's deleted, it can't be recovered. Before you remove the hold, be sure that you no longer need the contents in the mailbox. If you want to re-activate an inactive mailbox, you can recover it. For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="ee5e8-130">如需非使用中信箱的詳細資訊，請參閱[Office 365 中的非使用中信箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-130">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="ee5e8-131">步驟 1： 識別非使用中信箱的保留</span><span class="sxs-lookup"><span data-stu-id="ee5e8-131">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="ee5e8-p107">先前所述，不在作用中的信箱上可能會被放置訴訟暫止狀態、 就地保留功能，或 Office 365 的保留原則。第一個步驟是識別非使用中信箱的保留。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-p107">As previously stated, a Litigation Hold, In-Place Hold, or Office 365 retention policy might be placed on an inactive mailbox. The first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="ee5e8-134">執行下列命令以顯示您組織中的所有非使用中信箱的保留資訊。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-134">Run the following command to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

<span data-ttu-id="ee5e8-p108">**LitigationHoldEnabled**屬性值為**True**表示非使用中信箱處於訴訟暫止狀態。如果就地保留處於非使用中的信箱，保留 GUID 會顯示為**InPlaceHolds**屬性的值。例如，兩個非使用中信箱的下列結果顯示 Ann Beebe 的處於訴訟暫止狀態和兩個就地保留會放在 Pilar Pinilla。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-p108">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold. If an In-Place Hold is placed on an inactive mailbox, the GUID for the hold is displayed as the value for the **InPlaceHolds** property. For example, the following results for two inactive mailboxes show that a Litigation Hold is placed on Ann Beebe and that two In-Place Holds are placed on Pilar Pinilla.</span></span> 
  
```
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, ba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> <span data-ttu-id="ee5e8-p109">如果許多的就地保留處於非使用中的信箱，將會顯示不是所有的就地保留 Guid。您可以執行下列命令以顯示所有為 「 就地保留 Guid：`Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span><span class="sxs-lookup"><span data-stu-id="ee5e8-p109">If a lot of In-Place Holds are placed on an inactive mailbox, not all of the In-Place Hold GUIDs will be displayed. You can run the following command to display all the In-Place Hold GUIDs:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span></span>
  
## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a><span data-ttu-id="ee5e8-140">步驟 2： 從非使用中的信箱移除保留</span><span class="sxs-lookup"><span data-stu-id="ee5e8-140">Step 2: Remove a hold from an inactive mailbox</span></span>

<span data-ttu-id="ee5e8-p110">在您識別何種類型的保留處於非使用中信箱之後 （以及是否有多個保留） 下, 一步是要移除信箱的保留。先前所述，您必須移除若要永久刪除非作用中信箱的所有保留。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-p110">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to remove the holds on the mailbox. As previously stated, you have to remove all holds to permanently delete an inactive mailbox.</span></span> 
  
### <a name="remove-a-litigation-hold"></a><span data-ttu-id="ee5e8-143">移除訴訟暫止狀態</span><span class="sxs-lookup"><span data-stu-id="ee5e8-143">Remove a Litigation Hold</span></span>

<span data-ttu-id="ee5e8-p111">先前所述，您必須使用 Windows PowerShell 移除從非使用中信箱的訴訟暫止狀態。您無法使用 EAC。執行下列命令以移除訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-p111">As previously stated, you have to use Windows PowerShell to remove a Litigation Hold from an inactive mailbox. You can't use the EAC. Run the following command to remove a Litigation Hold.</span></span>
  
```
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> <span data-ttu-id="ee5e8-p112">識別非使用中信箱的最佳方式是使用其辨別名稱或 Exchange 的 GUID 值。使用下列值之一有助於防止不慎指定了錯誤的信箱。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-p112">The best way to identify an inactive mailbox is by using its Distinguished Name or Exchange GUID value. Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="remove-in-place-holds"></a><span data-ttu-id="ee5e8-149">移除就地保留</span><span class="sxs-lookup"><span data-stu-id="ee5e8-149">Remove In-Place Holds</span></span>

 <span data-ttu-id="ee5e8-150">有兩種方式移除就地保留非使用中的信箱：</span><span class="sxs-lookup"><span data-stu-id="ee5e8-150">There are two ways to remove an In-Place Hold from an inactive mailbox:</span></span> 
  
- <span data-ttu-id="ee5e8-151">**刪除就地保留物件**如果您想要永久地刪除非使用中信箱是唯一的來源信箱的就地保留，您可以只刪除就地保留物件。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-151">**Delete the In-Place Hold object** If the inactive mailbox that you want to permanently delete is the only source mailbox for an In-Place Hold, you can just delete the In-Place Hold object.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="ee5e8-p113">您必須停用保留才能刪除就地保留的物件。如果您嘗試刪除已啟用保留就地保留物件，您會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-p113">You have to disable the hold before you can delete an In-Place Hold object. If you try to delete an In-Place Hold object that has the hold enabled, you'll receive an error message.</span></span> 
  
- <span data-ttu-id="ee5e8-154">**移除不在作用中信箱為來源信箱的就地保留**如果您想要保留其他來源信箱的就地保留，您可以從來源信箱清單中移除的非使用中的信箱並保留就地保留物件。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-154">**Remove the inactive mailbox as a source mailbox of an In-Place Hold** If you want to retain other source mailboxes for an In-Place Hold, you can remove the inactive mailbox from the list of source mailboxes and keep the In-Place Hold object.</span></span> 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a><span data-ttu-id="ee5e8-155">使用 EAC 來刪除就地保留</span><span class="sxs-lookup"><span data-stu-id="ee5e8-155">Use the EAC to delete an In-Place Hold</span></span>

1. <span data-ttu-id="ee5e8-p114">如果您知道您想要刪除就地保留的名稱，您可以前往下一個步驟。否則請執行下列命令以取得您想要永久地刪除非使用中信箱處於就地保留的名稱。使用就地保留 GUID 所取得的[步驟 1： 識別非使用中的信箱上保留](delete-an-inactive-mailbox.md#step1)。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-p114">If you know the name of the In-Place Hold that you want to delete, you can go to the next step. Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox that you want to permanently delete. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](delete-an-inactive-mailbox.md#step1).</span></span>
    
```
  Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
```

2. <span data-ttu-id="ee5e8-159">在 EAC 中，移至 [**規範管理** \> **就地 eDiscovery&amp;保留**。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-159">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="ee5e8-160">選取您要刪除的就地保留，然後按一下 [**編輯**![編輯圖示](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-160">Select the In-Place Hold you want to delete, and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="ee5e8-161">在**就地 eDiscovery&amp;保留**屬性頁面、 按一下 [**就地保留**、 取消核取 [**比對搜尋查詢中所選取的信箱上進行內容保留**] 方塊中，然後再按一下 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-161">On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**, uncheck the **Place content matching the search query in selected mailboxes on hold** box, and then click **Save**.</span></span>
    
5. <span data-ttu-id="ee5e8-162">在**就地 eDiscovery&amp;保留**頁面、 就地保留請再次選取，然後再按一下 [**刪除**![刪除圖示](media/87565fbb-5147-4f22-9ed7-1c18ce664392.png)。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-162">On the **In-Place eDiscovery &amp; Hold** page, select the In-Place Hold again, and then click **Delete**![Delete icon](media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>
    
6. <span data-ttu-id="ee5e8-163">在警告中，按一下 [**是]** 以刪除就地保留]。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-163">On the warning, click **Yes** to delete the In-Place Hold.</span></span> 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a><span data-ttu-id="ee5e8-164">使用 Exchange Online PowerShell 刪除就地保留</span><span class="sxs-lookup"><span data-stu-id="ee5e8-164">Use Exchange Online PowerShell to delete an In-Place Hold</span></span>

1. <span data-ttu-id="ee5e8-p115">建立包含您想要刪除的就地保留屬性的變數。使用就地保留 GUID 所取得的[步驟 1： 識別非使用中的信箱上保留](delete-an-inactive-mailbox.md#step1)。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-p115">Create a variable that contains the properties of the In-Place Hold that you want to delete. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](delete-an-inactive-mailbox.md#step1).</span></span>
    
```
  $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
```

2. <span data-ttu-id="ee5e8-167">停用設為 「 就地保留的保留。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-167">Disable the hold on the In-Place Hold.</span></span>
    
```
  Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
```

3. <span data-ttu-id="ee5e8-168">刪除就地保留。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-168">Delete the In-Place Hold.</span></span>
    
```
  Remove-MailboxSearch $InPlaceHold.Name
```

#### <a name="use-the-eac-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="ee5e8-169">使用 EAC 來移除不在作用中的信箱就地保留</span><span class="sxs-lookup"><span data-stu-id="ee5e8-169">Use the EAC to remove an inactive mailbox from an In-Place Hold</span></span>

1. <span data-ttu-id="ee5e8-p116">如果您知道名稱不在作用中信箱處於就地保留，您可以前往下一個步驟。否則請執行下列命令以取得信箱處於就地保留的名稱。使用就地保留 GUID 所取得的[步驟 1： 識別非使用中的信箱上保留](delete-an-inactive-mailbox.md#step1)。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-p116">If you know the name of the In-Place Hold that's placed on the inactive mailbox, you can go to the next step. Otherwise, run the following command to get the name of the In-Place Hold placed on the mailbox. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](delete-an-inactive-mailbox.md#step1).</span></span>
    
```
  Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
```

2. <span data-ttu-id="ee5e8-173">在 EAC 中，移至 [**規範管理** \> **就地 eDiscovery&amp;保留**。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-173">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="ee5e8-174">選取 [非使用中信箱處於就地保留，然後按一下 [**編輯**![編輯圖示](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-174">Select the In-Place Hold that is placed on the inactive mailbox, and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="ee5e8-175">在**就地 eDiscovery&amp;保留**屬性] 頁面上，按一下 [**來源**]。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-175">On the **In-Place eDiscovery &amp; Hold** properties page, click **Sources**.</span></span>
    
5. <span data-ttu-id="ee5e8-176">在來源信箱清單中，按一下您要移除的非使用中信箱的名稱] 和 [**移除**![移除圖示](media/adf01106-cc79-475c-8673-065371c1897b.gif)。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-176">In the list of source mailboxes, click the name of the inactive mailbox that you want to remove, and then click **Remove**![Remove icon](media/adf01106-cc79-475c-8673-065371c1897b.gif).</span></span>
    
6. <span data-ttu-id="ee5e8-p117">按一下 [**儲存**] 以儲存變更。會顯示訊息表示作業已順利完成。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-p117">Click **Save** to save the change. A message is displayed saying the operation was successfully completed.</span></span> 
    
7. <span data-ttu-id="ee5e8-179">重複步驟 1 到 6，以移除處於非使用中信箱其他就地保留。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-179">Repeat steps 1 through 6 to remove other In-Place Holds placed on the inactive mailbox.</span></span>
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="ee5e8-180">利用 Exchange Online PowerShell 移除不在作用中的信箱就地保留</span><span class="sxs-lookup"><span data-stu-id="ee5e8-180">Use Exchange Online PowerShell to remove an inactive mailbox from an In-Place Hold</span></span>

<span data-ttu-id="ee5e8-p118">如果在 In-place Hold 包含大量的來源信箱，很可能不在作用中的信箱將不會列在 EAC 中的 [**來源**] 頁面上。最多個 3000 信箱會顯示在 [**來源**] 頁面編輯就地保留時。如果非使用中的信箱未列在 [**來源**] 頁面上，您可以使用 Exchange Online PowerShell 移除就地保留。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-p118">If the In-Place Hold contains a large number of source mailboxes, it's possible the inactive mailbox won't be listed on the **Sources** page in the EAC. Up to 3,000 mailboxes are displayed on the **Sources** page when you edit an In-Place Hold. If an inactive mailbox isn't listed on the **Sources** page, you can use Exchange Online PowerShell to remove it from the In-Place Hold.</span></span> 
  
1. <span data-ttu-id="ee5e8-p119">建立包含的非使用中信箱處於就地保留屬性的變數。使用就地保留 GUID 所取得的[步驟 1： 識別非使用中的信箱上保留](delete-an-inactive-mailbox.md#step1)。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-p119">Create a variable that contains the properties of the In-Place Hold placed on the inactive mailbox. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](delete-an-inactive-mailbox.md#step1).</span></span>
    
```
  $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
```

2. <span data-ttu-id="ee5e8-186">確認非使用中的信箱已列出為來源信箱的就地保留。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-186">Verify that the inactive mailbox is listed as a source mailbox for the In-Place Hold.</span></span> 
    
```
  $InPlaceHold.Sources
```

   <span data-ttu-id="ee5e8-p120">**附註：** 就地保留的*來源*屬性及其*LegacyExchangeDN*屬性來識別來源信箱。因為這個屬性會唯一識別非使用中的信箱，使用就地保留從*來源*屬性可協助防止移除錯誤的信箱。這也有助於避免發生的問題如果兩個信箱有相同的別名或 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-p120">**Note:** The *Sources* property of the In-Place Hold identifies the source mailboxes by their *LegacyExchangeDN* properties. Because this property uniquely identifies inactive mailboxes, using the *Sources* property from the In-Place Hold helps prevent removing the wrong mailbox. This also helps to avoid issues if two mailboxes have the same alias or SMTP address.</span></span> 
   
3. <span data-ttu-id="ee5e8-p121">移除在變數中的來源信箱清單中的非使用中的信箱。請務必使用前一個步驟中的命令會傳回非使用中信箱的**LegacyExchangeDN** 。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-p121">Remove the inactive mailbox from the list of source mailboxes in the variable. Be sure to use the **LegacyExchangeDN** of the inactive mailbox that's returned by the command in the previous step.</span></span> 
    
```
  $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
```

    For example, the following command removes the inactive mailbox for Pilar Pinilla.
    
  ```
  $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
  ```

4. <span data-ttu-id="ee5e8-192">確認非使用中的信箱已從變數中的來源信箱的清單。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-192">Verify that the inactive mailbox is removed from the list of source mailboxes in the variable.</span></span>
    
```
  $InPlaceHold.Sources
```

5. <span data-ttu-id="ee5e8-193">修改與更新的來源信箱清單不包括非使用中的信箱就地保留。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-193">Modify the In-Place Hold with the updated list of source mailboxes, which doesn't include the inactive mailbox.</span></span>
    
```
  Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
```

6. <span data-ttu-id="ee5e8-194">確認為就地保留非使用中的信箱已從來源信箱清單中移除。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-194">Verify that the inactive mailbox is removed from the list of source mailboxes for the In-Place Hold.</span></span>
    
```
  Get-MailboxSearch $InPlaceHold.Name | FL Sources
```

## <a name="more-information"></a><span data-ttu-id="ee5e8-195">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="ee5e8-195">More information</span></span>

- <span data-ttu-id="ee5e8-p122">**非使用中的信箱是一種虛刪除信箱。** 在 Exchange Online 虛刪除信箱是已遭刪除，但在特定的保留期間內可復原的信箱。Exchange Online 中的虛刪除信箱保留期間是 30 天。這表示信箱的可復原的正在虛刪除 30 天內。30 天後虛刪除信箱標記為永久刪除和無法復原。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-p122">**An inactive mailbox is a type of soft-deleted mailbox.** In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period. The soft-deleted mailbox retention period in Exchange Online is 30 days. This means that the mailbox can be recovered within 30 days of being soft-deleted. After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered.</span></span> 
    
- <span data-ttu-id="ee5e8-p123">**移除不在作用中的信箱上保留之後會發生什麼事？** 信箱會視為其他虛刪除信箱和 30 天虛刪除信箱保留期間到期後目標記為要永久刪除。此保留期間啟動時之信箱的第一次進行非使用中的日期。此日期就是所謂的虛刪除的日期，這是對應的 Office 365 使用者帳戶已遭刪除或 Exchange Online 信箱刪除使用**Remove-mailbox**指令程式時的日期。虛刪除日期不移除保留的日期。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-p123">**What happens after you remove the hold on an inactive mailbox?** The mailbox is treated like other soft-deleted mailboxes and is marked for permanent deletion after the 30-day soft-deleted mailbox retention period expires. This retention period starts on the date when the mailbox was first made inactive. This date is known as the soft-deleted date, which is the date the corresponding Office 365 user account was deleted or when the Exchange Online mailbox was deleted with the **Remove-Mailbox** cmdlet. The soft-deleted date isn't the date on which you remove the hold.</span></span> 
    
- <span data-ttu-id="ee5e8-p124">**立即之後移除保留永久刪除非作用中信箱吗？** 如果不在作用中信箱的虛刪除日期是超過 30 天，一旦移除保留，將不會永久刪除信箱。信箱會標示為永久刪除和刪除其已處理的下一次。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-p124">**Is an inactive mailbox permanently deleted immediately after the hold is removed?** If the soft-deleted date for an inactive mailbox is older than 30 days, the mailbox won't be permanently deleted as soon as you remove the hold. The mailbox will be marked for permanent deletion and is deleted the next time it's processed.</span></span> 
    
- <span data-ttu-id="ee5e8-p125">**虛刪除信箱保留期間如何影響不在作用中的信箱？** 如果不在作用中信箱的虛刪除日期是超過 30 天保留已移除的日期之前，信箱被標示為永久刪除。但如果不在作用中的信箱已在過去 30 天內虛刪除日期及移除保留，您可以使用復原信箱直到虛刪除信箱保留期間到期。如需詳細資訊，請參閱[刪除或還原使用者信箱在 Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835)。虛刪除信箱保留期間到期後，您有遵循來復原不在作用中信箱的程序。如需詳細資訊，請參閱[Office 365 中的不在作用中信箱復原](recover-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-p125">**How does the soft-deleted mailbox retention period affect inactive mailboxes?** If the soft-deleted date for an inactive mailbox is more than 30 days before the date the hold was removed, the mailbox is marked for permanent deletion. But if an inactive mailbox has a soft-deleted date within the last 30 days and you remove the hold, you can recover the mailbox up until the soft-deleted mailbox retention period expires. For details, see [Delete or restore user mailboxes in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835). After the soft-deleted mailbox retention period expires, you have follow the procedures for recovering an inactive mailbox. For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="ee5e8-p126">**如何顯示不在作用中信箱的相關資訊之後移除保留？** 撤除和非使用中信箱會回到虛刪除信箱後，它將不會傳回使用*InactiveMailboxOnly*參數與**Get-mailbox**指令程式。但是您可以使用**Get-mailbox SoftDeletedMailbox**命令來顯示信箱的相關資訊。例如：</span><span class="sxs-lookup"><span data-stu-id="ee5e8-p126">**How do you display information about an inactive mailbox after the hold is removed?** After a hold is removed and the inactive mailbox is reverted back to a soft-deleted mailbox, it won't be returned by using the  *InactiveMailboxOnly*  parameter with the **Get-Mailbox** cmdlet. But you can display information about the mailbox by using the **Get-Mailbox -SoftDeletedMailbox** command. For example:</span></span> 
    
```
  Get-Mailbox -SoftDeletedMailbox -Identity pilarp | FL Name,Identity,LitigationHoldEnabled,In
  Placeholds,WhenSoftDeleted,IsInactiveMailbox
  Name                   : pilarp
  Identity               : Soft Deleted Objects\pilarp
  LitigationHoldEnabled  : False
  InPlaceHolds           : {}
  WhenSoftDeleted        : 10/30/2014 1:19:04 AM
  IsInactiveMailbox      : False
```
  
<span data-ttu-id="ee5e8-p127">在上述範例中， *WhenSoftDeleted*屬性識別的虛刪除日期，這在此範例中是 2014 年 10 月 30 日。如果此虛刪除信箱先前非作用中的信箱移除保留的程式，它將會永久刪除的 30 天後*WhenSoftDeleted*屬性的值。在此例中 2014 年 11 月 30 日之後永久刪除信箱。</span><span class="sxs-lookup"><span data-stu-id="ee5e8-p127">In the above example, the *WhenSoftDeleted* property identifies the soft-deleted date, which in this example is October 30, 2014. If this soft-deleted mailbox was previously an inactive mailbox for which the hold was removed, it will be permanently deleted 30 days after the value of the *WhenSoftDeleted* property. In this case, the mailbox is permanently deleted after November 30, 2014.</span></span>

