---
title: 稽核共用來找出與外部使用者共用的資源
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 2/13/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- BCS160
- MET150
ms.assetid: 50bbf89f-7870-4c2a-ae14-42635e0cfc01
description: '共用是 SharePoint Online 和商務用 OneDrive 中的主要活動。 系統管理員現在可以使用 Office 365 稽核記錄檔中的共用稽核來判斷如何共用正在使用其組織中。 '
ms.openlocfilehash: 08b511acdf74edac5b2d595d1b60bdd84d630918
ms.sourcegitcommit: 6c9340e4eb221bf81472ff3f1ae25ae21aaf5297
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/11/2019
ms.locfileid: "31813944"
---
# <a name="use-sharing-auditing-in-the-office-365-audit-log"></a><span data-ttu-id="ea74a-104">稽核共用來找出與外部使用者共用的資源</span><span class="sxs-lookup"><span data-stu-id="ea74a-104">Use sharing auditing in the Office 365 audit log</span></span>

<span data-ttu-id="ea74a-105">共用是 SharePoint Online 和商務用 OneDrive 中的主要活動，它廣泛用在 Office 365 組織。</span><span class="sxs-lookup"><span data-stu-id="ea74a-105">Sharing is a key activity in SharePoint Online and OneDrive for Business, and it's widely used in Office 365 organizations.</span></span> <span data-ttu-id="ea74a-106">系統管理員現在可以使用 Office 365 稽核記錄檔中的共用稽核來判斷如何共用正在使用其組織中。</span><span class="sxs-lookup"><span data-stu-id="ea74a-106">Administrators can now use sharing auditing in the Office 365 audit log to determine how sharing is being used in their organization.</span></span> 
  
## <a name="the-sharepoint-sharing-schema"></a><span data-ttu-id="ea74a-107">SharePoint 共用結構描述</span><span class="sxs-lookup"><span data-stu-id="ea74a-107">The SharePoint Sharing schema</span></span>

<span data-ttu-id="ea74a-108">共用事件 （排除的共用原則和共用連結的事件） 中主要的一種方式是不同的檔案和資料夾相關的事件： 一個使用者所要採取一些效果在另一位使用者的動作。</span><span class="sxs-lookup"><span data-stu-id="ea74a-108">Sharing events (excluding sharing policy and sharing link events) are different from file- and folder-related events in one primary way: one user is taking an action that has some effect on another user.</span></span> <span data-ttu-id="ea74a-109">例如，使用者 A 可讓使用者 B 存取檔案。</span><span class="sxs-lookup"><span data-stu-id="ea74a-109">For example, User A gives User B access to a file.</span></span> <span data-ttu-id="ea74a-110">在這個範例中，使用者 A 的*做使用者*且使用者 B 是*目標使用者*。</span><span class="sxs-lookup"><span data-stu-id="ea74a-110">In this example, User A is the  *acting user*  and User B is the  *target user*.</span></span> <span data-ttu-id="ea74a-111">在 SharePoint 檔案結構描述中之使用者的巨集指令只會影響檔案本身。</span><span class="sxs-lookup"><span data-stu-id="ea74a-111">In the SharePoint File schema, the acting user's action only affects the file itself.</span></span> <span data-ttu-id="ea74a-112">當使用者開啟檔案，僅**FileAccessed**事件中所需的資訊是影響之使用者。</span><span class="sxs-lookup"><span data-stu-id="ea74a-112">When User A opens a file, the only information needed in the **FileAccessed** event is the acting user.</span></span> <span data-ttu-id="ea74a-113">若要解決這項差異，沒有個別結構描述，稱為*SharePoint 共用結構描述*，會擷取共用事件的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="ea74a-113">To address this difference, there is a separate schema, called the  *SharePoint Sharing schema*, that captures more information about sharing events.</span></span> <span data-ttu-id="ea74a-114">這可確保系統管理員有更深入的人員共用資源和使用者資源共用的。</span><span class="sxs-lookup"><span data-stu-id="ea74a-114">This ensures that administrators have more insight into who shared a resource and the user the resource was shared with.</span></span> 
  
<span data-ttu-id="ea74a-115">共用結構描述提供兩個額外的欄位與共用事件相關的稽核記錄中：</span><span class="sxs-lookup"><span data-stu-id="ea74a-115">The Sharing schema provides two additional fields in the audit log related to sharing events:</span></span> 
  
