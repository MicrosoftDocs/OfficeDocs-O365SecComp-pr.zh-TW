---
title: 將搜尋結果新增至檢閱集
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
ms.openlocfilehash: fac8ab829107befaa1a3f8b3afe1cec8d3468f1b
ms.sourcegitcommit: bac1b5be5db381e6f8d8f652cff1f8ef4d7f6330
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2019
ms.locfileid: "35233320"
---
# <a name="add-search-results-to-a-review-set"></a><span data-ttu-id="08f9b-102">將搜尋結果新增至檢閱集</span><span class="sxs-lookup"><span data-stu-id="08f9b-102">Add search results to a review set</span></span>

<span data-ttu-id="08f9b-103">當您滿意搜尋結果並準備好查看和分析這些搜尋結果時, 您可以將它們新增至案例中的審閱集。</span><span class="sxs-lookup"><span data-stu-id="08f9b-103">When you're satisfied with the results of a search and you're ready to review and analyze those search results, you can add them to a review set in the case.</span></span> <span data-ttu-id="08f9b-104">將原始資料複製到 [審閱] 集時, 也可透過提供高級分析工具 (如主題偵測、接近重複偵測, 以及電子郵件線索識別), 協助審閱和分析程式。</span><span class="sxs-lookup"><span data-stu-id="08f9b-104">Copying the original data to the review set also facilitates the review and analysis process by providing you with advanced analytics tools such as themes detection, near-duplicate detection, and email thread identification.</span></span> <span data-ttu-id="08f9b-105">您也可以將非 Office 365 資料來源中的資料新增至審閱集, 讓您除了從 Office 365 收集的資料之外, 還可以查看該資料。</span><span class="sxs-lookup"><span data-stu-id="08f9b-105">You can also add data from non-Office 365 data sources to a review set so that you can review that data in addition to the data you collect from Office 365.</span></span>

<span data-ttu-id="08f9b-106">當您將搜尋結果新增至審閱集時 (檢查集位於案例的 [**複查集**] 索引標籤上) 時, 會發生下列情況:</span><span class="sxs-lookup"><span data-stu-id="08f9b-106">When you add the results of a search to a review set (review sets are on the **Review sets** tab of the case), the following things occur:</span></span>

- <span data-ttu-id="08f9b-107">會再次執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="08f9b-107">The search is run again.</span></span> <span data-ttu-id="08f9b-108">這表示複製到 [審閱] 集的實際搜尋結果, 可能與上次執行搜尋時所傳回的估計結果不同。</span><span class="sxs-lookup"><span data-stu-id="08f9b-108">This means the actual search results copied to the review set may be different than the estimated results that were returned when the search was last run.</span></span>

- <span data-ttu-id="08f9b-109">搜尋結果中的所有專案都會從 live Office 365 服務中的原始資料來源複製, 並複製到 Microsoft 雲端中的安全 Azure 儲存位置。</span><span class="sxs-lookup"><span data-stu-id="08f9b-109">All items in the search results are copied from the original data source in the live Office 365 services, and copied to a secure Azure storage location in the Microsoft cloud.</span></span>

- <span data-ttu-id="08f9b-110">所有專案 (包括內容和中繼資料) 都會被重新編制索引, 以便在複查事例資料時可完全搜尋評審集中的所有資料。</span><span class="sxs-lookup"><span data-stu-id="08f9b-110">All items (including the content and metadata) are re-indexed so that all data in the review set is fully searchable during the review of the case data.</span></span> <span data-ttu-id="08f9b-111">當您在案例調查期間搜尋檢查集中的資料時, 重新編制資料的索引會產生完整且非常快速的搜尋。</span><span class="sxs-lookup"><span data-stu-id="08f9b-111">Re-indexing the data results in thorough and very fast searches when you search the data in the review set during the case investigation.</span></span>

<span data-ttu-id="08f9b-112">若要將資料新增至審閱集, 請按一下 [**搜尋**] 索引標籤上的 [搜尋], 然後按一下 [**將結果新增至**飛入] 頁面上的 [設定]。</span><span class="sxs-lookup"><span data-stu-id="08f9b-112">To add data to a review set, click a search on the **Searches** tab, and then click **Add results to review set** on the flyout page.</span></span>

![將資料新增至審閱集](../media/c1b4fc00-7a15-4587-b9b0-ce594bb02e4d.png)

<span data-ttu-id="08f9b-114">您可以新增至現有的檢查集, 或建立新的審閱集。</span><span class="sxs-lookup"><span data-stu-id="08f9b-114">You can add to an existing review set or create a new review set.</span></span>  <span data-ttu-id="08f9b-115">如果新增至新的審閱集, 請指定名稱, 然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="08f9b-115">If adding to a new review set, specify the name and then click **Add**.</span></span>

![選取審閱集](../media/e8c6ab51-da8d-4c39-9b21-26bfdf453fb9.png)

