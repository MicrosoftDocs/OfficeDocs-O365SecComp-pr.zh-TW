---
title: GDPR 的 Office 365 資訊保護概觀
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: 取得 GDPR 的 Office 365 資訊保護概觀。了解如何探索、分類、保護及監視個人資料。
ms.openlocfilehash: 5f10b8c19a2a0d3fe5ace8bcfe8cf6f64c30308f
ms.sourcegitcommit: 15983a08a4ae9c2050344172c7e957830ce3867e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2019
ms.locfileid: "30373854"
---
# <a name="overview-of-office-365-information-protection-for-gdpr"></a><span data-ttu-id="b04f3-104">GDPR 的 Office 365 資訊保護概觀</span><span class="sxs-lookup"><span data-stu-id="b04f3-104">Overview of Office 365 Information Protection for GDPR</span></span>

<span data-ttu-id="b04f3-p102">這個解決方案示範如何保護 Office 365 服務中儲存的敏感資料。其包含探索、分類、保護及監控個人資料的規範性建議。這個解決方案會使用一般資料保護規定 (GDPR) 做為範例，但您可以套用相同的程序，以遵守許多其他法規。包含探索、分類、保護及監控個人資料的規範性建議。</span><span class="sxs-lookup"><span data-stu-id="b04f3-p102">This solution demonstrates how to protect sensitive data that is stored in Office 365 services. It includes prescriptive recommendations for discovering, classifying, protecting, and monitoring personal data. This solution uses General Data Protection Regulation (GDPR) as an example, but you can apply the same process to achieve compliance with many other regulations.</span></span>

<span data-ttu-id="b04f3-p103">GDPR 規定個人資料的收集、儲存、處理及共用。在 GDPR 下，個人資料廣泛地定義為與已識別或可識別之自然人 (即歐盟 (EU) 居民) 相關的任何資料。</span><span class="sxs-lookup"><span data-stu-id="b04f3-p103">GDPR regulates the collection, storage, processing, and sharing of personal data. Personal data is defined very broadly under the GDPR as any data that relates to an identified or identifiable natural person that is a resident of the European Union (EU).</span></span>

<span data-ttu-id="b04f3-110">文章 4 – 定義</span><span class="sxs-lookup"><span data-stu-id="b04f3-110">Article 4 – Definitions</span></span>

> <span data-ttu-id="b04f3-111">「個人資料」表示與已識別或可識別之自然人 (資料主旨) 相關的任何資訊。可識別的自然人是可以直接或間接識別的人員，尤其藉由參照識別碼來識別，例如名稱、身分證號碼、位置資料、線上識別碼，或特定於該自然人的身體、生理、基因、心理、經濟、文化或社會身份的一個或多個因素；</span><span class="sxs-lookup"><span data-stu-id="b04f3-111">‘personal data’ means any information relating to an identified or identifiable natural person (‘data subject’); an identifiable natural person is one who can be identified, directly or indirectly, in particular by reference to an identifier such as a name, an identification number, location data, an online identifier or to one or more factors specific to the physical, physiological, genetic, mental, economic, cultural or social identity of that natural person;</span></span>

<span data-ttu-id="b04f3-p104">這套解決方案旨在協助組織探索並保護 Office 365 中可能受到 GDPR 約束的個人資料。它不是作為 GDPR 規範認證提供的。組織有責任確保自己的 GDPR 規範，並建議諮詢其法律和規範團隊，或向專門從事規範工作的第三方尋求指導和建議。</span><span class="sxs-lookup"><span data-stu-id="b04f3-p104">This solution is intended to help organizations discover and protect personal data in Office 365 that might be subject to the GDPR. It is not offered as a GDPR compliance attestation. Organizations are responsible for ensuring their own GDPR compliance and are advised to consult their legal and compliance teams or to seek guidance and advice from third parties that specialize in compliance.</span></span>

