---
title: 變更 Office 365 中的非使用中信箱的保留期間
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/29/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: bdee24ed-b8cf-4dd0-92ae-b86ec4661e6b
description: Office 365 信箱進行非使用中之後，您可以變更 Office 365 保留原則指派給非使用中信箱的保留持續的時間。 保留期間定義中可復原的項目] 資料夾會保留多久的項目。
ms.openlocfilehash: 57b4bda5bda49785b752646174620101f8441135
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2019
ms.locfileid: "30999596"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox-in-office-365"></a>變更 Office 365 中的非使用中信箱的保留期間

非使用中信箱用來他或她離開組織之後保留離職員工的電子郵件。 信箱成為非使用中時訴訟暫止狀態，就地保留，Office 365 保留原則，或與 eDiscovery 案例相關聯保留信箱，並刪除對應的 Office 365 使用者帳戶。 已進行非使用中之前，已處於信箱的保留期間內仍會保留不在作用中信箱的內容。 保留期間定義中可復原的項目] 資料夾會保留多久的項目。 當保留期間到期的 [可復原的項目] 資料夾中的項目時，此項目會永久刪除 （清除） 從非使用中的信箱。 信箱進行非使用中之後，您可以變更 Office 365 保留原則指派給非使用中信箱的保留持續的時間。
  
> [!IMPORTANT]
> 我們已將 2017 年 7 月 1 日的期限延後，以建立新的「就地保留」來建立非使用中的信箱。但到今年年底或明年年初，您將無法在 Exchange Online 中建立新的「就地保留」。到時，只有「訴訟資料暫留」和 Office 365 保留原則可以用來建立非使用中的信箱。不過，仍會支援「就地保留」上現有的非使用中信箱，並且您可以繼續管理非使用信箱上的「就地保留」。這包括變更「就地保留」期間，以及透過移除「就地保留」永久刪除非使用中的信箱。 
  
## <a name="before-you-begin"></a>開始之前

- 您必須使用 Exchange Online PowerShell，若要變更的訴訟資料暫留在非使用中信箱的保留期間。 您無法使用 Exchange 系統管理中心 (EAC)。 但是，您可以使用 Exchange Online PowerShell 或 EAC 來變更為 「 就地保留的保留期間。 若要變更 Office 365 保留原則的保留期間，您可以使用安全性與合規性中心或安全性 & 合規性中心 PowerShell。
    
