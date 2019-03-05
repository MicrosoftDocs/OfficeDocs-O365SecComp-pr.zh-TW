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
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: 了解如何使用 Office 標籤做為 GDPR 保護計劃的一部分。
ms.openlocfilehash: 9474d4b911936bca2c06c9660578790578fba4a2
ms.sourcegitcommit: 15983a08a4ae9c2050344172c7e957830ce3867e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2019
ms.locfileid: "30373894"
---
# <a name="apply-labels-to-personal-data-in-office-365"></a>將標籤套用至 Office 365 中的個人資料

 如果您使用 Office 標籤做為 GDPR 保護計劃的一部分，請使用本主題。目前可在 Office 365 安全性與合規性中心和 Azure 資訊保護中建立標籤。隨著時間的推移，這些技術將匯聚成一個統一的標籤和分類體驗，而且您將能夠達成更多的目標。

如果您是使用標籤來保護 Office 365 中的個人資料，Microsoft 建議您先建立 Office 標籤。您可以使用進階資料控管，根據敏感資訊或其他準則自動套用標籤。您可以使用 Office 標籤與資料外洩防護搭配來套用保護。您也可以使用標籤與進階電子文件探索和內容搜尋搭配。您很快就可以同時使用標籤和敏感資訊類型與 Cloud App Security 搭配，來監視位於其他 SaaS 應用程式中的個人資料。

目前建議將 Azure 資訊保護標籤套用至內部部署以及其他雲端服務和提供者中的檔案。也建議將這些標籤用於 Office 365 中需要 Microsoft Azure AD Rights Management (Azure RMS) 加密來保護資料的檔案，例如商業機密檔案。

此時，對於資料在 Office 365 中受到 GDPR 約束的檔案，建議不要使用 Azure 資訊保護來套用 Azure RMS 加密。Office 365 服務目前無法讀取 RMS 加密的檔案。因此，服務找不到檔案中的敏感資料。

Azure 資訊保護標籤可套用至 Exchange Online 中的郵件，而且這些標籤會搭配使用 Office 365 資料外洩防護。即將推出統一的分類和標記引擎，讓您能夠針對電子郵件及檔案使用相同的標籤，包括自動標記並保護傳輸中的電子郵件。

![Office 365 標籤和 Azure 資訊保護標籤](Media/Apply-labels-to-personal-data-in-Office-365-image1.png)

在此圖例中：

-   將 Office 365 標籤用於個人資料，以及 SharePoint Online 和商務用 OneDrive 中高度管制的商業機密檔案。

-   將 Azure 資訊保護 (AIP) 標籤用於高度管制的商業機密檔案、Exchange Online 電子郵件、其他 SaaS 服務中的檔案、內部部署資料中心中的檔案，以及其他雲端提供者中的檔案。

-   即將推出：這兩種類型的標籤將匯聚成統一的分類和標記體驗。

## <a name="use-office-labels-and-sensitive-information-types-across-microsoft-365-for-information-protection"></a>在整個 Microsoft 365 中使用 Office 標籤和敏感資訊類型以保護資訊

下圖顯示如何在標籤原則、資料外洩防護原則，以及搭配雲端 App 安全性原則使用 Office 標籤和敏感資訊類型。

![Office 標籤和敏感資訊類型](Media/Apply-labels-to-personal-data-in-Office-365-image2.png)

為了便於存取，下表會在圖例中提供相同的範例。

<table>
<thead>
<tr class="header">
<th align="left"><strong>分類元素</strong></th>
<th align="left"><strong>標籤原則 — 2 個範例</strong></th>
<th align="left"><strong>資料外洩防護原則 — 2 個範例</strong></th>
<th align="left"><strong>所有 SaaS 應用程式的雲端 App 安全性原則 — 1 個範例</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Office 標籤。範例：個人、公用、客戶資料、HR 資料、機密、高度機密</td>
<td align="left"><p>自動套用此標籤 . . .</p>
<p>客戶資料</p>
<p>. . . 至符合這些敏感資訊類型的文件 . . .</p>
<p>&lt;敏感資訊類型範例的清單&gt;</p></td>
<td align="left"><p>套用此保護 . . .</p>
<p>&lt;定義保護&gt;</p>
<p>. . . 至具有此標籤的文件 . . .</p>
<p>客戶資料</p></td>
<td align="left"><p>在任何獲批准的 SaaS App 中具有這些屬性的檔案 . . .</p>
<p>&lt;預先定義的 PII 屬性或自訂運算式&gt;</p>
<p>. . . 在組織外共用時發出警示</p></td>
</tr>
<tr class="even">
<td align="left">敏感資訊類型範例：比利時國民編碼、信用卡號碼、克羅埃西亞身分證號碼、芬蘭國民身分證</td>
<td align="left"><p>發佈這些使用者的這些標籤以手動套用 . . .</p>
<p>&lt;選取標籤&gt;</p>
<p>. . . 至這些位置 . . .</p>
<p>&lt;所有位置或選擇特定位置&gt;</p></td>
<td align="left"><p>套用此保護 . . .</p>
<p>&lt;定義保護&gt;</p>
<p>. . . 至符合這些敏感資訊類型的文件&gt;</p></td>
<td align="left">注意：雲端 App 安全性即將推出的屬性包含 Office 365 敏感資訊類型，以及 Office 365 與 Azure 資訊保護中的統一標籤。</td>
</tr>
</tbody>
</table>

