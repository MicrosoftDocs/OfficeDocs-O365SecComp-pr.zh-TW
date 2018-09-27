---
title: 設定 Office 365 ATP 安全連結原則
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
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
description: 設定安全的連結原則來保護您的組織不在 Word、 Excel、 PowerPoint 及 Visio 檔案，以及在電子郵件訊息中的惡意連結。
ms.openlocfilehash: 94ad3a5d497a5fe97144e3aad29ba25d2073cde1
ms.sourcegitcommit: 9826013c3e0532ae5d01b3d88a14691f8dd0f6b7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/27/2018
ms.locfileid: "25092949"
---
# <a name="set-up-office-365-atp-safe-links-policies"></a><span data-ttu-id="7291c-103">設定 Office 365 ATP 安全連結原則</span><span class="sxs-lookup"><span data-stu-id="7291c-103">Set up Office 365 ATP Safe Links policies</span></span>

<span data-ttu-id="7291c-p101">[ATP 安全連結](atp-safe-links.md)的[Office 365 進階威脅保護](office-365-atp.md)(ATP) 的功能可協助保護您的組織中用於網路釣魚和其他攻擊的惡意連結。如果您有必要[權限指派在 Office 365 安全性&amp;規範中心](permissions-in-the-security-and-compliance-center.md)、 您可以設定 ATP 安全連結原則以協助確保當使用者按一下 [網站位址 (Url)、 貴組織保護。ATP 安全連結原則可以設定要掃描電子郵件中的 Url 及 Office 文件中的 Url。</span><span class="sxs-lookup"><span data-stu-id="7291c-p101">[ATP Safe Links](atp-safe-links.md) , a feature of [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), can help protect your organization from malicious links used in phishing and other attacks. If you have the necessary [permissions assigned in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md), you can set up ATP Safe Links policies to help ensure that when people click web addresses (URLs), your organization is protected. Your ATP Safe Links policies can be configured to scan URLs in email and URLs in Office documents.</span></span>
  
<span data-ttu-id="7291c-p102">[新功能所需要經常新增至 ATP 安全的連結](atp-safe-links.md#new-features-added-to-atp-safe-links)。隨著增加新功能，您可能需要調整您現有的 ATP 安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="7291c-p102">[New features are continually being added to ATP Safe Links](atp-safe-links.md#new-features-added-to-atp-safe-links). As new features are added, you may need to make adjustments to your existing ATP Safe Links policies.</span></span>

## <a name="what-to-do"></a><span data-ttu-id="7291c-109">該怎麼辦</span><span class="sxs-lookup"><span data-stu-id="7291c-109">What to do</span></span> 
  
1. <span data-ttu-id="7291c-110">[請先檢閱必要條件](#review-the-prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="7291c-110">[Review the prerequisites](#review-the-prerequisites).</span></span>
    
2. <span data-ttu-id="7291c-p103">[檢閱並編輯預設 ATP 安全連結原則可套用到所有人](#define-an-atp-safe-links-policy-that-applies-to-everyone)。例如，您可以[設定 ATP 安全連結您自訂封鎖 Url 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="7291c-p103">[Review and edit the default ATP Safe Links policy that applies to everyone](#define-an-atp-safe-links-policy-that-applies-to-everyone). For example, you can [set up your custom blocked URLs list for ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).</span></span>
    
3. <span data-ttu-id="7291c-113">[新增或編輯原則的特定電子郵件收件者](#add-a-policy-for-specific-email-recipients)，包括[您自訂 「 未修正"Url 清單 ATP 安全連結的設定](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="7291c-113">[Add or edit policies for specific email recipients](#add-a-policy-for-specific-email-recipients), including [setting up your custom "Do not rewrite" URLs list for ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
    
4. <span data-ttu-id="7291c-114">[了解 ATP 安全連結原則選項](#learn-about-atp-safe-links-policy-options)（在本文中），包括 [最近變更的設定</span><span class="sxs-lookup"><span data-stu-id="7291c-114">[Learn about ATP Safe Links policy options](#learn-about-atp-safe-links-policy-options) (in this article), including settings for recent changes</span></span>
    
## <a name="step-1-review-the-prerequisites"></a><span data-ttu-id="7291c-115">步驟 1： 檢閱必要條件</span><span class="sxs-lookup"><span data-stu-id="7291c-115">Step 1: Review the prerequisites</span></span>

- <span data-ttu-id="7291c-116">請確定您的組織具有[Office 365 進階威脅保護](office-365-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="7291c-116">Make sure that your organization has [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span>
    
- <span data-ttu-id="7291c-p104">請確定您已定義或編輯 ATP 原則的必要權限。請參閱[中的 Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="7291c-p104">Make sure that you have the necessary permissions to define or edit ATP policies. See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    
- <span data-ttu-id="7291c-119">[了解 ATP 安全連結原則選項](#learn-about-atp-safe-links-policy-options)（在本文）。</span><span class="sxs-lookup"><span data-stu-id="7291c-119">[Learn about ATP Safe Links policy options](#learn-about-atp-safe-links-policy-options) (in this article).</span></span> 

- <span data-ttu-id="7291c-120">請確定 Office 用戶端設定為使用[經過驗證](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)。</span><span class="sxs-lookup"><span data-stu-id="7291c-120">Make sure that Office clients are configured to use [Modern Authentication](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).</span></span>
    
- <span data-ttu-id="7291c-121">可讓您新增或更新原則散佈到所有 Office 365 資料中心的最多 30 分鐘。</span><span class="sxs-lookup"><span data-stu-id="7291c-121">Allow up to 30 minutes for your new or updated policy to spread to all Office 365 datacenters.</span></span>
    
## <a name="step-2-define-or-review-the-atp-safe-links-policy-that-applies-to-everyone"></a><span data-ttu-id="7291c-122">步驟 2： 定義 （或檢閱） 套用至所有人 ATP 安全連結原則</span><span class="sxs-lookup"><span data-stu-id="7291c-122">Step 2: Define (or review) the ATP Safe Links policy that applies to everyone</span></span>

<span data-ttu-id="7291c-123">當您在 Office 365 企業版中有進階威脅保護時，您必須套用至組織中所有人預設 ATP 安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="7291c-123">When you have Advanced Threat Protection in Office 365 Enterprise, you will have a default ATP Safe Links policy that applies to everyone in your organization.</span></span> 

> [!TIP]
> <span data-ttu-id="7291c-p105">您可以編輯您的原則可以是安全性&amp;規範中心 」 或 「 Exchange 系統管理中心。**建議使用安全性&amp;檢閱或編輯的任何 ATP 原則規範中心**。</span><span class="sxs-lookup"><span data-stu-id="7291c-p105">You can edit your policy in either the Security &amp; Compliance Center or the Exchange admin center. **We recommend using the Security &amp; Compliance Center to review or edit any of your ATP policies**.</span></span>
  
1. <span data-ttu-id="7291c-126">移至 [[https://protection.office.com](https://protection.office.com)和登入工作或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="7291c-126">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="7291c-127">在左導覽列中， **Threat management**] 下選擇**原則\>\*\*\*\*安全的連結**。</span><span class="sxs-lookup"><span data-stu-id="7291c-127">In the left navigation, under **Threat management**, choose **Policy \>** **Safe Links**.</span></span>
    
3. <span data-ttu-id="7291c-128">**套用至整個組織的原則**] 區段中選取 [**預設**]，然後選擇**編輯**（[編輯] 按鈕以鉛筆）。</span><span class="sxs-lookup"><span data-stu-id="7291c-128">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span> 
    
    ![按一下 [編輯] 以編輯您的預設原則的安全連結保護](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)
  
4. <span data-ttu-id="7291c-p106">在 [**封鎖下列 Url** ] 區段中，指定您想要避免造訪您組織中的一或多個 Url。（請參閱[Set up 自訂封鎖 Url 清單使用 ATP 安全連結](set-up-a-custom-blocked-urls-list-wtih-atp.md)）。</span><span class="sxs-lookup"><span data-stu-id="7291c-p106">In the **Block the following URLs** section, specify one or more URLs that you want to prevent people in your organization from visiting. (See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).)</span></span>
    
5. <span data-ttu-id="7291c-p107">**套用至內容除了電子郵件設定**] 區段中選取 （或清除） [您想要使用的選項。（我們建議您選取的所有選項）。</span><span class="sxs-lookup"><span data-stu-id="7291c-p107">In the **Settings that apply to content except email** section, select (or clear) the options you want to use. (We recommend that you select all the options.)</span></span> 
    
6. <span data-ttu-id="7291c-134">選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="7291c-134">Choose **Save**.</span></span>
    
## <a name="step-3-add-or-edit-atp-safe-links-policies-that-apply-to-specific-email-recipients"></a><span data-ttu-id="7291c-135">步驟 3： 新增 （或編輯） ATP 安全連結原則套用至特定電子郵件收件者</span><span class="sxs-lookup"><span data-stu-id="7291c-135">Step 3: Add (or edit) ATP Safe Links policies that apply to specific email recipients</span></span>

<span data-ttu-id="7291c-p108">檢閱 ATP 安全連結原則的所有使用者之後，請考慮其他原則定義的電子郵件收件者的特定群組。這可讓您指定為預設原則的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="7291c-p108">After you have reviewed the ATP Safe Links policy for all users, consider defining additional policies for specific groups of email recipients. This enables you to specify exceptions to your default policy.</span></span> 

> [!TIP]
> <span data-ttu-id="7291c-p109">您可以新增使用任一安全性原則&amp;規範中心 （建議使用） 或 Exchange 系統管理中心。**建議使用安全性&amp;檢閱或編輯的任何 ATP 原則規範中心**。</span><span class="sxs-lookup"><span data-stu-id="7291c-p109">You can add policies using either the Security &amp; Compliance Center (recommended) or the Exchange admin center. **We recommend using the Security &amp; Compliance Center to review or edit any of your ATP policies**.</span></span>
  
1. <span data-ttu-id="7291c-140">移至 [[https://protection.office.com](https://protection.office.com)和登入工作或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="7291c-140">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="7291c-141">在左導覽列中， **Threat management**] 下選擇 [**原則**]。</span><span class="sxs-lookup"><span data-stu-id="7291c-141">In the left navigation, under **Threat management**, choose **Policy**.</span></span>
    
3. <span data-ttu-id="7291c-142">選擇 [**安全的連結**。</span><span class="sxs-lookup"><span data-stu-id="7291c-142">Choose **Safe Links**.</span></span>
    
4. <span data-ttu-id="7291c-143">在 [**原則套用至特定收件者**] 區段中選擇 [**新增**] ([新增] 按鈕的格式類似於加號 ( **+**))。</span><span class="sxs-lookup"><span data-stu-id="7291c-143">In the **Policies that apply to specific recipients** section, choose **New** (the New button resembles a plus sign ( **+**)).</span></span>
    
    ![選擇 [新增] 可為特定電子郵件收件者新增的安全連結原則](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
5. <span data-ttu-id="7291c-145">指定原則的名稱、描述及設定。</span><span class="sxs-lookup"><span data-stu-id="7291c-145">Specify the name, description, and settings for your policy.</span></span>
    
    <span data-ttu-id="7291c-146">**範例：** 若要設定稱為 「 沒有直接點選"不允許人員的特定群組中按一下透過特定的網站不 ATP 安全連結保護組織的原則，您可能會指定下列建議設定：</span><span class="sxs-lookup"><span data-stu-id="7291c-146">**Example:** To set up a policy called "no direct click through" that does not allow people in a certain group in your organization to click through to a specific website without ATP Safe Links protection, you might specify the following recommended settings:</span></span> 
    
  - <span data-ttu-id="7291c-147">在 [**名稱**] 方塊中輸入沒有直接點選。</span><span class="sxs-lookup"><span data-stu-id="7291c-147">In the **Name** box, type no direct click through.</span></span>
    
  - <span data-ttu-id="7291c-148">在 [**描述**] 方塊中輸入像轉人員從透過按一下沒有 ATP 安全連結驗證的網站特定群組中的描述。</span><span class="sxs-lookup"><span data-stu-id="7291c-148">In the **Description** box, type a description like, Prevents people in certain groups from clicking through to a website without ATP Safe Links verification.</span></span>
    
  - <span data-ttu-id="7291c-149">**選取動作**] 區段中選擇 [**上**]。</span><span class="sxs-lookup"><span data-stu-id="7291c-149">In the **Select the action** section, choose **On**.</span></span>
    
  - <span data-ttu-id="7291c-150">選取 [**使用安全附件掃描可下載的內容**。</span><span class="sxs-lookup"><span data-stu-id="7291c-150">Select **Use Safe Attachments to scan downloadable content**.</span></span>
    
  - <span data-ttu-id="7291c-151">使用此選項時，選取 [**套用至組織內傳送訊息的安全連結**。</span><span class="sxs-lookup"><span data-stu-id="7291c-151">If this option is available, select **Apply Safe Links to messages sent within the organization**.</span></span>
    
  - <span data-ttu-id="7291c-152">選取 [**不允許使用者透過按一下以原始 URL**。</span><span class="sxs-lookup"><span data-stu-id="7291c-152">Select **Do not allow user to click through to original URL**.</span></span>
    
  - <span data-ttu-id="7291c-p110">（這是選用的）**未修正下列 Url** ] 區段中指定被視為安全組織的一或多個 Url。（請參閱[Set up 自訂 「 未修正"Url 清單使用 ATP 安全連結](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)）</span><span class="sxs-lookup"><span data-stu-id="7291c-p110">(This is optional) In the **Do not rewrite the following URLs** section, specify one or more URLs that are considered to be safe for your organization. (See [Set up a custom "Do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md))</span></span>
    
  - <span data-ttu-id="7291c-p111">**套用至**] 區段中選擇 [**收件者是成員**，然後按您想要包含在您的原則中的群組。選擇 [**新增**]，然後選擇 [ **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="7291c-p111">In the **Applied To** section, choose **The recipient is a member of**, and then choose the group(s) you want to include in your policy. Choose **Add**, and then choose **OK**.</span></span>
    
6. <span data-ttu-id="7291c-157">選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="7291c-157">Choose **Save**.</span></span>
    
## <a name="step-5-learn-about-atp-safe-links-policy-options"></a><span data-ttu-id="7291c-158">步驟 5： 了解 ATP 安全連結原則選項</span><span class="sxs-lookup"><span data-stu-id="7291c-158">Step 5: Learn about ATP Safe Links policy options</span></span>

<span data-ttu-id="7291c-p112">當您設定或編輯 ATP 安全連結原則時，會看到數個可用選項。您會知道這些選項為何下, 表說明每一個和其效果。</span><span class="sxs-lookup"><span data-stu-id="7291c-p112">As you set up or edit your ATP Safe Links policies, will see several options available. In case you are wondering what these options are, the following table describes each one and its effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="7291c-p113">有兩種主要原則來定義或編輯： 套用至所有人、 的預設原則和其他原則所定義的特定收件者。這些被區別下表中的 ["的此原則"] 欄中。</span><span class="sxs-lookup"><span data-stu-id="7291c-p113">There are two main kinds of policies to define or edit: a default policy that applies to everyone, and additional policies that are defined for specific recipients. Those are differentiated in the "For this policy" column in the following table.</span></span>
  
|<span data-ttu-id="7291c-163">**此原則**</span><span class="sxs-lookup"><span data-stu-id="7291c-163">**For this policy**</span></span>|<span data-ttu-id="7291c-164">**此選項**</span><span class="sxs-lookup"><span data-stu-id="7291c-164">**This option**</span></span>|<span data-ttu-id="7291c-165">**執行動作**</span><span class="sxs-lookup"><span data-stu-id="7291c-165">**Does this**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7291c-166">預設值 （一旦定義預設原則可套用至組織中所有的人）</span><span class="sxs-lookup"><span data-stu-id="7291c-166">Default (once defined, the default policy applies to everyone in the organization)</span></span>  <br/> |<span data-ttu-id="7291c-167">**封鎖下列 Url**</span><span class="sxs-lookup"><span data-stu-id="7291c-167">**Block the following URLs**</span></span> <br/> |<span data-ttu-id="7291c-p114">可讓您的組織具有自訂清單的自動封鎖的 Url。當使用者按一下此清單中的 URL 時，他們會前往說明 URL 封鎖的原因[警告] 頁面](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="7291c-p114">Enables your organization to have a custom list of URLs that are automatically blocked. When users click a URL in this list, they'll be taken to a [warning page](atp-safe-links-warning-pages.md) that explains why the URL is blocked.  </span></span><br/> <span data-ttu-id="7291c-170">請參閱 ＜ [Set up 自訂封鎖 Url 清單使用 ATP 安全連結](set-up-a-custom-blocked-urls-list-wtih-atp.md)如需詳細資訊，例如新增支援多達三個萬用字元星號 (\*)。</span><span class="sxs-lookup"><span data-stu-id="7291c-170">See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md) for more details, such as newly added support for up to three wildcard asterisks (\*).</span></span>  <br/> |
|<span data-ttu-id="7291c-171">預設</span><span class="sxs-lookup"><span data-stu-id="7291c-171">Default</span></span>  <br/> |<span data-ttu-id="7291c-172">**Office 365 ProPlus iOS 適用於 Office 及 android （英文）**</span><span class="sxs-lookup"><span data-stu-id="7291c-172">**Office 365 ProPlus, Office for iOS and Android**</span></span> <br/> |<span data-ttu-id="7291c-173">選取此選項時，ATP 保護套用至 Url 的文件內的安全連結中開啟 Office 365 ProPlus （Word、 Excel 及 PowerPoint Windows 或 Mac OS） iOS 或 Android 裝置上 Windows 及 Office Online (Word Visio 2016 上的 Office 文件線上、 PowerPoint Online、 Excel Online 和 OneNote Online），提供使用者已登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="7291c-173">When this option is selected, ATP Safe Links protection is applied to URLs in documents that are open in Office 365 ProPlus (Word, Excel, and PowerPoint on Windows or Mac OS), Office documents on iOS, or Android devices, Visio 2016 on Windows, and Office Online (Word Online, PowerPoint Online, Excel Online, and OneNote Online), provided the user has signed into Office 365.</span></span> <br/><br/><span data-ttu-id="7291c-p115">如果您看到只**在 Windows 的 Office 2016**，然後功能更新已無法連至 Office 365 環境尚未 （和它們即將推出）。加上 then，直到 ATP 安全連結保護適用於 Word 2016、 Excel 2016、 PowerPoint 2016 或 Visio 2016 Windows 上執行。</span><span class="sxs-lookup"><span data-stu-id="7291c-p115">If you see only **Office 2016 on Windows**, then the feature updates have not reached your Office 365 environment yet (and they are coming soon). Until then, ATP Safe Links protection applies to Word 2016, Excel 2016, PowerPoint 2016 or Visio 2016 running on Windows.</span></span>           |
|<span data-ttu-id="7291c-176">預設</span><span class="sxs-lookup"><span data-stu-id="7291c-176">Default</span></span>  <br/> |<span data-ttu-id="7291c-177">**當使用者按一下 ATP 安全連結時不要追蹤**</span><span class="sxs-lookup"><span data-stu-id="7291c-177">**Don't track when users click ATP Safe Links**</span></span> <br/> |<span data-ttu-id="7291c-178">選取此選項時，按一下資料中的不會儲存在 Word、 Excel、 PowerPoint 及 Visio 文件中的 Url。</span><span class="sxs-lookup"><span data-stu-id="7291c-178">When this option is selected, click data for URLs in Word, Excel, PowerPoint, and Visio documents is not stored.</span></span>  <br/> |
|<span data-ttu-id="7291c-179">預設</span><span class="sxs-lookup"><span data-stu-id="7291c-179">Default</span></span>  <br/> |<span data-ttu-id="7291c-180">**不讓使用者按一下 [透過 ATP 原始 URL 的安全連結**</span><span class="sxs-lookup"><span data-stu-id="7291c-180">**Don't let users click through ATP Safe Links to original URL**</span></span> <br/> |<span data-ttu-id="7291c-181">選取此選項時，使用者無法繼續過去的[警告] 頁面上](atp-safe-links-warning-pages.md)決定為惡意的 URL。</span><span class="sxs-lookup"><span data-stu-id="7291c-181">When this option is selected, users cannot proceed past a [warning page](atp-safe-links-warning-pages.md) to a URL that is determined to be malicious.</span></span>  <br/> |
|<span data-ttu-id="7291c-182">建立特定電子郵件收件者的原則</span><span class="sxs-lookup"><span data-stu-id="7291c-182">A policy created for specific email recipients</span></span>  <br/> |<span data-ttu-id="7291c-183">**Off**</span><span class="sxs-lookup"><span data-stu-id="7291c-183">**Off**</span></span> <br/> |<span data-ttu-id="7291c-184">不會掃描電子郵件訊息中的 Url。</span><span class="sxs-lookup"><span data-stu-id="7291c-184">Does not scan URLs in email messages.</span></span>  <br/> <span data-ttu-id="7291c-185">可讓您定義的例外狀況規則，例如不會掃描一組特定的收件者的電子郵件訊息中 Url 的規則。</span><span class="sxs-lookup"><span data-stu-id="7291c-185">Enables you to define an exception rule, such as a rule that does not scan URLs in email messages for a specific group of recipients.</span></span>  <br/> |
|<span data-ttu-id="7291c-186">建立特定電子郵件收件者的原則</span><span class="sxs-lookup"><span data-stu-id="7291c-186">A policy created for specific email recipients</span></span>  <br/> |<span data-ttu-id="7291c-187">**在**</span><span class="sxs-lookup"><span data-stu-id="7291c-187">**On**</span></span> <br/> |<span data-ttu-id="7291c-188">當使用者按一下 [Url] 中的電子郵件，路由使用者可透過 ATP 安全連結保護修正 Url。</span><span class="sxs-lookup"><span data-stu-id="7291c-188">Rewrites URLs to route users through ATP Safe Links protection when the users click URLs in email messages.</span></span>  <br/> <span data-ttu-id="7291c-189">檢查當您按一下針對封鎖或惡意 Url 清單的 URL。</span><span class="sxs-lookup"><span data-stu-id="7291c-189">Checks a URL when clicked against a list of blocked or malicious URLs.</span></span>  <br/> |
|<span data-ttu-id="7291c-190">建立特定電子郵件收件者的原則</span><span class="sxs-lookup"><span data-stu-id="7291c-190">A policy created for specific email recipients</span></span>  <br/> |<span data-ttu-id="7291c-191">**使用安全附件掃描的可下載內容**</span><span class="sxs-lookup"><span data-stu-id="7291c-191">**Use Safe Attachments to scan downloadable content**</span></span> <br/> |<span data-ttu-id="7291c-192">選取此選項時，會掃描指向可下載內容的 Url。</span><span class="sxs-lookup"><span data-stu-id="7291c-192">When this option is selected, URLs that point to downloadable content are scanned.</span></span>  <br/> |
|<span data-ttu-id="7291c-193">建立特定電子郵件收件者的原則</span><span class="sxs-lookup"><span data-stu-id="7291c-193">A policy created for specific email recipients</span></span>  <br/> |<span data-ttu-id="7291c-194">**套用至組織內傳送訊息的安全連結**</span><span class="sxs-lookup"><span data-stu-id="7291c-194">**Apply Safe Links to messages sent within the organization**</span></span> <br/> | <span data-ttu-id="7291c-195">當可用及選取此選項即 ATP 安全連結保護會套用至組織中所提供的電子郵件帳戶的人員之間所寄送的郵件都架設在 Office 365 的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="7291c-195">When this option is available and selected, ATP Safe Links protection is applied to email messages sent between people in your organization, provided the email accounts are hosted in Office 365.</span></span>  <br/> |
|<span data-ttu-id="7291c-196">建立特定電子郵件收件者的原則</span><span class="sxs-lookup"><span data-stu-id="7291c-196">A policy created for specific email recipients</span></span>  <br/> |<span data-ttu-id="7291c-197">**不會追蹤使用者點選**</span><span class="sxs-lookup"><span data-stu-id="7291c-197">**Do not track user clicks**</span></span> <br/> |<span data-ttu-id="7291c-p116">選取此選項時，按一下資料中的 Url 來自外部寄件者的電子郵件中不會儲存。目前不支援 URL click 追蹤組織內傳送的電子郵件訊息內的連結。</span><span class="sxs-lookup"><span data-stu-id="7291c-p116">When this option is selected, click data for URLs in email from external senders is not stored. URL click tracking for links within email messages sent within the organization is currently not supported.</span></span>  <br/> |
|<span data-ttu-id="7291c-200">建立特定電子郵件收件者的原則</span><span class="sxs-lookup"><span data-stu-id="7291c-200">A policy created for specific email recipients</span></span>  <br/> |<span data-ttu-id="7291c-201">**不允許使用者透過按一下以原始 URL**</span><span class="sxs-lookup"><span data-stu-id="7291c-201">**Do not allow users to click through to original URL**</span></span> <br/> |<span data-ttu-id="7291c-202">選取此選項時，使用者無法繼續過去的[警告] 頁面上](atp-safe-links-warning-pages.md)決定為惡意的 URL。</span><span class="sxs-lookup"><span data-stu-id="7291c-202">When this option is selected, users cannot proceed past a [warning page](atp-safe-links-warning-pages.md) to a URL that is determined to be malicious.</span></span>  <br/> |
|<span data-ttu-id="7291c-203">建立特定電子郵件收件者的原則</span><span class="sxs-lookup"><span data-stu-id="7291c-203">A policy created for specific email recipients</span></span>  <br/> |<span data-ttu-id="7291c-204">**未修正下列 Url**</span><span class="sxs-lookup"><span data-stu-id="7291c-204">**Do not rewrite the following URLs**</span></span> <br/> |<span data-ttu-id="7291c-p117">以離開 Url。保留自訂清單的安全不需要一組特定的組織中的電子郵件收件者的掃描的 Url。 請參閱 ＜ [Set up 自訂 「 未修正"Url 清單使用 ATP 安全連結](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)如需詳細資訊，包括支援的萬用字元星號最近的變更 (\*)。</span><span class="sxs-lookup"><span data-stu-id="7291c-p117">Leaves URLs as they are. Keeps a custom list of safe URLs that don't need scanning for a specific group of email recipients in your organization.  See [Set up a custom "Do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for more details, including recent changes to support for wildcard asterisks (\*).  </span></span><br/> |
   
## <a name="related-topics"></a><span data-ttu-id="7291c-208">相關主題</span><span class="sxs-lookup"><span data-stu-id="7291c-208">Related topics</span></span>

[<span data-ttu-id="7291c-209">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="7291c-209">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="7291c-210">Office 365 中的 ATP 安全連結</span><span class="sxs-lookup"><span data-stu-id="7291c-210">ATP Safe Links in Office 365</span></span>](atp-safe-links.md)
  
[<span data-ttu-id="7291c-211">Office 365 中的 ATP 安全附件</span><span class="sxs-lookup"><span data-stu-id="7291c-211">ATP Safe Attachments in Office 365</span></span>](atp-safe-attachments.md)
  
[<span data-ttu-id="7291c-212">設定自訂封鎖 Url 清單使用 ATP 安全連結</span><span class="sxs-lookup"><span data-stu-id="7291c-212">Set up a custom blocked URLs list using ATP Safe Links</span></span>](set-up-a-custom-blocked-urls-list-wtih-atp.md)
  
[<span data-ttu-id="7291c-213">設定自訂 「 未修正"Url 清單使用 ATP 安全連結</span><span class="sxs-lookup"><span data-stu-id="7291c-213">Set up a custom "Do not rewrite" URLs list using ATP Safe Links</span></span>](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)
  
[<span data-ttu-id="7291c-214">進階威脅保護的檢視報告</span><span class="sxs-lookup"><span data-stu-id="7291c-214">View the reports for Advanced Threat Protection</span></span>](view-reports-for-atp.md)

[<span data-ttu-id="7291c-215">Office 365 安全性權限&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="7291c-215">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  

