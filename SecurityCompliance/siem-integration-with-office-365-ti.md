---
title: Office 365 進階威脅防護的 SIEM 整合
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.collection:
- M365-security-compliance
description: 將貴組織的 SIEM 伺服器整合與 Office 365 進階威脅防護和 Office 365 活動管理 API 中的相關的威脅事件。
ms.openlocfilehash: 6c0468f8f3fdd25082bff8a3008d2abf00ed9d4d
ms.sourcegitcommit: 74ad22a5c6c3c9d9324f0f97070909e323a4e9cf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/11/2019
ms.locfileid: "30523987"
---
# <a name="siem-integration-with-office-365-advanced-threat-protection"></a><span data-ttu-id="11dea-103">Office 365 進階威脅防護的 SIEM 整合</span><span class="sxs-lookup"><span data-stu-id="11dea-103">SIEM integration with Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="11dea-104">如果您的組織使用的安全性事件和事件管理 (SIEM) 伺服器，您可以使用 SIEM 伺服器整合 Office 365 進階威脅防護。</span><span class="sxs-lookup"><span data-stu-id="11dea-104">If your organization is using a security incident and event management (SIEM) server, you can integrate Office 365 Advanced Threat Protection with your SIEM server.</span></span> <span data-ttu-id="11dea-105">SIEM 整合可讓您檢視資訊，例如惡意程式碼或在 SIEM 伺服器報表中 Office 365 進階防護，所偵測到的釣魚程式。</span><span class="sxs-lookup"><span data-stu-id="11dea-105">SIEM integration enables you to view information, such as malware or phish detected by Office 365 Advanced Protection, in your SIEM server reports.</span></span> <span data-ttu-id="11dea-106">若要設定 SIEM 整合，您可以使用[Office 365 活動管理 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)。</span><span class="sxs-lookup"><span data-stu-id="11dea-106">To set up SIEM integration, you use the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="11dea-107">Office 365 活動管理 API 從貴組織的 Office 365 和 Azure Active Directory 活動記錄檔擷取使用者、 系統、 系統及原則動作和事件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="11dea-107">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Office 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="11dea-108">[Office 365 進階威脅防護結構描述](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-intelligence-schema)搭配進階威脅防護，因此如果您的組織有 Office 365 進階威脅防護方案 1 或方案 2 或 Office 365 E5，您仍然可以使用該相同的 API 您 SIEM 伺服器整合。</span><span class="sxs-lookup"><span data-stu-id="11dea-108">The [Office 365 Advanced Threat Protection schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-intelligence-schema) works with Advanced Threat Protection, so if your organization has the Office 365 Advanced Threat Protection Plan 1 or Plan 2 or Office 365 E5, you can still use that same API for your SIEM server integration.</span></span> 

<span data-ttu-id="11dea-109">SIEM 伺服器或其他相似 system 應輪詢 access 偵測事件**audit.general**工作負載。</span><span class="sxs-lookup"><span data-stu-id="11dea-109">The SIEM server or other similar system should poll the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="11dea-110">若要深入了解，請參閱[開始使用 Office 365 管理 Api](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)。</span><span class="sxs-lookup"><span data-stu-id="11dea-110">To learn more see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="11dea-111">您必須是 Office 365 全域系統管理員或具有安全性系統管理員角色指派的安全性 & 合規性中心以設定 Office 365 進階威脅防護的 SIEM 整合。</span><span class="sxs-lookup"><span data-stu-id="11dea-111">You must be an Office 365 global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Office 365 Advanced Threat Protection.</span></span><br/><span data-ttu-id="11dea-112">稽核記錄必須開啟適用於 Office 365 環境。</span><span class="sxs-lookup"><span data-stu-id="11dea-112">Audit logging must be turned on for your Office 365 environment.</span></span> <span data-ttu-id="11dea-113">若要取得此問題的協助，請參閱[開啟 Office 365 稽核記錄搜尋的開啟或關閉](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="11dea-113">To get help with this, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="11dea-114">相關主題</span><span class="sxs-lookup"><span data-stu-id="11dea-114">Related topics</span></span>

[<span data-ttu-id="11dea-115">Office 365 威脅調查及回應</span><span class="sxs-lookup"><span data-stu-id="11dea-115">Office 365 Threat Investigation and Response</span></span>](office-365-ti.md)

[<span data-ttu-id="11dea-116">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="11dea-116">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

[<span data-ttu-id="11dea-117">智慧型報表和深入了解 Office 365 安全性&amp;合規性中心</span><span class="sxs-lookup"><span data-stu-id="11dea-117">Smart reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="11dea-118">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="11dea-118">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  