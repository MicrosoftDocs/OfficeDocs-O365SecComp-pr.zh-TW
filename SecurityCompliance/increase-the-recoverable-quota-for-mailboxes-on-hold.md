---
title: 增加保留信箱的「可復原的項目」配額
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a8bdcbdd-9298-462f-b889-df26037a990c
description: '啟用封存信箱並開啟自動展開封存增加的 Office 365 中的信箱 [可復原的項目] 資料夾的大小。 '
ms.openlocfilehash: ebb052ba17ba8a84076e1e75a82713cc5cf437a1
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218473"
---
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a>增加保留信箱的「可復原的項目」配額

預設保留原則-名為預設 MRM 原則--亦即會自動套用至新的信箱在 Exchange Online 中包含名為可復原的項目 14 天移至封存其保留標記。此保留標記移動項目從使用者的主要信箱中的 [可復原的項目] 資料夾至使用者的封存信箱中 [可復原的項目] 資料夾後的 14 天保留期間到期的項目。這會發生，必須啟用使用者的封存信箱。如果未啟用封存信箱，會不採取任何動作，這表示可復原的項目保留信箱上的資料夾中的項目都移到封存信箱後的 14 天保留期間到期。Nothing 從保留信箱中刪除，因為有可能可能會超過儲存配額可復原的項目] 資料夾，特別是如果未啟用使用者的封存信箱。 
  
若要協助減少超過此限制的機會、 儲存配額可復原的項目] 資料夾是自動從增加 30 GB 100 gb 保留處於時為信箱在 Exchange Online。如果已啟用封存信箱，封存信箱中的 [可復原的項目] 資料夾的存放區配額也增加從 30 GB 100 gb。如果自動展開封存功能在 Exchange Online 已啟用、 [可復原的項目] 資料夾中使用者的封存儲存配額將不受限制。
  
  下表摘要說明 [可復原的項目] 資料夾的儲存配額。 
  
|**[可復原的項目] 資料夾的位置**|**未保留的信箱**|**保留的信箱**|
|:-----|:-----|:-----|
|主要信箱  <br/> |30 GB  <br/> |100 GB  <br/> |
|封存信箱<sup>\*</sup> <br/> |無限制  <br/> |無限制  <br/> |
|**[可復原的項目] 資料夾的儲存配額總計** <br/> |無限制  <br/> |無限制  <br/> |
   
> [!NOTE]
> <sup>\*</sup>封存信箱的初始儲存配額為 100 GB 具有 Exchange Online (Plan 2) 授權的使用者。但是，自動展開封存開啟時上保留信箱、 封存信箱與 [可復原的項目] 資料夾的存放區配額增加為 110 GB。額外的封存儲存空間在佈建時所需結果中封存儲存區中不受限制的數量。如需關於自動展開封存，請參閱[Overview of Office 365 中沒有限制之封存](unlimited-archiving.md)。 
  
在保留信箱的主要信箱中，當 [可復原的項目] 資料夾的儲存配額接近限制時，您可以執行下列動作︰
  
- **啟用封存信箱並開啟自動展開封存**-您可以只是透過啟用封存信箱並再開啟自動展開封存功能 Exchange 中啟用 [可復原的項目] 資料夾不受限制的儲存容量線上。這會產生 110 GB 主要信箱與使用者的封存中的 [可復原的項目] 資料夾的儲存容量不受限制的數量的可復原的項目] 資料夾。請參閱如何：[啟用封存信箱在 Office 365 安全性&amp;規範中心](enable-archive-mailboxes.md)並[啟用 Office 365 中沒有限制之封存](enable-unlimited-archiving.md)。
    
    > [!NOTE]
    > 啟用封存信箱的接近超過儲存配額可復原的項目] 資料夾以之後，您可能會想要執行受管理的資料夾助理員以手動觸發的移到期的項目處理的信箱助理員封存信箱中的可復原的項目資料夾。請參閱指示的[步驟 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) 。請注意其他使用者的信箱中的項目可能會移至新的封存信箱。請考慮告知使用者這可能會發生之後您啟用封存信箱。 
  
- **建立自訂的保留原則的信箱上保留**-啟用封存信箱與自動展開封存信箱訴訟暫止或就地保留功能，以及可能也想要在建立自訂的保留原則的信箱保留。這讓我們您保留原則套用至預設 MRM 原則套用至不保留的信箱與不同的保留信箱。這可讓您可以套用特別設計上保留信箱的保留標記。這包括建立新的保留標記可復原的項目] 資料夾。 
    
本主題的其餘部分說明為保留信箱建立自訂保留原則的逐步程序。
  
[步驟 1：為 [可復原的項目] 資料夾建立自訂保留標籤](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)

