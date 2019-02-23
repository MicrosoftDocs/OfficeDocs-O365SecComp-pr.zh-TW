---
title: 將標籤套用至 Office 365 中的個人資料
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
ms.service: O365-seccomp
localization_priority: Priority
ms.custom: ''
ms.assetid: ''
search.appverid:
- MET150
description: 了解如何使用 Office 標籤做為 GDPR 保護計劃的一部分。
ms.openlocfilehash: 1ba410b4ff6471c5e32587f5f213033eef4c6c18
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30221233"
---
# <a name="apply-labels-to-personal-data-in-office-365"></a><span data-ttu-id="66ac3-103">將標籤套用至 Office 365 中的個人資料</span><span class="sxs-lookup"><span data-stu-id="66ac3-103">Apply labels to personal data in Office 365</span></span>

 <span data-ttu-id="66ac3-p101">如果您使用 Office 標籤做為 GDPR 保護計劃的一部分，請使用本主題。目前可在 Office 365 安全性與合規性中心和 Azure 資訊保護中建立標籤。隨著時間的推移，這些技術將匯聚成一個統一的標籤和分類體驗，而且您將能夠達成更多的目標。</span><span class="sxs-lookup"><span data-stu-id="66ac3-p101">Use this topic if you are using Office labels as part of your GDPR protection plan. Today labels can be created in the Office 365 Security & Compliance Center and in Azure Information Protection. Over time these technologies will converge into a unified labeling and classification experience and you will be able to achieve even more.</span></span>

<span data-ttu-id="66ac3-p102">如果您是使用標籤來保護 Office 365 中的個人資料，Microsoft 建議您先建立 Office 標籤。您可以使用進階資料控管，根據敏感資訊或其他準則自動套用標籤。您可以使用 Office 標籤與資料外洩防護搭配來套用保護。您也可以使用標籤與進階電子文件探索和內容搜尋搭配。您很快就可以同時使用標籤和敏感資訊類型與 Cloud App Security 搭配，來監視位於其他 SaaS 應用程式中的個人資料。</span><span class="sxs-lookup"><span data-stu-id="66ac3-p102">If you are using labels for protection of personal data in Office 365, Microsoft recommends you start with Office labels. You can use Advanced Data Governance to automatically apply labels based on sensitive information types or other criteria. You can use Office labels with data loss prevention to apply protection. You can also use labels with eDiscovery and Content Search. You’ll soon be able to use both labels and sensitive information types with Cloud App Security to monitor personal data that resides in other SaaS apps.</span></span>

<span data-ttu-id="66ac3-p103">目前建議將 Azure 資訊保護標籤套用至內部部署以及其他雲端服務和提供者中的檔案。也建議將這些標籤用於 Office 365 中需要 Microsoft Azure AD Rights Management (Azure RMS) 加密來保護資料的檔案，例如商業機密檔案。</span><span class="sxs-lookup"><span data-stu-id="66ac3-p103">Azure Information Protection labels are currently recommended for applying labels to files on premises and in other cloud services and providers. These are also recommended for files in Office 365 that require Azure Rights Management (Azure RMS) encryption for data protection, such as trade secret files.</span></span>

<span data-ttu-id="66ac3-p104">此時，對於資料在 Office 365 中受到 GDPR 約束的檔案，建議不要使用 Azure 資訊保護來套用 Azure RMS 加密。Office 365 服務目前無法讀取 RMS 加密的檔案。因此，服務找不到檔案中的敏感資料。</span><span class="sxs-lookup"><span data-stu-id="66ac3-p104">At this time, using Azure Information Protection to apply Azure RMS encryption is not recommended for files in Office 365 with data that is subject to the GDPR. Office 365 services currently cannot read into RMS-encrypted files. Therefore, the service can’t find sensitive data in these files.</span></span>

<span data-ttu-id="66ac3-p105">Azure 資訊保護標籤可套用至 Exchange Online 中的郵件，而且這些標籤會搭配使用 Office 365 資料外洩防護。即將推出統一的分類和標記引擎，讓您能夠針對電子郵件及檔案使用相同的標籤，包括自動標記並保護傳輸中的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="66ac3-p105">Azure Information Protection labels can be applied to mail in Exchange Online and these labels work with Office 365 data loss prevention. Coming soon with the unified classification and labeling engine you will be able to use the same labels for email and files, including automatically labeling and protecting email in transit.</span></span>