<span data-ttu-id="08f9b-117">將資料新增至審閱集是一個長時間執行的程式。</span><span class="sxs-lookup"><span data-stu-id="08f9b-117">Adding data to a review set is a long-running process.</span></span> <span data-ttu-id="08f9b-118">此套裝程式括從 Office 365 的原始資料來源收集項目 (例如, 從信箱和網站), 並將其複製到 Azure 儲存位置 (這個複製程式也稱為*攝取*), 然後重新編制專案的索引。</span><span class="sxs-lookup"><span data-stu-id="08f9b-118">This process includes gathering items from the original data sources in Office 365 (for example, from mailboxes and sites), copying them to the Azure storage location (this copying process is also called *ingestion*), and then re-indexing the items.</span></span> <span data-ttu-id="08f9b-119">您可以在 [**工作**] 索引標籤或 [**搜尋**] 索引標籤上, 監視 [**新增資料至審查集合**] 欄中的狀態。</span><span class="sxs-lookup"><span data-stu-id="08f9b-119">You can track the progress on the **Jobs** tab or on the **Searches** tab by monitoring the status in the **Added data to review set** column.</span></span> <span data-ttu-id="08f9b-120">完成審閱集處理之後, 按一下案例中的 [**檢查集**] 索引標籤, 然後按一下 [檢查集], 以開始篩選、檢查、標記及匯出審閱集中的資料的程式。</span><span class="sxs-lookup"><span data-stu-id="08f9b-120">After the review set processing is completed, click the **Review sets** tab in the case, and click the review set to start the process of filtering, reviewing, tagging, and exporting data in the review set.</span></span>

## <a name="add-a-sample-to-a-review-set"></a><span data-ttu-id="08f9b-121">將範例新增至審閱集</span><span class="sxs-lookup"><span data-stu-id="08f9b-121">Add a sample to a review set</span></span>

<span data-ttu-id="08f9b-122">如果您想要更深入地驗證搜尋的結果, 再將所有專案新增至審閱集, 您可以將搜尋結果的範例新增至審閱集, 而不是新增任何專案。</span><span class="sxs-lookup"><span data-stu-id="08f9b-122">If you want to validate the results of a search more thoroughly before adding all of them to a review set, you can add a sample of the search results to a review set instead of adding everything.</span></span>

<span data-ttu-id="08f9b-123">若要將範例新增至審閱集, 請按一下 [**搜尋**] 索引標籤上的搜尋, 然後按一下飛入頁面上的 [**範例**]。</span><span class="sxs-lookup"><span data-stu-id="08f9b-123">To add a sample to a review set, click a search on the **Searches** tab and click **Sample** on the flyout page.</span></span> <span data-ttu-id="08f9b-124">在 [**抽樣參數**] 頁面上, 選擇下列其中一個選項:</span><span class="sxs-lookup"><span data-stu-id="08f9b-124">On the **Sampling parameters** page, choose one of the following options:</span></span>

- <span data-ttu-id="08f9b-125">**信賴等級%** 和**信賴區間%** –新增至審閱集的專案會由您所設定的統計參數決定。</span><span class="sxs-lookup"><span data-stu-id="08f9b-125">**Confidence level %** and **Confidence interval %** – The items added to the review set will be determined by the statistical parameters that you set.</span></span> <span data-ttu-id="08f9b-126">如果您通常會在採樣結果時使用信賴等級和間隔, 請在下拉式方塊中加以指定。</span><span class="sxs-lookup"><span data-stu-id="08f9b-126">If you typically use a confidence level and interval when sampling results, specify them in the drop-down boxes.</span></span> <span data-ttu-id="08f9b-127">否則, 請使用預設設定。</span><span class="sxs-lookup"><span data-stu-id="08f9b-127">Otherwise, use the default settings.</span></span>

- <span data-ttu-id="08f9b-128">**隨機範例%** –新增至審閱集的專案是根據搜尋傳回的總專案數所指定百分比的隨機選取。</span><span class="sxs-lookup"><span data-stu-id="08f9b-128">**Random sample %** – The items added to the review set is based on a random selection of the specified percentage of the total number of items returned by the search.</span></span>

<span data-ttu-id="08f9b-129">選取並設定其中一個先前的選項之後, 請選擇要將範例新增至其中的 [審閱集], 然後按一下 [**傳送**]。</span><span class="sxs-lookup"><span data-stu-id="08f9b-129">After selecting and configuring one of the previous options, choose a review set to add the sample to and then click **Send**.</span></span> <span data-ttu-id="08f9b-130">同樣地, 您可以透過監控 [**新增資料至審查集合**] 欄中的狀態, 追蹤 [**工作**] 索引標籤或 [**搜尋**] 索引標籤上的進度。</span><span class="sxs-lookup"><span data-stu-id="08f9b-130">Again, you can track the progress on the **Jobs** tab or on the **Searches** tab by monitoring the status in the **Added data to review set** column.</span></span>