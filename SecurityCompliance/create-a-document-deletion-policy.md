---
title: 建立文件刪除原則
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
ms.assetid: 41b2ed73-eb8d-4429-945e-a8197894585a
description: 基於規範、法律或其他規定，組織通常必須將文件保留一段時間。但是，將文件保留超過要求時間，可能會讓組織暴露在法律風險下。
ms.openlocfilehash: e8f85f4cc9ae541d8a962dfb270e5216c912ac7d
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153915"
---
# <a name="create-a-document-deletion-policy"></a><span data-ttu-id="82db9-104">建立文件刪除原則</span><span class="sxs-lookup"><span data-stu-id="82db9-104">Create a document deletion policy</span></span>

> [!IMPORTANT]
> <span data-ttu-id="82db9-105">我們建議您使用保留原則或建立 Microsoft 365 合規性中心、 Microsoft 365 安全中心或 Office 365 安全性中的保留標籤向前發展，&amp;合規性中心，而不是文件刪除原則。</span><span class="sxs-lookup"><span data-stu-id="82db9-105">Moving forward, we recommend that you use a retention policy or retention labels created in the Microsoft 365 compliance center, Microsoft 365 security center, or Office 365 Security &amp; Compliance Center instead of a document deletion policy.</span></span> <span data-ttu-id="82db9-106">文件刪除原則將會繼續運作並排保留原則，但如果您需要保留或刪除 Office 365 中的任何位置的內容，我們建議您使用保留原則。</span><span class="sxs-lookup"><span data-stu-id="82db9-106">Document deletion policies will continue to work side by side with retention policies, but if you need to retain or delete content anywhere in Office 365, we recommend that you use a retention policy.</span></span> <span data-ttu-id="82db9-107">如需詳細資訊，請參閱 <<c0>使用保留原則而非這些功能。</span><span class="sxs-lookup"><span data-stu-id="82db9-107">For more information, see [Use a retention policy instead of these features](retention-policies.md#use-a-retention-policy-instead-of-these-features).</span></span> 
  
<span data-ttu-id="82db9-p103">基於規範、法律或其他規定，組織通常必須將文件保留一段時間。但是，將文件保留超過要求時間，可能會讓組織暴露在法律風險下。</span><span class="sxs-lookup"><span data-stu-id="82db9-p103">Organizations are often required to retain documents for a certain period of time due to compliance, legal, or other regulations. However, retaining documents for longer than required can expose the organization to legal risk.</span></span>
  
<span data-ttu-id="82db9-110">使用文件刪除原則，您可以積極降低風險藉由在一段特定時間之後刪除文件中的網站 — 例如，您可以刪除文件中的使用者的 OneDrive for Business 網站的五年之後建立的文件。</span><span class="sxs-lookup"><span data-stu-id="82db9-110">With a document deletion policy, you can proactively reduce risk by deleting documents in a site after a specific period of time—for example, you can delete documents in users' OneDrive for Business sites five years after the documents were created.</span></span> 
  
<span data-ttu-id="82db9-p104">建立文件刪除原則後，您可以將其指派到網站集合範本，因此可將此原則套用到從那個範本中建立的所有網站集合。您也可以指派一個原則至特定網站集合，它會覆寫已經指派到此網站集合範本的任何原則。</span><span class="sxs-lookup"><span data-stu-id="82db9-p104">After you create a document deletion policy, you can assign it to a site collection template, so that the policy is available to all site collections created from that template. You can also assign a policy to a specific a site collection, which overrides any policies that may have been assigned to the template for that site collection.</span></span>
  
![文件刪除原則中心的首頁](media/IP-Document-Deletion-Policy-Center-home-page.png)
  
## <a name="policy-templates"></a><span data-ttu-id="82db9-114">原則範本</span><span class="sxs-lookup"><span data-stu-id="82db9-114">Policy templates</span></span>

<span data-ttu-id="82db9-p105">您可以從頭開始建立文件刪除原則，或是使用其中一個範例原則。規範原則中心含有可供您直接使用的範例原則，或者您可以將它們做為起點，然後加以重新命名或修改。</span><span class="sxs-lookup"><span data-stu-id="82db9-p105">You can create a document deletion policy from scratch, or you can use one of the sample policies. The Compliance Policy Center includes sample policies that you can use as is, or you can use them as a starting point and then rename or modify them.</span></span>
  
![文件刪除原則範例](media/IP-Sample-deletion-policies.png)
  
## <a name="examples-of-how-to-use-document-deletion-policies"></a><span data-ttu-id="82db9-118">範例</span><span class="sxs-lookup"><span data-stu-id="82db9-118">Examples of how to use document deletion policies</span></span>

<span data-ttu-id="82db9-119">一個網站集合或網站集合範本可擁有一或多個原則指派，每個原則可擁有一或多個規則。</span><span class="sxs-lookup"><span data-stu-id="82db9-119">A site collection or a site collection template can have one more policies assigned to it, and each of those policies can have one or more rules.</span></span> <span data-ttu-id="82db9-120">不過，可以為每個網站，作用中的只能將一個原則，以及可以有正在使用中的站台內的文件庫的任何時候只能有一個刪除規則。</span><span class="sxs-lookup"><span data-stu-id="82db9-120">However, there can be only one policy that's active per site, and there can be only one deletion rule that's active at any time for the libraries within the site.</span></span>
  
![顯示原則間關係的圖表](media/IP-Two-policies-four-rules.png)
  
<span data-ttu-id="82db9-122">此外，您可以將原則選擇做為強制或預設原則，也可以將刪除規則選擇做為預設規則：</span><span class="sxs-lookup"><span data-stu-id="82db9-122">In addition, you can select a policy as mandatory or default, and you can select a deletion rule as a default rule:</span></span> 
  
- <span data-ttu-id="82db9-123">**強制原則**當原則會標示為必要時，只有一個原則可指派給網站集合或範本。</span><span class="sxs-lookup"><span data-stu-id="82db9-123">**Mandatory policy**When a policy is marked as mandatory, only one policy can be assigned to the site collection or template.</span></span> <span data-ttu-id="82db9-124">原則必須標示為預設值，將會套用至所有網站。</span><span class="sxs-lookup"><span data-stu-id="82db9-124">The policy must be marked as default and will be applied to all sites.</span></span> <span data-ttu-id="82db9-125">網站擁有者無法選擇退出原則。</span><span class="sxs-lookup"><span data-stu-id="82db9-125">Site owners cannot opt out of the policy.</span></span>
    
- <span data-ttu-id="82db9-126">**預設原則**當原則設為預設值時，原則位於自動作用中的所有網站，將它指派給網站擁有者所需進行任何動作。</span><span class="sxs-lookup"><span data-stu-id="82db9-126">**Default policy**When a policy is set as default, the policy is automatically active in all sites that it's assigned to with no action required by site owner.</span></span>
    
- <span data-ttu-id="82db9-127">**預設規則**當將刪除規則設為預設值時，它會自動套用至使用該原則的網站中的所有文件庫。</span><span class="sxs-lookup"><span data-stu-id="82db9-127">**Default rule**When a deletion rule is set as default, it is automatically applied to all libraries in the sites that use the policy.</span></span>
    
<span data-ttu-id="82db9-128">下列範例將說明何時您可能需要使用一個強制原則或預設原則與規則。</span><span class="sxs-lookup"><span data-stu-id="82db9-128">The following examples explain when you might want to use a mandatory policy or default policies and rules.</span></span>
  
### <a name="example-1-apply-a-single-policy-with-a-single-rule-to-a-site-collection-template"></a><span data-ttu-id="82db9-129">範例 1：套用一個擁有單一規則的單一原則至網站集合範本。</span><span class="sxs-lookup"><span data-stu-id="82db9-129">Example 1: Apply a single policy with a single rule to a site collection template</span></span>

<span data-ttu-id="82db9-p108">您可能會想要在範圍廣泛的非結構化內容 (例如 OneDrive for Business 網站或所有小組網站) 上，強制執行文件刪除原則。如果要確定文件刪除原則已套用到網站集合範本裡的所有網站，您可以：</span><span class="sxs-lookup"><span data-stu-id="82db9-p108">You may want to enforce a document deletion policy across a broad range of unstructured content, such as all OneDrive for Business sites or all team sites. If you want to ensure that a single document deletion policy is active in all sites created from a site collection template, you can:</span></span>
  
1. <span data-ttu-id="82db9-132">建立包含單一預設刪除規則的單一原則。</span><span class="sxs-lookup"><span data-stu-id="82db9-132">Create a single policy with a single default deletion rule.</span></span>
    
2. <span data-ttu-id="82db9-133">將原則設定為強制和預設原則。</span><span class="sxs-lookup"><span data-stu-id="82db9-133">Set the policy as mandatory and default.</span></span>
    
3. <span data-ttu-id="82db9-134">將此原則指派到網站集合範本。</span><span class="sxs-lookup"><span data-stu-id="82db9-134">Assign the policy to a site collection template.</span></span>
    
<span data-ttu-id="82db9-p109">在此範例中，預設的刪除原則將套用到範本下網站集合的所有文件庫，而且網站擁有者無法選擇退出此原則。這是最簡單的方法來廣泛且正確地強制執行文件刪除原則。</span><span class="sxs-lookup"><span data-stu-id="82db9-p109">In this example, the default deletion rule will be applied to all libraries in all site collections created from the template, and site owners cannot opt out of the policy. This is the simplest way to broadly and rigidly enforce a document deletion policy.</span></span>
  
![顯示單一強制原則的圖表](media/IP-Example-1-doc-deletion-policies.png)
  
### <a name="example-2-apply-a-single-policy-with-several-rules-to-a-site-collection-template"></a><span data-ttu-id="82db9-138">範例 2： 將包含數個規則的單一原則套用至網站集合範本。</span><span class="sxs-lookup"><span data-stu-id="82db9-138">Example 2: Apply a single policy with several rules to a site collection template</span></span>

<span data-ttu-id="82db9-p110">網站擁有者通常最清楚他們網站的內容類型，所以，您也可以讓網站擁有者選擇最適合套用到他們網站的刪除原則。您也可以允許網站擁有者完全選擇退出原則。</span><span class="sxs-lookup"><span data-stu-id="82db9-p110">Site owners often know best what type of content their site contains, so you may choose to allow site owners to select the deletion rule that best applies to their site. You may also want to allow site owners to opt out of a policy entirely.</span></span>
  
<span data-ttu-id="82db9-p111">在此同時，您仍然可以集中建立與管理這些原則。您也可以選擇將一個原則與規則做為預設原則和規則，所以在網站擁有者選擇不同原則或選擇退出原則之前，該原則將永遠有效。如果您要為網站擁有者提供這樣的彈性，您可以：</span><span class="sxs-lookup"><span data-stu-id="82db9-p111">At the same time, you can still centrally create and manage the policies. You can also select one policy and rule as the default, so that a policy is always in effect until the site owner chooses a different one or opts out. If you want to provide such flexibility to site owners, you can:</span></span>
  
1. <span data-ttu-id="82db9-143">建立包含數個刪除規則之單一原則，並將一個規則設定為預設規則。</span><span class="sxs-lookup"><span data-stu-id="82db9-143">Create a single policy with several deletion rules, and set one rule as the default.</span></span>
    
2. <span data-ttu-id="82db9-144">將原則設定為預設原則。</span><span class="sxs-lookup"><span data-stu-id="82db9-144">Set the policy as the default policy.</span></span>
    
3. <span data-ttu-id="82db9-145">將此原則指派到網站集合範本。</span><span class="sxs-lookup"><span data-stu-id="82db9-145">Assign the policy to a site collection template.</span></span>
    
<span data-ttu-id="82db9-146">網站擁有者可選擇其中一個替代刪除規則、選擇退出原則，或是不執行任何動作，然後遵循預設的原則和規則。</span><span class="sxs-lookup"><span data-stu-id="82db9-146">Site owners can select one of the alternate deletion rules, opt out of the policy, or do nothing and be subject to the default policy and rule.</span></span>
  
![顯示含有許多規則之原則的圖表](media/IP-Example-2-doc-deletion-policies.png)
  
### <a name="example-3-apply-several-policies-with-one-or-more-rules-to-a-site-collection"></a><span data-ttu-id="82db9-148">範例 3：將包含一或多個規則的數個原則套用至網站集合</span><span class="sxs-lookup"><span data-stu-id="82db9-148">Example 3: Apply several policies with one or more rules to a site collection</span></span>

<span data-ttu-id="82db9-p112">此範例可為網站擁有者提供最大彈性，因為他們可以從多個原則中做選擇，而且選擇一個原則後，他們通常還可以從數個規則中做選擇。將一個原則和規則設定為預設原則和規則，所以在網站擁有者選擇不同原則或選擇退出原則之前，該原則將永遠有效。請注意，如果您並未將一個原則和規則設定為預設原則和規則，則在網站擁有者選取和套用這些原則和規則之前，所有原則和規則對網站的文件庫都將無效。</span><span class="sxs-lookup"><span data-stu-id="82db9-p112">This example provides the maximum flexibility to site owners because they can choose from several policies, and after selecting a policy they can often choose from several rules. One policy and rule are set as default, so that a policy is always in effect until the site owner chooses a different one or opts out. Note that if you do not set a policy and rule as the default, then no policies or rules will be active for the document libraries in the site until the site owner takes action to select and apply them.</span></span>
  
<span data-ttu-id="82db9-p113">與前兩個範例不同之處在於，這些原則是指派到一個特定網站集合，而非網站集合範本。這代表可以針對特定網站集合中的內容，更具體地量身訂作原則。</span><span class="sxs-lookup"><span data-stu-id="82db9-p113">Unlike the previous two examples, these policies are assigned to a specific site collection — not the site collection template. This means the policies can be more specifically tailored for the content in a specific site collection.</span></span>
  
<span data-ttu-id="82db9-p114">原則與規則是繼承而來的。網站擁有者可以為他們的網站選擇一個原則與一個規則，而所有子網站將繼承其上層的原則。但是，子網站的擁有者可以藉由選擇不同的原則和規則來中斷繼承，而再次中斷繼承之後，這個原則與規則便會套用到所有子網站。</span><span class="sxs-lookup"><span data-stu-id="82db9-p114">Policies and rules are inherited. Site owners can select a policy and rule for their site, and all subsites inherit the policy from the parent. However, an owner of a subsite can break inheritance by selecting a different policy and rule, which in turn applies to all subsites until inheritance is broken again.</span></span>
  
<span data-ttu-id="82db9-156">若要設定此狀況，您可以：</span><span class="sxs-lookup"><span data-stu-id="82db9-156">To set up this scenario, you can:</span></span>
  
1. <span data-ttu-id="82db9-157">建立數個原則，並且每個原則都包含一或多個規則。</span><span class="sxs-lookup"><span data-stu-id="82db9-157">Create several policies that each contains one or more rules.</span></span>
    
2. <span data-ttu-id="82db9-158">將一個原則和規則設定為預設原則和規則。</span><span class="sxs-lookup"><span data-stu-id="82db9-158">Set a policy and rule as the default.</span></span>
    
3. <span data-ttu-id="82db9-159">將這些原則指派至特定網站集合。</span><span class="sxs-lookup"><span data-stu-id="82db9-159">Assign the policies to a specific site collection.</span></span>
    
<span data-ttu-id="82db9-160">此外，這些原則與規則專為特定網站集合量身訂作，其中網站擁有者藉由選擇最符合其網站需求的原則和規則來中斷繼承。</span><span class="sxs-lookup"><span data-stu-id="82db9-160">In addition, the policies and rules are tailored to a specific site collection, where site owners can break inheritance by selecting the policy and rule that best applies to their site.</span></span>
  
![顯示許多原則和規則的圖表](media/IP-Example-3-doc-deletion-policies.png)
  
## <a name="create-a-document-deletion-policy"></a><span data-ttu-id="82db9-162">建立文件刪除原則</span><span class="sxs-lookup"><span data-stu-id="82db9-162">Create a document deletion policy</span></span>

1. <span data-ttu-id="82db9-163">在 [Office 365Security&amp;合規性中心，導覽至 [**資料管理** \> **保留**。</span><span class="sxs-lookup"><span data-stu-id="82db9-163">In the Office 365Security &amp; Compliance Center, navigate to **Data management** \> **Retention**.</span></span> <span data-ttu-id="82db9-164">**刪除**，請按一下 [**管理文件刪除原則的 SharePoint Online 和商務用 OneDrive**。</span><span class="sxs-lookup"><span data-stu-id="82db9-164">Under **Delete**, click **Manage document deletion policies for SharePoint Online and OneDrive for Business**.</span></span> <span data-ttu-id="82db9-165">「文件刪除原則中心」會在新瀏覽器索引標籤中開啟。</span><span class="sxs-lookup"><span data-stu-id="82db9-165">The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
    <span data-ttu-id="82db9-166">第一次您從安全性瀏覽&amp;以文件刪除原則中心合規性中心，為您自動建立原則中心。</span><span class="sxs-lookup"><span data-stu-id="82db9-166">The first time you navigate from the Security &amp; Compliance Center to the Document Deletion Policy Center, the policy center is automatically created for you.</span></span> <span data-ttu-id="82db9-167">或者，您可以手動建立原則中心藉由[建立網站集合](http://go.microsoft.com/fwlink/p/?LinkID=404342)，並選擇 [**企業**] 索引標籤上的 [**符合性原則中心**。</span><span class="sxs-lookup"><span data-stu-id="82db9-167">Alternatively, you can manually create the policy center by [creating the site collection](http://go.microsoft.com/fwlink/p/?LinkID=404342) and choosing **Compliance Policy Center** on the **Enterprise** tab.</span></span> 
    
2. <span data-ttu-id="82db9-168">選擇 [**刪除原則**]。</span><span class="sxs-lookup"><span data-stu-id="82db9-168">Choose **Deletion Policies**.</span></span>
    
    ![刪除原則選項](media/IP-Deletion-Policies-option.png)
  
3. <span data-ttu-id="82db9-170">選擇 **[新增項目]**。</span><span class="sxs-lookup"><span data-stu-id="82db9-170">Choose **new item**.</span></span>
    
4. <span data-ttu-id="82db9-p117">輸入原則名稱與說明。網站擁有者可以根據這個名稱和說明為其網站選擇一個原則，因此請註明足夠資訊，以便網站擁有者能選擇正確的原則。</span><span class="sxs-lookup"><span data-stu-id="82db9-p117">Enter a policy name and description. Site owners may be selecting a policy for their site based on this name and description, so include enough information for them to choose the correct policy.</span></span>
    
5. <span data-ttu-id="82db9-173">若要建立一個規則，請選擇 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="82db9-173">To create a rule, choose **New**.</span></span>
    
6. <span data-ttu-id="82db9-174">輸入一個名稱，然後選擇下列選項：</span><span class="sxs-lookup"><span data-stu-id="82db9-174">Enter a name and choose the following options:</span></span>
    
  - <span data-ttu-id="82db9-175">選擇是否將規則永久刪除，或是丟到資源回收桶。</span><span class="sxs-lookup"><span data-stu-id="82db9-175">Choose whether the rule will permanently delete documents or delete them to the Recycle Bin.</span></span> <span data-ttu-id="82db9-176">從網站永久刪除一個項目前，資源回收筒提供了一個第二階段的安全網。</span><span class="sxs-lookup"><span data-stu-id="82db9-176">The Recycle Bin provides a second-stage safety net before an item is permanently deleted from a site.</span></span> <span data-ttu-id="82db9-177">如需資源回收筒的詳細資訊，請參閱[清理資源回收筒或還原您的檔案](http://go.microsoft.com/fwlink/p/?LinkID=404348)。</span><span class="sxs-lookup"><span data-stu-id="82db9-177">For more information about the Recycle Bin, see [Empty the Recycle Bin or restore your files](http://go.microsoft.com/fwlink/p/?LinkID=404348).</span></span>
    
  - <span data-ttu-id="82db9-178">選擇刪除日期是以文件建立當天或最後一次更新的日期開始算起。</span><span class="sxs-lookup"><span data-stu-id="82db9-178">Choose whether the deletion date is calculated from the date when a document was created or last modified.</span></span>
    
  - <span data-ttu-id="82db9-179">輸入期限的天數、月數或年數，超過此期限後，文件將會遭到刪除。</span><span class="sxs-lookup"><span data-stu-id="82db9-179">Enter a number of days, months, or years as the time period after which a document will be deleted.</span></span>
    
  - <span data-ttu-id="82db9-p119">選擇此規則是否是預設的規則。您所建立的第一個規則會自動設定為預設的規則。預設規則會自動套用到使用此原則之網站上的所有文件庫。</span><span class="sxs-lookup"><span data-stu-id="82db9-p119">Choose whether the rule is a default rule. The first rule that you create is automatically set as the default rule. A default rule is automatically applied to all libraries in the sites that use the policy.</span></span>
    
![新增刪除規則頁面](media/IP-New-deletion-rule.png)
  
7. <span data-ttu-id="82db9-184">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="82db9-184">Click **Save**.</span></span>
    
8. <span data-ttu-id="82db9-p120">您也可以建立其他的規則，讓網站擁有者可以選擇將不同規則套用到他們的網站。如果網站擁有者沒有執行任何動作，則會套用預設規則 (若有的話)。</span><span class="sxs-lookup"><span data-stu-id="82db9-p120">Create additional rules if you want site owners to be able to choose different rules to apply to their site. The default rule, if any, will be applied if the site owner takes no action.</span></span>
    
9. <span data-ttu-id="82db9-187">若要從原則移除規則，選取規則，按一下 [**刪除**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="82db9-187">To remove a rule from a policy, select the rule, click **Delete**, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="82db9-188">如果您刪除規則，且原則中並未包含預設規則，那麼沒有規則將會作用於該原則--也就是說，將會刪除任何文件。</span><span class="sxs-lookup"><span data-stu-id="82db9-188">If you delete a rule, and the policy does not contain a default rule, then no rule will be in effect for that policy—in other words, no documents will be deleted.</span></span> 
  
![確認從原則移除規則訊息](media/IP-Remove-rule-from-policy-message.png)
  
## <a name="assign-the-document-deletion-policy-to-a-site-collection-template"></a><span data-ttu-id="82db9-190">將文件刪除原則指派至網站集合範本。</span><span class="sxs-lookup"><span data-stu-id="82db9-190">Assign the document deletion policy to a site collection template</span></span>

<span data-ttu-id="82db9-191">指派一個原則到網站集合範本後，這個原則即套用到此範本建立的所有網站集合，包含現有的與未來建立的網站集合。</span><span class="sxs-lookup"><span data-stu-id="82db9-191">By assigning a policy to a site collection template, you make the policy available to all site collections created from that template, including both existing site collections and site collections created in the future.</span></span>
  
<span data-ttu-id="82db9-192">請務必了解期間指定的文件刪除原則表示時間自文件已建立或修改，不是時間後已指派原則。</span><span class="sxs-lookup"><span data-stu-id="82db9-192">It's important to understand that the time period specified for a document deletion policy means the time since the document was created or modified, not the time since the policy was assigned.</span></span> <span data-ttu-id="82db9-193">如果您是初次指派原則，網站上所有文件皆會列入評估，符合標準的文件就會遭到刪除。</span><span class="sxs-lookup"><span data-stu-id="82db9-193">When you assign the policy for the first time, all documents in the site are evaluated and, if they meet the criteria, they will be deleted.</span></span> <span data-ttu-id="82db9-194">此原則適用於所有現有文件，而不是只適用於指派原則後才建立的新文件。</span><span class="sxs-lookup"><span data-stu-id="82db9-194">This applies to all existing documents, not just new documents created since the policy was assigned.</span></span>
  
1. <span data-ttu-id="82db9-195">安全性&amp;合規性中心，導覽至 [**資料管理** \> **保留**。</span><span class="sxs-lookup"><span data-stu-id="82db9-195">In the Security &amp; Compliance Center, navigate to **Data management** \> **Retention**.</span></span> <span data-ttu-id="82db9-196">**刪除**，請按一下 [**管理文件刪除原則的 SharePoint Online 和商務用 OneDrive**。</span><span class="sxs-lookup"><span data-stu-id="82db9-196">Under **Delete**, click **Manage document deletion policies for SharePoint Online and OneDrive for Business**.</span></span> <span data-ttu-id="82db9-197">「文件刪除原則中心」會在新瀏覽器索引標籤中開啟。</span><span class="sxs-lookup"><span data-stu-id="82db9-197">The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
2. <span data-ttu-id="82db9-198">選擇 [範本的原則指派]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="82db9-198">Choose **Policy Assignments for Templates**.</span></span>
    
    ![範本的原則指派選項](media/IP-Policy-Assignments-for-Templates-option.png)
  
3. <span data-ttu-id="82db9-200">選擇 **[新增項目]**。</span><span class="sxs-lookup"><span data-stu-id="82db9-200">Choose **new item**.</span></span>
    
4. <span data-ttu-id="82db9-201">執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="82db9-201">Do one of the following:</span></span>
    
  - <span data-ttu-id="82db9-202">若要指派原則至網站集合範本 (如「小組網站」範本)，請選取 [指派至網站集合範本]\*\*\*\*，然後選取網站集合範本。</span><span class="sxs-lookup"><span data-stu-id="82db9-202">To assign the policy to a site collection template such as the Team Site template, select **Assign to site collection template**, and then select the site collection template.</span></span>
    
  - <span data-ttu-id="82db9-203">若要將原則指派給使用者的 One Drive for Business，選擇 [**指派給 OneDrive for Business 範本**，請反白顯示下方。</span><span class="sxs-lookup"><span data-stu-id="82db9-203">To assign the policy to users' One Drive for Business, choose **Assign to OneDrive for Business Template**, highlighted below.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="82db9-204">當您將原則指派至網站集合範本，此原則會套用到範本下現有的網站集合以及未來建立的網站集合。</span><span class="sxs-lookup"><span data-stu-id="82db9-204">When you assign a policy to a site collection template, that policy will be available both to existing site collections created from that template and to site collections created in the future.</span></span> 
  
![選擇範本頁面，顯示 OneDrive 選項](media/IP-Choose-a-template.png)
  
5. <span data-ttu-id="82db9-206">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="82db9-206">Click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="82db9-207">每個範本只能有一個指派給它的原則。</span><span class="sxs-lookup"><span data-stu-id="82db9-207">Each template can have only one set of policies assigned to it.</span></span> <span data-ttu-id="82db9-208">如果您看到錯誤訊息說明此範本已經有原則指派給它，選擇 [**取消**\>左側導覽窗格中的 [**指派至網站集合**\>選取檢視及管理的一組原則已使用的網站集合指派。</span><span class="sxs-lookup"><span data-stu-id="82db9-208">If you see an error saying that this template already has policies assigned to it, choose **Cancel** \> **Assign to Site Collection** in the left navigation \> select a site collection to view and manage the set of policies that are already assigned.</span></span> 
  
6. <span data-ttu-id="82db9-209">選取 **[管理指派的原則]**，選擇您要指派的原則，然後選擇是否設定為預設原則。</span><span class="sxs-lookup"><span data-stu-id="82db9-209">Choose **Manage Assigned Policies**, select the policies that you want to assign, and then choose whether one policy is the default policy.</span></span> <span data-ttu-id="82db9-210">如果您設定一個預設原則，所有套用此原則的網站都會自動執行此原則，網站擁有者不需要進行任何動作。</span><span class="sxs-lookup"><span data-stu-id="82db9-210">When you set a default policy, all sites assigned to the policy automatically have the policy active with no action required by site owner.</span></span>
    
    ![新增和管理原則頁面](media/IP-Add-and-manage-policies-page.png)
  
7. <span data-ttu-id="82db9-212">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="82db9-212">Click **Save**.</span></span>
    
8. <span data-ttu-id="82db9-p125">如果您要在所有網站上強制執行該原則，且不允許網站擁有者選擇退出，請選擇 **[將原則設定為強制原則]**。當您將原則設定為強制原則時後，便只能將該單一原則指派至網站集合範本。該原則也會標示為預設原則。</span><span class="sxs-lookup"><span data-stu-id="82db9-p125">If you want to enforce the policy on all sites without allowing site owners to opt out, choose **Mark Policy as Mandatory**. When you make a policy mandatory, only that single policy can be assigned to the site collection template. The policy must also be marked as default.</span></span>
    
    <span data-ttu-id="82db9-216">如果此選項變為灰色，請選擇 **[管理指派的原則]** 然後確定是否至少指派了一個原則並將之設定為預設原則。</span><span class="sxs-lookup"><span data-stu-id="82db9-216">If this option is grayed out, choose **Manage Assigned Policies** and make sure that at least one policy is assigned and set as default.</span></span> 
    
9. <span data-ttu-id="82db9-217">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="82db9-217">Click **Save**.</span></span>
    
## <a name="assign-the-document-deletion-policy-to-a-site-collection"></a><span data-ttu-id="82db9-218">將文件刪除原則指派至網站集合</span><span class="sxs-lookup"><span data-stu-id="82db9-218">Assign the document deletion policy to a site collection</span></span>

<span data-ttu-id="82db9-p126">將原則指派至特定網站集合，即表示此原則僅可供該特定網站集合使用。這表示您可以制定更符合網站集合內容的原則。同樣地，指派到特定網站集合的原則會覆寫已經指派到此網站集合範本的任何原則。舉例來說，指派到「業務部門」網站集合 (由小組網站建立) 的原則，將會覆寫指派到小組網站範本的任何原則。</span><span class="sxs-lookup"><span data-stu-id="82db9-p126">By assigning a policy to a specific site collection, you make the policy available only to that specific site collection. This means you can tailor policies more closely to the content in the site collection. Also, policies assigned to a specific site collection will override any policies that are assigned to the template for that site collection. For example, a policy assigned to the Sales Department site collection (created from the Team Site template) will override any policies assigned to the Team Site template.</span></span>
  
<span data-ttu-id="82db9-223">請務必了解期間指定的文件刪除原則表示時間自文件已建立或修改，不是時間後已指派原則。</span><span class="sxs-lookup"><span data-stu-id="82db9-223">It's important to understand that the time period specified for a document deletion policy means the time since the document was created or modified, not the time since the policy was assigned.</span></span> <span data-ttu-id="82db9-224">如果您是初次指派原則，網站上所有文件皆會列入評估，符合標準的文件就會遭到刪除。</span><span class="sxs-lookup"><span data-stu-id="82db9-224">When you assign the policy for the first time, all documents in the site are evaluated and, if they meet the criteria, they will be deleted.</span></span> <span data-ttu-id="82db9-225">此原則適用於所有現有文件，而不是只適用於指派原則後才建立的新文件。</span><span class="sxs-lookup"><span data-stu-id="82db9-225">This applies to all existing documents, not just new documents created since the policy was assigned.</span></span>
  
1. <span data-ttu-id="82db9-226">安全性&amp;合規性中心，導覽至 [**資料管理** \> **保留**。</span><span class="sxs-lookup"><span data-stu-id="82db9-226">In the Security &amp; Compliance Center, navigate to **Data management** \> **Retention**.</span></span> <span data-ttu-id="82db9-227">**刪除**，請選擇 [**管理文件刪除原則的 SharePoint Online 和商務用 OneDrive**。</span><span class="sxs-lookup"><span data-stu-id="82db9-227">Under **Delete**, choose **Manage document deletion policies for SharePoint Online and OneDrive for Business**.</span></span> <span data-ttu-id="82db9-228">「文件刪除原則中心」會在新瀏覽器索引標籤中開啟。</span><span class="sxs-lookup"><span data-stu-id="82db9-228">The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
2. <span data-ttu-id="82db9-229">選擇 [網站集合的原則指派]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="82db9-229">Choose **Policy Assignments for Site Collections**.</span></span>
    
    ![網站集合的原則指派選項](media/IP-Policy-Assignments-for-Site-Collections-option.png)
  
3. <span data-ttu-id="82db9-231">選擇 **[新增項目]**。</span><span class="sxs-lookup"><span data-stu-id="82db9-231">Choose **new item**.</span></span>
    
4. <span data-ttu-id="82db9-232">選擇 **[選擇網站集合**。</span><span class="sxs-lookup"><span data-stu-id="82db9-232">Choose **Choose a site collection**.</span></span> <span data-ttu-id="82db9-233">搜尋依名稱或 URL 的網站集合、 選取網站集合並按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="82db9-233">Search for the site collection by name or URL, select the site collection and click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="82db9-234">每個網站集合只能有一個指派給它的原則。</span><span class="sxs-lookup"><span data-stu-id="82db9-234">Each site collection can have only one set of policies assigned to it.</span></span> <span data-ttu-id="82db9-235">如果您看到錯誤訊息說明此網站集合已有原則指派給它，選擇 [**取消** \> **指派給網站集合**，並選取 [網站集合來檢視及管理的一組已指派的原則。</span><span class="sxs-lookup"><span data-stu-id="82db9-235">If you see an error saying that this site collection already has policies assigned to it, choose **Cancel** \> **Assign to Site Collection** and select a site collection to view and manage the set of policies that are already assigned.</span></span> 
  
![選擇網站集合頁面](media/IP-Choose-a-site-collection-page.png)
  
5. <span data-ttu-id="82db9-237">選取 **[管理指派的原則]**，選擇您要指派的原則，然後選擇是否設定為預設原則。</span><span class="sxs-lookup"><span data-stu-id="82db9-237">Choose **Manage Assigned Policies**, select the policies that you want to assign, and then choose whether one policy is the default policy.</span></span> <span data-ttu-id="82db9-238">如果您設定一個預設原則，所有套用此原則的網站都會自動執行此原則，網站擁有者不需要進行任何動作。</span><span class="sxs-lookup"><span data-stu-id="82db9-238">When you set a default policy, all sites assigned to the policy automatically have the policy active with no action required by site owner.</span></span>
    
    ![新增和管理原則頁面](media/IP-Add-and-manage-policies-page.png)
  
6. <span data-ttu-id="82db9-240">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="82db9-240">Click **Save**.</span></span>
    
7. <span data-ttu-id="82db9-p132">如果您要在所有網站上強制執行該原則，且不允許網站擁有者選擇退出，請選擇 **[將原則設定為強制原則]**。當您將原則設定為強制原則時後，便只能將該單一原則指派至網站集合。該原則也會標示為預設原則。</span><span class="sxs-lookup"><span data-stu-id="82db9-p132">If you want to enforce the policy on all sites without allowing site owners to opt out, choose **Mark Policy as Mandatory**. When you make a policy mandatory, only that single policy can be assigned to the site collection. The policy must also be marked as default.</span></span>
    
    <span data-ttu-id="82db9-244">如果此選項變為灰色，請選擇 **[管理指派的原則]** 然後確定是否至少指派了一個原則並將之設定為預設原則。</span><span class="sxs-lookup"><span data-stu-id="82db9-244">If this option is grayed out, choose **Manage Assigned Policies** and make sure that at least one policy is assigned and set as default.</span></span> 
    
8. <span data-ttu-id="82db9-245">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="82db9-245">Click **Save**.</span></span>
    
## <a name="delete-a-policy-assignment"></a><span data-ttu-id="82db9-246">刪除原則指派</span><span class="sxs-lookup"><span data-stu-id="82db9-246">Delete a policy assignment</span></span>

<span data-ttu-id="82db9-247">當您刪除指派，其指派的原則將不再套用到網站集合的任何網站或網站集合範本。</span><span class="sxs-lookup"><span data-stu-id="82db9-247">When you delete an assignment, the assigned policies will no longer apply to any sites in the site collection or site collection template.</span></span>
  
1. <span data-ttu-id="82db9-248">安全性&amp;合規性中心，導覽至 [**資料管理** \> **保留**。</span><span class="sxs-lookup"><span data-stu-id="82db9-248">In the Security &amp; Compliance Center, navigate to **Data management** \> **Retention**.</span></span> <span data-ttu-id="82db9-249">**刪除**，請選擇 [**管理文件刪除原則的 SharePoint Online 和商務用 OneDrive**。</span><span class="sxs-lookup"><span data-stu-id="82db9-249">Under **Delete**, choose **Manage document deletion policies for SharePoint Online and OneDrive for Business**.</span></span> <span data-ttu-id="82db9-250">「文件刪除原則中心」會在新瀏覽器索引標籤中開啟。</span><span class="sxs-lookup"><span data-stu-id="82db9-250">The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
2. <span data-ttu-id="82db9-251">選擇 [範本的原則指派]\*\*\*\* 或 [網站集合的原則指派]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="82db9-251">Choose either **Policy Assignments for Templates** or **Policy Assignments for Site Collections**.</span></span>
    
3. <span data-ttu-id="82db9-252">選擇指派項目，然後按一下 [**刪除項目**。</span><span class="sxs-lookup"><span data-stu-id="82db9-252">Select the assignment item and click **Delete Item**.</span></span>
    
    ![原則指派的刪除項目命令](media/IP-Delete-policy-assignment.png)
  
## <a name="delete-a-policy"></a><span data-ttu-id="82db9-254">刪除原則</span><span class="sxs-lookup"><span data-stu-id="82db9-254">Delete a policy</span></span>

<span data-ttu-id="82db9-255">您無法刪除使用中的原則。</span><span class="sxs-lookup"><span data-stu-id="82db9-255">You can't delete a policy that's in use.</span></span> <span data-ttu-id="82db9-256">您可以刪除原則之前，您必須先刪除網站集合和網站集合範本包含該原則的所有工作分派，請參閱前一節。</span><span class="sxs-lookup"><span data-stu-id="82db9-256">Before you can delete a policy, you first need to delete all assignments to site collections and site collection templates that include that policy—see the previous section.</span></span>
  
1. <span data-ttu-id="82db9-257">安全性&amp;合規性中心\>選擇 [**資料管理** \> **保留**在左側導覽中\>下**刪除** \> **管理文件刪除原則的 SharePoint Online 和 OneDrive商務用**。</span><span class="sxs-lookup"><span data-stu-id="82db9-257">In the Security &amp; Compliance Center \> choose **Data management** \> **Retention** in the left navigation \> under **Delete** \> **Manage document deletion policies for SharePoint Online and OneDrive for Business**.</span></span> <span data-ttu-id="82db9-258">「文件刪除原則中心」會在新瀏覽器索引標籤中開啟。</span><span class="sxs-lookup"><span data-stu-id="82db9-258">The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
2. <span data-ttu-id="82db9-259">選擇 [\* \* 刪除原則 \* \*。</span><span class="sxs-lookup"><span data-stu-id="82db9-259">Choose \*\* Deletion Policies \*\*.</span></span>
    
    ![刪除原則選項](media/IP-Deletion-Policies-option.png)
  
3. <span data-ttu-id="82db9-261">選取原則。</span><span class="sxs-lookup"><span data-stu-id="82db9-261">Select the policy.</span></span>
    
4. <span data-ttu-id="82db9-262">在功能區上\>**項目**] 索引標籤\>**移除原則**。</span><span class="sxs-lookup"><span data-stu-id="82db9-262">On the Ribbon \> **Items** tab \> **Remove Policy**.</span></span>
    
    ![功能區上的移除原則按鈕](media/IP-Remove-Policy-button-on-Ribbon.png)
  
5. <span data-ttu-id="82db9-264">如果原則是使用中，系統會要求您如果您想要移除其中所使用的網站集合的所有原則。</span><span class="sxs-lookup"><span data-stu-id="82db9-264">If the policy is in use, you'll be asked if you want to remove the policy from all of the site collections where it's being used.</span></span> <span data-ttu-id="82db9-265">如果您確定，請選擇 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="82db9-265">If you're sure, choose **OK**.</span></span>
    
    ![刪除原則確認訊息](media/IP-Delete-policy-confirmation.png)
  
## <a name="see-also"></a><span data-ttu-id="82db9-267">另請參閱</span><span class="sxs-lookup"><span data-stu-id="82db9-267">See also</span></span>

[<span data-ttu-id="82db9-268">文件刪除原則概觀</span><span class="sxs-lookup"><span data-stu-id="82db9-268">Overview of document deletion policies</span></span>](document-deletion-policies.md)

[<span data-ttu-id="82db9-269">套用或移除網站的文件刪除原則</span><span class="sxs-lookup"><span data-stu-id="82db9-269">Apply or remove a document deletion policy for a site</span></span>](apply-or-remove-a-document-deletion-policy-for-a-site.md)
 

