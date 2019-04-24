---
title: 在 Office 365 中的 eDiscovery 案例中的保留建立報表
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/11/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid: MOE150
ms.assetid: cca08d26-6fbf-4b2c-b102-b226e4cd7381
description: 使用本文中的指令碼，來產生報告，其中包含與 Office 365 或 Microsoft 365 的合規性中心中的 eDiscovery 案例相關聯的所有保留的相關資訊。
ms.openlocfilehash: db5a462087dd20ed71f87efe2fd83b821654f1b9
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32258764"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases-in-office-365"></a><span data-ttu-id="610bf-103">在 Office 365 中的 eDiscovery 案例中的保留建立報表</span><span class="sxs-lookup"><span data-stu-id="610bf-103">Create a report on holds in eDiscovery cases in Office 365</span></span>
  
<span data-ttu-id="610bf-104">本文中的指令碼可讓 eDiscovery 系統管理員和 eDiscovery 管理員產生報告中的 eDiscovery 案例相關聯的所有保留的相關資訊，請在 Office 365 或 Microsoft 365 合規性中心。</span><span class="sxs-lookup"><span data-stu-id="610bf-104">The script in this article lets eDiscovery administrators and eDiscovery managers generate a report that contains information about all holds that are associated with eDiscovery cases in the the compliance center in Office 365 or Microsoft 365.</span></span> <span data-ttu-id="610bf-105">例如的情況下保留名稱是關聯的內容位置會處於暫止狀態，以及是否保留為查詢型報告中包含的資訊。</span><span class="sxs-lookup"><span data-stu-id="610bf-105">The report contains information such as the name of the case a hold is associated with, the content locations that are placed on hold, and whether the hold is query-based.</span></span> <span data-ttu-id="610bf-106">如果沒有任何保留的情況下，指令碼會建立額外的報表不保留的情況下的清單。</span><span class="sxs-lookup"><span data-stu-id="610bf-106">If there are cases that don't have any holds, the script will create an additional report with a list of cases without holds.</span></span>

