---
title: 使用 Office 365 中的內容搜尋目標集合
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/19/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: e3cbc79c-5e97-43d3-8371-9fbc398cd92e
description: 使用 Office 365 安全性內容搜尋&amp;規範中心來執行目標的集合。目標的集合表示您是有信心回應案例的項目或權限項目都位於特定信箱或站台資料夾。使用本文中的指令碼來取得資料夾 ID 或想要搜尋的特定信箱或站台資料夾的路徑。
ms.openlocfilehash: bb808e38f24ebf09a975b3082ef1dc61bc6344c4
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038296"
---
# <a name="use-content-search-in-office-365-for-targeted-collections"></a>使用 Office 365 中的內容搜尋目標集合

Office 365 安全性內容的搜尋功能&amp;規範中心不提供在 UI 中搜尋特定的資料夾中 Exchange 信箱或 SharePoint 和 OneDrive 商務網站直接的方式。不過，它是可以藉由指定的資料夾識別碼或路徑實際的搜尋查詢語法中搜尋特定的資料夾 （稱為 「 目標的集合）。當您確信回應案例的項目或權限項目都位於特定信箱或站台資料夾，使用內容搜尋執行目標的集合特別有用。您可以使用本文中的指令碼來取得信箱資料夾的資料夾識別碼或商務網站上的 SharePoint 和 OneDrive 資料夾的路徑。然後您可以使用的資料夾識別碼或路徑搜尋查詢中要傳回的項目位於資料夾中。
  
## <a name="before-you-begin"></a>開始之前

