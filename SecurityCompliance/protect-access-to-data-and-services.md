---
title: 保護使用者和裝置存取權
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/17/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: 保護 O365 資料與服務存取權的登陸頁面
ms.openlocfilehash: e1b529a641d25f82521c40d0df9d091e0ebb5d90
ms.sourcegitcommit: e23b84ef4eee9cccec7205826b71ddfe9aaac2f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/28/2019
ms.locfileid: "33403001"
---
# <a name="protect-user-and-device-access"></a><span data-ttu-id="25224-103">保護使用者和裝置存取權</span><span class="sxs-lookup"><span data-stu-id="25224-103">Protect user and device access</span></span>

<span data-ttu-id="25224-104">保護您的 Office 365 資料與服務存取權是防禦網路攻擊與防止資料遺失而言很重要的。</span><span class="sxs-lookup"><span data-stu-id="25224-104">Protecting access to your Office 365 data and services is crucial to defending against cyber-attacks and guarding against data loss.</span></span> <span data-ttu-id="25224-105">同一種保護方式可套用至環境中的其他 SaaS 應用程式，甚至可在內部應用程式發佈與 Azure Active Directory 應用程式 Proxy。</span><span class="sxs-lookup"><span data-stu-id="25224-105">The same protections can be applied to other SaaS applications in your environment and even to on-premises applications published with Azure Active Directory Application Proxy.</span></span>
  
## <a name="step-1-review-recommendations"></a><span data-ttu-id="25224-106">步驟 1： 檢閱建議</span><span class="sxs-lookup"><span data-stu-id="25224-106">Step 1: Review recommendations</span></span>

<span data-ttu-id="25224-107">推薦可用於保護身分識別和裝置的功能，其可存取 Office 365、其他 SaaS 服務，以及與 Azure AD 應用程式 Proxy 一起發佈的內部部署應用程式。</span><span class="sxs-lookup"><span data-stu-id="25224-107">Recommended capabilities for protecting identities and devices that access Office 365, other SaaS services, and on-premises applications published with Azure AD Application Proxy.</span></span>
  
