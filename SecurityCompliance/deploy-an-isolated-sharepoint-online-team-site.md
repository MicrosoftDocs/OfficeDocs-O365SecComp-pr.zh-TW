---
title: 部署獨立的 SharePoint Online 小組網站
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 3033614b-e23b-4f68-9701-f62525eafaab
description: 摘要： 部署新隔離的 SharePoint Online 小組網站與這些逐步指示。
ms.openlocfilehash: 4cb60cd55f526592cb469d80a061375a4f556afe
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32257000"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="e4ea1-103">部署獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="e4ea1-103">Deploy an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="e4ea1-104">**摘要：** 部署新隔離的 SharePoint Online 小組網站，這些逐步指示。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-104">**Summary:** Deploy a new isolated SharePoint Online team site with these step-by-step instructions.</span></span>
  
<span data-ttu-id="e4ea1-105">本文適用於建立與 Microsoft Office 365 中設定隔離的 SharePoint Online 小組網站的逐步部署指南 》。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-105">This article is a step-by-step deployment guide for creating and configuring an isolated SharePoint Online team site in Microsoft Office 365.</span></span> <span data-ttu-id="e4ea1-106">這些步驟假設使用三個預設 SharePoint 群組和對應的權限層級，與每個層級的存取權的單一的 Azure Active Directory AD 存取群組。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-106">These steps assume the use of the three default SharePoint groups and corresponding permission levels, with a single Azure Active Directory (AD)-based access group for each level of access.</span></span>
  
## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a><span data-ttu-id="e4ea1-107">階段 1： 建立並填入小組網站存取群組</span><span class="sxs-lookup"><span data-stu-id="e4ea1-107">Phase 1: Create and populate the team site access groups</span></span>

<span data-ttu-id="e4ea1-108">在這個階段，您會建立三個預設 SharePoint 群組的三個 Azure AD 為基礎的存取群組，並填入適當的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-108">In this phase, you create the three Azure AD-based access groups for the three default SharePoint groups and populate them with the appropriate user accounts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e4ea1-109">下列步驟假設所有必要的使用者帳戶已存在，並指派適當的授權。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-109">The following steps assume that all necessary user accounts already exist and are assigned the appropriate licenses.</span></span> <span data-ttu-id="e4ea1-110">如果沒有，請將它們新增，並指派授權，繼續進行步驟 1。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-110">If not, please add them and assign licenses before proceeding to step 1.</span></span> 
  
### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a><span data-ttu-id="e4ea1-111">步驟 1： 將網站的 SharePoint Online 系統管理員</span><span class="sxs-lookup"><span data-stu-id="e4ea1-111">Step 1: List the SharePoint Online admins for the site</span></span>

<span data-ttu-id="e4ea1-112">決定的使用者帳戶對應至隔離的小組網站的 SharePoint Online 系統管理員。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-112">Determine the set of user accounts corresponding to the SharePoint Online admins for the isolated team site.</span></span>
  
