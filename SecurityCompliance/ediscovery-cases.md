---
title: Office 365 安全性的 eDiscovery 案例&amp;規範中心
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 8dd335ab-29d0-41c3-8dd8-9f7c7481e60c
description: 使用 Office 365 安全性&amp;規範中心來建立及管理組織中的 eDiscovery 案例。您可以將成員指派給大小寫、 放置內容保留執行內容 Searchs 位置相關聯情況下，並匯出搜尋結果。您也可以準備進一步分析進階 ediscovery 案例的資料。
ms.openlocfilehash: 1265aa5f4d08f5bbbff4c52a50dd2fd8eacffd21
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296846"
---
# <a name="ediscovery-cases-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="7cea3-105">Office 365 安全性的 eDiscovery 案例&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="7cea3-105">eDiscovery cases in the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="7cea3-p102">您可以使用 eDiscovery 案例中 Office 365 安全性&amp;規範中心控制人員可以建立、 存取及管理組織中的 eDiscovery 案例。如果貴組織的 Office 365 E5 訂閱，也可以使用 eDiscovery 案例分析使用 Office 365 進階 eDiscovery 搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p102">You can use eDiscovery cases in the Office 365 Security &amp; Compliance Center to control who can create, access, and manage eDiscovery cases in your organization. If your organization has an Office 365 E5 subscription, you can also use eDiscovery cases to analyze search results by using Office 365 Advanced eDiscovery.</span></span>
  
<span data-ttu-id="7cea3-p103">EDiscovery 案例可讓您將成員新增至案例、 控制哪些類型的特定案例的成員可以執行、 置於保留的內容位置相關法律案例，並建立多個內容搜尋與單一案例的關聯的動作。您也可以與案例相關聯的任何內容搜尋結果匯出或準備分析進階在 eDiscovery 中搜尋結果。eDiscovery 案例是很好的方式來限制在組織中有存取特定的法律案例內容的搜尋及搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p103">An eDiscovery case allows you to add members to a case, control what types of actions that specific case members can perform, place a hold on content locations relevant to a legal case, and associate multiple Content Searches with a single case. You can also export the results of any Content Search that is associated with a case or prepare search results for analysis in Advanced eDiscovery. eDiscovery cases are a good way to limit who has access to Content Searches and search results for a specific legal case in your organization.</span></span>
  
