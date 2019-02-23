---
title: Office 365 中的系統管理存取控制
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 摘要： Office 365 系統管理存取控制項和資料分類的概觀。
ms.openlocfilehash: b23fcdcb6c790b3860a24a555424beb3bb99e4f4
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216023"
---
# <a name="administrative-access-controls-in-office-365"></a>Office 365 中的系統管理存取控制 

## <a name="introduction"></a>簡介
Microsoft 已投資嚴重與據以在系統及自動化大部分的 Office 365 作業時刻意限制客戶內容的 Microsoft access 的控制項。人們控管服務及軟體的操作服務。這可讓 Microsoft Office 365 管理向外延展，以及管理客戶內容惡意執行者，例如 Microsoft 工程師，依此類推矛網路釣魚內部威脅的風險。

根據預設，Microsoft 工程師會有零出位置管理權限和客戶內容零出位置存取 Office 365 中。Microsoft 工程師可以有限制、 稽核、 及安全存取客戶內容的有限的時間，但是只有當時所需的服務作業且時由 Microsoft 資深管理 （及成員的客戶而言核准授權給客戶 Lockbox 功能，客戶）。

Microsoft 提供線上服務，包括 Office 365 中，使用多個表單的雲端傳遞：

- **公用 Cloud** -包含多租用戶版本的 Office 365、 Azure、 和裝載於 「 北美地區 」、 南美洲、 歐洲、 亞洲、 澳洲等其他服務。
- **國民雲朵**-例如中國 （這由 21Vianet 21vianet) 中的 Office 365 與 Office 365 德國包括 （但不包括這些上方另有說明），美國以外的所有統領和第三方 21vianet 雲朵 (這由 Microsoft 21vianet 但在 [下一種模型德文資料者，Deutsche Telekom 控制及監視客戶資料並包含客戶資料的系統的 Microsoft access）。
- **政府雲朵**-包含可用來美國政府客戶的 Office 365 和 Azure 服務。

基於本文的詳細資訊，Office 365 服務包括[Exchange Online](https://docs.microsoft.com/Exchange/exchange-online)、 [Exchange Online Protection](https://docs.microsoft.com/Office365/SecurityCompliance/eop/exchange-online-protection-overview)、 [SharePoint Online](https://docs.microsoft.com/sharepoint/sharepoint-online) （包括[OneDrive for Business](https://docs.microsoft.com/OneDrive/onedrive)） 和[Skype for Business](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online)的其他資訊關於某些[Yammer Enterprise](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US)存取控制項。其他 Office 365 服務已超出本文範圍。

## <a name="office-365-access-controls"></a>Office 365 的存取控制
基於存取控制，Office 365 的資料會歸類為客戶資料或其他類型的資料。客戶資料是由或代表 「 客戶使用的 Office 365 服務，例如客戶內容 （內容直接建立或由 Office 365 使用者包括電子郵件、 SharePoint Online 內容、 立即訊息、 上傳到客戶提供的所有資料行事曆項目、 文件及儲存在 Office 365 中的連絡人） 和使用者識別資訊 (EUII) （這是唯一的使用者，或資料的連結給個別使用者但不包括客戶內容）。 

其他類型的資料包含帳戶資料 （包括系統管理的資料，這是當他們註冊或購買服務及付款儀器，例如信用的相關資訊的付款資料卡片詳細資料時由系統管理員所提供的資訊）公司識別資訊 (可用來識別租用戶; 的資料或使用狀況資料 ； 它不是連結至個別使用者並不包含客戶內容)，與系統中繼資料 （包括包含的組態設定的服務記錄檔系統狀態、 Microsoft IP 位址和訂閱及租用戶的技術資訊）。

Microsoft 已建立存取控制機制來確定無人具有未的資料的存取權的客戶資料或存取控制 (用來管理存取其他類型的資料或在函數中的環境，包括存取客戶內容或 EUII ； 它包含 Microsoft 密碼、 安全性憑證和驗證相關的其他資料） 或未實體、 邏輯、 或遠端存取 Office 365 實際執行環境。

使用 Microsoft 的操作 Office 365 的存取控制項可分為三種類別：
- 隔離控制項
- 人員控制項
- 技術控制項

當組合，這些控制項協助防止與 Office 365 中偵測到惡意的動作。除了隔離、 人員及 Microsoft 所使用的技術控制項中，有控制項的第四個類別： 所實作的客戶。

Office 365 可讓您管理在內部部署環境中受管理的相同方式資料中有多少資料。會設定組織的 Office 365 自動的人員會變成全域管理員 (admin)。全域管理員具有管理入口網站 （例如管理中心和遠端 PowerShell） 中的所有功能的存取權及可以建立或編輯使用者、 將系統管理員角色指派給其他人、 重設使用者密碼、 管理使用者授權、 管理網域，並核准客戶 Lockbox總而言之的要求。我們建議每個組織要指定至少兩種管理帳戶]，並根據貴組織的大小，您可能會想要指定數個系統管理員提供不同功能。如需指派管理角色和權限的資訊，請參閱[指派 Office 365 中的系統管理員角色](https://support.office.com/article/Assigning-admin-roles-in-Office-365-eac4d046-1afd-4f1a-85fc-8219c79e1504)和[有關 Office 365 系統管理員角色](https://support.office.com/article/Permissions-in-Office-365-DA585EEA-F576-4F55-A1E0-87090B6AAA9D)。


## <a name="related-links"></a>相關的連結

- [隔離控制項](office-365-isolation-controls.md)
- [人員控制項](office-365-personnel-controls.md)
- [技術控制項](office-365-technology-controls.md)
- [監視及稽核的存取控制](office-365-monitoring-and-auditing-access-controls.md)
- [Yammer 企業存取控制](office-365-yammer-enterprise-access-controls.md)