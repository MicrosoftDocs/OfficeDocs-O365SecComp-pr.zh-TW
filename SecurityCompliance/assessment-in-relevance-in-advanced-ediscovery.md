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
# <a name="understand-assessment-in-relevance-in-office-365-advanced-ediscovery"></a>在 Office 365 進階電子文件探索中了解相關性評估

> [!NOTE]
> 進階的 eDiscovery 需要您組織與進階規範附加元件或 E5 訂閱 Office 365 E3。如果您不具有該對應並想要嘗試進階的 eDiscovery，您還可以[註冊 Office 365 企業版 E5 的試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
進階的 eDiscovery 啟用早期評估，例如已定義的問題和資料匯入的案例。進階的 eDiscovery 可讓專家制定決策相關採行的方法和套用至文件檢閱專案。
  
## <a name="understanding-assessment"></a>了解評估

在評估、 專家會檢閱可用來判斷問題的豐富並產生反映訓練結果的統計資料的至少 500 檔案隨機組。評估在達到統計的層級可協助進階的 eDiscovery 相關性以提供正確的統計資料，並以有效地決定訓練程序中的穩定點發現足夠相關的檔案時已成功。 
  
較高的相關統計資料和穩定性演算法的效益評估的更正確設定檔案。相關的評估檔案內的檔案數目，可根據的問題而定。豐富是估計集中相關問題的相關檔案的百分比。更豐富的問題會在比問題更快速地達到更相關的檔案數目與較低的豐富。極低豐富的問題 (例如 2%或更少) 需要非常大的評估設為達到重要相關的檔案數目。
  
出現在 [追蹤及決定索引標籤中訓練期間和之後批次計算的統計資料，包括估算的重新叫用不同檢閱設定。根據樣本的估算設定 （在此例中評估檔案） 的統計資料，包括的錯誤限度及該錯誤邊界信賴等級。例如，估計重新叫用的 80%可能會有錯誤的加號或減去 5%的邊界 95%的信賴等級。這表示估計重新叫用的實際 75%-85%以及此估計有 95%信賴。越大評估集的錯誤限度變成較小且更精確的統計資料。 
  
專家檢閱初始評估組 500 檔案之後，相關性是錯誤的能夠判斷目前的重新叫用值的邊界。相關性也將會設定有預設的錯誤限度達到最佳化評估組它建議。以下是一些範例：
  
- 如果已設定評估產生的加號或減去 10%的錯誤限度、 相關性會建議移至訓練 （沒有其他評估檢閱需要）。 
    
- 如果評估集產生的錯誤或加號的 13%減去邊界、 相關性可能會建議另一組達到有較小限度的評估檔案的檢閱。 
    
- 如果極低豐富，相關性可能會建議停止評估即使的錯誤限度是大型 （進行統計資料並不實用）、 因為評估集需要連絡有很有用的錯誤限度會太大。
    
每一項問題有其專屬豐富、 錯誤、 的目前邊界與因此，估計其他評估檔案數目。下一個評估組會建立根據 （最多 1000 個中的單一集會) 的檔案數目上限。
  
您可以接受的相關性建議或根據您的需求來調整目前的錯誤限度。錯誤的預設目前界取決於的重新叫用在等於或高於 75%。
  
> [!NOTE]
> 評估階段可以會略過，在**相關性\>追蹤**中有問題，清除個別問題，然後針對 「 所有問題"**評估**核取方塊的延伸檢視] 索引標籤。不過，因此，會有這個問題沒有統計資料。> 清除**評估**] 核取方塊可以只完成之前執行評估。評估案例中多個問題有，已略過只有當] 核取方塊已清除每個問題 
  
## <a name="see-also"></a>另請參閱

[Office 365 進階電子文件探索](office-365-advanced-ediscovery.md)
  
[標記及評估](tagging-and-assessment-in-advanced-ediscovery.md)
  
[標記及相關性訓練](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[追蹤相關性分析](track-relevance-analysis-in-advanced-ediscovery.md)
  
[決定所得的結果](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[測試相關性分析](test-relevance-analysis-in-advanced-ediscovery.md)

