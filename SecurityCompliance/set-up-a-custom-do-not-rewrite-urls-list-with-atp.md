---
title: 使用 Office 365 ATP 安全連結, 設定自訂的不重新寫入 Url 清單
ms.author: deniseb
author: denisebmsft
manager: laurawi
audience: Admin
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
description: 當您設定 ATP 安全連結原則時, 可以包含 [不修正] 的 Url 清單, 讓組織中的某些人能夠造訪您的清單中所包含的網站。
ms.openlocfilehash: a7f8f041832d7d5935ea959073d2b11cc6bdcf53
ms.sourcegitcommit: 4fedeb06a6e7796096fc6279cfb091c7b89d484d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/31/2019
ms.locfileid: "34652726"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-office-365-atp-safe-links"></a><span data-ttu-id="41873-103">使用 Office 365 ATP 安全連結, 設定自訂的不重新寫入 Url 清單</span><span class="sxs-lookup"><span data-stu-id="41873-103">Set up a custom do-not-rewrite URLs list using Office 365 ATP Safe Links</span></span>

> [!IMPORTANT]
> <span data-ttu-id="41873-104">本文適用于擁有[Office 365 高級威脅防護](office-365-atp.md)的商務客戶。</span><span class="sxs-lookup"><span data-stu-id="41873-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="41873-105">如果您是尋找 Outlook 中安全連結相關資訊的家庭使用者, 請參閱[Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="41873-105">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="41873-106">透過[Office 365 高級威脅防護](office-365-atp.md)(ATP), 您的組織可以有[自訂封鎖的 url](set-up-a-custom-blocked-urls-list-wtih-atp.md), 例如, 當使用者按一下電子郵件訊息或特定 Office 檔中的網頁位址 (url) 時, 這些 url 就不會傳送至這些 url。</span><span class="sxs-lookup"><span data-stu-id="41873-106">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a [custom blocked URLs](set-up-a-custom-blocked-urls-list-wtih-atp.md), such that when people click on web addresses (URLs) in email messages or certain Office documents, they are prevented from going to those URLs.</span></span> <span data-ttu-id="41873-107">您的組織也可以為組織中的特定群組提供自訂「不要重寫」清單。</span><span class="sxs-lookup"><span data-stu-id="41873-107">Your organization can also have custom "do not rewrite" lists for specific groups in your organization.</span></span> <span data-ttu-id="41873-108">「不要重新寫入」清單可讓某些人造訪[Office 365 中的 ATP 安全連結](atp-safe-links.md)所封鎖的 url。</span><span class="sxs-lookup"><span data-stu-id="41873-108">A "do not rewrite" list enables some people to visit URLs that are otherwise blocked by [ATP Safe Links in Office 365](atp-safe-links.md).</span></span> 
  
<span data-ttu-id="41873-109">本文說明如何指定從 ATP 安全連結掃描中排除的 Url 清單, 以及請記住的一些重要要點。</span><span class="sxs-lookup"><span data-stu-id="41873-109">This article describes how to specify a list of URLs that are excluded from ATP Safe Links scanning, and a few important points to keep in mind.</span></span>

## <a name="set-up-a-do-not-rewrite-list"></a><span data-ttu-id="41873-110">設定「不要重寫」清單</span><span class="sxs-lookup"><span data-stu-id="41873-110">Set up a "do not rewrite" list</span></span>

<span data-ttu-id="41873-111">ATP 安全連結保護使用數個清單, 包括您組織的封鎖 Url 清單和「不要重寫」清單中的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="41873-111">ATP Safe Links protection uses several lists, including your organization's blocked URLs list and the "do not rewrite" lists for exceptions.</span></span> <span data-ttu-id="41873-112">如果您有必要的許可權, 您可以設定您的自訂「不要重寫」清單。</span><span class="sxs-lookup"><span data-stu-id="41873-112">If you have the necessary permissions, you can set up your custom "do not rewrite" lists.</span></span> <span data-ttu-id="41873-113">當您新增或編輯適用于組織中特定收件者的安全連結原則時, 就會執行此動作。</span><span class="sxs-lookup"><span data-stu-id="41873-113">You do this when you add or edit Safe Links policies that apply to specific recipients in your organization.</span></span> 

<span data-ttu-id="41873-114">若要編輯 (或定義) ATP 原則, 您必須獲指派下表所述的其中一個角色:</span><span class="sxs-lookup"><span data-stu-id="41873-114">To edit (or define) ATP policies, you must be assigned one of the roles described in the following table:</span></span>

