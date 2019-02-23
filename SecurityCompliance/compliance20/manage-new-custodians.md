---
title: 管理進階的 eDiscovery （預覽） 案例中的 custodians
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 0c33335ecc103a97090dacaa769315ad9413b3c6
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214973"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-preview-case"></a><span data-ttu-id="861b3-102">管理進階的 eDiscovery （預覽） 案例中的 custodians</span><span class="sxs-lookup"><span data-stu-id="861b3-102">Manage custodians in an Advanced eDiscovery (Preview) case</span></span>

<span data-ttu-id="861b3-p101">[Custodians] 索引標籤包含案例中的所有 custodians 可排序的清單。Custodians 新增至案例之後，Azure Active Directory 中會自動收集有關每個 okay 的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="861b3-p101">The Custodians tab contains a sortable list of all the custodians in the case. After you add custodians to a case, details about each custodian will automatically be collected from Azure Active Directory.</span></span>

## <a name="viewing-custodian-details"></a><span data-ttu-id="861b3-105">檢視 okay 詳細資料</span><span class="sxs-lookup"><span data-stu-id="861b3-105">Viewing custodian details</span></span>

<span data-ttu-id="861b3-p102">含有 okay 詳細資料彈出式] 頁面隨即顯示之後將 okay 新增至案例並從 [ **Custodians** ] 索引標籤上的清單中加以選取。從這裡，您可以檢視該 okay 相關的所有詳細資料。彈出式頁面包含下列欄位：</span><span class="sxs-lookup"><span data-stu-id="861b3-p102">The flyout page that contains custodian details appears after you add a custodian to a case and select them from the list on the **Custodians** tab. From here, you can view all the details related to that custodian. The flyout page contains the following fields:</span></span>

- <span data-ttu-id="861b3-108">連絡人資訊</span><span class="sxs-lookup"><span data-stu-id="861b3-108">Contact information</span></span>

  - <span data-ttu-id="861b3-p103">**顯示名稱**： okay 顯示在通訊錄中的名稱。這通常是 okay 名字、 中間的初始和最後一個名稱的組合。</span><span class="sxs-lookup"><span data-stu-id="861b3-p103">**Display Name**: The name displayed in the address book for the custodian. This is usually the combination of the custodian’s first name, middle initial and last name.</span></span>
  - <span data-ttu-id="861b3-111">**郵件/SMTP**: okay，例如 jeff@contoso.onmicrosoft.com 的 SMTP 位址。</span><span class="sxs-lookup"><span data-stu-id="861b3-111">**Mail/SMTP**: The SMTP address for the custodian, for example, jeff@contoso.onmicrosoft.com.</span></span>  
  - <span data-ttu-id="861b3-112">**標題**： okay 的職稱。</span><span class="sxs-lookup"><span data-stu-id="861b3-112">**Title**: The custodian’s job title.</span></span>
  - <span data-ttu-id="861b3-113">**部門**： 部門 okay 運作方式的名稱。</span><span class="sxs-lookup"><span data-stu-id="861b3-113">**Department**: The name for the department in which the custodian works.</span></span>
  - <span data-ttu-id="861b3-p104">**Manager**: okay 的管理員。指定的管理員將會收到此 okay 任何呈報通訊。</span><span class="sxs-lookup"><span data-stu-id="861b3-p104">**Manager**: The custodian’s manager. The designated manager will receive any Escalation communications for this custodian.</span></span>
  
- <span data-ttu-id="861b3-116">位置資訊</span><span class="sxs-lookup"><span data-stu-id="861b3-116">Location information</span></span>

  - <span data-ttu-id="861b3-117">**縣/市**： okay 所在位置的城市。</span><span class="sxs-lookup"><span data-stu-id="861b3-117">**City**: The city in which the custodian is located.</span></span>
  - <span data-ttu-id="861b3-118">**狀態**： 位置的省或市 okay 地址。</span><span class="sxs-lookup"><span data-stu-id="861b3-118">**State**: The state or province in the custodian’s address.</span></span>
  - <span data-ttu-id="861b3-119">**國家 （地區）**： 在其中 okay 位於; 國家/地區例如，"US"或者"英國"。</span><span class="sxs-lookup"><span data-stu-id="861b3-119">**Country/Region**: The country/region in which the custodian’s is located; for example, “US” or “UK”.</span></span>
  - <span data-ttu-id="861b3-120">**Office**： 業務的 okay 就地的辦公室位置。</span><span class="sxs-lookup"><span data-stu-id="861b3-120">**Office**: The office location in the custodian’s place of business.</span></span>

