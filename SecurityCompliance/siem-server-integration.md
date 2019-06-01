---
title: Microsoft 365 的 SIEM 伺服器整合
ms.author: deniseb
author: denisebmsft
manager: laurawi
audience: ITPro
ms.topic: article
ms.date: 10/29/2018
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: 摘要： 閱讀本篇文章以取得 Microsoft 365 的 SIEM 伺服器整合的概觀。
ms.openlocfilehash: 05b6e980ae8c6a6b5d32fb3428748468dd861902
ms.sourcegitcommit: 4fedeb06a6e7796096fc6279cfb091c7b89d484d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/31/2019
ms.locfileid: "34652576"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="fc9f4-103">Microsoft 365 服務和應用程式的 SIEM 伺服器整合</span><span class="sxs-lookup"><span data-stu-id="fc9f4-103">SIEM server integration with Microsoft 365 services and applications</span></span>

## <a name="overview"></a><span data-ttu-id="fc9f4-104">概觀</span><span class="sxs-lookup"><span data-stu-id="fc9f4-104">Overview</span></span>

<span data-ttu-id="fc9f4-105">如果您的組織使用的安全性資訊和事件管理 (SIEM) 伺服器，或如果您計劃要推出取得 SIEM 伺服器，您可能想知道如何，將您的 Microsoft 365，包括 Office 365 E5 與整合。</span><span class="sxs-lookup"><span data-stu-id="fc9f4-105">If your organization is using a Security Information and Event Management (SIEM) server, or if you are planning to get a SIEM server soon, you might be wondering how that'll integrate with your Microsoft 365, including Office 365 E5.</span></span> <span data-ttu-id="fc9f4-106">您是否需要 SIEM 伺服器取決於許多因素，例如貴組織的安全性需求。</span><span class="sxs-lookup"><span data-stu-id="fc9f4-106">Whether you need a SIEM server depends on many factors, such as your organization's security requirements.</span></span> <span data-ttu-id="fc9f4-107">Microsoft 365 提供各種不同的安全性功能;不過，如果您的組織有內容和應用程式內部部署和雲端 （如混合式雲端部署的大小寫） 中，您可能會考慮新增額外的保護 SIEM 伺服器。</span><span class="sxs-lookup"><span data-stu-id="fc9f4-107">Microsoft 365 offers a variety of security features; however, if your organization has content and applications on premises and in the cloud (as in the case of a hybrid cloud deployment), you might consider adding a SIEM server for extra protection.</span></span> <span data-ttu-id="fc9f4-108">或者，如果您的組織有必須符合的特別嚴格的安全性需求，您可以考慮將 SIEM 伺服器新增至您的環境。</span><span class="sxs-lookup"><span data-stu-id="fc9f4-108">Or, if your organization has particularly stringent security requirements you must meet, you might consider adding a SIEM server to your environment.</span></span>

## <a name="siem-server-integration-microsoft-365"></a><span data-ttu-id="fc9f4-109">SIEM 伺服器整合 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fc9f4-109">SIEM server integration Microsoft 365</span></span>

<span data-ttu-id="fc9f4-110">SIEM 伺服器可以接收來自各種不同的 Microsoft 365 服務和應用程式的資料。</span><span class="sxs-lookup"><span data-stu-id="fc9f4-110">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="fc9f4-111">下表列出數個 Microsoft 365 服務和應用程式以及 SIEM 伺服器的輸入和移至深入了解 SIEM 伺服器整合的位置。</span><span class="sxs-lookup"><span data-stu-id="fc9f4-111">The following table lists several Microsoft 365 services and applications along with SIEM server inputs and where to go to learn more about SIEM server integration.</span></span> 

