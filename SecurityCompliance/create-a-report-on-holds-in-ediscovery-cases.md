---
title: 在 Office 365 中的 eDiscovery 案例中保留上建立報告
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/11/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: cca08d26-6fbf-4b2c-b102-b226e4cd7381
description: 使用本文中的指令碼來產生報告包含與 Office 365 安全性的 eDiscovery 案例相關聯的所有保留的相關資訊&amp;規範中心。
ms.openlocfilehash: b6cef2824002d7e45e4f500bc6c1e9bc880cbd41
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038206"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases-in-office-365"></a><span data-ttu-id="192e1-103">在 Office 365 中的 eDiscovery 案例中保留上建立報告</span><span class="sxs-lookup"><span data-stu-id="192e1-103">Create a report on holds in eDiscovery cases in Office 365</span></span>
  
<span data-ttu-id="192e1-p101">本文中的指令碼可讓 eDiscovery 管理員和 eDiscovery 管理員產生報告包含與 Office 365 安全性的 eDiscovery 案例相關聯的所有保留的相關資訊&amp;規範中心。報告包含資訊例如保留的大小寫的名稱是關聯保留、 內容位置及是否保留為查詢為基礎。如果沒有任何保留的情況下，指令碼會建立其他報表不保留的情況下的清單。</span><span class="sxs-lookup"><span data-stu-id="192e1-p101">The script in this article lets eDiscovery administrators and eDiscovery managers generate a report that contains information about all holds that are associated with eDiscovery cases in the Office 365 Security &amp; Compliance Center. The report contains information such as the name of the case a hold is associated with, the content locations that are placed on hold, and whether the hold is query-based. If there are cases that don't have any holds, the script will create an additional report with a list of cases without holds.</span></span>

