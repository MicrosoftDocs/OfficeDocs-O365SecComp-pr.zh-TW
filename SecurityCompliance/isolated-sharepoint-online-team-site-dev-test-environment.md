---
title: 隔離的 SharePoint Online 小組網站開發/測試環境
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: d1795031-beef-49ea-a6fc-5da5450d320d
description: 摘要：設定 SharePoint Online 小組網站，該網站與 Office 365 開發/測試環境中組織的其他網站隔離。
ms.openlocfilehash: 0aa5e6e47344134b1e103fb287f627afd2808af6
ms.sourcegitcommit: e0f016aca7befc8806233a492ee916cbe646094f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/27/2018
ms.locfileid: "25345815"
---
# <a name="isolated-sharepoint-online-team-site-devtest-environment"></a><span data-ttu-id="792a8-103">隔離的 SharePoint Online 小組網站開發/測試環境</span><span class="sxs-lookup"><span data-stu-id="792a8-103">Isolated SharePoint Online team site dev/test environment</span></span>

 <span data-ttu-id="792a8-104">**摘要：** 設定 SharePoint Online 小組網站，該網站與 Office 365 開發/測試環境中組織的其他網站隔離。</span><span class="sxs-lookup"><span data-stu-id="792a8-104">**Summary:** Configure a SharePoint Online team site that is isolated from the rest of the organization in your Office 365 dev/test environment.</span></span>
  
<span data-ttu-id="792a8-p101">在 Office 365 中的 SharePoint Online 小組網站都是使用一般的文件庫、 OneNote 筆記本，以及其他服務的共同作業的位置。在許多情況下，您跨部門或組織要寬存取及共同作業。不過，在某些情況下，您想要緊密控制存取及一小群人員之間的共同作業的權限。</span><span class="sxs-lookup"><span data-stu-id="792a8-p101">SharePoint Online team sites in Office 365 are locations for collaboration using a common document library, a OneNote notebook, and other services. In many cases, you want wide access and collaboration across departments or organizations. However, in some cases, you want to tightly control the access and permissions for collaboration among a small group of people.</span></span>
  
<span data-ttu-id="792a8-p102">由 SharePoint 群組與權限層級控制存取 SharePoint Online 小組網站與使用者可以執行的動作。根據預設，SharePoint Online 網站會有三種存取層級：</span><span class="sxs-lookup"><span data-stu-id="792a8-p102">Access to SharePoint Online team sites and what users can do is controlled by SharePoint groups and permission levels. By default, SharePoint Online sites have three levels of access:</span></span>
  
- <span data-ttu-id="792a8-110">**成員**，該使用者可以檢視、建立及修改網站上的資源。</span><span class="sxs-lookup"><span data-stu-id="792a8-110">**Members**, who can view, create, and modify resources on the site.</span></span>
    
- <span data-ttu-id="792a8-111">**擁有者**，該使用者擁有網站的完整控制權，包括變更權限的能力。</span><span class="sxs-lookup"><span data-stu-id="792a8-111">**Owners**, who have complete control of the site, including the ability to change permissions.</span></span>
    
- <span data-ttu-id="792a8-112">**訪客**，該使用者只能夠檢視網站上的資源。</span><span class="sxs-lookup"><span data-stu-id="792a8-112">**Visitors**, who only can view resources on the site.</span></span>
    
<span data-ttu-id="792a8-p103">本文章步驟您完成秘密研究專案隔離 SharePoint Online 小組網站的設定名為 ProjectX。存取需求是：</span><span class="sxs-lookup"><span data-stu-id="792a8-p103">This article steps you through the configuration of an isolated SharePoint Online team site for a secret research project named ProjectX. The access requirements are:</span></span>
  
- <span data-ttu-id="792a8-115">只有專案的成員才能夠存取網站及其內容 (文件、OneNote 筆記本、頁面)，編輯和檢視 SharePoint 權限層級是透過群組成員資格進行控制的。</span><span class="sxs-lookup"><span data-stu-id="792a8-115">Only members of the project can access the site and its contents (documents, OneNote Notebook, Pages), with edit and view SharePoint permission levels controlled through group membership.</span></span>
    
- <span data-ttu-id="792a8-116">只有網站建立者和網站的 Admins 群組成員可以執行網站管理，包括修改網站層級權限。</span><span class="sxs-lookup"><span data-stu-id="792a8-116">Only the site creator and members of an Admins group for the site can perform site administration, which includes modifying site-level permissions.</span></span>
    
<span data-ttu-id="792a8-117">在您的 Office 365 開發/測試環境中設定隔離的 SharePoint Online 小組網站有三個階段：</span><span class="sxs-lookup"><span data-stu-id="792a8-117">There are three phases to setting up an isolated SharePoint Online team site in your Office 365 dev/test environment:</span></span>
  
