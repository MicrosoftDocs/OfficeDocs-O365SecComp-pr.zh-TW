---
title: 檢查您的內容搜尋查詢是否有錯誤
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/30/2016
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 88898874-e262-4c5c-b6d2-4e697497fc74
description: 檢查錯誤和錯字，例如不支援的字元的內容搜尋的關鍵字查詢和小寫布林運算子，才能執行搜尋。 如果我們發現錯誤，則將建議的修訂的查詢。
ms.openlocfilehash: 00612116f345e2a01471d5c83df77f4bc8db9ce5
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32243654"
---
# <a name="check-your-content-search-query-for-errors"></a><span data-ttu-id="e06ab-104">檢查您的內容搜尋查詢是否有錯誤</span><span class="sxs-lookup"><span data-stu-id="e06ab-104">Check your Content Search query for errors</span></span>

<span data-ttu-id="e06ab-105">當您建立或編輯內容搜尋時，您可以檢查您的查詢不支援的字元及不可能必須大寫的布林值運算元的 Office 365。</span><span class="sxs-lookup"><span data-stu-id="e06ab-105">When you create or edit a Content Search, you can have Office 365 check your query for unsupported characters and Boolean operators that might not be capitalized.</span></span> <span data-ttu-id="e06ab-106">怎麼做？</span><span class="sxs-lookup"><span data-stu-id="e06ab-106">How?</span></span> <span data-ttu-id="e06ab-107">只要按一下**檢查錯字查詢**的內容搜尋的查詢] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="e06ab-107">Just click **Check query for typos** on the query page of a Content Search.</span></span> 
  
![按一下 「 檢查錯字查詢 」 來檢查您的搜尋查詢不受支援的字元](media/e5314306-cfb2-481d-9b5c-13ce658156e7.png)
  
<span data-ttu-id="e06ab-109">以下是我們檢查不支援字元的清單。</span><span class="sxs-lookup"><span data-stu-id="e06ab-109">Here's a list of the unsupported characters that we check for.</span></span> <span data-ttu-id="e06ab-110">通常已隱藏不支援的字元，而且它們通常會導致搜尋錯誤，或傳回非預期的結果。</span><span class="sxs-lookup"><span data-stu-id="e06ab-110">Unsupported characters are often hidden, and they typically cause a search error or return unintended results.</span></span>
  
- <span data-ttu-id="e06ab-111">不支援**智慧引號**智慧單引號及雙引號引號 （也稱為 「 智慧引號 」）。</span><span class="sxs-lookup"><span data-stu-id="e06ab-111">**Smart quotation marks** - Smart single and double quotation marks (also called curly quotes) aren't supported.</span></span> <span data-ttu-id="e06ab-112">僅限一般引號將可用於搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="e06ab-112">Only straight quotation marks can be used in a search query.</span></span> 
    
- <span data-ttu-id="e06ab-113">**不可列印和控制字元**的非可列印和控制字元不代表撰寫的符號，例如英數字元。</span><span class="sxs-lookup"><span data-stu-id="e06ab-113">**Non-printable and control characters** - Non-printable and control characters don't represent a written symbol, such as a alpha-numeric character.</span></span> <span data-ttu-id="e06ab-114">範例的非可列印和控制字元加入文字或個別行文字格式的字元。</span><span class="sxs-lookup"><span data-stu-id="e06ab-114">Examples of non-printable and control characters include characters that format text or separate lines of text.</span></span> 
    
- <span data-ttu-id="e06ab-115">**左到右和從右至左標記**-這些是用來指出文字方向為左到右的語言 （例如英文和西班牙文） 和 （例如阿拉伯文和希伯來文） 的從右至左語言的控制字元。</span><span class="sxs-lookup"><span data-stu-id="e06ab-115">**Left-to-right and right-to-left marks** - These are control characters used to indicate text direction for left-to-right languages (such as English and Spanish) and right-to-left languages (such as Arabic and Hebrew).</span></span>
    
