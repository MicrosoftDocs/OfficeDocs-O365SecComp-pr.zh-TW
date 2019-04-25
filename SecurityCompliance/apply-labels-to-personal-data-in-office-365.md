---
title: 將標籤套用至 Office 365 中的個人資料
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: ''
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
description: 了解如何使用 Office 標籤做為 GDPR 保護計劃的一部分。
ms.openlocfilehash: a5ffcca94ea98a3d6426dc60fae0f6cb98d0029d
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32244153"
---
# <a name="apply-labels-to-personal-data-in-office-365"></a><span data-ttu-id="58439-103">將標籤套用至 Office 365 中的個人資料</span><span class="sxs-lookup"><span data-stu-id="58439-103">Apply labels to personal data in Office 365</span></span>

 <span data-ttu-id="58439-104">如果您使用分類標籤做為 GDPR 保護計劃的一部分，請使用本主題。</span><span class="sxs-lookup"><span data-stu-id="58439-104">Use this topic if you are using classification labels as part of your GDPR protection plan.</span></span> 

<span data-ttu-id="58439-105">如果您使用標籤來保護 Office 365 中的個人資料，Microsoft 建議從使用[保留標籤](labels.md)開始。</span><span class="sxs-lookup"><span data-stu-id="58439-105">If you are using labels for protection of personal data in Office 365, Microsoft recommends you start with [retention labels](labels.md).</span></span> <span data-ttu-id="58439-106">使用保留標籤，您可以：</span><span class="sxs-lookup"><span data-stu-id="58439-106">With retention labels, you can:</span></span>
- <span data-ttu-id="58439-107">使用「進階資料控管」，根據敏感性資訊類型或其他準則自動套用標籤。</span><span class="sxs-lookup"><span data-stu-id="58439-107">Use Advanced Data Governance to automatically apply labels based on sensitive information types or other criteria.</span></span>
- <span data-ttu-id="58439-108">使用保留標籤搭配資料外洩防護來套用保護。</span><span class="sxs-lookup"><span data-stu-id="58439-108">Use retention labels with data loss prevention to apply protection.</span></span> 
- <span data-ttu-id="58439-109">使用標籤搭配電子文件探索和內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="58439-109">Use labels with eDiscovery and Content Search.</span></span> 

<span data-ttu-id="58439-110">雲端 App 安全性目前不支援保留標籤，但是您可以使用 Office 365 敏感資訊類型搭配雲端 App 安全性，監視位於其他 SaaS 應用程式中的個人資料。</span><span class="sxs-lookup"><span data-stu-id="58439-110">Cloud App Security doesn't currently support retention labels, but you can use Office 365 sensitive information types with Cloud App Security to monitor personal data that resides in other SaaS apps.</span></span>

<span data-ttu-id="58439-111">目前建議使用[敏感度標籤](sensitivity-labels.md)，將標籤套用至內部部署與其他雲端服務和提供者中的檔案。</span><span class="sxs-lookup"><span data-stu-id="58439-111">[Sensitivity labels](sensitivity-labels.md) are currently recommended for applying labels to files on premises and in other cloud services and providers.</span></span> <span data-ttu-id="58439-112">也有對於 Office 365 中需要使用 Azure 資訊保護加密進行資料保護的檔案 (例如商業秘密檔案) 所建議的事項。</span><span class="sxs-lookup"><span data-stu-id="58439-112">These are also recommended for files in Office 365 that require Azure Information Protection (AIP) encryption for data protection, such as trade secret files.</span></span>

<span data-ttu-id="58439-113">目前，對於 Office 365 中具有、受限於 GDPR 資料的檔案，不建議使用 Azure 資訊保護來套用加密。</span><span class="sxs-lookup"><span data-stu-id="58439-113">At this time, using Azure Information Protection to apply encryption is not recommended for files in Office 365 with data that is subject to the GDPR.</span></span> <span data-ttu-id="58439-114">Office 365 服務目前無法讀取使用 AIP 加密的檔案。</span><span class="sxs-lookup"><span data-stu-id="58439-114">Office 365 services currently cannot read into AIP-encrypted files.</span></span> <span data-ttu-id="58439-115">因此，服務找不到這些檔案中的敏感性資料。</span><span class="sxs-lookup"><span data-stu-id="58439-115">Therefore, the service can’t find sensitive data in these files.</span></span>

