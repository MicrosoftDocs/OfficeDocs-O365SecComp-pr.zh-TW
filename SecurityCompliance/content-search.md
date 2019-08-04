---
title: Office 365 中的內容搜尋
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 53390468-eec6-45cb-b6cd-7511f9c909e4
description: 使用 Office 365 或 Microsoft 365 合規性中心中的「內容搜尋」工具，來搜尋信箱中的內容、SharePoint Online 網站，OneDrive 帳戶、Microsoft Teams、Office 365 群組和商務用 Skype 交談。 您可以使用關鍵字搜尋查詢和搜尋條件來縮小搜尋結果。 然後您可以預覽和匯出搜尋結果。 內容搜尋也是用來搜尋與 GDPR 資料主體要求相關內容的有效工具。
ms.openlocfilehash: 3df1ee02cc7b31a8dd316bac5ccd4455c26922c5
ms.sourcegitcommit: 73dcdafb15b462223d1a670c781db260eb73c2f5
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/01/2019
ms.locfileid: "36048185"
---
# <a name="content-search-in-office-365"></a><span data-ttu-id="d59a3-106">Office 365 中的內容搜尋</span><span class="sxs-lookup"><span data-stu-id="d59a3-106">Partially indexed items in Content Search in Office 365</span></span>

<span data-ttu-id="d59a3-107">您可以使用 Office 365 或 Microsoft 365 合規性中心中的內容搜尋電子文件探索工具，來搜尋 Office 365 組織中的就地項目，例如電子郵件、文件和立即訊息交談。</span><span class="sxs-lookup"><span data-stu-id="d59a3-107">You can use the Content Search eDiscovery tool in the compliance center in Office 365 or Microsoft 365 to search for in-place items such as email, documents, and instant messaging conversations in your Office 365 organization.</span></span> <span data-ttu-id="d59a3-108">使用此工具來搜尋這些 Office 365 服務中的項目：</span><span class="sxs-lookup"><span data-stu-id="d59a3-108">Use this tool to search for items in these Office 365 services:</span></span>
  
- <span data-ttu-id="d59a3-109">Exchange Online 信箱和公用資料夾</span><span class="sxs-lookup"><span data-stu-id="d59a3-109">Exchange Online mailboxes and public folders</span></span>
    
- <span data-ttu-id="d59a3-110">SharePoint Online 網站和商務用 OneDrive 帳戶</span><span class="sxs-lookup"><span data-stu-id="d59a3-110">All SharePoint Online sites and OneDrive for Business accounts in your organization</span></span>
    
- <span data-ttu-id="d59a3-111">商務用 Skype 交談</span><span class="sxs-lookup"><span data-stu-id="d59a3-111">im – Searches Skype for Business conversations</span></span>
    
- <span data-ttu-id="d59a3-112">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d59a3-112">Microsoft Teams</span></span> 
    
- <span data-ttu-id="d59a3-113">Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="d59a3-113">Office 365 Groups</span></span>
    
<span data-ttu-id="d59a3-114">執行內容搜尋之後，內容位置數目及預估的搜尋結果數目會顯示在搜尋設定檔中。</span><span class="sxs-lookup"><span data-stu-id="d59a3-114">After you run a Content Search, the number of content sources and an estimated number of search results are displayed in the details pane on the Content search page.</span></span> <span data-ttu-id="d59a3-115">您也可以快速檢視統計資料，例如多數項目符合搜尋查詢的內容位置。</span><span class="sxs-lookup"><span data-stu-id="d59a3-115">You can also quickly view statistics, such as the content locations that have the most items that match the search query.</span></span> <span data-ttu-id="d59a3-116">執行搜尋後，您可以預覽結果或將結果匯出到本機電腦上。</span><span class="sxs-lookup"><span data-stu-id="d59a3-116">After you run a Content Search you can preview the results, export the results to a local computer, or prepare the results for analysis in EquivioAnalyticsFirstMention.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="d59a3-117">建立搜尋</span><span class="sxs-lookup"><span data-stu-id="d59a3-117">Create a search</span></span>

