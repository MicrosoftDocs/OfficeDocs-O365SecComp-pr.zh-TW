---
title: 管理 custodians 進階電子文件 （預覽） 案例中
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
ms.openlocfilehash: 6a21240f71c64f244ee42c3d3a2ed9d75381edaa
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/06/2019
ms.locfileid: "30454935"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-preview-case"></a><span data-ttu-id="e3475-102">管理 custodians 進階電子文件 （預覽） 案例中</span><span class="sxs-lookup"><span data-stu-id="e3475-102">Manage custodians in an Advanced eDiscovery (Preview) case</span></span>

<span data-ttu-id="e3475-103">[Custodians] 索引標籤包含的情況下的所有 custodians 排序清單。</span><span class="sxs-lookup"><span data-stu-id="e3475-103">The Custodians tab contains a sortable list of all the custodians in the case.</span></span> <span data-ttu-id="e3475-104">Custodians 新增至案例之後，從 Azure Active Directory 會自動收集有關每個 custodian 的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="e3475-104">After you add custodians to a case, details about each custodian will automatically be collected from Azure Active Directory.</span></span>

![管理 Custodians](../media/CustodianDetails.PNG)

## <a name="viewing-custodian-details"></a><span data-ttu-id="e3475-106">檢視 custodian 詳細資料</span><span class="sxs-lookup"><span data-stu-id="e3475-106">Viewing custodian details</span></span>

<span data-ttu-id="e3475-107">之後您將 custodian 新增至案例及**Custodians** ] 索引標籤上，從清單中選取他們，會出現包含 custodian 詳細資料彈出式頁面。從這裡開始，您可以檢視該 custodian 與相關的所有詳細資料。</span><span class="sxs-lookup"><span data-stu-id="e3475-107">The flyout page that contains custodian details appears after you add a custodian to a case and select them from the list on the **Custodians** tab. From here, you can view all the details related to that custodian.</span></span> <span data-ttu-id="e3475-108">彈出式頁面包含下列欄位：</span><span class="sxs-lookup"><span data-stu-id="e3475-108">The flyout page contains the following fields:</span></span>