|<span data-ttu-id="41873-115">角色</span><span class="sxs-lookup"><span data-stu-id="41873-115">Role</span></span>  |<span data-ttu-id="41873-116">指派的位置/方式</span><span class="sxs-lookup"><span data-stu-id="41873-116">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="41873-117">Office 365 全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="41873-117">Office 365 Global Administrator</span></span> |<span data-ttu-id="41873-118">註冊購買 Office 365 的人員預設為全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="41873-118">The person who signs up to buy Office 365 is a global admin by default.</span></span> <span data-ttu-id="41873-119">(請參閱[關於 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)以深入瞭解。)</span><span class="sxs-lookup"><span data-stu-id="41873-119">(See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="41873-120">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="41873-120">Security Administrator</span></span> |<span data-ttu-id="41873-121">Azure Active Directory 系統管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="41873-121">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="41873-122">Exchange Online 組織管理</span><span class="sxs-lookup"><span data-stu-id="41873-122">Exchange Online Organization Management</span></span> |<span data-ttu-id="41873-123">Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="41873-123">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="41873-124">或</span><span class="sxs-lookup"><span data-stu-id="41873-124">or</span></span> <br>  <span data-ttu-id="41873-125">PowerShell Cmdlet (請參閱[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span><span class="sxs-lookup"><span data-stu-id="41873-125">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span></span> |

> [!TIP]
> <span data-ttu-id="41873-126">若要深入瞭解角色和許可權, 請參閱[Office 365 安全性&amp;與合規性中心的許可權](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="41873-126">To learn more about roles and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="to-view-or-edit-a-custom-do-not-rewrite-urls-list"></a><span data-ttu-id="41873-127">若要查看或編輯自訂「不要重寫」 Url 清單</span><span class="sxs-lookup"><span data-stu-id="41873-127">To view or edit a custom "do not rewrite" URLs list</span></span>
  
1. <span data-ttu-id="41873-128">移至[https://protection.office.com](https://protection.office.com) , 並使用您的公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="41873-128">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="41873-129">在左側導覽中, 在 [**威脅管理** \> **原則** \> **安全連結**] 底下。</span><span class="sxs-lookup"><span data-stu-id="41873-129">In the left navigation, under **Threat management** \> **Policy** \> **Safe Links**.</span></span>
    
3. <span data-ttu-id="41873-130">在 [套用**至特定**收件者的原則] 區段中, 選擇 [**新增**] ([新增**+**] 按鈕類似加號 ()) 來建立新的原則。</span><span class="sxs-lookup"><span data-stu-id="41873-130">In the **Policies that apply to specific recipients** section, choose **New** (the New button resembles a plus sign ( **+**)) to create a new policy.</span></span> <span data-ttu-id="41873-131">(或者, 您也可以編輯現有的原則)。</span><span class="sxs-lookup"><span data-stu-id="41873-131">(Alternatively, you can edit an existing policy.)</span></span><br/><span data-ttu-id="41873-132">![選擇 [新增] 以新增特定電子郵件收件者的安全連結原則](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span><span class="sxs-lookup"><span data-stu-id="41873-132">![Choose New to add a Safe Links policy for specific email recipients](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span></span>
  
4. <span data-ttu-id="41873-133">指定原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="41873-133">Specify a name and description for your policy.</span></span>
    
5. <span data-ttu-id="41873-134">在 [**不要重新寫入下列 url** ] 區段中, 選取 [**輸入有效的 url** ] 方塊, 然後輸入 URL, 然後選擇加號 (+)。</span><span class="sxs-lookup"><span data-stu-id="41873-134">In the **Do not rewrite the following URLs** section, select the **Enter a valid URL** box, and then type a URL, and then choose the plus sign (+).</span></span> 
    
6. <span data-ttu-id="41873-135">在 [套用**至**] 區段中, 選擇 [**收件者是的成員**], 然後選擇您要包含在原則中的群組。</span><span class="sxs-lookup"><span data-stu-id="41873-135">In the **Applied To** section, choose **The recipient is a member of**, and then choose the group(s) you want to include in your policy.</span></span> <span data-ttu-id="41873-136">選擇 [**新增**], 然後選擇 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="41873-136">Choose **Add**, and then choose **OK**.</span></span>
    
7. <span data-ttu-id="41873-137">完成新增 Url 之後, 請在螢幕的右下角選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="41873-137">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="41873-138">請務必檢查您組織的已封鎖 Url 的自訂清單。</span><span class="sxs-lookup"><span data-stu-id="41873-138">Make sure to review your organization's custom list of blocked URLs.</span></span> <span data-ttu-id="41873-139">請參閱[使用 ATP 安全連結設定自訂封鎖的 url 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="41873-139">See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).</span></span> 
  
## <a name="important-points-to-keep-in-mind"></a><span data-ttu-id="41873-140">需要記住的重要要點</span><span class="sxs-lookup"><span data-stu-id="41873-140">Important points to keep in mind</span></span>

- <span data-ttu-id="41873-141">您在「不要重寫」清單中指定的任何 Url 都會從 ATP 安全連結中排除, 以掃描您指定的收件者。</span><span class="sxs-lookup"><span data-stu-id="41873-141">Any URLs that you specify in the "do not rewrite" list are excluded from ATP Safe Links scanning for the recipients that you specify.</span></span>
 
- <span data-ttu-id="41873-142">當您為 ATP 安全連結原則指定「不要重寫」清單時, 最多可以包含三個萬用字元星號 (\*)。</span><span class="sxs-lookup"><span data-stu-id="41873-142">When you specify a "do not rewrite" list for an ATP Safe Links policy, you can include up to three wildcard asterisks (\*).</span></span> <span data-ttu-id="41873-143">會假設\*萬用字元 () `contoso.com`, 例如, 不明確包含首碼或子域之類的專案, 例如`http://`或。 `https://`</span><span class="sxs-lookup"><span data-stu-id="41873-143">Wildcards (\*) are assumed for entries such as `contoso.com`, which do not explicitly include prefixes or subdomains, like `http://` or `https://`.</span></span> <span data-ttu-id="41873-144">這表示專案, 例如`contoso.com`類似于您`*contoso.com*`的「不要重寫」清單。</span><span class="sxs-lookup"><span data-stu-id="41873-144">This means an entry, such as `contoso.com` is similar to `*contoso.com*` for your "do not rewrite" list.</span></span>

- <span data-ttu-id="41873-145">如果您的 [不要重新寫入] 清單中已經有 Url 清單, 請務必檢查該清單, 並視需要新增萬用字元。</span><span class="sxs-lookup"><span data-stu-id="41873-145">If you already have a list of URLs in your "do not rewrite" list, make sure to review that list and add wildcards as appropriate.</span></span> <span data-ttu-id="41873-146">例如, 如果您現有的清單中有類似`http://contoso.com/a`的專案, 而且您想要在`http://contoso.com/a/b`您的原則中包含類似的子路徑, 請在您的`http://contoso.com/a*`專案中新增萬用字元, 讓它看起來像這樣。</span><span class="sxs-lookup"><span data-stu-id="41873-146">For example, if your existing list has an entry like `http://contoso.com/a` and you want to include subpaths like `http://contoso.com/a/b` in your policy, add a wildcard to your entry so it looks like `http://contoso.com/a*`.</span></span>
    
- <span data-ttu-id="41873-147">不要在您在「不要重寫」清單中指定的 Url 中包含正斜線 (/)。</span><span class="sxs-lookup"><span data-stu-id="41873-147">Do not include a forward slash (/) in the URLs that you specify in your "do not rewrite" list.</span></span> <span data-ttu-id="41873-148">例如, 請輸入`contoso.com/` `contoso.com`, 而不是在「不要重寫」清單中輸入。</span><span class="sxs-lookup"><span data-stu-id="41873-148">For example, rather than enter `contoso.com/` in your "do not rewrite" list, enter `contoso.com`.</span></span>
    
<span data-ttu-id="41873-149">下表列出您可以輸入之專案的範例, 以及這些專案有何影響。</span><span class="sxs-lookup"><span data-stu-id="41873-149">The following table lists examples of what you can enter and what effect those entries have.</span></span>
    
|<span data-ttu-id="41873-150">**範例專案**</span><span class="sxs-lookup"><span data-stu-id="41873-150">**Example Entry**</span></span>|<span data-ttu-id="41873-151">**功能**</span><span class="sxs-lookup"><span data-stu-id="41873-151">**What It Does**</span></span>|
|:-----|:-----|
|`*contoso.com*`  <br/> |<span data-ttu-id="41873-152">允許特定收件者造訪網域、子域和路徑, 例如`http://www.contoso.com`、 `https://www.contoso.com` `https://maps.contoso.com`、或`http://www.contoso.com/a`</span><span class="sxs-lookup"><span data-stu-id="41873-152">Allows specific recipients to visit a domain, subdomains, and paths, such as `http://www.contoso.com`, `https://www.contoso.com`, `https://maps.contoso.com`, or `http://www.contoso.com/a`</span></span>  <br/> |
|`http://contoso.com/a`  <br/> |<span data-ttu-id="41873-153">允許特定收件者造訪類似`http://contoso.com/a`的網站, 但不允許像這樣的子路徑`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="41873-153">Allows specific recipients to visit a site like `http://contoso.com/a`, but not subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
|`http://contoso.com/a*`  <br/> |<span data-ttu-id="41873-154">允許特定的收件者造訪像`http://contoso.com/a`這樣的子網站和子路徑`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="41873-154">Allows specific recipients to visit a site like `http://contoso.com/a` and subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
   
 