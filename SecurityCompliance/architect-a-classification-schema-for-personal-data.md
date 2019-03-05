---
title: 設計個人資料的分類結構描述
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: overview
ms.collection:
- Strat_O365_Enterprise
- Ent_O365
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: 判斷您的組織是否將實作標籤做為 GDPR 計劃的一部分。
ms.openlocfilehash: be700d0b055346822ddd63c3c250fad048a7fce8
ms.sourcegitcommit: 15983a08a4ae9c2050344172c7e957830ce3867e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2019
ms.locfileid: "30373864"
---
# <a name="architect-a-classification-schema-for-personal-data"></a><span data-ttu-id="ddbb3-103">設計個人資料的分類結構描述</span><span class="sxs-lookup"><span data-stu-id="ddbb3-103">Architect a classification schema for personal data</span></span>

<span data-ttu-id="ddbb3-p101">本系列先前的文章著重於使用敏感資訊類型，識別受到 GDPR 約束的個人資料。敏感資訊類型是一種分類形式。這可能正是您需要的分類。不過，許多組織會使用標籤，實作更廣泛的資料控管策略。使用本主題，來決定您是否也想要實作標籤做為 GDPR 計劃的一部分。如果您這麼做，本主題提供一些指導方針和範例。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-p101">Previous articles in this series focus on using sensitive information types to identify personal data that is subject to GDPR. Sensitive information types are a form of classification. This might be all the classification you need. However, many organizations implement a broader data governance strategy using labels. Use this topic to decide if you also want to implement labels as part of your GDPR plan. If you do, this topic provides some guidance and examples.</span></span>

<span data-ttu-id="ddbb3-p102">附註：定義組織的分類結構描述和設定原則、標籤和條件，需要仔細規劃和準備。了解這不是 IT 導向程序很重要。請務必與您的法律和規範小組合作，為您組織的資料開發適當的分類與標示結構描述。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-p102">Note: Defining a classification schema for an organization and configuring policies, labels, and conditions requires careful planning and preparation. It is important to realize that this is not an IT driven process. Be sure to work with your legal and compliance team to develop an appropriate classification and labeling schema for your organization’s data.</span></span>

## <a name="decide-if-you-are-using-labels-in-addition-to-sensitive-data-types"></a><span data-ttu-id="ddbb3-113">除了敏感性資料類型外，判斷您是否也使用標籤</span><span class="sxs-lookup"><span data-stu-id="ddbb3-113">Decide if you are using labels in addition to sensitive data types</span></span>

<span data-ttu-id="ddbb3-p103">您可以在 Office 365 中採取兩種方法，對個人資訊進行分類。其中一種可以用於 GDPR 保護。如果決定僅使用敏感資訊類型進行分類，您可以跳過本主題的其餘部分。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-p103">You can take one of two approaches for classification in Office 365 for personal information. Either of these can be used for GDPR protection. If decide to use only sensitive information types for classification, you can skip the rest of this topic.</span></span>

<span data-ttu-id="ddbb3-117">選擇下列其中一個選項。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-117">Choose one of the following options.</span></span>

### <a name="option-1-use-only-office-365-sensitive-information-types"></a><span data-ttu-id="ddbb3-118">選項 1：僅使用 Office 365 敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="ddbb3-118">Option 1: Use only Office 365 sensitive information types</span></span>

-   <span data-ttu-id="ddbb3-119">敏感資訊類型非常適用於識別和保護受到 GDPR 和其他法規類型約束的個人資料。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-119">Sensitive information types work well to identify and protect personal data subject to GDPR and other types of regulations.</span></span>

-   <span data-ttu-id="ddbb3-120">如果您的組織尚未有敏感資訊類型，或打算使用標籤，實作更廣泛的資料控管計劃，則這些敏感資訊類型更易於使用。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-120">These are simpler to use if your organization doesn’t already have or plan to implement a broader data governance plan using labels.</span></span>

-   <span data-ttu-id="ddbb3-121">這些敏感資訊類型會使用 DLP 規則 (Office 標籤也一樣)。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-121">These work with DLP rules (so do Office labels).</span></span>

