---
title: 適用於 Office 伺服器的 GDPR
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: ''
localization_priority: Priority
description: 深入了解如何在內部部署 Office 伺服器中解決 GDPR 需求。
ms.openlocfilehash: 2f5dc98a9842d6afc70563c6d9dbc0e46b85b089
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272438"
---
# <a name="gdpr-for-office-on-premises-servers"></a><span data-ttu-id="1f57f-103">適用於內部部署 Office 伺服器的 GDPR</span><span class="sxs-lookup"><span data-stu-id="1f57f-103">GDPR for Office on-premises Servers</span></span>

<span data-ttu-id="1f57f-p101">一般資料保護規定 (GDPR) 引進了適用於組織的需求，以保護個人資料並且適當地回應資料主體要求。這一系列的文章提供內部部署工作負載的建議方法：</span><span class="sxs-lookup"><span data-stu-id="1f57f-p101">The General Data Protection Regulation (GDPR) introduces requirements for organizations to protect personal data and respond appropriately to data subject requests. This series of articles provides recommended approaches for on-premises workloads:</span></span>

-   [<span data-ttu-id="1f57f-106">SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="1f57f-106">SharePoint Server</span></span>](gdpr-for-sharepoint-server.md)

-   [<span data-ttu-id="1f57f-107">Exchange Server</span><span class="sxs-lookup"><span data-stu-id="1f57f-107">Exchange Server</span></span>](gdpr-for-exchange-server.md)

-   [<span data-ttu-id="1f57f-108">商務用 Skype Server</span><span class="sxs-lookup"><span data-stu-id="1f57f-108">Skype for Business Server</span></span>](gdpr-for-skype-for-business-server.md)

-   [<span data-ttu-id="1f57f-109">Project Server</span><span class="sxs-lookup"><span data-stu-id="1f57f-109">Project Server</span></span>](gdpr-for-project-server.md)

-   [<span data-ttu-id="1f57f-110">Office Web Apps Server 和 Office Online Server</span><span class="sxs-lookup"><span data-stu-id="1f57f-110">Office Web Apps Server and Office Online Server</span></span>](gdpr-for-office-online-server.md)

-   [<span data-ttu-id="1f57f-111">內部部署檔案共用</span><span class="sxs-lookup"><span data-stu-id="1f57f-111">On-premises file shares</span></span>](gdpr-for-on-premises-file-shares.md)

