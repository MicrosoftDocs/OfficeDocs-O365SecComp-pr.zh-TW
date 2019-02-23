---
title: 在您的 eDiscovery 工作流程中使用內容搜尋
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 55f31488-288a-473a-9b9e-831a11e3711a
description: '使用 PowerShell 指令碼的就地 eDiscovery 搜尋在 Exchange Online 建立根據搜尋建立 Office 365 安全性&amp;規範中心。 '
ms.openlocfilehash: fff50b7dcd89790c84bb2911f560ce1b061b8f17
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216043"
---
# <a name="use-content-search-in-your-ediscovery-workflow"></a><span data-ttu-id="fb40e-103">在您的 eDiscovery 工作流程中使用內容搜尋</span><span class="sxs-lookup"><span data-stu-id="fb40e-103">Use Content Search in your eDiscovery workflow</span></span>

<span data-ttu-id="fb40e-p101">Office 365 安全性內容的搜尋功能&amp;規範中心 」 可讓您在組織中搜尋所有信箱。不同 Exchange Online （其中您可以搜尋最多 10000 個信箱） 中的就地 eDiscovery 有單一搜尋中的目標信箱數目沒有限制。如需要執行整個組織搜尋的案例，您可以使用內容搜尋來搜尋所有信箱。然後您可以使用就地 eDiscovery 的工作流程功能來執行其他 eDiscovery 相關工作，例如將信箱保留與匯出搜尋結果。例如，假設您有搜尋所有信箱移轉至識別回應法律案例的特定 custodians。您可以使用內容的搜尋安全性&amp;規範中心來識別回應案例的組織中搜尋所有信箱。然後您可以使用 okay 信箱該清單為來源信箱的 Exchange Online 中的就地 eDiscovery 搜尋。使用就地 eDiscovery 也可讓您將這些來源信箱上設定保留、 將搜尋結果複製到探索信箱和匯出搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="fb40e-p101">The Content Search feature in the Office 365 Security &amp; Compliance Center allows you to search all mailboxes in your organization. Unlike In-Place eDiscovery in Exchange Online (where you can search up to 10,000 mailboxes), there are no limits for the number of target mailboxes in a single search. For scenarios that require you to perform organization-wide searches, you can use Content Search to search all mailboxes. Then you can use the workflow features of In-Place eDiscovery to perform other eDiscovery-related tasks, such as placing mailboxes on hold and exporting search results. For example, let's say you have to search all mailboxes to identify specific custodians that are responsive to a legal case. You can use Content Search in the Security &amp; Compliance Center to search all mailboxes in your organization to identify those that are responsive to the case. Then you can use that list of custodian mailboxes as the source mailboxes for an In-Place eDiscovery search in Exchange Online. Using In-Place eDiscovery also allows you to put a hold on those source mailboxes, copy search results to a discovery mailbox, and export the search results.</span></span>
  
<span data-ttu-id="fb40e-p102">本主題包含您可以使用來源信箱和搜尋安全性中建立的搜尋查詢的清單建立就地 eDiscovery 搜尋在 Exchange Online 中執行的指令碼&amp;規範中心。以下是程序概觀：</span><span class="sxs-lookup"><span data-stu-id="fb40e-p102">This topic includes a script that you can run to create an In-Place eDiscovery search in Exchange Online by using the list of source mailboxes and search query from a search created in the Security &amp; Compliance Center. Here's an overview of the process:</span></span>
  
