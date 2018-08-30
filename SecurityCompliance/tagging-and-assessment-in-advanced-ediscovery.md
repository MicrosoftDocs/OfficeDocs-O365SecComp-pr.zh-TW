---
title: Office 365 進階電子文件探索中的標記與評估
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: b5c82de7-ed2f-4cc6-becd-db403faf4d18
description: '檢閱執行評估訓練，包括標記檔案、 和檢閱評估結果在 Office 365 進階 eDiscovery 的步驟。 '
ms.openlocfilehash: 0f67dd4780a29536888231f556c18fe887f230ba
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526622"
---
# <a name="tagging-and-assessment-in-office-365-advanced-ediscovery"></a><span data-ttu-id="23847-103">Office 365 進階電子文件探索中的標記與評估</span><span class="sxs-lookup"><span data-stu-id="23847-103">Tagging and Assessment in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="23847-p101">進階的 eDiscovery 需要您組織與進階規範附加元件或 E5 訂閱 Office 365 E3。如果您不具有該對應並想要嘗試進階的 eDiscovery，您還可以[註冊 Office 365 企業版 E5 的試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="23847-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="23847-106">本節中的 [進階的 eDiscovery 相關性評估模組的程序。</span><span class="sxs-lookup"><span data-stu-id="23847-106">This section describes the procedure for the Advanced eDiscovery Relevance Assessment module.</span></span> 
  
## <a name="performing-assessment-training-and-analysis"></a><span data-ttu-id="23847-107">執行評估訓練與分析</span><span class="sxs-lookup"><span data-stu-id="23847-107">Performing Assessment training and analysis</span></span>

1. <span data-ttu-id="23847-108">在**相關性\>追蹤**] 索引標籤中按一下 [啟動 case 評估的**評估**。</span><span class="sxs-lookup"><span data-stu-id="23847-108">In the **Relevance \> Track** tab, click **Assessment** to start case assessment.</span></span> 
    
    <span data-ttu-id="23847-109">例如範例評估的一組 500 檔案會建立在此程序的目的，並顯示 [**標籤**] 索引標籤，其中包含 [標記] 面板中、 顯示的檔案的內容及其他標記的選項。</span><span class="sxs-lookup"><span data-stu-id="23847-109">For example purposes in this procedure, a sample assessment set of 500 files is created and the **Tag** tab is displayed, which contains the Tagging panel, displayed file content and other tagging options.</span></span> 
    
    ![相關性標記評量的索引標籤](media/c8acf891-b1cd-4344-816c-eabb8cbbe742.png)
  
2. <span data-ttu-id="23847-111">檢閱範例中的每一個檔案、 決定每個案例的問題的檔案的相關性與標記不使用 Relevance (R) 檔案相關 （編號） 並略過按鈕**標記控制台]** 窗格中。</span><span class="sxs-lookup"><span data-stu-id="23847-111">Review each file in the sample, determine the file's relevance for each case issue, and tag the file using the Relevance (R), Not relevant (NR) and Skip buttons in the **Tagging panel** pane.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="23847-p102">評估需要 500 標記的檔案。如果"跳過檔案 」，您會收到標記的多個檔案。</span><span class="sxs-lookup"><span data-stu-id="23847-p102">Assessment requires 500 tagged files. If files are "skipped", you will receive more files to tag.</span></span> 
  