<span data-ttu-id="192e1-107">請參閱[的詳細資訊](#more-information)] 區段中的報表中所含的資訊的詳細說明。</span><span class="sxs-lookup"><span data-stu-id="192e1-107">See the [More information](#more-information) section for a detailed description of the information included in the report.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="192e1-108">開始之前</span><span class="sxs-lookup"><span data-stu-id="192e1-108">Before you begin</span></span>

- <span data-ttu-id="192e1-p102">若要在組織中產生上所有的 eDiscovery 案例的報告，您必須是您組織中的 eDiscovery 管理員。如果您是 eDiscovery 管理員，報表只會包含您可以存取的案例的相關資訊。如需 eDiscovery 權限的詳細資訊，請參閱[指派 Office 365 安全性 eDiscovery 權限&amp;規範中心](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="192e1-p102">To generate a report on all eDiscovery cases in your organization, you have to be an eDiscovery Administrator in your organization. If you are an eDiscovery Manager, the report will only include information about the cases that you can access. For more information about eDiscovery permissions, see [Assign eDiscovery permissions in the Office‍ 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="192e1-p103">本文中的指令碼有最少的錯誤處理。主要目的是快速建立與您組織中的 eDiscovery 案例相關聯的保留報告。</span><span class="sxs-lookup"><span data-stu-id="192e1-p103">The script in this article has minimal error handling. The primary purpose is to quickly create report about the holds that are associated with the eDiscovery cases in your organization.</span></span>
    
- <span data-ttu-id="192e1-p104">在任何 Microsoft 標準支援程式或服務下，不支援本主題提供的指令碼。範例指令碼係依「現狀」提供，不附帶任何明示或默示的擔保。Microsoft 另外不承擔任何明示或默示的擔保，包括但不限於適售性或適合某特定用途的默示擔保。使用或操作範例指令碼和文件發生的所有風險皆屬於您的責任。Microsoft、其作者以及其他與建置、生產或交付程式碼相關的任何人在任何情況下皆完全不需對任何損失負責任，包括但不限於商業利潤損失、業務中斷、業務資訊損失、或其他錢財損失等因使用或無法使用範例指令碼所發生的損失，即使 Microsoft 曾建議這些損失發生的可能性。</span><span class="sxs-lookup"><span data-stu-id="192e1-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-connect-to-the-security-amp-compliance-center-using-remote-powershell"></a><span data-ttu-id="192e1-119">步驟 1： 連線至安全性&amp;規範中心使用遠端 PowerShell</span><span class="sxs-lookup"><span data-stu-id="192e1-119">Step 1: Connect to the Security &amp; Compliance Center using Remote PowerShell</span></span>

<span data-ttu-id="192e1-120">第一個步驟是連線至安全性的 Windows PowerShell&amp;貴組織的規範中心。</span><span class="sxs-lookup"><span data-stu-id="192e1-120">The first step is to connect Windows PowerShell to the Security &amp; Compliance Center for your organization.</span></span>
  
1. <span data-ttu-id="192e1-121">使用.ps1; filename 尾碼將下列文字儲存到 Windows PowerShell 指令碼檔案例如， `ConnectSCC.ps1`。</span><span class="sxs-lookup"><span data-stu-id="192e1-121">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `ConnectSCC.ps1`.</span></span> 
    
      ```
      # Get login credentials 
      $UserCredential = Get-Credential 
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
      Import-PSSession $Session -AllowClobber -DisableNameChecking 
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Office 365 Security &amp; Compliance Center)" 
    ```

2. <span data-ttu-id="192e1-122">在您的本機電腦上開啟 Windows PowerShell，並移至您儲存指令碼的資料夾。</span><span class="sxs-lookup"><span data-stu-id="192e1-122">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span> 
    
3. <span data-ttu-id="192e1-123">執行指令碼 ；例如：</span><span class="sxs-lookup"><span data-stu-id="192e1-123">Run the script; for example:</span></span>

    ```
    .\ConnectSCC.ps1
    ```
   
4. <span data-ttu-id="192e1-124">當系統提示提供認證，請輸入您的電子郵件地址和密碼，並再按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="192e1-124">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span> 
  
## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a><span data-ttu-id="192e1-125">步驟 2： 執行指令碼以報告包含關聯 eDiscovery 案例</span><span class="sxs-lookup"><span data-stu-id="192e1-125">Step 2: Run the script to report on holds associated with eDiscovery cases</span></span>

<span data-ttu-id="192e1-126">您是否已連線至 [安全性] 後&amp;規範中心使用遠端 PowerShell 下, 一步是建立並執行指令碼，收集您組織中的 eDiscovery 案例的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="192e1-126">After you've connected to the Security &amp; Compliance Center with remote PowerShell, the next step is to create and run the script that collects information about the eDiscovery cases in your organization.</span></span> 
  
1. <span data-ttu-id="192e1-127">使用.ps1; filename 尾碼將下列文字儲存到 Windows PowerShell 指令碼檔案例如，CaseHoldsReport.ps1。</span><span class="sxs-lookup"><span data-stu-id="192e1-127">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, CaseHoldsReport.ps1.</span></span> 
    
  ```
#script begin
" " 
write-host "***********************************************"
write-host "   Office 365 Security & Compliance Center   " -foregroundColor yellow -backgroundcolor darkgreen
write-host "        eDiscovery cases - Holds report         " -foregroundColor yellow -backgroundcolor darkgreen 
write-host "***********************************************"
" " 
#prompt users to specify a path to store the output files
$time=get-date
$Path = Read-Host 'Enter a file path to save the report to a .csv file'
$outputpath=$Path+'\'+'CaseHoldsReport'+' '+$time.day+'-'+$time.month+'-'+$time.year+' '+$time.hour+'.'+$time.minute+'.csv'
$noholdsfilepath=$Path+'\'+'CaseswithNoHolds'+' '+$time.day+'-'+$time.month+'-'+$time.year+' '+$time.hour+'.'+$time.minute+'.csv'
#add case details to the csv file
function add-tocasereport{
Param([string]$casename,
[String]$casestatus,
[datetime]$casecreatedtime,
[string]$casemembers,
[datetime]$caseClosedDateTime,
[string]$caseclosedby,
[string]$holdname,
[String]$Holdenabled,
[string]$holdcreatedby,
[string]$holdlastmodifiedby,
[string]$ExchangeLocation,
[string]$sharePointlocation,
[string]$ContentMatchQuery,
[datetime]$holdcreatedtime,
[datetime]$holdchangedtime
)
$addRow = New-Object PSObject 
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case name" -Value $casename
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case status" -Value $casestatus
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case members" -Value $casemembers
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case created time" -Value $casecreatedtime
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case closed time" -Value $caseClosedDateTime
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case closed by" -Value $caseclosedby
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold name" -Value $holdname
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold enabled" -Value $Holdenabled
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold created by" -Value $holdcreatedby
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold last changed by" -Value $holdlastmodifiedby
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Exchange locations" -Value  $ExchangeLocation
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "SharePoint locations" -Value $sharePointlocation
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold query" -Value $ContentMatchQuery
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold created time (UTC)" -Value $holdcreatedtime
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold changed time (UTC)" -Value $holdchangedtime
$allholdreport = $addRow | Select-Object "Case name","Case status","Hold name","Hold enabled","Case members", "Case created time","Case closed time","Case closed by","Exchange locations","SharePoint locations","Hold query","Hold created by","Hold created time (UTC)","Hold last changed by","Hold changed time (UTC)"
$allholdreport | export-csv -path $outputPath -notypeinfo -append -Encoding ascii 
}
#get information on the cases and pass values to the case report function
" "
write-host "Gathering a list of cases and holds..."
" "
$edc =Get-ComplianceCase -ErrorAction SilentlyContinue
foreach($cc in $edc)
{
write-host "Working on case :" $cc.name
if($cc.status -eq 'Closed')
{
$cmembers = ((Get-ComplianceCaseMember -Case $cc.name).windowsLiveID)-join ';'
add-tocasereport -casename $cc.name -casestatus $cc.Status -caseclosedby $cc.closedby -caseClosedDateTime $cc.ClosedDateTime -casemembers $cmembers 
}
else{
$cmembers = ((Get-ComplianceCaseMember -Case $cc.name).windowsLiveID)-join ';'
$policies = Get-CaseHoldPolicy -Case $cc.Name | %{ Get-CaseHoldPolicy $_.Name -Case $_.CaseId -DistributionDetail}
if ($policies -ne $NULL)
{
foreach ($policy in $policies)
{
$rule=Get-CaseHoldRule -Policy $policy.name
add-tocasereport -casename $cc.name -casemembers $cmembers -casestatus $cc.Status -casecreatedtime $cc.CreatedDateTime -holdname $policy.name -holdenabled $policy.enabled -holdcreatedby $policy.CreatedBy -holdlastmodifiedby $policy.LastModifiedBy -ExchangeLocation (($policy.exchangelocation.name)-join ';') -SharePointLocation (($policy.sharePointlocation.name)-join ';') -ContentMatchQuery $rule.ContentMatchQuery -holdcreatedtime $policy.WhenCreatedUTC -holdchangedtime $policy.WhenChangedUTC
}
}
else{
write-host "No hold policies found in case:" $cc.name -foregroundColor 'Yellow'
" "
[string]$cc.name | out-file -filepath $noholdsfilepath -append 
}
}
}

" "
Write-host "Script complete! Report files saved to this folder: '$Path'"
" "
#script end
  ```

2. <span data-ttu-id="192e1-128">在步驟 1 中開啟 Windows PowerShell 工作階段中移至儲存指令碼的資料夾。</span><span class="sxs-lookup"><span data-stu-id="192e1-128">In the Windows PowerShell session that opened in Step 1, go to the folder where you saved the script.</span></span> 
    
3. <span data-ttu-id="192e1-129">執行指令碼 ；例如：</span><span class="sxs-lookup"><span data-stu-id="192e1-129">Run the script; for example:</span></span>

    ```
    .\CaseHoldsReport.ps1
    ```

    <span data-ttu-id="192e1-130">指令碼會提示儲存報告的目標資料夾中。</span><span class="sxs-lookup"><span data-stu-id="192e1-130">The script will prompt for a target folder to save the report to.</span></span> 
    
4. <span data-ttu-id="192e1-131">輸入要儲存、 報告資料夾的完整路徑名稱，然後按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="192e1-131">Type the full path name of the folder to save the report to, and then press **Enter**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="192e1-p105">若要儲存報表指令碼位於相同資料夾中，輸入句點 ("。") 的目標資料夾出現提示時。若要儲存報表指令碼所在的資料夾中的子資料夾中，只輸入的子資料夾的名稱。</span><span class="sxs-lookup"><span data-stu-id="192e1-p105">To save the report in the same folder that the script is located in, type a period (".") when prompted for a target folder. To save the report in a subfolder in the folder where the script is located, just type the name of the subfolder.</span></span> 
  
    <span data-ttu-id="192e1-p106">指令碼會開始收集您組織中所有的 eDiscovery 案例的相關資訊。執行指令碼時，不存取報告檔案。指令碼完成之後，請確認訊息會顯示在 Windows PowerShell 工作階段。會顯示此訊息之後，您可以存取您在步驟 4 中指定的資料夾中的報表。報表的檔案名稱為`CaseHoldsReport<DateTimeStamp>.csv`。</span><span class="sxs-lookup"><span data-stu-id="192e1-p106">The script starts to collect information about all the eDiscovery cases in your organization. Don't access the report file while the script is running. After the script is complete, a confirmation message is displayed in the Windows PowerShell session. After this message is displayed, you can access the report in the folder that you specified in Step 4. The file name for the report is `CaseHoldsReport<DateTimeStamp>.csv`.</span></span>

    <span data-ttu-id="192e1-p107">此外，指令碼也會建立報表沒有任何保留的情況下的清單。這份報告的檔案名稱是`CaseswithNoHolds<DateTimeStamp>.csv`。</span><span class="sxs-lookup"><span data-stu-id="192e1-p107">Addtionally, the script also creates a report with a list of cases that don't have any holds. The file name for this report is `CaseswithNoHolds<DateTimeStamp>.csv`.</span></span>
    
    <span data-ttu-id="192e1-141">以下是執行 CaseHoldsReport.ps1 指令碼範例。</span><span class="sxs-lookup"><span data-stu-id="192e1-141">Here's an example of running the CaseHoldsReport.ps1 script.</span></span> 
    
    ![執行 CaseHoldsReport.ps1 指令碼之後輸出](media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)
  
## <a name="more-information"></a><span data-ttu-id="192e1-143">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="192e1-143">More information</span></span>

<span data-ttu-id="192e1-p108">大小寫包含當您在本文中執行指令碼時所建立的報告包含下列每個保留的相關資訊。如先前所述，您必須是 eDiscovery 管理員，才可傳回組織中的所有保留的資訊。如保留案例的詳細資訊，請參閱[Office 365 安全性的 eDiscovery 案例&amp;規範中心](ediscovery-cases.md)。</span><span class="sxs-lookup"><span data-stu-id="192e1-p108">The case holds report that's created when you run the script in this article contains the following information about each hold. As previously explained, you have to be an eDiscovery Administrator to return information for all holds in your organization. For more information about case holds, see [eDiscovery cases in the Office 365 Security &amp; Compliance Center](ediscovery-cases.md).</span></span>
  
  - <span data-ttu-id="192e1-147">保留和 eDiscovery 案例的保留相關聯的名稱的名稱。</span><span class="sxs-lookup"><span data-stu-id="192e1-147">The name of the hold and the name of the eDiscovery case that the hold is associated with.</span></span>
    
  - <span data-ttu-id="192e1-148">是否 eDiscovery 案例為使用中或關閉。</span><span class="sxs-lookup"><span data-stu-id="192e1-148">Whether or not the eDiscovery case is active or closed.</span></span>
    
  - <span data-ttu-id="192e1-149">保留是否啟用或停用。</span><span class="sxs-lookup"><span data-stu-id="192e1-149">Whether or not the hold is enabled or disabled.</span></span>
    
  - <span data-ttu-id="192e1-p109">保留相關聯的 eDiscovery 案例的成員。Case 成員可以檢視或管理案例中，根據已被指派的 eDiscovery 權限而定。</span><span class="sxs-lookup"><span data-stu-id="192e1-p109">The members of the eDiscovery case that the hold is associated with. Case members can view or manage a case, depending on the eDiscovery permissions they've been assigned.</span></span>
    
  - <span data-ttu-id="192e1-152">大小寫的建立的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="192e1-152">The time and date the case was created.</span></span>
    
  - <span data-ttu-id="192e1-153">如果已關閉案例，關閉關閉它與時間和日期它的人員。</span><span class="sxs-lookup"><span data-stu-id="192e1-153">If a case is closed, the person who closed it and the time and date it was closed.</span></span>
    
  - <span data-ttu-id="192e1-154">Exchange 信箱與 SharePoint 網站所保留的位置。</span><span class="sxs-lookup"><span data-stu-id="192e1-154">The Exchange mailboxes and SharePoint sites locations that are on hold.</span></span>
    
  - <span data-ttu-id="192e1-155">如果查詢式保留查詢語法。</span><span class="sxs-lookup"><span data-stu-id="192e1-155">If the hold is query-based, the query syntax.</span></span>
    
  - <span data-ttu-id="192e1-156">與保留的建立的日期和時間建立它的人員。</span><span class="sxs-lookup"><span data-stu-id="192e1-156">The time and date the hold was created and the person who created it.</span></span>
    
  - <span data-ttu-id="192e1-157">與保留上次變更的日期和時間變更它的人員。</span><span class="sxs-lookup"><span data-stu-id="192e1-157">The time and date the hold was last changed and the person who changed it.</span></span>