- <span data-ttu-id="e06ab-116">**小寫布林運算子**-如果您使用布林運算子，例如**AND**、**或者**，並**不**在 [搜尋查詢時，它必須大寫。</span><span class="sxs-lookup"><span data-stu-id="e06ab-116">**Lowercase Boolean operators** - If you use a Boolean operator, such as **AND**, **OR**, and **NOT** in a search query, it must be uppercase.</span></span> <span data-ttu-id="e06ab-117">當我們檢查錯字的查詢時，查詢語法會通常指出即使可能使用小寫運算子;，正在使用布林運算子例如， `(WordA or WordB) and (WordC or WordD)`。</span><span class="sxs-lookup"><span data-stu-id="e06ab-117">When we check a query for typos, the query syntax will often indicate that a Boolean operator is being used even though lowercase operators might be used; for example,  `(WordA or WordB) and (WordC or WordD)`.</span></span>
    
## <a name="what-happens-if-a-query-has-an-unsupported-character"></a><span data-ttu-id="e06ab-118">如果查詢有不支援的字元，會發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="e06ab-118">What happens if a query has an unsupported character?</span></span>

<span data-ttu-id="e06ab-119">如果找不到查詢中的不受支援的字元，會顯示警告訊息表示找不到的不支援的字元和建議的另一種方法。</span><span class="sxs-lookup"><span data-stu-id="e06ab-119">If unsupported characters are found in your query, a warning message is displayed that says unsupported characters that were found and a suggests an alternative.</span></span> <span data-ttu-id="e06ab-120">然後您然後可以選擇保留原始查詢，或取代的建議的修訂查詢。</span><span class="sxs-lookup"><span data-stu-id="e06ab-120">Then you then have the option keep the original query or replace it with the suggested revised query.</span></span> <span data-ttu-id="e06ab-121">以下是您的搜尋查詢的前一個螢幕擷取畫面中按一下 [**檢查錯字查詢**後，會出現警告訊息的範例。</span><span class="sxs-lookup"><span data-stu-id="e06ab-121">Here's an example of the warning message that's displayed after you click **Check query for typos** for the search query in the previous screenshot.</span></span> <span data-ttu-id="e06ab-122">請注意，原始查詢包含智慧引號和小寫布林運算子。</span><span class="sxs-lookup"><span data-stu-id="e06ab-122">Notice that the original query contains smart quotes and lowercase Boolean operators.</span></span> 
  
![針對您的查詢建議修訂會顯示警告訊息](media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a><span data-ttu-id="e06ab-124">如何避免在搜尋查詢中不支援的字元</span><span class="sxs-lookup"><span data-stu-id="e06ab-124">How to prevent unsupported characters in your search queries</span></span>

<span data-ttu-id="e06ab-125">當您從其他應用程式 （例如 Microsoft Word 或 Microsoft Excel） 複製的查詢的組件，並將其複製到的內容搜尋的 [查詢] 頁面上的 [關鍵字] 方塊時，不支援的字元通常會新增至查詢。</span><span class="sxs-lookup"><span data-stu-id="e06ab-125">Unsupported characters are typically added to a query when you copy the query or parts of the query from other applications (such as Microsoft Word or Microsoft Excel) and copy them to the keyword box on the query page of a Content Search.</span></span> <span data-ttu-id="e06ab-126">若要防止不支援的字元，最好是只需要輸入 [關鍵字] 方塊中的查詢。</span><span class="sxs-lookup"><span data-stu-id="e06ab-126">The best way to prevent unsupported characters is to just type the query in the keyword box.</span></span> <span data-ttu-id="e06ab-127">或者，您可以從 Word 或 Excel 複製查詢，並再將它的純文字編輯器，Microsoft [記事本] 之類的檔案貼。</span><span class="sxs-lookup"><span data-stu-id="e06ab-127">Alternatively, you can copy a query from Word or Excel and then paste it to file in a plain text editor, such as Microsoft Notepad.</span></span> <span data-ttu-id="e06ab-128">然後儲存為文字檔，並在 [**編碼**] 下拉式清單中選取**ANSI** 。</span><span class="sxs-lookup"><span data-stu-id="e06ab-128">Then save the text file and select **ANSI** in the **Encoding** drop-down list.</span></span> <span data-ttu-id="e06ab-129">這會移除任何格式設定與不支援的字元。</span><span class="sxs-lookup"><span data-stu-id="e06ab-129">This will remove any formatting and unsupported characters.</span></span> <span data-ttu-id="e06ab-130">然後您可以複製並貼上文字檔案中查詢，以關鍵字的查詢] 方塊中。</span><span class="sxs-lookup"><span data-stu-id="e06ab-130">Then you can copy and paste the query from the text file to the keyword query box.</span></span> 
