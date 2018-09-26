---
title: 將 eDiscovery 權限指派至 OneDrive for Business 網站
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/27/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
ms.assetid: 422858ff-917b-46d4-9e5b-3397f60eee4d
description: 您可以使用 SharePoint Online 中的 eDiscovery 中心來搜尋特定關鍵字、 敏感資訊及其他搜尋條件的組織中所有 OneDrive for Business 的網站。在組織中的每位使用者為其 OneDrive for Business 網站，位於名為網站集合的擁有人https://domain-my.sharepoint.com。根據預設，Office 365 全域管理員或規範管理員無法使用 SharePoint Online 中的 eDiscovery 中心搜尋任何 OneDrive for Business 的網站。若要搜尋 OneDrive for Business 網站、 系統管理員或規範經理必須是該 OneDrive for Business 網站的網站集合管理員。
ms.openlocfilehash: 61f068a03bcce599d9f1b7eb62d7b317b7feab68
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038086"
---
# <a name="assign-ediscovery-permissions-to-onedrive-for-business-sites"></a>將 eDiscovery 權限指派至 OneDrive for Business 網站

您可以使用 SharePoint Online 中的 eDiscovery 中心來搜尋特定關鍵字、 敏感資訊及其他搜尋條件的組織中所有 OneDrive for Business 的網站。在組織中的每位使用者為其 OneDrive for Business 網站，位於名為網站集合的擁有人https://domain-my.sharepoint.com。根據預設，Office 365 全域管理員或規範管理員無法使用 SharePoint Online 中的 eDiscovery 中心搜尋任何 OneDrive for Business 的網站。若要搜尋 OneDrive for Business 網站、 系統管理員或規範經理必須是該 OneDrive for Business 網站的網站集合管理員。 
  
本文會引導您完成讓系統管理員或法務經理每一個 OneDrive for Business 網站的網站集合管理員在組織中的步驟。 
  
