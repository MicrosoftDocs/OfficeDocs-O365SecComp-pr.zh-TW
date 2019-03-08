---
title: 在 Office 365 中使用內容搜尋，對目標集合
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
description: 在 Office 365 安全性中使用內容搜尋&amp;合規性中心，以執行已設定目標的集合。 目標的集合表示您確信回應大小寫的項目或特殊權限項目都位於信箱或網站的特定資料夾。 使用本文中的指令碼，以取得資料夾識別碼或您想要搜尋的特定信箱或網站資料夾的路徑。
ms.openlocfilehash: 1a2a104405cdbbbbbeba0bb62e302ae59638be07
ms.sourcegitcommit: 9f38ba72eba0b656e507860ca228726e4199f7ec
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/07/2019
ms.locfileid: "30475713"
---
# <a name="use-content-search-in-office-365-for-targeted-collections"></a><span data-ttu-id="76a26-105">在 Office 365 中使用內容搜尋，對目標集合</span><span class="sxs-lookup"><span data-stu-id="76a26-105">Use Content Search in Office 365 for targeted collections</span></span>

<span data-ttu-id="76a26-106">Office 365 安全性中的內容搜尋功能&amp;合規性中心不提供在 UI 中搜尋特定資料夾中部署 Exchange 信箱或 SharePoint 和 OneDrive for Business 網站直接的方法。</span><span class="sxs-lookup"><span data-stu-id="76a26-106">The Content Search feature in the Office 365 Security &amp; Compliance Center doesn't provide a direct way in the UI to search specific folders in Exchange mailboxes or SharePoint and OneDrive for Business sites.</span></span> <span data-ttu-id="76a26-107">不過，很可能在實際的搜尋查詢語法中指定的資料夾識別碼或路徑來搜尋特定資料夾 （稱為 「*目標集合*）。</span><span class="sxs-lookup"><span data-stu-id="76a26-107">However, it's possible to search specific folders (called a *targeted collection*) by specifying the folder ID or path in the actual search query syntax.</span></span> <span data-ttu-id="76a26-108">當您確信回應大小寫的項目或特殊權限項目會位於特定的信箱或網站資料夾中，使用內容搜尋來執行目標的集合特別有用。</span><span class="sxs-lookup"><span data-stu-id="76a26-108">Using Content Search to perform a targeted collection is useful when you're confident that items responsive to a case or privileged items are located in a specific mailbox or site folder.</span></span> <span data-ttu-id="76a26-109">您可以使用本文中的指令碼，以取得信箱資料夾的資料夾識別碼或資料夾上的 SharePoint 和 OneDrive for Business 網站的路徑。</span><span class="sxs-lookup"><span data-stu-id="76a26-109">You can use the script in this article to obtain the folder ID for mailbox folders or the path for folders on a SharePoint and OneDrive for Business site.</span></span> <span data-ttu-id="76a26-110">然後您可以使用的資料夾識別碼或路徑在搜尋查詢中要傳回的項目位於資料夾中。</span><span class="sxs-lookup"><span data-stu-id="76a26-110">Then you can use the folder ID or path in a search query to return items located in the folder.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="76a26-111">開始之前</span><span class="sxs-lookup"><span data-stu-id="76a26-111">Before you begin</span></span>

