---
title: Office 365 報告功能
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
- M365-analytics
description: Office 365 內報表功能的說明。
ms.openlocfilehash: e23942e574dbeb42248470c151e57e672b4704d6
ms.sourcegitcommit: aa60a6cdf83c67576e858668d1182cd4fffeb5e0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2019
ms.locfileid: "33622463"
---
# <a name="office-365-reporting-features"></a>Office 365 報告功能 

## <a name="introduction"></a>簡介

Office 365 中的 [報告] 功能可提供 Azure Active Directory (AD)、Exchange Online、裝置管理、主管審查和資料遺失防護 (DLP) 的各種核查報告。 這些報告與 Office 365 活動報告不同並分開。

## <a name="office-365-reports-dashboard"></a>Office 365 報告儀表板

Microsoft 365 系統管理中心預覽中的 [報告] 儀表板會顯示跨 Office 365 的使用方式活動。 Office 365 全域管理員或 Exchange Online、SharePoint Online 或商務用 Skype 系統管理員可以取得該服務使用方式的詳細資訊。 例如, 特定 Office 365 服務中的使用者數目、已啟用 Office Professional Plus 的使用者數目, 以及郵件流向組織的數量。 報告適用于過去7、30、90和180天。

下列是可用的報告:

- [電子郵件活動報告](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--Email-activity-1cbe2c00-ca65-4fb9-9663-1bbfa58ebe44)
- [Microsoft Office 啟用報告](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--Microsoft-Office-activations-87c24ae2-82e0-4d1e-be01-c3bcc3f18c60)
- [SharePoint Online 網站使用方式報告](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--SharePoint-site-usage-4ecfb843-e5d5-464d-8bf6-7ed512a9b213)
- [商務用 OneDrive 使用方式報告](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Preview--OneDrive-for-Business-usage-0de3b312-c4e8-4e4b-a02d-32b2f726a680)
- [Yammer 活動報告](https://support.office.com/article/View-the-Yammer-Activity-report-in-the-Office-365-admin-center-preview-c7c9f938-5b8e-4d52-b1a2-c7c32cb2312a)
- [商務用 Skype 活動報告](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/activity-report)
- [商務用 Skype 對等活動報告](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/peer-to-peer-activity-report)
- [商務用 Skype 會議召集人報告](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/conference-organizer-activity-report)
- [商務用 Skype 會議參與者活動報告](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/conference-participant-activity-report)

如需詳細資訊, 請參閱[Microsoft 365 系統管理中心的活動報告](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)。

## <a name="azure-active-directory-reports"></a>Azure Active Directory 報告

Office 365 會使用 Azure AD 進行驗證和身分識別管理。 Office 365 系統管理員會使用 Azure 所產生的報告, 來識別不尋常的活動, 以及未經授權存取其資料。 您可以在 Azure AD 中使用存取和使用方式報告, 以深入瞭解組織的目錄完整性及安全性。 有了這種資訊, 您就可以找出並降低可能的安全性風險。

Azure AD 報告可以匯出至 Microsoft Excel, 並與 Office 365 中的其他資料相關聯。 例如, audit log search 的結果可讓您瞭解存取、驗證和應用層級的活動。 Azure AD Premium 可使用高級異常和資源使用方式報告。 這些高級報告可協助改善您的安全性狀況, 並協助您對裝置存取和應用程式使用方式套用分析, 以協助您回應潛在的威脅。 如需詳細資訊, 請參閱[Azure Active Directory 報告](https://docs.microsoft.com/azure/active-directory/reports-monitoring/overview-reports/)。

## <a name="exchange-online-audit-reports"></a>Exchange Online Audit Reports

Exchange Online audit 報表包含有關信箱存取的詳細資料, 以及系統管理員對您的 Exchange Online 租使用者所做的變更。 使用信箱審核, 您可以使用下表中的工作來執行報表及匯出 Exchange Online audit 記錄檔。

> [!NOTE]
> 您必須啟用每個信箱的信箱審核記錄, 以便將已審核的事件儲存在該信箱的 audit 記錄中。 如果信箱的信箱審核記錄未啟用信箱, 則該信箱的事件將不會儲存在 audit 記錄檔中, 而且不會出現在信箱審計報告中。 如需詳細資訊, 請參閱[啟用信箱審核](https://support.office.com/article/Enable-mailbox-auditing-in-Office-365-aaca8987-5b62-458b-9882-c28476a66918)。

| 工作 | 描述 |
|----------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [執行非擁有者信箱存取報告](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report) | 顯示由其他人存取的信箱清單, 而非信箱的擁有者。 報告包含誰存取信箱的相關資訊、他們在信箱中採取的動作, 以及動作是否成功。 |
| [匯出信箱稽核記錄](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs) | 信箱 audit 記錄檔包含信箱擁有者以外的使用者所採取之信箱中之存取和動作的資訊。 系統管理員可以指定信箱以及日期範圍來產生報告。 這些記錄會以 XML 儲存, 並附加至郵件, 並傳送給特定使用者 (由系統管理員決定)。 |
| [執行系統管理員角色群組報告](https://docs.microsoft.com/Office365/SecurityCompliance/eop/run-an-administrator-role-group-report-in-eop-eop) | 系統管理員角色群組會將管理許可權指派給使用者。 這些許可權可讓使用者執行系統管理工作, 例如重設密碼、建立或修改信箱, 以及將系統管理員許可權指派給其他使用者。 系統管理員角色群組報告會顯示角色群組的變更, 包括新增或移除成員。 |
| [查看管理員審查記錄檔](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log) | 系統管理員 audit log 報告會列出系統管理員在 Exchange Online 中執行的所有建立、更新及刪除功能。 記錄專案提供有關執行 Cmdlet 的資訊、所使用的參數、執行 Cmdlet 的人員, 以及受影響的物件。 |
| [信箱內容搜尋和保留](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) | 提供信箱的就地 eDiscovery 或就地保留設定的任何變更詳細資料。 |
| [匯出系統管理員審查記錄檔](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/search-role-group-changes) | 系統管理員審核記錄檔會記錄在 Exchange Online 中建立、更新及刪除等特定的管理動作。 記錄的結果會匯出為 XML, 系統管理員可以選擇將此記錄傳送給一組使用者。 |
| [執行每個信箱的訴訟資料暫留報告](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/per-mailbox-litigation-hold-report) | 提供信箱上訴訟暫止設定變更的詳細資料。 |
| [查看及匯出外部系統管理員審查記錄檔](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-external-admin-audit-log) | 包含外部系統管理員所執行之動作的詳細資料。 這些專案會提供執行指令程式的資訊、所使用的參數, 以及在 Exchange Online 中建立、修改或刪除物件的任何動作。 |

## <a name="device-compliance-reports"></a>裝置合規性報告

您可以使用 Office 365 行動裝置管理 (MDM) 來管理和保護連線至 Office 365 組織的行動裝置。 用來存取工作電子郵件、行事曆、連絡人及檔的行動裝置, 可確保員工可以隨時和任何地方都能運作。 保護貴組織的資訊非常重要。 您可以使用 Office 365 MDM 來設定裝置安全性原則和存取規則。 如果遺失或被盜, 您也可以使用 Office 365 MDM 來清除行動裝置。

MDM 合規性報告提供組織所設定的原則, 以保護存取 Office 365 資料的行動裝置。 此報告允許依規範狀態、報告違規、封鎖的裝置, 以及因安全性原則而被清除的裝置數目來篩選裝置。 如需詳細資訊, 請參閱[Office 365 的行動裝置管理概述](https://support.office.com/article/Overview-of-Mobile-Device-Management-for-Office-365-faa7d8e5-645d-4d59-839c-c8d4c1869e4a)。

## <a name="data-loss-prevention"></a>資料遺失防護

DLP 原則可協助管理組織中資訊的安全性和流程。 您可以設定原則以封鎖對內容的存取、加密資料, 或使用應用程式中的 DLP 原則提示通知使用者原則和原則違規。 DLP 報告可讓您深入瞭解原則和規則相符、覆寫和誤報的數目。

您可以使用 Microsoft 365 系統管理中心來查看 DLP 原則所偵測到的郵件數目資訊。 DLP 報告可讓您深入瞭解已傳送和接收的郵件的原則和規則相符。 您也可以使用 Exchange 系統管理中心, 在過去24小時內, 查看每個原則的相符專案、覆寫和 false 陽性數目。 如果您下載 Excel 報表, 您可以查看更多詳細資料, 例如誰在哪一天傳送哪一封郵件, 以及觸發的原則相符專案。 如需詳細資訊, 請參閱[查看有關 DLP 原則](https://technet.microsoft.com/en-us/library/jj889415(v=exchg.150).aspx)偵測的報告。

## <a name="auditing-in-yammer-enterprise"></a>Yammer Enterprise 中的審核

Yammer Enterprise 讓系統管理員能夠透過[Yammer 資料匯出 API](https://support.office.com/article/export-data-from-yammer-enterprise-b303d8f3-007d-4ad4-81f8-54fb1ecfb3f2)從其 yammer 網路匯出使用者活動資料, 或是透過 yammer 網路管理頁面手動匯出。 匯出記錄的功能僅限於 Yammer 中的網路系統管理員。 (所有 Office 365 全域系統管理員都是 Yammer 網路系統管理員。)

可匯出下列資料:

| Filename | 描述 |
|----------------------------|-------------------------------------------------------------------------|
| Users.csv | 網路中所有的新、擱置及暫停的使用者 |
| Messages.csv | 網路中的所有郵件 |
| Files .csv (中繼資料) | 中繼資料, 例如 filename、檔案 API URL、上傳識別碼、上傳的位置等等。 |
| Files .csv (原始檔案) | 將使用者上傳的原始檔案的 Zip 檔案轉換成 Yammer |
| Topics.csv | 在網路上建立的主題 |
| Pages.csv | 網路中使用者所建立的頁面 (附注) |
| Admins.csv | 網路上所有已驗證的系統管理員 |
| Networks.csv | 所有 Yammer 外部網路 |

Yammer Enterprise 資料也可透過 Office 365 活動報告取得。 此外, Yammer 目前正在處理透過 Office 365 管理活動 API 公開額外記錄的功能, 以及使用 Power BI 來使用資料的原因。 如需這些功能的詳細資訊, 請參閱[Office 藍圖](https://fasttrack.microsoft.com/roadmap?filters=yammer)。