![Office 365 標籤和 Azure 資訊保護標籤](Media/Apply-labels-to-personal-data-in-Office-365-image1.png)

<span data-ttu-id="66ac3-120">在此圖例中：</span><span class="sxs-lookup"><span data-stu-id="66ac3-120">In the illustration:</span></span>

-   <span data-ttu-id="66ac3-121">將 Office 365 標籤用於個人資料，以及 SharePoint Online 和商務用 OneDrive 中高度管制的商業機密檔案。</span><span class="sxs-lookup"><span data-stu-id="66ac3-121">Use Office 365 labels for personal data and for highly regulated & trade secret files in SharePoint Online and OneDrive for Business.</span></span>

-   <span data-ttu-id="66ac3-122">將 Azure 資訊保護 (AIP) 標籤用於高度管制的商業機密檔案、Exchange Online 電子郵件、其他 SaaS 服務中的檔案、內部部署資料中心中的檔案，以及其他雲端提供者中的檔案。</span><span class="sxs-lookup"><span data-stu-id="66ac3-122">Use Azure Information Protection (AIP) labels for highly regulated & trade secret files, Exchange Online email, files in other SaaS services, files in on-premises datacenters, and files in other cloud providers.</span></span>

-   <span data-ttu-id="66ac3-123">即將推出：這兩種類型的標籤將匯聚成統一的分類和標記體驗。</span><span class="sxs-lookup"><span data-stu-id="66ac3-123">Coming soon: both types of labels will converge into a unified classification and labeling experience.</span></span>

## <a name="use-office-labels-and-sensitive-information-types-across-microsoft-365-for-information-protection"></a><span data-ttu-id="66ac3-124">在整個 Microsoft 365 中使用 Office 標籤和敏感資訊類型以保護資訊</span><span class="sxs-lookup"><span data-stu-id="66ac3-124">Use Office labels and sensitive information types across Microsoft 365 for information protection</span></span>

<span data-ttu-id="66ac3-125">下圖顯示如何在標籤原則、資料外洩防護原則，以及搭配雲端 App 安全性原則使用 Office 標籤和敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="66ac3-125">The following illustration shows how Office labels and sensitive information types can be used in label policies, data loss prevention policies, and with Cloud App Security policies.</span></span>

![Office 標籤和敏感資訊類型](Media/Apply-labels-to-personal-data-in-Office-365-image2.png)

