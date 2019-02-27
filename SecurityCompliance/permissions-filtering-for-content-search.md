---
title: 設定內容搜尋的權限篩選
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/14/2018
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
ms.assetid: 1adffc35-38e5-4f7d-8495-8e0e8721f377
description: 使用內容搜尋篩選，讓搜尋 Office 365 組織中信箱和網站的子集 eDiscovery 管理員的權限。
ms.openlocfilehash: f9f3344fce11e5eacfede43aab593b6235cfe1c7
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296906"
---
# <a name="configure-permissions-filtering-for-content-search"></a>設定內容搜尋的權限篩選

您可以使用搜尋篩選，讓搜尋 Office 365 組織中信箱和網站的子集 eDiscovery 管理員的權限。您也可以使用篩選，讓該相同的 eDiscovery 管理員只搜尋符合特定搜尋準則的信箱或網站內容的權限。例如，您可能會讓搜尋之使用者的信箱中的特定位置或部門 eDiscovery 管理員。您執行這項作業來建立可使用支援的收件者篩選器來限制哪些信箱可搜尋的篩選。您也可以建立會指定要搜尋信箱內容篩選器。做法是建立可使用的可搜尋的訊息屬性的篩選。同樣地，您可能會讓只有您組織中搜尋特定的 SharePoint 網站的 eDiscovery 管理員。您執行這項作業所建立的篩選會限制可搜尋的網站。您也可以建立會指定要搜尋網站內容的篩選。做法是建立可使用的可搜尋網站屬性的篩選。

您也可以使用搜尋篩選建立邏輯界限 （稱為*規範界限*） Office 365 組織內可控制使用者的內容位置 （例如信箱、 SharePoint 網站及 OneDrive 帳戶） 的權限的可搜尋特定的 eDiscovery 管理員。如需詳細資訊，請參閱 ＜ [Set up Office 365 中的 eDiscovery 調查的規範界限](set-up-compliance-boundaries.md)。
  
Office 365 安全性內容的搜尋功能的支援搜尋篩選的權限&amp;規範中心。下列四個 cmdlet 可讓您設定及管理搜尋 permisisons 篩選：
  