<span data-ttu-id="e4ea1-113">如果您正在管理使用者帳戶和透過 Office 365 群組，並想要使用 Windows PowerShell，建立一份其使用者主體名稱 (Upn) (範例 UPN: belindan@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-113">If you are managing user accounts and groups through Office 365 and want to use Windows PowerShell, make a list of their user principal names (UPNs) (example UPN: belindan@contoso.com).</span></span>
  
### <a name="step-2-list-the-members-for-the-site"></a><span data-ttu-id="e4ea1-114">步驟 2： 將網站成員</span><span class="sxs-lookup"><span data-stu-id="e4ea1-114">Step 2: List the members for the site</span></span>

<span data-ttu-id="e4ea1-115">決定一組使用者帳戶對應至隔離的小組網站，使用者將會儲存在網站內的資源上共同作業的成員。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-115">Determine the set of user accounts corresponding to the members for the isolated team site, those who will be collaborating on resources stored within the site.</span></span>
  
<span data-ttu-id="e4ea1-116">如果您正在管理使用者帳戶和透過 Office 365 群組，而且想要使用 PowerShell，請他們的 Upn 清單。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-116">If you are managing user accounts and groups through Office 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="e4ea1-117">如果有很多網站成員，您可以在文字檔中儲存的 Upn 清單，並將其新增所有與單一 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-117">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>
  
### <a name="step-3-list-the-viewers-for-the-site"></a><span data-ttu-id="e4ea1-118">步驟 3： 將網站檢視者</span><span class="sxs-lookup"><span data-stu-id="e4ea1-118">Step 3: List the viewers for the site</span></span>

<span data-ttu-id="e4ea1-119">決定對應至檢視隔離的小組網站，使用者可以檢視儲存在網站中的資源，但不是需要修改或直接在其內容進行共同作業的使用者帳戶的集合。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-119">Determine the set of user accounts corresponding to the viewers of the isolated team site, those who can view the resources stored in the site but not modify them or directly collaborate on their contents.</span></span>
  
<span data-ttu-id="e4ea1-120">如果您正在管理使用者帳戶和透過 Office 365 群組，而且想要使用 PowerShell，請他們的 Upn 清單。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-120">If you are managing user accounts and groups through Office 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="e4ea1-121">如果有很多網站成員，您可以在文字檔中儲存的 Upn 清單，並將其新增所有與單一 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-121">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>
  
<span data-ttu-id="e4ea1-122">行政人員管理、 法律顧問或是 inter-departmental 專案關係人，可能包含網站檢視者。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-122">Viewers for the site might include executive management, legal counsel, or inter-departmental stakeholders.</span></span>
  
### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a><span data-ttu-id="e4ea1-123">步驟 4： 在 Azure AD 中建立三個存取群組網站</span><span class="sxs-lookup"><span data-stu-id="e4ea1-123">Step 4: Create the three access groups for the site in Azure AD</span></span>

<span data-ttu-id="e4ea1-124">您必須在 Azure AD 中建立下列存取群組：</span><span class="sxs-lookup"><span data-stu-id="e4ea1-124">You need to create the following access groups in Azure AD:</span></span>
  
- <span data-ttu-id="e4ea1-125">網站管理員 （其會包含從步驟 1 的清單）</span><span class="sxs-lookup"><span data-stu-id="e4ea1-125">Site admins (which will contain the list from step 1)</span></span>
    
- <span data-ttu-id="e4ea1-126">網站成員 （其會包含在步驟 2 的清單）</span><span class="sxs-lookup"><span data-stu-id="e4ea1-126">Site members (which will contain the list from step 2)</span></span>
    
- <span data-ttu-id="e4ea1-127">網站檢視者 （其會包含清單中的，從步驟 3）</span><span class="sxs-lookup"><span data-stu-id="e4ea1-127">Site viewers (which will contain the list from step 3)</span></span>
    
1. <span data-ttu-id="e4ea1-128">在瀏覽器中，移至 Azure 入口網站，網址[https://portal.azure.com](https://portal.azure.com)並以已指派使用者管理系統管理員或公司系統管理員角色與帳戶的認證登入。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-128">In your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com) and sign in with the credentials of an account that has been assigned with User Management Admin or Company Administrator role.</span></span>
    
2. <span data-ttu-id="e4ea1-129">在 Azure 入口網站中，按一下 [Azure Active Directory] > [群組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-129">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>
    
3. <span data-ttu-id="e4ea1-130">在 [群組 - 所有群組]\*\*\*\* 刀鋒視窗中，按一下 [+ 新增群組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-130">On the **Groups - All groups** blade, click **+ New group**.</span></span>
    
4. <span data-ttu-id="e4ea1-131">在 [群組]\*\*\*\* 刀鋒視窗中：</span><span class="sxs-lookup"><span data-stu-id="e4ea1-131">On the **Group** blade:</span></span>
    
  - <span data-ttu-id="e4ea1-132">選取 [群組類型]\*\*\*\* 中的 [Office 365]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-132">Select **Office 365** in **Group type**.</span></span>
    
  - <span data-ttu-id="e4ea1-133">在 [**名稱]** 中輸入群組名稱。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-133">Type the group name in **Name**.</span></span>
    
  - <span data-ttu-id="e4ea1-134">在 [**群組描述**輸入群組的描述。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-134">Type a description of the group in **Group description**.</span></span>
    
  - <span data-ttu-id="e4ea1-135">在 [成員資格類型]\*\*\*\* 中選取 [已指派]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-135">Select **Assigned** in **Membership type**.</span></span>
    
5. <span data-ttu-id="e4ea1-136">按一下 [建立]\*\*\*\*，然後關閉 [群組]\*\*\*\* 刀鋒視窗。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-136">Click **Create**, and then close the **Group** blade.</span></span>
    
6. <span data-ttu-id="e4ea1-137">針對其他群組重複步驟 3-5。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-137">Repeat steps 3-5 for your additional groups.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e4ea1-138">您需要使用 Azure 入口網站來建立群組，以便他們有啟用 Office 功能。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-138">You need to use the Azure portal to create the groups so that they have Office features enabled.</span></span> <span data-ttu-id="e4ea1-139">如果 SharePoint Online 隔離的網站稍後再設定為具有加密檔案並將權限指派給特定群組的 Azure 資訊保護標籤的高度機密網站時，必須允許的群組已建立啟用 Office 功能。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-139">If a SharePoint Online isolated site is later configured as a Highly Confidential site with an Azure Information Protection label to encrypt files and assign permission to specific groups, the permitted groups must have been created with Office features enabled.</span></span> <span data-ttu-id="e4ea1-140">已建立之後，您無法變更的 Azure AD 群組的 Office 功能設定。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-140">You cannot change the Office features setting of an Azure AD group after it has been created.</span></span> 
  
<span data-ttu-id="e4ea1-141">以下是三個網站存取群組與您產生的組態。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-141">Here is your resulting configuration with the three site access groups.</span></span>
  
![三個存取群組的隔離 SharePoint Online 網站部署。](media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)
  
### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a><span data-ttu-id="e4ea1-143">步驟 5。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-143">Step 5.</span></span> <span data-ttu-id="e4ea1-144">將使用者帳戶新增至 access 群組</span><span class="sxs-lookup"><span data-stu-id="e4ea1-144">Add the user accounts to the access groups</span></span>

<span data-ttu-id="e4ea1-145">在此步驟中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="e4ea1-145">In this step, do the following:</span></span>
  
1. <span data-ttu-id="e4ea1-146">步驟 1 中的使用者清單新增至網站系統管理員存取群組</span><span class="sxs-lookup"><span data-stu-id="e4ea1-146">Add the list of users from step 1 to the site admins access group</span></span>
    
2. <span data-ttu-id="e4ea1-147">步驟 2 中加入網站成員存取群組的使用者清單</span><span class="sxs-lookup"><span data-stu-id="e4ea1-147">Add the list of users from step 2 to the site members access group</span></span>
    
3. <span data-ttu-id="e4ea1-148">步驟 3 中的使用者清單新增至網站檢視者存取群組</span><span class="sxs-lookup"><span data-stu-id="e4ea1-148">Add the list of users from step 3 to the site viewers access group</span></span>
    
<span data-ttu-id="e4ea1-149">如果您要管理使用者帳戶和透過 Windows Server AD 群組，將使用者新增至適當的存取群組使用標準的 Windows Server AD 使用者和群組管理程序，並等待同步處理您的 Office 365 訂閱。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-149">If you are managing user accounts and groups through Windows Server AD, add users to the appropriate access groups using your normal Windows Server AD user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="e4ea1-150">如果您要管理使用者帳戶和群組透過 Office 365，您可以使用 Office 系統管理中心或 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-150">If you are managing user accounts and groups through Office 365, you can use the Office Admin center or PowerShell.</span></span> <span data-ttu-id="e4ea1-151">如果您有任何一個存取群組重複群組名稱，您應該使用 Office 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-151">If you have duplicate group names for any of the access groups, you should use the Office Admin center.</span></span>
  
<span data-ttu-id="e4ea1-152">針對 Office 系統管理中心中，使用已被指派的使用者帳戶系統管理員或公司系統管理員角色的使用者帳戶登入並使用群組，以新增適當的使用者帳戶和群組，以適當的存取群組。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-152">For the Office Admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate user accounts and groups to the appropriate access groups.</span></span>
  
<span data-ttu-id="e4ea1-153">Powershell 中，第一個[與 PowerShell 的 Azure Active Directory 針對 Graph 模組連線](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-153">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="e4ea1-154">接下來，使用下列命令區塊，將個別使用者帳戶新增至 access 群組：</span><span class="sxs-lookup"><span data-stu-id="e4ea1-154">Next, use the following command block to add an individual user account to an access group:</span></span>
  
```
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

> [!TIP]
> <span data-ttu-id="e4ea1-155">文字檔案，其中包含所有 PowerShell 命令和 Excel PowerShell 命令將會產生的組態工作表的群組和使用者帳戶名稱，請下載[隔離 SharePoint Online 小組網站部署套件](https://gallery.technet.microsoft.com/Isolated-SharePoint-Online-0b364907)。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-155">For a text file that contains all the PowerShell commands and an Excel configuration worksheet that generates PowerShell commands based on your group and user account names, download the [Isolated SharePoint Online Team Site Deployment Kit](https://gallery.technet.microsoft.com/Isolated-SharePoint-Online-0b364907).</span></span> 
  
<span data-ttu-id="e4ea1-156">如果您儲存 upn 的任何一個存取群組的使用者帳戶，請在文字檔案中，您可以使用下列 PowerShell 命令區塊，將它們新增一次：</span><span class="sxs-lookup"><span data-stu-id="e4ea1-156">If you stored the UPNs of user accounts for any of the access groups in a text file, you can use the following PowerShell command block to add them all at one time:</span></span>
  
```
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

<span data-ttu-id="e4ea1-157">PowerShell 中，使用下列命令區塊，將個別的群組新增至 access 群組：</span><span class="sxs-lookup"><span data-stu-id="e4ea1-157">For PowerShell, use the following command block to add an individual group to an access group:</span></span>
  
```
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID

```

<span data-ttu-id="e4ea1-158">結果應為下列各項：</span><span class="sxs-lookup"><span data-stu-id="e4ea1-158">The results should be the following:</span></span>
  
- <span data-ttu-id="e4ea1-159">網站管理員 Azure AD 群組包含網站系統管理員使用者帳戶或群組</span><span class="sxs-lookup"><span data-stu-id="e4ea1-159">The site admins Azure AD group contains the site admin user accounts or groups</span></span>
    
- <span data-ttu-id="e4ea1-160">網站成員 Azure AD 群組包含網站成員的使用者帳戶或群組</span><span class="sxs-lookup"><span data-stu-id="e4ea1-160">The site members Azure AD group contains the site member user accounts or groups</span></span>
    
- <span data-ttu-id="e4ea1-161">網站檢視者 Azure AD 群組包含使用者帳戶或群組，僅可檢視網站內容</span><span class="sxs-lookup"><span data-stu-id="e4ea1-161">The site viewers Azure AD group contains the user accounts or groups that can only view the site contents</span></span>
    
<span data-ttu-id="e4ea1-162">驗證與 Office 系統管理中心或使用下列 PowerShell 命令區塊，每個存取群組的群組成員的清單：</span><span class="sxs-lookup"><span data-stu-id="e4ea1-162">Validate the list of group members for each access group with the Office Admin center or with the following PowerShell command block:</span></span>
  
```
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

<span data-ttu-id="e4ea1-163">以下是三個網站存取群組填寫了使用者帳戶或群組具有您產生的組態。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-163">Here is your resulting configuration with the three site access groups populated with user accounts or groups.</span></span>
  
![三個存取群組填寫了使用者帳戶。](media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)
  
## <a name="phase-2-create-and-configure-the-isolated-team-site"></a><span data-ttu-id="e4ea1-165">階段 2： 建立及設定隔離的小組網站</span><span class="sxs-lookup"><span data-stu-id="e4ea1-165">Phase 2: Create and configure the isolated team site</span></span>

<span data-ttu-id="e4ea1-166">在這個階段，您可以建立隔離的 SharePoint Online 網站，並設定以使用新的 Azure AD 為基礎的存取群組的預設 SharePoint Online 權限層級的權限。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-166">In this phase, you create the isolated SharePoint Online site and configure the permissions for the default SharePoint Online permission levels to use your new Azure AD-based access groups.</span></span>
  
<span data-ttu-id="e4ea1-167">首先，使用下列步驟建立 SharePoint Online 小組網站。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-167">First, create the SharePoint Online team site with these steps.</span></span>
  
1. <span data-ttu-id="e4ea1-168">使用也可用來管理 SharePoint Online 小組網站的帳戶 (SharePoint Online 系統管理員) 登入系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-168">Sign in to the admin center with an account that will also be used to administer the SharePoint Online team site (a SharePoint Online administrator).</span></span> <span data-ttu-id="e4ea1-169">如需說明，請參閱[在何處登入 Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-169">For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="e4ea1-170">在磚清單中，按一下 [SharePoint]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-170">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="e4ea1-171">在新的 [SharePoint] \*\*\*\* 瀏覽器索引標籤中，按一下 [+ 建立網站]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-171">In the new **SharePoint** tab of your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="e4ea1-172">在 [建立網站]\*\*\*\* 頁面上，按一下 [小組網站]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-172">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="e4ea1-173">在 [**網站名稱**] 中，輸入小組網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-173">In **Site name**, type a name for the team site.</span></span> 
    
6. <span data-ttu-id="e4ea1-174">在 [**小組網站描述] 中，** 鍵入網站用途的選用描述。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-174">In **Team site description,** type an optional description of the purpose of the site.</span></span>
    
7. <span data-ttu-id="e4ea1-175">在 [隱私權設定]\*\*\*\* 中，選取 [私人 - 只有成員可以存取此網站]\*\*\*\*，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-175">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="e4ea1-176">在 [您想要新增誰?]\*\*\*\* 窗格上，按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-176">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="e4ea1-177">接下來，從新的 SharePoint Online 小組網站，設定權限。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-177">Next, from the new SharePoint Online team site, configure permissions.</span></span>
  
1. <span data-ttu-id="e4ea1-178">在工具列中，按一下設定圖示，然後按一下 [網站權限]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-178">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
    
2. <span data-ttu-id="e4ea1-179">在 [網站權限]\*\*\*\* 窗格中，按一下 [進階權限設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-179">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
    
3. <span data-ttu-id="e4ea1-180">在新的 [權限]\*\*\*\* 瀏覽器索引標籤中，按一下 [存取要求設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-180">On the new **Permissions** tab of your browser, click **Access Request Settings**.</span></span>
    
4. <span data-ttu-id="e4ea1-181">在 [**存取要求設定**] 對話方塊中，清除 [**允許成員共用網站以及個別檔案和資料夾**，以及**允許存取權要求**（使所有三個核取方塊皆已取消），然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-181">In the **Access Requests Settings** dialog box, clear **Allow member to share the site and individual files and folders** and **Allow access requests** (so that all three check boxes are cleared), and then click **OK**.</span></span>
    
5. <span data-ttu-id="e4ea1-182">在瀏覽器的 [**權限**] 索引標籤中，按一下 [**\<網站 name> 成員**清單中。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-182">On the **Permissions** tab of your browser, click **\<site name> Members** in the list.</span></span>
    
6. <span data-ttu-id="e4ea1-183">在 [人員與群組]\*\*\*\* 中，按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-183">In **People and Groups**, click **New**.</span></span>
    
7. <span data-ttu-id="e4ea1-184">在 [**共用**] 對話方塊中，輸入網站成員存取群組的名稱、 選取它，，然後按一下 [**共用**。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-184">In the **Share** dialog box, type the name of the site members access group, select it, and then click **Share**.</span></span>
    
8. <span data-ttu-id="e4ea1-185">按一下瀏覽器上的 [上一頁] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-185">Click the back button on your browser.</span></span>
    
9. <span data-ttu-id="e4ea1-186">按一下 [**\<網站 name> 擁有者**清單中。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-186">Click **\<site name> Owners** in the list.</span></span>
    
10. <span data-ttu-id="e4ea1-187">在 [人員與群組]\*\*\*\* 中，按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-187">In **People and Groups**, click **New**.</span></span>
    
11. <span data-ttu-id="e4ea1-188">在 [**共用**] 對話方塊中，輸入網站系統管理員存取群組的名稱、 加以選取，，然後按一下 [**共用**]。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-188">In the **Share** dialog box, type the name of the site admins access group, select it, and then click **Share**.</span></span>
    
12. <span data-ttu-id="e4ea1-189">按一下瀏覽器上的 [上一頁] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-189">Click the back button on your browser.</span></span>
    
13. <span data-ttu-id="e4ea1-190">按一下 [**\<網站 name> 訪客**清單中。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-190">Click **\<site name> Visitors** in the list.</span></span>
    
14. <span data-ttu-id="e4ea1-191">在 [人員與群組]\*\*\*\* 中，按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-191">In **People and Groups**, click **New**.</span></span>
    
15. <span data-ttu-id="e4ea1-192">在 [**共用**] 對話方塊中，輸入網站檢視者存取群組的名稱、 加以選取，，然後按一下 [**共用**]。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-192">In the **Share** dialog box, type the name of the site viewers access group, select it, and then click **Share**.</span></span>
    
16. <span data-ttu-id="e4ea1-193">關閉 [權限]\*\*\*\* 瀏覽器索引標籤。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-193">Close the **Permissions** tab of your browser.</span></span>
    
<span data-ttu-id="e4ea1-194">這些權限設定的結果是：</span><span class="sxs-lookup"><span data-stu-id="e4ea1-194">The results of these permission settings are:</span></span>
  
- <span data-ttu-id="e4ea1-195">**\<網站 name> 擁有者**SharePoint 群組包含網站管理員存取群組，所有成員都具有 [**完全控制**」 權限等級。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-195">The **\<site name> Owners** SharePoint group contains the site admins access group, in which all the members have the **Full control** permission level.</span></span>
    
- <span data-ttu-id="e4ea1-196">**\<網站 name> 成員**SharePoint 群組包含網站成員存取群組，其中的所有成員都具有 [**編輯**權限等級。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-196">The **\<site name> Members** SharePoint group contains the site members access group, in which all the members have the **Edit** permission level.</span></span>
    
- <span data-ttu-id="e4ea1-197">**\<網站 name> 訪客**SharePoint 群組包含網站檢視者存取群組，其中的所有成員都具有 [**讀取**權限等級。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-197">The **\<site name> Visitors** SharePoint group contains the site viewers access group, in which all the members have the **Read** permission level.</span></span>
    
- <span data-ttu-id="e4ea1-198">成員邀請其他成員或非成員要求存取的功能已停用。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-198">The ability for members to invite other members or for non-members to request access is disabled.</span></span>
    
<span data-ttu-id="e4ea1-199">以下是您產生的組態與設定成使用三個存取群組，填寫了使用者帳戶或 Azure AD 群組網站的三個 SharePoint 群組。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-199">Here is your resulting configuration with the three SharePoint groups for the site configured to use the three access groups, which are populated with user accounts or Azure AD groups.</span></span>
  
![最終組態的隔離 SharePoint Online 網站的存取群組與使用者帳戶。](media/e7618971-06ab-447b-90ff-d8be3790fe63.png)
  
<span data-ttu-id="e4ea1-201">您和網站，透過在存取群組，其中的群組成員資格的成員可以立即共同作業網站的資源。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-201">You and the members of the site, through group membership in one of the access groups, can now collaborate using the resources of the site.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="e4ea1-202">下一步</span><span class="sxs-lookup"><span data-stu-id="e4ea1-202">Next step</span></span>

<span data-ttu-id="e4ea1-203">當您需要變更站台存取群組成員資格，或建立具有自訂權限的文件資料夾時，請參閱 <<c0>管理隔離的 SharePoint Online 小組網站。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-203">When you need to change site access group membership or create a document folder with custom permissions, see [Manage an isolated SharePoint Online team site](manage-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e4ea1-204">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e4ea1-204">See Also</span></span>

<span data-ttu-id="e4ea1-205">[獨立的 SharePoint Online 小組網站](isolated-sharepoint-online-team-sites.md)。</span><span class="sxs-lookup"><span data-stu-id="e4ea1-205">[Isolated SharePoint Online team sites](isolated-sharepoint-online-team-sites.md)</span></span>
  
[<span data-ttu-id="e4ea1-206">設計獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="e4ea1-206">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)
  
[<span data-ttu-id="e4ea1-207">管理獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="e4ea1-207">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)
  



