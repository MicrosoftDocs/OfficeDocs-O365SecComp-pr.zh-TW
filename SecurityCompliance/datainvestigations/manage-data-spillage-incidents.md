---
title: 管理 Microsoft 365 中的資料外洩事件
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 本文說明使用安全性 & 合規性中心的新資料調查 （預覽） 工具，來管理資料外洩事件。
ms.openlocfilehash: 7aada296566bb5312ab56680485798323d0ab096
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34150745"
---
# <a name="manage-a-data-spillage-incident-in-microsoft-365"></a><span data-ttu-id="27613-103">管理 Microsoft 365 中的資料外洩事件</span><span class="sxs-lookup"><span data-stu-id="27613-103">Manage a data spillage incident in Microsoft 365</span></span>

<span data-ttu-id="27613-104">資料外洩時，包含、 敏感或機密惡意資訊的文件發行到未受信任的環境。</span><span class="sxs-lookup"><span data-stu-id="27613-104">Data spillage is when a document containing confidential, sensitive or malicious information is released into an untrusted environment.</span></span> <span data-ttu-id="27613-105">偵測到的資料外洩事件時，務必快速包含環境、 評估的大小和位置的外洩、 檢查使用者活動周圍，並再刪除 spilled 的資料從服務。</span><span class="sxs-lookup"><span data-stu-id="27613-105">When a data spillage incident is detected, it's important to quickly contain the environment, assess the size and locations of the spillage, examine user activities around it, and then delete the spilled data from the service.</span></span> <span data-ttu-id="27613-106">使用資料調查 （預覽） 工具，您可以跨 Office 365 中搜尋敏感、 惡意或找不到資料調查若要了解發生了什麼事，，然後採取適當的動作。</span><span class="sxs-lookup"><span data-stu-id="27613-106">Using the Data Investigations (Preview) tool, you can search for sensitive, malicious or misplaced data across Office 365, investigate to find out what happened, and then take appropriate actions.</span></span>  

## <a name="scope-of-this-article"></a><span data-ttu-id="27613-107">本文討論範圍</span><span class="sxs-lookup"><span data-stu-id="27613-107">Scope of this article</span></span>

<span data-ttu-id="27613-108">本文提供如何永久刪除項目從 Office 365 信箱時，就無法再存取或由使用者或系統管理員可復原清單中的指示。</span><span class="sxs-lookup"><span data-stu-id="27613-108">This article provides a list of instructions on how to permanently delete items from Office 365 mailboxes so they are no longer accessible or recoverable by users or admins.</span></span> 

> [!NOTE]
> <span data-ttu-id="27613-109">當您刪除項目位於 SharePoint 或 OneDrive for Business 網站時，他們會保留您刪除其原始位置的時間從 93 天。</span><span class="sxs-lookup"><span data-stu-id="27613-109">When you delete items located in a SharePoint or OneDrive for Business site, they are retained for 93 days from the time you delete them from their original location.</span></span>

## <a name="scenario"></a><span data-ttu-id="27613-110">案例</span><span class="sxs-lookup"><span data-stu-id="27613-110">Scenario</span></span>

<span data-ttu-id="27613-111">您正在其中員工不知情的情況下高度機密文件與多個人員共用透過電子郵件資料外洩事件的通知。</span><span class="sxs-lookup"><span data-stu-id="27613-111">You're informed of a data spillage incident where an employee unknowingly shared a highly-confidential document with multiple people through email.</span></span> <span data-ttu-id="27613-112">您想要快速評估者接收到此文件，同時內部和外部組織。</span><span class="sxs-lookup"><span data-stu-id="27613-112">You want to quickly assess who received this document, both inside and outside of your organization.</span></span> <span data-ttu-id="27613-113">您已調查事件之後，您想要與其他現場檢閱，並再從您的 Office 365 組織永久移除 spilled 的資料共用您所發現的錯誤。</span><span class="sxs-lookup"><span data-stu-id="27613-113">After you've investigate the incident, you plan to share your findings with other investigators to review, and then permanently remove the spilled data from your Office 365 organization.</span></span> <span data-ttu-id="27613-114">調查完成後，您想要移除所有的證據。</span><span class="sxs-lookup"><span data-stu-id="27613-114">After the investigation is complete, you want to remove all evidence.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="27613-115">當您將會永久移除您的組織內部的 spilled 的資料時，溢出組織外的任何資料不能移除與這些功能。</span><span class="sxs-lookup"><span data-stu-id="27613-115">While you'll be able to permanently remove the spilled data within your own organization, any data spilled outside your organization can't be removed with these capabilities.</span></span>