1. <span data-ttu-id="792a8-118">建立 Office 365 開發/測試環境。
</span><span class="sxs-lookup"><span data-stu-id="792a8-118">Create the Office 365 dev/test environment.</span></span>
    
2. <span data-ttu-id="792a8-119">為 ProjectX 建立使用者和群組。</span><span class="sxs-lookup"><span data-stu-id="792a8-119">Create the users and groups for ProjectX.</span></span>
    
3. <span data-ttu-id="792a8-120">建立新的 ProjectX SharePoint Online 小組網站並且隔離它。</span><span class="sxs-lookup"><span data-stu-id="792a8-120">Create a new ProjectX SharePoint Online team site and isolate it.</span></span>
    
> [!TIP]
> <span data-ttu-id="792a8-121">按一下[這裡](http://aka.ms/catlgstack)，可查看 One Microsoft Cloud 測試實驗室指南堆疊中文件的所有視覺對應。</span><span class="sxs-lookup"><span data-stu-id="792a8-121">Click [here](http://aka.ms/catlgstack) for a visual map to all the articles in the One Microsoft Cloud Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-lightweight-or-simulated-enterprise-office-365-devtest-environment"></a><span data-ttu-id="792a8-122">階段 1：建置輕量型或模擬的企業 Office 365 開發/測試環境</span><span class="sxs-lookup"><span data-stu-id="792a8-122">Phase 1: Build out your lightweight or simulated enterprise Office 365 dev/test environment</span></span>

<span data-ttu-id="792a8-123">如果您只是要建立的最低需求的輕量型方式隔離的 SharePoint Online 小組網站，請在階段 2 和 3 的[Office 365 開發人員/測試環境](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment)中遵循的指示。</span><span class="sxs-lookup"><span data-stu-id="792a8-123">If you just want to create an isolated SharePoint Online team site in a lightweight way with the minimum requirements, follow the instructions in phases 2 and 3 of [Office 365 dev/test environment](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment).</span></span>
  
<span data-ttu-id="792a8-124">如果您想要建立隔離的 SharePoint Online 小組網站中的模擬的企業設定，請遵循[DirSync Office 365 開發人員/測試環境](https://docs.microsoft.com/office365/enterprise/dirsync-for-your-office-365-dev-test-environment)中的指示。</span><span class="sxs-lookup"><span data-stu-id="792a8-124">If you want to create an isolated SharePoint Online team site in a simulated enterprise configuration, follow the instructions in [DirSync for your Office 365 dev/test environment](https://docs.microsoft.com/office365/enterprise/dirsync-for-your-office-365-dev-test-environment).</span></span>
  
> [!NOTE]
> <span data-ttu-id="792a8-p104">建立隔離的 SharePoint Online 網站不需要模擬的企業開發/測試環境，其中包括模擬的內部網路 (連線到網際網路) 和 Windows Server AD 樹系中的目錄同步處理。它在這裡提供作為選項，讓您可以在代表典型組織的環境中測試建立隔離的 SharePoint Online 網站並且進行試驗。</span><span class="sxs-lookup"><span data-stu-id="792a8-p104">Creating an isolated SharePoint Online site does not require the simulated enterprise dev/test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test an isolated SharePoint Online site and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-create-user-accounts-and-access-groups"></a><span data-ttu-id="792a8-127">階段 2： 建立使用者帳戶並存取群組</span><span class="sxs-lookup"><span data-stu-id="792a8-127">Phase 2: Create user accounts and access groups</span></span>

<span data-ttu-id="792a8-128">使用[Connect to Office 365 PowerShell](https://technet.microsoft.com/library/dn975125.aspx)中的指示來連線至您的 Office 365 軌跡訂閱與您的全域管理員帳戶從：</span><span class="sxs-lookup"><span data-stu-id="792a8-128">Use the instructions in [Connect to Office 365 PowerShell](https://technet.microsoft.com/library/dn975125.aspx) to connect to your Office 365 trail subscription with your global administrator account from:</span></span>
  
- <span data-ttu-id="792a8-129">您的電腦 (適用於輕量型 Office 365 開發/測試環境)。</span><span class="sxs-lookup"><span data-stu-id="792a8-129">Your computer (for the lightweight Office 365 dev/test environment).</span></span>
    
- <span data-ttu-id="792a8-130">CLIENT1 虛擬機器 (適用於模擬的企業 Office 365 開發/測試環境)。</span><span class="sxs-lookup"><span data-stu-id="792a8-130">The CLIENT1 virtual machine (for the simulated enterprise Office 365 dev/test environment).</span></span>
    
<span data-ttu-id="792a8-131">若要建立新的存取群組 ProjectX SharePoint Online 小組網站，請在 Windows Azure Active Directory Module for Windows PowerShell 提示字元處執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="792a8-131">To create the new access groups for the ProjectX SharePoint Online team site, run these commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
  
```
$groupName="ProjectX-Members"
$groupDesc="People allowed to collaborate for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Admins"
$groupDesc="People allowed to administer SharePoint for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Viewers"
$groupDesc="People allowed to view the SharePoint resources for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
```

> [!TIP]
> <span data-ttu-id="792a8-132">按一下[這裡](https://gallery.technet.microsoft.com/PowerShell-commands-for-an-b2608df1)包含所有的 PowerShell 命令會在本文中的文字檔案。</span><span class="sxs-lookup"><span data-stu-id="792a8-132">Click [here](https://gallery.technet.microsoft.com/PowerShell-commands-for-an-b2608df1) for a text file that contains all of the PowerShell commands in this article.</span></span>
  
<span data-ttu-id="792a8-133">填入您的組織名稱 (範例︰contosotoycompany)，位置的兩個字元國家/地區代碼，再從適用於 Windows PowerShell 的 Windows Azure Active Directory 模組提示字元中執行下列命令︰</span><span class="sxs-lookup"><span data-stu-id="792a8-133">Fill in your organization name (example: contosotoycompany), the two-character country code for your location, and then run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
  
```
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$licAssignment= $orgName + ":ENTERPRISEPREMIUM"
$userName= "designer@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Designer" -FirstName Lead -LastName Designer -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="792a8-134">從 **New-MsolUser** 命令的顯示畫面中，記下針對 Lead Designer 帳戶產生的密碼，並且將密碼記錄在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="792a8-134">From the display of the **New-MsolUser** command, note the generated password for the Lead Designer account and record it in a safe location.</span></span>
  
<span data-ttu-id="792a8-135">從適用於 Windows PowerShell 的 Windows Azure Active Directory 模組提示字元中執行下列命令︰</span><span class="sxs-lookup"><span data-stu-id="792a8-135">Run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
  
```
$userName= "researcher@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Researcher" -FirstName Lead -LastName Researcher -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="792a8-136">從 **New-MsolUser** 命令的顯示畫面中，記下針對 Lead Researcher 帳戶產生的密碼，並且將密碼記錄在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="792a8-136">From the display of the **New-MsolUser** command, note the generated password for the Lead Researcher account and record it in a safe location.</span></span>
  
<span data-ttu-id="792a8-137">從適用於 Windows PowerShell 的 Windows Azure Active Directory 模組提示字元中執行下列命令︰</span><span class="sxs-lookup"><span data-stu-id="792a8-137">Run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
  
```
$userName= "devvp@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Development VP" -FirstName Development -LastName VP -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="792a8-138">從 **New-MsolUser** 命令的顯示畫面中，記下針對 Development VP 帳戶產生的密碼，並且將密碼記錄在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="792a8-138">From the display of the **New-MsolUser** command, note the generated password for the Development VP account and record it in a safe location.</span></span>
  
<span data-ttu-id="792a8-139">下一步] 將帳戶新增至新的存取群組，請從 Windows Azure Active Directory Module for Windows PowerShell 提示字元下執行下列 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="792a8-139">Next, to add the new accounts to the new access groups, run these PowerShell commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
  
```
$grpName="ProjectX-Members"
$userUPN="designer@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$userUPN="researcher@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Admins"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userCredential.UserName }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Viewers"
$userUPN="devvp@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
```

<span data-ttu-id="792a8-140">結果：</span><span class="sxs-lookup"><span data-stu-id="792a8-140">Results:</span></span>
  
- <span data-ttu-id="792a8-141">ProjectX 成員存取群組包含導致設計工具] 和 [導致研究者使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="792a8-141">The ProjectX-Members access group contains the Lead Designer and Lead Researcher user accounts</span></span>
    
- <span data-ttu-id="792a8-142">ProjectX 系統管理員存取群組包含您的試用版訂閱的全域管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="792a8-142">The ProjectX-Admins access group contains the global administrator account for your trial subscription</span></span>
    
- <span data-ttu-id="792a8-143">ProjectX 檢視者存取群組包含開發 VP 使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="792a8-143">The ProjectX-Viewers access group contains the Development VP user account</span></span>
    
<span data-ttu-id="792a8-144">圖 1 顯示的存取群組和其成員資格。</span><span class="sxs-lookup"><span data-stu-id="792a8-144">Figure 1 shows the access groups and their membership.</span></span>
  
<span data-ttu-id="792a8-145">**圖 1**</span><span class="sxs-lookup"><span data-stu-id="792a8-145">**Figure 1**</span></span>

![獨立的 SharePoint Online 群組網站的 Office 365 群組及其成員資格](media/5b7373b9-2a80-4880-afe5-63ffb17237e6.png)
  
## <a name="phase-3-create-a-new-projectx-sharepoint-online-team-site-and-isolate-it"></a><span data-ttu-id="792a8-147">階段 3：建立新的 ProjectX SharePoint Online 小組網站並且隔離它</span><span class="sxs-lookup"><span data-stu-id="792a8-147">Phase 3: Create a new ProjectX SharePoint Online team site and isolate it</span></span>

<span data-ttu-id="792a8-148">若要為 ProjectX 建立 SharePoint Online 小組網站，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="792a8-148">To create a SharePoint Online team site for ProjectX, do the following:</span></span>
  
1. <span data-ttu-id="792a8-149">在 [您的本機電腦 （輕量級的設定） 使用瀏覽器或在 CLIENT1 上 （模擬的企業組態） 登入 Office 365 入口網站 ([https://portal.office.com](https://portal.office.com)) 使用全域管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="792a8-149">Using a browser on either your local computer (lightweight configuration) or on CLIENT1 (simulated enterprise configuration), sign in to the Office 365 portal ([https://portal.office.com](https://portal.office.com)) using your global administrator account.</span></span>
    
2. <span data-ttu-id="792a8-150">在磚清單中，按一下 [SharePoint]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="792a8-150">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="792a8-151">在 [新增 SharePoint] 索引標籤在瀏覽器中按一下 [ **+ 建立網站**。</span><span class="sxs-lookup"><span data-stu-id="792a8-151">On the new SharePoint tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="792a8-p105">在**小組網站名稱**] 中輸入**ProjectX**。**隱私權設定**] 中選取 [**私人-只有成員可以存取此站台**。</span><span class="sxs-lookup"><span data-stu-id="792a8-p105">In **Team site name**, type **ProjectX**. In **Privacy settings**, select **Private - only members can access this site**.</span></span>
    
5. <span data-ttu-id="792a8-154">在**小組網站描述**] 中，輸入**SharePoint 網站的 ProjectX**]，然後按 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="792a8-154">In **Team site description**, type **SharePoint site for ProjectX**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="792a8-155">在**您要新增誰**？] 窗格中，按一下 [**完成]**。</span><span class="sxs-lookup"><span data-stu-id="792a8-155">On the **Who do you want to add**? pane, click **Finish**.</span></span>
    
7. <span data-ttu-id="792a8-156">在瀏覽器中的 [工具] 列中新的**ProjectX 首頁**] 索引標籤上按一下 [設定] 圖示，和 [**網站權限**。</span><span class="sxs-lookup"><span data-stu-id="792a8-156">On the new **ProjectX-Home** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
    
8. <span data-ttu-id="792a8-157">在 [網站權限]\*\*\*\* 窗格中，按一下 [進階權限設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="792a8-157">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
    
9. <span data-ttu-id="792a8-158">在新**權限： X 專案**在瀏覽器] 索引標籤中按一下 [**存取要求的設定**。</span><span class="sxs-lookup"><span data-stu-id="792a8-158">In the new **Permissions: Project X** tab in your browser, click **Access Request Settings**.</span></span>
    
10. <span data-ttu-id="792a8-159">**存取要求設定**] 對話方塊中，清除 [**允許成員] 共用網站和個別的檔案及資料夾**並**允許存取權要求**（使已取消選取所有的三個核取方塊），然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="792a8-159">In the **Access Requests Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow access requests** (so that all three check boxes are cleared), and then click **OK**.</span></span>
    
11. <span data-ttu-id="792a8-160">清單中的 [ **ProjectX 成員**。</span><span class="sxs-lookup"><span data-stu-id="792a8-160">Click **ProjectX Members** in the list.</span></span>
    
12. <span data-ttu-id="792a8-161">在 [人員與群組]\*\*\*\* 頁面上，按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="792a8-161">On the **People and Groups** page, click **New**.</span></span>
    
13. <span data-ttu-id="792a8-162">在 [**共用**] 對話方塊中，輸入**ProjectX 成員**、 選取它，，然後按一下 [**共用**]。</span><span class="sxs-lookup"><span data-stu-id="792a8-162">In the **Share** dialog box, type **ProjectX-Members**, select it, and then click **Share**.</span></span>
    
14. <span data-ttu-id="792a8-163">按一下瀏覽器上的 [上一頁] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="792a8-163">Click the back button on your browser.</span></span>
    
15. <span data-ttu-id="792a8-164">按一下 [ **ProjectX 擁有者**] 清單中。</span><span class="sxs-lookup"><span data-stu-id="792a8-164">Click **ProjectX Owners** in the list.</span></span>
    
16. <span data-ttu-id="792a8-165">在 [人員與群組]\*\*\*\* 頁面上，按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="792a8-165">On the **People and Groups** page, click **New**.</span></span>
    
17. <span data-ttu-id="792a8-166">在 [**共用**] 對話方塊中，輸入**ProjectX Admins**、 選取它，，然後按一下 [**共用**。</span><span class="sxs-lookup"><span data-stu-id="792a8-166">In the **Share** dialog box, type **ProjectX-Admins**, select it, and then click **Share**.</span></span>
    
18. <span data-ttu-id="792a8-167">按一下瀏覽器上的 [上一頁] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="792a8-167">Click the back button on your browser.</span></span>
    
19. <span data-ttu-id="792a8-168">按一下 [ **ProjectX 訪客**] 清單中。</span><span class="sxs-lookup"><span data-stu-id="792a8-168">Click **ProjectX Visitors** in the list.</span></span>
    
20. <span data-ttu-id="792a8-169">在 [人員與群組]\*\*\*\* 頁面上，按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="792a8-169">On the **People and Groups** page, click **New**.</span></span>
    
21. <span data-ttu-id="792a8-170">在 [**共用**] 對話方塊中，輸入**ProjectX 檢視**、 選取它，，然後按一下 [**共用**。</span><span class="sxs-lookup"><span data-stu-id="792a8-170">In the **Share** dialog box, type **ProjectX-Viewers**, select it, and then click **Share**.</span></span>
    
22. <span data-ttu-id="792a8-171">關閉瀏覽器中的 [**人員與群組**] 索引標籤、 按一下 [瀏覽器上**ProjectX 常用**] 索引標籤，然後關閉 [**網站權限**] 窗格。</span><span class="sxs-lookup"><span data-stu-id="792a8-171">Close the **People and Groups** tab in your browser, click the **ProjectX-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>
    
<span data-ttu-id="792a8-172">以下是設定權限的結果：</span><span class="sxs-lookup"><span data-stu-id="792a8-172">Here are the results of configuring permissions:</span></span>
  
- <span data-ttu-id="792a8-173">ProjectX 成員 SharePoint 群組包含只 ProjectX 成員存取群組 （其中包含只會導致設計工具] 和 [導致研究者使用者帳戶） 和 ProjectX 群組 （其中包含只有一個全域管理員使用者帳戶）。</span><span class="sxs-lookup"><span data-stu-id="792a8-173">The ProjectX Members SharePoint group contains only the ProjectX-Members access group (which contains only the Lead Designer and Lead Researcher user accounts) and the ProjectX group (which contains only the global administrator user account).</span></span>
    
- <span data-ttu-id="792a8-174">ProjectX 擁有者 SharePoint 群組包含只 ProjectX 系統管理員存取群組 （其中包含只有一個全域管理員使用者帳戶）。</span><span class="sxs-lookup"><span data-stu-id="792a8-174">The ProjectX Owners SharePoint group contains only the ProjectX-Admins access group (which contains only the global administrator user account).</span></span>
    
- <span data-ttu-id="792a8-175">ProjectX 訪客 SharePoint 群組包含只 ProjectX 檢視者存取群組 （其中包含只有開發 VP 使用者帳戶）。</span><span class="sxs-lookup"><span data-stu-id="792a8-175">The ProjectX Visitors SharePoint group contains only the ProjectX-Viewers access group (which contains only the Development VP user account).</span></span>
    
- <span data-ttu-id="792a8-176">成員無法修改網站層級權限 (這個操作只能由 ProjectX-Admins 群組的成員完成)。</span><span class="sxs-lookup"><span data-stu-id="792a8-176">Members cannot modify site-level permissions (this can only be done by members of the ProjectX-Admins group).</span></span>
    
- <span data-ttu-id="792a8-177">其他使用者帳戶無法存取網站或它的資源，或要求網站的存取權。</span><span class="sxs-lookup"><span data-stu-id="792a8-177">Other user accounts cannot access the site or its resources or request access to the site.</span></span>
    
<span data-ttu-id="792a8-178">圖 2 顯示 SharePoint 群組及其成員資格。</span><span class="sxs-lookup"><span data-stu-id="792a8-178">Figure 2 shows the SharePoint groups and their membership.</span></span>
  
<span data-ttu-id="792a8-179">**圖 2**</span><span class="sxs-lookup"><span data-stu-id="792a8-179">**Figure 2**</span></span>

![獨立的 SharePoint Online 群組網站的 SharePoint Online 群組及其成員資格](media/595abff4-64f9-49de-a37a-c70c6856936b.png)
  
<span data-ttu-id="792a8-181">現在我們示範使用導致 Designer 使用者帳戶的存取：</span><span class="sxs-lookup"><span data-stu-id="792a8-181">Now let's demonstrate access using the Lead Designer user account:</span></span>
  
1. <span data-ttu-id="792a8-182">關閉瀏覽器上**ProjectX 常用**] 索引標籤，然後按一下 [在瀏覽器中的 [ **Microsoft Office Home** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="792a8-182">Close the **ProjectX-Home** tab in your browser, and then click the **Microsoft Office Home** tab in your browser.</span></span>
    
2. <span data-ttu-id="792a8-183">按一下您的全域管理員名稱] 和 [**登出**。</span><span class="sxs-lookup"><span data-stu-id="792a8-183">Click the name of your global administrator, and then click **Sign out**.</span></span>
    
3. <span data-ttu-id="792a8-184">登入 Office 365 入口網站 ([https://portal.office.com](https://portal.office.com)) 使用導致 Designer 帳戶名稱和其密碼。</span><span class="sxs-lookup"><span data-stu-id="792a8-184">Sign in to the Office 365 portal ([https://portal.office.com](https://portal.office.com)) using the Lead Designer account name and its password.</span></span>
    
4. <span data-ttu-id="792a8-185">在磚清單中，按一下 [SharePoint]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="792a8-185">In the list of tiles, click **SharePoint**.</span></span>
    
5. <span data-ttu-id="792a8-p106">在 [新**SharePoint** ] 索引標籤在瀏覽器在 [搜尋] 方塊中輸入**ProjectX**啟動搜尋] 及 [ **ProjectX**小組網站。您應該 ProjectX 小組網站的瀏覽器中看到新的索引標籤。</span><span class="sxs-lookup"><span data-stu-id="792a8-p106">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box, activate the search, and then click the **ProjectX** team site. You should see a new tab in your browser for the ProjectX team site.</span></span>
    
6. <span data-ttu-id="792a8-p107">按一下 [設定] 圖示。請注意是沒有**網站**權限] 選項。因為只有 ProjectX Admins 群組的成員可以修改在網站上的權限正確</span><span class="sxs-lookup"><span data-stu-id="792a8-p107">Click the settings icon. Notice that there is no option for **Site Permissions**. This is correct because only the members of the ProjectX-Admins group can modify permissions on the site</span></span>
    
7. <span data-ttu-id="792a8-191">開啟 [記事本] 或您選擇的文字編輯器。</span><span class="sxs-lookup"><span data-stu-id="792a8-191">Open Notepad or a text editor of your choice.</span></span>
    
8. <span data-ttu-id="792a8-192">複製 ProjectX 小組網站的 URL，並將它貼至記事本或文字編輯器中新的一行。</span><span class="sxs-lookup"><span data-stu-id="792a8-192">Copy the URL of the ProjectX team site and paste it on a new line in Notepad or your text editor.</span></span>
    
9. <span data-ttu-id="792a8-193">在 [新**ProjectX 首頁**] 索引標籤在瀏覽器中按一下 [**文件**。</span><span class="sxs-lookup"><span data-stu-id="792a8-193">On the new **ProjectX-Home** tab in your browser, click **Documents**.</span></span>
    
10. <span data-ttu-id="792a8-194">複製 ProjectX 文件資料夾的 URL，並將它貼至記事本或文字編輯器中新的一行。</span><span class="sxs-lookup"><span data-stu-id="792a8-194">Copy the URL of the ProjectX documents folder and paste it on a new line in Notepad or your text editor.</span></span>
    
11. <span data-ttu-id="792a8-195">在 [新**ProjectX 文件**] 索引標籤在瀏覽器中按一下 [**新增 > Word 文件**。</span><span class="sxs-lookup"><span data-stu-id="792a8-195">On the new **ProjectX-Documents** tab in your browser, click **New > Word document**.</span></span>
    
12. <span data-ttu-id="792a8-p108">**Word Online** ] 頁面中輸入一些文字、 等待以指出**儲存**] 和 [上一頁] 按鈕在瀏覽器中，然後重新整理] 頁面上的狀態。您應該會看見新**Document.docx** **文件**] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="792a8-p108">Type some text in the **Word Online** page, wait for the status to indicate **Saved**, click the back button on your browser, and then refresh the page. You should see a new **Document.docx** in the **Documents** folder.</span></span>
    
13. <span data-ttu-id="792a8-198">按一下 [ **Document.docx**文件的省略符號和 [**取得] 連結**。</span><span class="sxs-lookup"><span data-stu-id="792a8-198">Click the ellipsis for the **Document.docx** document, and then click **Get a link**.</span></span>
    
14. <span data-ttu-id="792a8-199">複製**共用 'Document.docx'** ] 對話方塊中的 URL 並將其貼上 [記事本] 或文字編輯器中，新增一行，然後關閉**共用 'Document.docx'** ] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="792a8-199">Copy the URL in the **Share 'Document.docx'** dialog box and paste it on a new line in Notepad or your text editor, and then close the **Share 'Document.docx'** dialog box.</span></span>
    
15. <span data-ttu-id="792a8-200">關閉瀏覽器上的 [ **ProjectX 文件**及**SharePoint** ] 索引標籤，然後按一下 [ **Microsoft Office Home** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="792a8-200">Close the **ProjectX-Documents** and **SharePoint** tabs in your browser, and then click the **Microsoft Office Home** tab.</span></span>
    
16. <span data-ttu-id="792a8-201">按一下 [**客戶販售 Designer**名稱] 和 [**登出**。</span><span class="sxs-lookup"><span data-stu-id="792a8-201">Click the **Lead Designer** name, and then click **Sign out**.</span></span>
    
<span data-ttu-id="792a8-202">現在我們示範使用開發 VP 使用者帳戶的存取：</span><span class="sxs-lookup"><span data-stu-id="792a8-202">Now let's demonstrate access using the Development VP user account:</span></span>
  
1. <span data-ttu-id="792a8-203">登入 Office 365 入口網站 ([https://portal.office.com](https://portal.office.com)) 使用開發 VP 帳戶名稱和其密碼。</span><span class="sxs-lookup"><span data-stu-id="792a8-203">Sign in to the Office 365 portal ([https://portal.office.com](https://portal.office.com)) using the Development VP account name and its password.</span></span>
    
2. <span data-ttu-id="792a8-204">在磚清單中，按一下 [SharePoint]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="792a8-204">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="792a8-p109">在 [新**SharePoint** ] 索引標籤在瀏覽器在 [搜尋] 方塊中輸入**ProjectX**啟動搜尋] 及 [ **ProjectX**小組網站。您應該 ProjectX 小組網站的瀏覽器中看到新的索引標籤。</span><span class="sxs-lookup"><span data-stu-id="792a8-p109">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box, activate the search, and then click the **ProjectX** team site. You should see a new tab in your browser for the ProjectX team site.</span></span>
    
4. <span data-ttu-id="792a8-207">按一下 [**文件**，然後按一下 [ **Document.docx**檔案。</span><span class="sxs-lookup"><span data-stu-id="792a8-207">Click **Documents**, and then click the **Document.docx** file.</span></span>
    
5. <span data-ttu-id="792a8-p110">在瀏覽器中的 [ **Document.docx** ] 索引標籤中嘗試修改的文字。您應該會看到訊息表示**本文件是唯讀屬性。** 這被預期因為開發 VP 使用者帳戶只有網站檢視權限。</span><span class="sxs-lookup"><span data-stu-id="792a8-p110">In the **Document.docx** tab in your browser, try to modify the text. You should see a message stating **This document is read-only.** This is expected because the Development VP user account only has view permissions for the site.</span></span>
    
6. <span data-ttu-id="792a8-211">關閉 [在瀏覽器中的 [ **Document.docx**、 **ProjectX 文件**和**SharePoint** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="792a8-211">Close the **Document.docx**, **ProjectX-Documents**, and **SharePoint** tabs in your browser.</span></span>
    
7. <span data-ttu-id="792a8-212">按一下 [ **Microsoft Office Home** ] 索引標籤、 [**開發 VP**名稱和 [**登出**。</span><span class="sxs-lookup"><span data-stu-id="792a8-212">Click the **Microsoft Office Home** tab, click the **Development VP** name, and then click **Sign out**.</span></span>
    
<span data-ttu-id="792a8-213">現在我們示範沒有權限的使用者帳戶具有存取權：</span><span class="sxs-lookup"><span data-stu-id="792a8-213">Now let's demonstrate access with a user account that has no permissions:</span></span>
  
1. <span data-ttu-id="792a8-214">登入 Office 365 入口網站 ([https://portal.office.com](https://portal.office.com)) 使用的使用者 3 帳戶名稱和其密碼。</span><span class="sxs-lookup"><span data-stu-id="792a8-214">Sign in to the Office 365 portal ([https://portal.office.com](https://portal.office.com)) using the User 3 account name and its password.</span></span>
    
2. <span data-ttu-id="792a8-215">在磚清單中，按一下 [SharePoint]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="792a8-215">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="792a8-p111">[新增**SharePoint** ] 索引標籤在瀏覽器中的搜尋方塊中輸入**ProjectX**並再啟動搜尋。您應該會看到郵件**Nothing 以下符合您的搜尋。**</span><span class="sxs-lookup"><span data-stu-id="792a8-p111">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box and then activate the search. You should see the message **Nothing here matches your search.**</span></span>
    
4. <span data-ttu-id="792a8-p112">從 [記事本] 或文字編輯器開啟的執行個體，將 ProjectX 網站的 URL 複製到您的瀏覽器的位址列並按**Enter**。您應該會看到 **「 拒絕存取 」** 頁面。</span><span class="sxs-lookup"><span data-stu-id="792a8-p112">From the open instance of Notepad or your text editor, copy the URL for the ProjectX site into the address bar of your browser and press **Enter**. You should see an **Access Denied** page.</span></span>
    
5. <span data-ttu-id="792a8-p113">從 [記事本] 或文字編輯器，將 ProjectX 文件] 資料夾的 URL 複製到您的瀏覽器的位址列並按**Enter**。您應該會看到 **「 拒絕存取 」** 頁面。</span><span class="sxs-lookup"><span data-stu-id="792a8-p113">From Notepad or your text editor, copy the URL for the ProjectX Documents folder into the address bar of your browser and press **Enter**. You should see an **Access Denied** page.</span></span>
    
6. <span data-ttu-id="792a8-p114">從 [記事本] 或文字編輯器，將 Documents.docx 檔案的 URL 複製到您的瀏覽器的位址列並按**Enter**。您應該會看到 **「 拒絕存取 」** 頁面。</span><span class="sxs-lookup"><span data-stu-id="792a8-p114">From Notepad or your text editor, copy the URL for the Documents.docx file into the address bar of your browser and press **Enter**. You should see an **Access Denied** page.</span></span>
    
7. <span data-ttu-id="792a8-224">關閉瀏覽器中的 [ **SharePoint** ] 索引標籤、 [ **Microsoft Office Home** ] 索引標籤、 [**使用者 3**的名稱，和 [**登出**。</span><span class="sxs-lookup"><span data-stu-id="792a8-224">Close the **SharePoint** tab in your browser, click the **Microsoft Office Home** tab, click the **User 3** name, and then click **Sign out**.</span></span>
    
<span data-ttu-id="792a8-225">隔離的 SharePoint Online 網站現在已備妥可供您其他試驗。</span><span class="sxs-lookup"><span data-stu-id="792a8-225">Your isolated SharePoint Online site is now ready for your additional experimentation.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="792a8-226">下一步</span><span class="sxs-lookup"><span data-stu-id="792a8-226">Next Step</span></span>

<span data-ttu-id="792a8-227">當您準備好要在生產環境中部署獨立的 SharePoint Online 小組網站時，請參閱＜[設計獨立的 SharePoint Online 小組網站](design-an-isolated-sharepoint-online-team-site.md)＞中的逐步設計考量。</span><span class="sxs-lookup"><span data-stu-id="792a8-227">When you are ready to deploy an isolated SharePoint Online team site in production, see the step-by-step design considerations in [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="792a8-228">另請參閱</span><span class="sxs-lookup"><span data-stu-id="792a8-228">See Also</span></span>

<span data-ttu-id="792a8-229">[隔離的 SharePoint Online 小組網站](isolated-sharepoint-online-team-sites.md)。</span><span class="sxs-lookup"><span data-stu-id="792a8-229">[Isolated SharePoint Online team sites](isolated-sharepoint-online-team-sites.md)</span></span>
  
[<span data-ttu-id="792a8-230">雲端採用測試實驗室指南 (TLG)</span><span class="sxs-lookup"><span data-stu-id="792a8-230">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)
  
[<span data-ttu-id="792a8-231">基底組態開發/測試環境</span><span class="sxs-lookup"><span data-stu-id="792a8-231">Base Configuration dev/test environment</span></span>](https://docs.microsoft.com/office365/enterprise/base-configuration-dev-test-environment)
  
[<span data-ttu-id="792a8-232">Office 365 開發/測試環境</span><span class="sxs-lookup"><span data-stu-id="792a8-232">Office 365 dev/test environment</span></span>](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment)
  
[<span data-ttu-id="792a8-233">雲端採用和混合式解決方案</span><span class="sxs-lookup"><span data-stu-id="792a8-233">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)




