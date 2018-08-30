---
title: eDiscovery 解決方案數列的資料 spillage 案例-搜尋和清除
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d945f7dd-f62f-4ca7-b3e7-469824cfd493
description: 使用 Office 365 eDiscovery 及搜尋工具來管理，並在組織中建立資料 spillage 事件回應。
ms.openlocfilehash: 2bf17923408bd5cf8325d27a38595331d169906f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526261"
---
# <a name="ediscovery-solution-series-data-spillage-scenario---search-and-purge"></a><span data-ttu-id="c7dc4-103">eDiscovery 解決方案系列： 資料 spillage 案例-搜尋和清除</span><span class="sxs-lookup"><span data-stu-id="c7dc4-103">eDiscovery solution series: Data spillage scenario - Search and purge</span></span>

 <span data-ttu-id="c7dc4-p101">**資料 spillage 及不可您不知吗？** 機密文件發行至不受信任的環境時資料 spillage。當偵測到資料 spillage 事件時，務必快速評估的大小及位置的 spillage、 檢查周圍、 使用者活動及則從系統永久清除 spilled 的資料。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-p101">**What is data spillage and why should you care?** Data spillage is when a confidential document is released into an untrusted environment. When a data spillage incident is detected, it's important to quickly assess the size and locations of the spillage, examine user activities around it,  and then permanently purge the spilled data from the system.</span></span> 
  
## <a name="data-spillage-scenario"></a><span data-ttu-id="c7dc4-107">資料 spillage 案例</span><span class="sxs-lookup"><span data-stu-id="c7dc4-107">Data spillage scenario</span></span>

<span data-ttu-id="c7dc4-p102">您是在 contoso 公司負責人資訊安全主管。您要得知其中員工不知情的情況下高度機密文件與多人共用透過電子郵件資料 spillage 情況。您想要快速評估者接收到此文件內部及外部。之後，您想與其他現場，檢閱，然後從 Office 365 永久移除資料共用案例研究結果。將正在調查完成後，您想要與任何供未來參照永久移除與其他案例的詳細資料證據產生報告。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-p102">You’re a lead information security officer at Contoso. You are informed of a data spillage situation where an employee unknowingly shared a highly confidential document with multiple people through email. You want to quickly assess who received this document internally and externally. Once identified, you would like to share case findings with other investigators to review, and then permanently remove the data from Office 365. After the investigation is complete, you want to generate a report with the evidence of permanent removal and other case details for any future reference.</span></span>
  
### <a name="scope-of-this-article"></a><span data-ttu-id="c7dc4-113">本文的範圍</span><span class="sxs-lookup"><span data-stu-id="c7dc4-113">Scope of this article</span></span>

