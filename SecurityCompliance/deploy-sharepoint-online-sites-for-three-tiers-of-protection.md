---
title: 部署三種保護層級的 SharePoint Online 網站
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 1e8e3cfd-b878-4088-b941-9940363a5fae
description: 摘要：建立及設定各種資訊保護等級的 SharePoint Online 小組網站。
ms.openlocfilehash: c39b1d85241c2d21c196e0c2c7f0d5c70149de5c
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220303"
---
# <a name="deploy-sharepoint-online-sites-for-three-tiers-of-protection"></a><span data-ttu-id="ebbc0-103">部署三種保護層級的 SharePoint Online 網站</span><span class="sxs-lookup"><span data-stu-id="ebbc0-103">Deploy SharePoint Online sites for three tiers of protection</span></span>

 <span data-ttu-id="ebbc0-104">**摘要：** 建立及設定各種資訊保護等級的 SharePoint Online 小組網站。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-104">**Summary:** Create and configure SharePoint Online team sites for various levels of information protection.</span></span>
  
<span data-ttu-id="ebbc0-p101">您可以使用本文中的步驟，來設計及部署基準、機密和高度機密 SharePoint Online 小組網站。 如需這三種保護層級的詳細資訊，請參閱[保護 SharePoint Online 網站與檔案](secure-sharepoint-online-sites-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-p101">Use the steps in this article to design and deploy baseline, sensitive, and highly confidential SharePoint Online team sites. For more information about these three tiers of protection, see [Secure SharePoint Online sites and files](secure-sharepoint-online-sites-and-files.md).</span></span>
  
## <a name="baseline-sharepoint-online-team-sites"></a><span data-ttu-id="ebbc0-107">基準 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="ebbc0-107">Baseline SharePoint Online team sites</span></span>

<span data-ttu-id="ebbc0-p102">基準保護包含公用和私人小組網站。 公用小組網站可供組織中的任何人探索及存取。 私人網站只能供與小組網站關聯的 Office 365 群組成員探索及存取。 這兩種小組網站類型都可讓成員與其他人共用網站。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-p102">Baseline protection includes both public and private team sites. Public team sites can be discovered and accessed by anybody in the organization. Private sites can only be discovered and accessed by members of the Office 365 group associated with the team site. Both of these types of team sites allow members to share the site with others.</span></span>
  
### <a name="public"></a><span data-ttu-id="ebbc0-112">公用</span><span class="sxs-lookup"><span data-stu-id="ebbc0-112">Public</span></span>

<span data-ttu-id="ebbc0-113">若要建立具有公用存取和權限的基準 SharePoint Online 小組網站，請執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="ebbc0-113">To create a baseline SharePoint Online team site with public access and permissions, do the following:</span></span>
  
1. <span data-ttu-id="ebbc0-p103">使用也可用來管理 SharePoint Online 小組網站的帳戶 (SharePoint Online 系統管理員) 登入 Office 365 入口網站。 如需說明，請參閱[在何處登入 Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-p103">Sign in to the Office 365 portal with an account that will also be used to administer the SharePoint Online team site (a SharePoint Online administrator). For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="ebbc0-116">在磚清單中，按一下 [SharePoint]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-116">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="ebbc0-117">在瀏覽器的新 [SharePoint]\*\*\*\* 索引標籤上，按一下 [+ 建立網站]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-117">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="ebbc0-118">在 [建立網站]\*\*\*\* 頁面上，按一下 [小組網站]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-118">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="ebbc0-119">在 [網站名稱]\*\*\*\* 中，鍵入公用小組網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-119">In **Site name**, type a name for the public team site.</span></span> 
    
6. <span data-ttu-id="ebbc0-120">在 [小組網站描述]\*\*\*\* 中，鍵入網站用途的描述。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-120">In **Team site description**, type a description of the purpose of the site.</span></span>
    
7. <span data-ttu-id="ebbc0-121">在 [隱私權設定]\*\*\*\* 中，選取 [公用 - 組織中的任何人都可以存取此網站]\*\*\*\*，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-121">In **Privacy settings**, select **Public - anyone in the organization can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="ebbc0-122">在 [您想要新增誰?]\*\*\*\* 窗格上，按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-122">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="ebbc0-123">以下是您產生的組態。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-123">Here is your resulting configuration.</span></span>
  
![適用於公用 SharePoint Online 小組網站的基準層級保護。](media/bcd46b8d-3f89-4398-80ce-4da17ee85e03.png)
  
### <a name="private"></a><span data-ttu-id="ebbc0-125">Private</span><span class="sxs-lookup"><span data-stu-id="ebbc0-125">Private</span></span>

<span data-ttu-id="ebbc0-126">若要建立具有私人存取和權限的基準 SharePoint Online 小組網站，請執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="ebbc0-126">To create a baseline SharePoint Online team site with private access and permissions, do the following:</span></span>
  
1. <span data-ttu-id="ebbc0-p104">使用也可用來管理 SharePoint Online 小組網站的帳戶 (SharePoint Online 系統管理員) 登入 Office 365 入口網站。 如需說明，請參閱[在何處登入 Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-p104">Sign in to the Office 365 portal with an account that will also be used to administer the SharePoint Online team site (a SharePoint Online administrator). For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="ebbc0-129">在磚清單中，按一下 [SharePoint]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-129">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="ebbc0-130">在瀏覽器的新 [SharePoint]\*\*\*\* 索引標籤上，按一下 [+ 建立網站]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-130">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="ebbc0-131">在 [建立網站]\*\*\*\* 頁面上，按一下 [小組網站]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-131">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="ebbc0-132">在 [網站名稱]\*\*\*\* 中，鍵入私人小組網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-132">In **Site name**, type a name for the private team site.</span></span> 
    
6. <span data-ttu-id="ebbc0-133">在 [小組網站描述]\*\*\*\* 中，鍵入網站用途的描述。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-133">In **Team site description,** type a description of the purpose of the site.</span></span>
    
7. <span data-ttu-id="ebbc0-134">在 [隱私權設定]\*\*\*\* 中，選取 [私人 - 只有成員可以存取此網站]\*\*\*\*，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-134">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="ebbc0-135">在 [您想要新增誰?]\*\*\*\* 窗格的 [新增成員]\*\*\*\* 中，鍵入有權存取此私人小組網站之使用者帳戶的名稱。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-135">On the **Who do you want to add?** pane, in **Add members**, type the names of user accounts that have access to this private team site.</span></span>
    
9. <span data-ttu-id="ebbc0-136">當您完成將初始成員集新增至網站之後，按一下 [完成] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-136">When you are done adding the initial set of members to the site, click **Finish**</span></span>
    
<span data-ttu-id="ebbc0-137">以下是您產生的組態。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-137">Here is your resulting configuration.</span></span>
  
![適用於私人 SharePoint Online 小組網站的基準層級保護。](media/91769026-37e3-4383-ac3c-dbf7aca98e41.png)
  
## <a name="sensitive-sharepoint-online-team-sites"></a><span data-ttu-id="ebbc0-139">機密 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="ebbc0-139">Sensitive SharePoint Online team sites</span></span>

<span data-ttu-id="ebbc0-140">機密 SharePoint Online 小組網站是隔離的小組網站，這表示權限是透過 SharePoint 群組成員資格來控制，而不是透過與小組網站關聯的 Office 365 群組成員資格來控制。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-140">A sensitive SharePoint Online team site is an isolated team site, which means that permissions are controlled through membership in SharePoint groups instead of membership in the Office 365 group associated with the team site.</span></span>
  
<span data-ttu-id="ebbc0-141">建立隔離的小組網站有兩個主要步驟。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-141">To create an isolated team site, there are two main steps.</span></span>
  
### <a name="step-1-design-your-isolated-site"></a><span data-ttu-id="ebbc0-142">步驟 1：設計隔離的網站</span><span class="sxs-lookup"><span data-stu-id="ebbc0-142">Step 1: Design your isolated site</span></span>

<span data-ttu-id="ebbc0-143">若要設計隔離的小組網站，您需要決定：</span><span class="sxs-lookup"><span data-stu-id="ebbc0-143">To design your isolated team site, you need to determine:</span></span>
  
- <span data-ttu-id="ebbc0-144">SharePoint 群組和權限等級。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-144">Your SharePoint groups and permission levels.</span></span>
    
- <span data-ttu-id="ebbc0-145">屬於 SharePoint 群組的一組存取群組。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-145">The set of access groups that will be members of your SharePoint groups.</span></span>
    
     <span data-ttu-id="ebbc0-146">這組建議的存取群組包含網站成員存取群組、網站檢視者存取群組及網站管理員存取群組。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-146">The recommended set of access groups is one for site members, one for site viewers, and one for site administrators.</span></span>
    
- <span data-ttu-id="ebbc0-147">是否要在存取群組中使用巢狀群組。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-147">Whether you will use nested groups within your access groups.</span></span>
    
<span data-ttu-id="ebbc0-148">例如，建議的群組結構和權限等級如下所示：</span><span class="sxs-lookup"><span data-stu-id="ebbc0-148">For example, the recommended group structure and permission levels look like this:</span></span>
  
|<span data-ttu-id="ebbc0-149">**SharePoint 群組**</span><span class="sxs-lookup"><span data-stu-id="ebbc0-149">**SharePoint group**</span></span>|<span data-ttu-id="ebbc0-150">**權限等級**</span><span class="sxs-lookup"><span data-stu-id="ebbc0-150">**Permission level**</span></span>|<span data-ttu-id="ebbc0-151">**存取群組 (範例)**</span><span class="sxs-lookup"><span data-stu-id="ebbc0-151">**Access group (examples)**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ebbc0-152">[網站名稱] 成員</span><span class="sxs-lookup"><span data-stu-id="ebbc0-152">[site name] Members</span></span>  <br/> |<span data-ttu-id="ebbc0-153">編輯</span><span class="sxs-lookup"><span data-stu-id="ebbc0-153">Edit</span></span>  <br/> |<span data-ttu-id="ebbc0-154">[網站名稱] 成員</span><span class="sxs-lookup"><span data-stu-id="ebbc0-154">[site name] Members</span></span>  <br/> |
|<span data-ttu-id="ebbc0-155">[網站名稱] 訪客</span><span class="sxs-lookup"><span data-stu-id="ebbc0-155">[site name] Visitors</span></span>  <br/> |<span data-ttu-id="ebbc0-156">讀取</span><span class="sxs-lookup"><span data-stu-id="ebbc0-156">Read</span></span>  <br/> |<span data-ttu-id="ebbc0-157">[網站名稱] 檢視者</span><span class="sxs-lookup"><span data-stu-id="ebbc0-157">[site name] Viewers</span></span>  <br/> |
|<span data-ttu-id="ebbc0-158">[網站名稱] 擁有者</span><span class="sxs-lookup"><span data-stu-id="ebbc0-158">[site name] Owners</span></span>  <br/> |<span data-ttu-id="ebbc0-159">完全控制</span><span class="sxs-lookup"><span data-stu-id="ebbc0-159">Full control</span></span>  <br/> |<span data-ttu-id="ebbc0-160">[網站名稱] 管理員</span><span class="sxs-lookup"><span data-stu-id="ebbc0-160">[site name] Admins</span></span>  <br/> |
   
<span data-ttu-id="ebbc0-p105">預設會為小組網站建立 SharePoint 群組和權限等級。 您需要決定存取群組的名稱。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-p105">The SharePoint groups and permission levels are created by default for a team site. You need to determine the names of your access groups.</span></span>
  
<span data-ttu-id="ebbc0-163">如需設計程序的詳細資訊，請參閱 [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md) (設計隔離的 SharePoint Online 小組網站)。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-163">For the details of the design process, see [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>
  
### <a name="step-2-deploy-your-isolated-site"></a><span data-ttu-id="ebbc0-164">步驟 2：部署隔離的網站</span><span class="sxs-lookup"><span data-stu-id="ebbc0-164">Step 2: Deploy your isolated site</span></span>

<span data-ttu-id="ebbc0-165">若要部署隔離的網站，您必須先：</span><span class="sxs-lookup"><span data-stu-id="ebbc0-165">To deploy your isolated site, you first need to:</span></span>
  
- <span data-ttu-id="ebbc0-166">決定要新增至每個存取群組的使用者帳戶和群組。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-166">Determine the user accounts and groups to add to each of your access groups.</span></span>
    
- <span data-ttu-id="ebbc0-167">建立存取群組並新增使用者和群組成員。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-167">Create the access groups and add the user and group members.</span></span>
    
<span data-ttu-id="ebbc0-168">如需詳細步驟，請參閱[部署隔離的 SharePoint Online 小組網站](deploy-an-isolated-sharepoint-online-team-site.md)的**階段 1**。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-168">For the detailed steps, see **Phase 1** of [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).</span></span>
  
<span data-ttu-id="ebbc0-169">接下來，使用下列步驟建立 SharePoint Online 小組網站。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-169">Next, you create the SharePoint Online team site with these steps.</span></span>
  
1. <span data-ttu-id="ebbc0-p106">使用也可用來管理 SharePoint Online 小組網站的帳戶 (SharePoint Online 系統管理員) 登入 Office 365 入口網站。 如需說明，請參閱[在何處登入 Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-p106">Sign in to the Office 365 portal with an account that will also be used to administer the SharePoint Online team site (a SharePoint Online administrator). For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="ebbc0-172">在磚清單中，按一下 [SharePoint]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-172">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="ebbc0-173">在新的 [SharePoint] \*\*\*\* 瀏覽器索引標籤中，按一下 [+ 建立網站]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-173">In the new **SharePoint** tab of your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="ebbc0-174">在 [建立網站]\*\*\*\* 頁面上，按一下 [小組網站]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-174">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="ebbc0-175">在 [網站名稱]\*\*\*\* 中，鍵入私人小組網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-175">In **Site name**, type a name for the private team site.</span></span>
    
6. <span data-ttu-id="ebbc0-176">在 [小組網站描述]\*\*\*\* 中，鍵入選擇性描述。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-176">In **Team site description**, type an optional description.</span></span>
    
7. <span data-ttu-id="ebbc0-177">在 [隱私權設定]\*\*\*\* 中，選取 [私人 - 只有成員可以存取此網站]\*\*\*\*，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-177">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="ebbc0-178">在 [您想要新增誰?]\*\*\*\* 窗格上，按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-178">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="ebbc0-179">接下來，從新的 SharePoint Online 小組網站，使用下列步驟設定權限。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-179">Next, from the new SharePoint Online team site, configure permissions with these steps.</span></span>
  
1. <span data-ttu-id="ebbc0-p107">決定 IT 系統管理員或將負責回應網站及向網站提出存取要求之其他人員的使用者主體名稱 (UPN) (belindan@contoso.com 為 UPN 範例)。在此寫下該 UPN：![](./media/Common-Images/TableLine.png)。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-p107">Determine the User Principal Name (UPN) of the IT administrator or other person who will be responsible for responding to and addressing requests for access to the site (belindan@contoso.com is an example of a UPN). Write that UPN here: ![](./media/Common-Images/TableLine.png).</span></span>
    
2. <span data-ttu-id="ebbc0-182">在工具列中，按一下設定圖示，然後按一下 [網站權限]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-182">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
    
3. <span data-ttu-id="ebbc0-183">在 [網站權限]\*\*\*\* 窗格中，按一下 [進階權限設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-183">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
    
4. <span data-ttu-id="ebbc0-184">在新的 [權限]\*\*\*\* 瀏覽器索引標籤中，按一下 [存取要求設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-184">On the new **Permissions** tab of your browser, click **Access Request Settings**.</span></span>
    
5. <span data-ttu-id="ebbc0-185">在 [存取要求設定]\*\*\*\* 對話方塊中：</span><span class="sxs-lookup"><span data-stu-id="ebbc0-185">In the **Access Requests Settings** dialog box:</span></span>
    
  - <span data-ttu-id="ebbc0-186">清除 [允許成員共用網站以及個別檔案和資料夾]\*\*\*\* 和 [允許成員邀請其他人加入網站成員群組]\*\*\*\* 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-186">Clear the **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** check boxes.</span></span>
    
  - <span data-ttu-id="ebbc0-187">在 [傳送存取下列電子郵件地址的所有要求]\*\*\*\* 中，鍵入步驟 1 中的 IT 系統管理員 UPN。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-187">Type the UPN of your IT administrator from step 1 in **Send all requests for access**.</span></span>
    
  - <span data-ttu-id="ebbc0-188">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-188">Click **OK**.</span></span>
    
6. <span data-ttu-id="ebbc0-189">在 [權限]\*\*\*\* 瀏覽器索引標籤中，按一下清單中的 [[網站名稱] 成員]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-189">On the **Permissions** tab of your browser, click **[site name] Members** in the list.</span></span>
    
7. <span data-ttu-id="ebbc0-190">在 [人員與群組]\*\*\*\* 中，按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-190">In **People and Groups**, click **New**.</span></span>
    
8. <span data-ttu-id="ebbc0-191">在 [共用]\*\*\*\* 對話方塊中，鍵入此網站的網站成員存取群組名稱並加以選取，然後按一下 [共用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-191">In the **Share** dialog box, type the name of your site members access group for this site, select it, and then click **Share**.</span></span>
    
9. <span data-ttu-id="ebbc0-192">按一下瀏覽器上的 [上一頁] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-192">Click the back button on your browser.</span></span>
    
10. <span data-ttu-id="ebbc0-193">按一下清單中 [[網站名稱] 擁有者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-193">Click **[site name] Owners** in the list.</span></span>
    
11. <span data-ttu-id="ebbc0-194">在 [人員與群組]\*\*\*\* 中，按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-194">In **People and Groups**, click **New**.</span></span>
    
12. <span data-ttu-id="ebbc0-195">在 [共用]\*\*\*\* 對話方塊中，鍵入此網站的網站管理員存取群組名稱並加以選取，然後按一下 [共用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-195">In the **Share** dialog box, type the name of the site administrators access group for this site, select it, and then click **Share**.</span></span>
    
13. <span data-ttu-id="ebbc0-196">按一下瀏覽器上的 [上一頁] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-196">Click the back button on your browser.</span></span>
    
14. <span data-ttu-id="ebbc0-197">按一下清單中 [[網站名稱] 訪客]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-197">Click **[site name] Visitors** in the list.</span></span>
    
15. <span data-ttu-id="ebbc0-198">在 [人員與群組]\*\*\*\* 中，按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-198">In **People and Groups**, click **New**.</span></span>
    
16. <span data-ttu-id="ebbc0-199">在 [共用]\*\*\*\* 對話方塊中，鍵入此網站的網站檢視者存取群組名稱並加以選取，然後按一下 [共用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-199">In the **Share** dialog box, type the name of the site viewers access group for this site, select it, and then click **Share**.</span></span>
    
17. <span data-ttu-id="ebbc0-200">關閉 [權限]\*\*\*\* 瀏覽器索引標籤。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-200">Close the **Permissions** tab of your browser.</span></span>
    
<span data-ttu-id="ebbc0-201">這些權限設定的結果是：</span><span class="sxs-lookup"><span data-stu-id="ebbc0-201">The results of these permission settings are:</span></span>
  
- <span data-ttu-id="ebbc0-202">[[網站名稱] 擁有者]\*\*\*\* SharePoint 群組包含網站管理員存取群組，其中的所有成員都具有 [完全控制]\*\*\*\* 權限等級。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-202">The **[site name] Owners** SharePoint group contains the site administrators access group, in which all the members have the **Full control** permission level.</span></span>
    
- <span data-ttu-id="ebbc0-203">[[網站名稱] 成員]\*\*\*\* SharePoint 群組包含網站成員存取群組，其中的所有成員都具有 [編輯]\*\*\*\* 權限等級。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-203">The **[site name] Members** SharePoint group contains the site members access group, in which all the members have the **Edit** permission level.</span></span>
    
- <span data-ttu-id="ebbc0-204">[[網站名稱] 訪客]\*\*\*\* SharePoint 群組包含網站檢視者存取群組，其中的所有成員都具有 [讀取]\*\*\*\* 權限等級。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-204">The **[site name] Visitors** SharePoint group contains the site viewers access group, in which all the members have the **Read** permission level.</span></span>
    
- <span data-ttu-id="ebbc0-205">成員邀請其他成員的功能已停用。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-205">The ability for members to invite other members is disabled.</span></span>
    
- <span data-ttu-id="ebbc0-206">非成員要求存取的功能已啟用。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-206">The ability for non-members to request access is enabled.</span></span>
    
<span data-ttu-id="ebbc0-207">以下是您產生的組態。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-207">Here is your resulting configuration.</span></span>
  
![適用於隔離 SharePoint Online 小組網站的敏感性層級保護。](media/7a6ab9c6-560a-4674-ac39-8175644dbe6f.png)
  
<span data-ttu-id="ebbc0-209">網站成員現在可以透過其中一個存取群組的群組成員資格，安全地在網站的資源上共同作業。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-209">The members of the site, through group membership in one of the access groups, can now securely collaborate on the resources of the site.</span></span>
  
## <a name="highly-confidential-sharepoint-online-team-sites"></a><span data-ttu-id="ebbc0-210">高度機密 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="ebbc0-210">Highly confidential SharePoint Online team sites</span></span>

<span data-ttu-id="ebbc0-211">高度機密 SharePoint Online 小組網站是隔離的小組網站，這表示權限是透過 SharePoint 群組成員資格來控制，而不是透過與小組網站關聯的 Office 365 群組成員資格來控制。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-211">A highly confidential SharePoint Online team site is an isolated team site, which means that permissions are controlled through membership in SharePoint groups instead of membership in the Office 365 group associated with the team site.</span></span>
  
<span data-ttu-id="ebbc0-212">若要建立適用於高度機密資訊和共同作業的隔離小組網站，有兩個主要步驟。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-212">To create an isolated team site for highly confidential information and collaboration, there are two main steps.</span></span>
  
### <a name="step-1-design-your-isolated-site"></a><span data-ttu-id="ebbc0-213">步驟 1：設計隔離的網站</span><span class="sxs-lookup"><span data-stu-id="ebbc0-213">Step 1: Design your isolated site</span></span>

<span data-ttu-id="ebbc0-214">若要設計隔離的小組網站，您需要決定：</span><span class="sxs-lookup"><span data-stu-id="ebbc0-214">To design your isolated team site, you need to determine:</span></span>
  
- <span data-ttu-id="ebbc0-215">SharePoint 群組和權限等級。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-215">Your SharePoint groups and permission levels.</span></span>
    
- <span data-ttu-id="ebbc0-216">屬於 SharePoint 群組的一組存取群組。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-216">The set of access groups that will be members of your SharePoint groups.</span></span>
    
     <span data-ttu-id="ebbc0-217">這組建議的存取群組包含網站成員存取群組、網站檢視者存取群組及網站管理員存取群組。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-217">The recommended set of access groups is one for site members, one for site viewers, and one for site administrators.</span></span>
    
- <span data-ttu-id="ebbc0-218">是否要在存取群組中使用巢狀群組。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-218">Whether you will use nested groups within your access groups.</span></span>
    
<span data-ttu-id="ebbc0-219">例如，建議的群組結構和權限等級如下所示：</span><span class="sxs-lookup"><span data-stu-id="ebbc0-219">For example, the recommended group structure and permission levels look like this:</span></span>
  
|<span data-ttu-id="ebbc0-220">**SharePoint 群組**</span><span class="sxs-lookup"><span data-stu-id="ebbc0-220">**SharePoint group**</span></span>|<span data-ttu-id="ebbc0-221">**權限等級**</span><span class="sxs-lookup"><span data-stu-id="ebbc0-221">**Permission level**</span></span>|<span data-ttu-id="ebbc0-222">**存取群組 (範例)**</span><span class="sxs-lookup"><span data-stu-id="ebbc0-222">**Access group (examples)**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ebbc0-223">[網站名稱] 成員</span><span class="sxs-lookup"><span data-stu-id="ebbc0-223">[site name] Members</span></span>  <br/> |<span data-ttu-id="ebbc0-224">編輯</span><span class="sxs-lookup"><span data-stu-id="ebbc0-224">Edit</span></span>  <br/> |<span data-ttu-id="ebbc0-225">[網站名稱] 成員</span><span class="sxs-lookup"><span data-stu-id="ebbc0-225">[site name] Members</span></span>  <br/> |
|<span data-ttu-id="ebbc0-226">[網站名稱] 訪客</span><span class="sxs-lookup"><span data-stu-id="ebbc0-226">[site name] Visitors</span></span>  <br/> |<span data-ttu-id="ebbc0-227">讀取</span><span class="sxs-lookup"><span data-stu-id="ebbc0-227">Read</span></span>  <br/> |<span data-ttu-id="ebbc0-228">[網站名稱] 檢視者</span><span class="sxs-lookup"><span data-stu-id="ebbc0-228">[site name] Viewers</span></span>  <br/> |
|<span data-ttu-id="ebbc0-229">[網站名稱] 擁有者</span><span class="sxs-lookup"><span data-stu-id="ebbc0-229">[site name] Owners</span></span>  <br/> |<span data-ttu-id="ebbc0-230">完全控制</span><span class="sxs-lookup"><span data-stu-id="ebbc0-230">Full control</span></span>  <br/> |<span data-ttu-id="ebbc0-231">[網站名稱] 管理員</span><span class="sxs-lookup"><span data-stu-id="ebbc0-231">[site name] Admins</span></span>  <br/> |
   
<span data-ttu-id="ebbc0-p108">預設會為小組網站建立 SharePoint 群組和權限等級。 您需要決定存取群組的名稱。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-p108">The SharePoint groups and permission levels are created by default for a team site. You need to determine the names of your access groups.</span></span>
  
<span data-ttu-id="ebbc0-234">如需設計程序的詳細資訊，請參閱 [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md) (設計隔離的 SharePoint Online 小組網站)。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-234">For the details of the design process, see [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>
  
### <a name="step-2-deploy-your-isolated-site"></a><span data-ttu-id="ebbc0-235">步驟 2：部署隔離的網站</span><span class="sxs-lookup"><span data-stu-id="ebbc0-235">Step 2: Deploy your isolated site</span></span>

<span data-ttu-id="ebbc0-236">若要部署隔離的網站，您必須先：</span><span class="sxs-lookup"><span data-stu-id="ebbc0-236">To deploy your isolated site, you first need to:</span></span>
  
- <span data-ttu-id="ebbc0-237">決定每個存取群組的使用者和群組成員</span><span class="sxs-lookup"><span data-stu-id="ebbc0-237">Determine the user and group members of each of your access groups</span></span>
    
- <span data-ttu-id="ebbc0-238">建立存取群組並新增使用者和群組成員</span><span class="sxs-lookup"><span data-stu-id="ebbc0-238">Create the access groups and add the user and group members</span></span>
    
- <span data-ttu-id="ebbc0-239">建立使用存取群組的隔離小組網站。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-239">Create an isolated team site that uses your access groups</span></span>
    
<span data-ttu-id="ebbc0-240">如需詳細步驟，請參閱[部署隔離的 SharePoint Online 小組網站](deploy-an-isolated-sharepoint-online-team-site.md)。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-240">For the detailed steps, see [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).</span></span>
  
<span data-ttu-id="ebbc0-241">權限設定的結果是：</span><span class="sxs-lookup"><span data-stu-id="ebbc0-241">The results of the permission settings are:</span></span>
  
- <span data-ttu-id="ebbc0-242">[[網站名稱] 擁有者]\*\*\*\* SharePoint 群組包含網站管理員存取群組，其中的所有成員都具有 [完全控制]\*\*\*\* 權限等級。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-242">The **[site name] Owners** SharePoint group contains the site administrators access group, in which all the members have the **Full control** permission level.</span></span>
    
- <span data-ttu-id="ebbc0-243">[[網站名稱] 成員]\*\*\*\* SharePoint 群組包含網站成員存取群組，其中的所有成員都具有 [編輯]\*\*\*\* 權限等級。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-243">The **[site name] Members** SharePoint group contains the site members access group, in which all the members have the **Edit** permission level.</span></span>
    
- <span data-ttu-id="ebbc0-244">[[網站名稱] 訪客]\*\*\*\* SharePoint 群組包含網站檢視者存取群組，其中的所有成員都具有 [讀取]\*\*\*\* 權限等級。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-244">The **[site name] Visitors** SharePoint group contains the site viewers access group, in which all the members have the **Read** permission level.</span></span>
    
- <span data-ttu-id="ebbc0-245">成員邀請其他成員的功能已停用。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-245">The ability for members to invite other members is disabled.</span></span>
    
- <span data-ttu-id="ebbc0-246">非成員要求存取的功能已停用。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-246">The ability for non-members to request access is disabled.</span></span>
    
<span data-ttu-id="ebbc0-247">以下是您產生的組態。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-247">Here is your resulting configuration.</span></span>
  
![適用於隔離 SharePoint Online 小組網站的高度機密層級保護。](media/196359ab-d7ed-4fcf-97b4-61820a74aca4.png)
  
<span data-ttu-id="ebbc0-249">網站成員現在可以透過其中一個存取群組的群組成員資格，安全地在網站的資源上共同作業。</span><span class="sxs-lookup"><span data-stu-id="ebbc0-249">The members of the site, through group membership in one of the access groups, can now securely collaborate on the resources of the site.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="ebbc0-250">下一步</span><span class="sxs-lookup"><span data-stu-id="ebbc0-250">Next step</span></span>

[<span data-ttu-id="ebbc0-251">使用 Azure 資訊保護來保護 SharePoint Online 檔案</span><span class="sxs-lookup"><span data-stu-id="ebbc0-251">Protect SharePoint Online files with Azure Information Protection</span></span>](protect-sharepoint-online-files-with-azure-information-protection.md)


## <a name="see-also"></a><span data-ttu-id="ebbc0-252">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ebbc0-252">See also</span></span>

[<span data-ttu-id="ebbc0-253">保護 SharePoint Online 網站與檔案</span><span class="sxs-lookup"><span data-stu-id="ebbc0-253">Secure SharePoint Online sites and files</span></span>](secure-sharepoint-online-sites-and-files.md)
  
[<span data-ttu-id="ebbc0-254">適用於政治活動、非營利組織和其他彈性組織的 Microsoft 安全性指南</span><span class="sxs-lookup"><span data-stu-id="ebbc0-254">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="ebbc0-255">雲端採用和混合式解決方案</span><span class="sxs-lookup"><span data-stu-id="ebbc0-255">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)




