---
title: 在 Office 365 進階電子文件探索中的測試相關性分析
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
description: '了解如何使用 Office 365 進階電子文件探索中的批次計算後的 [測試] 索引標籤，來測試、 比較，並驗證處理的整體品質。  '
ms.openlocfilehash: 984a7b3f8088604aca235a1caf60bb67b5471499
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34158305"
---
# <a name="test-relevance-analysis-in-office-365-advanced-ediscovery"></a><span data-ttu-id="ce7b2-103">在 Office 365 進階電子文件探索中的測試相關性分析</span><span class="sxs-lookup"><span data-stu-id="ce7b2-103">Test Relevance analysis in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="ce7b2-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="ce7b2-106">在進階電子文件中的 [測試] 索引標籤可讓您測試、 比較，並驗證處理的整體品質。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-106">The Test tab in Advanced eDiscovery enables you to test, compare, and validate the overall quality of processing.</span></span> <span data-ttu-id="ce7b2-107">這些測試會執行批次計算後。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-107">These tests are performed after Batch calculation.</span></span> <span data-ttu-id="ce7b2-108">依標記集合中的檔案，專家可讓每個標記的檔案是否與案件相關實際最終斟酌。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-108">By tagging the files in the collection, an expert makes the final judgment about whether each tagged file is actually relevant to the case.</span></span> 
  
<span data-ttu-id="ce7b2-109">在單一和多重問題案例中，每個問題通常執行測試。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-109">In single and multiple-issue scenarios, tests are typically performed per issue.</span></span> <span data-ttu-id="ce7b2-110">可以在每個測試之後, 檢視結果，並測試結果，可以指定的範例測試檔案已修訂。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-110">Results can be viewed after each test, and test results can be reworked with specified sample test files.</span></span>
  
## <a name="testing-the-rest"></a><span data-ttu-id="ce7b2-111">測試其餘</span><span class="sxs-lookup"><span data-stu-id="ce7b2-111">Testing the rest</span></span>

<span data-ttu-id="ce7b2-112">「 測試 Rest 「 測試用來驗證揀選決策，例如，若要檢閱上方最後一個進階電子文件探索結果為基礎的特定相關性截止分數的檔案。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-112">The "Test the Rest" test is used to validate culling decisions, for example, to review only files above a specific Relevance cutoff score based on the final Advanced eDiscovery results.</span></span> <span data-ttu-id="ce7b2-113">專家檢閱底下選取截止分數 」 來評估相關的檔案，該集合內的數字的檔案的範例。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-113">The expert reviews a sample of files under a selected cutoff score to evaluate the number of relevant files within that set.</span></span>
  
<span data-ttu-id="ce7b2-114">這項測試會提供統計資料和檢閱設定和測試之間的比較 Rest 母體。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-114">This test provides statistics and a comparison between the Review set and the Test the Rest population.</span></span> <span data-ttu-id="ce7b2-115">檢閱一組的結果是指計算相關性訓練期間。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-115">The results of the review set are those calculated by Relevance during Training.</span></span> <span data-ttu-id="ce7b2-116">結果包含計算，根據的設定和輸入的參數，例如：</span><span class="sxs-lookup"><span data-stu-id="ce7b2-116">The results include calculations , based on settings and input parameters, such as:</span></span>
  
- <span data-ttu-id="ce7b2-117">在範例和已識別的相關檔案中測試範例統計資料的檔案數目。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-117">Test sample statistics of the number of files in a sample and identified relevant files.</span></span> 
    
- <span data-ttu-id="ce7b2-118">檢閱一組及其餘部分，例如，檔案，數目的母體參數的表格式比較估計數目相關的檔案、 預估的豐富性和尋找相關的其他檔案的平均成本。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-118">Tabular comparison of the Population parameters of the Review set and the Rest, for example, the number of files, estimated number of relevant files, estimated richness, and the average cost of finding an additional relevant file.</span></span> <span data-ttu-id="ce7b2-119">成本設定可以由系統管理員設定的參數。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-119">Cost parameter settings can be set by the administrator.</span></span>
    
1. <span data-ttu-id="ce7b2-120">開啟**相關性\>測試**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-120">Open the **Relevance \> Test** tab.</span></span> 
    
