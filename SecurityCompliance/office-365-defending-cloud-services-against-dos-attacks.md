---
title: Office 365 抵禦拒絕服務攻擊防禦雲端服務
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 如何 Microsoft 進行防禦拒絕服務 (DoS) 攻擊對其雲端服務。
ms.openlocfilehash: 932e5a4d206a9d91c81e868e353259db954a2452
ms.sourcegitcommit: f0d23e57b00f07cef5b1b2d366eaeeeacda37e3e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/18/2019
ms.locfileid: "35786688"
---
# <a name="defending-microsoft-cloud-services-against-denial-of-service-attacks"></a>防禦拒絕服務攻擊的 Microsoft 雲端服務

## <a name="introduction"></a>簡介
Microsoft 資料中心受到包含周邊圍欄、 攝影機、 安全性人員及使用生物識別技術、 智慧卡和多重要素驗證的安全設置的深度防禦安全性。 深度防禦安全性會繼續通過每個區域的設施以及每個實體伺服器單位。 [Microsoft 雲端基礎結構和作業] 群組](https://www.microsoft.com/en-us/cloud-platform/global-datacenters)會傳遞的核心基礎結構和我們雲端服務基礎技術。 我們的資料中心遵守業界標準的實體安全性和可靠性和受管理、 監視，且由 Microsoft 作業人員管理。

若要進一步保護我們的雲端服務，Microsoft 會提供 DDoS 國防版系統的 Microsoft Azure 持續監視和滲透測試程序的一部分。 Azure DDoS 防護系統不僅為了承受從外，也能使用其他 Azure 租用戶的攻擊。 Azure 使用標準偵測和防護技術，例如 SYN-RCVD cookie、 率限制，以及連線限制，以防止 DDoS 攻擊。

Microsoft 的雲端服務須遵守從多個來源的攻擊威脅。 減輕並防範各種 DoS 威脅高度可延展及動態以 Azure 為基礎的威脅偵測和降低系統已開發並實作與從 DoS 保護基礎結構的主要目標攻擊，進而協助以避免服務中斷的雲端服務客戶。 Azure DoS 降低系統保護輸入、 輸出和地區的流量。

大部分的 DoS 攻擊啟動對網路 (L3) 和傳輸的目標 (L4)[開啟系統互相連線](https://docs.microsoft.com/windows-hardware/drivers/network/windows-network-architecture-and-the-osi-model)(OSI) 模型層。 而網路介面或攻擊流量使癱瘓資源和拒絕回應合法的傳輸服務，旨在導向 L3 L4 層級的攻擊。 具體而言，L3 和 L4 攻擊嘗試滲透網路連結、 裝置或服務的容量，或使癱瘓 Cpu 的伺服器或虛擬機器支援應用程式。

若要防止 L3 和 L4 攻擊，Microsoft 已設計、 開發，及部署解決方案目標特別保護來自遭受攻擊保護這些層級的基礎結構和客戶目標。 保護基礎結構可確保對象為一位客戶的攻擊流量不會導致附帶損害或執行其他客戶服務的網路品質。 解決方案會使用流量資料中心路由器的取樣資料。 此資料是由監視服務來偵測攻擊網路進行分析。 偵測到攻擊時，自動化的防禦機制開始運作。

## <a name="application-level-defenses"></a>應用程式層級的防禦措施
Microsoft 工程團隊依循嚴格的標準[Microsoft 操作安全性保證](https://www.microsoft.com/en-us/SDL/OperationalSecurityAssurance)設協助保護客戶資料。 Microsoft 雲端服務會刻意內建支援也非常高的負載保護及減輕應用程式層級的 DoS 攻擊。 我們已實作其中服務會分配到多個區域的隔離及節流工作負載的一些功能的全球資料中心的向外擴充架構。

每個客戶的國家/地區或區域，客戶的系統管理員識別服務的初始安裝期間，會決定該客戶資料的主要儲存區位置。 客戶資料會根據主要/備份策略的備援資料中心之間複寫。 主要資料中心主控的應用程式軟體，以及軟體上執行的所有主要客戶資料。 備份資料中心提供自動容錯移轉。 如果主要資料中心會停止運作因任何原因，要求會重新導向至備份資料中心中的軟體和客戶資料的複本。 在任何指定的時間，可能會以主要或備份資料中心處理客戶資料。 將資料分散到多個資料中心會減少受影響的表面區域，以防遭受攻擊一個資料中心。 此外，在受影響的資料中心中的服務可以快速地重新導向至次要資料中心做為其中一個副與復原機制，前者 （重新導向回主要資料中心之後還原服務）。

個別的工作負載包含內建管理資源使用情況的功能。 例如，節流機制在 Exchange Online 和 SharePoint Online 屬於防禦 DoS 攻擊的多層次方法。 Exchange Online 使用者節流根據一般使用者而言所耗用資源的層級，資源是否在 Active Directory、 Exchange Online 的資訊儲存庫，或其他地方。 預算會為每個用戶端，以限制使用者消耗的資源配置。 Exchange Online 的使用者活動] 和 [系統元件節流為基礎[的工作負載管理](http://technet.microsoft.com/en-us/library/jj150503(v=exchg.150).aspx)。 Exchange Online 的工作負載為 Exchange Online 的功能、 通訊協定或明確定義為 Exchange Online 的系統資源管理的服務。 每一個 Exchange Online 的工作負載需要 CPU、 信箱資料庫操作等系統資源，或 Active Directory 要求執行使用者要求或背景工作。 Exchange Online 的工作負載的範例包括 Outlook web、 Exchange ActiveSync、 信箱移轉和信箱助理員。 租用戶系統管理員可以管理 Exchange 工作負載管理節流設定的使用者使用 Exchange 管理命令介面。 有各種形式的節流設定，在 Exchange Online，包括 PowerShell、 Exchange Web 服務，以及 POP 和 IMAP、 Exchange ActiveSync 行動裝置連線、 收件者，等等，已經實作。 時的內部部署 Exchange 部署的系統管理員可以設定節流原則，系統管理員無法用於 Exchange Online 設定節流原則。

SharePoint Online 中節流的最常見觸發程序是用戶端物件模型 (CSOM) 程式碼會執行得太高頻率太多動作。 使用 csom 撰寫，可使用單一要求，其中可以超過使用狀況的限制，且每個使用者節流會造成執行許多動作。

不論活動，可能會導致節流，當使用者超過使用狀況的限制，任何進一步的要求該使用者帳戶，通常是在短期間內的 SharePoint Online 節流。 使用者節流生效時，該使用者的所有動作已受到都節流，直到節流，過期取決於下列準則：
- 針對使用者直接在瀏覽器中執行的要求，SharePoint Online 重新導向至節流資訊] 頁面中，並要求失敗。
- 對於所有其他要求，包括 CSOM 呼叫，SharePoint Online 傳回 HTTP 狀態碼 429 （「 太多要求 」），並要求失敗。

如果違規的程序持續超過使用狀況的限制，SharePoint Online 可能完全封鎖程序，並傳回 HTTP 狀態碼 503 （「 服務無法使用 」）。

## <a name="vulnerability-and-penetration-testing"></a>弱點和滲透測試
Microsoft 會使用許多[安全性技術與作法](https://www.microsoft.com/en-us/trustcenter/security/threatmanagement)對新式、 複雜的威脅，包括使用反惡意程式碼的元件和服務的雲端服務時，虛擬[保護其雲端基礎結構](https://blogs.technet.microsoft.com/hybridcloud/2015/05/05/protecting-your-datacenter-and-cloud-from-emerging-threats/)，並在內部網路機器 (Vm)，與其他系統。 進階的威脅分析，以監視正常流量模式網路、 系統及使用者，以及採用機器學習超出正常，和一般滲透測試任何行為的旗標。

除了執行自己滲透測試和[Microsoft 雲端整合滲透測試程式](https://technet.microsoft.com/en-us/mt784683)提供給我們的客戶，我們也邀請與協力廠商安全性專業人員執行一般弱點評估和滲透測試對我們雲端服務。 我們從這些協力廠商弱點評估報告可供下載從進行[服務信任](https://aka.ms/STP)及[服務保證](https://aka.ms/ServiceAssurance)入口網站。
