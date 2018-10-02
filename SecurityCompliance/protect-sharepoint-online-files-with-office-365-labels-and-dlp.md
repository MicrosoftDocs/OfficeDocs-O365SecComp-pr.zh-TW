---
title: 使用 Office 365 標籤與 DLP 來保護 SharePoint Online 檔案
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: c9f837af-8d71-4df1-a285-dedb1c5618b3
description: 摘要：使用各種資訊保護層級，對 SharePoint Online 小組網站套用 Office 365 標籤和資料外洩防護 (DLP) 原則。
ms.openlocfilehash: f8d835481c0eac00be11f7934c1d74b8a2d08d78
ms.sourcegitcommit: e0f016aca7befc8806233a492ee916cbe646094f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/27/2018
ms.locfileid: "25345965"
---
# <a name="protect-sharepoint-online-files-with-office-365-labels-and-dlp"></a><span data-ttu-id="2c53c-103">使用 Office 365 標籤與 DLP 來保護 SharePoint Online 檔案</span><span class="sxs-lookup"><span data-stu-id="2c53c-103">Protect SharePoint Online files with Office 365 labels and DLP</span></span>

 <span data-ttu-id="2c53c-104">**摘要：** 使用各種資訊保護層級，對 SharePoint Online 小組網站套用 Office 365 標籤和資料外洩防護 (DLP) 原則。</span><span class="sxs-lookup"><span data-stu-id="2c53c-104">**Summary:** Apply Office 365 labels and data loss prevention (DLP) policies for SharePoint Online team sites with various levels of information protection.</span></span>
  
