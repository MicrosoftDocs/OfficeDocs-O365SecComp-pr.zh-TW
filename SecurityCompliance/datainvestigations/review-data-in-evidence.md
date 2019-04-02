---
title: 辨識項的檢閱資料
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
ms.openlocfilehash: 279d2117a69e889f9e605e0ab211c03c5842a59d
ms.sourcegitcommit: 2c5834235c32b2616e1813ce24eeb3419a09629f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2019
ms.locfileid: "31029996"
---
# <a name="review-data-in-evidence"></a><span data-ttu-id="b54c2-102">辨識項的檢閱資料</span><span class="sxs-lookup"><span data-stu-id="b54c2-102">Review data in evidence</span></span>

<span data-ttu-id="b54c2-103">**辨識項**是您收集到的搜尋結果的快照。</span><span class="sxs-lookup"><span data-stu-id="b54c2-103">**Evidence** is a snapshot of search results that you collected.</span></span> <span data-ttu-id="b54c2-104">當您新增搜尋結果的辨識項時，以解壓縮檔案、 中繼資料，以及文字觸發程序。</span><span class="sxs-lookup"><span data-stu-id="b54c2-104">When you add search results to evidence, a process is triggered to extract files, metadata, and text.</span></span> <span data-ttu-id="b54c2-105">然後，系統會建立新索引的所有資料，並將加入**證據**。</span><span class="sxs-lookup"><span data-stu-id="b54c2-105">Then, the system builds a new index of all the data and adds to **Evidence**.</span></span> 

<span data-ttu-id="b54c2-106">針對任何時效性的事件，這可讓您快速地包含環境時調查隔離環境中的重新建立辨識項，刪除原始位置的資料。</span><span class="sxs-lookup"><span data-stu-id="b54c2-106">For any time-sensitive incidents, this allows you to quickly contain the environment by deleting data at original locations while investigating re-created evidence in a quarantined environment.</span></span> <span data-ttu-id="b54c2-107">一旦收集證據，您可以檢閱其原生格式、 文字格式或附近原生格式中的個別文件。</span><span class="sxs-lookup"><span data-stu-id="b54c2-107">Once evidence is collected, you can review individual documents in their native format, text format, or a near-native format.</span></span> <span data-ttu-id="b54c2-108">此外，您可以執行查詢，以縮小時間範圍、 檔案類型、 資料擁有者及許多其他條件介面卡的資料。</span><span class="sxs-lookup"><span data-stu-id="b54c2-108">Additionally, you can run queries to narrow the data by time range, file types, data owners, and many other condition cards.</span></span> <span data-ttu-id="b54c2-109">使用作者/寄件者/收件者條件卡，您可以快速檢視屬於參與不要大和如果有任何外部共用。</span><span class="sxs-lookup"><span data-stu-id="b54c2-109">Using Author/Sender/Recipient condition cards, you can quickly examine who are involved in the spill and if there have been any external shares.</span></span> <span data-ttu-id="b54c2-110">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="b54c2-110">For more information, see:</span></span>

  - [<span data-ttu-id="b54c2-111">查詢中的辨識項的資料</span><span class="sxs-lookup"><span data-stu-id="b54c2-111">Query the data in evidence</span></span>](evidence-query.md)

<span data-ttu-id="b54c2-112">群組文件，並取得更多協助您檢閱，按一下 [**管理辨識項**]。</span><span class="sxs-lookup"><span data-stu-id="b54c2-112">To group documents and get more assistance for your review, click **Manage evidence**.</span></span> <span data-ttu-id="b54c2-113">在 [**分析**] 磚中，按一下 [**分析**]。</span><span class="sxs-lookup"><span data-stu-id="b54c2-113">In the **Analytics** tile, click **Analyze**.</span></span> <span data-ttu-id="b54c2-114">這將會執行進階的分析，例如重複資料偵測、 電子郵件執行緒，以及佈景主題分析。</span><span class="sxs-lookup"><span data-stu-id="b54c2-114">This will run advanced analytics such as duplicate detection, email threading, and theme analysis.</span></span> <span data-ttu-id="b54c2-115">之後，您可以看到一般的佈景主題的資料，並由電子郵件執行緒，完全重複和近似重複項目來協助您調查也組織文件。</span><span class="sxs-lookup"><span data-stu-id="b54c2-115">Afterwards, you can see the general themes of the data and also organize documents by email threads, exact duplicates and near duplicates to facilitate your investigation.</span></span> <span data-ttu-id="b54c2-116">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="b54c2-116">For more information, see:</span></span>

  - [<span data-ttu-id="b54c2-117">執行更快速地調查的分析</span><span class="sxs-lookup"><span data-stu-id="b54c2-117">Run analytics to investigate faster</span></span>](run-analytics-to-investigate-faster.md)

