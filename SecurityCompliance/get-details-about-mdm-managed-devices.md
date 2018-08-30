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
ms.openlocfilehash: 2e406d3583e7892531b7c74bef0db374672956c7
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272528"
---
# <a name="get-details-about-devices-managed-by-mobile-device-management-mdm-for-office-365"></a><span data-ttu-id="89c76-103">取得有關管理 Office 365 的行動裝置管理 (MDM) 的裝置的詳細資料</span><span class="sxs-lookup"><span data-stu-id="89c76-103">Get details about devices managed by Mobile Device Management (MDM) for Office 365</span></span>

<span data-ttu-id="89c76-104">本文說明如何使用 Windows PowerShell 來取得您設定的行動裝置管理 Office 365 組織中裝置的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="89c76-104">This article shows you how to use Windows PowerShell to get details about the devices in your organization that you set up for Mobile Device Management for Office 365.</span></span> 
  
## <a name="what-device-details-can-i-get"></a><span data-ttu-id="89c76-105">可以取得何種裝置的詳細資訊？</span><span class="sxs-lookup"><span data-stu-id="89c76-105">What device details can I get?</span></span>

<span data-ttu-id="89c76-106">以下是分解。</span><span class="sxs-lookup"><span data-stu-id="89c76-106">Here's a breakdown.</span></span>
  
