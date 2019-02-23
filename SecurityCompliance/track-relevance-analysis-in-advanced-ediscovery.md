---
title: 在 Office 365 進階電子文件探索中追蹤相關性分析
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
ms.assetid: 3ab1e2c3-28cf-4bf5-b0a8-c0222f32bdf5
description: '了解如何檢視及轉譯的相關性訓練狀態與 Office 365 進階 ediscovery 案件問題的結果。  '
ms.openlocfilehash: 8bdfd2ddb88215b7217d1cc4cdacf2e775a0d977
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218172"
---
# <a name="track-relevance-analysis-in-office-365-advanced-ediscovery"></a><span data-ttu-id="01798-103">在 Office 365 進階電子文件探索中追蹤相關性分析</span><span class="sxs-lookup"><span data-stu-id="01798-103">Track Relevance analysis in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="01798-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="01798-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="01798-106">進階 ediscovery 相關性追蹤] 索引標籤會顯示在 [標籤] 索引標籤中執行的相關性訓練的計算的有效性並會指出在相關性採取反覆訓練程序中下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="01798-106">In Advanced eDiscovery, the Relevance Track tab displays the calculated validity of the Relevance training performed in the Tag tab and indicates the next step to take in the iterative training process in Relevance.</span></span> 
  
## <a name="tracking-relevance-training-status"></a><span data-ttu-id="01798-107">追蹤相關性訓練狀態</span><span class="sxs-lookup"><span data-stu-id="01798-107">Tracking Relevance training status</span></span>

