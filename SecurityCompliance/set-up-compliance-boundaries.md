---
title: 設定 Office 365 中電子文件探索調查的合規性界限
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/6/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 1b45c82f-26c8-44fb-9f3b-b45436fe2271
description: 若要建立 Office 365 組織內控制 eDiscovery 管理員可搜尋的使用者內容位置的邏輯界限使用規範界限。規範界限使用搜尋篩選 （也稱為的規範安全性篩選） 若要控制哪些信箱、 SharePoint 網站的權限，並可由特定使用者搜尋 OneDrive 帳戶。
ms.openlocfilehash: 822d228d64d2fd5432db327db98e8d7329c7d939
ms.sourcegitcommit: c166964fe14eec69139a2d3d9c10d2c40ab33f91
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/28/2018
ms.locfileid: "23258631"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations-in-office-365"></a><span data-ttu-id="f9004-104">設定 Office 365 中電子文件探索調查的合規性界限</span><span class="sxs-lookup"><span data-stu-id="f9004-104">Set up compliance boundaries for eDiscovery investigations in Office 365</span></span>

<span data-ttu-id="f9004-p102">規範界限建立 Office 365 組織內控制的使用者內容位置 （例如信箱、 SharePoint 網站及 OneDrive 帳戶） eDiscovery 管理員可搜尋的邏輯界限。此外，規範界限控制人員可以存取用來管理法律、 人力資源或其他調查組織中的 eDiscovery 案例。規範界限需要通常是必要必須遵守地理退敵軍和法規、 多重民公司及政府，通常會分成不同案件。在 Office 365，您符合規範界限說明執行時這些需求的內容搜尋與管理 eDiscovery 案例與調查。</span><span class="sxs-lookup"><span data-stu-id="f9004-p102">Compliance boundaries create logical boundaries within an Office 365 organization that control the user content locations (such as mailboxes, SharePoint sites, and OneDrive accounts) that eDiscovery managers can search. Additionally, compliance boundaries control who can access eDiscovery cases used to manage the legal, human resources, or other investigations within your organization. The need for compliance boundaries is often necessary for multi-nations corporations that have to respect geographical boarders and regulations, and for governments, which are often divided into different agencies. In Office 365, compliance boundaries help you meet these requirements when performing content searches and managing investigations with eDiscovery cases.</span></span>
  
<span data-ttu-id="f9004-109">我們用於範例會在下圖說明規範界限的運作方式。</span><span class="sxs-lookup"><span data-stu-id="f9004-109">We'll use the example in the following illustration to explain how compliance boundaries work.</span></span>
  
![規範界限組成搜尋權限篩選控制存取行政機關和系統管理員角色群組 eDisocovery 的情況下的控制存取](media/5c206cc8-a6eb-4d6b-a3a5-21e158791f9a.png)
  
<span data-ttu-id="f9004-p103">在本例中為 Contoso LTD 是 Office 365 組織所組成的兩個子公司 Fourth Coffee 和 Coho Winery。公司需要的 eDiscovery 管理員中及現場只能搜尋 Exchange 信箱、 OneDrive 帳戶及 SharePoint 網站中其機構。此外，eDiscovery 管理員及現場只能看到中的 eDiscovery 案例中其 agency，並只可以存取它們的成員的情況。以下是規範界限如何符合這些需求。</span><span class="sxs-lookup"><span data-stu-id="f9004-p103">In this example, Contoso LTD is an Office 365 organization that consists of two subsidiaries, Fourth Coffee and Coho Winery. The business requires that eDiscovery mangers and investigators can only search the Exchange mailboxes, OneDrive accounts, and SharePoint sites in their agency. Additionally, eDiscovery managers and investigators can only see eDiscovery cases in the in their agency, and they can only access the cases that they're a member of. Here's how compliance boundaries meet these requirements.</span></span>
  
- <span data-ttu-id="f9004-p104">篩選內容搜尋控制項中的功能 eDiscovery 管理員及現場可搜尋的內容位置搜尋的權限。這表示 eDiscovery 管理員及現場 Fourth Coffee 機構中的只能搜尋的內容位置中 Fourth Coffee 子公司。Coho Winery 子公司套用相同的限制。</span><span class="sxs-lookup"><span data-stu-id="f9004-p104">The search permissions filtering functionality in Content Search controls the content locations that eDiscovery managers and investigators can search. This means eDiscovery managers and investigators in the Fourth Coffee agency can only search content locations in the Fourth Coffee subsidiary. The same restriction applies to the Coho Winery subsidiary.</span></span>
    
    <span data-ttu-id="f9004-p105">角色群組控制可以看到 Office 365 安全性的 eDiscovery 案例&amp;規範中心。這表示 eDiscovery 管理員及現場只可以看到其機構中的 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="f9004-p105">Role groups control who can see the eDiscovery cases in the Office 365 Security &amp; Compliance Center. This means that eDiscovery managers and investigators can only see the eDiscovery cases in their agency.</span></span>
    
- <span data-ttu-id="f9004-p106">角色群組也會控制誰可將成員指派至 eDiscovery 案例。這表示 eDiscovery 管理員及現場可以只將成員指派給他們本身是成員的情況下。</span><span class="sxs-lookup"><span data-stu-id="f9004-p106">Role groups also control who can assign members to an eDiscovery case. This means eDiscovery managers and investigators can only assign members to cases that they themselves are a member of.</span></span>
    
<span data-ttu-id="f9004-122">以下是設定規範界限的程序：</span><span class="sxs-lookup"><span data-stu-id="f9004-122">Here's the process for setting up compliance boundaries:</span></span>
  
