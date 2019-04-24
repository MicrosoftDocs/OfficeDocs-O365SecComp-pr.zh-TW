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
description: 使用內容搜尋篩選，以讓 Office 365 組織中搜尋的信箱和站台子集 eDiscovery 管理員的權限。
ms.openlocfilehash: 1e12a125390deae60cc8762318b3b6bcf0e6533f
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32261251"
---
# <a name="configure-permissions-filtering-for-content-search"></a>設定內容搜尋的權限篩選

您可以使用搜尋篩選，以讓 Office 365 組織中搜尋的信箱和站台子集 eDiscovery 管理員的權限。 您也可以使用權限篩選，讓相同的 eDiscovery 管理員僅搜尋符合特定搜尋準則的信箱或網站內容。 例如，您可以讓 eDiscovery 管理員只在特定位置或部門中搜尋使用者的信箱。 您可以藉由建立篩選器來完成這個動作，該篩選器使用支援的收件者篩選器以限制可搜尋的信箱。 您也可以建立篩選器，指定可搜尋的信箱內容。 可以藉由建立篩選器來完成這個動作，該篩選器會使用可搜尋的郵件屬性。 同樣地，您可能會讓電子文件探索管理員只搜尋組織中的 [特定的 SharePoint 網站。 您可以藉由建立篩選器來完成這個動作，該篩選器會限制可搜尋的網站。 您也可以建立篩選器，指定可搜尋的網站內容。 可以藉由建立篩選器來完成這個動作，該篩選器會使用可搜尋的網站屬性。

您也可以使用篩選，以建立邏輯界限 （稱為 「*合規性界限*） 內的 Office 365 組織，以控制 （例如信箱、 SharePoint 網站與 OneDrive 帳戶） 的使用者內容位置的搜尋權限，可以搜尋特定的 eDiscovery 管理員。 如需詳細資訊，請參閱 <<c0>設定 Office 365 中電子文件探索調查的合規性界限。
  
搜尋權限篩選受到安全性 & 合規性中心中的內容搜尋功能。 這些四個 cmdlet 可讓您設定及管理搜尋 permisisons 篩選器：
  
[新 ComplianceSecurityFilter](#new-compliancesecurityfilter)

[取得 ComplianceSecurityFilter](#get-compliancesecurityfilter)

[Set-compliancesecurityfilter](#set-compliancesecurityfilter)

[Remove-compliancesecurityfilter](#remove-compliancesecurityfilter)

## <a name="before-you-begin"></a>開始之前

- 若要執行的合規性安全性篩選器指令程式，您必須是安全性 & 合規性中心中 「 組織管理角色群組的成員。 如需詳細資訊，請參閱 <<c0>安全性 &amp; 合規性中心中的權限。
    
- 您必須將 Windows PowerShell 連線到這兩種安全性 & 合規性中心以及 Exchange Online 的組織使用合規性安全性篩選器指令程式。 這是必要的因為這些指令程式會要求存取信箱內容，也就是為何您必須連線至 Exchange Online。 請參閱下一節中的步驟。 
    
- 請參閱[More information](#more-information)一節以取得搜尋權限篩選器的詳細資訊。 
    
- 搜尋權限篩選是適用於非使用中信箱，這表示您可以使用信箱和信箱內容篩選以限制可以搜尋非使用中的信箱。 請參閱權限篩選和非使用中信箱的其他資訊[的詳細資訊](#more-information)一節。 
    
-  搜尋權限篩選不能用來限制誰可以在 Exchange 搜尋公用資料夾。 
    
- 沒有任何限制可以在組織中建立搜尋權限篩選器的數目。 不過，有 100 個以上的搜尋權限篩選器時，會影響搜尋效能。 若要在組織中的搜尋權限篩選器數目保持盡可能的小，建立結合的 Exchange、 SharePoint 和 OneDrive 的規則，盡可能在單一篩選中的篩選器。
    
## <a name="connect-to-the-security--compliance-center-and-exchange-online-in-a-single-remote-powershell-session"></a>在單一遠端 PowerShell 工作階段中連接至安全 & 與規範中心和 Exchange Online

1. 使用.ps1 檔名尾碼，顯示下列文字儲存到 Windows PowerShell 指令碼檔案。 例如，您可以儲存至名為 ConnectEXO-CC.ps1 的檔案。
    
    ```
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -AllowClobber -DisableNameChecking
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. 在您的本機電腦上開啟 Windows PowerShell 移至您在上一個步驟中建立的指令碼所在的資料夾，然後執行指令碼。例如：
    
    ```
    .\ConnectEXO-CC.ps1
    ```
 
如何知道這是否正常運作？ 執行指令碼之後，從安全性 & 規範中心和 Exchange Online 指令程式會匯入您的本機 Windows PowerShell 工作階段。 如果您未收到任何錯誤，便已順利連線。 快速測試是執行安全性 & 合規性中心 cmdlet — 例如，**安裝 UnifiedCompliancePrerequisite** — 和 Exchange Online 指令程式，例如**Get-mailbox**。 
  
如果您收到錯誤，請檢查下列需求：
  
- 密碼錯誤是常見的問題。再次執行這兩個步驟，並密切注意您在步驟 1 中輸入的使用者名稱和密碼。
    
- 確認您的帳戶具有存取安全性 & 合規性中心的權限。 如需詳細資訊，請參閱[讓使用者能夠存取至安全性 & 合規性中心](grant-access-to-the-security-and-compliance-center.md)。
    
- 為防止拒絕服務 (DoS) 攻擊，您正在限制為三個遠端 PowerShell 連線到安全性 & 合規性中心。
    
- 您必須設定 Windows PowerShell 才能執行指令碼。您只需在電腦上設定此設定一次，而不用在每次連線時進行設定。若要讓 Windows PowerShell 執行經過簽署的指令碼，請在提高權限的 Windows PowerShell 視窗 (藉由選取 **[以管理員身分執行]** 開啟的 Windows PowerShell 視窗) 中執行下列命令。

    ```
    Set-ExecutionPolicy RemoteSigned
    ```
- 本機電腦與 Office 365 之間必須開啟 TCP 連接埠 80 流量。 該連接埠可能已開啟，但必須考量您的組織是否有限制性網際網路存取原則。
    

  
## <a name="new-compliancesecurityfilter"></a>新 ComplianceSecurityFilter
<a name="New"> </a>

**New-compliancesecurityfilter**用來建立新的搜尋權限篩選器。 下表說明此 cmdlet 的參數。 建立符合性安全性篩選器需要所有參數。 
  
|**參數**|**描述**|
|:-----|:-----|
| _Action_ <br/> | _Action_參數會指定該類型的篩選套用到的搜尋動作。 可能的內容搜尋動作是︰  <br/><br/> 匯出搜尋結果時，會套用**匯出**的篩選器。  <br/> 預覽搜尋結果時，會套用**預覽**篩選。  <br/> 清除搜尋結果時，會套用**清除**-篩選器。  <br/> 執行搜尋時，會套用**搜尋**篩選器。  <br/> **所有**的篩選器會套用到所有的搜尋動作。  <br/> |
| _FilterName_ <br/> |_FilterName_參數會指定權限篩選器名稱。 此名稱是用來在使用 **Get-ComplianceSecurityFilter**、**Set-ComplianceSecurityFilter,** 和 **Remove-ComplianceSecurityFilter** Cmdlet 時識別篩選器。  <br/> |
| _篩選_ <br/> | _篩選_參數會指定的法規安全性篩選的搜尋準則。 您可以建立三個不同類型的篩選器：  <br/><br/> **信箱篩選**-這種類型的篩選器指定 （_使用者_參數所指定） 分派的使用者可以搜尋的信箱。 這種類型的篩選器語法是**Mailbox_** _MailboxPropertyName_，其中_MailboxPropertyName_會指定用來範圍可以搜尋的信箱的信箱屬性。 例如，信箱篩選`"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"`會在 CustomAttribute10 屬性中允許使用者指派給此篩選只搜尋具有值的信箱 」 OttawaUsers 」。  <br/>  任何支援的可篩選收件者屬性可以用於_MailboxPropertyName_屬性。 如需支援的屬性的清單，請參閱[-RecipientFilter 參數的可篩選內容](https://go.microsoft.com/fwlink/p/?LinkId=784903)。  <br/><br/> **信箱內容篩選**-這種類型的篩選器會套用至可搜尋的內容。 它會指定受指派的使用者可以搜尋的信箱內容。 這種類型的篩選器語法是**MailboxContent_** _SearchablePropertyName:value_，其中_SearchablePropertyName_會指定可以在內容搜尋中指定的關鍵字查詢語言 (KQL) 屬性。 例如，信箱內容篩選器`MailboxContent_recipients:contoso.com`會允許使用者指派給此篩選只搜尋的郵件傳送至 contoso.com 網域中的收件者。  <br/>  如需可搜尋郵件屬性的清單，請參閱[關鍵字查詢和搜尋條件的內容搜尋](keyword-queries-and-search-conditions.md)。  <br/><br/> **網站與網站內容篩選**-有兩個 SharePoint 和 OneDrive for Business 網站相關篩選器，您可指定哪些網站或網站內容被指派的使用者可以搜尋：  <br/><br/> - **Site_**_SearchableSiteProperty_ <br/> - **SiteContent_**_SearchableSiteProperty_ <br/><br/>  這些兩個篩選器是可以互換;例如`"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"`和`"SiteContent_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"`會傳回相同的結果。 若要協助您找出篩選器的運作，您可以使用，但是`Site_`若要指定網站的相關內容 （例如網站的 URL) 和`SiteContent_`來指定內容的相關內容 （例如文件類型。 例如，篩選`"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"`會允許使用者指派至只搜尋中的內容此篩選https://contoso.sharepoint.com/sites/doctors網站集合。 篩選`"SiteContent_FileExtension -eq 'docx'"`會允許使用者指派給此篩選只搜尋的 Word 文件 (Word 2007 及更新版本)。  <br/><br/>  如需可搜尋的網站內容的清單，請參閱 < <b0>Overview of 編目及 managed properties in SharePoint</b0>。 屬性標記為使用中的 [ **]** * * 設定為可查詢 * * 欄可以用來建立網站內容篩選器。  <br/> <br/> **重要：** 單一搜尋篩選只能有一種類型的篩選器。它不能包含信箱篩選和站台的篩選器。同樣地，它不能包含信箱篩選和信箱內容篩選器。 不過，篩選器可以包含相同類型的較複雜查詢。 例如，  `"Mailbox_CustomAttribute10 -eq 'FTE' -and Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"` <br/><br/> **重要：** 您必須建立搜尋權限篩選器，明確防止使用者在特定的 Office 365 服務 （例如，使得使用者無法搜尋的任何 Exchange 信箱或任何 SharePoint 網站） 中搜尋內容位置。 也就是說，建立可讓使用者搜尋組織中的所有 SharePoint 網站的都搜尋權限篩選器並不會防止使用者搜尋信箱。 例如，若要讓 SharePoint 系統管理員只搜尋 [SharePoint 網站，您必須建立建立篩選器，防止搜尋信箱。 同樣地，以允許 Exchange 系統管理員只搜尋信箱，您必須建立建立可防止搜尋網站的篩選。           |
| _Users_ <br/> |_使用者_參數會指定要取得此篩選器套用至其內容搜尋的使用者。 依其別名或主要 SMTP 位址識別使用者。 您可以指定以逗號分隔的多個值，或者您也可以使用值 **All** 將篩選器指派給所有使用者。  <br/> 您也可以使用_使用者_參數來指定安全性 & 合規性中心角色群組。 這可讓您建立自訂角色群組，然後為該角色群組指派搜尋權限篩選器。 例如，假設您有多國公司的美國子公司的 eDiscovery 管理員的自訂角色群組。 您可以使用_使用者_參數 （藉由使用角色群組的 Name 屬性） 指定這個角色群組，並再使用_Filter_參數，以允許只在美國要搜尋的信箱。  <br/> 使用此參數，無法指定通訊群組。  <br/> |
   

## <a name="examples-of-creating-search-permissions-filters"></a>建立搜尋權限篩選器的範例

以下是使用 **New-ComplianceSecurityFilter** Cmdlet 來建立搜尋權限篩選器的範例。 
  
此範例允許使用者 annb@contoso.com 僅適用於信箱加拿大執行所有內容搜尋動作。 此篩選器包含根據 ISO 3166-1 的三位數數字加拿大國碼。

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
   
此範例會允許在 OneDrive 中的組織中的商務位置只搜尋的內容 OneDrive eDiscovery Managers 自訂角色群組的成員。

```
New-ComplianceSecurityFilter -FilterName OneDriveOnly  -Users "OneDrive eDiscovery Managers" -Filters "Site_Path -like 'https://contoso-my.sharepoint.com/personal*'" -Action Search
```
   
> [!NOTE]
> 若要限制使用者搜尋特定的網站，使用 [篩選器`Site_Path`、 上述範例所示。 使用`Site_Site`將無法運作。 
  
此範例會限制使用者只能對 2015 年期間傳送的電子郵件執行所有內容搜尋動作。

```
New-ComplianceSecurityFilter -FilterName EmailDateRestrictionFilter -Users donh@contoso.com -Filters "MailboxContent_Received -ge '01-01-2015' -and MailboxContent_Received -le '12-31-2015'" -Action All
```
   
類似於先前的範例，此範例會限制使用者對於在 2015 年進行最後變更的文件執行所有內容搜尋動作。

```
New-ComplianceSecurityFilter -FilterName DocumentDateRestrictionFilter -Users donh@contoso.com -Filters "SiteContent_LastModifiedTime -ge '01-01-2015' -and SiteContent_LastModifiedTime -le '12-31-2015'" -Action All
```
   
本範例會防止在組織中任何信箱上執行內容搜尋動作 」 OneDrive 探索管理員 」 角色群組的成員。 

```
New-ComplianceSecurityFilter -FilterName NoEXO -Users "OneDrive Discovery Managers" -Filters "Mailbox_Alias -notlike '*'"  -Action All
```
  
## <a name="get-compliancesecurityfilter"></a>取得 ComplianceSecurityFilter

**取得 ComplianceSecurityFilter**用來傳回搜尋權限篩選器的清單。 使用_FilterName_參數傳回特定的搜尋篩選器的資訊。 
  
## <a name="set-compliancesecurityfilter"></a>Set-compliancesecurityfilter

**Set-compliancesecurityfilter**用來修改現有的搜尋權限篩選器。 唯一必要的參數是_FilterName_。 
  
|**參數**|**描述**|
|:-----|:-----|
| _Action_| _Action_參數會指定該類型的篩選套用到的搜尋動作。 可能的內容搜尋動作是︰ <br/><br/> 匯出搜尋結果時，會套用**匯出**的篩選器。  <br/> 預覽搜尋結果時，會套用**預覽**篩選。  <br/> 清除搜尋結果時，會套用**清除**-篩選器。  <br/> 執行搜尋時，會套用**搜尋**篩選器。  <br/> **所有**的篩選器會套用到所有的搜尋動作。  <br/> |
| _FilterName_|_FilterName_參數會指定權限篩選器名稱。 |
| _篩選_| _篩選_參數會指定的法規安全性篩選的搜尋準則。 您可以建立兩個不同類型的篩選器： <br/><br/>**信箱篩選**-這種類型的篩選器指定 （_使用者_參數所指定） 分派的使用者可以搜尋的信箱。 這種類型的篩選器語法是**Mailbox_** _MailboxPropertyName_，其中_MailboxPropertyName_會指定用來範圍可以搜尋的信箱的信箱屬性。 例如，信箱篩選`"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"`會在 CustomAttribute10 屬性中允許使用者指派給此篩選只搜尋具有值的信箱 」 OttawaUsers 」。  任何支援的可篩選收件者屬性可以用於_MailboxPropertyName_屬性。 如需支援的屬性的清單，請參閱[-RecipientFilter 參數的可篩選內容](https://go.microsoft.com/fwlink/p/?LinkId=784903)。 <br/><br/>**信箱內容篩選**-這種類型的篩選器會套用至可搜尋的內容。 它會指定受指派的使用者可以搜尋的信箱內容。 這種類型的篩選器語法是**MailboxContent_** _SearchablePropertyName:value_，其中_SearchablePropertyName_會指定可以在內容搜尋中指定的關鍵字查詢語言 (KQL) 屬性。 例如，信箱內容篩選器`MailboxContent_recipients:contoso.com`會允許使用者指派給此篩選只搜尋的郵件傳送至 contoso.com 網域中的收件者。  如需可搜尋的郵件內容清單，請參閱[Keyword queries for Content Search](keyword-queries-and-search-conditions.md)。 <br/><br/>**網站與網站內容篩選**有兩個 SharePoint 和 OneDrive for Business 網站相關篩選器，您可指定哪些網站或網站內容被指派的使用者可以搜尋： <br/><br/>- **Site_***SearchableSiteProperty* <br/>- **SiteContent**_*SearchableSiteProperty*<br/><br/>這些兩個篩選器是可以互換;例如`"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"`和`"SiteContent_Path -like 'https://contoso.spoppe.com/sites/doctors*'"`會傳回相同的結果。 若要協助您找出篩選器的運作，您可以使用，但是`Site_`若要指定網站的相關內容 （例如網站的 URL) 和`SiteContent_`來指定內容的相關內容 （例如文件類型。 例如，篩選`"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"`會允許使用者指派至只搜尋中的內容此篩選https://contoso.spoppe.com/sites/doctors網站集合。 篩選`"SiteContent_FileExtension -eq 'docx'"`會允許使用者指派給此篩選只搜尋的 Word 文件 (Word 2007 及更新版本)。  <br/><br/>如需可搜尋的網站內容的清單，請參閱 < <b0>Overview of 編目及 managed properties in SharePoint</b0>。 標示為具有 [**是]** **設定為可查詢**] 欄中的屬性可用來建立網站內容篩選器。 <br/><br/> **重要：** 單一搜尋篩選只能有一種類型的篩選器。它不能包含信箱篩選和站台的篩選器。同樣地，它不能包含信箱篩選和信箱內容篩選器。 不過，篩選器可以包含相同類型的較複雜查詢。 例如，  `"Mailbox_CustomAttribute10 -eq 'FTE' -and Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"`          |
| _Users_|_使用者_參數會指定要取得此篩選器套用至其內容搜尋的使用者。 由於這是多重值屬性，使用此參數指定使用者或使用者群組將會覆寫現有的使用者清單。 請參閱下列範例以了解新增和移除選取的使用者的語法。 <br/><br/>您也可以使用_使用者_參數來指定安全性 & 合規性中心角色群組。 這可讓您建立自訂角色群組，然後為該角色群組指派搜尋權限篩選器。 例如，假設您有多國公司的美國子公司的 eDiscovery 管理員的自訂角色群組。 您可以使用_使用者_參數 （藉由使用角色群組的 Name 屬性） 指定這個角色群組，並再使用_Filter_參數，以允許只在美國要搜尋的信箱。 <br/><br/>使用此參數，無法指定通訊群組。 |

## <a name="examples-of-changing-search-permissions-filters"></a>變更搜尋的權限篩選器的範例

這些範例顯示如何使用**Get-ComplianceSecurityFilter**和**Set-compliancesecurityfilter** cmdlet 來新增或移除現有的清單篩選會指派給使用者的使用者。 當您新增或移除篩選器的使用者時，使用其 SMTP 位址指定使用者。 
  
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
  
## <a name="remove-compliancesecurityfilter"></a>Remove-compliancesecurityfilter

**Remove-compliancesecurityfilter**用來刪除搜尋篩選器。 使用_FilterName_參數來指定您想要刪除的篩選器。 
  
## <a name="more-information"></a>其他資訊

- **搜尋權限篩選如何運作？** 當執行內容搜尋時，權限篩選器會新增至搜尋查詢。 搜尋查詢基本上被加入權限篩選器由**與**布林運算子。 例如，假設您的權限篩選器，允許 Bob 工作者通訊群組成員的信箱上執行所有的搜尋動作。 然後 Bob 在搜尋查詢與組織中所有信箱上執行內容搜尋`sender:jerry@adatum.com`。 因為權限篩選器和搜尋查詢邏輯上是透過 **AND** 運算子結合，搜尋會傳回由 jerry@adatum.com 傳送給 Workers 通訊群組任何成員的郵件。 
    
- **如果您有多個搜尋權限篩選器會發生什麼情況？** 在內容搜尋查詢中，多個權限篩選器會藉由 **OR** 布林運算子合併。 因此任何篩選器為 true，則會傳回結果。 在內容搜尋中，所有篩選器 (由 **OR** 運算子合併) 隨後會與 **AND** 運算子的搜尋查詢合併。 讓我們以先前的範例為例，搜尋篩選器允許 Bob 只搜尋 Workers 通訊群組成員的信箱。 然後我們建立另一個篩選器，防止 Bob 搜尋 Phil 的信箱 ("Mailbox_Alias -ne 'Phil'")。 同時假設 Phil 是 Workers 群組的成員。 當 Bob 在組織中所有信箱上 （從先前的範例） 執行內容搜尋時，搜尋結果將傳回費歐的信箱，即使您套用篩選，以防止 Bob 搜尋費歐的信箱。 原因是允許 Bob 搜尋 Workers 群組的第一個篩選器為 true。 且由於 Phil 是 Workers 群組的成員，因此 Bob 可搜尋 Phil 的信箱。 
    
- **並會搜尋篩選工時非使用中信箱的權限？** 是，您可以使用信箱和信箱內容篩選器來限制誰可以在組織中搜尋非使用中信箱。 像是一般信箱，非使用中的信箱都必須以用來建立權限篩選器的收件者屬性來設定。 如有需要，您可以使用**Get-mailbox InactiveMailboxOnly**命令來顯示非使用中信箱的屬性。 如需詳細資訊，請參閱[建立及管理 Office 365 中的非使用中信箱](create-and-manage-inactive-mailboxes.md)。
    
- **並會搜尋篩選工時公用資料夾的權限？** 否。 為先前所述，搜尋篩選的權限無法用來限制可以在 Exchange 搜尋公用資料夾。 例如，公用資料夾的位置中的項目無法從搜尋結果排除，由權限篩選器。 
    
- **允許使用者搜尋特定的服務中的所有內容位置也無法將它們從不同的服務中的搜尋內容位置？** 否。 如先前所述，您必須建立搜尋權限篩選器，明確防止使用者在特定的 Office 365 服務 （例如，使得使用者無法搜尋的任何 Exchange 信箱或任何 SharePoint 網站） 中搜尋內容位置。 也就是說，建立可讓使用者搜尋組織中的所有 SharePoint 網站的都搜尋權限篩選器並不會防止使用者搜尋信箱。 例如，若要讓 SharePoint 系統管理員只搜尋 [SharePoint 網站，您必須建立建立篩選器，防止搜尋信箱。 同樣地，以允許 Exchange 系統管理員只搜尋信箱，您必須建立建立可防止搜尋網站的篩選。
