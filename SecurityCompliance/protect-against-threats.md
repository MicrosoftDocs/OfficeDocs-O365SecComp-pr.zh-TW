---
title: 防止 Office 365 中的威脅
ms.author: tracyp
author: msfttracyp
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 05/09/2019
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: 請立即使用本文做為設定威脅防護功能的指南。
ms.openlocfilehash: 6700e2714ea607f675b487204404d53c1d51db93
ms.sourcegitcommit: 424a614141c1f19a1c84a67ec2d71dd3d7ef6694
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/30/2019
ms.locfileid: "34590576"
---
# <a name="protect-against-threats-in-office-365"></a><span data-ttu-id="0b830-103">防止 Office 365 中的威脅</span><span class="sxs-lookup"><span data-stu-id="0b830-103">Protect against threats in Office 365</span></span>

<span data-ttu-id="0b830-104">Office 365 包含各種威脅防護功能。</span><span class="sxs-lookup"><span data-stu-id="0b830-104">Office 365 includes a variety of threat protection features.</span></span> <span data-ttu-id="0b830-105">以下是快速入門手冊, 您可以用來做為檢查清單, 以確保您的組織已設定威脅防護功能。</span><span class="sxs-lookup"><span data-stu-id="0b830-105">Here's a quick-start guide you can use as a checklist to make sure your threat protection features are set up for your organization.</span></span> <span data-ttu-id="0b830-106">如果您是 Office 365 中威脅防護功能的新功能, 或您不確定要開始的位置, 請使用下列指引做為起點。</span><span class="sxs-lookup"><span data-stu-id="0b830-106">If you're new to threat protection features in Office 365, or you're just not sure where to begin, use the following guidance as a starting point.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="0b830-107">**每種原則都包含初始建議設定, 不過, 有許多選項可供使用, 而且您可以調整您的設定以符合特定組織的需求**。</span><span class="sxs-lookup"><span data-stu-id="0b830-107">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="0b830-108">針對您的原則, 允許大約30分鐘, 或變更以透過您的資料中心來運作。</span><span class="sxs-lookup"><span data-stu-id="0b830-108">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="requirements"></a><span data-ttu-id="0b830-109">需求</span><span class="sxs-lookup"><span data-stu-id="0b830-109">Requirements</span></span>

### <a name="subscriptions"></a><span data-ttu-id="0b830-110">訂閱</span><span class="sxs-lookup"><span data-stu-id="0b830-110">Subscriptions</span></span>

<span data-ttu-id="0b830-111">威脅防護功能包含在所有的 Office 365 訂閱中。不過, 有些訂閱包含更多的高級功能。</span><span class="sxs-lookup"><span data-stu-id="0b830-111">Threat protection features are included in all Office 365 subscriptions; however, some subscriptions include more advanced features.</span></span> <span data-ttu-id="0b830-112">下表列出本文隨附的保護功能, 以及最基本的訂閱需求。</span><span class="sxs-lookup"><span data-stu-id="0b830-112">The following table lists the protection features included in this article together with the minimum subscription requirements.</span></span><br/>

