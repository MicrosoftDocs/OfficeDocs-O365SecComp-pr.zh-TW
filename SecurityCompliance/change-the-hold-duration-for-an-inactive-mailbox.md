---
title: 變更 Office 365 中不在作用中信箱的保留期間
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/29/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: bdee24ed-b8cf-4dd0-92ae-b86ec4661e6b
description: Office 365 信箱進行非使用中之後，您可以變更保留或 Office 365 保留原則指派給非使用中信箱的工期。保留期間可復原的項目] 資料夾，可以保留中定義多久的項目。
ms.openlocfilehash: e3d1d6c7ec0311813dfa1144cc960d2fed9e160d
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038056"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox-in-office-365"></a>變更 Office 365 中不在作用中信箱的保留期間

非使用中的信箱用來保留先前員工的電子郵件之後他離開貴組織。信箱成為非使用中時訴訟暫止狀態、 就地保留、 Office 365 保留原則或保留與 eDiscovery 案例相關聯處於信箱，並刪除對應的 Office 365 使用者帳戶。不在作用中信箱的內容會保留它進行非使用中之前被指定信箱的保留期間。保留期間可復原的項目] 資料夾，可以保留中定義多久的項目。保留期間到期的可復原的項目] 資料夾中的項目、 時項目會永久刪除 （清除） 從非使用中的信箱。進行不在作用中信箱之後，您可以變更保留或 Office 365 保留原則指派給非使用中信箱的工期。
  
> [!IMPORTANT]
> 我們已將 2017 年 7 月 1 日的期限延後，以建立新的「就地保留」來建立非使用中的信箱。但到今年年底或明年年初，您將無法在 Exchange Online 中建立新的「就地保留」。到時，只有「訴訟資料暫留」和 Office 365 保留原則可以用來建立非使用中的信箱。不過，仍會支援「就地保留」上現有的非使用中信箱，並且您可以繼續管理非使用信箱上的「就地保留」。這包括變更「就地保留」期間，以及透過移除「就地保留」永久刪除非使用中的信箱。 
  
## <a name="before-you-begin"></a>開始之前

- 您必須使用 Exchange Online PowerShell 訴訟暫止狀態不在作用中的信箱上變更保留持續時間。您無法使用 Exchange 系統管理中心 (EAC)。但是您可以使用 Exchange Online PowerShell 或 EAC 來變更為就地保留的保留期間。您可以使用 Office 365 安全性&amp;規範中心或安全性&amp;規範中心 PowerShell 來變更 Office 365 保留原則的保留期間。
    