## <a name="view-documents-in-evidence"></a><span data-ttu-id="b54c2-118">檢視文件中的辨識項</span><span class="sxs-lookup"><span data-stu-id="b54c2-118">View documents in evidence</span></span>

<span data-ttu-id="b54c2-119">資料調查 （預覽） 會顯示透過數個檢視每個具有不同用途的內容。</span><span class="sxs-lookup"><span data-stu-id="b54c2-119">Data investigation (Preview) displays content via several viewers each with different purposes.</span></span> <span data-ttu-id="b54c2-120">各種檢視者可以使用中的 [任何文件上**辨識項**。</span><span class="sxs-lookup"><span data-stu-id="b54c2-120">The various viewers can be used by clicking on any document in **Evidence**.</span></span> <span data-ttu-id="b54c2-121">目前提供檢視程式：</span><span class="sxs-lookup"><span data-stu-id="b54c2-121">The viewers currently provided are:</span></span>

- <span data-ttu-id="b54c2-122">檔案中繼資料</span><span class="sxs-lookup"><span data-stu-id="b54c2-122">File metadata</span></span>
- <span data-ttu-id="b54c2-123">原生檢視</span><span class="sxs-lookup"><span data-stu-id="b54c2-123">Native view</span></span>
- <span data-ttu-id="b54c2-124">文字檢視</span><span class="sxs-lookup"><span data-stu-id="b54c2-124">Text view</span></span>
- <span data-ttu-id="b54c2-125">加上註解檢視</span><span class="sxs-lookup"><span data-stu-id="b54c2-125">Annotate view</span></span>
- <span data-ttu-id="b54c2-126">轉換後的檢視</span><span class="sxs-lookup"><span data-stu-id="b54c2-126">Converted view</span></span>

## <a name="file-metadata"></a><span data-ttu-id="b54c2-127">檔案中繼資料</span><span class="sxs-lookup"><span data-stu-id="b54c2-127">File metadata</span></span>

<span data-ttu-id="b54c2-128">此面板可以切換為開啟/關閉顯示各種文件相關聯的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="b54c2-128">This panel can be toggled on/off to display various metadata associated with the document.</span></span> <span data-ttu-id="b54c2-129">雖然可以自訂搜尋結果方格，以顯示特定的中繼資料，但有其中水平捲動可能很難同時檢閱資料的執行個體。</span><span class="sxs-lookup"><span data-stu-id="b54c2-129">Although the search results grid can be customized to display specific metadata, there are instances where scrolling horizontally can be difficult while reviewing data.</span></span> <span data-ttu-id="b54c2-130">檔案中繼資料] 面板可讓使用者在檢視器中檢視切換。</span><span class="sxs-lookup"><span data-stu-id="b54c2-130">The File metadata panel allows a user to toggle on a view within the viewer.</span></span>

![<span data-ttu-id="b54c2-131">檔案中繼資料] 面板</span><span class="sxs-lookup"><span data-stu-id="b54c2-131">File metadata panel</span></span>
](../media/Reviewimage2.png)

## <a name="native-view"></a><span data-ttu-id="b54c2-132">原生檢視</span><span class="sxs-lookup"><span data-stu-id="b54c2-132">Native view</span></span>

<span data-ttu-id="b54c2-133">原生檢視器會顯示最豐富的文件檢視。</span><span class="sxs-lookup"><span data-stu-id="b54c2-133">The Native viewer displays the richest view of a document.</span></span> <span data-ttu-id="b54c2-134">它支援數百個檔案類型，用來顯示 truest 可能的原生經驗。</span><span class="sxs-lookup"><span data-stu-id="b54c2-134">It supports hundreds of file types and is meant to display the truest to native experience possible.</span></span> <span data-ttu-id="b54c2-135">對於 Microsoft Office 檔案，例如檢視器運用 Office Online 才能顯示內容，例如文件的註解的 Excel 公式、 隱藏的列/欄、 PowerPoint 備忘稿、 等等。如需更多關於 Office 線上檢視程式的詳細資訊，請造訪以下\[需要連結\]</span><span class="sxs-lookup"><span data-stu-id="b54c2-135">For Microsoft Office files, for example, the viewer leverages Office Online in order to display content such as document comments, Excel formulas, hidden rows/columns, PowerPoint notes, etc. For more information regarding the Office Online viewers, visit here \[need link\]</span></span>

