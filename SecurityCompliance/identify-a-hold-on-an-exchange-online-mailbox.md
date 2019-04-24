---
title: 如何找出位於 Exchange Online 信箱的保留類型
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/22/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6057daa8-6372-4e77-a636-7ea599a76128
description: 了解如何識別不同類型的可以放在 Office 365 信箱的保留。 這些類型的保留包含訴訟暫止、 eDiscovery 保留和 Office 365 保留原則。 您也可以判定是否使用者已被排除全組織保留原則
ms.openlocfilehash: e0c1c54cedfc7494233f12f043bb6d033576eca8
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32253881"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a>如何找出位於 Exchange Online 信箱的保留類型

本文說明如何識別保留暫留在 Office 365 中的 Exchange Online 信箱。

Office 365 提供許多組織可以防止永久刪除信箱內容的方法。 這可讓您的組織來保留以符合規範 regulars 的內容或期間內的法律或其他類型的調查。 以下是 Office 365 的保留功能 （也稱為*保留*） 的清單：

- **訴訟暫止**-已套用至 Exchange Online 中的使用者信箱的保留。

- **eDiscovery 保留**-在安全性與合規性中心 eDiscovery 案例相關聯的保留。 eDiscovery 保留可以套用到使用者信箱，並在對應的信箱上 Office 365 群組和 Microsoft Teams。

- **就地保留**位在 Exchange 系統管理員使用就地 eDiscovery & 保留工具已套用至使用者信箱的保留中心在 Exchange Online。

- **Office 365 保留原則**-Office 365 群組及 Microsoft Teams 保留使用者信箱在 Exchange Online 和對應的信箱中的內容。 您可以建立保留原則會儲存在使用者信箱中的商務交談保留 Skype。

  有兩種類型的 Office 365 保留原則，可以指派給信箱。

    - **特定位置保留原則**，這些是指派給特定使用者的內容位置原則。 您在 Exchange Online PowerShell 中使用**Get-mailbox**指令程式，來取得指派給特定信箱的保留原則的相關資訊。

    - **整個組織的保留原則**，這些是指派給組織中的所有內容位置原則。 您在 Exchange Online PowerShell 中使用**Get-organizationconfig**指令程式，來取得全組織保留原則的相關資訊。
  如需詳細資訊，請參閱 「 將保留原則套用至整個組織或特定位置 」 一節中[概觀的 Office 365 保留原則](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)。

