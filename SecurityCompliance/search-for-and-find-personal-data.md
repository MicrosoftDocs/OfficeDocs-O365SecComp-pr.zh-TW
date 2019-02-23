---
title: 搜尋並找出個人資料
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
search.appverid:
- MET150
description: 了解如何搜尋並找出 Office 365 中的個人資料。
ms.openlocfilehash: 8b9359c6daf3817b4da73d6be5a652d17d19549b
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223552"
---
# <a name="search-for-and-find-personal-data"></a>搜尋並找出個人資料

在 GDPR 下，個人資料廣泛地定義為與已識別或可識別之自然人員 (即歐盟 (EU) 居民) 相關的任何資料。

文章 4 – 定義

> 「個人資料」表示與已識別或可識別之自然人 (資料主旨) 相關的任何資訊。可識別的自然人是可以直接或間接識別的人員，尤其藉由參照識別碼來識別，例如名稱、身分證號碼、位置資料、線上識別碼，或特定於該自然人的身體、生理、基因、心理、經濟、文化或社會身份的一個或多個因素；

本文示範如何找出 SharePoint 和商務用 OneDrive (其中包含所有 Office 365 群組和 Microsoft Teams 的網站) 中儲存的個人資料。

尋找受制於 GDPR 的個人資料，依賴使用 Office 365 中的敏感資訊類型。這些定義自動化程序如何辨識特定資訊類型，例如健康服務號碼和信用卡號碼。此時，這些無法用來在 Exchange 靜態信箱中尋找資料。不過，敏感資訊類型可與資料外洩防護原則搭配使用，以在傳輸時尋找郵件中的個人資料。

因此，目前無法使用內容搜尋，在 Exchange Online 信箱中尋找靜態個人資料，而您可以使用針對 GDPR 策劃的機密資訊類型，在個人資訊透過電子郵件傳送時，尋找並保護個人資訊。

## <a name="use-content-search-to-find-personal-data"></a>使用內容搜尋來尋找個人資料

Microsoft 建議三階段方法，來尋找 Office 365 中的個人資料。本主題的其餘部分提供其中每一個階段的指引。

<table>
<thead>
<tr class="header">
<th align="left"><strong>步驟</strong></th>
<th align="left"><strong>描述</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>1. 搜尋敏感資訊類型</p></td>
<td align="left"><p>首先，使用敏感資訊類型來尋找個人資料。為每一個敏感資訊類型建立內容搜尋查詢。執行查詢，然後分析結果。</p>
如有需要，新增參數至查詢，以降低誤判： <li>計數範圍</li>
    <li>信賴範圍</li>
    <li>更複雜查詢的其他屬性或運算子</li>
<p>如有需要，修改敏感資訊類型，以提高組織的精確度：</p>
<p><li>直接在 XML 中調整信賴等級。</li></p>
<p><li>新增關鍵字。</li></p>
<p><li>調整關鍵字的鄰近性需求。</li></p></td>
</tr>
<tr class="even">
<td align="left"><p>2. 使用關鍵字查詢語言 (KQL) 以在環境中尋找其他個人資料</p></td>
<td align="left"><p>若要尋找敏感資訊類型中未包含的資料，請使用 KQL 查詢語言來開發自訂查詢。</p>
<p>測試這些搜尋的結果，並調整 KQL 查詢字串，直到您得到預期的結果。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>3. 使用 KQL 查詢來建立新的自訂敏感資訊類型</p></td>
<td align="left">在最佳化 KQL 查詢以找出目標資料之後，請使用這些查詢來建立新的自訂敏感資訊類型。然後，您可以在 DLP 原則和其他工具中，以及在其他 KQL 查詢內，使用這些自訂的敏感資訊類型來搭配「內容搜尋」。</td>
</tr>
</tbody>
</table>

即將推出 — 您將能夠在安全性與合規性中心的新使用者介面中建立及修改敏感資訊類型。您可以動態查看相符結果，並調整敏感資訊類型以符合您的需求。

## <a name="search-for-sensitive-information-types-using-content-search"></a>使用內容搜尋來搜尋敏感資訊類型

開始使用隨附於 Office 365 的敏感資訊類型搜尋個人資料。這些類型列示於安全性與合規性中心的 [分類] 之下。

本主題包含一個清單，列出目前適用於歐盟公民的敏感資訊類型。請使用這些類型做為起點。經常檢查安全性與合規性中心，以取得有助於符合 GDPR 合規性的新增項目。

