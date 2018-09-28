---
title: 設計隔離的 SharePoint Online 小組網站
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: 摘要： 透過隔離的 SharePoint Online 小組網站的設計程序的步驟。
ms.openlocfilehash: bd36044eb16b9f6ee3ee9bbb444fe8f4efe2fd63
ms.sourcegitcommit: e0f016aca7befc8806233a492ee916cbe646094f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/27/2018
ms.locfileid: "25345805"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="893a2-103">設計隔離的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="893a2-103">Design an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="893a2-104">**摘要：** 逐步解說隔離的 SharePoint Online 小組網站的設計程序的步驟。</span><span class="sxs-lookup"><span data-stu-id="893a2-104">**Summary:** Step through the design process for isolated SharePoint Online team sites.</span></span>
  
<span data-ttu-id="893a2-105">本文會引導您完成建立隔離的 SharePoint Online 小組網站之前，您必須進行的重要的設計決策。</span><span class="sxs-lookup"><span data-stu-id="893a2-105">This article takes you through the key design decisions you must make before creating an isolated SharePoint Online team site.</span></span>
  
## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a><span data-ttu-id="893a2-106">階段 1： 決定您的 SharePoint 群組和權限層級</span><span class="sxs-lookup"><span data-stu-id="893a2-106">Phase 1: Determine your SharePoint groups and permission levels</span></span>

<span data-ttu-id="893a2-107">每個預設的 SharePoint Online 小組網站被建立具有下列 SharePoint 群組：</span><span class="sxs-lookup"><span data-stu-id="893a2-107">Every SharePoint Online team site by default is created with the following SharePoint groups:</span></span>
  
- <span data-ttu-id="893a2-108">\<站台名稱 > 成員</span><span class="sxs-lookup"><span data-stu-id="893a2-108">\<site name> Members</span></span>
    
- <span data-ttu-id="893a2-109">\<站台名稱 > 訪客</span><span class="sxs-lookup"><span data-stu-id="893a2-109">\<site name> Visitors</span></span>
    
- <span data-ttu-id="893a2-110">\<站台名稱 > 擁有者</span><span class="sxs-lookup"><span data-stu-id="893a2-110">\<site name> Owners</span></span>
    
<span data-ttu-id="893a2-111">這些群組是不同 Office 365 和 Azure Active Directory (AD) 群組和指派資源的權限之網站的基礎。</span><span class="sxs-lookup"><span data-stu-id="893a2-111">These groups are separate from Office 365 and Azure Active Directory (AD) groups and are the basis for assigning permissions for the resources of the site.</span></span>
  
<span data-ttu-id="893a2-p101">會決定 SharePoint 群組的成員可以執行網站中的特定權限集是權限等級。SharePoint Online 小組網站的預設有三個權限層級： 編輯、 讀取、 及完全控制。下表顯示預設相互關聯之 SharePoint 群組及指派權限層級：</span><span class="sxs-lookup"><span data-stu-id="893a2-p101">The set of specific permissions that determines what a member of a SharePoint group can do in a site is a permission level. There are three permission levels by default for a SharePoint Online team site: Edit, Read, and Full control. The following table shows the default correlation of SharePoint groups and assigned permission levels:</span></span>
  
|<span data-ttu-id="893a2-115">**SharePoint 群組**</span><span class="sxs-lookup"><span data-stu-id="893a2-115">**SharePoint group**</span></span>|<span data-ttu-id="893a2-116">**權限等級**</span><span class="sxs-lookup"><span data-stu-id="893a2-116">**Permission level**</span></span>|
|:-----|:-----|
|<span data-ttu-id="893a2-117">\<站台名稱 > 成員</span><span class="sxs-lookup"><span data-stu-id="893a2-117">\<site name> Members</span></span>  <br/> |<span data-ttu-id="893a2-118">編輯</span><span class="sxs-lookup"><span data-stu-id="893a2-118">Edit</span></span>  <br/> |
|<span data-ttu-id="893a2-119">\<站台名稱 > 訪客</span><span class="sxs-lookup"><span data-stu-id="893a2-119">\<site name> Visitors</span></span>  <br/> |<span data-ttu-id="893a2-120">讀取</span><span class="sxs-lookup"><span data-stu-id="893a2-120">Read</span></span>  <br/> |
|<span data-ttu-id="893a2-121">\<站台名稱 > 擁有者</span><span class="sxs-lookup"><span data-stu-id="893a2-121">\<site name> Owners</span></span>  <br/> |<span data-ttu-id="893a2-122">完全控制</span><span class="sxs-lookup"><span data-stu-id="893a2-122">Full control</span></span>  <br/> |
   
 <span data-ttu-id="893a2-p102">**最佳作法：** 您可以建立其他 SharePoint 群組與權限等級。不過，我們建議您隔離的 SharePoint Online 網站使用的預設 SharePoint 群組和權限層級。</span><span class="sxs-lookup"><span data-stu-id="893a2-p102">**Best practice:** You can create additional SharePoint groups and permission levels. However, we recommend using the default SharePoint groups and permission levels for your isolated SharePoint Online site.</span></span>
  
