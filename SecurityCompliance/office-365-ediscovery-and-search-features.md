---
title: Office 365 eDiscovery 和搜尋功能概述
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
description: 電子檔探索功能的總覽, 以及 Office 365 中的其他搜尋功能, 以供審計使用和透明度。
ms.openlocfilehash: 985a7fad9d321005439ea592b6fef8744a88220f
ms.sourcegitcommit: aa60a6cdf83c67576e858668d1182cd4fffeb5e0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2019
ms.locfileid: "33622453"
---
# <a name="ediscovery-and-search-features"></a>電子文件探索與搜尋功能 

## <a name="ediscovery"></a>eDiscovery

EDiscovery 功能為系統管理員、合規性監察官和其他授權使用者提供單一位置, 以在 Office 365 使用者活動中進行完整的調查。 具有適當許可權的安全性官員會執行搜尋並保留內容。 搜尋結果是您從內容搜尋取得的相同結果, 但不包括為任何套用的保留建立 eDiscovery 案例。 電子檔探索搜尋的結果會針對安全性進行加密, 您可以使用[高級 eDiscovery](https://support.office.com/article/office-365-advanced-ediscovery-fd53438a-a760-45f6-9df4-861b50161ae4)分析匯出的資料。

## <a name="content-search"></a>內容搜尋

[內容搜尋](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a)是 ediscovery 搜尋工具, 可提供比先前 eDiscovery 搜尋工具更佳的調整和效能功能。 您可以使用內容搜尋來搜尋信箱、公用資料夾、SharePoint Online 網站和商務用 OneDrive 位置。 內容搜尋支援大型搜尋。 您可以搜尋的信箱和網站數目沒有限制。 同時執行的搜尋數目也不會有任何限制。 執行搜尋之後, 會在 [搜尋] 頁面上的 [詳細資料] 窗格中顯示內容來源數目和預估的搜尋結果數目。 您可以預覽結果, 或將結果匯出至本機電腦。 如果您的組織有 Office 365 企業版 E5 訂閱, 您可以使用[office 365 高級 eDiscovery](http://go.microsoft.com/fwlink/p/?LinkID=620116)的功能強大的分析功能, 準備要進行分析的[結果](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a#prepare)。

## <a name="audit-log-search"></a>稽核記錄搜尋

除了在 Office 365 組織中追蹤變更之外, 您還可以查看審計報告及匯出的審計記錄檔。 一旦啟用 Office 365 租使用者的審計, 就會在事件記錄檔中記錄使用者和系統管理活動, 並讓其可供搜尋。 例如, 您可以使用信箱審核記錄來追蹤信箱擁有者以外的使用者對信箱所執行的動作。 合規性監察官可以針對特定使用者活動使用搜尋和篩選功能。 例如, 若要識別查看或下載特定檔的使用者, 如果系統管理員已執行使用者管理活動, 或在過去的90天內查看租使用者設定中的變更。 搜尋結果包含使用者或系統管理員所執行之特定活動的寶貴鑒證資訊。 請參閱[office 365 中的已審核活動](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c#auditlogevents), 以取得 office 365 中所記錄之使用者和系統管理活動的描述。

來自 SharePoint Online 和商務用 OneDrive 的事件會在記錄檔的30分鐘內顯示。 Exchange Online 中的事件會出現在發生24小時內的 [audit] 記錄中。 來自 Azure AD 的登入事件會在發生幾分鐘內提供, 而來自 Azure AD 的其他目錄事件則會在24小時內提供。 您可以在審計記錄搜尋結果中匯出通風口, 以進一步進行分析。 從單一審計記錄搜尋中, 最多可匯出50000個專案。 若要匯出此限制的更多專案, 請減少日期範圍或執行多個審核記錄搜尋。

下表詳細說明 [活動報告] 中顯示的部分資訊。 請參閱[office 365 audit 記錄檔中的詳細](https://support.office.com/article/detailed-properties-in-the-office-365-audit-log-ce004100-9e7f-443e-942b-9b04098fcfc3)資訊, 以取得每個 Office 365 工作負載所收集之屬性的詳細資訊。

| 屬性	 | 描述 |
|----------------|----------------------------------------------------------------------------------------------------------------------|
| 日期 | 事件的日期和時間 |
| 使用者 | 執行動作的使用者 |
| ClientIP | 記錄活動時所使用之裝置的 IPv4 或 IPv6 位址。 |
| CreationTime | 使用者執行活動時的日期和時間 (國際標準時間 (UTC))。 |
| EventSource | 識別發生的事件。 可能的值為 SharePoint 和 ObjectModel。 |
| ID | 報表專案的識別碼。 識別碼可唯一識別報表專案。 |
| 作業 | 使用者或活動的名稱, 對應于此使用者活動顯示結果中選取的值。 |
| OrganizationId | 發生事件之組織之 Office 365 服務的 GUID。 |
| UserAgent | 瀏覽器所提供之使用者瀏覽器的相關資訊。 |
| UserId | 執行動作的使用者 (在 Operation 屬性中指定), 導致記錄正在記錄中。 |
| UserType | 執行作業的使用者類型。 下列值表示使用者類型。 |
|  | 0表示一般使用者。 |
|  | 2表示您的 Office 365 組織中的系統管理員。 |
|  | 3表示 Microsoft 資料中心管理員或資料中心系統帳戶。 |
| 工作量 | 發生活動的 Office 365 服務。 此屬性可能的值為: |
|  | Exchange Online |
|  | SharePoint Online |
|  | 商務用 OneDrive |
|  | Azure Active Directory 報告 |

如需搜尋 Office 365 audit logs 的詳細步驟, 請參閱[在 office 365 中搜尋 audit logs](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)。

## <a name="search-unified-audit-log"></a>搜尋整合的審計記錄檔

使用 [Audit Log Search] 功能來搜尋統一的審計記錄檔。 Office 365 也提供使用遠端 PowerShell 搜尋此記錄的功能。 Exchange Online PowerShell 中的[UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/Search-UnifiedAuditLog?view=exchange-ps)指令程式是用來搜尋與使用者作業 (與 Exchange Online、SharePoint Online、商務用 OneDrive 和 Azure AD) 相關的整合審計記錄檔。 

您可以在指定的日期範圍內搜尋所有事件, 也可以依據特定的準則來篩選結果, 例如特定的動作、執行動作的使用者, 或目標物件。 系統管理員最多可以使用三個同時執行的 Exchange Online PowerShell 會話來分割大量的日期範圍搜尋。