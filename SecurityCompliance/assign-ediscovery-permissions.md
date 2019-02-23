---
title: Office 365 安全性 eDiscovery 權限指派&amp;規範中心
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 5b9a067b-9d2e-4aa5-bb33-99d8c0d0b5d7
description: 指派權限才能執行 eDiscovery 相關的工作使用安全性&amp;規範中心。
ms.openlocfilehash: c4dcbf51282aa2887fd7d5032eb8587b5e9d56d7
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223272"
---
# <a name="assign-ediscovery-permissions-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="802c3-103">Office 365 安全性 eDiscovery 權限指派&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="802c3-103">Assign eDiscovery permissions in the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="802c3-p101">如果您想使用 eDiscovery 相關任何的工具 Office 365 安全性人員&amp;規範中心，您必須將它們指派適當的權限。為達成此目的最簡單的方法是在 Office 365 安全性**權限**] 頁面上新增適當的角色群組的人員&amp;規範中心。本主題說明執行 eDiscovery 相關之工作使用安全性所需的權限&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="802c3-p101">If you want people to use any of the eDiscovery-related tools in the Office 365 Security &amp; Compliance Center, you have to assign them the appropriate permissions. The easiest way to do this is to add the person the appropriate role group on the **Permissions** page in the Office 365 Security &amp; Compliance Center. This topic describes the permissions required to perform eDiscovery-related tasks using the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="802c3-p102">主要 eDiscovery 相關的角色群組安全性&amp;規範中心會呼叫**eDiscovery 管理員**。有兩個子群組內此角色群組。</span><span class="sxs-lookup"><span data-stu-id="802c3-p102">The primary eDiscovery-related role group in Security &amp; Compliance Center is called **eDiscovery Manager**. There are two subgroups within this role group.</span></span> 
  
- <span data-ttu-id="802c3-p103">**eDiscovery 經理**-eDiscovery 管理員可以使用 「 內容搜尋工具安全性&amp;規範中心來執行各種與搜尋相關動作，例如預覽與匯出搜尋及搜尋組織中的內容位置結果。成員也可以建立與管理 eDiscovery 案例、 新增和移除成員案例、 建立 case 保留及執行內容與案例中為及存取 Office 365 進階 ediscovery case 資料相關聯的搜尋。 EDiscovery 管理員，才能存取及管理他們所建立的案例。他們無法存取或管理其他 eDiscovery 管理員所建立的案例。</span><span class="sxs-lookup"><span data-stu-id="802c3-p103">**eDiscovery Managers** - An eDiscovery Manager can use the Content Search tool in the Security &amp; Compliance Center to search content locations in the organization, and perform various search-related actions such as preview and export search results. Members can also create and manage eDiscovery cases, add and remove members to a case, create case holds, and run Content Searches associated with a case, and access case data in Office 365 Advanced eDiscovery.  An eDiscovery Managers can only access and manage the cases they create. They can't access or manage cases created by other eDiscovery Managers.</span></span> 
    
