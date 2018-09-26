---
title: 搜尋 Office 365 稽核記錄中的 eDiscovery 活動
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/24/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 67cc7f42-a53d-4751-b929-6005c80798f7
description: 了解如何將搜尋 Office 365 稽核記錄的規範管理員可執行內容搜尋與 eDiscovery 案件工作安全性會記錄的事件&amp;規範中心。
ms.openlocfilehash: a4cc3a6b5030a6412d739236e4c534f36948d57f
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038346"
---
# <a name="search-for-ediscovery-activities-in-the-office-365-audit-log"></a>搜尋 Office 365 稽核記錄中的 eDiscovery 活動

內容搜尋及執行 Office 365 安全性的 eDiscovery 與相關活動&amp;規範中心或執行相對應的 Windows PowerShell 指令程式會記錄在 Office 365 稽核記錄檔。當系統管理員或規範系統管理員 （或任何已指派的 eDiscovery 權限的使用者） 的下列內容的搜尋和 eDiscovery 相關的工作中執行 Office 365 安全性會記錄事件&amp;規範中心：
  
- 建立及管理 eDiscovery 案例
    
- 建立、 啟動和編輯內容的搜尋
    
- 執行內容搜尋動作，例如預覽，匯出，以及刪除搜尋結果
    
- 設定內容搜尋篩選的權限
    
- 管理 eDiscovery 系統管理員角色
    
> [!IMPORTANT]
> 本文所述的活動會使用 [安全性] 來執行 eDiscovery 工作的結果&amp;規範中心。使用 Exchange Online 或 SharePoint Online 中的 eDiscovery 中心中的就地 eDiscovery 工具所執行的 eDiscovery 工作不包含在內。 
  
如需搜尋 Office 365 稽核記錄的詳細資訊，權限的需要，並匯出搜尋結果，請參閱[Office 365 安全性搜尋稽核記錄&amp;規範中心](search-the-audit-log-in-security-and-compliance.md)。
  
## <a name="how-to-search-for-and-view-ediscovery-activities"></a>如何將搜尋及檢視 eDiscovery 活動

目前，您必須執行檢視 Office 365 稽核記錄中的 eDiscovery 活動的一些特定動作。以下是如何。
  
