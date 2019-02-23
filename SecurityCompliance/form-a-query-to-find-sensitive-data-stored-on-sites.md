---
title: 形成查詢以搜尋儲存在網站上的敏感資料
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 3019fbc5-7f15-4972-8d0e-dc182dc7f836
description: 與資料外洩防護 (DLP) SharePoint Online 中，您可以探索包含機密資料整個租用戶中的文件。之後探索文件，您可以使用以保護資料的文件擁有者。本主題可協助您的表單來搜尋機密資料的查詢。
ms.openlocfilehash: 3dc1081d4627f1a26c50eed84f733c31a3f6c194
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217233"
---
# <a name="form-a-query-to-find-sensitive-data-stored-on-sites"></a><span data-ttu-id="c2963-105">形成查詢以搜尋儲存在網站上的敏感資料</span><span class="sxs-lookup"><span data-stu-id="c2963-105">Form a query to find sensitive data stored on sites</span></span>

<span data-ttu-id="c2963-p102">使用者通常儲存機密資料，例如信用卡號碼、 社會安全編號，或個人，在他們的網站和一段時間這會暴露鍰等重要資料遺失的風險。儲存在網站上的文件 — 包括 OneDrive for Business 的網站-無法共用組織外不應該具有存取資訊的人員。與資料外洩防護 (DLP) SharePoint Online 中，您可以探索包含機密資料整個租用戶中的文件。之後探索文件，您可以使用以保護資料的文件擁有者。本主題可協助您的表單來搜尋機密資料的查詢。</span><span class="sxs-lookup"><span data-stu-id="c2963-p102">Users often store sensitive data, such as credit card numbers, social security numbers, or personal, on their sites, and over time this can expose an organization to significant risk of data loss. Documents stored on sites—including OneDrive for Business sites—could be shared with people outside the organization who shouldn't have access to the information. With data loss prevention (DLP) in SharePoint Online, you can discover documents that contain sensitive data throughout your tenant. After discovering the documents, you can work with the document owners to protect the data. This topic can help you form a query to search for sensitive data.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c2963-111">電子化搜索或 eDiscovery 及 DLP 是 premium 功能需要進行[SharePoint Online 計劃 2](https://go.microsoft.com/fwlink/?LinkId=510080)。</span><span class="sxs-lookup"><span data-stu-id="c2963-111">Electronic discovery, or eDiscovery, and DLP are premium features that require [SharePoint Online Plan 2](https://go.microsoft.com/fwlink/?LinkId=510080).</span></span> 
  
## <a name="forming-a-basic-dlp-query"></a><span data-ttu-id="c2963-112">形成基本 DLP 查詢</span><span class="sxs-lookup"><span data-stu-id="c2963-112">Forming a basic DLP query</span></span>

<span data-ttu-id="c2963-p103">有三個部分構成的基本的 DLP 查詢： SensitiveType、 計算範圍和信賴的範圍。如下圖所示下， **SensitiveType:"\<類型\>"** 是必要的並同時**|\<計算的範圍\>** 和**|\<信賴範圍\>** 皆為選用。</span><span class="sxs-lookup"><span data-stu-id="c2963-p103">There are three parts that make up a basic DLP query: SensitiveType, count range, and confidence range. As illustrated in the following graphic, **SensitiveType:"\<type\>"** is required, and both**|\<count range\>** and**|\<confidence range\>** are optional.</span></span> 
  
![查詢範例分為必要和選用](media/DLP-query-example-text.png)
  
### <a name="sensitive-type---required"></a><span data-ttu-id="c2963-116">敏感類型 - 必要</span><span class="sxs-lookup"><span data-stu-id="c2963-116">Sensitive type - required</span></span>

