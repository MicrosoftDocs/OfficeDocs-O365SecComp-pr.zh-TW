---
title: 檢視 okay 稽核活動
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 8219ae8a061f6d08dd37da5b7f2974dd86c68f04
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607546"
---
# <a name="viewing-custodian-audit-activity"></a><span data-ttu-id="039c0-102">檢視 okay 稽核活動</span><span class="sxs-lookup"><span data-stu-id="039c0-102">Viewing custodian audit activity</span></span>

<span data-ttu-id="039c0-p101">需要尋找是否使用者檢視特定文件或清除 [從他們的信箱項目吗？進階的 eDiscovery （預覽） 現在整合安全性 & 規範中心中現有的稽核記錄搜尋工具。使用此內嵌的經驗，您可以使用進階的 eDiscovery （預覽） Okay 管理工具來協助您調查由輕鬆地存取和搜尋中您案例的 custodians 活動。</span><span class="sxs-lookup"><span data-stu-id="039c0-p101">Need to find if a user viewed a specific document or purged an item from their mailbox? Advanced eDiscovery (Preview) is now integrated with the existing audit log search tool in the Security & Compliance Center. Using this embedded experience, you can use the Advanced eDiscovery (Preview) Custodian Management tool to facilitate your investigation by easily accessing and searching the activity for custodians within your case.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="039c0-106">開始之前</span><span class="sxs-lookup"><span data-stu-id="039c0-106">Before you begin</span></span>

<span data-ttu-id="039c0-p102">您必須指派 「 僅檢視稽核記錄 」 或 「 稽核記錄角色在 Exchange Online 搜尋 Office 365 稽核記錄。根據預設，這些角色指派給相符性管理及 Exchange 系統管理中心的 [權限] 頁面上的組織管理角色群組。若要讓使用者能夠搜尋進階的 eDiscovery （預覽） 稽核記錄的最低權限，Exchange Online 中建立自訂角色群組、 新增 「 僅檢視稽核記錄或稽核記錄 」 角色及再將使用者新增為新的角色 /gr 成員oup。如需詳細資訊，請參閱 Exchange Online 中的管理角色群組。</span><span class="sxs-lookup"><span data-stu-id="039c0-p102">You have to be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online to search the Office 365 audit log. By default, these roles are assigned to the Compliance Management and Organization Management role groups on the Permissions page in the Exchange admin center. To give a user the ability to search the Advanced eDiscovery (Preview) audit log with the minimum level of privileges, you can create a custom role group in Exchange Online, add the View-Only Audit Logs or Audit Logs role, and then add the user as a member of the new role group. For more information, see Manage role groups in Exchange Online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="039c0-p103">如果您在安全性 & 規範中心權限] 頁面上的僅檢視稽核記錄或稽核記錄角色指派使用者，他們將無法搜尋 Office 365 稽核記錄。您必須指派 Exchange Online 中的權限。這是因為基礎指令程式來搜尋稽核記錄是 Exchange Online 指令程式。</span><span class="sxs-lookup"><span data-stu-id="039c0-p103">If you assign a user the View-Only Audit Logs or Audit Logs role on the Permissions page in the Security & Compliance Center, they won't be able to search the Office 365 audit log. You have to assign the permissions in Exchange Online. This is because the underlying cmdlet used to search the audit log is an Exchange Online cmdlet.</span></span>