|<span data-ttu-id="0b830-113">保護類型</span><span class="sxs-lookup"><span data-stu-id="0b830-113">Protection type</span></span>  |<span data-ttu-id="0b830-114">訂閱需求</span><span class="sxs-lookup"><span data-stu-id="0b830-114">Subscription requirement</span></span>  |
|---------|---------|
|<span data-ttu-id="0b830-115">反惡意程式碼保護</span><span class="sxs-lookup"><span data-stu-id="0b830-115">Anti-malware protection</span></span>    | <span data-ttu-id="0b830-116">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)EOP</span><span class="sxs-lookup"><span data-stu-id="0b830-116">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) (EOP)</span></span>        |
|<span data-ttu-id="0b830-117">保護電子郵件和 Office 檔中的惡意 Url 和檔案</span><span class="sxs-lookup"><span data-stu-id="0b830-117">Protection from malicious URLs and files in email and Office documents</span></span>    | <span data-ttu-id="0b830-118">[Office 365 高級威脅防護](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)ATP</span><span class="sxs-lookup"><span data-stu-id="0b830-118">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP)</span></span>       |
|<span data-ttu-id="0b830-119">反網路釣魚保護</span><span class="sxs-lookup"><span data-stu-id="0b830-119">Anti-phishing protection</span></span>    | [<span data-ttu-id="0b830-120">EOP</span><span class="sxs-lookup"><span data-stu-id="0b830-120">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)      |
|<span data-ttu-id="0b830-121">高級反網路釣魚保護</span><span class="sxs-lookup"><span data-stu-id="0b830-121">Advanced anti-phishing protection</span></span>    | [<span data-ttu-id="0b830-122">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="0b830-122">Office 365 ATP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)   |
|<span data-ttu-id="0b830-123">反垃圾郵件保護</span><span class="sxs-lookup"><span data-stu-id="0b830-123">Anti-spam protection</span></span>     | [<span data-ttu-id="0b830-124">EOP</span><span class="sxs-lookup"><span data-stu-id="0b830-124">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)       |
|<span data-ttu-id="0b830-125">零小時自動清除 (電子郵件)</span><span class="sxs-lookup"><span data-stu-id="0b830-125">Zero-hour auto purge (for email)</span></span>    | [<span data-ttu-id="0b830-126">EOP</span><span class="sxs-lookup"><span data-stu-id="0b830-126">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)        |
|<span data-ttu-id="0b830-127">審核記錄 (這是用於報告目的)</span><span class="sxs-lookup"><span data-stu-id="0b830-127">Audit logging (this is used for reporting purposes)</span></span>    | [<span data-ttu-id="0b830-128">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0b830-128">Exchange Online</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description)        |

### <a name="roles-and-permissions"></a><span data-ttu-id="0b830-129">角色及權限</span><span class="sxs-lookup"><span data-stu-id="0b830-129">Roles and permissions</span></span>

<span data-ttu-id="0b830-130">您必須獲指派適當的角色, 才能設定[安全性 & 規範中心](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)中的原則。</span><span class="sxs-lookup"><span data-stu-id="0b830-130">You must be assigned an appropriate role to configure policies in the [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="0b830-131">下表包含一些範例:</span><span class="sxs-lookup"><span data-stu-id="0b830-131">The following table includes some examples:</span></span> 

|<span data-ttu-id="0b830-132">角色或角色群組</span><span class="sxs-lookup"><span data-stu-id="0b830-132">Role or role group</span></span>  |<span data-ttu-id="0b830-133">深入瞭解</span><span class="sxs-lookup"><span data-stu-id="0b830-133">Where to learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="0b830-134">Office 365 全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="0b830-134">Office 365 Global Administrator</span></span> |[<span data-ttu-id="0b830-135">關於 Office 365 系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="0b830-135">About Office 365 admin roles</span></span>](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|<span data-ttu-id="0b830-136">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="0b830-136">Security Administrator</span></span> |[<span data-ttu-id="0b830-137">Azure Active Directory 中的系統管理員角色許可權</span><span class="sxs-lookup"><span data-stu-id="0b830-137">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="0b830-138">Exchange Online 組織管理</span><span class="sxs-lookup"><span data-stu-id="0b830-138">Exchange Online Organization Management</span></span> |[<span data-ttu-id="0b830-139">Exchange Online 中的許可權</span><span class="sxs-lookup"><span data-stu-id="0b830-139">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/en-us/exchange/permissions-exo/permissions-exo) <br><span data-ttu-id="0b830-140">與</span><span class="sxs-lookup"><span data-stu-id="0b830-140">and</span></span><br> [<span data-ttu-id="0b830-141">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="0b830-141">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|

<span data-ttu-id="0b830-142">若要深入瞭解, 請參閱[Office 365 安全性&amp;與合規性中心的許可權](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="0b830-142">To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="part-1---anti-malware-protection"></a><span data-ttu-id="0b830-143">第1部分-反惡意程式碼保護</span><span class="sxs-lookup"><span data-stu-id="0b830-143">Part 1 - Anti-malware protection</span></span>

<span data-ttu-id="0b830-144">您可以在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)的訂閱中使用[反惡意程式碼保護](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="0b830-144">[Anti-malware protection](anti-malware-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span> 

1. <span data-ttu-id="0b830-145">在 [[安全性 & 規範中心](https://protection.office.com)] 中, 選擇 [**威脅管理** > **原則** > **反惡意**代碼]。</span><span class="sxs-lookup"><span data-stu-id="0b830-145">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-malware**.</span></span>

2. <span data-ttu-id="0b830-146">按兩下**預設**原則, 然後選擇 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="0b830-146">Double-click the **Default** policy, and then choose **settings**.</span></span>

3. <span data-ttu-id="0b830-147">指定下列設定:</span><span class="sxs-lookup"><span data-stu-id="0b830-147">Specify the following settings:</span></span>

    - <span data-ttu-id="0b830-148">在 [**惡意程式碼偵測回應**] 區段中, 保留預設設定 [**否**]。</span><span class="sxs-lookup"><span data-stu-id="0b830-148">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>

    - <span data-ttu-id="0b830-149">在 [**通用附件類型篩選**] 區段中, 選擇 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="0b830-149">In the **Common Attachment Types Filter** section, choose **On**.</span></span>

4. <span data-ttu-id="0b830-150">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0b830-150">Click **Save**.</span></span>

<span data-ttu-id="0b830-151">若要深入瞭解反惡意程式碼原則選項, 請參閱[設定反惡意程式碼原則](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="0b830-151">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---protection-from-malicious-urls-and-files"></a><span data-ttu-id="0b830-152">第2部分-防護惡意 Url 和檔案</span><span class="sxs-lookup"><span data-stu-id="0b830-152">Part 2 - Protection from malicious URLs and files</span></span>

<span data-ttu-id="0b830-153">在包含[Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP) 的訂閱中, 可以使用 [從惡意 url 和檔案進行防護], 並透過[atp 安全附件](atp-safe-attachments.md)和[atp 安全連結](atp-safe-links.md)原則設定。</span><span class="sxs-lookup"><span data-stu-id="0b830-153">Time-of-click protection from malicious URLs and files is available in subscriptions that include [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP), and is set up through [ATP Safe Attachments](atp-safe-attachments.md) and [ATP Safe Links](atp-safe-links.md) policies.</span></span>

### <a name="atp-safe-attachments-policies"></a><span data-ttu-id="0b830-154">ATP 安全附件原則</span><span class="sxs-lookup"><span data-stu-id="0b830-154">ATP Safe Attachments policies</span></span>

<span data-ttu-id="0b830-155">若要設定[Atp 安全附件](atp-safe-attachments.md), 您必須至少定義一個 ATP 安全附件原則。</span><span class="sxs-lookup"><span data-stu-id="0b830-155">To set up [ATP Safe Attachments](atp-safe-attachments.md), you must define at least one ATP Safe Attachments policy.</span></span> 

1. <span data-ttu-id="0b830-156">在 [[安全性 & 規範中心](https://protection.office.com)] 中, 選擇 [**威脅管理** > **原則** > **ATP 安全附件**]。</span><span class="sxs-lookup"><span data-stu-id="0b830-156">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP safe attachments**.</span></span>

2. <span data-ttu-id="0b830-157">選取 [**開啟 SharePoint、OneDrive 及 Microsoft 團隊的 ATP**] 選項。</span><span class="sxs-lookup"><span data-stu-id="0b830-157">Select the option **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

3. <span data-ttu-id="0b830-158">在 [**保護電子郵件附件**] 區段中, 按一下加號**+**()。</span><span class="sxs-lookup"><span data-stu-id="0b830-158">In the **Protect email attachments** section, click the plus sign (**+**).</span></span>

4. <span data-ttu-id="0b830-159">指定下列設定:</span><span class="sxs-lookup"><span data-stu-id="0b830-159">Specify the following settings:</span></span>

    - <span data-ttu-id="0b830-160">在 [**名稱**] 方塊中`Block malware`, 輸入。</span><span class="sxs-lookup"><span data-stu-id="0b830-160">In the **Name** box, type `Block malware`.</span></span>

    - <span data-ttu-id="0b830-161">在 [回應] 區段中, 選擇 [**區塊**]。</span><span class="sxs-lookup"><span data-stu-id="0b830-161">In the response section, choose **Block**.</span></span>

    - <span data-ttu-id="0b830-162">在 [重新**導向附件**] 區段中, 選取 [**啟用重新導向**] 選項, 然後指定組織的安全性系統管理員或操作員的電子郵件地址, 以查看偵測到的檔案。</span><span class="sxs-lookup"><span data-stu-id="0b830-162">In the **Redirect attachment** section, select the option **Enable redirect**, and then specify the email address for your organization's security administrator or operator who will review detected files.</span></span>

    - <span data-ttu-id="0b830-163">在 [套用**至**] 區段中, 選擇 [**收件**者] 網域。</span><span class="sxs-lookup"><span data-stu-id="0b830-163">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="0b830-164">然後, 選取您的網域, 選擇 [**新增**], 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="0b830-164">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

5. <span data-ttu-id="0b830-165">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0b830-165">Click **Save**.</span></span>

6. <span data-ttu-id="0b830-166">(**建議的其他步驟**)在全域系統管理員或 SharePoint Online 系統管理員對您的 Office 365 環境執行**[set-spotenant 指令程式](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)**, 並將**DisallowInfectedFileDownload**參數設為*true* 。</span><span class="sxs-lookup"><span data-stu-id="0b830-166">(**Recommended additional step**) As a global administrator or a SharePoint Online administrator run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true* for your Office 365 environment.</span></span> <span data-ttu-id="0b830-167">(這可防止使用者開啟、移動、複製或共用偵測到惡意的檔案)。</span><span class="sxs-lookup"><span data-stu-id="0b830-167">(This prevents people from opening, moving, copying, or sharing files that are detected as malicious.)</span></span>  

<span data-ttu-id="0b830-168">若要深入瞭解, 請參閱[設定 office 365 Atp 安全附件原則](set-up-atp-safe-attachments-policies.md)和[開啟 office 365 atp For SharePoint、OneDrive 及 Microsoft 團隊](turn-on-atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="0b830-168">To learn more, see [Set up Office 365 ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="atp-safe-links-policies"></a><span data-ttu-id="0b830-169">ATP 安全連結原則</span><span class="sxs-lookup"><span data-stu-id="0b830-169">ATP Safe Links policies</span></span>

<span data-ttu-id="0b830-170">若要設定[ATP 安全連結](atp-safe-links.md), 請查看和編輯您的預設原則, 並新增特定使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="0b830-170">To set up [ATP Safe Links](atp-safe-links.md), review and edit your default policy, and add a policy for specific users.</span></span>

1. <span data-ttu-id="0b830-171">在 [[安全性 & 規範中心](https://protection.office.com)] 中, 選擇 [**威脅管理** > **原則** > **ATP 安全連結**]。</span><span class="sxs-lookup"><span data-stu-id="0b830-171">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP Safe Links**.</span></span>

2. <span data-ttu-id="0b830-172">按兩下**預設**原則。</span><span class="sxs-lookup"><span data-stu-id="0b830-172">Double-click the **Default** policy.</span></span>

3. <span data-ttu-id="0b830-173">在 [**使用安全連結**] 區段中, 選取 [ **office 365 專業增強版]、[office for iOS] 和 [Android**] 選項, 然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="0b830-173">In the **Use safe links in** section, select the option **Office 365 ProPlus, Office for iOS and Android**, and then click **Save**.</span></span>

4. <span data-ttu-id="0b830-174">在 [套用**至特定**收件者的原則] 區段中, 按一下**+** 加號 ()。</span><span class="sxs-lookup"><span data-stu-id="0b830-174">In the **Policies that apply to specific recipients** section, click the plus sign (**+**).</span></span>

5. <span data-ttu-id="0b830-175">指定下列設定:</span><span class="sxs-lookup"><span data-stu-id="0b830-175">Specify the following settings:</span></span>

    - <span data-ttu-id="0b830-176">在 [**名稱**] 方塊中, 輸入名稱, 例如`Safe Links`。</span><span class="sxs-lookup"><span data-stu-id="0b830-176">In the **Name** box, type a name, such as `Safe Links`.</span></span>

    - <span data-ttu-id="0b830-177">在 [**選取動作**] 區段中, 選擇 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="0b830-177">In the **Select the action** section, choose **On**.</span></span>

    - <span data-ttu-id="0b830-178">選取下列選項:</span><span class="sxs-lookup"><span data-stu-id="0b830-178">Select these options:</span></span>

        - <span data-ttu-id="0b830-179">**使用安全附件掃描可下載的內容**</span><span class="sxs-lookup"><span data-stu-id="0b830-179">**Use safe attachments to scan downloadable content**</span></span> 

        - <span data-ttu-id="0b830-180">**將安全連結套用至組織內傳送的電子郵件**</span><span class="sxs-lookup"><span data-stu-id="0b830-180">**Apply safe links to email messages sent within the organization**</span></span>

        - <span data-ttu-id="0b830-181">**不要讓使用者點擊至原始 URL 的安全連結**</span><span class="sxs-lookup"><span data-stu-id="0b830-181">**Do not let users click through safe links to original URL**</span></span>

    - <span data-ttu-id="0b830-182">在 [套用**至**] 區段中, 選擇 [**收件**者] 網域。</span><span class="sxs-lookup"><span data-stu-id="0b830-182">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="0b830-183">然後, 選取您的網域, 選擇 [**新增**], 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="0b830-183">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

6. <span data-ttu-id="0b830-184">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0b830-184">Click **Save**.</span></span>

<span data-ttu-id="0b830-185">若要深入瞭解, 請參閱[設定 Office 365 ATP 安全連結原則](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="0b830-185">To learn more, see [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md).</span></span> 

## <a name="part-3---anti-phishing-protection"></a><span data-ttu-id="0b830-186">第3部分-反網路釣魚保護</span><span class="sxs-lookup"><span data-stu-id="0b830-186">Part 3 - Anti-phishing protection</span></span>

<span data-ttu-id="0b830-187">您可以在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)的訂閱中使用[反網路釣魚保護](anti-phishing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="0b830-187">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span> <span data-ttu-id="0b830-188">您可以在[ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)中使用高級的反網路釣魚防護。</span><span class="sxs-lookup"><span data-stu-id="0b830-188">Advanced anti-phishing protection is available in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> <span data-ttu-id="0b830-189">下列程式說明如何設定 ATP 反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="0b830-189">The following procedure describes how to configure an ATP anti-phishing policy.</span></span> <span data-ttu-id="0b830-190">設定反網路釣魚原則 (不含 ATP) 的步驟類似。</span><span class="sxs-lookup"><span data-stu-id="0b830-190">The steps are similar for configuring an anti-phishing policy (without ATP).</span></span>

1. <span data-ttu-id="0b830-191">在 [[安全性 & 規範中心](https://protection.office.com)] 中, 選擇 [**威脅管理** > **原則** > **ATP 反網路釣魚**]。</span><span class="sxs-lookup"><span data-stu-id="0b830-191">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0b830-192">按一下 [**預設原則**]。</span><span class="sxs-lookup"><span data-stu-id="0b830-192">Click **Default policy**.</span></span>

3. <span data-ttu-id="0b830-193">在 [ \*\*\*\* 模擬] 區段中, 按一下 [**編輯**], 然後指定下列設定:</span><span class="sxs-lookup"><span data-stu-id="0b830-193">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>

    - <span data-ttu-id="0b830-194">在 [**新增要保護的使用者**] 索引標籤上開啟 [保護]。</span><span class="sxs-lookup"><span data-stu-id="0b830-194">On the **Add users to protect** tab, turn protection on.</span></span> <span data-ttu-id="0b830-195">然後新增使用者, 例如您組織的董事會成員、CEO、CFO 和其他資深負責人。</span><span class="sxs-lookup"><span data-stu-id="0b830-195">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="0b830-196">(您可以輸入個別的電子郵件地址, 或按一下以顯示清單)。</span><span class="sxs-lookup"><span data-stu-id="0b830-196">(You can type an individual email address, or click to display a list.)</span></span>

    - <span data-ttu-id="0b830-197">在 [**新增要保護的網域**] 索引標籤上, 開啟 [**自動包含我擁有的網域**]。</span><span class="sxs-lookup"><span data-stu-id="0b830-197">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="0b830-198">如果您有自訂網域, 也請新增這些網域。</span><span class="sxs-lookup"><span data-stu-id="0b830-198">If you have custom domains, add those as well.</span></span>

    - <span data-ttu-id="0b830-199">在 [**動作**] 索引標籤上, 選取 [**將郵件移至收件者的垃圾郵件資料夾**中的模擬的使用者和模擬的網域], 然後開啟 [安全提示]。</span><span class="sxs-lookup"><span data-stu-id="0b830-199">On the **Actions** tab, select **Move message to the recipients' Junk Email folders** for both impersonated user and impersonated domain, and turn on safety tips.</span></span>

    - <span data-ttu-id="0b830-200">在 [**信箱智慧**] 索引標籤上, 確定已開啟 [信箱智慧]。</span><span class="sxs-lookup"><span data-stu-id="0b830-200">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on.</span></span>

    - <span data-ttu-id="0b830-201">在 [**檢查您的設定**] 索引標籤上, 檢查您的設定後, 按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="0b830-201">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span>

4. <span data-ttu-id="0b830-202">在 [**哄騙**] 區段中, 按一下 [**編輯**], 然後指定下列設定:</span><span class="sxs-lookup"><span data-stu-id="0b830-202">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>

    - <span data-ttu-id="0b830-203">在 [**哄騙篩選器設定**] 索引標籤上, 確定已開啟反欺詐保護。</span><span class="sxs-lookup"><span data-stu-id="0b830-203">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>

    - <span data-ttu-id="0b830-204">在 [**動作**] 索引標籤上, 選擇 [將郵件移至收件者的垃圾郵件資料夾]。</span><span class="sxs-lookup"><span data-stu-id="0b830-204">On the **Actions** tab, choose Move message to the recipients' Junk Email folders.</span></span>

    - <span data-ttu-id="0b830-205">在 [**檢查您的設定**] 索引標籤上, 檢查您的設定後, 按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="0b830-205">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span> <span data-ttu-id="0b830-206">(如果您沒有進行任何變更, 請按一下 [**取消**]。)</span><span class="sxs-lookup"><span data-stu-id="0b830-206">(If you didn't make any changes, click **Cancel**.)</span></span>

5. <span data-ttu-id="0b830-207">關閉 [預設原則設定] 頁面。</span><span class="sxs-lookup"><span data-stu-id="0b830-207">Close the default policy settings page.</span></span>

<span data-ttu-id="0b830-208">若要深入瞭解您的反網路釣魚原則選項, 請參閱[設定反網路釣魚原則](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="0b830-208">To learn more about your anti-phishing policy options, see [Set up anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

## <a name="part-4---anti-spam-protection"></a><span data-ttu-id="0b830-209">第4部分-反垃圾郵件保護</span><span class="sxs-lookup"><span data-stu-id="0b830-209">Part 4 - Anti-spam protection</span></span>

<span data-ttu-id="0b830-210">您可以在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)的訂閱中使用[反垃圾郵件保護](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="0b830-210">[Anti-spam protection](anti-spam-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="0b830-211">在 [[安全性 & 規範中心](https://protection.office.com)] 中, 選擇 [**威脅管理** > **原則** > **反垃圾郵件**]。</span><span class="sxs-lookup"><span data-stu-id="0b830-211">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-spam**.</span></span>

2. <span data-ttu-id="0b830-212">在 [**自訂**] 索引標籤上開啟**自訂設定**。</span><span class="sxs-lookup"><span data-stu-id="0b830-212">On the **Custom** tab, turn **Custom settings** on.</span></span>

3. <span data-ttu-id="0b830-213">展開 [**預設垃圾郵件篩選原則**], 按一下 [**編輯原則**], 然後指定下列設定:</span><span class="sxs-lookup"><span data-stu-id="0b830-213">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>

    - <span data-ttu-id="0b830-214">在 [**垃圾郵件和大量動作**] 區段中, 將臨界值設為5或6。</span><span class="sxs-lookup"><span data-stu-id="0b830-214">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>

    - <span data-ttu-id="0b830-215">在 [**允許清單**] 區段中, 複查 (並在必要時編輯) 您允許的寄件者和網域。</span><span class="sxs-lookup"><span data-stu-id="0b830-215">In the **Allow lists** section, review (and if necessary, edit) your allowed senders and domains.</span></span>

4. <span data-ttu-id="0b830-216">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0b830-216">Click **Save**.</span></span>

<span data-ttu-id="0b830-217">若要深入瞭解您的反垃圾郵件原則選項, 請參閱[設定反垃圾郵件原則](configure-the-anti-spam-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="0b830-217">To learn more about your anti-spam policy options, see [Configure the anti-spam policies](configure-the-anti-spam-policies.md).</span></span>

## <a name="part-5---additional-settings-to-configure"></a><span data-ttu-id="0b830-218">第5部分-要設定的其他設定</span><span class="sxs-lookup"><span data-stu-id="0b830-218">Part 5 - Additional settings to configure</span></span>

<span data-ttu-id="0b830-219">除了設定惡意程式碼、惡意 Url 和檔案、網路釣魚和垃圾郵件的防護之外, 建議您設定零時自動清除和審核記錄設定。</span><span class="sxs-lookup"><span data-stu-id="0b830-219">In addition to configuring protection from malware, malicious URLs and files, phishing, and spam, we recommend that you configure your zero-hour auto purge and audit logging settings.</span></span>

### <a name="zero-hour-auto-purge-for-email"></a><span data-ttu-id="0b830-220">電子郵件的零時自動清除</span><span class="sxs-lookup"><span data-stu-id="0b830-220">Zero-hour auto purge for email</span></span>

<span data-ttu-id="0b830-221">[零小時自動清除](zero-hour-auto-purge.md)(ZAP) 可在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)的訂閱中使用。</span><span class="sxs-lookup"><span data-stu-id="0b830-221">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span> <span data-ttu-id="0b830-222">此保護預設為開啟。不過, 若要使保護生效, 必須符合下列條件:</span><span class="sxs-lookup"><span data-stu-id="0b830-222">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>

- <span data-ttu-id="0b830-223">在[反垃圾郵件原則](anti-spam-protection.md)中, 垃圾郵件動作會設定為**將郵件移至垃圾郵件資料夾**。</span><span class="sxs-lookup"><span data-stu-id="0b830-223">Spam actions are set to **Move message to Junk Email folder** in [anti-spam policies](anti-spam-protection.md).</span></span>

- <span data-ttu-id="0b830-224">使用者保留其預設的[垃圾郵件設定](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md), 且未關閉垃圾郵件保護。</span><span class="sxs-lookup"><span data-stu-id="0b830-224">Users have kept their default [junk email settings](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md), and have not turned off junk email protection.</span></span>

<span data-ttu-id="0b830-225">若要深入瞭解, 請參閱[零時自動清除防護垃圾郵件和惡意](zero-hour-auto-purge.md)代碼。</span><span class="sxs-lookup"><span data-stu-id="0b830-225">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

### <a name="audit-logging-for-reporting-and-investigation"></a><span data-ttu-id="0b830-226">報告和調查的審核記錄</span><span class="sxs-lookup"><span data-stu-id="0b830-226">Audit logging for reporting and investigation</span></span>

<span data-ttu-id="0b830-227">您可以在包含[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description)的訂閱中取得審核記錄。</span><span class="sxs-lookup"><span data-stu-id="0b830-227">Audit logging is available in subscriptions that include [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description).</span></span> <span data-ttu-id="0b830-228">若要在威脅防護報告中查看資料, 例如[安全性儀表板](security-dashboard.md)、[電子郵件安全性報告](view-email-security-reports.md)和[Explorer](use-explorer-in-security-and-compliance.md), 您的組織必須開啟審核記錄。</span><span class="sxs-lookup"><span data-stu-id="0b830-228">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](use-explorer-in-security-and-compliance.md), audit logging must be turned on for your organization.</span></span> <span data-ttu-id="0b830-229">若要深入瞭解, 請參閱[開啟或關閉 Office 365 audit log search](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="0b830-229">To learn more, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>

## <a name="post-setup-tasks"></a><span data-ttu-id="0b830-230">安裝後的工作</span><span class="sxs-lookup"><span data-stu-id="0b830-230">Post-setup tasks</span></span>

<span data-ttu-id="0b830-231">設定威脅防護功能之後, 請務必監視這些功能的運作方式、視需要查看和修訂原則, 以及查看新功能和服務更新。</span><span class="sxs-lookup"><span data-stu-id="0b830-231">After you have configured your threat protection features, make sure to monitor how those features are working, review and revise your policies as needed, and watch for new features and service updates.</span></span>

|<span data-ttu-id="0b830-232">待辦事項</span><span class="sxs-lookup"><span data-stu-id="0b830-232">What to do</span></span>  |<span data-ttu-id="0b830-233">要深入瞭解的資源</span><span class="sxs-lookup"><span data-stu-id="0b830-233">Resources to learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="0b830-234">透過查看報告, 查看您組織的威脅防護功能的運作方式</span><span class="sxs-lookup"><span data-stu-id="0b830-234">See how threat protection features are working for your organization by viewing reports</span></span>    |[<span data-ttu-id="0b830-235">安全性儀表板</span><span class="sxs-lookup"><span data-stu-id="0b830-235">Security dashboard</span></span>](security-dashboard.md)<br/>[<span data-ttu-id="0b830-236">電子郵件安全性報告</span><span class="sxs-lookup"><span data-stu-id="0b830-236">Email security reports</span></span>](view-email-security-reports.md)<br/>[<span data-ttu-id="0b830-237">Office 365 ATP 的報告</span><span class="sxs-lookup"><span data-stu-id="0b830-237">Reports for Office 365 ATP</span></span>](view-reports-for-atp.md)<br/>[<span data-ttu-id="0b830-238">威脅總管</span><span class="sxs-lookup"><span data-stu-id="0b830-238">Threat Explorer</span></span>](use-explorer-in-security-and-compliance.md)    |
|<span data-ttu-id="0b830-239">視需要定期檢查和修訂威脅防護原則</span><span class="sxs-lookup"><span data-stu-id="0b830-239">Periodically review and revise your threat protection policies as needed</span></span>    |[<span data-ttu-id="0b830-240">安全分數</span><span class="sxs-lookup"><span data-stu-id="0b830-240">Secure Score</span></span>](microsoft-secure-score.md)<br/>[<span data-ttu-id="0b830-241">智慧報表和深入資訊</span><span class="sxs-lookup"><span data-stu-id="0b830-241">Smart reports and insights</span></span>](reports-and-insights-in-security-and-compliance.md)<br/>[<span data-ttu-id="0b830-242">Office 365 威脅調查和回應功能</span><span class="sxs-lookup"><span data-stu-id="0b830-242">Office 365 threat investigation and response features</span></span>](keep-users-safe-with-office-365-ti.md)          |
|<span data-ttu-id="0b830-243">監視新功能和服務更新</span><span class="sxs-lookup"><span data-stu-id="0b830-243">Watch for new features and service updates</span></span>     |[<span data-ttu-id="0b830-244">標準和目標發行選項</span><span class="sxs-lookup"><span data-stu-id="0b830-244">Standard and Targeted release options</span></span>](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide)<br/>[<span data-ttu-id="0b830-245">訊息中心</span><span class="sxs-lookup"><span data-stu-id="0b830-245">Message Center</span></span>](https://docs.microsoft.com/office365/admin/manage/message-center?view=o365-worldwide)<br/>[<span data-ttu-id="0b830-246">Microsoft 365 藍圖</span><span class="sxs-lookup"><span data-stu-id="0b830-246">Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[<span data-ttu-id="0b830-247">服務說明</span><span class="sxs-lookup"><span data-stu-id="0b830-247">Service Descriptions</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)         |