<span data-ttu-id="66ac3-127">為了便於存取，下表會在圖例中提供相同的範例。</span><span class="sxs-lookup"><span data-stu-id="66ac3-127">For accessibility, the following table provides the same examples in the illustration.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="66ac3-128"><strong>分類元素</strong></span><span class="sxs-lookup"><span data-stu-id="66ac3-128"><strong>Classification elements</strong></span></span></th>
<th align="left"><span data-ttu-id="66ac3-129"><strong>標籤原則 — 2 個範例</strong></span><span class="sxs-lookup"><span data-stu-id="66ac3-129"><strong>Label policies — 2 examples</strong></span></span></th>
<th align="left"><span data-ttu-id="66ac3-130"><strong>資料外洩防護原則 — 2 個範例</strong></span><span class="sxs-lookup"><span data-stu-id="66ac3-130"><strong>Data loss prevention policies — 2 examples</strong></span></span></th>
<th align="left"><span data-ttu-id="66ac3-131"><strong>所有 SaaS 應用程式的雲端 App 安全性原則 — 1 個範例</strong></span><span class="sxs-lookup"><span data-stu-id="66ac3-131"><strong>Cloud App Security policies for all SaaS apps — 1 example</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="66ac3-p106">Office 標籤。範例：個人、公用、客戶資料、HR 資料、機密、高度機密</span><span class="sxs-lookup"><span data-stu-id="66ac3-p106">Office labels. Examples: Personal, Public, Customer data, HR data, Confidential, Highly confidential</span></span></td>
<td align="left"><p><span data-ttu-id="66ac3-p107">自動套用此標籤 . . .</span><span class="sxs-lookup"><span data-stu-id="66ac3-p107">Auto apply this label . . .</span></span></p>
<p><span data-ttu-id="66ac3-137">客戶資料</span><span class="sxs-lookup"><span data-stu-id="66ac3-137">Customer data</span></span></p>
<p><span data-ttu-id="66ac3-p108">. . . 至符合這些敏感資訊類型的文件 . . .</span><span class="sxs-lookup"><span data-stu-id="66ac3-p108">. . . to documents that match these sensitive information types . . .</span></span></p>
<p><span data-ttu-id="66ac3-144">&lt;敏感資訊類型範例的清單&gt;</span><span class="sxs-lookup"><span data-stu-id="66ac3-144">&lt;list of example sensitive information types&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="66ac3-p109">套用此保護 . . .</span><span class="sxs-lookup"><span data-stu-id="66ac3-p109">Apply this protection . . .</span></span></p>
<p><span data-ttu-id="66ac3-148">&lt;定義保護&gt;</span><span class="sxs-lookup"><span data-stu-id="66ac3-148">&lt;define protection&gt;</span></span></p>
<p><span data-ttu-id="66ac3-p110">. . . 至具有此標籤的文件 . . .</span><span class="sxs-lookup"><span data-stu-id="66ac3-p110">. . . to documents with this label . . .</span></span></p>
<p><span data-ttu-id="66ac3-155">客戶資料</span><span class="sxs-lookup"><span data-stu-id="66ac3-155">Customer data</span></span></p></td>
<td align="left"><p><span data-ttu-id="66ac3-p111">在任何獲批准的 SaaS App 中具有這些屬性的檔案 . . .</span><span class="sxs-lookup"><span data-stu-id="66ac3-p111">Alert when files with these attributes . . .</span></span></p>
<p><span data-ttu-id="66ac3-159">&lt;預先定義的 PII 屬性或自訂運算式&gt;</span><span class="sxs-lookup"><span data-stu-id="66ac3-159">&lt;predefined PII attribute -or- custom expression&gt;</span></span></p>
<p><span data-ttu-id="66ac3-p112">. . . 在組織外共用時發出警示</span><span class="sxs-lookup"><span data-stu-id="66ac3-p112">. . . in any sanctioned SaaS app are shared outside the organization</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="66ac3-p113">敏感資訊類型範例：比利時國民編碼、信用卡號碼、克羅埃西亞身分證號碼、芬蘭國民身分證</span><span class="sxs-lookup"><span data-stu-id="66ac3-p113">Sensitive information types. Examples: Belgium National Number, Credit Card Number, Croatia Identity Cart Number, Finland National ID</span></span></td>
<td align="left"><p><span data-ttu-id="66ac3-p114">發佈這些使用者的這些標籤以手動套用 . . .</span><span class="sxs-lookup"><span data-stu-id="66ac3-p114">Publish these labels for users to manually apply . . .</span></span></p>
<p><span data-ttu-id="66ac3-169">&lt;選取標籤&gt;</span><span class="sxs-lookup"><span data-stu-id="66ac3-169">&lt;select labels&gt;</span></span></p>
<p><span data-ttu-id="66ac3-p115">. . . 至這些位置 . . .</span><span class="sxs-lookup"><span data-stu-id="66ac3-p115">. . . to these locations . . .</span></span></p>
<p><span data-ttu-id="66ac3-176">&lt;所有位置或選擇特定位置&gt;</span><span class="sxs-lookup"><span data-stu-id="66ac3-176">&lt;all locations or choose specific locations&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="66ac3-p116">套用此保護 . . .</span><span class="sxs-lookup"><span data-stu-id="66ac3-p116">Apply this protection . . .</span></span></p>
<p><span data-ttu-id="66ac3-180">&lt;定義保護&gt;</span><span class="sxs-lookup"><span data-stu-id="66ac3-180">&lt;define protection&gt;</span></span></p>
<p><span data-ttu-id="66ac3-p117">. . . 至符合這些敏感資訊類型的文件&gt;</span><span class="sxs-lookup"><span data-stu-id="66ac3-p117">. . . to documents that match these sensitive information types&gt;</span></span></p></td>
<td align="left"><span data-ttu-id="66ac3-185">注意：雲端 App 安全性即將推出的屬性包含 Office 365 敏感資訊類型，以及 Office 365 與 Azure 資訊保護中的統一標籤。</span><span class="sxs-lookup"><span data-stu-id="66ac3-185">Note: Attributes coming soon to Cloud App Security include Office 365 sensitive information types and Unified labels across Office 365 and Azure Information Protection.</span></span></td>
</tr>
</tbody>
</table>

