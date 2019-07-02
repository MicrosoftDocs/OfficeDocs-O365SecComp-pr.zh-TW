---
title: 使用 Office 365 ATP 安全連結設定自訂封鎖的 Url 清單
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
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
ms.collection:
- M365-security-compliance
description: 瞭解如何使用 Office 365 高級威脅防護來設定組織的封鎖 Url 清單。 封鎖的 Url 會根據您的 ATP 安全連結原則, 套用至電子郵件和 Office 檔。
ms.openlocfilehash: 4856d0ae76318c99a9c9c2404ef8a4cd700e4953
ms.sourcegitcommit: 4fedeb06a6e7796096fc6279cfb091c7b89d484d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/31/2019
ms.locfileid: "34652716"
---
# <a name="set-up-a-custom-blocked-urls-list-using-office-365-atp-safe-links"></a><span data-ttu-id="4db54-104">使用 Office 365 ATP 安全連結設定自訂封鎖的 Url 清單</span><span class="sxs-lookup"><span data-stu-id="4db54-104">Set up a custom blocked URLs list using Office 365 ATP Safe Links</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4db54-105">本文適用于擁有[Office 365 高級威脅防護](office-365-atp.md)的商務客戶。</span><span class="sxs-lookup"><span data-stu-id="4db54-105">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="4db54-106">如果您是尋找 Outlook 中安全連結相關資訊的家庭使用者, 請參閱[Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="4db54-106">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="4db54-107">透過[Office 365 高級威脅防護](office-365-atp.md)(ATP), 您的組織可以有已封鎖的網站位址 (url) 自訂清單。</span><span class="sxs-lookup"><span data-stu-id="4db54-107">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a custom list of website addresses (URLs) that are blocked.</span></span> <span data-ttu-id="4db54-108">當鎖定 URL 時, 按一下封鎖 URL 連結的人員會進入[警告頁面](atp-safe-links-warning-pages.md), 如下圖所示:</span><span class="sxs-lookup"><span data-stu-id="4db54-108">When a URL is blocked, people who click on links to the blocked URL are taken to a [warning page](atp-safe-links-warning-pages.md) that resembles the following image:</span></span> 
  