<span data-ttu-id="58439-116">您可對 Exchange Online 中的郵件套用保留標籤，而這些標籤可搭配 Office 365 資料外洩防護使用。</span><span class="sxs-lookup"><span data-stu-id="58439-116">Retention labels can be applied to mail in Exchange Online and these labels work with Office 365 data loss prevention.</span></span> 

![Office 365 標籤和 Azure 資訊保護標籤](Media/Apply-labels-to-personal-data-in-Office-365-image1.png)


<span data-ttu-id="58439-118">在此圖例中：</span><span class="sxs-lookup"><span data-stu-id="58439-118">In the illustration:</span></span>

-   <span data-ttu-id="58439-119">將保留標籤用於個人資料，以及 SharePoint Online 和商務用 OneDrive 中高度管制的商業機密檔案。</span><span class="sxs-lookup"><span data-stu-id="58439-119">Use retention labels for personal data and for highly regulated & trade secret files in SharePoint Online and OneDrive for Business.</span></span>
-   <span data-ttu-id="58439-120">Office 365 敏感性資訊類型可以用於 Office 365 之中，也可以搭配雲端 App 安全性，監視位於其他 SaaS 應用程式中的個人資料。</span><span class="sxs-lookup"><span data-stu-id="58439-120">Office 365 sensitive information types can be used within Office 365 and with Cloud App Security to monintor personal data that resides in other SaaS apps.</span></span>
-   <span data-ttu-id="58439-121">將敏感度標籤用於高度管制的商業機密檔案、Exchange Online 電子郵件、其他 SaaS 服務中的檔案、內部部署資料中心中的檔案，以及其他雲端提供者中的檔案。</span><span class="sxs-lookup"><span data-stu-id="58439-121">Use sensitivity labels for highly regulated & trade secret files, Exchange Online email, files in other SaaS services, files in on-premises datacenters, and files in other cloud providers.</span></span>


## <a name="use-retention-labels-and-sensitive-information-types-across-microsoft-365-for-information-protection"></a><span data-ttu-id="58439-122">在 Microsoft 365 間使用保留標籤和敏感性資訊類型以保護資訊</span><span class="sxs-lookup"><span data-stu-id="58439-122">Use retention labels and sensitive information types across Microsoft 365 for information protection</span></span>

<span data-ttu-id="58439-123">下圖顯示如何在標籤原則、資料外洩防護原則，以及搭配雲端 App 安全性原則使用保留標籤和敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="58439-123">The following illustration shows how retention labels and sensitive information types can be used in label policies, data loss prevention policies, and with Cloud App Security policies.</span></span>

![Office 標籤和敏感資訊類型](Media/Apply-labels-to-personal-data-in-Office-365-image2.png)

