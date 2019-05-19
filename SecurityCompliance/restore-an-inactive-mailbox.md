---
title: 還原 Office 365 中的非使用中信箱
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/28/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 97e06a7a-ef9a-4ce8-baea-18b9e20449a3
description: 如果新進員工或另一位使用者需要存取 Office 365 中的非使用中信箱的內容，您可以還原 （或合併） 到現有的信箱不在作用中信箱的內容。
ms.openlocfilehash: 6bd147296e4324c5f75ff808768f8899cf9b59fd
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34157305"
---
# <a name="restore-an-inactive-mailbox-in-office-365"></a><span data-ttu-id="0f09e-103">還原 Office 365 中的非使用中信箱</span><span class="sxs-lookup"><span data-stu-id="0f09e-103">Restore an inactive mailbox in Office 365</span></span>

<span data-ttu-id="0f09e-104">非使用中信箱 （也就是一種虛刪除的信箱） 用來他或她離開組織之後保留離職員工的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="0f09e-104">An inactive mailbox (which is a type of soft-deleted mailbox) is used to retain a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="0f09e-105">如果另一位員工承擔承接已離開員工工作職責，或者該員工返回您的組織，有兩種方法可將非作用中信箱的內容提供給使用者：</span><span class="sxs-lookup"><span data-stu-id="0f09e-105">If another employee takes on the job responsibilities of the departed employee or if that employee returns to your organization, there are two ways that you can make the contents of the inactive mailbox available to a user:</span></span> 
  
- <span data-ttu-id="0f09e-106">**還原非使用中信箱**如果另一位員工承擔承接已離開員工的工作職責或另一位使用者需要存取非使用中信箱的內容，您可以還原 （或合併） 到現有的信箱不在作用中信箱的內容。</span><span class="sxs-lookup"><span data-stu-id="0f09e-106">**Restore an inactive mailbox** If another employee takes on the job responsibilities of the departed employee, or if another user needs access to the contents of the inactive mailbox, you can restore (or merge) the contents of the inactive mailbox to an existing mailbox.</span></span> <span data-ttu-id="0f09e-107">您也可以從非使用中信箱還原封存。</span><span class="sxs-lookup"><span data-stu-id="0f09e-107">You can also restore the archive from an inactive mailbox.</span></span> <span data-ttu-id="0f09e-108">它會還原後，非使用中的信箱會保留，並會保留為非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="0f09e-108">After it's restored, the inactive mailbox is preserved and is retained as an inactive mailbox.</span></span> <span data-ttu-id="0f09e-109">本主題說明用來還原非使用中信箱的程序。</span><span class="sxs-lookup"><span data-stu-id="0f09e-109">This topic describes the procedures for restoring an inactive mailbox.</span></span> 
    
- <span data-ttu-id="0f09e-110">**復原非使用中信箱**如果承接已離開的員工返回您的組織，或是新進員工雇用採取承接已離開員工工作職責，您可以復原非使用中信箱的內容。</span><span class="sxs-lookup"><span data-stu-id="0f09e-110">**Recover an inactive mailbox** If the departed employee returns to your organization, or if a new employee is hired to take on the job responsibilities of the departed employee, you can recover the contents of the inactive mailbox.</span></span> <span data-ttu-id="0f09e-111">此方法會將作用中的信箱轉換成新的信箱，其中包含非作用中信箱的內容。</span><span class="sxs-lookup"><span data-stu-id="0f09e-111">This method converts the inactive mailbox to a new mailbox that contains the contents of the inactive mailbox.</span></span> <span data-ttu-id="0f09e-112">它會復原之後，非使用中的信箱不存在。</span><span class="sxs-lookup"><span data-stu-id="0f09e-112">After it's recovered, the inactive mailbox no longer exists.</span></span> <span data-ttu-id="0f09e-113">如需逐步程序，請參閱[復原非使用中信箱 Office 365 中](recover-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="0f09e-113">For the step-by-step procedures, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
<span data-ttu-id="0f09e-114">請參閱這篇文章，如需詳細資訊還原和復原非使用中的信箱之間的差異**的詳細資訊**一節。</span><span class="sxs-lookup"><span data-stu-id="0f09e-114">See the **More information** section in this article for more details about the differences between restoring and recovering an inactive mailbox.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="0f09e-115">開始之前</span><span class="sxs-lookup"><span data-stu-id="0f09e-115">Before you begin</span></span>