- 若要連線至 Exchange Online PowerShell 或安全性&amp;規範中心 PowerShell，請參閱下列主題的其中一個：
    
  - [使用遠端 PowerShell 連線到 Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
  - [連接到 Office 365 安全性與合規性中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=799771)
    
- 保留 eDiscovery 案例相關聯的記事會無限期保留，這表示沒有可變更沒有保留持續時間。項目會保留不限次數或直到移除保留及刪除非使用中的信箱。
    
- 如需非使用中信箱的詳細資訊，請參閱[Office 365 中的非使用中信箱](inactive-mailboxes-in-office-365.md)。
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>步驟 1： 識別非使用中信箱的保留

因為不同類型的保留或一或多個 Office 365 保留原則可能會被放置在非使用中的信箱，第一個步驟是識別非使用中信箱的保留。
  
執行下列命令在 Exchange Online PowerShell 來顯示您組織中所有非使用中信箱的保留資訊。
  
```
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,InPlaceHolds
```
   
**LitigationHoldEnabled**屬性值為**True**表示非使用中信箱處於訴訟暫止狀態。若為 「 就地保留 eDiscovery 保留，或 Office 365 保留原則處於非使用中的信箱，保留或保留原則的 GUID 被顯示為**InPlaceHolds**屬性的值。例如，以下顯示 5 的非使用中信箱的結果。 
  
||
|:-----|
|
```
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
LitigationHoldDuration: 365.00:00:00
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491}
...
DisplayName           : Mario Necaise
Name                  : marion
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {}
...
DisplayName           : Carol Olson
Name                  : carolo
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {mbxcdbbb86ce60342489bff371876e7f224}
...
DisplayName           : Abraham McMahon
Name                  : abrahamm
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {UniH7d895d48-7e23-4a8d-8346-533c3beac15d}
```
   
下表列出用來停用每個信箱的五個不同的保留類型。
  
|**非使用中信箱**|**保留類型**|**如何識別在非使用中信箱的保留**|
|:-----|:-----|:-----|
|Ann Beebe  <br/> |訴訟暫止  <br/> |*LitigationHoldEnabled*屬性設為`True`。  <br/> |
|Pilar Pinilla  <br/> |原有範圍暫止  <br/> |*InPlaceHolds*屬性會包含非使用中信箱處於就地保留 GUID。您可以分清這是就地保留因為識別碼不會開始使用前置詞。<br/> 您可以使用 ' Get MailboxSearch InPlaceHoldIdentity<hold GUID> | FL' 命令以取得關於就地保留資訊不在作用中的信箱上的 Exchange Online PowerShell 中。  <br/> |
|伊 Necaise  <br/> |在 [安全性] 中的整個組織的 Office 365 保留原則&amp;規範中心  <br/> |*InPlaceHolds*屬性是空的。這指出一或多個整個組織或 （Exchange 全） Office 365 保留原則套用至非使用中的信箱。在此例中，您可以執行 ' Get-organizationconfig | Select-object-ExpandProperty InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Office 365 retention policies. The GUID for organization-wide retention policies that are applied to Exchange mailboxes start with the  `mbx` prefix; for example  `mbxa3056bb15562480fadb46ce523ff7b02`.  <br/> <br/>To identity the Office 365 retention policy that's applied to the inactive mailbox, run the following command in Security &amp; Compliance Center PowerShell.  <br/><br/> `Get RetentionCompliancePolicy<retention policy GUID without prefix> | FL 名稱 '<br/><br/>
|收件者 Olson  <br/> |在 [安全性] 中的 office 365 保留原則&amp;規範中心套用至特定信箱  <br/> |*InPlaceHolds*屬性會包含 Office 365 保留原則套用至非使用中信箱的 GUID。您可以分清這是因為 GUID 開頭套用至特定信箱的保留原則`mbx`前置詞。請注意，如果保留原則套用至非使用中信箱的 GUID 入門`skp`前置詞表示將保留原則套用至 Skype 商務交談。<br/><br/> Identity 為 Office 365 保留原則套用至非使用中的信箱，以執行下列命令安全性&amp;規範中心 PowerShell。<br/><br/> ' 取得 RetentionCompliancePolicy<retention policy GUID without prefix> | FL 名稱` <br/><br/>Be sure to remove the  `mbx` or  `skp' prefix 當您執行此命令。  <br/> |
|林肯 McMahon  <br/> |eDiscovery 案例保留安全性&amp;規範中心  <br/> |*InPlaceHolds*屬性會包含處於非使用中信箱的 eDiscovery 案件保留 GUID。您可以分清這是因為 GUID 開頭的 eDiscovery 案件保留`UniH`前置詞。<br/> 您可以使用`Get-CaseHoldPolicy`指令程式的安全性&amp;規範中心 PowerShell 取得不在作用中信箱的保留相關聯的 eDiscovery 案例的相關資訊。例如，您可以執行此命令 ' Get CaseHoldPolicy<hold GUID without prefix> | FL 名稱` to display the name of the case hold that's on the inactive mailbox. Be sure to remove the  `UniH` prefix when you run this command.  <br/><br/> To identity the eDiscovery case that the hold on the inactive mailbox is associated with, run the following commands.  <br/><br/> `$CaseHold = Get CaseHoldPolicy <hold GUID without prefix> `<br/><br/> `Get ComplianceCase $CaseHold.CaseId | FL 名稱 '<br/><br/><br/> **附註：** 我們不建議使用 eDiscovery 保留為非作用中的信箱。那是因為 eDiscovery 案例適用於特定的時間繫結案例相關的法律問題。有些時候法律案例可能將會結束與將會移除與案例相關聯的保留和 eDiscovery 案例將會關閉 （或刪除）。事實上，如果處於非使用中信箱的保留相關聯 eDiscovery 案例、 和發行保留或關閉或刪除 eDiscovery 案例、 非使用中的信箱將會永久刪除。 

如需 Office 365 的保留原則的詳細資訊，請參閱 ＜ [Overview of 保留原則](retention-policies.md)。
  
## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a>步驟 2： 變更非使用中信箱的保留期間

在您識別何種類型的保留處於非使用中信箱之後 （以及是否有多個保留） 下, 一步是要變更保留持續時間。 
  
### <a name="change-the-duration-for-a-litigation-hold"></a>變更的訴訟暫止狀態的持續時間

以下是如何使用 Exchange Online PowerShell 來變更為非使用中的信箱處於訴訟暫止狀態的保留期間。您無法使用 EAC。執行下列命令以變更保留期間。在這個範例中，保留持續時間會變更為不受限制的一段時間。
  
```
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldDuration unlimited
```

結果是不在作用中的信箱中的項目會保留無限期或直到撤除或保留持續時間變更為不同的值。
  
> [!TIP]
> 識別非使用中信箱的最佳方式是使用其**辨別名稱**或**Exchange 的 GUID**值。使用下列值之一有助於防止不慎指定了錯誤的信箱。 
  
### <a name="change-the-duration-for-an-in-place-hold"></a>變更為就地保留期間

 您可以使用 EAC 或 Exchange Online PowerShell 變更為就地保留的保留期間。 
  
#### <a name="use-the-eac-to-change-the-hold-duration"></a>使用 EAC 來變更保留期間

1. 如果您知道您想要變更為 「 就地保留的名稱，請移至下一個步驟。否則請執行下列命令以取得處於非使用中的信箱就地保留的名稱。使用就地保留 GUID 您在[步驟 1](#step-1-identify-the-holds-on-an-inactive-mailbox)中取得。

    ```
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. 在 EAC 中，移至 [**規範管理** \> **就地 eDiscovery&amp;保留**。
    
3. 選取您想要變更為 「 就地保留，然後按一下 [**編輯**![編輯圖示](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。
    
4. 在**就地 eDiscovery&amp;保留**屬性] 頁面上，按一下 [**就地保留功能**。 
    
5. 根據目前的下列其中之一不要保留持續時間：
    
1. 按一下 [**無限期保留**無限一段時間保留項目。 
    
2. 按一下以在特定期間內保留項目**指定天數以保留項目相對於其接收日期**。輸入您想要保留的項目保留的天數。 
    
    ![變更就地保留之持續期間的螢幕擷取畫面](media/cfcfd92a-9d65-40c0-90ef-ab72697b0166.png)
  
6. 按一下 [儲存]****。
    
#### <a name="use-exchange-online-powershell-to-change-the-hold-duration"></a>使用 Exchange Online PowerShell 來變更保留持續時間

1. 如果您知道您想要變更為 「 就地保留的名稱，請移至下一個步驟。否則請執行下列命令以取得處於非使用中的信箱就地保留的名稱。使用就地保留 GUID 您在[步驟 1](#step-1-identify-the-holds-on-an-inactive-mailbox)中取得。

    ```
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. 執行下列命令以變更保留期間。在這個範例中，保留持續時間會變更為 2,555 天 （大約 7 年）。 
    
    ```
    Set-MailboxSearch <identity of In-Place Hold> -ItemHoldPeriod 2555
    ```

     若要變更保留持續時間為不受限制的一段時間，請使用 _-ItemHoldPeriod 無限制_。
  
## <a name="more-information"></a>詳細資訊

- **的保留持續時間計算方式為在非使用中的信箱項目？** 將信箱項目所接收或建立的原始日期被計算持續時間。 
    
- **保留期間到期時會發生什麼事？** 保留期間到期的可復原的項目] 資料夾中的信箱項目、 時項目會永久刪除 （清除） 從非使用中的信箱。如果沒有指定放置在非使用中信箱的保留給沒有工期，將 （除非不在作用中信箱的保留期間會在變更） 永遠不會清除 [可復原的項目] 資料夾中的項目。 
    
- **仍不在作用中的信箱上處理 Exchange 保留原則吗？** 如果 （通訊記錄管理或 MRM，Exchange Online 中的功能） Exchange 保留原則套用到信箱已進行非使用中時，將會刪除原則 」 （這是設定為**刪除**保留動作的保留標記）繼續處理非使用中的信箱。這表示與刪除原則標記的項目移至 [可復原的項目] 資料夾保留期間到期時。項目的保留期間到期時將這些項目然後會清除從非使用中的信箱。 
    
    反之，會略過任何封存原則 （這是以**movetoarchive：** 保留動作來設定的保留標記） 所包含的指派給非使用中信箱的保留原則。這表示在非使用中信箱與封存原則標記的項目保持在主要信箱的保留期間到期時。它們不被移至封存信箱或封存信箱中 [可復原的項目] 資料夾。使用者無法登入非使用中的信箱，因為沒有理由使用的資料中心的資源來處理封存原則。 
    
- **來檢查新保留持續時間，請執行下列命令。** 第一個命令會針對訴訟暫止狀態 ；第二個是就地保留功能。 

    ```
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | FL LitigationHoldDuration
    ```

    ```
    Get-MailboxSearch <identity of In-Place Hold> | FL ItemHoldPeriod
    ```

- **Like 一般信箱受管理的資料夾助理員 (MFA) 也處理非使用中的信箱。** 在 Exchange Online MFA 程序一次大約每 7 天的信箱。變更非使用中信箱的保留期間之後，您可以使用**Start-managedfolderassistant**指令程式可以立即開始處理非使用中信箱的新保留持續時間。執行下列命令。 

    ```
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- **如果許多的保留會放在非使用中的信箱，不會顯示 Guid 的保留的所有。** 您可以執行下列命令以顯示 （除了訴訟保留） 放置在非使用中的信箱的所有保留的 Guid。 
    
    ```
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```
