---
title: 管理隔離的 SharePoint Online 小組網站
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: 摘要： 管理隔離這些程序與 SharePoint Online 小組網站。
ms.openlocfilehash: 22b4cbbdd926635286d23570e1f61b64529d0e76
ms.sourcegitcommit: e0f016aca7befc8806233a492ee916cbe646094f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/27/2018
ms.locfileid: "25345935"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="0041e-103">管理隔離的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="0041e-103">Manage an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="0041e-104">**摘要：** 管理隔離這些程序與 SharePoint Online 小組網站。</span><span class="sxs-lookup"><span data-stu-id="0041e-104">**Summary:** Manage your isolated SharePoint Online team site with these procedures.</span></span>
  
<span data-ttu-id="0041e-105">本文說明隔離的 SharePoint Online 小組網站的一般管理作業。</span><span class="sxs-lookup"><span data-stu-id="0041e-105">This article describes common management operations for an isolated SharePoint Online team site.</span></span>
  
## <a name="add-a-new-user"></a><span data-ttu-id="0041e-106">將新使用者</span><span class="sxs-lookup"><span data-stu-id="0041e-106">Add a new user</span></span>

<span data-ttu-id="0041e-107">當某人新加入的網站時，您必須決定其參與網站層級：</span><span class="sxs-lookup"><span data-stu-id="0041e-107">When someone new joins the site, you must decide their level of participation in the site:</span></span>
  
- <span data-ttu-id="0041e-108">管理： 將新的使用者帳戶新增至網站管理員存取群組</span><span class="sxs-lookup"><span data-stu-id="0041e-108">Administration: Add the new user account to the site admins access group</span></span>
    
- <span data-ttu-id="0041e-109">作用中的共同作業： 將使用者帳戶新增至網站成員存取群組</span><span class="sxs-lookup"><span data-stu-id="0041e-109">Active collaboration: Add the user account to the site members access group</span></span>
    
- <span data-ttu-id="0041e-110">檢視： 將使用者帳戶新增至網站檢視者存取群組</span><span class="sxs-lookup"><span data-stu-id="0041e-110">Viewing: Add the user account to the site viewers access group</span></span>
    
<span data-ttu-id="0041e-111">如果您正在管理使用者帳戶和群組透過 Windows Server Active Directory (AD)，將適當的使用者新增至您一般 Windows Server AD 使用者和群組管理程序的適當存取群組並等候同步處理您Office 365 訂閱。</span><span class="sxs-lookup"><span data-stu-id="0041e-111">If you are managing user accounts and groups through Windows Server Active Directory (AD), add the appropriate users to the appropriate access groups using your normal Windows Server AD user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="0041e-112">如果您正在管理使用者帳戶和群組透過 Office 365，您可以使用 Office 系統管理中心或 Microsoft PowerShell：</span><span class="sxs-lookup"><span data-stu-id="0041e-112">If you are managing user accounts and groups through Office 365, you can use the Office Admin center or Microsoft PowerShell:</span></span>
  
- <span data-ttu-id="0041e-113">針對 Office 系統管理中心中，使用已指派之使用者帳戶系統管理員或公司管理員角色的使用者帳戶登入並使用群組將適當的使用者新增至適當的存取群組。</span><span class="sxs-lookup"><span data-stu-id="0041e-113">For the Office Admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate users to the appropriate access groups.</span></span>
    
