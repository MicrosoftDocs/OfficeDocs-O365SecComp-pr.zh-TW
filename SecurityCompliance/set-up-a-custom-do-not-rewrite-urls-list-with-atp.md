---
title: 設定使用 Office 365 ATP 安全連結的自訂不要-not-修正 Url 清單
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
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
description: 當您設定好您 ATP 安全連結原則時，您可以包含不要 not 修正 ' 要讓組織中某些使用者瀏覽您在您的清單中包含的網站 Url 的清單。
ms.openlocfilehash: d3883d6aff29b9a061b62e4854e7aad52656769f
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2019
ms.locfileid: "28015045"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-office-365-atp-safe-links"></a><span data-ttu-id="337d6-103">設定使用 Office 365 ATP 安全連結的自訂不要-not-修正 Url 清單</span><span class="sxs-lookup"><span data-stu-id="337d6-103">Set up a custom do-not-rewrite URLs list using Office 365 ATP Safe Links</span></span>

<span data-ttu-id="337d6-p101">與[Office 365 進階威脅保護](office-365-atp.md)(ATP)，您的組織可以[自訂封鎖的 Url](set-up-a-custom-blocked-urls-list-wtih-atp.md)如此人員時在 web 上按一下 [位址 (Url) 中有電子郵件訊息或特定 Office 文件、 其禁止移至這些 Url。您的組織也可以在組織中有特定群組中 「 未修正"的自訂清單。"不 rewrite"清單可讓有些人以造訪否則封鎖透過[ATP Office 365 中的安全連結](atp-safe-links.md)的 Url。</span><span class="sxs-lookup"><span data-stu-id="337d6-p101">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a [custom blocked URLs](set-up-a-custom-blocked-urls-list-wtih-atp.md), such that when people click on web addresses (URLs) in email messages or certain Office documents, they are prevented from going to those URLs. Your organization can also have custom "do not rewrite" lists for specific groups in your organization. A "do not rewrite" list enables some people to visit URLs that are otherwise blocked by [ATP Safe Links in Office 365](atp-safe-links.md).</span></span> 
  
<span data-ttu-id="337d6-107">本文說明如何在指定的清單中所排除的 ATP 安全連結掃描，和幾個重點牢記的 Url。</span><span class="sxs-lookup"><span data-stu-id="337d6-107">This article describes how to specify a list of URLs that are excluded from ATP Safe Links scanning, and a few important points to keep in mind.</span></span>

## <a name="set-up-a-do-not-rewrite-list"></a><span data-ttu-id="337d6-108">設定 「 未修正 」 清單</span><span class="sxs-lookup"><span data-stu-id="337d6-108">Set up a "do not rewrite" list</span></span>

<span data-ttu-id="337d6-p102">ATP 安全連結保護使用多個清單，包括您的組織已封鎖的 Url 清單和 「 未修正"例外狀況的清單。如果您擁有的必要權限，您可以設定自訂的 「 未修正 」 清單。當您新增或編輯套用至組織中特定收件者的安全連結原則，您可以這麼做。</span><span class="sxs-lookup"><span data-stu-id="337d6-p102">ATP Safe Links protection uses several lists, including your organization's blocked URLs list and the "do not rewrite" lists for exceptions. If you have the necessary permissions, you can set up your custom "do not rewrite" lists. You do this when you add or edit Safe Links policies that apply to specific recipients in your organization.</span></span> 
  
1. <span data-ttu-id="337d6-112">移至 [[https://protection.office.com](https://protection.office.com)和登入工作或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="337d6-112">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="337d6-113">在左導覽列中，[ **Threat management** \> **原則** \> **安全的連結**。</span><span class="sxs-lookup"><span data-stu-id="337d6-113">In the left navigation, under **Threat management** \> **Policy** \> **Safe Links**.</span></span>
    
3. <span data-ttu-id="337d6-p103">在 [**原則套用至特定收件者**] 區段中選擇 [**新增**] ([新增] 按鈕的格式類似於加號 ( **+**)) 來建立新的原則。（或者，您可以編輯現有的原則。）</span><span class="sxs-lookup"><span data-stu-id="337d6-p103">In the **Policies that apply to specific recipients** section, choose **New** (the New button resembles a plus sign ( **+**)) to create a new policy. (Alternatively, you can edit an existing policy.)</span></span><br/><span data-ttu-id="337d6-116">![選擇 [新增] 可為特定電子郵件收件者新增的安全連結原則](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span><span class="sxs-lookup"><span data-stu-id="337d6-116">![Choose New to add a Safe Links policy for specific email recipients](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span></span>
  
4. <span data-ttu-id="337d6-117">指定的名稱和描述您的原則。</span><span class="sxs-lookup"><span data-stu-id="337d6-117">Specify a name and description for your policy.</span></span>
    
5. <span data-ttu-id="337d6-118">**未修正下列 Url** ] 區段中選取 [**輸入有效的 URL** ] 方塊中，然後輸入 URL，然後選擇 [加號 （+）。</span><span class="sxs-lookup"><span data-stu-id="337d6-118">In the **Do not rewrite the following URLs** section, select the **Enter a valid URL** box, and then type a URL, and then choose the plus sign (+).</span></span> 
    
6. <span data-ttu-id="337d6-p104">**套用至**] 區段中選擇 [**收件者是成員**，然後按您想要包含在您的原則中的群組。選擇 [**新增**]，然後選擇 [ **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="337d6-p104">In the **Applied To** section, choose **The recipient is a member of**, and then choose the group(s) you want to include in your policy. Choose **Add**, and then choose **OK**.</span></span>
    
7. <span data-ttu-id="337d6-121">在螢幕右下角新增 Url、 完成時，選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="337d6-121">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="337d6-p105">請務必檢閱您的組織自訂清單之已封鎖的 Url。請參閱 ＜ [Set up 自訂封鎖 Url 清單使用 ATP 安全的連結](set-up-a-custom-blocked-urls-list-wtih-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="337d6-p105">Make sure to review your organization's custom list of blocked URLs. See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).</span></span> 
  
## <a name="important-points-to-keep-in-mind"></a><span data-ttu-id="337d6-124">請記住的重要事項</span><span class="sxs-lookup"><span data-stu-id="337d6-124">Important points to keep in mind</span></span>

- <span data-ttu-id="337d6-125">您指定的收件者所掃描的 ATP 安全連結不包含任何您在 「 未修正"] 清單中指定的 Url。</span><span class="sxs-lookup"><span data-stu-id="337d6-125">Any URLs that you specify in the "do not rewrite" list are excluded from ATP Safe Links scanning for the recipients that you specify.</span></span>
 
- <span data-ttu-id="337d6-p106">當您指定"未修正"ATP 安全連結原則的清單時，您可以包含多達三個萬用字元星號 (\*)。萬用字元 (\*) 會假設其值的項目如`contoso.com`，這不明確包含前置字元或子網域，如`http://`或`https://`。這表示項目，例如`contoso.com`類似於`*contoso.com*`您 「 未修正"的清單。</span><span class="sxs-lookup"><span data-stu-id="337d6-p106">When you specify a "do not rewrite" list for an ATP Safe Links policy, you can include up to three wildcard asterisks (\*). Wildcards (\*) are assumed for entries such as `contoso.com`, which do not explicitly include prefixes or subdomains, like `http://` or `https://`. This means an entry, such as `contoso.com` is similar to `*contoso.com*` for your "do not rewrite" list.</span></span>

- <span data-ttu-id="337d6-p107">如果您已"未修正 」 清單中的 Url 清單，請務必檢閱該清單並視情況新增萬用字元。例如，如果您現有的清單項目，像是`http://contoso.com/a`與您想要包含子路徑 like`http://contoso.com/a/b`在您的原則中加入萬用字元項目讓它看起來像是`http://contoso.com/a*`。</span><span class="sxs-lookup"><span data-stu-id="337d6-p107">If you already have a list of URLs in your "do not rewrite" list, make sure to review that list and add wildcards as appropriate. For example, if your existing list has an entry like `http://contoso.com/a` and you want to include subpaths like `http://contoso.com/a/b` in your policy, add a wildcard to your entry so it looks like `http://contoso.com/a*`.</span></span>
    
- <span data-ttu-id="337d6-p108">不要"未修正 」 清單中指定的 Url 中包含正斜線 （/）。例如，而不是輸入`contoso.com/`您 「 未修正 」 清單中，輸入`contoso.com`。</span><span class="sxs-lookup"><span data-stu-id="337d6-p108">Do not include a forward slash (/) in the URLs that you specify in your "do not rewrite" list. For example, rather than enter `contoso.com/` in your "do not rewrite" list, enter `contoso.com`.</span></span>
    
<span data-ttu-id="337d6-133">具有下表列出您可以輸入和範例什麼 effect 這些項目。</span><span class="sxs-lookup"><span data-stu-id="337d6-133">The following table lists examples of what you can enter and what effect those entries have.</span></span>
    
|<span data-ttu-id="337d6-134">**範例項目**</span><span class="sxs-lookup"><span data-stu-id="337d6-134">**Example Entry**</span></span>|<span data-ttu-id="337d6-135">**及其作用**</span><span class="sxs-lookup"><span data-stu-id="337d6-135">**What It Does**</span></span>|
|:-----|:-----|
|`*contoso.com*`  <br/> |<span data-ttu-id="337d6-136">允許特定收件者瀏覽網域、 子網域，以及路徑，例如`http://www.contoso.com`、 `https://www.contoso.com`、 `https://maps.contoso.com`，或`http://www.contoso.com/a`</span><span class="sxs-lookup"><span data-stu-id="337d6-136">Allows specific recipients to visit a domain, subdomains, and paths, such as `http://www.contoso.com`, `https://www.contoso.com`, `https://maps.contoso.com`, or `http://www.contoso.com/a`</span></span>  <br/> |
|`http://contoso.com/a`  <br/> |<span data-ttu-id="337d6-137">允許特定收件者類似的網站瀏覽`http://contoso.com/a`，但不是個子路徑 like`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="337d6-137">Allows specific recipients to visit a site like `http://contoso.com/a`, but not subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
|`http://contoso.com/a*`  <br/> |<span data-ttu-id="337d6-138">允許特定收件者類似的網站瀏覽`http://contoso.com/a`及 like 個子路徑`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="337d6-138">Allows specific recipients to visit a site like `http://contoso.com/a` and subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
   
 