<span data-ttu-id="893a2-125">以下是預設 SharePoint 群組與權限等級。</span><span class="sxs-lookup"><span data-stu-id="893a2-125">Here are the default SharePoint groups and permission levels.</span></span>
  
![SharePoint Online 網站的預設 SharePoint 群組和權限等級。](media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)
  
## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a><span data-ttu-id="893a2-127">階段 2： 指派給使用者的存取群組與權限</span><span class="sxs-lookup"><span data-stu-id="893a2-127">Phase 2: Assign permissions to users with access groups</span></span>

<span data-ttu-id="893a2-p103">您可以指派給使用者的權限新增其使用者帳戶或 Office 365 或 Azure AD 群組是所屬的使用者帳戶至 SharePoint 群組的成員。新增之後，Office 365 使用者帳戶，其直接或間接透過 Office 365 或 Azure AD 的群組成員資格，指派給關聯的 SharePoint 群組的權限層級。</span><span class="sxs-lookup"><span data-stu-id="893a2-p103">You can assign permissions to users by adding their user account, or an Office 365 or Azure AD group of which the user account is a member, to the SharePoint groups. Once added, the Office 365 user accounts, either directly or indirectly via membership in an Office 365 or Azure AD group, are assigned the permission level associated with the SharePoint group.</span></span>
  
<span data-ttu-id="893a2-130">使用預設 SharePoint 群組作為範例：</span><span class="sxs-lookup"><span data-stu-id="893a2-130">Using the default SharePoint groups as an example:</span></span>
  
- <span data-ttu-id="893a2-131">成員**\<站台名稱 > 成員**SharePoint 群組，其中可能包含使用者帳戶和群組，已指派的**編輯**權限層級</span><span class="sxs-lookup"><span data-stu-id="893a2-131">Members of the **\<site name> Members** SharePoint group, which can include both user accounts and groups, are assigned the **Edit** permission level</span></span>
    
- <span data-ttu-id="893a2-132">成員**\<站台名稱 > 訪客**SharePoint 群組，其中可能包含使用者帳戶和群組，已指派**讀取**權限等級</span><span class="sxs-lookup"><span data-stu-id="893a2-132">Members of the **\<site name> Visitors** SharePoint group, which can include both user accounts and groups, are assigned the **Read** permission level</span></span>
    
- <span data-ttu-id="893a2-133">成員**\<站台名稱 > 擁有者**SharePoint 群組，其中可能包含使用者帳戶和群組，已指派的**完全控制**」 權限層級</span><span class="sxs-lookup"><span data-stu-id="893a2-133">Members of the **\<site name> Owners** SharePoint group, which can include both user accounts and groups, are assigned the **Full control** permission level</span></span>
    
 <span data-ttu-id="893a2-p104">**最佳作法：** 雖然您可以透過管理權限的個別使用者帳戶，我們建議您使用單一 Azure AD] 群組中，而稱為 access] 群組中。這可透過在 [存取] 群組的成員資格的權限管理簡化而不是每個 SharePoint 群組管理清單的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="893a2-p104">**Best practice:** Although you can manage permissions through individual user accounts, we recommend that you use a single Azure AD group, known as an access group, instead. This simplifies the management of permissions through membership in the access group, rather than managing the list of user accounts for each SharePoint group.</span></span>
  
<span data-ttu-id="893a2-p105">Office 365 的 azure AD 群組是 Office 365 群組與不同。Azure AD 群組會出現在**安全性**其**型別**組與 Office 系統管理中心和不具有電子郵件地址。您可以管理 azure AD 群組內：</span><span class="sxs-lookup"><span data-stu-id="893a2-p105">Azure AD groups for Office 365 are different than Office 365 groups. Azure AD groups appear in the Office Admin center with their **Type** set to **Security** and do not have an email address. Azure AD groups can be managed within:</span></span>
  
