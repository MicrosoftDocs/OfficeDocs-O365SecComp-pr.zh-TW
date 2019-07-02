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
description: Office 365 管理活動 API 的簡短摘要。
ms.openlocfilehash: 759a8c7035c02ddf17d18080629a715a5525c4d6
ms.sourcegitcommit: aa60a6cdf83c67576e858668d1182cd4fffeb5e0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2019
ms.locfileid: "33622503"
---
# <a name="office-365-management-activity-api"></a><span data-ttu-id="5dcde-103">Office 365 管理活動 API</span><span class="sxs-lookup"><span data-stu-id="5dcde-103">Office 365 Management Activity API</span></span>

<span data-ttu-id="5dcde-104">Microsoft 提供 reporting services, 您可以用來取得有關 Office 365 租使用者的匯總交易資訊。</span><span class="sxs-lookup"><span data-stu-id="5dcde-104">Microsoft provides reporting services you can use to obtain aggregated transactional information about your Office 365 tenant.</span></span> <span data-ttu-id="5dcde-105">[Office 365 管理活動 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)使用行業標準 RESTful 設計和 OAuth v2 進行驗證。</span><span class="sxs-lookup"><span data-stu-id="5dcde-105">The [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview) uses an industry-standard RESTful design and OAuth v2 for authentication.</span></span> <span data-ttu-id="5dcde-106">這可讓您輕鬆開始體驗如何檢索資料, 並將資料 ingesting 至視覺化檢視和應用程式。</span><span class="sxs-lookup"><span data-stu-id="5dcde-106">This makes it easy to start experimenting with retrieving data and ingesting it into visualization tools and applications.</span></span> <span data-ttu-id="5dcde-107">API 提供 Office 365 中使用者、系統管理員、作業及安全性活動相關資訊的資料摘要。</span><span class="sxs-lookup"><span data-stu-id="5dcde-107">The API provides a data feed with information about user, administrator, operations, and security activity in Office 365.</span></span> <span data-ttu-id="5dcde-108">資料可出於法規目的而保留, 或與內部部署基礎結構或其他來源的記錄資料採購相結合。</span><span class="sxs-lookup"><span data-stu-id="5dcde-108">The data can be kept for regulatory purposes, or combined with log data procured from an on-premises infrastructure or other sources.</span></span> <span data-ttu-id="5dcde-109">這可協助為整個企業的作業、安全性及合規性建立監視解決方案。</span><span class="sxs-lookup"><span data-stu-id="5dcde-109">This helps build a monitoring solution for operations, security, and compliance across the enterprise.</span></span>

<span data-ttu-id="5dcde-110">Office 365 管理活動 API 提供來自 Office 365 和 Azure Active Directory 活動記錄的各種使用者、系統管理員、系統及原則動作及事件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="5dcde-110">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Office 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="5dcde-111">API 提供一致的審核架構, 其所有服務都有10個以上的欄位。</span><span class="sxs-lookup"><span data-stu-id="5dcde-111">The API provides a consistent audit schema with over 10 fields common across all the services.</span></span> <span data-ttu-id="5dcde-112">API 可讓組織在事件之間進行簡單的連線, 並啟用資料的原因的新方法。</span><span class="sxs-lookup"><span data-stu-id="5dcde-112">The API allows organizations to make easy connections between events, and enables new ways to reason over the data.</span></span>

<span data-ttu-id="5dcde-113">許多獨立軟體廠商 (Isv) 與 Microsoft 合作, 並已建立以 API 為基礎的解決方案。</span><span class="sxs-lookup"><span data-stu-id="5dcde-113">Dozens of Independent Software Vendors (ISVs) partnered with Microsoft and have built solutions based on the API.</span></span> <span data-ttu-id="5dcde-114">某些解決方案主要著重于 Office 365 資料和其他雲端提供者和內部部署系統的來來源資料, 以建立作業、安全性及規範相關活動的統一視圖。</span><span class="sxs-lookup"><span data-stu-id="5dcde-114">Some solutions focus solely on Office 365 data and others source data from multiple cloud providers and on-premises systems to create a unified view of operations, security, and compliance-related activity.</span></span> 

<span data-ttu-id="5dcde-115">如需詳細資訊, 請參閱[Office 365 管理活動 API 參考](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)。</span><span class="sxs-lookup"><span data-stu-id="5dcde-115">For more information, see the [Office 365 Management Activity API reference](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>
