---
title: Office 365 進階電子文件探索中的測試相關性分析
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
description: '了解如何使用 Office 365 進階在 eDiscovery 中的批次計算後的 [測試] 索引標籤來測試、 比較和驗證處理的整體品質。  '
ms.openlocfilehash: 735a6d8088b4696e2ebc348db435a11914bd0b10
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215833"
---
# <a name="test-relevance-analysis-in-office-365-advanced-ediscovery"></a><span data-ttu-id="bbfb3-103">Office 365 進階電子文件探索中的測試相關性分析</span><span class="sxs-lookup"><span data-stu-id="bbfb3-103">Test Relevance analysis in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="bbfb3-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="bbfb3-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="bbfb3-p102">進階在 eDiscovery 中的 [測試] 索引標籤可讓您測試、 比較和驗證處理的整體品質。這些測試是批次計算後執行。由標記集合中的檔案、 專家進行最終的判斷關於是否已標記的每一個檔案實際案例相關。</span><span class="sxs-lookup"><span data-stu-id="bbfb3-p102">The Test tab in Advanced eDiscovery enables you to test, compare, and validate the overall quality of processing. These tests are performed after Batch calculation. By tagging the files in the collection, an expert makes the final judgment about whether each tagged file is actually relevant to the case.</span></span> 
  
<span data-ttu-id="bbfb3-p103">在單一與多問題的情況下，測試通常會執行每個問題。每個測試後可檢視結果並測試結果可以已修訂與指定之的範例測試檔案。</span><span class="sxs-lookup"><span data-stu-id="bbfb3-p103">In single and multiple-issue scenarios, tests are typically performed per issue. Results can be viewed after each test, and test results can be reworked with specified sample test files.</span></span>
  
## <a name="testing-the-rest"></a><span data-ttu-id="bbfb3-111">測試其餘部分</span><span class="sxs-lookup"><span data-stu-id="bbfb3-111">Testing the rest</span></span>

<span data-ttu-id="bbfb3-p104">"測試 Rest"測試用來驗證挑選出決策，例如、 檢閱上方最後一個進階的 eDiscovery 結果為基礎的特定相關性截止分數的檔案。專家檢閱下用來評估在該集相關的檔案數目的選定截止分數檔案的範例。</span><span class="sxs-lookup"><span data-stu-id="bbfb3-p104">The "Test the Rest" test is used to validate culling decisions, for example, to review only files above a specific Relevance cutoff score based on the final Advanced eDiscovery results. The expert reviews a sample of files under a selected cutoff score to evaluate the number of relevant files within that set.</span></span>
  
<span data-ttu-id="bbfb3-p105">這項測試會提供統計資料和檢閱設定及測試的比較 Rest 母體。檢閱一組的結果是指由相關性計算期間訓練。結果包含計算、 根據的設定與輸入的參數，例如：</span><span class="sxs-lookup"><span data-stu-id="bbfb3-p105">This test provides statistics and a comparison between the Review set and the Test the Rest population. The results of the review set are those calculated by Relevance during Training. The results include calculations , based on settings and input parameters, such as:</span></span>
  
- <span data-ttu-id="bbfb3-117">測試範例的檔案數目的統計資料的範例及識別相關的檔案。</span><span class="sxs-lookup"><span data-stu-id="bbfb3-117">Test sample statistics of the number of files in a sample and identified relevant files.</span></span> 
    
- <span data-ttu-id="bbfb3-p106">檢閱設定與其餘部分，例如檔案數目的母體參數的表格式比較估計數目相關的檔案、 估計的豐富及尋找其他相關檔案的平均成本。成本設定可以由系統管理員設定的參數。</span><span class="sxs-lookup"><span data-stu-id="bbfb3-p106">Tabular comparison of the Population parameters of the Review set and the Rest, for example, the number of files, estimated number of relevant files, estimated richness, and the average cost of finding an additional relevant file. Cost parameter settings can be set by the administrator.</span></span>
    
1. <span data-ttu-id="bbfb3-120">開啟**相關性\>測試**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="bbfb3-120">Open the **Relevance \> Test** tab.</span></span> 
    
2. <span data-ttu-id="bbfb3-p107">在 [**測試**] 索引標籤中按一下 [**新增測試**。**建立測試**] 對話方塊隨即出現，如下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="bbfb3-p107">In the **Test** tab, click **New test**. The **Create test** dialog is displayed, as shown in the following example.</span></span> 
    
    ![相關性測試的其他結果](media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. <span data-ttu-id="bbfb3-124">**測試名稱**與**描述**] 中輸入名稱與描述。</span><span class="sxs-lookup"><span data-stu-id="bbfb3-124">In **Test name**, and **Description**, type the name and description.</span></span>
    