<span data-ttu-id="d59a3-118">若要有權存取**內容搜尋**頁面以執行搜尋和預覽並匯出搜尋結果，系統管理員、法務人員或電子文件探索管理員必須是安全性與合規性中心中電子文件探索管理員角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="d59a3-118">To have access to the **Content search** page to run searches and preview and export search results, an administrator, compliance officer, or eDiscovery manager must be a member of the eDiscovery Manager role group in the Security & Compliance Center.</span></span> <span data-ttu-id="d59a3-119">如需詳細資訊，請參閱[指派電子文件探索權限](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="d59a3-119">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>
  
1. <span data-ttu-id="d59a3-120">移至 [https://protection.office.com](https://protection.office.com) 並使用您的 Office 365 電子郵件地址和密碼登入。</span><span class="sxs-lookup"><span data-stu-id="d59a3-120">Go to [https://protection.office.com](https://protection.office.com) and sign in using your Office 365 email address and password.</span></span>
    
2. <span data-ttu-id="d59a3-121">按一下 [搜尋]\*\*\*\* \> [內容搜尋]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d59a3-121">Click **Search** \> **Content search**.</span></span>
    
3. <span data-ttu-id="d59a3-122">在 [搜尋]\*\*\*\* 頁面上，按一下 [![加號圖示](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) 新增搜尋]\*\*\*\* 旁邊的箭號。</span><span class="sxs-lookup"><span data-stu-id="d59a3-122">On the **Search** page, click the arrow next to ![Add icon](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New search**.</span></span> 
    
    ![[新增搜尋] 下拉式清單](media/76b25861-55c5-4f50-9d48-9e2be2d0d078.png)
  
    <span data-ttu-id="d59a3-124">您可以選擇下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="d59a3-124">You can choose one of the following options:</span></span>
    
    - <span data-ttu-id="d59a3-125">\*\*引導式搜尋 - 此選項會啟動精靈，引導您建立搜尋。</span><span class="sxs-lookup"><span data-stu-id="d59a3-125">\*\*Guided search — This option starts a wizard that guides you through the creating the search.</span></span> <span data-ttu-id="d59a3-126">用來選取內容位置和建置搜尋查詢的使用者介面與 [新增搜尋]\*\*\*\* 選項完全相同。</span><span class="sxs-lookup"><span data-stu-id="d59a3-126">The user interface to select content locations and build the search query are the same as the **New search** option.</span></span> 
    
    - <span data-ttu-id="d59a3-127">**新增搜尋** - 此選項會顯示用來建立搜尋的更新的使用者介面。</span><span class="sxs-lookup"><span data-stu-id="d59a3-127">**New search** – This option displays an updated user interface to create a search.</span></span> <span data-ttu-id="d59a3-128">如果您按一下 [新增搜尋]\*\*\*\*，這會是預設選項。</span><span class="sxs-lookup"><span data-stu-id="d59a3-128">This is the default option if you click **New search**.</span></span>
    
    - <span data-ttu-id="d59a3-129">**依識別碼清單搜尋** - 此選項可讓您使用 Exchange 識別碼的清單來搜尋特定的電子郵件訊息和其他信箱項目。</span><span class="sxs-lookup"><span data-stu-id="d59a3-129">**Search by ID List** – This option lets you search for specific email messages and other mailbox items using a list of Exchange IDs.</span></span> <span data-ttu-id="d59a3-130">若要建立識別碼清單搜尋 (正式名稱為目標搜尋)，您可以提交可識別要搜尋的特定信箱項目的逗點分隔值 (CSV) 檔案。</span><span class="sxs-lookup"><span data-stu-id="d59a3-130">To create an ID list search (formally called a targeted search), you submit a comma-separated value (CSV) file that identifies the specific mailbox items to search for.</span></span> <span data-ttu-id="d59a3-131">如需相關指示，請參閱[在 Office 365 中準備識別碼清單內容搜尋的 CSV 檔案](csv-file-for-an-id-list-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="d59a3-131">For instructions, see [Prepare a CSV file for an ID list Content Search in Office 365](csv-file-for-an-id-list-content-search.md).</span></span>
    
    <span data-ttu-id="d59a3-132">此程序中的其餘步驟會遵循預設的新增搜尋工作流程。</span><span class="sxs-lookup"><span data-stu-id="d59a3-132">The remainder of the steps in this procedure follows the default new search workflow.</span></span>
    
4. <span data-ttu-id="d59a3-133">在下拉式清單中按一下 [新增搜尋]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d59a3-133">Click **New search** in the drop-down list.</span></span> 
    
5. <span data-ttu-id="d59a3-134">在 [搜尋查詢]\*\*\*\* 下，指定下列項目：</span><span class="sxs-lookup"><span data-stu-id="d59a3-134">Under **Search query**, specify the following things:</span></span>
    
    ![指定要搜尋的關鍵字、條件和位置](media/1e6de9dd-eac9-4e2a-819d-9740cf6c9106.png)
  
   - <span data-ttu-id="d59a3-136">**搜尋的關鍵字** - 在 [關鍵字]\*\*\*\* 方塊中輸入搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="d59a3-136">**Keywords to search for** – Type a search query in **Keywords** box.</span></span> <span data-ttu-id="d59a3-137">您可以指定關鍵字、例如傳送和接收日期的郵件屬性，或者例如檔案名稱或文件上次變更的日期的文件屬性。</span><span class="sxs-lookup"><span data-stu-id="d59a3-137">You can specify keywords, message properties such as sent and received dates, or document properties such as file names or the date that a document was last changed.</span></span> <span data-ttu-id="d59a3-138">您可以使用內含布林運算子的更複雜的查詢，例如 **AND**、**OR**、**NOT** 和 **NEAR**。</span><span class="sxs-lookup"><span data-stu-id="d59a3-138">You can  use a more complex queries that use a Boolean operator, such as **AND**, **OR**,  **NOT**, **NEAR**, or  ONEAR.</span></span> <span data-ttu-id="d59a3-139">您也可以搜尋文件中的機密資訊 (如身分證號碼) 或搜尋曾在外部共用的文件。</span><span class="sxs-lookup"><span data-stu-id="d59a3-139">You can also search for sensitive information (such as social security numbers) in  documents, or search for documents that have been shared externally.</span></span> <span data-ttu-id="d59a3-140">如果將關鍵字方塊保留空白，則位於指定內容位置的所有內容都會包含在搜尋結果中。</span><span class="sxs-lookup"><span data-stu-id="d59a3-140">If you leave the keyword  box empty, then all content  located in the specified  content sources will be included in  the search results.</span></span>
    
      <span data-ttu-id="d59a3-141">或者，您可以按一下 [顯示關鍵字清單]\*\*\*\* 核取方塊，然後在每一列中輸入關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d59a3-141">Alternatively, you can click the **Show keyword list** checkbox and the type a keyword in each row.</span></span> <span data-ttu-id="d59a3-142">如果您這麼做，每一列的關鍵字會以邏輯運算子 (**c:s**) 連接，其功能與建立的搜尋查詢中的 **OR** 運算子類似。</span><span class="sxs-lookup"><span data-stu-id="d59a3-142">If you do this, the keywords on each row are connected by a logical operator (**c:s**) that is similar in functionality to the **OR** operator in the search query that's created.</span></span> 
    
      <span data-ttu-id="d59a3-143">為什麼要使用關鍵字清單？</span><span class="sxs-lookup"><span data-stu-id="d59a3-143">Why use the keyword list?</span></span> <span data-ttu-id="d59a3-144">您可以取得會顯示有多少個項目符合每個關鍵字的統計資料。</span><span class="sxs-lookup"><span data-stu-id="d59a3-144">You can get statistics that show how many items match each keyword.</span></span> <span data-ttu-id="d59a3-145">這可協助您快速找出哪些關鍵字最有效(和最不有效)。</span><span class="sxs-lookup"><span data-stu-id="d59a3-145">This can help you quickly identify which keywords are the most (and least) effective.</span></span> <span data-ttu-id="d59a3-146">您也可以在一列中使用關鍵字片語 (以括號括住)。</span><span class="sxs-lookup"><span data-stu-id="d59a3-146">Keywords on each row are connected by the OR operator in the search query that's created. You can also use a keyword phrase (surrounded by parentheses) in a row.</span></span> <span data-ttu-id="d59a3-147">如需搜尋統計資料的詳細資訊，請參閱[檢視內容搜尋結果的關鍵字統計資料](view-keyword-statistics-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="d59a3-147">For more information about search statistics, see [View keyword statistics for Content Search results](view-keyword-statistics-for-content-search.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="d59a3-148">為了協助降低大量關鍵字清單造成的問題，您會受限於在關鍵字清單中最多可有 20 列。</span><span class="sxs-lookup"><span data-stu-id="d59a3-148">To help reduce issues caused by large keyword lists, you're now limited to a maximum of 20 rows in the keyword list.</span></span>
    
    - <span data-ttu-id="d59a3-149">**條件** - 您可以新增搜尋條件來縮小搜尋範圍，並傳回更精簡的結果集。</span><span class="sxs-lookup"><span data-stu-id="d59a3-149">Under **Conditions**,   add conditions to a  search query to narrow a search and return a more refined set of results.</span></span> <span data-ttu-id="d59a3-150">每個條件會將一個子句新增至搜尋查詢，當您啟動搜尋時便會建立並執行。</span><span class="sxs-lookup"><span data-stu-id="d59a3-150">Each condition adds a clause to the KQL search query that is created and run when you start the search.</span></span> <span data-ttu-id="d59a3-151">條件會在邏輯上使用功能上與 **AND** 運算子類似的邏輯運算子 (**c:c**) 與關鍵字查詢連結 (在關鍵字方塊中指定)。</span><span class="sxs-lookup"><span data-stu-id="d59a3-151">A condition is logically connected to the keyword query (specified in the keyword box) by a logical operator (**c:c**) that is similar in functionality to the **AND** operator.</span></span> <span data-ttu-id="d59a3-152">這表示結果中包含的項目必須同時滿足關鍵字查詢與一或多個條件。</span><span class="sxs-lookup"><span data-stu-id="d59a3-152">That means that items have to satisfy both the keyword query and the condition to be included in the results.</span></span> <span data-ttu-id="d59a3-153">這是條件協助縮小搜尋結果的方式。</span><span class="sxs-lookup"><span data-stu-id="d59a3-153">This is how conditions help to narrow your results.</span></span> <span data-ttu-id="d59a3-154">如需您可以在搜尋查詢中使用的條件清單和描述，請參閱[內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md#search-conditions)中的「搜尋條件」一節。</span><span class="sxs-lookup"><span data-stu-id="d59a3-154">For a list and description of conditions that you can use in a search query, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md#search-conditions).</span></span>
    
       - <span data-ttu-id="d59a3-155">**位置** - 選擇要搜尋的內容位置。</span><span class="sxs-lookup"><span data-stu-id="d59a3-155">**Locations** – Choose the content locations to search.</span></span>
    
      - <span data-ttu-id="d59a3-156">**所有位置** - 使用此選項來搜尋組織中的所有內容位置。</span><span class="sxs-lookup"><span data-stu-id="d59a3-156">**All locations** – Use this option to search all content locations in your organization.</span></span> <span data-ttu-id="d59a3-157">這包括所有 Exchange 信箱 (包括所有非作用中信箱、所有 Office 365 群組的信箱、所有的 Microsoft Teams 信箱) 中的電子郵件、所有商務用 Skype 交談、所有 SharePoint 和商務用 OneDrive 網站 (包括適用於所有 Office 365 群組和 Microsoft Teams 的網站)，以及所有 Exchange 公用資料夾中的項目。</span><span class="sxs-lookup"><span data-stu-id="d59a3-157">This includes email in all Exchange mailboxes (including all inactive mailboxes, mailboxes for all Office 365 Groups, mailboxes for all Microsoft Teams), all Skype for Business conversations, all SharePoint and OneDrive for Business sites (including the sites for all Office 365 Groups and Microsoft Teams), and items in all Exchange public folders.</span></span>
    
      - <span data-ttu-id="d59a3-158">**特定位置** - 使用此選項來搜尋特定內容位置。</span><span class="sxs-lookup"><span data-stu-id="d59a3-158">**Specific locations** – Use this option to search specific content locations.</span></span> <span data-ttu-id="d59a3-159">您可以搜尋特定 Office 365 服務的所有內容位置 (例如搜尋所有 Exchange 信箱或搜尋所有 SharePoint 網站)，或者您可以搜尋所顯示的任何 Office 365 服務中的特定位置。</span><span class="sxs-lookup"><span data-stu-id="d59a3-159">You can search all content locations for a specific Office 365 service (such as searching all Exchange mailboxes or search all SharePoint sites) or you can search specific locations in any of the Office 365 services that are displayed.</span></span> 
    
        ![用來選擇要搜尋的內容位置的使用者介面](media/9a09708b-f8a2-4382-8c4e-2c610ec33c72.png)
  
         <span data-ttu-id="d59a3-161">您也可以將通訊群組新增到要搜尋的 Exchange 信箱清單。</span><span class="sxs-lookup"><span data-stu-id="d59a3-161">You can also add distribution groups to the list of Exchange mailboxes to search.</span></span> <span data-ttu-id="d59a3-162">針對通訊群組，會搜尋群組成員的信箱。</span><span class="sxs-lookup"><span data-stu-id="d59a3-162">For distribution groups, the mailboxes of group members are searched.</span></span> <span data-ttu-id="d59a3-163">不支援動態通訊群組。</span><span class="sxs-lookup"><span data-stu-id="d59a3-163">Dynamic distribution groups aren't supported.</span></span>
    
       > [!NOTE]
       > <span data-ttu-id="d59a3-164">當您搜尋所有信箱位置或只是特定信箱時，匯出內容搜尋的結果時，會包含儲存在使用者信箱、來自其他 Office 365 應用程式的資料。</span><span class="sxs-lookup"><span data-stu-id="d59a3-164">When you search all mailbox locations or just specific mailboxes, data from other Office 365 applications that's saved to user mailboxes is included when you export the results of a Content Search.</span></span> <span data-ttu-id="d59a3-165">此資料不會包含在估計的搜尋結果中，並且無法提供預覽。</span><span class="sxs-lookup"><span data-stu-id="d59a3-165">This data won't be included in the estimated search results and isn't available for preview.</span></span> <span data-ttu-id="d59a3-166">當您匯出並下載搜尋結果時會包含在內。</span><span class="sxs-lookup"><span data-stu-id="d59a3-166">It is included when you export and download the search results.</span></span> <span data-ttu-id="d59a3-167">如需詳細資訊，請參閱[儲存在 Exchange Online 信箱中的內容](what-is-stored-in-exo-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="d59a3-167">For more information, see [Manage inactive mailboxes in Exchange Online](what-is-stored-in-exo-mailbox.md).</span></span>

    
6. <span data-ttu-id="d59a3-168">設定您的搜尋查詢之後，請按一下 [儲存並執行]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d59a3-168">After you've set up your search query, click **Save & run**.</span></span>
    
7. <span data-ttu-id="d59a3-169">在 [儲存搜尋]\*\*\*\* 頁面上，輸入搜尋的名稱，以及可協助識別搜尋的選擇性描述。</span><span class="sxs-lookup"><span data-stu-id="d59a3-169">On the **Save search** page, type a name for the search, and an optional description that helps identify the search.</span></span> <span data-ttu-id="d59a3-170">搜尋的名稱在組織中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="d59a3-170">The name of the search has to be unique in your organization.</span></span> 
    
8. <span data-ttu-id="d59a3-171">按一下 [儲存]\*\*\*\* 開始搜尋。</span><span class="sxs-lookup"><span data-stu-id="d59a3-171">Click **ok** to start running the advanced search.</span></span> 
    
    <span data-ttu-id="d59a3-172">儲存並執行搜尋之後，搜尋所傳回的任何結果會顯示在結果窗格中。</span><span class="sxs-lookup"><span data-stu-id="d59a3-172">After you save and run the search, any results returned by the search are displayed in the results pane.</span></span> <span data-ttu-id="d59a3-173">根據您設定預覽設定的方式，搜尋結果會顯示或者您可以按一下 [預覽結果]\*\*\*\* 來加以檢視。</span><span class="sxs-lookup"><span data-stu-id="d59a3-173">Depending on how you have the preview setting configured, the search results are display or you have to click **Preview results** to view them.</span></span> <span data-ttu-id="d59a3-174">如需詳細資料，請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="d59a3-174">See the next section for details.</span></span> 
    
<span data-ttu-id="d59a3-175">若要再次存取此內容搜尋，或存取 [內容搜尋]\*\*\*\* 頁面上所列的其他內容搜尋，請選取搜尋，然後按一下 [開啟]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d59a3-175">To access this content search again or access other content searches listed on the **Content search** page, select the search and then click **Open**.</span></span> 
  
<span data-ttu-id="d59a3-176">若要清除結果，或建立另一個搜尋，請按一下 [![加號圖示](media/O365-MDM-CreatePolicy-AddIcon.gif) 新增搜尋]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d59a3-176">To clear the results or create another search, click ![Add icon](media/O365-MDM-CreatePolicy-AddIcon.gif) **New search**.</span></span> 

  
## <a name="preview-search-results"></a><span data-ttu-id="d59a3-177">預覽搜尋結果</span><span class="sxs-lookup"><span data-stu-id="d59a3-177">Preview search results</span></span>

<span data-ttu-id="d59a3-178">預覽搜尋結果有兩個組態設定。</span><span class="sxs-lookup"><span data-stu-id="d59a3-178">There are two configuration settings for previewing search results.</span></span> <span data-ttu-id="d59a3-179">執行新搜尋或開啟現有的搜尋之後，請按一下 **個別結果** 來檢視下列預覽設定：</span><span class="sxs-lookup"><span data-stu-id="d59a3-179">After you run a new search or open an existing search, click \*\* Individual results \*\* to view the following preview settings:</span></span> 
  
![預覽搜尋結果設定](media/83519477-1c85-4442-8886-481f186fd758.png)
  
1. <span data-ttu-id="d59a3-181">**自動預覽結果** - 此設定會在您執行搜尋後顯示搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="d59a3-181">**Preview results automatically** – This setting displays the search results after you a run a search.</span></span>
    
2. <span data-ttu-id="d59a3-182">**手動預覽結果** - 此設定會在搜尋結果窗格中顯示預留位置，並顯示 [預覽結果]\*\*\*\* 按鈕，您必須按一下該按鈕才能顯示搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="d59a3-182">**Preview results manually** – This setting displays placeholders in the search results pane, and displays the **Preview results** button that you have to click to display the search results.</span></span> <span data-ttu-id="d59a3-183">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="d59a3-183">This is the default setting.</span></span> <span data-ttu-id="d59a3-184">透過不要在開啟現有搜尋時自動顯示搜尋結果，這有助於增強搜尋效能。</span><span class="sxs-lookup"><span data-stu-id="d59a3-184">It helps enhance search performance by not automatically displaying the search results when you open an existing search.</span></span> 
    
<span data-ttu-id="d59a3-185">可供預覽的項目數有相關的限制。</span><span class="sxs-lookup"><span data-stu-id="d59a3-185">There are limits related to how many items are available to be previewed.</span></span> <span data-ttu-id="d59a3-186">如需詳細資訊，請參閱[內容搜尋的限制](limits-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="d59a3-186">For more information, see [Keyword queries and search conditions for Content Search](limits-for-content-search.md).</span></span> 
  
<span data-ttu-id="d59a3-187">如需可預覽的受支援檔案類型清單，請參閱「有關內容搜尋的詳細資訊」小節中的[預覽搜尋結果](#previewing-search-results)。</span><span class="sxs-lookup"><span data-stu-id="d59a3-187">For a list of supported file types that can be previewed, see [Previewing search results](#previewing-search-results) in the "More information about content search" section.</span></span> <span data-ttu-id="d59a3-188">如果某個檔案類型不支援預覽，或者若要下載文件的副本，您可以按一下 [下載原始檔案]\*\*\*\* 來將它下載至本機電腦。</span><span class="sxs-lookup"><span data-stu-id="d59a3-188">If a file type isn't supported for preview or to download a copy of a document, you can click **Download original file** to download it to your local computer.</span></span> <span data-ttu-id="d59a3-189">針對 .aspx 網頁，將會包含網頁的 URL，不過您可能沒有存取該頁面的權限。</span><span class="sxs-lookup"><span data-stu-id="d59a3-189">For .aspx Web pages, the URL for the page is included though you might not have permissions to access the page.</span></span> 
  
<span data-ttu-id="d59a3-190">也請注意，未建立索引的項目無法提供預覽。</span><span class="sxs-lookup"><span data-stu-id="d59a3-190">Also note that unindexed items aren't available for previewing.</span></span>
  
## <a name="view-information-and-statistics-about-a-search"></a><span data-ttu-id="d59a3-191">檢視有關搜尋的資訊和統計資料</span><span class="sxs-lookup"><span data-stu-id="d59a3-191">View information and statistics about a search</span></span>

<span data-ttu-id="d59a3-192">建立並執行內容搜尋後，您可以檢視估計的搜尋結果的相關統計資料。</span><span class="sxs-lookup"><span data-stu-id="d59a3-192">After you create and run a content search, you can view statistics about the estimated search results.</span></span> <span data-ttu-id="d59a3-193">這包括搜尋結果的摘要、查詢統計資料，例如具有的項目符合搜尋查詢的內容位置數量，以及具有最符合項目的內容位置名稱。</span><span class="sxs-lookup"><span data-stu-id="d59a3-193">This includes a summary of the search results, the query statistics such as the number of content locations with items that match the search query, and the name of content locations that have the most matching items.</span></span> <span data-ttu-id="d59a3-194">您可以顯示一或多個內容搜尋的統計資料。</span><span class="sxs-lookup"><span data-stu-id="d59a3-194">You can display statistics for one or more content searches.</span></span> <span data-ttu-id="d59a3-195">如此可讓您快速比較多個搜尋的結果，並對您的搜尋查詢的有效性進行相關決策。</span><span class="sxs-lookup"><span data-stu-id="d59a3-195">This lets you quickly compare the results for multiple searches and make decisions about the effectiveness of your search queries.</span></span>
  
<span data-ttu-id="d59a3-196">您也可以將搜尋統計資料和關鍵字統計資料下載至 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="d59a3-196">You can also download the search statistics and keyword statistics to a CSV file.</span></span> <span data-ttu-id="d59a3-197">如此可讓您使用 Excel 中的篩選和排序功能來比較結果，並為您的搜尋結果準備報告。</span><span class="sxs-lookup"><span data-stu-id="d59a3-197">This lets you use the filtering and sorting features in Excel to compare results, and prepare reports for your search results.</span></span>
  
<span data-ttu-id="d59a3-198">若要檢視搜尋統計資料：</span><span class="sxs-lookup"><span data-stu-id="d59a3-198">To view search statistics:</span></span>
  
1. <span data-ttu-id="d59a3-199">在 [內容搜尋]\*\*\*\* 頁面上，按一下 [開啟]\*\*\*\*，然後按一下您想要檢視其統計資料的搜尋。</span><span class="sxs-lookup"><span data-stu-id="d59a3-199">On the **Content search** page, click **Open** and then click the search that you want to view the statistic for.</span></span> 
    
2. <span data-ttu-id="d59a3-200">在飛出視窗頁面上，按一下 [開啟查詢]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d59a3-200">On the flyout page, click **Open query**.</span></span> 
    
3. <span data-ttu-id="d59a3-201">在 [個別結果]\*\*\*\* 下拉式清單中，按一下 [搜尋設定檔]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d59a3-201">In the **Individual results** drop down list, click **Search profile**.</span></span>
    
4. <span data-ttu-id="d59a3-202">在 [類型]\*\*\*\* 下拉式清單中，視您想要檢視的搜尋統計資料而定，按一下下列其中一個選項。</span><span class="sxs-lookup"><span data-stu-id="d59a3-202">In the **Type** drop down list, click one of the following options depending on the search statistics you want to view.</span></span> 
    
  - <span data-ttu-id="d59a3-203">**摘要** - 顯示所搜尋的每個類型內容位置的統計資料。</span><span class="sxs-lookup"><span data-stu-id="d59a3-203">**Summary** – Displays statistics for each type of content locations searched.</span></span> <span data-ttu-id="d59a3-204">這包括包含的項目符合搜尋查詢的內容位置的數量，以及搜尋結果項目的總數量和大小。</span><span class="sxs-lookup"><span data-stu-id="d59a3-204">This contents the number of content locations that contained items that matched the search query, and the total number and size of search result items.</span></span> <span data-ttu-id="d59a3-205">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="d59a3-205">This is the default setting.</span></span>
    
  - <span data-ttu-id="d59a3-206">**查詢** - 顯示搜尋查詢的相關統計資料。</span><span class="sxs-lookup"><span data-stu-id="d59a3-206">**Queries** – Displays statistics about the search query.</span></span> <span data-ttu-id="d59a3-207">這包括查詢統計資料所適用的內容位置類型、適用的搜尋查詢統計資料部分 (請注意，**主要**代表整個搜尋查詢)、包含符合搜尋查詢項目的內容位置的數量，以及所找到符合搜尋查詢項目的總數量和大小 (在指定的內容位置中)。</span><span class="sxs-lookup"><span data-stu-id="d59a3-207">This includes the type of content location the query statistics are applicable to, part of the search query the statistics are applicable to (note that **Primary** indicates the entire search query), the number of the content locations that contain items that match the search query, and the total number and size and items that were found (in the specified content location) that match the search query.</span></span> <span data-ttu-id="d59a3-208">未編製索引項目的統計資料 (也稱為*部分編製索引的項目*) 也會顯示。</span><span class="sxs-lookup"><span data-stu-id="d59a3-208">Statistics for unindexed items (also called *partially indexed items*) are also displayed.</span></span> <span data-ttu-id="d59a3-209">不過，統計資料中只會包含來自信箱的部分編製索引的項目。</span><span class="sxs-lookup"><span data-stu-id="d59a3-209">However, only partially indexed items from mailboxes are included in the statistics.</span></span> <span data-ttu-id="d59a3-210">統計資料中不會包括來自 SharePoint 和 OneDrive 的部分編製索引項目。</span><span class="sxs-lookup"><span data-stu-id="d59a3-210">Partially indexed items from SharePoint and OneDrive are not included in the statistics.</span></span>
    
  - <span data-ttu-id="d59a3-211">**熱門位置** - 顯示每個內容位置中符合搜尋查詢的項目數量的相關統計資料。</span><span class="sxs-lookup"><span data-stu-id="d59a3-211">**Top locations** – Displays statistics about the number of items that match the search query in each content location.</span></span> <span data-ttu-id="d59a3-212">會顯示前 1,000 個位置。</span><span class="sxs-lookup"><span data-stu-id="d59a3-212">The top 1,000 locations are displayed.</span></span>
    
<span data-ttu-id="d59a3-213">如需搜尋統計資料的更詳細資訊，請參閱[檢視內容搜尋結果的關鍵字統計資料](view-keyword-statistics-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="d59a3-213">For more detailed information about search statistics, see [View keyword statistics for Content Search results](view-keyword-statistics-for-content-search.md).</span></span>
  
  
## <a name="export-search-results"></a><span data-ttu-id="d59a3-214">匯出搜尋結果</span><span class="sxs-lookup"><span data-stu-id="d59a3-214">Export search results</span></span>

<span data-ttu-id="d59a3-215">搜尋執行成功之後，您可以將搜尋結果匯出到本機電腦。</span><span class="sxs-lookup"><span data-stu-id="d59a3-215">After a search is successfully run, you can  export the  search results to a local computer.</span></span> <span data-ttu-id="d59a3-216">當您匯出電子郵件結果時，其會以 PST 檔案或以個別郵件 (.msg files) 形式下載到您的電腦。</span><span class="sxs-lookup"><span data-stu-id="d59a3-216">When you export email results, they can be downloaded to your computer as PST files or as individual messages (.msg files).</span></span> <span data-ttu-id="d59a3-217">從 SharePoint 和 OneDrive 網站匯出內容時，會匯出原生 Office 文件的副本。</span><span class="sxs-lookup"><span data-stu-id="d59a3-217">When you export content from SharePoint and skydrive_pro sites, copies of native Office documents are exported.</span></span> <span data-ttu-id="d59a3-218">匯出的搜尋結果中還有其他文件和報告。</span><span class="sxs-lookup"><span data-stu-id="d59a3-218">There are also additional documents and reports that are included with the exported search results.</span></span> <span data-ttu-id="d59a3-219">您也可以匯出搜尋結果報告，而非實際的項目。</span><span class="sxs-lookup"><span data-stu-id="d59a3-219">You can also export the search results report and not the actual items.</span></span>
  
<span data-ttu-id="d59a3-220">若要匯出搜尋結果：</span><span class="sxs-lookup"><span data-stu-id="d59a3-220">To export search results:</span></span>
  
1. <span data-ttu-id="d59a3-221">在 [內容搜尋]\*\*\*\* 頁面上，按一下您想要匯出其結果的搜尋。</span><span class="sxs-lookup"><span data-stu-id="d59a3-221">On the **Content search** page, select the search that you want to update the results for.</span></span> 
    
2. <span data-ttu-id="d59a3-222">在飛出視窗頁面上，按一下 [![匯出搜尋結果圖示](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) 其他]\*\*\*\*，然後按一下 [匯出結果]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d59a3-222">On the flyout page, click ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **More**, and then click **Export results**.</span></span> <span data-ttu-id="d59a3-223">您也可以匯出搜尋結果報告。</span><span class="sxs-lookup"><span data-stu-id="d59a3-223">You can also export a search results report.</span></span>
    
3. <span data-ttu-id="d59a3-224">完成 [匯出結果]\*\*\*\* 飛出視窗頁面上的區段。</span><span class="sxs-lookup"><span data-stu-id="d59a3-224">Complete the sections on the **Export results** fly out page. Be sure to use the scroll bar to view all export options.</span></span> <span data-ttu-id="d59a3-225">務必使用捲軸來檢視所有的匯出選項。</span><span class="sxs-lookup"><span data-stu-id="d59a3-225">Complete the sections on the Export results fly out page. Be sure to use the scroll bar to view all export options.</span></span> 
    
<span data-ttu-id="d59a3-226">如需詳細指示和疑難排解提示，請參閱：</span><span class="sxs-lookup"><span data-stu-id="d59a3-226">For more detailed instructions and troubleshooting tips, see:</span></span>
  
- [<span data-ttu-id="d59a3-227">匯出內容搜尋結果</span><span class="sxs-lookup"><span data-stu-id="d59a3-227">Export Content Search results</span></span>](export-search-results.md)
    
- [<span data-ttu-id="d59a3-228">匯出內容搜尋報告</span><span class="sxs-lookup"><span data-stu-id="d59a3-228">Export a Content Search report</span></span>](export-a-content-search-report.md)
    
  
## <a name="more-information-about-content-search"></a><span data-ttu-id="d59a3-229">有關內容搜尋的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="d59a3-229">More information about content search</span></span>

<span data-ttu-id="d59a3-230">如需有關內容搜尋的詳細資訊，請參閱以下小節。</span><span class="sxs-lookup"><span data-stu-id="d59a3-230">See the following sections for more information about what's new in Exchange 2013:</span></span>
  
[<span data-ttu-id="d59a3-231">內容搜尋限制</span><span class="sxs-lookup"><span data-stu-id="d59a3-231">Content search limits</span></span>](#content-search-limits)
  
[<span data-ttu-id="d59a3-232">建立搜尋查詢</span><span class="sxs-lookup"><span data-stu-id="d59a3-232">Building a search query</span></span>](#building-a-search-query)
  
[<span data-ttu-id="d59a3-233">搜尋 OneDrive 帳戶</span><span class="sxs-lookup"><span data-stu-id="d59a3-233">Searching OneDrive accounts</span></span>](#searching-onedrive-accounts)
  
[<span data-ttu-id="d59a3-234">搜尋 Microsoft Teams 和 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="d59a3-234">Microsoft Teams and Office 365</span></span>](#searching-microsoft-teams-and-office-365-groups)
  
[<span data-ttu-id="d59a3-235">搜尋非作用中信箱</span><span class="sxs-lookup"><span data-stu-id="d59a3-235">Searching inactive mailboxes</span></span>](#searching-inactive-mailboxes)
  
[<span data-ttu-id="d59a3-236">預覽搜尋結果</span><span class="sxs-lookup"><span data-stu-id="d59a3-236">Previewing search results</span></span>](#previewing-search-results)
  
[<span data-ttu-id="d59a3-237">部分編製索引的項目</span><span class="sxs-lookup"><span data-stu-id="d59a3-237">Partially indexed items in Content Search</span></span>](#partially-indexed-items)
  
### <a name="content-search-limits"></a><span data-ttu-id="d59a3-238">內容搜尋限制</span><span class="sxs-lookup"><span data-stu-id="d59a3-238">Content search limits</span></span>

- <span data-ttu-id="d59a3-239">如需內容搜尋功能適用限制的說明，請參閱[內容搜尋的限制](limits-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="d59a3-239">For a description of the limits that are applied to the Content Search feature, see [Limits for Search in the Office 365 Compliance Center](limits-for-content-search.md).</span></span>
    
- <span data-ttu-id="d59a3-240">Microsoft 會收集所有 Office 365 組織執行的內容搜尋的效能資訊。</span><span class="sxs-lookup"><span data-stu-id="d59a3-240">Microsoft collects performance information for Content Searches run by all Office 365 organizations.</span></span> <span data-ttu-id="d59a3-241">雖然搜尋查詢的複雜性可能會影響搜尋時間，會影響搜尋所需時間的最大因素是搜尋的信箱數量。</span><span class="sxs-lookup"><span data-stu-id="d59a3-241">While the complexity of the search query can impact search times, the biggest factor that affects how long searches take is the number of mailboxes searched.</span></span> <span data-ttu-id="d59a3-242">雖然 Microsoft 不對搜尋時間提供服務等級協定，下表根據搜尋中包含的信箱數量列出內容搜尋的平均搜尋時間。</span><span class="sxs-lookup"><span data-stu-id="d59a3-242">Although Microsoft doesn't provide a Service Level Agreement for search times, the following table lists average search times for a Content Search based on the number of mailboxes included in the search.</span></span>
    
|<span data-ttu-id="d59a3-243">**信箱數目**</span><span class="sxs-lookup"><span data-stu-id="d59a3-243">**Number of mailboxes**</span></span>|<span data-ttu-id="d59a3-244">**平均搜尋時間**</span><span class="sxs-lookup"><span data-stu-id="d59a3-244">**Average uncached search time.**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d59a3-245">100</span><span class="sxs-lookup"><span data-stu-id="d59a3-245">-100</span></span>  <br/> |<span data-ttu-id="d59a3-246">30 秒</span><span class="sxs-lookup"><span data-stu-id="d59a3-246">30 seconds</span></span>  <br/> |
|<span data-ttu-id="d59a3-247">1,000</span><span class="sxs-lookup"><span data-stu-id="d59a3-247">1,000</span></span>  <br/> |<span data-ttu-id="d59a3-248">45 秒</span><span class="sxs-lookup"><span data-stu-id="d59a3-248">45 seconds</span></span>  <br/> |
|<span data-ttu-id="d59a3-249">10,000</span><span class="sxs-lookup"><span data-stu-id="d59a3-249">10,000</span></span>  <br/> |<span data-ttu-id="d59a3-250">4 分鐘</span><span class="sxs-lookup"><span data-stu-id="d59a3-250">4 minutes</span></span>  <br/> |
|<span data-ttu-id="d59a3-251">25,000</span><span class="sxs-lookup"><span data-stu-id="d59a3-251">25,000</span></span>  <br/> |<span data-ttu-id="d59a3-252">10 分鐘</span><span class="sxs-lookup"><span data-stu-id="d59a3-252">10 minutes</span></span>  <br/> |
|<span data-ttu-id="d59a3-253">50,000</span><span class="sxs-lookup"><span data-stu-id="d59a3-253">50,000 per list</span></span>  <br/> |<span data-ttu-id="d59a3-254">20 分鐘</span><span class="sxs-lookup"><span data-stu-id="d59a3-254">20 minutes</span></span>  <br/> |
|<span data-ttu-id="d59a3-255">100,000</span><span class="sxs-lookup"><span data-stu-id="d59a3-255">100,000</span></span>  <br/> |<span data-ttu-id="d59a3-256">25 分鐘</span><span class="sxs-lookup"><span data-stu-id="d59a3-256">25 minutes</span></span>  <br/> |
  
### <a name="building-a-search-query"></a><span data-ttu-id="d59a3-257">建立搜尋查詢</span><span class="sxs-lookup"><span data-stu-id="d59a3-257">Building a search query</span></span>

<span data-ttu-id="d59a3-258">如需建立搜尋查詢、使用布林搜尋運算子和搜尋條件，以及搜尋與組織外部使用者共用的機密資訊類型和內容的詳細資訊，請參閱[內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="d59a3-258">For detailed information about creating a search query, using Boolean search operators and search conditions, and searching for sensitive information types and content shared with users outside your organization, see [Keyword queries and search conditions for Content Search ](keyword-queries-and-search-conditions.md).</span></span>
  
<span data-ttu-id="d59a3-259">使用關鍵字清單建立搜尋查詢時，請記住下列事項。</span><span class="sxs-lookup"><span data-stu-id="d59a3-259">Keep the following things in mind when using the keyword list to create a search query.</span></span>
  
- <span data-ttu-id="d59a3-260">您必須選取 [顯示關鍵字清單]\*\*\*\* 核取方塊，然後在不同的列輸入每個關鍵字來建立搜尋查詢，其中每個列的關鍵字 (或關鍵字字詞) 是用 **OR** 運算子連接。</span><span class="sxs-lookup"><span data-stu-id="d59a3-260">You have to select the **Show keyword list** checkbox and then type each keyword in a separate row to create a search query where the keywords (or keyword phrases) in each row are connected by the **OR** operator.</span></span> <span data-ttu-id="d59a3-261">如果您在輸入關鍵字之後，於關鍵字方塊中貼上關鍵字清單或按下 **Enter** 鍵，就不會使用 **OR** 運算子將其連接。</span><span class="sxs-lookup"><span data-stu-id="d59a3-261">If you paste a list of keywords in the keyword box or press the **Enter** key after typing a keyword, they won't be connected by the **OR** operator.</span></span> <span data-ttu-id="d59a3-262">以下是如何新增關鍵字清單的不正確和正確範例。</span><span class="sxs-lookup"><span data-stu-id="d59a3-262">Here are incorrect and correct examples of how to add a list of keywords.</span></span> 
    
    <span data-ttu-id="d59a3-263">**不正確**</span><span class="sxs-lookup"><span data-stu-id="d59a3-263">**Incorrect:**</span></span>
    
    ![設定關鍵字清單格式的方式不正確 (在關鍵字方塊中貼上清單)](media/fb54e3df-232a-439a-b3d7-27a60ec76a4c.png)
  
    <span data-ttu-id="d59a3-265">**正確**</span><span class="sxs-lookup"><span data-stu-id="d59a3-265">**Correct:**</span></span>
    
    ![設定關鍵字清單格式的方式正確 (選取核取方塊，然後貼上清單)](media/5d511a7b-c1f9-499c-bffe-e075bfc9adec.png)
  
- <span data-ttu-id="d59a3-267">您也可以在 Excel 檔案或純文字檔案中準備關鍵字或關鍵字片語的清單，然後將您的清單複製並貼入關鍵字清單中。</span><span class="sxs-lookup"><span data-stu-id="d59a3-267">You can also prepare a list of keywords or keyword phrases in an Excel file or a plain text file, and then copy and paste your list into the keyword list.</span></span> <span data-ttu-id="d59a3-268">若要這麼做，您必須選取 [顯示關鍵字清單]\*\*\*\* 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d59a3-268">To do this, you have to select the **Show keyword list** check box.</span></span> <span data-ttu-id="d59a3-269">然後在關鍵字清單的第一列按一下，並貼上您的清單。</span><span class="sxs-lookup"><span data-stu-id="d59a3-269">Then, click the first row in the keyword list and paste your list.</span></span> <span data-ttu-id="d59a3-270">來自 Excel 或文字檔案的每一行都會貼到關鍵字清單中的不同列。</span><span class="sxs-lookup"><span data-stu-id="d59a3-270">Each line from the Excel or text file is pasted into separate row in the keyword list.</span></span> 
    
- <span data-ttu-id="d59a3-271">使用關鍵字清單建立查詢之後，最好先驗證搜尋查詢語法，以讓該搜尋查詢成為您想要的查詢。</span><span class="sxs-lookup"><span data-stu-id="d59a3-271">After you create a query using the keyword list, it's a good idea to verify the search query syntax to make the search query is what you intended.</span></span> <span data-ttu-id="d59a3-272">在詳細資料窗格的 [查詢]\*\*\*\* 下顯示的搜尋查詢中，關鍵字使用文字 **(c:s)** 分隔。</span><span class="sxs-lookup"><span data-stu-id="d59a3-272">In the search query that's displayed under **Query** in the details pane, the keywords are separated by the text **(c:s)**.</span></span> <span data-ttu-id="d59a3-273">這表示關鍵字是使用與 **OR** 運算子類似功能的邏輯運算子連接。</span><span class="sxs-lookup"><span data-stu-id="d59a3-273">This indicates that the keywords are connected by a logical operator similar in functionality to the **OR** operator.</span></span> <span data-ttu-id="d59a3-274">同樣地，如果您的搜尋查詢中包含條件，關鍵字與條件以文字 **(c:c)** 分隔。</span><span class="sxs-lookup"><span data-stu-id="d59a3-274">Similarly, if your search query includes conditions, the keywords and the conditions are separated by the text **(c:c)**.</span></span> <span data-ttu-id="d59a3-275">這表示關鍵字是使用與 **AND** 運算子類似功能的邏輯運算子與條件連接。</span><span class="sxs-lookup"><span data-stu-id="d59a3-275">This indicates that the keywords are connected to the conditions with a logical operator similar in functionality to the **AND** operator.</span></span> <span data-ttu-id="d59a3-276">以下是使用關鍵字清單與條件時產生的搜尋查詢的範例 (顯示在 [詳細資料] 窗格中)。</span><span class="sxs-lookup"><span data-stu-id="d59a3-276">Here's an example of the search query (displayed in the Details pane) that results when using the keyword list and a condition.</span></span> 
    
    ![使用關鍵字清單與條件時建立的查詢範例](media/b463750c-57fa-4602-9fed-0d5a420db3ad.png)
  
- <span data-ttu-id="d59a3-278">執行內容搜尋時，Office 365 會自動檢查您的搜尋查詢中是否有不受支援的字元，以及可能未大寫的布林值運算子。</span><span class="sxs-lookup"><span data-stu-id="d59a3-278">When you run a content search, Office 365 automatically checks your search query for unsupported characters and for Boolean operators that may not be capitalized.</span></span> <span data-ttu-id="d59a3-279">不支援的字元通常會隱藏起來，且通常會導致搜尋錯誤或傳回非預期的結果。</span><span class="sxs-lookup"><span data-stu-id="d59a3-279">Unsupported characters are often hidden and typically cause a search error or return unintended results.</span></span> <span data-ttu-id="d59a3-280">如需所檢查不受支援字元的詳細資訊，請參閱[檢查您的內容搜尋查詢是否有錯誤](check-your-content-search-query-for-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="d59a3-280">For more information about the unsupported characters that are checked, see [Check your Content Search query for errors](check-your-content-search-query-for-errors.md).</span></span>
    
- <span data-ttu-id="d59a3-281">如果您有包含非英文字元 (例如中文字元) 關鍵字的搜尋查詢時，您可以按一下 [查詢語言-國家/地區]\*\*\*\*![內容搜尋中的 [查詢語言-國家/地區] 圖示](media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png)，然後選取搜尋的語言-國家/地區文化特性代碼值。</span><span class="sxs-lookup"><span data-stu-id="d59a3-281">If you have a search query that contains keywords for non-English characters (such as Chinese characters), you can click **Query language-country/region**![Query language-country/region icon in Content search](media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) and select a language-country culture code value for the search.</span></span> <span data-ttu-id="d59a3-282">預設的語言-國家/地區為中性。</span><span class="sxs-lookup"><span data-stu-id="d59a3-282">The default language/region is neutral.</span></span> <span data-ttu-id="d59a3-283">如何判斷您是否需要變更內容搜尋的語言設定？</span><span class="sxs-lookup"><span data-stu-id="d59a3-283">How can you tell if you need to change the language setting for a content search?</span></span> <span data-ttu-id="d59a3-284">如果您確定您要搜尋的內容位置包含非英文字元，但搜尋未傳回任何結果，語言設定可能為其原因。</span><span class="sxs-lookup"><span data-stu-id="d59a3-284">If you're certain content locations contain the non-English characters you're searching for, but the search returns no results, the language setting might be the cause.</span></span> 
  
### <a name="searching-onedrive-accounts"></a><span data-ttu-id="d59a3-285">搜尋 OneDrive 帳戶</span><span class="sxs-lookup"><span data-stu-id="d59a3-285">Searching OneDrive accounts</span></span>

- <span data-ttu-id="d59a3-286">若要收集組織中 OneDrive 網站的 URL 清單，請參閱[建立組織中所有 OneDrive 位置的清單](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a)。</span><span class="sxs-lookup"><span data-stu-id="d59a3-286">To collect a list of the URLs for the OneDrive sites in your organization, see [Create a list of all OneDrive locations in your organization](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a).</span></span> <span data-ttu-id="d59a3-287">本文章中的這個指令碼會建立文字檔案，其中包含所有 OneDrive 網站的清單。</span><span class="sxs-lookup"><span data-stu-id="d59a3-287">This script creates a text file that contains a list of all skydrive_pro sites.</span></span> <span data-ttu-id="d59a3-288">若要執行此指令碼，您必須安裝並使用 SharePoint Online 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="d59a3-288">To run this script, you have to install and use the SharePoint Online Management Shell.</span></span> <span data-ttu-id="d59a3-289">請務必將您組織 MySite 網域的 URL 附加至您要搜尋的每個 OneDrive 網站。</span><span class="sxs-lookup"><span data-stu-id="d59a3-289">Be sure to append the URL for your organization’s MySite domain to each skydrive_pro site that you want to search.</span></span> <span data-ttu-id="d59a3-290">這是包含您所有 OneDrive 的網域；例如，`https://contoso-my.sharepoint.com`。</span><span class="sxs-lookup"><span data-stu-id="d59a3-290">This is the domain that contains all your skydrive_pro; for example, https://contoso-my.sharepoint.com.</span></span> <span data-ttu-id="d59a3-291">以下是使用者 OneDrive 網站 URL 的範例：`https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`。</span><span class="sxs-lookup"><span data-stu-id="d59a3-291">Here's an example of a URL for a user's skydrive_pro site: https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com.</span></span>
    
    <span data-ttu-id="d59a3-292">在人員的使用者主體名稱 (UPN) 變更的少數情況下，其 OneDrive 位置的 URL 將會變更以納入新的 UPN。</span><span class="sxs-lookup"><span data-stu-id="d59a3-292">In the rare case that a person's user principal name (UPN) is changed, the URL for their OneDrive location is changed to incorporate the new UPN.</span></span> <span data-ttu-id="d59a3-293">如果發生這種情況，您必須透過新增使用者的新 OneDrive URL 並移除舊 URL 來修改內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="d59a3-293">If this happens, you have to modify a content search by adding the user's new OneDrive URL and removing the old one.</span></span>
  
### <a name="searching-microsoft-teams-and-office-365-groups"></a><span data-ttu-id="d59a3-294">搜尋 Microsoft Teams 和 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="d59a3-294">Microsoft Teams and Office 365</span></span>

<span data-ttu-id="d59a3-295">您可以搜尋與 Office 365 群組或 Microsoft Teams 相關聯的信箱。</span><span class="sxs-lookup"><span data-stu-id="d59a3-295">You can search the mailbox that's associated with an Office 365 Group or a Microsoft Team.</span></span> <span data-ttu-id="d59a3-296">因為 Office 365 群組上建置於 Microsoft Teams 上，搜尋它們的方式很類似。</span><span class="sxs-lookup"><span data-stu-id="d59a3-296">Because Microsoft Teams is built on Office 365 Groups, searching them is similar.</span></span> <span data-ttu-id="d59a3-297">在這兩個情況下，只會搜尋群組或團隊信箱。</span><span class="sxs-lookup"><span data-stu-id="d59a3-297">In both cases, only the group or team mailbox is searched.</span></span> <span data-ttu-id="d59a3-298">不會搜尋群組或團隊成員的信箱。</span><span class="sxs-lookup"><span data-stu-id="d59a3-298">The mailboxes of the group or team members aren't searched.</span></span> <span data-ttu-id="d59a3-299">若要進行搜尋，您必須特別將它們新增至搜尋。</span><span class="sxs-lookup"><span data-stu-id="d59a3-299">To search them, you have to specifically add them to the search.</span></span>
  
<span data-ttu-id="d59a3-300">搜尋 Microsoft Teams 和 Office 365 群組中的內容時，請記住下列事項。</span><span class="sxs-lookup"><span data-stu-id="d59a3-300">Keep the following things in mind when searching for content in Microsoft Teams and Office 365 Groups.</span></span>
  
- <span data-ttu-id="d59a3-301">若要搜尋位於 Teams 和 Office 365 群組中的內容，您必須指定與團隊或群組相關聯的信箱和 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="d59a3-301">To search for content located in Teams and Office 365 Groups, you have to specify the mailbox and SharePoint site that are associated with a team or group.</span></span>
    
- <span data-ttu-id="d59a3-302">在 Exchange Online 中執行 **Get-UnifiedGroup** Cmdlet，以檢視團隊或 Office 365 群組的內容。</span><span class="sxs-lookup"><span data-stu-id="d59a3-302">Run the **Get-UnifiedGroup** cmdlet in Exchange Online to view properties for a team or an Office 365 Group.</span></span> <span data-ttu-id="d59a3-303">這是取得與團隊或群組相關聯的網站 URL 的絕佳方法。</span><span class="sxs-lookup"><span data-stu-id="d59a3-303">This is a good way to get the URL for the site that's associated with a team or a group.</span></span> <span data-ttu-id="d59a3-304">例如，下列命令會顯示名為「資深領導團隊」的 Office 365 群組的所選屬性：</span><span class="sxs-lookup"><span data-stu-id="d59a3-304">For example, the following command displays selected properties for an Office365 group named Senior Leadership Team:</span></span> 
    
  ```
  Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
  DisplayName            : Senior Leadership Team
  Alias                  : seniorleadershipteam
  PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
  SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
  
  ```

    > [!NOTE]
    > <span data-ttu-id="d59a3-305">若要執行 **Get-UnifiedGroup** Cmdlet，您必須獲指派 Exchange Online 中的「僅檢視收件者」角色或者為獲指派「僅檢視收件者」角色之角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="d59a3-305">To run the **Get-UnifiedGroup** cmdlet, you have to be assigned the View-Only Recipients role in Exchange Online or be a member of a role group that's assigned the View-Only Recipients role.</span></span> 
  
- <span data-ttu-id="d59a3-306">搜尋使用者的信箱時，不會搜尋使用者所隸屬的任何團隊或 Office 365 群組。</span><span class="sxs-lookup"><span data-stu-id="d59a3-306">When a user's mailbox is searched, any Office365 group that the user is a member of won't be searched.</span></span> <span data-ttu-id="d59a3-307">同樣地，當您搜尋團隊或 Office 365 群組時，只會搜尋您指定的群組信箱及群組網站。</span><span class="sxs-lookup"><span data-stu-id="d59a3-307">Similarly, when you search a team or an Office 365 Group, only the group mailbox and group site that you specify is searched.</span></span> <span data-ttu-id="d59a3-308">不會搜尋群組成員的信箱和商務用 OneDrive 帳戶，除非您明確地將它們新增至搜尋。</span><span class="sxs-lookup"><span data-stu-id="d59a3-308">The mailboxes and OneDrive for Business accounts of group members aren't searched unless you explicitly add them to the search.</span></span>
    
- <span data-ttu-id="d59a3-309">若要取得團隊或 Office 365 群組的成員清單，您可以在 Microsoft 365 系統管理中心的 [常用] \> [群組]\*\*\*\* 頁面上檢視內容。</span><span class="sxs-lookup"><span data-stu-id="d59a3-309">To get a list of the members of a team or an Office 365 Group, you can view the properties on the **Home \> Groups** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="d59a3-310">或者，您可以在 Exchange Online PowerShell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="d59a3-310">Alternatively, you can run the following command in Exchange Online PowerShell:</span></span> 
    
  ```
  Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress 
  ```

    > [!NOTE]
    > <span data-ttu-id="d59a3-311">若要執行 **Get-UnifiedGroupLinks** Cmdlet，您必須獲指派 Exchange Online 中的「僅檢視收件者」角色或者為獲指派「僅檢視收件者」角色之角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="d59a3-311">To run the **Get-UnifiedGroupLinks** cmdlet, you have to be assigned the View-Only Recipients role in Exchange Online or be a member of a role group that's assigned the View-Only Recipients role.</span></span> 
  
- <span data-ttu-id="d59a3-312">屬於 Teams 頻道一部分的交談會儲存在與團隊相關聯的信箱中。</span><span class="sxs-lookup"><span data-stu-id="d59a3-312">Conversations that are part of a Teams channel are stored in the mailbox that's associated with the team.</span></span> <span data-ttu-id="d59a3-313">同樣地，團隊成員在頻道中共用的檔案會儲存在團隊的 SharePoint 網站上。</span><span class="sxs-lookup"><span data-stu-id="d59a3-313">Similarly, files that team members share in a channel are stored on the team's SharePoint site.</span></span> <span data-ttu-id="d59a3-314">因此，您必須將團隊信箱和 SharePoint 網站新增為內容位置，才能搜尋頻道中的交談和檔案。</span><span class="sxs-lookup"><span data-stu-id="d59a3-314">Therefore, you have to add the team mailbox and SharePoint site as a content location to search conversations and files in a channel.</span></span>
    
- <span data-ttu-id="d59a3-315">或者，屬於 Teams 中聊天清單的交談會儲存在參與聊天的使用者的 Exchange Online 信箱中。</span><span class="sxs-lookup"><span data-stu-id="d59a3-315">Alternatively, conversations that are part of the Chat list in Teams are stored in the Exchange Online mailbox of the users who participate in the chat.</span></span> <span data-ttu-id="d59a3-316">而使用者在聊天交談中共用的檔案會儲存在共用檔案的使用者的商務用 OneDrive 帳戶中。</span><span class="sxs-lookup"><span data-stu-id="d59a3-316">And files that a user shares in Chat conversations are stored in the OneDrive for Business account of the user who shares the file.</span></span> <span data-ttu-id="d59a3-317">因此，您必須將個別使用者信箱和商務用 OneDrive 帳戶新增為內容位置，才能搜尋聊天清單中的交談和檔案。</span><span class="sxs-lookup"><span data-stu-id="d59a3-317">Therefore, you have to add the individual user mailboxes and OneDrive for Business accounts as content locations to search conversations and files in the Chat list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d59a3-318">在 Exchange 混合式部署中，具有內部部署信箱的使用者可能會參與屬於 Teams 中聊天清單的交談。</span><span class="sxs-lookup"><span data-stu-id="d59a3-318">In an Exchange hybrid deployment, users with an on-premises mailbox might participate in conversations that are part of the Chat list in Teams.</span></span> <span data-ttu-id="d59a3-319">在此情況下，來自這些交談的內容也可供搜尋，因為針對具有內部部署信箱的使用者，這些內容會儲存到雲端式存放區域 (稱為*內部部署使用者的雲端式信箱*)。</span><span class="sxs-lookup"><span data-stu-id="d59a3-319">In this case, content from these conversations is also searchable because it's saved to a cloud-based storage area (called a *cloud-based mailbox for on-premises users*) for users who have an on-premises mailbox.</span></span> <span data-ttu-id="d59a3-320">如需詳細資訊，請參閱[在 Office 365 中搜尋內部部署使用者的雲端式信箱](search-cloud-based-mailboxes-for-on-premises-users.md)。</span><span class="sxs-lookup"><span data-stu-id="d59a3-320">For more information, see [Searching cloud-based mailboxes for on-premises users in Office 365](search-cloud-based-mailboxes-for-on-premises-users.md).</span></span>
  
- <span data-ttu-id="d59a3-321">每個團隊或團隊頻道包含一個 Wiki，用於記筆記和進行共同作業。</span><span class="sxs-lookup"><span data-stu-id="d59a3-321">Every team or team channel contains a Wiki for note-taking and collaboration.</span></span> <span data-ttu-id="d59a3-322">Wiki 的內容會自動儲存至 .mht 格式的檔案中。</span><span class="sxs-lookup"><span data-stu-id="d59a3-322">The Wiki content is automatically saved to a file with a .mht format.</span></span> <span data-ttu-id="d59a3-323">此檔案會儲存在團隊 SharePoint 網站上的 Teams Wiki 資料文件庫中。</span><span class="sxs-lookup"><span data-stu-id="d59a3-323">This file is stored in the Teams Wiki Data document library on the team's SharePoint site.</span></span> <span data-ttu-id="d59a3-324">您可以使用「內容搜尋」工具來搜尋 Wiki，方法是將團隊的 SharePoint 網站指定為要搜尋的內容位置。</span><span class="sxs-lookup"><span data-stu-id="d59a3-324">You can use the Content Search tool to search the Wiki by specifying the team's SharePoint site as the content location to search.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="d59a3-325">搜尋團隊或頻道的 Wiki 功能 (搜尋團隊的 SharePoint 網站時) 是在 2017 年 6 月 22 日推出。</span><span class="sxs-lookup"><span data-stu-id="d59a3-325">The capability to search the Wiki for a team or channel (when you search the team's SharePoint site) was released on June 22, 2017.</span></span> <span data-ttu-id="d59a3-326">在該日期當日或之後儲存或更新的 Wiki 頁面可供搜尋。</span><span class="sxs-lookup"><span data-stu-id="d59a3-326">Wiki pages that were saved or updated on that date or after are available to be searched.</span></span> <span data-ttu-id="d59a3-327">在該日期之前儲存或更新的 Wiki 頁面無法供搜尋。</span><span class="sxs-lookup"><span data-stu-id="d59a3-327">Wiki pages last saved or updated before that date aren't available for search.</span></span> 
 
- <span data-ttu-id="d59a3-328">Teams 頻道中的會議及電話的摘要資訊也會儲存在撥入會議或電話使用者的信箱中。</span><span class="sxs-lookup"><span data-stu-id="d59a3-328">Summary information for meetings and calls in a Teams channel are also stored in the mailboxes of users who dialed into the meeting or call.</span></span> <span data-ttu-id="d59a3-329">這表示您可以使用內容搜尋來搜尋這些摘要記錄。</span><span class="sxs-lookup"><span data-stu-id="d59a3-329">This means you can use Content Search to search these summary records.</span></span> <span data-ttu-id="d59a3-330">摘要資訊包含：</span><span class="sxs-lookup"><span data-stu-id="d59a3-330">Summary information includes:</span></span> 
  
  - <span data-ttu-id="d59a3-331">會議或通話的日期、開始時間、結束時間和持續期間</span><span class="sxs-lookup"><span data-stu-id="d59a3-331">Date, start time, end time, and duration of a meeting or call</span></span>

  - <span data-ttu-id="d59a3-332">每個參與者加入或離開會議或通話的日期及時間</span><span class="sxs-lookup"><span data-stu-id="d59a3-332">The date and time when each participant joined or left the meeting or call</span></span>

  - <span data-ttu-id="d59a3-333">傳送到語音信箱的通話</span><span class="sxs-lookup"><span data-stu-id="d59a3-333">Calls sent to voice mail</span></span>

  - <span data-ttu-id="d59a3-334">未接來電或無人接聽的來電</span><span class="sxs-lookup"><span data-stu-id="d59a3-334">Missed or unanswered calls</span></span>

  - <span data-ttu-id="d59a3-335">來電轉接，以兩個不同通話的形式呈現</span><span class="sxs-lookup"><span data-stu-id="d59a3-335">Call transfers, which are represented as two separate calls</span></span>

  <span data-ttu-id="d59a3-336">可能需要最長達 8 小時的時間，會議和通話摘要記錄才可供搜尋。</span><span class="sxs-lookup"><span data-stu-id="d59a3-336">It can take up to 8 hours for meeting and call summary records to be available to be searched.</span></span>

  <span data-ttu-id="d59a3-337">在搜尋結果中，會在 [類型]\*\*\*\* 欄位中將會議摘要識別為 [會議]\*\*\*\*，以及將通話摘要識別為 [通話]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d59a3-337">In the search results, meeting summaries are identified as **Meeting** in the **Type field**, and call summaries are identified as **Call**.</span></span> <span data-ttu-id="d59a3-338">此外，屬於 Teams 頻道和 1xN 聊天的交談，會在 [類型]\*\*\*\* 欄位中識別為 **IM**。</span><span class="sxs-lookup"><span data-stu-id="d59a3-338">Also, conversations that are part of a Teams channel and 1xN chats are identified as **IM** in the **Type** field.</span></span>
  
  ![Teams 會議、通話和 1xN 聊天都可在 [類型] 欄位中識別](media/O365-ContentSearch-Teams-MessageKind.png)

- <span data-ttu-id="d59a3-340">您可以使用 **Kind** 電子郵件屬性或 [郵件類型]\*\*\*\* 搜尋條件來搜尋 Teams 中的專屬內容。</span><span class="sxs-lookup"><span data-stu-id="d59a3-340">You can use the **Kind** email property or the **Message kind** search condition to search specifically for content in Teams.</span></span> 
  
  - <span data-ttu-id="d59a3-341">若要隨著關鍵字搜尋查詢使用 **Kind** 屬性，請在搜尋查詢的 [關鍵字]\*\*\*\* 方塊中輸入 `kind:microsoftteams`。</span><span class="sxs-lookup"><span data-stu-id="d59a3-341">To use the **Kind** property as part of the keyword search query, in the **Keywords** box of a search query, type `kind:microsoftteams`.</span></span>

    ![在關鍵字方塊中使用 kind:microsoftteams](media/O365-ContentSearch-Teams-Keywords.png)
  
  - <span data-ttu-id="d59a3-343">若要使用搜尋條件，請新增 [郵件類型]\*\*\*\* 條件，然後使用值 `microsoftteams`。</span><span class="sxs-lookup"><span data-stu-id="d59a3-343">To use a search condition, add the **Message kind** condition and use the value `microsoftteams`.</span></span> 

    ![使用郵件類型條件搭配值 microsoftteams。](media/O365-ContentSearch-Teams-MessageKindCondition.png)

<span data-ttu-id="d59a3-345">請注意，條件會使用 **AND** 運算子以邏輯方式連接至關鍵字查詢。</span><span class="sxs-lookup"><span data-stu-id="d59a3-345">Note that conditions are logically connected to the keyword query by the **AND** operator.</span></span> <span data-ttu-id="d59a3-346">這表示某個項目必須同時符合關鍵字查詢和搜尋條件，才能在搜尋結果中傳回。</span><span class="sxs-lookup"><span data-stu-id="d59a3-346">That means an item must match both the keyword query and the search condition to be returned in the search results.</span></span> <span data-ttu-id="d59a3-347">如需詳細資訊，請參閱[內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md#guidelines-for-using-conditions)中的「使用條件的指導方針」小節。</span><span class="sxs-lookup"><span data-stu-id="d59a3-347">For more information, see the "Guidelines for using conditions" section in [Keyword queries and search conditions for Content Search.](keyword-queries-and-search-conditions.md#guidelines-for-using-conditions)</span></span>

  
### <a name="searching-inactive-mailboxes"></a><span data-ttu-id="d59a3-348">搜尋非作用中信箱</span><span class="sxs-lookup"><span data-stu-id="d59a3-348">Searching inactive mailboxes</span></span>

<span data-ttu-id="d59a3-349">您可以在內容搜尋中搜尋非作用中信箱。</span><span class="sxs-lookup"><span data-stu-id="d59a3-349">You can search inactive mailboxes in a content search.</span></span> <span data-ttu-id="d59a3-350">若要取得組織中非作用中信箱的清單，請在 Exchange Online PowerShell 中執行命令 `Get-Mailbox -InactiveMailboxOnly`。</span><span class="sxs-lookup"><span data-stu-id="d59a3-350">To get a list of the inactive mailboxes in your organization, run the command  `Get-Mailbox -InactiveMailboxOnly` in Exchange Online PowerShell.</span></span> <span data-ttu-id="d59a3-351">或者，您可以移至安全性與合規性中心中的 [資料控管]\*\*\*\* \> [保留]\*\*\*\*，然後按一下 [更多\*\*\*\*![瀏覽列省略符號](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif)] \> [非作用中信箱]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d59a3-351">Alternatively, you can go to **Data governance** \> **Retention** in the Security & Compliance Center, and then click **More**![Navigation Bar ellipses](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) \> **Inactive mailboxes**.</span></span>
  
<span data-ttu-id="d59a3-352">搜尋非作用中信箱時，請注意以下幾點。</span><span class="sxs-lookup"><span data-stu-id="d59a3-352">Here are a few things to keep in mind when searching inactive mailboxes.</span></span>
  
- <span data-ttu-id="d59a3-353">如果內容搜尋包含使用者信箱，且該信箱接著就會成為非作用中，信箱成為非作用中之後，當您重新執行搜尋時，內容搜尋會繼續搜尋非作用中信箱。</span><span class="sxs-lookup"><span data-stu-id="d59a3-353">If a content search includes a user mailbox and that mailbox is, then made inactive, the content search will continue to search the inactive mailbox when you rerun the search after it becomes inactive.</span></span>
    
- <span data-ttu-id="d59a3-354">有時候，使用者可能會有具有相同 SMTP 地址的作用中信箱及非作用中信箱。</span><span class="sxs-lookup"><span data-stu-id="d59a3-354">Sometimes a user may have an active mailbox and an inactive mailbox that have the same SMTP address.</span></span> <span data-ttu-id="d59a3-355">在此情況下，僅會搜尋您選取做為內容搜尋位置的特定信箱。</span><span class="sxs-lookup"><span data-stu-id="d59a3-355">In this case, only the specific mailbox that you select as a location for a content search is searched.</span></span> <span data-ttu-id="d59a3-356">換句話說，如果您將使用者的信箱新增至搜尋，您無法假設會同時搜尋其作用中和非作用中信箱。</span><span class="sxs-lookup"><span data-stu-id="d59a3-356">In other words, if you add a user's mailbox to a search, you can't assume that both their active and inactive mailboxes are searched.</span></span> <span data-ttu-id="d59a3-357">只會搜尋您明確地新增至搜尋的信箱。</span><span class="sxs-lookup"><span data-stu-id="d59a3-357">Only the mailbox that you explicitly add to the search is searched.</span></span>
    
- <span data-ttu-id="d59a3-358">我們強烈建議您避免使用具有相同 SMTP 地址的作用中信箱及非作用中信箱。</span><span class="sxs-lookup"><span data-stu-id="d59a3-358">We strongly recommend that you avoid having an active mailbox and inactive mailbox with the same SMTP address.</span></span> <span data-ttu-id="d59a3-359">如果您需要重複使用已指派給非作用中信箱的 SMTP 地址，建議您復原非作用中信箱，或將非作用中信箱的內容還原為作用中信箱 (或者作用中信箱的封存)，然後刪除非作用中信箱。</span><span class="sxs-lookup"><span data-stu-id="d59a3-359">If you need to reuse the SMTP address that is assigned to an inactive mailbox, we recommend that you recover the inactive mailbox or restore the contents of an inactive mailbox to an active mailbox (or the archive of an active mailbox), and then delete the inactive mailbox.</span></span> <span data-ttu-id="d59a3-360">如需詳細資訊，請參閱下列其中一個主題：</span><span class="sxs-lookup"><span data-stu-id="d59a3-360">For more information, see the following topics:</span></span>
    
  - [<span data-ttu-id="d59a3-361">在 Office 365 中復原非作用中的信箱</span><span class="sxs-lookup"><span data-stu-id="d59a3-361">Recover an inactive mailbox in Office 365</span></span>](recover-an-inactive-mailbox.md)
    
  - [<span data-ttu-id="d59a3-362">在 Office 365 中還原非作用中的信箱</span><span class="sxs-lookup"><span data-stu-id="d59a3-362">Restore an inactive mailbox in Office 365</span></span>](restore-an-inactive-mailbox.md)
    
  - [<span data-ttu-id="d59a3-363">在 Office 365 中刪除非作用中的信箱</span><span class="sxs-lookup"><span data-stu-id="d59a3-363">Delete an inactive mailbox in Office 365</span></span>](delete-an-inactive-mailbox.md)

  
### <a name="previewing-search-results"></a><span data-ttu-id="d59a3-364">預覽搜尋結果</span><span class="sxs-lookup"><span data-stu-id="d59a3-364">Previewing search results</span></span>

<span data-ttu-id="d59a3-365">您可以在預覽窗格中預覽支援的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="d59a3-365">You can preview supported file types in the preview pane.</span></span> <span data-ttu-id="d59a3-366">如果某個檔案類型不受支援，您必須下載檔案的副本到您的本機電腦以便檢視。</span><span class="sxs-lookup"><span data-stu-id="d59a3-366">If a file type isn't supported, you have to download a copy of the file to your local computer to view it.</span></span> <span data-ttu-id="d59a3-367">支援下列檔案類型，並且可在搜尋結果窗格中預覽。</span><span class="sxs-lookup"><span data-stu-id="d59a3-367">The following file types are supported and can be previewed in the search results pane.</span></span>
  
- <span data-ttu-id="d59a3-368">.txt、.html、.mhtml</span><span class="sxs-lookup"><span data-stu-id="d59a3-368">.txt, .html, .mhtml</span></span>
    
- <span data-ttu-id="d59a3-369">.eml</span><span class="sxs-lookup"><span data-stu-id="d59a3-369">.eml</span></span>
    
- <span data-ttu-id="d59a3-370">.doc、.docx、.docm</span><span class="sxs-lookup"><span data-stu-id="d59a3-370">.doc, .docx, .docm</span></span>
    
- <span data-ttu-id="d59a3-371">.pptm、.pptx</span><span class="sxs-lookup"><span data-stu-id="d59a3-371">.pptm, .pptx</span></span>
    
- <span data-ttu-id="d59a3-372">.pdf</span><span class="sxs-lookup"><span data-stu-id="d59a3-372">.pdf</span></span>
    
<span data-ttu-id="d59a3-373">還支援下列檔案容器類型。</span><span class="sxs-lookup"><span data-stu-id="d59a3-373">Also, the following file container types are supported.</span></span> <span data-ttu-id="d59a3-374">您可以在預覽窗格的容器中檢視檔案的清單。</span><span class="sxs-lookup"><span data-stu-id="d59a3-374">You can view the list of files in the container in the preview pane.</span></span>
  
- <span data-ttu-id="d59a3-375">.zip</span><span class="sxs-lookup"><span data-stu-id="d59a3-375">Zip</span></span>
    
- <span data-ttu-id="d59a3-376">.gzip</span><span class="sxs-lookup"><span data-stu-id="d59a3-376">.gzip</span></span>
    
### <a name="partially-indexed-items"></a><span data-ttu-id="d59a3-377">部分編製索引的項目</span><span class="sxs-lookup"><span data-stu-id="d59a3-377">Partially indexed items</span></span>

- <span data-ttu-id="d59a3-378">如先前所解說，估計的搜尋結果中會包含信箱中部分編製索引的項目。</span><span class="sxs-lookup"><span data-stu-id="d59a3-378">As previously explained, partially indexed items in mailboxes are included in the estimated search results.</span></span> <span data-ttu-id="d59a3-379">估計的搜尋結果中不會包括來自 SharePoint 和 OneDrive 的部分編製索引項目。</span><span class="sxs-lookup"><span data-stu-id="d59a3-379">Partially indexed items from SharePoint and OneDrive aren't included in the estimated search results.</span></span> 
    
- <span data-ttu-id="d59a3-380">若部分編製索引的項目符合搜尋查詢 (因為其他郵件或文件屬性符合搜尋準則)，則不會將它包含在未編製索引項目的估計數量中。</span><span class="sxs-lookup"><span data-stu-id="d59a3-380">If an unindexed item matches the search query (because other message or document properties meet the search criteria), it won't be include in the estimated number of unindexed items.</span></span> <span data-ttu-id="d59a3-381">若搜尋準則排除了部分編製索引的項目，則不會將它包含在未編製索引項目的估計數量中。</span><span class="sxs-lookup"><span data-stu-id="d59a3-381">If a partially indexed item is excluded by the search criteria, it isn't included in the estimated number of unindexed items.</span></span> <span data-ttu-id="d59a3-382">如需詳細資訊，請參閱 [Office 365 的內容搜尋中部分編製索引的項目](partially-indexed-items-in-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="d59a3-382">[Partially indexed items in Content Search in Office 365](partially-indexed-items-in-content-search.md)</span></span>
