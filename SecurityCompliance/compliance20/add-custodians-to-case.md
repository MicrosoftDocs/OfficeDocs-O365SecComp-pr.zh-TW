---
title: 將 custodians 新增至進階的 eDiscovery （預覽） 案例
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: d9a7dc6b1c2eeffdcd49be64d1d09d4a2bda782b
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607577"
---
# <a name="add-custodians-to-an-advanced-ediscovery-preview-case"></a><span data-ttu-id="5511a-102">新增 custodians （預覽） 進階 ediscovery 案例</span><span class="sxs-lookup"><span data-stu-id="5511a-102">Add custodians to an Advanced eDiscovery (Preview) Case</span></span>

<span data-ttu-id="5511a-p101">使用進階的 eDiscovery （預覽），您可以運用協調繞管理 custodians 和相關、 custodial 資料來源的案例中用來識別您工作流程內建 okay 管理工具。當您新增 okay 時，系統可以自動識別、 和就地保留在其主要 Exchange 信箱和 OneDrive 商務網站。當您進行您探索，也可能會從抽出和對應其他信箱或網站確認 okay 存取過去或小組中 okay 是今天的成員。</span><span class="sxs-lookup"><span data-stu-id="5511a-p101">Using Advanced eDiscovery (Preview), you can leverage the built-in custodian management tool to coordinate your workflows around managing custodians and identifying relevant, custodial data sources within a case. When you add a custodian, the system can automatically identify, and place holds on their primary Exchange mailbox and OneDrive for Business site. As you conduct your discovery, you might also uncover and map additional mailboxes or sites that a custodian accessed in the past or Teams that a custodian is a member of today.</span></span>

<span data-ttu-id="5511a-106">新增及管理 custodians 安全性 & 規範中心內的進階的 eDiscovery （預覽） 案例中使用下列工作流程。</span><span class="sxs-lookup"><span data-stu-id="5511a-106">Use the following workflow to add and manage custodians in Advanced eDiscovery (Preview) cases within the Security & Compliance Center.</span></span> 

## <a name="step-1-identify-potential-custodians"></a><span data-ttu-id="5511a-107">步驟 1： 識別潛在 custodians</span><span class="sxs-lookup"><span data-stu-id="5511a-107">Step 1: Identify potential custodians</span></span>

<span data-ttu-id="5511a-p102">第一個步驟是以識別您專家的適當 custodians。若要新增 custodians 案例，您必須是 eDiscovery 管理員的成員或 eDiscovery 系統管理員角色群組。</span><span class="sxs-lookup"><span data-stu-id="5511a-p102">The first step is to identify the appropriate custodians for your matter. To add custodians to a case, you must be a member of the eDiscovery Managers or eDiscovery Admins role group.</span></span>   

<span data-ttu-id="5511a-110">若要將 custodians 新增至現有的進階的 eDiscovery （預覽） 案例：</span><span class="sxs-lookup"><span data-stu-id="5511a-110">To add custodians to an existing Advanced eDiscovery (Preview) case:</span></span>

1. <span data-ttu-id="5511a-111">從 [**進階的 eDiscovery （預覽）** ] 頁面上，移至您的案例。</span><span class="sxs-lookup"><span data-stu-id="5511a-111">From the **Advanced eDiscovery (Preview)** page, go to your case.</span></span>
 
