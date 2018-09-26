---
title: 在您的 eDiscovery 工作流程中使用內容搜尋
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 55f31488-288a-473a-9b9e-831a11e3711a
description: '使用 PowerShell 指令碼的就地 eDiscovery 搜尋在 Exchange Online 建立根據搜尋建立 Office 365 安全性&amp;規範中心。 '
ms.openlocfilehash: 42af94ce850736dede52e619c240bb9e0a6f7031
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038066"
---
# <a name="use-content-search-in-your-ediscovery-workflow"></a>在您的 eDiscovery 工作流程中使用內容搜尋

Office 365 安全性內容的搜尋功能&amp;規範中心 」 可讓您在組織中搜尋所有信箱。不同 Exchange Online （其中您可以搜尋最多 10000 個信箱） 中的就地 eDiscovery 有單一搜尋中的目標信箱數目沒有限制。如需要執行整個組織搜尋的案例，您可以使用內容搜尋來搜尋所有信箱。然後您可以使用就地 eDiscovery 的工作流程功能來執行其他 eDiscovery 相關工作，例如將信箱保留與匯出搜尋結果。例如，假設您有搜尋所有信箱移轉至識別回應法律案例的特定 custodians。您可以使用內容的搜尋安全性&amp;規範中心來識別回應案例的組織中搜尋所有信箱。然後您可以使用 okay 信箱該清單為來源信箱的 Exchange Online 中的就地 eDiscovery 搜尋。使用就地 eDiscovery 也可讓您將這些來源信箱上設定保留、 將搜尋結果複製到探索信箱和匯出搜尋結果。
  
本主題包含您可以使用來源信箱和搜尋安全性中建立的搜尋查詢的清單建立就地 eDiscovery 搜尋在 Exchange Online 中執行的指令碼&amp;規範中心。以下是程序概觀：
  