<span data-ttu-id="c7dc4-p103">本文件提供如何將永久移除郵件來自 Office 365，讓它不是可存取或可復原清單中的指示。若要刪除一則訊息並使其可復原已刪除的項目保留期間到期之前，請參閱[Search for 和 Office 365 組織中的刪除電子郵件訊息](search-for-and-delete-messages-in-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-p103">This document provides a list of instructions on how to permanently remove a message from Office 365 so that it's not accessible or recoverable. To delete a message and make it recoverable until the deleted item retention period expires, see [Search for and delete email messages in your Office 365 organization](search-for-and-delete-messages-in-your-organization.md).</span></span>
  
## <a name="workflow-for-managing-data-spillage-incidents"></a><span data-ttu-id="c7dc4-116">工作流程以管理資料 spillage 事件</span><span class="sxs-lookup"><span data-stu-id="c7dc4-116">Workflow for managing data spillage incidents</span></span>

<span data-ttu-id="c7dc4-117">以下是如何管理資料 spillage 事件：</span><span class="sxs-lookup"><span data-stu-id="c7dc4-117">Here's a how to manage a data spillage incident:</span></span>

![管理資料 spillage 事件的步驟 8 工作流程](media/O365-eDiscoverySolutions-DataSpillage-workflow.png)
  
[<span data-ttu-id="c7dc4-119">（選用）步驟 1： 管理人員可以存取案例和設定規範界限</span><span class="sxs-lookup"><span data-stu-id="c7dc4-119">(Optional) Step 1: Manage who can access the case and set compliance boundaries</span></span>](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries)<br/>
[<span data-ttu-id="c7dc4-120">步驟 2： 建立 eDiscovery 案例</span><span class="sxs-lookup"><span data-stu-id="c7dc4-120">Step 2: Create an eDiscovery case</span></span>](#step-2-create-an-ediscovery-case)<br/>
[<span data-ttu-id="c7dc4-121">步驟 3： 搜尋 spilled 資料</span><span class="sxs-lookup"><span data-stu-id="c7dc4-121">Step 3: Search for the spilled data</span></span>](#step-3-search-for-the-spilled-data)<br/>
[<span data-ttu-id="c7dc4-122">步驟 4： 檢閱並驗證案例研究結果</span><span class="sxs-lookup"><span data-stu-id="c7dc4-122">Step 4: Review and validate case findings</span></span>](#step-4-review-and-validate-case-findings)<br/>
[<span data-ttu-id="c7dc4-123">步驟 5： 使用郵件追蹤記錄檔以檢查如何溢出資料的形式共用</span><span class="sxs-lookup"><span data-stu-id="c7dc4-123">Step 5: Use message trace log to check how spilled data was shared</span></span>](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared)<br/>
[<span data-ttu-id="c7dc4-124">步驟 6： 準備信箱</span><span class="sxs-lookup"><span data-stu-id="c7dc4-124">Step 6: Prepare the mailboxes</span></span>](#step-6-prepare-the-mailboxes)<br/>
[<span data-ttu-id="c7dc4-125">步驟 7： 永久刪除 spilled 的資料</span><span class="sxs-lookup"><span data-stu-id="c7dc4-125">Step 7: Permanently delete the spilled data</span></span>](#step-7-permanently-delete-the-spilled-data)<br/>
[<span data-ttu-id="c7dc4-126">步驟 8： 驗證、 提供證明刪除，及稽核</span><span class="sxs-lookup"><span data-stu-id="c7dc4-126">Step 8: Verify, provide a proof of deletion, and audit</span></span>](#step-8-verify-provide-a-proof-of-deletion-and-audit)<br/>

## <a name="things-to-know-before-you-start"></a><span data-ttu-id="c7dc4-127">須知事項開始之前</span><span class="sxs-lookup"><span data-stu-id="c7dc4-127">Things to know before you start</span></span>

- <span data-ttu-id="c7dc4-p104">當信箱處於 [保留時] 直到保留期間到期或保留已刪除的郵件會維持可復原的項目] 資料夾中。[步驟 6](#step-6-prepare-the-mailboxes)說明如何從信箱移除保留。記錄管理或法務部門檢查之前先移除保留。您的組織可能已定義是否在信箱保留原則或建立資料 spillage 事件採用優先順序。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-p104">When a mailbox is on hold, a deleted message remains in the Recoverable Items folder until the retention period expires or the hold is released. [Step 6](#step-6-prepare-the-mailboxes) describes how to remove hold from the mailboxes. Check with your records management or legal departments before removing the hold. Your organization might have a policy that defines whether a mailbox on hold or a data spillage incident takes priority.</span></span> 
    
- <span data-ttu-id="c7dc4-p105">若要控制哪些使用者信箱資料 spillage 調查可以搜尋並管理人員可以存取案例，您可以設定規範界限及建立自訂角色群組，在[步驟 1](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries)中所述。為達成此目的，您必須是 「 組織管理角色群組的成員或角色的管理角色指派。如果您或在組織中的系統管理員已經有設定規範界限，您可以略過步驟 1。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-p105">To control which user mailboxes an data spillage investigator can search and manage who can access the case, you can set up compliance boundaries and create a custom role group, which is described in [Step 1](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries). To do this, you have to be a member of the Organization Management role group or be assigned the role management role. If you or in administrator in your organization has already set compliance boundaries, you can skip Step 1.</span></span>
    
- <span data-ttu-id="c7dc4-p106">若要建立案例，您必須是 「 eDiscovery 管理員角色群組的成員或是已指派的案例管理角色自訂角色群組的成員。如果您不是成員，要求 Office 365 管理員[將您新增至 eDiscovery 管理員角色群組](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-p106">To create a case, you must be a member of the eDiscovery Manager role group or be a member of a custom role group that's assigned the Case Management role. If you're not a member, ask an Office 365 administrator to [add you to the eDiscovery manager role group](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="c7dc4-p107">若要刪除溢出至您的組織的資料，您需要在 Exchange Online PowerShell 中使用[Search-mailbox DeleteContent](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Search-Mailbox?view=exchange-ps)命令。此外，若要使用*DeleteContent*參數，您也必須是 Exchange Online 中有指派的信箱匯入 / 匯出 」 角色的角色群組的成員。請參閱[管理角色群組](https://technet.microsoft.com/library/jj657480%28v=exchg.150%29.aspx)的 「 將角色新增至角色群組 」 一節。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-p107">To delete data that's spilled into your organization, you need to use the [Search-Mailbox -DeleteContent](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Search-Mailbox?view=exchange-ps) command in Exchange Online PowerShell. Additionally, to use the  *DeleteContent* parameter, you also have to be a member of a role group in Exchange Online that's assigned the Mailbox Import Export role. See the "Add a role to a role group" section in [Manage role groups](https://technet.microsoft.com/library/jj657480%28v=exchg.150%29.aspx).</span></span>
    
- <span data-ttu-id="c7dc4-p108">若要在步驟 8 中搜尋 Office 365 稽核記錄檔 eDiscovery 活動，稽核必須開啟您的組織。您可搜尋過去 90 天內所執行的活動。若要深入了解如何啟用及使用稽核，請參閱[稽核資料 spillage 調查程序](#auditing-the-data-spillage-investigation-process)] 區段中的步驟 8。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-p108">To search the Office 365 audit log eDiscovery activities in Step 8, auditing must be turned on for your organization. You can search for activities that were performed within the last 90 days. To learn more about how to enable and use auditing, see the [Auditing the data spillage investigation process](#auditing-the-data-spillage-investigation-process) section in Step 8.</span></span> 
    
## <a name="optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries"></a><span data-ttu-id="c7dc4-143">（選用）步驟 1： 管理人員可以存取案例和設定規範界限</span><span class="sxs-lookup"><span data-stu-id="c7dc4-143">(Optional) Step 1: Manage who can access the case and set compliance boundaries</span></span>

<span data-ttu-id="c7dc4-p109">隨您組織的作法是，您必須控制可存取用來建立資料 spillage 事件的調查並設定規範界限 eDiscovery 案例的人員。執行這項作業的最簡單方式是將現場新增為 Office 365 的安全性與規範中心中的現有角色群組的成員並再新增 eDiscovery 案例的成員身分的角色群組。內建的 eDiscovery 角色群組以及如何將成員新增至 eDiscovery 案例的相關資訊，請參閱[指派 Office 365 安全性 eDiscovery 權限&amp;規範中心](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-p109">Depending on your organizational practice, you need to control who can access the eDiscovery case used to investigate a data spillage incident and set up compliance boundaries. The easiest way to do this is to add investigators as members of an existing role group in the Office 365 Security & Compliance Center and then add the role group as a member of the eDiscovery case. For information about the built-in eDiscovery role groups and how to add members to an eDiscovery case, see [Assign eDiscovery permissions in the Office 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
  
<span data-ttu-id="c7dc4-p110">您也可以建立新的角色群組的對齊您組織的需求。例如，您可能會想存取及進行共同作業的所有資料 spillage 案例組織中的資料 spillage 現場群組。您可以這麼做建立"資料 Spillage 調查 」 角色群組、 指派適當的角色 （匯出、 RMS 解密、 檢閱、 Preview、 規範搜尋及案例管理）、 資料 spillage 現場新增至角色群組，然後將資料 spillage eDiscovery 案例的成員身分的角色群組。請參閱[Set up Office 365 中的 eDiscovery 調查的規範界限](set-up-compliance-boundaries.md)如何執行這項作業的詳細指示。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-p110">You can also create a new role group that aligns with your organizational needs. For example, you might want a group of data spillage investigators in the organization to access and collaborate on all data spillage cases. You can do this by creating a "Data Spillage Investigator" role group, assigning the appropriate roles (Export, RMS Decrypt, Review, Preview, Compliance Search, and Case Management), adding the data spillage investigators to the role group, and then adding the role group as a member of the data spillage eDiscovery case. See [Set up compliance boundaries for eDiscovery investigations in Office 365](set-up-compliance-boundaries.md) for detailed instructions on how to do this.</span></span> 
  
## <a name="step-2-create-an-ediscovery-case"></a><span data-ttu-id="c7dc4-151">步驟 2： 建立 eDiscovery 案例</span><span class="sxs-lookup"><span data-stu-id="c7dc4-151">Step 2: Create an eDiscovery case</span></span>

<span data-ttu-id="c7dc4-p111">EDiscovery 案例提供有效的方法來管理您的資料 spillage 調查。您可以將成員新增至您在步驟 1 中建立的角色群組、 角色群組新增新的 eDiscovery 案例的成員身分執行反覆執行搜尋以尋找 spilled 的資料、 將共用、 追蹤的情況下，狀態報表匯出以及然後參照回 c 的詳細資訊如果需要，ase。請考慮建立用於資料 spillage 事件、 eDiscovery 案例的命名慣例及提供方式，儘可能案例名稱與描述，讓您可以找出並參照未來如有必要的資訊。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-p111">An eDiscovery case provides an effective way to manage your data spillage investigation. You can add members to the role group that you created in Step 1, add the role group as a member of new a eDiscovery case, perform iterative searches to find the spilled data, export a report to share, track the status of the case, and then refer back to the details of the case if needed. Consider establishing a naming convention for eDiscovery cases used for data spillage incidents, and provide as much information as you can in the case name and description so you can locate and refer to in the future if necessary.</span></span>
  
<span data-ttu-id="c7dc4-p112">若要建立新的案例，您可以使用 eDiscovery 安全性&amp;規範中心。請參閱[[Office 365 安全性及規範中心中的 eDiscovery 案例](ediscovery-cases.md#step-2-create-a-new-case)中的 「 建立新的案例 」。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-p112">To create a new case, you can use eDiscovery in the Security &amp; Compliance Center. See "Create a new case" in [eDiscovery Cases in the Office 365 Security & Compliance Center](ediscovery-cases.md#step-2-create-a-new-case).</span></span>
  
## <a name="step-3-search-for-the-spilled-data"></a><span data-ttu-id="c7dc4-157">步驟 3： 搜尋 spilled 資料</span><span class="sxs-lookup"><span data-stu-id="c7dc4-157">Step 3: Search for the spilled data</span></span>

<span data-ttu-id="c7dc4-p113">既然您已經建立案例和受管理的存取，您可以使用反覆搜尋來尋找 spilled 的資料並找出包含 spilled 的資料之信箱的大小寫。您將會使用您用來找出要刪除那些相同的郵件在[步驟 7](#step-7-permanently-delete-the-spilled-data)中的電子郵件訊息的同一個搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-p113">Now that you've created a case and managed access, you can use the case to iteratively search to find the spilled data and identify the mailboxes that contain the spilled data. You will use the same search query that you used to find the email messages to delete those same messages in [Step 7](#step-7-permanently-delete-the-spilled-data).</span></span>
  
<span data-ttu-id="c7dc4-160">若要建立內容的搜尋相關聯的 eDiscovery 案例，請參閱[[Office 365 安全性及規範中心中的 eDiscovery 案例](ediscovery-cases.md#step-5-create-and-run-a-content-search-associated-with-a-case)中的 「 建立和執行與案例相關聯之內容的搜尋 」。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-160">To create a content searches associated with an eDiscovery case, see "Create and run a Content Search associated with a case" in [eDiscovery Cases in the Office 365 Security & Compliance Center](ediscovery-cases.md#step-5-create-and-run-a-content-search-associated-with-a-case).</span></span>
  
 <span data-ttu-id="c7dc4-p114">**重要：** 搜尋查詢中使用關鍵字可能包含您要搜尋的實際 spilled 的資料。例如，如果搜尋文件包含社會安全號碼與您使用 it 如搜尋關鍵字，您必須刪除事後以避免進一步 spillage 查詢。請參閱在步驟 8 中的 [[刪除的搜尋查詢](#deleting-the-search-query)。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-p114">**Important:** The keywords that you use in the search query may contain the actual spilled data that you're searching for. For example, if you searching for documents containing a social security number and you use the it as search keyword, you must delete the query afterwards to avoid further spillage. See [Deleting the search query](#deleting-the-search-query) in Step 8.</span></span> 
  
## <a name="step-4-review-and-validate-case-findings"></a><span data-ttu-id="c7dc4-164">步驟 4： 檢閱並驗證案例研究結果</span><span class="sxs-lookup"><span data-stu-id="c7dc4-164">Step 4: Review and validate case findings</span></span>

<span data-ttu-id="c7dc4-p115">建立內容的搜尋之後，您需要檢閱並驗證搜尋結果並確認其包含只的必須刪除電子郵件。在內容搜尋，您可預覽 1000 封電子郵件隨機取樣不含匯出搜尋結果，以避免進一步資料 spillage。您可以閱讀更多關於在預覽限制[Limits for Office 365 安全性內容搜尋&amp;規範中心](limits-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-p115">After you create a content search, you need to review and validate that the search results and verify that they consist only of the email messages that must be deleted. In a content search, you can preview a random sampling of 1,000 email messages without exporting the search results to avoid further data spillage. You can read more about the preview limitations at [Limits for Content Search in the Office 365 Security &amp; Compliance Center](limits-for-content-search.md).</span></span>
  
<span data-ttu-id="c7dc4-p116">如果您有超過 1000 個信箱或超過 100 封電子郵件訊息每個可供檢閱的信箱，您可以使用其他關鍵字或日期範圍或寄件者/收件者的條件將首次搜尋分割成多個搜尋並檢閱每個搜尋結果個別。請務必注意下時刪除訊息在[步驟 7](#step-7-permanently-delete-the-spilled-data)中的所使用的所有搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-p116">If you have more than 1,000 mailboxes or more than 100 email messages per mailbox to review, you can divide the initial search into multiple searches by using additional keywords or conditions such as date range or sender/recipient and review the results of each search individually. Make sure to note down all search queries to use when you delete messages in [Step 7](#step-7-permanently-delete-the-spilled-data).</span></span>

<span data-ttu-id="c7dc4-p117">如果 okay 或使用者指派 Office 36 E5 授權，您可以檢查一次使用 Office 365 進階 eDiscovery 的最多 10000 個搜尋結果。檢閱 10000 個以上的電子郵件訊息時，您可以除以日期範圍的搜尋查詢和搜尋結果會依日期排序個別檢閱每個搜尋結果。進階 ediscovery 可以標記 [預覽] 面板中使用**標籤設為**功能的搜尋結果，而您所標示的標籤來篩選搜尋結果。當您與次要檢閱者共同作業將很有用。進階 eDiscovery，例如光學字元辨識、 電子郵件超執行緒，以及預測撰寫程式碼中使用其他分析工具您可以快速處理及檢閱數千個郵件並加以標記供進一步檢閱。請參閱[Office 365 進階 ediscovery 快速設定](quick-setup-for-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-p117">If a custodian or end user is assigned an Office 36 E5 license, you can examine up to 10,000 search results at once using Office 365 Advanced eDiscovery. If there are more than 10,000 email messages to review, you can divide the search query by date range and review each result individually as search results are sorted by date. In Advanced eDiscovery, you can tag search results using the **Label as** feature in the preview panel and filter the search result by the tag you labeled. This is helpful when you collaborate with a secondary reviewer. By using additional analytics tools in Advanced eDiscovery, such as optical character recognition, email threading, and predictive coding, you can quickly process and review thousands of messages and tag them for further review. See [Quick setup for Office 365 Advanced eDiscovery](quick-setup-for-advanced-ediscovery.md).</span></span>

<span data-ttu-id="c7dc4-p118">當您尋找電子郵件訊息內含溢出資料時，請檢查要判斷是否它的形式共用外部之郵件的收件者。若要進一步追蹤訊息，您可以收集寄件者資訊和日期範圍讓您可以在[步驟 5 中](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared)有相關描述使用郵件追蹤記錄檔。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-p118">When you find an email message that contains spilled data, check the recipients of the message to determine if it was shared externally. To further trace an message, you can collect sender information and date range so you can use the message trace logs, which is described in [Step 5](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared).</span></span>

<span data-ttu-id="c7dc4-p119">確認搜尋結果的 Afer，可能會想要次要檢閱與其他人共用您發現項目。您指派給在步驟 1 中的大小寫的人員可以檢閱 eDiscovery 及進階的 eDiscovery 案件內容及核准案例研究結果。您也可以產生報表不含匯出實際內容。您也可以使用這個相同的報告為刪除，在[步驟 8](#step-8-verify-provide-a-proof-of-deletion-and-audit)中所述的概念。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-p119">Afer you verified the search results, you may want to share your findings with others for a secondary review. People who you assigned to the case in Step 1 can review the case content in both eDiscovery and Advanced eDiscovery and approve case findings. You can also generate a report without exporting the actual content. You can also use this same report as a proof of deletion, which is described in [Step 8](#step-8-verify-provide-a-proof-of-deletion-and-audit).</span></span>
  
 <span data-ttu-id="c7dc4-182">**若要產生統計的報告：**</span><span class="sxs-lookup"><span data-stu-id="c7dc4-182">**To generate a statistical report:**</span></span>
  
1. <span data-ttu-id="c7dc4-183">移至 eDiscovery 案例中，在 [**搜尋**] 頁面上，按一下 [搜尋想要產生的報告。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-183">Go to the **Search** page in the eDiscovery case, and click the search that you want to generate a report for.</span></span> 
    
2. <span data-ttu-id="c7dc4-184">在 [彈出式] 頁面上，按一下 [**更多 > 匯出報告**。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-184">On the flyout page, click **More > Export report**.</span></span>
 
      <span data-ttu-id="c7dc4-185">會顯示 [匯出報告] 頁面。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-185">The Export report page is displayed.</span></span>

    ![選取 [搜尋] 和 [更多 > 匯出彈出式] 頁面上的報表](media/O365-eDiscoverySolutions-DataSpillage-ExportReport1.png)
    
3. <span data-ttu-id="c7dc4-187">選取**所有項目，包括類有無法辨認的格式來加密或未編製索引的其他原因**，然後按一下 [**產生報表**。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-187">Select **All items, including ones that have unrecognized format, are encrypted, or weren’t indexed for other reasons** and then click **Generate report**.</span></span>

4. <span data-ttu-id="c7dc4-p120">在 eDiscovery 案例中，按一下 [要顯示的匯出工作清單的 [**匯出**]。您必須按一下 [更新以顯示您剛才建立的匯出工作清單的 [**重新整理**。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-p120">In the eDiscovery case, click **Export** to display the list of export jobs. You may have to click **Refresh** to update the list to display the export job you just created.</span></span>

5. <span data-ttu-id="c7dc4-190">按一下匯出工作，並再按一下 [**下載**報告彈出式] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-190">Click the export job, and then click **Download** report on the flyout page.</span></span>
 
    ![在 [匯出] 頁面上按一下匯出] 和 ["下載報告"](media/O365-eDiscoverySolutions-DataSpillage-ExportReport2.png)

<span data-ttu-id="c7dc4-p121">**匯出的摘要**報告包含位置找到結果與大小的搜尋結果數目。您可以使用這比較刪除之後所產生的報表，並提供以證明刪除。**結果**報告包含更詳細的摘要的搜尋結果，包括主旨、 寄件者、 收件者，如果已讀取的電子郵件、 日期和每個郵件的大小。如果這份報告的詳細資料的任何包含該實際 spilled 的資料，請務必將正在調查完成時永久刪除 Results.csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-p121">The **Export Summary** report contains the number of locations found with results and the size of the search results. You can use this to compare with the report generated after deletion and provide as a proof of deletion. The **Results** report contains a more detailed summary of the search results, including the subject, sender, recipients, if the email was read, dates, and size of each message. If any of the details in this report contains that actual spilled data, be sure to permanently delete the Results.csv file when the investigation is complete.</span></span>

<span data-ttu-id="c7dc4-196">如需匯出報告的詳細資訊，請參閱[匯出內容搜尋報告](export-a-content-search-report.md)。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-196">For more information about exporting reports, see [Export a Content Search report](export-a-content-search-report.md).</span></span>
    
## <a name="step-5-use-message-trace-log-to-check-how-spilled-data-was-shared"></a><span data-ttu-id="c7dc4-197">步驟 5： 使用郵件追蹤記錄檔以檢查如何溢出資料的形式共用</span><span class="sxs-lookup"><span data-stu-id="c7dc4-197">Step 5: Use message trace log to check how spilled data was shared</span></span>

<span data-ttu-id="c7dc4-p122">如果溢出資料的電子郵件的形式共用的進一步調查，您可以選擇性地查詢郵件追蹤記錄檔的寄件者資訊與您在步驟 4 中所收集的日期範圍資訊。請注意目的保留期間的郵件追蹤 30 天的即時資料及 90 天的歷程資料。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-p122">To further investigate if email with spilled data was shared, you can optionally query the message trace logs with the sender information and the date range information that you gathered in Step 4. Note that the retention period for message trace is 30 days for real time data and 90 days for historical data.</span></span>
  
<span data-ttu-id="c7dc4-p123">您可以使用郵件追蹤的安全性與規範中心或使用對應 cmdlet 在 Exchange Online PowerShell。請務必注意郵件追蹤並不提供完整保證在傳回的資料完整性。如需使用郵件追蹤的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="c7dc4-p123">You can use Message trace in the Security & Compliance Center or use the corresponding cmdlets in Exchange Online PowerShell. It's important to note that message tracing doesn't offer full guarantees on the completeness of data returned. For more information about using Message trace, see:</span></span> 
  
- [<span data-ttu-id="c7dc4-203">郵件追蹤的 Office 365 安全性&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="c7dc4-203">Message trace in the Office 365 Security &amp; Compliance Center</span></span>](https://support.office.com/article/3e64f99d-ac33-4aba-91c5-9cb4ca476803.aspx)
    
- [<span data-ttu-id="c7dc4-204">新的 Message Trace in Office 365 安全性&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="c7dc4-204">New Message Trace in Office 365 Security &amp; Compliance Center</span></span>](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)
    
## <a name="step-6-prepare-the-mailboxes"></a><span data-ttu-id="c7dc4-205">步驟 6： 準備信箱</span><span class="sxs-lookup"><span data-stu-id="c7dc4-205">Step 6: Prepare the mailboxes</span></span>

<span data-ttu-id="c7dc4-p124">檢閱並驗證的搜尋結果包含必須要刪除的郵件之後，您需要收集受影響信箱時您執行**搜尋信箱 DeleteContent**命令在步驟 7 中使用的電子郵件地址清單。您也可以準備才能永久刪除電子郵件訊息根據是否包含 spilled 的資料或任何這些信箱位於音樂信箱上啟用單一項目復原的信箱。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-p124">After you review and validate that the search results contains only the messages that must be deleted, you need to collect a list of the email addresses of the impacted mailboxes to use in Step 7 when you run the **Search-Mailbox -DeleteContent** command. You may also have to prepare the mailboxes before you can permanently delete email messages depending on whether single item recovery is enabled on the mailboxes that contain the spilled data or if any of those mailboxes are on hold.</span></span>
  
### <a name="get-a-list-of-addresses-of-mailboxes-with-spilled-data"></a><span data-ttu-id="c7dc4-208">要取得的信箱溢出資料的地址清單</span><span class="sxs-lookup"><span data-stu-id="c7dc4-208">Get a list of addresses of mailboxes with spilled data</span></span>

<span data-ttu-id="c7dc4-209">有兩種方式來收集溢出資料的信箱的電子郵件地址清單。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-209">There are two ways to collect a list of email addresses of mailboxes with spilled data.</span></span>

<span data-ttu-id="c7dc4-210">**做法 1： 取得信箱溢出資料的地址清單**</span><span class="sxs-lookup"><span data-stu-id="c7dc4-210">**Option 1: Get a list of addresses of mailboxes with spilled data**</span></span>

1. <span data-ttu-id="c7dc4-211">開啟 eDiscovery 案例、 移至 [**搜尋**] 頁面並選取適當的內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-211">Open the eDiscovery case, go to the **Search** page and select the appropriate content search.</span></span> 
    
2. <span data-ttu-id="c7dc4-212">在 [彈出式] 頁面上按一下 [**檢視結果**。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-212">On the flyout page, click **View results**.</span></span>
    
3. <span data-ttu-id="c7dc4-213">在**個別的結果**] 下拉式清單中，按一下 [**搜尋統計資料**。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-213">In the **Individual results** drop down list, click **Search statistics**.</span></span>
    
4. <span data-ttu-id="c7dc4-214">在 [**類型**] 下拉式清單中，按一下 [**上方的位置**。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-214">In the **Type** drop down list, click **Top locations**.</span></span>
    
    ![取得包含在搜尋統計資料上方的位置] 頁面上的搜尋結果的信箱的清單](media/O365-eDiscoverySolutions-DataSpillage-TopLocations.png)

    <span data-ttu-id="c7dc4-p125">會顯示包含搜尋結果的信箱的清單。也會顯示每個信箱中比對搜尋查詢的項目數。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-p125">A list of mailboxes that contain search results is displayed. The number of items in each mailbox that match the search query is also displayed.</span></span>
    
5. <span data-ttu-id="c7dc4-218">複製清單中的資訊並將它儲存到檔案或按一下 [**下載**下載至 CSV 檔案的資訊。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-218">Copy the information in the list and save it to a file or click **Download** to download the information to a CSV file.</span></span> 
    
<span data-ttu-id="c7dc4-219">**選項 2： 取得信箱位置從匯出報告**</span><span class="sxs-lookup"><span data-stu-id="c7dc4-219">**Option 2: Get mailbox locations from the export report**</span></span>

<span data-ttu-id="c7dc4-p126">在 [[步驟 4](#step-4-review-and-validate-case-findings)中開啟您下載匯出摘要報告。在報表中第一欄中，每個信箱的電子郵件地址會列於 [**位置**] 下。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-p126">Open the Export Summary report that you downloaded in [Step 4](#step-4-review-and-validate-case-findings). In the first column in the report, the email address of each mailbox is listed under **Locations**.</span></span>
  
### <a name="prepare-the-mailboxes-so-you-can-delete-the-spilled-data"></a><span data-ttu-id="c7dc4-222">準備讓您可以刪除 spilled 的資料的信箱</span><span class="sxs-lookup"><span data-stu-id="c7dc4-222">Prepare the mailboxes so you can delete the spilled data</span></span>

<span data-ttu-id="c7dc4-p127">如果已啟用單一項目復原或信箱處於保留狀態，永久刪除 （清除） 的訊息將會保留在可復原的項目] 資料夾中。如此可清除溢出資料之前，需要檢查現有的信箱設定和停用單一項目復原，並且移除任何保留或 Office 365 保留原則。請記住您可以準備一次一個信箱，然後在不同的信箱上執行相同的命令或建立 PowerShell 指令碼以準備在同一時間的多個信箱。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-p127">If single item recovery is enabled or if a mailbox is placed on hold, a permanently deleted (purged) message will be retained in Recoverable Items folder. So before you can purge spilled data, you need to check the existing mailbox configurations and disable single item recovery and remove any hold or Office 365 retention policy. Keep in mind that you can prepare one mailbox at a time, and then run the same command on different mailboxes or create a PowerShell script to prepare multiple mailboxes at the same time.</span></span>

- <span data-ttu-id="c7dc4-226">請參閱 「 步驟 1： 收集信箱的相關資訊 」 中如需如何檢查是否啟用單一項目復原或如果信箱處於保留或指派給的指示的 [[可復原的項目保留的雲端架構信箱上的資料夾內刪除項目](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-1-collect-information-about-the-mailbox)保留原則。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-226">See "Step 1: Collect information about the mailbox" in [Delete items in the Recoverable Items folder of cloud-based mailboxes on hold](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-1-collect-information-about-the-mailbox) for instructions about how to check if single item recovery is enabled or if the mailbox is placed on hold or it's assigned to a retention policy.</span></span> 
    
- <span data-ttu-id="c7dc4-227">請參閱 「 步驟 2： 準備信箱"中如需停用單一項目復原指示的 [[可復原的項目保留的雲端架構信箱上的資料夾內刪除項目](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-2-prepare-the-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-227">See "Step 2: Prepare the mailbox" in [Delete items in the Recoverable Items folder of cloud-based mailboxes on hold](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-2-prepare-the-mailbox) for instructions about disabling single item recovery.</span></span> 
    
- <span data-ttu-id="c7dc4-228">請參閱 「 步驟 3： 從信箱移除所有保留"中如需如何從信箱都移除保留或保留原則的指示的 [[可復原的項目保留的雲端架構信箱上的資料夾內刪除項目](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-3-remove-all-holds-from-the-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-228">See "Step 3: Remove all holds from the mailbox" in [Delete items in the Recoverable Items folder of cloud-based mailboxes on hold](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-3-remove-all-holds-from-the-mailbox) for instructions about how to remove a hold or retention policy from a mailbox.</span></span> 
    
 <span data-ttu-id="c7dc4-p128">**重要：** 記錄管理或法務部門檢查之前先移除保留或保留原則。您的組織可能會有定義是否在信箱保留原則或建立資料 spillage 事件採用優先順序。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-p128">**Important:** Check with your records management or legal departments before removing a hold or retention policy. Your organization may have a policy that defines whether a mailbox on hold or a data spillage incident takes priority.</span></span> 
  
<span data-ttu-id="c7dc4-p129">請務必確認已永久刪除 spilled 的資料之後還原至先前的設定的信箱。請參閱在[步驟 7](#step-7-permanently-delete-the-spilled-data)中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-p129">Be sure to revert the mailbox to previous configurations after you verify that the spilled data has been permanently deleted. See the details in [Step 7](#step-7-permanently-delete-the-spilled-data).</span></span>

## <a name="step-7-permanently-delete-the-spilled-data"></a><span data-ttu-id="c7dc4-233">步驟 7： 永久刪除 spilled 的資料</span><span class="sxs-lookup"><span data-stu-id="c7dc4-233">Step 7: Permanently delete the spilled data</span></span>

<span data-ttu-id="c7dc4-p130">收集並準備步驟 6 和建立及精簡尋找包含 spilled 的資料的電子郵件訊息的步驟 3 中的搜尋查詢中的信箱位置，您可以使用現在永久刪除 spilled 的資料。如先前所述，您必須獲指派信箱匯入 / 匯出角色在 Exchange Online 從中刪除郵件使用下列程序。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-p130">Using the mailbox locations that you collected and prepared in Step 6 and the search query that was created and refined in Step 3 to find email messages that contain the spilled data, you can now permanently delete the spilled data. As previously explained, you have to be assigned the Mailbox Import Export role in Exchange Online to delete messages using the following procedure.</span></span>
  
1. <span data-ttu-id="c7dc4-236">[連線到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-236">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span></span>
    
2. <span data-ttu-id="c7dc4-237">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="c7dc4-237">Run the following command:</span></span>
    
    ```
    Search-Mailbox -Identity <mailbox identity> -SearchDumpster -DeleteContent $true -SearchQuery <search query>
    ```
  
3. <span data-ttu-id="c7dc4-238">重新執行上述命令包含 spilled 的資料、 所取代的 Identity 參數值 ； 每個信箱例如：</span><span class="sxs-lookup"><span data-stu-id="c7dc4-238">Re-run the previous command for each mailbox that contains the spilled data, by replacing the value for the Identity parameter; for example:</span></span>

    ```
    Search-Mailbox -Identity sarad@contoso.onmicrosoft.com -SearchQuery <search query> -DeleteContent
    ```

    ```
    Search-Mailbox -Identity janets@contoso.onmicrosoft.com -SearchQuery <search query> -DeleteContent
    ```

   ```
   Search-Mailbox -Identity pilarp@contoso.onmicrosoft.com -SearchQuery <search query> -DeleteContent
   ```
  
<span data-ttu-id="c7dc4-239">先前所述，您也可以建立[powershell 指令碼](https://docs.microsoft.com/powershell/scripting/powershell-scripting?view=powershell-6)並執行對信箱的清單，讓指令碼會刪除每個信箱中的 spilled 的資料。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-239">As previously stated, you can also create a [powershell script](https://docs.microsoft.com/powershell/scripting/powershell-scripting?view=powershell-6) and run it against a list of mailboxes so that the script deletes the spilled data in each mailbox.</span></span>
  
## <a name="step-8-verify-provide-a-proof-of-deletion-and-audit"></a><span data-ttu-id="c7dc4-240">步驟 8： 驗證、 提供證明刪除，及稽核</span><span class="sxs-lookup"><span data-stu-id="c7dc4-240">Step 8: Verify, provide a proof of deletion, and audit</span></span>

<span data-ttu-id="c7dc4-p131">管理資料 spillage 事件的工作流程的最後一個步驟是驗證 spilled 的資料已永久移除從信箱移至 eDiscovery 案例並重新執行相同的搜尋查詢用來不刪除任何結果 ar，確認該資料傳回 e。您確認已永久移除 spilled 的資料之後，您可以將報表匯出並包括其 （搭配原始的報表） 以證明刪除。然後您可以[關閉案例](ediscovery-cases.md#optional-step-9-close-a-case)，可讓您如果未來參照它重新開啟。此外，您也可以還原信箱以其先前的狀態，刪除用來尋找 spilled 的資料，並搜尋稽核記錄的工作會管理資料 spillage 事件時執行搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-p131">The final step in the workflow to manage a data spillage incident is to verify that the spilled data was permanently removed from the mailbox by going to the eDiscovery case and re-running the same search query that was used to delete that data to confirm that no results are returned. After you confirm the spilled data has been permanently removed, you can export a report and include it (along with the original report) as a proof of deletion. Then you can [close the case](ediscovery-cases.md#optional-step-9-close-a-case), which will allow you to re-open it if you have refer to it in the future. Additionally, you can also revert mailboxes to their previous state, delete the search query used to find the spilled data, and search for auditing records of tasks performed when managing the data spillage incident.</span></span> 
  
### <a name="reverting-the-mailboxes-to-their-previous-state"></a><span data-ttu-id="c7dc4-245">回復至其先前狀態的信箱</span><span class="sxs-lookup"><span data-stu-id="c7dc4-245">Reverting the mailboxes to their previous state</span></span>

<span data-ttu-id="c7dc4-p132">如果您變更任何信箱中的設定步驟 6，以準備信箱已刪除的 spilled 的資料之前，您必須將它們還原先前的狀態。請參閱 「 步驟 5： 還原成先前狀態的信箱 」 中[可復原的項目保留的雲端架構信箱上的資料夾內刪除項目](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-5-revert-the-mailbox-to-its-previous-state)。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-p132">If you changed any mailbox configuration in Step 6 to prepare the mailboxes before the spilled data was deleted, you will need to revert them to their previous state. See "Step 5: Revert the mailbox to its previous state" in [Delete items in the Recoverable Items folder of cloud-based mailboxes on hold](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-5-revert-the-mailbox-to-its-previous-state).</span></span>
  
### <a name="deleting-the-search-query"></a><span data-ttu-id="c7dc4-248">刪除搜尋查詢</span><span class="sxs-lookup"><span data-stu-id="c7dc4-248">Deleting the search query</span></span>

<span data-ttu-id="c7dc4-249">如果您建立及使用步驟 3 中的搜尋查詢中的關鍵字包含部分或所有實際 spilled 資料，您應該刪除搜尋查詢以避免進一步資料 spillage。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-249">If the keywords in the search query that you created and used in Step 3 contains some of all of the actual spilled data, you should delete the search query to prevent further data spillage.</span></span>
  
1. <span data-ttu-id="c7dc4-250">安全性及規範中心] 中開啟 eDiscovery 案例、 移至 [**搜尋**] 頁面上，並選取適當的內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-250">In the Security & Compliance Center, open the eDiscovery case, go to the **Search** page, and select the appropriate content search.</span></span>
    
2. <span data-ttu-id="c7dc4-251">在 [彈出式] 頁面上按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-251">On the flyout page, click **Delete**.</span></span>

    ![選取搜尋] 和 [彈出式] 頁面上 [刪除](media/O365-eDiscoverySolutions-DataSpillage-DeleteSearch.png)
    
### <a name="auditing-the-data-spillage-investigation-process"></a><span data-ttu-id="c7dc4-253">稽核資料 spillage 調查程序</span><span class="sxs-lookup"><span data-stu-id="c7dc4-253">Auditing the data spillage investigation process</span></span>

<span data-ttu-id="c7dc4-p133">您可以搜尋期間將正在調查所執行的 eDiscovery 活動的 Office 365 稽核記錄。您也可以搜尋稽核記錄，以傳回在您執行**搜尋信箱 DeleteContent**命令刪除 spilled 的資料時所建立的稽核記錄。如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="c7dc4-p133">You can search the Office 365 audit log for the eDiscovery activities that were performed during the investigation. You can also search the audit log to return the audit records that were created when you ran the **Search-Mailbox -DeleteContent** command to delete the spilled data. For more information, see:</span></span>

- [<span data-ttu-id="c7dc4-257">在 Office 365 安全與規範中心搜尋稽核記錄</span><span class="sxs-lookup"><span data-stu-id="c7dc4-257">Search the audit log in the Office 365 Security &amp; Compliance Center</span></span>](search-the-audit-log-in-security-and-compliance.md)

- [<span data-ttu-id="c7dc4-258">搜尋 Office 365 稽核記錄中的 eDiscovery 活動</span><span class="sxs-lookup"><span data-stu-id="c7dc4-258">Search for eDiscovery activities in the Office 365 audit log</span></span>](search-for-ediscovery-activities-in-the-audit-log.md)

- <span data-ttu-id="c7dc4-259">請參閱"稽核活動-Exchange 管理員稽核記錄 」 一節中的[搜尋稽核記錄中的 Office 365 安全性 & 規範中心](search-the-audit-log-in-security-and-compliance.md#audited-activities)如需如何執行 Exchange Online 中的 cmdlet 與相關的稽核記錄搜尋的指引。</span><span class="sxs-lookup"><span data-stu-id="c7dc4-259">See the "Audited activities - Exchange admin audit log " section in [Search the audit log in the Office 365 Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#audited-activities) for guidance about how to search for audit records related to running cmdlets in Exchange Online.</span></span>
  

