---
title: 快速入門： 設定 Office 365 進階威脅防護
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/19/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: 以下是您可以使用以確保 Office 365 進階威脅防護 (ATP) 會安裝並設定您組織快速入門指南。
ms.openlocfilehash: a071c626327aa7d0055df522e8fec5ebe41d6a83
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2019
ms.locfileid: "30999396"
---
# <a name="quick-start-guide-set-up-office-365-advanced-threat-protection"></a><span data-ttu-id="0da33-103">快速入門指南：設定 Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="0da33-103">Quick Start Guide: Set up Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="0da33-104">以下是您可以使用一份清單，請確定 Office 365 進階威脅防護 (ATP)，會為您的組織設定好快速入門指南。</span><span class="sxs-lookup"><span data-stu-id="0da33-104">Here's a quick-start guide you can use as a checklist to make sure Office 365 Advanced Threat Protection (ATP) is set up for your organization.</span></span> <span data-ttu-id="0da33-105">如果您是初次使用 Office 365 中的威脅防護，或您不只是確定要開始，請使用下列指引做為起點。</span><span class="sxs-lookup"><span data-stu-id="0da33-105">If you're new to threat protection in Office 365, or you're just not sure where to begin, use the following guidance as a starting point.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="0da33-106">**初始建議的設定包含每種原則; 不過，有許多選項可用，且您可以調整您的設定以符合您特定的組織需求**。</span><span class="sxs-lookup"><span data-stu-id="0da33-106">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="0da33-107">允許大約 30 分鐘，為您的原則或變更其透過您的資料中心的方式運作。</span><span class="sxs-lookup"><span data-stu-id="0da33-107">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0da33-108">必要條件</span><span class="sxs-lookup"><span data-stu-id="0da33-108">Prerequisites</span></span>

- <span data-ttu-id="0da33-109">您的組織必須包含[Office 365 進階威脅防護](office-365-atp.md)(ATP) 訂閱。</span><span class="sxs-lookup"><span data-stu-id="0da33-109">Your organization must have a subscription that includes [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP).</span></span>

