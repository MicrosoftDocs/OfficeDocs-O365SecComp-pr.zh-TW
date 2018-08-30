---
title: Office 365 eDiscovery 與搜尋功能概觀 （英文）
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
ms.collection: Strat_O365_Enterprise
description: Overview of eDiscovery 功能，以及 Office 365 內其他搜尋功能來稽核和透明度。
ms.openlocfilehash: 2d5cc2533c195b51f685aebd8da4462518116905
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526785"
---
# <a name="ediscovery-and-search-features"></a>電子文件探索與搜尋功能 

## <a name="ediscovery"></a>eDiscovery
EDiscovery 功能提供了單一位置的系統管理員、 法務人員及其他已授權使用者是否能進行完整的調查到 Office 365 使用者活動。執行搜尋，可以使用適當的權限的安全性主管和就地保留中的內容。搜尋結果項目相同的結果跳內容的搜尋，但是會套用任何保留建立 eDiscovery 案例。EDiscovery 搜尋的結果會加密安全性，並可以使用[進階的 eDiscovery](https://support.office.com/article/office-365-advanced-ediscovery-fd53438a-a760-45f6-9df4-861b50161ae4)分析所匯出的資料。

## <a name="content-search"></a>內容搜尋
[內容搜尋](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a)與熊掌可以兼舊的 eDiscovery 搜尋工具新的 eDiscovery 搜尋工具中的安全性與規範中心提供改善的調整和效能功能。您可以使用內容搜尋來搜尋信箱、 公用資料夾、 SharePoint Online 站台及 OneDrive for Business 位置。內容搜尋已特別設計非常大的搜尋。有無限制的信箱和可搜尋的網站數目而定。也有可以同時執行的搜尋數目沒有限制。之後您執行搜尋、 內容來源數目和估計的搜尋結果的搜尋頁面，您可以在其中預覽結果，或將它們匯出到本機電腦上的 [詳細資料] 窗格中顯示的數目。如果貴組織的 Office 365 企業版 E5 訂閱，您也可以使用強大的分析功能的[Office 365 進階 eDiscovery](http://go.microsoft.com/fwlink/p/?LinkID=620116)分析[準備結果](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a#prepare)。

## <a name="audit-log-search"></a>稽核記錄搜尋
除了追蹤其 Office 365 組織中的變更，也可以檢視稽核報告和匯出稽核記錄的客戶。稽核的 Office 365 租用戶中啟用後，使用者和系統管理活動的租用戶會記錄在事件記錄檔並供搜尋。例如，您可以使用信箱稽核記錄來追蹤信箱擁有者以外的使用者信箱上執行動作。進一步、 法務人員可以使用搜尋和篩選功能如果使用者已檢視或下載特定文件或系統管理員已執行使用者管理活動或過去 90 天承租人設定所做的變更。搜尋結果可以包含重要資訊識特定使用者或系統管理員所進行的活動。請參閱[Office 365 中的 Audited 活動](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c#auditlogevents)的使用者和登入 Office 365 的管理活動的描述。

從 SharePoint Online 和 OneDrive for Business 的事件記錄檔中顯示其相符項目的 30 分鐘內。從 Exchange Online 事件會出現稽核記錄檔中出現的 24 小時內。從 Azure AD 的登入事件可用的項目、 分鐘內與其他目錄從 Azure AD 是可用的事件發生的 24 小時內。也可以供進一步分析匯出稽核記錄搜尋結果中的事件。（50000 項目最多可以從單一的稽核記錄搜尋匯出。若要匯出多個項目，此限制，減少日期範圍，或是執行多個稽核記錄搜尋。）

下表詳細說明一些活動報告中顯示的資訊。請參閱[Office 365 中的詳細的內容稽核記錄](https://support.office.com/article/detailed-properties-in-the-office-365-audit-log-ce004100-9e7f-443e-942b-9b04098fcfc3
)的相關的內容所收集的每一個 Office 365 工作負載的詳細資訊。

| 屬性 | 描述 |
|----------------|----------------------------------------------------------------------------------------------------------------------|
| 日期 | 日期及時間的事件 |
| 使用者 | 執行巨集指令的使用者 |
| ClientIP | 活動已記錄時使用的裝置 IPv4 或 IPv6 位址。 |
| CreationTime | 日期及時間的國際標準時間 (UTC) 使用者執行活動時。 |
| EventSource | 會識別事件發生。可能的值為 SharePoint 和 ObjectModel。 |
| ID | 報告項目的識別碼。識別碼可唯一識別報告項目。 |
| 作業 | 使用者或對應到此使用者活動顯示結果中選取值的活動的名稱。 |
| OrganizationId | 發生此事件的組織的 Office 365 服務的 GUID。 |
| UserAgent | 使用者瀏覽器瀏覽器所提供的資訊。 |
| UserId | 執行該詞彙所產生正在記錄一筆記錄的動作 （作業屬性中所指定） 的使用者。 |
| UserType | 使用者執行作業的類型。下列的值會指出使用者類型。 |
|  | 0 表示一般使用者。 |
|  | 2 會指出在 Office 365 組織中的系統管理員。 |
|  | 3 指出 Microsoft 資料中心系統管理員或資料中心系統帳戶。 |
| 工作量 | Office 365 服務中發生活動。此屬性的可能值是： |
|  | Exchange Online |
|  | SharePoint Online |
|  | 商務用 OneDrive |
|  | Azure Active Directory 報告 |


如需詳細的步驟來搜尋 Office 365 稽核記錄檔，請參閱[[Office 365 安全性及規範中心中搜尋稽核記錄檔](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)。

## <a name="search-unified-audit-log"></a>整合的稽核記錄檔中搜尋
在 [安全性及規範中心的稽核記錄搜尋功能可用來搜尋整合的稽核記錄。Office 365 還提供使用遠端 PowerShell 此記錄檔中搜尋的能力。尤其是 Exchange Online PowerShell 中的[搜尋 UnifiedAuditLog 指令程式](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/Search-UnifiedAuditLog?view=exchange-ps)可用來搜尋事件與相關使用者作業從 Exchange Online、 SharePoint Online、 OneDrive for Business 和 Azure AD 的整合的稽核記錄檔。您可以搜尋指定的日期範圍內的所有事件或您可以當做篩選依據特定準則，例如特定動作、 執行巨集指令或目標物件之使用者的結果。系統管理員可以使用最多可同時執行 Exchange Online PowerShell 工作階段的 3 分割大型的日期範圍的搜尋設定。
