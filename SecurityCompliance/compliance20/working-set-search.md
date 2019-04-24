---
title: 查詢工作集中的資料
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 3000a066bf69f71327801035e7c270cc602565ac
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32263805"
---
# <a name="query-the-data-in-a-working-set"></a><span data-ttu-id="0b0c4-102">查詢工作集中的資料</span><span class="sxs-lookup"><span data-stu-id="0b0c4-102">Query the data in a working set</span></span>

<span data-ttu-id="0b0c4-103">在大多數情況下，將能夠深入探討項目有工作集合中，並將它們更有效率地檢閱組織很有用。</span><span class="sxs-lookup"><span data-stu-id="0b0c4-103">In most cases, it will be useful to be able to dig deeper into what is there in a working set and organize them to review more efficiently.</span></span> <span data-ttu-id="0b0c4-104">查詢中的工作集可讓您若要這樣做，可讓您專注於符合一次您所定義之準則的文件的子集。</span><span class="sxs-lookup"><span data-stu-id="0b0c4-104">Queries within a working set enables you to do so by letting you focus on a subset of documents that meet the criteria defined by you at once.</span></span>

## <a name="creating-and-running-a-query-within-a-working-set"></a><span data-ttu-id="0b0c4-105">建立和執行的工作集內的查詢</span><span class="sxs-lookup"><span data-stu-id="0b0c4-105">Creating and running a query within a working set</span></span>

<span data-ttu-id="0b0c4-106">才能建立及執行查詢，以在您的工作集內，按一下 [在您的工作集在 「 新增查詢 」。</span><span class="sxs-lookup"><span data-stu-id="0b0c4-106">In order to create and run a query within your working set, click on "New Query" in your working set.</span></span> <span data-ttu-id="0b0c4-107">在您的查詢名稱並定義條件之後，按一下 「 儲存 」 以執行查詢。</span><span class="sxs-lookup"><span data-stu-id="0b0c4-107">After you name your query and define the conditions, click "Save" to run the query.</span></span> <span data-ttu-id="0b0c4-108">若要執行的查詢，先前尚未儲存，只要按一下已儲存的查詢。</span><span class="sxs-lookup"><span data-stu-id="0b0c4-108">To run a query that has been previously saved, simply click on the saved query.</span></span> <span data-ttu-id="0b0c4-109">如需您可以藉由搜尋的中繼資料的清單，請參閱[文件中繼資料](document-metadata-fields.md)欄位。</span><span class="sxs-lookup"><span data-stu-id="0b0c4-109">Refer to [Document metadata fields](document-metadata-fields.md) for a list of metadata you can search by.</span></span>

## <a name="building-your-query"></a><span data-ttu-id="0b0c4-110">建立您的查詢</span><span class="sxs-lookup"><span data-stu-id="0b0c4-110">Building your query</span></span>

<span data-ttu-id="0b0c4-111">您可以建置查詢關鍵字條件卡片中使用條件卡和查詢語言的組合。</span><span class="sxs-lookup"><span data-stu-id="0b0c4-111">You can build your query using a combination of condition cards and query language in the Keywords condition card.</span></span> <span data-ttu-id="0b0c4-112">您可以在一起作為區塊，以製作較複雜的查詢群組條件卡。</span><span class="sxs-lookup"><span data-stu-id="0b0c4-112">You can group condition cards together as a block to craft a more complex query.</span></span>

### <a name="condition-card"></a><span data-ttu-id="0b0c4-113">條件卡</span><span class="sxs-lookup"><span data-stu-id="0b0c4-113">Condition card</span></span>

<span data-ttu-id="0b0c4-114">工作集合中每個可搜尋的欄位具有對應的條件介面卡，您可用來建置您的查詢。</span><span class="sxs-lookup"><span data-stu-id="0b0c4-114">Every searchable field in a working set has a corresponding condition card that you can use to build your query.</span></span>

<span data-ttu-id="0b0c4-115">有多種類型的條件卡：</span><span class="sxs-lookup"><span data-stu-id="0b0c4-115">There are multiple types of condition cards:</span></span>
- <span data-ttu-id="0b0c4-116">Freetext 條件卡用於文字欄位，例如主旨 Freetext:。</span><span class="sxs-lookup"><span data-stu-id="0b0c4-116">Freetext: freetext condition card is used for text fields such as subject.</span></span> <span data-ttu-id="0b0c4-117">您可以使用分號分隔這些列出多個搜尋字詞。</span><span class="sxs-lookup"><span data-stu-id="0b0c4-117">You can list multiple search terms by separating them out with a comma.</span></span>
- <span data-ttu-id="0b0c4-118">日期： 日期條件卡係供例如上次修改日期的日期欄位。</span><span class="sxs-lookup"><span data-stu-id="0b0c4-118">Date: date condition card is used for date fields such as last modified date.</span></span>
- <span data-ttu-id="0b0c4-119">搜尋選項： 搜尋選項條件卡片會提供可能的值清單的工作集合中特定的欄位。</span><span class="sxs-lookup"><span data-stu-id="0b0c4-119">Search options: search options condition card will provide a list of possible values for the particular field in your working set.</span></span> <span data-ttu-id="0b0c4-120">這用於欄位，例如寄件者，其中沒有數量有限的工作集合中的可能值。</span><span class="sxs-lookup"><span data-stu-id="0b0c4-120">This is used for fields, such as sender, where there is a finite number of possible values in your working set.</span></span>
- <span data-ttu-id="0b0c4-121">關鍵字： 關鍵字條件卡片是 freetext 條件卡片，您可以使用搜尋字詞，或使用 KQL 類似的查詢語言中的特定執行個體。</span><span class="sxs-lookup"><span data-stu-id="0b0c4-121">Keyword: keyword condition card is a specific instance of freetext condition card that you can use to search for terms, or use KQL-like query language in.</span></span> <span data-ttu-id="0b0c4-122">如需詳細資訊，請參閱以下內容。</span><span class="sxs-lookup"><span data-stu-id="0b0c4-122">See below for more detail.</span></span>

### <a name="query-language"></a><span data-ttu-id="0b0c4-123">查詢語言</span><span class="sxs-lookup"><span data-stu-id="0b0c4-123">Query language</span></span>

<span data-ttu-id="0b0c4-124">除了條件卡] 底下，您可以使用類似的 KQL 查詢語言關鍵字卡片，製作您的查詢。</span><span class="sxs-lookup"><span data-stu-id="0b0c4-124">In addition to condition cards, you can use a KQL-like query language in the Keywords card to craft your query.</span></span> <span data-ttu-id="0b0c4-125">語言支援標準 KQL 語法，例如 AND、 OR、 NOT、 查詢和 NEAR(n)。</span><span class="sxs-lookup"><span data-stu-id="0b0c4-125">The query language supports standard KQL syntax like AND, OR, NOT, and NEAR(n).</span></span> <span data-ttu-id="0b0c4-126">它也支援單一字元萬用字元 （？） 以及多重字元萬用字元 （\*）。</span><span class="sxs-lookup"><span data-stu-id="0b0c4-126">It also supports single-character wildcard (?) and multi-character wildcard (\*).</span></span>

