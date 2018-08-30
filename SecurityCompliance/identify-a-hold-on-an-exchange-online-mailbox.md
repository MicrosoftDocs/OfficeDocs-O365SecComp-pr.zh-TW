---
title: 如何找出位於 Exchange Online 信箱的保留類型
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/22/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6057daa8-6372-4e77-a636-7ea599a76128
ms.openlocfilehash: d24e51bca0e3d290f110b1ab40f3ee9ae7993678
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22527019"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a>如何找出位於 Exchange Online 信箱的保留類型

本文說明如何識別放入 Office 365 中的 Exchange Online 信箱的保留。

Office 365 提供數種貴組織可防止信箱內容會永久刪除的方式。這可讓您的組織內容以符合規範 regulars 保留或法律或其他類型的調查的持續期間。以下是 Office 365 中的保留功能 （也稱為保留） 的清單：

- **訴訟暫止狀態**-已套用至 Exchange Online 中的使用者信箱的保留。

- **eDiscovery 保留**-保留相關聯的安全性與規範中心 eDiscovery 案例。eDiscovery 保留會套用至使用者信箱與對應的信箱上為 Office 365 群組和 Microsoft 小組。

- **就地保留**-使用就地 eDiscovery 和保留工具在 Exchange 系統中已套用至使用者信箱的保留中心在 Exchange Online。

- **Office 365 保留原則**-Office 365 群組及 Microsoft 小組會保留在 Exchange Online 和對應的信箱中的使用者信箱中的內容。您可以建立保留原則會儲存在使用者信箱中的商務交談的保留 Skype。

  有兩種類型的 Office 365 可以指派給信箱的保留原則。

    - **特定位置保留原則**-這些是指派給特定使用者的內容位置原則。您可以在 Exchange Online PowerShell 中使用 Get-mailbox 指令程式取得指派至特定信箱的保留原則的相關資訊。

    - **全組織的保留原則**-這些是指派給您組織中的所有內容位置原則。您可以在 Exchange Online PowerShell 中使用 Get-organizationconfig 指令程式取得整個組織的保留原則的相關資訊。如需詳細資訊，請參閱 Office 365 概觀 （英文) 的保留原則的 「 套用至整個組織或特定位置的保留原則 」 一節。

若要管理保留信箱，您必須識別，讓您可以執行工作，例如變更保留持續時間、 暫時或永久移除保留，或從 Office 365 保留原則除外信箱被放置在信箱的保留的類型。在下列情況下，第一個步驟是保留的識別信箱的類型。與多個保留 （和不同類型的保留） 可以放在單一信箱，因為您必須識別如果您想要移除或變更這些保留放在信箱上的所有保留。

## <a name="step-1-obtaining-the-guid-for-holds-placed-on-a-mailbox"></a>步驟 1： 取得保留 GUID 放在信箱上

