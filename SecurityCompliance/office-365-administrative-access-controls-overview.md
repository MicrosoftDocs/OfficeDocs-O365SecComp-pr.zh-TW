---
title: Office 365 中的系統管理存取控制
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
description: '摘要: Office 365 的系統管理存取控制和資料分類的簡介。'
ms.openlocfilehash: 38519fe4e9c05e3468ac3f9f6367c096fb64d195
ms.sourcegitcommit: 7b5e4a7a51f3cdd741deb77a2d60a18e2316618d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/01/2019
ms.locfileid: "33520693"
---
# <a name="administrative-access-controls-in-office-365"></a>Office 365 中的系統管理存取控制 

Microsoft 已投入大量的系統和控制項, 可自動化大部分的 Office 365 作業, 並故意限制 Microsoft 對客戶內容的存取。 人管理服務, 而軟體則會操作服務。 這可讓 Microsoft 以規模來管理 Office 365, 並管理對客戶內容內部威脅的風險。

根據預設, Microsoft 工程師的系統管理許可權為零, 而在 Office 365 中則不會有客戶內容的存取權。 Microsoft 工程師可在有限的時間內擁有對客戶內容的有限、已審核和安全的存取權。 只有在服務作業需要時才可存取, 而且只有在 Microsoft 資深管理的成員核准時才能存取。 對於客戶加密箱授權的客戶, 客戶會對其主控于 Office 365 的內容提供核准。

Microsoft 會使用多種形式的雲端傳遞來提供線上服務:

- **公用群:** 包含多租使用者版本的 Office 365、Azure 和其他託管于北美、南美洲、歐洲、亞洲、澳大利亞等的服務。
- **國家雲彩:** 包含美國以外的所有以及主權和協力廠商運作的雲彩 (除了先前所述的地方), 例如中國的 Office 365 (由世紀運作), 以及德國的 Office 365 (由 Microsoft 運作, 但在德文資料受託人的模型下)。德國 Telekom, 控制並監控 Microsoft 對客戶資料和包含客戶資料的系統的存取。
- **政府雲彩:** 包含適用于美國政府客戶的 Office 365 和 Azure 服務。

基於本文的目的, Office 365 服務包括:

- [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online)
- [Exchange Online Protection](https://docs.microsoft.com/Office365/SecurityCompliance/eop/exchange-online-protection-overview)
- [SharePoint Online](https://docs.microsoft.com/sharepoint/sharepoint-online)
- [商務用 OneDrive](https://docs.microsoft.com/OneDrive/onedrive)
- [商務用 Skype](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online)
- [Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
- [Yammer](https://docs.microsoft.com/yammer/yammer-landing-page)

## <a name="office-365-access-controls"></a>Office 365 存取控制

針對存取控制目的, Microsoft 會將 Office 365 資料分類為客戶資料或其他類型的資料。

### <a name="customer-data"></a>客戶資料

客戶資料是指使用 Office 365 服務時, 或代表客戶提供的所有資料。 這是由 Office 365 使用者直接建立或上傳的客戶內容, 包括:

- 電子郵件
- SharePoint Online 內容
- 立即訊息
- 行事曆專案
- 文件
- Contacts
- 使用者身分識別資訊 (EUII) (是使用者特有或 linkable 給個別使用者, 但不包含客戶內容) 的資料。

### <a name="other-types-of-data"></a>其他類型的資料

其他類型的資料包括:

- **帳戶資料:** 包含管理資料 (系統管理員在註冊或購買服務時提供的資訊), 以及付款資料 (有關付款儀器的資訊, 例如信用卡詳細資訊)。
- **組織識別資訊:** 包含用來識別租使用者、使用狀況資料, 而不是 linkable 給個別使用者或包含在客戶內容中的資料。
- **系統中繼資料:** 包含服務記錄檔, 其中包含有關訂閱和承租人的設定設定、系統狀態、Microsoft IP 位址及技術資訊。

Microsoft 已建立存取控制機制, 以確保任何人都無法撤銷對客戶資料或存取控制資料的存取。 存取控制資料可管理環境內其他類型的資料或功能的存取, 包括對客戶內容或 EUII、Microsoft 密碼、安全性憑證及其他驗證相關資料的存取。 存取控制機制也會防止未核准的實體、邏輯或遠端存取 Office 365 生產環境。

Microsoft 適用于運作 Office 365 的 access 控制項有三種類別:

- 隔離控制項
- 人員控制項
- 技術控制項

結合時, 這些控制項可協助防止和偵測 Office 365 中的惡意動作。 除了 Microsoft 所使用的隔離、人員和技術控制項, 還有第四種類別的控制項: 由客戶實施的控制項。

Office 365 可讓您管理資料, 就像在內部部署環境中管理資料一樣。 註冊 Office 365 組織的人員會自動成為全域系統管理員。 全域系統管理員可以存取管理入口網站中的所有功能, 並且可以:

- 建立或編輯使用者
- 指派系統管理員角色給其他人
- 重設使用者密碼
- 管理使用者授權
- 管理網域
- 核准客戶加密箱要求

建議每個組織至少設定兩個系統管理員帳戶。 對於大型企業組織, 我們建議以不同的功能為特定的系統管理員帳戶。

如需指派系統管理員角色及許可權的詳細資訊, 請參閱[在 office 365 中指派系統管理員角色](https://support.office.com/article/Assigning-admin-roles-in-Office-365-eac4d046-1afd-4f1a-85fc-8219c79e1504)和[關於 Office 365 系統管理員角色](https://support.office.com/article/Permissions-in-Office-365-DA585EEA-F576-4F55-A1E0-87090B6AAA9D)。

## <a name="related-links"></a>相關連結

- [隔離控制項](office-365-isolation-controls.md)
- [人員控制項](office-365-personnel-controls.md)
- [技術控制項](office-365-technology-controls.md)
- [監視及稽核的存取控制](office-365-monitoring-and-auditing-access-controls.md)
- [Yammer 企業存取控制](office-365-yammer-enterprise-access-controls.md)