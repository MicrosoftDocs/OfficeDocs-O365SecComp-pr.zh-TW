---
title: Office 365 隔離控制措施
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 摘要： 在 Office 365 中的隔離控制項的說明。
ms.openlocfilehash: a6ff2b11ea02334a6c47317cbb77b8d47207b552
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217313"
---
# <a name="office-365-isolation-controls"></a><span data-ttu-id="cfc90-103">Office 365 隔離控制措施</span><span class="sxs-lookup"><span data-stu-id="cfc90-103">Office 365 Isolation Controls</span></span> 

<span data-ttu-id="cfc90-p101">若要確認 Office 365 的多重租用戶架構支援企業層級安全性、 機密性、 隱私權、 完整性及可用性[標準](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons)，以及本機和以國際標準的 Microsoft 持續運作。指定的範圍及提供的 Microsoft 服務範圍，是說過很難且非經濟如果大幅人工互動需要管理 Office 365。Office 365 服務提供透過多個全域分散式資料中心、 高度自動化的方式，其中的資料中心操作極少需要人工觸控且甚至是較少的作業需要客戶內容的存取權。我們人員支援這些服務及使用自動化的工具資料中心及高度安全的遠端存取。部分的詳細資訊如何大規模服務被 21vianet Office 365，請參閱[幕後作業查看適用於 IT 專業人員的 Office 365 後置](https://channel9.msdn.com/Events/SharePoint-Conference/2014/SPC202)中。</span><span class="sxs-lookup"><span data-stu-id="cfc90-p101">Microsoft continuously works to ensure that the multi-tenant architecture of Office 365 supports enterprise-level security, confidentiality, privacy, integrity, and availability [standards](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons), as well as local and international standards. Given the scale and the scope of services provided by Microsoft, it would be difficult and non-economical to manage Office 365 if significant human interaction were required. Office 365 services are provided through multiple globally-distributed datacenters, in a highly-automated fashion, where extremely few datacenter operations require a human touch, and even fewer operations require access to customer content. Our staff supports these services and datacenters using automated tools and highly secure remote access. For some of the details about how large-scale services are operated in Office 365, see [a behind the scenes look at Office 365 for IT Pros](https://channel9.msdn.com/Events/SharePoint-Conference/2014/SPC202).</span></span>

<span data-ttu-id="cfc90-p102">Office 365 被組成多個服務，提供重要的商務功能及參與整個 Office 365 經驗。每個這些服務的設計目的是自給自足與彼此互相整合。Office 365 設計與[本篇架構](https://msdn.microsoft.com/library/aa480021.aspx)，這會定義為設計及開發軟體的互通性服務提供定義完善的商務功能和[操作的安全性表單中的原則保證](http://www.microsoft.com/download/details.aspx?id=40872)，同時知識 framework 獲得透過各種不同的是 Microsoft，包括 Microsoft[安全性開發週期](https://www.microsoft.com/sdl/default.aspx)、 [Microsoft 安全性回應中心](https://technet.microsoft.com/library/dn440717.aspx)、 及深層專用的功能cybersecurity 威脅橫向感知。</span><span class="sxs-lookup"><span data-stu-id="cfc90-p102">Office 365 is composed of multiple services that provide important business functionality and contribute to the entire Office 365 experience. Each of these services is designed to be self-contained and to integrate with one another. Office 365 is designed with the principles of a [Service-Oriented Architecture](https://msdn.microsoft.com/library/aa480021.aspx), which is defined as designing and developing software in the form of interoperable services providing well-defined business functionality, and [Operational Security Assurance](http://www.microsoft.com/download/details.aspx?id=40872), a framework that incorporates the knowledge gained through a variety of capabilities that are unique to Microsoft, including the Microsoft [Security Development Lifecycle](https://www.microsoft.com/sdl/default.aspx), the [Microsoft Security Response Center](https://technet.microsoft.com/library/dn440717.aspx), and deep awareness of the cybersecurity threat landscape.</span></span>

<span data-ttu-id="cfc90-p103">Office 365 服務彼此相互溝通，但他們正在設計和實作可以部署和操作為自發式服務，彼此獨立。Microsoft 區分責任及區域的 Office 365 以減少未經授權或無意修改的機會責任或誤用的組織資產。Office 365 小組已定義的角色全方位的角色型存取控制機制的一部分。</span><span class="sxs-lookup"><span data-stu-id="cfc90-p103">Office 365 services interoperate with each other, but they are designed and implemented so that they can be deployed and operated as autonomous services, independent of each other. Microsoft segregates duties and areas of responsibility for Office 365 to reduce opportunities for unauthorized or unintentional modification or misuse of the organization's assets. Office 365 teams have defined roles as part of a comprehensive role-based access control mechanism.</span></span>

## <a name="customer-content-isolation"></a><span data-ttu-id="cfc90-115">客戶內容隔離</span><span class="sxs-lookup"><span data-stu-id="cfc90-115">Customer Content Isolation</span></span>
<span data-ttu-id="cfc90-p104">屬於租用戶的所有客戶內容都是隔離從其他租用戶和管理 Office 365 中使用的作業與系統資料。Office 任何的 365 Office 365 服務或應用程式或任何取得未經授權存取承租人或 Office 365 系統本身的資訊洩露風險降至最低整個已經實作多個表單的保護。如需 Microsoft 如何實作邏輯隔離的 Office 365 租用戶資料，請參閱 ＜[在 Office 365 租用戶隔離](office-365-tenant-isolation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="cfc90-p104">All customer content belonging to a tenant is isolated from other tenants and from the operations and systems data used in the management of Office 365. Multiple forms of protection have been implemented throughout Office 365 to minimize the risk of compromise of any Office 365 service or application, or any gaining of unauthorized access to the information of tenants or the Office 365 system itself. For information about how Microsoft implements logical isolation of tenant data within Office 365, see [Tenant Isolation in Office 365](office-365-tenant-isolation-overview.md).</span></span>
