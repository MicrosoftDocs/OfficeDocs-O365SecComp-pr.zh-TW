---
title: Office 365 的安全性最佳做法
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/22/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MBS150
- BCS160
- MET150
ms.assetid: 9295e396-e53d-49b9-ae9b-0b5828cdedc3
description: 儘量減少資料破壞或洩漏的帳戶可能會遵循下列建議的最佳作法。
ms.openlocfilehash: d40fa5e4534bef1bb8389989022c44967a162aee
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30212813"
---
# <a name="security-best-practices-for-office-365"></a>Office 365 的安全性最佳做法

儘量減少資料破壞或洩漏的帳戶可能會遵循下列建議的最佳作法。
  
本文包含最佳作法快速的清單。如需深入的分析和安全性設定的詳細資訊，請參閱[Office 365 安全性藍圖： 最常用的優先順序的前 30 天 90 天和超過](security-roadmap.md)。在該文章，您會發現調查的真實世界攻擊為基礎的資訊我們上方的 Microsoft Office 365 cybersecurity 專家提供指導如何評估風險及實作最重要的安全性、 規範、 及資訊若要保護您的 Office 365 租用戶保護控制項。您將了解如何將優先順序威脅、 威脅翻譯成技術的策略，並實作功能與控制項採取適用於系統化方法。
  
## <a name="use-office-365-secure-score"></a>使用 Office 365 安全分數

安全的分數是建議可以怎麼做以進一步減少風險的安全性分析工具。安全的分數會查看您的 Office 365 設定和活動，並與比較 Microsoft 所建立的基準。您將取得如何對齊的最佳安全性作法為基礎的分數。如需如何取得安全分數並使用 Office 365 組織的安全性的詳細資訊，請參閱[簡介 Office 365 安全分數](office-365-secure-score.md)。
  
想要試用安全分數嗎？
  