<span data-ttu-id="58439-125">為了便於存取，下表會在圖例中提供相同的範例。</span><span class="sxs-lookup"><span data-stu-id="58439-125">For accessibility, the following table provides the same examples in the illustration.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="58439-126"><strong>分類元素</strong></span><span class="sxs-lookup"><span data-stu-id="58439-126"><strong>Classification elements</strong></span></span></th>
<th align="left"><span data-ttu-id="58439-127"><strong>標籤原則 — 2 個範例</strong></span><span class="sxs-lookup"><span data-stu-id="58439-127"><strong>Label policies — 2 examples</strong></span></span></th>
<th align="left"><span data-ttu-id="58439-128"><strong>資料外洩防護原則 — 2 個範例</strong></span><span class="sxs-lookup"><span data-stu-id="58439-128"><strong>Data loss prevention policies — 2 examples</strong></span></span></th>
<th align="left"><span data-ttu-id="58439-129"><strong>所有 SaaS 應用程式的雲端 App 安全性原則 — 1 個範例</strong></span><span class="sxs-lookup"><span data-stu-id="58439-129"><strong>Cloud App Security policies for all SaaS apps — 1 example</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="58439-130">保留標籤。</span><span class="sxs-lookup"><span data-stu-id="58439-130">Retention labels.</span></span> <span data-ttu-id="58439-131">範例：個人、公用、客戶資料、HR 資料、機密、高度機密</span><span class="sxs-lookup"><span data-stu-id="58439-131">Examples: Personal, Public, Customer data, HR data, Confidential, Highly confidential</span></span></td>
<td align="left"><p><span data-ttu-id="58439-p105">自動套用此標籤 . . .</span><span class="sxs-lookup"><span data-stu-id="58439-p105">Auto apply this label . . .</span></span></p>
<p><span data-ttu-id="58439-135">客戶資料</span><span class="sxs-lookup"><span data-stu-id="58439-135">Customer data</span></span></p>
<p><span data-ttu-id="58439-p106">. . . 至符合這些敏感資訊類型的文件 . . .</span><span class="sxs-lookup"><span data-stu-id="58439-p106">. . . to documents that match these sensitive information types . . .</span></span></p>
<p><span data-ttu-id="58439-142">&lt;敏感資訊類型範例的清單&gt;</span><span class="sxs-lookup"><span data-stu-id="58439-142">&lt;list of example sensitive information types&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="58439-p107">套用此保護 . . .</span><span class="sxs-lookup"><span data-stu-id="58439-p107">Apply this protection . . .</span></span></p>
<p><span data-ttu-id="58439-146">&lt;定義保護&gt;</span><span class="sxs-lookup"><span data-stu-id="58439-146">&lt;define protection&gt;</span></span></p>
<p><span data-ttu-id="58439-p108">. . . 至具有此標籤的文件 . . .</span><span class="sxs-lookup"><span data-stu-id="58439-p108">. . . to documents with this label . . .</span></span></p>
<p><span data-ttu-id="58439-153">客戶資料</span><span class="sxs-lookup"><span data-stu-id="58439-153">Customer data</span></span></p></td>
<td align="left"><p><span data-ttu-id="58439-p109">在任何獲批准的 SaaS App 中具有這些屬性的檔案 . . .</span><span class="sxs-lookup"><span data-stu-id="58439-p109">Alert when files with these attributes . . .</span></span></p>
<p><span data-ttu-id="58439-157">選擇一或多個屬性：預先定義的 PII 屬性、Office 365 機密資訊類型、敏感度標籤 (AIP)、自訂運算式</span><span class="sxs-lookup"><span data-stu-id="58439-157">Choose one or more attribute: predefined PII attribute, Office 365 sensitive information type, sensitivity label (AIP), custom expression</span></span></p>
<p><span data-ttu-id="58439-158">。</span><span class="sxs-lookup"><span data-stu-id="58439-158">.</span></span> <span data-ttu-id="58439-159">。</span><span class="sxs-lookup"><span data-stu-id="58439-159">.</span></span> <span data-ttu-id="58439-160">。</span><span class="sxs-lookup"><span data-stu-id="58439-160">.</span></span> <span data-ttu-id="58439-161">在組織外共用時發出警示</span><span class="sxs-lookup"><span data-stu-id="58439-161">in any sanctioned SaaS app are shared outside the organization</span></span></p><p><span data-ttu-id="58439-162">附註：雲端 App 安全性目前不支援保留標籤。</span><span class="sxs-lookup"><span data-stu-id="58439-162">Note: Retention labels are currently not supported in Cloud App Security.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="58439-p111">敏感資訊類型範例：比利時國民編碼、信用卡號碼、克羅埃西亞身分證號碼、芬蘭國民身分證</span><span class="sxs-lookup"><span data-stu-id="58439-p111">Sensitive information types. Examples: Belgium National Number, Credit Card Number, Croatia Identity Cart Number, Finland National ID</span></span></td>
<td align="left"><p><span data-ttu-id="58439-p112">發佈這些使用者的這些標籤以手動套用 . . .</span><span class="sxs-lookup"><span data-stu-id="58439-p112">Publish these labels for users to manually apply . . .</span></span></p>
<p><span data-ttu-id="58439-168">&lt;選取標籤&gt;</span><span class="sxs-lookup"><span data-stu-id="58439-168">&lt;select labels&gt;</span></span></p>
<p><span data-ttu-id="58439-p113">. . . 至這些位置 . . .</span><span class="sxs-lookup"><span data-stu-id="58439-p113">. . . to these locations . . .</span></span></p>
<p><span data-ttu-id="58439-175">&lt;所有位置或選擇特定位置&gt;</span><span class="sxs-lookup"><span data-stu-id="58439-175">&lt;all locations or choose specific locations&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="58439-p114">套用此保護 . . .</span><span class="sxs-lookup"><span data-stu-id="58439-p114">Apply this protection . . .</span></span></p>
<p><span data-ttu-id="58439-179">&lt;定義保護&gt;</span><span class="sxs-lookup"><span data-stu-id="58439-179">&lt;define protection&gt;</span></span></p>
<p><span data-ttu-id="58439-p115">. . . 至符合這些敏感資訊類型的文件&gt;</span><span class="sxs-lookup"><span data-stu-id="58439-p115">. . . to documents that match these sensitive information types&gt;</span></span></p></td>
<td align="left"></td>
</tr>
</tbody>
</table>