2. <span data-ttu-id="5511a-112">選取案例之後，請移至 [ **Custodians** ] 索引標籤並按一下 [ **+ 新增 Okay**。</span><span class="sxs-lookup"><span data-stu-id="5511a-112">After you have selected a case, go to the **Custodians** tab and click **+ Add Custodian**.</span></span> 
 
3. <span data-ttu-id="5511a-p103">選擇您想要新增至案例 custodians。您可以搜尋並從您的組織 Azure Active Directory 選取的使用者輸入來啟動。</span><span class="sxs-lookup"><span data-stu-id="5511a-p103">Choose the custodians that you want to add to the case. You can start by typing to search and select the users from your organization's Azure Active Directory.</span></span>
 
4. <span data-ttu-id="5511a-115">您已完成的 custodians 清單之後，按 [**下一**開始用來識別潛在的資料來源。</span><span class="sxs-lookup"><span data-stu-id="5511a-115">After you have finalized the list of custodians, click **Next** to begin identifying potential data sources.</span></span> 
   
## <a name="optional-step-2-select-custodian-data-sources"></a><span data-ttu-id="5511a-116">（選用）步驟 2： 選取 okay 資料來源</span><span class="sxs-lookup"><span data-stu-id="5511a-116">(Optional) Step 2: Select custodian data sources</span></span>

<span data-ttu-id="5511a-p104">新增 custodians 案例之後，您可以運用 Office 365 可協助您識別並保留主要 okay 資料來源。此工作流程的下一個步驟是選取步驟 1 中所指定 custodians 所擁有的資料來源。</span><span class="sxs-lookup"><span data-stu-id="5511a-p104">After you have added custodians to a case, you can leverage Office 365 to help you identify and preserve the primary custodian data sources. The next step in this workflow is to select the data sources owned by the custodians specified in Step 1.</span></span> 

<span data-ttu-id="5511a-119">識別 okay 資料來源：</span><span class="sxs-lookup"><span data-stu-id="5511a-119">To identify custodian data sources:</span></span> 

1. <span data-ttu-id="5511a-120">針對每個 okay 中，選取 [ **Exchange**如果您想要自動找出並新增 okay 主要 Exchange 信箱的系統。</span><span class="sxs-lookup"><span data-stu-id="5511a-120">For each custodian, select **Exchange** if you would like the system to automatically identify and add the custodian's primary Exchange mailbox.</span></span> 
 
2. <span data-ttu-id="5511a-121">針對每個 okay、 選取**OneDrive**如果您想要自動找出並新增 okay 主要 OneDrive URL 系統。</span><span class="sxs-lookup"><span data-stu-id="5511a-121">For each custodian, select **OneDrive** if you would like the system to automatically identify and add the custodian's primary OneDrive URL.</span></span> 

    <span data-ttu-id="5511a-122">您是否已進行您的選擇之後, 這些系統將會自動嘗試找出的資料來源並將其新增至您的案例。</span><span class="sxs-lookup"><span data-stu-id="5511a-122">After you've made your selections, they system will automatically try to identify the data sources and add them to your case.</span></span>
 
4. <span data-ttu-id="5511a-123">按 [**下一**開始將其他資料來源對應至您 okay。</span><span class="sxs-lookup"><span data-stu-id="5511a-123">Click **Next** to begin mapping additional data sources to your custodian.</span></span>

## <a name="optional-step-3-map-additional-data-sources"></a><span data-ttu-id="5511a-124">（選用）步驟 3： 將對應其他資料來源</span><span class="sxs-lookup"><span data-stu-id="5511a-124">(Optional) Step 3: Map additional data sources</span></span>

<span data-ttu-id="5511a-p105">根據您的案例中，可能也想要新增給定的 okay 可能已經使用過去的信箱群組的 okay 那過去其中 okay 目前成員或網站。除了主要 okay 資料來源而言，您可以為 okay 新增其他 Office 365 的資料來源或利用 Office 365 可協助您識別也可能相關的資料來源。</span><span class="sxs-lookup"><span data-stu-id="5511a-p105">Depending on your case, you may also want to add mailboxes that a given custodian may have used in the past, groups where a custodian is currently a member, or sites that a custodian had access to in the past. In addition to primary custodian data sources, you can add additional Office 365 data sources to a custodian or leverage Office 365 to help you identify potentially relevant data sources as well.</span></span> 

<span data-ttu-id="5511a-127">若要將信箱、 網站或小組對應至特定 okay：</span><span class="sxs-lookup"><span data-stu-id="5511a-127">To map mailboxes, sites, or teams to a specific custodian:</span></span>
1. <span data-ttu-id="5511a-128">選取要指派給特定 okay 的信箱、 網站和小組類似的內容位置**更新**。</span><span class="sxs-lookup"><span data-stu-id="5511a-128">Select **Update** to assign content locations, like mailboxes, sites, and Teams, to a specific custodian.</span></span> 

2. <span data-ttu-id="5511a-129">彈出式中指定下列項目：</span><span class="sxs-lookup"><span data-stu-id="5511a-129">In the flyout, specify the following:</span></span>
   
  -  <span data-ttu-id="5511a-p106">**Exchange 信箱**-[**選擇使用者、 群組或小組**和 [**選擇使用者、 群組或小組**一次。若要指定要指派給所選 okay 信箱，使用 [搜尋] 方塊中尋找使用者信箱和通訊群組。您也可以針對 Office 365 群組或 Microsoft 小組指派關聯的信箱。選取使用者、 群組、 小組] 核取方塊、 按一下 [**選擇**] 和 [**完成**。</span><span class="sxs-lookup"><span data-stu-id="5511a-p106">**Exchange Mailboxes** - Click **Choose users, groups, or Teams** and then click **Choose users, groups, or teams** again. To specify mailboxes to assign to the selected custodian, use the search box to find user mailboxes and distribution groups. You can also assign the associated mailbox for an Office 365 Group or a Microsoft Team. Select the user, group, team check box, click **Choose**, and then click **Done**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="5511a-p107">當您按一下 [選擇使用者、 群組或小組來指定信箱時，會顯示信箱選擇是空的。這是由設計，以提升效能。若要將人員新增至這份清單中，輸入的名稱 （至少要有 3 個字元） 在 [搜尋] 方塊中。</span><span class="sxs-lookup"><span data-stu-id="5511a-p107">When you click Choose users, groups, or teams to specify mailboxes, the mailbox picker that's displayed is empty. This is by design to enhance performance. To add people to this list, type a name (a minimum of 3 characters) in the search box.</span></span>
     
   - <span data-ttu-id="5511a-p108">**SharePoint 網站**-按一下 [**選擇的網站**] 和 [一次可指定您想要指派給所選 okay 商務網站其他 SharePoint 及 OneDrive 的**選擇網站**。您也可以針對 Office 365 群組或 Microsoft 小組新增 SharePoint 網站的 URL。輸入您要指派每個網站的 URL。按一下 [**選擇**] 和 [**完成**。</span><span class="sxs-lookup"><span data-stu-id="5511a-p108">**SharePoint Sites** - Click **Choose sites** and then click **Choose sites** again to specify additional SharePoint and OneDrive for Business sites that you would like to assign to the selected custodian. You can also add the URL for the SharePoint site for an Office 365 Group or a Microsoft Team. Type the URL for each site that you want to assign. Click **Choose**, and then click **Done**.</span></span>
   - <span data-ttu-id="5511a-p109">**Microsoft 小組**– 按一下 [**選擇 [小組**] 和 [**選擇小組**再次若要檢視清單中的 Microsoft 小組群組 okay 是今天的成員。選取您想要新增至您 okay 小組。一旦選取，系統會自動識別 & 選取相關聯的 [SharePoint 網站] 和 [群組信箱相關聯的 Microsoft 小組。按一下 [**選擇**] 和 [**完成**。</span><span class="sxs-lookup"><span data-stu-id="5511a-p109">**Microsoft Teams** – Click **Choose Teams** and then click **Choose Teams** again to view a list of Microsoft Team groups that the custodian is a member of today. Select the Teams that you would like to add to your custodian. Once selected, the system will automatically identify & select the associated SharePoint site and Group Mailbox associated to that Microsoft Team. Click **Choose**, and then click **Done**.</span></span>
        
      > [!NOTE]
      > <span data-ttu-id="5511a-145">若要新增其他的 Microsoft 小組，您必須分別新增信箱和 SharePoint 網站上面所示。</span><span class="sxs-lookup"><span data-stu-id="5511a-145">To add additional Microsoft Teams, you will need to separately add the mailbox and SharePoint site as shown above.</span></span>

<span data-ttu-id="5511a-p110">完成對應您的來源之後，您可以檢視您剛新增 custodians 信箱總數、 網站及小組。當您已完成相關之資料來源的特定 okay 時，此對應會維護及延伸至 eDiscovery 集合、 處理和檢閱工作流程。</span><span class="sxs-lookup"><span data-stu-id="5511a-p110">After you have finished mapping your sources, you can view the total mailboxes, sites, and Teams for the custodians that you have just added. When you've finalized the data sources relevant for a specific custodian, this mapping will be maintained and extended to the eDiscovery collection, processing, and review workflows.</span></span> 

## <a name="optional-step-4-place-custodians-on-hold"></a><span data-ttu-id="5511a-148">（選用）步驟 4： 就地保留在 custodians</span><span class="sxs-lookup"><span data-stu-id="5511a-148">(Optional) Step 4: Place custodians on hold</span></span>

 <span data-ttu-id="5511a-p111">您已完成的 custodians 與您想要新增至您案例的資料來源之後，您可以選擇性地放置某些或您 custodians 上的所有保留。當您保留上放置 okay 時，對應至該使用者的內容會保留直到您放開 okay 從案例或直到您刪除保留。在某些情況下，可能會想要新增 custodians 案例而不將其置於保留。</span><span class="sxs-lookup"><span data-stu-id="5511a-p111">After you have finalized the custodians and data sources that you would like to add to your case, you can optionally place some or all of your custodians on hold. When you place a custodian on hold, the content mapped to that user is held until you release the custodian from the case or until you delete the hold. In some cases, you may want to add custodians to a case without placing them on hold.</span></span> 

<span data-ttu-id="5511a-152">若要放置在所選 custodians 與資料來源上的保留：</span><span class="sxs-lookup"><span data-stu-id="5511a-152">To place the selected custodians and data sources on hold:</span></span>

1. <span data-ttu-id="5511a-p112">確認 okay 選項，然後選取每個 okay 置於保留 checkox。一旦 okay 處於保留狀態，將會自動建立包含所有 custodial 來源 okay 保留原則。如果未選取這個選項，okay & 選取資料來源會新增至案例但不是會保留內容。</span><span class="sxs-lookup"><span data-stu-id="5511a-p112">Verify your custodian selections and select the checkox to place each custodian on hold.Once a custodian is placed on hold, a custodian hold policy containing all custodial sources will automatically be created. If the option is not checked, the custodian & selected data sources will be added to the case but the content will not be preserved.</span></span>

2. <span data-ttu-id="5511a-155">移至 [**保留**] 索引標籤並選取**Okay 保留原則**。</span><span class="sxs-lookup"><span data-stu-id="5511a-155">Go to the **Holds** tab and select the **Custodian Hold Policy**.</span></span> 

3. <span data-ttu-id="5511a-156">按一下 [**編輯**] 以檢視所有選取的 okay 資料來源。</span><span class="sxs-lookup"><span data-stu-id="5511a-156">Click **Edit** to view all the selected custodian data sources.</span></span>
