---
title: 複製內容搜尋
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/26/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
ms.assetid: 7b40eeaa-544c-4534-b89b-9f79998e374c
description: 使用本文中的 Windows PowerShell 指令碼，以快速地複製現有的 Office 365 或 Microsoft 365 的合規性中心中 「 內容搜尋。 當您複製搜尋時、 （以新名稱） 的新搜尋會建立包含原始的搜尋相同的屬性。 然後您可以編輯新的搜尋 （藉由變更的關鍵字查詢或日期範圍），然後再執行它。
ms.openlocfilehash: b08ccb6fbaf2dc9d92e0814fe9f92ea77c731147
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2019
ms.locfileid: "31001196"
---
# <a name="clone-a-content-search"></a><span data-ttu-id="13648-105">複製內容搜尋</span><span class="sxs-lookup"><span data-stu-id="13648-105">Clone a Content Search</span></span>

<span data-ttu-id="13648-106">在 Office 365 或 Microsoft 365 的合規性中心中建立 「 內容搜尋 」 搜尋大量信箱或 SharePoint 和 OneDrive for Business 網站可能需要一段時間。</span><span class="sxs-lookup"><span data-stu-id="13648-106">Creating a Content Search in the compliance center in Office 365 or Microsoft 365 that searches a lot of mailboxes or SharePoint and OneDrive for Business sites can take awhile.</span></span> <span data-ttu-id="13648-107">指定要搜尋的網站也可以是出錯的機會如果打錯的 URL。</span><span class="sxs-lookup"><span data-stu-id="13648-107">Specifying the sites to search can also be prone to errors if you mistype a URL.</span></span> <span data-ttu-id="13648-108">若要避免這些問題，您可以使用 Windows PowerShell 指令碼本文中，快速地複製現有的內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="13648-108">To avoid these issues, you can use the Windows PowerShell script in this article to quickly clone an existing Content Search.</span></span> <span data-ttu-id="13648-109">當您複製搜尋時，會建立包含屬性 （例如內容的位置和搜尋查詢） 與相同的原始的搜尋 （使用不同的名稱） 的新搜尋。</span><span class="sxs-lookup"><span data-stu-id="13648-109">When a you clone a search, a new search (with a different name) is created that contains the same properties (such as the content locations and the search query) as the original search.</span></span> <span data-ttu-id="13648-110">然後您可以編輯新的搜尋 （藉由變更的關鍵字查詢或日期範圍），並加以執行。</span><span class="sxs-lookup"><span data-stu-id="13648-110">Then you can edit the new search (by changing the keyword query or the date range) and run it.</span></span>
  
<span data-ttu-id="13648-111">為什麼要複製的內容搜尋？</span><span class="sxs-lookup"><span data-stu-id="13648-111">Why clone Content Searches?</span></span>
  
- <span data-ttu-id="13648-112">若要比較的結果不同的關鍵字搜尋查詢的相同的內容位置上執行。</span><span class="sxs-lookup"><span data-stu-id="13648-112">To compare the results of different keyword search queries run on the same content locations.</span></span>
    
- <span data-ttu-id="13648-113">若要儲存您不必重新輸入大量內容的位置，當您建立新的搜尋。</span><span class="sxs-lookup"><span data-stu-id="13648-113">To save you from having to re-enter a large number of content locations when you create a new search.</span></span>
    
- <span data-ttu-id="13648-114">若要縮小搜尋結果中。例如，如果您有傳回結果太多要匯出的搜尋，您可以複製搜尋，然後再新增搜尋條件，根據日期範圍，以減少搜尋結果數目。</span><span class="sxs-lookup"><span data-stu-id="13648-114">To decrease the size of the search results; for example, if you have a search that returns too many results to export, you can clone the search and then add a search condition based on a date range to reduce the number of search results.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="13648-115">開始之前</span><span class="sxs-lookup"><span data-stu-id="13648-115">Before you begin</span></span>

- <span data-ttu-id="13648-116">您必須是 eDiscovery 管理員角色群組的成員安全性 & 合規性中心中若要執行本主題所述的指令碼。</span><span class="sxs-lookup"><span data-stu-id="13648-116">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the script described in this topic.</span></span>
    
- <span data-ttu-id="13648-117">指令碼包含最少的錯誤處理。</span><span class="sxs-lookup"><span data-stu-id="13648-117">The script includes minimal error handling.</span></span> <span data-ttu-id="13648-118">指令碼的主要用途是快速地複製內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="13648-118">The primary purpose of the script is to quickly clone a content search.</span></span>
    
