---
title: 保護 Office 365 中的資料與服務存取權
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 4/17/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: 保護存取 O365 資料及服務的登陸頁面
ms.openlocfilehash: e6e2d8d3ba6482d4b80593bd9e09d49d6120af80
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22527013"
---
# <a name="protect-access-to-data-and-services-in-office-365"></a><span data-ttu-id="d4acd-103">保護 Office 365 中的資料與服務存取權</span><span class="sxs-lookup"><span data-stu-id="d4acd-103">Protect access to data and services in Office 365</span></span>

<span data-ttu-id="d4acd-p101">保護您的 Office 365 資料及服務的存取很重要防禦適當攻擊及防範資料遺失。相同的保護設定可套用至您的環境中的其他 saas 和應用程式及偶數內部應用程式發佈與 Azure Active Directory 應用程式 Proxy。</span><span class="sxs-lookup"><span data-stu-id="d4acd-p101">Protecting access to your Office 365 data and services is crucial to defending against cyber-attacks and guarding against data loss. The same protections can be applied to other SaaS applications in your environment and even to on-premises applications published with Azure Active Directory Application Proxy.</span></span>
  
## <a name="step-1-review-recommendations"></a><span data-ttu-id="d4acd-106">步驟 1： 檢閱建議</span><span class="sxs-lookup"><span data-stu-id="d4acd-106">Step 1: Review recommendations</span></span>

<span data-ttu-id="d4acd-107">推薦可用於保護身分識別和裝置的功能，其可存取 Office 365、其他 SaaS 服務，以及與 Azure AD 應用程式 Proxy 一起發佈的內部部署應用程式。</span><span class="sxs-lookup"><span data-stu-id="d4acd-107">Recommended capabilities for protecting identities and devices that access Office 365, other SaaS services, and on-premises applications published with Azure AD Application Proxy.</span></span>
  