## <a name="prioritize-auto-apply-label-policies"></a><span data-ttu-id="66ac3-186">指定自動套用標籤原則的優先順序</span><span class="sxs-lookup"><span data-stu-id="66ac3-186">Prioritize auto-apply label policies</span></span>

<span data-ttu-id="66ac3-p118">對於受到 GDPR 約束的個人資料，Microsoft 建議利用您為環境策劃的敏感資訊類型來自動套用標籤。請務必妥善地設計並測試自動套用標籤原則，以確保發生預期的行為。</span><span class="sxs-lookup"><span data-stu-id="66ac3-p118">For personal data that is subject to GDPR, Microsoft recommends auto-applying labels by using the sensitive information types you curated for your environment. It is important that auto-apply label policies are well designed and tested to ensure the intended behavior occurs.</span></span>

<span data-ttu-id="66ac3-p119">建立自動套用原則的順序，以及使用者是否也套用這些標籤會影響結果。因此，仔細做好推出計劃很重要。以下是您需要知道的。</span><span class="sxs-lookup"><span data-stu-id="66ac3-p119">The order that auto-apply policies are created and whether users are also applying these labels affect the result. So, it is important to carefully plan the roll-out. Here’s what you need to know.</span></span>

### <a name="one-label-at-a-time"></a><span data-ttu-id="66ac3-191">一次一個標籤</span><span class="sxs-lookup"><span data-stu-id="66ac3-191">One label at a time</span></span>

<span data-ttu-id="66ac3-192">您只能將一個標籤指派給一個文件。</span><span class="sxs-lookup"><span data-stu-id="66ac3-192">You can only assign one label to a document.</span></span>

### <a name="older-auto-apply-policies-win"></a><span data-ttu-id="66ac3-193">越舊的自動套用原則越優先採用</span><span class="sxs-lookup"><span data-stu-id="66ac3-193">Older auto-apply policies win</span></span>

<span data-ttu-id="66ac3-p120">如果有多個指派自動套用標籤的項規，且內容符合多個規則的條件，則會指派最舊規則的標籤。基於這個原因，請務必審慎規劃標籤原則，然後再設定它們。如果組織要求變更標籤原則的優先順序，您需要先刪除它們，然後重新建立。</span><span class="sxs-lookup"><span data-stu-id="66ac3-p120">If there are multiple rules that assign an auto-apply label and content meets the conditions of multiple rules, the label for the oldest rule is assigned. For this reason, it is important to plan the label policies carefully before configuring them. If an organization requires a change to the priority of the label policies, they will need to delete and recreate them.</span></span>

### <a name="manual-user-applied-labels-trump-auto-applied-labels"></a><span data-ttu-id="66ac3-197">手動使用者套用標籤優先於自動套用標籤</span><span class="sxs-lookup"><span data-stu-id="66ac3-197">Manual user-applied labels trump auto-applied labels</span></span>

<span data-ttu-id="66ac3-p121">手動使用者套用標籤優先於自動套用標籤。自動套用原則無法取代已由使用者套用的標籤。使用者可以取代自動套用的標籤。</span><span class="sxs-lookup"><span data-stu-id="66ac3-p121">Manual user applied labels trump auto-applied labels. Auto-apply policies cannot replace a label that is already applied by a user. Users can replace labels that are auto-applied.</span></span>

### <a name="auto-assigned-labels-can-be-updated"></a><span data-ttu-id="66ac3-201">可以更新自動指派的標籤</span><span class="sxs-lookup"><span data-stu-id="66ac3-201">Auto-assigned labels can be updated</span></span>

<span data-ttu-id="66ac3-202">更新的標籤原則或現有原則的更新，可以更新自動指派的標籤。</span><span class="sxs-lookup"><span data-stu-id="66ac3-202">Auto-assigned labels can be updated by either newer label policies or by updates to existing policies.</span></span>

