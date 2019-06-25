---
title: 產生審閱集的搜尋字詞報告
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
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: 877c0017359ab9193c4cae81cbef4240909053a8
ms.sourcegitcommit: e323610df2df71c84f536e8a38650d33d8069e41
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2019
ms.locfileid: "34714992"
---
# <a name="generate-search-term-report-for-a-review-set"></a><span data-ttu-id="6d06c-102">產生審閱集的搜尋字詞報告</span><span class="sxs-lookup"><span data-stu-id="6d06c-102">Generate search term report for a review set</span></span>

<span data-ttu-id="6d06c-103">在 eDiscovery 中, 查詢檔最常使用的條件之一是使用關鍵字搜尋字詞。</span><span class="sxs-lookup"><span data-stu-id="6d06c-103">In eDiscovery, one of the most frequently used conditions for querying documents is by using keyword search terms.</span></span> <span data-ttu-id="6d06c-104">透過識別包含特定關鍵字的檔 (也稱為*字詞*), 對案例而言很重要, 因此檢閱者可以開始深入瞭解其所面臨的情況。</span><span class="sxs-lookup"><span data-stu-id="6d06c-104">By identifying documents that contain the specific keywords (also referred to as *terms*) that are important to a case, reviewers can begin to get a high-level understanding of what they are facing.</span></span> <span data-ttu-id="6d06c-105">在 Microsoft 365 的 [Advanced eDiscovery] 中, 您可以在檢查集內的儲存查詢上產生搜尋字詞報告, 以完成此項作業。</span><span class="sxs-lookup"><span data-stu-id="6d06c-105">In Advanced eDiscovery in Microsoft 365, you can do precisely this by generating search term reports on saved queries within a review set.</span></span>

## <a name="step-1-create-a-saved-query-in-the-review-set"></a><span data-ttu-id="6d06c-106">步驟 1: 在考核集中建立已儲存的查詢</span><span class="sxs-lookup"><span data-stu-id="6d06c-106">Step 1: Create a saved query in the review set</span></span>

<span data-ttu-id="6d06c-107">若要產生有意義的搜尋字詞報告, 請建立儲存的查詢, 以定義要產生搜尋字詞報告的審閱集中的一組檔。</span><span class="sxs-lookup"><span data-stu-id="6d06c-107">To generate a meaningful search term report, create a saved query that defines the set of documents in the review set that you want to generate a search term report for.</span></span> <span data-ttu-id="6d06c-108">例如, 您可以使用日期範圍或實際的搜尋字詞集合 (使用關鍵字條件卡片) 來建立查詢。</span><span class="sxs-lookup"><span data-stu-id="6d06c-108">For example, you can use a date range or the actual set of search terms (by using the Keywords condition card) to create the query.</span></span> <span data-ttu-id="6d06c-109">若要深入瞭解評審集查詢, 請參閱[查詢評審集中的資料](review-set-search.md)。</span><span class="sxs-lookup"><span data-stu-id="6d06c-109">To learn more about review set queries, see [Query the data in a review set](review-set-search.md).</span></span>

## <a name="step-2-generate-a-search-term-report"></a><span data-ttu-id="6d06c-110">步驟 2: 產生搜尋字詞報告</span><span class="sxs-lookup"><span data-stu-id="6d06c-110">Step 2: Generate a search term report</span></span>

<span data-ttu-id="6d06c-111">有兩種不同的方式可以產生搜尋字詞報告: 透過您在步驟1中建立的已儲存查詢的快顯功能表, 或透過搜尋字詞報告管理主控台。</span><span class="sxs-lookup"><span data-stu-id="6d06c-111">There are two different ways to generate a search term report: through the context menu of the saved query you created in Step 1, or through the search term report management console.</span></span>

- <span data-ttu-id="6d06c-112">若要使用快顯功能表, 請開啟您在步驟1中所建立之已儲存查詢的快顯功能表, 然後按一下 [**產生搜尋字詞報告**]。</span><span class="sxs-lookup"><span data-stu-id="6d06c-112">To use the context menu, open the context menu of the saved query you created in Step 1, and click **Generate search term report**.</span></span>

- <span data-ttu-id="6d06c-113">若要使用管理主控台, 請移至 [**管理審閱集] > View search term reports**], 按一下 [**新增**], 然後選取您在步驟1中建立的已儲存查詢。</span><span class="sxs-lookup"><span data-stu-id="6d06c-113">To use the management console, go to **Manage review set > View search term reports**, click **New**, and then select the saved query you created in Step 1.</span></span>

<span data-ttu-id="6d06c-114">然後, 輸入您想要報告的字詞, 並以分行符號隔開;如果您在步驟1中建立的已儲存查詢使用關鍵字條件卡, 飛入頁面將會預先填入所儲存查詢中所使用的第一個關鍵字條件卡中的字詞。</span><span class="sxs-lookup"><span data-stu-id="6d06c-114">Then, enter the terms you would like to report on, separated by newline; if the saved query that you created in Step 1 used keyword condition card, the flyout page will be pre-populated with the terms from the first keyword condition card used in the saved query.</span></span>

<span data-ttu-id="6d06c-115">然後, 選取最多三個樞軸進行報告, 然後按一下 [**產生**], 這會啟動搜尋字詞報告產生工作。</span><span class="sxs-lookup"><span data-stu-id="6d06c-115">Then, select up to three pivots to report on, and click on **Generate**, which will start the search term report generation job.</span></span>

### <a name="what-is-a-pivot"></a><span data-ttu-id="6d06c-116">何謂資料透視？</span><span class="sxs-lookup"><span data-stu-id="6d06c-116">What is a pivot?</span></span>