[<span data-ttu-id="f9004-123">步驟 1： 識別使用者屬性以定義您的行政機關</span><span class="sxs-lookup"><span data-stu-id="f9004-123">Step 1: Identify a user attribute to define your agencies</span></span>](#step-1-identify-a-user-attribute-to-define-your-agencies)

[<span data-ttu-id="f9004-124">步驟 2： 檔案要求 Microsoft 技術支援人員以同步處理至 OneDrive 帳戶的使用者屬性</span><span class="sxs-lookup"><span data-stu-id="f9004-124">Step 2: File a request with Microsoft Support to synchronize the user attribute to OneDrive accounts</span></span>](#step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts)

[<span data-ttu-id="f9004-125">步驟 3： 建立角色群組的每個機構</span><span class="sxs-lookup"><span data-stu-id="f9004-125">Step 3: Create a role group for each agency</span></span>](#step-3-create-a-role-group-for-each-agency)

[<span data-ttu-id="f9004-126">步驟 4： 建立搜尋權限篩選器來強制執行規範界限</span><span class="sxs-lookup"><span data-stu-id="f9004-126">Step 4: Create a search permissions filter to enforce the compliance boundary</span></span>](#step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[<span data-ttu-id="f9004-127">步驟 5： 建立內機構調查的 eDiscovery 案例</span><span class="sxs-lookup"><span data-stu-id="f9004-127">Step 5: Create an eDiscovery case for an intra-agency investigations</span></span>](#step-5-create-an-ediscovery-case-for-an-intra-agency-investigations)
  
## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a><span data-ttu-id="f9004-128">步驟 1： 識別使用者屬性以定義您的行政機關</span><span class="sxs-lookup"><span data-stu-id="f9004-128">Step 1: Identify a user attribute to define your agencies</span></span>

<span data-ttu-id="f9004-p107">第一個步驟是定義在行政機關選擇要使用的 Azure Active Directory 屬性。此屬性會用來建立限制 eDiscovery 搜尋的權限篩選來搜尋使用者對其指派特定的值為此屬性的內容位置的管理員。例如，假設 Contoso 決定要使用的**部門**屬性。Fourth Coffee 子公司中使用者的這個屬性的值就是`FourthCoffee`和 Coho Winery 子公司中使用者的值就是`CohoWinery`。在步驟 4 中，您將使用此`attribute:value`限制使用者對 (例如*部門： FourthCoffee* ) 內容 eDiscovery 管理員可搜尋的位置。</span><span class="sxs-lookup"><span data-stu-id="f9004-p107">The first step is to choose an Azure Active Directory attribute to use that will define your agencies. This attribute will be used to create the search permissions filter that limits an eDiscovery manager to search only the content locations of users who are assigned a specific value for this attribute. For example, let's say Contoso decides to use the **Department** attribute. The value for this attribute for users in the Fourth Coffee subsidiary would be  `FourthCoffee`  and the value for users in Coho Winery subsidiary would be `CohoWinery`. In Step 4, you'll use this  `attribute:value`  pair (for example,  *Department:FourthCoffee*  ) to limit the user content locations that eDiscovery managers can search.</span></span> 
  
<span data-ttu-id="f9004-134">以下是您可以使用規範界限的 Azure Active Directory 使用者屬性的清單：</span><span class="sxs-lookup"><span data-stu-id="f9004-134">Here's a list of Azure Active Directory user attributes that you can use for compliance boundaries:</span></span>
  
- <span data-ttu-id="f9004-135">Company</span><span class="sxs-lookup"><span data-stu-id="f9004-135">Company</span></span>
    
- <span data-ttu-id="f9004-136">CountryCode</span><span class="sxs-lookup"><span data-stu-id="f9004-136">CountryCode</span></span>
    
- <span data-ttu-id="f9004-137">CustomAttribute1-CustomAttribute15</span><span class="sxs-lookup"><span data-stu-id="f9004-137">CustomAttribute1 - CustomAttribute15</span></span>
    
- <span data-ttu-id="f9004-138">部門</span><span class="sxs-lookup"><span data-stu-id="f9004-138">Department</span></span>
    
- <span data-ttu-id="f9004-139">辦公室</span><span class="sxs-lookup"><span data-stu-id="f9004-139">Office</span></span>
    
<span data-ttu-id="f9004-140">雖然多個使用者屬性可供，特別是 Exchange 信箱，以上所列的屬性是目前支援的 OneDrive 的唯一錯誤。</span><span class="sxs-lookup"><span data-stu-id="f9004-140">Although more user attributes are available, particularly for Exchange mailboxes, the attributes listed above are the only ones currently supported by OneDrive.</span></span>
  
## <a name="step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts"></a><span data-ttu-id="f9004-141">步驟 2： 檔案要求 Microsoft 技術支援人員以同步處理至 OneDrive 帳戶的使用者屬性</span><span class="sxs-lookup"><span data-stu-id="f9004-141">Step 2: File a request with Microsoft Support to synchronize the user attribute to OneDrive accounts</span></span>

<span data-ttu-id="f9004-p108">下一步是檔案同步處理您選擇在步驟 1 中所有 OneDrive 帳戶在組織中的 Azure Active Directory 屬性與 Microsoft 支援要求。此同步處理發生屬性 （和其值） 後您在步驟 1 中選擇要對應至名為 SharePoint 中隱藏的 managed 屬性`ComplianceAttribute`。您將使用此屬性來建立步驟 4 中的 OneDrive 搜尋權限篩選。</span><span class="sxs-lookup"><span data-stu-id="f9004-p108">The next step is to file a request with Microsoft Support to synchronize the Azure Active Directory attribute that you chose in Step 1 to all OneDrive accounts in your organization. After this synchronization occurs, the attribute (and its value) that you chose in Step 1 will be mapped to a hidden managed property in SharePoint named  `ComplianceAttribute`. You'll use this attribute to create the search permissions filter for OneDrive in Step 4.</span></span>
  
<span data-ttu-id="f9004-145">當您要求提交至 Microsoft 支援包括下列資訊：</span><span class="sxs-lookup"><span data-stu-id="f9004-145">Include the following information when you submit the request to Microsoft support:</span></span>
  
- <span data-ttu-id="f9004-146">Office 365 組織的預設網域名稱</span><span class="sxs-lookup"><span data-stu-id="f9004-146">The default domain name of your Office 365 organization</span></span>
    
- <span data-ttu-id="f9004-147">Azure Active Directory 屬性 （從步驟 1) 的名稱</span><span class="sxs-lookup"><span data-stu-id="f9004-147">The name of the Azure Active Directory attribute (from Step 1)</span></span>
    
- <span data-ttu-id="f9004-p109">下列的標題或支援要求的用途說明:"啟用 OneDrive for 商務同步處理與 Azure Active Directory 的規範安全性篩選"。這有助於路由要求傳送到 Office 365 eDiscovery 工程小組人員實作要求。</span><span class="sxs-lookup"><span data-stu-id="f9004-p109">The following title or description of the purpose of the support request: "Enable OneDrive for Business Synchronization with Azure Active Directory for Compliance Security Filters". This will help route the request to the Office 365 eDiscovery engineering team who will implement the request.</span></span>
    
<span data-ttu-id="f9004-p110">工程變更並屬性已同步處理至 OneDrive 之後，Microsoft 技術支援人員會傳送給您在進行變更的組建編號與估計的部署日期。請注意部署程序通常會 4-6 週後支援將要求送出。</span><span class="sxs-lookup"><span data-stu-id="f9004-p110">After the engineering change is made and the attribute is synchronized to OneDrive, Microsoft Support will send you the build number that the change was made in and an estimated deployment date. Note that the deployment process usually takes 4-6 weeks after you submit the support request.</span></span>
  
 <span data-ttu-id="f9004-p111">**重要：** 您可以在部署變更之前完成步驟 3 到步驟 5。但是執行內容的搜尋不會傳回文件從之後部署變更指定直到搜尋權限篩選器中的 OneDrive 網站。</span><span class="sxs-lookup"><span data-stu-id="f9004-p111">**Important:** You can complete Step 3 through Step 5 before the change is deployed. But running content searches won't return documents from OneDrive sites specified in the search permissions filter until after the change is deployed.</span></span> 
  
## <a name="step-3-create-a-role-group-for-each-agency"></a><span data-ttu-id="f9004-154">步驟 3： 建立角色群組的每個機構</span><span class="sxs-lookup"><span data-stu-id="f9004-154">Step 3: Create a role group for each agency</span></span>

<span data-ttu-id="f9004-p112">下一步是建立 Office 365 安全性角色群組&amp;將您的行政機關最符合的規範中心。我們建議您建立新的角色群組的方式將複製的內建的 eDiscovery 管理員群組新增適當的成員，移除角色可能不會套用至您的需求。如需 eDiscovery 相關的角色的詳細資訊，請參閱[指派 Office 365 安全性 eDiscovery 權限&amp;規範中心](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="f9004-p112">The next step is to create the role groups in the Office 365 Security &amp; Compliance Center that will align with your agencies. We recommend that you create a new role group by copying the built-in eDiscovery Managers group, adding the appropriate members, and removing roles that may not be applicable to your needs. For more information about eDiscovery-related roles, see [Assign eDiscovery permissions in the Office‍ 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
  
<span data-ttu-id="f9004-158">若要建立角色群組，請前往 [安全性**權限**] 頁面上&amp;規範中心及中會使用規範界限和 eDiscovery 案例來管理調查每個機構建立每個小組角色群組。</span><span class="sxs-lookup"><span data-stu-id="f9004-158">To create the role groups, go to the **Permissions** page in the Security &amp; Compliance Center and create a role group for each team in each agency that will use compliance boundaries and eDiscovery cases to manage investigations.</span></span> 
  
<span data-ttu-id="f9004-159">使用 Contoso 規範界限案例，需要建立四個角色群組和適當的成員新增至每個。</span><span class="sxs-lookup"><span data-stu-id="f9004-159">Using the Contoso compliance boundaries scenario, four role groups need to be created and the appropriate members added to each one.</span></span>
  
- <span data-ttu-id="f9004-160">Fourth Coffee eDiscovery 管理員</span><span class="sxs-lookup"><span data-stu-id="f9004-160">Fourth Coffee eDiscovery Managers</span></span>
    
- <span data-ttu-id="f9004-161">Fourth Coffee 現場</span><span class="sxs-lookup"><span data-stu-id="f9004-161">Fourth Coffee Investigators</span></span>
    
- <span data-ttu-id="f9004-162">Coho Winery eDiscovery 管理員</span><span class="sxs-lookup"><span data-stu-id="f9004-162">Coho Winery eDiscovery Managers</span></span>
    
- <span data-ttu-id="f9004-163">Coho Winery 現場</span><span class="sxs-lookup"><span data-stu-id="f9004-163">Coho Winery Investigators</span></span>
    

  
## <a name="step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a><span data-ttu-id="f9004-164">步驟 4： 建立搜尋權限篩選器來強制執行規範界限</span><span class="sxs-lookup"><span data-stu-id="f9004-164">Step 4: Create a search permissions filter to enforce the compliance boundary</span></span>
<span data-ttu-id="f9004-165"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="f9004-165"></span></span>

<span data-ttu-id="f9004-p113">您已建立的每個機構的角色群組之後下, 一步是建立關聯至其特定機構的每個角色群組搜尋的權限篩選及定義的規範界限本身擷取。您需要建立一個搜尋權限篩選的每個機構。如需建立安全性權限篩選器的詳細資訊，請參閱 ＜ [Configure 權限的內容搜尋篩選](permissions-filtering-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="f9004-p113">After you've created role groups for each agency, the next step is to create the search permissions filters that associate each role group to its specific agency and defines the compliance boundary itself. You need to create one search permissions filter for each agency. For more information about creating security permissions filters, see [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md).</span></span>
  
<span data-ttu-id="f9004-169">用來建立規範界限用於搜尋的權限篩選語法如下所示。</span><span class="sxs-lookup"><span data-stu-id="f9004-169">Here's the syntax that's used to create a search permissions filter used for compliance boundaries.</span></span>

```
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<Compliance attribute from Step 1>  -eq '<AttributeVale> '", "Site_ComplianceAttribute  -eq <AttributeValue>' -or Site_Path -like <SharePointURL> *'" -Action <Action >
```
  
<span data-ttu-id="f9004-170">以下是在命令中的每個參數的描述：</span><span class="sxs-lookup"><span data-stu-id="f9004-170">Here's a description of each parameter in the command:</span></span>
  
-  <span data-ttu-id="f9004-p114">`FilterName`-指定篩選的名稱。將用於使用說明或識別篩選機構的名稱。</span><span class="sxs-lookup"><span data-stu-id="f9004-p114">`FilterName` - Specifies the name of the filter. Use a name that describes or identifies the agency that filter will be used in.</span></span> 
    
-  <span data-ttu-id="f9004-p115">`Users`-指定使用者或群組取得此篩選器套用至他們所執行的內容搜尋動作。規範界限此參數會指定您建立的篩選器機構的角色群組 （您在步驟 3 中建立）。請注意此多重值參數讓您可以包含一或多個以逗號分隔的角色群組。</span><span class="sxs-lookup"><span data-stu-id="f9004-p115">`Users` - Specifies the users or groups who get this filter applied to the Content Search actions they perform. For compliance boundaries, this parameter specifies the role groups (that you created in Step 3) in the agency that you're creating the filter for. Note this is a multi-value parameter so you can include one or more role groups, separated by commas.</span></span> 
    
-  <span data-ttu-id="f9004-p116">`Filters`-指定篩選條件的搜尋準則。規範界限中，您將會定義下列篩選器。每一個適用於使用者的內容位置。</span><span class="sxs-lookup"><span data-stu-id="f9004-p116">`Filters` - Specifies the search criteria for the filter. For the compliance boundaries, you will define the following filters. Each one applies to a user content location.</span></span> 
    
  -  <span data-ttu-id="f9004-p117">`Mailbox`-指定中所定義的角色群組的信箱`Users`參數可搜尋。規範界限*ComplianceAttribute*是您在步驟 1 中識別之相同屬性並*AttributeValue*指定機構。此篩選允許只在特定的機構 ； 搜尋之信箱的角色群組的成員例如， `"Mailbox_Department -eq 'FourthCoffee'"` 。</span><span class="sxs-lookup"><span data-stu-id="f9004-p117">`Mailbox` - Specifies the mailboxes that the role groups defined in the  `Users` parameter can search. For compliance boundaries,  *ComplianceAttribute*  is the same attribute that you identified in Step 1 and  *AttributeValue*  specifies the agency. This filter allow members of the role group to only search the mailboxes in a specific agency; for example,  `"Mailbox_Department -eq 'FourthCoffee'"` .</span></span> 
    
  -  <span data-ttu-id="f9004-p118">`Site`-指定角色群組中所定義的 OneDrive 帳戶`Users`參數可搜尋。使用 OneDrive 篩選器的實際字串`ComplianceAttribute`;這會對應至您在步驟 1 中識別和同步處理至 OneDrive 帳戶是您在步驟 2; 送出的支援要求的相同屬性 *AttributeValue*指定機構。此篩選允許只在特定的機構 ； 搜尋 OneDrive 帳戶的角色群組的成員例如， `"Site_ComplianceAttribute -eq 'FourthCoffee'"`。</span><span class="sxs-lookup"><span data-stu-id="f9004-p118">`Site` - Specifies the OneDrive accounts that the role groups defined in the  `Users` parameter can search. For the OneDrive filter, use the actual string  `ComplianceAttribute`; this will map to the same attribute that you identified in Step 1 and that's synchronized to OneDrive accounts as a result of the support request that you submitted in Step 2;  *AttributeValue*  specifies the agency. This filter allow members of the role group to only search the OneDrive accounts in a specific agency; for example,  `"Site_ComplianceAttribute -eq 'FourthCoffee'"`.</span></span>
    
  -  <span data-ttu-id="f9004-p119">`Site_Path`-指定角色群組中所定義的 SharePoint 網站`Users`參數可搜尋。*SharePointURL*指定網站中的角色群組的成員可以搜尋 ； 機構例如，`Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`</span><span class="sxs-lookup"><span data-stu-id="f9004-p119">`Site_Path` - Specifies the SharePoint sites that the role groups defined in the  `Users` parameter can search. The  *SharePointURL*  specifies the sites in the agency that members of the role group can search; for example,  `Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`</span></span>
    
-  <span data-ttu-id="f9004-p120">`Action`-指定篩選條件套用到規範搜尋動作的類型。例如，`-Action Search`就只會套用篩選器時中所定義的角色群組的成員`Users`參數執行內容的搜尋。在此例中匯出搜尋結果時不會套用篩選。規範界限使用`-Action All`所以篩選條件套用到所有搜尋動作。</span><span class="sxs-lookup"><span data-stu-id="f9004-p120">`Action` - Specifies the type of Compliance Search action that the filter is applied to. For example,  `-Action Search` would only apply the filter when members of the role groups defined in the  `Users` parameter runs a content search. In this case, the filter wouldn't be applied when exporting search results. For compliance boundaries, use  `-Action All` so the filter applies to all search actions.</span></span> 
    
    <span data-ttu-id="f9004-191">內容搜尋動作的清單，請參閱[設定權限的內容搜尋篩選](permissions-filtering-for-content-search.md#new-compliancesecurityfilter)"New-ComplianceSecurityFilter 」 一節。</span><span class="sxs-lookup"><span data-stu-id="f9004-191">For a list of the Content Search actions, see the "New-ComplianceSecurityFilter" section in [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md#new-compliancesecurityfilter).</span></span>
    
<span data-ttu-id="f9004-192">以下是範例會建立為支援 Contoso 規範界限案例的兩個搜尋權限篩選器。</span><span class="sxs-lookup"><span data-stu-id="f9004-192">Here are examples of the two search permissions filters that would be created to support the Contoso compliance boundaries scenario.</span></span>
  
 <span data-ttu-id="f9004-193">**Fourth Coffee**</span><span class="sxs-lookup"><span data-stu-id="f9004-193">**Fourth Coffee**</span></span>

```
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```
   
 <span data-ttu-id="f9004-194">**Coho Winery**</span><span class="sxs-lookup"><span data-stu-id="f9004-194">**Coho Winery**</span></span>

```
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-5-create-an-ediscovery-case-for-an-intra-agency-investigations"></a><span data-ttu-id="f9004-195">步驟 5： 建立內機構調查的 eDiscovery 案例</span><span class="sxs-lookup"><span data-stu-id="f9004-195">Step 5: Create an eDiscovery case for an intra-agency investigations</span></span>

<span data-ttu-id="f9004-p121">最後一個步驟是在 [安全性] 中建立新的 eDiscovery 案例&amp;規範中心然後新增角色群組 — 您在步驟 3 中建立 — 為大小寫的成員。這會產生使用規範界限的兩個重要特性：</span><span class="sxs-lookup"><span data-stu-id="f9004-p121">The final step is to create a new eDiscovery case in the Security &amp; Compliance Center and then add the role group—that you created in Step 3—as a member of the case. This results in two important characteristics of using compliance boundaries:</span></span>
  
- <span data-ttu-id="f9004-p122">僅新增至案例的角色群組的成員能看到並存取安全性案例&amp;規範中心。例如，如果案例的唯一成員 Fourth Coffee 現場角色群組，然後 Fourth Coffee eDiscovery 管理員角色群組 （或其他任何角色群組的成員） 的成員不會能夠請參閱或存取大小寫。</span><span class="sxs-lookup"><span data-stu-id="f9004-p122">Only members of the role group added to the case will be able to see and access the case in the Security &amp; Compliance Center. For example, if the Fourth Coffee Investigators role group is the only member of a case, then members of the Fourth Coffee eDiscovery Managers role group (or members of any other role group) won't be able to see or access the case.</span></span>
    
- <span data-ttu-id="f9004-200">指派給案例的角色群組的成員執行與案例相關聯的搜尋時所將只能夠搜尋其機構 （這由定義您在步驟 4 中建立的搜尋權限篩選。） 內的內容位置</span><span class="sxs-lookup"><span data-stu-id="f9004-200">When a member of the role group assigned to a case runs a search associated with the case, they will only be able to search the content locations within their agency (which is defined by the search permissions filter that you created in Step 4.)</span></span>


<span data-ttu-id="f9004-201">若要建立新案例並指派成員：</span><span class="sxs-lookup"><span data-stu-id="f9004-201">To create a new case and assign members:</span></span>
    
1. <span data-ttu-id="f9004-202">移至 [ **eDiscovery** ] 頁面上的 [安全性]&amp;規範中心並建立新的案例。</span><span class="sxs-lookup"><span data-stu-id="f9004-202">Go to the **eDiscovery** page in the Security &amp; Compliance Center and create a new case.</span></span> 
    
2. <span data-ttu-id="f9004-203">在清單中的 eDiscovery 的情況下，按一下您剛建立的大小寫的名稱。</span><span class="sxs-lookup"><span data-stu-id="f9004-203">In the list of eDiscovery cases, click the name of the case you just created.</span></span>
    
3. <span data-ttu-id="f9004-204">[**管理角色群組**、 [**管理此例中**彈出式] 頁面中按一下 [![新增圖示](media/8ee52980-254b-440b-99a2-18d068de62d3.gif)**新增]**。</span><span class="sxs-lookup"><span data-stu-id="f9004-204">In the **Manage this case** flyout page, under **Mange role groups**, click ![Add icon](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **Add**.</span></span>
    
    ![新增 eDiscovery 案例的成員身分的角色群組](media/f8b4b557-01b9-4388-85be-b5b5ab7c5629.png)
  
4. <span data-ttu-id="f9004-206">在角色群組的清單中，選取您在步驟 3 中建立的角色群組的其中一個並按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="f9004-206">In the list of role groups, select one of the role groups that you created in Step 3, and click **Add**.</span></span>
    
5. <span data-ttu-id="f9004-207">按一下 [**管理此例中**彈出式以儲存變更上的 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="f9004-207">Click **Save** on the **Manage this case** flyout to save the change.</span></span> 

## <a name="compliance-boundary-limitations"></a><span data-ttu-id="f9004-208">規範界限限制</span><span class="sxs-lookup"><span data-stu-id="f9004-208">Compliance boundary limitations</span></span>

<span data-ttu-id="f9004-209">管理 eDiscovery 案例和規範界限的使用調查時，請記住下列限制。</span><span class="sxs-lookup"><span data-stu-id="f9004-209">Keep the following limitations in mind when managing eDiscovery cases and investigations that use of compliance boundaries.</span></span>
  
- <span data-ttu-id="f9004-p123">當建立和執行內容搜尋時，您可以選取您機構外的內容位置。不過，搜尋權限篩選，因此將不會包含從這些位置內容搜尋結果中。</span><span class="sxs-lookup"><span data-stu-id="f9004-p123">When creating and running a Content Search, you can select content locations that are outside of your agency. However, because of the search permissions filter, content from those locations won't be included in the search results.</span></span>
    
- <span data-ttu-id="f9004-p124">規範界限不適用於保留 eDiscovery 案例中。這表示一個機構中的 eDiscovery 管理員可以將使用者放入保留不同機構。不過，規範界限將強制執行如果 eDiscovery 管理員會搜尋已處於保留狀態的使用者內容的位置。這表示 eDiscovery 管理員將不會是無法搜尋使用者的內容位置、 即使交易能夠將使用者放入保留。</span><span class="sxs-lookup"><span data-stu-id="f9004-p124">Compliance boundaries don't apply to holds in eDiscovery cases. That means an eDiscovery manager in one agency can place a user in a different agency on hold. However, the compliance boundary will be enforced if the eDiscovery manager searches the content locations of the user who was placed on hold. That means the eDiscovery manager won't be able search the user's content locations, even though they were able to place the user on hold.</span></span>
    
    <span data-ttu-id="f9004-216">此外，保留統計資料會僅適用於機構中的內容位置。</span><span class="sxs-lookup"><span data-stu-id="f9004-216">Additionally, hold statistics will only apply to content locations in the agency.</span></span>
    
- <span data-ttu-id="f9004-217">搜尋的權限篩選不會套用到 Exchange 公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="f9004-217">Search permissions filters aren't applied to Exchange public folders.</span></span>

## <a name="searching-and-exporting-sharepoint-content-in-multi-geo-environments"></a><span data-ttu-id="f9004-218">搜尋和匯出多個地理位置環境中的 SharePoint 內容</span><span class="sxs-lookup"><span data-stu-id="f9004-218">Searching and exporting SharePoint content in Multi-Geo environments</span></span>

<span data-ttu-id="f9004-219">搜尋的權限篩選也可讓您控制其中的內容會路由傳送的匯出與可以是哪一個資料中心的 SharePoint 網站和 OneDrive 帳戶搜尋[SharePoint 多重地理位置環境](https://go.microsoft.com/fwlink/?linkid=860840)中：</span><span class="sxs-lookup"><span data-stu-id="f9004-219">Search permissions filters also let you control where content is routed for export and which datacenters can be searched SharePoint sites and OneDrive accounts in a [SharePoint Multi-Geo environment](https://go.microsoft.com/fwlink/?linkid=860840):</span></span>
  
- <span data-ttu-id="f9004-p125">從特定的資料中心匯出搜尋結果。這表示您可以指定資料中心的位置搜尋結果將會從匯出。</span><span class="sxs-lookup"><span data-stu-id="f9004-p125">Export search results from a specific data center. This means that you can specify the data center location that search results will be exported from.</span></span>
    
- <span data-ttu-id="f9004-p126">路由 SharePoint 網站及 OneDrive 帳戶的搜尋衛星資料中心。這表示您可以指定能執行搜尋的資料中心位置。</span><span class="sxs-lookup"><span data-stu-id="f9004-p126">Route searches of SharePoint sites and OneDrive accounts to a satellite data center. This means you can specify the data center location where searches will be run.</span></span>
    
<span data-ttu-id="f9004-224">用於**Region**參數**新增 ComplianceSecurityFilter**或**組 ComplianceSecurityFilter** cmdlet 建立或變更匯出將轉接到哪一個資料中心。</span><span class="sxs-lookup"><span data-stu-id="f9004-224">Use the **Region** parameter for **New-ComplianceSecurityFilter** or **Set-ComplianceSecurityFilter** cmdlets to create or change which datacenter the export will be routed through.</span></span>
  
|<span data-ttu-id="f9004-225">**參數值**</span><span class="sxs-lookup"><span data-stu-id="f9004-225">**Parameter value**</span></span>|<span data-ttu-id="f9004-226">**資料中心位置**</span><span class="sxs-lookup"><span data-stu-id="f9004-226">**Data center location**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f9004-227">NAM</span><span class="sxs-lookup"><span data-stu-id="f9004-227">NAM</span></span>  <br/> |<span data-ttu-id="f9004-228">北美地區 （實際資料中心有實際在美國）</span><span class="sxs-lookup"><span data-stu-id="f9004-228">North American (actual data centers are in the US)</span></span>  <br/> |
|<span data-ttu-id="f9004-229">EUR</span><span class="sxs-lookup"><span data-stu-id="f9004-229">EUR</span></span>  <br/> |<span data-ttu-id="f9004-230">歐洲</span><span class="sxs-lookup"><span data-stu-id="f9004-230">Europe</span></span>  <br/> |
|<span data-ttu-id="f9004-231">APC</span><span class="sxs-lookup"><span data-stu-id="f9004-231">APC</span></span>  <br/> |<span data-ttu-id="f9004-232">亞太地區</span><span class="sxs-lookup"><span data-stu-id="f9004-232">Asia Pacific</span></span>  <br/> |
|<span data-ttu-id="f9004-233">CAN</span><span class="sxs-lookup"><span data-stu-id="f9004-233">CAN</span></span> <br/> |<span data-ttu-id="f9004-234">加拿大</span><span class="sxs-lookup"><span data-stu-id="f9004-234">Canada</span></span>
   
<span data-ttu-id="f9004-p127">同樣地，您可以使用下列**區域**的參數值的值來控制內容搜尋搜尋 SharePoint 及 OneDrive 位置時所執行的哪些資料中心。請注意，如下表也會顯示匯出將轉接到哪一個資料中心。</span><span class="sxs-lookup"><span data-stu-id="f9004-p127">Similarly, you can use the following values for the **Region** parameter values to control which data center that Content Searches will run in when searching SharePoint and OneDrive locations. Note that the following table also shows which data center exports will be routed through.</span></span> 
  
|<span data-ttu-id="f9004-237">**參數值**</span><span class="sxs-lookup"><span data-stu-id="f9004-237">**Parameter value**</span></span>|<span data-ttu-id="f9004-238">**資料中心匯出路由的位置**</span><span class="sxs-lookup"><span data-stu-id="f9004-238">**Data center routing locations for export**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f9004-239">NAM</span><span class="sxs-lookup"><span data-stu-id="f9004-239">NAM</span></span>  <br/> |<span data-ttu-id="f9004-240">US</span><span class="sxs-lookup"><span data-stu-id="f9004-240">US</span></span>  <br/> |
|<span data-ttu-id="f9004-241">EUR</span><span class="sxs-lookup"><span data-stu-id="f9004-241">EUR</span></span>  <br/> |<span data-ttu-id="f9004-242">歐洲</span><span class="sxs-lookup"><span data-stu-id="f9004-242">Europe</span></span>  <br/> |
|<span data-ttu-id="f9004-243">APC</span><span class="sxs-lookup"><span data-stu-id="f9004-243">APC</span></span>  <br/> |<span data-ttu-id="f9004-244">亞太地區</span><span class="sxs-lookup"><span data-stu-id="f9004-244">Asia Pacific</span></span>  <br/> |
|<span data-ttu-id="f9004-245">CAN</span><span class="sxs-lookup"><span data-stu-id="f9004-245">CAN</span></span>  <br/> |<span data-ttu-id="f9004-246">US</span><span class="sxs-lookup"><span data-stu-id="f9004-246">US</span></span>  <br/> |
|<span data-ttu-id="f9004-247">AUS</span><span class="sxs-lookup"><span data-stu-id="f9004-247">AUS</span></span>  <br/> |<span data-ttu-id="f9004-248">亞太地區</span><span class="sxs-lookup"><span data-stu-id="f9004-248">Asia Pacific</span></span>  <br/> |
|<span data-ttu-id="f9004-249">KOR</span><span class="sxs-lookup"><span data-stu-id="f9004-249">KOR</span></span>  <br/> |<span data-ttu-id="f9004-250">組織的預設資料中心</span><span class="sxs-lookup"><span data-stu-id="f9004-250">The organization's default data center</span></span>  <br/> |
|<span data-ttu-id="f9004-251">GBR</span><span class="sxs-lookup"><span data-stu-id="f9004-251">GBR</span></span>  <br/> |<span data-ttu-id="f9004-252">歐洲</span><span class="sxs-lookup"><span data-stu-id="f9004-252">Europe</span></span>  <br/> |
|<span data-ttu-id="f9004-253">JPN</span><span class="sxs-lookup"><span data-stu-id="f9004-253">JPN</span></span>  <br/> |<span data-ttu-id="f9004-254">亞太地區</span><span class="sxs-lookup"><span data-stu-id="f9004-254">Asia Pacific</span></span>  <br/> |
|<span data-ttu-id="f9004-255">尋找</span><span class="sxs-lookup"><span data-stu-id="f9004-255">IND</span></span>  <br/> |<span data-ttu-id="f9004-256">亞太地區</span><span class="sxs-lookup"><span data-stu-id="f9004-256">Asia Pacific</span></span>  <br/> |
|<span data-ttu-id="f9004-257">LAM</span><span class="sxs-lookup"><span data-stu-id="f9004-257">LAM</span></span>  <br/> |<span data-ttu-id="f9004-258">US</span><span class="sxs-lookup"><span data-stu-id="f9004-258">US</span></span>  <br/> |
   
 <span data-ttu-id="f9004-259">**附註：** 如果您沒有指定搜尋的權限篩選 Region 參數，搜尋結果都要匯出從最接近的資料中心。</span><span class="sxs-lookup"><span data-stu-id="f9004-259">**Note:** If you don't specify the Region parameter for a search permissions filter, then search results are exported from the closest data center.</span></span> 
  
<span data-ttu-id="f9004-p128">以下是範例使用 **-地區**參數建立規範界限搜尋 」 權限篩選器時。這是假設 Fourth Coffee 子公司位於 「 北美地區 」 與 Coho Winery 處於 Europe。</span><span class="sxs-lookup"><span data-stu-id="f9004-p128">Here are examples of using the **-Region** parameter when creating search permission filters for compliance boundaries. This assumes that the Fourth Coffee subsidiary is located in North America and that Coho Winery is in Europe.</span></span> 
  
```
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Department -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Department -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```
   
<span data-ttu-id="f9004-262">保留多個地理位置環境中的內容] 中搜尋和匯出 SharePoint 和 OneDrive 時，請謹記下列事項。</span><span class="sxs-lookup"><span data-stu-id="f9004-262">Keep the following things in mind when searching and exporting SharePoint and OneDrive content in multi-geo environments.</span></span>
  
- <span data-ttu-id="f9004-p129">**Region**參數不會控制 Exchange 信箱 ； 的搜尋搜尋信箱時將會搜尋所有的資料中心。若要限制可搜尋的哪些 Exchange 信箱的範圍，請使用**篩選**參數建立或變更搜尋權限篩選時。</span><span class="sxs-lookup"><span data-stu-id="f9004-p129">The **Region** parameter doesn't control searches of Exchange mailboxes; all data centers will be searched when you search mailboxes. To limit the scope of which Exchange mailboxes can be searched, use the **Filters** parameter when creating or changing a search permissions filter.</span></span> 
    
- <span data-ttu-id="f9004-265">如果時所需的 eDiscovery 來搜尋跨多個 SharePoint 區域的管理員，您需要搜尋權限篩選以指定的備用區域中可用的管理員建立不同的使用者帳戶該的 ediscovery （英文） 位置SharePoint 網站或 OneDrive 帳戶位於。</span><span class="sxs-lookup"><span data-stu-id="f9004-265">If it's necessary for an eDiscovery Manager to search across multiple SharePoint regions, you'll need to create a different user account for that eDiscovery manager that can be used in the search permissions filter to specify the alternate region where the SharePoint sites or OneDrive accounts are located.</span></span>
    
- <span data-ttu-id="f9004-p130">搜尋 SharePoint 和 OneDrive 中的內容、 時**Region**參數會指示搜尋以其中一個主要或附屬 eDiscovery 管理員會對執行 eDiscovery 調查的位置。如果 eDiscovery 管理員搜尋中搜尋的權限篩選指定的區域外部的 SharePoint 和 OneDrive 網站，會不傳回任何搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="f9004-p130">When searching for content in SharePoint and OneDrive, the **Region** parameter directs searches to either the main or satellite location where the eDiscovery manager will conduct eDiscovery investigations. If an eDiscovery manager searches SharePoint and OneDrive sites outside of the region that's specified in the search permissions filter, no search results will be returned.</span></span> 
    
- <span data-ttu-id="f9004-p131">從所有內容的位置 （包括 Exchange、 Skype Business、 SharePoint、 onedrive 及其他 Office 365 服務，您可以使用 「 內容搜尋工具來搜尋） 的內容匯出搜尋結果時, 將上傳至在 Azure 的儲存位置**區域**參數所指定的資料中心。這可幫助組織內規範保持不允許匯出控制框線之間的內容。如果搜尋權限篩選器中指定無區域，則內容已上傳至組織的預設區域。</span><span class="sxs-lookup"><span data-stu-id="f9004-p131">When exporting search results, content from all content locations (including Exchange, Skype for Business, SharePoint, OneDrive and other Office 365 services that you can search by using the Content Search tool) will be uploaded to the Azure storage location in the data center that's specified by the **Region** parameter. This helps organizations stay within compliance by not allowing content to be exported across controlled borders. If no region is specified in the search permissions filter, content is uploaded to the organization's default region.</span></span> 
    
- <span data-ttu-id="f9004-271">您可以編輯現有的搜尋權限篩選條件新增或變更區域中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="f9004-271">You can edit an existing search permissions filter to add or change the region by running the following command:</span></span>

    ```
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```
 
## <a name="frequently-asked-questions"></a><span data-ttu-id="f9004-272">常見問題集</span><span class="sxs-lookup"><span data-stu-id="f9004-272">Frequently asked questions</span></span>

 <span data-ttu-id="f9004-273">**誰可以建立及管理搜尋的權限篩選 （使用 New ComplianceSecurityFilter 和設定 ComplianceSecurityFilter cmdlet）？**</span><span class="sxs-lookup"><span data-stu-id="f9004-273">**Who can create and manage search permissions filters (using New-ComplianceSecurityFilter and Set-ComplianceSecurityFilter cmdlets )?**</span></span>
  
<span data-ttu-id="f9004-274">若要建立、 檢視及修改搜尋權限篩選，您必須是安全性組織管理角色群組的成員&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="f9004-274">To create, view and modify search permissions filters, you have to be a member of the Organization Management role group in the Security &amp; Compliance Center.</span></span>
  
 <span data-ttu-id="f9004-275">**如果 eDiscovery 管理員指派給多個角色群組跨多個行政機關，如何搜尋時一個機構中的內容或其他？**</span><span class="sxs-lookup"><span data-stu-id="f9004-275">**If an eDiscovery manager is assigned to more than one role group that spans multiple agencies, how do they search for content in one agency or the other?**</span></span>
  
<span data-ttu-id="f9004-p132">EDiscovery 管理員可以將參數加入至特定機構會限制搜尋其搜尋查詢。例如，如果組織具有指定**CustomAttribute10**屬性來區分行政機關，他們可以附加下列至其搜尋查詢，以搜尋特定的機構中信箱和 OneDrive 帳戶： `CustomAttribute10:<value> AND Site_ComplianceAttribute:<value>`。</span><span class="sxs-lookup"><span data-stu-id="f9004-p132">The eDiscovery manager can add parameters to their search query that will restrict the search to a specific agency. For example, if an organization has specified the **CustomAttribute10** property to differentiate agencies, they can append the following to their search query to search mailboxes and OneDrive accounts in a specific agency:  `CustomAttribute10:<value> AND Site_ComplianceAttribute:<value>`.</span></span>
  
 <span data-ttu-id="f9004-278">**如果會做為搜尋權限篩選器中的規範屬性的屬性值變更發生什麼情況？**</span><span class="sxs-lookup"><span data-stu-id="f9004-278">**What happens if the value of the attribute that's used as the compliance attribute in a search permissions filter is changed?**</span></span>
  
<span data-ttu-id="f9004-p133">延長最多可搜尋的權限篩選強制規範界限如果在篩選中使用的屬性值變更為 3 天。例如，Contoso 的案例中假設 Fourth Coffee 機構中的使用者會轉接到 Coho Winery 機構。因此，使用者物件上的**部門**屬性的值會從*FourthCoffee*變更為*CohoWinery* 。在此情況下，Fourth Coffee eDiscovery 及投資者會針對該使用者的設定屬性有所變更之後為 3 天取得搜尋結果。同樣地，需要最多為 3 天前 Coho Winery eDiscovery 管理員及現場將使用者取得搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="f9004-p133">It takes up to 3 days for a search permissions filter to enforce the compliance boundary if the value of the attribute that's used in the filter is changed. For example, in the Contoso scenario let's say that a user in the Fourth Coffee agency is transferred to the Coho Winery agency. As a result, the value of the **Department** attribute on the user object is changed from  *FourthCoffee*  to  *CohoWinery*  . In this situation, Fourth Coffee eDiscovery and investors will get search results for that user for up 3 days after the attribute is changed. Similarly, it will take up to 3 days before Coho Winery eDiscovery managers and investigators will get search results for the user.</span></span> 
  
 <span data-ttu-id="f9004-284">**EDiscovery 管理員可以看到兩個獨立的規範界限的內容吗？**</span><span class="sxs-lookup"><span data-stu-id="f9004-284">**Can an eDiscovery manager see content from two separate compliance boundaries?**</span></span>
  
<span data-ttu-id="f9004-p134">[是]。這可以完成將使用者新增至角色群組具有兩個行政機關看得到。</span><span class="sxs-lookup"><span data-stu-id="f9004-p134">Yes. This can be done by adding the user to role groups that have visibility to both agencies.</span></span>
  
 <span data-ttu-id="f9004-287">**搜尋的權限篩選 eDiscovery 案件保留、 Office 365 的保留原則或 DLP 吗？**</span><span class="sxs-lookup"><span data-stu-id="f9004-287">**Do search permissions filters work for eDiscovery case holds, Office 365 retention policies, or DLP?**</span></span>
  
<span data-ttu-id="f9004-288">否，未在此階段</span><span class="sxs-lookup"><span data-stu-id="f9004-288">No, not at this time</span></span>
  
 <span data-ttu-id="f9004-289">**如果我指定一個區域，其中會匯出內容，但我沒有該區域中的 SharePoint 組織的控制項，可以使用仍搜尋 SharePoint？**</span><span class="sxs-lookup"><span data-stu-id="f9004-289">**If I specify a region to control where content is exported, but I don't have a SharePoint organization in that region, can I still search SharePoint?**</span></span>
  
<span data-ttu-id="f9004-290">如果指定搜尋的權限篩選器中的區域不存在您組織中，將可搜尋的預設區域。</span><span class="sxs-lookup"><span data-stu-id="f9004-290">If the region specified in the search permissions filter doesn't exist in your organization, the default region will be searched.</span></span>
  
 <span data-ttu-id="f9004-291">**什麼是搜尋權限篩選器可以在組織中建立的最大數目？**</span><span class="sxs-lookup"><span data-stu-id="f9004-291">**What is the maximum number of search permissions filters that can be created in an organization?**</span></span>
  
<span data-ttu-id="f9004-p135">沒有可建立在組織中的搜尋權限篩選數目受限制。但如有 100 個以上的搜尋權限篩選將會影響搜尋效能。若要在組織中的搜尋權限篩選數目維持盡可能的小，建立的 Exchange、 SharePoint 及 OneDrive 的規則合併成單一搜尋權限篩選盡可能的篩選器。</span><span class="sxs-lookup"><span data-stu-id="f9004-p135">There is no limit to the number of search permissions filters that can be created in an organization. However, search performance will be impacted when there are more than 100 search permissions filters. To keep the number of search permissions filters in your organization as small as possible, create filters that combine rules for Exchange, SharePoint, and OneDrive into a single search permissions filter whenever possible.</span></span>