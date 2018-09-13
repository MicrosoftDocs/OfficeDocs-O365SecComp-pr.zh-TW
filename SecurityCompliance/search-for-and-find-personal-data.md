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
ms.service: o365-solutions
localization_priority: Priority
search.appverid:
- MET150
ms.custom: ''
ms.assetid: ''
description: 了解如何搜尋並找出 Office 365 中的個人資料。
ms.openlocfilehash: d83e37db57443580e74b42e7b9bc89d440bf5319
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272398"
---
# <a name="search-for-and-find-personal-data"></a><span data-ttu-id="4fae8-103">搜尋並找出個人資料</span><span class="sxs-lookup"><span data-stu-id="4fae8-103">Search for and find personal data</span></span>

<span data-ttu-id="4fae8-104">在 GDPR 下，個人資料廣泛地定義為與已識別或可識別之自然人員 (即歐盟 (EU) 居民) 相關的任何資料。</span><span class="sxs-lookup"><span data-stu-id="4fae8-104">Personal data is defined very broadly under the GDPR as any data that relates to an identified or identifiable natural person that is a resident of the European Union (EU).</span></span>

<span data-ttu-id="4fae8-105">文章 4 – 定義</span><span class="sxs-lookup"><span data-stu-id="4fae8-105">Article 4 – Definitions</span></span>

> <span data-ttu-id="4fae8-106">「個人資料」表示與已識別或可識別之自然人 (資料主旨) 相關的任何資訊。可識別的自然人是可以直接或間接識別的人員，尤其藉由參照識別碼來識別，例如名稱、身分證號碼、位置資料、線上識別碼，或特定於該自然人的身體、生理、基因、心理、經濟、文化或社會身份的一個或多個因素；</span><span class="sxs-lookup"><span data-stu-id="4fae8-106">‘personal data’ means any information relating to an identified or identifiable natural person (‘data subject’); an identifiable natural person is one who can be identified, directly or indirectly, in particular by reference to an identifier such as a name, an identification number, location data, an online identifier or to one or more factors specific to the physical, physiological, genetic, mental, economic, cultural or social identity of that natural person;</span></span>

<span data-ttu-id="4fae8-107">本文示範如何找出 SharePoint 和商務用 OneDrive (其中包含所有 Office 365 群組和 Microsoft Teams 的網站) 中儲存的個人資料。</span><span class="sxs-lookup"><span data-stu-id="4fae8-107">This article demonstrates how to find personal data stored in SharePoint Online and OneDrive for Business (which includes the sites for all Office 365 groups and Microsoft Teams).</span></span>

<span data-ttu-id="4fae8-p101">尋找受制於 GDPR 的個人資料，依賴使用 Office 365 中的敏感資訊類型。這些定義自動化程序如何辨識特定資訊類型，例如健康服務號碼和信用卡號碼。此時，這些無法用來在 Exchange 靜態信箱中尋找資料。不過，敏感資訊類型可與資料外洩防護原則搭配使用，以在傳輸時尋找郵件中的個人資料。</span><span class="sxs-lookup"><span data-stu-id="4fae8-p101">Finding personal data subject to GDPR relies on using sensitive information types in Office 365. These define how the automated process recognizes specific information types such as health service numbers and credit card numbers. At this time these cannot be used to find data in Exchange mailboxes at rest. However, sensitive information types can be used with data loss prevention policies to find personal data in mail while in transit.</span></span>

<span data-ttu-id="4fae8-112">因此，目前無法使用內容搜尋，在 Exchange Online 信箱中尋找靜態個人資料，而您可以使用針對 GDPR 策劃的機密資訊類型，在個人資訊透過電子郵件傳送時，尋找並保護個人資訊。</span><span class="sxs-lookup"><span data-stu-id="4fae8-112">So, while you can’t currently use Content Search to find personal data at rest in Exchange Online mailboxes, you can use the sensitive information types you curate for GDPR to find and protect personal information as it is sent through email.</span></span>

