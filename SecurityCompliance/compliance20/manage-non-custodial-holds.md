---
title: 進階 eDiscovery （預覽） 來管理保留
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
ms.openlocfilehash: 75ddbcfb401d285dfb7a4b610e3f0709e21946f2
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607572"
---
# <a name="rename-this-page-and-md-file-to-managing-holds"></a><span data-ttu-id="ae163-102">重新命名此頁面及 MD 檔案，以 「 管理保留"</span><span class="sxs-lookup"><span data-stu-id="ae163-102">Rename this page and MD File to "Managing Holds"</span></span>

# <a name="holds-in-advanced-ediscovery-preview"></a><span data-ttu-id="ae163-103">進階 eDiscovery (Preview) 中的保留</span><span class="sxs-lookup"><span data-stu-id="ae163-103">Holds in Advanced eDiscovery (Preview)</span></span>
<span data-ttu-id="ae163-p101">您可以使用進階的 eDiscovery （預覽） 案例來建立保留来保留可能是您案例相關的內容。使用進階的 eDiscovery （預覽） 保留功能，您可以利用保留 custodians 和其資料來源。此外，您可以利用非 custodial 保留對信箱和 OneDrive for Business 的網站。您也可以將保留群組信箱、 SharePoint 網站及 OneDrive 商務網站的 Office 365 群組。同樣地，您可以利用保留對信箱和相關聯的 Microsoft 小組網站。當您保留上放置的內容位置時，內容會保留直到您放開 okay、 移除特定資料位置，或完全刪除保留原則。</span><span class="sxs-lookup"><span data-stu-id="ae163-p101">You can use an Advanced eDiscovery (Preview) case to create holds to preserve content that might be relevant to your case. Using the Advanced eDiscovery (Preview) hold capabilities, you can place holds on custodians and their data sources. Additionally, you can place a non-custodial hold on mailboxes and OneDrive for Business sites. You can also place a hold on the group mailbox, SharePoint site, and OneDrive for Business site for an Office 365 Group. Similarly, you can place a hold on the mailbox and site that are associated with Microsoft Teams. When you place content locations on hold, content is held until you release the custodian, remove a specific data location, or delete the hold policy entirely.</span></span>

## <a name="manage-custodian-based-holds"></a><span data-ttu-id="ae163-110">管理 Okay 型保留</span><span class="sxs-lookup"><span data-stu-id="ae163-110">Manage Custodian Based Holds</span></span>

<span data-ttu-id="ae163-p102">在某些情況下，您可能需要一組資料 custodians 您識別並選擇来保留。進階的 ediscovery （預覽），這些 custodians thold，當使用者和自己所選取的資料來源會自動新增至 okay 保留原則。</span><span class="sxs-lookup"><span data-stu-id="ae163-p102">In some cases, you may have a set of data custodians that you have identified and choosen to preserve. In Advanced eDiscovery (Preview), when these custodians are placed on thold, the user and their selected data sources are automatically added to a custodian hold policy.</span></span> 

<span data-ttu-id="ae163-113">若要檢視 okay 保留原則：</span><span class="sxs-lookup"><span data-stu-id="ae163-113">To view the custodian hold policy:</span></span>

1. <span data-ttu-id="ae163-114">**安全性 & 規範中心**中，按一下 [ **eDiscovery > 進階的 eDiscovery （預覽）** 若要在組織中顯示的情況下的清單。</span><span class="sxs-lookup"><span data-stu-id="ae163-114">In the **Security & Compliance Center**, click **eDiscovery > Advanced eDiscovery (Preview)** to display the list of cases in your organization.</span></span>
   
2. <span data-ttu-id="ae163-p103">瀏覽至要新增您的案例中的 custodians **Custodians** ] 索引標籤。若要了解如何新增及上的進行 custodians 保留進階的 eDiscovery （預覽） 案例中，瀏覽**案例中管理 Custodians**一節。如果您已新增 custodians 並處於保留狀態，移至步驟 3。</span><span class="sxs-lookup"><span data-stu-id="ae163-p103">Navigate to the **Custodians** tab to add custodians within your case. To learn how you can add and place custodians on hold within an Advanced eDiscovery (Preview) case, visit the **Managing Custodians within a Case** section. If you have already added custodians and placed them on hold, move to Step 3.</span></span>
   