## <a name="prioritize-auto-apply-label-policies"></a><span data-ttu-id="58439-184">指定自動套用標籤原則的優先順序</span><span class="sxs-lookup"><span data-stu-id="58439-184">Prioritize auto-apply label policies</span></span>

<span data-ttu-id="58439-p116">對於受到 GDPR 約束的個人資料，Microsoft 建議利用您為環境策劃的敏感資訊類型來自動套用標籤。請務必妥善地設計並測試自動套用標籤原則，以確保發生預期的行為。</span><span class="sxs-lookup"><span data-stu-id="58439-p116">For personal data that is subject to GDPR, Microsoft recommends auto-applying labels by using the sensitive information types you curated for your environment. It is important that auto-apply label policies are well designed and tested to ensure the intended behavior occurs.</span></span>

<span data-ttu-id="58439-p117">建立自動套用原則的順序，以及使用者是否也套用這些標籤會影響結果。因此，仔細做好推出計劃很重要。以下是您需要知道的。</span><span class="sxs-lookup"><span data-stu-id="58439-p117">The order that auto-apply policies are created and whether users are also applying these labels affect the result. So, it is important to carefully plan the roll-out. Here’s what you need to know.</span></span>

### <a name="one-label-at-a-time"></a><span data-ttu-id="58439-189">一次一個標籤</span><span class="sxs-lookup"><span data-stu-id="58439-189">One label at a time</span></span>

<span data-ttu-id="58439-190">您只能將一個標籤指派給一個文件。</span><span class="sxs-lookup"><span data-stu-id="58439-190">You can only assign one label to a document.</span></span>

### <a name="older-auto-apply-policies-win"></a><span data-ttu-id="58439-191">越舊的自動套用原則越優先採用</span><span class="sxs-lookup"><span data-stu-id="58439-191">Older auto-apply policies win</span></span>

<span data-ttu-id="58439-p118">如果有多個指派自動套用標籤的項規，且內容符合多個規則的條件，則會指派最舊規則的標籤。基於這個原因，請務必審慎規劃標籤原則，然後再設定它們。如果組織要求變更標籤原則的優先順序，您需要先刪除它們，然後重新建立。</span><span class="sxs-lookup"><span data-stu-id="58439-p118">If there are multiple rules that assign an auto-apply label and content meets the conditions of multiple rules, the label for the oldest rule is assigned. For this reason, it is important to plan the label policies carefully before configuring them. If an organization requires a change to the priority of the label policies, they will need to delete and recreate them.</span></span>

### <a name="manual-user-applied-labels-trump-auto-applied-labels"></a><span data-ttu-id="58439-195">手動使用者套用標籤優先於自動套用標籤</span><span class="sxs-lookup"><span data-stu-id="58439-195">Manual user-applied labels trump auto-applied labels</span></span>

<span data-ttu-id="58439-p119">手動使用者套用標籤優先於自動套用標籤。自動套用原則無法取代已由使用者套用的標籤。使用者可以取代自動套用的標籤。</span><span class="sxs-lookup"><span data-stu-id="58439-p119">Manual user applied labels trump auto-applied labels. Auto-apply policies cannot replace a label that is already applied by a user. Users can replace labels that are auto-applied.</span></span>

