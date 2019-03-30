---
title: 增加保留信箱可復原的項目配額
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a8bdcbdd-9298-462f-b889-df26037a990c
description: '啟用封存信箱，並開啟自動展開封存增加的 Office 365 中的信箱 [可復原的項目] 資料夾的大小。 '
ms.openlocfilehash: f419da5b1b42d52433e9fc288aa5b401a2123c1c
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2019
ms.locfileid: "30998966"
---
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a>增加保留信箱可復原的項目配額

預設保留原則 — 名為 「 預設 MRM 原則，也就是 Exchange Online 中的自動套用至新的信箱包含名為 [可復原的項目 14 天移至封存的保留標記。 此保留標記移動項目從使用者的主要信箱中的 [可復原的項目] 資料夾至使用者的封存信箱中可復原的項目資料夾後的 14 天保留期間到期的項目。 針對此動作，必須啟用使用者的封存信箱。 如果未啟用封存信箱，會不採取任何動作，這表示中可復原的項目資料夾上的信箱保留, 的項目不會將移至封存信箱後的 14 天保留期間到期。 因為不會刪除保留狀態的信箱中，有可能，可能會超過 [可復原的項目] 資料夾的儲存配額，尤其是如果未啟用使用者的封存信箱。 
  
若要協助減少超過此限制，[可復原的項目] 資料夾的儲存配額會自動增加從 30 GB 至 100 GB 時保留信箱在 Exchange Online。 如果啟用封存信箱時，封存信箱中 [可復原的項目] 資料夾的儲存配額是也從 30 GB 增加到 100GB。 如果自動展開封存中可用的功能在 Exchange Online 已啟用，在使用者的封存中 [可復原的項目] 資料夾的儲存配額會無限制。
  
 下表摘要說明 [可復原的項目] 資料夾的儲存配額。 
  
|**可復原的項目] 資料夾的位置**|**不保留的信箱**|**保留的信箱**|
|:-----|:-----|:-----|
|主要信箱  <br/> |30 GB  <br/> |100 GB  <br/> |
|封存信箱<sup>\*</sup> <br/> |無限制  <br/> |無限制  <br/> |
|**[可復原的項目] 資料夾的總儲存配額** <br/> |無限制  <br/> |無限制  <br/> |
   
> [!NOTE]
> <sup>\*</sup>封存信箱的儲存配額為 100 GB 的使用者使用 Exchange Online (Plan 2) 授權。 不過，自動展開封存開啟時保留的信箱，封存信箱和可復原的項目] 資料夾的儲存配額增加為 110 GB。 必要時，將會佈建額外的封存儲存空間這會導致不受限制的封存儲存空間量。 如需自動展開封存，請參閱[在 Office 365 中的無限制封存概觀](unlimited-archiving.md)。 
  
當主要信箱的保留狀態的信箱中的 [可復原的項目] 資料夾的儲存配額接近限制時，您可以執行下列動作：
  
- **啟用封存信箱，並開啟自動展開封存**-您可以啟用 [可復原的項目] 資料夾不受限制的儲存容量只要啟用封存信箱，並再開啟自動展開封存功能在 Exchange 中線上。 這會導致 110 GB 的主要信箱和使用者的封存中的 [可復原的項目] 資料夾的儲存容量無限的量中可復原的項目] 資料夾。 請參閱如何：[啟用封存信箱中的安全性 & 合規性中心](enable-archive-mailboxes.md)，並[啟用 Office 365 中的無限制封存](enable-unlimited-archiving.md)。
    
    > [!NOTE]
    > 啟用接近超出可復原的項目] 資料夾的儲存配額的信箱的封存後，您可能想要執行受管理的資料夾助理員來手動觸發助理員，以處理信箱，以便過期的項目都會移封存信箱中 [可復原項目] 資料夾。 如需相關指示，請參閱 「[步驟 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) 」。 請注意其他使用者的信箱中的項目，可能會移至新的封存信箱。 請考慮告知使用者，可能會發生此之後啟用封存信箱。 
  
- **建立自訂保留原則的信箱保留**-除了啟用封存信箱及自動展開封存信箱的訴訟暫止或就地保留，您可能也想要建立自訂保留原則的信箱上保留。 這讓我們您保留原則套用至預設 MRM 原則套用至不保留的信箱與不同的保留的信箱。 這可讓您可以套用專為保留信箱的保留標記。 這包括建立新的保留標記可復原的項目] 資料夾。 
    
本主題的其餘部分說明建立自訂保留原則的信箱保留的逐步程序。
  
[步驟 1： 建立自訂保留標籤的 [可復原的項目] 資料夾](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)

