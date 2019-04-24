---
title: Office 365 中的租用戶隔離
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
description: Microsoft 如何強制執行 Office 365 租用戶隔離摘要。
ms.openlocfilehash: 87fd8cddce830ef58bcaa08462d6bcb120d1e05f
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262375"
---
# <a name="tenant-isolation-in-office-365"></a><span data-ttu-id="9634f-103">Office 365 中的租用戶隔離</span><span class="sxs-lookup"><span data-stu-id="9634f-103">Tenant Isolation in Office 365</span></span>

<span data-ttu-id="9634f-104">雲端運算同時許多客戶之間的共用共通的基礎結構的概念，而導致的規模的主要好處之一。</span><span class="sxs-lookup"><span data-stu-id="9634f-104">One of the primary benefits of cloud computing is concept of a shared, common infrastructure across numerous customers simultaneously, leading to economies of scale.</span></span> <span data-ttu-id="9634f-105">此概念稱為*多重租用*。</span><span class="sxs-lookup"><span data-stu-id="9634f-105">This concept is called *multi-tenancy*.</span></span> <span data-ttu-id="9634f-106">Microsoft 持續運作，以確保我們雲端服務的多重租用戶架構支援企業層級安全性、 機密性、 隱私權、 完整性和可用性標準。</span><span class="sxs-lookup"><span data-stu-id="9634f-106">Microsoft works continuously to ensure that the multi-tenant architectures of our cloud services support enterprise-level security, confidentiality, privacy, integrity, and availability standards.</span></span>

