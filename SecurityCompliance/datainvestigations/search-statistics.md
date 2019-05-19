---
title: 搜尋統計資料
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
ms.openlocfilehash: 99310723ed0c157c45363c45c4cca56200d263a7
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153595"
---
# <a name="search-statistics"></a><span data-ttu-id="67c74-102">搜尋統計資料</span><span class="sxs-lookup"><span data-stu-id="67c74-102">Search statistics</span></span>

<span data-ttu-id="67c74-103">有效的方法若要驗證您的搜尋結果時調查資料事件來檢視您的搜尋結果，以確保其符合您預期的相關統計資料。</span><span class="sxs-lookup"><span data-stu-id="67c74-103">An effective way to validate your search results when investigation a data incident is to view the statistics about your search results to make sure they align with your expectations.</span></span> <span data-ttu-id="67c74-104">當為 [已完成執行搜尋時，下列高階統計資料搜尋的詳細資訊彈出式頁面上會顯示 [**狀態**] 下：</span><span class="sxs-lookup"><span data-stu-id="67c74-104">When a search as finished running, the following high-level statistics are displayed under **Status** on the search details flyout page:</span></span>

![搜尋的詳細資訊彈出式頁面上的搜尋 statisics](../media/SearchDetailsFlyout.png)

- <span data-ttu-id="67c74-106">估計的數量和大小符合搜尋準則的項目。</span><span class="sxs-lookup"><span data-stu-id="67c74-106">The estimated number and size of items that matched the search criteria.</span></span>

- <span data-ttu-id="67c74-107">數目與大小 （也稱為*未編製索引的項目*） 的已局部編製索引項目不可搜尋，但已包含在搜尋內容位置中，找到。</span><span class="sxs-lookup"><span data-stu-id="67c74-107">The number and size of partially indexed items (also called *unindexed items*) that aren't searchable but that were found in the content locations that were included in the search.</span></span>

- <span data-ttu-id="67c74-108">信箱及所搜尋的網站數目。</span><span class="sxs-lookup"><span data-stu-id="67c74-108">The number of mailboxes and sites that were searched.</span></span>

<span data-ttu-id="67c74-109">若要檢視更詳細的統計資料，請按一下 [**統計資料**搜尋詳細資料] 彈出式頁面上。</span><span class="sxs-lookup"><span data-stu-id="67c74-109">To view more detailed statistics, click **Statistics** on the search details flyout page.</span></span> <span data-ttu-id="67c74-110">在 [**搜尋統計資料**] 頁面上，您可以檢視搜尋摘要，包含項目符合搜尋查詢相關的詳細統計資料與搜尋結果的頂端位置。</span><span class="sxs-lookup"><span data-stu-id="67c74-110">On the **Search statistics** page, you can view the search summary, the top location that contained items that matched the search results, and detailed statistics about the search query.</span></span>

![搜尋統計資料] 下拉式清單](../media/SearchStatisticsDropDownList.png)

## <a name="summary"></a><span data-ttu-id="67c74-112">摘要</span><span class="sxs-lookup"><span data-stu-id="67c74-112">Summary</span></span>

<span data-ttu-id="67c74-113">在 [**摘要**] 檢視中，您可以看到依位置類型細分的搜尋結果 （例如，位置包含 Exchange 信箱和 SharePoint 網站）。</span><span class="sxs-lookup"><span data-stu-id="67c74-113">In the **Summary** view, you can see the search results broken down by location type (for example, locations include Exchange mailboxes and SharePoint sites).</span></span> <span data-ttu-id="67c74-114">針對每個位置類型，會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="67c74-114">The following information is displayed for each location type:</span></span>

- <span data-ttu-id="67c74-115">位置會有符合搜尋準則的項目數目。</span><span class="sxs-lookup"><span data-stu-id="67c74-115">The number of locations that had items that matched the search criteria.</span></span>

- <span data-ttu-id="67c74-116">從每個位置類型符合搜尋準則的項目總數。</span><span class="sxs-lookup"><span data-stu-id="67c74-116">The total number of items from each location type that matched the search criteria.</span></span>

