---
title: 建立搜尋查詢
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: a33ecb6e1a2549b6bdc3bde9897b8a75e742b482
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151925"
---
# <a name="build-search-queries"></a><span data-ttu-id="8cd77-102">建立搜尋查詢</span><span class="sxs-lookup"><span data-stu-id="8cd77-102">Build search queries</span></span>

<span data-ttu-id="8cd77-103">在建置查詢，您可以使用各種關鍵字和條件來定義要尋找的項目。</span><span class="sxs-lookup"><span data-stu-id="8cd77-103">In building your query, you can use various keywords and conditions to define which items to find.</span></span>

## <a name="keyword-searches"></a><span data-ttu-id="8cd77-104">關鍵字搜尋</span><span class="sxs-lookup"><span data-stu-id="8cd77-104">Keyword searches</span></span>

<span data-ttu-id="8cd77-105">在 [**關鍵字**] 方塊中輸入搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="8cd77-105">Type a search query in **Keywords** box.</span></span> <span data-ttu-id="8cd77-106">您可以指定關鍵字、例如傳送和接收日期的郵件屬性，或者例如檔案名稱或文件上次變更的日期的文件屬性。</span><span class="sxs-lookup"><span data-stu-id="8cd77-106">You can specify keywords, message properties such as sent and received dates, or document properties such as file names or the date that a document was last changed.</span></span> <span data-ttu-id="8cd77-107">您可以使用更複雜的查詢，使用布林運算子，例如**AND**、**或**、**不**、 和**NEAR**。</span><span class="sxs-lookup"><span data-stu-id="8cd77-107">You can use a more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="8cd77-108">您也可以搜尋 （如社會安全編號） 中的文件或外部共用的文件中搜尋的敏感資訊。</span><span class="sxs-lookup"><span data-stu-id="8cd77-108">You can also search for sensitive information (such as social security numbers) in documents, or search for documents that have been shared externally.</span></span> <span data-ttu-id="8cd77-109">如果您將 [關鍵字] 方塊保留空白，位於指定的內容位置中的所有內容將會都包含在搜尋結果中。</span><span class="sxs-lookup"><span data-stu-id="8cd77-109">If you leave the keyword box empty, all content located in the specified content locations will be included in the search results.</span></span>
    
<span data-ttu-id="8cd77-110">或者，您可以按一下**顯示關鍵字清單**] 核取方塊並輸入每一列中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="8cd77-110">Alternatively, you can click the **Show keyword list** checkbox and the type a keyword in each row.</span></span> <span data-ttu-id="8cd77-111">如果您這麼做時，每一列上的關鍵字來類似功能中建立搜尋查詢的**OR**運算子邏輯運算子 ( **c:s**) 連線。</span><span class="sxs-lookup"><span data-stu-id="8cd77-111">If you do this, the keywords on each row are connected by a logical operator ( **c:s**) that is similar in functionality to the **OR** operator in the search query that's created.</span></span> 
    
<span data-ttu-id="8cd77-112">為什麼要使用關鍵字清單？</span><span class="sxs-lookup"><span data-stu-id="8cd77-112">Why use the keyword list?</span></span> <span data-ttu-id="8cd77-113">您可以取得顯示多少個項目比對每個關鍵字的統計資料。</span><span class="sxs-lookup"><span data-stu-id="8cd77-113">You can get statistics that show how many items match each keyword.</span></span> <span data-ttu-id="8cd77-114">這可協助您快速找出哪些關鍵字是最 （和至少） 有效。</span><span class="sxs-lookup"><span data-stu-id="8cd77-114">This can help you quickly identify which keywords are the most (and least) effective.</span></span> <span data-ttu-id="8cd77-115">您也可以使用 （以括號括住） 的關鍵字文句] 列中。</span><span class="sxs-lookup"><span data-stu-id="8cd77-115">You can also use a keyword phrase (surrounded by parentheses) in a row.</span></span> <span data-ttu-id="8cd77-116">如需搜尋統計資料的詳細資訊，請參閱 <<c0>搜尋統計資料。</span><span class="sxs-lookup"><span data-stu-id="8cd77-116">For more information about search statistics, see [Search statistic](search-statistics.md).</span></span>

## <a name="conditions"></a><span data-ttu-id="8cd77-117">條件</span><span class="sxs-lookup"><span data-stu-id="8cd77-117">Conditions</span></span>
    
<span data-ttu-id="8cd77-118">您可以新增搜尋條件縮小搜尋範圍，並傳回更精細的結果集。</span><span class="sxs-lookup"><span data-stu-id="8cd77-118">You can add search conditions to narrow a search and return a more refined set of results.</span></span> <span data-ttu-id="8cd77-119">每個條件將子句新增至搜尋查詢，建立及執行當您啟動搜尋。</span><span class="sxs-lookup"><span data-stu-id="8cd77-119">Each condition adds a clause to the search query that is created and run when you start the search.</span></span> <span data-ttu-id="8cd77-120">條件以邏輯方式是透過類似功能**AND**運算子邏輯運算子 (**c:c**) 連接至 （在 [關鍵字] 方塊中指定） 的關鍵字查詢。</span><span class="sxs-lookup"><span data-stu-id="8cd77-120">A condition is logically connected to the keyword query (specified in the keyword box) by a logical operator (**c:c**) that is similar in functionality to the **AND** operator.</span></span> <span data-ttu-id="8cd77-121">這表示項目必須符合的關鍵字查詢和結果中包含的一或多個條件。</span><span class="sxs-lookup"><span data-stu-id="8cd77-121">That means that items have to satisfy both the keyword query and one or more conditions to be included in the results.</span></span> <span data-ttu-id="8cd77-122">這就是條件如何協助您縮小搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="8cd77-122">This is how conditions help to narrow your results.</span></span> <span data-ttu-id="8cd77-123">清單和說明您可以在搜尋查詢中使用的條件，請參閱 「 搜尋條件 」 一節中[關鍵字查詢和搜尋條件的內容搜尋](../keyword-queries-and-search-conditions.md#search-conditions)。</span><span class="sxs-lookup"><span data-stu-id="8cd77-123">For a list and description of conditions that you can use in a search query, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](../keyword-queries-and-search-conditions.md#search-conditions).</span></span>


