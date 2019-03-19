---
title: 管理信箱的稽核
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
ms.assetid: aaca8987-5b62-458b-9882-c28476a66918
description: 信箱稽核記錄 （也稱為預設信箱稽核或信箱的稽核預設情況下） 的 Microsoft 365 中預設已開啟。 這表示信箱擁有者、 代理人和系統管理員所執行的特定動作都會自動記錄在信箱稽核記錄，您可以搜尋的信箱上執行的活動。
ms.openlocfilehash: 604b7fc26c2e97a5efce28fe844fbd066196c4ce
ms.sourcegitcommit: b688d67935edb036658bb5aa1671328498d5ddd3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2019
ms.locfileid: "30670628"
---
# <a name="manage-mailbox-auditing"></a>管理信箱的稽核
  
2019 年 1 月開始，Microsoft 開啟信箱稽核記錄依預設，所有的 Microsoft 365 組織。 這表示自動記錄信箱擁有者、 代理人和系統管理員所執行某些動作，以及對應的信箱稽核記錄時，會提供您的信箱稽核記錄中搜尋它們。 信箱稽核依預設已開啟之前，您必須以手動啟用每個使用者信箱在您的組織中使用。 

以下是一些信箱的稽核預設的優點：

- 會啟用稽核預設當您建立新的信箱。 您不需要手動啟用為新的使用者。 

- 您不會管理稽核的信箱動作。 根據預設會針對每種類型的登入稽核一組定義的信箱動作。 這些[登入類型](#mailbox-actions-logged-by-default)都擁有者、 代理人及系統管理]。

- 由 Microsoft 發行新的信箱動作將會依預設稽核。 當 Microsoft 發行新的信箱動作 （尤其是一種是協助保護您的組織，並協助鑑定調查） 時，它會自動新增至預設的稽核的信箱動作清單。 這表示您不需要將新動作新增至擁有者、 代理人或系統管理員所執行的信箱動作的清單。 

- 請確定您正在讓貴組織有一致的信箱稽核原則可能稽核所有信箱的相同的動作。

> [!TIP]
> 請記得重點是，與信箱的稽核預設版本，您不需要執行任何動作來管理信箱的稽核。 不過，如果您想要了解更多、 變更行為，從預設設定，或將它關閉完全，這篇文章可協助您使用的。

## <a name="verify-mailbox-auditing-on-by-default-is-turned-on"></a>確認信箱的稽核預設已開啟

若要確認該信箱上的預設開啟稽核功能為您的組織， [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)中執行下列命令：

```
Get-OrganizationConfig | FL AuditDisabled
``` 

**False**值表示，為您的組織中啟用信箱稽核上預設。 

當信箱上的預設開啟稽核功能 （當*AuditDisabled*屬性設為**False**）、 [組織] 設定會覆寫的稽核設定特定信箱的信箱。 例如，如果*AuditEnabled*屬性信箱的信箱設**為 False**，但信箱稽核上的預設值啟用組織、 預設信箱動作將會對該信箱稽核。 如果信箱稽核已明確停用特定的信箱，而且您仍然想要停用它，您可以設定信箱稽核略過信箱擁有者，以及已被其他使用者委派信箱存取權。 如需詳細資訊，請參閱本文中的 [[略過信箱稽核記錄](#bypass-mailbox-audit-logging)] 區段。

> [!NOTE]
> 當開啟預設的稽核的信箱時， *AuditEnabled*屬性信箱的信箱不會變更為**True** ，如果目前設為**False**。 換句話說，信箱的稽核依預設會忽略*AuditEnabled*屬性信箱的信箱。

## <a name="supported-mailbox-types"></a>支援的信箱類型

下表顯示預設的稽核的信箱目前支援的信箱類型：

|信箱類型|支援|不支援|
|:---------|:---------:|:---------:|
|使用者信箱    |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)       |         |
|共用信箱    |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)        |       |
|Office 365 群組信箱    |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)         |         |
|資源信箱    |      |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)        |
|公用資料夾信箱    |       |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)  |
||||

## <a name="mailbox-actions-logged-by-default"></a>記錄預設的信箱動作

