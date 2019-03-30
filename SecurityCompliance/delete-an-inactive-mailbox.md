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
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2019
ms.locfileid: "31001066"
---
# <a name="delete-an-inactive-mailbox-in-office-365"></a>刪除 Office 365 中的非使用中信箱

在前任員工離開您的組織之後，可透過非使用中信箱來保留其電子郵件。 當您不再需要保留非使用中信箱的內容時，您可以永久刪除非使用中信箱移除保留。 此外，很可能多項保留可能處於非使用中的信箱。 例如，非使用中信箱也可能會放置訴訟暫止，並在一或多個就地保留。 此外，Office 365 保留原則 （在 Office 365 或 Microsoft 365 安全性與合規性中心] 中建立） 可能會套用至非使用中信箱。 您必須將它刪除非使用中信箱中移除所有的保留和 Office 365 保留原則。 保留和保留原則中移除之後，在作用中信箱標記為待刪除，並永久刪除之後就會處理。
  
> [!IMPORTANT]
> 我們已將 2017 年 7 月 1 日的期限延後，以建立新的「就地保留」來建立非使用中的信箱。但到今年年底或明年年初，您將無法在 Exchange Online 中建立新的「就地保留」。到時，只有「訴訟資料暫留」和 Office 365 保留原則可以用來建立非使用中的信箱。不過，仍會支援「就地保留」上現有的非使用中信箱，並且您可以繼續管理非使用信箱上的「就地保留」。這包括變更「就地保留」期間，以及透過移除「就地保留」永久刪除非使用中的信箱。 
  
