---
title: 搜尋所有信箱及使用 eDiscovery Center 的網站
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 56e2978f-71b6-4141-b769-ad856d31bbec
description: 在 Office 365 的 eDiscovery 中心，您可以搜尋所有的 Exchange Online 信箱、 SharePoint Online 網站及 OneDrive 單一 eDiscovery 搜尋中的商務網站。若要在組織中搜尋所有內容來源，eDiscovery 管理員必須具有每個內容來源的適當 eDiscovery 權限。
ms.openlocfilehash: b3508d5929ca2b5b7a937eb2dccf677a2968cbbc
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526594"
---
# <a name="search-all-mailboxes-and-sites-using-the-ediscovery-center"></a><span data-ttu-id="d7650-104">搜尋所有信箱及使用 eDiscovery Center 的網站</span><span class="sxs-lookup"><span data-stu-id="d7650-104">Search all mailboxes and sites using the eDiscovery Center</span></span>

<span data-ttu-id="d7650-p102">在 Office 365 的 eDiscovery 中心，您可以搜尋所有的 Exchange Online 信箱、 SharePoint Online 網站及 OneDrive 單一 eDiscovery 搜尋中的商務網站。若要在組織中搜尋所有內容來源，eDiscovery 管理員必須具有每個內容來源的適當 eDiscovery 權限。</span><span class="sxs-lookup"><span data-stu-id="d7650-p102">In the eDiscovery Center in Office 365, you can search all Exchange Online mailboxes, SharePoint Online sites, and OneDrive for Business sites in a single eDiscovery search. To search all content sources in the organization, an eDiscovery manager must be assigned the appropriate eDiscovery permissions for each content source.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="d7650-107">開始之前</span><span class="sxs-lookup"><span data-stu-id="d7650-107">Before you begin</span></span>

- <span data-ttu-id="d7650-p103">必須指派適當的權限給 eDiscovery 管理員，才能搜尋內容來源。如需有關指派 eDiscovery 權限給信箱與網站的詳細資訊，請參閱下列內容：</span><span class="sxs-lookup"><span data-stu-id="d7650-p103">An eDiscovery manager must be assigned the appropriate permissions to search a content source. For more information about assigning eDiscovery permissions to mailboxes and sites, see the following:</span></span> 
    
  - [<span data-ttu-id="d7650-110">Exchange 中指派 eDiscovery 權限</span><span class="sxs-lookup"><span data-stu-id="d7650-110">Assign eDiscovery permissions in Exchange</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=526886)
    
  - [<span data-ttu-id="d7650-111">指派 SharePoint Online 中的 eDiscovery 權限</span><span class="sxs-lookup"><span data-stu-id="d7650-111">Assign eDiscovery permissions in SharePoint Online</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=526885)
    
  - [<span data-ttu-id="d7650-112">將電子文件探索權限指派至商務用 OneDrive 網站</span><span class="sxs-lookup"><span data-stu-id="d7650-112">Assign eDiscovery permissions to OneDrive for Business sites</span></span>](assign-permissions-to-onedrive-for-business-sites.md)
    
- <span data-ttu-id="d7650-p104">您可以在單一 eDiscovery 搜尋查詢中搜尋最大值為 10000 個信箱和數目不受限制的 SharePoint Online 和 OneDrive for Business 的網站。不過，如果您指定要搜尋特定的網站，限制為 100 的網站。</span><span class="sxs-lookup"><span data-stu-id="d7650-p104">You can search a maximum of 10,000 mailboxes and an unlimited number of SharePoint Online and OneDrive for Business sites in a single eDiscovery search query. However, if you specify the specific sites to search, the limit is 100 sites.</span></span>
    
