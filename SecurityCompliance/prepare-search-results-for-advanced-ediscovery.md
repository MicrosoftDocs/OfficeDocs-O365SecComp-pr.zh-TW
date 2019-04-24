---
title: 準備 Office 365 進階 eDiscovery 的搜尋結果
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExportWithZoom
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: 0b6fac2d-8627-4b05-9df0-03609db6248b
description: 了解如何準備安全性 & 在 Office 365 規範中心中的內容搜尋的結果，以便進一步分析使用進階電子文件探索工具。
ms.openlocfilehash: 772ef8e24613a0fb872f0c397d7ea80bdad16e4b
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32261975"
---
# <a name="prepare-search-results-for-office-365-advanced-ediscovery"></a><span data-ttu-id="c8d72-103">準備 Office 365 進階 eDiscovery 的搜尋結果</span><span class="sxs-lookup"><span data-stu-id="c8d72-103">Prepare search results for Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="c8d72-104">之後與規範中心成功執行安全性 & 中 eDiscovery 案例相關聯的搜尋，您可以準備搜尋結果，以便進一步分析與 Office 365 進階 eDiscovery，可讓您分析大型、 未結構化資料集並減少相關的法律案件的資料量。</span><span class="sxs-lookup"><span data-stu-id="c8d72-104">After a search that's associated with an eDiscovery case in the Security & Compliance Center is successfully run, you can prepare the search results for further analysis with Office 365 Advanced eDiscovery, which lets you analyze large, unstructured data sets and reduce the amount of data that's relevant to a legal case.</span></span> <span data-ttu-id="c8d72-105">進階電子文件的功能包括：</span><span class="sxs-lookup"><span data-stu-id="c8d72-105">Advanced eDiscovery features include:</span></span>
  
- <span data-ttu-id="c8d72-106">**光學字元辨識**-當您準備搜尋結果進階電子文件，光學字元辨識 (OCR) 功能會自動從圖像、 擷取文字及包含這會在載入若要在搜尋結果進行分析的進階電子文件。</span><span class="sxs-lookup"><span data-stu-id="c8d72-106">**Optical character recognition** - When you prepare search results for Advanced eDiscovery, optical character recognition (OCR) functionality automatically extracts text from images, and includes this with the search results that are loaded in to Advanced eDiscovery for analysis.</span></span> <span data-ttu-id="c8d72-107">OCR 鬆散檔案可支援、 電子郵件附件，與內嵌影像。</span><span class="sxs-lookup"><span data-stu-id="c8d72-107">OCR is supported for loose files, email attachments, and embedded images.</span></span> <span data-ttu-id="c8d72-108">這可讓您將套用至影像檔案中的文字內容的進階電子文件 （近似重複項目、 電子郵件執行緒、 主題和預測撰寫程式碼） 的文字分析功能。</span><span class="sxs-lookup"><span data-stu-id="c8d72-108">This allows you to apply the text analytic capabilities of Advanced eDiscovery (near-duplicates, email threading, themes, and predictive coding) to the text content in image files.</span></span> <span data-ttu-id="c8d72-109">進階電子文件探索 OCR 影像檔案支援下列格式：</span><span class="sxs-lookup"><span data-stu-id="c8d72-109">Advanced eDiscovery OCR supports the following formats for image files:</span></span>

    - <span data-ttu-id="c8d72-110">GIF</span><span class="sxs-lookup"><span data-stu-id="c8d72-110">GIF</span></span>
    - <span data-ttu-id="c8d72-111">JPEG</span><span class="sxs-lookup"><span data-stu-id="c8d72-111">JPEG</span></span>
    - <span data-ttu-id="c8d72-112">JPG</span><span class="sxs-lookup"><span data-stu-id="c8d72-112">JPG</span></span>
    - <span data-ttu-id="c8d72-113">PNG</span><span class="sxs-lookup"><span data-stu-id="c8d72-113">PNG</span></span>
    - <span data-ttu-id="c8d72-114">TIFF</span><span class="sxs-lookup"><span data-stu-id="c8d72-114">TIFF</span></span>
    
