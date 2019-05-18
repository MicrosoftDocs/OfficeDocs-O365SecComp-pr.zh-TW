---
title: 搜尋調查中的資料
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 3e9e1cb6a434a0b8e5f7b723630812e9cdeda36d
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153635"
---
# <a name="search-for-data-in-an-investigation"></a><span data-ttu-id="21104-102">搜尋調查中的資料</span><span class="sxs-lookup"><span data-stu-id="21104-102">Search for data in an investigation</span></span>

<span data-ttu-id="21104-103">在資料調查的 [**搜尋**] 索引標籤上，您可以搜尋中使用關鍵字和條件的 Office 365 中的內容位置找不到、 機密或機密資料。</span><span class="sxs-lookup"><span data-stu-id="21104-103">On the **Search** tab in a data investigation, you can search for misplaced, confidential, or sensitive data in content locations in Office 365 using keywords and conditions.</span></span> 

<span data-ttu-id="21104-104">執行搜尋之後，您可以檢視統計資料，請在搜尋範圍，例如有大部分的項目符合搜尋查詢的內容位置所傳回的項目。</span><span class="sxs-lookup"><span data-stu-id="21104-104">After you run a search, you can view statistics on the items returned by the search, such as the content locations that had the most items that matched the search query.</span></span> <span data-ttu-id="21104-105">您也可以預覽結果的子集。</span><span class="sxs-lookup"><span data-stu-id="21104-105">You can also preview a subset of the results.</span></span> <span data-ttu-id="21104-106">您已識別想要更進一步調查的文件的設定之後，您可以新增搜尋的結果來辨識項集合來進一步程序及分析。</span><span class="sxs-lookup"><span data-stu-id="21104-106">After you've identified the set of documents that want to further investigate, you can add the results of the search to an evidence set to further process and analyze.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="21104-107">Create a search</span><span class="sxs-lookup"><span data-stu-id="21104-107">Create a search</span></span>

1. <span data-ttu-id="21104-108">在和調查]，按一下 [**搜尋**] 索引標籤，然後按一下**新的搜尋**。</span><span class="sxs-lookup"><span data-stu-id="21104-108">In an investigation, click the **Searches** tab, and then click **New search**.</span></span> 

    <span data-ttu-id="21104-109">會顯示一個精靈，將引導您完成建立搜尋的程序。</span><span class="sxs-lookup"><span data-stu-id="21104-109">A wizard is displayed that will guide you through the process of creating a search.</span></span>

2. <span data-ttu-id="21104-110">輸入搜尋名稱及搜尋的選用描述。</span><span class="sxs-lookup"><span data-stu-id="21104-110">Enter a search name and an optional description for the search.</span></span>

3. <span data-ttu-id="21104-111">定義您的搜尋準則。</span><span class="sxs-lookup"><span data-stu-id="21104-111">Define your search criteria.</span></span> <span data-ttu-id="21104-112">使用預先內建的條件卡或使用中的關鍵字查詢的搜尋屬性的名稱，您可以新增搜尋條件。</span><span class="sxs-lookup"><span data-stu-id="21104-112">You can add conditions for the search by using the pre-built condition cards or by using search property names in the keyword query.</span></span> <span data-ttu-id="21104-113">如需詳細資訊，請參閱 <<c0>建立搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="21104-113">For more information, see [Build search queries](build-search-queries.md).</span></span>

