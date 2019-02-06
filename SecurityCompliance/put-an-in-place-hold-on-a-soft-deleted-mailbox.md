---
title: 置於就地保留虛刪除信箱在 Exchange Online
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid: ''
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
description: 了解如何建立就地保留虛刪除信箱以進行非使用中並保留其內容。然後您可以使用 Microsoft eDiscovery 工具來搜尋非使用中的信箱。
ms.openlocfilehash: e666ac608ec224bf97caa947be2cb42b742c6fa9
ms.sourcegitcommit: ca97beff215d154b6ab006ce1222056434fde1a9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2019
ms.locfileid: "29740795"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a><span data-ttu-id="d0eac-104">置於就地保留虛刪除信箱在 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d0eac-104">Put an In-Place Hold on a soft-deleted mailbox in Exchange Online</span></span>

<span data-ttu-id="d0eac-p102">了解如何建立就地保留虛刪除信箱以進行非使用中並保留其內容。然後您可以使用 Microsoft eDiscovery 工具來搜尋非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="d0eac-p102">Learn how to create an In-Place Hold for a soft-deleted mailbox to make it inactive and preserve its contents. Then you can use Microsoft eDiscovery tools to search the inactive mailbox.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d0eac-p103">我們已延遲到達期限時建立的新就地保留 Exchange Online 中 （在 Office 365 和 Exchange Online 獨立計劃）。但是稍後今年或早期明年您將無法建立新就地保留在 Exchange Online。若要使用就地保留或者，您可以使用[eDiscovery 案例](https://go.microsoft.com/fwlink/?linkid=780738)或[保留原則](https://go.microsoft.com/fwlink/?linkid=827811)Office 365 安全性&amp;規範中心。我們解除委任新就地保留之後，您將仍然可以修改現有的就地保留，並建立新的就地保留在 Exchange Server 2013 和 Exchange 混合部署將仍然支援。然後您仍必須能夠將信箱設為在訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="d0eac-p103">We've postponed the deadline for creating new In-Place Holds in Exchange Online (in Office 365 and Exchange Online standalone plans). But later this year or early next year, you won't be able to create new In-Place Holds in Exchange Online. As an alternative to using In-Place Holds, you can use [eDiscovery cases](https://go.microsoft.com/fwlink/?linkid=780738) or [retention policies](https://go.microsoft.com/fwlink/?linkid=827811) in the Office 365 Security &amp; Compliance Center. After we decommission new In-Place Holds, you'll still be able to modify existing In-Place Holds, and creating new In-Place Holds in Exchange Server 2013 and Exchange hybrid deployments will still be supported. And, you'll still be able to place mailboxes on Litigation Hold.</span></span> 
  
<span data-ttu-id="d0eac-p104">您可能必須在其中人員會靠左您的組織和其對應的使用者帳戶和信箱已刪除的情況。之後，您了解有需要保留信箱中的資訊。您可以執行什麼動作？如果尚未過期的已刪除的信箱保留期間，您可以置於就地保留已刪除的信箱 （稱為 「 虛刪除信箱） 並使其不在作用中的信箱。*非使用中信箱*用來保留先前員工的電子郵件之後他離開貴組織。不在作用中信箱的內容會保留的持續時間內所就地保留處於虛刪除信箱時上次進行非使用中。進行不在作用中信箱之後，您可以在 Exchange Online 中，Office 365 安全性內容搜尋使用就地 eDiscovery 搜尋信箱&amp;規範中心或 SharePoint Online 中的 eDiscovery 中心。</span><span class="sxs-lookup"><span data-stu-id="d0eac-p104">You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted. Afterwards, you realize there's information in the mailbox that needs to be preserved. What can you do? If the deleted mailbox retention period hasn't expired, you can put an In-Place Hold on the deleted mailbox (called a  soft-deleted mailbox ) and make it an inactive mailbox. An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization. The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive. After the mailbox is made inactive, you can search the mailbox by using In-Place eDiscovery in Exchange Online, Content Search in the Office 365 Security &amp; Compliance Center, or the eDiscovery Center in SharePoint Online.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d0eac-p105">在 Exchange Online 虛刪除信箱是已遭刪除，但在特定的保留期間內可復原的信箱。Exchange Online 中的虛刪除信箱保留期間是 30 天。這表示可以信箱復原 （或進行非使用中的信箱） 的要刪除的 30 天內。30 天後虛刪除信箱標記為永久刪除和無法復原或進行非使用中。</span><span class="sxs-lookup"><span data-stu-id="d0eac-p105">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period. The soft-deleted mailbox retention period in Exchange Online is 30 days. This means that the mailbox can be recovered (or made an inactive mailbox) within 30 days of being deleted. After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered or made inactive.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="d0eac-123">開始之前</span><span class="sxs-lookup"><span data-stu-id="d0eac-123">Before you begin</span></span>

