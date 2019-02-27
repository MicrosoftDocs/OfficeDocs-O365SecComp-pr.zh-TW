---
title: 設定 Office 365 ATP 安全連結原則
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.date: 02/26/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: 設定安全的連結原則來保護您的組織不在 Word、 Excel、 PowerPoint 及 Visio 檔案，以及在電子郵件訊息中的惡意連結。
ms.openlocfilehash: e9ab086454703113bca6e8b260ba898a5e36ef9b
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296826"
---
# <a name="set-up-office-365-atp-safe-links-policies"></a><span data-ttu-id="2478f-103">設定 Office 365 ATP 安全連結原則</span><span class="sxs-lookup"><span data-stu-id="2478f-103">Set up Office 365 ATP Safe Links policies</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2478f-p101">本文適用於 Office 365 企業版客戶的。如果您使用 Outlook.com、 Office 365 首頁] 或 [Office 365 個人，而且您要尋找在 Outlook 中的安全連結的相關資訊，請參閱[進階 Outlook.com 安全性](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="2478f-p101">This article is intended for Office 365 Enterprise customers. If you are using Outlook.com, Office 365 Home, or Office 365 Personal, and you're looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="2478f-p102">[ATP 安全連結](atp-safe-links.md)的[Office 365 進階威脅保護](office-365-atp.md)(ATP) 的功能可協助保護您的組織中用於網路釣魚和其他攻擊的惡意連結。如果您有必要[的 Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)、 您可以設定 ATP 安全連結原則以協助確保當使用者按一下 [網站位址 (Url)、 貴組織保護。ATP 安全連結原則可以設定要掃描電子郵件中的 Url 及 Office 文件中的 Url。</span><span class="sxs-lookup"><span data-stu-id="2478f-p102">[ATP Safe Links](atp-safe-links.md), a feature of [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), can help protect your organization from malicious links used in phishing and other attacks. If you have the necessary [permissions for the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md), you can set up ATP Safe Links policies to help ensure that when people click web addresses (URLs), your organization is protected. Your ATP Safe Links policies can be configured to scan URLs in email and URLs in Office documents.</span></span>
  