- <span data-ttu-id="893a2-139">Windows Server Active Directory (AD)</span><span class="sxs-lookup"><span data-stu-id="893a2-139">Windows Server Active Directory (AD)</span></span>
    
    <span data-ttu-id="893a2-p106">這些是在您的內部部署 Windows Server AD 基礎結構中建立及同步處理至 Office 365 訂閱的群組。在 Office 系統管理中心，這些群組會有**與 active directory Synched\*\*\*\*狀態**。</span><span class="sxs-lookup"><span data-stu-id="893a2-p106">These are groups that have been created in your on-premises Windows Server AD infrastructure and synchronized to your Office 365 subscription. In the Office Admin center, these groups have a **Status** of **Synched with active directory**.</span></span>
    
- <span data-ttu-id="893a2-142">Office 365</span><span class="sxs-lookup"><span data-stu-id="893a2-142">Office 365</span></span>
    
    <span data-ttu-id="893a2-p107">這些是透過 Office 系統管理中心、 Azure 入口網站，或使用 Microsoft PowerShell 已建立的群組。在 Office 系統管理中心，這些群組會有**雲端**的**狀態**。</span><span class="sxs-lookup"><span data-stu-id="893a2-p107">These are groups that have been created using either the Office Admin center, the Azure portal, or Microsoft PowerShell. In the Office Admin center, these groups have a **Status** of **Cloud**.</span></span>
    
 <span data-ttu-id="893a2-145">**最佳作法：** 如果您使用 Windows Server AD 的內部使用者和群組管理與 Windows Server AD 同步處理與您的 Office 365 訂閱執行。</span><span class="sxs-lookup"><span data-stu-id="893a2-145">**Best practice:** If you are using Windows Server AD on-premises and synchronizing with your Office 365 subscription, perform your user and group management with Windows Server AD.</span></span>
  
<span data-ttu-id="893a2-146">隔離 SharePoint Online 小組網站的建議的群組結構如下：</span><span class="sxs-lookup"><span data-stu-id="893a2-146">For isolated SharePoint Online team sites, the recommended group structure looks like this:</span></span>
  
|<span data-ttu-id="893a2-147">**SharePoint 群組**</span><span class="sxs-lookup"><span data-stu-id="893a2-147">**SharePoint group**</span></span>|<span data-ttu-id="893a2-148">**Azure AD 式存取群組**</span><span class="sxs-lookup"><span data-stu-id="893a2-148">**Azure AD-based access group**</span></span>|<span data-ttu-id="893a2-149">**權限等級**</span><span class="sxs-lookup"><span data-stu-id="893a2-149">**Permission level**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="893a2-150">\<站台名稱 > 成員</span><span class="sxs-lookup"><span data-stu-id="893a2-150">\<site name> Members</span></span>  <br/> |<span data-ttu-id="893a2-151">\<站台名稱 > 成員</span><span class="sxs-lookup"><span data-stu-id="893a2-151">\<site name> Members</span></span>  <br/> |<span data-ttu-id="893a2-152">編輯</span><span class="sxs-lookup"><span data-stu-id="893a2-152">Edit</span></span>  <br/> |
|<span data-ttu-id="893a2-153">\<站台名稱 > 訪客</span><span class="sxs-lookup"><span data-stu-id="893a2-153">\<site name> Visitors</span></span>  <br/> |<span data-ttu-id="893a2-154">\<站台名稱 > 檢視器</span><span class="sxs-lookup"><span data-stu-id="893a2-154">\<site name> Viewers</span></span>  <br/> |<span data-ttu-id="893a2-155">讀取</span><span class="sxs-lookup"><span data-stu-id="893a2-155">Read</span></span>  <br/> |
|<span data-ttu-id="893a2-156">\<站台名稱 > 擁有者</span><span class="sxs-lookup"><span data-stu-id="893a2-156">\<site name> Owners</span></span>  <br/> |<span data-ttu-id="893a2-157">\<站台名稱 > 系統管理員</span><span class="sxs-lookup"><span data-stu-id="893a2-157">\<site name> Admins</span></span>  <br/> |<span data-ttu-id="893a2-158">完全控制</span><span class="sxs-lookup"><span data-stu-id="893a2-158">Full control</span></span>  <br/> |
   
 <span data-ttu-id="893a2-p108">**最佳作法：** 雖然您可以使用 Office 365 或 Azure AD 群組 SharePoint 群組的成員身分，我們建議您使用 Azure AD 群組。Azure AD 群組、 受管理的透過 Windows Server AD 或 Office 365 提供您更多彈性，可使用巢狀的群組來指派權限。</span><span class="sxs-lookup"><span data-stu-id="893a2-p108">**Best practice:** Although you can use either Office 365 or Azure AD groups as members of SharePoint groups, we recommend that you use Azure AD groups. Azure AD groups, managed either through Windows Server AD or Office 365, give you more flexibility to use nested groups to assign permissions.</span></span>
  
