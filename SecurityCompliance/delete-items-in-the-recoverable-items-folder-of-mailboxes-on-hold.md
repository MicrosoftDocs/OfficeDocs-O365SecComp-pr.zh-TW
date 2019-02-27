---
title: 刪除項目可復原的項目] 資料夾中的雲端架構信箱保留-Admin 說明
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: a85e1c87-a48e-4715-bfa9-d5275cde67b0
description: 系統管理員： 即使該信箱處於合法持有刪除 Exchange Online 的信箱使用者的可復原的項目] 資料夾中的項目。這是有效的方式刪除已意外溢出至 Office 365 的資料。
ms.openlocfilehash: 4b7b12b33a2364d76b5d7dab6c7e94dc8f00d151
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296176"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold---admin-help"></a>刪除項目可復原的項目] 資料夾中的雲端架構信箱保留-Admin 說明

若要防止意外或惡意刪除存在於 Exchange Online 信箱 [可復原的項目] 資料夾。它也用來儲存都會保留且存取 Office 365 規範功能，例如保留和 eDiscovery 搜尋的項目。不過，在某些情況下組織可能會有已不小心保留在他們必須刪除 [可復原的項目] 資料夾中的資料。例如，使用者可能不知情的情況下傳送或轉寄電子郵件包含敏感資訊或可能會有嚴重商務後果的資訊。即使永久刪除郵件，則可能會保留無限期因為合法持有放置在信箱。此案例中稱為資料 spillage 因為資料不小心溢出至 Office 365。在下列情況下，您可以刪除 Exchange Online 的信箱使用者的可復原的項目] 資料夾中的項目即使該信箱處於保留狀態使用其中一個 Office 365 中的不同保留功能。這些類型的保留包括訴訟保留、 就地保留、 eDiscovery 保留及 Office 365 保留原則建立 Office 365 安全性&amp;規範中心。 
  
 本文說明如何從所保留的雲端架構信箱 [可復原的項目] 資料夾刪除項目。此程序包括停用信箱的存取權和停用單一項目復原，停用受管理的資料夾助理員處理信箱、 暫時移除保留，從 [可復原的項目] 資料夾刪除項目及再回復以其先前的設定信箱。以下是程序： 
  