<span data-ttu-id="2478f-p103">[ATP 持續所加入的新功能](office-365-atp.md#new-features-in-office-365-atp)。隨著增加新功能，您可能需要調整您現有的 ATP 安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="2478f-p103">[New features are continually being added to ATP](office-365-atp.md#new-features-in-office-365-atp). As new features are added, you may need to make adjustments to your existing ATP Safe Links policies.</span></span>

## <a name="what-to-do"></a><span data-ttu-id="2478f-111">該怎麼辦</span><span class="sxs-lookup"><span data-stu-id="2478f-111">What to do</span></span> 
  
1. <span data-ttu-id="2478f-112">[請先檢閱必要條件](#review-the-prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="2478f-112">[Review the prerequisites](#review-the-prerequisites).</span></span>
    
2. <span data-ttu-id="2478f-p104">[檢閱並編輯預設 ATP 安全連結原則可套用到所有人](#define-an-atp-safe-links-policy-that-applies-to-everyone)。例如，您可以[設定 ATP 安全連結您自訂封鎖 Url 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="2478f-p104">[Review and edit the default ATP Safe Links policy that applies to everyone](#define-an-atp-safe-links-policy-that-applies-to-everyone). For example, you can [set up your custom blocked URLs list for ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).</span></span>
    
3. <span data-ttu-id="2478f-115">[新增或編輯原則的特定電子郵件收件者](#add-a-policy-for-specific-email-recipients)，包括[您自訂 「 未修正"Url 清單 ATP 安全連結的設定](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="2478f-115">[Add or edit policies for specific email recipients](#add-a-policy-for-specific-email-recipients), including [setting up your custom "Do not rewrite" URLs list for ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
    
4. <span data-ttu-id="2478f-116">[了解 ATP 安全連結原則選項](#learn-about-atp-safe-links-policy-options)（在本文中），包括設定為最近的變更。</span><span class="sxs-lookup"><span data-stu-id="2478f-116">[Learn about ATP Safe Links policy options](#learn-about-atp-safe-links-policy-options) (in this article), including settings for recent changes.</span></span>
    
## <a name="step-1-review-the-prerequisites"></a><span data-ttu-id="2478f-117">步驟 1： 檢閱必要條件</span><span class="sxs-lookup"><span data-stu-id="2478f-117">Step 1: Review the prerequisites</span></span>

- <span data-ttu-id="2478f-118">請確定您的組織具有[Office 365 進階威脅保護](office-365-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="2478f-118">Make sure that your organization has [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span>
    
- <span data-ttu-id="2478f-p105">請確定您具有必要的權限。若要定義 （或編輯） ATP 原則，您必須指派適當的角色。下表說明一些範例：</span><span class="sxs-lookup"><span data-stu-id="2478f-p105">Make sure that you have the necessary permissions. To define (or edit) ATP policies, you must be assigned an appropriate role. Some examples are described in the following table:</span></span> <br>

    |<span data-ttu-id="2478f-122">角色</span><span class="sxs-lookup"><span data-stu-id="2478f-122">Role</span></span>  |<span data-ttu-id="2478f-123">Where/如何指派</span><span class="sxs-lookup"><span data-stu-id="2478f-123">Where/how assigned</span></span>  |
    |---------|---------|
    |<span data-ttu-id="2478f-124">Office 365 全域管理員</span><span class="sxs-lookup"><span data-stu-id="2478f-124">Office 365 Global Administrator</span></span> |<span data-ttu-id="2478f-p106">若要購買 Office 365 設定簽署者為預設的全域系統管理員。（請參閱若要深入了[解 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)）。</span><span class="sxs-lookup"><span data-stu-id="2478f-p106">The person who signs up to buy Office 365 is a global admin by default. (See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
    |<span data-ttu-id="2478f-127">安全性管理員</span><span class="sxs-lookup"><span data-stu-id="2478f-127">Security Administrator</span></span> |<span data-ttu-id="2478f-128">Azure Active Directory 系統管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="2478f-128">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
    |<span data-ttu-id="2478f-129">Exchange Online 組織管理</span><span class="sxs-lookup"><span data-stu-id="2478f-129">Exchange Online Organization Management</span></span> |<span data-ttu-id="2478f-130">Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="2478f-130">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="2478f-131">或</span><span class="sxs-lookup"><span data-stu-id="2478f-131">or</span></span> <br>  <span data-ttu-id="2478f-132">PowerShell cmdlet (請參閱[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span><span class="sxs-lookup"><span data-stu-id="2478f-132">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span></span> |

    <span data-ttu-id="2478f-133">若要深入了解角色和權限，請參閱[Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="2478f-133">To learn more about roles and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="2478f-134">請確定 Office 用戶端設定為使用[經過驗證](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)（這是 Office 文件中的 ATP 安全連結保護）。</span><span class="sxs-lookup"><span data-stu-id="2478f-134">Make sure that Office clients are configured to use [Modern Authentication](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016) (this is for ATP Safe Links protection in Office documents).</span></span>
    
- <span data-ttu-id="2478f-135">[了解 ATP 安全連結原則選項](#learn-about-atp-safe-links-policy-options)（在本文）。</span><span class="sxs-lookup"><span data-stu-id="2478f-135">[Learn about ATP Safe Links policy options](#learn-about-atp-safe-links-policy-options) (in this article).</span></span> 

- <span data-ttu-id="2478f-136">可讓您新增或更新原則散佈到所有 Office 365 資料中心的最多 30 分鐘。</span><span class="sxs-lookup"><span data-stu-id="2478f-136">Allow up to 30 minutes for your new or updated policy to spread to all Office 365 datacenters.</span></span>
    
## <a name="step-2-define-or-review-the-atp-safe-links-policy-that-applies-to-everyone"></a><span data-ttu-id="2478f-137">步驟 2： 定義 （或檢閱） 套用至所有人 ATP 安全連結原則</span><span class="sxs-lookup"><span data-stu-id="2478f-137">Step 2: Define (or review) the ATP Safe Links policy that applies to everyone</span></span>

<span data-ttu-id="2478f-p107">當您有[Office 365 進階威脅保護](office-365-atp.md)時，您必須套用至組織中所有人預設 ATP 安全連結原則。請務必檢閱，並視需要編輯預設原則。</span><span class="sxs-lookup"><span data-stu-id="2478f-p107">When you have [Office 365 Advanced Threat Protection](office-365-atp.md), you will have a default ATP Safe Links policy that applies to everyone in your organization. Make sure to review, and if needed, edit your default policy.</span></span>
  
1. <span data-ttu-id="2478f-140">移至 [[https://protection.office.com](https://protection.office.com)和登入工作或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="2478f-140">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="2478f-141">在左導覽列中， **Threat management**] 下選擇**原則\>\*\*\*\*安全的連結**。</span><span class="sxs-lookup"><span data-stu-id="2478f-141">In the left navigation, under **Threat management**, choose **Policy \>** **Safe Links**.</span></span>
    
3. <span data-ttu-id="2478f-142">**套用至整個組織的原則**] 區段中選取 [**預設**]，然後選擇**編輯**（[編輯] 按鈕以鉛筆）。</span><span class="sxs-lookup"><span data-stu-id="2478f-142">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span><br/><span data-ttu-id="2478f-143">![按一下 [編輯] 以編輯您的預設原則的安全連結保護](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span><span class="sxs-lookup"><span data-stu-id="2478f-143">![Click Edit to edit your default policy for Safe Links protection](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span></span>
  
4. <span data-ttu-id="2478f-p108">在 [**封鎖下列 Url** ] 區段中，指定您想要避免造訪您組織中的一或多個 Url。（請參閱[Set up 自訂封鎖 Url 清單使用 ATP 安全連結](set-up-a-custom-blocked-urls-list-wtih-atp.md)）。</span><span class="sxs-lookup"><span data-stu-id="2478f-p108">In the **Block the following URLs** section, specify one or more URLs that you want to prevent people in your organization from visiting. (See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).)</span></span>
    
5. <span data-ttu-id="2478f-p109">**套用至內容除了電子郵件設定**] 區段中選取 （或清除） [您想要使用的選項。（我們建議您選取的所有選項）。</span><span class="sxs-lookup"><span data-stu-id="2478f-p109">In the **Settings that apply to content except email** section, select (or clear) the options you want to use. (We recommend that you select all the options.)</span></span> 
    
6. <span data-ttu-id="2478f-148">選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="2478f-148">Choose **Save**.</span></span>
    
## <a name="step-3-add-or-edit-atp-safe-links-policies-that-apply-to-specific-email-recipients"></a><span data-ttu-id="2478f-149">步驟 3： 新增 （或編輯） ATP 安全連結原則套用至特定電子郵件收件者</span><span class="sxs-lookup"><span data-stu-id="2478f-149">Step 3: Add (or edit) ATP Safe Links policies that apply to specific email recipients</span></span>

<span data-ttu-id="2478f-p110">您已檢閱 （或編輯） 套用至所有人預設 ATP 安全連結原則之後下, 一步是定義會套用至特定收件者的其他原則。例如，您可以指定例外狀況為預設原則所定義的其他原則。</span><span class="sxs-lookup"><span data-stu-id="2478f-p110">After you have reviewed (or edited) the default ATP Safe Links policy that applies to everyone, your next step is to define additional policies that would apply to specific recipients. For example, you can specify exceptions to your default policy by defining an additional policy.</span></span> 
  
1. <span data-ttu-id="2478f-152">移至 [[https://protection.office.com](https://protection.office.com)和登入工作或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="2478f-152">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="2478f-153">在左導覽列中， **Threat management**] 下選擇 [**原則**]。</span><span class="sxs-lookup"><span data-stu-id="2478f-153">In the left navigation, under **Threat management**, choose **Policy**.</span></span>
    
3. <span data-ttu-id="2478f-154">選擇 [**安全的連結**。</span><span class="sxs-lookup"><span data-stu-id="2478f-154">Choose **Safe Links**.</span></span>
    
4. <span data-ttu-id="2478f-155">在 [**原則套用至特定收件者**] 區段中選擇 [**新增**] ([新增] 按鈕的格式類似於加號 ( **+**))。</span><span class="sxs-lookup"><span data-stu-id="2478f-155">In the **Policies that apply to specific recipients** section, choose **New** (the New button resembles a plus sign ( **+**)).</span></span><br/><span data-ttu-id="2478f-156">![選擇 [新增] 可為特定電子郵件收件者新增的安全連結原則](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span><span class="sxs-lookup"><span data-stu-id="2478f-156">![Choose New to add a Safe Links policy for specific email recipients](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span></span>
  
5. <span data-ttu-id="2478f-157">指定原則的名稱、描述及設定。</span><span class="sxs-lookup"><span data-stu-id="2478f-157">Specify the name, description, and settings for your policy.</span></span><br/><span data-ttu-id="2478f-158">**範例：** 若要設定稱為 「 沒有直接點選"不允許人員的特定群組中按一下透過特定的網站不 ATP 安全連結保護組織的原則，您可能會指定下列建議設定：</span><span class="sxs-lookup"><span data-stu-id="2478f-158">**Example:** To set up a policy called "no direct click through" that does not allow people in a certain group in your organization to click through to a specific website without ATP Safe Links protection, you might specify the following recommended settings:</span></span> 
    
  - <span data-ttu-id="2478f-159">在 [**名稱**] 方塊中輸入沒有直接點選。</span><span class="sxs-lookup"><span data-stu-id="2478f-159">In the **Name** box, type no direct click through.</span></span>
    
  - <span data-ttu-id="2478f-160">在 [**描述**] 方塊中輸入像轉人員從透過按一下沒有 ATP 安全連結驗證的網站特定群組中的描述。</span><span class="sxs-lookup"><span data-stu-id="2478f-160">In the **Description** box, type a description like, Prevents people in certain groups from clicking through to a website without ATP Safe Links verification.</span></span>
    
  - <span data-ttu-id="2478f-161">**選取動作**] 區段中選擇 [**上**]。</span><span class="sxs-lookup"><span data-stu-id="2478f-161">In the **Select the action** section, choose **On**.</span></span>
    
  - <span data-ttu-id="2478f-162">選取 [**使用安全附件掃描可下載的內容**。</span><span class="sxs-lookup"><span data-stu-id="2478f-162">Select **Use Safe Attachments to scan downloadable content**.</span></span>
    
  - <span data-ttu-id="2478f-163">使用此選項時，選取 [**套用至組織內傳送訊息的安全連結**。</span><span class="sxs-lookup"><span data-stu-id="2478f-163">If this option is available, select **Apply Safe Links to messages sent within the organization**.</span></span>
    
  - <span data-ttu-id="2478f-164">選取 [**不允許使用者透過按一下以原始 URL**。</span><span class="sxs-lookup"><span data-stu-id="2478f-164">Select **Do not allow user to click through to original URL**.</span></span>
    
  - <span data-ttu-id="2478f-p111">（這是選用的）**未修正下列 Url** ] 區段中指定被視為安全組織的一或多個 Url。（請參閱[Set up 自訂 「 未修正"Url 清單使用 ATP 安全連結](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)）</span><span class="sxs-lookup"><span data-stu-id="2478f-p111">(This is optional) In the **Do not rewrite the following URLs** section, specify one or more URLs that are considered to be safe for your organization. (See [Set up a custom "Do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md))</span></span>
    
  - <span data-ttu-id="2478f-p112">**套用至**] 區段中選擇 [**收件者是成員**，然後按您想要包含在您的原則中的群組。選擇 [**新增**]，然後選擇 [ **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="2478f-p112">In the **Applied To** section, choose **The recipient is a member of**, and then choose the group(s) you want to include in your policy. Choose **Add**, and then choose **OK**.</span></span>
    
6. <span data-ttu-id="2478f-169">選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="2478f-169">Choose **Save**.</span></span>
    
## <a name="step-4-learn-about-atp-safe-links-policy-options"></a><span data-ttu-id="2478f-170">步驟 4︰ 了解 ATP 安全連結原則選項</span><span class="sxs-lookup"><span data-stu-id="2478f-170">Step 4: Learn about ATP Safe Links policy options</span></span>

<span data-ttu-id="2478f-p113">當您設定或編輯 ATP 安全連結原則時，會看到數個可用選項。您會知道這些選項為何下, 表說明每一個和其效果。有兩種主要定義或編輯 ATP 安全連結原則，請記得：</span><span class="sxs-lookup"><span data-stu-id="2478f-p113">As you set up or edit your ATP Safe Links policies, will see several options available. In case you are wondering what these options are, the following table describes each one and its effect. Remember that there are two main kinds of ATP Safe Links policies to define or edit:</span></span>
- <span data-ttu-id="2478f-174">套用至所有人;[預設原則](#default-policy-options)與</span><span class="sxs-lookup"><span data-stu-id="2478f-174">a [default policy](#default-policy-options) that applies to everyone; and</span></span>  
- <span data-ttu-id="2478f-175">其他[特定收件者的原則](#policies-that-apply-to-specific-email-recipients)</span><span class="sxs-lookup"><span data-stu-id="2478f-175">additional [policies for specific recipients](#policies-that-apply-to-specific-email-recipients)</span></span> 

### <a name="default-policy-options"></a><span data-ttu-id="2478f-176">預設原則選項</span><span class="sxs-lookup"><span data-stu-id="2478f-176">Default policy options</span></span>

<span data-ttu-id="2478f-177">預設原則選項套用至組織中所有的人。</span><span class="sxs-lookup"><span data-stu-id="2478f-177">Default policy options apply to everyone in your organization.</span></span>

|<span data-ttu-id="2478f-178">此選項</span><span class="sxs-lookup"><span data-stu-id="2478f-178">This option</span></span>  |<span data-ttu-id="2478f-179">執行動作</span><span class="sxs-lookup"><span data-stu-id="2478f-179">Does this</span></span>  |
|---------|---------|
| <span data-ttu-id="2478f-180">**封鎖下列 Url**</span><span class="sxs-lookup"><span data-stu-id="2478f-180">**Block the following URLs**</span></span> <br/>    | <span data-ttu-id="2478f-p114">可讓您的組織具有自訂清單的自動封鎖的 Url。當使用者按一下此清單中的 URL 時，他們會前往說明 URL 封鎖的原因[警告] 頁面](atp-safe-links-warning-pages.md)。如需了解，請參閱[Set up 使用 Office 365 ATP 安全連結的自訂封鎖 Url 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="2478f-p114">Enables your organization to have a custom list of URLs that are automatically blocked. When users click a URL in this list, they'll be taken to a [warning page](atp-safe-links-warning-pages.md) that explains why the URL is blocked. To learn more, see [Set up a custom blocked URLs list using Office 365 ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).</span></span> |
| <span data-ttu-id="2478f-184">**Office 365 ProPlus iOS 適用於 Office 及 android （英文）**</span><span class="sxs-lookup"><span data-stu-id="2478f-184">**Office 365 ProPlus, Office for iOS and Android**</span></span> <br/>    | <span data-ttu-id="2478f-185">ATP 安全連結保護選取此選項時，會套用至 Windows 或 Mac OS、 iOS 或 Android 裝置上的 Office 文件上 Windows 及 Office Online （線上 Word、 PowerPoint Online、 Excel Online Visio 2016 上的 Word、 Excel 及 PowerPoint 檔案中的 Url與 OneNote Online），提供使用者已登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="2478f-185">When this option is selected, ATP Safe Links protection is applied to URLs in Word, Excel, and PowerPoint files on Windows or Mac OS, Office documents on iOS, or Android devices, Visio 2016 on Windows, and Office Online (Word Online, PowerPoint Online, Excel Online, and OneNote Online), provided the user has signed into Office 365.</span></span> |
| <span data-ttu-id="2478f-186">**當使用者按一下 ATP 安全連結時不要追蹤**</span><span class="sxs-lookup"><span data-stu-id="2478f-186">**Don't track when users click ATP Safe Links**</span></span> <br/>  | <span data-ttu-id="2478f-187">選取此選項時，按一下資料中的不會儲存在 Word、 Excel、 PowerPoint 及 Visio 文件中的 Url。</span><span class="sxs-lookup"><span data-stu-id="2478f-187">When this option is selected, click data for URLs in Word, Excel, PowerPoint, and Visio documents is not stored.</span></span>  <br/> |
|<span data-ttu-id="2478f-188">**不讓使用者按一下 [透過 ATP 原始 URL 的安全連結**</span><span class="sxs-lookup"><span data-stu-id="2478f-188">**Don't let users click through ATP Safe Links to original URL**</span></span> <br/> |<span data-ttu-id="2478f-189">選取此選項時，使用者無法繼續過去的[警告] 頁面上](atp-safe-links-warning-pages.md)決定為惡意的 URL。</span><span class="sxs-lookup"><span data-stu-id="2478f-189">When this option is selected, users cannot proceed past a [warning page](atp-safe-links-warning-pages.md) to a URL that is determined to be malicious.</span></span>  <br/> |

### <a name="policies-that-apply-to-specific-email-recipients"></a><span data-ttu-id="2478f-190">套用至特定電子郵件收件者的原則</span><span class="sxs-lookup"><span data-stu-id="2478f-190">Policies that apply to specific email recipients</span></span>

|<span data-ttu-id="2478f-191">此選項</span><span class="sxs-lookup"><span data-stu-id="2478f-191">This option</span></span>  |<span data-ttu-id="2478f-192">執行動作</span><span class="sxs-lookup"><span data-stu-id="2478f-192">Does this</span></span>  |
|---------|---------|
|<span data-ttu-id="2478f-193">**Off**</span><span class="sxs-lookup"><span data-stu-id="2478f-193">**Off**</span></span> <br/> |<span data-ttu-id="2478f-194">不會掃描電子郵件訊息中的 Url。</span><span class="sxs-lookup"><span data-stu-id="2478f-194">Does not scan URLs in email messages.</span></span>  <br/> <span data-ttu-id="2478f-195">可讓您定義的例外狀況規則，例如不會掃描一組特定的收件者的電子郵件訊息中 Url 的規則。</span><span class="sxs-lookup"><span data-stu-id="2478f-195">Enables you to define an exception rule, such as a rule that does not scan URLs in email messages for a specific group of recipients.</span></span>  <br/> |
|<span data-ttu-id="2478f-196">**開啟**</span><span class="sxs-lookup"><span data-stu-id="2478f-196">**On**</span></span> <br/> |<span data-ttu-id="2478f-197">當使用者按一下 [Url] 中的電子郵件，路由使用者可透過 ATP 安全連結保護修正 Url。</span><span class="sxs-lookup"><span data-stu-id="2478f-197">Rewrites URLs to route users through ATP Safe Links protection when the users click URLs in email messages.</span></span>  <br/> <span data-ttu-id="2478f-198">檢查當您按一下針對封鎖或惡意 Url 清單的 URL。</span><span class="sxs-lookup"><span data-stu-id="2478f-198">Checks a URL when clicked against a list of blocked or malicious URLs.</span></span>  <br/> |
|<span data-ttu-id="2478f-199">**使用安全附件掃描的可下載內容**</span><span class="sxs-lookup"><span data-stu-id="2478f-199">**Use Safe Attachments to scan downloadable content**</span></span> <br/> |<span data-ttu-id="2478f-200">選取此選項時，會掃描指向可下載內容的 Url。</span><span class="sxs-lookup"><span data-stu-id="2478f-200">When this option is selected, URLs that point to downloadable content are scanned.</span></span>  <br/> |
|<span data-ttu-id="2478f-201">**套用至組織內傳送訊息的安全連結**</span><span class="sxs-lookup"><span data-stu-id="2478f-201">**Apply Safe Links to messages sent within the organization**</span></span> <br/> | <span data-ttu-id="2478f-202">當可用及選取此選項即 ATP 安全連結保護會套用至組織中所提供的電子郵件帳戶的人員之間所寄送的郵件都架設在 Office 365 的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="2478f-202">When this option is available and selected, ATP Safe Links protection is applied to email messages sent between people in your organization, provided the email accounts are hosted in Office 365.</span></span>  <br/> |
|<span data-ttu-id="2478f-203">**不會追蹤使用者點選**</span><span class="sxs-lookup"><span data-stu-id="2478f-203">**Do not track user clicks**</span></span> <br/> |<span data-ttu-id="2478f-p115">選取此選項時，按一下資料中的 Url 來自外部寄件者的電子郵件中不會儲存。目前不支援 URL click 追蹤組織內傳送的電子郵件訊息內的連結。</span><span class="sxs-lookup"><span data-stu-id="2478f-p115">When this option is selected, click data for URLs in email from external senders is not stored. URL click tracking for links within email messages sent within the organization is currently not supported.</span></span>  <br/> |
|<span data-ttu-id="2478f-206">**不允許使用者透過按一下以原始 URL**</span><span class="sxs-lookup"><span data-stu-id="2478f-206">**Do not allow users to click through to original URL**</span></span> <br/> |<span data-ttu-id="2478f-207">選取此選項時，使用者無法繼續過去的[警告] 頁面上](atp-safe-links-warning-pages.md)決定為惡意的 URL。</span><span class="sxs-lookup"><span data-stu-id="2478f-207">When this option is selected, users cannot proceed past a [warning page](atp-safe-links-warning-pages.md) to a URL that is determined to be malicious.</span></span>  <br/> |
|<span data-ttu-id="2478f-208">**未修正下列 Url**</span><span class="sxs-lookup"><span data-stu-id="2478f-208">**Do not rewrite the following URLs**</span></span> <br/> |<span data-ttu-id="2478f-p116">以離開 Url。保留自訂清單的安全不需要一組特定的組織中的電子郵件收件者的掃描的 Url。 請參閱 ＜ [Set up 自訂 「 未修正"Url 清單使用 ATP 安全連結](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)如需詳細資訊，包括支援的萬用字元星號最近的變更 (\*)。</span><span class="sxs-lookup"><span data-stu-id="2478f-p116">Leaves URLs as they are. Keeps a custom list of safe URLs that don't need scanning for a specific group of email recipients in your organization.  See [Set up a custom "Do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for more details, including recent changes to support for wildcard asterisks (\*).  </span></span><br/> |
   
## <a name="next-steps"></a><span data-ttu-id="2478f-212">後續步驟</span><span class="sxs-lookup"><span data-stu-id="2478f-212">Next steps</span></span>

<span data-ttu-id="2478f-p117">一旦您 ATP 安全連結原則已備妥，您可以看到 ATP 如何為貴組織運作檢視報告。請參閱下列資源以深入了解：</span><span class="sxs-lookup"><span data-stu-id="2478f-p117">Once your ATP Safe Links policies are in place, you can see how ATP is working for your orgnization by viewing reports. See the following resources to learn more:</span></span>

- [<span data-ttu-id="2478f-215">Office 365 進階威脅保護的檢視報告</span><span class="sxs-lookup"><span data-stu-id="2478f-215">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

- [<span data-ttu-id="2478f-216">使用瀏覽器安全性&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="2478f-216">Use Explorer in the Security &amp; Compliance Center</span></span>](use-explorer-in-security-and-compliance.md)

<span data-ttu-id="2478f-p118">隨時掌握置於 ATP 傳入的新功能。請造訪[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)並了解[新功能，要新增至 ATP](office-365-atp.md#new-features-in-office-365-atp)。</span><span class="sxs-lookup"><span data-stu-id="2478f-p118">Stay on top of new features coming to ATP. visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) and learn about [new features that are being added to ATP](office-365-atp.md#new-features-in-office-365-atp).</span></span>