2. <span data-ttu-id="ce7b2-121">在 [**測試**] 索引標籤中，按一下 [**新增測試**。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-121">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="ce7b2-122">**建立測試**] 對話方塊隨即顯示，如下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-122">The **Create test** dialog is displayed, as shown in the following example.</span></span> 
    
    ![相關性測試的其他結果](media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. <span data-ttu-id="ce7b2-124">**測試名稱**與**描述**] 中輸入的名稱與描述。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-124">In **Test name**, and **Description**, type the name and description.</span></span>
    
4. <span data-ttu-id="ce7b2-125">在 [**測試類型**] 清單中，選取 [**測試其餘**</span><span class="sxs-lookup"><span data-stu-id="ce7b2-125">In the **Test type** list, select **Test the Rest**</span></span>
    
5. <span data-ttu-id="ce7b2-126">在 [**問題 / 類別**清單中，選取 [此問題： 名稱。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-126">In the **Issue / Category** list, select the issue name.</span></span> 
    
6. <span data-ttu-id="ce7b2-127">在 [**載入**] 清單中，選取負載。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-127">In the **Load** list, select the load.</span></span> 
    
7. <span data-ttu-id="ce7b2-128">在**讀取 %**，接受預設值或選取值，如截止相關性分數。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-128">In **Read %**, accept the default value or select a value for the cutoff Relevance score.</span></span> 
    
8. <span data-ttu-id="ce7b2-129">在 [**設定大小**，或接受預設值。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-129">In **Set size**, or accept the default value.</span></span> <span data-ttu-id="ce7b2-130">請注意，還原圖示會還原預設值。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-130">Note that the restore icons will restore the default values.</span></span>
    
9. <span data-ttu-id="ce7b2-131">按一下 [**開始標記**。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-131">Click **Start tagging**.</span></span> <span data-ttu-id="ce7b2-132">測試範例則會產生。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-132">A test sample is generated.</span></span>
    
10. <span data-ttu-id="ce7b2-133">檢閱及標記的每個在檔案**相關性\>標籤**] 索引標籤，並完成時，按一下 [**計算**]。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-133">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>
    
11. <span data-ttu-id="ce7b2-134">在 [測試] 索引標籤中，您可以按一下 [<b0>檢視結果</b0>，請參閱 < 的測試結果。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-134">In the Test tab, you can click **View results** to see the test results.</span></span> <span data-ttu-id="ce7b2-135">範例如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-135">An example is shown in the following figure.</span></span> 
    
    ![測試其他結果](media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
<span data-ttu-id="ce7b2-137">在上述圖中，[**範例參數**] 區段中的資料表包含詳細標記專家，範例中的檔案數目和相關的範例中找到的檔案數目。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-137">In the figure above, the **Sample parameters** section of the table contains details about the number of files in the sample tagged by the expert, and the number of relevant files found in that sample.</span></span> 
  
<span data-ttu-id="ce7b2-138">[**母體參數**] 區段中的表格包含測試結果，包括檢閱組擴展下方選取截止分數的檔案和 「 Rest 」 母群體的上方選取截止分數的檔案。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-138">The **Population parameters** section of the table contains the test results, including the Review set population of files with a score below the selected cutoff and "The Rest" population of files with a score above the selected cutoff.</span></span> <span data-ttu-id="ce7b2-139">針對每個母群體，會顯示下列結果：</span><span class="sxs-lookup"><span data-stu-id="ce7b2-139">For each population, the following results are displayed:</span></span> 
  
- <span data-ttu-id="ce7b2-140">包含檔案讀取 %-所述的截止</span><span class="sxs-lookup"><span data-stu-id="ce7b2-140">Includes files with read % - Stated cutoff</span></span>
    
- <span data-ttu-id="ce7b2-141">檔案總數</span><span class="sxs-lookup"><span data-stu-id="ce7b2-141">The total number of files</span></span> 
    
- <span data-ttu-id="ce7b2-142">估計的相關的檔案數目</span><span class="sxs-lookup"><span data-stu-id="ce7b2-142">The estimated number of relevant files</span></span> 
    
- <span data-ttu-id="ce7b2-143">估計的豐富性</span><span class="sxs-lookup"><span data-stu-id="ce7b2-143">The estimated richness</span></span> 
    
- <span data-ttu-id="ce7b2-144">平均檢閱成本的尋找另一個相關的檔案</span><span class="sxs-lookup"><span data-stu-id="ce7b2-144">The average review cost of finding another relevant file</span></span>
    
## <a name="testing-the-slice"></a><span data-ttu-id="ce7b2-145">測試配量</span><span class="sxs-lookup"><span data-stu-id="ce7b2-145">Testing the slice</span></span>

<span data-ttu-id="ce7b2-146">「 測試切片 」 測試執行測試類似的 「 測試其他 「 測試，，但檔案的區段設定所指定的相關性讀取 %。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-146">The "Test the Slice" test performs testing similar to the "Test the Rest" test, but to a segment of the file set as specified by Relevance Read %.</span></span>
  
1. <span data-ttu-id="ce7b2-147">開啟**相關性\>測試**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-147">Open the **Relevance \> Test** tab.</span></span> 
    
2. <span data-ttu-id="ce7b2-148">在 [**測試**] 索引標籤中，按一下 [**新增測試**。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-148">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="ce7b2-149">**建立測試**] 對話方塊隨即顯示。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-149">The **Create test** dialog is displayed.</span></span> 
    
3. <span data-ttu-id="ce7b2-150">**測試名稱**與**描述**] 中輸入資訊。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-150">In **Test name** and **Description**, type the information.</span></span>
    
4. <span data-ttu-id="ce7b2-151">在 [**測試類型**] 清單中，選取 [**測試配量**。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-151">In the **Test type** list, select **Test the Slice**.</span></span>
    
5. <span data-ttu-id="ce7b2-152">在 [**問題**] 清單中，選取此問題： 名稱。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-152">In the **Issue** list, select the issue name.</span></span> 
    
6. <span data-ttu-id="ce7b2-153">在 [**載入**] 清單中，選取負載。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-153">In the **Load** list, select the load.</span></span> 
    
7. <span data-ttu-id="ce7b2-154">在**讀取 %之間**，接受預設低或高範圍值或選取的值，如截止相關性分數。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-154">In **Read % between**, accept the default low and high range values or select values for the cutoff Relevance scores.</span></span> 
    
8. <span data-ttu-id="ce7b2-155">在**設定大小**，請選取一個值，或接受預設值。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-155">In **Set size**, select a value or accept the default value.</span></span>
    
    <span data-ttu-id="ce7b2-156">還原圖示會還原預設值。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-156">The restore icons will restore the default value.</span></span>
    
9. <span data-ttu-id="ce7b2-157">按一下 [**開始標記**。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-157">Click **Start tagging**.</span></span> <span data-ttu-id="ce7b2-158">測試範例則會產生。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-158">A test sample is generated.</span></span>
    
10. <span data-ttu-id="ce7b2-159">檢閱及標記的每個在檔案**相關性\>標籤**] 索引標籤，並完成時，按一下 [**計算**]。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-159">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span> 
    
11. <span data-ttu-id="ce7b2-160">在 [測試] 索引標籤中，您可以按一下 [<b0>檢視結果</b0>，請參閱 < 的測試結果。</span><span class="sxs-lookup"><span data-stu-id="ce7b2-160">In the Test tab, you can click **View results** to see the test results.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="ce7b2-161">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ce7b2-161">See also</span></span>

[<span data-ttu-id="ce7b2-162">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="ce7b2-162">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="ce7b2-163">了解相關性評估</span><span class="sxs-lookup"><span data-stu-id="ce7b2-163">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="ce7b2-164">標記與評估</span><span class="sxs-lookup"><span data-stu-id="ce7b2-164">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="ce7b2-165">標記與相關性訓練</span><span class="sxs-lookup"><span data-stu-id="ce7b2-165">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="ce7b2-166">追蹤相關性分析</span><span class="sxs-lookup"><span data-stu-id="ce7b2-166">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="ce7b2-167">決定根據結果</span><span class="sxs-lookup"><span data-stu-id="ce7b2-167">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)

