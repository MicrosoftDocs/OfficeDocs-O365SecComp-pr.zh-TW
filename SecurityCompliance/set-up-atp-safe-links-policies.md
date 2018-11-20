---
title: 設定 Office 365 ATP 安全連結原則
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.date: 11/02/2018
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
description: 設定安全的連結原則來保護您的組織不在 Word、 Excel、 PowerPoint 及 Visio 檔案，以及在電子郵件訊息中的惡意連結。
ms.openlocfilehash: 2fce043aaf6e5e844415bd0caaaded8d30c18291
ms.sourcegitcommit: 147768bbe44c8c98c02fa29ae9d882cee4ec2d6b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/09/2018
ms.locfileid: "26238455"
---
# <a name="set-up-office-365-atp-safe-links-policies"></a><span data-ttu-id="924b9-103">設定 Office 365 ATP 安全連結原則</span><span class="sxs-lookup"><span data-stu-id="924b9-103">Set up Office 365 ATP Safe Links policies</span></span>

<span data-ttu-id="924b9-p101">[ATP 安全連結](atp-safe-links.md)的[Office 365 進階威脅保護](office-365-atp.md)(ATP) 的功能可協助保護您的組織中用於網路釣魚和其他攻擊的惡意連結。如果您有必要[權限指派在 Office 365 安全性&amp;規範中心](permissions-in-the-security-and-compliance-center.md)、 您可以設定 ATP 安全連結原則以協助確保當使用者按一下 [網站位址 (Url)、 貴組織保護。ATP 安全連結原則可以設定要掃描電子郵件中的 Url 及 Office 文件中的 Url。</span><span class="sxs-lookup"><span data-stu-id="924b9-p101">[ATP Safe Links](atp-safe-links.md) , a feature of [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), can help protect your organization from malicious links used in phishing and other attacks. If you have the necessary [permissions assigned in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md), you can set up ATP Safe Links policies to help ensure that when people click web addresses (URLs), your organization is protected. Your ATP Safe Links policies can be configured to scan URLs in email and URLs in Office documents.</span></span>
  
<span data-ttu-id="924b9-p102">[ATP 持續所加入的新功能](office-365-atp.md#new-features-are-continually-being-added-to-atp)。隨著增加新功能，您可能需要調整您現有的 ATP 安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="924b9-p102">[New features are continually being added to ATP](office-365-atp.md#new-features-are-continually-being-added-to-atp). As new features are added, you may need to make adjustments to your existing ATP Safe Links policies.</span></span>

## <a name="what-to-do"></a><span data-ttu-id="924b9-109">該怎麼辦</span><span class="sxs-lookup"><span data-stu-id="924b9-109">What to do</span></span> 
  
1. <span data-ttu-id="924b9-110">[請先檢閱必要條件](#review-the-prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="924b9-110">[Review the prerequisites](#review-the-prerequisites).</span></span>
    
2. <span data-ttu-id="924b9-p103">[檢閱並編輯預設 ATP 安全連結原則可套用到所有人](#define-an-atp-safe-links-policy-that-applies-to-everyone)。例如，您可以[設定 ATP 安全連結您自訂封鎖 Url 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="924b9-p103">[Review and edit the default ATP Safe Links policy that applies to everyone](#define-an-atp-safe-links-policy-that-applies-to-everyone). For example, you can [set up your custom blocked URLs list for ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).</span></span>
    
3. <span data-ttu-id="924b9-113">[新增或編輯原則的特定電子郵件收件者](#add-a-policy-for-specific-email-recipients)，包括[您自訂 「 未修正"Url 清單 ATP 安全連結的設定](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="924b9-113">[Add or edit policies for specific email recipients](#add-a-policy-for-specific-email-recipients), including [setting up your custom "Do not rewrite" URLs list for ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
    
4. <span data-ttu-id="924b9-114">[了解 ATP 安全連結原則選項](#learn-about-atp-safe-links-policy-options)（在本文中），包括 [最近變更的設定</span><span class="sxs-lookup"><span data-stu-id="924b9-114">[Learn about ATP Safe Links policy options](#learn-about-atp-safe-links-policy-options) (in this article), including settings for recent changes</span></span>
    
## <a name="step-1-review-the-prerequisites"></a><span data-ttu-id="924b9-115">步驟 1： 檢閱必要條件</span><span class="sxs-lookup"><span data-stu-id="924b9-115">Step 1: Review the prerequisites</span></span>

- <span data-ttu-id="924b9-116">請確定您的組織具有[Office 365 進階威脅保護](office-365-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="924b9-116">Make sure that your organization has [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span>
    
- <span data-ttu-id="924b9-p104">請確定您已定義或編輯 ATP 原則的必要權限。請參閱[中的 Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="924b9-p104">Make sure that you have the necessary permissions to define or edit ATP policies. See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="924b9-119">請確定 Office 用戶端設定為使用[經過驗證](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)（這是 Office 文件中的 ATP 安全連結保護）。</span><span class="sxs-lookup"><span data-stu-id="924b9-119">Make sure that Office clients are configured to use [Modern Authentication](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016) (this is for ATP Safe Links protection in Office documents).</span></span>
    
- <span data-ttu-id="924b9-120">[了解 ATP 安全連結原則選項](#learn-about-atp-safe-links-policy-options)（在本文）。</span><span class="sxs-lookup"><span data-stu-id="924b9-120">[Learn about ATP Safe Links policy options](#learn-about-atp-safe-links-policy-options) (in this article).</span></span> 

- <span data-ttu-id="924b9-121">可讓您新增或更新原則散佈到所有 Office 365 資料中心的最多 30 分鐘。</span><span class="sxs-lookup"><span data-stu-id="924b9-121">Allow up to 30 minutes for your new or updated policy to spread to all Office 365 datacenters.</span></span>
    
## <a name="step-2-define-or-review-the-atp-safe-links-policy-that-applies-to-everyone"></a><span data-ttu-id="924b9-122">步驟 2： 定義 （或檢閱） 套用至所有人 ATP 安全連結原則</span><span class="sxs-lookup"><span data-stu-id="924b9-122">Step 2: Define (or review) the ATP Safe Links policy that applies to everyone</span></span>

<span data-ttu-id="924b9-p105">當您有[Office 365 進階威脅保護](office-365-atp.md)時，您必須套用至組織中所有人預設 ATP 安全連結原則。請務必檢閱，並視需要編輯預設原則。</span><span class="sxs-lookup"><span data-stu-id="924b9-p105">When you have [Office 365 Advanced Threat Protection](office-365-atp.md), you will have a default ATP Safe Links policy that applies to everyone in your organization. Make sure to review, and if needed, edit your default policy.</span></span>
  
1. <span data-ttu-id="924b9-125">移至 [[https://protection.office.com](https://protection.office.com)和登入工作或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="924b9-125">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="924b9-126">在左導覽列中， **Threat management**] 下選擇**原則\>\*\*\*\*安全的連結**。</span><span class="sxs-lookup"><span data-stu-id="924b9-126">In the left navigation, under **Threat management**, choose **Policy \>** **Safe Links**.</span></span>
    
3. <span data-ttu-id="924b9-127">**套用至整個組織的原則**] 區段中選取 [**預設**]，然後選擇**編輯**（[編輯] 按鈕以鉛筆）。</span><span class="sxs-lookup"><span data-stu-id="924b9-127">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span> 
    
    ![按一下 [編輯] 以編輯您的預設原則的安全連結保護](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)
  
4. <span data-ttu-id="924b9-p106">在 [**封鎖下列 Url** ] 區段中，指定您想要避免造訪您組織中的一或多個 Url。（請參閱[Set up 自訂封鎖 Url 清單使用 ATP 安全連結](set-up-a-custom-blocked-urls-list-wtih-atp.md)）。</span><span class="sxs-lookup"><span data-stu-id="924b9-p106">In the **Block the following URLs** section, specify one or more URLs that you want to prevent people in your organization from visiting. (See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).)</span></span>
    
5. <span data-ttu-id="924b9-p107">**套用至內容除了電子郵件設定**] 區段中選取 （或清除） [您想要使用的選項。（我們建議您選取的所有選項）。</span><span class="sxs-lookup"><span data-stu-id="924b9-p107">In the **Settings that apply to content except email** section, select (or clear) the options you want to use. (We recommend that you select all the options.)</span></span> 
    
6. <span data-ttu-id="924b9-133">選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="924b9-133">Choose **Save**.</span></span>
    
## <a name="step-3-add-or-edit-atp-safe-links-policies-that-apply-to-specific-email-recipients"></a><span data-ttu-id="924b9-134">步驟 3： 新增 （或編輯） ATP 安全連結原則套用至特定電子郵件收件者</span><span class="sxs-lookup"><span data-stu-id="924b9-134">Step 3: Add (or edit) ATP Safe Links policies that apply to specific email recipients</span></span>

<span data-ttu-id="924b9-p108">您已檢閱 （或編輯） 套用至所有人預設 ATP 安全連結原則之後下, 一步是定義會套用至特定收件者的其他原則。例如，您可以指定例外狀況為預設原則所定義的其他原則。</span><span class="sxs-lookup"><span data-stu-id="924b9-p108">After you have reviewed (or edited) the default ATP Safe Links policy that applies to everyone, your next step is to define additional policies that would apply to specific recipients. For example, you can specify exceptions to your default policy by defining an additional policy.</span></span> 
  
1. <span data-ttu-id="924b9-137">移至 [[https://protection.office.com](https://protection.office.com)和登入工作或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="924b9-137">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="924b9-138">在左導覽列中， **Threat management**] 下選擇 [**原則**]。</span><span class="sxs-lookup"><span data-stu-id="924b9-138">In the left navigation, under **Threat management**, choose **Policy**.</span></span>
    
3. <span data-ttu-id="924b9-139">選擇 [**安全的連結**。</span><span class="sxs-lookup"><span data-stu-id="924b9-139">Choose **Safe Links**.</span></span>
    
4. <span data-ttu-id="924b9-140">在 [**原則套用至特定收件者**] 區段中選擇 [**新增**] ([新增] 按鈕的格式類似於加號 ( **+**))。</span><span class="sxs-lookup"><span data-stu-id="924b9-140">In the **Policies that apply to specific recipients** section, choose **New** (the New button resembles a plus sign ( **+**)).</span></span><br/><span data-ttu-id="924b9-141">![選擇 [新增] 可為特定電子郵件收件者新增的安全連結原則](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span><span class="sxs-lookup"><span data-stu-id="924b9-141">![Choose New to add a Safe Links policy for specific email recipients](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span></span>
  
5. <span data-ttu-id="924b9-142">指定原則的名稱、描述及設定。</span><span class="sxs-lookup"><span data-stu-id="924b9-142">Specify the name, description, and settings for your policy.</span></span><br/><span data-ttu-id="924b9-143">**範例：** 若要設定稱為 「 沒有直接點選"不允許人員的特定群組中按一下透過特定的網站不 ATP 安全連結保護組織的原則，您可能會指定下列建議設定：</span><span class="sxs-lookup"><span data-stu-id="924b9-143">**Example:** To set up a policy called "no direct click through" that does not allow people in a certain group in your organization to click through to a specific website without ATP Safe Links protection, you might specify the following recommended settings:</span></span> 
    
  - <span data-ttu-id="924b9-144">在 [**名稱**] 方塊中輸入沒有直接點選。</span><span class="sxs-lookup"><span data-stu-id="924b9-144">In the **Name** box, type no direct click through.</span></span>
    
  - <span data-ttu-id="924b9-145">在 [**描述**] 方塊中輸入像轉人員從透過按一下沒有 ATP 安全連結驗證的網站特定群組中的描述。</span><span class="sxs-lookup"><span data-stu-id="924b9-145">In the **Description** box, type a description like, Prevents people in certain groups from clicking through to a website without ATP Safe Links verification.</span></span>
    
  - <span data-ttu-id="924b9-146">**選取動作**] 區段中選擇 [**上**]。</span><span class="sxs-lookup"><span data-stu-id="924b9-146">In the **Select the action** section, choose **On**.</span></span>
    
  - <span data-ttu-id="924b9-147">選取 [**使用安全附件掃描可下載的內容**。</span><span class="sxs-lookup"><span data-stu-id="924b9-147">Select **Use Safe Attachments to scan downloadable content**.</span></span>
    
  - <span data-ttu-id="924b9-148">使用此選項時，選取 [**套用至組織內傳送訊息的安全連結**。</span><span class="sxs-lookup"><span data-stu-id="924b9-148">If this option is available, select **Apply Safe Links to messages sent within the organization**.</span></span>
    
  - <span data-ttu-id="924b9-149">選取 [**不允許使用者透過按一下以原始 URL**。</span><span class="sxs-lookup"><span data-stu-id="924b9-149">Select **Do not allow user to click through to original URL**.</span></span>
    
  - <span data-ttu-id="924b9-p109">（這是選用的）**未修正下列 Url** ] 區段中指定被視為安全組織的一或多個 Url。（請參閱[Set up 自訂 「 未修正"Url 清單使用 ATP 安全連結](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)）</span><span class="sxs-lookup"><span data-stu-id="924b9-p109">(This is optional) In the **Do not rewrite the following URLs** section, specify one or more URLs that are considered to be safe for your organization. (See [Set up a custom "Do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md))</span></span>
    
  - <span data-ttu-id="924b9-p110">**套用至**] 區段中選擇 [**收件者是成員**，然後按您想要包含在您的原則中的群組。選擇 [**新增**]，然後選擇 [ **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="924b9-p110">In the **Applied To** section, choose **The recipient is a member of**, and then choose the group(s) you want to include in your policy. Choose **Add**, and then choose **OK**.</span></span>
    
6. <span data-ttu-id="924b9-154">選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="924b9-154">Choose **Save**.</span></span>
    
## <a name="step-4-learn-about-atp-safe-links-policy-options"></a><span data-ttu-id="924b9-155">步驟 4︰ 了解 ATP 安全連結原則選項</span><span class="sxs-lookup"><span data-stu-id="924b9-155">Step 4: Learn about ATP Safe Links policy options</span></span>

<span data-ttu-id="924b9-p111">當您設定或編輯 ATP 安全連結原則時，會看到數個可用選項。您會知道這些選項為何下, 表說明每一個和其效果。有兩種主要定義或編輯 ATP 安全連結原則，請記得：</span><span class="sxs-lookup"><span data-stu-id="924b9-p111">As you set up or edit your ATP Safe Links policies, will see several options available. In case you are wondering what these options are, the following table describes each one and its effect. Remember that there are two main kinds of ATP Safe Links policies to define or edit:</span></span>
- <span data-ttu-id="924b9-159">套用至所有人的[預設原則](#default-policy-options)</span><span class="sxs-lookup"><span data-stu-id="924b9-159">a [default policy](#default-policy-options) that applies to everyone</span></span> 
- <span data-ttu-id="924b9-160">其他[原則所定義的特定收件者](#policies-that-apply-to-specific-email-recipients)</span><span class="sxs-lookup"><span data-stu-id="924b9-160">additional [policies that are defined for specific recipients](#policies-that-apply-to-specific-email-recipients)</span></span> 

### <a name="default-policy-options"></a><span data-ttu-id="924b9-161">預設原則選項</span><span class="sxs-lookup"><span data-stu-id="924b9-161">Default policy options</span></span>

<span data-ttu-id="924b9-162">預設原則選項套用至組織中所有的人。</span><span class="sxs-lookup"><span data-stu-id="924b9-162">Default policy options apply to everyone in your organization.</span></span>

|<span data-ttu-id="924b9-163">此選項</span><span class="sxs-lookup"><span data-stu-id="924b9-163">This option</span></span>  |<span data-ttu-id="924b9-164">執行動作</span><span class="sxs-lookup"><span data-stu-id="924b9-164">Does this</span></span>  |
|---------|---------|
| <span data-ttu-id="924b9-165">**封鎖下列 Url**</span><span class="sxs-lookup"><span data-stu-id="924b9-165">**Block the following URLs**</span></span> <br/>    | <span data-ttu-id="924b9-p112">可讓您的組織具有自訂清單的自動封鎖的 Url。當使用者按一下此清單中的 URL 時，他們會前往說明 URL 封鎖的原因[警告] 頁面](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="924b9-p112">Enables your organization to have a custom list of URLs that are automatically blocked. When users click a URL in this list, they'll be taken to a [warning page](atp-safe-links-warning-pages.md) that explains why the URL is blocked.  </span></span><br/> <span data-ttu-id="924b9-168">若要深入了解，請參閱 [Set up 自訂封鎖 Url 清單使用 ATP 安全連結</span><span class="sxs-lookup"><span data-stu-id="924b9-168">To learn more, see [Set up a custom blocked URLs list using ATP Safe Links</span></span>      |
| <span data-ttu-id="924b9-169">**Office 365 ProPlus iOS 適用於 Office 及 android （英文）**</span><span class="sxs-lookup"><span data-stu-id="924b9-169">**Office 365 ProPlus, Office for iOS and Android**</span></span> <br/>    | <span data-ttu-id="924b9-170">選取此選項時，ATP 保護套用至 Url 的文件內的安全連結中開啟 Office 365 ProPlus （Word、 Excel 及 PowerPoint Windows 或 Mac OS） iOS 或 Android 裝置上 Windows 及 Office Online (Word Visio 2016 上的 Office 文件線上、 PowerPoint Online、 Excel Online 和 OneNote Online），提供使用者已登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="924b9-170">When this option is selected, ATP Safe Links protection is applied to URLs in documents that are open in Office 365 ProPlus (Word, Excel, and PowerPoint on Windows or Mac OS), Office documents on iOS, or Android devices, Visio 2016 on Windows, and Office Online (Word Online, PowerPoint Online, Excel Online, and OneNote Online), provided the user has signed into Office 365.</span></span> <br/><br/><span data-ttu-id="924b9-p113">如果您看到只**在 Windows 的 Office 2016**，然後功能更新已無法連至 Office 365 環境尚未 （和它們即將推出）。加上 then，直到 ATP 安全連結保護適用於 Word 2016、 Excel 2016、 PowerPoint 2016 或 Visio 2016 Windows 上執行。</span><span class="sxs-lookup"><span data-stu-id="924b9-p113">If you see only **Office 2016 on Windows**, then the feature updates have not reached your Office 365 environment yet (and they are coming soon). Until then, ATP Safe Links protection applies to Word 2016, Excel 2016, PowerPoint 2016 or Visio 2016 running on Windows.</span></span>            |
| <span data-ttu-id="924b9-173">**當使用者按一下 ATP 安全連結時不要追蹤**</span><span class="sxs-lookup"><span data-stu-id="924b9-173">**Don't track when users click ATP Safe Links**</span></span> <br/>  | <span data-ttu-id="924b9-174">選取此選項時，按一下資料中的不會儲存在 Word、 Excel、 PowerPoint 及 Visio 文件中的 Url。</span><span class="sxs-lookup"><span data-stu-id="924b9-174">When this option is selected, click data for URLs in Word, Excel, PowerPoint, and Visio documents is not stored.</span></span>  <br/> |
|<span data-ttu-id="924b9-175">**不讓使用者按一下 [透過 ATP 原始 URL 的安全連結**</span><span class="sxs-lookup"><span data-stu-id="924b9-175">**Don't let users click through ATP Safe Links to original URL**</span></span> <br/> |<span data-ttu-id="924b9-176">選取此選項時，使用者無法繼續過去的[警告] 頁面上](atp-safe-links-warning-pages.md)決定為惡意的 URL。</span><span class="sxs-lookup"><span data-stu-id="924b9-176">When this option is selected, users cannot proceed past a [warning page](atp-safe-links-warning-pages.md) to a URL that is determined to be malicious.</span></span>  <br/> |

### <a name="policies-that-apply-to-specific-email-recipients"></a><span data-ttu-id="924b9-177">套用至特定電子郵件收件者的原則</span><span class="sxs-lookup"><span data-stu-id="924b9-177">Policies that apply to specific email recipients</span></span>

|<span data-ttu-id="924b9-178">此選項</span><span class="sxs-lookup"><span data-stu-id="924b9-178">This option</span></span>  |<span data-ttu-id="924b9-179">執行動作</span><span class="sxs-lookup"><span data-stu-id="924b9-179">Does this</span></span>  |
|---------|---------|
|<span data-ttu-id="924b9-180">**Off**</span><span class="sxs-lookup"><span data-stu-id="924b9-180">**Off**</span></span> <br/> |<span data-ttu-id="924b9-181">不會掃描電子郵件訊息中的 Url。</span><span class="sxs-lookup"><span data-stu-id="924b9-181">Does not scan URLs in email messages.</span></span>  <br/> <span data-ttu-id="924b9-182">可讓您定義的例外狀況規則，例如不會掃描一組特定的收件者的電子郵件訊息中 Url 的規則。</span><span class="sxs-lookup"><span data-stu-id="924b9-182">Enables you to define an exception rule, such as a rule that does not scan URLs in email messages for a specific group of recipients.</span></span>  <br/> |
|<span data-ttu-id="924b9-183">**在**</span><span class="sxs-lookup"><span data-stu-id="924b9-183">**On**</span></span> <br/> |<span data-ttu-id="924b9-184">當使用者按一下 [Url] 中的電子郵件，路由使用者可透過 ATP 安全連結保護修正 Url。</span><span class="sxs-lookup"><span data-stu-id="924b9-184">Rewrites URLs to route users through ATP Safe Links protection when the users click URLs in email messages.</span></span>  <br/> <span data-ttu-id="924b9-185">檢查當您按一下針對封鎖或惡意 Url 清單的 URL。</span><span class="sxs-lookup"><span data-stu-id="924b9-185">Checks a URL when clicked against a list of blocked or malicious URLs.</span></span>  <br/> |
|<span data-ttu-id="924b9-186">**使用安全附件掃描的可下載內容**</span><span class="sxs-lookup"><span data-stu-id="924b9-186">**Use Safe Attachments to scan downloadable content**</span></span> <br/> |<span data-ttu-id="924b9-187">選取此選項時，會掃描指向可下載內容的 Url。</span><span class="sxs-lookup"><span data-stu-id="924b9-187">When this option is selected, URLs that point to downloadable content are scanned.</span></span>  <br/> |
|<span data-ttu-id="924b9-188">**套用至組織內傳送訊息的安全連結**</span><span class="sxs-lookup"><span data-stu-id="924b9-188">**Apply Safe Links to messages sent within the organization**</span></span> <br/> | <span data-ttu-id="924b9-189">當可用及選取此選項即 ATP 安全連結保護會套用至組織中所提供的電子郵件帳戶的人員之間所寄送的郵件都架設在 Office 365 的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="924b9-189">When this option is available and selected, ATP Safe Links protection is applied to email messages sent between people in your organization, provided the email accounts are hosted in Office 365.</span></span>  <br/> |
|<span data-ttu-id="924b9-190">**不會追蹤使用者點選**</span><span class="sxs-lookup"><span data-stu-id="924b9-190">**Do not track user clicks**</span></span> <br/> |<span data-ttu-id="924b9-p114">選取此選項時，按一下資料中的 Url 來自外部寄件者的電子郵件中不會儲存。目前不支援 URL click 追蹤組織內傳送的電子郵件訊息內的連結。</span><span class="sxs-lookup"><span data-stu-id="924b9-p114">When this option is selected, click data for URLs in email from external senders is not stored. URL click tracking for links within email messages sent within the organization is currently not supported.</span></span>  <br/> |
|<span data-ttu-id="924b9-193">**不允許使用者透過按一下以原始 URL**</span><span class="sxs-lookup"><span data-stu-id="924b9-193">**Do not allow users to click through to original URL**</span></span> <br/> |<span data-ttu-id="924b9-194">選取此選項時，使用者無法繼續過去的[警告] 頁面上](atp-safe-links-warning-pages.md)決定為惡意的 URL。</span><span class="sxs-lookup"><span data-stu-id="924b9-194">When this option is selected, users cannot proceed past a [warning page](atp-safe-links-warning-pages.md) to a URL that is determined to be malicious.</span></span>  <br/> |
|<span data-ttu-id="924b9-195">**未修正下列 Url**</span><span class="sxs-lookup"><span data-stu-id="924b9-195">**Do not rewrite the following URLs**</span></span> <br/> |<span data-ttu-id="924b9-p115">以離開 Url。保留自訂清單的安全不需要一組特定的組織中的電子郵件收件者的掃描的 Url。 請參閱 ＜ [Set up 自訂 「 未修正"Url 清單使用 ATP 安全連結](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)如需詳細資訊，包括支援的萬用字元星號最近的變更 (\*)。</span><span class="sxs-lookup"><span data-stu-id="924b9-p115">Leaves URLs as they are. Keeps a custom list of safe URLs that don't need scanning for a specific group of email recipients in your organization.  See [Set up a custom "Do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for more details, including recent changes to support for wildcard asterisks (\*).  </span></span><br/> |
   
## <a name="next-steps"></a><span data-ttu-id="924b9-199">後續步驟</span><span class="sxs-lookup"><span data-stu-id="924b9-199">Next steps</span></span>

<span data-ttu-id="924b9-p116">一旦您 ATP 安全連結原則已備妥，您可以看到 ATP 如何為貴組織運作檢視報告。請參閱下列資源以深入了解：</span><span class="sxs-lookup"><span data-stu-id="924b9-p116">Once your ATP Safe Links policies are in place, you can see how ATP is working for your orgnization by viewing reports. See the following resources to learn more:</span></span>

- [<span data-ttu-id="924b9-202">Office 365 進階威脅保護的檢視報告</span><span class="sxs-lookup"><span data-stu-id="924b9-202">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

- [<span data-ttu-id="924b9-203">使用瀏覽器安全性&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="924b9-203">Use Explorer in the Security &amp; Compliance Center</span></span>](use-explorer-in-security-and-compliance.md) 