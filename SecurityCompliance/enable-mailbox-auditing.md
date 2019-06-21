---
title: 管理信箱稽核
ms.author: chrisda
author: chrisda
manager: serdars
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: aaca8987-5b62-458b-9882-c28476a66918
description: 預設會在 Microsoft 365 (也稱為預設信箱審核或信箱審核) 上開啟信箱審核記錄。 這表示信箱擁有者、代理人和系統管理員所執行的特定動作會自動記錄在信箱審核記錄檔中, 您可以在此搜尋信箱上執行的活動。
ms.openlocfilehash: f100fa1eb8244aeaea463440025ee489ec019406
ms.sourcegitcommit: ef2657e4221296be7032191f2d91e8ff727523c6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/21/2019
ms.locfileid: "35117688"
---
# <a name="manage-mailbox-auditing"></a>管理信箱稽核

從2019年1月開始, Microsoft 目前針對所有 Microsoft 365 組織開啟信箱審核記錄功能。 這表示信箱擁有者、代理人和系統管理員所執行的特定動作會自動記錄, 當您在信箱審核記錄檔中進行搜尋時, 會有對應的信箱 audit 記錄可供使用。 在信箱審核預設為開啟之前, 您必須針對組織中的每個使用者信箱手動啟用它。

以下是信箱審核預設的一些優點:

- 當您建立新的信箱時, 系統會自動啟用審核。 您不需要為新使用者手動啟用它。

- 您不需要管理已審核的信箱動作。 每個登入類型 (系統管理員、代理人和擁有者) 預設會審核一組預先定義的信箱動作。

- 當 Microsoft 發行新的信箱動作時 (特別有助於保護您的組織並協助您進行鑒證調查的動作), 會自動將該動作新增至依預設進行審核的信箱動作清單中。 這表示您不需要在信箱上監視新增的動作。

- 您的整個組織都擁有一致的信箱審核原則 (因為您正在為所有信箱進行相同的動作)。

> [!TIP]
> 關於預設的信箱審核版本, 請記住: 您不需要執行任何動作即可管理信箱審核。 不過, 若要深入瞭解, 請從預設設定自訂信箱審核, 或完全關閉它, 本主題可協助您。

## <a name="verify-mailbox-auditing-on-by-default-is-turned-on"></a>[確認預設會啟用信箱審核]

若要確認您的組織預設已啟用信箱審核, 請在[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)中執行下列命令:

```
Get-OrganizationConfig | Format-List AuditDisabled
```

值**False**表示組織的預設啟用信箱審核。 根據預設, 組織值會覆寫特定信箱上的信箱審核設定。 例如, 如果已停用信箱的信箱審核 (信箱上的*AuditEnabled*屬性為**False** ), 則信箱的預設信箱動作仍會針對信箱進行審核, 因為預設會啟用信箱審核公司.