<span data-ttu-id="893a2-161">以下是預設值設定為使用 Azure AD 型的存取群組的 SharePoint 群組。</span><span class="sxs-lookup"><span data-stu-id="893a2-161">Here are the default SharePoint groups configured to use Azure AD-based access groups.</span></span>
  
![使用存取群組作為預設 SharePoint Online 網站群組的成員。](media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)
  
<span data-ttu-id="893a2-163">設計的三種存取群組、 時請謹記下列事項：</span><span class="sxs-lookup"><span data-stu-id="893a2-163">When designing the three access groups, keep the following in mind:</span></span>
  
- <span data-ttu-id="893a2-164">應該有幾個成員只在**\<站台名稱 > Admins**存取群組，對應至少量的 SharePoint Online 系統管理員所管理小組網站。</span><span class="sxs-lookup"><span data-stu-id="893a2-164">There should be only a few members in the **\<site name> Admins** access group, corresponding to a small number of SharePoint Online administrators who are managing the team site.</span></span>
    
- <span data-ttu-id="893a2-p109">大部分的網站成員位於**\<站台名稱 > 成員**或**\<站台名稱 > 檢視者**存取群組。因為網站中的成員**\<站台名稱 > 成員**存取群組已刪除或修改網站中的資源、 謹慎考慮其成員資格的能力。當有疑問，新增至該網站成員**\<站台名稱 > 檢視者**存取群組。</span><span class="sxs-lookup"><span data-stu-id="893a2-p109">Most of your site members are in the **\<site name> Members** or **\<site name> Viewers** access groups. Because site members in the **\<site name> Members** access group have the ability to delete or modify resources in the site, carefully consider its membership. When in doubt, add the site member to the **\<site name> Viewers** access group.</span></span>
    
<span data-ttu-id="893a2-168">以下是範例中的 SharePoint 群組和名為 ProjectX 隔離網站的存取群組。</span><span class="sxs-lookup"><span data-stu-id="893a2-168">Here is an example of the SharePoint groups and access groups for an isolated site named ProjectX.</span></span>
  
![為名為 ProjectX 的 SharePoint Online 網站使用存取群組的範例。](media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)
  
## <a name="phase-3-use-nested-azure-ad-groups"></a><span data-ttu-id="893a2-170">階段 3： 使用巢狀 Azure AD 群組</span><span class="sxs-lookup"><span data-stu-id="893a2-170">Phase 3: Use nested Azure AD groups</span></span>

<span data-ttu-id="893a2-p110">侷限於人員少數專案、 Azure AD 式存取群組新增至網站的 SharePoint 群組的單一層級適合大部分的情況。不過，如果您有大量的人員與這些人員的已經成員建立 Azure AD 群組，您可以更輕鬆地指派 SharePoint 權限使用巢狀的群組或包含其他群組成員的群組。</span><span class="sxs-lookup"><span data-stu-id="893a2-p110">For a project confined to a small number of people, a single level of Azure AD-based access groups added to the SharePoint groups of the site will fit most scenarios. However, if you have a large number of people and those people are already members of established Azure AD groups, you can more easily assign SharePoint permissions by using nested groups, or groups that contain other groups as members.</span></span>
  
