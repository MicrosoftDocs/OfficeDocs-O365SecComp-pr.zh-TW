---
title: 建立、回報及刪除多個內容搜尋
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/26/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: 1d463dda-a3b5-4675-95d4-83db19c9c4a3
description: 了解如何自動化建立搜尋和透過 Office 365 安全性的 PowerShell 指令碼執行報告類似的內容搜尋工作&amp;規範中心。
ms.openlocfilehash: 2baa569c28ed5324e6674addeac688b854a65ed8
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526405"
---
# <a name="create-report-on-and-delete-multiple-content-searches"></a><span data-ttu-id="06050-103">建立、回報及刪除多個內容搜尋</span><span class="sxs-lookup"><span data-stu-id="06050-103">Create, report on, and delete multiple Content Searches</span></span>

 <span data-ttu-id="06050-p101">快速建立和報告探索搜尋是通常重要步驟 eDiscovery 與調查時若要瞭解基礎資料的豐富功能和搜尋的品質。若要協助您達成此目的，安全性&amp;規範中心提供一組的自動化耗時內容搜尋工作的 Windows PowerShell cmdlet。這些指令碼提供快速又簡單的方式來建立數個搜尋，然後再執行 [報告可協助您判斷資料有問題的數量的預估的搜尋結果。您也可以使用指令碼來建立不同版本的搜尋來比較每一個所產生的結果。這些指令碼可協助您快速且有效地識別及 cull 您的資料。</span><span class="sxs-lookup"><span data-stu-id="06050-p101">Quickly creating and reporting discovery searches is often an important step in eDiscovery and investigations when you're trying to learn about the underlying data, and the richness and quality of your searches. To help you do this, the Security &amp; Compliance Center offers a set of Windows PowerShell cmdlets to automate time-consuming Content Search tasks. These scripts provide a quick and easy way to create a number of searches, and then run reports of the estimated search results that can help you determine the quantity of data in question. You can also use the scripts to create different versions of searches to compare the results each one produces. These scripts can help you to quickly and efficiently identify and cull your data.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="06050-109">開始之前</span><span class="sxs-lookup"><span data-stu-id="06050-109">Before you begin</span></span>

- <span data-ttu-id="06050-110">您必須是安全性 eDiscovery 管理員角色群組的成員&amp;規範中心執行本主題中所述的指令碼。</span><span class="sxs-lookup"><span data-stu-id="06050-110">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to run the scripts that are described in this topic.</span></span> 
    
- <span data-ttu-id="06050-111">Onedrive for Business 網站組織可讓您加入至步驟 1 中的 CSV 檔案中收集的 Url 清單，請參閱[建立的組織中的所有 OneDrive 位置清單](https://support.office.com/article/Create-a-list-of-all-OneDrive-locations-in-your-organization-8e200cb2-c768-49cb-88ec-53493e8ad80a)。</span><span class="sxs-lookup"><span data-stu-id="06050-111">To collect a list of the URLs for the OneDrive for Business sites in your organization that you can add to the CSV file in Step 1, see [Create a list of all OneDrive locations in your organization](https://support.office.com/article/Create-a-list-of-all-OneDrive-locations-in-your-organization-8e200cb2-c768-49cb-88ec-53493e8ad80a).</span></span> 
    
- <span data-ttu-id="06050-p102">請務必儲存您在此主題以相同的資料夾中建立的所有檔案。會將容易執行指令碼。</span><span class="sxs-lookup"><span data-stu-id="06050-p102">Be sure to save all the files that you create in this topic to the same folder. That will make it easier to run the scripts.</span></span>
    
- <span data-ttu-id="06050-p103">指令碼包括最少的錯誤處理。其主要用途是快速建立、 報告、 和刪除多個內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="06050-p103">The scripts include minimal error handling. Their primary purpose is to quickly create, report on, and delete multiple Content Searches.</span></span>
    
- <span data-ttu-id="06050-p104">本主題中所提供的範例指令碼不支援任何 Microsoft 標準支援程式或服務底下。為 IS 提供範例指令碼沒有任何類型的瑕疵擔保。Microsoft 進一步不作所有默示之的擔保包括但不限於任何默示擔保售或適合特定用途。與您保持承擔使用或效能的範例指令碼及文件的風險。事件無法在 Microsoft、 其作者，或其他參與建立、 實際執行或指令碼傳遞的任何人對於而概之任何損害皆不 （包括但不限於，遺漏的商務利潤、 業務中斷、 遺失的損害商務資訊或其他金錢遺失） 引起的使用或無法使用的範例指令碼或文件即使 Microsoft 已被告知這類損害的可能性。</span><span class="sxs-lookup"><span data-stu-id="06050-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-searches-you-want-to-run"></a><span data-ttu-id="06050-121">步驟 1： 建立包含您想要執行哪些搜尋的相關資訊的 CSV 檔案</span><span class="sxs-lookup"><span data-stu-id="06050-121">Step 1: Create a CSV file that contains information about the searches you want to run</span></span>

<span data-ttu-id="06050-p105">您在此步驟中建立的逗號分隔的值 (CSV) 檔案包含要搜尋每位使用者的資料列。您可以搜尋使用者的 Exchange Online 信箱 （其中包括封存信箱，如果已啟用） 和其 OneDrive for Business 網站。或者您可以搜尋剛信箱或 OneDrive for Business 網站。您也可以搜尋任何網站 SharePoint Online 組織中。您在步驟 3 中執行的指令碼會建立每一列的個別的搜尋 CSV 檔案中。</span><span class="sxs-lookup"><span data-stu-id="06050-p105">The comma separated value (CSV) file that you create in this step contains a row for each user that want to search. You can search the user's Exchange Online mailbox (which includes the archive mailbox, if it's enabled) and their OneDrive for Business site. Or you can search just the mailbox or the OneDrive for Business site. You can also search any site in your SharePoint Online organization. The script that you run in Step 3 will create a separate search for each row in the CSV file.</span></span> 
  
1. <span data-ttu-id="06050-p106">複製並貼入.txt 檔案使用 [記事本] 中的下列文字。本機電腦上將此檔案儲存至資料夾。您將會儲存其他指令碼，以及此資料夾。</span><span class="sxs-lookup"><span data-stu-id="06050-p106">Copy and paste the following text into a .txt file using NotePad. Save this file to a folder on your local computer. You'll save the other scripts to this folder as well.</span></span>
    
    ```
    ExchangeLocation,SharePointLocation,ContentMatchQuery,StartDate,EndDate
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2000,12/31/2005
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2006,12/31/2010
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2011,3/21/2016
    ,https://contoso.sharepoint.com/sites/contoso,,,3/21/2016
    ,https://contoso-my.sharepoint.com/personal/davidl_contoso_onmicrosoft_com,,1/1/2015,
    ,https://contoso-my.sharepoint.com/personal/janets_contoso_onmicrosoft_com,,1/1/2015,
    ```

    <span data-ttu-id="06050-p107">第一列或檔案的標頭列列出會使用 （在步驟 3 中的指令碼） 的**新 ComplianceSearch**指令程式來建立新的內容搜尋的參數。每個參數名稱是以逗號分隔。請務必在標題列中沒有任何空格。標頭列] 下方的每一個資料列代表每個搜尋的參數值。請務必 CSV 檔案中的版面配置區資料取代實際資料。</span><span class="sxs-lookup"><span data-stu-id="06050-p107">The first row, or header row, of the file lists the parameters that will be used by **New-ComplianceSearch** cmdlet (in the script in Step 3) to create a new Content Searches. Each parameter name is separated by a comma. Make sure there aren't any spaces in the header row. Each row under the header row represents the parameter values for each search. Be sure to replace the placeholder data in the CSV file with your actual data.</span></span> 
    
