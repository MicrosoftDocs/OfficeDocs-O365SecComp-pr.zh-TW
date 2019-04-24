---
title: Office 365 監視和稽核的存取控制
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
description: 摘要： 各種監視和稽核存取控制 Office 365 內提供摘要。
ms.openlocfilehash: 753acd1a0bd0d3b4a834263071d431b63836f399
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262535"
---
# <a name="monitoring-and-auditing-access-controls-in-office-365"></a><span data-ttu-id="f92bc-103">監視和稽核的 Office 365 中的存取控制</span><span class="sxs-lookup"><span data-stu-id="f92bc-103">Monitoring and Auditing Access Controls in Office 365</span></span>

<span data-ttu-id="f92bc-104">Microsoft 會執行廣泛的監視與稽核所有委派、 所有使用的權限，以及所有 Office 365 內發生的作業。</span><span class="sxs-lookup"><span data-stu-id="f92bc-104">Microsoft performs extensive monitoring and auditing of all delegation, all use of privileges, and all operations that occur within Office 365.</span></span> <span data-ttu-id="f92bc-105">Office 365 的存取控制為基礎的最低權限，並納入資料的存取控制與稽核原則自動化程序：</span><span class="sxs-lookup"><span data-stu-id="f92bc-105">Office 365 access control is an automated process built on the principle of least privilege and to incorporate data access controls and audits:</span></span>
- <span data-ttu-id="f92bc-106">追蹤至唯一的使用者，讓系統管理員負責的客戶內容處理所有允許的存取。</span><span class="sxs-lookup"><span data-stu-id="f92bc-106">All permitted access is traceable to a unique user, making administrators accountable for their handling of customer content.</span></span>
- <span data-ttu-id="f92bc-107">存取控制項要求、 核准，管理作業記錄檔會擷取與分析安全性觀點及惡意的事件。</span><span class="sxs-lookup"><span data-stu-id="f92bc-107">Access control requests, approvals, and administrative operations logs are captured for analysis of security insights and malicious events.</span></span>
- <span data-ttu-id="f92bc-108">存取層級中檢閱接近即時根據的安全性群組成員資格，以確保只有使用者已獲授權業務理由，且符合資格需求有系統的存取。</span><span class="sxs-lookup"><span data-stu-id="f92bc-108">Access levels are reviewed in near real-time based on security group membership to ensure that only users who have authorized business justifications and meet the eligibility requirements have access to the systems.</span></span>
- <span data-ttu-id="f92bc-109">Office 365、 其存取控制和支援服務，包括 Azure Active Directory 和我們的實體資料中心，定期[ISO/IEC 27001](https://www.microsoft.com/en-us/TrustCenter/Compliance/iso-iec-27001)、 [ISO/IEC 27018](https://www.microsoft.com/en-us/TrustCenter/Compliance/iso-iec-27018)、 [SOC](https://www.microsoft.com/en-us/TrustCenter/Compliance/SOC)、 規範的獨立第三方稽核[FedRAMP](https://www.microsoft.com/en-us/TrustCenter/Compliance/FedRAMP)和其他的[標準](https://www.microsoft.com/en-us/TrustCenter/Compliance?service=Office#Icons)。</span><span class="sxs-lookup"><span data-stu-id="f92bc-109">Office 365, its access controls, and supporting services, including Azure Active Directory and our physical datacenters, are regularly audited by independent third-parties for compliance with [ISO/IEC 27001](https://www.microsoft.com/en-us/TrustCenter/Compliance/iso-iec-27001), [ISO/IEC 27018](https://www.microsoft.com/en-us/TrustCenter/Compliance/iso-iec-27018), [SOC](https://www.microsoft.com/en-us/TrustCenter/Compliance/SOC), [FedRAMP](https://www.microsoft.com/en-us/TrustCenter/Compliance/FedRAMP), and other [standards](https://www.microsoft.com/en-us/TrustCenter/Compliance?service=Office#Icons).</span></span>
- <span data-ttu-id="f92bc-110">Office 365 工程師所需採取每年的安全性訓練檢閱提高權限的存取最佳作法與風險，且同意 Microsoft 的安全性與隱私權原則，以繼續維護其權利至服務。</span><span class="sxs-lookup"><span data-stu-id="f92bc-110">Office 365 engineers are required to take yearly security training reviewing elevated access best practices and risks and acknowledge Microsoft's security and privacy policies to continue maintaining their entitlements to the service.</span></span>

<span data-ttu-id="f92bc-111">偵測到可疑的活動時，例如在短時間內多個失敗的登入，便會觸發自動的提醒。</span><span class="sxs-lookup"><span data-stu-id="f92bc-111">Automated alerts are triggered when suspicious activity is detected, such as multiple failed logins within a short period.</span></span> <span data-ttu-id="f92bc-112">在 Office 365 安全性回應小組會使用機器學習和大的資料分析，檢閱和分析不規則存取模式的活動，以及主動回應異常和非法活動。</span><span class="sxs-lookup"><span data-stu-id="f92bc-112">The Office 365 Security Response team uses machine learning and big data analysis to review and analyze activity for irregular access patterns and to proactively respond to anomalous and illicit activities.</span></span> <span data-ttu-id="f92bc-113">Microsoft 也採用滲透測試人員專用的小組，並在定期紅色小組及藍色小組凝聚練習，來尋找安全性和存取控制服務中的問題。</span><span class="sxs-lookup"><span data-stu-id="f92bc-113">Microsoft also employs a dedicated team of penetration testers and engages in periodic red team and blue team exercises to find security and access control issues in the service.</span></span> <span data-ttu-id="f92bc-114">客戶也可能會使用稽核報告和管理活動 API 由 Office 365 提供確認訪問控制系統的有效性。</span><span class="sxs-lookup"><span data-stu-id="f92bc-114">Customers may also verify the effectiveness of access control systems by using audit reports and the management activity API provided by Office 365.</span></span> 

<span data-ttu-id="f92bc-115">如需詳細資訊，請參閱[Office 365 管理活動 API 參考資料](https://msdn.microsoft.com/en-us/library/office/mt227394.aspx)及[稽核與 Office 365 中的報告](office-365-auditing-and-reporting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="f92bc-115">For more information, see [Office 365 Management Activity API reference](https://msdn.microsoft.com/en-us/library/office/mt227394.aspx) and [Auditing and Reporting in Office 365](office-365-auditing-and-reporting-overview.md).</span></span>
