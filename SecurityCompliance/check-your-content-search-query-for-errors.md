---
title: 檢查您的內容搜尋查詢是否有錯誤
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/30/2016
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 88898874-e262-4c5c-b6d2-4e697497fc74
description: 檢查錯誤及錯字，例如不支援字元的內容搜尋關鍵字查詢及小寫布林運算子，才能執行搜尋。如果我們尋找錯誤，我們會建議修訂的查詢。
ms.openlocfilehash: 6ae14edc29bb7f8bab5dd2306282a69443872633
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038286"
---
# <a name="check-your-content-search-query-for-errors"></a><span data-ttu-id="581fa-104">檢查您的內容搜尋查詢是否有錯誤</span><span class="sxs-lookup"><span data-stu-id="581fa-104">Check your Content Search query for errors</span></span>

<span data-ttu-id="581fa-p102">當您建立或編輯內容搜尋時，您可以檢查您的查詢不受支援的字元與可能未接的布林值運算元的 Office 365。如何？只要按一下**檢查錯字查詢**的內容的搜尋查詢] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="581fa-p102">When you create or edit a Content Search, you can have Office 365 check your query for unsupported characters and Boolean operators that might not be capitalized. How? Just click **Check query for typos** on the query page of a Content Search.</span></span> 
  
![按一下 「 檢查查詢錯字"以檢查搜尋查詢不受支援的字元](media/e5314306-cfb2-481d-9b5c-13ce658156e7.png)
  
<span data-ttu-id="581fa-p103">以下是我們檢查不支援字元的清單。不受支援的字元通常處於隱藏狀態，以及它們通常是搜尋的錯誤或傳回非預期的結果。</span><span class="sxs-lookup"><span data-stu-id="581fa-p103">Here's a list of the unsupported characters that we check for. Unsupported characters are often hidden, and they typically cause a search error or return unintended results.</span></span>
  
- <span data-ttu-id="581fa-p104">不支援**智慧引號**智慧單一及雙引號 （也稱為 「 智慧引號 」）。僅限一般引號可以用於搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="581fa-p104">**Smart quotation marks** - Smart single and double quotation marks (also called curly quotes) aren't supported. Only straight quotation marks can be used in a search query.</span></span> 
    
- <span data-ttu-id="581fa-p105">**非列印和控制字元**-非列印和控制字元不代表書寫的符號，例如英數字元。範例的非列印和控制字元加入格式化文字或個別行文字的字元。</span><span class="sxs-lookup"><span data-stu-id="581fa-p105">**Non-printable and control characters** - Non-printable and control characters don't represent a written symbol, such as a alpha-numeric character. Examples of non-printable and control characters include characters that format text or separate lines of text.</span></span> 
    
- <span data-ttu-id="581fa-115">**左到右和從右至左標記**-這些是用來指出 （例如英文和西班牙文） 以從左至右語言和從右至左語言 （如阿拉伯文和希伯來文） 的文字方向的控制字元。</span><span class="sxs-lookup"><span data-stu-id="581fa-115">**Left-to-right and right-to-left marks** - These are control characters used to indicate text direction for left-to-right languages (such as English and Spanish) and right-to-left languages (such as Arabic and Hebrew).</span></span>
    
- <span data-ttu-id="581fa-p106">**小寫布林值運算元**-如果您使用布林運算子，例如**AND**、**或者**，並**不**在搜尋查詢時，它必須是大寫。當我們檢查錯字的查詢時，查詢語法會通常表示布林運算子正在使用的即使可能會使用小寫運算子;例如， `(WordA or WordB) and (WordC or WordD)`。</span><span class="sxs-lookup"><span data-stu-id="581fa-p106">**Lowercase Boolean operators** - If you use a Boolean operator, such as **AND**, **OR**, and **NOT** in a search query, it must be uppercase. When we check a query for typos, the query syntax will often indicate that a Boolean operator is being used even though lowercase operators might be used; for example,  `(WordA or WordB) and (WordC or WordD)`.</span></span>
    
## <a name="what-happens-if-a-query-has-an-unsupported-character"></a><span data-ttu-id="581fa-118">如果查詢有不受支援的字元發生什麼情況？</span><span class="sxs-lookup"><span data-stu-id="581fa-118">What happens if a query has an unsupported character?</span></span>

<span data-ttu-id="581fa-p107">如果不受支援的字元在查詢中找到的警告訊息會顯示 [不支援的字元所找到與建議另一種替代。然後您接著必須保留原始查詢或取代為建議的修訂查詢的選項。以下是範例中的搜尋查詢舊的螢幕擷取畫面中按一下 [**檢查錯字查詢**之後，會顯示警告訊息。請注意原始查詢包含智慧引號 」 與小寫布林運算子。</span><span class="sxs-lookup"><span data-stu-id="581fa-p107">If unsupported characters are found in your query, a warning message is displayed that says unsupported characters that were found and a suggests an alternative. Then you then have the option keep the original query or replace it with the suggested revised query. Here's an example of the warning message that's displayed after you click **Check query for typos** for the search query in the previous screenshot. Notice that the original query contains smart quotes and lowercase Boolean operators.</span></span> 
  
![警告訊息會顯示與針對您的查詢建議修訂](media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a><span data-ttu-id="581fa-124">如何避免在搜尋查詢中不支援的字元</span><span class="sxs-lookup"><span data-stu-id="581fa-124">How to prevent unsupported characters in your search queries</span></span>

<span data-ttu-id="581fa-p108">當您從其他應用程式 （例如 Microsoft Word 或 Microsoft Excel） 複製的查詢的組件並將其複製到 [查詢] 頁面上的內容搜尋 [關鍵字] 方塊不受支援的字元通常新增查詢。若要防止不支援的字元的最佳方式是只需要輸入 [關鍵字] 方塊中的查詢。或者，您可以從 Word 或 Excel 複製查詢並再將它的純文字編輯器，如 Microsoft [記事本] 中的檔案貼。然後將文字檔儲存並選取 [**編碼**] 下拉式清單中的**ANSI** 。這會移除任何格式設定與不支援的字元。然後您可以複製並貼到該關鍵字查詢] 方塊的查詢文字檔案中。</span><span class="sxs-lookup"><span data-stu-id="581fa-p108">Unsupported characters are typically added to a query when you copy the query or parts of the query from other applications (such as Microsoft Word or Microsoft Excel) and copy them to the keyword box on the query page of a Content Search. The best way to prevent unsupported characters is to just type the query in the keyword box. Alternatively, you can copy a query from Word or Excel and then paste it to file in a plain text editor, such as Microsoft Notepad. Then save the text file and select **ANSI** in the **Encoding** drop-down list. This will remove any formatting and unsupported characters. Then you can copy and paste the query from the text file to the keyword query box.</span></span> 