- <span data-ttu-id="0041e-p101">Powershell，第一個[連接使用 Azure Active Directory V2 PowerShell 模組](https://go.microsoft.com/fwlink/?linkid=842218)。若要將使用者帳戶新增至其使用者主體名稱 (UPN) 的存取群組，使用下列 PowerShell 命令區塊：</span><span class="sxs-lookup"><span data-stu-id="0041e-p101">For PowerShell, first [Connect with the Azure Active Directory V2 PowerShell module](https://go.microsoft.com/fwlink/?linkid=842218). To add a user account to an access group with its user principal name (UPN), use the following PowerShell command block:</span></span>
    
```
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

> [!TIP]
> <span data-ttu-id="0041e-116">包含所有的 PowerShell 命令與 Excel 的文字檔案的 PowerShell 命令將會產生的設定工作表根據您的群組和使用者帳戶名稱、 下載[隔離 SharePoint Online 小組網站部署套件 （英文)](https://gallery.technet.microsoft.com/Isolated-SharePoint-Online-0b364907)。</span><span class="sxs-lookup"><span data-stu-id="0041e-116">For a text file that contains all the PowerShell commands and an Excel configuration worksheet that generates PowerShell commands based on your group and user account names, download the [Isolated SharePoint Online Team Site Deployment Kit](https://gallery.technet.microsoft.com/Isolated-SharePoint-Online-0b364907).</span></span> 

<span data-ttu-id="0041e-117">若要將使用者帳戶新增至其顯示名稱的存取群組，使用下列 PowerShell 命令區塊：</span><span class="sxs-lookup"><span data-stu-id="0041e-117">To add a user account to an access group with its display name, use the following PowerShell command block:</span></span>

```
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a><span data-ttu-id="0041e-118">新增新的群組</span><span class="sxs-lookup"><span data-stu-id="0041e-118">Add a new group</span></span>

<span data-ttu-id="0041e-119">若要新增至整個群組的存取，您必須決定網站中的群組所有成員的參與的層級：</span><span class="sxs-lookup"><span data-stu-id="0041e-119">To add access to an entire group, you must decide the level of participation of all the members of the group in the site:</span></span>
  
- <span data-ttu-id="0041e-120">管理： 將群組新增至網站管理員存取群組</span><span class="sxs-lookup"><span data-stu-id="0041e-120">Administration: Add the group to the site admins access group</span></span>
    
- <span data-ttu-id="0041e-121">作用中的共同作業： 將群組新增至網站成員存取群組</span><span class="sxs-lookup"><span data-stu-id="0041e-121">Active collaboration: Add the group to the site members access group</span></span>
    
- <span data-ttu-id="0041e-122">檢視： 將群組新增至網站檢視者存取群組</span><span class="sxs-lookup"><span data-stu-id="0041e-122">Viewing: Add the group to the site viewers access group</span></span>
    
<span data-ttu-id="0041e-123">如果您正在管理使用者帳戶及 Windows Server AD 透過群組，將適當的群組新增至適當的群組使用標準的 Windows Server AD 使用者和群組管理程序，並等待與您的 Office 365 訂閱進行同步處理。</span><span class="sxs-lookup"><span data-stu-id="0041e-123">If you are managing user accounts and groups through Windows Server AD, add the appropriate groups to the appropriate groups using your normal Windows Server AD user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="0041e-124">如果您正在管理使用者帳戶和群組透過 Office 365，您可以使用 Office 系統管理中心或 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="0041e-124">If you are managing user accounts and groups through Office 365, you can use the Office Admin center or PowerShell:</span></span>
  
- <span data-ttu-id="0041e-125">針對 Office 系統管理中心中，使用已指派之使用者帳戶系統管理員或公司管理員角色的使用者帳戶登入並使用群組將適當的群組新增至適當的存取群組。</span><span class="sxs-lookup"><span data-stu-id="0041e-125">For the Office Admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate groups to the appropriate access groups.</span></span>
    
- <span data-ttu-id="0041e-p102">Powershell，第一個[連接使用 Azure Active Directory V2 PowerShell 模組](https://go.microsoft.com/fwlink/?linkid=842218)。然後，使用下列 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="0041e-p102">For PowerShell, first [Connect with the Azure Active Directory V2 PowerShell module](https://go.microsoft.com/fwlink/?linkid=842218). Then, use the following PowerShell commands:</span></span>
 
```
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a><span data-ttu-id="0041e-128">移除使用者</span><span class="sxs-lookup"><span data-stu-id="0041e-128">Remove a user</span></span>

<span data-ttu-id="0041e-129">當某個人的存取必須從網站移除時，您移除它們從其目前成員的根據他們參與網站的存取群組：</span><span class="sxs-lookup"><span data-stu-id="0041e-129">When someone's access must be removed from the site, you remove them from the access group for which they are currently a member based on their participation in the site:</span></span>
  
- <span data-ttu-id="0041e-130">管理： 移除從網站管理員存取群組的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="0041e-130">Administration: Remove the user account from the site admins access group</span></span>
    
- <span data-ttu-id="0041e-131">作用中的共同作業： 移除從網站成員存取群組的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="0041e-131">Active collaboration: Remove the user account from the site members access group</span></span>
    
- <span data-ttu-id="0041e-132">檢視： 移除從網站檢視者存取] 群組中的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="0041e-132">Viewing: Remove the user account from the site viewers access group</span></span>
    
<span data-ttu-id="0041e-133">如果您正在管理使用者帳戶和群組透過 Windows Server AD，移除使用標準的 Windows Server AD 使用者和群組管理程序的適當存取群組中的適當的使用者並等候與您的 Office 365 進行同步處理訂閱。</span><span class="sxs-lookup"><span data-stu-id="0041e-133">If you are managing user accounts and groups through Windows Server AD, remove the appropriate users from the appropriate access groups using your normal Windows Server AD user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="0041e-134">如果您正在管理使用者帳戶和群組透過 Office 365，您可以使用 Office 系統管理中心或 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="0041e-134">If you are managing user accounts and groups through Office 365, you can use the Office Admin center or PowerShell:</span></span>
  
- <span data-ttu-id="0041e-135">針對 Office 系統管理中心中，使用已指派之使用者帳戶系統管理員或公司管理員角色的使用者帳戶登入並使用群組移除適當的存取群組中的適當的使用者。</span><span class="sxs-lookup"><span data-stu-id="0041e-135">For the Office Admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate users from the appropriate access groups.</span></span>
    
- <span data-ttu-id="0041e-p103">Powershell，第一個[連接使用 Azure Active Directory V2 PowerShell 模組](https://go.microsoft.com/fwlink/?linkid=842218)。若要從其 upn 的存取群組移除使用者帳戶，請使用下列 PowerShell 命令區塊：</span><span class="sxs-lookup"><span data-stu-id="0041e-p103">For PowerShell, first [Connect with the Azure Active Directory V2 PowerShell module](https://go.microsoft.com/fwlink/?linkid=842218). To remove a user account from an access group with its UPN, use the following PowerShell command block:</span></span>
    
```
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="0041e-138">若要從其顯示名稱的存取群組移除使用者帳戶，請使用下列 PowerShell 命令區塊：</span><span class="sxs-lookup"><span data-stu-id="0041e-138">To remove a user account from an access group with its display name, use the following PowerShell command block:</span></span>
    
```
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a><span data-ttu-id="0041e-139">移除群組</span><span class="sxs-lookup"><span data-stu-id="0041e-139">Remove a group</span></span>

<span data-ttu-id="0041e-140">若要移除整個群組存取權，您從其目前成員的根據他們參與網站存取群組中移除群組：</span><span class="sxs-lookup"><span data-stu-id="0041e-140">To remove access for an entire group, you remove the group from the access group for which they are currently a member based on their participation in the site:</span></span>
  
- <span data-ttu-id="0041e-141">管理： 移除網站管理員存取群組的群組</span><span class="sxs-lookup"><span data-stu-id="0041e-141">Administration: Remove the group from the site admins access group</span></span>
    
- <span data-ttu-id="0041e-142">作用中的共同作業： 移除從網站成員存取群組的群組</span><span class="sxs-lookup"><span data-stu-id="0041e-142">Active collaboration: Remove the group from the site members access group</span></span>
    
- <span data-ttu-id="0041e-143">檢視： 移除網站檢視者存取群組的群組</span><span class="sxs-lookup"><span data-stu-id="0041e-143">Viewing: Remove the group from the site viewers access group</span></span>
    
<span data-ttu-id="0041e-144">如果您正在管理使用者帳戶及透過 Windows Server Active Directory 群組，從您一般 Windows Server AD 使用者和群組管理程序的適當存取群組中移除適當的群組，並等待同步處理您Office 365 訂閱。</span><span class="sxs-lookup"><span data-stu-id="0041e-144">If you are managing user accounts and groups through Windows Server Active Directory, remove the appropriate groups from the appropriate access groups using your normal Windows Server AD user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="0041e-145">如果您正在管理使用者帳戶和群組透過 Office 365，您可以使用 Office 系統管理中心或 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="0041e-145">If you are managing user accounts and groups through Office 365, you can use the Office Admin center or PowerShell:</span></span>
  
- <span data-ttu-id="0041e-146">針對 Office 系統管理中心中，使用已指派之使用者帳戶系統管理員或公司管理員角色的使用者帳戶登入並使用群組移除適當的存取群組中的適當的群組。</span><span class="sxs-lookup"><span data-stu-id="0041e-146">For the Office Admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate groups from the appropriate access groups.</span></span>
    
- <span data-ttu-id="0041e-147">Powershell，第一個[連接使用 Azure Active Directory V2 PowerShell 模組](https://go.microsoft.com/fwlink/?linkid=842218)。</span><span class="sxs-lookup"><span data-stu-id="0041e-147">For PowerShell, first [Connect with the Azure Active Directory V2 PowerShell module](https://go.microsoft.com/fwlink/?linkid=842218).</span></span>    
<span data-ttu-id="0041e-148">若要使用其顯示名稱的存取群組中移除群組，請使用下列 PowerShell 命令區塊：</span><span class="sxs-lookup"><span data-stu-id="0041e-148">To remove a group from an access group using their display names, use the following PowerShell command block:</span></span>
    
```
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a><span data-ttu-id="0041e-149">使用自訂權限建立文件的子資料夾</span><span class="sxs-lookup"><span data-stu-id="0041e-149">Create a documents subfolder with custom permissions</span></span>

<span data-ttu-id="0041e-p104">在某些情況下，使用隔離的站台內的人員的子集需要更多私人的位置進行共同作業。SharePoint Online 網站，您可以在站台的文件] 資料夾中建立子資料夾及指派自訂權限。這些權限而不會看到子資料夾。</span><span class="sxs-lookup"><span data-stu-id="0041e-p104">In some cases, a subset of the people working within the isolated site need a more private place to collaborate. For SharePoint Online sites, you can create a subfolder in the Documents folder of the site and assign custom permissions. Those without permissions will not see the subfolder.</span></span>
  
<span data-ttu-id="0041e-153">若要建立的自訂權限的文件子資料夾，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="0041e-153">To create a documents subfolder with custom permissions, do the following:</span></span>
  
1. <span data-ttu-id="0041e-p105">以屬於 admins 存取網站群組的成員帳戶登入 Office 365。為了協助，請參閱 ＜[登入 Office 365 的位置](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="0041e-p105">Sign in to Office 365 with an account that is a member of the admins access group for the site. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="0041e-156">移至隔離的小組網站並按一下 [**文件**。</span><span class="sxs-lookup"><span data-stu-id="0041e-156">Go to the isolated team site and click **Documents**.</span></span>
    
3. <span data-ttu-id="0041e-157">瀏覽至將包含具有自訂的權限的子資料夾、 建立資料夾，並加以開啟的文件] 資料夾中的資料夾。</span><span class="sxs-lookup"><span data-stu-id="0041e-157">Browse to the folder in the documents folder that will contain the subfolder with custom permissions, create the folder, and then open it.</span></span>
    
4. <span data-ttu-id="0041e-158">按一下 **[共用]**。</span><span class="sxs-lookup"><span data-stu-id="0041e-158">Click **Share**.</span></span>
    
5. <span data-ttu-id="0041e-159">按一下 [**與共用 > 進階**。</span><span class="sxs-lookup"><span data-stu-id="0041e-159">Click **Shared with > Advanced**.</span></span>
    
6. <span data-ttu-id="0041e-160">按一下 [**停止繼承權限**] 和 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="0041e-160">Click **Stop inheriting permissions**, and then click **OK**.</span></span>
    
7. <span data-ttu-id="0041e-161">按一下 **[共用]**。</span><span class="sxs-lookup"><span data-stu-id="0041e-161">Click **Share**.</span></span>
    
8. <span data-ttu-id="0041e-162">按一下 [**與共用 > 進階**。</span><span class="sxs-lookup"><span data-stu-id="0041e-162">Click **Shared with > Advanced**.</span></span>
    
9. <span data-ttu-id="0041e-163">按一下 [**授與權限 > 與共用 > 進階**。</span><span class="sxs-lookup"><span data-stu-id="0041e-163">Click **Grant Permissions > Shared with > Advanced**.</span></span>
    
10. <span data-ttu-id="0041e-164">在 [權限] 頁面上，按一下 [**\<站台名稱 > 清單中的成員**。</span><span class="sxs-lookup"><span data-stu-id="0041e-164">On the permissions page, click **\<site name> Members in the list**.</span></span>
    
11. <span data-ttu-id="0041e-165">在**\<站台名稱 > 成員**] 頁面上、 選取網站成員存取群組旁邊的核取記號表示、 按一下 [**動作]**、 按一下 [**移除從群組中的使用者**，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="0041e-165">On the **\<site name> Members** page, select the checkmark next to the site members access group, click **Actions**, click **Remove users from group**, and then click **OK**.</span></span>
    
12. <span data-ttu-id="0041e-166">若要將特定成員新增到這個子資料夾中，按一下 [**新增 > 新增使用者**。</span><span class="sxs-lookup"><span data-stu-id="0041e-166">To add specific members to this subfolder, click **New > Add users**.</span></span>
    
13. <span data-ttu-id="0041e-167">在 [**共用**] 對話方塊中，輸入可以共同作業的子資料夾中的檔案，然後按一下 [**共用**的使用者帳戶的名稱。</span><span class="sxs-lookup"><span data-stu-id="0041e-167">In the **Share** dialog box, type the names of the user accounts that can collaborate on files in the subfolder, and then click **Share**.</span></span>
    
14. <span data-ttu-id="0041e-168">重新整理 web 頁面才能看見新的結果。</span><span class="sxs-lookup"><span data-stu-id="0041e-168">Refresh the web page to see the new results.</span></span>
    
15. <span data-ttu-id="0041e-169">[**群組**的左方導覽中，按一下 [**\<站台名稱 > 訪客**群組及使用步驟 11 14 指定可以檢視中的檔案的子資料夾 （視） 的使用者帳戶的設定。</span><span class="sxs-lookup"><span data-stu-id="0041e-169">Under **Groups** in the left navigation, click the **\<site name> Visitors** group and use steps 11-14 to specify the set of user accounts that can view the files in the subfolder (as needed).</span></span>
    
16. <span data-ttu-id="0041e-170">[**群組**的左方導覽中，按一下 [**\<站台名稱 > 擁有者**群組及使用步驟 11 14 指定 （視） 可以管理子資料夾中的權限的使用者帳戶的設定。</span><span class="sxs-lookup"><span data-stu-id="0041e-170">Under **Groups** in the left navigation, click the **\<site name> Owners** group and use steps 11-14 to specify the set of user accounts that can administer the permissions in the subfolder (as needed).</span></span>
    
17. <span data-ttu-id="0041e-171">關閉瀏覽器中的 [**人員與群組**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="0041e-171">Close the **People and Groups** tab in your browser.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0041e-172">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0041e-172">See Also</span></span>

<span data-ttu-id="0041e-173">[隔離的 SharePoint Online 小組網站](isolated-sharepoint-online-team-sites.md)。</span><span class="sxs-lookup"><span data-stu-id="0041e-173">[Isolated SharePoint Online team sites](isolated-sharepoint-online-team-sites.md)</span></span>
  
[<span data-ttu-id="0041e-174">設計隔離的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="0041e-174">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="0041e-175">部署獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="0041e-175">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)



