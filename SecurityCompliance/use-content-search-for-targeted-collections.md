---
title: 使用 Office 365 中的內容搜尋目標集合
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid: MOE150
ms.assetid: e3cbc79c-5e97-43d3-8371-9fbc398cd92e
description: 使用 Office 365 安全性內容搜尋&amp;規範中心來執行目標的集合。目標的集合表示您是有信心回應案例的項目或權限項目都位於特定信箱或站台資料夾。使用本文中的指令碼來取得資料夾 ID 或想要搜尋的特定信箱或站台資料夾的路徑。
ms.openlocfilehash: c6e837e2f95b4f2ae3e32344f966f096407e360e
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296926"
---
# <a name="use-content-search-in-office-365-for-targeted-collections"></a><span data-ttu-id="12ad7-105">使用 Office 365 中的內容搜尋目標集合</span><span class="sxs-lookup"><span data-stu-id="12ad7-105">Use Content Search in Office 365 for targeted collections</span></span>

<span data-ttu-id="12ad7-p102">Office 365 安全性內容的搜尋功能&amp;規範中心不提供在 UI 中搜尋特定的資料夾中 Exchange 信箱或 SharePoint 和 OneDrive 商務網站直接的方式。不過，它是可以藉由指定的資料夾識別碼或路徑實際的搜尋查詢語法中搜尋特定的資料夾 （稱為 「*目標集合*）。當您確信回應案例的項目或權限項目都位於特定信箱或站台資料夾，使用內容搜尋執行目標的集合特別有用。您可以使用本文中的指令碼來取得信箱資料夾的資料夾識別碼或商務網站上的 SharePoint 和 OneDrive 資料夾的路徑。然後您可以使用的資料夾識別碼或路徑搜尋查詢中要傳回的項目位於資料夾中。</span><span class="sxs-lookup"><span data-stu-id="12ad7-p102">The Content Search feature in the Office 365 Security &amp; Compliance Center doesn't provide a direct way in the UI to search specific folders in Exchange mailboxes or SharePoint and OneDrive for Business sites. However, it's possible to search specific folders (called a *targeted collection*) by specifying the folder ID or path in the actual search query syntax. Using Content Search to perform a targeted collection is useful when you're confident that items responsive to a case or privileged items are located in a specific mailbox or site folder. You can use the script in this article to obtain the folder ID for mailbox folders or the path for folders on a SharePoint and OneDrive for Business site. Then you can use the folder ID or path in a search query to return items located in the folder.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="12ad7-111">開始之前</span><span class="sxs-lookup"><span data-stu-id="12ad7-111">Before you begin</span></span>

