---
title: 部署隔離的 SharePoint Online 小組網站
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 3033614b-e23b-4f68-9701-f62525eafaab
description: 摘要： 部署新隔離的 SharePoint Online 小組網站與這些逐步指示。
ms.openlocfilehash: d233ec46b1e7257a92451c781afd6c61312f44b8
ms.sourcegitcommit: e0f016aca7befc8806233a492ee916cbe646094f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/27/2018
ms.locfileid: "25345975"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="bb6d4-103">部署隔離的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="bb6d4-103">Deploy an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="bb6d4-104">**摘要：** 部署新隔離的 SharePoint Online 小組網站與這些逐步指示。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-104">**Summary:** Deploy a new isolated SharePoint Online team site with these step-by-step instructions.</span></span>
  
<span data-ttu-id="bb6d4-p101">本文是建立及設定 Microsoft Office 365 中隔離的 SharePoint Online 小組網站的逐步說明部署指南 》。這些步驟假設使用三個預設 SharePoint 群組及對應的權限層級、 與每個存取層級單一 Azure Active Directory AD 型的存取群組。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-p101">This article is a step-by-step deployment guide for creating and configuring an isolated SharePoint Online team site in Microsoft Office 365. These steps assume the use of the three default SharePoint groups and corresponding permission levels, with a single Azure Active Directory (AD)-based access group for each level of access.</span></span>
  
## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a><span data-ttu-id="bb6d4-107">階段 1： 建立並填入小組網站的存取群組</span><span class="sxs-lookup"><span data-stu-id="bb6d4-107">Phase 1: Create and populate the team site access groups</span></span>

<span data-ttu-id="bb6d4-108">在此階段中，您建立三個 Azure AD 式存取群組之三個預設 SharePoint 群組，並填入適當的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-108">In this phase, you create the three Azure AD-based access groups for the three default SharePoint groups and populate them with the appropriate user accounts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bb6d4-p102">下列步驟假設的所有必要的使用者帳戶已存在且已指派適當的授權。如果不使用，請將其新增並指派授權再繼續進行至步驟 1。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-p102">The following steps assume that all necessary user accounts already exist and are assigned the appropriate licenses. If not, please add them and assign licenses before proceeding to step 1.</span></span> 
  
### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a><span data-ttu-id="bb6d4-111">步驟 1： 列出網站的 SharePoint Online 系統管理員</span><span class="sxs-lookup"><span data-stu-id="bb6d4-111">Step 1: List the SharePoint Online admins for the site</span></span>

<span data-ttu-id="bb6d4-112">決定的使用者帳戶對應至隔離的小組網站的 SharePoint Online 系統管理員。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-112">Determine the set of user accounts corresponding to the SharePoint Online admins for the isolated team site.</span></span>
  