<span data-ttu-id="c2963-p104">那麼每一個部分是什麼？使用屬性通常是開始 SharePoint DLP 查詢`SensitiveType:"`和資訊類型名稱的[敏感資訊類型詳細目錄](https://go.microsoft.com/fwlink/?LinkID=509999)，且結尾為`"`。您也可以使用您為組織建立[自訂的敏感資訊類型](create-a-custom-sensitive-information-type.md)的名稱。例如，您可能會尋找包含信用卡數字的文件。在這種執行個體，您可以使用下列格式： `SensitiveType:"Credit Card Number"`。因為您沒有加入計數範圍或信賴範圍、 該查詢會傳回信用卡號會偵測到每個文件。這是最簡單的查詢，您可以執行，並且會傳回大部分的結果。請記住，拼字檢查及機密類型的間距很重要。</span><span class="sxs-lookup"><span data-stu-id="c2963-p104">So what is each part? SharePoint DLP queries typically begin with the property  `SensitiveType:"` and an information type name from the [sensitive information types inventory](https://go.microsoft.com/fwlink/?LinkID=509999), and end with a  `"`. You can also use the name of a [custom sensitive information type](create-a-custom-sensitive-information-type.md) that you created for your organization. For example, you might be looking for documents that contain credit card numbers. In such an instance, you'd use the following format:  `SensitiveType:"Credit Card Number"`. Because you didn't include count range or confidence range, the query returns every document in which a credit card number is detected. This is the simplest query that you can run, and it returns the most results. Keep in mind that the spelling and spacing of the sensitive type matters.</span></span> 
  
### <a name="ranges---optional"></a><span data-ttu-id="c2963-125">範圍 - 選用</span><span class="sxs-lookup"><span data-stu-id="c2963-125">Ranges - optional</span></span>

<span data-ttu-id="c2963-p105">下一步] 兩個部分都範圍，讓我們快速檢查某個範圍的外觀。在 SharePoint DLP 查詢基本的範圍會以表示以兩個句號分隔的兩個號碼這看起來像這樣： `[number]..[number]`。例如，如果`10..20`會使用該範圍會擷取介於 10%到 20 的數字。有許多不同的範圍組合及幾種本主題。</span><span class="sxs-lookup"><span data-stu-id="c2963-p105">Both of the next two parts are ranges, so let's quickly examine what a range looks like. In SharePoint DLP queries, a basic range is represented by two numbers separated by two periods, which looks like this:  `[number]..[number]`. For instance, if  `10..20` is used, that range would capture numbers from 10 through 20. There are many different range combinations and several are covered in this topic.</span></span> 
  
<span data-ttu-id="c2963-p106">我們將計數範圍新增至查詢。您可以使用 count 範圍定義中的文件必須包含在查詢結果中包含之前的機密資訊的次數。例如，如果您想要傳回含有完全五個信用卡號的文件查詢，請使用此： `SensitiveType:"Credit Card Number|5"`。Count 範圍也可以協助您識別造成的風險高度的文件。例如，您的組織可能高風險考慮五個或多個信用卡號與文件。若要尋找並排列此準則的文件，您可以使用此查詢： `SensitiveType:"Credit Card Number|5.."`。或者，您可以找到五個文件或更少使用此查詢信用卡片號碼： `SensitiveType:"Credit Card Number|..5"`。</span><span class="sxs-lookup"><span data-stu-id="c2963-p106">Let's add a count range to the query. You can use count range to define the number of occurrences of sensitive information a document needs to contain before it's included in the query results. For example, if you want your query to return only documents that contain exactly five credit card numbers, use this:  `SensitiveType:"Credit Card Number|5"`. Count range can also help you identify documents that pose high degrees of risk. For example, your organization might consider documents with five or more credit card numbers a high risk. To find documents fitting this criterion, you would use this query:  `SensitiveType:"Credit Card Number|5.."`. Alternatively, you can find documents with five or fewer credit card numbers by using this query:  `SensitiveType:"Credit Card Number|..5"`.</span></span> 
  
#### <a name="confidence-range"></a><span data-ttu-id="c2963-137">信賴範圍</span><span class="sxs-lookup"><span data-stu-id="c2963-137">Confidence range</span></span>