一組信箱動作會記錄依預設，針對每個以下的登入類型：  

   - **擁有者**的信箱擁有者。 
   
   - **委派**-另一位使用者獲指派 SendAs、 SendOnBehalf 或 FullAccess 權限給某個人的信箱。 請注意，已指派的 FullAccess 權限給使用者的信箱的系統管理員也會被視為委派使用者。
   
    - **系統管理員**的信箱會被視為只能在下列案例中的系統管理員登入類型的存取：
    
       - 當信箱搜尋與下列的 Microsoft eDiscovery 工具之一： 

         - 在 「 規範中心中的內容搜尋。
       
         -  eDiscovery 或規範中心中的進階電子文件。
       
         - Exchange Online 中的就地 eDiscovery。
       - 當[Microsoft Exchange Server MAPI Editor](https://go.microsoft.com/fwlink/p/?linkId=204086)用來存取信箱。     

下表列出目前記錄依預設，每個登入類型的信箱動作。

|系統管理動作|代理人動作|擁有者動作|
|:---------|:---------|:---------|
|Create    |Create       | HardDelete        |
|HardDelete    |HardDelete        |MoveToDeletedItems       |
|MoveToDeletedItems    |MoveToDeletedItems         |SoftDelete         |
|SendAs    |SendAs      |    Update     |
|SendOnBehalf    |SendOnBehalf       |UpdateCalendarDelegation        |
|SoftDelete     |SoftDelete      | UpdateFolderPermissions        |
|Update    |Update       |UpdateInboxRules         |
|UpdateCalendarDelegation    | UpdateFolderPermissions        |         |
|UpdateFolderPermissions     | UpdateInboxRules        |         |
|UpdateInboxRules     |         |         |
||||

以下是這些信箱動作的描述。 

|信箱動作|描述|
|:---------|:---------|
|**Create** <br/> |在信箱; 中的 [行事曆、 連絡人、 備忘稿或工作] 資料夾中建立項目例如，會建立新的會議邀請。 請注意不稽核建立、 傳送或接收郵件。 此外，不稽核建立一個信箱資料夾。  <br/> |
|**HardDelete** <br/> |郵件已從 [可復原的項目] 資料夾中清除。  <br/> |
|**MoveToDeletedItems** <br/> |已刪除的郵件，並將它移至 [刪除的項目] 資料夾。  <br/> |
|**SendAs** <br/> |郵件已傳送使用 SendAs 權限。 這表示另一位使用者傳送的郵件，就好像它來自信箱擁有者。  <br/> |
|**SendOnBehalf** <br/> |郵件已傳送使用 SendOnBehalf 權限。 這表示另一位使用者傳送代表信箱擁有者的郵件。 郵件已傳送代理者誰以及實際寄件者郵件的訊息會指出收件者。  <br/> |
|**SoftDelete** <br/> |郵件已永久刪除，或從 [刪除的項目] 資料夾中刪除。 虛刪除的項目會移至 [可復原的項目] 資料夾。  <br/> |
|**Update** <br/> |郵件或其屬性已變更。  <br/> |
|**UpdateCalendarDelegation** <br/> |行事曆委派已指派給信箱。 行事曆委派可讓其他人在相同的組織權限來管理信箱擁有者的行事曆。  <br/> |
|**UpdateFolderPermissions** <br/> |已變更資料夾的權限。 資料夾的權限控制您組織中的哪些使用者可以存取信箱，而且這些資料夾中的郵件中的資料夾。  <br/> |
|**UpdateInboxRules** <br/> |收件匣規則已新增、 移除或變更。 收件匣規則用來處理郵件使用者的收件匣根據指定的條件，並符合規則的條件，例如將郵件移至指定資料夾或刪除郵件時採取的動作。  <br/> |
|||

信箱的動作，包括可用，但不包含在預設動作，一組動作的完整清單，請參閱本文中的[信箱稽核動作](#mailbox-auditing-actions)] 區段。

> [!IMPORTANT]
> 如果您有明確地設定信箱来稽核的動作前信箱的稽核預設組織正在開啟任何登入類型，信箱的現有設定將優先，並不會覆寫預設的信箱本節中所述的動作。 如果任何時候您想要回復至預設信箱動作，您可以執行的**Set-mailbox DefaultAuditSet**命令。 如需執行此動作的詳細資訊，請參閱本文中的 [[還原預設信箱動作](#restore-the-default-mailbox-actions)] 區段。

### <a name="verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type"></a>確認記錄每個登入類型預設信箱動作

版本信箱的稽核依預設，已新增名為*DefaultAuditSet*新信箱屬性。 此屬性會指出指定信箱的每個登入類型正在稽核 （由 Microsoft 管理） 的預設信箱動作。 您可以執行下列命令，以顯示此屬性的值：

```
Get-Mailbox <username> | FL DefaultAuditSet
```

值為`Admin, Delegate, Owner`指出稽核所有三個登入類型的預設信箱動作，而且*不具有*您組織的系統管理員變更任何登入類型的動作。 請注意這是預設狀態之後的信箱上預設開啟稽核功能最初貴組織中。 

如果您組織中的系統管理員已變更稽核登入類型 （藉由使用**Set-mailbox**指令程式搭配*AuditAdmin*、 *AuditDelegate*或*AuditOwner*參數），然後值的信箱動作*DefaultAuditSet*屬性將會是不同的預設值。 例如，值為`Owner`指出唯一要稽核的信箱擁有者的預設信箱動作，且動作`Delegate`和`Admin`已經變更。 如果沒有任何*DefaultAuditSet*屬性 （也稱為*null*值） 顯示的值已被變更所有三個登入類型的信箱動作。

請參閱如需有關變更稽核的信箱動作本文中的[預設記錄變更或還原的信箱動作](#change-or-restore-mailbox-actions-logged-by-default)」 一節。

### <a name="display-a-list-of-mailbox-actions-logged-by-default"></a>顯示預設記錄的信箱動作的清單

您可以執行下列命令，在 Exchange Online PowerShell 來顯示目前正在的每個登入類型的信箱的信箱動作的清單：

**擁有者動作**

```
Get-Mailbox <username> | Select-Object -ExpandProperty AuditOwner
```

**代理人動作**

```
Get-Mailbox <username> | Select-Object -ExpandProperty AuditDelegate
```

**系統管理動作**

```
Get-Mailbox <username> | Select-Object -ExpandProperty AuditAdmin
```

## <a name="change-or-restore-mailbox-actions-logged-by-default"></a>變更或還原預設記錄的信箱動作

如同先前的說明，其中一個信箱的稽核預設的主要優點是，您不需要管理稽核的信箱動作。 Microsoft 會為您，並將會自動新增新的信箱動作，以稽核依預設，當他們都釋放為止。 不過，您的組織可能有稽核一組不同的預設探索信箱動作的原因。 本節說明如何變更的登入類型] 中，每個稽核的信箱動作，以及如何回復到 Microsoft 受管理的預設動作。

> [!IMPORTANT]
> 如果您對使用者的信箱動作，然後由 Microsoft 釋放任何新信箱動作不會針對這些信箱稽核記錄預設 （如 [下一步] 區段中所述），進行任何變更。 您必須明確地將新的信箱動作新增至登入類型稽核的動作清單。

### <a name="change-the-mailbox-actions-to-audit"></a>變更要稽核的信箱動作

您可以使用**Set-mailbox**指令程式*AuditAdmin*、 *AuditDelegate*或*AuditOwner*參數變更稽核，取決於登入類型的信箱動作。 因為這些稽核相關的參數是多重值參數 （這表示他們可以有多個值），有兩個不同的方式來變更它們。

- 您可以指定多個信箱動作，請使用下列語法來覆寫現有的動作： `action1,action2,...actionN`。

- 您可以新增或移除一或多個信箱巨集指令，而不影響任何現有的記錄，使用下列語法：`@{Add="action1","value2"}`或`@{Remove="action1","action2"}`。

不論其您使用的方法若要變更要稽核的信箱動作稽核 （適用於您已變更的登入類型） 的預設信箱動作將不再是由 Microsoft 管理。 此外，您變更登入類型的值不會顯示在*DefaultAuditSet* mailbox 參數已[先前所述](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type)。

以下是使用下列方法之一來變更要稽核的每個不同的登入類型的信箱動作的一些範例。 

本範例會變更的系統信箱動作 SoftDelete 與 HardDelete 覆寫預設動作。 

```
Set-Mailbox <username> -AuditAdmin HardDelete,SoftDelete
```

此範例會新增 MailboxLogin 擁有者動作。 

```
Set-Mailbox <username> -AuditOwner @{Add="MailboxLogin"}
```

此範例會移除 MoveToDeletedItems 委派巨集指令。

```
Set-Mailbox <username> -AuditDelegate @{Remove="MoveToDeletedItems"}
```

#### <a name="checking-the-defaultauditset-property"></a>檢查 DefaultAuditSet 屬性

變更登入類型的預設信箱動作之後，在信箱上的*DefaultAuditSet*屬性將會自動更新以反映此變更。 例如，如果您執行`Get-Mailbox <username> | FL DefaultAuditSet`之後第一次新增或移除信箱擁有者動作，此命令只會傳回的值為`Admin, Delegate`。 這表示，預設信箱動作的擁有者已經變更，這也表示，由 Microsoft 釋放任何新信箱擁有者動作不會自動新增到此信箱。 同樣適用於變更系統管理員或代理人登入類型的信箱動作。

### <a name="restore-the-default-mailbox-actions"></a>還原預設信箱動作

如果您登入類型進行稽核的信箱動作的變更，您可以還原稽核所執行的預設信箱動作`Set-Mailbox -DefaultAuditSet`命令。 當您這麼做時，會發生下列事項：

- 目前的信箱動作清單會取代適當的登入類型的預設信箱動作。
 
- 由 Microsoft 釋放任何新信箱動作將會自動新增至適當的登入類型的清單。

- [DefaultAuditSet 信箱屬性](#checking-the-defaultauditset-property)將會更新以包含適當的登入類型。

若要還原所有登入類型的預設信箱動作，請執行下列命令：

```
Set-Mailbox <username> -DefaultAuditSet Admin,Delegate,Owner
```

您可以使用此命令，還原任何登入類型的預設信箱動作 （藉由使用**系統管理員**、**代理人**或**擁有者**值*DefaultAuditSet*參數。）

## <a name="turn-off-mailbox-auditing-on-by-default-for-your-organization"></a>關閉信箱的稽核預設為您的組織

如果因任何原因您的組織會決定它不會想要稽核的信箱動作，您可以關閉信箱稽核上預設為整個組織的 Exchange Online PowerShell 中執行下列命令：

```
Set-OrganizationConfig -AuditDisabled $true
```

當信箱的稽核預設為關閉 （ *AuditDisabled*屬性設為**True**） 的組織中，會發生下列情形會：

- 信箱稽核已停用您的組織。

- （從時稽核已停用組織的時間開始），請將稽核沒有信箱動作即使*AuditEnabled*屬性信箱的信箱上設定為**True**。

- 不會針對新的信箱啟用信箱稽核，並設定新的 （或現有的） 的信箱 **，則為 True** *AuditEnabled*屬性信箱都會被忽略。

- 任何信箱稽核略過的關聯 （使用**Set-mailboxauditbypassassociation**指令程式來設定） 的設定將被忽略。

- 現有的信箱稽核記錄保留稽核記錄檔保留天數之前記錄到期。

### <a name="turn-on-mailbox-auditing-on-by-default"></a>信箱上開啟稽核預設

若要開啟信箱的稽核重新開啟您的組織，只需在 Exchange Online PowerShell 中執行下列命令：

```
Set-OrganizationConfig -AuditDisabled $false
```

## <a name="bypass-mailbox-audit-logging"></a>略過信箱稽核記錄

目前，您無法停用信箱稽核特定信箱的信箱上的稽核預設組織中開啟時。 例如， *AuditEnabled*信箱屬性設定為**False**則會忽略。  不過，您可以仍使用**Set-mailboxauditbypassassociation**指令程式在 Exchange Online PowerShell 來防止從正在記錄的特定使用者所執行的信箱動作。 當您要略過信箱稽核時，不稽核的特定使用者所執行的信箱動作，不論哪個信箱這些動作正在執行上。 如果您略過信箱稽核特定使用者，然後將不會記錄該使用者所執行的信箱擁有者動作。 而且如果相同使用者權限指派給其他使用者的信箱 （或共用的信箱），然後執行第一位使用者的代理人動作也不會記錄。

若要略過信箱稽核記錄的特定使用者，執行下列命令：

```
Set-MailboxAuditBypassAssociation -Identity <username> -AuditByPassEnabled $true
```

若要確認已針對指定的使用者略過的稽核，請執行下列命令：

```
Get-MailboxAuditBypassAssociation -Identity <username> | FL AuditByPassEnabled
```

**True**值表示該信箱稽核記錄會略過該使用者。

## <a name="mailbox-auditing-actions"></a>信箱稽核動作
  
下表摘要說明每個使用者登入類型稽核的動作。 在表格中，為星號 ( **\*** ) 表示預設會記錄的動作。 **不**會指出巨集指令不會記錄該登入類型。 請注意，獲指派 「 完整存取 」 權限的使用者信箱的系統管理員會被視為委派使用者。 
  
|**Action**|**描述**|**Admin**|**委派**|**Owner**|
|:-----|:-----|:-----|:-----|:-----|
|**Copy** <br/> |郵件已複製到另一個資料夾。  <br/> |是  <br/> |否  <br/> |否  <br/> |
|**Create** <br/> |在信箱; 中的 [行事曆、 連絡人、 備忘稿或工作] 資料夾中建立項目例如，會建立新的會議邀請。 請注意不稽核建立、 傳送或接收郵件。 此外，不稽核建立一個信箱資料夾。  <br/> |是\*  <br/> |是\*  <br/> |是  <br/> |
|**FolderBind**\** <br/> |存取信箱資料夾。 系統管理員或代理人開啟信箱時，也會記錄此巨集指令。  <br/> |是  <br/> |是  <br/> |否  <br/> |
|**HardDelete** <br/> |郵件已從 [可復原的項目] 資料夾中清除。  <br/> |是\*  <br/> |是\*  <br/> |是\*  <br/> |
|**MailboxLogin** <br/> |使用者登入其信箱。  <br/> |否  <br/> |否  <br/> |是  <br/> |
|**MessageBind**\*** <br/> |郵件已在 [預覽] 窗格中檢視，或開啟。  <br/> |是  <br/> |否  <br/> |否  <br/> |
|**Move** <br/> |郵件已移到另一個資料夾。  <br/> |是  <br/> |是  <br/> |是  <br/> |
|**MoveToDeletedItems** <br/> |已刪除的郵件，並將它移至 [刪除的項目] 資料夾。  <br/> |是\*  <br/> |是\*  <br/> |是\*  <br/> |
|**SendAs** <br/> |郵件已傳送使用 SendAs 權限。 這表示另一位使用者傳送的郵件，就好像它來自信箱擁有者。  <br/> |是\*  <br/> |是\*  <br/> |否  <br/> |
|**SendOnBehalf** <br/> |郵件已傳送使用 SendOnBehalf 權限。 這表示另一位使用者傳送代表信箱擁有者的郵件。 郵件已傳送代理者誰以及實際寄件者郵件的訊息會指出收件者。  <br/> |是\*  <br/> |是\*  <br/> |否  <br/> |
|**SoftDelete** <br/> |郵件已永久刪除，或從 [刪除的項目] 資料夾中刪除。 虛刪除的項目會移至 [可復原的項目] 資料夾。  <br/> |是\*  <br/> |是\*  <br/> |是\*  <br/> |
|**Update** <br/> |郵件或其屬性已變更。  <br/> |是\*  <br/> |是\*  <br/> |是\*  <br/> |
|**UpdateCalendarDelegation** <br/> |行事曆委派已指派給信箱。 行事曆委派可讓其他人在組織權限來管理信箱擁有者的行事曆。  <br/> |是\*  <br/> |否  <br/> |是\*  <br/> |
|**UpdateFolderPermissions** <br/> |已變更資料夾的權限。 資料夾的權限控制您組織中的哪些使用者可以存取信箱，而且這些資料夾中的郵件中的資料夾。  <br/> |是\*  <br/> |是\*  <br/> |是\*  <br/> |
|**UpdateInboxRules** <br/> |已新增、 移除或變更收件匣規則。 收件匣規則用來處理郵件使用者的收件匣根據指定的條件，並符合規則的條件，例如將郵件移至指定資料夾或刪除郵件時採取的動作。  <br/> |是\*  <br/> |是\*  <br/> |是\*  <br/> |
   
> [!NOTE]
> <sup>\*</sup>預設信箱稽核登入類型啟用時，依預設稽核。 <br/><br/>  <sup>\*\*</sup>合併委派所執行的資料夾繫結動作的稽核記錄。 為 24 小時的時間範圍內的個別資料夾存取產生一個稽核記錄。 <br/><br/> <sup> \* \* \* </sup> MessageBind 巨集指令在 Exchange Online 中，已過時，不再可供新增至系統管理員的登入類型的信箱動作清單。 

## <a name="more-information"></a>詳細資訊

- 根據預設，信箱稽核記錄會記錄會保留 90 天，並再刪除。 您可以在 Exchange Online PowerShell 中使用**Set-mailbox AuditLogAgeLimit**命令變更稽核記錄保留天數。 請注意，增加的信箱稽核記錄預設存留期限制不會影響的信箱稽核記錄會記錄 Microsoft 365 稽核記錄中 90 天存留期限制。 比方說，如果您增加為 365 天信箱稽核記錄會記錄保留天數時，信箱稽核記錄會在 Microsoft 365 稽核記錄檔可搜尋僅在相對應的事件發生後 90 天。 在此情況下，您必須記錄超過 90 天的使用者的信箱稽核記錄檔中搜尋。 如需搜尋信箱稽核記錄的詳細資訊，請參閱[Search-mailboxauditlog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog)。

- 如果您已經變更*AuditLogAgeLimit*屬性之前信箱的稽核預設組織正在開啟信箱，將不會變更現有的信箱稽核記錄保留限制;換句話說，信箱的稽核預設不會影響信箱稽核記錄的目前保留限制。

- 信箱稽核記錄的每位使用者的信箱中 [可復原的項目] 資料夾中 （名為*稽核*） 的子資料夾中儲存的記錄。 保留信箱稽核記錄和可復原的項目] 資料夾的相關記住下列事項。
   
    - [可復原的項目] 資料夾，（[警告] 配額為 20 GB） 的預設為 30 GB 的儲存配額的信箱稽核記錄個數。 請注意，[可復原的項目] 資料夾的儲存配額會自動從增加到 100GB （90 MB 警告配額） 時保留在信箱上或信箱指派給 「 規範中心中的保留原則。

    - 信箱稽核記錄也會計算對[[可復原的項目] 資料夾的資料夾限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits)。 項目 （也就是在此案例中的稽核記錄），可以儲存在 [稽核] 子資料夾數目上限為 3 百萬個項目。 

      > [!NOTE]
      > 它是不太可能會影響信箱的稽核依預設，儲存空間配額或 [可復原的項目] 資料夾的資料夾限制。 

    - 您可以執行下列命令在 Exchange Online PowerShell，在 [可復原的項目] 資料夾中的 [稽核] 子資料夾中顯示的大小和項目數： 
       ```
       Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | Where-Object {$_.Name -eq 'Audits'} | FL FolderPath,FolderSize,ItemsInFolder
       ```

     - 您無法直接存取稽核記錄檔中記錄 [可復原的項目] 資料夾中。相反地，您會使用**Search-mailboxauditlog**指令程式，或搜尋 Microsoft 365 稽核記錄] 來尋找及檢視信箱稽核記錄。

- 如果信箱會處於暫止狀態或指派給 「 規範中心中的保留原則，稽核記錄會記錄仍會保留信箱 （這預設設定為 90 天） 的*AuditLogAgeLimit*屬性所定義的持續時間。 若要保留稽核記錄會記錄較長的保留的信箱，您必須藉由增加*AuditLogAgeLimit*屬性的值增加的保留期間。