<span data-ttu-id="1f57f-112">如需有關 GDPR 以及 Microsoft 可以如何協助您的詳細資訊，請參閱 [Microsoft 信任中心](https://www.microsoft.com/zh-TW/TrustCenter/Privacy/gdpr/default.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1f57f-112">For more information about the GDPR and how Microsoft can help you, see the [Microsoft Trust Center](https://www.microsoft.com/zh-TW/TrustCenter/Privacy/gdpr/default.aspx).</span></span>

<span data-ttu-id="1f57f-p102">在您使用內部部署資料進行任何工作之前，請洽詢您的法務和合規性小組，以尋求指引並且深入了解使用個人資料的現有分類結構描述和方法。Microsoft 在位於 [http://aka.ms/gdprpartners](<http://aka.ms/gdprpartners>) 的「Microsoft GDPR 資料探索工具組」中提供開發和擴充分類結構描述的建議。這個工具組也會說明將內部部署資料移至雲端 (您可以在其中使用更複雜的資料控管功能) 的方法。本節中的這篇文章提供對於要保留在內部部署的資料的建議。</span><span class="sxs-lookup"><span data-stu-id="1f57f-p102">Before doing any work with on-premises data, consult with your legal and compliance teams to seek guidance and to learn about existing classification schemas and approaches to working with personal data. Microsoft provides recommendations for developing and extending classifications schemas in the Microsoft GDPR Data Discovery Toolkit at [http://aka.ms/gdprpartners](<http://aka.ms/gdprpartners>). This toolkit also describes approaches for moving on-premises data to the cloud where you can use more sophisticated data governance capabilities, if this is desired. The articles in this section provide recommendations for data that is intended to remain on premises.</span></span>

<span data-ttu-id="1f57f-p103">下圖列出在各個工作負載中使用的建議功能，以探索、分類、保護及監視個人資料。請參閱本節中的文章以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="1f57f-p103">The following illustration lists recommended capabilities to use across each of these workloads to discover, classify, protect, and monitor personal data. See the articles in this section for more information.</span></span>

![](media/gdpr-for-office-servers-image1.png)

## <a name="illustration-description"></a><span data-ttu-id="1f57f-119">圖例說明</span><span class="sxs-lookup"><span data-stu-id="1f57f-119">Illustration description</span></span>

<span data-ttu-id="1f57f-120">為了便於存取，下表會在圖例中提供相同的範例。</span><span class="sxs-lookup"><span data-stu-id="1f57f-120">For accessibility, the following table provides the same examples in the illustration.</span></span>

|             |<span data-ttu-id="1f57f-121">Windows Server 檔案共用</span><span class="sxs-lookup"><span data-stu-id="1f57f-121">Windows Server file shares</span></span>|<span data-ttu-id="1f57f-122">SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="1f57f-122">SharePoint Server</span></span>|<span data-ttu-id="1f57f-123">Exchange Server</span><span class="sxs-lookup"><span data-stu-id="1f57f-123">Exchange Server</span></span>|<span data-ttu-id="1f57f-124">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="1f57f-124">Skype for Business</span></span>|<span data-ttu-id="1f57f-125">Project Server</span><span class="sxs-lookup"><span data-stu-id="1f57f-125">Project Server</span></span>|
|:------------|:-------------------------|:----------------|:--------------|:-----------------|:-------------|
|<span data-ttu-id="1f57f-126">探索</span><span class="sxs-lookup"><span data-stu-id="1f57f-126">Discover</span></span>|<span data-ttu-id="1f57f-127">Azure 資訊保護掃描器\*</span><span class="sxs-lookup"><span data-stu-id="1f57f-127">Azure Information Protection scanner\*</span></span>|<span data-ttu-id="1f57f-128">搜尋中心或 eDiscovery (在資料分類之後)；Azure 資訊保護掃描器\*</span><span class="sxs-lookup"><span data-stu-id="1f57f-128">Search Center or eDiscovery (after data is classified); Azure Information Protection scanner\*</span></span>|<span data-ttu-id="1f57f-129">Exchange eDiscovery 入口網站</span><span class="sxs-lookup"><span data-stu-id="1f57f-129">Exchange eDiscovery Portal</span></span>|<span data-ttu-id="1f57f-130">Exchange eDiscovery 入口網站</span><span class="sxs-lookup"><span data-stu-id="1f57f-130">Exchange eDiscovery portal</span></span>|<span data-ttu-id="1f57f-131">用於探索和匯出的 SQL 指令碼</span><span class="sxs-lookup"><span data-stu-id="1f57f-131">SQL scripts for discovery and exporting</span></span>|
|<span data-ttu-id="1f57f-132">分類</span><span class="sxs-lookup"><span data-stu-id="1f57f-132">Classify</span></span>|<span data-ttu-id="1f57f-133">Azure 資訊保護掃描器 \*；Office 365 機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="1f57f-133">Azure Information Protection scanner\*; Office 365 sensitive information types</span></span>|<span data-ttu-id="1f57f-134">Azure 資訊保護掃描器 \*；Office 365 機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="1f57f-134">Azure Information Protection scanner\*; Office 365 sensitive information types</span></span>|<span data-ttu-id="1f57f-135">Exchange 保留標記和保留原則</span><span class="sxs-lookup"><span data-stu-id="1f57f-135">Exchange retention tags and retention policies</span></span>|<span data-ttu-id="1f57f-136">Exchange 保留標記和保留原則</span><span class="sxs-lookup"><span data-stu-id="1f57f-136">Exchange retention tags and retention policies</span></span>||
|<span data-ttu-id="1f57f-137">保護</span><span class="sxs-lookup"><span data-stu-id="1f57f-137">Protect</span></span>||<span data-ttu-id="1f57f-138">Exchange Server 資料外洩防護規則；權限，文件庫的 IRM 保護</span><span class="sxs-lookup"><span data-stu-id="1f57f-138">Exchange Server data loss prevention rules; Permissions, IRM-protection for libraries</span></span>|<span data-ttu-id="1f57f-139">Exchange Server 資料外洩防護規則；與 Exchange Server 的 IRM 整合</span><span class="sxs-lookup"><span data-stu-id="1f57f-139">Exchange Server data loss prevention rules; IRM integration with Exchange Server</span></span>|||
|<span data-ttu-id="1f57f-140">監視</span><span class="sxs-lookup"><span data-stu-id="1f57f-140">Monitor</span></span>|<span data-ttu-id="1f57f-141">整合記錄與 SIEM 工具</span><span class="sxs-lookup"><span data-stu-id="1f57f-141">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="1f57f-142">整合記錄與 SIEM 工具</span><span class="sxs-lookup"><span data-stu-id="1f57f-142">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="1f57f-143">整合記錄與 SIEM 工具</span><span class="sxs-lookup"><span data-stu-id="1f57f-143">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="1f57f-144">整合記錄與 SIEM 工具</span><span class="sxs-lookup"><span data-stu-id="1f57f-144">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="1f57f-145">整合記錄與 SIEM 工具</span><span class="sxs-lookup"><span data-stu-id="1f57f-145">Integrate logs with SIEM tools</span></span>|

<span data-ttu-id="1f57f-p104">\*請注意，保護會加密檔案。因此，SharePoint Server 在保護的檔案中找不到機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="1f57f-p104">\*Note that protection encrypts the file. Consequently, SharePoint Server can’t find the sensitive information types in protected files.</span></span>
