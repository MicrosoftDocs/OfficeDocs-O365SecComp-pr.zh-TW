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
ms.openlocfilehash: 4de390972672509422e055cd3fd6a9f65d54a7ba
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155235"
---
# <a name="add-search-results-to-a-review-set"></a><span data-ttu-id="5cb12-102">將搜尋結果新增至檢閱集</span><span class="sxs-lookup"><span data-stu-id="5cb12-102">Add search results to a review set</span></span>

<span data-ttu-id="5cb12-103">當您滿意的搜尋結果，且您準備好要檢閱和分析搜尋結果時，您可以將其新增到的情況下設定檢閱。</span><span class="sxs-lookup"><span data-stu-id="5cb12-103">When you're satisfied with the results of a search and you're ready to review and analyze those search results, you can add them to a review set in the case.</span></span> <span data-ttu-id="5cb12-104">複製原始資料至檢閱設定也有助於檢閱和分析處理程序藉由提供進階的分析工具，例如佈景主題偵測近似重複偵測，和電子郵件執行緒識別碼。</span><span class="sxs-lookup"><span data-stu-id="5cb12-104">Copying the original data to the review set also facilitates the review and analysis process by providing you with advanced analytics tools such as themes detection, near-duplicate detection, and email thread identification.</span></span> <span data-ttu-id="5cb12-105">您也可以新增非 Office 365 資料來源的資料，以檢閱設定，以便您可以檢閱該資料，除了您從 Office 365 收集的資料。</span><span class="sxs-lookup"><span data-stu-id="5cb12-105">You can also add data from non-Office 365 data sources to a review set so that you can review that data in addition to the data you collect from Office 365.</span></span>

<span data-ttu-id="5cb12-106">當您將搜尋結果新增至檢閱設定 （請檢閱設定位於 [**檢閱設定**] 索引標籤的大小寫） 時，會發生下列兩件事：</span><span class="sxs-lookup"><span data-stu-id="5cb12-106">When you add the results of a search to a review set (review sets are located on the **Review sets** tab of the case), the following two things occur:</span></span>

- <span data-ttu-id="5cb12-107">在搜尋結果中的所有項目會複製從原始資料來源中的即時的 Office 365 服務，並複製到 Microsoft cloud 中的安全的 Azure 儲存體位置。</span><span class="sxs-lookup"><span data-stu-id="5cb12-107">All items in the search results are copied from the original data source in the live Office 365 services, and copied to a secure Azure storage location in the Microsoft cloud.</span></span>

- <span data-ttu-id="5cb12-108">（包括的內容和中繼資料） 的所有項目重新編製索引，以便檢閱中的所有資料都設定時，會完整搜尋案例資料的檢閱。</span><span class="sxs-lookup"><span data-stu-id="5cb12-108">All items (including the content and metadata) are re-indexed so that all data in the review set is fully searchable during the review of the case data.</span></span> <span data-ttu-id="5cb12-109">重新索引徹底和非常快速搜尋中的資料結果，當您在檢閱搜尋資料設定期間案例的調查。</span><span class="sxs-lookup"><span data-stu-id="5cb12-109">Re-indexing the data results in thorough and very fast searches when you search the data in the review set during the case investigation.</span></span>

<span data-ttu-id="5cb12-110">若要將資料新增至檢閱設定，按一下 [**搜尋**] 索引標籤上的搜尋，然後按一下**檢閱組新增結果**在彈出式頁面上。</span><span class="sxs-lookup"><span data-stu-id="5cb12-110">To add data to a review set, click a search on the **Searches** tab and then click **Add results to review set** on the flyout page.</span></span>

![將資料新增到檢閱設定](../media/c1b4fc00-7a15-4587-b9b0-ce594bb02e4d.png)

<span data-ttu-id="5cb12-112">請注意，您可以新增至現有檢閱設定，或建立新的檢閱集合。</span><span class="sxs-lookup"><span data-stu-id="5cb12-112">Note that you can add to an existing review set or create a new review set.</span></span>  <span data-ttu-id="5cb12-113">如果新增至新的檢閱設定，指定名稱，然後按一下 [**新增]**。</span><span class="sxs-lookup"><span data-stu-id="5cb12-113">If adding to a new review set, specify the name and then click **Add**.</span></span>

