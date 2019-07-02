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
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a><span data-ttu-id="5d884-103">使用內容搜尋來搜尋信箱與商務用 OneDrive 網站的使用者清單</span><span class="sxs-lookup"><span data-stu-id="5d884-103">Use Content Search to search the mailbox and OneDrive for Business site for a list of users</span></span>

<span data-ttu-id="5d884-104">安全性 & 合規性中心提供許多 Windows PowerShell Cmdlet, 可讓您自動化耗時的 eDiscovery 相關工作。</span><span class="sxs-lookup"><span data-stu-id="5d884-104">The Security & Compliance Center provides a number of Windows PowerShell cmdlets that let you automate time-consuming eDiscovery-related tasks.</span></span> <span data-ttu-id="5d884-105">目前, 在安全性 & 合規性中心內建立內容搜尋, 以搜尋大量的保管人內容位置, 需要時間和準備。</span><span class="sxs-lookup"><span data-stu-id="5d884-105">Currently, creating a Content Search in the Security & Compliance Center to search a large number of custodian content locations takes time and preparation.</span></span> <span data-ttu-id="5d884-106">建立搜尋之前, 您必須收集每個商務用 OneDrive 網站的 URL, 然後將每個信箱和商務用 OneDrive 網站新增至搜尋。</span><span class="sxs-lookup"><span data-stu-id="5d884-106">Before you create a search, you have to collect the URL for each OneDrive for Business site and then add each mailbox and OneDrive for Business site to the search.</span></span> <span data-ttu-id="5d884-107">在未來的版本中, 這會在安全性 & 規範中心中更容易進行。</span><span class="sxs-lookup"><span data-stu-id="5d884-107">In future releases, this will be easier to do in the Security & Compliance Center.</span></span> <span data-ttu-id="5d884-108">在此之前, 您可以使用本文中的腳本來自動化此程式。</span><span class="sxs-lookup"><span data-stu-id="5d884-108">Until then, you can use the script in this article to automate this process.</span></span> <span data-ttu-id="5d884-109">此腳本會提示您輸入組織的 [我的網站] 網域的名稱 ( \*\*\*\* 例如, 在 URL https://contoso-my.sharepoint.com)中輸入 contoso、使用者電子郵件地址的清單、新內容搜尋的名稱, 以及要使用的搜尋查詢)。</span><span class="sxs-lookup"><span data-stu-id="5d884-109">This script prompts you for the name of your organization's MySite domain (for example, **contoso** in the URL https://contoso-my.sharepoint.com), a list of user email addresses, the name of the new Content Search, and the search query to use.</span></span> <span data-ttu-id="5d884-110">腳本會取得清單中每位使用者的商務用 OneDrive URL, 然後建立並啟動內容搜尋, 搜尋清單中每位使用者的信箱和商務用 OneDrive 網站, 並使用您提供的搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="5d884-110">The script gets the OneDrive for Business URL for each user in the list, and then it creates and starts a Content Search that searches the mailbox and OneDrive for Business site for each user in the list, using the search query that you provide.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="5d884-111">開始之前</span><span class="sxs-lookup"><span data-stu-id="5d884-111">Before you begin</span></span>

- <span data-ttu-id="5d884-112">您必須是安全性 & 合規性中心內的 eDiscovery 管理員角色群組成員, 以及 SharePoint Online 全域系統管理員, 才能在步驟3中執行腳本。</span><span class="sxs-lookup"><span data-stu-id="5d884-112">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center and a SharePoint Online global administrator to run the script in Step 3.</span></span>
    
- <span data-ttu-id="5d884-113">請務必將您在步驟2中建立的使用者清單與步驟3中的腳本儲存在相同的資料夾中。</span><span class="sxs-lookup"><span data-stu-id="5d884-113">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder.</span></span> <span data-ttu-id="5d884-114">這可讓您更容易執行腳本。</span><span class="sxs-lookup"><span data-stu-id="5d884-114">That will make it easier to run the script.</span></span>
    
- <span data-ttu-id="5d884-115">腳本包含最少的錯誤處理。</span><span class="sxs-lookup"><span data-stu-id="5d884-115">The script includes minimal error handling.</span></span> <span data-ttu-id="5d884-116">其主要用途是快速且輕鬆地搜尋每個使用者的信箱和商務用 OneDrive 網站。</span><span class="sxs-lookup"><span data-stu-id="5d884-116">It's primary purpose is to quickly and easily search the mailbox and OneDrive for Business site of each user.</span></span>
    
- <span data-ttu-id="5d884-117">在任何 Microsoft standard 支援方案或服務下, 都不支援本主題中提供的範例腳本。</span><span class="sxs-lookup"><span data-stu-id="5d884-117">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="5d884-118">範例腳本是以原樣提供, 而不是任何種類的擔保。</span><span class="sxs-lookup"><span data-stu-id="5d884-118">The sample scripts are provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="5d884-119">Microsoft 會進一步否認所有[https://go.microsoft.com/fwlink/p/?LinkId=517283](https://go.microsoft.com/fwlink/p/?LinkId=517283)的 mplied 保證, 包括但不限於任何適售性或特定用途適用性的任何暗示擔保。</span><span class="sxs-lookup"><span data-stu-id="5d884-119">Microsoft further disclaims all i[https://go.microsoft.com/fwlink/p/?LinkId=517283](https://go.microsoft.com/fwlink/p/?LinkId=517283)mplied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="5d884-120">由範例腳本和檔的使用或效能所造成的全部風險, 都會保留給您。</span><span class="sxs-lookup"><span data-stu-id="5d884-120">The entire risk arising out of the use or performance of the sample scripts and documentation remains with you.</span></span> <span data-ttu-id="5d884-121">在沒有任何事件的情況下, Microsoft、其作者, 或腳本的建立、生產或交付的任何人都對任何損害負責 (包括但不限於失去業務利潤損失、業務中斷、遺失因使用或無法使用範例腳本或檔, 而造成的商務資訊或其他 pecuniary 遺失, 即使 Microsoft 已被告知這類損害的可能性, 也是如此。</span><span class="sxs-lookup"><span data-stu-id="5d884-121">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="5d884-122">步驟 1：安裝 SharePoint Online 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="5d884-122">Step 1: Install the SharePoint Online Management Shell</span></span>
<span data-ttu-id="5d884-123"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="5d884-123"></span></span>

<span data-ttu-id="5d884-124">第一步是安裝 SharePoint Online 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="5d884-124">The first step is to install the SharePoint Online Management Shell.</span></span> <span data-ttu-id="5d884-125">您不需要在此程式中使用命令介面, 但是必須安裝它, 因為它包含您在步驟3中執行之腳本所需的必要條件。</span><span class="sxs-lookup"><span data-stu-id="5d884-125">You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3.</span></span> <span data-ttu-id="5d884-126">這些必要條件可讓腳本與 SharePoint Online 通訊, 以取得商務用 OneDrive 網站的 Url。</span><span class="sxs-lookup"><span data-stu-id="5d884-126">These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="5d884-127">請移至[設定 Sharepoint Online 管理命令介面 Windows PowerShell 環境](https://go.microsoft.com/fwlink/p/?LinkID=286318), 並執行步驟1和步驟 2, 以安裝 SharePoint Online 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="5d884-127">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](https://go.microsoft.com/fwlink/p/?LinkID=286318) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell.</span></span>
  
## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="5d884-128">步驟 2: 產生使用者清單</span><span class="sxs-lookup"><span data-stu-id="5d884-128">Step 2: Generate a list of users</span></span>
<span data-ttu-id="5d884-129"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="5d884-129"></span></span>

<span data-ttu-id="5d884-130">步驟3中的腳本會建立內容搜尋, 以在信箱和 OneDrive 帳戶中搜尋使用者清單。</span><span class="sxs-lookup"><span data-stu-id="5d884-130">The script in Step 3 will create a Content Search to search the mailboxes and OneDrive accounts for a list of users.</span></span> <span data-ttu-id="5d884-131">您可以只在文字檔中輸入電子郵件地址, 也可以在 Windows PowerShell 中執行命令, 以取得電子郵件地址清單, 並將其儲存至檔案 (位於您將在步驟3中儲存腳本的相同資料夾中)。</span><span class="sxs-lookup"><span data-stu-id="5d884-131">You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="5d884-132">以下是您可以 runt 的[Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283)命令, 以取得組織中所有使用者的電子郵件地址清單, 並將其儲存至名為`Users.txt`的文字檔。</span><span class="sxs-lookup"><span data-stu-id="5d884-132">Here's an [Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283) command that you can runt to get a list of email addresses for all users in your organization and save it to a text file named `Users.txt`.</span></span> 
  
```
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

<span data-ttu-id="5d884-133">在您執行此命令之後, 請務必開啟檔案並移除包含屬性名稱的標頭`PrimarySmtpAddress`。</span><span class="sxs-lookup"><span data-stu-id="5d884-133">After you run this command, be sure to open the file and remove the header that contains the property name,  `PrimarySmtpAddress`.</span></span> <span data-ttu-id="5d884-134">文字檔應該只包含電子郵件地址清單, 而不包含其他內容。</span><span class="sxs-lookup"><span data-stu-id="5d884-134">The text file should just contain a list of email addresses, and nothing else.</span></span> <span data-ttu-id="5d884-135">請確定在電子郵件地址清單之前或之後都沒有空白列。</span><span class="sxs-lookup"><span data-stu-id="5d884-135">Make sure there are no blank rows before or after the list of email addresses.</span></span>
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a><span data-ttu-id="5d884-136">步驟 3: 執行腳本以建立及啟動搜尋</span><span class="sxs-lookup"><span data-stu-id="5d884-136">Step 3: Run the script to create and start the search</span></span>

<span data-ttu-id="5d884-137">當您在此步驟中執行腳本時, 會提示您輸入下列資訊。</span><span class="sxs-lookup"><span data-stu-id="5d884-137">When you run the script in this step, it will prompt you for the following information.</span></span> <span data-ttu-id="5d884-138">請務必準備好此資訊, 再執行腳本。</span><span class="sxs-lookup"><span data-stu-id="5d884-138">Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="5d884-139">**您的使用者認證**-腳本會使用您的認證來存取 SharePoint Online, 以取得商務用 OneDrive url, 並使用遠端 PowerShell 連線至安全性 & 合規性中心。</span><span class="sxs-lookup"><span data-stu-id="5d884-139">**Your user credentials** - The script will use your credentials to access SharePoint Online to get the OneDrive for Business URLs and to connect to the Security & Compliance Center with remote PowerShell.</span></span> 
    
- <span data-ttu-id="5d884-140">**您的「我的網站」網功能變數名稱稱**-「我的網站」網域是包含組織中所有商務用 OneDrive 網站的網域。</span><span class="sxs-lookup"><span data-stu-id="5d884-140">**Name of your MySite domain** - The MySite domain is the domain that contains all the OneDrive for Business sites in your organization.</span></span> <span data-ttu-id="5d884-141">例如, 如果您的 [我的網站] 網域**https://contoso-my.sharepoint.com**的 URL 是, 您`contoso`可以在腳本提示您輸入您的「我的網站」網域的名稱時輸入。</span><span class="sxs-lookup"><span data-stu-id="5d884-141">For example, if the URL for your MySite domain is **https://contoso-my.sharepoint.com**, then you would enter  `contoso` when the script prompts you for the name of your MySite domain.</span></span> 
    
- <span data-ttu-id="5d884-142">**步驟2中文字檔的路徑名**-您在步驟2中建立之文字檔的路徑名。</span><span class="sxs-lookup"><span data-stu-id="5d884-142">**Pathname of the text file from Step 2** - The pathname of the text file that you created in Step 2.</span></span> <span data-ttu-id="5d884-143">如果文字檔和腳本位於相同的資料夾中, 則輸入文字檔的名稱。</span><span class="sxs-lookup"><span data-stu-id="5d884-143">If the text file and the script are located in the same folder, then enter the name of the text file.</span></span> <span data-ttu-id="5d884-144">否則, 請輸入文字檔的完整路徑名。</span><span class="sxs-lookup"><span data-stu-id="5d884-144">Otherwise, enter the complete pathname for the text file.</span></span> 
    
- <span data-ttu-id="5d884-145">**內容搜尋的名稱**-將由腳本建立之內容搜尋的名稱。</span><span class="sxs-lookup"><span data-stu-id="5d884-145">**Name of the Content Search** - The name of the Content Search that will be created by the script.</span></span> 
    
- <span data-ttu-id="5d884-146">**搜尋查詢**-會建立並執行將用於內容搜尋的搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="5d884-146">**Search query** - The search query that will be used with the Content Search is created and run.</span></span> <span data-ttu-id="5d884-147">如需搜尋查詢的詳細資訊, 請參閱[內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="5d884-147">For more information about search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>


<span data-ttu-id="5d884-148">**若要執行腳本:**</span><span class="sxs-lookup"><span data-stu-id="5d884-148">**To run the script:**</span></span>
    
1. <span data-ttu-id="5d884-149">使用 filename 的檔案名尾碼, 將下列文字儲存至 Windows PowerShell 腳本檔案。例如, `SearchEXOOD4B.ps1`。</span><span class="sxs-lookup"><span data-stu-id="5d884-149">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `SearchEXOOD4B.ps1`.</span></span> <span data-ttu-id="5d884-150">將檔案儲存到您在步驟2中儲存使用者清單的相同資料夾。</span><span class="sxs-lookup"><span data-stu-id="5d884-150">Save the file to the same folder where you saved the list of users in Step 2.</span></span>
    
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

2. <span data-ttu-id="5d884-151">開啟 Windows PowerShell, 然後移至您在其中儲存腳本的資料夾和步驟2中的使用者清單。</span><span class="sxs-lookup"><span data-stu-id="5d884-151">Open Windows PowerShell and go to the folder where you saved the script and the list of users from Step 2.</span></span>
    
3. <span data-ttu-id="5d884-152">啟動腳本;例如:</span><span class="sxs-lookup"><span data-stu-id="5d884-152">Start the script; for example:</span></span>
    
    ```
    .\SearchEXOOD4B.ps1
    ```

4. <span data-ttu-id="5d884-153">當系統提示您輸入您的認證時, 請輸入您的電子郵件地址和密碼, 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="5d884-153">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span> 
    
5. <span data-ttu-id="5d884-154">當腳本提示時, 輸入下列資訊。</span><span class="sxs-lookup"><span data-stu-id="5d884-154">Enter following information when prompted by the script.</span></span> <span data-ttu-id="5d884-155">輸入每一條資訊, 然後按**enter**。</span><span class="sxs-lookup"><span data-stu-id="5d884-155">Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="5d884-156">您的 [我的網站] 網域的名稱。</span><span class="sxs-lookup"><span data-stu-id="5d884-156">The name of your MySite domain.</span></span> 
    
    - <span data-ttu-id="5d884-157">包含使用者清單之文字檔的路徑名。</span><span class="sxs-lookup"><span data-stu-id="5d884-157">The pathname of the text file that contains the list of users.</span></span>
    
    - <span data-ttu-id="5d884-158">內容搜尋的名稱。</span><span class="sxs-lookup"><span data-stu-id="5d884-158">A name for the Content Search.</span></span>
    
    - <span data-ttu-id="5d884-159">搜尋查詢 (保留此空白可傳回內容位置中的所有專案)。</span><span class="sxs-lookup"><span data-stu-id="5d884-159">The search query (leave this blank to return all items in the content locations).</span></span>
    
    <span data-ttu-id="5d884-160">腳本會取得每個商務用 OneDrive 網站的 Url, 然後建立並啟動搜尋。</span><span class="sxs-lookup"><span data-stu-id="5d884-160">The script gets the URLs for each OneDrive for Business site and then creates and starts the search.</span></span> <span data-ttu-id="5d884-161">您可以在安全性 & 合規性中心 PowerShell 中執行**new-compliancesearch 指令程式**, 以顯示搜尋統計資料和結果, 或是您可以移至安全性 & 規範中心的 [**內容搜尋**] 頁面, 以查看資訊關於搜尋。</span><span class="sxs-lookup"><span data-stu-id="5d884-161">You can either run the **Get-ComplianceSearch** cmdlet in Security & Compliance Center PowerShell to display the search statistics and results, or you can go to the **Content search** page in the Security & Compliance Center to view information about the search.</span></span> 