<span data-ttu-id="d4acd-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [更多語言](https://www.microsoft.com/download/details.aspx?id=55032)</span><span class="sxs-lookup"><span data-stu-id="d4acd-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [More languages](https://www.microsoft.com/download/details.aspx?id=55032)</span></span>
  
## <a name="step-2-configure-mfa"></a><span data-ttu-id="d4acd-109">步驟 2： 設定 MFA</span><span class="sxs-lookup"><span data-stu-id="d4acd-109">Step 2: Configure MFA</span></span>

<span data-ttu-id="d4acd-110">使用您自己的方式放置到 MFA、 決定哪個版本最適合您，這些資源，然後規劃及部署 MFA 為您的環境。</span><span class="sxs-lookup"><span data-stu-id="d4acd-110">Use these resources to orient yourself to MFA, decide which version is right for you, and then plan and deploy MFA for your environment.</span></span>
  
- [<span data-ttu-id="d4acd-111">什麼是 Azure 的多重要素驗證？</span><span class="sxs-lookup"><span data-stu-id="d4acd-111">What is Azure multi-factor authentication?</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication)
    
- [<span data-ttu-id="d4acd-112">您選擇的 Azure 的多重要素驗證解決方案</span><span class="sxs-lookup"><span data-stu-id="d4acd-112">Choose the Azure multi-factor authentication solution for you</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started)
    
- [<span data-ttu-id="d4acd-113">如何取得 Azure 的多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="d4acd-113">How to get Azure multi-factor authentication</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-versions-plans)
    
- [<span data-ttu-id="d4acd-114">規劃 Office 365 部署的多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="d4acd-114">Plan for multi-factor authentication for Office 365 deployments</span></span>](https://support.office.com/article/043807b2-21db-4d5c-b430-c8a6dee0e6ba)
    
- [<span data-ttu-id="d4acd-115">設定 Office 365 使用者的多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="d4acd-115">Set up multi-factor authentication for Office 365 users</span></span>](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)
    
- [<span data-ttu-id="d4acd-116">規劃部署 MFA、 雲端或內部部署位置</span><span class="sxs-lookup"><span data-stu-id="d4acd-116">Plan where to deploy MFA, Cloud or on-premises</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started)
    
- [<span data-ttu-id="d4acd-117">設定 Azure 的多重要素驗證設定</span><span class="sxs-lookup"><span data-stu-id="d4acd-117">Configure Azure multi-factor authentication settings</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-whats-next)
    
## <a name="step-3-enforce-mfa-with-azure-ad-conditional-access-rules"></a><span data-ttu-id="d4acd-118">步驟 3： 強制 MFA 搭配 Azure AD 條件式存取規則</span><span class="sxs-lookup"><span data-stu-id="d4acd-118">Step 3: Enforce MFA with Azure AD conditional access rules</span></span>

<span data-ttu-id="d4acd-119">如果您使用 Azure AD MFA，建立 MFA 需要存取 Office 365 和您環境中的其他 saas 和應用程式的設定格式化的條件存取規則。</span><span class="sxs-lookup"><span data-stu-id="d4acd-119">If you are using Azure AD MFA, create a conditional access rule to require MFA for access to Office 365 and other SaaS apps in your environment.</span></span>
  
- [<span data-ttu-id="d4acd-120">Azure Active Directory 中的設定格式化的條件存取</span><span class="sxs-lookup"><span data-stu-id="d4acd-120">Conditional access in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)
    
## <a name="step-4-configure-sharepoint-device-access-policies"></a><span data-ttu-id="d4acd-121">步驟 4： 設定 SharePoint 裝置存取原則</span><span class="sxs-lookup"><span data-stu-id="d4acd-121">Step 4: Configure SharePoint device access policies</span></span>

<span data-ttu-id="d4acd-p102">SharePoint Online 和 OneDrive for Business 的裝置存取原則建議進行保護機密、 機密、 和規範資料。即將推出則裝置存取原則套用至個別小組網站的能力。</span><span class="sxs-lookup"><span data-stu-id="d4acd-p102">Device access policies for SharePoint Online and OneDrive for Business are recommended for protecting sensitive, classified, and regulated data. Coming soon is the ability to apply device access policies to individual team sites.</span></span>
  
- [<span data-ttu-id="d4acd-124">從未受控裝置中控制存取權</span><span class="sxs-lookup"><span data-stu-id="d4acd-124">Control access from unmanaged devices</span></span>](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622?ui=en-US&amp;rs=en-US&amp;ad=US)
    
## <a name="step-5-configure-app-and-data-protection-for-devices"></a><span data-ttu-id="d4acd-125">步驟 5： 設定應用程式及資料保護裝置</span><span class="sxs-lookup"><span data-stu-id="d4acd-125">Step 5: Configure app and data protection for devices</span></span>

<span data-ttu-id="d4acd-p103">您可以管理不論是否將裝置註冊的行動裝置管理的行動裝置上的應用程式。這會對意外 Office 365，包括郵件和檔案中的資料外洩保護。</span><span class="sxs-lookup"><span data-stu-id="d4acd-p103">You can manage applications on mobile devices regardless of whether the devices are enrolled for mobile device management. This protects against accidental leakage of data in Office 365, including mail and files.</span></span>
  
- <span data-ttu-id="d4acd-128">IOS 及 android （英文）：[保護應用程式資料 Microsoft intune 的應用程式保護原則 （英文）](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="d4acd-128">For iOS and Android: [Protect app data using app protection policies with Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)</span></span>
    
<span data-ttu-id="d4acd-129">對於 Windows 10 設定 Windows 資訊保護 (WIP) 以避免意外的資料外洩。</span><span class="sxs-lookup"><span data-stu-id="d4acd-129">For Windows 10, configure Windows Information Protection (WIP) to prevent accidental data leaks.</span></span>
  
- <span data-ttu-id="d4acd-130">受管理的裝置：[建立與註冊原則使用 Azure 入口網站的 Microsoft Intune Windows 資訊保護 (WIP)](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune-azure)</span><span class="sxs-lookup"><span data-stu-id="d4acd-130">For managed devices: [Create a Windows Information Protection (WIP) with enrollment policy using the Azure portal for Microsoft Intune](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune-azure)</span></span>
    
- <span data-ttu-id="d4acd-131">未受管理的裝置：[建立及部署 Windows 資訊保護 (WIP) 應用程式保護原則 intune](https://docs.microsoft.com/intune/windows-information-protection-policy-create)</span><span class="sxs-lookup"><span data-stu-id="d4acd-131">For un-managed devices: [Create and deploy Windows Information Protection (WIP) app protection policy with Intune](https://docs.microsoft.com/intune/windows-information-protection-policy-create)</span></span>
    
## <a name="step-6-manage-devices-with-intune"></a><span data-ttu-id="d4acd-132">步驟 6： 管理 intune 的裝置</span><span class="sxs-lookup"><span data-stu-id="d4acd-132">Step 6: Manage devices with Intune</span></span>

<span data-ttu-id="d4acd-p104">管理裝置可讓您以確保其皆為正常且符合標準前環境中允許資源的存取權。裝置以設定格式化條件規則可協助您確保攻擊者無法存取您的資源來自未受管理的裝置的存取。</span><span class="sxs-lookup"><span data-stu-id="d4acd-p104">Managing devices allows you to ensure that they are healthy and compliant before allowing them access to resources in your environment. Device based conditional access rules help ensure attackers can't gain access to your resources from unmanaged devices.</span></span>
  
- [<span data-ttu-id="d4acd-135">註冊裝置管理的 Intune</span><span class="sxs-lookup"><span data-stu-id="d4acd-135">Enroll devices for management in Intune</span></span>](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)
    
## <a name="step-7-configure-additional-intune-policies-and-conditional-access-rules-for-your-environment"></a><span data-ttu-id="d4acd-136">步驟 7： 設定其他 Intune 原則和您環境的條件式存取規則</span><span class="sxs-lookup"><span data-stu-id="d4acd-136">Step 7: Configure additional Intune policies and conditional access rules for your environment</span></span>

<span data-ttu-id="d4acd-137">使用下列建議設定為起點的企業規模或複雜的存取安全使用情況。</span><span class="sxs-lookup"><span data-stu-id="d4acd-137">Use these recommended configurations as a starting point for enterprise scale or sophisticated access security scenarios.</span></span>
  
- [<span data-ttu-id="d4acd-138">安全的電子郵件原則及組態</span><span class="sxs-lookup"><span data-stu-id="d4acd-138">Secure email policies and configurations</span></span>](https://docs.microsoft.com/azure/active-directory/secure-email-introduction)
    

