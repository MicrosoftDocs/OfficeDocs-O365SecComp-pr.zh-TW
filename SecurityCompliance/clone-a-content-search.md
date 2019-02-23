---
title: 複製內容的搜尋 Office 365 安全性&amp;規範中心
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
description: 使用本文中的 Windows PowerShell 指令碼來快速複製現有內容的搜尋安全性&amp;Compliane 中心搜尋。當您複製搜尋時、 新的搜尋 （使用新的名稱） 會建立包含原始搜尋相同的屬性。然後您可以編輯新的搜尋 （由變更關鍵字查詢或日期範圍），然後再執行它。
ms.openlocfilehash: 15f1ca5d00f03f510745fef7ae8418192a9eb448
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213543"
---
# <a name="clone-a-content-search-in-the-office-365-security-amp-compliance-center"></a>複製內容的搜尋 Office 365 安全性&amp;規範中心

建立內容的搜尋 Office 365 安全性&amp;搜尋許多的信箱或 SharePoint 的規範中心及 OneDrive for Business 的網站可能需要一段時間。指定要搜尋網站也可以是容易錯誤如果您拼錯的 URL。若要避免這些問題，您可以使用本文中的 Windows PowerShell 指令碼來快速複製現有的內容搜尋。當您複製搜尋時、 新的搜尋 （使用不同的名稱） 會建立包含原始搜尋相同內容 （如內容的位置和搜尋查詢）。然後您可以編輯新的搜尋 （透過變更關鍵字查詢或日期範圍） 並執行它。
  
為什麼要選擇複製內容搜尋？
  
- 若要比較的不同關鍵字結果搜尋查詢執行相同的內容位置上。
    
- 若要儲存您從不必重新輸入大量的內容位置當您建立新的搜尋。
    
- 若要縮小搜尋結果;例如，如果您有傳回結果太多要匯出的搜尋，您可以複製搜尋並再新增 [日期範圍，以減少的搜尋結果數為基礎的搜尋條件。
  
## <a name="before-you-begin"></a>開始之前

- 您必須是安全性 eDiscovery 管理員角色群組的成員&amp;規範中心執行本主題所述的指令碼。
    
- 指令碼包括最少的錯誤處理。指令碼的主要目的是要快速複製內容的搜尋。
    
- 指令碼會建立新的內容搜尋，但不會啟動它。
    
- 此指令碼應考慮是否要藉由複製內容搜尋相關聯的 eDiscovery 案例。如果搜尋相關聯的案例，也會關聯的大小寫相同新的搜尋。如果現有的搜尋未與案例相關聯，新的搜尋將會列在 [安全性]**內容搜尋**] 頁面上&amp;規範中心。 
    
- 本主題中所提供的指令碼範例不支援任何 Microsoft 標準支援程式或服務底下。指令碼範例會為 IS 提供不含任何類型的瑕疵擔保。Microsoft 進一步不作所有默示之的擔保包括但不限於任何默示擔保售或適合特定用途。與您保持承擔使用或效能的範例指令碼及文件的風險。事件無法在 Microsoft、 其作者，或其他參與建立、 實際執行或指令碼傳遞的任何人對於而概之任何損害皆不 （包括但不限於，遺漏的商務利潤、 業務中斷、 遺失的損害商務資訊或其他金錢遺失） 引起的使用或無法使用的範例指令碼或文件即使 Microsoft 已被告知這類損害的可能性。
  
## <a name="step-1-run-the-script-to-clone-a-search"></a>步驟 1： 執行指令碼以複製搜尋

在此步驟中的指令碼會建立新的內容搜尋藉由複製現有的欄位。當您執行此指令碼時，將會提示您輸入下列資訊：
  
- **您的使用者認證**-指令碼會使用您的認證連線至安全性&amp;使用 Windows PowerShell for Office 365 組織的規範中心。如先前所述，您必須是安全性 eDiscovery 管理員角色群組的成員&amp;規範中心以執行指令碼。 
    
- **現有的搜尋的名稱**-這是您想要複製內容搜尋。 
    
- **將建立的新搜尋的名稱**-如果您將此值保留空白，指令碼會建立新的搜尋藉由複製搜尋的名稱為基礎的名稱。 
    
若要複製之搜尋：
  
1. 使用.ps1; filename 尾碼將下列文字儲存到 Windows PowerShell 指令碼檔案例如， `CloneSearch.ps1`。
    
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

2. 開啟 Windows PowerShell 並移至您儲存指令碼的資料夾。
    
3. 執行指令碼 ；例如：
    
    ```
    .\CloneSearch.ps1
    ```

4. 當系統提示提供認證，請輸入您的電子郵件地址和密碼，並再按一下 [**確定]**。
    
5. 輸入下列資訊時提示指令碼。輸入每段資訊，然後按**Enter**鍵。
    
    - 現有的搜尋的名稱。
    
    - 新的搜尋的名稱。
    
    指令碼會建立新的內容搜尋，但不會啟動它。這可讓您能夠編輯並在下一個步驟中執行搜尋。您可以在執行**Get ComplianceSearch**指令程式或移至 [安全性]**內容搜尋**或**eDiscovery** ] 頁面上檢視的新的搜尋屬性&amp;規範中心，根據是否新的搜尋與案例相關聯。 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-security-amp-compliance-center"></a>步驟 2： 編輯及執行複製的搜尋安全性&amp;規範中心

您是否已執行指令碼以複製現有的內容搜尋之後下, 一步是以移至 [安全性]&amp;規範中心編輯及執行新的搜尋。如先前所述，您可以編輯搜尋關鍵字搜尋查詢和新增或移除搜尋條件。如需詳細資訊，請參閱：
  
- [Office 365 中的內容搜尋](content-search.md)
    
- [內容搜尋的關鍵字查詢與搜尋條件](keyword-queries-and-search-conditions.md)
    
- [Office 365 安全性的 eDiscovery 案例&amp;規範中心](ediscovery-cases.md)
