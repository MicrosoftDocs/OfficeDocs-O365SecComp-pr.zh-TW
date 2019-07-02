---
title: 在高級 eDiscovery 中收集案例的資料
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
ms.openlocfilehash: 091d6f8835ae1aae2f075f0b510954255c3a6a5c
ms.sourcegitcommit: e323610df2df71c84f536e8a38650d33d8069e41
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2019
ms.locfileid: "34703836"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a><span data-ttu-id="e7e5f-102">在高級 eDiscovery 中收集案例的資料</span><span class="sxs-lookup"><span data-stu-id="e7e5f-102">Collect data for a case in Advanced eDiscovery</span></span>

<span data-ttu-id="e7e5f-103">一旦您識別出對您的情況感興趣的保管人和資料來源, 就可以識別要深入瞭解的檔集合。</span><span class="sxs-lookup"><span data-stu-id="e7e5f-103">Once you have identified custodians and data sources that are of interest for your case, it's time to identify the set of documents to delve into.</span></span> <span data-ttu-id="e7e5f-104">您可以使用高級 eDiscovery 中的搜尋工具, 從 Office 365 中的 custodial 和非 custodial 位置加以識別。</span><span class="sxs-lookup"><span data-stu-id="e7e5f-104">You can use the Search tool in Advanced eDiscovery to identify these from custodial and non-custodial locations in Office 365.</span></span>

<span data-ttu-id="e7e5f-105">執行搜尋之後, 您就可以查看所檢索專案的統計資料, 例如與搜尋查詢相符專案最多的位置。</span><span class="sxs-lookup"><span data-stu-id="e7e5f-105">After you run a search, you will be able to view statistics on the retrieved items such as the locations that had the most items that matched the search query.</span></span> <span data-ttu-id="e7e5f-106">您也可以預覽結果的子集。</span><span class="sxs-lookup"><span data-stu-id="e7e5f-106">You can also preview a subset of the results.</span></span> <span data-ttu-id="e7e5f-107">當您識別想要進一步檢查的檔集合時, 您可以將搜尋結果新增至審閱集, 以收集並處理。</span><span class="sxs-lookup"><span data-stu-id="e7e5f-107">When you've identified the set of documents that want to further examine, you can add the search results to a review set to collect and process.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="e7e5f-108">Create a search</span><span class="sxs-lookup"><span data-stu-id="e7e5f-108">Create a search</span></span>

<span data-ttu-id="e7e5f-109">按一下 [**搜尋**] 索引標籤上的 [**新增搜尋**], 即可啟動引導您完成建立搜尋的嚮導。</span><span class="sxs-lookup"><span data-stu-id="e7e5f-109">Clicking **New search** on the **Searches** tab will start a wizard that guides you through creating a search.</span></span> <span data-ttu-id="e7e5f-110">如需如何建立搜尋的詳細資訊, 請參閱[建立搜尋以收集資料](create-search-to-collect-data.md)。</span><span class="sxs-lookup"><span data-stu-id="e7e5f-110">For detailed information on how to create a search, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="e7e5f-111">在建立搜尋之後, 會顯示含有詳細資料的飛出頁面。</span><span class="sxs-lookup"><span data-stu-id="e7e5f-111">After a search is created, a flyout page with details is displayed.</span></span> <span data-ttu-id="e7e5f-112">請注意, [**統計資料]** 和 [**預覽**] 按鈕最初會呈現為灰色, 因為尚未完成搜尋。</span><span class="sxs-lookup"><span data-stu-id="e7e5f-112">Note that the **Statistics** and **Preview** buttons are initially grayed out because the search has not completed yet.</span></span> <span data-ttu-id="e7e5f-113">您可以在 [**搜尋**] 索引標籤上追蹤搜尋的進度。</span><span class="sxs-lookup"><span data-stu-id="e7e5f-113">You can keep track of the progress of the search on the **Searches** tab.</span></span>

## <a name="view-search-results-and-statistics"></a><span data-ttu-id="e7e5f-114">查看搜尋結果和統計資料</span><span class="sxs-lookup"><span data-stu-id="e7e5f-114">View search results and statistics</span></span>

<span data-ttu-id="e7e5f-115">內容搜尋有兩個元件: [統計資料 (估計)] 和 [預覽]。</span><span class="sxs-lookup"><span data-stu-id="e7e5f-115">There are two components of a content search: Statistics (Estimates) and Preview.</span></span> <span data-ttu-id="e7e5f-116">每個元件完成後, 您就會看到 [**搜尋**] 索引標籤上的對應欄中顯示的狀態, 從\*\*\*\* [已**提交**至完成] 的 [**已完成**]。</span><span class="sxs-lookup"><span data-stu-id="e7e5f-116">As each of these components complete, you will see the status displayed in the corresponding columns on the **Searches** tab change from from **Submitted** to **In progress** to **Completed**.</span></span>

<span data-ttu-id="e7e5f-117">搜尋預估完成後, 按一下 [搜尋] 以顯示飛出頁面, 此頁面會顯示搜尋結果的一些高階統計資料。</span><span class="sxs-lookup"><span data-stu-id="e7e5f-117">Once the search estimate is completed, click the search to display the flyout page, which will display some high-level statistics about the results of the search.</span></span> <span data-ttu-id="e7e5f-118">此時,**統計資料**按鈕將會使用中。</span><span class="sxs-lookup"><span data-stu-id="e7e5f-118">At this point, the **Statistics** button will be active.</span></span> <span data-ttu-id="e7e5f-119">您可以按一下它以查看搜尋統計資料, 例如:</span><span class="sxs-lookup"><span data-stu-id="e7e5f-119">You can click it to see search statistics, such as:</span></span>

- <span data-ttu-id="e7e5f-120">摘要</span><span class="sxs-lookup"><span data-stu-id="e7e5f-120">Summary</span></span>
- <span data-ttu-id="e7e5f-121">頂端位置</span><span class="sxs-lookup"><span data-stu-id="e7e5f-121">Top locations</span></span>
- <span data-ttu-id="e7e5f-122">查詢</span><span class="sxs-lookup"><span data-stu-id="e7e5f-122">Queries</span></span>

<span data-ttu-id="e7e5f-123">如需搜尋統計資料的詳細資訊, 請參閱[搜尋統計資料](search-statistics.md)。</span><span class="sxs-lookup"><span data-stu-id="e7e5f-123">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

<span data-ttu-id="e7e5f-124">預覽完成後,**預覽**按鈕就會使用中。</span><span class="sxs-lookup"><span data-stu-id="e7e5f-124">Once preview is completed, the **Preview** button will be active.</span></span> <span data-ttu-id="e7e5f-125">按一下它以預覽結果的抽樣子集。</span><span class="sxs-lookup"><span data-stu-id="e7e5f-125">Click it to preview a sampled subset of the results.</span></span>

## <a name="adding-search-results-to-a-review-set"></a><span data-ttu-id="e7e5f-126">將搜尋結果新增至審閱集</span><span class="sxs-lookup"><span data-stu-id="e7e5f-126">Adding search results to a review set</span></span>

<span data-ttu-id="e7e5f-127">當您準備好收集及處理整個搜尋結果時, 您可以將其新增至審閱集來執行。</span><span class="sxs-lookup"><span data-stu-id="e7e5f-127">When you are ready to collect and process the entire results of a search, you can do so by adding it to a review set.</span></span> <span data-ttu-id="e7e5f-128">如需詳細資訊, 請參閱[將資料新增至審閱集](add-data-to-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="e7e5f-128">For details, see [Add data to a review set](add-data-to-review-set.md).</span></span> 