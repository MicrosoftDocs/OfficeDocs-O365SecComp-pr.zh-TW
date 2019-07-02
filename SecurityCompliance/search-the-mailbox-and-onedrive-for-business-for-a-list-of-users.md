---
title: 使用內容搜尋來搜尋信箱與商務用 OneDrive 網站的使用者清單
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/3/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 5f4f8206-2d6a-4cb2-bbc6-7a0698703cc0
description: 使用內容搜尋和本文中的腳本, 搜尋使用者群組的信箱和商務用 OneDrive 網站。
ms.openlocfilehash: a9ee2db0bc0fc7a4b53c58f02bcb9d16f96fc403
ms.sourcegitcommit: a6968df6e47ab5733a995f1efdc6e3676c5b5d7b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2019
ms.locfileid: "35253922"
---
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a>使用內容搜尋來搜尋信箱與商務用 OneDrive 網站的使用者清單

安全性 & 合規性中心提供許多 Windows PowerShell Cmdlet, 可讓您自動化耗時的 eDiscovery 相關工作。 目前, 在安全性 & 合規性中心內建立內容搜尋, 以搜尋大量的保管人內容位置, 需要時間和準備。 建立搜尋之前, 您必須收集每個商務用 OneDrive 網站的 URL, 然後將每個信箱和商務用 OneDrive 網站新增至搜尋。 在未來的版本中, 這會在安全性 & 規範中心中更容易進行。 在此之前, 您可以使用本文中的腳本來自動化此程式。 此腳本會提示您輸入組織的 [我的網站] 網域的名稱 ( **** 例如, 在 URL https://contoso-my.sharepoint.com)中輸入 contoso、使用者電子郵件地址的清單、新內容搜尋的名稱, 以及要使用的搜尋查詢)。 腳本會取得清單中每位使用者的商務用 OneDrive URL, 然後建立並啟動內容搜尋, 搜尋清單中每位使用者的信箱和商務用 OneDrive 網站, 並使用您提供的搜尋查詢。 
  
## <a name="before-you-begin"></a>開始之前

- 您必須是安全性 & 合規性中心內的 eDiscovery 管理員角色群組成員, 以及 SharePoint Online 全域系統管理員, 才能在步驟3中執行腳本。
    
- 請務必將您在步驟2中建立的使用者清單與步驟3中的腳本儲存在相同的資料夾中。 這可讓您更容易執行腳本。
    
- 腳本包含最少的錯誤處理。 其主要用途是快速且輕鬆地搜尋每個使用者的信箱和商務用 OneDrive 網站。
    
- 在任何 Microsoft standard 支援方案或服務下, 都不支援本主題中提供的範例腳本。 範例腳本是以原樣提供, 而不是任何種類的擔保。 Microsoft 會進一步否認所有[https://go.microsoft.com/fwlink/p/?LinkId=517283](https://go.microsoft.com/fwlink/p/?LinkId=517283)的 mplied 保證, 包括但不限於任何適售性或特定用途適用性的任何暗示擔保。 由範例腳本和檔的使用或效能所造成的全部風險, 都會保留給您。 在沒有任何事件的情況下, Microsoft、其作者, 或腳本的建立、生產或交付的任何人都對任何損害負責 (包括但不限於失去業務利潤損失、業務中斷、遺失因使用或無法使用範例腳本或檔, 而造成的商務資訊或其他 pecuniary 遺失, 即使 Microsoft 已被告知這類損害的可能性, 也是如此。
    
## <a name="step-1-install-the-sharepoint-online-management-shell"></a>步驟 1：安裝 SharePoint Online 管理命令介面
<a name="step1"> </a>

第一步是安裝 SharePoint Online 管理命令介面。 您不需要在此程式中使用命令介面, 但是必須安裝它, 因為它包含您在步驟3中執行之腳本所需的必要條件。 這些必要條件可讓腳本與 SharePoint Online 通訊, 以取得商務用 OneDrive 網站的 Url。
  
請移至[設定 Sharepoint Online 管理命令介面 Windows PowerShell 環境](https://go.microsoft.com/fwlink/p/?LinkID=286318), 並執行步驟1和步驟 2, 以安裝 SharePoint Online 管理命令介面。
  
## <a name="step-2-generate-a-list-of-users"></a>步驟 2: 產生使用者清單
<a name="step2"> </a>

步驟3中的腳本會建立內容搜尋, 以在信箱和 OneDrive 帳戶中搜尋使用者清單。 您可以只在文字檔中輸入電子郵件地址, 也可以在 Windows PowerShell 中執行命令, 以取得電子郵件地址清單, 並將其儲存至檔案 (位於您將在步驟3中儲存腳本的相同資料夾中)。
  
以下是您可以 runt 的[Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283)命令, 以取得組織中所有使用者的電子郵件地址清單, 並將其儲存至名為`Users.txt`的文字檔。 
  
```
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

在您執行此命令之後, 請務必開啟檔案並移除包含屬性名稱的標頭`PrimarySmtpAddress`。 文字檔應該只包含電子郵件地址清單, 而不包含其他內容。 請確定在電子郵件地址清單之前或之後都沒有空白列。
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a>步驟 3: 執行腳本以建立及啟動搜尋

當您在此步驟中執行腳本時, 會提示您輸入下列資訊。 請務必準備好此資訊, 再執行腳本。
  
- **您的使用者認證**-腳本會使用您的認證來存取 SharePoint Online, 以取得商務用 OneDrive url, 並使用遠端 PowerShell 連線至安全性 & 合規性中心。 
    
- **您的「我的網站」網功能變數名稱稱**-「我的網站」網域是包含組織中所有商務用 OneDrive 網站的網域。 例如, 如果您的 [我的網站] 網域**https://contoso-my.sharepoint.com**的 URL 是, 您`contoso`可以在腳本提示您輸入您的「我的網站」網域的名稱時輸入。 
    
- **步驟2中文字檔的路徑名**-您在步驟2中建立之文字檔的路徑名。 如果文字檔和腳本位於相同的資料夾中, 則輸入文字檔的名稱。 否則, 請輸入文字檔的完整路徑名。 
    
- **內容搜尋的名稱**-將由腳本建立之內容搜尋的名稱。 
    
- **搜尋查詢**-會建立並執行將用於內容搜尋的搜尋查詢。 如需搜尋查詢的詳細資訊, 請參閱[內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。


**若要執行腳本:**
    
1. 使用 filename 的檔案名尾碼, 將下列文字儲存至 Windows PowerShell 腳本檔案。例如, `SearchEXOOD4B.ps1`。 將檔案儲存到您在步驟2中儲存使用者清單的相同資料夾。
    
  ```
  # This PowerShell script will prompt you for the following information:
  #    * Your user credentials 
  #    * The name of your organization's MySite domain                                              
  #    * The pathname for the text file that contains a list of user email addresses
  #    * The name of the Content Search that will be created
  #    * The search query string
  # The script will then:
  #    * Find the OneDrive for Business site for each user in the text file
  #    * Create and start a Content Search using the above information
  # Get user credentials
  if (!$credentials)
  {
      $credentials = Get-Credential
  }
  # Get the user's MySite domain name.  We use this to create the admin URL and root URL for OneDrive for Business
  $mySiteDomain = Read-Host "What is your organization's MySite domain?  For example,  'contoso' for 'https://contoso-my.sharepoint.com'"
  $AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
  $mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
  # Get other required information
  $inputfile = read-host "Enter the file name of the text file that contains the email addresses for the users you want to search"
  $searchName = Read-Host "Enter the name for the new search"
  $searchQuery = Read-Host "Enter the search query you want to use"
  $emailAddresses = Get-Content $inputfile | where {$_ -ne ""}  | foreach{ $_.Trim() }
  # Connect to Office 365
  if (!$s -or !$a)
  {
      $s = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://ps.compliance.protection.outlook.com/powershell-liveid" -Credential $credentials -Authentication Basic -AllowRedirection -SessionOption (New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck)
      $a = Import-PSSession $s -AllowClobber
      if (!$s)
      {
          Write-Error "Could not create PowerShell session."
          return;
      }
  }
  # Load the SharePoint assemblies from the SharePoint Online Management Shell
  # To install, go to http://go.microsoft.com/fwlink/p/?LinkId=255251
  if (!$SharePointClient -or !$SPRuntime -or !$SPUserProfile)
  {
      $SharePointClient = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client")
      $SPRuntime = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.Runtime")
      $SPUserProfile = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.UserProfiles")
      if (!$SharePointClient)
      {
          Write-Error "SharePoint Online Management Shell isn't installed, please install from: http://go.microsoft.com/fwlink/p/?LinkId=255251 and then run this script again"
          return;
      }
  }
  if (!$spCreds)
  {
      $spCreds = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($credentials.UserName, $credentials.Password)
  }
  # Add the path of the User Profile Service to the SPO admin URL, then create a new webservice proxy to access it
  $proxyaddr = "$AdminUrl/_vti_bin/UserProfileService.asmx?wsdl"
  $UserProfileService= New-WebServiceProxy -Uri $proxyaddr -UseDefaultCredential False
  $UserProfileService.Credentials = $credentials
  # Take care of auth cookies
  $strAuthCookie = $spCreds.GetAuthenticationCookie($AdminUrl)
  $uri = New-Object System.Uri($AdminUrl)
  $container = New-Object System.Net.CookieContainer
  $container.SetCookies($uri, $strAuthCookie)
  $UserProfileService.CookieContainer = $container
  Write-Host "Getting each user's OneDrive for Business URL"
  $urls = @()
  foreach($emailAddress in $emailAddresses)
  {
      try
      {
          $prop = $UserProfileService.GetUserProfileByName("i:0#.f|membership|$emailAddress") | Where-Object { $_.Name -eq "PersonalSpace" } 
          $url = $prop.values[0].value
          $furl = $mySiteUrlRoot + $url
          $urls += $furl
          Write-Host "-$emailAddress => $furl"
      }
      catch
      {
          Write-Warning "Could not locate OneDrive for $emailAddress"
      }
  }
  Write-Host "Creating and starting the search"
  $search = New-ComplianceSearch -Name $searchName -ExchangeLocation $emailAddresses -SharePointLocation $urls -ContentMatchQuery $searchQuery
  # Finally, start the search and then display the status
  if($search)
  {
      Start-ComplianceSearch $search.Name
      Get-ComplianceSearch $search.Name
  }
  
  ```

2. 開啟 Windows PowerShell, 然後移至您在其中儲存腳本的資料夾和步驟2中的使用者清單。
    
3. 啟動腳本;例如:
    
    ```
    .\SearchEXOOD4B.ps1
    ```

4. 當系統提示您輸入您的認證時, 請輸入您的電子郵件地址和密碼, 然後按一下 **[確定]**。 
    
5. 當腳本提示時, 輸入下列資訊。 輸入每一條資訊, 然後按**enter**。
    
    - 您的 [我的網站] 網域的名稱。 
    
    - 包含使用者清單之文字檔的路徑名。
    
    - 內容搜尋的名稱。
    
    - 搜尋查詢 (保留此空白可傳回內容位置中的所有專案)。
    
    腳本會取得每個商務用 OneDrive 網站的 Url, 然後建立並啟動搜尋。 您可以在安全性 & 合規性中心 PowerShell 中執行**new-compliancesearch 指令程式**, 以顯示搜尋統計資料和結果, 或是您可以移至安全性 & 規範中心的 [**內容搜尋**] 頁面, 以查看資訊關於搜尋。 