- <span data-ttu-id="e3475-109">連絡人資訊</span><span class="sxs-lookup"><span data-stu-id="e3475-109">Contact information</span></span>

  - <span data-ttu-id="e3475-110">**顯示名稱**： custodian 顯示在通訊錄中的名稱。</span><span class="sxs-lookup"><span data-stu-id="e3475-110">**Display Name**: The name displayed in the address book for the custodian.</span></span> <span data-ttu-id="e3475-111">這通常是 custodian 名字]、 [中間的初始和最後一個名稱的組合。</span><span class="sxs-lookup"><span data-stu-id="e3475-111">This is usually the combination of the custodian’s first name, middle initial and last name.</span></span>
  - <span data-ttu-id="e3475-112">**郵件/SMTP**: custodian，例如 jeff@contoso.onmicrosoft.com 的 SMTP 位址。</span><span class="sxs-lookup"><span data-stu-id="e3475-112">**Mail/SMTP**: The SMTP address for the custodian, for example, jeff@contoso.onmicrosoft.com.</span></span>  
  - <span data-ttu-id="e3475-113">**標題**： custodian 的職稱。</span><span class="sxs-lookup"><span data-stu-id="e3475-113">**Title**: The custodian’s job title.</span></span>
  - <span data-ttu-id="e3475-114">**部門**： custodian 適用於部門的名稱。</span><span class="sxs-lookup"><span data-stu-id="e3475-114">**Department**: The name for the department in which the custodian works.</span></span>
  - <span data-ttu-id="e3475-115">**管理員**： custodian 的管理員。</span><span class="sxs-lookup"><span data-stu-id="e3475-115">**Manager**: The custodian’s manager.</span></span> <span data-ttu-id="e3475-116">指定的管理員會收到此 custodian 任何呈報通訊。</span><span class="sxs-lookup"><span data-stu-id="e3475-116">The designated manager will receive any Escalation communications for this custodian.</span></span>
  
- <span data-ttu-id="e3475-117">位置資訊</span><span class="sxs-lookup"><span data-stu-id="e3475-117">Location information</span></span>

  - <span data-ttu-id="e3475-118">**縣/市**： custodian 所在的市/鎮。</span><span class="sxs-lookup"><span data-stu-id="e3475-118">**City**: The city in which the custodian is located.</span></span>
  - <span data-ttu-id="e3475-119">**狀態**： 縣 / 市 custodian 的地址。</span><span class="sxs-lookup"><span data-stu-id="e3475-119">**State**: The state or province in the custodian’s address.</span></span>
  - <span data-ttu-id="e3475-120">**國家/地區**： 於 custodian 所在; 國家/地區例如，「 美國 」 或者 「 英國 」。</span><span class="sxs-lookup"><span data-stu-id="e3475-120">**Country/Region**: The country/region in which the custodian’s is located; for example, “US” or “UK”.</span></span>
  - <span data-ttu-id="e3475-121">**Office**： 商務版 custodian 就地的辦公室位置。</span><span class="sxs-lookup"><span data-stu-id="e3475-121">**Office**: The office location in the custodian’s place of business.</span></span>

- <span data-ttu-id="e3475-122">案例資訊</span><span class="sxs-lookup"><span data-stu-id="e3475-122">Case information</span></span>

  - <span data-ttu-id="e3475-123">**保留狀態**： 指出是否 custodian 具有已處於保留狀態。</span><span class="sxs-lookup"><span data-stu-id="e3475-123">**Hold status**: Indicates if the custodian has been placed on hold.</span></span> 
  - <span data-ttu-id="e3475-124">**通訊狀態**： 指出 custodian 是否已經發出保留通知。</span><span class="sxs-lookup"><span data-stu-id="e3475-124">**Communication status**: Indicates if the custodian has been issued a hold notice.</span></span> <span data-ttu-id="e3475-125">如果 custodian 已發出的通知，這會被標示為*已發佈*。</span><span class="sxs-lookup"><span data-stu-id="e3475-125">If the custodian has been issued a notice, then this will be marked as *Published*.</span></span> <span data-ttu-id="e3475-126">如果 custodian 已不發出通知，則此狀態將會是*未發佈*。</span><span class="sxs-lookup"><span data-stu-id="e3475-126">If the custodian has not been issued a notice, then this status will be *Un-Published*.</span></span> 
  - <span data-ttu-id="e3475-127">**狀態**： 在 case custodian 的狀態。</span><span class="sxs-lookup"><span data-stu-id="e3475-127">**Status**: The status of the custodian within the case.</span></span> <span data-ttu-id="e3475-128">如果 custodian 仍處於保留的情況下，這會是*作用中*。</span><span class="sxs-lookup"><span data-stu-id="e3475-128">This will be *Active* if the custodian is still on hold for the case.</span></span> <span data-ttu-id="e3475-129">如果從案例移除 custodian，其狀態會變更為*發行*。</span><span class="sxs-lookup"><span data-stu-id="e3475-129">If a custodian is removed from a case, their status will change to *Released*.</span></span> 

- <span data-ttu-id="e3475-130">處理狀態</span><span class="sxs-lookup"><span data-stu-id="e3475-130">Processing status</span></span>

  - <span data-ttu-id="e3475-131">**編製索引狀態**： 指出深層索引工作的狀態。</span><span class="sxs-lookup"><span data-stu-id="e3475-131">**Indexing status**: Indicates the status of the deep indexing job.</span></span>  
  - <span data-ttu-id="e3475-132">**編製索引上次更新時間**： 指出的深層索引工作最後觸發 datestamp。</span><span class="sxs-lookup"><span data-stu-id="e3475-132">**Indexing Last Updated Time**: Indicates the datestamp of when the deep indexing job was last triggered.</span></span>
  - <span data-ttu-id="e3475-133">**資料來源**： 顯示的信箱、 網站和小組 custodian 已選取的計數。</span><span class="sxs-lookup"><span data-stu-id="e3475-133">**Data sources**: Shows the count of mailboxes, sites, and Teams that have been selected for the custodian.</span></span>

## <a name="editing-a-custodian"></a><span data-ttu-id="e3475-134">編輯 custodian</span><span class="sxs-lookup"><span data-stu-id="e3475-134">Editing a custodian</span></span>

<span data-ttu-id="e3475-135">隨著您案例的進度，您可能會發現可能有其他資料來源相關的特定 custodian & 您的案例。</span><span class="sxs-lookup"><span data-stu-id="e3475-135">As your case progresses, you may discover that there may be additional data sources relevant to a specific custodian & your case.</span></span> <span data-ttu-id="e3475-136">在其他情況下，您可能想要移除特定資料來源的檢閱和視為不相關。</span><span class="sxs-lookup"><span data-stu-id="e3475-136">In other scenarios, you may want to remove certain data sources that have been reviewed and deemed as not relevant.</span></span>

<span data-ttu-id="e3475-137">若要更新 custodian 及選取的資料來源：</span><span class="sxs-lookup"><span data-stu-id="e3475-137">To update a custodian and the selected data sources:</span></span>

1. <span data-ttu-id="e3475-138">從**eDiscovery > 進階電子文件 （預覽）** 中選取現有的案例。</span><span class="sxs-lookup"><span data-stu-id="e3475-138">Select an existing case from the **eDiscovery > Advanced eDiscovery (Preview)**.</span></span>
  
2. <span data-ttu-id="e3475-139">在案例中，按一下 [ **Custodians** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="e3475-139">In the case, click the **Custodians** tab.</span></span>
  
3. <span data-ttu-id="e3475-140">從清單中選取 custodian(s)，然後按一下 [**編輯來源**。</span><span class="sxs-lookup"><span data-stu-id="e3475-140">Select the custodian(s) from the list and click **Edit sources**.</span></span>

    ![編輯資料來源](../media/EditCustodianDataSource.PNG)
  
4. <span data-ttu-id="e3475-142">按一下 [**選擇資料來源**，更新 Exchange 和 OneDrive 位置的選項。</span><span class="sxs-lookup"><span data-stu-id="e3475-142">Update selections for Exchange and OneDrive locations by clicking **Choose data sources**.</span></span>
  
5. <span data-ttu-id="e3475-143">新增或移除 microsoft Teams、 SharePoint 或 Exchange 信箱]，即可選取**其他資料來源**對應的使用者。</span><span class="sxs-lookup"><span data-stu-id="e3475-143">Add or remove Teams, SharePoint, or Exchange mailboxes mapped the user by clicking to **Select additional data sources**.</span></span> <span data-ttu-id="e3475-144">如需您可以將對應的資料來源到 custodian 的方式的詳細資訊，請參閱 < <b0>Add custodians 案例</b0>。</span><span class="sxs-lookup"><span data-stu-id="e3475-144">For more information about how you to map data sources to a custodian, see [Add custodians to a case](add-custodians-to-case.md).</span></span>
  
6. <span data-ttu-id="e3475-145">若要更新的 custodian 持有狀態，按一下 [ **custodial 就地保留**，以及啟用或停用 custodians 保留。</span><span class="sxs-lookup"><span data-stu-id="e3475-145">To update the custodian hold status, click **Place custodial holds**, and enable or disable the hold for custodians.</span></span>

> [!TIP]
> <span data-ttu-id="e3475-146">您可以選取多個 custodians 來執行 [大量動作]，或重新編製索引，放開，編輯一群 custodians 等。</span><span class="sxs-lookup"><span data-stu-id="e3475-146">You can select multiple custodians to perform bulk actions, like re-indexing, releasing, or editing a set of custodians.</span></span>

## <a name="resolving-custodian-processing-errors"></a><span data-ttu-id="e3475-147">解決 custodian 處理錯誤</span><span class="sxs-lookup"><span data-stu-id="e3475-147">Resolving custodian processing errors</span></span>

<span data-ttu-id="e3475-148">大部分合法的工作流程，即會為特定的調查，新增 custodians 之後會搜尋使用者的資料子集。</span><span class="sxs-lookup"><span data-stu-id="e3475-148">In most Legal workflows, after custodians are added for a specific investigation, a subset of the users’ data will be searched.</span></span> <span data-ttu-id="e3475-149">因為大型檔案的大小或可能損毀，custodians 的資料來源中的某些項目可能是已局部編製索引。</span><span class="sxs-lookup"><span data-stu-id="e3475-149">Due to large file sizes or possible corruption, some items within the custodians’ data sources may be partially indexed.</span></span> <span data-ttu-id="e3475-150">使用進階電子文件 （預覽） 深層索引功能，這些已局部編製索引的項目可進行自動修復重新編目和重新編製索引視需要這些項目。</span><span class="sxs-lookup"><span data-stu-id="e3475-150">Using the Advanced eDiscovery (Preview) deep indexing capability, these partially indexed items can be automatically remediated by re-crawling and re-indexing these items on demand.</span></span> 

<span data-ttu-id="e3475-151">當 custodian 新增至案例時，其資料將會自動為 「 deep 編製索引 」 時，允許使用者離開這些已局部編製索引而不必下載、 修正，並重新執行搜尋 Office 365 以外的位置中的項目。</span><span class="sxs-lookup"><span data-stu-id="e3475-151">When a custodian is added to a case, their data will automatically be "deep indexed”, allowing users to leave these partially indexed items in place instead of having to download, remediate and re-run searches outside of Office 365.</span></span> <span data-ttu-id="e3475-152">週期中的情況下，使用者可能修復項目，或指定 custodian 新增新的資料來源。</span><span class="sxs-lookup"><span data-stu-id="e3475-152">During the lifecycle of a case, a user may remediate items or add new data sources for a given custodian.</span></span> <span data-ttu-id="e3475-153">這可能需要更新 Custodian 索引。</span><span class="sxs-lookup"><span data-stu-id="e3475-153">This may require the Custodian Index to be updated.</span></span> 

<span data-ttu-id="e3475-154">若要觸發地址重新編製索引程序已局部編製索引的項目：</span><span class="sxs-lookup"><span data-stu-id="e3475-154">To trigger a re-indexing process to address partially indexed items:</span></span>

1. <span data-ttu-id="e3475-155">移至**eDiscovery > 進階電子文件 （預覽）** ，然後選取現有的案例。</span><span class="sxs-lookup"><span data-stu-id="e3475-155">Go to **eDiscovery > Advanced eDiscovery (Preview)** and select an existing case.</span></span>

2. <span data-ttu-id="e3475-156">在案例中，按一下 [ **Custodians] 索引標籤**。</span><span class="sxs-lookup"><span data-stu-id="e3475-156">In the case, click to **Custodians tab**.</span></span> 

3. <span data-ttu-id="e3475-157">選取 [需要以重新建立索引，然後按一下 [custodian(s)</span><span class="sxs-lookup"><span data-stu-id="e3475-157">Select the custodian(s) that needs to be re-indexed, and then click</span></span> ![更新索引](../media/UpdateIndex.PNG) <span data-ttu-id="e3475-159">在彈出式頁面。</span><span class="sxs-lookup"><span data-stu-id="e3475-159">on the flyout page.</span></span>

4. <span data-ttu-id="e3475-160">**Custodians** ] 索引標籤上的 [**編製索引工作狀態**] 欄中的連結，即可檢查 custodian 索引的狀態。</span><span class="sxs-lookup"><span data-stu-id="e3475-160">Check the status of the custodian index by clicking the link in the **Indexing job Status** column on the **Custodians** tab.</span></span>  

5. <span data-ttu-id="e3475-161">在 [**工作**] 索引標籤上也可以追蹤重新編製索引的程序的狀態。</span><span class="sxs-lookup"><span data-stu-id="e3475-161">The status for the re-indexing process can also be tracked on the **Jobs** tab.</span></span>

<span data-ttu-id="e3475-162">如需重新編製索引和補救局部編製索引的項目的詳細資訊，請參閱[修正處理錯誤](processing-data-for-case.md)。</span><span class="sxs-lookup"><span data-stu-id="e3475-162">For more information about re-indexing and remediating partially indexed items, see [Fix processing errors](processing-data-for-case.md).</span></span>

## <a name="releasing-a-custodian-from-a-case"></a><span data-ttu-id="e3475-163">釋放 custodian 從案例</span><span class="sxs-lookup"><span data-stu-id="e3475-163">Releasing a custodian from a case</span></span>

<span data-ttu-id="e3475-164">Custodian 發行的情況下其中關閉案例、 custodian 不再下義務以保留內容的情況下，或當 custodian 會被視為不會再是相關為特定案例。</span><span class="sxs-lookup"><span data-stu-id="e3475-164">A custodian is released in situations where a case is closed, a custodian is no longer under obligation to preserve content for a case, or when a custodian is deemed to no longer be relevant to a particular case.</span></span> 

<span data-ttu-id="e3475-165">如果已發佈保留通知之後，您就會釋放 custodian，發行通知會傳送至 custodian。</span><span class="sxs-lookup"><span data-stu-id="e3475-165">If you release a custodian after a hold notice was published, a release notice will be sent to the custodian.</span></span> <span data-ttu-id="e3475-166">此外，也會移除歸因於發行 custodians 任何 custodial 保留。</span><span class="sxs-lookup"><span data-stu-id="e3475-166">In addition, any custodial holds attributed to the released custodians will also be removed.</span></span>

<span data-ttu-id="e3475-167">如果 custodian 已處於暫止無訊息狀態，其所未發出任何合法持有通知，然後將移除歸因於發行 custodians 任何 custodial 保留。</span><span class="sxs-lookup"><span data-stu-id="e3475-167">If the custodian was placed on a silent hold, where they were not issued any legal hold notifications, then any custodial holds attributed to the released custodians will be removed.</span></span>  

<span data-ttu-id="e3475-168">若要發行 custodian:</span><span class="sxs-lookup"><span data-stu-id="e3475-168">To release a custodian:</span></span> 

1.  <span data-ttu-id="e3475-169">移至 [ **Custodians** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="e3475-169">Go to the **Custodians** tab.</span></span>

2.  <span data-ttu-id="e3475-170">從清單中選取 custodian，然後按一下 [</span><span class="sxs-lookup"><span data-stu-id="e3475-170">Select the custodian from the list and click</span></span> ![版本 Custodian](../media/ReleaseCustodian.PNG) <span data-ttu-id="e3475-172">在彈出式頁面。</span><span class="sxs-lookup"><span data-stu-id="e3475-172">on the flyout page.</span></span>

    <span data-ttu-id="e3475-173">Custodian **Custodians** ] 索引標籤上的狀態設為**已發行**並**保留狀態**的彈出式頁面變更為**非作用中**。</span><span class="sxs-lookup"><span data-stu-id="e3475-173">The status of the custodian on the **Custodians** tab is set to **Released** and the **Hold status** on the flyout page is changed to **Inactive**.</span></span> 

> [!TIP]
> <span data-ttu-id="e3475-174">Custodian 可同時可能參與數個合法持有事件。</span><span class="sxs-lookup"><span data-stu-id="e3475-174">A custodian might be simultaneously be involved in several legal hold matters.</span></span> <span data-ttu-id="e3475-175">當 custodian 發行從案例時，不會影響保留和跨其他事件通知。</span><span class="sxs-lookup"><span data-stu-id="e3475-175">When a custodian is released from a case, the holds and notifications across other matters will not be impacted.</span></span>

## <a name="related-information"></a><span data-ttu-id="e3475-176">相關資訊</span><span class="sxs-lookup"><span data-stu-id="e3475-176">Related information</span></span>

 - [<span data-ttu-id="e3475-177">處理資料時發生補救錯誤</span><span class="sxs-lookup"><span data-stu-id="e3475-177">Error remediation when processing data</span></span>](error-remediation.md) 
- [<span data-ttu-id="e3475-178">使用通訊</span><span class="sxs-lookup"><span data-stu-id="e3475-178">Work with communications</span></span>](managing-custodian-communications.md)