您可以執行下列兩個指令程式在 Exchange Online PowerShell 取得會放在信箱保留的 GUID。取得 GUID 之後，您會使用它來識別特定保留在步驟 2。請注意訴訟保留不所識別的 GUID。[啟用或停用信箱的訴訟保留。

- **Get-mailbox** -使用此指令程式來決定是否啟用信箱的訴訟暫止狀態，並取得 Guid ediscovery 保留、 就地保留，及 Office 365 明確指派給信箱的保留原則。此 cmdlet 的輸出也會表示若信箱已明確地從排除整個組織的保留原則。

- **Get-organizationconfig** -使用此指令程式來取得整個組織的保留原則的 Guid。

若要連線至 Exchange Online PowerShell，請參閱[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)。

### <a name="get-mailbox"></a>Get-Mailbox

執行下列命令以取得保留及 Office 365 保留原則套用到信箱的相關資訊。

```
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> 如果 InPlaceHolds 屬性中有太多值並不是所有的顯示，則可以執行`Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds`命令以顯示每個 GUID 分列一行。

下表說明如何識別不同類型的保留當您執行**Get-mailbox**指令程式根據*InPlaceHolds*屬性中的值。


|保留類型  |範例值  |如何識別保留  |
|---------|---------|---------|
|訴訟暫止     |    `True`     |     如果*LitigationHoldEnabled*屬性設為訴訟資料暫留啟用信箱的`True`。    |
|eDiscovery 保留     |  `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`       |   *InPlaceHolds 屬性*會包含任何保留與 eDiscovery 案例中的安全性與規範中心相關聯的 GUID。您可以分清這是因為 GUID 開頭的 eDiscovery 保留`UniH`前置詞 （這表示整合保留）。      |
|原有範圍暫止     |     `c0ba3ce811b6432a8751430937152491` <br/> 或 <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`  |     *InPlaceHolds*屬性會包含信箱處於就地保留 GUID。您可以分清這是就地保留因為 GUID 也不會啟動具有前置詞或其開頭`cld`前置詞。     |
|Office 365 特別套用到信箱的保留原則     |    `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> 或 <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3`     |     InPlaceHolds 屬性會包含任何特定位置保留原則套用至信箱的 Guid。您可以識別保留原則因為 GUID 開頭`mbx`或`skp`前置詞。`skp`前置詞表示保留原則套用至 Skype 商務使用者的信箱中的交談。    |
|排除全組織的 Office 365 保留原則     |   `-mbxe9b52bf7ab3b46a286308ecb29624696`      |     如果信箱排除在整個組織的 Office 365 保留原則、 排除信箱的保留原則的 GUID InPlaceHolds 屬性中會顯示與所識別`-mbx`前置詞。    |

### <a name="get-organizationconfig"></a>Get-organizationconfig
如果當您執行**Get-mailbox**指令程式*InPlaceHolds*屬性是空的仍可能會有一或多個整個組織的 Office 365 保留原則套用至信箱。執行下列命令在 Exchange Online PowerShell 可取得整個組織的 Office 365 保留原則清單的 Guid。

```
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> 如果 InPlaceHolds 屬性中有太多值並不是所有的顯示，則可以執行`Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`命令以顯示每個 GUID 分列一行。

下表說明不同類型的全組織保留，以及如何識別每種類型根據執行**Get-organizationconfig**指令程式時*InPlaceHolds*屬性中所含的 Guid。


|保留類型  |範例值  |描述  |
|---------|---------|---------|
|Office 365 的保留原則套用至 Exchange 信箱、 Exchange 公共資料夾及小組聊天室    |      `mbx7cfb30345d454ac0a989ab3041051209:2`   |   整個組織的保留原則套用至 Exchange 信箱、 Exchange 公共資料夾及 1xN 聊天室中的 Microsoft 小組所識別的開頭的 Guid`mbx`前置詞。請注意 1xN 聊天會儲存在個別的交談參與者的信箱。      |
|Office 365 的保留原則套用至 Office 365 群組及小組通道郵件     |   `grp1a0a132ee8944501a4bb6a452ec31171:3`      |    整個組織的保留原則套用至 Office 365 群組和通道郵件中的 Microsoft 小組所識別的開頭的 Guid`grp`前置詞。請注意通道訊息會儲存群組信箱相關聯的 Microsoft 小組中。     |

如需詳細資訊保留原則套用至 Microsoft 小組請參閱 「 小組位置 」] 區段中[的保留原則的概觀](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)。

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a>了解保留原則的 InPlaceHolds 值的格式

除了前置詞 （mbx、 skp、 或群組） 可識別 InPlaceHolds 屬性為 Office 365 保留原則中的項目，此值也包含尾碼可識別的保留原則設定的動作類型。例如會在下列範例中的粗體類型醒目提示的動作後置詞：

   `skp127d7cf1076947929bf136b7a2a8c36f`**: 1**

   `mbx7cfb30345d454ac0a989ab3041051209`**: 2**

   `grp1a0a132ee8944501a4bb6a452ec31171`**: 3**

下表定義的三種可能的保留動作：

|值  |描述  |
|---------|---------|
|**1**     | 會指出保留原則已刪除的項目 ；原則不會保留的項目。        |
|**2**    |    會指出保留原則設定為要保留的項目 ；之後保留期間到期原則不會刪除項目。     |
|**3**     |   會指出保留原則設定為保留的項目並再予以刪除之後保留期間到期。      |

如需保留動作的詳細資訊，請參閱"的特定期間內保留內容"] 區段中的[保留原則的概觀](retention-policies.md#retaining-content-for-a-specific-period-of-time)。
   
## <a name="step-2-using-the-guid-to-identify-the-hold"></a>步驟 2： 使用 GUID 來找出保留

取得保留套用到信箱的 GUID 之後下, 一步是用以識別保留的 GUID。下列各節說明如何識別保留 （和其他資訊） 的名稱使用保留 GUID。

### <a name="ediscovery-holds"></a>eDiscovery 保留

安全性及規範中心 PowerShell，以識別套用至信箱 eDiscovery 保留中執行下列命令。使用 GUID （不包括 UniH 前置詞） 的 ediscovery （英文） 保留您在步驟 1 中識別。第一個命令會建立包含保留; 的相關資訊的變數其他命令中使用這個變數。第二個命令會顯示保留相關聯的 eDiscovery 案例的名稱。第三個命令會顯示的保留名稱並保留套用至信箱的清單。

```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```
$CaseHold | FL Name,ExchangeLocation
```

若要連線至安全性與規範中心 PowerShell，請參閱[Connect to Office 365 的安全性與規範中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。

### <a name="in-place-holds"></a>就地保留

在識別為 「 就地保留套用到信箱的 Exchange Online PowerShell 中執行下列命令。使用您在步驟 1 中識別為 「 就地保留 GUID。此命令會顯示的保留名稱並保留套用至信箱的清單。

```
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```
請注意，如果 GUID 的就地保留開頭`cld`首碼，請務必執行上述命令時包含前置詞。

### <a name="office-365-retention-policies"></a>Office 365 的保留原則

執行下列命令的安全性與規範中心 PowerShell 身分識別會套用至信箱的 Office 365 保留原則 （整個組織或特定的位置）。使用您在步驟 1 中識別的 GUID （不包括的 mbx、 skp、 或群組的前置字元或的動作後置字元）。

```
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="next-steps"></a>後續步驟

識別套用到信箱的保留之後，您可以執行工作如變更保留的期限暫時或永久移除保留，或者在 Office 365 的保留原則除外非使用中的信箱原則。如需執行保留的相關工作的詳細資訊，請參閱下列主題的其中一個：

- 執行[組 RetentionCompliancePolicy AddExchangeLocationException\<使用者信箱 >](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/Set-RetentionCompliancePolicy?view=exchange-ps)命令的安全性及規範中心 PowerShell，以從全組織的 Office 365 保留原則中排除信箱。請注意此命令可只用於保留原則其中*ExchangeLocation*屬性的值等於`All`。

- 執行[Set-mailbox ExcludeFromOrgHolds\<保留 GUID 而首碼或尾碼 >](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps)在整個組織的 Office 365 保留原則中排除不在作用中信箱的 Exchange Online PowerShell 命令。

- [變更 Office 365 中不在作用中信箱的保留期間](change-the-hold-duration-for-an-inactive-mailbox.md)

- [刪除非作用中的信箱在 Office 365](delete-an-inactive-mailbox.md)

- [刪除雲端式信箱中可復原的項目資料夾中的保留項目](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)