4. <span data-ttu-id="21104-114">選擇要搜尋的內容位置 （資料來源）。</span><span class="sxs-lookup"><span data-stu-id="21104-114">Choose the content locations (data sources) to search.</span></span> <span data-ttu-id="21104-115">您可以藉由選取感興趣的特定人員的內容位置 （如果您已新增任何調查） 的範圍搜尋]。</span><span class="sxs-lookup"><span data-stu-id="21104-115">You can scope the search by selecting the content locations of specific people of interest (if you added any to the investigation).</span></span> <span data-ttu-id="21104-116">如果您已新增人員感興趣的調查，您可以新增他們在[管理人員感興趣的](manage-people-of-interest.md#add-people-of-interest)步驟。</span><span class="sxs-lookup"><span data-stu-id="21104-116">If you have added people of interest to the investigation, you can add them by following the steps in [Manage people of interest](manage-people-of-interest.md#add-people-of-interest).</span></span>
 
    <span data-ttu-id="21104-117">在某些情況下，您可能需要先搜尋組織中; 中的所有內容位置或者，您可能需要搜尋不由特定人員所擁有的位置。</span><span class="sxs-lookup"><span data-stu-id="21104-117">In some cases, you may first need to search all content locations in your organization; alternatively, you may need to search locations that aren't owned by a specific person.</span></span> <span data-ttu-id="21104-118">在此案例中，您可以選擇搜尋整個組織或所有位置特定的 Office 365 服務 （例如 Exchange、 SharePoint、 商務用 OneDrive 或 microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="21104-118">In this scenarios, you can choose to search your entire organization, or all locations for a specific Office 365 services (such as Exchange, SharePoint, OneDrive of Business, or Teams.</span></span>

5. <span data-ttu-id="21104-119">儲存並執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="21104-119">Save and run the search.</span></span>

<span data-ttu-id="21104-120">建立搜尋之後，彈出式頁面會顯示關於搜尋的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="21104-120">After the search is created, a flyout page is displayed with details about the search.</span></span> <span data-ttu-id="21104-121">請注意，[**統計資料**和**預覽**] 按鈕一開始變為灰色，因為搜尋尚未完成。</span><span class="sxs-lookup"><span data-stu-id="21104-121">Note that the **Statistics** and **Preview** buttons are initially grayed out because the search hasn't completed.</span></span> <span data-ttu-id="21104-122">您可以追蹤的迴圈的進度藉由監視**搜尋**] 索引標籤上的 [**狀態**] 欄。</span><span class="sxs-lookup"><span data-stu-id="21104-122">You can keep track of the progress of by monitoring the **Status** column on the **Searches** tab.</span></span>

## <a name="view-statistics-and-search-results"></a><span data-ttu-id="21104-123">檢視統計資料和搜尋結果</span><span class="sxs-lookup"><span data-stu-id="21104-123">View statistics and search results</span></span>

<span data-ttu-id="21104-124">建立並啟動資料調查搜尋之後，工具會使用您定義的搜尋準則 （搜尋查詢和內容位置），並符合您的搜尋準則的項目 live 服務中搜尋索引。</span><span class="sxs-lookup"><span data-stu-id="21104-124">After you create and start a data investigation search, the tool uses the search criteria (the search query and content locations) that you defined and searches an index in the live service for items that match your search criteria.</span></span> <span data-ttu-id="21104-125">有三個元件的搜尋所傳回搜尋完成時：</span><span class="sxs-lookup"><span data-stu-id="21104-125">There are three components of a search that are returned when the search is complete:</span></span> 

- <span data-ttu-id="21104-126">**估計**的搜尋結果搜尋只會搜尋索引 （而不是實際的內容位置），因為是預估值 （根據項目中找不到符合搜尋結果的索引）。</span><span class="sxs-lookup"><span data-stu-id="21104-126">**Estimate** - Because the search only searches an index (rather than the actual content locations), the results of a search are an estimate (based on what was found in the index that matched the search results).</span></span> <span data-ttu-id="21104-127">預估的摘要隨即出現在 [**狀態**] 下的 [搜尋] 彈出式頁面上。</span><span class="sxs-lookup"><span data-stu-id="21104-127">A summary of the estimate is displayed on the search flyout page under **Status**.</span></span> <span data-ttu-id="21104-128">請注意，搜尋的評估程序的狀態會顯示**預估狀態**] 欄中的 [**搜尋**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="21104-128">Note that the status for the estimate process for a search is displayed on the **Searches** tab in the **Estimate status** column.</span></span> <span data-ttu-id="21104-129">搜尋 estimate 完成時，此狀態設為**成功**。</span><span class="sxs-lookup"><span data-stu-id="21104-129">When the search estimate is complete, this status is set to **Successful**.</span></span>

- <span data-ttu-id="21104-130">**統計資料**-統計資料會提供更詳細的搜尋結果的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="21104-130">**Statistics** - Statistics provide more detailed information about the search results.</span></span> <span data-ttu-id="21104-131">其中包括下列項目：</span><span class="sxs-lookup"><span data-stu-id="21104-131">This includes the following:</span></span>

    - <span data-ttu-id="21104-132">摘要-類似於搜尋統計資料估計彈出式頁面上顯示的結果。</span><span class="sxs-lookup"><span data-stu-id="21104-132">Summary - Statistics similar to the search estimate results displayed on the flyout page.</span></span>
    - <span data-ttu-id="21104-133">上方的位置-符合搜尋查詢的每個所搜尋的內容位置的項目數目相關的統計資料。</span><span class="sxs-lookup"><span data-stu-id="21104-133">Top locations - Statistics about the number of items that match the search query in each content location that was searched.</span></span> 
    - <span data-ttu-id="21104-134">查詢的搜尋查詢相關的詳細統計資料包括符合搜尋查詢中的每個條件的項目數。</span><span class="sxs-lookup"><span data-stu-id="21104-134">Queries - Detailed statistics about the search query, including the number of items that match each condition in a search query.</span></span>

    <span data-ttu-id="21104-135">在彈出式頁面來檢視這些統計資料，請按一下 [**統計資料**]。</span><span class="sxs-lookup"><span data-stu-id="21104-135">Click **Statistics** on the flyout page to view these statistics.</span></span> <span data-ttu-id="21104-136">請注意這個按鈕是不在作用中，直到**評估狀態**在 [**搜尋**] 索引標籤上的值設為 [**成功**。</span><span class="sxs-lookup"><span data-stu-id="21104-136">Note that this button is inactive until the value of the **Estimate status** on the **Searches** tab is set to **Successful**.</span></span> <span data-ttu-id="21104-137">如需搜尋統計資料的詳細資訊，請參閱 <<c0>搜尋統計資料。</span><span class="sxs-lookup"><span data-stu-id="21104-137">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

- <span data-ttu-id="21104-138">**預覽**-搜尋完成時，您可以檢視範例子集從搜尋所傳回的搜尋結果的實際項目。</span><span class="sxs-lookup"><span data-stu-id="21104-138">**Preview** - When the search is complete, you can view the actual items from a sample subset of the search results returned by the search.</span></span> <span data-ttu-id="21104-139">您可以檢視的項目類型的原生檢視中，任何您也可以檢視項目相關的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="21104-139">YOu can view in the native view of the item type, any you can also view metadata about the item.</span></span> <span data-ttu-id="21104-140">這是一個好方法來快速地判斷如果您的搜尋結果所預期，或者如果您要編輯搜尋]，然後重新執行它。</span><span class="sxs-lookup"><span data-stu-id="21104-140">This is a good way to quickly determine if your search results are what you expected or if you need to edit the search and re-run it.</span></span> <span data-ttu-id="21104-141">按一下 [**預覽**] 彈出式頁面以檢視搜尋結果中的項目。</span><span class="sxs-lookup"><span data-stu-id="21104-141">Click  **Preview** on the flyout page to view items from the search results.</span></span> <span data-ttu-id="21104-142">請注意此按鈕是不在作用中，直到**預覽狀態**在 [**搜尋**] 索引標籤上的值設為 [**成功**。</span><span class="sxs-lookup"><span data-stu-id="21104-142">Note that this button is inactive until the value of the **Preview status** on the **Searches** tab is set to **Successful**.</span></span>
 
> [!NOTE]
> <span data-ttu-id="21104-143">在 [**搜尋**] 索引標籤上的**預估**和**預覽狀態**資料行的 [狀態] 值，而**已送出**、**在進行中**，**成功**。</span><span class="sxs-lookup"><span data-stu-id="21104-143">The status values for the **Estimate status** and **Preview status** columns on the **Searches** tab are **Submitted**, **In progress**, and **Successful**.</span></span> <span data-ttu-id="21104-144">使用搜尋發生錯誤時，會顯示狀態為**Failed** 。</span><span class="sxs-lookup"><span data-stu-id="21104-144">If there is an error with the search, the status of **Failed** is displayed.</span></span>

## <a name="add-search-results-to-evidence"></a><span data-ttu-id="21104-145">將搜尋結果新增至辨識項</span><span class="sxs-lookup"><span data-stu-id="21104-145">Add search results to evidence</span></span>

<span data-ttu-id="21104-146">當您滿意的搜尋結果，且您準備好要分析並修復這些搜尋結果時，您可以將其新增至辨識項集合中調查。</span><span class="sxs-lookup"><span data-stu-id="21104-146">When you're satisfied with the results of a search and you're ready to analyze and remediate those search results, you can add them to an evidence set in the investigation.</span></span> <span data-ttu-id="21104-147">當您新增的辨識項集合**證據**] 索引標籤上的項目時，會發生下列兩件事：</span><span class="sxs-lookup"><span data-stu-id="21104-147">When you add items to an evidence set on the **Evidence** tab, the following two things occur:</span></span>

- <span data-ttu-id="21104-148">在搜尋結果中的所有項目會複製從資料來源中的即時的服務，並複製到 Microsoft cloud 中的安全的 Azure 儲存體位置。</span><span class="sxs-lookup"><span data-stu-id="21104-148">All items in the search results are copied from the data source in the live service, and copied to a secure Azure storage location in the Microsoft cloud.</span></span>

- <span data-ttu-id="21104-149">使辨識項集合中的所有資料完全可搜尋您調查期間，會重新編製索引 （包括的內容和中繼資料） 的所有項目。</span><span class="sxs-lookup"><span data-stu-id="21104-149">All items (including the content and metadata) are re-indexed so that all data in the evidence set is fully searchable during your investigation.</span></span> <span data-ttu-id="21104-150">當您在搜尋中辨識項的資料重新索引徹底和非常快速搜尋中的資料結果在調查期間設定。</span><span class="sxs-lookup"><span data-stu-id="21104-150">Re-indexing the data results in thorough and very fast searches when you search the data in the evidence set during your investigation.</span></span>

<span data-ttu-id="21104-151">將實際資料複製到的辨識項集合在 Azure 中的其中一個優勢是，如時效性或重大事件，您可以快速地包含所造成的損害立即刪除原始資料來源中的即時服務中的可疑內容，然後調查藉由分析已複製到 Azure 的儲存位置的隔離環境的辨識項事件。</span><span class="sxs-lookup"><span data-stu-id="21104-151">One advantage of copying the live data to an evidence set in Azure is that for time-sensitive or critical incidents, you can quickly contain the damage by immediately deleting suspicious content in the original data source in the live service and then investigating the incident by analyzing the evidence that was copied to the quarantined environment of the Azure storage location.</span></span> 

<span data-ttu-id="21104-152">原始的資料複製到的辨識項集合也有助於您調查藉由提供進階的分析工具，例如佈景主題偵測、 近似重複偵測和電子郵件執行緒識別碼。</span><span class="sxs-lookup"><span data-stu-id="21104-152">Copying the original data to the evidence set also facilitates your investigation by providing you with advanced analytics tools such as themes detection, near-duplicate detection, and email thread identification.</span></span>

<span data-ttu-id="21104-153">如有需要，您也可以設定，讓它會隨著資料一併儲存您從 Office 365 收集辨識項新增非 Office 365 資料來源資料。</span><span class="sxs-lookup"><span data-stu-id="21104-153">If necessary, you can also add data from non-Office 365 data sources to an evidence set so that it's stored along with the data you collect from Office 365.</span></span>

<span data-ttu-id="21104-154">若要新增資料至 evidenced 的組，選取**搜尋**] 索引標籤上，然後按一下彈出式頁面上的 [**新增結果辨識項**的搜尋。</span><span class="sxs-lookup"><span data-stu-id="21104-154">To add data to an an evidenced set, select a search on the **Searches** tab, and then clicking **Add results to evidence** on the flyout page.</span></span> <span data-ttu-id="21104-155">請注意，您可以新增至現有的辨識項的資料設定，或建立新的辨識項集合上飛出視窗。</span><span class="sxs-lookup"><span data-stu-id="21104-155">Note that you can add data to an existing evidence set or create a new evidence set on the fly.</span></span>

### <a name="tracking-the-progress-of-adding-search-results-to-evidence"></a><span data-ttu-id="21104-156">追蹤進度的辨識項新增搜尋結果</span><span class="sxs-lookup"><span data-stu-id="21104-156">Tracking the progress of adding search results to evidence</span></span>

<span data-ttu-id="21104-157">將資料新增到辨識項集合是一個長時間執行程序。</span><span class="sxs-lookup"><span data-stu-id="21104-157">Adding data to an evidence set is a long-running process.</span></span> <span data-ttu-id="21104-158">處理程序包含原始資料來源收集項目，從 Office 365 （例如，從信箱和站台），複製至 Azure 儲存體的位置 （此複製程序也稱為*擷取*），然後重新編製索引的項目。</span><span class="sxs-lookup"><span data-stu-id="21104-158">The process includes collecting the items the original data source from Office 365 ( for example, from mailboxes and sites), copying them to the Azure storage location (this copying process is also called *ingestion*), and then re-indexing the items.</span></span> <span data-ttu-id="21104-159">**辨識項的新增資料**行中的 [**搜尋**] 索引標籤或 [**工作**] 索引標籤上，您也可以追蹤進度。</span><span class="sxs-lookup"><span data-stu-id="21104-159">You can either track the progress on the **Jobs** tab or on the **Searches** tab in the **Added data to evidence** column.</span></span> <span data-ttu-id="21104-160">辨識項處理的處理完成後，您可以移至**證據**] 索引標籤上，按一下 [辨識項集合，然後再啟動藉由搜尋、 檢閱、 標記，並將相關的資料匯出為必要的 [您調查。</span><span class="sxs-lookup"><span data-stu-id="21104-160">After the processing of evidence processing is completed, you can go to the **Evidence** tab, click the evidence set, and then start your investigation by searching, reviewing, tagging, and exporting the relevant data as necessary.</span></span>