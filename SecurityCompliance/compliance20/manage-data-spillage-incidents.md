---
title: 管理 Microsoft 365 中的建立資料 spillage 事件
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
description: 本文說明如何使用 Office 365 安全性 & 規範中心新資料調查 （預覽） 工具來管理資料 spillage 事件。
ms.openlocfilehash: 93cbbed8763f0af31ab8d4e32348f01bfda17a2a
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218123"
---
# <a name="manage-a-data-spillage-incident-in-microsoft-365"></a><span data-ttu-id="c2f07-103">管理 Microsoft 365 中的建立資料 spillage 事件</span><span class="sxs-lookup"><span data-stu-id="c2f07-103">Manage a data spillage incident in Microsoft 365</span></span> 

<span data-ttu-id="c2f07-p101">機密文件發行至不受信任的環境時資料 spillage。當偵測到資料 spillage 事件時，務必快速評估的大小及位置的 spillage、 檢查周圍、 使用者活動及則從系統永久清除 spilled 的資料。</span><span class="sxs-lookup"><span data-stu-id="c2f07-p101">Data spillage is when a confidential document is released into an untrusted environment. When a data spillage incident is detected, it's important to quickly assess the size and locations of the spillage, examine user activities around it, and then permanently purge the spilled data from the system.</span></span>

## <a name="scope-of-this-article"></a><span data-ttu-id="c2f07-106">本文的範圍</span><span class="sxs-lookup"><span data-stu-id="c2f07-106">Scope of this article</span></span>

<span data-ttu-id="c2f07-107">本文提供如何將永久移除項目從 Office 365 信箱所以不再是可存取或依使用者或系統管理員可復原清單中的指示。</span><span class="sxs-lookup"><span data-stu-id="c2f07-107">This article provides a list of instructions on how to permanently remove items from Office 365 mailboxes so they are no longer accessible or recoverable by users or admins.</span></span> 

> [!NOTE]
> <span data-ttu-id="c2f07-108">當您刪除項目位於 SharePoint 或 OneDrive 商務網站時，他們會保留從您從其原始位置刪除時間 93 天。</span><span class="sxs-lookup"><span data-stu-id="c2f07-108">When you delete items located in a SharePoint or OneDrive for Business site, they are retained for 93 days from the time you delete them from their original location.</span></span>

## <a name="scenario"></a><span data-ttu-id="c2f07-109">案例</span><span class="sxs-lookup"><span data-stu-id="c2f07-109">Scenario</span></span>

<span data-ttu-id="c2f07-p102">您正在得知其中員工不知情的情況下高度機密文件與多人共用透過電子郵件資料 spillage 事件。您想要快速評估者接收到此文件、 內部和外部組織。您已調查事件之後，您想與其他現場，檢閱，然後從 Office 365 永久移除 spilled 的資料共用您發現項目。將正在調查完成後，您要移除所有證據。</span><span class="sxs-lookup"><span data-stu-id="c2f07-p102">You're informed of a data spillage incident where an employee unknowingly shared a highly-confidential document with multiple people through email. You want to quickly assess who received this document, both inside and outside of your organization. After you've investigate the incident, you plan to share your findings with other investigators to review, and then permanently remove the spilled data from Office 365. After the investigation is complete, you want to remove all evidence.</span></span> 

## <a name="workflow"></a><span data-ttu-id="c2f07-114">工作流程</span><span class="sxs-lookup"><span data-stu-id="c2f07-114">Workflow</span></span>

<span data-ttu-id="c2f07-115">以下是使用資料調查 （預覽） 來管理資料 spillage 事件的工作流程：</span><span class="sxs-lookup"><span data-stu-id="c2f07-115">Here's the workflow for using Data Investigations (Preview) to manage a data spillage incident:</span></span>

1.  <span data-ttu-id="c2f07-116">建立資料調查。</span><span class="sxs-lookup"><span data-stu-id="c2f07-116">Create a data investigation.</span></span>

2.  <span data-ttu-id="c2f07-117">搜尋 spilled 資料。</span><span class="sxs-lookup"><span data-stu-id="c2f07-117">Search for the spilled data.</span></span>

