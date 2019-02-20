---
title: 在 Office 365 租用戶隔離
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
- M365-security-compliance
description: Microsoft 如何強制執行 Office 365 租用戶隔離的摘要。
ms.openlocfilehash: c0b58f149ace1e6b1ecf179534bdd75d15840a7f
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/20/2019
ms.locfileid: "30090985"
---
# <a name="tenant-isolation-in-office-365"></a><span data-ttu-id="fc9b7-103">在 Office 365 租用戶隔離</span><span class="sxs-lookup"><span data-stu-id="fc9b7-103">Tenant Isolation in Office 365</span></span>

<span data-ttu-id="fc9b7-p101">其中一個雲端運算同時許多客戶之間的共用、 常見的基礎架構的概念、 而導致的規模的主要好處。此概念稱為*多重租用*。Microsoft 持續運作來確保我們雲端服務多承租人架構支援企業層級安全性、 機密性、 隱私權、 完整性及可用性的標準。</span><span class="sxs-lookup"><span data-stu-id="fc9b7-p101">One of the primary benefits of cloud computing is concept of a shared, common infrastructure across numerous customers simultaneously, leading to economies of scale. This concept is called *multi-tenancy*. Microsoft works continuously to ensure that the multi-tenant architectures of our cloud services support enterprise-level security, confidentiality, privacy, integrity, and availability standards.</span></span>