- <span data-ttu-id="13648-119">指令碼會建立新的內容搜尋，但不會啟動它。</span><span class="sxs-lookup"><span data-stu-id="13648-119">The script creates a new Content Search, but doesn't start it.</span></span>
    
- <span data-ttu-id="13648-120">此指令碼會考慮是否要複製內容搜尋相關聯的 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="13648-120">This script takes into account whether the Content Search that you're cloning is associated with an eDiscovery case.</span></span> <span data-ttu-id="13648-121">如果搜尋與案例相關聯，也會與相同的案例相關聯的新搜尋。</span><span class="sxs-lookup"><span data-stu-id="13648-121">If the search is associated with a case, the new search will also be associated with the same case.</span></span> <span data-ttu-id="13648-122">如果現有的搜尋不與案例相關聯，新的搜尋將會列在規範中心中的 [**內容搜尋**] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="13648-122">If the existing search isn't associated with a case, the new search will be listed on the **Content search** page in the compliance center.</span></span> 
    
- <span data-ttu-id="13648-123">本主題所提供的範例指令碼不支援任何 Microsoft 標準支援程式或服務。</span><span class="sxs-lookup"><span data-stu-id="13648-123">The sample script provided in this topic isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="13648-124">以提供範例指令碼不擔保。</span><span class="sxs-lookup"><span data-stu-id="13648-124">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="13648-125">Microsoft 進一步不作任何默示的擔保，包括，但不限於任何默示擔保售或適合特定用途。</span><span class="sxs-lookup"><span data-stu-id="13648-125">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="13648-126">與您保持承擔使用或效能的範例指令碼和文件的風險。</span><span class="sxs-lookup"><span data-stu-id="13648-126">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="13648-127">事件無法在 Microsoft、 其作者，或任何其他參與建立、 實際執行環境或傳遞的指令碼的人對於而概之任何損害皆不 （包括，但不限於遺失的商務利益、 業務中斷、 遺失的損害嗎商業資訊或其他金錢遺失） 即使 Microsoft 已被告知賠償的可能性，承擔使用或無法使用的範例指令碼或文件。</span><span class="sxs-lookup"><span data-stu-id="13648-127">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-clone-a-search"></a><span data-ttu-id="13648-128">步驟 1： 執行指令碼以複製搜尋</span><span class="sxs-lookup"><span data-stu-id="13648-128">Step 1: Run the script to clone a search</span></span>

<span data-ttu-id="13648-129">在此步驟中的指令碼會建立新的內容搜尋由複製現有的方式。</span><span class="sxs-lookup"><span data-stu-id="13648-129">The script in this step will create a new Content Search by cloning an existing one.</span></span> <span data-ttu-id="13648-130">當您執行此指令碼時，將會提示您輸入下列資訊：</span><span class="sxs-lookup"><span data-stu-id="13648-130">When you run this script, you'll be prompted for the following information:</span></span>
  
- <span data-ttu-id="13648-131">**您的使用者認證**-指令碼會使用您的認證來連線至 Office 365 組織使用 Windows PowerShell 安全性 & 合規性中心。</span><span class="sxs-lookup"><span data-stu-id="13648-131">**Your user credentials** - The script will use your credentials to connect to the Security & Compliance Center for your Office 365 organization with Windows PowerShell.</span></span> <span data-ttu-id="13648-132">如先前所述，您必須是 eDiscovery 管理員角色群組的成員安全性 & compCompliance 管理中心中執行指令碼。</span><span class="sxs-lookup"><span data-stu-id="13648-132">As previously stated, you have to be a member of the eDiscovery Manager role group in the Security & compCompliance Center to run the script.</span></span> 
    
- <span data-ttu-id="13648-133">**現有的搜尋的名稱**-這是您想要複製內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="13648-133">**The name of the existing search** - This is the Content Search that you want to clone.</span></span> 
    
- <span data-ttu-id="13648-134">**，將會建立新搜尋的名稱**-如果您將此值保留空白，指令碼會建立新的搜尋，根據您要複製的搜尋名稱的名稱。</span><span class="sxs-lookup"><span data-stu-id="13648-134">**The name of the new search that will be created** - If you leave this value blank, the script will create a name for the new search that is based on the name of the search that you're cloning.</span></span> 
    