<span data-ttu-id="610bf-107">請參閱報告中包含的資訊的詳細說明[的詳細資訊](#more-information)一節。</span><span class="sxs-lookup"><span data-stu-id="610bf-107">See the [More information](#more-information) section for a detailed description of the information included in the report.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="610bf-108">開始之前</span><span class="sxs-lookup"><span data-stu-id="610bf-108">Before you begin</span></span>

- <span data-ttu-id="610bf-109">若要在組織中產生的所有 eDiscovery 案例的報告，您必須是 eDiscovery 系統管理員在組織中。</span><span class="sxs-lookup"><span data-stu-id="610bf-109">To generate a report on all eDiscovery cases in your organization, you have to be an eDiscovery Administrator in your organization.</span></span> <span data-ttu-id="610bf-110">如果您是 eDiscovery 管理員，報告只會包含您可以存取的案例的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="610bf-110">If you are an eDiscovery Manager, the report will only include information about the cases that you can access.</span></span> <span data-ttu-id="610bf-111">如需 eDiscovery 權限的詳細資訊，請參閱[指派 eDiscovery 權限](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="610bf-111">For more information about eDiscovery permissions, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="610bf-112">本文中的指令碼具有最少的錯誤處理。</span><span class="sxs-lookup"><span data-stu-id="610bf-112">The script in this article has minimal error handling.</span></span> <span data-ttu-id="610bf-113">主要目的是快速建立有關保留與您組織中的 eDiscovery 案例相關聯的報告。</span><span class="sxs-lookup"><span data-stu-id="610bf-113">The primary purpose is to quickly create report about the holds that are associated with the eDiscovery cases in your organization.</span></span>
    
- <span data-ttu-id="610bf-p104">在任何 Microsoft 標準支援程式或服務下，不支援本主題提供的指令碼。範例指令碼係依「現狀」提供，不附帶任何明示或默示的擔保。Microsoft 另外不承擔任何明示或默示的擔保，包括但不限於適售性或適合某特定用途的默示擔保。使用或操作範例指令碼和文件發生的所有風險皆屬於您的責任。Microsoft、其作者以及其他與建置、生產或交付程式碼相關的任何人在任何情況下皆完全不需對任何損失負責任，包括但不限於商業利潤損失、業務中斷、業務資訊損失、或其他錢財損失等因使用或無法使用範例指令碼所發生的損失，即使 Microsoft 曾建議這些損失發生的可能性。</span><span class="sxs-lookup"><span data-stu-id="610bf-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-connect-to-the-security--compliance-center-powershell"></a><span data-ttu-id="610bf-119">步驟 1： 連接到安全性 & 合規性中心 PowerShell</span><span class="sxs-lookup"><span data-stu-id="610bf-119">Step 1: Connect to the Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="610bf-120">第一個步驟是連線至您的組織安全性 & 合規性中心。</span><span class="sxs-lookup"><span data-stu-id="610bf-120">The first step is to connect to the Security & Compliance Center for your organization.</span></span>
  
1. <span data-ttu-id="610bf-121">使用.ps1 檔名尾碼，將下列文字儲存至 Windows PowerShell 指令碼檔案例如， `ConnectSCC.ps1`。</span><span class="sxs-lookup"><span data-stu-id="610bf-121">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `ConnectSCC.ps1`.</span></span> 
    
      ```
      # Get login credentials 
      $UserCredential = Get-Credential 
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
      Import-PSSession $Session -AllowClobber -DisableNameChecking 
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Security & Compliance Center)" 
    ```

2. <span data-ttu-id="610bf-122">在您的本機電腦上開啟 Windows PowerShell，並移至您儲存指令碼的資料夾。</span><span class="sxs-lookup"><span data-stu-id="610bf-122">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span> 
    
3. <span data-ttu-id="610bf-123">執行指令碼。例如：</span><span class="sxs-lookup"><span data-stu-id="610bf-123">Run the script; for example:</span></span>

    ```
    .\ConnectSCC.ps1
    ```
   
4. <span data-ttu-id="610bf-124">當系統提示提供認證，請輸入您的電子郵件地址和密碼，，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="610bf-124">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span> 
  
## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a><span data-ttu-id="610bf-125">步驟 2： 執行指令碼，以報告保留與 eDiscovery 案例相關聯</span><span class="sxs-lookup"><span data-stu-id="610bf-125">Step 2: Run the script to report on holds associated with eDiscovery cases</span></span>

<span data-ttu-id="610bf-126">您已連接到安全性 & 合規性中心 PowerShell 之後下, 一步是建立並執行指令碼，收集組織中的 eDiscovery 案例的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="610bf-126">After you've connected to Security & Compliance Center PowerShell, the next step is to create and run the script that collects information about the eDiscovery cases in your organization.</span></span> 
  
1. <span data-ttu-id="610bf-127">使用.ps1 檔名尾碼，將下列文字儲存至 Windows PowerShell 指令碼檔案例如，CaseHoldsReport.ps1。</span><span class="sxs-lookup"><span data-stu-id="610bf-127">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, CaseHoldsReport.ps1.</span></span> 
    
  ```
#script begin
" " 
write-host "***********************************************"
write-host "   Security & Compliance Center   " -foregroundColor yellow -backgroundcolor darkgreen
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

2. <span data-ttu-id="610bf-128">在 Windows PowerShell 工作階段開啟在步驟 1 中，移至您儲存指令碼的資料夾。</span><span class="sxs-lookup"><span data-stu-id="610bf-128">In the Windows PowerShell session that opened in Step 1, go to the folder where you saved the script.</span></span> 
    
3. <span data-ttu-id="610bf-129">執行指令碼。例如：</span><span class="sxs-lookup"><span data-stu-id="610bf-129">Run the script; for example:</span></span>

    ```
    .\CaseHoldsReport.ps1
    ```

    <span data-ttu-id="610bf-130">指令碼會提示輸入要儲存報表的目標資料夾。</span><span class="sxs-lookup"><span data-stu-id="610bf-130">The script will prompt for a target folder to save the report to.</span></span> 
    
4. <span data-ttu-id="610bf-131">輸入要儲存，至報告的資料夾的完整路徑名稱，然後按**Enter**鍵。</span><span class="sxs-lookup"><span data-stu-id="610bf-131">Type the full path name of the folder to save the report to, and then press **Enter**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="610bf-132">若要儲存報表指令碼位於相同資料夾中，輸入一個句點 (「。 」) 時提示您輸入目標資料夾。</span><span class="sxs-lookup"><span data-stu-id="610bf-132">To save the report in the same folder that the script is located in, type a period (".") when prompted for a target folder.</span></span> <span data-ttu-id="610bf-133">若要在指令碼的所在位置的資料夾中的子資料夾中儲存報表，只要輸入子資料夾名稱。</span><span class="sxs-lookup"><span data-stu-id="610bf-133">To save the report in a subfolder in the folder where the script is located, just type the name of the subfolder.</span></span> 
  
    <span data-ttu-id="610bf-134">指令碼會開始收集組織中的所有 eDiscovery 案例的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="610bf-134">The script starts to collect information about all the eDiscovery cases in your organization.</span></span> <span data-ttu-id="610bf-135">執行指令碼時，不存取報告檔案。</span><span class="sxs-lookup"><span data-stu-id="610bf-135">Don't access the report file while the script is running.</span></span> <span data-ttu-id="610bf-136">指令碼完成之後，在 Windows PowerShell 工作階段中會顯示確認訊息。</span><span class="sxs-lookup"><span data-stu-id="610bf-136">After the script is complete, a confirmation message is displayed in the Windows PowerShell session.</span></span> <span data-ttu-id="610bf-137">會顯示此訊息之後，您可以存取您在步驟 4 中指定的資料夾中的報表。</span><span class="sxs-lookup"><span data-stu-id="610bf-137">After this message is displayed, you can access the report in the folder that you specified in Step 4.</span></span> <span data-ttu-id="610bf-138">報表的檔案名稱是`CaseHoldsReport<DateTimeStamp>.csv`。</span><span class="sxs-lookup"><span data-stu-id="610bf-138">The file name for the report is `CaseHoldsReport<DateTimeStamp>.csv`.</span></span>

    <span data-ttu-id="610bf-139">此外，指令碼也會建立報表沒有任何保留的情況下的清單。</span><span class="sxs-lookup"><span data-stu-id="610bf-139">Addtionally, the script also creates a report with a list of cases that don't have any holds.</span></span> <span data-ttu-id="610bf-140">此報表的檔案名稱是`CaseswithNoHolds<DateTimeStamp>.csv`。</span><span class="sxs-lookup"><span data-stu-id="610bf-140">The file name for this report is `CaseswithNoHolds<DateTimeStamp>.csv`.</span></span>
    
    <span data-ttu-id="610bf-141">以下是執行 CaseHoldsReport.ps1 指令碼的範例。</span><span class="sxs-lookup"><span data-stu-id="610bf-141">Here's an example of running the CaseHoldsReport.ps1 script.</span></span> 
    
    ![執行 CaseHoldsReport.ps1 指令碼之後輸出](media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)
  
## <a name="more-information"></a><span data-ttu-id="610bf-143">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="610bf-143">More information</span></span>

<span data-ttu-id="610bf-144">這種情況會保留在本文中執行指令碼時建立的報告中包含下列每個保留的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="610bf-144">The case holds report that's created when you run the script in this article contains the following information about each hold.</span></span> <span data-ttu-id="610bf-145">如先前所述，您必須是 eDiscovery 管理員，才可傳回您組織中的所有保留的資訊。</span><span class="sxs-lookup"><span data-stu-id="610bf-145">As previously explained, you have to be an eDiscovery Administrator to return information for all holds in your organization.</span></span> <span data-ttu-id="610bf-146">如需案件保留的詳細資訊，請參閱 < <b0>eDiscovery 案例</b0>。</span><span class="sxs-lookup"><span data-stu-id="610bf-146">For more information about case holds, see [eDiscovery cases](ediscovery-cases.md).</span></span>
  
  - <span data-ttu-id="610bf-147">保留和 eDiscovery 案例，保留相關聯的名稱的名稱。</span><span class="sxs-lookup"><span data-stu-id="610bf-147">The name of the hold and the name of the eDiscovery case that the hold is associated with.</span></span>
    
  - <span data-ttu-id="610bf-148">是否不信由你的 eDiscovery 案例為 active 或關閉。</span><span class="sxs-lookup"><span data-stu-id="610bf-148">Whether or not the eDiscovery case is active or closed.</span></span>
    
  - <span data-ttu-id="610bf-149">是否保留為啟用或停用。</span><span class="sxs-lookup"><span data-stu-id="610bf-149">Whether or not the hold is enabled or disabled.</span></span>
    
  - <span data-ttu-id="610bf-150">保留相關聯的 eDiscovery 案例的成員。</span><span class="sxs-lookup"><span data-stu-id="610bf-150">The members of the eDiscovery case that the hold is associated with.</span></span> <span data-ttu-id="610bf-151">案例成員可以檢視或管理的情況下，根據已被指派的 eDiscovery 權限。</span><span class="sxs-lookup"><span data-stu-id="610bf-151">Case members can view or manage a case, depending on the eDiscovery permissions they've been assigned.</span></span>
    
  - <span data-ttu-id="610bf-152">這種情況的建立的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="610bf-152">The time and date the case was created.</span></span>
    
  - <span data-ttu-id="610bf-153">如果被關閉的情況下，已關閉，關閉它與時間和日期它的人員。</span><span class="sxs-lookup"><span data-stu-id="610bf-153">If a case is closed, the person who closed it and the time and date it was closed.</span></span>
    
  - <span data-ttu-id="610bf-154">Exchange 信箱和 SharePoint 網站上保留的位置。</span><span class="sxs-lookup"><span data-stu-id="610bf-154">The Exchange mailboxes and SharePoint sites locations that are on hold.</span></span>
    
  - <span data-ttu-id="610bf-155">如果保留是查詢為基礎的查詢語法。</span><span class="sxs-lookup"><span data-stu-id="610bf-155">If the hold is query-based, the query syntax.</span></span>
    
  - <span data-ttu-id="610bf-156">和保留的建立的日期和時間建立它的人員。</span><span class="sxs-lookup"><span data-stu-id="610bf-156">The time and date the hold was created and the person who created it.</span></span>
    
  - <span data-ttu-id="610bf-157">與保留上次變更的日期和時間變更它的人員。</span><span class="sxs-lookup"><span data-stu-id="610bf-157">The time and date the hold was last changed and the person who changed it.</span></span>