## <a name="filter"></a><span data-ttu-id="0b0c4-127">篩選</span><span class="sxs-lookup"><span data-stu-id="0b0c4-127">Filter</span></span>

<span data-ttu-id="0b0c4-128">除了您可以儲存的查詢，您可以使用篩選器您查詢結果重疊飛出視窗上的其他條件。</span><span class="sxs-lookup"><span data-stu-id="0b0c4-128">In addition to queries that you can save, you can overlay additional conditions on the fly to your query results using filters.</span></span> <span data-ttu-id="0b0c4-129">篩選與一些重大的方式不同查詢：</span><span class="sxs-lookup"><span data-stu-id="0b0c4-129">Filters differ from queries in a few significant ways:</span></span>
- <span data-ttu-id="0b0c4-130">篩選器是暫時性 （亦即它們不會保存透過不同的工作階段），而查詢會儲存至工作集。</span><span class="sxs-lookup"><span data-stu-id="0b0c4-130">Filters are transient (i.e. they do not persist over different sessions), whereas queries are saved to the working set.</span></span>
- <span data-ttu-id="0b0c4-131">篩選器永遠都會 additive;篩選會套用掌握您此時，有作用中的查詢，而套用查詢將會取代查詢作用中。</span><span class="sxs-lookup"><span data-stu-id="0b0c4-131">Filters are always additive; filters will apply on top of the query you have in effect at the moment, whereas applying a query will replace the query in effect.</span></span>