請參閱如需本文，包括修改在步驟 3 中移除使用者為網站集合管理員的 OneDrive for Business 的網站中的指令碼中使用指令碼的提示[的詳細資訊](#more-information)] 區段。 
  
## <a name="before-you-begin"></a>開始之前

- 安裝 SharePoint Online 管理命令介面。資訊，請參閱[設定 SharePoint Online 管理命令介面 Windows PowerShell 環境](https://go.microsoft.com/fwlink/p/?LinkID=286318)。
    
- 步驟 3 中您想要為網站集合管理員的使用者指派給您組織中的商務網站的任何 OneDrive 每的次執行指令碼。 
    
    > [!IMPORTANT]
    > 系統管理員或法務 manager 身為網站集合管理員的 OneDrive for Business 網站可以開啟使用者的 OneDrive for Business 文件庫和執行為擁有者相同的工作。請務必控制及監視尚未指派之 eDiscovery 的權限至 OneDrive 針對在組織中的商務網站。 
  
- 本文中提供的指令碼範例不支援任何 Microsoft 標準支援程式或服務底下。指令碼範例會為 IS 提供不含任何類型的瑕疵擔保。Microsoft 進一步不作所有默示之的擔保包括但不限於任何默示擔保售或適合特定用途。與您保持承擔使用或效能的範例指令碼及文件的風險。事件無法在 Microsoft、 其作者，或其他參與建立、 實際執行或指令碼傳遞的任何人對於而概之任何損害皆不 （包括但不限於，遺漏的商務利潤、 業務中斷、 遺失的損害商務資訊或其他金錢遺失） 引起的使用或無法使用的範例指令碼或文件即使 Microsoft 已被告知這類損害的可能性。
    
## <a name="step-1-collect-a-list-of-all-onedrive-for-business-sites"></a>步驟 1： 收集所有 OneDrive for Business 的網站的清單

第一個步驟是在組織中建立的所有 OneDrive for Business 的網站清單。指示，請參閱[建立您的組織中的所有 OneDrive 位置的清單](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a)。本文中的此指令碼會建立包含的所有 OneDrive 網站清單的文字檔案。您在步驟 3 中執行的指令碼會將指定的使用者作為網站集合管理員指派給每個 OneDrive for Business 網站會在此步驟中建立的文字檔案中所列。顯示下列文字會提供範例應該用來格式化此檔案中的網站清單的方式。視您可以移除此檔案的網站。

```
/personal/annb_contoso_onmicrosoft_com/
/personal/carolt_contoso_onmicrosoft_com/
/personal/esterv_contoso_onmicrosoft_com/
/personal/hollyh_contoso_onmicrosoft_com/
/personal/jeffl_contoso_onmicrosoft_com/
/personal/joeh_contoso_onmicrosoft_com/
/personal/kaia_contoso_onmicrosoft_com/
```

## <a name="step-2-connect-sharepoint-online-management-shell-to-your-organization"></a>步驟 2： 連線至組織的 SharePoint Online 管理命令介面

1. 在您的本機電腦上，開啟 SharePoint Online 管理命令介面，執行以下命令：

    ```
    $credentials = Get-Credential
    ```

2. 在 **[Windows PowerShell 認證要求]** 對話方塊中，輸入 Office 365 全域管理員帳戶的使用者名稱和密碼，然後按一下 **[確定]**。
    
3. 執行下列程式碼將命令介面連線至您的 SharePoint Online 組織：
    
    ```
    Connect-SPOService -Url https://<your organization name>-admin.sharepoint.com -credential $credentials
    ```
   
4. 若要確認您已連線至 SharePoint Online 組織，執行下列命令以取得貴組織中所有網站的清單：
    
    ```
    Get-SPOSite
    ```

## <a name="step-3-assign-a-user-as-a-site-collection-administrator-to-onedrive-for-business-sites"></a>步驟 3：指派使用者為 OneDrive for Business 網站的網站集合管理員

下一步是執行指令碼會將指定的使用者指派為中每一個 OneDrive for Business 網站在組織中的網站集合管理員。此指令碼使用您在步驟 1 中建立的商務網站 OneDrive 的清單。先前所述，您必須執行此指令碼每次您要為網站集合管理員指派使用者至 OneDrive for Business 的網站。
  
1. 儲存下列文字至文字檔。例如，您可以儲存至名為 OD4BAssignSCA.txt 的檔案。

    ```
    # Start logging, so if this script fails, you can look at the last successful change,
    # remove any OneDrive for Business paths that worked it from the input file, and then rerun the script.

    Start-Transcript

    # URL for your organization's SPO admin service

    $AdminURI = "https://<your organization name>-admin.sharepoint.com"

    # User account for an Office 365 global admin in your organization

    $AdminAccount = "<global admin account>"

    # Compliance manager to be made site collection admin on each MySite

    $eDiscoveryUser = "<eDiscovery user account>"

    # URL for your tenant's MySite domain

    $MySitePrefix = "https://<your organization name>-my.sharepoint.com"

    # Where should we read the list of MySites?
    # This file should contain partial MySite paths formatted as follows, one per line; for example
    # /personal/junminh_contoso_onmicrosoft_com/

    $MySiteListFile = 'C:\Users\<youralias>\Desktop\ListOfMysites.txt'

    # Begin by connecting to the service
    Connect-SPOService -Url $AdminURI -Credential $AdminAccount

    # Make a reader for our list of MySites

    $reader = [System.IO.File]::OpenText($MySiteListFile)

    try {
      for(;;) {

    # Read a line
          $line = $reader.ReadLine()
    # Stop if it doesn't exist
          if ($line -eq $null) { break }

    # Turn the line into a complete SharePoint site path by merging $MySitePrefix
    # Formatted like this: "https://contoso-my.sharepoint.com"
    # ...with each partial MySite path in the file, formatted like this:
    # "/personal/junminh_contoso_onmicrosoft_com/"

          $fullsitepath = "$MySitePrefix$line"

    Write-Host "Operating on $fullsitepath "

    # We need to remove the last "/" to work around an issue.
    # "/personal/junminh_contoso_onmicrosoft_com/"
    # becomes "/personal/junminh_contoso_onmicrosoft_com"

    $fullsitepath = $fullsitepath.trimend("/")

    # Make the specified eDiscovery user a site collection admin on the OneDrive for Business site
    Write-Host "Making $eDiscoveryUser a Site Collection Admin"
    Set-SPOUser -Site $fullsitepath -LoginName $eDiscoveryUser -IsSiteCollectionAdmin $true
      }
    }
    finally {
      $reader.Close()
    }
    Write-Host "Done!"
    Stop-Transcript
    Write-Host "Log written."
    ```

2. 編輯下列變數中的指令碼檔案開頭並使用專屬於貴組織的資訊。下列範例假設您組織的網域名稱是 contoso.onmicrosoft.com。請務必環繞含有雙引號變數的值 ("")。
    
    - **$AdminURI** -這會指定之 URI 的 SharePoint Online 的管理服務，例如`"https://contoso-admin.sharepoint.com"`。
    
    - **$AdminAccount** -這會指定全域管理員帳戶的 Office 365 組織，例如`"admin@contoso.onmicrosoft.com"`。
    
    - **$eDiscoveryUser** -這會指定系統管理員的使用者帳戶或規範 manager 將被指派為每個 OneDrive for Business 網站組織中的網站集合管理員例如`"annb@contoso.onmicrosoft.com"`。
    
      > [!NOTE]
      > 變更 **$eDiscoveryUser**變數所指定的使用者帳戶並重新執行指令碼，以指派不同的使用者作為網站集合管理員 OneDrive for Business **$MySiteListFile**變數所指定的網站。 
  
    - **$MySitePrefix**這會指定您組織的我的網站網域的 URL。這是例如包含所有 OneDrive for Business 網站組織中的網域`"https://contoso-my.sharepoint.com"`。
    
    - **$MySiteListFile**這會指定您在步驟 1 中建立的文字檔案的完整路徑。這個檔案包含您的組織中的商務網站的 OneDrive 清單例如`'C:\Users\<youralias>\Desktop\ListOfMysites.txt'`。請務必環繞單一引號的此變數的值 (' ')。請注意您應該指定您在步驟 1 中儲存到文字檔的位置。
    
3. 變更檔名尾碼為 .ps1，將文字檔儲存為 PowerShell 指令碼檔案。例如，儲存 OD4BAssignSCA.txt 檔案為 OD4BAssignSCA.ps1。
    
4. 在 SharePoint Online 管理命令介面中，移至前一步驟建立之 PowerShell 指令碼的所在資料夾，然後執行指令碼，例如：
    
    ```
    .\OD4BAssignSCA.ps1
    ```

    系統會提示您輸入指令碼中所指定的系統管理員帳戶的密碼。如果指令碼執行成功，郵件`"Making  _\<user specified by $eDiscoveryUser\>_ a Site Collection Admin"`會顯示每個 OneDrive for Business 網站 **$MySiteListFile**所指定輸入檔案中所列出的。

## <a name="more-information"></a>詳細資訊

- 您在步驟 3 中執行的指令碼使用**組 SPOUser**指令程式將指定的使用者作為網站集合管理員指派給每個 OneDrive for Business 傳回會列在 **$MySiteListFile**變數所指定的檔案。如果您有很大的組織使用千分位的使用者，請考慮下列 cmdlet 以方便管理指派的 eDiscovery 權限。 
    
  - 編輯您在該清單所在 of OneDrive for Business 的網站，使其包含的網站使用者的使用中的法律案例相關的步驟 1 中建立的檔案。
    
  - 將權限指派給不超過 2500 OneDrive for Business 網站每日。例如，假設您組織中有 10000 OneDrive for Business 的網站。您無法在收集所有網站的步驟 1 中建立清單。然後您可以使用該檔案來建立四個各含 2500 使用者的檔案。在第一天中，您會先 2500 OneDrive for Business 網站指派權限的步驟 3 中執行指令碼。第二個的日期，您將接著 2500 onedrive for Business 網站執行指令碼等等。
    
- 保留記錄的 OneDrive for Business 已指派 eDiscovery 權限和指派為網站集合管理員之使用者的網站。例如指派權限之後，您可以儲存包含清單的 OneDrive for Business 網站的文字檔案並將一條線新增至其識別被指派為網站集合管理員的使用者。
    
- 使用者可以檢視其 OneDrive for Business 網站的網站集合 administators 清單。因為使用者自己 OneDrive for Business 網站的網站集合管理員，他們可以移除網站集合管理員。請考慮下列 cmdlet 以減輕移除指定 eDiscovery 權限給 OneDrive for Business 的網站之使用者的使用者的機會。
    
  - 通訊的 eDiscovery 及規範用途法務已指派為網站集合管理員 OneDrive 貴組織中的商務網站的使用者。
    
  - 重新執行指令碼步驟 3 中，如有必要，將使用者重新指派為網站集合管理員的 OneDrive for Business 的網站。
    
- 您也可以使用您在步驟 3 中執行的指令碼為網站集合管理員移除使用者的 OneDrive for Business 的網站。若要移除的使用者作為網站集合管理員，您必須從變更 （鄰近的指令碼的結尾） 的下列命令： 

    ```
    Set-SPOUser -Site $fullsitepath -LoginName $eDiscoveryUser -IsSiteCollectionAdmin $true
    ```

    變更為：
    
    ```
    Set-SPOUser -Site $fullsitepath -LoginName $eDiscoveryUser -IsSiteCollectionAdmin $false
    ```

    您也可以將指令碼中的這一行：

    ```
    "Making $eDiscoveryUser a Site Collection Admin"
    ```

    變更為：
    
    ```
    "Removing $eDiscoveryUser as a Site Collection Admin"
    ```

    進行這些變更後，使用不同的名稱，例如 OD4BRemoveSCA.ps1、 儲存指令碼，然後用它來移除使用者作為網站集合管理員群組中的 OneDrive 商務網站。
