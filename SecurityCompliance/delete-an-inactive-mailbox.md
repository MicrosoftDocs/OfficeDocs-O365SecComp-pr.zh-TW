---
title: 刪除 Office 365 中的非使用中信箱
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
description: 當您不再需要保留的 Office 365 不在作用中信箱內容時，您可以永久刪除非使用中信箱移除保留。 之後移除保留，請在作用中信箱標示為刪除，並永久刪除之後就會處理。
ms.openlocfilehash: f1aa29b0e40d02e4b6450202c0b2a34ae3075677
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32257104"
---
# <a name="delete-an-inactive-mailbox-in-office-365"></a><span data-ttu-id="f8045-104">刪除 Office 365 中的非使用中信箱</span><span class="sxs-lookup"><span data-stu-id="f8045-104">Delete an inactive mailbox in Office 365</span></span>

<span data-ttu-id="f8045-105">在前任員工離開您的組織之後，可透過非使用中信箱來保留其電子郵件。</span><span class="sxs-lookup"><span data-stu-id="f8045-105">An inactive mailbox is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="f8045-106">當您不再需要保留非使用中信箱的內容時，您可以永久刪除非使用中信箱移除保留。</span><span class="sxs-lookup"><span data-stu-id="f8045-106">When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold.</span></span> <span data-ttu-id="f8045-107">此外，很可能多項保留可能處於非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="f8045-107">Also, it's possible that multiple holds might be placed on an inactive mailbox.</span></span> <span data-ttu-id="f8045-108">例如，非使用中信箱也可能會放置訴訟暫止，並在一或多個就地保留。</span><span class="sxs-lookup"><span data-stu-id="f8045-108">For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds.</span></span> <span data-ttu-id="f8045-109">此外，Office 365 保留原則 （在 Office 365 或 Microsoft 365 安全性與合規性中心] 中建立） 可能會套用至非使用中信箱。</span><span class="sxs-lookup"><span data-stu-id="f8045-109">Additionally, an Office 365 retention policy (created in the security and compliance center in Office 365 or Microsoft 365) might be applied to the inactive mailbox.</span></span> <span data-ttu-id="f8045-110">您必須將它刪除非使用中信箱中移除所有的保留和 Office 365 保留原則。</span><span class="sxs-lookup"><span data-stu-id="f8045-110">You have to remove all holds and Office 365 retention policies from an inactive mailbox to delete it.</span></span> <span data-ttu-id="f8045-111">保留和保留原則中移除之後，在作用中信箱標記為待刪除，並永久刪除之後就會處理。</span><span class="sxs-lookup"><span data-stu-id="f8045-111">After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f8045-p103">我們已將 2017 年 7 月 1 日的期限延後，以建立新的「就地保留」來建立非使用中的信箱。但到今年年底或明年年初，您將無法在 Exchange Online 中建立新的「就地保留」。到時，只有「訴訟資料暫留」和 Office 365 保留原則可以用來建立非使用中的信箱。不過，仍會支援「就地保留」上現有的非使用中信箱，並且您可以繼續管理非使用信箱上的「就地保留」。這包括變更「就地保留」期間，以及透過移除「就地保留」永久刪除非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="f8045-p103">We've postponed the July 1, 2017 deadline for creating new In-Place Holds to make a mailbox inactive. But later this year or early next year, you won't be able to create new In-Place Holds in Exchange Online. At that time, only Litigation Holds and Office 365 retention policies can be used to create an inactive mailbox. However, existing inactive mailboxes that are on In-Place Hold will still be supported, and you can continue to manage the In-Place Holds on inactive mailboxes. This includes changing the duration of an In-Place Hold and permanently deleting an inactive mailbox by removing the In-Place Hold.</span></span> 
  