- <span data-ttu-id="0da33-110">您必須獲指派適當的角色，才能存取 ATP 功能。</span><span class="sxs-lookup"><span data-stu-id="0da33-110">You must be assigned an appropriate role to access ATP features.</span></span> <span data-ttu-id="0da33-111">下表包含一些範例：</span><span class="sxs-lookup"><span data-stu-id="0da33-111">The following table includes some examples:</span></span> 

    |<span data-ttu-id="0da33-112">角色或角色群組</span><span class="sxs-lookup"><span data-stu-id="0da33-112">Role or role group</span></span>  |<span data-ttu-id="0da33-113">若要了解更多的位置</span><span class="sxs-lookup"><span data-stu-id="0da33-113">Where to learn more</span></span>  |
    |---------|---------|
    |<span data-ttu-id="0da33-114">Office 365 全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="0da33-114">Office 365 Global Administrator</span></span> |[<span data-ttu-id="0da33-115">關於 Office 365 系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="0da33-115">About Office 365 admin roles</span></span>](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
    |<span data-ttu-id="0da33-116">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="0da33-116">Security Administrator</span></span> |[<span data-ttu-id="0da33-117">在 Azure Active Directory 系統管理員角色權限</span><span class="sxs-lookup"><span data-stu-id="0da33-117">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
    |<span data-ttu-id="0da33-118">Exchange Online 組織管理</span><span class="sxs-lookup"><span data-stu-id="0da33-118">Exchange Online Organization Management</span></span> |[<span data-ttu-id="0da33-119">權限在 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0da33-119">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/en-us/exchange/permissions-exo/permissions-exo) <br><span data-ttu-id="0da33-120">與</span><span class="sxs-lookup"><span data-stu-id="0da33-120">and</span></span><br> [<span data-ttu-id="0da33-121">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="0da33-121">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|

    <span data-ttu-id="0da33-122">(請參閱[中的 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。)</span><span class="sxs-lookup"><span data-stu-id="0da33-122">(See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).)</span></span>

## <a name="part-1---anti-malware"></a><span data-ttu-id="0da33-123">1-反惡意程式碼組件</span><span class="sxs-lookup"><span data-stu-id="0da33-123">Part 1 - Anti-malware</span></span>

1. <span data-ttu-id="0da33-124">在 [[安全性 & 合規性中心](https://protection.office.com)中，選擇 [**威脅管理** > **原則** > **反惡意程式碼**。</span><span class="sxs-lookup"><span data-stu-id="0da33-124">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-malware**.</span></span>
2. <span data-ttu-id="0da33-125">連按兩下**預設**原則]，然後再選擇 [**設定**。</span><span class="sxs-lookup"><span data-stu-id="0da33-125">Double-click the **Default** policy, and then choose **settings**.</span></span>
3. <span data-ttu-id="0da33-126">指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="0da33-126">Specify the following settings:</span></span>
    - <span data-ttu-id="0da33-127">在 [**惡意程式碼偵測回應**] 區段中，保留預設設定 [**否]**。</span><span class="sxs-lookup"><span data-stu-id="0da33-127">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>
    - <span data-ttu-id="0da33-128">**常見附件類型篩選**] 區段中，選擇 [**上**]。</span><span class="sxs-lookup"><span data-stu-id="0da33-128">In the **Common Attachment Types Filter** section, choose **On**.</span></span>
4. <span data-ttu-id="0da33-129">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0da33-129">Click **Save**.</span></span>

<span data-ttu-id="0da33-130">若要深入了解反惡意程式碼原則選項，請參閱 <<c0>設定反惡意程式碼原則。</span><span class="sxs-lookup"><span data-stu-id="0da33-130">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---zero-day-protection"></a><span data-ttu-id="0da33-131">組件 2-零時差保護</span><span class="sxs-lookup"><span data-stu-id="0da33-131">Part 2 - Zero-day protection</span></span>

<span data-ttu-id="0da33-132">零時差保護是透過原則，例如 ATP 安全連結和安全附件原則設定。</span><span class="sxs-lookup"><span data-stu-id="0da33-132">Zero-day protection is set up through policies, such as ATP Safe Links and Safe Attachments policies.</span></span>

### <a name="atp-safe-attachments-policies"></a><span data-ttu-id="0da33-133">ATP 安全附件原則</span><span class="sxs-lookup"><span data-stu-id="0da33-133">ATP Safe Attachments policies</span></span>

1. <span data-ttu-id="0da33-134">在 [[安全性 & 合規性中心](https://protection.office.com)中，選擇 [**威脅管理** > **原則** > **ATP 安全附件**。</span><span class="sxs-lookup"><span data-stu-id="0da33-134">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP safe attachments**.</span></span>
2. <span data-ttu-id="0da33-135">選取 [**開啟 ATP SharePoint、 OneDrive 及 Microsoft Teams**] 選項。</span><span class="sxs-lookup"><span data-stu-id="0da33-135">Select the option **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>
3. <span data-ttu-id="0da33-136">在 [**保護電子郵件附件**] 區段中，按一下加號 (**+**)。</span><span class="sxs-lookup"><span data-stu-id="0da33-136">In the **Protect email attachments** section, click the plus sign (**+**).</span></span>
4. <span data-ttu-id="0da33-137">指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="0da33-137">Specify the following settings:</span></span>
    - <span data-ttu-id="0da33-138">在 [**名稱**] 方塊中，輸入`Block malware`。</span><span class="sxs-lookup"><span data-stu-id="0da33-138">In the **Name** box, type `Block malware`.</span></span>
    - <span data-ttu-id="0da33-139">在 [回應] 區段中，選擇 [**封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="0da33-139">In the response section, choose **Block**.</span></span>
    - <span data-ttu-id="0da33-140">在**重新導向附件**] 區段中，選取 [**啟用重新導向**，] 選項，然後指定貴組織的安全性系統管理員或運算子會檢閱者的電子郵件地址偵測到的檔案。</span><span class="sxs-lookup"><span data-stu-id="0da33-140">In the **Redirect attachment** section, select the option **Enable redirect**, and then specify the email address for your organization's security administrator or operator who will review detected files.</span></span>
    - <span data-ttu-id="0da33-141">在 [**套用至**] 區段中，選擇 [**收件者網域是**]。</span><span class="sxs-lookup"><span data-stu-id="0da33-141">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="0da33-142">接著，選取您的網域選擇 [**新增**]，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="0da33-142">Then, select your domain, choose **Add**, and then click **OK**.</span></span>
5. <span data-ttu-id="0da33-143">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0da33-143">Click **Save**.</span></span>
6. <span data-ttu-id="0da33-144">（建議使用額外的步驟）以全域系統管理員或 SharePoint Online 管理員執行**[Set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** 指令程式搭配**DisallowInfectedFileDownload**參數設為*true*適用於 Office 365 環境。</span><span class="sxs-lookup"><span data-stu-id="0da33-144">(Recommended additional step) As a global administrator or a SharePoint Online administrator run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true* for your Office 365 environment.</span></span> <span data-ttu-id="0da33-145">（這可防止人員開啟、 移動、 複製或共用檔案，就會被視為惡意。）</span><span class="sxs-lookup"><span data-stu-id="0da33-145">(This prevents people from opening, moving, copying, or sharing files that are detected as malicious.)</span></span>  

<span data-ttu-id="0da33-146">若要了解更多，請參閱[設定 Office 365 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)及[開啟 Office 365 ATP SharePoint、 OneDrive 及 Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="0da33-146">To learn more, see [Set up Office 365 ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="atp-safe-links-policies"></a><span data-ttu-id="0da33-147">ATP 安全連結原則</span><span class="sxs-lookup"><span data-stu-id="0da33-147">ATP Safe Links policies</span></span>

<span data-ttu-id="0da33-148">若要設定 ATP 安全連結，檢閱您的預設原則，並新增原則。</span><span class="sxs-lookup"><span data-stu-id="0da33-148">To set up ATP Safe Links, review your default policy and add a policy.</span></span>

1. <span data-ttu-id="0da33-149">在 [[安全性 & 合規性中心](https://protection.office.com)中，選擇 [**威脅管理** > **原則** > **ATP 安全連結**。</span><span class="sxs-lookup"><span data-stu-id="0da33-149">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP Safe Links**.</span></span>
2. <span data-ttu-id="0da33-150">連按兩下**預設**原則。</span><span class="sxs-lookup"><span data-stu-id="0da33-150">Double-click the **Default** policy.</span></span>
3. <span data-ttu-id="0da33-151">在**使用中的安全連結**] 區段中，選取 [ **Office 365 專業增強版、 Office for iOS 和 Android**，] 選項，然後按一下 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="0da33-151">In the **Use safe links in** section, select the option **Office 365 ProPlus, Office for iOS and Android**, and then click **Save**.</span></span>
4. <span data-ttu-id="0da33-152">在**原則套用至特定收件者**] 區段中，按一下加號 (**+**)。</span><span class="sxs-lookup"><span data-stu-id="0da33-152">In the **Policies that apply to specific recipients** section, click the plus sign (**+**).</span></span>
5. <span data-ttu-id="0da33-153">指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="0da33-153">Specify the following settings:</span></span>
    - <span data-ttu-id="0da33-154">在 [**名稱**] 方塊中，輸入名稱，例如： `Safe Links`。</span><span class="sxs-lookup"><span data-stu-id="0da33-154">In the **Name** box, type a name, such as `Safe Links`.</span></span>
    - <span data-ttu-id="0da33-155">在 [**選取動作**] 區段中，選擇 [**上**]。</span><span class="sxs-lookup"><span data-stu-id="0da33-155">In the **Select the action** section, choose **On**.</span></span>
    - <span data-ttu-id="0da33-156">選取這些選項：</span><span class="sxs-lookup"><span data-stu-id="0da33-156">Select these options:</span></span>
        - <span data-ttu-id="0da33-157">**使用安全附件以掃描可下載內容**</span><span class="sxs-lookup"><span data-stu-id="0da33-157">**Use safe attachments to scan downloadable content**</span></span> 
        - <span data-ttu-id="0da33-158">**套用至組織內傳送的電子郵件的安全連結**</span><span class="sxs-lookup"><span data-stu-id="0da33-158">**Apply safe links to email messages sent within the organization**</span></span>
        - <span data-ttu-id="0da33-159">**不要讓使用者按一下原始 url 的安全連結**</span><span class="sxs-lookup"><span data-stu-id="0da33-159">**Do not let users click through safe links to original URL**</span></span>
    - <span data-ttu-id="0da33-160">在 [**套用至**] 區段中，選擇 [**收件者網域是**]。</span><span class="sxs-lookup"><span data-stu-id="0da33-160">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="0da33-161">接著，選取您的網域選擇 [**新增**]，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="0da33-161">Then, select your domain, choose **Add**, and then click **OK**.</span></span>
6. <span data-ttu-id="0da33-162">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0da33-162">Click **Save**.</span></span>

<span data-ttu-id="0da33-163">若要深入了解，請參閱 <<c0>設定 Office 365 ATP 安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="0da33-163">To learn more, see [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md).</span></span> 

## <a name="part-3---anti-phishing"></a><span data-ttu-id="0da33-164">第 3-反網路釣魚部分</span><span class="sxs-lookup"><span data-stu-id="0da33-164">Part 3 - Anti-phishing</span></span> 

1. <span data-ttu-id="0da33-165">在 [[安全性 & 合規性中心](https://protection.office.com)中，選擇 [**威脅管理** > **原則** > **ATP 防網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="0da33-165">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP anti-phishing**.</span></span>
2. <span data-ttu-id="0da33-166">按一下 [**預設原則**。</span><span class="sxs-lookup"><span data-stu-id="0da33-166">Click **Default policy**.</span></span>
3. <span data-ttu-id="0da33-167">在 [**模擬**] 區段中，按一下 [**編輯**]，然後指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="0da33-167">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>
    -  <span data-ttu-id="0da33-168">在 [**新增使用者至保護**索引標籤中，開啟保護。</span><span class="sxs-lookup"><span data-stu-id="0da33-168">On the **Add users to protect** tab, turn protection on.</span></span> <span data-ttu-id="0da33-169">然後新增使用者，例如您的組織棋盤成員、 CEO、 CFO，以及其他資深領導人。</span><span class="sxs-lookup"><span data-stu-id="0da33-169">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="0da33-170">（您可以輸入個別電子郵件地址，或按一下 [顯示清單。）</span><span class="sxs-lookup"><span data-stu-id="0da33-170">(You can type an individual email address, or click to display a list.)</span></span>
    - <span data-ttu-id="0da33-171">[**新增網域，以保護**] 索引標籤中，開啟**自動包含我所擁有的網域**。</span><span class="sxs-lookup"><span data-stu-id="0da33-171">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="0da33-172">如果您有自訂網域，以及將它們新增。</span><span class="sxs-lookup"><span data-stu-id="0da33-172">If you have custom domains, add those as well.</span></span>
    - <span data-ttu-id="0da33-173">在 [**動作**] 索引標籤上選取 [**將郵件移至 [收件者的垃圾郵件資料夾**都要模擬使用者模擬的網域，並開啟安全提示。</span><span class="sxs-lookup"><span data-stu-id="0da33-173">On the **Actions** tab, select **Move message to the recipients' Junk Email folders** for both impersonated user and impersonated domain, and turn on safety tips.</span></span>
    - <span data-ttu-id="0da33-174">在**信箱智慧**] 索引標籤，請確定信箱智慧已開啟。</span><span class="sxs-lookup"><span data-stu-id="0da33-174">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on.</span></span>
    - <span data-ttu-id="0da33-175">在 [**檢閱您的設定**] 索引標籤中，檢閱您的設定之後，按一下 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="0da33-175">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span>
4. <span data-ttu-id="0da33-176">在 [**詐騙**] 區段中，按一下 [**編輯**]，然後指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="0da33-176">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>
    - <span data-ttu-id="0da33-177">**詐騙篩選設定**索引標籤上，確定已開啟反詐騙保護。</span><span class="sxs-lookup"><span data-stu-id="0da33-177">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>
    - <span data-ttu-id="0da33-178">在 [**動作**] 索引標籤中，選擇 [將郵件移至 [收件者的垃圾郵件資料夾。</span><span class="sxs-lookup"><span data-stu-id="0da33-178">On the **Actions** tab, choose Move message to the recipients' Junk Email folders.</span></span>
    - <span data-ttu-id="0da33-179">在 [**檢閱您的設定**] 索引標籤中，檢閱您的設定之後，按一下 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="0da33-179">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span> <span data-ttu-id="0da33-180">(如果您未進行任何變更，按一下 [**取消**。)</span><span class="sxs-lookup"><span data-stu-id="0da33-180">(If you didn't make any changes, click **Cancel**.)</span></span>
5. <span data-ttu-id="0da33-181">關閉 [預設原則設定] 頁面。</span><span class="sxs-lookup"><span data-stu-id="0da33-181">Close the default policy settings page.</span></span>

<span data-ttu-id="0da33-182">若要深入了解反網路釣魚原則的選項，請參閱[Office 365 ATP 防網路釣魚和防網路釣魚原則設定](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="0da33-182">To learn more about your anti-phishing policy options, see [Set up Office 365 ATP anti-phishing and anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

## <a name="part-4---anti-spam"></a><span data-ttu-id="0da33-183">組件 4-反垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="0da33-183">Part 4 - Anti-spam</span></span>

1. <span data-ttu-id="0da33-184">在 [[安全性 & 合規性中心](https://protection.office.com)中，選擇 [**威脅管理** > **原則** > **反垃圾郵件**。</span><span class="sxs-lookup"><span data-stu-id="0da33-184">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-spam**.</span></span>
2. <span data-ttu-id="0da33-185">在 [**自訂**] 索引標籤中，開啟**自訂設定**。</span><span class="sxs-lookup"><span data-stu-id="0da33-185">On the **Custom** tab, turn **Custom settings** on.</span></span>
3. <span data-ttu-id="0da33-186">依序展開 [**預設垃圾郵件篩選原則**，按一下 [**編輯原則**]，然後指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="0da33-186">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>
    - <span data-ttu-id="0da33-187">在 [**垃圾郵件和大量動作**] 區段中，臨界值設為 5 或 6 的值。</span><span class="sxs-lookup"><span data-stu-id="0da33-187">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>
    - <span data-ttu-id="0da33-188">在 [**允許清單**] 區段中，檢閱 （和必要時，編輯） 允許寄件者和網域。</span><span class="sxs-lookup"><span data-stu-id="0da33-188">In the **Allow lists** section, review (and if necessary, edit) your allowed senders and domains.</span></span>
4. <span data-ttu-id="0da33-189">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0da33-189">Click **Save**.</span></span>

<span data-ttu-id="0da33-190">若要深入了解反垃圾郵件原則的選項，請參閱[設定反垃圾郵件原則](configure-the-anti-spam-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="0da33-190">To learn more about your anti-spam policy options, see [Configure the anti-spam policies](configure-the-anti-spam-policies.md).</span></span>

## <a name="part-5---service-wide-settings"></a><span data-ttu-id="0da33-191">組件 5-全服務設定</span><span class="sxs-lookup"><span data-stu-id="0da33-191">Part 5 - Service-wide settings</span></span>

### <a name="zero-hour-auto-purge"></a><span data-ttu-id="0da33-192">零時差自動清除</span><span class="sxs-lookup"><span data-stu-id="0da33-192">Zero-hour auto purge</span></span>

<span data-ttu-id="0da33-193">零時差自動清除 (ZAP) 開啟預設;不過，必須符合下列條件：</span><span class="sxs-lookup"><span data-stu-id="0da33-193">Zero-hour auto purge (ZAP) is turned on by default; however, the following conditions must be met:</span></span>
- <span data-ttu-id="0da33-194">垃圾郵件動作會將**移至垃圾郵件] 資料夾的郵件**設定反垃圾郵件原則。</span><span class="sxs-lookup"><span data-stu-id="0da33-194">Spam actions are set to **Move message to Junk Email folder** in anti-spam policies.</span></span>
- <span data-ttu-id="0da33-195">使用者有保留其預設的垃圾郵件設定，且已不會關閉垃圾郵件保護。</span><span class="sxs-lookup"><span data-stu-id="0da33-195">Users have kept their default junk email settings, and have not turned off junk email protection.</span></span>

<span data-ttu-id="0da33-196">若要深入了解，請參閱[零時差自動清除-防範垃圾郵件和惡意程式碼](zero-hour-auto-purge.md)。</span><span class="sxs-lookup"><span data-stu-id="0da33-196">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

### <a name="audit-logging"></a><span data-ttu-id="0da33-197">稽核記錄</span><span class="sxs-lookup"><span data-stu-id="0da33-197">Audit logging</span></span>

<span data-ttu-id="0da33-198">若要檢視的資料在威脅保護報告，例如[安全性儀表板](security-dashboard.md)與[檔案總管](use-explorer-in-security-and-compliance.md)] 中，稽核記錄必須開啟為您的組織。</span><span class="sxs-lookup"><span data-stu-id="0da33-198">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md) and [Explorer](use-explorer-in-security-and-compliance.md), audit logging must be turned on for your organization.</span></span>

<span data-ttu-id="0da33-199">請參閱[開啟 Office 365 稽核記錄搜尋的開啟或關閉](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="0da33-199">See [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>

## <a name="post-setup-tasks"></a><span data-ttu-id="0da33-200">安裝後期工作</span><span class="sxs-lookup"><span data-stu-id="0da33-200">Post-setup tasks</span></span>

### <a name="watch-for-new-features-and-service-updates"></a><span data-ttu-id="0da33-201">監看的新功能和服務更新</span><span class="sxs-lookup"><span data-stu-id="0da33-201">Watch for new features and service updates</span></span>

- [<span data-ttu-id="0da33-202">請造訪 Microsoft 365 藍圖</span><span class="sxs-lookup"><span data-stu-id="0da33-202">Visit the Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)

- [<span data-ttu-id="0da33-203">請參閱 Office 365 進階的威脅防護服務說明</span><span class="sxs-lookup"><span data-stu-id="0da33-203">See the Office 365 Advanced Threat Protection Service Description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)

### <a name="see-how-atp-is-working-for-your-organization"></a><span data-ttu-id="0da33-204">請參閱 ATP 為您的組織的運作方式</span><span class="sxs-lookup"><span data-stu-id="0da33-204">See how ATP is working for your organization</span></span>

- [<span data-ttu-id="0da33-205">檢視 Office 365 進階威脅防護報告</span><span class="sxs-lookup"><span data-stu-id="0da33-205">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

- [<span data-ttu-id="0da33-206">使用檔案總管中的安全性&amp;合規性中心</span><span class="sxs-lookup"><span data-stu-id="0da33-206">Use Explorer in the Security &amp; Compliance Center</span></span>](use-explorer-in-security-and-compliance.md)

### <a name="periodically-review-and-revise-your-atp-policies"></a><span data-ttu-id="0da33-207">定期檢閱並修改您的 ATP 原則</span><span class="sxs-lookup"><span data-stu-id="0da33-207">Periodically review and revise your ATP policies</span></span>

- [<span data-ttu-id="0da33-208">保護您的 Office 365 使用者安全與 Office 365 威脅調查及回應</span><span class="sxs-lookup"><span data-stu-id="0da33-208">Keep your Office 365 users safe with Office 365 threat investigation and response</span></span>](keep-users-safe-with-office-365-ti.md) 

- [<span data-ttu-id="0da33-209">使用 Office 365 安全性中的智慧型報表和深入解析&amp;合規性中心</span><span class="sxs-lookup"><span data-stu-id="0da33-209">Use the smart reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md) 