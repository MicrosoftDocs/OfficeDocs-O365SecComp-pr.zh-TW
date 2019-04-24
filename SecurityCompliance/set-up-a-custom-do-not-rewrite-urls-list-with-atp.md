---
title: 設定自訂的修正-無法執行-Url 清單，使用 Office 365 ATP 安全連結
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
ms.collection:
- M365-security-compliance
description: 當您設定 ATP 安全連結原則時，您可以包含 do not 修正 ' 若要讓組織中的部分使用者造訪網站時，您在清單中包含的 Url 清單。
ms.openlocfilehash: 006dab44054f9cb707bb13d158588ab6606fab5c
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32264448"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-office-365-atp-safe-links"></a><span data-ttu-id="01a06-103">設定自訂的修正-無法執行-Url 清單，使用 Office 365 ATP 安全連結</span><span class="sxs-lookup"><span data-stu-id="01a06-103">Set up a custom do-not-rewrite URLs list using Office 365 ATP Safe Links</span></span>

> [!IMPORTANT]
> <span data-ttu-id="01a06-104">本文適用於商務版客戶。</span><span class="sxs-lookup"><span data-stu-id="01a06-104">This article is intended for business customers.</span></span> <span data-ttu-id="01a06-105">如果您是家庭使用者尋找關於在 Outlook 中的安全連結的資訊，請參閱 <<c0>進階 Outlook.com 安全性。</span><span class="sxs-lookup"><span data-stu-id="01a06-105">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="01a06-106">使用[Office 365 進階威脅防護](office-365-atp.md)(ATP)，您的組織可以有[自訂封鎖的 Url](set-up-a-custom-blocked-urls-list-wtih-atp.md)中，如此當人員在 web 上按一下 [位址 (Url) 的電子郵件或特定的 Office 文件中，他們會禁止移至這些 Url。</span><span class="sxs-lookup"><span data-stu-id="01a06-106">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a [custom blocked URLs](set-up-a-custom-blocked-urls-list-wtih-atp.md), such that when people click on web addresses (URLs) in email messages or certain Office documents, they are prevented from going to those URLs.</span></span> <span data-ttu-id="01a06-107">您的組織也可以在組織中具有特定群組的自訂 「 不要重寫 」 清單。</span><span class="sxs-lookup"><span data-stu-id="01a06-107">Your organization can also have custom "do not rewrite" lists for specific groups in your organization.</span></span> <span data-ttu-id="01a06-108">「 不要重寫 」 清單讓某些人員能瀏覽否則封鎖由[Office 365 中的 ATP 安全連結](atp-safe-links.md)的 Url。</span><span class="sxs-lookup"><span data-stu-id="01a06-108">A "do not rewrite" list enables some people to visit URLs that are otherwise blocked by [ATP Safe Links in Office 365](atp-safe-links.md).</span></span> 
  
<span data-ttu-id="01a06-109">本文說明如何指定的 Url 所排除的 ATP 安全連結掃描，和幾個重點謹記清單。</span><span class="sxs-lookup"><span data-stu-id="01a06-109">This article describes how to specify a list of URLs that are excluded from ATP Safe Links scanning, and a few important points to keep in mind.</span></span>

## <a name="set-up-a-do-not-rewrite-list"></a><span data-ttu-id="01a06-110">設定 「 不可修正 」 清單</span><span class="sxs-lookup"><span data-stu-id="01a06-110">Set up a "do not rewrite" list</span></span>

<span data-ttu-id="01a06-111">ATP 安全連結保護使用多個清單，包括您的組織封鎖的 Url 清單及 「 不要重寫 」 清單例外狀況。</span><span class="sxs-lookup"><span data-stu-id="01a06-111">ATP Safe Links protection uses several lists, including your organization's blocked URLs list and the "do not rewrite" lists for exceptions.</span></span> <span data-ttu-id="01a06-112">如果您有必要的權限，您可以設定自訂 「 不要重寫 」 清單。</span><span class="sxs-lookup"><span data-stu-id="01a06-112">If you have the necessary permissions, you can set up your custom "do not rewrite" lists.</span></span> <span data-ttu-id="01a06-113">當您新增或編輯套用至組織中特定收件者的安全連結原則，您可以這麼做。</span><span class="sxs-lookup"><span data-stu-id="01a06-113">You do this when you add or edit Safe Links policies that apply to specific recipients in your organization.</span></span> 

<span data-ttu-id="01a06-114">若要編輯 （或定義） ATP 原則，您必須獲指派其中一個，如下表所述的角色：</span><span class="sxs-lookup"><span data-stu-id="01a06-114">To edit (or define) ATP policies, you must be assigned one of the roles described in the following table:</span></span>

|<span data-ttu-id="01a06-115">角色</span><span class="sxs-lookup"><span data-stu-id="01a06-115">Role</span></span>  |<span data-ttu-id="01a06-116">位置/方式指派</span><span class="sxs-lookup"><span data-stu-id="01a06-116">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="01a06-117">Office 365 全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="01a06-117">Office 365 Global Administrator</span></span> |<span data-ttu-id="01a06-118">若要購買 Office 365 註冊的人員是預設的全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="01a06-118">The person who signs up to buy Office 365 is a global admin by default.</span></span> <span data-ttu-id="01a06-119">（請參閱[關於 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)，以了解更多）。</span><span class="sxs-lookup"><span data-stu-id="01a06-119">(See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="01a06-120">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="01a06-120">Security Administrator</span></span> |<span data-ttu-id="01a06-121">Azure Active Directory 系統管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="01a06-121">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="01a06-122">Exchange Online 組織管理</span><span class="sxs-lookup"><span data-stu-id="01a06-122">Exchange Online Organization Management</span></span> |<span data-ttu-id="01a06-123">Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="01a06-123">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="01a06-124">或</span><span class="sxs-lookup"><span data-stu-id="01a06-124">or</span></span> <br>  <span data-ttu-id="01a06-125">PowerShell cmdlet (請參閱[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span><span class="sxs-lookup"><span data-stu-id="01a06-125">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span></span> |

> [!TIP]
> <span data-ttu-id="01a06-126">若要深入了解角色和權限，請參閱[中 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="01a06-126">To learn more about roles and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="to-view-or-edit-a-custom-do-not-rewrite-urls-list"></a><span data-ttu-id="01a06-127">若要檢視或編輯自訂 「 不要重寫 」 Url 清單</span><span class="sxs-lookup"><span data-stu-id="01a06-127">To view or edit a custom "do not rewrite" URLs list</span></span>
  
1. <span data-ttu-id="01a06-128">移至 [[https://protection.office.com](https://protection.office.com)並以您的公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="01a06-128">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="01a06-129">在左側導覽中，[**威脅管理** \> **原則** \> **安全連結**。</span><span class="sxs-lookup"><span data-stu-id="01a06-129">In the left navigation, under **Threat management** \> **Policy** \> **Safe Links**.</span></span>
    
3. <span data-ttu-id="01a06-130">在 [**原則套用至特定收件者**] 區段中，選擇 [**新增]** ([新增] 按鈕的格式類似於加上加號 ( **+**)) 來建立新的原則。</span><span class="sxs-lookup"><span data-stu-id="01a06-130">In the **Policies that apply to specific recipients** section, choose **New** (the New button resembles a plus sign ( **+**)) to create a new policy.</span></span> <span data-ttu-id="01a06-131">（或者，您可以編輯現有的原則。）</span><span class="sxs-lookup"><span data-stu-id="01a06-131">(Alternatively, you can edit an existing policy.)</span></span><br/><span data-ttu-id="01a06-132">![選擇 [新增若要將特定電子郵件收件者的安全連結原則](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span><span class="sxs-lookup"><span data-stu-id="01a06-132">![Choose New to add a Safe Links policy for specific email recipients](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span></span>
  
4. <span data-ttu-id="01a06-133">指定的名稱和描述您的原則。</span><span class="sxs-lookup"><span data-stu-id="01a06-133">Specify a name and description for your policy.</span></span>
    
5. <span data-ttu-id="01a06-134">中**不要重寫下列 Url** ] 區段中，選取 [**輸入有效的 URL** ] 方塊中，然後輸入 URL，然後選擇 [加號 （+）。</span><span class="sxs-lookup"><span data-stu-id="01a06-134">In the **Do not rewrite the following URLs** section, select the **Enter a valid URL** box, and then type a URL, and then choose the plus sign (+).</span></span> 
    
6. <span data-ttu-id="01a06-135">在**套用至**] 區段中，選擇 [**收件者是的成員**，然後再選擇您想要包含在原則中的群組。</span><span class="sxs-lookup"><span data-stu-id="01a06-135">In the **Applied To** section, choose **The recipient is a member of**, and then choose the group(s) you want to include in your policy.</span></span> <span data-ttu-id="01a06-136">選擇 [**新增**]，然後選擇 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="01a06-136">Choose **Add**, and then choose **OK**.</span></span>
    
7. <span data-ttu-id="01a06-137">當您完成新增 Url、 在螢幕的右下角，選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="01a06-137">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="01a06-138">請務必檢閱您的組織自訂封鎖 Url 清單。</span><span class="sxs-lookup"><span data-stu-id="01a06-138">Make sure to review your organization's custom list of blocked URLs.</span></span> <span data-ttu-id="01a06-139">請參閱 <<c0>設定自訂封鎖 Url 清單使用 ATP 安全連結。</span><span class="sxs-lookup"><span data-stu-id="01a06-139">See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).</span></span> 
  
## <a name="important-points-to-keep-in-mind"></a><span data-ttu-id="01a06-140">請記住的重要事項</span><span class="sxs-lookup"><span data-stu-id="01a06-140">Important points to keep in mind</span></span>

- <span data-ttu-id="01a06-141">在 「 不要重寫 」 清單中指定任何 Url 中所排除的 ATP 安全連結掃描的收件者，您指定。</span><span class="sxs-lookup"><span data-stu-id="01a06-141">Any URLs that you specify in the "do not rewrite" list are excluded from ATP Safe Links scanning for the recipients that you specify.</span></span>
 
- <span data-ttu-id="01a06-142">當您指定 「 不要重寫 」 清單中的 ATP 安全連結原則時，您可以包含最多三個萬用字元星號 (\*)。</span><span class="sxs-lookup"><span data-stu-id="01a06-142">When you specify a "do not rewrite" list for an ATP Safe Links policy, you can include up to three wildcard asterisks (\*).</span></span> <span data-ttu-id="01a06-143">使用萬用字元 (\*) 例如，假設為項目`contoso.com`，這不明確包含前置詞或子網域，like`http://`或`https://`。</span><span class="sxs-lookup"><span data-stu-id="01a06-143">Wildcards (\*) are assumed for entries such as `contoso.com`, which do not explicitly include prefixes or subdomains, like `http://` or `https://`.</span></span> <span data-ttu-id="01a06-144">這表示項目，例如：`contoso.com`類似於`*contoso.com*`「 不要重寫 」 清單。</span><span class="sxs-lookup"><span data-stu-id="01a06-144">This means an entry, such as `contoso.com` is similar to `*contoso.com*` for your "do not rewrite" list.</span></span>

- <span data-ttu-id="01a06-145">如果您已在 「 不要重寫 」 清單中的 Url 清單，請務必檢閱該清單，並新增為適當的萬用字元。</span><span class="sxs-lookup"><span data-stu-id="01a06-145">If you already have a list of URLs in your "do not rewrite" list, make sure to review that list and add wildcards as appropriate.</span></span> <span data-ttu-id="01a06-146">例如，如果您現有的清單項目 like`http://contoso.com/a`及您想要包含子路徑，例如`http://contoso.com/a/b`在您的原則，萬用字元加入您的項目，讓它看起來像是`http://contoso.com/a*`。</span><span class="sxs-lookup"><span data-stu-id="01a06-146">For example, if your existing list has an entry like `http://contoso.com/a` and you want to include subpaths like `http://contoso.com/a/b` in your policy, add a wildcard to your entry so it looks like `http://contoso.com/a*`.</span></span>
    
- <span data-ttu-id="01a06-147">不要在您指定 「 不要重寫 」 清單中的 Url 中包含正斜線 （/）。</span><span class="sxs-lookup"><span data-stu-id="01a06-147">Do not include a forward slash (/) in the URLs that you specify in your "do not rewrite" list.</span></span> <span data-ttu-id="01a06-148">例如，而不是輸入`contoso.com/`在 「 不要重寫 」 清單中，輸入`contoso.com`。</span><span class="sxs-lookup"><span data-stu-id="01a06-148">For example, rather than enter `contoso.com/` in your "do not rewrite" list, enter `contoso.com`.</span></span>
    
<span data-ttu-id="01a06-149">下列表格清單範例，您可以輸入和功能會影響這些項目有。</span><span class="sxs-lookup"><span data-stu-id="01a06-149">The following table lists examples of what you can enter and what effect those entries have.</span></span>
    
|<span data-ttu-id="01a06-150">**範例項目**</span><span class="sxs-lookup"><span data-stu-id="01a06-150">**Example Entry**</span></span>|<span data-ttu-id="01a06-151">**其用途**</span><span class="sxs-lookup"><span data-stu-id="01a06-151">**What It Does**</span></span>|
|:-----|:-----|
|`*contoso.com*`  <br/> |<span data-ttu-id="01a06-152">允許特定收件者，請造訪網域、 子網域，以及路徑，例如： `http://www.contoso.com`、 `https://www.contoso.com`、 `https://maps.contoso.com`，或`http://www.contoso.com/a`</span><span class="sxs-lookup"><span data-stu-id="01a06-152">Allows specific recipients to visit a domain, subdomains, and paths, such as `http://www.contoso.com`, `https://www.contoso.com`, `https://maps.contoso.com`, or `http://www.contoso.com/a`</span></span>  <br/> |
|`http://contoso.com/a`  <br/> |<span data-ttu-id="01a06-153">可讓特定的收件者，以瀏覽網站，例如`http://contoso.com/a`，但不是個子路徑 like`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="01a06-153">Allows specific recipients to visit a site like `http://contoso.com/a`, but not subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
|`http://contoso.com/a*`  <br/> |<span data-ttu-id="01a06-154">可讓特定的收件者，以瀏覽網站，例如`http://contoso.com/a`和子路徑 like`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="01a06-154">Allows specific recipients to visit a site like `http://contoso.com/a` and subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
   
 