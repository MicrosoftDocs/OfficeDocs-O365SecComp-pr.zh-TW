---
title: 使用指令碼將使用者新增至 Office 365 安全性 eDiscovery 案例中保留&amp;規範中心
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/23/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: bad352ff-d5d2-45d8-ac2a-6cb832f10e73
description: 執行指令碼以快速新增信箱並 OneDrive for Business 至新的保留與 Office 365 安全性 eDiscovery 案例相關聯的網站&amp;規範中心。
ms.openlocfilehash: eb53f01b4f1b7245e1411ac470db629115eb1ef5
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526672"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-an-ediscovery-case-in-the-office-365-security-amp-compliance-center"></a>使用指令碼將使用者新增至 Office 365 安全性 eDiscovery 案例中保留&amp;規範中心

Office 365 安全性&amp;規範中心提供可讓您的 Windows PowerShell cmdlet 的許多自動化耗時建立及管理 eDiscovery 案例相關的工作。目前在安全性使用 eDiscovery 案件工具&amp;大量 okay 內容位置置於保留規範中心採用時間及準備。例如，建立保留之前，您必須收集的每個 OneDrive for Business 您想要保留的網站的 URL。然後針對想要保留每位使用者，您必須將他們的信箱和其 OneDrive for Business 網站新增至保留。在未來版本的安全性&amp;規範中心這越精確，取得更輕鬆地執行。加上 then，直到您可以使用本文中的指令碼來自動化此程序。
  
