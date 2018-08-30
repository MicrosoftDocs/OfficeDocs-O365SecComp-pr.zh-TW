---
title: 在 Office 365 進階電子文件探索中了解相關性評估
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1d33d4fb-91ed-41c0-b72e-5a26eca3a2a7
description: '取得評估階段和其在 Office 365 進階 ediscovery 的相關性訓練期間判定問題的豐富的角色的概觀。  '
ms.openlocfilehash: a54a4134609b16568586f3cb6b60ebdeba860bac
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526763"
---
# <a name="understand-assessment-in-relevance-in-office-365-advanced-ediscovery"></a><span data-ttu-id="a6c15-103">在 Office 365 進階電子文件探索中了解相關性評估</span><span class="sxs-lookup"><span data-stu-id="a6c15-103">Understand Assessment in Relevance in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="a6c15-p101">進階的 eDiscovery 需要您組織與進階規範附加元件或 E5 訂閱 Office 365 E3。如果您不具有該對應並想要嘗試進階的 eDiscovery，您還可以[註冊 Office 365 企業版 E5 的試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="a6c15-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="a6c15-p102">進階的 eDiscovery 啟用早期評估，例如已定義的問題和資料匯入的案例。進階的 eDiscovery 可讓專家制定決策相關採行的方法和套用至文件檢閱專案。</span><span class="sxs-lookup"><span data-stu-id="a6c15-p102">Advanced eDiscovery enables early assessment, for example, for the defined issues and the data imported for a case. Advanced eDiscovery enables the expert to make decisions pertaining to an adopted approach and to apply them to the document review project.</span></span>
  
## <a name="understanding-assessment"></a><span data-ttu-id="a6c15-108">了解評估</span><span class="sxs-lookup"><span data-stu-id="a6c15-108">Understanding assessment</span></span>

<span data-ttu-id="a6c15-p103">在評估、 專家會檢閱可用來判斷問題的豐富並產生反映訓練結果的統計資料的至少 500 檔案隨機組。評估在達到統計的層級可協助進階的 eDiscovery 相關性以提供正確的統計資料，並以有效地決定訓練程序中的穩定點發現足夠相關的檔案時已成功。</span><span class="sxs-lookup"><span data-stu-id="a6c15-p103">In Assessment, the expert reviews a random set of at least 500 files, which are used to determine the richness of the issues and to produce statistics that reflect the training results. Assessment is successful when enough relevant files are found to reach a statistical level that will help Advanced eDiscovery Relevance to provide accurate statistics and to effectively determine the stabilization point in the training process.</span></span> 
  
<span data-ttu-id="a6c15-p104">較高的相關統計資料和穩定性演算法的效益評估的更正確設定檔案。相關的評估檔案內的檔案數目，可根據的問題而定。豐富是估計集中相關問題的相關檔案的百分比。更豐富的問題會在比問題更快速地達到更相關的檔案數目與較低的豐富。極低豐富的問題 (例如 2%或更少) 需要非常大的評估設為達到重要相關的檔案數目。</span><span class="sxs-lookup"><span data-stu-id="a6c15-p104">The higher the number of relevant files in the assessment set, the more accurate the statistics and the effectiveness of the stability algorithm. The number of relevant files within the assessment files depends on the richness of the issue. Richness is the estimated percent of relevant files in the set relevant to an issue. Issues with higher richness will reach a higher number of relevant files more quickly than issues with lower richness. Issues with extremely low richness (for example, 2% or less) will require a very large assessment set to reach a significant number of Relevant files.</span></span>
  