- <span data-ttu-id="861b3-121">案例資訊</span><span class="sxs-lookup"><span data-stu-id="861b3-121">Case information</span></span>

  - <span data-ttu-id="861b3-122">**保留狀態**： 指出是否 okay 具有已處於保留狀態。</span><span class="sxs-lookup"><span data-stu-id="861b3-122">**Hold status**: Indicates if the custodian has been placed on hold.</span></span> 
  - <span data-ttu-id="861b3-p105">**通訊狀態**： 指出 okay 是否已發行的保留通知。如果已核發給 okay 請注意，這將會標示為*已發佈*。如果 okay 不已發行的通知，然後將此狀態*解除發佈*。</span><span class="sxs-lookup"><span data-stu-id="861b3-p105">**Communication status**: Indicates if the custodian has been issued a hold notice. If the custodian has been issued a notice, then this will be marked as *Published*. If the custodian has not been issued a notice, then this status will be *Un-Published*.</span></span> 
  - <span data-ttu-id="861b3-p106">**狀態**： okay 內大小寫的狀態。這是*Active* okay 時仍在保留案例。已從案例移除 okay 則及其狀態會變更為*發行*。</span><span class="sxs-lookup"><span data-stu-id="861b3-p106">**Status**: The status of the custodian within the case. This will be *Active* if the custodian is still on hold for the case. If a custodian is removed from a case, their status will change to *Released*.</span></span> 

- <span data-ttu-id="861b3-129">處理狀態</span><span class="sxs-lookup"><span data-stu-id="861b3-129">Processing status</span></span>

  - <span data-ttu-id="861b3-130">**編製索引狀態**： 指出深層索引工作的狀態。</span><span class="sxs-lookup"><span data-stu-id="861b3-130">**Indexing status**: Indicates the status of the deep indexing job.</span></span>  
  - <span data-ttu-id="861b3-131">**編製索引上次更新時間**： 指出的最後一個觸發深層索引工作 datestamp。</span><span class="sxs-lookup"><span data-stu-id="861b3-131">**Indexing Last Updated Time**: Indicates the datestamp of when the deep indexing job was last triggered.</span></span>
  - <span data-ttu-id="861b3-132">**資料來源**： 顯示的信箱、 網站和小組已選取的 okay 計數。</span><span class="sxs-lookup"><span data-stu-id="861b3-132">**Data sources**: Shows the count of mailboxes, sites, and Teams that have been selected for the custodian.</span></span>

## <a name="updating-a-custodian"></a><span data-ttu-id="861b3-133">更新 okay</span><span class="sxs-lookup"><span data-stu-id="861b3-133">Updating a custodian</span></span>

<span data-ttu-id="861b3-p107">隨著您案例的進度，您可能會發現可能有其他資料來源相關的特定 okay & 您的案例。在其他情況下，可能會想要移除特定資料來源的檢閱和視為不相關。</span><span class="sxs-lookup"><span data-stu-id="861b3-p107">As your case progresses, you may discover that there may be additional data sources relevant to a specific custodian & your case. In other scenarios, you may want to remove certain data sources that have been reviewed and deemed as not relevant.</span></span>

<span data-ttu-id="861b3-136">若要更新 okay 及選取的資料來源：</span><span class="sxs-lookup"><span data-stu-id="861b3-136">To update a custodian and the selected data sources:</span></span>

1. <span data-ttu-id="861b3-137">從**eDiscovery > 進階的 eDiscovery (Preview)** 中選取現有的案例。</span><span class="sxs-lookup"><span data-stu-id="861b3-137">Select an existing case from the **eDiscovery > Advanced eDiscovery (Preview)**.</span></span>
  
