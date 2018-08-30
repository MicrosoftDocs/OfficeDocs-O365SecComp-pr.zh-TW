---
title: Office 365 監視和稽核功能的存取控制
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
description: 摘要： 各種監視和稽核存取控制項可在 Office 365 中的摘要。
ms.openlocfilehash: 7ef25d62ce3c4fa320dd0b164183c6f67be7d76d
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22527273"
---
# <a name="monitoring-and-auditing-access-controls-in-office-365"></a>監控和稽核存取 Office 365 中的控制項

Microsoft 執行廣泛的監控和稽核的所有委派、 所有用途權限，以及出現在 Office 365 內的所有作業。Office 365 的存取控制是建置在這當中的最低權限和併入資料存取控制項和稽核自動化程序：
- 所有允許的存取是唯一的使用者，讓系統管理員的努力其處理的客戶內容可進行追蹤。
- 存取控制邀請、 核准、 及管理作業記錄檔會擷取所進行的安全性見解與建議惡意事件的分析。
- 附近即時根據的安全性群組成員資格以確保僅限已獲得授權商務只要有以及符合資格需求使用者可以存取系統的存取層級是已檢閱。
- Office 365、 存取控制項和支援服務，包括 Azure Active Directory 與我們實體資料中心來定期獨立遵守[ISO/IEC 27001](https://www.microsoft.com/en-us/TrustCenter/Compliance/iso-iec-27001)、 [ISO/IEC 27018](https://www.microsoft.com/en-us/TrustCenter/Compliance/iso-iec-27018)、 [SOC](https://www.microsoft.com/en-us/TrustCenter/Compliance/SOC)、 第三方的稽核[FedRAMP](https://www.microsoft.com/en-us/TrustCenter/Compliance/FedRAMP)、 及其他[標準 （英文）](https://www.microsoft.com/en-us/TrustCenter/Compliance?service=Office#Icons)。
- 為每年的安全性訓練檢閱提高權限的存取最佳作法和風險和確認 Microsoft 的安全性及隱私權原則繼續執行維護其權利服務所需 office 365 工程師。

偵測到可疑活動時，例如在短時間內的多個失敗登入觸發自動的提醒。Office 365 安全性回應小組使用機器學習與 big 資料分析來檢閱和分析活動不正常空格的存取模式和主動回應異常和非法活動。Microsoft 也會採用滲透測試人員專用的小組與會定期紅色小組和藍色小組中請練習來尋找安全性和存取控制服務中的問題。客戶也可能會確認效益的存取控制系統使用稽核報告和管理活動 Office 365 所提供的 API。 

如需詳細資訊，請參閱[Office 365 管理活動 API 參考資料](https://msdn.microsoft.com/en-us/library/office/mt227394.aspx)與[稽核與 Office 365 中的報告](office-365-auditing-and-reporting-overview.md)。