指令碼會提示您的組織的我的網站網域名稱 (例如， **contoso** URL 中https://contoso-my.sharepoint.com)、 現有的 eDiscovery 案例的名稱、 新的保留名稱的關聯大小寫、 您想要之使用者的電子郵件地址清單若要放入保留和搜尋查詢使用如果您想要建立查詢式保留。指令碼再 onedrive for Business 網站清單中每個使用者取得的 URL、 會建立新的保留，然後 mailbox 和 OneDrive 新增商務網站的清單中的每位使用者的至保留。指令碼也會產生記錄檔包含的新保留的相關資訊。 
  
若要完成這項工作的步驟如下：
  
[步驟 1：安裝 SharePoint Online 管理命令介面](use-a-script-to-add-users-to-a-hold-in-ediscovery.md#step1)
  
[步驟 2： 產生使用者的清單](use-a-script-to-add-users-to-a-hold-in-ediscovery.md#step2)
  
[步驟 3： 執行指令碼來建立保留和新增使用者](use-a-script-to-add-users-to-a-hold-in-ediscovery.md#step3)
  
## <a name="before-you-begin"></a>開始之前

- 您必須是安全性 eDiscovery 管理員角色群組的成員&amp;規範中心和步驟 3 中執行指令碼的 SharePoint Online 全域管理員。如需詳細資訊，請參閱[指派 Office 365 安全性 eDiscovery 權限&amp;規範中心](assign-ediscovery-permissions.md)。
    
- 最大值為 1000 信箱和 100 網站可以新增至 eDiscovery 案例中的安全性與相關聯保留&amp;規範中心。假設您想要保留每個使用者具有 OneDrive for Business 網站，您可以新增使用本文中的指令碼保留最大值為 100 位使用者。 
    
- 請務必儲存您在步驟 2 和步驟 3 中指令碼以相同的資料夾中建立的使用者清單。會將容易執行指令碼。
    
- 指令碼會將使用者清單新增至新的保留相關聯的現有案例。請確定您要建立關聯的保留與案例建立之前執行指令碼。
    
- 指令碼包括最少的錯誤處理。其主要用途是快速又輕鬆地放置信箱按住 OneDrive for Business 網站上的每位使用者。
    
- 本主題中所提供的範例指令碼不支援任何 Microsoft 標準支援程式或服務底下。為 IS 提供範例指令碼沒有任何類型的瑕疵擔保。Microsoft 進一步不作所有默示之的擔保包括但不限於任何默示擔保售或適合特定用途。與您保持承擔使用或效能的範例指令碼及文件的風險。事件無法在 Microsoft、 其作者，或其他參與建立、 實際執行或指令碼傳遞的任何人對於而概之任何損害皆不 （包括但不限於，遺漏的商務利潤、 業務中斷、 遺失的損害商務資訊或其他金錢遺失） 引起的使用或無法使用的範例指令碼或文件即使 Microsoft 已被告知這類損害的可能性。

## <a name="step-1-install-the-sharepoint-online-management-shell"></a>步驟 1：安裝 SharePoint Online 管理命令介面

第一個步驟是如果尚未安裝在本機電腦上安裝 SharePoint Online 管理命令介面。您沒有在此程序，使用命令介面，但因為包含您在步驟 3 中執行的指令碼所需的必要條件安裝方式。這些先決條件允許指令碼與 SharePoint Online 取得 Url onedrive for Business 網站進行通訊。
  
移至 [[設定 SharePoint Online 管理命令介面 Windows PowerShell 環境](https://go.microsoft.com/fwlink/p/?LinkID=286318)及執行步驟 1 與步驟 2 到本機電腦上安裝 SharePoint Online 管理命令介面。 

## <a name="step-2-generate-a-list-of-users"></a>步驟 2： 產生使用者的清單
<a name="step2"> </a>

步驟 3 中的指令碼會建立具有相關聯的 eDiscovery 案例、 及新增信箱和 OneDrive 至保留的使用者清單中的商務網站的保留。您只可以輸入電子郵件地址的文字檔案，或您可以取得的電子郵件地址清單並將其儲存至檔案 （位於相同的資料夾，您將步驟 3 中儲存指令碼） 的 Windows PowerShell 中執行的命令。
  
以下是 PowerShell 命令 （即您執行使用遠端 PowerShell 連線至 Exchange Online 組織） 取得組織中的所有使用者的電子郵件地址清單並將它儲存到文字檔名為 HoldUsers.txt。
  
```
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

在執行此命令、 開啟文字檔案並移除包含屬性名稱的標頭之後`PrimarySmtpAddress`。然後移除您要新增至保留您將在步驟 3 中建立的使用者除外的所有電子郵件地址。請確定有無空白資料列之前或之後的電子郵件地址清單。
  

  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a>步驟 3： 執行指令碼來建立保留和新增使用者
<a name="step3"> </a>

當您在此步驟中執行指令碼時，它會提示您下列資訊。請務必在執行指令碼之前已準備好此資訊。
  
- **您的使用者認證**-指令碼會使用您的認證連線至安全性&amp;遠端 PowerShell 與規範中心。它也會使用這些認證以存取 SharePoint Online 取得 OneDrive for Business Url 的使用者清單。
    
- **我的網站網域的名稱**-我的網站的網域是包含所有 OneDrive for Business 您組織中的網站的網域。例如，如果我的網站網域 URL **https://contoso-my.sharepoint.com**，則要輸入`contoso`當指令碼會提示您輸入 MySite 網域的名稱。 
    
- **大小寫的名稱**-現有案例的名稱。指令碼會建立新的保留相關聯此案例。
    
- 會建立**的保留名稱**的指令碼的保留名稱並將其關聯的指定大小寫。
    
- **搜尋查詢的查詢式保留**-您可以建立查詢式保留，以符合指定的搜尋準則的內容處於保留狀態。若要置於保留的所有內容，只是按下**Enter**當系統提示您在搜尋查詢。 
    
- **是否要開啟 [保留**-您可以在建立或您可以建立保留不啟用它的指令碼之後開啟保留的指令碼。如果您沒有開啟保留的指令碼，您可以在加以開啟稍後安全性&amp;規範中心或執行下列 PowerShell 命令： 
    
  ```
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- **使用者的清單的文字檔案名稱**-包含清單的使用者新增至保留的步驟 2 中的文字檔案的名稱。如果此檔案位於指令碼相同的資料夾，只輸入檔案 (例如 HoldUsers.txt) 的名稱。在另一個資料夾中的文字檔案時，輸入檔案的完整路徑名稱。
    
您已收集指令碼會提示您輸入的資訊之後，最後一個步驟是執行指令碼建立新的保留並將使用者新增至其。
  
1. 使用.ps1; filename 尾碼將下列文字儲存到 Windows PowerShell 指令碼檔案例如， `AddUsersToHold.ps1`。
    
  ```
  #script begin
  " " 
  write-host "***********************************************"
  write-host "   Office 365 Security &amp; Compliance Center   " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "   eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
  write-host "***********************************************"
  " " 
  # Get user credentials &amp; Connect to Office 365 SCC, SPO
  $credentials = Get-Credential -Message "Specify your credentials to connect to the Office 365 Security &amp; Compliance Center and SharePoint Online"
  $s = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://ps.compliance.protection.outlook.com/powershell-liveid" -Credential $credentials -Authentication Basic -AllowRedirection -SessionOption (New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck)
  $a = Import-PSSession $s -AllowClobber
      if (!$s)
      {
          Write-Error "Couldn't create PowerShell session."
          return;
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
          Write-Error "The SharePoint Online Management Shell isn't installed. Please install it from: http://go.microsoft.com/fwlink/p/?LinkId=255251 and then re-run this script."
          return;
      }
  }
  if (!$spCreds)
  {
      $spCreds = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($credentials.UserName, $credentials.Password)
  }
  # Get the user's MySite domain name. We use this to create the admin URL and root URL for OneDrive for Business
  ""
  $mySiteDomain = Read-Host "Enter the name of your organization's MySite domain. For example, 'contoso' for 'https://contoso-my.sharepoint.com'"
  ""
  # Get other required information
  do{
  $casename = Read-Host "Enter the name of the case"
  $caseexists = (get-compliancecase -identity "$casename" -erroraction SilentlyContinue).isvalid
  if($caseexists -ne 'True')
  {""
  write-host "A case named '$casename' doesn't exist. Please specify the name of an existing case, or create a new case and then re-run the script." -foregroundColor Yellow
  ""}
  }While($caseexists -ne 'True')
  ""
  do{
  $holdName = Read-Host "Enter the name of the new hold"
  $holdexists=(get-caseholdpolicy -identity "$holdname" -case "$casename" -erroraction SilentlyContinue).isvalid
  if($holdexists -eq 'True')
  {""
  write-host "A hold named '$holdname' already exists. Please specify a new hold name." -foregroundColor Yellow
  ""}
  }While($holdexists -eq 'True')
  ""
  $holdQuery = Read-Host "Enter a search query to create a query-based hold, or press Enter to hold all content"
  ""
  $holdstatus = read-host "Do you want the hold enabled after it's created? (Yes/No)"
  do{
  ""
  $inputfile = read-host "Enter the name of the text file that contains the email addresses of the users to add to the hold"
  ""
  $fileexists = test-path -path $inputfile
  if($fileexists -ne 'True'){write-host "$inputfile doesn't exist. Please enter a valid file name." -foregroundcolor Yellow}
  }while($fileexists -ne 'True')
  #Import the list of addresses from the txt file.  Trim any excess spaces and make sure all addresses 
      #in the list are unique.
    [array]$emailAddresses = Get-Content $inputfile -ErrorAction SilentlyContinue | where {$_.trim() -ne ""}  | foreach{ $_.Trim() }
    [int]$dupl = $emailAddresses.count
    [array]$emailAddresses = $emailAddresses | select-object -unique
    $dupl -= $emailAddresses.count
  #Validate email addresses so the hold creation does not run in to an error.
  if($emailaddresses.count -gt 0){
  write-host ($emailAddresses).count "addresses were found in the text file. There were $dupl duplicate entries in the file." -foregroundColor Yellow
  ""
  Write-host "Validating the email addresses. Please wait..." -foregroundColor Yellow
  ""
  $finallist =@()
  foreach($emailAddress in $emailAddresses)
  {
  if((get-recipient $emailaddress -erroraction SilentlyContinue).isvalid -eq 'True')
  {$finallist += $emailaddress}
  else {"Unable to find the user $emailaddress"
  [array]$excludedlist += $emailaddress}
  }
  ""
  #find user's OneDrive Site URL using email address
  Write-Host "Getting the URL for each user's OneDrive for Business site." -foregroundColor Yellow
  ""
  $AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
  $mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
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
  $urls = @()
  foreach($emailAddress in $emailAddresses)
  {
        try{
          $prop = $UserProfileService.GetUserProfileByName("i:0#.f|membership|$emailAddress") | Where-Object { $_.Name -eq "PersonalSpace" }
          $url = $prop.values[0].value
        if($url -ne $null){
          $furl = $mySiteUrlRoot + $url
          $urls += $furl
          Write-Host "- $emailAddress => $furl"
        [array]$ODadded += $furl}
    else{    
          Write-Warning "Couldn't locate OneDrive for $emailAddress"
        [array]$ODExluded += $emailAddress
      }}
    catch { 
    Write-Warning "Could not locate OneDrive for $emailAddress"
    [array]$ODExluded += $emailAddress
    Continue }
  }
  if(($finallist.count -gt 0) -or ($urls.count -gt 0)){
  ""
  Write-Host "Creating the hold named $holdname. Please wait..." -foregroundColor Yellow
  if(($holdstatus -eq "Y") -or ($holdstatus -eq  "y") -or ($holdstatus -eq "yes") -or ($holdstatus -eq "YES")){
  New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $True | out-null
  New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery | out-null
  }
  else{
  New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $false | out-null
  New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery -disabled $true | out-null
  }
  ""
  }
  else {"No valid locations were identified. Therefore, the hold wasn't created."}
  #write log files (if needed)
  $newhold=Get-CaseHoldPolicy -Identity "$holdname" -Case "$casename" -erroraction SilentlyContinue
  $newholdrule=Get-CaseHoldRule -Identity "$holdName" -erroraction SilentlyContinue
  if(($ODAdded.count -gt 0) -or ($ODExluded.count -gt 0) -or ($finallist.count -gt 0) -or ($excludedlist.count -gt 0) -or ($newhold.isvalid -eq 'True') -or ($newholdrule.isvalid -eq 'True'))
  {
  Write-Host "Generating output files..." -foregroundColor Yellow
  if($ODAdded.count -gt 0){
  "OneDrive Locations" | add-content .\LocationsOnHold.txt
  "==================" | add-content .\LocationsOnHold.txt 
  $newhold.SharePointLocation.name | add-content .\LocationsOnHold.txt}
  if($ODExluded.count -gt 0){ 
  "Users without OneDrive locations" | add-content .\LocationsNotOnHold.txt
  "================================" | add-content .\LocationsNotOnHold.txt
  $ODExluded | add-content .\LocationsNotOnHold.txt}
  if($finallist.count -gt 0){
  " " | add-content .\LocationsOnHold.txt
  "Exchange Locations" | add-content .\LocationsOnHold.txt
  "==================" | add-content .\LocationsOnHold.txt 
  $newhold.ExchangeLocation.name | add-content .\LocationsOnHold.txt}
  if($excludedlist.count -gt 0){
  " "| add-content .\LocationsNotOnHold.txt
  "Mailboxes not added to the hold" | add-content .\LocationsNotOnHold.txt
  "===============================" | add-content .\LocationsNotOnHold.txt
  $excludedlist | add-content .\LocationsNotOnHold.txt}
  $FormatEnumerationLimit=-1
  if($newhold.isvalid -eq 'True'){$newhold|fl >.\GetCaseHoldPolicy.txt}
  if($newholdrule.isvalid -eq 'True'){$newholdrule|Fl >.\GetCaseHoldRule.txt}
  }
  }
  else {"The hold wasn't created because no valid entries were found in the text file."}
  ""
  Write-host "Script complete!" -foregroundColor Yellow
  ""
  #script end
  ```

2. 在您的本機電腦上開啟 Windows PowerShell，並移至您儲存指令碼的資料夾。
    
3. 執行指令碼 ；例如：
    
      ```
    .\AddUsersToHold.ps1
      ```

4. 輸入指令碼會提示您輸入的資訊。
    
    指令碼連線到安全性與規範中心 PowerShell]，然後 eDiscovery 案例中建立新的保留並新增信箱和 OneDrive for Business 的清單中的使用者。您可以在 [ **eDiscovery** ] 頁面上的 [安全性] 移至大小寫&amp;規範中心檢視新的保留。 
    
指令碼完成之後執行，它會建立下列記錄檔，並將它們儲存到指令碼所在的資料夾。
  
- **LocationsOnHold.txt** -包含之商務網站的指令碼成功放入保留信箱和 OneDrive 的清單。
    
- **LocationsNotOnHold.txt** -包含之商務網站的指令碼並未不會保留上放置信箱和 OneDrive 的清單。如果使用者擁有信箱，但不是 OneDrive for Business 網站，使用者就會包含清單中的 OneDrive for 未處於保留狀態的商務網站。
    
- **GetCaseHoldPolicy.txt** -包含新的保留在建立新的保留之後執行指令碼**取得 CaseHoldPolicy** cmdlet 的輸出。此指令程式所傳回的資訊包括保留及是否啟用或停用保留放置其信箱和 OneDrive for Business 網站的使用者清單。 
    
- **GetCaseHoldRule.txt** -包含新的保留在建立新的保留之後執行指令碼**取得 CaseHoldRule** cmdlet 的輸出。如果您用來建立查詢式保留的指令碼，此指令程式所傳回的資訊包括搜尋查詢。 