![<span data-ttu-id="b54c2-136">原生檢視</span><span class="sxs-lookup"><span data-stu-id="b54c2-136">Native view</span></span>
](../media/Reviewimage3.png)

## <a name="text-view"></a><span data-ttu-id="b54c2-137">文字檢視</span><span class="sxs-lookup"><span data-stu-id="b54c2-137">Text view</span></span>

<span data-ttu-id="b54c2-138">文字檢視器提供解壓縮檔案的文字的檢視。</span><span class="sxs-lookup"><span data-stu-id="b54c2-138">The Text viewer provides a view of the extracted text of a file.</span></span> <span data-ttu-id="b54c2-139">它會忽略任何內嵌的影像，並但格式會是非常效能低落檢視，如果使用者正在嘗試快速了解內容。</span><span class="sxs-lookup"><span data-stu-id="b54c2-139">It ignores any embedded images and formatting but will be a very performant view if a user is trying to understand the content quickly.</span></span> <span data-ttu-id="b54c2-140">文字檢視也包含其他功能：</span><span class="sxs-lookup"><span data-stu-id="b54c2-140">Text view also includes other features:</span></span>

  - <span data-ttu-id="b54c2-141">線條計數器容易參照特定的某些部分的文件</span><span class="sxs-lookup"><span data-stu-id="b54c2-141">Line counter makes it easier to reference specific portions of a document</span></span>

  - <span data-ttu-id="b54c2-142">搜尋結果醒目提示，將會反白顯示文件，以及 scrollbar 中的字詞</span><span class="sxs-lookup"><span data-stu-id="b54c2-142">Search hit highlighting that will highlight terms within the document as well as the scrollbar</span></span>

  - <span data-ttu-id="b54c2-143">Diff 檢視提供比較檢視，檢視接近重複的文件時，會醒目提示文字的差異</span><span class="sxs-lookup"><span data-stu-id="b54c2-143">Diff view provides a comparison view that highlights textual differences when viewing Near Duplicate documents</span></span>

![<span data-ttu-id="b54c2-144">文字檢視</span><span class="sxs-lookup"><span data-stu-id="b54c2-144">Text view</span></span>
](../media/Reviewimage4.png)

![<span data-ttu-id="b54c2-145">Diff 檢視</span><span class="sxs-lookup"><span data-stu-id="b54c2-145">Diff view</span></span>
](../media/Reviewimage5.png)

## <a name="annotate-view"></a><span data-ttu-id="b54c2-146">加上註解檢視</span><span class="sxs-lookup"><span data-stu-id="b54c2-146">Annotate view</span></span>

<span data-ttu-id="b54c2-147">[附註] 檢視提供的功能，可讓使用者將標記文件上套用期間調查包括：</span><span class="sxs-lookup"><span data-stu-id="b54c2-147">The Annotate view provides features that allow users to apply markup on a document during investigation including:</span></span>

  - <span data-ttu-id="b54c2-148">區域 redactions – 使用者可以在方塊上繪製文件以隱藏敏感內容</span><span class="sxs-lookup"><span data-stu-id="b54c2-148">Area redactions – users can draw a box on the document in order to hide sensitive content</span></span>

  - <span data-ttu-id="b54c2-149">鉛筆 – 使用者可以在文件上的手繪圖若要將移至文件的某些部分的注意事項</span><span class="sxs-lookup"><span data-stu-id="b54c2-149">Pencil – users can free-hand draw on a document in order to bring attention to certain portions of a document</span></span>

  - <span data-ttu-id="b54c2-150">選取 [註解-使用者可以選取文件上的註解才能刪除</span><span class="sxs-lookup"><span data-stu-id="b54c2-150">Select annotations - users can select annotations on a document in order to delete</span></span>

  - <span data-ttu-id="b54c2-151">切換的附註透明度 – 讓註釋半透明才能檢視註解後面的內容</span><span class="sxs-lookup"><span data-stu-id="b54c2-151">Toggle annotation transparency – makes annotations semi-transparent in order to view the content behind the annotation</span></span>

  - <span data-ttu-id="b54c2-152">上一頁 – 瀏覽至先前的頁面</span><span class="sxs-lookup"><span data-stu-id="b54c2-152">Previous page – navigates to previous page</span></span>

  - <span data-ttu-id="b54c2-153">下一步] 頁面上 – 瀏覽至 [下一步] 頁面上</span><span class="sxs-lookup"><span data-stu-id="b54c2-153">Next page – navigates to the next page</span></span>

  - <span data-ttu-id="b54c2-154">移至頁面 – 使用者可以輸入來瀏覽至特定的頁面數字</span><span class="sxs-lookup"><span data-stu-id="b54c2-154">Go to page – user can enter a specific page number to navigate to</span></span>

  - <span data-ttu-id="b54c2-155">縮放 – 設定附註] 檢視的縮放層級</span><span class="sxs-lookup"><span data-stu-id="b54c2-155">Zoom – set zoom level for annotate view</span></span>

  - <span data-ttu-id="b54c2-156">旋轉 – 使用者可以將文件順時針方向旋轉</span><span class="sxs-lookup"><span data-stu-id="b54c2-156">Rotate – user can rotate document clockwise</span></span>

  - <span data-ttu-id="b54c2-157">搜尋 – 使用者可以在文件中搜尋和瀏覽至文件內各種拜訪人次</span><span class="sxs-lookup"><span data-stu-id="b54c2-157">Search – user can search within a document and navigate to the various hits within the document</span></span>
    
    ![<span data-ttu-id="b54c2-158">加上註解檢視</span><span class="sxs-lookup"><span data-stu-id="b54c2-158">Annotate view</span></span>
    ](../media/Reviewimage1.png)

