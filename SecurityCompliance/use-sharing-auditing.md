---
title: 使用共用的 Office 365 稽核記錄中的稽核
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 2/13/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- BCS160
- MET150
ms.assetid: 50bbf89f-7870-4c2a-ae14-42635e0cfc01
description: '共用是 SharePoint Online 和 OneDrive for Business 的主要活動。管理員可以立即使用共用的 Office 365 稽核記錄中的稽核來判斷如何共用所要使用其組織中。 '
ms.openlocfilehash: 511f8b0e61d450659d78177d5b87fac9ee636cd4
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526863"
---
# <a name="use-sharing-auditing-in-the-office-365-audit-log"></a><span data-ttu-id="c977c-104">使用共用的 Office 365 稽核記錄中的稽核</span><span class="sxs-lookup"><span data-stu-id="c977c-104">Use sharing auditing in the Office 365 audit log</span></span>

<span data-ttu-id="c977c-p102">共用是主要活動 SharePoint Online 和 OneDrive for Business，並加以廣泛使用在 Office 365 組織中。管理員可以立即使用共用的 Office 365 稽核記錄中的稽核來判斷如何共用所要使用其組織中。</span><span class="sxs-lookup"><span data-stu-id="c977c-p102">Sharing is a key activity in SharePoint Online and OneDrive for Business, and it's widely used in Office 365 organizations. Administrators can now use sharing auditing in the Office 365 audit log to determine how sharing is being used in their organization.</span></span> 
  
## <a name="the-sharepoint-sharing-schema"></a><span data-ttu-id="c977c-107">SharePoint 共用結構描述</span><span class="sxs-lookup"><span data-stu-id="c977c-107">The SharePoint Sharing schema</span></span>

<span data-ttu-id="c977c-p103">主要的其中一個方法位於不同檔案和資料夾相關的事件 （不共用原則和共用連結事件） 的共用事件： 一位使用者正在進行一些影響另一位使用者的動作。例如，使用者 A 可以讓使用者 B 存取檔案。在這個範例中，使用者 A 是*代表使用者*和使用者 B 是*目標使用者*。在 SharePoint 檔結構描述中影響之使用者的巨集指令只會影響檔案本身。當使用者 A 開啟檔案， **FileAccessed**事件中所需的唯一資訊會影響之使用者。為了處理這個差異，有不同的結構描述，稱為*SharePoint 共用的結構描述*，來擷取共用事件的詳細資訊。這可確保系統管理員才有更深入之共用資源與使用者之資源的形式共用與。</span><span class="sxs-lookup"><span data-stu-id="c977c-p103">Sharing events (excluding sharing policy and sharing link events) are different from file- and folder-related events in one primary way: one user is taking an action that has some effect on another user. For example, User A gives User B access to a file. In this example, User A is the  *acting user*  and User B is the  *target user*. In the SharePoint File schema, the acting user's action only affects the file itself. When User A opens a file, the only information needed in the **FileAccessed** event is the acting user. To address this difference, there is a separate schema, called the  *SharePoint Sharing schema*, that captures more information about sharing events. This ensures that administrators have more insight into who shared a resource and the user the resource was shared with.</span></span> 
  
<span data-ttu-id="c977c-115">Sharing 架構提供兩個額外的欄位與共用事件相關的稽核記錄檔中：</span><span class="sxs-lookup"><span data-stu-id="c977c-115">The Sharing schema provides two additional fields in the audit log related to sharing events:</span></span> 
  
- <span data-ttu-id="c977c-116">**TargetUserOrGroupName** -儲存 UPN 或目標使用者或群組資源已共用與 (上述範例中的 「 使用者 B 」) 的名稱。</span><span class="sxs-lookup"><span data-stu-id="c977c-116">**TargetUserOrGroupName** - Stores the UPN or name of the target user or group that a resource was shared with (User B in the previous example).</span></span> 
    
- <span data-ttu-id="c977c-117">**TargetUserOrGroupType** -識別是否目標使用者或群組成員、 訪客、 群組或協力廠商。</span><span class="sxs-lookup"><span data-stu-id="c977c-117">**TargetUserOrGroupType** - Identifies whether the target user or group is a Member, Guest, Group, or Partner.</span></span> 
    
<span data-ttu-id="c977c-118">例如使用者驗證、 作業及日期可以分清*哪個*使用者共用*哪些*資源與*對象**時*的相關完整本文這兩個欄位，以及其他屬性從 Office 365 的稽核記錄檔結構描述。</span><span class="sxs-lookup"><span data-stu-id="c977c-118">These two fields, in addition to other properties from the Office 365 audit log schema such as User, Operation, and Date can tell the full story about  *which*  user shared  *what*  resource with  *whom*  and  *when*.</span></span> 
  
