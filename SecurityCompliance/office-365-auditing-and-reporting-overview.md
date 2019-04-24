---
title: 稽核和報告在 Microsoft 雲端服務
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
- M365-analytics
description: 稽核和報告內 Office 365、 Microsoft 365，以及服務保證功能的概觀。
ms.openlocfilehash: a5df0dcb6f762723c6ec0102b2c39f1bc157720c
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262965"
---
# <a name="auditing-and-reporting-in-microsoft-cloud-services"></a>稽核和報告在 Microsoft 雲端服務

## <a name="introduction"></a>簡介
Microsoft 雲端服務包含數個的稽核和報告功能，客戶可以用來追蹤使用者和其租用戶，變更其 Exchange Online 和 SharePoint Online 租用戶組態設定，例如中的系統管理活動與文件及其他項目由使用者所做的變更。 客戶可以更有效率地管理使用者體驗、 減輕風險，以及滿足合規義務使用我們的雲端服務中可用的報告與稽核資訊。

## <a name="security--compliance-centers"></a>安全性 & 合規性中心
[Office 365 安全性 & 合規性中心](https://protection.office.com)、 [Microsoft 365 安全性中心](https://security.microsoft.com)中， [Microsoft 365 合規性中心](https://compliance.microsoft.com)一次入口網站來保護您組織中的資料，且其包含多個的稽核和報告功能。 這些中心專為具有資料的組織保護或法務遵循需求，或想要稽核使用者和系統管理員活動。 您可以存取這些中心使用您訂閱的系統管理員帳戶。

這些中心包含您提供數個功能的存取權的導覽窗格：
- **提醒**-可讓您管理警示、 檢視安全性相關的提醒，以及管理進階的提醒使用[Office 365 雲端 App 安全性](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/office-365-cas-overview)。 
- **權限**-可讓您[指派權限](https://support.office.com/article/Give-users-access-to-the-Office-365-Security-Compliance-Center-2cfce2c8-20c5-47f9-afc4-24b059c1bd76)等合規性系統管理員、 電子文件探索管理員] 中，其他人給您組織中的人員，讓他們可以執行這些中心中的工作。 您可以指派每個中心中的大部分功能的權限，但必須使用 Exchange 系統管理中心和 SharePoint 系統管理中心設定其他權限。
- **威脅管理**-可讓您建立及套用來設定[資料外洩防護](https://support.office.com/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e)(DLP) 原則，為您的組織，來設定電子郵件篩選，使用[Office 365 行動裝置管理](https://support.office.com/article/Overview-of-Mobile-Device-Management-for-Office-365-faa7d8e5-645d-4d59-839c-c8d4c1869e4a)、 裝置管理原則反惡意程式碼、 DomainKeys Identified Mail (DKIM)、 安全附件、 安全連結和 OAuth 應用程式。
- **資料控管**-可讓您[匯入電子郵件或其他系統到 Office 365 的 SharePoint 資料](https://support.office.com/article/Import-PST-files-or-SharePoint-data-to-Office-365-ba688e0a-0fcb-4bd7-8e57-2b669564ea84)，[封存信箱設定](https://support.office.com/article/Enable-archive-mailboxes-in-the-Office-365-Security-Compliance-Center-268a109e-7843-405b-bb3d-b9393b2342ce)，並設定[保留原則](https://support.office.com/article/Retention-in-the-Office-365-Security-Compliance-Center-2a0fc432-f18c-45aa-a539-30ab035c608c)的電子郵件和其他組織內的內容。
- **搜尋 & 調查**-提供[內容搜尋](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a)、[稽核記錄檔](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)、 隔離及[eDiscovery 案例管理](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da)工具，可快速切入跨 Exchange Online 信箱、 群組和公用資料夾，SharePoint 活動線上和商務用 OneDrive。
- **報告**-可讓您快速存取[報告](https://support.office.com/article/Reports-in-the-Office-365-Security-Compliance-Center-7acd33ce-1ec8-49fb-b625-43bac7b58c5a)的 SharePoint Online、 OneDrive for Business、 Exchange Online 中，和 Azure AD。
- **服務保證**-提供 Microsoft 如何維護安全性、 隱私權和 Office 365、 Azure、 Microsoft Dynamics CRM Online、 Microsoft Intune 和其他雲端服務與全球標準的合規性的相關資訊。 也包括第三方 ISO、 SOC、 和其他稽核報告，以及稽核控制措施，提供不同的控制項的已測試及驗證 Office 365 的第三方稽核者所需的詳細資訊的存取。

## <a name="service-assurance"></a>服務保證
我們的客戶在管制產業中的許多受限於廣泛的符合性需求。 若要執行自己的風險評估，客戶通常需要 Office 365 會維護其資料的隱私權與安全性的深入資訊。 Microsoft 會竭盡所其雲端服務中的客戶資料的隱私權與安全性，並提供其作業，並讓您輕鬆存取獨立的規範符合性報告和 「 評估 」 的透明檢視贏得客戶的信任。

服務保證提供透明度作業，以及 Microsoft 如何維護安全性、 隱私權和法規遵循 Office 365 中的客戶資料的資訊。 它包含以及文件庫的白皮書、 常見問題集，以及其他材料例如資料加密、 資料恢復功能、 安全性事件管理和多個 Office 365 主題的協力廠商稽核報告。 若要執行自己的法規風險評估，客戶可以使用這項資訊。 法務人員可以指派 「 服務保證使用者 」 角色，才能讓使用者能夠存取服務保證。 租用戶系統管理員也可以提供外部使用者，例如獨立稽核員，透過[Microsoft 雲端服務信任入口網站](http://aka.ms/STP)(STP) 的服務保證儀表板中的資訊的存取權。 如需如何存取在 STP 上的詳細資訊，請造訪[開始使用服務信任入口網站的 Office 365 商務版、 Azure 和 Dynamics CRM Online 訂閱](http://aka.ms/STPHelp)。

## <a name="onedrive-for-business-admin-center"></a>OneDrive 商務版系統管理中心
在新的 Microsoft OneDrive 系統管理中心可協助您快速並輕鬆管理貴組織的 OneDrive for Business 設定在一個位置。 若要使用 OneDrive 系統管理中心，您必須允許存取 onedrive.com。 您也必須是全域系統管理員為您的組織或具有 SharePoint 系統管理員角色的自訂系統管理員。 存取 OneDrive for Business 系統管理中心預覽在[https://admin.onedrive.com](https://admin.onedrive.com/)。

主要功能包括像是搜尋稽核記錄檔、 使用 DLP、 保留、 eDiscovery 和警示的關鍵案例的連結至適當的管理中心提供系統管理員的合規性區域。

## <a name="related-links"></a>相關連結
- [電子文件探索與搜尋功能](office-365-ediscovery-and-search-features.md)
- [Office 365 回報功能](office-365-reporting-features.md)
- [Office 365 管理活動 API](office-365-management-activity-api.md)
- [Office 365 信箱移轉](office-365-mailbox-migrations.md)
- [Office 365 工程內部記錄](office-365-internal-logging.md)