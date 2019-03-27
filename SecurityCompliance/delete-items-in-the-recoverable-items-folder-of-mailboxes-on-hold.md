---
title: 刪除 [可復原的項目] 資料夾中項目保留狀態的雲端式信箱的系統管理說明
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
description: 系統管理員： 刪除 Exchange Online 信箱，使用者可復原的項目] 資料夾中的項目，即使該信箱處於合法持有。 這是有效的方法來刪除已不小心溢出至 Office 365 的資料。
ms.openlocfilehash: a1abfd73d96db6d67e1e1fe13d5487ac55c40344
ms.sourcegitcommit: c0d4fe3e43e22353f30034567ade28330266bcf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/27/2019
ms.locfileid: "30900112"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold---admin-help"></a>刪除 [可復原的項目] 資料夾中項目保留狀態的雲端式信箱的系統管理說明

若要防止意外或惡意刪除存在於 Exchange Online 信箱 [可復原的項目] 資料夾。 它也用來儲存項目會保留並存取 Office 365 合規性功能，例如保留和 eDiscovery 搜尋。 不過，在某些情況下的組織可能必須在他們必須刪除 [可復原的項目] 資料夾中已不小心保留的資料。 例如，使用者可能不知情的情況下傳送或轉寄電子郵件包含敏感資訊或可能會有嚴重的商務後果的資訊。 即使永久刪除的郵件，它可能對其會無限期保留，因為合法持有已放在信箱上。 此案例中稱為資料外洩，因為資料不小心溢出至 Office 365。 在這些情況下，您可以刪除 Exchange Online 信箱，使用者可復原的項目] 資料夾中的項目，即使該信箱處於保留狀態，以其中一個 Office 365 中的不同的保留功能。 這些類型的保留包含訴訟保留、 就地保留、 eDiscovery 保留和建立 Office 365 安全性中的 Office 365 保留原則&amp;合規性中心。 
  
 本文說明如何從保留的雲端架構信箱 [可復原的項目] 資料夾刪除項目。 此程序牽涉到停用信箱存取權，以及停用單一項目復原，停用受管理的資料夾助理員處理信箱暫時移除保留、 從可復原的項目] 資料夾刪除項目，然後還原信箱以其先前的設定。 以下是程序： 
  
