---
title: 防範 Office 365 中的威脅
ms.author: tracyp
author: msfttracyp
manager: laurawi
ms.audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: 使用本文做為指南，現在設定您的威脅防護功能。
ms.openlocfilehash: 646ec220bf4649472d4ab885824010bc32ea862c
ms.sourcegitcommit: e23b84ef4eee9cccec7205826b71ddfe9aaac2f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/28/2019
ms.locfileid: "33402981"
---
# <a name="protect-against-threats-in-office-365"></a><span data-ttu-id="c79b1-103">防範 Office 365 中的威脅</span><span class="sxs-lookup"><span data-stu-id="c79b1-103">Protect against threats in Office 365</span></span>

<span data-ttu-id="c79b1-104">Office 365 包含各種威脅防護功能。</span><span class="sxs-lookup"><span data-stu-id="c79b1-104">Office 365 includes a variety of threat protection features.</span></span> <span data-ttu-id="c79b1-105">以下為您的組織設定您可以使用為檢查清單，以確定您威脅保護功能快速入門指南。</span><span class="sxs-lookup"><span data-stu-id="c79b1-105">Here's a quick-start guide you can use as a checklist to make sure your threat protection features are set up for your organization.</span></span> <span data-ttu-id="c79b1-106">如果您是初次使用 Office 365 中的威脅保護功能，或您不只是確定要開始，請使用下列指引做為起點。</span><span class="sxs-lookup"><span data-stu-id="c79b1-106">If you're new to threat protection features in Office 365, or you're just not sure where to begin, use the following guidance as a starting point.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="c79b1-107">**初始建議的設定包含每種原則; 不過，有許多選項可用，且您可以調整您的設定以符合您特定的組織需求**。</span><span class="sxs-lookup"><span data-stu-id="c79b1-107">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="c79b1-108">允許大約 30 分鐘，為您的原則或變更其透過您的資料中心的方式運作。</span><span class="sxs-lookup"><span data-stu-id="c79b1-108">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="requirements"></a><span data-ttu-id="c79b1-109">需求</span><span class="sxs-lookup"><span data-stu-id="c79b1-109">Requirements</span></span>

### <a name="subscriptions"></a><span data-ttu-id="c79b1-110">訂閱</span><span class="sxs-lookup"><span data-stu-id="c79b1-110">Subscriptions</span></span>

<span data-ttu-id="c79b1-111">在所有 Office 365 訂閱中; 包含威脅保護功能不過，有些訂閱包含更進階的功能。</span><span class="sxs-lookup"><span data-stu-id="c79b1-111">Threat protection features are included in all Office 365 subscriptions; however, some subscriptions include more advanced features.</span></span> <span data-ttu-id="c79b1-112">下表列出這篇文章搭配最小訂閱需求的保護功能。</span><span class="sxs-lookup"><span data-stu-id="c79b1-112">The following table lists the protection features included in this article together with the minimum subscription requirements.</span></span><br/>