-   <span data-ttu-id="ddbb3-122">未來，這些敏感資訊類型將使用雲端 App 安全性，以便您可以偵測其他 SaaS 應用程式中的敏感資訊。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-122">In the future these will work with Cloud App Security so you can detect sensitive information in other SaaS apps.</span></span>

### <a name="option-2-use-sensitive-information-types--office-labels"></a><span data-ttu-id="ddbb3-123">選項 2：使用敏感資訊類型 + Office 標籤</span><span class="sxs-lookup"><span data-stu-id="ddbb3-123">Option 2: Use sensitive information types + Office labels</span></span>

-   <span data-ttu-id="ddbb3-124">您將需要敏感資訊類型，以自動將標籤套用至受到 GDPR 約束的個人資料，因此這些敏感資訊類型是必要的。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-124">You’ll need sensitive information types to automatically apply labels to personal data that is subject to GDPR, so these are a prerequisite.</span></span>

-   <span data-ttu-id="ddbb3-125">使用 Office 標籤可讓您將受到 GDPR 約束的個人資料併入更廣泛的資料控管計劃中。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-125">Using Office labels allows you to include personal data that is subject to GDPR into a broader data governance plan for your organization.</span></span>

-   <span data-ttu-id="ddbb3-126">稍後，Office 標籤將與 Azure 資訊保護標籤匯聚成統一的分類和標示引擎。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-126">Later, Office labels will converge with Azure Information Protection labels into a unified classification and labeling engine.</span></span>

## <a name="develop-a-label-schema-that-includes-personal-data"></a><span data-ttu-id="ddbb3-127">開發包含個人資料的標籤結構描述</span><span class="sxs-lookup"><span data-stu-id="ddbb3-127">Develop a label schema that includes personal data</span></span>

<span data-ttu-id="ddbb3-p104">在使用技術功能來套用標籤和保護之前，於您的整個組織中首先定義分類結構描述。您的組織可能已有分類結構描述，可讓您更輕鬆地新增個人資料。本主題包含分類結構描述範例。必要時，您可以使用此範例做為起點。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-p104">Before using technical capabilities to apply labels and protection, first work across your organization to define a classification schema. Your organization might already have a classification schema, which makes it easier to add personal data. This topic includes an example classification schema. You can use this as a starting point, if needed.</span></span>

### <a name="getting-started"></a><span data-ttu-id="ddbb3-132">快速入門</span><span class="sxs-lookup"><span data-stu-id="ddbb3-132">Getting started</span></span>

<span data-ttu-id="ddbb3-p105">從決定要實作之標籤的數目和名稱開始。執行此活動，不必擔心要使用哪種技術，以及將如何套用標籤。將此結構描述套用至您的整個組織，包括存放在內部部署以及其他雲端服務中的資料。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-p105">Begin by deciding on the number and names of labels to implement. Do this activity without worrying about which technology to use and how labels will be applied. Apply this schema universally throughout your organization, including data that resides on premises and in other cloud services.</span></span>

### <a name="recommendations"></a><span data-ttu-id="ddbb3-136">建議</span><span class="sxs-lookup"><span data-stu-id="ddbb3-136">Recommendations</span></span> 

<span data-ttu-id="ddbb3-137">設計和實作原則、標籤和條件時，請考慮遵循下列建議：</span><span class="sxs-lookup"><span data-stu-id="ddbb3-137">When designing and implementing policies, labels and conditions, consider following these recommendations:</span></span>

-   <span data-ttu-id="ddbb3-p106">使用現有的分類結構描述 (如果有的話) — 許多組織已在使用某種形式的資料分類。仔細評估現有的標籤結構描述，並盡可能按原狀使用。利用使用者可以辨識的熟悉標籤將提高採用率。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-p106">Use existing classification schema (if any) — Many organizations already are using data classification in some form. Carefully evaluate the existing label schema and if possible use it as is. Using familiar labels that are recognizable to the end-user will drive adoption.</span></span>

