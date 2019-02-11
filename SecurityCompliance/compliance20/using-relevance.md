---
title: 使用 [相關性] 模組來分析進階 eDiscovery (Preview) 中的資料
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 56e83a1f8a951fd6e14172122a5e86447c6f2ccf
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2019
ms.locfileid: "29695169"
---
# <a name="use-the-relevance-module-to-analyze-data-in-advanced-ediscovery-preview"></a><span data-ttu-id="6948e-102">使用 [相關性] 模組來分析進階 eDiscovery (Preview) 中的資料</span><span class="sxs-lookup"><span data-stu-id="6948e-102">Use the Relevance module to analyze data in Advanced eDiscovery (Preview)</span></span>

<span data-ttu-id="6948e-p101">進階 eDiscovery (Preview) 中 [相關性] 模組包含相關性訓練及檔案與案例相關的檢閱。相關性工作流程會顯示及說明如下：</span><span class="sxs-lookup"><span data-stu-id="6948e-p101">In Advanced eDiscovery (Preview), the Relevance module includes the Relevance training and review of files related to a case. The Relevance workflow is shown and described as follows:</span></span>
  
![相關性工作流程](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- <span data-ttu-id="6948e-106">**評估和追蹤週期**：</span><span class="sxs-lookup"><span data-stu-id="6948e-106">**Cycles of assessment and tracking**:</span></span>
    
  - <span data-ttu-id="6948e-107">**評估**： 可讓檔案的隨機樣本為基礎的最早評估，並使用此評估適用於決定預測的編碼程序的效能的決策。</span><span class="sxs-lookup"><span data-stu-id="6948e-107">**Assessment**: Enables early assessment based on a random sample of files and uses this assessment to apply decisions to determine the performance of the predictive coding process.</span></span> 
    
  - <span data-ttu-id="6948e-108">**追蹤**： 計算與顯示中期時監控的程序的統計有效性評估結果。</span><span class="sxs-lookup"><span data-stu-id="6948e-108">**Track**: Calculate and display interim results of the assessment while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="6948e-109">**循環的訓練及追蹤**</span><span class="sxs-lookup"><span data-stu-id="6948e-109">**Cycles of training and tracking**</span></span>
    
  - <span data-ttu-id="6948e-110">**Tag**： 進階的 eDiscovery （預覽） 可學習相關性準則特定根據專家反覆檢閱每個問題和標記的個別的檔案。</span><span class="sxs-lookup"><span data-stu-id="6948e-110">**Tag**: Advanced eDiscovery (Preview) learns Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span></span>
    
  - <span data-ttu-id="6948e-111">**追蹤**： 計算並顯示中期結果的相關性訓練時監視統計程序的有效性。</span><span class="sxs-lookup"><span data-stu-id="6948e-111">**Track**: Calculate and display interim results of the Relevance training while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="6948e-112">**批次計算**： 累積和學相關性準則會套用至整個檔案集合，並相關性分數會產生每個檔案。</span><span class="sxs-lookup"><span data-stu-id="6948e-112">**Batch calculation**: The accumulated and learned Relevance criteria is applied to the entire file collection, and a Relevance score is generated for each file.</span></span>
    
- <span data-ttu-id="6948e-113">**決定**： 批次計算後顯示套用至整個案例分析的結果並顯示用來決定文件檢閱的資料。</span><span class="sxs-lookup"><span data-stu-id="6948e-113">**Decide**: The results of the analysis applied to the entire case is displayed after Batch calculation, and data used to make document review decisions is displayed.</span></span>
    
- <span data-ttu-id="6948e-114">**測試**： 若要確認的有效性和進階的 eDiscovery （預覽） 處理效能就可以測試結果。</span><span class="sxs-lookup"><span data-stu-id="6948e-114">**Test**: Results can be tested to verify the validity and effectiveness of the Advanced eDiscovery (Preview) processing.</span></span>

- <span data-ttu-id="6948e-115">**搜尋**： 相關性工作流程完成後，您可以使用如讀取百分位數的文件的輸出問題的工作集內執行查詢時。</span><span class="sxs-lookup"><span data-stu-id="6948e-115">**Search**: Once the Relevance workflow is complete, you can use the output such as read percentile of a document for your issue when you run a query within your working set.</span></span>
    
## <a name="guidelines-for-relevance-training-and-review"></a><span data-ttu-id="6948e-116">相關性訓練及檢閱的指導方針</span><span class="sxs-lookup"><span data-stu-id="6948e-116">Guidelines for Relevance training and review</span></span>

<span data-ttu-id="6948e-117">以下是概觀相關性訓練及檢閱的指導方針：</span><span class="sxs-lookup"><span data-stu-id="6948e-117">Following is an overview of guidelines for Relevance training and review:</span></span>
  
- <span data-ttu-id="6948e-p102">**錯誤與不一致處**： 如果標記錯誤進行訓練期間，傳回更正它們的舊檔案範例。若有太多錯誤修正或沒有大小寫或問題的新觀點來看，相關性準則會應該重新定義系統管理員，並重新啟動相關性訓練。</span><span class="sxs-lookup"><span data-stu-id="6948e-p102">**Errors and inconsistencies**: If tagging errors are made during training, return to previous file samples to correct them. If there are too many errors to correct or there is a new perspective of the case or issue, the Relevance criteria should be redefined by the Administrator, and the Relevance training restarted.</span></span>
    
- <span data-ttu-id="6948e-120">**標記及訓練**：</span><span class="sxs-lookup"><span data-stu-id="6948e-120">**Tagging and training**:</span></span> 
    
  - <span data-ttu-id="6948e-p103">檔案應該根據內容僅限標記。不考慮中繼資料，例如 okay、 日期或檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="6948e-p103">Files should be tagged based on content only. Do not consider metadata, such as custodian, date, or file path.</span></span> 
    
  - <span data-ttu-id="6948e-123">不需考量的日期範圍表示文字中的標記檔案。</span><span class="sxs-lookup"><span data-stu-id="6948e-123">Do not consider date range indications in the text when tagging files.</span></span>
    
  - <span data-ttu-id="6948e-124">標記檔案時，請勿考量內嵌圖形的圖像。</span><span class="sxs-lookup"><span data-stu-id="6948e-124">Do not consider embedded graphical images when tagging files.</span></span>
     
  - <span data-ttu-id="6948e-p104">搜尋時忽略文字檢視中顯示的檔案內容中的相關性移除套用至相關的文字。如果忽略文字值已定義相關性訓練已經開始之後，新已忽略的文字會套用至從它所定義的點所建立的範例檔案。其使用可能會降低效能的檔案分析搜尋時忽略文字功能也應該謹慎、 使用</span><span class="sxs-lookup"><span data-stu-id="6948e-p104">Ignore text applied to Relevance will be removed in the displayed file content in the text view in Relevance. If the values for Ignore text were defined after Relevance training already started, the new ignored text will be applied to sample files created from the point in which it was defined. The Ignore Text feature should be used cautiously, as its use may reduce the performance of file analysis</span></span>
    
  - <span data-ttu-id="6948e-p105">使用 [**略過 [標記**] 選項只有在必要時。略過的檔案上進階的 eDiscovery （預覽） 不會不訓練根據。在評估，如果很難辨別檔案是有關最好是標記為 Relevant (R) 或不相關 （編號） 只要可行而不是選取**略過**。當進階的 eDiscovery （預覽） 評估訓練時，然後才能看到它方式以及處理這些類型的檔案。</span><span class="sxs-lookup"><span data-stu-id="6948e-p105">Use the **Skip tagging** option only when necessary. Advanced eDiscovery (Preview) does not train based on skipped files. In assessment, if it's hard to tell whether a file is relevant, it is better to tag as Relevant (R) or Not relevant (NR) whenever possible rather than selecting **Skip**. When Advanced eDiscovery (Preview) evaluates training, it can then be seen how well these types of files were processed.</span></span>
    
  - <span data-ttu-id="6948e-132">偶數檔案解壓縮文字非常小數量應該訓練 R/編號，而非"略過"，儘可能在標記。</span><span class="sxs-lookup"><span data-stu-id="6948e-132">Even files with a very small amount of extracted text should be tagged in training as R/NR, rather than as "Skip", when possible.</span></span> 
    
  - <span data-ttu-id="6948e-133">標記可能會影響類別器，只要檔案是可讀和可以標記為 R/編號。</span><span class="sxs-lookup"><span data-stu-id="6948e-133">Tagging can impact the classifier as long as the file is readable and can be tagged as R/NR.</span></span>
    
  - <span data-ttu-id="6948e-134">檔案序號上顯示的範例檔案清單 [**標籤**] 索引標籤可讓使用者返回原始檔的顯示順序。</span><span class="sxs-lookup"><span data-stu-id="6948e-134">The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files.</span></span> 
    
  - <span data-ttu-id="6948e-p106">您可以回到任何範例變更評估的標記和訓練設定檔。當建立下一個範例會套用所做的變更。</span><span class="sxs-lookup"><span data-stu-id="6948e-p106">You can go back to any sample and change the tagging of the assessment and training set files. The changes will be applied when creating the next sample.</span></span>
    
  - <span data-ttu-id="6948e-137">掃描的 Excel 檔案以 PDF 格式應視為相同原生的 Excel 檔案時標記檔案。</span><span class="sxs-lookup"><span data-stu-id="6948e-137">Scanned Excel files in PDF format should be treated the same as native Excel files when tagging files.</span></span>
    
  - <span data-ttu-id="6948e-p107">在 [相關檔案相關性標記有疑問，請洽詢專家。不正確標記相關性訓練期間可能會導致遺失稍後的程序的時間和品質的整體結果上也可能會造成負面影響。</span><span class="sxs-lookup"><span data-stu-id="6948e-p107">When in doubt regarding the Relevance tagging of a file, consult an expert. Incorrect tagging during the Relevance training can lead to lost time later in the process and may also have a negative impact on the quality of the overall results.</span></span>
    
  - <span data-ttu-id="6948e-140">已定義的關鍵字的關鍵字清單將會顯示在可協助使用者識別相關的檔案時標記的色彩。</span><span class="sxs-lookup"><span data-stu-id="6948e-140">Keywords that were defined in Keyword lists will be displayed in colors to help the user identify relevant files while tagging.</span></span>
    
- <span data-ttu-id="6948e-p108">**批次計算**： 已標記為 R/編號專家會收到 0 或 100 分數的檔案。這適用於標記之前批次計算。如果專家切換到閒置的問題之後批次計算並繼續標記這個問題，新標記的分數將無法 100/0 但而是原始分數。</span><span class="sxs-lookup"><span data-stu-id="6948e-p108">**Batch calculation**: Files that were tagged as R/NR by the expert will receive a score of either 0 or 100. This applies to tagging made before Batch calculation. If the expert switched the issue to Idle after Batch Calculation and continued tagging this issue, the newly tagged scores will not be 100/0 but rather the original score.</span></span>
    
- <span data-ttu-id="6948e-144">**問題和取樣模式**： 問題通常是已關閉時將這些工作已完成 （穩定相關性訓練與執行批次計算） 的問題會取消時，或另一位使用者在問題的處理時。</span><span class="sxs-lookup"><span data-stu-id="6948e-144">**Issues and sampling mode**: Issues are usually turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.</span></span>
    
## <a name="steps-in-relevance-training"></a><span data-ttu-id="6948e-145">相關性訓練中的步驟</span><span class="sxs-lookup"><span data-stu-id="6948e-145">Steps in Relevance training</span></span>

<span data-ttu-id="6948e-p109">在**相關性\>追蹤**] 索引標籤進階的 eDiscovery 提供建議如何處理，使用下列的下一個步驟中繼續執行。當相關性訓練程序中建議的每個以下的步驟如下所述隱含意義。</span><span class="sxs-lookup"><span data-stu-id="6948e-p109">In the **Relevance \> Track** tab, Advanced eDiscovery provides recommendations on how to proceed in the processing, with the following next steps. The implications are described below when each of the following steps is recommended in the Relevance training process.</span></span> 
  
- <span data-ttu-id="6948e-148">標記的標記 /continue： 檔案檢閱及相關性標記執行每個專家檔案和問題內範例。</span><span class="sxs-lookup"><span data-stu-id="6948e-148">Tagging / Continue tagging: File review and Relevance tagging performed by an expert for each file and issue within a sample.</span></span>
    
  - <span data-ttu-id="6948e-149">連帶： 現有範例需要標記。</span><span class="sxs-lookup"><span data-stu-id="6948e-149">Implication: An existing sample needs to be tagged.</span></span>
    
- <span data-ttu-id="6948e-150">評估程式繼續評估： 可讓 case 問題相關性的最早驗證和匯入目前的大小寫檔案母群體的相關性的初步檢視。</span><span class="sxs-lookup"><span data-stu-id="6948e-150">Assessment / Continue assessment: Enables early validation of case issue relevance and a preliminary view of the relevance of the file population imported for the current case.</span></span>
    
  - <span data-ttu-id="6948e-151">連帶： 詳細評估是必要或建議。</span><span class="sxs-lookup"><span data-stu-id="6948e-151">Implication: More assessment is required or recommended.</span></span>
    
- <span data-ttu-id="6948e-152">訓練 /continue 訓練： 程序期間的進階 eDiscovery 可學習向已標記檔案專家範例 （英文） 和取得能夠識別相關性準則與每個案例的內容中每個問題。</span><span class="sxs-lookup"><span data-stu-id="6948e-152">Training / Continue training: Process during which Advanced eDiscovery learns from the expert who is tagging the file samples and acquires the ability to identify Relevance criteria pertinent to each issue within the context of each case.</span></span>
    
  - <span data-ttu-id="6948e-153">連帶： 問題需要更多訓練;應建立及標記的下一個範例。</span><span class="sxs-lookup"><span data-stu-id="6948e-153">Implication: The issue needs more training; the next sample should be created and tagged.</span></span> 
    
- <span data-ttu-id="6948e-p110">批次計算： 相關性處理程序中的進階 eDiscovery 採用取得訓練階段的知識與套用至整個檔案母體。與檔案群組中的所有檔案所評估的相關性與指派相關性分數。</span><span class="sxs-lookup"><span data-stu-id="6948e-p110">Batch calculation: Relevance process in which Advanced eDiscovery takes the knowledge acquired during the training stage and applies it to the entire file population. All files in the pertinent file group are assessed for relevance and assigned a Relevance score.</span></span>
    
  - <span data-ttu-id="6948e-156">連帶： 穩定問題後，且可以執行批次計算。</span><span class="sxs-lookup"><span data-stu-id="6948e-156">Implication: The issue has stabilized, and Batch calculation can be performed.</span></span>
    
- <span data-ttu-id="6948e-157">Catch-up： 相關性會指出當專家檢閱及 tags 期間啟用載入的案例中選取 [從其他檔案載入的檔案的範例。</span><span class="sxs-lookup"><span data-stu-id="6948e-157">Catch-up: Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Loads scenario.</span></span>
    
  - <span data-ttu-id="6948e-158">連帶： 已新增新的負載，並 Catch-up，才能繼續進行工作。</span><span class="sxs-lookup"><span data-stu-id="6948e-158">Implication: A new load has been added, and Catch-up is required to continue working.</span></span>
    
- <span data-ttu-id="6948e-159">標記不一致處： 處理程序識別，透過進階的 eDiscovery 演算法檔案標記可能會造成負面影響分析的程序中的不一致。</span><span class="sxs-lookup"><span data-stu-id="6948e-159">Tag inconsistencies: Process identifies, via an Advanced eDiscovery algorithm, inconsistencies in the file tagging process that may negatively impact the analysis.</span></span>
    
  - <span data-ttu-id="6948e-160">連帶： 下一個範例將會包含已標記的檔案上一個範例中，必須取消復原其標記。</span><span class="sxs-lookup"><span data-stu-id="6948e-160">Implication: The next sample will include files that have been tagged in previous samples, and their tagging must be redone.</span></span>
    
- <span data-ttu-id="6948e-161">更新類別器： 可讓使用者套用標記或植入變更。</span><span class="sxs-lookup"><span data-stu-id="6948e-161">Update classifier: Allows the user to apply tagging or seeding changes.</span></span>
    
  - <span data-ttu-id="6948e-162">連帶： 標記及植入的變更而不需要以手動方式執行其他相關性範例可套用。</span><span class="sxs-lookup"><span data-stu-id="6948e-162">Implication: Tagging and seeding changes can be applied without needing to manually run another Relevance sample.</span></span>
    
- <span data-ttu-id="6948e-163">保留： 完成相關性訓練程序。</span><span class="sxs-lookup"><span data-stu-id="6948e-163">On hold: The Relevance training process is completed.</span></span>
    
  - <span data-ttu-id="6948e-164">連帶： 無相關性訓練，則需要此時。</span><span class="sxs-lookup"><span data-stu-id="6948e-164">Implication: No Relevance training is required at this point.</span></span>
    
<span data-ttu-id="6948e-165">雖然進階的 eDiscovery 引導您完成之程序與建議下一個步驟的不同階段，它也可讓您瀏覽] 索引標籤和頁面、 之間及選項對位址情況可能會改變在個別的案例 issue 功能或文件檢閱程序。</span><span class="sxs-lookup"><span data-stu-id="6948e-165">Although Advanced eDiscovery guides you through the process, with recommended Next steps at different stages, it also allows you to navigate between tabs and pages, and to make choices to address situations that may be pertinent to your individual case, issue, or document review process.</span></span> 
  
<span data-ttu-id="6948e-p111">有可能接受或覆寫進階的 eDiscovery 處理選擇的下一個步驟。如果您想要執行不建議的下一步步驟、 按一下 [**下一個步驟**中擴充的問題顯示在對話方塊中所列、 按一下 [下一步，旁邊的 [**修改**] 按鈕並選取另一個下一個步驟選項。</span><span class="sxs-lookup"><span data-stu-id="6948e-p111">It is possible to accept or override Advanced eDiscovery Next step processing choices. If you want to perform a step other than the recommended Next step, click the **Next step** listed in the expanded issue display in the dialog, click the **Modify** button next to the Next step, and select another Next step option.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6948e-168">某些選項可能都維持停用之後解除鎖定為不支援以用於在那個時候處理程序。</span><span class="sxs-lookup"><span data-stu-id="6948e-168">Some options may remain disabled after unlocking as they are not supported for use at that point in the process.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="6948e-169">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="6948e-169">More information</span></span>

[<span data-ttu-id="6948e-170">了解評估的相關性</span><span class="sxs-lookup"><span data-stu-id="6948e-170">Understanding Assessment in Relevance</span></span>](../assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="6948e-171">標記及評估</span><span class="sxs-lookup"><span data-stu-id="6948e-171">Tagging and Assessment</span></span>](../tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="6948e-172">標記及相關性訓練</span><span class="sxs-lookup"><span data-stu-id="6948e-172">Tagging and Relevance training</span></span>](../tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="6948e-173">追蹤相關性分析</span><span class="sxs-lookup"><span data-stu-id="6948e-173">Tracking Relevance analysis</span></span>](../track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="6948e-174">決定所得的結果</span><span class="sxs-lookup"><span data-stu-id="6948e-174">Deciding based on the results</span></span>](../decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="6948e-175">測試相關性分析</span><span class="sxs-lookup"><span data-stu-id="6948e-175">Testing Relevance analysis</span></span>](../test-relevance-analysis-in-advanced-ediscovery.md)

[<span data-ttu-id="6948e-176">查詢內工作集</span><span class="sxs-lookup"><span data-stu-id="6948e-176">Query within working set</span></span>](working-set-search.md)