<span data-ttu-id="c977c-p104">有另一個很重要的共用本文的結構描述屬性。**EventData**屬性儲存共用事件的額外資訊。例如，當使用者與其他使用者共用網站，這被藉由將目標使用者新增至 SharePoint 群組。**EventData**屬性擷取此系統管理員提供內容的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="c977c-p104">There's another schema property that's important to the sharing story. The **EventData** property stores additional information about sharing events. For example, when a user shares a site with another user, this is accomplished by adding the target user to a SharePoint group. The **EventData** property captures this additional information to provide context for administrators.</span></span> 

## <a name="the-sharepoint-sharing-model-and-sharing-events"></a><span data-ttu-id="c977c-123">SharePoint 共用模型和共用事件</span><span class="sxs-lookup"><span data-stu-id="c977c-123">The SharePoint Sharing model and sharing events</span></span>

<span data-ttu-id="c977c-p105">共用實際上定義三個不同的事件： **SharingSet**、 **SharingInvitationCreated**，以及**SharingInvitaitonAccepted**。以下方式共用事件的工作流程會記錄在 Office 365 稽核記錄檔。</span><span class="sxs-lookup"><span data-stu-id="c977c-p105">Sharing is actually defined by three separate events: **SharingSet**, **SharingInvitationCreated**, and **SharingInvitaitonAccepted**. Here's the work flow for how sharing events are logged in the Office 365 audit log.</span></span> 
  
![共用稽核的運作方式的流程圖](media/d83dd40f-919b-484f-bfd6-5dc8de31bff6.png)
  
<span data-ttu-id="c977c-p106">當使用者 （影響之使用者） 想要與另一位使用者 （目標使用者） 共用資源時，SharePoint （或 OneDrive for Business） 先檢查是否已與組織目錄中的使用者帳戶相關聯之目標使用者的電子郵件地址。如果目標使用者位於組織目錄中，SharePoint 會執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="c977c-p106">When a user (the acting user) wants to share a resource with another user (the target user), SharePoint (or OneDrive for Business) first checks if the email address of the target user is already associated with a user account in the organization's directory. If the target user is in the organization's directory, SharePoint does the following:</span></span>
  
-  <span data-ttu-id="c977c-129">立即指派存取資源的目標使用者權限。</span><span class="sxs-lookup"><span data-stu-id="c977c-129">Immediately assigns the target user permissions to access the resource.</span></span> 
    
- <span data-ttu-id="c977c-130">目標使用者的電子郵件地址傳送共用通知。</span><span class="sxs-lookup"><span data-stu-id="c977c-130">Sends a sharing notification to the email address of the target user.</span></span>
    
- <span data-ttu-id="c977c-131">**SharingSet**事件記錄。</span><span class="sxs-lookup"><span data-stu-id="c977c-131">Logs a **SharingSet** event.</span></span> 
    
 <span data-ttu-id="c977c-132">如果目標使用者的使用者帳戶不是組織的目錄中，SharePoint 會執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="c977c-132">If a user account for the target user isn't in the organization's directory, SharePoint does the following:</span></span> 
  
- <span data-ttu-id="c977c-133">會建立共用邀請，並將它傳送至目標使用者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="c977c-133">Creates a sharing invitation and sends it to the email address of the target user.</span></span>
    
- <span data-ttu-id="c977c-134">**SharingInvitationCreated**事件記錄。</span><span class="sxs-lookup"><span data-stu-id="c977c-134">Logs a **SharingInvitationCreated** event.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="c977c-135">**SharingInvitationCreated**事件相關聯最一律外部或來賓共用時的目標使用者沒有存取權的形式共用的資源。</span><span class="sxs-lookup"><span data-stu-id="c977c-135">The **SharingInvitationCreated** event is most always associated with external or guest sharing when the target user doesn't have access to the resource that was shared.</span></span> 
  
<span data-ttu-id="c977c-p107">當目標使用者接受已經傳送給他們 （依序按一下 [邀請中的連結)，SharePoint 共用邀請**SharingInvitationAccepted**事件記錄並指派以存取資源的目標使用者權限。也登目標使用者的其他資訊，例如邀請傳送給使用者和實際接受邀請之使用者的身分識別。在某些情況下，這些使用者 （或電子郵件地址） 可能會不同。</span><span class="sxs-lookup"><span data-stu-id="c977c-p107">When the target user accepts the sharing invitation that's sent to them (by clicking the link in the invitation), SharePoint logs a **SharingInvitationAccepted** event and assigns the target user permissions to access the resource. Additional information about the target user is also logged, such as the identity of the user that the invitation was sent to and the user who actually accepted the invitation. In some case, these users (or email addresses) might be different.</span></span> 
  

  
## <a name="how-to-identify-resources-shared-with-external-users"></a><span data-ttu-id="c977c-139">如何識別與外部使用者共用的資源</span><span class="sxs-lookup"><span data-stu-id="c977c-139">How to identify resources shared with external users</span></span>

