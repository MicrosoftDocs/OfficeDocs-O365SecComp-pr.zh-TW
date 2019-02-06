---
title: 設定自訂封鎖 Url 清單使用 Office 365 ATP 安全連結
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.date: 02/05/2019
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
description: 了解如何設定您的組織使用 Office 365 進階威脅保護封鎖 Url 的清單。封鎖的 Url 將會套用至電子郵件與根據您 ATP 安全連結原則的 Office 文件。
ms.openlocfilehash: 4146424056c9a5b30f51a58fd020df912fa048ef
ms.sourcegitcommit: a64af0ebd0b03e4a5e60a33e9108c44c7d74f356
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2019
ms.locfileid: "29741016"
---
# <a name="set-up-a-custom-blocked-urls-list-using-office-365-atp-safe-links"></a><span data-ttu-id="b442e-104">設定自訂封鎖 Url 清單使用 Office 365 ATP 安全連結</span><span class="sxs-lookup"><span data-stu-id="b442e-104">Set up a custom blocked URLs list using Office 365 ATP Safe Links</span></span>

<span data-ttu-id="b442e-p102">與[Office 365 進階威脅保護](office-365-atp.md)(ATP)，您的組織可以自訂的網站位址 (Url) 會封鎖清單。當封鎖 URL 時，人員封鎖 URL 的連結按一下 [將被帶往類似下列影像[警告] 頁面上](atp-safe-links-warning-pages.md)：</span><span class="sxs-lookup"><span data-stu-id="b442e-p102">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a custom list of website addresses (URLs) that are blocked. When a URL is blocked, people who click on links to the blocked URL are taken to a [warning page](atp-safe-links-warning-pages.md) that resembles the following image:</span></span> 
  