|<span data-ttu-id="89c76-107">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="89c76-107">**Detail**</span></span>|<span data-ttu-id="89c76-108">**要尋找 PowerShell 中的項目**</span><span class="sxs-lookup"><span data-stu-id="89c76-108">**What to look for in PowerShell**</span></span>|
|:-----|:-----|
|<span data-ttu-id="89c76-109">裝置會[在 MDM for Office 365 中註冊](enroll-your-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="89c76-109">Device is [enrolled in MDM for Office 365](enroll-your-mobile-device.md)</span></span> <br/> |<span data-ttu-id="89c76-110">*IsManaged*參數的值為：</span><span class="sxs-lookup"><span data-stu-id="89c76-110">The value of the  *isManaged*  parameter is:</span></span>  <br/> <span data-ttu-id="89c76-111">**True 是表示**= 註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="89c76-111">**True** = device is enrolled.</span></span>  <br/> <span data-ttu-id="89c76-112">**False** = 不註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="89c76-112">**False** = device is not enrolled.</span></span>  <br/> |
|<span data-ttu-id="89c76-113">裝置符合您的[裝置安全性原則](https://go.microsoft.com/fwlink/?linkid=615144)</span><span class="sxs-lookup"><span data-stu-id="89c76-113">Device is compliant with your [device security policies](https://go.microsoft.com/fwlink/?linkid=615144)</span></span> <br/> |<span data-ttu-id="89c76-114">*IsCompliant*參數的值為：</span><span class="sxs-lookup"><span data-stu-id="89c76-114">The value of the  *isCompliant*  parameter is:</span></span>  <br/> <span data-ttu-id="89c76-115">**True 是表示**= 裝置是否符合原則。</span><span class="sxs-lookup"><span data-stu-id="89c76-115">**True** = device is compliant with policies.</span></span>  <br/> <span data-ttu-id="89c76-116">**False** = 裝置不符合原則。</span><span class="sxs-lookup"><span data-stu-id="89c76-116">**False** = device is not compliant with policies.</span></span>  <br/> |
   
![顯示裝置已註冊是否與抱怨的 AAD 命令介面參數值的流程](media/647b70f4-f886-41ef-8bff-04773a1da278.png)
  
> [!NOTE]
> <span data-ttu-id="89c76-118">命令和本文中的指令碼也會傳回有關[Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune)受任何裝置的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="89c76-118">The commands and scripts in this article will also return details about any devices that are managed by [Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune).</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="89c76-119">開始之前</span><span class="sxs-lookup"><span data-stu-id="89c76-119">Before you begin</span></span>

<span data-ttu-id="89c76-120">有一些您需要設定設定為在本文中執行的命令和指令碼所述的事項。</span><span class="sxs-lookup"><span data-stu-id="89c76-120">There are a few things you'll need to set up to run the commands and scripts described in this article.</span></span>
  
### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="89c76-121">步驟 1： 下載及安裝 Azure Active Directory Module for Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="89c76-121">Step 1: Download and install the Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="89c76-122">如需這些步驟的詳細資訊，請參閱 ＜ [Connect to Office 365 PowerShell](https://docs.microsoft.com/Office365/enterprise/powershell/connect-to-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="89c76-122">For more info on these steps, see [Connect to Office 365 PowerShell](https://docs.microsoft.com/Office365/enterprise/powershell/connect-to-office-365-powershell).</span></span>
  
1. <span data-ttu-id="89c76-123">移至[Microsoft Online Services 登入小幫手的 IT 專業人員 RTWl](https://www.microsoft.com/en-us/download/details.aspx?id=41950)並按一下 [**下載**Microsoft Online Services 登入小幫手。</span><span class="sxs-lookup"><span data-stu-id="89c76-123">Go to [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl](https://www.microsoft.com/en-us/download/details.aspx?id=41950) and click **Download** for Microsoft Online Services Sign-in Assistant.</span></span> 
    
2. <span data-ttu-id="89c76-124">以下列步驟安裝適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組：</span><span class="sxs-lookup"><span data-stu-id="89c76-124">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>
    
    1. <span data-ttu-id="89c76-125">開啟管理員層級的 PowerShell 命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="89c76-125">Open an administrator-level PowerShell command prompt.</span></span>
        
    2. <span data-ttu-id="89c76-126">執行`Install-Module MSOnline`命令。</span><span class="sxs-lookup"><span data-stu-id="89c76-126">Run the `Install-Module MSOnline` command.</span></span>
        
    3. <span data-ttu-id="89c76-127">如果系統提示安裝 NuGet 提供者，請輸入`Y`並按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="89c76-127">If prompted to install the NuGet provider, type `Y` and press ENTER.</span></span>
        
    4. <span data-ttu-id="89c76-128">如果系統提示從 PSGallery 安裝此模組，請輸入`Y`並按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="89c76-128">If prompted to install the module from PSGallery, type `Y` and press ENTER.</span></span>
        
    5. <span data-ttu-id="89c76-129">安裝完成後，請關閉 PowerShell 命令視窗。</span><span class="sxs-lookup"><span data-stu-id="89c76-129">After installation, close the PowerShell command window.</span></span>
    
### <a name="step-2-connect-to-your-office-365-subscription"></a><span data-ttu-id="89c76-130">步驟 2：連線至您的 Office 365 訂用帳戶</span><span class="sxs-lookup"><span data-stu-id="89c76-130">Step 2: Connect to your Office 365 subscription</span></span>

1. <span data-ttu-id="89c76-131">在 Windows Azure Active Directory 模組的 Windows PowerShell 中執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="89c76-131">In the Windows Azure Active Directory Module for Windows PowerShell, run the following command.</span></span></br>  
  `$UserCredential = Get-Credential`

2. <span data-ttu-id="89c76-132">在**Windows PowerShell 認證要求**] 對話方塊中，輸入使用者名稱與您的 Office 365 全域管理員帳戶的密碼並再按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="89c76-132">In the **Windows PowerShell Credential Request** dialog box, type the user name and password for your Office 365 global admin account, and then click **OK**.</span></span>
    
3. <span data-ttu-id="89c76-133">執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="89c76-133">Run the following command.</span></span></br>
    `
  Connect-MsolService -Credential $UserCredential
  `

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a><span data-ttu-id="89c76-134">步驟 3： 請確定您已執行 PowerShell 指令碼</span><span class="sxs-lookup"><span data-stu-id="89c76-134">Step 3: Make sure you're able to run PowerShell scripts</span></span>

> [!NOTE]
> <span data-ttu-id="89c76-135">如果您正在已經設定好執行 PowerShell 指令碼，可以略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="89c76-135">You can skip this step if you're already set up to run PowerShell scripts.</span></span> 
  
<span data-ttu-id="89c76-136">若要執行**Get MsolUserDeviceComplianceStatus.ps1**指令碼，您需要啟用的 PowerShell 指令碼執行。</span><span class="sxs-lookup"><span data-stu-id="89c76-136">To run the **Get-MsolUserDeviceComplianceStatus.ps1** script, you need to enable the running of PowerShell scripts.</span></span> 
  
1. <span data-ttu-id="89c76-p101">從 Windows 桌面，按一下 [**開始**]，然後輸入 Windows PowerShell。以滑鼠右鍵按一下 [ **Windows PowerShell**] 和 [**以系統管理員身分執行**。</span><span class="sxs-lookup"><span data-stu-id="89c76-p101">From your Windows Desktop, click **Start**, and then type Windows PowerShell. Right click **Windows PowerShell**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="89c76-139">執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="89c76-139">Run the following command.</span></span></br>
  `Set-ExecutionPolicy RemoteSigned`

3. <span data-ttu-id="89c76-140">出現提示時，輸入`Y`，然後按 Enter。</span><span class="sxs-lookup"><span data-stu-id="89c76-140">When prompted, type `Y` and then press Enter.</span></span> 
    
## <a name="run-the-get-msoldevice-cmdlet-to-display-details-for-all-devices-in-your-organization"></a><span data-ttu-id="89c76-141">執行 Get MsolDevice cmdlet 可顯示組織中的所有裝置的詳細資料</span><span class="sxs-lookup"><span data-stu-id="89c76-141">Run the Get-MsolDevice cmdlet to display details for all devices in your organization</span></span>

1. <span data-ttu-id="89c76-142">開啟適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。</span><span class="sxs-lookup"><span data-stu-id="89c76-142">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="89c76-143">執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="89c76-143">Run the following command.</span></span></br>
  ```
  Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}
  ```

<span data-ttu-id="89c76-144">如需更多範例，請參閱 ＜ [Get MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721)。</span><span class="sxs-lookup"><span data-stu-id="89c76-144">For more examples, see [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721).</span></span>
  
## <a name="run-a-script-to-get-device-details"></a><span data-ttu-id="89c76-145">執行指令碼以取得裝置的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="89c76-145">Run a script to get device details</span></span>

### <a name="first-save-the-script-to-your-computer"></a><span data-ttu-id="89c76-146">首先，將指令碼儲存到您的電腦</span><span class="sxs-lookup"><span data-stu-id="89c76-146">First, save the script to your computer</span></span>

1. <span data-ttu-id="89c76-147">複製並貼入下列的文字貼入 [記事本]。</span><span class="sxs-lookup"><span data-stu-id="89c76-147">Copy and paste the following text into Notepad.</span></span></br> 
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

2. <span data-ttu-id="89c76-148">將其儲存為 Windows PowerShell 指令碼檔案使用將副檔名 **.ps1**。</span><span class="sxs-lookup"><span data-stu-id="89c76-148">Save it as a Windows PowerShell script file by using the file extension **.ps1**.</span></span> </br><span data-ttu-id="89c76-149">範例：</span><span class="sxs-lookup"><span data-stu-id="89c76-149">Example:</span></span></br> <span data-ttu-id="89c76-150">`Get-MsolUserDeviceComplianceStatus.ps1`.</span><span class="sxs-lookup"><span data-stu-id="89c76-150"></span></span>
    
### <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a><span data-ttu-id="89c76-151">執行指令碼，以取得單一使用者帳戶的裝置資訊</span><span class="sxs-lookup"><span data-stu-id="89c76-151">Run the script to get device information for a single user account</span></span>

1. <span data-ttu-id="89c76-152">開啟適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。</span><span class="sxs-lookup"><span data-stu-id="89c76-152">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="89c76-p102">瀏覽至儲存指令碼的資料夾。例如，如果您儲存至 C:\PS-Scripts，會執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="89c76-p102">Navigate to the folder where you saved the script. For example, if you saved it to C:\PS-Scripts, you'd run the following command.</span></span></br>
    `cd C:\PS-Scripts`

3. <span data-ttu-id="89c76-p103">執行下列命令來識別使用者想要取得裝置的詳細資料。此範例會取得 bar@example.com 的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="89c76-p103">Run the following command to identify the user you want to get device details for. This example gets details for bar@example.com.</span></span></br>
  ```
  $u = Get-MsolUser -UserPrincipalName bar@example.com
  ```

4. <span data-ttu-id="89c76-157">執行下列命令以啟動指令碼。</span><span class="sxs-lookup"><span data-stu-id="89c76-157">Run the following command to initiate the script.</span></span></br>
  ```
  .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
  ```

<span data-ttu-id="89c76-p104">資訊至 Windows 桌面匯出為 CSV 檔案。您可以使用其他參數來指定 CSV 的路徑與檔案名稱。</span><span class="sxs-lookup"><span data-stu-id="89c76-p104">The information is exported to your Windows Desktop as a CSV file. You can use additional parameters to specify the file name and path of the CSV.</span></span>
  
### <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a><span data-ttu-id="89c76-160">執行指令碼，以取得裝置資訊的使用者群組</span><span class="sxs-lookup"><span data-stu-id="89c76-160">Run the script to get device information for a group of users</span></span>

1. <span data-ttu-id="89c76-161">開啟適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。</span><span class="sxs-lookup"><span data-stu-id="89c76-161">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="89c76-p105">瀏覽至儲存指令碼的資料夾。例如，如果您儲存至 C:\PS-Scripts，會執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="89c76-p105">Navigate to the folder where you saved the script. For example, if you saved it to C:\PS-Scripts, you'd run the following command.</span></span></br>
  `cd C:\PS-Scripts`

3. <span data-ttu-id="89c76-p106">執行下列命令來識別群組想要取得裝置的詳細資料。此範例會取得 FinanceStaff] 群組中的使用者的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="89c76-p106">Run the following command to identify the group you want to get device details for. This example gets details for users in the FinanceStaff group.</span></span></br>
  ```
  $u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }
  ```

4. <span data-ttu-id="89c76-166">執行下列命令以啟動指令碼。</span><span class="sxs-lookup"><span data-stu-id="89c76-166">Run the following command to initiate the script.</span></span></br>
  ```
  .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
  ```

<span data-ttu-id="89c76-p107">資訊至 Windows 桌面匯出為 CSV 檔案。您可以使用其他參數來指定 CSV 的路徑與檔案名稱。</span><span class="sxs-lookup"><span data-stu-id="89c76-p107">The information is exported to your Windows Desktop as a CSV file. You can use additional parameters to specify the file name and path of the CSV.</span></span>
  
## <a name="more-info"></a><span data-ttu-id="89c76-169">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="89c76-169">More info</span></span>

[<span data-ttu-id="89c76-170">Office 365 MDM 的概觀</span><span class="sxs-lookup"><span data-stu-id="89c76-170">Overview of MDM for Office 365</span></span>](overview-of-mdm.md)
  
[<span data-ttu-id="89c76-171">取得 MsolDevice</span><span class="sxs-lookup"><span data-stu-id="89c76-171">Get-MsolDevice</span></span>](https://go.microsoft.com/fwlink/?linkid=841721)
  

