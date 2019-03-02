---
title: Office 365 的安全性最佳做法
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 5/22/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- BCS160
- MET150
ms.assetid: 9295e396-e53d-49b9-ae9b-0b5828cdedc3
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_IP
description: 降低資料外洩或遭入侵的帳戶可能有遵循這些建議的最佳作法。
ms.openlocfilehash: 97dffe6e0cf4551c9addc1ba53c4f95c7d88b3f3
ms.sourcegitcommit: 7adfd8eda038cf25449bdf3df78b5e2fcc1999e7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/01/2019
ms.locfileid: "30357524"
---
# <a name="security-best-practices-for-office-365"></a>Office 365 的安全性最佳做法

降低資料外洩或遭入侵的帳戶可能有遵循這些建議的最佳作法。
  
本文包含快速清單的最佳作法。如需深入分析和安全性設定的詳細資訊，請參閱[Office 365 安全性藍圖： 前的 30 天、 前 90 天及過後](security-roadmap.md)。在該文中，您會發現資訊根據真實的攻擊的調查，我們上方的 Microsoft Office 365 cybersecurity 專家會提供指導評估風險及實作最重要的安全性、 規範和資訊的方式保護來保護您的 Office 365 租用戶的控制項。您將了解如何設定優先順序威脅、 威脅轉化技術的策略，，然後採取實作功能和控制項的 [系統化的方法。
  
## <a name="use-office-365-secure-score"></a>使用 Office 365 安全分數

安全分數是種安全性分析工具，建議您能夠如何進一步降低風險。安全分數會查看您的 Office 365 設定和活動，並比較它們，由 Microsoft 所建立的基線。您會看到如何對齊您使用最佳安全性作法為基礎的分數。如需如何取得安全分數，並使用它來增加您的 Office 365 組織的安全性的詳細資訊，請參閱[介紹 Office 365 安全分數](office-365-secure-score.md)。
  
要嘗試安全分數嗎？
  
使用已被指派 Office 365[關於 Office 365 系統管理員角色](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)的角色，[登入 Office 365](https://www.office.com/signin)工作或學校帳戶。
  
存取安全分數在[https://SecureScore.office.com](https://SecureScore.office.com)。
  
## <a name="use-multi-factor-authentication-mfa"></a>使用多重要素驗證 (MFA)

MFA 會藉由要求使用者確認電話、 文字訊息或其智慧型手機上的應用程式通知正確輸入其密碼之後，將額外的保護層級新增至強式密碼策略。透過就地 MFA，Office 365 使用者帳戶仍受到防止未經授權存取即使危害使用者的密碼。因為未授與存取直到帳戶之後未滿足其他挑戰，帳戶會受到保護。遭入侵或被竊密碼不足夠。
  
- [Office 365 部署多重要素驗證方案](https://support.office.com/article/043807b2-21db-4d5c-b430-c8a6dee0e6ba)

- [設定 Office 365 使用者的多重要素驗證](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)

## <a name="use-office-365-cloud-app-security"></a>使用 Office 365 雲端 App 安全性

設定原則根據您追蹤異常的活動，並對它的業務需求。設定與 Office 365 雲端 App 安全性的提醒，以系統管理員可以檢閱不尋常或高風險使用者活動，例如下載大量的資料，多次失敗登入嘗試次數或從未知或危險的 IP 位址的登入。對使用 Office 365 企業版 E5 方案的組織而言，您可以開始使用 Office 365 雲端 App 安全性立即。如果您有不同的企業版方案，您可以以附加元件形式購買 Office 365 雲端 App 安全性。
  
- [O365 雲端 App 安全性概觀](office-365-cas-overview.md)

- [開啟 Office 365 雲端 App 安全性](turn-on-office-365-cas.md)

## <a name="secure-mail-flow"></a>安全郵件流程

實作豐富型功能設定 Exchange Online Protection 中的獲得更大的保證關於每個電子郵件，寄件者的身分識別和防護未知惡意程式碼、 病毒及透過電子郵件傳輸的惡意 Url。
  
- 設定您組織的[Office 365 電子郵件反垃圾郵件保護](anti-spam-protection.md)原則。

- 了解，然後使用 [[安全附件和安全連結的進階的威脅防護](https://technet.microsoft.com/library/mt148491.aspx)。

- [新增至您的組織的反惡意程式碼保護](https://technet.microsoft.com/en-us/library/jj200669%28v=exchg.150%29.aspx)。

- 了解並為您的使用者啟用[Office 365 中的電子郵件訊息中的安全提示](safety-tips-in-office-365.md)。

- 如果您正在使用您的組織在 Office 365 中的自訂網域，設定 SPF，DKIM，然後 DMARC 以驗證您的組織所傳送的郵件，並協助防止詐騙：

  - [設定 spf 以協助防止詐騙的 Office 365 中](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)。

  - [使用 DKIM 驗證從您在 Office 365 中的自訂網域傳送的外寄電子郵件](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)。

  - [使用 DMARC 來驗證 Office 365 中的電子郵件](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx)。

## <a name="enable-mailbox-audit-logging"></a>啟用信箱稽核記錄

某些啟用稽核記錄會自動為您在 Office 365;不過，信箱稽核記錄預設無法開啟。使用 Exchange Online PowerShell 開啟 Office 365 中的所有使用者信箱的稽核記錄。如詳細資訊，請參閱 <<c0>啟用 Office 365 中的稽核的信箱。
  
稽核記錄您啟用後可以[搜尋稽核記錄以在 Office 365 安全性&amp;合規性中心](search-the-audit-log-in-security-and-compliance.md)以找出誰已登入您的使用者信箱，傳送訊息，以及其他信箱擁有者，委派的使用者所執行的活動或系統管理員。如需隨附於 Office 365 信箱活動的清單依預設稽核記錄，請參閱[Exchange 信箱活動](search-the-audit-log-in-security-and-compliance.md#exchange-mailbox-activities)。
  
如需其他動作的資訊您可以執行與稽核記錄檔，例如變更的項目儲存在稽核記錄檔中的時間量，請參閱[信箱稽核記錄中 Exchange 2016](https://technet.microsoft.com/en-us/library/ff459237%28v=exchg.160%29.aspx)。
  
## <a name="configure-data-loss-prevention-dlp"></a>設定資料外洩防護 (DLP)

DLP 可讓您識別敏感資料，並建立原則，以協助防止使用者意外或故意共用資料。DLP 的運作方式，讓您的使用者可以符合規範，而不中斷其工作流程包括 Exchange Online、 SharePoint Online 和 OneDrive 的 Office 365。如需詳細資訊，請參閱 <<c0>資料外洩防護原則概觀。
  
## <a name="use-customer-lockbox"></a>使用客戶加密箱

身為 Office 365 系統管理員，您可以使用 Customer Lockbox 控制 Microsoft 支援工程師如何協助工作階段期間存取您的資料。在工程師需要存取您的資料進行疑難排解並修正此問題的情況下，Customer Lockbox 可讓您核准或拒絕存取要求。如果您核准，工程師就可以存取的資料。每個要求有到期時間，且一旦解決問題，要求已關閉，且會撤銷存取權。Customer Lockbox 隨附於 Office 365 企業版 E5 方案，或您可以購買與任何其他 Office 365 企業版方案個別的訂閱。如需資訊，請參閱 < <b0>Office 365 客戶加密箱要求</b0>。
  
## <a name="try-it-yourself"></a>自己試試看
<a name="SecureScore"> </a>

請參閱這些安全性功能之前在生產環境中採用這些 Office 365 試用版訂閱中運作。
  
- [建立 Office 365 試用訂閱](https://technet.microsoft.com/library/mt736406.aspx)

- [設定及測試使用者帳戶的 MFA](https://technet.microsoft.com/library/mt492459.aspx)

- [設定並測試 Office 365 雲端 App 安全性來通知您的全域系統管理員活動](https://technet.microsoft.com/library/mt757250.aspx)

- [設定及測試 ATP 可疑的電子郵件](https://technet.microsoft.com/library/mt490479.aspx)

- 檢查每個以上步驟您試用版訂閱[Office 365 安全分數](https://securescore.office.com/)