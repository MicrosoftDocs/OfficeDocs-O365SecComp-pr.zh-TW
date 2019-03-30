---
title: 置於就地保留虛刪除的信箱在 Exchange Online
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
description: 了解如何建立就地保留虛刪除信箱進行非使用中並保留其內容。 然後您可以使用 Microsoft eDiscovery 工具來搜尋非使用中信箱。
ms.openlocfilehash: f5ac31b4bfd993bf384aa17ba5f71de937cec720
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2019
ms.locfileid: "30999506"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a><span data-ttu-id="ac858-104">置於就地保留虛刪除的信箱在 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ac858-104">Put an In-Place Hold on a soft-deleted mailbox in Exchange Online</span></span>

<span data-ttu-id="ac858-105">了解如何建立就地保留虛刪除信箱進行非使用中並保留其內容。</span><span class="sxs-lookup"><span data-stu-id="ac858-105">Learn how to create an In-Place Hold for a soft-deleted mailbox to make it inactive and preserve its contents.</span></span> <span data-ttu-id="ac858-106">然後您可以使用 Microsoft eDiscovery 工具來搜尋非使用中信箱。</span><span class="sxs-lookup"><span data-stu-id="ac858-106">Then you can use Microsoft eDiscovery tools to search the inactive mailbox.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ac858-107">我們已建立新的就地保留在 Exchange Online （在 Office 365 和 Exchange Online 獨立計劃） 的期限延後。</span><span class="sxs-lookup"><span data-stu-id="ac858-107">We've postponed the deadline for creating new In-Place Holds in Exchange Online (in Office 365 and Exchange Online standalone plans).</span></span> <span data-ttu-id="ac858-108">但到今年年底或明年年初，您將無法在 Exchange Online 中建立新的「就地保留」。</span><span class="sxs-lookup"><span data-stu-id="ac858-108">But later this year or early next year, you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="ac858-109">改成使用就地保留，您可以使用安全性 & 合規性中心中的[eDiscovery 案例](https://go.microsoft.com/fwlink/?linkid=780738)或[保留原則](https://go.microsoft.com/fwlink/?linkid=827811)。</span><span class="sxs-lookup"><span data-stu-id="ac858-109">As an alternative to using In-Place Holds, you can use [eDiscovery cases](https://go.microsoft.com/fwlink/?linkid=780738) or [retention policies](https://go.microsoft.com/fwlink/?linkid=827811) in the Security & Compliance Center.</span></span> <span data-ttu-id="ac858-110">我們解除委任新就地保留之後，您仍然可以修改現有的就地保留，並建立新的就地保留在 Exchange Server 2013 和 Exchange 混合式部署仍會支援。</span><span class="sxs-lookup"><span data-stu-id="ac858-110">After we decommission new In-Place Holds, you'll still be able to modify existing In-Place Holds, and creating new In-Place Holds in Exchange Server 2013 and Exchange hybrid deployments will still be supported.</span></span> <span data-ttu-id="ac858-111">然後您仍然可以將信箱設為訴訟暫止。</span><span class="sxs-lookup"><span data-stu-id="ac858-111">And, you'll still be able to place mailboxes on Litigation Hold.</span></span> 
  
