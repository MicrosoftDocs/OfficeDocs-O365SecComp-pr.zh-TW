---
title: Office 365 進階威脅防護
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/20/2019
ms.audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
ms.collection:
- M365-security-compliance
description: Office 365 進階威脅保護包含安全附件、 安全的連結進階的反網路釣魚工具、 報告和威脅智慧功能。
ms.openlocfilehash: 33a98781c29a6ab8a44a69922afd976ce044c09d
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220003"
---
# <a name="office-365-advanced-threat-protection"></a>Office 365 進階威脅防護

> [!IMPORTANT]
> 本文適用於 Office 365 企業版客戶的。如果您使用 Outlook.com、 Office 365 首頁] 或 [Office 365 個人，而且您要尋找在 Outlook 中的安全連結的相關資訊，請參閱[進階 Outlook.com 安全性](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)。

## <a name="overview"></a>概觀

Office 365 進階威脅保護 (ATP) 保護惡意設電子郵件、 連結 (Url) 和共同作業工具所產生的威脅對貴組織。ATP 包括：

- [威脅保護原則](#configure-atp-policies)： 定義威脅保護原則保護組織的適當層級的設定。 

- [報表](#view-atp-reports)： 檢視即時監視組織中的 ATP 效能報告。 

- [威脅智慧功能](#utilize-threat-intelligence-capabilities)： 運用調查、 了解、 模擬，並防止威脅的領導 edge 工具。 
 

## <a name="configure-atp-policies"></a>設定 ATP 原則

Office 365 ATP 提供許多工具來設定適當的層級的貴組織保護。 

貴組織的安全性小組必須定義原則的每個 ATP 工具在 Office 365 安全性 & 規範中心。移至 [ **Threat management** > **原則**來存取原則選項。 

針對您組織所定義的原則決定預先定義的威脅的行為與保護層級。原則選項是極具彈性。例如，貴組織的安全性小組可以設定微調威脅保護使用者、 組織、 收件者和網域層級。請務必定期檢閱您的原則因為新威脅與挑戰出現 [每日。  

- [ATP 安全附件](atp-safe-attachments.md)： 提供零時差保護來保護您的訊息系統檢查惡意內容的電子郵件附件。並路由傳送所有郵件及附件不含病毒/惡意程式碼簽章特殊環境中，然後使用機器學習與分析的技術來偵測惡意的用途。如果不找到任何可疑的活動，就會將郵件轉接至信箱。若要深入了解，請參閱[Set up Office 365 ATP 安全附件的原則](set-up-atp-safe-attachments-policies.md)。

- [ATP 安全連結](atp-safe-links.md)： 提供之 Url 的時間按一下 [驗證電子郵件訊息和 Office 檔案中。保護會持續與套用您的通訊和 Office 環境。連結的每個 click 掃描： 安全的連結會保持存取和動態封鎖惡意的連結。若要深入了解，請參閱[Set up Office 365 ATP 安全連結原則](https://docs.microsoft.com/en-us/office365/securitycompliance/set-up-atp-safe-links-policies)。 

- [SharePoint、 OneDrive 及 Microsoft 小組 ATP](atp-for-spo-odb-and-teams.md)： 當使用者共同作業及來識別共用檔案、 而封鎖惡意檔案小組網站及文件庫會保護您的組織。若要深入了解，請參閱[開啟 Office 365 ATP for SharePoint、 OneDrive 及 Microsoft 小組](turn-on-atp-for-spo-odb-and-teams.md)。 

- [ATP 反網路釣魚保護](atp-anti-phishing.md)： 偵測嘗試模擬使用者和自訂的網域。它會套用機器學習模型和進階的模擬偵測演算法來說明網路釣魚攻擊。若要深入了解，請參閱[Set up Office 365 ATP 反網路釣魚和反網路釣魚原則](set-up-anti-phishing-policies.md)。

## <a name="view-atp-reports"></a>檢視 ATP 報告

Office 365 ATP 包括進階[報表的儀表板](view-reports-for-atp.md)監視 ATP 效能。您可以在**報表 > 儀表板**存取它的安全性 & 規範中心。 

更新中的報告即時，提供最新的觀點。這些報告也會提供的建議及提醒您即將威脅。預先定義的報告包含[威脅保護狀態報表](view-reports-for-atp.md#threat-protection-status-report)、 [ATP 檔案類型的報告](view-reports-for-atp.md#atp-file-types-report)、 [ATP 郵件處理報告](view-reports-for-atp.md#atp-message-disposition-report)及其他。 

## <a name="utilize-threat-intelligence-capabilities"></a>運用威脅智慧功能

Office 365 ATP 包含適合的類別[威脅智慧工具](office-365-ti.md)可讓您組織的安全性小組預期、 了解，並防止惡意的攻擊。 

- [威脅追蹤者](threat-trackers.md)提供最新智慧主流 cybersecurity 問題。例如，您可以檢視最新惡意程式碼的相關資訊及之前它會變成實際的潛在威脅對組織必須執行因應對策。可追蹤者包括[值得注意的追蹤者](threat-trackers.md#noteworthy-trackers)、 [[趨勢追蹤者](threat-trackers.md#trending-trackers)、[追蹤查詢](threat-trackers.md#tracked-queries)和[Saved 查詢](threat-trackers.md#saved-queries)。

- [瀏覽器](use-explorer-in-security-and-compliance.md)（也稱為威脅 Explorer） 是可讓您識別和分析最近威脅即時報告。您可以設定的自訂週期] 會將資料顯示的瀏覽器。

- [攻擊模擬器](attack-simulator.md)可讓您識別 vulnerabilites 組織中執行真實感化的攻擊案例。模擬目前類型的攻擊可用，包括[顯示名稱矛網路釣魚攻擊](attack-simulator.md#display-name-spear-phishing-attack)、[密碼噴灑攻擊](attack-simulator.md#password-spray-attack)、[暴力密碼攻擊](attack-simulator.md#brute-force-password-attack)，等等。
    
## <a name="permissions-required-to-use-atp-features"></a>使用 ATP 功能所需的權限

若要存取的安全性 & 規範中心 ATP 功能，您必須指派適當的角色。下表包含一些範例：

|角色或角色群組  |若要深入了解的資源  |
|---------|---------|
|Office 365 全域管理員 |[關於 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|安全性管理員 |[Azure Active Directory 中的系統管理員角色權限](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Exchange Online 組織管理 |[Exchange Online 中的權限](https://docs.microsoft.com/en-us/exchange/permissions-exo/permissions-exo) <br>和<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|

另請參閱：
- [在 Office 365 安全性 & 規範中心的權限](permissions-in-the-security-and-compliance-center.md) 

- [讓使用者能夠存取 Office 365 安全性 & 規範中心](grant-access-to-the-security-and-compliance-center.md)

## <a name="get-office-365-atp"></a>取得 Office 365 ATP

Office 365 ATP 隨附於 Office 365 企業版 E5、 Office 365 教育版 A5、 及 Microsoft 365 Business。如果您的訂閱不包括 Office 365 ATP，則您可能可以購買 ATP 做為附加元件。若要深入了解，請參閱下列資源：

- 請參閱[Office 365 進階威脅保護 (ATP) 可用性](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability)包括 ATP 計劃的訂閱的清單。

- 計劃 1 和 2 中所包含的功能清單中看到[不同進階威脅保護 (ATP) 計劃中可用的功能](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。

- 請參閱比較計劃及購買 Office 365 ATP[取得 Office 365 進階威脅保護右邊](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content)。

## <a name="new-features-in-office-365-atp"></a>Office 365 ATP 中的新功能

新功能會需要經常新增至 Office 365 ATP。若要深入了解，請參閱下列資源：

- [Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)提供開發及啟用新功能的清單。

- [Office 365 進階威脅 Protection 服務說明](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)說明不同 ATP 計劃的功能與可用性。