<span data-ttu-id="a6c15-p105">出現在 [追蹤及決定索引標籤中訓練期間和之後批次計算的統計資料，包括估算的重新叫用不同檢閱設定。根據樣本的估算設定 （在此例中評估檔案） 的統計資料，包括的錯誤限度及該錯誤邊界信賴等級。例如，估計重新叫用的 80%可能會有錯誤的加號或減去 5%的邊界 95%的信賴等級。這表示估計重新叫用的實際 75%-85%以及此估計有 95%信賴。越大評估集的錯誤限度變成較小且更精確的統計資料。</span><span class="sxs-lookup"><span data-stu-id="a6c15-p105">The statistics, which are presented in the Track and Decide tabs during training and after Batch calculation, include estimations of recall for different review sets. In statistics, estimations that are based on a sample set (in this case, the assessment files) include the margin of error and the confidence level of that error margin. For example, estimated recall of 80% might have a margin of error of plus or minus 5% with a confidence level of 95%. This means that the estimated recall is actually 75%-85% and this estimation has 95% confidence. The larger the assessment set, the margin of error becomes smaller and the statistics are more accurate.</span></span> 
  
<span data-ttu-id="a6c15-p106">專家檢閱初始評估組 500 檔案之後，相關性是錯誤的能夠判斷目前的重新叫用值的邊界。相關性也將會設定有預設的錯誤限度達到最佳化評估組它建議。以下是一些範例：</span><span class="sxs-lookup"><span data-stu-id="a6c15-p106">After the expert reviews an initial assessment set of 500 files, Relevance is able to determine the current margin of error of the recall values. Relevance will also set a default margin of error that it recommends to reach to optimize the assessment set. Following are some examples:</span></span>
  
- <span data-ttu-id="a6c15-124">如果已設定評估產生的加號或減去 10%的錯誤限度、 相關性會建議移至訓練 （沒有其他評估檢閱需要）。</span><span class="sxs-lookup"><span data-stu-id="a6c15-124">If the assessment set already yielded a margin of error of plus or minus 10%, Relevance will recommend to move on to training (no additional assessment review is needed).</span></span> 
    
- <span data-ttu-id="a6c15-125">如果評估集產生的錯誤或加號的 13%減去邊界、 相關性可能會建議另一組達到有較小限度的評估檔案的檢閱。</span><span class="sxs-lookup"><span data-stu-id="a6c15-125">If the assessment set yielded a margin of error of plus or minus 13%, Relevance might recommend the review of another set of assessment files to reach a smaller margin.</span></span> 
    
- <span data-ttu-id="a6c15-126">如果極低豐富，相關性可能會建議停止評估即使的錯誤限度是大型 （進行統計資料並不實用）、 因為評估集需要連絡有很有用的錯誤限度會太大。</span><span class="sxs-lookup"><span data-stu-id="a6c15-126">If richness is extremely low, Relevance might recommend stopping assessment even though the margin of error is large (making statistics impractical), because the assessment set needed to reach a useful margin of error is too large.</span></span>
    
<span data-ttu-id="a6c15-p107">每一項問題有其專屬豐富、 錯誤、 的目前邊界與因此，估計其他評估檔案數目。下一個評估組會建立根據 （最多 1000 個中的單一集會) 的檔案數目上限。</span><span class="sxs-lookup"><span data-stu-id="a6c15-p107">Each issue has its own richness, current margin of error, and as a result, estimated number of additional assessment files. The next assessment set is created according to the maximum number of files (up to 1,000 in a single set).</span></span>
  
<span data-ttu-id="a6c15-p108">您可以接受的相關性建議或根據您的需求來調整目前的錯誤限度。錯誤的預設目前界取決於的重新叫用在等於或高於 75%。</span><span class="sxs-lookup"><span data-stu-id="a6c15-p108">You can accept the Relevance recommendations or adjust the current margin of error according to your needs. The default current margin of error is determined for recall at equal or above 75%.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a6c15-p109">評估階段可以會略過，在**相關性\>追蹤**中有問題，清除個別問題，然後針對 「 所有問題"**評估**核取方塊的延伸檢視] 索引標籤。不過，因此，會有這個問題沒有統計資料。> 清除**評估**] 核取方塊可以只完成之前執行評估。評估案例中多個問題有，已略過只有當] 核取方塊已清除每個問題</span><span class="sxs-lookup"><span data-stu-id="a6c15-p109">The Assessment stage can be bypassed, in the **Relevance \> Track** tab in the expanded view for an issue, by clearing the **Assessment** check box per issue and then for "all issues". However, as a result, there will be no statistics for this issue. > Clearing the **Assessment** check box can only be done before assessment is performed. Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a6c15-135">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a6c15-135">See also</span></span>

[<span data-ttu-id="a6c15-136">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="a6c15-136">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="a6c15-137">標記及評估</span><span class="sxs-lookup"><span data-stu-id="a6c15-137">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a6c15-138">標記及相關性訓練</span><span class="sxs-lookup"><span data-stu-id="a6c15-138">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a6c15-139">追蹤相關性分析</span><span class="sxs-lookup"><span data-stu-id="a6c15-139">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a6c15-140">決定所得的結果</span><span class="sxs-lookup"><span data-stu-id="a6c15-140">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a6c15-141">測試相關性分析</span><span class="sxs-lookup"><span data-stu-id="a6c15-141">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