請參閱說明從非使用中信箱移除保留後，會發生什麼情況[的詳細資訊](#more-information)一節。 
  
## <a name="before-you-begin"></a>開始之前

- 您必須使用 Exchange Online PowerShell 來從非使用中的信箱中移除 [訴訟暫止狀態。 您無法使用 Exchange 系統管理中心 (EAC)。 如需逐步指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。 您可以使用 Exchange Online PowerShell 或 EAC 來移除從非使用中信箱的 [就地保留。 
    
- 移除保留與刪除非使用中信箱之前，您可以不在作用中信箱的內容複製到另一個信箱。 如需詳細資訊，請參閱 <<c0>還原 Office 365 中的非使用中信箱。
    
- 如果您從非使用中信箱移除保留或 Office 365 保留原則和信箱的虛刪除信箱保留期間已過期，將永久刪除信箱。 會在刪除之後，便無法復原。 移除保留之前，先確定您不再需要的信箱中的內容。 如果您想要重新啟用非使用中的信箱，您就可以進行復原。 如需詳細資訊，請參閱[復原非使用中信箱 Office 365 中](recover-an-inactive-mailbox.md)。
    
- 如需非使用中信箱的詳細資訊，請參閱 <<c0>在 Office 365 中的非使用中信箱。
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>步驟 1： 識別非使用中信箱上保留

如先前所述，訴訟暫止，原有範圍暫止，或 Office 365 保留原則可能會處於非使用中的信箱。 第一個步驟是識別非使用中信箱上的保留。
  
執行下列命令，以顯示貴組織中的所有非使用中信箱的保留資訊。
  
```
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

**LitigationHoldEnabled**屬性的**則為 True**的值會指出作用中的信箱處於訴訟暫止狀態。 如果在原有範圍暫止處於非使用中的信箱，保留的 GUID 被顯示為**InPlaceHolds**屬性的值。 例如，兩個非使用中信箱的下列結果顯示的訴訟暫止狀態會置於 Ann Beebe 和兩個就地保留放在 Pilar Pinilla。 
  
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
> 如果許多為 「 就地保留處於非使用中的信箱，將會顯示不是所有的就地保留 Guid。 您可以執行下列命令，以顯示所有為 「 就地保留的 Guid:`Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`
  
## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a>步驟 2： 從非使用中的信箱移除保留

識別何種類型的保留處於非使用中信箱之後 （以及是否有多項保留） 下, 一步是要移除的信箱上保留。 如先前所述，您必須移除所有保留]，以永久刪除非使用中的信箱。 
  
### <a name="remove-a-litigation-hold"></a>移除訴訟資料暫留

如先前所述，您必須使用 Windows PowerShell 來從非使用中的信箱中移除 [訴訟暫止狀態。 您無法使用 EAC。 執行下列命令，以移除訴訟暫止狀態。
  
```
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> 若要識別非使用中信箱的最佳方式是使用其辨別名稱或 Exchange GUID 值。 使用下列值之一，有助於防止不小心指定錯誤的信箱。 
  
### <a name="remove-in-place-holds"></a>移除就地保留

 有兩種方式可從非使用中的信箱中移除 [就地保留： 
  
- **刪除就地保留的物件**如果您想要永久刪除非使用中信箱是在原有範圍暫止的唯一來源信箱，您可以只刪除就地保留物件。 
    
    > [!NOTE]
    > 您必須停用保留後，才能刪除就地保留的 object。 如果您嘗試刪除就地保留物件已啟用保留時，您會收到錯誤訊息。 
  
- **移除為來源信箱的就地保留的非使用中信箱**如果您想要保留其他來源信箱的就地保留，您可以移除不在作用中信箱從來源信箱的清單，並保留在原有範圍暫止物件。 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a>使用 EAC 來刪除就地保留

1. 如果您知道想要刪除就地保留的名稱，您可以移至下一個步驟。 否則，執行下列命令，以取得您想要永久刪除非使用中信箱處於就地保留的名稱。 使用就地保留 GUID 中得到的[步驟 1： 識別非使用中信箱上的保留](#step-1-identify-the-holds-on-an-inactive-mailbox)。
    
```
  Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
```

2. 在 EAC 中，移至 [**規範管理** \> **就地 eDiscovery&amp;保留**。
    
3. 選取您要刪除就地保留，然後按一下 [**編輯**![編輯圖示](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。
    
4. 在**就地 eDiscovery&amp;保留**屬性] 頁面上，按一下 [**原有範圍暫止**、 取消核取 [**將符合搜尋查詢的所選信箱上內容保留**] 方塊中，，然後按一下 [**儲存**。
    
5. 在**就地 eDiscovery&amp;保留**] 頁面上，選擇一次，為 「 就地保留，然後按一下 [**刪除**![刪除圖示](media/87565fbb-5147-4f22-9ed7-1c18ce664392.png)。
    
6. 在警告中，按一下 [ **]** 以刪除 「 就地保留 」 狀態。 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a>使用 Exchange Online PowerShell 來刪除就地保留

1. 建立包含您想要刪除就地保留的屬性的變數。 使用就地保留 GUID 中得到的[步驟 1： 識別非使用中信箱上的保留](#step-1-identify-the-holds-on-an-inactive-mailbox)。
    
```
  $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
```

2. 停用保留在 「 就地保留 」 狀態。
    
```
  Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
```

3. 刪除就地保留。
    
```
  Remove-MailboxSearch $InPlaceHold.Name
```

#### <a name="use-the-eac-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a>使用 EAC 來移除非使用中的信箱就地保留

1. 如果您知道處於非使用中的信箱就地保留的名稱，您可以移至下一個步驟。 否則，執行下列命令，以取得在原有範圍暫止放置在信箱上的名稱。 使用就地保留 GUID 中得到的[步驟 1： 識別非使用中信箱上的保留](#step-1-identify-the-holds-on-an-inactive-mailbox)。
    
```
  Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
```

2. 在 EAC 中，移至 [**規範管理** \> **就地 eDiscovery&amp;保留**。
    
3. 選取處於非使用中信箱中，就地保留，然後按一下 [**編輯**![編輯圖示](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。
    
4. 在**就地 eDiscovery&amp;保留**屬性] 頁面上，按一下 [**來源**]。
    
5. 在來源信箱的清單中，按一下您想要移除，非使用中信箱的名稱，然後按一下 [**移除**![移除圖示](media/adf01106-cc79-475c-8673-065371c1897b.gif)。
    
6. 按一下 [**儲存**] 以儲存變更。 會顯示一則訊息，指出作業已順利完成。 
    
7. 重複步驟 1 至 6，放置在非使用中信箱上其他就地保留中移除。
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a>若要移除的非使用中的信箱就地保留使用 Exchange Online PowerShell

如果 「 就地保留 」 狀態包含大量的來源信箱，則可能不在作用中信箱不會列出在 EAC 中的 [**來源**] 頁面上。 顯示最多 3000 信箱會在 [**來源**] 頁面上編輯在原有範圍暫止時。 如果不在作用中信箱未列在 [**來源**] 頁面上，您可以使用 Exchange Online PowerShell 移除 「 就地保留 」 狀態。 
  
1. 建立包含在原有範圍暫止處於非使用中信箱的屬性的變數。 使用就地保留 GUID 中得到的[步驟 1： 識別非使用中信箱上的保留](#step-1-identify-the-holds-on-an-inactive-mailbox)。
    
```
  $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
```

2. 確認非使用中信箱列出的來源信箱的 「 就地保留 」 狀態。 
    
```
  $InPlaceHold.Sources
```

   **附註：**「 就地保留 」 狀態的*來源*屬性會識別來源信箱由其*LegacyExchangeDN*屬性。 因為這個屬性可唯一識別非使用中信箱，使用 [*來源*] 屬性，從 「 就地保留 」 狀態有助於防止移除錯誤的信箱。 這也有助於避免發生問題，如果這兩個信箱有相同的別名或 SMTP 位址。 
   
3. 非使用中信箱移除在變數中的來源信箱的清單。 請務必使用前一個步驟中的命令會傳回非使用中信箱的**LegacyExchangeDN** 。 
    
```
  $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
```

    For example, the following command removes the inactive mailbox for Pilar Pinilla.
    
  ```
  $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
  ```

4. 確認非使用中的信箱會移除在變數中的來源信箱的清單。
    
```
  $InPlaceHold.Sources
```

5. 修改與更新來源信箱的清單，其中不包含作用中的信箱就地保留。
    
```
  Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
```

6. 確認非使用中的信箱從來源信箱的清單移除的 「 就地保留 」 狀態。
    
```
  Get-MailboxSearch $InPlaceHold.Name | FL Sources
```

## <a name="more-information"></a>詳細資訊

- **非使用中信箱是信箱的一種虛刪除。** 在 Exchange Online 中，將虛刪除的信箱會是已刪除，但可以在特定的保留期間內可復原的信箱。 Exchange Online 中的虛刪除信箱保留期間是 30 天。 這表示被虛刪除的 30 天內，即可復原信箱。 30 天後，虛刪除的信箱會標示為永久刪除，並且無法復原。 
    
- **移除位於非使用中信箱保留後，會發生什麼事？** 信箱就會被視為其他虛刪除信箱，並在 30 天虛刪除信箱保留期間到期後，會標示為永久刪除。 當信箱已第一次進行非使用中的日期上，啟動此保留期間。 此日期就是所謂的虛刪除的日期，這是已刪除對應的 Office 365 使用者帳戶，或使用**Remove-mailbox** cmdlet 刪除 Exchange Online 信箱已時的日期。 虛刪除日期不移除保留的日期。 
    
- **非使用中信箱永久刪除之後移除保留嗎？** 如果不在作用中信箱的虛刪除日期是超過 30 天，只要您移除保留，不會被永久刪除信箱。 信箱會被標示為永久刪除，而且刪除它會處理在下一次。 
    
- **虛刪除信箱保留期間如何影響非使用中信箱？** 如果不在作用中信箱的虛刪除日期超過 30 天保留已移除日期之前，信箱會標示為永久刪除。 但是，如果不在作用中的信箱已在過去 30 天內的虛刪除日期，並且移除保留，您就可以復原信箱，直到虛刪除信箱保留期間到期為止。 如需詳細資訊，請參閱[刪除或還原使用者信箱在 Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835)。 虛刪除信箱保留期間到期之後，您必須依照復原非使用中信箱的程序。 如需詳細資訊，請參閱[復原非使用中信箱 Office 365 中](recover-an-inactive-mailbox.md)。
    
- **如何顯示不在作用中信箱的相關資訊之後移除保留？** 移除保留且非使用中的信箱會回到虛刪除的信箱之後，它不會傳回*InactiveMailboxOnly*參數使用**Get-mailbox**指令程式。 但是，您可以使用**Get-mailbox SoftDeletedMailbox**命令來顯示信箱的相關資訊。 例如： 
    
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
  
在上述範例中， *WhenSoftDeleted*屬性識別的虛刪除的日期，這在這個範例中是 2014 年 10 月 30 日。 如果此虛刪除的信箱先前已保留已移除的非使用中信箱，它將會永久刪除的 30 天後*WhenSoftDeleted*屬性的值。 在此情況下，在 2014 年 11 月 30 日之後永久刪除信箱。