<span data-ttu-id="fc9b7-107">根據重大的投資和收集哪些[高可信度電腦運算](https://www.microsoft.com/en-us/twc/default.aspx)及[安全性開發技術支援週期](http://www.microsoft.com/security/sdl/default.aspx)的經驗，Microsoft 雲端服務所設計與所有的租用戶會加入到所有可能有害的假設其他的承租人與我們已實作安全性措施阻止影響安全性或服務的另一個承租人或存取另一個承租人的內容從一個承租人的動作。</span><span class="sxs-lookup"><span data-stu-id="fc9b7-107">Based upon the significant investments and experience gathered from [Trustworthy Computing](https://www.microsoft.com/en-us/twc/default.aspx) and the [Security Development Lifecycle](http://www.microsoft.com/security/sdl/default.aspx), Microsoft cloud services were designed with the assumption that all tenants are potentially hostile to all other tenants, and we have implemented security measures to prevent the actions of one tenant from affecting the security or service of another tenant, or accessing the content of another tenant.</span></span>

<span data-ttu-id="fc9b7-108">維護租用戶隔離多承租人環境中的兩個主要目標是：</span><span class="sxs-lookup"><span data-stu-id="fc9b7-108">The two primary goals of maintaining tenant isolation in a multi-tenant environment are:</span></span>
1.  <span data-ttu-id="fc9b7-109">防止外的洩或未經授權的存取到客戶內容不同的承租人;與</span><span class="sxs-lookup"><span data-stu-id="fc9b7-109">Preventing leakage of, or unauthorized access to, customer content across tenants; and</span></span>
2.  <span data-ttu-id="fc9b7-110">防止一個承租人的動作有不良影響的另一個承租人的服務</span><span class="sxs-lookup"><span data-stu-id="fc9b7-110">Preventing the actions of one tenant from adversely affecting the service for another tenant</span></span>

<span data-ttu-id="fc9b7-111">整個可防止從危及系統的 Office 365 服務或應用程式或取得未經授權的存取權的其他承租人或本身，包括 Office 365 系統資訊的客戶的 Office 365 中已實作多個表單的保護：</span><span class="sxs-lookup"><span data-stu-id="fc9b7-111">Multiple forms of protection have been implemented throughout Office 365 to prevent customers from compromising Office 365 services or applications or gaining unauthorized access to the information of other tenants or the Office 365 system itself, including:</span></span>
- <span data-ttu-id="fc9b7-112">Office 365 服務的每個租用戶中的客戶內容的邏輯隔離是透過 Azure Active Directory 授權和角色型存取控制來達成。</span><span class="sxs-lookup"><span data-stu-id="fc9b7-112">Logical isolation of customer content within each tenant for Office 365 services is achieved through Azure Active Directory authorization and role-based access control.</span></span>
- <span data-ttu-id="fc9b7-113">SharePoint Online 提供資料儲存區層級的隔離機制。</span><span class="sxs-lookup"><span data-stu-id="fc9b7-113">SharePoint Online provides data isolation mechanisms at the storage level.</span></span>
- <span data-ttu-id="fc9b7-p102">Microsoft 使用嚴格的實體安全性、 背景檢測及多重分層的加密策略來保護機密性和客戶內容完整性。所有的 Office 365 資料中心有生物特徵存取控制項，具有最要求棕櫚列印至實體的存取。此外，所有美國型 Microsoft 員工已順利完成所需標準背景] 核取雇用程序的一部分。如需有關用於系統管理存取 Office 365 中的控制項的詳細資訊，請參閱[Office 365 系統管理存取控制項](office-365-administrative-access-controls-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="fc9b7-p102">Microsoft uses rigorous physical security, background screening, and a multi-layered encryption strategy to protect the confidentiality and integrity of customer content. All Office 365 datacenters have biometric access controls, with most requiring palm prints to gain physical access. In addition, all U.S.-based Microsoft employees are required to successfully complete a standard background check as part of the hiring process. For more information on the controls used for administrative access in Office 365, see [Office 365 Administrative Access Controls](office-365-administrative-access-controls-overview.md).</span></span>
- <span data-ttu-id="fc9b7-p103">Office 365 使用服務端技術加密客戶內容靜態及傳輸，包括 BitLocker，每個檔案加密的傳輸層安全性 (TLS) 及網際網路通訊協定安全性 (IPsec)。如需 Office 365 中的加密特定的詳細資訊，請參閱[Office 365 中的資料加密技術](office-365-encryption-in-the-microsoft-cloud-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="fc9b7-p103">Office 365 uses service-side technologies that encrypt customer content at rest and in transit, including BitLocker, per-file encryption, Transport Layer Security (TLS) and Internet Protocol Security (IPsec). For specific details about encryption in Office 365, see [Data Encryption Technologies in Office 365](office-365-encryption-in-the-microsoft-cloud-overview.md).</span></span>

<span data-ttu-id="fc9b7-120">在一起，上述模式保護提供提供威脅保護和減輕等於提供單獨的實體隔離的強大的邏輯隔離控制項。</span><span class="sxs-lookup"><span data-stu-id="fc9b7-120">Together, the above-listed protections provide robust logical isolation controls that provide threat protection and mitigation equivalent to that provided by physical isolation alone.</span></span>

## <a name="related-links"></a><span data-ttu-id="fc9b7-121">相關的連結</span><span class="sxs-lookup"><span data-stu-id="fc9b7-121">Related Links</span></span>
- [<span data-ttu-id="fc9b7-122">Azure Active Directory 中的隔離與存取控制</span><span class="sxs-lookup"><span data-stu-id="fc9b7-122">Isolation and Access Control in Azure Active Directory</span></span>](office-365-isolation-in-azure-active-directory.md)
- [<span data-ttu-id="fc9b7-123">Office Graph 與 Delve 中的租用戶隔離</span><span class="sxs-lookup"><span data-stu-id="fc9b7-123">Tenant Isolation in the Office Graph and Delve</span></span>](office-365-isolation-in-graph-and-delve.md)
- [<span data-ttu-id="fc9b7-124">Office 365 搜尋中的租用戶隔離</span><span class="sxs-lookup"><span data-stu-id="fc9b7-124">Tenant Isolation in Office 365 Search</span></span>](office-365-isolation-in-office-365-search.md)
- [<span data-ttu-id="fc9b7-125">Office 365 影片中的租用戶隔離</span><span class="sxs-lookup"><span data-stu-id="fc9b7-125">Tenant Isolation in Office 365 Video</span></span>](office-365-isolation-in-office-365-video.md)
- [<span data-ttu-id="fc9b7-126">資源限制</span><span class="sxs-lookup"><span data-stu-id="fc9b7-126">Resource Limits</span></span>](office-365-resource-limits.md)
- [<span data-ttu-id="fc9b7-127">監視及測試租用戶界限</span><span class="sxs-lookup"><span data-stu-id="fc9b7-127">Monitoring and Testing Tenant Boundaries</span></span>](office-365-monitoring-and-testing.md)
- [<span data-ttu-id="fc9b7-128">Office 365 中的隔離與存取控制</span><span class="sxs-lookup"><span data-stu-id="fc9b7-128">Isolation and Access Control in Office 365</span></span>](office-365-isolation-in-office-365.md)