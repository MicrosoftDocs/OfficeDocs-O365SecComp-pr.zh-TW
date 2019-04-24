---
title: 檢閱辨識項中的資料
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
ms.openlocfilehash: e84f05fa1a7356952b62f2f4adc3b7d0f1ddc94e
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32258041"
---
# <a name="review-the-data-in-evidence"></a><span data-ttu-id="1b566-102">檢閱辨識項中的資料</span><span class="sxs-lookup"><span data-stu-id="1b566-102">Review the data in evidence</span></span>

<span data-ttu-id="1b566-103">辨識項集合中的資料調查中的資料是收集並新增至辨識項集合的搜尋結果的快照集。</span><span class="sxs-lookup"><span data-stu-id="1b566-103">The data in an evidence set in a data investigation is a snapshot of the search results that you collected and added to the evidence set.</span></span> <span data-ttu-id="1b566-104">當您將搜尋結果新增至辨識項時，程序就會觸發從搜尋所傳回的項目解壓縮檔案、 中繼資料，以及文字。</span><span class="sxs-lookup"><span data-stu-id="1b566-104">When you add search results to evidence, a process is triggered to extract files, metadata, and text from the items returned by the search.</span></span> <span data-ttu-id="1b566-105">然後資料調查 （預覽） 工具然後來建立新的索引 （稱為 「*進階編製索引*的程序） 的所有資料，並將新增至設定索引標籤的**辨識項**證據。</span><span class="sxs-lookup"><span data-stu-id="1b566-105">Then the Data Investigations (Preview) tool then builds a new index (by a process called *Advanced indexing*) of all the data and adds to an evidence set on the **Evidence** tab.</span></span> 

<span data-ttu-id="1b566-106">時效性調查，這可讓您快速地刪除實際的溢出包含環境或惡意的資料位於在原始的資料來源，在同一時間可讓您調查中的重新建立辨識項隔離的環境中，在此情況下是 [複製到辨識項的資料設定）。</span><span class="sxs-lookup"><span data-stu-id="1b566-106">For time-sensitive investigations, this allows you to quickly contain the environment by deleting the actual spilled or malicious data located in the at original data source, while at the same time allowing you to investigate the re-created evidence in a quarantined environment, which in this case is the data copied to the evidence set).</span></span> <span data-ttu-id="1b566-107">收集證據且新增至辨識項集合之後，您可以檢閱其原生格式、 文字格式或附近原生格式，您可用於加上註解及 redact 文件中的個別文件。</span><span class="sxs-lookup"><span data-stu-id="1b566-107">After the evidence is collected and added to the evidence set, you can review individual documents in their native format, text format, or a near-native format that you can use to annotate and redact documents.</span></span> <span data-ttu-id="1b566-108">此外，您可以執行查詢，以縮小時間範圍、 檔案類型、 資料擁有者及許多其他屬性和搜尋條件的資料集。</span><span class="sxs-lookup"><span data-stu-id="1b566-108">Additionally, you can run queries to narrow the data set by time range, file types, data owners, and many other properties and search conditions.</span></span> <span data-ttu-id="1b566-109">例如，藉由使用作者、 寄件者或收件者的情況，您可以快速地識別人員為參與事件的，如果已與外部使用者共用任何從您的組織的資料。</span><span class="sxs-lookup"><span data-stu-id="1b566-109">For example, by using the Author, Sender, or Recipient conditions, you can quickly identify the people are involved in the incident and if any data from your organization has been shared with external users.</span></span> <span data-ttu-id="1b566-110">如需關於搜尋整個資料中的辨識項設定，請參閱[查詢中的辨識項的資料](evidence-query.md)。</span><span class="sxs-lookup"><span data-stu-id="1b566-110">For more information about searching through data in an evidence set, see [Query the data in evidence](evidence-query.md).</span></span>