- <span data-ttu-id="802c3-p104">**eDiscovery 管理員**-eDiscovery 管理員 eDiscovery 管理員角色群組的成員，且可以執行相同的內容搜尋與 eDiscovery 管理員可執行區分管理相關的工作。此外，eDiscovery 管理員可以：</span><span class="sxs-lookup"><span data-stu-id="802c3-p104">**eDiscovery Administrators** - An eDiscovery Administrator is a member of the eDiscovery Manager role group, and can perform the same Content Search and case management-related tasks that an eDiscovery Manager can perform. Additionally, an eDiscovery Administrator can:</span></span> 
    
  - <span data-ttu-id="802c3-115">存取已列在 [安全性] 中的**eDiscovery 案例**] 頁面上的所有案例&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="802c3-115">Access all cases that are listed on the **eDiscovery cases** page in the Security &amp; Compliance Center.</span></span> 

  - <span data-ttu-id="802c3-116">存取 case 進階 eDiscovery 針對在組織中任何案例中的資料。</span><span class="sxs-lookup"><span data-stu-id="802c3-116">Access case data in Advanced eDiscovery for any case in the organization.</span></span>
    
  - <span data-ttu-id="802c3-117">在自行新增為案例的成員之後管理任何 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="802c3-117">Manage any eDiscovery case after they add themself as a member of the case.</span></span>
  
  <span data-ttu-id="802c3-118">請參閱您可能會想 eDiscovery 管理員在組織中原因[的詳細資訊](#more-information)] 區段中。</span><span class="sxs-lookup"><span data-stu-id="802c3-118">See the [More information](#more-information) section for reasons why you might want eDiscovery Administrators in your organization.</span></span> 

> [!NOTE]
> <span data-ttu-id="802c3-p105">若要分析使用進階的 eDiscovery 的使用者資料，使用者 (資料 okay) 必須指派 Office 365 E5 授權。或者，使用 Office 365 E1 或 E3 授權的使用者可以將指派進階的 eDiscovery 獨立授權。系統管理員及法務人員對於已指派給的情況下並使用進階的 eDiscovery 分析資料不需要的 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="802c3-p105">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license. Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license. Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="802c3-122">開始之前</span><span class="sxs-lookup"><span data-stu-id="802c3-122">Before you begin</span></span>

- <span data-ttu-id="802c3-123">您必須是 「 組織管理角色群組的成員 （或要指派的角色管理角色） 指派 eDiscovery 權限安全性&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="802c3-123">You have to be a member of the Organization Management role group (or be assigned the Role Management role) to assign eDiscovery permissions in the Security &amp; Compliance Center.</span></span>
    
- <span data-ttu-id="802c3-p106">您可以使用[Add-rolegroupmember](https://technet.microsoft.com/en-us/library/dd638207%28v=exchg.160%29.aspx)指令程式的安全性&amp;規範中心 PowerShell 將擁有郵件功能的安全性群組新增為 eDiscovery 管理員角色群組中的 eDiscovery 管理員子群組的成員。不過，您無法將擁有郵件功能的安全性群組新增至 eDiscovery 管理員子群組。請參閱如需詳細資訊[的詳細資訊](#more-information)] 區段。</span><span class="sxs-lookup"><span data-stu-id="802c3-p106">You can use the [Add-RoleGroupMember](https://technet.microsoft.com/en-us/library/dd638207%28v=exchg.160%29.aspx) cmdlet in Security &amp; Compliance Center PowerShell to add a mail-enabled security group as a member of the eDiscovery Managers subgroup in the eDiscovery Manager role group. However, you can't add a mail-enabled security group to the eDiscovery Administrators subgroup. See the [More information](#more-information) section for more details.</span></span> 
    
## <a name="assign-ediscovery-permissions-in-the-security-amp-compliance-center"></a><span data-ttu-id="802c3-127">在 [安全性] 中的 eDiscovery 權限指派&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="802c3-127">Assign eDiscovery permissions in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="802c3-128">移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="802c3-128">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="802c3-129">使用公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="802c3-129">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="802c3-130">在 [安全性] 的左窗格中&amp;規範中心按一下**權限**，然後再按一下 [ **eDiscovery 管理員**] 旁的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="802c3-130">In the left pane of the Security &amp; Compliance Center, click **Permissions**, and then click the checkbox next to **eDiscovery Manager**.</span></span>
    
4. <span data-ttu-id="802c3-131">在 [ **eDiscovery 管理員**彈出式] 頁面上執行根據想要指定 eDiscovery 權限的下列其中之一。</span><span class="sxs-lookup"><span data-stu-id="802c3-131">On the **eDiscovery Manager** flyout page, do one of the following based on the eDiscovery permissions that you want to assign.</span></span> 
    
  - <span data-ttu-id="802c3-p107">**若要讓使用者 eDiscovery 管理員\*\*\*\*EDiscovery 管理員**] 旁按一下 [**編輯**]。[**選定 eDiscovery 管理員**，按一下 [**編輯**] 和 [![新增圖示](media/ITPro-EAC-AddIcon.gif)**新增]**。選取的使用者 （或使用者） 您要新增為 eDiscovery 管理員] 中，然後按一下 [**新增]**。新增使用者完成後，按一下 [**完成**]。然後，在 [**編輯選擇 eDiscovery 管理員**彈出式] 頁面上按一下 [**儲存**] 以將變更儲存至 eDiscovery 管理員成員資格。</span><span class="sxs-lookup"><span data-stu-id="802c3-p107">**To make a user an eDiscovery Manager** Next to **eDiscovery Manager**, click **Edit**. Under **Selected eDiscovery Managers**, click **Edit**, and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **Add**. Select the user (or users) you want to add as an eDiscovery manager, and then click **Add**. When you're finished adding users, click **Done**. Then, on the **Editing Choose eDiscovery Manager** flyout page, click **Save** to save the changes to the eDiscovery Manager membership.</span></span> 
    
  - <span data-ttu-id="802c3-p108">**若要讓使用者 eDiscovery 管理員\*\*\*\*EDiscovery 管理員**] 旁按一下 [**編輯**]。[**選定 eDiscovery 管理員**，按一下 [**編輯**] 和 [![新增圖示](media/ITPro-EAC-AddIcon.gif)**新增]**。選取的使用者 （或使用者） 您要新增為 eDiscovery 管理員，然後按一下 [**新增]**。新增使用者完成後，按一下 [**完成**]。然後，在 [**編輯選擇 eDiscovery 管理員**彈出式] 頁面上按一下 [**儲存**] 以將變更儲存至 eDiscovery 管理員的成員資格。</span><span class="sxs-lookup"><span data-stu-id="802c3-p108">**To make a user an eDiscovery Administrator** Next to **eDiscovery Administrator**, click **Edit**. Under **Selected eDiscovery Administrators**, click **Edit**, and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **Add**. Select the user (or users) you want to add as an eDiscovery Administrator, and then click **Add**. When you're finished adding users, click **Done**. Then, on the **Editing Choose eDiscovery Administrator** flyout page, click **Save** to save the changes to the eDiscovery Administrator membership.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="802c3-p109">您也可以使用**Add eDiscoveryCaseAdmin**指令程式，讓使用者 eDiscovery 管理員。不過，使用者必須具有案例管理角色才可以使用此指令程式，使其 eDiscovery 管理員。如需詳細資訊，請參閱 ＜ [Add eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkID=798217)。</span><span class="sxs-lookup"><span data-stu-id="802c3-p109">You can also use the **Add-eDiscoveryCaseAdmin** cmdlet to make a user an eDiscovery Administrator. However, the user must be assigned the Case Management role before you can use this cmdlet to make them an eDiscovery Administrator. For more information, see [Add-eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkID=798217).</span></span> 
  
<span data-ttu-id="802c3-p110">在 [安全性]**權限**] 頁面上&amp;規範中心，您也可以指派使用者 eDiscovery 相關的權限透過將它們新增至 [規範管理員、 組織管理及檢閱者 」 角色群組。EDiscovery 與相關 RBAC 角色指派給每個這些角色群組的說明，請參閱[RBAC 角色與 eDiscovery 相關](#rbac-roles-related-to-ediscovery)] 區段中。</span><span class="sxs-lookup"><span data-stu-id="802c3-p110">On the **Permissions** page in the Security &amp; Compliance Center, you can also assign users eDiscovery-related permissions, by adding them to the Compliance Administrator, Organization Management, and Reviewer role groups. For a description of the eDiscovery-related RBAC roles assigned to each of these role groups, see the [RBAC roles related to eDiscovery](#rbac-roles-related-to-ediscovery) section.</span></span> 

## <a name="rbac-roles-related-to-ediscovery"></a><span data-ttu-id="802c3-147">EDiscovery 與相關的 RBAC 角色</span><span class="sxs-lookup"><span data-stu-id="802c3-147">RBAC roles related to eDiscovery</span></span>

<span data-ttu-id="802c3-148">下表列出 eDiscovery 相關的 RBAC 角色的安全性 & 規範中心並指出每個角色指派給預設的內建角色群組。</span><span class="sxs-lookup"><span data-stu-id="802c3-148">The following table lists the eDiscovery-related RBAC roles in the Security & Compliance Center, and indicates the built-in role groups that each role is assigned to by default.</span></span> 
    
|<span data-ttu-id="802c3-149">**角色**</span><span class="sxs-lookup"><span data-stu-id="802c3-149">**Role**</span></span>|<span data-ttu-id="802c3-150">**規範系統管理員**</span><span class="sxs-lookup"><span data-stu-id="802c3-150">**Compliance Administrator**</span></span>|<span data-ttu-id="802c3-151">**eDiscovery 管理員 & 管理員**</span><span class="sxs-lookup"><span data-stu-id="802c3-151">**eDiscovery Manager & Administrator**</span></span>|<span data-ttu-id="802c3-152">**組織管理**</span><span class="sxs-lookup"><span data-stu-id="802c3-152">**Organization Management**</span></span>|<span data-ttu-id="802c3-153">**檢閱者**</span><span class="sxs-lookup"><span data-stu-id="802c3-153">**Reviewer**</span></span>|
|:-----|:-----:|:-----:|:-----:|:-----:|
|<span data-ttu-id="802c3-154">管理 （英文）</span><span class="sxs-lookup"><span data-stu-id="802c3-154">Case Management</span></span> <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|<span data-ttu-id="802c3-158">合規性搜尋</span><span class="sxs-lookup"><span data-stu-id="802c3-158">Compliance Search</span></span> <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|<span data-ttu-id="802c3-162">匯出</span><span class="sxs-lookup"><span data-stu-id="802c3-162">Export</span></span> <br/> | <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> | <br/> |
|<span data-ttu-id="802c3-164">保留</span><span class="sxs-lookup"><span data-stu-id="802c3-164">Hold</span></span> <br/>  |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|<span data-ttu-id="802c3-168">預覽</span><span class="sxs-lookup"><span data-stu-id="802c3-168">Preview</span></span> <br/>  | <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> | <br/> |
|<span data-ttu-id="802c3-170">檢閱 </span><span class="sxs-lookup"><span data-stu-id="802c3-170">Review</span></span> <br/>  | <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |
|<span data-ttu-id="802c3-173">RMS 解密</span><span class="sxs-lookup"><span data-stu-id="802c3-173">RMS Decrypt</span></span> <br/>  ||![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |||
|<span data-ttu-id="802c3-175">搜尋和清除</span><span class="sxs-lookup"><span data-stu-id="802c3-175">Search And Purge</span></span> <br/> | <br/> | <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> | <br/> | 
||||
  
<span data-ttu-id="802c3-177">下列各節說明上表中所列的 eDiscovery 相關 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="802c3-177">The following sections describe each of the eDiscovery-related RBAC roles listed in the previous table.</span></span>

### <a name="case-management"></a><span data-ttu-id="802c3-178">管理 （英文）</span><span class="sxs-lookup"><span data-stu-id="802c3-178">Case Management</span></span>

<span data-ttu-id="802c3-p111">此角色可讓使用者建立、 編輯、 刪除及控制安全性 & 規範中心中的 eDiscovery 案例的存取。如需詳細資訊，請參閱[管理 Office 365 安全性的 eDiscovery 案例&amp;規範中心](manage-ediscovery-cases.md)。如先前所述，使用者必須具有案例管理角色才可以使用**Add eDiscoveryCaseAdmin**指令程式，使其 eDiscovery 管理員。</span><span class="sxs-lookup"><span data-stu-id="802c3-p111">This role lets users create, edit, delete, and control access to eDiscovery cases in the Security & Compliance Center. For more information, see [Manage eDiscovery cases in the Office 365 Security &amp; Compliance Center](manage-ediscovery-cases.md). As previously explained, a user must be assigned the Case Management role before you can use the **Add-eDiscoveryCaseAdmin** cmdlet to make them an eDiscovery Administrator.</span></span> 

### <a name="compliance-search"></a><span data-ttu-id="802c3-182">合規性搜尋</span><span class="sxs-lookup"><span data-stu-id="802c3-182">Compliance Search</span></span>

<span data-ttu-id="802c3-p112">此角色可讓使用者在安全性 & 規範中心來搜尋信箱與公用資料夾、 SharePoint Online 網站、 OneDrive for Business 網站 Skype for Business 交談、 Office 365 群組及 Microsoft 小組執行內容搜尋工具。此角色可讓使用者取得搜尋結果的評估並建立匯出報告，但其他角色不需要修改初始化內容搜尋動作，例如預覽、 匯出或刪除搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="802c3-p112">This role lets users run the Content Search tool in the Security & Compliance Center to search mailboxes and public folders, SharePoint Online sites, OneDrive for Business sites, Skype for Business conversations, Office 365 Groups, and Microsoft Teams. This role allows a user to get an estimate of the search results and create export reports, but additional roles are needed to initiate content search actions such as previewing, exporting, or deleting search results.</span></span>

<span data-ttu-id="802c3-p113">請注意使用者指派規範搜尋角色但不需要預覽角色可預覽其預覽巨集指令具有起始由使用者指派角色預覽搜尋結果。沒有預覽角色的使用者可以預覽最多 2 週的初始預覽巨集指令建立後的結果。</span><span class="sxs-lookup"><span data-stu-id="802c3-p113">Note that users assigned the Compliance Search role but don't have the Preview role can preview the results of a search in which the preview action has been initiated by a user that's assigned the Preview role. The user without the Preview role can preview results for up to 2 weeks after the initial preview action was created.</span></span>

<span data-ttu-id="802c3-p114">同樣地，指派給使用者的規範搜尋角色，但沒有角色可以下載中的匯出巨集指令具有由已指派 「 匯出 」 角色的使用者起始的搜尋結果匯出。沒有匯出角色的使用者可以下載最多 2 週後的初始匯出巨集指令建立的搜尋結果。之後，他們將無法除非某人匯出角色與重新啟動匯出下載結果。</span><span class="sxs-lookup"><span data-stu-id="802c3-p114">Similarly, users assigned the Compliance Search role but don't have the Export role can download the results of a search in which the export action has initiated by a user that's assigned the Export role. The user without the Export role can download the results of a search for up to 2 weeks after the initial export action was created. After that they won’t be able to download the results unless someone with the Export role restarts the export.</span></span>

<span data-ttu-id="802c3-190">如需詳細資訊，請參閱[Office 365 中的內容搜尋](content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="802c3-190">For more information, see [Content Search in Office 365](content-search.md).</span></span> 

### <a name="export"></a><span data-ttu-id="802c3-191">匯出</span><span class="sxs-lookup"><span data-stu-id="802c3-191">Export</span></span>

<span data-ttu-id="802c3-p115">角色可讓使用者將內容的搜尋結果匯出至本機電腦。它也可讓其準備分析進階在 eDiscovery 中搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="802c3-p115">The role lets users export the results of a Content Search to a local computer. It also lets them prepare search results for analysis in Advanced eDiscovery.</span></span> 

<span data-ttu-id="802c3-194">如需匯出搜尋結果的詳細資訊，請參閱[Office 365 安全性 & 規範中心的搜尋結果匯出](export-search-results.md)。</span><span class="sxs-lookup"><span data-stu-id="802c3-194">For more information about exporting search results, see [Export search results from the Office 365 Security & Compliance Center](export-search-results.md).</span></span>

### <a name="hold"></a><span data-ttu-id="802c3-195">保留</span><span class="sxs-lookup"><span data-stu-id="802c3-195">Hold</span></span>

<span data-ttu-id="802c3-p116">此角色可讓使用者將內容放入信箱、 公用資料夾、 網站、 商務交談的 Skype 按住上的 Office 365 群組。保留內容時，內容擁有者將仍能修改或刪除原始的內容，但會保留內容，直到撤除或保留期間到期。</span><span class="sxs-lookup"><span data-stu-id="802c3-p116">This role lets users place content in mailboxes, public folders, sites, Skype for Business conversations, and Office 365 groups on hold. When content is on hold, content owners will still be able to modify or delete the original content, but the content will be preserved until the hold is removed or until the hold duration expires.</span></span> 

<span data-ttu-id="802c3-198">如需保留的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="802c3-198">For more information about holds, see:</span></span>

- [<span data-ttu-id="802c3-199">在 Office 365 安全性 & 規範中心中的 eDiscovery 案例</span><span class="sxs-lookup"><span data-stu-id="802c3-199">eDiscovery cases in the Office 365 Security & Compliance Center</span></span>](ediscovery-cases.md) 
- [<span data-ttu-id="802c3-200">保留原則概觀</span><span class="sxs-lookup"><span data-stu-id="802c3-200">Overview of retention policies</span></span>](retention-policies.md)

### <a name="preview"></a><span data-ttu-id="802c3-201">預覽</span><span class="sxs-lookup"><span data-stu-id="802c3-201">Preview</span></span>

<span data-ttu-id="802c3-p117">此角色可讓使用者檢視內容的搜尋所傳回的項目清單。他們也必須能夠開啟並檢視來檢視其內容清單中的每個項目。</span><span class="sxs-lookup"><span data-stu-id="802c3-p117">This role lets users view a list of items that were returned from a Content Search. They'll also be able to open and view each item from the list to view its contents.</span></span>

### <a name="review"></a><span data-ttu-id="802c3-204">檢閱 </span><span class="sxs-lookup"><span data-stu-id="802c3-204">Review</span></span>

<span data-ttu-id="802c3-p118">此角色可讓使用者存取 Office 365 進階 ediscovery 案件資料。此角色的主要目的是讓使用者能夠存取進階 eDiscovery。會指定給此角色的使用者可以看到並開啟安全性 & 他們是成員的規範中心 [eDiscovery] 頁面上的情況下的清單。使用者存取的安全性 & 規範中心的案例之後，他們可以按一下 [**進階 ediscovery 參數**來存取及分析中進階 eDiscovery 案例的資料。此角色不允許使用者預覽與案例相關聯之內容搜尋的結果或執行其他內容搜尋或案例的管理工作。</span><span class="sxs-lookup"><span data-stu-id="802c3-p118">This role lets users access case data in Office 365 Advanced eDiscovery. The primary purpose of this role is to give users access to Advanced eDiscovery. Users who are assigned this role can see and open the list of cases on the eDiscovery page in the Security & Compliance Center that they are members of. After the user accesses a case in the Security & Compliance Center, they can click **Switch to Advanced eDiscovery** to access and analyze the case data in Advanced eDiscovery. This role doesn't allow the user to preview the results of a content search that's associated with the case or to perform other content search or case management tasks.</span></span>

### <a name="rms-decrypt"></a><span data-ttu-id="802c3-210">RMS 解密</span><span class="sxs-lookup"><span data-stu-id="802c3-210">RMS Decrypt</span></span>

<span data-ttu-id="802c3-p119">此角色可讓使用者解密 RMS 加密電子郵件訊息時匯出進階在 eDiscovery 中搜尋結果或準備進行分析的搜尋結果。如需關於解密在匯出期間的搜尋結果，請參閱[Office 365 安全性 & 規範中心的搜尋結果匯出](export-search-results.md)。</span><span class="sxs-lookup"><span data-stu-id="802c3-p119">This role lets users decrypt RMS-encrypted email messages when exporting search results or preparing search results for analysis in Advanced eDiscovery. For more information about decrypting search results during export, see [Export search results from the Office 365 Security & Compliance Center](export-search-results.md).</span></span>

### <a name="search-and-purge"></a><span data-ttu-id="802c3-213">搜尋和清除</span><span class="sxs-lookup"><span data-stu-id="802c3-213">Search And Purge</span></span>

<span data-ttu-id="802c3-p120">此角色可讓使用者執行大量移除相符的內容的搜尋準則的資料。如需詳細資訊，請參閱[Search for 和 Office 365 組織中的刪除電子郵件訊息](search-for-and-delete-messages-in-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="802c3-p120">This role lets users perform bulk removal of data matching the criteria of a content search. For more information, see [Search for and delete email messages in your Office 365 organization](search-for-and-delete-messages-in-your-organization.md).</span></span> 


## <a name="more-information"></a><span data-ttu-id="802c3-216">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="802c3-216">More information</span></span>

- <span data-ttu-id="802c3-p121">**為什麼要選擇建立 [eDiscovery 管理員？** 如先前清楚，系統管理員是可以檢視及存取您組織中所有的 eDiscovery 案例 eDiscovery 管理員角色群組的成員 eDiscovery。這項功能來存取所有的 eDiscovery 案例有兩個重要的用途：</span><span class="sxs-lookup"><span data-stu-id="802c3-p121">**Why create an eDiscovery Administrator?** As previously explained, an eDiscovery Administrator is member of the eDiscovery Manager role group who can view and access all eDiscovery cases in your organization. This ability to access all the eDiscovery cases has two important purposes:</span></span> 
    
  - <span data-ttu-id="802c3-p122">如果 eDiscovery 案例的唯一成員的人員離開貴組織，因為他們未成員任何人 （包括組織管理角色群組的成員或另一個 eDiscovery 管理員角色群組的成員） 是可存取該 eDiscovery 案例案例。在此情況下，就會有任何方法，以存取案例中的資料。但 eDiscovery 管理員可以存取所有在組織中的 eDiscovery 案例，因為他們可以檢視案例安全性&amp;規範中心並將其本身或另一個 eDiscovery 管理員新增為大小寫的成員。</span><span class="sxs-lookup"><span data-stu-id="802c3-p122">If a person who is the only member of an eDiscovery case leaves your organization, no one (including members of the Organization Management role group or another member of the eDiscovery Manager role group) can access that eDiscovery case because they aren't a member of a case. In this situation, there would be no way to access the data in the case. But because an eDiscovery Administrator can access all eDiscovery cases in the organization, they can view the case in the Security &amp; Compliance Center and add themselves or another eDiscovery manager as a member of the case.</span></span>
    
  - <span data-ttu-id="802c3-p123">EDiscovery 系統管理員可以檢視及存取所有的 eDiscovery 案例，因為他們可以稽核和監督所有案例和相關聯規範搜尋。這有助於防止任何誤用規範搜尋或 eDiscovery 案例。與因為 eDiscovery 系統管理員可以存取規範搜尋結果中的潛在敏感資訊，您應該限制的 eDiscovery 管理員的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="802c3-p123">Because an eDiscovery Administrator can view and access all eDiscovery cases, they can audit and oversee all cases and associated compliance searches. This can help to prevent any misuse of compliance searches or eDiscovery cases. And because eDiscovery Administrators can access potentially sensitive information in the results of a compliance search, you should limit the number of people who are eDiscovery Administrators.</span></span>
    
    <span data-ttu-id="802c3-p124">此外，eDiscovery 安全性管理員&amp;規範中心會自動新增為進階 ediscovery 的管理員。這表示人員必須 eDiscovery 管理員，才可執行進階的 eDiscovery、 使用者設定、 建立的情況下，以及將資料匯入案例的管理工作。</span><span class="sxs-lookup"><span data-stu-id="802c3-p124">Also, eDiscovery Administrators in the Security &amp; Compliance Center are automatically added as administrators in Advanced eDiscovery. That means a person must be an eDiscovery Administrator to perform administrative tasks in Advanced eDiscovery, such as setting up users, creating cases, and importing data in to a case.</span></span>
    
- <span data-ttu-id="802c3-p125">**可以新增群組安全性 eDiscovery 管理員角色群組的成員身分&amp;規範中心吗？** 如先前清楚，您可以使用**Add-rolegroupmember**指令程式的安全性 eDiscovery 管理員角色群組中的 eDiscovery 管理員子群組的成員身分新增擁有郵件功能的安全性群組&amp;規範中心 PowerShell。例如，您可以執行下列命令以將擁有郵件功能的安全性群組新增至 eDiscovery 管理員角色群組。</span><span class="sxs-lookup"><span data-stu-id="802c3-p125">**Can I add a group as a member of the eDiscovery Manager role group in the Security &amp; Compliance Center?** As previously explained, you can add a mail-enabled security group as a member of the eDiscovery Managers subgroup in the eDiscovery Manager role group by using the **Add-RoleGroupMember** cmdlet in Security &amp; Compliance Center PowerShell. For example, you can run the following command to add a mail-enabled security group to the eDiscovery Manager role group.</span></span> 
    
  ```
  Add-RoleGroupMember "eDiscovery Manager" -Member <name of security group>
  ```

    <span data-ttu-id="802c3-p126">請注意 Exchange 通訊群組或 Office 365 群組不受支援。您必須使用擁有郵件功能的安全群組，其中您可以在 Exchange Online PowerShell 中使用建立` New-DistributionGroup -Type Security `命令。您也可以建立擁有郵件功能的安全性群組 （及新增成員） Exchange 系統管理中心或 Office 365 系統管理中心中。請注意可能需要最多 60 分鐘後您建立的新擁有郵件功能的安全性設為可用來新增至 eDiscovery 管理員角色群組。</span><span class="sxs-lookup"><span data-stu-id="802c3-p126">Note that an Exchange distribution group or an Office 365 group aren't supported. You must use a mail-enabled security group, which you can create in Exchange Online PowerShell by using the ` New-DistributionGroup -Type Security ` command. You can also create a mail-enabled security group (and add members) in the Exchange admin center or in the Office 365 admin center. Note that it might take up to 60 minutes after you create it for a new mail-enabled security to be available to add to the eDiscovery Managers role group.</span></span> 
    
    <span data-ttu-id="802c3-p127">也為先前所述，您不能進行擁有郵件功能的安全性 eDiscovery 管理員群組**新增 eDiscoveryCaseAdmin**指令程式使用安全性&amp;規範中心 PowerShell。您只可以將個別使用者新增為 eDiscovery 管理員。</span><span class="sxs-lookup"><span data-stu-id="802c3-p127">Also as previously stated, you can't make a mail-enabled security group an eDiscovery Administrator by using the **Add-eDiscoveryCaseAdmin** cmdlet in Security &amp; Compliance Center PowerShell. You can only add individual users as eDiscovery Administrators.</span></span> 
    
    <span data-ttu-id="802c3-237">請注意也無法新增具有郵件功能的安全性群組為大小寫的成員。</span><span class="sxs-lookup"><span data-stu-id="802c3-237">Note that you also can't add a mail-enabled security group as a member of a case.</span></span>
