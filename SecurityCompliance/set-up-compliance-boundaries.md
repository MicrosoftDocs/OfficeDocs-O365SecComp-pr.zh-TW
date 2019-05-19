---
title: 設定 Office 365 中電子文件探索調查的合規性界限
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 1b45c82f-26c8-44fb-9f3b-b45436fe2271
description: 使用合規性界限來建立 Office 365 組織內控制電子文件探索管理員可搜尋的使用者內容位置的邏輯界限。 合規性界限使用搜尋權限篩選 （也稱為的法規安全性篩選器） 來控制哪些信箱、 SharePoint 網站，並可搜尋特定使用者的 OneDrive 帳戶。
ms.openlocfilehash: ab9fae4dcae04bc79c94f5a5138dfd56cc551414
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156575"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations-in-office-365"></a><span data-ttu-id="e4200-104">設定 Office 365 中電子文件探索調查的合規性界限</span><span class="sxs-lookup"><span data-stu-id="e4200-104">Set up compliance boundaries for eDiscovery investigations in Office 365</span></span>

<span data-ttu-id="e4200-105">合規性界限建立 Office 365 組織內控制的使用者內容位置 （例如信箱、 SharePoint 網站與 OneDrive 帳戶） 電子文件探索管理員可搜尋的邏輯界限。</span><span class="sxs-lookup"><span data-stu-id="e4200-105">Compliance boundaries create logical boundaries within an Office 365 organization that control the user content locations (such as mailboxes, SharePoint sites, and OneDrive accounts) that eDiscovery managers can search.</span></span> <span data-ttu-id="e4200-106">此外，合規性界限控制可以存取用來管理法律、 人力資源或組織內其他調查的 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="e4200-106">Additionally, compliance boundaries control who can access eDiscovery cases used to manage the legal, human resources, or other investigations within your organization.</span></span> <span data-ttu-id="e4200-107">合規性界限的需求，通常會需要必須遵守地理退敵軍與法規，多重民族企業與政府，通常可分為不同的行政機關。</span><span class="sxs-lookup"><span data-stu-id="e4200-107">The need for compliance boundaries is often necessary for multi-nations corporations that have to respect geographical boarders and regulations, and for governments, which are often divided into different agencies.</span></span> <span data-ttu-id="e4200-108">在 Office 365、 合規性界限協助您符合這些需求時執行內容搜尋和使用 eDiscovery 案例的管理調查。</span><span class="sxs-lookup"><span data-stu-id="e4200-108">In Office 365, compliance boundaries help you meet these requirements when performing content searches and managing investigations with eDiscovery cases.</span></span>
  
<span data-ttu-id="e4200-109">我們將使用下列圖例中的範例，說明合規性界限的運作方式。</span><span class="sxs-lookup"><span data-stu-id="e4200-109">We'll use the example in the following illustration to explain how compliance boundaries work.</span></span>
  
![合規性界限組成搜尋權限篩選器控制項存取行政機關和系統管理員角色群組 eDisocovery 的情況下，控制存取](media/5c206cc8-a6eb-4d6b-a3a5-21e158791f9a.png)
  
<span data-ttu-id="e4200-111">在這個範例中，Contoso LTD 是 Fourth Coffee 和 Coho Winery 的兩個子公司所組成的 Office 365 組織。</span><span class="sxs-lookup"><span data-stu-id="e4200-111">In this example, Contoso LTD is an Office 365 organization that consists of two subsidiaries, Fourth Coffee and Coho Winery.</span></span> <span data-ttu-id="e4200-112">業務需要，eDiscovery 管理員中和現場只能搜尋 Exchange 信箱、 OneDrive 帳戶，以及 SharePoint 網站中其機構。</span><span class="sxs-lookup"><span data-stu-id="e4200-112">The business requires that eDiscovery mangers and investigators can only search the Exchange mailboxes, OneDrive accounts, and SharePoint sites in their agency.</span></span> <span data-ttu-id="e4200-113">此外，eDiscovery 主管和現場僅能看到中的 eDiscovery 案例中其 agency，以及它們只能存取他們所隸屬的情況。</span><span class="sxs-lookup"><span data-stu-id="e4200-113">Additionally, eDiscovery managers and investigators can only see eDiscovery cases in the in their agency, and they can only access the cases that they're a member of.</span></span> <span data-ttu-id="e4200-114">以下是合規性界限如何符合這些需求。</span><span class="sxs-lookup"><span data-stu-id="e4200-114">Here's how compliance boundaries meet these requirements.</span></span>
  
- <span data-ttu-id="e4200-115">篩選內容搜尋控制項中的功能可以搜尋 eDiscovery 主管和現場的內容位置搜尋權限。</span><span class="sxs-lookup"><span data-stu-id="e4200-115">The search permissions filtering functionality in Content Search controls the content locations that eDiscovery managers and investigators can search.</span></span> <span data-ttu-id="e4200-116">這表示 eDiscovery 主管和現場 Fourth Coffee 機構中的只能搜尋內容位置中的 Fourth Coffee 子公司。</span><span class="sxs-lookup"><span data-stu-id="e4200-116">This means eDiscovery managers and investigators in the Fourth Coffee agency can only search content locations in the Fourth Coffee subsidiary.</span></span> <span data-ttu-id="e4200-117">Coho Winery 子公司套用相同的限制。</span><span class="sxs-lookup"><span data-stu-id="e4200-117">The same restriction applies to the Coho Winery subsidiary.</span></span>
    
    <span data-ttu-id="e4200-118">角色群組的控制可以看到安全性 & 合規性中心中的 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="e4200-118">Role groups control who can see the eDiscovery cases in the Security & Compliance Center.</span></span> <span data-ttu-id="e4200-119">這表示，eDiscovery 主管和現場只能看到其機構中的 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="e4200-119">This means that eDiscovery managers and investigators can only see the eDiscovery cases in their agency.</span></span>
    
- <span data-ttu-id="e4200-120">角色群組也會控制誰可以指派至 eDiscovery 案例的成員。</span><span class="sxs-lookup"><span data-stu-id="e4200-120">Role groups also control who can assign members to an eDiscovery case.</span></span> <span data-ttu-id="e4200-121">這表示 eDiscovery 主管和現場可以只將成員指派給他們彼此之間是成員的情況下。</span><span class="sxs-lookup"><span data-stu-id="e4200-121">This means eDiscovery managers and investigators can only assign members to cases that they themselves are a member of.</span></span>
    
<span data-ttu-id="e4200-122">以下是設定合規性界限的程序：</span><span class="sxs-lookup"><span data-stu-id="e4200-122">Here's the process for setting up compliance boundaries:</span></span>
  