![封鎖此站台](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
<span data-ttu-id="b442e-108">封鎖的 Url 清單定義組織的 Office 365 安全性小組、 與 Office 365 ATP 安全連結原則所涵蓋組織中的每個人都適用於該清單。</span><span class="sxs-lookup"><span data-stu-id="b442e-108">The blocked URLs list is defined by your organization's Office 365 security team, and that list applies to everyone in the organization who is covered by Office 365 ATP Safe Links policies.</span></span> 
  
<span data-ttu-id="b442e-109">閱讀本文以了解如何為[ATP Office 365 中的安全連結](atp-safe-links.md)設定您的組織自訂封鎖 Url 的清單。</span><span class="sxs-lookup"><span data-stu-id="b442e-109">Read this article to learn how to set up your organization's custom blocked URLs list for [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>
  
## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a><span data-ttu-id="b442e-110">檢視或編輯封鎖 Url 的自訂清單</span><span class="sxs-lookup"><span data-stu-id="b442e-110">View or edit a custom list of blocked URLs</span></span>

<span data-ttu-id="b442e-p103">[Office 365 中的 ATP 安全連結](atp-safe-links.md)會使用多個清單，包括您的組織自訂封鎖的 Url 的清單。如果您擁有的必要權限，您可以設定您的組織自訂清單。藉由編輯貴組織的預設安全連結原則達成此目的。</span><span class="sxs-lookup"><span data-stu-id="b442e-p103">[ATP Safe Links in Office 365](atp-safe-links.md) uses several lists, including your organization's custom blocked URLs list. If you have the necessary permissions, you can set up your organization's custom list. You do this by editing your organization's default Safe Links policy.</span></span>

<span data-ttu-id="b442e-114">若要編輯 （或定義） ATP 原則，您必須具有角色如下表所示的其中一個：</span><span class="sxs-lookup"><span data-stu-id="b442e-114">To edit (or define) ATP policies, you must be assigned one of the roles described in the following table:</span></span> 

|<span data-ttu-id="b442e-115">角色</span><span class="sxs-lookup"><span data-stu-id="b442e-115">Role</span></span>  |<span data-ttu-id="b442e-116">Where/如何指派</span><span class="sxs-lookup"><span data-stu-id="b442e-116">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="b442e-117">Office 365 全域管理員</span><span class="sxs-lookup"><span data-stu-id="b442e-117">Office 365 Global Administrator</span></span> |<span data-ttu-id="b442e-p104">若要購買 Office 365 設定簽署者為預設的全域系統管理員。（請參閱若要深入了[解 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)）。</span><span class="sxs-lookup"><span data-stu-id="b442e-p104">The person who signs up to buy Office 365 is a global admin by default. (See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="b442e-120">Office 365 安全性管理員</span><span class="sxs-lookup"><span data-stu-id="b442e-120">Office 365 Security Administrator</span></span> |<span data-ttu-id="b442e-121">系統管理中心 ([https://aka.ms/admincenter](https://aka.ms/admincenter))</span><span class="sxs-lookup"><span data-stu-id="b442e-121">Admin center ([https://aka.ms/admincenter](https://aka.ms/admincenter))</span></span>|
|<span data-ttu-id="b442e-122">Exchange Online 組織管理</span><span class="sxs-lookup"><span data-stu-id="b442e-122">Exchange Online Organization Management</span></span> |<span data-ttu-id="b442e-123">Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="b442e-123">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="b442e-124">或</span><span class="sxs-lookup"><span data-stu-id="b442e-124">or</span></span> <br>  <span data-ttu-id="b442e-125">PowerShell cmdlet (請參閱[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span><span class="sxs-lookup"><span data-stu-id="b442e-125">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span></span> |
  
1. <span data-ttu-id="b442e-126">移至 [[https://protection.office.com](https://protection.office.com)和登入工作或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="b442e-126">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="b442e-127">在左導覽列中， **Threat management**] 下選擇 [**原則** \> **安全的連結**。</span><span class="sxs-lookup"><span data-stu-id="b442e-127">In the left navigation, under **Threat management**, choose **Policy** \> **Safe Links**.</span></span>
    
3. <span data-ttu-id="b442e-128">**套用至整個組織的原則**] 區段中選取 [**預設**]，然後選擇**編輯**（[編輯] 按鈕以鉛筆）。</span><span class="sxs-lookup"><span data-stu-id="b442e-128">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span><br/><span data-ttu-id="b442e-129">![按一下 [編輯] 以編輯您的預設原則的安全連結保護](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span><span class="sxs-lookup"><span data-stu-id="b442e-129">![Click Edit to edit your default policy for Safe Links protection](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span></span><br/><span data-ttu-id="b442e-p105">這可讓您檢視您的封鎖 Url 的清單。在第一，您可能沒有任何此處所列的 Url。</span><span class="sxs-lookup"><span data-stu-id="b442e-p105">This enables you to view your list of blocked URLs. At first, you might not have any URLs listed here.</span></span><br/><span data-ttu-id="b442e-132">![封鎖預設的安全連結原則中的 Url 清單](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span><span class="sxs-lookup"><span data-stu-id="b442e-132">![Blocked URLs list in the default Safe Links policy](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span></span>
  
4. <span data-ttu-id="b442e-133">選取**輸入有效的 URL** ] 方塊中，輸入 URL，然後選擇 [加號 (**+**)。</span><span class="sxs-lookup"><span data-stu-id="b442e-133">Select the **Enter a valid URL** box, type a URL, and then choose the plus sign (**+**).</span></span> 

5. <span data-ttu-id="b442e-134">在螢幕右下角新增 Url、 完成時，選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="b442e-134">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>
    
## <a name="a-few-things-to-keep-in-mind"></a><span data-ttu-id="b442e-135">牢記的一些事項</span><span class="sxs-lookup"><span data-stu-id="b442e-135">A few things to keep in mind</span></span>

<span data-ttu-id="b442e-136">當您新增到清單的 Url 時，請記住以下幾點：</span><span class="sxs-lookup"><span data-stu-id="b442e-136">While you add URLs to your list, keep the following points in mind:</span></span> 

- <span data-ttu-id="b442e-p106">不包含正斜線 ( **/**) 結尾的 URL。例如，而不是輸入`http://www.contoso.com/`、 輸入`http://www.contoso.com`。</span><span class="sxs-lookup"><span data-stu-id="b442e-p106">Do not include a forward slash ( **/**) at the end of the URL. For example, instead of entering `http://www.contoso.com/`, enter `http://www.contoso.com`.</span></span>
    
- <span data-ttu-id="b442e-p107">您可以指定僅限網域的 URL (例如`contoso.com`或`tailspintoys.com`)。這將會封鎖點閱上任何包含網域的 URL。</span><span class="sxs-lookup"><span data-stu-id="b442e-p107">You can specify a domain-only URL (like `contoso.com` or `tailspintoys.com`). This will block clicks on any URL that contains the domain.</span></span>

- <span data-ttu-id="b442e-p108">您可以指定子網域 (例如`toys.contoso.com*`) 而不會封鎖的完整網域 (類似`contoso.com`)。這會封鎖按一下任何 URL 包含子網域，但它不會封鎖點閱到包含完整的網域的 URL。</span><span class="sxs-lookup"><span data-stu-id="b442e-p108">You can specify a subdomain (like `toys.contoso.com*`) without blocking a full domain (like `contoso.com`). This will block clicks any URL that contains the subdomain, but it won't block clicks to a URL that contains the full domain.</span></span>  
    
- <span data-ttu-id="b442e-p109">您可以包含多達三個萬用字元星號 (\*) 每個 URL。下表列出有一些您可以輸入及什麼 effect 這些項目範例。</span><span class="sxs-lookup"><span data-stu-id="b442e-p109">You can include up to three wildcard asterisks (\*) per URL. The following table lists some examples of what you can enter and what effect those entries have.</span></span>
    
|<span data-ttu-id="b442e-145">**範例項目**</span><span class="sxs-lookup"><span data-stu-id="b442e-145">**Example Entry**</span></span>|<span data-ttu-id="b442e-146">**及其作用**</span><span class="sxs-lookup"><span data-stu-id="b442e-146">**What It Does**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b442e-147">`contoso.com`或`*contoso.com*`</span><span class="sxs-lookup"><span data-stu-id="b442e-147">`contoso.com` or `*contoso.com*`</span></span>  <br/> |<span data-ttu-id="b442e-148">封鎖的網域子網域，且路徑，例如`https://www.contoso.com`、 `http://sub.contoso.com`、 和`http://contoso.com/abc`</span><span class="sxs-lookup"><span data-stu-id="b442e-148">Blocks the domain, subdomains, and paths, such as `https://www.contoso.com`, `http://sub.contoso.com`, and `http://contoso.com/abc`</span></span>  <br/> |
|`http://contoso.com/a`  <br/> |<span data-ttu-id="b442e-149">封鎖網站`http://contoso.com/a`但沒有其他子路徑 like`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="b442e-149">Blocks a site `http://contoso.com/a` but not additional subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
|`http://contoso.com/a*`  <br/> |<span data-ttu-id="b442e-150">封鎖網站`http://contoso.com/a`及其他子路徑 like`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="b442e-150">Blocks a site `http://contoso.com/a` and additional subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
|`http://toys.contoso.com*`  <br/> |<span data-ttu-id="b442e-151">封鎖的子網域 (在此例中為"toys") 但允許點選其他網域的 url (例如`http://contoso.com`或`http://home.contoso.com`)。</span><span class="sxs-lookup"><span data-stu-id="b442e-151">Blocks a subdomain ("toys" in this case) but allow clicks to other domain URLs (like `http://contoso.com` or `http://home.contoso.com`).</span></span>  <br/> |
   

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a><span data-ttu-id="b442e-152">如何在組織中定義的特定使用者的例外狀況</span><span class="sxs-lookup"><span data-stu-id="b442e-152">How to define exceptions for certain users in an organization</span></span>

<span data-ttu-id="b442e-p110">如果您想要能夠檢視 Url 可能會封鎖其他人的特定群組，您可以指定套用至特定收件者 ATP 安全連結原則。請參閱 ＜ [Set up 自訂 「 未修正"Url 清單使用 ATP 安全的連結](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="b442e-p110">If you want certain groups to be able to view URLs that might be blocked for others, you can specify an ATP Safe Links policy that applies to specific recipients. See [Set up a custom "do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
  