<span data-ttu-id="2c53c-p101">您可以使用本文中的步驟，為基準、機密和高度機密 SharePoint Online 小組網站設計及部署 Office 365 標籤和資料外洩防護 (DLP) 原則。如需這三種保護層級的詳細資訊，請參閱[保護 SharePoint Online 網站與檔案](secure-sharepoint-online-sites-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="2c53c-p101">Use the steps in this article to design and deploy Office 365 labels and DLP policies for baseline, sensitive, and highly confidential SharePoint Online team sites. For more information about these three tiers of protection, see [Secure SharePoint Online sites and files](secure-sharepoint-online-sites-and-files.md).</span></span>
  
## <a name="how-this-works"></a><span data-ttu-id="2c53c-107">如何進行此作業</span><span class="sxs-lookup"><span data-stu-id="2c53c-107">How this works</span></span>
1. <span data-ttu-id="2c53c-p102">建立所需標籤並加以發行。發行這些標籤可能長達 12 小時的時間。</span><span class="sxs-lookup"><span data-stu-id="2c53c-p102">Create the desired labels and publish these. It can take up to 12 hours for these to be published.</span></span>
2. <span data-ttu-id="2c53c-110">針對所需的 SharePoint 網站，請編輯文件庫設定，將標籤套用至文件庫中的項目。</span><span class="sxs-lookup"><span data-stu-id="2c53c-110">For the desired SharePoint sites, edit the document library settings to apply a label to items in the library.</span></span>
3. <span data-ttu-id="2c53c-111">建立 DLP 原則，以根據標籤採取行動。</span><span class="sxs-lookup"><span data-stu-id="2c53c-111">Create DLP policies to take action based on the labels.</span></span>

<span data-ttu-id="2c53c-p103">當使用者將文件新增至文件庫時，文件依預設會接收指派的標籤。使用者可以視需要變更標籤。當使用者在組織外部共用文件時，DLP 會檢查是否已指派標籤，且如果 DLP 原則符合標籤則採取行動。DLP 也會尋找其他原則相符項目，例如若設定這類原則，則使用信用卡號碼來保護檔案。</span><span class="sxs-lookup"><span data-stu-id="2c53c-p103">When users add a document to the library, the document will receive the assigned label by default. Users can change the label,if needed. When a user shares a document outside the organization, DLP will check to see if a label is assigned and take action if a DLP policy matches the label. DLP will look for other policy matches as well, such as protecting files with credit card numbers if this type of policy is configured.</span></span> 

## <a name="office-365-labels-for-your-sharepoint-online-sites"></a><span data-ttu-id="2c53c-116">適用於 SharePoint Online 網站的 Office 365 標籤</span><span class="sxs-lookup"><span data-stu-id="2c53c-116">Office 365 labels for your SharePoint Online sites</span></span>

<span data-ttu-id="2c53c-117">建立 Office 365 標籤並將其指派給 SharePoint Online 小組網站時的三個階段。</span><span class="sxs-lookup"><span data-stu-id="2c53c-117">There are three phases to creating and then assigning Office 365 labels to SharePoint Online team sites.</span></span>
  
### <a name="phase-1-determine-the-office-365-label-names"></a><span data-ttu-id="2c53c-118">階段 1：決定 Office 365 標籤名稱</span><span class="sxs-lookup"><span data-stu-id="2c53c-118">Phase 1: Determine the Office 365 label names</span></span>

<span data-ttu-id="2c53c-p104">在此階段中，您會為套用至 SharePoint Online 小組網站的四種資訊保護層級，決定其 Office 365 標籤的名稱。 下表列出每種層級的建議名稱。</span><span class="sxs-lookup"><span data-stu-id="2c53c-p104">In this phase, you determine the names of your Office 365 labels for the four levels of information protection applied to SharePoint Online team sites. The following table lists the recommended names for each level.</span></span>
  
|<span data-ttu-id="2c53c-121">**SharePoint Online 小組網站保護層級**</span><span class="sxs-lookup"><span data-stu-id="2c53c-121">**SharePoint Online team site protection level**</span></span>|<span data-ttu-id="2c53c-122">**標籤名稱**</span><span class="sxs-lookup"><span data-stu-id="2c53c-122">**Label name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2c53c-123">基準-公用</span><span class="sxs-lookup"><span data-stu-id="2c53c-123">Baseline-Public</span></span>  <br/> |<span data-ttu-id="2c53c-124">內部公用</span><span class="sxs-lookup"><span data-stu-id="2c53c-124">Internal public</span></span>  <br/> |
|<span data-ttu-id="2c53c-125">基準-私人</span><span class="sxs-lookup"><span data-stu-id="2c53c-125">Baseline-Private</span></span>  <br/> |<span data-ttu-id="2c53c-126">Private</span><span class="sxs-lookup"><span data-stu-id="2c53c-126">Private</span></span>  <br/> |
|<span data-ttu-id="2c53c-127">敏感性</span><span class="sxs-lookup"><span data-stu-id="2c53c-127">Sensitive</span></span>  <br/> |<span data-ttu-id="2c53c-128">敏感性</span><span class="sxs-lookup"><span data-stu-id="2c53c-128">Sensitive</span></span>  <br/> |
|<span data-ttu-id="2c53c-129">高度機密</span><span class="sxs-lookup"><span data-stu-id="2c53c-129">Highly Confidential</span></span>  <br/> |<span data-ttu-id="2c53c-130">高度機密</span><span class="sxs-lookup"><span data-stu-id="2c53c-130">Highly Confidential</span></span>  <br/> |
   
### <a name="phase-2-create-the-office-365-labels"></a><span data-ttu-id="2c53c-131">階段 2：建立 Office 365 標籤</span><span class="sxs-lookup"><span data-stu-id="2c53c-131">Phase 2: Create the Office 365 labels</span></span>

<span data-ttu-id="2c53c-132">在此階段中，您會為不同資訊保護層級建立所決定的標籤，然後將它發佈。</span><span class="sxs-lookup"><span data-stu-id="2c53c-132">In this phase, you create and then publish your determined labels for the different levels of information protection.</span></span>
  
<span data-ttu-id="2c53c-133">若要建立標籤，您可以使用 Office 365 系統管理中心或 Microsoft PowerShell。</span><span class="sxs-lookup"><span data-stu-id="2c53c-133">To create the labels, you can use the Office 365 Admin center or Microsoft PowerShell.</span></span>
  
### <a name="create-office-365-labels-with-the-office-365-admin-center"></a><span data-ttu-id="2c53c-134">使用 Office 365 系統管理中心建立 Office 365 標籤</span><span class="sxs-lookup"><span data-stu-id="2c53c-134">Create Office 365 labels with the Office 365 Admin center</span></span>

1. <span data-ttu-id="2c53c-p105">使用具有安全性系統管理員或公司系統管理員角色的帳戶登入 Office 365 入口網站。 如需說明，請參閱[在何處登入 Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="2c53c-p105">Sign in to the Office 365 portal with an account that has the Security Administrator or Company Administrator role. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="2c53c-137">從 [Microsoft Office 的首頁]\*\*\*\* 索引標籤中，按一下 [管理]\*\*\*\* 磚。</span><span class="sxs-lookup"><span data-stu-id="2c53c-137">From the **Microsoft Office Home** tab, click the **Admin** tile.</span></span>
    
3. <span data-ttu-id="2c53c-138">從瀏覽器的新 [Office 系統管理中心]\*\*\*\* 索引標籤中，按一下 [系統管理中心] > [安全性 &amp; 合規性]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-138">From the new **Office Admin center** tab of your browser, click **Admin centers > Security &amp; Compliance**.</span></span>
    
4. <span data-ttu-id="2c53c-139">從瀏覽器的新 [首頁 - 安全性 &amp; 合規性]\*\*\*\* 索引標籤中，按一下 [分類] > [標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-139">From the new **Home - Security &amp; Compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
5. <span data-ttu-id="2c53c-140">從 [首頁] > [標籤]\*\*\*\* 窗格中，按一下 [建立標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-140">From the **Home > Labels** pane, click **Create a label**.</span></span>
    
6. <span data-ttu-id="2c53c-141">在 [命名您的標籤]\*\*\*\* 窗格中，鍵入標籤的名稱，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-141">On the **Name your label** pane, type the name of the label, and then click **Next**.</span></span>
    
7. <span data-ttu-id="2c53c-142">在 [標籤設定]\*\*\*\* 窗格中，按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-142">On the **Label settings** pane, click **Next**.</span></span>
    
8. <span data-ttu-id="2c53c-143">在 [檢閱您的設定]\*\*\*\* 窗格中，按一下 [建立此標籤]\*\*\*\*，然後按一下 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-143">On the **Review your settings** pane, click **Create this label**, and then click **Close**.</span></span>
    
9. <span data-ttu-id="2c53c-144">針對其他標籤重複步驟 5 至 8。</span><span class="sxs-lookup"><span data-stu-id="2c53c-144">Repeat steps 5-8 for your additional labels.</span></span>
    
### <a name="create-office-365-labels-with-powershell"></a><span data-ttu-id="2c53c-145">使用 PowerShell 建立 Office 365 標籤</span><span class="sxs-lookup"><span data-stu-id="2c53c-145">Create Office 365 labels with PowerShell</span></span>

1. <span data-ttu-id="2c53c-146">[使用遠端 PowerShell 連線到 Office 365 安全 &amp;規範中心，](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)並指定具有安全性系統管理員或公司系統管理員角色之帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="2c53c-146">[Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409) and specify the credentials of an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="2c53c-147">填寫標籤名稱清單，然後在 PowerShell 命令提示字元中執行這些命令：</span><span class="sxs-lookup"><span data-stu-id="2c53c-147">Fill out the list of label names, and then run these commands at the PowerShell command prompt:</span></span>
    
  ```
  $labelNames=@(<list of label names, each enclosed in quotes and separated by commas>)
ForEach ($element in $labelNames){ New-ComplianceTag -Name $element }
  ```

<span data-ttu-id="2c53c-148">接下來，使用下列步驟來發佈新的 Office 365 標籤。</span><span class="sxs-lookup"><span data-stu-id="2c53c-148">Next, use these steps to publish the new Office 365 labels.</span></span>
  
1. <span data-ttu-id="2c53c-149">從安全性 &amp; 合規性的 [首頁] > [標籤]\*\*\*\* 窗格中，按一下 [發佈標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-149">From the **Home > Labels** pane the Security &amp; Compliance Center, click **Publish labels**.</span></span>
    
2. <span data-ttu-id="2c53c-150">在 [選擇要發佈的標籤]\*\*\*\* 窗格中，按一下 [選擇要發佈的標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-150">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
3. <span data-ttu-id="2c53c-151">在 [Choose labels]\(選擇標籤)\*\*\*\* 窗格中，按一下 [新增]\*\*\*\* 並選取所有四個標籤。</span><span class="sxs-lookup"><span data-stu-id="2c53c-151">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
4. <span data-ttu-id="2c53c-152">按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-152">Click **Done**.</span></span>
    
5. <span data-ttu-id="2c53c-153">在 [選擇要發佈的標籤]\*\*\*\* 窗格上，按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-153">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="2c53c-154">在 [選擇位置]\*\*\*\* 窗格中，按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-154">On the **Choose locations** pane, click **Next**.</span></span>
    
7. <span data-ttu-id="2c53c-155">在 [命名您的原則]\*\*\*\* 窗格的 [名稱]\*\*\*\* 中，鍵入標籤集的名稱，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-155">On the **Name your policy** pane, type a name for your set of labels in **Name**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="2c53c-156">在 [檢閱您的設定]\*\*\*\* 窗格中，按一下 [發佈標籤]\*\*\*\*，然後按一下 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-156">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>
    
### <a name="phase-3-apply-the-office-365-labels-to-your-sharepoint-online-sites"></a><span data-ttu-id="2c53c-157">階段 3：將 Office 365 標籤套用至 SharePoint Online 網站</span><span class="sxs-lookup"><span data-stu-id="2c53c-157">Phase 3: Apply the Office 365 labels to your SharePoint Online sites</span></span>

<span data-ttu-id="2c53c-158">使用下列步驟，將 Office 365 標籤套用至 SharePoint Online 小組網站的文件資料夾。</span><span class="sxs-lookup"><span data-stu-id="2c53c-158">Use these steps to apply the Office 365 labels to the documents folders of your SharePoint Online team sites.</span></span>
  
1. <span data-ttu-id="2c53c-159">從 [Microsoft Office 的首頁]\*\*\*\* 瀏覽器索引標籤，按一下 [SharePoint]\*\*\*\* 磚。</span><span class="sxs-lookup"><span data-stu-id="2c53c-159">From the **Microsoft Office Home** tab of your browser, click the **SharePoint** tile.</span></span>
    
2. <span data-ttu-id="2c53c-160">在新的 [SharePoint]\*\*\*\* 瀏覽器索引標籤中，按一下需要指派 Office 365 標籤的網站。</span><span class="sxs-lookup"><span data-stu-id="2c53c-160">On the new **SharePoint** tab in your browser, click a site that needs an Office 365 label assigned.</span></span>
    
3. <span data-ttu-id="2c53c-161">在瀏覽器的新 [SharePoint 網站] 索引標籤中，按一下 [文件]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-161">In the new SharePoint site tab of your browser, click **Documents**.</span></span>
    
4. <span data-ttu-id="2c53c-162">按一下設定圖示，然後按一下 [文件庫設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-162">Click the settings icon, and then click **Library settings**.</span></span>
    
5. <span data-ttu-id="2c53c-163">在 [權限與管理]\*\*\*\* 下，按一下 [Apply label to items in this library]\(將標籤套用至此文件庫中的項目)\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-163">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
6. <span data-ttu-id="2c53c-164">在 [設定] - [套用標籤]\*\*\*\* 中，選取適當的標籤，然後按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-164">In **Settings-Apply Label**, select the appropriate label, and then click **Save**.</span></span>
    
7. <span data-ttu-id="2c53c-165">關閉 SharePoint Online 網站的索引標籤。</span><span class="sxs-lookup"><span data-stu-id="2c53c-165">Close the tab for the SharePoint Online site.</span></span>
    
8. <span data-ttu-id="2c53c-166">重複步驟 3-8，將 Office 365 標籤指派給其他 SharePoint Online 網站。</span><span class="sxs-lookup"><span data-stu-id="2c53c-166">Repeat steps 3-8 to assign Office 365 labels to your additional SharePoint Online sites.</span></span>
    
<span data-ttu-id="2c53c-167">以下是您產生的組態。</span><span class="sxs-lookup"><span data-stu-id="2c53c-167">Here is your resulting configuration.</span></span>
  
![用於四種類型 SharePoint Online 小組網站的 Office 365 標籤。](media/e0a4fdd2-1c30-4d93-8af4-a6f0c6c29966.png)
  
## <a name="dlp-policies-for-your-sharepoint-online-sites"></a><span data-ttu-id="2c53c-169">適用於 SharePoint Online 網站的 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="2c53c-169">DLP policies for your SharePoint Online sites</span></span>

<span data-ttu-id="2c53c-170">使用下列步驟來設定 DLP 原則，以在使用者共用組織外部 SharePoint Online 機密小組網站上的文件時通知使用者。</span><span class="sxs-lookup"><span data-stu-id="2c53c-170">Use these steps to configure a DLP policy that notifies users when they share a document on a SharePoint Online sensitive team site outside the organization.</span></span>
  
1. <span data-ttu-id="2c53c-171">從瀏覽器的 [Microsoft Office 的首頁]\*\*\*\* 索引標籤中，按一下 [安全性 &amp; 合規性]\*\*\*\* 磚。</span><span class="sxs-lookup"><span data-stu-id="2c53c-171">From the **Microsoft Office Home** tab in your browser, click the **Security &amp; Compliance** tile.</span></span>
    
2. <span data-ttu-id="2c53c-172">在瀏覽器的新 [安全性 &amp; 合規性]\*\*\*\* 索引標籤上，按一下 [資料外洩防護] > [原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-172">On the new **Security &amp; Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>
    
3. <span data-ttu-id="2c53c-173">在 [資料外洩防護]\*\*\*\* 窗格中，按一下 [+ 建立原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-173">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>
    
4. <span data-ttu-id="2c53c-174">在 [從範本開始或建立自訂原則]\*\*\*\* 窗格中，按一下 [自訂]\*\*\*\*，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-174">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="2c53c-175">在 [命名您的原則]\*\*\*\* 窗格的 [名稱]\*\*\*\* 中，鍵入機密層級 DLP 原則的名稱，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-175">In the **Name your policy** pane, type the name for the sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="2c53c-176">在 [選擇位置]\*\*\*\* 窗格中，按一下 [讓我選擇特定位置]\*\*\*\*，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-176">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="2c53c-177">在位置清單中，停用 [Exchange 電子郵件]\*\*\*\* 和 [OneDrive 帳戶]\*\*\*\* 位置，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-177">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="2c53c-178">在 [Customize the types of sensitive info you want to protect]\(自訂您要保護的機密資訊類型)\*\*\*\* 窗格中，按一下 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-178">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="2c53c-179">在 [選擇要保護的內容類型]\*\*\*\* 窗格中，從下拉式方塊按一下 [新增]\*\*\*\*，然後按一下 [標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-179">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>
    
10. <span data-ttu-id="2c53c-180">在 [標籤]\*\*\*\* 窗格中，按一下 [+ 新增]\*\*\*\* 並選取 [敏感性]\*\*\*\* 標籤，然後依序按一下 [新增]\*\*\*\* 和 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-180">In the **Labels** pane, click **+ Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="2c53c-181">在 [Choose the types of content to protect]\(選擇要保護的內容類型)\*\*\*\* 窗格中，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-181">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="2c53c-182">在 [Customize the types of sensitive info you want to protect]\(自訂您要保護的機密資訊類型)\*\*\*\* 窗格中，按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-182">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
13. <span data-ttu-id="2c53c-183">在 [What do you want to do if we detect sensitive info?]\(如果偵測到機密資訊要如何處理?)\*\*\*\* 窗格中，按一下 [Customize the tip and email]\(自訂提示和電子郵件)\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-183">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="2c53c-184">在 [Customize policy tips and email notifications]\(自訂原則提示和電子郵件通知)\*\*\*\* 窗格中，按一下 [Customize the policy tip text]\(自訂原則提示文字)\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-184">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="2c53c-185">在文字方塊中，根據您是否實作 Azure 資訊保護來保護高度機密的檔案，以鍵入或貼上下列其中一個提示：</span><span class="sxs-lookup"><span data-stu-id="2c53c-185">In the text box, type or paste in one of the following tips, depending on if you implemented Azure Information Protection to protect highly confidential files:</span></span>
    
  - <span data-ttu-id="2c53c-p106">若要與組織外部的使用者共用，請下載檔案，然後將它開啟。 依序按一下 [檔案]、[保護文件] 和 [以密碼加密]，然後指定強式密碼。 以個別電子郵件或其他通訊方式傳送密碼。</span><span class="sxs-lookup"><span data-stu-id="2c53c-p106">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
  - <span data-ttu-id="2c53c-p107">高度機密的檔案會受加密保護。只有獲得您 IT 部門授與權限的外部使用者可以讀取它們。</span><span class="sxs-lookup"><span data-stu-id="2c53c-p107">Highly confidential files are protected with encryption. Only external users who are granted permissions to these files by your IT department can read them.</span></span>
    
    <span data-ttu-id="2c53c-191">或者，鍵入或貼上您自己的原則提示，以指示使用者如何共用組織外部的檔案。</span><span class="sxs-lookup"><span data-stu-id="2c53c-191">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="2c53c-192">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-192">Click **OK**.</span></span>
    
17. <span data-ttu-id="2c53c-193">在 [如果偵測到機密資訊要如何處理?]\*\*\*\* 窗格中，清除 [禁止人員共用及限制共用內容的存取]\*\*\*\* 核取方塊，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-193">In the **What do you want to do if we detect sensitive info?** pane, clear the **Block people from sharing, and restrict access to shared content** check box, and then click **Next**.</span></span>
    
18. <span data-ttu-id="2c53c-194">在 [要先開啟原則或測試內容嗎?]\*\*\*\* 窗格中，按一下 [是]\*\*\*\* 立即將它開啟，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-194">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="2c53c-195">在 [檢閱您的設定]\*\*\*\* 窗格中，按一下 [建立]\*\*\*\*，然後按一下 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-195">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="2c53c-196">以下是敏感性 SharePoint Online 小組網站的設定結果。</span><span class="sxs-lookup"><span data-stu-id="2c53c-196">Here is your resulting configuration for sensitive SharePoint Online team sites.</span></span>
  
![使用敏感性 Office 365 標籤之隔離 SharePoint Online 小組網站的 DLP 原則。](media/2ff4cc53-87a8-43e3-b637-3068d88409f3.png)
  
<span data-ttu-id="2c53c-198">接下來，使用下列步驟來設定 DLP 原則，以在使用者共用組織外部 SharePoint Online 高度機密小組網站上的文件時封鎖使用者。</span><span class="sxs-lookup"><span data-stu-id="2c53c-198">Next, use these steps to configure a DLP policy that blocks users when they share a document on a SharePoint Online highly confidential team site outside the organization.</span></span>
  
1. <span data-ttu-id="2c53c-199">從瀏覽器的 [Microsoft Office 的首頁]\*\*\*\* 索引標籤中，按一下 [安全性 &amp; 合規性]\*\*\*\* 磚。</span><span class="sxs-lookup"><span data-stu-id="2c53c-199">From the **Microsoft Office Home** tab in your browser, click the **Security &amp; Compliance** tile.</span></span>
    
2. <span data-ttu-id="2c53c-200">在瀏覽器的新 [安全性 &amp; 合規性]\*\*\*\* 索引標籤上，按一下 [資料外洩防護] > [原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-200">On the new **Security &amp; Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>
    
3. <span data-ttu-id="2c53c-201">在 [資料外洩防護]\*\*\*\* 窗格中，按一下 [+ 建立原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-201">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>
    
4. <span data-ttu-id="2c53c-202">在 [從範本開始或建立自訂原則]\*\*\*\* 窗格中，按一下 [自訂]\*\*\*\*，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-202">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="2c53c-203">在 [命名您的原則]\*\*\*\* 窗格的 [名稱]\*\*\*\* 中，鍵入高度機密層級 DLP 原則的名稱，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-203">In the **Name your policy** pane, type the name for the highly sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="2c53c-204">在 [選擇位置]\*\*\*\* 窗格中，按一下 [讓我選擇特定位置]\*\*\*\*，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-204">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="2c53c-205">在位置清單中，停用 [Exchange 電子郵件]\*\*\*\* 和 [OneDrive 帳戶]\*\*\*\* 位置，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-205">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="2c53c-206">在 [Customize the types of sensitive info you want to protect]\(自訂您要保護的機密資訊類型)\*\*\*\* 窗格中，按一下 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-206">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="2c53c-207">在 [選擇要保護的內容類型]\*\*\*\* 窗格中，從下拉式方塊按一下 [新增]\*\*\*\*，然後按一下 [標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-207">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>
    
10. <span data-ttu-id="2c53c-208">在 [標籤]\*\*\*\* 窗格中，按一下 [+ 新增]\*\*\*\*，並選取 [高度機密]\*\*\*\* 標籤，然後依序按一下 [新增]\*\*\*\* 和 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-208">In the **Labels** pane, click **+ Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="2c53c-209">在 [Choose the types of content to protect]\(選擇要保護的內容類型)\*\*\*\* 窗格中，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-209">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="2c53c-210">在 [Customize the types of sensitive info you want to protect]\(自訂您要保護的機密資訊類型)\*\*\*\* 窗格中，按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-210">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
13. <span data-ttu-id="2c53c-211">在 [What do you want to do if we detect sensitive info?]\(如果偵測到機密資訊要如何處理?)\*\*\*\* 窗格中，按一下 [Customize the tip and email]\(自訂提示和電子郵件)\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-211">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="2c53c-212">在 [Customize policy tips and email notifications]\(自訂原則提示和電子郵件通知)\*\*\*\* 窗格中，按一下 [Customize the policy tip text]\(自訂原則提示文字)\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-212">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="2c53c-213">在文字方塊中，鍵入或貼上下列內容：</span><span class="sxs-lookup"><span data-stu-id="2c53c-213">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="2c53c-p108">若要與組織外部的使用者共用，請下載檔案，然後將它開啟。 依序按一下 [檔案]、[保護文件] 和 [以密碼加密]，然後指定強式密碼。 以個別電子郵件或其他通訊方式傳送密碼。</span><span class="sxs-lookup"><span data-stu-id="2c53c-p108">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
    <span data-ttu-id="2c53c-217">或者，鍵入或貼上您自己的原則提示，以指示使用者如何共用組織外部的檔案。</span><span class="sxs-lookup"><span data-stu-id="2c53c-217">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="2c53c-218">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-218">Click **OK**.</span></span>
    
17. <span data-ttu-id="2c53c-219">在 [如果偵測到機密資訊要如何處理?]\*\*\*\* 窗格中，選取 [需要有業務上的正當理由才能覆寫]\*\*\*\*，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-219">In the **What do you want to do if we detect sensitive info?** pane, select **Require a business justification to override**, and then click **Next**.</span></span>
    
18. <span data-ttu-id="2c53c-220">在 [要先開啟原則或測試內容嗎?]\*\*\*\* 窗格中，按一下 [是]\*\*\*\* 立即將它開啟，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-220">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="2c53c-221">在 [檢閱您的設定]\*\*\*\* 窗格中，按一下 [建立]\*\*\*\*，然後按一下 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c53c-221">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="2c53c-222">以下是高度機密 SharePoint Online 小組網站的設定結果。</span><span class="sxs-lookup"><span data-stu-id="2c53c-222">Here is your resulting configuration for high confidentiality SharePoint Online team sites.</span></span>
  
![使用高度機密 Office 365 標籤之隔離 SharePoint Online 小組網站的 DLP 原則。](media/f705d3d0-23c9-4333-8b70-ad3b91f835ea.png)
  
## <a name="next-step"></a><span data-ttu-id="2c53c-224">下一步</span><span class="sxs-lookup"><span data-stu-id="2c53c-224">Next step</span></span>

[<span data-ttu-id="2c53c-225">使用 Azure 資訊保護來保護 SharePoint Online 檔案</span><span class="sxs-lookup"><span data-stu-id="2c53c-225">Protect SharePoint Online files with Azure Information Protection</span></span>](protect-sharepoint-online-files-with-azure-information-protection.md)
    
## <a name="see-also"></a><span data-ttu-id="2c53c-226">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2c53c-226">See Also</span></span>

[<span data-ttu-id="2c53c-227">保護 SharePoint Online 網站與檔案</span><span class="sxs-lookup"><span data-stu-id="2c53c-227">Secure SharePoint Online sites and files</span></span>](secure-sharepoint-online-sites-and-files.md)
  
[<span data-ttu-id="2c53c-228">在開發/測試環境中保護 SharePoint Online 網站</span><span class="sxs-lookup"><span data-stu-id="2c53c-228">Secure SharePoint Online sites in a dev/test environment</span></span>](secure-sharepoint-online-sites-in-a-dev-test-environment.md)
  
[<span data-ttu-id="2c53c-229">適用於政治活動、非營利組織和其他彈性組織的 Microsoft 安全性指南</span><span class="sxs-lookup"><span data-stu-id="2c53c-229">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="2c53c-230">雲端採用和混合式解決方案</span><span class="sxs-lookup"><span data-stu-id="2c53c-230">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)


