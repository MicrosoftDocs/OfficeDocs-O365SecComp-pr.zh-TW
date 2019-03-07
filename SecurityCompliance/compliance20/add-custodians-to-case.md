---
title: 新增 custodians 至進階電子文件 （預覽） 案例
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: fe208f4a9f7927d8481d5c6ec8b901baafb98626
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/06/2019
ms.locfileid: "30455295"
---
# <a name="add-custodians-to-an-advanced-ediscovery-preview-case"></a><span data-ttu-id="ed655-102">新增 custodians 至進階電子文件 （預覽） 案例</span><span class="sxs-lookup"><span data-stu-id="ed655-102">Add custodians to an Advanced eDiscovery (Preview) case</span></span>

<span data-ttu-id="ed655-103">使用進階電子文件 （預覽），您可以利用內建 custodian 管理工具，來調整您的工作流程管理 custodians 和識別案例中的相關、 custodial 資料來源周圍。</span><span class="sxs-lookup"><span data-stu-id="ed655-103">Using Advanced eDiscovery (Preview), you can leverage the built-in custodian management tool to coordinate your workflows around managing custodians and identifying relevant, custodial data sources within a case.</span></span> <span data-ttu-id="ed655-104">當您新增 custodian 時，系統可以自動辨識，和就地保留在其主要 Exchange 信箱和 OneDrive for Business 網站。</span><span class="sxs-lookup"><span data-stu-id="ed655-104">When you add a custodian, the system can automatically identify, and place holds on their primary Exchange mailbox and OneDrive for Business site.</span></span> <span data-ttu-id="ed655-105">當您進行您探索，您可能也從抽出及對應其他信箱或網站，custodian 存取過去或小組中 custodian 是今天的成員。</span><span class="sxs-lookup"><span data-stu-id="ed655-105">As you conduct your discovery, you might also uncover and map additional mailboxes or sites that a custodian accessed in the past or Teams that a custodian is a member of today.</span></span>

<span data-ttu-id="ed655-106">若要新增及管理 custodians 在進階電子文件 （預覽） 安全性 & 合規性中心內的情況下使用下列工作流程。</span><span class="sxs-lookup"><span data-stu-id="ed655-106">Use the following workflow to add and manage custodians in Advanced eDiscovery (Preview) cases within the Security & Compliance Center.</span></span> 

![Custodian 管理] 索引標籤](../media/CustodianMgtPage.png)


## <a name="step-1-identify-potential-custodians"></a><span data-ttu-id="ed655-108">步驟 1： 找出潛在 custodians</span><span class="sxs-lookup"><span data-stu-id="ed655-108">Step 1: Identify potential custodians</span></span>

<span data-ttu-id="ed655-109">第一個步驟是以識別您專家的適當 custodians。</span><span class="sxs-lookup"><span data-stu-id="ed655-109">The first step is to identify the appropriate custodians for your matter.</span></span> <span data-ttu-id="ed655-110">若要新增 custodians 案例，您必須是成員的 eDiscovery 管理員或 eDiscovery 管理員 」 角色群組。</span><span class="sxs-lookup"><span data-stu-id="ed655-110">To add custodians to a case, you must be a member of the eDiscovery Managers or eDiscovery Admins role group.</span></span>   

![識別潛在 Custodians](../media/AddCustodianStep1.png)

<span data-ttu-id="ed655-112">若要將 custodians 新增至現有的進階電子文件 （預覽） 案例：</span><span class="sxs-lookup"><span data-stu-id="ed655-112">To add custodians to an existing Advanced eDiscovery (Preview) case:</span></span>

1. <span data-ttu-id="ed655-113">從 [**進階電子文件 （預覽）** ] 頁面上，移至您的案例。</span><span class="sxs-lookup"><span data-stu-id="ed655-113">From the **Advanced eDiscovery (Preview)** page, go to your case.</span></span>
 