| <span data-ttu-id="fc9f4-112">Microsoft 365 服務或應用程式</span><span class="sxs-lookup"><span data-stu-id="fc9f4-112">Microsoft 365 Service or Application</span></span> | <span data-ttu-id="fc9f4-113">SIEM 伺服器輸入</span><span class="sxs-lookup"><span data-stu-id="fc9f4-113">SIEM server inputs</span></span> | <span data-ttu-id="fc9f4-114">若要了解更多的資源</span><span class="sxs-lookup"><span data-stu-id="fc9f4-114">Resources to learn more</span></span> |
| --- | --- | --- |
| [<span data-ttu-id="fc9f4-115">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="fc9f4-115">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md) <br/>   <span data-ttu-id="fc9f4-116">或</span><span class="sxs-lookup"><span data-stu-id="fc9f4-116">or</span></span>   <br/>[<span data-ttu-id="fc9f4-117">Office 365 威脅情報</span><span class="sxs-lookup"><span data-stu-id="fc9f4-117">Office 365 Threat Intelligence</span></span>](office-365-ti.md) | <span data-ttu-id="fc9f4-118">稽核記錄</span><span class="sxs-lookup"><span data-stu-id="fc9f4-118">Audit logs</span></span> | [<span data-ttu-id="fc9f4-119">Office 365 進階威脅防護的 SIEM 整合</span><span class="sxs-lookup"><span data-stu-id="fc9f4-119">SIEM integration with Office 365 Advanced Threat Protection</span></span>](siem-integration-with-office-365-ti.md) |
| [<span data-ttu-id="fc9f4-120">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="fc9f4-120">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | <span data-ttu-id="fc9f4-121">記錄整合</span><span class="sxs-lookup"><span data-stu-id="fc9f4-121">Log integration</span></span> | [<span data-ttu-id="fc9f4-122">Microsoft Cloud App Security 的 SIEM 整合</span><span class="sxs-lookup"><span data-stu-id="fc9f4-122">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem) |
| [<span data-ttu-id="fc9f4-123">Office 365 雲端 App 安全性</span><span class="sxs-lookup"><span data-stu-id="fc9f4-123">Office 365 Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | <span data-ttu-id="fc9f4-124">記錄整合</span><span class="sxs-lookup"><span data-stu-id="fc9f4-124">Log integration</span></span> | [<span data-ttu-id="fc9f4-125">將 SIEM 伺服器整合搭配雲端 App 安全性</span><span class="sxs-lookup"><span data-stu-id="fc9f4-125">Integrate your SIEM server with Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem) |
| [<span data-ttu-id="fc9f4-126">Windows Defender 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="fc9f4-126">Windows Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/) | <span data-ttu-id="fc9f4-127">記錄整合</span><span class="sxs-lookup"><span data-stu-id="fc9f4-127">Log integration</span></span> | [<span data-ttu-id="fc9f4-128">提取提醒您 SIEM 工具</span><span class="sxs-lookup"><span data-stu-id="fc9f4-128">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-siem-windows-defender-advanced-threat-protection) |
| <span data-ttu-id="fc9f4-129">[Azure 資訊安全中心](https://docs.microsoft.com/azure/security-center/security-center-intro)（威脅保護和威脅偵測）</span><span class="sxs-lookup"><span data-stu-id="fc9f4-129">[Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-intro) (Threat Protection and Threat Detection)</span></span> | <span data-ttu-id="fc9f4-130">警示</span><span class="sxs-lookup"><span data-stu-id="fc9f4-130">Alerts</span></span> | [<span data-ttu-id="fc9f4-131">Azure 安全性資料匯出至 SIEM-管線組態-預覽</span><span class="sxs-lookup"><span data-stu-id="fc9f4-131">Azure Security data export to SIEM - Pipeline Configuration - Preview</span></span>](https://docs.microsoft.com/azure/security-center/security-center-export-data-to-siem) |
| [<span data-ttu-id="fc9f4-132">Azure Active Directory 身分識別保護</span><span class="sxs-lookup"><span data-stu-id="fc9f4-132">Azure Active Directory Identity Protection</span></span>](https://docs.microsoft.com/azure/active-directory/identity-protection/overview) | <span data-ttu-id="fc9f4-133">稽核記錄</span><span class="sxs-lookup"><span data-stu-id="fc9f4-133">Audit logs</span></span> | [<span data-ttu-id="fc9f4-134">整合 Azure Active Directory 稽核記錄</span><span class="sxs-lookup"><span data-stu-id="fc9f4-134">Integrate Azure Active Directory audit logs</span></span>](https://docs.microsoft.com/azure/security/security-azure-log-integration-ad) |
| [<span data-ttu-id="fc9f4-135">Azure 的進階的威脅分析</span><span class="sxs-lookup"><span data-stu-id="fc9f4-135">Azure Advanced Threat Analytics</span></span>](https://docs.microsoft.com/azure/security/azure-threat-detection) | <span data-ttu-id="fc9f4-136">記錄整合</span><span class="sxs-lookup"><span data-stu-id="fc9f4-136">Log integration</span></span> | [<span data-ttu-id="fc9f4-137">ATA SIEM 記錄檔參考</span><span class="sxs-lookup"><span data-stu-id="fc9f4-137">ATA SIEM log reference</span></span>](https://docs.microsoft.com/advanced-threat-analytics/cef-format-sa) |

## <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="fc9f4-138">必須先開啟稽核記錄</span><span class="sxs-lookup"><span data-stu-id="fc9f4-138">Audit logging must be turned on</span></span>

<span data-ttu-id="fc9f4-139">請確定您在設定 SIEM 伺服器整合之前，開啟稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="fc9f4-139">Make sure audit logging is turned on before you configure SIEM server integration.</span></span> 

- <span data-ttu-id="fc9f4-140">OneDrive for Business 和 Azure Active Directory[稽核記錄安全性 & 合規性中心中開啟](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off)SharePoint online，版本。</span><span class="sxs-lookup"><span data-stu-id="fc9f4-140">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).</span></span>

- <span data-ttu-id="fc9f4-141">針對 Exchange Online、[使用 Windows PowerShell 開啟稽核記錄](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing)。</span><span class="sxs-lookup"><span data-stu-id="fc9f4-141">For Exchange Online, [audit logging is turned on with Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).</span></span>
 
## <a name="see-also"></a><span data-ttu-id="fc9f4-142">另請參閱</span><span class="sxs-lookup"><span data-stu-id="fc9f4-142">See Also</span></span>

[<span data-ttu-id="fc9f4-143">雲端採用和混合式解決方案</span><span class="sxs-lookup"><span data-stu-id="fc9f4-143">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
[<span data-ttu-id="fc9f4-144">雲端採用測試實驗室指南 (TLG)</span><span class="sxs-lookup"><span data-stu-id="fc9f4-144">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)