[[步驟 2： 建立新的保留原則的信箱保留](#step-2-create-a-new-retention-policy-for-mailboxes-on-hold)

[步驟 3：將新的保留原則套用至保留信箱](#step-3-apply-the-new-retention-policy-to-mailboxes-on-hold)

[(選用) 步驟 4：執行受管理的資料夾助理員套用新的保留設定](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)
  
## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a>步驟 1：為 [可復原的項目] 資料夾建立自訂保留標籤

第一個步驟是建立自訂保留標記 （稱為 「 保留原則標記或印） 可復原的項目] 資料夾。如先前所述，此印會移動項目至使用者的封存信箱中 [可復原的項目] 資料夾從使用者的主要信箱中的 [可復原的項目] 資料夾。您必須使用 PowerShell 建立印可復原的項目] 資料夾。您無法使用 Exchange 系統管理中心 (EAC)。 
  
1. [使用遠端 PowerShell 連線到 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=517283)
    
2. 執行下列命令為 [可復原的項目] 資料夾建立新的 RPT：  
    
    ```
    New-RetentionPolicyTag -Name <Name of RPT> -Type RecoverableItems -AgeLimitForRetention <Number of days> -RetentionAction MoveToArchive
    ```

    例如，下列命令會為 [可復原的項目] 資料夾建立名為 「保留信箱可復原的項目 30 天」的 RPT，保留期限為 30 天。這表示當項目在 [可復原的項目] 資料夾中停留 30 天後，將會移至使用者封存信箱中的 [可復原的項目] 資料夾。
    
    ```
    New-RetentionPolicyTag -Name "Recoverable Items 30 days for mailboxes on hold" -Type RecoverableItems -AgeLimitForRetention 30 -RetentionAction MoveToArchive
    ```

    > [!TIP]
    > 建議您保留期間 （ _AgeLimitForRetention_參數所定義） 的可復原的項目印會印會套用至信箱已刪除的項目保留期間相同。這可讓使用者整個刪除項目保留期間復原已刪除的項目之前他們會移到封存信箱。在上述範例中，保留期間設為 30 天的信箱已刪除的項目保留期間也是 30 天的假設情況為基礎。Exchange Online 信箱會依預設設定為 14 天內，保留已刪除的項目。但是您可以變更此設定最大值為 30 天。如需詳細資訊，請參閱[變更 Exchange Online 信箱的刪除項目保留期間](https://go.microsoft.com/fwlink/p/?LinkId=286940)。 
  
## <a name="step-2-create-a-new-retention-policy-for-mailboxes-on-hold"></a>步驟 2：為保留信箱建立新的保留原則

下一個步驟是建立新的保留原則，並在其中新增保留標記，包括您在步驟 1 中建立的可復原的項目 RPT。下一個步驟會將這個新的原則會套用至保留信箱。  
  
在建立新的保留原則之前，請決定您想要新增的其他保留標記。如需有關新增至預設 MRM 原則的保留標記清單及建立新保留標籤的資訊，請參閱下列資源︰
  
- [預設的保留原則 in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=746954)
    
- [支援保留原則標記的預設資料夾](https://go.microsoft.com/fwlink/p/?LinkId=746957)
    
- [Create a Retention Policy](https://go.microsoft.com/fwlink/p/?LinkId=404422)主題中 「 建立保留標記 」 小節。
    
您可以使用 EAC 或 Exchange Online PowerShell 來建立保留原則。
  
### <a name="use-the-eac-to-create-a-retention-policy"></a>使用 EAC 建立保留原則
  
1. 在 EAC 中，移至 [**規範管理** \> **保留原則**，然後按一下 [**新增**![新增圖示](media/ITPro-EAC-AddIcon.gif)。
    
2. 在 [**新的保留原則**] 頁面上的 [**名稱**] 下輸入描述用途的保留原則的名稱例如**MRM 原則保留的信箱**。 
    
3. [**保留標記**，按一下 [**新增**![新增圖示](media/ITPro-EAC-AddIcon.gif)。
    
4. 在清單中的保留標記，選取 [可復原的項目印您在步驟 1 中建立並再按一下 [**新增**]。
    
    ![選取自訂的 [可復原的項目] 保留標記](media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)
  
5. 選取其他要新增至保留原則的保留標記。例如，您可能想要新增預設 MRM 原則包含的相同標記。
    
6. 新增保留標記完成後，按一下 [**確定]**。
    
7. 按一下 [**儲存**] 以建立新的保留原則。 
    
    請注意，連結至保留原則的保留標記會顯示在詳細資料窗格中。
    
    ![連結到保留原則的保留標記，會顯示在詳細資料窗格中](media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)
  
### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a>使用 Exchange Online PowerShell 來建立保留原則
  
執行下列命令為保留信箱建立新的保留原則。  
  
```
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>

```

例如，下列命令會建立保留原則和上圖所示的連結保留標記。
  
```
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```
  
## <a name="step-3-apply-the-new-retention-policy-to-mailboxes-on-hold"></a>步驟 3：將新的保留原則套用至保留信箱

最後一個步驟是您在步驟 2 到信箱保留組織中建立新保留原則套用。您可以使用 EAC 或 Exchange Online PowerShell 將保留原則套用至單一信箱或多個信箱。 
  
### <a name="use-the-eac-to-apply-the-new-retention-policy"></a>使用 EAC 套用新的保留原則
  
1. 移至 [**收件者** \> **信箱**。
    
2. 在清單檢視中，選取您想要套用保留原則]、 的信箱] 和 [**編輯**![編輯圖示](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。
    
3. 在 [**使用者信箱**] 頁面上按一下 [**信箱功能**]。
    
4. [**保留原則**] 下選取您在步驟 2 中建立的保留原則] 和 [**儲存**。
    
您也可以使用 EAC 將保留原則套用至多個信箱。
  
1. 移至 [**收件者** \> **信箱**。
    
2. 在清單檢視中，使用 Shift 鍵或 Ctrl 鍵來選取多個信箱。
    
3. 在 [詳細資料] 窗格中，按一下 [**更多選項]**。
    
4. [**保留原則**] 下按一下 [**更新**]。
    
5. 在 **[大量指派保留原則]** 頁面上，選取您在步驟 2 建立的保留原則，然後按一下 **[儲存]**。  
    
### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a>使用 Exchange Online PowerShell 套用新的保留原則
  
您可以使用 Exchange Online PowerShell 將新的保留原則套用至單一信箱。但實際的 PowerShell 電源可以使用可快速識別所有訴訟暫止狀態或就地保留功能，並再新保留原則套用至所有的信箱在組織中信箱保留在單一命令中。以下是一些使用 Exchange PowerShell 將保留原則套用至一或多個信箱的範例。步驟 2 中建立保留原則套用的所有範例。
  
此範例將新的保留原則套用至 Pilar Pinilla 的信箱。
  
```
Set-Mailbox "Pilar Pinilla" -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

此範例將新的保留原則套用至組織中的所有訴訟資料暫留信箱。
  
```
$LitigationHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'}
```

```
$LitigationHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

此範例將新的保留原則套用至組織中的所有就地保留信箱。
  
```
$InPlaceHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null}
```

```
$InPlaceHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

您可以使用 **Get-Mailbox** Cmdlet 來確認已套用新的保留原則。 
  
以下這些範例可確認先前範例中的命令已將「保留信箱的 MRM 原則」保留原則，套用至訴訟資料暫留的信箱和就地保留的信箱。
  
```
Get-Mailbox "Pilar Pinilla" | Select RetentionPolicy
```

```
Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'} | FT DisplayName,RetentionPolicy -Auto
```

```
Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null} | FT DisplayName,RetentionPolicy -Auto
```
  
## <a name="optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings"></a>(選用) 步驟 4：執行受管理的資料夾助理員套用新的保留設定

您將新的保留原則套用至信箱保留之後，可能很多達 7 天在 Exchange Online 的受管理的資料夾助理員處理使用新的保留原則中設定這些信箱。而非等候受管理的資料夾助理員執行，您可以使用**Start-managedfolderassistant**指令程式來手動觸發處理套用至新的保留原則的信箱助理員。 
  
執行下列命令，對 Pilar Pinilla 的信箱啟動受管理的資料夾助理員。
  
```
Start-ManagedFolderAssistant "Pilar Pinilla"
```

執行下列命令，對所有保留信箱啟動受管理的資料夾助理員。
  
```
$MailboxesOnHold = Get-Mailbox -ResultSize unlimited | Where-Object {($_.InPlaceHolds -ne $null) -or ($_.LitigationHoldEnabled -eq "True")}
```

```
$MailboxesOnHold.DistinguishedName | Start-ManagedFolderAssistant
```

## <a name="more-information"></a>詳細資訊

- 啟用使用者的封存信箱之後，請考慮告知他們的信箱 （而不只可復原的項目] 資料夾中項目） 中的其他項目可能會移至封存信箱的使用者。這是因為預設 MRM 原則指派給 Exchange Online 信箱包含將項目移至封存信箱項目已傳遞至信箱或所建立的日期之後的兩個年度其保留標記 （具名的預設 2 年移至封存）使用者。如需詳細資訊，請參閱[Exchange Online 中的預設保留原則](https://go.microsoft.com/fwlink/p/?LinkId=746954)
    
- 啟用使用者的封存信箱之後，可能會告訴使用者，他們可以復原已刪除封存信箱中 [可復原的項目] 資料夾中的項目。他們可以這麼做在 Outlook 中選取 [**刪除的郵件**] 資料夾中的封存信箱，然後按一下 [**首頁**] 索引標籤上的 [**復原刪除的項目從伺服器**。如需復原刪除的項目的詳細資訊，請參閱[復原已刪除的 Outlook for Windows 中的項目](https://go.microsoft.com/fwlink/p/?LinkId=624829)。 
