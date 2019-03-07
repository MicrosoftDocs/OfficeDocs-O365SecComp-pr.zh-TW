---
title: 檢視 custodian 稽核活動
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: defc89f1d54238e62f947fd197e7a866380ee601
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/06/2019
ms.locfileid: "30455165"
---
# <a name="view-custodian-audit-activity"></a><span data-ttu-id="a1823-102">檢視 custodian 稽核活動</span><span class="sxs-lookup"><span data-stu-id="a1823-102">View custodian audit activity</span></span>

<span data-ttu-id="a1823-103">要尋找是否使用者檢視特定的文件，或清除其信箱中的項目？</span><span class="sxs-lookup"><span data-stu-id="a1823-103">Need to find if a user viewed a specific document or purged an item from their mailbox?</span></span> <span data-ttu-id="a1823-104">進階電子文件 （預覽） 現在已與安全性 & 合規性中心中現有的稽核記錄搜尋工具整合。</span><span class="sxs-lookup"><span data-stu-id="a1823-104">Advanced eDiscovery (Preview) is now integrated with the existing audit log search tool in the Security & Compliance Center.</span></span> <span data-ttu-id="a1823-105">使用此內嵌的體驗，您可以使用進階電子文件 （預覽） Custodian 管理工具來協助您調查輕鬆地存取搜尋並活動 custodians 內您的案例。</span><span class="sxs-lookup"><span data-stu-id="a1823-105">Using this embedded experience, you can use the Advanced eDiscovery (Preview) Custodian Management tool to facilitate your investigation by easily accessing and searching the activity for custodians within your case.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a1823-106">開始之前</span><span class="sxs-lookup"><span data-stu-id="a1823-106">Before you begin</span></span>

