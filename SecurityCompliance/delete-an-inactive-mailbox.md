---
title: 刪除非作用中的信箱在 Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
description: 當您不再需要保留的 Office 365 不在作用中信箱內容時，您可以藉由移除保留永久刪除非使用中的信箱。之後移除保留，非使用中信箱標記為待刪除，然後會永久刪除之後會處理。
ms.openlocfilehash: a7284be650d7ec6c89a6fdc43d8614603d6f1e19
ms.sourcegitcommit: 82fd4c85b952819157fbb13175c7b2dbbdff510f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/13/2018
ms.locfileid: "23965250"
---
# <a name="delete-an-inactive-mailbox-in-office-365"></a>刪除非作用中的信箱在 Office 365

非使用中的信箱用來保留先前員工的電子郵件之後他離開貴組織。當您不再需要保留非使用中信箱的內容時，您可以藉由移除保留永久刪除非使用中的信箱。此外，很可能多個保留可能會被放置在非使用中的信箱。例如，非使用中的信箱可能放置訴訟暫止狀態以及一或多個就地保留。此外，Office 365 保留原則 (建立 Office 365 安全性&amp;規範中心) 可能會套用至非使用中的信箱。您必須將它刪除非使用中信箱中移除所有的保留與 Office 365 的保留原則。移除保留和保留原則之後，非使用中信箱標記為待刪除並永久刪除之後會處理。
  
> [!IMPORTANT]
> 我們已將 2017 年 7 月 1 日的期限延後，以建立新的「就地保留」來建立非使用中的信箱。但到今年年底或明年年初，您將無法在 Exchange Online 中建立新的「就地保留」。到時，只有「訴訟資料暫留」和 Office 365 保留原則可以用來建立非使用中的信箱。不過，仍會支援「就地保留」上現有的非使用中信箱，並且您可以繼續管理非使用信箱上的「就地保留」。這包括變更「就地保留」期間，以及透過移除「就地保留」永久刪除非使用中的信箱。 
  