- 您必須是安全性 eDiscovery 管理員角色群組的成員&amp;執行指令碼在步驟 1 中的規範中心。如需詳細資訊，請參閱[指派 Office 365 安全性 eDiscovery 權限&amp;規範中心](assign-ediscovery-permissions.md)。
    
    此外，您必須指定給 Exchange Online 組織中的郵件收件者角色。這才可執行**Get-mailboxfolderstatistics 指令**指令程式，它包含在步驟 1 中的指令碼。根據預設，收件者角色指派給組織管理及收件者管理角色群組在 Exchange Online。如需指派 Exchange Online 中的權限的詳細資訊，請參閱[管理角色群組成員](https://go.microsoft.com/fwlink/p/?linkid=692102)。您可能也建立自訂角色群組、 將 Mail Recipients 角色指派給它，然後再新增需要執行指令碼在步驟 1 中的成員。如需詳細資訊，請參閱[管理角色群組](https://go.microsoft.com/fwlink/p/?linkid=730688)。
    
- 每次您在步驟 1 中，執行指令碼會建立新的遠端 PowerShell 工作階段。因此您可以使用 「 所有遠端 PowerShell 工作階段提供給您。若要防止發生這種情況，您可以執行下列命令來中斷連線的作用中的遠端 PowerShell 工作階段。
    
  ```
  Get-PSSession | Remove-PSSession
  ```

    如需詳細資訊，請參閱[使用遠端 PowerShell 連線到 Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=396554)。
    
- 指令碼包括最少的錯誤處理。指令碼的主要用途是搜尋的快速顯示信箱資料夾識別碼的清單或站台可用於執行目標的集合之內容的搜尋查詢語法的路徑。
    
- 本主題中所提供的指令碼範例不支援任何 Microsoft 標準支援程式或服務底下。指令碼範例會為 IS 提供不含任何類型的瑕疵擔保。Microsoft 進一步不作所有默示之的擔保包括但不限於任何默示擔保售或適合特定用途。與您保持承擔使用或效能的範例指令碼及文件的風險。事件無法在 Microsoft、 其作者，或其他參與建立、 實際執行或指令碼傳遞的任何人對於而概之任何損害皆不 （包括但不限於，遺漏的商務利潤、 業務中斷、 遺失的損害商務資訊或其他金錢遺失） 引起的使用或無法使用的範例指令碼或文件即使 Microsoft 已被告知這類損害的可能性。
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a>步驟 1： 執行指令碼來取得信箱或站台的資料夾清單

您在此第一個步驟中執行的指令碼會傳回清單中的信箱資料夾或 SharePoint 或 OneDrive for Business 資料夾和對應的資料夾識別碼或針對每個資料夾的路徑。當您執行此指令碼時，它會提示您下列資訊。
  
- **電子郵件地址或網站的 URL**輸入要傳回的 Exchange 信箱資料夾清單及摺疊識別碼 okay 電子郵件地址。或輸入要傳回的指定網站的路徑清單的 [SharePoint 網站的 URL 或 OneDrive for Business 網站。以下是一些範例： 
    
  - **Exchange** -stacig@contoso.onmicrosoft.com 
    
  - **SharePoint** - https://contoso.sharepoint.com/sites/marketing 
    
  - **OneDrive for Business** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com 
    
- **您的使用者認證**-指令碼會使用您的認證連線至 Exchange Online 與安全性&amp;遠端 PowerShell 與規範中心。如先前所述，您必須指派適當的權限才能順利執行此指令碼。
    
若要顯示的信箱資料夾清單或網站路徑名稱：
  
1. 使用.ps1; filename 尾碼將下列文字儲存到 Windows PowerShell 指令碼檔案例如， `GetFolderSearchParameters.ps1`。
    
  ```
  #########################################################################################################
  # This PowerShell script will prompt you for:                             #
  #    * Admin credentials for a user who can run the Get-MailboxFolderStatistics cmdlet in Exchange    #
  #      Online and who is an eDiscovery Manager in the Security &amp; Compliance Center.           #
  # The script will then:                                           #
  #    * If an email address is supplied: list the folders for the target mailbox.          #
  #    * If a SharePoint or OneDrive for Business site is supplied: list the folder paths for the site. #
  #    * In both cases, the script supplies the correct search properties (folderid: or path:)      #
  #      appeneded to the folder ID or path ID to use in a Content Search.              #
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
  # Authenticate with Exchange Online and the Security &amp; Complaince Center (Exchange Online Protection - EOP)
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
      # Authenticate with the Security &amp; Complaince Center
      if (!$SccSession)
      {
          $SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $credentials -Authentication Basic -AllowRedirection
          Import-PSSession $SccSession -AllowClobber -DisableNameChecking
      }
      # Clean-up, if the the script was aborted, the search we created might not have been deleted.  Try to do so now.
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
          # Create a Complinace Search Action and wait for it to complete. The folders will be listed in the .Results parameter
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

2. 在您的本機電腦上開啟 Windows PowerShell，並移至您儲存指令碼的資料夾。
    
3. 執行指令碼 ；例如：
    
      ```
      .\GetFolderSearchParameters.ps1
      ```

4. 輸入指令碼會提示您輸入的資訊。
    
    指令碼會顯示清單中的信箱資料夾或指定使用者的 [網站] 資料夾。可讓此視窗開啟讓您可以複製資料夾 ID 或路徑名稱並將其中貼到步驟 2 中的搜尋查詢。
    
    > [!TIP]
    > 而不是在 [電腦] 畫面上顯示的資料夾清單，您可以使用重新導向至文字檔的指令碼的輸出。此檔案都會儲存到指令碼所在的資料夾。例如，重新導向指令碼的輸出傳送至的文字檔案，執行下列命令在步驟 3：`.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt`然後您可以從要在搜尋查詢中使用的檔案複製資料夾 ID 或路徑。
  
### <a name="script-output-for-mailbox-folders"></a>信箱資料夾的指令碼輸出

如果您正在快速信箱資料夾識別碼、 指令碼使用遠端 PowerShell 連線到 Exchange Online、 執行**Get MailboxFolderStatisics**指令程式，然後顯示 [從指定的信箱資料夾的清單。針對信箱中每個資料夾，指令碼會顯示在**FolderPath**欄和 [ **FolderQuery** ] 欄中的資料夾識別碼資料夾的名稱。此外，指令碼可將**folderId** （這是信箱屬性的名稱） 的前置詞資料夾識別碼。由於**folderid**屬性是可搜尋的屬性，您將使用`folderid:<folderid>`中搜尋該資料夾的步驟 2 中的搜尋查詢。 
  
以下是範例傳回信箱資料夾的指令碼的輸出。
  
![範例中的信箱資料夾和資料夾傳回的 id 指令碼的清單](media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
步驟 2 中的範例會顯示用來在使用者的 [可復原的項目] 資料夾中搜尋 [清除] 子資料夾的查詢。
  
### <a name="script-output-for-site-folders"></a>網站資料夾的指令碼輸出

如果您收到路徑從 SharePoint 或 OneDrive for Business 的網站、 指令碼連接至 [安全性]&amp;規範中心使用遠端 PowerShell 會建立新的內容搜尋的搜尋資料夾的網站，然後顯示的資料夾清單位在指定站台。指令碼會顯示每個資料夾的名稱，並新增至資料夾的 URL**路徑**（這是網站屬性的名稱） 的前置詞。**Path**屬性是可搜尋的屬性，因為您要使用`path:<path>`中搜尋該資料夾的步驟 2 中的搜尋查詢。 
  
以下是由網站資料夾的指令碼所傳回的輸出的範例。
  
![範例中的指令碼所傳回的網站資料夾的路徑名稱的清單](media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-path-to-perform-a-targeted-collection"></a>步驟 2： 使用工作資料夾識別碼或路徑來執行目標的集合

您是否已執行指令碼，以收集資料夾 Id 或特定使用者的路徑清單之後下, 一個步驟移至 [安全性]&amp;規範中心並建立新的內容搜尋來搜尋特定的資料夾。您要使用`folderid:<folderid>`或`path:<path>`在您設定內容搜尋關鍵字] 方塊中 （或如果您使用**New ComplianceSearch**指令程式*ContentMatchQuery*參數的值為） 搜尋查詢的屬性。您可以合併`folderid`或`path`屬性與其他搜尋參數或搜尋條件。如果您只包含`folderid`或`path`中查詢的屬性，搜尋會傳回位於指定的資料夾內的所有項目。 
  
> [!NOTE]
> 使用`path`搜尋 OneDrive 位置屬性不會傳回搜尋結果中的媒體檔案，例如.png、.tiff、 或使用的.wav 檔。 
  
1. 請移至 [https://protection.office.com](https://protection.office.com)。
    
2. 登入 Office 365 使用的帳戶與您用來執行指令碼在步驟 1 中的認證。
    
3. 在 [安全性] 的左窗格中&amp;規範中心按一下**搜尋&amp;調查** \> **內容搜尋**] 然後按一下 [**新增**![新增圖示](media/O365-MDM-CreatePolicy-AddIcon.gif)。
    
4. 在 [**新的搜尋**] 頁面上輸入內容搜尋的名稱。此名稱必須是唯一的組織中。 
    
5. 下**執行您想我們看起來**，請執行下列其中一個動作根據是否在搜尋信箱資料夾或網站] 資料夾：
    
    - 按一下 [**選擇来搜尋的特定信箱**，然後新增您在步驟 1 中執行指令碼時所指定的相同信箱。 
    
      或
    
    - 按一下 [**選擇要搜尋的特定網站**來搜尋並再新增您在步驟 1 中執行指令碼時所指定的相同網站 URL。 
    
6. 按 [下一步]。
    
7. 在**您想什麼我們要尋找的**] 頁面上的 [關鍵字] 方塊中貼上`folderid:<folderid>`或`path:<path>`指令碼在步驟 1 中所傳回的值。 
    
    例如下列螢幕擷取畫面中的查詢會在使用者的 [可復原的項目] 資料夾中的 [清除] 子資料夾中的任何項目進行搜尋 (值`folderid`在步驟 1 中的螢幕擷取畫面顯示 [清除] 子資料夾的屬性)：
    
    ![貼上 folderid 或 [關鍵字] 方塊中的搜尋查詢中的路徑](media/84057516-b663-48a4-a78f-8032a8f8da80.png)
  
8. 按一下 [**搜尋**] 以啟動目標的集合搜尋。 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a>目標集合的搜尋查詢範例

以下是一些範例使用`folderid`和`path`中執行目標的集合的搜尋查詢的屬性。請注意用於版面配置區`folderid:<folderid>`和`path:<path>`以節省空間。 
  
- 本範例會搜尋三個不同的信箱資料夾。您可以使用類似查詢語法來搜尋使用者的 [可復原的項目] 資料夾中的隱藏的資料夾。
    
  ```
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- 本範例會搜尋信箱資料夾包含在精確對應字詞的項目。
    
  ```
  folderid:<folderid> AND "Contoso financial results"
  ```

- 本範例會搜尋含有標題中的字母"NDA"的文件的網站資料夾 （及任何子資料夾）。
    
  ```
  path:<path> AND filename:nda
  ```

- 此範例會搜尋文件那里已變更的日期範圍內的網站資料夾 （及任何子資料夾）。
    
  ```
  path:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```
  
## <a name="more-information"></a>詳細資訊

使用本文中的指令碼和執行目標集合時請記住下列事項。
  
- 指令碼不會從結果中移除任何資料夾。讓某些資料夾中所列的結果可能是無法搜尋 （或傳回零的項目） 因為它們包含系統產生的內容。
    
- 此指令碼只會傳回使用者的主要信箱資料夾資訊。它不會傳回使用者的封存信箱資料夾的相關資訊。
    
- 搜尋信箱資料夾，只有在指定的資料夾時 (識別由其`folderid`屬性) 拼寫須符合。將不會搜尋子資料夾。若要搜尋的子資料夾，您需要使用`folderid`針對您想要搜尋的子資料夾。 
    
- 搜尋網站資料夾、 資料夾時 (識別由其`path`屬性) 並將搜尋的所有子資料夾。 
    
- 先前所述，您無法使用`path`屬性來搜尋的媒體檔案，例如.png、.tiff、 或使用的.wav 檔位於 OneDrive 位置。使用不同的[站台屬性](keyword-queries-and-search-conditions.md#searchable-site-properties)來搜尋 OneDrive 資料夾中的媒體檔案。 