[步驟 1： 收集信箱的相關資訊](#step-1-collect-information-about-the-mailbox)

[步驟 2： 準備信箱](#step-2-prepare-the-mailbox)

[步驟 3： 從信箱移除所有保留](#step-3-remove-all-holds-from-the-mailbox)

[步驟 4： 從信箱移除延遲保留](#step-4-remove-the-delay-hold-from-the-mailbox)

[步驟 5： 刪除 [可復原的項目] 資料夾中的項目](#step-5-delete-items-in-the-recoverable-items-folder)

[步驟 6： 將回復到之前的狀態的信箱](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> 本文所述的程序會導致資料被永久刪除 （清除） 從 Exchange Online 信箱。 這表示您從 [可復原的項目] 資料夾中刪除的郵件無法復原，而且不會為可供法律或其他規範用途。 如果您想要從一部分訴訟暫止狀態，原有範圍暫止，處於保留狀態的信箱刪除郵件保留電子文件探索，或建立 Office 365 安全性中的 Office 365 保留原則&amp;合規性中心，請洽詢您的記錄管理或法律移除保留之前的部門。 您的組織可能會有一個原則來定義是否要保留的信箱上或資料外洩事件會優先採用。 
  
## <a name="before-you-begin"></a>開始之前

- 您必須同時被指派下列管理角色，在 Exchange Online 來搜尋並刪除在步驟 5 中的 [可復原的項目] 資料夾中的郵件。
    
  - **信箱搜尋**-此角色可讓您搜尋您的組織中的信箱。 根據預設，Exchange 系統管理員未指派此角色。 若要自行指派此角色，將自己新增為 「 探索管理角色群組的成員在 Exchange Online。 
    
  - **信箱匯入 / 匯出**-此角色可讓您從使用者的信箱刪除郵件。 根據預設，此角色不指派給任何角色群組。 若要從使用者的信箱刪除郵件，您可以新增 「 信箱匯入 / 匯出 」 角色給組織管理角色群組在 Exchange Online。 
    
- 本文所述的程序不支援的非使用中信箱。 這是因為您無法重新套用保留 （或 Office 365 保留原則） 給非使用中信箱後移除它。 當您從非使用中的信箱移除保留時，它會變更為一般的虛刪除信箱，並將從您的組織永久刪除之後就會受管理的資料夾助理員所處理。
    
- 您無法執行此程序的各個信箱。 已指派給已鎖定保留鎖定與 Office 365 保留原則。 這是因為保留鎖定可防止您無法移除或從 Office 365 保留原則和停用受管理的資料夾助理員在信箱中排除信箱。 如需鎖定保留原則的詳細資訊，請參閱[鎖定保留原則](retention-policies.md#locking-a-retention-policy)。
    
- 如果信箱未處於暫止狀態 （或都不會有已啟用單一項目復原），您只可以從 [可復原的項目] 資料夾刪除項目。 如需如何執行這項操作的詳細資訊，請參閱[搜尋並刪除郵件](https://go.microsoft.com/fwlink/?linkid=852453)。
  
## <a name="step-1-collect-information-about-the-mailbox"></a>步驟 1： 收集信箱的相關資訊

此第一個步驟是從目標信箱，將會影響此程序收集選取的內容。 請務必記下這些設定，或將它們儲存到文字檔，因為您將會變更其中某些屬性，並從 [可復原的項目] 資料夾刪除項目之後，再回復為步驟 6 中的原始值。 以下是您需要收集的信箱內容清單。
  
-  *SingleItemRecoveryEnabled*和*RetainDeletedItemsFor* ;如有必要，您將會停用單一復原，並增加在步驟 3 中的已刪除的項目保留期間。 
    
-  *LitigationHoldEnabled*和*InPlaceHolds* ;您需要識別所有保留在信箱上，讓您可以在步驟 3 中，暫時移除它們。 請參閱如何識別可能置於信箱類型保留秘訣[的詳細資訊](#more-information)一節。 
    
此外，您需要取得信箱用戶端存取設定，以便您可以暫時停用它們讓其擁有人 （或其他使用者） 無法在此程序期間存取信箱。 最後，您可以在 [可復原的項目] 資料夾中取得目前的大小和項目數。 刪除在步驟 5 中的 [可復原的項目] 資料夾中的項目之後，您將使用這項資訊來確認已確實移除項目。
  
1. [連線至 Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554) (機器翻譯)。 請務必使用已被指派 Exchange Online 中的適當的管理角色的系統管理員帳戶的使用者名稱和密碼。 
    
2. 執行下列命令，以取得單一項目復原和刪除項目保留期間的相關資訊。

    ```
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   如果已啟用單一項目復原，您必須停用它在步驟 2 中。 如果已刪除的項目保留期間未設定為 30 天 （Exchange Online 中的最大值），然後您可以增加其在步驟 2 中。 
    
3. 執行下列命令，以取得信箱存取信箱的設定。 
    
    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   您將會停用所有的這些存取方法，在 [步驟 2。
    
4. 執行下列命令，以取得保留和 Office 365 保留原則套用到信箱的相關資訊。
    
    ```
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```


   > [!TIP]
    > 如果*InPlaceHolds*屬性中有太多的值，而且並非所有的顯示，您可以執行`Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds`命令，以顯示的個別行上的每個值。 
  
5. 執行下列命令，以取得任何全組織的 Office 365 保留原則的相關資訊。 

    ```
    Get-OrganizationConfig | FL InPlaceHolds
    ```
   如果您的組織有任何全組織的 Office 365 保留原則，您必須從步驟 3 中的這些原則中排除信箱。

   > [!TIP]
    > 如果*InPlaceHolds*屬性中有太多的值，而且並非所有的顯示，您可以執行`Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`命令，以顯示的個別行上的每個值。 
  
6. 執行下列命令，以取得目前的大小和項目數總計資料夾與使用者的主要信箱中 [可復原的項目] 資料夾中的子資料夾中。 

    ```
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   如果啟用使用者的封存信箱時，執行下列命令，以取得的大小和項目數總計資料夾和其封存信箱中 [可復原的項目] 資料夾中的子資料夾中。 

    ```s
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   當您刪除在步驟 5 中的項目時，您可以選擇要刪除或無法刪除使用者的主要的封存信箱中的 [可復原的項目] 資料夾中的項目。 請注意是否自動展開封存的信箱已啟用，將不會刪除輔助封存信箱中的項目。
  
## <a name="step-2-prepare-the-mailbox"></a>步驟 2： 準備信箱

收集和儲存信箱的相關資訊之後, 下一個步驟是準備信箱藉由執行下列工作： 
  
- **停用用戶端存取信箱**，使信箱擁有者無法存取其信箱和信箱資料進行任何變更，在此程序期間。 
    
- **增加的已刪除的項目保留期間**為 30 天 （Exchange Online 中的最大值），讓項目，不會清除從 [可復原的項目] 資料夾之前在步驟 5 中予以刪除。 
    
- **停用單一項目復原**的項目，不會保留 （適用於已刪除的項目保留期間的持續時間） 之後您刪除在步驟 5 中的 [可復原的項目] 資料夾。 
    
- **停用受管理的資料夾助理員**讓它不會處理信箱並保留您在步驟 5 中刪除的項目。 
    
在 Exchange Online PowerShell 中執行下列步驟。
  
1. 執行下列命令，以停用信箱的所有用戶端存取。 命令語法假設信箱上已啟用所有的用戶端存取方法。

    ```   
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```
   
   > [!NOTE]
    > 可能需要 60 分鐘的時間將停用信箱的所有用戶端存取方法。 請注意，停用這些存取方法不會中斷連線他們目前登入信箱擁有者。 如果擁有者未登入，然後他們將無法存取其信箱之後這些存取方法都會停用。 
  
2. 執行下列命令，以提高刪除項目保留期間的最大值為 30 天。 這會假設目前的設定是小於 30 天。 

    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. 執行下列命令，以停用單一項目復原。
    
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

   > [!NOTE]
    > 可能需要 60 分鐘的時間將停用單一項目復原。 不要刪除 [可復原的項目] 資料夾中的項目，直到在經過這段期間。 
  
4. 執行下列命令，以防止受管理的資料夾助理員處理信箱。 如先前所述，您可以停用受管理的資料夾助理員只有當使用保留鎖定的 Office 365 保留原則不會套用到信箱。 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a>步驟 3： 從信箱移除所有保留

您可以從 [可復原的項目] 資料夾刪除項目之前的最後一個步驟是移除所有保留 （您在步驟 1 中識別） 放置在信箱上。 如此將不會保留項目，當您從 [可復原的項目] 資料夾刪除之後，必須先移除所有保留。 下列各節包含不同類型的保留在信箱上的相關資訊。 請參閱如何識別可能置於信箱類型保留秘訣[的詳細資訊](#more-information)一節。 如需詳細資訊，請參閱 <<c0>如何識別的型別保留放在 Exchange Online 信箱。
  
> [!CAUTION]
> 如先前所述，請洽詢您的記錄管理或法務部門之前先從信箱移除保留。 
  
 ### <a name="litigation-hold"></a>訴訟資料暫留
  
下列命令在 Exchange Online PowerShell 中執行從信箱移除訴訟暫止狀態。

```
Set-Mailbox <username> -LitigationHoldEnabled $false
```

   
> [!NOTE]
> 類似於停用單一項目復原與用戶端存取方法，它可能需要 60 分鐘的時間將移除訴訟暫止狀態。 不要從 [可復原的項目] 資料夾刪除項目，直到經過這段期間。 
  
 ### <a name="in-place-hold"></a>原有範圍暫止
  
PowerShell 中執行下列命令在 Exchange Online 來識別信箱處於就地保留。 針對您在步驟 1 中識別為 「 就地保留使用 GUID。 

```
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```
   
識別 「 就地保留 」 狀態之後，您可以使用 Exchange 系統管理中心 (EAC) 或 Exchange Online PowerShell，從保留移除信箱。 如需詳細資訊，請參閱[建立或移除就地保留](https://go.microsoft.com/fwlink/?linkid=852668)。
  
 ### <a name="office-365-retention-policies-applied-to-specific-mailboxes"></a>Office 365 保留原則套用至特定信箱
  
在 [執行下列命令[Office 365 安全性&amp;合規性中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)來識別 Office 365 保留原則套用到信箱。 使用的 GUID (不包括`mbx`或`skp`字首) 您在步驟 1 中識別的保留原則。 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```
   
識別的保留原則之後，請移至**日期控管** \> **保留**] 頁面上，安全性&amp;合規性中心編輯您在上一個步驟中識別的保留原則，並從清單中移除信箱如果收件者包含在保留原則。 
  
 ### <a name="organization-wide-office-365-retention-policies"></a>整個組織的 Office 365 保留原則
  
全組織和 Exchange 整個 Office 365 保留原則會套用至組織中的每個信箱。 它們會套用在組織層級 （而不是信箱層級），當您在步驟 1 中執行**Get-organizationconfig** cmdlet 會傳回。 執行下列命令[安全性&amp;合規性中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)來識別全組織的 Office 365 保留原則。 使用的 GUID (不包括`mbx`字首) 針對您在步驟 1 中識別的全組織保留原則。 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

找出整個組織的 Office 365 保留原則之後，請移至**日期控管** \> **保留**] 頁面上，安全性&amp;合規性中心編輯中識別每個全組織保留原則上一個步驟，並將信箱新增至排除的收件者清單。 執行此動作會從保留原則中移除使用者的信箱。 

### <a name="office-365-retention-labels"></a>Office 365 保留標籤

每當使用者套用設定為保留內容或保留，然後刪除任何資料夾或其信箱中的項目內容的標籤， *ComplianceTagHoldApplied*信箱屬性設為**True**。 發生這種情況，信箱會被視為在保存時，就如同它已處於訴訟暫止狀態或指派給 Office 365 保留原則。

若要檢視*ComplianceTagHoldApplied*屬性的值，請在 Exchange Online PowerShell 中執行下列命令：

```
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

您已識別的信箱處於保留因為保留標籤套用至資料夾或項目之後，您可以使用安全性 & 合規性中心中的內容搜尋工具來使用 ComplianceTag 搜尋條件來搜尋標記項目。 如需詳細資訊，請參閱 「 搜尋條件 」 一節中[關鍵字查詢和搜尋條件的內容搜尋](keyword-queries-and-search-conditions.md#conditions-for-common-properties)。

如需標籤的詳細資訊，請參閱 <<c0>概觀的 Office 365 標籤。

 ### <a name="ediscovery-case-holds"></a>eDiscovery 案件保留
  
執行下列命令，[安全性&amp;合規性中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)來識別保留套用到信箱的 eDiscovery 案例相關聯。 使用的 GUID (不包括`UniH`字首) ediscovery 保留您在步驟 1 中識別。 請注意，第二個命令會顯示保留相關聯; 的 eDiscovery 案例的名稱第三個命令會顯示的保留名稱。 
  
```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```
$CaseHold.Name
```

您已識別的名稱的 eDiscovery 案例及保留之後，請移至**搜尋&amp;調查** \> **eDiscovery** ] 頁面上，安全性&amp;合規性中心，開啟案例，並從保留移除信箱。 如需詳細資訊，請參閱[管理 Office 365 安全性中的 eDiscovery 案例&amp;合規性中心](manage-ediscovery-cases.md)。
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a>步驟 4： 從信箱移除延遲保留

從信箱移除任何類型的保留後， *DelayHoldApplied*信箱屬性的值設為**True**。 發生此情況下一次受管理的資料夾助理員處理信箱，並會偵測已移除保留。 這稱為*延遲保留*，表示實際移除保留延遲，以防止資料會永久刪除信箱的 30 天。 （延遲保留的用途是讓系統管理員機會搜尋或復原之後移除保留為止，將清除的信箱項目）。 當延遲暫留時保留該信箱時，信箱會仍被視為不受限制的持續期間，保留為信箱是否訴訟暫止。 30 天後，延遲保留到期，與 Office 365 會自動嘗試移除延遲保留 （ *DelayHoldApplied*屬性設定為**False**），讓實際移除保留為止。 

您可以刪除在步驟 5 中的項目之前，您必須從信箱移除延遲保留。 首先，決定是否延遲保留套用至信箱的 Exchange Online PowerShell 中執行下列命令：

```
Get-Mailbox <username> | FL DelayHoldApplied
```

如果*DelayHoldApplied*屬性的值設為**False**，延遲有不被暫留保留信箱。 您可以移至步驟 5，並刪除 [可復原的項目] 資料夾中的項目。

如果*DelayHoldApplied*屬性的值設為**True**，執行下列命令，以移除延遲保留：

```
Set-Mailbox <username> -RemoveDelayHoldApplied
```
請注意，您必須獲指派法律保留角色在 Exchange Online 使用*RemoveDelayHoldApplied*參數。

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a>步驟 5： 刪除 [可復原的項目] 資料夾中的項目

現在，您已準備實際使用[Search-mailbox](https://go.microsoft.com/fwlink/?linkid=852595)指令程式在 Exchange Online PowerShell 中刪除 [可復原的項目] 資料夾中的項目。 執行**搜尋信箱**指令程式時，您會有三個選項。 
  
- 刪除之前，您可以檢查的項目，如有必要，刪除之前，請將項目複製到目標信箱。
    
- 將項目複製到目標信箱，並在同一個命令中刪除。
    
- 刪除項目，而不將它們複製到目標信箱。 
    
請注意，當您執行**Search-mailbox**指令程式時，也會刪除使用者的主要的封存信箱中的 [可復原的項目] 資料夾中的項目。 若要避免這種情況，您可以包含*DoNotIncludeArchive*參數。 如先前所述，如果自動展開封存會啟用信箱，並 * * 搜尋信箱 * * 指令程式不會刪除輔助封存信箱中的項目。 如需自動展開封存，請參閱[在 Office 365 中的無限制封存概觀](unlimited-archiving.md)。
  
> [!NOTE]
> 如果您使用包含在搜尋查詢 （ *SearchQuery*參數），此**Search-mailbox** cmdlet 會傳回最大值為 10000 個項目在搜尋結果中。 因此如果您包含在搜尋查詢，您可能必須執行**Search-mailbox**命令多次，以刪除 10000 個以上的項目。 
  
下列範例會顯示命令語法為每個這些選項。 這些範例使用`-SearchQuery size>0`參數值，從 [可復原的項目] 資料夾中的所有子資料夾中刪除所有項目。 如果您需要刪除符合特定條件的項目，您也可以使用*SearchQuery*參數來指定其他種條件，例如一則訊息或日期範圍的主旨。 請參閱下列的[其他使用 SearchQuery 參數的範例](#other-examples-of-using-the-searchquery-parameter)。 
  
### <a name="example-1"></a>範例 1

本範例會在使用者的 [可復原的項目] 資料夾中的所有項目複製至貴組織的探索搜尋信箱中的資料夾。 這可讓您永久刪除之前，先檢閱項目。

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>"
```

在前一個範例中，不需要將項目複製到 [探索搜尋信箱。 您可以將郵件複製到任何目標信箱。 不過，若要避免潛在機密的信箱資料存取，建議將郵件複製到存取限制 [已授權的人員的信箱。 根據預設，探索搜尋信箱的預設值會限制存取探索管理角色群組的成員在 Exchange Online。 
  
### <a name="example-2"></a>範例 2

本範例會在使用者的 [可復原的項目] 資料夾中的所有項目複製到貴組織的探索搜尋信箱中的資料夾，並再刪除使用者的 [可復原的項目] 資料夾中的項目。

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>" -DeleteContent
```
 
### <a name="example-3"></a>範例 3

本範例會刪除使用者的 [可復原的項目] 資料夾中的所有項目，而不將它們複製到目標信箱。 

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -DeleteContent
```

### <a name="other-examples-of-using-the-searchquery-parameter"></a>使用 SearchQuery 參數的其他範例

以下是一些使用*SearchQuery*參數來找出特定郵件的範例。 如果您使用*SearchQuery*參數來搜尋特定項目，請考慮將搜尋結果複製到目標信箱，以便您可以檢閱搜尋結果，然後修訂巨集查詢視之前刪除的搜尋結果。 
  
此範例會傳回包含 [主旨] 欄位中的特定片語的郵件。
  
```
SearchQuery 'subject:"MAIL_BOX VALIDATION/UPGRADE!!!"' 
```

此範例會傳回在指定的日期範圍內所傳送的郵件。
  
```
SearchQuery 'sent>=06/01/2016 AND sent<=09/01/2016'
```
 
此範例會傳回至指定的人員所傳送的郵件。

```
SearchQuery 'to:garthf@alpinehouse.com'
```
   
### <a name="verify-that-items-were-deleted"></a>確認已刪除項目

若要確認您已成功刪除的項目從信箱 [可復原的項目] 資料夾，使用**Get-mailboxfolderstatistics**指令程式在 Exchange Online PowerShell 來檢查的大小和可復原的項目] 資料夾中的項目數。 您可以比較以您在步驟 1 中所收集的這些統計資料。 
  
在 [執行下列命令，以取得目前的大小和項目數總計資料夾與使用者的主要信箱中 [可復原的項目] 資料夾中的子資料夾中。 
  
```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
   
執行下列命令，以取得的大小和項目數總計資料夾與使用者的封存信箱中 [可復原的項目] 資料夾中的子資料夾中。 

```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
  
## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a>步驟 6： 將回復到之前的狀態的信箱

最後一個步驟是要還原的信箱回到其先前的設定。 這表示重設您在步驟 2 中已變更的內容，並重新套用您在步驟 3 中移除保留。 其中包括：
  
- 變更刪除項目保留期間回到其先前的值。 或者，您可以只保留在 [Exchange 設定為 30 天，最大值這線上。
    
- 重新啟用單一項目復原。
    
- 重新啟用用戶端存取方法，讓其擁有人可以存取其信箱。
    
- 重新套用保留和您所移除的 Office 365 保留原則。
    
- 重新啟用受管理的資料夾助理員處理信箱。
    
> [!IMPORTANT]
> 我們建議您等候 24 小時後重新套用保留或 Office 365 保留原則 （並確認它已經準備就緒） 重新啟用受管理的資料夾助理員處理信箱之前。 
  
在 Exchange Online PowerShell 中執行下列步驟 （指定的順序）。
  
1. 執行下列命令，以變更刪除項目保留期間回到原來的數值。 這會假設先前的設定為小於 30 天的資料;例如 14 天。 
    
    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```
   
2. 執行下列命令，以重新啟用單一項目復原。
   
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. 執行下列命令，以重新啟用信箱的所有用戶端存取方法。
    
    ```
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```
   
4. 重新套用您在步驟 3 中移除保留。 根據保留的類型，使用下列程序之一。
    
    **訴訟資料暫留**
    
    執行下列命令，以重新啟用 [訴訟暫止的信箱。
    
    ```
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    **原有範圍暫止**
    
    使用 EAC （或 Exchange Online PowerShell），若要將信箱新增至 「 就地保留 」 狀態。 
    
    **Office 365 保留原則套用至特定信箱**
    
    使用安全性&amp;若要將信箱新增至 Office 365 保留原則與合規性中心。 移至**日期控管** \> **保留**] 頁面上，安全性&amp;合規性中心編輯保留原則，並將信箱新增至保留原則套用至收件者清單。 
    
    **整個組織的 Office 365 保留原則**
    
    如果您藉由排除從原則移除整個組織或 Exchange 全保留原則，然後使用安全性&amp;若要從清單中移除信箱的合規性中心中排除的使用者。 移至**日期控管** \> **保留**] 頁面上，安全性&amp;合規性中心編輯全組織保留原則，並從排除的收件者清單中移除信箱。 執行此動作將會重新將保留原則套用至使用者的信箱。 
    
    **eDiscovery 案件保留**
    
    使用安全性&amp;合規性中心，以將信箱新增備份保留與 eDiscovery 案例相關聯。 移至**搜尋&amp;調查** \> **eDiscovery** ] 頁面上，安全性&amp;合規性中心，開啟案例，並將信箱新增至保留。 
    
5. 執行下列命令，以允許受管理的資料夾助理員處理信箱一次。 如先前所述，我們建議您等候 24 小時後重新套用保留或 Office 365 保留原則 （並確認它已經準備就緒） 重新啟用受管理的資料夾助理員之前。 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```
   
6. 若要確認信箱已要還原為其先前的設定，您可以執行下列命令，並再比較到您在步驟 1 中所收集的設定。

    ```
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```
  
## <a name="more-information"></a>詳細資訊

以下是描述如何識別不同類型的保留根據*InPlaceHolds*屬性中的值，當您執行**Get-mailbox**或**Get-organizationconfig**指令程式時的資料表。 如需詳細資訊，請參閱 <<c0>如何識別的型別保留放在 Exchange Online 信箱。

如先前所述，您必須移除所有保留，並從信箱之前的 Office 365 保留原則可以成功刪除 [可復原的項目] 資料夾中的項目。 
  
|**保留類型**|**範例值**|**如何找出保留**|
|:-----|:-----|:-----|
|訴訟資料暫留  <br/> | `True` <br/> |*LitigationHoldEnabled*屬性設為`True`。  <br/> |
|原有範圍暫止  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |*InPlaceHolds*屬性包含信箱處於就地保留的 GUID。 您可以告訴這是在原有範圍暫止因為 GUID 不會啟動與前置詞。  <br/> 您可以使用`Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL`以取得有關 「 就地保留 」 狀態的資訊在信箱上的 Exchange Online PowerShell 中的命令。  <br/> |
| 安全性中的 office 365 保留原則&amp;合規性中心套用至特定信箱  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> 或  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |當您執行**Get-mailbox**指令程式時， *InPlaceHolds*屬性也會包含 Guid 的 Office 365 保留原則套用到信箱。 您可以識別保留原則，因為 GUID 開頭`mbx`前置詞。 請注意，如果保留原則的 GUID 開頭`skp`前置詞，表示保留原則套用至 Skype for Business 交談。  <br/> 要套用到信箱的身分識別 Office 365 保留原則，請執行下列命令中安全性&amp;合規性中心 PowerShell: <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>請務必移除`mbx`或`skp`當您執行此命令的前置詞。  <br/> |
|安全性中的全組織的 Office 365 保留原則&amp;合規性中心  <br/> |沒有值  <br/> 或  <br/>  `-mbxe9b52bf7ab3b46a286308ecb29624696`（表示信箱已排除的全組織原則）  <br/> |即使*InPlaceHolds*屬性是空的當您執行**Get-mailbox**指令程式時，仍可能有一或多個全組織的 Office 365 保留原則套用到信箱。  <br/> 若要確認此，您可以執行`Get-OrganizationConfig | FL InPlaceHolds`命令在 Exchange Online PowerShell，以取得整個組織的 Office 365 保留原則 Guid 的清單。 整個組織的保留原則套用至 Exchange 信箱的開頭的 GUID`mbx`字首;例如`mbxa3056bb15562480fadb46ce523ff7b02`。  <br/> 身分識別全組織的 Office 365 保留原則套用到信箱，請執行下列命令中安全性&amp;合規性中心 PowerShell: <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>請注意，是否從整個組織的 Office 365 保留原則中排除信箱，保留原則的 GUID 會顯示在使用者信箱的*InPlaceHolds*屬性當您執行**Get-mailbox**指令程式;它由前置詞`-mbx`;例如，`-mbxe9b52bf7ab3b46a286308ecb29624696` <br/> |
|eDiscovery 案例保留安全性&amp;合規性中心  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |*InPlaceHolds*屬性也包含安全性 eDiscovery 案例相關聯的任何保留的 GUID&amp;也可能會放置在信箱的合規性中心。 您可以分清這是 eDiscovery 案例保留，因為 GUID 開頭`UniH`前置詞。  <br/> 您可以使用`Get-CaseHoldPolicy`指令程式中安全性&amp;合規性中心 PowerShell，以取得在信箱上的保留相關聯的 eDiscovery 案例的相關資訊。 例如，您可以執行此命令`Get-CaseHoldPolicy <hold GUID without prefix> | FL Name`來顯示在信箱上的案例保留的名稱。 請務必移除`UniH`當您執行此命令的前置詞。  <br/><br/> 身分識別與相關聯的信箱上保留的 eDiscovery 案例中，執行下列命令：<br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`


