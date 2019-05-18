---
title: 執行分析以更快速地調查
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
ms.openlocfilehash: 7462b415c2e5b0a66c08bb9b5abb647f366e9785
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153655"
---
# <a name="run-analytics-to-investigate-faster"></a><span data-ttu-id="f1e43-102">執行分析以更快速地調查</span><span class="sxs-lookup"><span data-stu-id="f1e43-102">Run analytics to investigate faster</span></span>

<span data-ttu-id="f1e43-103">大型辨識項集合時，它可能很難全部加以檢閱。</span><span class="sxs-lookup"><span data-stu-id="f1e43-103">When an evidence collection is large, it can be difficult to review them all.</span></span> <span data-ttu-id="f1e43-104">一群證據通常包含相同或類似的電子郵件或文件的多個副本。</span><span class="sxs-lookup"><span data-stu-id="f1e43-104">A set of evidence often includes multiple copies of the same or similar email messages or documents.</span></span> <span data-ttu-id="f1e43-105">資料調查 （預覽） 提供了數分析工具，可協助您降低需要檢閱沒有任何遺失的資訊中的文件數量。</span><span class="sxs-lookup"><span data-stu-id="f1e43-105">Data Investigations (Preview) provides a number of analytics tools that can help you reduce the volume of documents that need to be reviewed without any loss in information.</span></span> <span data-ttu-id="f1e43-106">若要深入了解這些功能，請參閱：</span><span class="sxs-lookup"><span data-stu-id="f1e43-106">To learn more about these capabilities, see:</span></span>

- [<span data-ttu-id="f1e43-107">近似重複項偵測</span><span class="sxs-lookup"><span data-stu-id="f1e43-107">Near duplicate detection</span></span>](near-duplicates.md)

- [<span data-ttu-id="f1e43-108">電子郵件執行緒</span><span class="sxs-lookup"><span data-stu-id="f1e43-108">Email threading</span></span>](email-threading.md)

- [<span data-ttu-id="f1e43-109">佈景主題</span><span class="sxs-lookup"><span data-stu-id="f1e43-109">Themes</span></span>](themes.md)

<span data-ttu-id="f1e43-110">若要分析辨識項集合中的資料：</span><span class="sxs-lookup"><span data-stu-id="f1e43-110">To analyze data in an evidence set:</span></span>

1. <span data-ttu-id="f1e43-111">設定您調查分析。</span><span class="sxs-lookup"><span data-stu-id="f1e43-111">Configure the analytics settings for your investigation.</span></span> <span data-ttu-id="f1e43-112">如需詳細資訊，請參閱 < <b0>Configure search 和分析設定</b0>。</span><span class="sxs-lookup"><span data-stu-id="f1e43-112">For more information, see [Configure search and analytics settings](configure-search-analytics-settings.md).</span></span>

2. <span data-ttu-id="f1e43-113">開啟辨識項集合。</span><span class="sxs-lookup"><span data-stu-id="f1e43-113">Open the evidence set.</span></span>

