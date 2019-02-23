---
title: 搜尋統計資料
ms.author: markjjo
author: esclee
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 98999d3d82efaace7673d70b0334cb0efb80fc08
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215203"
---
# <a name="search-statistics"></a><span data-ttu-id="57831-102">搜尋統計資料</span><span class="sxs-lookup"><span data-stu-id="57831-102">Search statistics</span></span>

<span data-ttu-id="57831-p101">您可以驗證您的搜尋結果的其中一個方法是要查看周圍以確保它們對齊與您的預期結果的統計資料。搜尋完成時，搜尋的詳細資訊彈出式上顯示高層級的統計資料：</span><span class="sxs-lookup"><span data-stu-id="57831-p101">One way you can validate your search results is to look at the statistics around your results to make sure they align with your expectations. When a search completes, high-level statistics are shown on the search details flyout:</span></span>
- <span data-ttu-id="57831-105">數字及擷取搜尋的項目量</span><span class="sxs-lookup"><span data-stu-id="57831-105">Number and volume of items retrieved by the search</span></span>
- <span data-ttu-id="57831-106">數目與大量的部分編製索引/未建立索引在搜尋位置中找到的項目</span><span class="sxs-lookup"><span data-stu-id="57831-106">Number and volume of partially indexed/unindexed items that were found in the search locations</span></span>
- <span data-ttu-id="57831-p102">搜尋的信箱及位置的數目。以檢視詳細統計資料，請按一下 ["統計資料 」 搜尋的詳細資訊彈出式。</span><span class="sxs-lookup"><span data-stu-id="57831-p102">Number of mailboxes and locations searched. In order to view more detailed statistics, click on "Statistics" from the search details flyout.</span></span>

## <a name="summary"></a><span data-ttu-id="57831-109">摘要</span><span class="sxs-lookup"><span data-stu-id="57831-109">Summary</span></span>

<span data-ttu-id="57831-p103">在摘要檢視中，您可以看到位置類型 (例如 Exchange) 來細分的搜尋結果。每個位置類型，您可以看到：</span><span class="sxs-lookup"><span data-stu-id="57831-p103">In Summary view, you can see the search results broken down by location type (e.g. Exchange). For each location type, you can see:</span></span>
- <span data-ttu-id="57831-112">位置鎖符合搜尋條件的項目數目</span><span class="sxs-lookup"><span data-stu-id="57831-112">Number of locations that had items that matched the search conditions</span></span>
- <span data-ttu-id="57831-113">從下列位置符合搜尋條件的項目數</span><span class="sxs-lookup"><span data-stu-id="57831-113">Number of items from these locations that matched the search conditions</span></span>
- <span data-ttu-id="57831-114">總量符合搜尋條件的項目。</span><span class="sxs-lookup"><span data-stu-id="57831-114">Total volume of items that matched the search conditions.</span></span>

## <a name="top-locations"></a><span data-ttu-id="57831-115">上方的位置</span><span class="sxs-lookup"><span data-stu-id="57831-115">Top locations</span></span>

<span data-ttu-id="57831-p104">在上方的位置檢視中，您會看到最符合項目的個別位置。針對每個位置中，您會看到：</span><span class="sxs-lookup"><span data-stu-id="57831-p104">In Top locations view, you see the individual locations with the most matches. For each location, you will see:</span></span>
- <span data-ttu-id="57831-118">位置名稱 (例如 SharePoint URL)</span><span class="sxs-lookup"><span data-stu-id="57831-118">Location name (e.g. SharePoint URL)</span></span>
- <span data-ttu-id="57831-119">位置類型</span><span class="sxs-lookup"><span data-stu-id="57831-119">Location type</span></span>
- <span data-ttu-id="57831-120">比對搜尋條件的項目數</span><span class="sxs-lookup"><span data-stu-id="57831-120">Number of items that matched the search conditions</span></span>
- <span data-ttu-id="57831-121">總量符合搜尋條件的項目。</span><span class="sxs-lookup"><span data-stu-id="57831-121">Total volume of items that matched the search conditions.</span></span>

## <a name="queries"></a><span data-ttu-id="57831-122">查詢</span><span class="sxs-lookup"><span data-stu-id="57831-122">Queries</span></span>

<span data-ttu-id="57831-p105">如果您已在查詢中使用 (c:s) 關鍵字] 或 [關鍵字列，您可以看到分解為您在每個位置類型的查詢檢視中的查詢。每個位置類型，您會看到：</span><span class="sxs-lookup"><span data-stu-id="57831-p105">If you have used (c:s) keyword or keyword rows in your query, then you can see the breakdown of your query in Queries view per location type. For each location type, you will see:</span></span>

- <span data-ttu-id="57831-p106">組件： 此資料行必須單字"主要"或"關鍵字"。「 主要"表示 [列在整個查詢中，提供統計資料而"關鍵字"表示一種查詢元件。</span><span class="sxs-lookup"><span data-stu-id="57831-p106">Part: this column will either have the word "Primary" or "Keyword". "Primary" means that the row presents statistics on the entire query, whereas "Keyword" means one of the query components.</span></span>

- <span data-ttu-id="57831-p107">查詢： 的實際查詢元件之列參照。如果"主要"組件，這是整個查詢;如果組件 」 關鍵字"，您會看到其中一個查詢元件。</span><span class="sxs-lookup"><span data-stu-id="57831-p107">Query: the actual query component the row refers to. If Part is "Primary", this will be the entire query; if Part was "Keyword", you will see one of the query components here.</span></span>
  
  - <span data-ttu-id="57831-129">（透過未指定任何關鍵字） 中搜尋所有 contentin 信箱的實際查詢是 (大小 > = 0)，所以會傳回所有的項目</span><span class="sxs-lookup"><span data-stu-id="57831-129">When you search all contentin mailboxes (by not specifying any keywords), the actual query is (size >= 0) so that all items are returned</span></span>
  
  - <span data-ttu-id="57831-130">當您搜尋 SharePoint Online 和 OneDrive 商務網站時，會新增兩個下列元件：</span><span class="sxs-lookup"><span data-stu-id="57831-130">When you search SharePoint Online and OneDrive for Business sites, the two following components are added:</span></span>
    
    - <span data-ttu-id="57831-131">不 IsExternalContent:1-從內部部署 SharePoint 組織排除任何內容</span><span class="sxs-lookup"><span data-stu-id="57831-131">NOT IsExternalContent:1 - excludes any content from an on-premises SharePoint organization</span></span>
    
    - <span data-ttu-id="57831-132">不 isOneNotePage： 1-排除所有 OneNote 檔案因為這些是任何符合搜尋查詢的文件的重複項目。</span><span class="sxs-lookup"><span data-stu-id="57831-132">NOT isOneNotePage: 1 - excludes all OneNote files because these would be duplicates of any document that matches the search query.</span></span>

- <span data-ttu-id="57831-133">位置鎖符合搜尋條件的項目數目。</span><span class="sxs-lookup"><span data-stu-id="57831-133">Number of locations that had items that matched the search conditions.</span></span>

- <span data-ttu-id="57831-134">從下列位置符合搜尋條件的項目數。</span><span class="sxs-lookup"><span data-stu-id="57831-134">Number of items from these locations that matched the search conditions.</span></span>

- <span data-ttu-id="57831-135">總量符合搜尋條件的項目。</span><span class="sxs-lookup"><span data-stu-id="57831-135">Total volume of items that matched the search conditions.</span></span>