-   <span data-ttu-id="ddbb3-p107">從預設原則和標籤開始 — 所有解決方案都隨附一組預先定義的原則和標籤。針對組織法律和商務需求仔細評估這些原則和標籤，並考慮使用它們，而不建立新的原則和標籤。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-p107">Start with default policies and labels — All solutions come with a set of predefined policies and labels. Carefully evaluate these against the organizations legal and business requirements and consider using them instead of creating new ones.</span></span>

-   <span data-ttu-id="ddbb3-p108">從少量開始 — 可以建立的標籤數目幾乎沒有限制。不過，大量標籤和子標籤將對採用造成負面影響。太多選擇通常表示完全沒有選擇。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-p108">Start small — There is virtually no limit to the number of labels that can be created. However, large numbers of labels and sub-labels will negatively impact the adoption. Too many choices often means no choice at all.</span></span>

-   <span data-ttu-id="ddbb3-146">使用情節和使用案例 — 識別組織內常見的使用案例，並使用衍生自 GDPR 的情節，來驗證構想的標籤和分類設定是否實際可行。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-146">Use scenarios and use cases — Identify common use cases within the organization and use scenarios derived from the GDPR to verify if the envisioned label and classification configuration will work in practice.</span></span>

-   <span data-ttu-id="ddbb3-p109">每次要求新標籤時，問自己每個情節或使用案例真的需要新的標籤，還是可以使用已有的標籤？保持最少的標籤數目可以提高採用率。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-p109">Question every request for a new label, does every scenario or use case really need a new label or can we use what we already have? Keeping the number of labels to a minimum improves adoption.</span></span>

-   <span data-ttu-id="ddbb3-p110">對重要部門使用子標籤，某些部門將有需要特定標籤的特定需求。定義這些標籤做為現有標籤的子標籤，並考慮使用已指派給使用者群組，而不是全域指派的範圍限定原則。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-p110">Use sub-labels for key departments, some departments will have specific needs that require specific labels. Define these labels as sub-labels to an existing label and consider using scoped policies that are assigned to user groups instead of globally.</span></span>

-   <span data-ttu-id="ddbb3-p111">請考慮範圍限定原則，此為將使用者子集設為目標的原則，將防止「標籤超載」。範圍限定原則可讓您只將角色或部門特定 (子) 標籤指派給為特定部門工作的員工。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-p111">Consider scoped policies, polices targeted at subsets of users will prevent "label overload". A scoped policy enables assigning role or department specific (sub-)labels to just employees that work for that specific department.</span></span>

-   <span data-ttu-id="ddbb3-p112">使用有意義的標籤名稱，建議您不要使用行話、標準或縮略字做為標籤名稱。請嘗試使用與使用者產生共鳴的名稱，以提高採用率。不是使用如 PII、PCI、HIPAA、LBI、MBI 和 HBI 這類的標籤，而是考慮如非商務、公用、一般、機密、高度機密這類的名稱。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-p112">Use meaningful label names, it is recommended not to use jargon, standards or acronyms as label names. Try to use names that resonate with the end user to improve adoption. Instead of using labels like PII, PCI, HIPAA, LBI, MBI and HBI consider names like Non-Business, Public, General, Confidential and Highly Confidential.</span></span>