<span data-ttu-id="b54c2-159">請注意，這些註釋上做為辨識項，不是在其原始位置 live 系統中所收集的資料。</span><span class="sxs-lookup"><span data-stu-id="b54c2-159">Note that these annotations are on data collected as evidence, not at its original location in live system.</span></span> 

## <a name="more-information"></a><span data-ttu-id="b54c2-160">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="b54c2-160">More information</span></span>

<span data-ttu-id="b54c2-161">下表列出資料調查 （預覽） 中的辨識項的限制。</span><span class="sxs-lookup"><span data-stu-id="b54c2-161">The following table lists the limits for evidence in Data Investigations (Preview).</span></span>  <span data-ttu-id="b54c2-162">任何超過單一檔案最大值的項目會顯示為處理錯誤。</span><span class="sxs-lookup"><span data-stu-id="b54c2-162">Any items that exceed the single file maximums will show up as processing errors.</span></span>
    
  |<span data-ttu-id="b54c2-163">**限制說明**</span><span class="sxs-lookup"><span data-stu-id="b54c2-163">**Description of limit**</span></span>|<span data-ttu-id="b54c2-164">**限制**</span><span class="sxs-lookup"><span data-stu-id="b54c2-164">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="b54c2-165">辨識項集合的最大數目</span><span class="sxs-lookup"><span data-stu-id="b54c2-165">Maximum number of evidence collections</span></span>  <br/> |<span data-ttu-id="b54c2-166">50</span><span class="sxs-lookup"><span data-stu-id="b54c2-166">50</span></span>  <br/> |
  |<span data-ttu-id="b54c2-167">可以 ingested 到的案例 （調查中的所有辨識項集合） 的文件總數</span><span class="sxs-lookup"><span data-stu-id="b54c2-167">Total number of documents that can be ingested into a case (for all evidence collections in the investigation)</span></span>  <br/> |<span data-ttu-id="b54c2-168">1 百萬</span><span class="sxs-lookup"><span data-stu-id="b54c2-168">1 million</span></span>  <br/> |
  |<span data-ttu-id="b54c2-169">每負載的總檔案大小</span><span class="sxs-lookup"><span data-stu-id="b54c2-169">Total file size per load</span></span>  <br/> |<span data-ttu-id="b54c2-170">100 GB</span><span class="sxs-lookup"><span data-stu-id="b54c2-170">100 GB</span></span>  <br/> |
  |<span data-ttu-id="b54c2-171">單一檔案的大小上限</span><span class="sxs-lookup"><span data-stu-id="b54c2-171">Maximum size of single file</span></span>   <br/> |<span data-ttu-id="b54c2-172">100 MB</span><span class="sxs-lookup"><span data-stu-id="b54c2-172">100 MB</span></span>  <br/> |
  |<span data-ttu-id="b54c2-173">從單一檔案解壓縮的字元數上限</span><span class="sxs-lookup"><span data-stu-id="b54c2-173">Maximum number of characters extracted from a single file</span></span>  <br/> |<span data-ttu-id="b54c2-174">10 萬</span><span class="sxs-lookup"><span data-stu-id="b54c2-174">10 million</span></span>  <br/> |
  |<span data-ttu-id="b54c2-175">內嵌文件中的項目的深度</span><span class="sxs-lookup"><span data-stu-id="b54c2-175">Depth of embedded items in a document</span></span>  <br/> |<span data-ttu-id="b54c2-176">25</span><span class="sxs-lookup"><span data-stu-id="b54c2-176">25</span></span>  <br/> |
  