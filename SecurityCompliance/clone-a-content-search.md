---
title: 複製內容的搜尋 Office 365 安全性&amp;規範中心
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/26/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 7b40eeaa-544c-4534-b89b-9f79998e374c
description: 使用本文中的 Windows PowerShell 指令碼來快速複製現有內容的搜尋安全性&amp;Compliane 中心搜尋。當您複製搜尋時、 新的搜尋 （使用新的名稱） 會建立包含原始搜尋相同的屬性。然後您可以編輯新的搜尋 （由變更關鍵字查詢或日期範圍），然後再執行它。
ms.openlocfilehash: a4f801e3de281e8caf8aeb7d1c2bd48f0facb77c
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526625"
---
# <a name="clone-a-content-search-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="7cdbc-105">複製內容的搜尋 Office 365 安全性&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="7cdbc-105">Clone a Content Search in the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="7cdbc-p102">建立內容的搜尋 Office 365 安全性&amp;搜尋許多的信箱或 SharePoint 的規範中心及 OneDrive for Business 的網站可能需要一段時間。指定要搜尋網站也可以是容易錯誤如果您拼錯的 URL。若要避免這些問題，您可以使用本文中的 Windows PowerShell 指令碼來快速複製現有的內容搜尋。當您複製搜尋時、 新的搜尋 （使用不同的名稱） 會建立包含原始搜尋相同內容 （如內容的位置和搜尋查詢）。然後您可以編輯新的搜尋 （透過變更關鍵字查詢或日期範圍） 並執行它。</span><span class="sxs-lookup"><span data-stu-id="7cdbc-p102">Creating a Content Search in Office 365 Security &amp; Compliance Center that searches a lot of mailboxes or SharePoint and OneDrive for Business sites can take awhile. Specifying the sites to search can also be prone to errors if you mistype a URL. To avoid these issues, you can use the Windows PowerShell script in this article to quickly clone an existing Content Search. When a you clone a search, a new search (with a different name) is created that contains the same properties (such as the content locations and the search query) as the original search. Then you can edit the new search (by changing the keyword query or the date range) and run it.</span></span>
  
<span data-ttu-id="7cdbc-111">為什麼要選擇複製內容搜尋？</span><span class="sxs-lookup"><span data-stu-id="7cdbc-111">Why clone Content Searches?</span></span>
  
- <span data-ttu-id="7cdbc-112">若要比較的不同關鍵字結果搜尋查詢執行相同的內容位置上。</span><span class="sxs-lookup"><span data-stu-id="7cdbc-112">To compare the results of different keyword search queries run on the same content locations.</span></span>
    
- <span data-ttu-id="7cdbc-113">若要儲存您從不必重新輸入大量的內容位置當您建立新的搜尋。</span><span class="sxs-lookup"><span data-stu-id="7cdbc-113">To save you from having to re-enter a large number of content locations when you create a new search.</span></span>
    
- <span data-ttu-id="7cdbc-114">若要縮小搜尋結果;例如，如果您有傳回結果太多要匯出的搜尋，您可以複製搜尋並再新增 [日期範圍，以減少的搜尋結果數為基礎的搜尋條件。</span><span class="sxs-lookup"><span data-stu-id="7cdbc-114">To decrease the size of the search results; for example, if you have a search that returns too many results to export, you can clone the search and then add a search condition based on a date range to reduce the number of search results.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="7cdbc-115">開始之前</span><span class="sxs-lookup"><span data-stu-id="7cdbc-115">Before you begin</span></span>

- <span data-ttu-id="7cdbc-116">您必須是安全性 eDiscovery 管理員角色群組的成員&amp;規範中心執行本主題所述的指令碼。</span><span class="sxs-lookup"><span data-stu-id="7cdbc-116">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to run the script described in this topic.</span></span>
    
- <span data-ttu-id="7cdbc-p103">指令碼包括最少的錯誤處理。指令碼的主要目的是要快速複製內容的搜尋。</span><span class="sxs-lookup"><span data-stu-id="7cdbc-p103">The script includes minimal error handling. The primary purpose of the script is to quickly clone a content search.</span></span>
    
- <span data-ttu-id="7cdbc-119">指令碼會建立新的內容搜尋，但不會啟動它。</span><span class="sxs-lookup"><span data-stu-id="7cdbc-119">The script creates a new Content Search, but doesn't start it.</span></span>
    
- <span data-ttu-id="7cdbc-p104">此指令碼應考慮是否要藉由複製內容搜尋相關聯的 eDiscovery 案例。如果搜尋相關聯的案例，也會關聯的大小寫相同新的搜尋。如果現有的搜尋未與案例相關聯，新的搜尋將會列在 [安全性]**內容搜尋**] 頁面上&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="7cdbc-p104">This script takes into account whether the Content Search that you're cloning is associated with an eDiscovery case. If the search is associated with a case, the new search will also be associated with the same case. If the existing search isn't associated with a case, the new search will be listed on the **Content search** page in the Security &amp; Compliance Center.</span></span> 
    
