---
title: 在您的 eDiscovery 工作流程中使用內容搜尋
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 55f31488-288a-473a-9b9e-831a11e3711a
description: '使用 PowerShell 指令碼在 Exchange Online 中根據安全性 & 合規性中心中建立搜尋建立就地 eDiscovery 搜尋。 '
ms.openlocfilehash: d021836a735d5c5dd12124e16e348729d88e6022
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34157975"
---
# <a name="use-content-search-in-your-ediscovery-workflow"></a>在您的電子文件探索工作流程中使用內容搜尋

安全性 & 合規性中心中的內容搜尋功能可讓您在組織中搜尋所有信箱。 不同 Exchange Online （其中您可以搜尋最多 10000 個信箱） 中的 「 就地 eDiscovery，有單一搜尋中的目標信箱數目沒有限制。 對於要求您執行整個組織搜尋的案例，您可以使用「內容搜尋」來搜尋所有信箱。 然後您可以使用就地 eDiscovery 的工作流程功能來執行其他 eDiscovery 相關工作，例如將信箱設定為保留與匯出搜尋結果。 例如，假設您必須搜尋所有信箱以識別回應法律案件的特定監管人。 您可以使用安全性 & 合規性中心中的內容搜尋來搜尋所有信箱來識別回應的情況下，您組織中。 然後您可以使用 custodian 信箱該清單為來源信箱的 Exchange Online 中就地 eDiscovery 搜尋。 使用就地 eDiscovery 也可讓您在這些來源信箱上設定保留、 將搜尋結果複製到探索信箱，並匯出搜尋結果。
  
本主題包含的指令碼，您可以執行 Exchange Online 中建立的就地 eDiscovery 搜尋所使用的來源信箱和搜尋查詢從中安全性 & 合規性中心建立搜尋清單。 以下是程序的概觀：
  
