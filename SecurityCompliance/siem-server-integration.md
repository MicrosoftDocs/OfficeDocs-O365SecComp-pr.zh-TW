---
title: Microsoft 365 SIEM server 整合
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.date: 10/29/2018
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- SIEM
description: 摘要： 閱讀本篇文章以取得 Microsoft 365 SIEM server 整合的概觀。
ms.openlocfilehash: 4b9b631ab27d777be610ed3b954acc7b2c3bdf50
ms.sourcegitcommit: 1c73c2f83703af0a30a5b0633db00d8e0e6b39b5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/25/2019
ms.locfileid: "30241875"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="58f33-103">SIEM server 與 Microsoft 365 服務及應用程式的整合</span><span class="sxs-lookup"><span data-stu-id="58f33-103">SIEM server integration with Microsoft 365 services and applications</span></span>

## <a name="overview"></a><span data-ttu-id="58f33-104">概觀</span><span class="sxs-lookup"><span data-stu-id="58f33-104">Overview</span></span>

<span data-ttu-id="58f33-p101">如果您的組織使用的安全性資訊及事件管理 (SIEM) 的伺服器，或如果打算推出取得 SIEM 伺服器，您可能會想要知道如何會將包含 Office 365 企業版的 Microsoft 365 與整合。您是否需要 SIEM 伺服器取決於許多因素，例如貴組織的安全性需求。Microsoft 365 外部提供各種安全性功能 ；但是，如果組織有內容和應用程式在內部部署和雲端 （如所示的混合式雲端部署的大小寫） 中，您可能會考慮新增額外的保護 SIEM 伺服器。或者，如果您的組織必須符合的特別嚴苛安全性需求，您可能會考慮將 SIEM 伺服器新增至您的環境。</span><span class="sxs-lookup"><span data-stu-id="58f33-p101">If your organization is using a Security Information and Event Management (SIEM) server, or if you are planning to get a SIEM server soon, you might be wondering how that'll integrate with your Microsoft 365, including Office 365 Enterprise. Whether you need a SIEM server depends on many factors, such as your organization's security requirements. Microsoft 365 offers a variety of security features; however, if your organization has content and applications on premises and in the cloud (as in the case of a hybrid cloud deployment), you might consider adding a SIEM server for extra protection. Or, if your organization has particularly stringent security requirements you must meet, you might consider adding a SIEM server to your environment.</span></span>

## <a name="siem-server-integration-microsoft-365"></a><span data-ttu-id="58f33-109">SIEM 伺服器整合 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="58f33-109">SIEM server integration Microsoft 365</span></span>

