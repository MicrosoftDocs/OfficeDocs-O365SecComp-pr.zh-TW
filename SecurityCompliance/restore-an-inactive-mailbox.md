---
title: 還原 Office 365 中的非使用中信箱
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/28/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 97e06a7a-ef9a-4ce8-baea-18b9e20449a3
description: 如果新員工或另一位使用者需要存取 Office 365 中不在作用中信箱的內容，您可以還原 （或合併） 至現有的信箱不在作用中信箱的內容。
ms.openlocfilehash: 671b13b913cddcfc3a7784d621b01b864b07e4e3
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214233"
---
# <a name="restore-an-inactive-mailbox-in-office-365"></a><span data-ttu-id="663e6-103">還原 Office 365 中的非使用中信箱</span><span class="sxs-lookup"><span data-stu-id="663e6-103">Restore an inactive mailbox in Office 365</span></span>

<span data-ttu-id="663e6-p101">（這是一種虛刪除信箱） 的非使用中信箱用來保留先前員工的電子郵件之後他離開貴組織。如果另一位員工採用 departed 員工的工作職責上或該員工會傳回您組織，有兩種方式您可以決定將非使用中信箱的內容提供給使用者：</span><span class="sxs-lookup"><span data-stu-id="663e6-p101">An inactive mailbox (which is a type of soft-deleted mailbox) is used to retain a former employee's email after he or she leaves your organization. If another employee takes on the job responsibilities of the departed employee or if that employee returns to your organization, there are two ways that you can make the contents of the inactive mailbox available to a user:</span></span> 
  
- <span data-ttu-id="663e6-p102">**還原非使用中的信箱**如果另一位員工採用 departed 員工、 工作職責上或另一位使用者需要存取非使用中信箱的內容，您可以還原 （或合併） 至現有的信箱不在作用中信箱的內容。您也可以從非使用中信箱還原封存。會還原後，非使用中的信箱已受保護而保留為非使用中的信箱。本主題說明的程序還原非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="663e6-p102">**Restore an inactive mailbox** If another employee takes on the job responsibilities of the departed employee, or if another user needs access to the contents of the inactive mailbox, you can restore (or merge) the contents of the inactive mailbox to an existing mailbox. You can also restore the archive from an inactive mailbox. After it's restored, the inactive mailbox is preserved and is retained as an inactive mailbox. This topic describes the procedures for restoring an inactive mailbox.</span></span> 
    
- <span data-ttu-id="663e6-p103">**復原不在作用中的信箱**如果 departed 的員工會傳回您組織中，或將新的員工雇用採取 departed 員工的工作職責，您可以復原不在作用中信箱的內容。此方法會將非使用中信箱轉換成新的信箱包含非作用中信箱的內容。它會復原之後，非使用中的信箱不存在。逐步程序，請參閱[Office 365 中的不在作用中信箱復原](recover-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="663e6-p103">**Recover an inactive mailbox** If the departed employee returns to your organization, or if a new employee is hired to take on the job responsibilities of the departed employee, you can recover the contents of the inactive mailbox. This method converts the inactive mailbox to a new mailbox that contains the contents of the inactive mailbox. After it's recovered, the inactive mailbox no longer exists. For the step-by-step procedures, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
<span data-ttu-id="663e6-114">請參閱如需詳細資訊還原與復原非使用中的信箱之間的差異本文中**的詳細資訊**] 區段。</span><span class="sxs-lookup"><span data-stu-id="663e6-114">See the **More information** section in this article for more details about the differences between restoring and recovering an inactive mailbox.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="663e6-115">開始之前</span><span class="sxs-lookup"><span data-stu-id="663e6-115">Before you begin</span></span>