[<span data-ttu-id="e4200-123">步驟 1： 識別來定義貴機構使用者屬性</span><span class="sxs-lookup"><span data-stu-id="e4200-123">Step 1: Identify a user attribute to define your agencies</span></span>](#step-1-identify-a-user-attribute-to-define-your-agencies)

[<span data-ttu-id="e4200-124">步驟 2： 將歸檔與 Microsoft 支援服務以同步處理至 OneDrive 帳戶的使用者屬性</span><span class="sxs-lookup"><span data-stu-id="e4200-124">Step 2: File a request with Microsoft Support to synchronize the user attribute to OneDrive accounts</span></span>](#step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts)

[<span data-ttu-id="e4200-125">步驟 3： 建立每個代理程式的角色群組</span><span class="sxs-lookup"><span data-stu-id="e4200-125">Step 3: Create a role group for each agency</span></span>](#step-3-create-a-role-group-for-each-agency)

[<span data-ttu-id="e4200-126">步驟 4： 建立搜尋權限篩選器來強制執行的合規性界限</span><span class="sxs-lookup"><span data-stu-id="e4200-126">Step 4: Create a search permissions filter to enforce the compliance boundary</span></span>](#step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[<span data-ttu-id="e4200-127">步驟 5： 建立內機構調查的 eDiscovery 案例</span><span class="sxs-lookup"><span data-stu-id="e4200-127">Step 5: Create an eDiscovery case for an intra-agency investigations</span></span>](#step-5-create-an-ediscovery-case-for-an-intra-agency-investigations)
  
## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a><span data-ttu-id="e4200-128">步驟 1： 識別來定義貴機構使用者屬性</span><span class="sxs-lookup"><span data-stu-id="e4200-128">Step 1: Identify a user attribute to define your agencies</span></span>

<span data-ttu-id="e4200-129">第一個步驟是選擇要使用的 Azure Active Directory 屬性將會定義您行政機關。</span><span class="sxs-lookup"><span data-stu-id="e4200-129">The first step is to choose an Azure Active Directory attribute to use that will define your agencies.</span></span> <span data-ttu-id="e4200-130">此屬性會用來建立限制 eDiscovery 搜尋的權限篩選來搜尋使用者獲指派此屬性的特定值的內容位置的管理員。</span><span class="sxs-lookup"><span data-stu-id="e4200-130">This attribute will be used to create the search permissions filter that limits an eDiscovery manager to search only the content locations of users who are assigned a specific value for this attribute.</span></span> <span data-ttu-id="e4200-131">例如，假設 Contoso 決定要使用的**部門**屬性。</span><span class="sxs-lookup"><span data-stu-id="e4200-131">For example, let's say Contoso decides to use the **Department** attribute.</span></span> <span data-ttu-id="e4200-132">為 Fourth Coffee 子公司中使用者的此屬性的值會是`FourthCoffee`和 Coho Winery 子公司中的使用者的值會是`CohoWinery`。</span><span class="sxs-lookup"><span data-stu-id="e4200-132">The value for this attribute for users in the Fourth Coffee subsidiary would be  `FourthCoffee`  and the value for users in Coho Winery subsidiary would be `CohoWinery`.</span></span> <span data-ttu-id="e4200-133">在 [步驟 4 中，您將使用此`attribute:value`以限制使用者對 (例如，*部門： FourthCoffee* ) 內容電子文件探索管理員可搜尋的位置。</span><span class="sxs-lookup"><span data-stu-id="e4200-133">In Step 4, you'll use this  `attribute:value`  pair (for example,  *Department:FourthCoffee*  ) to limit the user content locations that eDiscovery managers can search.</span></span> 
  
<span data-ttu-id="e4200-134">以下是您可以使用合規性界限的 Azure Active Directory 使用者屬性的清單：</span><span class="sxs-lookup"><span data-stu-id="e4200-134">Here's a list of Azure Active Directory user attributes that you can use for compliance boundaries:</span></span>
  
- <span data-ttu-id="e4200-135">Company</span><span class="sxs-lookup"><span data-stu-id="e4200-135">Company</span></span>
    
- <span data-ttu-id="e4200-136">CustomAttribute1-CustomAttribute15</span><span class="sxs-lookup"><span data-stu-id="e4200-136">CustomAttribute1 - CustomAttribute15</span></span>
    
- <span data-ttu-id="e4200-137">部門</span><span class="sxs-lookup"><span data-stu-id="e4200-137">Department</span></span>
    
- <span data-ttu-id="e4200-138">辦公室</span><span class="sxs-lookup"><span data-stu-id="e4200-138">Office</span></span>

- <span data-ttu-id="e4200-139">C （兩個字母國碼/地區碼）</span><span class="sxs-lookup"><span data-stu-id="e4200-139">C (Two letter Country Code)</span></span>
    
<span data-ttu-id="e4200-140">雖然多個使用者屬性可用，尤其是針對 Exchange 信箱，上面所列的屬性是目前支援 OneDrive 是唯一的。</span><span class="sxs-lookup"><span data-stu-id="e4200-140">Although more user attributes are available, particularly for Exchange mailboxes, the attributes listed above are the only ones currently supported by OneDrive.</span></span>
  
## <a name="step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts"></a><span data-ttu-id="e4200-141">步驟 2： 將歸檔與 Microsoft 支援服務以同步處理至 OneDrive 帳戶的使用者屬性</span><span class="sxs-lookup"><span data-stu-id="e4200-141">Step 2: File a request with Microsoft Support to synchronize the user attribute to OneDrive accounts</span></span>

<span data-ttu-id="e4200-142">下一步是檔案同步處理您選擇在步驟 1 中所有 OneDrive 帳戶中組織的 Azure Active Directory 屬性與 Microsoft 支援服務要求。</span><span class="sxs-lookup"><span data-stu-id="e4200-142">The next step is to file a request with Microsoft Support to synchronize the Azure Active Directory attribute that you chose in Step 1 to all OneDrive accounts in your organization.</span></span> <span data-ttu-id="e4200-143">此同步處理發生時，屬性 （和其值） 後您選擇在步驟 1 中將會對應至名為 SharePoint 中的隱藏 managed 屬性`ComplianceAttribute`。</span><span class="sxs-lookup"><span data-stu-id="e4200-143">After this synchronization occurs, the attribute (and its value) that you chose in Step 1 will be mapped to a hidden managed property in SharePoint named  `ComplianceAttribute`.</span></span> <span data-ttu-id="e4200-144">您將使用這個屬性來建立搜尋權限篩選器的步驟 4 中的 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="e4200-144">You'll use this attribute to create the search permissions filter for OneDrive in Step 4.</span></span>
  
<span data-ttu-id="e4200-145">當您將要求提交給 Microsoft 支援服務時，請包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="e4200-145">Include the following information when you submit the request to Microsoft support:</span></span>
  
- <span data-ttu-id="e4200-146">Office 365 組織的預設網域名稱</span><span class="sxs-lookup"><span data-stu-id="e4200-146">The default domain name of your Office 365 organization</span></span>
    
- <span data-ttu-id="e4200-147">Azure Active Directory 屬性 （從步驟 1) 的名稱</span><span class="sxs-lookup"><span data-stu-id="e4200-147">The name of the Azure Active Directory attribute (from Step 1)</span></span>
    
- <span data-ttu-id="e4200-148">下列的標題或支援要求的用途的描述: 「 啟用 OneDrive 的商務同步處理與 Azure Active Directory 的法規安全性篩選器 」。</span><span class="sxs-lookup"><span data-stu-id="e4200-148">The following title or description of the purpose of the support request: "Enable OneDrive for Business Synchronization with Azure Active Directory for Compliance Security Filters".</span></span> <span data-ttu-id="e4200-149">這有助於將要求路由傳送至 Office 365 電子文件探索工程團隊會實作要求者。</span><span class="sxs-lookup"><span data-stu-id="e4200-149">This will help route the request to the Office 365 eDiscovery engineering team who will implement the request.</span></span>
    
<span data-ttu-id="e4200-150">工程變更，而且屬性同步至 OneDrive 之後，Microsoft 支援服務會傳送給您在進行變更的組建編號和預估的部署日期。</span><span class="sxs-lookup"><span data-stu-id="e4200-150">After the engineering change is made and the attribute is synchronized to OneDrive, Microsoft Support will send you the build number that the change was made in and an estimated deployment date.</span></span> <span data-ttu-id="e4200-151">請注意，在部署程序通常需要 4-6 週後您提交支援要求。</span><span class="sxs-lookup"><span data-stu-id="e4200-151">Note that the deployment process usually takes 4-6 weeks after you submit the support request.</span></span>
  
 <span data-ttu-id="e4200-152">**重要：** 在部署變更之前，您可以完成步驟 3 到步驟 5。</span><span class="sxs-lookup"><span data-stu-id="e4200-152">**Important:** You can complete Step 3 through Step 5 before the change is deployed.</span></span> <span data-ttu-id="e4200-153">但執行內容搜尋不會傳回文件從 OneDrive 網站部署變更之後，直到搜尋權限篩選器中指定。</span><span class="sxs-lookup"><span data-stu-id="e4200-153">But running content searches won't return documents from OneDrive sites specified in the search permissions filter until after the change is deployed.</span></span> 
  
## <a name="step-3-create-a-role-group-for-each-agency"></a><span data-ttu-id="e4200-154">步驟 3： 建立每個代理程式的角色群組</span><span class="sxs-lookup"><span data-stu-id="e4200-154">Step 3: Create a role group for each agency</span></span>

<span data-ttu-id="e4200-155">下一步是建立安全性 & 會符合貴機構的合規性中心中的角色群組。</span><span class="sxs-lookup"><span data-stu-id="e4200-155">The next step is to create the role groups in the Security & Compliance Center that will align with your agencies.</span></span> <span data-ttu-id="e4200-156">我們建議您複製內建的 eDiscovery Managers 群組、 新增適當的成員，以及移除角色，可能無法適用於您的需求來建立新的角色群組。</span><span class="sxs-lookup"><span data-stu-id="e4200-156">We recommend that you create a new role group by copying the built-in eDiscovery Managers group, adding the appropriate members, and removing roles that may not be applicable to your needs.</span></span> <span data-ttu-id="e4200-157">如需 eDiscovery 相關角色的詳細資訊，請參閱[指派 Office 365 安全性 & 合規性中心中的 eDiscovery 權限](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="e4200-157">For more information about eDiscovery-related roles, see [Assign eDiscovery permissions in the Office‍ 365 Security & Compliance Center](assign-ediscovery-permissions.md).</span></span>
  
<span data-ttu-id="e4200-158">若要建立的角色群組，移至安全性 & 合規性中心中的 [**權限**] 頁面上，將會使用合規性界限和 eDiscovery 案例來管理調查每個代理程式中建立的每個小組的角色群組。</span><span class="sxs-lookup"><span data-stu-id="e4200-158">To create the role groups, go to the **Permissions** page in the Security & Compliance Center and create a role group for each team in each agency that will use compliance boundaries and eDiscovery cases to manage investigations.</span></span> 
  
<span data-ttu-id="e4200-159">使用 Contoso 合規性界限案例中，需要建立四個角色群組，並適當成員新增至每個。</span><span class="sxs-lookup"><span data-stu-id="e4200-159">Using the Contoso compliance boundaries scenario, four role groups need to be created and the appropriate members added to each one.</span></span>
  
- <span data-ttu-id="e4200-160">Fourth Coffee eDiscovery 管理員</span><span class="sxs-lookup"><span data-stu-id="e4200-160">Fourth Coffee eDiscovery Managers</span></span>
    
- <span data-ttu-id="e4200-161">Fourth Coffee 現場</span><span class="sxs-lookup"><span data-stu-id="e4200-161">Fourth Coffee Investigators</span></span>
    
- <span data-ttu-id="e4200-162">Coho Winery eDiscovery 管理員</span><span class="sxs-lookup"><span data-stu-id="e4200-162">Coho Winery eDiscovery Managers</span></span>
    
- <span data-ttu-id="e4200-163">Coho Winery 現場</span><span class="sxs-lookup"><span data-stu-id="e4200-163">Coho Winery Investigators</span></span>
    

  
## <a name="step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a><span data-ttu-id="e4200-164">步驟 4： 建立搜尋權限篩選器來強制執行的合規性界限</span><span class="sxs-lookup"><span data-stu-id="e4200-164">Step 4: Create a search permissions filter to enforce the compliance boundary</span></span>

<span data-ttu-id="e4200-165">您已建立的每個代理程式的角色群組之後下, 一步是建立關聯至其特定的機構每個角色群組的搜尋權限篩選器，並定義本身的合規性界限。</span><span class="sxs-lookup"><span data-stu-id="e4200-165">After you've created role groups for each agency, the next step is to create the search permissions filters that associate each role group to its specific agency and defines the compliance boundary itself.</span></span> <span data-ttu-id="e4200-166">您需要建立一個每個代理程式的搜尋權限篩選器。</span><span class="sxs-lookup"><span data-stu-id="e4200-166">You need to create one search permissions filter for each agency.</span></span> <span data-ttu-id="e4200-167">如需建立安全性權限篩選器的詳細資訊，請參閱 <<c0>設定的權限篩選內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="e4200-167">For more information about creating security permissions filters, see [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md).</span></span>
  
<span data-ttu-id="e4200-168">以下是用來建立搜尋權限的篩選器，用於合規性界限的語法。</span><span class="sxs-lookup"><span data-stu-id="e4200-168">Here's the syntax that's used to create a search permissions filter used for compliance boundaries.</span></span>

```
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<Compliance attribute from Step 1>  -eq '<AttributeVale> '", "Site_ComplianceAttribute  -eq <AttributeValue>' -or Site_Path -like <SharePointURL> *'" -Action <Action >
```
  
<span data-ttu-id="e4200-169">以下是在命令中每個參數的描述：</span><span class="sxs-lookup"><span data-stu-id="e4200-169">Here's a description of each parameter in the command:</span></span>
  
-  <span data-ttu-id="e4200-170">`FilterName`對指定的篩選器的名稱。</span><span class="sxs-lookup"><span data-stu-id="e4200-170">`FilterName` - Specifies the name of the filter.</span></span> <span data-ttu-id="e4200-171">將用於使用說明或識別篩選機構的名稱。</span><span class="sxs-lookup"><span data-stu-id="e4200-171">Use a name that describes or identifies the agency that filter will be used in.</span></span> 
    
-  <span data-ttu-id="e4200-172">`Users`-指定使用者或群組，取得此篩選器套用至他們所執行的內容搜尋動作。</span><span class="sxs-lookup"><span data-stu-id="e4200-172">`Users` - Specifies the users or groups who get this filter applied to the Content Search actions they perform.</span></span> <span data-ttu-id="e4200-173">合規性界限，此參數會指定您要建立的篩選器代理的角色群組 （您在步驟 3 中建立）。</span><span class="sxs-lookup"><span data-stu-id="e4200-173">For compliance boundaries, this parameter specifies the role groups (that you created in Step 3) in the agency that you're creating the filter for.</span></span> <span data-ttu-id="e4200-174">請注意這是多重值參數，因此您可以包含一或多個角色群組，以逗號隔開。</span><span class="sxs-lookup"><span data-stu-id="e4200-174">Note this is a multi-value parameter so you can include one or more role groups, separated by commas.</span></span> 
    
-  <span data-ttu-id="e4200-175">`Filters`-指定篩選的搜尋準則。</span><span class="sxs-lookup"><span data-stu-id="e4200-175">`Filters` - Specifies the search criteria for the filter.</span></span> <span data-ttu-id="e4200-176">合規性界限，您將定義下列篩選器。</span><span class="sxs-lookup"><span data-stu-id="e4200-176">For the compliance boundaries, you will define the following filters.</span></span> <span data-ttu-id="e4200-177">每個會套用到使用者的內容位置。</span><span class="sxs-lookup"><span data-stu-id="e4200-177">Each one applies to a user content location.</span></span> 
    
  -  <span data-ttu-id="e4200-178">`Mailbox`對指定的角色群組定義中的信箱`Users`參數可以搜尋。</span><span class="sxs-lookup"><span data-stu-id="e4200-178">`Mailbox` - Specifies the mailboxes that the role groups defined in the  `Users` parameter can search.</span></span> <span data-ttu-id="e4200-179">合規性界限*ComplianceAttribute*是您在步驟 1 中識別之相同屬性， *AttributeValue*指定機構。</span><span class="sxs-lookup"><span data-stu-id="e4200-179">For compliance boundaries,  *ComplianceAttribute*  is the same attribute that you identified in Step 1 and  *AttributeValue*  specifies the agency.</span></span> <span data-ttu-id="e4200-180">此篩選允許只搜尋特定的機構; 中的 [信箱角色群組的成員例如， `"Mailbox_Department -eq 'FourthCoffee'"` 。</span><span class="sxs-lookup"><span data-stu-id="e4200-180">This filter allow members of the role group to only search the mailboxes in a specific agency; for example,  `"Mailbox_Department -eq 'FourthCoffee'"` .</span></span> 
    
  -  <span data-ttu-id="e4200-181">`Site`對指定的角色群組定義中的 OneDrive 帳戶`Users`參數可以搜尋。</span><span class="sxs-lookup"><span data-stu-id="e4200-181">`Site` - Specifies the OneDrive accounts that the role groups defined in the  `Users` parameter can search.</span></span> <span data-ttu-id="e4200-182">OneDrive 篩選時，使用實際字串`ComplianceAttribute`;這會對應至相同的屬性，您在步驟 1 中識別的同步處理至您在步驟 2; 提交支援要求因為 OneDrive 帳戶 *AttributeValue*指定機構。</span><span class="sxs-lookup"><span data-stu-id="e4200-182">For the OneDrive filter, use the actual string  `ComplianceAttribute`; this will map to the same attribute that you identified in Step 1 and that's synchronized to OneDrive accounts as a result of the support request that you submitted in Step 2;  *AttributeValue*  specifies the agency.</span></span> <span data-ttu-id="e4200-183">此篩選器可讓角色群組，以只搜尋特定的機構; 中的 [OneDrive 帳戶的成員例如， `"Site_ComplianceAttribute -eq 'FourthCoffee'"`。</span><span class="sxs-lookup"><span data-stu-id="e4200-183">This filter allow members of the role group to only search the OneDrive accounts in a specific agency; for example,  `"Site_ComplianceAttribute -eq 'FourthCoffee'"`.</span></span>
    
  -  <span data-ttu-id="e4200-184">`Site_Path`對指定的角色群組定義中的 SharePoint 網站`Users`參數可以搜尋。</span><span class="sxs-lookup"><span data-stu-id="e4200-184">`Site_Path` - Specifies the SharePoint sites that the role groups defined in the  `Users` parameter can search.</span></span> <span data-ttu-id="e4200-185">*SharePointURL*指定網站中的角色群組的成員可以搜尋; 機構例如，`"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`</span><span class="sxs-lookup"><span data-stu-id="e4200-185">The  *SharePointURL*  specifies the sites in the agency that members of the role group can search; for example,  `"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`</span></span>
    
-  <span data-ttu-id="e4200-186">`Action`對指定篩選套用至符合性搜尋動作的類型。</span><span class="sxs-lookup"><span data-stu-id="e4200-186">`Action` - Specifies the type of Compliance Search action that the filter is applied to.</span></span> <span data-ttu-id="e4200-187">例如，`-Action Search`中定義的角色群組的成員時，則只會套用篩選器`Users`參數執行內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="e4200-187">For example,  `-Action Search` would only apply the filter when members of the role groups defined in the  `Users` parameter runs a content search.</span></span> <span data-ttu-id="e4200-188">在此例中匯出搜尋結果時，就不會套用篩選器。</span><span class="sxs-lookup"><span data-stu-id="e4200-188">In this case, the filter wouldn't be applied when exporting search results.</span></span> <span data-ttu-id="e4200-189">合規性界限，使用`-Action All`讓篩選套用至所有的搜尋動作。</span><span class="sxs-lookup"><span data-stu-id="e4200-189">For compliance boundaries, use  `-Action All` so the filter applies to all search actions.</span></span> 
    
    <span data-ttu-id="e4200-190">如需內容搜尋動作的清單，請參閱 <<c0>設定的權限篩選內容搜尋中的 「 New-compliancesecurityfilter 」 一節。</span><span class="sxs-lookup"><span data-stu-id="e4200-190">For a list of the Content Search actions, see the "New-ComplianceSecurityFilter" section in [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md#new-compliancesecurityfilter).</span></span>
    
<span data-ttu-id="e4200-191">以下是會建立為支援 contoso 公司的合規性界限案例的兩個搜尋的權限篩選器的範例。</span><span class="sxs-lookup"><span data-stu-id="e4200-191">Here are examples of the two search permissions filters that would be created to support the Contoso compliance boundaries scenario.</span></span>
  
 <span data-ttu-id="e4200-192">**Fourth Coffee**</span><span class="sxs-lookup"><span data-stu-id="e4200-192">**Fourth Coffee**</span></span>

```
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```
   
 <span data-ttu-id="e4200-193">**Coho Winery**</span><span class="sxs-lookup"><span data-stu-id="e4200-193">**Coho Winery**</span></span>

```
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-5-create-an-ediscovery-case-for-an-intra-agency-investigations"></a><span data-ttu-id="e4200-194">步驟 5： 建立內機構調查的 eDiscovery 案例</span><span class="sxs-lookup"><span data-stu-id="e4200-194">Step 5: Create an eDiscovery case for an intra-agency investigations</span></span>

<span data-ttu-id="e4200-195">最後一個步驟是在安全性 & 合規性中心中建立新的 eDiscovery 案例，然後將新增角色群組，您在步驟 3 中建立 — 為案例的成員。</span><span class="sxs-lookup"><span data-stu-id="e4200-195">The final step is to create a new eDiscovery case in the Security & Compliance Center and then add the role group—that you created in Step 3—as a member of the case.</span></span> <span data-ttu-id="e4200-196">這會導致使用合規性界限的兩個重要特性：</span><span class="sxs-lookup"><span data-stu-id="e4200-196">This results in two important characteristics of using compliance boundaries:</span></span>
  
- <span data-ttu-id="e4200-197">只有新增至案例的角色群組的成員能夠查看及存取安全性 & 合規性中心中的情況。</span><span class="sxs-lookup"><span data-stu-id="e4200-197">Only members of the role group added to the case will be able to see and access the case in the Security & Compliance Center.</span></span> <span data-ttu-id="e4200-198">例如，如果 Fourth Coffee 現場角色群組是案例的唯一成員，然後 Fourth Coffee eDiscovery 管理員角色群組 （或任何其他角色群組的成員） 的成員無法看到或存取這種情況。</span><span class="sxs-lookup"><span data-stu-id="e4200-198">For example, if the Fourth Coffee Investigators role group is the only member of a case, then members of the Fourth Coffee eDiscovery Managers role group (or members of any other role group) won't be able to see or access the case.</span></span>
    
- <span data-ttu-id="e4200-199">當案例指派給角色群組的成員執行與案例相關聯的搜尋時，他們將只能搜尋其機構 （這由所定義您在步驟 4 中建立搜尋權限篩選器。） 內的內容位置</span><span class="sxs-lookup"><span data-stu-id="e4200-199">When a member of the role group assigned to a case runs a search associated with the case, they will only be able to search the content locations within their agency (which is defined by the search permissions filter that you created in Step 4.)</span></span>


<span data-ttu-id="e4200-200">若要建立新的案例，並指派成員：</span><span class="sxs-lookup"><span data-stu-id="e4200-200">To create a new case and assign members:</span></span>
    
1. <span data-ttu-id="e4200-201">移至安全性 & 合規性中心中的 [ **eDiscovery** ] 頁面上，並建立新的案例。</span><span class="sxs-lookup"><span data-stu-id="e4200-201">Go to the **eDiscovery** page in the Security & Compliance Center and create a new case.</span></span> 
    
2. <span data-ttu-id="e4200-202">在清單中的 eDiscovery 案例，按一下您剛才建立的大小寫名稱。</span><span class="sxs-lookup"><span data-stu-id="e4200-202">In the list of eDiscovery cases, click the name of the case you just created.</span></span>
    
3. <span data-ttu-id="e4200-203">在 [**管理此情況下**彈出式視窗] 頁面的 [**管理角色群組**，按一下 [![加入圖示](media/8ee52980-254b-440b-99a2-18d068de62d3.gif)**新增**。</span><span class="sxs-lookup"><span data-stu-id="e4200-203">In the **Manage this case** flyout page, under **Mange role groups**, click ![Add icon](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **Add**.</span></span>
    
    ![將角色群組新增為 eDiscovery 案例成員](media/f8b4b557-01b9-4388-85be-b5b5ab7c5629.png)
  
4. <span data-ttu-id="e4200-205">在角色群組的清單中，選取下列其中一個您在步驟 3 中建立的角色群組，並按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="e4200-205">In the list of role groups, select one of the role groups that you created in Step 3, and click **Add**.</span></span>
    
5. <span data-ttu-id="e4200-206">在 [**管理此情況下**彈出式視窗以儲存變更，按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="e4200-206">Click **Save** on the **Manage this case** flyout to save the change.</span></span> 

## <a name="compliance-boundary-limitations"></a><span data-ttu-id="e4200-207">合規性界限限制</span><span class="sxs-lookup"><span data-stu-id="e4200-207">Compliance boundary limitations</span></span>

<span data-ttu-id="e4200-208">管理 eDiscovery 案例] 和 [合規性界限的調查，使用時，請記住下列限制。</span><span class="sxs-lookup"><span data-stu-id="e4200-208">Keep the following limitations in mind when managing eDiscovery cases and investigations that use of compliance boundaries.</span></span>
  
- <span data-ttu-id="e4200-209">在建立和執行內容搜尋，您可以選取您機構外的內容位置。</span><span class="sxs-lookup"><span data-stu-id="e4200-209">When creating and running a Content Search, you can select content locations that are outside of your agency.</span></span> <span data-ttu-id="e4200-210">不過，因為搜尋權限篩選器，而這些位置的內容將不會包含在搜尋結果中。</span><span class="sxs-lookup"><span data-stu-id="e4200-210">However, because of the search permissions filter, content from those locations won't be included in the search results.</span></span>
    
- <span data-ttu-id="e4200-211">合規性界限不適用於 eDiscovery 案例中的保留。</span><span class="sxs-lookup"><span data-stu-id="e4200-211">Compliance boundaries don't apply to holds in eDiscovery cases.</span></span> <span data-ttu-id="e4200-212">這表示一個機構中的 eDiscovery 管理員可以在不同的機構保留的使用者。</span><span class="sxs-lookup"><span data-stu-id="e4200-212">That means an eDiscovery manager in one agency can place a user in a different agency on hold.</span></span> <span data-ttu-id="e4200-213">不過，如果 「 eDiscovery 管理員 」 搜尋已處於保留狀態的使用者內容的位置，則強制合規性界限。</span><span class="sxs-lookup"><span data-stu-id="e4200-213">However, the compliance boundary will be enforced if the eDiscovery manager searches the content locations of the user who was placed on hold.</span></span> <span data-ttu-id="e4200-214">這表示電子文件探索管理員不會是無法搜尋使用者的內容位置，即使它們我們能夠將使用者放入保留。</span><span class="sxs-lookup"><span data-stu-id="e4200-214">That means the eDiscovery manager won't be able search the user's content locations, even though they were able to place the user on hold.</span></span>
    
    <span data-ttu-id="e4200-215">此外，保留統計資料將只會套用至機構中的內容位置。</span><span class="sxs-lookup"><span data-stu-id="e4200-215">Additionally, hold statistics will only apply to content locations in the agency.</span></span>
    
- <span data-ttu-id="e4200-216">搜尋的權限篩選器不會套用到 Exchange 公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="e4200-216">Search permissions filters aren't applied to Exchange public folders.</span></span>

## <a name="searching-and-exporting-content-in-multi-geo-environments"></a><span data-ttu-id="e4200-217">搜尋和匯出在多地理位置環境中的內容</span><span class="sxs-lookup"><span data-stu-id="e4200-217">Searching and exporting content in Multi-Geo environments</span></span>

<span data-ttu-id="e4200-218">搜尋的權限篩選器也可讓您控制會匯出的路由傳送內容，以及[SharePoint 多地理位置環境](https://go.microsoft.com/fwlink/?linkid=860840)中搜尋內容位置時，就可以搜尋哪些資料中心。</span><span class="sxs-lookup"><span data-stu-id="e4200-218">Search permissions filters also let you control where content is routed for export and which datacenter can be searched when searching content locations in a [SharePoint Multi-Geo environment](https://go.microsoft.com/fwlink/?linkid=860840).</span></span>
  
- <span data-ttu-id="e4200-219">**匯出搜尋結果**-您可以從 Exchange 信箱、 SharePoint 網站與 OneDrive 帳戶從特定的資料中心匯出搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="e4200-219">**Export search results** - You can export the search results from Exchange mailboxes, SharePoint sites, and OneDrive accounts from a specific datacenter.</span></span> <span data-ttu-id="e4200-220">這表示您可以指定將會從匯出搜尋結果的資料中心位置。</span><span class="sxs-lookup"><span data-stu-id="e4200-220">This means that you can specify the datacenter location that search results will be exported from.</span></span>

    <span data-ttu-id="e4200-221">將**區域**參數用於**New-compliancesecurityfilter**或**Set-compliancesecurityfilter** cmdlet 來建立或變更匯出，將透過路由傳送的資料中心。</span><span class="sxs-lookup"><span data-stu-id="e4200-221">Use the **Region** parameter for **New-ComplianceSecurityFilter** or **Set-ComplianceSecurityFilter** cmdlets to create or change which datacenter the export will be routed through.</span></span>
  
    |<span data-ttu-id="e4200-222">**參數值**</span><span class="sxs-lookup"><span data-stu-id="e4200-222">**Parameter value**</span></span>|<span data-ttu-id="e4200-223">**資料中心位置**</span><span class="sxs-lookup"><span data-stu-id="e4200-223">**Datacenter location**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="e4200-224">NAM</span><span class="sxs-lookup"><span data-stu-id="e4200-224">NAM</span></span>  <br/> |<span data-ttu-id="e4200-225">北美地區 （實際資料中心是在美國）</span><span class="sxs-lookup"><span data-stu-id="e4200-225">North American (actual datacenters are in the US)</span></span>  <br/> |
    |<span data-ttu-id="e4200-226">EUR</span><span class="sxs-lookup"><span data-stu-id="e4200-226">EUR</span></span>  <br/> |<span data-ttu-id="e4200-227">歐洲</span><span class="sxs-lookup"><span data-stu-id="e4200-227">Europe</span></span>  <br/> |
    |<span data-ttu-id="e4200-228">APC</span><span class="sxs-lookup"><span data-stu-id="e4200-228">APC</span></span>  <br/> |<span data-ttu-id="e4200-229">亞太地區</span><span class="sxs-lookup"><span data-stu-id="e4200-229">Asia Pacific</span></span>  <br/> |
    |<span data-ttu-id="e4200-230">CAN</span><span class="sxs-lookup"><span data-stu-id="e4200-230">CAN</span></span> <br/> |<span data-ttu-id="e4200-231">加拿大</span><span class="sxs-lookup"><span data-stu-id="e4200-231">Canada</span></span>
    
- <span data-ttu-id="e4200-232">**路由傳送內容搜尋**-您可以將 SharePoint 網站與 OneDrive 帳戶的內容搜尋路由傳送到衛星資料中心。</span><span class="sxs-lookup"><span data-stu-id="e4200-232">**Route content searches** - You can route the content searches of SharePoint sites and OneDrive accounts to a satellite data center.</span></span> <span data-ttu-id="e4200-233">這表示您可以指定將會執行搜尋的資料中心位置。</span><span class="sxs-lookup"><span data-stu-id="e4200-233">This means you can specify the datacenter location where searches will be run.</span></span>
    
    <span data-ttu-id="e4200-234">使用下列**區域**參數值的值來控制哪些搜尋 SharePoint 網站與 OneDrive 位置時，將會執行中的內容搜尋的資料中心。</span><span class="sxs-lookup"><span data-stu-id="e4200-234">Use the following values for the **Region** parameter values to control which datacenter that Content Searches will run in when searching SharePoint sites and OneDrive locations.</span></span> <span data-ttu-id="e4200-235">請注意，下表也會顯示的資料中心匯出都會透過路由傳送。</span><span class="sxs-lookup"><span data-stu-id="e4200-235">Note that the following table also shows which datacenter exports will be routed through.</span></span> 
  
    |<span data-ttu-id="e4200-236">**參數值**</span><span class="sxs-lookup"><span data-stu-id="e4200-236">**Parameter value**</span></span>|<span data-ttu-id="e4200-237">**匯出資料中心路由位置**</span><span class="sxs-lookup"><span data-stu-id="e4200-237">**Datacenter routing locations for export**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="e4200-238">NAM</span><span class="sxs-lookup"><span data-stu-id="e4200-238">NAM</span></span>  <br/> |<span data-ttu-id="e4200-239">與我們連絡</span><span class="sxs-lookup"><span data-stu-id="e4200-239">US</span></span>  <br/> |
    |<span data-ttu-id="e4200-240">EUR</span><span class="sxs-lookup"><span data-stu-id="e4200-240">EUR</span></span>  <br/> |<span data-ttu-id="e4200-241">歐洲</span><span class="sxs-lookup"><span data-stu-id="e4200-241">Europe</span></span>  <br/> |
    |<span data-ttu-id="e4200-242">APC</span><span class="sxs-lookup"><span data-stu-id="e4200-242">APC</span></span>  <br/> |<span data-ttu-id="e4200-243">亞太地區</span><span class="sxs-lookup"><span data-stu-id="e4200-243">Asia Pacific</span></span>  <br/> |
    |<span data-ttu-id="e4200-244">CAN</span><span class="sxs-lookup"><span data-stu-id="e4200-244">CAN</span></span>  <br/> |<span data-ttu-id="e4200-245">與我們連絡</span><span class="sxs-lookup"><span data-stu-id="e4200-245">US</span></span>  <br/> |
    |<span data-ttu-id="e4200-246">AUS</span><span class="sxs-lookup"><span data-stu-id="e4200-246">AUS</span></span>  <br/> |<span data-ttu-id="e4200-247">亞太地區</span><span class="sxs-lookup"><span data-stu-id="e4200-247">Asia Pacific</span></span>  <br/> |
    |<span data-ttu-id="e4200-248">KOR</span><span class="sxs-lookup"><span data-stu-id="e4200-248">KOR</span></span>  <br/> |<span data-ttu-id="e4200-249">組織的預設資料中心</span><span class="sxs-lookup"><span data-stu-id="e4200-249">The organization's default data center</span></span>  <br/> |
    |<span data-ttu-id="e4200-250">GBR</span><span class="sxs-lookup"><span data-stu-id="e4200-250">GBR</span></span>  <br/> |<span data-ttu-id="e4200-251">歐洲</span><span class="sxs-lookup"><span data-stu-id="e4200-251">Europe</span></span>  <br/> |
    |<span data-ttu-id="e4200-252">JPN</span><span class="sxs-lookup"><span data-stu-id="e4200-252">JPN</span></span>  <br/> |<span data-ttu-id="e4200-253">亞太地區</span><span class="sxs-lookup"><span data-stu-id="e4200-253">Asia Pacific</span></span>  <br/> |
    |<span data-ttu-id="e4200-254">IND</span><span class="sxs-lookup"><span data-stu-id="e4200-254">IND</span></span>  <br/> |<span data-ttu-id="e4200-255">亞太地區</span><span class="sxs-lookup"><span data-stu-id="e4200-255">Asia Pacific</span></span>  <br/> |
    |<span data-ttu-id="e4200-256">LAM</span><span class="sxs-lookup"><span data-stu-id="e4200-256">LAM</span></span>  <br/> |<span data-ttu-id="e4200-257">與我們連絡</span><span class="sxs-lookup"><span data-stu-id="e4200-257">US</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="e4200-258">如果您沒有指定的搜尋權限篩選器的**區域**參數，將搜尋組織的預設 SharePoint 區域，然後搜尋結果匯出至最接近的資料中心。</span><span class="sxs-lookup"><span data-stu-id="e4200-258">If you don't specify the **Region** parameter for a search permissions filter, the organizations default SharePoint region will be searched, then search results are exported to the closest datacenter.</span></span> 
  
<span data-ttu-id="e4200-259">以下是建立搜尋的合規性界限的權限篩選器時，使用**Region**參數的範例。</span><span class="sxs-lookup"><span data-stu-id="e4200-259">Here are examples of using the **Region** parameter when creating search permission filters for compliance boundaries.</span></span> <span data-ttu-id="e4200-260">這假設 Fourth Coffee 子公司位於 「 北美地區 」，且 Coho Winery Europe。</span><span class="sxs-lookup"><span data-stu-id="e4200-260">This assumes that the Fourth Coffee subsidiary is located in North America and that Coho Winery is in Europe.</span></span> 
  
```
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Department -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Department -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```
   
<span data-ttu-id="e4200-261">保留記住時搜尋和匯出中的下列事項多地理位置環境中的內容。</span><span class="sxs-lookup"><span data-stu-id="e4200-261">Keep the following things in mind when searching and exporting content in multi-geo environments.</span></span>
  
- <span data-ttu-id="e4200-262">**Region**參數並不會控制 Exchange 信箱; 的搜尋當您搜尋信箱時，便會搜尋所有的資料中心。</span><span class="sxs-lookup"><span data-stu-id="e4200-262">The **Region** parameter doesn't control searches of Exchange mailboxes; all data centers will be searched when you search mailboxes.</span></span> <span data-ttu-id="e4200-263">若要限制可搜尋的哪些 Exchange 信箱的範圍，請使用時建立或變更的搜尋權限篩選器的**篩選器**參數。</span><span class="sxs-lookup"><span data-stu-id="e4200-263">To limit the scope of which Exchange mailboxes can be searched, use the **Filters** parameter when creating or changing a search permissions filter.</span></span> 
    
- <span data-ttu-id="e4200-264">如果它是所需的 eDiscovery 搜尋跨多個 SharePoint 區域的管理員，您需要建立不同的使用者帳戶的電子文件探索管理員可以使用搜尋權限篩選器來指定備用區域中：SharePoint 網站或 OneDrive 帳戶有位於。</span><span class="sxs-lookup"><span data-stu-id="e4200-264">If it's necessary for an eDiscovery Manager to search across multiple SharePoint regions, you'll need to create a different user account for that eDiscovery manager that can be used in the search permissions filter to specify the alternate region where the SharePoint sites or OneDrive accounts are located.</span></span>
    
- <span data-ttu-id="e4200-265">當您搜尋 SharePoint 和 OneDrive 中的內容， **Region**參數會指示任一種主要的搜尋或衛星位置電子文件探索管理員將會進行電子文件探索調查的位置。</span><span class="sxs-lookup"><span data-stu-id="e4200-265">When searching for content in SharePoint and OneDrive, the **Region** parameter directs searches to either the main or satellite location where the eDiscovery manager will conduct eDiscovery investigations.</span></span> <span data-ttu-id="e4200-266">如果 eDiscovery 管理員 」 搜尋中搜尋權限篩選器所指定的地區外的 SharePoint 和 OneDrive 網站，將會不傳回任何搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="e4200-266">If an eDiscovery manager searches SharePoint and OneDrive sites outside of the region that's specified in the search permissions filter, no search results will be returned.</span></span> 
    
- <span data-ttu-id="e4200-267">匯出搜尋結果時, （包括 Exchange、 Skype for Business，SharePoint、 OneDrive 及其他 Office 365 服務，您可以使用 「 內容搜尋 」 工具來搜尋） 的所有內容位置的內容就會上傳到 Azure 的儲存位置**區域**參數所指定的資料中心。</span><span class="sxs-lookup"><span data-stu-id="e4200-267">When exporting search results, content from all content locations (including Exchange, Skype for Business, SharePoint, OneDrive and other Office 365 services that you can search by using the Content Search tool) will be uploaded to the Azure storage location in the data center that's specified by the **Region** parameter.</span></span> <span data-ttu-id="e4200-268">這可協助組織保持在合規性內不允許匯出受控制的框線之間的內容。</span><span class="sxs-lookup"><span data-stu-id="e4200-268">This helps organizations stay within compliance by not allowing content to be exported across controlled borders.</span></span> <span data-ttu-id="e4200-269">如果沒有區域指定搜尋的權限篩選器中，內容是上傳到組織的預設區域。</span><span class="sxs-lookup"><span data-stu-id="e4200-269">If no region is specified in the search permissions filter, content is uploaded to the organization's default region.</span></span> 
    
- <span data-ttu-id="e4200-270">您可以編輯現有的搜尋權限篩選器來新增或變更區域藉由執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="e4200-270">You can edit an existing search permissions filter to add or change the region by running the following command:</span></span>

    ```
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```
 
## <a name="frequently-asked-questions"></a><span data-ttu-id="e4200-271">常見問題集</span><span class="sxs-lookup"><span data-stu-id="e4200-271">Frequently asked questions</span></span>

 <span data-ttu-id="e4200-272">**誰可以建立及管理搜尋的權限篩選器 （使用 New-compliancesecurityfilter 和 Set-compliancesecurityfilter cmdlet）？**</span><span class="sxs-lookup"><span data-stu-id="e4200-272">**Who can create and manage search permissions filters (using New-ComplianceSecurityFilter and Set-ComplianceSecurityFilter cmdlets )?**</span></span>
  
<span data-ttu-id="e4200-273">若要建立、 檢視及修改搜尋權限篩選器，您必須是安全性 & 合規性中心中 「 組織管理角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="e4200-273">To create, view and modify search permissions filters, you have to be a member of the Organization Management role group in the Security & Compliance Center.</span></span>
  
 <span data-ttu-id="e4200-274">**如果 eDiscovery 管理員指派給多個角色群組跨越多個行政機關，如何在搜尋一個機構中的內容或其他？**</span><span class="sxs-lookup"><span data-stu-id="e4200-274">**If an eDiscovery manager is assigned to more than one role group that spans multiple agencies, how do they search for content in one agency or the other?**</span></span>
  
<span data-ttu-id="e4200-275">電子文件探索管理員可以將參數新增至其搜尋查詢，會限制搜尋至特定的機構。</span><span class="sxs-lookup"><span data-stu-id="e4200-275">The eDiscovery manager can add parameters to their search query that will restrict the search to a specific agency.</span></span> <span data-ttu-id="e4200-276">例如，如果組織具有指定在**CustomAttribute10**屬性，來區分行政機關，他們可以附加下列至其搜尋查詢以搜尋特定的機構中信箱和 OneDrive 帳戶： `CustomAttribute10:<value> AND Site_ComplianceAttribute:<value>`。</span><span class="sxs-lookup"><span data-stu-id="e4200-276">For example, if an organization has specified the **CustomAttribute10** property to differentiate agencies, they can append the following to their search query to search mailboxes and OneDrive accounts in a specific agency:  `CustomAttribute10:<value> AND Site_ComplianceAttribute:<value>`.</span></span>
  
 <span data-ttu-id="e4200-277">**如果屬性做為搜尋權限篩選器中的規範屬性的值已變更發生什麼情況？**</span><span class="sxs-lookup"><span data-stu-id="e4200-277">**What happens if the value of the attribute that's used as the compliance attribute in a search permissions filter is changed?**</span></span>
  
<span data-ttu-id="e4200-278">花費最多可為 3 天來強制執行的合規性界限，如果在篩選中使用屬性的值已變更的搜尋權限篩選器。</span><span class="sxs-lookup"><span data-stu-id="e4200-278">It takes up to 3 days for a search permissions filter to enforce the compliance boundary if the value of the attribute that's used in the filter is changed.</span></span> <span data-ttu-id="e4200-279">例如，在 Contoso 案例假設 Fourth Coffee 機構中的使用者會被轉接至 Coho Winery 機構。</span><span class="sxs-lookup"><span data-stu-id="e4200-279">For example, in the Contoso scenario let's say that a user in the Fourth Coffee agency is transferred to the Coho Winery agency.</span></span> <span data-ttu-id="e4200-280">因此，使用者物件上的**部門**屬性值會從*FourthCoffee*變更為*CohoWinery* 。</span><span class="sxs-lookup"><span data-stu-id="e4200-280">As a result, the value of the **Department** attribute on the user object is changed from  *FourthCoffee*  to  *CohoWinery*  .</span></span> <span data-ttu-id="e4200-281">在此情況下，Fourth Coffee eDiscovery 和投資者會針對該使用者的設定之後屬性變更為 3 天取得搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="e4200-281">In this situation, Fourth Coffee eDiscovery and investors will get search results for that user for up 3 days after the attribute is changed.</span></span> <span data-ttu-id="e4200-282">同樣地，它將會需要最多 3 天前 Coho Winery eDiscovery 管理員和現場會取得使用者的搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="e4200-282">Similarly, it will take up to 3 days before Coho Winery eDiscovery managers and investigators will get search results for the user.</span></span> 
  
 <span data-ttu-id="e4200-283">**電子文件探索管理員可以看到兩個不同的合規性界限的內容？**</span><span class="sxs-lookup"><span data-stu-id="e4200-283">**Can an eDiscovery manager see content from two separate compliance boundaries?**</span></span>
  
<span data-ttu-id="e4200-284">是。</span><span class="sxs-lookup"><span data-stu-id="e4200-284">Yes.</span></span> <span data-ttu-id="e4200-285">這可以經由將使用者新增至角色群組，有兩個行政機關看得到。</span><span class="sxs-lookup"><span data-stu-id="e4200-285">This can be done by adding the user to role groups that have visibility to both agencies.</span></span>
  
 <span data-ttu-id="e4200-286">**搜尋 eDiscovery 案件保留、 Office 365 保留原則，或 DLP 權限篩選器的運作？**</span><span class="sxs-lookup"><span data-stu-id="e4200-286">**Do search permissions filters work for eDiscovery case holds, Office 365 retention policies, or DLP?**</span></span>
  
<span data-ttu-id="e4200-287">否，不是在這個階段</span><span class="sxs-lookup"><span data-stu-id="e4200-287">No, not at this time</span></span>
  
 <span data-ttu-id="e4200-288">**如果指定其中要匯出的內容，但我沒有該區域中的 SharePoint 組織控制項的區域，我仍然可以搜尋 SharePoint？**</span><span class="sxs-lookup"><span data-stu-id="e4200-288">**If I specify a region to control where content is exported, but I don't have a SharePoint organization in that region, can I still search SharePoint?**</span></span>
  
<span data-ttu-id="e4200-289">如果您的組織中不存在搜尋權限篩選器中指定的區域，可供搜尋的預設區域。</span><span class="sxs-lookup"><span data-stu-id="e4200-289">If the region specified in the search permissions filter doesn't exist in your organization, the default region will be searched.</span></span>
  
 <span data-ttu-id="e4200-290">**可以在組織中建立搜尋權限篩選器的最大數目為何？**</span><span class="sxs-lookup"><span data-stu-id="e4200-290">**What is the maximum number of search permissions filters that can be created in an organization?**</span></span>
  
<span data-ttu-id="e4200-291">沒有任何限制可以在組織中建立搜尋權限篩選器的數目。</span><span class="sxs-lookup"><span data-stu-id="e4200-291">There is no limit to the number of search permissions filters that can be created in an organization.</span></span> <span data-ttu-id="e4200-292">不過，有 100 個以上的搜尋權限篩選器時，會影響搜尋效能。</span><span class="sxs-lookup"><span data-stu-id="e4200-292">However, search performance will be impacted when there are more than 100 search permissions filters.</span></span> <span data-ttu-id="e4200-293">若要保留組織中搜尋的權限篩選數目，盡可能的小，建立篩選器，將規則的 Exchange、 SharePoint 和 OneDrive 合併成單一搜尋權限篩選器儘。</span><span class="sxs-lookup"><span data-stu-id="e4200-293">To keep the number of search permissions filters in your organization as small as possible, create filters that combine rules for Exchange, SharePoint, and OneDrive into a single search permissions filter whenever possible.</span></span>