<span data-ttu-id="58f33-p102">SIEM 伺服器可以接收資料從各種不同的 Microsoft 365 服務及應用程式。下表列出數個 Microsoft 365 服務及應用程式以及 SIEM server 的輸入和位置移至 [深入了解 SIEM 伺服器整合。</span><span class="sxs-lookup"><span data-stu-id="58f33-p102">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications. The following table lists several Microsoft 365 services and applications along with SIEM server inputs and where to go to learn more about SIEM server integration.</span></span> 

| <span data-ttu-id="58f33-112">Microsoft 365 Service 或應用程式</span><span class="sxs-lookup"><span data-stu-id="58f33-112">Microsoft 365 Service or Application</span></span> | <span data-ttu-id="58f33-113">SIEM 伺服器輸入</span><span class="sxs-lookup"><span data-stu-id="58f33-113">SIEM server inputs</span></span> | <span data-ttu-id="58f33-114">若要深入了解的資源</span><span class="sxs-lookup"><span data-stu-id="58f33-114">Resources to learn more</span></span> |
| --- | --- | --- |
| [<span data-ttu-id="58f33-115">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="58f33-115">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md) <br/>   <span data-ttu-id="58f33-116">或</span><span class="sxs-lookup"><span data-stu-id="58f33-116">or</span></span>   <br/>[<span data-ttu-id="58f33-117">Office 365 威脅情報</span><span class="sxs-lookup"><span data-stu-id="58f33-117">Office 365 Threat Intelligence</span></span>](office-365-ti.md) | <span data-ttu-id="58f33-118">稽核記錄</span><span class="sxs-lookup"><span data-stu-id="58f33-118">Audit logs</span></span> | [<span data-ttu-id="58f33-119">與 Office 365 威脅智慧及進階威脅保護 SIEM 整合</span><span class="sxs-lookup"><span data-stu-id="58f33-119">SIEM integration with Office 365 Threat Intelligence and Advanced Threat Protection</span></span>](siem-integration-with-office-365-ti.md) |
| [<span data-ttu-id="58f33-120">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="58f33-120">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | <span data-ttu-id="58f33-121">記錄檔的整合</span><span class="sxs-lookup"><span data-stu-id="58f33-121">Log integration</span></span> | [<span data-ttu-id="58f33-122">Microsoft 雲端應用程式安全性 SIEM 整合</span><span class="sxs-lookup"><span data-stu-id="58f33-122">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem) |
| [<span data-ttu-id="58f33-123">Office 365 雲端 App 安全性</span><span class="sxs-lookup"><span data-stu-id="58f33-123">Office 365 Cloud App Security</span></span>](office-365-cas-overview.md) | <span data-ttu-id="58f33-124">記錄檔的整合</span><span class="sxs-lookup"><span data-stu-id="58f33-124">Log integration</span></span> | [<span data-ttu-id="58f33-125">將 SIEM 伺服器與 Office 365 雲端 App 安全性整合</span><span class="sxs-lookup"><span data-stu-id="58f33-125">Integrate your SIEM server with Office 365 Cloud App Security</span></span>](integrate-your-siem-server-with-office-365-cas.md) |
| [<span data-ttu-id="58f33-126">Windows Defender 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="58f33-126">Windows Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/) | <span data-ttu-id="58f33-127">記錄檔的整合</span><span class="sxs-lookup"><span data-stu-id="58f33-127">Log integration</span></span> | [<span data-ttu-id="58f33-128">提取提醒 SIEM 工具</span><span class="sxs-lookup"><span data-stu-id="58f33-128">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-siem-windows-defender-advanced-threat-protection) |
| <span data-ttu-id="58f33-129">[Azure 安全性中心](https://docs.microsoft.com/azure/security-center/security-center-intro)（threat 保護和威脅偵測）</span><span class="sxs-lookup"><span data-stu-id="58f33-129">[Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-intro) (Threat Protection and Threat Detection)</span></span> | <span data-ttu-id="58f33-130">警示</span><span class="sxs-lookup"><span data-stu-id="58f33-130">Alerts</span></span> | [<span data-ttu-id="58f33-131">Azure 安全性資料匯出至 SIEM-管線組態-預覽</span><span class="sxs-lookup"><span data-stu-id="58f33-131">Azure Security data export to SIEM - Pipeline Configuration - Preview</span></span>](https://docs.microsoft.com/azure/security-center/security-center-export-data-to-siem) |
| [<span data-ttu-id="58f33-132">Azure Active Directory 識別保護</span><span class="sxs-lookup"><span data-stu-id="58f33-132">Azure Active Directory Identity Protection</span></span>](https://docs.microsoft.com/azure/active-directory/identity-protection/overview) | <span data-ttu-id="58f33-133">稽核記錄</span><span class="sxs-lookup"><span data-stu-id="58f33-133">Audit logs</span></span> | [<span data-ttu-id="58f33-134">整合 Azure Active Directory 稽核記錄</span><span class="sxs-lookup"><span data-stu-id="58f33-134">Integrate Azure Active Directory audit logs</span></span>](https://docs.microsoft.com/azure/security/security-azure-log-integration-ad) |
| [<span data-ttu-id="58f33-135">Azure 進階的威脅分析</span><span class="sxs-lookup"><span data-stu-id="58f33-135">Azure Advanced Threat Analytics</span></span>](https://docs.microsoft.com/azure/security/azure-threat-detection) | <span data-ttu-id="58f33-136">記錄檔的整合</span><span class="sxs-lookup"><span data-stu-id="58f33-136">Log integration</span></span> | [<span data-ttu-id="58f33-137">ATA SIEM 記錄參考 （英文)</span><span class="sxs-lookup"><span data-stu-id="58f33-137">ATA SIEM log reference</span></span>](https://docs.microsoft.com/advanced-threat-analytics/cef-format-sa) |

## <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="58f33-138">必須開啟稽核記錄</span><span class="sxs-lookup"><span data-stu-id="58f33-138">Audit logging must be turned on</span></span>

<span data-ttu-id="58f33-139">請務必再設定 SIEM 伺服器整合稽核記錄已開啟。</span><span class="sxs-lookup"><span data-stu-id="58f33-139">Make sure audit logging is turned on before you configure SIEM server integration.</span></span> 

- <span data-ttu-id="58f33-140">針對 SharePoint Online OneDrive for Business 和 Azure Active Directory、[稽核記錄在安全性 & 規範中心已開啟](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off)。</span><span class="sxs-lookup"><span data-stu-id="58f33-140">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).</span></span>

- <span data-ttu-id="58f33-141">針對 Exchange Online，[稽核記錄已開啟 Windows powershell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing)。</span><span class="sxs-lookup"><span data-stu-id="58f33-141">For Exchange Online, [audit logging is turned on with Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).</span></span>
 
## <a name="see-also"></a><span data-ttu-id="58f33-142">另請參閱</span><span class="sxs-lookup"><span data-stu-id="58f33-142">See Also</span></span>

[<span data-ttu-id="58f33-143">雲端採用和混合式解決方案</span><span class="sxs-lookup"><span data-stu-id="58f33-143">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
[<span data-ttu-id="58f33-144">雲端採用測試實驗室指南 (TLG)</span><span class="sxs-lookup"><span data-stu-id="58f33-144">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)