### <a name="auto-assigned-labels-can-be-updated"></a><span data-ttu-id="58439-199">可以更新自動指派的標籤</span><span class="sxs-lookup"><span data-stu-id="58439-199">Auto-assigned labels can be updated</span></span>

<span data-ttu-id="58439-200">更新的標籤原則或現有原則的更新，可以更新自動指派的標籤。</span><span class="sxs-lookup"><span data-stu-id="58439-200">Auto-assigned labels can be updated by either newer label policies or by updates to existing policies.</span></span>

<span data-ttu-id="58439-201">請確定實作標籤的計劃包括：</span><span class="sxs-lookup"><span data-stu-id="58439-201">Be sure your plan for implementing labels includes:</span></span>

-   <span data-ttu-id="58439-202">指定建立自動套用原則的優先順序。</span><span class="sxs-lookup"><span data-stu-id="58439-202">Prioritizing the order that auto-apply policies are created.</span></span>

-   <span data-ttu-id="58439-p120">在推出標籤供使用者手動套用之前，允許有足夠的時間自動套用這些標籤。最多可能需要 7 天，標籤才會套用至符合條件的所有內容。</span><span class="sxs-lookup"><span data-stu-id="58439-p120">Allowing enough time for labels to be automatically applied before rolling these out for users to manually apply. It can take up to seven days for the labels to be applied to all content that matches the conditions.</span></span>

### <a name="example-priority-for-creating-the-auto-apply-policies"></a><span data-ttu-id="58439-205">建立自動套用原則的優先順序範例</span><span class="sxs-lookup"><span data-stu-id="58439-205">Example priority for creating the auto-apply policies</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="58439-206"><strong>標籤</strong></span><span class="sxs-lookup"><span data-stu-id="58439-206"><strong>Labels</strong></span></span></th>
<th align="left"><span data-ttu-id="58439-207"><strong>建立自動套用原則的優先順序</strong></span><span class="sxs-lookup"><span data-stu-id="58439-207"><strong>Priority order to create auto-apply policies</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="58439-208">人力資源 — 員工資料</span><span class="sxs-lookup"><span data-stu-id="58439-208">Human Resources — Employee Data</span></span></td>
<td align="left"><span data-ttu-id="58439-209">1</span><span class="sxs-lookup"><span data-stu-id="58439-209">1</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="58439-210">客戶資料</span><span class="sxs-lookup"><span data-stu-id="58439-210">Customer Data</span></span></td>
<td align="left"><span data-ttu-id="58439-211">2</span><span class="sxs-lookup"><span data-stu-id="58439-211">2</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="58439-212">高度機密</span><span class="sxs-lookup"><span data-stu-id="58439-212">Highly Confidential</span></span></td>
<td align="left"><span data-ttu-id="58439-213">3</span><span class="sxs-lookup"><span data-stu-id="58439-213">3</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="58439-214">人力資源 — 薪資資料</span><span class="sxs-lookup"><span data-stu-id="58439-214">Human Resources — Salary Data</span></span></td>
<td align="left"><span data-ttu-id="58439-215">4</span><span class="sxs-lookup"><span data-stu-id="58439-215">4</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="58439-216">機密</span><span class="sxs-lookup"><span data-stu-id="58439-216">Confidential</span></span></td>
<td align="left"><span data-ttu-id="58439-217">5</span><span class="sxs-lookup"><span data-stu-id="58439-217">5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="58439-218">公開</span><span class="sxs-lookup"><span data-stu-id="58439-218">Public</span></span></td>
<td align="left"><span data-ttu-id="58439-219">6</span><span class="sxs-lookup"><span data-stu-id="58439-219">6</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="58439-220">個人</span><span class="sxs-lookup"><span data-stu-id="58439-220">Personal</span></span></td>
<td align="left"><span data-ttu-id="58439-221">沒有自動套用原則</span><span class="sxs-lookup"><span data-stu-id="58439-221">No auto-apply policy</span></span></td>
</tr>
</tbody>
</table>

## <a name="create-labels-and-auto-apply-label-policies"></a><span data-ttu-id="58439-222">建立標籤和自動套用標籤原則</span><span class="sxs-lookup"><span data-stu-id="58439-222">Create labels and auto-apply label policies</span></span>