- <span data-ttu-id="c8d72-115">**近似重複偵測**-可讓您更有效率，結構化資料檢閱讓一位人員檢閱一群類似的文件。</span><span class="sxs-lookup"><span data-stu-id="c8d72-115">**Near-duplicate detection** - Lets you structure your data review more efficiently, so one person reviews a group of similar documents.</span></span> <span data-ttu-id="c8d72-116">這有助於防止多位檢閱者需要檢視相同的文件的不同版本。</span><span class="sxs-lookup"><span data-stu-id="c8d72-116">This helps prevent multiple reviewers from having to view different versions of the same document.</span></span> 
    
- <span data-ttu-id="c8d72-117">**電子郵件執行緒**-可協助您找出電子郵件執行緒中唯一的郵件，因此您可以專注於僅中每一封郵件的新資訊。</span><span class="sxs-lookup"><span data-stu-id="c8d72-117">**Email threading** - Helps you identify the unique messages in an email thread so you can focus on only the new information in each message.</span></span> <span data-ttu-id="c8d72-118">在 [電子郵件執行緒，第二個郵件會包含第一個訊息。</span><span class="sxs-lookup"><span data-stu-id="c8d72-118">In an email thread, the second message contains the first message.</span></span> <span data-ttu-id="c8d72-119">同樣地，更新版本的郵件會包含所有舊的郵件。</span><span class="sxs-lookup"><span data-stu-id="c8d72-119">Likewise, later messages contain all the previous messages.</span></span> <span data-ttu-id="c8d72-120">電子郵件執行緒中移除需要檢閱其完整的電子郵件執行緒中每一封郵件。</span><span class="sxs-lookup"><span data-stu-id="c8d72-120">Email threading removes the need to review every message in its entirety in an email thread.</span></span> 
    
- <span data-ttu-id="c8d72-121">**佈景主題**-協助您寶貴的意見，關於您的資料超過剛關鍵字搜尋統計資料。</span><span class="sxs-lookup"><span data-stu-id="c8d72-121">**Themes** - Help you get valuable insight about your data beyond just keyword search statistics.</span></span> <span data-ttu-id="c8d72-122">佈景主題可協助調查分組相關的文件，因此您可以查看在內容中的文件。</span><span class="sxs-lookup"><span data-stu-id="c8d72-122">Themes help investigations by grouping related documents so you can look at the documents in context.</span></span> <span data-ttu-id="c8d72-123">時使用佈景主題，您可以檢視文件的一組相關的佈景主題、 決定任何重疊，並再識別 cross-sections 相關的資料。</span><span class="sxs-lookup"><span data-stu-id="c8d72-123">When using themes, you can view the related themes for a set of documents, determine any overlap, and then identify cross-sections of related data.</span></span> 
    
- <span data-ttu-id="c8d72-124">**Predictive 編碼**-可讓您訓練上您要尋找哪些，讓您進行決策 （某個項目是否相關與否） 的系統上一小群的文件。</span><span class="sxs-lookup"><span data-stu-id="c8d72-124">**Predictive coding** - Lets you train the system on what you're looking for, by allowing you to make decisions (about whether something is relevant or not) on a small set of documents.</span></span> <span data-ttu-id="c8d72-125">進階電子文件然後適用於 （根據您指引），學習分析中的資料集的文件的所有時。</span><span class="sxs-lookup"><span data-stu-id="c8d72-125">Advanced eDiscovery then applies that learning (based on your guidance) when analyzing all of the documents in the data set.</span></span> <span data-ttu-id="c8d72-126">根據該學習，進階電子文件，提供相關性排名，因此您可以決定要檢閱哪些文件何種文件為基礎會很有可能是相關的大小寫。</span><span class="sxs-lookup"><span data-stu-id="c8d72-126">Based on that learning, Advanced eDiscovery provides a relevance ranking so you can decide which documents to review based on what document are the most likely to be relevant to the case.</span></span> 
    
- <span data-ttu-id="c8d72-127">**匯出資料，請先檢閱應用程式**-您已完成您的分析，並減少資料集之後，您可以從進階電子文件和 Office 365 匯出資料。</span><span class="sxs-lookup"><span data-stu-id="c8d72-127">**Exporting data for review applications**  - You can export data from Advanced eDiscovery and Office 365 after you've completed your analysis and reduced the data set.</span></span> <span data-ttu-id="c8d72-128">匯出封裝也會包含包含從匯出的內容和分析中繼資料屬性之 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="c8d72-128">The export package includes a CSV file that contains the properties from the exported content and analytics metadata.</span></span> <span data-ttu-id="c8d72-129">此匯出套件然後匯入至 eDiscovery 檢閱應用程式。</span><span class="sxs-lookup"><span data-stu-id="c8d72-129">This export package can then be imported to an eDiscovery review application.</span></span> 
    
## <a name="before-you-begin"></a><span data-ttu-id="c8d72-130">開始之前</span><span class="sxs-lookup"><span data-stu-id="c8d72-130">Before you begin</span></span>

- <span data-ttu-id="c8d72-131">若要分析使用進階電子文件的使用者資料，使用者 (資料的 custodian) 必須被指派 Office 365 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="c8d72-131">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license.</span></span> <span data-ttu-id="c8d72-132">或者，使用 Office 365 E1 或 E3 授權的使用者可被指派的進階電子文件獨立授權。</span><span class="sxs-lookup"><span data-stu-id="c8d72-132">Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license.</span></span> <span data-ttu-id="c8d72-133">系統管理員和法務人員對於已指派給的情況下，並使用進階電子文件探索分析資料不需要 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="c8d72-133">Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span> 
    
- <span data-ttu-id="c8d72-134">您必須是 eDiscovery 管理員或 eDiscovery 系統管理員的安全性 & 合規性中心，以準備進階電子文件中的搜尋結果中。</span><span class="sxs-lookup"><span data-stu-id="c8d72-134">You have to be an eDiscovery Manager or an eDiscovery Administrator in the Security & Compliance Center to prepare search results for Advanced eDiscovery.</span></span> <span data-ttu-id="c8d72-135">eDiscovery 管理員為 eDiscovery 管理員角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="c8d72-135">An eDiscovery Manager is a member of the eDiscovery Manager role group.</span></span> <span data-ttu-id="c8d72-136">eDiscovery 系統管理員也是 eDiscovery 管理員角色群組的成員，但已獲指派其他 eDiscovery 權限。</span><span class="sxs-lookup"><span data-stu-id="c8d72-136">An eDiscovery Administrator is also member of the eDiscovery Manager role group, but has been assigned additional eDiscovery privileges.</span></span> <span data-ttu-id="c8d72-137">如需指派 eDiscovery 系統管理員權限的指示，請參閱[eDiscovery 案例](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members)中的步驟 1。</span><span class="sxs-lookup"><span data-stu-id="c8d72-137">For instructions about assigning eDiscovery Administrator permissions, see Step 1 in [eDiscovery cases](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span></span>
    
## <a name="step-1-prepare-search-results-for-advanced-ediscovery"></a><span data-ttu-id="c8d72-138">步驟 1： 準備搜尋結果的進階電子文件</span><span class="sxs-lookup"><span data-stu-id="c8d72-138">Step 1: Prepare search results for Advanced eDiscovery</span></span>

<span data-ttu-id="c8d72-139">您可以準備與 eDiscovery 案例相關聯的搜尋的結果。</span><span class="sxs-lookup"><span data-stu-id="c8d72-139">You can prepare the results of a search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="c8d72-140">當您準備進階 eDiscovery 的搜尋結果時，資料已上傳，且暫時儲存在 Microsoft cloud 中的唯一 Windows Azure 存放區域中。</span><span class="sxs-lookup"><span data-stu-id="c8d72-140">When you prepare search results for Advanced eDiscovery, the data is uploaded and temporarily stored in a unique Windows Azure storage area in the Microsoft cloud.</span></span> <span data-ttu-id="c8d72-141">此時會 OCR 功能會從搜尋結果中的影像擷取文字。</span><span class="sxs-lookup"><span data-stu-id="c8d72-141">It's at this point that the OCR functionality extracts text from images in the search results.</span></span> <span data-ttu-id="c8d72-142">在 [[步驟 2](#step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery)，此文字和其他搜尋結果資料載入至進階電子文件中的案例。</span><span class="sxs-lookup"><span data-stu-id="c8d72-142">In [Step 2](#step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery), this text and the other search results data is loaded in to the case in Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="c8d72-143">在 [安全性 & 合規性中心中，按一下 [ **eDiscovery** \> **eDiscovery**來顯示貴組織中的案例清單。</span><span class="sxs-lookup"><span data-stu-id="c8d72-143">In the Security & Compliance Center, click **eDiscovery** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="c8d72-144">您想要準備進階 eDiscovery 中分析的搜尋結果的案例旁邊，按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="c8d72-144">Click **Open** next to the case that you want to prepare search results for analysis in Advanced eDiscovery.</span></span> 
    
3. <span data-ttu-id="c8d72-145">在 [**首頁**] 頁面的情況下，按一下 [**搜尋**]，然後選取搜尋]。</span><span class="sxs-lookup"><span data-stu-id="c8d72-145">On the **Home** page for the case, click **Search**, and then select the search.</span></span>
    
4. <span data-ttu-id="c8d72-146">在 [詳細資料] 窗格中，[**進階電子文件探索分析結果**，請按一下 [**準備供分析的結果**。</span><span class="sxs-lookup"><span data-stu-id="c8d72-146">In the details pane, under **Analyze results with Advanced eDiscovery**, click **Prepare results for analysis**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c8d72-147">如果搜尋的結果是早於 7 天前，則會提示您更新搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="c8d72-147">If the search results are older than 7 days, you will be prompted to update the search results.</span></span> 
  
5. <span data-ttu-id="c8d72-148">在**準備供分析的結果**的頁面上，執行下列動作︰ </span><span class="sxs-lookup"><span data-stu-id="c8d72-148">On the **Prepare results for analysis** page, do the following:</span></span> 
    
    - <span data-ttu-id="c8d72-149">選擇要準備進階 eDiscovery 中分析的編製索引的項目、 已編製索引和未編製索引項目或僅未編製索引的項目。</span><span class="sxs-lookup"><span data-stu-id="c8d72-149">Choose to prepare indexed items, indexed and unindexed items, or only unindexed items for analysis in Advanced eDiscovery.</span></span>
    
    - <span data-ttu-id="c8d72-150">選擇是否要包含在符合搜尋準則的 SharePoint 上找到的文件的所有版本。</span><span class="sxs-lookup"><span data-stu-id="c8d72-150">Choose whether to include all versions of documents found on SharePoint that met the search criteria.</span></span> <span data-ttu-id="c8d72-151">這個選項只在搜尋內容來源包含網站時才會出現。</span><span class="sxs-lookup"><span data-stu-id="c8d72-151">This option appears only if the content sources for the search includes sites.</span></span>
    
    - <span data-ttu-id="c8d72-152">指定是否要通知訊息傳送 （或複製） 給人員準備程序完成時，且資料就緒可進行處理進階電子文件中。</span><span class="sxs-lookup"><span data-stu-id="c8d72-152">Specify whether you want a notification message sent (or copied) to a person when the preparation process is completed and the data is ready to be processed in Advanced eDiscovery.</span></span>
    
6. <span data-ttu-id="c8d72-153">按一下 [準備]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c8d72-153">Click **Prepare**.</span></span>
    
    <span data-ttu-id="c8d72-154">搜尋結果會準備用於進階電子文件探索分析。</span><span class="sxs-lookup"><span data-stu-id="c8d72-154">The search results are prepared for analysis with Advanced eDiscovery.</span></span>
    
7. <span data-ttu-id="c8d72-155">在 [詳細資料] 窗格中，按一下 [**檢查準備狀態**顯示準備程序的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c8d72-155">In the details pane, click **Check preparation status** to display information about the preparation process.</span></span> <span data-ttu-id="c8d72-156">準備程序完成時，您可以移至進階電子文件處理資料以供分析中的案例。</span><span class="sxs-lookup"><span data-stu-id="c8d72-156">When the preparation process is finished, you can go to the case in Advanced eDiscovery to process the data for analysis.</span></span> 
    
## <a name="step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery"></a><span data-ttu-id="c8d72-157">步驟 2： 將搜尋結果資料新增至進階電子文件中的案例</span><span class="sxs-lookup"><span data-stu-id="c8d72-157">Step 2: Add the search results data to the case in Advanced eDiscovery</span></span>
<span data-ttu-id="c8d72-158"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="c8d72-158"></span></span>

<span data-ttu-id="c8d72-159">準備完成時下, 一步是移至進階電子文件，然後搜尋結果資料 （這已上傳至 Microsoft 雲端中的 Azure 儲存體] 區域） 載入至進階電子文件中的案例。</span><span class="sxs-lookup"><span data-stu-id="c8d72-159">When the preparation is finished, the next step is to go to Advanced eDiscovery and load the search results data (which have been uploaded to an Azure storage area in the Microsoft cloud ) to the case in Advanced eDiscovery.</span></span> <span data-ttu-id="c8d72-160">如同先前的說明，來存取您必須是在進階電子文件中的安全性 & 合規性中心中的 eDiscovery 系統管理員或系統管理員的進階電子文件。</span><span class="sxs-lookup"><span data-stu-id="c8d72-160">As previously explained, to access Advanced eDiscovery you have to be an eDiscovery Administrator in the Security & Compliance Center or an administrator in Advanced eDiscovery.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c8d72-161">花費的時間資料安全性 & 合規性中心設為可供新增至進階電子文件中的案例會因從 eDiscovery 搜尋結果的大小而有所不同。</span><span class="sxs-lookup"><span data-stu-id="c8d72-161">The time it takes for the data from the Security & Compliance Center to be available to add to a case in Advanced eDiscovery varies, depending on the size of the results from the eDiscovery search.</span></span> 
  
1. <span data-ttu-id="c8d72-162">在 [安全性 & 合規性中心中，按一下 [ **eDiscovery** \> **eDiscovery**來顯示貴組織中的案例清單。</span><span class="sxs-lookup"><span data-stu-id="c8d72-162">In the Security & Compliance Center, click **eDiscovery** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="c8d72-163">您想要將資料載入在進階電子文件中的案例旁邊，按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="c8d72-163">Click **Open** next to the case that you want to load data in to in Advanced eDiscovery.</span></span> 
    
3. <span data-ttu-id="c8d72-164">在案例的 [首頁]\*\*\*\* 頁面上，按一下 [進階電子文件探索]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c8d72-164">On the **Home** page for the case, click **Advanced eDiscovery**.</span></span> 
    
    ![按一下切換以開啟 [進階電子文件中的 [大小寫的進階 ediscovery](media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    <span data-ttu-id="c8d72-166">**連線至進階電子文件**會顯示進度列。</span><span class="sxs-lookup"><span data-stu-id="c8d72-166">The **Connecting to Advanced eDiscovery** progress bar is displayed.</span></span> <span data-ttu-id="c8d72-167">當您已連線至進階電子文件時，在這種情況的 [設定] 頁面上會顯示容器的清單。</span><span class="sxs-lookup"><span data-stu-id="c8d72-167">When you're connected to Advanced eDiscovery, a list of containers is displayed on the setup page for the case.</span></span> 
    
    ![這種情況會顯示在進階電子文件](media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     <span data-ttu-id="c8d72-169">這些容器代表您準備好在步驟 1 中的進階 eDiscovery 中分析的搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="c8d72-169">These containers represent the search results that you prepared for analysis in Advanced eDiscovery in Step 1.</span></span> <span data-ttu-id="c8d72-170">請注意，容器的名稱相同的名稱搜尋安全性 & 合規性中心中的情況。</span><span class="sxs-lookup"><span data-stu-id="c8d72-170">Note that the name of the container has the same name as the search in the case in the Security & Compliance Center.</span></span> <span data-ttu-id="c8d72-171">在清單容器是您備妥。</span><span class="sxs-lookup"><span data-stu-id="c8d72-171">The containers in the list are the ones that you prepared.</span></span> <span data-ttu-id="c8d72-172">如果不同的使用者準備進階電子文件中的搜尋結果，將不會在清單中包含對應的容器。</span><span class="sxs-lookup"><span data-stu-id="c8d72-172">If a different user prepared search results for Advanced eDiscovery, the corresponding containers won't be included in the list.</span></span> 
    
4. <span data-ttu-id="c8d72-173">若要從容器中的搜尋結果資料載入至進階電子文件中的案例中，選取的容器，然後按一下 [**程序**。</span><span class="sxs-lookup"><span data-stu-id="c8d72-173">To load the search result data from a container in to the case in Advanced eDiscovery, select a container and then click **Process**.</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="c8d72-174">後續步驟</span><span class="sxs-lookup"><span data-stu-id="c8d72-174">Next steps</span></span>

<span data-ttu-id="c8d72-175">之後結果的 eDiscovery 搜尋會加入至情況下下, 一步是使用進階電子文件探索工具來分析資料，並識別特定的法律案件回應的內容。</span><span class="sxs-lookup"><span data-stu-id="c8d72-175">After the results of an eDiscovery search are added to a case, the next step is to use the Advanced eDiscovery tools to analyze the data and identify the content that's responsive to a specific legal case.</span></span> <span data-ttu-id="c8d72-176">如需使用進階電子文件的詳細資訊，請參閱 < <b0>Office 365 進階電子文件探索</b0>。</span><span class="sxs-lookup"><span data-stu-id="c8d72-176">For information about using Advanced eDiscovery, see [Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md).</span></span>
  
## <a name="more-information"></a><span data-ttu-id="c8d72-177">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="c8d72-177">More information</span></span>

<span data-ttu-id="c8d72-178">當您準備進階 eDiscovery 中分析時，將會解密任何包含在搜尋結果中的 RMS 加密的電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="c8d72-178">Any RMS-encrypted email messages that are included in the search results will be decrypted when you prepare them for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="c8d72-179">預設會啟用此解密功能的 eDiscovery 管理員角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="c8d72-179">This decryption capability is enabled by default for members of the eDiscovery Manager role group.</span></span> <span data-ttu-id="c8d72-180">這是因為 RMS 解密管理角色指派給這個角色群組。</span><span class="sxs-lookup"><span data-stu-id="c8d72-180">This is because the RMS Decrypt management role is assigned to this role group.</span></span> <span data-ttu-id="c8d72-181">請謹記下列事項需要注意的解密電子郵件：</span><span class="sxs-lookup"><span data-stu-id="c8d72-181">Keep the following things in mind about decrypting email messages:</span></span>
  
- <span data-ttu-id="c8d72-182">目前，此解密功能不會包括加密的內容則來自 SharePoint 和 OneDrive for Business 網站。</span><span class="sxs-lookup"><span data-stu-id="c8d72-182">Currently, this decryption capability doesn't include encrypted content from SharePoint and OneDrive for Business sites.</span></span> <span data-ttu-id="c8d72-183">當您將其匯出，將會解密只 RMS 加密的電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="c8d72-183">Only RMS-encrypted email messages will be decrypted when you export them.</span></span>
    
- <span data-ttu-id="c8d72-184">如果 RMS 加密的電子郵件訊息的附件 （例如文件或另一個電子郵件），也要加密，將會解密只最上層的電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="c8d72-184">If an RMS-encrypted email message has an attachment (such as a document or another email message) that's also encrypted, only the top-level email message will be decrypted.</span></span>
    
- <span data-ttu-id="c8d72-185">如果您需要防止其他人解密受 RMS 加密的郵件，準備進階 eDiscovery 中分析的搜尋結果時，您必須建立自訂角色群組 （藉由複製內建的 eDiscovery 管理員角色群組），然後移除 RMS解密從自訂角色群組的管理角色。</span><span class="sxs-lookup"><span data-stu-id="c8d72-185">If you need to prevent someone from decrypting RMS-encrypted messages when preparing search results for analysis in Advanced eDiscovery, you'll have to create a custom role group (by copying the built-in eDiscovery Manager role group) and then remove the RMS Decrypt management role from the custom role group.</span></span> <span data-ttu-id="c8d72-186">然後新增您不想要將郵件解密的自訂角色群組的成員身分的人員。</span><span class="sxs-lookup"><span data-stu-id="c8d72-186">Then add the person who you don't want to decrypt messages as a member of the custom role group.</span></span>