<span data-ttu-id="7cea3-111">使用下列工作流程設定和安全性中使用 eDiscovery 案例&amp;規範中心] 及 [進階 eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="7cea3-111">Use the following workflow to set up and use eDiscovery cases in the Security &amp; Compliance Center and Advanced eDiscovery.</span></span>

[<span data-ttu-id="7cea3-112">步驟 1：將 eDiscovery 權限指派給潛在的案例成員</span><span class="sxs-lookup"><span data-stu-id="7cea3-112">Step 1: Assign eDiscovery permissions to potential case members</span></span>](#step-1-assign-ediscovery-permissions-to-potential-case-members)

[<span data-ttu-id="7cea3-113">步驟 2： 建立新的案例</span><span class="sxs-lookup"><span data-stu-id="7cea3-113">Step 2: Create a new case</span></span>](#step-2-create-a-new-case)

[<span data-ttu-id="7cea3-114">步驟 3： 將成員新增至案例</span><span class="sxs-lookup"><span data-stu-id="7cea3-114">Step 3: Add members to a case</span></span>](#step-3-add-members-to-a-case)

[<span data-ttu-id="7cea3-115">步驟 4： 就地保留上的內容位置</span><span class="sxs-lookup"><span data-stu-id="7cea3-115">Step 4: Place content locations on hold</span></span>](#step-4-place-content-locations-on-hold)

[<span data-ttu-id="7cea3-116">步驟 5： 建立並執行與案例相關聯之內容搜尋</span><span class="sxs-lookup"><span data-stu-id="7cea3-116">Step 5: Create and run a Content Search associated with a case</span></span>](#step-5-create-and-run-a-content-search-associated-with-a-case)

[<span data-ttu-id="7cea3-117">步驟 6： 匯出與案例相關聯之內容搜尋的結果</span><span class="sxs-lookup"><span data-stu-id="7cea3-117">Step 6: Export the results of a Content Search associated with a case</span></span>](#step-6-export-the-results-of-a-content-search-associated-with-a-case)

[<span data-ttu-id="7cea3-118">步驟 7： 準備搜尋結果進階 ediscovery （英文）</span><span class="sxs-lookup"><span data-stu-id="7cea3-118">Step 7: Prepare search results for Advanced eDiscovery</span></span>](#step-7-prepare-search-results-for-advanced-ediscovery)

<span data-ttu-id="7cea3-119">[步驟 8： 移至 [進階 ediscovery 案例](#step-8-go-to-the-case-in-advanced-ediscovery)</span><span class="sxs-lookup"><span data-stu-id="7cea3-119">[Step 8: Go to the case in Advanced eDiscovery](#step-8-go-to-the-case-in-advanced-ediscovery)</span></span>

[<span data-ttu-id="7cea3-120">（選用）步驟 9： 關閉案例</span><span class="sxs-lookup"><span data-stu-id="7cea3-120">(Optional) Step 9: Close a case</span></span>](#optional-step-9-close-a-case)

[<span data-ttu-id="7cea3-121">（選用）步驟 10： 重新開啟關閉的案例</span><span class="sxs-lookup"><span data-stu-id="7cea3-121">(Optional) Step 10: Re-open a closed case</span></span>](#optional-step-10-re-open-a-closed-case)

[<span data-ttu-id="7cea3-122">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="7cea3-122">More information</span></span>](#more-information)
  
## <a name="step-1-assign-ediscovery-permissions-to-potential-case-members"></a><span data-ttu-id="7cea3-123">步驟 1：將 eDiscovery 權限指派給潛在的案例成員</span><span class="sxs-lookup"><span data-stu-id="7cea3-123">Step 1: Assign eDiscovery permissions to potential case members</span></span>

<span data-ttu-id="7cea3-p104">第一個步驟是將適當的 eDiscovery 相關權限指派給人員讓您可以將其新增至 eDiscovery 案例在步驟 2。您必須是 「 組織管理角色群組的成員 （或要指派的角色管理角色） Office 365 安全性&amp;規範中心指派 eDiscovery 權限。下列清單說明 eDiscovery 相關的角色群組安全性&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p104">The first step is to assign the appropriate eDiscovery-related permissions to people so you can add them to an eDiscovery case in Step 2. You have to be a member of the Organization Management role group (or be assigned the Role Management role) in the Office 365 Security &amp; Compliance Center to assign eDiscovery permissions. The following list describes the eDiscovery-related role groups in the Security &amp; Compliance Center.</span></span> 
  
- <span data-ttu-id="7cea3-p105">**檢閱**此角色群組具有最嚴格的 eDiscovery 相關權限。此角色群組的主要目的是要允許成員檢視及存取 case Office 365 進階在 eDiscovery 中的資料。此群組的成員只能看到並在 [安全性] 中開啟 [ **eDiscovery** ] 頁面上的案例清單&amp;他們是成員的規範中心。使用者存取的安全性 & 規範中心的案例之後，他們可以按一下 [**進階 ediscovery 參數**來存取及分析中進階 eDiscovery 案例的資料。他們無法建立的情況下，將成員新增至案例、 建立保留、 建立搜尋、 預覽搜尋結果、 匯出搜尋結果或準備進階 eDiscovery 的結果。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p105">**Reviewer** - This role group has the most restrictive eDiscovery-related permissions. The primary purpose of this role group is to allow members to view and access case data in Office 365 Advanced eDiscovery. Members of this group can only see and open the list of the cases on the **eDiscovery** page in the Security &amp; Compliance Center that they are members of. After the user accesses a case in the Security & Compliance Center, they can click **Switch to Advanced eDiscovery** to access and analyze the case data in Advanced eDiscovery. They can't create cases, add members to a case, create holds, create searches, preview search results, export search results, or prepare results for Advanced eDiscovery.</span></span> 
    
- <span data-ttu-id="7cea3-p106">**eDiscovery 管理員**此角色群組的成員可以建立與管理 eDiscovery 案例。他們可以新增和移除成員、 放置的內容上的位置保留、 建立及編輯與案例相關聯的內容搜尋]、 [匯出搜尋結果的內容，並準備分析進階在 eDiscovery 中搜尋結果。有兩個此角色群組中的子群組。這些子群組之間的差異根據範圍。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p106">**eDiscovery Manager** - Members of this role group can create and manage eDiscovery cases. They can add and remove members, place content locations on hold, create and edit Content Searches associated with a case, export the results of a Content Search, and prepare search results for analysis in Advanced eDiscovery. There are two sub-groups in this role group. The difference between these subgroups is based on scope.</span></span>
    
  - <span data-ttu-id="7cea3-p107">**eDiscovery 管理員**-可檢視與管理 eDiscovery 案例所建立或成員。如果另一個 eDiscovery 管理員會建立案例，但不會將第二個 eDiscovery 管理員新增為該案例的成員，第二個 eDiscovery 管理員將無法檢視或在 [安全性] 中開啟 [ **eDiscovery** ] 頁面上的大小寫&amp;規範中心。eDiscovery 管理員也可以存取他們的情況下執行分析工作的進階 ediscovery。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p107">**eDiscovery Manager** - Can view and manage the eDiscovery cases they create or are a member of. If another eDiscovery Manager creates a case but doesn't add a second eDiscovery Manager as a member of that case, the second eDiscovery Manager won't be able to view or open the case on the **eDiscovery** page in the Security &amp; Compliance Center. eDiscovery Managers can also access their cases in Advanced eDiscovery to perform analysis tasks.</span></span> 
    
  - <span data-ttu-id="7cea3-p108">**eDiscovery 管理員**-可以執行 eDiscovery 管理員可以執行的所有管理工作。此外，eDiscovery 管理員可以：</span><span class="sxs-lookup"><span data-stu-id="7cea3-p108">**eDiscovery Administrator** - Can perform all case management tasks that an eDiscovery Manager can do. Additionally, an eDiscovery Administrator can:</span></span>
    
    - <span data-ttu-id="7cea3-141">在 [ **eDiscovery** ] 頁面上檢視所列的所有案例。</span><span class="sxs-lookup"><span data-stu-id="7cea3-141">View all cases that are listed on the **eDiscovery** page.</span></span> 
    
    - <span data-ttu-id="7cea3-142">管理組織中的任何案例之後他們將自己新增為大小寫的成員。</span><span class="sxs-lookup"><span data-stu-id="7cea3-142">Manage any case in the organization after they add themself as a member of the case.</span></span>
    
    - <span data-ttu-id="7cea3-143">存取 case 進階 eDiscovery 針對在組織中任何案例中的資料。</span><span class="sxs-lookup"><span data-stu-id="7cea3-143">Access case data in Advanced eDiscovery for any case in the organization.</span></span>
    
    <span data-ttu-id="7cea3-144">請參閱[More information](#more-information)一節以了解為何您可能希望組織中有 eDiscovery 系統管理員的原因。</span><span class="sxs-lookup"><span data-stu-id="7cea3-144">See the [More information](#more-information) section for reasons why you may want an eDiscovery Administrator in your organization.</span></span> 
    
> [!IMPORTANT]
> <span data-ttu-id="7cea3-145">如果使用者不是其中一個這些 eDiscovery 相關的角色群組的成員或不是已指派的檢閱者 」 角色的角色群組的成員，您無法將其新增為 eDiscovery 案例的成員。</span><span class="sxs-lookup"><span data-stu-id="7cea3-145">If a person isn't a member of one of these eDiscovery-related role groups, or isn't a member of a role group that's assigned the Reviewer role, you can't add them as a member of an eDiscovery case.</span></span> 

<span data-ttu-id="7cea3-146">如需 eDiscovery 權限的詳細資訊，請參閱[指派 Office 365 安全性 eDiscovery 權限&amp;規範中心](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="7cea3-146">For more information about eDiscovery permissions, see [Assign eDiscovery permissions in the Office 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
  
 <span data-ttu-id="7cea3-147">**若要指派 eDiscovery 權限：**</span><span class="sxs-lookup"><span data-stu-id="7cea3-147">**To assign eDiscovery permissions:**</span></span>
  
1. <span data-ttu-id="7cea3-148">移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="7cea3-148">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="7cea3-149">使用公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="7cea3-149">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="7cea3-150">安全性&amp;規範中心 [**權限**，然後再執行作業根據想要指定 eDiscovery 權限的下列其中之一。</span><span class="sxs-lookup"><span data-stu-id="7cea3-150">In the Security &amp; Compliance Center, click **Permissions**, and then do one of the following based on the eDiscovery permissions that you want to assign.</span></span>
    
    - <span data-ttu-id="7cea3-p109">若要指定檢閱者權限，選取 「**檢閱者**」 角色群組，然後按一下 [**成員**] 旁的 [**編輯**。按一下 [**選擇成員**、 按一下 [**編輯**]、 按一下 [![新增圖示](media/ITPro-EAC-AddIcon.gif)**新增**]，選取您要新增至 「 檢閱者 」 角色群組、 使用者，然後按一下 [**新增]**。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p109">To assign Reviewer permissions, select the **Reviewer** role group, and then next to **Members**, click **Edit**. Click **Choose members**, click **Edit**, click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **Add**, select the user that you want to add to the Reviewer role group, and then click **Add**.</span></span>
    
    - <span data-ttu-id="7cea3-p110">若要指派 eDiscovery 管理員權限，選取**eDiscovery 管理員**角色群組中，，然後按一下 [ **eDiscovery 管理員**旁的 [**編輯**。按一下 [**選擇 eDiscovery 管理員**、 按一下 [**編輯**]，按一下 [![新增圖示](media/ITPro-EAC-AddIcon.gif)\* \* 新增 \* \*、 選取您要新增 eDiscovery 管理員] 中，為該使用者，然後按一下 [**新增]**。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p110">To assign eDiscovery Manager permissions, select the **eDiscovery Manager** role group, and then next to **eDiscovery Manager**, click **Edit**. Click **Choose eDiscovery Manager**, click **Edit**, click ![Add Icon](media/ITPro-EAC-AddIcon.gif) \*\* Add \*\*, select the user that you want to add as an eDiscovery Manager, and then click **Add**.</span></span>
    
    - <span data-ttu-id="7cea3-p111">若要指派 eDiscovery 管理員權限，請選取**eDiscovery 管理員**角色群組，然後按一下 [ **eDiscovery 管理員**旁的 [**編輯**。按一下 [**選擇 eDiscovery 管理員**、 按一下 [**編輯**]，按一下 [![新增圖示](media/ITPro-EAC-AddIcon.gif)**新增**]，選取您要新增為 eDiscovery 管理員的使用者，然後按一下 [**新增]**。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p111">To assign eDiscovery Administrator permissions, select the **eDiscovery Manager** role group, and then next to **eDiscovery Administrator**, click **Edit**. Click **Choose eDiscovery Administrator**, click **Edit**, click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **Add**, select the user that you want to add as an eDiscovery Administrator, and then click **Add**.</span></span>
    
4. <span data-ttu-id="7cea3-157">您已新增的所有使用者之後，請按一下 [**完成**]、 按一下 [**儲存**] 以將所做的變更儲存到角色群組中，然後按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="7cea3-157">After you've added all the users, click **Done**, click **Save** to save the changes to the role group, and then click **Close**.</span></span>

## <a name="step-2-create-a-new-case"></a><span data-ttu-id="7cea3-158">步驟 2： 建立新的案例</span><span class="sxs-lookup"><span data-stu-id="7cea3-158">Step 2: Create a new case</span></span>

<span data-ttu-id="7cea3-p112">下一步是建立新的 eDiscovery 案例。您必須是要建立 eDiscovery 案例的 eDiscovery 管理員角色群組的成員。如先前清楚，您在 [安全性] 建立新案例之後&amp;規範中心、 您 （和其他案例的成員） 將能夠存取進階 eDiscovery 如果您組織中的相同案例具有 Office 365 E5 訂閱。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p112">The next step is to create a new eDiscovery case. You must be a member of the eDiscovery Managers role group to create eDiscovery cases. As previously explained, after you create a new case in the Security &amp; Compliance Center, you (and other case members) will be able to access that same case in Advanced eDiscovery if you're organization has an Office 365 E5 subscription.</span></span>
  
1. <span data-ttu-id="7cea3-162">移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="7cea3-162">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="7cea3-163">使用公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="7cea3-163">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="7cea3-164">安全性&amp;規範中心，按一下 [**搜尋&amp;調查** \> **eDiscovery**，然後按一下 [![新增圖示](media/ITPro-EAC-AddIcon.gif)**建立案例**。</span><span class="sxs-lookup"><span data-stu-id="7cea3-164">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery**, and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **Create a case**.</span></span>
    
4. <span data-ttu-id="7cea3-p113">在 [**新案例**] 頁面提供大小寫的名稱、 輸入選用描述，和 [**儲存**。請注意大小寫的名稱必須是唯一您組織中。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p113">On the **New Case** page, give the case a name, type an optional description, and then click **Save**. Note that the case name must be unique in your organization.</span></span>
    
    ![建立新案例](media/7f78f83b-1525-4c77-9888-4b6bda1e148d.png)
  
    <span data-ttu-id="7cea3-p114">新的案例會顯示在 [ **eDiscovery** ] 頁面上的情況下的清單中。您可以將游標滑鼠停留在來顯示關於情況下，包括] （**使用中**或**已關閉**） 的大小寫的狀態資訊的案例名稱的附註的 （也就在上一個步驟中建立） 的情況下，描述與大小寫當上次變更及誰已變更它。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p114">The new case is displayed in the list of cases on the **eDiscovery** page. Note that you can hover the cursor over a case name to display information about the case, including the status of the case ( **Active** or **Closed**), the description of the case (that was created in the previous step), and when the case was changed last and who changed it.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="7cea3-p115">建立新案例之後，您可以隨時命名。只要按一下在 [ **eDiscovery** ] 頁面的大小寫的名稱。在 [**管理此例中**彈出式] 頁面變更 [**名稱**] 方塊中顯示的名稱並儲存變更。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p115">After you create a new case, you can rename it anytime. Just click the name of the case on the **eDiscovery** page. On the **Manage this case** flyout page, change the name displayed in the box under **Name**, and then save the change.</span></span> 
  
## <a name="step-3-add-members-to-a-case"></a><span data-ttu-id="7cea3-173">步驟 3： 將成員新增至案例</span><span class="sxs-lookup"><span data-stu-id="7cea3-173">Step 3: Add members to a case</span></span>

<span data-ttu-id="7cea3-p116">建立新案例之後下, 一步是將成員新增至大小寫。如先前所述的僅限成員的檢閱者的使用者或 eDiscovery 管理員角色群組可新增為的大小寫的成員。請注意 eDiscovery 管理員建立案例會自動新增為成員。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p116">After you create a new case, the next step is to add members to the case. As previous explained, only users who are members of the Reviewer or eDiscovery Manager role groups can be added as members of the case. Note that the eDiscovery Manager who created the case is automatically added as a member.</span></span>
  
1. <span data-ttu-id="7cea3-177">在安全性與合規性中心，按一下 [搜尋和調查]\*\*\*\* \> [電子文件探索]\*\*\*\*，來顯示貴組織中的案例清單。</span><span class="sxs-lookup"><span data-stu-id="7cea3-177">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="7cea3-178">按一下您想要將成員新增至的大小寫的名稱。</span><span class="sxs-lookup"><span data-stu-id="7cea3-178">Click the name of the case that you want to add members to.</span></span>
    
    <span data-ttu-id="7cea3-179">會顯示 [**管理此例中**彈出式] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7cea3-179">The **Manage this case** flyout page is displayed.</span></span> 
    
    ![管理案例彈出式] 頁面](media/11f35ceb-6c98-4580-a3bc-ad688e9c7af9.png)
  
3. <span data-ttu-id="7cea3-181">在 [**管理成員**、 下方按一下 [![新增圖示](media/ITPro-EAC-AddIcon.gif)**新增**成員新增到大小寫。</span><span class="sxs-lookup"><span data-stu-id="7cea3-181">Under **Manage members**, click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **Add** to add members to the case.</span></span> 
    
    <span data-ttu-id="7cea3-p117">您也可以選擇將角色群組新增至案例。[**管理角色群組**、 按一下 [![新增圖示](media/ITPro-EAC-AddIcon.gif)**新增]**。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p117">You can also choose to add a role group to the case. Under **Manage role groups**, click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **Add**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7cea3-p118">可將成員指派至 eDiscovery 案例的角色群組控制項。這表示您只能指派的角色群組您案例的成員。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p118">Role groups control who can assign members to an eDiscovery case. That means you can only assign the role groups that you are a member of to a case.</span></span>
    
4. <span data-ttu-id="7cea3-186">在可新增為成員的大小寫的人員或角色群組的清單中，按一下您想要新增的人員或角色群組的名稱旁邊的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="7cea3-186">In the list of people or role groups that can be added as members of the case, click the check box next to the names of the people or role groups that you want to add.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="7cea3-187">如果您有大型的人員可新增為成員的清單，可用於**搜尋**方塊的清單中的特定人員搜尋。</span><span class="sxs-lookup"><span data-stu-id="7cea3-187">If you have a large list of people who can added as members, use the **Search** box to search for a specific person in the list.</span></span> 
  
5. <span data-ttu-id="7cea3-188">您已選取 [加入群組之成員的人員或角色群組之後，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="7cea3-188">After you've selected the people or role groups to add as members of the group, click **Add**.</span></span>
    
    <span data-ttu-id="7cea3-189">在 [**管理此例中**，按一下 [**儲存**] 以儲存新案例成員的清單。</span><span class="sxs-lookup"><span data-stu-id="7cea3-189">In **Manage this case**, click **Save** to save the new list of case members.</span></span> 
    
6. <span data-ttu-id="7cea3-190">按一下 [**儲存**] 以儲存新案例成員的清單。</span><span class="sxs-lookup"><span data-stu-id="7cea3-190">Click **Save** to save the new list of case members.</span></span> 
  
## <a name="step-4-place-content-locations-on-hold"></a><span data-ttu-id="7cea3-191">步驟 4： 就地保留上的內容位置</span><span class="sxs-lookup"><span data-stu-id="7cea3-191">Step 4: Place content locations on hold</span></span>

<span data-ttu-id="7cea3-p119">您可以使用 eDiscovery 案例來建立保留来保留可能案例相關的內容。您可以置於保留信箱和 OneDrive 商務網站的是 custodians 案例中的人員。您也可以將保留群組信箱、 SharePoint 網站及 OneDrive 商務網站的 Office 365 群組。同樣地，您可以利用保留對信箱和相關聯的 Microsoft 小組網站。當您保留上放置的內容位置時，內容會保留直到您移除保留內容的位置或直到您刪除保留。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p119">You can use an eDiscovery case to create holds to preserve content that might be relevant to the case. You can place a hold on the mailboxes and OneDrive for Business sites of people who are custodians in the case. You can also place a hold on the group mailbox, SharePoint site, and OneDrive for Business site for an Office 365 Group. Similarly, you can place a hold on the mailbox and site that are associated with Microsoft Teams. When you place content locations on hold, content is held until you remove the hold from the content location or until you delete the hold.</span></span>

> [!NOTE]
> <span data-ttu-id="7cea3-197">內容位置置於保留之後，所花費 24 小時的時間的保留才會生效。</span><span class="sxs-lookup"><span data-stu-id="7cea3-197">After you place a content location on hold, it takes up to 24 hours for the hold to take effect.</span></span> 
>   
<span data-ttu-id="7cea3-198">當您建立保留時，您有下列選項的範圍會保留在指定的內容位置的內容：</span><span class="sxs-lookup"><span data-stu-id="7cea3-198">When you create a hold, you have the following options to scope the content that is held in the specified content locations:</span></span>
  
- <span data-ttu-id="7cea3-p120">您建立的所有內容都處於保留狀態設為無限期保留。或者，您可以建立查詢式的保留僅符合內容的搜尋查詢處於保留狀態。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p120">You create an infinite hold where all content is placed on hold. Alternatively, you can create a query-based hold where only content that matches a search query is placed on hold.</span></span>
    
- <span data-ttu-id="7cea3-p121">您可以指定日期範圍，以保留已傳送、 接收到，或建立的日期範圍內的內容。或者，您可以保留不論當它已傳送、 接收到，或建立的所有內容。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p121">You can specify a date range to hold only the content that was sent, received, or created within that date range. Alternatively, you can hold all content regardless of when it was sent, received, or created.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7cea3-203">您可以將最多 10000 個跨所有組織中的 eDiscovery 案例與保留原則。</span><span class="sxs-lookup"><span data-stu-id="7cea3-203">You can have a maximum of 10,000 hold policies across all eDiscovery cases in your organization.</span></span> 
  
<span data-ttu-id="7cea3-204">若要建立保留 eDiscovery 案例：</span><span class="sxs-lookup"><span data-stu-id="7cea3-204">To create a hold for an eDiscovery case:</span></span>
  
1. <span data-ttu-id="7cea3-205">在安全性與合規性中心，按一下 [搜尋和調查]\*\*\*\* \> [電子文件探索]\*\*\*\*，來顯示貴組織中的案例清單。</span><span class="sxs-lookup"><span data-stu-id="7cea3-205">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="7cea3-206">按一下您想要建立的保留案例] 旁的 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="7cea3-206">Click **Open** next to the case that you want to create the holds in.</span></span> 
    
3. <span data-ttu-id="7cea3-207">在 [**首頁**] 頁面的大小寫上按一下 [**保留**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="7cea3-207">On the **Home** page for the case, click the **Hold** tab.</span></span> 
    
    ![按一下 [保留] 索引標籤](media/3fef2db4-36de-4517-a34d-82f47b82d9bf.png)
  
4. <span data-ttu-id="7cea3-209">在 [**保留**] 頁面上，按一下 [![新增圖示](media/ITPro-EAC-AddIcon.gif)**建立**。</span><span class="sxs-lookup"><span data-stu-id="7cea3-209">On the **Hold** page, click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **Create**.</span></span>
    
5. <span data-ttu-id="7cea3-p122">在 [**名稱您保留**] 頁面提供保留的名稱。保留名稱必須是在組織中唯一的。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p122">On the **Name your hold** page, give the hold a name. The name of the hold must be unique in your organization.</span></span> 
    
    ![讓您保留的唯一名稱](media/7e15ea63-abd1-4f14-a29c-7ecfb9571d2c.png)
  
6. <span data-ttu-id="7cea3-213">（選用）在 [**描述**] 方塊中新增的保留的描述。</span><span class="sxs-lookup"><span data-stu-id="7cea3-213">(Optional) In the **Description** box, add a description of the hold.</span></span> 
    
7. <span data-ttu-id="7cea3-214">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7cea3-214">Click **Next**.</span></span>
    
8. <span data-ttu-id="7cea3-p123">選擇您想要進行的內容位置保留。您可以在保留上放置信箱、 網站及公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p123">Choose the content locations that you want to place on hold. You can place mailboxes, sites, and public folders on hold.</span></span>
    
    ![選擇要保留的內容位置](media/a59e4265-9151-4dbf-913f-6a4ab8db06b4.png)
  
   <span data-ttu-id="7cea3-p124">a. **Exchange 電子郵件**-[**選擇使用者、 群組或小組**和 [**選擇使用者、 群組或小組**一次。若要指定要保留信箱。使用 [搜尋] 方塊中找到使用者信箱使用者和通訊群組 （置於群組成員的信箱保留） 至保留。您也可撥打相關聯的信箱上的保留供 Office 365 群組或 Microsoft 小組。選取使用者、 群組、 小組] 核取方塊、 按一下 [**選擇**] 和 [**完成**。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p124">a. **Exchange email** - Click **Choose users, groups, or teams** and then click **Choose users, groups, or teams** again. to specify mailboxes to place on hold. Use the search box to find user mailboxes and distribution groups (to place a hold on the mailboxes of group members) to place on hold. You can also place a hold on the associated mailbox for an Office 365 Group or a Microsoft Team. Select the user, group, team check box, click **Choose**, and then click **Done**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7cea3-p125">當您按一下 [**選擇使用者、 群組或小組**來指定要保留信箱，會顯示信箱選擇是空的。這是由設計，以提升效能。若要將人員新增至這份清單中，輸入的名稱 （至少要有 3 個字元） 在 [搜尋] 方塊中。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p125">When you click **Choose users, groups, or teams** to specify mailboxes to place on hold, the mailbox picker that's displayed is empty. This is by design to enhance performance. To add people to this list, type a name (a minimum of 3 characters) in the search box.</span></span> 
  
   <span data-ttu-id="7cea3-p126">b. **SharePoint 網站**-按一下 [**選擇的網站**] 和 [**選擇網站**一次以指定 SharePoint 和 OneDrive for Business 網站置於保留。輸入您想要保留每個網站的 URL。您也可以針對 Office 365 群組或 Microsoft 小組新增 SharePoint 網站的 URL。按一下 [**選擇**] 和 [**完成**。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p126">b. **SharePoint Sites** - Click **Choose sites** and then click **Choose sites** again to specify SharePoint and OneDrive for Business sites to place on hold. Type the URL for each site that you want to place on hold. You can also add the URL for the SharePoint site for an Office 365 Group or a Microsoft Team. Click **Choose**, and then click **Done**.</span></span>
    
    <span data-ttu-id="7cea3-232">請參閱[的詳細資訊](#more-information)] 區段中放入保留的 Office 365 群組及 Microsoft 小組的秘訣。</span><span class="sxs-lookup"><span data-stu-id="7cea3-232">See the [More information](#more-information) section for tips on putting Office 365 Groups and Microsoft Teams on hold.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="7cea3-p127">在極罕見的情況下變更人員的使用者主體名稱 (UPN) 時，其 OneDrive 帳戶的 URL 會變更要併入新的 UPN。如果發生這種情況，您必須新增使用者的新 OneDrive URL 並移除舊來修改保留。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p127">In the rare case that a person's user principal name (UPN) is changed, the URL for their OneDrive account will also be changed to incorporate the new UPN. If this happens, you'll have to modify the hold by adding the user's new OneDrive URL and removing the old one.</span></span> 
  
   <span data-ttu-id="7cea3-p128">c. **Exchange 公用資料夾**-移動切換參數![切換控制項](media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)將放入保留 Exchange Online 組織的所有公用資料夾的**所有**位置。請注意，您無法選擇特定公用資料夾遷移至放入保留。保留設定成 [**無**如果您不想要的公用資料夾上設定保留切換參數。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p128">c. **Exchange public folders** - Move the toggle switch ![Toggle control](media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) to the **All** position to put all public folders in your Exchange Online organization on hold. Note that you can't choose specific public folders to put on hold. Leave the toggle switch set to **None** if you don't want to put a hold on public folders.</span></span>
    
9. <span data-ttu-id="7cea3-239">當您完成新增至保留的內容位置時，按一下 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="7cea3-239">When you're done adding content locations to the hold, click **Next**.</span></span>
    
10. <span data-ttu-id="7cea3-p129">若要建立條件查詢式保留，請完成下列設定。否則請只是按 [**下一步**</span><span class="sxs-lookup"><span data-stu-id="7cea3-p129">To create a query-based hold with conditions, complete the following. Otherwise, just click **Next**</span></span>
    
    ![使用條件建立查詢式保留](media/d587b58e-d05c-4ac0-b0fe-09019e4f1063.png)
  
    
       <span data-ttu-id="7cea3-p130">a.在 [**關鍵字**] 方塊中類型] 方塊中的搜尋查詢以便符合搜尋準則的內容放入保留。您可以指定關鍵字、 郵件內容或文件屬性，例如檔案名稱。您也可以使用較複雜布林運算子，例如**AND**、 **OR**，或**未**使用的查詢。如果您遺漏保留空白，則將會位於指定之內容的位置中的所有內容都放在 [關鍵字] 方塊。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p130">a. In the box under **Keywords**, type a search query in the box so that only the content that meets the search criteria is placed on hold. You can specify keywords, message properties, or document properties, such as file names. You can also use more complex queries that use a Boolean operator, such as **AND**, **OR**, or **NOT**. If you leave the keyword box empty, then all content located in the specified content locations will be placed on hold.</span></span>
    
    <span data-ttu-id="7cea3-p131">b 按一下 [![新增圖示](media/ITPro-EAC-AddIcon.gif)**新增條件**新增一或多個條件，縮減保留搜尋查詢。每個條件將子句新增至 KQL 搜尋查詢，建立及執行當您建立保留。例如您可以指定日期範圍，讓電子郵件或站台建立日期範圍內的文件會處於保留狀態。條件是以邏輯方式連線到 （在 [關鍵字] 方塊中指定） 的關鍵字查詢**和**運算子。表示項目必須滿足的關鍵字查詢及可放置在此條件就會保留。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p131">b. Click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **Add conditions** to add one or more conditions to narrow the search query for the hold. Each condition adds a clause to the KQL search query that is created and run when you create the hold. For example you can specify a date range so that email or site documents that were created within the date ranged are placed on hold. A condition is logically connected to the keyword query (specified in the keyword box) by the **AND** operator. That means that items have to satisfy both the keyword query and the condition to be placed on hold.</span></span>

    <span data-ttu-id="7cea3-254">如需建立搜尋查詢和使用情況的詳細資訊，請參閱[關鍵字查詢和搜尋條件的內容搜尋](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="7cea3-254">For more information about creating a search query and using conditions, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
    
11. <span data-ttu-id="7cea3-255">設定查詢式之後保留、 按一下 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7cea3-255">After configuring a query-based hold, click **Next**.</span></span>
    
12. <span data-ttu-id="7cea3-256">檢閱您的設定] 和 [**建立此保留**。</span><span class="sxs-lookup"><span data-stu-id="7cea3-256">Review your settings, and then click **Create this hold**.</span></span>
    
### <a name="hold-statistics"></a><span data-ttu-id="7cea3-257">保留的統計資料</span><span class="sxs-lookup"><span data-stu-id="7cea3-257">Hold statistics</span></span>

<span data-ttu-id="7cea3-p132">While 後的新保留的相關資訊會顯示所選保留的 [**保留**] 頁面的詳細資料窗格中。此資訊包含的信箱數目上的網站保留與已對內容的相關的統計資料保留，例如處於保留狀態的總人數及的項目大小和上次所計算的統計資料的保留。這些保留統計值能協助您識別要保留多少 eDiscovery 案例相關的內容。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p132">After a while, information about the new hold is displayed in the details pane on the **Holds** page for the selected hold. This information includes the number of mailboxes and sites on hold and statistics about the content that was placed on hold, such as the total number and size of items placed on hold and the last time the hold statistics were calculated. These hold statistics help you identify how much content that's related to the eDiscovery case is being held.</span></span> 
  
![保留的統計資料](media/575cfe0a-9210-4ae4-8df8-65665d66712e.png)
  
<span data-ttu-id="7cea3-262">保留有關保留統計資料記住下列事項：</span><span class="sxs-lookup"><span data-stu-id="7cea3-262">Keep the following things in mind about hold statistics:</span></span>
  
- <span data-ttu-id="7cea3-p133">保留的項目數總計會指出從保留的所有內容來源的項目數。如果您已建立查詢式保留功能，這次統計指出符合查詢的項目數。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p133">The total number of items on hold indicates the number of items from all content sources that are placed on hold. If you've created a query-based hold, this statistic indicates the number of items that match the query.</span></span>
    
- <span data-ttu-id="7cea3-p134">保留的項目數也包含編製索引的內容位置中找到的項目。如果您建立查詢式保留，內容的位置中的所有編製索引項目會放在保留的記事。這包括編製索引的項目不符合搜尋準則的查詢式保留及編製索引的項目可能屬於以外的日期範圍條件。這是與當您執行內容搜尋] 中編製索引的項目已不符合搜尋查詢或排除的日期範圍條件不包含在搜尋結果中有什麼不同。如需編製索引項目的詳細資訊，請參閱[部分編製索引項目中的 Office 365 中的內容搜尋](partially-indexed-items-in-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p134">The number of items on hold also includes unindexed items found in the content locations. Note that if you create a query-based hold, all unindexed items in the content locations are placed on hold. This includes unindexed items that don't match the search criteria of a query-based hold and unindexed items that might fall outside of a date range condition. This is different than what happens when you run a Content Search, in which unindexed items that don't match the search query or are excluded by a date range condition aren't included in the search results. For more information about unindexed items, see [Partially indexed items in Content Search in Office 365](partially-indexed-items-in-content-search.md).</span></span>
    
- <span data-ttu-id="7cea3-p135">您可以取得最新保留按一下 [重新執行搜尋的 [**更新統計資料**的統計資料評估的計算目前保留的項目數。若有必要，請按一下 [**重新整理**![重新整理] 圖示](media/O365-MDM-Policy-RefreshIcon.gif)要更新的詳細資料窗格中的保留統計資料工具列中。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p135">You can get the latest hold statistics by clicking **Update statistics** to re-run a search estimate that calculates the current number of items on hold. If necessary, click **Refresh**![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) in the toolbar to update the hold statistics in the details pane.</span></span> 
    
- <span data-ttu-id="7cea3-272">因為其信箱或網站會保留使用者通常會傳送或接收新的電子郵件訊息和建立新的 SharePoint 和 OneDrive for Business 文件增加一段時間保留它的一般上的項目數目。</span><span class="sxs-lookup"><span data-stu-id="7cea3-272">It's normal for the number of items on hold to increase over time because users whose mailbox or site is on hold are typically sending or receiving new email message and creating new SharePoint and OneDrive for Business documents.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7cea3-p136">如果當移至不同的區域在多個地理位置環境中的 SharePoint 網站或 OneDrive 帳戶時，該網站的統計資料將不會包含在保留統計資料。不過，在網站中的內容仍能音樂。此外，如果網站移至不同的區域不會更新顯示在保留中的 URL。您必須編輯保留及更新 URL。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p136">If a SharePoint site or OneDrive account is moved to a different region in a multi-geo environment, the statistics for that site won't be included in the hold statistics. However, the content in the site will still be on hold. Also, if a site is moved to a different region the URL that's displayed in the hold will not be updated. You'll have to edit the hold and update the URL.</span></span> 
  
## <a name="step-5-create-and-run-a-content-search-associated-with-a-case"></a><span data-ttu-id="7cea3-277">步驟 5： 建立並執行與案例相關聯之內容搜尋</span><span class="sxs-lookup"><span data-stu-id="7cea3-277">Step 5: Create and run a Content Search associated with a case</span></span>

<span data-ttu-id="7cea3-p137">建立 eDiscovery 案例並與案例相關的任何 custodians 處於保留狀態之後，您可建立並執行一或多個內容搜尋與案例相關聯。內容與案例相關聯的搜尋未列在安全性中的 [**搜尋**] 頁面上&amp;規範中心。內容搜尋相關聯的大小寫這表示只可以存取來區分成員能夠同時 eDiscovery 管理員角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p137">After an eDiscovery case is created and any custodians related to the case are placed on hold, you can create and run one or more Content Searches that are associated with the case. Content Searches associated with a case aren't listed on the **Search** page in the Security &amp; Compliance Center. This means that Content Searches associated with a case can only be accessed by case members who are also members of the eDiscovery Manager role group.</span></span> 
  
1. <span data-ttu-id="7cea3-281">在安全性與合規性中心，按一下 [搜尋和調查]\*\*\*\* \> [電子文件探索]\*\*\*\*，來顯示貴組織中的案例清單。</span><span class="sxs-lookup"><span data-stu-id="7cea3-281">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="7cea3-282">按一下 [大小寫您要建立的內容搜尋] 旁的 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="7cea3-282">Click **Open** next to the case that you want to create a Content Search in.</span></span> 
    
3. <span data-ttu-id="7cea3-283">按一下 [**首頁**] 頁面的大小寫的 [**搜尋**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="7cea3-283">On the **Home** page for the case, click the **Search** tab.</span></span> 
    
    ![搜尋索引標籤](media/2e15fe32-1a2e-4588-ad0b-5d96f77cece9.png)
  
4. <span data-ttu-id="7cea3-285">在 [**搜尋**] 頁面上，按一下 [![新增圖示](media/ITPro-EAC-AddIcon.gif)**新的搜尋**。</span><span class="sxs-lookup"><span data-stu-id="7cea3-285">On the **Search** page, click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **New search**.</span></span> 
    
5. <span data-ttu-id="7cea3-286">您可以在 [**新的搜尋**] 頁面上新增關鍵字和條件來建立搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="7cea3-286">On the **New search** page, you can add keywords and conditions to create the search query.</span></span> 
    
    ![新的搜尋](media/0e9954e7-c0ea-4e05-820b-e4b81dc5f81d.png)
  
6. <span data-ttu-id="7cea3-p138">您可以指定郵件的屬性，例如傳送和接收日期或文件屬性，例如檔案名稱或上次變更文件的日期的關鍵字。您可以使用較複雜使用布林運算子，例如**AND**、**或**、**不**、 **NEAR**或**ONEAR**的查詢。您也可以搜尋文件或搜尋功能已從外部共用的文件中的機密資訊 （例如社會安全編號）。如果 [關鍵字] 方塊中保留空白，將會在搜尋結果中包含位於指定之內容的位置中的所有內容。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p138">You can specify keywords, message properties, such as sent and received dates, or document properties, such as file names or the date that a document was last changed. You can use more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, **NEAR**, or **ONEAR**. You can also search for sensitive information (such as social security numbers) in documents, or search for documents that have been shared externally. If you leave the keyword box empty, all content located in the specified content locations will be included in the search results.</span></span> 
    
7. <span data-ttu-id="7cea3-p139">您可以按一下 [**顯示關鍵字清單**] 核取方塊和類型中的每一列的關鍵字。如果您這樣做，在每一列的關鍵字連接**OR**運算子會建立搜尋查詢中所連接。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p139">You can click the **Show keyword list** check box and the type a keyword in each row. If you do this, the keywords on each row are connected by the **OR** operator in the search query that's created.</span></span> 
    
    ![關鍵字清單](media/29cceb5d-2817-4fc4-b91a-ced1c5824a17.png)
  
    <span data-ttu-id="7cea3-p140">為什麼要選擇使用 [關鍵字] 清單？您可以取得顯示多少個項目比對每個關鍵字的統計資料。這可協助您快速識別出哪些關鍵字是最 （且至少） 有效。您也可以使用 （以括弧括住） 的關鍵字文句] 列中。如需搜尋統計資料的詳細資訊，請參閱 ＜[檢視內容的搜尋結果的關鍵字統計資料](view-keyword-statistics-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p140">Why use the keyword list? You can get statistics that show how many items match each keyword. This can help you quickly identify which keywords are the most (and least) effective. You can also use a keyword phrase (surrounded by parentheses) in a row. For more information about search statistics, see [View keyword statistics for Content Search results](view-keyword-statistics-for-content-search.md).</span></span>
    
    <span data-ttu-id="7cea3-300">如需使用關鍵字] 清單中的詳細資訊，請參閱[建立搜尋查詢](content-search.md#building-a-search-query)。</span><span class="sxs-lookup"><span data-stu-id="7cea3-300">For more information about using the keywords list, see [Building a search query](content-search.md#building-a-search-query).</span></span>
    
8. <span data-ttu-id="7cea3-p141">在 [**條件**新增條件來縮小搜尋及傳回一組更精簡的結果在搜尋查詢。每個條件將子句新增至 KQL 搜尋查詢，建立及執行當您啟動搜尋。條件是以邏輯方式連線到 （在 [關鍵字] 方塊中指定） 的關鍵字查詢**和**運算子。這表示項目必須滿足的關鍵字查詢與結果中包含的條件。這是條件，縮減結果協助的方式。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p141">Under **Conditions**, add conditions to a search query to narrow a search and return a more refined set of results. Each condition adds a clause to the KQL search query that is created and run when you start the search. A condition is logically connected to the keyword query (specified in the keyword box) by the **AND** operator. That means that items have to satisfy both the keyword query and the condition to be included in the results. This is how conditions help to narrow your results.</span></span> 
    
    <span data-ttu-id="7cea3-306">如需建立搜尋查詢和使用條件的相關資訊，請參閱 [Keyword queries for Content Search](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="7cea3-306">For more information about creating a search query and using conditions, see [Keyword queries for Content Search](keyword-queries-and-search-conditions.md).</span></span>
    
9. <span data-ttu-id="7cea3-p142">下**位置： 保留位置**，選擇您要搜尋的內容位置。您可以在相同的搜尋中搜尋信箱、 網站及公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p142">Under **Locations: locations on hold**, choose the content locations that you want to search. You can search mailboxes, sites, and public folders in the same search.</span></span>
    
    ![位置、 保留位置](media/d56398aa-0b20-4500-8e26-494eab92a99f.png)
  
    - <span data-ttu-id="7cea3-p143">**所有位置**-選取這個選項可在組織中搜尋所有內容的位置。當您選取這個選項時，您可以選擇搜尋所有的 Exchange 信箱 （其中包含信箱的所有 Office 365 群組與的 Microsoft 小組），所有 SharePoint 和 OneDrive for Business 的網站 （其中包含所有的 Office 365 群組與 Microsoft 的網站小組） 及所有公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p143">**All locations** - Select this option to search all content locations in your organization. When you select this option, you can choose to search all Exchange mailboxes (which includes the mailboxes for all Office 365 Groups and Microsoft Teams), all SharePoint and OneDrive for Business sites (which includes the sites for all Office 365 Groups and Microsoft Teams), and all public folders.</span></span>
    
    - <span data-ttu-id="7cea3-p144">**上的所有位置都保留**-選取此選項可搜尋已對所有內容位置都保留在 [大小寫。如果案例包含多個保留，當您選取這個選項會搜尋的所有保留位置的內容。此外，如果查詢式保留撥打內容的位置，只會保留的項目拼寫須符合當您執行您在此步驟中建立的內容搜尋。例如，如果使用者已處於查詢為基礎的案例保留保留項目已傳送或特定日期之前建立的這些項目嗎搜尋所使用之內容的搜尋的搜尋準則。這被藉由將 case 保留查詢及內容的搜尋查詢所**AND**運算子連線。請參閱如需詳細資訊搜尋 case 內容本文結尾處[的詳細資訊](ediscovery-cases.md#moreinfo_1)] 區段。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p144">**All locations on hold** - Select this option to search all the content locations that have been placed on hold in the case. If the case contains multiple holds, the content locations from all holds will be searched when you select this option. Additionally, if a content location was placed on a query-based hold, only the items that are on hold will be searched when you run the content search that you're creating in this step. For example, if a user was placed on query-based case hold that preserves items that were sent or created before a specific date, only those items would be searched by using the search criteria of the content search. This is accomplished by connecting the case hold query and the content search query by an **AND** operator. See the [More information](ediscovery-cases.md#moreinfo_1) section at the end of this article for more details about searching case content.</span></span> 
    
    - <span data-ttu-id="7cea3-p145">**特定位置**-選取這個選項可選取的信箱與您想要搜尋的網站。當您選取此選項並按一下 [**修改**] 時，會出現的位置清單。您可以選擇搜尋任何或所有的使用者、 群組、 小組或網站位置。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p145">**Specific locations** - Select this option to select the mailboxes and sites that you want to search. When you select this option and click **Modify**, a list of locations appears. You can choose to search any or all users, groups, teams, or site locations.</span></span>
    
      ![選取特定位置](media/97469b15-7be1-4aee-be27-f8343636152c.png)
  
      <span data-ttu-id="7cea3-p146">您也可以選擇在您的組織中搜尋所有的公用資料夾，但如果您選取此選項與搜尋上的任何內容位置保留、 從查詢為基礎的案例保留任何查詢不會套用至搜尋查詢。換句話說，搜尋位置中的所有內容，而不只保留查詢為基礎的案例保留的內容。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p146">You can also choose to search all public folders in your organization, but if you select this option and search any content location that's on hold, any query from a query-based case hold won't be applied to the search query. In other words, all content in a location is searched, not just the content that is preserved by a query-based case hold.</span></span>
    
      <span data-ttu-id="7cea3-p147">您可以移除預先填入的區分內容位置或新增新的。如果您選擇這個選項，您也可以彈性來搜尋特定的服務 （例如搜尋所有的 Exchange 信箱） 的所有內容的位置或可搜尋服務的特定內容的位置。您也可以選擇要在組織中搜尋的公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p147">You can remove the pre-populated case content locations or add new ones. If you choose this option, you also have flexibility to search all content locations for a specific service (such as searching all Exchange mailboxes) or you can search specific content locations for a service. You can also choose whether or not to search the public folders in your organization.</span></span>
    
      <span data-ttu-id="7cea3-327">新增要搜尋的內容位置時請牢記下列事項：</span><span class="sxs-lookup"><span data-stu-id="7cea3-327">Keep these things in mind when adding content locations to search:</span></span>
    
      - <span data-ttu-id="7cea3-p148">當您按一下 [**選擇使用者、 群組或小組**來指定要搜尋的信箱時，會顯示信箱選擇是空的。這是由設計，以提升效能。若要新增至這份清單的收件者，按一下 [**選擇使用者、 群組或小組**、 在 [搜尋] 方塊中輸入名稱 （至少要有 3 個字元）、 選取名稱旁的核取方塊和 [**選擇**。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p148">When you click **Choose users, groups, or teams** to specify mailboxes to search, the mailbox picker that's displayed is empty. This is by design to enhance performance. To add recipients to this list, click **Choose users, groups, or teams**, type a name (a minimum of 3 characters) in the search box, select the check box next to the name, and then click **Choose**.</span></span> 
    
      - <span data-ttu-id="7cea3-p149">您可以將非使用中信箱、 Office 365 群組、 Microsoft 小組及通訊群組新增至搜尋信箱清單。不支援動態通訊群組。若您要新增的 Office 365 群組或 Microsoft 小組、 群組或小組信箱搜尋 ；群組成員的信箱不搜尋。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p149">You can add inactive mailboxes, Office 365 Groups, Microsoft Teams, and distribution groups to the list of mailboxes to search. Dynamic distribution groups aren't supported. If you add Office 365 Groups or Microsoft Teams, the group or team mailbox is searched; the mailboxes of the group members aren't searched.</span></span>
    
      - <span data-ttu-id="7cea3-p150">若要新增網站按一下 [**選擇網站**、 再次按一下 [**選擇的網站**，並接著輸入您要搜尋的每個網站的 URL。您也可以新增 SharePoint 網站的 URL 為 Office 365 群組和 Microsoft 小組。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p150">To add sites click **Choose sites**, click **Choose sites** again, and then type the URL for each site that you want to search. You can also add the URL for the SharePoint site for Office 365 Groups and Microsoft Teams.</span></span> 
    
10. <span data-ttu-id="7cea3-336">之後您選取 [內容的位置來搜尋、 按一下 [**完成**]，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="7cea3-336">After you select the content locations to search, click **Done** and then click **Save**.</span></span>
    
11. <span data-ttu-id="7cea3-p151">在 [**新的搜尋**] 頁面上，按一下 [**儲存**]，然後輸入搜尋的名稱。與案例相關聯的內容搜尋必須是 Office 365 組織內唯一的名稱。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p151">On the **New search** page, click **Save** and then type a name for the search. Content Searches associated with a case must have names that are unique within your Office 365 organization.</span></span> 
    
12. <span data-ttu-id="7cea3-339">按一下 [**儲存&amp;執行**儲存搜尋設定。</span><span class="sxs-lookup"><span data-stu-id="7cea3-339">Click **Save &amp; run** to save the search settings.</span></span> 
    
13. <span data-ttu-id="7cea3-340">輸入搜尋] 中的唯一名稱並按一下 [**儲存**] 以啟動搜尋。</span><span class="sxs-lookup"><span data-stu-id="7cea3-340">Enter a unique name for the search, and click **Save** to start the search.</span></span> 
    
    <span data-ttu-id="7cea3-p152">一開始會搜尋。While 之後評估會有搜尋結果會顯示詳細資料窗格中。評估包含的總大小和符合搜尋準則的項目數。搜尋 estimate 也包括所搜尋的內容位置編製索引的項目數。編製索引不符合搜尋準則的項目數將包含在詳細資料窗格中顯示的搜尋統計資料。如果搜尋查詢 （因為其他訊息或文件屬性符合搜尋準則） 編製索引的項目相符，則不會包含在估計編製索引的項目數。如果編製索引的項目會排除的搜尋準則，它也不會包含在評估編製索引的項目。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p152">The search begins. After a while, an estimate of the search results is displayed in the details pane. The estimate includes the total size and number of items that matched the search criteria. The search estimate also includes the number of unindexed items in the content locations that were searched. The number of unindexed items that don't meet the search criteria will be included in the search statistics displayed in the details pane. If an unindexed item matches the search query (because other message or document properties meet the search criteria), it won't be included in the estimated number of unindexed items. If an unindexed item is excluded by the search criteria, it also won't be included in the estimate of unindexed items.</span></span>
    
  <span data-ttu-id="7cea3-p153">搜尋完成後，您可預覽搜尋結果。若有必要，請按一下 [**重新整理**![重新整理] 圖示](media/O365-MDM-Policy-RefreshIcon.gif)要更新的詳細資料窗格中的資訊。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p153">After the search is completed, you can preview the search results. If necessary, click **Refresh**![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
## <a name="step-6-export-the-results-of-a-content-search-associated-with-a-case"></a><span data-ttu-id="7cea3-350">步驟 6： 匯出與案例相關聯之內容搜尋的結果</span><span class="sxs-lookup"><span data-stu-id="7cea3-350">Step 6: Export the results of a Content Search associated with a case</span></span>

<span data-ttu-id="7cea3-p154">成功執行搜尋之後，您可以將匯出的搜尋結果。當您將搜尋結果匯出信箱項目會下載 PST 檔案中或以個別的郵件。當您匯出 SharePoint 與內容 OneDrive for Business 的網站時，都要匯出的原生 Office 文件和其他文件複本。包含每個搜尋結果的相關資訊的資訊清單檔案 （以 XML 格式） 也會匯出。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p154">After a search is successfully run, you can export the search results. When you export search results, mailbox items are downloaded in PST files or as individual messages. When you export content from SharePoint and OneDrive for Business sites, copies of native Office documents and other documents are exported. A manifest file (in XML format) that contains information about every search result is also exported.</span></span>
  
<span data-ttu-id="7cea3-355">您可以將匯出的[匯出與案例相關聯的單一搜尋結果](ediscovery-cases.md#singlesearch_1)的結果或您可以將匯出的[匯出其結果的多個案例相關聯的搜尋](ediscovery-cases.md#multiplesearches_1)結果。</span><span class="sxs-lookup"><span data-stu-id="7cea3-355">You can export the results of a [Export the results of a single search associated with a case](ediscovery-cases.md#singlesearch_1) or you can export the results of [Export the results of multiple searches associated with a case](ediscovery-cases.md#multiplesearches_1).</span></span>
  
### <a name="export-the-results-of-a-single-search-associated-with-a-case"></a><span data-ttu-id="7cea3-356">匯出與案例相關聯的單一搜尋結果</span><span class="sxs-lookup"><span data-stu-id="7cea3-356">Export the results of a single search associated with a case</span></span>

1. <span data-ttu-id="7cea3-357">在安全性與合規性中心，按一下 [搜尋和調查]\*\*\*\* \> [電子文件探索]\*\*\*\*，來顯示貴組織中的案例清單。</span><span class="sxs-lookup"><span data-stu-id="7cea3-357">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="7cea3-358">按一下您想要匯出從搜尋案例] 旁的 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="7cea3-358">Click **Open** next to the case that you want to export search from.</span></span> 
    
3. <span data-ttu-id="7cea3-359">在 [**首頁**] 頁面的大小寫上按一下 [**搜尋**]。</span><span class="sxs-lookup"><span data-stu-id="7cea3-359">On the **Home** page for the case, click **Search**.</span></span>
    
4. <span data-ttu-id="7cea3-360">在搜尋案例清單中，按一下 [您想要匯出的搜尋結果中，按一下 [搜尋![匯出搜尋結果圖示](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png)**多個**，並再選取 [**匯出結果**的下拉式清單中。</span><span class="sxs-lookup"><span data-stu-id="7cea3-360">In the list of searches for the case, click the search that you want to export search results from, click ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **More**, and then select **Export results** from the drop-down list.</span></span> 
    
    <span data-ttu-id="7cea3-361">會顯示 [**匯出結果**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7cea3-361">The **Export results** page is displayed.</span></span> 
    
    ![匯出結果頁面](media/ab0bb46d-310b-4374-8644-717146df6676.png)
  
    <span data-ttu-id="7cea3-p155">要匯出之內容的搜尋結果的工作流程相關聯的案例是可與相同匯出搜尋結果在**內容搜尋**] 頁面上。如需逐步說明，請參閱[匯出內容的搜尋結果的 Office 365 安全性&amp;規範中心](export-search-results.md)。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p155">The workflow to export the results from a Content Search associated with a case is that same as exporting the search results for a search on the **Content search** page. For step-by-step instructions, see [Export Content Search results from the Office 365 Security &amp; Compliance Center](export-search-results.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7cea3-p156">匯出搜尋結果時，必須啟用重複資料刪除以便只有一個電子郵件的副本匯出即使多個執行個體相同的訊息可能會有已搜尋的信箱中找到的選項。如需詳細資訊需重複資料刪除和如何重複的項目會識別出，請參閱[重複資料刪除 eDiscovery 搜尋結果中](de-duplication-in-ediscovery-search-results.md)。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p156">When you export search results, you have the option to enable de-duplication so that only one copy of an email message is exported even though multiple instances of the same message might have been found in the mailboxes that were searched. For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span> 
  
5. <span data-ttu-id="7cea3-367">按一下 [**匯出**] 索引標籤以顯示該案例存在的匯出工作的清單。</span><span class="sxs-lookup"><span data-stu-id="7cea3-367">Click the **Export** tab to display the list of export jobs that exist for that case.</span></span> 
    
    ![匯出] 索引標籤](media/1b84c45e-4ec9-4ecd-9e07-eaf8fc4cc307.png)
  
    <span data-ttu-id="7cea3-p157">您可能必須按一下 [**重新整理**![重新整理] 圖示](media/O365-MDM-Policy-RefreshIcon.gif)使其顯示匯出工作剛建立更新的匯出工作清單。請注意匯出工作有相同名稱的對應的內容搜尋與 **_Export**附加至搜尋名稱結尾。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p157">You might have to click **Refresh**![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the list of export jobs so that it shows the export job that you just created. Note that export jobs have the same name as the corresponding Content Search with **_Export** appended to the end of search name.</span></span> 
    
6. <span data-ttu-id="7cea3-p158">按一下您剛建立的詳細資料窗格中顯示狀態資訊的匯出工作。此資訊包含已經移轉到 Microsoft 雲端 Azure 儲存區的項目百分比。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p158">Click the export job that you just created to display status information in the details pane. This information includes the percentage of items that have been transferred to an Azure storage area in the Microsoft cloud.</span></span>
    
    <span data-ttu-id="7cea3-p159">所有項目已傳送之後，按一下 [下載至您的本機電腦的搜尋結果的 [**下載結果**。如需詳細資訊，請參閱 ＜ 步驟 2 中[匯出內容的搜尋結果的 Office 365 安全性&amp;規範中心](export-search-results.md)</span><span class="sxs-lookup"><span data-stu-id="7cea3-p159">After all items have been transferred, click **Download results** to download the search results to your local computer. For more information, see Step 2 in [Export Content Search results from the Office 365 Security &amp; Compliance Center](export-search-results.md)</span></span>
    
### <a name="export-the-results-of-multiple-searches-associated-with-a-case"></a><span data-ttu-id="7cea3-375">匯出多個案例相關聯的搜尋結果</span><span class="sxs-lookup"><span data-stu-id="7cea3-375">Export the results of multiple searches associated with a case</span></span>

<span data-ttu-id="7cea3-p160">當另一種替代匯出單一內容的搜尋結果相關聯的案例，您可以從單一匯出中的相同情況匯出多個搜尋的結果。匯出多個搜尋的結果是更快且更容易比匯出結果一個搜尋一次。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p160">As an alternative to exporting the results of a single Content Search associated with a case, you can export the results of multiple searches from the same case in a single export. Exporting the results of multiple searches is faster and easier than exporting the results one search at a time.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7cea3-p161">您無法將多個搜尋結果匯出如果其中一個這些搜尋設定為搜尋所有案例的內容。僅匯出多個搜尋與 eDiscovery 案例相關聯的搜尋結果。您無法將匯出的安全性**內容搜尋**] 頁面上所列的多個搜尋結果&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p161">You can't export the results of multiple searches if one of those searches was configured to search all case content. only export the results of multiple searches for searches that are associated with an eDiscovery case. You can't export the results of multiple searches listed on the **Content search** page in the Security &amp; Compliance Center.</span></span> 
  
1. <span data-ttu-id="7cea3-381">在安全性與合規性中心，按一下 [搜尋和調查]\*\*\*\* \> [電子文件探索]\*\*\*\*，來顯示貴組織中的案例清單。</span><span class="sxs-lookup"><span data-stu-id="7cea3-381">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="7cea3-382">按一下您想要匯出的搜尋結果的大小寫] 旁的 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="7cea3-382">Click **Open** next to the case that you want to export search results from.</span></span> 
    
3. <span data-ttu-id="7cea3-383">在 [**首頁**] 頁面的大小寫上按一下 [**搜尋**]。</span><span class="sxs-lookup"><span data-stu-id="7cea3-383">On the **Home** page for the case, click **Search**.</span></span>
    
4. <span data-ttu-id="7cea3-384">在 [大小寫的搜尋] 清單選取您想要匯出的搜尋結果的兩個或多個搜尋。</span><span class="sxs-lookup"><span data-stu-id="7cea3-384">In the list of searches for the case, select two or more searches that you want to export search results from.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7cea3-p162">若要選取多個搜尋，按住 Ctrl 鍵按一下每個搜尋。或者，您可以按一下第一個搜尋、 按住 Shift 鍵，然後按一下 [上次搜尋來選取多個相鄰的搜尋。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p162">To select multiple searches, press Ctrl as you click each search. Or you can select multiple adjacent searches by clicking the first search, holding down the Shift key, and then clicking the last search.</span></span> 
  
5. <span data-ttu-id="7cea3-387">選取搜尋之後，便會出現 [**大量動作**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7cea3-387">After you select the searches, the **Bulk actions** page appears.</span></span> 
    
    ![在 [大量動作] 頁面上，按一下 [匯出結果](media/f34e3707-a9c1-494f-91a4-da1165aa730a.png)
  
    
6. <span data-ttu-id="7cea3-389">按一下 [![匯出搜尋結果圖示](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png)**匯出結果**。</span><span class="sxs-lookup"><span data-stu-id="7cea3-389">Click ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **Export results**.</span></span>

7. <span data-ttu-id="7cea3-p163">在**匯出結果**] 頁面上提供匯出的唯一名稱，選取 [輸出選項並選擇 [匯出內容的方式。按一下 [**匯出**]。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p163">On the **Export results** page, give the export a unique name, select output options, and choose how your content will be exported. Click **Export**.</span></span>
    
    <span data-ttu-id="7cea3-p164">要匯出結果從多個內容搜尋與案例相關聯的工作流程並匯出單一搜尋結果相同。如需逐步說明，請參閱[匯出內容的搜尋結果的 Office 365 安全性&amp;規範中心](export-search-results.md)。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p164">The workflow to export the results from multiple content searches associated with a case is the same as exporting the search results for a single search. For step-by-step instructions, see [Export Content Search results from the Office 365 Security &amp; Compliance Center](export-search-results.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7cea3-p165">當您從多個案例相關聯的搜尋匯出搜尋結果時，您也可以啟用重複資料刪除以便只有一個電子郵件的副本匯出即使多個執行個體相同訊息可能會有中找到的選項在一或多個搜尋所搜尋的信箱。如需詳細資訊需重複資料刪除和如何重複的項目會識別出，請參閱[重複資料刪除 eDiscovery 搜尋結果中](de-duplication-in-ediscovery-search-results.md)。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p165">When you export search results from multiple searches associated with a case, you also have the option to enable de-duplication so that only one copy of an email message is exported even though multiple instances of the same message might have been found in the mailboxes that were searched in one or more of the searches. For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span> 
  
8. <span data-ttu-id="7cea3-396">在您開始匯出之後，按一下 [**匯出**] 索引標籤以顯示該案例的匯出工作的清單。</span><span class="sxs-lookup"><span data-stu-id="7cea3-396">After you start the export, click the **Export** tab to display the list of export jobs for that case.</span></span> 
    
    ![匯出多個搜尋索引標籤](media/b9505e1b-559f-4a8c-96b3-a3f734753926.png)
  
    <span data-ttu-id="7cea3-p166">您可能必須按一下 [**重新整理**![重新整理] 圖示](media/O365-MDM-Policy-RefreshIcon.gif)要更新的匯出至顯示您剛才建立的匯出工作的工作清單。請注意匯出工作中所包含的搜尋所列在 [**搜尋**] 欄中。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p166">You might have to click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the list of export jobs to display the export job that you just created. Note that the searches that were included in the export job are listed in the **Searches** column.</span></span> 
    
8. <span data-ttu-id="7cea3-p167">按一下您剛建立的詳細資料窗格中顯示狀態資訊的匯出工作。此資訊包含已經移轉到 Microsoft 雲端 Azure 儲存區的項目百分比。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p167">Click the export job that you just created to display status information in the details pane. This information includes the percentage of items that have been transferred to an Azure storage area in the Microsoft cloud.</span></span>
    
9. <span data-ttu-id="7cea3-p168">所有項目已傳送之後，按一下 [下載至您的本機電腦的搜尋結果的 [**下載結果**。如需詳細資訊，請參閱 ＜ 步驟 2 中[匯出搜尋結果的 Office 365 安全性&amp;規範中心](export-search-results.md)</span><span class="sxs-lookup"><span data-stu-id="7cea3-p168">After all items have been transferred, click **Download results** to download the search results to your local computer. For more information, see Step 2 in [Export search results from the Office 365 Security &amp; Compliance Center](export-search-results.md)</span></span>
    
#### <a name="more-information-about-exporting-the-results-of-multiple-searches"></a><span data-ttu-id="7cea3-404">匯出多個搜尋結果的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="7cea3-404">More information about exporting the results of multiple searches</span></span>

- <span data-ttu-id="7cea3-p169">當您將匯出的多個搜尋結果時，搜尋查詢所有搜尋從結合使用**或**運算子，然後合併的搜尋已啟動。估計合併的搜尋結果會顯示所選的匯出工作的詳細資料窗格中。在搜尋結果會然後轉接到 Microsoft 雲端中的 [Azure 存放區] 區域。傳輸狀態也會顯示在詳細資料窗格中。先前所述，已轉移所有搜尋結果之後，您可以下載這些到您的本機電腦。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p169">When you export the results of multiple searches, the search queries from all the searches are combined by using **OR** operators, and then the combined search is started. The estimated results of the combined search are displayed in the details pane of the selected export job. The search results are then transferred to the Azure storage area in the Microsoft cloud. The status of the transfer is also displayed in the details pane. As previously stated, after all the search results have been transferred, you can download them to your local computer.</span></span> 
    
- <span data-ttu-id="7cea3-p170">您想要匯出的所有搜尋搜尋查詢關鍵字的數目上限為 500。（這是單一內容搜尋的相同限制。）那是因為匯出工作合併所有搜尋查詢使用**OR**運算子。如果您超過此限制，則會傳回錯誤。在此例中，您必須從較少的搜尋結果匯出或簡化您想要匯出的搜尋搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p170">The maximum number of keywords from the search queries for all searches that you want to export is 500. (this is the same limit for a single Content Search). That's because the export job combines all the search queries by using the **OR** operator. If you exceed this limit, an error will be returned. In this case, you'll have to export the results from fewer searches or simplify the search queries of the searches that you want to export.</span></span> 
    
- <span data-ttu-id="7cea3-p171">會匯出搜尋結果被依據此項目中找到的內容來源。這表示在匯出結果的內容來源可能會有不同的搜尋所傳回的項目。例如，如果您選擇要匯出的每個信箱的一個 PST 檔案中的電子郵件訊息、 PST 檔案可能會有來自多個搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p171">The search results that are exported are organized by the content source the item was found in. That means a content source in the export results might have items returned by different searches. For example, if you chose to export email messages in one PST file for each mailbox, the PST file might have results from multiple searches.</span></span>
    
- <span data-ttu-id="7cea3-418">如果相同的電子郵件項目或文件從相同的內容位置由多個匯出搜尋所傳回，要匯出的項目只有一個複本。</span><span class="sxs-lookup"><span data-stu-id="7cea3-418">If the same email item or document from the same content location is returned by more than one of the searches that you export, only one copy of the item will be exported.</span></span>
    
- <span data-ttu-id="7cea3-p172">您在建立之後，您無法編輯匯出多個搜尋。例如，您無法新增或移除匯出搜尋。您必須建立新的匯出工作變更都要匯出哪些搜尋結果。建立 「 匯出 」 工作之後，您只可以下載到電腦的結果、 重新啟動匯出，或刪除匯出工作。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p172">You can't edit an export for multiple searches after you create it. For example, you can't add or remove searches from the export. You'll have to create a new export job to change which search results are exported. After a export job is created, you only can download the results to a computer, restart the export, or delete the export job.</span></span>
    
- <span data-ttu-id="7cea3-p173">如果您重新啟動匯出的匯出工作所組成的搜尋查詢的任何變更將不會影響將擷取的搜尋結果。當您重新啟動匯出時，將會再次執行建立匯出工作時所執行的相同合併的搜尋查詢工作。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p173">If you restart the export, any changes to the queries of the searches that make up the export job won't affect the search results that will be retrieved. When you restart an export, the same combined search query job that was run when the export job was created will be run again.</span></span>
    
- <span data-ttu-id="7cea3-425">如果您重新啟動 eDiscovery 案例中的匯出從 [**匯出**] 頁面上，會轉接到 Azure 儲存區的搜尋結果會覆寫先前的結果 ；先前的結果有已轉接通話將不會可供下載。</span><span class="sxs-lookup"><span data-stu-id="7cea3-425">If you restart an export from the **Exports** page in an eDiscovery case, the search results that are transferred to the Azure storage area will overwrite the previous results; the previous results there were transferred won't be available to be downloaded.</span></span> 
    
- <span data-ttu-id="7cea3-p174">準備進行分析進階在 eDiscovery 中的多個搜尋結果無法使用。您只可以準備進行分析進階在 eDiscovery 中的單一搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p174">Preparing the results of multiple searches for analysis in Advanced eDiscovery isn't available. You can only prepare the results of a single search for analysis in Advanced eDiscovery.</span></span>

## <a name="step-7-prepare-search-results-for-advanced-ediscovery"></a><span data-ttu-id="7cea3-428">步驟 7： 準備搜尋結果進階 ediscovery （英文）</span><span class="sxs-lookup"><span data-stu-id="7cea3-428">Step 7: Prepare search results for Advanced eDiscovery</span></span>

<span data-ttu-id="7cea3-p175">如果貴組織的 Office 365 E5 訂閱，您可以準備內容進行分析進階 ediscovery 案例相關聯的搜尋的結果。準備好搜尋結果之後，您可以前往進階的 eDiscovery (請參閱[步驟 8： 移至 [進階 ediscovery 案例](#step-8-go-to-the-case-in-advanced-ediscovery)) 及處理供進一步分析進階在 eDiscovery 中搜尋結果資料。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p175">If your organization has an Office 365 E5 subscription, you can prepare the results of Content Searches associated with a case for analysis in Advanced eDiscovery. After you prepare search results, you can go to Advanced eDiscovery (see [Step 8: Go to the case in Advanced eDiscovery](#step-8-go-to-the-case-in-advanced-ediscovery)) and process the search result data for further analysis in Advanced eDiscovery.</span></span>
  
<span data-ttu-id="7cea3-p176">當您準備進階 eDiscovery 搜尋結果時，光學字元辨識 (OCR) 功能自動擷取文字的圖像。OCR 支援寬鬆的檔案、 電子郵件附件、 和內嵌圖像。這可讓您將文字分析功能的進階 eDiscovery （接近重複項目、 電子郵件執行緒、 佈景主題及預測編碼） 套用至圖像檔案中的任何文字。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p176">When you prepare search results for Advanced eDiscovery, optical character recognition (OCR) functionality automatically extracts text from images. OCR is supported for loose files, email attachments, and embedded images. This allows you to apply the text analytic capabilities of Advanced eDiscovery (near-duplicates, email threading, themes, and predictive coding) to any text in image files.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7cea3-p177">若要分析使用進階的 eDiscovery 的使用者資料，使用者 (資料 okay) 必須指派 Office 365 E5 授權。或者，使用 Office 365 E1 或 E3 授權的使用者可以將指派進階的 eDiscovery 獨立授權。系統管理員及法務人員對於已指派給的情況下並使用進階的 eDiscovery 分析資料不需要的 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p177">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license. Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license. Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span> 
  
1. <span data-ttu-id="7cea3-437">在安全性與合規性中心，按一下 [搜尋和調查]\*\*\*\* \> [電子文件探索]\*\*\*\*，來顯示貴組織中的案例清單。</span><span class="sxs-lookup"><span data-stu-id="7cea3-437">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="7cea3-438">按一下您想要準備分析進階在 eDiscovery 中搜尋結果的大小寫] 旁的 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="7cea3-438">Click **Open** next to the case that you want to prepare search results for analysis in Advanced eDiscovery.</span></span> 
    
3. <span data-ttu-id="7cea3-439">在 [**首頁**] 頁面的大小寫 [**搜尋**]，然後選取搜尋]。</span><span class="sxs-lookup"><span data-stu-id="7cea3-439">On the **Home** page for the case, click **Search**, and then select the search.</span></span>
    
4. <span data-ttu-id="7cea3-440">在 [詳細資料] 窗格中，按一下 [![匯出搜尋結果圖示](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png)**多個**，然後按一下 [**準備進階 ediscovery （英文）**。</span><span class="sxs-lookup"><span data-stu-id="7cea3-440">In the details pane, click ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **More**, and then click **Prepare for Advanced eDiscovery**.</span></span>
    
    ![準備您的結果進階 ediscovery （英文）](media/b6548ff0-a6e9-42b1-9ae4-5c15146f5690.png)
  
5. <span data-ttu-id="7cea3-442">在 [**進階 ediscovery （英文） 的準備**] 頁面上選擇 [準備下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="7cea3-442">On the **Prepare for Advanced eDiscovery** page, choose to prepare one of the following:</span></span> 
    
    - <span data-ttu-id="7cea3-443">排除那些使用無法辨識格式的所有項目已加密或未編製索引的其他原因。</span><span class="sxs-lookup"><span data-stu-id="7cea3-443">All items, excluding those with unrecognized format, are encrypted, or weren't indexed for other reasons.</span></span>
    
    - <span data-ttu-id="7cea3-444">包括已無法辨認的格式的所有項目已加密或未編製索引的其他原因。</span><span class="sxs-lookup"><span data-stu-id="7cea3-444">All items, including those that have unrecognized format, are encrypted, or weren't indexed for other reasons.</span></span>
    
    - <span data-ttu-id="7cea3-445">僅有格式無法辨識的項目已加密或未編製索引的其他原因。</span><span class="sxs-lookup"><span data-stu-id="7cea3-445">Only items that have an unrecognizable format, are encrypted, or weren't indexed for other reasons.</span></span>
    
6. <span data-ttu-id="7cea3-446">（選用）按一下 [ **SharePoint 檔案包含版本**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="7cea3-446">(Optional) Click the **Include versions for SharePoint files** check box.</span></span> 
    
7. <span data-ttu-id="7cea3-447">按一下 [**準備**]。</span><span class="sxs-lookup"><span data-stu-id="7cea3-447">Click **Prepare**.</span></span>
    
    <span data-ttu-id="7cea3-448">在搜尋結果已備妥與進階 eDiscovery 的分析。</span><span class="sxs-lookup"><span data-stu-id="7cea3-448">The search results are prepared for analysis with Advanced eDiscovery.</span></span>
    
8. <span data-ttu-id="7cea3-449">按一下 [**關閉**] 以關閉詳細資料窗格中。</span><span class="sxs-lookup"><span data-stu-id="7cea3-449">Click **Close** to close the details pane.</span></span> 
    
## <a name="step-8-go-to-the-case-in-advanced-ediscovery"></a><span data-ttu-id="7cea3-450">步驟 8： 移至 [進階 ediscovery 案例</span><span class="sxs-lookup"><span data-stu-id="7cea3-450">Step 8: Go to the case in Advanced eDiscovery</span></span>

<span data-ttu-id="7cea3-451">安全性建立案例之後&amp;規範中心您可以前往進階在 eDiscovery 中相同的大小寫。</span><span class="sxs-lookup"><span data-stu-id="7cea3-451">After you create a case in the Security &amp; Compliance Center, you can go to the same case in Advanced eDiscovery.</span></span>
  
<span data-ttu-id="7cea3-452">若要移至進階電子文件探索中的案例：</span><span class="sxs-lookup"><span data-stu-id="7cea3-452">To go to a case in Advanced eDiscovery:</span></span>
  
1. <span data-ttu-id="7cea3-453">在安全性與合規性中心，按一下 [搜尋和調查]\*\*\*\* \> [電子文件探索]\*\*\*\*，來顯示貴組織中的案例清單。</span><span class="sxs-lookup"><span data-stu-id="7cea3-453">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="7cea3-454">按一下您想要移至 [進階 ediscovery 案例] 旁的 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="7cea3-454">Click **Open** next to the case that you want to go to in Advanced eDiscovery.</span></span> 
    
3. <span data-ttu-id="7cea3-455">按一下 [**首頁**] 頁面的大小寫的 [**進階 ediscovery 的切換參數**。</span><span class="sxs-lookup"><span data-stu-id="7cea3-455">On the **Home** page for the case, click **Switch to Advanced eDiscovery**.</span></span>
    
    ![選取進階 ediscovery 的切換參數](media/d7e31558-e79c-4782-b841-2b735568a576.png)
  
    <span data-ttu-id="7cea3-p178">會顯示 [**連線至進階 eDiscovery**進度列。當您連線至進階的 eDiscovery 時、 容器清單隨即顯示在頁面。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p178">The **Connecting to Advanced eDiscovery** progress bar is displayed. When you're connected to Advanced eDiscovery, a list of containers is displayed on the page.</span></span> 
    
    ![進階的 eDiscorvery 進度列](media/4a84273d-765b-44b8-9006-c20e810ea393.png)
  
    <span data-ttu-id="7cea3-p179">這些容器代表您準備進行分析步驟 7 中的進階 eDiscovery 中搜尋結果。該容器的名稱同名內容搜尋案例中安全性的附註&amp;規範中心。在清單容器是過您準備。如果不同的使用者準備進階 eDiscovery 搜尋結果，相對應的容器不會包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p179">These containers represent the search results that you prepared for analysis in Advanced eDiscovery in Step 7. Note that the name of the container has the same name as Content Search in the case in the Security &amp; Compliance Center. The containers in the list are the ones that you prepared. If a different user prepared search results for Advanced eDiscovery, the corresponding containers won't be included in the list.</span></span>
    
4. <span data-ttu-id="7cea3-464">從容器的搜尋結果資料載入至進階 ediscovery 案例中，選取容器並按一下 [**程序**。</span><span class="sxs-lookup"><span data-stu-id="7cea3-464">To load the search result data from a container to the case in Advanced eDiscovery, select a container and click **Process**.</span></span>
    
    <span data-ttu-id="7cea3-465">如需如何處理程序容器的資訊，請參閱[執行程序模組和 Office 365 進階在 eDiscovery 中的將資料載入](run-the-process-module-and-load-data-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="7cea3-465">For information about how to process containers, see [Run the Process module and load data in Office 365 Advanced eDiscovery](run-the-process-module-and-load-data-in-advanced-ediscovery.md).</span></span>
    
> [!TIP]
> <span data-ttu-id="7cea3-466">按一下 [ **ediscovery 切換**回移至 [安全性] 中的相同情況&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="7cea3-466">Click **Switch to eDiscovery** to go back to the same case in the Security &amp; Compliance Center.</span></span> 
  
## <a name="optional-step-9-close-a-case"></a><span data-ttu-id="7cea3-467">（選用）步驟 9： 關閉案例</span><span class="sxs-lookup"><span data-stu-id="7cea3-467">(Optional) Step 9: Close a case</span></span>

<span data-ttu-id="7cea3-p180">法律案例或 eDiscovery 案例所支援的調查完成時，即可關閉案例。以下是當您關閉案例會發生什麼事：</span><span class="sxs-lookup"><span data-stu-id="7cea3-p180">When the legal case or investigation supported by an eDiscovery case is completed, you can close the case. Here's what happens when you close a case:</span></span>
  
- <span data-ttu-id="7cea3-p181">如果案例包含音樂的所有內容位置，將會開啟這些保留。這可能會導致內容要永久刪除或清除、 使用者或自動程序，例如的刪除原則。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p181">If the case contains any content locations on hold, those holds will be turned off. This might result in content being permanently deleted or purged, either by the user or by an automated process, such as a deletion policy.</span></span>
    
- <span data-ttu-id="7cea3-p182">關閉案例只會關閉與該案例相關聯的保留。如果其他保留內容的位置 （例如訴訟保留。 保留原則，或從不同的 eDiscovery 案例的保留） 上進行這些保留則仍會保留。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p182">Closing a case only turns off the holds that are associated with that case. If other holds are place on a content location (such as a Litigation Hold. a Preservation Policy, or a hold from a different eDiscovery case) those holds will still be maintained.</span></span>
    
- <span data-ttu-id="7cea3-p183">大小寫仍會列在 [eDiscovery] 頁面上的 [安全性]&amp;規範中心。會保留詳細資料、 保留、 搜尋，並關閉案例的成員。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p183">The case is still listed on the eDiscovery page in the Security &amp; Compliance Center. The details, holds, searches, and members of a closed case are retained.</span></span>
    
- <span data-ttu-id="7cea3-p184">會在關閉之後，您可以編輯案例。例如，您可以新增或移除成員建立搜尋、 匯出搜尋結果，並準備分析進階在 eDiscovery 中搜尋結果。作用中且已關閉的情況下的主要差異在於保留已關閉時關閉案例。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p184">You can edit a case after it's closed. For example, you can add or removing members, create searches, export search results, and prepare search result for analysis in Advanced eDiscovery. The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>
    
<span data-ttu-id="7cea3-480">若要關閉案例：</span><span class="sxs-lookup"><span data-stu-id="7cea3-480">To close a case:</span></span>
  
1. <span data-ttu-id="7cea3-481">在安全性與合規性中心，按一下 [搜尋和調查]\*\*\*\* \> [電子文件探索]\*\*\*\*，來顯示貴組織中的案例清單。</span><span class="sxs-lookup"><span data-stu-id="7cea3-481">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="7cea3-482">按一下您想要關閉的大小寫的名稱。</span><span class="sxs-lookup"><span data-stu-id="7cea3-482">Click the name of the case that you want to close.</span></span>
    
    <span data-ttu-id="7cea3-483">會顯示 [**管理此例中**彈出式] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7cea3-483">The **Manage this case** flyout page is displayed.</span></span> 
    
3. <span data-ttu-id="7cea3-484">[**管理案例狀態**] 下按一下 [![移除 [預覽] 按鈕](media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif)**關閉案例**。</span><span class="sxs-lookup"><span data-stu-id="7cea3-484">Under **Manage case status**, click ![Remove the peek button](media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) **Close case**.</span></span>
    
    <span data-ttu-id="7cea3-485">預警案例相關聯的保留將已關閉顯示一則警告訊息。</span><span class="sxs-lookup"><span data-stu-id="7cea3-485">A warning is displayed saying that the holds associated with the case will be turned off.</span></span>
    
4. <span data-ttu-id="7cea3-486">按一下 [**是]** 以關閉 [大小寫。</span><span class="sxs-lookup"><span data-stu-id="7cea3-486">Click **Yes** to close the case.</span></span> 
    
    <span data-ttu-id="7cea3-487">在 [**管理此例中**彈出式頁面上的狀態會從**作用中**變更為**關閉**。</span><span class="sxs-lookup"><span data-stu-id="7cea3-487">The status on the **Manage this case** flyout page is changed from **Active** to **Closing**.</span></span>
    
5. <span data-ttu-id="7cea3-488">關閉 [**管理此例中**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7cea3-488">Close the **Manage this case** page.</span></span> 
    
6. <span data-ttu-id="7cea3-p185">在 [ **eDiscovery** ] 頁面上，按一下 [![重新整理] 圖示](media/O365-MDM-Policy-RefreshIcon.gif)**重新整理**更新關閉大小寫的狀態。可能需要最多 60 分鐘結束程序來完成。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p185">On the **eDiscovery** page, click ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) **Refresh** to update the status of the closed case. It might take up to 60 minutes for the closing process to complete.</span></span> 
    
    <span data-ttu-id="7cea3-p186">程序完成時，請大小寫的狀態變更為 「**已關閉**[ **eDiscovery** ] 頁面上。按一下 [大小寫一次以顯示 [**管理此例中**彈出式] 頁面，包含以下資訊時關閉案例和誰在關閉的名稱。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p186">When the process is complete, the status of the case is changed to **Closed** on the **eDiscovery** page. Click the name of the case again to display the **Manage this case** flyout page, which contains information about when the case was closed and who closed it.</span></span> 
     
## <a name="optional-step-10-re-open-a-closed-case"></a><span data-ttu-id="7cea3-493">（選用）步驟 10： 重新開啟關閉的案例</span><span class="sxs-lookup"><span data-stu-id="7cea3-493">(Optional) Step 10: Re-open a closed case</span></span>

<span data-ttu-id="7cea3-p187">當您重新開啟案例時，將不會自動恢復已備妥時關閉案例是任何保留。大小寫重新開啟後，您必須移至 [**保留**] 頁面上，並開啟先前保留。若要開啟保留，請選取其和詳細資料窗格中按一下 [**開啟**。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p187">When you reopen a case, any holds that were in place when the case was closed won't be automatically reinstated. After the case is reopened, you'll have to go to the **Hold** page and turn on the previous holds. To turn a hold on, select it and click **Turn it on** in the details pane.</span></span> 
  
1. <span data-ttu-id="7cea3-497">在安全性與合規性中心，按一下 [搜尋和調查]\*\*\*\* \> [電子文件探索]\*\*\*\*，來顯示貴組織中的案例清單。</span><span class="sxs-lookup"><span data-stu-id="7cea3-497">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="7cea3-498">按一下您想要重新開啟的大小寫的名稱。</span><span class="sxs-lookup"><span data-stu-id="7cea3-498">Click the name of the case that you want to reopen.</span></span>
    
    <span data-ttu-id="7cea3-499">會顯示 [**管理此例中**彈出式] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7cea3-499">The **Manage this case** flyout page is displayed.</span></span> 
    
3. <span data-ttu-id="7cea3-500">**管理案例的狀態**，請按一下 [**重新開啟案例**。</span><span class="sxs-lookup"><span data-stu-id="7cea3-500">Under **Manage case status**, click **Reopen case**.</span></span>
    
    <span data-ttu-id="7cea3-501">表示上次關閉時已與案例相關聯的保留將不會自動開啟顯示警告。</span><span class="sxs-lookup"><span data-stu-id="7cea3-501">A warning is displayed saying that the holds that were associated with the case when it was closed won't be turned on automatically.</span></span>
    
4. <span data-ttu-id="7cea3-502">按一下 [**是]** 以重新開啟大小寫。</span><span class="sxs-lookup"><span data-stu-id="7cea3-502">Click **Yes** to reopen the case.</span></span> 
    
    <span data-ttu-id="7cea3-503">在 [**管理此例中**彈出式頁面上的狀態會從**已關閉**變更為**使用中**。</span><span class="sxs-lookup"><span data-stu-id="7cea3-503">The status on the **Manage this case** flyout page is changed from **Closed** to **Active**.</span></span>
    
5. <span data-ttu-id="7cea3-504">關閉 [**管理此例中**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7cea3-504">Close the **Manage this case** page.</span></span> 
    
6. <span data-ttu-id="7cea3-p188">在 [ **eDiscovery** ] 頁面上，按一下 [![重新整理] 圖示](media/O365-MDM-Policy-RefreshIcon.gif)**重新整理**更新重新開啟大小寫的狀態。可能需要最多 60 分鐘，才可完成 reopening 程序。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p188">On the **eDiscovery** page, click ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) **Refresh** to update the status of the reopened case. It might take up to 60 minutes for the reopening process to complete.</span></span> 
    
    <span data-ttu-id="7cea3-507">程序完成時，大小寫的狀態變更為 [**作用中**[ **eDiscovery** ] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="7cea3-507">When the process is complete, the status of the case is changed to **Active** on the **eDiscovery** page.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="7cea3-508">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="7cea3-508">More information</span></span>

- <span data-ttu-id="7cea3-p189">**有 eDiscovery 案例或保留與 eDiscovery 案例相關聯的任何限制吗？** 下表列出 eDiscovery 案例] 和 [大小寫的保留的限制。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p189">**Are there any limits for eDiscovery cases or holds associated with an eDiscovery case?** The following table lists the limits for eDiscovery cases and case holds.</span></span>
    
  |<span data-ttu-id="7cea3-511">**限制說明**</span><span class="sxs-lookup"><span data-stu-id="7cea3-511">**Description of limit**</span></span>|<span data-ttu-id="7cea3-512">**限制**</span><span class="sxs-lookup"><span data-stu-id="7cea3-512">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="7cea3-513">為組織的情況下的最大數目</span><span class="sxs-lookup"><span data-stu-id="7cea3-513">Maximum number of cases for an organization</span></span>  <br/> |<span data-ttu-id="7cea3-514">無限制</span><span class="sxs-lookup"><span data-stu-id="7cea3-514">No limit</span></span>  <br/> |
  |<span data-ttu-id="7cea3-515">為組織保留最大數目大小寫</span><span class="sxs-lookup"><span data-stu-id="7cea3-515">Maximum number of case holds for an organization</span></span>  <br/> |<span data-ttu-id="7cea3-516">10,000</span><span class="sxs-lookup"><span data-stu-id="7cea3-516">10,000</span></span>  <br/> |
  |<span data-ttu-id="7cea3-517">單一 case 保留中的信箱數量上限</span><span class="sxs-lookup"><span data-stu-id="7cea3-517">Maximum number of mailboxes in a single case hold</span></span>  <br/> |<span data-ttu-id="7cea3-518">1,000</span><span class="sxs-lookup"><span data-stu-id="7cea3-518">1,000</span></span>  <br/> |
  |<span data-ttu-id="7cea3-519">與最大數目 SharePoint OneDrive 單一案例中的商務網站的保留</span><span class="sxs-lookup"><span data-stu-id="7cea3-519">Maximum number of SharePoint and OneDrive for Business sites in a single case hold</span></span>  <br/> |<span data-ttu-id="7cea3-520">100</span><span class="sxs-lookup"><span data-stu-id="7cea3-520">100</span></span>  <br/> |
   
- <span data-ttu-id="7cea3-p190">**因應在 [管理] 頁面上建立進階 ediscovery 的情況下？** 您可以按一下在 [ **eDiscovery** ] 頁面上的 [安全性] 下方的連結來存取較舊的進階的 eDiscovery 案例的清單&amp;規範中心。不過，執行較舊的案例中的任何工作，您必須連絡 Office 365 支援人員並要求大小寫要移至新的 eDiscovery 案例安全性&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p190">**What about cases that were created on the case management page in Advanced eDiscovery?** You can access a list of older Advanced eDiscovery cases by clicking the link at the bottom on the **eDiscovery** page in the Security &amp; Compliance Center. However, to do any work in an older case, you have to contact Office 365 Support and request that the case be moved to a new eDiscovery case in the Security &amp; Compliance Center.</span></span> 
    
- <span data-ttu-id="7cea3-p191">**為什麼要選擇建立 [eDiscovery 管理員？** 如先前清楚，系統管理員是可以檢視及存取您組織中所有的 eDiscovery 案例 eDiscovery 管理員角色群組的成員 eDiscovery。這項功能來存取所有的 eDiscovery 案例有兩個重要的用途：</span><span class="sxs-lookup"><span data-stu-id="7cea3-p191">**Why create an eDiscovery Administrator?** As previously explained, an eDiscovery Administrator is member of the eDiscovery Manager role group who can view and access all eDiscovery cases in your organization. This ability to access all the eDiscovery cases has two important purposes:</span></span>
    
  - <span data-ttu-id="7cea3-p192">如果 eDiscovery 案例的唯一成員的人員離開貴組織，因為他們未成員任何人 （包括組織管理角色群組的成員或另一個 eDiscovery 管理員角色群組的成員） 是可存取該 eDiscovery 案例案例。在此情況下，就會有任何方法，以存取案例中的資料。但 eDiscovery 管理員可以存取所有在組織中的 eDiscovery 案例，因為他們可以檢視案例安全性&amp;規範中心並將其本身或另一個 eDiscovery 管理員新增為大小寫的成員。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p192">If a person who is the only member of an eDiscovery case leaves your organization, no one (including members of the Organization Management role group or another member of the eDiscovery Manager role group) can access that eDiscovery case because they aren't a member of a case. In this situation, there would be no way to access the data in the case. But because an eDiscovery Administrator can access all eDiscovery cases in the organization, they can view the case in the Security &amp; Compliance Center and add themselves or another eDiscovery manager as a member of the case.</span></span>
    
  - <span data-ttu-id="7cea3-p193">EDiscovery 系統管理員可以檢視及存取所有的 eDiscovery 案例，因為他們可以稽核和監督所有案例和相關聯的內容搜尋。這有助於防止任何誤用內容搜尋或 eDiscovery 案例。與因為 eDiscovery 系統管理員可以存取內容的搜尋結果中的潛在敏感資訊，您應該限制的 eDiscovery 管理員的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p193">Because an eDiscovery Administrator can view and access all eDiscovery cases, they can audit and oversee all cases and associated Content Searches. This can help to prevent any misuse of Content Searches or eDiscovery cases. And because eDiscovery Administrators can access potentially sensitive information in the results of a Content Search, you should limit the number of people who are eDiscovery Administrators.</span></span>
    
    <span data-ttu-id="7cea3-p194">最後，如先前清楚、 eDiscovery 管理員可以在 [安全性]&amp;規範中心會自動新增為進階 ediscovery 的管理員。這表示 eDiscovery 管理員的人員可執行的使用者設定、 建立的情況下，並將資料新增到的情況下進階 eDiscovery 的管理工作。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p194">Finally, as previous explained, eDiscovery Administrators in the Security &amp; Compliance Center are automatically added as administrators in Advanced eDiscovery. That means a person who is an eDiscovery Administrator can perform administrative tasks in Advanced eDiscovery, such as setting up users, creating cases, and adding data to cases.</span></span>
    
- <span data-ttu-id="7cea3-p195">**授權的內容位置置於保留需求為何吗？** 一般而言，組織需要的 Office 365 E3 訂閱或更高的內容位置置於保留。若要將信箱就地保留，Exchange Online 計劃 2 授權，則需要針對您想要保留的信箱。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p195">**What are the licensing requirements to place content locations on hold?** In general, organizations require an Office 365 E3 subscription or higher to place content locations on hold. To place mailboxes on hold, an Exchange Online Plan 2 license is required for the mailbox you want to place on hold.</span></span>
    
- <span data-ttu-id="7cea3-p196">**還有什麼應該您了解在步驟 5 中搜尋所有案例的內容？** 如先前所述，您可以搜尋有已處於保留狀態的大小寫的內容位置。當您這麼做時，保留條件會比對的內容為 [搜尋]。如果沒有任何保留準則，將搜尋所有內容。如果內容上查詢式保留，只會比對這兩個保留準則 （放在步驟 4 中保留） 的內容及搜尋準則 （從步驟 5 中搜尋） 會傳回與搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p196">**What else should you know about searching all case content in Step 5?** As previously explained, you can search the content locations that have been placed on hold in the case. When you do this, only the content that matches the hold criteria is search. If there is no hold criteria, all content is searched. If contents are on a query-based hold, only the content that matches both hold criteria (from the hold placed in Step 4) and the search criteria (from the search in Step 5) is returned with the search results.</span></span>
    
    <span data-ttu-id="7cea3-543">以下是搜尋所有案例的內容時請牢記的一些其他事項：</span><span class="sxs-lookup"><span data-stu-id="7cea3-543">Here are some other things to keep in mind when searching all case content:</span></span>
    
  - <span data-ttu-id="7cea3-p197">如果內容的位置是在相同的案例中的多個保留的一部分，保留查詢來結合**OR**運算子時搜尋的內容位置，使用所有案例內容] 選項。同樣地，如果內容位置屬於兩個不同保留，其中一個是查詢為基礎而另一個是設為無限期保留 （其中的所有內容都處於保留狀態），則所有內容將會無限期保留因都是搜尋。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p197">If a content location is part of multiple holds within the same case, the hold queries are combined by an **OR** operator when you search that content location using the all case content option. Similarly, if a content location is part of two different holds, where one is query-based and the other is an infinite hold (where all content is placed on hold), then all content will be search because of the infinite hold.</span></span> 
    
  - <span data-ttu-id="7cea3-p198">如果內容搜尋是案例和您已設定要搜尋所有案例的內容，然後 （藉由新增或移除內容的位置或變更保留查詢） 變更保留這些變更更新的搜尋設定。不過，您必須重新執行搜尋之後保留變更來更新的搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p198">If a content search is for a case and you've configured it to search all case content and then you change a hold (by adding or removing a content location or changing the hold query), the search configuration is updated with those changes. However, you have to re-run the search after the hold is changed to update the search results.</span></span>
    
  - <span data-ttu-id="7cea3-p199">如果多個案例保留會放在 eDiscovery 案例中的內容位置且選取搜尋所有案例的內容、 關鍵字的搜尋查詢數目上限為 500。那是因為內容的搜尋將所有查詢式保留結合使用**OR**運算子。如果有超過 500 個關鍵字中合併保留查詢及內容的搜尋查詢，然後搜尋信箱中的所有內容，而不只是符合任何查詢為基礎的案例該內容保留。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p199">If multiple case holds are placed on a content location in an eDiscovery case and you select to search all case content, the maximum number of keywords for that search query is 500. That's because the content search combines all the query-based holds by using the **OR** operator. If there are more than 500 keywords in the combined hold queries and the content search query, then all content in the mailbox is searched, not just that content that matches the any of query-based case holds.</span></span> 
    
  - <span data-ttu-id="7cea3-551">如果 case 保留的**開啟**狀態，您仍然可以搜尋案例的內容位置在已開啟保留。</span><span class="sxs-lookup"><span data-stu-id="7cea3-551">If a case hold has a status of **Turning on**, you can still search the case content locations while the hold is being turned on.</span></span>
    
  - <span data-ttu-id="7cea3-p200">如先前所述，如果搜尋設定成搜尋所有案例的內容，則您不能包含搜尋如果您想要匯出的多個搜尋結果。如果搜尋設定成搜尋所有案例的內容，然後您必須將匯出的單一搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p200">As previously stated, if a search is configured to search all case content, then you can't include that search if you want to export the results of multiple searches. If a search is configured to search all case content, then you'll have to export the results of that single search.</span></span>
    
- <span data-ttu-id="7cea3-p201">**當信箱、 SharePoint 網站或保留 OneDrive 帳戶移至不同的區域在多個地理位置環境中，會保留仍適用於吗？** 在所有的情況下，仍會保留信箱、 網站或 OneDrive 帳戶中的內容。不過，保留統計資料不會再將會包含從已移至不同的區域的內容位置的項目。若要包含已移動的內容位置保留統計資料，您必須編輯保留及更新 URL （或之信箱的 SMTP 地址） 使內容位置再次隨附於保留統計資料。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p201">**If a mailbox, SharePoint site, or OneDrive account that is on hold is moved to a different region in a multi-geo environment, will the hold still apply?** In all cases, the content in a mailbox, site, or OneDrive account will still be retained. However, the hold statistics will no longer include items from a content location that's been moved to a different region. To include hold statistics for a content location that's been moved, you'll have to edit the hold and update the URL (or SMTP address of a mailbox) so that the content location is once again included in the hold statistics.</span></span> 
    
- <span data-ttu-id="7cea3-p202">**不住在 Office 365 群組及 Microsoft 小組中放置保留吗？** Office 365 群組之內建的 Microsoft 小組。因此，將其置於保留 eDiscovery 案例中是非常類似。將 Office 365 群組和上的 Microsoft 小組保留狀態時請記住下列事項。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p202">**What about placing a hold on Office 365 Groups and Microsoft Teams?** Microsoft Teams are built on Office 365 Groups. Therefore, placing them on hold in an eDiscovery case is very similar. Keep the following things in mind when placing Office 365 Groups and Microsoft Teams on hold.</span></span> 
    
  - <span data-ttu-id="7cea3-562">若要放置音樂位於 Office 365 群組及 Microsoft 小組中的內容，您必須指定的信箱與 SharePoint 網站的群組或小組與之相關聯。</span><span class="sxs-lookup"><span data-stu-id="7cea3-562">To place content located in Office 365 Groups and Microsoft Teams on hold, you have to specify the mailbox and SharePoint site that associated with a group or team.</span></span>
    
  - <span data-ttu-id="7cea3-p203">執行**Get UnifiedGroup** cmdlet 在 Exchange Online 中檢視 Office 365 群組或 Microsoft 小組的屬性。這是一個好方法來取得具有相關聯的 Office 365 群組或 Microsoft 小組網站的 URL。例如，下列命令會顯示所選的屬性名為資深領導小組 Office 365 群組：</span><span class="sxs-lookup"><span data-stu-id="7cea3-p203">Run the **Get-UnifiedGroup** cmdlet in Exchange Online to view properties for an Office 365 Group or Microsoft Team. This is a good way to get the URL for the site that's associated with an Office 365 Group or a Microsoft Team. For example, the following command displays selected properties for an Office 365 Group named Senior Leadership Team:</span></span> 
    
     ```
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl

     DisplayName            : Senior Leadership Team
     Alias                  : seniorleadershipteam
     PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
     SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > <span data-ttu-id="7cea3-566">若要執行**Get UnifiedGroup**指令程式，您必須指派 「 僅檢視收件者 」 角色在 Exchange Online 或角色群組的成員，已指派 「 僅檢視收件者 」 角色。</span><span class="sxs-lookup"><span data-stu-id="7cea3-566">To run the **Get-UnifiedGroup** cmdlet, you have to be assigned the View-Only Recipients role in Exchange Online or be a member of a role group that's assigned the View-Only Recipients role.</span></span> 
  
  - <span data-ttu-id="7cea3-p204">當使用者的信箱搜尋時，將不會搜尋所有 Office 365 群組或使用者為其成員的 Microsoft 小組。同樣地，當撥打 Office 365 群組或 Microsoft 小組保留，只有群組信箱和群組網站會放在保留;信箱和 OneDrive for Business 網站群組成員的不處於保留狀態除非您明確地將其新增保留。因此，如果您基於法律考量，保留上放置在 Office 365 群組或 Microsoft 小組需要考慮新增信箱和 OneDrive 商務網站的群組和小組成員在相同的音樂。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p204">When a user's mailbox is searched, any Office 365 Group or Microsoft Team that the user is a member of won't be searched. Similarly, when you place an Office 365 Group or Microsoft Team hold, only the group mailbox and group site are placed on hold; the mailboxes and OneDrive for Business sites of group members aren't placed on hold unless you explicitly add them to the hold. Therefore, if you the need to place an Office 365 Group or Microsoft Team on hold for a legal reasons, consider adding the mailboxes and OneDrive for Business sites for group and team members on the same hold.</span></span>
    
  - <span data-ttu-id="7cea3-p205">若要取得 Office 365 群組或 Microsoft 小組成員的清單，您可以檢視屬性**首頁\>群組**頁面上的 Office 365 系統管理中心。或者，您可以在 Exchange Online PowerShell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="7cea3-p205">To get a list of the members of a Office 365 Group or Microsoft Team, you can view the properties on the **Home \> Groups** page in the Office 365 admin center. Alternatively, you can run the following command in Exchange Online PowerShell:</span></span> 
    
      ```
      Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress 
      ```

    > [!NOTE]
    > <span data-ttu-id="7cea3-572">若要執行**Get UnifiedGroupLinks**指令程式，您必須指派 「 僅檢視收件者 」 角色在 Exchange Online 或角色群組的成員，已指派 「 僅檢視收件者 」 角色。</span><span class="sxs-lookup"><span data-stu-id="7cea3-572">To run the **Get-UnifiedGroupLinks** cmdlet, you have to be assigned the View-Only Recipients role in Exchange Online or be a member of a role group that's assigned the View-Only Recipients role.</span></span> 
  
  - <span data-ttu-id="7cea3-p206">屬於 Microsoft 小組通道的交談會儲存在具有 Microsoft 小組與相關聯的信箱。同樣地，小組成員共用通道中的檔案都會儲存在團隊的 SharePoint 網站上。因此，您必須將 Microsoft 小組信箱和 SharePoint 網站上的保留要保留交談和通道中的檔案。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p206">Conversations that are part of a Microsoft Teams channel are stored in the mailbox that's associated with the Microsoft Team. Similarly, files that team members share in a channel are stored on the team's SharePoint site. Therefore, you have to place the Microsoft Team mailbox and SharePoint site on hold to retain conversations and files in a channel.</span></span>
    
    <span data-ttu-id="7cea3-p207">或者，是 [聊天室] 清單中的 Microsoft 小組的一部分的交談會儲存在信箱的使用者參與交談。與使用者共用聊天交談中的檔案都會儲存在 OneDrive for Business 網站共用檔案的使用者。因此，您必須將個別使用者信箱並 OneDrive for Business 網站上按住保留交談和在 [聊天室] 清單中的檔案。這就是為什麼很好置於除了放置小組信箱 （及網站） 的 Microsoft 小組成員之信箱的保留音樂。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p207">Alternatively, conversations that are part of the Chat list in Microsoft Teams are stored in the mailbox of the user's who participate in the chat. And files that a user shares in Chat conversations are stored in the OneDrive for Business site of the user who shares the file. Therefore, you have to place the individual user mailboxes and OneDrive for Business sites on hold to retain conversations and files in the Chat list. That's why it's a good idea to place a hold on the mailboxes of members of a Microsoft Team in addition to placing the team mailbox (and site) on hold.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7cea3-p208">參與交談屬於 [聊天室] 清單中的 Microsoft 小組的使用者必須具有 （雲端） 的 Exchange Online 信箱以保留信箱處於 eDiscovery 保留狀態時的交談的交談。那是因為交談屬於 [聊天室] 清單會儲存在雲端架構信箱的交談參與者。如果交談參與者都不會有 Exchange Online 信箱，將不能夠保留交談的交談。例如，在 Exchange 混合部署，可能會能夠參與交談屬於 [聊天室] 清單中的 Microsoft 小組與內部部署信箱的使用者。但在此例中，從這些交談內容無法保留因為使用者沒有雲端架構信箱。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p208">Users who participate in conversations that are part of the Chat list in Microsoft Teams must have an Exchange Online (cloud-based) mailbox in order to retain chat conversations when the mailbox is placed on an eDiscovery hold. That's because conversations that are part of the Chat list are stored in the cloud-based mailboxes of the chat participants. If a chat participant doesn't have an Exchange Online mailbox, you won't be able to retain chat conversations. For example, in an Exchange hybrid deployment, users with an on-premises mailbox might be able to participate in conversations that are part of the Chat list in Microsoft Teams. However in this case, content from these conversation can't be retained because the users don't have cloud-based mailboxes.</span></span> 
  
  - <span data-ttu-id="7cea3-p209">每個 Microsoft 小組或小組通道包含 Wiki 筆記記錄與共同作業。Wiki 內容會自動儲存至含有.mht 格式的檔案。此檔案儲存在團隊的 SharePoint 網站上的小組 Wiki 資料文件庫。您可以利用音樂 Wiki 內容所保留上放置團隊的 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p209">Every Microsoft Team or team channel contains a Wiki for note-taking and collaboration. The Wiki content is automatically saved to a file with a .mht format. This file is stored in the Teams Wiki Data document library on the team's SharePoint site. You can place the content in the Wiki on hold by placing the team's SharePoint site on hold.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7cea3-p210">要保留的 Microsoft 小組或小組通道 Wiki 內容 （如果您保留上放置團隊的 SharePoint 網站） 的功能已於 2017 年 6 月 22 日發行。如果小組網站上保留，將啟動到期保留內容 wiki （英文）。不過，如果小組網站會保留與 Wiki 內容已遭刪除之前 2017 年 6 月 22 Wiki 內容已不會保留。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p210">The capability to retain Wiki content for a Microsoft Team or team channel (when you place the team's SharePoint site on hold) was released on June 22, 2017. If a team site is on hold, the Wiki content will be retained starting on that date. However, if a team site is on hold and the Wiki content was deleted before June 22, 2017, the Wiki content was not retained.</span></span> 
  
- <span data-ttu-id="7cea3-p211">**如何尋找 onedrive 的 URL 放商務網站？** 若要收集的 Url 清單 onedrive，如，因此您可以將其新增至保留或搜尋您組織中的商務網站相關聯 eDiscovery 案例，請參閱[建立您的組織中的所有 OneDrive 位置的清單](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a)。本文中的此指令碼會建立包含的所有 OneDrive 網站清單的文字檔案。若要執行此指令碼，您必須安裝及使用 SharePoint Online 管理命令介面。請務必附加至每個想要搜尋的 OneDrive 網站的組織的我的網站網域的 URL。這是包含您 OneDrive; 的網域例如， `https://contoso-my.sharepoint.com`。以下是使用者的 OneDrive 網站的 URL 範例： `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`。</span><span class="sxs-lookup"><span data-stu-id="7cea3-p211">**How do I find the URL for OneDrive for Business sites?** To collect a list of the URLs for the OneDrive for Business sites in your organization so you can add them to a hold or search associated with an eDiscovery case, see [Create a list of all OneDrive locations in your organization](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a). This script in this article creates a text file that contains a list of all OneDrive sites. To run this script, you'll have to install and use the SharePoint Online Management Shell. Be sure to append the URL for your organization's MySite domain to each OneDrive site that you want to search. This is the domain that contains all your OneDrive; for example,  `https://contoso-my.sharepoint.com`. Here's an example of a URL for a user's OneDrive site:  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`.</span></span>
