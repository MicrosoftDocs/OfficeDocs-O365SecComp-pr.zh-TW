---
title: 搜尋 Office 365 稽核記錄中的 eDiscovery 活動
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/24/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 67cc7f42-a53d-4751-b929-6005c80798f7
description: 了解如何搜尋 Office 365 稽核記錄會記錄合規性管理員中的安全性 & 合規性中心執行內容搜尋和 eDiscovery 案例的工作時的事件。
ms.openlocfilehash: 62c58d123367fd5ee6778034716bc1deb5afc1e2
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32260961"
---
# <a name="search-for-ediscovery-activities-in-the-office-365-audit-log"></a>搜尋 Office 365 稽核記錄中的 eDiscovery 活動

在 Office 365 稽核記錄檔中記錄內容搜尋和 eDiscovery 相關的活動中安全性 & 合規性中心，或藉由執行對應的 Windows PowerShell cmdlet 所執行。 當系統管理員或符合性系統管理員 （或任何已指派的 eDiscovery 權限的使用者） 執行下列內容搜尋和 eDiscovery 相關工作安全性 & 合規性中心中，會記錄事件：
  
- 建立及管理 eDiscovery 案例
    
- 建立、 啟動和編輯內容搜尋
    
- 執行內容搜尋動作，例如預覽，匯出，以及刪除搜尋結果
    
- 設定內容搜尋的權限篩選
    
- 管理 eDiscovery 系統管理員角色
    
> [!IMPORTANT]
> 本文所述的活動會只執行使用安全性 & 合規性中心的 eDiscovery 工作的結果。 使用 Exchange Online 或 SharePoint Online 中的 eDiscovery 中心的就地 eDiscovery 工具所執行的 eDiscovery 工作不包含在內。 
  
如需關於搜尋 Office 365 稽核記錄，是必要的並匯出搜尋結果，請參閱 <<c0>的搜尋稽核記錄中的安全性 &amp; 合規性中心的權限。
  
## <a name="how-to-search-for-and-view-ediscovery-activities"></a>如何搜尋及檢視電子文件探索活動

目前，您需要進行特定事項若要檢視 Office 365 稽核記錄中的 eDiscovery 活動。 方法如下。
  
