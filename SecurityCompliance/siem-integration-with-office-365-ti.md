---
title: 與 Office 365 威脅智慧及進階威脅保護 SIEM 整合
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
description: 整合您的組織 SIEM server 與 Office 365 威脅智慧及進階威脅保護的 Office 365 活動管理 api。
ms.openlocfilehash: cecfb3910520ddf535c50bbe4bccbf200ae8e121
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30212733"
---
# <a name="siem-integration-with-office-365-threat-intelligence-and-advanced-threat-protection"></a><span data-ttu-id="ac534-103">與 Office 365 威脅智慧及進階威脅保護 SIEM 整合</span><span class="sxs-lookup"><span data-stu-id="ac534-103">SIEM integration with Office 365 Threat Intelligence and Advanced Threat Protection</span></span>

<span data-ttu-id="ac534-p101">如果貴組織要使用安全性事件及事件管理 (SIEM) 伺服器，您可以使用 SIEM server 整合 Office 365 威脅智慧及進階威脅保護。SIEM 整合可讓您檢視的資訊，例如偵測到的 Office 365 進階保護和威脅智慧您 SIEM server 報告中的惡意程式碼。若要設定 SIEM 整合，您可以使用[Office 365 活動管理 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)。</span><span class="sxs-lookup"><span data-stu-id="ac534-p101">If your organization is using a security incident and event management (SIEM) server, you can integrate Office 365 Threat Intelligence and Advanced Threat Protection with your SIEM server. SIEM integration enables you to view information, such as malware detected by Office 365 Advanced Protection and Threat Intelligence, in your SIEM server reports. To set up SIEM integration, you use the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="ac534-p102">Office 365 活動管理 API 從您組織的 Office 365 和 Azure Active Directory 活動記錄檔擷取使用者、 管理、 系統及原則動作和事件的相關資訊。[Office 365 進階威脅保護和威脅智慧結構描述](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-intelligence-schema)搭配威脅智慧及/或進階威脅防護，因此如果您的組織有但不是威脅智慧 （反之亦然），進階威脅保護，您可以仍然使用該相同的 API 來進行 SIEM server 的整合。</span><span class="sxs-lookup"><span data-stu-id="ac534-p102">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Office 365 and Azure Active Directory activity logs. The [Office 365 Advanced Threat Protection and Threat Intelligence schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-intelligence-schema) works with Threat Intelligence and/or Advanced Threat Protection, so if your organization has Advanced Threat Protection but not Threat Intelligence (or vice versa), you can still use that same API for your SIEM server integration.</span></span> 

<span data-ttu-id="ac534-p103">SIEM 伺服器或其他類似系統應輪詢 access 偵測事件**audit.general**工作量。若要了解，請參閱[開始使用 Office 365 管理 api （英文）](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)。</span><span class="sxs-lookup"><span data-stu-id="ac534-p103">The SIEM server or other similar system should poll the **audit.general** workload to access detection events. To learn more see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="ac534-111">您必須是 Office 365 全域管理員或已指派給安全性 & 規範中心來設定與 Office 365 進階威脅保護 SIEM 整合安全性管理員角色。</span><span class="sxs-lookup"><span data-stu-id="ac534-111">You must be an Office 365 global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Office 365 Advanced Threat Protection.</span></span><br/><span data-ttu-id="ac534-p104">稽核記錄必須針對 Office 365 環境開啟。若要取得與此說明，請參閱[開啟 Office 365 稽核記錄搜尋開啟或關閉](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="ac534-p104">Audit logging must be turned on for your Office 365 environment. To get help with this, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ac534-114">相關主題</span><span class="sxs-lookup"><span data-stu-id="ac534-114">Related topics</span></span>

[<span data-ttu-id="ac534-115">Office 365 威脅情報</span><span class="sxs-lookup"><span data-stu-id="ac534-115">Office 365 Threat Intelligence</span></span>](office-365-ti.md)

[<span data-ttu-id="ac534-116">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="ac534-116">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

[<span data-ttu-id="ac534-117">智慧報表和 Office 365 安全性前瞻&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="ac534-117">Smart reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="ac534-118">Office 365 安全性權限&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="ac534-118">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  