## <a name="use-content-search-to-find-personal-data"></a><span data-ttu-id="4fae8-113">使用內容搜尋來尋找個人資料</span><span class="sxs-lookup"><span data-stu-id="4fae8-113">Use Content Search to find personal data</span></span>

<span data-ttu-id="4fae8-p102">Microsoft 建議三階段方法，來尋找 Office 365 中的個人資料。本主題的其餘部分提供其中每一個階段的指引。</span><span class="sxs-lookup"><span data-stu-id="4fae8-p102">Microsoft recommends a three-stage approach to finding personal data in Office 365. The rest of this topic provides guidance for each of these stages.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4fae8-116"><strong>步驟</strong></span><span class="sxs-lookup"><span data-stu-id="4fae8-116"><strong>Step</strong></span></span></th>
<th align="left"><span data-ttu-id="4fae8-117"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="4fae8-117"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fae8-118">1. 搜尋敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="4fae8-118">1. Search for sensitive information types</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fae8-p103">首先，使用敏感資訊類型來尋找個人資料。為每一個敏感資訊類型建立內容搜尋查詢。執行查詢，然後分析結果。</span><span class="sxs-lookup"><span data-stu-id="4fae8-p103">Start by using sensitive information types to find personal data. Create a Content Search query for each sensitive information type. Run the query and analyze the results.</span></span></p>
<span data-ttu-id="4fae8-122">如有需要，新增參數至查詢，以降低誤判：</span><span class="sxs-lookup"><span data-stu-id="4fae8-122">If needed, add parameters to the query to reduce false positives:</span></span> <li><span data-ttu-id="4fae8-123">計數範圍</span><span class="sxs-lookup"><span data-stu-id="4fae8-123">Count range</span></span></li>
    <li><span data-ttu-id="4fae8-124">信賴範圍</span><span class="sxs-lookup"><span data-stu-id="4fae8-124">Confidence range</span></span></li>
    <li><span data-ttu-id="4fae8-125">更複雜查詢的其他屬性或運算子</span><span class="sxs-lookup"><span data-stu-id="4fae8-125">Other properties or operators for more complex queries</span></span></li>
<p><span data-ttu-id="4fae8-126">如有需要，修改敏感資訊類型，以提高組織的精確度：</span><span class="sxs-lookup"><span data-stu-id="4fae8-126">If necessary, modify a sensitive information type to improve accuracy for your organization:</span></span></p>
<p><li><span data-ttu-id="4fae8-127">直接在 XML 中調整信賴等級。</span><span class="sxs-lookup"><span data-stu-id="4fae8-127">Adjust the confidence level directly in the XML.</span></span></li></p>
<p><li><span data-ttu-id="4fae8-128">新增關鍵字。</span><span class="sxs-lookup"><span data-stu-id="4fae8-128">Add key words.</span></span></li></p>
<p><li><span data-ttu-id="4fae8-129">調整關鍵字的鄰近性需求。</span><span class="sxs-lookup"><span data-stu-id="4fae8-129">Adjust the proximity requirements for keywords.</span></span></li></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4fae8-130">2. 使用關鍵字查詢語言 (KQL) 以在環境中尋找其他個人資料</span><span class="sxs-lookup"><span data-stu-id="4fae8-130">2. Use Keyword Query Language (KQL) to find additional personal data in your environment</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fae8-131">若要尋找敏感資訊類型中未包含的資料，請使用 KQL 查詢語言來開發自訂查詢。</span><span class="sxs-lookup"><span data-stu-id="4fae8-131">To find data not included in sensitive information types, use the KQL query language to develop custom queries.</span></span></p>
<p><span data-ttu-id="4fae8-132">測試這些搜尋的結果，並調整 KQL 查詢字串，直到您得到預期的結果。</span><span class="sxs-lookup"><span data-stu-id="4fae8-132">Test the results of these searches and adjust the KQL query string until you achieve the expected result.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fae8-133">3. 使用 KQL 查詢來建立新的自訂敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="4fae8-133">3. Create new custom sensitive information types using the KQL queries</span></span></p></td>
<td align="left"><span data-ttu-id="4fae8-p104">在最佳化 KQL 查詢以找出目標資料之後，請使用這些查詢來建立新的自訂敏感資訊類型。然後，您可以在 DLP 原則和其他工具中，以及在其他 KQL 查詢內，使用這些自訂的敏感資訊類型來搭配「內容搜尋」。</span><span class="sxs-lookup"><span data-stu-id="4fae8-p104">After optimizing KQL queries to find target data, create new custom sensitive information types using these queries. You can then use these custom sensitive information types with Content Search, in DLP policies and other tools, and within other KQL queries.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4fae8-p105">即將推出 — 您將能夠在安全性與合規性中心的新使用者介面中建立及修改敏感資訊類型。您可以動態查看相符結果，並調整敏感資訊類型以符合您的需求。</span><span class="sxs-lookup"><span data-stu-id="4fae8-p105">Coming soon — You'll be able to create and modify sensitive information types in a new user interface in the Security and Compliance Center. You can dynamically see matching results and tune sensitive information types to meet your needs.</span></span>