3. <span data-ttu-id="23847-114">之後標示所有檔案範例中的，按一下 [**計算**]。</span><span class="sxs-lookup"><span data-stu-id="23847-114">After tagging all files in the sample, click **Calculate**.</span></span> 
    
    <span data-ttu-id="23847-p103">評估目前的錯誤邊界與豐富計算並顯示 [**相關性追蹤**] 索引標籤的問題，個別的擴充詳細資料如下所示。此對話方塊的更多詳細說明 [更新] 區段中 「 檢閱評估結果 」。</span><span class="sxs-lookup"><span data-stu-id="23847-p103">The Assessment current error margin and richness are calculated and displayed in the **Relevance Track** tab, with expanded details per issue, as shown below. More details about this dialog are described in the later section "Reviewing Assessments results".</span></span> 
    
    ![相關性追蹤 - 評量](media/da911ba5-8678-40d6-9ad5-fd0b058355c1.png)
  
    > [!TIP]
    > <span data-ttu-id="23847-p104">根據預設，我們建議的您繼續預設下一個步驟完成評估進度列指示器問題之後，指出評估範例已經過檢閱並已標記的足夠相關的檔案。> 否則如果您想要檢視**追蹤**] 索引標籤結果與控制項邊界的錯誤與下一個步驟，按一下 [**修改**相鄰**下一步**]、 選取 [**繼續評估**，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="23847-p104">By default, we recommend that you proceed to the default Next step when the Assessment progress indicator for the issue has completed, indicating that the assessment sample was reviewed and sufficient relevant files were tagged. > Otherwise, if you want to view the **Track** tab results and control the margin of error and the next step, click **Modify** adjacent to **Next Step**, select **Continue assessment**, and then click **OK**.</span></span> 
  
1. <span data-ttu-id="23847-p105">按一下 [**修改**右邊的**評估**] 核取方塊來檢視及指定每個問題評估參數。每個問題**評估層級**] 對話方塊會顯示，如下列範例所示：</span><span class="sxs-lookup"><span data-stu-id="23847-p105">Click **Modify** to the right of the **Assessment** check box to view and specify assessment parameters per issue. An **Assessment level** dialog for each issue is displayed, as shown in the following example:</span></span> 
    
    ![評量層級案例問題](media/b7113fef-d125-4617-ae1b-c9eb0bf79aec.png)
  
    <span data-ttu-id="23847-123">下列參數的問題會計算並顯示**評估層級**] 對話方塊中：</span><span class="sxs-lookup"><span data-stu-id="23847-123">The following parameters for the issue are calculated and displayed in the **Assessment level** dialog:</span></span> 
    
    <span data-ttu-id="23847-p106">**目標錯誤邊界的重新叫用來估計**： 根據此值，可供檢閱所需的其他檔案的估計的數量的計算公式。用於重新叫用的邊界為大於 75%並且 95%信賴等級。</span><span class="sxs-lookup"><span data-stu-id="23847-p106">**Target error margin for recall estimates**: Based on this value, the estimated number of additional files necessary to review is calculated. The margin used for recall is greater than 75% and with a 95% confidence level.</span></span> 
    
    <span data-ttu-id="23847-126">**其他評估檔案所需**： 指出多少的多個檔案所需如果不符合目前的錯誤邊界需求。</span><span class="sxs-lookup"><span data-stu-id="23847-126">**Additional assessment files required**: Indicates how many more files are necessary if the current error margin's requirements have not been met.</span></span> 
    
2. <span data-ttu-id="23847-127">調整目前錯誤邊界，然後查看 （每個問題） 不同的錯誤邊界的影響：</span><span class="sxs-lookup"><span data-stu-id="23847-127">To adjust the current error margin and see the effect of different error margins (per issue):</span></span>
    
1. <span data-ttu-id="23847-128">在 [**選取問題**] 清單中選取 [問題]。</span><span class="sxs-lookup"><span data-stu-id="23847-128">In the **Select issue** list, select an issue.</span></span> 
    
2. <span data-ttu-id="23847-129">在**目標錯誤邊界的重新叫用來估計**，輸入新值。</span><span class="sxs-lookup"><span data-stu-id="23847-129">In **Target error margin for recall estimates**, enter a new value.</span></span>
    
3. <span data-ttu-id="23847-130">按一下 [**更新值**來查看調整的影響。</span><span class="sxs-lookup"><span data-stu-id="23847-130">Click **Update values** to see the impact of the adjustments.</span></span> 
    
3. <span data-ttu-id="23847-131">按一下 [**進階**] 在**評估層級**] 對話方塊中看到下列額外的參數和詳細資料：</span><span class="sxs-lookup"><span data-stu-id="23847-131">Click **Advanced** in the **Assessment level** dialog to see the following additional parameters and details:</span></span> 
    
    ![評量層級案例問題的進階檢視](media/577d7e0e-95df-48c2-9dec-bdeab5e801d8.png)
  
    <span data-ttu-id="23847-133">**估計豐富**： 預估豐富根據目前的評估結果</span><span class="sxs-lookup"><span data-stu-id="23847-133">**Estimated richness**: Estimated richness according to the current assessment results</span></span>
    
    <span data-ttu-id="23847-p107">**針對假定重新叫用**： 根據預設，目標錯誤邊界適用於重新叫用上方 75%。如果您想要變更此參數與控制的重新叫用值的不同範圍上的錯誤限度，請按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="23847-p107">**For assumed recall**: By default, the target error margin applies to recall above 75%. Click **Edit** if you want to change this parameter and control the margin of error on a different range of recall values.</span></span> 
    
    <span data-ttu-id="23847-p108">**信賴等級**： 根據預設，信賴的建議的錯誤邊界為 95%。如果您想要變更此參數，請按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="23847-p108">**Confidence level**: By default, the recommended error margin for confidence is 95%. Click **Edit** if you want to change this parameter.</span></span> 
    
    <span data-ttu-id="23847-138">**預期豐富錯誤邊界**： 授與更新的值，這是預期的邊界的豐富功能的錯誤之後會檢閱所有其他評估檔案。</span><span class="sxs-lookup"><span data-stu-id="23847-138">**Expected richness error margin**: Given the updated values, this is the expected margin of error of the richness, after all additional assessment files are reviewed.</span></span>
    
    <span data-ttu-id="23847-139">**其他評估檔案所需**： 授與更新的值，其他評估數目檔案該需要檢閱達到目標。</span><span class="sxs-lookup"><span data-stu-id="23847-139">**Additional assessment files required**: Given the updated values, the number of additional assessment files that need to be reviewed to reach the target.</span></span>
    
    <span data-ttu-id="23847-140">**總評估檔案所需**： 授與更新的值，總評估檔案所需的檢閱。</span><span class="sxs-lookup"><span data-stu-id="23847-140">**Total assessment files required**: Given the updated values, total assessment files required for review.</span></span>
    
    <span data-ttu-id="23847-141">**預期在評估相關的檔案數目**： 授與更新的值，預期在整個評定後檢閱所有其他評估檔案所相關的檔案數目。</span><span class="sxs-lookup"><span data-stu-id="23847-141">**Expected number of relevant files in assessment**: Given the updated values, the expected number of relevant files in the entire assessment after all additional assessment files are reviewed.</span></span>
    