![此網站被封鎖](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
<span data-ttu-id="4db54-110">封鎖的 Url 清單是由貴組織的 Office 365 安全小組所定義, 而且此清單適用于 Office 365 ATP 安全連結原則所涵蓋的組織中的所有人。</span><span class="sxs-lookup"><span data-stu-id="4db54-110">The blocked URLs list is defined by your organization's Office 365 security team, and that list applies to everyone in the organization who is covered by Office 365 ATP Safe Links policies.</span></span> 
  
<span data-ttu-id="4db54-111">如需瞭解如何為[Office 365 中的 ATP 安全連結](atp-safe-links.md)設定您組織的自訂封鎖 url 清單, 請閱讀本文。</span><span class="sxs-lookup"><span data-stu-id="4db54-111">Read this article to learn how to set up your organization's custom blocked URLs list for [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>
  
## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a><span data-ttu-id="4db54-112">查看或編輯已封鎖 Url 的自訂清單</span><span class="sxs-lookup"><span data-stu-id="4db54-112">View or edit a custom list of blocked URLs</span></span>

<span data-ttu-id="4db54-113">[Office 365 中的 ATP 安全連結](atp-safe-links.md)使用數個清單, 包括您組織的自訂封鎖 url 清單。</span><span class="sxs-lookup"><span data-stu-id="4db54-113">[ATP Safe Links in Office 365](atp-safe-links.md) uses several lists, including your organization's custom blocked URLs list.</span></span> <span data-ttu-id="4db54-114">如果您有必要的許可權, 您可以設定您組織的自訂清單。</span><span class="sxs-lookup"><span data-stu-id="4db54-114">If you have the necessary permissions, you can set up your organization's custom list.</span></span> <span data-ttu-id="4db54-115">您可以編輯組織的預設安全連結原則來執行這項操作。</span><span class="sxs-lookup"><span data-stu-id="4db54-115">You do this by editing your organization's default Safe Links policy.</span></span>

<span data-ttu-id="4db54-116">若要編輯 (或定義) ATP 原則, 您必須獲指派下表所述的其中一個角色:</span><span class="sxs-lookup"><span data-stu-id="4db54-116">To edit (or define) ATP policies, you must be assigned one of the roles described in the following table:</span></span> 

|<span data-ttu-id="4db54-117">角色</span><span class="sxs-lookup"><span data-stu-id="4db54-117">Role</span></span>  |<span data-ttu-id="4db54-118">指派的位置/方式</span><span class="sxs-lookup"><span data-stu-id="4db54-118">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="4db54-119">Office 365 全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="4db54-119">Office 365 Global Administrator</span></span> |<span data-ttu-id="4db54-120">註冊購買 Office 365 的人員預設為全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="4db54-120">The person who signs up to buy Office 365 is a global admin by default.</span></span> <span data-ttu-id="4db54-121">(請參閱[關於 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)以深入瞭解。)</span><span class="sxs-lookup"><span data-stu-id="4db54-121">(See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="4db54-122">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="4db54-122">Security Administrator</span></span> |<span data-ttu-id="4db54-123">Azure Active Directory 系統管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="4db54-123">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="4db54-124">Exchange Online 組織管理</span><span class="sxs-lookup"><span data-stu-id="4db54-124">Exchange Online Organization Management</span></span> |<span data-ttu-id="4db54-125">Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="4db54-125">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="4db54-126">或</span><span class="sxs-lookup"><span data-stu-id="4db54-126">or</span></span> <br>  <span data-ttu-id="4db54-127">PowerShell Cmdlet (請參閱[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span><span class="sxs-lookup"><span data-stu-id="4db54-127">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span></span> |

> [!TIP]
> <span data-ttu-id="4db54-128">若要深入瞭解角色和許可權, 請參閱[Office 365 安全性&amp;與合規性中心的許可權](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="4db54-128">To learn more about roles and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="to-view-or-edit-a-custom-blocked-urls-list"></a><span data-ttu-id="4db54-129">若要查看或編輯自訂封鎖的 Url 清單</span><span class="sxs-lookup"><span data-stu-id="4db54-129">To view or edit a custom blocked URLs list</span></span>
  
1. <span data-ttu-id="4db54-130">移至[https://protection.office.com](https://protection.office.com) , 並使用您的公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="4db54-130">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="4db54-131">在左側導覽中的 [**威脅管理**] 下, 選擇 [**原則** \> **安全連結**]。</span><span class="sxs-lookup"><span data-stu-id="4db54-131">In the left navigation, under **Threat management**, choose **Policy** \> **Safe Links**.</span></span>
    
3. <span data-ttu-id="4db54-132">在 [**適用于整個組織的原則**] 區段中, 選取 [**預設**], \*\*\*\* 然後選擇 [編輯] ([編輯] 按鈕就像是鉛筆)。</span><span class="sxs-lookup"><span data-stu-id="4db54-132">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span><br/><span data-ttu-id="4db54-133">![按一下 [編輯] 以編輯安全連結保護的預設原則](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span><span class="sxs-lookup"><span data-stu-id="4db54-133">![Click Edit to edit your default policy for Safe Links protection](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span></span><br/><span data-ttu-id="4db54-134">這可讓您查看封鎖的 Url 清單。</span><span class="sxs-lookup"><span data-stu-id="4db54-134">This enables you to view your list of blocked URLs.</span></span> <span data-ttu-id="4db54-135">首先, 您可能不會在這裡列出任何 Url。</span><span class="sxs-lookup"><span data-stu-id="4db54-135">At first, you might not have any URLs listed here.</span></span><br/><span data-ttu-id="4db54-136">![預設安全連結原則中的封鎖 Url 清單](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span><span class="sxs-lookup"><span data-stu-id="4db54-136">![Blocked URLs list in the default Safe Links policy](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span></span>
  
4. <span data-ttu-id="4db54-137">選取 [**輸入有效的 url** ] 方塊, 輸入 URL, 然後選擇加號 (**+**)。</span><span class="sxs-lookup"><span data-stu-id="4db54-137">Select the **Enter a valid URL** box, type a URL, and then choose the plus sign (**+**).</span></span> 

5. <span data-ttu-id="4db54-138">完成新增 Url 之後, 請在螢幕的右下角選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="4db54-138">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>
    
## <a name="a-few-things-to-keep-in-mind"></a><span data-ttu-id="4db54-139">請記住一些事項</span><span class="sxs-lookup"><span data-stu-id="4db54-139">A few things to keep in mind</span></span>

<span data-ttu-id="4db54-140">當您將 Url 新增至清單時, 請牢記下列要點:</span><span class="sxs-lookup"><span data-stu-id="4db54-140">While you add URLs to your list, keep the following points in mind:</span></span> 

- <span data-ttu-id="4db54-141">不要在 URL 的結尾加入正**/** 斜線 ()。</span><span class="sxs-lookup"><span data-stu-id="4db54-141">Do not include a forward slash ( **/**) at the end of the URL.</span></span> <span data-ttu-id="4db54-142">例如, 您不用輸入`http://www.contoso.com/`, 而是`http://www.contoso.com`輸入。</span><span class="sxs-lookup"><span data-stu-id="4db54-142">For example, instead of entering `http://www.contoso.com/`, enter `http://www.contoso.com`.</span></span>
    
- <span data-ttu-id="4db54-143">您可以指定僅限網域的 URL (例如`contoso.com`或`tailspintoys.com`)。</span><span class="sxs-lookup"><span data-stu-id="4db54-143">You can specify a domain-only URL (like `contoso.com` or `tailspintoys.com`).</span></span> <span data-ttu-id="4db54-144">這會封鎖任何包含網域的 URL 上的按一下。</span><span class="sxs-lookup"><span data-stu-id="4db54-144">This will block clicks on any URL that contains the domain.</span></span>

- <span data-ttu-id="4db54-145">您可以指定子域 (如`toys.contoso.com*`), 但不封鎖完整網域 (例如`contoso.com`)。</span><span class="sxs-lookup"><span data-stu-id="4db54-145">You can specify a subdomain (like `toys.contoso.com*`) without blocking a full domain (like `contoso.com`).</span></span> <span data-ttu-id="4db54-146">這會封鎖按一下任何包含子域的 URL, 但不會封鎖按一下包含完整網域的 URL。</span><span class="sxs-lookup"><span data-stu-id="4db54-146">This will block clicks any URL that contains the subdomain, but it won't block clicks to a URL that contains the full domain.</span></span>  
    
- <span data-ttu-id="4db54-147">每個 URL 最多可以包含三個\*萬用字元星號 ()。</span><span class="sxs-lookup"><span data-stu-id="4db54-147">You can include up to three wildcard asterisks (\*) per URL.</span></span> <span data-ttu-id="4db54-148">下表列出您可以輸入之專案的一些範例, 以及這些專案有何影響。</span><span class="sxs-lookup"><span data-stu-id="4db54-148">The following table lists some examples of what you can enter and what effect those entries have.</span></span>
    
|<span data-ttu-id="4db54-149">**範例專案**</span><span class="sxs-lookup"><span data-stu-id="4db54-149">**Example Entry**</span></span>|<span data-ttu-id="4db54-150">**功能**</span><span class="sxs-lookup"><span data-stu-id="4db54-150">**What It Does**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4db54-151">`contoso.com` 或 `*contoso.com*`</span><span class="sxs-lookup"><span data-stu-id="4db54-151">`contoso.com` or `*contoso.com*`</span></span>  <br/> |<span data-ttu-id="4db54-152">封鎖網域、子域及路徑, 例如`https://www.contoso.com`、和`http://sub.contoso.com``http://contoso.com/abc`</span><span class="sxs-lookup"><span data-stu-id="4db54-152">Blocks the domain, subdomains, and paths, such as `https://www.contoso.com`, `http://sub.contoso.com`, and `http://contoso.com/abc`</span></span>  <br/> |
|`http://contoso.com/a`  <br/> |<span data-ttu-id="4db54-153">封鎖網站`http://contoso.com/a` , 但不會封鎖其他的子路徑, 如`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="4db54-153">Blocks a site `http://contoso.com/a` but not additional subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
|`http://contoso.com/a*`  <br/> |<span data-ttu-id="4db54-154">封鎖網站`http://contoso.com/a`和其他子路徑, 如`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="4db54-154">Blocks a site `http://contoso.com/a` and additional subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
|`http://toys.contoso.com*`  <br/> |<span data-ttu-id="4db54-155">封鎖子域 (在此情況下為 "玩具"), 但允許按一下其他網域 Url ( `http://contoso.com`如`http://home.contoso.com`或)。</span><span class="sxs-lookup"><span data-stu-id="4db54-155">Blocks a subdomain ("toys" in this case) but allow clicks to other domain URLs (like `http://contoso.com` or `http://home.contoso.com`).</span></span>  <br/> |
   

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a><span data-ttu-id="4db54-156">如何為組織中的特定使用者定義例外狀況</span><span class="sxs-lookup"><span data-stu-id="4db54-156">How to define exceptions for certain users in an organization</span></span>

<span data-ttu-id="4db54-157">如果您想要讓某些群組能夠查看其他人可能會封鎖的 Url, 您可以指定適用于特定收件者的 ATP 安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="4db54-157">If you want certain groups to be able to view URLs that might be blocked for others, you can specify an ATP Safe Links policy that applies to specific recipients.</span></span> <span data-ttu-id="4db54-158">請參閱[設定自訂「不要重寫」 url 清單使用 ATP 安全連結](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="4db54-158">See [Set up a custom "do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
  