3. <span data-ttu-id="f1e43-114">按一下 [**管理證據**。</span><span class="sxs-lookup"><span data-stu-id="f1e43-114">Click **Manage evidence**.</span></span>

4. <span data-ttu-id="f1e43-115">[**分析**，按一下 [**分析]**。</span><span class="sxs-lookup"><span data-stu-id="f1e43-115">Under **Analytics**, click **Analyze**.</span></span>

<span data-ttu-id="f1e43-116">您可以在您調查檢查分析**工作**] 索引標籤上的進度。</span><span class="sxs-lookup"><span data-stu-id="f1e43-116">You can check the progress of analysis on the **Jobs** tab in your investigation.</span></span> <span data-ttu-id="f1e43-117">觸發工作類型是名為**執行分析**。</span><span class="sxs-lookup"><span data-stu-id="f1e43-117">The job type that's triggered is named **Running analytics**.</span></span>

 <span data-ttu-id="f1e43-118">分析完成之後，您可以查看完全重複或近似重複項目在檢閱文件位於右側的 [資訊] 面板。</span><span class="sxs-lookup"><span data-stu-id="f1e43-118">After analysis is completed, you can see a list of exact duplicates or near-duplicates of the document that you're reviewing located in the panel on the right.</span></span> <span data-ttu-id="f1e43-119">若要選取您要檢視文件的所有重複項目，您可以輕鬆地執行使用此面板。</span><span class="sxs-lookup"><span data-stu-id="f1e43-119">To select all duplicates of the document you're viewing, you can easily do so using this panel.</span></span> <span data-ttu-id="f1e43-120">若要深入了解此面板上的其他功能，請參閱 <<c0>在辨識項的檢閱資料。</span><span class="sxs-lookup"><span data-stu-id="f1e43-120">To learn more about other features on this panel, see [Review data in evidence](review-data-in-evidence.md).</span></span> 

<span data-ttu-id="f1e43-121">您也可以執行額外的查詢中使用的佈景主題例如分析輸出您證據。</span><span class="sxs-lookup"><span data-stu-id="f1e43-121">You can also run additional queries within your evidence using the outputs of the analysis such as themes.</span></span> <span data-ttu-id="f1e43-122">如需詳細資訊，請參閱 <<c0>查詢中的辨識項的資料。</span><span class="sxs-lookup"><span data-stu-id="f1e43-122">For more information, see [Query the data in evidence](evidence-query.md).</span></span>

## <a name="analytics-report"></a><span data-ttu-id="f1e43-123">分析報告</span><span class="sxs-lookup"><span data-stu-id="f1e43-123">Analytics report</span></span>

<span data-ttu-id="f1e43-124">若要檢視您的辨識項分析報告：</span><span class="sxs-lookup"><span data-stu-id="f1e43-124">To view an analytics report for your evidence:</span></span>

1. <span data-ttu-id="f1e43-125">開啟辨識項集合。</span><span class="sxs-lookup"><span data-stu-id="f1e43-125">Open the evidence set.</span></span>

2. <span data-ttu-id="f1e43-126">按一下 [**管理證據**。</span><span class="sxs-lookup"><span data-stu-id="f1e43-126">Click **Manage evidence**.</span></span>

3. <span data-ttu-id="f1e43-127">[**分析**，按一下 [**檢視報告**。</span><span class="sxs-lookup"><span data-stu-id="f1e43-127">Under **Analytics**, click **View report**.</span></span>

<span data-ttu-id="f1e43-128">報表中包含從分析的四個元件：</span><span class="sxs-lookup"><span data-stu-id="f1e43-128">The report has four components from analysis:</span></span>

- <span data-ttu-id="f1e43-129">**分解**-的未經處理的電子郵件、 附件，並找到辨識項集合中的文件數。</span><span class="sxs-lookup"><span data-stu-id="f1e43-129">**Breakdown** - The number of raw emails, attachments, and documents found in the evidence set.</span></span>

- <span data-ttu-id="f1e43-130">**電子郵件**-eamil inclusives、 內含 minuses、 內含的副本，或沒有任何一個以上的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="f1e43-130">**Emails** - The number of eamil messages that are inclusives, inclusive minuses, inclusive copies, or none of the above.</span></span>
   - <span data-ttu-id="f1e43-131">Inclusives： 最後一封電子郵件執行緒，包含所有舊的歷程記錄，而且需要檢閱中。</span><span class="sxs-lookup"><span data-stu-id="f1e43-131">Inclusives: The last message in the email thread that contains all previous history and requires review.</span></span>
   - <span data-ttu-id="f1e43-132">內含 minuses： 需要檢閱的訊息中的執行緒，其中包含一或多不同的附件。</span><span class="sxs-lookup"><span data-stu-id="f1e43-132">Inclusive minuses: The message in the thread that contains one or more different attachments that requires review.</span></span>
   - <span data-ttu-id="f1e43-133">內含的副本： 是另一個 （含） 或減號 （主旨和內文） 的訊息內含的複本的訊息。</span><span class="sxs-lookup"><span data-stu-id="f1e43-133">Inclusive copies: The message that is a copy of another inclusive or inclusive minus message (subject and body).</span></span>

- <span data-ttu-id="f1e43-134">**附件**-都是唯一的電子郵件附件數] 或 [重複項目中相同的不同的電子郵件附件的證據相同。</span><span class="sxs-lookup"><span data-stu-id="f1e43-134">**Attachments** - The number of email attachments that are unique or duplicates of a different email attachment within the same evidence same.</span></span>

- <span data-ttu-id="f1e43-135">**文件 （不含電子郵件附件）** -唯一需要檢閱，例如近似重複組最代表性文件或完全重複的另一個文件的文件數目）。</span><span class="sxs-lookup"><span data-stu-id="f1e43-135">**Documents (excluding email attachments)** - The number of unique documents that require review, for example, the most representative document of the near-duplicate set or an exact duplicate of another document).</span></span>