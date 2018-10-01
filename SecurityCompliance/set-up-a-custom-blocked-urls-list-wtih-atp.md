---
title: 設定自訂封鎖 Url 清單使用 Office 365 ATP 安全連結
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
description: 閱讀本文以了解如何設定您的組織使用 Office 365 進階威脅保護封鎖 Url 的清單。封鎖的 Url 將會套用至電子郵件與根據您 ATP 安全連結原則的 Office 文件。
ms.openlocfilehash: 36d295e6924d2e9972c185657885fa25bd96bf08
ms.sourcegitcommit: 7032830867eb3fc71760e04b8342aff174c5d757
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/01/2018
ms.locfileid: "25353249"
---
# <a name="set-up-a-custom-blocked-urls-list-using-office-365-atp-safe-links"></a><span data-ttu-id="4a5ab-104">設定自訂封鎖 Url 清單使用 Office 365 ATP 安全連結</span><span class="sxs-lookup"><span data-stu-id="4a5ab-104">Set up a custom blocked URLs list using Office 365 ATP Safe Links</span></span>

<span data-ttu-id="4a5ab-p102">與[Office 365 進階威脅保護](office-365-atp.md)(ATP)，您的組織可以自訂的網站位址 (Url) 會封鎖清單。當封鎖 URL 時，人員封鎖 URL 的連結按一下 [將被帶往類似下列影像[警告] 頁面上](atp-safe-links-warning-pages.md)：</span><span class="sxs-lookup"><span data-stu-id="4a5ab-p102">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a custom list of website addresses (URLs) that are blocked. When a URL is blocked, people who click on links to the blocked URL are taken to a [warning page](atp-safe-links-warning-pages.md) that resembles the following image:</span></span> 
  
