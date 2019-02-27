---
title: 管理 Office 365 中的法律調查
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e
description: Office 365 安全性使用 eDiscovery 案例&amp;規範中心來管理您的組織法律調查。如果您有 E5 訂閱，您可以進一步分析 case 資料使用的文字分析、 機器學習及預測編碼功能進階 eDiscovery 中。
ms.openlocfilehash: b97bd99740e2db090df70af0c76070186f5b8ccf
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296896"
---
# <a name="manage-legal-investigations-in-office-365"></a>管理 Office 365 中的法律調查

組織有許多回應法律案例有關特定主管或組織中的其他員工的原因。這可能會涉及快速找出並保留進一步調查特定資訊的電子郵件、 文件、 立即訊息交談及其他人員在其日常性工作的工作所使用的內容位置。您可以在 Office 365 安全性使用 eDiscovery 案件工具來執行這些結構元件及其他許多類似的活動&amp;規範中心。
  
[管理 eDiscovery 案例與法律調查](#manage-legal-investigations-with-ediscovery-cases)
  
[分析使用 Office 365 進階 eDiscovery 案件資料](#analyze-case-data-using-office-365-advanced-ediscovery)
  
**想要知道 Microsoft 管理其 eDiscovery 調查的方式？** 以下是[技術白皮書 （英文）](https://go.microsoft.com/fwlink/?linkid=852161)您可以下載說明我們如何管理我們內部 eDiscovery 工作流程使用的相同的 Office 365 搜尋與調查有關工具的問題。
   
## <a name="manage-legal-investigations-with-ediscovery-cases"></a>管理 eDiscovery 案例與法律調查

eDiscovery 的情況下可讓您控制可以建立、 存取及管理組織中的 eDiscovery 案例。使用情況下新增成員並控制哪些類型的動作時可以執行、 置於保留的內容位置相關法律案例，並使用 「 內容搜尋工具來搜尋位置保留可能會有回應至您案例的內容。然後您也可以匯出並下載進一步外部檢閱者所使用的結果。如果您的 Office 365 組織擁有 E5 訂閱，也可以進行分析進階在 eDiscovery 中準備搜尋結果。
  
- [管理 eDiscovery 工作流程](ediscovery-cases.md)來建立和使用 eDiscovery 案例的每個法律調查有關您的組織有 ps_1st_currentver 
    
- [EDiscovery 權限指派](assign-ediscovery-permissions.md)給可以建立並管理組織中的 eDiscovery 案例的控制項 
    
- 若要控制 eDiscovery 管理員可搜尋的使用者內容位置[設定規範界限](set-up-compliance-boundaries.md) 
    
- 在組織中[搜尋的內容](search-for-content.md) 
    
- [準備進階 ediscovery 案件內容](prepare-search-results-for-advanced-ediscovery.md)讓您可以使用分析執行進階 eDiscovery 的強大分析工具，例如光學字元辨識、 電子郵件超執行緒，及預測編碼 
    
### <a name="use-scripts-for-advanced-scenarios"></a>使用指令碼為進階案例

如前一節所列的內容搜尋案例指令碼，我們也已建立一些安全性&amp;規範中心 PowerShell 指令碼可協助您管理 eDiscovery 案例。
  
- [建立 eDiscovery 保留報告](create-a-report-on-holds-in-ediscovery-cases.md)包含所有的資訊包含在組織中關聯 eDiscovery 案例 
    
- [新增信箱和 OneDrive 位置](use-a-script-to-add-users-to-a-hold-in-ediscovery.md)的清單中的 ediscovery 使用者保留 
  
## <a name="analyze-case-data-using-office-365-advanced-ediscovery"></a>分析使用 Office 365 進階 eDiscovery 案件資料

Office 365 進階的 eDiscovery 建置在前文各節所述的內容搜尋與 eDiscovery 功能。建立 eDiscovery 案例後，請進行 okay 位置上的按住並收集資料，可能會有回應案例，您可以再進一步分析資料使用文字分析、 學習、 電腦及預測編碼的進階功能eDiscovery。這可協助您快速處理數千個電子郵件、 文件及其他類型的資料以尋找這些項目是很有可能相關的特定案例的組織。與我們，讓您能夠順暢地管理中安全性的大小寫相同已整合管理 （英文） 和進階的 eDiscovery&amp;規範中心。
  
> [!NOTE]
> 若要分析使用進階的 eDiscovery 的使用者資料，使用者 (資料 okay) 必須指派 Office 365 E5 授權。或者，使用 Office 365 E1 或 E3 授權的使用者可以將指派進階的 eDiscovery 獨立授權。系統管理員及法務人員對於已指派給的情況下並使用進階的 eDiscovery 分析資料不需要的 E5 授權。 
  
### <a name="get-started"></a>開始使用

快速入門與進階 eDiscovery 最快的方法是建立案例並準備搜尋結果中安全性&amp;規範中心載入進階 ediscovery 這些結果，然後執行分析 Express 分析的案例資料，然後將匯出供外部檢閱結果。
  
- [取得快速概觀 （英文）](quick-setup-for-advanced-ediscovery.md)的進階的 eDiscovery 工作流程 
    
- [設定使用者和案例](set-up-users-and-cases-in-advanced-ediscovery.md)的進階 eDiscovery 藉由建立案例，請指定 eDiscovery 權限和新增案例成員所有使用安全性&amp;規範中心 
    
- [準備和負載搜尋資料](prepare-data-for-advanced-ediscovery.md)中的進階 eDiscovery 案例 
    
- [載入非 Office 365 資料](import-non-office-365-data-into-advanced-ediscovery.md)中案例來分析進階的 ediscovery 
    
- 若要快速分析案例中的資料和輕鬆匯出結果[使用 Express 分析](use-express-analysis-in-advanced-ediscovery.md) 
    
### <a name="analyze-data"></a>分析資料

搜尋資料載入到進階 ediscovery 案例之後，您將使用分析模組來啟動分析它。分析程序的第一個部分組成組織成群組的唯一檔案、 重複、 檔案及接近重複項目 （文件相似性為也會知道）。然後您將將資料組織到階層結構化群組的電子郵件執行緒及佈景主題的一次並選擇性地組略過分析從排除特定文字的文字篩選器。然後您將執行分析和檢視結果。
  
- [解文件相似性](understand-document-similarity-in-advanced-ediscovery.md)準備進階 eDiscovery 中分析資料 
    
- [接近重複項目、 佈景主題及電子郵件超執行緒，然後執行 [分析] 模組的 [[設定選項](set-analyze-options-in-advanced-ediscovery.md) 
    
- 從分析; 排除文字和文字字串的 [[設定搜尋時忽略文字篩選](set-ignore-text-in-advanced-ediscovery.md)這些篩選器也將會忽略文字當您執行相關性分析 
    
- 分析程序的 [[檢視結果](view-analyze-results-in-advanced-ediscovery.md) 
    
- 分析程序[設定進階設定](set-analyze-advanced-settings-in-advanced-ediscovery.md) 
    
### <a name="set-up-relevance-training"></a>設定相關性訓練

預測性編碼 （稱為的相關性） 在 [進階 eDiscovery 可讓您訓練上什麼您在這裡尋找來可讓您進行決策 （某個項目是否相關或無意） 的系統上小型的文件。
  
- [解設定相關性訓練](manage-relevance-setup-in-advanced-ediscovery.md)、 標記案例相關的檔案和定義案例問題 
    
- [定義案例問題](define-issues-and-assign-users.md)並將每個問題指派給使用者，將訓練檔案 
    
- [新增至目前或新負載匯入的檔案](set-up-loads-to-add-imported-files.md)將會新增至相關性訓練;在負載為新的批次的檔案新增至案例及則用於相關性訓練 
    
- [定義醒目提示的關鍵字](define-highlighted-keywords-and-advanced-options.md)可新增至相關性訓練;這可協助您更妥善地識別案例相關的檔案 
    
### <a name="run-the-relevance-module"></a>執行 [相關性] 模組

訓練設定] 後您準備好要執行的相關性模組及評估此結果的相關性排名，可協助您決定如果您需要執行其他訓練或您準備好要啟動標記檔案儲存為訓練設定的效率您的案例相關。
  
- 標記、 追蹤和重新訓練[了解的相關程序](use-relevance-in-advanced-ediscovery.md)及評估反覆執行程序，根據檔案的範例設定 
    
- [解評估](assessment-in-relevance-in-advanced-ediscovery.md)，其中大小寫專家熟悉檢閱 case 檔案的一組而決定效益的相關性訓練 
    
- [Assess case 檔案](tagging-and-assessment-in-advanced-ediscovery.md)的訓練設定]，然後為相關或您的案例 ； 不相關的標記檔案計算效益 （稱為*豐富*）這可協助您決定目前訓練是否足夠或者您應調整訓練設定。 
    
- [執行相關性訓練](tagging-and-relevance-training-in-advanced-ediscovery.md)之後評估已完成，並再次標記檔案的大小寫相關或不相關至您已定義的問題 
    
- 若要判斷相關性訓練是否已達到 （又稱為*穩定訓練狀態*） 您評估目標值或是否需要更多訓練;[追蹤相關性分析](track-relevance-analysis-in-advanced-ediscovery.md)程序您也可以檢視每個案例的問題的相關結果 
    
- 若要判斷案例的結果集大小檔案的[根據相關性分析做出決策](decision-based-on-the-results-in-advanced-ediscovery.md)可以匯出而進行檢閱 
    
- 若要驗證的相關程序期間所做的挑選出決策[測試相關性分析的品質](test-relevance-analysis-in-advanced-ediscovery.md) 
    
### <a name="export-results"></a>匯出結果

案例中分析資料進階 eDiscovery 的最後一個步驟是匯出外部檢閱分析的結果。
  
- [了解匯出案例的資料](export-case-data-in-advanced-ediscovery.md)
    
- [匯出案例資料](export-results-in-advanced-ediscovery.md)
    
- [檢視批次歷程記錄及匯出過去的結果](view-batch-history-and-export-past-results.md)
    
- [匯出報告欄位](export-report-fields-in-advanced-ediscovery.md)
    
### <a name="other-advanced-ediscovery-tools"></a>其他進階的 eDiscovery 工具

進階的 eDiscovery 提供其他工具和超過分析 case 資料、 相關性分析及匯出資料的功能。
  
- [執行進階的 eDiscovery 報告](run-reports-in-advanced-ediscovery.md)
    
- [定義案例和承租人設定](define-case-and-tenant-settings-in-advanced-ediscovery.md)
    
- [進階的 eDiscovery 公用程式](use-advanced-ediscovery-utilities.md)
