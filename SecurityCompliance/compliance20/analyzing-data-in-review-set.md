---
title: 在進階電子文件探索中設定檢閱中分析資料
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
ms.openlocfilehash: cfed07d473f2af367de4cb2e9fe924a29e4123cd
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155205"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="c3abe-102">在進階電子文件探索中設定檢閱中分析資料</span><span class="sxs-lookup"><span data-stu-id="c3abe-102">Analyze data in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="c3abe-103">大型收集文件數目時，它可以是很難全部加以檢閱。</span><span class="sxs-lookup"><span data-stu-id="c3abe-103">When the number of collected documents is large, it can be quite difficult to review them all.</span></span> <span data-ttu-id="c3abe-104">進階電子文件提供數個工具來分析文件，以減少大量的文件沒有任何遺失的資訊，請檢閱，以及協助您組織的文件中以一致的方式。</span><span class="sxs-lookup"><span data-stu-id="c3abe-104">Advanced eDiscovery provides a number of tools to analyze the documents to reduce the volume of documents to be reviewed without any loss in information, and to help you organize the documents in a coherent manner.</span></span> <span data-ttu-id="c3abe-105">若要深入了解這些功能，請參閱：</span><span class="sxs-lookup"><span data-stu-id="c3abe-105">To learn more about these capabilities, see:</span></span>

- [<span data-ttu-id="c3abe-106">近似重複項偵測</span><span class="sxs-lookup"><span data-stu-id="c3abe-106">Near duplicate detection</span></span>](near-duplicates.md)

- [<span data-ttu-id="c3abe-107">電子郵件執行緒</span><span class="sxs-lookup"><span data-stu-id="c3abe-107">Email threading</span></span>](email-threading.md)

- [<span data-ttu-id="c3abe-108">佈景主題</span><span class="sxs-lookup"><span data-stu-id="c3abe-108">Themes</span></span>](themes.md)

<span data-ttu-id="c3abe-109">若要分析檢閱集中的資料：</span><span class="sxs-lookup"><span data-stu-id="c3abe-109">To analyze data in a review set:</span></span>

1. <span data-ttu-id="c3abe-110">設定分析您的案例。</span><span class="sxs-lookup"><span data-stu-id="c3abe-110">Configure analytics settings for your case.</span></span> <span data-ttu-id="c3abe-111">如需詳細資訊，請參閱 < <b0>Configure search 和分析設定</b0>。</span><span class="sxs-lookup"><span data-stu-id="c3abe-111">For more information, see [Configure search and analytics settings](configure-search-analytics-settings.md).</span></span>

2. <span data-ttu-id="c3abe-112">開啟您想要分析檢閱設定。</span><span class="sxs-lookup"><span data-stu-id="c3abe-112">Open the review set you want to analyze.</span></span>

3. <span data-ttu-id="c3abe-113">按一下 [**管理檢視設定**]。</span><span class="sxs-lookup"><span data-stu-id="c3abe-113">Click **Manage review set**.</span></span>

4. <span data-ttu-id="c3abe-114">按一下 [**分析**]。</span><span class="sxs-lookup"><span data-stu-id="c3abe-114">Click **Analyze**.</span></span>

<span data-ttu-id="c3abe-115">您可以檢查 analysis 案例的**工作**] 索引標籤上的進度。</span><span class="sxs-lookup"><span data-stu-id="c3abe-115">You can check the progress of analysis on the **Jobs** tab of the case.</span></span>

 <span data-ttu-id="c3abe-116">分析完成之後，您可以檢視分析報表中，執行查詢中分析的輸出上您檢閱設定 （請參閱[設定內檢閱查詢](review-set-search.md)），並查看相關的文件的指定的文件 （請參閱[檢閱資料中的檢閱設定](reviewing-data-in-review-set.md)）。</span><span class="sxs-lookup"><span data-stu-id="c3abe-116">After analysis is completed, you can view analytics report, run queries within your review set on outputs of the analysis (see [Query within your review set](review-set-search.md)), and see related documents of a given document (see [Reviewing data in review set](reviewing-data-in-review-set.md)).</span></span>

## <a name="analytics-report"></a><span data-ttu-id="c3abe-117">分析報告</span><span class="sxs-lookup"><span data-stu-id="c3abe-117">Analytics report</span></span>

<span data-ttu-id="c3abe-118">若要檢視檢閱設定分析報告：</span><span class="sxs-lookup"><span data-stu-id="c3abe-118">To view a analytics report for a review set:</span></span>

1. <span data-ttu-id="c3abe-119">開啟 [檢閱設定]。</span><span class="sxs-lookup"><span data-stu-id="c3abe-119">Open the review set.</span></span>

2. <span data-ttu-id="c3abe-120">按一下 [**管理檢視設定**]。</span><span class="sxs-lookup"><span data-stu-id="c3abe-120">Click **Manage review set**.</span></span>

3. <span data-ttu-id="c3abe-121">按一下 [**報告**]。</span><span class="sxs-lookup"><span data-stu-id="c3abe-121">Click **Report**.</span></span>

<span data-ttu-id="c3abe-122">報表中包含從分析的四個元件：</span><span class="sxs-lookup"><span data-stu-id="c3abe-122">The report has four components from analysis:</span></span>

- <span data-ttu-id="c3abe-123">檢閱集合中找不到**分解**-多少電子郵件訊息、 附件及寬鬆的文件。</span><span class="sxs-lookup"><span data-stu-id="c3abe-123">**Breakdown** - How many email messages, attachments, and loose documents were found in the review set.</span></span>

- <span data-ttu-id="c3abe-124">**文件 （不含附件）** -多少寬鬆的文件已樞紐分析表，唯一接近重複的樞紐分析表或完全重複的另一個文件。</span><span class="sxs-lookup"><span data-stu-id="c3abe-124">**Documents (excluding attachments)** - How many loose documents were pivots, unique near duplicates of a pivot, or an exact duplicate of another document.</span></span>

- <span data-ttu-id="c3abe-125">**電子郵件**-多少電子郵件訊息所 inclusives、 內含的副本，內含 minuses，或無以上。</span><span class="sxs-lookup"><span data-stu-id="c3abe-125">**Emails** - How many email messages were inclusives, inclusive copies, inclusive minuses, or none of the above.</span></span>

- <span data-ttu-id="c3abe-126">**附件**-多少電子郵件附件是唯一或重複的另一個電子郵件附件中檢閱設定。</span><span class="sxs-lookup"><span data-stu-id="c3abe-126">**Attachments** - How many email attachments were unique or duplicates of a another email attachment in the review set.</span></span>