- <span data-ttu-id="76a26-112">您必須是安全性中的 eDiscovery 管理員角色群組的成員&amp;合規性中心，以在步驟 1 中執行指令碼。</span><span class="sxs-lookup"><span data-stu-id="76a26-112">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to run the script in Step 1.</span></span> <span data-ttu-id="76a26-113">如需詳細資訊，請參閱[指派 Office 365 安全性中的 eDiscovery 權限&amp;合規性中心](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="76a26-113">For more information, see [Assign eDiscovery permissions in the Office‍ 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
    
    <span data-ttu-id="76a26-114">此外，您必須獲指派 Exchange Online 組織中的 「 郵件收件者角色。</span><span class="sxs-lookup"><span data-stu-id="76a26-114">Additionally, you have to be assigned the Mail Recipients role in your Exchange Online organization.</span></span> <span data-ttu-id="76a26-115">這樣才能執行**Get-mailboxfolderstatistics**指令程式，在 [步驟 1 中的指令碼包含這個功能。</span><span class="sxs-lookup"><span data-stu-id="76a26-115">This is required to run the **Get-MailboxFolderStatistics** cmdlet, which is included in the script in Step 1.</span></span> <span data-ttu-id="76a26-116">根據預設，「 郵件收件者 」 角色被指派給組織管理和收件者管理角色群組在 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="76a26-116">By default, the Mail Recipients role is assigned to the Organization Management and Recipient Management role groups in Exchange Online.</span></span> <span data-ttu-id="76a26-117">如需指派 Exchange Online 中的權限的詳細資訊，請參閱[管理角色群組成員](https://go.microsoft.com/fwlink/p/?linkid=692102)。</span><span class="sxs-lookup"><span data-stu-id="76a26-117">For more information about assigning permissions in Exchange Online, see [Manage role group members](https://go.microsoft.com/fwlink/p/?linkid=692102).</span></span> <span data-ttu-id="76a26-118">您可能也建立自訂角色群組、 指派 「 郵件收件者 」 角色給它，然後再新增需要執行指令碼在步驟 1 中的成員。</span><span class="sxs-lookup"><span data-stu-id="76a26-118">You could also create a custom role group, assign the Mail Recipients role to it, and then add the members who need to run the script in Step 1.</span></span> <span data-ttu-id="76a26-119">如需詳細資訊，請參閱[管理角色群組](https://go.microsoft.com/fwlink/p/?linkid=730688)。</span><span class="sxs-lookup"><span data-stu-id="76a26-119">For more information, see [Manage role groups](https://go.microsoft.com/fwlink/p/?linkid=730688).</span></span>
    
- <span data-ttu-id="76a26-120">每次您在步驟 1 中，執行指令碼會建立新的遠端 PowerShell 工作階段。</span><span class="sxs-lookup"><span data-stu-id="76a26-120">Each time you run the script in Step 1, a new remote PowerShell session is created.</span></span> <span data-ttu-id="76a26-121">因此您可能會用完所有遠端 PowerShell 工作階段提供給您。</span><span class="sxs-lookup"><span data-stu-id="76a26-121">So you could use up all the remote PowerShell sessions available to you.</span></span> <span data-ttu-id="76a26-122">若要避免這種情況，您可以執行下列命令，以中斷連線的作用中的遠端 PowerShell 工作階段。</span><span class="sxs-lookup"><span data-stu-id="76a26-122">To prevent this from happening, you can run the following command to disconnect your active remote PowerShell sessions.</span></span>
    
  ```
  Get-PSSession | Remove-PSSession
  ```

    <span data-ttu-id="76a26-123">如需詳細資訊，請參閱[連線至 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="76a26-123">For more information, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
- <span data-ttu-id="76a26-124">指令碼包含最少的錯誤處理。</span><span class="sxs-lookup"><span data-stu-id="76a26-124">The script includes minimal error handling.</span></span> <span data-ttu-id="76a26-125">指令碼的主要用途是快速顯示信箱資料夾識別碼的清單或網站可以在內容搜尋的搜尋查詢語法中用來執行目標的集合的路徑。</span><span class="sxs-lookup"><span data-stu-id="76a26-125">The primary purpose of the script is to quickly display a list of mailbox folder IDs or site paths that can be used in the search query syntax of a Content Search to perform a targeted collection.</span></span>
    
- <span data-ttu-id="76a26-126">本主題所提供的範例指令碼不支援任何 Microsoft 標準支援程式或服務。</span><span class="sxs-lookup"><span data-stu-id="76a26-126">The sample script provided in this topic isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="76a26-127">以提供範例指令碼不擔保。</span><span class="sxs-lookup"><span data-stu-id="76a26-127">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="76a26-128">Microsoft 進一步不作任何默示的擔保，包括，但不限於任何默示擔保售或適合特定用途。</span><span class="sxs-lookup"><span data-stu-id="76a26-128">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="76a26-129">與您保持承擔使用或效能的範例指令碼和文件的風險。</span><span class="sxs-lookup"><span data-stu-id="76a26-129">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="76a26-130">事件無法在 Microsoft、 其作者，或任何其他參與建立、 實際執行環境或傳遞的指令碼的人對於而概之任何損害皆不 （包括，但不限於遺失的商務利益、 業務中斷、 遺失的損害嗎商業資訊或其他金錢遺失） 即使 Microsoft 已被告知賠償的可能性，承擔使用或無法使用的範例指令碼或文件。</span><span class="sxs-lookup"><span data-stu-id="76a26-130">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a><span data-ttu-id="76a26-131">步驟 1： 執行指令碼，以取得之信箱或網站的資料夾清單</span><span class="sxs-lookup"><span data-stu-id="76a26-131">Step 1: Run the script to get a list of folders for a mailbox or site</span></span>

<span data-ttu-id="76a26-132">您在此第一個步驟中執行的指令碼會傳回清單中的信箱資料夾或 SharePoint 或 OneDrive for Business 資料夾和對應資料夾識別碼或每個資料夾的路徑。</span><span class="sxs-lookup"><span data-stu-id="76a26-132">The script that you run in this first step will return a list of mailbox folders or SharePoint or OneDrive for Business folders, and the corresponding folder ID or path for each folder.</span></span> <span data-ttu-id="76a26-133">當您執行此指令碼時，它會提示您輸入下列資訊。</span><span class="sxs-lookup"><span data-stu-id="76a26-133">When you run this script, it will prompt you for the following information.</span></span>
  
- <span data-ttu-id="76a26-134">**電子郵件地址或網站的 URL**輸入到 Exchange 信箱資料夾和資料夾識別碼的清單傳回 custodian 電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="76a26-134">**Email address or site URL** Type an email address of the custodian to return a list of Exchange mailbox folders and folder IDs.</span></span> <span data-ttu-id="76a26-135">或輸入 SharePoint 網站的 URL 或商務用 OneDrive 網站，可傳回指定網站的路徑清單。</span><span class="sxs-lookup"><span data-stu-id="76a26-135">Or type the URL for a SharePoint site or a OneDrive for Business site to return a list of paths for the specified site.</span></span> <span data-ttu-id="76a26-136">以下為一些範例：</span><span class="sxs-lookup"><span data-stu-id="76a26-136">Here are some examples:</span></span> 
    
  - <span data-ttu-id="76a26-137">**Exchange** -stacig@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="76a26-137">**Exchange** - stacig@contoso.onmicrosoft.com</span></span> 
    
  - <span data-ttu-id="76a26-138">**SharePoint** - https://contoso.sharepoint.com/sites/marketing</span><span class="sxs-lookup"><span data-stu-id="76a26-138">**SharePoint** - https://contoso.sharepoint.com/sites/marketing</span></span> 
    
  - <span data-ttu-id="76a26-139">**商務用 OneDrive** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span><span class="sxs-lookup"><span data-stu-id="76a26-139">**OneDrive for Business** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span></span> 
    
- <span data-ttu-id="76a26-140">**您的使用者認證**-指令碼會使用您的認證來連線至 Exchange Online 和安全性&amp;使用遠端 PowerShell 的合規性中心。</span><span class="sxs-lookup"><span data-stu-id="76a26-140">**Your user credentials** - The script will use your credentials to connect to Exchange Online and the Security &amp; Compliance Center with remote PowerShell.</span></span> <span data-ttu-id="76a26-141">如先前所述，您必須指派適當的權限，才能成功執行此指令碼。</span><span class="sxs-lookup"><span data-stu-id="76a26-141">As previously explained, you have to assigned the appropriate permissions to successfully run this script.</span></span>
    
<span data-ttu-id="76a26-142">若要顯示的信箱資料夾清單或網站 documentlink （路徑） 名稱：</span><span class="sxs-lookup"><span data-stu-id="76a26-142">To display a list of mailbox folders or site documentlink (path) names:</span></span>
  
1. <span data-ttu-id="76a26-143">使用.ps1 檔名尾碼，將下列文字儲存至 Windows PowerShell 指令碼檔案例如， `GetFolderSearchParameters.ps1`。</span><span class="sxs-lookup"><span data-stu-id="76a26-143">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `GetFolderSearchParameters.ps1`.</span></span>
    
  ```
  #########################################################################################################
  # This PowerShell script will prompt you for:                             #
  #    * Admin credentials for a user who can run the Get-MailboxFolderStatistics cmdlet in Exchange    #
  #      Online and who is an eDiscovery Manager in the Security &amp; Compliance Center.           #
  # The script will then:                                           #
  #    * If an email address is supplied: list the folders for the target mailbox.          #
  #    * If a SharePoint or OneDrive for Business site is supplied: list the documentlinks (folder paths) #
  #    * for the site.                                                                                  #
  #    * In both cases, the script supplies the correct search properties (folderid: or documentlink:)  #
  #      appended to the folder ID or documentlink to use in a Content Search.              #
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
              Write-Host "DocumentLink:""$rawUrl"""
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

2. <span data-ttu-id="76a26-144">在您的本機電腦上開啟 Windows PowerShell，並移至您儲存指令碼的資料夾。</span><span class="sxs-lookup"><span data-stu-id="76a26-144">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="76a26-145">執行指令碼。例如：</span><span class="sxs-lookup"><span data-stu-id="76a26-145">Run the script; for example:</span></span>
    
      ```
      .\GetFolderSearchParameters.ps1
      ```

4. <span data-ttu-id="76a26-146">輸入指令碼會提示您輸入的資訊。</span><span class="sxs-lookup"><span data-stu-id="76a26-146">Enter the information that the script prompts you for.</span></span>
    
    <span data-ttu-id="76a26-147">指令碼會顯示一份信箱資料夾或指定之使用者的 [網站] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="76a26-147">The script displays a list of mailbox folders or site folder for the specified user.</span></span> <span data-ttu-id="76a26-148">讓此視窗開啟，讓您可以複製的資料夾識別碼或路徑名稱，並將它在貼到步驟 2 中的搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="76a26-148">Let this window open so that you can copy a folder ID or path name and paste it in to a search query in Step 2.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="76a26-149">而不是在 [電腦] 畫面上顯示的資料夾清單，您可以重新導向至文字檔的指令碼的輸出。</span><span class="sxs-lookup"><span data-stu-id="76a26-149">Instead of displaying a list of folders on the computer screen, you can re-direct the output of the script to a text file.</span></span> <span data-ttu-id="76a26-150">此檔案會儲存至指令碼的所在位置的資料夾。</span><span class="sxs-lookup"><span data-stu-id="76a26-150">This file will be saved to the folder where the script is located.</span></span> <span data-ttu-id="76a26-151">例如，要重新導向的輸出傳送至文字檔的指令碼，在步驟 3 中執行下列命令：`.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt`然後您可以從搜尋查詢中使用的檔案複製的資料夾識別碼或路徑。</span><span class="sxs-lookup"><span data-stu-id="76a26-151">For example, to redirect the script output to a text file, run the following command in Step 3:  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` Then you can copy a folder ID or path from the file to use in a search query.</span></span>
  
### <a name="script-output-for-mailbox-folders"></a><span data-ttu-id="76a26-152">信箱資料夾的指令碼輸出</span><span class="sxs-lookup"><span data-stu-id="76a26-152">Script output for mailbox folders</span></span>

<span data-ttu-id="76a26-153">如果您收到信箱資料夾識別碼，指令碼會使用遠端 PowerShell 連線到 Exchange Online、 執行**Get MailboxFolderStatisics**指令程式，然後顯示 [從指定的信箱資料夾的清單。</span><span class="sxs-lookup"><span data-stu-id="76a26-153">If you're getting mailbox folder IDs, the script connects to Exchange Online by using remote PowerShell, runs the **Get-MailboxFolderStatisics** cmdlet, and then displays the list of the folders from the specified mailbox.</span></span> <span data-ttu-id="76a26-154">信箱中每個資料夾，指令碼會顯示在**FolderPath**行中，[ **FolderQuery** ] 欄中的資料夾識別碼的資料夾名稱。</span><span class="sxs-lookup"><span data-stu-id="76a26-154">For every folder in the mailbox, the script displays the name of the folder in the **FolderPath** column and the folder ID in the **FolderQuery** column.</span></span> <span data-ttu-id="76a26-155">此外，指令碼會將**folderId** （這是信箱屬性的名稱） 的前置詞新增至資料夾識別碼。</span><span class="sxs-lookup"><span data-stu-id="76a26-155">Additionally, the script adds the prefix of **folderId** (which is the name of the mailbox property) to the folder ID.</span></span> <span data-ttu-id="76a26-156">由於**folderid**屬性是可搜尋的屬性，您要使用`folderid:<folderid>`搜尋查詢中搜尋該資料夾的步驟 2 中。</span><span class="sxs-lookup"><span data-stu-id="76a26-156">Because the **folderid** property is a searchable property, you'll use  `folderid:<folderid>` in a search query in Step 2 to search that folder.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="76a26-157">本文中的指令碼包含編碼方式將轉換都會由**Get-mailboxfolderstatistics**會編入搜尋索引的相同 48 個字元格式的 64 個字元的資料夾識別碼值的邏輯。</span><span class="sxs-lookup"><span data-stu-id="76a26-157">The script in this article includes encoding logic that converts the 64-character folder Id values that are returned by **Get-MailboxFolderStatistics** to the same 48-character format that is indexed for search.</span></span> <span data-ttu-id="76a26-158">如果您只要在 PowerShell 中的資料夾識別碼取得 （而不是在本文中執行指令碼） 執行**Get-mailboxfolderstatistics**指令程式，將會失敗的搜尋查詢，會使用該資料夾用戶端識別碼值。</span><span class="sxs-lookup"><span data-stu-id="76a26-158">If you just run the **Get-MailboxFolderStatistics** cmdlet in PowerShell to obtain a folder Id (instead of running the script in this article), a search query that uses that folder Id value will fail.</span></span> <span data-ttu-id="76a26-159">您必須執行指令碼，以在內容搜尋中取得正確格式化資料夾可用的識別碼。</span><span class="sxs-lookup"><span data-stu-id="76a26-159">You have to run the script to get the correctly-formatted folder Ids that can be used in a Content Search.</span></span>
  
<span data-ttu-id="76a26-160">以下是範例傳回信箱資料夾的指令碼的輸出。</span><span class="sxs-lookup"><span data-stu-id="76a26-160">Here's an example of the output returned by the script for mailbox folders.</span></span>
  
![信箱資料夾和傳回的 id 指令碼的資料夾清單的範例](media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
<span data-ttu-id="76a26-162">步驟 2 中的範例會顯示用來搜尋使用者的 [可復原的項目] 資料夾中的清除] 子資料夾的查詢。</span><span class="sxs-lookup"><span data-stu-id="76a26-162">The example in Step 2 shows the query used to search the Purges subfolder in the user's Recoverable Items folder.</span></span>
  
### <a name="script-output-for-site-folders"></a><span data-ttu-id="76a26-163">網站資料夾的指令碼輸出</span><span class="sxs-lookup"><span data-stu-id="76a26-163">Script output for site folders</span></span>

<span data-ttu-id="76a26-164">如果您收到 documentlinks 從 SharePoint 或 OneDrive for Business 網站，指令碼會連接到安全性&amp;，使用遠端 PowerShell 的合規性中心建立新的內容搜尋的搜尋資料夾的網站，然後顯示的清單位於指定的站台的資料夾。</span><span class="sxs-lookup"><span data-stu-id="76a26-164">If you're getting documentlinks from SharePoint or OneDrive for Business sites, the script connects to the Security &amp; Compliance Center using remote PowerShell, creates a new Content Search that searches the site for folders, and then displays a list of the folders located in the specified site.</span></span> <span data-ttu-id="76a26-165">指令碼會顯示每個資料夾的名稱，並將之字首的**路徑**（也就是網站屬性的名稱） 新增至資料夾的 URL。</span><span class="sxs-lookup"><span data-stu-id="76a26-165">The script displays the name of each folder and adds the prefix of **path** (which is the name of the site property) to the folder URL.</span></span> <span data-ttu-id="76a26-166">**Path**屬性為可搜尋的屬性，因為您要使用`path:<path>`搜尋查詢中搜尋該資料夾的步驟 2 中。</span><span class="sxs-lookup"><span data-stu-id="76a26-166">Because the **path** property is a searchable property, you'll use  `path:<path>` in a search query in Step 2 to search that folder.</span></span> 
  
<span data-ttu-id="76a26-167">以下是範例的指令碼的站台資料夾所傳回的輸出。</span><span class="sxs-lookup"><span data-stu-id="76a26-167">Here's an example of the output returned by the script for site folders.</span></span>
  
![指令碼所傳回的站台資料夾 documentlink 名稱的清單的範例](media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a><span data-ttu-id="76a26-169">步驟 2： 使用資料夾識別碼或 documentlink 來執行目標的集合</span><span class="sxs-lookup"><span data-stu-id="76a26-169">Step 2: Use a folder ID or documentlink to perform a targeted collection</span></span>

<span data-ttu-id="76a26-170">您已執行指令碼，以收集資料夾識別碼或 documentlinks 特定使用者的清單之後，下一步] 步驟以移至安全性&amp;合規性中心，並建立新的內容搜尋來搜尋特定的資料夾。</span><span class="sxs-lookup"><span data-stu-id="76a26-170">After you've run the script to collect a list of folder IDs or documentlinks for a specific user, the next step to go to the Security &amp; Compliance Center and create a new Content Search to search a specific folder.</span></span> <span data-ttu-id="76a26-171">您要使用`folderid:<folderid>`或`documentlink:<path>`屬性的搜尋查詢中，您設定內容搜尋關鍵字] 方塊中 （或如果您使用**New-compliancesearch** cmdlet *ContentMatchQuery*參數的值為）。</span><span class="sxs-lookup"><span data-stu-id="76a26-171">You'll use the  `folderid:<folderid>` or  `documentlink:<path>` property in the search query that you configure in the Content Search keyword box (or as the value for the  *ContentMatchQuery*  parameter if you use the **New-ComplianceSearch** cmdlet).</span></span> <span data-ttu-id="76a26-172">您可以合併`folderid`或`documentlink`屬性與其他搜尋參數，或搜尋條件。</span><span class="sxs-lookup"><span data-stu-id="76a26-172">You can combine the  `folderid` or  `documentlink` property with other search parameters or search conditions.</span></span> <span data-ttu-id="76a26-173">如果您只會包括`folderid`或`documentlink`屬性在查詢中的，搜尋會傳回位於指定的資料夾內的所有項目。</span><span class="sxs-lookup"><span data-stu-id="76a26-173">If you only include the  `folderid` or  `documentlink` property in the query, the search will return all items located in the specified folder.</span></span> 
  
1. <span data-ttu-id="76a26-174">請移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="76a26-174">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="76a26-175">登入 Office 365 中，使用的帳戶與您用來執行指令碼在步驟 1 中的認證。</span><span class="sxs-lookup"><span data-stu-id="76a26-175">Sign in to Office 365 using the account and credentials that you used to run the script in Step 1.</span></span>
    
3. <span data-ttu-id="76a26-176">安全性的左窗格中&amp;合規性中心，按一下 [**搜尋&amp;調查** \> **內容搜尋**]，然後按一下 [**新增**![加入圖示](media/O365-MDM-CreatePolicy-AddIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="76a26-176">In the left pane of the Security &amp; Compliance Center, click **Search &amp; investigation** \> **Content search**, and then click **New** ![Add icon](media/O365-MDM-CreatePolicy-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="76a26-177">在 [新增搜尋]\*\*\*\* 頁面上，輸入內容搜尋的名稱。</span><span class="sxs-lookup"><span data-stu-id="76a26-177">On the **New search** page, type a name for the Content Search.</span></span> <span data-ttu-id="76a26-178">此名稱在您的組織中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="76a26-178">This name has to be unique in your organization.</span></span> 
    
5. <span data-ttu-id="76a26-179">在 [**您希望在哪裡我們在哪裡**，執行下列其中一項根據您要搜尋的信箱資料夾或站台資料夾：</span><span class="sxs-lookup"><span data-stu-id="76a26-179">Under **Where do you want us to look**, do one of the following, based on whether you're searching a mailbox folder or a site folder:</span></span>
    
    - <span data-ttu-id="76a26-180">按一下 [**選擇来搜尋的特定信箱**，然後新增您指定當您在步驟 1 中執行指令碼的同一個信箱。</span><span class="sxs-lookup"><span data-stu-id="76a26-180">Click **Choose specific mailboxes to search** and then add the same mailbox that you specified when you ran the script in Step 1.</span></span> 
    
      <span data-ttu-id="76a26-181">或</span><span class="sxs-lookup"><span data-stu-id="76a26-181">Or</span></span>
    
    - <span data-ttu-id="76a26-182">按一下 [**選擇要搜尋的特定網站**新增至搜尋，然後新增您指定當您在步驟 1 中執行指令碼的相同網站 URL。</span><span class="sxs-lookup"><span data-stu-id="76a26-182">Click **Choose specific sites to search** to search and then add the same site URL that you specified when you ran the script in Step 1.</span></span> 
    
6. <span data-ttu-id="76a26-183">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="76a26-183">Click **Next**.</span></span>
    
7. <span data-ttu-id="76a26-184">在**什麼您希望我們要尋找的**頁面上的 [關鍵字] 方塊中，貼上`folderid:<folderid>`或`documentlink:<path>`指令碼在步驟 1 中所傳回的值。</span><span class="sxs-lookup"><span data-stu-id="76a26-184">In the keyword box on the **What do you want us to look for** page, paste the  `folderid:<folderid>` or  `documentlink:<path>` value that was returned by the script in Step 1.</span></span> 
    
    <span data-ttu-id="76a26-185">例如，下列螢幕擷取畫面中的查詢會搜尋使用者的 [可復原的項目] 資料夾中的 [清除] 子資料夾中的任何項目 (值`folderid`在步驟 1 中的螢幕擷取畫面所示的清除] 子資料夾的屬性):</span><span class="sxs-lookup"><span data-stu-id="76a26-185">For example, the query in the following screenshot will search for any item in the Purges subfolder in the user's Recoverable Items folder (the value of the `folderid` property for the Purges subfolder is shown in the screenshot in Step 1):</span></span>
    
    ![貼上 folderid 或至搜尋查詢的 [關鍵字] 方塊中 documentlink](media/84057516-b663-48a4-a78f-8032a8f8da80.png)
  
8. <span data-ttu-id="76a26-187">按一下 [**搜尋**] 以啟動目標的集合的搜尋。</span><span class="sxs-lookup"><span data-stu-id="76a26-187">Click **Search** to start the targeted collection search.</span></span> 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a><span data-ttu-id="76a26-188">對目標集合的搜尋查詢的範例</span><span class="sxs-lookup"><span data-stu-id="76a26-188">Examples of search queries for targeted collections</span></span>

<span data-ttu-id="76a26-189">以下是使用的一些範例`folderid`和`documentlink`搜尋查詢來執行目標的集合中的屬性。</span><span class="sxs-lookup"><span data-stu-id="76a26-189">Here are some examples of using the  `folderid` and  `documentlink` properties in a search query to perform a targeted collection.</span></span> <span data-ttu-id="76a26-190">請注意，用於預留位置`folderid:<folderid>`和`documentlink:<path>`儲存空間。</span><span class="sxs-lookup"><span data-stu-id="76a26-190">Note that placeholders are used for  `folderid:<folderid>` and  `documentlink:<path>` to save space.</span></span> 
  
- <span data-ttu-id="76a26-191">本範例會搜尋三個不同的信箱資料夾。</span><span class="sxs-lookup"><span data-stu-id="76a26-191">This example searches three different mailbox folders.</span></span> <span data-ttu-id="76a26-192">您可以使用類似的查詢語法來搜尋使用者的 [可復原的項目] 資料夾中的隱藏的資料夾。</span><span class="sxs-lookup"><span data-stu-id="76a26-192">You could use similar query syntax to search the hidden folders in a user's Recoverable Items folder.</span></span>
    
  ```
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- <span data-ttu-id="76a26-193">本範例會搜尋信箱資料夾包含精準字詞的項目。</span><span class="sxs-lookup"><span data-stu-id="76a26-193">This example searches a mailbox folder for items that contain an exact phrase.</span></span>
    
  ```
  folderid:<folderid> AND "Contoso financial results"
  ```

- <span data-ttu-id="76a26-194">本範例會搜尋包含標題中的字母 「 NDA 」 的文件的網站資料夾 （和任何子資料夾）。</span><span class="sxs-lookup"><span data-stu-id="76a26-194">This example searches a site folder (and any subfolders) for documents that contain the letters "NDA" in the title.</span></span>
    
  ```
  documentlink:<path> AND filename:nda
  ```

- <span data-ttu-id="76a26-195">本範例會搜尋網站資料夾 （和任何子資料夾） 的文件那里已變更的日期範圍內。</span><span class="sxs-lookup"><span data-stu-id="76a26-195">This example searches a site folder (and any subfolder) for documents there were changed within a date range.</span></span>
    
  ```
  documentlink:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```
  
## <a name="more-information"></a><span data-ttu-id="76a26-196">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="76a26-196">More information</span></span>

<span data-ttu-id="76a26-197">在本文中使用指令碼來執行目標的集合時，請記住下列事項。</span><span class="sxs-lookup"><span data-stu-id="76a26-197">Keep the following things in mind when using the script in this article to perform targeted collections.</span></span>
  
- <span data-ttu-id="76a26-198">指令碼不會從結果中移除任何資料夾。</span><span class="sxs-lookup"><span data-stu-id="76a26-198">The script doesn't remove any folders from the results.</span></span> <span data-ttu-id="76a26-199">讓某些資料夾中所列的結果可能無法 （或傳回零的項目） 因為它們包含系統所產生的內容。</span><span class="sxs-lookup"><span data-stu-id="76a26-199">So some folders listed in the results might be unsearchable (or return zero items) because they contain system-generated content.</span></span>
    
- <span data-ttu-id="76a26-200">此指令碼只會傳回使用者的主要信箱資料夾的資訊。</span><span class="sxs-lookup"><span data-stu-id="76a26-200">This script only returns folder information for the user's primary mailbox.</span></span> <span data-ttu-id="76a26-201">它不會在使用者的封存信箱中傳回資料夾的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="76a26-201">It doesn't return information about folders in the user's archive mailbox.</span></span>
    
- <span data-ttu-id="76a26-202">搜尋信箱資料夾時，只有指定的資料夾時 (識別由其`folderid`屬性) 可供搜尋。</span><span class="sxs-lookup"><span data-stu-id="76a26-202">When searching mailbox folders, only the specified folder (identified by its  `folderid` property) will be searched.</span></span> <span data-ttu-id="76a26-203">無法搜尋的子資料夾。</span><span class="sxs-lookup"><span data-stu-id="76a26-203">Subfolders won't be searched.</span></span> <span data-ttu-id="76a26-204">若要搜尋的子資料夾，您需要使用的資料夾識別碼，針對您想要搜尋的子資料夾。</span><span class="sxs-lookup"><span data-stu-id="76a26-204">To search sub-folders, you need to use the  folder ID for the sub-folder that you want to search.</span></span> 
    
- <span data-ttu-id="76a26-205">搜尋網站資料夾，該資料夾時 (由識別其`documentlink`屬性)，以及將會搜尋所有的子資料夾。</span><span class="sxs-lookup"><span data-stu-id="76a26-205">When searching site folders, the folder (identified by its  `documentlink` property) and all sub-folders will be searched.</span></span> 
    
- <span data-ttu-id="76a26-206">匯出在其中您只指定搜尋結果時`folderid`在搜尋查詢的屬性，您可以選擇先匯出選項，「 不含已無法辨識的格式，如果出版物的所有項目已加密，或因為其他原因而未建立索引 」。</span><span class="sxs-lookup"><span data-stu-id="76a26-206">When exporting the results of a search in which you only specified the `folderid` property in the search query, you can choose the first export option, "All items, excluding ones that have an unrecognized format, are encrypted, or weren't indexed for other reasons."</span></span> <span data-ttu-id="76a26-207">一律會將資料夾中的所有項目匯出不論其索引狀態，因為資料夾識別碼一律編製索引。</span><span class="sxs-lookup"><span data-stu-id="76a26-207">All items in the folder will always be exported regardless of their indexing status because the folder ID is always indexed.</span></span>