## <a name="prioritize-auto-apply-label-policies"></a>指定自動套用標籤原則的優先順序

對於受到 GDPR 約束的個人資料，Microsoft 建議利用您為環境策劃的敏感資訊類型來自動套用標籤。請務必妥善地設計並測試自動套用標籤原則，以確保發生預期的行為。

建立自動套用原則的順序，以及使用者是否也套用這些標籤會影響結果。因此，仔細做好推出計劃很重要。以下是您需要知道的。

### <a name="one-label-at-a-time"></a>一次一個標籤

您只能將一個標籤指派給一個文件。

### <a name="older-auto-apply-policies-win"></a>越舊的自動套用原則越優先採用

如果有多個指派自動套用標籤的項規，且內容符合多個規則的條件，則會指派最舊規則的標籤。基於這個原因，請務必審慎規劃標籤原則，然後再設定它們。如果組織要求變更標籤原則的優先順序，您需要先刪除它們，然後重新建立。

### <a name="manual-user-applied-labels-trump-auto-applied-labels"></a>手動使用者套用標籤優先於自動套用標籤

手動使用者套用標籤優先於自動套用標籤。自動套用原則無法取代已由使用者套用的標籤。使用者可以取代自動套用的標籤。

### <a name="auto-assigned-labels-can-be-updated"></a>可以更新自動指派的標籤

更新的標籤原則或現有原則的更新，可以更新自動指派的標籤。

請確定實作標籤的計劃包括：

-   指定建立自動套用原則的優先順序。

-   在推出標籤供使用者手動套用之前，允許有足夠的時間自動套用這些標籤。最多可能需要 7 天，標籤才會套用至符合條件的所有內容。

### <a name="example-priority-for-creating-the-auto-apply-policies"></a>建立自動套用原則的優先順序範例

<table>
<thead>
<tr class="header">
<th align="left"><strong>標籤</strong></th>
<th align="left"><strong>建立自動套用原則的優先順序</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">人力資源 — 員工資料</td>
<td align="left">1</td>
</tr>
<tr class="even">
<td align="left">客戶資料</td>
<td align="left">2</td>
</tr>
<tr class="odd">
<td align="left">高度機密</td>
<td align="left">3</td>
</tr>
<tr class="even">
<td align="left">人力資源 — 薪資資料</td>
<td align="left">4</td>
</tr>
<tr class="odd">
<td align="left">機密</td>
<td align="left">5</td>
</tr>
<tr class="even">
<td align="left">公開</td>
<td align="left">6</td>
</tr>
<tr class="odd">
<td align="left">個人</td>
<td align="left">沒有自動套用原則</td>
</tr>
</tbody>
</table>

## <a name="create-labels-and-auto-apply-label-policies"></a>建立標籤和自動套用標籤原則

在安全性與合規性中心建立標籤和原則。

<table>
<thead>
<tr class="header">
<th align="left"><strong>步驟</strong></th>
<th align="left"><strong>描述</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>將權限授與規範小組的成員。</p></td>
<td align="left"><p>要建立標籤的合規性小組成員需有有使用安全性與合規性中心的權限。請移至安全性與合規性中心的 [權限]，然後修改合規性系統管理員群組的成員。</p>
<p>請參閱<a href="https://support.office.com/en-ie/article/Give-users-access-to-the-Office-365-Security-Compliance-Center-2cfce2c8-20c5-47f9-afc4-24b059c1bd76">讓使用者能夠存取 Office 365 安全性與合規性中心</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>建立 Office 標籤。</p></td>
<td align="left">移至安全性與合規性中心中的 [分類]、選擇 [標籤]，然後建立適用於您環境的標籤。</td>
</tr>
<tr class="odd">
<td align="left"><p>建立標籤的自動套用原則。</p></td>
<td align="left">移至安全性與合規性中心的 [分類]、選擇標籤原則，然後建立自動套用標籤的原則。請務必依優先順序建立這些原則。</td>
</tr>
</tbody>
</table>

下圖顯示如何為客戶資料標籤建立自動套用標籤。

![為客戶資料建立及套用標籤](Media/Apply-labels-to-personal-data-in-Office-365-image3.png)

在此圖例中：

-   已建立「客戶資料」標籤。

-   已列出所需的敏感資訊類型範例：比利時國民編碼、信用卡號碼、克羅埃西亞身分證號碼、芬蘭國民身分證

-   建立自動套用原則可將標籤「客戶資料」指派給任何檔案，其中包含您新增至原則的其中一個敏感資訊類型。