4. <span data-ttu-id="bbfb3-125">在 [**測試類型**] 清單中選取 [**測試其餘部分**</span><span class="sxs-lookup"><span data-stu-id="bbfb3-125">In the **Test type** list, select **Test the Rest**</span></span>
    
5. <span data-ttu-id="bbfb3-126">在**問題 / 類別**清單中，選取問題名稱。</span><span class="sxs-lookup"><span data-stu-id="bbfb3-126">In the **Issue / Category** list, select the issue name.</span></span> 
    
6. <span data-ttu-id="bbfb3-127">在**載入**] 清單中，選取負載。</span><span class="sxs-lookup"><span data-stu-id="bbfb3-127">In the **Load** list, select the load.</span></span> 
    
7. <span data-ttu-id="bbfb3-128">在**讀取 %**、 接受預設值或選取截止相關性分數的值。</span><span class="sxs-lookup"><span data-stu-id="bbfb3-128">In **Read %**, accept the default value or select a value for the cutoff Relevance score.</span></span> 
    
8. <span data-ttu-id="bbfb3-p108">在**設定大小**，或接受預設值。請注意還原圖示會還原預設值。</span><span class="sxs-lookup"><span data-stu-id="bbfb3-p108">In **Set size**, or accept the default value. Note that the restore icons will restore the default values.</span></span>
    