2. <span data-ttu-id="06050-135">在 Excel 中開啟.txt 檔案並再使用下表中的資訊來編輯每個搜尋資訊的檔案。</span><span class="sxs-lookup"><span data-stu-id="06050-135">Open the .txt file in Excel, and then use the information in the following table to edit the file with information for each search.</span></span> 
    
    |<span data-ttu-id="06050-136">**參數**</span><span class="sxs-lookup"><span data-stu-id="06050-136">**Parameter**</span></span>|<span data-ttu-id="06050-137">**描述**</span><span class="sxs-lookup"><span data-stu-id="06050-137">**Description**</span></span>|
    |:-----|:-----|
    | `ExchangeLocation` <br/> |<span data-ttu-id="06050-138">使用者信箱的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="06050-138">The SMTP address of the user's mailbox.</span></span>  <br/> |
    | `SharePointLocation` <br/> |<span data-ttu-id="06050-p108">使用者的 OneDrive for Business 網站或組織中任何網站的 URL 的 URL。OneDrive for Business 網站的 url，請使用此格式： ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com `。例如， `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`。</span><span class="sxs-lookup"><span data-stu-id="06050-p108">The URL for the user's OneDrive for Business site or the URL for any site in your organization. For the URL for OneDrive for Business sites, use this format: ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com `. For example,  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`.  </span></span><br/> |
    | `ContentMatchQuery` <br/> |<span data-ttu-id="06050-p109">搜尋產品的搜尋查詢。如需建立搜尋查詢的詳細資訊，請參閱[關鍵字查詢和搜尋條件的內容搜尋](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="06050-p109">The search query for the search. For more information about creating a search query, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).  </span></span><br/> |
    | `StartDate` <br/> |<span data-ttu-id="06050-p110">電子郵件、 日期當天或之後一則訊息已接收到收件者或寄件者所傳送。文件上 SharePoint 或 OneDrive for Business 的網站的上次修改日期當天或之後將文件。</span><span class="sxs-lookup"><span data-stu-id="06050-p110">For email, the date on or after a message was received by a recipient or sent by the sender. For documents on SharePoint or OneDrive for Business sites, the date on or after a document was last modified.</span></span>  <br/> |
    | `EndDate` <br/> |<span data-ttu-id="06050-p111">電子郵件的傳送日期當天或之前郵件已傳送的使用者。文件上 SharePoint 或 OneDrive for Business 的網站的上次修改日期當天或之前將文件。</span><span class="sxs-lookup"><span data-stu-id="06050-p111">For email, the date on or before a message was sent by a sent by the user. For documents on SharePoint or OneDrive for Business sites, the date on or before a document was last modified.</span></span>  <br/> |
   
3. <span data-ttu-id="06050-p112">儲存為 CSV 檔案的資料夾的 Excel 檔案本機電腦上。您在步驟 3 中建立的指令碼會使用此 CSV 檔案中的資訊來建立搜尋。</span><span class="sxs-lookup"><span data-stu-id="06050-p112">Save the Excel file as a CSV file to a folder on your local computer. The script that you create in Step 3 will use the information in this CSV file to create the searches.</span></span> 
  
## <a name="step-2-connect-to-security--compliance-center-powershell"></a><span data-ttu-id="06050-150">步驟 2： 連線至安全性與規範中心 PowerShell</span><span class="sxs-lookup"><span data-stu-id="06050-150">Step 2: Connect to Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="06050-151">下一步是連線至安全性的 Windows PowerShell&amp;貴組織的規範中心。</span><span class="sxs-lookup"><span data-stu-id="06050-151">The next step is to connect Windows PowerShell to the Security &amp; Compliance Center for your organization.</span></span>
  
1. <span data-ttu-id="06050-p113">使用.ps1; filename 尾碼將下列文字儲存到 Windows PowerShell 指令碼檔案例如， `ConnectSCC.ps1`。將檔案儲存至您在步驟 1 中儲存的 CSV 檔案的相同資料夾中。</span><span class="sxs-lookup"><span data-stu-id="06050-p113">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `ConnectSCC.ps1`. Save the file to the same folder that you saved the CSV file to in Step 1.</span></span>
    
    ```
    # Get login credentials 
    $UserCredential = Get-Credential 
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
    Import-PSSession $Session -AllowClobber -DisableNameChecking 
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Office 365 Security &amp; Compliance Center)" 
    ```

2. <span data-ttu-id="06050-154">在您的本機電腦上開啟 Windows PowerShell，移至您在上一個步驟中建立的指令碼所在的資料夾，然後執行指令碼 ；例如：</span><span class="sxs-lookup"><span data-stu-id="06050-154">On your local computer, open Windows PowerShell, go to the folder where the script that you created in the previous step is located, and then run the script; for example:</span></span>
    
    ```
    .\ConnectSCC.ps1
    ```
  
## <a name="step-3-run-the-script-to-create-and-start-the-searches"></a><span data-ttu-id="06050-155">步驟 3： 執行指令碼，以建立並啟動搜尋</span><span class="sxs-lookup"><span data-stu-id="06050-155">Step 3: Run the script to create and start the searches</span></span>

<span data-ttu-id="06050-p114">在此步驟中的指令碼將您在步驟 1 中建立 CSV 檔案中建立的每一列的個別內容搜尋。當您執行此指令碼時，將會提示您兩個值：</span><span class="sxs-lookup"><span data-stu-id="06050-p114">The script in this step will create a separate Content Search for each row in the CSV file that you created in Step 1. When you run this script, you'll be prompted for two values:</span></span>
  
- <span data-ttu-id="06050-p115">**搜尋群組識別碼**此名稱會提供簡便的方式來組織建立 CSV 檔案中搜尋。建立每個搜尋名為搜尋群組識別碼，然後數字會附加至搜尋名稱。例如，如果您輸入**ContosoCase**搜尋群組識別碼，然後搜尋被具名**ContosoCase_1**、 **ContosoCase_2**、 **ContosoCase_3**、 等等。請注意您輸入的名稱會區分大小寫。當您使用搜尋群組識別碼在步驟 4 和步驟 5 中時，您必須如同您在建立時使用的相同的大小寫。</span><span class="sxs-lookup"><span data-stu-id="06050-p115">**Search Group ID** - This name provides an easy way to organize the searches that are created from the CSV file. Each search that's created is named with the Search Group ID, and then a number is appended to the search name. For example, if you enter **ContosoCase** for the Search Group ID, then the searches are named **ContosoCase_1**, **ContosoCase_2**, **ContosoCase_3**, and so on. Note that the name you type is case sensitive. When you use the Search Group ID in Step 4 and Step 5, you have to use the same case as you did when you created it.</span></span> 
    
- <span data-ttu-id="06050-p116">**CSV 檔案**-您在步驟 1 中建立 CSV 檔案的名稱。請務必包含使用完整的檔案名稱，包括.csv 檔案的副檔名;例如， `ContosoCase.csv`。</span><span class="sxs-lookup"><span data-stu-id="06050-p116">**CSV file** - The name of the CSV file that you created in Step 1. Be sure to include the use the full filename, include the .csv file extension; for example,  `ContosoCase.csv`.</span></span>
    
<span data-ttu-id="06050-165">若要執行指令碼，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="06050-165">To run the script:</span></span>

1. <span data-ttu-id="06050-p117">使用.ps1; filename 尾碼將下列文字儲存到 Windows PowerShell 指令碼檔案例如， `CreateSearches.ps1`。將檔案儲存至您儲存其他檔案的相同資料夾中。</span><span class="sxs-lookup"><span data-stu-id="06050-p117">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CreateSearches.ps1`. Save the file to the same folder where you saved the other files.</span></span>
    
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