## <a name="step-1-create-an-advanced-ediscovery-preview-audit-log-search"></a><span data-ttu-id="039c0-114">步驟 1： 建立進階的 eDiscovery （預覽） 稽核記錄搜尋</span><span class="sxs-lookup"><span data-stu-id="039c0-114">Step 1: Create an Advanced eDiscovery (Preview) audit log search</span></span>

   1. <span data-ttu-id="039c0-115">從**安全性 & 規範中心 > 進階的 eDiscovery (Preview)** 中選取現有的案例。</span><span class="sxs-lookup"><span data-stu-id="039c0-115">Select an existing case from the **Security & Compliance Center > Advanced eDiscovery (Preview)**.</span></span>
   
   2. <span data-ttu-id="039c0-116">瀏覽至 [ **Custodians** ] 索引標籤並選取 okay。</span><span class="sxs-lookup"><span data-stu-id="039c0-116">Navigate to the **Custodians** tab and select a custodian.</span></span>
   
   3. <span data-ttu-id="039c0-117">您一次選取 okay，從 [詳細資料] 面板中按一下 [**檢視 Okay 活動**。</span><span class="sxs-lookup"><span data-stu-id="039c0-117">Once you have selected a custodian, click **View Custodian Activity** from the details panel.</span></span>
   
   4. <span data-ttu-id="039c0-118">設定下列搜尋準則：</span><span class="sxs-lookup"><span data-stu-id="039c0-118">Configure the following search criteria:</span></span>
      
      <span data-ttu-id="039c0-p104">a.**活動**-[下拉式清單，以顯示您可以搜尋的活動。執行搜尋之後，會顯示只選取活動的稽核記錄。選取 [**顯示所有的活動的結果**會顯示所有符合搜尋準則的活動的結果。</span><span class="sxs-lookup"><span data-stu-id="039c0-p104">a. **Activities** - Click the drop-down list to display the activities that you can search for. After you run the search, only the audit records for the selected activities are displayed. Selecting **Show results for all activities** will display results for all activities that meet the other search criteria.</span></span>
      
      <span data-ttu-id="039c0-p105">b.**開始日期和結束日期**-選取以顯示該期間內發生之事件的日期和時間範圍。預設會選取過去 7 天。以國際標準時間 (UTC) 格式所呈現的日期和時間。您可以指定的最大的日期範圍是一年以上。</span><span class="sxs-lookup"><span data-stu-id="039c0-p105">b. **Start date and End date** - Select a date and time range to display the events that occurred within that period. The last seven days are selected by default. The date and time are presented in Coordinated Universal Time (UTC) format. The maximum date range that you can specify is one year.</span></span>
      
      <span data-ttu-id="039c0-p106">c. **Custodians**按一下在此方塊，然後選取 [顯示搜尋特定 okay 的結果。選取您在此方塊中選取的使用者所執行的活動的稽核記錄所顯示的結果清單中。</span><span class="sxs-lookup"><span data-stu-id="039c0-p106">c. **Custodians** - Click in this box and then select a specific custodian to display search results for. Audit records for the selected activity performed by the users you select in this box are displayed in the list of results.</span></span>
    
    1. <span data-ttu-id="039c0-p107">按一下 [**搜尋**來執行使用搜尋準則的 [搜尋]。會載入搜尋結果，並在幾分鐘之後時顯示下結果 Okay 活動搜尋] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="039c0-p107">Click **Search** to run the search using your search criteria. The search results are loaded, and after a few moments they are displayed under Results on the Custodian Activities search page.</span></span> 

## <a name="step-2-view-the-audit-log-search-results"></a><span data-ttu-id="039c0-133">步驟 2： 檢視稽核記錄搜尋結果</span><span class="sxs-lookup"><span data-stu-id="039c0-133">Step 2: View the audit log search results</span></span>

<span data-ttu-id="039c0-p108">稽核記錄搜尋結果會顯示 [結果在 Okay 稽核記錄檔] 頁面上。最大值為 5000 個 （最新） 事件會顯示在 150 事件以遞增。若要顯示多個事件您可以使用捲軸列在 [結果] 窗格中或您可以按 Shift + End 顯示下一步] 150 事件。</span><span class="sxs-lookup"><span data-stu-id="039c0-p108">The results of an audit log search are displayed under Results on the Custodian Audit log page. A maximum of 5,000 (newest) events are displayed in increments of 150 events. To display more events you can use the scroll bar in the Results pane or you can press Shift + End to display the next 150 events.</span></span>

<span data-ttu-id="039c0-137">結果包含下列搜尋傳回的每個事件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="039c0-137">The results contain the following information about each event returned by the search.</span></span>
- <span data-ttu-id="039c0-138">**日期**： 日期和時間 （UTC 格式） 事件發生的時間。</span><span class="sxs-lookup"><span data-stu-id="039c0-138">**Date**: The date and time (in UTC format) when the event occurred.</span></span>

- <span data-ttu-id="039c0-p109">**IP 位址**： 活動已記錄時所使用之裝置的 IP 位址。IP 位址是 IPv4 或 IPv6 地址格式顯示。</span><span class="sxs-lookup"><span data-stu-id="039c0-p109">**IP address**: The IP address of the device that was used when the activity was logged. The IP address is displayed in either an IPv4 or IPv6 address format.</span></span>

- <span data-ttu-id="039c0-141">**使用者**： 使用者 （或服務帳戶） 誰執行觸發事件的動作。</span><span class="sxs-lookup"><span data-stu-id="039c0-141">**User**: The user (or service account) who performed the action that triggered the event.</span></span>

- <span data-ttu-id="039c0-p110">**活動**： 之使用者所執行的活動。此值會對應至您在 [活動] 下拉式清單中選取的活動。從 Exchange 管理員稽核記錄的事件，此資料行中的值會是 Exchange cmdlet。</span><span class="sxs-lookup"><span data-stu-id="039c0-p110">**Activity**: The activity performed by the user. This value corresponds to the activities that you selected in the Activities drop down list. For an event from the Exchange admin audit log, the value in this column is an Exchange cmdlet.</span></span>

- <span data-ttu-id="039c0-p111">**項目**： 物件已建立或修改因為相對應的活動。例如，已檢視或修改的檔案或已更新的使用者帳戶。並非所有的活動具有此欄中的值。</span><span class="sxs-lookup"><span data-stu-id="039c0-p111">**Item**: The object that was created or modified as a result of the corresponding activity. For example, the file that was viewed or modified or the user account that was updated. Not all activities have a value in this column.</span></span>

- <span data-ttu-id="039c0-p112">**詳細資料**： 活動相關的其他詳細資訊。同樣地，不是所有的活動都有值。</span><span class="sxs-lookup"><span data-stu-id="039c0-p112">**Detail**: Additional detail about an activity. Again, not all activities will have a value.</span></span>

## <a name="step-3-filter-the-search-results"></a><span data-ttu-id="039c0-150">步驟 3： 篩選搜尋結果</span><span class="sxs-lookup"><span data-stu-id="039c0-150">Step 3: Filter the search results</span></span>

<span data-ttu-id="039c0-p113">除了排序，您也可以篩選的稽核記錄搜尋的結果。這可協助您快速篩選特定使用者或活動的結果。</span><span class="sxs-lookup"><span data-stu-id="039c0-p113">In addition to sorting, you can also filter the results of an audit log search. This can help you quickly filter the results for a specific user or activity.</span></span> 

<span data-ttu-id="039c0-153">若要篩選結果：</span><span class="sxs-lookup"><span data-stu-id="039c0-153">To filter the results:</span></span>

 1. <span data-ttu-id="039c0-154">建立並執行稽核記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="039c0-154">Create and run an audit log search.</span></span>
  
2. <span data-ttu-id="039c0-155">時所顯示的結果，按一下 [**篩選結果**。</span><span class="sxs-lookup"><span data-stu-id="039c0-155">When the results are displayed, click **Filter results**.</span></span>
 
3. <span data-ttu-id="039c0-156">關鍵字] 方塊會顯示每個資料行標題底下。</span><span class="sxs-lookup"><span data-stu-id="039c0-156">Keyword boxes are displayed under each column header.</span></span>
  
4. <span data-ttu-id="039c0-p114">按一下欄標題下的其中一個方塊，輸入的單字或片語，視您要篩選的資料行。結果會以動態方式重新調整以顯示符合您的篩選器的事件。</span><span class="sxs-lookup"><span data-stu-id="039c0-p114">Click one of the boxes under a column header and type a word or phrase, depending on the column you're filtering on. The results will dynamically readjust to display the events that match your filter.</span></span>
  
5. <span data-ttu-id="039c0-159">若要清除篩選，請按一下 [篩選] 方塊中的**X**或只要按一下 [**隱藏篩選**。</span><span class="sxs-lookup"><span data-stu-id="039c0-159">To clear a filter, click the **X** in the filter box or just click **Hide filtering**.</span></span>

## <a name="export-the-search-results-to-a-file"></a><span data-ttu-id="039c0-160">將搜尋結果匯出至檔案</span><span class="sxs-lookup"><span data-stu-id="039c0-160">Export the search results to a file</span></span>

<span data-ttu-id="039c0-p115">您可以將稽核記錄搜尋結果匯出至本機電腦上逗點分隔的值 (CSV) 檔案。您可以在 Microsoft Excel 中開啟此檔案並使用功能，例如搜尋、 排序、 篩選和分割單一欄 （其中包含多重值的儲存格） 到多個資料欄。</span><span class="sxs-lookup"><span data-stu-id="039c0-p115">You can export the results of an audit log search to a comma separated value (CSV) file on your local computer. You can open this file in Microsoft Excel and use features such as search, sorting, filtering, and splitting a single column (that contains multi-value cells) into multiple columns.</span></span>

1. <span data-ttu-id="039c0-163">執行稽核記錄搜尋，並再修改搜尋準則直到您有想要的結果。</span><span class="sxs-lookup"><span data-stu-id="039c0-163">Run an audit log search, and then revise the search criteria until you have the desired results.</span></span>
  
2. <span data-ttu-id="039c0-164">按一下 [匯出結果並選取下列選項之一：</span><span class="sxs-lookup"><span data-stu-id="039c0-164">Click Export results and select one of the following options:</span></span>

    - <span data-ttu-id="039c0-p116">**儲存載入結果：** 選擇此選項可匯出的顯示在 [**結果** **Okay 稽核記錄搜尋**] 頁面的項目。已下載的 CSV 檔案包含相同資料行 （和資料） 顯示在頁面 （日期、 使用者、 活動、 項目及詳細資料）。（名稱為**多個**） 其他欄隨附於包含稽核記錄項目中的詳細資訊的 CSV 檔案。因為您要匯出相同的結果會載入 （及檢視） 的最大值為 5000 項目都要匯出稽核記錄搜尋] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="039c0-p116">**Save loaded results:** Choose this option to export only the entries that are displayed under **Results** on the **Custodian Audit log search** page. The CSV file that is downloaded contains the same columns (and data) displayed on the page (Date, User, Activity, Item, and Details). An additional column (titled **More**) is included in the CSV file that contains more information from the audit log entry. Because you're exporting the same results that are loaded (and viewable) on the Audit log search page, a maximum of 5,000 entries are exported.</span></span>
        
    - <span data-ttu-id="039c0-p117">**下載所有結果：** 選擇此選項可從符合搜尋準則的 Office 365 稽核記錄中匯出所有的項目。搜尋結果的一大組，選擇此選項除了可以**Okay 稽核記錄檔**的 [搜尋] 頁面顯示 5000 筆結果的稽核記錄檔從下載所有項目。這個選項會下載從稽核記錄的原始資料至 CSV 檔案，並包含名為 AuditData] 欄中的稽核記錄項目中的其他資訊。可能需要更久，如果您選擇這個匯出選項因為檔案可能會更加大於會下載如果您選擇其他選項的下載檔案。</span><span class="sxs-lookup"><span data-stu-id="039c0-p117">**Download all results:** Choose this option to export all entries from the Office 365 audit log that meet the search criteria. For a large set of search results, choose this option to download all entries from the audit log in addition to the 5,000 results that can be displayed on the **Custodian Audit log** search page. This option will download the raw data from the audit log to a CSV file, and contains additional information from the audit log entry in a column named AuditData. It may take longer to download the file if you choose this export option because the file may be much larger than the one that's downloaded if you choose the other option.</span></span>
    
      > [!IMPORTANT]
      > <span data-ttu-id="039c0-p118">您可以下載到 CSV 檔案的最大值為 50000 項目從單一的稽核記錄搜尋。如果 50000 項目會下載到 CSV 檔案，您可能可以假設有超過 50000 個符合搜尋準則的事件。若要匯出超過此限制，嘗試使用日期範圍減少的稽核記錄項目數目。您可能必須執行多個搜尋與較小的日期範圍中匯出 50000 個以上的項目。</span><span class="sxs-lookup"><span data-stu-id="039c0-p118">You can download a maximum of 50,000 entries to a CSV file from a single audit log search. If 50,000 entries are downloaded to the CSV file, you can probably assume there are more than 50,000 events that met the search criteria. To export more than this limit, try using a date range to reduce the number of audit log entries. You might have to run multiple searches with smaller date ranges to export more than 50,000 entries.</span></span>
        

3. <span data-ttu-id="039c0-177">選取 [匯出] 選項後，會提示您開啟 CSV 檔案，將它儲存到 [下載項目] 資料夾中，或將其儲存至特定資料夾視窗底部顯示訊息</span><span class="sxs-lookup"><span data-stu-id="039c0-177">After you select an export option, a message is displayed at the bottom of the window that prompts you to open the CSV file, save it to the Downloads folder, or save it to a specific folder</span></span>

[!NOTE] 
 <span data-ttu-id="039c0-178">如需檢視、 篩選或匯出稽核記錄搜尋結果的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="039c0-178">For more information about viewing, filtering, or exporting audit log search results, see:</span></span>
   - <span data-ttu-id="039c0-179">檢視清單中的稽核活動</span><span class="sxs-lookup"><span data-stu-id="039c0-179">View List of Audited Activities</span></span> 
   - <span data-ttu-id="039c0-180">開始之前： 整合的稽核記錄</span><span class="sxs-lookup"><span data-stu-id="039c0-180">Before You Begin: Unified Audit Logs</span></span>
 