---
title: 收集資料的進階電子文件中的案例
ms.author: esclee
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
ms.openlocfilehash: 8e67c3c8a693e627bade9e581f0f1e246bf6802a
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151885"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a><span data-ttu-id="6180d-102">收集資料的進階電子文件中的案例</span><span class="sxs-lookup"><span data-stu-id="6180d-102">Collect data for a case in Advanced eDiscovery</span></span>

<span data-ttu-id="6180d-103">一旦您已識別 custodians，針對您的案例感興趣的資料來源，該是時候來識別文件，以探究一組。</span><span class="sxs-lookup"><span data-stu-id="6180d-103">Once you have identified custodians and data sources that are of interest for your case, it's time to identify the set of documents to delve into.</span></span> <span data-ttu-id="6180d-104">您可以使用進階電子文件中的 「 搜尋 」 工具，來識別這些從 custodial 及非 custodial Office 365 中的位置。</span><span class="sxs-lookup"><span data-stu-id="6180d-104">You can use the Search tool in Advanced eDiscovery to identify these from custodial and non-custodial locations in Office 365.</span></span>

<span data-ttu-id="6180d-105">執行搜尋之後，您可以檢視統計資料，例如有符合搜尋查詢的大部分項目位置擷取的項目。</span><span class="sxs-lookup"><span data-stu-id="6180d-105">After you run a search, you will be able to view statistics on the retrieved items such as the locations that had the most items that matched the search query.</span></span> <span data-ttu-id="6180d-106">您也可以預覽結果的子集。</span><span class="sxs-lookup"><span data-stu-id="6180d-106">You can also preview a subset of the results.</span></span> <span data-ttu-id="6180d-107">當您已識別想要更進一步檢查的文件組時，您可以新增設收集和處理程序檢閱搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="6180d-107">When you've identified the set of documents that want to further examine, you can add the search results to a review set to collect and process.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="6180d-108">Create a search</span><span class="sxs-lookup"><span data-stu-id="6180d-108">Create a search</span></span>

<span data-ttu-id="6180d-109">按一下 [**搜尋**] 索引標籤上的 [**新的搜尋**會啟動精靈，引導您完成建立搜尋。</span><span class="sxs-lookup"><span data-stu-id="6180d-109">Clicking **New search** on the **Searches** tab will start a wizard that guides you through creating a search.</span></span> <span data-ttu-id="6180d-110">如需如何建立搜尋的詳細資訊，請參閱 <<c0>建立 「 搜尋 」 來收集資料。</span><span class="sxs-lookup"><span data-stu-id="6180d-110">For detailed information on how to create a search, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="6180d-111">建立搜尋之後，會顯示詳細資料的彈出式頁面。</span><span class="sxs-lookup"><span data-stu-id="6180d-111">After a search is created, a flyout page with details is displayed.</span></span> <span data-ttu-id="6180d-112">請注意，[**統計資料**和**預覽**] 按鈕一開始變為灰色，因為搜尋尚未完成。</span><span class="sxs-lookup"><span data-stu-id="6180d-112">Note that the **Statistics** and **Preview** buttons are initially grayed out because the search has not completed yet.</span></span> <span data-ttu-id="6180d-113">您可以追蹤的 [**搜尋**] 索引標籤上的搜尋的進度。</span><span class="sxs-lookup"><span data-stu-id="6180d-113">You can keep track of the progress of the search on the **Searches** tab.</span></span>

## <a name="view-search-results-and-statistics"></a><span data-ttu-id="6180d-114">檢視搜尋結果，並統計資料</span><span class="sxs-lookup"><span data-stu-id="6180d-114">View search results and statistics</span></span>
<span data-ttu-id="6180d-115">有兩個內容搜尋元件： 統計資料 （評估） 和預覽。</span><span class="sxs-lookup"><span data-stu-id="6180d-115">There are two components of a content search: Statistics (Estimates) and Preview.</span></span> <span data-ttu-id="6180d-116">為每個完成這些元件，您會看到從**已提交**變更為 [**進行中**為 [**已完成**狀態顯示在 [**搜尋**] 索引標籤上的對應資料行。</span><span class="sxs-lookup"><span data-stu-id="6180d-116">As each of these components complete, you will see the status displayed in the corresponding columns on the **Searches** tab change from from **Submitted** to **In progress** to **Completed**.</span></span>

<span data-ttu-id="6180d-117">搜尋 estimate 完成之後，按一下 [搜尋] 以顯示 [彈出式視窗] 頁面上，將會顯示一些相關的搜尋結果的高階統計資料。</span><span class="sxs-lookup"><span data-stu-id="6180d-117">Once the search estimate is completed, click the search to display the flyout page, which will display some high-level statistics about the results of the search.</span></span> <span data-ttu-id="6180d-118">此時，[**統計資料**] 按鈕會在作用中。</span><span class="sxs-lookup"><span data-stu-id="6180d-118">At this point, the **Statistics** button will be active.</span></span> <span data-ttu-id="6180d-119">您可以按一下它，請參閱 < 搜尋統計資料，例如：</span><span class="sxs-lookup"><span data-stu-id="6180d-119">You can click it to see search statistics, such as:</span></span>

- <span data-ttu-id="6180d-120">摘要</span><span class="sxs-lookup"><span data-stu-id="6180d-120">Summary</span></span>
- <span data-ttu-id="6180d-121">上方的位置</span><span class="sxs-lookup"><span data-stu-id="6180d-121">Top locations</span></span>
- <span data-ttu-id="6180d-122">查詢</span><span class="sxs-lookup"><span data-stu-id="6180d-122">Queries</span></span>

<span data-ttu-id="6180d-123">如需搜尋統計資料的詳細資訊，請參閱 <<c0>搜尋統計資料。</span><span class="sxs-lookup"><span data-stu-id="6180d-123">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

<span data-ttu-id="6180d-124">預覽完成之後，[**預覽**] 按鈕會在作用中。</span><span class="sxs-lookup"><span data-stu-id="6180d-124">Once preview is completed, the **Preview** button will be active.</span></span> <span data-ttu-id="6180d-125">按一下以預覽取樣結果的子集。</span><span class="sxs-lookup"><span data-stu-id="6180d-125">Click it to preview a sampled subset of the results.</span></span>

## <a name="adding-search-results-to-a-review-set"></a><span data-ttu-id="6180d-126">將搜尋結果新增至檢閱設定</span><span class="sxs-lookup"><span data-stu-id="6180d-126">Adding search results to a review set</span></span>

<span data-ttu-id="6180d-127">當您準備好要收集和處理整個搜尋的結果時，您可以藉由將它新增至檢閱來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="6180d-127">When you are ready to collect and process the entire results of a search, you can do so by adding it to a review set.</span></span> <span data-ttu-id="6180d-128">如需詳細資訊，請參閱 <<c0>新增資料，以檢閱設定。</span><span class="sxs-lookup"><span data-stu-id="6180d-128">For details, see [Add data to a review set](add-data-to-review-set.md).</span></span> 