3. <span data-ttu-id="ae163-118">瀏覽至 [**保留**] 索引標籤並選取 Okay 原則。</span><span class="sxs-lookup"><span data-stu-id="ae163-118">Navigate to the **Holds** tab and select the 'Custodian Policy'.</span></span>
   
4. <span data-ttu-id="ae163-p104">在詳細資料彈出式中，您可以看到保留原則的統計資料。您也可以執行像是將查詢套用至您 okay 型保留的動作。如需建立保留查詢和使用情況的詳細資訊，請參閱[關鍵字查詢和搜尋條件的內容搜尋](https://docs.microsoft.com/en-us/office365/SecurityCompliance/keyword-queries-and-search-conditions )</span><span class="sxs-lookup"><span data-stu-id="ae163-p104">In the details flyout, you can see hold statistics for your policy. You can also perform actions like apply a query to your custodian-based hold. For more information about creating a hold query and using conditions, see [Keyword queries and search conditions for Content Search](https://docs.microsoft.com/en-us/office365/SecurityCompliance/keyword-queries-and-search-conditions )</span></span>
 
## <a name="manage-non-custodial-holds"></a><span data-ttu-id="ae163-122">管理非 Custodial 保留</span><span class="sxs-lookup"><span data-stu-id="ae163-122">Manage Non-Custodial Holds</span></span>
<span data-ttu-id="ae163-123">當您建立保留時，您有下列選項的範圍會保留在指定的內容位置的內容：</span><span class="sxs-lookup"><span data-stu-id="ae163-123">When you create a hold, you have the following options to scope the content that is held in the specified content locations:</span></span>
  - <span data-ttu-id="ae163-p105">您建立的所有內容都處於保留狀態設為無限期保留。或者，您可以建立查詢式的保留僅符合內容的搜尋查詢處於保留狀態。</span><span class="sxs-lookup"><span data-stu-id="ae163-p105">You create an infinite hold where all content is placed on hold. Alternatively, you can create a query-based hold where only content that matches a search query is placed on hold.</span></span>
  - <span data-ttu-id="ae163-p106">您可以指定日期範圍，以保留已傳送、 接收到，或建立的日期範圍內的內容。或者，您可以保留不論當它已傳送、 接收到，或建立的所有內容。</span><span class="sxs-lookup"><span data-stu-id="ae163-p106">You can specify a date range to hold only the content that was sent, received, or created within that date range. Alternatively, you can hold all content regardless of when it was sent, received, or created.</span></span>

<span data-ttu-id="ae163-128">若要建立保留 eDiscovery 案例：</span><span class="sxs-lookup"><span data-stu-id="ae163-128">To create a hold for an eDiscovery case:</span></span>
  1. <span data-ttu-id="ae163-129">**安全性 & 規範中心**中，按一下 [ **eDiscovery > 進階的 eDiscovery （預覽）** 若要在組織中顯示的情況下的清單。</span><span class="sxs-lookup"><span data-stu-id="ae163-129">In the **Security & Compliance Center**, click **eDiscovery > Advanced eDiscovery (Preview)** to display the list of cases in your organization.</span></span>
  
  2. <span data-ttu-id="ae163-130">按一下您想要建立的保留案例] 旁的 [開啟]。</span><span class="sxs-lookup"><span data-stu-id="ae163-130">Click Open next to the case that you want to create the holds in.</span></span>
  
  3. <span data-ttu-id="ae163-131">在 [**首頁**] 索引標籤的大小寫按一下 [**保留**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="ae163-131">On the**Home** tab for the case, click the **Holds** tab.</span></span>
  
  4. <span data-ttu-id="ae163-132">在 [**保留**] 索引標籤上按一下 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="ae163-132">On the **Holds** tab, click  **Create**.</span></span>
  
  5. <span data-ttu-id="ae163-p107">在 [名稱保留] 頁面中，提供保留的名稱。保留名稱必須是在組織中唯一的。</span><span class="sxs-lookup"><span data-stu-id="ae163-p107">On the Name your hold page, give the hold a name. The name of the hold must be unique in your organization.</span></span>
 
  6. <span data-ttu-id="ae163-135">（選用）在 [描述] 方塊中新增的保留的描述。</span><span class="sxs-lookup"><span data-stu-id="ae163-135">(Optional) In the Description box, add a description of the hold.</span></span>
  
  7. <span data-ttu-id="ae163-136">按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="ae163-136">Click **Next**.</span></span>
  
  8. <span data-ttu-id="ae163-p108">選擇您想要進行的內容位置保留。您可以在保留上放置信箱、 網站及公用資料夾。a. **Exchange 電子郵件**-[**選擇使用者、 群組或小組**和 [**選擇使用者、 群組或小組**一次。若要指定要保留信箱。使用 [搜尋] 方塊中找到使用者信箱使用者和通訊群組 （置於群組成員的信箱保留） 至保留。您也可撥打相關聯的信箱上的保留供 Office 365 群組或 Microsoft 小組。選取使用者、 群組、 小組] 核取方塊、 按一下 [**選擇**] 和 [**完成**。</span><span class="sxs-lookup"><span data-stu-id="ae163-p108">Choose the content locations that you want to place on hold. You can place mailboxes, sites, and public folders on hold. a. **Exchange email** - Click **Choose users, groups, or teams** and then click **Choose users, groups, or teams** again. to specify mailboxes to place on hold. Use the search box to find user mailboxes and distribution groups (to place a hold on the mailboxes of group members) to place on hold. You can also place a hold on the associated mailbox for an Office 365 Group or a Microsoft Team. Select the user, group, team check box, click **Choose**, and then click **Done**.</span></span>
 
    [!NOTE]
    <span data-ttu-id="ae163-p109">當您按一下 [**選擇使用者、 群組或小組**來指定要保留信箱，會顯示信箱選擇是空的。這是由設計，以提升效能。若要將人員新增至這份清單中，輸入的名稱 （至少要有 3 個字元） 在 [搜尋] 方塊中。</span><span class="sxs-lookup"><span data-stu-id="ae163-p109">When you click **Choose users, groups, or teams** to specify mailboxes to place on hold, the mailbox picker that's displayed is empty. This is by design to enhance performance. To add people to this list, type a name (a minimum of 3 characters) in the search box.</span></span>


    <span data-ttu-id="ae163-p110">b. **SharePoint 網站**-按一下 [**選擇的網站**] 和 [**選擇網站**一次以指定 SharePoint 和 OneDrive for Business 網站置於保留。輸入您想要保留每個網站的 URL。您也可以針對 Office 365 群組或 Microsoft 小組新增 SharePoint 網站的 URL。按一下 [**選擇**] 和 [**完成**。</span><span class="sxs-lookup"><span data-stu-id="ae163-p110">b. **SharePoint Sites** - Click **Choose sites** and then click **Choose sites** again to specify SharePoint and OneDrive for Business sites to place on hold. Type the URL for each site that you want to place on hold. You can also add the URL for the SharePoint site for an Office 365 Group or a Microsoft Team. Click **Choose**, and then click **Done**.</span></span>
    
     <span data-ttu-id="ae163-153">請參閱**FAQ** ] 區段中放入保留的 Office 365 群組及 Microsoft 小組的秘訣。</span><span class="sxs-lookup"><span data-stu-id="ae163-153">See the **FAQ** section for tips on putting Office 365 Groups and Microsoft Teams on hold.</span></span>

    [!NOTE]
    <span data-ttu-id="ae163-p111">在極罕見的人員的使用者主體名稱 (UPN) 已變更案例中，其 OneDrive 帳戶的 URL 會變更要併入新的 UPN。如果發生這種情況，您必須新增使用者的新 OneDrive URL 並移除舊來修改保留。</span><span class="sxs-lookup"><span data-stu-id="ae163-p111">In the rare case that a person's user principal name (UPN) has changed, the URL for their OneDrive account will also be changed to incorporate the new UPN. If this happens, you'll have to modify the hold by adding the user's new OneDrive URL and removing the old one.</span></span>

     <span data-ttu-id="ae163-p112">c. **Exchange 公用資料夾**-將切換參數移至組織保留的所有位置將放在 Exchange Online 中的所有公用資料夾。請注意，您無法選擇特定公用資料夾遷移至放入保留。保留設定成 [**無**如果您不想要的公用資料夾上設定保留切換參數。</span><span class="sxs-lookup"><span data-stu-id="ae163-p112">c. **Exchange public folders** - Move the toggle switch to the All position to put all public folders in your Exchange Online organization on hold. Note that you can't choose specific public folders to put on hold. Leave the toggle switch set to **None** if you don't want to put a hold on public folders.</span></span>

  9. <span data-ttu-id="ae163-160">當您完成新增至保留的內容位置時，按一下 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="ae163-160">When you're done adding content locations to the hold, click **Next**.</span></span>
  
  10. <span data-ttu-id="ae163-p113">若要建立條件查詢式保留，請完成下列設定。否則請只是按一下 [**下一步**。1.1 中 [關鍵字] 方塊中，類型] 方塊中的搜尋查詢以便符合搜尋準則的內容放入保留。您可以指定關鍵字、 郵件內容或文件屬性，例如檔案名稱。您也可以使用或不使用布林運算子，例如 AND、 OR 的較複雜查詢。如果您遺漏保留空白，則將會位於指定之內容的位置中的所有內容都放在 [關鍵字] 方塊。</span><span class="sxs-lookup"><span data-stu-id="ae163-p113">To create a query-based hold with conditions, complete the following. Otherwise, just click **Next**. 1.1 In the box under Keywords, type a search query in the box so that only the content that meets the search criteria is placed on hold. You can specify keywords, message properties, or document properties, such as file names. You can also use more complex queries that use a Boolean operator, such as AND, OR, or NOT. If you leave the keyword box empty, then all content located in the specified content locations will be placed on hold.</span></span>

    <span data-ttu-id="ae163-p114">1.2 按一下 [**新增**條件新增一或多個條件，縮減保留搜尋查詢]。每個條件將子句新增至 KQL 搜尋查詢，建立及執行當您建立保留。例如您可以指定日期範圍，讓電子郵件或站台建立日期範圍內的文件會處於保留狀態。條件是以邏輯方式連線到 （在 [關鍵字] 方塊中指定） 的關鍵字查詢 AND 運算子。表示項目必須滿足的關鍵字查詢及可放置在此條件就會保留。</span><span class="sxs-lookup"><span data-stu-id="ae163-p114">1.2 Click  **Add** conditions to add one or more conditions to narrow the search query for the hold. Each condition adds a clause to the KQL search query that is created and run when you create the hold. For example you can specify a date range so that email or site documents that were created within the date ranged are placed on hold. A condition is logically connected to the keyword query (specified in the keyword box) by the AND operator. That means that items have to satisfy both the keyword query and the condition to be placed on hold.</span></span>

     <span data-ttu-id="ae163-172">如需建立搜尋查詢和使用情況的詳細資訊，請參閱[關鍵字查詢和搜尋條件的內容搜尋](https://docs.microsoft.com/en-us/office365/SecurityCompliance/keyword-queries-and-search-conditions)。</span><span class="sxs-lookup"><span data-stu-id="ae163-172">For more information about creating a search query and using conditions, see [Keyword queries and search conditions for Content Search](https://docs.microsoft.com/en-us/office365/SecurityCompliance/keyword-queries-and-search-conditions).</span></span>

  11. <span data-ttu-id="ae163-173">設定查詢式之後保留、 按一下 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="ae163-173">After configuring a query-based hold, click **Next**.</span></span>
 
  12. <span data-ttu-id="ae163-174">檢閱您的設定] 和 [**建立此保留**。</span><span class="sxs-lookup"><span data-stu-id="ae163-174">Review your settings, and then click **Create this hold**.</span></span>


## <a name="view-hold-statistics"></a><span data-ttu-id="ae163-175">檢視保留統計資料</span><span class="sxs-lookup"><span data-stu-id="ae163-175">View Hold Statistics</span></span>
<span data-ttu-id="ae163-p115">一些時間之後的新保留的相關資訊會顯示所選保留 [**保留**] 索引標籤的詳細資料窗格中。此資訊包含的信箱數目上的網站保留與已對內容的相關的統計資料保留，例如處於保留狀態的總人數及的項目大小和上次所計算的統計資料的保留。這些保留統計值能協助您識別要保留多少 eDiscovery 案例相關的內容。</span><span class="sxs-lookup"><span data-stu-id="ae163-p115">After some time, information about the new hold is displayed in the details pane on the **Holds** tab for the selected hold. This information includes the number of mailboxes and sites on hold and statistics about the content that was placed on hold, such as the total number and size of items placed on hold and the last time the hold statistics were calculated. These hold statistics help you identify how much content that's related to the eDiscovery case is being held.</span></span>

<span data-ttu-id="ae163-179">保留有關保留統計資料記住下列事項：</span><span class="sxs-lookup"><span data-stu-id="ae163-179">Keep the following things in mind about hold statistics:</span></span>

  - <span data-ttu-id="ae163-p116">保留的項目數總計會指出從保留的所有內容來源的項目數。如果您已建立查詢式保留功能，這次統計指出符合查詢的項目數。</span><span class="sxs-lookup"><span data-stu-id="ae163-p116">The total number of items on hold indicates the number of items from all content sources that are placed on hold. If you've created a query-based hold, this statistic indicates the number of items that match the query.</span></span>
  - <span data-ttu-id="ae163-p117">保留的項目數也包含編製索引的內容位置中找到的項目。如果您建立查詢式保留，內容的位置中的所有編製索引項目會放在保留的記事。這包括編製索引的項目不符合搜尋準則的查詢式保留及編製索引的項目可能屬於以外的日期範圍條件。這是與當您執行內容搜尋] 中編製索引的項目已不符合搜尋查詢或排除的日期範圍條件不包含在搜尋結果中有什麼不同。編製索引的項目相關的詳細資訊，請參閱 [Office 365 中的內容搜尋中部分索引項目] (https://docs.microsoft.com/en-us/office365/SecurityCompliance/partially-indexed-items-in-content-search)。</span><span class="sxs-lookup"><span data-stu-id="ae163-p117">The number of items on hold also includes unindexed items found in the content locations. Note that if you create a query-based hold, all unindexed items in the content locations are placed on hold. This includes unindexed items that don't match the search criteria of a query-based hold and unindexed items that might fall outside of a date range condition. This is different than what happens when you run a Content Search, in which unindexed items that don't match the search query or are excluded by a date range condition aren't included in the search results. For more information about unindexed items, see [Partially indexed items in Content Search in Office 365] (https://docs.microsoft.com/en-us/office365/SecurityCompliance/partially-indexed-items-in-content-search).</span></span> 
  - <span data-ttu-id="ae163-187">您可以透過按一下 [更新統計資料以重新執行計算保留的項目數目前的搜尋預估取得最新的保留統計資料。</span><span class="sxs-lookup"><span data-stu-id="ae163-187">You can get the latest hold statistics by clicking Update statistics to re-run a search estimate that calculates the current number of items on hold.</span></span>
  - <span data-ttu-id="ae163-188">若有必要，請按一下 [重新整理在工具列中要更新的詳細資料窗格中的保留統計資料。</span><span class="sxs-lookup"><span data-stu-id="ae163-188">If necessary, click Refresh in the toolbar to update the hold statistics in the details pane.</span></span>
  - <span data-ttu-id="ae163-189">因為其信箱或網站會保留使用者通常會傳送或接收新的電子郵件訊息和建立新的 SharePoint 和 OneDrive for Business 文件增加一段時間保留它的一般上的項目數目。</span><span class="sxs-lookup"><span data-stu-id="ae163-189">It's normal for the number of items on hold to increase over time because users whose mailbox or site is on hold are typically sending or receiving new email message and creating new SharePoint and OneDrive for Business documents.</span></span>

[!NOTE]
<span data-ttu-id="ae163-p118">如果當移至不同的區域在多個地理位置環境中的 SharePoint 網站或 OneDrive 帳戶時，該網站的統計資料將不會包含在保留統計資料。不過，在網站中的內容仍能音樂。此外，如果網站移至不同的區域不會更新顯示在保留中的 URL。您必須編輯保留及更新 URL。</span><span class="sxs-lookup"><span data-stu-id="ae163-p118">If a SharePoint site or OneDrive account is moved to a different region in a multi-geo environment, the statistics for that site won't be included in the hold statistics. However, the content in the site will still be on hold. Also, if a site is moved to a different region the URL that's displayed in the hold will not be updated. You'll have to edit the hold and update the URL.</span></span>

## <a name="faq"></a><span data-ttu-id="ae163-194">常見問題集</span><span class="sxs-lookup"><span data-stu-id="ae163-194">FAQ</span></span>
- <span data-ttu-id="ae163-p119">**如何 okay 以對應其他 Office 365 群組或 Microsoft 小組網站？與不住放置非-Custodial 暫止 Office 365 群組及 Microsoft 小組？** Office 365 群組之內建的 Microsoft 小組。因此，將其置於保留 eDiscovery 案例中是非常類似。將 Office 365 群組和上的 Microsoft 小組保留狀態時請記住下列事項。</span><span class="sxs-lookup"><span data-stu-id="ae163-p119">**How do I map an additional Office 365 Groups or Microsoft Teams site to a custodian? And what about placing a non-Custodial hold on Office 365 Groups and Microsoft Teams?** Microsoft Teams are built on Office 365 Groups. Therefore, placing them on hold in an eDiscovery case is very similar. Keep the following things in mind when placing Office 365 Groups and Microsoft Teams on hold.</span></span>
  - <span data-ttu-id="ae163-199">若要放置音樂位於 Office 365 群組及 Microsoft 小組中的內容，您必須指定的信箱與 SharePoint 網站的群組或小組與之相關聯。</span><span class="sxs-lookup"><span data-stu-id="ae163-199">To place content located in Office 365 Groups and Microsoft Teams on hold, you have to specify the mailbox and SharePoint site that associated with a group or team.</span></span>
  
  - <span data-ttu-id="ae163-p120">執行**Get UnifiedGroup** cmdlet 在 Exchange Online 中檢視 Office 365 群組或 Microsoft 小組的屬性。這是一個好方法來取得具有相關聯的 Office 365 群組或 Microsoft 小組網站的 URL。例如，下列命令會顯示所選的屬性名為資深領導小組 Office 365 群組：</span><span class="sxs-lookup"><span data-stu-id="ae163-p120">Run the **Get-UnifiedGroup** cmdlet in Exchange Online to view properties for an Office 365 Group or Microsoft Team. This is a good way to get the URL for the site that's associated with an Office 365 Group or a Microsoft Team. For example, the following command displays selected properties for an Office 365 Group named Senior Leadership Team:</span></span>

<span data-ttu-id="ae163-203">'' powershell</span><span class="sxs-lookup"><span data-stu-id="ae163-203">''' powershell</span></span>

    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    '''

 [!NOTE]
 <span data-ttu-id="ae163-204">若要執行 Get UnifiedGroup 指令程式，您必須指派 「 僅檢視收件者 」 角色在 Exchange Online 或角色群組的成員，已指派 「 僅檢視收件者 」 角色。</span><span class="sxs-lookup"><span data-stu-id="ae163-204">To run the Get-UnifiedGroup cmdlet, you have to be assigned the View-Only Recipients role in Exchange Online or be a member of a role group that's assigned the View-Only Recipients role.</span></span>

 - <span data-ttu-id="ae163-p121">當使用者的信箱搜尋時，將不會搜尋所有 Office 365 群組或使用者為其成員的 Microsoft 小組。同樣地，當撥打 Office 365 群組或 Microsoft 小組保留，只有群組信箱和群組網站會放在保留;信箱和 OneDrive for Business 網站群組成員的不處於保留狀態除非您明確地將其新增為 custodians 或將其資料來源保留。因此，如果您在會放置在 Office 365 群組或 Microsoft 小組需要保留特定 okay，請考慮將群組網站及群組信箱對應至 okay (請參閱管理 Custodians 進階 eDiscovery (Preview) 中)。如果 Office 365 群組或 Microsoft 小組不能歸因於單一 okay，請考慮新增至非-custodial 來源保留。</span><span class="sxs-lookup"><span data-stu-id="ae163-p121">When a user's mailbox is searched, any Office 365 Group or Microsoft Team that the user is a member of won't be searched. Similarly, when you place an Office 365 Group or Microsoft Team hold, only the group mailbox and group site are placed on hold; the mailboxes and OneDrive for Business sites of group members aren't placed on hold unless you explicitly add them as custodians or place their data sources hold. Therefore, if you the need to place an Office 365 Group or Microsoft Team on hold for a specific custodian, consider mapping the group site and group mailbox to the custodian (See Managing Custodians in Advanced eDiscovery (Preview)). If the Office 365 Group or Microsoft Team is not attributable to a single custodian, consider adding the source to a non-custodial hold.</span></span> 
 
 - <span data-ttu-id="ae163-p122">若要取得 Office 365 群組或 Microsoft 小組成員的清單，您可以在 Office 365 系統管理中心首頁 > 群組] 頁面上檢視屬性。或者，您可以在 Exchange Online PowerShell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ae163-p122">To get a list of the members of a Office 365 Group or Microsoft Team, you can view the properties on the Home > Groups page in the Office 365 admin center. Alternatively, you can run the following command in Exchange Online PowerShell:</span></span>

    <span data-ttu-id="ae163-211">'' powershell</span><span class="sxs-lookup"><span data-stu-id="ae163-211">''' powershell</span></span>
    
        Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
        '''

[!NOTE]
<span data-ttu-id="ae163-212">若要執行 Get UnifiedGroupLinks 指令程式，您必須指派 「 僅檢視收件者 」 角色在 Exchange Online 或角色群組的成員，已指派 「 僅檢視收件者 」 角色。</span><span class="sxs-lookup"><span data-stu-id="ae163-212">To run the Get-UnifiedGroupLinks cmdlet, you have to be assigned the View-Only Recipients role in Exchange Online or be a member of a role group that's assigned the View-Only Recipients role.</span></span>

- <span data-ttu-id="ae163-p123">屬於 Microsoft 小組通道的通道交談會儲存在具有小組與相關聯的信箱。同樣地，小組成員共用通道中的檔案都會儲存在團隊的 SharePoint 網站上。因此，您必須將 Microsoft 小組信箱和 SharePoint 網站上的保留要保留交談和通道中的檔案。</span><span class="sxs-lookup"><span data-stu-id="ae163-p123">Channel conversations that are part of a Microsoft Teams channel are stored in the mailbox that's associated with the Team. Similarly, files that team members share in a channel are stored on the team's SharePoint site. Therefore, you have to place the Microsoft Team mailbox and SharePoint site on hold to retain conversations and files in a channel.</span></span>
  
- <span data-ttu-id="ae163-p124">或者，是 [聊天室] 清單中的 Microsoft 小組的一部分的交談會儲存在信箱的使用者參與交談。 使用者共用聊天交談中的檔案儲存在 OneDrive for Business 網站共用檔案的使用者。因此，您必須將個別使用者信箱並 OneDrive for Business 網站上按住保留交談和在 [聊天室] 清單中的檔案。</span><span class="sxs-lookup"><span data-stu-id="ae163-p124">Alternatively, conversations that are part of the Chat list in Microsoft Teams are stored in the mailbox of the user's who participate in the chat.  Files that a user shares in Chat conversations are stored in the OneDrive for Business site of the user who shares the file. Therefore, you have to place the individual user mailboxes and OneDrive for Business sites on hold to retain conversations and files in the Chat list.</span></span> 
  
- <span data-ttu-id="ae163-p125">每個 Microsoft 小組或小組通道包含 Wiki 筆記記錄與共同作業。Wiki 內容會自動儲存至含有.mht 格式的檔案。此檔案儲存在團隊的 SharePoint 網站上的小組 Wiki 資料文件庫。您可以利用音樂 Wiki 內容所保留上放置團隊的 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="ae163-p125">Every Microsoft Team or team channel contains a Wiki for note-taking and collaboration. The Wiki content is automatically saved to a file with a .mht format. This file is stored in the Teams Wiki Data document library on the team's SharePoint site. You can place the content in the Wiki on hold by placing the team's SharePoint site on hold.</span></span>

[!Note]
<span data-ttu-id="ae163-p126">要保留的 Microsoft 小組或小組通道 Wiki 內容 （如果您保留上放置團隊的 SharePoint 網站） 的功能已於 2017 年 6 月 22 日發行。如果小組網站上保留，將啟動到期保留內容 wiki （英文）。不過，如果小組網站會保留與 Wiki 內容已遭刪除之前 2017 年 6 月 22 Wiki 內容已不會保留。</span><span class="sxs-lookup"><span data-stu-id="ae163-p126">The capability to retain Wiki content for a Microsoft Team or team channel (when you place the team's SharePoint site on hold) was released on June 22, 2017. If a team site is on hold, the Wiki content will be retained starting on that date. However, if a team site is on hold and the Wiki content was deleted before June 22, 2017, the Wiki content was not retained.</span></span>
   