1. 移至 [https://protection.office.com](https://protection.office.com)。
    
2. 使用公司或學校帳戶登入 Office 365。
    
3. 在左窗格中，按一下 [**搜尋**]，然後按一下 [**稽核記錄搜尋**。
    
4. 在 [**活動**] 下拉式清單中，[**電子文件探索活動**，按一下 [若要搜尋的一或多個活動。 或者，您可以按一下 [**電子文件探索活動**來搜尋所有 eDiscovery 相關的活動。 
    
    > [!NOTE]
    > [活動] 下拉式清單也包含一組活動名為**eDiscovery 指令程式活動**，會傳回記錄的指令程式稽核記錄檔。 
  
5.  選取要顯示 eDiscovery 時所發生事件的期間內的日期和時間範圍。 
    
6. 在 [**使用者**] 方塊中，選取一或多個使用者顯示的搜尋結果。 保留此方塊留白，以傳回所有使用者的項目。 
    
7. 按一下 [**搜尋**] 以執行使用您的搜尋準則的 [搜尋]。 
    
8. 搜尋結果出現之後，您可以按一下 [篩選或排序結果活動記錄的**篩選結果**。 不幸的是，您無法使用篩選來明確地中排除某些活動。 
    
9. 若要檢視的相關活動的詳細資訊，請按一下 [搜尋結果清單中的活動記錄。 
    
    **詳細資料**飛入] 頁面會顯示包含從事件記錄的詳細的屬性。 若要顯示其他詳細資訊，請按一下 [**詳細資訊**。 如需這些屬性的說明，請參閱 < <b0>eDiscovery 活動的詳細的內容</b0>] 區段中。 

  
## <a name="ediscovery-activities"></a>電子文件探索活動

下表說明的內容搜尋和 eDiscovery 相關的活動，會記錄系統管理員或使用者在使用安全性 & 合規性中心，或執行對應的 cmdlet 執行 eDiscovery 相關的活動時遠端 PowerShell 連線到您組織的安全性 & 合規性中心。 
  
> [!NOTE]
> 本節所述的 eDiscovery 活動提供類似的資訊來下一節所述的 eDiscovery 指令程式活動。 我們建議您使用本節中所述，因為它們會在 30 分鐘內出現在稽核記錄搜尋結果中的 eDiscovery 活動。 花費最多 24 小時的 ediscovery （英文） 指令程式的活動，以顯示在稽核記錄搜尋結果。 
  
|**易記名稱**|**Operation**|**對應的 cmdlet**|**描述**|
|:-----|:-----|:-----|:-----|
|新增的成員至 eDiscovery 案例  <br/> |CaseMemberAdded  <br/> |新增 ComplianceCaseMember  <br/> |使用者已新增為 eDiscovery 案例的成員。 身為成員的情況下，使用者可以執行各種案例相關的工作，根據是否他們已獲指派必要權限。  <br/> |
|變更內容搜尋  <br/> |SearchUpdated  <br/> |Set-ComplianceSearch  <br/> |已變更現有的內容搜尋。 新增或移除內容位置或編輯搜尋查詢，可以包含的變更。  <br/> |
|已變更的 eDiscovery 系統管理員成員資格  <br/> |CaseAdminUpdated  <br/> |更新 eDiscoveryCaseAdmin  <br/> |在您的組織中的 eDiscovery 系統管理員的清單已變更。 EDiscovery 系統管理員的清單取代一組新的使用者時，會記錄此活動。 如果新增或移除單一使用者，會記錄 CaseAdminAdded 作業。  <br/> |
|已變更的 eDiscovery 案例  <br/> |CaseUpdated  <br/> |Set-compliancecase  <br/> |已變更的 eDiscovery 案例。 變更包括關閉開啟的情況下，或重新開啟關閉的案例。  <br/> |
|已變更的 eDiscovery 案例的成員資格  <br/> |CaseMemberUpdated  <br/> |更新 ComplianceCaseMember  <br/> |EDiscovery 案例的成員資格清單已變更。 當所有成員已都取代為新的使用者群組，會記錄此活動。 如果新增或移除的單一成員，則會記錄 CaseMemberAdded 或 CaseMemberRemoved 作業。  <br/> |
|變更搜尋權限篩選器  <br/> |SearchPermissionUpdated  <br/> |Set-compliancesecurityfilter  <br/> |已變更的搜尋權限篩選器。  <br/> |
|EDiscovery 案例保留變更的搜尋查詢  <br/> |HoldUpdated  <br/> |Set-caseholdrule  <br/> |EDiscovery 案例相關聯查詢式保留已變更。 可能的變更，包括編輯查詢或日期範圍查詢式保留。  <br/> |
|下載內容搜尋預覽項目  <br/> |PreviewItemDownloaded  <br/> |不適用  <br/> |使用者下載項目至其本機電腦 （藉由按一下 [**下載原始項目**] 連結） 時預覽搜尋結果。  <br/> |
|內容搜尋預覽項目列  <br/> |PreviewItemListed  <br/> |不適用  <br/> |使用者按下**預覽搜尋結果**，以顯示 [預覽搜尋結果] 頁面，其中會列出從內容搜尋的結果超過 1000 個項目。  <br/> |
|內容搜尋預覽項目檢視  <br/> |PreviewItemRendered  <br/> |不適用  <br/> |電子文件探索管理員預覽搜尋結果時按一下 [檢視項目。  <br/> |
|建立內容搜尋  <br/> |SearchCreated  <br/> |New-ComplianceSearch  <br/> |建立新的內容搜尋。  <br/> |
|建立的 eDiscovery 管理員  <br/> |CaseAdminAdded  <br/> |新增 eDiscoveryCaseAdmin  <br/> |使用者已新增為 eDiscovery 系統管理員在組織中。  <br/> |
|建立的 eDiscovery 案例  <br/> |CaseAdded  <br/> |新 ComplianceCase  <br/> |建立 eDiscovery 案例。 建立案例時，您只需要指定其名稱。 例如新增成員、 建立保留，以及建立與案例的結果中所記錄的其他事件相關聯的內容搜尋其他案例相關的工作。  <br/> |
|建立搜尋權限篩選器  <br/> |SearchPermissionCreated  <br/> |新 ComplianceSecurityFilter  <br/> |建立搜尋權限篩選器。  <br/> |
|建立的搜尋查詢的 eDiscovery 案例保留  <br/> |HoldCreated  <br/> |新 CaseHoldRule  <br/> |建立查詢式保留 eDiscovery 案例相關聯。  <br/> |
|已刪除的內容搜尋  <br/> |SearchRemoved  <br/> |Remove-ComplianceSearch  <br/> |已刪除現有的內容搜尋。  <br/> |
|刪除的 eDiscovery 系統管理員  <br/> |CaseAdminRemoved  <br/> |移除 eDiscoveryCaseAdmin  <br/> |EDiscovery 系統管理員已刪除從您的組織。  <br/> |
|刪除的 eDiscovery 案例  <br/> |CaseRemoved  <br/> |Remove-compliancecase  <br/> |已刪除 eDiscovery 案例。 請注意，這種情況可以刪除之前要移除已與案例相關聯的任何保留。  <br/> |
|刪除的搜尋權限篩選器  <br/> |SearchPermissionRemoved  <br/> |Remove-compliancesecurityfilter  <br/> |搜尋權限篩選器已遭刪除。  <br/> |
|EDiscovery 案例保留已刪除的搜尋查詢  <br/> |HoldRemoved  <br/> |Remove-caseholdrule  <br/> |EDiscovery 案例相關聯查詢式保留已刪除。 從保留移除查詢通常是刪除保留的結果。 刪除保留或保留查詢，就會釋放已保留的內容位置。  <br/> |
|下載的匯出的內容搜尋  <br/> |SearchExportDownloaded  <br/> |不適用  <br/> |使用者下載到本機電腦的內容搜尋的結果。 請注意，**啟動匯出內容搜尋**活動來進行初始化前可以下載搜尋結果。  <br/> |
|預覽內容搜尋的結果  <br/> |SearchPreviewed  <br/> |不適用  <br/> |使用者可預覽內容搜尋的結果。  <br/> |
|清除內容搜尋的結果  <br/> |SearchResultsPurged  <br/> |新 ComplianceSearchAction  <br/> |使用者藉由執行清除的內容搜尋的結果**New-compliancesearchaction-清除**命令。  <br/> |
|已移除的內容搜尋的分析  <br/> |RemovedSearchResultsSentToZoom  <br/> |移除 ComplianceSearchAction  <br/> |內容搜尋準備動作 （若要準備 Office 365 進階電子文件探索搜尋結果） 已遭刪除。 如果準備動作少於兩週的舊，已從 Microsoft Azure 存放區刪除已備妥進階電子文件的搜尋結果。 如果 [準備] 動作已超過 2 週，此事件表示會以對應準備動作已遭刪除。  <br/> |
|已移除的匯出的內容搜尋  <br/> |RemovedSearchExported  <br/> |移除 ComplianceSearchAction  <br/> |已刪除內容搜尋匯出巨集指令。 如果 [匯出] 動作已少於兩週的舊，已刪除已上傳至 Microsoft Azure 存放區的搜尋結果。 如果 [匯出] 動作已超過 2 週，此事件表示會以對應匯出動作已遭刪除。  <br/> |
|從 eDiscovery 案例移除的成員  <br/> |CaseMemberRemoved  <br/> |移除 ComplianceCaseMember  <br/> |使用者已移除 eDiscovery 案例的成員身分。  <br/> |
|移除的內容搜尋的預覽結果  <br/> |RemovedSearchPreviewed  <br/> |移除 ComplianceSearchAction  <br/> |已刪除的內容搜尋預覽] 動作。  <br/> |
|已移除的清除巨集指令執行內容搜尋  <br/> |RemovedSearchResultsPurged  <br/> |移除 ComplianceSearchAction  <br/> |已刪除的內容搜尋清除動作。  <br/> |
|移除搜尋報告  <br/> |SearchReportRemoved  <br/> |移除 ComplianceSearchAction  <br/> |巨集指令已刪除的報表匯出內容搜尋。  <br/> |
|內容搜尋的啟動的分析  <br/> |SearchResultsSentToZoom  <br/> |新 ComplianceSearchAction  <br/> |進階 eDiscovery 中分析已備妥的內容搜尋的結果。  <br/> |
|啟動內容搜尋  <br/> |SearchStarted  <br/> |Start-ComplianceSearch  <br/> |內容搜尋已啟動。 當您建立或變更內容搜尋所使用的安全性 & 合規性中心 GUI 時，搜尋會自動啟動。 如果您建立或變更搜尋使用**New-compliancesearch**或**Set-compliancesearch** cmdlet，您必須執行**Start-compliancesearch** cmdlet 來啟動搜尋。  <br/> |
|啟動的匯出的內容搜尋  <br/> |SearchExported  <br/> |新 ComplianceSearchAction  <br/> |使用者匯出內容搜尋的結果。  <br/> |
|[開始的匯出] 報告  <br/> |SearchReport  <br/> |新 ComplianceSearchAction  <br/> |使用者匯出內容搜尋報告。  <br/> |
|停止內容搜尋  <br/> |SearchStopped  <br/> |Stop-ComplianceSearch  <br/> |使用者已停止內容搜尋。  <br/> |
  
## <a name="ediscovery-cmdlet-activities"></a>eDiscovery 指令程式活動

下表列出系統管理員或使用者在使用安全性 & 合規性中心或連線的遠端 PowerShell 中執行對應的 cmdlet 來執行 eDiscovery 相關的活動時，會記錄指令程式稽核記錄至貴組織的安全性 & 合規性中心。 請注意，是不同此表格中所列的指令程式活動和上一節所述的 eDiscovery 活動中的稽核記錄檔記錄的詳細的資訊。 
  
如先前所述，花費最多 24 小時 ediscovery 指令程式的活動，以顯示在稽核記錄搜尋結果。
  
> [!TIP]
> 下表中的 [**作業**] 欄中的 cmdlet 被連結至 TechNet 上對應的指令程式說明主題。 移至每個指令程式可用參數的描述指令程式說明主題。 會記錄每個 eDiscovery 指令程式活動的稽核記錄項目中隨附的參數和參數值所使用的指令程式。 
  
|**易記名稱**|**作業 (cmdlet)**|**描述**|
|:-----|:-----|:-----|
|EDiscovery 案例中建立的保留  <br/> |[新 CaseHoldPolicy](https://go.microsoft.com/fwlink/p/?LinkId=823813) <br/> |保留已建立的 eDiscovery 案例。 可建立保留，或者沒有指定的內容來源。 如果指定的內容來源，他們將稽核記錄項目中識別。  <br/> |
|刪除的保留從 eDiscovery 案例  <br/> |[Remove-caseholdpolicy](https://go.microsoft.com/fwlink/p/?LinkId=823814) <br/> |EDiscovery 案例相關聯的保留已刪除。 刪除保留釋放所有從保留的內容位置。 刪除保留也會導致刪除與該保留相關聯的案例保留規則 （請參閱**Remove-caseholdrule**下方）。  <br/> |
|EDiscovery 案例中的變更的保留  <br/> |[Set-caseholdpolicy](https://go.microsoft.com/fwlink/p/?LinkId=823815) <br/> |已變更保留 eDiscovery 與相關聯。 可能的變更，包括新增或移除內容位置或關閉 （停用） 保留。  <br/> |
|建立的搜尋查詢的 eDiscovery 案例保留  <br/> |[新 CaseHoldRule](https://go.microsoft.com/fwlink/p/?LinkId=823816) <br/> |建立查詢式保留 eDiscovery 案例相關聯。  <br/> |
|EDiscovery 案例保留已刪除的搜尋查詢  <br/> |[Remove-caseholdrule](https://go.microsoft.com/fwlink/p/?LinkId=823820) <br/> |EDiscovery 案例相關聯查詢式保留已刪除。 從保留移除查詢通常是刪除保留的結果。 刪除保留或保留查詢，就會釋放已保留的內容位置。  <br/> |
|EDiscovery 案例保留變更的搜尋查詢  <br/> |[Set-caseholdrule](https://go.microsoft.com/fwlink/p/?LinkId=823819) <br/> |EDiscovery 案例相關聯查詢式保留已變更。 可能的變更，包括編輯查詢或日期範圍查詢式保留。  <br/> |
|建立的 eDiscovery 案例  <br/> |[新 ComplianceCase](https://go.microsoft.com/fwlink/p/?LinkId=823842) <br/> |建立 eDiscovery 案例。 建立案例時，您只需要指定其名稱。 例如新增成員、 建立保留，以及建立與案例的結果中所記錄的其他事件相關聯的內容搜尋其他案例相關的工作。  <br/> |
|刪除的 eDiscovery 案例  <br/> |[Remove-compliancecase](https://go.microsoft.com/fwlink/p/?LinkId=823844) <br/> |已刪除 eDiscovery 案例。 請注意，這種情況可以刪除之前要移除已與案例相關聯的任何保留。  <br/> |
|已變更的 eDiscovery 案例  <br/> |[Set-compliancecase](https://go.microsoft.com/fwlink/p/?LinkId=823846) <br/> |已變更的 eDiscovery 案例。 變更包括關閉開啟的情況下，或重新開啟關閉的案例。  <br/> |
|新增的成員至 eDiscovery 案例  <br/> |[新增 ComplianceCaseMember](https://go.microsoft.com/fwlink/p/?LinkId=823848) <br/> |使用者已新增為 eDiscovery 案例的成員。 身為成員的情況下，使用者可以執行各種案例相關的工作，根據是否他們已獲指派必要權限。  <br/> |
|從 eDiscovery 案例移除的成員  <br/> |[移除 ComplianceCaseMember](https://go.microsoft.com/fwlink/p/?LinkId=823849) <br/> |使用者已移除 eDiscovery 案例的成員身分。  <br/> |
|已變更的 eDiscovery 案例的成員資格  <br/> |[更新 ComplianceCaseMember](https://go.microsoft.com/fwlink/p/?LinkId=823850) <br/> |EDiscovery 案例的成員資格清單已變更。 當所有成員已都取代為新的使用者群組，會記錄此活動。 如果新增或移除的單一成員，會記錄在**ComplianceCaseMember 新增**或**移除 ComplianceCaseMember**作業。  <br/> |
|建立內容搜尋  <br/> |[New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935) <br/> |建立新的內容搜尋。  <br/> |
|已刪除的內容搜尋  <br/> |[Remove-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517936) <br/> |已刪除現有的內容搜尋。  <br/> |
|變更內容搜尋  <br/> |[Set-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517937) <br/> |已變更現有的內容搜尋。 新增或移除要搜尋的內容位置及編輯搜尋查詢，可以包含的變更。  <br/> |
|啟動內容搜尋  <br/> |[Start-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517938) <br/> |內容搜尋已啟動。 當您建立或變更內容搜尋所使用的安全性 & 合規性中心 GUI 時，搜尋會自動啟動。 如果您建立或變更搜尋使用**New-compliancesearch**或**Set-compliancesearch** cmdlet，您必須執行**Start-compliancesearch** cmdlet 來啟動搜尋。  <br/> |
|停止內容搜尋  <br/> |[Stop-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517939) <br/> |已停止執行內容搜尋。  <br/> |
|建立內容搜尋動作  <br/> |[新 ComplianceSearchAction](https://go.microsoft.com/fwlink/p/?LinkId=527971) <br/> |已建立的內容搜尋動作。 內容搜尋動作包括預覽搜尋結果匯出搜尋結果、 準備 Office 365 進階 eDiscovery 中分析的搜尋結果，永久刪除的內容搜尋的搜尋準則相符的項目。  <br/> |
|已刪除的內容搜尋動作  <br/> |[移除 ComplianceSearchAction](https://go.microsoft.com/fwlink/p/?LinkId=824027) <br/> |已刪除的內容搜尋動作。  <br/> |
|建立搜尋權限篩選器  <br/> |[新 ComplianceSecurityFilter](https://go.microsoft.com/fwlink/p/?LinkId=617542) <br/> |建立搜尋權限篩選器。  <br/> |
|刪除的搜尋權限篩選器  <br/> |[Remove-compliancesecurityfilter](https://go.microsoft.com/fwlink/p/?LinkId=617543) <br/> |搜尋權限篩選器已遭刪除。  <br/> |
|變更搜尋權限篩選器  <br/> |[Set-compliancesecurityfilter](https://go.microsoft.com/fwlink/p/?LinkId=617544) <br/> |已變更的搜尋權限篩選器。  <br/> |
|建立的 eDiscovery 管理員  <br/> |[新增 eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkId=798217) <br/> |使用者已新增為 eDiscovery 系統管理員在組織中。  <br/> |
|刪除的 eDiscovery 系統管理員  <br/> |[移除 eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkId=823945) <br/> |EDiscovery 系統管理員已刪除從您的組織。  <br/> |
|已變更的 eDiscovery 系統管理員成員資格  <br/> |[更新 eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkId=823946) <br/> |在您的組織中的 eDiscovery 系統管理員的清單已變更。 EDiscovery 系統管理員的清單取代一組新的使用者時，會記錄此活動。 如果新增或移除單一使用者，會記錄在**eDiscoveryCaseAdmin 新增**或**移除 eDiscoveryCaseAdmin**作業。  <br/> |
   
## <a name="detailed-properties-for-ediscovery-activities"></a>電子文件探索活動的詳細的內容

下表說明當您按一下 [搜尋結果清單中的 eDiscovery 活動的**詳細資料**頁面**的詳細資訊**都是包含的屬性。 當您匯出稽核記錄搜尋結果時，這些屬性也會包含在 CSV 檔案中。 請注意，電子文件探索活動的稽核記錄檔記錄不會包含下面列出每個詳細的屬性。 
  
> [!TIP]
> 當您匯出搜尋結果時，CSV 檔案包含名為的**詳細資訊**，其中包含下表中的多重值屬性中所述的詳細的屬性的資料行。 您可以使用 Excel 中的 Power Query 功能，此資料行分割成多個資料行，使每個屬性將有它自己的資料行。 這可讓您排序及篩選一或多個這些屬性。 如需詳細資訊，請參閱 <<c0>搜尋稽核記錄檔的 「 匯出至檔案的搜尋結果 」 一節。 
  
|**屬性**|**描述**|
|:-----|:-----|
|案例  <br/> |身分識別 (GUID) 的已建立、 變更或刪除的 eDiscovery 案例。  <br/> |
|ClientApplication  <br/> |eDiscovery 指令程式活動有此屬性值的**EMC** 。 這表示使用安全性 & 合規性中心 GUI 或 PowerShell 中執行此 cmdlet 所執行的活動。  <br/> |
|ClientIP  <br/> |活動已記錄時使用的裝置 IP 位址。 IP 位址會顯示在 IPv4 或 IPv6 地址格式。  <br/> |
|ClientRequestId  <br/> | 對於 eDiscovery 活動，此屬性為通常是空白的。  <br/> |
|CmdletVersion  <br/> |您組織中執行安全性 & 合規性中心版本的組建編號。  <br/> |
|CreationTime  <br/> |日期和時間以 Coordinated Universal Time (UTC) 時 eDiscovery 活動已完成。  <br/> |
|EffectiveOrganization  <br/> |名稱您的 Office 365 組織。  <br/> |
|ExchangeLocations  <br/> |Exchange Online 信箱的內容搜尋中包含或暫留保留 eDiscovery 案例。  <br/> |
|排除項目  <br/> |排除內容搜尋] 或 [eDiscovery 案例中的保留的信箱或網站的位置。  <br/> |
|ExtendedProperties  <br/> |額外的內容，從內容搜尋，內容搜尋動作，或保留 eDiscovery 案例，例如物件 GUID 和對應的 cmdlet 和執行活動時，所使用的 cmdlet 參數。  <br/> |
|Id  <br/> |報告項目的識別碼。 識別碼可唯一識別的稽核記錄項目。  <br/> |
|NonPIIParameters  <br/> |（不含任何值） 所使用的 [作業] 屬性中所識別的指令程式的參數清單。 此屬性中所列的參數是所列在 [參數] 屬性的相同。  <br/> |
|ObjectId  <br/> |GUID 或物件名稱 （例如，「 內容搜尋 」 或 eDiscovery 案例） 已建立、 變更或刪除作業屬性中所列的活動。 這個物件也被識別稽核記錄搜尋結果中的 [項目] 欄中。  <br/> |
|ObjectType  <br/> |EDiscovery 物件的使用者建立、 刪除或修改; 的類型例如 （預覽、 匯出或清除） 的內容搜尋動作、 eDiscovery 案例或內容搜尋。  <br/> |
|作業  <br/> |會對應至電子文件探索活動所執行的作業的名稱。  <br/> |
|OrganizationId  <br/> |Office 365 組織的 GUID。  <br/> |
|參數  <br/> |名稱和值與相對應的指令程式所使用的參數。  <br/> |
|PublicFolderLocations  <br/> |EDiscovery 案例中保留 Exchange Online 中已包含在內容搜尋或暫留的公用資料夾位置。  <br/> |
|查詢  <br/> |搜尋查詢的活動，例如 「 內容搜尋或查詢式保留相關聯。  <br/> |
|RecordType  <br/> |指定記錄的作業類型。 **18**值可指示[eDiscovery 指令程式活動](#ediscovery-cmdlet-activities)] 區段中列出活動相關的事件。 **24**的值會指出[如何搜尋及檢視電子文件探索活動](#how-to-search-for-and-view-ediscovery-activities)] 區段中列出活動相關的事件。  <br/> |
|ResultStatus  <br/> |會指出 （在 [作業] 屬性中指定） 的動作是否成功與否。  <br/> |
|SecurityComplianceCenterEventType  <br/> |表示活動是安全性 & 合規性中心事件。 電子文件探索的所有活動會都有此屬性為**0**的值。  <br/> |
|SharepointLocations  <br/> |SharePoint Online 網站的內容搜尋中包含或暫留保留 eDiscovery 案例。  <br/> |
|StartTime  <br/> |日期和時間以 Coordinated Universal Time (UTC) 時啟動 eDiscovery 活動。  <br/> |
|UserId  <br/> |執行活動 （在 [作業] 屬性中指定），造成正在記錄之記錄中的使用者。 請注意系統帳戶 （例如 NT AUTHORITY\SYSTEM) 所執行的 eDiscovery 活動的記錄也會包含在稽核記錄檔。  <br/> |
|UserKey  <br/> |UserId 屬性中所識別之使用者的替代識別碼。 電子文件探索活動，此屬性的值通常是使用 UserId 屬性相同。  <br/> |
|UserServicePlan  <br/> |貴組織所使用的 Office 365 訂閱。 對於 eDiscovery 活動，此屬性為通常是空白的。  <br/> |
|UserType  <br/> |執行此作業的使用者類型。 下列的值可指出使用者類型。  <br/> 0 的一般使用者。 2 在 Office 365 組織中的系統管理員。 3 在 Microsoft 資料中心系統管理員或資料中心系統帳戶。 4 系統帳戶。 5 如果應用程式。 6 服務主要名稱。 |
|版本  <br/> |會指出記錄活動 （由 Operation 屬性識別） 的版本號碼。  <br/> |
|工作量  <br/> |Office 365 服務發生的活動。 電子文件探索活動，值會是**SecurityComplianceCenter**。  <br/> |