2. <span data-ttu-id="861b3-138">情況下，按一下 [ **Custodians**索引標籤。</span><span class="sxs-lookup"><span data-stu-id="861b3-138">In the case, click the **Custodians** tab.</span></span>
  
3. <span data-ttu-id="861b3-139">從清單中選取 custodian(s) 並按一下 [**編輯來源**。</span><span class="sxs-lookup"><span data-stu-id="861b3-139">Select the custodian(s) from the list and click **Edit sources**.</span></span>
  
4. <span data-ttu-id="861b3-140">依序按一下 [**選擇資料來源**中更新 Exchange 和 OneDrive 位置的選項。</span><span class="sxs-lookup"><span data-stu-id="861b3-140">Update selections for Exchange and OneDrive locations by clicking **Choose data sources**.</span></span>
  
5. <span data-ttu-id="861b3-p108">新增或移除小組、 SharePoint、 或 Exchange 信箱對應使用者按一下以**選取其他資料來源**。如需您可以將對應的資料來源以 okay 的方式的詳細資訊，請參閱 ＜ [Add custodians 案例](add-custodians-to-case.md)。</span><span class="sxs-lookup"><span data-stu-id="861b3-p108">Add or remove Teams, SharePoint, or Exchange mailboxes mapped the user by clicking to **Select additional data sources**. For more information about how you to map data sources to a custodian, see [Add custodians to a case](add-custodians-to-case.md).</span></span>
  
6. <span data-ttu-id="861b3-143">若要更新之 okay 持有狀態，按一下 [ **custodial 就地保留**，並啟用或停用 custodians 保留。</span><span class="sxs-lookup"><span data-stu-id="861b3-143">To update the custodian hold status, click **Place custodial holds**, and enable or disable the hold for custodians.</span></span>

> [!TIP]
> <span data-ttu-id="861b3-144">您可以選取多個 custodians 執行大量動作，像重新編製索引、 釋放，或編輯 custodians 一組。</span><span class="sxs-lookup"><span data-stu-id="861b3-144">You can select multiple custodians to perform bulk actions, like re-indexing, releasing, or editing a set of custodians.</span></span>

## <a name="resolving-custodian-processing-errors"></a><span data-ttu-id="861b3-145">協助您解決 okay 處理錯誤</span><span class="sxs-lookup"><span data-stu-id="861b3-145">Resolving custodian processing errors</span></span>

<span data-ttu-id="861b3-p109">大部分的法律工作流程的 custodians 新增針對特定的調查之後, 會搜尋之使用者的資料子集。因為大型檔案大小或可能損毀、 custodians 的資料來源中的某些項目可能是部分編製索引。使用 「 進階的 eDiscovery （預覽） 深層索引 」 功能，這些部分已編製索引的項目可以是自動在於重新編目，並重新編製索引隨選這些項目。</span><span class="sxs-lookup"><span data-stu-id="861b3-p109">In most Legal workflows, after custodians are added for a specific investigation, a subset of the users’ data will be searched. Due to large file sizes or possible corruption, some items within the custodians’ data sources may be partially indexed. Using the Advanced eDiscovery (Preview) deep indexing capability, these partially indexed items can be automatically remediated by re-crawling and re-indexing these items on demand.</span></span> 

<span data-ttu-id="861b3-p110">當 okay 加入至案例時，自己的資料將會自動為"deep 編製索引 」，讓使用者能夠部分保留這些編製索引而不需要下載、 修復及重新執行搜尋 Office 365 外部的進行中的項目。案例的技術支援週期期間的使用者可能會修復項目或新增新的資料來源的特定 okay。這可能需要更新 Okay 索引。</span><span class="sxs-lookup"><span data-stu-id="861b3-p110">When a custodian is added to a case, their data will automatically be "deep indexed”, allowing users to leave these partially indexed items in place instead of having to download, remediate and re-run searches outside of Office 365. During the lifecycle of a case, a user may remediate items or add new data sources for a given custodian. This may require the Custodian Index to be updated.</span></span> 

<span data-ttu-id="861b3-152">若要觸發重新索引程序，以地址部分編製索引的項目：</span><span class="sxs-lookup"><span data-stu-id="861b3-152">To trigger a re-indexing process to address partially indexed items:</span></span>

1. <span data-ttu-id="861b3-153">移至**eDiscovery > 進階的 eDiscovery （預覽）** 並選取現有的案例。</span><span class="sxs-lookup"><span data-stu-id="861b3-153">Go to **eDiscovery > Advanced eDiscovery (Preview)** and select an existing case.</span></span>

2. <span data-ttu-id="861b3-154">在案例中，按一下 [ **Custodians] 索引標籤**。</span><span class="sxs-lookup"><span data-stu-id="861b3-154">In the case, click to **Custodians tab**.</span></span> 

3. <span data-ttu-id="861b3-155">選取需要重新編製索引，custodian(s) 然後再按一下 [彈出式頁面上的 [**更新索引**。</span><span class="sxs-lookup"><span data-stu-id="861b3-155">Select the custodian(s) that needs to be re-indexed, and then click **Update index** on the flyout page.</span></span>

4. <span data-ttu-id="861b3-156">按一下連結**Custodians** ] 索引標籤上的 [**編製索引工作狀態**] 欄中檢查 okay 索引的狀態。</span><span class="sxs-lookup"><span data-stu-id="861b3-156">Check the status of the custodian index by clicking the link in the **Indexing job Status** column on the **Custodians** tab.</span></span>  

5. <span data-ttu-id="861b3-157">也可以在 [**工作**] 索引標籤上追蹤重新索引程序的狀態。</span><span class="sxs-lookup"><span data-stu-id="861b3-157">The status for the re-indexing process can also be tracked on the **Jobs** tab.</span></span>

<span data-ttu-id="861b3-158">如需重新索引及補救部分已編製索引項目的詳細資訊，請參閱[修正處理錯誤](processing-data-for-case.md)。</span><span class="sxs-lookup"><span data-stu-id="861b3-158">For more information about re-indexing and remediating partially indexed items, see [Fix processing errors](processing-data-for-case.md).</span></span>

## <a name="releasing-a-custodian-from-a-case"></a><span data-ttu-id="861b3-159">釋放 okay 從案例</span><span class="sxs-lookup"><span data-stu-id="861b3-159">Releasing a custodian from a case</span></span>

<span data-ttu-id="861b3-160">Okay 發行情況其中關閉案例、 okay 不再下義務来保留內容的案例中，或當 okay 已被視為不會再是相關內容為特定案例。</span><span class="sxs-lookup"><span data-stu-id="861b3-160">A custodian is released in situations where a case is closed, a custodian is no longer under obligation to preserve content for a case, or when a custodian is deemed to no longer be relevant to a particular case.</span></span> 

<span data-ttu-id="861b3-p111">如果已發佈的保留通知後釋放 okay 版本通知將會傳送至 okay。此外，也會移除對應到發行的 custodians 任何 custodial 保留。</span><span class="sxs-lookup"><span data-stu-id="861b3-p111">If you release a custodian after a hold notice was published, a release notice will be sent to the custodian. In addition, any custodial holds attributed to the released custodians will also be removed.</span></span>

<span data-ttu-id="861b3-163">如果 okay 被指定無訊息保留其已不發出任何合法持有通知，將會移除對應到發行的 custodians 任何 custodial 保留。</span><span class="sxs-lookup"><span data-stu-id="861b3-163">If the custodian was placed on a silent hold, where they were not issued any legal hold notifications, then any custodial holds attributed to the released custodians will be removed.</span></span>  

<span data-ttu-id="861b3-164">若要發行 okay:</span><span class="sxs-lookup"><span data-stu-id="861b3-164">To release a custodian:</span></span> 

1.  <span data-ttu-id="861b3-165">移至 [ **Custodians** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="861b3-165">Go to the **Custodians** tab.</span></span>

2.  <span data-ttu-id="861b3-166">從清單中選取 okay 並按一下**版本 custodians**彈出式頁面上。</span><span class="sxs-lookup"><span data-stu-id="861b3-166">Select the custodian from the list and click **Release custodians** on the flyout page.</span></span>

    <span data-ttu-id="861b3-167">Okay **Custodians** ] 索引標籤上的狀態設為**發行**和**保留狀態**彈出式] 頁面上會變更為**非使用中**。</span><span class="sxs-lookup"><span data-stu-id="861b3-167">The status of the custodian on the **Custodians** tab is set to **Released** and the **Hold status** on the flyout page is changed to **Inactive**.</span></span> 

> [!TIP]
> <span data-ttu-id="861b3-p112">Okay 可能同時也會參與數個合法持有不僅。當 okay 發行從案例時，不會影響 [保留] 及 [其他不僅不同的通知。</span><span class="sxs-lookup"><span data-stu-id="861b3-p112">A custodian might be simultaneously be involved in several legal hold matters. When a custodian is released from a case, the holds and notifications across other matters will not be impacted.</span></span>

## <a name="related-information"></a><span data-ttu-id="861b3-170">相關資訊</span><span class="sxs-lookup"><span data-stu-id="861b3-170">Related information</span></span>

 - [<span data-ttu-id="861b3-171">處理資料時發生補救錯誤</span><span class="sxs-lookup"><span data-stu-id="861b3-171">Error remediation when processing data</span></span>](error-remediation.md) 
- [<span data-ttu-id="861b3-172">使用通訊</span><span class="sxs-lookup"><span data-stu-id="861b3-172">Work with communications</span></span>](managing-custodian-communications.md)