[步驟 1：建立「內容搜尋」來搜尋組織中的所有信箱](#step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization)

[步驟 2： 連線至安全性&amp;規範中心和 Exchange Online 中的單一遠端 PowerShell 工作階段](#step-2-connect-to-the-security-amp-compliance-center-and-exchange-online-in-a-single-remote-powershell-session)
  
[步驟 3：執行指令碼以從內容搜尋建立就地 eDiscovery 搜尋](#step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search)

[步驟 4：啟動就地 eDiscovery 搜尋](#step-4-start-the-in-place-ediscovery-search)

## <a name="step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization"></a>步驟 1：建立「內容搜尋」來搜尋組織中的所有信箱

第一個步驟是使用安全性&amp;規範中心 （或安全性及規範中心 PowerShell） 建立搜尋組織中所有信箱內容搜尋。有單一的內容搜尋沒有限制的信箱數目。指定適當的關鍵字查詢 （或查詢的敏感資訊類型） 搜尋會傳回與您正在調查的來源信箱。如有必要，調整搜尋查詢來縮小搜尋結果與來源信箱所傳回的範圍。
  
> [!NOTE]
> 如果來源內容搜尋沒有傳回任何結果，當您在步驟 3 中執行指令碼時不會建立就地 eDiscovery。您可能必須修改搜尋查詢然後重新執行內容搜尋以傳回搜尋結果。 
  
### <a name="use-the-security-amp-compliance-center-to-search-all-mailboxes"></a>使用安全性&amp;規範中心來搜尋所有信箱

1. [移至 Office 365 安全性&amp;規範中心](go-to-the-securitycompliance-center.md)。 
    
2. 按一下 [**搜尋&amp;調查**、 按一下 [**內容搜尋**] 及 [**新增**![新增圖示](media/O365-MDM-CreatePolicy-AddIcon.gif)。
    
3. 在 **[新增搜尋]** 頁面上，輸入內容搜尋的名稱。 
    
4. 下**出您想我們要尋找？**、 按一下 [**搜尋所有信箱**，並再按 [**下一步**。
    
5. 在下] 方塊中**您想什麼我們要尋找的？**、] 方塊中輸入搜尋查詢。您可以指定關鍵字，訊息屬性例如傳送及接收日期或文件內容，例如檔案名稱或上次變更文件的日期。您可以使用較複雜的查詢不使用布林運算子，例如 AND、 OR 或靠近，或是您也可搜尋的訊息中的機密資訊 （例如社會安全編號）。如需建立搜尋查詢的詳細資訊，請參閱 ＜[內容搜尋的關鍵字查詢](keyword-queries-and-search-conditions.md)。
    
6. 按一下 [**搜尋**] 以儲存搜尋設定並啟動搜尋。 
    
    While 之後評估會有搜尋結果顯示詳細資料窗格中。評估包含總大小及搜尋結果的項目數。搜尋完成後，您可預覽搜尋結果。若有必要，請按一下 [**重新整理**![重新整理] 圖示](media/O365-MDM-Policy-RefreshIcon.gif)要更新的詳細資料窗格中的資訊。 
    
7.  如有必要，縮小搜尋查詢以縮小搜尋結果的範圍然後重新啟動搜尋。 
    
### <a name="use-security--compliance-center-powershell-to-search-all-mailboxes"></a>使用安全性及規範中心 PowerShell，以搜尋所有信箱

您也可以使用**New ComplianceSearch**指令程式來搜尋您組織中所有信箱。第一個步驟是[連線至 Office 365 安全性&amp;規範中心 PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=627084)。
  
以下是使用 PowerShell 來搜尋您組織中所有信箱的範例。搜尋查詢會傳回 2015 年 1 月 1、 和 2015 年 6 月 30，之間傳送的所有郵件及可包含片語主旨行中的 「 財務 report"。第一個命令會建立搜尋和第二個命令會執行搜尋。 
  
```
New-ComplianceSearch -Name "Search All-Financial Report" -ExchangeLocation all -ContentMatchQuery 'sent>=01/01/2015 AND sent<=06/30/2015 AND subject:"financial report"'
```

```
Start-ComplianceSearch -Identity "Search All-Financial Report"
```

如需詳細資訊，請參閱[新增 ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935)。
  
### <a name="verify-the-number-of-source-mailboxes-in-the-content-search"></a>確認內容搜尋中的來源信箱數目

內容搜尋會傳回 1000 個來源信箱包含搜尋結果的最大值。如果有超過 1000 個信箱內含符合搜尋查詢的內容，僅使用大部分的搜尋結果的前 1000 個信箱並包含您在上一個步驟中建立的內容搜尋。因此如果超過 1000 個信箱包含搜尋結果，這些信箱的部分不包含在複製到新的就地 eDiscovery 搜尋在步驟 3 中建立的來源信箱的清單。 
  
為了協助您使用不超過 1000 來源信箱中建立內容的搜尋，請遵循下列步驟執行指令碼會顯示您在步驟 1 中建立的內容搜尋傳回的來源信箱 （內含搜尋結果） 數目。 
  
1. 使用.ps1 filename 尾碼儲存到 PowerShell 指令碼檔案的下列文字。例如，您無法將它儲存到名為 csv 檔案`SourceMailboxes.ps1`。
    
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

2. 安全性與規範中心 PowerShell，在移至您在上一個步驟中建立的指令碼所在的資料夾，然後執行 [指令碼 ；例如：
    
    ```
    .\SourceMailboxes.ps1
    ```

3. 當指令碼提示時，輸入您在步驟 1 中建立的內容搜尋的名稱。
    
    指令碼會顯示包含搜尋結果的來源信箱數目。
    
如果有超過 1000 個來源信箱，請嘗試建立兩個 （或多個） 內容的搜尋。例如一內容的搜尋及其他內容的搜尋中其他半中一半貴組織的信箱搜尋。您也可以變更搜尋準則以減少包含搜尋結果的信箱數目。例如，您可能包含日期範圍或調整關鍵字查詢。
  
## <a name="step-2-connect-to-the-security-amp-compliance-center-and-exchange-online-in-a-single-remote-powershell-session"></a>步驟 2： 連線至安全性&amp;規範中心和 Exchange Online 中的單一遠端 PowerShell 工作階段

下一步是連線至這兩種安全性的 Windows PowerShell&amp;規範中心和 Exchange Online 組織。因為您在步驟 3 中執行的指令碼需要存取安全性內容搜尋指令程式會視需要&amp;規範中心和 Exchange Online 中的就地 eDiscovery cmdlet。
  
1. 使用.ps1 filename 尾碼儲存到 Windows PowerShell 指令碼檔案的下列文字。例如，您無法將它儲存到名為 csv 檔案`ConnectEXO-CC.ps1`。
    
    ```
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -AllowClobber -DisableNameChecking
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. 在您的本機電腦上開啟 Windows PowerShell，移至您在上一個步驟中建立的指令碼所在的資料夾，然後執行指令碼 ；例如：
    
    ```
    .\ConnectEXO-CC.ps1
    ```

如何知道是否這是否正常運作？在您執行的指令碼指令程式的安全性之後&amp;規範中心和 Exchange Online 匯入至本機 PowerShell 工作階段。如果您沒有收到任何錯誤，您已順利連線。快速測試是執行安全性&amp;規範中心 cmdlet — 例如**安裝 UnifiedCompliancePrerequisite** — 和 Exchange Online 指令程式，例如**Get-mailbox**。 
  
## <a name="step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search"></a>步驟 3：執行指令碼以從內容搜尋建立就地 eDiscovery 搜尋

您在步驟 2 中建立雙 PowerShell 工作階段後下, 一步是執行指令碼會將現有的內容搜尋轉換為 「 就地 eDiscovery 搜尋。這裡就是什麼指令碼：
  
- 提示您輸入要轉換的內容搜尋的名稱。
    
- 確認內容搜尋已完成執行。如果內容搜尋未傳回任何結果，就不會建立就地 eDiscovery。
    
- 從包含搜尋結果的內容搜尋將來源信箱的清單儲存至變數。
    
- 建立新的就地 eDiscovery 搜尋，具有下列屬性。請注意，並未啟動新的搜尋。您將在步驟 4 中加以啟動。
    
  - **名稱**-新的搜尋的名稱會使用此格式：\<內容搜尋名稱\>_MBSearch1。如果您再次執行指令碼並使用相同的來源內容搜尋，將名為搜尋\<內容搜尋名稱\>_MBSearch2。
    
  - **來源信箱**-所有信箱內容的搜尋從內含搜尋結果。 
    
  - **搜尋查詢**的新搜尋會使用搜尋查詢的內容搜尋。如果內容搜尋包含所有的內容 （其中搜尋查詢是空白） 的新搜尋也將具有空白搜尋查詢和就會包含在來源信箱中找到的所有內容。 
    
  - **評估僅搜尋**-新的搜尋已標示為僅限評估的搜尋。它將不會將搜尋結果複製到探索信箱後啟動它。 
    
1. 使用 ps1 filename 尾碼儲存到 Windows PowerShell 指令碼檔案的下列文字。例如，您無法將它儲存到名為 csv 檔案`CreateMBSearchFromComplianceSearch.ps1`。
    
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

2. 在您在步驟 2 中建立 Windows PowerShell 工作階段中移至您在上一個步驟中建立的指令碼所在的資料夾，然後執行 [指令碼 ；例如：
    
    ```
    .\CreateMBSearchFromComplianceSearch.ps1
    ```

3. 出現提示時所指令碼，輸入您想要轉換為 「 就地 eDiscovery 搜尋 （例如搜尋您在步驟 1 中建立），內容搜尋的名稱，然後按**Enter**。
    
    如果成功，指令碼，新的就地 eDiscovery 搜尋會建立**為 NotStarted**的狀態。執行命令`Get-MailboxSearch <Name of Content Search>_MBSearch1 | FL`以顯示新的搜尋的屬性。 
  
## <a name="step-4-start-the-in-place-ediscovery-search"></a>步驟 4：啟動就地 eDiscovery 搜尋

您在步驟 3 中執行的指令碼會建立新的就地 eDiscovery 搜尋，但不會啟動。下一個步驟是啟動搜尋，讓您取得搜尋結果的預估。
  
1. 在 Exchange 系統管理中心 (EAC) 中，移至 [**相符性管理** \> **就地 eDiscovery&amp;保留**。
    
2. 在清單檢視中，選取您在步驟 3 中建立的就地 eDiscovery 搜尋。
    
3. 按一下 [**搜尋**]![搜尋圖示](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif) \> **預估搜尋結果**開始搜尋及傳回的估計項目總大小和搜尋傳回的項目數。 
    
    在詳細資料窗格中顯示預估值。按一下 [**重新整理**![重新整理] 圖示](media/O365-MDM-Policy-RefreshIcon.gif)要更新的詳細資料窗格中顯示的資訊。 
    
4. 若要預覽結果在搜尋完成後，請按一下 [詳細資料窗格中的**預覽搜尋結果**。
  
## <a name="next-steps-after-creating-and-running-the-in-place-ediscovery-search"></a>建立和執行就地 eDiscovery 搜尋之後接下來的步驟

建立並啟動步驟 3 中的指令碼建立的就地 eDiscovery 搜尋之後，您可以使用一般的就地 eDiscovery 工作流程在搜尋結果上執行不同的 eDiscovery 動作。
  
### <a name="create-an-in-place-hold"></a>建立就地保留

1. 在 EAC 中，移至 [**規範管理** \> **就地 eDiscovery&amp;保留**。
    
2. 在清單檢視中，選取您在步驟 3 中建立就地 eDiscovery 搜尋] 和 [**編輯**![編輯圖示](media/O365_MDM_CreatePolicy_EditIcon.gif)。
    
3. 在**就地保留功能**] 頁面上選取 [**比對搜尋查詢中所選取的信箱上進行內容保留**] 核取方塊，然後選取下列選項之一： 
    
  - **無限期保留**-選擇這個選項會放置在搜尋傳回設為無限期保留項目。除非您移除搜尋信箱或移除搜尋則保留音樂的項目。 
    
  - **指定天數以保留項目相對於其接收日期**-選擇此選項可在特定期間內保留項目。信箱項目會接收或建立日期被計算持續時間。 
    
4. 按一下 [**儲存**] 以建立就地保留和重新啟動搜尋。 
    
[回到頁首](use-content-search-in-ediscovery.md#top)
  
### <a name="copy-the-search-results"></a>複製搜尋結果

1. 在 EAC 中，移至 [**規範管理** \> **就地 eDiscovery&amp;保留**。
    
2. 在清單檢視中，選取您在步驟 3 中建立的就地 eDiscovery 搜尋。
    
3. 按一下 [**搜尋**]![搜尋圖示](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif)，然後從下拉式清單中按一下 [**複製搜尋結果**。 
    
4. **複製搜尋結果**中選取 [從下列選項：
    
    - **包含無法搜尋的項目**-選取此核取方塊包含無法搜尋 （例如無法依 Exchange 搜尋編製索引的檔案類型附件的郵件） 的信箱項目。 
    
    - **啟用重複資料刪除**-選取此核取方塊來排除重複的郵件。要在單一執行個體的訊息複製到探索信箱。 
    
    - **啟用完整的記錄**-選取此核取方塊可在搜尋結果中包含完整的記錄檔。 
    
    - **將郵件複製完成時傳送我**-選取此核取方塊可搜尋完成時要取得的電子郵件通知。 
    
    - **複製到此探索信箱的結果**集按一下以選取您想要在搜尋結果的探索信箱的 [**瀏覽**複製到。 
    
5. 按一下 [**複製**到啟動程序來將搜尋結果複製到指定的探索信箱。 
    
6. 按一下 [**重新整理**![重新整理] 圖示](media/O365-MDM-Policy-RefreshIcon.gif)來更新顯示在 [詳細資料] 窗格中的複製狀態的相關資訊。 
    
7. 複製完成後，請按一下 [開啟要檢視搜尋結果的探索信箱的 [**開啟**]。 
  
### <a name="export-the-search-results"></a>匯出搜尋結果

1. 在 EAC 中，移至 [**規範管理** \> **就地 eDiscovery&amp;保留**。
    
2. 在清單檢視中，選取您在步驟 3 中建立就地 eDiscovery 搜尋和 [**匯出至 PST 檔案**。
    
3. 在 [ **eDiscovery PST 匯出工具**] 視窗中，執行下列動作： 
    
    - 按一下 [**瀏覽]** 以指定您要下載 PST 檔案的位置。 
    
    - 按一下 [**啟用 deduplication** ] 核取方塊來排除重複的郵件。單一執行個體的訊息將會包含在 PST 檔案。 
    
    - 按一下 [**包含無法搜尋的項目**] 核取方塊以包含無法搜尋 （例如無法依 Exchange 搜尋編製索引的檔案類型附件的郵件） 的信箱項目。無法搜尋的項目都要匯出至不同的 PST 檔案。 
    
4. 按一下 [搜尋結果匯出至 PST 檔案的 [**啟動**]。 
    
    包含匯出程序狀態資訊的視窗便會隨即顯示。