1. <span data-ttu-id="01798-108">檢視下列詳細資料中相關性追蹤案例的問題，從而**問題名稱**] 對話方塊的下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="01798-108">View the following details in Relevance Track for the case issues, as shown in the following example of an **Issue name** dialog below.</span></span> 
    
  - <span data-ttu-id="01798-p102">**評估**： 此進度列指示器會顯示以何種程度訓練執行此點相關性已達到評估目標出現的錯誤限度。豐富的相關性訓練結果也會顯示。</span><span class="sxs-lookup"><span data-stu-id="01798-p102">**Assessment**: This progress indicator shows to what degree the Relevance training performed to this point has achieved the assessment target in terms of margin of error. The richness of the Relevance training results is also displayed.</span></span> 
    
  - <span data-ttu-id="01798-p103">**訓練**： 此色彩編碼的進度指標及工具提示顯示指出相關性訓練結果穩定性並顯示 [相關性訓練樣本數字刻度標記的每個問題。專家監視反覆相關性訓練程序的進度。</span><span class="sxs-lookup"><span data-stu-id="01798-p103">**Training**: This color-coded progress indicator and tool-tip display indicates the Relevance training results stability and a numeric scale showing the number of Relevance training samples tagged for each issue. The expert monitors the progress of the iterative Relevance training process.</span></span> 
    
  - <span data-ttu-id="01798-113">**批次計算**： 此進度列指示器提供完成的批次計算的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="01798-113">**Batch calculation**: This progress indicator provides information about the completion of Batch calculation.</span></span>
    
  - <span data-ttu-id="01798-114">**下一步**： 顯示要執行的下一個步驟的建議。</span><span class="sxs-lookup"><span data-stu-id="01798-114">**Next step**: Displays the recommendation for the next step to be performed.</span></span> 
    
    <span data-ttu-id="01798-p104">在範例中，會顯示已順利完成的評估問題，以完成的色彩進度列指示器及核取記號表示。標記為技巧，但大小寫仍然會被視為不穩定 （也顯示為工具提示的穩定性狀態）。下一個步驟建議"的訓練"。</span><span class="sxs-lookup"><span data-stu-id="01798-p104">In the example, a successfully completed Assessment for an issue is shown, indicated by the completed color progress indicator and the checkmark. Tagging is underway, but the case is still considered unstable (stability status also shown in a tool-tip). The next step recommendation is "Training".</span></span> 
    
    ![相關性追蹤訓練步驟 1](media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    <span data-ttu-id="01798-p105">[延伸] 檢視會顯示其他資訊和選項。顯示目前的錯誤邊界是在評估，指定現有 （已標記） 評估檔案的目前狀態重新叫用錯誤邊界。</span><span class="sxs-lookup"><span data-stu-id="01798-p105">The expanded view displays additional information and options. The displayed current error margin is the error margin of the recall in the current state of assessment, given the existing (already tagged) assessment files.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="01798-p106">評估階段可以略過清除個別問題，然後針對 「 所有問題"**評估**核取方塊。不過，因此，會有這個問題沒有統計資料。之前執行評估只可以完成 > 清除**評估**] 核取方塊。評估案例中多個問題有，已略過只有當] 核取方塊已清除每個問題</span><span class="sxs-lookup"><span data-stu-id="01798-p106">The Assessment stage can be bypassed by clearing the **Assessment** check box per issue and then for "all issues". However, as a result, there will be no statistics for this issue. > Clearing the **Assessment** check box can only be done before assessment is performed. Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
    <span data-ttu-id="01798-125">當評估就不會完成與第一個範例設定檔的、 評估可能會接著標記多個檔案。</span><span class="sxs-lookup"><span data-stu-id="01798-125">When assessment is not completed with the first sample set of files, assessment might be the next step for tagging more files.</span></span> 
    
    <span data-ttu-id="01798-p107">在 [**相關性** \> **追蹤**、 訓練進度列指示器及工具提示會指出到達穩定性所需的其他樣本估計的數。此評估所需的其他訓練提供指導方針。</span><span class="sxs-lookup"><span data-stu-id="01798-p107">In **Relevance** \> **Track**, the training progress indicator and tool-tip indicate the estimated number of additional samples needed to reach stability. This estimate provides a guideline for the additional training needed.</span></span>
    
    ![相關性追蹤訓練](media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. <span data-ttu-id="01798-p108">如果您需要繼續訓練和完成標記後，按一下 [**訓練**。從載入的檔案設定的其他訓練產生另一個範例組檔案。您再回到標記及訓練多個檔案的 [標籤] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="01798-p108">When you're done tagging and if you need to continue training, click **Training**. Another sample set of files is generated from the loaded file set for additional training. You are then returned to the Tag tab to tag and train more files.</span></span>
    
### <a name="reaching-stable-training-levels"></a><span data-ttu-id="01798-132">即將達到穩定訓練層級</span><span class="sxs-lookup"><span data-stu-id="01798-132">Reaching stable training levels</span></span>

<span data-ttu-id="01798-133">評估檔案已得到穩定層級的之後，進階的 eDiscovery 是訓練的備妥可供批次計算。</span><span class="sxs-lookup"><span data-stu-id="01798-133">After the assessment files have attained a stable level of training, Advanced eDiscovery is ready for Batch calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="01798-p109">通常，其中三項穩定訓練範例之後下, 一步就是"批次計算"。可能會有例外狀況，例如標記檔案從舊版範例 （英文） 或植入檔案時新增至未發生變更時。</span><span class="sxs-lookup"><span data-stu-id="01798-p109">Usually, after three stable training samples, the next step is "Batch calculation". There may be exceptions, for example, when there were changes to the tagging of files from earlier samples or when seed files were added.</span></span> 
  
### <a name="performing-batch-calculation"></a><span data-ttu-id="01798-136">執行批次計算</span><span class="sxs-lookup"><span data-stu-id="01798-136">Performing Batch calculation</span></span>

<span data-ttu-id="01798-137">批次計算執行作為下一個步驟之後訓練成功完成 （當穩定訓練狀態顯示核取記號表示和穩定狀態的工具提示中的進度列。）批次計算會套用至整個檔案母群體，以評估的檔案關聯及指派相關性分數的相關性訓練期間取得知識。</span><span class="sxs-lookup"><span data-stu-id="01798-137">Batch calculation is executed as the next step after training is successfully completed (when a stable training status is shown by the progress bar, a checkmark and stable status in the tool-tip.) Batch calculation applies the knowledge acquired during the Relevance training to the entire file population, to assess the files' relevance and to assign Relevance scores.</span></span>
  
<span data-ttu-id="01798-p110">多個問題時，批次會計算每個問題。批次計算期間會同時處理所有檔案監視進度。</span><span class="sxs-lookup"><span data-stu-id="01798-p110">When there is more than one issue, Batch calculation is done per issue. During Batch calculation, progress is monitored while processing all of the files.</span></span> 
  
<span data-ttu-id="01798-p111">以下，建議的下一個步驟是"None"，這表示沒有其他反覆相關性訓練不需要此時。下一個階段是**相關性\>決定**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="01798-p111">Here, the recommended next step is "None", which indicates that no additional iterative Relevance training is required at this point. The next phase is the **Relevance \> Decide** tab.</span></span> 
  
<span data-ttu-id="01798-142">如果您想要匯入新的檔案批次計算後，系統管理員可以將匯入的檔案新增至新的負載。</span><span class="sxs-lookup"><span data-stu-id="01798-142">If you want to import new files after Batch calculation, the administrator can add the imported files to a new load.</span></span>
  
> [!NOTE]
> <span data-ttu-id="01798-p112">如果您按一下 [**取消**批次計算期間] 程序會儲存項目已經有執行時。如果您執行一次批次計算，程序會繼續從上次執行點。</span><span class="sxs-lookup"><span data-stu-id="01798-p112">If you click **Cancel** during Batch calculation, the process saves what was already executed. If you run Batch calculation again, the process will continue from the last executed point.</span></span> 
  
### <a name="assessing-tagging-consistency"></a><span data-ttu-id="01798-145">評估標記一致性</span><span class="sxs-lookup"><span data-stu-id="01798-145">Assessing tagging consistency</span></span>

<span data-ttu-id="01798-p113">如果在檔案標記不一致，它會影響分析。結果不最佳或一致性會有疑問時可以使用進階的 eDiscovery 標記一致性處理程序。會傳回可能對於已標記的檔案清單，並可以檢閱並重新標記，視。</span><span class="sxs-lookup"><span data-stu-id="01798-p113">If there are inconsistencies in file tagging, it can affect the analysis. The Advanced eDiscovery tagging consistency process can be used when results are not optimal or consistency is in doubt. A list of possible inconsistently tagged files is returned, and they can be reviewed and re-tagged, as necessary.</span></span>
  
> [!NOTE]
> <span data-ttu-id="01798-p114">後可檢視下列評估、 標記一致性**相關性**中的七個或多個訓練趨\>**追蹤** \> **問題** \> **詳細的結果** \> **訓練進度**。此檢閱是一次完成一個問題。</span><span class="sxs-lookup"><span data-stu-id="01798-p114">After seven or more training rounds following assessment, tagging consistency can be viewed in **Relevance** \> **Track** \> **Issue** \> **Detailed results** \> **Training progress**. This review is done for one issue at a time.</span></span> 
  
1. <span data-ttu-id="01798-151">在**相關性\>追蹤**，依序展開 [問題] 列。</span><span class="sxs-lookup"><span data-stu-id="01798-151">In **Relevance \> Track**, expand an issue's row.</span></span>
    
2. <span data-ttu-id="01798-152">至右邊的**下一個步驟**中，按一下 [**修改**]。</span><span class="sxs-lookup"><span data-stu-id="01798-152">To the right of **Next step**, click **Modify**.</span></span>
    
3. <span data-ttu-id="01798-153">選取 [**下一步**] 選項後七個訓練範例為**標記不一致**，並按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="01798-153">Select **Tag inconsistencies** as the **Next step** option, after seven training samples and click **OK**.</span></span>
    
4. <span data-ttu-id="01798-p115">選取 [**標記不一致處**。[**標籤**] 索引標籤會開啟顯示來重新標記為必要的不一致的清單。</span><span class="sxs-lookup"><span data-stu-id="01798-p115">Select **Tag inconsistencies**. The **Tag** tab opens displaying a list of the inconsistencies to re-tag as necessary.</span></span> 
    
5. <span data-ttu-id="01798-p116">按一下 [**計算**送出所做的變更。下一個步驟之後標記不一致處"訓練"。</span><span class="sxs-lookup"><span data-stu-id="01798-p116">Click **Calculate** to submit the changes. The next step after tagging inconsistencies is "Training".</span></span> 
    
## <a name="viewing-and-using-relevance-results"></a><span data-ttu-id="01798-158">檢視及使用結果的相關性</span><span class="sxs-lookup"><span data-stu-id="01798-158">Viewing and using Relevance results</span></span>

<span data-ttu-id="01798-p117">在**相關性\>追蹤**] 索引標籤、 依序展開 [問題] 資料列及**詳細的結果**旁邊按一下 [**檢視**]。詳細的結果窗格會顯示、 以顯示與下面所述。</span><span class="sxs-lookup"><span data-stu-id="01798-p117">In the **Relevance \> Track** tab, expand an issue's row, and next to **Detailed results**, click **View**. The Detailed results panes are displayed, as shown and described below.</span></span>
  
![相關性訓練的詳細結果](media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a><span data-ttu-id="01798-162">標記的摘要</span><span class="sxs-lookup"><span data-stu-id="01798-162">Tagging summary</span></span>

 <span data-ttu-id="01798-163">在下面所顯示的範例中，**標記摘要**會顯示每個評估、 訓練及執行更新性檔案標記程序總計。</span><span class="sxs-lookup"><span data-stu-id="01798-163">In the example shown below, the **Tagging summary** displays totals for each of Assessment, Training, and Catch-up file tagging processes.</span></span> 
  
![相關性追蹤的標記摘要](media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a><span data-ttu-id="01798-165">關鍵字</span><span class="sxs-lookup"><span data-stu-id="01798-165">Keywords</span></span>

<span data-ttu-id="01798-p118">關鍵字是唯一的字串、 word、 片語或序列進階 eDiscovery 所識別的檔案是否與相關的重要指標為檔案中的字數。"包含"欄清單關鍵字與標記為相關，檔案中的寬度及"排除 」 資料行清單關鍵字和 weights 檔案已標記為不相關。</span><span class="sxs-lookup"><span data-stu-id="01798-p118">A keyword is a unique string, word, phrase, or sequence of words in a file identified by Advanced eDiscovery as a significant indicator of whether a file is relevant. The "Include" columns list keyword and weights in files tagged as Relevant, and the "Exclude" columns lists keywords and weights in files tagged as Not relevant.</span></span>
  
<span data-ttu-id="01798-p119">進階的 eDiscovery 指派負數或正數關鍵字加權值。較高權數、 越高關鍵字會出現檔案批次計算期間指派較高的相關性分數的可能性。</span><span class="sxs-lookup"><span data-stu-id="01798-p119">Advanced eDiscovery assigns negative or positive keyword weight values. The higher the weight, the higher the likelihood that a file in which the keyword appears is assigned a higher Relevance score during Batch calculation.</span></span> 
  
<span data-ttu-id="01798-170">關鍵字進階的 eDiscovery 清單可用以輔助建置專家或間接例行性檢查清單在檔案中的任何時候檢閱程序。</span><span class="sxs-lookup"><span data-stu-id="01798-170">The Advanced eDiscovery list of keywords can be used to supplement a list built by an expert or as an indirect sanity check at any point in the file review process.</span></span>
  
### <a name="training-progress"></a><span data-ttu-id="01798-171">訓練進度</span><span class="sxs-lookup"><span data-stu-id="01798-171">Training progress</span></span>

<span data-ttu-id="01798-172">**訓練進度**窗格包含訓練進度圖形和品質指標顯示，如以下範例所示。</span><span class="sxs-lookup"><span data-stu-id="01798-172">The **Training Progress** pane includes a training progress graph and quality indicator display, as shown in the example below.</span></span> 
  
![相關性追蹤訓練進度](media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
 <span data-ttu-id="01798-174">**訓練品質指標**： 顯示標記一致性的評等，如下所示：</span><span class="sxs-lookup"><span data-stu-id="01798-174">**Training quality indicator**: Displays the rating of the tagging consistency as follows:</span></span>
  
- <span data-ttu-id="01798-p120">**良好**： 可持續標示的檔案。（顯示綠色亮）</span><span class="sxs-lookup"><span data-stu-id="01798-p120">**Good**: Files are tagged consistently. (Green light displayed)</span></span>
    
- <span data-ttu-id="01798-p121">**中型**： 可能對於標記某些檔案。（黃色淺色顯示）</span><span class="sxs-lookup"><span data-stu-id="01798-p121">**Medium**: Some files may be tagged inconsistently. (Yellow light displayed)</span></span>
    
- <span data-ttu-id="01798-p122">**警告**： 許多檔案可能對於標記。（顯示紅色燈）</span><span class="sxs-lookup"><span data-stu-id="01798-p122">**Warning**: Many files may be tagged inconsistently. (Red light displayed)</span></span>
    
 <span data-ttu-id="01798-p123">**訓練進度圖表**： 顯示相關性訓練穩定性程度後 F 量值與相關性訓練循環數目。當相關性訓練結果最佳化我們為由右移動整個圖表信賴區間以縮小並搭配 F 測量，由進階 eDiscovery 來決定穩定性的相關性。</span><span class="sxs-lookup"><span data-stu-id="01798-p123">**Training progress graph**: Shows the degree of Relevance training stability after a number of Relevance training cycles in comparison to the F-measure value. As we move from the left to the right across the graph, the confidence interval narrows and is used, along with the F-measure, by Advanced eDiscovery Relevance to determine stability when the Relevance training results are optimized.</span></span>
  
> [!NOTE]
> <span data-ttu-id="01798-p124">相關性使用 F2，其中重新叫用會接收倍粗細為精確度 F 度量評量。案例與高豐富 （超過 25%) 相關性用途 F1 （1:1 的比例）。F 量值的比例的設定方式**相關性安裝** \> **進階的設定**。</span><span class="sxs-lookup"><span data-stu-id="01798-p124">Relevance uses F2, an F-measure metric where Recall receives twice as much weight as Precision. For cases with high richness (over 25%), Relevance uses F1 (1:1 ratio). The F-measure ratio can be configured in **Relevance setup** \> **Advanced settings**.</span></span> 
  
### <a name="batch-calculation-results"></a><span data-ttu-id="01798-186">批次計算結果</span><span class="sxs-lookup"><span data-stu-id="01798-186">Batch calculation results</span></span>

<span data-ttu-id="01798-187">**批次計算結果**] 窗格中包含，如下所示計分相關性的檔案的數目：</span><span class="sxs-lookup"><span data-stu-id="01798-187">The **Batch calculation results** pane includes the number of files that were scored for Relevance, as follows:</span></span> 
  
- <span data-ttu-id="01798-188">**成功**</span><span class="sxs-lookup"><span data-stu-id="01798-188">**Success**</span></span>
    
- <span data-ttu-id="01798-189">**空白**： 不包含文字，例如僅空格 /] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="01798-189">**Empty**: Contains no text, for example, only spaces/tabs</span></span>
    
- <span data-ttu-id="01798-190">**失敗**： 由於過多的大小或無法讀取</span><span class="sxs-lookup"><span data-stu-id="01798-190">**Failed**: Due to excessive size or could not be read</span></span>
    
- <span data-ttu-id="01798-191">**Ignored**： 由於過多的大小</span><span class="sxs-lookup"><span data-stu-id="01798-191">**Ignored**: Due to excessive size</span></span>
    
- <span data-ttu-id="01798-192">**Nebulous**： 包含沒有意義的文字或相關問題沒有功能</span><span class="sxs-lookup"><span data-stu-id="01798-192">**Nebulous**: Contains meaningless text or no features relevant to the issue</span></span>
    
> [!NOTE]
> <span data-ttu-id="01798-193">空白、 失敗、 Ignored 或 Nebulous 將會收到-1 的相關性分數。</span><span class="sxs-lookup"><span data-stu-id="01798-193">Empty, Failed, Ignored, or Nebulous will receive a Relevance score of -1.</span></span> 
  
### <a name="training-statistics"></a><span data-ttu-id="01798-194">訓練統計資料</span><span class="sxs-lookup"><span data-stu-id="01798-194">Training statistics</span></span>

<span data-ttu-id="01798-195">**訓練統計資料**] 窗格會顯示的統計資料和進階的 eDiscovery 相關性訓練結果為基礎的圖形。</span><span class="sxs-lookup"><span data-stu-id="01798-195">The **Training statistics** pane displays statistics and graphs based on results from Advanced eDiscovery Relevance training.</span></span> 
  
![相關性追蹤訓練統計資料](media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
<span data-ttu-id="01798-197">這個檢視會顯示下列：</span><span class="sxs-lookup"><span data-stu-id="01798-197">This view shows the following:</span></span>
  
- <span data-ttu-id="01798-p125">**檢閱重新叫用比率**： 的假設情況下線性檢閱得到的結果的相關性根據比較。檢閱設定大小組特定估計重新叫用。</span><span class="sxs-lookup"><span data-stu-id="01798-p125">**Review-recall ratio**: Comparison of results according to Relevance scores in a hypothetically linear review. Recall is estimated given the review set size set.</span></span>
    
- <span data-ttu-id="01798-200">**參數**： 累計計算設定整個案例檔案母群體的 relation 中檢閱相關的統計資料。</span><span class="sxs-lookup"><span data-stu-id="01798-200">**Parameters**: Cumulative calculated statistics pertaining to the review set in relation to the file population for the entire case.</span></span>
    
- <span data-ttu-id="01798-201">**檢閱**： 百分比檔案可供檢閱根據此截止。</span><span class="sxs-lookup"><span data-stu-id="01798-201">**Review**: Percentage of files to review based on this cutoff.</span></span>
    
- <span data-ttu-id="01798-202">**重新叫用**： 檢閱集中檔案相關的百分比。</span><span class="sxs-lookup"><span data-stu-id="01798-202">**Recall**: Percentage of Relevant files in the review set.</span></span> 
    
- <span data-ttu-id="01798-p126">**由相關性分數的通訊群組**： 在暗灰色向左顯示的檔案並下方截止分數。工具提示會顯示 relation 總檔案中設定的檢閱檔案中的相關性分數和相關的檔案的百分比。</span><span class="sxs-lookup"><span data-stu-id="01798-p126">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score. A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="01798-205">另請參閱</span><span class="sxs-lookup"><span data-stu-id="01798-205">See also</span></span>

[<span data-ttu-id="01798-206">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="01798-206">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="01798-207">了解評估的相關性</span><span class="sxs-lookup"><span data-stu-id="01798-207">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="01798-208">執行及檢閱評估</span><span class="sxs-lookup"><span data-stu-id="01798-208">Performing and reviewing Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="01798-209">執行相關性訓練</span><span class="sxs-lookup"><span data-stu-id="01798-209">Performing Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="01798-210">進行決策根據結果</span><span class="sxs-lookup"><span data-stu-id="01798-210">Making decisions based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="01798-211">測試相關性分析</span><span class="sxs-lookup"><span data-stu-id="01798-211">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

