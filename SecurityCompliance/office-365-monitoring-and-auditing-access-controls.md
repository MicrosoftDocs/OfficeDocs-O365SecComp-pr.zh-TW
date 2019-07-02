---
title: Office 365 監視和審核存取控制
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
description: '摘要: Office 365 中可用的各種監視和審核存取控制的摘要。'
ms.openlocfilehash: 39ee2b535c89419e161558cba2122e325228ffb1
ms.sourcegitcommit: 7b5e4a7a51f3cdd741deb77a2d60a18e2316618d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/01/2019
ms.locfileid: "33520713"
---
# <a name="monitoring-and-auditing-access-controls-in-office-365"></a>Office 365 的監視和審核存取控制

Microsoft 會對 Office 365 內發生的所有委派、許可權和作業進行廣泛的監視和審核。 Office 365 存取控制是一種自動化程式, 是以最小特權的原則為基礎, 而且包含資料存取控制和審核:

- 所有允許的存取都可針對唯一的使用者進行追蹤。 系統管理員負責處理客戶內容。
- 會捕獲存取控制要求、核准和管理作業記錄檔, 以進行安全性和惡意事件的分析。
- 存取層級會以接近即時的安全性群組成員資格來檢查, 以確保只有具備授權的業務理由且符合資格需求的使用者才可存取系統。
- Office 365、其存取控制和支援服務, 包括 Azure Active Directory 和實體資料中心, 會定期由獨立的協力廠商進行審核, 以符合[ISO/IEC 27001](https://www.microsoft.com/en-us/TrustCenter/Compliance/iso-iec-27001)、 [ISO/iec 27018](https://www.microsoft.com/en-us/TrustCenter/Compliance/iso-iec-27018)、 [SOC](https://www.microsoft.com/en-us/TrustCenter/Compliance/SOC)、 [FedRAMP](https://www.microsoft.com/en-us/TrustCenter/Compliance/FedRAMP)及其他[標準](https://www.microsoft.com/en-us/TrustCenter/Compliance?service=Office#Icons)。
- Office 365 工程師必須參加年度的安全性訓練、審查更高的存取最佳程式, 並確認 Microsoft 的安全性和隱私權原則, 以維護服務的權利。

偵測到可疑活動 (例如短期間內的多個失敗的登入) 時, 會觸發自動化的警示。 Office 365 安全性回應小組使用機器學習和大型資料分析, 來審查和分析活動、尋找不規則的存取模式, 以及主動回應反常和違法的活動。 Microsoft 也會使用專屬的滲透測試小組, 並以週期性的紅色小組和藍色的小組練習來尋找服務中的安全性和存取控制問題。 客戶可以使用審核報告以及 Office 365 所提供的管理活動 API, 來驗證存取控制系統的效率。

如需詳細資訊, 請參閱 Office 365 中的[office 365 管理活動 API 參考](https://msdn.microsoft.com/en-us/library/office/mt227394.aspx)和[審核與報告](office-365-auditing-and-reporting-overview.md)。
