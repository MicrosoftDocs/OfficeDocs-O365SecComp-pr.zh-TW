---
title: 建立、回報及刪除多個內容搜尋
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/26/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
ms.assetid: 1d463dda-a3b5-4675-95d4-83db19c9c4a3
description: 了解如何自動化建立搜尋和透過 Office 365 安全性的 PowerShell 指令碼執行報告類似的內容搜尋工作&amp;規範中心。
ms.openlocfilehash: c61a62c7b31d24346fd58b7562872a7c45d1c65d
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213233"
---
# <a name="create-report-on-and-delete-multiple-content-searches"></a>建立、回報及刪除多個內容搜尋

 快速建立和報告探索搜尋是通常重要步驟 eDiscovery 與調查時若要瞭解基礎資料的豐富功能和搜尋的品質。若要協助您達成此目的，安全性&amp;規範中心提供一組的自動化耗時內容搜尋工作的 Windows PowerShell cmdlet。這些指令碼提供快速又簡單的方式來建立數個搜尋，然後再執行 [報告可協助您判斷資料有問題的數量的預估的搜尋結果。您也可以使用指令碼來建立不同版本的搜尋來比較每一個所產生的結果。這些指令碼可協助您快速且有效地識別及 cull 您的資料。 
  
## <a name="before-you-begin"></a>開始之前

- 您必須是安全性 eDiscovery 管理員角色群組的成員&amp;規範中心執行本主題中所述的指令碼。 
    
- Onedrive for Business 網站組織可讓您加入至步驟 1 中的 CSV 檔案中收集的 Url 清單，請參閱[建立的組織中的所有 OneDrive 位置清單](https://support.office.com/article/Create-a-list-of-all-OneDrive-locations-in-your-organization-8e200cb2-c768-49cb-88ec-53493e8ad80a)。 
    
- 請務必儲存您在此主題以相同的資料夾中建立的所有檔案。會將容易執行指令碼。
    
- 指令碼包括最少的錯誤處理。其主要用途是快速建立、 報告、 和刪除多個內容搜尋。
    
- 在任何 Microsoft 標準支援程式或服務下，不支援本主題提供的指令碼。範例指令碼係依「現狀」提供，不附帶任何明示或默示的擔保。Microsoft 另外不承擔任何明示或默示的擔保，包括但不限於適售性或適合某特定用途的默示擔保。使用或操作範例指令碼和文件發生的所有風險皆屬於您的責任。Microsoft、其作者以及其他與建置、生產或交付程式碼相關的任何人在任何情況下皆完全不需對任何損失負責任，包括但不限於商業利潤損失、業務中斷、業務資訊損失、或其他錢財損失等因使用或無法使用範例指令碼所發生的損失，即使 Microsoft 曾建議這些損失發生的可能性。
    
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-searches-you-want-to-run"></a>步驟 1： 建立包含您想要執行哪些搜尋的相關資訊的 CSV 檔案

您在此步驟中建立的逗號分隔的值 (CSV) 檔案包含要搜尋每位使用者的資料列。您可以搜尋使用者的 Exchange Online 信箱 （其中包括封存信箱，如果已啟用） 和其 OneDrive for Business 網站。或者您可以搜尋剛信箱或 OneDrive for Business 網站。您也可以搜尋任何網站 SharePoint Online 組織中。您在步驟 3 中執行的指令碼會建立每一列的個別的搜尋 CSV 檔案中。 
  
1. 複製並貼入.txt 檔案使用 [記事本] 中的下列文字。本機電腦上將此檔案儲存至資料夾。您將會儲存其他指令碼，以及此資料夾。
    
    ```
    ExchangeLocation,SharePointLocation,ContentMatchQuery,StartDate,EndDate
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2000,12/31/2005
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2006,12/31/2010
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2011,3/21/2016
    ,https://contoso.sharepoint.com/sites/contoso,,,3/21/2016
    ,https://contoso-my.sharepoint.com/personal/davidl_contoso_onmicrosoft_com,,1/1/2015,
    ,https://contoso-my.sharepoint.com/personal/janets_contoso_onmicrosoft_com,,1/1/2015,
    ```

    第一列或檔案的標頭列列出會使用 （在步驟 3 中的指令碼） 的**新 ComplianceSearch**指令程式來建立新的內容搜尋的參數。每個參數名稱是以逗號分隔。請務必在標題列中沒有任何空格。標頭列] 下方的每一個資料列代表每個搜尋的參數值。請務必 CSV 檔案中的版面配置區資料取代實際資料。 
    
2. 在 Excel 中開啟.txt 檔案並再使用下表中的資訊來編輯每個搜尋資訊的檔案。 
    
    |**參數**|**描述**|
    |:-----|:-----|
    | `ExchangeLocation` <br/> |使用者信箱的 SMTP 地址。  <br/> |
    | `SharePointLocation` <br/> |使用者的 OneDrive for Business 網站或組織中任何網站的 URL 的 URL。OneDrive for Business 網站的 url，請使用此格式： ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com `。例如， `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`。<br/> |
    | `ContentMatchQuery` <br/> |搜尋產品的搜尋查詢。如需建立搜尋查詢的詳細資訊，請參閱[關鍵字查詢和搜尋條件的內容搜尋](keyword-queries-and-search-conditions.md)。<br/> |
    | `StartDate` <br/> |電子郵件、 日期當天或之後一則訊息已接收到收件者或寄件者所傳送。文件上 SharePoint 或 OneDrive for Business 的網站的上次修改日期當天或之後將文件。  <br/> |
    | `EndDate` <br/> |電子郵件的傳送日期當天或之前郵件已傳送的使用者。文件上 SharePoint 或 OneDrive for Business 的網站的上次修改日期當天或之前將文件。  <br/> |
   
3. 儲存為 CSV 檔案的資料夾的 Excel 檔案本機電腦上。您在步驟 3 中建立的指令碼會使用此 CSV 檔案中的資訊來建立搜尋。 
  
## <a name="step-2-connect-to-security--compliance-center-powershell"></a>步驟 2： 連線至安全性 & 規範中心 PowerShell

下一步是連線至安全性的 Windows PowerShell&amp;貴組織的規範中心。
  
1. 使用.ps1; filename 尾碼將下列文字儲存到 Windows PowerShell 指令碼檔案例如， `ConnectSCC.ps1`。將檔案儲存至您在步驟 1 中儲存的 CSV 檔案的相同資料夾中。
    
    ```
    # Get login credentials 
    $UserCredential = Get-Credential 
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
    Import-PSSession $Session -AllowClobber -DisableNameChecking 
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Office 365 Security &amp; Compliance Center)" 
    ```

2. 在您的本機電腦上開啟 Windows PowerShell，移至您在上一個步驟中建立的指令碼所在的資料夾，然後執行指令碼 ；例如：
    
    ```
    .\ConnectSCC.ps1
    ```
  
## <a name="step-3-run-the-script-to-create-and-start-the-searches"></a>步驟 3： 執行指令碼，以建立並啟動搜尋

在此步驟中的指令碼將您在步驟 1 中建立 CSV 檔案中建立的每一列的個別內容搜尋。當您執行此指令碼時，將會提示您兩個值：
  
- **搜尋群組識別碼**此名稱會提供簡便的方式來組織建立 CSV 檔案中搜尋。建立每個搜尋名為搜尋群組識別碼，然後數字會附加至搜尋名稱。例如，如果您輸入**ContosoCase**搜尋群組識別碼，然後搜尋被具名**ContosoCase_1**、 **ContosoCase_2**、 **ContosoCase_3**、 等等。請注意您輸入的名稱會區分大小寫。當您使用搜尋群組識別碼在步驟 4 和步驟 5 中時，您必須如同您在建立時使用的相同的大小寫。 
    
- **CSV 檔案**-您在步驟 1 中建立 CSV 檔案的名稱。請務必包含使用完整的檔案名稱，包括.csv 檔案的副檔名;例如， `ContosoCase.csv`。
    
若要執行指令碼，請執行下列步驟：

1. 使用.ps1; filename 尾碼將下列文字儲存到 Windows PowerShell 指令碼檔案例如， `CreateSearches.ps1`。將檔案儲存至您儲存其他檔案的相同資料夾中。
    
  ```
  # Get the Search Group ID and the location of the CSV input file
  $searchGroup = Read-Host 'Search Group ID'
  $csvFile = Read-Host 'Source CSV file'
    
  # Do a quick check to make sure our group name will not collide with other searches
  $searchCounter = 1
  import-csv $csvFile |
    ForEach-Object{
    
    $searchName = $searchGroup +'_' + $searchCounter
    $search = Get-ComplianceSearch $searchName -EA SilentlyContinue
    if ($search)
    {
        Write-Error "The Search Group ID conflicts with existing searches.  Please choose a search group name and restart the script."
        return
    }
    $searchCounter++
  }
    
  $searchCounter = 1
  import-csv $csvFile |
    ForEach-Object{
    
    # Create the query
    $query = $_.ContentMatchQuery
    if(($_.StartDate -or $_.EndDate))
    {
          # Add the appropriate date restrictions.  NOTE: Using the Date condition property here because it works across Exchange, SharePoint, and OneDrive for Business.
          # For Exchange, the Date condition property maps to the Sent and Received dates; for SharePoint and OneDrive for Business, it maps to Created and Modified dates.
          if($query)
          {
              $query += " AND"
          }
          $query += " ("
          if($_.StartDate)
          {
              $query += "Date >= " + $_.StartDate
          }
          if($_.EndDate)
          {
              if($_.StartDate)
              {
                  $query += " AND "
              }
              $query += "Date <= " + $_.EndDate
          }
          $query += ")"
    }
      
      # -ExchangeLocation can't be set to an empty string, set to null if there's no location.
      $exchangeLocation = $null
      if ( $_.ExchangeLocation)
      {
           $exchangeLocation = $_.ExchangeLocation
      }
    
    # Create and run the search        
    $searchName = $searchGroup +'_' + $searchCounter
    Write-Host "Creating and running search: " $searchName -NoNewline
    $search = New-ComplianceSearch -Name $searchName -ExchangeLocation $exchangeLocation -SharePointLocation $_.SharePointLocation -ContentMatchQuery $query
    
    # Start and wait for each search to complete
    Start-ComplianceSearch $search.Name
    while ((Get-ComplianceSearch $search.Name).Status -ne "Completed")
    {
        Write-Host " ." -NoNewline
        Start-Sleep -s 3
    }
    Write-Host ""
    
    $searchCounter++
  }
  ```

2. 在 Windows PowerShell 中移至您在先前步驟中，儲存指令碼的資料夾，然後執行 [指令碼 ；例如：
    
    ```
    .\CreateSearches.ps1
    ```

3. 在**搜尋群組識別碼**提示中輸入搜尋的群組名稱與按下**Enter**;例如， `ContosoCase`。請記住此名稱會區分大小寫，因此您必須在後續步驟中輸入相同的方式。
    
4. 在**來源 CSV 檔**提示中輸入包含.csv 檔案的副檔名; CSV 檔案的名稱例如， `ContosoCase.csv`。
    
5. 按**Enter**以繼續執行指令碼。 
    
    指令碼會顯示進度的建立和執行搜尋。當指令碼完成時，它會傳回提示。 
    
    ![執行指令碼以建立多個規範搜尋的範例輸出](media/37d59b0d-5f89-4dbc-9e2d-0e88e2ed7b4c.png)
  
## <a name="step-4-run-the-script-to-report-the-search-estimates"></a>步驟 4： 執行指令碼回報搜尋估計

建立搜尋之後下, 一步是執行指令碼會顯示簡單的每個搜尋步驟 3 中所建立的搜尋命中數報告。報告也會包含每個搜尋伺服器與總數拜訪人次及總大小的所有搜尋結果的大小。當您執行報表的指令碼時，將會提示您搜尋群組識別碼及 CSV 檔案名稱如果您想要將報告儲存為 CSV 檔案。
  
1. 使用.ps1; filename 尾碼將下列文字儲存到 Windows PowerShell 指令碼檔案例如， `SearchReport.ps1`。將檔案儲存至您儲存其他檔案的相同資料夾中。
    
  ```
  $searchGroup = Read-Host 'Search Group ID'
  $outputFile = Read-Host 'Enter a file name or file path to save the report to a .csv file. Leave blank to only display the report'
  $searches = Get-ComplianceSearch | ?{$_.Name -clike $searchGroup + "_*"}
  $allSearchStats = @()
  foreach ($partialObj in $searches)
  {
      $search = Get-ComplianceSearch $partialObj.Name
      $sizeMB = [System.Math]::Round($search.Size / 1MB, 2)
      $searchStatus = $search.Status
      if($search.Errors)
      {
          $searchStatus = "Failed"
      }elseif($search.NumFailedSources -gt 0)
      {
          $searchStatus = "Failed Sources"
      }
      $searchStats = New-Object PSObject
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Name -Value $search.Name
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name ContentMatchQuery -Value $search.ContentMatchQuery
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Status -Value $searchStatus
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Items -Value $search.Items
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name "Size" -Value $search.Size
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name "Size(MB)" -Value $sizeMB
      $allSearchStats += $searchStats
  }
  # Calculate the totals
  $allItems = ($allSearchStats | Measure-Object Items -Sum).Sum
  # Convert the total size to MB and round to the nearst 100th
  $allSize = ($allSearchStats | Measure-Object 'Size' -Sum).Sum
  $allSizeMB = [System.Math]::Round($allSize  / 1MB, 2)
  # Get the total successful searches and total of all searches
  $allSuccessCount = ($allSearchStats |?{$_.Status -eq "Completed"}).Count
  $allCount = $allSearchStats.Count
  $allStatus = [string]$allSuccessCount + " of " + [string]$allCount
  # Totals Row
  $totalSearchStats = New-Object PSObject
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Name -Value "Total"
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Status -Value $allStatus
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Items -Value $allItems
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name "Size(MB)" -Value $allSizeMB
  $allSearchStats += $totalSearchStats
  # Just get the columns we're interested in showing
  $allSearchStatsPrime = $allSearchStats | Select-Object Name, Status, Items, "Size(MB)", ContentMatchQuery
  # Print the results to the screen
  $allSearchStatsPrime |ft -AutoSize -Wrap
  # Save the results to a CSV file
  if ($outputFile)
  {
      $allSearchStatsPrime | Export-Csv -Path $outputFile -NoTypeInformation
  }
  ```

2. 在 Windows PowerShell 中移至您在先前步驟中，儲存指令碼的資料夾，然後執行 [指令碼 ；例如：
    
    ```
    .\SearchReport.ps1
    ```

3. 在**搜尋群組識別碼**提示中輸入搜尋的群組名稱與按下**Enter**;例如`ContosoCase`。請記住此名稱會區分大小寫，因此您必須輸入它的相同方式執行您在步驟 3 中執行指令碼時。
    
4. 在**檔案儲存為 CSV 檔案 （只顯示報告保留空白） 報告路徑**提示中輸入檔案名稱的完整檔案名稱路徑 （包括.csv 檔案的副檔名） 如果您想要將報告儲存為 CSV 檔案。CSV 檔案，包括副檔名.csv 檔案的名稱。例如，您可以輸入`ContosoCaseReport.csv`若要將其儲存至目前目錄或您無法輸入`C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv`將它儲存到其他資料夾。您也可以將提示留白以顯示報表，但不是將它儲存到檔案。 
    
5. 按下**輸入**。
    
    指令碼會顯示進度的建立和執行搜尋。當指令碼完成時，會顯示報表。 
    
    ![執行搜尋報告，以顯示搜尋群組的估計](media/3b5f2595-71d5-4a14-9214-fad156c981f8.png)
  
> [!NOTE]
> 如果相同的信箱或網站指定為在 [搜尋] 群組中的多個搜尋的內容位置、 （適用於項目數目及大小總計） 報告中的總結果估計可能包含相同的項目結果。那是因為相同的電子郵件訊息或文件將會計算一次以上是否符合 [搜尋] 群組中的不同搜尋查詢。 
  
## <a name="step-5-run-the-script-to-delete-the-searches"></a>步驟 5： 執行指令碼，以刪除搜尋

您可能會建立大量的搜尋，因為此最後一個指令碼剛方便快速地刪除您在步驟 3 中建立搜尋。像其他的指令碼，以此也會提示您輸入搜尋群組識別碼。當您執行此指令碼時將會刪除所有搜尋中搜尋名稱搜尋群組識別碼。 
  
1. 使用.ps1; filename 尾碼將下列文字儲存到 Windows PowerShell 指令碼檔案例如， `DeleteSearches.ps1`。將檔案儲存至您儲存其他檔案的相同資料夾中。
    
  ```
  # Delete all searches in a search group
  $searchGroup = Read-Host 'Search Group ID'
  Get-ComplianceSearch |
      ForEach-Object{
      # If the name matches the search group name pattern (case sensitive), delete the search
      if ($_.Name -cmatch $searchGroup + "_\d+")
      {
          Write-Host "Deleting search: " $_.Name
          Remove-ComplianceSearch $_.Name -Confirm:$false
      }
  }
  ```

2. 在 Windows PowerShell 中移至您在先前步驟中，儲存指令碼的資料夾，然後執行 [指令碼 ；例如：
    
    ```
    .\DeleteSearches.ps1
    ```

3. 在**搜尋群組識別碼**提示中輸入您要刪除的搜尋的搜尋群組名稱與按下**Enter**;例如， `ContosoCase`。請記住此名稱會區分大小寫，因此您必須輸入它的相同方式執行您在步驟 3 中執行指令碼時。
    
    指令碼會顯示在刪除每個搜尋的名稱。
    
    ![執行指令碼，以刪除搜尋群組中的搜尋](media/9d97b9d6-a539-4d9b-a4e4-e99989144ec7.png)