[[步驟 2： 建立新的保留原則的信箱保留](#step-2-create-a-new-retention-policy-for-mailboxes-on-hold)

[步驟 3： 將新的保留原則套用至保留的信箱](#step-3-apply-the-new-retention-policy-to-mailboxes-on-hold)

[（選用）步驟 4： 執行受管理的資料夾助理員套用新的保留設定](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)
  
## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a>步驟 1： 建立自訂保留標籤的 [可復原的項目] 資料夾

第一個步驟是建立自訂保留標籤 （稱為 「 保留原則標記或 RPT） 的 [可復原的項目] 資料夾。 如先前所述，此 RPT 會移動項目，從使用者的主要信箱中的 [可復原的項目] 資料夾至使用者的封存信箱中 [可復原的項目] 資料夾。 您必須使用 PowerShell 來建立 rpt，適用於 [可復原的項目] 資料夾。 您無法使用 Exchange 系統管理中心 (EAC)。 
  
1. [使用遠端 PowerShell 連線到 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=517283)
    
2. 執行下列命令，以建立新的 RPT，[可復原的項目] 資料夾： 
    
    ```
    New-RetentionPolicyTag -Name <Name of RPT> -Type RecoverableItems -AgeLimitForRetention <Number of days> -RetentionAction MoveToArchive
    ```

    例如，下列命令會建立 rpt，適用於名為 「 可復原的項目上的信箱 30 天保留 」，為 30 天保留期間使用的可復原的項目] 資料夾。 這表示，項目中 [可復原的項目] 資料夾 30 天之後，它將會移至使用者的封存信箱中 [可復原的項目] 資料夾。
    
    ```
    New-RetentionPolicyTag -Name "Recoverable Items 30 days for mailboxes on hold" -Type RecoverableItems -AgeLimitForRetention 30 -RetentionAction MoveToArchive
    ```

    > [!TIP]
    > 我們建議可復原的項目 RPT 的保留期間 （ _AgeLimitForRetention_參數所定義） 會印會套用至信箱的刪除項目保留期間相同。 這可讓使用者的整個已刪除的項目保留期間它們移至封存信箱之前，復原刪除的項目。 在前一個範例中，保留期間設為根據信箱已刪除的項目保留期間同時也是 30 天的 30 天。 Exchange Online 信箱預設會將刪除的項目保留 14 天。 但您可以變更此設定最大值為 30 天。 如需詳細資訊，請參閱[變更 Exchange Online 信箱的刪除項目保留期間](https://go.microsoft.com/fwlink/p/?LinkId=286940)。 
  
## <a name="step-2-create-a-new-retention-policy-for-mailboxes-on-hold"></a>步驟 2： 建立新的保留原則的信箱保留

下一步是建立新的保留原則，並將保留標記新增至，包括可復原的項目 RPT，您在步驟 1 中建立。 此新原則會套用至下一個步驟中保留的信箱。 
  
建立新的保留原則之前，請決定您想要新增其他保留標記。 如需保留標記新增至預設 MRM 原則的清單，以及建立新的保留標記的相關資訊，請參閱下列各項：
  
- [預設保留原則在 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=746954)
    
- [支援保留原則標記的預設資料夾](https://go.microsoft.com/fwlink/p/?LinkId=746957)
    
- 「 建立保留標記 」 一節主題中的 < <b0>Create a Retention Policy</b0> 。
    
您可以使用 EAC 或 Exchange Online PowerShell 來建立保留原則。
  
### <a name="use-the-eac-to-create-a-retention-policy"></a>使用 EAC 來建立保留原則
  
1. 在 EAC 中，移至 [**規範管理** \> **保留原則**，然後按一下 [**新增**![加入圖示](media/ITPro-EAC-AddIcon.gif)。
    
2. 在**新的保留原則**] 頁面的 [**名稱**] 中，輸入描述用途的保留原則; 的名稱例如， **MRM Policy for 保留的信箱**。 
    
3. [**保留標記**，按一下 [**新增**![加入圖示](media/ITPro-EAC-AddIcon.gif)。
    
4. 在清單中的保留標記，選取 [可復原的項目 RPT，您在步驟 1 中建立，然後按一下 [**新增]**。
    
    ![選取自訂的 [可復原的項目] 保留標記](media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)
  
5. 選取要新增至保留原則的其他保留標記。 例如，您可能要新增相同的標籤，包含在預設 MRM 原則。
    
6. 當您完成新增保留標記時，按一下 [**確定]**。
    
7. 按一下 [**儲存**] 以建立新的保留原則。 
    
    請注意，連結至保留原則的保留標記會顯示在詳細資料窗格中。
    
    ![連結到保留原則的保留標記，會顯示在詳細資料窗格中](media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)
  
### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a>使用 Exchange Online PowerShell 來建立保留原則
  
執行下列命令，以建立新的保留原則的信箱保留。 
  
```
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>

```

例如，下列命令會建立在上圖中顯示的連結的保留標記與保留原則。
  
```
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```
  
## <a name="step-3-apply-the-new-retention-policy-to-mailboxes-on-hold"></a>步驟 3： 將新的保留原則套用至保留的信箱

最後一個步驟是套用您在步驟 2 中要保留的信箱在組織中建立的新保留原則。 若要將保留原則套用至單一信箱或多個信箱，您可以使用 EAC 或 Exchange Online PowerShell。 
  
### <a name="use-the-eac-to-apply-the-new-retention-policy"></a>使用 EAC 套用新的保留原則
  
1. 前往 [**收件者** \> **信箱**。
    
2. 在清單檢視中，選取您想要套用保留原則的信箱，然後按一下 [**編輯**![編輯圖示](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。
    
3. 在 [**使用者信箱**] 頁面上，按一下 [**信箱功能**]。
    
4. [**保留原則**] 中，選取您在步驟 2 中建立的保留原則，然後按一下 [**儲存**。
    
您也可以使用 EAC 將保留原則套用至多個信箱。
  
1. 前往 [**收件者** \> **信箱**。
    
2. 在清單檢視中，使用 Shift 鍵或 Ctrl 鍵來選取多個信箱。
    
3. 在詳細資料窗格中，按一下 [其他選項]****。
    
4. 在 [保留原則]**** 下方，按一下 [更新]****。
    
5. 在 [**大量指派保留原則**] 頁面上，選取您在步驟 2 中建立的保留原則，然後按一下 [**儲存**。 
    
### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a>使用 Exchange Online PowerShell 來套用新的保留原則
  
您可以使用 Exchange Online PowerShell 將新的保留原則套用至單一信箱。 但的 PowerShell 係數力量，您可以使用它來快速找出所有您組織中的信箱訴訟暫止，或在原有範圍暫止，並在再將新的保留原則套用到所有信箱保留在單一命令。 以下是一些使用 Exchange PowerShell 將保留原則套用至一或多個信箱的範例。 在步驟 2 中建立保留原則套用的所有範例。
  
此範例會將新的保留原則套用到 Pilar Pinilla 的信箱。
  
```
Set-Mailbox "Pilar Pinilla" -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

此範例會將新的保留原則套用至組織中的訴訟暫止的所有信箱。
  
```
$LitigationHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'}
```

```
$LitigationHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

本範例會將新的保留原則套用於組織中所有位於原有範圍暫止的信箱。
  
```
$InPlaceHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null}
```

```
$InPlaceHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

若要確認已套用新的保留原則，您可以使用**Get-mailbox**指令程式。 
  
以下是一些範例，以確認在上述範例中的命令會套用到信箱訴訟暫止和就地保留 」 狀態的信箱的 「 MRM 原則的信箱上保留 」 的保留原則。
  
```
Get-Mailbox "Pilar Pinilla" | Select RetentionPolicy
```

```
Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'} | FT DisplayName,RetentionPolicy -Auto
```

```
Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null} | FT DisplayName,RetentionPolicy -Auto
```
  
## <a name="optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings"></a>（選用）步驟 4： 執行受管理的資料夾助理員套用新的保留設定

您將新的保留原則套用至保留的信箱之後，它可能需要多達 7 天在 Exchange Online 的受管理的資料夾助理員處理程序使用新的保留原則中設定這些信箱。 而不是等待受管理的資料夾助理員執行，您可以使用**Start-managedfolderassistant** cmdlet 手動觸發助理員，以處理已套用至新的保留原則的信箱。 
  
執行下列命令，以啟動受管理的資料夾助理員 Pilar Pinilla 的信箱。
  
```
Start-ManagedFolderAssistant "Pilar Pinilla"
```

執行下列命令，以啟動受管理的資料夾助理員的所有信箱保留。
  
```
$MailboxesOnHold = Get-Mailbox -ResultSize unlimited | Where-Object {($_.InPlaceHolds -ne $null) -or ($_.LitigationHoldEnabled -eq "True")}
```

```
$MailboxesOnHold.DistinguishedName | Start-ManagedFolderAssistant
```

## <a name="more-information"></a>詳細資訊

- 啟用使用者的封存信箱之後，請考慮告知使用者他們的信箱 （不只是 [可復原的項目] 資料夾中項目） 中的其他項目可能會移至封存信箱。 這是因為預設 MRM 原則指派給 Exchange Online 信箱包含兩個年度的項目已傳遞至信箱或所建立的日期之後將項目移至封存信箱的保留標記 （名為 Default 2 年移至封存）使用者。 如需詳細資訊，請參閱[Exchange Online 中的預設保留原則](https://go.microsoft.com/fwlink/p/?LinkId=746954)
    
- 啟用使用者的封存信箱之後，也可能會告訴使用者，他們可以復原刪除的項目在其封存信箱中 [可復原的項目] 資料夾中。 他們可以在 Outlook 中執行這在封存信箱中，選取 [**刪除的項目**] 資料夾，然後按一下 [**首頁**] 索引標籤上的 [**復原刪除的項目從伺服器**。如需有關復原已刪除的項目的詳細資訊，請參閱[復原已刪除的 Outlook for Windows 中的項目](https://go.microsoft.com/fwlink/p/?LinkId=624829)。 