<span data-ttu-id="13648-135">複製搜尋：</span><span class="sxs-lookup"><span data-stu-id="13648-135">To clone a search:</span></span>
  
1. <span data-ttu-id="13648-136">使用.ps1 檔名尾碼，將下列文字儲存至 Windows PowerShell 指令碼檔案例如， `CloneSearch.ps1`。</span><span class="sxs-lookup"><span data-stu-id="13648-136">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CloneSearch.ps1`.</span></span>
    
  ```
  # This PowerShell script clones an existing Content Search in the Office 365 security and compliance center.
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
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Security & Compliance Center)"
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

2. <span data-ttu-id="13648-137">開啟 Windows PowerShell，並移至您儲存指令碼的資料夾。</span><span class="sxs-lookup"><span data-stu-id="13648-137">Open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="13648-138">執行指令碼。例如：</span><span class="sxs-lookup"><span data-stu-id="13648-138">Run the script; for example:</span></span>
    
    ```
    .\CloneSearch.ps1
    ```

4. <span data-ttu-id="13648-139">當系統提示提供認證，請輸入您的電子郵件地址和密碼，，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="13648-139">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span>
    
5. <span data-ttu-id="13648-140">輸入下列資訊時提示指令碼。</span><span class="sxs-lookup"><span data-stu-id="13648-140">Enter following information when prompted by the script.</span></span> <span data-ttu-id="13648-141">輸入每一項資訊，然後按**Enter**鍵。</span><span class="sxs-lookup"><span data-stu-id="13648-141">Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="13648-142">現有的搜尋的名稱。</span><span class="sxs-lookup"><span data-stu-id="13648-142">The name of the existing search.</span></span>
    
    - <span data-ttu-id="13648-143">新的搜尋的名稱。</span><span class="sxs-lookup"><span data-stu-id="13648-143">The name of the new search.</span></span>
    
    <span data-ttu-id="13648-144">指令碼會建立新的內容搜尋，但不會啟動它。</span><span class="sxs-lookup"><span data-stu-id="13648-144">The script creates the new Content Search, but doesn't start it.</span></span> <span data-ttu-id="13648-145">這可以讓您有機會編輯，並在下一個步驟中執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="13648-145">This gives you a chance to edit and run the search in the next step.</span></span> <span data-ttu-id="13648-146">藉由執行**Get-compliancesearch** cmdlet 或移至 [規範中心，根據新的搜尋是與案例相關聯的 [**內容搜尋**] 或 [ **eDiscovery** ] 頁面上，您可以檢視新的搜尋的屬性。</span><span class="sxs-lookup"><span data-stu-id="13648-146">You can view the properties of the new search by running the **Get-ComplianceSearch** cmdlet or by going to the **Content search** or **eDiscovery** page in the compliance center, depending on whether or not the new search is associated with a case.</span></span> 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-compliance-center"></a><span data-ttu-id="13648-147">步驟 2： 編輯，並在 「 規範中心執行複製的搜尋</span><span class="sxs-lookup"><span data-stu-id="13648-147">Step 2: Edit and run the cloned search in the compliance center</span></span>

<span data-ttu-id="13648-148">您已執行指令碼以複製現有的內容搜尋之後下, 一步是以移至 「 合規性中心 」，編輯與執行新的搜尋。</span><span class="sxs-lookup"><span data-stu-id="13648-148">After the you've run the script to clone an existing Content Search, the next step is to go to the compliance center to edit and run the new search.</span></span> <span data-ttu-id="13648-149">如先前所述，您可以編輯搜尋的關鍵字搜尋查詢以及新增或移除搜尋條件。</span><span class="sxs-lookup"><span data-stu-id="13648-149">As previously stated, you can edit a search by changing the keyword search query and adding or removing search conditions.</span></span> <span data-ttu-id="13648-150">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="13648-150">For more information, see:</span></span>
  
- [<span data-ttu-id="13648-151">Office 365 中的內容搜尋</span><span class="sxs-lookup"><span data-stu-id="13648-151">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="13648-152">內容搜尋的關鍵字查詢與搜尋條件</span><span class="sxs-lookup"><span data-stu-id="13648-152">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
    
- [<span data-ttu-id="13648-153">eDiscovery 案例</span><span class="sxs-lookup"><span data-stu-id="13648-153">eDiscovery cases</span></span>](ediscovery-cases.md)