<span data-ttu-id="ac858-112">您可能需要其中人員已離開您的組織和其對應的使用者帳戶和信箱已刪除的情況。</span><span class="sxs-lookup"><span data-stu-id="ac858-112">You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted.</span></span> <span data-ttu-id="ac858-113">之後，您要瞭解沒有需要保留信箱中的資訊。</span><span class="sxs-lookup"><span data-stu-id="ac858-113">Afterwards, you realize there's information in the mailbox that needs to be preserved.</span></span> <span data-ttu-id="ac858-114">您可以做什麼？</span><span class="sxs-lookup"><span data-stu-id="ac858-114">What can you do?</span></span> <span data-ttu-id="ac858-115">如果尚未過期刪除的信箱保留期間，您可以置於就地保留已刪除的信箱 （稱為 「 虛刪除的信箱），並使其不在作用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="ac858-115">If the deleted mailbox retention period hasn't expired, you can put an In-Place Hold on the deleted mailbox (called a  soft-deleted mailbox ) and make it an inactive mailbox.</span></span> <span data-ttu-id="ac858-116">*非使用中信箱*用於他或她離開組織之後保留離職員工的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="ac858-116">An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="ac858-117">如已為 「 就地保留的持續時間處於虛刪除的信箱已進行非使用中時，會保留不在作用中信箱的內容。</span><span class="sxs-lookup"><span data-stu-id="ac858-117">The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive.</span></span> <span data-ttu-id="ac858-118">信箱進行非使用中之後，您可以使用 Exchange Online、 安全 & 與規範中心中，內容搜尋] 或 [SharePoint Online 中的 eDiscovery 中心中的 「 就地 eDiscovery 來搜尋信箱。</span><span class="sxs-lookup"><span data-stu-id="ac858-118">After the mailbox is made inactive, you can search the mailbox by using In-Place eDiscovery in Exchange Online, Content Search in the Security & Compliance Center, or the eDiscovery Center in SharePoint Online.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ac858-119">在 Exchange Online 中，將虛刪除的信箱會是已刪除，但可以在特定的保留期間內可復原的信箱。</span><span class="sxs-lookup"><span data-stu-id="ac858-119">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period.</span></span> <span data-ttu-id="ac858-120">Exchange Online 中的虛刪除信箱保留期間是 30 天。</span><span class="sxs-lookup"><span data-stu-id="ac858-120">The soft-deleted mailbox retention period in Exchange Online is 30 days.</span></span> <span data-ttu-id="ac858-121">這表示信箱可以復原 （或進行非使用中信箱） 的被刪除的 30 天內。</span><span class="sxs-lookup"><span data-stu-id="ac858-121">This means that the mailbox can be recovered (or made an inactive mailbox) within 30 days of being deleted.</span></span> <span data-ttu-id="ac858-122">30 天後，虛刪除的信箱標示為永久刪除和無法復原或進行非使用中。</span><span class="sxs-lookup"><span data-stu-id="ac858-122">After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered or made inactive.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="ac858-123">開始之前</span><span class="sxs-lookup"><span data-stu-id="ac858-123">Before you begin</span></span>

- <span data-ttu-id="ac858-124">您必須使用 Windows PowerShell 中的**New-mailboxsearch** cmdlet，將放在虛刪除的信箱上的 [就地保留。</span><span class="sxs-lookup"><span data-stu-id="ac858-124">You have to use the **New-MailboxSearch** cmdlet in Windows PowerShell to put an In-Place Hold on a soft-deleted mailbox.</span></span> <span data-ttu-id="ac858-125">您無法使用 Exchange 系統管理中心 (EAC) 或 SharePoint Online 中的 eDiscovery 中心。</span><span class="sxs-lookup"><span data-stu-id="ac858-125">You can't use the Exchange admin center (EAC) or the eDiscovery Center in SharePoint Online.</span></span> 
    
- <span data-ttu-id="ac858-126">若要了解如何使用 Windows PowerShell 連線到 Exchange Online，請參閱[連線到 Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="ac858-126">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
- <span data-ttu-id="ac858-127">執行下列命令，以取得貴組織中的虛刪除信箱的身分識別資訊。</span><span class="sxs-lookup"><span data-stu-id="ac858-127">Run the following command to get identity information about the soft-deleted mailboxes in your organization.</span></span> 
    
  ```
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- <span data-ttu-id="ac858-128">如需非使用中信箱的詳細資訊，請參閱 < <b0>Overview of Office 365 中的非使用中信箱</b0>。</span><span class="sxs-lookup"><span data-stu-id="ac858-128">For more information about inactive mailboxes, see [Overview of inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a><span data-ttu-id="ac858-129">放在虛刪除的信箱，使其成為非使用中信箱上的 [就地保留</span><span class="sxs-lookup"><span data-stu-id="ac858-129">Put an In-Place Hold on a soft-deleted mailbox to make it an inactive mailbox</span></span>

<span data-ttu-id="ac858-130">使用**New-mailboxsearch** cmdlet 將虛刪除的信箱不在作用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="ac858-130">Use the **New-MailboxSearch** cmdlet to make a soft-deleted mailbox an inactive mailbox.</span></span> <span data-ttu-id="ac858-131">如需詳細資訊，請參閱[New-mailboxsearch](http://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ac858-131">For more information, see [New-MailboxSearch](http://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx).</span></span>
  
1. <span data-ttu-id="ac858-132">建立包含變數，虛刪除信箱的內容。</span><span class="sxs-lookup"><span data-stu-id="ac858-132">Create a variable that contains the properties of the soft-deleted mailbox.</span></span> 
    
   ```
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="ac858-133">在上述命令中，使用 [ **DistinguishedName** ] 或 [ **ExchangeGuid**屬性的值來識別虛刪除的信箱。</span><span class="sxs-lookup"><span data-stu-id="ac858-133">In the previous command, use the value of the **DistinguishedName** or **ExchangeGuid** property to identify the soft-deleted mailbox.</span></span> <span data-ttu-id="ac858-134">這些屬性是唯一的組織中每個信箱，而是可能作用中信箱和虛刪除的信箱可能會有相同的主要 SMTP 位址。</span><span class="sxs-lookup"><span data-stu-id="ac858-134">These properties are unique for each mailbox in your organization, whereas it's possible that an active mailbox and a soft-deleted mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="ac858-135">建立就地保留，並將它放在虛刪除的信箱。</span><span class="sxs-lookup"><span data-stu-id="ac858-135">Create an In-Place Hold and place it on the soft-deleted mailbox.</span></span> <span data-ttu-id="ac858-136">在這個範例中，會指定不保留持續時間。</span><span class="sxs-lookup"><span data-stu-id="ac858-136">In this example, no hold duration is specified.</span></span> <span data-ttu-id="ac858-137">這表示項目將會無限期保留或直到從非使用中信箱移除保留為止。</span><span class="sxs-lookup"><span data-stu-id="ac858-137">This means items will be held indefinitely or until the hold is removed from the inactive mailbox.</span></span>
    
   ```
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```
   <span data-ttu-id="ac858-138">您也可以指定當您建立就地保留將保留持續時間。</span><span class="sxs-lookup"><span data-stu-id="ac858-138">You can also specify a hold duration when you create the In-Place Hold.</span></span> <span data-ttu-id="ac858-139">本範例會保留在作用中信箱項目大約 7 年。</span><span class="sxs-lookup"><span data-stu-id="ac858-139">This example holds items in the inactive mailbox for approximately 7 years.</span></span>
    
   ```
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. <span data-ttu-id="ac858-140">在一段時間之後執行下列其中一個下列命令，以確認虛刪除的信箱不在作用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="ac858-140">After a few moments, run one of the following commands to verify that the soft-deleted mailbox is an inactive mailbox.</span></span>
    
   ```
   Get-Mailbox -InactiveMailboxOnly
   ```

    <span data-ttu-id="ac858-141">或</span><span class="sxs-lookup"><span data-stu-id="ac858-141">Or</span></span>
    
   ```
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a><span data-ttu-id="ac858-142">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="ac858-142">More information</span></span>

<span data-ttu-id="ac858-143">之後，請將虛刪除的信箱不在作用中信箱有多種方式可以管理信箱。</span><span class="sxs-lookup"><span data-stu-id="ac858-143">After you make a soft-deleted mailbox an inactive mailbox, there are a number of ways you can manage the mailbox.</span></span> <span data-ttu-id="ac858-144">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="ac858-144">For more information, see:</span></span>
  
- [<span data-ttu-id="ac858-145">變更非使用中信箱的保留期間</span><span class="sxs-lookup"><span data-stu-id="ac858-145">Change the hold duration for an inactive mailbox</span></span>](change-the-hold-duration-for-an-inactive-mailbox.md)
    
- [<span data-ttu-id="ac858-146">復原非使用中的信箱</span><span class="sxs-lookup"><span data-stu-id="ac858-146">Recover an inactive mailbox</span></span>](recover-an-inactive-mailbox.md)
    
- [<span data-ttu-id="ac858-147">還原非使用中的信箱</span><span class="sxs-lookup"><span data-stu-id="ac858-147">Restore an inactive mailbox</span></span>](restore-an-inactive-mailbox.md)
    
- <span data-ttu-id="ac858-148">[刪除非使用中信箱](delete-an-inactive-mailbox.md)（藉由移除保留）</span><span class="sxs-lookup"><span data-stu-id="ac858-148">[Delete an inactive mailbox](delete-an-inactive-mailbox.md) (by removing the hold)</span></span>
