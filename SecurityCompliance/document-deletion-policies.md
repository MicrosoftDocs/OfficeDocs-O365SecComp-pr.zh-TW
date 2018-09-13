---
title: 文件刪除原則概觀
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/12/2017
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- SPO160
ms.assetid: 55e8d858-f278-482b-a198-2e62d6a2e6e5
description: 您的組織可能需要保留一段時間因規範、 法律文件或其他的業務需求。不過，如果您的組織會超過所需的文件，您會建立不必要的法律風險。與文件刪除原則，您可以主動降低風險藉由在一段特定時間之後刪除文件中的網站 — 例如，您可以刪除文件中的使用者 OneDrive 對於商務網站的五年後所建立的文件。
ms.openlocfilehash: 495dd781c56e25e884d47f72a7e48410ea340208
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013657"
---
# <a name="overview-of-document-deletion-policies"></a><span data-ttu-id="36c77-105">文件刪除原則概觀</span><span class="sxs-lookup"><span data-stu-id="36c77-105">Overview of document deletion policies</span></span>

> [!IMPORTANT]
> <span data-ttu-id="36c77-p102">我們建議您使用保留原則或建立安全性標籤向前移動&amp;規範中心，而不是文件刪除原則。文件刪除原則會繼續運作並排保留原則，但如果您需要保留或刪除內容 Office 365 中的任何位置，我們建議您使用保留原則。如需詳細資訊，請參閱[使用保留原則，而不是這些功能](retention-policies.md#use-a-retention-policy-instead-of-these-features)。</span><span class="sxs-lookup"><span data-stu-id="36c77-p102">Moving forward, we recommend that you use a retention policy or labels created in the Security &amp; Compliance Center instead of a document deletion policy. Document deletion policies will continue to work side by side with retention policies, but if you need to retain or delete content anywhere in Office 365, we recommend that you use a retention policy. For more information, see [Use a retention policy instead of these features](retention-policies.md#use-a-retention-policy-instead-of-these-features).</span></span>
  
<span data-ttu-id="36c77-p103">您的組織可能需要保留一段時間因規範、 法律文件或其他的業務需求。不過，如果您的組織會超過所需的文件，您會建立不必要的法律風險。與文件刪除原則，您可以主動降低風險藉由在一段特定時間之後刪除文件中的網站 — 例如，您可以刪除文件中的使用者 OneDrive 對於商務網站的五年後所建立的文件。</span><span class="sxs-lookup"><span data-stu-id="36c77-p103">Your organization may be required to retain documents for a period of time because of compliance, legal, or other business requirements. However, if your organization keeps documents longer than required, you create unnecessary legal risk. With a document deletion policy, you can proactively reduce risk by deleting documents in a site after a specific period of time—for example, you can delete documents in users' OneDrive for Business sites five years after the documents were created.</span></span>
  
<span data-ttu-id="36c77-112">文件刪除原則兼具功能性和彈性 — 例如，您可以：</span><span class="sxs-lookup"><span data-stu-id="36c77-112">Document deletion policies are powerful yet flexible—for example, you can:</span></span>
  
- <span data-ttu-id="36c77-p104">讓站台擁有者選擇您集中建立和管理的原則。您也可讓站台擁有者在認為原則不適用於其內容時，選擇完全不採用。</span><span class="sxs-lookup"><span data-stu-id="36c77-p104">Allow site owners to choose from policies that you centrally create and manage. You can also allow site owners to opt out altogether if they decide a policy does not apply to their content.</span></span>
    
- <span data-ttu-id="36c77-115">對站台集合中的所有站台 (例如所有 OneDrive for Business 站台) 施行單一強制原則，甚或對建立自特定站台集合範本 (例如「小組站台」範本) 的所有站台集合施行原則。</span><span class="sxs-lookup"><span data-stu-id="36c77-115">Enforce a single mandatory policy on all sites in a site collection, such as all OneDrive for Business sites, or even enforce a policy on all site collections created from a specific site collection template, such as the Team Site template.</span></span>
    
- <span data-ttu-id="36c77-116">提供具有預設規則、無須站台擁有者執行任何動作即會自動套用的預設原則。</span><span class="sxs-lookup"><span data-stu-id="36c77-116">Provide a default policy with a default rule that will be automatically applied without any action required by site owners.</span></span>
    
- <span data-ttu-id="36c77-117">建立有數個刪除規則可供站台擁有者選擇的原則。</span><span class="sxs-lookup"><span data-stu-id="36c77-117">Create a policy that includes several deletion rules that a site owner can choose from.</span></span>
    
<span data-ttu-id="36c77-p105">建立及使用文件刪除原則中心，您可以找到下**保留**在 Office 365 安全性管理文件刪除原則&amp;規範中心。或者，您可以建立原則中心手動[建立網站集合](https://go.microsoft.com/fwlink/p/?LinkID=404342)並在 [**企業**] 索引標籤上選擇**規範原則中心**。每個租用戶可以有一個文件刪除原則中心，以及它將會自動建立如果您從 [安全性] 啟動&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="36c77-p105">You create and manage document deletion policies by using the Document Deletion Policy Center, which you can find under **Retention** in the Office 365 Security &amp; Compliance Center. Alternatively, you can create the policy center manually by [creating the site collection](https://go.microsoft.com/fwlink/p/?LinkID=404342) and choosing **Compliance Policy Center** on the **Enterprise** tab. Each tenant can have only one Document Deletion Policy Center, and it'll be created automatically if you start from the Security &amp; Compliance Center.</span></span> 
  
![文件刪除原則中心的首頁](media/IP-Document-Deletion-Policy-Center-home-page.png)
  
## <a name="when-to-use-document-deletion-policies"></a><span data-ttu-id="36c77-121">文件刪除原則的使用時機</span><span class="sxs-lookup"><span data-stu-id="36c77-121">When to use document deletion policies</span></span>

<span data-ttu-id="36c77-122">除了文件刪除原則以外，Office 365 還為站台內容提供下列保留原則：</span><span class="sxs-lookup"><span data-stu-id="36c77-122">In addition to document deletion policies, Office 365 provides these retention policies for site content:</span></span>
  
- [<span data-ttu-id="36c77-123">記錄管理</span><span class="sxs-lookup"><span data-stu-id="36c77-123">Records management</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=404250)
    
- [<span data-ttu-id="36c77-124">內容類型、 清單及文件庫的資訊管理原則</span><span class="sxs-lookup"><span data-stu-id="36c77-124">Information management policies for content types, lists, and libraries</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=404239)
    
- [<span data-ttu-id="36c77-125">網站原則</span><span class="sxs-lookup"><span data-stu-id="36c77-125">Site policies</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=404242)
    
<span data-ttu-id="36c77-p106">每個類型的站台或資料都有其最適用的原則類型。舉例來說，您的組織可能會有使用內容類型的高度結構化站台，例如用於合約的財務站台，或文章的知識庫等。在此情況下，您即可使用內容類型原則。或者，您的組織可能需要保留法律文件，在此情況下，您可以使用內容類型和記錄中心來實作檔案規劃。</span><span class="sxs-lookup"><span data-stu-id="36c77-p106">Each type of policy works best for a specific type of site or data. For example, your organization may have a highly structured site that uses content types, such as a financial site for contracts or a knowledge base for articles. In this case, you can use content type policies. Or your organization may need to retain legal documents, in which case you might use content types and a Records Center to implement a file plan.</span></span>
  
<span data-ttu-id="36c77-p107">文件刪除原則不取代記錄管理或資訊管理原則，其運作起來最順暢結構化的資料與內容類型。但是，您應該使用文件刪除原則時需要廣泛管理等 OneDrive for Business 的網站 」 和小組網站的非結構化資料自動刪除。</span><span class="sxs-lookup"><span data-stu-id="36c77-p107">Document deletion policies don't replace records management or information management policies, which work best with structured data and content types. Instead, you should use document deletion policies when you need to broadly manage the automatic deletion of unstructured data such as OneDrive for Business sites and team sites.</span></span>
  
![顯示網站內容保留選項的圖表](media/IP-Retention-policies-for-site-content.png)
  
<span data-ttu-id="36c77-p108">如果您將文件刪除原則套用至已對清單或文件庫使用內容類型原則或資訊管理原則的站台，這些原則將會被忽略，而文件刪除原則會有效用。這表示，您在規劃站台時應僅使用適用於結構化或非結構化內容的原則，而非同時使用兩種原則。如需有關文件刪除原則會如何覆寫其他原則的詳細資訊，請參閱[Apply or remove a document deletion policy for a site](apply-or-remove-a-document-deletion-policy-for-a-site.md)。</span><span class="sxs-lookup"><span data-stu-id="36c77-p108">If you apply a document deletion policy to a site that already uses content type policies or information management policies for a list or library, those policies are ignored while the document deletion policy is in effect. This means you should plan for a site to use only policies meant for structured or unstructured content, not both. For more information on how document deletion policies override other policies, see [Apply or remove a document deletion policy for a site](apply-or-remove-a-document-deletion-policy-for-a-site.md).</span></span>
  
<span data-ttu-id="36c77-136">不同於其他原則，文件刪除原則只對文件庫有效用，對清單則否。</span><span class="sxs-lookup"><span data-stu-id="36c77-136">Unlike other policies, document deletion policies work only on document libraries, not lists.</span></span>
  
## <a name="deletion-policies-and-rules"></a><span data-ttu-id="36c77-137">刪除原則和規則</span><span class="sxs-lookup"><span data-stu-id="36c77-137">Deletion policies and rules</span></span>

<span data-ttu-id="36c77-138">文件刪除原則包含一或多個刪除規則，分別指定：</span><span class="sxs-lookup"><span data-stu-id="36c77-138">A document deletion policy contains one or more delete rules that specify:</span></span>
  
- <span data-ttu-id="36c77-139">刪除之前的期間。</span><span class="sxs-lookup"><span data-stu-id="36c77-139">The time period until deletion.</span></span>
    
- <span data-ttu-id="36c77-140">是否要從文件的建立時間或前次修改時間計算刪除日期。</span><span class="sxs-lookup"><span data-stu-id="36c77-140">Whether to calculate the deletion date from the when the document was created or last modified.</span></span>
    
- <span data-ttu-id="36c77-141">要永久刪除文件，還是放置到資源回收筒。</span><span class="sxs-lookup"><span data-stu-id="36c77-141">Whether to delete the document permanently or to the Recycle Bin.</span></span>
    
<span data-ttu-id="36c77-142">如果原則包含多個規則，站台擁有者可以從中選取最適用於其內容的規則。</span><span class="sxs-lookup"><span data-stu-id="36c77-142">If a policy contains more than one rule, site owners can select the rule that best applies to their content.</span></span>
  
![新增刪除規則頁面](media/IP-New-deletion-rule.png)
  
## <a name="policies-and-assignments"></a><span data-ttu-id="36c77-144">原則和指派</span><span class="sxs-lookup"><span data-stu-id="36c77-144">Policies and assignments</span></span>

<span data-ttu-id="36c77-p109">建立文件刪除原則之後，您可以將其指派給網站集合範本 — 例如，您可以將原則指派給 OneDrive for Business 範本，使其包含每個使用者的 OneDrive 的網站。當您將原則指派給網站集合範本時，這適用於已建立該範本，以及從該範本未來建立任何網站集合中的所有網站集合。</span><span class="sxs-lookup"><span data-stu-id="36c77-p109">After you create a document deletion policy, you can assign it to a site collection template — for example, you can assign a policy to the OneDrive for Business template so that it includes every user's OneDrive site. When you assign a policy to a site collection template, this applies to all site collections already created from that template, in addition to any site collections created from that template in the future.</span></span>
  
![選擇範本頁面，顯示 OneDrive 選項](media/IP-Choose-a-template.png)
  
<span data-ttu-id="36c77-p110">您也可以將原則指派至特定站台集合 — 這會覆寫任何已指派至該站台集合範本的原則。例如，您可以將原則指派至「小組站台」範本，但接著將不同的原則集套用至建立自該範本的特定站台集合，而覆寫該原則。</span><span class="sxs-lookup"><span data-stu-id="36c77-p110">You can also assign a policy to a specific site collection— doing so overrides any policies that have been assigned to that site collection template. For example, you may assign policies to the Team Site template, but then override them by applying a different set of policies to a specific site collection created from that template.</span></span>
  
### <a name="one-mandatory-policy-or-several-policies-to-choose-from"></a><span data-ttu-id="36c77-150">選擇一個強制原則或數個原則</span><span class="sxs-lookup"><span data-stu-id="36c77-150">One mandatory policy or several policies to choose from</span></span>

<span data-ttu-id="36c77-p111">在指派原則時，您可以選擇將其設為強制原則，而使其成為唯一可供指派的原則，且將會套用至站台集合中的所有站台。站台擁有者無法選擇不採用強制原則，也就是說，站台中的文件無論如何都會受到刪除原則的管理。</span><span class="sxs-lookup"><span data-stu-id="36c77-p111">When you assign a policy, you can choose to make it mandatory, so that only this policy can be assigned and that it will be applied to all sites in the site collection. Site owners cannot opt out of a mandatory policy, which means documents in the site will be subject to the delete policy no matter what.</span></span>
  
<span data-ttu-id="36c77-p112">除了設定單一強制原則以外，您也可以將數個原則指派至站台集合，這樣可讓每個站台擁有者能夠選擇要對其站台套用的原則，甚或選擇完全不採用。例如，您可以為一般商業文件建立一個原則，並且為具有不同保留排程的財務文件建立另一個原則。站台擁有者通常最清楚其站台包含哪些內容，因此也最了解應套用哪個文件刪除原則。每個站台只能套用一個原則。</span><span class="sxs-lookup"><span data-stu-id="36c77-p112">Instead of making a single policy mandatory, you can also assign several policies to a site collection, which allows each site owner to choose which policy to apply to their site, or even to opt out altogether. For example, you can create one policy for general business documents and another policy for financial documents that have a different retention schedule. A site owner often knows best what content their site contains and therefore which document deletion policy to apply. Each site can have only one policy applied to it.</span></span>
  
### <a name="one-rule-or-several-rules-to-choose-from"></a><span data-ttu-id="36c77-157">選擇一個規則或數個規則</span><span class="sxs-lookup"><span data-stu-id="36c77-157">One rule or several rules to choose from</span></span>

<span data-ttu-id="36c77-158">接著，每個原則可包含許多規則 — 例如，一般商業文件刪除原則可能會有兩個規則：</span><span class="sxs-lookup"><span data-stu-id="36c77-158">In turn, each policy can contain many rules—for example, a deletion policy for general business documents may have two rules:</span></span>
  
- <span data-ttu-id="36c77-159">不需要保留的文件根據法律義務或現行商業需求不應保留一年以上自建立的。</span><span class="sxs-lookup"><span data-stu-id="36c77-159">Documents that don't need retention based on legal obligations or ongoing business need should not be retained for more than one year from creation.</span></span>
    
- <span data-ttu-id="36c77-160">現行商業用途所需、且需使用一年以上的文件，自建立後不應保留三年以上。</span><span class="sxs-lookup"><span data-stu-id="36c77-160">Documents necessary for active, ongoing business use that are needed for more than one year, should not be retained for more than three years from creation.</span></span>
    
<span data-ttu-id="36c77-p113">網站擁有人可以判斷其網站包含一般商業文件選取此刪除原則，然後從原則中選取適當的規則。您只能選取一個規則從目前套用至網站 （不是從任何原則） 的原則和規則套用至網站中的所有文件庫。</span><span class="sxs-lookup"><span data-stu-id="36c77-p113">A site owner can determine that their site contains general business documents, select this deletion policy, and then select the appropriate rule from the policy. You can only select a rule from the policy that's currently applied to the site (not from any policy), and the rule applies to all document libraries in the site.</span></span>
  
## <a name="the-relationship-of-site-collections-policies-and-rules"></a><span data-ttu-id="36c77-163">站台集合、原則和規則的關係</span><span class="sxs-lookup"><span data-stu-id="36c77-163">The relationship of site collections, policies, and rules</span></span>

<span data-ttu-id="36c77-164">基本關係如下：</span><span class="sxs-lookup"><span data-stu-id="36c77-164">The basic relationship is this:</span></span>
  
<span data-ttu-id="36c77-p114">網站集合或網站集合範本可以有一或多個原則指派給它，而每個原則可以有一或多個規則。不過，可以為每個站台、 使用中的一個原則，而且可以是屬於作用中的文件庫站台內的任何時候只有一個刪除規則。</span><span class="sxs-lookup"><span data-stu-id="36c77-p114">A site collection or a site collection template can have one or more policies assigned to it, and each of those policies can have one or more rules. However, there can be only one policy that's active per site, and there can be only one deletion rule that's active at any time for the libraries within the site.</span></span>
  
![顯示原則間關係的圖表](media/IP-Two-policies-four-rules.png)
  
## <a name="document-deletion-policies-are-inherited"></a><span data-ttu-id="36c77-168">繼承文件刪除原則</span><span class="sxs-lookup"><span data-stu-id="36c77-168">Document deletion policies are inherited</span></span>

<span data-ttu-id="36c77-p115">如同權限、瀏覽和許多其他站台功能，文件刪除原則是可繼承的。站台擁有者可為其站台選取文件刪除原則，並且讓子站台繼承父項的原則。子站台的擁有者可選取不同的原則和規則組合以解除繼承，而該原則將會套用至所有子站台，直到繼承再次解除為止。</span><span class="sxs-lookup"><span data-stu-id="36c77-p115">Like permissions, navigation, and many other site features, document deletion policies are inherited. A site owner can select a document deletion policy for their site, and all subsites inherit the policy from the parent. An owner of a subsite can break inheritance by selecting a different policy and rule combination, and that policy applies to all subsites until inheritance is broken again.</span></span>
  
## <a name="assigning-document-deletion-policies-for-the-first-time"></a><span data-ttu-id="36c77-172">第一次指派文件刪除原則</span><span class="sxs-lookup"><span data-stu-id="36c77-172">Assigning document deletion policies for the first time</span></span>

<span data-ttu-id="36c77-p116">請務必了解的時間期間指定的文件刪除原則表示時間文件已建立或修改不是時間由於已指派原則。例如，您可能會建立兩年後建立時，會永久刪除文件的文件刪除原則，然後將該原則指派給從中數個網站集合建立四個或五個年前的網站集合範本。在此例中為可能的現有的網站集合包含許多已超過設定的兩個年度刪除原則所指定的文件 — 這表示大量內容將會刪除推出之後將第一個文件刪除原則指派時間。</span><span class="sxs-lookup"><span data-stu-id="36c77-p116">It's important to understand that the time period specified for a document deletion policy means the time since the document was created or modified, not the time since the policy was assigned. For example, you might create a document deletion policy that permanently deletes documents two years after they were created, and then assign that policy to a site collection template from which several site collections were created four or five years ago. In this case, it's likely that the existing site collections contain many documents that are already older than the two years specified by the deletion policy—this means a lot of content will be deleted soon after assigning the document deletion policy for the first time.</span></span>
  
<span data-ttu-id="36c77-p117">如果您是初次指派原則，網站上所有文件皆會列入評估，符合標準的文件就會遭到刪除。此原則適用於所有現有文件，而不是只適用於指派原則後才建立的新文件。同時請切記，原則的期間是以各文件的存留期為準，而不是第一次指派原則的時間。</span><span class="sxs-lookup"><span data-stu-id="36c77-p117">When you assign the policy for the first time, all documents in the site are evaluated and, if they meet the criteria, they will be deleted. This applies to all existing documents, not just new documents created since the policy was assigned. And remember that the time period is for the age of each document, not the time from when the policy was first assigned.</span></span>
  
<span data-ttu-id="36c77-p118">因此，在第一次指派站台的原則之前，您應先考量現有內容的存留期，以及原則對這些內容可能造成的影響。您也可以在指派新原則前先與站台擁有者溝通，讓他們有足夠的時間可評估可能的影響。</span><span class="sxs-lookup"><span data-stu-id="36c77-p118">Therefore, before you assign a policy to a site for the first time, you should first consider the age of the existing content and how the policy may impact that existing content. You may also want to communicate the new policy to site owners before assigning it, to give them time to assess the possible impact.</span></span>
  
## <a name="time-lag-for-propagating-policies"></a><span data-ttu-id="36c77-181">傳播原則的時間延遲</span><span class="sxs-lookup"><span data-stu-id="36c77-181">Time lag for propagating policies</span></span>

<span data-ttu-id="36c77-182">在您將原則指派至站台集合後，站台擁有者可以使用 **[站台設定]** 頁面上的 **[文件刪除原則]** 連結，來檢視及套用適用於站台的原則。</span><span class="sxs-lookup"><span data-stu-id="36c77-182">After you assign policies to a site collection, site owners use the **Document Deletion Policies** link on the **Site Settings** page to view and apply policies available for the site.</span></span> 
  
<span data-ttu-id="36c77-p119">除非已指派原則至網站集合將不會出現 [**文件刪除原則**] 連結。原則已指派給網站後立即不會出現連結的同時，— 約 24 小時的時間從時原則指派給**文件刪除原則**連結出現時。</span><span class="sxs-lookup"><span data-stu-id="36c77-p119">The **Document Deletion Policies** link won't appear unless policies have been assigned to the site collection. Also, the link doesn't appear immediately after policies have been assigned to the site—it can take up to 24 hours from when the policies are assigned to when the **Document Deletion Policies** link appears.</span></span> 
  
## <a name="permissions"></a><span data-ttu-id="36c77-185">權限</span><span class="sxs-lookup"><span data-stu-id="36c77-185">Permissions</span></span>

<span data-ttu-id="36c77-p120">您的法規小組成員若要使用文件刪除原則中心，將必須同時取得原則中心和將要套用原則之站台集合的權限。我們建議您：</span><span class="sxs-lookup"><span data-stu-id="36c77-p120">Members of your compliance team who will use the Document Deletion Policy Center need permissions to both the policy center and site collections to which policies will be applied. We recommend that you:</span></span>
  
1. <span data-ttu-id="36c77-p121">建立包含的文件刪除原則中心的所有使用者的安全性群組 — 很有可能規範原則管理小組。如需詳細資訊，請參閱[Manage Mail-Enabled 安全性群組](https://go.microsoft.com/fwlink/p/?LinkID=404345)。</span><span class="sxs-lookup"><span data-stu-id="36c77-p121">Create a security group that contains all users of the Document Deletion Policy Center—most likely your compliance policy-management team. See [Manage Mail-Enabled Security Groups](https://go.microsoft.com/fwlink/p/?LinkID=404345) for more information.</span></span> 
    
2. <span data-ttu-id="36c77-p122">在文件刪除原則中心] 中，指定網站集合擁有者權限安全性群組。如需詳細資訊，請參閱[網站集合管理員的權限](https://go.microsoft.com/fwlink/p/?LinkID=404346)。</span><span class="sxs-lookup"><span data-stu-id="36c77-p122">In the Document Deletion Policy Center, assign site collection owner permissions to the security group. See [Permissions for site collection administrators](https://go.microsoft.com/fwlink/p/?LinkID=404346) for more information.</span></span> 
    
3. <span data-ttu-id="36c77-192">在每個需要指派文件刪除原則的站台集合中，將站台集合擁有者權限指派給安全性群組。</span><span class="sxs-lookup"><span data-stu-id="36c77-192">In each site collection to which you need to assign document deletion policies, assign site collection owner permissions to the security group.</span></span>
    
## <a name="how-document-deletion-policies-work-with-hold-policies"></a><span data-ttu-id="36c77-193">文件刪除原則與保留原則的搭配運作方式</span><span class="sxs-lookup"><span data-stu-id="36c77-193">How document deletion policies work with hold policies</span></span>

<span data-ttu-id="36c77-194">保留原則可確保所有內容皆能在特定的一段時間內保存，而文件刪除原則則可確保所有內容會在特定的一段時間後刪除。</span><span class="sxs-lookup"><span data-stu-id="36c77-194">A hold policy ensures that all content is preserved for a specific period of time, while a document deletion policy ensures that all content is deleted after a specific period of time.</span></span>
  
<span data-ttu-id="36c77-p123">如果您需要在固定的一段時間內保有文件，您可以將保留原則與刪除原則搭配使用。例如，您可以在文件修改後將其保留三年，然後設定會在文件前次修改的三年之後加以刪除的刪除原則。</span><span class="sxs-lookup"><span data-stu-id="36c77-p123">If you need to retain documents for a fixed period of time, you can use a hold policy in conjunction with a deletion policy. For example, you could hold documents for three years after they are modified, and then set up a deletion policy to delete those documents three years after they were last modified.</span></span>
  
<span data-ttu-id="36c77-p124">請注意，刪除原則不可覆寫保留原則。如果站台處於保留狀態，而文件刪除原則刪除了某文件，該文件將會保存在文件保留庫中，如同文件是以手動方式刪除一般。</span><span class="sxs-lookup"><span data-stu-id="36c77-p124">Note that a deletion policy cannot override a hold. If a site is on hold and a document deletion policy deletes a document, then the document will be preserved in the Preservation Hold library in the same way as if the document had been deleted manually.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="36c77-199">另請參閱</span><span class="sxs-lookup"><span data-stu-id="36c77-199">See also</span></span>

[<span data-ttu-id="36c77-200">套用或移除站台的文件刪除原則</span><span class="sxs-lookup"><span data-stu-id="36c77-200">Apply or remove a document deletion policy for a site</span></span>](apply-or-remove-a-document-deletion-policy-for-a-site.md)

[<span data-ttu-id="36c77-201">建立文件刪除原則</span><span class="sxs-lookup"><span data-stu-id="36c77-201">Create a document deletion policy</span></span>](create-a-document-deletion-policy.md)

