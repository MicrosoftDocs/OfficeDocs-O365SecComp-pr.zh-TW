---
title: Office 365 進階威脅防護
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/19/2019
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
description: Office 365 進階威脅防護包括安全附件、 安全連結、 進階的反網路釣魚工具、 報告工具和威脅智慧功能。
ms.openlocfilehash: ce4652e19f97cda6dbbea7df8083531ee0a0a1fc
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693052"
---
# <a name="office-365-advanced-threat-protection"></a>Office 365 進階威脅防護

> [!IMPORTANT]
> 本文適用於 Office 365 企業版客戶。 如果您使用 Outlook.com、 Office 365 家用版、 Office 365 個人或，而且您正在尋找在 Outlook 中的安全連結的相關資訊，請參閱 <<c0>進階 Outlook.com 安全性。

## <a name="overview"></a>概觀

Office 365 進階威脅防護 (ATP) 會保護您的組織抵禦惡意電子郵件、 連結 (Url) 及共同作業工具所造成的威脅。 ATP 包含：

- [威脅防護原則](#configure-atp-policies)： 定義威脅防護原則，以設定適當的組織保護層級。 

- [報告](#view-atp-reports)： 檢視即時報告來監視您組織中的 ATP 效能。 

- [威脅調查及回應功能](#use-threat-investigation-and-response-capabilities)： 使用前置 edge 工具來調查、 了解、 模擬，並防止潛在威脅。 
 

## <a name="configure-atp-policies"></a>設定 ATP 原則

Office 365 ATP 提供許多工具來設定適當的組織保護層級。 

貴組織的安全性小組必須在 Office 365 安全性 & 合規性中心中定義每個 ATP 工具的原則。 移至**威脅管理，** > **原則**，以存取原則選項。 

針對您組織所定義的原則決定預先定義的威脅的行為和保護層級。 原則選項是相當有彈性。 例如，貴組織的安全性小組可以在使用者、 組織、 收件者及網域層級設定微調威脅防護。 請務必定期檢閱您的原則因為新的威脅與挑戰浮現每日。  

- [ATP 安全附件](atp-safe-attachments.md)： 提供零時差保護來保護郵件系統，藉由檢查電子郵件附件為惡意內容。 它路由傳送所有郵件和附件，不需要特殊環境中，病毒/惡意程式碼簽章]，然後會使用機器學習和分析技術來偵測惡意意圖。 如果不找到任何可疑的活動，則郵件會轉送到信箱。 若要深入了解，請參閱 <<c0>設定 Office 365 ATP 安全附件原則。

- [ATP 安全連結](atp-safe-links.md)： 提供電子郵件訊息和 Office 檔案中的時間按一下 [驗證的 Url。 保護持續進行，並套用您的通訊和 Office 環境。 連結掃描的每個 click： 安全連結仍然可以存取和動態封鎖惡意連結。 若要深入了解，請參閱 <<c0>設定 Office 365 ATP 安全連結原則。 

- [適用於 SharePoint、 OneDrive 及 Microsoft Teams ATP](atp-for-spo-odb-and-teams.md)： 會保護您的組織，當使用者共同作業和共用檔案，藉由識別和封鎖惡意檔案小組網站和文件庫。 若要深入了解，請參閱[開啟 Office 365 ATP SharePoint、 OneDrive 及 Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)。 

- [ATP 防網路釣魚保護](atp-anti-phishing.md)： 偵測到嘗試模擬您的使用者與自訂的網域。 它會套用機器學習模型和進階的模擬偵測演算法來說明網路釣魚攻擊。 若要深入了解，請參閱 < <b0>Set up Office 365 ATP 防網路釣魚和防網路釣魚原則</b0>。

## <a name="view-atp-reports"></a>檢視 ATP 報告

Office 365 ATP 包含進階[報告儀表板](view-reports-for-atp.md)來監視您 ATP 的效能。 您可以在**報告 > 儀表板**存取它的安全性 & 合規性中心中。 

更新中的報表即時，提供您最新的深入資訊。 這些報告也會提供建議和提醒您即將威脅。 預先定義的報告包含[威脅保護狀態報表](view-reports-for-atp.md#threat-protection-status-report)、 [ATP 檔案類型的報告](view-reports-for-atp.md#atp-file-types-report)、 [ATP 郵件處理報表](view-reports-for-atp.md#atp-message-disposition-report)等等。 

## <a name="use-threat-investigation-and-response-capabilities"></a>使用威脅調查及回應功能

Office 365 ATP 計劃 2 包含適合的類別[威脅調查及回應工具](office-365-ti.md)，可讓您組織的安全性小組，以預測，了解，並防止惡意攻擊。 

- [威脅追蹤器](threat-trackers.md)提供最新智慧主流 cybersecurity 問題。 例如，您可以檢視最新惡意程式碼的相關資訊，並採取的因應對策之前就會變成組織實際威脅。 可用的追蹤器包括[值得注意的追蹤器](threat-trackers.md#noteworthy-trackers)、[趨勢追蹤器](threat-trackers.md#trending-trackers)、[追蹤查詢](threat-trackers.md#tracked-queries)，以及[已儲存查詢](threat-trackers.md#saved-queries)。

- [檔案總管](use-explorer-in-security-and-compliance.md)（也稱為威脅總管） 是即時報告，可讓您識別和分析最近的威脅。 您可以設定自訂期間顯示資料的檔案總管。

- [攻擊模擬器](attack-simulator.md)可讓您識別 vulnerabilites 您組織中執行真實的攻擊案例。 目前類型的攻擊模擬可供使用，包括[顯示名稱矛網路釣魚攻擊](attack-simulator.md#display-name-spear-phishing-attack)、[密碼噴灑攻擊](attack-simulator.md#password-spray-attack)、[暴力密碼攻擊](attack-simulator.md#brute-force-password-attack)，等等。
    
## <a name="permissions-required-to-use-atp-features"></a>使用 ATP 功能所需的權限

若要存取安全性 & 合規性中心中的 ATP 功能，您必須獲指派適當的角色。 下表包含一些範例：

|角色或角色群組  |若要了解更多的資源  |
|---------|---------|
|Office 365 全域系統管理員 |[關於 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|安全性系統管理員 |[在 Azure Active Directory 系統管理員角色權限](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Exchange Online 組織管理 |[權限在 Exchange Online](https://docs.microsoft.com/en-us/exchange/permissions-exo/permissions-exo) <br>與<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|

如需詳細資訊，請參閱：

- [Office 365 安全性 & 合規性中心的權限](permissions-in-the-security-and-compliance-center.md) 

- [讓使用者能夠存取 Office 365 安全性 & 合規性中心](grant-access-to-the-security-and-compliance-center.md)

## <a name="get-office-365-atp"></a>取得 Office 365 ATP

Office 365 ATP 隨附於 Office 365 企業版 E5，Office 365 教育版 A5，Microsoft 365 商務版。 如果您的訂閱未包含 Office 365 ATP，您可能可以當作附加元件購買 ATP。 若要深入了解，請參閱下列資源：

- 如需訂閱包含 ATP 計劃的清單，請參閱[Office 365 進階威脅防護 (ATP) 可用性](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability)。

- 如需方案 1 和 2 中所包含的功能清單，請參閱[進階威脅防護 (ATP) 計劃的功能可用性](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。

- 若要比較方案，並購買 Office 365 ATP[取得 Office 365 進階威脅防護的權限](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content)，請參閱。

## <a name="new-features-in-office-365-atp"></a>Office 365 ATP 中新功能

新功能會持續新增至 Office 365 ATP。 若要深入了解，請參閱下列資源：

- [Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)提供在開發和推出新功能的清單。

- [Office 365 進階威脅防護服務說明](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)說明 ATP 計劃的功能和可用性。
