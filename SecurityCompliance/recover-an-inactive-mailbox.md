---
title: 復原 Office 365 中不在作用中信箱
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/21/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 35d0ecdb-7cb0-44be-ad5c-69df2f8f8b25
description: '如果先前的員工會傳回您組織中，或將新的員工雇用採取 departed 員工的工作職責，您可以復原 Office 365 中的非使用中信箱的內容。當您復原不在作用中的信箱時，它會轉換成新的信箱包含非作用中信箱的內容。 '
ms.openlocfilehash: bebcf5cbb569c9e2e591294a084defea15af4c0f
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216133"
---
# <a name="recover-an-inactive-mailbox-in-office-365"></a><span data-ttu-id="aa29b-104">復原 Office 365 中不在作用中信箱</span><span class="sxs-lookup"><span data-stu-id="aa29b-104">Recover an inactive mailbox in Office 365</span></span>

<span data-ttu-id="aa29b-p102">（這是一種虛刪除信箱） 的非使用中信箱用來保留先前員工的電子郵件之後他離開貴組織。如果該員工會傳回您組織或另一位員工則是在先前的員工的工作職責上，有兩種方式您可以決定將非使用中信箱的內容提供給使用者：</span><span class="sxs-lookup"><span data-stu-id="aa29b-p102">An inactive mailbox (which is a type of soft-deleted mailbox) is used to preserve a former employee's email after he or she leaves your organization. If that employee returns to your organization or if another employee takes on the job responsibilities of the former employee, there are two ways that you can make the contents of the inactive mailbox available to a user:</span></span> 
  
- <span data-ttu-id="aa29b-p103">**復原不在作用中的信箱**如果先前的員工會傳回您組織中，或將新的員工雇用才會在先前的員工的工作職責，您可以復原不在作用中信箱的內容。此方法會將非使用中信箱轉換至新的作用中信箱包含非作用中信箱的內容。它會復原之後，非使用中的信箱不存在。本主題中的程序說明此方法。</span><span class="sxs-lookup"><span data-stu-id="aa29b-p103">**Recover an inactive mailbox** If the former employee returns to your organization, or if a new employee is hired to take on the job responsibilities of the former employee, you can recover the contents of the inactive mailbox. This method converts the inactive mailbox to a new, active mailbox that contains the contents of the inactive mailbox. After it's recovered, the inactive mailbox no longer exists. The procedures in this topic describe this method.</span></span> 
    