[步驟 1：建立「內容搜尋」來搜尋組織中的所有信箱](#step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization)

[步驟 2： 連線到安全性\&合規性中心和 Exchange Online 中的單一遠端 PowerShell 工作階段](#step-2-connect-to-the-security--compliance-center-and-exchange-online-in-a-single-remote-powershell-session)
  
[步驟 3：執行指令碼以從內容搜尋建立就地 eDiscovery 搜尋](#step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search)

[Step 4: Start the In-Place eDiscovery search](#step-4-start-the-in-place-ediscovery-search)

## <a name="step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization"></a>步驟 1：建立「內容搜尋」來搜尋組織中的所有信箱

第一個步驟是在組織中使用安全性 & 合規性中心 （或安全性 & 合規性中心 PowerShell），若要建立內容的搜尋會搜尋所有信箱。 單一內容搜尋的信箱數目沒有限制。 指定適當的關鍵字查詢 (或敏感資訊類型的查詢)，讓搜尋僅傳回與調查有關的來源信箱。 如有必要，縮小搜尋查詢以縮小搜尋結果的範圍和傳回的來源信箱。
  
> [!NOTE]
> 如果來源內容搜尋沒有傳回任何結果，當您在步驟 3 中執行指令碼時不會建立就地 eDiscovery。您可能必須修改搜尋查詢然後重新執行內容搜尋以傳回搜尋結果。 
  
### <a name="use-the-security--compliance-center-to-search-all-mailboxes"></a>使用安全規範中心來搜尋所有信箱

1. [移至安全性 & 規範中心](go-to-the-securitycompliance-center.md)。 
    
2. 按一下 [**搜尋** > **內容搜尋**]，然後按一下 [**新搜尋**![加入圖示](media/O365-MDM-CreatePolicy-AddIcon.gif)。
    
3. 在 **[新增搜尋]** 頁面上，輸入內容搜尋的名稱。 
    
4. 在 [您希望我們在哪裡搜尋?]**** 底下按一下 [搜尋所有信箱]****，然後按 [下一步]****。
    
5. 在 [您希望我們尋找什麼?]**** 下方的方塊，在方塊中輸入搜尋查詢。 您可以指定關鍵字、例如傳送和接收日期的郵件屬性，或者例如檔案名稱或文件上次變更的日期的文件屬性。 您可以使用更複雜的查詢，使用布林運算子，例如 AND、 OR、 NOT 或附近，或者您也可以搜尋的敏感資訊 （例如社會安全編號） 中的郵件。 如需建立搜尋查詢的相關資訊，請參閱[Keyword queries for Content Search](keyword-queries-and-search-conditions.md)。
    
6. 按一下 [搜尋]**** 以儲存搜尋設定並開始搜尋。 
    
    在一段時間之後, 的估計項目在搜尋結果顯示在詳細資料窗格中。 預估包括搜尋結果的項目大小總計和總數。 在搜尋完成之後，您可以預覽搜尋結果。 如有必要，請按一下 [**重新整理**![重新整理圖示](media/O365-MDM-Policy-RefreshIcon.gif)以更新詳細資料窗格中的資訊。 
    
7.  如有必要，縮小搜尋查詢以縮小搜尋結果的範圍然後重新啟動搜尋。 
    
### <a name="use-security--compliance-center-powershell-to-search-all-mailboxes"></a>使用安全性 & 來搜尋所有信箱的合規性中心 PowerShell

您也可以使用 **New-ComplianceSearch** Cmdlet 來搜尋組織中的所有信箱。 第一個步驟是[連接到安全性 & 合規性中心 PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=627084)。
  
以下是使用 PowerShell 來搜尋組織中的所有信箱的範例。 搜尋查詢會傳回 2015 年 1 月 1 日和 2015 年 6 月 30 日之間傳送的所有郵件，以及主旨行中包含片語 "financial report" 的郵件。 第一個命令會建立搜尋，第二個命令會執行搜尋。 
  
```
New-ComplianceSearch -Name "Search All-Financial Report" -ExchangeLocation all -ContentMatchQuery 'sent>=01/01/2015 AND sent<=06/30/2015 AND subject:"financial report"'
```

```
Start-ComplianceSearch -Identity "Search All-Financial Report"
```

如需詳細資訊，請參閱 < <b0>New-compliancesearch</b0>。
  
### <a name="verify-the-number-of-source-mailboxes-in-the-content-search"></a>確認內容搜尋中的來源信箱數目

內容搜尋結果未傳回最多達 1000 個來源信箱包含搜尋結果。 如果有超過 1000 個信箱包含符合搜尋查詢的內容，請僅在大部分的搜尋結果的前 1000 個信箱併入您在上一個步驟中建立內容搜尋。 因此如果超過 1000 個信箱包含搜尋結果，這些信箱的一些不包括在來源信箱複製到新的就地 eDiscovery 搜尋在步驟 3 中建立的清單。 
  
為了協助您建立 「 內容搜尋以不超過 1000 來源信箱，請遵循下列步驟來執行指令碼會顯示您在步驟 1 中建立內容搜尋所傳回的來源信箱 （內含搜尋結果） 數目。 
  
1. 使用.ps1 檔名尾碼，顯示下列文字儲存到 PowerShell 指令碼檔案。 例如，您無法將其儲存至名為 csv 檔案`SourceMailboxes.ps1`。
    
  ```
  [CmdletBinding()]
  Param(
      [Parameter(Mandatory=$True,Position=1)]
      [string]$SearchName
  )
  $search = Get-ComplianceSearch $SearchName
  if ($search.Status -ne "Completed")
  {
                  "Please wait until the search finishes.";
                  break;
  }
  $results = $search.SuccessResults;
  if (($search.Items -le 0) -or ([string]::IsNullOrWhiteSpace($results)))
  {
                  "The Content Search " + $SearchName + " didn't return any useful results.";
                  break;
  }
  $mailboxes = @();
  $lines = $results -split '[\r\n]+';
  foreach ($line in $lines)
  {
      if ($line -match 'Location: (\S+),.+Item count: (\d+)' -and $matches[2] -gt 0)
      {
          $mailboxes += $matches[1];
      }
  }
  "Number of mailboxes that have search hits: " + $mailboxes.Count
  ```

2. 在安全性 & 合規性中心 PowerShell，移至您在上一個步驟中建立的指令碼所在的資料夾，然後執行指令碼。例如：
    
    ```
    .\SourceMailboxes.ps1
    ```

3. 當指令碼提示時，輸入您在步驟 1 中建立的內容搜尋的名稱。
    
    指令碼會顯示包含搜尋結果的來源信箱數目。
    
如果有 1000 個以上的來源信箱，請嘗試建立兩個 （或多個） 的內容搜尋。 例如，在一個內容搜尋中搜尋您組織的一半信箱，在另一個內容搜尋中搜尋另外一半。 您也可以變更搜尋準則來減少包含搜尋結果的信箱數目。 例如，您可能包含日期範圍，或縮小關鍵字查詢。
  
## <a name="step-2-connect-to-the-security--compliance-center-and-exchange-online-in-a-single-remote-powershell-session"></a>步驟 2： 連線到安全性\&合規性中心和 Exchange Online 中的單一遠端 PowerShell 工作階段

下一步是將 Windows PowerShell 連線到這兩種安全性 & 合規性中心以及 Exchange Online 組織。 這是必要因為您在步驟 3 中執行的指令碼需要存取安全 & 合規性中心內的內容搜尋 cmdlet 和就地 eDiscovery 指令程式在 Exchange Online。
  
1. 使用.ps1 檔名尾碼，顯示下列文字儲存到 Windows PowerShell 指令碼檔案。 例如，您無法將其儲存至名為 csv 檔案`ConnectEXO-CC.ps1`。
    
    ```
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -AllowClobber -DisableNameChecking
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. 在您的本機電腦上開啟 Windows PowerShell 移至您在上一個步驟中建立的指令碼所在的資料夾，然後執行指令碼。例如：
    
    ```
    .\ConnectEXO-CC.ps1
    ```

如何知道這是否正常運作？ 執行指令碼之後，從安全性 & 規範中心和 Exchange Online 指令程式會匯入至本機 PowerShell 工作階段。 如果您未收到任何錯誤，便已順利連線。 快速測試是執行安全性 & 合規性中心 cmdlet — 例如，**安裝 UnifiedCompliancePrerequisite** — 和 Exchange Online 指令程式，例如**Get-mailbox**。 
  
## <a name="step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search"></a>步驟 3：執行指令碼以從內容搜尋建立就地 eDiscovery 搜尋

您在步驟 2 中建立雙 PowerShell 工作階段之後下, 一步是執行的指令碼，會將現有的內容搜尋轉換為 「 就地 eDiscovery 搜尋。 以下是指令碼執行的動作：
  
- 提示您輸入要轉換的內容搜尋的名稱。
    
- 確認內容搜尋已完成執行。如果內容搜尋未傳回任何結果，就不會建立就地 eDiscovery。
    
- 從包含搜尋結果的內容搜尋將來源信箱的清單儲存至變數。
    
- 建立新的就地 eDiscovery 搜尋，具有下列屬性。請注意，並未啟動新的搜尋。您將在步驟 4 中加以啟動。
    
  - **名稱**-新搜尋的名稱使用此格式：\<內容搜尋的名稱\>_MBSearch1。 如果您再次執行指令碼，並使用相同的來源內容搜尋，搜尋會命名為\<內容搜尋的名稱\>_MBSearch2。
    
  - **來源信箱**的所有信箱內容搜尋從包含搜尋結果。 
    
  - **搜尋查詢**的新搜尋會使用搜尋查詢從內容搜尋。 如果內容搜尋包括所有內容 (其中搜尋查詢為空白)，新的搜尋也會有空白的搜尋查詢並將包含在來源信箱中找到的所有內容。 
    
  - **評估只搜尋**-新的搜尋會標示為僅限預估的搜尋。 在啟動之後，它不會將搜尋結果複製到探索信箱。 
    
1. 使用 ps1 檔名尾碼，顯示下列文字儲存到 Windows PowerShell 指令碼檔案。 例如，您無法將其儲存至名為 csv 檔案`CreateMBSearchFromComplianceSearch.ps1`。
    
  ```
  [CmdletBinding()]
  Param(
      [Parameter(Mandatory=$True,Position=1)]
      [string]$SearchName,
      [switch]$original,
      [switch]$restoreOriginal
  )
  $search = Get-ComplianceSearch $SearchName
  if ($search.Status -ne "Completed")
  {
    "Please wait until the search finishes";
    break;
  }
  $results = $search.SuccessResults;
  if (($search.Items -le 0) -or ([string]::IsNullOrWhiteSpace($results)))
  {
    "The Content Search " + $SearchName + " didn't return any useful results";
    "A mailbox search object wasn't created";
    break;
  }
  $mailboxes = @();
  $lines = $results -split '[\r\n]+';
  foreach ($line in $lines)
  {
      if ($line -match 'Location: (\S+),.+Item count: (\d+)' -and $matches[2] -gt 0)
      {
          $mailboxes += $matches[1];
      }
  }
  $msPrefix = $SearchName + "_MBSearch";
  $I = 1;
  $mbSearches = Get-MailboxSearch;
  while ($true)
  {
      $found = $false;
      $mbsName = "$msPrefix$I";
      foreach ($mbs in $mbSearches)
      {
          if ($mbs.Name -eq $mbsName)
          {
              $found = $true;
              break;
          }
      }
      if (!$found)
      {
          break;
      }
      $I++;
  }
  $query = $search.KeywordQuery;
  if ([string]::IsNullOrWhiteSpace($query))
  {
      $query = $search.ContentMatchQuery;
  }
  if ([string]::IsNullOrWhiteSpace($query))
  {
    New-MailboxSearch "$msPrefix$i" -SourceMailboxes $mailboxes -EstimateOnly;
  }
  else
  {
    New-MailboxSearch "$msPrefix$i" -SourceMailboxes $mailboxes -SearchQuery $query -EstimateOnly;
  }
  
  ```

2. 在您在步驟 2 中建立 Windows PowerShell 工作階段，移至您在上一個步驟中建立的指令碼所在的資料夾，然後執行指令碼。例如：
    
    ```
    .\CreateMBSearchFromComplianceSearch.ps1
    ```

3. 出現提示時由指令碼，輸入您想要轉換為 「 就地 eDiscovery 搜尋 （例如，搜尋您在步驟 1 中建立），內容搜尋的名稱，然後按**Enter**鍵。
    
    如果指令碼狀態為成功，會建立新的就地 eDiscovery 搜尋，狀態為 **NotStarted**。 執行命令`Get-MailboxSearch <Name of Content Search>_MBSearch1 | FL`以顯示新的搜尋的屬性。 
  
## <a name="step-4-start-the-in-place-ediscovery-search"></a>步驟 4：啟動就地 eDiscovery 搜尋

您在步驟 3 中執行的指令碼會建立新的就地 eDiscovery 搜尋，但不會啟動。下一個步驟是啟動搜尋，讓您取得搜尋結果的預估。
  
1. 在 Exchange 系統管理中心 (EAC) 中，移至 [**規範管理** \> **就地 eDiscovery&amp;保留**。
    
2. 在清單檢視中，選取您在步驟 3 中建立的就地 eDiscovery 搜尋。
    
3. 按一下 [**搜尋**![搜尋圖示](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif) \> **估計搜尋結果]** 以啟動搜尋並傳回的估計項目總大小和搜尋所傳回的項目數目。 
    
    估計結果會顯示在詳細資料窗格中。 按一下 [**重新整理**![重新整理圖示](media/O365-MDM-Policy-RefreshIcon.gif)以更新詳細資料窗格中顯示的資訊。 
    
4. 若要在搜尋完成之後預覽結果，按一下詳細資料窗格中的 [預覽搜尋結果]****。
  
## <a name="next-steps-after-creating-and-running-the-in-place-ediscovery-search"></a>建立和執行就地 eDiscovery 搜尋之後接下來的步驟

建立並啟動步驟 3 中的指令碼建立的就地 eDiscovery 搜尋之後，您可以使用一般的就地 eDiscovery 工作流程在搜尋結果上執行不同的 eDiscovery 動作。
  
### <a name="create-an-in-place-hold"></a>建立就地保留

1. 在 EAC 中，移至 [**規範管理** \> **就地 eDiscovery&amp;保留**。
    
2. 在清單檢視中，選取您在步驟 3 中建立的就地 eDiscovery 搜尋，然後按一下 [**編輯**![編輯圖示](media/O365_MDM_CreatePolicy_EditIcon.gif)。
    
3. 在 [就地保留設定]**** 頁面上，勾選 [將符合搜尋查詢的內容放入保留的所選信箱]**** 核取方塊，然後選擇下列其中一個選項： 
    
  - **無限期保留**-選擇此選項以將設為無限期保留搜尋所傳回的項目。 除非您從搜尋中移除信箱或移除搜尋，否則保留的項目會一直保存下來。 
    
  - **指定的天數將其接收日期的項目保留**-選擇此選項可在特定期間內保留項目。 持續時間自接收或建立信箱項目的日期開始計算。 
    
4. 按一下 [儲存]**** 以建立就地保留並重新啟動搜尋。 
    
[回到頁首](use-content-search-in-ediscovery.md#top)
  
### <a name="copy-the-search-results"></a>複製搜尋結果

1. 在 EAC 中，移至 [**規範管理** \> **就地 eDiscovery&amp;保留**。
    
2. 在清單檢視中，選取您在步驟 3 中建立的就地 eDiscovery 搜尋。
    
3. 按一下 [**搜尋**![搜尋圖示](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif)，然後從下拉式清單中按一下 [**複製搜尋結果**。 
    
4. 在 [複製搜尋結果]**** 中，從下列選項選取：
    
    - **包含無法搜尋的項目**-選取此核取方塊可包含無法搜尋 （例如，無法由 「 Exchange 搜尋編製索引的檔案類型附件的郵件） 的信箱項目。 
    
    - **啟用重複資料刪除**-選取此核取方塊以排除重複的郵件。 單一執行個體的郵件將會複製到探索信箱。 
    
    - **啟用完整記錄**-選取此核取方塊以在搜尋結果中包含完整的記錄檔。 
    
    - **將郵件複製完成時傳送我**-選取此核取方塊以在搜尋完成時收到電子郵件通知。 
    
    - **複製到探索信箱的結果**-按一下 [**瀏覽]** 以選取您想要在搜尋結果的探索信箱複製到。 
    
5. 按一下 [複製]**** 以開始程序來將搜尋結果複製到指定的探索信箱。 
    
6. 按一下 [**重新整理**![重新整理圖示](media/O365-MDM-Policy-RefreshIcon.gif)以更新詳細資料窗格中顯示的複製狀態資訊。 
    
7. 複製完成時，按一下 [開啟]**** 以開啟要檢視搜尋結果的探索信箱。 
  
### <a name="export-the-search-results"></a>匯出搜尋結果

1. 在 EAC 中，移至 [**規範管理** \> **就地 eDiscovery&amp;保留**。
    
2. 在清單檢視中，選取您在步驟 3 中建立的就地 eDiscovery 搜尋，然後按一下 [匯出為 PST 檔案]****。
    
3. In the **eDiscovery PST Export Tool** window, do the following: 
    
    - Click **Browse** to specify the location where you want to download the PST file. 
    
    - Click the **Enable deduplication** checkbox to exclude duplicate messages. Only a single instance of a message will be included in the PST file. 
    
    - Click the **Include unsearchable items** checkbox to include mailbox items that couldn't be searched (for example, messages with attachments of file types that couldn't be indexed by Exchange Search). Unsearchable items are exported to a separate PST file. 
    
4. Click **Start** to export the search results to a PST file. 
    
    包含匯出程序狀態資訊的視窗便會隨即顯示。