- <span data-ttu-id="ea74a-116">**TargetUserOrGroupName** -儲存 UPN 或的目標使用者或群組，資源共用 (在上述範例中的 「 使用者 B 」) 的名稱。</span><span class="sxs-lookup"><span data-stu-id="ea74a-116">**TargetUserOrGroupName** - Stores the UPN or name of the target user or group that a resource was shared with (User B in the previous example).</span></span> 
    
- <span data-ttu-id="ea74a-117">**TargetUserOrGroupType** -識別是否目標使用者或群組成員、 訪客、 群組或合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="ea74a-117">**TargetUserOrGroupType** - Identifies whether the target user or group is a Member, Guest, Group, or Partner.</span></span> 
    
<span data-ttu-id="ea74a-118">這兩個欄位，除了其他屬性，從 Office 365 稽核記錄檔結構描述，例如使用者、 作業及日期可以告訴完整本文*哪些*使用者共用*哪些*資源與*對象\*\*時*的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="ea74a-118">These two fields, in addition to other properties from the Office 365 audit log schema such as User, Operation, and Date can tell the full story about  *which*  user shared  *what*  resource with  *whom*  and  *when*.</span></span> 
  
<span data-ttu-id="ea74a-119">沒有很重要的共用的本文的另一個資料庫架構屬性。</span><span class="sxs-lookup"><span data-stu-id="ea74a-119">There's another schema property that's important to the sharing story.</span></span> <span data-ttu-id="ea74a-120">**EventData**屬性會儲存共用事件相關的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="ea74a-120">The **EventData** property stores additional information about sharing events.</span></span> <span data-ttu-id="ea74a-121">例如，當使用者與其他使用者共用網站，這被透過將目標使用者新增至 SharePoint 群組。</span><span class="sxs-lookup"><span data-stu-id="ea74a-121">For example, when a user shares a site with another user, this is accomplished by adding the target user to a SharePoint group.</span></span> <span data-ttu-id="ea74a-122">**EventData**屬性擷取此為系統管理員提供內容的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="ea74a-122">The **EventData** property captures this additional information to provide context for administrators.</span></span> 

## <a name="the-sharepoint-sharing-model-and-sharing-events"></a><span data-ttu-id="ea74a-123">SharePoint 共用模型及共用事件</span><span class="sxs-lookup"><span data-stu-id="ea74a-123">The SharePoint Sharing model and sharing events</span></span>

<span data-ttu-id="ea74a-124">共用實際上定義由三個不同的事件： **SharingSet**、 **SharingInvitationCreated**和**SharingInvitaitonAccepted**。</span><span class="sxs-lookup"><span data-stu-id="ea74a-124">Sharing is actually defined by three separate events: **SharingSet**, **SharingInvitationCreated**, and **SharingInvitaitonAccepted**.</span></span> <span data-ttu-id="ea74a-125">以下方式共用事件的工作流程登入 Office 365 稽核記錄檔。</span><span class="sxs-lookup"><span data-stu-id="ea74a-125">Here's the work flow for how sharing events are logged in the Office 365 audit log.</span></span> 
  
![共用稽核的運作方式的流程圖](media/d83dd40f-919b-484f-bfd6-5dc8de31bff6.png)
  
<span data-ttu-id="ea74a-127">當使用者 （影響之使用者） 想要與另一位使用者 （目標使用者） 共用資源時，SharePoint （或商務用 OneDrive） 會先檢查目標使用者的電子郵件地址是否已在組織的目錄中的使用者帳戶相關聯。</span><span class="sxs-lookup"><span data-stu-id="ea74a-127">When a user (the acting user) wants to share a resource with another user (the target user), SharePoint (or OneDrive for Business) first checks if the email address of the target user is already associated with a user account in the organization's directory.</span></span> <span data-ttu-id="ea74a-128">如果目標使用者位於組織的目錄中，SharePoint 會執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="ea74a-128">If the target user is in the organization's directory, SharePoint does the following:</span></span>
  
-  <span data-ttu-id="ea74a-129">立即將指派的目標使用者權限來存取資源。</span><span class="sxs-lookup"><span data-stu-id="ea74a-129">Immediately assigns the target user permissions to access the resource.</span></span> 
    