<span data-ttu-id="893a2-p111">例如，您要建立隔離的 SharePoint online 小組網站的銷售、 行銷、 工程、 法律高階主管之間的共同作業及支援部門與這些部門已經自己群組以高階主管的使用者帳戶成員資格。而不是建立新的網站成員的新群組並放所有個別高階主管的使用者帳戶，將每個部門的現有 executive 群組置於新的群組。</span><span class="sxs-lookup"><span data-stu-id="893a2-p111">For example, you want to create an isolated SharePoint online team site for collaboration among the executives of the sales, marketing, engineering, legal, and support departments and those departments already their own groups with executive user account membership. Rather than creating a new group for the new site members and placing all the individual executive user accounts in it, put the existing executive groups for each department in the new group.</span></span>
  
 <span data-ttu-id="893a2-p112">如果您要共用多個組織之間的 Office 365 訂閱，組織隔離網站群組成員資格的單一層級可能會不易管理因為大量的使用者帳戶。在此例中，您可以使用巢狀的每個組織的 Azure AD 群組包含在其組織中管理的權限的群組。</span><span class="sxs-lookup"><span data-stu-id="893a2-p112">If you are sharing an Office 365 subscription between multiple organizations, a single level of group membership for an isolated site for an organization might become difficult to manage due to the sheer number of user accounts. In this case, you can use nested Azure AD groups for each organization that contain the groups within their organizations to manage the permissions.</span></span>
  
<span data-ttu-id="893a2-177">若要使用巢狀 Azure AD 群組：</span><span class="sxs-lookup"><span data-stu-id="893a2-177">To use nested Azure AD groups:</span></span>
  
1. <span data-ttu-id="893a2-178">識別或建立將包含使用者帳戶並將適當的使用者帳戶新增為成員的 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="893a2-178">Identify or create the Azure AD groups that will contain user accounts and add the appropriate user accounts as members.</span></span>
    
2. <span data-ttu-id="893a2-179">建立將包含 「 Azure AD 群組並將這些群組新增為成員的容器 Azure AD 式存取群組。</span><span class="sxs-lookup"><span data-stu-id="893a2-179">Create the container Azure AD-based access group that will contain the other Azure AD groups and add those groups as members.</span></span>
    
3.  <span data-ttu-id="893a2-180">對於容器存取群組存取權的適當層級，識別 SharePoint 群組與對應的權限層級。</span><span class="sxs-lookup"><span data-stu-id="893a2-180">For the appropriate level of access for the container access group, identify the SharePoint group and corresponding permission level.</span></span>
    
> [!NOTE]
> <span data-ttu-id="893a2-181">您無法使用巢狀的 Office 365 群組。</span><span class="sxs-lookup"><span data-stu-id="893a2-181">You cannot use nested Office 365 groups.</span></span> 
  
<span data-ttu-id="893a2-182">以下是巢狀的 Azure AD 的範例群組 ProjectX 成員存取群組。</span><span class="sxs-lookup"><span data-stu-id="893a2-182">Here is an example of nested Azure AD groups for the ProjectX member access group.</span></span>
  
![針對 ProjectX 網站之成員存取群組使用巢狀存取群組的範例。](media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)
  
<span data-ttu-id="893a2-184">因為參考資料、 工程和專案中的使用者帳戶的所有負責人小組都是設為網站成員、 將其 Azure AD 群組新增至 ProjectX 成員存取群組變得更容易。</span><span class="sxs-lookup"><span data-stu-id="893a2-184">Because all of the user accounts in the Research, Engineering, and Project leads teams are intended to be site members, it is easier to add their Azure AD groups to the ProjectX Members access group.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="893a2-185">下一步</span><span class="sxs-lookup"><span data-stu-id="893a2-185">Next step</span></span>

<span data-ttu-id="893a2-186">當您準備好建立及設定在生產環境中隔離的網站時，請參閱 ＜ [Deploy 隔離的 SharePoint Online 小組網站](deploy-an-isolated-sharepoint-online-team-site.md)。</span><span class="sxs-lookup"><span data-stu-id="893a2-186">When you are ready to create and configure an isolated site in production, see [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="893a2-187">另請參閱</span><span class="sxs-lookup"><span data-stu-id="893a2-187">See Also</span></span>

<span data-ttu-id="893a2-188">[隔離的 SharePoint Online 小組網站](isolated-sharepoint-online-team-sites.md)。</span><span class="sxs-lookup"><span data-stu-id="893a2-188">[Isolated SharePoint Online team sites](isolated-sharepoint-online-team-sites.md)</span></span>
  
[<span data-ttu-id="893a2-189">管理隔離的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="893a2-189">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="893a2-190">部署獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="893a2-190">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)



