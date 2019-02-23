---
title: 根據 Office 365 進階電子文件探索中的結果所作的決策
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
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: '了解如何在 Office 365 進階 eDiscovery 決定] 索引標籤提供資料可幫助您決定正確的檢閱一組 case 檔案大小。 '
ms.openlocfilehash: c4767e703d03ef5dbdb808332e873d22094d7bca
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216103"
---
# <a name="decision-based-on-the-results-in-office-365-advanced-ediscovery"></a><span data-ttu-id="6d4f2-103">根據 Office 365 進階電子文件探索中的結果所作的決策</span><span class="sxs-lookup"><span data-stu-id="6d4f2-103">Decision based on the results in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="6d4f2-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="6d4f2-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
 <span data-ttu-id="6d4f2-106">進階 ediscovery 決定] 索引標籤會提供檢視和使用來決定檢閱一組 case 檔案的大小決策支援統計資料的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="6d4f2-106">In Advanced eDiscovery, the Decide tab provides additional information for viewing and using decision-support statistics for determining the size of the review set of case files.</span></span> 
  
## <a name="using-the-decide-tab"></a><span data-ttu-id="6d4f2-107">使用 [決定] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="6d4f2-107">Using the Decide tab</span></span>

![決定相關性](media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
<span data-ttu-id="6d4f2-109">此索引標籤包含下列內容：</span><span class="sxs-lookup"><span data-stu-id="6d4f2-109">This tab includes the following:</span></span>
  
- <span data-ttu-id="6d4f2-110">**問題**： 從這裡，您可以選取 [從清單中的感興趣的問題。</span><span class="sxs-lookup"><span data-stu-id="6d4f2-110">**Issue**: From here, you can select the issue of interest from the list.</span></span> 
    
- <span data-ttu-id="6d4f2-p102">**檢閱重新叫用比率**： 進階比較 eDiscovery 檢閱根據相關性分數。截止點在圖表中的代表檔案來檢閱、 的百分比對應至相關性分數。這用於在相關性測試階段和匯出臨界值為挑選。預設截止點可供檢閱的檔案數目的位於重新叫用與精確度之間的平衡最佳點。實際截止點應取決於使用者根據目標的成本取捨 （%檢閱） 和風險 （%重新叫用）。您可以使用滑桿，調整截止點並調整 %要擷取相關的檔案和前驗證決策時影響的圖表與參數，請參閱 ＜。</span><span class="sxs-lookup"><span data-stu-id="6d4f2-p102">**Review-recall ratio**: Comparison of Advanced eDiscovery review according to Relevance scores. The Cutoff point in the chart represents the percentage of files to review, mapped to a Relevance score. This is used in the Relevance Test phase and as an Export threshold for culling. The default cutoff point, for the number of files to review is at the point in which the balance between Recall and Precision is optimal. The actual cutoff point should be determined by the user depending on objectives and the cost tradeoff (%review) and risk (%recall).Using the slider, you can adjust the cutoff point and see the effect on the graph and parameters, when adjusting the percent of relevant files to be retrieved, and before validating a decision.</span></span>
    
- <span data-ttu-id="6d4f2-p103">**參數**： 檢閱、 重新叫用下一個彼此相關而且總成本參數彼此相關設定整個案例集合的 relation 中檢閱累計計算統計資料。這些參數的定義如下所示：</span><span class="sxs-lookup"><span data-stu-id="6d4f2-p103">**Parameters**: Review, Recall, Next relevant and Total cost parameters are cumulative calculated statistics pertaining to the review set in relation to the collection for the entire case. Definitions for these parameters are as follows:</span></span>
    
    <span data-ttu-id="6d4f2-118">**檢閱**： 百分比檔案可供檢閱根據此截止。</span><span class="sxs-lookup"><span data-stu-id="6d4f2-118">**Review**: Percentage of files to review based on this cutoff.</span></span> 
    
    <span data-ttu-id="6d4f2-119">**重新叫用**： 檢閱集中相關檔案的百分比。</span><span class="sxs-lookup"><span data-stu-id="6d4f2-119">**Recall**: Percentage of relevant files in the review set.</span></span> 
    
    <span data-ttu-id="6d4f2-120">**下一步與相關**： 若要檢閱並識別目前尚未檢閱中設定的其他相關檔案的成本。</span><span class="sxs-lookup"><span data-stu-id="6d4f2-120">**Next relevant**: Cost to review and identify an additional relevant file that is not currently in the review set.</span></span> 
    
    <span data-ttu-id="6d4f2-p104">**總成本**： 用於檢閱此百分比 case 檔案的成本。成本的參數設定可以設定依案例的管理員。</span><span class="sxs-lookup"><span data-stu-id="6d4f2-p104">**Total cost**: Cost for reviewing this percentage of the case files. Cost parameter settings can be set by the Case manager.</span></span>
    
- <span data-ttu-id="6d4f2-p105">**由相關性分數的通訊群組**： 在暗灰色向左顯示的檔案並下方截止分數。工具提示會顯示 relation 總檔案中設定的檢閱檔案中的相關性分數和相關的檔案的百分比。</span><span class="sxs-lookup"><span data-stu-id="6d4f2-p105">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score. A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
    
<span data-ttu-id="6d4f2-p106">展開 [詳細資料] 窗格會顯示其他詳細資料。在集合圖表目錄中的檔案不包含空白或不是很明確的檔案。系列檔案數據代表未載入相關性，尚未仍計算系列的一部分的檔案。</span><span class="sxs-lookup"><span data-stu-id="6d4f2-p106">The expanded Details pane displays additional details. Files in collection figures do not include empty or nebulous files. Family files figures represent files that are not loaded in Relevance, yet still counted as part of the family.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6d4f2-128">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6d4f2-128">See also</span></span>

[<span data-ttu-id="6d4f2-129">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="6d4f2-129">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="6d4f2-130">了解評估的相關性</span><span class="sxs-lookup"><span data-stu-id="6d4f2-130">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="6d4f2-131">標記及評估</span><span class="sxs-lookup"><span data-stu-id="6d4f2-131">Tagging and Assessment</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="6d4f2-132">執行相關性訓練</span><span class="sxs-lookup"><span data-stu-id="6d4f2-132">Performing Relevance training</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="6d4f2-133">追蹤相關性分析</span><span class="sxs-lookup"><span data-stu-id="6d4f2-133">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="6d4f2-134">測試相關性分析</span><span class="sxs-lookup"><span data-stu-id="6d4f2-134">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

