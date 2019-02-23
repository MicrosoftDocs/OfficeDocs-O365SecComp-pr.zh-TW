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
# <a name="decision-based-on-the-results-in-office-365-advanced-ediscovery"></a>根據 Office 365 進階電子文件探索中的結果所作的決策

> [!NOTE]
> 進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
 進階 ediscovery 決定] 索引標籤會提供檢視和使用來決定檢閱一組 case 檔案的大小決策支援統計資料的其他資訊。 
  
## <a name="using-the-decide-tab"></a>使用 [決定] 索引標籤

![決定相關性](media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
此索引標籤包含下列內容：
  
- **問題**： 從這裡，您可以選取 [從清單中的感興趣的問題。 
    
- **檢閱重新叫用比率**： 進階比較 eDiscovery 檢閱根據相關性分數。截止點在圖表中的代表檔案來檢閱、 的百分比對應至相關性分數。這用於在相關性測試階段和匯出臨界值為挑選。預設截止點可供檢閱的檔案數目的位於重新叫用與精確度之間的平衡最佳點。實際截止點應取決於使用者根據目標的成本取捨 （%檢閱） 和風險 （%重新叫用）。您可以使用滑桿，調整截止點並調整 %要擷取相關的檔案和前驗證決策時影響的圖表與參數，請參閱 ＜。
    
- **參數**： 檢閱、 重新叫用下一個彼此相關而且總成本參數彼此相關設定整個案例集合的 relation 中檢閱累計計算統計資料。這些參數的定義如下所示：
    
    **檢閱**： 百分比檔案可供檢閱根據此截止。 
    
    **重新叫用**： 檢閱集中相關檔案的百分比。 
    
    **下一步與相關**： 若要檢閱並識別目前尚未檢閱中設定的其他相關檔案的成本。 
    
    **總成本**： 用於檢閱此百分比 case 檔案的成本。成本的參數設定可以設定依案例的管理員。
    
- **由相關性分數的通訊群組**： 在暗灰色向左顯示的檔案並下方截止分數。工具提示會顯示 relation 總檔案中設定的檢閱檔案中的相關性分數和相關的檔案的百分比。
    
展開 [詳細資料] 窗格會顯示其他詳細資料。在集合圖表目錄中的檔案不包含空白或不是很明確的檔案。系列檔案數據代表未載入相關性，尚未仍計算系列的一部分的檔案。
  
## <a name="see-also"></a>另請參閱

[Office 365 進階電子文件探索](office-365-advanced-ediscovery.md)
  
[了解評估的相關性](assessment-in-relevance-in-advanced-ediscovery.md)
  
[標記及評估](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[執行相關性訓練](tagging-and-assessment-in-advanced-ediscovery.md)
  
[追蹤相關性分析](track-relevance-analysis-in-advanced-ediscovery.md)
  
[測試相關性分析](test-relevance-analysis-in-advanced-ediscovery.md)

