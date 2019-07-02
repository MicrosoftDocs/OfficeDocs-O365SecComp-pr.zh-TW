---
title: Office 365 隔離控制
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
description: '摘要: Office 365 內隔離控制項的說明。'
ms.openlocfilehash: 6f5980ae25b412cbbccc20ec3b5726b5a4ceed86
ms.sourcegitcommit: 7b5e4a7a51f3cdd741deb77a2d60a18e2316618d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/01/2019
ms.locfileid: "33520683"
---
# <a name="office-365-isolation-controls"></a><span data-ttu-id="22441-103">Office 365 隔離控制</span><span class="sxs-lookup"><span data-stu-id="22441-103">Office 365 Isolation Controls</span></span> 

<span data-ttu-id="22441-104">Microsoft 持續運作, 以確保 Office 365 的多租使用者架構支援企業級的安全性、機密性、隱私權、完整性、當地、國際和可用性[標準](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons)。</span><span class="sxs-lookup"><span data-stu-id="22441-104">Microsoft continuously works to ensure that the multi-tenant architecture of Office 365 supports enterprise-level security, confidentiality, privacy, integrity, local, international, and availability [standards](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons).</span></span> <span data-ttu-id="22441-105">Microsoft 所提供之服務的規模和範圍, 可讓您使用重要的人工互動來管理 Office 365。</span><span class="sxs-lookup"><span data-stu-id="22441-105">The scale and the scope of services provided by Microsoft make it difficult and non-economical to manage Office 365 with significant human interaction.</span></span> <span data-ttu-id="22441-106">Office 365 服務是透過多個全域分散式資料中心提供, 每個都以高自動化的方式進行, 且需要人工觸控或任何存取客戶內容。</span><span class="sxs-lookup"><span data-stu-id="22441-106">Office 365 services are provided through multiple globally distributed data centers, each highly automated with few operations requiring a human touch or any access to customer content.</span></span> <span data-ttu-id="22441-107">我們的員工會使用自動化的工具和高度安全的遠端存取, 來支援這些服務和資料中心。</span><span class="sxs-lookup"><span data-stu-id="22441-107">Our staff supports these services and data centers using automated tools and highly secure remote access.</span></span> <span data-ttu-id="22441-108">如需有關如何在 Office 365 中運作大量服務的詳細資訊, 請參閱[office 365 FOR IT 專業人員的主題](https://channel9.msdn.com/Events/SharePoint-Conference/2014/SPC202)。</span><span class="sxs-lookup"><span data-stu-id="22441-108">For some of the details about how large-scale services are operated in Office 365, see [a behind the scenes look at Office 365 for IT Pros](https://channel9.msdn.com/Events/SharePoint-Conference/2014/SPC202).</span></span>

<span data-ttu-id="22441-109">Office 365 是由多種服務所組成, 可提供重要的商務功能, 並參與整個 Office 365 的體驗。</span><span class="sxs-lookup"><span data-stu-id="22441-109">Office 365 is composed of multiple services that provide important business functionality and contribute to the entire Office 365 experience.</span></span> <span data-ttu-id="22441-110">這些服務都是獨立的, 且設計為彼此整合。</span><span class="sxs-lookup"><span data-stu-id="22441-110">Each of these services is self-contained and designed to integrate with one another.</span></span>

<span data-ttu-id="22441-111">Office 365 的設計具有下列原則:</span><span class="sxs-lookup"><span data-stu-id="22441-111">Office 365 is designed with the following principles:</span></span>

 - <span data-ttu-id="22441-112">以**[服務為導向的架構](https://msdn.microsoft.com/library/aa480021.aspx):** 以可交互操作服務的形式來設計及開發軟體, 以提供良好定義的商務功能。</span><span class="sxs-lookup"><span data-stu-id="22441-112">**[Service-Oriented Architecture](https://msdn.microsoft.com/library/aa480021.aspx):** designing and developing software in the form of interoperable services providing well-defined business functionality.</span></span>
 - <span data-ttu-id="22441-113">**[運作安全性保證](http://www.microsoft.com/download/details.aspx?id=40872):** 一種架構, 其包含透過 microsoft 獨有的各種功能所取得的知識, 包括 Microsoft[安全性開發週期](https://www.microsoft.com/sdl/default.aspx)、 [microsoft 安全性回應中心](https://technet.microsoft.com/library/dn440717.aspx), 以及深入瞭解 cybersecurity 威脅環境。</span><span class="sxs-lookup"><span data-stu-id="22441-113">**[Operational Security Assurance](http://www.microsoft.com/download/details.aspx?id=40872):** a framework that incorporates the knowledge gained through various capabilities that are unique to Microsoft, including the Microsoft [Security Development Lifecycle](https://www.microsoft.com/sdl/default.aspx), the [Microsoft Security Response Center](https://technet.microsoft.com/library/dn440717.aspx), and deep awareness of the cybersecurity threat landscape.</span></span>

<span data-ttu-id="22441-114">Office 365 服務間相互運作, 但已設計好並執行, 因此可將它們部署並運作為自治服務, 彼此無關。</span><span class="sxs-lookup"><span data-stu-id="22441-114">Office 365 services inter-operate with each other, but are designed and implemented so they can be deployed and operated as autonomous services, independent of each other.</span></span> <span data-ttu-id="22441-115">Microsoft segregates Office 365 的責任和責任領域, 以減少未經授權或無意間修改或濫用組織資產的機會。</span><span class="sxs-lookup"><span data-stu-id="22441-115">Microsoft segregates duties and areas of responsibility for Office 365 to reduce opportunities for unauthorized or unintentional modification or misuse of the organization's assets.</span></span> <span data-ttu-id="22441-116">Office 365 小組已定義角色, 作為綜合角色型存取控制機制的一部分。</span><span class="sxs-lookup"><span data-stu-id="22441-116">Office 365 teams have defined roles as part of a comprehensive role-based access control mechanism.</span></span>

## <a name="customer-content-isolation"></a><span data-ttu-id="22441-117">客戶內容隔離</span><span class="sxs-lookup"><span data-stu-id="22441-117">Customer content isolation</span></span>

<span data-ttu-id="22441-118">租使用者中的所有客戶內容都是與其他承租人, 以及 Office 365 管理中所使用的作業和系統資料隔離。</span><span class="sxs-lookup"><span data-stu-id="22441-118">All customer content in a tenant is isolated from other tenants and from operations and systems data used in the management of Office 365.</span></span> <span data-ttu-id="22441-119">在整個 Office 365 中會執行多種保護形式, 以降低受到任何 Office 365 服務或應用程式威脅的風險。</span><span class="sxs-lookup"><span data-stu-id="22441-119">Multiple forms of protection are implemented throughout Office 365 to minimize the risk of compromise of any Office 365 service or application.</span></span> <span data-ttu-id="22441-120">多種保護形式也會防止未經授權的存取租使用者或 Office 365 系統本身的資訊。</span><span class="sxs-lookup"><span data-stu-id="22441-120">Multiple forms of protection also prevent unauthorized access to the information of tenants or the Office 365 system itself.</span></span>

<span data-ttu-id="22441-121">如需 Microsoft 如何在 Office 365 中實現租使用者資料邏輯隔離的相關資訊, 請參閱[office 365 中的租使用者隔離](office-365-tenant-isolation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="22441-121">For information about how Microsoft implements logical isolation of tenant data within Office 365, see [Tenant Isolation in Office 365](office-365-tenant-isolation-overview.md).</span></span>
