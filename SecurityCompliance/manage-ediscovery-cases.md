---
title: 管理 Office 365 安全性的 eDiscovery 案例&amp;規範中心
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 7/2/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 9a00b9ea-33fd-4772-8ea6-9d3c65e829e6
description: 使用 Office 365 安全性&amp;規範中心建立 eDiscovery 保留及來存取，並管理組織中的 eDiscovery 案例。
ms.openlocfilehash: 5be66419e19f9703be5dde3fad82837bda249b72
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526738"
---
# <a name="manage-ediscovery-cases-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="7332d-103">管理 Office 365 安全性的 eDiscovery 案例&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="7332d-103">Manage eDiscovery cases in the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="7332d-p101">您可以使用 eDiscovery 案例中 Office 365 安全性&amp;規範中心控制人員可以建立、 存取及管理組織中的 eDiscovery 案例。如果貴組織的 Office 365 E5 訂閱，也可以使用 eDiscovery 案例分析使用 Office 365 進階 eDiscovery 搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="7332d-p101">You can use eDiscovery cases in the Office 365 Security &amp; Compliance Center to control who can create, access, and manage eDiscovery cases in your organization. If your organization has an Office 365 E5 subscription, you can also use eDiscovery cases to analyze search results by using Office 365 Advanced eDiscovery.</span></span>
  
<span data-ttu-id="7332d-p102">EDiscovery 案例可讓您將成員新增至案例、 控制哪些類型的特定案例的成員可以執行、 置於保留的內容位置相關法律案例，並建立多個內容搜尋與單一案例的關聯的動作。您也可以與案例相關聯的任何內容搜尋結果匯出或準備分析進階在 eDiscovery 中搜尋結果。eDiscovery 案例是很好的方式來限制在組織中有存取特定的法律案例內容的搜尋及搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="7332d-p102">An eDiscovery case allows you to add members to a case, control what types of actions that specific case members can perform, place a hold on content locations relevant to a legal case, and associate multiple Content Searches with a single case. You can also export the results of any Content Search that is associated with a case or prepare search results for analysis in Advanced eDiscovery. eDiscovery cases are a good way to limit who has access to Content Searches and search results for a specific legal case in your organization.</span></span>
  