- **Office 365 保留標籤**-如果使用者將 （一個已設定為保留內容或保留，然後刪除內容） 的 Office 365 保留標籤套用至*任何*資料夾或項目在其信箱，保留置於信箱，就如同信箱已處於訴訟暫止狀態或指派給 Office 365 保留原則。 如需詳細資訊，請參閱本文[Identifying 的信箱，所以已保留標籤套用至資料夾或項目保留](#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item)一節。

若要管理保留的信箱，您可能要識別，讓您可以執行工作，例如變更保留持續時間、 暫時或永久移除保留，或從 Office 365 保留原則中排除信箱置於信箱的保留的類型。 在這些情況下，第一個步驟是識別保留暫留信箱的類型。 因為多個保留 （與不同類型的保留） 可以放在單一信箱，您必須識別放置在信箱上，如果您想要移除或變更這些保留的所有保留。

## <a name="step-1-obtaining-the-guid-for-holds-placed-on-a-mailbox"></a>步驟 1： 取得的 GUID，保留暫留信箱

您可以執行下列兩個指令程式在 Exchange Online PowerShell，以取得的信箱置於保留的 GUID。 取得 GUID 之後，您會使用它來識別特定保留在 [步驟 2。 請注意的訴訟暫止會保留不識別 GUID。 [啟用或停用信箱的訴訟資料暫留。

- **Get-mailbox** -使用此指令程式，若要判斷是否啟用信箱的訴訟暫止，並取得 Guid ediscovery 保留、 就地保留，以及 Office 365 保留原則，特別是指派給信箱。 此 cmdlet 的輸出也會指出是否信箱具有已明確排除全組織保留原則。

- **Get-organizationconfig** -使用此指令程式來取得全組織保留原則的 Guid。

若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)。

### <a name="get-mailbox"></a>Get-Mailbox

執行下列命令，以取得保留和 Office 365 保留原則套用至信箱的相關資訊。

```
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> 如果 InPlaceHolds 屬性中有太多的值，而且並非所有的顯示，您可以執行`Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds`命令，以顯示的個別行上的每個 GUID。

下表描述如何識別不同類型的保留根據*InPlaceHolds*屬性中的值，當您執行**Get-mailbox**指令程式。


|保留類型  |範例值  |如何找出保留  |
|---------|---------|---------|
|訴訟資料暫留     |    `True`     |     如果*LitigationHoldEnabled*屬性設為，將會啟用信箱的訴訟資料暫留`True`。    |
|eDiscovery 保留     |  `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`       |   *InPlaceHolds 屬性*會包含任何保留在安全性與合規性中心 eDiscovery 案例相關聯的 GUID。 您可以分清這是 eDiscovery 保留，因為 GUID 開頭`UniH`（這表示整合保留） 的前置詞。      |
|原有範圍暫止     |     `c0ba3ce811b6432a8751430937152491` <br/> 或 <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`  |     *InPlaceHolds*屬性包含信箱處於就地保留的 GUID。 您可以分清這是在原有範圍暫止因為 GUID 也不會啟動與前置詞或它的開頭`cld`前置詞。     |
|Office 365 保留原則特別套用到信箱     |    `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> 或 <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3`     |     InPlaceHolds 屬性會包含任何特定位置保留原則套用到信箱的 Guid。 您可以識別保留原則，因為 GUID 開頭`mbx`或`skp`前置詞。 `skp`前置詞會指示的保留原則套用至 Skype，商務交談在使用者的信箱中的。    |
|排除在整個組織的 Office 365 保留原則     |   `-mbxe9b52bf7ab3b46a286308ecb29624696`      |     如果信箱排除全組織的 Office 365 保留原則，排除信箱的保留原則的 GUID 會顯示在 InPlaceHolds 屬性，而且由`-mbx`前置詞。    |

### <a name="get-organizationconfig"></a>Get-organizationconfig
如果*InPlaceHolds*屬性是空的當您執行**Get-mailbox**指令程式時，仍可能有一或多個全組織的 Office 365 保留原則套用到信箱。 下列命令在 Exchange Online PowerShell 中執行到整個組織的 Office 365 保留原則來取得 Guid 的清單。

```
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> 如果 InPlaceHolds 屬性中有太多的值，而且並非所有的顯示，您可以執行`Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`命令，以顯示的個別行上的每個 GUID。

下表說明不同類型的全組織保留，以及如何識別每個包含*InPlaceHolds*屬性中，當您執行**Get-organizationconfig**指令程式的 Guid 為基礎的類型。


|保留類型  |範例值  |說明  |
|---------|---------|---------|
|Office 365 保留原則套用至 Exchange 信箱、 Exchange 公用資料夾及小組聊天    |      `mbx7cfb30345d454ac0a989ab3041051209:2`   |   整個組織的保留原則套用至 Exchange 信箱、 Exchange 公用資料夾和 Microsoft teams 1xN 聊天室以開頭的 Guid 來識別`mbx`前置詞。 請注意 1xN 聊天會儲存在個別的交談參與者的信箱。      |
|Office 365 保留原則套用至 Office 365 群組及小組通道訊息     |   `grp1a0a132ee8944501a4bb6a452ec31171:3`      |    整個組織的保留原則套用至 Office 365 群組和 Microsoft Teams 中的通道郵件以開頭的 Guid 來識別`grp`前置詞。 請注意通道訊息會存放在 Microsoft 小組與相關聯的群組信箱。     |

如需資訊的保留原則套用至 Microsoft Teams，請參閱 「 microsoft Teams 位置 」 一節[的保留原則概觀](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)。

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a>了解保留原則的 InPlaceHolds 值的格式

除了前置詞 （mbx、 skp 或群組） 可識別 InPlaceHolds 屬性做為 Office 365 保留原則中的項目，此值也包含可識別已設定原則的保留動作的類型後置詞。 例如，動作後置詞會反白顯示在下列範例中以粗體字型：

   `skp127d7cf1076947929bf136b7a2a8c36f`**: 1**

   `mbx7cfb30345d454ac0a989ab3041051209`**: 2**

   `grp1a0a132ee8944501a4bb6a452ec31171`**: 3**

下表定義三個可能的保留動作：

|值  |描述  |
|---------|---------|
|**1**     | 會指出保留原則設為刪除項目;項目時，不會保留原則。        |
|**2**    |    會指出保留原則設為保留項目;在保留期間到期之後，原則不會刪除項目。     |
|**3**     |   會指出保留原則設為保留項目，然後在保留期間到期後刪除，它們。      |

如需有關保留動作的詳細資訊，請參閱 <<c0>保留原則概觀中的 「 時間在特定期間內保留內容 」 一節。
   
## <a name="step-2-using-the-guid-to-identify-the-hold"></a>步驟 2： 使用 GUID 來識別保留

取得保留套用到信箱的 GUID 之後下, 一個步驟是使用該 GUID 來識別保留。 下列各節說明如何識別保留 （及其他資訊） 的名稱使用保留 GUID。

### <a name="ediscovery-holds"></a>eDiscovery 保留

安全性 & 合規性中心 PowerShell 找出電子文件探索保留套用到信箱中執行下列命令。 使用 （不包括 UniH 前置詞） 的 GUID ediscovery 保留您在步驟 1 中識別。 第一個命令會建立變數，包含保留; 的相關資訊此變數會用於其他命令。 第二個命令會顯示保留相關聯的 eDiscovery 案例的名稱。 第三個命令會顯示的保留名稱並保留套用至信箱的清單。

```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```
$CaseHold | FL Name,ExchangeLocation
```

若要連接到安全性 & 合規性中心 PowerShell，請參閱[連線到安全性 & 合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。

### <a name="in-place-holds"></a>就地保留

若要識別為 「 就地保留套用到信箱的 Exchange Online PowerShell 中執行下列命令。 針對您在步驟 1 中識別為 「 就地保留使用 GUID。 此命令會顯示的保留名稱並保留套用至信箱的清單。

```
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```
請注意，如果 GUID 為 「 就地保留 」 狀態的開頭`cld`前置詞，請務必執行上述命令時包含前置詞。

### <a name="office-365-retention-policies"></a>Office 365 保留原則

執行下列命令中安全性 & 合規性中心 PowerShell 身分識別的 Office 365 保留原則 （全組織或特定位置），會套用至信箱。 使用您在步驟 1 中識別的 GUID （不包括 mbx、 skp 或群組的前置詞或動作後置字元）。

```
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item"></a>識別信箱，所以已保留標籤套用至資料夾或項目保留

每當使用者套用保留標籤設定為保留內容或保留，然後刪除任何資料夾或項目在其信箱的內容， *ComplianceTagHoldApplied*信箱屬性設為**True**。 發生這種情況，信箱會被視為在保存時，就如同它已處於訴訟暫止狀態或指派給 Office 365 保留原則。 當*ComplianceTagHoldApplied*屬性設定為**True**時，可能會發生下列情形：

- 如果刪除信箱或使用者的 Office 365 使用者帳戶時，信箱會變成[非使用中信箱](inactive-mailboxes-in-office-365.md)。
- 您無法停用信箱 （主要信箱還是封存信箱，如果已啟用）。
- 可能比預期會再保留信箱中的項目。 這是因為信箱處於保留狀態，因此沒有項目將會永久刪除 （清除）。

若要檢視*ComplianceTagHoldApplied*屬性的值，請在 Exchange Online PowerShell 中執行下列命令：

```
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

如需保留標籤的詳細資訊，請參閱 < <b0>Office 365 的概觀保留標籤</b0>。

## <a name="managing-mailboxes-on-delay-hold"></a>管理信箱的延遲

從信箱移除任何類型的保留後， *DelayHoldApplied*信箱屬性的值設為**True**。 發生此情況下一次受管理的資料夾助理員處理信箱，並會偵測已移除保留。 這稱為*延遲保留*，表示實際移除保留已延遲，30 天的時間可以防止資料被永久刪除 （清除） 的信箱。 這讓系統管理員有機會搜尋或復原之後實際移除保留為止，將清除的信箱項目。 當延遲暫留時保留該信箱時，信箱會仍被視為不受限制的持續期間，保留為信箱是否訴訟暫止。 30 天後，延遲保留到期，與 Office 365 會自動嘗試移除延遲保留 （ *DelayHoldApplied*屬性設定為**False**），以便將實際移除保留。 *DelayHoldApplied*屬性設**為 False**之後, 會標示為待移除的項目都將予以受管理的資料夾助理員處理信箱時的下一個時間。

若要檢視信箱*DelayHoldApplied*屬性的值，請在 Exchange Online PowerShell 中執行下列命令。

```
Get-Mailbox <username> | FL DelayHoldApplied
```

若要移除的延遲保留到期之前，您可以在 Exchange Online PowerShell 中執行下列命令： 
 
```
Set-Mailbox <username> -RemoveDelayHoldApplied
```
請注意，您必須獲指派法律保留角色在 Exchange Online 使用*RemoveDelayHoldApplied*參數 

若要移除的延遲保留非使用中信箱上，請在 Exchange Online PowerShell 中執行下列命令：

```
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayHoldApplied
```

> [!TIP]
> 在上述命令中指定非使用中信箱的最佳方式是使用其辨別名稱或 Exchange GUID 值。 使用下列值之一，有助於防止不小心指定錯誤的信箱。 

## <a name="next-steps"></a>後續步驟

識別保留已套用至信箱之後，您可以執行工作，例如變更暫時的保留持續時間或永久移除保留，或在 Office 365 保留原則的情況下從原則中排除不在作用中的信箱。 如需執行保留與相關的工作的詳細資訊，請參閱下列主題的其中一種：

- 執行[Set-retentioncompliancepolicy AddExchangeLocationException\<使用者 mailbox>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/Set-RetentionCompliancePolicy?view=exchange-ps)命令中安全性 & 合規性中心 PowerShell，從全組織的 Office 365 保留原則中排除信箱。 請注意，此命令僅可用於保留原則*ExchangeLocation*屬性的值等於`All`。

- 執行[Set-mailbox ExcludeFromOrgHolds\<保留 GUID 不含前置詞或 suffix>](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps)命令在整個組織的 Office 365 保留原則中排除不在作用中信箱的 Exchange Online PowerShell。

- [變更 Office 365 中的非使用中信箱的保留期間](change-the-hold-duration-for-an-inactive-mailbox.md)

- [刪除 Office 365 中的非使用中信箱](delete-an-inactive-mailbox.md)

- [刪除雲端式信箱中可復原的項目資料夾中的保留項目](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)
