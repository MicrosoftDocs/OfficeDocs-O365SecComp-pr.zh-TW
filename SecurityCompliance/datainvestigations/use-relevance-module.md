---
title: 使用相關性模組來辨識項中分析資料
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
ms.openlocfilehash: 3aa37a6778947934759eb652a9367559b9ef838b
ms.sourcegitcommit: 2c5834235c32b2616e1813ce24eeb3419a09629f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2019
ms.locfileid: "31030004"
---
# <a name="use-the-relevance-module-to-analyze-data-in-evidence"></a><span data-ttu-id="2a6f7-102">使用相關性模組來辨識項中分析資料</span><span class="sxs-lookup"><span data-stu-id="2a6f7-102">Use the Relevance module to analyze data in evidence</span></span>

<span data-ttu-id="2a6f7-103">在 [資料調查 （預覽），相關性模組包含相關性訓練與 < review of 調查相關檔案。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-103">In Data Investigations (Preview), the Relevance module includes the Relevance training and review of files related to an investigation.</span></span> <span data-ttu-id="2a6f7-104">相關性工作流程會顯示，並說明如下：</span><span class="sxs-lookup"><span data-stu-id="2a6f7-104">The Relevance workflow is shown and described as follows:</span></span>
  
![相關性工作流程](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- <span data-ttu-id="2a6f7-106">**循環的評估和追蹤**：</span><span class="sxs-lookup"><span data-stu-id="2a6f7-106">**Cycles of assessment and tracking**:</span></span>
    
  - <span data-ttu-id="2a6f7-107">**評估**： 啟用檔案的隨機樣本為基礎的早期評估，並使用此評定套用決策，以決定預測的程式碼撰寫程序的效能。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-107">**Assessment**: Enables early assessment based on a random sample of files and uses this assessment to apply decisions to determine the performance of the predictive coding process.</span></span> 
    
  - <span data-ttu-id="2a6f7-108">**追蹤**： 計算並顯示過渡同時監視程序的統計有效性的評估結果。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-108">**Track**: Calculate and display interim results of the assessment while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="2a6f7-109">**循環的訓練與追蹤**</span><span class="sxs-lookup"><span data-stu-id="2a6f7-109">**Cycles of training and tracking**</span></span>
    
  - <span data-ttu-id="2a6f7-110">**標記**： 資料調查 （預覽） 可學習相關性準則專屬於根據專家的反覆運算檢閱每一項問題和標記的個別的檔案。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-110">**Tag**: Data Investigations (Preview) learns Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span></span>
    
  - <span data-ttu-id="2a6f7-111">**追蹤**： 計算並顯示過渡結果的相關性訓練，同時監視程序的統計的有效性。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-111">**Track**: Calculate and display interim results of the Relevance training while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="2a6f7-112">**批次計算**： 累積和學相關性準則套用至整個檔案集合，並為每個檔案產生相關性分數。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-112">**Batch calculation**: The accumulated and learned Relevance criteria is applied to the entire file collection, and a Relevance score is generated for each file.</span></span>
    
- <span data-ttu-id="2a6f7-113">**決定**： 套用至整個案例分析的結果會顯示批次計算後，並且會顯示用來決定文件檢閱資料。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-113">**Decide**: The results of the analysis applied to the entire case is displayed after Batch calculation, and data used to make document review decisions is displayed.</span></span>
    
- <span data-ttu-id="2a6f7-114">**測試**： 可以測試結果，以確認資料調查 （預覽） 處理程序的效率的有效性。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-114">**Test**: Results can be tested to verify the validity and effectiveness of the Data Investigations (Preview) processing.</span></span>

- <span data-ttu-id="2a6f7-115">**搜尋**： 相關性工作流程完成後，您可以使用例如讀取百分位數的文件的輸出為您的問題當您執行查詢時您工作集內。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-115">**Search**: Once the Relevance workflow is complete, you can use the output such as read percentile of a document for your issue when you run a query within your working set.</span></span>
    
## <a name="guidelines-for-relevance-training-and-review"></a><span data-ttu-id="2a6f7-116">相關性訓練及檢閱指導方針</span><span class="sxs-lookup"><span data-stu-id="2a6f7-116">Guidelines for Relevance training and review</span></span>

<span data-ttu-id="2a6f7-117">下列是概觀相關性訓練及檢閱指導方針：</span><span class="sxs-lookup"><span data-stu-id="2a6f7-117">Following is an overview of guidelines for Relevance training and review:</span></span>
  
- <span data-ttu-id="2a6f7-118">**錯誤與不一致**： 如果標記錯誤所做的訓練期間，傳回以更正這些舊檔案範例。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-118">**Errors and inconsistencies**: If tagging errors are made during training, return to previous file samples to correct them.</span></span> <span data-ttu-id="2a6f7-119">如果有太多錯誤更正或沒有的情況下，或是此問題： 新觀點來看，應重新定義相關性準則，由系統管理員，且相關性訓練重新啟動。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-119">If there are too many errors to correct or there is a new perspective of the case or issue, the Relevance criteria should be redefined by the Administrator, and the Relevance training restarted.</span></span>
    
- <span data-ttu-id="2a6f7-120">**標記和訓練**：</span><span class="sxs-lookup"><span data-stu-id="2a6f7-120">**Tagging and training**:</span></span> 
    
  - <span data-ttu-id="2a6f7-121">檔案應該根據內容才標記。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-121">Files should be tagged based on content only.</span></span> <span data-ttu-id="2a6f7-122">執行動作時，不會考慮中繼資料，例如 custodian、 日期或檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-122">Do not consider metadata, such as custodian, date, or file path.</span></span> 
    
  - <span data-ttu-id="2a6f7-123">執行動作時，考慮日期範圍表示在文字中的標記檔案。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-123">Do not consider date range indications in the text when tagging files.</span></span>
    
  - <span data-ttu-id="2a6f7-124">當標記檔案不認為內嵌圖形的映像。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-124">Do not consider embedded graphical images when tagging files.</span></span>
     
  - <span data-ttu-id="2a6f7-125">忽略中 [文字] 檢視中顯示的檔案內容相關性中移除套用至相關性文字。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-125">Ignore text applied to Relevance will be removed in the displayed file content in the text view in Relevance.</span></span> <span data-ttu-id="2a6f7-126">如果略過的文字的值已定義相關性訓練已啟動後，新略過的文字將套用到從其已定義的點建立的範例檔案。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-126">If the values for Ignore text were defined after Relevance training already started, the new ignored text will be applied to sample files created from the point in which it was defined.</span></span> <span data-ttu-id="2a6f7-127">略過文字使用的功能應該謹慎，其使用可能會降低檔案分析的效能</span><span class="sxs-lookup"><span data-stu-id="2a6f7-127">The Ignore Text feature should be used cautiously, as its use may reduce the performance of file analysis</span></span>
    
  - <span data-ttu-id="2a6f7-128">使用 [**略過標記**] 選項僅在必要時。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-128">Use the **Skip tagging** option only when necessary.</span></span> <span data-ttu-id="2a6f7-129">略過的檔案上資料調查 （預覽） 不會不訓練根據。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-129">Data Investigations (Preview) does not train based on skipped files.</span></span> <span data-ttu-id="2a6f7-130">在評估，如果很難判斷檔案是否相關，最好是標記為 Relevant (R) 或不相關 （編號） 儘而不是選取 [**略過**。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-130">In assessment, if it's hard to tell whether a file is relevant, it is better to tag as Relevant (R) or Not relevant (NR) whenever possible rather than selecting **Skip**.</span></span> <span data-ttu-id="2a6f7-131">當資料調查 （預覽） 評估訓練時，然後才能看到它如何妥善處理這些類型的檔案。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-131">When Data Investigations (Preview) evaluates training, it can then be seen how well these types of files were processed.</span></span>
    
  - <span data-ttu-id="2a6f7-132">具有很少量的擷取文字偶數檔案應該標記中為 R/編號，而非 「 略過 」，儘可能的訓練。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-132">Even files with a very small amount of extracted text should be tagged in training as R/NR, rather than as "Skip", when possible.</span></span> 
    
  - <span data-ttu-id="2a6f7-133">標記可能會影響類別器，只要檔案是可讀取，並且可以標示為 R/編號。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-133">Tagging can impact the classifier as long as the file is readable and can be tagged as R/NR.</span></span>
    
  - <span data-ttu-id="2a6f7-134">在 [**標籤**] 索引標籤上顯示範例檔案清單上的檔案順序編號可讓使用者返回原始檔的顯示順序。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-134">The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files.</span></span> 
    
  - <span data-ttu-id="2a6f7-135">您可以回到任何範例，並變更的評估標記和訓練設定檔案。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-135">You can go back to any sample and change the tagging of the assessment and training set files.</span></span> <span data-ttu-id="2a6f7-136">建立下一個範例時，將會套用所做的變更。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-136">The changes will be applied when creating the next sample.</span></span>
    
  - <span data-ttu-id="2a6f7-137">掃描的 Excel 以 PDF 格式的檔案應被視為相同原生的 Excel 檔案時標記檔案。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-137">Scanned Excel files in PDF format should be treated the same as native Excel files when tagging files.</span></span>
    
  - <span data-ttu-id="2a6f7-138">在 [相關檔案相關性標記有疑問，請洽詢專家。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-138">When in doubt regarding the Relevance tagging of a file, consult an expert.</span></span> <span data-ttu-id="2a6f7-139">不正確的標記相關性訓練期間可能會導致遺失時間稍後的程序與在整體結果的品質也可能會造成負面影響。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-139">Incorrect tagging during the Relevance training can lead to lost time later in the process and may also have a negative impact on the quality of the overall results.</span></span>
    
  - <span data-ttu-id="2a6f7-140">已定義的關鍵字的關鍵字清單中會顯示以協助使用者識別相關的檔案時標記的色彩。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-140">Keywords that were defined in Keyword lists will be displayed in colors to help the user identify relevant files while tagging.</span></span>
    
- <span data-ttu-id="2a6f7-141">**批次計算**： 已標記為 R/編號的專家將會收到 [0] 或 [100 分數的檔案。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-141">**Batch calculation**: Files that were tagged as R/NR by the expert will receive a score of either 0 or 100.</span></span> <span data-ttu-id="2a6f7-142">這適用於標記進行批次計算之前。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-142">This applies to tagging made before Batch calculation.</span></span> <span data-ttu-id="2a6f7-143">如果專家切換閒置批次計算後問題，並繼續標記這個問題，新標記的分數將無法 100/0，但而原始分數。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-143">If the expert switched the issue to Idle after Batch Calculation and continued tagging this issue, the newly tagged scores will not be 100/0 but rather the original score.</span></span>
    
- <span data-ttu-id="2a6f7-144">**問題和取樣模式**： 問題通常已關閉時於這些工作已完成 （穩定相關性訓練與執行批次計算） 時便會取消問題，或當另一位使用者工作的問題時。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-144">**Issues and sampling mode**: Issues are usually turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.</span></span>
    
## <a name="steps-in-relevance-training"></a><span data-ttu-id="2a6f7-145">在 [相關性訓練的步驟</span><span class="sxs-lookup"><span data-stu-id="2a6f7-145">Steps in Relevance training</span></span>

<span data-ttu-id="2a6f7-146">在**相關性\>追蹤**] 索引標籤，資料調查提供的建議如何繼續處理，使用下列的下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-146">In the **Relevance \> Track** tab, Data investigations provides recommendations on how to proceed in the processing, with the following next steps.</span></span> <span data-ttu-id="2a6f7-147">當相關性訓練程序中建議的每個以下的步驟如下所述所造成影響。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-147">The implications are described below when each of the following steps is recommended in the Relevance training process.</span></span> 
  
- <span data-ttu-id="2a6f7-148">標記 / 繼續標記： 檔案檢閱與相關性標記執行的最高]，為每個檔案並發出內範例。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-148">Tagging / Continue tagging: File review and Relevance tagging performed by an expert for each file and issue within a sample.</span></span>
    
  - <span data-ttu-id="2a6f7-149">Mincopiestoprotect 這個： 現有範例需要標記。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-149">Implication: An existing sample needs to be tagged.</span></span>
    
- <span data-ttu-id="2a6f7-150">評估 / 繼續進行評估： 可讓早期驗證案例問題相關性和匯入目前的大小寫檔案母群體的相關性的初步檢視。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-150">Assessment / Continue assessment: Enables early validation of case issue relevance and a preliminary view of the relevance of the file population imported for the current case.</span></span>
    
  - <span data-ttu-id="2a6f7-151">Mincopiestoprotect 這個： 多個評估需要或建議。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-151">Implication: More assessment is required or recommended.</span></span>
    
- <span data-ttu-id="2a6f7-152">訓練 / 繼續訓練： 程序期間哪些資料調查可學習從專家標記檔案範例和取得能夠識別相關性準則改變每個案例的內容中每一項問題。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-152">Training / Continue training: Process during which Data investigations learns from the expert who is tagging the file samples and acquires the ability to identify Relevance criteria pertinent to each issue within the context of each case.</span></span>
    
  - <span data-ttu-id="2a6f7-153">Mincopiestoprotect 這個： 問題需要更多的教育訓練;應建立及標記的下一個範例。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-153">Implication: The issue needs more training; the next sample should be created and tagged.</span></span> 
    
- <span data-ttu-id="2a6f7-154">批次計算： 相關性處理程序中的資料調查採用知識取得訓練階段期間，然後套用至整個檔案母體。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-154">Batch calculation: Relevance process in which Data investigations takes the knowledge acquired during the training stage and applies it to the entire file population.</span></span> <span data-ttu-id="2a6f7-155">相關檔案群組中的所有檔案都相關性評估，並指派相關性分數。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-155">All files in the pertinent file group are assessed for relevance and assigned a Relevance score.</span></span>
    
  - <span data-ttu-id="2a6f7-156">Mincopiestoprotect 這個： 穩定問題後，而且可以執行批次計算。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-156">Implication: The issue has stabilized, and Batch calculation can be performed.</span></span>
    
- <span data-ttu-id="2a6f7-157">Catch-up： 相關性指出專家檢閱，以及標記從其他檔案負載期間循環載入的案例中所選取的檔案的範例。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-157">Catch-up: Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Loads scenario.</span></span>
    
  - <span data-ttu-id="2a6f7-158">Mincopiestoprotect 這個： 已新增新的負載，且 Catch-up 需要繼續使用。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-158">Implication: A new load has been added, and Catch-up is required to continue working.</span></span>
    
- <span data-ttu-id="2a6f7-159">標記不一致： 程序識別，透過資料調查演算法，標記可能會造成負面影響分析的程序在檔案中的不一致。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-159">Tag inconsistencies: Process identifies, via an Data investigations algorithm, inconsistencies in the file tagging process that may negatively impact the analysis.</span></span>
    
  - <span data-ttu-id="2a6f7-160">Mincopiestoprotect 這個： 下一個範例會在前一個範例中，包括已標記的檔案，必須取消復原其標記。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-160">Implication: The next sample will include files that have been tagged in previous samples, and their tagging must be redone.</span></span>
    
- <span data-ttu-id="2a6f7-161">更新器： 可讓使用者套用標記或植入的變更。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-161">Update classifier: Allows the user to apply tagging or seeding changes.</span></span>
    
  - <span data-ttu-id="2a6f7-162">Mincopiestoprotect 這個： 標記及植入變更可套用而不需要以手動方式執行相關性的另一個範例。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-162">Implication: Tagging and seeding changes can be applied without needing to manually run another Relevance sample.</span></span>
    
- <span data-ttu-id="2a6f7-163">保留： 相關性訓練程序完成。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-163">On hold: The Relevance training process is completed.</span></span>
    
  - <span data-ttu-id="2a6f7-164">Mincopiestoprotect 這個： 沒有相關性訓練，則需要這個時候。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-164">Implication: No Relevance training is required at this point.</span></span>
    
<span data-ttu-id="2a6f7-165">雖然資料調查將引導您完成程序，以建議的後續步驟，在不同的階段，您還可以] 索引標籤和頁面之間瀏覽，並選擇地址情況可能會改變您個別的情況下，問題，或文件檢閱程序。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-165">Although Data investigations guides you through the process, with recommended Next steps at different stages, it also allows you to navigate between tabs and pages, and to make choices to address situations that may be pertinent to your individual case, issue, or document review process.</span></span> 
  
<span data-ttu-id="2a6f7-166">就可以接受或覆寫資料調查下一步處理選項。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-166">It is possible to accept or override Data investigations Next step processing choices.</span></span> <span data-ttu-id="2a6f7-167">如果您想要執行的步驟以外的建議的下一個步驟，請按一下 [**下一步**] 對話方塊中的擴充此問題： 顯示中所列，按一下 [下一步旁的 [**修改**] 按鈕並選取另一個下一步步驟選項。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-167">If you want to perform a step other than the recommended Next step, click the **Next step** listed in the expanded issue display in the dialog, click the **Modify** button next to the Next step, and select another Next step option.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2a6f7-168">某些選項可能都維持在已停用之後解除鎖定為不受支援之程序中使用點。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-168">Some options may remain disabled after unlocking as they are not supported for use at that point in the process.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="2a6f7-169">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="2a6f7-169">More information</span></span>

[<span data-ttu-id="2a6f7-170">了解相關性評估</span><span class="sxs-lookup"><span data-stu-id="2a6f7-170">Understanding Assessment in Relevance</span></span>](../assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2a6f7-171">標記與評估</span><span class="sxs-lookup"><span data-stu-id="2a6f7-171">Tagging and assessment</span></span>](../tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2a6f7-172">標記與相關性訓練</span><span class="sxs-lookup"><span data-stu-id="2a6f7-172">Tagging and Relevance training</span></span>](../tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2a6f7-173">追蹤相關性分析</span><span class="sxs-lookup"><span data-stu-id="2a6f7-173">Tracking Relevance analysis</span></span>](../track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2a6f7-174">決定根據結果</span><span class="sxs-lookup"><span data-stu-id="2a6f7-174">Deciding based on the results</span></span>](../decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2a6f7-175">測試相關性分析</span><span class="sxs-lookup"><span data-stu-id="2a6f7-175">Testing Relevance analysis</span></span>](../test-relevance-analysis-in-advanced-ediscovery.md)

[<span data-ttu-id="2a6f7-176">查詢中的辨識項的資料</span><span class="sxs-lookup"><span data-stu-id="2a6f7-176">Query the data in evidence</span></span>](evidence-query.md)