|<span data-ttu-id="c79b1-113">保護類型</span><span class="sxs-lookup"><span data-stu-id="c79b1-113">Protection type</span></span>  |<span data-ttu-id="c79b1-114">訂閱需求</span><span class="sxs-lookup"><span data-stu-id="c79b1-114">Subscription requirement</span></span>  |
|---------|---------|
|<span data-ttu-id="c79b1-115">反惡意程式碼保護</span><span class="sxs-lookup"><span data-stu-id="c79b1-115">Anti-malware protection</span></span>    | <span data-ttu-id="c79b1-116">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)(EOP)</span><span class="sxs-lookup"><span data-stu-id="c79b1-116">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) (EOP)</span></span>        |
|<span data-ttu-id="c79b1-117">從惡意 Url 與電子郵件和 Office 文件中的檔案保護</span><span class="sxs-lookup"><span data-stu-id="c79b1-117">Protection from malicious URLs and files in email and Office documents</span></span>    | [<span data-ttu-id="c79b1-118">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="c79b1-118">Office 365 ATP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)        |
|<span data-ttu-id="c79b1-119">反網路釣魚保護</span><span class="sxs-lookup"><span data-stu-id="c79b1-119">Anti-phishing protection</span></span>    | [<span data-ttu-id="c79b1-120">EOP</span><span class="sxs-lookup"><span data-stu-id="c79b1-120">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)      |
|<span data-ttu-id="c79b1-121">進階反網路釣魚保護</span><span class="sxs-lookup"><span data-stu-id="c79b1-121">Advanced anti-phishing protection</span></span>    | [<span data-ttu-id="c79b1-122">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="c79b1-122">Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)   |
|<span data-ttu-id="c79b1-123">反垃圾郵件保護</span><span class="sxs-lookup"><span data-stu-id="c79b1-123">Anti-spam protection</span></span>     | [<span data-ttu-id="c79b1-124">EOP</span><span class="sxs-lookup"><span data-stu-id="c79b1-124">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)       |
|<span data-ttu-id="c79b1-125">零時差自動清除 （適用於電子郵件）</span><span class="sxs-lookup"><span data-stu-id="c79b1-125">Zero-hour auto purge (for email)</span></span>    | <span data-ttu-id="c79b1-126">[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)(EOP)</span><span class="sxs-lookup"><span data-stu-id="c79b1-126">[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) (EOP)</span></span>        |
|<span data-ttu-id="c79b1-127">稽核的記錄 （這用來報告之用）</span><span class="sxs-lookup"><span data-stu-id="c79b1-127">Audit logging (this is used for reporting purposes)</span></span>    | [<span data-ttu-id="c79b1-128">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c79b1-128">Exchange Online</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description)        |

### <a name="roles-and-permissions"></a><span data-ttu-id="c79b1-129">角色及權限</span><span class="sxs-lookup"><span data-stu-id="c79b1-129">Roles and permissions</span></span>

<span data-ttu-id="c79b1-130">您必須獲指派適當的角色，才能設定[安全性 & 合規性中心](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)中的原則。</span><span class="sxs-lookup"><span data-stu-id="c79b1-130">You must be assigned an appropriate role to configure policies in the [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="c79b1-131">下表包含一些範例：</span><span class="sxs-lookup"><span data-stu-id="c79b1-131">The following table includes some examples:</span></span> 

|<span data-ttu-id="c79b1-132">角色或角色群組</span><span class="sxs-lookup"><span data-stu-id="c79b1-132">Role or role group</span></span>  |<span data-ttu-id="c79b1-133">若要了解更多的位置</span><span class="sxs-lookup"><span data-stu-id="c79b1-133">Where to learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="c79b1-134">Office 365 全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="c79b1-134">Office 365 Global Administrator</span></span> |[<span data-ttu-id="c79b1-135">關於 Office 365 系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="c79b1-135">About Office 365 admin roles</span></span>](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|<span data-ttu-id="c79b1-136">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="c79b1-136">Security Administrator</span></span> |[<span data-ttu-id="c79b1-137">在 Azure Active Directory 系統管理員角色權限</span><span class="sxs-lookup"><span data-stu-id="c79b1-137">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="c79b1-138">Exchange Online 組織管理</span><span class="sxs-lookup"><span data-stu-id="c79b1-138">Exchange Online Organization Management</span></span> |[<span data-ttu-id="c79b1-139">權限在 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c79b1-139">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/en-us/exchange/permissions-exo/permissions-exo) <br><span data-ttu-id="c79b1-140">與</span><span class="sxs-lookup"><span data-stu-id="c79b1-140">and</span></span><br> [<span data-ttu-id="c79b1-141">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="c79b1-141">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|

<span data-ttu-id="c79b1-142">若要深入了解，請參閱[中 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="c79b1-142">To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="part-1---anti-malware-protection"></a><span data-ttu-id="c79b1-143">第 1 部份-反惡意程式碼保護</span><span class="sxs-lookup"><span data-stu-id="c79b1-143">Part 1 - Anti-malware protection</span></span>

<span data-ttu-id="c79b1-144">在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) (EOP) 的訂閱中使用[反惡意程式碼保護](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="c79b1-144">[Anti-malware protection](anti-malware-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) (EOP).</span></span> 

1. <span data-ttu-id="c79b1-145">在 [[安全性 & 合規性中心](https://protection.office.com)中，選擇 [**威脅管理** > **原則** > **反惡意程式碼**。</span><span class="sxs-lookup"><span data-stu-id="c79b1-145">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-malware**.</span></span>

2. <span data-ttu-id="c79b1-146">連按兩下**預設**原則]，然後再選擇 [**設定**。</span><span class="sxs-lookup"><span data-stu-id="c79b1-146">Double-click the **Default** policy, and then choose **settings**.</span></span>

3. <span data-ttu-id="c79b1-147">指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="c79b1-147">Specify the following settings:</span></span>
    
    - <span data-ttu-id="c79b1-148">在 [**惡意程式碼偵測回應**] 區段中，保留預設設定 [**否]**。</span><span class="sxs-lookup"><span data-stu-id="c79b1-148">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>
   
    - <span data-ttu-id="c79b1-149">**常見附件類型篩選**] 區段中，選擇 [**上**]。</span><span class="sxs-lookup"><span data-stu-id="c79b1-149">In the **Common Attachment Types Filter** section, choose **On**.</span></span>

4. <span data-ttu-id="c79b1-150">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c79b1-150">Click **Save**.</span></span>

<span data-ttu-id="c79b1-151">若要深入了解反惡意程式碼原則選項，請參閱 <<c0>設定反惡意程式碼原則。</span><span class="sxs-lookup"><span data-stu-id="c79b1-151">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---protection-from-malicious-urls-and-files"></a><span data-ttu-id="c79b1-152">第 2 層保護來自惡意 Url 和檔案</span><span class="sxs-lookup"><span data-stu-id="c79b1-152">Part 2 - Protection from malicious URLs and files</span></span>

<span data-ttu-id="c79b1-153">按一下 [時間保護來自惡意 Url 與檔案提供訂用帳戶包含[Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP) 功能，而且透過[ATP 安全附件](atp-safe-attachments.md)和[ATP 安全連結](atp-safe-links.md)原則設定。</span><span class="sxs-lookup"><span data-stu-id="c79b1-153">Time-of-click protection from malicious URLs and files is available in subscriptions that include [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP), and is set up through [ATP Safe Attachments](atp-safe-attachments.md) and [ATP Safe Links](atp-safe-links.md) policies.</span></span>

### <a name="atp-safe-attachments-policies"></a><span data-ttu-id="c79b1-154">ATP 安全附件原則</span><span class="sxs-lookup"><span data-stu-id="c79b1-154">ATP Safe Attachments policies</span></span>

<span data-ttu-id="c79b1-155">若要設定[ATP 安全附件](atp-safe-attachments.md)，您必須定義至少一個 ATP 安全附件原則。</span><span class="sxs-lookup"><span data-stu-id="c79b1-155">To set up [ATP Safe Attachments](atp-safe-attachments.md), you must define at least one ATP Safe Attachments policy.</span></span> 

1. <span data-ttu-id="c79b1-156">在 [[安全性 & 合規性中心](https://protection.office.com)中，選擇 [**威脅管理** > **原則** > **ATP 安全附件**。</span><span class="sxs-lookup"><span data-stu-id="c79b1-156">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP safe attachments**.</span></span>

2. <span data-ttu-id="c79b1-157">選取 [**開啟 ATP SharePoint、 OneDrive 及 Microsoft Teams**] 選項。</span><span class="sxs-lookup"><span data-stu-id="c79b1-157">Select the option **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

3. <span data-ttu-id="c79b1-158">在 [**保護電子郵件附件**] 區段中，按一下加號 (**+**)。</span><span class="sxs-lookup"><span data-stu-id="c79b1-158">In the **Protect email attachments** section, click the plus sign (**+**).</span></span>

4. <span data-ttu-id="c79b1-159">指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="c79b1-159">Specify the following settings:</span></span>

    - <span data-ttu-id="c79b1-160">在 [**名稱**] 方塊中，輸入`Block malware`。</span><span class="sxs-lookup"><span data-stu-id="c79b1-160">In the **Name** box, type `Block malware`.</span></span>

    - <span data-ttu-id="c79b1-161">在 [回應] 區段中，選擇 [**封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="c79b1-161">In the response section, choose **Block**.</span></span>

    - <span data-ttu-id="c79b1-162">在**重新導向附件**] 區段中，選取 [**啟用重新導向**，] 選項，然後指定貴組織的安全性系統管理員或運算子會檢閱者的電子郵件地址偵測到的檔案。</span><span class="sxs-lookup"><span data-stu-id="c79b1-162">In the **Redirect attachment** section, select the option **Enable redirect**, and then specify the email address for your organization's security administrator or operator who will review detected files.</span></span>

    - <span data-ttu-id="c79b1-163">在 [**套用至**] 區段中，選擇 [**收件者網域是**]。</span><span class="sxs-lookup"><span data-stu-id="c79b1-163">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="c79b1-164">接著，選取您的網域選擇 [**新增**]，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="c79b1-164">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

5. <span data-ttu-id="c79b1-165">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c79b1-165">Click **Save**.</span></span>

6. <span data-ttu-id="c79b1-166">（**建議使用額外的步驟**）以全域系統管理員或 SharePoint Online 管理員執行**[Set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** 指令程式搭配**DisallowInfectedFileDownload**參數設為*true*適用於 Office 365 環境。</span><span class="sxs-lookup"><span data-stu-id="c79b1-166">(**Recommended additional step**) As a global administrator or a SharePoint Online administrator run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true* for your Office 365 environment.</span></span> <span data-ttu-id="c79b1-167">（這可防止人員開啟、 移動、 複製或共用檔案，就會被視為惡意。）</span><span class="sxs-lookup"><span data-stu-id="c79b1-167">(This prevents people from opening, moving, copying, or sharing files that are detected as malicious.)</span></span>  

<span data-ttu-id="c79b1-168">若要了解更多，請參閱[設定 Office 365 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)及[開啟 Office 365 ATP SharePoint、 OneDrive 及 Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="c79b1-168">To learn more, see [Set up Office 365 ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="atp-safe-links-policies"></a><span data-ttu-id="c79b1-169">ATP 安全連結原則</span><span class="sxs-lookup"><span data-stu-id="c79b1-169">ATP Safe Links policies</span></span>

<span data-ttu-id="c79b1-170">若要設定[ATP 安全連結](atp-safe-links.md)，請先檢閱和編輯您的預設原則，並新增特定使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="c79b1-170">To set up [ATP Safe Links](atp-safe-links.md), review and edit your default policy, and add a policy for specific users.</span></span>

1. <span data-ttu-id="c79b1-171">在 [[安全性 & 合規性中心](https://protection.office.com)中，選擇 [**威脅管理** > **原則** > **ATP 安全連結**。</span><span class="sxs-lookup"><span data-stu-id="c79b1-171">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP Safe Links**.</span></span>

2. <span data-ttu-id="c79b1-172">連按兩下**預設**原則。</span><span class="sxs-lookup"><span data-stu-id="c79b1-172">Double-click the **Default** policy.</span></span>

3. <span data-ttu-id="c79b1-173">在**使用中的安全連結**] 區段中，選取 [ **Office 365 專業增強版、 Office for iOS 和 Android**，] 選項，然後按一下 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="c79b1-173">In the **Use safe links in** section, select the option **Office 365 ProPlus, Office for iOS and Android**, and then click **Save**.</span></span>

4. <span data-ttu-id="c79b1-174">在**原則套用至特定收件者**] 區段中，按一下加號 (**+**)。</span><span class="sxs-lookup"><span data-stu-id="c79b1-174">In the **Policies that apply to specific recipients** section, click the plus sign (**+**).</span></span>

5. <span data-ttu-id="c79b1-175">指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="c79b1-175">Specify the following settings:</span></span>

    - <span data-ttu-id="c79b1-176">在 [**名稱**] 方塊中，輸入名稱，例如： `Safe Links`。</span><span class="sxs-lookup"><span data-stu-id="c79b1-176">In the **Name** box, type a name, such as `Safe Links`.</span></span>

    - <span data-ttu-id="c79b1-177">在 [**選取動作**] 區段中，選擇 [**上**]。</span><span class="sxs-lookup"><span data-stu-id="c79b1-177">In the **Select the action** section, choose **On**.</span></span>

    - <span data-ttu-id="c79b1-178">選取這些選項：</span><span class="sxs-lookup"><span data-stu-id="c79b1-178">Select these options:</span></span>

        - <span data-ttu-id="c79b1-179">**使用安全附件以掃描可下載內容**</span><span class="sxs-lookup"><span data-stu-id="c79b1-179">**Use safe attachments to scan downloadable content**</span></span> 

        - <span data-ttu-id="c79b1-180">**套用至組織內傳送的電子郵件的安全連結**</span><span class="sxs-lookup"><span data-stu-id="c79b1-180">**Apply safe links to email messages sent within the organization**</span></span>

        - <span data-ttu-id="c79b1-181">**不要讓使用者按一下原始 url 的安全連結**</span><span class="sxs-lookup"><span data-stu-id="c79b1-181">**Do not let users click through safe links to original URL**</span></span>

    - <span data-ttu-id="c79b1-182">在 [**套用至**] 區段中，選擇 [**收件者網域是**]。</span><span class="sxs-lookup"><span data-stu-id="c79b1-182">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="c79b1-183">接著，選取您的網域選擇 [**新增**]，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="c79b1-183">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

6. <span data-ttu-id="c79b1-184">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c79b1-184">Click **Save**.</span></span>

<span data-ttu-id="c79b1-185">若要深入了解，請參閱 <<c0>設定 Office 365 ATP 安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="c79b1-185">To learn more, see [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md).</span></span> 

## <a name="part-3---anti-phishing-protection"></a><span data-ttu-id="c79b1-186">組件 3-反網路釣魚保護</span><span class="sxs-lookup"><span data-stu-id="c79b1-186">Part 3 - Anti-phishing protection</span></span>

<span data-ttu-id="c79b1-187">在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)的訂閱中使用[反網路釣魚保護](anti-phishing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="c79b1-187">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span> <span data-ttu-id="c79b1-188">使用[ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)中進階的反網路釣魚保護。</span><span class="sxs-lookup"><span data-stu-id="c79b1-188">Advanced anti-phishing protection is available in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> <span data-ttu-id="c79b1-189">下列程序說明如何設定 ATP 防網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="c79b1-189">The following procedure describes how to configure an ATP anti-phishing policy.</span></span> <span data-ttu-id="c79b1-190">步驟很類似 （不含 ATP) 反網路釣魚原則 」 的設定。</span><span class="sxs-lookup"><span data-stu-id="c79b1-190">The steps are similar for configuring an anti-phishing policy (without ATP).</span></span>

1. <span data-ttu-id="c79b1-191">在 [[安全性 & 合規性中心](https://protection.office.com)中，選擇 [**威脅管理** > **原則** > **ATP 防網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="c79b1-191">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="c79b1-192">按一下 [**預設原則**。</span><span class="sxs-lookup"><span data-stu-id="c79b1-192">Click **Default policy**.</span></span>

3. <span data-ttu-id="c79b1-193">在 [**模擬**] 區段中，按一下 [**編輯**]，然後指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="c79b1-193">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>

    -  <span data-ttu-id="c79b1-194">在 [**新增使用者至保護**索引標籤中，開啟保護。</span><span class="sxs-lookup"><span data-stu-id="c79b1-194">On the **Add users to protect** tab, turn protection on.</span></span> <span data-ttu-id="c79b1-195">然後新增使用者，例如您的組織棋盤成員、 CEO、 CFO，以及其他資深領導人。</span><span class="sxs-lookup"><span data-stu-id="c79b1-195">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="c79b1-196">（您可以輸入個別電子郵件地址，或按一下 [顯示清單。）</span><span class="sxs-lookup"><span data-stu-id="c79b1-196">(You can type an individual email address, or click to display a list.)</span></span>

    - <span data-ttu-id="c79b1-197">[**新增網域，以保護**] 索引標籤中，開啟**自動包含我所擁有的網域**。</span><span class="sxs-lookup"><span data-stu-id="c79b1-197">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="c79b1-198">如果您有自訂網域，以及將它們新增。</span><span class="sxs-lookup"><span data-stu-id="c79b1-198">If you have custom domains, add those as well.</span></span>

    - <span data-ttu-id="c79b1-199">在 [**動作**] 索引標籤上選取 [**將郵件移至 [收件者的垃圾郵件資料夾**都要模擬使用者模擬的網域，並開啟安全提示。</span><span class="sxs-lookup"><span data-stu-id="c79b1-199">On the **Actions** tab, select **Move message to the recipients' Junk Email folders** for both impersonated user and impersonated domain, and turn on safety tips.</span></span>

    - <span data-ttu-id="c79b1-200">在**信箱智慧**] 索引標籤，請確定信箱智慧已開啟。</span><span class="sxs-lookup"><span data-stu-id="c79b1-200">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on.</span></span>

    - <span data-ttu-id="c79b1-201">在 [**檢閱您的設定**] 索引標籤中，檢閱您的設定之後，按一下 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="c79b1-201">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span>

4. <span data-ttu-id="c79b1-202">在 [**詐騙**] 區段中，按一下 [**編輯**]，然後指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="c79b1-202">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>

    - <span data-ttu-id="c79b1-203">**詐騙篩選設定**索引標籤上，確定已開啟反詐騙保護。</span><span class="sxs-lookup"><span data-stu-id="c79b1-203">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>

    - <span data-ttu-id="c79b1-204">在 [**動作**] 索引標籤中，選擇 [將郵件移至 [收件者的垃圾郵件資料夾。</span><span class="sxs-lookup"><span data-stu-id="c79b1-204">On the **Actions** tab, choose Move message to the recipients' Junk Email folders.</span></span>

    - <span data-ttu-id="c79b1-205">在 [**檢閱您的設定**] 索引標籤中，檢閱您的設定之後，按一下 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="c79b1-205">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span> <span data-ttu-id="c79b1-206">(如果您未進行任何變更，按一下 [**取消**。)</span><span class="sxs-lookup"><span data-stu-id="c79b1-206">(If you didn't make any changes, click **Cancel**.)</span></span>

5. <span data-ttu-id="c79b1-207">關閉 [預設原則設定] 頁面。</span><span class="sxs-lookup"><span data-stu-id="c79b1-207">Close the default policy settings page.</span></span>

<span data-ttu-id="c79b1-208">若要深入了解反網路釣魚原則的選項，請參閱[設定反網路釣魚原則](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c79b1-208">To learn more about your anti-phishing policy options, see [Set up anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

## <a name="part-4---anti-spam-protection"></a><span data-ttu-id="c79b1-209">組件 4-反垃圾郵件保護</span><span class="sxs-lookup"><span data-stu-id="c79b1-209">Part 4 - Anti-spam protection</span></span>

<span data-ttu-id="c79b1-210">在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)的訂閱中使用[反垃圾郵件保護](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="c79b1-210">[Anti-spam protection](anti-spam-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="c79b1-211">在 [[安全性 & 合規性中心](https://protection.office.com)中，選擇 [**威脅管理** > **原則** > **反垃圾郵件**。</span><span class="sxs-lookup"><span data-stu-id="c79b1-211">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-spam**.</span></span>

2. <span data-ttu-id="c79b1-212">在 [**自訂**] 索引標籤中，開啟**自訂設定**。</span><span class="sxs-lookup"><span data-stu-id="c79b1-212">On the **Custom** tab, turn **Custom settings** on.</span></span>

3. <span data-ttu-id="c79b1-213">依序展開 [**預設垃圾郵件篩選原則**，按一下 [**編輯原則**]，然後指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="c79b1-213">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>

    - <span data-ttu-id="c79b1-214">在 [**垃圾郵件和大量動作**] 區段中，臨界值設為 5 或 6 的值。</span><span class="sxs-lookup"><span data-stu-id="c79b1-214">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>

    - <span data-ttu-id="c79b1-215">在 [**允許清單**] 區段中，檢閱 （和必要時，編輯） 允許寄件者和網域。</span><span class="sxs-lookup"><span data-stu-id="c79b1-215">In the **Allow lists** section, review (and if necessary, edit) your allowed senders and domains.</span></span>

4. <span data-ttu-id="c79b1-216">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c79b1-216">Click **Save**.</span></span>

<span data-ttu-id="c79b1-217">若要深入了解反垃圾郵件原則的選項，請參閱[設定反垃圾郵件原則](configure-the-anti-spam-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c79b1-217">To learn more about your anti-spam policy options, see [Configure the anti-spam policies](configure-the-anti-spam-policies.md).</span></span>

## <a name="part-5---additional-settings-to-configure"></a><span data-ttu-id="c79b1-218">組件 5-若要設定其他設定</span><span class="sxs-lookup"><span data-stu-id="c79b1-218">Part 5 - Additional settings to configure</span></span>

<span data-ttu-id="c79b1-219">除了設定從惡意程式碼、 惡意 Url 與檔案、 網路釣魚和垃圾郵件保護，我們建議您設定為零時差自動清除及稽核記錄設定。</span><span class="sxs-lookup"><span data-stu-id="c79b1-219">In addition to configuring protection from malware, malicious URLs and files, phishing, and spam, we recommend that you configure your zero-hour auto purge and audit logging settings.</span></span>

### <a name="zero-hour-auto-purge-for-email"></a><span data-ttu-id="c79b1-220">零時差自動清除電子郵件</span><span class="sxs-lookup"><span data-stu-id="c79b1-220">Zero-hour auto purge for email</span></span>

<span data-ttu-id="c79b1-221">[零時差自動清除](zero-hour-auto-purge.md)在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)的訂閱中使用 (ZAP)。</span><span class="sxs-lookup"><span data-stu-id="c79b1-221">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span> <span data-ttu-id="c79b1-222">預設值; 會開啟此保護不過，必須符合下列條件，才會生效的保護：</span><span class="sxs-lookup"><span data-stu-id="c79b1-222">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>

- <span data-ttu-id="c79b1-223">垃圾郵件動作會將**移至垃圾郵件] 資料夾的郵件**設定[反垃圾郵件原則](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="c79b1-223">Spam actions are set to **Move message to Junk Email folder** in [anti-spam policies](anti-spam-protection.md).</span></span>

- <span data-ttu-id="c79b1-224">使用者有保留其預設[垃圾郵件設定](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)，且已不會關閉垃圾郵件保護。</span><span class="sxs-lookup"><span data-stu-id="c79b1-224">Users have kept their default [junk email settings](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md), and have not turned off junk email protection.</span></span>

<span data-ttu-id="c79b1-225">若要深入了解，請參閱[零時差自動清除-防範垃圾郵件和惡意程式碼](zero-hour-auto-purge.md)。</span><span class="sxs-lookup"><span data-stu-id="c79b1-225">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

### <a name="audit-logging-for-reporting-and-investigation"></a><span data-ttu-id="c79b1-226">稽核記錄報告和調查</span><span class="sxs-lookup"><span data-stu-id="c79b1-226">Audit logging for reporting and investigation</span></span>

<span data-ttu-id="c79b1-227">在包含[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description)的訂閱中使用稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="c79b1-227">Audit logging is available in subscriptions that include [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description).</span></span> <span data-ttu-id="c79b1-228">若要檢視的資料在威脅保護報告，例如[安全性儀表板](security-dashboard.md)、[電子郵件安全性報告](view-email-security-reports.md)和 [[檔案總管](use-explorer-in-security-and-compliance.md)] 中，稽核記錄必須開啟為您的組織。</span><span class="sxs-lookup"><span data-stu-id="c79b1-228">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](use-explorer-in-security-and-compliance.md), audit logging must be turned on for your organization.</span></span> <span data-ttu-id="c79b1-229">若要深入了解，請參閱[開啟 Office 365 稽核記錄搜尋的開啟或關閉](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="c79b1-229">To learn more, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>

## <a name="post-setup-tasks"></a><span data-ttu-id="c79b1-230">安裝後期工作</span><span class="sxs-lookup"><span data-stu-id="c79b1-230">Post-setup tasks</span></span>

<span data-ttu-id="c79b1-231">您已設定您的威脅防護功能之後，請務必監視這些功能運作方式、 檢視並修改您的原則，如有需要並監看的新功能和服務更新。</span><span class="sxs-lookup"><span data-stu-id="c79b1-231">After you have configured your threat protection features, make sure to monitor how those features are working, review and revise your policies as needed, and watch for new features and service updates.</span></span>

|<span data-ttu-id="c79b1-232">要執行的動作</span><span class="sxs-lookup"><span data-stu-id="c79b1-232">What to do</span></span>  |<span data-ttu-id="c79b1-233">若要了解更多的資源</span><span class="sxs-lookup"><span data-stu-id="c79b1-233">Resources to learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="c79b1-234">請參閱威脅保護功能如何為您的組織使用中檢視報告</span><span class="sxs-lookup"><span data-stu-id="c79b1-234">See how threat protection features are working for your organization by viewing reports</span></span>    |[<span data-ttu-id="c79b1-235">安全性儀表板</span><span class="sxs-lookup"><span data-stu-id="c79b1-235">Security dashboard</span></span>](security-dashboard.md)<br/>[<span data-ttu-id="c79b1-236">電子郵件安全性報告</span><span class="sxs-lookup"><span data-stu-id="c79b1-236">Email security reports</span></span>](view-email-security-reports.md)<br/>[<span data-ttu-id="c79b1-237">Office 365 atp 報告</span><span class="sxs-lookup"><span data-stu-id="c79b1-237">Reports for Office 365 ATP</span></span>](view-reports-for-atp.md)<br/>[<span data-ttu-id="c79b1-238">威脅總管</span><span class="sxs-lookup"><span data-stu-id="c79b1-238">Threat Explorer</span></span>](use-explorer-in-security-and-compliance.md)    |
|<span data-ttu-id="c79b1-239">定期檢閱及修訂視您威脅保護原則</span><span class="sxs-lookup"><span data-stu-id="c79b1-239">Periodically review and revise your threat protection policies as needed</span></span>    |[<span data-ttu-id="c79b1-240">安全分數</span><span class="sxs-lookup"><span data-stu-id="c79b1-240">Secure Score</span></span>](microsoft-secure-score.md)<br/>[<span data-ttu-id="c79b1-241">智慧型報表和深入解析</span><span class="sxs-lookup"><span data-stu-id="c79b1-241">Smart reports and insights</span></span>](reports-and-insights-in-security-and-compliance.md)<br/>[<span data-ttu-id="c79b1-242">Office 365 威脅調查及回應功能</span><span class="sxs-lookup"><span data-stu-id="c79b1-242">Office 365 threat investigation and response features</span></span>](keep-users-safe-with-office-365-ti.md)          |
|<span data-ttu-id="c79b1-243">監看的新功能和服務更新</span><span class="sxs-lookup"><span data-stu-id="c79b1-243">Watch for new features and service updates</span></span>     |[<span data-ttu-id="c79b1-244">標準和已設定目標發行選項</span><span class="sxs-lookup"><span data-stu-id="c79b1-244">Standard and Targeted release options</span></span>](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide)<br/>[<span data-ttu-id="c79b1-245">訊息中心</span><span class="sxs-lookup"><span data-stu-id="c79b1-245">Message Center</span></span>](https://docs.microsoft.com/office365/admin/manage/message-center?view=o365-worldwide)<br/>[<span data-ttu-id="c79b1-246">Microsoft 365 藍圖</span><span class="sxs-lookup"><span data-stu-id="c79b1-246">Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[<span data-ttu-id="c79b1-247">服務說明</span><span class="sxs-lookup"><span data-stu-id="c79b1-247">Service Descriptions</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)         |