### <a name="example-classification-schema"></a><span data-ttu-id="ddbb3-156">分類結構描述範例</span><span class="sxs-lookup"><span data-stu-id="ddbb3-156">Example classification schema</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ddbb3-157"><strong>標籤名稱</strong></span><span class="sxs-lookup"><span data-stu-id="ddbb3-157"><strong>Label name</strong></span></span></th>
<th align="left"><span data-ttu-id="ddbb3-158"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="ddbb3-158"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="ddbb3-159">個人</span><span class="sxs-lookup"><span data-stu-id="ddbb3-159">Personal</span></span></td>
<td align="left"><span data-ttu-id="ddbb3-160">非商務資料，僅供個人使用。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-160">Non-business data, for personal use only.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="ddbb3-161">公用</span><span class="sxs-lookup"><span data-stu-id="ddbb3-161">Public</span></span></td>
<td align="left"><span data-ttu-id="ddbb3-162">特別準備並核准公開取用的商務資料。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-162">Business data that is specifically prepared and approved for public consumption.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="ddbb3-163">客戶資料</span><span class="sxs-lookup"><span data-stu-id="ddbb3-163">Customer data</span></span></td>
<td align="left"><span data-ttu-id="ddbb3-p113">包含個人識別資訊的商務資料。範例有信用卡號、銀行帳戶號碼和社會安全號碼。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-p113">Business data that contains personal identifiable information. Examples are credit card numbers, bank account numbers, and social security numbers.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="ddbb3-166">HR 資料</span><span class="sxs-lookup"><span data-stu-id="ddbb3-166">HR data</span></span></td>
<td align="left"><span data-ttu-id="ddbb3-167">關於 Contoso 員工的人力資源資料，例如員工編號和薪資資料。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-167">Human Resource data about Contoso employees, such as employee number and salary data.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="ddbb3-168">機密</span><span class="sxs-lookup"><span data-stu-id="ddbb3-168">Confidential</span></span></td>
<td align="left"><span data-ttu-id="ddbb3-p114">若與未經授權的人員共用，可能對企業造成損害的敏感商務資料。範例包括合約、安全性報告、預測摘要和銷售帳單資料。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-p114">Sensitive business data that could cause damage to the business if shared with unauthorized people. Examples include contracts, security reports, forecast summaries, and sales account data.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="ddbb3-171">高度機密</span><span class="sxs-lookup"><span data-stu-id="ddbb3-171">Highly confidential</span></span></td>
<td align="left"><span data-ttu-id="ddbb3-p115">如果與未經授權的人員共用，將對企業造成損害的非常敏感商務資料。範例包括員工與客戶資訊、密碼、程式碼和預先公告的財務報表。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-p115">Very sensitive business data that would cause damage to the business if it was shared with unauthorized people. Examples include employee and customer information, passwords, source code, and pre-announced financial reports.</span></span></td>
</tr>
</tbody>
</table>

## <a name="define-a-taxonomy-and-search-criteria-for-each-label"></a><span data-ttu-id="ddbb3-174">定義每一個標籤的分類與搜尋準則</span><span class="sxs-lookup"><span data-stu-id="ddbb3-174">Define a taxonomy and search criteria for each label</span></span>

<span data-ttu-id="ddbb3-p116">在為您的組織開發分類結構描述之後，下一個步驟是開發用於尋找此資料的分類與搜尋準則。對於個人資料，您已經完成此工作，方法為識別敏感資訊類型，同時也為您的環境自訂或建立新的敏感資訊類型，。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-p116">After developing a classification schema for your organization, the next step is to develop the taxonomy and search criteria for finding this data. For personal data, you’ve already completed this work by identifying sensitive information types and also by customizing or creating new sensitive information types for your environment.</span></span>

<span data-ttu-id="ddbb3-p117">下表提供組織適用的結構描述、分類和搜尋準則範例。標籤依敏感性層級排序 (從最不敏感到最敏感) 以確保符合多個標籤條件的資料會被指派適當的標籤。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-p117">The following table provides an example schema, taxonomy, and search criteria for an organization. The labels are ordered by sensitivity level from least sensitive to most sensitive to ensure that data that matches multiple label conditions is assigned the appropriate label.</span></span>

<span data-ttu-id="ddbb3-179">附註：提供的設定範例僅供說明，而不是做為部署指引和參考。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-179">Note: The configuration example is provided for illustration only and is not intended as deployment guidance or reference.</span></span>

<span data-ttu-id="ddbb3-180">重點是確保您投入以針對 GDPR 規範分類個人資料的工作，與您整個組織的目標一致。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-180">The important takeaway is to ensure that the work you invest to classify personal data for GDPR compliance fits together with the objectives for your entire organization.</span></span>