[步驟 1： 收集信箱的相關資訊](#step-1-collect-information-about-the-mailbox)

[步驟 2： 準備信箱](#step-2-prepare-the-mailbox)

[步驟 3： 從信箱移除所有保留](#step-3-remove-all-holds-from-the-mailbox)

[步驟 4： 從信箱移除延遲保留](#step-4-remove-the-delay-hold-from-the-mailbox)

[步驟 5： 刪除 [可復原的項目] 資料夾中的項目](#step-5-delete-items-in-the-recoverable-items-folder)

[步驟 6： 還原成先前狀態的信箱](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> 本文所述的程序會導致資料要永久刪除 （清除） 從 Exchange Online 信箱。這表示您從 [可復原的項目] 資料夾中刪除的郵件無法復原並不會供法律調查或其他規範用途之用。如果您想要刪除的訴訟暫止狀態、 就地保留功能，一部分處於保留狀態的信箱的郵件 eDiscovery 保留，或 Office 365 保留原則建立 Office 365 安全性&amp;規範中心、 記錄管理或法務的核取然後再移除保留的部門。您的組織可能已定義是否在信箱保留原則或建立資料 spillage 事件採用優先順序。 
  
## <a name="before-you-begin"></a>開始之前

- 您必須指派兩個以下的管理角色在 Exchange Online 來搜尋並刪除 [可復原的項目] 資料夾中之步驟 5 中的郵件。
    
  - **信箱搜尋**此角色可讓您在組織中搜尋信箱。Exchange 系統管理員未指派此角色預設。若要將自己指派此角色，新增您自己探索管理角色群組的成員身分在 Exchange Online。 
    
  - **信箱匯入 / 匯出**-此角色可讓您刪除使用者信箱的郵件。根據預設，此角色不被指派給任何角色群組。若要刪除的郵件從使用者的信箱，您可以新增信箱匯入 / 匯出角色至組織管理角色群組在 Exchange Online。 
    
- 本文所述的程序不支援的非使用中的信箱。那是因為您無法重新套用保留 （或 Office 365 保留原則） 不在作用中的信箱後您移除。當您從非使用中信箱移除保留時，它會變更為 [正常的虛刪除信箱並會永久刪除從您的組織之後的受管理的資料夾助理員處理。
    
- 您無法執行此程序已指派給已遭鎖定保留鎖定與 Office 365 保留原則的信箱。那是因為保留鎖定會防止您從移除或從 Office 365 保留原則及停用受管理的資料夾助理員信箱中排除信箱。如需鎖定保留原則的詳細資訊，請參閱[鎖定保留原則](retention-policies.md#locking-a-retention-policy)。
    
- 如果信箱不處於保留狀態] （或都不會有已啟用單一項目復原） 則您只可以從 [可復原的項目] 資料夾刪除項目。如需如何執行這項作業的詳細資訊，請參閱[搜尋和刪除郵件](https://go.microsoft.com/fwlink/?linkid=852453)。
  
## <a name="step-1-collect-information-about-the-mailbox"></a>步驟 1： 收集信箱的相關資訊

此第一個步驟是從目標信箱會影響此程序收集所選的屬性。請務必寫下這些設定或儲存至的文字檔案，因為在將變更這些屬性的一些且當您從 [可復原的項目] 資料夾刪除項目之後還原回到步驟 6 中的原始值。以下是您需要收集的信箱內容的清單。
  
-  *SingleItemRecoveryEnabled*和*RetainDeletedItemsFor* ;若有需要，您將會停用單一復原並增加步驟 3 中的已刪除的項目保留期間。 
    
-  *LitigationHoldEnabled*和*InPlaceHolds* ;您必須識別放置信箱上以便可以暫時移除這些步驟 3 中的所有保留。請參閱如需如何識別可能會被放置在信箱的類型保留的提示[的詳細資訊](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#moreinfo)] 區段。 
    
此外，您需要取得信箱用戶端存取設定讓您可以暫時停用它們，讓其擁有人 （或其他使用者） 無法在此程序期間存取信箱。最後，您可以在 [可復原的項目] 資料夾中取得目前的大小和項目數。刪除 [可復原的項目] 資料夾中之步驟 5 中的項目之後，您將使用此資訊來確認已真正移除項目。
  
1. [連線到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554)。請務必使用已指派 Exchange Online 中的適當的管理角色的系統管理員帳戶的使用者名稱和密碼。 
    
2. 執行下列命令以取得單一項目復原已刪除的項目保留期間的相關資訊。

    ```
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   如果已啟用單一項目復原，您必須加以停用在步驟 2。如果已刪除的項目保留期間未設定為 30 天 （Exchange Online 中的最大值），則您可增加其在步驟 2。 
    
3. 執行下列命令以取得信箱的信箱的存取設定。 
    
    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   您將會停用所有的這些步驟 2 中的存取方法。
    
4. 執行下列命令以取得保留及 Office 365 保留原則套用至信箱的相關資訊。
    
    ```
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```


   > [!TIP]
    > 如果*InPlaceHolds*屬性中有太多值並不是所有的顯示，則可以執行`Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds`命令以顯示每個值以一行。 
  
5. 執行下列命令來取得任何整個組織的 Office 365 保留原則的相關資訊。 

    ```
    Get-OrganizationConfig | FL InPlaceHolds
    ```
   如果您的組織有任何整個組織的 Office 365 的保留原則，您必須從步驟 3 中的這些原則中排除信箱。

   > [!TIP]
    > 如果*InPlaceHolds*屬性中有太多值並不是所有的顯示，則可以執行`Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`命令以顯示每個值以一行。 
  
6. 執行下列命令以取得目前的大小和項目總數資料夾和使用者的主要信箱中 [可復原的項目] 資料夾中的子資料夾中。 

    ```
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   如果已啟用使用者的封存信箱，執行下列命令以取得資料夾和封存信箱中 [可復原的項目] 資料夾中的子資料夾中的大小和項目總數。 

    ```s
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   當您刪除項目在步驟 5 中時，您可以選擇刪除或刪除使用者的主要封存信箱中 [可復原的項目] 資料夾中的項目。請注意是否啟用自動展開封存信箱，將不會被刪除輔助封存信箱中的項目。
  
## <a name="step-2-prepare-the-mailbox"></a>步驟 2： 準備信箱

收集並之後儲存信箱的相關資訊下, 一步是執行下列工作以準備信箱： 
  
- **停用信箱的用戶端存取**信箱擁有者無法存取其信箱和信箱資料進行任何變更此程序期間。 
    
- **提高刪除項目保留期間**為 30 天 （Exchange Online 中的最大值），讓才能刪除這些步驟 5 中將項目未從 [可復原的項目] 資料夾清除。 
    
- **停用單一項目復原**的項目因此將不會保留 （適用於已刪除的項目保留期間的持續期間） 之後您刪除 [可復原的項目] 資料夾中之步驟 5。 
    
- **停用受管理的資料夾助理員**，讓它不會處理的信箱並保留您在步驟 5 中刪除的項目。 
    
在 Exchange Online PowerShell 中執行下列步驟。
  
1. 執行下列命令以停用所有的用戶端存取信箱。命令語法假設所有用戶端存取方法已啟用信箱。

    ```   
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```
   
   > [!NOTE]
    > 可能需要停用信箱的所有用戶端存取方法最多 60 分鐘。請注意停用這些存取方法不會中斷連線信箱擁有者他們目前登入。如果擁有者無法登入，然後將不會加以能夠存取其信箱之後已停用這些存取方法。 
  
2. 執行下列命令，以提高刪除項目保留期間的 30 天的最大值。這是假設目前的設定是早於 30 天。 

    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. 執行下列命令以停用單一項目復原。
    
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

   > [!NOTE]
    > 可能需要停用單一項目復原最多 60 分鐘。等到此期間經過不刪除 [可復原的項目] 資料夾中的項目。 
  
4. 執行下列命令，以防止受管理的資料夾助理員處理信箱。如先前所述，您可以停用受管理的資料夾助理員只有當保留鎖定 Office 365 保留原則不會套用至信箱。 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a>步驟 3： 從信箱移除所有保留

您可以從 [可復原的項目] 資料夾刪除項目之前的最後一個步驟是要移除所有保留 （即您在步驟 1 中識別） 信箱。如此當您從 [可復原的項目] 資料夾刪除之後將不會保留項目必須移除所有保留。下列各節包含移除不同類型的保留在信箱上的相關資訊。請參閱如需如何識別可能會被放置在信箱的類型保留的提示[的詳細資訊](#more-information)] 區段。如需詳細資訊，請參閱[如何識別的類型保留放在 Exchange Online 信箱](identify-a-hold-on-an-exchange-online-mailbox.md)。
  
> [!CAUTION]
> 先前所述，取出與記錄管理或法務部門才可從信箱移除保留。 
  
 ### <a name="litigation-hold"></a>訴訟暫止
  
執行下列命令在 Exchange Online PowerShell 從信箱移除訴訟暫止狀態。

```
Set-Mailbox <username> -LitigationHoldEnabled $false
```

   
> [!NOTE]
> 類似停用用戶端存取方法和單一項目復原，則可能需要最多 60 分鐘移除訴訟暫止狀態。直到經過此期間從 [可復原的項目] 資料夾不刪除項目。 
  
 ### <a name="in-place-hold"></a>原有範圍暫止
  
執行下列命令在 Exchange Online PowerShell 來識別信箱處於就地保留。使用您在步驟 1 中識別為 「 就地保留 GUID。 

```
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```
   
在識別為 「 就地保留之後，您可以使用 Exchange 系統管理中心 (EAC) 或 Exchange Online PowerShell 從保留移除信箱。如需詳細資訊，請參閱[建立或移除就地保留](https://go.microsoft.com/fwlink/?linkid=852668)。
  
 ### <a name="office-365-retention-policies-applied-to-specific-mailboxes"></a>Office 365 的保留原則套用至特定信箱
  
執行下列命令[Office 365 安全性&amp;規範中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)識別 Office 365 保留原則套用至信箱。使用 GUID (不包括`mbx`或`skp`字首) 您在步驟 1 中所識別的保留原則。 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```
   
識別保留原則之後，請移至**日期控管** \> **保留**] 頁面的 [安全性] 中&amp;規範中心編輯您在上一個步驟中識別的保留原則及移除清單中的信箱收件者所包含的保留原則。 
  
 ### <a name="organization-wide-office-365-retention-policies"></a>Office 365 全組織的保留原則
  
全組織與 Exchange 全 Office 365 的保留原則套用至組織中每個信箱。他們在組織層級 （而不是信箱層級） 套用，且當您在步驟 1 中執行**Get-organizationconfig**指令程式會傳回。執行下列命令[安全性&amp;規範中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)識別全組織的 Office 365 保留原則。使用 GUID (不包括`mbx`字首) 您在步驟 1 中識別之整個組織的保留原則。 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

識別全組織的 Office 365 保留原則之後，請移至**日期控管** \> **保留**] 頁面的 [安全性] 中&amp;規範中心編輯中識別的每個整個組織的保留原則上一個步驟，並將信箱新增至已排除的收件者的清單。執行此動作會從保留原則中移除使用者的信箱。 

### <a name="office-365-retention-labels"></a>Office 365 保留標籤

每當使用者套用設定成保留內容或保留與再刪除任何資料夾或信箱中的項目內容的標籤、 *ComplianceTagHoldApplied*信箱屬性是設定為**True**。在這種情況下，信箱會被視為在保留，就如同它已處於訴訟暫止狀態或指派給 Office 365 保留原則。

若要檢視*ComplianceTagHoldApplied*屬性的值，請在 Exchange Online PowerShell 中執行下列命令：

```
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

您已識別信箱是保留因為保留標籤套用到資料夾或項目之後，您可以使用安全性 & 規範中心中的內容搜尋工具來使用 ComplianceTag 搜尋條件來搜尋已標記的項目。如需詳細資訊，請參閱 「 搜尋條件 」 一節[關鍵字查詢](keyword-queries-and-search-conditions.md#conditions-for-common-properties)和搜尋條件的內容搜尋。

如需標籤的詳細資訊，請參閱[Office 365 概觀 （英文) 標籤](labels.md)。

 ### <a name="ediscovery-case-holds"></a>保留 eDiscovery 案例
  
執行下列命令[安全性&amp;規範中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)識別保留套用到信箱的 eDiscovery 案例相關聯。使用 GUID (不包括`UniH`前置詞) 的 ediscovery （英文） 保留您在步驟 1 中識別。請注意第二個命令會顯示保留相關聯; eDiscovery 案例的名稱第三個命令會顯示的保留名稱。 
  
```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```
$CaseHold.Name
```

您已識別的 eDiscovery 案例及保留名稱之後，請移至**搜尋&amp;調查** \> **eDiscovery**頁面的 [安全性]&amp;規範中心開啟情況下，並從保留移除信箱。如需詳細資訊，請參閱[管理 Office 365 安全性的 eDiscovery 案例&amp;規範中心](manage-ediscovery-cases.md)。
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a>步驟 4： 從信箱移除延遲保留

從信箱移除任何類型的保留之後， *DelayHoldApplied*信箱屬性的值是設定為**True**。發生此情況下一次受管理的資料夾助理員處理的信箱並偵測已移除保留。這會呼叫*延遲按住*並表示保留的實際移除延遲防止資料會永久刪除信箱的 30 天。（延遲保留的用途是提供系統管理員有機會搜尋或復原之後移除保留為止，將清除的信箱項目）。 當信箱處於延遲保留時，信箱會仍被視為不受限制的持續期間保留為信箱是否在訴訟暫止狀態。30 天後延遲保留過期，及 Office 365 將會自動嘗試移除 （由*DelayHoldApplied*屬性設**為 False**） 的延遲保留使真正移除保留為止。 

您可以刪除步驟 5 中的項目之前，您必須從信箱移除延遲保留。首先，決定是否延遲保留套用至信箱在 Exchange Online PowerShell 中執行下列命令：

```
Get-Mailbox <username> | FL DelayHoldApplied
```

如果*DelayHoldApplied*屬性的值設為**False**，延遲保留尚未放在信箱上。您可以前往 [步驟 5 和刪除 [可復原的項目] 資料夾中的項目。

如果*DelayHoldApplied*屬性的值設為**True**，執行下列命令以移除延遲保留：

```
Set-Mailbox <username> -RemoveDelayHoldApplied
```
請注意您必須具有的法律保留角色在 Exchange Online 使用*RemoveDelayHoldApplied*參數。

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a>步驟 5： 刪除 [可復原的項目] 資料夾中的項目

現在您已經準備好實際使用[Search-mailbox](https://go.microsoft.com/fwlink/?linkid=852595)指令程式在 Exchange Online PowerShell 中刪除 [可復原的項目] 資料夾中的項目。時執行**搜尋信箱**指令程式會有三個選項。 
  
- 刪除之前，讓您可以檢閱項目，必要時，才能刪除這些將項目複製到目標信箱。
    
- 將項目複製到目標信箱並刪除這些同一個命令中。
    
- 刪除項目而不將其複製到目標信箱。 
    
請注意在使用者的主要封存信箱 [可復原的項目] 資料夾中的項目也都會刪除時執行**搜尋信箱**指令程式。若要避免此問題，您可以包含*DoNotIncludeArchive*參數。與先前所述，如果自動展開封存啟用信箱、 * * Search-mailbox * * 指令程式不會刪除輔助封存信箱中的項目。如需關於自動展開封存，請參閱 ＜ [Overview of Office 365 中沒有限制之封存](unlimited-archiving.md)。
  
> [!NOTE]
> 如果您包括在搜尋查詢 （使用*SearchQuery*參數）， **Search-mailbox**指令程式會在搜尋結果中傳回最大值為 10000 個項目。因此如果您包括在搜尋查詢時，您可能必須執行**搜尋信箱**命令多次刪除 10000 個以上的項目。 
  
下列範例會顯示這些選項的每個命令語法。下列範例使用`-SearchQuery size>0`參數值，從 [可復原的項目] 資料夾中的所有子資料夾中刪除所有項目。如果您需要刪除符合特定條件的項目，您也可以使用*SearchQuery*參數來指定其他條件，例如日期範圍或郵件的主旨。請參閱[使用 SearchQuery 參數的其他範例](#other-examples-of-using-the-searchquery-parameter)下面的。 
  
### <a name="example-1"></a>範例 1

此範例會在使用者的 [可復原的項目] 資料夾中的所有項目複製至您的組織探索搜尋信箱中的資料夾。這可讓您永久刪除之前檢閱項目。

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>"
```

在上述範例中，則不需要將項目複製到 [探索搜尋信箱。您可以將郵件複製到任何目標信箱。不過，若要防止敏感性信箱資料存取，建議將郵件複製到已授權的人員限制存取的信箱。根據預設，預設探索搜尋信箱會限制存取至探索管理角色群組的成員在 Exchange Online。 
  
### <a name="example-2"></a>範例 2

本範例會在使用者的 [可復原的項目] 資料夾中的所有項目複製到貴組織的探索搜尋信箱中的資料夾，然後從使用者的 [可復原的項目] 資料夾刪除項目。

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>" -DeleteContent
```
 
### <a name="example-3"></a>範例 3

此範例會在使用者的可復原的項目] 資料夾中的所有項目刪除而不將其複製到目標信箱。 

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -DeleteContent
```

### <a name="other-examples-of-using-the-searchquery-parameter"></a>使用 SearchQuery 參數的其他範例

以下是一些範例使用*SearchQuery*參數來尋找特定的郵件。如果您使用*SearchQuery*參數來搜尋特定的項目，請考慮將搜尋結果複製到目標信箱，讓您可以檢閱搜尋結果並再修改查詢視之前刪除的搜尋結果。 
  
此範例會傳回包含 [主旨] 欄位中的特定片語的郵件。
  
```
SearchQuery 'subject:"MAIL_BOX VALIDATION/UPGRADE!!!"' 
```

此範例會傳回指定的日期範圍內所傳送的郵件。
  
```
SearchQuery 'sent>=06/01/2016 AND sent<=09/01/2016'
```
 
此範例會傳回至指定的人員所傳送的郵件。

```
SearchQuery 'to:garthf@alpinehouse.com'
```
   
### <a name="verify-that-items-were-deleted"></a>確認已刪除的項目

若要確認您是否已成功刪除的項目從 [可復原的項目] 資料夾的信箱，使用**Get-mailboxfolderstatistics 指令**指令程式在 Exchange Online PowerShell 檢查的大小和可復原的項目] 資料夾中的項目數。您可以比較與您在步驟 1 中收集的過這些統計資料。 
  
執行下列命令以取得目前的大小和項目總數資料夾和使用者的主要信箱中 [可復原的項目] 資料夾中的子資料夾中。 
  
```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
   
執行下列命令以取得中資料夾與使用者的封存信箱中 [可復原的項目] 資料夾中的子資料夾的大小和項目總數。 

```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
  
## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a>步驟 6： 還原成先前狀態的信箱

最後一個步驟是要還原的信箱回到先前的設定。這表示您在步驟 2 中變更的屬性重設並重新套用您在步驟 3 中移除保留。這包括：
  
- 變更刪除項目保留期間回到先前的值。或者，您可以只保留這設為 30 天內，最大值在 Exchange Online。
    
- 重新啟用單一項目復原。
    
- 重新啟用用戶端存取方法使其擁有人可以存取他們的信箱。
    
- 重新套用保留與您移除的 Office 365 保留原則。
    
- 重新啟用受管理的資料夾助理員處理的信箱。
    
> [!IMPORTANT]
> 我們建議您等待 24 小時之後重新套用保留或 Office 365 保留原則 （並確認已備妥） 重新啟用受管理的資料夾助理員處理信箱之前。 
  
在 Exchange Online PowerShell 中執行下列步驟 （依照指定的順序）。
  
1. 執行下列命令以變更刪除項目保留期間回到原來的數值。本範例假設先前設定為早於 30 天;例如 14 天。 
    
    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```
   
2. 執行下列命令來重新啟用單一項目復原。
   
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. 執行下列命令來重新啟用信箱的所有用戶端存取方法。
    
    ```
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```
   
4. 重新套用您在步驟 3 中移除保留。根據保留的類型，使用下列程序之一。
    
    **訴訟暫止**
    
    執行下列命令來重新啟用信箱的訴訟暫止狀態。
    
    ```
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    **原有範圍暫止**
    
    使用 EAC （或 Exchange Online PowerShell） 新增信箱回到就地保留。 
    
    **Office 365 的保留原則套用至特定信箱**
    
    使用安全性&amp;規範中心將信箱回復至 Office 365 保留原則。移至 [**日期控管** \> **保留**] 頁面的 [安全性] 中&amp;規範中心編輯保留原則，並回到 [保留原則套用至收件者] 清單中新增的信箱。 
    
    **Office 365 全組織的保留原則**
    
    如果您排除從原則移除整個組織或 Exchange 全保留原則，然後使用 [安全性]&amp;規範中心以從清單中移除信箱排除的使用者。移至 [**日期控管** \> **保留**] 頁面的 [安全性] 中&amp;規範中心編輯整個組織的保留原則，並移除已排除的收件者清單中的信箱。執行此動作會重新保留原則套用至使用者的信箱。 
    
    **保留 eDiscovery 案例**
    
    使用安全性&amp;規範中心新增信箱後保留與 eDiscovery 案例相關聯。移至 [**搜尋&amp;調查** \> **eDiscovery**頁面的 [安全性]&amp;規範中心開啟情況下，並新增回至保留的信箱。 
    
5. 執行下列命令，以允許在受管理的資料夾助理員處理一次的信箱。如先前所述，我們建議您等待 24 小時之後重新套用保留或 Office 365 保留原則 （並確認已備妥） 重新啟用受管理的資料夾助理員之前。 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```
   
6. 若要確認信箱具有已會回到先前的設定，您可以執行下列命令並再比較過您收集在步驟 1 中的設定。

    ```
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```
  
## <a name="more-information"></a>詳細資訊

以下是描述如何識別不同類型的保留當您執行**Get-mailbox**或**Get-organizationconfig**指令程式根據*InPlaceHolds*屬性中的值的表格。如需詳細資訊，請參閱[如何識別的類型保留放在 Exchange Online 信箱](identify-a-hold-on-an-exchange-online-mailbox.md)。

如先前清楚，您必須移除所有保留與 Office 365 之前信箱的保留原則可以成功地刪除 [可復原的項目] 資料夾中的項目。 
  
|**保留類型**|**範例值**|**如何識別保留**|
|:-----|:-----|:-----|
|訴訟暫止  <br/> | `True` <br/> |*LitigationHoldEnabled*屬性設為`True`。  <br/> |
|原有範圍暫止  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |*InPlaceHolds*屬性會包含信箱處於就地保留 GUID。您可以分清這是就地保留由於 GUID 不會開始使用前置詞。<br/> 您可以使用`Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL`取得資訊就地保留信箱上的 Exchange Online PowerShell 中的命令。  <br/> |
| 在 [安全性] 中的 office 365 保留原則&amp;規範中心套用至特定信箱  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> 或  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |當您執行**Get-mailbox**指令程式時， *InPlaceHolds*屬性也會包含 Office 365 Guid 保留原則套用至信箱。您可以識別保留原則因為 GUID 開頭`mbx`前置詞。請注意，如果保留原則的 GUID 開頭`skp`前置詞表示保留原則套用至 Skype 商務交談。<br/> 到 Office 365 身分識別保留原則套用至信箱執行下列命令安全性&amp;規範中心 PowerShell： <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>請務必移除`mbx`或`skp`prefix 當您執行此命令。  <br/> |
|整個組織的 Office 365 中安全性的保留原則&amp;規範中心  <br/> |沒有值  <br/> 或  <br/>  `-mbxe9b52bf7ab3b46a286308ecb29624696`（表示信箱不排除全組織的原則）  <br/> |即使當您執行**Get-mailbox**指令程式*InPlaceHolds*屬性是空的還是可能有一或多個整個組織的 Office 365 保留原則套用至信箱。  <br/> 若要確認此，您可以執行`Get-OrganizationConfig | FL InPlaceHolds`命令在 Exchange Online PowerShell 取得整個組織的 Office 365 保留原則之 Guid 的清單。整個組織的保留原則套用至 Exchange 信箱開始 GUID`mbx`首碼 ；例如`mbxa3056bb15562480fadb46ce523ff7b02`。<br/> 身分識別整個組織的 Office 365 保留原則套用至信箱，請執行下列命令安全性&amp;規範中心 PowerShell： <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>請注意是否信箱排除在整個組織的 Office 365 保留原則、 保留原則的 GUID 顯示在使用者信箱的*InPlaceHolds*屬性當您執行**Get-mailbox**指令程式 ；識別前置字元`-mbx`;例如，`-mbxe9b52bf7ab3b46a286308ecb29624696` <br/> |
|eDiscovery 案例保留安全性&amp;規範中心  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |*InPlaceHolds*屬性也會包含任何保留 eDiscovery 案例安全性相關聯的 GUID&amp;可能會被放置在信箱的規範中心。您可以分清這是因為 GUID 開頭的 eDiscovery 案件保留`UniH`前置詞。<br/> 您可以使用`Get-CaseHoldPolicy`指令程式的安全性&amp;規範中心 PowerShell 取得信箱保留相關聯的 eDiscovery 案例的相關資訊。例如，您可以執行此命令`Get-CaseHoldPolicy <hold GUID without prefix> | FL Name`顯示上信箱的大小寫保留的名稱。請務必移除`UniH`prefix 當您執行此命令。<br/><br/> 身分識別與關聯信箱的保留 eDiscovery 案例中，執行下列命令：<br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`