<span data-ttu-id="a1823-107">您必須獲指派 「 僅檢視稽核記錄檔] 或 [稽核記錄檔角色在 Exchange Online 來搜尋 Office 365 稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="a1823-107">You have to be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online to search the Office 365 audit log.</span></span> <span data-ttu-id="a1823-108">根據預設，這些角色被指派給相符性管理和在 Exchange 系統管理中心中的權限] 頁面上的組織管理角色群組。</span><span class="sxs-lookup"><span data-stu-id="a1823-108">By default, these roles are assigned to the Compliance Management and Organization Management role groups on the Permissions page in the Exchange admin center.</span></span> <span data-ttu-id="a1823-109">若要讓使用者能夠搜尋進階電子文件 （預覽） 稽核記錄的最低權限，在 Exchange Online 中建立自訂角色群組、 新增 「 僅檢視稽核記錄檔] 或 [稽核記錄 」 角色，並再將使用者新增為新的角色 /gr 成員oup。</span><span class="sxs-lookup"><span data-stu-id="a1823-109">To give a user the ability to search the Advanced eDiscovery (Preview) audit log with the minimum level of privileges, you can create a custom role group in Exchange Online, add the View-Only Audit Logs or Audit Logs role, and then add the user as a member of the new role group.</span></span> <span data-ttu-id="a1823-110">如需詳細資訊，請參閱 < Exchange Online 中的管理角色群組。</span><span class="sxs-lookup"><span data-stu-id="a1823-110">For more information, see Manage role groups in Exchange Online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a1823-111">如果您在安全性 & 合規性中心中的 [權限] 頁面上的僅檢視稽核記錄檔] 或 [稽核記錄檔角色指派使用者，他們將無法搜尋 Office 365 稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="a1823-111">If you assign a user the View-Only Audit Logs or Audit Logs role on the Permissions page in the Security & Compliance Center, they won't be able to search the Office 365 audit log.</span></span> <span data-ttu-id="a1823-112">您必須指派 Exchange Online 中的權限。</span><span class="sxs-lookup"><span data-stu-id="a1823-112">You have to assign the permissions in Exchange Online.</span></span> <span data-ttu-id="a1823-113">這是因為基礎指令程式用來搜尋稽核記錄是 Exchange Online cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a1823-113">This is because the underlying cmdlet used to search the audit log is an Exchange Online cmdlet.</span></span>

## <a name="step-1-create-an-advanced-ediscovery-preview-audit-log-search"></a><span data-ttu-id="a1823-114">步驟 1： 建立進階電子文件 （預覽） 的稽核記錄搜尋</span><span class="sxs-lookup"><span data-stu-id="a1823-114">Step 1: Create an Advanced eDiscovery (Preview) audit log search</span></span>

   1. <span data-ttu-id="a1823-115">從**安全性 & 合規性中心 > 進階電子文件 （預覽）** 中選取現有的案例。</span><span class="sxs-lookup"><span data-stu-id="a1823-115">Select an existing case from the **Security & Compliance Center > Advanced eDiscovery (Preview)**.</span></span>
   
   2. <span data-ttu-id="a1823-116">瀏覽至 [ **Custodians** ] 索引標籤，然後選取 [custodian。</span><span class="sxs-lookup"><span data-stu-id="a1823-116">Navigate to the **Custodians** tab and select a custodian.</span></span>
   
   3. <span data-ttu-id="a1823-117">一旦您已選取 custodian，按一下 [</span><span class="sxs-lookup"><span data-stu-id="a1823-117">Once you have selected a custodian, click</span></span>  ![檢視 Custodian 活動](../media/ViewCustodianActivity.PNG)  <span data-ttu-id="a1823-119">從 [詳細資料] 面板中。</span><span class="sxs-lookup"><span data-stu-id="a1823-119">from the details panel.</span></span>
   
   4. <span data-ttu-id="a1823-120">設定下列搜尋準則：</span><span class="sxs-lookup"><span data-stu-id="a1823-120">Configure the following search criteria:</span></span>
      
      <span data-ttu-id="a1823-121">a.</span><span class="sxs-lookup"><span data-stu-id="a1823-121">a.</span></span> <span data-ttu-id="a1823-122">**活動**-按一下下拉式清單，顯示您可以搜尋的活動。</span><span class="sxs-lookup"><span data-stu-id="a1823-122">**Activities** - Click the drop-down list to display the activities that you can search for.</span></span> <span data-ttu-id="a1823-123">執行搜尋之後，會顯示只有選取活動的稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="a1823-123">After you run the search, only the audit records for the selected activities are displayed.</span></span> <span data-ttu-id="a1823-124">選取 [**顯示所有活動的結果**會顯示結果符合其他搜尋準則的所有活動。</span><span class="sxs-lookup"><span data-stu-id="a1823-124">Selecting **Show results for all activities** will display results for all activities that meet the other search criteria.</span></span>

      ![活動的清單](../media/CustodianActivityAudit.PNG)
      
      <span data-ttu-id="a1823-126">b.</span><span class="sxs-lookup"><span data-stu-id="a1823-126">b.</span></span> <span data-ttu-id="a1823-127">**開始日期和結束日期**-選取日期與時間範圍，以顯示該期間內發生的事件。</span><span class="sxs-lookup"><span data-stu-id="a1823-127">**Start date and End date** - Select a date and time range to display the events that occurred within that period.</span></span> <span data-ttu-id="a1823-128">預設會選取過去 7 天。</span><span class="sxs-lookup"><span data-stu-id="a1823-128">The last seven days are selected by default.</span></span> <span data-ttu-id="a1823-129">日期和時間會以 Coordinated Universal Time (UTC) 格式呈現。</span><span class="sxs-lookup"><span data-stu-id="a1823-129">The date and time are presented in Coordinated Universal Time (UTC) format.</span></span> <span data-ttu-id="a1823-130">您可以指定的最大的日期範圍是一年。</span><span class="sxs-lookup"><span data-stu-id="a1823-130">The maximum date range that you can specify is one year.</span></span>
      
      <span data-ttu-id="a1823-131">c.</span><span class="sxs-lookup"><span data-stu-id="a1823-131">c.</span></span> <span data-ttu-id="a1823-132">**Custodians** -按一下 [在這個方塊，然後選取 [顯示搜尋結果提供給特定 custodian。</span><span class="sxs-lookup"><span data-stu-id="a1823-132">**Custodians** - Click in this box and then select a specific custodian to display search results for.</span></span> <span data-ttu-id="a1823-133">選取您在此方塊中選取的使用者所執行的活動的稽核記錄會顯示在結果清單中。</span><span class="sxs-lookup"><span data-stu-id="a1823-133">Audit records for the selected activity performed by the users you select in this box are displayed in the list of results.</span></span>
      
   5. <span data-ttu-id="a1823-134">按一下</span><span class="sxs-lookup"><span data-stu-id="a1823-134">Click</span></span>   ![[搜尋] 按鈕](../media/SearchButton.PNG)  <span data-ttu-id="a1823-136">若要執行搜尋使用您的搜尋準則。</span><span class="sxs-lookup"><span data-stu-id="a1823-136">to run the search using your search criteria.</span></span> <span data-ttu-id="a1823-137">載入的搜尋結果時，並在幾分鐘之後他們顯示的結果下 Custodian 活動的 [搜尋] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="a1823-137">The search results are loaded, and after a few moments they are displayed under Results on the Custodian Activities search page.</span></span> 

## <a name="step-2-view-the-audit-log-search-results"></a><span data-ttu-id="a1823-138">步驟 2： 檢視稽核記錄搜尋結果</span><span class="sxs-lookup"><span data-stu-id="a1823-138">Step 2: View the audit log search results</span></span>

<span data-ttu-id="a1823-139">稽核記錄搜尋結果] 底下會顯示結果 Custodian 稽核記錄 」 頁面。</span><span class="sxs-lookup"><span data-stu-id="a1823-139">The results of an audit log search are displayed under Results on the Custodian Audit log page.</span></span> <span data-ttu-id="a1823-140">最大值為 5000 個 （最新） 的事件都會顯示在 150 事件以遞增。</span><span class="sxs-lookup"><span data-stu-id="a1823-140">A maximum of 5,000 (newest) events are displayed in increments of 150 events.</span></span> <span data-ttu-id="a1823-141">若要顯示更多事件您可以使用捲軸列在 [結果] 窗格中，或您可以按 Shift + End 以顯示下一步] 150 事件。</span><span class="sxs-lookup"><span data-stu-id="a1823-141">To display more events you can use the scroll bar in the Results pane or you can press Shift + End to display the next 150 events.</span></span>

<span data-ttu-id="a1823-142">結果包含下列搜尋傳回的每個事件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a1823-142">The results contain the following information about each event returned by the search.</span></span>
- <span data-ttu-id="a1823-143">**日期**： 日期和時間 （UTC 格式） 事件發生時。</span><span class="sxs-lookup"><span data-stu-id="a1823-143">**Date**: The date and time (in UTC format) when the event occurred.</span></span>

- <span data-ttu-id="a1823-144">**IP 位址**： 已登入活動時所用的裝置的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a1823-144">**IP address**: The IP address of the device that was used when the activity was logged.</span></span> <span data-ttu-id="a1823-145">IP 位址會顯示在 IPv4 或 IPv6 地址格式。</span><span class="sxs-lookup"><span data-stu-id="a1823-145">The IP address is displayed in either an IPv4 or IPv6 address format.</span></span>

- <span data-ttu-id="a1823-146">**使用者**： 使用者 （或服務帳戶） 誰執行觸發事件的動作。</span><span class="sxs-lookup"><span data-stu-id="a1823-146">**User**: The user (or service account) who performed the action that triggered the event.</span></span>

- <span data-ttu-id="a1823-147">**活動**： 使用者所執行的活動。</span><span class="sxs-lookup"><span data-stu-id="a1823-147">**Activity**: The activity performed by the user.</span></span> <span data-ttu-id="a1823-148">此值會對應至您在 [活動] 下拉式清單中選取的活動。</span><span class="sxs-lookup"><span data-stu-id="a1823-148">This value corresponds to the activities that you selected in the Activities drop down list.</span></span> <span data-ttu-id="a1823-149">從 Exchange 系統管理員稽核記錄的事件，此欄中的值會是 Exchange 指令程式。</span><span class="sxs-lookup"><span data-stu-id="a1823-149">For an event from the Exchange admin audit log, the value in this column is an Exchange cmdlet.</span></span>

- <span data-ttu-id="a1823-150">**項目**： 物件已建立或修改由於相對應的活動。</span><span class="sxs-lookup"><span data-stu-id="a1823-150">**Item**: The object that was created or modified as a result of the corresponding activity.</span></span> <span data-ttu-id="a1823-151">例如，檢視或修改的檔案或已更新的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="a1823-151">For example, the file that was viewed or modified or the user account that was updated.</span></span> <span data-ttu-id="a1823-152">並非所有活動中此欄都有值。</span><span class="sxs-lookup"><span data-stu-id="a1823-152">Not all activities have a value in this column.</span></span>

- <span data-ttu-id="a1823-153">**詳細資料**： 活動相關的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a1823-153">**Detail**: Additional detail about an activity.</span></span> <span data-ttu-id="a1823-154">同樣地，並非所有活動會都有一個值。</span><span class="sxs-lookup"><span data-stu-id="a1823-154">Again, not all activities will have a value.</span></span>

## <a name="step-3-filter-the-search-results"></a><span data-ttu-id="a1823-155">步驟 3： 篩選搜尋結果</span><span class="sxs-lookup"><span data-stu-id="a1823-155">Step 3: Filter the search results</span></span>

<span data-ttu-id="a1823-156">除了排序，您也可以篩選稽核記錄搜尋的結果。</span><span class="sxs-lookup"><span data-stu-id="a1823-156">In addition to sorting, you can also filter the results of an audit log search.</span></span> <span data-ttu-id="a1823-157">這可協助您快速篩選特定使用者或活動的結果。</span><span class="sxs-lookup"><span data-stu-id="a1823-157">This can help you quickly filter the results for a specific user or activity.</span></span> 

<span data-ttu-id="a1823-158">若要篩選的結果：</span><span class="sxs-lookup"><span data-stu-id="a1823-158">To filter the results:</span></span>

 1. <span data-ttu-id="a1823-159">建立並執行稽核記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="a1823-159">Create and run an audit log search.</span></span>
  
2. <span data-ttu-id="a1823-160">結果會顯示，按一下 [**篩選結果**。</span><span class="sxs-lookup"><span data-stu-id="a1823-160">When the results are displayed, click **Filter results**.</span></span>
 
3. <span data-ttu-id="a1823-161">關鍵字方塊會顯示在每個資料行標題之下。</span><span class="sxs-lookup"><span data-stu-id="a1823-161">Keyword boxes are displayed under each column header.</span></span>
  
4. <span data-ttu-id="a1823-162">按一下其中一個方塊下欄標題，然後輸入單字或片語，視您正在篩選的資料行。</span><span class="sxs-lookup"><span data-stu-id="a1823-162">Click one of the boxes under a column header and type a word or phrase, depending on the column you're filtering on.</span></span> <span data-ttu-id="a1823-163">結果會以動態方式重新調整以顯示符合篩選的事件。</span><span class="sxs-lookup"><span data-stu-id="a1823-163">The results will dynamically readjust to display the events that match your filter.</span></span>
  
5. <span data-ttu-id="a1823-164">若要清除篩選，請按一下 [篩選] 方塊中的**X**或只要按一下 [**隱藏篩選**。</span><span class="sxs-lookup"><span data-stu-id="a1823-164">To clear a filter, click the **X** in the filter box or just click **Hide filtering**.</span></span>

## <a name="export-the-search-results-to-a-file"></a><span data-ttu-id="a1823-165">將搜尋結果匯出至檔案</span><span class="sxs-lookup"><span data-stu-id="a1823-165">Export the search results to a file</span></span>

<span data-ttu-id="a1823-166">您可以將稽核記錄搜尋結果匯出至本機電腦上的逗點分隔的值 (CSV) 檔案。</span><span class="sxs-lookup"><span data-stu-id="a1823-166">You can export the results of an audit log search to a comma separated value (CSV) file on your local computer.</span></span> <span data-ttu-id="a1823-167">您可以在 Microsoft Excel 中開啟此檔案，並使用多個資料行到功能，例如搜尋，排序、 篩選及分割的單一資料行 （包含多重值的儲存格）。</span><span class="sxs-lookup"><span data-stu-id="a1823-167">You can open this file in Microsoft Excel and use features such as search, sorting, filtering, and splitting a single column (that contains multi-value cells) into multiple columns.</span></span>

1. <span data-ttu-id="a1823-168">執行稽核記錄搜尋]，然後再修訂的搜尋準則，直到您有想要的結果。</span><span class="sxs-lookup"><span data-stu-id="a1823-168">Run an audit log search, and then revise the search criteria until you have the desired results.</span></span>
  
2. <span data-ttu-id="a1823-169">按一下 [匯出結果，然後選取下列選項之一：</span><span class="sxs-lookup"><span data-stu-id="a1823-169">Click Export results and select one of the following options:</span></span>

    - <span data-ttu-id="a1823-170">**儲存載入結果：** 選擇此選項以匯出**Custodian 稽核記錄搜尋**] 頁面的**結果**下顯示的項目。</span><span class="sxs-lookup"><span data-stu-id="a1823-170">**Save loaded results:** Choose this option to export only the entries that are displayed under **Results** on the **Custodian Audit log search** page.</span></span> <span data-ttu-id="a1823-171">下載的 CSV 檔案包含 （日期、 使用者、 活動、 項目，以及詳細資料） 頁面上顯示的相同資料行 （和資料）。</span><span class="sxs-lookup"><span data-stu-id="a1823-171">The CSV file that is downloaded contains the same columns (and data) displayed on the page (Date, User, Activity, Item, and Details).</span></span> <span data-ttu-id="a1823-172">（標題為**多個**） 額外一欄隨附於 CSV 檔案包含稽核記錄項目從的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="a1823-172">An additional column (titled **More**) is included in the CSV file that contains more information from the audit log entry.</span></span> <span data-ttu-id="a1823-173">因為您要匯出相同的結果載入 （與檢視） 的最大值為 5000 的項目會被匯出稽核記錄搜尋] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="a1823-173">Because you're exporting the same results that are loaded (and viewable) on the Audit log search page, a maximum of 5,000 entries are exported.</span></span>
        
    - <span data-ttu-id="a1823-174">**下載所有的結果：** 選擇此選項以從符合搜尋準則的 Office 365 稽核記錄檔匯出所有的項目。</span><span class="sxs-lookup"><span data-stu-id="a1823-174">**Download all results:** Choose this option to export all entries from the Office 365 audit log that meet the search criteria.</span></span> <span data-ttu-id="a1823-175">一組大型的搜尋結果，選擇此選項以從除了可以**Custodian 稽核記錄**搜尋] 頁面顯示 5000 筆結果的稽核記錄檔下載所有項目。</span><span class="sxs-lookup"><span data-stu-id="a1823-175">For a large set of search results, choose this option to download all entries from the audit log in addition to the 5,000 results that can be displayed on the **Custodian Audit log** search page.</span></span> <span data-ttu-id="a1823-176">此選項將稽核記錄檔從下載的未經處理資料至 CSV 檔案，並包含名為 AuditData] 欄中的稽核記錄項目中的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="a1823-176">This option will download the raw data from the audit log to a CSV file, and contains additional information from the audit log entry in a column named AuditData.</span></span> <span data-ttu-id="a1823-177">可能需要較長的時間下載檔案，如果您選擇此匯出選項，因為可能遠大於一如果您選擇其他選項下載的檔案。</span><span class="sxs-lookup"><span data-stu-id="a1823-177">It may take longer to download the file if you choose this export option because the file may be much larger than the one that's downloaded if you choose the other option.</span></span>
    
      > [!IMPORTANT]
      > <span data-ttu-id="a1823-178">您可以下載至 CSV 檔案的最大值為 50000 的項目從單一的稽核記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="a1823-178">You can download a maximum of 50,000 entries to a CSV file from a single audit log search.</span></span> <span data-ttu-id="a1823-179">如果 50000 的項目會下載到 CSV 檔案，您可能可以假設有超過 50000 個符合搜尋準則的事件。</span><span class="sxs-lookup"><span data-stu-id="a1823-179">If 50,000 entries are downloaded to the CSV file, you can probably assume there are more than 50,000 events that met the search criteria.</span></span> <span data-ttu-id="a1823-180">若要匯出超過此限制，請嘗試使用日期範圍，以減少稽核記錄項目的數目。</span><span class="sxs-lookup"><span data-stu-id="a1823-180">To export more than this limit, try using a date range to reduce the number of audit log entries.</span></span> <span data-ttu-id="a1823-181">您可能使用較小的日期範圍，若要匯出超過 50000 個項目執行多個搜尋。</span><span class="sxs-lookup"><span data-stu-id="a1823-181">You might have to run multiple searches with smaller date ranges to export more than 50,000 entries.</span></span>
        

3. <span data-ttu-id="a1823-182">選取 [匯出] 選項後，會提示您開啟 CSV 檔案，將它儲存到 [下載項目] 資料夾中，或將其儲存至特定資料夾視窗底部顯示訊息</span><span class="sxs-lookup"><span data-stu-id="a1823-182">After you select an export option, a message is displayed at the bottom of the window that prompts you to open the CSV file, save it to the Downloads folder, or save it to a specific folder</span></span>

<span data-ttu-id="a1823-183">如需檢視的詳細資訊，篩選，或匯出稽核記錄搜尋結果，請參閱[的搜尋稽核記錄中 Office 365 安全性 & 合規性中心](../search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="a1823-183">For more information about viewing, filtering, or exporting audit log search results, see [Search the audit log in the Office 365 Security & Compliance Center](../search-the-audit-log-in-security-and-compliance.md).</span></span>