### <a name="example-schema-taxonomy-and-search-criteria"></a><span data-ttu-id="ddbb3-181">結構描述、分類和搜尋準則範例</span><span class="sxs-lookup"><span data-stu-id="ddbb3-181">Example schema, taxonomy, and search criteria</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ddbb3-182"><strong>標籤</strong></span><span class="sxs-lookup"><span data-stu-id="ddbb3-182"><strong>Label</strong></span></span></th>
<th align="left"><span data-ttu-id="ddbb3-183"><strong>分類</strong></span><span class="sxs-lookup"><span data-stu-id="ddbb3-183"><strong>Taxonomy</strong></span></span></th>
<th align="left"><span data-ttu-id="ddbb3-184"><strong>方法</strong></span><span class="sxs-lookup"><span data-stu-id="ddbb3-184"><strong>Method</strong></span></span></th>
<th align="left"><span data-ttu-id="ddbb3-185"><strong>搜尋語法</strong></span><span class="sxs-lookup"><span data-stu-id="ddbb3-185"><strong>Search syntax</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="ddbb3-186">個人</span><span class="sxs-lookup"><span data-stu-id="ddbb3-186">Personal</span></span></td>
<td align="left"><span data-ttu-id="ddbb3-187">使用者手動標示為個人的文件。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-187">Documents manually labelled personal by the end user.</span></span></td>
<td align="left"><span data-ttu-id="ddbb3-188">手動</span><span class="sxs-lookup"><span data-stu-id="ddbb3-188">Manual</span></span></td>
<td align="left"><span data-ttu-id="ddbb3-189">使用者手動標示為個人的文件。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-189">Documents manually labelled personal by the end user.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="ddbb3-190">公用</span><span class="sxs-lookup"><span data-stu-id="ddbb3-190">Public</span></span></td>
<td align="left"><span data-ttu-id="ddbb3-191">包含不區分大小寫之字詞 Approved for Public Release ##/#### 的文件，其中 # 代表任何數字。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-191">Documents containing the case insensitive phrase Approved for Public Release ##/#### where # represents any digit.</span></span></td>
<td align="left"><p><span data-ttu-id="ddbb3-192">KQL</span><span class="sxs-lookup"><span data-stu-id="ddbb3-192">KQL</span></span></p>
<p><span data-ttu-id="ddbb3-193">RegEx</span><span class="sxs-lookup"><span data-stu-id="ddbb3-193">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="ddbb3-194">KQL — Approved for Public Release\*</span><span class="sxs-lookup"><span data-stu-id="ddbb3-194">KQL — Approved for Public Release\*</span></span></p>
<p><span data-ttu-id="ddbb3-195">RegEx — (?i)(\bApproved for Public Release \d{2}\/\d{4}\b)</span><span class="sxs-lookup"><span data-stu-id="ddbb3-195">RegEx — (?i)(\bApproved for Public Release \d{2}\/\d{4}\b)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="ddbb3-196">客戶資料</span><span class="sxs-lookup"><span data-stu-id="ddbb3-196">Customer data</span></span></td>
<td align="left"><span data-ttu-id="ddbb3-197">歐盟公民資料的敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-197">Sensitive information types for EU citizen data.</span></span></td>
<td align="left"><span data-ttu-id="ddbb3-198">敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="ddbb3-198">Sensitive information types</span></span></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="ddbb3-199">人力資源 — 員工資料</span><span class="sxs-lookup"><span data-stu-id="ddbb3-199">Human Resources — Employee Data</span></span></td>
<td align="left"><span data-ttu-id="ddbb3-200">以格式 CONTOSO-9##### 包含區分大小寫之員工 ID 的文件，其中 # 代表任何數字。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-200">Documents that include the case sensitive employee id in the format CONTOSO-9##### where # represents any digit.</span></span></td>
<td align="left"><p><span data-ttu-id="ddbb3-201">KQL</span><span class="sxs-lookup"><span data-stu-id="ddbb3-201">KQL</span></span></p>
<p><span data-ttu-id="ddbb3-202">RegEx</span><span class="sxs-lookup"><span data-stu-id="ddbb3-202">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="ddbb3-203">KQL — CONTOSO-9\*</span><span class="sxs-lookup"><span data-stu-id="ddbb3-203">KQL — CONTOSO-9\*</span></span></p>
<p><span data-ttu-id="ddbb3-204">RegEx — (\bCONTOSO-9\d{5}\b)</span><span class="sxs-lookup"><span data-stu-id="ddbb3-204">RegEx — (\bCONTOSO-9\d{5}\b)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="ddbb3-205">人力資源 — 薪資資料</span><span class="sxs-lookup"><span data-stu-id="ddbb3-205">Human Resources — Salary Data</span></span></td>
<td align="left"><span data-ttu-id="ddbb3-206">包含關鍵字 (不區分大小寫) Contoso AND 或關鍵字 (不區分大小寫) Salary OR Compensation 的文字</span><span class="sxs-lookup"><span data-stu-id="ddbb3-206">Documents that include the keyword (not case sensitive) Contoso AND either keyword (not case sensitive) Salary OR Compensation</span></span></td>
<td align="left"><p><span data-ttu-id="ddbb3-207">KQL</span><span class="sxs-lookup"><span data-stu-id="ddbb3-207">KQL</span></span></p>
<p><span data-ttu-id="ddbb3-208">RegEx</span><span class="sxs-lookup"><span data-stu-id="ddbb3-208">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="ddbb3-209">KQL — Contoso AND (Salary OR Compensation)</span><span class="sxs-lookup"><span data-stu-id="ddbb3-209">KQL — Contoso AND (Salary OR Compensation)</span></span></p>
<p><span data-ttu-id="ddbb3-210">RegEx — (\bCONTOSO-9\d{5}\b)</span><span class="sxs-lookup"><span data-stu-id="ddbb3-210">RegEx — (\bCONTOSO-9\d{5}\b)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="ddbb3-211">機密</span><span class="sxs-lookup"><span data-stu-id="ddbb3-211">Confidential</span></span></td>
<td align="left"><span data-ttu-id="ddbb3-212">包含字詞 (不區分大小寫) Contoso Confidential 的文件。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-212">Documents containing the phrase (not case sensitive) Contoso Confidential.</span></span></td>
<td align="left"><p><span data-ttu-id="ddbb3-213">KQL</span><span class="sxs-lookup"><span data-stu-id="ddbb3-213">KQL</span></span></p>
<p><span data-ttu-id="ddbb3-214">RegEx</span><span class="sxs-lookup"><span data-stu-id="ddbb3-214">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="ddbb3-215">KQL — Contoso Confidential</span><span class="sxs-lookup"><span data-stu-id="ddbb3-215">KQL — Contoso Confidential</span></span></p>
<p><span data-ttu-id="ddbb3-216">RegEx — (?i)(\bContoso Confidential\b)</span><span class="sxs-lookup"><span data-stu-id="ddbb3-216">RegEx — (?i)(\bContoso Confidential\b)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="ddbb3-217">高度機密</span><span class="sxs-lookup"><span data-stu-id="ddbb3-217">Highly confidential</span></span></td>
<td align="left"><span data-ttu-id="ddbb3-218">包含字詞 (區分大小寫) Contoso Secret 或 Secret-C#### 的文件，其中 # 代表任何數字。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-218">Documents that include either pharase (case sensitive) Contoso Secret or Secret-C#### where # represents any digit.</span></span></td>
<td align="left"><p><span data-ttu-id="ddbb3-219">KQL</span><span class="sxs-lookup"><span data-stu-id="ddbb3-219">KQL</span></span></p>
<p><span data-ttu-id="ddbb3-220">RegEx</span><span class="sxs-lookup"><span data-stu-id="ddbb3-220">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="ddbb3-221">KQL — Contoso Secret OR Secret-C\*</span><span class="sxs-lookup"><span data-stu-id="ddbb3-221">KQL — Contoso Secret OR Secret-C\*</span></span></p>
<p><span data-ttu-id="ddbb3-222">RegEx — (?i)(\bContoso Secret\b)|(\bSecret-C\d{4}\b)</span><span class="sxs-lookup"><span data-stu-id="ddbb3-222">RegEx — (?i)(\bContoso Secret\b)|(\bSecret-C\d{4}\b)</span></span></p></td>
</tr>
</tbody>
</table>