9. <span data-ttu-id="bbfb3-p109">按一下 [**啟動標記**。產生測試範例。</span><span class="sxs-lookup"><span data-stu-id="bbfb3-p109">Click **Start tagging**. A test sample is generated.</span></span>
    
10. <span data-ttu-id="bbfb3-133">檢閱及標籤的檔案] 中的每個**相關性\>標籤**] 索引標籤和完成時，按一下 [**計算**。</span><span class="sxs-lookup"><span data-stu-id="bbfb3-133">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>
    
11. <span data-ttu-id="bbfb3-p110">在 [測試] 索引標籤中，您可以按一下 [**檢視結果**查看測試結果。下圖顯示範例。</span><span class="sxs-lookup"><span data-stu-id="bbfb3-p110">In the Test tab, you can click **View results** to see the test results. An example is shown in the following figure.</span></span> 
    
    ![測試其他結果](media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
<span data-ttu-id="bbfb3-137">在如上圖**範例參數**] 區段中的表格包含標記的專家，範例中的檔案數目及相關的範例中找到的檔案數目的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="bbfb3-137">In the figure above, the **Sample parameters** section of the table contains details about the number of files in the sample tagged by the expert, and the number of relevant files found in that sample.</span></span> 
  
<span data-ttu-id="bbfb3-p111">[**母體參數**] 區段中的表格包含的測試結果，包括檢閱組母體具有所選截止下方的分數檔案和"Rest"母群體的檔案與所選截止上方的分數。針對每個母群體，會顯示下列結果：</span><span class="sxs-lookup"><span data-stu-id="bbfb3-p111">The **Population parameters** section of the table contains the test results, including the Review set population of files with a score below the selected cutoff and "The Rest" population of files with a score above the selected cutoff. For each population, the following results are displayed:</span></span> 
  
- <span data-ttu-id="bbfb3-140">包含具有讀取 %-所述的截止檔案</span><span class="sxs-lookup"><span data-stu-id="bbfb3-140">Includes files with read % - Stated cutoff</span></span>
    
- <span data-ttu-id="bbfb3-141">檔案總數</span><span class="sxs-lookup"><span data-stu-id="bbfb3-141">The total number of files</span></span> 
    
- <span data-ttu-id="bbfb3-142">估計的相關的檔案數目</span><span class="sxs-lookup"><span data-stu-id="bbfb3-142">The estimated number of relevant files</span></span> 
    
- <span data-ttu-id="bbfb3-143">估計的豐富</span><span class="sxs-lookup"><span data-stu-id="bbfb3-143">The estimated richness</span></span> 
    
- <span data-ttu-id="bbfb3-144">平均檢閱總成本的尋找其他相關檔案</span><span class="sxs-lookup"><span data-stu-id="bbfb3-144">The average review cost of finding another relevant file</span></span>
    
## <a name="testing-the-slice"></a><span data-ttu-id="bbfb3-145">測試扇形</span><span class="sxs-lookup"><span data-stu-id="bbfb3-145">Testing the slice</span></span>

<span data-ttu-id="bbfb3-146">「 測試扇形"測試執行測試類似"測試其餘"測試，但為檔案的區段設定相關性讀取 %所指定。</span><span class="sxs-lookup"><span data-stu-id="bbfb3-146">The "Test the Slice" test performs testing similar to the "Test the Rest" test, but to a segment of the file set as specified by Relevance Read %.</span></span>
  
1. <span data-ttu-id="bbfb3-147">開啟**相關性\>測試**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="bbfb3-147">Open the **Relevance \> Test** tab.</span></span> 
    
2. <span data-ttu-id="bbfb3-p112">在 [**測試**] 索引標籤中按一下 [**新增測試**。**建立測試**對話方塊會顯示。</span><span class="sxs-lookup"><span data-stu-id="bbfb3-p112">In the **Test** tab, click **New test**. The **Create test** dialog is displayed.</span></span> 
    
3. <span data-ttu-id="bbfb3-150">**測試名稱**與**描述**] 中輸入資訊。</span><span class="sxs-lookup"><span data-stu-id="bbfb3-150">In **Test name** and **Description**, type the information.</span></span>
    
4. <span data-ttu-id="bbfb3-151">在 [**測試類型**] 清單中選取 [**測試扇形**。</span><span class="sxs-lookup"><span data-stu-id="bbfb3-151">In the **Test type** list, select **Test the Slice**.</span></span>
    
5. <span data-ttu-id="bbfb3-152">[**問題**] 清單中選取問題名稱。</span><span class="sxs-lookup"><span data-stu-id="bbfb3-152">In the **Issue** list, select the issue name.</span></span> 
    
6. <span data-ttu-id="bbfb3-153">在**載入**] 清單中，選取負載。</span><span class="sxs-lookup"><span data-stu-id="bbfb3-153">In the **Load** list, select the load.</span></span> 
    
7. <span data-ttu-id="bbfb3-154">**讀取 %之間**，接受預設低或高範圍值或選取值截止相關性分數。</span><span class="sxs-lookup"><span data-stu-id="bbfb3-154">In **Read % between**, accept the default low and high range values or select values for the cutoff Relevance scores.</span></span> 
    
8. <span data-ttu-id="bbfb3-155">在**設定大小**，請選取一個值或接受預設值。</span><span class="sxs-lookup"><span data-stu-id="bbfb3-155">In **Set size**, select a value or accept the default value.</span></span>
    
    <span data-ttu-id="bbfb3-156">還原圖示會還原預設值。</span><span class="sxs-lookup"><span data-stu-id="bbfb3-156">The restore icons will restore the default value.</span></span>
    
9. <span data-ttu-id="bbfb3-p113">按一下 [**啟動標記**。產生測試範例。</span><span class="sxs-lookup"><span data-stu-id="bbfb3-p113">Click **Start tagging**. A test sample is generated.</span></span>
    
10. <span data-ttu-id="bbfb3-159">檢閱及標籤的檔案] 中的每個**相關性\>標籤**] 索引標籤和完成時，按一下 [**計算**。</span><span class="sxs-lookup"><span data-stu-id="bbfb3-159">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span> 
    
11. <span data-ttu-id="bbfb3-160">在 [測試] 索引標籤中，您可以按一下 [**檢視結果**查看測試結果。</span><span class="sxs-lookup"><span data-stu-id="bbfb3-160">In the Test tab, you can click **View results** to see the test results.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="bbfb3-161">另請參閱</span><span class="sxs-lookup"><span data-stu-id="bbfb3-161">See also</span></span>

[<span data-ttu-id="bbfb3-162">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="bbfb3-162">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="bbfb3-163">了解評估的相關性</span><span class="sxs-lookup"><span data-stu-id="bbfb3-163">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="bbfb3-164">標記及評估</span><span class="sxs-lookup"><span data-stu-id="bbfb3-164">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="bbfb3-165">標記及相關性訓練</span><span class="sxs-lookup"><span data-stu-id="bbfb3-165">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="bbfb3-166">追蹤相關性分析</span><span class="sxs-lookup"><span data-stu-id="bbfb3-166">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="bbfb3-167">決定所得的結果</span><span class="sxs-lookup"><span data-stu-id="bbfb3-167">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)