若要讓特定信箱停用信箱審核, 您可以針對信箱擁有者和其他已被委派存取信箱之使用者的信箱, 設定信箱審核略過。 如需詳細資訊, 請參閱本主題中的[略過信箱審核記錄](#bypass-mailbox-audit-logging)一節。

> [!NOTE]
> 針對組織的預設啟用信箱審核時, 受影響信箱的*AuditEnabled*屬性不會從**False**變更為**True**。 換句話說, 預設的信箱審核會忽略信箱上的*AuditEnabled*屬性。

## <a name="supported-mailbox-types"></a>支援的信箱類型

下表顯示預設會由信箱審核支援的信箱類型。

|**信箱類型**|**支援**|**不支援**|
|:---------|:---------:|:---------:|
|使用者信箱|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|共用信箱|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|Office 365 群組信箱|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|資源信箱||![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|公用資料夾信箱||![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|

## <a name="logon-types-and-mailbox-actions"></a>登入類型和信箱動作

登入類型會分類已在信箱上進行審核動作的使用者。 下列清單說明用於信箱審核記錄的登入類型:

- **擁有**者: 信箱擁有者 (與信箱相關聯的帳戶)。

- **代理人**:

  - 已將 SendAs、SendOnBehalf 或 FullAccess 許可權指派給其他信箱的使用者。

  - 獲指派 FullAccess 許可權給使用者信箱的系統管理員。

- 系統**管理**:

  - 使用下列其中一個 Microsoft eDiscovery 工具來搜尋信箱:

    - 規範中心內的內容搜尋。

    - 規範中心的 eDiscovery 或高級 eDiscovery。

    - Exchange Online 中的就地 eDiscovery。

  - 信箱是使用[Microsoft Exchange SERVER MAPI 編輯器](https://go.microsoft.com/fwlink/p/?linkId=204086)來存取。

### <a name="mailbox-actions-for-user-mailboxes-and-shared-mailboxes"></a>使用者信箱和共用信箱的信箱動作

下表說明使用者信箱和共用信箱的信箱審核記錄中可用的信箱動作。

- 核取記號 ( ![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)) 表示可記錄登入類型的信箱動作 (並非所有動作都適用于所有的登入類型)。

- 核取記號後<sup>\*</sup>的星號 () 表示登入類型預設會記錄信箱動作。

- 請記住, 擁有信箱完整存取權限的系統管理員會被視為代理人。

|**信箱動作**|**描述**|**Admin**|**代理人**|**Owner**|
|:---------|:---------|:---------:|:---------:|:---------:|
|**AddFolderPermissions**|**附注**: 雖然此值接受為信箱動作, 但它已包含在**UpdateFolderPermissions**動作中, 而且不會個別審核。 換句話說, 請勿使用此值。||||
|**ApplyRecord**|專案已標示為記錄。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**Copy**|郵件已複製到另一個資料夾。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|**Create**|已在信箱的 [行事曆]、[連絡人]、[記事] 或 [任務] 資料夾中建立專案 (例如, 建立新的會議邀請)。 請注意, 不會審核建立、傳送或接收郵件。 此外, 也不會審核建立信箱資料夾。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**FolderBind**|已存取信箱資料夾。 當系統管理員或代理人開啟信箱時, 也會記錄此動作。 <br/><br/> **附注**: 合併委派所執行之資料夾系結動作的審計記錄。 為24小時期間內的個別資料夾存取產生一個審計記錄。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|**HardDelete**|已從 [可復原的專案] 資料夾中清除郵件。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**MailboxLogin**|使用者已登入其信箱。 |||![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**MessageBind**|已在預覽窗格中查看或開啟郵件。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|**ModifyFolderPermissions**|**附注**: 雖然此值接受為信箱動作, 但它已包含在**UpdateFolderPermissions**動作中, 而且不會個別審核。 換句話說, 請勿使用此值。||||
|**Move**|郵件已移至另一個資料夾。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**MoveToDeletedItems**|郵件已刪除並移至 [刪除的郵件] 資料夾。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**RecordDelete**|標示為記錄的專案已虛刪除 (移至 [可復原的專案] 資料夾)。 標記為記錄的專案無法永久刪除 (從 [可復原的專案] 資料夾中清除)。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**RemoveFolderPermissions**|**附注**: 雖然此值接受為信箱動作, 但它已包含在**UpdateFolderPermissions**動作中, 而且不會個別審核。 換句話說, 請勿使用此值。||||
|**SendAs**|使用 SendAs 許可權傳送郵件。 這表示另一位使用者傳送郵件的方式, 就好像它來自信箱擁有者一樣。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**SendOnBehalf**|使用 SendOnBehalf 許可權傳送郵件。 這表示另一位使用者會代表信箱擁有者傳送郵件。 此訊息會指出郵件的收件者是代表傳送郵件, 以及實際傳送郵件的寄件者。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**SoftDelete**|從 [刪除的郵件] 資料夾中永久刪除或刪除郵件。 虛刪除的專案會移至 [可復原的專案] 資料夾。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**Update**|已變更郵件或其屬性。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**UpdateCalendarDelegation**|已將行事曆委派指派給信箱。 行事曆委派可讓相同組織中的其他人管理信箱擁有者的行事曆。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**UpdateFolderPermissions**|已變更資料夾許可權。 資料夾許可權控制您組織中的哪些使用者可以存取信箱中的資料夾, 以及位於這些資料夾中的郵件。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**UpdateInboxRules**|新增、移除或變更收件匣規則。 收件匣規則用來根據指定的條件處理使用者收件匣中的郵件, 並在符合規則條件時採取動作, 例如將郵件移至指定的資料夾或刪除郵件。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|

> [!IMPORTANT]
> 如果您已在組織中針對預設啟用信箱審核而** 自訂要對任何登入類型進行審核的信箱動作, 則自訂設定會保留在信箱上, 而且預設信箱動作不會覆寫該自訂設定。本節所述。 若要將審核信箱動作還原成其預設值 (您可以隨時執行), 請參閱本主題稍後的[還原預設信箱動作](#restore-the-default-mailbox-actions)一節。

### <a name="mailbox-actions-for-office-365-group-mailboxes"></a>Office 365 群組信箱的信箱動作

信箱的審核預設會將信箱審核記錄帶入 Office 365 群組信箱, 但您無法自訂要記錄的內容 (您無法新增或移除針對任何登入類型記錄的信箱動作)。

下表說明每個登入類型的 Office 365 群組信箱上預設記錄的信箱動作。

請記住, 擁有 Office 365 群組信箱完整存取權限的系統管理員會被視為代理人。

|**信箱動作**|**描述**|**Admin**|**代理人**|**Owner**|
|:---------|:---------|:---------:|:---------:|:---------:|
|**Create**|建立行事曆專案。 請注意, 不會審核建立、傳送或接收郵件。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**HardDelete**|已從 [可復原的專案] 資料夾中清除郵件。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**MoveToDeletedItems**|郵件已刪除並移至 [刪除的郵件] 資料夾。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**SendAs**|使用 SendAs 許可權傳送郵件。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**SendOnBehalf**|使用 SendOnBehalf 許可權傳送郵件。 |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**SoftDelete**|從 [刪除的郵件] 資料夾中永久刪除或刪除郵件。 虛刪除的專案會移至 [可復原的專案] 資料夾。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**Update**|已變更郵件或其屬性。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|

### <a name="verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type"></a>確認每個登入類型都要記錄預設信箱動作

信箱審核依據預設值會將新的*DefaultAuditSet*屬性新增至所有信箱。 此屬性的值會指出是否要在信箱上審核預設信箱動作 (由 Microsoft 管理)。

若要在使用者信箱或共用信箱上顯示值, \<請\>將 mailboxidentity 為信箱取代為信箱的名稱、別名、電子郵件地址或使用者主要名稱 (username), 並在 Exchange Online PowerShell 中執行下列命令:

```
Get-Mailbox -Identity <MailboxIdentity> | Format-List DefaultAuditSet
```

若要在 Office 365 群組信箱上顯示值, \<請\>將 mailboxidentity 為信箱取代為共用信箱的名稱、別名或電子郵件地址, 並在 Exchange Online PowerShell 中執行下列命令:

```
Get-Mailbox -Identity <MailboxIdentity> -GroupMailbox | Format-List DefaultAuditSet
```

此值`Admin, Delegate, Owner`表示:

- 所有三種登入類型的預設信箱動作都會受到審核。 請注意, 這是您在 Office 365 群組信箱上看到的唯一值。

- 系統管理員*未*變更使用者信箱或共用信箱上任何登入類型的已審核信箱動作。 附注: 這是最初在您的組織中開啟信箱審核之後的預設狀態。

如果系統管理員曾經變更過使用*AuditAdmin*、 *AuditDelegate*或*AuditOwner*參數的登**入**類型所審核的信箱動作, 則此屬性值會不同。

例如, 使用者信箱或`Owner`共用信箱上的*DefaultAuditSet*屬性值會指出:

- 審核信箱擁有者的預設信箱動作。

- [] 和`Delegate` `Admin` [登入] 類型的已審核信箱動作已變更為預設動作。

*DefaultAuditSet*屬性的空白值會指出在使用者信箱或共用信箱上, 所有三種登入類型的信箱動作都已變更。

如需詳細資訊, 請參閱本主題中的 [[變更或還原依預設記錄的信箱動作](#change-or-restore-mailbox-actions-logged-by-default)] 一節

### <a name="display-the-mailbox-actions-that-are-being-logged-on-mailboxes"></a>顯示正在登入信箱的信箱動作

若要查看目前登入使用者信箱或共用信箱的信箱動作, 請將 mailboxidentity 為信箱\< \>取代為信箱的名稱、別名、電子郵件地址或使用者主要名稱 (username), 並執行下列一或多項作業:Exchange Online PowerShell 中的命令。

> [!NOTE]
> 雖然您可以將此`-GroupMailbox`參數新增至 Office 365 群組信箱的下列**取得信箱**命令, 但不相信您看到的值。 在本主題稍早的[office 365 群組信箱的信箱動作](#mailbox-actions-for-office-365-group-mailboxes)中, 會說明針對 Office 365 群組信箱所審核的預設和靜態信箱動作。

#### <a name="owner-actions"></a>擁有者動作

```
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditOwner
```

#### <a name="delegate-actions"></a>委派動作

```
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditDelegate
```

#### <a name="admin-actions"></a>系統管理動作

```
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditAdmin
```

## <a name="change-or-restore-mailbox-actions-logged-by-default"></a>變更或還原依預設記錄的信箱動作

如先前所述, 預設會啟用信箱審核的其中一個主要優點是: 您不需要管理已審核的信箱動作。 Microsoft 為您執行這一作業, 我們會在發佈時自動新增要進行審核的新信箱動作。

不過, 您的組織可能需要為使用者信箱和共用信箱審計一組不同的信箱動作。 本節中的程式將示範如何變更針對每個登入類型進行審核的信箱動作, 以及如何回復至 Microsoft 受管理的預設動作。

> [!IMPORTANT]
> 如果您使用下列程式來自訂使用者信箱或共用信箱上所記錄的信箱動作, 則不會在這些信箱上自動進行任何 Microsoft 發行的預設信箱動作。 您必須手動將任何新的信箱動作新增至自訂的動作清單中。

### <a name="change-the-mailbox-actions-to-audit"></a>變更要審核的信箱動作

您可以在**設定信箱**Cmdlet 上使用*AuditAdmin*、 *AuditDelegate*或*AuditOwner*參數, 以變更針對使用者信箱和共用信箱所審核的信箱動作 (Office 365 群組的已審核動作)無法自訂信箱)。

您可以使用兩種不同的方法來指定信箱動作:

- *Replace*(使用下列語法, 覆寫) 現有的信箱動作`action1,action2,...actionN`:。

- 使用下列語法,*新增或移除*信箱動作, 而不影響其他現有`@{Add="action1","action2",..."actionN"}`的`@{Remove="action1","action2",..."actionN"}`值: 或。

此範例會使用 SoftDelete 和 HardDelete 覆寫預設動作, 以變更名為 "Gabriela Laureano" 之信箱的系統管理員信箱動作。

```
Set-Mailbox -Identity "Gabriela Laureano" -AuditAdmin HardDelete,SoftDelete
```

此範例會將 MailboxLogin 擁有者動作新增至信箱 laura@contoso.onmicrosoft.com。

```
Set-Mailbox -Identity laura@contoso.onmicrosoft.com -AuditOwner @{Add="MailboxLogin"}
```

本範例會移除小組討論信箱的 MoveToDeletedItems 委派動作。

```
Set-Mailbox -Identity "Team Discussion" -AuditDelegate @{Remove="MoveToDeletedItems"}
```

不論您使用的是何種方法, 自訂使用者信箱或共用信箱上的已審核信箱動作都有下列結果:

- 對於您自訂的登入類型, 已不再由 Microsoft 管理已審核的信箱動作。

- 您自訂的登入類型不再顯示在信箱的*DefaultAuditSet*屬性值中, 如[先前所述](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type)。

### <a name="restore-the-default-mailbox-actions"></a>還原預設信箱動作

如果您自訂在使用者信箱或共用信箱上進行審核的信箱動作, 您可以使用下列語法來還原一或所有登入類型的預設信箱動作:

```
Set-Mailbox -Identity <MailboxIdentity> -DefaultAuditSet <Admin | Delegate | Owner>
```

您可以指定多個以逗號分隔的*DefaultAuditSet*值

**附注**: 下列程式不適用於 Office 365 群組信箱 (其限制為預設動作, 如下所述)。 [](#mailbox-actions-for-office-365-group-mailboxes)

此範例會針對信箱 mark@contoso.onmicrosoft.com 上的所有登入類型, 還原預設的已審核信箱動作。

```
Set-Mailbox -Identity mark@contoso.onmicrosoft.com -DefaultAuditSet Admin,Delegate,Owner
```

此範例會針對信箱 chris@contoso.onmicrosoft.com 上的系統管理員登入類型還原預設的已審核信箱動作, 但會保留委派和擁有者登入類型的自訂已審核信箱動作。

```
Set-Mailbox -Identity chris@contoso.onmicrosoft.com -DefaultAuditSet Admin
```

還原登入類型的預設已審核信箱動作有下列結果:

- 目前的信箱動作清單會取代為登入類型的預設信箱動作。

- 任何由 Microsoft 發行的新信箱動作都會自動新增至登入類型的已審核動作清單中。

- 信箱的*DefaultAuditSet*屬性值會更新為包含還原的登入類型。

## <a name="turn-off-mailbox-auditing-on-by-default-for-your-organization"></a>針對貴組織預設關閉信箱審核

您可以在 Exchange Online PowerShell 中執行下列命令, 關閉整個組織的預設信箱審核:

```
Set-OrganizationConfig -AuditDisabled $true
```

根據預設, 關閉信箱審計的結果如下:

- 您的組織已停用信箱審核。

- 從您停用信箱審核時, 預設不會審核任何信箱動作 (即使信箱上的*AuditEnabled*屬性為**True**)。

- 信箱審核未啟用新信箱, 並將新的或現有的信箱上的*AuditEnabled*屬性設定為**True**將會被忽略。

- 會忽略任何信箱審核略過的關聯設定 (使用 Set-mailboxauditbypassassociation 指令程式**設定**)。

- 現有的信箱審計記錄會保留, 直到記錄的審核記錄保留限制到期為止。

### <a name="turn-on-mailbox-auditing-on-by-default"></a>依預設開啟信箱審計

若要為您的組織開啟信箱審核, 請在 Exchange Online PowerShell 中執行下列命令:

```
Set-OrganizationConfig -AuditDisabled $false
```

## <a name="bypass-mailbox-audit-logging"></a>略過信箱審核記錄

目前您的組織中開啟信箱審核時, 您無法停用特定信箱的信箱審核。 例如, 會忽略將*AuditEnabled*信箱屬性設為**False** 。

不過, 您仍然可以在 Exchange Online PowerShell 中使用**set-mailboxauditbypassassociation 指令程式**, 以防止指定使用者記錄*任何*信箱動作, 而不論動作發生的位置為何。 例如：

- 略過的使用者所執行的信箱擁有者動作不會登入。

- 委派使用者信箱 (包括共用信箱) 上略過的使用者所執行的動作不會被記錄。

- 由略過的使用者執行的系統管理動作不會記錄。

若要略過特定使用者的信箱審核記錄, \<請\>將 mailboxidentity 為信箱取代為使用者的名稱、電子郵件地址、別名或使用者主要名稱 (username), 並執行下列命令:

```
Set-MailboxAuditBypassAssociation -Identity <MailboxIdentity> -AuditByPassEnabled $true
```

若要確認是否略過指定使用者的審核, 請執行下列命令:

```
Get-MailboxAuditBypassAssociation -Identity <MailboxIdentity> | Format-List AuditByPassEnabled
```

**True**值表示使用者的信箱審核記錄被略過。

## <a name="more-information"></a>詳細資訊

- 依預設, 信箱審核記錄記錄會在刪除之前保留90天。 您可以使用 Exchange Online PowerShell 中**設定信箱**指令程式上的*AuditLogAgeLimit*參數, 來變更 audit log 記錄的保留限制。 不過, 增加此值並不會讓您在 Microsoft 365 audit 記錄檔中搜尋超過90天的事件。

  如果您增加保留時間限制, 您必須在 Exchange Online PowerShell 中使用[search-mailboxauditlog examples 指令程式](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog), 以搜尋超過90天之記錄的使用者信箱 audit 記錄檔。

- 如果您已在信箱審核之前將信箱的*AuditLogAgeLimit*屬性變更為 [組織], 則信箱的現有審核記錄保留時間限制不會變更。 換句話說, 預設的信箱審核不會影響信箱審計記錄的目前保留限制。

- 若要變更 Office 365 群組信箱上的*AuditLogAgeLimit*值, 您必須將該`-GroupMailbox`參數包含在 [**設定信箱**] 命令中。

- 信箱 audit log 記錄會儲存在每個使用者信箱** 的 [可復原的專案] 資料夾中的子資料夾 (名為 audit)。 請記住下列有關信箱審計記錄和 [可復原的專案] 資料夾的事項:

  - 信箱審計記錄會依據 [可復原的專案] 資料夾的儲存配額來計算, 預設值為 30GB (警告配額為 20 GB)。 在下列情況中, 儲存配額會自動增加為 100 GB (含 90 GB 警告配額):

    - 保留在信箱上。

    - 信箱會指派給規範中心的保留原則。

  - 信箱審計記錄也會依據[[可復原的專案] 資料夾的資料夾限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits)計數。 [Audit] 子資料夾中最多可儲存3000000個專案 (審計記錄)。

    > [!NOTE]
    > 依預設, 信箱審核不太可能會影響儲存配額或 [可復原的專案] 資料夾的資料夾限制。

    - 您可以在 Exchange Online PowerShell 中執行下列命令, 以在 [可復原的專案] 資料夾的 [核查] 子資料夾中顯示專案的大小和數目:

      ```
      Get-MailboxFolderStatistics -Identity <MailboxIdentity> -FolderScope RecoverableItems | Where-Object {$_.Name -eq 'Audits'} | Format-List FolderPath,FolderSize,ItemsInFolder
      ```

    - 您無法直接存取 [可復原的專案] 資料夾中的審計記錄記錄;相反地, 您可以使用**search-mailboxauditlog examples 指令程式**, 或搜尋 Microsoft 365 audit log 來尋找並查看信箱審計記錄。

- 如果信箱處於暫止狀態, 或指派給規範中心的保留原則, 則在信箱的*AuditLogAgeLimit*屬性 (預設值為90天) 內所定義的期間仍會保留 audit log 記錄。 若要保留長時間保留信箱的審計記錄檔, 您需要增加信箱的*AuditLogAgeLimit*值。