- <span data-ttu-id="12ad7-p103">您必須是安全性 eDiscovery 管理員角色群組的成員&amp;執行指令碼在步驟 1 中的規範中心。如需詳細資訊，請參閱[指派 Office 365 安全性 eDiscovery 權限&amp;規範中心](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="12ad7-p103">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to run the script in Step 1. For more information, see [Assign eDiscovery permissions in the Office‍ 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
    
    <span data-ttu-id="12ad7-p104">此外，您必須指定給 Exchange Online 組織中的郵件收件者角色。這才可執行**Get-mailboxfolderstatistics 指令**指令程式，它包含在步驟 1 中的指令碼。根據預設，收件者角色指派給組織管理及收件者管理角色群組在 Exchange Online。如需指派 Exchange Online 中的權限的詳細資訊，請參閱[管理角色群組成員](https://go.microsoft.com/fwlink/p/?linkid=692102)。您可能也建立自訂角色群組、 將 Mail Recipients 角色指派給它，然後再新增需要執行指令碼在步驟 1 中的成員。如需詳細資訊，請參閱[管理角色群組](https://go.microsoft.com/fwlink/p/?linkid=730688)。</span><span class="sxs-lookup"><span data-stu-id="12ad7-p104">Additionally, you have to be assigned the Mail Recipients role in your Exchange Online organization. This is required to run the **Get-MailboxFolderStatistics** cmdlet, which is included in the script in Step 1. By default, the Mail Recipients role is assigned to the Organization Management and Recipient Management role groups in Exchange Online. For more information about assigning permissions in Exchange Online, see [Manage role group members](https://go.microsoft.com/fwlink/p/?linkid=692102). You could also create a custom role group, assign the Mail Recipients role to it, and then add the members who need to run the script in Step 1. For more information, see [Manage role groups](https://go.microsoft.com/fwlink/p/?linkid=730688).</span></span>
    
- <span data-ttu-id="12ad7-p105">每次您在步驟 1 中，執行指令碼會建立新的遠端 PowerShell 工作階段。因此您可以使用 「 所有遠端 PowerShell 工作階段提供給您。若要防止發生這種情況，您可以執行下列命令來中斷連線的作用中的遠端 PowerShell 工作階段。</span><span class="sxs-lookup"><span data-stu-id="12ad7-p105">Each time you run the script in Step 1, a new remote PowerShell session is created. So you could use up all the remote PowerShell sessions available to you. To prevent this from happening, you can run the following command to disconnect your active remote PowerShell sessions.</span></span>
    
  ```
  Get-PSSession | Remove-PSSession
  ```

    <span data-ttu-id="12ad7-123">如需詳細資訊，請參閱[使用遠端 PowerShell 連線到 Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="12ad7-123">For more information, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
- <span data-ttu-id="12ad7-p106">指令碼包括最少的錯誤處理。指令碼的主要用途是搜尋的快速顯示信箱資料夾識別碼的清單或站台可用於執行目標的集合之內容的搜尋查詢語法的路徑。</span><span class="sxs-lookup"><span data-stu-id="12ad7-p106">The script includes minimal error handling. The primary purpose of the script is to quickly display a list of mailbox folder IDs or site paths that can be used in the search query syntax of a Content Search to perform a targeted collection.</span></span>
    
- <span data-ttu-id="12ad7-p107">本主題中所提供的指令碼範例不支援任何 Microsoft 標準支援程式或服務底下。指令碼範例會為 IS 提供不含任何類型的瑕疵擔保。Microsoft 進一步不作所有默示之的擔保包括但不限於任何默示擔保售或適合特定用途。與您保持承擔使用或效能的範例指令碼及文件的風險。事件無法在 Microsoft、 其作者，或其他參與建立、 實際執行或指令碼傳遞的任何人對於而概之任何損害皆不 （包括但不限於，遺漏的商務利潤、 業務中斷、 遺失的損害商務資訊或其他金錢遺失） 引起的使用或無法使用的範例指令碼或文件即使 Microsoft 已被告知這類損害的可能性。</span><span class="sxs-lookup"><span data-stu-id="12ad7-p107">The sample script provided in this topic isn't supported under any Microsoft standard support program or service. The sample script is provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample script and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a><span data-ttu-id="12ad7-131">步驟 1： 執行指令碼來取得信箱或站台的資料夾清單</span><span class="sxs-lookup"><span data-stu-id="12ad7-131">Step 1: Run the script to get a list of folders for a mailbox or site</span></span>

<span data-ttu-id="12ad7-p108">您在此第一個步驟中執行的指令碼會傳回清單中的信箱資料夾或 SharePoint 或 OneDrive for Business 資料夾和對應的資料夾識別碼或針對每個資料夾的路徑。當您執行此指令碼時，它會提示您下列資訊。</span><span class="sxs-lookup"><span data-stu-id="12ad7-p108">The script that you run in this first step will return a list of mailbox folders or SharePoint or OneDrive for Business folders, and the corresponding folder ID or path for each folder. When you run this script, it will prompt you for the following information.</span></span>
  
- <span data-ttu-id="12ad7-p109">**電子郵件地址或網站的 URL**輸入要傳回的 Exchange 信箱資料夾和資料夾識別碼清單 okay 電子郵件地址。或輸入要傳回的指定網站的路徑清單的 [SharePoint 網站的 URL 或 OneDrive for Business 網站。以下是一些範例：</span><span class="sxs-lookup"><span data-stu-id="12ad7-p109">**Email address or site URL** Type an email address of the custodian to return a list of Exchange mailbox folders and folder IDs. Or type the URL for a SharePoint site or a OneDrive for Business site to return a list of paths for the specified site. Here are some examples:</span></span> 
    
  - <span data-ttu-id="12ad7-137">**Exchange** -stacig@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="12ad7-137">**Exchange** - stacig@contoso.onmicrosoft.com</span></span> 
    
  - <span data-ttu-id="12ad7-138">**SharePoint** - https://contoso.sharepoint.com/sites/marketing</span><span class="sxs-lookup"><span data-stu-id="12ad7-138">**SharePoint** - https://contoso.sharepoint.com/sites/marketing</span></span> 
    
  - <span data-ttu-id="12ad7-139">**OneDrive for Business** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span><span class="sxs-lookup"><span data-stu-id="12ad7-139">**OneDrive for Business** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span></span> 
    
- <span data-ttu-id="12ad7-p110">**您的使用者認證**-指令碼會使用您的認證連線至 Exchange Online 與安全性&amp;遠端 PowerShell 與規範中心。如先前所述，您必須指派適當的權限才能順利執行此指令碼。</span><span class="sxs-lookup"><span data-stu-id="12ad7-p110">**Your user credentials** - The script will use your credentials to connect to Exchange Online and the Security &amp; Compliance Center with remote PowerShell. As previously explained, you have to assigned the appropriate permissions to successfully run this script.</span></span>
    
<span data-ttu-id="12ad7-142">若要顯示的信箱資料夾清單或網站路徑名稱：</span><span class="sxs-lookup"><span data-stu-id="12ad7-142">To display a list of mailbox folders or site path names:</span></span>
  
1. <span data-ttu-id="12ad7-143">使用.ps1; filename 尾碼將下列文字儲存到 Windows PowerShell 指令碼檔案例如， `GetFolderSearchParameters.ps1`。</span><span class="sxs-lookup"><span data-stu-id="12ad7-143">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `GetFolderSearchParameters.ps1`.</span></span>
    
  ```
  #########################################################################################################
  # This PowerShell script will prompt you for:                             #
  #    * Admin credentials for a user who can run the Get-MailboxFolderStatistics cmdlet in Exchange    #
  #      Online and who is an eDiscovery Manager in the Security &amp; Compliance Center.           #
  # The script will then:                                           #
  #    * If an email address is supplied: list the folders for the target mailbox.          #
  #    * If a SharePoint or OneDrive for Business site is supplied: list the folder paths for the site. #
  #    * In both cases, the script supplies the correct search properties (folderid: or path:)      #
  #      appended to the folder ID or path ID to use in a Content Search.               #
  # Notes:                                              #
  #    * For SharePoint and OneDrive for Business, the paths are searched recursively; this means the   #
  #      the current folder and all sub-folders are searched.                       #
  #    * For Exchange, only the specified folder will be searched; this means sub-folders in the folder #
  #      will not be searched.  To search sub-folders, you need to use the specify the folder ID for    #
  #      each sub-folder that you want to search.                               #
  #    * For Exchange, only folders in the user's primary mailbox will be returned by the script.       #
  #########################################################################################################
  # Collect the target email address or SharePoint Url
  $addressOrSite = Read-Host "Enter an email address or a URL for a SharePoint or OneDrive for Business site"
  # Authenticate with Exchange Online and the Security &amp; Compliance Center (Exchange Online Protection - EOP)
  if (!$credentials)
  {
      $credentials = Get-Credential
  }
  if ($addressOrSite.IndexOf("@") -ige 0)
  {
      # List the folder Ids for the target mailbox
      $emailAddress = $addressOrSite
      # Authenticate with Exchange Online
      if (!$ExoSession)
      {
          $ExoSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid/ -Credential $credentials -Authentication Basic -AllowRedirection
          Import-PSSession $ExoSession -AllowClobber -DisableNameChecking
      }
      $folderQueries = @()
      $folderStatistics = Get-MailboxFolderStatistics $emailAddress
      foreach ($folderStatistic in $folderStatistics)
      {
          $folderId = $folderStatistic.FolderId;
          $folderPath = $folderStatistic.FolderPath;
          $encoding= [System.Text.Encoding]::GetEncoding("us-ascii")
          $nibbler= $encoding.GetBytes("0123456789ABCDEF");
          $folderIdBytes = [Convert]::FromBase64String($folderId);
          $indexIdBytes = New-Object byte[] 48;
          $indexIdIdx=0;
          $folderIdBytes | select -skip 23 -First 24 | %{$indexIdBytes[$indexIdIdx++]=$nibbler[$_ -shr 4];$indexIdBytes[$indexIdIdx++]=$nibbler[$_ -band 0xF]}
          $folderQuery = "folderid:$($encoding.GetString($indexIdBytes))";
          $folderStat = New-Object PSObject
          Add-Member -InputObject $folderStat -MemberType NoteProperty -Name FolderPath -Value $folderPath
          Add-Member -InputObject $folderStat -MemberType NoteProperty -Name FolderQuery -Value $folderQuery
          $folderQueries += $folderStat
      }
      Write-Host "-----Exchange Folders-----"
      $folderQueries |ft
  }
  elseif ($addressOrSite.IndexOf("http") -ige 0)
  {
      $searchName = "SPFoldersSearch"
      $searchActionName = "SPFoldersSearch_Preview"
      # List the folders for the SharePoint or OneDrive for Business Site
      $siteUrl = $addressOrSite
      # Authenticate with the Security &amp; Compliance Center
      if (!$SccSession)
      {
          $SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $credentials -Authentication Basic -AllowRedirection
          Import-PSSession $SccSession -AllowClobber -DisableNameChecking
      }
      # Clean-up, if the script was aborted, the search we created might not have been deleted.  Try to do so now.
      Remove-ComplianceSearch $searchName -Confirm:$false -ErrorAction 'SilentlyContinue'
      # Create a Content Search against the SharePoint Site or OneDrive for Business site and only search for folders; wait for the search to complete
      $complianceSearch = New-ComplianceSearch -Name $searchName -ContentMatchQuery "contenttype:folder" -SharePointLocation $siteUrl
      Start-ComplianceSearch $searchName
      do{
          Write-host "Waiting for search to complete..."
          Start-Sleep -s 5
          $complianceSearch = Get-ComplianceSearch $searchName
      }while ($complianceSearch.Status -ne 'Completed')
      if ($complianceSearch.Items -gt 0)
      {
          # Create a Compliance Search Action and wait for it to complete. The folders will be listed in the .Results parameter
          $complianceSearchAction = New-ComplianceSearchAction -SearchName $searchName -Preview
          do
          {
              Write-host "Waiting for search action to complete..."
              Start-Sleep -s 5
              $complianceSearchAction = Get-ComplianceSearchAction $searchActionName
          }while ($complianceSearchAction.Status -ne 'Completed')
          # Get the results and print out the folders
          $results = $complianceSearchAction.Results
          $matches = Select-String "Data Link:.+[,}]" -Input $results -AllMatches
          foreach ($match in $matches.Matches)
          {
              $rawUrl = $match.Value
              $rawUrl = $rawUrl -replace "Data Link: " -replace "," -replace "}"
              Write-Host "path:""$rawUrl"""
          }
      }
      else
      {
          Write-Host "No folders were found for $siteUrl"
      }
      Remove-ComplianceSearch $searchName -Confirm:$false -ErrorAction 'SilentlyContinue'
  }
  else
  {
      Write-Error "Couldn't recognize $addressOrSite as an email address or a site URL"
  }
  ```

2. <span data-ttu-id="12ad7-144">在您的本機電腦上開啟 Windows PowerShell，並移至您儲存指令碼的資料夾。</span><span class="sxs-lookup"><span data-stu-id="12ad7-144">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="12ad7-145">執行指令碼 ；例如：</span><span class="sxs-lookup"><span data-stu-id="12ad7-145">Run the script; for example:</span></span>
    
      ```
      .\GetFolderSearchParameters.ps1
      ```

4. <span data-ttu-id="12ad7-146">輸入指令碼會提示您輸入的資訊。</span><span class="sxs-lookup"><span data-stu-id="12ad7-146">Enter the information that the script prompts you for.</span></span>
    
    <span data-ttu-id="12ad7-p111">指令碼會顯示清單中的信箱資料夾或指定使用者的 [網站] 資料夾。可讓此視窗開啟讓您可以複製資料夾 ID 或路徑名稱並將其中貼到步驟 2 中的搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="12ad7-p111">The script displays a list of mailbox folders or site folder for the specified user. Let this window open so that you can copy a folder ID or path name and paste it in to a search query in Step 2.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="12ad7-p112">而不是在 [電腦] 畫面上顯示的資料夾清單，您可以使用重新導向至文字檔的指令碼的輸出。此檔案都會儲存到指令碼所在的資料夾。例如，重新導向指令碼的輸出傳送至的文字檔案，執行下列命令在步驟 3：`.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt`然後您可以從要在搜尋查詢中使用的檔案複製資料夾 ID 或路徑。</span><span class="sxs-lookup"><span data-stu-id="12ad7-p112">Instead of displaying a list of folders on the computer screen, you can re-direct the output of the script to a text file. This file will be saved to the folder where the script is located. For example, to redirect the script output to a text file, run the following command in Step 3:  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` Then you can copy a folder ID or path from the file to use in a search query.</span></span>
  
### <a name="script-output-for-mailbox-folders"></a><span data-ttu-id="12ad7-152">信箱資料夾的指令碼輸出</span><span class="sxs-lookup"><span data-stu-id="12ad7-152">Script output for mailbox folders</span></span>

<span data-ttu-id="12ad7-p113">如果您正在快速信箱資料夾識別碼、 指令碼使用遠端 PowerShell 連線到 Exchange Online、 執行**Get MailboxFolderStatisics**指令程式，然後顯示 [從指定的信箱資料夾的清單。針對信箱中每個資料夾，指令碼會顯示在**FolderPath**欄和 [ **FolderQuery** ] 欄中的資料夾識別碼資料夾的名稱。此外，指令碼可將**folderId** （這是信箱屬性的名稱） 的前置詞資料夾識別碼。由於**folderid**屬性是可搜尋的屬性，您將使用`folderid:<folderid>`中搜尋該資料夾的步驟 2 中的搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="12ad7-p113">If you're getting mailbox folder IDs, the script connects to Exchange Online by using remote PowerShell, runs the **Get-MailboxFolderStatisics** cmdlet, and then displays the list of the folders from the specified mailbox. For every folder in the mailbox, the script displays the name of the folder in the **FolderPath** column and the folder ID in the **FolderQuery** column. Additionally, the script adds the prefix of **folderId** (which is the name of the mailbox property) to the folder ID. Because the **folderid** property is a searchable property, you'll use  `folderid:<folderid>` in a search query in Step 2 to search that folder.</span></span> 
  
<span data-ttu-id="12ad7-157">以下是範例傳回信箱資料夾的指令碼的輸出。</span><span class="sxs-lookup"><span data-stu-id="12ad7-157">Here's an example of the output returned by the script for mailbox folders.</span></span>
  
![範例中的信箱資料夾和資料夾傳回的 id 指令碼的清單](media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
<span data-ttu-id="12ad7-159">步驟 2 中的範例會顯示用來在使用者的 [可復原的項目] 資料夾中搜尋 [清除] 子資料夾的查詢。</span><span class="sxs-lookup"><span data-stu-id="12ad7-159">The example in Step 2 shows the query used to search the Purges subfolder in the user's Recoverable Items folder.</span></span>
  
### <a name="script-output-for-site-folders"></a><span data-ttu-id="12ad7-160">網站資料夾的指令碼輸出</span><span class="sxs-lookup"><span data-stu-id="12ad7-160">Script output for site folders</span></span>

<span data-ttu-id="12ad7-p114">如果您收到路徑從 SharePoint 或 OneDrive for Business 的網站、 指令碼連接至 [安全性]&amp;規範中心使用遠端 PowerShell 會建立新的內容搜尋的搜尋資料夾的網站，然後顯示的資料夾清單位在指定站台。指令碼會顯示每個資料夾的名稱，並新增至資料夾的 URL**路徑**（這是網站屬性的名稱） 的前置詞。**Path**屬性是可搜尋的屬性，因為您要使用`path:<path>`中搜尋該資料夾的步驟 2 中的搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="12ad7-p114">If you're getting paths from SharePoint or OneDrive for Business sites, the script connects to the Security &amp; Compliance Center using remote PowerShell, creates a new Content Search that searches the site for folders, and then displays a list of the folders located in the specified site. The script displays the name of each folder and adds the prefix of **path** (which is the name of the site property) to the folder URL. Because the **path** property is a searchable property, you'll use  `path:<path>` in a search query in Step 2 to search that folder.</span></span> 
  
<span data-ttu-id="12ad7-164">以下是由網站資料夾的指令碼所傳回的輸出的範例。</span><span class="sxs-lookup"><span data-stu-id="12ad7-164">Here's an example of the output returned by the script for site folders.</span></span>
  
![範例中的指令碼所傳回的網站資料夾的路徑名稱的清單](media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-path-to-perform-a-targeted-collection"></a><span data-ttu-id="12ad7-166">步驟 2： 使用工作資料夾識別碼或路徑來執行目標的集合</span><span class="sxs-lookup"><span data-stu-id="12ad7-166">Step 2: Use a folder ID or path to perform a targeted collection</span></span>

<span data-ttu-id="12ad7-p115">您是否已執行指令碼，以收集資料夾 Id 或特定使用者的路徑清單之後下, 一個步驟移至 [安全性]&amp;規範中心並建立新的內容搜尋來搜尋特定的資料夾。您要使用`folderid:<folderid>`或`path:<path>`在您設定內容搜尋關鍵字] 方塊中 （或如果您使用**New ComplianceSearch**指令程式*ContentMatchQuery*參數的值為） 搜尋查詢的屬性。您可以合併`folderid`或`path`屬性與其他搜尋參數或搜尋條件。如果您只包含`folderid`或`path`中查詢的屬性，搜尋會傳回位於指定的資料夾內的所有項目。</span><span class="sxs-lookup"><span data-stu-id="12ad7-p115">After you've run the script to collect a list of folder IDs or paths for a specific user, the next step to go to the Security &amp; Compliance Center and create a new Content Search to search a specific folder. You'll use the  `folderid:<folderid>` or  `path:<path>` property in the search query that you configure in the Content Search keyword box (or as the value for the  *ContentMatchQuery*  parameter if you use the **New-ComplianceSearch** cmdlet). You can combine the  `folderid` or  `path` property with other search parameters or search conditions. If you only include the  `folderid` or  `path` property in the query, the search will return all items located in the specified folder.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="12ad7-171">使用`path`搜尋 OneDrive 位置屬性不會傳回搜尋結果中的媒體檔案，例如.png、.tiff、 或使用的.wav 檔。</span><span class="sxs-lookup"><span data-stu-id="12ad7-171">Using the  `path` property to search OneDrive locations won't return media files, such as .png, .tiff, or .wav files, in the search results.</span></span> 
  
1. <span data-ttu-id="12ad7-172">請移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="12ad7-172">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="12ad7-173">登入 Office 365 使用的帳戶與您用來執行指令碼在步驟 1 中的認證。</span><span class="sxs-lookup"><span data-stu-id="12ad7-173">Sign in to Office 365 using the account and credentials that you used to run the script in Step 1.</span></span>
    
3. <span data-ttu-id="12ad7-174">在 [安全性] 的左窗格中&amp;規範中心按一下**搜尋&amp;調查** \> **內容搜尋**] 然後按一下 [**新增**![新增圖示](media/O365-MDM-CreatePolicy-AddIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="12ad7-174">In the left pane of the Security &amp; Compliance Center, click **Search &amp; investigation** \> **Content search**, and then click **New** ![Add icon](media/O365-MDM-CreatePolicy-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="12ad7-p116">在 [**新的搜尋**] 頁面上輸入內容搜尋的名稱。此名稱必須是唯一的組織中。</span><span class="sxs-lookup"><span data-stu-id="12ad7-p116">On the **New search** page, type a name for the Content Search. This name has to be unique in your organization.</span></span> 
    
5. <span data-ttu-id="12ad7-177">下**執行您想我們看起來**，請執行下列其中一個動作根據您搜尋信箱資料夾或網站] 資料夾：</span><span class="sxs-lookup"><span data-stu-id="12ad7-177">Under **Where do you want us to look**, do one of the following, based on whether you're searching a mailbox folder or a site folder:</span></span>
    
    - <span data-ttu-id="12ad7-178">按一下 [**選擇来搜尋的特定信箱**，然後新增您在步驟 1 中執行指令碼時所指定的相同信箱。</span><span class="sxs-lookup"><span data-stu-id="12ad7-178">Click **Choose specific mailboxes to search** and then add the same mailbox that you specified when you ran the script in Step 1.</span></span> 
    
      <span data-ttu-id="12ad7-179">或</span><span class="sxs-lookup"><span data-stu-id="12ad7-179">Or</span></span>
    
    - <span data-ttu-id="12ad7-180">按一下 [**選擇要搜尋的特定網站**來搜尋並再新增您在步驟 1 中執行指令碼時所指定的相同網站 URL。</span><span class="sxs-lookup"><span data-stu-id="12ad7-180">Click **Choose specific sites to search** to search and then add the same site URL that you specified when you ran the script in Step 1.</span></span> 
    
6. <span data-ttu-id="12ad7-181">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="12ad7-181">Click **Next**.</span></span>
    
7. <span data-ttu-id="12ad7-182">在**您想什麼我們要尋找的**] 頁面上的 [關鍵字] 方塊中貼上`folderid:<folderid>`或`path:<path>`指令碼在步驟 1 中所傳回的值。</span><span class="sxs-lookup"><span data-stu-id="12ad7-182">In the keyword box on the **What do you want us to look for** page, paste the  `folderid:<folderid>` or  `path:<path>` value that was returned by the script in Step 1.</span></span> 
    
    <span data-ttu-id="12ad7-183">例如下列螢幕擷取畫面中的查詢會在使用者的 [可復原的項目] 資料夾中的 [清除] 子資料夾中的任何項目進行搜尋 (值`folderid`在步驟 1 中的螢幕擷取畫面顯示 [清除] 子資料夾的屬性)：</span><span class="sxs-lookup"><span data-stu-id="12ad7-183">For example, the query in the following screenshot will search for any item in the Purges subfolder in the user's Recoverable Items folder (the value of the `folderid` property for the Purges subfolder is shown in the screenshot in Step 1):</span></span>
    
    ![貼上 folderid 或 [關鍵字] 方塊中的搜尋查詢中的路徑](media/84057516-b663-48a4-a78f-8032a8f8da80.png)
  
8. <span data-ttu-id="12ad7-185">按一下 [**搜尋**] 以啟動目標的集合搜尋。</span><span class="sxs-lookup"><span data-stu-id="12ad7-185">Click **Search** to start the targeted collection search.</span></span> 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a><span data-ttu-id="12ad7-186">目標集合的搜尋查詢範例</span><span class="sxs-lookup"><span data-stu-id="12ad7-186">Examples of search queries for targeted collections</span></span>

<span data-ttu-id="12ad7-p117">以下是一些範例使用`folderid`和`path`中執行目標的集合的搜尋查詢的屬性。請注意用於版面配置區`folderid:<folderid>`和`path:<path>`以節省空間。</span><span class="sxs-lookup"><span data-stu-id="12ad7-p117">Here are some examples of using the  `folderid` and  `path` properties in a search query to perform a targeted collection. Note that placeholders are used for  `folderid:<folderid>` and  `path:<path>` to save space.</span></span> 
  
- <span data-ttu-id="12ad7-p118">本範例會搜尋三個不同的信箱資料夾。您可以使用類似查詢語法來搜尋使用者的 [可復原的項目] 資料夾中的隱藏的資料夾。</span><span class="sxs-lookup"><span data-stu-id="12ad7-p118">This example searches three different mailbox folders. You could use similar query syntax to search the hidden folders in a user's Recoverable Items folder.</span></span>
    
  ```
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- <span data-ttu-id="12ad7-191">本範例會搜尋信箱資料夾包含在精確對應字詞的項目。</span><span class="sxs-lookup"><span data-stu-id="12ad7-191">This example searches a mailbox folder for items that contain an exact phrase.</span></span>
    
  ```
  folderid:<folderid> AND "Contoso financial results"
  ```

- <span data-ttu-id="12ad7-192">本範例會搜尋含有標題中的字母"NDA"的文件的網站資料夾 （及任何子資料夾）。</span><span class="sxs-lookup"><span data-stu-id="12ad7-192">This example searches a site folder (and any subfolders) for documents that contain the letters "NDA" in the title.</span></span>
    
  ```
  path:<path> AND filename:nda
  ```

- <span data-ttu-id="12ad7-193">此範例會搜尋文件那里已變更的日期範圍內的網站資料夾 （及任何子資料夾）。</span><span class="sxs-lookup"><span data-stu-id="12ad7-193">This example searches a site folder (and any subfolder) for documents there were changed within a date range.</span></span>
    
  ```
  path:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```
  
## <a name="more-information"></a><span data-ttu-id="12ad7-194">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="12ad7-194">More information</span></span>

<span data-ttu-id="12ad7-195">使用本文中的指令碼來執行目標的集合時請記住下列事項。</span><span class="sxs-lookup"><span data-stu-id="12ad7-195">Keep the following things in mind when using the script in this article to perform targeted collections.</span></span>
  
- <span data-ttu-id="12ad7-p119">指令碼不會從結果中移除任何資料夾。讓某些資料夾中所列的結果可能是無法搜尋 （或傳回零的項目） 因為它們包含系統產生的內容。</span><span class="sxs-lookup"><span data-stu-id="12ad7-p119">The script doesn't remove any folders from the results. So some folders listed in the results might be unsearchable (or return zero items) because they contain system-generated content.</span></span>
    
- <span data-ttu-id="12ad7-p120">此指令碼只會傳回使用者的主要信箱資料夾資訊。它不會傳回使用者的封存信箱資料夾的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="12ad7-p120">This script only returns folder information for the user's primary mailbox. It doesn't return information about folders in the user's archive mailbox.</span></span>
    
- <span data-ttu-id="12ad7-p121">搜尋信箱資料夾，只有在指定的資料夾時 (識別由其`folderid`屬性) 拼寫須符合。將不會搜尋子資料夾。若要搜尋的子資料夾，您需要使用資料夾識別碼為您要搜尋的子資料夾。</span><span class="sxs-lookup"><span data-stu-id="12ad7-p121">When searching mailbox folders, only the specified folder (identified by its  `folderid` property) will be searched. Subfolders won't be searched. To search sub-folders, you need to use the  folder ID for the sub-folder that you want to search.</span></span> 
    
- <span data-ttu-id="12ad7-203">搜尋網站資料夾、 資料夾時 (識別由其`path`屬性) 並將搜尋的所有子資料夾。</span><span class="sxs-lookup"><span data-stu-id="12ad7-203">When searching site folders, the folder (identified by its  `path` property) and all sub-folders will be searched.</span></span> 
    
- <span data-ttu-id="12ad7-p122">先前所述，您無法使用`path`屬性來搜尋的媒體檔案，例如.png、.tiff、 或使用的.wav 檔位於 OneDrive 位置。使用不同的[站台屬性](keyword-queries-and-search-conditions.md#searchable-site-properties)來搜尋 OneDrive 資料夾中的媒體檔案。</span><span class="sxs-lookup"><span data-stu-id="12ad7-p122">As previously stated, you can't use  `path` property to search for media files, such as .png, .tiff, or .wav files, located in OneDrive locations. Use a different [site property](keyword-queries-and-search-conditions.md#searchable-site-properties) to search for media files in OneDrive folders.</span></span> 

- <span data-ttu-id="12ad7-p123">匯出在其中您只指定搜尋結果時`folderid`在搜尋查詢的屬性，您可以選擇第一個匯出選項"排除類具有無法辨識的格式的所有項目已加密或未編製索引的其他原因"。因為資料夾 ID 一律編製索引的資料夾中的所有項目一律要匯出不論其索引狀態為何。</span><span class="sxs-lookup"><span data-stu-id="12ad7-p123">When exporting the results of a search in which you only specified the `folderid` property in the search query, you can choose the first export option, "All items, excluding ones that have an unrecognized format, are encrypted, or weren't indexed for other reasons." All items in the folder will always be exported regardless of their indexing status because the folder ID is always indexed.</span></span>