2. <span data-ttu-id="06050-168">在 Windows PowerShell 中移至您在先前步驟中，儲存指令碼的資料夾，然後執行 [指令碼 ；例如：</span><span class="sxs-lookup"><span data-stu-id="06050-168">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>
    
    ```
    .\CreateSearches.ps1
    ```

3. <span data-ttu-id="06050-p118">在**搜尋群組識別碼**提示中輸入搜尋的群組名稱與按下**Enter**;例如， `ContosoCase`。請記住此名稱會區分大小寫，因此您必須在後續步驟中輸入相同的方式。</span><span class="sxs-lookup"><span data-stu-id="06050-p118">At the **Search Group ID** prompt, type a search group name, and then press **Enter**; for example,  `ContosoCase`. Remember that this name is case sensitive, so you'll have to type it the same way in the subsequent steps.</span></span>
    
4. <span data-ttu-id="06050-171">在**來源 CSV 檔**提示中輸入包含.csv 檔案的副檔名; CSV 檔案的名稱例如， `ContosoCase.csv`。</span><span class="sxs-lookup"><span data-stu-id="06050-171">At the **Source CSV file** prompt, type the name of the CSV file, including the .csv file extension; for example,  `ContosoCase.csv`.</span></span>
    
5. <span data-ttu-id="06050-172">按**Enter**以繼續執行指令碼。</span><span class="sxs-lookup"><span data-stu-id="06050-172">Press **Enter** to continue running the script.</span></span> 
    
    <span data-ttu-id="06050-p119">指令碼會顯示進度的建立和執行搜尋。當指令碼完成時，它會傳回提示。</span><span class="sxs-lookup"><span data-stu-id="06050-p119">The script displays the progress of creating and running the searches. When the script is complete, it returns to the prompt.</span></span> 
    
    ![執行指令碼以建立多個規範搜尋的範例輸出](media/37d59b0d-5f89-4dbc-9e2d-0e88e2ed7b4c.png)
  
## <a name="step-4-run-the-script-to-report-the-search-estimates"></a><span data-ttu-id="06050-176">步驟 4： 執行指令碼回報搜尋估計</span><span class="sxs-lookup"><span data-stu-id="06050-176">Step 4: Run the script to report the search estimates</span></span>

<span data-ttu-id="06050-p120">建立搜尋之後下, 一步是執行指令碼會顯示簡單的每個搜尋步驟 3 中所建立的搜尋命中數報告。報告也會包含每個搜尋伺服器與總數拜訪人次及總大小的所有搜尋結果的大小。當您執行報表的指令碼時，將會提示您搜尋群組識別碼及 CSV 檔案名稱如果您想要將報告儲存為 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="06050-p120">After you create the searches, the next step is to run a script that displays a simple report of the number of search hits for each search that was created in Step 3. The report also includes the size of results for each search, and the total number of hits and total size of all searches. When you run the reporting script, you'll be prompted for the Search Group ID, and a CSV filename if you want to save the report to a CSV file.</span></span>
  
1. <span data-ttu-id="06050-p121">使用.ps1; filename 尾碼將下列文字儲存到 Windows PowerShell 指令碼檔案例如， `SearchReport.ps1`。將檔案儲存至您儲存其他檔案的相同資料夾中。</span><span class="sxs-lookup"><span data-stu-id="06050-p121">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `SearchReport.ps1`. Save the file to the same folder where you saved the other files.</span></span>
    
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

2. <span data-ttu-id="06050-182">在 Windows PowerShell 中移至您在先前步驟中，儲存指令碼的資料夾，然後執行 [指令碼 ；例如：</span><span class="sxs-lookup"><span data-stu-id="06050-182">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>
    
    ```
    .\SearchReport.ps1
    ```

3. <span data-ttu-id="06050-p122">在**搜尋群組識別碼**提示中輸入搜尋的群組名稱與按下**Enter**;例如`ContosoCase`。請記住此名稱會區分大小寫，因此您必須輸入它的相同方式執行您在步驟 3 中執行指令碼時。</span><span class="sxs-lookup"><span data-stu-id="06050-p122">At the **Search Group ID** prompt, type a search group name, and then press **Enter**; for example  `ContosoCase`. Remember that this name is case sensitive, so you'll have to type it the same way you did when you ran the script in Step 3.</span></span>
    
4. <span data-ttu-id="06050-p123">在**檔案儲存為 CSV 檔案 （只顯示報告保留空白） 報告路徑**提示中輸入檔案名稱的完整檔案名稱路徑 （包括.csv 檔案的副檔名） 如果您想要將報告儲存為 CSV 檔案。CSV 檔案，包括副檔名.csv 檔案的名稱。例如，您可以輸入`ContosoCaseReport.csv`若要將其儲存至目前目錄或您無法輸入`C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv`將它儲存到其他資料夾。您也可以將提示留白以顯示報表，但不是將它儲存到檔案。</span><span class="sxs-lookup"><span data-stu-id="06050-p123">At the **File path to save the report to a CSV file (leave blank to just display the report)** prompt, type a file name of complete filename path (including the .csv file extension) if you want to save the report to a CSV file. name of the CSV file, including the .csv file extension. For example, you could type  `ContosoCaseReport.csv` to save it to the current directory or you could type  `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` to save it to a different folder. You can also leave the prompt blank to display the report but not save it to a file.</span></span> 
    
5. <span data-ttu-id="06050-189">按下**輸入**。</span><span class="sxs-lookup"><span data-stu-id="06050-189">Press **Enter**.</span></span>
    
    <span data-ttu-id="06050-p124">指令碼會顯示進度的建立和執行搜尋。當指令碼完成時，會顯示報表。</span><span class="sxs-lookup"><span data-stu-id="06050-p124">The script displays the progress of creating and running the searches. When the script is complete, the report is displayed.</span></span> 
    
    ![執行搜尋報告，以顯示搜尋群組的估計](media/3b5f2595-71d5-4a14-9214-fad156c981f8.png)
  
> [!NOTE]
> <span data-ttu-id="06050-p125">如果相同的信箱或網站指定為在 [搜尋] 群組中的多個搜尋的內容位置、 （適用於項目數目及大小總計） 報告中的總結果估計可能包含相同的項目結果。那是因為相同的電子郵件訊息或文件將會計算一次以上是否符合 [搜尋] 群組中的不同搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="06050-p125">If the same mailbox or site is specified as a content location in more than one search in a search group, the total results estimate in the report (for both the number of items and the total size) might include results for the same items. That's because the same email message or document will be counted more than once if it matches the query for different searches in the search group.</span></span> 
  
## <a name="step-5-run-the-script-to-delete-the-searches"></a><span data-ttu-id="06050-195">步驟 5： 執行指令碼，以刪除搜尋</span><span class="sxs-lookup"><span data-stu-id="06050-195">Step 5: Run the script to delete the searches</span></span>

<span data-ttu-id="06050-p126">您可能會建立大量的搜尋，因為此最後一個指令碼剛方便快速地刪除您在步驟 3 中建立搜尋。像其他的指令碼，以此也會提示您輸入搜尋群組識別碼。當您執行此指令碼時將會刪除所有搜尋中搜尋名稱搜尋群組識別碼。</span><span class="sxs-lookup"><span data-stu-id="06050-p126">Because you might be creating a lot of searches, this last script just makes it easy to quickly delete the searches you created in Step 3. Like the other scripts, this one also prompts you for the Search Group ID. All searches with the Search Group ID in the search name will be deleted when you run this script.</span></span> 
  
1. <span data-ttu-id="06050-p127">使用.ps1; filename 尾碼將下列文字儲存到 Windows PowerShell 指令碼檔案例如， `DeleteSearches.ps1`。將檔案儲存至您儲存其他檔案的相同資料夾中。</span><span class="sxs-lookup"><span data-stu-id="06050-p127">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `DeleteSearches.ps1`. Save the file to the same folder where you saved the other files.</span></span>
    
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

2. <span data-ttu-id="06050-201">在 Windows PowerShell 中移至您在先前步驟中，儲存指令碼的資料夾，然後執行 [指令碼 ；例如：</span><span class="sxs-lookup"><span data-stu-id="06050-201">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>
    
    ```
    .\DeleteSearches.ps1
    ```

3. <span data-ttu-id="06050-p128">在**搜尋群組識別碼**提示中輸入您要刪除的搜尋的搜尋群組名稱與按下**Enter**;例如， `ContosoCase`。請記住此名稱會區分大小寫，因此您必須輸入它的相同方式執行您在步驟 3 中執行指令碼時。</span><span class="sxs-lookup"><span data-stu-id="06050-p128">At the **Search Group ID** prompt, type a search group name for the searches that you want to delete, and then press **Enter**; for example,  `ContosoCase`. Remember that this name is case sensitive, so you'll have to type it the same way you did when you ran the script in Step 3.</span></span>
    
    <span data-ttu-id="06050-204">指令碼會顯示在刪除每個搜尋的名稱。</span><span class="sxs-lookup"><span data-stu-id="06050-204">The script displays the name of each search that's deleted.</span></span>
    
    ![執行指令碼，以刪除搜尋群組中的搜尋](media/9d97b9d6-a539-4d9b-a4e4-e99989144ec7.png)