<span data-ttu-id="25224-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [更多語言](https://www.microsoft.com/download/details.aspx?id=55032)</span><span class="sxs-lookup"><span data-stu-id="25224-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [More languages](https://www.microsoft.com/download/details.aspx?id=55032)</span></span>
  
## <a name="step-2-protect-administrator-accounts-and-access"></a><span data-ttu-id="25224-109">步驟 2： 保護系統管理員帳戶和存取</span><span class="sxs-lookup"><span data-stu-id="25224-109">Step 2: Protect administrator accounts and access</span></span>
<span data-ttu-id="25224-110">您用於管理 Office 365 環境的管理帳戶包括提升的權限。</span><span class="sxs-lookup"><span data-stu-id="25224-110">The administrative accounts you use to administer your Office 365 environment include elevated privileges.</span></span> <span data-ttu-id="25224-111">這些是有價值的目標的駭客和網路罪犯。</span><span class="sxs-lookup"><span data-stu-id="25224-111">These are valuable targets for hackers and cyber criminals.</span></span> 

<span data-ttu-id="25224-112">開始使用系統管理員帳戶僅適用於管理。</span><span class="sxs-lookup"><span data-stu-id="25224-112">Begin by using administrator accounts only for administration.</span></span> <span data-ttu-id="25224-113">系統管理員應該有個別的使用者帳戶一般，非系統管理員使用與僅使用其管理的帳戶時所需完成其工作職責相關聯的工作。</span><span class="sxs-lookup"><span data-stu-id="25224-113">Admins should have a separate user account for regular, non-administrative use and only use their administrative account when necessary to complete a task associated with their job function.</span></span>

<span data-ttu-id="25224-114">保護您的系統管理員帳戶具有多重要素驗證和條件式存取。</span><span class="sxs-lookup"><span data-stu-id="25224-114">Protect your administrator accounts with multi-factor authentication and conditional access.</span></span> <span data-ttu-id="25224-115">如需詳細資訊，請參閱[ Protecting 系統管理員帳戶](https://docs.microsoft.com/en-us/microsoft-365/enterprise/identity-access-prerequisites#protecting-administrator-accounts)。</span><span class="sxs-lookup"><span data-stu-id="25224-115">For more information, see [Protecting administrator accounts](https://docs.microsoft.com/en-us/microsoft-365/enterprise/identity-access-prerequisites#protecting-administrator-accounts).</span></span> 

<span data-ttu-id="25224-116">接下來，在 Office 365 中設定特殊權限的存取管理。</span><span class="sxs-lookup"><span data-stu-id="25224-116">Next, configure privileged access management in Office 365.</span></span> <span data-ttu-id="25224-117">特殊權限存取管理可讓 Office 365 中的特殊權限的系統管理工作更精細的存取控制。</span><span class="sxs-lookup"><span data-stu-id="25224-117">Privileged access management allows granular access control over privileged admin tasks in Office 365.</span></span> <span data-ttu-id="25224-118">它可以協助保護您的組織可能使用現有的特殊權限的系統管理員帳戶具有常設存取權的敏感資料或存取重要的組態設定的外洩。</span><span class="sxs-lookup"><span data-stu-id="25224-118">It can help protect your organization from breaches that may use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings.</span></span>

- [<span data-ttu-id="25224-119">概觀權限存取管理</span><span class="sxs-lookup"><span data-stu-id="25224-119">Overview of privileged access management</span></span>](privileged-access-management-overview.md)
- [<span data-ttu-id="25224-120">設定特殊權限存取管理</span><span class="sxs-lookup"><span data-stu-id="25224-120">Configure privileged access management</span></span>](privileged-access-management-configuration.md)

<span data-ttu-id="25224-121">其他上方的建議是使用工作站特別針對系統管理工作。</span><span class="sxs-lookup"><span data-stu-id="25224-121">Another top recommendation is to use workstations specifically configured for administrative work.</span></span> <span data-ttu-id="25224-122">這些是僅適用於系統管理工作的專用的裝置。</span><span class="sxs-lookup"><span data-stu-id="25224-122">These are dedicated devices that are only used for administrative tasks.</span></span> <span data-ttu-id="25224-123">請參閱[保護特殊存取權限](https://docs.microsoft.com/en-us/windows-server/identity/securing-privileged-access/securing-privileged-access)。</span><span class="sxs-lookup"><span data-stu-id="25224-123">See [Securing privileged access](https://docs.microsoft.com/en-us/windows-server/identity/securing-privileged-access/securing-privileged-access).</span></span>

<span data-ttu-id="25224-124">最後，您可以在您的租用戶中建立兩個或多個緊急存取帳戶來降低不慎缺乏系統管理存取權的影響。</span><span class="sxs-lookup"><span data-stu-id="25224-124">Finally, you can mitigate the impact of inadvertent lack of administrative access by creating two or more emergency access accounts in your tenant.</span></span> <span data-ttu-id="25224-125">請參閱[在 Azure AD 中的管理緊急存取帳戶](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-emergency-access)。</span><span class="sxs-lookup"><span data-stu-id="25224-125">See [Manage emergency access accounts in Azure AD](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span> 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a><span data-ttu-id="25224-126">步驟 3： 設定建議身分識別與裝置存取原則</span><span class="sxs-lookup"><span data-stu-id="25224-126">Step 3: Configure recommended identity and device access policies</span></span>
<span data-ttu-id="25224-127">多重要素驗證 (MFA) 和條件式存取原則是功能強大的工具針對遭入侵帳戶減輕和未經授權的存取。</span><span class="sxs-lookup"><span data-stu-id="25224-127">Multi-factor authentication (MFA) and conditional access policies are powerful tools for mitigating against compromised accounts and unauthorized access.</span></span> <span data-ttu-id="25224-128">我們建議您實作一群一起經過測試的原則。</span><span class="sxs-lookup"><span data-stu-id="25224-128">We recommend implementing a set of policies that have been tested together.</span></span> <span data-ttu-id="25224-129">如需詳細資訊，包括部署步驟，請參閱[身分識別與裝置存取設定](https://docs.microsoft.com/en-us/microsoft-365/enterprise/microsoft-365-policies-configurations)。</span><span class="sxs-lookup"><span data-stu-id="25224-129">For more information, including deployment steps, see [Identity and device access configurations](https://docs.microsoft.com/en-us/microsoft-365/enterprise/microsoft-365-policies-configurations).</span></span>

 <span data-ttu-id="25224-130">這些原則實作下列功能：</span><span class="sxs-lookup"><span data-stu-id="25224-130">These policies implement the following capabilities:</span></span>
- <span data-ttu-id="25224-131">單行雙因素驗證</span><span class="sxs-lookup"><span data-stu-id="25224-131">Mult-factor authentication</span></span>
- <span data-ttu-id="25224-132">條件式存取</span><span class="sxs-lookup"><span data-stu-id="25224-132">Conditional access</span></span>
- <span data-ttu-id="25224-133">Intune 應用程式防護 （應用程式和資料保護，裝置）</span><span class="sxs-lookup"><span data-stu-id="25224-133">Intune app protection (app and data protection for devices)</span></span>
- <span data-ttu-id="25224-134">Intune 裝置合規性</span><span class="sxs-lookup"><span data-stu-id="25224-134">Intune device compliance</span></span>
- <span data-ttu-id="25224-135">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="25224-135">Azure AD Identity Protection</span></span>

<span data-ttu-id="25224-136">Implemetning Intune 裝置合規性需要裝置註冊。</span><span class="sxs-lookup"><span data-stu-id="25224-136">Implemetning Intune device compliance requires device enrollment.</span></span> <span data-ttu-id="25224-137">管理裝置，可讓您以確保它們的狀況良好且符合標準前環境中允許存取資源。</span><span class="sxs-lookup"><span data-stu-id="25224-137">Managing devices allows you to ensure that they are healthy and compliant before allowing them access to resources in your environment.</span></span> <span data-ttu-id="25224-138">請參閱 <<c0>管理在 Intune 中註冊裝置</span><span class="sxs-lookup"><span data-stu-id="25224-138">See [Enroll devices for management in Intune](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span></span>

## <a name="step-4-configure-sharepoint-device-access-policies"></a><span data-ttu-id="25224-139">步驟 4： 設定 SharePoint 的裝置存取原則</span><span class="sxs-lookup"><span data-stu-id="25224-139">Step 4: Configure SharePoint device access policies</span></span>

<span data-ttu-id="25224-140">Microsoft 建議您保護機密和高管制與裝置存取控制內容的 SharePoint 網站內容。</span><span class="sxs-lookup"><span data-stu-id="25224-140">Microsoft recommends you protect content in SharePoint sites with sensitive and highly-regulated content with device access controls.</span></span> <span data-ttu-id="25224-141">如需詳細資訊，請參閱 <<c0>保護 SharePoint 網站與檔案的原則建議。</span><span class="sxs-lookup"><span data-stu-id="25224-141">For more information, see [Policy recommendations for securing SharePoint sites and files](https://docs.microsoft.com/en-us/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span>



    