<span data-ttu-id="f8045-117">請參閱說明從非使用中信箱移除保留後，會發生什麼情況[的詳細資訊](#more-information)一節。</span><span class="sxs-lookup"><span data-stu-id="f8045-117">See the [More information](#more-information) section for a description of what happens after holds are removed from an inactive mailbox.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="f8045-118">開始之前</span><span class="sxs-lookup"><span data-stu-id="f8045-118">Before you begin</span></span>

- <span data-ttu-id="f8045-119">您必須使用 Exchange Online PowerShell 來從非使用中的信箱中移除 [訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="f8045-119">You have to use Exchange Online PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="f8045-120">您無法使用 Exchange 系統管理中心 (EAC)。</span><span class="sxs-lookup"><span data-stu-id="f8045-120">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="f8045-121">如需逐步指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。</span><span class="sxs-lookup"><span data-stu-id="f8045-121">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span></span> <span data-ttu-id="f8045-122">您可以使用 Exchange Online PowerShell 或 EAC 來移除從非使用中信箱的 [就地保留。</span><span class="sxs-lookup"><span data-stu-id="f8045-122">You can use Exchange Online PowerShell or the EAC to remove an In-Place Hold from an inactive mailbox.</span></span> 
    
- <span data-ttu-id="f8045-123">移除保留與刪除非使用中信箱之前，您可以不在作用中信箱的內容複製到另一個信箱。</span><span class="sxs-lookup"><span data-stu-id="f8045-123">You can copy the contents of an inactive mailbox to another mailbox before you remove the hold and delete an inactive mailbox.</span></span> <span data-ttu-id="f8045-124">如需詳細資訊，請參閱 <<c0>還原 Office 365 中的非使用中信箱。</span><span class="sxs-lookup"><span data-stu-id="f8045-124">For details, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="f8045-125">如果您從非使用中信箱移除保留或 Office 365 保留原則和信箱的虛刪除信箱保留期間已過期，將永久刪除信箱。</span><span class="sxs-lookup"><span data-stu-id="f8045-125">If you remove the hold or Office 365 retention policy from an inactive mailbox and the soft-deleted mailbox retention period for the mailbox has expired, the mailbox will be permanently deleted.</span></span> <span data-ttu-id="f8045-126">會在刪除之後，便無法復原。</span><span class="sxs-lookup"><span data-stu-id="f8045-126">After it's deleted, it can't be recovered.</span></span> <span data-ttu-id="f8045-127">移除保留之前，先確定您不再需要的信箱中的內容。</span><span class="sxs-lookup"><span data-stu-id="f8045-127">Before you remove the hold, be sure that you no longer need the contents in the mailbox.</span></span> <span data-ttu-id="f8045-128">如果您想要重新啟用非使用中的信箱，您就可以進行復原。</span><span class="sxs-lookup"><span data-stu-id="f8045-128">If you want to re-activate an inactive mailbox, you can recover it.</span></span> <span data-ttu-id="f8045-129">如需詳細資訊，請參閱[復原非使用中信箱 Office 365 中](recover-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="f8045-129">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="f8045-130">如需非使用中信箱的詳細資訊，請參閱 <<c0>在 Office 365 中的非使用中信箱。</span><span class="sxs-lookup"><span data-stu-id="f8045-130">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="f8045-131">步驟 1： 識別非使用中信箱上保留</span><span class="sxs-lookup"><span data-stu-id="f8045-131">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="f8045-132">如先前所述，訴訟暫止，原有範圍暫止，或 Office 365 保留原則可能會處於非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="f8045-132">As previously stated, a Litigation Hold, In-Place Hold, or Office 365 retention policy might be placed on an inactive mailbox.</span></span> <span data-ttu-id="f8045-133">第一個步驟是識別非使用中信箱上的保留。</span><span class="sxs-lookup"><span data-stu-id="f8045-133">The first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="f8045-134">執行下列命令，以顯示貴組織中的所有非使用中信箱的保留資訊。</span><span class="sxs-lookup"><span data-stu-id="f8045-134">Run the following command to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

<span data-ttu-id="f8045-135">**LitigationHoldEnabled**屬性的**則為 True**的值會指出作用中的信箱處於訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="f8045-135">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold.</span></span> <span data-ttu-id="f8045-136">如果在原有範圍暫止處於非使用中的信箱，保留的 GUID 被顯示為**InPlaceHolds**屬性的值。</span><span class="sxs-lookup"><span data-stu-id="f8045-136">If an In-Place Hold is placed on an inactive mailbox, the GUID for the hold is displayed as the value for the **InPlaceHolds** property.</span></span> <span data-ttu-id="f8045-137">例如，兩個非使用中信箱的下列結果顯示的訴訟暫止狀態會置於 Ann Beebe 和兩個就地保留放在 Pilar Pinilla。</span><span class="sxs-lookup"><span data-stu-id="f8045-137">For example, the following results for two inactive mailboxes show that a Litigation Hold is placed on Ann Beebe and that two In-Place Holds are placed on Pilar Pinilla.</span></span> 
  
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
> <span data-ttu-id="f8045-138">如果許多為 「 就地保留處於非使用中的信箱，將會顯示不是所有的就地保留 Guid。</span><span class="sxs-lookup"><span data-stu-id="f8045-138">If a lot of In-Place Holds are placed on an inactive mailbox, not all of the In-Place Hold GUIDs will be displayed.</span></span> <span data-ttu-id="f8045-139">您可以執行下列命令，以顯示所有為 「 就地保留的 Guid:`Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span><span class="sxs-lookup"><span data-stu-id="f8045-139">You can run the following command to display all the In-Place Hold GUIDs:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span></span>
  
## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a><span data-ttu-id="f8045-140">步驟 2： 從非使用中的信箱移除保留</span><span class="sxs-lookup"><span data-stu-id="f8045-140">Step 2: Remove a hold from an inactive mailbox</span></span>

<span data-ttu-id="f8045-141">識別何種類型的保留處於非使用中信箱之後 （以及是否有多項保留） 下, 一步是要移除的信箱上保留。</span><span class="sxs-lookup"><span data-stu-id="f8045-141">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to remove the holds on the mailbox.</span></span> <span data-ttu-id="f8045-142">如先前所述，您必須移除所有保留]，以永久刪除非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="f8045-142">As previously stated, you have to remove all holds to permanently delete an inactive mailbox.</span></span> 
  
### <a name="remove-a-litigation-hold"></a><span data-ttu-id="f8045-143">移除訴訟資料暫留</span><span class="sxs-lookup"><span data-stu-id="f8045-143">Remove a Litigation Hold</span></span>

<span data-ttu-id="f8045-144">如先前所述，您必須使用 Windows PowerShell 來從非使用中的信箱中移除 [訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="f8045-144">As previously stated, you have to use Windows PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="f8045-145">您無法使用 EAC。</span><span class="sxs-lookup"><span data-stu-id="f8045-145">You can't use the EAC.</span></span> <span data-ttu-id="f8045-146">執行下列命令，以移除訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="f8045-146">Run the following command to remove a Litigation Hold.</span></span>
  
```
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> <span data-ttu-id="f8045-147">若要識別非使用中信箱的最佳方式是使用其辨別名稱或 Exchange GUID 值。</span><span class="sxs-lookup"><span data-stu-id="f8045-147">The best way to identify an inactive mailbox is by using its Distinguished Name or Exchange GUID value.</span></span> <span data-ttu-id="f8045-148">使用下列值之一，有助於防止不小心指定錯誤的信箱。</span><span class="sxs-lookup"><span data-stu-id="f8045-148">Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="remove-in-place-holds"></a><span data-ttu-id="f8045-149">移除就地保留</span><span class="sxs-lookup"><span data-stu-id="f8045-149">Remove In-Place Holds</span></span>

 <span data-ttu-id="f8045-150">有兩種方式可從非使用中的信箱中移除 [就地保留：</span><span class="sxs-lookup"><span data-stu-id="f8045-150">There are two ways to remove an In-Place Hold from an inactive mailbox:</span></span> 
  
- <span data-ttu-id="f8045-151">**刪除就地保留的物件**如果您想要永久刪除非使用中信箱是在原有範圍暫止的唯一來源信箱，您可以只刪除就地保留物件。</span><span class="sxs-lookup"><span data-stu-id="f8045-151">**Delete the In-Place Hold object** If the inactive mailbox that you want to permanently delete is the only source mailbox for an In-Place Hold, you can just delete the In-Place Hold object.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="f8045-152">您必須停用保留後，才能刪除就地保留的 object。</span><span class="sxs-lookup"><span data-stu-id="f8045-152">You have to disable the hold before you can delete an In-Place Hold object.</span></span> <span data-ttu-id="f8045-153">如果您嘗試刪除就地保留物件已啟用保留時，您會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="f8045-153">If you try to delete an In-Place Hold object that has the hold enabled, you'll receive an error message.</span></span> 
  
- <span data-ttu-id="f8045-154">**移除為來源信箱的就地保留的非使用中信箱**如果您想要保留其他來源信箱的就地保留，您可以移除不在作用中信箱從來源信箱的清單，並保留在原有範圍暫止物件。</span><span class="sxs-lookup"><span data-stu-id="f8045-154">**Remove the inactive mailbox as a source mailbox of an In-Place Hold** If you want to retain other source mailboxes for an In-Place Hold, you can remove the inactive mailbox from the list of source mailboxes and keep the In-Place Hold object.</span></span> 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a><span data-ttu-id="f8045-155">使用 EAC 來刪除就地保留</span><span class="sxs-lookup"><span data-stu-id="f8045-155">Use the EAC to delete an In-Place Hold</span></span>

1. <span data-ttu-id="f8045-156">如果您知道想要刪除就地保留的名稱，您可以移至下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="f8045-156">If you know the name of the In-Place Hold that you want to delete, you can go to the next step.</span></span> <span data-ttu-id="f8045-157">否則，執行下列命令，以取得您想要永久刪除非使用中信箱處於就地保留的名稱。</span><span class="sxs-lookup"><span data-stu-id="f8045-157">Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox that you want to permanently delete.</span></span> <span data-ttu-id="f8045-158">使用就地保留 GUID 中得到的[步驟 1： 識別非使用中信箱上的保留](#step-1-identify-the-holds-on-an-inactive-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="f8045-158">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
```
  Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
```

2. <span data-ttu-id="f8045-159">在 EAC 中，移至 [**規範管理** \> **就地 eDiscovery&amp;保留**。</span><span class="sxs-lookup"><span data-stu-id="f8045-159">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="f8045-160">選取您要刪除就地保留，然後按一下 [**編輯**![編輯圖示](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。</span><span class="sxs-lookup"><span data-stu-id="f8045-160">Select the In-Place Hold you want to delete, and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="f8045-161">在**就地 eDiscovery&amp;保留**屬性] 頁面上，按一下 [**原有範圍暫止**、 取消核取 [**將符合搜尋查詢的所選信箱上內容保留**] 方塊中，，然後按一下 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="f8045-161">On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**, uncheck the **Place content matching the search query in selected mailboxes on hold** box, and then click **Save**.</span></span>
    
5. <span data-ttu-id="f8045-162">在**就地 eDiscovery&amp;保留**] 頁面上，選擇一次，為 「 就地保留，然後按一下 [**刪除**![刪除圖示](media/87565fbb-5147-4f22-9ed7-1c18ce664392.png)。</span><span class="sxs-lookup"><span data-stu-id="f8045-162">On the **In-Place eDiscovery &amp; Hold** page, select the In-Place Hold again, and then click **Delete**![Delete icon](media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>
    
6. <span data-ttu-id="f8045-163">在警告中，按一下 [ **]** 以刪除 「 就地保留 」 狀態。</span><span class="sxs-lookup"><span data-stu-id="f8045-163">On the warning, click **Yes** to delete the In-Place Hold.</span></span> 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a><span data-ttu-id="f8045-164">使用 Exchange Online PowerShell 來刪除就地保留</span><span class="sxs-lookup"><span data-stu-id="f8045-164">Use Exchange Online PowerShell to delete an In-Place Hold</span></span>

1. <span data-ttu-id="f8045-165">建立包含您想要刪除就地保留的屬性的變數。</span><span class="sxs-lookup"><span data-stu-id="f8045-165">Create a variable that contains the properties of the In-Place Hold that you want to delete.</span></span> <span data-ttu-id="f8045-166">使用就地保留 GUID 中得到的[步驟 1： 識別非使用中信箱上的保留](#step-1-identify-the-holds-on-an-inactive-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="f8045-166">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
```
  $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
```

2. <span data-ttu-id="f8045-167">停用保留在 「 就地保留 」 狀態。</span><span class="sxs-lookup"><span data-stu-id="f8045-167">Disable the hold on the In-Place Hold.</span></span>
    
```
  Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
```

3. <span data-ttu-id="f8045-168">刪除就地保留。</span><span class="sxs-lookup"><span data-stu-id="f8045-168">Delete the In-Place Hold.</span></span>
    
```
  Remove-MailboxSearch $InPlaceHold.Name
```

#### <a name="use-the-eac-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="f8045-169">使用 EAC 來移除非使用中的信箱就地保留</span><span class="sxs-lookup"><span data-stu-id="f8045-169">Use the EAC to remove an inactive mailbox from an In-Place Hold</span></span>

1. <span data-ttu-id="f8045-170">如果您知道處於非使用中的信箱就地保留的名稱，您可以移至下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="f8045-170">If you know the name of the In-Place Hold that's placed on the inactive mailbox, you can go to the next step.</span></span> <span data-ttu-id="f8045-171">否則，執行下列命令，以取得在原有範圍暫止放置在信箱上的名稱。</span><span class="sxs-lookup"><span data-stu-id="f8045-171">Otherwise, run the following command to get the name of the In-Place Hold placed on the mailbox.</span></span> <span data-ttu-id="f8045-172">使用就地保留 GUID 中得到的[步驟 1： 識別非使用中信箱上的保留](#step-1-identify-the-holds-on-an-inactive-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="f8045-172">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
```
  Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
```

2. <span data-ttu-id="f8045-173">在 EAC 中，移至 [**規範管理** \> **就地 eDiscovery&amp;保留**。</span><span class="sxs-lookup"><span data-stu-id="f8045-173">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="f8045-174">選取處於非使用中信箱中，就地保留，然後按一下 [**編輯**![編輯圖示](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。</span><span class="sxs-lookup"><span data-stu-id="f8045-174">Select the In-Place Hold that is placed on the inactive mailbox, and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="f8045-175">在**就地 eDiscovery&amp;保留**屬性] 頁面上，按一下 [**來源**]。</span><span class="sxs-lookup"><span data-stu-id="f8045-175">On the **In-Place eDiscovery &amp; Hold** properties page, click **Sources**.</span></span>
    
5. <span data-ttu-id="f8045-176">在來源信箱的清單中，按一下您想要移除，非使用中信箱的名稱，然後按一下 [**移除**![移除圖示](media/adf01106-cc79-475c-8673-065371c1897b.gif)。</span><span class="sxs-lookup"><span data-stu-id="f8045-176">In the list of source mailboxes, click the name of the inactive mailbox that you want to remove, and then click **Remove**![Remove icon](media/adf01106-cc79-475c-8673-065371c1897b.gif).</span></span>
    
6. <span data-ttu-id="f8045-177">按一下 [**儲存**] 以儲存變更。</span><span class="sxs-lookup"><span data-stu-id="f8045-177">Click **Save** to save the change.</span></span> <span data-ttu-id="f8045-178">會顯示一則訊息，指出作業已順利完成。</span><span class="sxs-lookup"><span data-stu-id="f8045-178">A message is displayed saying the operation was successfully completed.</span></span> 
    
7. <span data-ttu-id="f8045-179">重複步驟 1 至 6，放置在非使用中信箱上其他就地保留中移除。</span><span class="sxs-lookup"><span data-stu-id="f8045-179">Repeat steps 1 through 6 to remove other In-Place Holds placed on the inactive mailbox.</span></span>
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="f8045-180">若要移除的非使用中的信箱就地保留使用 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="f8045-180">Use Exchange Online PowerShell to remove an inactive mailbox from an In-Place Hold</span></span>

<span data-ttu-id="f8045-181">如果 「 就地保留 」 狀態包含大量的來源信箱，則可能不在作用中信箱不會列出在 EAC 中的 [**來源**] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="f8045-181">If the In-Place Hold contains a large number of source mailboxes, it's possible the inactive mailbox won't be listed on the **Sources** page in the EAC.</span></span> <span data-ttu-id="f8045-182">顯示最多 3000 信箱會在 [**來源**] 頁面上編輯在原有範圍暫止時。</span><span class="sxs-lookup"><span data-stu-id="f8045-182">Up to 3,000 mailboxes are displayed on the **Sources** page when you edit an In-Place Hold.</span></span> <span data-ttu-id="f8045-183">如果不在作用中信箱未列在 [**來源**] 頁面上，您可以使用 Exchange Online PowerShell 移除 「 就地保留 」 狀態。</span><span class="sxs-lookup"><span data-stu-id="f8045-183">If an inactive mailbox isn't listed on the **Sources** page, you can use Exchange Online PowerShell to remove it from the In-Place Hold.</span></span> 
  
1. <span data-ttu-id="f8045-184">建立包含在原有範圍暫止處於非使用中信箱的屬性的變數。</span><span class="sxs-lookup"><span data-stu-id="f8045-184">Create a variable that contains the properties of the In-Place Hold placed on the inactive mailbox.</span></span> <span data-ttu-id="f8045-185">使用就地保留 GUID 中得到的[步驟 1： 識別非使用中信箱上的保留](#step-1-identify-the-holds-on-an-inactive-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="f8045-185">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
```
  $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
```

2. <span data-ttu-id="f8045-186">確認非使用中信箱列出的來源信箱的 「 就地保留 」 狀態。</span><span class="sxs-lookup"><span data-stu-id="f8045-186">Verify that the inactive mailbox is listed as a source mailbox for the In-Place Hold.</span></span> 
    
```
  $InPlaceHold.Sources
```

   <span data-ttu-id="f8045-187">**附註：**「 就地保留 」 狀態的*來源*屬性會識別來源信箱由其*LegacyExchangeDN*屬性。</span><span class="sxs-lookup"><span data-stu-id="f8045-187">**Note:** The *Sources* property of the In-Place Hold identifies the source mailboxes by their *LegacyExchangeDN* properties.</span></span> <span data-ttu-id="f8045-188">因為這個屬性可唯一識別非使用中信箱，使用 [*來源*] 屬性，從 「 就地保留 」 狀態有助於防止移除錯誤的信箱。</span><span class="sxs-lookup"><span data-stu-id="f8045-188">Because this property uniquely identifies inactive mailboxes, using the *Sources* property from the In-Place Hold helps prevent removing the wrong mailbox.</span></span> <span data-ttu-id="f8045-189">這也有助於避免發生問題，如果這兩個信箱有相同的別名或 SMTP 位址。</span><span class="sxs-lookup"><span data-stu-id="f8045-189">This also helps to avoid issues if two mailboxes have the same alias or SMTP address.</span></span> 
   
3. <span data-ttu-id="f8045-190">非使用中信箱移除在變數中的來源信箱的清單。</span><span class="sxs-lookup"><span data-stu-id="f8045-190">Remove the inactive mailbox from the list of source mailboxes in the variable.</span></span> <span data-ttu-id="f8045-191">請務必使用前一個步驟中的命令會傳回非使用中信箱的**LegacyExchangeDN** 。</span><span class="sxs-lookup"><span data-stu-id="f8045-191">Be sure to use the **LegacyExchangeDN** of the inactive mailbox that's returned by the command in the previous step.</span></span> 
    
```
  $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
```

    For example, the following command removes the inactive mailbox for Pilar Pinilla.
    
  ```
  $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
  ```

4. <span data-ttu-id="f8045-192">確認非使用中的信箱會移除在變數中的來源信箱的清單。</span><span class="sxs-lookup"><span data-stu-id="f8045-192">Verify that the inactive mailbox is removed from the list of source mailboxes in the variable.</span></span>
    
```
  $InPlaceHold.Sources
```

5. <span data-ttu-id="f8045-193">修改與更新來源信箱的清單，其中不包含作用中的信箱就地保留。</span><span class="sxs-lookup"><span data-stu-id="f8045-193">Modify the In-Place Hold with the updated list of source mailboxes, which doesn't include the inactive mailbox.</span></span>
    
```
  Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
```

6. <span data-ttu-id="f8045-194">確認非使用中的信箱從來源信箱的清單移除的 「 就地保留 」 狀態。</span><span class="sxs-lookup"><span data-stu-id="f8045-194">Verify that the inactive mailbox is removed from the list of source mailboxes for the In-Place Hold.</span></span>
    
```
  Get-MailboxSearch $InPlaceHold.Name | FL Sources
```

## <a name="more-information"></a><span data-ttu-id="f8045-195">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="f8045-195">More information</span></span>

- <span data-ttu-id="f8045-196">**非使用中信箱是信箱的一種虛刪除。**</span><span class="sxs-lookup"><span data-stu-id="f8045-196">**An inactive mailbox is a type of soft-deleted mailbox.**</span></span> <span data-ttu-id="f8045-197">在 Exchange Online 中，將虛刪除的信箱會是已刪除，但可以在特定的保留期間內可復原的信箱。</span><span class="sxs-lookup"><span data-stu-id="f8045-197">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period.</span></span> <span data-ttu-id="f8045-198">Exchange Online 中的虛刪除信箱保留期間是 30 天。</span><span class="sxs-lookup"><span data-stu-id="f8045-198">The soft-deleted mailbox retention period in Exchange Online is 30 days.</span></span> <span data-ttu-id="f8045-199">這表示被虛刪除的 30 天內，即可復原信箱。</span><span class="sxs-lookup"><span data-stu-id="f8045-199">This means that the mailbox can be recovered within 30 days of being soft-deleted.</span></span> <span data-ttu-id="f8045-200">30 天後，虛刪除的信箱會標示為永久刪除，並且無法復原。</span><span class="sxs-lookup"><span data-stu-id="f8045-200">After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered.</span></span> 
    
- <span data-ttu-id="f8045-201">**移除位於非使用中信箱保留後，會發生什麼事？**</span><span class="sxs-lookup"><span data-stu-id="f8045-201">**What happens after you remove the hold on an inactive mailbox?**</span></span> <span data-ttu-id="f8045-202">信箱就會被視為其他虛刪除信箱，並在 30 天虛刪除信箱保留期間到期後，會標示為永久刪除。</span><span class="sxs-lookup"><span data-stu-id="f8045-202">The mailbox is treated like other soft-deleted mailboxes and is marked for permanent deletion after the 30-day soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="f8045-203">當信箱已第一次進行非使用中的日期上，啟動此保留期間。</span><span class="sxs-lookup"><span data-stu-id="f8045-203">This retention period starts on the date when the mailbox was first made inactive.</span></span> <span data-ttu-id="f8045-204">此日期就是所謂的虛刪除的日期，這是已刪除對應的 Office 365 使用者帳戶，或使用**Remove-mailbox** cmdlet 刪除 Exchange Online 信箱已時的日期。</span><span class="sxs-lookup"><span data-stu-id="f8045-204">This date is known as the soft-deleted date, which is the date the corresponding Office 365 user account was deleted or when the Exchange Online mailbox was deleted with the **Remove-Mailbox** cmdlet.</span></span> <span data-ttu-id="f8045-205">虛刪除日期不移除保留的日期。</span><span class="sxs-lookup"><span data-stu-id="f8045-205">The soft-deleted date isn't the date on which you remove the hold.</span></span> 
    
- <span data-ttu-id="f8045-206">**非使用中信箱永久刪除之後移除保留嗎？**</span><span class="sxs-lookup"><span data-stu-id="f8045-206">**Is an inactive mailbox permanently deleted immediately after the hold is removed?**</span></span> <span data-ttu-id="f8045-207">如果不在作用中信箱的虛刪除日期是超過 30 天，只要您移除保留，不會被永久刪除信箱。</span><span class="sxs-lookup"><span data-stu-id="f8045-207">If the soft-deleted date for an inactive mailbox is older than 30 days, the mailbox won't be permanently deleted as soon as you remove the hold.</span></span> <span data-ttu-id="f8045-208">信箱會被標示為永久刪除，而且刪除它會處理在下一次。</span><span class="sxs-lookup"><span data-stu-id="f8045-208">The mailbox will be marked for permanent deletion and is deleted the next time it's processed.</span></span> 
    
- <span data-ttu-id="f8045-209">**虛刪除信箱保留期間如何影響非使用中信箱？**</span><span class="sxs-lookup"><span data-stu-id="f8045-209">**How does the soft-deleted mailbox retention period affect inactive mailboxes?**</span></span> <span data-ttu-id="f8045-210">如果不在作用中信箱的虛刪除日期超過 30 天保留已移除日期之前，信箱會標示為永久刪除。</span><span class="sxs-lookup"><span data-stu-id="f8045-210">If the soft-deleted date for an inactive mailbox is more than 30 days before the date the hold was removed, the mailbox is marked for permanent deletion.</span></span> <span data-ttu-id="f8045-211">但是，如果不在作用中的信箱已在過去 30 天內的虛刪除日期，並且移除保留，您就可以復原信箱，直到虛刪除信箱保留期間到期為止。</span><span class="sxs-lookup"><span data-stu-id="f8045-211">But if an inactive mailbox has a soft-deleted date within the last 30 days and you remove the hold, you can recover the mailbox up until the soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="f8045-212">如需詳細資訊，請參閱[刪除或還原使用者信箱在 Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835)。</span><span class="sxs-lookup"><span data-stu-id="f8045-212">For details, see [Delete or restore user mailboxes in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835).</span></span> <span data-ttu-id="f8045-213">虛刪除信箱保留期間到期之後，您必須依照復原非使用中信箱的程序。</span><span class="sxs-lookup"><span data-stu-id="f8045-213">After the soft-deleted mailbox retention period expires, you have follow the procedures for recovering an inactive mailbox.</span></span> <span data-ttu-id="f8045-214">如需詳細資訊，請參閱[復原非使用中信箱 Office 365 中](recover-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="f8045-214">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="f8045-215">**如何顯示不在作用中信箱的相關資訊之後移除保留？**</span><span class="sxs-lookup"><span data-stu-id="f8045-215">**How do you display information about an inactive mailbox after the hold is removed?**</span></span> <span data-ttu-id="f8045-216">移除保留且非使用中的信箱會回到虛刪除的信箱之後，它不會傳回*InactiveMailboxOnly*參數使用**Get-mailbox**指令程式。</span><span class="sxs-lookup"><span data-stu-id="f8045-216">After a hold is removed and the inactive mailbox is reverted back to a soft-deleted mailbox, it won't be returned by using the  *InactiveMailboxOnly*  parameter with the **Get-Mailbox** cmdlet.</span></span> <span data-ttu-id="f8045-217">但是，您可以使用**Get-mailbox SoftDeletedMailbox**命令來顯示信箱的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f8045-217">But you can display information about the mailbox by using the **Get-Mailbox -SoftDeletedMailbox** command.</span></span> <span data-ttu-id="f8045-218">例如：</span><span class="sxs-lookup"><span data-stu-id="f8045-218">For example:</span></span> 
    
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
  
<span data-ttu-id="f8045-219">在上述範例中， *WhenSoftDeleted*屬性識別的虛刪除的日期，這在這個範例中是 2014 年 10 月 30 日。</span><span class="sxs-lookup"><span data-stu-id="f8045-219">In the above example, the *WhenSoftDeleted* property identifies the soft-deleted date, which in this example is October 30, 2014.</span></span> <span data-ttu-id="f8045-220">如果此虛刪除的信箱先前已保留已移除的非使用中信箱，它將會永久刪除的 30 天後*WhenSoftDeleted*屬性的值。</span><span class="sxs-lookup"><span data-stu-id="f8045-220">If this soft-deleted mailbox was previously an inactive mailbox for which the hold was removed, it will be permanently deleted 30 days after the value of the *WhenSoftDeleted* property.</span></span> <span data-ttu-id="f8045-221">在此情況下，在 2014 年 11 月 30 日之後永久刪除信箱。</span><span class="sxs-lookup"><span data-stu-id="f8045-221">In this case, the mailbox is permanently deleted after November 30, 2014.</span></span>

