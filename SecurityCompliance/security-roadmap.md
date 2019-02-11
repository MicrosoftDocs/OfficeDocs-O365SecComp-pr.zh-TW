---
title: Office 365 安全性藍圖上方的前 30 天 90 天和以外的優先順序
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/08/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
search.appverid:
- MET150
ms.assetid: 28c86a1c-e4dd-4aad-a2a6-c768a21cb352
description: 'Microsoft 的 cybersecurity 小組實作安全性功能來保護您的 Office 365 環境的最佳建議。 '
ms.openlocfilehash: 58767ea9a2b825d1583d9135f9d8edcb0d20d7c2
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2019
ms.locfileid: "25450078"
---
# <a name="office-365-security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>Office 365 安全性藍圖上方的前 30 天 90 天和以外的優先順序

本文包含 Microsoft 的 cybersecurity 小組實作安全性功能來保護您的 Office 365 環境的最佳建議。本文是從 Microsoft 起始工作階段配合 —[安全 like cybersecurity 專業人員的 Office 365： 最常用的優先順序的前 30 天 90 天和超過](https://www.youtube.com/watch?v=luignzNyR-o)。此工作階段已開發和簡報者標記 Simos 和 Matt Kemelhar、 企業 Cybersecurity 設計師。
  
本文內容：
  
- [藍圖成果](security-roadmap.md#Roadmap)
    
- [30 天 — 強大的快速 wins](security-roadmap.md#Thirdaydays)
    
- [90 天 — 增強保護設定](security-roadmap.md#Ninetydays)
    
- [超過](security-roadmap.md#Beyond)
    
## <a name="roadmap-outcomes"></a>藍圖成果
<a name="Roadmap"> </a>

這些藍圖建議是邏輯順序與下列目標的三個階段跨分段。

|||
|:-----|:-----|
| |結果
|30 天|快速設定：  <br/> • [基本系統保護設定  <br/> • [記錄與分析  <br/> • [基本識別保護設定  <br/> 租用戶組態  <br/>  準備專案關係人  <br/> |
|90 天|進階模式保護功能：  <br/> • [系統管理帳戶  <br/>  • 資料&amp;的使用者帳戶  <br/>  可見性規範、 威脅和使用者需求  <br/>  能否及實作預設原則與保護設定  <br/> |
|超過|調整及調整主要原則和控制項  <br/> 擴充至內部部署相依性的保護設定  <br/> 與業務與安全性程序 （法律、 內部威脅） 整合  <br/> |
  

   
## <a name="30-days--powerful-quick-wins"></a>30 天 — 強大的快速 wins
<a name="Thirdaydays"> </a>

這些工作可以快速地完成，並且對使用者的影響小。
  
|||
|:-----|:-----|
|範圍  <br/> |工作  <br/> |
|安全性管理  <br/> |• [檢查安全分數並記下您目前的分數 ( [https://securescore.office.com](https://securescore.office.com))。  <br/>  • [開啟的 Office 365 的稽核記錄。請參閱[Office 365 安全性搜尋稽核記錄&amp;規範中心](search-the-audit-log-in-security-and-compliance.md)。<br/> • [[設定您的 Office 365 租用戶增加安全性](tenant-wide-setup-for-increased-security.md)。  <br/>  • [定期檢閱儀表板和 reports in Office 365 安全性和規範中心 」 及雲端應用程式安全性。  <br/> |
|威脅防護  <br/> |若要啟動監控使用異常行為預設威脅偵測原則[連線至 Microsoft 雲端應用程式安全性的 Office 365](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) 。延長建置異常偵測的比較基準 7 日間。<br><br/>  實作保護系統帳戶：  <br/> • [使用專用系統帳戶管理活動。  <br/>  • [強制執行管理帳戶的多重要素的驗證 (MFA)。  <br/>  • 使用[高度安全 Windows 10 裝置](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-highly-secure)的系統活動。  <br/> |
|身分識別和存取管理  <br/> |• [[啟用 Azure Active Directory 識別保護](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)。  <br/> • [同盟身分識別環境中，強制執行帳戶安全性 （密碼長度、 保留時間下限、 複雜性等）。  <br/> |
|資訊保護  <br/> | 檢閱範例資訊保護建議。資訊保護需要協調整個組織。開始使用這些資源：<br/> • [GDPR 的 office 365 的資訊保護](http://aka.ms/o365gdpr) <br/> • [[安全的 SharePoint Online 網站及檔案](https://docs.microsoft.com/Office365/enterprise/secure-sharepoint-online-sites-and-files)（包括共用、 分類、 資料外洩防護及 Azure 資訊保護）  <br/> |
   
## <a name="90-days--enhanced-protections"></a>90 天 — 增強保護設定
<a name="Ninetydays"> </a>

這個工作需要多一些時間來計劃及實作，但是可以大幅增加您的安全性狀態。 
  
|||
|:-----|:-----|
|範圍  <br/> |工作  <br/> |
|安全性管理  <br/> | • [建議的動作為您的環境檢查安全分數 ( [https://securescore.office.com](https://securescore.office.com))。  <br/>  • 繼續定期檢閱儀表板及 Office 365 安全性和規範中心、 雲端應用程式安全性]，以及 SIEM 工具中的報表。  <br/>  • [尋找及實作軟體更新。  <br/>  • 召開攻擊模擬矛網路釣魚、 密碼噴灑，及使用 （包含[Office 365 威脅智慧](office-365-ti.md)） 的[攻擊模擬器](https://support.office.com/article/attack-simulator-office-365-da5845db-c578-4a41-b2cb-5a09689a551b)暴力密碼攻擊。  <br/>  • [外觀共用風險透過檢閱內建的報告的雲端應用程式安全性 （調查] 索引標籤）。  <br/>  • [檢查[規範管理員](meet-data-protection-and-regulatory-reqs-using-microsoft-cloud.md)可供檢閱的規定適用於您的組織 （例如 GDPR NIST 800 171) 的狀態。  <br/> |
|威脅防護  <br/> | 實作增強模式保護功能的管理帳戶：  <br/>  • [系統管理活動的設定[權限存取工作站](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations)（腳印）。  <br/>  • 設定[Azure AD 權限的身分識別管理](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)。  <br/>  • 設定從 Office 365、 雲端應用程式安全性及其他服務，包括 AD FS 收集記錄資料的安全性資訊及事件 (SIEM) 管理工具。Office 365 稽核記錄會儲存資料的僅 90 天。擷取 SIEM 工具在此資料可讓您儲存在較長的期間內的資料。<br/> |
|身分識別和存取管理  <br/> | • [啟用並強制 MFA 執行的所有使用者。  <br/>  • 實作一組的[設定格式化的條件存取及相關的原則](https://docs.microsoft.com/en-us/microsoft-365/enterprise/microsoft-365-policies-configurations)。 |
|資訊保護  <br/> | 能否及實作資訊保護原則。這些資源包括範例：<br/> • [GDPR 的 office 365 的資訊保護](http://aka.ms/o365gdpr) <br/> • [[安全的 SharePoint Online 網站及檔案](https://docs.microsoft.com/Office365/enterprise/secure-sharepoint-online-sites-and-files) <br/> <br> 資料外洩防護原則和監視工具在 Office 365 中使用 Office 365 （而非雲端應用程式安全性） 中儲存的資料。 <br><br>用於進階警示 （而非資料遺失防護） 的功能搭配 Office 365 雲端應用程式安全性。  <br/> |
   
## <a name="beyond"></a>超過
<a name="Beyond"> </a>

這些是建置在上一個工作的重要安全性措施。 
  
|||
|:-----|:-----|
|範圍  <br/> |工作  <br/> |
|安全性管理  <br/> |• 繼續使用安全分數規劃後續動作 ( [https://securescore.office.com](https://securescore.office.com))。  <br/>  • 繼續定期檢閱儀表板及 Office 365 安全性和規範中心、 雲端應用程式安全性]，以及 SIEM 工具中的報表。  <br/>  • 繼續尋找與實作軟體更新。  <br/>  • 整合到您的法律 eDiscovery 及威脅回應程序。  <br/> |
|威脅防護  <br/> | • 實作[安全權限存取](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access)(SPA) 適用於內部部署 （AD、 AD FS） 的身分識別元件。  <br/>  • 使用雲端應用程式安全性要監視之內部威脅。  <br/>  • 使用雲端應用程式安全性探索陰影 IT saas 和使用狀況。  <br/> |
|身分識別和存取管理  <br/> | • 精選資訊保護原則：  <br/>  • Azure 的資訊保護及 Office 365 資料外洩防護 (DLP)。  <br/>  • 雲端應用程式安全性原則和提醒。  <br/> |
|資訊保護  <br/> | • 精選原則及操作的程序。  <br/>  • 使用 Azure AD 身分識別保護以識別內部威脅。  <br/> |
   
另請參閱：[如何減輕快速 cyberattacks Petya 等 WannaCrypt](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/)。 
  

