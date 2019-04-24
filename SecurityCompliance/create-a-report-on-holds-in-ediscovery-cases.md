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
# <a name="create-a-report-on-holds-in-ediscovery-cases-in-office-365"></a>在 Office 365 中的 eDiscovery 案例中的保留建立報表
  
本文中的指令碼可讓 eDiscovery 系統管理員和 eDiscovery 管理員產生報告中的 eDiscovery 案例相關聯的所有保留的相關資訊，請在 Office 365 或 Microsoft 365 合規性中心。 例如的情況下保留名稱是關聯的內容位置會處於暫止狀態，以及是否保留為查詢型報告中包含的資訊。 如果沒有任何保留的情況下，指令碼會建立額外的報表不保留的情況下的清單。

請參閱報告中包含的資訊的詳細說明[的詳細資訊](#more-information)一節。 
  
## <a name="before-you-begin"></a>開始之前

- 若要在組織中產生的所有 eDiscovery 案例的報告，您必須是 eDiscovery 系統管理員在組織中。 如果您是 eDiscovery 管理員，報告只會包含您可以存取的案例的相關資訊。 如需 eDiscovery 權限的詳細資訊，請參閱[指派 eDiscovery 權限](assign-ediscovery-permissions.md)。
    
- 本文中的指令碼具有最少的錯誤處理。 主要目的是快速建立有關保留與您組織中的 eDiscovery 案例相關聯的報告。
    
- 在任何 Microsoft 標準支援程式或服務下，不支援本主題提供的指令碼。範例指令碼係依「現狀」提供，不附帶任何明示或默示的擔保。Microsoft 另外不承擔任何明示或默示的擔保，包括但不限於適售性或適合某特定用途的默示擔保。使用或操作範例指令碼和文件發生的所有風險皆屬於您的責任。Microsoft、其作者以及其他與建置、生產或交付程式碼相關的任何人在任何情況下皆完全不需對任何損失負責任，包括但不限於商業利潤損失、業務中斷、業務資訊損失、或其他錢財損失等因使用或無法使用範例指令碼所發生的損失，即使 Microsoft 曾建議這些損失發生的可能性。
    
## <a name="step-1-connect-to-the-security--compliance-center-powershell"></a>步驟 1： 連接到安全性 & 合規性中心 PowerShell

第一個步驟是連線至您的組織安全性 & 合規性中心。
  
1. 使用.ps1 檔名尾碼，將下列文字儲存至 Windows PowerShell 指令碼檔案例如， `ConnectSCC.ps1`。 
    
      ```
      # Get login credentials 
      $UserCredential = Get-Credential 
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
      Import-PSSession $Session -AllowClobber -DisableNameChecking 
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Security & Compliance Center)" 
    ```

2. 在您的本機電腦上開啟 Windows PowerShell，並移至您儲存指令碼的資料夾。 
    
3. 執行指令碼。例如：

    ```
    .\ConnectSCC.ps1
    ```
   
4. 當系統提示提供認證，請輸入您的電子郵件地址和密碼，，然後按一下 [**確定]**。 
  
## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a>步驟 2： 執行指令碼，以報告保留與 eDiscovery 案例相關聯

您已連接到安全性 & 合規性中心 PowerShell 之後下, 一步是建立並執行指令碼，收集組織中的 eDiscovery 案例的相關資訊。 
  
1. 使用.ps1 檔名尾碼，將下列文字儲存至 Windows PowerShell 指令碼檔案例如，CaseHoldsReport.ps1。 
    
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

2. 在 Windows PowerShell 工作階段開啟在步驟 1 中，移至您儲存指令碼的資料夾。 
    
3. 執行指令碼。例如：

    ```
    .\CaseHoldsReport.ps1
    ```

    指令碼會提示輸入要儲存報表的目標資料夾。 
    
4. 輸入要儲存，至報告的資料夾的完整路徑名稱，然後按**Enter**鍵。
    
    > [!TIP]
    > 若要儲存報表指令碼位於相同資料夾中，輸入一個句點 (「。 」) 時提示您輸入目標資料夾。 若要在指令碼的所在位置的資料夾中的子資料夾中儲存報表，只要輸入子資料夾名稱。 
  
    指令碼會開始收集組織中的所有 eDiscovery 案例的相關資訊。 執行指令碼時，不存取報告檔案。 指令碼完成之後，在 Windows PowerShell 工作階段中會顯示確認訊息。 會顯示此訊息之後，您可以存取您在步驟 4 中指定的資料夾中的報表。 報表的檔案名稱是`CaseHoldsReport<DateTimeStamp>.csv`。

    此外，指令碼也會建立報表沒有任何保留的情況下的清單。 此報表的檔案名稱是`CaseswithNoHolds<DateTimeStamp>.csv`。
    
    以下是執行 CaseHoldsReport.ps1 指令碼的範例。 
    
    ![執行 CaseHoldsReport.ps1 指令碼之後輸出](media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)
  
## <a name="more-information"></a>詳細資訊

這種情況會保留在本文中執行指令碼時建立的報告中包含下列每個保留的相關資訊。 如先前所述，您必須是 eDiscovery 管理員，才可傳回您組織中的所有保留的資訊。 如需案件保留的詳細資訊，請參閱 < <b0>eDiscovery 案例</b0>。
  
  - 保留和 eDiscovery 案例，保留相關聯的名稱的名稱。
    
  - 是否不信由你的 eDiscovery 案例為 active 或關閉。
    
  - 是否保留為啟用或停用。
    
  - 保留相關聯的 eDiscovery 案例的成員。 案例成員可以檢視或管理的情況下，根據已被指派的 eDiscovery 權限。
    
  - 這種情況的建立的日期和時間。
    
  - 如果被關閉的情況下，已關閉，關閉它與時間和日期它的人員。
    
  - Exchange 信箱和 SharePoint 網站上保留的位置。
    
  - 如果保留是查詢為基礎的查詢語法。
    
  - 和保留的建立的日期和時間建立它的人員。
    
  - 與保留上次變更的日期和時間變更它的人員。
