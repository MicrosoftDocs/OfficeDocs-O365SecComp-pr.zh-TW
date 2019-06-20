---
title: 定義資訊屏障原則
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/19/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: 瞭解如何在 Microsoft 小組中定義資訊障礙的原則。
ms.openlocfilehash: fb162e380fa467cf3e832bd7bbdafcde136b1db6
ms.sourcegitcommit: 087cf1a022b13c46e207270d6837f09a9752c972
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/20/2019
ms.locfileid: "35083861"
---
# <a name="define-policies-for-information-barriers-preview"></a>定義資訊障礙的原則 (預覽)

## <a name="overview"></a>概觀

有了資訊障礙, 您可以定義原則, 以防止特定的使用者區段相互通訊, 或允許特定的區段只能與特定的其他區段進行通訊。 資訊屏障原則可協助您的組織維持相關行業標準與法規的合規性, 並避免潛在的利益衝突。 若要深入瞭解, 請參閱[資訊障礙 (預覽)](information-barriers.md)。 

本文說明如何規劃、定義、實施及管理資訊屏障原則。 涉及數個步驟, 工作流程分成數個部分。 請務必先閱讀[必要條件](#prerequisites)和整個程式, 再開始定義 (或編輯) 資訊屏障原則。

> [!TIP]
> 本文包含一個[範例案例](#example-contosos-departments-segments-and-policies)和一個[可下載的 Excel 活頁簿](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx), 可協助您規劃及定義資訊障礙原則。

## <a name="concepts-of-information-barrier-policies"></a>資訊障礙原則的概念

瞭解資訊屏障原則的基礎概念會很有説明:

- **使用者帳戶屬性**是在 Azure Active Directory (或 Exchange Online) 中定義的。 這些屬性可以包括部門、職稱、位置、小組名稱及其他工作設定檔詳細資料。 

- **區段**是使用選取的**使用者帳戶屬性**, 在 [Office 365 安全性 & 合規性中心] 中定義的使用者集合。 (請參閱[支援的屬性清單](information-barriers-attributes.md))。 

- **資訊屏障原則**會決定通訊限制或限制。 當您定義資訊屏障原則時, 您可以選擇兩種原則:
    - 「封鎖」原則會防止一個區段與另一個區段進行通訊。
    - 「允許」原則允許一段時間只與特定的其他區段進行通訊。

- **原則應用程式**是在定義所有資訊屏障原則之後完成, 而且您已準備好將它們套用到您的組織中。

## <a name="the-work-flow-at-a-glance"></a>工作流程概覽

|階段    |涉及的專案  |
|---------|---------|
|[確定符合必要條件](#prerequisites)     |-確認您具備必要的[授權和許可權](information-barriers.md#required-licenses-and-permissions)<br/>-確認您的目錄包含分割使用者的資料<br/>-啟用 Microsoft 小組的範圍目錄搜尋<br/>-請確定已開啟審核記錄<br/>-使用 PowerShell (提供範例)<br/>-提供 Microsoft 小組的系統管理員同意 (包括步驟)          |
|[第1部分: 分割組織中的使用者](#part-1-segment-users)     |-決定所需的原則<br/>-建立要定義的區段清單<br/>-識別要使用的屬性<br/>-以原則篩選的條款定義區段        |
|[第2部分: 定義資訊障礙原則](#part-2-define-information-barrier-policies)     |-定義您的原則 (尚不適用)<br/>-選擇兩種類型 (封鎖或允許) |
|[第3部分: 套用資訊屏障原則](#part-3-apply-information-barrier-policies)     |-將原則設為主動狀態<br/>-執行原則應用程式<br/>-查看原則狀態         |
|(視需要而來)[編輯區段或原則](#edit-a-segment-or-a-policy)     |-編輯區段<br/>-編輯或移除原則<br/>-執行原則應用程式<br/>-查看原則狀態         |
|(視需要而來)[疑難排解](information-barriers-troubleshooting.md)|-當事物未如預期運作時採取動作|

## <a name="prerequisites"></a>必要條件

除了[必要的授權和許可權](information-barriers.md#required-licenses-and-permissions)之外, 請確定符合下列需求: 
     
- **目錄資料**。 請確定您組織的結構反映在目錄資料中。 若要這麼做, 請確定在 Azure Active Directory (或 Exchange Online) 中正確填入使用者帳戶屬性, 例如群組成員資格、部門名稱等等。 若要深入瞭解, 請參閱下列資源:
  - [資訊障礙原則的屬性 (預覽)](information-barriers-attributes.md)
  - [使用 Azure Active Directory 新增或更新使用者的設定檔資訊](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)
  - [使用 Office 365 PowerShell 中設定使用者帳戶屬性](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)

- **範圍目錄搜尋**。 在您定義組織的第一個資訊屏障原則之前, 您必須[在 Microsoft 小組中啟用範圍目錄搜尋](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)。 在您設定或定義資訊屏障原則之前, 請至少等候24小時之後啟用範圍目錄搜尋。

- **審核記錄**。 為了查詢原則應用程式的狀態, 必須開啟 audit 記錄。 在您開始定義區段或原則之前, 我們建議您這麼做。 若要深入瞭解, 請參閱[開啟或關閉 Office 365 audit log search](turn-audit-log-search-on-or-off.md)。

- **PowerShell**。 目前, 資訊屏障原則是在 Office 365 安全性 & 合規性中心使用 PowerShell Cmdlet 來定義及管理。 雖然本文提供了數個範例, 但是您必須熟悉 PowerShell Cmdlet 和參數。 連線[至 Office 365 安全性 & 合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。

- **Microsoft 小組中資訊障礙的系統管理員同意**。 當您的原則就緒時, 資訊障礙就可以從交談會話中移除他們不應該在交談中的人員。 這有助於確保您的組織符合原則和規定。 使用下列程式可讓資訊障礙原則在 Microsoft 小組中如預期的方式運作。 

   1. 執行下列 PowerShell Cmdlet:

      ```
      Login-AzureRmAccount 
      $appId="bcf62038-e005-436d-b970-2a472f8c1982" 
      $sp=Get-AzureRmADServicePrincipal -ServicePrincipalName $appId
      if ($sp -eq $null) { New-AzureRmADServicePrincipal -ApplicationId $appId }
      Start-Process  "https://login.microsoftonline.com/common/adminconsent?client_id=$appId"
      ```

   2. 出現提示時, 使用您的公司或學校帳戶登入 Office 365。

   3. 在 [**要求的許可權**] 對話方塊中, 查看資訊, 然後選擇 [**接受**]。

當符合所有必要條件時, 請繼續進行下一節。

> [!TIP]
> 為協助您準備方案, 本文包含範例案例。 [請參閱 Contoso 的部門、區段及原則](#example-contosos-departments-segments-and-policies)。<p>此外, 也可以使用可下載的 Excel 活頁簿, 協助您規劃及定義您的區段和原則 (以及建立您的 PowerShell Cmdlet)。 [取得活頁簿](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx)。 

## <a name="part-1-segment-users"></a>第1部分: 分割使用者

在這個階段中, 您可以決定所需的資訊屏障原則、建立區段清單以定義, 然後定義您的區段。

### <a name="determine-what-policies-are-needed"></a>決定所需的原則

考慮法律和行業法規, 誰是貴組織內需要資訊障礙原則的群組？ 建立清單。 是否有任何群組應該防止與其他群組通訊？ 是否有任何群組應該允許只與一或兩個其他群組通訊？ 請考慮您所需的原則屬於下列兩個群組之一:
- 「封鎖」原則防止一個群組與另一個群組通訊。
- 「允許」原則允許群組僅與特定的其他特定群組進行通訊。

當您擁有群組和原則的初始清單時, 請繼續識別您將需要的區段。 

### <a name="identify-segments"></a>識別區段

除了您的初始原則清單之外, 請列出您組織的區段。 將包含在資訊屏障原則中的使用者應該屬於某個區段, 而且使用者不應屬於兩個或多個區段。 每個區段只能套用一個資訊屏障原則。 

決定您要用來定義資料段的組織目錄資料中的哪些屬性。 您可以使用*部門*、 *MemberOf*或任何支援的屬性。 請確定您為使用者選取的屬性中有值。 [請參閱資訊障礙 (預覽) 支援的屬性清單](information-barriers-attributes.md)。

> [!IMPORTANT]
> 在**繼續下一節之前, 請確定您的目錄資料具有可用來定義資料段的屬性值**。 如果您的目錄資料沒有您要使用之屬性的值, 則在繼續進行資訊障礙之前, 必須更新使用者帳戶以包含該資訊。 若要取得這項協助, 請參閱下列資源:<br/>- [使用 Office 365 PowerShell 設定使用者帳戶屬性](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)<br/>- [使用 Azure Active Directory 新增或更新使用者的設定檔資訊](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

### <a name="define-segments-using-powershell"></a>使用 PowerShell 定義線段

定義區段不會影響使用者;它只會設定要定義並套用的資訊屏障原則階段。

若要定義組織區段, 請使用**OrganizationSegment 指令程式**搭配**UserGroupFilter**參數, 該參數對應至您要使用的[屬性](information-barriers-attributes.md)。

句法`New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"`

範例： `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"`

在此範例中, 名為*hr*的區段是使用*Hr*、[*部門*] 屬性中的值來定義。 Cmdlet 的 "-eq" 部分是指 "等於"。

請針對您要定義的每個區段重複此程式。

在執行每個 Cmdlet 之後, 您應該會看到有關新線段的詳細資料清單。 詳細資料包含區段的類型、建立或上次修改的日期, 等等。 

> [!IMPORTANT]
> **請確定您的區段沒有重迭**。 將受到資訊障礙影響的每個使用者都應屬於一個 (且只有一個) 區段。 任何使用者都不應該屬於兩個或多個區段。 (請參閱[範例: Contoso](#contosos-defined-segments)在本文中定義的區段。)

定義您的區段之後, 請繼續定義資訊障礙原則。

### <a name="using-equals-and-not-equals-in-segment-definitions"></a>在區段定義中使用「等於」和「不等於」

在上方顯示的第一個範例中, 我們定義了包含邏輯、*部門等於 HR*的區段。 您也可以使用 "not 等於" 參數來定義線段, 如下列範例所示:

句法`New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -ne 'attributevalue'"`

範例： `New-OrganizationSegment -Name "NotSales" -UserGroupFilter "Department -ne 'Sales'"`

在此範例中, 我們定義了一個稱為 NotSales 的區段, 其中包含不在銷售的任何人。 Cmdlet 的 "-ne" 部分是指 "not equals"。

此外, 您可以使用 "等於" 和 "not =" 參數來定義區段。

範例： `New-OrganizationSegment -Name "LocalFTE" -UserGroupFilter "Location -eq 'Local'" and "Position -ne 'Temporary'"`

在這個範例中, 我們定義了一個稱為*LocalFTE*的區段, 其中包括位於本機的人員, 且其位置未列為*暫時*。

## <a name="part-2-define-information-barrier-policies"></a>第2部分: 定義資訊障礙原則

決定您是否需要防止特定區段之間的通訊, 或限制特定區段的通訊。 理想情況下, 您會使用最小的原則數目, 以確保您的組織符合法律和行業的需求。

使用您的使用者區段清單, 以及您想要定義的資訊屏障原則, 選取案例, 然後依照步驟進行。 

- [案例 1: 封鎖區段之間的通訊](#scenario-1-block-communications-between-segments)
- [案例 2: 允許區段只與一個其他區段通訊](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)

> [!IMPORTANT]
> 請**確定您在定義原則時, 不會將多個原則指派**給一個區段。 例如, 如果您為名為*sales*的部門定義一個原則, 請不要為*sales*定義額外的原則。<p>此外, 當您定義資訊屏障原則時, 請務必將這些原則設定為非使用中狀態, 直到您準備好要套用這些原則為止。 定義 (或編輯) 原則不會影響使用者, 直到這些原則設定為 [作用中] 狀態, 然後套用為止。

(請參閱[範例: Contoso 的資訊屏障原則](#contosos-information-barrier-policies)在本文中)。

### <a name="scenario-1-block-communications-between-segments"></a>案例 1: 封鎖區段之間的通訊

當您想要封鎖多個片段之間的通訊時, 您會定義兩個原則: 一個用於每個方向。 每個原則只會封鎖通訊一種方式。

例如, 假設您想要封鎖區段 A 與區段 B 之間的通訊。在這種情況下, 您可以定義一個原則, 讓區段 A 無法與欄位 B 通訊, 然後定義第二個原則, 以防止段 B 與區段 A 進行通訊。

1. 若要定義您的第一個封鎖原則, 請使用**InformationBarrierPolicy 指令程式**搭配**SegmentsBlocked**參數。 

    句法`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsBlocked "segment2name"`

    範例： `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive`

    在此範例中, 我們為名為*sales*的部門定義一個名為「*銷售-調研*」的原則。 使用中和套用時, 此原則可防止*銷售*人員與「*調查*」區段中的人員進行通訊。

2. 若要定義第二個封鎖區段, 請再次使用**InformationBarrierPolicy 指令程式**搭配**SegmentsBlocked**參數, 這段時間會將分次還原。

    範例： `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive`

    在此範例中, 我們定義了一個稱為「*調查-銷售*」的原則, 以防止與*銷售*通訊的*資訊檢索*。
 
2. 請繼續執行下列其中一項操作:

   - (如有需要)[定義原則以允許區段只與一個其他的區段進行通訊](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment) 
   - (在定義所有原則之後)套用[資訊屏障原則](#part-3-apply-information-barrier-policies)

### <a name="scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment"></a>案例 2: 允許區段只與一個其他區段通訊

1. 若要允許一個區段只與一個其他區段通訊, 請使用**InformationBarrierPolicy 指令程式**搭配**SegmentsAllowed**參數。 

    句法`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name"`

    範例： `New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR" -State Inactive`

    在此範例中, 我們定義了一個名為「製造 *-HR* 」 ** 的原則。 使用中和套用時, 此原則可讓*製造*人員只能與稱為*HR*的部門中的人員進行通訊。 (在此情況下,*製造*無法與不屬於*HR*的使用者通訊。)

    **如有需要, 您可以使用此 Cmdlet 指定多個區段, 如下列範例所示。**

    句法`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name", "segment3name"`

    **範例 2: 定義原則以允許區段只與其他兩個區段進行通訊**    

    `New-InformationBarrierPolicy -Name "Research-HRManufacturing" -AssignedSegment "Research" -SegmentsAllowed "HR","Manufacturing" -State Inactive`

    在此範例中, 我們定義了一個原則, 讓*調研*區段只能與*HR*和*製造公司*通訊。

    針對您要定義的每個原則, 重複此步驟, 讓特定的區段只能與特定的特定區段進行通訊。

2. 請繼續執行下列其中一項操作:

   - (如有需要)[定義原則以封鎖區段之間的通訊](#scenario-1-block-communications-between-segments) 
   - (在定義所有原則之後)套用[資訊屏障原則](#part-3-apply-information-barrier-policies)

## <a name="part-3-apply-information-barrier-policies"></a>第3部分: 套用資訊屏障原則

資訊屏障原則在您將其設為 [作用中] 狀態後, 才會生效, 然後套用原則。

1. 使用**InformationBarrierPolicy**指令程式來查看已定義的原則清單。 記下每個原則的狀態和身分識別 (GUID)。

    句法`Get-InformationBarrierPolicy`

2. 若要將原則設定為 [使用中] 狀態, 請使用**InformationBarrierPolicy**指令程式搭配**Identity**參數, 並將**State**參數**** 設為 [作用中]。 

    句法`Set-InformationBarrierPolicy -Identity GUID -State Active`

    範例： `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Active`
    
    在此範例中, 我們設定了 GUID *43c37853-ea10-4b90-a23d-ab8c93772471*為 [使用中] 狀態的資訊屏障原則。

    請視需要對每個原則重複此步驟。

3. 當您完成將資訊關卡原則設定為 [作用中] 狀態時, 請使用 Office 365 安全性 & 規範中心內的 **「開始-InformationBarrierPoliciesApplication** Cmdlet。

    句法`Start-InformationBarrierPoliciesApplication`

    在大約半小時之後, 您組織的原則會套用至使用者。 如果您的組織很大, 可能需要24小時 (或更多), 才能完成此程式。 (一般來說, 處理5000使用者帳戶需要大約一小時的時間。)

## <a name="view-status-of-user-accounts-segments-policies-or-policy-application"></a>查看使用者帳戶、區段、原則或原則應用程式的狀態

您可以使用 PowerShell 來查看使用者帳戶、區段、原則和原則應用程式的狀態, 如下表所列。

|若要查看此  |執行  |
|---------|---------|
|使用者帳戶     |使用**InformationBarrierRecipientStatus 指令程式**搭配 Identity 參數。 <p>句法`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p>您可以使用唯一識別每個使用者的任何值, 例如名稱、別名、辨別名稱、正常化功能變數名稱、電子郵件地址或 GUID。 <p>範例： `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p>在此範例中, 我們會參考 Office 365 中的兩個使用者帳戶: *meganb* for *Megan*, 以及*alexw* for *Alex*。 <p>(您也可以將此 Cmdlet 用於單一使用者: `Get-InformationBarrierRecipientStatus -Identity <value>`) <p>此 Cmdlet 會傳回使用者的相關資訊, 例如屬性值以及所套用的任何資訊屏障原則。|
|細分     |使用**OrganizationSegment 指令程式**。<p>句法`Get-OrganizationSegment` <p>這會顯示針對您組織所定義之所有區段的清單。         |
|資訊屏障原則     |使用**InformationBarrierPolicy 指令程式**。 <p> 句法`Get-InformationBarrierPolicy` <p>這會顯示已定義的資訊屏障原則及其狀態的清單。       |
|最新的資訊屏障原則應用程式     | 使用**InformationBarrierPoliciesApplicationStatus 指令程式**。 <p>句法`Get-InformationBarrierPoliciesApplicationStatus`<p>    這會顯示原則應用程式是否已完成、失敗或正在進行中的資訊。       |
|所有資訊屏障原則應用程式|執行`Get-InformationBarrierPoliciesApplicationStatus -All $true`<p>這會顯示原則應用程式是否已完成、失敗或正在進行中的資訊。|

## <a name="stop-a-policy-application"></a>停止原則應用程式

如果您已開始套用資訊屏障原則, 而您想要停止套用這些原則, 請使用下列程式。 請記住, 此程式會花大約30-35 分鐘的時間來開始。

1. 若要查看最新資訊屏障原則應用程式的狀態, 請使用**InformationBarrierPoliciesApplicationStatus**指令程式。

    句法`Get-InformationBarrierPoliciesApplicationStatus`

    記下應用程式的 GUID。

2. 使用**InformationBarrierPoliciesApplication**指令程式搭配 Identity 參數。

    句法`Stop-InformationBarrierPoliciesApplication -Identity GUID`

    範例： `InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1`

## <a name="edit-a-segment-or-a-policy"></a>編輯區段或原則

### <a name="edit-a-segment"></a>編輯區段

1. 若要查看所有現有的區段, 請使用**OrganizationSegment 指令程式**。
    
    句法`Get-OrganizationSegment`

    您會看到每個區段和詳細資料的清單, 例如區段類型、其 UserGroupFilter 值、建立日期或上次修改者、GUID 等等。

    > [!TIP]
    > 列印或儲存您的區段清單供日後參考。 例如, 如果您想要編輯某個區段, 您將需要知道其名稱或識別值 (這會與 Identity 參數搭配使用)。

2. 若要編輯區段, 請使用**OrganizationSegment 指令程式**搭配**Identity**參數及相關的詳細資料。 

    句法`Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"`

    範例： `Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"`

    在此範例中, 針對具有 GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*的區段, 我們會將部門名稱更新為 "HRDept"。

當您完成組織的資料段編輯後, 您可以繼續[定義](#part-2-define-information-barrier-policies)或[編輯](#edit-a-policy)資訊屏障原則。

### <a name="edit-a-policy"></a>編輯原則

1. 若要查看目前資訊屏障原則的清單, 請使用**InformationBarrierPolicy 指令程式**。

    句法`Get-InformationBarrierPolicy`

    在結果清單中, 識別您要變更的原則。 記下原則的 GUID 和名稱。

2. 使用**InformationBarrierPolicy**指令程式搭配**Identity**參數, 並指定您想要進行的變更。

    範例: 假設已定義原則來封鎖*研究*資料段與*銷售*和*行銷*資料段的通訊。 原則是使用此 Cmdlet 定義的:`New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`
    
    假設我們想要變更它, 讓*研究*部門中的人員只能與*HR*區段中的人通訊。 若要進行這種變更, 我們會使用此 Cmdlet:`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`

    在此範例中, 我們將 "SegmentsBlocked" 變更為 "SegmentsAllowed", 並指定*HR*區段。

3. 當您完成編輯原則時, 請務必套用您的變更。 (請參閱套用[資訊屏障原則](#part-3-apply-information-barrier-policies)。)

### <a name="remove-a-policy"></a>移除原則

1. 若要查看目前資訊屏障原則的清單, 請使用**InformationBarrierPolicy 指令程式**。

    句法`Get-InformationBarrierPolicy`

    在結果清單中, 識別您要移除的原則。 記下原則的 GUID 和名稱。 請確定原則設定為非使用中狀態。

2. 使用**InformationBarrierPolicy**指令程式搭配 Identity 參數。

    句法`Remove-InformationBarrierPolicy -Identity GUID`

    範例: 假設我們想要移除 GUID *43c37853-ea10-4b90-a23d-ab8c93772471*的原則。 若要這麼做, 我們會使用此 Cmdlet:
    
    `Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471`

    出現提示時, 請確認變更。

3. 針對您要移除的每個原則, 重複步驟1-2。

4. 當您完成移除原則時, 請套用您的變更。 若要這麼做, 請使用**InformationBarrierPoliciesApplication 指令程式**。

    句法`Start-InformationBarrierPoliciesApplication`

    針對您的組織, 會套用使用者的變更。 如果您的組織很大, 可能需要24小時 (或更多), 才能完成此程式。

### <a name="set-a-policy-to-inactive-status"></a>將原則設定為非使用中狀態

1. 若要查看目前資訊屏障原則的清單, 請使用**InformationBarrierPolicy 指令程式**。

    句法`Get-InformationBarrierPolicy`

    在結果清單中, 識別您要變更 (或移除) 的原則。 記下原則的 GUID 和名稱。

2. 若要將原則的狀態設定為非使用中, 請使用**InformationBarrierPolicy**指令程式搭配 Identity 參數, 並將 State 參數設為非使用中。

    句法`Set-InformationBarrierPolicy -Identity GUID -State Inactive`

    `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive`

    在此範例中, 我們將*43c37853-ea10-4b90-a23d-ab8c9377247*的資訊屏障原則設定為非使用中狀態。

3. 若要套用您的變更, 請使用**InformationBarrierPoliciesApplication 指令程式**。

    句法`Start-InformationBarrierPoliciesApplication`

    針對您的組織, 會套用使用者的變更。 如果您的組織很大, 可能需要24小時 (或更多), 才能完成此程式。 (一般來說, 處理5000使用者帳戶需要大約一小時的時間。)

此時, 一或多個資訊屏障原則會設為非使用中狀態。 從這裡, 您可以執行下列任何一項操作:
- 保留原樣 (原則設定為非作用中的狀態對使用者不會有任何影響)
- [編輯原則](#edit-a-policy) 
- [移除原則](#remove-a-policy)

## <a name="example-contosos-departments-segments-and-policies"></a>範例: Contoso 的部門、區段和原則

若要查看組織如何定義區段和原則的方法, 請考慮下列範例。

### <a name="contosos-departments-and-plan"></a>Contoso 的部門與計畫

Contoso 有五個部門: HR、銷售、行銷、調研和製造。 為了維持與業界法規的相容性, 某些部門中的人員不應該與其他部門通訊, 如下表所列:

|部分  |可以交談  |無法交談  |
|---------|---------|---------|
|人力資源     |所有人         |(無限制)         |
|銷售量     |HR、行銷、製造業         |參考資料         |
|行銷     |所有人         |(無限制)         |
|參考資料     |HR、行銷、製造業        |銷售量     |
|製造 |人力資源、行銷 |非 HR 或 Marketing 以外的任何人 |

考慮到這一點, Contoso 的計畫包含三種資訊屏障原則:

1. 旨在防止銷售人員與調查進行通訊的原則 (和另一個原則, 以防止與銷售通訊的資訊檢索)
2. 一種原則, 其設計目的是讓製造業只能與 HR 和 Marketing 通訊 

您不需要定義 HR 或 Marketing 的原則。

### <a name="contosos-defined-segments"></a>Contoso 的定義區段

Contoso 會使用 Azure Active Directory 中的部門屬性來定義區段, 如下所示:

|部門  |區段定義  |
|---------|---------|
|人力資源     | `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"`        |
|銷售量     | `New-OrganizationSegment -Name "Sales" -UserGroupFilter "Department -eq 'Sales'"`        |
|行銷     | `New-OrganizationSegment -Name "Marketing" -UserGroupFilter "Department -eq 'Marketing'"`        |
|參考資料     | `New-OrganizationSegment -Name "Research" -UserGroupFilter "Department -eq 'Research'"`        |
|製造     | `New-OrganizationSegment -Name "Manufacturing" -UserGroupFilter "Department -eq 'Manufacturing'"`        |

在定義的區段中, Contoso 會繼續定義原則。 

### <a name="contosos-information-barrier-policies"></a>Contoso 的資訊屏障原則

Contoso 會定義三個原則, 如下表所述:

|原則  |原則定義  |
|---------|---------|
|原則 1: 防止銷售與資訊檢索進行通訊     | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> 在此範例中, 資訊屏障原則稱為「*銷售-研究*」。 使用且套用此原則時, 將有助於防止銷售部門中的使用者與研究資料段中的使用者進行通訊。 這是單向原則;它不會防止研究與銷售進行通訊。 為此, 需要原則2。      |
|原則 2: 防止與銷售通訊的調研     | `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` <p> 在此範例中, 資訊屏障原則稱為「*調研-銷售*」。 使用且套用此原則時, 將有助於防止研究資料段中的使用者與銷售部門中的使用者進行通訊。       |
|原則 3: 允許製造業僅與 HR 和 Marketing 通訊     | `New-InformationBarrierPolicy -Name "Manufacturing-HRMarketing" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Marketing" -State Inactive` <p>在這種情況下, 資訊屏障原則稱為*車間-HRMarketing*。 使用且套用此原則時, 製造業只能與 HR 和 Marketing 通訊。 請注意, HR 和 Marketing 不會受到限制, 無法與其他段進行通訊。 |

根據定義的區段和原則, Contoso 會執行**InformationBarrierPoliciesApplication**指令程式, 以套用原則。 

完成後, Contoso 就符合法律和行業的需求。

## <a name="related-articles"></a>相關文章

[取得資訊障礙的概況](information-barriers.md)

[深入瞭解 Microsoft 小組中的資訊障礙](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

[資訊障礙原則的屬性 (預覽)](information-barriers-attributes.md)

[疑難排解資訊障礙 (預覽)](information-barriers-troubleshooting.md)