- <span data-ttu-id="aa29b-p104">**還原非使用中的信箱**如果另一位員工採用在先前的員工、 工作職責或另一位使用者需要存取非使用中信箱的內容，您可以還原 （或合併） 至現有的信箱不在作用中信箱的內容。您也可以從非使用中信箱還原封存。此方法的程序，請參閱[還原 Office 365 中的非使用中信箱](restore-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="aa29b-p104">**Restore an inactive mailbox** If another employee takes on the job responsibilities of the former employee, or if another user needs access to the contents of the inactive mailbox, you can restore (or merge) the contents of the inactive mailbox to an existing mailbox. You can also restore the archive from an inactive mailbox. For the procedures for this method, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>
    
<span data-ttu-id="aa29b-114">請參閱[的詳細資訊](recover-an-inactive-mailbox.md#moreinfo)] 區段中復原與還原為非作用中信箱之間差異的詳細資訊與復原非使用中的信箱時會發生什麼情況的描述。</span><span class="sxs-lookup"><span data-stu-id="aa29b-114">See the [More information](recover-an-inactive-mailbox.md#moreinfo) section for more details about the differences between recovering and restoring an inactive mailbox, and for a description of what happens when an inactive mailbox is recovered.</span></span>
  
> [!NOTE]
> <span data-ttu-id="aa29b-p105">我們已延遲就地保留來讓信箱成為非使用中新建立的期限。但在某些未來，您將不能夠新就地保留 Exchange Online 中建立。該次僅訴訟保留與 Office 365 的保留原則可用來建立非使用中的信箱。不過，仍會支援現有的非使用中信箱上就地保留，而您可以繼續管理非使用中的信箱上的就地保留。這包括變更為 「 就地保留持續時間和永久刪除非使用中的信箱移除就地保留 」 狀態。</span><span class="sxs-lookup"><span data-stu-id="aa29b-p105">We've postponed the deadline for creating new In-Place Holds to make a mailbox inactive. But at some point in the future, you won't be able to create new In-Place Holds in Exchange Online. At that time, only Litigation Holds and Office 365 retention policies can be used to create an inactive mailbox. However, existing inactive mailboxes that are on In-Place Hold will still be supported, and you can continue to manage the In-Place Holds on inactive mailboxes. This includes changing the duration of an In-Place Hold and permanently deleting an inactive mailbox by removing the In-Place Hold.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="aa29b-120">開始之前</span><span class="sxs-lookup"><span data-stu-id="aa29b-120">Before you begin</span></span>

- <span data-ttu-id="aa29b-p106">您必須使用 Exchange Online PowerShell 來還原非使用中的信箱。您無法使用 Exchange 系統管理中心 (EAC)。如需逐步說明，請參閱[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="aa29b-p106">You have to use Exchange Online PowerShell to restore an inactive mailbox. You can't use the Exchange admin center (EAC). For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span></span>
    
- <span data-ttu-id="aa29b-124">執行下列命令以取得組織中不在作用中信箱的身分識別資訊。</span><span class="sxs-lookup"><span data-stu-id="aa29b-124">Run the following command to get identity information for the inactive mailboxes in your organization.</span></span> 

    ```
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

    <span data-ttu-id="aa29b-125">使用這個命令所傳回的資訊來復原特定的非使用中信箱。</span><span class="sxs-lookup"><span data-stu-id="aa29b-125">Use the information returned by this command to recover a specific inactive mailbox.</span></span>
    
- <span data-ttu-id="aa29b-126">如需非使用中信箱的詳細資訊，請參閱[Office 365 中的非使用中信箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="aa29b-126">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="recover-an-inactive-mailbox"></a><span data-ttu-id="aa29b-127">復原非使用中的信箱</span><span class="sxs-lookup"><span data-stu-id="aa29b-127">Recover an inactive mailbox</span></span>

<span data-ttu-id="aa29b-128">搭配*InactiveMailbox*參數的**New-mailbox**指令程式來復原不在作用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="aa29b-128">Use the **New-Mailbox** cmdlet with the  *InactiveMailbox*  parameter to recover an inactive mailbox.</span></span> 
  
1. <span data-ttu-id="aa29b-129">建立包含非作用中信箱之屬性的變數。</span><span class="sxs-lookup"><span data-stu-id="aa29b-129">Create a variable that contains the properties of the inactive mailbox.</span></span> 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```
   
    > [!IMPORTANT]
    > <span data-ttu-id="aa29b-p107">在上述命令中，使用**DistinguishedName**或**ExchangeGUID**屬性的值來識別非使用中的信箱。這些屬性是唯一的組織中每個信箱，而很可能使用中和非使用中的信箱可能會有相同的主要 SMTP 位址。</span><span class="sxs-lookup"><span data-stu-id="aa29b-p107">In the previous command, use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active and an inactive mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="aa29b-p108">本範例會使用在上一個命令中取得的內容並復原到 Ann Beebe 的使用者使用中信箱不在作用中的信箱。是確定組織內唯一的*名稱*和*MicrosoftOnlineServicesID*參數指定值。</span><span class="sxs-lookup"><span data-stu-id="aa29b-p108">This example uses the properties obtained in the previous command and recovers the inactive mailbox to an active mailbox for the user Ann Beebe. Be sure that the values specified for the  *Name*  and  *MicrosoftOnlineServicesID*  parameters are unique within your organization.</span></span> 

    ```
    New-Mailbox -InactiveMailbox $InactiveMailbox.DistinguishedName -Name annbeebe -FirstName Ann -LastName Beebe -DisplayName "Ann Beebe" -MicrosoftOnlineServicesID Ann.Beebe@contoso.com -Password (ConvertTo-SecureString -String 'P@ssw0rd' -AsPlainText -Force) -ResetPasswordOnNextLogon $true
    ```

    <span data-ttu-id="aa29b-134">為要復原的非使用中信箱的主要 SMTP 位址必須*MicrosoftOnlineServicesID*參數所指定的一個相同的值。</span><span class="sxs-lookup"><span data-stu-id="aa29b-134">The primary SMTP address for the recovered inactive mailbox will have the same value as the one specified by the  *MicrosoftOnlineServicesID*  parameter.</span></span> 
    
<span data-ttu-id="aa29b-p109">不在作用中的信箱復原之後，也會建立新的 Office 365 使用者帳戶。您必須將授權指派啟動此使用者帳戶。若要指派 Office 365 系統管理中心中的授權，請參閱[指派或取消指派 Office 365 企業版授權](https://go.microsoft.com/fwlink/p/?LinkId=276798)。</span><span class="sxs-lookup"><span data-stu-id="aa29b-p109">After you recover an inactive mailbox, a new Office 365 user account is also created. You have to activate this user account by assigning a license. To assign a license in the Office 365 admin center, see [Assign or unassign licenses for Office 365 for business](https://go.microsoft.com/fwlink/p/?LinkId=276798).</span></span>
  
## <a name="more-information"></a><span data-ttu-id="aa29b-138">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="aa29b-138">More information</span></span>

- <span data-ttu-id="aa29b-p110">**什麼是復原及還原不在作用中信箱的主要差異？** 當您復原不在作用中的信箱時，信箱基本上會轉換為新的信箱、 保留的內容和非使用中的信箱資料夾結構，及信箱連結至新的使用者帳戶。它復原、 非使用中的信箱不存在，以及對新的信箱中的內容進行任何變更會影響原本的內容之後保留在非使用中的信箱。反之，當您還原非使用中的信箱，內容純粹都會複製到另一個信箱。非使用中的信箱已受保護而會維持不在作用中的信箱。目標信箱中的內容進行任何變更將不會影響保存在非使用中信箱的原始內容。非使用中信箱仍可使用就地 eDiscovery 搜尋、 其內容可以還原至另一個信箱或復原或刪除日後。</span><span class="sxs-lookup"><span data-stu-id="aa29b-p110">**What's the main difference between recovering and restoring an inactive mailbox?** When you recover an inactive mailbox, the mailbox is basically converted to a new mailbox, the contents and folder structure of the inactive mailbox are retained, and the mailbox is linked to a new user account. After it's recovered, the inactive mailbox no longer exists, and any changes made to the content in the new mailbox will affect the content that was originally on hold in the inactive mailbox. Conversely, when you restore an inactive mailbox, the contents are merely copied to another mailbox. The inactive mailbox is preserved and remains an inactive mailbox. Any changes made to the content in the target mailbox won't affect the original content held in the inactive mailbox. The inactive mailbox can still be searched by using In-Place eDiscovery, its contents can be restored to another mailbox, or it can be recovered or deleted at a later date.</span></span> 
    
- <span data-ttu-id="aa29b-p111">**不在作用中的信箱復原時會發生什麼情況？** 當您復原不在作用中的信箱時，便會發生下列事項：</span><span class="sxs-lookup"><span data-stu-id="aa29b-p111">**What happens when you recover an inactive mailbox?** When you recover an inactive mailbox, the following things occur:</span></span> 
    
  - <span data-ttu-id="aa29b-148">已移除訴訟資料暫留 （如果已啟用非作用中信箱）。</span><span class="sxs-lookup"><span data-stu-id="aa29b-148">Litigation Hold (if it was enabled for the inactive mailbox) is removed.</span></span>
    
  - <span data-ttu-id="aa29b-p112">會移除就地保留。這表示不在作用中信箱以任何在暫止或就地 eDiscovery 搜尋中來源信箱移除。</span><span class="sxs-lookup"><span data-stu-id="aa29b-p112">In-Place Holds are removed. This means that the inactive mailbox is removed as a source mailbox from any In-Place Hold or In-Place eDiscovery searches.</span></span> 
    
  - <span data-ttu-id="aa29b-151">非使用中的信箱已從任何 Office 365 的保留原則移除該位置套用。</span><span class="sxs-lookup"><span data-stu-id="aa29b-151">The inactive mailbox is removed from any Office 365 retention policies that where applied to it.</span></span>
    
  - <span data-ttu-id="aa29b-p113">（這**RetainDeletedItemsFor**信箱屬性所定義） 的單一項目復原期間設為 30 天。一般而言，新的信箱建立時在 Exchange Online，此保留期間設為 14 天。這個設定設為 30 天的最大值可讓您更多時間以復原任何已永久刪除 （或清除） 的資料從非使用中的信箱。您也可以停用單一項目復原或設定單一項目復原期間回到預設值為 14 天。如需詳細資訊，請參閱[啟用或停用單一項目復原的信箱](https://go.microsoft.com/fwlink/?linkid=856769)。</span><span class="sxs-lookup"><span data-stu-id="aa29b-p113">The single item recovery period (which is defined by the **RetainDeletedItemsFor** mailbox property) is set to 30 days. Typically, when a new mailbox is created in Exchange Online, this retention period is set to 14 days. Setting this to the maximum value of 30 days gives you more time to recover any data that's been permanently deleted (or purged) from the inactive mailbox. You can also disable single item recovery or set the single item recovery period back to the default of 14 days. For more information, see [Enable or disable single item recovery for a mailbox](https://go.microsoft.com/fwlink/?linkid=856769).</span></span>
    
  - <span data-ttu-id="aa29b-p114">已啟用保留功能，並保留保留持續時間設為 30 天。這表示預設 Exchange 保留原則和指派給新的信箱的保留原則不會處理 30 天的任何整個組織或 Exchange 全 Office 365。這可讓傳回員工或非使用中的信箱復原的時間的新擁有人管理舊郵件。否則請 Exchange 或 Office 365 保留原則可能會刪除舊的信箱項目 （或將項目移至封存信箱，如果已啟用） 已過期根據設定 Exchange 或 Office 365 保留原則的設定。30 天後保留過期**RetentionHoldEnabled**信箱屬性設為**False**，且受管理的資料夾助理員開始處理指派給信箱的原則。如果您不需要此額外的時間，您可以只移除保留功能。或者，您可以使用**Set-mailbox EndDateForRetentionHold**命令增加保留持續的時間。如需詳細資訊，請參閱[就地保留信箱保留 」 狀態](https://go.microsoft.com/fwlink/?linkid=856300)。</span><span class="sxs-lookup"><span data-stu-id="aa29b-p114">Retention hold is enabled, and the retention hold duration is set to 30 days. This means that the default Exchange retention policy and any organization-wide or Exchange-wide Office 365 retention policies that are assigned to the new mailbox won't be processed for 30 days. This gives the returning employee or the new owner of the recovered inactive mailbox time to manage the old messages. Otherwise, the Exchange or Office 365 retention policy might delete old mailbox items (or move items to the archive mailbox, if it's enabled) that have expired based on the settings configured for the Exchange or Office 365 retention policies. After 30 days, the retention hold expires, the **RetentionHoldEnabled** mailbox property is set to **False**, and the Managed Folder Assistant starts processing the policies assigned to the mailbox. If you don't need this additional time, you can just remove the retention hold. Alternatively, you can increase the duration of the retention hold by using the **Set-Mailbox -EndDateForRetentionHold** command. For more information, see [Place a mailbox on retention hold](https://go.microsoft.com/fwlink/?linkid=856300).</span></span>
    
- <span data-ttu-id="aa29b-p115">**復原的信箱上設定保留，若您要保留的非使用中信箱的原始狀態。** 若要防止永久刪除任何郵件從要復原的非使用中信箱的新信箱擁有者或保留原則，您可以信箱置於訴訟保留的詳細資訊，請參閱[Place 在訴訟暫止狀態的信箱](https://go.microsoft.com/fwlink/?linkid=856286)。</span><span class="sxs-lookup"><span data-stu-id="aa29b-p115">**Put a hold on the recovered mailbox if you need to preserve the original state of the inactive mailbox.** To prevent the new mailbox owner or retention policy from permanently deleting any messages from the recovered inactive mailbox, you can place the mailbox on Litigation Hold For more information, see [Place a mailbox on Litigation Hold](https://go.microsoft.com/fwlink/?linkid=856286).</span></span>
    
- <span data-ttu-id="aa29b-p116">**哪些使用者識別碼可以使用時的復原不在作用中的信箱？** 當您復原不在作用中的信箱時，您為*MicrosoftOnlineServicesID*參數指定的值可以是與原始一個非使用中的信箱與關聯的不同。您也可以使用原始使用者識別碼。但先前所述，確認*名稱*] 和 [ *MicrosoftOnlineServicesID*所用的值是唯一組織內時復原不在作用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="aa29b-p116">**What user ID can you use when recovering an inactive mailbox?** When you recover an inactive mailbox, the value that you specify for the  *MicrosoftOnlineServicesID*  parameter can be different from the original one that was associated with the inactive mailbox. You can also use the original user ID. But as previously stated, make sure that the values used for  *Name*  and  *MicrosoftOnlineServicesID*  are unique within your organization when you recover the inactive mailbox.</span></span> 
    
- <span data-ttu-id="aa29b-p117">**不在作用中信箱的信箱保留期間尚未過期怎麼辦吗？** 如果不在作用中的信箱虛刪除早於 30 天，您無法復原它使用**New-mailbox InactiveMailbox**命令。您必須復原來還原對應的 Office 365 使用者帳戶。如需詳細資訊，請參閱[刪除或還原使用者](https://go.microsoft.com/fwlink/p/?LinkId=279162)。</span><span class="sxs-lookup"><span data-stu-id="aa29b-p117">**What if the mailbox retention period for the inactive mailbox hasn't expired?** If an inactive mailbox was soft-deleted less than 30 days ago, you can't use the **New-Mailbox -InactiveMailbox** command to recover it. You have to recover it by restoring the corresponding Office 365 user account. For more information, see [Delete or restore users](https://go.microsoft.com/fwlink/p/?LinkId=279162).</span></span>
    
- <span data-ttu-id="aa29b-p118">**如何知道不在作用中信箱的虛刪除信箱保留期間是否已經過期？** 執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="aa29b-p118">**How do you know if the soft-deleted mailbox retention period for an inactive mailbox has expired?** Run the following command.</span></span> 
    
    ```
    Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | FL ExternalDirectoryObjectId
  ```

    <span data-ttu-id="aa29b-p119">如果沒有**ExternalDirectoryObjectId**屬性的值，信箱保留期間內已過期，以及您可以執行**New-mailbox InactiveMailbox**命令來復原不在作用中的信箱。如果沒有**ExternalDirectoryObjectId**屬性的值，虛刪除信箱保留期間尚未過期，且必須復原信箱還原 Office 365 使用者帳戶。請參閱[刪除或還原使用者](https://go.microsoft.com/fwlink/p/?LinkId=279162)</span><span class="sxs-lookup"><span data-stu-id="aa29b-p119">If there isn't a value for the **ExternalDirectoryObjectId** property, the mailbox retention period has expired, and you can recover the inactive mailbox by running the **New-Mailbox -InactiveMailbox** command. If there is a value for the **ExternalDirectoryObjectId** property, the soft-deleted mailbox retention period hasn't expired and you have to recover the mailbox by restoring the Office 365 user account. See [Delete or restore users](https://go.microsoft.com/fwlink/p/?LinkId=279162)</span></span>
    
- <span data-ttu-id="aa29b-p120">**不在作用中的信箱復原之後啟用封存信箱的考量事項。** 這可讓您傳回使用者或新員工將舊郵件移至封存信箱。與時保留過期的封存原則屬於預設 Exchange 保留原則指派給 Exchange Online 信箱移相關的兩個年度的項目或較舊的封存信箱。如果您不要啟用封存信箱，超過兩個年度的項目將會保留在使用者的主要信箱。如需詳細資訊，請參閱[啟用封存信箱在 Office 365 安全性&amp;規範中心](enable-archive-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="aa29b-p120">**Consider enabling the archive mailbox after you recover an inactive mailbox.** This lets the returning user or new employee move old messages to the archive mailbox. And when the retention hold expires, the archive policy that is part of the default Exchange retention policy assigned to Exchange Online mailboxes will move items that are two years or older to the archive mailbox. If you don't enable the archive mailbox, items older than two years will remain in the user's primary mailbox. For more information, see [Enable archive mailboxes in the Office 365 Security &amp; Compliance Center](enable-archive-mailboxes.md).</span></span>
 