## <a name="search-for-sensitive-information-types-using-content-search"></a><span data-ttu-id="4fae8-138">使用內容搜尋來搜尋敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="4fae8-138">Search for sensitive information types using Content Search</span></span>

<span data-ttu-id="4fae8-p106">開始使用隨附於 Office 365 的敏感資訊類型搜尋個人資料。這些類型列示於安全性與合規性中心的 [分類] 之下。</span><span class="sxs-lookup"><span data-stu-id="4fae8-p106">Begin searching for personal data by using the sensitive information types that are included with Office 365. These are listed in the Security and Compliance Center under Classification.</span></span>

<span data-ttu-id="4fae8-p107">本主題包含一個清單，列出目前適用於歐盟公民的敏感資訊類型。請使用這些類型做為起點。經常檢查安全性與合規性中心，以取得有助於符合 GDPR 合規性的新增項目。</span><span class="sxs-lookup"><span data-stu-id="4fae8-p107">This topic includes a list of current sensitive information types that apply to citizens in the European Union. Use these as a starting point. Check Security and Compliance Center frequently for new additions that can help with GDPR compliance.</span></span>

<span data-ttu-id="4fae8-144">另請參閱這篇文章：[敏感資訊類型的清單和每一種敏感資訊類型的樣子](https://support.office.com/zh-TW/article/What-the-sensitive-information-types-look-for-fd505979-76be-4d9f-b459-abef3fc9e86b)。</span><span class="sxs-lookup"><span data-stu-id="4fae8-144">Also see this article: [List of sensitive information types and what each one looks for](https://support.office.com/zh-TW/article/What-the-sensitive-information-types-look-for-fd505979-76be-4d9f-b459-abef3fc9e86b).</span></span>

<span data-ttu-id="4fae8-p108">敏感資訊類型定義自動化程序如何辨識特定資訊類型，例如銀行帳號、健康服務號碼和信用卡號碼。敏感資訊類型也稱為條件。敏感資訊類型由規則運算式或函數所能識別的模式來定義。此外，也可使用關鍵字和總和檢查碼之類的佐證來識別敏感資訊類型。評估程序中也會使用信賴等級和鄰近性。</span><span class="sxs-lookup"><span data-stu-id="4fae8-p108">Sensitive information types define how the automated process recognizes specific information types such as bank account numbers, health service numbers, and credit card numbers. Sensitive information types are also referred to as conditions. A sensitive information type is defined by a pattern that can be identified by a regular expression or a function. In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type. Confidence level and proximity are also used in the evaluation process.</span></span>

<span data-ttu-id="4fae8-150">此時機密資訊類型無法在信箱中尋找靜態資料。</span><span class="sxs-lookup"><span data-stu-id="4fae8-150">At this time sensitive information types cannot be used to find data at rest in mailboxes.</span></span>

### <a name="using-content-search-with-sensitive-information-types"></a><span data-ttu-id="4fae8-151">使用內容搜尋搭配敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="4fae8-151">Using Content Search with sensitive information types</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4fae8-152"><strong>步驟</strong></span><span class="sxs-lookup"><span data-stu-id="4fae8-152"><strong>Step</strong></span></span></th>
<th align="left"><span data-ttu-id="4fae8-153"><strong>詳細資訊</strong></span><span class="sxs-lookup"><span data-stu-id="4fae8-153"><strong>More information</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd"><td align="left"><p><span data-ttu-id="4fae8-154">移至安全性與合規性中心的內容搜尋</span><span class="sxs-lookup"><span data-stu-id="4fae8-154">Go to Content Search in the Security and Compliance Center</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fae8-155">在安全性與合規性中心的左窗格中，按一下 [搜尋與調查]**** &gt; [內容搜尋]****。</span><span class="sxs-lookup"><span data-stu-id="4fae8-155">In the left pane of the Security &amp; Compliance Center, click **Search &amp; investigation** &gt; **Content search**.</span></span></p>
<p><span data-ttu-id="4fae8-156">請參閱<a href="https://support.office.com/en-us/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a">在 Office 365 安全性與合規性中心執行內容搜尋</a>。</span><span class="sxs-lookup"><span data-stu-id="4fae8-156">See <a href="https://support.office.com/en-us/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a">Run a Content Search in the Office 365 Security &amp; Compliance Center</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4fae8-157">為每一種敏感資訊類型建立新的搜尋項目</span><span class="sxs-lookup"><span data-stu-id="4fae8-157">Create a new search item for each sensitive information type</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fae8-158">請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="4fae8-158">Use the following syntax:</span></span></p>
<blockquote>
<p><span data-ttu-id="4fae8-159">SensitiveType:”&lt;type&gt;”</span><span class="sxs-lookup"><span data-stu-id="4fae8-159">SensitiveType:”&lt;type&gt;”</span></span></p>
</blockquote>
<p><span data-ttu-id="4fae8-160">例如：</span><span class="sxs-lookup"><span data-stu-id="4fae8-160">For example:</span></span></p>
<blockquote>
<p><span data-ttu-id="4fae8-161">SensitiveType:&quot;France Passport Number&quot;</span><span class="sxs-lookup"><span data-stu-id="4fae8-161">SensitiveType:&quot;France Passport Number&quot;</span></span></p>
</blockquote>
<p><span data-ttu-id="4fae8-p109">限定 SharePoint (包括商務用 OneDrive) 的搜尋範圍。請確定語法完全正確，而且沒有多餘的空格或錯字。</span><span class="sxs-lookup"><span data-stu-id="4fae8-p109">Scope the search to SharePoint (includes OneDrive for Business). Make sure the syntax is exact and there are no extra spaces or typos.</span></span></p>
<p><span data-ttu-id="4fae8-164">請參閱<a href="https://support.office.com/zh-TW/article/Form-a-query-to-find-sensitive-data-stored-on-sites-3019fbc5-7f15-4972-8d0e-dc182dc7f836">形成查詢以搜尋儲存在網站上的敏感資料</a>。</span><span class="sxs-lookup"><span data-stu-id="4fae8-164">See <a href="https://support.office.com/zh-TW/article/Form-a-query-to-find-sensitive-data-stored-on-sites-3019fbc5-7f15-4972-8d0e-dc182dc7f836">Form a query to find sensitive data stored on sites</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fae8-165">檢閱每個搜尋的結果</span><span class="sxs-lookup"><span data-stu-id="4fae8-165">Review the results for each search</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fae8-166">尋找這些類型的問題來判斷查詢目標是否精確：</span><span class="sxs-lookup"><span data-stu-id="4fae8-166">Look for these types of issues to determine if the query accuracy is on target:</span></span></p>
<p><li><span data-ttu-id="4fae8-167">許多誤判</span><span class="sxs-lookup"><span data-stu-id="4fae8-167">Many false positives</span></span></li></p>
<p><li><span data-ttu-id="4fae8-168">缺少已知的資料執行個體</span><span class="sxs-lookup"><span data-stu-id="4fae8-168">Missing known instances of data</span></span></li></p>
<p><span data-ttu-id="4fae8-169">請參閱<a href="https://support.office.com/en-us/article/Export-Content-Search-results-from-the-Office-365-Security-Compliance-Center-ed48d448-3714-4c42-85f5-10f75f6a4278">從 Office 365 安全性與合規性中心匯出搜尋結果</a>。</span><span class="sxs-lookup"><span data-stu-id="4fae8-169">See <a href="https://support.office.com/en-us/article/Export-Content-Search-results-from-the-Office-365-Security-Compliance-Center-ed48d448-3714-4c42-85f5-10f75f6a4278">Export Content Search results from the Office 365 Security &amp; Compliance Center</a>.</span></span></p>
<p><span data-ttu-id="4fae8-170">注意：如果您是使用 Mozilla Firefox 或 Chrome，則可能需要先使用 Internet Explorer 或 Edge 下載報告，才能安裝所需的增益集。</span><span class="sxs-lookup"><span data-stu-id="4fae8-170">Note: if you’re using Mozilla Firefox or Chrome, you might need to first download reports using Internet Explorer or Edge in order to install the required add-in.</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="sensitive-information-types-for-eu-citizen-data"></a><span data-ttu-id="4fae8-171">歐盟公民資料的敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="4fae8-171">Sensitive information types for EU citizen data</span></span>

<span data-ttu-id="4fae8-p110">開始使用這些敏感資訊類型。不久將對歐盟國家中的個人資料推出許多更敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="4fae8-p110">Start with these sensitive information types. Many more sensitive information types are coming soon for personal data in EU countries.</span></span>

> <span data-ttu-id="4fae8-174">比利時國民編碼</span><span class="sxs-lookup"><span data-stu-id="4fae8-174">Belgium National Number</span></span>
>
> <span data-ttu-id="4fae8-175">信用卡號碼</span><span class="sxs-lookup"><span data-stu-id="4fae8-175">Credit Card Number</span></span>
>
> <span data-ttu-id="4fae8-176">克羅埃西亞身分證號碼</span><span class="sxs-lookup"><span data-stu-id="4fae8-176">Croatia Identity Card Number</span></span>
>
> <span data-ttu-id="4fae8-177">克羅埃西亞個人識別 (OIB) 碼</span><span class="sxs-lookup"><span data-stu-id="4fae8-177">Croatia Personal Identification (OIB) Number</span></span>
>
> <span data-ttu-id="4fae8-178">捷克國民身分證號碼</span><span class="sxs-lookup"><span data-stu-id="4fae8-178">Czech National Identity Card Number</span></span>
>
> <span data-ttu-id="4fae8-179">丹麥個人識別碼</span><span class="sxs-lookup"><span data-stu-id="4fae8-179">Denmark Personal Identification Number</span></span>
>
> <span data-ttu-id="4fae8-180">歐盟轉帳卡號碼</span><span class="sxs-lookup"><span data-stu-id="4fae8-180">EU Debit Card Number</span></span>
>
> <span data-ttu-id="4fae8-181">芬蘭國民身分證</span><span class="sxs-lookup"><span data-stu-id="4fae8-181">Finland National ID</span></span>
>
> <span data-ttu-id="4fae8-182">芬蘭護照號碼</span><span class="sxs-lookup"><span data-stu-id="4fae8-182">Finland Passport Number</span></span>
>
> <span data-ttu-id="4fae8-183">法國駕照編號</span><span class="sxs-lookup"><span data-stu-id="4fae8-183">France Driver's License Number</span></span>
>
> <span data-ttu-id="4fae8-184">法國國民身分證 (CNI)</span><span class="sxs-lookup"><span data-stu-id="4fae8-184">France National ID Card (CNI)</span></span>
>
> <span data-ttu-id="4fae8-185">法國護照號碼</span><span class="sxs-lookup"><span data-stu-id="4fae8-185">France Passport Number</span></span>
>
> <span data-ttu-id="4fae8-186">法國社會安全號碼 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="4fae8-186">France Social Security Number (INSEE)</span></span>
>
> <span data-ttu-id="4fae8-187">德國駕照號碼</span><span class="sxs-lookup"><span data-stu-id="4fae8-187">German Driver’s License Number</span></span>
>
> <span data-ttu-id="4fae8-188">德國身分證號碼</span><span class="sxs-lookup"><span data-stu-id="4fae8-188">Germany Identity Card Number</span></span>
>
> <span data-ttu-id="4fae8-189">德國護照號碼</span><span class="sxs-lookup"><span data-stu-id="4fae8-189">German Passport Number</span></span>
>
> <span data-ttu-id="4fae8-190">希臘國民身分證</span><span class="sxs-lookup"><span data-stu-id="4fae8-190">Greece National ID Card</span></span>
>
> <span data-ttu-id="4fae8-191">國際銀行帳號 (IBAN)</span><span class="sxs-lookup"><span data-stu-id="4fae8-191">International Banking Account Number (IBAN)</span></span>
>
> <span data-ttu-id="4fae8-192">IP 位址</span><span class="sxs-lookup"><span data-stu-id="4fae8-192">IP Address</span></span>
>
> <span data-ttu-id="4fae8-193">愛爾蘭個人公用服務 (PPS) 號碼</span><span class="sxs-lookup"><span data-stu-id="4fae8-193">Ireland Personal Public Service (PPS) Number</span></span>
>
> <span data-ttu-id="4fae8-194">義大利駕照號碼</span><span class="sxs-lookup"><span data-stu-id="4fae8-194">Italy’s Driver’s License Number</span></span>
>
> <span data-ttu-id="4fae8-195">荷蘭公民服務 (BSN) 號碼</span><span class="sxs-lookup"><span data-stu-id="4fae8-195">Netherlands Citizen’s Service (BSN) Number</span></span>
>
> <span data-ttu-id="4fae8-196">挪威身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="4fae8-196">Norway Identity Number</span></span>
>
> <span data-ttu-id="4fae8-197">波蘭身分證明卡</span><span class="sxs-lookup"><span data-stu-id="4fae8-197">Poland Identity Card</span></span>
>
> <span data-ttu-id="4fae8-198">波蘭國民身分證 (PESEL)</span><span class="sxs-lookup"><span data-stu-id="4fae8-198">Poland National ID (PESEL)</span></span>
>
> <span data-ttu-id="4fae8-199">波蘭護照</span><span class="sxs-lookup"><span data-stu-id="4fae8-199">Poland Passport</span></span>
>
> <span data-ttu-id="4fae8-200">葡萄牙公民證號碼</span><span class="sxs-lookup"><span data-stu-id="4fae8-200">Portugal Citizen Card Number</span></span>
>
> <span data-ttu-id="4fae8-201">西班牙社會安全號碼 (SSN)</span><span class="sxs-lookup"><span data-stu-id="4fae8-201">Spain Social Security Number (SSN)</span></span>
>
> <span data-ttu-id="4fae8-202">瑞典國民身分證號</span><span class="sxs-lookup"><span data-stu-id="4fae8-202">Sweden National ID</span></span>
>
> <span data-ttu-id="4fae8-203">瑞典護照號碼</span><span class="sxs-lookup"><span data-stu-id="4fae8-203">Sweden Passport Number</span></span>
>
> <span data-ttu-id="4fae8-p111">英國駕照號碼</span><span class="sxs-lookup"><span data-stu-id="4fae8-p111">U.K. Driver’s License Number</span></span>
>
> <span data-ttu-id="4fae8-p112">英國選民名冊編號</span><span class="sxs-lookup"><span data-stu-id="4fae8-p112">U.K. Electoral Roll Number</span></span>
>
> <span data-ttu-id="4fae8-p113">英國國民健保服務號碼</span><span class="sxs-lookup"><span data-stu-id="4fae8-p113">U.K. National Health Service Number</span></span>
>
> <span data-ttu-id="4fae8-p114">英國國民保險號碼 (NINO)</span><span class="sxs-lookup"><span data-stu-id="4fae8-p114">U.K. National Insurance Number (NINO)</span></span>
>
> <span data-ttu-id="4fae8-p115">美國/英國護照號碼</span><span class="sxs-lookup"><span data-stu-id="4fae8-p115">U.S./U.K. Passport Number</span></span>

## <a name="add-parameters-to-a-sensitive-information-type-query-to-hone-the-results"></a><span data-ttu-id="4fae8-214">將參數新增至敏感資訊類型查詢來調整結果</span><span class="sxs-lookup"><span data-stu-id="4fae8-214">Add parameters to a sensitive information type query to hone the results</span></span>

<span data-ttu-id="4fae8-215">您可以將這些參數新增至敏感資訊類型查詢：</span><span class="sxs-lookup"><span data-stu-id="4fae8-215">You can add these parameters to a sensitive information type query:</span></span>

-   <span data-ttu-id="4fae8-216">Count range — 在納入查詢結果之前，定義文件需要包含之敏感資訊的發生次數。</span><span class="sxs-lookup"><span data-stu-id="4fae8-216">Count range — define the number of occurrences of sensitive information a document needs to contain before it’s included in the query results.</span></span>

-   <span data-ttu-id="4fae8-217">Confidence range — 已偵測之敏感類型實際符合的信賴等級，例如 85 (85%)。</span><span class="sxs-lookup"><span data-stu-id="4fae8-217">Confidence range — the level of confidence that the detected sensitive type is actually a match, such as 85 (85%).</span></span>

<span data-ttu-id="4fae8-218">語法：</span><span class="sxs-lookup"><span data-stu-id="4fae8-218">Syntax:</span></span>

-   <span data-ttu-id="4fae8-219">SensitiveType:”\<type\>|\<count range\>|\<confidence range\>”</span><span class="sxs-lookup"><span data-stu-id="4fae8-219">SensitiveType:”\<type\>|\<count range\>|\<confidence range\>”</span></span>

<span data-ttu-id="4fae8-220">範例：</span><span class="sxs-lookup"><span data-stu-id="4fae8-220">Examples:</span></span>

-   <span data-ttu-id="4fae8-221">SensitiveType:“Credit Card Number|5” (僅傳回確切地包含五個信用卡號碼的文件)</span><span class="sxs-lookup"><span data-stu-id="4fae8-221">SensitiveType:“Credit Card Number|5” (return only documents that contain exactly five credit card numbers)</span></span>

-   <span data-ttu-id="4fae8-p116">SensitiveType:“Credit Card Number|\*|85..” (信賴範圍為 85% 或更高)</span><span class="sxs-lookup"><span data-stu-id="4fae8-p116">SensitiveType:“Credit Card Number|\*|85..” (confidence range is 85 percent or higher)</span></span>

<span data-ttu-id="4fae8-224">注意：“SensitiveType” 會區分大小寫，但查詢的其餘部分不會。</span><span class="sxs-lookup"><span data-stu-id="4fae8-224">Note: “SensitiveType” is case sensitive, but the rest of the query is not.</span></span>

<span data-ttu-id="4fae8-p117">您也可以使用屬性和運算子來說明您如何修改查詢。如需詳細資訊和範例，請參閱[形成查詢以搜尋儲存在網站上的敏感資料](https://support.office.com/zh-TW/article/Form-a-query-to-find-sensitive-data-stored-on-sites-3019fbc5-7f15-4972-8d0e-dc182dc7f836)。</span><span class="sxs-lookup"><span data-stu-id="4fae8-p117">You can also use properties, and operators to illustrate how you can refine your queries. For more information and examples, see [Form a query to find sensitive data stored on sites](https://support.office.com/zh-TW/article/Form-a-query-to-find-sensitive-data-stored-on-sites-3019fbc5-7f15-4972-8d0e-dc182dc7f836).</span></span>