4. <span data-ttu-id="23847-p109">按一下 [**重新計算的值**，如果變更參數。當您完成一個問題時，按一下 **[確定]** 儲存的變更 （或**下一個**要檢視或修改的多個問題時，然後**完成時間**）。</span><span class="sxs-lookup"><span data-stu-id="23847-p109">Click **Recalculate values**, if parameters are changed. When you are done, if there is one issue, click **OK** to save the changes (or **Next** when there are multiple issues to review or modify and then **Finish**).</span></span> 
    
    <span data-ttu-id="23847-144">如有多個問題之後已檢閱或調整，所有問題**評估層級： 摘要**] 對話方塊隨即出現，如下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="23847-144">When there are multiple issues, after all issues have been reviewed or adjusted, an **Assessment level: summary** dialog is displayed, as shown in the following example.</span></span> 
    
    ![評量層級摘要](media/4997b46d-10a5-4abc-b3b2-7b75a370eb9e.png)
  
    <span data-ttu-id="23847-146">評估在成功完成，請繼續進行相關性訓練的下一個階段。</span><span class="sxs-lookup"><span data-stu-id="23847-146">Upon successful completion of assessment, proceed to the next stage in Relevance training.</span></span>
    
## <a name="reviewing-assessment-results"></a><span data-ttu-id="23847-147">檢閱評估結果</span><span class="sxs-lookup"><span data-stu-id="23847-147">Reviewing assessment results</span></span>

<span data-ttu-id="23847-148">標記評估範例之後，評估結果所計算並顯示 [相關性追蹤] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="23847-148">After an Assessment sample is tagged, the assessment results are calculated and displayed in the Relevance Track tab.</span></span>
  
<span data-ttu-id="23847-149">以下結果會顯示在展開追蹤顯示：</span><span class="sxs-lookup"><span data-stu-id="23847-149">The following results are displayed in the expanded Track display:</span></span> 
  
- <span data-ttu-id="23847-150">評估目前錯誤邊界的重新叫用來估計</span><span class="sxs-lookup"><span data-stu-id="23847-150">Assessment current error margin for recall estimates</span></span>
    
- <span data-ttu-id="23847-151">估計的豐富</span><span class="sxs-lookup"><span data-stu-id="23847-151">Estimated richness</span></span>
    
- <span data-ttu-id="23847-152">其他評估所需檔案 （請檢閱）</span><span class="sxs-lookup"><span data-stu-id="23847-152">Additional assessment files required (for review)</span></span>
    
<span data-ttu-id="23847-p110">評估目前錯誤邊界是建議的進階 eDiscovery 的錯誤邊界。"其他評估所需的檔案 」 所顯示的數字對應至該建議。</span><span class="sxs-lookup"><span data-stu-id="23847-p110">The Assessment current error margin is the error margin recommended by Advanced eDiscovery. The number displayed for the "Additional assessment files required" corresponds to that recommendation.</span></span>
  
<span data-ttu-id="23847-p111">評估進度列指示器會顯示完成評估授與目前的錯誤邊界的程度。時評估技巧，使用者將會標記另一個評估範例。</span><span class="sxs-lookup"><span data-stu-id="23847-p111">The Assessment progress indicator shows the level of completion of the assessment, given the current error margin. When assessment is underway, the user will tag another assessment sample.</span></span>
  