- <span data-ttu-id="ea74a-130">將共用通知傳送至目標使用者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="ea74a-130">Sends a sharing notification to the email address of the target user.</span></span>
    
- <span data-ttu-id="ea74a-131">記錄**SharingSet**事件。</span><span class="sxs-lookup"><span data-stu-id="ea74a-131">Logs a **SharingSet** event.</span></span> 
    
 <span data-ttu-id="ea74a-132">如果目標使用者的使用者帳戶不在組織的目錄，SharePoint 會執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="ea74a-132">If a user account for the target user isn't in the organization's directory, SharePoint does the following:</span></span> 
  
- <span data-ttu-id="ea74a-133">建立共用邀請，並將其傳送到的目標使用者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="ea74a-133">Creates a sharing invitation and sends it to the email address of the target user.</span></span>
    
- <span data-ttu-id="ea74a-134">記錄**SharingInvitationCreated**事件。</span><span class="sxs-lookup"><span data-stu-id="ea74a-134">Logs a **SharingInvitationCreated** event.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="ea74a-135">**SharingInvitationCreated**事件相關聯最一律外部或是使用來賓身分共用時的目標使用者沒有存取共用的資源。</span><span class="sxs-lookup"><span data-stu-id="ea74a-135">The **SharingInvitationCreated** event is most always associated with external or guest sharing when the target user doesn't have access to the resource that was shared.</span></span> 
  
<span data-ttu-id="ea74a-136">當在目標使用者接受已傳送給他們 （藉由按一下邀請中的連結），SharePoint 共用邀請記錄**SharingInvitationAccepted**事件，並指派的目標使用者權限來存取資源。</span><span class="sxs-lookup"><span data-stu-id="ea74a-136">When the target user accepts the sharing invitation that's sent to them (by clicking the link in the invitation), SharePoint logs a **SharingInvitationAccepted** event and assigns the target user permissions to access the resource.</span></span> <span data-ttu-id="ea74a-137">在目標使用者的其他資訊也會記錄，例如邀請傳送至使用者和實際接受邀請之使用者的身分識別。</span><span class="sxs-lookup"><span data-stu-id="ea74a-137">Additional information about the target user is also logged, such as the identity of the user that the invitation was sent to and the user who actually accepted the invitation.</span></span> <span data-ttu-id="ea74a-138">在某些情況下，這些使用者 （或電子郵件地址） 可能會不同。</span><span class="sxs-lookup"><span data-stu-id="ea74a-138">In some case, these users (or email addresses) might be different.</span></span> 
  

  
## <a name="how-to-identify-resources-shared-with-external-users"></a><span data-ttu-id="ea74a-139">如何找出與外部使用者共用的資源</span><span class="sxs-lookup"><span data-stu-id="ea74a-139">How to identify resources shared with external users</span></span>

<span data-ttu-id="ea74a-140">系統管理員的一般需求建立指與組織外部使用者共用的所有資源的清單。</span><span class="sxs-lookup"><span data-stu-id="ea74a-140">A common requirement for administrators is creating a list of all resources that have been shared with users outside of the organization.</span></span> <span data-ttu-id="ea74a-141">藉由使用 Office 365 中的共用稽核，系統管理員現在可以產生這份清單。</span><span class="sxs-lookup"><span data-stu-id="ea74a-141">By using sharing auditing in Office 365, administrators can now generate this list.</span></span> <span data-ttu-id="ea74a-142">方法如下。</span><span class="sxs-lookup"><span data-stu-id="ea74a-142">Here's how.</span></span>
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a><span data-ttu-id="ea74a-143">步驟 1： 搜尋共用事件，並將結果匯出至 CSV 檔案</span><span class="sxs-lookup"><span data-stu-id="ea74a-143">Step 1: Search for sharing events and export the results to a CSV file</span></span>

<span data-ttu-id="ea74a-144">第一個步驟是搜尋共用事件的 Office 365 稽核記錄檔。</span><span class="sxs-lookup"><span data-stu-id="ea74a-144">The first step is to search the Office 365 audit log for sharing events.</span></span> <span data-ttu-id="ea74a-145">如需詳細資訊 （包括的必要權限） 的相關搜尋稽核記錄，請參閱 <<c0>的搜尋稽核記錄中的安全性 &amp; 合規性中心。</span><span class="sxs-lookup"><span data-stu-id="ea74a-145">For more details (including the required permissions) about searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
  
