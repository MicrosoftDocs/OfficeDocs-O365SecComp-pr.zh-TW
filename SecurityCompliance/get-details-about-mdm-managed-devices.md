---
title: 取得有關管理 Office 365 的行動裝置管理 (MDM) 的裝置的詳細資料
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 6/12/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MBS150
- MET150
ms.assetid: 5602963c-a1f2-4c21-afb9-f66cd7dca1f0
description: 本文說明如何使用 Windows PowerShell 來取得您設定的行動裝置管理 Office 365 組織中裝置的詳細資訊。
ms.openlocfilehash: 90ee59c5afed1cd260e13134299a7cb4f17dc5bc
ms.sourcegitcommit: 17c7e18d7d00135b1af40cbea117c9a817a41117
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/24/2018
ms.locfileid: "24972315"
---
# <a name="get-details-about-devices-managed-by-mobile-device-management-mdm-for-office-365"></a>取得有關管理 Office 365 的行動裝置管理 (MDM) 的裝置的詳細資料

本文說明如何使用 Windows PowerShell 來取得您設定的行動裝置管理 Office 365 組織中裝置的詳細資訊。 
  
## <a name="what-device-details-can-i-get"></a>可以取得何種裝置的詳細資訊？

以下是分解。
  
|**詳細資料**|**要尋找 PowerShell 中的項目**|
|:-----|:-----|
|裝置會[在 MDM for Office 365 中註冊](enroll-your-mobile-device.md) <br/> |*IsManaged*參數的值為：  <br/> **True 是表示**= 註冊裝置。  <br/> **False** = 不註冊裝置。  <br/> |
|裝置符合您的[裝置安全性原則](https://go.microsoft.com/fwlink/?linkid=615144) <br/> |*IsCompliant*參數的值為：  <br/> **True 是表示**= 裝置是否符合原則。  <br/> **False** = 裝置不符合原則。  <br/> |
   
![顯示裝置已註冊是否與抱怨的 AAD 命令介面參數值的流程](media/647b70f4-f886-41ef-8bff-04773a1da278.png)
  
> [!NOTE]
> 命令和本文中的指令碼也會傳回有關[Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune)受任何裝置的詳細資訊。 
  
## <a name="before-you-begin"></a>開始之前

有一些您需要設定設定為在本文中執行的命令和指令碼所述的事項。
  
### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a>步驟 1： 下載及安裝 Azure Active Directory Module for Windows PowerShell

如需這些步驟的詳細資訊，請參閱 ＜ [Connect to Office 365 PowerShell](https://docs.microsoft.com/Office365/enterprise/powershell/connect-to-office-365-powershell)。
  
1. 移至[Microsoft Online Services 登入小幫手的 IT 專業人員 RTWl](https://www.microsoft.com/en-us/download/details.aspx?id=41950)並按一下 [**下載**Microsoft Online Services 登入小幫手。 
    
2. 以下列步驟安裝適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組：
    
    1. 開啟管理員層級的 PowerShell 命令提示字元。
        
    2. 執行`Install-Module MSOnline`命令。
        
    3. 如果系統提示安裝 NuGet 提供者，請輸入`Y`並按 ENTER。
        
    4. 如果系統提示從 PSGallery 安裝此模組，請輸入`Y`並按 ENTER。
        
    5. 安裝完成後，請關閉 PowerShell 命令視窗。
    
### <a name="step-2-connect-to-your-office-365-subscription"></a>步驟 2：連線至您的 Office 365 訂用帳戶

1. 在 Windows Azure Active Directory 模組的 Windows PowerShell 中執行下列命令。<br/>  
  `$UserCredential = Get-Credential`

2. 在**Windows PowerShell 認證要求**] 對話方塊中，輸入使用者名稱與您的 Office 365 全域管理員帳戶的密碼並再按一下 [**確定]**。
    
3. 執行下列命令。<br/>
    `
  Connect-MsolService -Credential $UserCredential
  `

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a>步驟 3： 請確定您已執行 PowerShell 指令碼

> [!NOTE]
> 如果您正在已經設定好執行 PowerShell 指令碼，可以略過此步驟。 
  
若要執行**Get MsolUserDeviceComplianceStatus.ps1**指令碼，您需要啟用的 PowerShell 指令碼執行。 
  
1. 從 Windows 桌面，按一下 [**開始**]，然後輸入 Windows PowerShell。以滑鼠右鍵按一下 [ **Windows PowerShell**] 和 [**以系統管理員身分執行**。
    
2. 執行下列命令。<br/>
  `Set-ExecutionPolicy RemoteSigned`

3. 出現提示時，輸入`Y`，然後按 Enter。 
    
## <a name="run-the-get-msoldevice-cmdlet-to-display-details-for-all-devices-in-your-organization"></a>執行 Get MsolDevice cmdlet 可顯示組織中的所有裝置的詳細資料

1. 開啟適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。
    
2. 執行下列命令。<br/>
  ```
  Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}
  ```

如需更多範例，請參閱 ＜ [Get MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721)。
  
## <a name="run-a-script-to-get-device-details"></a>執行指令碼以取得裝置的詳細資訊

### <a name="first-save-the-script-to-your-computer"></a>首先，將指令碼儲存到您的電腦

1. 複製並貼入下列的文字貼入 [記事本]。<br/> 
  ```
  param (
      [PSObject[]]$users = @(),
      [Switch]$export,
      [String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",
      [String]$exportPath = [Environment]::GetFolderPath("Desktop")
   )
  [System.Collections.IDictionary]$script:schema = @{
      
      DeviceId = ''
      DeviceOSType = ''
      DeviceOSVersion = ''
      DeviceTrustLevel = ''
      DisplayName = ''
      IsCompliant = ''
      IsManaged = ''
      ApproximateLastLogonTimestamp = ''
      DeviceObjectId = ''    
      RegisteredOwnerUpn = ''
      RegisteredOwnerObjectId = ''
      RegisteredOwnerDisplayName = ''
  }
  function createResultObject
  {
      [PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema
      return $resultObject
  }
  If ($users.Count -eq 0)
  {
      $users = Get-MsolUser
  }
  [PSObject[]]$result = foreach ($u in $users)
  {
      
      [PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName
      foreach ($d in $devices)
      {
          [PSObject]$deviceResult = createResultObject
          $deviceResult.DeviceId = $d.DeviceId 
          $deviceResult.DeviceOSType = $d.DeviceOSType 
          $deviceResult.DeviceOSVersion = $d.DeviceOSVersion 
          $deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel
          $deviceResult.DisplayName = $d.DisplayName
          $deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant
          $deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged
          $deviceResult.DeviceObjectId = $d.ObjectId
          $deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName
          $deviceResult.RegisteredOwnerObjectId = $u.ObjectId
          $deviceResult.RegisteredOwnerDisplayName = $u.DisplayName
          $deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp
          $deviceResult
      }
  }
  If ($export)
  {
      $result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation
  }
  Else
  {
      $result
  }
  
  ```

2. 將其儲存為 Windows PowerShell 指令碼檔案使用將副檔名 **.ps1**。 <br/>範例：<br/> `Get-MsolUserDeviceComplianceStatus.ps1`.
    
### <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a>執行指令碼，以取得單一使用者帳戶的裝置資訊

1. 開啟適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。
    
2. 瀏覽至儲存指令碼的資料夾。例如，如果您儲存至 C:\PS-Scripts，會執行下列命令。<br/>
    `cd C:\PS-Scripts`

3. 執行下列命令來識別使用者想要取得裝置的詳細資料。此範例會取得 bar@example.com 的詳細資料。<br/>
  ```
  $u = Get-MsolUser -UserPrincipalName bar@example.com
  ```

4. 執行下列命令以啟動指令碼。<br/>
  ```
  .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
  ```

資訊至 Windows 桌面匯出為 CSV 檔案。您可以使用其他參數來指定 CSV 的路徑與檔案名稱。
  
### <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a>執行指令碼，以取得裝置資訊的使用者群組

1. 開啟適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。
    
2. 瀏覽至儲存指令碼的資料夾。例如，如果您儲存至 C:\PS-Scripts，會執行下列命令。<br/>
  `cd C:\PS-Scripts`

3. 執行下列命令來識別群組想要取得裝置的詳細資料。此範例會取得 FinanceStaff] 群組中的使用者的詳細資訊。<br/>
  ```
  $u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }
  ```

4. 執行下列命令以啟動指令碼。<br/>
  ```
  .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
  ```

資訊至 Windows 桌面匯出為 CSV 檔案。您可以使用其他參數來指定 CSV 的路徑與檔案名稱。
  
## <a name="more-info"></a>詳細資訊

[Office 365 MDM 的概觀](overview-of-mdm.md)
  
[取得 MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721)
  