<span data-ttu-id="b04f3-115">[GDPR 評估](https://assessment.microsoft.com/gdpr-compliance)是免費的快速線上自我評估工具，可協助您的組織檢閱其遵循 GDPR 的整體就緒程度。(<http://aka.ms/gdprassessment>)。</span><span class="sxs-lookup"><span data-stu-id="b04f3-115">[GDPR Assessment](https://assessment.microsoft.com/gdpr-compliance) is a quick, online self-evaluation tool available at no cost to help your organization review its overall level of readiness to comply with the GDPR (<http://aka.ms/gdprassessment>).</span></span>

## <a name="assess-and-manage-your-compliance-risk"></a><span data-ttu-id="b04f3-116">評估和管理您的規範風險</span><span class="sxs-lookup"><span data-stu-id="b04f3-116">Assess and manage your compliance risk</span></span>

<span data-ttu-id="b04f3-p105">遵循 GDPR 規範的第一個步驟為評估 GDPR 是否適用於您的組織，如果適用，可到什麼程度。此分析包括了解您組織處理的資料，以及其所在位置。</span><span class="sxs-lookup"><span data-stu-id="b04f3-p105">The first step towards GDPR compliance is to assess whether the GDPR applies to your organization, and, if so, to what extent. This analysis includes understanding the data your organization processes and where it resides.</span></span>

### <a name="step-1--use-compliance-manager-to-view-the-regulation-requirements-and-track-your-progress"></a><span data-ttu-id="b04f3-119">步驟 1 — 使用合規性管理員來檢視規定需求及追蹤進度</span><span class="sxs-lookup"><span data-stu-id="b04f3-119">Step 1 — Use Compliance Manager to view the regulation requirements and track your progress</span></span>

<span data-ttu-id="b04f3-120">合規性管理員提供數個工具來追蹤、實作及管理稽核控制，以協助組織達到各種不同的規範標準，包括 GDPR。</span><span class="sxs-lookup"><span data-stu-id="b04f3-120">Compliance Manager provides tools to track, implement, and manage the auditing controls to help your organization reach compliance against various standards, including GDPR.</span></span>

![使用合規性管理員來檢視需求及追蹤進度](Media/Overview-image1.png)

<span data-ttu-id="b04f3-122">如需詳細資訊，請參閱[使用服務信任入口網站中的合規性管理員](https://support.office.com/zh-TW/article/Use-Compliance-Manager-in-the-Service-Trust-Portal-Preview-5756d342-5af9-4496-82e8-4dd50fa39942)。</span><span class="sxs-lookup"><span data-stu-id="b04f3-122">For more information, see [Use Compliance Manager in the Service Trust Portal](https://support.office.com/zh-TW/article/Use-Compliance-Manager-in-the-Service-Trust-Portal-Preview-5756d342-5af9-4496-82e8-4dd50fa39942).</span></span> 

### <a name="step-2--use-content-search-and-sensitive-information-types-to-find-personal-data"></a><span data-ttu-id="b04f3-123">步驟 2 — 使用內容搜尋和敏感資訊類型來尋找個人資料</span><span class="sxs-lookup"><span data-stu-id="b04f3-123">Step 2 — Use Content Search and sensitive information types to find personal data</span></span> 

<span data-ttu-id="b04f3-p106">探索環境中受到 GDPR 約束的個人資料。請使用內容搜尋與敏感資訊類型搭配，來：</span><span class="sxs-lookup"><span data-stu-id="b04f3-p106">Discover personal data in your environment that is subject to the GDPR. Use Content Search together with sensitive information types to:</span></span>

-   <span data-ttu-id="b04f3-126">尋找並報告個人資料所在的位置。</span><span class="sxs-lookup"><span data-stu-id="b04f3-126">Find and report on where personal data resides.</span></span>

-   <span data-ttu-id="b04f3-127">最佳化敏感資料類型和其他查詢，以尋找環境中的所有個人資料。</span><span class="sxs-lookup"><span data-stu-id="b04f3-127">Optimize sensitive data types and other queries to find all personal data in your environment.</span></span>

![使用內容搜尋和敏感資訊類型來尋找個人資料](Media/Overview-image2.png)

<span data-ttu-id="b04f3-p107">敏感資訊類型會定義自動化程序如何辨識特定資訊類型，例如健康服務號碼和信用卡號碼。本文包含一組可以用作起點的資訊類型。即將對歐盟國家中的個人資料推出許多更敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="b04f3-p107">Sensitive information types define how the automated process recognizes specific information types such as health service numbers and credit card numbers. This article includes a set you can use as a starting point. Many more sensitive information types are coming soon for personal data in EU countries.</span></span>

<span data-ttu-id="b04f3-132">如需詳細資訊，請參閱[搜尋並找出個人資料](search-for-and-find-personal-data.md)。</span><span class="sxs-lookup"><span data-stu-id="b04f3-132">For more information, see [Search for and find personal data](search-for-and-find-personal-data.md).</span></span> 

## <a name="classify-protect-and-monitor-personal-data-in-office-365-and-other-saas-apps"></a><span data-ttu-id="b04f3-133">分類、保護及監視 Office 365 和其他 SaaS 應用程式中的個人資料</span><span class="sxs-lookup"><span data-stu-id="b04f3-133">Classify, protect, and monitor personal data in Office 365 and other SaaS apps</span></span>

<span data-ttu-id="b04f3-134">Office 365 中用於資訊保護的部分功能也可以用來保護其他 SaaS 應用程式中的敏感資料。</span><span class="sxs-lookup"><span data-stu-id="b04f3-134">Some of the capabilities used for information protection in Office 365 can also be used to protect sensitive data in other SaaS applications.</span></span>

![分類、保護及監視個人資料](Media/Overview-image3.png)

<span data-ttu-id="b04f3-136">本節的其餘部分 (步驟 3 - 5) 描述此圖。</span><span class="sxs-lookup"><span data-stu-id="b04f3-136">This illustration is described by the rest this section (steps 3-5).</span></span>

### <a name="step-3--decide-if-you-want-to-use-labels-in-addition-to-sensitive-information-types"></a><span data-ttu-id="b04f3-137">步驟 3 — 決定除了敏感資訊類型外，是否還要使用標籤</span><span class="sxs-lookup"><span data-stu-id="b04f3-137">Step 3 — Decide if you want to use labels in addition to sensitive information types</span></span>

<span data-ttu-id="b04f3-p108">敏感資訊類型是一種分類形式。請參閱[設計個人資料的分類結構描述架構](architect-a-classification-schema-for-personal-data.md)，以決定是否也要實作標籤。若要套用標籤，請參閱[將標籤套用至 Office 365 中的個人資料](apply-labels-to-personal-data-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="b04f3-p108">Sensitive information types are a form of classification. See [Architect a classification schema for personal data](architect-a-classification-schema-for-personal-data.md), to decide if you also want to implement labels. To apply labels, see [Apply labels to personal data in Office 365](apply-labels-to-personal-data-in-office-365.md).</span></span>

<span data-ttu-id="b04f3-p109">在圖例中，敏感資訊類型和標籤適用於整個 Office 365。不久以來，您可以使用這些項目與雲端 App 安全性搭配，來尋找其他 SaaS 應用程式 (例如 Box 和 Salesforce) 中的敏感資料。</span><span class="sxs-lookup"><span data-stu-id="b04f3-p109">In the illustration, sensitive information types and labels work across Office 365. Coming soon, you can use these with Cloud App Security to find sensitive data in other SaaS apps, such as Box and Salesforce.</span></span>

### <a name="step-4--protect-personal-data-in-office-365"></a><span data-ttu-id="b04f3-143">步驟 4 — 保護 Office 365 中的個人資料</span><span class="sxs-lookup"><span data-stu-id="b04f3-143">Step 4 — Protect personal data in Office 365</span></span> 

<span data-ttu-id="b04f3-p110">保護個人資料從 Office 365 資料外洩防護開始。有數個針對保護個人資料存取而建議的其他功能，包括電子郵件的 Office 365 郵件加密。</span><span class="sxs-lookup"><span data-stu-id="b04f3-p110">Protection for personal data starts with Office 365 data loss prevention. There are several other capabilities recommended for protecting access to personal data, including Office 365 Message Encryption for email.</span></span>

<span data-ttu-id="b04f3-146">這些保護能以特定資料集為目標：</span><span class="sxs-lookup"><span data-stu-id="b04f3-146">These protections can be targeted to specific data sets:</span></span>

-   <span data-ttu-id="b04f3-147">網站和文件庫層級權限</span><span class="sxs-lookup"><span data-stu-id="b04f3-147">Site and library-level permissions</span></span>

-   <span data-ttu-id="b04f3-148">網站層級外部共用原則</span><span class="sxs-lookup"><span data-stu-id="b04f3-148">Site-level external sharing policies</span></span>

-   <span data-ttu-id="b04f3-149">網站層級裝置存取控制</span><span class="sxs-lookup"><span data-stu-id="b04f3-149">Site-level device access policies</span></span>

<span data-ttu-id="b04f3-150">保護 Office 365 和其他雲端服務的存取包括：</span><span class="sxs-lookup"><span data-stu-id="b04f3-150">Protection for access to Office 365 and other cloud services include:</span></span>

-   <span data-ttu-id="b04f3-151">企業行動力 + 安全性 (EMS) 的身分識別與裝置存取保護</span><span class="sxs-lookup"><span data-stu-id="b04f3-151">Identity and device access protection in Enterprise Mobility + Security (EMS)</span></span>

-   <span data-ttu-id="b04f3-152">特許存取管理</span><span class="sxs-lookup"><span data-stu-id="b04f3-152">Privileged access management</span></span>

-   <span data-ttu-id="b04f3-153">Windows 10 安全性功能</span><span class="sxs-lookup"><span data-stu-id="b04f3-153">Windows 10 security capabilities</span></span>

<span data-ttu-id="b04f3-154">如需套用保護的詳細資訊，請參閱[將保護套用至 Office 365 中的個人資料](apply-protection-to-personal-data-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="b04f3-154">For more information about applying proteciton, see [Apply protection to personal data in Office 365](apply-protection-to-personal-data-in-office-365.md).</span></span>

### <a name="step-5--monitor-for-leaks-of-personal-data"></a><span data-ttu-id="b04f3-155">步驟 5 — 監視個人資料的外洩</span><span class="sxs-lookup"><span data-stu-id="b04f3-155">Step 5 — Monitor for leaks of personal data</span></span>

<span data-ttu-id="b04f3-p111">Office 365 資料外洩防護報告可提供監視敏感資料的最詳細層級。您可以設定自動警示，並使用 Office 365 稽核記錄調查洩露。雲端 App 安全性可將尋找並監視敏感性資料的功能擴充至其他 SaaS 提供者。如需這些工具的詳細資訊，請參閱[監視個人資料的洩露](monitor-for-leaks-of-personal-data.md)。</span><span class="sxs-lookup"><span data-stu-id="b04f3-p111">Office 365 data loss prevention reports provide the greatest level of detail for monitoring sensitive data. You can setup automated alerts and investigate breaches by using the Office 365 audit log. Cloud App Security extends the ability to find and monitor sensitive data to other SaaS providers. For more information on these tools, see [Monitor for breaches of personal data](monitor-for-leaks-of-personal-data.md).</span></span>
