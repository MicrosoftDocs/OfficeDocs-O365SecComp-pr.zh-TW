---
title: 對拒絕服務攻擊的 office 365 防禦雲端服務
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 如何 Microsoft 進行防禦拒絕服務 (DoS) 攻擊對其雲端服務。
ms.openlocfilehash: 64a99347e22612bba2035092764ed3714b596228
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/20/2019
ms.locfileid: "30090995"
---
# <a name="defending-microsoft-cloud-services-against-denial-of-service-attacks"></a>防禦抵禦拒絕服務攻擊的 Microsoft 雲端服務

## <a name="introduction"></a>簡介
Microsoft 資料中心會受到包含周邊圍欄、 視訊攝影機、 保全人員及使用生物、 智慧卡、 和多重要素驗證的安全進入深入防禦安全性。深入防禦安全性會繼續透過每個區域的設備及每個實體伺服器的單位。[Microsoft 雲端基礎結構和作業] 群組](https://www.microsoft.com/en-us/cloud-platform/global-datacenters)也可以與我們雲端服務的基礎技術的核心基礎結構。我們資料中心符合產業標準的實體安全性及可靠性與受管理的、 監視、 且由 Microsoft 作業人員管理。

若要進一步保護我們雲端服務、 Microsoft 提供 DDoS 防禦系統是 Microsoft Azure 連續監視和滲透測試程序的一部分。Azure DDoS 防禦預定系統不只承受從外，還來自其他 Azure 租用戶的攻擊。Azure 會使用標準偵測及例如 SYN cookie、 率限制，以及的連線限制減少技術以防止 DDoS 攻擊。

Microsoft 雲端服務會受到多個來源的攻擊威脅。減輕並針對各種 DoS 威脅高度可擴充和動態 Azure 型威脅偵測與減輕方式保護系統具有已開發及實作防止 DoS 攻擊的基礎架構的主要目標和協助防止雲端的服務中斷服務客戶。Azure DoS 減輕系統會保護輸入、 輸出及區域-region 流量。

大部分的 DoS 攻擊啟動針對目標的網路 (L3) 和傳輸的[開啟系統互相連線](https://docs.microsoft.com/windows-hardware/drivers/network/windows-network-architecture-and-the-osi-model)(OSI) 模型 (4) 層級。導向 L3 4 層級的攻擊的設計被用來讓要求大量湧入網路介面或攻擊流量會使不勝負荷資源及拒絕回應合法的傳輸服務。尤其是 L3 及 4 攻擊嘗試滲透容量的網路連結、 裝置或服務或伺服器或虛擬機器支援應用程式的 Cpu 會使不勝負荷。

若要防範 Microsoft 具有設計、 開發、 及部署方案的 L3 及 4 攻擊瞄準特別防護甚至遭受攻擊保護這些層的基礎結構和客戶目標。保護基礎結構可以確保一個客戶的適用對象的攻擊流量不會導致附帶損害或降低服務的其他客戶的網路品質。解決方案使用流量資料中心路由器取樣資料。此資料是由監控服務來偵測攻擊網路分析。當偵測到攻擊時，自動的防禦機制開始進行。

## <a name="application-level-defenses"></a>應用程式層級的防禦措施
Microsoft 工程小組遵循嚴格的標準由[Microsoft 運作的安全性保證](https://www.microsoft.com/en-us/SDL/OperationalSecurityAssurance)設為協助保護客戶資料。Microsoft 雲端服務是刻意建立的支援，以及更高負載來保護並降低對應用程式層級有無 DoS 攻擊。我們已實作其中服務會分散於多個區域的隔離與節流設定的工作負載的一些功能的通用資料中心的向外延展架構。

每個客戶的國家或地區、 客戶的系統管理員識別服務的初始安裝期間，會決定該客戶資料的主要儲存區位置。根據主要/備份策略的備援資料中心之間複製的客戶資料。主要資料中心主控應用程式軟體以及軟體上執行的所有主要的客戶資料。備份資料中心提供自動容錯移轉。如果主要資料中心會停止運作的任何原因，要求會重新導向至備份資料中心中的軟體和客戶資料的複本。在任何指定時間可能會在主要或備份資料中心處理客戶資料。將資料分散到多個資料中心減少受影響的介面區以防攻擊資料中心。此外，在受影響的資料中心服務可以快速地重新導向至次要資料中心做為其中一個復原機制與企業 （重新導向回主要資料中心之後還原服務） 的事情。

個別的工作負載包含內建管理資源使用情況的功能。例如，節流機制在 Exchange Online 和 SharePoint Online 屬於多重分層防禦 DoS 攻擊的方法。Exchange Online 使用者節流層級為基礎的資源消耗的使用者，是否是在 Active Directory、 Exchange Online 的資訊儲存庫，或其他地方的資源。預算配置給每個用戶端若要限制使用者消耗的資源。Exchange Online 使用者活動和系統元件的節流設定根據[工作負載管理](http://technet.microsoft.com/en-us/library/jj150503(v=exchg.150).aspx)。Exchange Online 的工作負載是 Exchange Online 的功能、 通訊協定或其已明確地定義基於的 Exchange Online 的系統資源管理服務。每個 Exchange Online 的工作負載需要 CPU、 信箱資料庫作業，例如的系統資源或執行使用者要求或背景工作要求的 Active Directory。Exchange Online 的工作負載的範例包括 Outlook web、 Exchange ActiveSync、 信箱移轉和信箱助理員上。租用戶系統管理員可以管理 Exchange 工作負載管理節流設定的使用者使用 Exchange 管理命令介面。有各種形式的節流設定其已在 Exchange Online，包括 PowerShell、 Exchange Web 服務和 POP 與 IMAP、 Exchange ActiveSync、 行動裝置連線、 收件者] 及其他實作。時的內部部署 Exchange 部署的系統管理員可以設定節流原則，系統管理員無法設定節流原則的 Exchange Online。

最常見的節流設定 SharePoint Online 中觸發程序是在太高頻率太多動作的用戶端物件模型 (CSOM) 程式碼。使用 CSOM，許多動作可以執行單一要求，它可以超過流量限制並導致個別使用者節流設定。

不論活動這可能會導致節流設定，當使用者超過流量限制、 SharePoint Online 節流任何進一步要求的使用者帳戶，通常是一段簡短時間。使用者節流處於作用中] 時由該使用者的所有動作已受到都節流直到節流，過期取決於下列準則：
- 直接在瀏覽器中之使用者所執行的要求，節流資訊] 頁面中的 SharePoint Online 重新導向及要求失敗。
- 所有其他要求，包括 CSOM 呼叫 SharePoint Online 傳回 HTTP 狀態碼 429 （"太多要求"），並要求失敗。

如果違規的程序會繼續超過流量限制、 SharePoint Online 可能完全封鎖程序並傳回 HTTP 狀態碼 503 （「 服務無法使用 」）。

## <a name="vulnerability-and-penetration-testing"></a>弱點和滲透測試
Microsoft 使用許多[安全性技術與作法](https://www.microsoft.com/en-us/trustcenter/security/threatmanagement)來[保護其雲端基礎結構](https://blogs.technet.microsoft.com/hybridcloud/2015/05/05/protecting-your-datacenter-and-cloud-from-emerging-threats/)和內部現代、 複雜威脅，包括使用反惡意程式碼元件和服務的雲端服務、 虛擬網路機器 (Vm) 與其他系統;進階的威脅分析、 網路、 系統及使用者的一般使用模式來進行監視及採用機器學習到超出一般、 和定期滲透測試任何行為的旗標。

除了執行自己滲透測試及[Microsoft Cloud 整合滲透測試程式](https://technet.microsoft.com/en-us/mt784683)提供給我們客戶，我們也參與的協力廠商安全性專業人員執行的一般弱點評估及滲透測試對我們雲端服務。我們進行來自這些協力廠商弱點評估報告可供下載的[信任服務](https://aka.ms/STP)及[服務保證](https://aka.ms/ServiceAssurance)入口網站。