<span data-ttu-id="1b566-111">群組文件，並取得更多協助您檢閱，選取 [**證據**] 索引標籤上的辨識項集合，然後按一下**管理證據**。</span><span class="sxs-lookup"><span data-stu-id="1b566-111">To group documents and get more assistance for your review, select an evidence set on the **Evidence** tab, and then click **Manage evidence**.</span></span> <span data-ttu-id="1b566-112">在 [**分析**] 磚中，按一下 [**重建整個集分析**。</span><span class="sxs-lookup"><span data-stu-id="1b566-112">In the **Analytics** tile, click **Rebuild analytics for the whole set**.</span></span> <span data-ttu-id="1b566-113">這將會執行進階的分析，例如重複資料偵測、 電子郵件執行緒，以及佈景主題分析。</span><span class="sxs-lookup"><span data-stu-id="1b566-113">This will run advanced analytics such as duplicate detection, email threading, and theme analysis.</span></span> <span data-ttu-id="1b566-114">之後，您可以看到一般的佈景主題的資料，並也組織的電子郵件執行緒，接近重複項目，並可協助您調查完全重複的 [文件。</span><span class="sxs-lookup"><span data-stu-id="1b566-114">Afterwards, you can see the general themes of the data and also organize documents by email threads, near duplicates, and exact duplicates to help your investigation.</span></span> <span data-ttu-id="1b566-115">如需詳細資訊，請參閱 <<c0>執行更快速地調查分析。</span><span class="sxs-lookup"><span data-stu-id="1b566-115">For more information, see [Run analytics to investigate faster](run-analytics-to-investigate-faster.md).</span></span>

## <a name="view-documents-in-evidence"></a><span data-ttu-id="1b566-116">檢視文件中的辨識項</span><span class="sxs-lookup"><span data-stu-id="1b566-116">View documents in evidence</span></span>

<span data-ttu-id="1b566-117">資料調查 （預覽） 可讓您在數個不同的檢視器，使用具有不同的用途每個檢視器中顯示內容。</span><span class="sxs-lookup"><span data-stu-id="1b566-117">Data Investigations (Preview) allows you to display content in several different viewers, with each viewer having a different purpose.</span></span> <span data-ttu-id="1b566-118">這些檢視程式：</span><span class="sxs-lookup"><span data-stu-id="1b566-118">These viewers are:</span></span>

- <span data-ttu-id="1b566-119">檔案中繼資料</span><span class="sxs-lookup"><span data-stu-id="1b566-119">File metadata</span></span>
- <span data-ttu-id="1b566-120">原生檢視</span><span class="sxs-lookup"><span data-stu-id="1b566-120">Native view</span></span>
- <span data-ttu-id="1b566-121">文字檢視</span><span class="sxs-lookup"><span data-stu-id="1b566-121">Text view</span></span>
- <span data-ttu-id="1b566-122">加上註解檢視</span><span class="sxs-lookup"><span data-stu-id="1b566-122">Annotate view</span></span>

<span data-ttu-id="1b566-123">若要存取這些檢視器，只選取的任何辨識項集合中的文件。</span><span class="sxs-lookup"><span data-stu-id="1b566-123">To access any of these viewers, just select a document in an evidence set.</span></span>

## <a name="file-metadata"></a><span data-ttu-id="1b566-124">檔案中繼資料</span><span class="sxs-lookup"><span data-stu-id="1b566-124">File metadata</span></span>

<span data-ttu-id="1b566-125">此檢視會顯示選取的文件相關聯的各種中繼資料屬性。</span><span class="sxs-lookup"><span data-stu-id="1b566-125">This view displays various metadata properties associated with the selected document.</span></span> <span data-ttu-id="1b566-126">您可以按一下**檔案中繼資料**來切換開啟或關閉此檢視。</span><span class="sxs-lookup"><span data-stu-id="1b566-126">You can toggle this view on and off by clicking **File metadata**.</span></span> <span data-ttu-id="1b566-127">當檢閱文件，您可以檢視檔案中繼資料，仍將不同的檢視之間。</span><span class="sxs-lookup"><span data-stu-id="1b566-127">When reviewing a document, you can view the file metadata and still change between the different viewers.</span></span>

<span data-ttu-id="1b566-128">以下是範例文件的檔案中繼資料。</span><span class="sxs-lookup"><span data-stu-id="1b566-128">Here's an example of the file metadata for a document.</span></span> <span data-ttu-id="1b566-129">如需中繼資料欄位的詳細資訊，請參閱 <<c0>資料調查 （預覽） 中的文件中繼資料欄位。</span><span class="sxs-lookup"><span data-stu-id="1b566-129">For more information about the metadata fields, see [Document metadata fields in Data Investigations (Preview)](document-metadata-fields.md).</span></span>

![檔案中繼資料] 面板](../media/Reviewimage2.png)

## <a name="native-view"></a><span data-ttu-id="1b566-131">原生檢視</span><span class="sxs-lookup"><span data-stu-id="1b566-131">Native view</span></span>

<span data-ttu-id="1b566-132">原生檢視器會以其原生格式顯示最精確的文件檢視。</span><span class="sxs-lookup"><span data-stu-id="1b566-132">The Native viewer displays the most accurate view of a document in it's native format.</span></span> <span data-ttu-id="1b566-133">原生檢視支援的數百個檔案類型而 truest 可能的原生經驗中顯示文件。</span><span class="sxs-lookup"><span data-stu-id="1b566-133">Native view is supported for hundreds of file types and is meant to display documents in the truest native experience possible.</span></span> <span data-ttu-id="1b566-134">Microsoft Office 檔案的原生檢視器會使用 Office Online。</span><span class="sxs-lookup"><span data-stu-id="1b566-134">For Microsoft Office files, the Native viewer uses Office Online.</span></span> <span data-ttu-id="1b566-135">這可讓您在不同的 Office 文件、 公式和隱藏的列/欄在 Excel 中和 PowerPoint 中的備忘稿檢視中檢視內容，例如註解。</span><span class="sxs-lookup"><span data-stu-id="1b566-135">This allows you to view content such as comments in different Office documents, formulas and hidden rows/columns in Excel, and the Notes view in PowerPoint.</span></span>

![<span data-ttu-id="1b566-136">原生檢視</span><span class="sxs-lookup"><span data-stu-id="1b566-136">Native view</span></span>
](../media/Reviewimage3.png)

## <a name="text-view"></a><span data-ttu-id="1b566-137">文字檢視</span><span class="sxs-lookup"><span data-stu-id="1b566-137">Text view</span></span>

<span data-ttu-id="1b566-138">文字檢視器提供解壓縮檔案的文字的檢視。</span><span class="sxs-lookup"><span data-stu-id="1b566-138">The Text viewer provides a view of the extracted text of a file.</span></span> <span data-ttu-id="1b566-139">它會忽略任何內嵌影像和格式設定，但此檢視是很有用，如果您嘗試要快速檢閱並了解文件中的內容。</span><span class="sxs-lookup"><span data-stu-id="1b566-139">It ignores any embedded images and formatting, but this view is very useful if you're trying to quickly review and understand the content in a document.</span></span> <span data-ttu-id="1b566-140">文字檢視也包含下列功能：</span><span class="sxs-lookup"><span data-stu-id="1b566-140">Text view also includes these features:</span></span>

  - <span data-ttu-id="1b566-141">線條計數器，來參照特定的某些部分的文件更容易。</span><span class="sxs-lookup"><span data-stu-id="1b566-141">A line counter, which makes it easier to reference specific portions of a document.</span></span>

  - <span data-ttu-id="1b566-142">搜尋結果醒目提示，請反白顯示文件中以及捲軸上的條款</span><span class="sxs-lookup"><span data-stu-id="1b566-142">Search hit highlighting that highlight terms in the document as well as on the scrollbar</span></span>

  - <span data-ttu-id="1b566-143">Diff 檢視提供比較檢視，檢視使用 [**接近重複項目**] 面板文件時，會醒目提示的文字差異。</span><span class="sxs-lookup"><span data-stu-id="1b566-143">A diff view provides a comparison view that highlights the text differences when viewing documents using the **Near duplicates** panel.</span></span>

<span data-ttu-id="1b566-144">**線條計數器及搜尋的範例結果醒目提示的文字和 scrollbar 中**</span><span class="sxs-lookup"><span data-stu-id="1b566-144">**Example of line counter and search hit highlighting in text and scrollbar**</span></span>

![<span data-ttu-id="1b566-145">文字檢視</span><span class="sxs-lookup"><span data-stu-id="1b566-145">Text view</span></span>
](../media/Reviewimage4.png)

<span data-ttu-id="1b566-146">**Diff 檢視的範例**</span><span class="sxs-lookup"><span data-stu-id="1b566-146">**Example of the diff view**</span></span>

![<span data-ttu-id="1b566-147">Diff 檢視</span><span class="sxs-lookup"><span data-stu-id="1b566-147">Diff view</span></span>
](../media/Reviewimage5.png)

## <a name="annotate-view"></a><span data-ttu-id="1b566-148">加上註解檢視</span><span class="sxs-lookup"><span data-stu-id="1b566-148">Annotate view</span></span>

<span data-ttu-id="1b566-149">[附註] 檢視提供的功能，可讓您可以套用標記的文件檢閱過程中;這包括這些工具：</span><span class="sxs-lookup"><span data-stu-id="1b566-149">The Annotate view provides features that allow you to apply markup on a document during the review process; this  includes these tools:</span></span>

  - <span data-ttu-id="1b566-150">**區域 redactions** – 您可以在隱藏敏感內容的文件上繪製不透明的方塊。</span><span class="sxs-lookup"><span data-stu-id="1b566-150">**Area redactions** – You can draw an opaque box on the document that hides sensitive content.</span></span>

  - <span data-ttu-id="1b566-151">**鉛筆**– 您可以前往注意到特定內容的部分文件上的手繪圖</span><span class="sxs-lookup"><span data-stu-id="1b566-151">**Pencil** – You can free-hand draw on a document to bring attention to certain portions of the content</span></span>

  - <span data-ttu-id="1b566-152">**選取 [註解**-您可以選取並刪除文件中的註解。</span><span class="sxs-lookup"><span data-stu-id="1b566-152">**Select annotations** - You can select and delete annotations in a document.</span></span>

  - <span data-ttu-id="1b566-153">**切換的附註透明度**– 您可以切換 （不透明和半透明） 之間的註解的透明度，因此您可以檢視註解後面的內容。</span><span class="sxs-lookup"><span data-stu-id="1b566-153">**Toggle annotation transparency** – You can toggle the transparency of annotations (between opaque and semi-transparent)so you can view the content behind the annotation.</span></span> <span data-ttu-id="1b566-154">這包括切換鉛筆註釋和 redactions 的透明度。</span><span class="sxs-lookup"><span data-stu-id="1b566-154">This includes toggling the transparency of pencil annotations and redactions.</span></span>

<span data-ttu-id="1b566-155">[附註] 檢視也會提供下列導覽功能：</span><span class="sxs-lookup"><span data-stu-id="1b566-155">The Annotate view also provides the following navigation functionality:</span></span>

  - <span data-ttu-id="1b566-156">**上一步] 頁面上**、**下一步] 頁面上**，並**移至頁面**-用於多頁文件的導覽控制項。</span><span class="sxs-lookup"><span data-stu-id="1b566-156">**Previous page**, **Next page**, and **Go to page** - Navigation controls to use for multi-page documents.</span></span>

  - <span data-ttu-id="1b566-157">**縮放**– 增加或減少附註] 檢視中的文件的大小。</span><span class="sxs-lookup"><span data-stu-id="1b566-157">**Zoom** – Increases or decreases the size of documents in Annotate view.</span></span>

  - <span data-ttu-id="1b566-158">**旋轉**– 順時針方向旋轉文件。</span><span class="sxs-lookup"><span data-stu-id="1b566-158">**Rotate** – Rotate documents clockwise.</span></span>

  - <span data-ttu-id="1b566-159">**搜尋**– 關鍵字的文件，然後使用前一個與下一個控制項 [搜尋]，以在文件中檢視是落在圖形 （這會反白顯示）。</span><span class="sxs-lookup"><span data-stu-id="1b566-159">**Search** – Search for keywords in a document, and then use Previous and Next controls to view the hits (which are highlighted) within the document.</span></span>

<span data-ttu-id="1b566-160">**附註] 檢視的範例**</span><span class="sxs-lookup"><span data-stu-id="1b566-160">**Example of Annotate view**</span></span>

![加上註解檢視](../media/Reviewimage1.png)

> [!NOTE]
> <span data-ttu-id="1b566-162">附註會套用至一份文件已加入至辨識項集合。</span><span class="sxs-lookup"><span data-stu-id="1b566-162">Annotations are applied to a copy of the document that was added to the evidence set.</span></span> <span data-ttu-id="1b566-163">即時服務中的原始文件不加註解。</span><span class="sxs-lookup"><span data-stu-id="1b566-163">The original documents in the live service aren't annotated.</span></span>