1. <span data-ttu-id="ea74a-146">移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="ea74a-146">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="ea74a-147">使用公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="ea74a-147">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="ea74a-148">在 [安全性 & 合規性中心的左窗格中，按一下 [**搜尋**  > **稽核記錄搜尋**。</span><span class="sxs-lookup"><span data-stu-id="ea74a-148">In the left pane of the Security & Compliance Center, click **Search**  > **Audit log search**.</span></span>
    
    <span data-ttu-id="ea74a-149">會顯示 [**稽核記錄搜尋**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="ea74a-149">The **Audit log search** page is displayed.</span></span> 
    
4. <span data-ttu-id="ea74a-150">[**活動**，按一下 [**共用活動**搜尋僅適用於共用事件。</span><span class="sxs-lookup"><span data-stu-id="ea74a-150">Under **Activities**, click **Sharing activities** to search only for sharing events.</span></span> 
    
    ![在活動下方，選取 [共用活動](media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5.  <span data-ttu-id="ea74a-152">選取要尋找共用所發生事件的期間內的日期和時間範圍。</span><span class="sxs-lookup"><span data-stu-id="ea74a-152">Select a date and time range to find the sharing events that occurred within that period.</span></span> 
    
6. <span data-ttu-id="ea74a-153">按一下 [**搜尋**] 以執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="ea74a-153">Click **Search** to run the search.</span></span> 
    
7. <span data-ttu-id="ea74a-154">搜尋完成時執行和結果會顯示，請按一下 [**匯出結果** \> **下載所有結果**。</span><span class="sxs-lookup"><span data-stu-id="ea74a-154">When the search is finished running and the results are displayed , click **Export results** \> **Download all results**.</span></span>
    
    <span data-ttu-id="ea74a-155">選取 [匯出] 選項後，會提示您開啟或儲存該 CSV 檔案的視窗底部會顯示訊息。</span><span class="sxs-lookup"><span data-stu-id="ea74a-155">After you select the export option, a message is displayed at the bottom of the window that prompts you to open or save the CSV file.</span></span>
    
8. <span data-ttu-id="ea74a-156">按一下 [**儲存** \> **另存為**並在本機電腦上將 CSV 檔案儲存至資料夾。</span><span class="sxs-lookup"><span data-stu-id="ea74a-156">Click **Save** \> **Save as** and save the CSV file to a folder on your local computer.</span></span> 
    

  
### <a name="step-2-filter-the-csv-file-for-resources-shared-with-external-users"></a><span data-ttu-id="ea74a-157">步驟 2： 篩選與外部使用者共用的資源的 CSV 檔案</span><span class="sxs-lookup"><span data-stu-id="ea74a-157">Step 2: Filter the CSV file for resources shared with external users</span></span>

<span data-ttu-id="ea74a-158">下一步是**SharingSet**和**SharingInvitationCreated**事件，將 CSV 篩選，並顯示這些事件**TargetUserOrGroupType**屬性所在**來賓**。</span><span class="sxs-lookup"><span data-stu-id="ea74a-158">The next step is to filter the CSV for the **SharingSet** and **SharingInvitationCreated** events, and to display those events where the **TargetUserOrGroupType** property is **Guest**.</span></span> <span data-ttu-id="ea74a-159">若要這麼做，您將在 Excel 中使用 Power Query 功能。</span><span class="sxs-lookup"><span data-stu-id="ea74a-159">You'll use the Power Query feature in Excel to do this.</span></span> <span data-ttu-id="ea74a-160">在 Excel 2016 中執行下列程序。</span><span class="sxs-lookup"><span data-stu-id="ea74a-160">The following procedure is performed in Excel 2016.</span></span> 
  
1. <span data-ttu-id="ea74a-161">在 Excel 2016 中，開啟空白活頁簿。</span><span class="sxs-lookup"><span data-stu-id="ea74a-161">In Excel 2016, open a blank workbook.</span></span>
    
2. <span data-ttu-id="ea74a-162">按一下 [**資料**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="ea74a-162">Click the **Data** tab.</span></span> 
    
3. <span data-ttu-id="ea74a-163">按一下 [**新增查詢** \> **檔案從** \> **從 CSV**。</span><span class="sxs-lookup"><span data-stu-id="ea74a-163">Click **New Query** \> **From file** \> **From CSV**.</span></span>
    
    ![在 [資料] 索引標籤中，選取 [新增查詢、 從檔案中，選取，然後選取從 CSV](media/5170ab34-b449-40ea-bd3f-f1432c1c5973.png)
  
4. <span data-ttu-id="ea74a-165">在步驟 1 中開啟您已下載的 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="ea74a-165">Open the CSV file that you downloaded in Step 1.</span></span>
    
    <span data-ttu-id="ea74a-166">在 [查詢編輯器] 中開啟 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="ea74a-166">The CSV file is opened in the Query Editor.</span></span> <span data-ttu-id="ea74a-167">請注意，有四個欄：**時間**、**使用者**、**動作**和**詳細資料**。</span><span class="sxs-lookup"><span data-stu-id="ea74a-167">Note that there are four columns: **Time**, **User**, **Action**, and **Detail**.</span></span> <span data-ttu-id="ea74a-168">[**詳細資料**] 欄是多重屬性的欄位。</span><span class="sxs-lookup"><span data-stu-id="ea74a-168">The **Detail** column is a multi-property field.</span></span> <span data-ttu-id="ea74a-169">下一步是建立新的資料行的每個 [**詳細資料**] 欄中的屬性。</span><span class="sxs-lookup"><span data-stu-id="ea74a-169">The next step is to create a new column for each of the properties in the **Detail** column.</span></span> 
    
5. <span data-ttu-id="ea74a-170">選取 [**詳細資料**] 欄中，，然後按一下 [**首頁**] 索引標籤上的 [**分割資料行** \> **的分隔符號**。</span><span class="sxs-lookup"><span data-stu-id="ea74a-170">Select the **Detail** column, and then on the **Home** tab, click **Split Column** \> **By Delimiter**.</span></span>
    
    ![在 [首頁] 索引標籤上按一下分割資料行，然後按一下 [由分隔符號](media/aeb503e8-565b-42ea-91e2-9f127a74c00c.png)
  
6. <span data-ttu-id="ea74a-172">在 [**分割資料行來分隔字元**] 視窗中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="ea74a-172">In the **Split Column by Delimiter** window, do the following:</span></span> 
    
      - <span data-ttu-id="ea74a-173">在 [**選取或輸入分隔符號**，選取 [**逗點**。</span><span class="sxs-lookup"><span data-stu-id="ea74a-173">Under **Select or enter delimiter**, select **Comma**.</span></span>
    
      - <span data-ttu-id="ea74a-174">在 [**分割**] 下選取 [**在分隔符號的每個項目**。</span><span class="sxs-lookup"><span data-stu-id="ea74a-174">Under **Split**, select **At each occurrence of the delimiter**.</span></span>
    
7. <span data-ttu-id="ea74a-175">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ea74a-175">Click **OK**.</span></span>
    
    <span data-ttu-id="ea74a-176">[**詳細資料**] 欄分割成多個資料行。</span><span class="sxs-lookup"><span data-stu-id="ea74a-176">The **Detail** column is split into multiple columns.</span></span> <span data-ttu-id="ea74a-177">每個新的欄名為**Detail.1**、 **Detail.2**、 **Detail.3**，等等。</span><span class="sxs-lookup"><span data-stu-id="ea74a-177">Each new column is named **Detail.1**, **Detail.2**, **Detail.3**, and so on.</span></span> <span data-ttu-id="ea74a-178">您會注意到**Detail.n**欄中的每個儲存格中的值以在屬性名稱例如，**作業： SharingSet**、**作業： SharingInvitationAccepted**和**作業： SharingInvitationCreated**。</span><span class="sxs-lookup"><span data-stu-id="ea74a-178">You'll notice the values in each cell in the **Detail.n** columns are prefixed with the name of the property; for example, **Operation:SharingSet**, **Operation:SharingInvitationAccepted**, and **Operation:SharingInvitationCreated**.</span></span>
    
    ![[詳細資料] 欄分割成多個資料行，其中每個屬性](media/4b104ead-0313-4bd4-b2a9-f143ccb378ac.png)
  
8. <span data-ttu-id="ea74a-180">在 [**檔案**] 索引標籤中，按一下 [**關閉&amp;負載**以關閉 [查詢編輯器，並開啟 Excel 活頁簿中的檔案。</span><span class="sxs-lookup"><span data-stu-id="ea74a-180">On the **File** tab, click **Close &amp; Load** to close the Query Editor and open the file in an Excel workbook.</span></span> 
    
    <span data-ttu-id="ea74a-181">下一步是以篩選要只會顯示**SharingSet**和**SharingInvitationCreated**事件的檔案。</span><span class="sxs-lookup"><span data-stu-id="ea74a-181">The next step is to filter the file to only display the **SharingSet** and **SharingInvitationCreated** events.</span></span> 
    
9. <span data-ttu-id="ea74a-182">移至 [**首頁**] 索引標籤，然後選取 [**動作**] 資料行。</span><span class="sxs-lookup"><span data-stu-id="ea74a-182">Go to the **Home** tab, and then select the **Action** column.</span></span> 
    
10. <span data-ttu-id="ea74a-183">在**排序&amp;篩選**下拉式清單中，清除所有選項，然後選取 [ **SharingSet**和**SharingInvitationCreated**，並按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="ea74a-183">In the **Sort &amp; Filter** drop-down list, clear all selections, then select **SharingSet** and **SharingInvitationCreated**, and click **OK**.</span></span>
    
    <span data-ttu-id="ea74a-184">Excel 會顯示**SharingSet**和**SharingInvitationCreated**事件的資料列。</span><span class="sxs-lookup"><span data-stu-id="ea74a-184">Excel displays the rows for the **SharingSet** and **SharingInvitationCreated** events.</span></span> 
    
11. <span data-ttu-id="ea74a-185">移至名為**Detail.17** （或哪一個資料行包含**TargetUserOrGroupType**屬性） 的資料行，然後選取它。</span><span class="sxs-lookup"><span data-stu-id="ea74a-185">Go to the column named **Detail.17** (or whichever column contains the **TargetUserOrGroupType** property) and select it.</span></span> 
    
12. <span data-ttu-id="ea74a-186">在**排序&amp;篩選**下拉式清單中，清除所有選項，然後選取 [ **TargetUserOrGroupType:Guest**，並按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="ea74a-186">In the **Sort &amp; Filter** drop-down list, clear all selections, then select **TargetUserOrGroupType:Guest**, and click **OK**.</span></span>
    
    <span data-ttu-id="ea74a-187">現在 Excel 顯示**SharingInvitationCreated**和**SharingSet**事件，而在目標使用者是您組織外的列，因為值**TargetUserOrGroupType:Guest**識別外部使用者。</span><span class="sxs-lookup"><span data-stu-id="ea74a-187">Now Excel displays the rows for **SharingInvitationCreated** and **SharingSet** events AND where the target user is outside of your organization, because external users are identified by the value **TargetUserOrGroupType:Guest**.</span></span> 
    
<span data-ttu-id="ea74a-188">下表會顯示指定的日期範圍內的來賓使用者與共用資源組織中所有使用者。</span><span class="sxs-lookup"><span data-stu-id="ea74a-188">The following table shows all users in the organization who shared resources with a guest user within a specified date range.</span></span>
  
![在 Office 365 中的共用活動的稽核記錄](media/0e0ecbe3-c794-4ca6-a2ca-63478fb3bb34.png)
  
<span data-ttu-id="ea74a-190">雖然它不會納入前一個表格， **Detail.10**資料行 （或哪一個資料行包含**ObjectId**屬性） 會識別已與目標使用者; 共用的資源例如`ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`。</span><span class="sxs-lookup"><span data-stu-id="ea74a-190">Although it's not included in the previous table, the **Detail.10** column (or whichever column contains the **ObjectId** property) identifies the resource that was shared with the target user; for example  `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`.</span></span>
  
> [!TIP]
> <span data-ttu-id="ea74a-191">如果您想要識別當來賓使用者已實際上指派權限可存取資源 (而不是只的資源，其中與他們共用)，重複步驟 10、 11 和 12，及**SharingInvitationAccepted**和**SharingSet 篩選**步驟 10 中的事件。</span><span class="sxs-lookup"><span data-stu-id="ea74a-191">If you want to identify when a guest user was actually assigned permissions to access a resource (as opposed to just the resources that where shared with them), repeat Steps 10, 11, and 12, and filter on the **SharingInvitationAccepted** and **SharingSet** events in Step 10.</span></span> 