<span data-ttu-id="58439-223">在安全性中心或合規性中心中建立標籤和原則。</span><span class="sxs-lookup"><span data-stu-id="58439-223">Create labels and policies in the scurity center or the compliance center.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="58439-224"><strong>步驟</strong></span><span class="sxs-lookup"><span data-stu-id="58439-224"><strong>Step</strong></span></span></th>
<th align="left"><span data-ttu-id="58439-225"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="58439-225"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="58439-226">將權限授與規範小組的成員。</span><span class="sxs-lookup"><span data-stu-id="58439-226">Give permissions to members of your compliance team.</span></span></p></td>
<td align="left"><p><span data-ttu-id="58439-p121">要建立標籤的合規性小組成員需有使用安全性中心和/或合規性中心的權限。請移至安全性中心或合規性中心的 [權限]，然後修改合規性系統管理員群組的成員。</span><span class="sxs-lookup"><span data-stu-id="58439-p121">Members of your compliance team who will create labels need permissions to use the security center and/or the compliance center. Go to Permissions in the security center or the compliance center and modify the members of the Compliance Administrator group.</span></span></p>
<p><span data-ttu-id="58439-229">請參閱<a href="https://support.office.com/en-ie/article/Give-users-access-to-the-Office-365-Security-Compliance-Center-2cfce2c8-20c5-47f9-afc4-24b059c1bd76">讓使用者能夠存取安全性中心和/或合規性中心</a>。</span><span class="sxs-lookup"><span data-stu-id="58439-229">See <a href="https://support.office.com/en-ie/article/Give-users-access-to-the-Office-365-Security-Compliance-Center-2cfce2c8-20c5-47f9-afc4-24b059c1bd76">Give users access to the security center and/or the compliance center</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="58439-230">建立保留標籤。</span><span class="sxs-lookup"><span data-stu-id="58439-230">Create retention labels.</span></span></p></td>
<td align="left"><span data-ttu-id="58439-231">移至安全性中心或合規性中心中的 [分類]，選擇 [保留] 標籤，然後建立適用於您環境的標籤。</span><span class="sxs-lookup"><span data-stu-id="58439-231">Go to Classifications in the Security center or the Compliance center, choose Retention labels, and create the labels for your environment.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="58439-232">建立標籤的自動套用原則。</span><span class="sxs-lookup"><span data-stu-id="58439-232">Create auto-apply policies for labels.</span></span></p></td>
<td align="left"><span data-ttu-id="58439-p122">移至安全性中心或合規性中心中的 [分類]，選擇 [標籤原則]，然後建立自動套用標籤的原則。請務必依優先順序建立這些原則。</span><span class="sxs-lookup"><span data-stu-id="58439-p122">Go to Classification in security center or the compliance center, choose Label policies, and create the policies for auto-applying labels. Be sure to create these policies in the prioritized order.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="58439-235">下圖顯示如何為客戶資料標籤建立自動套用標籤。</span><span class="sxs-lookup"><span data-stu-id="58439-235">The following illustration shows how to create an auto-apply label for the Customer data label.</span></span>

![為客戶資料建立及套用標籤](Media/Apply-labels-to-personal-data-in-Office-365-image3.png)

<span data-ttu-id="58439-237">在此圖例中：</span><span class="sxs-lookup"><span data-stu-id="58439-237">In the illustration:</span></span>

-   <span data-ttu-id="58439-238">已建立「客戶資料」標籤。</span><span class="sxs-lookup"><span data-stu-id="58439-238">The “Customer data” label is created.</span></span>

-   <span data-ttu-id="58439-239">已列出所需的敏感資訊類型範例：比利時國民編碼、信用卡號碼、克羅埃西亞身分證號碼、芬蘭國民身分證</span><span class="sxs-lookup"><span data-stu-id="58439-239">The desired sensitive information types for GDPR are listed: Belgium National Number, Credit Card Number, Croatia Identity Card Number, Finland National ID.</span></span>

-   <span data-ttu-id="58439-240">建立自動套用原則可將標籤「客戶資料」指派給任何檔案，其中包含您新增至原則的其中一個敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="58439-240">Create an auto-apply policy assigns the label “Customer data” to any file that includes one of the sensitive information types that you add to the policy.</span></span>