- 若要連接至 Exchange Online PowerShell 或安全性 & 合規性中心 PowerShell，請參閱下列其中一個下列主題：
    
  - [連線到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
  - [連線至 Office 365 Security& 合規性中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=799771)
    
- 請注意，保留與 eDiscovery 案例相關聯會無限期保留，這表示不沒有可以變更任何保留持續時間。 項目會保留不限次數，或直到移除保留及刪除非使用中信箱。
    
- 如需非使用中信箱的詳細資訊，請參閱 <<c0>在 Office 365 中的非使用中信箱。
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>步驟 1： 識別非使用中信箱上保留

因為不同類型的保留 」 或 「 一或多個 Office 365 保留原則也可能會放置在非使用中信箱上，第一個步驟是識別非使用中信箱上的保留。
  
PowerShell 中執行下列命令在 Exchange Online 來顯示貴組織中的所有非使用中信箱的保留資訊。
  
```
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,InPlaceHolds
```
   
**LitigationHoldEnabled**屬性的**則為 True**的值會指出作用中的信箱處於訴訟暫止狀態。 如果為 「 就地保留 eDiscovery 保留，或 Office 365 保留原則會被放置在非使用中信箱上，保留或保留原則的 GUID 被顯示為**InPlaceHolds**屬性的值。 例如，下列顯示 5 的非使用中信箱的結果。 
  
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
   
下表列出的五個不同的保留類型用來停用每個信箱。
  
|**非使用中信箱**|**保留類型**|**如何識別非使用中信箱上保留**|
|:-----|:-----|:-----|
|Ann Beebe  <br/> |訴訟資料暫留  <br/> |*LitigationHoldEnabled*屬性設為`True`。  <br/> |
|Pilar Pinilla  <br/> |原有範圍暫止  <br/> |*InPlaceHolds*屬性會包含在原有範圍暫止，處於非使用中信箱的 GUID。 您可以告訴這是在原有範圍暫止因為識別碼不會啟動與前置詞。  <br/> 您可以使用`Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL`命令在 Exchange Online PowerShell，以取得在作用中信箱 「 就地保留 」 狀態的資訊。  <br/> |
|伊 Necaise  <br/> |安全性 & 合規性中心中的全組織的 Office 365 保留原則  <br/> |*InPlaceHolds*屬性是空的。 這表示，一或多個全組織或 （Exchange 全） Office 365 保留原則套用至非使用中信箱。 在此情況下，您可以執行`Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`命令在 Exchange Online PowerShell，以取得整個組織的 Office 365 保留原則 Guid 的清單。 整個組織的保留原則套用至 Exchange 信箱的開頭的 GUID`mbx`字首;例如`mbxa3056bb15562480fadb46ce523ff7b02`。  <br/> <br/>會套用至非使用中信箱的身分識別 Office 365 保留原則，請在安全性 & 合規性中心 PowerShell 中執行下列命令。  <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>
|收件者 Olson  <br/> |安全性 & 套用至特定信箱的合規性中心中的 office 365 保留原則  <br/> |*InPlaceHolds*屬性包含 Office 365 保留原則套用至非使用中信箱的 GUID。 您可以分清這是因為 GUID 開頭套用至特定信箱的保留原則`mbx`前置詞。 請注意，如果保留原則套用至非使用中信箱的 GUID 入門`skp`前置詞，表示會保留原則套用至 Skype for Business 交談。  <br/><br/> 會套用至非使用中信箱的身分識別 Office 365 保留原則，請在安全性 & 合規性中心 PowerShell 中執行下列命令。<br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name` <br/><br/>請務必移除`mbx`或`skp`當您執行此命令的前置詞。  <br/> |
|林肯 McMahon  <br/> |安全性 & 合規性中心中保留電子文件探索案例  <br/> |*InPlaceHolds*屬性包含 eDiscovery 案例保留處於非使用中信箱的 GUID。 您可以分清這是 eDiscovery 案例保留，因為 GUID 開頭`UniH`前置詞。  <br/> 您可以使用`Get-CaseHoldPolicy`安全性 & 以取得在作用中的信箱保留相關聯的 eDiscovery 案例的相關資訊的合規性中心 PowerShell 中的指令程式。 例如，您可以執行此命令`Get-CaseHoldPolicy <hold GUID without prefix> | FL Name`來顯示在作用中的信箱上的案例保留的名稱。 請務必移除`UniH`當您執行此命令的前置詞。  <br/><br/> 若要識別非使用中信箱上的保留相關聯的 eDiscovery 案例，執行下列命令。  <br/><br/> `$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/> `Get-ComplianceCase $CaseHold.CaseId | FL Name`<br/><br/><br/> **附註：** 我們不建議使用 eDiscovery 保留非使用中的信箱。 That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue. 有些時候，法律案件最終會將可能並將移除保留與案例相關聯的 eDiscovery 案例將會關閉 （或刪除）。 事實上，如果處於非使用中信箱的保留相關聯的 eDiscovery 案例，並釋放保留或關閉或刪除 eDiscovery 案例，在作用中信箱將會永久刪除。 

如需有關 Office 365 保留原則的詳細資訊，請參閱[保留原則的概觀](retention-policies.md)。
  
## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a>步驟 2： 變更非使用中信箱的保留期間

識別何種類型的保留處於非使用中信箱之後 （以及是否有多項保留） 下, 一步是要變更保留持續時間。 
  
### <a name="change-the-duration-for-a-litigation-hold"></a>變更的訴訟暫止持續時間

以下是如何使用 Exchange Online PowerShell 來變更保留持續時間處於非使用中信箱訴訟暫止狀態。 您無法使用 EAC。 執行下列命令，以變更保留持續時間。 在這個範例中，保留期間會變更為不受限制的一段時間。
  
```
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldDuration unlimited
```

結果是不在作用中信箱中的項目會保留無限期或直到移除保留或保留持續時間變更為不同的值。
  
> [!TIP]
> 若要識別非使用中信箱的最佳方式是使用其**辨別名稱**或**Exchange GUID**值。 使用下列值之一，有助於防止不小心指定錯誤的信箱。 
  
### <a name="change-the-duration-for-an-in-place-hold"></a>變更為 「 就地保留的持續時間

 若要變更為 「 就地保留的保留期間，您可以使用 EAC 或 Exchange Online PowerShell。 
  
#### <a name="use-the-eac-to-change-the-hold-duration"></a>使用 EAC 來變更保留持續時間

1. 如果您知道想要變更為 「 就地保留的名稱，請移至下一個步驟。 否則，執行下列命令，以取得處於非使用中的信箱就地保留的名稱。 使用就地保留 GUID，您在[步驟 1](#step-1-identify-the-holds-on-an-inactive-mailbox)中所取得。

    ```
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. 在 EAC 中，移至 [**規範管理** \> **就地 eDiscovery&amp;保留**。
    
3. 選取您要變更為 「 就地保留，然後按一下 [**編輯**![編輯圖示](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。
    
4. 在**就地 eDiscovery&amp;保留**屬性] 頁面上，按一下 [**原有範圍暫止**。 
    
5. 根據目前的下列其中一個保留持續時間:
    
1. 按一下 [無限制一段時間保留項目 [**無限期保留**]。 
    
2. 按一下**指定的天數將其接收日期的項目保留**在特定期間內保留項目。 輸入您想要的項目保留天數。 
    
    ![變更就地保留之持續期間的螢幕擷取畫面](media/cfcfd92a-9d65-40c0-90ef-ab72697b0166.png)
  
6. 按一下 [儲存]****。
    
#### <a name="use-exchange-online-powershell-to-change-the-hold-duration"></a>使用 Exchange Online PowerShell 來變更保留持續時間

1. 如果您知道想要變更為 「 就地保留的名稱，請移至下一個步驟。 否則，執行下列命令，以取得處於非使用中的信箱就地保留的名稱。 使用就地保留 GUID，您在[步驟 1](#step-1-identify-the-holds-on-an-inactive-mailbox)中所取得。

    ```
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. 執行下列命令，以變更保留持續時間。 在這個範例中，保留期間會變更為 2,555 天 （約 7 年）。 
    
    ```
    Set-MailboxSearch <identity of In-Place Hold> -ItemHoldPeriod 2555
    ```

     若要變更保留持續時間為無限制的一段時間，請使用 _-ItemHoldPeriod 無限制_。
  
## <a name="more-information"></a>詳細資訊

- **針對非使用中的信箱中的項目如何計算保留持續時間？** 持續時間被計算的原始日期信箱項目所接收或建立。 
    
- **保留期間到期時，會發生什麼事？** 當保留期間到期的 [可復原的項目] 資料夾中的信箱項目時，此項目會永久刪除 （清除） 從非使用中的信箱。 如果沒有指定處於非使用中的信箱保留無期間，[可復原的項目] 資料夾中的項目永遠不會清除 （除非非使用中信箱的保留期間變更）。 
    
- **Exchange 保留原則仍上處理非使用中信箱嗎？** 如果它成為非使用中時，（通訊記錄管理 」 或 「 MRM，Exchange Online 中的功能） 的 Exchange 保留原則套用至信箱，將會刪除原則 （也就是設定以**刪除**保留動作的保留標記）繼續處理非使用中信箱上。 這表示與刪除原則標記的項目移至 [可復原的項目] 資料夾保留期間到期時。 然後會清除這些項目從非使用中的信箱項目保留期間到期時。 
    
    相反地，會略過任何封存原則 （也就是以**MoveToArchive** ： 保留動作設定的保留標記） 所隨附指派給非使用中信箱的保留原則。 這表示在非使用中信箱與封存原則標記的項目保留在主要信箱保留期間到期時。 它們不被移至封存信箱或封存信箱中 [可復原的項目] 資料夾。 因為使用者無法登入非使用中的信箱，則無須耗用資料中心的資源來處理封存原則。 
    
- **若要檢查新的保留期間，請執行下列其中一個下列命令。** 第一個命令為訴訟暫止狀態;第二個適用於原有範圍暫止。 

    ```
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | FL LitigationHoldDuration
    ```

    ```
    Get-MailboxSearch <identity of In-Place Hold> | FL ItemHoldPeriod
    ```

- **與一般信箱相同受管理的資料夾助理員 (MFA) 也會處理非使用中信箱。** 在 Exchange Online 中，MFA 會處理信箱一次大約每隔 7 天。 在變更非使用中信箱的保留期間後，您可以使用**Start-managedfolderassistant**指令程式可以立即開始處理非使用中信箱的新保留期間。 執行下列命令。 

    ```
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- **如果保留許多處於非使用中的信箱，不是所有的保留將顯示的 Guid。** 您可以執行下列命令，以顯示 （除了訴訟保留） 處於非使用中信箱的所有保留的 Guid。 
    
    ```
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```