<span data-ttu-id="c977c-p108">系統管理員的一般需求會建立已與組織外部的使用者共用的所有資源的清單。藉由使用共用 Office 365 中的稽核，系統管理員可以立即產生此清單。以下是如何。</span><span class="sxs-lookup"><span data-stu-id="c977c-p108">A common requirement for administrators is creating a list of all resources that have been shared with users outside of the organization. By using sharing auditing in Office 365, administrators can now generate this list. Here's how.</span></span>
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a><span data-ttu-id="c977c-143">步驟 1： 搜尋共用事件並將結果匯出至 CSV 檔案</span><span class="sxs-lookup"><span data-stu-id="c977c-143">Step 1: Search for sharing events and export the results to a CSV file</span></span>

<span data-ttu-id="c977c-p109">第一個步驟是搜尋共用事件的 Office 365 稽核記錄。如需詳細資訊 （包括必要的權限） 的相關搜尋稽核記錄，請參閱[Office 365 安全性搜尋稽核記錄&amp;規範中心](search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="c977c-p109">The first step is to search the Office 365 audit log for sharing events. For more details (including the required permissions) about searching the audit log, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
  
1. <span data-ttu-id="c977c-146">移至 [ [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="c977c-146">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="c977c-147">登入 Office 365 中，使用您工作或學校的帳戶。</span><span class="sxs-lookup"><span data-stu-id="c977c-147">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="c977c-148">在 [安全性] 的左窗格中&amp;規範中心按一下**搜尋&amp;調查**，然後按一下 [**稽核記錄搜尋**。</span><span class="sxs-lookup"><span data-stu-id="c977c-148">In the left pane of the Security &amp; Compliance Center, click **Search &amp; investigation**, and then click **Audit log search**.</span></span>
    
    <span data-ttu-id="c977c-149">會顯示 [**稽核記錄搜尋**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="c977c-149">The **Audit log search** page is displayed.</span></span> 
    
4. <span data-ttu-id="c977c-150">[**活動**，按一下 [**共用活動**搜尋僅共用事件。</span><span class="sxs-lookup"><span data-stu-id="c977c-150">Under **Activities**, click **Sharing activities** to search only for sharing events.</span></span> 
    
    ![在 [活動] 下選取 [共用活動](media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5.  <span data-ttu-id="c977c-152">選取 [尋找共用所發生事件的期間內的日期和時間範圍。</span><span class="sxs-lookup"><span data-stu-id="c977c-152">Select a date and time range to find the sharing events that occurred within that period.</span></span> 
    
6. <span data-ttu-id="c977c-153">按一下 [**搜尋**] 執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="c977c-153">Click **Search** to run the search.</span></span> 
    
7. <span data-ttu-id="c977c-154">完成搜尋會顯示執行和結果、 按一下 [**匯出結果** \> **下載所有結果**。</span><span class="sxs-lookup"><span data-stu-id="c977c-154">When the search is finished running and the results are displayed , click **Export results** \> **Download all results**.</span></span>
    
    <span data-ttu-id="c977c-155">您選取 [匯出] 選項後，會提示您開啟或儲存 CSV 檔案的視窗底部顯示訊息。</span><span class="sxs-lookup"><span data-stu-id="c977c-155">After you select the export option, a message is displayed at the bottom of the window that prompts you to open or save the CSV file.</span></span>
    
8. <span data-ttu-id="c977c-156">按一下 [**儲存** \> **另存為**CSV 檔案將本機電腦上的資料夾。</span><span class="sxs-lookup"><span data-stu-id="c977c-156">Click **Save** \> **Save as** and save the CSV file to a folder on your local computer.</span></span> 
    

  
### <a name="step-2-filter-the-csv-file-for-resources-shared-with-external-users"></a><span data-ttu-id="c977c-157">步驟 2： 篩選與外部使用者共用的資源的 CSV 檔案</span><span class="sxs-lookup"><span data-stu-id="c977c-157">Step 2: Filter the CSV file for resources shared with external users</span></span>

<span data-ttu-id="c977c-p110">下一步是篩選 CSV **SharingSet**和**SharingInvitationCreated**事件，並顯示這些事件其中**TargetUserOrGroupType**屬性是**來賓**。您將在 Excel 中使用 Power 查詢功能為達成此目的。在 Excel 2016 中執行下列程序。</span><span class="sxs-lookup"><span data-stu-id="c977c-p110">The next step is to filter the CSV for the **SharingSet** and **SharingInvitationCreated** events, and to display those events where the **TargetUserOrGroupType** property is **Guest**. You'll use the Power Query feature in Excel to do this. The following procedure is performed in Excel 2016.</span></span> 
  
1. <span data-ttu-id="c977c-161">在 Excel 2016 開啟空白的活頁簿。</span><span class="sxs-lookup"><span data-stu-id="c977c-161">In Excel 2016, open a blank workbook.</span></span>
    
2. <span data-ttu-id="c977c-162">按一下 [資料]**** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="c977c-162">Click the **Data** tab.</span></span> 
    
3. <span data-ttu-id="c977c-163">按一下 [**新增查詢** \> **從檔案** \> **從 CSV**。</span><span class="sxs-lookup"><span data-stu-id="c977c-163">Click **New Query** \> **From file** \> **From CSV**.</span></span>
    
    ![在 [資料] 索引標籤上選取 [新增查詢、 選取從檔案，然後選取從 CSV](media/5170ab34-b449-40ea-bd3f-f1432c1c5973.png)
  
4. <span data-ttu-id="c977c-165">在步驟 1 中開啟您下載的 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="c977c-165">Open the CSV file that you downloaded in Step 1.</span></span>
    
    <span data-ttu-id="c977c-p111">在 [查詢編輯器] 中開啟 CSV 檔案。請注意有四欄：**時間**、**使用者**、**動作**和**詳細資料**。[**詳細資料**] 欄是多重屬性欄位。下一步是建立新欄的每個 [**詳細資料**] 欄中的屬性。</span><span class="sxs-lookup"><span data-stu-id="c977c-p111">The CSV file is opened in the Query Editor. Note that there are four columns: **Time**, **User**, **Action**, and **Detail**. The **Detail** column is a multi-property field. The next step is to create a new column for each of the properties in the **Detail** column.</span></span> 
    
5. <span data-ttu-id="c977c-170">選取 [**詳細**資料行] 和 [**首頁**] 索引標籤上 [**分割資料行** \> **的分隔字元**。</span><span class="sxs-lookup"><span data-stu-id="c977c-170">Select the **Detail** column, and then on the **Home** tab, click **Split Column** \> **By Delimiter**.</span></span>
    
    ![在 [常用] 索引標籤上 [分割] 欄中，和 [依分隔符號](media/aeb503e8-565b-42ea-91e2-9f127a74c00c.png)
  
6. <span data-ttu-id="c977c-172">在 [**分割資料行來分隔字元**] 視窗中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="c977c-172">In the **Split Column by Delimiter** window, do the following:</span></span> 
    
      - <span data-ttu-id="c977c-173">在 [**選取或輸入分隔字元**，請選取**逗點**。</span><span class="sxs-lookup"><span data-stu-id="c977c-173">Under **Select or enter delimiter**, select **Comma**.</span></span>
    
      - <span data-ttu-id="c977c-174">[**分割**] 下選取 [**在分隔符號的每個項目**。</span><span class="sxs-lookup"><span data-stu-id="c977c-174">Under **Split**, select **At each occurrence of the delimiter**.</span></span>
    
7. <span data-ttu-id="c977c-175">按一下 [確定]****。</span><span class="sxs-lookup"><span data-stu-id="c977c-175">Click **OK**.</span></span>
    
    <span data-ttu-id="c977c-p112">[**詳細資料**] 欄會分割成多個資料欄。每個新的資料行名稱為**Detail.1**、 **Detail.2**、 **Detail.3**、 等等。您會發現**Detail.n**資料行中的每一個儲存格中的值以屬性的名稱例如，**作業： SharingSet**、**作業： SharingInvitationAccepted**、 和**作業： SharingInvitationCreated**。</span><span class="sxs-lookup"><span data-stu-id="c977c-p112">The **Detail** column is split into multiple columns. Each new column is named **Detail.1**, **Detail.2**, **Detail.3**, and so on. You'll notice the values in each cell in the **Detail.n** columns are prefixed with the name of the property; for example, **Operation:SharingSet**, **Operation:SharingInvitationAccepted**, and **Operation:SharingInvitationCreated**.</span></span>
    
    ![[詳細資料] 欄中分割成多個資料欄，其中每個屬性](media/4b104ead-0313-4bd4-b2a9-f143ccb378ac.png)
  
8. <span data-ttu-id="c977c-180">在 [**檔案**] 索引標籤上按一下 [**關閉&amp;負載**以關閉 [查詢編輯器並開啟 Excel 活頁簿中的檔案。</span><span class="sxs-lookup"><span data-stu-id="c977c-180">On the **File** tab, click **Close &amp; Load** to close the Query Editor and open the file in an Excel workbook.</span></span> 
    
    <span data-ttu-id="c977c-181">下一步是以篩選要只顯示**SharingSet**和**SharingInvitationCreated**事件的檔案。</span><span class="sxs-lookup"><span data-stu-id="c977c-181">The next step is to filter the file to only display the **SharingSet** and **SharingInvitationCreated** events.</span></span> 
    
9. <span data-ttu-id="c977c-182">移至 [**首頁**] 索引標籤，然後選取 [**動作**] 欄。</span><span class="sxs-lookup"><span data-stu-id="c977c-182">Go to the **Home** tab, and then select the **Action** column.</span></span> 
    
10. <span data-ttu-id="c977c-183">在**排序&amp;篩選**下拉式清單中，清除所有選項，然後選取 [ **SharingSet**和**SharingInvitationCreated**，並按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="c977c-183">In the **Sort &amp; Filter** drop-down list, clear all selections, then select **SharingSet** and **SharingInvitationCreated**, and click **OK**.</span></span>
    
    <span data-ttu-id="c977c-184">Excel 會顯示**SharingSet**和**SharingInvitationCreated**事件的資料列。</span><span class="sxs-lookup"><span data-stu-id="c977c-184">Excel displays the rows for the **SharingSet** and **SharingInvitationCreated** events.</span></span> 
    
11. <span data-ttu-id="c977c-185">移至名為**Detail.17** （或無論資料行包含**TargetUserOrGroupType**屬性） 的資料行並加以選取。</span><span class="sxs-lookup"><span data-stu-id="c977c-185">Go to the column named **Detail.17** (or whichever column contains the **TargetUserOrGroupType** property) and select it.</span></span> 
    
12. <span data-ttu-id="c977c-186">在**排序&amp;篩選**下拉式清單中，清除所有選項，然後選取 [ **TargetUserOrGroupType:Guest**，並按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="c977c-186">In the **Sort &amp; Filter** drop-down list, clear all selections, then select **TargetUserOrGroupType:Guest**, and click **OK**.</span></span>
    
    <span data-ttu-id="c977c-187">現在 Excel 因為外部使用者識別值**TargetUserOrGroupType:Guest**會顯示**SharingInvitationCreated**和**SharingSet**事件與您的組織外部的目標使用者所在的列。</span><span class="sxs-lookup"><span data-stu-id="c977c-187">Now Excel displays the rows for **SharingInvitationCreated** and **SharingSet** events AND where the target user is outside of your organization, because external users are identified by the value **TargetUserOrGroupType:Guest**.</span></span> 
    
<span data-ttu-id="c977c-188">下表顯示指定的日期範圍內的來賓使用者與共用資源組織中所有使用者。</span><span class="sxs-lookup"><span data-stu-id="c977c-188">The following table shows all users in the organization who shared resources with a guest user within a specified date range.</span></span>
  
![Office 365 中共用的事件稽核記錄](media/0e0ecbe3-c794-4ca6-a2ca-63478fb3bb34.png)
  
<span data-ttu-id="c977c-190">雖然它不包含在上一個表格中， **Detail.10**資料行 （或無論資料行包含**ObjectId**屬性） 會識別與目標使用者 ； 的形式共用的資源例如`ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`。</span><span class="sxs-lookup"><span data-stu-id="c977c-190">Although it's not included in the previous table, the **Detail.10** column (or whichever column contains the **ObjectId** property) identifies the resource that was shared with the target user; for example  `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`.</span></span>
  
> [!TIP]
> <span data-ttu-id="c977c-191">如果您想要找出時來賓使用者已實際上指派資源的存取權 (而非只是資源的位置與這些共用)、 重複步驟 10、 11 和 12、 及篩選**SharingInvitationAccepted**及**SharingSet**事件的步驟 10。</span><span class="sxs-lookup"><span data-stu-id="c977c-191">If you want to identify when a guest user was actually assigned permissions to access a resource (as opposed to just the resources that where shared with them), repeat Steps 10, 11, and 12, and filter on the **SharingInvitationAccepted** and **SharingSet** events in Step 10.</span></span> 
