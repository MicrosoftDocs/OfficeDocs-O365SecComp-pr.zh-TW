---
title: 置於就地保留虛刪除的信箱在 Exchange Online
ms.author: markjjo
author: markjjo
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
description: 了解如何建立就地保留虛刪除信箱進行非使用中並保留其內容。 然後您可以使用 Microsoft eDiscovery 工具來搜尋非使用中信箱。
ms.openlocfilehash: ce4121e6187a765b5a9e23d6e6e11d8cc2640161
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34157275"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a>置於就地保留虛刪除的信箱在 Exchange Online

了解如何建立就地保留虛刪除信箱進行非使用中並保留其內容。 然後您可以使用 Microsoft eDiscovery 工具來搜尋非使用中信箱。
  
> [!NOTE]
> 我們已建立新的就地保留在 Exchange Online （在 Office 365 和 Exchange Online 獨立計劃） 的期限延後。 但到今年年底或明年年初，您將無法在 Exchange Online 中建立新的「就地保留」。 改成使用就地保留，您可以使用安全性 & 合規性中心中的[eDiscovery 案例](https://go.microsoft.com/fwlink/?linkid=780738)或[保留原則](https://go.microsoft.com/fwlink/?linkid=827811)。 我們解除委任新就地保留之後，您仍然可以修改現有的就地保留，並建立新的就地保留在 Exchange Server 2013 和 Exchange 混合式部署仍會支援。 然後您仍然可以將信箱設為訴訟暫止。 
  
您可能需要其中人員已離開您的組織和其對應的使用者帳戶和信箱已刪除的情況。 之後，您要瞭解沒有需要保留信箱中的資訊。 您可以做什麼？ 如果尚未過期刪除的信箱保留期間，您可以置於就地保留已刪除的信箱 （稱為 「 虛刪除的信箱），並使其不在作用中的信箱。 *非使用中信箱*用於他或她離開組織之後保留離職員工的電子郵件。 如已為 「 就地保留的持續時間處於虛刪除的信箱已進行非使用中時，會保留不在作用中信箱的內容。 信箱進行非使用中之後，您可以使用 Exchange Online、 安全 & 與規範中心中，內容搜尋] 或 [SharePoint Online 中的 eDiscovery 中心中的 「 就地 eDiscovery 來搜尋信箱。 
  
> [!NOTE]
> 在 Exchange Online 中，將虛刪除的信箱會是已刪除，但可以在特定的保留期間內可復原的信箱。 Exchange Online 中的虛刪除信箱保留期間是 30 天。 這表示信箱可以復原 （或進行非使用中信箱） 的被刪除的 30 天內。 30 天後，虛刪除的信箱標示為永久刪除和無法復原或進行非使用中。 
  
## <a name="before-you-begin"></a>開始之前

- 您必須使用 Windows PowerShell 中的**New-mailboxsearch** cmdlet，將放在虛刪除的信箱上的 [就地保留。 您無法使用 Exchange 系統管理中心 (EAC) 或 SharePoint Online 中的 eDiscovery 中心。 
    
- 若要了解如何使用 Windows PowerShell 連線到 Exchange Online，請參閱[連線到 Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。
    
- 執行下列命令，以取得貴組織中的虛刪除信箱的身分識別資訊。 
    
  ```
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- 如需非使用中信箱的詳細資訊，請參閱 < <b0>Overview of Office 365 中的非使用中信箱</b0>。
    
## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a>放在虛刪除的信箱，使其成為非使用中信箱上的 [就地保留

使用**New-mailboxsearch** cmdlet 將虛刪除的信箱不在作用中的信箱。 如需詳細資訊，請參閱[New-mailboxsearch](http://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx)。
  
1. 建立包含變數，虛刪除信箱的內容。 
    
   ```
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > 在上述命令中，使用 [ **DistinguishedName** ] 或 [ **ExchangeGuid**屬性的值來識別虛刪除的信箱。 這些屬性是唯一的組織中每個信箱，而是可能作用中信箱和虛刪除的信箱可能會有相同的主要 SMTP 位址。 
  
2. 建立就地保留，並將它放在虛刪除的信箱。 在這個範例中，會指定不保留持續時間。 這表示項目將會無限期保留或直到從非使用中信箱移除保留為止。
    
   ```
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```
   您也可以指定當您建立就地保留將保留持續時間。 本範例會保留在作用中信箱項目大約 7 年。
    
   ```
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. 在一段時間之後執行下列其中一個下列命令，以確認虛刪除的信箱不在作用中的信箱。
    
   ```
   Get-Mailbox -InactiveMailboxOnly
   ```

    或
    
   ```
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a>詳細資訊

之後，請將虛刪除的信箱不在作用中信箱有多種方式可以管理信箱。 如需詳細資訊，請參閱：
  
- [變更非使用中信箱的保留期間](change-the-hold-duration-for-an-inactive-mailbox.md)
    
- [復原非使用中的信箱](recover-an-inactive-mailbox.md)
    
- [還原非使用中的信箱](restore-an-inactive-mailbox.md)
    
- [刪除非使用中信箱](delete-an-inactive-mailbox.md)（藉由移除保留）
