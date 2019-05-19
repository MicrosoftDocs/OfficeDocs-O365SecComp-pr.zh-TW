---
title: Office 365 安全性藍圖的 30 天、 前 90 天及過後的頂端優先順序
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/08/2018
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
ms.assetid: 28c86a1c-e4dd-4aad-a2a6-c768a21cb352
description: '上方來自 Microsoft 的 cybersecurity 小組實作的安全性功能來保護您的 Office 365 環境的建議。 '
ms.openlocfilehash: 12aa5833757901ba78a0716480cb34b5b60675a5
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34157635"
---
# <a name="office-365-security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>Office 365 安全性藍圖的 30 天、 前 90 天及過後的頂端優先順序

本文包含上方 Microsoft cybersecurity 小組實作的安全性功能來保護您的 Office 365 環境的建議。 本文是配合從 Microsoft Ignite 工作階段-[例如 pro cybersecurity 保護 Office 365： 前的 30 天、 前 90 天及過後](https://www.youtube.com/watch?v=luignzNyR-o)。 此工作階段已開發和出示標記 Simos 和 Matt Kemelhar、 企業 Cybersecurity 架構。
  
本文內容：
  
- [藍圖結果](security-roadmap.md#Roadmap)
    
- [30 天 — 強力快速 wins](security-roadmap.md#Thirdaydays)
    
- [90 天 — 加強保護](security-roadmap.md#Ninetydays)
    
- [Beyond](security-roadmap.md#Beyond)
    
## <a name="roadmap-outcomes"></a>藍圖結果
<a name="Roadmap"> </a>

這些藍圖建議被分段跨三個階段具有下列目標的邏輯順序。

|||
|:-----|:-----|
| |結果
|30 天|快速設定：  <br/> • 基本系統管理保護  <br/> • 記錄與分析  <br/> • 基本的身分識別保護  <br/> 租用戶組態  <br/>  準備專案關係人  <br/> |
|90 天|進階的保護設定：  <br/> • 系統管理員帳戶  <br/>  • 資料&amp;使用者帳戶  <br/>  合規性、 威脅，以及使用者需求的可視性  <br/>  適應並實作預設原則和保護  <br/> |
|Beyond|調整，調整索引鍵的原則和控制項  <br/> 擴充保護，來內部相依性  <br/> 與業務與安全性程序 （法律、 測試人員威脅） 整合  <br/> |
  

   
## <a name="30-days--powerful-quick-wins"></a>30 天 — 強力快速 wins
<a name="Thirdaydays"> </a>

這些工作可以快速地完成，並且對使用者的影響小。
  
|||
|:-----|:-----|
|範圍  <br/> |工作  <br/> |
|安全性管理  <br/> |• 檢查安全分數，並記下您目前的分數 ( [https://securescore.office.com](https://securescore.office.com))。  <br/>  • 開啟的 Office 365 稽核記錄。 請參閱 <<c0>搜尋稽核記錄檔。  <br/> •[設定 Office 365 租用戶以提高安全性](tenant-wide-setup-for-increased-security.md)。  <br/>  • 定期檢閱儀表板和報告中的 Microsoft 365 安全中心和 Cloud App Security。  <br/> |
|威脅防護  <br/> |[Office 365 連線到 Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) ，才能開始監控異常行為使用預設威脅偵測原則。 它會建置異常偵測的比較基準 7 天。  <br><br/>  實作保護系統管理員帳戶：  <br/> • 使用專用的系統管理員帳戶的系統管理員活動。  <br/>  • Enforce 系統管理員帳戶的多重要素驗證 (MFA)。  <br/>  • 使用[高度安全 Windows 10 裝置](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-highly-secure)的系統管理員活動。  <br/> |
|身分識別和存取管理  <br/> |•[啟用 Azure Active Directory Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)。  <br/> • 針對同盟身分識別環境中，強制執行帳戶安全性 （密碼長度、 保留、 複雜性等）。  <br/> |
|資訊保護  <br/> | 檢閱範例資訊保護建議。 資訊保護貴組織需要協調。 使用下列資訊開始使用：  <br/> • [GDPR 的 office 365 資訊保護](http://aka.ms/o365gdpr) <br/> •[保護 SharePoint Online 網站與檔案](https://docs.microsoft.com/Office365/enterprise/secure-sharepoint-online-sites-and-files)（包括共用、 分類、 資料外洩防護，與 Azure 資訊保護）  <br/> |
   
## <a name="90-days--enhanced-protections"></a>90 天 — 加強保護
<a name="Ninetydays"> </a>

這個工作需要多一些時間來計劃及實作，但是可以大幅增加您的安全性狀態。 
  
|||
|:-----|:-----|
|範圍  <br/> |工作  <br/> |
|安全性管理  <br/> | • 建議的動作，為您的環境檢查安全分數 ( [https://securescore.office.com](https://securescore.office.com))。  <br/>  • 繼續定期檢閱儀表板和報告在 Microsoft 365 安全性中心、 雲端 App 安全性與 SIEM 工具。  <br/>  • 尋找並實作軟體更新。  <br/>  • 進行攻擊模擬矛網路釣魚、 密碼-噴灑，及使用 （包含[Office 365 威脅情報](office-365-ti.md)） 的[攻擊模擬器](https://support.office.com/article/attack-simulator-office-365-da5845db-c578-4a41-b2cb-5a09689a551b)暴力密碼攻擊。  <br/>  • 藉由檢視 （上調查] 索引標籤） 雲端 App 安全性中的內建報告共用風險的外觀。  <br/>  • 檢查檢閱狀態套用至組織 （例如 GDPR、 NIST 800-171) 的法規[合規性管理員](meet-data-protection-and-regulatory-reqs-using-microsoft-cloud.md)。  <br/> |
|威脅防護  <br/> | 實作加強的保護系統管理員帳戶：  <br/>  • 設定[特殊權限存取工作站](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations)（腳印） 的系統管理員活動。  <br/>  • 設定[Azure AD 有權限的身分識別管理](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)。  <br/>  • 設定 Office 365、 Cloud App Security，和其他服務，包括 AD FS 收集記錄資料的安全性資訊和事件管理 (SIEM) 工具。 Office 365 稽核記錄檔會將資料儲存僅限 90 天。 擷取此資料在 SIEM 工具，可讓您儲存較長的資料。  <br/> |
|身分識別和存取管理  <br/> | • 啟用，並為所有使用者強制執行 MFA。  <br/>  • 實作[條件式存取及相關的原則](https://docs.microsoft.com/en-us/microsoft-365/enterprise/microsoft-365-policies-configurations)的設定。 |
|資訊保護  <br/> | 適應並實作資訊保護原則。 這些資源包括範例：  <br/> • [GDPR 的 office 365 資訊保護](http://aka.ms/o365gdpr) <br/> •[保護 SharePoint Online 網站與檔案](https://docs.microsoft.com/Office365/enterprise/secure-sharepoint-online-sites-and-files) <br/> <br> 使用資料外洩防護原則和監控工具在 Office 365 中 （而不是 Cloud App Security) 的 Office 365 中儲存的資料。 <br><br>用於進階警示 （以外的資料外洩防護） 的功能，則您可以使用 Office 365 雲端 App 安全性。  <br/> |
   
## <a name="beyond"></a>Beyond
<a name="Beyond"> </a>

以下是建立一個工作為基礎的重要的安全性措施。 
  
|||
|:-----|:-----|
|範圍  <br/> |工作  <br/> |
|安全性管理  <br/> |• 繼續下一步動作規劃使用安全分數 ( [https://securescore.office.com](https://securescore.office.com))。  <br/>  • 繼續定期檢閱儀表板和報告在 Microsoft 365 安全性中心、 雲端 App 安全性與 SIEM 工具。  <br/>  • 繼續尋找並實作軟體更新。  <br/>  • 整合到您 legal 的 eDiscovery 和威脅回應程序。  <br/> |
|威脅防護  <br/> | • 實作[Secure 特殊權限存取](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access)(SPA) 適用於內部部署 （AD、 AD FS） 的身分識別元件。  <br/>  • 使用 Cloud App Security 來監視測試人員威脅。  <br/>  • 藉由使用 Cloud App Security 探索陰影 IT SaaS 流量。  <br/> |
|身分識別和存取管理  <br/> | • 精簡原則和作業程序。  <br/>  • 使用 Azure AD Identity Protection 來識別測試人員威脅。  |
|資訊保護  <br/> | 調整資訊保護原則：  <br/>  • Microsoft 365 和 Office 365 的敏感度標籤和資料外洩防護 (DLP) 或 Azure 資訊保護。  <br/>  • 雲端 App 安全性原則和警訊。  <br/> |
   
另請參閱：[如何減輕 Petya 等 WannaCrypt 快速網路攻擊](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/)。 
  

