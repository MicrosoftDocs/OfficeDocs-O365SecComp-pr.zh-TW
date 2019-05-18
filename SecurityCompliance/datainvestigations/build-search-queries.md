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
description: 使用關鍵字和條件來縮小搜尋範圍時搜尋資料時使用 Microsoft 365 中的資料進行調查。
ms.openlocfilehash: 6d6c7e99257d071595365ec9a9557892fe3fe8db
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151055"
---
# <a name="build-search-queries"></a><span data-ttu-id="9990d-103">建立搜尋查詢</span><span class="sxs-lookup"><span data-stu-id="9990d-103">Build search queries</span></span>

<span data-ttu-id="9990d-104">在建置搜尋查詢時，您可以使用關鍵字來尋找特定的內容和條件來縮小搜尋以返回您調查與最相關的項目的範圍。</span><span class="sxs-lookup"><span data-stu-id="9990d-104">When building search queries, you can use keywords to find specific content and conditions to narrow the scope of the search to return items that are most relevant to your investigation.</span></span>

![使用關鍵字和條件來縮小搜尋結果](../media/SearchQueryBox.png)

## <a name="keyword-searches"></a><span data-ttu-id="9990d-106">關鍵字搜尋</span><span class="sxs-lookup"><span data-stu-id="9990d-106">Keyword searches</span></span>

<span data-ttu-id="9990d-107">在搜尋查詢中的 [**關鍵字**] 方塊中輸入關鍵字查詢。</span><span class="sxs-lookup"><span data-stu-id="9990d-107">Type a keyword query in the **Keywords** box in the search query.</span></span> <span data-ttu-id="9990d-108">您可以指定關鍵字、 電子郵件內容，（例如傳送和接收日期） 或文件內容 （例如檔案名稱或上次變更文件的日期）。</span><span class="sxs-lookup"><span data-stu-id="9990d-108">You can specify keywords, email message properties, (such as sent and received dates), or document properties (such as file names or the date that a document was last changed).</span></span> <span data-ttu-id="9990d-109">您可以使用更複雜的查詢，使用布林運算子，例如**AND**、**或**、**不**、 和**NEAR**。</span><span class="sxs-lookup"><span data-stu-id="9990d-109">You can use a more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="9990d-110">您也可以在 SharePoint 和 OneDrive （不在電子郵件） 或搜尋的外部共用的文件中的文件中搜尋的敏感資訊 （例如社會安全編號）。</span><span class="sxs-lookup"><span data-stu-id="9990d-110">You can also search for sensitive information (such as social security numbers) in documents in SharePoint and OneDrive (not in email messages), or search for documents that have been shared externally.</span></span> <span data-ttu-id="9990d-111">如果您將 [**關鍵字**] 方塊保留空白，位於指定的內容位置中的所有內容將會都包含在搜尋結果中。</span><span class="sxs-lookup"><span data-stu-id="9990d-111">If you leave the **Keywords** box empty, all content located in the specified content locations will be included in the search results.</span></span>
    
<span data-ttu-id="9990d-112">或者，您可以按一下**顯示關鍵字清單**] 核取方塊並輸入關鍵字或每一列中的關鍵字文句。</span><span class="sxs-lookup"><span data-stu-id="9990d-112">Alternatively, you can click the **Show keyword list** checkbox and the type a keyword or keyword phrase in each row.</span></span> <span data-ttu-id="9990d-113">如果您這麼做時，由邏輯運算子 （這當成*c:s*） 中建立搜尋查詢的**OR**運算子類似功能連線每一列中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="9990d-113">If you do this, the keywords in each row are connected by a logical operator (which is represented as *c:s*) that is similar in functionality to the **OR** operator in the search query that's created.</span></span> <span data-ttu-id="9990d-114">這表示包含任何資料列中的任何關鍵字的項目將會包含在搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="9990d-114">This means that items that contain any keyword in any row will be included in the search results.</span></span>

![使用 [關鍵字] 清單以取得在查詢中每個關鍵字統計資料](../media/KeywordListSearch.png)

<span data-ttu-id="9990d-116">為什麼要使用關鍵字清單？</span><span class="sxs-lookup"><span data-stu-id="9990d-116">Why use the keyword list?</span></span> <span data-ttu-id="9990d-117">您可以取得顯示多少個項目比對關鍵字清單中的每個關鍵字的統計資料。</span><span class="sxs-lookup"><span data-stu-id="9990d-117">You can get statistics that show how many items match each keyword in the keyword list.</span></span> <span data-ttu-id="9990d-118">這可協助您快速找出最 （和至少） 有效的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="9990d-118">This can help you quickly identify the keywords that are the most (and least) effective.</span></span> <span data-ttu-id="9990d-119">您也可以使用關鍵字片語 （圍繞括號） 中 [關鍵字] 清單中的資料列。</span><span class="sxs-lookup"><span data-stu-id="9990d-119">You can also use a keyword phrase (surrounded by parentheses) in a row in the keywords list.</span></span> <span data-ttu-id="9990d-120">如需搜尋統計資料的詳細資訊，請參閱 <<c0>搜尋統計資料。</span><span class="sxs-lookup"><span data-stu-id="9990d-120">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

> [!NOTE]
> <span data-ttu-id="9990d-121">若要協助減少大型關鍵字清單所導致的問題，您正在限制最多 20 列在 [關鍵字] 清單中的項目。</span><span class="sxs-lookup"><span data-stu-id="9990d-121">To help reduce issues caused by large keyword lists, you're limited to a maximum of 20 rows in the keyword list.</span></span>

## <a name="conditions"></a><span data-ttu-id="9990d-122">條件</span><span class="sxs-lookup"><span data-stu-id="9990d-122">Conditions</span></span>
    
<span data-ttu-id="9990d-123">您可以新增搜尋條件縮小搜尋範圍，並傳回更精細的結果集。</span><span class="sxs-lookup"><span data-stu-id="9990d-123">You can add search conditions to narrow the scope of a search and return a more refined set of results.</span></span> <span data-ttu-id="9990d-124">每個條件將子句新增至搜尋查詢，建立及執行當您啟動搜尋。</span><span class="sxs-lookup"><span data-stu-id="9990d-124">Each condition adds a clause to the search query that is created and run when you start the search.</span></span> <span data-ttu-id="9990d-125">條件是以邏輯方式連線到 （在 [關鍵字] 方塊中指定） 的關鍵字查詢邏輯運算子 （這當成*c:c*） 都與**AND**運算子相似的功能。</span><span class="sxs-lookup"><span data-stu-id="9990d-125">A condition is logically connected to the keyword query (specified in the keyword box) by a logical operator (which is represented as *c:c*) that is similar in functionality to the **AND** operator.</span></span> <span data-ttu-id="9990d-126">這表示項目必須符合的關鍵字查詢和搜尋結果中包含的一或多個條件。</span><span class="sxs-lookup"><span data-stu-id="9990d-126">That means that items have to satisfy both the keyword query and one or more conditions to be included in the search results.</span></span> <span data-ttu-id="9990d-127">這就是條件如何協助您縮小搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="9990d-127">This is how conditions help to narrow your results.</span></span> <span data-ttu-id="9990d-128">清單和說明您可以在搜尋查詢中使用的條件，請參閱 「 搜尋條件 」 一節中[關鍵字查詢和搜尋條件](../keyword-queries-and-search-conditions.md#search-conditions)。</span><span class="sxs-lookup"><span data-stu-id="9990d-128">For a list and description of conditions that you can use in a search query, see the "Search conditions" section in [Keyword queries and search conditions](../keyword-queries-and-search-conditions.md#search-conditions).</span></span>
