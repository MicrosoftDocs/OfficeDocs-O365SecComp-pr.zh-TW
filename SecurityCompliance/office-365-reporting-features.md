---
title: Office 365 回報功能
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-analytics
description: 報告功能，在 Office 365 的說明。
ms.openlocfilehash: 5e765045982d6788ee93550fa8041a52efb306c0
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2019
ms.locfileid: "31000246"
---
# <a name="office-365-reporting-features"></a>Office 365 回報功能 

## <a name="introduction"></a>簡介
Office 365 中的報告功能提供各種不同的 Azure Active Directory (AD)，Exchange Online 中，裝置管理、 主管檢閱和資料外洩防護 (DLP) 的稽核報告。 這些是不同與不同 Office 365 活動報告。

## <a name="office-365-reports-dashboard"></a>Office 365 報告儀表板
Microsoft 365 系統管理中心預覽中的報告儀表板會顯示 Office 365 流量活動。 Office 365 全域系統管理員，或 Exchange Online、 SharePoint Online 或商務用 Skype 系統管理員，可以取得該服務的使用狀況細微深入資訊。 報告可提供見解例如耗用特定的 Office 365 服務，及 Office Professional Plus，多少郵件流經組織已啟用的使用者人數的使用者數目。 報告可在上次 7、 30、 90，及 180 天。