2. <span data-ttu-id="ed655-114">選取案例之後，請移至 [ **Custodians** ] 索引標籤，然後按一下 [ **+ 新增 Custodian**。</span><span class="sxs-lookup"><span data-stu-id="ed655-114">After you have selected a case, go to the **Custodians** tab and click **+ Add Custodian**.</span></span> 
 
3. <span data-ttu-id="ed655-115">選擇您想要新增至案例 custodians。</span><span class="sxs-lookup"><span data-stu-id="ed655-115">Choose the custodians that you want to add to the case.</span></span> <span data-ttu-id="ed655-116">您可以啟動搜尋並從貴組織的 Azure Active Directory 選取使用者的輸入。</span><span class="sxs-lookup"><span data-stu-id="ed655-116">You can start by typing to search and select the users from your organization's Azure Active Directory.</span></span>
 
4. <span data-ttu-id="ed655-117">您已完成的 custodians 清單之後，按 [**下一**開始用來識別潛在的資料來源。</span><span class="sxs-lookup"><span data-stu-id="ed655-117">After you have finalized the list of custodians, click **Next** to begin identifying potential data sources.</span></span> 
  
## <a name="optional-step-2-select-custodian-data-sources"></a><span data-ttu-id="ed655-118">（選用）步驟 2： 選取 [custodian 資料來源</span><span class="sxs-lookup"><span data-stu-id="ed655-118">(Optional) Step 2: Select custodian data sources</span></span>

<span data-ttu-id="ed655-119">Custodians 新增至案例之後，您可以利用 Office 365，以協助您識別並保存 custodian 主要資料來源。</span><span class="sxs-lookup"><span data-stu-id="ed655-119">After you have added custodians to a case, you can leverage Office 365 to help you identify and preserve the primary custodian data sources.</span></span> <span data-ttu-id="ed655-120">此工作流程的下一個步驟是選取步驟 1 中所指定 custodians 所擁有的資料來源。</span><span class="sxs-lookup"><span data-stu-id="ed655-120">The next step in this workflow is to select the data sources owned by the custodians specified in Step 1.</span></span> 

![選取 [Custodial 資料來源](../media/AddCustodianStep2.png)

<span data-ttu-id="ed655-122">若要找出 custodian 資料來源：</span><span class="sxs-lookup"><span data-stu-id="ed655-122">To identify custodian data sources:</span></span> 

1. <span data-ttu-id="ed655-123">針對每個 custodian 中，選取**Exchange** ，如果您想要自動識別，並新增 custodian 主要 Exchange 信箱系統。</span><span class="sxs-lookup"><span data-stu-id="ed655-123">For each custodian, select **Exchange** if you would like the system to automatically identify and add the custodian's primary Exchange mailbox.</span></span> 
 
2. <span data-ttu-id="ed655-124">每個 custodian 中，選取 [ **OneDrive**如果您想要自動識別，並新增 custodian 主要 OneDrive URL 的系統。</span><span class="sxs-lookup"><span data-stu-id="ed655-124">For each custodian, select **OneDrive** if you would like the system to automatically identify and add the custodian's primary OneDrive URL.</span></span> 

    <span data-ttu-id="ed655-125">進行您的選擇之後, 他們系統會自動嘗試找出資料來源，並將其新增至您的案例。</span><span class="sxs-lookup"><span data-stu-id="ed655-125">After you've made your selections, they system will automatically try to identify the data sources and add them to your case.</span></span>
 
4. <span data-ttu-id="ed655-126">按 [**下一步**開始將其他資料來源對應至您 custodian。</span><span class="sxs-lookup"><span data-stu-id="ed655-126">Click **Next** to begin mapping additional data sources to your custodian.</span></span>

## <a name="optional-step-3-map-additional-data-sources"></a><span data-ttu-id="ed655-127">（選用）步驟 3： 將其他資料來源對應</span><span class="sxs-lookup"><span data-stu-id="ed655-127">(Optional) Step 3: Map additional data sources</span></span>

<span data-ttu-id="ed655-128">根據您的情況下，您可能還想要新增給定的 custodian 可能是在過去，使用的信箱群組其中 custodian 目前成員，或網站 custodian，必須在過去的存取權。</span><span class="sxs-lookup"><span data-stu-id="ed655-128">Depending on your case, you may also want to add mailboxes that a given custodian may have used in the past, groups where a custodian is currently a member, or sites that a custodian had access to in the past.</span></span> <span data-ttu-id="ed655-129">除了主要 custodian 資料來源，您可以將其他 Office 365 的資料來源新增至 custodian，或利用 Office 365，可協助您識別也可能相關的資料來源。</span><span class="sxs-lookup"><span data-stu-id="ed655-129">In addition to primary custodian data sources, you can add additional Office 365 data sources to a custodian or leverage Office 365 to help you identify potentially relevant data sources as well.</span></span> 

![將其他資料來源對應](../media/AddCustodianStep3.PNG)

<span data-ttu-id="ed655-131">若要將信箱、 網站或小組對應至特定 custodian:</span><span class="sxs-lookup"><span data-stu-id="ed655-131">To map mailboxes, sites, or teams to a specific custodian:</span></span>
1. <span data-ttu-id="ed655-132">選取 [**新增**若要將內容的位置，例如信箱、 網站和小組，指派給特定 custodian。</span><span class="sxs-lookup"><span data-stu-id="ed655-132">Select **Add** to assign content locations, like mailboxes, sites, and Teams, to a specific custodian.</span></span> 

2. <span data-ttu-id="ed655-133">在彈出式視窗中，指定下列設定：![對應的資料來源](../media/AddCustodianStep4.PNG)</span><span class="sxs-lookup"><span data-stu-id="ed655-133">In the flyout, specify the following: ![Map Data Sources](../media/AddCustodianStep4.PNG)</span></span>
  -  <span data-ttu-id="ed655-134">**Exchange 信箱**-按一下 [**選擇使用者、 群組或小組**，然後再按一下 [**選擇使用者、 群組或小組**。</span><span class="sxs-lookup"><span data-stu-id="ed655-134">**Exchange Mailboxes** - Click **Choose users, groups, or Teams** and then click **Choose users, groups, or teams** again.</span></span> <span data-ttu-id="ed655-135">若要指定要指派給所選 custodian 的信箱，請使用 [搜尋] 方塊來尋找使用者信箱和通訊群組。</span><span class="sxs-lookup"><span data-stu-id="ed655-135">To specify mailboxes to assign to the selected custodian, use the search box to find user mailboxes and distribution groups.</span></span> <span data-ttu-id="ed655-136">您也可以針對 Office 365 群組或 Microsoft 小組指派相關聯的信箱。</span><span class="sxs-lookup"><span data-stu-id="ed655-136">You can also assign the associated mailbox for an Office 365 Group or a Microsoft Team.</span></span> <span data-ttu-id="ed655-137">選取使用者、 群組、 小組] 核取方塊，按一下 [**選擇**，然後按一下 [**完成**。</span><span class="sxs-lookup"><span data-stu-id="ed655-137">Select the user, group, team check box, click **Choose**, and then click **Done**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="ed655-138">當您按一下 [選擇使用者、 群組或小組來指定信箱時，會顯示信箱選擇器是空的。</span><span class="sxs-lookup"><span data-stu-id="ed655-138">When you click Choose users, groups, or teams to specify mailboxes, the mailbox picker that's displayed is empty.</span></span> <span data-ttu-id="ed655-139">這項設計的目的是提升效能。</span><span class="sxs-lookup"><span data-stu-id="ed655-139">This is by design to enhance performance.</span></span> <span data-ttu-id="ed655-140">若要將人員新增至這份清單中，輸入的名稱 （3 個字元的最少） 在 [搜尋] 方塊中。</span><span class="sxs-lookup"><span data-stu-id="ed655-140">To add people to this list, type a name (a minimum of 3 characters) in the search box.</span></span>
     
     - <span data-ttu-id="ed655-141">**SharePoint 網站**-按一下 [**選擇網站**]，然後按一下 [**選擇網站**再次指定其他的 SharePoint 和 OneDrive for Business 網站，您可能會想要指派給所選 custodian。</span><span class="sxs-lookup"><span data-stu-id="ed655-141">**SharePoint Sites** - Click **Choose sites** and then click **Choose sites** again to specify additional SharePoint and OneDrive for Business sites that you would like to assign to the selected custodian.</span></span> <span data-ttu-id="ed655-142">您也可以新增 SharePoint 網站的 URL 的 Office 365 群組或 Microsoft 小組。</span><span class="sxs-lookup"><span data-stu-id="ed655-142">You can also add the URL for the SharePoint site for an Office 365 Group or a Microsoft Team.</span></span> <span data-ttu-id="ed655-143">輸入您想要指派每個網站的 URL。</span><span class="sxs-lookup"><span data-stu-id="ed655-143">Type the URL for each site that you want to assign.</span></span> <span data-ttu-id="ed655-144">按一下 [**選擇**，然後按一下 [**完成**。</span><span class="sxs-lookup"><span data-stu-id="ed655-144">Click **Choose**, and then click **Done**.</span></span>
     - <span data-ttu-id="ed655-145">**Microsoft Teams** – 按一下 [**選擇小組**，然後按一下 [**選擇小組**再次以檢視 Microsoft 小組群組 custodian 是今天成員的清單。</span><span class="sxs-lookup"><span data-stu-id="ed655-145">**Microsoft Teams** – Click **Choose Teams** and then click **Choose Teams** again to view a list of Microsoft Team groups that the custodian is a member of today.</span></span> <span data-ttu-id="ed655-146">選取您想要新增至您 custodian Teams。</span><span class="sxs-lookup"><span data-stu-id="ed655-146">Select the Teams that you would like to add to your custodian.</span></span> <span data-ttu-id="ed655-147">一旦選取，系統會自動識別相關聯的 [SharePoint 網站] 及 [群組信箱相關聯的 Microsoft Team & 選取。</span><span class="sxs-lookup"><span data-stu-id="ed655-147">Once selected, the system will automatically identify & select the associated SharePoint site and Group Mailbox associated to that Microsoft Team.</span></span> <span data-ttu-id="ed655-148">按一下 [**選擇**，然後按一下 [**完成**。</span><span class="sxs-lookup"><span data-stu-id="ed655-148">Click **Choose**, and then click **Done**.</span></span>
        
      > [!NOTE]
      > <span data-ttu-id="ed655-149">若要新增其他的 Microsoft Teams，您需要分別新增的信箱和 SharePoint 網站如上所示。</span><span class="sxs-lookup"><span data-stu-id="ed655-149">To add additional Microsoft Teams, you will need to separately add the mailbox and SharePoint site as shown above.</span></span>

<span data-ttu-id="ed655-150">完成對應您的來源之後，您可以檢視您剛新增 custodians 信箱總數、 網站及 microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="ed655-150">After you have finished mapping your sources, you can view the total mailboxes, sites, and Teams for the custodians that you have just added.</span></span> <span data-ttu-id="ed655-151">當您完成相關的資料來源的特定 custodian 時，將會維護此對應，而且延伸至 eDiscovery 收集、 處理及檢閱工作流程。</span><span class="sxs-lookup"><span data-stu-id="ed655-151">When you've finalized the data sources relevant for a specific custodian, this mapping will be maintained and extended to the eDiscovery collection, processing, and review workflows.</span></span> 

## <a name="optional-step-4-place-custodians-on-hold"></a><span data-ttu-id="ed655-152">（選用）步驟 4： 就地 custodians 上保留</span><span class="sxs-lookup"><span data-stu-id="ed655-152">(Optional) Step 4: Place custodians on hold</span></span>

![就地保留](../media/AddCustodianStep5.PNG)

<span data-ttu-id="ed655-154">您已完成的 custodians 和您想要新增至您案例的資料來源之後，您可以選擇性地放置部分或所有在您 custodians 保留。</span><span class="sxs-lookup"><span data-stu-id="ed655-154">After you have finalized the custodians and data sources that you would like to add to your case, you can optionally place some or all of your custodians on hold.</span></span> <span data-ttu-id="ed655-155">當您保留上放置 custodian 時，對應至該使用者的內容會保留直到您放開 custodian 從這種情況，或直到您刪除保留。</span><span class="sxs-lookup"><span data-stu-id="ed655-155">When you place a custodian on hold, the content mapped to that user is held until you release the custodian from the case or until you delete the hold.</span></span> <span data-ttu-id="ed655-156">在某些情況下，您可能想要將 custodians 新增至案例中，而不將其置於保留狀態。</span><span class="sxs-lookup"><span data-stu-id="ed655-156">In some cases, you may want to add custodians to a case without placing them on hold.</span></span> 

<span data-ttu-id="ed655-157">若要將所選 custodians 與資料來源上的保留：</span><span class="sxs-lookup"><span data-stu-id="ed655-157">To place the selected custodians and data sources on hold:</span></span>

1. <span data-ttu-id="ed655-158">驗證 custodian 選項，然後選取要就地保留每個 custodian] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="ed655-158">Verify your custodian selections and select the checkbox to place each custodian on hold.</span></span> <span data-ttu-id="ed655-159">Custodian 處於保留狀態之後，就會自動建立包含所有 custodial 來源 custodian 保留原則。</span><span class="sxs-lookup"><span data-stu-id="ed655-159">After a custodian is placed on hold, a custodian hold policy containing all custodial sources will be automatically created.</span></span> <span data-ttu-id="ed655-160">如果選項不會檢查，custodian，而且不是選取資料來源會新增至案例，但將不會保留內容。</span><span class="sxs-lookup"><span data-stu-id="ed655-160">If the option is not checked, the custodian and selected data sources will be added to the case but the content will not be preserved.</span></span>

2. <span data-ttu-id="ed655-161">移至 [**保留**] 索引標籤，然後選取 [ **Custodian 保留原則**。</span><span class="sxs-lookup"><span data-stu-id="ed655-161">Go to the **Holds** tab and select the **Custodian Hold Policy**.</span></span> 

3. <span data-ttu-id="ed655-162">按一下 [**編輯**] 以檢視所有選取的 custodian 資料來源。</span><span class="sxs-lookup"><span data-stu-id="ed655-162">Click **Edit** to view all the selected custodian data sources.</span></span>

   