1. 請移至 [https://protection.office.com](https://protection.office.com)。
    
2. 登入 Office 365 中，使用您工作或學校的帳戶。
    
3. 在左窗格中，按一下 [**搜尋&amp;調查**，然後按一下 [**稽核記錄搜尋**。
    
4. 在 [**活動**] 下拉式清單中，[ **eDiscovery 活動**，按一下 [搜尋的一或多項活動。或者您可以按一下 [ **eDiscovery 活動**搜尋所有 eDiscovery 相關的活動。 
    
    > [!NOTE]
    > [活動] 下拉式清單也會包含一組活動名為**eDiscovery 指令程式活動**會傳回從 cmdlet 稽核記錄的記錄。 
  
5.  選取要顯示 eDiscovery 所發生事件的期間內的日期和時間範圍。 
    
6. 在 [**使用者**] 方塊中選取一或多個使用者顯示的搜尋結果。保留此方塊空白以傳回所有使用者的項目。 
    
7. 按一下 [**搜尋**來執行使用搜尋準則的 [搜尋]。 
    
8. 在搜尋結果出現之後，您可以按一下 [篩選或排序所產生的活動記錄的**篩選結果**。但是您無法使用 [篩選]，明確排除特定的活動。 
    
9. 若要檢視有關活動的詳細資訊，請按一下 [搜尋結果的清單中的活動記錄]。 
    
    **詳細資料**飛入] 頁面會顯示包含從事件記錄的詳細的屬性。若要顯示其他的詳細資訊，請按一下 [**詳細資訊**。如需這些屬性的說明，請參閱 ＜ [eDiscovery 活動的詳細的內容](#detailed-properties-for-ediscovery-activities)] 區段中。 

  
## <a name="ediscovery-activities"></a>eDiscovery 活動

下表說明內容搜尋與會記錄系統管理員或使用者執行 eDiscovery 與相關活動使用安全性時的 eDiscovery 與相關活動&amp;規範中心或執行對應指令程式遠端 PowerShell 連線至您的組織安全性&amp;規範中心。 
  
> [!NOTE]
> 本節所述的 eDiscovery 活動提供類似下一節所述的 eDiscovery 指令程式活動的資訊。我們建議您使用因為它們 30 分鐘內出現在稽核記錄搜尋結果中本節所述的 eDiscovery 活動。延長 24 小時的時間的 ediscovery （英文） 指令程式會出現在稽核記錄搜尋結果中的活動。 
  
|**易記名稱**|**作業**|**對應的指令程式**|**描述**|
|:-----|:-----|:-----|:-----|
|新增的成員至 eDiscovery 案例  <br/> |CaseMemberAdded  <br/> |新增 ComplianceCaseMember  <br/> |使用者已新增為 eDiscovery 案例的成員。以案例的成員身分，使用者可以執行根據是否他們已指派必要權限的各種案例相關工作。  <br/> |
|已變更內容的搜尋  <br/> |SearchUpdated  <br/> |Set-ComplianceSearch  <br/> |已變更現有的內容搜尋。新增或移除的內容位置或編輯搜尋查詢可以包含的變更。  <br/> |
|已變更的 eDiscovery 管理員的成員資格  <br/> |CaseAdminUpdated  <br/> |更新 eDiscoveryCaseAdmin  <br/> |已變更您的組織中的 eDiscovery 管理員的清單。這項活動會記錄時的 eDiscovery 管理員清單取代為新的使用者群組。如果新增或移除單一使用者時，會記錄 CaseAdminAdded 作業。  <br/> |
|已變更的 eDiscovery 案例  <br/> |CaseUpdated  <br/> |設定 ComplianceCase  <br/> |已變更 eDiscovery 案例。變更包括關閉開啟的案例或重新開啟關閉的案例。  <br/> |
|已變更的 eDiscovery 案件成員資格  <br/> |CaseMemberUpdated  <br/> |更新 ComplianceCaseMember  <br/> |已變更 eDiscovery 案例的成員資格清單。當所有成員都已都取代為一組新的使用者會記錄此活動。如果新增或移除的單一成員時，會記錄 CaseMemberAdded 或 CaseMemberRemoved 作業。  <br/> |
|變更搜尋權限篩選  <br/> |SearchPermissionUpdated  <br/> |設定 ComplianceSecurityFilter  <br/> |搜尋的權限篩選已變更。  <br/> |
|已變更的搜尋查詢的 eDiscovery 案件保留  <br/> |HoldUpdated  <br/> |設定 CaseHoldRule  <br/> |已變更查詢式保留 eDiscovery 案例相關聯。可能的變更包括編輯查詢或日期範圍內的查詢式保留。  <br/> |
|下載內容搜尋預覽項目  <br/> |PreviewItemDownloaded  <br/> |不適用  <br/> |使用者下載項目至其本機電腦 （依序按一下 [**下載原始項目的**連結) 時預覽搜尋結果。  <br/> |
|內容搜尋預覽項目列  <br/> |PreviewItemListed  <br/> |不適用  <br/> |使用者按下**預覽搜尋結果**顯示預覽搜尋結果頁面，其中會列出最多 1000 位內容的搜尋結果項目。  <br/> |
|內容搜尋預覽項目檢視  <br/> |PreviewItemRendered  <br/> |不適用  <br/> |EDiscovery 管理員預覽搜尋結果時按一下 [檢視項目。  <br/> |
|建立內容的搜尋  <br/> |SearchCreated  <br/> |New-ComplianceSearch  <br/> |建立新的內容搜尋。  <br/> |
|建立的 eDiscovery 管理員  <br/> |CaseAdminAdded  <br/> |新增 eDiscoveryCaseAdmin  <br/> |使用者已新增為組織中的 eDiscovery 管理員。  <br/> |
|建立的 eDiscovery 案例  <br/> |CaseAdded  <br/> |新 ComplianceCase  <br/> |建立 eDiscovery 案例。建立案例之後，您只能有指定其名稱。新增成員、 建立保留，以及建立 case 結果中所記錄的其他事件相關聯的內容搜尋其他案例相關的工作。  <br/> |
|建立搜尋權限篩選  <br/> |SearchPermissionCreated  <br/> |新 ComplianceSecurityFilter  <br/> |建立搜尋權限篩選時。  <br/> |
|建立的搜尋查詢的 eDiscovery 案件保留  <br/> |HoldCreated  <br/> |新 CaseHoldRule  <br/> |建立查詢式保留 eDiscovery 案例相關聯。  <br/> |
|已刪除的內容搜尋  <br/> |SearchRemoved  <br/> |Remove-ComplianceSearch  <br/> |已刪除現有的內容搜尋。  <br/> |
|刪除的 eDiscovery 管理員  <br/> |CaseAdminRemoved  <br/> |移除 eDiscoveryCaseAdmin  <br/> |EDiscovery 管理員已從您的組織中刪除。  <br/> |
|已刪除的 eDiscovery 案例  <br/> |CaseRemoved  <br/> |移除 ComplianceCase  <br/> |已刪除 eDiscovery 案例。與案例相關聯任何保留具有要移除之前可刪除案例的附註。  <br/> |
|刪除的搜尋權限篩選  <br/> |SearchPermissionRemoved  <br/> |移除 ComplianceSecurityFilter  <br/> |搜尋的權限篩選已遭刪除。  <br/> |
|EDiscovery 案件保留已刪除的搜尋查詢  <br/> |HoldRemoved  <br/> |移除 CaseHoldRule  <br/> |EDiscovery 案例相關聯的查詢式保留已刪除。從保留移除查詢通常是刪除保留的結果。刪除保留或保留查詢時所保留的內容位置所發行。  <br/> |
|下載的匯出的內容搜尋  <br/> |SearchResultDownloaded  <br/> |不適用  <br/> |使用者下載到他們的本機電腦的內容的搜尋結果。請注意**啟動匯出的內容搜尋**活動起始之前可以下載搜尋結果。<br/> |
|預覽內容搜尋結果  <br/> |SearchPreviewed  <br/> |不適用  <br/> |使用者可預覽內容搜尋結果。  <br/> |
|已清除內容的搜尋結果  <br/> |SearchResultsPurged  <br/> |New-ComplianceSearchAction  <br/> |使用者執行清除內容的搜尋結果**新增 ComplianceSearchAction-清除**命令。  <br/> |
|已移除的內容搜尋分析  <br/> |RemovedSearchResultsSentToZoom  <br/> |移除 ComplianceSearchAction  <br/> |內容搜尋準備動作 （若要準備 Office 365 進階 eDiscovery 搜尋結果） 已遭刪除。若 [準備] 動作小於兩週的舊，請從 Microsoft Azure 存放區刪除已備妥進階 eDiscovery 搜尋結果。如果 [準備] 動作已超過 2 週，此事件會指出已刪除的對應準備動作。  <br/> |
|已移除的匯出的內容搜尋  <br/> |RemovedSearchExported  <br/> |移除 ComplianceSearchAction  <br/> |內容搜尋匯出動作已遭刪除。如果 [匯出] 動作已小於兩週的舊，已刪除已上傳至 Microsoft Azure 的存放區] 區域中的搜尋結果。如果 [匯出] 動作已超過 2 週，此事件會指出已刪除的對應匯出動作。  <br/> |
|已移除的成員從 eDiscovery 案例  <br/> |CaseMemberRemoved  <br/> |移除 ComplianceCaseMember  <br/> |使用者已移除 eDiscovery 案例的成員。  <br/> |
|移除預覽內容搜尋結果  <br/> |RemovedSearchPreviewed  <br/> |移除 ComplianceSearchAction  <br/> |內容搜尋預覽動作已遭刪除。  <br/> |
|執行內容搜尋已移除的清除動作  <br/> |RemovedSearchResultsPurged  <br/> |移除 ComplianceSearchAction  <br/> |內容搜尋清除動作已遭刪除。  <br/> |
|移除搜尋報告  <br/> |SearchReportRemoved  <br/> |移除 ComplianceSearchAction  <br/> |內容搜尋匯出報告動作已遭刪除。  <br/> |
|內容搜尋的開始的分析  <br/> |SearchResultsSentToZoom  <br/> |New-ComplianceSearchAction  <br/> |內容的搜尋結果已備妥進階在 eDiscovery 中的分析。  <br/> |
|啟動內容的搜尋  <br/> |SearchStarted  <br/> |Start-ComplianceSearch  <br/> |啟動內容的搜尋。當您建立或變更內容的搜尋使用安全性&amp;規範中心 GUI，搜尋會自動啟動。如果您建立或使用**新 ComplianceSearch**或**組 ComplianceSearch**指令程式來變更搜尋，您必須執行**開始 ComplianceSearch**指令程式來啟動搜尋。<br/> |
|內容搜尋的開始的匯出  <br/> |SearchExported  <br/> |New-ComplianceSearchAction  <br/> |使用者在匯出內容的搜尋結果。  <br/> |
|開始的匯出報告  <br/> |SearchReport  <br/> |New-ComplianceSearchAction  <br/> |使用者在匯出內容搜尋報告。  <br/> |
|停止內容搜尋  <br/> |SearchStopped  <br/> |Stop-ComplianceSearch  <br/> |使用者已停止內容的搜尋。  <br/> |
  
## <a name="ediscovery-cmdlet-activities"></a>eDiscovery 指令程式活動

下表列出系統管理員或使用者會使用 [安全性] 執行 eDiscovery 與相關活動會記錄指令程式稽核記錄&amp;規範中心或相對應的指令程式執行遠端 PowerShell 中的連線至您的組織安全性&amp;規範中心。請注意的不同此表格中所列的指令程式活動與前一節所述的 eDiscovery 活動的稽核記錄一筆記錄的詳細的資訊。 
  
先前所述，延長 24 小時的時間 ediscovery 指令程式會出現在稽核記錄搜尋結果中的活動。
  
> [!TIP]
> 下表中的 [**作業**] 欄中的 cmdlet 連結至 TechNet 上對應的指令程式說明主題。移至每個指令程式可用參數的描述指令程式說明主題。記錄每個 eDiscovery 指令程式活動的稽核記錄項目中會包含參數和參數值已指令程式搭配使用。 
  
|**易記名稱**|**作業 (cmdlet)**|**描述**|
|:-----|:-----|:-----|
|EDiscovery 案例中建立的暫止  <br/> |[新 CaseHoldPolicy](https://go.microsoft.com/fwlink/p/?LinkId=823813) <br/> |保留所建立的 eDiscovery 案例。或者沒有指定的內容來源可以建立保留。如果指定的內容來源，他們將稽核記錄項目中加以識別。  <br/> |
|刪除的保留從 eDiscovery 案例  <br/> |[移除 CaseHoldPolicy](https://go.microsoft.com/fwlink/p/?LinkId=823814) <br/> |EDiscovery 案例相關聯的保留已刪除。刪除保留釋放所有從保留內容的位置。刪除保留也會導致刪除與該保留相關聯的 case 保留規則 （請參閱**移除 CaseHoldRule**下）。<br/> |
|EDiscovery 案例中的變更的暫止  <br/> |[設定 CaseHoldPolicy](https://go.microsoft.com/fwlink/p/?LinkId=823815) <br/> |EDiscovery 與相關聯的保留已變更。可能的變更包括新增或移除的內容位置或關閉 （停用） 保留。  <br/> |
|建立的搜尋查詢的 eDiscovery 案件保留  <br/> |[新 CaseHoldRule](https://go.microsoft.com/fwlink/p/?LinkId=823816) <br/> |建立查詢式保留 eDiscovery 案例相關聯。  <br/> |
|EDiscovery 案件保留已刪除的搜尋查詢  <br/> |[移除 CaseHoldRule](https://go.microsoft.com/fwlink/p/?LinkId=823820) <br/> |EDiscovery 案例相關聯的查詢式保留已刪除。從保留移除查詢通常是刪除保留的結果。刪除保留或保留查詢時所保留的內容位置所發行。  <br/> |
|已變更的搜尋查詢的 eDiscovery 案件保留  <br/> |[設定 CaseHoldRule](https://go.microsoft.com/fwlink/p/?LinkId=823819) <br/> |已變更查詢式保留 eDiscovery 案例相關聯。可能的變更包括編輯查詢或日期範圍內的查詢式保留。  <br/> |
|建立的 eDiscovery 案例  <br/> |[新 ComplianceCase](https://go.microsoft.com/fwlink/p/?LinkId=823842) <br/> |建立 eDiscovery 案例。建立案例之後，您只能有指定其名稱。新增成員、 建立保留，以及建立 case 結果中所記錄的其他事件相關聯的內容搜尋其他案例相關的工作。  <br/> |
|已刪除的 eDiscovery 案例  <br/> |[移除 ComplianceCase](https://go.microsoft.com/fwlink/p/?LinkId=823844) <br/> |已刪除 eDiscovery 案例。與案例相關聯任何保留具有要移除之前可刪除案例的附註。  <br/> |
|已變更的 eDiscovery 案例  <br/> |[設定 ComplianceCase](https://go.microsoft.com/fwlink/p/?LinkId=823846) <br/> |已變更 eDiscovery 案例。變更包括關閉開啟的案例或重新開啟關閉的案例。  <br/> |
|新增的成員至 eDiscovery 案例  <br/> |[新增 ComplianceCaseMember](https://go.microsoft.com/fwlink/p/?LinkId=823848) <br/> |使用者已新增為 eDiscovery 案例的成員。以案例的成員身分，使用者可以執行根據是否他們已指派必要權限的各種案例相關工作。  <br/> |
|已移除的成員從 eDiscovery 案例  <br/> |[移除 ComplianceCaseMember](https://go.microsoft.com/fwlink/p/?LinkId=823849) <br/> |使用者已移除 eDiscovery 案例的成員。  <br/> |
|已變更的 eDiscovery 案件成員資格  <br/> |[更新 ComplianceCaseMember](https://go.microsoft.com/fwlink/p/?LinkId=823850) <br/> |已變更 eDiscovery 案例的成員資格清單。當所有成員都已都取代為一組新的使用者會記錄此活動。如果新增或移除的單一成員時，會記錄**ComplianceCaseMember 新增**或**移除 ComplianceCaseMember**作業。<br/> |
|建立內容的搜尋  <br/> |[New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935) <br/> |建立新的內容搜尋。  <br/> |
|已刪除的內容搜尋  <br/> |[Remove-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517936) <br/> |已刪除現有的內容搜尋。  <br/> |
|已變更內容的搜尋  <br/> |[Set-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517937) <br/> |已變更現有的內容搜尋。新增或移除要搜尋的內容位置與編輯搜尋查詢可以包含的變更。  <br/> |
|啟動內容的搜尋  <br/> |[Start-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517938) <br/> |啟動內容的搜尋。當您建立或變更內容的搜尋使用安全性&amp;規範中心 GUI，搜尋會自動啟動。如果您建立或使用**新 ComplianceSearch**或**組 ComplianceSearch**指令程式來變更搜尋，您必須執行**開始 ComplianceSearch**指令程式來啟動搜尋。<br/> |
|停止內容搜尋  <br/> |[Stop-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517939) <br/> |在執行內容搜尋已停止。  <br/> |
|建立內容搜尋巨集指令  <br/> |[New-ComplianceSearchAction](https://go.microsoft.com/fwlink/p/?LinkId=527971) <br/> |建立內容搜尋動作時。內容搜尋動作如下預覽搜尋結果、 匯出搜尋結果、 準備 Office 365 進階 eDiscovery 中搜尋結果及永久刪除符合搜尋準則的內容搜尋的項目。  <br/> |
|已刪除的內容搜尋巨集指令  <br/> |[移除 ComplianceSearchAction](https://go.microsoft.com/fwlink/p/?LinkId=824027) <br/> |內容搜尋動作已遭刪除。  <br/> |
|建立搜尋權限篩選  <br/> |[新 ComplianceSecurityFilter](https://go.microsoft.com/fwlink/p/?LinkId=617542) <br/> |建立搜尋權限篩選時。  <br/> |
|刪除的搜尋權限篩選  <br/> |[移除 ComplianceSecurityFilter](https://go.microsoft.com/fwlink/p/?LinkId=617543) <br/> |搜尋的權限篩選已遭刪除。  <br/> |
|變更搜尋權限篩選  <br/> |[設定 ComplianceSecurityFilter](https://go.microsoft.com/fwlink/p/?LinkId=617544) <br/> |搜尋的權限篩選已變更。  <br/> |
|建立的 eDiscovery 管理員  <br/> |[新增 eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkId=798217) <br/> |使用者已新增為您組織中的 eDiscovery 管理員。  <br/> |
|刪除的 eDiscovery 管理員  <br/> |[移除 eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkId=823945) <br/> |EDiscovery 管理員已從您的組織中刪除。  <br/> |
|已變更的 eDiscovery 管理員的成員資格  <br/> |[更新 eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkId=823946) <br/> |已變更您的組織中的 eDiscovery 管理員的清單。這項活動會記錄時的 eDiscovery 管理員清單取代為新的使用者群組。如果新增或移除單一使用者時，會記錄**eDiscoveryCaseAdmin 新增**或**移除 eDiscoveryCaseAdmin**作業。<br/> |
   
## <a name="detailed-properties-for-ediscovery-activities"></a>EDiscovery 活動的詳細的屬性

下表說明當您按一下 [搜尋結果中所列的 eDiscovery 活動的**詳細資料**頁面**的詳細資訊**時所包含的屬性。當您匯出稽核記錄搜尋結果的 CSV 檔案也會包含這些屬性。請注意 eDiscovery 活動的稽核記錄檔記錄不會包含下面所列的每個詳細的屬性。 
  
> [!TIP]
> 當您匯出搜尋結果時，CSV 檔案會包含名為**詳細資訊**，其中包含下表中的多重值屬性中所述的詳細的內容欄。您可以使用 Excel 中的 Power 查詢功能此資料行分割成多個資料欄，，讓每個屬性將有其專屬資料行。這可讓您排序及篩選一或多個這些屬性。如需詳細資訊，請參閱 ＜[的搜尋稽核記錄中的 Office 365 安全性 & 規範中心](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file)的 「 匯出至檔案的搜尋結果 」 一節。 
  
|**屬性**|**描述**|
|:-----|:-----|
|案例  <br/> |身分識別 (GUID) 已建立、 變更或刪除 eDiscovery 案例。  <br/> |
|ClientApplication  <br/> |eDiscovery 指令程式活動具有此屬性值的**EMC** 。這表示活動來執行使用安全性&amp;規範中心 GUI 或 PowerShell 中執行此指令程式。<br/> |
|ClientIP  <br/> |活動已記錄時使用的裝置 IP 位址。IP 位址是 IPv4 或 IPv6 地址格式顯示。  <br/> |
|ClientRequestId  <br/> | EDiscovery 活動，此屬性是通常是空白的。  <br/> |
|CmdletVersion  <br/> |證券的版本的組建編號&amp;規範中心您組織中執行。  <br/> |
|CreationTime  <br/> |日期及時間的國際標準時間 (UTC) 時 eDiscovery 活動已完成。  <br/> |
|EffectiveOrganization  <br/> |名稱您的 Office 365 組織。  <br/> |
|ExchangeLocations  <br/> |會包含在內容搜尋或放置在 Exchange Online 信箱保留之 eDiscovery 案例。  <br/> |
|排除  <br/> |排除內容搜尋] 或 [eDiscovery 案例中的保留的信箱或網站的位置。  <br/> |
|ExtendedProperties  <br/> |搜尋、 內容搜尋巨集指令，或保留 eDiscovery 案例，例如物件 GUID 對應的 cmdlet 與活動執行時所用的 cmdlet 參數中與內容的其他屬性。  <br/> |
|ID  <br/> |報告項目的識別碼。識別碼可唯一識別稽核記錄項目。  <br/> |
|NonPIIParameters  <br/> |使用中的 Operation 屬性識別指令程式所使用的參數 （不含任何值） 清單。此屬性中所列的參數是 Parameters 屬性中所列相同。  <br/> |
|ObjectId  <br/> |GUID 或物件 （例如內容搜尋或 eDiscovery 案例） 已建立、 變更或刪除活動的 Operation 屬性中所列的名稱。這個物件也會識別稽核記錄搜尋結果中的 [項目] 欄中。  <br/> |
|ObjectType  <br/> |使用者建立、 刪除或修改; eDiscovery 物件的類型例如 （預覽、 匯出或清除） 的內容搜尋動作、 eDiscovery 案例、 或內容的搜尋。  <br/> |
|作業  <br/> |會對應至 eDiscovery 活動所執行的作業的名稱。  <br/> |
|OrganizationId  <br/> |Office 365 組織的 GUID。  <br/> |
|參數  <br/> |名稱和值與相對應的指令程式所使用的參數。  <br/> |
|PublicFolderLocations  <br/> |Exchange Online 中已包含在內容搜尋或放置在公用資料夾位置保留之 eDiscovery 案例。  <br/> |
|查詢  <br/> |搜尋查詢的活動，例如內容搜尋或查詢式保留相關聯。  <br/> |
|RecordType  <br/> |指定記錄的作業類型。**18**的值會指出與相關活動[eDiscovery 指令程式活動](#ediscovery-cmdlet-activities)＞ 一節中的事件。值為**24**指出[如何搜尋及檢視 eDiscovery 活動](#how-to-search-for-and-view-ediscovery-activities)＞ 一節中的活動相關的事件。<br/> |
|ResultStatus  <br/> |會指出動作 （作業屬性中所指定） 是否已成功。  <br/> |
|SecurityComplianceCenterEventType  <br/> |會指出活動已安全性&amp;規範中心事件。所有的 eDiscovery 活動必須為**0**這個屬性的值。<br/> |
|SharepointLocations  <br/> |SharePoint Online 網站已包含在內容搜尋或放入保留之 eDiscovery 案例。  <br/> |
|開始時間  <br/> |日期及時間的國際標準時間 (UTC) 時啟動 eDiscovery 活動。  <br/> |
|UserId  <br/> |執行活動 （作業屬性中所指定），因為正在記錄的記錄所造成之使用者。請注意系統帳戶 （例如 NT AUTHORITY\SYSTEM) 所執行的 eDiscovery 活動的記錄也會包含在稽核記錄檔。  <br/> |
|UserKey  <br/> |UserId 屬性中所識別之使用者的替代 ID。EDiscovery 活動，此屬性的值通常是使用 UserId 屬性相同。  <br/> |
|UserServicePlan  <br/> |貴組織所使用的 Office 365 訂閱。EDiscovery 活動，此屬性是通常是空白的。  <br/> |
|UserType  <br/> |使用者執行作業的類型。下列的值會指出使用者類型。  <br/> 0 的一般使用者。2 Office 365 組織中是系統管理員。3 Microsoft 資料中心系統管理員或資料中心系統帳戶。4 系統帳戶。5 應用程式。6 服務主要名稱。 |
|版本  <br/> |會指出活動 （作業屬性識別） 已登入的版本號碼。  <br/> |
|工作量  <br/> |Office 365 服務發生活動。EDiscovery 活動的值會是**SecurityComplianceCenter**。<br/> |