- <span data-ttu-id="7cdbc-p105">本主題中所提供的指令碼範例不支援任何 Microsoft 標準支援程式或服務底下。指令碼範例會為 IS 提供不含任何類型的瑕疵擔保。Microsoft 進一步不作所有默示之的擔保包括但不限於任何默示擔保售或適合特定用途。與您保持承擔使用或效能的範例指令碼及文件的風險。事件無法在 Microsoft、 其作者，或其他參與建立、 實際執行或指令碼傳遞的任何人對於而概之任何損害皆不 （包括但不限於，遺漏的商務利潤、 業務中斷、 遺失的損害商務資訊或其他金錢遺失） 引起的使用或無法使用的範例指令碼或文件即使 Microsoft 已被告知這類損害的可能性。</span><span class="sxs-lookup"><span data-stu-id="7cdbc-p105">The sample script provided in this topic isn't supported under any Microsoft standard support program or service. The sample script is provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample script and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-clone-a-search"></a><span data-ttu-id="7cdbc-128">步驟 1： 執行指令碼以複製搜尋</span><span class="sxs-lookup"><span data-stu-id="7cdbc-128">Step 1: Run the script to clone a search</span></span>

<span data-ttu-id="7cdbc-p106">在此步驟中的指令碼會建立新的內容搜尋藉由複製現有的欄位。當您執行此指令碼時，將會提示您輸入下列資訊：</span><span class="sxs-lookup"><span data-stu-id="7cdbc-p106">The script in this step will create a new Content Search by cloning an existing one. When you run this script, you'll be prompted for the following information:</span></span>
  
- <span data-ttu-id="7cdbc-p107">**您的使用者認證**-指令碼會使用您的認證連線至安全性&amp;使用 Windows PowerShell for Office 365 組織的規範中心。如先前所述，您必須是安全性 eDiscovery 管理員角色群組的成員&amp;規範中心以執行指令碼。</span><span class="sxs-lookup"><span data-stu-id="7cdbc-p107">**Your user credentials** - The script will use your credentials to connect to the Security &amp; Compliance Center for your Office 365 organization with Windows PowerShell. As previously stated, you have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to run the script.</span></span> 
    
- <span data-ttu-id="7cdbc-133">**現有的搜尋的名稱**-這是您想要複製內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="7cdbc-133">**The name of the existing search** - This is the Content Search that you want to clone.</span></span> 
    
- <span data-ttu-id="7cdbc-134">**將建立的新搜尋的名稱**-如果您將此值保留空白，指令碼會建立新的搜尋藉由複製搜尋的名稱為基礎的名稱。</span><span class="sxs-lookup"><span data-stu-id="7cdbc-134">**The name of the new search that will be created** - If you leave this value blank, the script will create a name for the new search that is based on the name of the search that you're cloning.</span></span> 
    
<span data-ttu-id="7cdbc-135">若要複製之搜尋：</span><span class="sxs-lookup"><span data-stu-id="7cdbc-135">To clone a search:</span></span>
  