<span data-ttu-id="23847-157">時評估進度列指示器會顯示為完成評估，這表示已完成評估範例檢閱並已標記的足夠相關的檔案。</span><span class="sxs-lookup"><span data-stu-id="23847-157">When the assessment progress indicator shows assessment as complete, that means the assessment sample review was completed and sufficient relevant files were tagged.</span></span> 
  
<span data-ttu-id="23847-158">延伸的追蹤顯示顯示建議的下一個步驟、 評估統計資料和存取詳細結果。</span><span class="sxs-lookup"><span data-stu-id="23847-158">The expanded Track display shows the recommended next step, the assessment statistics, and access to detailed results.</span></span>
  
<span data-ttu-id="23847-p112">豐富相當低時，以達到最少產生很有用的統計資料相關的檔案數目所需的其他評估檔數目是非常高。進階的 eDiscovery 然後會建議將移至訓練。評估進度列指示器會有陰影，而且會提供任何統計資料。</span><span class="sxs-lookup"><span data-stu-id="23847-p112">When richness is very low, the number of additional assessment files needed to reach a minimal number of relevant files to produce useful statistics is very high. Advanced eDiscovery will then recommend moving on to training. The assessment progress indicator will be shaded, and no statistics will be available.</span></span> 
  
<span data-ttu-id="23847-p113">如果沒有統計根據穩定、 會結果的正確性與信賴等級的較低層級。不過，這些結果可用來尋找相關的檔案時不需要知道找到相關檔案的百分比。同樣地，此狀態可用來與低豐富訓練問題相關性分數其中加速存取相關的特定問題的檔案。</span><span class="sxs-lookup"><span data-stu-id="23847-p113">In the absence of statistically based stabilization, there will be results with a lower level of accuracy and confidence level. However, these results can be used to find relevant files when you do not need to know the percentage of relevant files found. Similarly, this status can be used to train issues with low richness, where Relevance scores can accelerate access to files relevant to a specific issue.</span></span>
  
> [!TIP]
> <span data-ttu-id="23847-p114">在**相關性\>追蹤**] 索引標籤顯示延伸的問題、 下列檢視選項可： > 建議的下一個步驟，例如**下一步： 標記**可以按一下 [**修改**] 按鈕略過 （每個問題） 及其向右，並再**下一個步驟**中選取不同的步驟。尚未完成評估進度列指示器，評估將下一個建議您選擇、 標記詳細評估檔案及增加的統計資料的正確性。> 您可以變更錯誤邊界並依序按一下 [**修改**] 並**評估層級] 對話方塊**，變更**目標錯誤邊界的重新叫用來估計**，然後按一下 [**更新值**評估它的影響。此外，此對話方塊中，您可以檢視進階的選項]，依序按一下 [**進階]**。> 您可以按一下 [**檢視**來檢視其他評估層級的統計資料和其影響。在 [顯示詳細資料結果] 對話方塊的統計資料可用個別問題有至少 500 標記的評估檔案和至少 18 檔案標示為相關問題時。</span><span class="sxs-lookup"><span data-stu-id="23847-p114">In the **Relevance \> Track** tab, expanded issue display, the following viewing options are available: > The recommended next step, such as **Next step: Tagging** can be bypassed (per issue) by clicking the **Modify** button to its right, and then selecting an different step in the **Next step**. When the assessment progress indicator has not completed, assessment will be the next recommended option, to tag more assessment files and increase statistics accuracy. > You can change the error margin and assess its impact, by clicking **Modify**, and in the **Assessment level dialog**, changing the **Target error margin for recall estimates**, and clicking **Update values**. Also, in this dialog, you can view advanced options, by clicking **Advanced**. > You can view additional assessment level statistics and their impact by clicking **View**. In the displayed Detail results dialog, statistics are available per issue, when there are at least 500 tagged assessment files and at least 18 files are tagged as Relevant for the issue.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="23847-171">另請參閱</span><span class="sxs-lookup"><span data-stu-id="23847-171">See also</span></span>

[<span data-ttu-id="23847-172">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="23847-172">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="23847-173">了解評估的相關性</span><span class="sxs-lookup"><span data-stu-id="23847-173">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="23847-174">標記及相關性訓練</span><span class="sxs-lookup"><span data-stu-id="23847-174">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="23847-175">追蹤相關性分析</span><span class="sxs-lookup"><span data-stu-id="23847-175">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="23847-176">決定所得的結果</span><span class="sxs-lookup"><span data-stu-id="23847-176">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="23847-177">測試相關性分析</span><span class="sxs-lookup"><span data-stu-id="23847-177">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

