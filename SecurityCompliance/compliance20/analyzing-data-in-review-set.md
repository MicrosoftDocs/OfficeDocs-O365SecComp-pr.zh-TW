---
title: 在高級 eDiscovery 中分析審閱集中的資料
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
ms.openlocfilehash: b331bba76f45a11a4d1c8c0552b27759cf49608a
ms.sourcegitcommit: e323610df2df71c84f536e8a38650d33d8069e41
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2019
ms.locfileid: "34703806"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="2f110-102">在高級 eDiscovery 中分析審閱集中的資料</span><span class="sxs-lookup"><span data-stu-id="2f110-102">Analyze data in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="2f110-103">當收集的檔數很大時, 很難完全查看。</span><span class="sxs-lookup"><span data-stu-id="2f110-103">When the number of collected documents is large, it can be quite difficult to review them all.</span></span> <span data-ttu-id="2f110-104">Advanced eDiscovery 提供許多工具來分析檔, 以減少不遺失資訊的檔數量, 並協助您以一致的方式組織檔。</span><span class="sxs-lookup"><span data-stu-id="2f110-104">Advanced eDiscovery provides a number of tools to analyze the documents to reduce the volume of documents to be reviewed without any loss in information, and to help you organize the documents in a coherent manner.</span></span> <span data-ttu-id="2f110-105">若要深入瞭解這些功能, 請參閱:</span><span class="sxs-lookup"><span data-stu-id="2f110-105">To learn more about these capabilities, see:</span></span>

- [<span data-ttu-id="2f110-106">近似重複項偵測</span><span class="sxs-lookup"><span data-stu-id="2f110-106">Near duplicate detection</span></span>](near-duplicates.md)

- [<span data-ttu-id="2f110-107">電子郵件執行緒</span><span class="sxs-lookup"><span data-stu-id="2f110-107">Email threading</span></span>](email-threading.md)

- [<span data-ttu-id="2f110-108">佈景主題</span><span class="sxs-lookup"><span data-stu-id="2f110-108">Themes</span></span>](themes.md)

<span data-ttu-id="2f110-109">若要分析審閱集中的資料:</span><span class="sxs-lookup"><span data-stu-id="2f110-109">To analyze data in a review set:</span></span>

1. <span data-ttu-id="2f110-110">設定您案例的分析設定。</span><span class="sxs-lookup"><span data-stu-id="2f110-110">Configure analytics settings for your case.</span></span> <span data-ttu-id="2f110-111">如需詳細資訊, 請參閱[設定搜尋和分析設定](configure-search-analytics-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="2f110-111">For more information, see [Configure search and analytics settings](configure-search-analytics-settings.md).</span></span>

2. <span data-ttu-id="2f110-112">開啟您要分析的檢查集。</span><span class="sxs-lookup"><span data-stu-id="2f110-112">Open the review set you want to analyze.</span></span>

3. <span data-ttu-id="2f110-113">按一下 [**管理審閱集**]。</span><span class="sxs-lookup"><span data-stu-id="2f110-113">Click **Manage review set**.</span></span>

4. <span data-ttu-id="2f110-114">**針對 [審閱集**] 按一下 [執行分析]。</span><span class="sxs-lookup"><span data-stu-id="2f110-114">Click **Run analytics for the review set**.</span></span>

<span data-ttu-id="2f110-115">您可以在案例的 [**工作**] 索引標籤上檢查分析進度。</span><span class="sxs-lookup"><span data-stu-id="2f110-115">You can check the progress of analysis on the **Jobs** tab of the case.</span></span>

 <span data-ttu-id="2f110-116">分析完成之後, 您可以查看分析報告、在分析輸出的檢查集內執行查詢 (請參閱您的[審閱集中的查詢](review-set-search.md)), 並查看指定檔的相關檔 (請參閱檢查[審閱集中的資料](reviewing-data-in-review-set.md))。</span><span class="sxs-lookup"><span data-stu-id="2f110-116">After analysis is completed, you can view analytics report, run queries within your review set on outputs of the analysis (see [Query within your review set](review-set-search.md)), and see related documents of a given document (see [Reviewing data in review set](reviewing-data-in-review-set.md)).</span></span>

## <a name="analytics-report"></a><span data-ttu-id="2f110-117">分析報告</span><span class="sxs-lookup"><span data-stu-id="2f110-117">Analytics report</span></span>

<span data-ttu-id="2f110-118">若要查看審查集的分析報告:</span><span class="sxs-lookup"><span data-stu-id="2f110-118">To view an analytics report for a review set:</span></span>

1. <span data-ttu-id="2f110-119">開啟 [檢查集]。</span><span class="sxs-lookup"><span data-stu-id="2f110-119">Open the review set.</span></span>

2. <span data-ttu-id="2f110-120">按一下 [**管理審閱集**]。</span><span class="sxs-lookup"><span data-stu-id="2f110-120">Click **Manage review set**.</span></span>

3. <span data-ttu-id="2f110-121">按一下 [**查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="2f110-121">Click **View report**.</span></span>

<span data-ttu-id="2f110-122">報告中有四個元件可供分析:</span><span class="sxs-lookup"><span data-stu-id="2f110-122">The report has four components from analysis:</span></span>

- <span data-ttu-id="2f110-123">**細目**-在審閱集中找到的電子郵件、附件和鬆散檔數目。</span><span class="sxs-lookup"><span data-stu-id="2f110-123">**Breakdown** - How many email messages, attachments, and loose documents were found in the review set.</span></span>

- <span data-ttu-id="2f110-124">**檔 (不包括附件)** -大量的鬆散檔、樞紐分析表的重復資料, 或是其他檔的完全相同的複本。</span><span class="sxs-lookup"><span data-stu-id="2f110-124">**Documents (excluding attachments)** - How many loose documents were pivots, unique near duplicates of a pivot, or an exact duplicate of another document.</span></span>

- <span data-ttu-id="2f110-125">**電子**郵件-inclusives 的電子郵件數目、包含的副本、包含的 minuses, 或上述都不是。</span><span class="sxs-lookup"><span data-stu-id="2f110-125">**Emails** - How many email messages were inclusives, inclusive copies, inclusive minuses, or none of the above.</span></span>

- <span data-ttu-id="2f110-126">**附件**-審閱集中其他電子郵件附件的電子郵件附件數目是唯一或重複的。</span><span class="sxs-lookup"><span data-stu-id="2f110-126">**Attachments** - How many email attachments were unique or duplicates of a another email attachment in the review set.</span></span>