![選取 [檢閱設定](../media/e8c6ab51-da8d-4c39-9b21-26bfdf453fb9.png)

<span data-ttu-id="5cb12-115">將資料新增到檢閱設定是長時間執行程序。</span><span class="sxs-lookup"><span data-stu-id="5cb12-115">Adding data to a review set is a long-running process.</span></span> <span data-ttu-id="5cb12-116">此程序包含從原始資料來源 （例如，從信箱和站台） 的 Office 365 中收集項目，複製至 Azure 儲存體的位置 （此複製程序也稱為*擷取*），然後重新編製索引的項目。</span><span class="sxs-lookup"><span data-stu-id="5cb12-116">This process includes gathering items from the original data sources in Office 365 (for example, from mailboxes and sites), copying them to the Azure storage location (this copying process is also called *ingestion*), and then re-indexing the items.</span></span> <span data-ttu-id="5cb12-117">您可以藉由監視**檢閱設定新增資料**行中的狀態，在 [**工作**] 索引標籤上，或在 [**搜尋**] 索引標籤上追蹤進度。</span><span class="sxs-lookup"><span data-stu-id="5cb12-117">You can track the progress on the **Jobs** tab or on the **Searches** tab by monitoring the status in the **Added data to review set** column.</span></span> <span data-ttu-id="5cb12-118">檢閱設定處理完成後，按一下 [**檢閱設定**] 索引標籤的情況，，，然後按一下 [檢閱設定開始程序進行篩選，檢閱，標記，並匯出檢閱集中的資料。</span><span class="sxs-lookup"><span data-stu-id="5cb12-118">After the review set processing is completed, click the **Review sets** tab in the case, and then click the review set to start the process filtering, reviewing, tagging, and exporting data in the review set.</span></span>

## <a name="add-a-sample-to-a-review-set"></a><span data-ttu-id="5cb12-119">檢閱組新增範例</span><span class="sxs-lookup"><span data-stu-id="5cb12-119">Add a sample to a review set</span></span>

<span data-ttu-id="5cb12-120">如果您想要驗證的更完整之前將它們新增至檢閱搜尋結果，您可以設定而不是新增每個項目檢閱新增的搜尋結果的範例。</span><span class="sxs-lookup"><span data-stu-id="5cb12-120">If you want to validate the results of a search more thoroughly before adding all of them to a review set, you can add a sample of the search results to a review set instead of adding everything.</span></span>

<span data-ttu-id="5cb12-121">若要檢閱組新增範例，請按一下 [**搜尋**] 索引標籤上的搜尋，並按一下彈出式頁面上的**範例**。</span><span class="sxs-lookup"><span data-stu-id="5cb12-121">To add a sample to a review set, click a search on the **Searches** tab and click **Sample** on the flyout page.</span></span> <span data-ttu-id="5cb12-122">在 [**取樣參數**] 頁面上，選擇下列選項之一：</span><span class="sxs-lookup"><span data-stu-id="5cb12-122">On the **Sampling parameters** page, choose one of the following options:</span></span>

- <span data-ttu-id="5cb12-123">**信賴等級 %** 和**信賴區間 %** 加入檢閱設定的項目都取決於您設定的統計參數。</span><span class="sxs-lookup"><span data-stu-id="5cb12-123">**Confidence level %** and **Confidence interval %** - The items added to the review set will be determined by the statistical parameters that you set.</span></span> <span data-ttu-id="5cb12-124">如果您通常信賴等級及間隔時使用取樣結果，請將它們指定下拉式方塊中。</span><span class="sxs-lookup"><span data-stu-id="5cb12-124">If you typically use a confidence level and interval when sampling results, specify them in the drop-down boxes.</span></span> <span data-ttu-id="5cb12-125">否則，僅使用預設設定。</span><span class="sxs-lookup"><span data-stu-id="5cb12-125">Otherwise, just use the default settings.</span></span>

- <span data-ttu-id="5cb12-126">**隨機範例 %** 加入檢閱設定的項目根據指定的搜尋所傳回的項目總數的百分比的隨機選取範圍。</span><span class="sxs-lookup"><span data-stu-id="5cb12-126">**Random sample %** - The items added to the review set is based on a random selection of the specified percentage of the total number of items returned by the search.</span></span>

<span data-ttu-id="5cb12-127">之後選取，然後設定下列其中一個先前的選項，選擇 [現有檢閱集新增至範例，然後按一下 [**傳送**]。</span><span class="sxs-lookup"><span data-stu-id="5cb12-127">After selecting and configuring one of the previous options, choose an existing review set to add the sample to and then click **Send**.</span></span> <span data-ttu-id="5cb12-128">同樣地，您可以追蹤進度在 [**工作**] 索引標籤上，或在 [**搜尋**] 索引標籤上藉由監視**檢閱設定新增資料**行中的狀態。</span><span class="sxs-lookup"><span data-stu-id="5cb12-128">Again, you can track the progress on the **Jobs** tab or on the **Searches** tab by monitoring the status in the **Added data to review set** column.</span></span>