[<span data-ttu-id="fb40e-114">步驟 1：建立「內容搜尋」來搜尋組織中的所有信箱</span><span class="sxs-lookup"><span data-stu-id="fb40e-114">Step 1: Create a Content Search to search all mailboxes in your organization</span></span>](#step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization)

[<span data-ttu-id="fb40e-115">步驟 2： 連線至安全性&amp;規範中心和 Exchange Online 中的單一遠端 PowerShell 工作階段</span><span class="sxs-lookup"><span data-stu-id="fb40e-115">Step 2: Connect to the Security &amp; Compliance Center and Exchange Online in a single remote PowerShell session</span></span>](#step-2-connect-to-the-security-amp-compliance-center-and-exchange-online-in-a-single-remote-powershell-session)
  
[<span data-ttu-id="fb40e-116">步驟 3：執行指令碼以從內容搜尋建立就地 eDiscovery 搜尋</span><span class="sxs-lookup"><span data-stu-id="fb40e-116">Step 3: Run the script to create an In-Place eDiscovery search from the Content Search</span></span>](#step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search)

[<span data-ttu-id="fb40e-117">步驟 4：啟動就地 eDiscovery 搜尋</span><span class="sxs-lookup"><span data-stu-id="fb40e-117">Step 4: Start the In-Place eDiscovery search</span></span>](#step-4-start-the-in-place-ediscovery-search)

## <a name="step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization"></a><span data-ttu-id="fb40e-118">步驟 1：建立「內容搜尋」來搜尋組織中的所有信箱</span><span class="sxs-lookup"><span data-stu-id="fb40e-118">Step 1: Create a Content Search to search all mailboxes in your organization</span></span>

<span data-ttu-id="fb40e-p103">第一個步驟是使用安全性&amp;規範中心 （或安全性 & 規範中心 PowerShell） 建立搜尋組織中所有信箱內容搜尋。有單一的內容搜尋沒有限制的信箱數目。指定適當的關鍵字查詢 （或查詢的敏感資訊類型） 搜尋會傳回與您正在調查的來源信箱。如有必要，調整搜尋查詢來縮小搜尋結果與來源信箱所傳回的範圍。</span><span class="sxs-lookup"><span data-stu-id="fb40e-p103">The first step is to use the Security &amp; Compliance Center (or Security & Compliance Center PowerShell) to create a Content Search that searches all mailboxes in your organization. There's no limit for the number of mailboxes for a single Content Search. Specify an appropriate keyword query (or a query for sensitive information types) so that the search returns only those source mailboxes that are relevant to your investigation. If necessary, refine the search query to narrow the scope of search results and source mailboxes that are returned.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fb40e-p104">如果來源內容搜尋沒有傳回任何結果，當您在步驟 3 中執行指令碼時不會建立就地 eDiscovery。您可能必須修改搜尋查詢然後重新執行內容搜尋以傳回搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="fb40e-p104">If the source Content Search doesn't return any results, an In-Place eDiscovery won't be created when you run the script in Step 3. You may have to revise the search query then rerun the Content Search to return search results.</span></span> 
  
### <a name="use-the-security-amp-compliance-center-to-search-all-mailboxes"></a><span data-ttu-id="fb40e-125">使用安全性&amp;規範中心來搜尋所有信箱</span><span class="sxs-lookup"><span data-stu-id="fb40e-125">Use the Security &amp; Compliance Center to search all mailboxes</span></span>

1. <span data-ttu-id="fb40e-126">[移至 Office 365 安全性&amp;規範中心](go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="fb40e-126">[Go to the Office 365 Security &amp; Compliance Center](go-to-the-securitycompliance-center.md).</span></span> 
    
2. <span data-ttu-id="fb40e-127">按一下 [**搜尋&amp;調查**、 按一下 [**內容搜尋**] 及 [**新增**![新增圖示](media/O365-MDM-CreatePolicy-AddIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="fb40e-127">Click **Search &amp; investigation**, click **Content search**, and then click **New** ![Add icon](media/O365-MDM-CreatePolicy-AddIcon.gif).</span></span>
    
3. <span data-ttu-id="fb40e-128">在 **[新增搜尋]** 頁面上，輸入內容搜尋的名稱。</span><span class="sxs-lookup"><span data-stu-id="fb40e-128">On the **New search** page, type a name for the Content Search.</span></span> 
    
4. <span data-ttu-id="fb40e-129">下**出您想我們要尋找？**、 按一下 [**搜尋所有信箱**，並再按 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="fb40e-129">Under **Where do you want us to look?**, click **Search all mailboxes**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="fb40e-p105">在下] 方塊中**您想什麼我們要尋找的？**、] 方塊中輸入搜尋查詢。您可以指定關鍵字，訊息屬性例如傳送及接收日期或文件內容，例如檔案名稱或上次變更文件的日期。您可以使用較複雜的查詢不使用布林運算子，例如 AND、 OR 或靠近，或是您也可搜尋的訊息中的機密資訊 （例如社會安全編號）。如需建立搜尋查詢的詳細資訊，請參閱 ＜[內容搜尋的關鍵字查詢](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="fb40e-p105">In the box under **What do you want us to look for?**, type a search query in the box. You can specify keywords, message properties such as sent and received dates, or document properties such as file names or the date that a document was last changed. You can use a more complex queries that use a Boolean operator, such as AND, OR, NOT or NEAR, or you can also search for sensitive information (such as social security numbers) in messages. For more information about creating search queries, see [Keyword queries for Content Search](keyword-queries-and-search-conditions.md).</span></span>
    
6. <span data-ttu-id="fb40e-134">按一下 [**搜尋**] 以儲存搜尋設定並啟動搜尋。</span><span class="sxs-lookup"><span data-stu-id="fb40e-134">Click **Search** to save the search settings and start the search.</span></span> 
    
    <span data-ttu-id="fb40e-p106">While 之後評估會有搜尋結果顯示詳細資料窗格中。評估包含總大小及搜尋結果的項目數。搜尋完成後，您可預覽搜尋結果。若有必要，請按一下 [**重新整理**![重新整理] 圖示](media/O365-MDM-Policy-RefreshIcon.gif)要更新的詳細資料窗格中的資訊。</span><span class="sxs-lookup"><span data-stu-id="fb40e-p106">After a while, an estimate of the search results displayed in the details pane. The estimate includes the total size and number of items for the search results. After the search is completed, you can preview the search results. If necessary, click **Refresh**![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
7.  <span data-ttu-id="fb40e-139">如有必要，縮小搜尋查詢以縮小搜尋結果的範圍然後重新啟動搜尋。</span><span class="sxs-lookup"><span data-stu-id="fb40e-139">If necessary, refine the search query to narrow the scope of search results and then restart the search.</span></span> 
    
### <a name="use-security--compliance-center-powershell-to-search-all-mailboxes"></a><span data-ttu-id="fb40e-140">使用安全性 & 規範中心 PowerShell 搜尋所有信箱</span><span class="sxs-lookup"><span data-stu-id="fb40e-140">Use Security & Compliance Center PowerShell to search all mailboxes</span></span>

<span data-ttu-id="fb40e-p107">您也可以使用**New ComplianceSearch**指令程式來搜尋您組織中所有信箱。第一個步驟是[連線至 Office 365 安全性&amp;規範中心 PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=627084)。</span><span class="sxs-lookup"><span data-stu-id="fb40e-p107">You can also use the **New-ComplianceSearch** cmdlet to search all mailboxes in your organization. The first step is to [Connect to Office 365 Security &amp; Compliance Center PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=627084).</span></span>
  
<span data-ttu-id="fb40e-p108">以下是使用 PowerShell 來搜尋您組織中所有信箱的範例。搜尋查詢會傳回 2015 年 1 月 1、 和 2015 年 6 月 30，之間傳送的所有郵件及可包含片語主旨行中的 「 財務 report"。第一個命令會建立搜尋和第二個命令會執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="fb40e-p108">Here's an example of using PowerShell to search all mailboxes in your organization. The search query returns all messages sent between January 1, 2015 and June 30, 2015 and that contain the phrase "financial report" in the subject line. The first command creates the search, and the second command runs the search.</span></span> 
  
```
New-ComplianceSearch -Name "Search All-Financial Report" -ExchangeLocation all -ContentMatchQuery 'sent>=01/01/2015 AND sent<=06/30/2015 AND subject:"financial report"'
```

```
Start-ComplianceSearch -Identity "Search All-Financial Report"
```

<span data-ttu-id="fb40e-146">如需詳細資訊，請參閱[新增 ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935)。</span><span class="sxs-lookup"><span data-stu-id="fb40e-146">For more information, see [New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935).</span></span>
  
### <a name="verify-the-number-of-source-mailboxes-in-the-content-search"></a><span data-ttu-id="fb40e-147">確認內容搜尋中的來源信箱數目</span><span class="sxs-lookup"><span data-stu-id="fb40e-147">Verify the number of source mailboxes in the Content Search</span></span>

<span data-ttu-id="fb40e-p109">內容搜尋會傳回 1000 個來源信箱包含搜尋結果的最大值。如果有超過 1000 個信箱內含符合搜尋查詢的內容，僅使用大部分的搜尋結果的前 1000 個信箱並包含您在上一個步驟中建立的內容搜尋。因此如果超過 1000 個信箱包含搜尋結果，這些信箱的部分不包含在複製到新的就地 eDiscovery 搜尋在步驟 3 中建立的來源信箱的清單。</span><span class="sxs-lookup"><span data-stu-id="fb40e-p109">A Content Search returns a maximum of 1,000 source mailboxes that contain search results. If there are more than 1,000 mailboxes that contain content that matches the search query, only the top 1,000 mailboxes with the most search results are included in the Content Search that you created in the previous step. So if more than 1,000 mailboxes contain search results, some of those mailboxes won't be included in the list of source mailboxes copied to the new In-Place eDiscovery search created in Step 3.</span></span> 
  
<span data-ttu-id="fb40e-151">為了協助您使用不超過 1000 來源信箱中建立內容的搜尋，請遵循下列步驟執行指令碼會顯示您在步驟 1 中建立的內容搜尋傳回的來源信箱 （內含搜尋結果） 數目。</span><span class="sxs-lookup"><span data-stu-id="fb40e-151">To help you create a Content Search with no more than 1,000 source mailboxes, follow these steps to run a script that displays the number of source mailboxes (that contain search results) returned by the Content Search you created in Step 1.</span></span> 
  
1. <span data-ttu-id="fb40e-p110">使用.ps1 filename 尾碼儲存到 PowerShell 指令碼檔案的下列文字。例如，您無法將它儲存到名為 csv 檔案`SourceMailboxes.ps1`。</span><span class="sxs-lookup"><span data-stu-id="fb40e-p110">Save the following text to a PowerShell script file by using a filename suffix of .ps1. For example, you could save it to a file named `SourceMailboxes.ps1`.</span></span>
    
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

2. <span data-ttu-id="fb40e-154">在安全性 & 規範中心 PowerShell，移至您在上一個步驟中建立的指令碼所在的資料夾，然後執行 [指令碼 ；例如：</span><span class="sxs-lookup"><span data-stu-id="fb40e-154">In Security & Compliance Center PowerShell, go to the folder where the script you created in the previous step is located, and then run the script; for example:</span></span>
    
    ```
    .\SourceMailboxes.ps1
    ```

3. <span data-ttu-id="fb40e-155">當指令碼提示時，輸入您在步驟 1 中建立的內容搜尋的名稱。</span><span class="sxs-lookup"><span data-stu-id="fb40e-155">When prompted by the script, type the name of the Content Search that you created in Step 1.</span></span>
    
    <span data-ttu-id="fb40e-156">指令碼會顯示包含搜尋結果的來源信箱數目。</span><span class="sxs-lookup"><span data-stu-id="fb40e-156">The script displays the number of source mailboxes that contain search results.</span></span>
    
<span data-ttu-id="fb40e-p111">如果有超過 1000 個來源信箱，請嘗試建立兩個 （或多個） 內容的搜尋。例如一內容的搜尋及其他內容的搜尋中其他半中一半貴組織的信箱搜尋。您也可以變更搜尋準則以減少包含搜尋結果的信箱數目。例如，您可能包含日期範圍或調整關鍵字查詢。</span><span class="sxs-lookup"><span data-stu-id="fb40e-p111">If there are more than 1,000 source mailboxes, try creating two (or more) Content Searches. For example, search half of your organization's mailboxes in one Content Search and the other half in another Content Search. You could also change the search criteria to reduce the number of mailboxes that contain search results. For example, you could include a date range or refine the keyword query.</span></span>
  
## <a name="step-2-connect-to-the-security-amp-compliance-center-and-exchange-online-in-a-single-remote-powershell-session"></a><span data-ttu-id="fb40e-161">步驟 2： 連線至安全性&amp;規範中心和 Exchange Online 中的單一遠端 PowerShell 工作階段</span><span class="sxs-lookup"><span data-stu-id="fb40e-161">Step 2: Connect to the Security &amp; Compliance Center and Exchange Online in a single remote PowerShell session</span></span>

<span data-ttu-id="fb40e-p112">下一步是連線至這兩種安全性的 Windows PowerShell&amp;規範中心和 Exchange Online 組織。因為您在步驟 3 中執行的指令碼需要存取安全性內容搜尋指令程式會視需要&amp;規範中心和 Exchange Online 中的就地 eDiscovery cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fb40e-p112">The next step is to connect Windows PowerShell to both the Security &amp; Compliance Center and to your Exchange Online organization. This is necessary because the script that you run in Step 3 requires access to the Content Search cmdlets in the Security &amp; Compliance Center and the In-Place eDiscovery cmdlets in Exchange Online.</span></span>
  
1. <span data-ttu-id="fb40e-p113">使用.ps1 filename 尾碼儲存到 Windows PowerShell 指令碼檔案的下列文字。例如，您無法將它儲存到名為 csv 檔案`ConnectEXO-CC.ps1`。</span><span class="sxs-lookup"><span data-stu-id="fb40e-p113">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1. For example, you could save it to a file named `ConnectEXO-CC.ps1`.</span></span>
    
    ```
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -AllowClobber -DisableNameChecking
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. <span data-ttu-id="fb40e-166">在您的本機電腦上開啟 Windows PowerShell，移至您在上一個步驟中建立的指令碼所在的資料夾，然後執行指令碼 ；例如：</span><span class="sxs-lookup"><span data-stu-id="fb40e-166">On your local computer, open Windows PowerShell, go to the folder where the script that you created in the previous step is located, and then run the script; for example:</span></span>
    
    ```
    .\ConnectEXO-CC.ps1
    ```

<span data-ttu-id="fb40e-p114">如何知道是否這是否正常運作？在您執行的指令碼指令程式的安全性之後&amp;規範中心和 Exchange Online 匯入至本機 PowerShell 工作階段。如果您沒有收到任何錯誤，您已順利連線。快速測試是執行安全性&amp;規範中心 cmdlet — 例如**安裝 UnifiedCompliancePrerequisite** — 和 Exchange Online 指令程式，例如**Get-mailbox**。</span><span class="sxs-lookup"><span data-stu-id="fb40e-p114">How do you know if this worked? After you run the script, cmdlets from the Security &amp; Compliance Center and Exchange Online are imported into your local PowerShell session. If you don't receive any errors, you connected successfully. A quick test is to run a Security &amp; Compliance Center cmdlet—for example, **Install-UnifiedCompliancePrerequisite** —and an Exchange Online cmdlet, such as **Get-Mailbox**.</span></span> 
  
## <a name="step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search"></a><span data-ttu-id="fb40e-171">步驟 3：執行指令碼以從內容搜尋建立就地 eDiscovery 搜尋</span><span class="sxs-lookup"><span data-stu-id="fb40e-171">Step 3: Run the script to create an In-Place eDiscovery search from the Content Search</span></span>

<span data-ttu-id="fb40e-p115">您在步驟 2 中建立雙 PowerShell 工作階段後下, 一步是執行指令碼會將現有的內容搜尋轉換為 「 就地 eDiscovery 搜尋。這裡就是什麼指令碼：</span><span class="sxs-lookup"><span data-stu-id="fb40e-p115">After you create the dual PowerShell session in Step 2, the next step is to run a script that will convert an existing Content Search to an In-Place eDiscovery search. Here's what the script does:</span></span>
  
- <span data-ttu-id="fb40e-174">提示您輸入要轉換的內容搜尋的名稱。</span><span class="sxs-lookup"><span data-stu-id="fb40e-174">Prompts you for the name of the Content Search to convert.</span></span>
    
- <span data-ttu-id="fb40e-p116">確認內容搜尋已完成執行。如果內容搜尋未傳回任何結果，就不會建立就地 eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="fb40e-p116">Verifies that the Content Search has completed running. If the Content Search doesn't return any results, and In-Place eDiscovery won't be created.</span></span>
    
- <span data-ttu-id="fb40e-177">從包含搜尋結果的內容搜尋將來源信箱的清單儲存至變數。</span><span class="sxs-lookup"><span data-stu-id="fb40e-177">Saves a list of the source mailboxes from the Content Search that contain search results to a variable.</span></span>
    
- <span data-ttu-id="fb40e-p117">建立新的就地 eDiscovery 搜尋，具有下列屬性。請注意，並未啟動新的搜尋。您將在步驟 4 中加以啟動。</span><span class="sxs-lookup"><span data-stu-id="fb40e-p117">Creates a new In-Place eDiscovery search, with the following properties. Note that the new search isn't started. You'll start it in step 4.</span></span>
    
  - <span data-ttu-id="fb40e-p118">**名稱**-新的搜尋的名稱會使用此格式：\<內容搜尋名稱\>_MBSearch1。如果您再次執行指令碼並使用相同的來源內容搜尋，將名為搜尋\<內容搜尋名稱\>_MBSearch2。</span><span class="sxs-lookup"><span data-stu-id="fb40e-p118">**Name** - The name of the new search uses this format: \<Name of Content Search\>_MBSearch1. If you run the script again and use the same source Content Search, the search will be named \<Name of Content Search\>_MBSearch2.</span></span>
    
  - <span data-ttu-id="fb40e-183">**來源信箱**-所有信箱內容的搜尋從內含搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="fb40e-183">**Source mailboxes** - All mailboxes from the Content Search that contain search results.</span></span> 
    
  - <span data-ttu-id="fb40e-p119">**搜尋查詢**的新搜尋會使用搜尋查詢的內容搜尋。如果內容搜尋包含所有的內容 （其中搜尋查詢是空白） 的新搜尋也將具有空白搜尋查詢和就會包含在來源信箱中找到的所有內容。</span><span class="sxs-lookup"><span data-stu-id="fb40e-p119">**Search query** - The new search uses the search query from the Content Search. If the Content Search includes all content (where the search query is blank) the new search will also have a blank search query and will include all content found in the source mailboxes.</span></span> 
    
  - <span data-ttu-id="fb40e-p120">**評估僅搜尋**-新的搜尋已標示為僅限評估的搜尋。它將不會將搜尋結果複製到探索信箱後啟動它。</span><span class="sxs-lookup"><span data-stu-id="fb40e-p120">**Estimate only search** - The new search is marked as an estimate-only search. It won't copy search results to a discovery mailbox after you start it.</span></span> 
    
1. <span data-ttu-id="fb40e-p121">使用 ps1 filename 尾碼儲存到 Windows PowerShell 指令碼檔案的下列文字。例如，您無法將它儲存到名為 csv 檔案`CreateMBSearchFromComplianceSearch.ps1`。</span><span class="sxs-lookup"><span data-stu-id="fb40e-p121">Save the following text to a Windows PowerShell script file by using a filename suffix of ps1. For example, you could save it to a file named `CreateMBSearchFromComplianceSearch.ps1`.</span></span>
    
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

2. <span data-ttu-id="fb40e-190">在您在步驟 2 中建立 Windows PowerShell 工作階段中移至您在上一個步驟中建立的指令碼所在的資料夾，然後執行 [指令碼 ；例如：</span><span class="sxs-lookup"><span data-stu-id="fb40e-190">In the Windows PowerShell session that you created in Step 2, go to the folder where the script that you created in the previous step is located, and then run the script; for example:</span></span>
    
    ```
    .\CreateMBSearchFromComplianceSearch.ps1
    ```

3. <span data-ttu-id="fb40e-191">出現提示時所指令碼，輸入您想要轉換為 「 就地 eDiscovery 搜尋 （例如搜尋您在步驟 1 中建立），內容搜尋的名稱，然後按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="fb40e-191">When prompted by the script, type the name of the Content Search that you want to covert to an In-Place eDiscovery search (for example, the search that you created in Step 1), and then press **Enter**.</span></span>
    
    <span data-ttu-id="fb40e-p122">如果成功，指令碼，新的就地 eDiscovery 搜尋會建立**為 NotStarted**的狀態。執行命令`Get-MailboxSearch <Name of Content Search>_MBSearch1 | FL`以顯示新的搜尋的屬性。</span><span class="sxs-lookup"><span data-stu-id="fb40e-p122">If the script is successful, a new In-Place eDiscovery search is created with a status of **NotStarted**. Run the command  `Get-MailboxSearch <Name of Content Search>_MBSearch1 | FL` to display the properties of the new search.</span></span> 
  
## <a name="step-4-start-the-in-place-ediscovery-search"></a><span data-ttu-id="fb40e-194">步驟 4：啟動就地 eDiscovery 搜尋</span><span class="sxs-lookup"><span data-stu-id="fb40e-194">Step 4: Start the In-Place eDiscovery search</span></span>

<span data-ttu-id="fb40e-p123">您在步驟 3 中執行的指令碼會建立新的就地 eDiscovery 搜尋，但不會啟動。下一個步驟是啟動搜尋，讓您取得搜尋結果的預估。</span><span class="sxs-lookup"><span data-stu-id="fb40e-p123">The script that you run in Step 3 creates a new In-Place eDiscovery search, but doesn't start it. The next step is to start the search so you can get an estimate of the search results.</span></span>
  
1. <span data-ttu-id="fb40e-197">在 Exchange 系統管理中心 (EAC) 中，移至 [**相符性管理** \> **就地 eDiscovery&amp;保留**。</span><span class="sxs-lookup"><span data-stu-id="fb40e-197">In the Exchange admin center (EAC), go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="fb40e-198">在清單檢視中，選取您在步驟 3 中建立的就地 eDiscovery 搜尋。</span><span class="sxs-lookup"><span data-stu-id="fb40e-198">In the list view, select the In-Place eDiscovery search that you created in Step 3.</span></span>
    
3. <span data-ttu-id="fb40e-199">按一下 [**搜尋**]![搜尋圖示](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif) \> **預估搜尋結果**開始搜尋及傳回的估計項目總大小和搜尋傳回的項目數。</span><span class="sxs-lookup"><span data-stu-id="fb40e-199">Click **Search** ![Search icon](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif) \> **Estimate search results** to start the search and return an estimate of the total size and number of items returned by the search.</span></span> 
    
    <span data-ttu-id="fb40e-p124">在詳細資料窗格中顯示預估值。按一下 [**重新整理**![重新整理] 圖示](media/O365-MDM-Policy-RefreshIcon.gif)要更新的詳細資料窗格中顯示的資訊。</span><span class="sxs-lookup"><span data-stu-id="fb40e-p124">The estimates are displayed in the details pane. Click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information displayed in the details pane.</span></span> 
    
4. <span data-ttu-id="fb40e-202">若要預覽結果在搜尋完成後，請按一下 [詳細資料窗格中的**預覽搜尋結果**。</span><span class="sxs-lookup"><span data-stu-id="fb40e-202">To preview the results after the search is completed, click **Preview search results** in the details pane.</span></span>
  
## <a name="next-steps-after-creating-and-running-the-in-place-ediscovery-search"></a><span data-ttu-id="fb40e-203">建立和執行就地 eDiscovery 搜尋之後接下來的步驟</span><span class="sxs-lookup"><span data-stu-id="fb40e-203">Next steps after creating and running the In-Place eDiscovery search</span></span>

<span data-ttu-id="fb40e-204">建立並啟動步驟 3 中的指令碼建立的就地 eDiscovery 搜尋之後，您可以使用一般的就地 eDiscovery 工作流程在搜尋結果上執行不同的 eDiscovery 動作。</span><span class="sxs-lookup"><span data-stu-id="fb40e-204">After you create and start the In-Place eDiscovery search that was created by the script in Step 3, you can use the normal In-Place eDiscovery workflow to perform different eDiscovery actions on the search results.</span></span>
  
### <a name="create-an-in-place-hold"></a><span data-ttu-id="fb40e-205">建立就地保留</span><span class="sxs-lookup"><span data-stu-id="fb40e-205">Create an In-Place Hold</span></span>

1. <span data-ttu-id="fb40e-206">在 EAC 中，移至 [**規範管理** \> **就地 eDiscovery&amp;保留**。</span><span class="sxs-lookup"><span data-stu-id="fb40e-206">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="fb40e-207">在清單檢視中，選取您在步驟 3 中建立就地 eDiscovery 搜尋] 和 [**編輯**![編輯圖示](media/O365_MDM_CreatePolicy_EditIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="fb40e-207">In the list view, select the In-Place eDiscovery search that you created in Step 3, and then click **Edit** ![Edit icon](media/O365_MDM_CreatePolicy_EditIcon.gif).</span></span>
    
3. <span data-ttu-id="fb40e-208">在**就地保留功能**] 頁面上選取 [**比對搜尋查詢中所選取的信箱上進行內容保留**] 核取方塊，然後選取下列選項之一：</span><span class="sxs-lookup"><span data-stu-id="fb40e-208">On the **In-Place Hold** page, select the **Place content matching the search query in selected mailboxes on hold** check box and then select one of the following options:</span></span> 
    
  - <span data-ttu-id="fb40e-p125">**無限期保留**-選擇這個選項會放置在搜尋傳回設為無限期保留項目。除非您移除搜尋信箱或移除搜尋則保留音樂的項目。</span><span class="sxs-lookup"><span data-stu-id="fb40e-p125">**Hold indefinitely** - Choose this option to place items returned by the search on an indefinite hold. Items on hold will be preserved until you remove the mailbox from the search or remove the search.</span></span> 
    
  - <span data-ttu-id="fb40e-p126">**指定天數以保留項目相對於其接收日期**-選擇此選項可在特定期間內保留項目。信箱項目會接收或建立日期被計算持續時間。</span><span class="sxs-lookup"><span data-stu-id="fb40e-p126">**Specify number of days to hold items relative to their received date** - Choose this option to hold items for a specific period. The duration is calculated from the date a mailbox item is received or created.</span></span> 
    
4. <span data-ttu-id="fb40e-213">按一下 [**儲存**] 以建立就地保留和重新啟動搜尋。</span><span class="sxs-lookup"><span data-stu-id="fb40e-213">Click **Save** to create the In-Place Hold and restart the search.</span></span> 
    
[<span data-ttu-id="fb40e-214">回到頁首</span><span class="sxs-lookup"><span data-stu-id="fb40e-214">Return to top</span></span>](use-content-search-in-ediscovery.md#top)
  
### <a name="copy-the-search-results"></a><span data-ttu-id="fb40e-215">複製搜尋結果</span><span class="sxs-lookup"><span data-stu-id="fb40e-215">Copy the search results</span></span>

1. <span data-ttu-id="fb40e-216">在 EAC 中，移至 [**規範管理** \> **就地 eDiscovery&amp;保留**。</span><span class="sxs-lookup"><span data-stu-id="fb40e-216">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="fb40e-217">在清單檢視中，選取您在步驟 3 中建立的就地 eDiscovery 搜尋。</span><span class="sxs-lookup"><span data-stu-id="fb40e-217">In the list view, select the In-Place eDiscovery search that you created in Step 3.</span></span>
    
3. <span data-ttu-id="fb40e-218">按一下 [**搜尋**]![搜尋圖示](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif)，然後從下拉式清單中按一下 [**複製搜尋結果**。</span><span class="sxs-lookup"><span data-stu-id="fb40e-218">Click **Search** ![Search icon](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif), and then click **Copy search results** from the drop-down list.</span></span> 
    
4. <span data-ttu-id="fb40e-219">**複製搜尋結果**中選取 [從下列選項：</span><span class="sxs-lookup"><span data-stu-id="fb40e-219">In **Copy Search Results**, select from the following options:</span></span>
    
    - <span data-ttu-id="fb40e-220">**包含無法搜尋的項目**-選取此核取方塊包含無法搜尋 （例如無法依 Exchange 搜尋編製索引的檔案類型附件的郵件） 的信箱項目。</span><span class="sxs-lookup"><span data-stu-id="fb40e-220">**Include unsearchable items** - Select this check box to include mailbox items that couldn't be searched (for example, messages with attachments of file types that couldn't be indexed by Exchange Search).</span></span> 
    
    - <span data-ttu-id="fb40e-p127">**啟用重複資料刪除**-選取此核取方塊來排除重複的郵件。要在單一執行個體的訊息複製到探索信箱。</span><span class="sxs-lookup"><span data-stu-id="fb40e-p127">**Enable de-duplication** - Select this check box to exclude duplicate messages. Only a single instance of a message will be copied to the discovery mailbox.</span></span> 
    
    - <span data-ttu-id="fb40e-223">**啟用完整的記錄**-選取此核取方塊可在搜尋結果中包含完整的記錄檔。</span><span class="sxs-lookup"><span data-stu-id="fb40e-223">**Enable full logging** - Select this check box to include a full log in search results.</span></span> 
    
    - <span data-ttu-id="fb40e-224">**將郵件複製完成時傳送我**-選取此核取方塊可搜尋完成時要取得的電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="fb40e-224">**Send me mail when the copy is completed** - Select this check box to get an email notification when the search is completed.</span></span> 
    
    - <span data-ttu-id="fb40e-225">**複製到此探索信箱的結果**集按一下以選取您想要在搜尋結果的探索信箱的 [**瀏覽**複製到。</span><span class="sxs-lookup"><span data-stu-id="fb40e-225">**Copy results to this discovery mailbox** - Click **Browse** to select the discovery mailbox where you want the search results copied to.</span></span> 
    
5. <span data-ttu-id="fb40e-226">按一下 [**複製**到啟動程序來將搜尋結果複製到指定的探索信箱。</span><span class="sxs-lookup"><span data-stu-id="fb40e-226">Click **Copy** to start the process to copy the search results to the specified discovery mailbox.</span></span> 
    
6. <span data-ttu-id="fb40e-227">按一下 [**重新整理**![重新整理] 圖示](media/O365-MDM-Policy-RefreshIcon.gif)來更新顯示在 [詳細資料] 窗格中的複製狀態的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="fb40e-227">Click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information about the copying status that is displayed in the details pane.</span></span> 
    
7. <span data-ttu-id="fb40e-228">複製完成後，請按一下 [開啟要檢視搜尋結果的探索信箱的 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="fb40e-228">When copying is complete, click **Open** to open the discovery mailbox to view the search results.</span></span> 
  
### <a name="export-the-search-results"></a><span data-ttu-id="fb40e-229">匯出搜尋結果</span><span class="sxs-lookup"><span data-stu-id="fb40e-229">Export the search results</span></span>

1. <span data-ttu-id="fb40e-230">在 EAC 中，移至 [**規範管理** \> **就地 eDiscovery&amp;保留**。</span><span class="sxs-lookup"><span data-stu-id="fb40e-230">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="fb40e-231">在清單檢視中，選取您在步驟 3 中建立就地 eDiscovery 搜尋和 [**匯出至 PST 檔案**。</span><span class="sxs-lookup"><span data-stu-id="fb40e-231">In the list view, select the In-Place eDiscovery search that you created in Step 3, and then click **Export to a PST file**.</span></span>
    
3. <span data-ttu-id="fb40e-232">在 [ **eDiscovery PST 匯出工具**] 視窗中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="fb40e-232">In the **eDiscovery PST Export Tool** window, do the following:</span></span> 
    
    - <span data-ttu-id="fb40e-233">按一下 [**瀏覽]** 以指定您要下載 PST 檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="fb40e-233">Click **Browse** to specify the location where you want to download the PST file.</span></span> 
    
    - <span data-ttu-id="fb40e-p128">按一下 [**啟用 deduplication** ] 核取方塊來排除重複的郵件。單一執行個體的訊息將會包含在 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="fb40e-p128">Click the **Enable deduplication** checkbox to exclude duplicate messages. Only a single instance of a message will be included in the PST file.</span></span> 
    
    - <span data-ttu-id="fb40e-p129">按一下 [**包含無法搜尋的項目**] 核取方塊以包含無法搜尋 （例如無法依 Exchange 搜尋編製索引的檔案類型附件的郵件） 的信箱項目。無法搜尋的項目都要匯出至不同的 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="fb40e-p129">Click the **Include unsearchable items** checkbox to include mailbox items that couldn't be searched (for example, messages with attachments of file types that couldn't be indexed by Exchange Search). Unsearchable items are exported to a separate PST file.</span></span> 
    
4. <span data-ttu-id="fb40e-238">按一下 [搜尋結果匯出至 PST 檔案的 [**啟動**]。</span><span class="sxs-lookup"><span data-stu-id="fb40e-238">Click **Start** to export the search results to a PST file.</span></span> 
    
    <span data-ttu-id="fb40e-239">包含匯出程序狀態資訊的視窗便會隨即顯示。</span><span class="sxs-lookup"><span data-stu-id="fb40e-239">A window is displayed that contains status information about the export process.</span></span>
