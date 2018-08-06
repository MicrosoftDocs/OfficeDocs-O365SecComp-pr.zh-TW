---
title: 置於就地保留虛刪除信箱在 Exchange Online
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/18/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
description: 了解如何建立就地保留虛刪除信箱以進行非使用中並保留其內容。然後您可以使用 Microsoft eDiscovery 工具來搜尋非使用中的信箱。
ms.openlocfilehash: 226929764fe39b99f526301029d4a41e2fa486cc
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027610"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a>置於就地保留虛刪除信箱在 Exchange Online

了解如何建立就地保留虛刪除信箱以進行非使用中並保留其內容。然後您可以使用 Microsoft eDiscovery 工具來搜尋非使用中的信箱。
  
> [!NOTE]
> 我們已延遲 2017 年 7 月 1、 到達期限時建立的新就地保留在 Exchange Online （在 Office 365 和 Exchange Online 獨立計劃）。但是稍後今年或早期明年您將無法建立新就地保留在 Exchange Online。若要使用就地保留或者，您可以使用[eDiscovery 案例](https://go.microsoft.com/fwlink/?linkid=780738)或[保留原則](https://go.microsoft.com/fwlink/?linkid=827811)Office 365 安全性&amp;規範中心。我們解除委任新就地保留之後，您將仍然可以修改現有的就地保留，並建立新的就地保留在 Exchange Server 2013 和 Exchange 混合部署將仍然支援。然後您仍必須能夠將信箱設為在訴訟暫止狀態。 
  
您可能必須在其中人員會靠左您的組織和其對應的使用者帳戶和信箱已刪除的情況。之後，您了解有需要保留信箱中的資訊。您可以執行什麼動作？如果尚未過期的已刪除的信箱保留期間，您可以置於就地保留已刪除的信箱 （稱為 「 虛刪除信箱） 並使其不在作用中的信箱。*非使用中信箱*用來保留先前員工的電子郵件之後他離開貴組織。不在作用中信箱的內容會保留的持續時間內所就地保留處於虛刪除信箱時上次進行非使用中。進行不在作用中信箱之後，您可以在 Exchange Online 中，Office 365 安全性內容搜尋使用就地 eDiscovery 搜尋信箱&amp;規範中心或 SharePoint Online 中的 eDiscovery 中心。 
  
> [!NOTE]
> 在 Exchange Online 虛刪除信箱是已遭刪除，但在特定的保留期間內可復原的信箱。Exchange Online 中的虛刪除信箱保留期間是 30 天。這表示可以信箱復原 （或進行非使用中的信箱） 的要刪除的 30 天內。30 天後虛刪除信箱標記為永久刪除和無法復原或進行非使用中。 
  
## <a name="before-you-begin"></a>開始之前
<a name="sectionSection0"> </a>

- 您必須在 Windows PowerShell 中使用**New-mailboxsearch**指令程式將放在虛刪除信箱上的 [就地保留。您無法使用 Exchange 系統管理中心 (EAC) 或 SharePoint Online 中的 eDiscovery 中心。 
    
- 若要了解如何使用 Windows PowerShell 連線到 Exchange Online，請參閱[連線到 Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。
    
- 執行下列命令以取得組織中的虛刪除信箱的身分識別資訊。 
    
  ```
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- 如需非使用中信箱的詳細資訊，請參閱[Exchange Online 中的非使用中信箱](http://technet.microsoft.com/library/2f2948c5-1c5a-4643-865c-b36e4ac1414b.aspx)。
    
## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a>放虛刪除信箱使其成為非使用中的信箱上的 [就地保留
<a name="sectionSection1"> </a>

使用**New-mailboxsearch** cmdlet 可讓虛刪除信箱成為非使用中的信箱。如需詳細資訊，請參閱[New-mailboxsearch](http://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx)。
  
1. 建立包含虛刪除信箱之屬性的變數。 
    
  ```
  $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
  ```

    > [!IMPORTANT]
    > 在上述命令中，使用**DistinguishedName**或**ExchangeGuid**屬性的值來識別虛刪除信箱。這些屬性是唯一的組織中每個信箱，而很可能使用中的信箱及虛刪除信箱可能會有相同的主要 SMTP 位址。 
  
2. 建立就地保留和放在虛刪除信箱。在這個範例中，會指定不保留持續時間。這表示項目將會保留無限期或直到撤除從非使用中的信箱。
    
  ```
  New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
  
  ```

    您也可以指定當您建立就地保留保留持續時間。本範例會包含一個項目不在作用中的信箱中大約 7 年。
    
  ```
  New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
  ```

3. 在一段時間後執行下列命令來確認虛刪除信箱不在作用中信箱的其中一個。
    
  ```
  Get-Mailbox -InactiveMailboxOnly
  ```

    或
    
  ```
  Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
  ```

## <a name="more-information"></a>其他資訊
<a name="sectionSection2"> </a>

進行虛刪除信箱不在作用中的信箱後，有數種方式可以管理信箱。如需詳細資訊，請參閱：
  
- [變更 Exchange Online 中不在作用中信箱的保留期間](http://technet.microsoft.com/library/96eb634e-af2f-454e-8014-b698396811c4.aspx)
    
- [復原 Exchange Online 中的非使用中信箱](http://technet.microsoft.com/library/283838b4-66ba-4c34-b221-e1a3875e1d29.aspx)
    
- [還原 Exchange Online 中的非使用中信箱](http://technet.microsoft.com/library/1fb02feb-49e5-4485-aec5-9f1537b772b6.aspx)
    
- [移除 Exchange Online 中不在作用中信箱的保留](http://technet.microsoft.com/library/930a98c3-cd81-4aaa-8e22-19714cb2b731.aspx)
    