使用已指派的 Office 365[有關 Office 365 系統管理員角色](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)的角色，[登入 Office 365](https://www.office.com/signin)工作或學校帳戶。
  
存取安全分數在[https://SecureScore.office.com](https://SecureScore.office.com)。
  
## <a name="use-multi-factor-authentication-mfa"></a>使用多重要素驗證 (MFA)

MFA 將額外的保護層級新增至強式密碼策略所需確認撥打的電話、 文字訊息或應用程式上的通知他們的智慧型手機之後正確地輸入其密碼的使用者。備妥 MFA，與 Office 365 使用者帳戶仍受到對抗未經授權存取即使危害使用者的密碼。帳戶會受到保護，因為沒有授與存取直到帳戶之後已滿足其他的挑戰。洩漏或竊密碼不足夠。
  
- [Office 365 部署多重要素驗證方案](https://support.office.com/article/043807b2-21db-4d5c-b430-c8a6dee0e6ba)
    
- [設定 Office 365 使用者的多重要素驗證](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)
    
## <a name="use-office-365-cloud-app-security"></a>使用 Office 365 雲端應用程式安全性

設定您的業務需求，以追蹤異常活動及對其為基礎的原則。設定與 Office 365 雲端應用程式安全性提醒，讓系統管理員可以檢閱不尋常或 risky 使用者活動，例如下載大量的資料，多無法登入嘗試次數或從未知或危險的 IP 位址的登入。對於 Office 365 企業版 E5 計劃的組織而言，您可以啟動立即使用 Office 365 雲端應用程式安全性。如果您有不同的企業計劃時，您可以做為附加元件購買 Office 365 雲端應用程式安全性。
  
- [O365 雲端應用程式安全性概觀](office-365-cas-overview.md)
    
- [開啟 Office 365 雲端 App 安全性](turn-on-office-365-cas.md)
    
## <a name="secure-mail-flow"></a>安全郵件流程

透過電子郵件傳輸的實作豐富型功能集 in Exchange Online Protection 和時會有關每個電子郵件之郵件的寄件者的身分識別的更保證並防止未知的惡意程式碼、 病毒、 及惡意 Url。
  
- 設定[Office 365 電子郵件反垃圾郵件保護](anti-spam-protection.md)您的組織的原則。 
    
- 了解，然後使用 [[進階的威脅保護安全附件及安全的連結](https://technet.microsoft.com/library/mt148491.aspx)。
    
- [新增您組織的反惡意程式碼保護](https://technet.microsoft.com/en-us/library/jj200669%28v=exchg.150%29.aspx)。
    
- 了解並為使用者啟用[Safety 秘訣 （英文） Office 365 中的電子郵件訊息中](safety-tips-in-office-365.md)。 
    
- 如果您組織在 Office 365 中使用自訂的網域，設定 SPF、 DKIM，然後 DMARC 來驗證您的組織所傳送的郵件，並協助防止詐騙：
    
  - [設定 SPF 避免詐騙的 Office 365 中](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)。
    
  - [使用 DKIM 驗證從您在 Office 365 中的自訂網域傳送的輸出電子郵件](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)。
    
  - [使用 DMARC 來驗證 Office 365 中的電子郵件](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx)。
    
## <a name="enable-mailbox-audit-logging"></a>啟用信箱稽核記錄

某些啟用稽核記錄會自動為您在 Office 365;不過，信箱稽核記錄不會開啟預設。您使用 Exchange Online PowerShell 開啟的 Office 365 中的所有使用者信箱的稽核記錄功能。資訊，請參閱[啟用信箱稽核 Office 365 中](https://go.microsoft.com/fwlink/p/?LinkID=626109)。
  
稽核記錄您是否已啟用之後可以[Office 365 安全性搜尋稽核記錄&amp;規範中心](search-the-audit-log-in-security-and-compliance.md)了解誰登入您的使用者信箱，傳送訊息及其他信箱擁有者、 委派的使用者所執行的活動或系統管理員。如需 Office 365 中隨附的信箱活動的清單依預設稽核記錄，請參閱[Exchange 信箱的活動](search-the-audit-log-in-security-and-compliance.md#exchange-mailbox-activities)。
  
如需資訊其他動作您可使用稽核記錄，例如變更的項目儲存在稽核記錄檔的時間執行的[信箱稽核記錄中 Exchange 2016](https://technet.microsoft.com/en-us/library/ff459237%28v=exchg.160%29.aspx)。
  
## <a name="configure-data-loss-prevention-dlp"></a>設定資料遺失防護 (DLP)

DLP 可讓您識別機密資料，並建立原則，協助使用者無法從有意或無意之間共用資料。DLP 的運作方式不同 Office 365 包括 Exchange Online、 SharePoint Online 和 OneDrive，讓使用者能停留相容而不會中斷其工作流程。如需詳細資訊，請參閱 ＜[資料外洩防護原則的概觀](data-loss-prevention-policies.md)。
  
## <a name="use-customer-lockbox"></a>使用客戶 Lockbox

為 Office 365 系統管理員，您可以使用客戶 Lockbox 控制 Microsoft 支援工程師說明工作階段期間所存取的資料。在其中工程師需要存取資料的疑難排解並修正問題的情況下，客戶 Lockbox 可讓您核准或拒絕存取要求。若加以核准、 工程師可以存取資料。每次要求有到期時間，並解決問題之後要求已關閉撤銷存取權。客戶 Lockbox 隨附的 Office 365 企業版 E5 計劃或可購買與任何其他 Office 365 企業版方案的不同訂閱。資訊，請參閱[Office 365 客戶 Lockbox 要求](https://support.office.com/article/36f9cdd1-e64c-421b-a7e4-4a54d16440a2)。
  
## <a name="try-it-yourself"></a>試試看
<a name="SecureScore"> </a>

請參閱使用 Office 365 試用版訂閱之前在生產環境中採用這些這些安全性功能。
  
- [建立 Office 365 試用版訂閱](https://technet.microsoft.com/library/mt736406.aspx)
    
- [設定和測試 MFA 使用者帳戶](https://technet.microsoft.com/library/mt492459.aspx)
    
- [設定及測試 Office 365 雲端應用程式安全性來通知您的全域管理員活動](https://technet.microsoft.com/library/mt757250.aspx)
    
- [設定和測試 ATP 可疑的電子郵件](https://technet.microsoft.com/library/mt490479.aspx)
    
- 檢查[Office 365 安全分數](https://securescore.office.com/)的每個以上步驟您試用訂閱 
    