3.  <span data-ttu-id="c2f07-118">檢閱並調查事件。</span><span class="sxs-lookup"><span data-stu-id="c2f07-118">Review and investigate the incident.</span></span>

4.  <span data-ttu-id="c2f07-119">永久刪除 spilled 的資料。</span><span class="sxs-lookup"><span data-stu-id="c2f07-119">Permanently delete the spilled data.</span></span>

5.  <span data-ttu-id="c2f07-120">關閉或刪除調查。</span><span class="sxs-lookup"><span data-stu-id="c2f07-120">Close or delete the investigation.</span></span>


## <a name="before-you-begin"></a><span data-ttu-id="c2f07-121">開始之前</span><span class="sxs-lookup"><span data-stu-id="c2f07-121">Before you begin</span></span>

- <span data-ttu-id="c2f07-p103">您將使用在 Office 365 安全性 & 規範中心中的資料調查 （預覽） 工具建立調查、 spilled 資料、 搜尋並檢閱並進行分析。然後您將使用安全性 & 規範中心 PowerShell 從 Office 365 永久刪除 spilled 的資料。</span><span class="sxs-lookup"><span data-stu-id="c2f07-p103">You'll use the Data Investigations (Preview) tool in the Office 365 Security & Compliance Center to create an investigation, search for the spilled data, and review and analyze it. Then you'll use Security & Compliance Center PowerShell to permanently delete the spilled data from Office 365.</span></span> 

- <span data-ttu-id="c2f07-124">若要建立調查，您必須是在安全性 & 規範中心規範系統管理員角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="c2f07-124">To create an investigation, you have to be a member of the Compliance Administrator role group in the Security & Compliance Center.</span></span>