- <span data-ttu-id="d0eac-p106">您必須在 Windows PowerShell 中使用**New-mailboxsearch**指令程式將放在虛刪除信箱上的 [就地保留。您無法使用 Exchange 系統管理中心 (EAC) 或 SharePoint Online 中的 eDiscovery 中心。</span><span class="sxs-lookup"><span data-stu-id="d0eac-p106">You have to use the **New-MailboxSearch** cmdlet in Windows PowerShell to put an In-Place Hold on a soft-deleted mailbox. You can't use the Exchange admin center (EAC) or the eDiscovery Center in SharePoint Online.</span></span> 
    
- <span data-ttu-id="d0eac-126">若要了解如何使用 Windows PowerShell 連線到 Exchange Online，請參閱[連線到 Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="d0eac-126">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
- <span data-ttu-id="d0eac-127">執行下列命令以取得組織中的虛刪除信箱的身分識別資訊。</span><span class="sxs-lookup"><span data-stu-id="d0eac-127">Run the following command to get identity information about the soft-deleted mailboxes in your organization.</span></span> 
    
  ```
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- <span data-ttu-id="d0eac-128">如需非使用中信箱的詳細資訊，請參閱 ＜ [Overview of Office 365 中的非使用中信箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="d0eac-128">For more information about inactive mailboxes, see [Overview of inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a><span data-ttu-id="d0eac-129">放虛刪除信箱使其成為非使用中的信箱上的 [就地保留</span><span class="sxs-lookup"><span data-stu-id="d0eac-129">Put an In-Place Hold on a soft-deleted mailbox to make it an inactive mailbox</span></span>

<span data-ttu-id="d0eac-p107">使用**New-mailboxsearch** cmdlet 可讓虛刪除信箱成為非使用中的信箱。如需詳細資訊，請參閱[New-mailboxsearch](http://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d0eac-p107">Use the **New-MailboxSearch** cmdlet to make a soft-deleted mailbox an inactive mailbox. For more information, see [New-MailboxSearch](http://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx).</span></span>
  
1. <span data-ttu-id="d0eac-132">建立包含虛刪除信箱之屬性的變數。</span><span class="sxs-lookup"><span data-stu-id="d0eac-132">Create a variable that contains the properties of the soft-deleted mailbox.</span></span> 
    
   ```
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="d0eac-p108">在上述命令中，使用**DistinguishedName**或**ExchangeGuid**屬性的值來識別虛刪除信箱。這些屬性是唯一的組織中每個信箱，而很可能使用中的信箱及虛刪除信箱可能會有相同的主要 SMTP 位址。</span><span class="sxs-lookup"><span data-stu-id="d0eac-p108">In the previous command, use the value of the **DistinguishedName** or **ExchangeGuid** property to identify the soft-deleted mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active mailbox and a soft-deleted mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="d0eac-p109">建立就地保留和放在虛刪除信箱。在這個範例中，會指定不保留持續時間。這表示項目將會保留無限期或直到撤除從非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="d0eac-p109">Create an In-Place Hold and place it on the soft-deleted mailbox. In this example, no hold duration is specified. This means items will be held indefinitely or until the hold is removed from the inactive mailbox.</span></span>
    
   ```
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```
   <span data-ttu-id="d0eac-p110">您也可以指定當您建立就地保留保留持續時間。本範例會包含一個項目不在作用中的信箱中大約 7 年。</span><span class="sxs-lookup"><span data-stu-id="d0eac-p110">You can also specify a hold duration when you create the In-Place Hold. This example holds items in the inactive mailbox for approximately 7 years.</span></span>
    
   ```
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. <span data-ttu-id="d0eac-140">在一段時間後執行下列命令來確認虛刪除信箱不在作用中信箱的其中一個。</span><span class="sxs-lookup"><span data-stu-id="d0eac-140">After a few moments, run one of the following commands to verify that the soft-deleted mailbox is an inactive mailbox.</span></span>
    
   ```
   Get-Mailbox -InactiveMailboxOnly
   ```

    <span data-ttu-id="d0eac-141">或</span><span class="sxs-lookup"><span data-stu-id="d0eac-141">Or</span></span>
    
   ```
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a><span data-ttu-id="d0eac-142">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="d0eac-142">More information</span></span>

<span data-ttu-id="d0eac-p111">進行虛刪除信箱不在作用中的信箱後，有數種方式可以管理信箱。如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="d0eac-p111">After you make a soft-deleted mailbox an inactive mailbox, there are a number of ways you can manage the mailbox. For more information, see:</span></span>
  
- [<span data-ttu-id="d0eac-145">變更非使用中信箱的保留期間</span><span class="sxs-lookup"><span data-stu-id="d0eac-145">Change the hold duration for an inactive mailbox</span></span>](change-the-hold-duration-for-an-inactive-mailbox.md)
    
- [<span data-ttu-id="d0eac-146">復原非使用中的信箱</span><span class="sxs-lookup"><span data-stu-id="d0eac-146">Recover an inactive mailbox</span></span>](recover-an-inactive-mailbox.md)
    
- [<span data-ttu-id="d0eac-147">還原非使用中的信箱</span><span class="sxs-lookup"><span data-stu-id="d0eac-147">Restore an inactive mailbox</span></span>](restore-an-inactive-mailbox.md)
    
- <span data-ttu-id="d0eac-148">[刪除非作用中的信箱](delete-an-inactive-mailbox.md)（由移除保留）</span><span class="sxs-lookup"><span data-stu-id="d0eac-148">[Delete an inactive mailbox](delete-an-inactive-mailbox.md) (by removing the hold)</span></span>