<span data-ttu-id="7332d-109">使用下列工作流程設定和安全性中使用 eDiscovery 案例&amp;規範中心] 及 [進階 eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="7332d-109">Use the following workflow to set up and use eDiscovery cases in the Security &amp; Compliance Center and Advanced eDiscovery.</span></span>
  
[<span data-ttu-id="7332d-110">步驟 1：將 eDiscovery 權限指派給潛在的案例成員</span><span class="sxs-lookup"><span data-stu-id="7332d-110">Step 1: Assign eDiscovery permissions to potential case members</span></span>](manage-ediscovery-cases.md#step1_1)
  
[<span data-ttu-id="7332d-111">步驟 2： 建立新的案例</span><span class="sxs-lookup"><span data-stu-id="7332d-111">Step 2: Create a new case</span></span>](manage-ediscovery-cases.md#step2_1)
  
[<span data-ttu-id="7332d-112">步驟 3： 將成員新增至案例</span><span class="sxs-lookup"><span data-stu-id="7332d-112">Step 3: Add members to a case</span></span>](manage-ediscovery-cases.md#step2a_1)
  
[<span data-ttu-id="7332d-113">步驟 4： 就地保留上的內容位置</span><span class="sxs-lookup"><span data-stu-id="7332d-113">Step 4: Place content locations on hold</span></span>](manage-ediscovery-cases.md#step3_1)
  
[<span data-ttu-id="7332d-114">步驟 5： 建立並執行與案例相關聯之內容搜尋</span><span class="sxs-lookup"><span data-stu-id="7332d-114">Step 5: Create and run a Content Search associated with a case</span></span>](manage-ediscovery-cases.md#step4_1)
  
[<span data-ttu-id="7332d-115">步驟 6： 匯出與案例相關聯之內容搜尋的結果</span><span class="sxs-lookup"><span data-stu-id="7332d-115">Step 6: Export the results of a Content Search associated with a case</span></span>](manage-ediscovery-cases.md#step5_1)
  
[<span data-ttu-id="7332d-116">步驟 7： 準備搜尋結果進階 ediscovery （英文）</span><span class="sxs-lookup"><span data-stu-id="7332d-116">Step 7: Prepare search results for Advanced eDiscovery</span></span>](manage-ediscovery-cases.md#step7_1)
  
<span data-ttu-id="7332d-117">[步驟 8： 移至 [進階 ediscovery 案例](manage-ediscovery-cases.md#gotoAeD_1)</span><span class="sxs-lookup"><span data-stu-id="7332d-117">[Step 8: Go to the case in Advanced eDiscovery](manage-ediscovery-cases.md#gotoAeD_1)</span></span>
  
[<span data-ttu-id="7332d-118">（選用）步驟 9： 關閉案例</span><span class="sxs-lookup"><span data-stu-id="7332d-118">(Optional) Step 9: Close a case</span></span>](manage-ediscovery-cases.md#closecase_1)
  
[<span data-ttu-id="7332d-119">（選用）步驟 10： 重新開啟關閉的案例</span><span class="sxs-lookup"><span data-stu-id="7332d-119">(Optional) Step 10: Re-open a closed case</span></span>](manage-ediscovery-cases.md#reopencase_1)
  
[<span data-ttu-id="7332d-120">其他資訊</span><span class="sxs-lookup"><span data-stu-id="7332d-120">More information</span></span>](manage-ediscovery-cases.md#moreinfo_1)
  
## <a name="step-1-assign-ediscovery-permissions-to-potential-case-members"></a><span data-ttu-id="7332d-121">步驟 1：將 eDiscovery 權限指派給潛在的案例成員</span><span class="sxs-lookup"><span data-stu-id="7332d-121">Step 1: Assign eDiscovery permissions to potential case members</span></span>
<span data-ttu-id="7332d-122"><a name="step1_1"> </a></span><span class="sxs-lookup"><span data-stu-id="7332d-122"></span></span>

<span data-ttu-id="7332d-p103">第一個步驟是將適當的 eDiscovery 相關權限指派給人員讓您可以將其新增至 eDiscovery 案例在步驟 2。您必須是 「 組織管理角色群組的成員 （或要指派的角色管理角色） Office 365 安全性&amp;規範中心指派 eDiscovery 權限。下列清單說明 eDiscovery 相關的角色群組安全性&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="7332d-p103">The first step is to assign the appropriate eDiscovery-related permissions to people so you can add them to an eDiscovery case in Step 2. You have to be a member of the Organization Management role group (or be assigned the Role Management role) in the Office 365 Security &amp; Compliance Center to assign eDiscovery permissions. The following list describes the eDiscovery-related role groups in the Security &amp; Compliance Center.</span></span>
  
- <span data-ttu-id="7332d-p104">**檢閱者**此角色群組具有最嚴格的 eDiscovery 相關權限。此群組的成員只能看到並在 [安全性] 中開啟 [ **eDiscovery** ] 頁面上的案例清單&amp;他們是成員的規範中心。他們無法建立的情況下，將成員新增至案例、 建立保留、 建立搜尋、 匯出搜尋結果或準備進階 eDiscovery 的結果。不過，成員可存取執行分析工作的進階 ediscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="7332d-p104">**Reviewer**This role group has the most restrictive eDiscovery-related permissions. Members of this group can only see and open the list of the cases on the **eDiscovery** page in the Security &amp; Compliance Center that they are members of. They can't create cases, add members to a case, create holds, create searches, export search results, or prepare results for Advanced eDiscovery. However, members can access cases in Advanced eDiscovery to perform analysis tasks.</span></span> 
    
- <span data-ttu-id="7332d-p105">**eDiscovery 管理員**此角色群組的成員可以建立與管理 eDiscovery 案例。他們可以新增和移除成員、 放置的內容上的位置保留、 建立及編輯與案例相關聯的內容搜尋]、 [匯出搜尋結果的內容，並準備分析進階在 eDiscovery 中搜尋結果。有兩個此角色群組中的子群組。這些子群組之間的差異根據範圍。</span><span class="sxs-lookup"><span data-stu-id="7332d-p105">**eDiscovery Manager**Members of this role group can create and manage eDiscovery cases. They can add and remove members, place content locations on hold, create and edit Content Searches associated with a case, export the results of a Content Search, and prepare search results for analysis in Advanced eDiscovery. There are two sub-groups in this role group. The difference between these subgroups is based on scope.</span></span>
    
  - <span data-ttu-id="7332d-p106">**eDiscovery 管理員**可以檢視及管理 eDiscovery 案例所建立或成員。如果另一個 eDiscovery 管理員會建立案例，但不會將第二個 eDiscovery 管理員新增為該案例的成員，第二個 eDiscovery 管理員將無法檢視或在 [安全性] 中開啟 [ **eDiscovery** ] 頁面上的大小寫&amp;規範中心。eDiscovery 管理員也可以存取他們的情況下執行分析工作的進階 ediscovery。</span><span class="sxs-lookup"><span data-stu-id="7332d-p106">**eDiscovery Manager**Can view and manage the eDiscovery cases they create or are a member of. If another eDiscovery Manager creates a case but doesn't add a second eDiscovery Manager as a member of that case, the second eDiscovery Manager won't be able to view or open the case on the **eDiscovery** page in the Security &amp; Compliance Center. eDiscovery Managers can also access their cases in Advanced eDiscovery to perform analysis tasks.</span></span> 
    
  - <span data-ttu-id="7332d-p107">**eDiscovery 管理員**可以執行 eDiscovery 管理員可以執行的所有管理工作。此外，eDiscovery 管理員可以：</span><span class="sxs-lookup"><span data-stu-id="7332d-p107">**eDiscovery Administrator**Can perform all case management tasks that an eDiscovery Manager can do. Additionally, an eDiscovery Administrator can:</span></span>
    
  - <span data-ttu-id="7332d-139">在 [ **eDiscovery** ] 頁面上檢視所列的所有案例。</span><span class="sxs-lookup"><span data-stu-id="7332d-139">View all cases that are listed on the **eDiscovery** page.</span></span> 
    
  - <span data-ttu-id="7332d-140">管理組織中的任何 eDiscovery 案例之後他們將自己新增為大小寫的成員。</span><span class="sxs-lookup"><span data-stu-id="7332d-140">Manage any eDiscovery case in the organization after they add themself as a member of the case.</span></span>
    
  - <span data-ttu-id="7332d-p108">執行進階 eDiscovery，例如處理案例資料以供分析、 設定案例，及從進階 eDiscovery 匯出資料的系統管理工作。這是因為 eDiscovery 安全性的系統管理員的人員&amp;規範中心會自動新增為進階 eDiscovery 的管理員。</span><span class="sxs-lookup"><span data-stu-id="7332d-p108">Perform administrative tasks in Advanced eDiscovery, such as processing case data for analysis, configuring case settings, and exporting data from Advanced eDiscovery. This is because a person who is an eDiscovery Administrator in the Security &amp; Compliance Center is automatically added as an administrator in Advanced eDiscovery.</span></span>
    
    <span data-ttu-id="7332d-143">請參閱[More information](manage-ediscovery-cases.md#moreinfo_1)一節以了解為何您可能希望組織中有 eDiscovery 系統管理員的原因。</span><span class="sxs-lookup"><span data-stu-id="7332d-143">See the [More information](manage-ediscovery-cases.md#moreinfo_1) section for reasons why you may want an eDiscovery Administrator in your organization.</span></span> 
    
> [!IMPORTANT]
> <span data-ttu-id="7332d-144">如果使用者不是其中一個這些 eDiscovery 相關的角色群組的成員或不是已指派的檢閱者 」 角色的角色群組的成員，您無法將其新增為 eDiscovery 案例的成員。</span><span class="sxs-lookup"><span data-stu-id="7332d-144">If a person isn't a member of one of these eDiscovery-related role groups, or isn't a member of a role group that's assigned the Reviewer role, you can't add them as a member of an eDiscovery case.</span></span> 
  
 <span data-ttu-id="7332d-145">**若要指派 eDiscovery 權限：**</span><span class="sxs-lookup"><span data-stu-id="7332d-145">**To assign eDiscovery permissions:**</span></span>
  
1. <span data-ttu-id="7332d-146">移至 [ [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="7332d-146">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="7332d-147">登入 Office 365 中，使用您工作或學校的帳戶。</span><span class="sxs-lookup"><span data-stu-id="7332d-147">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="7332d-148">安全性&amp;規範中心 [**權限**，然後再執行作業根據想要指定 eDiscovery 權限的下列其中之一。</span><span class="sxs-lookup"><span data-stu-id="7332d-148">In the Security &amp; Compliance Center, click **Permissions**, and then do one of the following based on the eDiscovery permissions that you want to assign.</span></span>
    
  - <span data-ttu-id="7332d-p109">若要指定檢閱者權限，選取 「**檢閱者**」 角色群組，然後按一下 [**成員**] 旁的 [**編輯**。依序按一下 [**選擇成員**、![新增圖示](media/ITPro-EAC-AddIcon.gif)**新增**選取您要新增至 「 檢閱者 」 角色群組、 使用者] 和 [**新增]**。</span><span class="sxs-lookup"><span data-stu-id="7332d-p109">To assign Reviewer permissions, select the **Reviewer** role group, and then next to **Members** click **Edit**. Click **Choose members**, click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **Add** select the user that you want to add to the Reviewer role group, and then click **Add**.</span></span>
    
  - <span data-ttu-id="7332d-p110">若要指派 eDiscovery 管理員權限，選取**eDiscovery 管理員**角色群組中，，然後按一下 [ **eDiscovery 管理員**旁的 [**編輯**。依序按一下 [**選擇 eDiscovery 管理員**、![新增圖示](media/ITPro-EAC-AddIcon.gif)* * 新增 * *、 選取您要新增 eDiscovery 管理員] 中，為該使用者，然後按一下 [**新增]**。</span><span class="sxs-lookup"><span data-stu-id="7332d-p110">To assign eDiscovery Manager permissions, select the **eDiscovery Manager** role group, and then next to **eDiscovery Manager**, click **Edit**. Click **Choose eDiscovery Manager**, click ![Add Icon](media/ITPro-EAC-AddIcon.gif) ** Add **, select the user that you want to add as an eDiscovery Manager, and then click **Add**.</span></span>
    
  - <span data-ttu-id="7332d-p111">若要指派 eDiscovery 管理員權限，請選取**eDiscovery 管理員**角色群組，然後按一下 [ **eDiscovery 管理員**旁的 [**編輯**。依序按一下 [**選擇 eDiscovery 管理員**、![新增圖示](media/ITPro-EAC-AddIcon.gif)**新增**]，選取您要新增為 eDiscovery 管理員的使用者，然後按一下 [**新增]**。</span><span class="sxs-lookup"><span data-stu-id="7332d-p111">To assign eDiscovery Administrator permissions, select the **eDiscovery Manager** role group, and then next to **eDiscovery Administrator**, click **Edit**. Click **Choose eDiscovery Administrator**, click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **Add**, select the user that you want to add as an eDiscovery Administrator, and then click **Add**.</span></span>
    
4. <span data-ttu-id="7332d-155">您已新增的所有使用者之後，請按一下 [**完成**]、 按一下 [**儲存**] 以將所做的變更儲存到角色群組中，然後按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="7332d-155">After you've added all the users, click **Done**, click **Save** to save the changes to the role group, and then click **Close**.</span></span>
    
[<span data-ttu-id="7332d-156">回到頁首</span><span class="sxs-lookup"><span data-stu-id="7332d-156">Return to top</span></span>](manage-ediscovery-cases.md#top)
  
## <a name="step-2-create-a-new-case"></a><span data-ttu-id="7332d-157">步驟 2： 建立新的案例</span><span class="sxs-lookup"><span data-stu-id="7332d-157">Step 2: Create a new case</span></span>
<span data-ttu-id="7332d-158"><a name="step2_1"> </a></span><span class="sxs-lookup"><span data-stu-id="7332d-158"></span></span>

<span data-ttu-id="7332d-p112">下一步是建立新的 eDiscovery 案例。您必須是要建立 eDiscovery 案例的 eDiscovery 管理員角色群組的成員。如先前清楚，您在 [安全性] 建立新案例之後&amp;規範中心、 您 （和其他案例的成員） 將能夠存取進階 eDiscovery 如果您組織中的相同案例具有 Office 365 E5 訂閱。</span><span class="sxs-lookup"><span data-stu-id="7332d-p112">The next step is to create a new eDiscovery case. You must be a member of the eDiscovery Managers role group to create eDiscovery cases. As previously explained, after you create a new case in the Security &amp; Compliance Center, you (and other case members) will be able to access that same case in Advanced eDiscovery if you're organization has an Office 365 E5 subscription.</span></span>
  
1. <span data-ttu-id="7332d-162">移至 [ [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="7332d-162">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="7332d-163">登入 Office 365 中，使用您工作或學校的帳戶。</span><span class="sxs-lookup"><span data-stu-id="7332d-163">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="7332d-164">安全性&amp;規範中心，按一下 [**搜尋&amp;調查** \> **eDiscovery**，然後按一下 [![新增圖示](media/ITPro-EAC-AddIcon.gif)**建立案例**。</span><span class="sxs-lookup"><span data-stu-id="7332d-164">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery**, and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **Create a case**.</span></span>
    
4. <span data-ttu-id="7332d-p113">在 [**新案例**] 頁面提供大小寫的名稱、 輸入選用描述，和 [**儲存**。請注意大小寫的名稱必須是唯一您組織中。</span><span class="sxs-lookup"><span data-stu-id="7332d-p113">On the **New Case** page, give the case a name, type an optional description, and then click **Save**. Note that the case name must be unique in your organization.</span></span>
    
    ![新案例的頁面](media/538f66b8-eb6e-4c4c-83d8-7154fd85883a.png)
  
    <span data-ttu-id="7332d-p114">新的案例會顯示在 [ **eDiscovery** ] 頁面上的情況下的清單中。您可以將游標滑鼠停留在來顯示關於情況下，包括] （**使用中**或**已關閉**） 的大小寫的狀態資訊的案例名稱的附註的 （也就在上一個步驟中建立） 的情況下，描述與大小寫當上次變更及誰已變更它。</span><span class="sxs-lookup"><span data-stu-id="7332d-p114">The new case is displayed in the list of cases on the **eDiscovery** page. Note that you can hover the cursor over a case name to display information about the case, including the status of the case ( **Active** or **Closed**), the description of the case (that was created in the previous step), and when the case was changed last and who changed it.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="7332d-p115">建立新案例之後，您可以隨時命名。只要按一下在 [ **eDiscovery** ] 頁面的大小寫的名稱。在 [**管理此例中**彈出式] 頁面變更 [**名稱**] 方塊中顯示的名稱並儲存變更。</span><span class="sxs-lookup"><span data-stu-id="7332d-p115">After you create a new case, you can rename it anytime. Just click the name of the case on the **eDiscovery** page. On the **Manage this case** flyout page, change the name displayed in the box under **Name**, and then save the change.</span></span> 
  
[<span data-ttu-id="7332d-173">回到頁首</span><span class="sxs-lookup"><span data-stu-id="7332d-173">Return to top</span></span>](manage-ediscovery-cases.md#top)
  
## <a name="step-3-add-members-to-a-case"></a><span data-ttu-id="7332d-174">步驟 3： 將成員新增至案例</span><span class="sxs-lookup"><span data-stu-id="7332d-174">Step 3: Add members to a case</span></span>
<span data-ttu-id="7332d-175"><a name="step2a_1"> </a></span><span class="sxs-lookup"><span data-stu-id="7332d-175"></span></span>

<span data-ttu-id="7332d-p116">建立新案例之後下, 一步是將成員新增至大小寫。如先前所述的檢閱者的成員的使用者或 eDiscovery 管理員角色群組可新增為大小寫的成員。請注意 eDiscovery 管理員建立案例會自動新增為成員。</span><span class="sxs-lookup"><span data-stu-id="7332d-p116">After you create a new case, the next step is to add members to the case. As previous explained, only users that are members of the Reviewer or eDiscovery Manager role groups can be added as a member of the case. Note that the eDiscovery Manager who created the case is automatically added as a member.</span></span>
  
1. <span data-ttu-id="7332d-179">安全性&amp;規範中心，按一下 [**搜尋&amp;調查** \> **eDiscovery**可在組織中顯示的情況下的清單。</span><span class="sxs-lookup"><span data-stu-id="7332d-179">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="7332d-180">按一下您想要將成員新增至的大小寫的名稱。</span><span class="sxs-lookup"><span data-stu-id="7332d-180">Click the name of the case that you want to add members to.</span></span>
    
    <span data-ttu-id="7332d-181">會顯示 [**管理此例中**彈出式] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7332d-181">The **Manage this case** flyout page is displayed.</span></span> 
    
    ![按一下案例名稱以顯示 [管理此案例的頁面](media/2364dc08-a3dc-4724-acf4-7a68c8588e6f.png)
  
3. <span data-ttu-id="7332d-183">在 [**管理成員**、 下方按一下 [![新增圖示](media/ITPro-EAC-AddIcon.gif)**新增**成員新增到大小寫。</span><span class="sxs-lookup"><span data-stu-id="7332d-183">Under **Manage members**, click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **Add** to add members to the case.</span></span> 
    
4. <span data-ttu-id="7332d-184">在可新增為的大小寫成員的人員清單中，按一下您想要新增至案例的人員名稱旁的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="7332d-184">In the list of people who can be added as a member of the case, click the checkbox next to the name of the people you want to add to the case.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="7332d-185">如果您有大型的人員可新增為成員的清單，可用於**搜尋**方塊的清單中的特定人員搜尋。</span><span class="sxs-lookup"><span data-stu-id="7332d-185">If you have a large list of people who can added as members, use the **Search** box to search for a specific person in the list.</span></span> 
  
5. <span data-ttu-id="7332d-186">您已選取加入群組之成員的人員之後，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="7332d-186">After you've selected the people to add as members of the group, click **Add**.</span></span>
    
    <span data-ttu-id="7332d-187">在 [**管理此例中**，按一下 [**儲存**] 以儲存新案例成員的清單。</span><span class="sxs-lookup"><span data-stu-id="7332d-187">In **Manage this case**, click **Save** to save the new list of case members.</span></span> 
    
6. <span data-ttu-id="7332d-188">按一下 [**儲存**] 以儲存新案例成員的清單。</span><span class="sxs-lookup"><span data-stu-id="7332d-188">Click **Save** to save the new list of case members.</span></span> 
    
[<span data-ttu-id="7332d-189">回到頁首</span><span class="sxs-lookup"><span data-stu-id="7332d-189">Return to top</span></span>](manage-ediscovery-cases.md#top)
  
## <a name="step-4-place-content-locations-on-hold"></a><span data-ttu-id="7332d-190">步驟 4： 就地保留上的內容位置</span><span class="sxs-lookup"><span data-stu-id="7332d-190">Step 4: Place content locations on hold</span></span>
<span data-ttu-id="7332d-191"><a name="step3_1"> </a></span><span class="sxs-lookup"><span data-stu-id="7332d-191"></span></span>

<span data-ttu-id="7332d-p117">您可以使用 eDiscovery 案例來建立保留来保留可能案例相關的內容。您可以置於保留信箱和 OneDrive 商務網站的是 custodians 案例中的人員。您也可以將保留群組信箱、 SharePoint 網站及 OneDrive 商務網站的 Office 365 群組。同樣地，您可以利用保留對信箱和相關聯的 Microsoft 小組網站。當您保留上放置的內容位置時，內容會保留直到您移除保留內容的位置或直到您刪除保留。</span><span class="sxs-lookup"><span data-stu-id="7332d-p117">You can use an eDiscovery case to create holds to preserve content that might be relevant to the case. You can place a hold on the mailboxes and OneDrive for Business sites of people who are custodians in the case. You can also place a hold on the group mailbox, SharePoint site, and OneDrive for Business site for an Office 365 Group. Similarly, you can place a hold on the mailbox and site that are associated with Microsoft Teams. When you place content locations on hold, content is held until you remove the hold from the content location or until you delete the hold.</span></span>
  
<span data-ttu-id="7332d-197">當您建立保留時，您有下列選項的範圍會保留在指定的內容位置的內容：</span><span class="sxs-lookup"><span data-stu-id="7332d-197">When you create a hold, you have the following options to scope the content that is held in the specified content locations:</span></span>
  
- <span data-ttu-id="7332d-p118">您建立的所有內容都處於保留狀態設為無限期保留。或者，您可以建立查詢式的保留僅符合內容的搜尋查詢處於保留狀態。</span><span class="sxs-lookup"><span data-stu-id="7332d-p118">You create an infinite hold where all content is placed on hold. Alternatively, you can create a query-based hold where only content that matches a search query is placed on hold.</span></span>
    
- <span data-ttu-id="7332d-p119">您可以指定日期範圍，以保留已傳送、 接收到，或建立的日期範圍內的內容。或者，您可以保留不論當它已傳送、 接收到，或建立的所有內容。</span><span class="sxs-lookup"><span data-stu-id="7332d-p119">You can specify a date range to hold only the content that was sent, received, or created within that date range. Alternatively, you can hold all content regardless of when it was sent, received, or created.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7332d-202">您可以將最多 10000 個跨所有組織中的 eDiscovery 案例與保留原則。</span><span class="sxs-lookup"><span data-stu-id="7332d-202">You can have a maximum of 10,000 hold policies across all eDiscovery cases in your organization.</span></span> 
  
<span data-ttu-id="7332d-203">若要建立保留 eDiscovery 案例：</span><span class="sxs-lookup"><span data-stu-id="7332d-203">To create a hold for an eDiscovery case:</span></span>
  
1. <span data-ttu-id="7332d-204">安全性&amp;規範中心，按一下 [**搜尋&amp;調查** \> **eDiscovery**可在組織中顯示的情況下的清單。</span><span class="sxs-lookup"><span data-stu-id="7332d-204">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="7332d-205">按一下您想要建立的保留案例] 旁的 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="7332d-205">Click **Open** next to the case that you want to create the holds in.</span></span> 
    
3. <span data-ttu-id="7332d-206">在 [**首頁**] 頁面的大小寫上按一下 [**保留**]。</span><span class="sxs-lookup"><span data-stu-id="7332d-206">On the **Home** page for the case, click **Hold**.</span></span>
    
    ![按一下 [顯示 [案件保留] 頁面的 [保留]。](media/25c0300a-bd33-4443-a121-d595b1a3e00f.png)
  
4. <span data-ttu-id="7332d-208">在 [**保留**] 頁面上，按一下 [**新增**![新增圖示](media/ITPro-EAC-AddIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="7332d-208">On the **Hold** page, click **New**![Add Icon](media/ITPro-EAC-AddIcon.gif).</span></span>
    
5. <span data-ttu-id="7332d-p120">在 [**建立新的保留**] 頁面上提供保留的名稱。保留名稱必須是在組織中唯一的。</span><span class="sxs-lookup"><span data-stu-id="7332d-p120">On the **Create a new hold** page, give the hold a name. The name of the hold must be unique in your organization.</span></span> 
    
6. <span data-ttu-id="7332d-p121">選擇您想要進行的內容位置保留。您可以在保留上放置信箱、 網站及公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="7332d-p121">Choose the content locations that you want to place on hold. You can place mailboxes, sites, and public folders on hold.</span></span>
    
    ![選擇要保留的內容位置](media/a00c952c-f91f-4708-b5a4-6213e4c413c7.png)
  
1. <span data-ttu-id="7332d-p122">**信箱**按一下 [**新增**![新增圖示](media/ITPro-EAC-AddIcon.gif)來指定要保留信箱。使用 [搜尋] 方塊中找到使用者信箱使用者和通訊群組 （置於群組成員的信箱保留） 至保留。您也可撥打相關聯的信箱上的保留供 Office 365 群組或 Microsoft 小組。</span><span class="sxs-lookup"><span data-stu-id="7332d-p122">**Mailboxes** Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.gif) to specify mailboxes to place on hold. Use the search box to find user mailboxes and distribution groups (to place a hold on the mailboxes of group members) to place on hold. You can also place a hold on the associated mailbox for an Office 365 Group or a Microsoft Team.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="7332d-p123">當您按一下 [**新增**![新增圖示](media/ITPro-EAC-AddIcon.gif)來指定要保留信箱，會顯示信箱選擇是空的。這是由設計，以提升效能。若要將人員新增至這份清單，在搜尋方塊中輸入的名稱 （至少要有 3 個字元） 並按一下 [**搜尋**]![搜尋圖示](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif)。</span><span class="sxs-lookup"><span data-stu-id="7332d-p123">When you click **Add**![Add Icon](media/ITPro-EAC-AddIcon.gif) to specify mailboxes to place on hold, the mailbox picker that's displayed is empty. This is by design to enhance performance. To add people to this list, type a name (a minimum of 3 characters) in the search box and click **Search**![Search icon](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif).</span></span> 
  
2. <span data-ttu-id="7332d-p124">**網站**按一下 [**新增**![新增圖示](media/ITPro-EAC-AddIcon.gif)指定 SharePoint 和 OneDrive for Business 網站保留。輸入您想要保留每個網站的 URL。您也可以針對 Office 365 群組或 Microsoft 小組新增 SharePoint 網站的 URL。</span><span class="sxs-lookup"><span data-stu-id="7332d-p124">**Sites** Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.gif) to specify SharePoint and OneDrive for Business sites to place on hold. Type the URL for each site that you want to place on hold. You can also add the URL for the SharePoint site for an Office 365 Group or a Microsoft Team.</span></span> 
    
<span data-ttu-id="7332d-p125"><<<<<<< 標題請參閱[管理 Office 365 安全性的 eDiscovery 案例&amp;規範中心](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da#moreinfo_1)] 區段中放入保留的 Office 365 群組及 Microsoft 小組的秘訣。=== 查看[詳細資訊](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da.aspx#moreinfo_1)] 區段中放入保留的 Office 365 群組及 Microsoft 小組的秘訣。</span><span class="sxs-lookup"><span data-stu-id="7332d-p125"><<<<<<< HEAD See the [Manage eDiscovery cases in the Office 365 Security &amp; Compliance Center](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da#moreinfo_1) section for tips on putting Office 365 Groups and Microsoft Teams on hold. ======= See the [More information](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da.aspx#moreinfo_1) section for tips on putting Office 365 Groups and Microsoft Teams on hold.</span></span> 
>>>>>>> <span data-ttu-id="7332d-225">deniseb 轉換</span><span class="sxs-lookup"><span data-stu-id="7332d-225">deniseb-conversion</span></span>
    
    > [!NOTE]
    > In the rare case that a person's user principal name (UPN) is changed, the URL for their OneDrive account will also be changed to incorporate the new UPN. If this happens, you'll have to modify the hold by adding the user's new OneDrive URL and removing the old one. 
  
3. <span data-ttu-id="7332d-p126">**公用資料夾**按一下 [將所有的公用資料夾放在您 Exchange Online 組織上的保留**保留所有公用資料夾**。請注意，您無法選擇特定公用資料夾遷移至放入保留。維持**不保留任何公用資料夾**選取選項如果您不想將放在公用資料夾的保留。</span><span class="sxs-lookup"><span data-stu-id="7332d-p126">**Public folders** Click **Hold all public folders** to put all of the public folders in your Exchange Online organization on hold. Note that you can't choose specific public folders to put on hold. Leave the **Don't hold any public folders** option selected if you don't want to put a hold on public folders.</span></span> 
    
7. <span data-ttu-id="7332d-229">當您完成新增至保留的內容位置時，按一下 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="7332d-229">When you're done adding content locations to the hold, click **Next**.</span></span>
    
8. <span data-ttu-id="7332d-p127">若要建立條件查詢式保留，請完成下列設定。否則，只要按一下 [**完成**] 以保留所有內容。</span><span class="sxs-lookup"><span data-stu-id="7332d-p127">To create a query-based hold with conditions, complete the following. Otherwise, just click **Finish** to hold all content.</span></span> 
    
    ![藉由指定的關鍵字與條件建立查詢式保留](media/a5bb802e-2e96-4f12-8b33-1ddd671638e4.png)
  
    <span data-ttu-id="7332d-233">如需建立搜尋查詢和使用情況的詳細資訊，請參閱[關鍵字查詢和搜尋條件的內容搜尋](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="7332d-233">For more information about creating a search query and using conditions, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
    
1. <span data-ttu-id="7332d-p128">在下] 方塊中**您想什麼我們要尋找的？**，以便符合搜尋準則的內容處於保留狀態] 方塊中輸入搜尋查詢。您可以指定關鍵字、 郵件內容或文件屬性，例如檔案名稱。您也可以使用較複雜布林運算子，例如**AND**、 **OR**，或**未**使用的查詢。如果您遺漏保留空白，則將會位於指定之內容的位置中的所有內容都放在 [關鍵字] 方塊。</span><span class="sxs-lookup"><span data-stu-id="7332d-p128">In the box under **What do you want us to look for?**, type a search query in the box so that only the content that meets the search criteria is placed on hold. You can specify keywords, message properties, or document properties, such as file names. You can also use more complex queries that use a Boolean operator, such as **AND**, **OR**, or **NOT**. If you leave the keyword box empty, then all content located in the specified content locations will be placed on hold.</span></span> 
    
2. <span data-ttu-id="7332d-p129">**條件**，按一下 [新增一或多個條件，縮減保留搜尋查詢的 [**新增條件**]。每個條件將子句新增至 KQL 搜尋查詢，建立及執行當您建立保留。例如您可以指定日期範圍，讓電子郵件或站台建立日期範圍內的文件會處於保留狀態。條件是以邏輯方式連線到 （在 [關鍵字] 方塊中指定） 的關鍵字查詢**和**運算子。表示項目必須滿足的關鍵字查詢及可放置在此條件就會保留。</span><span class="sxs-lookup"><span data-stu-id="7332d-p129">Under **Conditions**, click **Add condition** to add one or more conditions to narrow the search query for the hold. Each condition adds a clause to the KQL search query that is created and run when you create the hold. For example you can specify a date range so that email or site documents that were created within the date ranged are placed on hold. A condition is logically connected to the keyword query (specified in the keyword box) by the **AND** operator. That means that items have to satisfy both the keyword query and the condition to be placed on hold.</span></span> 
    
9. <span data-ttu-id="7332d-243">設定查詢式之後保留，按一下 [**完成**] 來建立保留。</span><span class="sxs-lookup"><span data-stu-id="7332d-243">After configuring a query-based hold, click **Finish** to create the hold.</span></span> 
    
[<span data-ttu-id="7332d-244">回到頁首</span><span class="sxs-lookup"><span data-stu-id="7332d-244">Return to top</span></span>](manage-ediscovery-cases.md#top)
  
### <a name="hold-statistics"></a><span data-ttu-id="7332d-245">保留的統計資料</span><span class="sxs-lookup"><span data-stu-id="7332d-245">Hold statistics</span></span>

<span data-ttu-id="7332d-p130">While 後的新保留的相關資訊會顯示所選保留的 [**保留**] 頁面的詳細資料窗格中。此資訊包含的信箱數目上的網站保留與已對內容的相關的統計資料保留，例如處於保留狀態的總人數及的項目大小和上次所計算的統計資料的保留。這些保留統計值能協助您識別要保留多少 eDiscovery 案例相關的內容。</span><span class="sxs-lookup"><span data-stu-id="7332d-p130">After a while, information about the new hold is displayed in the details pane on the **Holds** page for the selected hold. This information includes the number of mailboxes and sites on hold and statistics about the content that was placed on hold, such as the total number and size of items placed on hold and the last time the hold statistics were calculated. These hold statistics help you identify how much content that's related to the eDiscovery case is being held.</span></span> 
  
![保留選取保留在詳細資料窗格中顯示的統計資料](media/e46359a3-cba1-4771-bbf5-bc53b4a2cb14.png)
  
<span data-ttu-id="7332d-250">保留有關保留統計資料記住下列事項：</span><span class="sxs-lookup"><span data-stu-id="7332d-250">Keep the following things in mind about hold statistics:</span></span>
  
- <span data-ttu-id="7332d-p131">保留的項目數總計會指出從保留的所有內容來源的項目數。如果您已建立查詢式保留功能，這次統計指出符合查詢的項目數。</span><span class="sxs-lookup"><span data-stu-id="7332d-p131">The total number of items on hold indicates the number of items from all content sources that are placed on hold. If you've created a query-based hold, this statistic indicates the number of items that match the query.</span></span>
    
- <span data-ttu-id="7332d-p132">保留的項目數也包含編製索引的內容位置中找到的項目。如果您建立查詢式保留，內容的位置中的所有編製索引項目會放在保留的記事。這包括編製索引的項目不符合搜尋準則的查詢式保留及編製索引的項目可能屬於以外的日期範圍條件。這是與當您執行內容搜尋] 中編製索引的項目已不符合搜尋查詢或排除的日期範圍條件不包含在搜尋結果中有什麼不同。如需編製索引項目的詳細資訊，請參閱[編製索引的項目中的 Office 365 中的內容搜尋](partially-indexed-items-in-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="7332d-p132">The number of items on hold also includes unindexed items found in the content locations. Note that if you create a query-based hold, all unindexed items in the content locations are placed on hold. This includes unindexed items that don't match the search criteria of a query-based hold and unindexed items that might fall outside of a date range condition. This is different than what happens when you run a Content Search, in which unindexed items that don't match the search query or are excluded by a date range condition aren't included in the search results. For more information about unindexed items, see [Unindexed items in Content Search in Office 365](partially-indexed-items-in-content-search.md).</span></span>
    
- <span data-ttu-id="7332d-p133">您可以取得最新保留按一下 [重新執行搜尋的 [**更新統計資料**的統計資料評估的計算目前保留的項目數。若有必要，請按一下 [**重新整理**![重新整理] 圖示](media/O365-MDM-Policy-RefreshIcon.gif)要更新的詳細資料窗格中的保留統計資料工具列中。</span><span class="sxs-lookup"><span data-stu-id="7332d-p133">You can get the latest hold statistics by clicking **Update statistics** to re-run a search estimate that calculates the current number of items on hold. If necessary, click **Refresh**![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) in the toolbar to update the hold statistics in the details pane.</span></span> 
    
- <span data-ttu-id="7332d-260">因為其信箱或網站會保留使用者通常會傳送或接收新的電子郵件訊息和建立新的 SharePoint 和 OneDrive for Business 文件增加一段時間保留它的一般上的項目數目。</span><span class="sxs-lookup"><span data-stu-id="7332d-260">It's normal for the number of items on hold to increase over time because users whose mailbox or site is on hold are typically sending or receiving new email message and creating new SharePoint and OneDrive for Business documents.</span></span>
    
[<span data-ttu-id="7332d-261">回到頁首</span><span class="sxs-lookup"><span data-stu-id="7332d-261">Return to top</span></span>](manage-ediscovery-cases.md#top)
  
## <a name="step-5-create-and-run-a-content-search-associated-with-a-case"></a><span data-ttu-id="7332d-262">步驟 5： 建立並執行與案例相關聯之內容搜尋</span><span class="sxs-lookup"><span data-stu-id="7332d-262">Step 5: Create and run a Content Search associated with a case</span></span>
<span data-ttu-id="7332d-263"><a name="step4_1"> </a></span><span class="sxs-lookup"><span data-stu-id="7332d-263"></span></span>

<span data-ttu-id="7332d-p134">建立 eDiscovery 案例並與案例相關的任何 custodians 處於保留狀態之後，您可建立並執行一或多個內容搜尋與案例相關聯。內容與案例相關聯的搜尋未列在安全性中的 [**搜尋**] 頁面上&amp;規範中心。內容搜尋相關聯的大小寫這表示只可以存取來區分成員能夠同時 eDiscovery 管理員角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="7332d-p134">After an eDiscovery case is created and any custodians related to the case are placed on hold, you can create and run one or more Content Searches that are associated with the case. Content Searches associated with a case aren't listed on the **Search** page in the Security &amp; Compliance Center. This means that Content Searches associated with a case can only be accessed by case members who are also members of the eDiscovery Manager role group.</span></span> 
  
1. <span data-ttu-id="7332d-267">安全性&amp;規範中心，按一下 [**搜尋&amp;調查** \> **eDiscovery**可在組織中顯示的情況下的清單。</span><span class="sxs-lookup"><span data-stu-id="7332d-267">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="7332d-268">按一下 [大小寫您要建立的內容搜尋] 旁的 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="7332d-268">Click **Open** next to the case that you want to create a Content Search in.</span></span> 
    
3. <span data-ttu-id="7332d-269">在 [**首頁**] 頁面的大小寫上按一下 [**搜尋**]。</span><span class="sxs-lookup"><span data-stu-id="7332d-269">On the **Home** page for the case, click **Search**.</span></span>
    
    ![按一下 [大小寫的 [首頁] 頁面的 [搜尋](media/bd358eb3-12d4-4f0c-8317-d192286813d0.png)
  
4. <span data-ttu-id="7332d-271">在 [**搜尋**] 頁面上，按一下 [**新增**![新增圖示](media/ITPro-EAC-AddIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="7332d-271">On the **Search** page, click **New**![Add Icon](media/ITPro-EAC-AddIcon.gif).</span></span>
    
5. <span data-ttu-id="7332d-p135">在 [**新的搜尋**] 頁面上輸入搜尋的名稱。與案例相關聯的內容搜尋必須是 Office 365 組織內唯一的名稱。</span><span class="sxs-lookup"><span data-stu-id="7332d-p135">On the **New search** page, type a name for the search. Content Searches associated with a case must have names that are unique within your Office 365 organization.</span></span> 
    
6. <span data-ttu-id="7332d-p136">選擇您要搜尋的內容位置。您可以在相同的搜尋中搜尋信箱、 網站及公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="7332d-p136">Choose the content locations that you want to search. You can search mailboxes, sites, and public folders in the same search.</span></span>
    
    ![搜尋案例的內容位置，所有內容的位置，或選取特定的內容位置](media/08c523dc-cba8-4fce-aee6-f86251204393.png)
  
1. <span data-ttu-id="7332d-p137">**區分大小的所有內容**選取此選項可搜尋已處於保留狀態的情況下的所有內容位置。如果案例包含多個保留，當您選取這個選項會搜尋的所有保留位置的內容。此外，如果查詢式保留撥打內容的位置，只會保留的項目拼寫須符合當您執行您在此步驟中建立的內容搜尋。例如，如果使用者已處於查詢為基礎的案例保留保留項目已傳送或特定日期之前建立的這些項目嗎搜尋所使用之內容的搜尋的搜尋準則。這被藉由將 case 保留查詢及內容的搜尋查詢所**AND**運算子連線。請參閱如需詳細資訊搜尋 case 內容本文結尾處[的詳細資訊](manage-ediscovery-cases.md#moreinfo_1)] 區段。</span><span class="sxs-lookup"><span data-stu-id="7332d-p137">**All case content**Select this option to search all the content locations that have been placed on hold in the case. If the case contains multiple holds, the content locations from all holds will be searched when you select this option. Additionally, if a content location was placed on a query-based hold, only the items that are on hold will be searched when you run the content search that you're creating in this step. For example, if a user was placed on query-based case hold that preserves items that were sent or created before a specific date, only those items would be searched by using the search criteria of the content search. This is accomplished by connecting the case hold query and the content search query by an **AND** operator. See the [More information](manage-ediscovery-cases.md#moreinfo_1) section at the end of this article for more details about searching case content.</span></span> 
    
2. <span data-ttu-id="7332d-p138">**寄件人搜尋**選取此選項可在組織中搜尋所有內容的位置。當您選取這個選項時，您可以選擇搜尋所有的 Exchange 信箱 （其中包含信箱的所有 Office 365 群組與的 Microsoft 小組），所有 SharePoint 和 OneDrive for Business 的網站 （其中包含所有的 Office 365 群組與 Microsoft 的網站小組） 及所有公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="7332d-p138">**Search everywhere**Select this option to search all content locations in your organization. When you select this option, you can choose to search all Exchange mailboxes (which includes the mailboxes for all Office 365 Groups and Microsoft Teams), all SharePoint and OneDrive for Business sites (which includes the sites for all Office 365 Groups and Microsoft Teams), and all public folders.</span></span>
    
3. <span data-ttu-id="7332d-p139">**自訂位置選取項目**選取此選項可選取的信箱與您想要搜尋的網站。當您選取這個選項時，信箱和網站的清單會預先填入位置會放在保留內大小寫的內容。您也可以選擇在組織中搜尋所有的公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="7332d-p139">**Custom location selection**Select this option to select the mailboxes and sites that you want to search. When you select this option, the list of mailboxes and sites is pre-populated with the content locations that are placed on hold within the case. You can also choose to search all public folders in your organization.</span></span>
    
    ![搜尋所有案例的內容、 搜尋所有的位置，或搜尋自訂位置](media/7ca97ab4-52d5-46a5-9e24-e3a4d1001595.png)
  
    <span data-ttu-id="7332d-p140">如果您選取此選項與搜尋上的任何內容位置，但保留，從查詢為基礎的案例保留任何查詢不會套用至搜尋查詢。換句話說，搜尋位置中的所有內容，而不只保留查詢為基礎的案例保留的內容。</span><span class="sxs-lookup"><span data-stu-id="7332d-p140">But if you select this option and search any content location that's on hold, any query from a query-based case hold won't be applied to the search query. In other words, all content in a location is searched, not just the content that is preserved by a query-based case hold.</span></span>
    
    <span data-ttu-id="7332d-p141">您可以移除預先填入的區分內容位置或新增新的。如果您選擇這個選項，您也可以彈性來搜尋特定的服務 （例如搜尋所有的 Exchange 信箱） 的所有內容的位置或可搜尋服務的特定內容的位置。您也可以選擇要在組織中搜尋的公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="7332d-p141">You can remove the pre-populated case content locations or add new ones. If you choose this option, you also have flexibility to search all content locations for a specific service (such as searching all Exchange mailboxes) or you can search specific content locations for a service. You can also choose whether or not to search the public folders in your organization.</span></span>
    
    <span data-ttu-id="7332d-294">新增要搜尋的內容位置時請牢記下列事項：</span><span class="sxs-lookup"><span data-stu-id="7332d-294">Keep these things in mind when adding content locations to search:</span></span>
    
  - <span data-ttu-id="7332d-p142">當您按一下 [**新增**![新增圖示](media/ITPro-EAC-AddIcon.gif)來指定要搜尋的信箱，會顯示信箱選擇是空的。這是由設計，以提升效能。若要新增至這份清單的收件者，在搜尋方塊中輸入的名稱 （至少要有 3 個字元） 並按一下 [**搜尋**]![搜尋圖示](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif)。</span><span class="sxs-lookup"><span data-stu-id="7332d-p142">When you click **Add**![Add Icon](media/ITPro-EAC-AddIcon.gif) to specify mailboxes to search, the mailbox picker that's displayed is empty. This is by design to enhance performance. To add recipients to this list, type a name (a minimum of 3 characters) in the search box and click **Search**![Search icon](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif).</span></span>
    
  - <span data-ttu-id="7332d-p143">您可以將非使用中信箱、 Office 365 群組、 Microsoft 小組及通訊群組新增至搜尋信箱清單。不支援動態通訊群組。若您要新增的 Office 365 群組或 Microsoft 小組、 群組或小組信箱搜尋 ；群組成員的信箱不搜尋。</span><span class="sxs-lookup"><span data-stu-id="7332d-p143">You can add inactive mailboxes, Office 365 Groups, Microsoft Teams, and distribution groups to the list of mailboxes to search. Dynamic distribution groups aren't supported. If you add Office 365 Groups or Microsoft Teams, the group or team mailbox is searched; the mailboxes of the group members aren't searched.</span></span>
    
  - <span data-ttu-id="7332d-301">如果您不想要包含的任何信箱或網站搜尋中，選取**選擇搜尋特定信箱**] 或 [**選擇要搜尋的特定網站**、 但不信箱或網站新增至清單。</span><span class="sxs-lookup"><span data-stu-id="7332d-301">If you don't want to include any mailboxes or sites in a search, select **Choose specific mailboxes to search** or **Choose specific sites to search**, but don't add mailboxes or sites to the list.</span></span>
    
  - <span data-ttu-id="7332d-p144">若要新增網站按一下 [**新增**![新增圖示](media/ITPro-EAC-AddIcon.gif)然後輸入您要搜尋的每個網站的 URL。您也可以新增 SharePoint 網站的 URL 為 Office 365 群組和 Microsoft 小組。</span><span class="sxs-lookup"><span data-stu-id="7332d-p144">To add sites click **Add**![Add Icon](media/ITPro-EAC-AddIcon.gif) and then type the URL for each site that you want to search. You can also add the URL for the SharePoint site for Office 365 Groups and Microsoft Teams.</span></span> 
    
7. <span data-ttu-id="7332d-304">之後您選取 [內容的位置搜尋，並按一下 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="7332d-304">After you selected the content locations to search, click **Next**.</span></span>
    
8. <span data-ttu-id="7332d-305">您可以在 [**新的搜尋**] 頁面上新增關鍵字和條件來建立搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="7332d-305">On the **New search** page, you can add keywords and conditions to create the search query.</span></span> 
    
    ![搜尋條件和條件](media/9064147e-feac-4090-bbf6-2298ad7622c6.png)
  
1. <span data-ttu-id="7332d-p145">在下] 方塊中**您想什麼我們要尋找的？**、] 方塊中輸入搜尋查詢。您可以指定關鍵字，訊息屬性例如傳送及接收日期或文件內容，例如檔案名稱或上次變更文件的日期。您可以使用較複雜的查詢使用布林運算子，例如**AND**、**或**、**不**、 **NEAR**或**ONEAR**。您也可以搜尋文件或搜尋功能已從外部共用的文件中的機密資訊 （例如社會安全編號）。如果 [關鍵字] 方塊中保留空白，將會在搜尋結果中包含位於指定之內容的位置中的所有內容。</span><span class="sxs-lookup"><span data-stu-id="7332d-p145">In the box under **What do you want us to look for?**, type a search query in the box. You can specify keywords, message properties such as sent and received dates, or document properties such as file names or the date that a document was last changed. You can use a more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, **NEAR**, or **ONEAR**. You can also search for sensitive information (such as social security numbers) in documents, or search for documents that have been shared externally. If you leave the keyword box empty, all content located in the specified content locations will be included in the search results.</span></span> 
    
2. <span data-ttu-id="7332d-p146">您可以按一下 [**顯示關鍵字清單**] 核取方塊和類型中的每一列的關鍵字。如果您這樣做，在每一列的關鍵字連接**OR**運算子會建立搜尋查詢中所連接。</span><span class="sxs-lookup"><span data-stu-id="7332d-p146">You can click the **Show keyword list** checkbox and the type a keyword in each row. If you do this, the keywords on each row are connected by the **OR** operator in the search query that's created.</span></span> 
    
    ![搜尋關鍵字](media/c3ef511a-e0a3-4b5d-9779-36803270a193.png)
  
    <span data-ttu-id="7332d-p147">為什麼要選擇使用 [關鍵字] 清單？您可以取得顯示多少個項目比對每個關鍵字的統計資料。這可協助您快速識別出哪些關鍵字是最 （且至少） 有效。您也可以使用 （以括弧括住） 的關鍵字文句] 列中。如需搜尋統計資料的詳細資訊，請參閱 ＜[檢視內容的搜尋結果的關鍵字統計資料](view-keyword-statistics-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="7332d-p147">Why use the keyword list? You can get statistics that show how many items match each keyword. This can help you quickly identify which keywords are the most (and least) effective. You can also use a keyword phrase (surrounded by parentheses) in a row. For more information about search statistics, see [View keyword statistics for Content Search results](view-keyword-statistics-for-content-search.md).</span></span>
    
    <span data-ttu-id="7332d-320">如需使用關鍵字] 清單中的詳細資訊，請參閱[的詳細資訊](run-a-content-search-in-the-security-and-compliance-center.md#moreinfo)。</span><span class="sxs-lookup"><span data-stu-id="7332d-320">For more information about using the keywords list, see [More information](run-a-content-search-in-the-security-and-compliance-center.md#moreinfo).</span></span>
    
3. <span data-ttu-id="7332d-p148">按一下 [**檢查查詢錯字**檢查查詢不受支援的字元與可能未接的布林運算子。不支援的字元通常隱藏與通常搜尋的錯誤或傳回非預期的結果。如需會檢查有不支援字元的詳細資訊，請參閱[檢查錯誤的內容搜尋查詢](check-your-content-search-query-for-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="7332d-p148">Click **Check query for typos** to check your query for unsupported characters and for Boolean operators that might not be capitalized. Unsupported characters are often hidden and typically cause a search error or return unintended results. For more information about the unsupported characters that are checked, see [Check your Content Search query for errors](check-your-content-search-query-for-errors.md).</span></span>
    
4. <span data-ttu-id="7332d-p149">在 [**條件**新增條件來縮小搜尋及傳回一組更精簡的結果在搜尋查詢。每個條件將子句新增至 KQL 搜尋查詢，建立及執行當您啟動搜尋。條件是以邏輯方式連線到 （在 [關鍵字] 方塊中指定） 的關鍵字查詢**和**運算子。這表示項目必須滿足的關鍵字查詢與結果中包含的條件。這是條件，縮減結果協助的方式。</span><span class="sxs-lookup"><span data-stu-id="7332d-p149">Under **Conditions**, add conditions to a search query to narrow a search and return a more refined set of results. Each condition adds a clause to the KQL search query that is created and run when you start the search. A condition is logically connected to the keyword query (specified in the keyword box) by the **AND** operator. That means that items have to satisfy both the keyword query and the condition to be included in the results. This is how conditions help to narrow your results.</span></span> 
    
    <span data-ttu-id="7332d-329">如需建立搜尋查詢和使用條件的相關資訊，請參閱 [Keyword queries for Content Search](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="7332d-329">For more information about creating a search query and using conditions, see [Keyword queries for Content Search](keyword-queries-and-search-conditions.md).</span></span>
    
9. <span data-ttu-id="7332d-330">按一下 [**搜尋**] 以儲存搜尋設定並啟動搜尋。</span><span class="sxs-lookup"><span data-stu-id="7332d-330">Click **Search** to save the search settings and start the search.</span></span> 
    
    <span data-ttu-id="7332d-p150">啟動搜尋。While 之後評估會有搜尋結果會顯示詳細資料窗格中。評估包含的總大小和符合搜尋準則的項目數。搜尋 estimate 也包括所搜尋的內容位置編製索引的項目數。編製索引不符合搜尋準則的項目數將包含在詳細資料窗格中顯示的搜尋統計資料。如果搜尋查詢 （因為其他訊息或文件屬性符合搜尋準則） 編製索引的項目相符，則不會包含在估計編製索引的項目數。如果編製索引的項目會排除的搜尋準則，它也不會包含在評估編製索引的項目。</span><span class="sxs-lookup"><span data-stu-id="7332d-p150">The search is started. After a while, an estimate of the search results is displayed in the details pane. The estimate includes the total size and number of items that matched the search criteria. The search estimate also includes the number of the unindexed items in the content locations that were searched. The number of unindexed items that don't meet the search criteria will be included in the search statistics displayed in the details pane. If an unindexed item matches the search query (because other message or document properties meet the search criteria), it won't be included in the estimated number of unindexed items. If an unindexed item is excluded by the search criteria, it also won't be included in the estimate of unindexed items.</span></span>
    
    <span data-ttu-id="7332d-p151">搜尋完成後，您可預覽搜尋結果。若有必要，請按一下 [**重新整理**![重新整理] 圖示](media/O365-MDM-Policy-RefreshIcon.gif)要更新的詳細資料窗格中的資訊。</span><span class="sxs-lookup"><span data-stu-id="7332d-p151">After the search is completed, you can preview the search results. If necessary, click **Refresh**![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
[<span data-ttu-id="7332d-340">回到頁首</span><span class="sxs-lookup"><span data-stu-id="7332d-340">Return to top</span></span>](manage-ediscovery-cases.md#top)
  
## <a name="step-6-export-the-results-of-a-content-search-associated-with-a-case"></a><span data-ttu-id="7332d-341">步驟 6： 匯出與案例相關聯之內容搜尋的結果</span><span class="sxs-lookup"><span data-stu-id="7332d-341">Step 6: Export the results of a Content Search associated with a case</span></span>
<span data-ttu-id="7332d-342"><a name="step5_1"> </a></span><span class="sxs-lookup"><span data-stu-id="7332d-342"></span></span>

<span data-ttu-id="7332d-p152">成功執行搜尋之後，您可以將匯出的搜尋結果。當您將搜尋結果匯出信箱項目會下載 PST 檔案中或以個別的郵件。當您匯出 SharePoint 與內容 OneDrive for Business 的網站時，都要匯出的原生 Office 文件和其他文件複本。包含每個搜尋結果的相關資訊的資訊清單檔案 （以 XML 格式） 也會匯出。</span><span class="sxs-lookup"><span data-stu-id="7332d-p152">After a search is successfully run, you can export the search results. When you export search results, mailbox items are downloaded in PST files or as individual messages. When you export content from SharePoint and OneDrive for Business sites, copies of native Office documents and other documents are exported. A manifest file (in XML format) that contains information about every search result is also exported.</span></span>
  
<span data-ttu-id="7332d-347">您可以將匯出的[匯出與案例相關聯的單一搜尋結果](manage-ediscovery-cases.md#singlesearch_1)的結果或您可以將匯出的[匯出其結果的多個案例相關聯的搜尋](manage-ediscovery-cases.md#multiplesearches_1)結果。</span><span class="sxs-lookup"><span data-stu-id="7332d-347">You can export the results of a [Export the results of a single search associated with a case](manage-ediscovery-cases.md#singlesearch_1) or you can export the results of [Export the results of multiple searches associated with a case](manage-ediscovery-cases.md#multiplesearches_1).</span></span>
  
### <a name="export-the-results-of-a-single-search-associated-with-a-case"></a><span data-ttu-id="7332d-348">匯出與案例相關聯的單一搜尋結果</span><span class="sxs-lookup"><span data-stu-id="7332d-348">Export the results of a single search associated with a case</span></span>
<span data-ttu-id="7332d-349"><a name="singlesearch_1"> </a></span><span class="sxs-lookup"><span data-stu-id="7332d-349"></span></span>

1. <span data-ttu-id="7332d-350">安全性&amp;規範中心，按一下 [**搜尋&amp;調查** \> **eDiscovery**可在組織中顯示的情況下的清單。</span><span class="sxs-lookup"><span data-stu-id="7332d-350">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="7332d-351">按一下您想要匯出從搜尋案例] 旁的 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="7332d-351">Click **Open** next to the case that you want to export search from.</span></span> 
    
3. <span data-ttu-id="7332d-352">在 [**首頁**] 頁面的大小寫上按一下 [**搜尋**]。</span><span class="sxs-lookup"><span data-stu-id="7332d-352">On the **Home** page for the case, click **Search**.</span></span>
    
4. <span data-ttu-id="7332d-353">在搜尋案例清單中，按一下 [您想要匯出的搜尋結果中，按一下 [**匯出**搜尋![匯出搜尋結果圖示](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png)，然後按一下 [**匯出結果**。</span><span class="sxs-lookup"><span data-stu-id="7332d-353">In the list of searches for the case, click the search that you want to export search results from, click **Export**![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png), and then click **Export the results**.</span></span>
    
    <span data-ttu-id="7332d-p153">**匯出搜尋結果**頁面會顯示。要匯出之內容的搜尋結果的工作流程相關聯的案例是可與相同匯出搜尋結果在**內容搜尋**] 頁面上。如需逐步說明，請參閱[匯出搜尋結果的 Office 365 安全性&amp;規範中心](export-search-results.md)。</span><span class="sxs-lookup"><span data-stu-id="7332d-p153">The **Export search results** page is displayed. The workflow to export the results from a Content Search associated with a case is that same as exporting the search results for a search on the **Content search** page. For step-by-step instructions, see [Export search results from the Office 365 Security &amp; Compliance Center](export-search-results.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7332d-p154">匯出搜尋結果時，必須啟用重複資料刪除以便只有一個電子郵件的副本匯出即使多個執行個體相同的訊息可能會有已搜尋的信箱中找到的選項。如需詳細資訊需重複資料刪除和如何重複的項目會識別出，請參閱[重複資料刪除 eDiscovery 搜尋結果中](de-duplication-in-ediscovery-search-results.md)。</span><span class="sxs-lookup"><span data-stu-id="7332d-p154">When you export search results, you have the option to enable de-duplication so that only one copy of an email message is exported even though multiple instances of the same message might have been found in the mailboxes that were searched. For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span> 
  
5. <span data-ttu-id="7332d-359">在您開始匯出之後，按一下 [**匯出**至顯示存在於該案例的匯出工作的清單。</span><span class="sxs-lookup"><span data-stu-id="7332d-359">After you start the export, click **Export** to display the list of export jobs that exist for that case.</span></span> 
    
    ![按一下 [匯出至顯示的匯出工作清單](media/b7b95bf7-134e-471e-961e-f86c1bb633eb.png)
  
    <span data-ttu-id="7332d-p155">您可能必須按一下 [**重新整理**![重新整理] 圖示](media/O365-MDM-Policy-RefreshIcon.gif)要更新的匯出至顯示您剛才建立的匯出工作的工作清單。請注意匯出工作有相同名稱的對應的內容搜尋與 **_Export**附加至搜尋名稱結尾。</span><span class="sxs-lookup"><span data-stu-id="7332d-p155">You might have to click **Refresh**![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the list of export jobs to display the export job that you just created. Note that export jobs have the same name as the corresponding Content Search with **_Export** appended to the end of search name.</span></span> 
    
6. <span data-ttu-id="7332d-p156">按一下您剛建立的詳細資料窗格中顯示狀態資訊的匯出工作。此資訊包含已經移轉到 Microsoft 雲端 Azure 儲存區的項目百分比。</span><span class="sxs-lookup"><span data-stu-id="7332d-p156">Click the export job that you just created to display status information in the details pane. This information includes the percentage of items that have been transferred to an Azure storage area in the Microsoft cloud.</span></span>
    
    <span data-ttu-id="7332d-p157">所有項目已傳送之後，按一下 [**下載匯出結果**下載至您的本機電腦的搜尋結果。如需詳細資訊，請參閱 ＜ 步驟 2 中[匯出搜尋結果的 Office 365 安全性&amp;規範中心](export-search-results.md)</span><span class="sxs-lookup"><span data-stu-id="7332d-p157">After all items have been transferred, click **Download exported results** to download the search results to your local computer. For more information, see Step 2 in [Export search results from the Office 365 Security &amp; Compliance Center](export-search-results.md)</span></span>
    
### <a name="export-the-results-of-multiple-searches-associated-with-a-case"></a><span data-ttu-id="7332d-367">匯出多個案例相關聯的搜尋結果</span><span class="sxs-lookup"><span data-stu-id="7332d-367">Export the results of multiple searches associated with a case</span></span>
<span data-ttu-id="7332d-368"><a name="multiplesearches_1"> </a></span><span class="sxs-lookup"><span data-stu-id="7332d-368"></span></span>

<span data-ttu-id="7332d-p158">當另一種替代匯出單一內容的搜尋結果相關聯的案例，您可以從單一匯出中的相同情況匯出多個搜尋的結果。匯出多個搜尋的結果是更快且更容易比匯出結果一個搜尋一次。</span><span class="sxs-lookup"><span data-stu-id="7332d-p158">As an alternative to exporting the results of a single Content Search associated with a case, you can export the results of multiple searches from the same case in a single export. Exporting the results of multiple searches is faster and easier than exporting the results one search at a time.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7332d-p159">您無法將多個搜尋結果匯出如果其中一個這些搜尋設定為搜尋所有案例的內容。僅匯出多個搜尋與 eDiscovery 案例相關聯的搜尋結果。您無法將匯出的安全性**內容搜尋**] 頁面上所列的多個搜尋結果&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="7332d-p159">You can't export the results of multiple searches if one of those searches was configured to search all case content. only export the results of multiple searches for searches that are associated with an eDiscovery case. You can't export the results of multiple searches listed on the **Content search** page in the Security &amp; Compliance Center.</span></span> 
  
1. <span data-ttu-id="7332d-374">安全性&amp;規範中心，按一下 [**搜尋&amp;調查** \> **eDiscovery**可在組織中顯示的情況下的清單。</span><span class="sxs-lookup"><span data-stu-id="7332d-374">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="7332d-375">按一下您想要匯出從搜尋案例] 旁的 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="7332d-375">Click **Open** next to the case that you want to export search from.</span></span> 
    
3. <span data-ttu-id="7332d-376">在 [**首頁**] 頁面的大小寫上按一下 [**搜尋**]。</span><span class="sxs-lookup"><span data-stu-id="7332d-376">On the **Home** page for the case, click **Search**.</span></span>
    
4. <span data-ttu-id="7332d-377">在 [大小寫的搜尋] 清單選取您想要匯出的搜尋結果的兩個或多個搜尋。</span><span class="sxs-lookup"><span data-stu-id="7332d-377">In the list of searches for the case, select two or more searches that you want to export search results from.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7332d-p160">若要選取多個搜尋，請按住**ctrl 鍵**當您按一下每個搜尋。或者，您可以按一下第一個搜尋、 按住**Shift**鍵，然後按一下 [上次搜尋來選取多個相鄰的搜尋。</span><span class="sxs-lookup"><span data-stu-id="7332d-p160">To select multiple searches, press **Ctrl** as you click each search. Or you can select multiple adjacent searches by clicking the first search, holding down the **Shift** key, and then clicking the last search.</span></span> 
  
5. <span data-ttu-id="7332d-380">選取搜尋之後，按一下 [**匯出**![匯出搜尋結果圖示](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png)，然後按一下 [**匯出結果**。</span><span class="sxs-lookup"><span data-stu-id="7332d-380">After you select the searches, click **Export**![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png), and then click **Export the results**.</span></span>
    
6. <span data-ttu-id="7332d-p161">* * 匯出搜尋結果*n*搜尋 * * 顯示] 頁面上，其中*n*是您要匯出結果的搜尋數目。請注意您必須提供匯出工作的名稱。</span><span class="sxs-lookup"><span data-stu-id="7332d-p161">The **Export the search results for  *n*  searches ** page is displayed, where  *n*  is the number of searches that you're exporting results for. Note that you'll have to give the export job a name.</span></span> 
    
    <span data-ttu-id="7332d-p162">要匯出結果從多個內容搜尋與案例相關聯的工作流程並匯出單一搜尋結果相同。如需逐步說明，請參閱[匯出搜尋結果的 Office 365 安全性&amp;規範中心](export-search-results.md)。</span><span class="sxs-lookup"><span data-stu-id="7332d-p162">The workflow to export the results from multiple content searches associated with a case is the same as exporting the search results for a single search. For step-by-step instructions, see [Export search results from the Office 365 Security &amp; Compliance Center](export-search-results.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7332d-p163">當您從多個案例相關聯的搜尋匯出搜尋結果時，您也可以啟用重複資料刪除以便只有一個電子郵件的副本匯出即使多個執行個體相同訊息可能會有中找到的選項在一或多個搜尋所搜尋的信箱。如需詳細資訊需重複資料刪除和如何重複的項目會識別出，請參閱[重複資料刪除 eDiscovery 搜尋結果中](de-duplication-in-ediscovery-search-results.md)。</span><span class="sxs-lookup"><span data-stu-id="7332d-p163">When you export search results from multiple searches associated with a case, you also have the option to enable de-duplication so that only one copy of an email message is exported even though multiple instances of the same message might have been found in the mailboxes that were searched in one or more of the searches. For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span> 
  
7. <span data-ttu-id="7332d-387">在您開始匯出之後，按一下 [顯示匯出清單的 [**匯出**工作可針對該案例。</span><span class="sxs-lookup"><span data-stu-id="7332d-387">After you start the export, click **Export** to display the list of export jobs that for that case.</span></span> 
    
    ![按一下 [匯出至顯示的匯出工作清單](media/b7b95bf7-134e-471e-961e-f86c1bb633eb.png)
  
    <span data-ttu-id="7332d-p164">您可能必須按一下 [**重新整理**![重新整理] 圖示](media/O365-MDM-Policy-RefreshIcon.gif)要更新的匯出至顯示您剛才建立的匯出工作的工作清單。請注意匯出工作中所包含的搜尋所列在 [**搜尋**] 欄中。</span><span class="sxs-lookup"><span data-stu-id="7332d-p164">You might have to click **Refresh**![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the list of export jobs to display the export job that you just created. Note that the searches that were included in the export job are listed in the **Searches** column.</span></span> 
    
8. <span data-ttu-id="7332d-p165">按一下您剛建立的詳細資料窗格中顯示狀態資訊的匯出工作。此資訊包含已經移轉到 Microsoft 雲端 Azure 儲存區的項目百分比。</span><span class="sxs-lookup"><span data-stu-id="7332d-p165">Click the export job that you just created to display status information in the details pane. This information includes the percentage of items that have been transferred to an Azure storage area in the Microsoft cloud.</span></span>
    
9. <span data-ttu-id="7332d-p166">所有項目已傳送之後，按一下 [**下載匯出結果**下載至您的本機電腦的搜尋結果。如需詳細資訊，請參閱 ＜ 步驟 2 中[匯出搜尋結果的 Office 365 安全性&amp;規範中心](export-search-results.md)</span><span class="sxs-lookup"><span data-stu-id="7332d-p166">After all items have been transferred, click **Download exported results** to download the search results to your local computer. For more information, see Step 2 in [Export search results from the Office 365 Security &amp; Compliance Center](export-search-results.md)</span></span>
    
#### <a name="more-information-about-exporting-the-results-of-multiple-searches"></a><span data-ttu-id="7332d-395">匯出多個搜尋結果的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="7332d-395">More information about exporting the results of multiple searches</span></span>

- <span data-ttu-id="7332d-p167">當您將匯出的多個搜尋結果時，搜尋查詢所有搜尋從結合使用**或**運算子，然後合併的搜尋已啟動。估計合併的搜尋結果會顯示所選的匯出工作的詳細資料窗格中。在搜尋結果會然後轉接到 Microsoft 雲端中的 [Azure 存放區] 區域。傳輸狀態也會顯示在詳細資料窗格中。先前所述，已轉移所有搜尋結果之後，您可以下載這些到您的本機電腦。</span><span class="sxs-lookup"><span data-stu-id="7332d-p167">When you export the results of multiple searches, the search queries from all the searches are combined by using **OR** operators, and then the combined search is started. The estimated results of the combined search are displayed in the details pane of the selected export job. The search results are then transferred to the Azure storage area in the Microsoft cloud. The status of the transfer is also displayed in the details pane. As previously stated, after all the search results have been transferred, you can download them to your local computer.</span></span> 
    
- <span data-ttu-id="7332d-p168">您想要匯出的所有搜尋搜尋查詢關鍵字的數目上限為 500。（這是單一內容搜尋的相同限制。）那是因為匯出工作合併所有搜尋查詢使用**OR**運算子。如果您超過此限制，則會傳回錯誤。在此例中，您必須從較少的搜尋結果匯出或簡化您想要匯出的搜尋搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="7332d-p168">The maximum number of keywords from the search queries for all searches that you want to export is 500. (this is the same limit for a single Content Search). That's because the export job combines all the search queries by using the **OR** operator. If you exceed this limit, an error will be returned. In this case, you'll have to export the results from fewer searches or simplify the search queries of the searches that you want to export.</span></span> 
    
- <span data-ttu-id="7332d-p169">會匯出搜尋結果被依據此項目中找到的內容來源。這表示在匯出結果的內容來源可能會有不同的搜尋所傳回的項目。例如，如果您選擇要匯出的每個信箱的一個 PST 檔案中的電子郵件訊息、 PST 檔案可能會有來自多個搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="7332d-p169">The search results that are exported are organized by the content source the item was found in. That means a content source in the export results might have items returned by different searches. For example, if you chose to export email messages in one PST file for each mailbox, the PST file might have results from multiple searches.</span></span>
    
- <span data-ttu-id="7332d-409">如果相同的電子郵件項目或文件從相同的內容位置由多個匯出搜尋所傳回，要匯出的項目只有一個複本。</span><span class="sxs-lookup"><span data-stu-id="7332d-409">If the same email item or document from the same content location is returned by more than one of the searches that you export, only one copy of the item will be exported.</span></span>
    
- <span data-ttu-id="7332d-p170">您在建立之後，您無法編輯匯出多個搜尋。例如，您無法新增或移除匯出搜尋。您必須建立新的匯出工作變更都要匯出哪些搜尋結果。建立 「 匯出 」 工作之後，您只可以下載到電腦的結果、 重新啟動匯出，或刪除匯出工作。</span><span class="sxs-lookup"><span data-stu-id="7332d-p170">You can't edit an export for multiple searches after you create it. For example, you can't add or remove searches from the export. You'll have to create a new export job to change which search results are exported. After a export job is created, you only can download the results to a computer, restart the export, or delete the export job.</span></span>
    
- <span data-ttu-id="7332d-p171">如果您重新啟動匯出的匯出工作所組成的搜尋查詢的任何變更將不會影響將擷取的搜尋結果。當您重新啟動匯出時，將會再次執行建立匯出工作時所執行的相同合併的搜尋查詢工作。</span><span class="sxs-lookup"><span data-stu-id="7332d-p171">If you restart the export, any changes to the queries of the searches that make up the export job won't affect the search results that will be retrieved. When you restart an export, the same combined search query job that was run when the export job was created will be run again.</span></span>
    
- <span data-ttu-id="7332d-416">如果您重新啟動 eDiscovery 案例中的匯出從 [**匯出**] 頁面上，會轉接到 Azure 儲存區的搜尋結果會覆寫先前的結果 ；先前的結果有已轉接通話將不會可供下載。</span><span class="sxs-lookup"><span data-stu-id="7332d-416">If you restart an export from the **Exports** page in an eDiscovery case, the search results that are transferred to the Azure storage area will overwrite the previous results; the previous results there were transferred won't be available to be downloaded.</span></span> 
    
- <span data-ttu-id="7332d-p172">準備進行分析進階在 eDiscovery 中的多個搜尋結果無法使用。您只可以準備進行分析進階在 eDiscovery 中的單一搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="7332d-p172">Preparing the results of multiple searches for analysis in Advanced eDiscovery isn't available. You can only prepare the results of a single search for analysis in Advanced eDiscovery.</span></span>
    
[<span data-ttu-id="7332d-419">回到頁首</span><span class="sxs-lookup"><span data-stu-id="7332d-419">Return to top</span></span>](manage-ediscovery-cases.md#top)
  
## <a name="step-7-prepare-search-results-for-advanced-ediscovery"></a><span data-ttu-id="7332d-420">步驟 7： 準備搜尋結果進階 ediscovery （英文）</span><span class="sxs-lookup"><span data-stu-id="7332d-420">Step 7: Prepare search results for Advanced eDiscovery</span></span>
<span data-ttu-id="7332d-421"><a name="step7_1"> </a></span><span class="sxs-lookup"><span data-stu-id="7332d-421"></span></span>

<span data-ttu-id="7332d-p173">如果貴組織的 Office 365 E5 訂閱，您可以準備內容進行分析進階 ediscovery 案例相關聯的搜尋的結果。準備好搜尋結果之後，您可以前往進階的 eDiscovery (請參閱[步驟 8： 移至 [進階 ediscovery 案例](manage-ediscovery-cases.md#gotoAeD_1)) 及處理供進一步分析進階在 eDiscovery 中搜尋結果資料。</span><span class="sxs-lookup"><span data-stu-id="7332d-p173">If your organization has an Office 365 E5 subscription, you can prepare the results of Content Searches associated with a case for analysis in Advanced eDiscovery. After you prepare search results, you can go to Advanced eDiscovery (see [Step 8: Go to the case in Advanced eDiscovery](manage-ediscovery-cases.md#gotoAeD_1)) and process the search result data for further analysis in Advanced eDiscovery.</span></span>
  
<span data-ttu-id="7332d-p174">當您準備進階 eDiscovery 搜尋結果時，光學字元辨識 (OCR) 功能自動擷取文字的圖像。OCR 支援寬鬆的檔案、 電子郵件附件、 和內嵌圖像。這可讓您將文字分析功能的進階 eDiscovery （接近重複項目、 電子郵件執行緒、 佈景主題及預測編碼） 套用至圖像檔案中的任何文字。</span><span class="sxs-lookup"><span data-stu-id="7332d-p174">When you prepare search results for Advanced eDiscovery, optical character recognition (OCR) functionality automatically extracts text from images. OCR is supported for loose files, email attachments, and embedded images. This allows you to apply the text analytic capabilities of Advanced eDiscovery (near-duplicates, email threading, themes, and predictive coding) to any text in image files.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7332d-p175">若要分析使用進階的 eDiscovery 的使用者資料，使用者 (資料 okay) 必須指派 Office 365 E5 授權。或者，使用 Office 365 E1 或 E3 授權的使用者可以將指派進階的 eDiscovery 獨立授權。系統管理員及法務人員對於已指派給的情況下並使用進階的 eDiscovery 分析資料不需要的 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="7332d-p175">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license. Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license. Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span> 
  
1. <span data-ttu-id="7332d-430">安全性&amp;規範中心，按一下 [**搜尋&amp;調查** \> **eDiscovery**可在組織中顯示的情況下的清單。</span><span class="sxs-lookup"><span data-stu-id="7332d-430">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="7332d-431">按一下您想要準備分析進階在 eDiscovery 中搜尋結果的大小寫] 旁的 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="7332d-431">Click **Open** next to the case that you want to prepare search results for analysis in Advanced eDiscovery.</span></span> 
    
3. <span data-ttu-id="7332d-432">在 [**首頁**] 頁面的大小寫 [**搜尋**]，然後選取搜尋]。</span><span class="sxs-lookup"><span data-stu-id="7332d-432">On the **Home** page for the case, click **Search**, and then select the search.</span></span>
    
4. <span data-ttu-id="7332d-433">在詳細資料] 窗格中，[**具有進階 eDiscovery 的分析結果**，請按一下 [**準備進行分析的結果**。</span><span class="sxs-lookup"><span data-stu-id="7332d-433">In the details pane, under **Analyze results with Advanced eDiscovery**, click **Prepare results for analysis**.</span></span>
    
5. <span data-ttu-id="7332d-434">在**準備供分析的結果**的頁面上，執行下列動作︰ </span><span class="sxs-lookup"><span data-stu-id="7332d-434">On the **Prepare results for analysis** page, do the following:</span></span> 
    
  - <span data-ttu-id="7332d-435">選擇 [準備進階 ediscovery 分析已編製索引的項目、 已編製索引及編製索引項目或僅編製索引的項目。</span><span class="sxs-lookup"><span data-stu-id="7332d-435">Choose to prepare indexed items, indexed and unindexed items, or only unindexed items for analysis in Advanced eDiscovery.</span></span>
    
  - <span data-ttu-id="7332d-p176">選擇是否要包含的文件符合搜尋準則的 SharePoint 上找到的所有版本。只有當搜尋的內容來源包含網站會出現此選項。</span><span class="sxs-lookup"><span data-stu-id="7332d-p176">Choose whether to include all versions of documents found on SharePoint that met the search criteria. This option appears only if the content sources for the search includes sites.</span></span>
    
  - <span data-ttu-id="7332d-438">指定是否要通知訊息傳送 （或複製） 來準備程序完成時的人員及資料已準備好進階 ediscovery 處理。</span><span class="sxs-lookup"><span data-stu-id="7332d-438">Specify whether you want a notification message sent (or copied) to a person when the preparation process is completed and the data is ready to be processed in Advanced eDiscovery.</span></span>
    
6. <span data-ttu-id="7332d-439">按一下 [**準備**]。</span><span class="sxs-lookup"><span data-stu-id="7332d-439">Click **Prepare**.</span></span>
    
    <span data-ttu-id="7332d-440">在搜尋結果已備妥與進階 eDiscovery 的分析。</span><span class="sxs-lookup"><span data-stu-id="7332d-440">The search results are prepared for analysis with Advanced eDiscovery.</span></span>
    
7. <span data-ttu-id="7332d-p177">在 [詳細資料] 窗格中，按一下 [**檢查準備狀態**顯示的準備程序的相關資訊。準備程序完成時，您可以前往處理分析之資料的進階 ediscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="7332d-p177">In the details pane, click **Check preparation status** to display information about the preparation process. When the preparation process is finished, you can go to the case in Advanced eDiscovery to process the data for analysis.</span></span> 
    
[<span data-ttu-id="7332d-443">回到頁首</span><span class="sxs-lookup"><span data-stu-id="7332d-443">Return to top</span></span>](manage-ediscovery-cases.md#top)
  
## <a name="step-8-go-to-the-case-in-advanced-ediscovery"></a><span data-ttu-id="7332d-444">步驟 8： 移至 [進階 ediscovery 案例</span><span class="sxs-lookup"><span data-stu-id="7332d-444">Step 8: Go to the case in Advanced eDiscovery</span></span>
<span data-ttu-id="7332d-445"><a name="gotoAeD_1"> </a></span><span class="sxs-lookup"><span data-stu-id="7332d-445"></span></span>

<span data-ttu-id="7332d-446">安全性建立案例之後&amp;規範中心您可以前往進階在 eDiscovery 中相同的大小寫。</span><span class="sxs-lookup"><span data-stu-id="7332d-446">After you create a case in the Security &amp; Compliance Center, you can go to the same case in Advanced eDiscovery.</span></span>
  
<span data-ttu-id="7332d-447">移至進階 ediscovery 案例：</span><span class="sxs-lookup"><span data-stu-id="7332d-447">To go to a case in Advanced eDiscovery:</span></span>
  
1. <span data-ttu-id="7332d-448">安全性&amp;規範中心，按一下 [**搜尋&amp;調查** \> **eDiscovery**可在組織中顯示的情況下的清單。</span><span class="sxs-lookup"><span data-stu-id="7332d-448">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="7332d-449">按一下您想要移至 [進階 ediscovery 案例] 旁的 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="7332d-449">Click **Open** next to the case that you want to go to in Advanced eDiscovery.</span></span> 
    
3. <span data-ttu-id="7332d-450">按一下 [**首頁**] 頁面的大小寫的 [**進階 ediscovery 的切換參數**。</span><span class="sxs-lookup"><span data-stu-id="7332d-450">On the **Home** page for the case, click **Switch to Advanced eDiscovery**.</span></span>
    
    ![若要開啟 [進階在 eDiscovery 中的 [大小寫的進階 ediscovery 按一下切換參數](media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    <span data-ttu-id="7332d-p178">會顯示 [**連線至進階 eDiscovery**進度列。當您連線至進階的 eDiscovery 時、 容器清單隨即顯示在頁面。</span><span class="sxs-lookup"><span data-stu-id="7332d-p178">The **Connecting to Advanced eDiscovery** progress bar is displayed. When you're connected to Advanced eDiscovery, a list of containers is displayed on the page.</span></span> 
    
    ![大小寫會顯示在進階的 eDiscovery](media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
    <span data-ttu-id="7332d-p179">這些容器代表您準備進行分析步驟 7 中的進階 eDiscovery 中搜尋結果。該容器的名稱同名內容搜尋案例中安全性的附註&amp;規範中心。在清單容器是過您準備。如果不同的使用者準備進階 eDiscovery 搜尋結果，相對應的容器不會包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="7332d-p179">These containers represent the search results that you prepared for analysis in Advanced eDiscovery in Step 7. Note that the name of the container has the same name as Content Search in the case in the Security &amp; Compliance Center. The containers in the list are the ones that you prepared. If a different user prepared search results for Advanced eDiscovery, the corresponding containers won't be included in the list.</span></span>
    
4. <span data-ttu-id="7332d-459">從容器的搜尋結果資料載入至進階 ediscovery 案例中，選取容器並按一下 [**程序**。</span><span class="sxs-lookup"><span data-stu-id="7332d-459">To load the search result data from a container to the case in Advanced eDiscovery, select a container and click **Process**.</span></span>
    
    <span data-ttu-id="7332d-460">如需如何處理程序容器的資訊，請參閱[執行程序模組和 Office 365 進階在 eDiscovery 中的將資料載入](run-the-process-module-and-load-data-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="7332d-460">For information about how to process containers, see [Run the Process module and load data in Office 365 Advanced eDiscovery](run-the-process-module-and-load-data-in-advanced-ediscovery.md).</span></span>
    
> [!TIP]
> <span data-ttu-id="7332d-461">按一下 [ **ediscovery 切換**回移至 [安全性] 中的相同情況&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="7332d-461">Click **Switch to eDiscovery** to go back to the same case in the Security &amp; Compliance Center.</span></span> 
  
[<span data-ttu-id="7332d-462">回到頁首</span><span class="sxs-lookup"><span data-stu-id="7332d-462">Return to top</span></span>](manage-ediscovery-cases.md#top)
  
## <a name="optional-step-9-close-a-case"></a><span data-ttu-id="7332d-463">（選用）步驟 9： 關閉案例</span><span class="sxs-lookup"><span data-stu-id="7332d-463">(Optional) Step 9: Close a case</span></span>
<span data-ttu-id="7332d-464"><a name="closecase_1"> </a></span><span class="sxs-lookup"><span data-stu-id="7332d-464"></span></span>

<span data-ttu-id="7332d-p180">法律案例或 eDiscovery 案例所支援的調查完成時，即可關閉案例。以下是當您關閉案例會發生什麼事：</span><span class="sxs-lookup"><span data-stu-id="7332d-p180">When the legal case or investigation supported by an eDiscovery case is completed, you can close the case. Here's what happens when you close a case:</span></span>
  
- <span data-ttu-id="7332d-p181">如果案例包含音樂的所有內容位置，將會開啟這些保留。這可能會導致內容要永久刪除或清除、 使用者或自動程序，例如的刪除原則。</span><span class="sxs-lookup"><span data-stu-id="7332d-p181">If the case contains any content locations on hold, those holds will be turned off. This might result in content being permanently deleted or purged, either by the user or by an automated process, such as a deletion policy.</span></span>
    
- <span data-ttu-id="7332d-p182">關閉案例只會關閉與該案例相關聯的保留。如果其他保留內容的位置 （例如訴訟保留。 保留原則，或從不同的 eDiscovery 案例的保留） 上進行這些保留則仍會保留。</span><span class="sxs-lookup"><span data-stu-id="7332d-p182">Closing a case only turns off the holds that are associated with that case. If other holds are place on a content location (such as a Litigation Hold. a Preservation Policy, or a hold from a different eDiscovery case) those holds will still be maintained.</span></span>
    
- <span data-ttu-id="7332d-p183">大小寫仍會列在 [eDiscovery] 頁面上的 [安全性]&amp;規範中心。會保留詳細資料、 保留、 搜尋，並關閉案例的成員。</span><span class="sxs-lookup"><span data-stu-id="7332d-p183">The case is still listed on the eDiscovery page in the Security &amp; Compliance Center. The details, holds, searches, and members of a closed case are retained.</span></span>
    
- <span data-ttu-id="7332d-p184">會在關閉之後，您可以編輯案例。例如，您可以新增或移除成員建立搜尋、 匯出搜尋結果，並準備分析進階在 eDiscovery 中搜尋結果。作用中且已關閉的情況下的主要差異在於保留已關閉時關閉案例。</span><span class="sxs-lookup"><span data-stu-id="7332d-p184">You can edit a case after it's closed. For example, you can add or removing members, create searches, export search results, and prepare search result for analysis in Advanced eDiscovery. The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>
    
<span data-ttu-id="7332d-477">若要關閉案例：</span><span class="sxs-lookup"><span data-stu-id="7332d-477">To close a case:</span></span>
  
1. <span data-ttu-id="7332d-478">安全性&amp;規範中心，按一下 [**搜尋&amp;調查** \> **eDiscovery**可在組織中顯示的情況下的清單。</span><span class="sxs-lookup"><span data-stu-id="7332d-478">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="7332d-479">按一下您想要關閉的大小寫的名稱。</span><span class="sxs-lookup"><span data-stu-id="7332d-479">Click the name of the case that you want to close.</span></span>
    
    <span data-ttu-id="7332d-480">會顯示 [**管理此例中**彈出式] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7332d-480">The **Manage this case** flyout page is displayed.</span></span> 
    
3. <span data-ttu-id="7332d-481">[**管理案例狀態**] 下按一下 [![移除 [預覽] 按鈕](media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif)**關閉案例**。</span><span class="sxs-lookup"><span data-stu-id="7332d-481">Under **Manage case status**, click ![Remove the peek button](media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) **Close case**.</span></span>
    
4. <span data-ttu-id="7332d-482">在 [**詳細資料**] 頁面上，按一下 [**關閉案例**。</span><span class="sxs-lookup"><span data-stu-id="7332d-482">On the **Details** page, click **Close case**.</span></span>
    
    <span data-ttu-id="7332d-483">預警案例相關聯的保留將已關閉顯示一則警告訊息。</span><span class="sxs-lookup"><span data-stu-id="7332d-483">A warning is displayed saying that the holds associated with the case will be turned off.</span></span>
    
5. <span data-ttu-id="7332d-484">按一下 [**是]** 以關閉 [大小寫。</span><span class="sxs-lookup"><span data-stu-id="7332d-484">Click **Yes** to close the case.</span></span> 
    
    <span data-ttu-id="7332d-485">在 [**管理此例中**彈出式頁面上的狀態會從**作用中**變更為**關閉**。</span><span class="sxs-lookup"><span data-stu-id="7332d-485">The status on the **Manage this case** flyout page is changed from **Active** to **Closing**.</span></span>
    
6. <span data-ttu-id="7332d-486">關閉 [**管理此案例**。</span><span class="sxs-lookup"><span data-stu-id="7332d-486">Close **Manage this case**.</span></span>
    
7. <span data-ttu-id="7332d-p185">在 [ **eDiscovery** ] 頁面上，按一下 [![重新整理] 圖示](media/O365-MDM-Policy-RefreshIcon.gif)**重新整理**更新關閉大小寫的狀態。可能需要最多 60 分鐘結束程序來完成。</span><span class="sxs-lookup"><span data-stu-id="7332d-p185">On the **eDiscovery** page, click ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) **Refresh** to update the status of the closed case. It might take up to 60 minutes for the closing process to complete.</span></span> 
    
    <span data-ttu-id="7332d-p186">程序完成時，大小寫的狀態變更以**關閉**[ **eDiscovery** ] 頁面上。按一下 [大小寫一次以顯示 [**管理此例中**彈出式] 頁面，包含以下資訊時關閉案例和誰在關閉的名稱。</span><span class="sxs-lookup"><span data-stu-id="7332d-p186">When the process is complete, the status of the case is changed to **Close** on the **eDiscovery** page. Click the name of the case again to display the **Manage this case** flyout page, which contains information about when the case was closed and who closed it.</span></span> 
    
[<span data-ttu-id="7332d-491">回到頁首</span><span class="sxs-lookup"><span data-stu-id="7332d-491">Return to top</span></span>](manage-ediscovery-cases.md#top)
  
## <a name="optional-step-10-re-open-a-closed-case"></a><span data-ttu-id="7332d-492">（選用）步驟 10： 重新開啟關閉的案例</span><span class="sxs-lookup"><span data-stu-id="7332d-492">(Optional) Step 10: Re-open a closed case</span></span>
<span data-ttu-id="7332d-493"><a name="reopencase_1"> </a></span><span class="sxs-lookup"><span data-stu-id="7332d-493"></span></span>

<span data-ttu-id="7332d-p187">當您重新開啟案例時，將不會自動恢復已備妥時關閉案例是任何保留。大小寫重新開啟後，您必須移至 [**保留**] 頁面上，並開啟先前保留。若要開啟保留，請選取其和詳細資料窗格中按一下 [**開啟**。</span><span class="sxs-lookup"><span data-stu-id="7332d-p187">When you re-open a case, any holds that were in place when the case was closed won't be automatically reinstated. After the case is re-opened, you'll have to go to the **Hold** page and turn on the previous holds. To turn a hold on, select it and click **Turn it on** in the details pane.</span></span> 
  
1. <span data-ttu-id="7332d-497">安全性&amp;規範中心，按一下 [**搜尋&amp;調查** \> **eDiscovery**可在組織中顯示的情況下的清單。</span><span class="sxs-lookup"><span data-stu-id="7332d-497">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="7332d-498">按一下您想重新開啟的大小寫的名稱。</span><span class="sxs-lookup"><span data-stu-id="7332d-498">Click the name of the case that you want to re-open.</span></span>
    
    <span data-ttu-id="7332d-499">會顯示 [**管理此例中**彈出式] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7332d-499">The **Manage this case** flyout page is displayed.</span></span> 
    
3. <span data-ttu-id="7332d-500">**管理案例的狀態**，請按一下 [**重新開啟案例**。</span><span class="sxs-lookup"><span data-stu-id="7332d-500">Under **Manage case status**, click **Reopen case**.</span></span>
    
    <span data-ttu-id="7332d-501">預警時關閉已與案例相關聯的保留將不會自動開啟顯示一則警告訊息。</span><span class="sxs-lookup"><span data-stu-id="7332d-501">A warning is displayed saying that the holds that were associated with the case when it was close won't be turned on automatically.</span></span>
    
4. <span data-ttu-id="7332d-502">按一下 [**是]** 以重新開啟 [大小寫。</span><span class="sxs-lookup"><span data-stu-id="7332d-502">Click **Yes** to re-open the case.</span></span> 
    
    <span data-ttu-id="7332d-503">在 [**管理此例中**彈出式頁面上的狀態會從**已關閉**變更為**使用中**。</span><span class="sxs-lookup"><span data-stu-id="7332d-503">The status on the **Manage this case** flyout page is changed from **Closed** to **Active**.</span></span>
    
5. <span data-ttu-id="7332d-504">關閉 [**管理此案例**。</span><span class="sxs-lookup"><span data-stu-id="7332d-504">Close **Manage this case**.</span></span>
    
6. <span data-ttu-id="7332d-p188">在 [ **eDiscovery** ] 頁面上，按一下 [![重新整理] 圖示](media/O365-MDM-Policy-RefreshIcon.gif)**重新整理**更新重新開啟大小寫的狀態。可能需要重新前後的程序完成最多 60 分鐘。</span><span class="sxs-lookup"><span data-stu-id="7332d-p188">On the **eDiscovery** page, click ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) **Refresh** to update the status of the re-opened case. It might take up to 60 minutes for the re-opening process to complete.</span></span> 
    
    <span data-ttu-id="7332d-507">程序完成時，大小寫的狀態變更為 [**作用中**[ **eDiscovery** ] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="7332d-507">When the process is complete, the status of the case is changed to **Active** on the **eDiscovery** page.</span></span> 
    
[<span data-ttu-id="7332d-508">回到頁首</span><span class="sxs-lookup"><span data-stu-id="7332d-508">Return to top</span></span>](manage-ediscovery-cases.md#top)
  
## <a name="more-information"></a><span data-ttu-id="7332d-509">其他資訊</span><span class="sxs-lookup"><span data-stu-id="7332d-509">More information</span></span>
<span data-ttu-id="7332d-510"><a name="moreinfo_1"> </a></span><span class="sxs-lookup"><span data-stu-id="7332d-510"></span></span>

- <span data-ttu-id="7332d-511">**有 eDiscovery 案例或保留與 eDiscovery 案例相關聯的任何限制吗？** 下表列出 eDiscovery 案例] 和 [大小寫的保留的限制。</span><span class="sxs-lookup"><span data-stu-id="7332d-511">**Are there any limits for eDiscovery cases or holds associated with an eDiscovery case?** The following table lists the limits for eDiscovery cases and case holds.</span></span>
    
|<span data-ttu-id="7332d-512">**限制說明**</span><span class="sxs-lookup"><span data-stu-id="7332d-512">**Description of limit**</span></span>|<span data-ttu-id="7332d-513">**限制**</span><span class="sxs-lookup"><span data-stu-id="7332d-513">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7332d-514">為組織的情況下的最大數目</span><span class="sxs-lookup"><span data-stu-id="7332d-514">Maximum number of cases for an organization</span></span>  <br/> |<span data-ttu-id="7332d-515">無限制</span><span class="sxs-lookup"><span data-stu-id="7332d-515">No limit</span></span>  <br/> |
|<span data-ttu-id="7332d-516">為組織保留最大數目大小寫</span><span class="sxs-lookup"><span data-stu-id="7332d-516">Maximum number of case holds for an organization</span></span>  <br/> |<span data-ttu-id="7332d-517">10,000</span><span class="sxs-lookup"><span data-stu-id="7332d-517">10,000</span></span>  <br/> |
|<span data-ttu-id="7332d-518">單一 case 保留中的信箱數量上限</span><span class="sxs-lookup"><span data-stu-id="7332d-518">Maximum number of mailboxes in a single case hold</span></span>  <br/> |<span data-ttu-id="7332d-519">1,000</span><span class="sxs-lookup"><span data-stu-id="7332d-519">1,000</span></span>  <br/> |
|<span data-ttu-id="7332d-520">與最大數目 SharePoint OneDrive 單一案例中的商務網站的保留</span><span class="sxs-lookup"><span data-stu-id="7332d-520">Maximum number of SharePoint and OneDrive for Business sites in a single case hold</span></span>  <br/> |<span data-ttu-id="7332d-521">100</span><span class="sxs-lookup"><span data-stu-id="7332d-521">100</span></span>  <br/> |
   
- <span data-ttu-id="7332d-p189">**因應在 [管理] 頁面上建立進階 ediscovery 的情況下？** 您可以按一下在 [ **eDiscovery** ] 頁面上的 [安全性] 下方的連結來存取較舊的進階的 eDiscovery 案例的清單&amp;規範中心。不過，執行較舊的案例中的任何工作，您必須連絡 Office 365 支援人員並要求大小寫要移至新的 eDiscovery 案例安全性&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="7332d-p189">**What about cases that were created on the case management page in Advanced eDiscovery?** You can access a list of older Advanced eDiscovery cases by clicking the link at the bottom on the **eDiscovery** page in the Security &amp; Compliance Center. However, to do any work in an older case, you have to contact Office 365 Support and request that the case be moved to a new eDiscovery case in the Security &amp; Compliance Center.</span></span> 
    
- <span data-ttu-id="7332d-p190">**為什麼要選擇建立 [eDiscovery 管理員？** 如先前清楚，系統管理員是可以檢視及存取您組織中所有的 eDiscovery 案例 eDiscovery 管理員角色群組的成員 eDiscovery。這項功能來存取所有的 eDiscovery 案例有兩個重要的用途：</span><span class="sxs-lookup"><span data-stu-id="7332d-p190">**Why create an eDiscovery Administrator?** As previously explained, an eDiscovery Administrator is member of the eDiscovery Manager role group who can view and access all eDiscovery cases in your organization. This ability to access all the eDiscovery cases has two important purposes:</span></span>
    
  - <span data-ttu-id="7332d-p191">如果 eDiscovery 案例的唯一成員的人員離開貴組織，因為他們未成員任何人 （包括組織管理角色群組的成員或另一個 eDiscovery 管理員角色群組的成員） 是可存取該 eDiscovery 案例案例。在此情況下，就會有任何方法，以存取案例中的資料。但 eDiscovery 管理員可以存取所有在組織中的 eDiscovery 案例，因為他們可以檢視案例安全性&amp;規範中心並將其本身或另一個 eDiscovery 管理員新增為大小寫的成員。</span><span class="sxs-lookup"><span data-stu-id="7332d-p191">If a person who is the only member of an eDiscovery case leaves your organization, no one (including members of the Organization Management role group or another member of the eDiscovery Manager role group) can access that eDiscovery case because they aren't a member of a case. In this situation, there would be no way to access the data in the case. But because an eDiscovery Administrator can access all eDiscovery cases in the organization, they can view the case in the Security &amp; Compliance Center and add themselves or another eDiscovery manager as a member of the case.</span></span>
    
  - <span data-ttu-id="7332d-p192">EDiscovery 系統管理員可以檢視及存取所有的 eDiscovery 案例，因為他們可以稽核和監督所有案例和相關聯的內容搜尋。這有助於防止任何誤用內容搜尋或 eDiscovery 案例。與因為 eDiscovery 系統管理員可以存取內容的搜尋結果中的潛在敏感資訊，您應該限制的 eDiscovery 管理員的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="7332d-p192">Because an eDiscovery Administrator can view and access all eDiscovery cases, they can audit and oversee all cases and associated Content Searches. This can help to prevent any misuse of Content Searches or eDiscovery cases. And because eDiscovery Administrators can access potentially sensitive information in the results of a Content Search, you should limit the number of people who are eDiscovery Administrators.</span></span>
    
    <span data-ttu-id="7332d-p193">最後，如先前清楚、 eDiscovery 管理員可以在 [安全性]&amp;規範中心會自動新增為進階 ediscovery 的管理員。這表示 eDiscovery 管理員的人員可執行的使用者設定、 建立的情況下，並將資料新增到的情況下進階 eDiscovery 的管理工作。</span><span class="sxs-lookup"><span data-stu-id="7332d-p193">Finally, as previous explained, eDiscovery Administrators in the Security &amp; Compliance Center are automatically added as administrators in Advanced eDiscovery. That means a person who is an eDiscovery Administrator can perform administrative tasks in Advanced eDiscovery, such as setting up users, creating cases, and adding data to cases.</span></span>
    
<span data-ttu-id="7332d-534"><<<<<<< 標頭</span><span class="sxs-lookup"><span data-stu-id="7332d-534"><<<<<<< HEAD</span></span>
- <span data-ttu-id="7332d-p194">**授權的內容位置置於保留需求為何吗？** 一般而言，組織需要的 Office 365 E3 訂閱或更高的內容位置置於保留。若要將信箱就地保留，皆需有 Exchange Online 計劃 2 授權。如需詳細資訊，請參閱此[eDiscovery 常見問題集](https://support.office.com/article/9d1a29ae-b7b4-4a27-9c8c-84289023dcae#Q5)。=======</span><span class="sxs-lookup"><span data-stu-id="7332d-p194">**What are the licensing requirements to place content locations on hold?** In general, organizations require an Office 365 E3 subscription or higher to place content locations on hold. To place mailboxes on hold, an Exchange Online Plan 2 license is required. For more information, see this [eDiscovery FAQ](https://support.office.com/article/9d1a29ae-b7b4-4a27-9c8c-84289023dcae#Q5). =======</span></span>
- <span data-ttu-id="7332d-p195">**授權的內容位置置於保留需求為何吗？** 一般而言，組織需要的 Office 365 E3 訂閱或更高的內容位置置於保留。若要將信箱就地保留，皆需有 Exchange Online 計劃 2 授權。如需詳細資訊，請參閱此[常見問題集](https://support.office.com/article/9d1a29ae-b7b4-4a27-9c8c-84289023dcae.aspx#Q5)。</span><span class="sxs-lookup"><span data-stu-id="7332d-p195">**What are the licensing requirements to place content locations on hold?** In general, organizations require an Office 365 E3 subscription or higher to place content locations on hold. To place mailboxes on hold, an Exchange Online Plan 2 license is required. For more information, see this [FAQ](https://support.office.com/article/9d1a29ae-b7b4-4a27-9c8c-84289023dcae.aspx#Q5).</span></span>
>>>>>>> <span data-ttu-id="7332d-541">deniseb 轉換</span><span class="sxs-lookup"><span data-stu-id="7332d-541">deniseb-conversion</span></span>
    
- <span data-ttu-id="7332d-p196">**還有什麼應該您了解在步驟 5 中搜尋所有案例的內容？** 如先前所述，您可以搜尋的大小寫保留在內容位置。當您這麼做時，保留條件會比對的內容為 [搜尋]。如果沒有任何保留準則，將搜尋所有內容。如果內容上查詢式保留，只會比對這兩個保留準則 （放在步驟 4 中保留） 的內容及搜尋準則 （從步驟 5 中搜尋） 會傳回與搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="7332d-p196">**What else should you know about searching all case content in Step 5?** As previously explained, you can search the the content locations that have been placed on hold in the case. When you do this, only the content that matches the hold criteria is search. If there is no hold criteria, all content is searched. If contents are on a query-based hold, only the content that matches both hold criteria (from the hold placed in Step 4) and the search criteria (from the search in Step 5) is returned with the search results.</span></span>
    
    <span data-ttu-id="7332d-546">以下是搜尋所有案例的內容時請牢記的一些其他事項：</span><span class="sxs-lookup"><span data-stu-id="7332d-546">Here are some other things to keep in mind when searching all case content:</span></span>
    
  - <span data-ttu-id="7332d-p197">如果內容的位置是在相同的案例中的多個保留的一部分，保留查詢來結合**OR**運算子時搜尋的內容位置，使用所有案例內容] 選項。同樣地，如果內容位置屬於兩個不同保留，其中一個是查詢為基礎而另一個是設為無限期保留 （其中的所有內容都處於保留狀態），則所有內容將會無限期保留因都是搜尋。</span><span class="sxs-lookup"><span data-stu-id="7332d-p197">If a content location is part of multiple holds within the same case, the hold queries are combined by an **OR** operator when you search that content location using the all case content option. Similarly, if a content location is part of two different holds, where one is query-based and the other is an infinite hold (where all content is placed on hold), then all content will be search because of the infinite hold.</span></span> 
    
  - <span data-ttu-id="7332d-p198">如果內容搜尋是案例和您已設定要搜尋所有案例的內容，然後 （藉由新增或移除內容的位置或變更保留查詢） 變更保留這些變更更新的搜尋設定。不過，您必須重新執行搜尋之後保留變更來更新的搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="7332d-p198">If a content search is for a case and you've configured it to search all case content and then you change a hold (by adding or removing a content location or changing the hold query), the search configuration is updated with those changes. However, you have to re-run the search after the hold is changed to update the search results.</span></span>
    
  - <span data-ttu-id="7332d-p199">如果多個案例保留會放在 eDiscovery 案例中的內容位置且選取搜尋所有案例的內容、 關鍵字的搜尋查詢數目上限為 500。那是因為內容的搜尋將所有查詢式保留結合使用**OR**運算子。如果有超過 500 個關鍵字中合併保留查詢及內容的搜尋查詢，然後搜尋信箱中的所有內容，而不只是符合任何查詢為基礎的案例該內容保留。</span><span class="sxs-lookup"><span data-stu-id="7332d-p199">If multiple case holds are placed on a content location in an eDiscovery case and you select to search all case content, the maximum number of keywords for that search query is 500. That's because the content search combines all the query-based holds by using the **OR** operator. If there are more than 500 keywords in the combined hold queries and the content search query, then all content in the mailbox is searched, not just that content that matches the any of query-based case holds.</span></span> 
    
  - <span data-ttu-id="7332d-554">如果 case 保留的**開啟**狀態，您仍然可以搜尋案例的內容位置在已開啟保留。</span><span class="sxs-lookup"><span data-stu-id="7332d-554">If a case hold has a status of **Turning on**, you can still search the case content locations while the hold is being turned on.</span></span>
    
  - <span data-ttu-id="7332d-p200">如先前所述，如果搜尋設定成搜尋所有案例的內容，則您不能包含搜尋如果您想要匯出的多個搜尋結果。如果搜尋設定成搜尋所有案例的內容，然後您必須將匯出的單一搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="7332d-p200">As previously stated, if a search is configured to search all case content, then you can't include that search if you want to export the results of multiple searches. If a search is configured to search all case content, then you'll have to export the results of that single search.</span></span>
    
- <span data-ttu-id="7332d-p201">**不住在 Office 365 群組及 Microsoft 小組中放置保留吗？** Office 365 群組之內建的 Microsoft 小組。因此，將其置於保留 eDiscovery 案例中是非常類似。將 Office 365 群組和上的 Microsoft 小組保留狀態時請記住下列事項。</span><span class="sxs-lookup"><span data-stu-id="7332d-p201">**What about placing a hold on Office 365 Groups and Microsoft Teams?** Microsoft Teams are built on Office 365 Groups. Therefore, placing them on hold in an eDiscovery case is very similar. Keep the following things in mind when placing Office 365 Groups and Microsoft Teams on hold.</span></span> 
    
  - <span data-ttu-id="7332d-561">若要放置音樂位於 Office 365 群組及 Microsoft 小組中的內容，您必須指定的信箱與 SharePoint 網站的群組或小組與之相關聯。</span><span class="sxs-lookup"><span data-stu-id="7332d-561">To place content located in Office 365 Groups and Microsoft Teams on hold, you have to specify the mailbox and SharePoint site that associated with a group or team.</span></span>
    
  - <span data-ttu-id="7332d-p202">執行**Get UnifiedGroup** cmdlet 在 Exchange Online 中檢視 Office 365 群組或 Microsoft 小組的屬性。這是一個好方法來取得具有相關聯的 Office 365 群組或 Microsoft 小組網站的 URL。例如，下列命令會顯示所選的屬性名為資深領導小組 Office 365 群組：</span><span class="sxs-lookup"><span data-stu-id="7332d-p202">Run the **Get-UnifiedGroup** cmdlet in Exchange Online to view properties for an Office 365 Group or Microsoft Team. This is a good way to get the URL for the site that's associated with an Office 365 Group or a Microsoft Team. For example, the following command displays selected properties for an Office 365 Group named Senior Leadership Team:</span></span> 
    
  ```
  Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
  DisplayName            : Senior Leadership Team
  Alias                  : seniorleadershipteam
  PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
  SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
  
  ```

    > [!NOTE]
    > <span data-ttu-id="7332d-565">若要執行**Get UnifiedGroup**指令程式，您必須指派 「 僅檢視收件者 」 角色在 Exchange Online 或角色群組的成員，已指派 「 僅檢視收件者 」 角色。</span><span class="sxs-lookup"><span data-stu-id="7332d-565">To run the **Get-UnifiedGroup** cmdlet, you have to be assigned the View-Only Recipients role in Exchange Online or be a member of a role group that's assigned the View-Only Recipients role.</span></span> 
  
  - <span data-ttu-id="7332d-p203">當使用者的信箱搜尋時，將不會搜尋所有 Office 365 群組或使用者為其成員的 Microsoft 小組。同樣地，當撥打 Office 365 群組或 Microsoft 小組保留，只有群組信箱和群組網站會放在保留;信箱和 OneDrive for Business 網站群組成員的不處於保留狀態除非您明確地將其新增保留。因此，如果您基於法律考量，保留上放置在 Office 365 群組或 Microsoft 小組需要考慮新增信箱和 OneDrive 商務網站的群組和小組成員在相同的音樂。</span><span class="sxs-lookup"><span data-stu-id="7332d-p203">When a user's mailbox is searched, any Office 365 Group or Microsoft Team that the user is a member of won't be searched. Similarly, when you place an Office 365 Group or Microsoft Team hold, only the group mailbox and group site are placed on hold; the mailboxes and OneDrive for Business sites of group members aren't placed on hold unless you explicitly add them to the hold. Therefore, if you the need to place an Office 365 Group or Microsoft Team on hold for a legal reasons, consider adding the mailboxes and OneDrive for Business sites for group and team members on the same hold.</span></span>
    
  - <span data-ttu-id="7332d-p204">若要取得 Office 365 群組或 Microsoft 小組成員的清單，您可以檢視屬性**首頁\>群組**頁面上的 Office 365 系統管理中心。或者，您可以在 Exchange Online PowerShell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="7332d-p204">To get a list of the members of a Office 365 Group or Microsoft Team, you can view the properties on the **Home \> Groups** page in the Office 365 admin center. Alternatively, you can run the following command in Exchange Online PowerShell:</span></span> 
    
  ```
  Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress 
  ```

    > [!NOTE]
    > <span data-ttu-id="7332d-571">若要執行**Get UnifiedGroupLinks**指令程式，您必須指派 「 僅檢視收件者 」 角色在 Exchange Online 或角色群組的成員，已指派 「 僅檢視收件者 」 角色。</span><span class="sxs-lookup"><span data-stu-id="7332d-571">To run the **Get-UnifiedGroupLinks** cmdlet, you have to be assigned the View-Only Recipients role in Exchange Online or be a member of a role group that's assigned the View-Only Recipients role.</span></span> 
  
  - <span data-ttu-id="7332d-p205">屬於 Microsoft 小組通道的交談會儲存在具有 Microsoft 小組與相關聯的信箱。同樣地，小組成員共用通道中的檔案都會儲存在團隊的 SharePoint 網站上。因此，您必須將 Microsoft 小組信箱和 SharePoint 網站上的保留要保留交談和通道中的檔案。</span><span class="sxs-lookup"><span data-stu-id="7332d-p205">Conversations that are part of a Microsoft Teams channel are stored in the mailbox that's associated with the Microsoft Team. Similarly, files that team members share in a channel are stored on the team's SharePoint site. Therefore, you have to place the Microsoft Team mailbox and SharePoint site on hold to retain conversations and files in a channel.</span></span>
    
    <span data-ttu-id="7332d-p206">或者，是 [聊天室] 清單中的 Microsoft 小組的一部分的交談會儲存在信箱的使用者參與交談。與使用者共用聊天交談中的檔案都會儲存在 OneDrive for Business 網站共用檔案的使用者。因此，您必須將個別使用者信箱並 OneDrive for Business 網站上按住保留交談和在 [聊天室] 清單中的檔案。這就是為什麼很好置於除了放置小組信箱 （及網站） 的 Microsoft 小組成員之信箱的保留音樂。</span><span class="sxs-lookup"><span data-stu-id="7332d-p206">Alternatively, conversations that are part of the Chat list in Microsoft Teams are stored in the mailbox of the user's who participate in the chat. And files that a user shares in Chat conversations are stored in the OneDrive for Business site of the user who shares the file. Therefore, you have to place the individual user mailboxes and OneDrive for Business sites on hold to retain conversations and files in the Chat list. That's why it's a good idea to place a hold on the mailboxes of members of a Microsoft Team in addition to placing the team mailbox (and site) on hold.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7332d-p207">參與交談屬於 [聊天室] 清單中的 Microsoft 小組的使用者必須具有 （雲端） 的 Exchange Online 信箱以保留信箱處於 eDiscovery 保留狀態時的交談的交談。那是因為交談屬於 [聊天室] 清單會儲存在雲端架構信箱的交談參與者。如果交談參與者都不會有 Exchange Online 信箱，將不能夠保留交談的交談。例如，在 Exchange 混合部署，可能會能夠參與交談屬於 [聊天室] 清單中的 Microsoft 小組與內部部署信箱的使用者。但在此例中，從這些交談內容無法保留因為使用者沒有雲端架構信箱。</span><span class="sxs-lookup"><span data-stu-id="7332d-p207">Users who participate in conversations that are part of the Chat list in Microsoft Teams must have an Exchange Online (cloud-based) mailbox in order to retain chat conversations when the mailbox is placed on an eDiscovery hold. That's because conversations that are part of the Chat list are stored in the cloud-based mailboxes of the chat participants. If a chat participant doesn't have an Exchange Online mailbox, you won't be able to retain chat conversations. For example, in an Exchange hybrid deployment, users with an on-premises mailbox might be able to participate in conversations that are part of the Chat list in Microsoft Teams. However in this case, content from these conversation can't be retained because the users don't have cloud-based mailboxes.</span></span> 
  
  - <span data-ttu-id="7332d-p208">每個 Microsoft 小組或小組通道包含 Wiki 筆記記錄與共同作業。Wiki 內容會自動儲存至含有.mht 格式的檔案。此檔案儲存在團隊的 SharePoint 網站上的小組 Wiki 資料文件庫。您可以利用音樂 Wiki 內容所保留上放置團隊的 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="7332d-p208">Every Microsoft Team or team channel contains a Wiki for note-taking and collaboration. The Wiki content is automatically saved to a file with a .mht format. This file is stored in the Teams Wiki Data document library on the team's SharePoint site. You can place the content in the Wiki on hold by placing the team's SharePoint site on hold.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7332d-p209">要保留的 Microsoft 小組或小組通道 Wiki 內容 （如果您保留上放置團隊的 SharePoint 網站） 的功能已於 2017 年 6 月 22 日發行。如果小組網站上保留，將啟動到期保留內容 wiki （英文）。不過，如果小組網站會保留與 Wiki 內容已遭刪除之前 2017 年 6 月 22 Wiki 內容已不會保留。</span><span class="sxs-lookup"><span data-stu-id="7332d-p209">The capability to retain Wiki content for a Microsoft Team or team channel (when you place the team's SharePoint site on hold) was released on June 22, 2017. If a team site is on hold, the Wiki content will be retained starting on that date. However, if a team site is on hold and the Wiki content was deleted before June 22, 2017, the Wiki content was not retained.</span></span> 
  
- <span data-ttu-id="7332d-p210">**如何尋找 onedrive 的 URL 放商務網站？** 若要收集的 Url 清單 onedrive，如，因此您可以將其新增至保留或搜尋您組織中的商務網站相關聯 eDiscovery 案例，請參閱[建立您的組織中的所有 OneDrive 位置的清單](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a)。本文中的此指令碼會建立包含的所有 OneDrive 網站清單的文字檔案。若要執行此指令碼，您必須安裝及使用 SharePoint Online 管理命令介面。請務必附加至每個想要搜尋的 OneDrive 網站的組織的我的網站網域的 URL。這是包含您 OneDrive; 的網域例如， `https://contoso-my.sharepoint.com`。以下是使用者的 OneDrive 網站的 URL 範例： `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`。</span><span class="sxs-lookup"><span data-stu-id="7332d-p210">**How do I find the URL for OneDrive for Business sites?** To collect a list of the URLs for the OneDrive for Business sites in your organization so you can add them to a hold or search associated with an eDiscovery case, see [Create a list of all OneDrive locations in your organization](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a). This script in this article creates a text file that contains a list of all OneDrive sites. To run this script, you'll have to install and use the SharePoint Online Management Shell. Be sure to append the URL for your organization's MySite domain to each OneDrive site that you want to search. This is the domain that contains all your OneDrive; for example,  `https://contoso-my.sharepoint.com`. Here's an example of a URL for a user's OneDrive site:  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`.</span></span>