<span data-ttu-id="bb6d4-113">如果您正在管理使用者帳戶和群組透過 Office 365 並想要使用 Windows PowerShell，使其使用者清單主體名稱 (Upn) (範例 UPN: belindan@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-113">If you are managing user accounts and groups through Office 365 and want to use Windows PowerShell, make a list of their user principal names (UPNs) (example UPN: belindan@contoso.com).</span></span>
  
### <a name="step-2-list-the-members-for-the-site"></a><span data-ttu-id="bb6d4-114">步驟 2： 列出網站的成員</span><span class="sxs-lookup"><span data-stu-id="bb6d4-114">Step 2: List the members for the site</span></span>

<span data-ttu-id="bb6d4-115">決定一組使用者帳戶對應至將儲存在網站中的資源上共同作業的使用者可以隔離的小組網站的成員。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-115">Determine the set of user accounts corresponding to the members for the isolated team site, those who will be collaborating on resources stored within the site.</span></span>
  
<span data-ttu-id="bb6d4-p103">如果您正在管理使用者帳戶和群組透過 Office 365 並想要使用 PowerShell，使其 Upn 的清單。如果有許多網站成員的您可以儲存的 Upn 清單中的文字檔案並將其新增所有與單一 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-p103">If you are managing user accounts and groups through Office 365 and want to use PowerShell, make a list of their UPNs. If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>
  
### <a name="step-3-list-the-viewers-for-the-site"></a><span data-ttu-id="bb6d4-118">步驟 3： 列出之網站的檢視器</span><span class="sxs-lookup"><span data-stu-id="bb6d4-118">Step 3: List the viewers for the site</span></span>

<span data-ttu-id="bb6d4-119">決定對應至隔離的小組網站的檢視器的使用者可以檢視儲存在網站中的資源，但不是修改其或直接在其內容進行共同作業的使用者帳戶的設定。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-119">Determine the set of user accounts corresponding to the viewers of the isolated team site, those who can view the resources stored in the site but not modify them or directly collaborate on their contents.</span></span>
  
<span data-ttu-id="bb6d4-p104">如果您正在管理使用者帳戶和群組透過 Office 365 並想要使用 PowerShell，使其 Upn 的清單。如果有許多網站成員的您可以儲存的 Upn 清單中的文字檔案並將其新增所有與單一 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-p104">If you are managing user accounts and groups through Office 365 and want to use PowerShell, make a list of their UPNs. If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>
  
<span data-ttu-id="bb6d4-122">網站檢視者可能會包含 executive 管理、 法律顧問或是 inter-departmental 專案關係人。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-122">Viewers for the site might include executive management, legal counsel, or inter-departmental stakeholders.</span></span>
  
### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a><span data-ttu-id="bb6d4-123">步驟 4： 在 Azure AD 中建立網站的三種存取群組</span><span class="sxs-lookup"><span data-stu-id="bb6d4-123">Step 4: Create the three access groups for the site in Azure AD</span></span>

<span data-ttu-id="bb6d4-124">您需要在 Azure AD 中建立下列存取群組：</span><span class="sxs-lookup"><span data-stu-id="bb6d4-124">You need to create the following access groups in Azure AD:</span></span>
  
- <span data-ttu-id="bb6d4-125">網站管理員 （其中將包含從步驟 1 的清單）</span><span class="sxs-lookup"><span data-stu-id="bb6d4-125">Site admins (which will contain the list from step 1)</span></span>
    
- <span data-ttu-id="bb6d4-126">網站成員 （其中將包含步驟 2 的清單）</span><span class="sxs-lookup"><span data-stu-id="bb6d4-126">Site members (which will contain the list from step 2)</span></span>
    
- <span data-ttu-id="bb6d4-127">網站檢視器 （其中將包含從步驟 3 的清單）</span><span class="sxs-lookup"><span data-stu-id="bb6d4-127">Site viewers (which will contain the list from step 3)</span></span>
    
1. <span data-ttu-id="bb6d4-128">在瀏覽器中移至 Azure 入口網站[https://portal.azure.com](https://portal.azure.com)並簽署的已指派與使用者管理管理員或公司管理員角色的帳戶認證。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-128">In your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com) and sign in with the credentials of an account that has been assigned with User Management Admin or Company Administrator role.</span></span>
    
2. <span data-ttu-id="bb6d4-129">在 Azure 入口網站中，按一下 [Azure Active Directory] > [群組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-129">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>
    
3. <span data-ttu-id="bb6d4-130">在 [群組 - 所有群組]\*\*\*\* 刀鋒視窗中，按一下 [+ 新增群組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-130">On the **Groups - All groups** blade, click **+ New group**.</span></span>
    
4. <span data-ttu-id="bb6d4-131">在 [群組]\*\*\*\* 刀鋒視窗中：</span><span class="sxs-lookup"><span data-stu-id="bb6d4-131">On the **Group** blade:</span></span>
    
  - <span data-ttu-id="bb6d4-132">選取 [群組類型]\*\*\*\* 中的 [Office 365]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-132">Select **Office 365** in **Group type**.</span></span>
    
  - <span data-ttu-id="bb6d4-133">**名稱**] 中輸入群組名稱。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-133">Type the group name in **Name**.</span></span>
    
  - <span data-ttu-id="bb6d4-134">在 [**群組描述**輸入群組的描述。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-134">Type a description of the group in **Group description**.</span></span>
    
  - <span data-ttu-id="bb6d4-135">在 [成員資格類型]\*\*\*\* 中選取 [已指派]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-135">Select **Assigned** in **Membership type**.</span></span>
    
5. <span data-ttu-id="bb6d4-136">按一下 [建立]\*\*\*\*，然後關閉 [群組]\*\*\*\* 刀鋒視窗。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-136">Click **Create**, and then close the **Group** blade.</span></span>
    
6. <span data-ttu-id="bb6d4-137">針對您的其他群組重複步驟 3-5。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-137">Repeat steps 3-5 for your additional groups.</span></span>
    
> [!NOTE]
> <span data-ttu-id="bb6d4-p105">您需要使用 Azure 入口網站來建立的群組，讓他們有啟用 Office 功能。SharePoint Online 的隔離的網站稍後會設定為具有加密檔案並將權限指派給特定群組 Azure 資訊保護 (AIP) 標籤的高度機密網站中，如果允許的群組必須已建立以 Office 功能啟用。您不能變更 Office 功能的設定 Azure AD 群組之後已建立。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-p105">You need to use the Azure portal to create the groups so that they have Office features enabled. If a SharePoint Online isolated site is later configured as a Highly Confidential site with an Azure Information Protection (AIP) label to encrypt files and assign permission to specific groups, the permitted groups must have been created with Office features enabled. You cannot change the Office features setting of an Azure AD group after it has been created.</span></span> 
  
<span data-ttu-id="bb6d4-141">以下是三個網站存取群組與您所產生的設定。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-141">Here is your resulting configuration with the three site access groups.</span></span>
  
![用於部署隔離之 SharePoint Online 網站的三個存取群組。](media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)
  
### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a><span data-ttu-id="bb6d4-p106">步驟 5。將使用者帳戶新增至 access 群組</span><span class="sxs-lookup"><span data-stu-id="bb6d4-p106">Step 5. Add the user accounts to the access groups</span></span>

<span data-ttu-id="bb6d4-145">在此步驟中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="bb6d4-145">In this step, do the following:</span></span>
  
1. <span data-ttu-id="bb6d4-146">步驟 1 的使用者清單新增至網站管理員存取群組</span><span class="sxs-lookup"><span data-stu-id="bb6d4-146">Add the list of users from step 1 to the site admins access group</span></span>
    
2. <span data-ttu-id="bb6d4-147">步驟 2 的使用者清單新增至網站成員存取群組</span><span class="sxs-lookup"><span data-stu-id="bb6d4-147">Add the list of users from step 2 to the site members access group</span></span>
    
3. <span data-ttu-id="bb6d4-148">步驟 3 中的使用者清單新增至網站檢視者存取群組</span><span class="sxs-lookup"><span data-stu-id="bb6d4-148">Add the list of users from step 3 to the site viewers access group</span></span>
    
<span data-ttu-id="bb6d4-149">如果您正在管理使用者帳戶及 Windows Server AD 透過群組，將使用者新增到適當的存取群組使用標準的 Windows Server AD 使用者和群組管理程序，並等待與您的 Office 365 訂閱進行同步處理。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-149">If you are managing user accounts and groups through Windows Server AD, add users to the appropriate access groups using your normal Windows Server AD user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="bb6d4-p107">如果您正在管理使用者帳戶和群組透過 Office 365，您可以使用 Office 系統管理中心或 PowerShell。如果您有任何存取群組重複的群組名稱，您應該使用在 Office 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-p107">If you are managing user accounts and groups through Office 365, you can use the Office Admin center or PowerShell. If you have duplicate group names for any of the access groups, you should use the Office Admin center.</span></span>
  
<span data-ttu-id="bb6d4-152">針對 Office 系統管理中心中，使用已指派之使用者帳戶系統管理員或公司管理員角色的使用者帳戶登入並使用將適當的使用者帳戶新增群組和適當的存取群組的群組。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-152">For the Office Admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate user accounts and groups to the appropriate access groups.</span></span>
  
<span data-ttu-id="bb6d4-153">Powershell，第一個[連接使用 Azure Active Directory V2 PowerShell 模組](https://go.microsoft.com/fwlink/?linkid=842218)。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-153">For PowerShell, first [Connect with the Azure Active Directory V2 PowerShell module](https://go.microsoft.com/fwlink/?linkid=842218).</span></span>
  
<span data-ttu-id="bb6d4-154">接下來，使用下列的命令區塊將個別使用者帳戶新增至 access 群組：</span><span class="sxs-lookup"><span data-stu-id="bb6d4-154">Next, use the following command block to add an individual user account to an access group:</span></span>
  
```
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

> [!TIP]
> <span data-ttu-id="bb6d4-155">包含所有的 PowerShell 命令與 Excel 的文字檔案的 PowerShell 命令將會產生的設定工作表根據您的群組和使用者帳戶名稱、 下載[隔離 SharePoint Online 小組網站部署套件 （英文)](https://gallery.technet.microsoft.com/Isolated-SharePoint-Online-0b364907)。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-155">For a text file that contains all the PowerShell commands and an Excel configuration worksheet that generates PowerShell commands based on your group and user account names, download the [Isolated SharePoint Online Team Site Deployment Kit](https://gallery.technet.microsoft.com/Isolated-SharePoint-Online-0b364907).</span></span> 
  
<span data-ttu-id="bb6d4-156">如果您儲存的任何存取群組的使用者帳戶的 Upn 中的文字檔案時，您可以使用下列 PowerShell 命令區塊以將其新增到一次：</span><span class="sxs-lookup"><span data-stu-id="bb6d4-156">If you stored the UPNs of user accounts for any of the access groups in a text file, you can use the following PowerShell command block to add them all at one time:</span></span>
  
```
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

<span data-ttu-id="bb6d4-157">PowerShell 中使用下列的命令區塊將個別群組新增至 access 群組：</span><span class="sxs-lookup"><span data-stu-id="bb6d4-157">For PowerShell, use the following command block to add an individual group to an access group:</span></span>
  
```
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID

```

<span data-ttu-id="bb6d4-158">結果應該為下列各項：</span><span class="sxs-lookup"><span data-stu-id="bb6d4-158">The results should be the following:</span></span>
  
- <span data-ttu-id="bb6d4-159">網站管理員 Azure AD 群組包含的網站管理員的使用者帳戶或群組</span><span class="sxs-lookup"><span data-stu-id="bb6d4-159">The site admins Azure AD group contains the site admin user accounts or groups</span></span>
    
- <span data-ttu-id="bb6d4-160">網站成員 Azure AD 群組包含的網站成員使用者帳戶或群組</span><span class="sxs-lookup"><span data-stu-id="bb6d4-160">The site members Azure AD group contains the site member user accounts or groups</span></span>
    
- <span data-ttu-id="bb6d4-161">網站檢視者 Azure AD 群組包含使用者帳戶或僅可檢視網站內容的群組</span><span class="sxs-lookup"><span data-stu-id="bb6d4-161">The site viewers Azure AD group contains the user accounts or groups that can only view the site contents</span></span>
    
<span data-ttu-id="bb6d4-162">驗證每個存取群組與 Office 系統管理中心和下列 PowerShell 命令區塊的群組成員的清單：</span><span class="sxs-lookup"><span data-stu-id="bb6d4-162">Validate the list of group members for each access group with the Office Admin center or with the following PowerShell command block:</span></span>
  
```
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

<span data-ttu-id="bb6d4-163">以下是您所產生的設定與三個網站存取群組填入使用者帳戶或群組。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-163">Here is your resulting configuration with the three site access groups populated with user accounts or groups.</span></span>
  
![三個存取群組填寫了使用者帳戶。](media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)
  
## <a name="phase-2-create-and-configure-the-isolated-team-site"></a><span data-ttu-id="bb6d4-165">階段 2： 建立及設定隔離的小組網站</span><span class="sxs-lookup"><span data-stu-id="bb6d4-165">Phase 2: Create and configure the isolated team site</span></span>

<span data-ttu-id="bb6d4-166">在此階段中，您可以建立的隔離的 SharePoint Online 網站及設定的預設 SharePoint Online 權限等級以使用新的 Azure AD 式存取群組的權限。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-166">In this phase, you create the isolated SharePoint Online site and configure the permissions for the default SharePoint Online permission levels to use your new Azure AD-based access groups.</span></span>
  
<span data-ttu-id="bb6d4-167">首先，建立 SharePoint Online 小組網站進行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-167">First, create the SharePoint Online team site with these steps.</span></span>
  
1. <span data-ttu-id="bb6d4-p108">使用也可用來管理 SharePoint Online 小組網站的帳戶 (SharePoint Online 系統管理員) 登入 Office 365 入口網站。 如需說明，請參閱[在何處登入 Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-p108">Sign in to the Office 365 portal with an account that will also be used to administer the SharePoint Online team site (a SharePoint Online administrator). For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="bb6d4-170">在磚清單中，按一下 [SharePoint]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-170">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="bb6d4-171">在新的 [SharePoint] \*\*\*\* 瀏覽器索引標籤中，按一下 [+ 建立網站]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-171">In the new **SharePoint** tab of your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="bb6d4-172">在 [建立網站]\*\*\*\* 頁面上，按一下 [小組網站]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-172">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="bb6d4-173">在**站台名稱**] 中輸入小組網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-173">In **Site name**, type a name for the team site.</span></span> 
    
6. <span data-ttu-id="bb6d4-174">在**小組網站描述] 中，** 輸入網站的用途的選用描述。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-174">In **Team site description,** type an optional description of the purpose of the site.</span></span>
    
7. <span data-ttu-id="bb6d4-175">在 [隱私權設定]\*\*\*\* 中，選取 [私人 - 只有成員可以存取此網站]\*\*\*\*，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-175">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="bb6d4-176">在 [您想要新增誰?]\*\*\*\* 窗格上，按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-176">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="bb6d4-177">新的 SharePoint Online 小組網站下, 一步] 設定的權限。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-177">Next, from the new SharePoint Online team site, configure permissions.</span></span>
  
1. <span data-ttu-id="bb6d4-178">在工具列中，按一下設定圖示，然後按一下 [網站權限]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-178">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
    
2. <span data-ttu-id="bb6d4-179">在 [網站權限]\*\*\*\* 窗格中，按一下 [進階權限設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-179">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
    
3. <span data-ttu-id="bb6d4-180">在新的 [權限]\*\*\*\* 瀏覽器索引標籤中，按一下 [存取要求設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-180">On the new **Permissions** tab of your browser, click **Access Request Settings**.</span></span>
    
4. <span data-ttu-id="bb6d4-181">**存取要求設定**] 對話方塊中，清除 [**允許成員共用網站和個別的檔案及資料夾**，以及**允許存取權要求**（使已取消選取所有的三個核取方塊），然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-181">In the **Access Requests Settings** dialog box, clear **Allow member to share the site and individual files and folders** and **Allow access requests** (so that all three check boxes are cleared), and then click **OK**.</span></span>
    
5. <span data-ttu-id="bb6d4-182">在瀏覽器中的 [**權限**] 索引標籤中，按一下 [**\<站台名稱 > 成員**清單中。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-182">On the **Permissions** tab of your browser, click **\<site name> Members** in the list.</span></span>
    
6. <span data-ttu-id="bb6d4-183">在 [人員與群組]\*\*\*\* 中，按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-183">In **People and Groups**, click **New**.</span></span>
    
7. <span data-ttu-id="bb6d4-184">在 [**共用**] 對話方塊中，輸入網站成員存取群組的名稱、 選取它，，然後按一下 [**共用**。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-184">In the **Share** dialog box, type the name of the site members access group, select it, and then click **Share**.</span></span>
    
8. <span data-ttu-id="bb6d4-185">按一下瀏覽器上的 [上一頁] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-185">Click the back button on your browser.</span></span>
    
9. <span data-ttu-id="bb6d4-186">按一下 [**\<站台名稱 > 擁有者**清單中。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-186">Click **\<site name> Owners** in the list.</span></span>
    
10. <span data-ttu-id="bb6d4-187">在 [人員與群組]\*\*\*\* 中，按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-187">In **People and Groups**, click **New**.</span></span>
    
11. <span data-ttu-id="bb6d4-188">在 [**共用**] 對話方塊中，輸入網站管理員存取群組的名稱、 選取它，，然後按一下 [**共用**。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-188">In the **Share** dialog box, type the name of the site admins access group, select it, and then click **Share**.</span></span>
    
12. <span data-ttu-id="bb6d4-189">按一下瀏覽器上的 [上一頁] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-189">Click the back button on your browser.</span></span>
    
13. <span data-ttu-id="bb6d4-190">按一下 [**\<站台名稱 > 訪客**清單中。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-190">Click **\<site name> Visitors** in the list.</span></span>
    
14. <span data-ttu-id="bb6d4-191">在 [人員與群組]\*\*\*\* 中，按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-191">In **People and Groups**, click **New**.</span></span>
    
15. <span data-ttu-id="bb6d4-192">在 [**共用**] 對話方塊中，輸入網站檢視者存取群組的名稱、 選取它，，然後按一下 [**共用**。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-192">In the **Share** dialog box, type the name of the site viewers access group, select it, and then click **Share**.</span></span>
    
16. <span data-ttu-id="bb6d4-193">關閉 [權限]\*\*\*\* 瀏覽器索引標籤。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-193">Close the **Permissions** tab of your browser.</span></span>
    
<span data-ttu-id="bb6d4-194">這些權限設定的結果是：</span><span class="sxs-lookup"><span data-stu-id="bb6d4-194">The results of these permission settings are:</span></span>
  
- <span data-ttu-id="bb6d4-195">**\<站台名稱 > 擁有者**SharePoint 群組包含網站管理員存取群組中的所有成員具有 [**完全控制**」 權限層級。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-195">The **\<site name> Owners** SharePoint group contains the site admins access group, in which all the members have the **Full control** permission level.</span></span>
    
- <span data-ttu-id="bb6d4-196">**\<站台名稱 > 成員**SharePoint 群組包含網站成員存取群組，其中的所有成員擁有 「**編輯**」 權限層級。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-196">The **\<site name> Members** SharePoint group contains the site members access group, in which all the members have the **Edit** permission level.</span></span>
    
- <span data-ttu-id="bb6d4-197">**\<站台名稱 > 訪客**SharePoint 群組包含網站檢視者存取群組中的所有成員具有 「**讀取**」 權限等級。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-197">The **\<site name> Visitors** SharePoint group contains the site viewers access group, in which all the members have the **Read** permission level.</span></span>
    
- <span data-ttu-id="bb6d4-198">若要邀請其他成員的成員或非成員要求存取的功能已停用。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-198">The ability for members to invite other members or for non-members to request access is disabled.</span></span>
    
<span data-ttu-id="bb6d4-199">以下是您所產生的設定與網站設定成使用三個會填入使用者帳戶的存取群組或 Azure AD 群組的三種 SharePoint 群組。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-199">Here is your resulting configuration with the three SharePoint groups for the site configured to use the three access groups, which are populated with user accounts or Azure AD groups.</span></span>
  
![具有存取群組與使用者帳戶之隔離 SharePoint Online 網站的最後設定](media/e7618971-06ab-447b-90ff-d8be3790fe63.png)
  
<span data-ttu-id="bb6d4-201">您與網站，透過群組成員資格之一的存取群組的成員可以立即共同作業網站的資源。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-201">You and the members of the site, through group membership in one of the access groups, can now collaborate using the resources of the site.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="bb6d4-202">下一步</span><span class="sxs-lookup"><span data-stu-id="bb6d4-202">Next step</span></span>

<span data-ttu-id="bb6d4-203">當您需要變更網站的存取群組成員資格或建立自訂的權限的文件資料夾時，請參閱[管理隔離的 SharePoint Online 小組網站](manage-an-isolated-sharepoint-online-team-site.md)。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-203">When you need to change site access group membership or create a document folder with custom permissions, see [Manage an isolated SharePoint Online team site](manage-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bb6d4-204">另請參閱</span><span class="sxs-lookup"><span data-stu-id="bb6d4-204">See Also</span></span>

<span data-ttu-id="bb6d4-205">[隔離的 SharePoint Online 小組網站](isolated-sharepoint-online-team-sites.md)。</span><span class="sxs-lookup"><span data-stu-id="bb6d4-205">[Isolated SharePoint Online team sites](isolated-sharepoint-online-team-sites.md)</span></span>
  
[<span data-ttu-id="bb6d4-206">設計獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="bb6d4-206">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)
  
[<span data-ttu-id="bb6d4-207">管理獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="bb6d4-207">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)
  