- <span data-ttu-id="0f09e-116">您必須使用 Exchange Online PowerShell 來還原非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="0f09e-116">You have to use Exchange Online PowerShell to restore an inactive mailbox.</span></span> <span data-ttu-id="0f09e-117">您無法使用 Exchange 系統管理中心 (EAC)。</span><span class="sxs-lookup"><span data-stu-id="0f09e-117">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="0f09e-118">如需逐步指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。</span><span class="sxs-lookup"><span data-stu-id="0f09e-118">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span></span>
    
- <span data-ttu-id="0f09e-119">下列命令在 Exchange Online PowerShell 中執行若要取得您組織中的非使用中信箱的身分識別資訊。</span><span class="sxs-lookup"><span data-stu-id="0f09e-119">Run the following command in Exchange Online PowerShell to get identity information for the inactive mailboxes in your organization.</span></span> 
    
    ```
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

     <span data-ttu-id="0f09e-120">若要還原特定的非使用中信箱使用這個命令所傳回的資訊。</span><span class="sxs-lookup"><span data-stu-id="0f09e-120">Use the information returned by this command to restore a specific inactive mailbox.</span></span>
    
- <span data-ttu-id="0f09e-121">如需非使用中信箱的詳細資訊，請參閱 <<c0>在 Office 365 中的非使用中信箱。</span><span class="sxs-lookup"><span data-stu-id="0f09e-121">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="restore-an-inactive-mailbox"></a><span data-ttu-id="0f09e-122">還原非作用中的信箱</span><span class="sxs-lookup"><span data-stu-id="0f09e-122">Restore an inactive mailbox</span></span>

<span data-ttu-id="0f09e-123">使用**New-mailboxrestorerequest**指令程式搭配_SourceMailbox_和_TargetMailbox_參數，非使用中信箱的內容還原到現有的信箱。</span><span class="sxs-lookup"><span data-stu-id="0f09e-123">Use the **New-MailboxRestoreRequest** cmdlet with the  _SourceMailbox_ and  _TargetMailbox_ parameters to restore the contents of an inactive mailbox to an existing mailbox.</span></span> <span data-ttu-id="0f09e-124">如需使用此 cmdlet 的詳細資訊，請參閱[New-mailboxrestorerequest](https://go.microsoft.com/fwlink/?linkid=856298)。</span><span class="sxs-lookup"><span data-stu-id="0f09e-124">For more information about using this cmdlet, see [New-MailboxRestoreRequest](https://go.microsoft.com/fwlink/?linkid=856298).</span></span>
  
1. <span data-ttu-id="0f09e-125">建立包含非作用中信箱的內容的變數。</span><span class="sxs-lookup"><span data-stu-id="0f09e-125">Create a variable that contains the properties of the inactive mailbox.</span></span> 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="0f09e-126">在上述命令中，使用 [ **DistinguishedName** ] 或 [ **ExchangeGUID**屬性的值來識別非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="0f09e-126">In the previous command, use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox.</span></span> <span data-ttu-id="0f09e-127">這些屬性是唯一的組織中每個信箱，而是可能作用中或非使用中的信箱可能會有相同的主要 SMTP 位址。</span><span class="sxs-lookup"><span data-stu-id="0f09e-127">These properties are unique for each mailbox in your organization, whereas it's possible that an active and an inactive mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="0f09e-128">非使用中信箱的內容還原到現有的信箱。</span><span class="sxs-lookup"><span data-stu-id="0f09e-128">Restore the contents of the inactive mailbox to an existing mailbox.</span></span> <span data-ttu-id="0f09e-129">非使用中信箱 （來源信箱） 的內容將被合併到現有信箱 （目標信箱） 中相對應的資料夾。</span><span class="sxs-lookup"><span data-stu-id="0f09e-129">The contents of the inactive mailbox (source mailbox) will be merged into the corresponding folders in the existing mailbox (target mailbox).</span></span>
    
    ```
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -AllowLegacyDNMismatch
    ```
   
   <span data-ttu-id="0f09e-130">或者，您可以指定最上層資料夾中用來從非使用中信箱還原內容的目標信箱中。</span><span class="sxs-lookup"><span data-stu-id="0f09e-130">Alternatively, you can specify a top-level folder in the target mailbox in which to restore the contents from the inactive mailbox.</span></span> <span data-ttu-id="0f09e-131">如果目標信箱中不存在的指定的目標資料夾或目標資料夾結構，則會建立在還原程序。</span><span class="sxs-lookup"><span data-stu-id="0f09e-131">If the specified target folder or target folder structure doesn't already exist in the target mailbox, it is created during the restore process.</span></span> 
    
    <span data-ttu-id="0f09e-132">此範例會將信箱項目及從非使用中信箱至名為 「 非使用中信箱 」 資料夾的子資料夾複製目標信箱的最上層資料夾結構中。</span><span class="sxs-lookup"><span data-stu-id="0f09e-132">This example copies mailbox items and subfolders from an inactive mailbox to a folder named "Inactive Mailbox" in the top-level folder structure of the target mailbox.</span></span>
    
   ```
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
   ```
  
## <a name="restore-the-archive-from-an-inactive-mailbox"></a><span data-ttu-id="0f09e-133">從非使用中的信箱還原封存</span><span class="sxs-lookup"><span data-stu-id="0f09e-133">Restore the archive from an inactive mailbox</span></span>

<span data-ttu-id="0f09e-134">如果不在作用中信箱有封存信箱，可以也將它還原到現有信箱的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="0f09e-134">If an inactive mailbox has an archive mailbox, you can also restore it to the archive mailbox of an existing mailbox.</span></span> <span data-ttu-id="0f09e-135">若要從非使用中的信箱還原封存，您必須將_SourceIsArchive_和_TargetIsAchive_參數新增至用來還原非使用中信箱的命令。</span><span class="sxs-lookup"><span data-stu-id="0f09e-135">To restore the archive from an inactive mailbox, you have to add the  _SourceIsArchive_ and  _TargetIsAchive_ switches to the command used to restore an inactive mailbox.</span></span> 
  
1. <span data-ttu-id="0f09e-136">建立包含非作用中信箱的內容的變數。</span><span class="sxs-lookup"><span data-stu-id="0f09e-136">Create a variable that contains the properties of the inactive mailbox.</span></span> 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="0f09e-137">在上述命令中，使用 [ **DistinguishedName** ] 或 [ **ExchangeGUID**屬性的值來識別非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="0f09e-137">In the previous command, use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox.</span></span> <span data-ttu-id="0f09e-138">這些屬性是唯一的組織中每個信箱，而是可能作用中或非使用中的信箱可能會有相同的主要 SMTP 位址。</span><span class="sxs-lookup"><span data-stu-id="0f09e-138">These properties are unique for each mailbox in your organization, whereas it's possible that an active and an inactive mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="0f09e-139">非使用中信箱 （來源封存） 封存的內容，還原至現有信箱 （目標封存） 封存中。</span><span class="sxs-lookup"><span data-stu-id="0f09e-139">Restore the contents of the archive from the inactive mailbox (source archive) to the archive of an existing mailbox (target archive).</span></span> <span data-ttu-id="0f09e-140">在這個範例中，從來源封存的內容複製到目標信箱的封存中名為 「 非使用中信箱封存 」 資料夾。</span><span class="sxs-lookup"><span data-stu-id="0f09e-140">In this example, the contents from the source archive are copied to a folder named "Inactive Mailbox Archive" in the archive of the target mailbox.</span></span>

    ```
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -SourceIsArchive -TargetMailbox newemployee@contoso.com -TargetIsArchive -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
    ```

  
## <a name="more-information"></a><span data-ttu-id="0f09e-141">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="0f09e-141">More information</span></span>

- <span data-ttu-id="0f09e-142">**復原和還原非使用中信箱的主要差異是什麼？**</span><span class="sxs-lookup"><span data-stu-id="0f09e-142">**What's the main difference between recovering and restoring an inactive mailbox?**</span></span> <span data-ttu-id="0f09e-143">當您復原非使用中的信箱時，信箱基本上轉換成新的信箱、 仍會保留的內容和非使用中信箱的資料夾結構，以及信箱連結到新的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="0f09e-143">When you recover an inactive mailbox, the mailbox is basically converted to a new mailbox, the contents and folder structure of the inactive mailbox are retained, and the mailbox is linked to a new user account.</span></span> <span data-ttu-id="0f09e-144">它會復原後，在作用中的信箱不存在，任何新的信箱中的內容所做的變更會影響原先的內容保留在作用中信箱。</span><span class="sxs-lookup"><span data-stu-id="0f09e-144">After it's recovered, the inactive mailbox no longer exists, and any changes made to the content in the new mailbox will affect the content that was originally on hold in the inactive mailbox.</span></span> <span data-ttu-id="0f09e-145">相反地，當您還原非使用中信箱時，內容只會複製到另一個信箱。</span><span class="sxs-lookup"><span data-stu-id="0f09e-145">Conversely, when you restore an inactive mailbox, the contents are merely copied to another mailbox.</span></span> <span data-ttu-id="0f09e-146">非使用中的信箱會保留，並會維持不在作用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="0f09e-146">The inactive mailbox is preserved and remains an inactive mailbox.</span></span> <span data-ttu-id="0f09e-147">任何目標信箱中的內容所做的變更不會影響原始內容保留在作用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="0f09e-147">Any changes made to the content in the target mailbox won't affect the original content held in the inactive mailbox.</span></span> <span data-ttu-id="0f09e-148">非使用中信箱仍可搜尋的安全性 & 合規性中心中使用[內容搜尋工具](run-a-content-search-in-the-security-and-compliance-center.md)、 其內容可以還原至另一個信箱，或復原或刪除日後。</span><span class="sxs-lookup"><span data-stu-id="0f09e-148">The inactive mailbox can still be searched by using the [Content Search tool](run-a-content-search-in-the-security-and-compliance-center.md) in the Security & Compliance Center, its contents can be restored to another mailbox, or it can be recovered or deleted at a later date.</span></span> 
    
- <span data-ttu-id="0f09e-149">**您要如何找到非使用中信箱？**</span><span class="sxs-lookup"><span data-stu-id="0f09e-149">**How do you find inactive mailboxes?**</span></span> <span data-ttu-id="0f09e-150">若要取得您組織中的非使用中信箱的清單，並顯示適合用來還原非使用中信箱的資訊，您可以執行此命令。</span><span class="sxs-lookup"><span data-stu-id="0f09e-150">To get a list of the inactive mailboxes in your organization and display information that is useful for restoring an inactive mailbox, you can run this command.</span></span> 

  ```
  Get-Mailbox -InactiveMailboxOnly | FL Name,PrimarySMTPAddress,DistinguishedName,ExchangeGUID,LegacyExchangeDN,ArchiveStatus
  ```

- <span data-ttu-id="0f09e-151">**使用訴訟暫止狀態或 Office 365 保留原則來保留非使用中信箱的內容。**</span><span class="sxs-lookup"><span data-stu-id="0f09e-151">**Use a Litigation Hold or Office 365 retention policy to retain inactive mailbox content.**</span></span> <span data-ttu-id="0f09e-152">如果您想要保留狀態的非使用中的信箱還原後，您可以啟用[訴訟暫](https://go.microsoft.com/fwlink/?linkid=856286)止的目標信箱，或套用[Office 365 保留原則](retention-policies.md)，再還原非使用中信箱。</span><span class="sxs-lookup"><span data-stu-id="0f09e-152">If you want to retain the state of an inactive mailbox after it's restored, you can place the target mailbox on [Litigation Hold](https://go.microsoft.com/fwlink/?linkid=856286) or apply an [Office 365 retention policy](retention-policies.md) before you restore the inactive mailbox.</span></span> <span data-ttu-id="0f09e-153">這可防止從非使用中信箱的任何項目永久刪除之後他們正在還原至目標信箱。</span><span class="sxs-lookup"><span data-stu-id="0f09e-153">This will prevent the permanent deletion of any items from the inactive mailbox after they're restored to the target mailbox.</span></span> 
    
- <span data-ttu-id="0f09e-154">**還原非使用中信箱之前，請啟用保留功能，在目標信箱。**</span><span class="sxs-lookup"><span data-stu-id="0f09e-154">**Enable retention hold on the target mailbox before you restore an inactive mailbox.**</span></span> <span data-ttu-id="0f09e-155">從非使用中信箱的信箱項目可能是舊，因為您可以考慮再還原非使用中的信箱啟用保留功能，在目標信箱。</span><span class="sxs-lookup"><span data-stu-id="0f09e-155">Because mailbox items from an inactive mailbox could be old, you might consider enabling retention hold on the target mailbox before you restore an inactive mailbox.</span></span> <span data-ttu-id="0f09e-156">當您對信箱設定保留保留，不會處理保留原則指派給它，直到移除保留功能，或直到保留期間到期為止。</span><span class="sxs-lookup"><span data-stu-id="0f09e-156">When you put a mailbox on retention hold, the retention policy that's assigned to it won't be processed until the retention hold is removed or until the retention hold period expires.</span></span> <span data-ttu-id="0f09e-157">這可以讓目標信箱時間來管理舊郵件從非使用中信箱的擁有者。</span><span class="sxs-lookup"><span data-stu-id="0f09e-157">This gives the owner of the target mailbox time to manage old messages from the inactive mailbox.</span></span> <span data-ttu-id="0f09e-158">否則，保留原則可能會刪除舊項目 （或將項目移至封存信箱，如果已啟用） 已過期根據設定的目標信箱的保留設定。</span><span class="sxs-lookup"><span data-stu-id="0f09e-158">Otherwise, the retention policy might delete old items (or move items to the archive mailbox, if it's enabled) that have expired based on the retention settings configured for the target mailbox.</span></span> <span data-ttu-id="0f09e-159">如需詳細資訊，請參閱[就地保留信箱保留在 Exchange Online](https://go.microsoft.com/fwlink/?linkid=856300)。</span><span class="sxs-lookup"><span data-stu-id="0f09e-159">For more information, see [Place a mailbox on retention hold in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856300).</span></span>
    
- <span data-ttu-id="0f09e-160">**AllowLegacyDNMismatch 參數做什麼？**</span><span class="sxs-lookup"><span data-stu-id="0f09e-160">**What does the AllowLegacyDNMismatch switch do?**</span></span> <span data-ttu-id="0f09e-161">在還原非使用中信箱前一個範例中， **AllowLegacyDNMismatch**參數用來允許不在作用中信箱還原至不同的目標信箱。</span><span class="sxs-lookup"><span data-stu-id="0f09e-161">In the previous examples to restore an inactive mailbox, the **AllowLegacyDNMismatch** switch is used to allow restoring the inactive mailbox to a different target mailbox.</span></span> <span data-ttu-id="0f09e-162">在一般還原案例中，目標是要還原的內容來源和目標信箱所在位置，同一個信箱。</span><span class="sxs-lookup"><span data-stu-id="0f09e-162">In a typical restore scenario, the goal is to restore content where the source and target mailboxes are the same mailbox.</span></span> <span data-ttu-id="0f09e-163">因此依預設， **New-mailboxrestorerequest**指令程式會檢查以確定來源和目標信箱的**LegacyExchangeDN**屬性的值是相同。</span><span class="sxs-lookup"><span data-stu-id="0f09e-163">So by default, the **New-MailboxRestoreRequest** cmdlet checks to make sure that the value of the **LegacyExchangeDN** property on the source and target mailboxes is the same.</span></span> <span data-ttu-id="0f09e-164">這有助於防止您不小心將來源信箱還原到錯誤的目標信箱。</span><span class="sxs-lookup"><span data-stu-id="0f09e-164">This helps prevents you from accidentally restoring a source mailbox into the wrong target mailbox.</span></span> <span data-ttu-id="0f09e-165">如果您嘗試還原非使用中的信箱，而不使用**AllowLegacyDNMismatch**參數，命令可能會失敗如果來源和目標信箱有不同的**LegacyExchangeDN**屬性的值。</span><span class="sxs-lookup"><span data-stu-id="0f09e-165">If you try to restore an inactive mailbox without using the **AllowLegacyDNMismatch** switch, the command might fail if the source and target mailboxes have different values for the **LegacyExchangeDN** property.</span></span> 
    
- <span data-ttu-id="0f09e-166">**您可以使用 New-mailboxrestorerequest 指令程式搭配其他參數，來實作不同的還原案例的非使用中信箱。**</span><span class="sxs-lookup"><span data-stu-id="0f09e-166">**You can use other parameters with the New-MailboxRestoreRequest cmdlet to implement different restore scenarios for inactive mailboxes.**</span></span> <span data-ttu-id="0f09e-167">例如，您可以執行此命令以將封存從非使用中信箱還原至目標信箱的主要信箱。</span><span class="sxs-lookup"><span data-stu-id="0f09e-167">For example, you can run this command to restore the archive from the inactive mailbox into the primary mailbox of the target mailbox.</span></span> 
    
  ```
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -SourceIsArchive -TargetMailbox <target mailbox> -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
  ```

  <span data-ttu-id="0f09e-168">您也可以執行此命令，來還原至目標信箱的封存的非使用中的主要信箱。</span><span class="sxs-lookup"><span data-stu-id="0f09e-168">You can also restore the inactive primary mailbox into the archive of the target mailbox by running this command.</span></span>

  ```
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -TargetMailbox <target mailbox> -TargetIsArchive -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
  ```

- <span data-ttu-id="0f09e-169">**用途 TargetRootFolder 參數？**</span><span class="sxs-lookup"><span data-stu-id="0f09e-169">**What does the TargetRootFolder parameter do?**</span></span> <span data-ttu-id="0f09e-170">如先前所述，您可以使用**TargetRootFolder**參數指定的資料夾中 （也稱為根） 的資料夾結構的頂端在目標信箱中用來還原非使用中信箱的內容。</span><span class="sxs-lookup"><span data-stu-id="0f09e-170">As previously explained, you can use the **TargetRootFolder** parameter to specify a folder in the top of the folder structure (also called the root) in the target mailbox in which to restore the contents of the inactive mailbox.</span></span> <span data-ttu-id="0f09e-171">如果您未使用此參數，從非使用中信箱的信箱項目已合併成的目標信箱的對應預設資料夾，而自訂資料夾存在於目標信箱的根目錄中重新建立。</span><span class="sxs-lookup"><span data-stu-id="0f09e-171">If you don't use this parameter, mailbox items from the inactive mailbox are merged into the corresponding default folders of the target mailbox, and custom folders are re-created in the root of the target mailbox.</span></span> <span data-ttu-id="0f09e-172">下列圖例反白顯示這些差異不使用，而且使用**TargetRootFolder**參數。</span><span class="sxs-lookup"><span data-stu-id="0f09e-172">The following illustrations highlight these differences between not using and using the **TargetRootFolder** parameter.</span></span> 
    
    <span data-ttu-id="0f09e-173">**在目標信箱時未使用 TargetRootFolder 參數的資料夾階層**</span><span class="sxs-lookup"><span data-stu-id="0f09e-173">**Folder hierarchy in the target mailbox when the TargetRootFolder parameter isn't used**</span></span>
    
    ![未使用 TargetRootFolder 參數時的螢幕擷取畫面](media/76a759af-f483-4d1c-8cc7-243435b5562e.png)
  
    <span data-ttu-id="0f09e-175">**在目標信箱使用 TargetRootFolder 參數時的資料夾階層**</span><span class="sxs-lookup"><span data-stu-id="0f09e-175">**Folder hierarchy in the target mailbox when the TargetRootFolder parameter is used**</span></span>
    
    ![使用 TargetRootFolder 參數時的螢幕擷取畫面](media/300da592-7323-48db-b8a4-07012259d113.png)

  