<span data-ttu-id="66ac3-203">請確定實作標籤的計劃包括：</span><span class="sxs-lookup"><span data-stu-id="66ac3-203">Be sure your plan for implementing labels includes:</span></span>

-   <span data-ttu-id="66ac3-204">指定建立自動套用原則的優先順序。</span><span class="sxs-lookup"><span data-stu-id="66ac3-204">Prioritizing the order that auto-apply policies are created.</span></span>

-   <span data-ttu-id="66ac3-p122">在推出標籤供使用者手動套用之前，允許有足夠的時間自動套用這些標籤。最多可能需要 7 天，標籤才會套用至符合條件的所有內容。</span><span class="sxs-lookup"><span data-stu-id="66ac3-p122">Allowing enough time for labels to be automatically applied before rolling these out for users to manually apply. It can take up to seven days for the labels to be applied to all content that matches the conditions.</span></span>

### <a name="example-priority-for-creating-the-auto-apply-policies"></a><span data-ttu-id="66ac3-207">建立自動套用原則的優先順序範例</span><span class="sxs-lookup"><span data-stu-id="66ac3-207">Example priority for creating the auto-apply policies</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="66ac3-208"><strong>標籤</strong></span><span class="sxs-lookup"><span data-stu-id="66ac3-208"><strong>Labels</strong></span></span></th>
<th align="left"><span data-ttu-id="66ac3-209"><strong>建立自動套用原則的優先順序</strong></span><span class="sxs-lookup"><span data-stu-id="66ac3-209"><strong>Priority order to create auto-apply policies</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="66ac3-210">人力資源 — 員工資料</span><span class="sxs-lookup"><span data-stu-id="66ac3-210">Human Resources — Employee Data</span></span></td>
<td align="left"><span data-ttu-id="66ac3-211">1</span><span class="sxs-lookup"><span data-stu-id="66ac3-211">1</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="66ac3-212">客戶資料</span><span class="sxs-lookup"><span data-stu-id="66ac3-212">Customer Data</span></span></td>
<td align="left"><span data-ttu-id="66ac3-213">2</span><span class="sxs-lookup"><span data-stu-id="66ac3-213">2</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="66ac3-214">高度機密</span><span class="sxs-lookup"><span data-stu-id="66ac3-214">Highly Confidential</span></span></td>
<td align="left"><span data-ttu-id="66ac3-215">3</span><span class="sxs-lookup"><span data-stu-id="66ac3-215">3</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="66ac3-216">人力資源 — 薪資資料</span><span class="sxs-lookup"><span data-stu-id="66ac3-216">Human Resources — Salary Data</span></span></td>
<td align="left"><span data-ttu-id="66ac3-217">4</span><span class="sxs-lookup"><span data-stu-id="66ac3-217">4</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="66ac3-218">機密</span><span class="sxs-lookup"><span data-stu-id="66ac3-218">Confidential</span></span></td>
<td align="left"><span data-ttu-id="66ac3-219">5</span><span class="sxs-lookup"><span data-stu-id="66ac3-219">5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="66ac3-220">公開</span><span class="sxs-lookup"><span data-stu-id="66ac3-220">Public</span></span></td>
<td align="left"><span data-ttu-id="66ac3-221">6</span><span class="sxs-lookup"><span data-stu-id="66ac3-221">6</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="66ac3-222">個人</span><span class="sxs-lookup"><span data-stu-id="66ac3-222">Personal</span></span></td>
<td align="left"><span data-ttu-id="66ac3-223">沒有自動套用原則</span><span class="sxs-lookup"><span data-stu-id="66ac3-223">No auto-apply policy</span></span></td>
</tr>
</tbody>
</table>

## <a name="create-labels-and-auto-apply-label-policies"></a><span data-ttu-id="66ac3-224">建立標籤和自動套用標籤原則</span><span class="sxs-lookup"><span data-stu-id="66ac3-224">Create labels and auto-apply label policies</span></span>

