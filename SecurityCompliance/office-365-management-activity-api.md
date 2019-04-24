---
title: Office 365 管理活動 API
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
- M365-analytics
description: 關於 Office 365 管理活動 API 簡短摘要。
ms.openlocfilehash: 3405eaac000111fb5d5f054edcbe6816aa9af9e7
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262555"
---
# <a name="office-365-management-activity-api"></a><span data-ttu-id="b77c4-103">Office 365 管理活動 API</span><span class="sxs-lookup"><span data-stu-id="b77c4-103">Office 365 Management Activity API</span></span>
<span data-ttu-id="b77c4-104">Microsoft 提供報告服務可讓系統管理員，取得有關其 Office 365 租用戶的彙總交易資訊。</span><span class="sxs-lookup"><span data-stu-id="b77c4-104">Microsoft provides reporting services that enable administrators to obtain aggregated transactional information about their Office 365 tenant.</span></span> <span data-ttu-id="b77c4-105">[Office 365 管理活動 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)會使用業界標準 RESTful 設計和 OAuth v2 進行驗證，讓您輕鬆地進行實驗以開始擷取資料並 ingesting 到視覺效果工具和應用程式。</span><span class="sxs-lookup"><span data-stu-id="b77c4-105">The [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview) uses an industry-standard RESTful design and OAuth v2 for authentication, which makes it easy to start experimenting with retrieving data and ingesting it into visualization tools and applications.</span></span> <span data-ttu-id="b77c4-106">此 API 會提供資料摘要，包含在 Office 365 中的使用者、 系統管理員、 作業及安全性活動的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="b77c4-106">The API provides a data feed that includes information about user, administrator, operations, and security activity in Office 365.</span></span> <span data-ttu-id="b77c4-107">資料可以基於法規，保留或結合採購從內部部署基礎結構或其他來源]，以建立整個企業的作業、 安全性和規範監視解決方案的記錄資料。</span><span class="sxs-lookup"><span data-stu-id="b77c4-107">The data can be kept for regulatory purposes, or combined with log data procured from an on-premises infrastructure or other sources to build a monitoring solution for operations, security, and compliance across the enterprise.</span></span>

<span data-ttu-id="b77c4-108">Office 365 管理活動 API 從 Office 365 和 Azure Active Directory 活動記錄提供各種使用者、 系統、 系統及原則動作和事件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="b77c4-108">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Office 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="b77c4-109">API 提供一致的稽核結構描述具有超過 10 個共通的所有服務的欄位。</span><span class="sxs-lookup"><span data-stu-id="b77c4-109">The API provides a consistent audit schema with over 10 fields that are in common across all the services.</span></span> <span data-ttu-id="b77c4-110">這可讓組織進行輕鬆事件，之間的連線，並可透過資料讓原因的新方法。</span><span class="sxs-lookup"><span data-stu-id="b77c4-110">This allows organizations to make easy connections between events, and it enables new ways to reason over the data.</span></span> <span data-ttu-id="b77c4-111">數十個獨立軟體廠商 (Isv) 已建立與 Microsoft 合作關係，並建置 API 為基礎的解決方案。</span><span class="sxs-lookup"><span data-stu-id="b77c4-111">Dozens of Independent Software Vendors (ISVs) have partnered with Microsoft and built solutions based on the API.</span></span> <span data-ttu-id="b77c4-112">部分解決方案被著重於察覺 Office 365 資料，雖然其他人提供內嵌自多個雲端提供者與內部部署系統，來建立所有作業、 安全性及規範相關活動的整合的檢視資料的能力。</span><span class="sxs-lookup"><span data-stu-id="b77c4-112">Some solutions are focused solely on Office 365 data, while others provide the ability to ingest data from multiple cloud providers and on-premises systems to create a unified view of all operations, security, and compliance-related activity.</span></span> <span data-ttu-id="b77c4-113">如需詳細資訊，請參閱[Office 365 管理活動 API 參考資料](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)。</span><span class="sxs-lookup"><span data-stu-id="b77c4-113">For more information, see the [Office 365 Management Activity API reference](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>
