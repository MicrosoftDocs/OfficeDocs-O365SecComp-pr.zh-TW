---
title: 收集資料的進階 eDiscovery (Preview) 中的案例
ms.author: esclee
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
ms.openlocfilehash: 11e2c336512c91d65bd046c3022d5375ebecde4a
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2019
ms.locfileid: "29695049"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery-preview"></a><span data-ttu-id="d5c79-102">收集資料的進階 eDiscovery (Preview) 中的案例</span><span class="sxs-lookup"><span data-stu-id="d5c79-102">Collect data for a case in Advanced eDiscovery (Preview)</span></span>

<span data-ttu-id="d5c79-p101">一旦您識別 custodians 與您的案例感興趣的資料來源，該是時候來識別的探究的文件]。您可以使用進階的 eDiscovery (Preview) 中的搜尋工具來識別這些從 custodial 和非 custodial Office 365 中的位置。</span><span class="sxs-lookup"><span data-stu-id="d5c79-p101">Once you have identified custodians and data sources that are of interest for your case, it's time to identify the set of documents to delve into. You can use the Search tool in Advanced eDiscovery (Preview) to identify these from custodial and non-custodial locations in Office 365.</span></span>

<span data-ttu-id="d5c79-p102">執行搜尋之後，您將能夠檢視等有符合搜尋查詢的大部分項目位置擷取的項目上的統計資料。您也可以預覽結果的子集。當您已識別想要進一步檢查的文件集時，您可以新增收集及處理工作設在搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="d5c79-p102">After you run a search, you will be able to view statistics on the retrieved items such as the locations that had the most items that matched the search query. You can also preview a subset of the results. When you've identified the set of documents that want to further examine, you can add the search results to a working set to collect and process.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="d5c79-108">建立搜尋</span><span class="sxs-lookup"><span data-stu-id="d5c79-108">Create a search</span></span>

<span data-ttu-id="d5c79-p103">按一下 [**搜尋**] 索引標籤上的 [**新的搜尋**會啟動將引導您建立搜尋的精靈。如需如何建立搜尋的詳細資訊，請參閱 ＜ [Create 搜尋以收集資料](create-search-to-collect-data.md)。</span><span class="sxs-lookup"><span data-stu-id="d5c79-p103">Clicking **New search** on the **Searches** tab will start a wizard that guides you through creating a search. For detailed information on how to create a search, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="d5c79-p104">建立搜尋之後，會顯示彈出式頁面的詳細資料。請注意 [**統計資料**和**預覽**] 按鈕會最初灰因為尚未完成搜尋。您可以追蹤的 [**搜尋**] 索引標籤上的搜尋的進度。</span><span class="sxs-lookup"><span data-stu-id="d5c79-p104">After a search is created, a flyout page with details is displayed. Note that the **Statistics** and **Preview** buttons are initially grayed out because the search has not completed yet. You can keep track of the progress of the search on the **Searches** tab.</span></span>

## <a name="view-search-results-and-statistics"></a><span data-ttu-id="d5c79-114">檢視搜尋結果和統計資料</span><span class="sxs-lookup"><span data-stu-id="d5c79-114">View search results and statistics</span></span>
<span data-ttu-id="d5c79-p105">有兩個搜尋元件的內容： （評估） 的統計資料和預覽。為每個完成這些元件，您會看到從**已提交**變更為 [**進行中**為 [**已完成**狀態顯示在 [**搜尋**] 索引標籤上的對應欄中。</span><span class="sxs-lookup"><span data-stu-id="d5c79-p105">There are two components of a content search: Statistics (Estimates) and Preview. As each of these components complete, you will see the status displayed in the corresponding columns on the **Searches** tab change from from **Submitted** to **In progress** to **Completed**.</span></span>

<span data-ttu-id="d5c79-p106">搜尋 estimate 完成之後，按一下 [顯示彈出式] 頁面上，將會顯示一些高層級的統計資料的搜尋結果的相關搜尋]。此時，**統計資料**] 按鈕會為使用中。您可以按一下它以查看搜尋統計資料，例如：</span><span class="sxs-lookup"><span data-stu-id="d5c79-p106">Once the search estimate is completed, click the search to display the flyout page, which will display some high-level statistics about the results of the search. At this point, the **Statistics** button will be active. You can click it to see search statistics, such as:</span></span>

- <span data-ttu-id="d5c79-120">摘要</span><span class="sxs-lookup"><span data-stu-id="d5c79-120">Summary</span></span>
- <span data-ttu-id="d5c79-121">上方的位置</span><span class="sxs-lookup"><span data-stu-id="d5c79-121">Top locations</span></span>
- <span data-ttu-id="d5c79-122">查詢</span><span class="sxs-lookup"><span data-stu-id="d5c79-122">Queries</span></span>
- <span data-ttu-id="d5c79-123">精簡器</span><span class="sxs-lookup"><span data-stu-id="d5c79-123">Refiners</span></span>

<span data-ttu-id="d5c79-124">如需搜尋統計資料的詳細資訊，請參閱 ＜[搜尋統計資料](search-statistics.md)。</span><span class="sxs-lookup"><span data-stu-id="d5c79-124">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

<span data-ttu-id="d5c79-p107">預覽完成之後，將會為使用中 [**預覽**] 按鈕。按一下該預覽取樣結果的子集。</span><span class="sxs-lookup"><span data-stu-id="d5c79-p107">Once preview is completed, the **Preview** button will be active. Click it to preview a sampled subset of the results.</span></span>

## <a name="adding-search-results-to-a-working-set"></a><span data-ttu-id="d5c79-127">新增搜尋結果的工作集</span><span class="sxs-lookup"><span data-stu-id="d5c79-127">Adding search results to a working set</span></span>

<span data-ttu-id="d5c79-p108">當您準備好收集及處理整個搜尋結果時，您可以將它新增至工作集來執行此動作。如需詳細資訊，請參閱[新增資料至工作集](add-data-to-working-set.md)。</span><span class="sxs-lookup"><span data-stu-id="d5c79-p108">When you are ready to collect and process the entire results of a search, you can do so by adding it to a working set. For details, see [Add data to a working set](add-data-to-working-set.md).</span></span> 