另請參閱這篇文章：[敏感資訊類型的清單和每一種敏感資訊類型的樣子](https://support.office.com/zh-TW/article/What-the-sensitive-information-types-look-for-fd505979-76be-4d9f-b459-abef3fc9e86b)。

敏感資訊類型定義自動化程序如何辨識特定資訊類型，例如銀行帳號、健康服務號碼和信用卡號碼。敏感資訊類型也稱為條件。敏感資訊類型由規則運算式或函數所能識別的模式來定義。此外，也可使用關鍵字和總和檢查碼之類的佐證來識別敏感資訊類型。評估程序中也會使用信賴等級和鄰近性。

此時機密資訊類型無法在信箱中尋找靜態資料。

### <a name="using-content-search-with-sensitive-information-types"></a>使用內容搜尋搭配敏感資訊類型

<table>
<thead>
<tr class="header">
<th align="left"><strong>步驟</strong></th>
<th align="left"><strong>詳細資訊</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd"><td align="left"><p>移至安全性與合規性中心的內容搜尋</p></td>
<td align="left"><p>在安全性與合規性中心的左窗格中，按一下 [搜尋與調查]**** &gt; [內容搜尋]****。</p>
<p>請參閱<a href="https://support.office.com/en-us/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a">在 Office 365 安全性與合規性中心執行內容搜尋</a>。</p></td>
</tr>
<tr class="even">
<td align="left"><p>為每一種敏感資訊類型建立新的搜尋項目</p></td>
<td align="left"><p>請使用下列語法：</p>
<blockquote>
<p>SensitiveType:”&lt;type&gt;”</p>
</blockquote>
<p>例如：</p>
<blockquote>
<p>SensitiveType:&quot;France Passport Number&quot;</p>
</blockquote>
<p>限定 SharePoint (包括商務用 OneDrive) 的搜尋範圍。請確定語法完全正確，而且沒有多餘的空格或錯字。</p>
<p>請參閱<a href="https://support.office.com/zh-TW/article/Form-a-query-to-find-sensitive-data-stored-on-sites-3019fbc5-7f15-4972-8d0e-dc182dc7f836">形成查詢以搜尋儲存在網站上的敏感資料</a>。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>檢閱每個搜尋的結果</p></td>
<td align="left"><p>尋找這些類型的問題來判斷查詢目標是否精確：</p>
<p><li>許多誤判</li></p>
<p><li>缺少已知的資料執行個體</li></p>
<p>請參閱<a href="https://support.office.com/en-us/article/Export-Content-Search-results-from-the-Office-365-Security-Compliance-Center-ed48d448-3714-4c42-85f5-10f75f6a4278">從 Office 365 安全性與合規性中心匯出搜尋結果</a>。</p>
<p>注意：如果您是使用 Mozilla Firefox 或 Chrome，則可能需要先使用 Internet Explorer 或 Edge 下載報告，才能安裝所需的增益集。</p></td>
</tr>
</tbody>
</table>

## <a name="sensitive-information-types-for-eu-citizen-data"></a>歐盟公民資料的敏感資訊類型

開始使用這些敏感資訊類型。不久將對歐盟國家中的個人資料推出許多更敏感資訊類型。

> 比利時國民編碼
>
> 信用卡號碼
>
> 克羅埃西亞身分證號碼
>
> 克羅埃西亞個人識別 (OIB) 碼
>
> 捷克國民身分證號碼
>
> 丹麥個人識別碼
>
> 歐盟轉帳卡號碼
>
> 芬蘭國民身分證
>
> 芬蘭護照號碼
>
> 法國駕照編號
>
> 法國國民身分證 (CNI)
>
> 法國護照號碼
>
> 法國社會安全號碼 (INSEE)
>
> 德國駕照號碼
>
> 德國身分證號碼
>
> 德國護照號碼
>
> 希臘國民身分證
>
> 國際銀行帳號 (IBAN)
>
> IP 位址
>
> 愛爾蘭個人公用服務 (PPS) 號碼
>
> 義大利駕照號碼
>
> 荷蘭公民服務 (BSN) 號碼
>
> 挪威身分識別號碼
>
> 波蘭身分證明卡
>
> 波蘭國民身分證 (PESEL)
>
> 波蘭護照
>
> 葡萄牙公民證號碼
>
> 西班牙社會安全號碼 (SSN)
>
> 瑞典國民身分證號
>
> 瑞典護照號碼
>
> 英國駕照號碼
>
> 英國選民名冊編號
>
> 英國國民健保服務號碼
>
> 英國國民保險號碼 (NINO)
>
> 美國/英國護照號碼

## <a name="add-parameters-to-a-sensitive-information-type-query-to-hone-the-results"></a>將參數新增至敏感資訊類型查詢來調整結果

您可以將這些參數新增至敏感資訊類型查詢：

-   Count range — 在納入查詢結果之前，定義文件需要包含之敏感資訊的發生次數。

-   Confidence range — 已偵測之敏感類型實際符合的信賴等級，例如 85 (85%)。

語法：

-   SensitiveType:”\<type\>|\<count range\>|\<confidence range\>”

範例：

-   SensitiveType:“Credit Card Number|5” (僅傳回確切地包含五個信用卡號碼的文件)

-   SensitiveType:“Credit Card Number|\*|85..” (信賴範圍為 85% 或更高)

注意：“SensitiveType” 會區分大小寫，但查詢的其餘部分不會。

您也可以使用屬性和運算子來說明您如何修改查詢。如需詳細資訊和範例，請參閱[形成查詢以搜尋儲存在網站上的敏感資料](https://support.office.com/zh-TW/article/Form-a-query-to-find-sensitive-data-stored-on-sites-3019fbc5-7f15-4972-8d0e-dc182dc7f836)。