請參閱[的詳細資訊](delete-an-inactive-mailbox.md#moreinfo)] 區段中的什麼之後保留已從非使用中信箱的描述。 
  
## <a name="before-you-begin"></a>開始之前

- 您必須使用 Exchange Online PowerShell 來移除訴訟暫止狀態不在作用中的信箱。您無法使用 Exchange 系統管理中心 (EAC)。如需逐步說明，請參閱[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554)。您可以使用 Exchange Online PowerShell 或 EAC 來移除就地保留非使用中的信箱。 
    
- 您可以將非使用中信箱的內容複製到另一個信箱之前移除保留及刪除非作用中的信箱。如需詳細資訊，請參閱[還原 Office 365 中的非使用中信箱](restore-an-inactive-mailbox.md)。
    
- 如果您移除保留或 Office 365 保留原則不在作用中信箱和虛刪除信箱保留期間內的信箱已過期，將會永久刪除信箱。會在刪除後，它無法復原。移除保留之前，請確定您不再需要信箱中的內容。如果您想要重新啟動 [非使用中的信箱，您就可以進行復原。如需詳細資訊，請參閱[Office 365 中的不在作用中信箱復原](recover-an-inactive-mailbox.md)。
    
- 如需非使用中信箱的詳細資訊，請參閱[Office 365 中的非使用中信箱](inactive-mailboxes-in-office-365.md)。
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>步驟 1： 識別非使用中信箱的保留

先前所述，不在作用中的信箱上可能會被放置訴訟暫止狀態、 就地保留功能，或 Office 365 的保留原則。第一個步驟是識別非使用中信箱的保留。
  
執行下列命令以顯示您組織中的所有非使用中信箱的保留資訊。
  
```
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

**LitigationHoldEnabled**屬性值為**True**表示非使用中信箱處於訴訟暫止狀態。如果就地保留處於非使用中的信箱，保留 GUID 會顯示為**InPlaceHolds**屬性的值。例如，兩個非使用中信箱的下列結果顯示 Ann Beebe 的處於訴訟暫止狀態和兩個就地保留會放在 Pilar Pinilla。 
  
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
> 如果許多的就地保留處於非使用中的信箱，將會顯示不是所有的就地保留 Guid。您可以執行下列命令以顯示所有為 「 就地保留 Guid：`Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`
  
## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a>步驟 2： 從非使用中的信箱移除保留

在您識別何種類型的保留處於非使用中信箱之後 （以及是否有多個保留） 下, 一步是要移除信箱的保留。先前所述，您必須移除若要永久刪除非作用中信箱的所有保留。 
  
### <a name="remove-a-litigation-hold"></a>移除訴訟暫止狀態

先前所述，您必須使用 Windows PowerShell 移除從非使用中信箱的訴訟暫止狀態。您無法使用 EAC。執行下列命令以移除訴訟暫止狀態。
  
```
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> 識別非使用中信箱的最佳方式是使用其辨別名稱或 Exchange 的 GUID 值。使用下列值之一有助於防止不慎指定了錯誤的信箱。 
  
### <a name="remove-in-place-holds"></a>移除就地保留

 有兩種方式移除就地保留非使用中的信箱： 
  
- **刪除就地保留物件**如果您想要永久地刪除非使用中信箱是唯一的來源信箱的就地保留，您可以只刪除就地保留物件。 
    
    > [!NOTE]
    > 您必須停用保留才能刪除就地保留的物件。如果您嘗試刪除已啟用保留就地保留物件，您會收到錯誤訊息。 
  
- **移除不在作用中信箱為來源信箱的就地保留**如果您想要保留其他來源信箱的就地保留，您可以從來源信箱清單中移除的非使用中的信箱並保留就地保留物件。 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a>使用 EAC 來刪除就地保留

1. 如果您知道您想要刪除就地保留的名稱，您可以前往下一個步驟。否則請執行下列命令以取得您想要永久地刪除非使用中信箱處於就地保留的名稱。使用就地保留 GUID 所取得的[步驟 1： 識別非使用中的信箱上保留](delete-an-inactive-mailbox.md#step1)。
    
```
  Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
```

2. 在 EAC 中，移至 [**規範管理** \> **就地 eDiscovery&amp;保留**。
    
3. 選取您要刪除的就地保留，然後按一下 [**編輯**![編輯圖示](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。
    
4. 在**就地 eDiscovery&amp;保留**屬性頁面、 按一下 [**就地保留**、 取消核取 [**比對搜尋查詢中所選取的信箱上進行內容保留**] 方塊中，然後再按一下 [**儲存**。
    
5. 在**就地 eDiscovery&amp;保留**頁面、 就地保留請再次選取，然後再按一下 [**刪除**![刪除圖示](media/87565fbb-5147-4f22-9ed7-1c18ce664392.png)。
    
6. 在警告中，按一下 [**是]** 以刪除就地保留]。 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a>使用 Exchange Online PowerShell 刪除就地保留

1. 建立包含您想要刪除的就地保留屬性的變數。使用就地保留 GUID 所取得的[步驟 1： 識別非使用中的信箱上保留](delete-an-inactive-mailbox.md#step1)。
    
```
  $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
```

2. 停用設為 「 就地保留的保留。
    
```
  Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
```

3. 刪除就地保留。
    
```
  Remove-MailboxSearch $InPlaceHold.Name
```

#### <a name="use-the-eac-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a>使用 EAC 來移除不在作用中的信箱就地保留

1. 如果您知道名稱不在作用中信箱處於就地保留，您可以前往下一個步驟。否則請執行下列命令以取得信箱處於就地保留的名稱。使用就地保留 GUID 所取得的[步驟 1： 識別非使用中的信箱上保留](delete-an-inactive-mailbox.md#step1)。
    
```
  Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
```

2. 在 EAC 中，移至 [**規範管理** \> **就地 eDiscovery&amp;保留**。
    
3. 選取 [非使用中信箱處於就地保留，然後按一下 [**編輯**![編輯圖示](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。
    
4. 在**就地 eDiscovery&amp;保留**屬性] 頁面上，按一下 [**來源**]。
    
5. 在來源信箱清單中，按一下您要移除的非使用中信箱的名稱] 和 [**移除**![移除圖示](media/adf01106-cc79-475c-8673-065371c1897b.gif)。
    
6. 按一下 [**儲存**] 以儲存變更。會顯示訊息表示作業已順利完成。 
    
7. 重複步驟 1 到 6，以移除處於非使用中信箱其他就地保留。
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a>利用 Exchange Online PowerShell 移除不在作用中的信箱就地保留

如果在 In-place Hold 包含大量的來源信箱，很可能不在作用中的信箱將不會列在 EAC 中的 [**來源**] 頁面上。最多個 3000 信箱會顯示在 [**來源**] 頁面編輯就地保留時。如果非使用中的信箱未列在 [**來源**] 頁面上，您可以使用 Exchange Online PowerShell 移除就地保留。 
  
1. 建立包含的非使用中信箱處於就地保留屬性的變數。使用就地保留 GUID 所取得的[步驟 1： 識別非使用中的信箱上保留](delete-an-inactive-mailbox.md#step1)。
    
```
  $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
```

2. 確認非使用中的信箱已列出為來源信箱的就地保留。 
    
```
  $InPlaceHold.Sources
```

   **附註：** 就地保留的*來源*屬性及其*LegacyExchangeDN*屬性來識別來源信箱。因為這個屬性會唯一識別非使用中的信箱，使用就地保留從*來源*屬性可協助防止移除錯誤的信箱。這也有助於避免發生的問題如果兩個信箱有相同的別名或 SMTP 地址。 
   
3. 移除在變數中的來源信箱清單中的非使用中的信箱。請務必使用前一個步驟中的命令會傳回非使用中信箱的**LegacyExchangeDN** 。 
    
```
  $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
```

    For example, the following command removes the inactive mailbox for Pilar Pinilla.
    
  ```
  $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
  ```

4. 確認非使用中的信箱已從變數中的來源信箱的清單。
    
```
  $InPlaceHold.Sources
```

5. 修改與更新的來源信箱清單不包括非使用中的信箱就地保留。
    
```
  Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
```

6. 確認為就地保留非使用中的信箱已從來源信箱清單中移除。
    
```
  Get-MailboxSearch $InPlaceHold.Name | FL Sources
```

## <a name="more-information"></a>詳細資訊

- **非使用中的信箱是一種虛刪除信箱。** 在 Exchange Online 虛刪除信箱是已遭刪除，但在特定的保留期間內可復原的信箱。Exchange Online 中的虛刪除信箱保留期間是 30 天。這表示信箱的可復原的正在虛刪除 30 天內。30 天後虛刪除信箱標記為永久刪除和無法復原。 
    
- **移除不在作用中的信箱上保留之後會發生什麼事？** 信箱會視為其他虛刪除信箱和 30 天虛刪除信箱保留期間到期後目標記為要永久刪除。此保留期間啟動時之信箱的第一次進行非使用中的日期。此日期就是所謂的虛刪除的日期，這是對應的 Office 365 使用者帳戶已遭刪除或 Exchange Online 信箱刪除使用**Remove-mailbox**指令程式時的日期。虛刪除日期不移除保留的日期。 
    
- **立即之後移除保留永久刪除非作用中信箱吗？** 如果不在作用中信箱的虛刪除日期是超過 30 天，一旦移除保留，將不會永久刪除信箱。信箱會標示為永久刪除和刪除其已處理的下一次。 
    
- **虛刪除信箱保留期間如何影響不在作用中的信箱？** 如果不在作用中信箱的虛刪除日期是超過 30 天保留已移除的日期之前，信箱被標示為永久刪除。但如果不在作用中的信箱已在過去 30 天內虛刪除日期及移除保留，您可以使用復原信箱直到虛刪除信箱保留期間到期。如需詳細資訊，請參閱[刪除或還原使用者信箱在 Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835)。虛刪除信箱保留期間到期後，您有遵循來復原不在作用中信箱的程序。如需詳細資訊，請參閱[Office 365 中的不在作用中信箱復原](recover-an-inactive-mailbox.md)。
    
- **如何顯示不在作用中信箱的相關資訊之後移除保留？** 撤除和非使用中信箱會回到虛刪除信箱後，它將不會傳回使用*InactiveMailboxOnly*參數與**Get-mailbox**指令程式。但是您可以使用**Get-mailbox SoftDeletedMailbox**命令來顯示信箱的相關資訊。例如： 
    
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
  
在上述範例中， *WhenSoftDeleted*屬性識別的虛刪除日期，這在此範例中是 2014 年 10 月 30 日。如果此虛刪除信箱先前非作用中的信箱移除保留的程式，它將會永久刪除的 30 天後*WhenSoftDeleted*屬性的值。在此例中 2014 年 11 月 30 日之後永久刪除信箱。

