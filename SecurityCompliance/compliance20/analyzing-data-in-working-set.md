---
title: 分析進階 eDiscovery (Preview) 中使用集中的資料
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: e3f3e863423fe4312a944eb6f04a58182e11665c
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295476"
---
# <a name="analyze-data-in-a-working-set-in-advanced-ediscovery-preview"></a><span data-ttu-id="489b7-102">分析進階 eDiscovery (Preview) 中使用集中的資料</span><span class="sxs-lookup"><span data-stu-id="489b7-102">Analyze data in a working set in Advanced eDiscovery (Preview)</span></span>

<span data-ttu-id="489b7-p101">大型收集文件數目時，它可以是很難將所有加以檢閱。進階的 eDiscovery （預覽） 提供工具來分析來降低文件檢閱沒有任何遺失的資訊，並協助您組織的文件一致的方式數量的文件的數。若要深入了解這些功能，請參閱：</span><span class="sxs-lookup"><span data-stu-id="489b7-p101">When the number of collected documents is large, it can be quite difficult to review them all. Advanced eDiscovery (Preview) provides a number of tools to analyze the documents to reduce the volume of documents to be reviewed without any loss in information, and to help you organize the documents in a coherent manner. To learn more about these capabilities, see:</span></span>

- [<span data-ttu-id="489b7-106">近似重複項偵測</span><span class="sxs-lookup"><span data-stu-id="489b7-106">Near duplicate detection</span></span>](near-duplicates.md)
- [<span data-ttu-id="489b7-107">電子郵件威脅</span><span class="sxs-lookup"><span data-stu-id="489b7-107">Email threading</span></span>](email-threading.md)
- [<span data-ttu-id="489b7-108">佈景主題</span><span class="sxs-lookup"><span data-stu-id="489b7-108">Themes</span></span>](themes.md)

<span data-ttu-id="489b7-109">若要分析使用集中的資料：</span><span class="sxs-lookup"><span data-stu-id="489b7-109">To analyze data in a working set:</span></span>

1. <span data-ttu-id="489b7-p102">設定分析您的案例。如需詳細資訊，請參閱 ＜ [Configure search 及分析設定](configure-search-analytics-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="489b7-p102">Configure analytics settings for your case. For more information, see [Configure search and analytics settings](configure-search-analytics-settings.md).</span></span>
2. <span data-ttu-id="489b7-112">開啟您想要分析的工作集。</span><span class="sxs-lookup"><span data-stu-id="489b7-112">Open the working set you wish to analyze.</span></span>
3. <span data-ttu-id="489b7-113">移至 「 管理工作集 」。</span><span class="sxs-lookup"><span data-stu-id="489b7-113">Go to "Manage working set".</span></span>
4. <span data-ttu-id="489b7-114">按一下 ["分析"。</span><span class="sxs-lookup"><span data-stu-id="489b7-114">Click "Analyze".</span></span>

<span data-ttu-id="489b7-115">您可以在您的案例中檢查 [工作] 索引標籤中的分析的進度。</span><span class="sxs-lookup"><span data-stu-id="489b7-115">You can check the progress of analysis in the Jobs tab in your case.</span></span>

 <span data-ttu-id="489b7-116">分析完成之後，您可以檢視分析報表、 您使用內執行的查詢設定 （如需詳細資訊，請參閱[設定您的使用中查詢](working-set-search.md)） 分析的輸出並查看指定的文件 （如需詳細資訊，請參閱[相關的文件檢閱使用集中的資料](reviewing-data-in-working-set.md))。</span><span class="sxs-lookup"><span data-stu-id="489b7-116">Once analysis is completed, you can view analytics report, run queries within your working set on outputs of the analysis (for more information see [Query within your working set](working-set-search.md)), and see related documents of a given document (for more information see [Reviewing data in working set](reviewing-data-in-working-set.md)).</span></span>

## <a name="analytics-report"></a><span data-ttu-id="489b7-117">分析報告</span><span class="sxs-lookup"><span data-stu-id="489b7-117">Analytics report</span></span>

<span data-ttu-id="489b7-118">若要檢視您的工作集分析報告：</span><span class="sxs-lookup"><span data-stu-id="489b7-118">To view a analytics report for your working set:</span></span>

1. <span data-ttu-id="489b7-119">開啟工作設定。</span><span class="sxs-lookup"><span data-stu-id="489b7-119">Open your working set.</span></span>
2. <span data-ttu-id="489b7-120">移至 「 管理工作集 」。</span><span class="sxs-lookup"><span data-stu-id="489b7-120">Go to "Manage working set".</span></span>
3. <span data-ttu-id="489b7-121">按一下 ["Report"。</span><span class="sxs-lookup"><span data-stu-id="489b7-121">Click "Report".</span></span>

<span data-ttu-id="489b7-122">報表有四種分析元件：</span><span class="sxs-lookup"><span data-stu-id="489b7-122">The report has four components from analysis:</span></span>

- <span data-ttu-id="489b7-123">使用組中找不到**分解**-多少電子郵件、 附件及寬鬆的文件。</span><span class="sxs-lookup"><span data-stu-id="489b7-123">**Breakdown** - How many emails, attachments, and loose documents were found in the working set.</span></span>

- <span data-ttu-id="489b7-124">**文件 （不含附件）** -多少寬鬆的文件已樞紐分析表、 唯一接近重複項目之樞紐分析表或另一個文件完全重複。</span><span class="sxs-lookup"><span data-stu-id="489b7-124">**Documents (excluding attachments)** - How many loose documents were pivots, unique near duplicates of a pivot, or an exact duplicate of another document.</span></span>

- <span data-ttu-id="489b7-125">**電子郵件**-多少電子郵件已 inclusives、 （含） 的複本、 （含) minuses，或上述任一個項目。</span><span class="sxs-lookup"><span data-stu-id="489b7-125">**Emails** - How many emails were inclusives, inclusive copies, inclusive minuses, or none of the above.</span></span>

- <span data-ttu-id="489b7-126">**附件**-多少電子郵件附件中被唯一或重複內使用不同的電子郵件附件的設定。</span><span class="sxs-lookup"><span data-stu-id="489b7-126">**Attachments** - How many email attachments were unique or duplicates of a different email attachment within the working set.</span></span>