## <a name="workflow"></a><span data-ttu-id="27613-116">工作流程</span><span class="sxs-lookup"><span data-stu-id="27613-116">Workflow</span></span>

<span data-ttu-id="27613-117">以下是使用資料調查 （預覽） 來管理資料外洩事件的工作流程：</span><span class="sxs-lookup"><span data-stu-id="27613-117">Here's the workflow for using Data Investigations (Preview) to manage a data spillage incident:</span></span>

1.  <span data-ttu-id="27613-118">建立資料調查。</span><span class="sxs-lookup"><span data-stu-id="27613-118">Create a data investigation.</span></span>

2.  <span data-ttu-id="27613-119">搜尋敏感、 惡意或找不到的資料，並收集它們以作為證據。</span><span class="sxs-lookup"><span data-stu-id="27613-119">Search for sensitive, malicious, or misplaced data and collect them as evidence.</span></span>

3.  <span data-ttu-id="27613-120">檢閱並調查證據。</span><span class="sxs-lookup"><span data-stu-id="27613-120">Review and investigate the evidence.</span></span>

4.  <span data-ttu-id="27613-121">永久刪除 spilled 的資料。</span><span class="sxs-lookup"><span data-stu-id="27613-121">Permanently delete the spilled data.</span></span>

5.  <span data-ttu-id="27613-122">關閉或刪除調查。</span><span class="sxs-lookup"><span data-stu-id="27613-122">Close or delete the investigation.</span></span>


## <a name="before-you-begin"></a><span data-ttu-id="27613-123">開始之前</span><span class="sxs-lookup"><span data-stu-id="27613-123">Before you begin</span></span>

- <span data-ttu-id="27613-124">您將使用安全性 & 合規性中心中的資料調查 （預覽） 工具，來建立調查、 搜尋 spilled 的資料，請先檢閱和分析。</span><span class="sxs-lookup"><span data-stu-id="27613-124">You'll use the Data Investigations (Preview) tool in the Security & Compliance Center to create an investigation, search for the spilled data, and review and analyze it.</span></span> <span data-ttu-id="27613-125">然後您將使用安全性 & 合規性中心 PowerShell 來從 Office 365 中永久刪除 spilled 的資料。</span><span class="sxs-lookup"><span data-stu-id="27613-125">Then you'll use Security & Compliance Center PowerShell to permanently delete the spilled data from Office 365.</span></span> 

- <span data-ttu-id="27613-126">若要建立調查，您必須是中的安全性 & 合規性中心的符合性系統管理員角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="27613-126">To create an investigation, you have to be a member of the Compliance Administrator role group in the Security & Compliance Center.</span></span>

- <span data-ttu-id="27613-127">若要刪除的郵件，您必須是安全性 & 已指派搜尋及清除角色的合規性中心中的角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="27613-127">To delete messages, you have to be a member of a role group in the Security & Compliance Center that's assigned the Search and Purge role.</span></span> <span data-ttu-id="27613-128">根據預設，此角色被指派給 「 組織管理 」 角色群組。</span><span class="sxs-lookup"><span data-stu-id="27613-128">By default, this role is assigned to the Organization Management role group.</span></span> <span data-ttu-id="27613-129">如需將使用者新增至角色群組的詳細資訊，請參閱 <<c0>安全性 &amp; 合規性中心中的權限。</span><span class="sxs-lookup"><span data-stu-id="27613-129">For information about adding users to a role group, see [Permissions in the Security & Compliance Center](../permissions-in-the-security-and-compliance-center.md).</span></span> 

- <span data-ttu-id="27613-130">若要控制哪些使用者信箱和調查可搜尋的 OneDrive 帳戶，您的組織可以設定合規性界限。</span><span class="sxs-lookup"><span data-stu-id="27613-130">To control which user mailboxes and OneDrive accounts an investigator can search, your organization can set up compliance boundaries.</span></span> <span data-ttu-id="27613-131">如需詳細資訊，[設定電子文件探索調查的合規性界限](../set-up-compliance-boundaries.md)。</span><span class="sxs-lookup"><span data-stu-id="27613-131">For more information, [Set up compliance boundaries for eDiscovery investigations](../set-up-compliance-boundaries.md).</span></span> 