有下列報告：
- [電子郵件活動報告](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--Email-activity-1cbe2c00-ca65-4fb9-9663-1bbfa58ebe44)
- [Microsoft Office 啟用報告](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--Microsoft-Office-activations-87c24ae2-82e0-4d1e-be01-c3bcc3f18c60)
- [SharePoint Online 網站流量報告](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--SharePoint-site-usage-4ecfb843-e5d5-464d-8bf6-7ed512a9b213)
- [商務用 OneDrive 使用狀況報告](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Preview--OneDrive-for-Business-usage-0de3b312-c4e8-4e4b-a02d-32b2f726a680)
- [Yammer 活動報告](https://support.office.com/article/View-the-Yammer-Activity-report-in-the-Office-365-admin-center-preview-c7c9f938-5b8e-4d52-b1a2-c7c32cb2312a)
- [Skype 商務活動報告](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/activity-report)
- [Skype 商務-對等活動報告](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/peer-to-peer-activity-report)
- [Skype 商務會議召集人報表](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/conference-organizer-activity-report)
- [Skype 商務會議參與者活動報告](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/conference-participant-activity-report)

如需詳細資訊，請參閱 <<c0>在 Microsoft 365 系統管理中心的活動報告。


## <a name="azure-active-directory-reports"></a>Azure Active Directory 報告
Office 365 會使用 Azure AD 的驗證與身分識別管理。 Office 365 系統管理員可以使用 Azure 所產生的報告來查看不尋常的活動] 和 [未經授權的存取其資料。 您可以使用 Azure AD 中的存取和使用狀況報告，以取得貴組織的目錄的安全性與完整性的可視性。 利用此資訊，系統管理員可以更妥善地判斷其中可能的安全性風險可能，以便他們可以充分計劃以降低這些風險。

Azure AD 報告可匯出至 Microsoft Excel 及相互關聯到從 Office 365，其他資料，例如稽核記錄搜尋，以提供深入的存取、 驗證及應用程式層級活動的結果。 啟用 Azure AD Premium 時，可使用進階的異常和資源使用狀況報告。 這些進階的協助來改善組織的安全性狀態，並協助組織回應潛在威脅利用有關裝置存取與應用程式使用狀況分析報告。 如需詳細資訊，請參閱[Azure Active Directory 報告](https://docs.microsoft.com/azure/active-directory/reports-monitoring/overview-reports/)。

## <a name="exchange-online-audit-reports"></a>Exchange Online 稽核報告
Exchange Online 稽核報告包含信箱的存取和組織的 Exchange Online 租用戶系統管理員所做的變更的詳細資訊。 一旦啟用信箱稽核，您可以使用下表中的工作執行報告和匯出稽核記錄以 Exchange Online。

>**附註**： 您必須啟用信箱稽核記錄每個信箱，讓稽核的事件都儲存在該信箱的稽核記錄檔中。 如果信箱稽核記錄不會啟用信箱，該信箱的事件不會儲存在稽核記錄並不會出現在信箱稽核報告。 如需詳細資訊，請參閱[啟用信箱稽核](https://support.office.com/article/Enable-mailbox-auditing-in-Office-365-aaca8987-5b62-458b-9882-c28476a66918)。

| 工作 | 描述 |
|----------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [執行非擁有者信箱存取報告](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report) | 會顯示已經存取的信箱擁有者以外的信箱清單。 報告包含誰存取信箱的相關資訊，請在信箱中，採取的動作和動作是否已成功。 |
| [匯出信箱稽核記錄](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs) | 信箱稽核記錄檔包含的存取和信箱擁有者以外的使用者所採取的信箱中的動作的詳細資訊。 系統管理員可以指定日期範圍，以產生報告以及信箱。 記錄檔匯出 XML 中，附加到郵件並傳送給特定使用者是由系統管理員。 |
| [執行系統管理員角色群組報告](https://docs.microsoft.com/Office365/SecurityCompliance/eop/run-an-administrator-role-group-report-in-eop-eop) | 系統管理員角色群組用於將系統管理員權限指派給使用者。 這些權限允許使用者執行系統管理工作，例如重設密碼、 建立或修改的信箱，並將系統管理員權限指派給其他使用者。 系統管理員角色群組報表顯示變更角色群組，包括新增或移除成員。 |
| [檢視管理員稽核記錄](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log) | 所有建立的系統管理員稽核記錄報告清單更新及刪除 Exchange Online 中的系統管理員所執行的函式。 記錄項目哪個 cmdlet 所執行、 已使用哪些參數、 執行者指令程式，以及受影響的哪些物件提供的資訊。 |
| [信箱內容搜尋和保留](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) | 在信箱上提供任何變更為 「 就地 eDiscovery 或原有範圍暫止設定的詳細的資訊。 |
| [匯出系統管理員稽核記錄](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/search-role-group-changes) | 例如： 建立特定的系統管理動作，系統管理員稽核記錄會記錄更新和刪除在 Exchange Online。 記錄檔的結果會被匯出成 XML 和系統管理員可以選擇將此記錄傳送至一組使用者。 |
| [執行每個信箱的訴訟資料暫留報告](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/per-mailbox-litigation-hold-report) | 提供的任何訴訟暫止的變更詳細資料保留在信箱上設定。 |
| [檢視和匯出外部系統管理員稽核記錄](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-external-admin-audit-log) | 包含外部系統管理員所執行的動作詳細的資料。 項目提供哪個 cmdlet 已執行、 已使用哪些參數，並建立、 修改或刪除 Exchange Online 中的物件的任何動作的資訊。 |

## <a name="device-compliance-reports"></a>裝置合規性報告
您可以管理與保護行動裝置時他們正在使用 Office 365 行動裝置管理 (MDM) 連線至 Office 365 組織。 行動裝置，像是智慧型手機及平板電腦用來存取公司電子郵件、 行事曆、 連絡人、 和文件播放的大組件中確保員工都能夠隨時隨地，搭配從任何地方。 因此，很重要，您會保護您組織的資訊。 若要設定裝置安全性原則和存取規則，並清除行動裝置，如果他們正在遺失或遭竊，您可以使用 Office 365 MDM。

MDM 規範符合性報告提供已設定組織的安全存取 Office 365 資料的行動裝置原則的概觀。 報告可讓篩選的裝置合規性狀態、 回報的違規、 封鎖的裝置，並多少部裝置已清除由於安全性原則。 如需詳細資訊，請參閱 < <b0>Overview of Mobile Device Management for Office 365</b0>。

## <a name="data-loss-prevention"></a>資料遺失防護
DLP 原則協助您管理安全性與組織中的資訊流程。 您可以設定要封鎖內容的存取權、 加密資料，或通知使用者原則和使用中應用程式 DLP 原則提示的原則違規的原則。 DLP 報告提供深入的原則和規則相符項目、 覆寫及誤判數。

您可以使用 Microsoft 365 系統管理中心，檢視之圖形的圖表或表格格式中的 DLP 原則所偵測到的郵件數目的相關資訊。 具體而言，DLP 原則相符的傳送和接收郵件，並傳送和接收郵件的 DLP 規則相符。 您也可以使用 Exchange 系統管理中心過去 24 小時內檢視相符項目、 覆寫及誤判針對每個原則的數目。 不過，此資料不是以圖表形式提供。 如果您要下載在 Excel 中使用的報告，您可以檢視更多詳細資料，例如寄件者的郵件，在哪一天，以及哪些原則符合所觸發。 如需詳細資訊，請參閱 <<c0>檢視關於 DLP 原則偵測的報告。

## <a name="auditing-in-yammer-enterprise"></a>Yammer Enterprise 中的稽核
Yammer 企業提供系統管理員能夠從他們的 Yammer 網路透過[Yammer 資料匯出 API](https://support.office.com/article/export-data-from-yammer-enterprise-b303d8f3-007d-4ad4-81f8-54fb1ecfb3f2)中，或以手動方式透過 Yammer 網路管理員] 頁面上的使用者活動資料匯出。 匯出記錄檔的能力會限制在 Yammer 中的網路系統管理員。 （所有 Office 365 全域系統管理員都是 Yammer 網路管理員）。

可以匯出下列資料：

| 檔名 | 描述 |
|----------------------------|-------------------------------------------------------------------------|
| Users.csv | 在網路中的所有擱置中新功能及擱置使用者 |
| Messages.csv | 在網路中的所有郵件 |
| Files.csv （中繼資料） | 中繼資料檔案名稱，例如檔案 API URL 上, 傳者 ID，在上傳等等。 |
| Files.csv （原始的檔案） | Zip 檔案已由使用者上傳至 Yammer 的原始檔案 |
| Topics.csv | 在網路上建立的主題 |
| Pages.csv | 在網路中的使用者所建立的頁面 （附註） |
| Admins.csv | 所有已驗證的網路上的系統管理員 |
| Networks.csv | 所有 Yammer 外部網路 |

*表 3-Yammer 網路資料檔案可用來匯出的客戶*

Yammer Enterprise 資料也可透過 Office 365 活動報告。 此外，Yammer 積極地使用資料的 [在公開額外的記錄，透過 Office 365 管理活動 API，和原因的能力使用 Power BI。 這些功能，請參閱[Office 藍圖](https://fasttrack.microsoft.com/roadmap?filters=yammer)如需詳細資訊。
