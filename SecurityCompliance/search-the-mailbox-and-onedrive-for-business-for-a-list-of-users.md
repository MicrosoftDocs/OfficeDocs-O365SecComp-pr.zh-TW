---
title: 使用內容搜尋來搜尋信箱與商務用 OneDrive 網站的使用者清單
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/3/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 5f4f8206-2d6a-4cb2-bbc6-7a0698703cc0
description: 本文中使用內容搜尋與指令碼來搜尋信箱和 OneDrive 商務網站的使用者群組。
ms.openlocfilehash: e7f16ec0ca34d9f7f6155cab7e473119de3966cb
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038166"
---
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a><span data-ttu-id="bc05f-103">使用內容搜尋來搜尋信箱與商務用 OneDrive 網站的使用者清單</span><span class="sxs-lookup"><span data-stu-id="bc05f-103">Use Content Search to search the mailbox and OneDrive for Business site for a list of users</span></span>

<span data-ttu-id="bc05f-p101">Office 365 安全性&amp;規範中心提供幾種可讓您以自動化耗時 eDiscovery 相關之工作的 Windows PowerShell cmdlet。目前建立安全性中的 [內容搜尋&amp;規範中心來搜尋 okay 內容位置大量採用時間及準備。建立搜尋，您必須先收集每個 OneDrive for Business 網站的 URL，然後將每個信箱和 O neDrive 商務網站新增至搜尋。在未來版本，這是執行動作安全性變得更容易&amp;規範中心。加上 then，直到您可以使用本文中的指令碼來自動化此程序。此指令碼會提示您的組織的我的網站網域名稱 (例如， **contoso** URL 中https://contoso-my.sharepoint.com)，清單中的使用者電子郵件地址的新內容搜尋和搜尋查詢使用的名稱。指令碼取得 OneDrive 商務 url 的清單中，每位使用者，然後它會建立並啟動搜尋信箱內容搜尋與 OneDrive 商務網站中每個使用者] 清單中，使用您提供搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="bc05f-p101">The Office 365 Security &amp; Compliance Center provides a number of Windows PowerShell cmdlets that let you automate time-consuming eDiscovery-related tasks. Currently, creating a Content Search in the Security &amp; Compliance Center to search a large number of custodian content locations takes time and preparation. Before you create a search, you have to collect the URL for each OneDrive for Business site and then add each mailbox and O neDrive for Business site to the search. In future releases, this will be easier to do in the Security &amp; Compliance Center. Until then, you can use the script in this article to automate this process. This script prompts you for the name of your organization's MySite domain (for example, **contoso** in the URL https://contoso-my.sharepoint.com), a list of user email addresses, the name of the new Content Search, and the search query to use. The script gets the OneDrive for Business URL for each user in the list, and then it creates and starts a Content Search that searches the mailbox and OneDrive for Business site for each user in the list, using the search query that you provide.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="bc05f-111">開始之前</span><span class="sxs-lookup"><span data-stu-id="bc05f-111">Before you begin</span></span>

- <span data-ttu-id="bc05f-112">您必須是安全性 eDiscovery 管理員角色群組的成員&amp;規範中心和步驟 3 中執行指令碼的 SharePoint Online 全域管理員。</span><span class="sxs-lookup"><span data-stu-id="bc05f-112">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center and a SharePoint Online global administrator to run the script in Step 3.</span></span>
    
- <span data-ttu-id="bc05f-p102">請務必儲存您在步驟 2 和步驟 3 中指令碼以相同的資料夾中建立的使用者清單。會將容易執行指令碼。</span><span class="sxs-lookup"><span data-stu-id="bc05f-p102">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder. That will make it easier to run the script.</span></span>
    
- <span data-ttu-id="bc05f-p103">指令碼包括最少的錯誤處理。它的主要目的是要快速又輕鬆地搜尋信箱和 OneDrive 商務網站的每位使用者。</span><span class="sxs-lookup"><span data-stu-id="bc05f-p103">The script includes minimal error handling. It's primary purpose is to quickly and easily search the mailbox and OneDrive for Business site of each user.</span></span>
    
- <span data-ttu-id="bc05f-p104">本主題中所提供的範例指令碼不支援任何 Microsoft 標準支援程式或服務底下。為 IS 提供範例指令碼沒有任何類型的瑕疵擔保。Microsoft 進一步不作所有我[https://go.microsoft.com/fwlink/p/?LinkId=517283](https://go.microsoft.com/fwlink/p/?LinkId=517283)mplied 擔保包括但不限於任何默示擔保售或適合特定用途。與您保持承擔使用或效能的範例指令碼及文件的風險。事件無法在 Microsoft、 其作者，或其他參與建立、 實際執行或指令碼傳遞的任何人對於而概之任何損害皆不 （包括但不限於，遺漏的商務利潤、 業務中斷、 遺失的損害商務資訊或其他金錢遺失） 引起的使用或無法使用的範例指令碼或文件即使 Microsoft 已被告知這類損害的可能性。</span><span class="sxs-lookup"><span data-stu-id="bc05f-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all i[https://go.microsoft.com/fwlink/p/?LinkId=517283](https://go.microsoft.com/fwlink/p/?LinkId=517283)mplied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="bc05f-122">步驟 1：安裝 SharePoint Online 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="bc05f-122">Step 1: Install the SharePoint Online Management Shell</span></span>
<span data-ttu-id="bc05f-123"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="bc05f-123"></span></span>

<span data-ttu-id="bc05f-p105">第一個步驟是安裝 SharePoint Online 管理命令介面。您沒有在此程序，使用命令介面，但因為包含您在步驟 3 中執行的指令碼所需的必要條件安裝方式。這些先決條件允許指令碼與 SharePoint Online 取得 Url onedrive for Business 網站進行通訊。</span><span class="sxs-lookup"><span data-stu-id="bc05f-p105">The first step is to install the SharePoint Online Management Shell. You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3. These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="bc05f-127">移至 [[設定 SharePoint Online 管理命令介面 Windows PowerShell 環境](https://go.microsoft.com/fwlink/p/?LinkID=286318)及執行步驟 1 與步驟 2 以安裝 SharePoint Online 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="bc05f-127">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](https://go.microsoft.com/fwlink/p/?LinkID=286318) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell.</span></span>
  
## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="bc05f-128">步驟 2： 產生使用者的清單</span><span class="sxs-lookup"><span data-stu-id="bc05f-128">Step 2: Generate a list of users</span></span>
<span data-ttu-id="bc05f-129"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="bc05f-129"></span></span>

<span data-ttu-id="bc05f-p106">步驟 3 中的指令碼會建立內容的搜尋來搜尋信箱和 OneDrive 帳戶的使用者清單。您只可以輸入電子郵件地址的文字檔案，或您可以取得的電子郵件地址清單並將其儲存至檔案 （位於相同的資料夾，您將步驟 3 中儲存指令碼） 的 Windows PowerShell 中執行的命令。</span><span class="sxs-lookup"><span data-stu-id="bc05f-p106">The script in Step 3 will create a Content Search to search the mailboxes and OneDrive accounts for a list of users. You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="bc05f-132">以下是您可以取得的組織中的所有使用者的電子郵件地址清單並將其儲存至名為文字檔 runt [Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283)命令`Users.txt`。</span><span class="sxs-lookup"><span data-stu-id="bc05f-132">Here's an [Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283) command that you can runt to get a list of email addresses for all users in your organization and save it to a text file named `Users.txt`.</span></span> 
  
```
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

<span data-ttu-id="bc05f-p107">執行此命令後，請務必開啟檔案並移除包含屬性名稱的標頭`PrimarySmtpAddress`。文字檔案應該只包含電子郵件地址清單和其他人則是 nothing。請確定有無空白資料列之前或之後的電子郵件地址清單。</span><span class="sxs-lookup"><span data-stu-id="bc05f-p107">After you run this command, be sure to open the file and remove the header that contains the property name,  `PrimarySmtpAddress`. The text file should just contain a list of email addresses, and nothing else. Make sure there are no blank rows before or after the list of email addresses.</span></span>
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a><span data-ttu-id="bc05f-136">步驟 3： 執行指令碼，以建立並啟動搜尋</span><span class="sxs-lookup"><span data-stu-id="bc05f-136">Step 3: Run the script to create and start the search</span></span>

<span data-ttu-id="bc05f-p108">當您在此步驟中執行指令碼時，它會提示您下列資訊。請務必在執行指令碼之前已準備好此資訊。</span><span class="sxs-lookup"><span data-stu-id="bc05f-p108">When you run the script in this step, it will prompt you for the following information. Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="bc05f-139">**您的使用者認證**-指令碼會使用您的認證以存取 SharePoint Online 取得 OneDrive for Business Url 並連線至安全性&amp;遠端 PowerShell 與規範中心。</span><span class="sxs-lookup"><span data-stu-id="bc05f-139">**Your user credentials** - The script will use your credentials to access SharePoint Online to get the OneDrive for Business URLs and to connect to the Security &amp; Compliance Center with remote PowerShell.</span></span> 
    
- <span data-ttu-id="bc05f-p109">**我的網站網域的名稱**-我的網站的網域是包含所有 OneDrive for Business 您組織中的網站的網域。例如，如果我的網站網域 URL **https://contoso-my.sharepoint.com**，則要輸入`contoso`當指令碼會提示您輸入 MySite 網域的名稱。</span><span class="sxs-lookup"><span data-stu-id="bc05f-p109">**Name of your MySite domain** - The MySite domain is the domain that contains all the OneDrive for Business sites in your organization. For example, if the URL for your MySite domain is **https://contoso-my.sharepoint.com**, then you would enter  `contoso` when the script prompts you for the name of your MySite domain.</span></span> 
    
- <span data-ttu-id="bc05f-p110">**步驟 2 中的文字檔案的路徑名稱**-您在步驟 2 中建立的文字檔案的路徑名稱。如果將文字檔和指令碼位於相同的資料夾，然後輸入文字檔的名稱。否則請輸入的文字檔案的完整路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="bc05f-p110">**Pathname of the text file from Step 2** - The pathname of the text file that you created in Step 2. If the text file and the script are located in the same folder, then enter the name of the text file. Otherwise, enter the complete pathname for the text file.</span></span> 
    
- <span data-ttu-id="bc05f-145">**內容搜尋的名稱**-將指令碼所建立之內容搜尋的名稱。</span><span class="sxs-lookup"><span data-stu-id="bc05f-145">**Name of the Content Search** - The name of the Content Search that will be created by the script.</span></span> 
    
- <span data-ttu-id="bc05f-p111">建立及執行**搜尋查詢**內容的搜尋搭配使用的搜尋查詢。如需搜尋查詢的詳細資訊，請參閱[關鍵字查詢和搜尋條件的內容搜尋](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="bc05f-p111">**Search query** - The search query that will be used with the Content Search is created and run. For more information about search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>


<span data-ttu-id="bc05f-148">**若要執行指令碼：**</span><span class="sxs-lookup"><span data-stu-id="bc05f-148">**To run the script:**</span></span>
    
1. <span data-ttu-id="bc05f-p112">使用.ps1; filename 尾碼將下列文字儲存到 Windows PowerShell 指令碼檔案例如， `SearchEXOOD4B.ps1`。將檔案儲存到您在步驟 2 中儲存的使用者清單的相同資料夾。</span><span class="sxs-lookup"><span data-stu-id="bc05f-p112">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `SearchEXOOD4B.ps1`. Save the file to the same folder where you saved the list of users in Step 2.</span></span>
    
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

2. <span data-ttu-id="bc05f-151">開啟 Windows PowerShell 並移至您儲存指令碼和使用者清單從步驟 2 的資料夾。</span><span class="sxs-lookup"><span data-stu-id="bc05f-151">Open Windows PowerShell and go to the folder where you saved the script and the list of users from Step 2.</span></span>
    
3. <span data-ttu-id="bc05f-152">啟動指令碼 ；例如：</span><span class="sxs-lookup"><span data-stu-id="bc05f-152">Start the script; for example:</span></span>
    
    ```
    .\SearchEXOOD4B.ps1
    ```

4. <span data-ttu-id="bc05f-153">當系統提示提供認證，請輸入您的電子郵件地址和密碼，並再按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="bc05f-153">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span> 
    
5. <span data-ttu-id="bc05f-p113">輸入下列資訊時提示指令碼。輸入每段資訊，然後按**Enter**鍵。</span><span class="sxs-lookup"><span data-stu-id="bc05f-p113">Enter following information when prompted by the script. Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="bc05f-156">我的網站網域的名稱。</span><span class="sxs-lookup"><span data-stu-id="bc05f-156">The name of your MySite domain.</span></span> 
    
    - <span data-ttu-id="bc05f-157">包含使用者清單的文字檔案路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="bc05f-157">The pathname of the text file that contains the list of users.</span></span>
    
    - <span data-ttu-id="bc05f-158">內容搜尋的名稱。</span><span class="sxs-lookup"><span data-stu-id="bc05f-158">A name for the Content Search.</span></span>
    
    - <span data-ttu-id="bc05f-159">搜尋查詢 （離開此空白以傳回所有項目中的內容位置）。</span><span class="sxs-lookup"><span data-stu-id="bc05f-159">The search query (leave this blank to return all items in the content locations).</span></span>
    
    <span data-ttu-id="bc05f-p114">指令碼的每個 OneDrive for Business 網站取得 Url 然後會建立並啟動搜尋。您可以執行**Get ComplianceSearch**指令程式的安全性及規範中心 PowerShell，以顯示搜尋統計資料及結果，或可以移至 [**內容搜尋**] 頁面上的 [安全性]&amp;規範中心檢視搜尋的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="bc05f-p114">The script gets the URLs for each OneDrive for Business site and then creates and starts the search. You can either run the **Get-ComplianceSearch** cmdlet in Security & Compliance Center PowerShell to display the search statistics and results, or you can go to the **Content search** page in the Security &amp; Compliance Center to view information about the search.</span></span> 
