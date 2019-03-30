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
description: 摘要： Office 365 系統管理存取控制及資料分類的概觀。
ms.openlocfilehash: 90dd00049e7e3a9b9548530c42b1c21534cfd7fd
ms.sourcegitcommit: 1261a37c414111f869df5791548a768d853fda60
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/30/2019
ms.locfileid: "31004130"
---
# <a name="administrative-access-controls-in-office-365"></a>Office 365 中的系統管理存取控制 

## <a name="introduction"></a>簡介
Microsoft 已投資頻繁並據此系統和自動化 Office 365 的大部分作業時刻意限制 Microsoft 的客戶內容存取權的控制項。 人類，進而管理服務，及軟體的運作該服務。 這可讓 Microsoft，以管理 Office 365 規模，以及管理的客戶內容，例如惡意執行者的 Microsoft 工程師，依此類推矛網路釣魚的內部威脅風險。

根據預設，Microsoft 工程師會有零常設系統管理權限和客戶內容零常設存取 Office 365 中。 Microsoft 工程師可以有限制、 稽核、 及安全的存取的客戶內容的有限的時間，但是只有當所需的服務作業，且由成員的 Microsoft 資深 management （和客戶的核准時客戶加密箱功能，客戶授權）。

Microsoft 提供的線上服務，包括 Office 365 中，使用多個表單的雲端傳遞：

- **公用定域機組**-包含多租用戶版本的 Office 365、 Azure 及裝載於 「 北美地區 」、 南美洲、 歐洲、 亞洲、 澳洲等其他服務。
- **國家雲中**-包含所有統領和協力廠商運作定域機組外美國 （除了上面所述），例如在中國 （這由 21Vianet 運作的） 中的 Office 365 和 Office 365 Germany 中 (這由 Microsoft 運作，但模式下德國資料受託人，Deutsche Telekom 控制及監視 Microsoft 客戶資料與存取權包含客戶資料的系統）。
- **政府定域機組**-包含可用於美國政府版客戶的 Office 365 與 Azure 服務。

基於本文的詳細資訊，Office 365 服務包含[Exchange Online](https://docs.microsoft.com/Exchange/exchange-online)、 [Exchange Online Protection](https://docs.microsoft.com/Office365/SecurityCompliance/eop/exchange-online-protection-overview)、 [SharePoint Online](https://docs.microsoft.com/sharepoint/sharepoint-online) （包括[商務用 OneDrive](https://docs.microsoft.com/OneDrive/onedrive)） 和[商務用 Skype](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online)，以及其他資訊關於[某些 Yammer 企業](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US)存取控制。 其他 Office 365 服務已超出本文範圍。

## <a name="office-365-access-controls"></a>Office 365 的存取控制
以存取控制項來說，Office 365 資料分類為客戶資料或其他類型的資料。 客戶資料是由或代表客戶使用 Office 365 服務，例如客戶內容 （內容直接建立或上傳的 Office 365 使用者包括電子郵件，SharePoint Online 內容、 立即訊息，透過客戶提供的所有資料行事曆項目、 文件和連絡人會儲存在 Office 365） 及使用者識別資訊 (EUII) （這是唯一的使用者，或資料，是連結至個別使用者，但不包含客戶內容）。 

其他的資料類型包括帳戶資料 （包括管理資料，也就是當他們註冊或購買服務和付款資料，也就是資訊付款儀器，例如信用卡卡詳細資料時，由系統管理員所提供的資訊）公司識別資訊 (可以用來識別租用戶中; 的資料或使用狀況資料; 它不是連結至個別使用者並不會納入客戶內容)，以及系統中繼資料 （包括含有組態設定的服務記錄檔系統狀態、 Microsoft IP 位址和訂用帳戶及租用戶的技術資訊）。

Microsoft 已經建立存取控制機制，以確保沒有其他有未核准的資料存取權的客戶資料或存取控制 (用來管理存取其他類型的資料或在函數中的環境，包括存取客戶內容或 EUII; 它包含 Microsoft 密碼、 安全性憑證，以及其他驗證相關的資料） 或未核准實體、 邏輯、 或遠端存取 Office 365 實際執行環境。

Microsoft 用於操作 Office 365 的存取控制可分為三種類別：
- 隔離控制措施
- 人員控制措施
- 技術控制措施

當組合時，這些控制項協助防止，並在 Office 365 中偵測惡意的動作。 除了隔離、 人員及使用 Microsoft 技術控制措施，沒有控制項的第四個類別： 所實作的客戶。

Office 365 可讓您管理您有多少中資料的相同的方式受管理的內部部署環境中的資料。 註冊組織 Office 365 自動的人員會成為全域系統管理員 （系統管理員）。 全域系統管理員管理入口網站 （例如，系統管理中心和遠端 PowerShell） 中有權存取所有的功能可以建立或編輯使用者、 指派系統管理員角色給其他人、 重設使用者密碼、 管理使用者授權、 管理網域] 中，並核准客戶加密箱而在其他方面的要求。 我們建議每個組織指定至少兩個系統管理員帳戶，並依據組織的大小，您可能想要指定多個系統管理員負責不同職責。 如需指派系統管理員角色和權限的資訊，請參閱[指派 Office 365 中的系統管理員角色](https://support.office.com/article/Assigning-admin-roles-in-Office-365-eac4d046-1afd-4f1a-85fc-8219c79e1504)和[關於 Office 365 系統管理員角色](https://support.office.com/article/Permissions-in-Office-365-DA585EEA-F576-4F55-A1E0-87090B6AAA9D)。


## <a name="related-links"></a>相關連結

- [隔離控制措施](office-365-isolation-controls.md)
- [人員控制措施](office-365-personnel-controls.md)
- [技術控制措施](office-365-technology-controls.md)
- [監視及稽核的存取控制](office-365-monitoring-and-auditing-access-controls.md)
- [Yammer 企業存取控制](office-365-yammer-enterprise-access-controls.md)