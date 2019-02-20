---
title: Office 365 回報功能
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-analytics
description: 報告功能在 Office 365 中的說明。
ms.openlocfilehash: f750ac6647199ef14bd6605535797e00c1cab961
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/20/2019
ms.locfileid: "30090895"
---
# <a name="office-365-reporting-features"></a>Office 365 回報功能 

## <a name="introduction"></a>簡介
Office 365 中的 [報表] 功能提供各種 Azure Active Directory (AD)、 Exchange Online 裝置管理、 監督檢閱及資料外洩防護 (DLP) 的稽核報告。這些是不同且不同 Office 365 活動報告。

## <a name="office-365-reports-dashboard"></a>Office 365 報告儀表板
Office 365 系統管理中心預覽的報表儀表板顯示不同 Office 365 流量活動。Office 365 全域管理員或 Exchange Online、 SharePoint Online、 或 Skype 商務系統管理員可以取得更精細洞察力到該服務的使用狀況。報告可提供前瞻如取用特定 Office 365 服務已啟動與 Office Professional Plus 多少郵件通過組織的使用者數量的使用者人數。上次 7、 30、 90、 及 180 天內有報告。

目前提供了下列報告：
- [電子郵件活動報告](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--Email-activity-1cbe2c00-ca65-4fb9-9663-1bbfa58ebe44)
- [Microsoft Office 啟用報表](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--Microsoft-Office-activations-87c24ae2-82e0-4d1e-be01-c3bcc3f18c60)
- [SharePoint Online 網站流量報告](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--SharePoint-site-usage-4ecfb843-e5d5-464d-8bf6-7ed512a9b213)
- [OneDrive for Business 使用情況報告](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Preview--OneDrive-for-Business-usage-0de3b312-c4e8-4e4b-a02d-32b2f726a680)
- [Yammer 活動報告](https://support.office.com/article/View-the-Yammer-Activity-report-in-the-Office-365-admin-center-preview-c7c9f938-5b8e-4d52-b1a2-c7c32cb2312a)
- [Skype 商務活動報告](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/activity-report)
- [Skype 商務等活動報告](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/peer-to-peer-activity-report)
- [Skype 商務會議召集人報表](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/conference-organizer-activity-report)
- [Skype 商務會議參與者活動報告](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/conference-participant-activity-report)

如需詳細資訊，請參閱[Office 365 系統管理中心中的活動報告](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)。


## <a name="azure-active-directory-reports"></a>Azure Active Directory 報告
Office 365 使用 Azure AD 驗證及身分識別管理。Office 365 系統管理員可以使用 Azure 所產生的報告會尋找不尋常的活動及未經授權的存取其資料。您可以使用 Azure AD 中存取及使用狀況報告取得完整性及安全性貴組織的目錄的可見性。使用此資訊，以系統管理員可以更妥善地決定其中可能安全性風險可能，讓他們可以充分計劃以減輕這些風險。

Azure AD 報告可匯出至 Microsoft Excel 及相互關聯到其他資料來自 Office 365，例如提供深入了解 access、 驗證及應用程式層級活動的稽核記錄搜尋的結果。當啟用 Azure AD Premium 進階的異常及資源使用情況報告可用。這些進階協助改善組織的安全性狀況與說明組織回應的潛在威脅利用有關裝置存取和應用程式使用狀況分析報告。如需詳細資訊，請參閱[Azure Active Directory 報告](https://docs.microsoft.com/azure/active-directory/reports-monitoring/overview-reports/)。

## <a name="exchange-online-audit-reports"></a>Exchange Online 稽核報告
Exchange Online 稽核報告包含信箱存取及組織的 Exchange Online 租用戶系統管理員所做的變更的詳細資訊。啟用信箱稽核後，您可以使用下表中的工作來執行報告和匯出 Exchange Online 稽核記錄。

>**附註**： 您必須啟用信箱稽核記錄的信箱，使稽核的事件都儲存在該信箱的稽核記錄中。如果信箱稽核記錄未啟用信箱，該信箱的事件將不會儲存在稽核記錄，並將不會出現在信箱稽核報告。如需詳細資訊，請參閱[啟用信箱稽核](https://support.office.com/article/Enable-mailbox-auditing-in-Office-365-aaca8987-5b62-458b-9882-c28476a66918)。

| 工作 | 描述 |
|----------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [執行非擁有者信箱存取報告](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report) | 會顯示已已經由之信箱的擁有者以外的某人來存取的信箱清單。報告包含誰存取信箱的相關資訊、 他們萬一信箱中的動作和動作是否已成功。 |
| [匯出信箱稽核記錄](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs) | 信箱稽核記錄檔包含在存取和信箱的信箱擁有者以外的使用者所採取的動作的資訊。系統管理員可以指定日期範圍，以產生報表以及信箱。記錄所匯出的 xml、 附加至郵件並傳送給特定使用者為系統管理員所決定。 |
| [執行系統管理員角色群組報告](https://docs.microsoft.com/Office365/SecurityCompliance/eop/run-an-administrator-role-group-report-in-eop-eop) | 系統管理員角色群組用來指派給使用者的管理權限。這些權限允許使用者執行如重設密碼的管理工作、 建立或修改信箱，並指派給其他使用者的管理員權限。系統管理角色群組報告給角色群組，包括新增或移除成員顯示變更。 |
| [檢視管理員稽核記錄](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log) | 管理員稽核記錄報告清單所有建立、 更新及刪除 Exchange Online 中的系統管理員所執行的功能。記錄項目提供的哪些 cmdlet 所執行、 哪些參數所使用、 誰執行此指令程式，以及哪些物件所影響的資訊。 |
| [信箱內容搜尋並保留](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) | 在信箱上提供任何變更為就地 eDiscovery 或就地保留設定的詳細的資訊。 |
| [匯出管理員稽核記錄](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/search-role-group-changes) | 系統稽核記錄檔記錄管理的特定動作例如建立、 更新及刪除 Exchange Online。記錄檔的結果匯出至 XML 和系統管理員可以選擇將此記錄傳送至一組使用者。 |
| [執行每個信箱的訴訟資料暫留報告](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/per-mailbox-litigation-hold-report) | 提供的任何訴訟暫止的變更詳細資料保留在信箱上設定。 |
| [檢視和匯出外部管理員稽核記錄](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-external-admin-audit-log) | 包含外部系統管理員所執行的動作的詳細的資訊。項目提供哪些指令程式已執行、 使用哪些參數與任何動作的建立、 修改或刪除物件在 Exchange Online 中的資訊。 |

## <a name="device-compliance-reports"></a>裝置規範報告
您可以管理並保護行動裝置時他們透過 Office 365 行動裝置管理 (MDM) 連線至 Office 365 組織。行動裝置 like 智慧型手機與平板電腦用來存取工作電子郵件、 行事曆、 連絡人、 與文件播放大組中進行確定員工能夠搭配使用任何時候、 從任何地方。因此，很重要您保護組織的資訊。您可以使用 Office 365 MDM 設定的裝置安全性原則和存取規則，以及如果他們正在遺失或竊抹除行動裝置。

MDM 規範報告提供之原則的已設定組織的安全存取 Office 365 資料的行動裝置概觀 （英文）。報表允許的裝置的規範狀態、 報告的違規、 封鎖的裝置和裝置數量已清除因為安全性原則篩選。如需詳細資訊，請參閱[概觀 （英文） 的行動裝置管理 Office 365](https://support.office.com/article/Overview-of-Mobile-Device-Management-for-Office-365-faa7d8e5-645d-4d59-839c-c8d4c1869e4a)。

## <a name="data-loss-prevention"></a>資料遺失防護
DLP 原則協助您管理安全性與組織中的資訊流程。您可以設定原則以封鎖內容的存取權、 加密資料，或通知的原則及原則違規使用中應用程式 DLP 原則提示使用者。DLP 報告提供深入的原則和規則比對、 覆寫及誤判數目。

您可以使用 Office 365 系統管理中心來檢視所偵測到的 DLP 原則中圖形的圖表或表格格式的訊息數目的相關資訊。尤其是 DLP 原則相符的傳送和接收郵件，並傳送和接收郵件的 DLP 規則相符。您也可以使用 Exchange 系統管理中心過去 24 小時內檢視數目比對、 覆寫及誤判針對每個原則。不過，此資料不提供為圖表。如果您要下載在 Excel 中使用的報表，您可以檢視更多詳細資料，例如寄件者的郵件上何種一天和哪些原則會比對所觸發。如需詳細資訊，請參閱 ＜[關於 DLP 原則偵測檢視報告](https://technet.microsoft.com/en-us/library/jj889415(v=exchg.150).aspx)。

## <a name="auditing-in-yammer-enterprise"></a>Yammer Enterprise 中的稽核
Yammer Enterprise 提供系統管理員能夠從其 Yammer 網路透過[Yammer 資料匯出 API](https://support.office.com/article/export-data-from-yammer-enterprise-b303d8f3-007d-4ad4-81f8-54fb1ecfb3f2)] 或 [手動透過 [Yammer 網路管理員] 頁面上的使用者活動資料匯出。匯出記錄檔的功能僅限於 Yammer 中的網路管理員。（所有 Office 365 全域管理員都是 Yammer 網路系統管理員）。

可匯出的下列資料：

| 檔案名稱 | 描述 |
|----------------------------|-------------------------------------------------------------------------|
| Users.csv 儲存至 | 在網路中的所有新擱置中及已擱置使用者 |
| Messages.csv | 在網路中的所有郵件 |
| Files.csv （中繼資料） | 中繼資料檔案名稱，例如檔案上載程式識別碼在上傳、 之類 API URL。 |
| Files.csv （原始檔） | Zip 檔案由使用者上傳到 Yammer 的原始檔案 |
| Topics.csv | 建立在網路上的主題 |
| Pages.csv | 在網路中的使用者所建立的頁面 （附註） |
| Admins.csv | 所有已驗證網路上的管理員 |
| Networks.csv | 所有 Yammer 外部網路 |

*表 3-Yammer 網路資料可用的檔案匯出客戶*

Yammer Enterprise 資料也是可透過 Office 365 活動報告。此外，Yammer 主動資料透過使用公開透過 Office 365 管理活動 API 的其他記錄以及原因能夠使用 Power BI。請參閱這些功能的詳細資訊的[Office 藍圖](https://fasttrack.microsoft.com/roadmap?filters=yammer)。