- <span data-ttu-id="c2f07-p104">若要刪除的郵件，您必須在安全性 & 規範中心組織管理角色群組的成員或指派搜尋及清除的角色。如需將使用者新增至角色群組的資訊，請參閱[授與使用者存取安全性 & 規範中心](../grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="c2f07-p104">To delete messages, you have to be a member of the Organization Management role group in the Security & Compliance Center or be assigned the Search and Purge role. For information about adding users to a role group, see [Give users access to the Security & Compliance Center](../grant-access-to-the-security-and-compliance-center.md).</span></span> 

- <span data-ttu-id="c2f07-p105">若要控制哪些使用者信箱與調查可搜尋的 OneDrive 帳戶，您的組織可以設定規範界限。如需詳細資訊，[設定 eDiscovery 調查的規範界限](../set-up-compliance-boundaries.md)。</span><span class="sxs-lookup"><span data-stu-id="c2f07-p105">To control which user mailboxes and OneDrive accounts an investigator can search, your organization can set up compliance boundaries. For more information, [Set up compliance boundaries for eDiscovery investigations](../set-up-compliance-boundaries.md).</span></span> 

## <a name="step-1-create-a-data-investigation"></a><span data-ttu-id="c2f07-129">步驟 1： 建立資料調查</span><span class="sxs-lookup"><span data-stu-id="c2f07-129">Step 1: Create a data investigation</span></span>

<span data-ttu-id="c2f07-130">若要建立資料調查：</span><span class="sxs-lookup"><span data-stu-id="c2f07-130">To create a data investigation:</span></span>

1. <span data-ttu-id="c2f07-131">移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="c2f07-131">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="c2f07-132">使用公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="c2f07-132">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="c2f07-133">安全性 & 規範中心，按一下 [**資料調查**。</span><span class="sxs-lookup"><span data-stu-id="c2f07-133">In the Security & Compliance Center, click **Data Investigations**.</span></span>
 
4. <span data-ttu-id="c2f07-134">在 [**資料調查 （預覽）** ] 頁面上按一下 [**建立新的調查**。</span><span class="sxs-lookup"><span data-stu-id="c2f07-134">On the **Data Investigations (Preview)** page, click **Create a new investigation**.</span></span>
    
5. <span data-ttu-id="c2f07-p106">在 [**新的資料將正在調查**彈出式] 頁面上授與調查有關 （必要） 的名稱，然後輸入選用調查數字及描述。請注意的名稱必須是唯一您組織中。</span><span class="sxs-lookup"><span data-stu-id="c2f07-p106">On the **New data investigation** flyout page, give the investigation a name (required), and then type an optional investigation number and description. Note that the name must be unique in your organization.</span></span>

6. <span data-ttu-id="c2f07-137">下**您想要建立此調查之後設定其他設定吗？**，執行下列其中一個動作：</span><span class="sxs-lookup"><span data-stu-id="c2f07-137">Under **Do you want to configure additional settings after creating this investigation?**, do one of the following:</span></span>

    - <span data-ttu-id="c2f07-p107">按一下 [**是]** 以建立調查，並在新的案例中顯示 [**設定**] 頁面。這可讓您將成員新增至調查。</span><span class="sxs-lookup"><span data-stu-id="c2f07-p107">Click **Yes** to create the investigation, and display the **Settings** page in the new case. This allows you to add members to the investigation.</span></span>
    
    - <span data-ttu-id="c2f07-p108">按一下 [**否]** 剛建立調查並顯示在 [**資料調查 （預覽）** ] 頁面上的情況下的清單中。如果您選擇這個選項，您會新增將用於將正在調查及預設搜尋及分析設定的唯一成員。您可以將成員新增或變更設定之後建立調查有關的任何時間。</span><span class="sxs-lookup"><span data-stu-id="c2f07-p108">Click **No** to just create the investigation and display it in the list of cases on the **Data Investigations (Preview)** page. If you choose this option, you will be added as the only member of the investigation and the default search and analytics settings will be used. You can add members or change settings any time after the investigation is created.</span></span>

7. <span data-ttu-id="c2f07-143">按一下 [**儲存**] 以建立調查。</span><span class="sxs-lookup"><span data-stu-id="c2f07-143">Click **Save** to create the investigation.</span></span>

    <span data-ttu-id="c2f07-144">新的調查會顯示在 [**資料調查 （預覽）** ] 頁面上的清單。</span><span class="sxs-lookup"><span data-stu-id="c2f07-144">The new investigation is displayed in the list on the **Data Investigations (Preview)** page.</span></span> 

8. <span data-ttu-id="c2f07-145">若要開啟 [將正在調查，按一下 [將正在調查的名稱。</span><span class="sxs-lookup"><span data-stu-id="c2f07-145">To open an investigation, click the name of the investigation.</span></span> 

    <span data-ttu-id="c2f07-146">將正在調查的 [**首頁**] 索引標籤會顯示。</span><span class="sxs-lookup"><span data-stu-id="c2f07-146">The **Home** tab for the investigation is displayed.</span></span> 

> [!TIP]
> <span data-ttu-id="c2f07-147">請考慮建立調查的命名慣例並提供您可以在名稱和描述，讓您可以找出並參照未來如有必要的資訊為多。</span><span class="sxs-lookup"><span data-stu-id="c2f07-147">Consider establishing a naming convention for investigations and provide as much information as you can in the name and description so you can locate and refer to in the future if necessary.</span></span>
 
## <a name="step-2-search-for-the-spilled-data"></a><span data-ttu-id="c2f07-148">步驟 2： 搜尋 spilled 資料</span><span class="sxs-lookup"><span data-stu-id="c2f07-148">Step 2: Search for the spilled data</span></span> 
 
<span data-ttu-id="c2f07-p109">如果您知道哪些的使用者想要搜尋溢出資料，您可以將其新增為其他人感興趣的將其資料來源對應至將正在調查並快速搜尋其信箱和 OneDrive 帳戶。若要將興趣的人員新增至調查，[**感興趣的人員**，和 [**新增人員感興趣**。</span><span class="sxs-lookup"><span data-stu-id="c2f07-p109">If you know which users you want to search for spilled data, you can add them as people of interest to map their data sources to the investigation and quickly search their mailbox and OneDrive account. To add people of interest to the investigation, click **People of interest**, and then click **Add people of interest**.</span></span> 

<span data-ttu-id="c2f07-p110">在 [**搜尋**] 索引標籤中，您可以建立搜尋以尋找 spilled 的資料。您將會使用您用來找出要刪除這些[步驟 4](##step-4:-permanently-delete-the-spilled-data)中的相同郵件的 spilled 的資料的同一個搜尋查詢。如需建立搜尋的詳細資訊，請參閱 ＜ [Create 搜尋以收集資料](create-search-to-collect-data.md)。</span><span class="sxs-lookup"><span data-stu-id="c2f07-p110">On the **Searches** tab, you can create searches to find the spilled data. You will use the same search query that you used to find the spilled data to delete those same messages in [Step 4](##step-4:-permanently-delete-the-spilled-data). For more information about creating searches, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="c2f07-p111">執行搜尋之後，您可預覽搜尋結果和檢視搜尋統計資料來評估效益的搜尋查詢的範例。一旦您識別您要從 Office 365 中刪除的項目，您可以按一下 [**事件**] 索引標籤的 [然後建立事件並新增包含這些項目的搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="c2f07-p111">After you run the search, you can preview samples of search results and view search statistics to evaluate the effectiveness of your search query. Once you identify the items that you want to delete from Office 365, you can click the **Incidents** tab, and then create an incident and add search results that contain those items.</span></span> 

<span data-ttu-id="c2f07-p112">若要這樣做，按一下您想要調查的搜尋。在 [彈出式] 頁面上按一下 [**新增結果事件**並遵循指示。然後事件中檢閱個別的文件、 調查誰有存取權的文件和匯出文件。若要只刪除而不是檢閱這些文件，請前往[步驟 4](##step-4:-permanently-delete-the-spilled-data)。</span><span class="sxs-lookup"><span data-stu-id="c2f07-p112">To do this, click the search that you want to investigate. On the flyout page, click **Add results to incident** and follow the instructions. Then in the incident, you can review individual documents, investigate who had access to documents, and export the documents. To simply delete the documents instead of reviewing them, go to [Step 4](##step-4:-permanently-delete-the-spilled-data).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="c2f07-p113">搜尋查詢中使用關鍵字可能包含您要搜尋的實際 spilled 的資料。例如，如果您搜尋包含社會安全號碼與您的文件會使用其為在搜尋查詢關鍵字，您必須刪除事後以避免進一步 spillage 查詢。您可以刪除搜尋或刪除整個調查有關在[步驟 5](##step-5:-close-or-delete-investigation)。</span><span class="sxs-lookup"><span data-stu-id="c2f07-p113">The keywords that you use in the search query may contain the actual spilled data that you're searching for. For example, if you searching for documents containing a social security number and you use it as a keyword in the search query, you must delete the query afterwards to avoid further spillage. You can delete search or delete the entire investigation in [Step 5](##step-5:-close-or-delete-investigation).</span></span> 

## <a name="step-3-review-and-investigate"></a><span data-ttu-id="c2f07-163">步驟 3： 檢閱及調查</span><span class="sxs-lookup"><span data-stu-id="c2f07-163">Step 3: Review and investigate</span></span> 

<span data-ttu-id="c2f07-p114">在調查，移至 [**事件**] 索引標籤上，按一下 [在您在上一個步驟中建立事件。完成處理工作及搜尋結果會新增至事件之後，您可以檢閱其原生格式、 文字格式或附近原生格式中的個別文件。您可以建立額外的查詢以進一步縮小的文件及標籤文件以指出從您正在調查的研究結果清單。</span><span class="sxs-lookup"><span data-stu-id="c2f07-p114">In the investigation, go to **Incidents** tab and click on the incident that you created in the previous step. After the processing job is completed and the search results are added to the incident, you can review individual documents in their native format, text format, or a near-native format. You can create additional queries to further narrow the list of documents, and tag documents to indicate findings from your investigation.</span></span>

<span data-ttu-id="c2f07-p115">若要群組文件，並取得更多協助您檢閱，按一下 [**管理事件**。在 [**分析**] 磚中按一下 [**分析**]。這將會執行進階的分析例如重複資料偵測、 電子郵件超執行緒，以及佈景主題分析。如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="c2f07-p115">To group documents and get more assistance for your review, click **Manage incident**. In the **Analytics** tile, click **Analyze**. This will run advanced analytics such as duplicate detection, email threading, and theme analysis. For more information, see:</span></span>

- [<span data-ttu-id="c2f07-171">近似重複項偵測</span><span class="sxs-lookup"><span data-stu-id="c2f07-171">Near duplicate detection</span></span>](near-duplicates.md)
- [<span data-ttu-id="c2f07-172">電子郵件威脅</span><span class="sxs-lookup"><span data-stu-id="c2f07-172">Email threading</span></span>](email-threading.md)
- [<span data-ttu-id="c2f07-173">佈景主題</span><span class="sxs-lookup"><span data-stu-id="c2f07-173">Themes</span></span>](themes.md)

<span data-ttu-id="c2f07-p116">若要決定哪些使用者參與資料 spillage，您可以在事件中建立新的查詢，然後使用 [寄件者/作者和收件者條件。這會建立所有寄件者、 收件者和收集的資料已加入至事件中找到的作者的清單。請務必檢查清單，以判斷清單中是否有任何外部使用者。如需詳細資訊，請參閱[搜尋條件](../keyword-queries-and-search-conditions.md#search-conditions)。</span><span class="sxs-lookup"><span data-stu-id="c2f07-p116">To determine which users are involved in the data spillage, you can create a new query in the incident and then use the Sender/Author and Recipients conditions. This will create a list of all senders, recipients and authors found in collected data that was added to the incident. Be sure to examine the list to determine if there are any external users in the list. For more information, see [Search conditions](../keyword-queries-and-search-conditions.md#search-conditions).</span></span>

## <a name="step-4-permanently-delete-the-spilled-data"></a><span data-ttu-id="c2f07-178">步驟 4： 永久刪除 spilled 的資料</span><span class="sxs-lookup"><span data-stu-id="c2f07-178">Step 4: Permanently delete the spilled data</span></span>

### <a name="deleting-mailbox-items"></a><span data-ttu-id="c2f07-179">刪除的信箱項目</span><span class="sxs-lookup"><span data-stu-id="c2f07-179">Deleting mailbox items</span></span>

<span data-ttu-id="c2f07-p117">檢閱並驗證的搜尋結果包含只必須要刪除的電子郵件訊息之後，您可以永久刪除這些執行**新增 ComplianceSearchAction-清除-PurgeType HardDelete**命令中安全性 & 規範中心 PowerShell。指示，請參閱[搜尋和刪除電子郵件訊息](../search-for-and-delete-messages-in-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="c2f07-p117">After you review and validate that the search results contain only the email messages that must be deleted, you can permanently delete them by running the **New-ComplianceSearchAction -Purge -PurgeType HardDelete** command in Security & Compliance Center PowerShell. For instructions, see [Search for and delete email messages](../search-for-and-delete-messages-in-your-organization.md).</span></span> 

<span data-ttu-id="c2f07-p118">請注意，如果您的組織中的信箱啟用單一項目復原永久刪除項目會保留在使用者的 [可復原的項目] 資料夾中 （且可供系統管理員存取） 直到刪除項目保留期間端點 （預設值為 14 天）。此外，如果任何包含溢出資料的信箱處於合法持有或是指派給保留原則，就的訊息將會保留在可復原的項目] 資料夾直到撤除或排除信箱的保留原則。硬碟刪除郵件立即，需要執行其他工作。指示，請參閱[可復原的項目保留的雲端架構信箱上的資料夾內刪除項目](../delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)。</span><span class="sxs-lookup"><span data-stu-id="c2f07-p118">Note that if single item recovery is enabled for mailboxes in your organization, permanently deleted items will be retained in the user's Recoverable items folder (and accessible by admins) until the deleted item retention period ends (default is 14 days). Additionally, if any of the mailboxes that contain spilled data are on a legal hold or assigned to a retention policy, purged message will be retained in Recoverable items folder until the hold is removed or the mailbox is excluded from retention policies. To hard delete messages immediately, you need to perform addition tasks. For instructions, see [Delete items in the Recoverable Items folder of cloud-based mailboxes on hold ](../delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md).</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="c2f07-p119">記錄管理或法務部門檢查之前先移除保留或保留原則。您的組織可能會有定義是否在信箱保留原則或建立資料 spillage 事件採用優先順序。</span><span class="sxs-lookup"><span data-stu-id="c2f07-p119">Check with your records management or legal departments before removing a hold or retention policy. Your organization may have a policy that defines whether a mailbox on hold or a data spillage incident takes priority.</span></span> 

### <a name="deleting-site-items"></a><span data-ttu-id="c2f07-188">刪除網站項目</span><span class="sxs-lookup"><span data-stu-id="c2f07-188">Deleting site items</span></span>

<span data-ttu-id="c2f07-p120">商務帳戶從 SharePoint 網站或 OneDrive 永久刪除文件，您必須將它刪除而且然後您必須從網站刪除然後將其從網站集合資源回收筒刪除。指示，請參閱[刪除文件中的 SharePoint 和 OneDrive](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#deleting-documents-in-sharepoint-online-and-onedrive-for-business)。</span><span class="sxs-lookup"><span data-stu-id="c2f07-p120">To permanently delete a document from a SharePoint site or OneDrive for Business account, you have to delete it and then you have to delete from the site and then delete it from the site collection Recycle Bin. For instructions, see [Delete documents in SharePoint and OneDrive](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#deleting-documents-in-sharepoint-online-and-onedrive-for-business).</span></span>

<span data-ttu-id="c2f07-p121">或者，您可以刪除可能包含溢出資料整個網站集合。指示，請參閱[刪除網站集合](https://docs.microsoft.com/sharepoint/delete-site-collection)。</span><span class="sxs-lookup"><span data-stu-id="c2f07-p121">Alternatively, you can delete an entire site collection that might contained spilled data. For instructions, see [Delete a site collection](https://docs.microsoft.com/sharepoint/delete-site-collection).</span></span>

## <a name="step-5-close-or-delete-the-investigation"></a><span data-ttu-id="c2f07-193">步驟 5： 關閉或刪除調查</span><span class="sxs-lookup"><span data-stu-id="c2f07-193">Step 5: Close or delete the investigation</span></span>

<span data-ttu-id="c2f07-p122">刪除來源的內容位置 （信箱或網站） 中的文件之後，您仍必須將您新增至事件為您正在調查的一部分這些文件的複本。若要避免進一步資料 spillage，則應考慮刪除調查。</span><span class="sxs-lookup"><span data-stu-id="c2f07-p122">After you delete documents in the source content locations (mailboxes or sites), you will still have copies of these documents that you added to incidents as part of your investigation. To avoid further data spillage, you should consider deleting the investigation.</span></span>

<span data-ttu-id="c2f07-196">若要刪除調查：</span><span class="sxs-lookup"><span data-stu-id="c2f07-196">To delete an investigation:</span></span>

1. <span data-ttu-id="c2f07-197">在 [**設定**] 索引標籤上按一下 [**將正在調查資訊**]。</span><span class="sxs-lookup"><span data-stu-id="c2f07-197">On the **Settings** tab, click **Investigation information**.</span></span>

2. <span data-ttu-id="c2f07-198">按一下 [**刪除案例**。</span><span class="sxs-lookup"><span data-stu-id="c2f07-198">Click  **Delete case**.</span></span> 

<span data-ttu-id="c2f07-p123">如果您不需要刪除調查或您要儲存您收集期間調查有關的資訊，您可以按一下 [**關閉案例**。日後，您可以重新開啟關閉的調查。</span><span class="sxs-lookup"><span data-stu-id="c2f07-p123">If you don't need to delete the investigation or if you want to save the information that you collected during the investigation, you can click **Close case**. At a later date, you can re-open closed investigations.</span></span>