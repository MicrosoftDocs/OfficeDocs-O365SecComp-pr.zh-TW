---
title: Office 365 中的稽核與回報
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 12/03/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- M365-analytics
description: 稽核與報告內 Office 365，以及服務保證功能概觀。
ms.openlocfilehash: 0167239e854d9b96d9505f4264ada225804eef96
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/20/2019
ms.locfileid: "30091035"
---
# <a name="auditing-and-reporting-in-office-365"></a>Office 365 中的稽核與回報

## <a name="introduction"></a>簡介
Microsoft 雲端服務包含數個稽核與報告客戶可用來追蹤使用者和系統管理活動內其租用戶，例如其 Exchange Online 和 SharePoint Online 的租用戶組態設定所做的變更的功能與使用者所做變更的文件及其他項目。客戶可以使用稽核資訊及報表我們 cloud services 所提供之更有效率地管理使用者經驗、 降低風險及滿足規範責任。

## <a name="office-365-security--compliance-center"></a>Office 365 安全規範中心
[Office 365 安全性 & 規範中心](https://support.office.com/article/Go-to-the-Office-365-Security-Compliance-Center-7e696a40-b86b-4a20-afcc-559218b7b1b8)是個停駐點入口網站的 Office 365 的資料保護和其包含許多稽核和報告功能。它是 Office 365 規範中心 」 的發展。規範中心的設計之組織的資料保護或規範需求或安全性 & 想要稽核使用者與管理員的活動。您可以使用安全性 & 規範中心管理所有組織的 Office 365 資料的符合性。您可以存取安全性 & 規範中心[http://protection.office.com](http://protection.office.com/)使用您的 Office 365 系統管理帳戶。

安全性 & 規範中心包括提供數項功能的存取權給您的導覽窗格：
- **提醒**-可讓您管理提醒、 檢視安全性相關的提醒及管理使用[Office 365 雲端應用程式安全性](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/office-365-cas-overview)的進階的提醒。 
- **權限**-可讓您[指派權限](https://support.office.com/article/Give-users-access-to-the-Office-365-Security-Compliance-Center-2cfce2c8-20c5-47f9-afc4-24b059c1bd76)等規範管理員、 eDiscovery 管理員] 中，與其他組織內的人，讓他們可以執行的安全性 & 規範中心的工作。您可以將指派權限的安全性 & 規範中心中的大部分功能，但必須使用 Exchange 系統管理中心和 SharePoint 系統管理中心來設定其他權限。
- **Threat management** -可讓您建立與套用資料裝置管理原則使用[Office 365 行動裝置管理](https://support.office.com/article/Overview-of-Mobile-Device-Management-for-Office-365-faa7d8e5-645d-4d59-839c-c8d4c1869e4a)] 來設定您的組織設定電子郵件篩選的[資料外洩防護](https://support.office.com/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e)(DLP) 原則反惡意程式碼、 DomainKeys 識別郵件 (DKIM)、 安全的附件、 安全的連結，與 OAuth 應用程式。
- **資料管理**-可讓您若要[匯入電子郵件或其他系統到 Office 365 的 SharePoint 資料](https://support.office.com/article/Import-PST-files-or-SharePoint-data-to-Office-365-ba688e0a-0fcb-4bd7-8e57-2b669564ea84)，[設定封存信箱](https://support.office.com/article/Enable-archive-mailboxes-in-the-Office-365-Security-Compliance-Center-268a109e-7843-405b-bb3d-b9393b2342ce)，並將[保留原則](https://support.office.com/article/Retention-in-the-Office-365-Security-Compliance-Center-2a0fc432-f18c-45aa-a539-30ab035c608c)的電子郵件和其他組織內的內容。
- **搜尋 & 調查**-提供快速切入活動不同 Exchange Online 信箱、 群組及公用資料夾、 SharePoint[內容搜尋](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a)、[稽核記錄](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)、 隔離及[eDiscovery 案件管理](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da)工具線上和 OneDrive for Business。
- **報告**-可讓您快速存取[報告](https://support.office.com/article/Reports-in-the-Office-365-Security-Compliance-Center-7acd33ce-1ec8-49fb-b625-43bac7b58c5a)的 SharePoint Online、 OneDrive for Business、 Exchange Online 和 Azure AD。
- **服務保證**-提供 Microsoft 如何維護安全性、 隱私權和全域標準遵守 for Office 365、 Azure、 Microsoft Dynamics CRM Online、 Microsoft Intune 及其他雲端服務的相關資訊。也包含的存取權與協力廠商 ISO、 SOC、 和其他稽核報告]，以及您可以稽核的控制項，提供各種控制項的已測試及驗證 Office 365 的協力廠商稽核者所需的詳細資訊。

## <a name="service-assurance"></a>服務保證
許多我們客戶的規範產業會受到廣泛規範需求。若要執行他們自己的風險評估，客戶通常需要有關 Office 365 的維護方式的安全性和隱私權其資料的深入資訊。Microsoft 是認可的安全性與隱私權在其雲端服務中的客戶資料並提供其作業並容易存取獨立的規範報告及評估的透明檢視證明客戶的信任。

服務保證提供透明度作業及 Microsoft 如何維護安全性、 隱私權和 Office 365 中的客戶資料的符合性的相關資訊。它包含在 Office 365 主題，例如資料加密、 資料恢復、 安全性附隨管理及其他的協力廠商稽核報告以及白皮書、 常見問題集及其他資料的文件庫。客戶可以使用這項資訊來執行其自己的法規風險評估。法務人員可以指派要讓使用者能夠存取服務保證"服務保證使用者 」 角色。承租人管理員也可以提供外部使用者，例如獨立 auditors 透過[Microsoft 雲端服務信任入口網站](http://aka.ms/STP)(STP) 服務保證儀表板中的資訊的存取權。如需如何存取 STP 的詳細資訊，請造訪[快速入門服務信任入口網站的 Office 365 商務、 Azure、 及 Dynamics CRM Online 訂閱](http://aka.ms/STPHelp)。

## <a name="onedrive-for-business-admin-center"></a>OneDrive for Business 系統管理中心
在新的 Microsoft OneDrive 系統管理中心可協助您快速和輕鬆地管理您的組織 OneDrive for Business 設定一個位置。若要使用 OneDrive 系統管理中心，您必須允許存取 onedrive.com。您也必須是組織的全域系統管理員或自訂的管理與 SharePoint 系統管理員角色。存取 OneDrive for Business admin center 預覽在[https://admin.onedrive.com](https://admin.onedrive.com/)。

主要功能包括 like 搜尋稽核記錄、 使用 DLP、 保留、 eDiscovery 及之通知的主要案例的 Office 365 安全性和規範中心提供系統管理員具有連結的規範區域。

## <a name="related-links"></a>相關的連結
- [電子文件探索與搜尋功能](office-365-ediscovery-and-search-features.md)
- [Office 365 回報功能](office-365-reporting-features.md)
- [Office 365 管理活動 API](office-365-management-activity-api.md)
- [Office 365 信箱移轉](office-365-mailbox-migrations.md)
- [Office 365 工程內部記錄](office-365-internal-logging.md)