1. <span data-ttu-id="7cdbc-136">使用.ps1; filename 尾碼將下列文字儲存到 Windows PowerShell 指令碼檔案例如， `CloneSearch.ps1`。</span><span class="sxs-lookup"><span data-stu-id="7cdbc-136">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CloneSearch.ps1`.</span></span>
    
  ```
  # This PowerShell script clones an existing Content Search in the Office 365 Security &amp; Compliance Center
  # Get login credentials from the user
  if(!$UserCredential)
  {
      $UserCredential = Get-Credential
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
      if (!$Session)
      {
          Write-Error "Couldn't create a remote PowerShell session."
          return
      }
      Import-PSSession $Session -AllowClobber -DisableNameChecking
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Office 365 Security &amp; Compliance Center)"
  }
  # Ask for the name of the search you want to clone
  $searchName = Read-Host 'Enter the name of the search that you want to clone'
  # Ask for the name of the new search
  $newSearchName = Read-Host 'Enter a name for the new search [leave blank to automatically generate a name]'
  $originalSearch = Get-ComplianceSearch $searchName -EA SilentlyContinue
  # Make sure we have a valid search before continuing
  if(!$originalSearch)
  {
      Write-Error "Couldn't find search: $searchName"
      return
  }
  $searchNameCounter = 1
  # Find a suitable name for the new search
  while(!$newSearchName)
  {
      $newSearchName = $originalSearch.Name + "_" + $searchNameCounter
      $tempSearch = Get-ComplianceSearch $newSearchName -EA SilentlyContinue
      if ($tempSearch)
      {
          $newSearchName = $null
          $searchNameCounter++
      }
  }
  $caseName
  # Determine if the search is part of a case; if so get the case name
  if ($originalSearch.CaseId)
  {
      $searchCase = Get-ComplianceCase $originalSearch.CaseId
      $caseName = $searchCase.Name
  }
  # Need to cast this value as a Boolean the old fashion way
  $allowNotFoundExchangeLocationsEnabled = $false
  if ($originalSearch.AllowNotFoundExchangeLocationsEnabled)
  {
      $allowNotFoundExchangeLocationsEnabled = $true
  }
  $newSearch = New-ComplianceSearch -Name $newSearchName -AllowNotFoundExchangeLocationsEnabled $allowNotFoundExchangeLocationsEnabled -Case $caseName -ContentMatchQuery $originalSearch.ContentMatchQuery -Description $originalSearch.Description -ExchangeLocation $originalSearch.ExchangeLocation -ExchangeLocationExclusion $originalSearch.ExchangeLocationExclusion -Language $originalSearch.Language -SharePointLocation $originalSearch.SharePointLocation -SharePointLocationExclusion $originalSearch.SharePointLocationExclusion -PublicFolderLocation $originalSearch.PublicFolderLocation
  if ($newSearch)
  {
      Write-Host $newSearch.Name "was successfully created" -ForegroundColor Yellow
  }
  ```

2. <span data-ttu-id="7cdbc-137">開啟 Windows PowerShell 並移至您儲存指令碼的資料夾。</span><span class="sxs-lookup"><span data-stu-id="7cdbc-137">Open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="7cdbc-138">執行指令碼 ；例如：</span><span class="sxs-lookup"><span data-stu-id="7cdbc-138">Run the script; for example:</span></span>
    
    ```
    .\CloneSearch.ps1
    ```

4. <span data-ttu-id="7cdbc-139">當系統提示提供認證，請輸入您的電子郵件地址和密碼，並再按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="7cdbc-139">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span>
    
5. <span data-ttu-id="7cdbc-p108">輸入下列資訊時提示指令碼。輸入每段資訊，然後按**Enter**鍵。</span><span class="sxs-lookup"><span data-stu-id="7cdbc-p108">Enter following information when prompted by the script. Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="7cdbc-142">現有的搜尋的名稱。</span><span class="sxs-lookup"><span data-stu-id="7cdbc-142">The name of the existing search.</span></span>
    
    - <span data-ttu-id="7cdbc-143">新的搜尋的名稱。</span><span class="sxs-lookup"><span data-stu-id="7cdbc-143">The name of the new search.</span></span>
    
    <span data-ttu-id="7cdbc-p109">指令碼會建立新的內容搜尋，但不會啟動它。這可讓您能夠編輯並在下一個步驟中執行搜尋。您可以在執行**Get ComplianceSearch**指令程式或移至 [安全性]**內容搜尋**或**eDiscovery** ] 頁面上檢視的新的搜尋屬性&amp;規範中心，根據是否新的搜尋與案例相關聯。</span><span class="sxs-lookup"><span data-stu-id="7cdbc-p109">The script creates the new Content Search, but doesn't start it. This gives you a chance to edit and run the search in the next step. You can view the properties of the new search by running the **Get-ComplianceSearch** cmdlet or by going to the **Content search** or **eDiscovery** page in the Security &amp; Compliance Center, depending on whether or not the new search is associated with a case.</span></span> 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-security-amp-compliance-center"></a><span data-ttu-id="7cdbc-147">步驟 2： 編輯及執行複製的搜尋安全性&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="7cdbc-147">Step 2: Edit and run the cloned search in the Security &amp; Compliance Center</span></span>

<span data-ttu-id="7cdbc-p110">您是否已執行指令碼以複製現有的內容搜尋之後下, 一步是以移至 [安全性]&amp;規範中心編輯及執行新的搜尋。如先前所述，您可以編輯搜尋關鍵字搜尋查詢和新增或移除搜尋條件。如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="7cdbc-p110">After the you've run the script to clone an existing Content Search, the next step is to go to the Security &amp; Compliance Center to edit and run the new search. As previously stated, you can edit a search by changing the keyword search query and adding or removing search conditions. For more information, see:</span></span>
  
- [<span data-ttu-id="7cdbc-151">Office 365 中的內容搜尋</span><span class="sxs-lookup"><span data-stu-id="7cdbc-151">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="7cdbc-152">內容搜尋的關鍵字查詢與搜尋條件</span><span class="sxs-lookup"><span data-stu-id="7cdbc-152">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
    
- [<span data-ttu-id="7cdbc-153">Office 365 安全性的 eDiscovery 案例&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="7cdbc-153">eDiscovery cases in the Office 365 Security &amp; Compliance Center</span></span>](ediscovery-cases.md)
