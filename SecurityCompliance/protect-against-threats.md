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
description: 使用本文做為指南，立即設定您的威脅防護功能。
ms.openlocfilehash: c651c13d5aacf1a7f95a93cacf5030e8ade4b8fd
ms.sourcegitcommit: 895f67531f2b4afe46c7487ca5b44555ca791bae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/12/2019
ms.locfileid: "31836827"
---
# <a name="protect-against-threats-in-office-365"></a><span data-ttu-id="21847-103">防範 Office 365 中的威脅</span><span class="sxs-lookup"><span data-stu-id="21847-103">Protect against threats in Office 365</span></span>

<span data-ttu-id="21847-104">Office 365 包含各種威脅防護功能。</span><span class="sxs-lookup"><span data-stu-id="21847-104">Office 365 includes a variety of threat protection features.</span></span> <span data-ttu-id="21847-105">以下為您的組織設定您可以使用為檢查清單，以確定您威脅保護功能快速入門指南。</span><span class="sxs-lookup"><span data-stu-id="21847-105">Here's a quick-start guide you can use as a checklist to make sure your threat protection features are set up for your organization.</span></span> <span data-ttu-id="21847-106">如果您是初次使用 Office 365 中的威脅保護功能，或您不只是確定要開始，請使用下列指引做為起點。</span><span class="sxs-lookup"><span data-stu-id="21847-106">If you're new to threat protection features in Office 365, or you're just not sure where to begin, use the following guidance as a starting point.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="21847-107">**初始建議的設定包含每種原則; 不過，有許多選項可用，且您可以調整您的設定以符合您特定的組織需求**。</span><span class="sxs-lookup"><span data-stu-id="21847-107">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="21847-108">允許大約 30 分鐘，為您的原則或變更其透過您的資料中心的方式運作。</span><span class="sxs-lookup"><span data-stu-id="21847-108">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="21847-109">必要條件</span><span class="sxs-lookup"><span data-stu-id="21847-109">Prerequisites</span></span>