- <span data-ttu-id="67c74-117">從每個位置類型符合搜尋準則的項目總大小。</span><span class="sxs-lookup"><span data-stu-id="67c74-117">The total size of items from each location type that matched the search criteria.</span></span>

## <a name="top-locations"></a><span data-ttu-id="67c74-118">上方的位置</span><span class="sxs-lookup"><span data-stu-id="67c74-118">Top locations</span></span>

<span data-ttu-id="67c74-119">在**頂端的位置**] 檢視中，您會看到與大部分的項目符合搜尋準則的個別內容位置。</span><span class="sxs-lookup"><span data-stu-id="67c74-119">In the **Top locations** view, you see the individual content locations with the most items that matched the search criteria.</span></span> <span data-ttu-id="67c74-120">為每個內容的位置，會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="67c74-120">For each content location, the following information is displayed:</span></span>

- <span data-ttu-id="67c74-121">位置; 的名稱電子郵件地址，將信箱和 SharePoint 網站的 URL</span><span class="sxs-lookup"><span data-stu-id="67c74-121">The name of the location; the email address for mailboxes and the URL for SharePoint sites</span></span>

- <span data-ttu-id="67c74-122">位置類型</span><span class="sxs-lookup"><span data-stu-id="67c74-122">The location type</span></span>

- <span data-ttu-id="67c74-123">符合搜尋準則的項目數目</span><span class="sxs-lookup"><span data-stu-id="67c74-123">Number of items that matched the search criteria</span></span>

- <span data-ttu-id="67c74-124">符合搜尋準則的所有項目總大小。</span><span class="sxs-lookup"><span data-stu-id="67c74-124">The total size of all items that matched the search criteria.</span></span>

## <a name="queries"></a><span data-ttu-id="67c74-125">查詢</span><span class="sxs-lookup"><span data-stu-id="67c74-125">Queries</span></span>

<span data-ttu-id="67c74-126">在 [**查詢**] 檢視中，您可以看到每個元件的搜尋查詢的詳細統計資料。</span><span class="sxs-lookup"><span data-stu-id="67c74-126">In the **Queries** view, you can see detailed statistics for each component of the search query.</span></span> <span data-ttu-id="67c74-127">如果您在搜尋查詢中使用關鍵字清單，您可以在**查詢**檢視中顯示多少個項目比對每個關鍵字或關鍵字文句檢視增強的統計資料。</span><span class="sxs-lookup"><span data-stu-id="67c74-127">If you used the keyword list in the search query, you can view enhanced statistics in the **Queries** view  that show how many items match each keyword or keyword phrase.</span></span> <span data-ttu-id="67c74-128">這可協助您快速找出在查詢的哪個部分是最 （和至少） 有效。</span><span class="sxs-lookup"><span data-stu-id="67c74-128">This can help you quickly identify which parts of the query are the most (and least) effective.</span></span> 

<span data-ttu-id="67c74-129">在 [**查詢**] 檢視中，會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="67c74-129">The following information is displayed in the **Queries** view:</span></span>

 - <span data-ttu-id="67c74-130">**位置類型**： 內容位置] 列中顯示的統計資料的類型。</span><span class="sxs-lookup"><span data-stu-id="67c74-130">**Location type** - The type of content location for the statistics displayed in the row.</span></span>

- <span data-ttu-id="67c74-131">**組件**-此欄會顯示下列值之一：**主要**或**關鍵字**。</span><span class="sxs-lookup"><span data-stu-id="67c74-131">**Part** - This column will display one of the following values: **Primary** or **Keyword**.</span></span> <span data-ttu-id="67c74-132">**主要**表示資料列在整個查詢; 上呈現統計資料**關鍵字**表示資料列中的統計資料的其中一個查詢元件。</span><span class="sxs-lookup"><span data-stu-id="67c74-132">**Primary** means the row presents statistics on the entire query; **Keyword** means the statistics in the row are for one of the query components.</span></span>