<span data-ttu-id="6d06c-117">「轉動」是如何組織報表。</span><span class="sxs-lookup"><span data-stu-id="6d06c-117">Pivots are how the report will be organized.</span></span> <span data-ttu-id="6d06c-118">請考慮下列範例。</span><span class="sxs-lookup"><span data-stu-id="6d06c-118">Consider the following example.</span></span>

- <span data-ttu-id="6d06c-119">已儲存的查詢會檢索10份檔: doc1 到 doc10。</span><span class="sxs-lookup"><span data-stu-id="6d06c-119">The saved query retrieves 10 documents: doc1 thru doc10.</span></span>

- <span data-ttu-id="6d06c-120">doc1、doc2、doc3、doc4、doc5、doc6 和 doc7 包含「eDiscovery」一詞。</span><span class="sxs-lookup"><span data-stu-id="6d06c-120">doc1, doc2, doc3, doc4, doc5, doc6, and doc7 contain the term "eDiscovery".</span></span>

- <span data-ttu-id="6d06c-121">doc6、doc7、doc8、doc9 和 doc10 包含「調查」這一字。</span><span class="sxs-lookup"><span data-stu-id="6d06c-121">doc6, doc7, doc8, doc9, and doc10 contain the term "Investigation".</span></span>

- <span data-ttu-id="6d06c-122">doc1、doc3、doc5、doc7、doc9 是來自保管人 A。</span><span class="sxs-lookup"><span data-stu-id="6d06c-122">doc1, doc3, doc5, doc7, doc9 are from custodian A.</span></span>

- <span data-ttu-id="6d06c-123">doc2、doc4、doc6、doc8、doc10 是來自保管人 B。</span><span class="sxs-lookup"><span data-stu-id="6d06c-123">doc2, doc4, doc6, doc8, doc10 are from custodian B.</span></span>

<span data-ttu-id="6d06c-124">在這種情況下, 如果您要在保管人上產生「eDiscovery」和「調查」的搜尋字詞報告, 並在保管人上進行資料透視, 則搜尋字詞報告的組織方式如下:</span><span class="sxs-lookup"><span data-stu-id="6d06c-124">In this case, if you were to generate a search term report on the terms "eDiscovery" and "Investigation" and pivot on custodians, the search term report would be organized as follows:</span></span>

- <span data-ttu-id="6d06c-125">「eDiscovery」-保管人 A: 4 份檔</span><span class="sxs-lookup"><span data-stu-id="6d06c-125">"eDiscovery" - custodian A: 4 documents</span></span>

- <span data-ttu-id="6d06c-126">「eDiscovery」-管理員 B: 3 份檔</span><span class="sxs-lookup"><span data-stu-id="6d06c-126">"eDiscovery" - custodian B: 3 documents</span></span>

- <span data-ttu-id="6d06c-127">「調查」-管理員 A: 2 份檔</span><span class="sxs-lookup"><span data-stu-id="6d06c-127">"Investigation" - custodian A: 2 documents</span></span>

- <span data-ttu-id="6d06c-128">「調查」-管理員 B: 3 份檔</span><span class="sxs-lookup"><span data-stu-id="6d06c-128">"Investigation" - custodian B: 3 documents</span></span>

## <a name="step-3-download-report"></a><span data-ttu-id="6d06c-129">步驟 3: 下載報表</span><span class="sxs-lookup"><span data-stu-id="6d06c-129">Step 3: Download report</span></span>

<span data-ttu-id="6d06c-130">在搜尋字詞管理主控台中, 您可以追蹤先前建立之搜尋字詞報告工作的狀態。</span><span class="sxs-lookup"><span data-stu-id="6d06c-130">In the search term management console, you can track the status of a previously-created search term report job.</span></span> <span data-ttu-id="6d06c-131">工作完成後, 您可以按一下 [搜尋字詞] 報表的列, 然後按一下 [下載], 這會以 CSV 格式下載搜尋字詞報告。</span><span class="sxs-lookup"><span data-stu-id="6d06c-131">Once the job completes, you can click on the row for the search term report and click "Download", which will download the search term report in a CSV format.</span></span> <span data-ttu-id="6d06c-132">每個專案會有一個資料列 (搜尋字詞、樞軸) 元組, 而每一列會包含下列資訊:</span><span class="sxs-lookup"><span data-stu-id="6d06c-132">There will be one row per (search term, pivots) tuple, and each row will contain the following information:</span></span>

- <span data-ttu-id="6d06c-133">已檢索的檔數目為何？</span><span class="sxs-lookup"><span data-stu-id="6d06c-133">How many documents were retrieved?</span></span>

- <span data-ttu-id="6d06c-134">搜尋字詞在整個檔中找到多少次？</span><span class="sxs-lookup"><span data-stu-id="6d06c-134">How many times was the search term found across the documents?</span></span>

- <span data-ttu-id="6d06c-135">檢索的檔總量是多少？</span><span class="sxs-lookup"><span data-stu-id="6d06c-135">What is the total volume of retrieved documents?</span></span>

- <span data-ttu-id="6d06c-136">已檢索的族數目為何？</span><span class="sxs-lookup"><span data-stu-id="6d06c-136">How many families were retrieved?</span></span>

- <span data-ttu-id="6d06c-137">這些系列的總檔數目是多少, 包括沒有搜尋字詞的檔？</span><span class="sxs-lookup"><span data-stu-id="6d06c-137">What is the total document count of those families, including the documents that did not have the search term?</span></span>

- <span data-ttu-id="6d06c-138">以上的總容量是多少？</span><span class="sxs-lookup"><span data-stu-id="6d06c-138">What is the total volume of the above?</span></span>