<span data-ttu-id="21847-110">您必須獲指派適當的角色，才能設定[安全性 & 合規性中心](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)中的原則。</span><span class="sxs-lookup"><span data-stu-id="21847-110">You must be assigned an appropriate role to configure policies in the [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="21847-111">下表包含一些範例：</span><span class="sxs-lookup"><span data-stu-id="21847-111">The following table includes some examples:</span></span> 

|<span data-ttu-id="21847-112">角色或角色群組</span><span class="sxs-lookup"><span data-stu-id="21847-112">Role or role group</span></span>  |<span data-ttu-id="21847-113">若要了解更多的位置</span><span class="sxs-lookup"><span data-stu-id="21847-113">Where to learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="21847-114">Office 365 全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="21847-114">Office 365 Global Administrator</span></span> |[<span data-ttu-id="21847-115">關於 Office 365 系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="21847-115">About Office 365 admin roles</span></span>](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|<span data-ttu-id="21847-116">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="21847-116">Security Administrator</span></span> |[<span data-ttu-id="21847-117">在 Azure Active Directory 系統管理員角色權限</span><span class="sxs-lookup"><span data-stu-id="21847-117">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="21847-118">Exchange Online 組織管理</span><span class="sxs-lookup"><span data-stu-id="21847-118">Exchange Online Organization Management</span></span> |[<span data-ttu-id="21847-119">權限在 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="21847-119">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/en-us/exchange/permissions-exo/permissions-exo) <br><span data-ttu-id="21847-120">與</span><span class="sxs-lookup"><span data-stu-id="21847-120">and</span></span><br> [<span data-ttu-id="21847-121">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="21847-121">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|

<span data-ttu-id="21847-122">若要深入了解，請參閱[中 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="21847-122">To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="part-1---anti-malware"></a><span data-ttu-id="21847-123">1-反惡意程式碼組件</span><span class="sxs-lookup"><span data-stu-id="21847-123">Part 1 - Anti-malware</span></span>

<span data-ttu-id="21847-124">在包含[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) (EOP) 的訂閱中使用反惡意程式碼保護。</span><span class="sxs-lookup"><span data-stu-id="21847-124">Anti-malware protection is available in subscriptions that include [Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) (EOP).</span></span> 

1. <span data-ttu-id="21847-125">在 [[安全性 & 合規性中心](https://protection.office.com)中，選擇 [**威脅管理** > **原則** > **反惡意程式碼**。</span><span class="sxs-lookup"><span data-stu-id="21847-125">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-malware**.</span></span>
2. <span data-ttu-id="21847-126">連按兩下**預設**原則]，然後再選擇 [**設定**。</span><span class="sxs-lookup"><span data-stu-id="21847-126">Double-click the **Default** policy, and then choose **settings**.</span></span>
3. <span data-ttu-id="21847-127">指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="21847-127">Specify the following settings:</span></span>
    - <span data-ttu-id="21847-128">在 [**惡意程式碼偵測回應**] 區段中，保留預設設定 [**否]**。</span><span class="sxs-lookup"><span data-stu-id="21847-128">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>
    - <span data-ttu-id="21847-129">**常見附件類型篩選**] 區段中，選擇 [**上**]。</span><span class="sxs-lookup"><span data-stu-id="21847-129">In the **Common Attachment Types Filter** section, choose **On**.</span></span>
4. <span data-ttu-id="21847-130">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="21847-130">Click **Save**.</span></span>

<span data-ttu-id="21847-131">若要深入了解反惡意程式碼原則選項，請參閱 <<c0>設定反惡意程式碼原則。</span><span class="sxs-lookup"><span data-stu-id="21847-131">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---zero-day-protection"></a><span data-ttu-id="21847-132">組件 2-零時差保護</span><span class="sxs-lookup"><span data-stu-id="21847-132">Part 2 - Zero-day protection</span></span>

<span data-ttu-id="21847-133">零時差保護用於包含[Office 365 進階威脅防護](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)(ATP) 的訂閱，並透過[ATP 安全連結](atp-safe-links.md)和[ATP 安全附件](atp-safe-attachments.md)原則設定。</span><span class="sxs-lookup"><span data-stu-id="21847-133">Zero-day protection is available in subscriptions that include [Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP), and is set up through [ATP Safe Links](atp-safe-links.md) and [ATP Safe Attachments](atp-safe-attachments.md) policies.</span></span>

### <a name="atp-safe-attachments-policies"></a><span data-ttu-id="21847-134">ATP 安全附件原則</span><span class="sxs-lookup"><span data-stu-id="21847-134">ATP Safe Attachments policies</span></span>

1. <span data-ttu-id="21847-135">在 [[安全性 & 合規性中心](https://protection.office.com)中，選擇 [**威脅管理** > **原則** > **ATP 安全附件**。</span><span class="sxs-lookup"><span data-stu-id="21847-135">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP safe attachments**.</span></span>
2. <span data-ttu-id="21847-136">選取 [**開啟 ATP SharePoint、 OneDrive 及 Microsoft Teams**] 選項。</span><span class="sxs-lookup"><span data-stu-id="21847-136">Select the option **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>
3. <span data-ttu-id="21847-137">在 [**保護電子郵件附件**] 區段中，按一下加號 (**+**)。</span><span class="sxs-lookup"><span data-stu-id="21847-137">In the **Protect email attachments** section, click the plus sign (**+**).</span></span>
4. <span data-ttu-id="21847-138">指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="21847-138">Specify the following settings:</span></span>
    - <span data-ttu-id="21847-139">在 [**名稱**] 方塊中，輸入`Block malware`。</span><span class="sxs-lookup"><span data-stu-id="21847-139">In the **Name** box, type `Block malware`.</span></span>
    - <span data-ttu-id="21847-140">在 [回應] 區段中，選擇 [**封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="21847-140">In the response section, choose **Block**.</span></span>
    - <span data-ttu-id="21847-141">在**重新導向附件**] 區段中，選取 [**啟用重新導向**，] 選項，然後指定貴組織的安全性系統管理員或運算子會檢閱者的電子郵件地址偵測到的檔案。</span><span class="sxs-lookup"><span data-stu-id="21847-141">In the **Redirect attachment** section, select the option **Enable redirect**, and then specify the email address for your organization's security administrator or operator who will review detected files.</span></span>
    - <span data-ttu-id="21847-142">在 [**套用至**] 區段中，選擇 [**收件者網域是**]。</span><span class="sxs-lookup"><span data-stu-id="21847-142">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="21847-143">接著，選取您的網域選擇 [**新增**]，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="21847-143">Then, select your domain, choose **Add**, and then click **OK**.</span></span>
5. <span data-ttu-id="21847-144">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="21847-144">Click **Save**.</span></span>
6. <span data-ttu-id="21847-145">（建議使用額外的步驟）以全域系統管理員或 SharePoint Online 管理員執行**[Set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** 指令程式搭配**DisallowInfectedFileDownload**參數設為*true*適用於 Office 365 環境。</span><span class="sxs-lookup"><span data-stu-id="21847-145">(Recommended additional step) As a global administrator or a SharePoint Online administrator run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true* for your Office 365 environment.</span></span> <span data-ttu-id="21847-146">（這可防止人員開啟、 移動、 複製或共用檔案，就會被視為惡意。）</span><span class="sxs-lookup"><span data-stu-id="21847-146">(This prevents people from opening, moving, copying, or sharing files that are detected as malicious.)</span></span>  

<span data-ttu-id="21847-147">若要了解更多，請參閱[設定 Office 365 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)及[開啟 Office 365 ATP SharePoint、 OneDrive 及 Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="21847-147">To learn more, see [Set up Office 365 ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="atp-safe-links-policies"></a><span data-ttu-id="21847-148">ATP 安全連結原則</span><span class="sxs-lookup"><span data-stu-id="21847-148">ATP Safe Links policies</span></span>

<span data-ttu-id="21847-149">若要設定 ATP 安全連結，檢閱您的預設原則，並新增原則。</span><span class="sxs-lookup"><span data-stu-id="21847-149">To set up ATP Safe Links, review your default policy and add a policy.</span></span>

1. <span data-ttu-id="21847-150">在 [[安全性 & 合規性中心](https://protection.office.com)中，選擇 [**威脅管理** > **原則** > **ATP 安全連結**。</span><span class="sxs-lookup"><span data-stu-id="21847-150">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP Safe Links**.</span></span>
2. <span data-ttu-id="21847-151">連按兩下**預設**原則。</span><span class="sxs-lookup"><span data-stu-id="21847-151">Double-click the **Default** policy.</span></span>
3. <span data-ttu-id="21847-152">在**使用中的安全連結**] 區段中，選取 [ **Office 365 專業增強版、 Office for iOS 和 Android**，] 選項，然後按一下 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="21847-152">In the **Use safe links in** section, select the option **Office 365 ProPlus, Office for iOS and Android**, and then click **Save**.</span></span>
4. <span data-ttu-id="21847-153">在**原則套用至特定收件者**] 區段中，按一下加號 (**+**)。</span><span class="sxs-lookup"><span data-stu-id="21847-153">In the **Policies that apply to specific recipients** section, click the plus sign (**+**).</span></span>
5. <span data-ttu-id="21847-154">指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="21847-154">Specify the following settings:</span></span>
    - <span data-ttu-id="21847-155">在 [**名稱**] 方塊中，輸入名稱，例如： `Safe Links`。</span><span class="sxs-lookup"><span data-stu-id="21847-155">In the **Name** box, type a name, such as `Safe Links`.</span></span>
    - <span data-ttu-id="21847-156">在 [**選取動作**] 區段中，選擇 [**上**]。</span><span class="sxs-lookup"><span data-stu-id="21847-156">In the **Select the action** section, choose **On**.</span></span>
    - <span data-ttu-id="21847-157">選取這些選項：</span><span class="sxs-lookup"><span data-stu-id="21847-157">Select these options:</span></span>
        - <span data-ttu-id="21847-158">**使用安全附件以掃描可下載內容**</span><span class="sxs-lookup"><span data-stu-id="21847-158">**Use safe attachments to scan downloadable content**</span></span> 
        - <span data-ttu-id="21847-159">**套用至組織內傳送的電子郵件的安全連結**</span><span class="sxs-lookup"><span data-stu-id="21847-159">**Apply safe links to email messages sent within the organization**</span></span>
        - <span data-ttu-id="21847-160">**不要讓使用者按一下原始 url 的安全連結**</span><span class="sxs-lookup"><span data-stu-id="21847-160">**Do not let users click through safe links to original URL**</span></span>
    - <span data-ttu-id="21847-161">在 [**套用至**] 區段中，選擇 [**收件者網域是**]。</span><span class="sxs-lookup"><span data-stu-id="21847-161">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="21847-162">接著，選取您的網域選擇 [**新增**]，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="21847-162">Then, select your domain, choose **Add**, and then click **OK**.</span></span>
6. <span data-ttu-id="21847-163">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="21847-163">Click **Save**.</span></span>

<span data-ttu-id="21847-164">若要深入了解，請參閱 <<c0>設定 Office 365 ATP 安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="21847-164">To learn more, see [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md).</span></span> 

## <a name="part-3---anti-phishing"></a><span data-ttu-id="21847-165">第 3-反網路釣魚部分</span><span class="sxs-lookup"><span data-stu-id="21847-165">Part 3 - Anti-phishing</span></span> 

<span data-ttu-id="21847-166">在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)的訂閱中使用反網路釣魚保護。</span><span class="sxs-lookup"><span data-stu-id="21847-166">Anti-phishing protection is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span> <span data-ttu-id="21847-167">使用[ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)中進階的反網路釣魚保護。</span><span class="sxs-lookup"><span data-stu-id="21847-167">Advanced anti-phishing protection is available in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> <span data-ttu-id="21847-168">下列程序說明如何設定 ATP 防網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="21847-168">The following procedure describes how to configure an ATP anti-phishing policy.</span></span> <span data-ttu-id="21847-169">步驟很類似 （不含 ATP) 反網路釣魚原則 」 的設定。</span><span class="sxs-lookup"><span data-stu-id="21847-169">The steps are similar for configuring an anti-phishing policy (without ATP).</span></span>

1. <span data-ttu-id="21847-170">在 [[安全性 & 合規性中心](https://protection.office.com)中，選擇 [**威脅管理** > **原則** > **ATP 防網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="21847-170">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP anti-phishing**.</span></span>
2. <span data-ttu-id="21847-171">按一下 [**預設原則**。</span><span class="sxs-lookup"><span data-stu-id="21847-171">Click **Default policy**.</span></span>
3. <span data-ttu-id="21847-172">在 [**模擬**] 區段中，按一下 [**編輯**]，然後指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="21847-172">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>
    -  <span data-ttu-id="21847-173">在 [**新增使用者至保護**索引標籤中，開啟保護。</span><span class="sxs-lookup"><span data-stu-id="21847-173">On the **Add users to protect** tab, turn protection on.</span></span> <span data-ttu-id="21847-174">然後新增使用者，例如您的組織棋盤成員、 CEO、 CFO，以及其他資深領導人。</span><span class="sxs-lookup"><span data-stu-id="21847-174">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="21847-175">（您可以輸入個別電子郵件地址，或按一下 [顯示清單。）</span><span class="sxs-lookup"><span data-stu-id="21847-175">(You can type an individual email address, or click to display a list.)</span></span>
    - <span data-ttu-id="21847-176">[**新增網域，以保護**] 索引標籤中，開啟**自動包含我所擁有的網域**。</span><span class="sxs-lookup"><span data-stu-id="21847-176">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="21847-177">如果您有自訂網域，以及將它們新增。</span><span class="sxs-lookup"><span data-stu-id="21847-177">If you have custom domains, add those as well.</span></span>
    - <span data-ttu-id="21847-178">在 [**動作**] 索引標籤上選取 [**將郵件移至 [收件者的垃圾郵件資料夾**都要模擬使用者模擬的網域，並開啟安全提示。</span><span class="sxs-lookup"><span data-stu-id="21847-178">On the **Actions** tab, select **Move message to the recipients' Junk Email folders** for both impersonated user and impersonated domain, and turn on safety tips.</span></span>
    - <span data-ttu-id="21847-179">在**信箱智慧**] 索引標籤，請確定信箱智慧已開啟。</span><span class="sxs-lookup"><span data-stu-id="21847-179">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on.</span></span>
    - <span data-ttu-id="21847-180">在 [**檢閱您的設定**] 索引標籤中，檢閱您的設定之後，按一下 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="21847-180">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span>
4. <span data-ttu-id="21847-181">在 [**詐騙**] 區段中，按一下 [**編輯**]，然後指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="21847-181">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>
    - <span data-ttu-id="21847-182">**詐騙篩選設定**索引標籤上，確定已開啟反詐騙保護。</span><span class="sxs-lookup"><span data-stu-id="21847-182">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>
    - <span data-ttu-id="21847-183">在 [**動作**] 索引標籤中，選擇 [將郵件移至 [收件者的垃圾郵件資料夾。</span><span class="sxs-lookup"><span data-stu-id="21847-183">On the **Actions** tab, choose Move message to the recipients' Junk Email folders.</span></span>
    - <span data-ttu-id="21847-184">在 [**檢閱您的設定**] 索引標籤中，檢閱您的設定之後，按一下 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="21847-184">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span> <span data-ttu-id="21847-185">(如果您未進行任何變更，按一下 [**取消**。)</span><span class="sxs-lookup"><span data-stu-id="21847-185">(If you didn't make any changes, click **Cancel**.)</span></span>
5. <span data-ttu-id="21847-186">關閉 [預設原則設定] 頁面。</span><span class="sxs-lookup"><span data-stu-id="21847-186">Close the default policy settings page.</span></span>

<span data-ttu-id="21847-187">若要深入了解反網路釣魚原則的選項，請參閱[Office 365 ATP 防網路釣魚和防網路釣魚原則設定](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="21847-187">To learn more about your anti-phishing policy options, see [Set up Office 365 ATP anti-phishing and anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

## <a name="part-4---anti-spam"></a><span data-ttu-id="21847-188">組件 4-反垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="21847-188">Part 4 - Anti-spam</span></span>

<span data-ttu-id="21847-189">在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)的訂閱中使用反垃圾郵件保護。</span><span class="sxs-lookup"><span data-stu-id="21847-189">Anti-spam protection is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="21847-190">在 [[安全性 & 合規性中心](https://protection.office.com)中，選擇 [**威脅管理** > **原則** > **反垃圾郵件**。</span><span class="sxs-lookup"><span data-stu-id="21847-190">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-spam**.</span></span>
2. <span data-ttu-id="21847-191">在 [**自訂**] 索引標籤中，開啟**自訂設定**。</span><span class="sxs-lookup"><span data-stu-id="21847-191">On the **Custom** tab, turn **Custom settings** on.</span></span>
3. <span data-ttu-id="21847-192">依序展開 [**預設垃圾郵件篩選原則**，按一下 [**編輯原則**]，然後指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="21847-192">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>
    - <span data-ttu-id="21847-193">在 [**垃圾郵件和大量動作**] 區段中，臨界值設為 5 或 6 的值。</span><span class="sxs-lookup"><span data-stu-id="21847-193">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>
    - <span data-ttu-id="21847-194">在 [**允許清單**] 區段中，檢閱 （和必要時，編輯） 允許寄件者和網域。</span><span class="sxs-lookup"><span data-stu-id="21847-194">In the **Allow lists** section, review (and if necessary, edit) your allowed senders and domains.</span></span>
4. <span data-ttu-id="21847-195">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="21847-195">Click **Save**.</span></span>

<span data-ttu-id="21847-196">若要深入了解反垃圾郵件原則的選項，請參閱[設定反垃圾郵件原則](configure-the-anti-spam-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="21847-196">To learn more about your anti-spam policy options, see [Configure the anti-spam policies](configure-the-anti-spam-policies.md).</span></span>

## <a name="part-5---service-wide-settings"></a><span data-ttu-id="21847-197">組件 5-全服務設定</span><span class="sxs-lookup"><span data-stu-id="21847-197">Part 5 - Service-wide settings</span></span>

### <a name="zero-hour-auto-purge"></a><span data-ttu-id="21847-198">零時差自動清除</span><span class="sxs-lookup"><span data-stu-id="21847-198">Zero-hour auto purge</span></span>

<span data-ttu-id="21847-199">在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)的訂閱中使用零時差自動清除 (ZAP)。</span><span class="sxs-lookup"><span data-stu-id="21847-199">Zero-hour auto purge (ZAP) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span> <span data-ttu-id="21847-200">預設值; 會開啟此保護不過，必須符合下列條件，才會生效的保護：</span><span class="sxs-lookup"><span data-stu-id="21847-200">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>
- <span data-ttu-id="21847-201">垃圾郵件動作會將**移至垃圾郵件] 資料夾的郵件**設定反垃圾郵件原則。</span><span class="sxs-lookup"><span data-stu-id="21847-201">Spam actions are set to **Move message to Junk Email folder** in anti-spam policies.</span></span>
- <span data-ttu-id="21847-202">使用者有保留其預設的垃圾郵件設定，且已不會關閉垃圾郵件保護。</span><span class="sxs-lookup"><span data-stu-id="21847-202">Users have kept their default junk email settings, and have not turned off junk email protection.</span></span>

<span data-ttu-id="21847-203">若要深入了解，請參閱[零時差自動清除-防範垃圾郵件和惡意程式碼](zero-hour-auto-purge.md)。</span><span class="sxs-lookup"><span data-stu-id="21847-203">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

### <a name="audit-logging"></a><span data-ttu-id="21847-204">稽核記錄</span><span class="sxs-lookup"><span data-stu-id="21847-204">Audit logging</span></span>

<span data-ttu-id="21847-205">在包含[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description)的訂閱中使用稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="21847-205">Audit logging is available in subscriptions that include [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description).</span></span> <span data-ttu-id="21847-206">若要檢視的資料在威脅保護報告，例如[安全性儀表板](security-dashboard.md)、[電子郵件安全性報告](view-email-security-reports.md)和 [[檔案總管](use-explorer-in-security-and-compliance.md)] 中，稽核記錄必須開啟為您的組織。</span><span class="sxs-lookup"><span data-stu-id="21847-206">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](use-explorer-in-security-and-compliance.md), audit logging must be turned on for your organization.</span></span> <span data-ttu-id="21847-207">若要深入了解，請參閱[開啟 Office 365 稽核記錄搜尋的開啟或關閉](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="21847-207">To learn more, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>

## <a name="post-setup-tasks"></a><span data-ttu-id="21847-208">安裝後期工作</span><span class="sxs-lookup"><span data-stu-id="21847-208">Post-setup tasks</span></span>

### <a name="watch-for-new-features-and-service-updates"></a><span data-ttu-id="21847-209">監看的新功能和服務更新</span><span class="sxs-lookup"><span data-stu-id="21847-209">Watch for new features and service updates</span></span>

- [<span data-ttu-id="21847-210">請造訪 Microsoft 365 藍圖</span><span class="sxs-lookup"><span data-stu-id="21847-210">Visit the Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)

- [<span data-ttu-id="21847-211">請參閱 Office 365 進階的威脅防護服務說明</span><span class="sxs-lookup"><span data-stu-id="21847-211">See the Office 365 Advanced Threat Protection Service Description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)

### <a name="see-how-atp-is-working-for-your-organization"></a><span data-ttu-id="21847-212">請參閱 ATP 為您的組織的運作方式</span><span class="sxs-lookup"><span data-stu-id="21847-212">See how ATP is working for your organization</span></span>

- [<span data-ttu-id="21847-213">檢視 Office 365 進階威脅防護報告</span><span class="sxs-lookup"><span data-stu-id="21847-213">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

- [<span data-ttu-id="21847-214">使用檔案總管中的安全性&amp;合規性中心</span><span class="sxs-lookup"><span data-stu-id="21847-214">Use Explorer in the Security &amp; Compliance Center</span></span>](use-explorer-in-security-and-compliance.md)

### <a name="periodically-review-and-revise-your-atp-policies"></a><span data-ttu-id="21847-215">定期檢閱並修改您的 ATP 原則</span><span class="sxs-lookup"><span data-stu-id="21847-215">Periodically review and revise your ATP policies</span></span>

- [<span data-ttu-id="21847-216">保護您的 Office 365 使用者安全與 Office 365 威脅調查及回應</span><span class="sxs-lookup"><span data-stu-id="21847-216">Keep your Office 365 users safe with Office 365 threat investigation and response</span></span>](keep-users-safe-with-office-365-ti.md) 

- [<span data-ttu-id="21847-217">使用 Office 365 安全性中的智慧型報表和深入解析&amp;合規性中心</span><span class="sxs-lookup"><span data-stu-id="21847-217">Use the smart reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md) 