- <span data-ttu-id="67c74-133">會參照**條件**搜尋查詢的資料列的實際查詢元件。</span><span class="sxs-lookup"><span data-stu-id="67c74-133">**Condition** - The actual query component of the search query the row refers to.</span></span> <span data-ttu-id="67c74-134">如果**主要\*\*\*\*組件**] 欄中的值，會顯示整個搜尋查詢的統計資料;如果值為**關鍵字**，然後會顯示 [**查詢**] 欄中顯示的查詢元件的統計資料。</span><span class="sxs-lookup"><span data-stu-id="67c74-134">If the value in the **Part** column is **Primary**, then the statistics for the entire search query are displayed; if the value is **Keyword**, then the statistics for the component of the query shown in the **Query** column are displayed.</span></span> <span data-ttu-id="67c74-135">例如，如果有使用關鍵字清單，然後其中一個關鍵字的統計資料會顯示。</span><span class="sxs-lookup"><span data-stu-id="67c74-135">For example, if the keyword list was used, then the statistics one of the keywords are displayed.</span></span>

  <span data-ttu-id="67c74-136">以下是了解顯示在 [**查詢**] 欄中的統計資料的一些事項：</span><span class="sxs-lookup"><span data-stu-id="67c74-136">Here are some other things to know about the statistics displayed in the **Queries** column:</span></span>
  
  - <span data-ttu-id="67c74-137">當您搜尋的所有內容信箱中 （藉由不指定任何關鍵字），實際的查詢是 **(大小 > = 0)** 以便會傳回所有項目</span><span class="sxs-lookup"><span data-stu-id="67c74-137">When you search for all content in mailboxes (by not specifying any keywords), the actual query is **(size >= 0)** so that all items are returned</span></span>
  
  - <span data-ttu-id="67c74-138">當您搜尋 SharePoint 和 OneDrive 網站時，兩個下列元件新增至搜尋查詢：</span><span class="sxs-lookup"><span data-stu-id="67c74-138">When you search SharePoint and OneDrive sites, the two following components are added to the search query:</span></span>
    
    <span data-ttu-id="67c74-139">**不 isexternalcontent: 1** -這會從內部部署 SharePoint 組織排除任何內容</span><span class="sxs-lookup"><span data-stu-id="67c74-139">**NOT IsExternalContent:1** - This excludes any content from an on-premises SharePoint organization</span></span>
    
    <span data-ttu-id="67c74-140">**不 isOneNotePage:1** -這會排除所有 OneNote 檔案，因為這些是重複的任何符合搜尋查詢的文件。</span><span class="sxs-lookup"><span data-stu-id="67c74-140">**NOT isOneNotePage:1** - This excludes all OneNote files because these would be duplicates of any document that matches the search query.</span></span>

- <span data-ttu-id="67c74-141">**在搜尋中的位置**資料列中顯示的內容位置具有符合搜尋查詢的一部分/條件的項目數目。</span><span class="sxs-lookup"><span data-stu-id="67c74-141">**Locations in search** The number of content locations that had items that matched the search query for the part/condition displayed in the row.</span></span> <span data-ttu-id="67c74-142">請注意是否它們包含符合搜尋準則的項目，封存信箱會視為不同的位置。</span><span class="sxs-lookup"><span data-stu-id="67c74-142">Note that archive mailboxes are counted as a separate location if they contain items that match the search criteria.</span></span>

- <span data-ttu-id="67c74-143">資料列中顯示**的項目**比對部分/條件的搜尋準則的項目數總計。</span><span class="sxs-lookup"><span data-stu-id="67c74-143">**Items** - The total number of items that matched the search criteria for the part/condition displayed in the row.</span></span>

- <span data-ttu-id="67c74-144">資料列中顯示**大小**的比對部分/條件的搜尋準則的項目總數。</span><span class="sxs-lookup"><span data-stu-id="67c74-144">**Size** - The total number of items that matched the search criteria for the part/condition displayed in the row.</span></span>