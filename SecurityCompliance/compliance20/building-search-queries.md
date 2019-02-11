---
title: 建立搜尋查詢
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: c337b49491fca11e0ba5bc13d22ac3e54038c400
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2019
ms.locfileid: "29695069"
---
# <a name="build-search-queries"></a><span data-ttu-id="7838e-102">建立搜尋查詢</span><span class="sxs-lookup"><span data-stu-id="7838e-102">Build search queries</span></span>

<span data-ttu-id="7838e-103">在建置您的查詢，您可以使用各種關鍵字和條件來定義要尋找的項目。</span><span class="sxs-lookup"><span data-stu-id="7838e-103">In building your query, you can use various keywords and conditions to define which items to find.</span></span>

## <a name="keyword-searches"></a><span data-ttu-id="7838e-104">關鍵字搜尋</span><span class="sxs-lookup"><span data-stu-id="7838e-104">Keyword searches</span></span>

<span data-ttu-id="7838e-p101">在 [**關鍵字**] 方塊中輸入搜尋查詢。您可以指定關鍵字，訊息屬性例如傳送及接收日期或文件內容，例如檔案名稱或上次變更文件的日期。您可以使用較複雜的查詢使用布林運算子，例如**AND**、**或**、**不**及**NEAR**。您也可以搜尋文件或搜尋功能已從外部共用的文件中的機密資訊 （例如社會安全編號）。如果 [關鍵字] 方塊中保留空白，將會在搜尋結果中包含位於指定之內容的位置中的所有內容。</span><span class="sxs-lookup"><span data-stu-id="7838e-p101">Type a search query in **Keywords** box. You can specify keywords, message properties such as sent and received dates, or document properties such as file names or the date that a document was last changed. You can use a more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, and **NEAR**. You can also search for sensitive information (such as social security numbers) in documents, or search for documents that have been shared externally. If you leave the keyword box empty, all content located in the specified content locations will be included in the search results.</span></span>
    
<span data-ttu-id="7838e-p102">或者，您可以按一下 [**顯示關鍵字清單**] 核取方塊和類型中的每一列的關鍵字。如果您這樣做，在每一列的關鍵字連接的作用與**OR**運算子會建立搜尋查詢中相似的邏輯運算子 ( **c:s**) 所連接。</span><span class="sxs-lookup"><span data-stu-id="7838e-p102">Alternatively, you can click the **Show keyword list** checkbox and the type a keyword in each row. If you do this, the keywords on each row are connected by a logical operator ( **c:s**) that is similar in functionality to the **OR** operator in the search query that's created.</span></span> 
    
<span data-ttu-id="7838e-p103">為什麼要選擇使用 [關鍵字] 清單？您可以取得顯示多少個項目比對每個關鍵字的統計資料。這可協助您快速識別出哪些關鍵字是最 （且至少） 有效。您也可以使用 （以括弧括住） 的關鍵字文句] 列中。如需搜尋統計資料的詳細資訊，請參閱 ＜[搜尋統計資料](search-statistics.md)。</span><span class="sxs-lookup"><span data-stu-id="7838e-p103">Why use the keyword list? You can get statistics that show how many items match each keyword. This can help you quickly identify which keywords are the most (and least) effective. You can also use a keyword phrase (surrounded by parentheses) in a row. For more information about search statistics, see [Search statistic](search-statistics.md).</span></span>

## <a name="conditions"></a><span data-ttu-id="7838e-117">條件</span><span class="sxs-lookup"><span data-stu-id="7838e-117">Conditions</span></span>
    
<span data-ttu-id="7838e-p104">您可以新增要將搜尋縮小並傳回結果集更精簡的搜尋條件。每個條件將子句新增至搜尋查詢，建立及執行當您啟動搜尋。條件是以邏輯方式連線到 （在 [關鍵字] 方塊中指定） 的關鍵字查詢類似的作用**和**運算子的邏輯運算子 （**列**）。這表示項目必須滿足的關鍵字查詢與結果中包含的一或多個條件。這是條件，縮減結果協助的方式。清單和說明您可以在搜尋查詢中使用的條件，請參閱 「 搜尋條件 」 一節[關鍵字查詢和搜尋條件的內容搜尋](../keyword-queries-and-search-conditions.md#search-conditions)。</span><span class="sxs-lookup"><span data-stu-id="7838e-p104">You can add search conditions to narrow a search and return a more refined set of results. Each condition adds a clause to the search query that is created and run when you start the search. A condition is logically connected to the keyword query (specified in the keyword box) by a logical operator (**c:c**) that is similar in functionality to the **AND** operator. That means that items have to satisfy both the keyword query and one or more conditions to be included in the results. This is how conditions help to narrow your results. For a list and description of conditions that you can use in a search query, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](../keyword-queries-and-search-conditions.md#search-conditions).</span></span>