![封鎖此站台](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
<span data-ttu-id="4a5ab-108">封鎖的 Url 清單定義組織的 Office 365 安全性小組、 與 Office 365 ATP 安全連結原則所涵蓋組織中的每個人都適用於該清單。</span><span class="sxs-lookup"><span data-stu-id="4a5ab-108">The blocked URLs list is defined by your organization's Office 365 security team, and that list applies to everyone in the organization who is covered by Office 365 ATP Safe Links policies.</span></span> 
  
<span data-ttu-id="4a5ab-109">閱讀本文以了解如何為[ATP Office 365 中的安全連結](atp-safe-links.md)設定您的組織自訂封鎖 Url 的清單。</span><span class="sxs-lookup"><span data-stu-id="4a5ab-109">Read this article to learn how to set up your organization's custom blocked URLs list for [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>
  
## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a><span data-ttu-id="4a5ab-110">檢視或編輯封鎖 Url 的自訂清單</span><span class="sxs-lookup"><span data-stu-id="4a5ab-110">View or edit a custom list of blocked URLs</span></span>

<span data-ttu-id="4a5ab-p103">[Office 365 中的 ATP 安全連結](atp-safe-links.md)會使用多個清單，包括您的組織自訂封鎖的 Url 的清單。如果您擁有的必要權限，您可以設定您的組織自訂清單。藉由編輯貴組織的預設安全連結原則達成此目的。</span><span class="sxs-lookup"><span data-stu-id="4a5ab-p103">[ATP Safe Links in Office 365](atp-safe-links.md) uses several lists, including your organization's custom blocked URLs list. If you have the necessary permissions, you can set up your organization's custom list. You do this by editing your organization's default Safe Links policy.</span></span>
  
1. <span data-ttu-id="4a5ab-114">移至 [[https://protection.office.com](https://protection.office.com)和登入工作或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="4a5ab-114">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="4a5ab-115">在左導覽列中， **Threat management**] 下選擇 [**原則** \> **安全的連結**。</span><span class="sxs-lookup"><span data-stu-id="4a5ab-115">In the left navigation, under **Threat management**, choose **Policy** \> **Safe Links**.</span></span>
    
3. <span data-ttu-id="4a5ab-116">**套用至整個組織的原則**] 區段中選取 [**預設**]，然後選擇**編輯**（[編輯] 按鈕以鉛筆）。</span><span class="sxs-lookup"><span data-stu-id="4a5ab-116">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span> 
    
    ![按一下 [編輯] 以編輯您的預設原則的安全連結保護](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)
  
    <span data-ttu-id="4a5ab-p104">這是您前往檢視您的封鎖 Url 的清單。請注意在第一筆、 您將不會有任何列出的 Url。</span><span class="sxs-lookup"><span data-stu-id="4a5ab-p104">This is where you go to view your list of blocked URLs. Note that at first, you won't have any URLs listed.</span></span>
    
    ![封鎖的 Url 清單預設會套用至整個組織的安全連結原則。](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)
  
4. <span data-ttu-id="4a5ab-p105">選取 [**輸入有效的 URL** ] 方塊中，然後輸入 URL 並選擇 [加號 （+）。以下是一些事項謹記下列事項：</span><span class="sxs-lookup"><span data-stu-id="4a5ab-p105">Select the **Enter a valid URL** box, and then type a URL, and then choose the plus sign (+). Here are a few things to keep in mind:</span></span> 
    
  - <span data-ttu-id="4a5ab-p106">您可以指定僅限網域的 URL (例如`contoso.com`或`tailspintoys.com`)。這將會封鎖點閱上任何包含網域的 URL。</span><span class="sxs-lookup"><span data-stu-id="4a5ab-p106">You can specify a domain-only URL (like `contoso.com` or `tailspintoys.com`). This will block clicks on any URL that contains the domain.</span></span>
    
  - <span data-ttu-id="4a5ab-p107">不包含正斜線 ( **/**) 結尾的 URL。例如，而不是輸入`http://www.contoso.com/`、 輸入`http://www.contoso.com`。</span><span class="sxs-lookup"><span data-stu-id="4a5ab-p107">Do not include a forward slash ( **/**) at the end of the URL. For example, instead of entering `http://www.contoso.com/`, enter `http://www.contoso.com`.</span></span>
    
  - <span data-ttu-id="4a5ab-p108">您可以包含多達三個萬用字元星號 (\*) 每個 URL。下表列出有一些您可以輸入及什麼 effect 這些項目範例。</span><span class="sxs-lookup"><span data-stu-id="4a5ab-p108">You can include up to three wildcard asterisks (\*) per URL. The following table lists some examples of what you can enter and what effect those entries have.</span></span>
    
|<span data-ttu-id="4a5ab-129">**範例項目**</span><span class="sxs-lookup"><span data-stu-id="4a5ab-129">**Example Entry**</span></span>|<span data-ttu-id="4a5ab-130">**及其作用**</span><span class="sxs-lookup"><span data-stu-id="4a5ab-130">**What It Does**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4a5ab-131">`contoso.com`或`*contoso.com*`</span><span class="sxs-lookup"><span data-stu-id="4a5ab-131">`contoso.com` or `*contoso.com*`</span></span>  <br/> |<span data-ttu-id="4a5ab-132">封鎖的網域子網域，且路徑，例如`https://www.contoso.com`、 `http://sub.contoso.com`、 和`http://contoso.com/abc`</span><span class="sxs-lookup"><span data-stu-id="4a5ab-132">Blocks the domain, subdomains, and paths, such as `https://www.contoso.com`, `http://sub.contoso.com`, and `http://contoso.com/abc`</span></span>  <br/> |
|`http://contoso.com/a`  <br/> |<span data-ttu-id="4a5ab-133">封鎖網站`http://contoso.com/a`但沒有其他子路徑 like`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="4a5ab-133">Blocks a site `http://contoso.com/a` but not additional subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
|`http://contoso.com/a*`  <br/> |<span data-ttu-id="4a5ab-134">封鎖網站`http://contoso.com/a`及其他子路徑 like`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="4a5ab-134">Blocks a site `http://contoso.com/a` and additional subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
   
5. <span data-ttu-id="4a5ab-135">在螢幕右下角新增 Url、 完成時，選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="4a5ab-135">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>
    
## <a name="what-if-i-want-to-define-exceptions-for-certain-users-in-my-organization"></a><span data-ttu-id="4a5ab-136">怎麼辦？ 在我的組織中定義的特定使用者的例外狀況</span><span class="sxs-lookup"><span data-stu-id="4a5ab-136">What if I want to define exceptions for certain users in my organization?</span></span>

<span data-ttu-id="4a5ab-p109">如果您想要能夠檢視 Url 可能會封鎖其他人的特定群組，您可以指定套用至特定收件者 ATP 安全連結原則。請參閱 ＜ [Set up 自訂 「 未修正"Url 清單使用 ATP 安全的連結](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="4a5ab-p109">If you want certain groups to be able to view URLs that might be blocked for others, you can specify an ATP Safe Links policy that applies to specific recipients. See [Set up a custom "do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4a5ab-139">相關主題</span><span class="sxs-lookup"><span data-stu-id="4a5ab-139">Related topics</span></span>

[<span data-ttu-id="4a5ab-140">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="4a5ab-140">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="4a5ab-141">Office 365 中的 ATP 安全連結</span><span class="sxs-lookup"><span data-stu-id="4a5ab-141">ATP Safe Links in Office 365</span></span>](atp-safe-links.md)
  
[<span data-ttu-id="4a5ab-142">設定 Office 365 中的 ATP 安全連結原則</span><span class="sxs-lookup"><span data-stu-id="4a5ab-142">Set up ATP Safe Links policies in Office 365</span></span>](set-up-atp-safe-links-policies.md)
  
[<span data-ttu-id="4a5ab-143">Office 365 中的 ATP 安全附件</span><span class="sxs-lookup"><span data-stu-id="4a5ab-143">ATP Safe Attachments in Office 365</span></span>](atp-safe-attachments.md)

[<span data-ttu-id="4a5ab-144">Office 365 安全性權限&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="4a5ab-144">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  