[新 ComplianceSecurityFilter](#new-compliancesecurityfilter)

[Get-ComplianceSecurityFilter](#get-compliancesecurityfilter)

[設定 ComplianceSecurityFilter](#set-compliancesecurityfilter)

[移除 ComplianceSecurityFilter](#remove-compliancesecurityfilter)

## <a name="before-you-begin"></a>開始之前

- 若要執行規範安全性篩選器指令程式，您必須是安全性組織管理角色群組的成員&amp;規範中心。如需詳細資訊，請參閱[Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。
    
- 您必須連線至這兩種安全性的 Windows PowerShell&amp;規範中心和 Exchange Online 的組織使用規範安全性篩選器指令程式。因為這些指令程式需要這就是為什麼您必須連線到 Exchange Online 信箱屬性存取這是必要的。請參閱下一節中的步驟。 
    
- 請參閱[More information](#more-information)一節以取得搜尋權限篩選器的詳細資訊。 
    
- 搜尋篩選的權限是適用於非使用中的信箱，這表示您可以使用信箱和信箱內容篩選來限制可以搜尋非使用中的信箱。請參閱[的詳細資訊](#more-information)] 區段中的篩選的權限及非使用中信箱的其他資訊。 
    
-  搜尋篩選的權限無法用來限制誰可以在 Exchange 搜尋公用資料夾中。 
    
- 沒有可建立在組織中的搜尋權限篩選數目受限制。但如有 100 個以上的搜尋權限篩選將會影響搜尋效能。若要在組織中的搜尋權限篩選數目維持盡可能的小，建立 Exchange、 SharePoint 及 OneDrive for 結合規則盡可能在單一篩選中的篩選器。
    
## <a name="connect-to-the-security-amp-compliance-center-and-exchange-online-in-a-single-remote-powershell-session"></a>連線至安全性&amp;規範中心和 Exchange Online 中的單一遠端 PowerShell 工作階段

1. 使用.ps1 filename 尾碼儲存到 Windows PowerShell 指令碼檔案的下列文字。例如，您無法將它儲存到名為 ConnectEXO CC.ps1 的檔案。
    
    ```
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -AllowClobber -DisableNameChecking
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. 在您的本機電腦上開啟 Windows PowerShell，移至您在上一個步驟中建立的指令碼所在的資料夾，然後執行指令碼 ；例如：
    
    ```
    .\ConnectEXO-CC.ps1
    ```
 
如何知道是否這是否正常運作？在您執行的指令碼指令程式的安全性之後&amp;規範中心和 Exchange Online 匯入至本機的 Windows PowerShell 工作階段。如果您沒有收到任何錯誤，您已順利連線。快速測試是執行安全性&amp;規範中心 cmdlet — 例如**安裝 UnifiedCompliancePrerequisite** — 和 Exchange Online 指令程式，例如**Get-mailbox**。 
  
如果您收到錯誤，請檢查下列需求：
  
- 密碼錯誤是常見的問題。再次執行這兩個步驟，並密切注意您在步驟 1 中輸入的使用者名稱和密碼。
    
- 確認您的帳戶具有存取安全性權限&amp;規範中心。如需詳細資訊，請參閱[授與使用者存取權的安全性&amp;規範中心](grant-access-to-the-security-and-compliance-center.md)。
    
- 為防止拒絕服務 (DoS) 攻擊，您正在限制在三個遠端 PowerShell 連線到安全性&amp;規範中心。
    
- 您必須設定 Windows PowerShell 才能執行指令碼。您只需在電腦上設定此設定一次，而不用在每次連線時進行設定。若要讓 Windows PowerShell 執行經過簽署的指令碼，請在提高權限的 Windows PowerShell 視窗 (藉由選取 **[以管理員身分執行]** 開啟的 Windows PowerShell 視窗) 中執行下列命令。

    ```
    Set-ExecutionPolicy RemoteSigned
    ```
- 必須是本機電腦和 Office 365 之間開啟 TCP 連接埠 80 流量。很可能是開啟但是很考量您的組織若有限制網際網路存取原則的某個項目。
    

  
## <a name="new-compliancesecurityfilter"></a>新 ComplianceSecurityFilter
<a name="New"> </a>

**新增 ComplianceSecurityFilter**用來建立新的搜尋權限篩選。下表說明此 cmdlet 之參數。所有的參數，才能建立規範安全性篩選。 
  
|**參數**|**描述**|
|:-----|:-----|
| _動作_ <br/> | _Action_參數會指定篩選條件套用至搜尋動作的類型。會在可能的內容搜尋動作：<br/><br/> **匯出**-filter 匯出搜尋結果時套用。  <br/> 預覽搜尋結果時套用**預覽**篩選。  <br/> **清除**-filter 清除搜尋結果時套用。  <br/> **搜尋**篩選條件套用時執行搜尋。  <br/> **所有**-filter 套用至所有搜尋動作。  <br/> |
| _FilterName_ <br/> |_FilterName_參數會指定權限篩選器名稱。此名稱會用來識別篩選器時使用**Get ComplianceSecurityFilter**、 **Set-ComplianceSecurityFilter**與**移除 ComplianceSecurityFilter** cmdlet。<br/> |
| _篩選_ <br/> | _篩選_參數會指定規範安全性篩選的搜尋準則。您可以建立篩選器的三個不同的種類：<br/><br/> **信箱篩選**-這個類型的篩選器會指定可以搜尋指定的使用者 （_使用者_參數所指定） 的信箱。此類型語法是篩選的**Mailbox_** _MailboxPropertyName_，其中_MailboxPropertyName_會指定用來範圍可搜尋之信箱的信箱屬性。例如，信箱篩選`"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"`就 CustomAttribute10 屬性中允許使用者指派此篩選要只搜尋信箱包含值"OttawaUsers"。<br/>  任何支援的可篩選收件者屬性可以用於_MailboxPropertyName_屬性。如需支援屬性的清單，請參閱[Filterable properties for-RecipientFilter 參數](https://go.microsoft.com/fwlink/p/?LinkId=784903)。<br/><br/> **信箱內容篩選**-這種類型的篩選器會套用在可搜尋的內容。它會指定的使用者可以搜尋的信箱內容。此類型語法是篩選的**MailboxContent_** _SearchablePropertyName:value_，其中_SearchablePropertyName_會指定可以在內容搜尋中指定的關鍵字查詢語言 (KQL) 屬性。例如，信箱內容篩選器`MailboxContent_recipients:contoso.com`會允許使用者指派此篩選要只搜尋傳送至 contoso.com 網域中的收件者的郵件。<br/>  如需可搜尋的郵件內容的清單，請參閱[關鍵字查詢和搜尋條件的內容搜尋](keyword-queries-and-search-conditions.md)。  <br/><br/> **網站與網站內容篩選**-有兩個 SharePoint 及 OneDrive for 商務網站相關的篩選器可用來指定哪些網站或網站內容可以搜尋指定的使用者：  <br/><br/> - **Site_**_SearchableSiteProperty_ <br/> - **SiteContent_**_SearchableSiteProperty_ <br/><br/>  這些兩個篩選器可以互換 ；例如`"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"`和`"SiteContent_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"`會傳回相同的結果。為了協助您識別篩選器的運作，您可以使用，但是`Site_`指定網站相關的屬性 （例如網站 URL) 和`SiteContent_`指定與內容相關的屬性 （例如文件類型。例如，篩選`"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"`會允許使用者指派至只搜尋的內容此篩選https://contoso.sharepoint.com/sites/doctors網站集合。篩選`"SiteContent_FileExtension -eq 'docx'"`會允許使用者指派此篩選器只搜尋的 Word 文件 (Word 2007 與更新版本)。<br/><br/>  如需可搜尋網站內容的清單，請參閱[編目及 managed 屬性在 SharePoint 中的概觀](https://go.microsoft.com/fwlink/p/?LinkId=331599)。屬性標示**是**在 * * Queryable * * 欄可用來建立網站內容篩選器。<br/> <br/> **重要：** 單一搜尋篩選器只能有一個篩選; 類型它不能包含信箱篩選和站台的篩選器。同樣地，它不能包含信箱篩選和信箱內容篩選器。不過，篩選器可以包含較複雜的查詢相同的類型。例如，`"Mailbox_CustomAttribute10 -eq 'FTE' -and Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"` <br/><br/> **重要：** 您必須建立搜尋權限篩選器來明確防止使用者在特定 Office 365 服務 （例如防止使用者搜尋任何 Exchange 信箱或任何 SharePoint 網站） 中搜尋的內容位置。換句話說，建立可讓使用者在組織中搜尋所有 SharePoint 網站的都搜尋權限篩選器不會防止使用者搜尋信箱。例如，若要允許 SharePoint 系統管理員只搜尋 SharePoint 網站，您必須建立建立防止搜尋信箱的篩選。同樣地，若要允許 Exchange 系統管理員只搜尋信箱，您必須建立建立篩選器，防止搜尋網站。           |
| _使用者_ <br/> |_使用者_參數會指定要取得其內容的搜尋套用此篩選器的使用者。識別使用者使用其別名或主要 SMTP 位址。您可以指定多個以逗號分隔值或您可以篩選指派給所有使用者使用的**所有**值。<br/> 您也可以使用_使用者_參數指定安全性&amp;規範中心角色群組。此屬性可讓您建立自訂角色群組，然後將指派該角色群組的搜尋權限篩選器。例如，假設您有自訂角色群組的多國美國子公司的 eDiscovery 管理員。您可用於此角色群組 （使用指定的角色群組的名稱屬性），然後使用_Filter_參數允許僅在美國要搜尋的信箱_使用者_參數。<br/> 使用此參數，無法指定通訊群組。  <br/> |
   

## <a name="examples-of-creating-search-permissions-filters"></a>建立範例搜尋權限篩選

以下是使用 **New-ComplianceSecurityFilter** Cmdlet 來建立搜尋權限篩選器的範例。 
  
本範例可讓使用者 annb@contoso.com 僅適用於加拿大中信箱的執行內容搜尋的所有動作。此篩選包含第三位數數字國碼加拿大自 ISO 3166-1。

```
New-ComplianceSecurityFilter -FilterName CountryFilter  -Users annb@contoso.com -Filters "Mailbox_CountryCode  -eq '124'" -Action All
```

此範例允許使用者 donh 和 suzanf 僅搜尋針對 CustomAttribute1 信箱屬性具有值「行銷」的信箱。

```
New-ComplianceSecurityFilter -FilterName MarketingFilter  -Users donh,suzanf -Filters "Mailbox_CustomAttribute1  -eq 'Marketing'" -Action Search
```
   
此範例允許「美國探索管理員」角色群組的成員僅針對美國的信箱執行所有內容搜尋動作。此篩選器包含根據 ISO 3166-1 的三位數數字美國國碼。
  
```
New-ComplianceSecurityFilter -FilterName USDiscoveryManagers  -Users "US Discovery Managers" -Filters "Mailbox_CountryCode  -eq '840'" -Action All
```

此範例會指派允許 eDiscovery 管理員角色群組的成員僅搜尋 Ottawa Users 通訊群組成員的信箱。 
  
```
$DG = Get-DistributionGroup "Ottawa Users"
```

```
New-ComplianceSecurityFilter -FilterName DGFilter  -Users eDiscoveryManager -Filters "Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'" -Action Search
```
此範例可防止任何使用者從 Executive Team 通訊群組成員的信箱刪除內容。

```
$DG = Get-DistributionGroup "Executive Team"
```

```
New-ComplianceSecurityFilter -FilterName NoExecutivesPreview  -Users all -Filters "Mailbox_MemberOfGroup -ne '$($DG.DistinguishedName)'" -Action Purge
```
   
本範例會允許在組織中的商務位置的 onedrive 搜尋的內容 OneDrive eDiscovery 管理員自訂角色群組的成員。

```
New-ComplianceSecurityFilter -FilterName OneDriveOnly  -Users "OneDrive eDiscovery Managers" -Filters "Site_Path -like 'https://contoso-my.sharepoint.com/personal*'" -Action Search
```
   
> [!NOTE]
> 若要限制使用者搜尋特定的網站，使用 [篩選器`Site_Path`、 前一個範例所示。使用`Site_Site`將無法運作。 
  
此範例會限制使用者只能對 2015 年期間傳送的電子郵件執行所有內容搜尋動作。

```
New-ComplianceSecurityFilter -FilterName EmailDateRestrictionFilter -Users donh@contoso.com -Filters "MailboxContent_Received -ge '01-01-2015' -and MailboxContent_Received -le '12-31-2015'" -Action All
```
   
類似於先前的範例，此範例會限制使用者對於在 2015 年進行最後變更的文件執行所有內容搜尋動作。

```
New-ComplianceSecurityFilter -FilterName DocumentDateRestrictionFilter -Users donh@contoso.com -Filters "SiteContent_LastModifiedTime -ge '01-01-2015' -and SiteContent_LastModifiedTime -le '12-31-2015'" -Action All
```
   
本範例會在組織中的任何信箱上執行內容搜尋動作防止"OneDrive 探索管理員 」 角色群組的成員。 

```
New-ComplianceSecurityFilter -FilterName NoEXO -Users "OneDrive Discovery Managers" -Filters "Mailbox_Alias -notlike '*'"  -Action All
```
  
## <a name="get-compliancesecurityfilter"></a>Get-ComplianceSecurityFilter

**取得 ComplianceSecurityFilter**用來傳回篩選清單的搜尋權限。使用_FilterName_參數傳回特定搜尋篩選的資訊。 
  
## <a name="set-compliancesecurityfilter"></a>設定 ComplianceSecurityFilter

**設定 ComplianceSecurityFilter**用來修改現有的搜尋權限篩選條件。唯一需要的參數是_FilterName_。 
  
|**參數**|**描述**|
|:-----|:-----|
| _動作_| _Action_參數會指定篩選條件套用至搜尋動作的類型。會在可能的內容搜尋動作：<br/><br/> **匯出**-filter 匯出搜尋結果時套用。  <br/> 預覽搜尋結果時套用**預覽**篩選。  <br/> **清除**-filter 清除搜尋結果時套用。  <br/> **搜尋**篩選條件套用時執行搜尋。  <br/> **所有**-filter 套用至所有搜尋動作。  <br/> |
| _FilterName_|_FilterName_參數會指定權限篩選器名稱。 |
| _篩選_| _篩選_參數會指定規範安全性篩選的搜尋準則。您可以建立篩選器的兩個不同的種類：<br/><br/>**信箱篩選**-這個類型的篩選器會指定可以搜尋指定的使用者 （_使用者_參數所指定） 的信箱。此類型語法是篩選的**Mailbox_** _MailboxPropertyName_，其中_MailboxPropertyName_會指定用來範圍可搜尋之信箱的信箱屬性。例如，信箱篩選`"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"`就 CustomAttribute10 屬性中允許使用者指派此篩選要只搜尋信箱包含值"OttawaUsers"。 任何支援的可篩選收件者屬性可以用於_MailboxPropertyName_屬性。如需支援屬性的清單，請參閱[Filterable properties for-RecipientFilter 參數](https://go.microsoft.com/fwlink/p/?LinkId=784903)。<br/><br/>**信箱內容篩選**-這種類型的篩選器會套用在可搜尋的內容。它會指定的使用者可以搜尋的信箱內容。此類型語法是篩選的**MailboxContent_** _SearchablePropertyName:value_，其中_SearchablePropertyName_會指定可以在內容搜尋中指定的關鍵字查詢語言 (KQL) 屬性。例如，信箱內容篩選器`MailboxContent_recipients:contoso.com`會允許使用者指派此篩選要只搜尋傳送至 contoso.com 網域中的收件者的郵件。 如需可搜尋的郵件內容的清單，請參閱 ＜[內容搜尋的關鍵字查詢](keyword-queries-and-search-conditions.md)。<br/><br/>**網站與網站內容篩選**有兩個 SharePoint 及 OneDrive for 商務網站相關的篩選器可用來指定哪些網站或網站內容可以搜尋指定的使用者： <br/><br/>- **Site_***SearchableSiteProperty* <br/>- **SiteContent**_*SearchableSiteProperty*<br/><br/>這些兩個篩選器可以互換 ；例如`"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"`和`"SiteContent_Path -like 'https://contoso.spoppe.com/sites/doctors*'"`會傳回相同的結果。為了協助您識別篩選器的運作，您可以使用，但是`Site_`指定網站相關的屬性 （例如網站 URL) 和`SiteContent_`指定與內容相關的屬性 （例如文件類型。例如，篩選`"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"`會允許使用者指派至只搜尋的內容此篩選https://contoso.spoppe.com/sites/doctors網站集合。篩選`"SiteContent_FileExtension -eq 'docx'"`會允許使用者指派此篩選器只搜尋的 Word 文件 (Word 2007 與更新版本)。<br/><br/>如需可搜尋網站內容的清單，請參閱[編目及 managed 屬性在 SharePoint 中的概觀](https://go.microsoft.com/fwlink/p/?LinkId=331599)。標示 [**是]** **設定為可查詢**] 欄中的屬性可用來建立網站內容篩選器。<br/><br/> **重要：** 單一搜尋篩選器只能有一個篩選; 類型它不能包含信箱篩選和站台的篩選器。同樣地，它不能包含信箱篩選和信箱內容篩選器。不過，篩選器可以包含較複雜的查詢相同的類型。例如，`"Mailbox_CustomAttribute10 -eq 'FTE' -and Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"`          |
| _使用者_|_使用者_參數會指定要取得其內容的搜尋套用此篩選器的使用者。由於這是多重值屬性，因此使用此參數指定使用者群組會覆寫現有的使用者清單。請參閱下列語法新增和移除所選的使用者的範例。<br/><br/>您也可以使用_使用者_參數指定安全性&amp;規範中心角色群組。此屬性可讓您建立自訂角色群組，然後將指派該角色群組的搜尋權限篩選器。例如，假設您有自訂角色群組的多國美國子公司的 eDiscovery 管理員。您可用於此角色群組 （使用指定的角色群組的名稱屬性），然後使用_Filter_參數允許僅在美國要搜尋的信箱_使用者_參數。<br/><br/>使用此參數，無法指定通訊群組。 |

## <a name="examples-of-changing-search-permissions-filters"></a>變更搜尋權限篩選的範例

下列範例顯示如何使用**Get ComplianceSecurityFilter**和**設定 ComplianceSecurityFilter**指令程式來新增或移除現有的清單篩選指派給使用者的使用者。當您新增或移除篩選器的使用者時，指定使用者使用其 SMTP 地址。 
  
此範例會將使用者新增至篩選器。

```
$filterusers = Get-ComplianceSecurityFilter -FilterName OttawaUsersFilter
```
```
$filterusers.users.add("pilarp@contoso.com")
```

```
Set-ComplianceSecurityFilter -FilterName OttawaUsersFilter -Users $filterusers.users
```
   
此範例會從篩選器移除使用者。

```
$filterusers = Get-ComplianceSecurityFilter -FilterName OttawaUsersFilter
```

```
$filterusers.users.remove("annb@contoso.com")
```

```
Set-ComplianceSecurityFilter -FilterName OttawaUsersFilter -Users $filterusers.users
```
  
## <a name="remove-compliancesecurityfilter"></a>移除 ComplianceSecurityFilter

**移除 ComplianceSecurityFilter**用來刪除的搜尋篩選器。使用_FilterName_參數指定您想要刪除的篩選。 
  
## <a name="more-information"></a>詳細資訊

- **方式的搜尋篩選工作的權限？** 權限篩選新增至搜尋查詢時執行內容的搜尋。搜尋查詢基本上被加入權限篩選所**AND**布林運算子。例如，假設您有權限允許的篩選器 Bob 工作者通訊群組成員的信箱上執行搜尋的所有動作。然後 Bob 的搜尋查詢與組織中所有信箱上執行內容的搜尋`sender:jerry@adatum.com`。由於權限篩選器和搜尋查詢以邏輯方式來使用**AND**運算子結合，搜尋會傳回由 jerry@adatum.com 傳送到任何工作者通訊群組成員的任何訊息。 
    
- **如果您有多個搜尋權限篩選會發生什麼事？** 在內容搜尋查詢時，**或**布林運算子來結合多個權限篩選。因此，如果任何篩選條件為真會傳回結果。在內容搜尋] （**或**運算元來結合） 的所有篩選再使用搜尋查詢來都結合**AND**運算子。讓我們看前一個範例中，其中的搜尋篩選器可讓 Bob 僅搜尋之信箱的工作者通訊群組的成員。然後我們建立其他篩選禁止 Bob 搜尋費歐的信箱 ("Mailbox_Alias-ne '費歐'")。與我們也會假設費歐是工作者群組的成員。Bob 執行時內容搜尋 （從先前的範例） 在組織中的所有信箱搜尋結果會傳回費歐的信箱即使套用篩選器來防止 Bob 搜尋費歐的信箱。這是因為第一個篩選，可讓 Bob 工作者群組搜尋，則為 true。且 Bob 因為費歐工作者群組的成員，可以搜尋費歐的信箱。 
    
- **的搜尋篩選工作不在作用中信箱的權限吗？** 是，您可以使用信箱和信箱內容篩選器來限制誰可以在組織中搜尋不在作用中的信箱。像一般信箱非使用中的信箱有與收件者屬性是用來建立權限篩選設定。若有需要，您可以使用**Get-mailbox InactiveMailboxOnly**命令來顯示不在作用中信箱的屬性。如需詳細資訊，請參閱[建立及管理 Office 365 中的非使用中信箱](create-and-manage-inactive-mailboxes.md)。
    
- **的搜尋篩選公司的公用資料夾的權限吗？**[否]。先前所述，搜尋篩選的權限無法用來限制可以在 Exchange 搜尋公用資料夾。例如，在公用資料夾位置的項目無法由權限篩選排除從搜尋結果。 
    
- **並允許使用者在搜尋內容的所有位置中特定的服務也禁止它們在不同的服務中搜尋的內容位置吗？**[否]。如先前所述，您必須建立搜尋權限篩選器來明確防止使用者在特定 Office 365 服務 （例如防止使用者搜尋任何 Exchange 信箱或任何 SharePoint 網站） 中搜尋的內容位置。換句話說，建立可讓使用者在組織中搜尋所有 SharePoint 網站的都搜尋權限篩選器不會防止使用者搜尋信箱。例如，若要允許 SharePoint 系統管理員只搜尋 SharePoint 網站，您必須建立建立防止搜尋信箱的篩選。同樣地，若要允許 Exchange 系統管理員只搜尋信箱，您必須建立建立篩選器，防止搜尋網站。