## <a name="step-1-create-a-data-investigation"></a><span data-ttu-id="27613-132">步驟 1： 建立資料調查</span><span class="sxs-lookup"><span data-stu-id="27613-132">Step 1: Create a data investigation</span></span>

<span data-ttu-id="27613-133">若要建立調查資料調查 （預覽） 工具中：</span><span class="sxs-lookup"><span data-stu-id="27613-133">To create an investigation in the Data Investigations (Preview) tool:</span></span>

1. <span data-ttu-id="27613-134">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="27613-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com).</span></span>
    
2. <span data-ttu-id="27613-135">使用公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="27613-135">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="27613-136">在合規性中心] 中，按一下 [**資料調查**。</span><span class="sxs-lookup"><span data-stu-id="27613-136">In the compliance center, click **Data Investigations**.</span></span>
 
4. <span data-ttu-id="27613-137">在 [**資料調查 （預覽）** ] 頁面上，按一下 [**建立新的調查**。</span><span class="sxs-lookup"><span data-stu-id="27613-137">On the **Data Investigations (Preview)** page, click **Create new investigation**.</span></span>
    
5. <span data-ttu-id="27613-138">在**新的資料調查**彈出式頁面上，提供調查 （必要） 的名稱，然後輸入選用調查數目和描述。</span><span class="sxs-lookup"><span data-stu-id="27613-138">On the **New data investigation** flyout page, give the investigation a name (required), and then type an optional investigation number and description.</span></span> <span data-ttu-id="27613-139">請注意，必須在您的組織中是唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="27613-139">Note that the name must be unique in your organization.</span></span>

6. <span data-ttu-id="27613-140">**您想要設定其他設定之後建立此調查？**，執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="27613-140">Under **Do you want to configure additional settings after creating this investigation?**, do one of the following:</span></span>

    - <span data-ttu-id="27613-141">按一下 [ **]** 來建立和調查]，並顯示 [**設定**] 頁面中新的案例。</span><span class="sxs-lookup"><span data-stu-id="27613-141">Click **Yes** to create the investigation, and display the **Settings** page in the new case.</span></span> <span data-ttu-id="27613-142">這可讓您將成員新增至調查。</span><span class="sxs-lookup"><span data-stu-id="27613-142">This allows you to add members to the investigation.</span></span>
    
    - <span data-ttu-id="27613-143">按一下 [**否]** 剛建立調查，並顯示於 [**資料調查 （預覽）** ] 頁面上的案例清單。</span><span class="sxs-lookup"><span data-stu-id="27613-143">Click **No** to just create the investigation and display it in the list of cases on the **Data Investigations (Preview)** page.</span></span> <span data-ttu-id="27613-144">如果您選擇此選項，您將會新增將用調查，以及預設搜尋和分析設定的唯一成員。</span><span class="sxs-lookup"><span data-stu-id="27613-144">If you choose this option, you will be added as the only member of the investigation and the default search and analytics settings will be used.</span></span> <span data-ttu-id="27613-145">您可以將成員新增或變更設定之後建立調查的任何時間。</span><span class="sxs-lookup"><span data-stu-id="27613-145">You can add members or change settings any time after the investigation is created.</span></span>

7. <span data-ttu-id="27613-146">按一下 [**儲存**] 以建立調查。</span><span class="sxs-lookup"><span data-stu-id="27613-146">Click **Save** to create the investigation.</span></span>

    <span data-ttu-id="27613-147">新調查會顯示在**資料調查 （預覽）** 頁面上的清單。</span><span class="sxs-lookup"><span data-stu-id="27613-147">The new investigation is displayed in the list on the **Data Investigations (Preview)** page.</span></span> 

8. <span data-ttu-id="27613-148">若要開啟 [調查，請按一下 [調查的名稱。</span><span class="sxs-lookup"><span data-stu-id="27613-148">To open an investigation, click the name of the investigation.</span></span> 

    <span data-ttu-id="27613-149">針對調查 [**首頁**] 索引標籤會顯示。</span><span class="sxs-lookup"><span data-stu-id="27613-149">The **Home** tab for the investigation is displayed.</span></span> 

> [!TIP]
> <span data-ttu-id="27613-150">請考慮建立調查的命名慣例，並提供最多為讓您可以找出並參照在未來必要時，您可以在名稱和描述的資訊。</span><span class="sxs-lookup"><span data-stu-id="27613-150">Consider establishing a naming convention for investigations and provide as much information as you can in the name and description so you can locate and refer to in the future if necessary.</span></span>
 
## <a name="step-2-search-for-the-spilled-data"></a><span data-ttu-id="27613-151">步驟 2： 搜尋 spilled 資料</span><span class="sxs-lookup"><span data-stu-id="27613-151">Step 2: Search for the spilled data</span></span> 
 
<span data-ttu-id="27613-152">如果您知道想要搜尋溢出資料的使用者，您可以將其新增為調查對應及其資料來源，並快速搜尋其信箱和 OneDrive 帳戶感興趣的人員。</span><span class="sxs-lookup"><span data-stu-id="27613-152">If you know which users you want to search for spilled data, you can add them as people of interest to map their data sources to the investigation and quickly search their mailbox and OneDrive account.</span></span> <span data-ttu-id="27613-153">若要新增調查感興趣的人員，按一下 [**感興趣的人員**，，，然後按一下 [**新增人員感興趣**。</span><span class="sxs-lookup"><span data-stu-id="27613-153">To add people of interest to the investigation, click **People of interest**, and then click **Add people of interest**.</span></span> <span data-ttu-id="27613-154">如需詳細資訊，請參閱 <<c0>管理人員感興趣。</span><span class="sxs-lookup"><span data-stu-id="27613-154">For more information, see [Manage people of interest](manage-people-of-interest.md).</span></span>

<span data-ttu-id="27613-155">在 [**搜尋**] 索引標籤中，您可以建立搜尋來尋找 spilled 的資料。</span><span class="sxs-lookup"><span data-stu-id="27613-155">On the **Searches** tab, you can create searches to find the spilled data.</span></span> <span data-ttu-id="27613-156">您會使用您用來尋找要刪除這些相同的郵件，在[步驟 4](#step-4-delete-the-spilled-data)中的 spilled 的資料的相同搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="27613-156">You will use the same search query that you used to find the spilled data to delete those same messages in [Step 4](#step-4-delete-the-spilled-data).</span></span> <span data-ttu-id="27613-157">如需建立搜尋的詳細資訊，請參閱 <<c0>搜尋調查中的資料。</span><span class="sxs-lookup"><span data-stu-id="27613-157">For more information about creating searches, see [Search for data in an investigation](search-for-data.md).</span></span>

<span data-ttu-id="27613-158">執行搜尋之後，您可以預覽搜尋結果和檢視搜尋統計資料，來評估您的搜尋查詢的有效性的範例。</span><span class="sxs-lookup"><span data-stu-id="27613-158">After you run the search, you can preview samples of search results and view search statistics to evaluate the effectiveness of your search query.</span></span> <span data-ttu-id="27613-159">一旦您找出您想要從 Office 365 中刪除的項目，您可以**證據**] 索引標籤，然後建立辨識項集合並增加搜尋結果包含這些項目。</span><span class="sxs-lookup"><span data-stu-id="27613-159">Once you identify the items that you want to delete from Office 365, you can click the **Evidence** tab, and then create an evidence set and add search results that contain those items.</span></span> 

<span data-ttu-id="27613-160">若要這麼做，請按一下您想要調查的搜尋。</span><span class="sxs-lookup"><span data-stu-id="27613-160">To do this, click the search that you want to investigate.</span></span> <span data-ttu-id="27613-161">在彈出式頁面上，按一下 [**新增結果辨識項**，並遵循指示。</span><span class="sxs-lookup"><span data-stu-id="27613-161">On the flyout page, click **Add results to evidence** and follow the instructions.</span></span> <span data-ttu-id="27613-162">然後辨識項，可以檢閱個別文件、 調查誰有權存取文件，並匯出文件。</span><span class="sxs-lookup"><span data-stu-id="27613-162">Then in the evidence, you can review individual documents, investigate who had access to documents, and export the documents.</span></span> <span data-ttu-id="27613-163">只刪除而不是檢閱這些文件，請移至[步驟 4](#step-4-delete-the-spilled-data)。</span><span class="sxs-lookup"><span data-stu-id="27613-163">To simply delete the documents instead of reviewing them, go to [Step 4](#step-4-delete-the-spilled-data).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="27613-164">您在搜尋查詢中使用關鍵字可能包含您要搜尋的實際 spilled 的資料。</span><span class="sxs-lookup"><span data-stu-id="27613-164">The keywords that you use in the search query may contain the actual spilled data that you're searching for.</span></span> <span data-ttu-id="27613-165">例如，如果您搜尋包含社會安全號碼的文件，作為在搜尋查詢的關鍵字，您必須刪除之後，避免發生外洩的查詢。</span><span class="sxs-lookup"><span data-stu-id="27613-165">For example, if you search for documents containing a social security number and you use it as a keyword in the search query, you must delete the query afterwards to avoid further spillage.</span></span> <span data-ttu-id="27613-166">您可以刪除搜尋，或刪除整個調查在[步驟 5](#step-5-close-or-delete-the-investigation)。</span><span class="sxs-lookup"><span data-stu-id="27613-166">You can delete the search or delete the entire investigation in [Step 5](#step-5-close-or-delete-the-investigation).</span></span> 

## <a name="step-3-review-and-investigate"></a><span data-ttu-id="27613-167">步驟 3： 檢閱和調查</span><span class="sxs-lookup"><span data-stu-id="27613-167">Step 3: Review and investigate</span></span> 

<span data-ttu-id="27613-168">在調查，移至**證據**] 索引標籤上，按一下 [您在上一個步驟中建立辨識項集合。</span><span class="sxs-lookup"><span data-stu-id="27613-168">In the investigation, go to **Evidence** tab and click on the evidence set that you created in the previous step.</span></span> <span data-ttu-id="27613-169">完成處理工作，並在搜尋結果會新增至辨識項之後，您可以檢閱其原生格式、 文字格式或附近原生格式中的個別文件。</span><span class="sxs-lookup"><span data-stu-id="27613-169">After the processing job is completed and the search results are added to the evidence, you can review individual documents in their native format, text format, or a near-native format.</span></span> <span data-ttu-id="27613-170">您可以建立額外的查詢，以縮小範圍清單中的文件和標記文件，以指出從您調查所發現的錯誤。</span><span class="sxs-lookup"><span data-stu-id="27613-170">You can create additional queries to narrow the list of documents, and tag documents to indicate findings from your investigation.</span></span> <span data-ttu-id="27613-171">如需詳細資訊，請參閱[中的辨識項的檢閱資料](review-data-in-evidence.md)</span><span class="sxs-lookup"><span data-stu-id="27613-171">For more information, see [Review data in evidence](review-data-in-evidence.md)</span></span>

<span data-ttu-id="27613-172">群組文件，並取得更多協助您檢閱，按一下 [**管理辨識項**]。</span><span class="sxs-lookup"><span data-stu-id="27613-172">To group documents and get more assistance for your review, click **Manage evidence**.</span></span> <span data-ttu-id="27613-173">在 [**分析**] 磚中，按一下 [**分析**]。</span><span class="sxs-lookup"><span data-stu-id="27613-173">In the **Analytics** tile, click **Analyze**.</span></span> <span data-ttu-id="27613-174">這將會執行進階的分析，例如重複資料偵測、 電子郵件執行緒，以及佈景主題分析。</span><span class="sxs-lookup"><span data-stu-id="27613-174">This will run advanced analytics such as duplicate detection, email threading, and theme analysis.</span></span> <span data-ttu-id="27613-175">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="27613-175">For more information, see:</span></span>

- [<span data-ttu-id="27613-176">執行分析以更快速地調查</span><span class="sxs-lookup"><span data-stu-id="27613-176">Run analytics to investigate faster</span></span>](run-analytics-to-investigate-faster.md)
- [<span data-ttu-id="27613-177">近似重複項偵測</span><span class="sxs-lookup"><span data-stu-id="27613-177">Near duplicate detection</span></span>](near-duplicates.md)
- [<span data-ttu-id="27613-178">電子郵件執行緒</span><span class="sxs-lookup"><span data-stu-id="27613-178">Email threading</span></span>](email-threading.md)
- [<span data-ttu-id="27613-179">佈景主題</span><span class="sxs-lookup"><span data-stu-id="27613-179">Themes</span></span>](themes.md)

<span data-ttu-id="27613-180">若要決定哪些使用者參與資料外洩，您可以在辨識項集合中建立新的查詢，然後使用 [寄件者/作者和收件者條件。</span><span class="sxs-lookup"><span data-stu-id="27613-180">To determine which users are involved in the data spillage, you can create a new query in the evidence set and then use the Sender/Author and Recipients conditions.</span></span> <span data-ttu-id="27613-181">這會建立一份所有寄件者、 收件者，以及收集已新增至辨識項的資料中找到的作者。</span><span class="sxs-lookup"><span data-stu-id="27613-181">This will create a list of all senders, recipients, and authors found in collected data that was added to the evidence.</span></span> <span data-ttu-id="27613-182">請務必檢查清單，以判斷是否有任何外部使用者。</span><span class="sxs-lookup"><span data-stu-id="27613-182">Be sure to examine the list to determine if there are any external users.</span></span> <span data-ttu-id="27613-183">如需使用條件縮小搜尋結果的詳細資訊，請參閱 <<c0>搜尋條件。</span><span class="sxs-lookup"><span data-stu-id="27613-183">For more information about using conditions to narrow search results, see [Search conditions](../keyword-queries-and-search-conditions.md#search-conditions).</span></span>

## <a name="step-4-delete-the-spilled-data"></a><span data-ttu-id="27613-184">步驟 4： 刪除 spilled 的資料</span><span class="sxs-lookup"><span data-stu-id="27613-184">Step 4: Delete the spilled data</span></span>

### <a name="deleting-mailbox-items"></a><span data-ttu-id="27613-185">刪除信箱項目</span><span class="sxs-lookup"><span data-stu-id="27613-185">Deleting mailbox items</span></span>

<span data-ttu-id="27613-186">檢閱並驗證搜尋結果包含只必須刪除電子郵件之後，您可以永久刪除它們執行**New-compliancesearchaction-清除-PurgeType HardDelete**命令中安全性 & 合規性中心 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="27613-186">After you review and validate that the search results contain only the email messages that must be deleted, you can permanently delete them by running the **New-ComplianceSearchAction -Purge -PurgeType HardDelete** command in Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="27613-187">如需相關指示，請參閱[搜尋並刪除電子郵件訊息](../search-for-and-delete-messages-in-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="27613-187">For instructions, see [Search for and delete email messages](../search-for-and-delete-messages-in-your-organization.md).</span></span> 

<span data-ttu-id="27613-188">如果您的組織中的信箱啟用單一項目復原，則永久刪除的項目會保留在使用者的 [可復原的項目] 資料夾中 （以及由系統管理員可以存取） 直到已刪除的項目保留期間結束 （預設值是 14 天）。</span><span class="sxs-lookup"><span data-stu-id="27613-188">If single item recovery is enabled for mailboxes in your organization, permanently deleted items will be retained in the user's Recoverable items folder (and accessible by admins) until the deleted item retention period ends (the default is 14 days).</span></span> <span data-ttu-id="27613-189">此外，如果包含溢出資料的任何信箱處於合法持有或指派到保留原則後，清除的郵件仍會保留在 [可復原的項目] 資料夾中，項目保留期間到期之前。</span><span class="sxs-lookup"><span data-stu-id="27613-189">Additionally, if any mailbox that contains spilled data is on a legal hold or assigned to a retention policy, purged messages will be retained in the Recoverable items folder until the hold duration for the item expires.</span></span> <span data-ttu-id="27613-190">若要實刪除的郵件立即，您必須執行加入工作。</span><span class="sxs-lookup"><span data-stu-id="27613-190">To hard delete messages immediately, you need to perform addition tasks.</span></span> <span data-ttu-id="27613-191">如需相關指示，請參閱 <<c0>可復原的項目保留的雲端架構信箱上的資料夾內刪除項目。</span><span class="sxs-lookup"><span data-stu-id="27613-191">For instructions, see [Delete items in the Recoverable Items folder of cloud-based mailboxes on hold](../delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md).</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="27613-192">移除保留或保留原則之前，先檢查與您的記錄管理或法務部門。</span><span class="sxs-lookup"><span data-stu-id="27613-192">Check with your records management or legal departments before removing a hold or retention policy.</span></span> <span data-ttu-id="27613-193">您的組織可能會有一個原則來定義是否要保留的信箱上或資料外洩事件會優先採用。</span><span class="sxs-lookup"><span data-stu-id="27613-193">Your organization may have a policy that defines whether a mailbox on hold or a data spillage incident takes priority.</span></span> 

### <a name="deleting-site-items"></a><span data-ttu-id="27613-194">刪除站台的項目</span><span class="sxs-lookup"><span data-stu-id="27613-194">Deleting site items</span></span>

<span data-ttu-id="27613-195">若要永久刪除文件從 SharePoint 網站或 OneDrive 帳戶中，您必須刪除文件，然後您必須從網站資源回收筒刪除再刪除網站集合資源回收筒。</span><span class="sxs-lookup"><span data-stu-id="27613-195">To permanently delete a document from a SharePoint site or OneDrive account, you have to delete the document and then you have to delete from the site Recycle Bin and then delete it from the site collection Recycle Bin.</span></span> <span data-ttu-id="27613-196">如需詳細資訊，請參閱[刪除文件中的 SharePoint 和 OneDrive](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#deleting-documents-in-sharepoint-online-and-onedrive-for-business)。</span><span class="sxs-lookup"><span data-stu-id="27613-196">For more information, see [Delete documents in SharePoint and OneDrive](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#deleting-documents-in-sharepoint-online-and-onedrive-for-business).</span></span>

<span data-ttu-id="27613-197">或者，您可以刪除可能包含溢出資料整個網站集合。</span><span class="sxs-lookup"><span data-stu-id="27613-197">Alternatively, you can delete an entire site collection that might contained spilled data.</span></span> <span data-ttu-id="27613-198">如需相關指示，請參閱[刪除網站集合](https://docs.microsoft.com/sharepoint/delete-site-collection)。</span><span class="sxs-lookup"><span data-stu-id="27613-198">For instructions, see [Delete a site collection](https://docs.microsoft.com/sharepoint/delete-site-collection).</span></span>

## <a name="step-5-close-or-delete-the-investigation"></a><span data-ttu-id="27613-199">步驟 5： 關閉或刪除調查</span><span class="sxs-lookup"><span data-stu-id="27613-199">Step 5: Close or delete the investigation</span></span>

<span data-ttu-id="27613-200">即時服務中刪除文件中的來源的內容位置 （信箱或網站） 之後，您仍必須新增至您調查一部分的辨識項這些文件的複本。</span><span class="sxs-lookup"><span data-stu-id="27613-200">After you delete documents in the source content locations (mailboxes or sites) in the live service, you will still have copies of these documents that you added to evidence as part of your investigation.</span></span> <span data-ttu-id="27613-201">若要避免進一步的資料外洩，您應該考慮刪除調查本身擷取。</span><span class="sxs-lookup"><span data-stu-id="27613-201">To avoid further data spillage, you should consider deleting the investigation itself.</span></span>

<span data-ttu-id="27613-202">若要刪除調查：</span><span class="sxs-lookup"><span data-stu-id="27613-202">To delete an investigation:</span></span>

1. <span data-ttu-id="27613-203">在 [**設定**] 索引標籤中，按一下 [**調查的資訊**。</span><span class="sxs-lookup"><span data-stu-id="27613-203">On the **Settings** tab, click **Investigation information**.</span></span>

2. <span data-ttu-id="27613-204">按一下 [**刪除的調查**。</span><span class="sxs-lookup"><span data-stu-id="27613-204">Click  **Delete investigation**.</span></span> 

<span data-ttu-id="27613-205">如果您不需要刪除調查，或您想要儲存您在調查期間收集到的資訊，您可以按一下 [**關閉案例**。</span><span class="sxs-lookup"><span data-stu-id="27613-205">If you don't need to delete the investigation or if you want to save the information that you collected during the investigation, you can click **Close case**.</span></span> <span data-ttu-id="27613-206">然後日後，您可以重新開啟關閉的調查。</span><span class="sxs-lookup"><span data-stu-id="27613-206">Then at a later date, you can re-open closed investigations.</span></span>