- <span data-ttu-id="d7650-115">搜尋所有信箱和網站時檢視結果時看到[的詳細資訊](search-all-mailboxes-and-sites-with-ediscovery.md#moreinfo)] 區段中的限制的描述。</span><span class="sxs-lookup"><span data-stu-id="d7650-115">See the [More information](search-all-mailboxes-and-sites-with-ediscovery.md#moreinfo) section for a description of the limits when viewing the results when searching all mailboxes and sites.</span></span> 
    
- <span data-ttu-id="d7650-116">如需建立 eDiscovery Center 中的搜尋查詢的詳細資訊，請參閱[建立和執行的 eDiscovery 查詢](https://go.microsoft.com/fwlink/p/?LinkID=404032)。</span><span class="sxs-lookup"><span data-stu-id="d7650-116">For more information about creating search queries in the eDiscovery Center, see [Create and run eDiscovery queries](https://go.microsoft.com/fwlink/p/?LinkID=404032).</span></span>
    
## <a name="search-all-locations"></a><span data-ttu-id="d7650-117">搜尋所有位置</span><span class="sxs-lookup"><span data-stu-id="d7650-117">Search all locations</span></span>

1. <span data-ttu-id="d7650-118">在 eDiscovery 中心，開啟您想要執行搜尋查詢的 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="d7650-118">In the eDiscovery Center, open the eDiscovery case that you want to run the search query for.</span></span>
    
2. <span data-ttu-id="d7650-119">在 [**搜尋及匯出**] 按一下 [現有的查詢或按一下 [**新增項目**建立新的搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="d7650-119">Under **Search and Export**, click an existing query or click **New item** to create a new search query.</span></span> 
    
3. <span data-ttu-id="d7650-120">在 [搜尋查詢] 頁面的 [**來源**] 區段中，按一下 [**修改查詢範圍**。</span><span class="sxs-lookup"><span data-stu-id="d7650-120">On the search query page, in the **Sources** section, click **Modify Query Scope**.</span></span>
    
4. <span data-ttu-id="d7650-121">在**修改查詢範圍**] 頁面上，按一下 [**搜尋所有項目**、 並選取要搜尋的內容位置。</span><span class="sxs-lookup"><span data-stu-id="d7650-121">On the **Modify Query Scope** page, click **Search everything**, and select the content locations to search.</span></span>
    
  - <span data-ttu-id="d7650-122">選取 [ **Exchange**搜尋所有信箱。</span><span class="sxs-lookup"><span data-stu-id="d7650-122">Select **Exchange** to search all mailboxes.</span></span> 
    
  - <span data-ttu-id="d7650-123">選取 [ **SharePoint**搜尋的所有 SharePoint Online 及 OneDrive for Business 的網站。</span><span class="sxs-lookup"><span data-stu-id="d7650-123">Select **SharePoint** to search all SharePoint Online and OneDrive for Business sites.</span></span> 
    
  - <span data-ttu-id="d7650-124">選取 [ **Exchange**和**SharePoint**搜尋組織中的所有內容的位置。</span><span class="sxs-lookup"><span data-stu-id="d7650-124">Select both **Exchange** and **SharePoint** to search all content locations in your organization.</span></span> 
    
![搜尋所有信箱和站台](media/e1f919ab-5596-43bb-a3c9-626cd41067b3.gif)
  
5. <span data-ttu-id="d7650-126">按一下 **[確定]**，儲存變更。</span><span class="sxs-lookup"><span data-stu-id="d7650-126">Click **OK** to save the changes.</span></span> 
    
6. <span data-ttu-id="d7650-p105">完成或修改在搜尋查詢] 頁面上，例如關鍵字查詢、 日期範圍或縮小搜尋內容的特定類型的其他資訊。當您準備好執行查詢時，請按一下 [**搜尋**]。</span><span class="sxs-lookup"><span data-stu-id="d7650-p105">Complete or revise other information on the search query page, such as the keyword query, the date range, or narrowing the specific types of content to search for. When you're ready to run the query, click **Search**.</span></span> 
    
## <a name="more-information"></a><span data-ttu-id="d7650-129">其他資訊</span><span class="sxs-lookup"><span data-stu-id="d7650-129">More information</span></span>
<span data-ttu-id="d7650-130"><a name="moreinfo"> </a></span><span class="sxs-lookup"><span data-stu-id="d7650-130"></span></span>

- <span data-ttu-id="d7650-131">前 500 個信箱和前 500 個網站與大部分的結果會列在底下**來源****查詢**] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="d7650-131">The top 500 mailboxes and the top 500 sites with the most results are listed under **Sources** on the **Query** page.</span></span> 
    
- <span data-ttu-id="d7650-132">所有內容來源中找到的項目數總計和其合併的總大小的顯示在 [**來源****查詢**] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="d7650-132">The total number of items found in all content sources and their combined total size are displayed under **Sources** on the **Query** page.</span></span> 
    
- <span data-ttu-id="d7650-133">您可以在 [查詢]**** 頁面上預覽位於 Exchange 信箱或 SharePoint 網站中的最近 200 筆搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="d7650-133">You can preview the 200 most recent search results located in Exchange mailboxes or SharePoint sites on the **Query** page.</span></span> 
    
    <span data-ttu-id="d7650-134">下列螢幕擷取畫面顯示搜尋結果顯示在 [**查詢**] 頁面上所有信箱和網站中搜尋的範例。</span><span class="sxs-lookup"><span data-stu-id="d7650-134">The following screenshot shows an example of the search results displayed on the **Query** page when you search all mailboxes and sites.</span></span> 
    
    ![搜尋所有位置時之結果的螢幕擷取畫面](media/4bf430f6-41ab-4bf6-afa9-33c3f6fd8b16.gif)
  