<span data-ttu-id="9634f-107">根據重大投資和從[高可信度電腦運算](https://www.microsoft.com/en-us/twc/default.aspx)」 和 「[安全性開發生命週期](http://www.microsoft.com/security/sdl/default.aspx)中收集到的體驗，Microsoft 雲端服務的設計與所有租用戶是所有潛在惡意假設其他租用戶，以及我們已實作的安全性措施，以避免影響的安全性或服務，另一個租用戶，或存取另一個租用戶的內容從一個租用戶的動作。</span><span class="sxs-lookup"><span data-stu-id="9634f-107">Based upon the significant investments and experience gathered from [Trustworthy Computing](https://www.microsoft.com/en-us/twc/default.aspx) and the [Security Development Lifecycle](http://www.microsoft.com/security/sdl/default.aspx), Microsoft cloud services were designed with the assumption that all tenants are potentially hostile to all other tenants, and we have implemented security measures to prevent the actions of one tenant from affecting the security or service of another tenant, or accessing the content of another tenant.</span></span>

<span data-ttu-id="9634f-108">維護多承租人環境中的租用戶隔離的兩個主要目標如下：</span><span class="sxs-lookup"><span data-stu-id="9634f-108">The two primary goals of maintaining tenant isolation in a multi-tenant environment are:</span></span>
1.  <span data-ttu-id="9634f-109">防止外的洩或未經授權的存取，客戶內容給承租人;和</span><span class="sxs-lookup"><span data-stu-id="9634f-109">Preventing leakage of, or unauthorized access to, customer content across tenants; and</span></span>
2.  <span data-ttu-id="9634f-110">防止一個租用戶的動作有不良影響的服務，另一個租用戶</span><span class="sxs-lookup"><span data-stu-id="9634f-110">Preventing the actions of one tenant from adversely affecting the service for another tenant</span></span>

<span data-ttu-id="9634f-111">整個 Office 365 來防止從危及系統的 Office 365 服務或應用程式或未經授權存取的其他租用戶或本身，包括 Office 365 系統資訊的客戶，已經實作多個表單的保護：</span><span class="sxs-lookup"><span data-stu-id="9634f-111">Multiple forms of protection have been implemented throughout Office 365 to prevent customers from compromising Office 365 services or applications or gaining unauthorized access to the information of other tenants or the Office 365 system itself, including:</span></span>
- <span data-ttu-id="9634f-112">Office 365 服務的每個租用戶中的客戶內容的邏輯隔離，達成透過 Azure Active Directory 授權和角色型存取控制。</span><span class="sxs-lookup"><span data-stu-id="9634f-112">Logical isolation of customer content within each tenant for Office 365 services is achieved through Azure Active Directory authorization and role-based access control.</span></span>
- <span data-ttu-id="9634f-113">SharePoint Online 提供資料隔離機制儲存層級。</span><span class="sxs-lookup"><span data-stu-id="9634f-113">SharePoint Online provides data isolation mechanisms at the storage level.</span></span>
- <span data-ttu-id="9634f-114">Microsoft 會使用嚴密的實體安全性、 背景檢測和多層次的加密策略來保護的機密安全和完整性的客戶內容。</span><span class="sxs-lookup"><span data-stu-id="9634f-114">Microsoft uses rigorous physical security, background screening, and a multi-layered encryption strategy to protect the confidentiality and integrity of customer content.</span></span> <span data-ttu-id="9634f-115">所有 Office 365 資料中心都有生物識別的存取控制，以最要求棕櫚列印到實體存取。</span><span class="sxs-lookup"><span data-stu-id="9634f-115">All Office 365 datacenters have biometric access controls, with most requiring palm prints to gain physical access.</span></span> <span data-ttu-id="9634f-116">此外，所有美國 Microsoft 員工都順利完成所需的標準背景檢查僱用程序的一部分。</span><span class="sxs-lookup"><span data-stu-id="9634f-116">In addition, all U.S.-based Microsoft employees are required to successfully complete a standard background check as part of the hiring process.</span></span> <span data-ttu-id="9634f-117">如需有關用於 Office 365 中的系統管理存取權的控制項的詳細資訊，請參閱 < <b0>Office 365 系統管理存取控制</b0>。</span><span class="sxs-lookup"><span data-stu-id="9634f-117">For more information on the controls used for administrative access in Office 365, see [Office 365 Administrative Access Controls](office-365-administrative-access-controls-overview.md).</span></span>
- <span data-ttu-id="9634f-118">Office 365 會使用加密靜止和傳輸，包括 BitLocker，每一檔案加密中的客戶內容的服務端技術傳輸層安全性 (TLS) 及網際網路通訊協定安全性 (IPsec)。</span><span class="sxs-lookup"><span data-stu-id="9634f-118">Office 365 uses service-side technologies that encrypt customer content at rest and in transit, including BitLocker, per-file encryption, Transport Layer Security (TLS) and Internet Protocol Security (IPsec).</span></span> <span data-ttu-id="9634f-119">如需 Office 365 中加密的特定詳細資訊，請參閱 <<c0>在 Office 365 中的資料加密技術。</span><span class="sxs-lookup"><span data-stu-id="9634f-119">For specific details about encryption in Office 365, see [Data Encryption Technologies in Office 365](office-365-encryption-in-the-microsoft-cloud-overview.md).</span></span>

<span data-ttu-id="9634f-120">在一起，以上所列的保護提供強大的邏輯隔離控制項，可提供威脅防護和補救等於所提供的單獨的實體隔離。</span><span class="sxs-lookup"><span data-stu-id="9634f-120">Together, the above-listed protections provide robust logical isolation controls that provide threat protection and mitigation equivalent to that provided by physical isolation alone.</span></span>

## <a name="related-links"></a><span data-ttu-id="9634f-121">相關連結</span><span class="sxs-lookup"><span data-stu-id="9634f-121">Related Links</span></span>
- [<span data-ttu-id="9634f-122">Azure Active Directory 中的隔離與存取控制</span><span class="sxs-lookup"><span data-stu-id="9634f-122">Isolation and Access Control in Azure Active Directory</span></span>](office-365-isolation-in-azure-active-directory.md)
- [<span data-ttu-id="9634f-123">Office Graph 與 Delve 中的租用戶隔離</span><span class="sxs-lookup"><span data-stu-id="9634f-123">Tenant Isolation in the Office Graph and Delve</span></span>](office-365-isolation-in-graph-and-delve.md)
- [<span data-ttu-id="9634f-124">Office 365 搜尋中的租用戶隔離</span><span class="sxs-lookup"><span data-stu-id="9634f-124">Tenant Isolation in Office 365 Search</span></span>](office-365-isolation-in-office-365-search.md)
- [<span data-ttu-id="9634f-125">Office 365 影片中的租用戶隔離</span><span class="sxs-lookup"><span data-stu-id="9634f-125">Tenant Isolation in Office 365 Video</span></span>](office-365-isolation-in-office-365-video.md)
- [<span data-ttu-id="9634f-126">資源限制</span><span class="sxs-lookup"><span data-stu-id="9634f-126">Resource Limits</span></span>](office-365-resource-limits.md)
- [<span data-ttu-id="9634f-127">監視及測試租用戶界限</span><span class="sxs-lookup"><span data-stu-id="9634f-127">Monitoring and Testing Tenant Boundaries</span></span>](office-365-monitoring-and-testing.md)
- [<span data-ttu-id="9634f-128">Office 365 中的隔離與存取控制</span><span class="sxs-lookup"><span data-stu-id="9634f-128">Isolation and Access Control in Office 365</span></span>](office-365-isolation-in-office-365.md)