<span data-ttu-id="c2963-p107">最後，confidence 範圍是信賴偵測到的機密類型的實際相符項目層級。信賴範圍的值的運作方式很類似計算的範圍。您可以表單查詢而不需納入計數範圍。例如，若要搜尋的任意數量的信用卡號與文件 — 只要信賴範圍是從 85%或更高-您可以使用此查詢： `SensitiveType:"Credit Card Number|*|85.."`。</span><span class="sxs-lookup"><span data-stu-id="c2963-p107">Finally, confidence range is the level of confidence that the detected sensitive type is actually a match. The values for confidence range work similarly to count range. You can form a query without including a count range. For example, to search for documents with any number of credit card numbers—as long as the confidence range is 85 percent or higher—you would use this query:  `SensitiveType:"Credit Card Number|*|85.."`.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c2963-p108">星號 ( `*`) 是表示任何值的運作的萬用字元。您可以使用萬用字元 ( `*`) [計數範圍中或在信賴範圍中但不是在機密的類型。</span><span class="sxs-lookup"><span data-stu-id="c2963-p108">The asterisk ( `*`) is a wildcard character that means any value works. You can use the wildcard character ( `*`) either in the count range or in the confidence range, but not in a sensitive type.</span></span> 
  
### <a name="additional-query-properties-and-search-operators-available-in-the-ediscovery-center"></a><span data-ttu-id="c2963-144">可以在 eDiscovery 中心取得的其他查詢屬性和搜尋運算子</span><span class="sxs-lookup"><span data-stu-id="c2963-144">Additional query properties and search operators available in the eDiscovery Center</span></span>