- <span data-ttu-id="663e6-p104">您必須使用 Exchange Online PowerShell 來還原非使用中的信箱。您無法使用 Exchange 系統管理中心 (EAC)。如需逐步說明，請參閱[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="663e6-p104">You have to use Exchange Online PowerShell to restore an inactive mailbox. You can't use the Exchange admin center (EAC). For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span></span>
    
- <span data-ttu-id="663e6-119">執行下列命令在 Exchange Online PowerShell 取得組織中不在作用中信箱的身分識別資訊。</span><span class="sxs-lookup"><span data-stu-id="663e6-119">Run the following command in Exchange Online PowerShell to get identity information for the inactive mailboxes in your organization.</span></span> 
    
    ```
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

     <span data-ttu-id="663e6-120">使用這個命令所傳回的資訊來還原特定的非使用中信箱。</span><span class="sxs-lookup"><span data-stu-id="663e6-120">Use the information returned by this command to restore a specific inactive mailbox.</span></span>
    
- <span data-ttu-id="663e6-121">如需非使用中信箱的詳細資訊，請參閱[Office 365 中的非使用中信箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="663e6-121">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="restore-an-inactive-mailbox"></a><span data-ttu-id="663e6-122">還原非使用中的信箱</span><span class="sxs-lookup"><span data-stu-id="663e6-122">Restore an inactive mailbox</span></span>

<span data-ttu-id="663e6-p105">搭配_SourceMailbox_和_TargetMailbox_參數的**New-mailboxrestorerequest**指令程式來還原到現有的信箱不在作用中信箱的內容。如需使用此 cmdlet 的詳細資訊，請參閱[New-mailboxrestorerequest](https://go.microsoft.com/fwlink/?linkid=856298)。</span><span class="sxs-lookup"><span data-stu-id="663e6-p105">Use the **New-MailboxRestoreRequest** cmdlet with the  _SourceMailbox_ and  _TargetMailbox_ parameters to restore the contents of an inactive mailbox to an existing mailbox. For more information about using this cmdlet, see [New-MailboxRestoreRequest](https://go.microsoft.com/fwlink/?linkid=856298).</span></span>
  
1. <span data-ttu-id="663e6-125">建立包含非作用中信箱之屬性的變數。</span><span class="sxs-lookup"><span data-stu-id="663e6-125">Create a variable that contains the properties of the inactive mailbox.</span></span> 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="663e6-p106">在上述命令中，使用**DistinguishedName**或**ExchangeGUID**屬性的值來識別非使用中的信箱。這些屬性是唯一的組織中每個信箱，而很可能使用中和非使用中的信箱可能會有相同的主要 SMTP 位址。</span><span class="sxs-lookup"><span data-stu-id="663e6-p106">In the previous command, use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active and an inactive mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="663e6-p107">還原現有的信箱不在作用中信箱的內容。不在作用中的信箱 （來源信箱） 的內容會合併到現有的信箱 （目標信箱） 中所對應的資料夾。</span><span class="sxs-lookup"><span data-stu-id="663e6-p107">Restore the contents of the inactive mailbox to an existing mailbox. The contents of the inactive mailbox (source mailbox) will be merged into the corresponding folders in the existing mailbox (target mailbox).</span></span>
    
    ```
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -AllowLegacyDNMismatch
    ```
   
   <span data-ttu-id="663e6-p108">或者，您可以指定最上層資料夾中用來從非使用中信箱還原內容的目標信箱。如果指定的目標資料夾或目標資料夾結構不存在的目標信箱中，它會建立在還原程序期間。</span><span class="sxs-lookup"><span data-stu-id="663e6-p108">Alternatively, you can specify a top-level folder in the target mailbox in which to restore the contents from the inactive mailbox. If the specified target folder or target folder structure doesn't already exist in the target mailbox, it is created during the restore process.</span></span> 
    
    <span data-ttu-id="663e6-132">此範例會複製的信箱項目從非使用中的信箱至名為 「 不在作用中信箱 」 資料夾的子資料夾中的目標信箱的最上層資料夾結構。</span><span class="sxs-lookup"><span data-stu-id="663e6-132">This example copies mailbox items and subfolders from an inactive mailbox to a folder named "Inactive Mailbox" in the top-level folder structure of the target mailbox.</span></span>
    
   ```
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
   ```
  
## <a name="restore-the-archive-from-an-inactive-mailbox"></a><span data-ttu-id="663e6-133">從非使用中的信箱還原封存</span><span class="sxs-lookup"><span data-stu-id="663e6-133">Restore the archive from an inactive mailbox</span></span>

<span data-ttu-id="663e6-p109">如果不在作用中的信箱已封存信箱，您也可以還原它至現有的信箱的封存信箱。若要從非使用中信箱還原封存，您必須將_SourceIsArchive_和_TargetIsAchive_參數新增至用來還原非使用中信箱的命令。</span><span class="sxs-lookup"><span data-stu-id="663e6-p109">If an inactive mailbox has an archive mailbox, you can also restore it to the archive mailbox of an existing mailbox. To restore the archive from an inactive mailbox, you have to add the  _SourceIsArchive_ and  _TargetIsAchive_ switches to the command used to restore an inactive mailbox.</span></span> 
  
1. <span data-ttu-id="663e6-136">建立包含非作用中信箱之屬性的變數。</span><span class="sxs-lookup"><span data-stu-id="663e6-136">Create a variable that contains the properties of the inactive mailbox.</span></span> 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="663e6-p110">在上述命令中，使用**DistinguishedName**或**ExchangeGUID**屬性的值來識別非使用中的信箱。這些屬性是唯一的組織中每個信箱，而很可能使用中和非使用中的信箱可能會有相同的主要 SMTP 位址。</span><span class="sxs-lookup"><span data-stu-id="663e6-p110">In the previous command, use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active and an inactive mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="663e6-p111">從非使用中的信箱 （來源封存） 的封存的內容還原至現有的信箱 （目標封存） 封存中。在這個範例中，從來源封存的內容會複製到名為 「 不在作用中信箱封存 」 的目標信箱封存中的資料夾。</span><span class="sxs-lookup"><span data-stu-id="663e6-p111">Restore the contents of the archive from the inactive mailbox (source archive) to the archive of an existing mailbox (target archive). In this example, the contents from the source archive are copied to a folder named "Inactive Mailbox Archive" in the archive of the target mailbox.</span></span>

    ```
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -SourceIsArchive -TargetMailbox newemployee@contoso.com -TargetIsArchive -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
    ```

  
## <a name="more-information"></a><span data-ttu-id="663e6-141">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="663e6-141">More information</span></span>

- <span data-ttu-id="663e6-p112">**什麼是復原及還原不在作用中信箱的主要差異？** 當您復原不在作用中的信箱時，信箱基本上會轉換為新的信箱、 保留的內容和非使用中的信箱資料夾結構，及信箱連結至新的使用者帳戶。它復原、 非使用中的信箱不存在，以及對新的信箱中的內容進行任何變更會影響原本的內容之後保留在非使用中的信箱。反之，當您還原非使用中的信箱，內容純粹都會複製到另一個信箱。非使用中的信箱已受保護而會維持不在作用中的信箱。目標信箱中的內容進行任何變更將不會影響保存在非使用中信箱的原始內容。非使用中信箱仍可使用 Office 365 安全性[內容搜尋工具](run-a-content-search-in-the-security-and-compliance-center.md)來搜尋&amp;規範中心及其內容可以還原至另一個信箱或復原或刪除日後。</span><span class="sxs-lookup"><span data-stu-id="663e6-p112">**What's the main difference between recovering and restoring an inactive mailbox?** When you recover an inactive mailbox, the mailbox is basically converted to a new mailbox, the contents and folder structure of the inactive mailbox are retained, and the mailbox is linked to a new user account. After it's recovered, the inactive mailbox no longer exists, and any changes made to the content in the new mailbox will affect the content that was originally on hold in the inactive mailbox. Conversely, when you restore an inactive mailbox, the contents are merely copied to another mailbox. The inactive mailbox is preserved and remains an inactive mailbox. Any changes made to the content in the target mailbox won't affect the original content held in the inactive mailbox. The inactive mailbox can still be searched by using the [Content Search tool](run-a-content-search-in-the-security-and-compliance-center.md) in the Office 365 Security &amp; Compliance Center, its contents can be restored to another mailbox, or it can be recovered or deleted at a later date.</span></span> 
    
- <span data-ttu-id="663e6-p113">**如何尋找非使用中信箱？** 若要取得組織中不在作用中信箱的清單和顯示還原非使用中信箱的有用的資訊，您可以執行此命令。</span><span class="sxs-lookup"><span data-stu-id="663e6-p113">**How do you find inactive mailboxes?** To get a list of the inactive mailboxes in your organization and display information that is useful for restoring an inactive mailbox, you can run this command.</span></span> 

  ```
  Get-Mailbox -InactiveMailboxOnly | FL Name,PrimarySMTPAddress,DistinguishedName,ExchangeGUID,LegacyExchangeDN,ArchiveStatus
  ```

- <span data-ttu-id="663e6-p114">**使用訴訟暫止狀態或 Office 365 保留原則來保留非使用中信箱內容。** 如果您想要還原後保留的非使用中的信箱狀態，您可以置於目標信箱[訴訟暫止狀態](https://go.microsoft.com/fwlink/?linkid=856286)或[Office 365 保留原則](retention-policies.md)套用之前還原非使用中的信箱。如此可防止從非使用中信箱的所有項目永久刪除之後所要還原的目標信箱。</span><span class="sxs-lookup"><span data-stu-id="663e6-p114">**Use a Litigation Hold or Office 365 retention policy to retain inactive mailbox content.** If you want to retain the state of an inactive mailbox after it's restored, you can place the target mailbox on [Litigation Hold](https://go.microsoft.com/fwlink/?linkid=856286) or apply an [Office 365 retention policy](retention-policies.md) before you restore the inactive mailbox. This will prevent the permanent deletion of any items from the inactive mailbox after they're restored to the target mailbox.</span></span> 
    
- <span data-ttu-id="663e6-p115">**啟用保留目標信箱上再還原非使用中的信箱。** 從非使用中信箱的信箱項目可能是舊，因為您可能會考慮之前還原非使用中的信箱啟用目標信箱的保留。當您將放上保留信箱保留，直到移除保留或直到保留期間到期將不會處理保留原則指派給它。這可讓管理舊郵件從非使用中信箱擁有者的目標信箱時間。否則請保留原則可能會刪除舊項目 （或將項目移至封存信箱，如果已啟用） 已過期根據目標信箱的保留設定。如需詳細資訊，請參閱[就地保留信箱保留在 Exchange Online](https://go.microsoft.com/fwlink/?linkid=856300)。</span><span class="sxs-lookup"><span data-stu-id="663e6-p115">**Enable retention hold on the target mailbox before you restore an inactive mailbox.** Because mailbox items from an inactive mailbox could be old, you might consider enabling retention hold on the target mailbox before you restore an inactive mailbox. When you put a mailbox on retention hold, the retention policy that's assigned to it won't be processed until the retention hold is removed or until the retention hold period expires. This gives the owner of the target mailbox time to manage old messages from the inactive mailbox. Otherwise, the retention policy might delete old items (or move items to the archive mailbox, if it's enabled) that have expired based on the retention settings configured for the target mailbox. For more information, see [Place a mailbox on retention hold in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856300).</span></span>
    
- <span data-ttu-id="663e6-p116">**AllowLegacyDNMismatch 交換器做什麼？** 在要還原的非使用中的信箱上一個範例中， **AllowLegacyDNMismatch**參數用來允許不在作用中信箱還原至不同的目標信箱。在一般還原案例中，目標是要還原的內容來源和目標信箱位於相同的信箱的位置。因此預設會**New-mailboxrestorerequest**指令程式會檢查確定來源與目標信箱上的**LegacyExchangeDN**屬性的值相同。這可幫助會防止您意外錯誤的目標信箱將還原的來源信箱。如果您嘗試還原非使用中的信箱，而不使用**AllowLegacyDNMismatch**參數，如果來源與目標信箱有不同屬性的值**LegacyExchangeDN**命令可能會失敗。</span><span class="sxs-lookup"><span data-stu-id="663e6-p116">**What does the AllowLegacyDNMismatch switch do?** In the previous examples to restore an inactive mailbox, the **AllowLegacyDNMismatch** switch is used to allow restoring the inactive mailbox to a different target mailbox. In a typical restore scenario, the goal is to restore content where the source and target mailboxes are the same mailbox. So by default, the **New-MailboxRestoreRequest** cmdlet checks to make sure that the value of the **LegacyExchangeDN** property on the source and target mailboxes is the same. This helps prevents you from accidentally restoring a source mailbox into the wrong target mailbox. If you try to restore an inactive mailbox without using the **AllowLegacyDNMismatch** switch, the command might fail if the source and target mailboxes have different values for the **LegacyExchangeDN** property.</span></span> 
    
- <span data-ttu-id="663e6-p117">**您可以使用其他參數使用 New-mailboxrestorerequest 指令程式來實作的非使用中信箱的不同還原案例。** 例如，您可以執行此命令以從非使用中信箱的封存還原成的目標信箱的主要信箱。</span><span class="sxs-lookup"><span data-stu-id="663e6-p117">**You can use other parameters with the New-MailboxRestoreRequest cmdlet to implement different restore scenarios for inactive mailboxes.** For example, you can run this command to restore the archive from the inactive mailbox into the primary mailbox of the target mailbox.</span></span> 
    
  ```
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -SourceIsArchive -TargetMailbox <target mailbox> -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
  ```

  <span data-ttu-id="663e6-168">您也可以還原至的目標信箱封存的非使用中的主要信箱執行此命令。</span><span class="sxs-lookup"><span data-stu-id="663e6-168">You can also restore the inactive primary mailbox into the archive of the target mailbox by running this command.</span></span>

  ```
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -TargetMailbox <target mailbox> -TargetIsArchive -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
  ```

- <span data-ttu-id="663e6-p118">**執行 TargetRootFolder 參數執行什麼？** 如先前所述，您可以使用**TargetRootFolder**參數來指定資料夾中 （也稱為根目錄） 的資料夾結構的頂端在要還原的非使用中信箱內容的目標信箱。如果您未使用此參數，從非使用中信箱的信箱項目已合併成對應的預設資料夾的目標信箱，以及自訂資料夾的根目錄的目標信箱中重新建立。下圖反白顯示這些未使用和使用**TargetRootFolder**參數之間的差異。</span><span class="sxs-lookup"><span data-stu-id="663e6-p118">**What does the TargetRootFolder parameter do?** As previously explained, you can use the **TargetRootFolder** parameter to specify a folder in the top of the folder structure (also called the root) in the target mailbox in which to restore the contents of the inactive mailbox. If you don't use this parameter, mailbox items from the inactive mailbox are merged into the corresponding default folders of the target mailbox, and custom folders are re-created in the root of the target mailbox. The following illustrations highlight these differences between not using and using the **TargetRootFolder** parameter.</span></span> 
    
    <span data-ttu-id="663e6-173">**目標信箱時不會使用 TargetRootFolder 參數中的資料夾階層**</span><span class="sxs-lookup"><span data-stu-id="663e6-173">**Folder hierarchy in the target mailbox when the TargetRootFolder parameter isn't used**</span></span>
    
    ![未使用 TargetRootFolder 參數時的螢幕擷取畫面](media/76a759af-f483-4d1c-8cc7-243435b5562e.png)
  
    <span data-ttu-id="663e6-175">**在 [目標信箱 TargetRootFolder 參數使用時的資料夾階層**</span><span class="sxs-lookup"><span data-stu-id="663e6-175">**Folder hierarchy in the target mailbox when the TargetRootFolder parameter is used**</span></span>
    
    ![使用 TargetRootFolder 參數時的螢幕擷取畫面](media/300da592-7323-48db-b8a4-07012259d113.png)

  

