---
title: 重試內容搜尋以解決錯誤的內容位置
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 重試] 按鈕可用於解決有內容位置錯誤的內容搜尋。
ms.openlocfilehash: 032d93ef0990ed1dd7c1ea7bf2ba16653b3a862f
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218853"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a><span data-ttu-id="584f1-103">重試內容搜尋以解決錯誤的內容位置</span><span class="sxs-lookup"><span data-stu-id="584f1-103">Retry a Content Search to resolve a content location error</span></span>

<span data-ttu-id="584f1-104">當您使用內容搜尋在 Office 365 安全性 & 規範中心來搜尋超大 （例如搜尋 100000 信箱或其他單一內容搜尋功能） 的信箱數目，您可能會得到類似下列的搜尋錯誤：</span><span class="sxs-lookup"><span data-stu-id="584f1-104">When you use Content Search in the Office 365 Security & Compliance Center to search a very large number of mailboxes (for example, searching 100,000 mailboxes or more in a single Content Search), you may get search errors that are similar to the following:</span></span>

```
Error

The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

<span data-ttu-id="584f1-p101">這些錯誤 （錯誤代碼 CS008 009 和 CS012 002） 指出內容搜尋失敗來搜尋特定的內容位置 ；在此範例中未搜尋兩個信箱。這些錯誤會顯示在 [狀態的詳細資訊彈出式] 頁面上之內容的搜尋。</span><span class="sxs-lookup"><span data-stu-id="584f1-p101">These errors (with error codes of CS008-009 and CS012-002) indicate that Content Search failed to search specific content locations; in this example, two mailboxes weren't searched. These errors are displayed on the status details flyout page of the Content Search.</span></span>

## <a name="cause-of-content-location-errors"></a><span data-ttu-id="584f1-107">內容位置錯誤的原因</span><span class="sxs-lookup"><span data-stu-id="584f1-107">Cause of content location errors</span></span>

<span data-ttu-id="584f1-p102">搜尋的信箱數目，搜尋會分散於數以千計之 Microsoft 資料中心中的伺服器。在任何時候的特定伺服器可能是在重新開機狀態或收件人容錯移轉備援副本的程序。在下列情況下擷取資料的內容的搜尋要求將會逾時。在上述範例中，錯誤失敗的信箱已搜尋逾時的結果。</span><span class="sxs-lookup"><span data-stu-id="584f1-p102">When searching a large number of mailboxes, the search is distributed across thousands of servers in a Microsoft datacenter. At any one time, specific servers could be in reboot state or in the process of failing over to redundant copies. In either of these cases, the Content Search's request to retrieve data will timeout. In the previous example, the errors for the mailboxes that failed were the result of the search timing out.</span></span>

## <a name="resolving-content-location-errors"></a><span data-ttu-id="584f1-112">協助您解決內容位置錯誤</span><span class="sxs-lookup"><span data-stu-id="584f1-112">Resolving content location errors</span></span>

<span data-ttu-id="584f1-p103">在不同伺服器上的類似錯誤通常會產生重新啟動搜尋。而不重新啟動搜尋，按一下 [搜尋結果頁面頂端會顯示 [**重試**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="584f1-p103">Restarting the search will often result in similar errors on different servers. Instead of restarting the search, click the **Retry** button that is displayed at the top of the search results page.</span></span>

![按一下 [重試] 按鈕以解決內容位置錯誤](media/retrycontentsearch3.png)

<span data-ttu-id="584f1-p104">這會導致重試僅針對失敗的信箱搜尋。當您重試搜尋時，會保留已順利傳回的結果。</span><span class="sxs-lookup"><span data-stu-id="584f1-p104">This will result in the retrying the search only for the mailboxes that failed. When you retry the search, the other results that were successfully returned are retained.</span></span>

## <a name="tips-to-avoid-content-location-errors"></a><span data-ttu-id="584f1-118">若要避免內容位置錯誤的秘訣</span><span class="sxs-lookup"><span data-stu-id="584f1-118">Tips to avoid content location errors</span></span>

<span data-ttu-id="584f1-119">以下是一些除了原因的內容位置錯誤和一些秘訣可協助您搜尋大量信箱時加以避免。</span><span class="sxs-lookup"><span data-stu-id="584f1-119">Here are some addition causes of content location errors and some tips to help you avoid them when searching large numbers of mailboxes.</span></span>

- <span data-ttu-id="584f1-p105">所搜尋的信箱可能會因為使用者活動忙碌。在此例中的搜尋服務可能節流本身防止信箱變成無法使用。若要避免此問題，請嘗試執行搜尋期間非上班時間。</span><span class="sxs-lookup"><span data-stu-id="584f1-p105">The mailbox being searched might be busy due to user activity. In this case, the search service might throttle itself to prevent the mailbox from becoming unavailable. To avoid this, try running searches during non-business hours.</span></span>

- <span data-ttu-id="584f1-p106">搜尋查詢可能會從信箱太多內容擷取。請儘可能嘗試使用關鍵字、 日期範圍和搜尋條件來縮小搜尋範圍。</span><span class="sxs-lookup"><span data-stu-id="584f1-p106">The search query might be retrieving too much content from the mailbox. If possible, try to narrow the scope of the search by using keywords, date ranges, and search conditions.</span></span>

- <span data-ttu-id="584f1-p107">太多的關鍵字或當您建立搜尋查詢使用的[關鍵字] 清單中](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-content-searches)的關鍵字詞。當您執行搜尋查詢使用關鍵字] 清單中時，基本上執行服務的每一列的個別搜尋關鍵字清單中，讓可產生統計資料。如果您在搜尋查詢中使用關鍵字] 清單中，最小化] 的 [關鍵字] 清單中的列數或分成較小的清單中的數字的關鍵字，並建立不同的搜尋為每個關鍵字清單。</span><span class="sxs-lookup"><span data-stu-id="584f1-p107">Too many keywords or keyword phrases when you create a search query using the [keywords list](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-content-searches). When you run a search query that uses the keywords list, the service essentially runs a separate search for each row in the keyword list so that statistics can be generated. If you're using the keywords list in search queries, minimize the number of rows in the keyword list or divide the number keywords into smaller lists and create a different search for each keyword list.</span></span>

  > [!NOTE]
  > <span data-ttu-id="584f1-128">若要協助減少大型關鍵字清單所導致的問題，現在是限制最大值為 20 列在 [關鍵字] 清單中的搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="584f1-128">To help reduce issues caused by large keyword lists, you're now limited to a maximum of 20 rows in the keyword list of a search query.</span></span>

- <span data-ttu-id="584f1-p108">太多搜尋相同的信箱上正在執行在同一時間。請儘可能嘗試在任何一個信箱上一次執行一個搜尋。</span><span class="sxs-lookup"><span data-stu-id="584f1-p108">Too many searches are being performed on the same mailbox at the same time. If possible, try to run one search at a time on any one mailbox.</span></span>

- <span data-ttu-id="584f1-p109">在單一搜尋中搜尋太多的信箱。搜尋非常大的信箱數目時會增加的內容位置錯誤的機率。請儘可能嘗試執行多個搜尋，讓每個搜尋組織中包含信箱的子集。</span><span class="sxs-lookup"><span data-stu-id="584f1-p109">Searching too many mailboxes in a single search. The probability of content location errors increases when searching a very large number of mailboxes. If possible, try to run multiple searches so that each search includes a subset of  mailboxes in your organization.</span></span>

- <span data-ttu-id="584f1-p110">必要的維護信箱上執行。雖然此原因可能會發生常，等待一點時後接收內容位置錯誤，然後重試搜尋。</span><span class="sxs-lookup"><span data-stu-id="584f1-p110">Required maintenance is being performed on the mailbox. Though this cause probably occurs infrequently, wait a little while after receiving the content location error and then retry the search.</span></span>