<span data-ttu-id="c2963-p109">在 SharePoint 中的 DLP 也介紹 LastSensitiveContentScan 屬性，可協助您搜尋特定的時間範圍內所掃描的檔案。使用查詢範例`LastSensitiveContentScan`屬性，請參閱下一節中的[複雜查詢範例](form-a-query-to-find-sensitive-data-stored-on-sites.md#BKMK_ExamplesOfComplexQueries)。</span><span class="sxs-lookup"><span data-stu-id="c2963-p109">DLP in SharePoint also introduces the LastSensitiveContentScan property, which can help you search for files scanned within a specific timeframe. For query examples with the  `LastSensitiveContentScan` property, see the [Examples of complex queries](form-a-query-to-find-sensitive-data-stored-on-sites.md#BKMK_ExamplesOfComplexQueries) in the next section.</span></span> 
  
<span data-ttu-id="c2963-p110">您可以如使用 DLP 特有的屬性來建立查詢時，不僅標準 SharePoint eDiscovery 搜尋屬性`Author`或`FileExtension`。您可以使用運算子來建立複雜的查詢。可用的屬性和運算子清單，請參閱 ＜[使用搜尋屬性與使用 eDiscovery 運算子](https://go.microsoft.com/fwlink/?LinkId=510093)部落格文章。</span><span class="sxs-lookup"><span data-stu-id="c2963-p110">You can use not only DLP-specific properties to create a query, but also standard SharePoint eDiscovery search properties such as  `Author` or  `FileExtension`. You can use operators to build complex queries. For the list of available properties and operators, see the [Using Search Properties and Operators with eDiscovery](https://go.microsoft.com/fwlink/?LinkId=510093) blog post.</span></span> 
  
## <a name="examples-of-complex-queries"></a><span data-ttu-id="c2963-150">範例</span><span class="sxs-lookup"><span data-stu-id="c2963-150">Examples of complex queries</span></span>

<span data-ttu-id="c2963-151">下列範例會使用不同的機密類型、 屬性及運算子來說明您可以在如何讓您查詢以尋找完全您正在尋找的項目。</span><span class="sxs-lookup"><span data-stu-id="c2963-151">The following examples use different sensitive types, properties, and operators to illustrate how you can refine your queries to find exactly what you're looking for.</span></span>
  
|<span data-ttu-id="c2963-152">**查詢**</span><span class="sxs-lookup"><span data-stu-id="c2963-152">**Query**</span></span>|<span data-ttu-id="c2963-153">**說明**</span><span class="sxs-lookup"><span data-stu-id="c2963-153">**Explanation**</span></span>|
|:-----|:-----|
| `SensitiveType:"International Banking Account Number (IBAN)"` <br/> |<span data-ttu-id="c2963-p111">因為它是這麼久，但該機密類型的正確名稱似乎怪異名稱。請務必使用[敏感資訊類型詳細目錄](https://go.microsoft.com/fwlink/?LinkID=509999)中的實際名稱。您也可以使用您為組織建立[自訂的敏感資訊類型](create-a-custom-sensitive-information-type.md)的名稱。</span><span class="sxs-lookup"><span data-stu-id="c2963-p111">The name might seem strange because it's so long, but it's the correct name for that sensitive type. Make sure to use exact names from the [sensitive information types inventory](https://go.microsoft.com/fwlink/?LinkID=509999). You can also use the name of a [custom sensitive information type](create-a-custom-sensitive-information-type.md) that you created for your organization.  </span></span><br/> |
| `SensitiveType:"Credit Card Number|1..4294967295|1..100"` <br/> |<span data-ttu-id="c2963-p112">這會具有至少一個相符的文件傳回成機密類型"信用卡號"。每個範圍的值是個別的最小和最大值。更簡單的方法來撰寫此查詢是`SensitiveType:"Credit Card Number"`，但所在中的樂趣吗？</span><span class="sxs-lookup"><span data-stu-id="c2963-p112">This returns documents with at least one match to the sensitive type "Credit Card Number." The values for each range are the respective minimum and maximum values. A simpler way to write this query is  `SensitiveType:"Credit Card Number"`, but where's the fun in that?  </span></span><br/> |
| `SensitiveType:"Credit Card Number| 5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018"` <br/> |<span data-ttu-id="c2963-160">這會從 2018 年 8 月 11、 透過 2018 年 8 月 13、 傳回 5-25 信用卡號所掃描的文件。</span><span class="sxs-lookup"><span data-stu-id="c2963-160">This returns documents with 5-25 credit card numbers that were scanned from August 11, 2018 through August 13, 2018.</span></span>  <br/> |
| `SensitiveType:"Credit Card Number| 5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018" NOT FileExtension:XLSX` <br/> |<span data-ttu-id="c2963-p113">這會從 2018 年 8 月 11、 透過 2018 年 8 月 13、 傳回 5-25 信用卡號所掃描的文件。XLSX 副檔名的檔案不包含在查詢結果。 `FileExtension`是其中一個可以包含在查詢中的許多屬性。如需詳細資訊，請參閱[使用搜尋屬性與使用 eDiscovery 的運算子](https://go.microsoft.com/fwlink/?LinkId=510093)。</span><span class="sxs-lookup"><span data-stu-id="c2963-p113">This returns documents with 5-25 credit card numbers that were scanned from August 11, 2018 through August 13, 2018. Files with an XLSX extension aren't included in the query results.  `FileExtension` is one of many properties that you can include in a query. For more information, see [Using Search Properties and Operators with eDiscovery](https://go.microsoft.com/fwlink/?LinkId=510093).  </span></span><br/> |
| `SensitiveType:"Credit Card Number" OR SensitiveType:"U.S. Social Security Number (SSN)"` <br/> |<span data-ttu-id="c2963-165">這會傳回包含信用卡號碼或身分證字號的文件。</span><span class="sxs-lookup"><span data-stu-id="c2963-165">This returns documents that contain either a credit card number or a social security number.</span></span>  <br/> |
   
## <a name="examples-of-queries-to-avoid"></a><span data-ttu-id="c2963-166">範例</span><span class="sxs-lookup"><span data-stu-id="c2963-166">Examples of queries to avoid</span></span>

<span data-ttu-id="c2963-p114">並非所有的查詢會建立相等。下表提供範例不使用 DLP SharePoint 中的查詢，並說明為何。</span><span class="sxs-lookup"><span data-stu-id="c2963-p114">Not all queries are created equal. The following table gives examples of queries that don't work with DLP in SharePoint and describes why.</span></span>
  
|<span data-ttu-id="c2963-169">**不受支援的查詢**</span><span class="sxs-lookup"><span data-stu-id="c2963-169">**Unsupported query**</span></span>|<span data-ttu-id="c2963-170">**原因**</span><span class="sxs-lookup"><span data-stu-id="c2963-170">**Reason**</span></span>|
|:-----|:-----|
| `SensitiveType:"Credit Card Number|.."` <br/> |<span data-ttu-id="c2963-171">您必須至少新增一個數值。</span><span class="sxs-lookup"><span data-stu-id="c2963-171">You must add at least one number.</span></span>  <br/> |
| `SensitiveType:"NotARule"` <br/> |<span data-ttu-id="c2963-p115">"NotARule"不是有效的機密類型名稱。DLP 查詢中運作僅[敏感資訊類型詳細目錄](https://go.microsoft.com/fwlink/?LinkID=509999)中的名稱。</span><span class="sxs-lookup"><span data-stu-id="c2963-p115">"NotARule" isn't a valid sensitive type name. Only names in the [sensitive information types inventory](https://go.microsoft.com/fwlink/?LinkID=509999) work in DLP queries.  </span></span><br/> |
| `SensitiveType:"Credit Card Number|0"` <br/> |<span data-ttu-id="c2963-174">最小值或範圍中的最大值為零而言無效。</span><span class="sxs-lookup"><span data-stu-id="c2963-174">Zero isn't valid as either the minimum value or the maximum value in a range.</span></span>  <br/> |
| `SensitiveType:"Credit Card Number"` <br/> |<span data-ttu-id="c2963-p116">很可能很難將看到，但是沒有額外"信用"和"卡片"讓查詢無效之間的空格。使用[敏感資訊類型詳細目錄](https://go.microsoft.com/fwlink/?LinkID=509999)中的確切機密類型名稱。</span><span class="sxs-lookup"><span data-stu-id="c2963-p116">It's might be difficult to see, but there's extra white space between "Credit" and "Card" that makes the query invalid. Use exact sensitive type names from the [sensitive information types inventory](https://go.microsoft.com/fwlink/?LinkID=509999).  </span></span><br/> |
| `SensitiveType:"Credit Card Number|1. .3"` <br/> |<span data-ttu-id="c2963-177">不應該以空格分隔的兩個週期部分。</span><span class="sxs-lookup"><span data-stu-id="c2963-177">The two-period portion shouldn't be separated by a space.</span></span>  <br/> |
| `SensitiveType:"Credit Card Number| |1..|80.."` <br/> |<span data-ttu-id="c2963-178">有太多管道分隔符號 （</span><span class="sxs-lookup"><span data-stu-id="c2963-178">There are too many pipe delimiters (</span></span>|<span data-ttu-id="c2963-p117">).請改為遵循此格式：`SensitiveType: "Credit Card Number|1..|80.."`</span><span class="sxs-lookup"><span data-stu-id="c2963-p117">). Follow this format instead: `SensitiveType: "Credit Card Number|1..|80.."`</span></span> <br/> |
| `SensitiveType:"Credit Card Number|1..|80..101"` <br/> |<span data-ttu-id="c2963-p118">信賴值都代表百分比，因為它們不能超過 100。而是介於 1 到 100 選擇數字。</span><span class="sxs-lookup"><span data-stu-id="c2963-p118">Because confidence values represent a percentage, they can't exceed 100. Choose a number from 1 through 100 instead.</span></span>  <br/> |
   
## <a name="for-more-information"></a><span data-ttu-id="c2963-183">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="c2963-183">For more information</span></span>

[<span data-ttu-id="c2963-184">機密資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="c2963-184">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
  
[<span data-ttu-id="c2963-185">Office 365 安全性執行內容的搜尋&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="c2963-185">Run a Content Search in the Office 365 Security &amp; Compliance Center</span></span>](run-a-content-search-in-the-security-and-compliance-center.md)
  
[<span data-ttu-id="c2963-186">內容搜尋的關鍵字查詢與搜尋條件</span><span class="sxs-lookup"><span data-stu-id="c2963-186">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
  