<span data-ttu-id="66ac3-225">在安全性與合規性中心建立標籤和原則。</span><span class="sxs-lookup"><span data-stu-id="66ac3-225">Create labels and policies in the Security & Compliance Center.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="66ac3-226"><strong>步驟</strong></span><span class="sxs-lookup"><span data-stu-id="66ac3-226"><strong>Step</strong></span></span></th>
<th align="left"><span data-ttu-id="66ac3-227"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="66ac3-227"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="66ac3-228">將權限授與規範小組的成員。</span><span class="sxs-lookup"><span data-stu-id="66ac3-228">Give permissions to members of your compliance team.</span></span></p></td>
<td align="left"><p><span data-ttu-id="66ac3-p123">要建立標籤的合規性小組成員需有有使用安全性與合規性中心的權限。請移至安全性與合規性中心的 [權限]，然後修改合規性系統管理員群組的成員。</span><span class="sxs-lookup"><span data-stu-id="66ac3-p123">Members of your compliance team who will create labels need permissions to use the Security &amp; Compliance Center. Go to Permissions in Security and Compliance Center and modify the members of the Compliance Administrator group.</span></span></p>
<p><span data-ttu-id="66ac3-231">請參閱<a href="https://support.office.com/en-ie/article/Give-users-access-to-the-Office-365-Security-Compliance-Center-2cfce2c8-20c5-47f9-afc4-24b059c1bd76">讓使用者能夠存取 Office 365 安全性與合規性中心</a></span><span class="sxs-lookup"><span data-stu-id="66ac3-231">See <a href="https://support.office.com/en-ie/article/Give-users-access-to-the-Office-365-Security-Compliance-Center-2cfce2c8-20c5-47f9-afc4-24b059c1bd76">Give users access to the Office 365 Security &amp; Compliance Center</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="66ac3-232">建立 Office 標籤。</span><span class="sxs-lookup"><span data-stu-id="66ac3-232">Create Office labels.</span></span></p></td>
<td align="left"><span data-ttu-id="66ac3-233">移至安全性與合規性中心中的 [分類]、選擇 [標籤]，然後建立適用於您環境的標籤。</span><span class="sxs-lookup"><span data-stu-id="66ac3-233">Go to Classifications in Security and Compliance Center, choose Labels, and create the labels for your environment.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="66ac3-234">建立標籤的自動套用原則。</span><span class="sxs-lookup"><span data-stu-id="66ac3-234">Create auto-apply policies for labels.</span></span></p></td>
<td align="left"><span data-ttu-id="66ac3-p124">移至安全性與合規性中心的 [分類]、選擇標籤原則，然後建立自動套用標籤的原則。請務必依優先順序建立這些原則。</span><span class="sxs-lookup"><span data-stu-id="66ac3-p124">Go to Classification in Security and Compliance Center, choose Label policies, and create the policies for auto-applying labels. Be sure to create these policies in the prioritized order.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="66ac3-237">下圖顯示如何為客戶資料標籤建立自動套用標籤。</span><span class="sxs-lookup"><span data-stu-id="66ac3-237">The following illustration shows how to create an auto-apply label for the Customer data label.</span></span>

![為客戶資料建立及套用標籤](Media/Apply-labels-to-personal-data-in-Office-365-image3.png)

<span data-ttu-id="66ac3-239">在此圖例中：</span><span class="sxs-lookup"><span data-stu-id="66ac3-239">In the illustration:</span></span>

-   <span data-ttu-id="66ac3-240">已建立「客戶資料」標籤。</span><span class="sxs-lookup"><span data-stu-id="66ac3-240">The “Customer data” label is created.</span></span>

-   <span data-ttu-id="66ac3-241">已列出所需的敏感資訊類型範例：比利時國民編碼、信用卡號碼、克羅埃西亞身分證號碼、芬蘭國民身分證</span><span class="sxs-lookup"><span data-stu-id="66ac3-241">The desired sensitive information types for GDPR are listed: Belgium National Number, Credit Card Number, Croatia Identity Card Number, Finland National ID.</span></span>

-   <span data-ttu-id="66ac3-242">建立自動套用原則可將標籤「客戶資料」指派給任何檔案，其中包含您新增至原則的其中一個敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="66ac3-242">Create an auto-apply policy assigns the label “Customer data” to any file that includes one of the sensitive information types that you add to the policy.</span></span>
