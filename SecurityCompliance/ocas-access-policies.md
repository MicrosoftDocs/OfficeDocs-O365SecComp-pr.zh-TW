---
title: Office 365 雲端 App 安全性中的存取原則
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.reviewer: alesibov
ms.audience: Admin
ms.topic: reference
ms.date: 02/27/2019
ms.service: O365-seccomp
localization_priority: Normal
description: Office 365 雲端 App 安全性存取原則啟用即時監視，並根據使用者、 位置、 裝置的雲端應用程式及應用程式的存取控制。 您可以建立任何裝置，包括未網域加入，並且不會管理 Windows Intune 推行至受管理的裝置的用戶端憑證或使用現有的憑證，例如協力廠商 MDM 憑證的裝置存取的原則。 例如，您可以部署至受管理的裝置、 用戶端憑證，而然後封鎖來自不使用憑證的裝置的存取。
ms.openlocfilehash: 5e8b8fa293420bc9ff3616daf288b8e02a2eb768
ms.sourcegitcommit: 866d8cab6bcfdd124516a8369e47ec797bc7cf8a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/27/2019
ms.locfileid: "30312080"
---
# <a name="access-policies-in-office-365-cloud-app-security"></a><span data-ttu-id="e78c3-105">Office 365 雲端 App 安全性中的存取原則</span><span class="sxs-lookup"><span data-stu-id="e78c3-105">Access policies in Office 365 Cloud App Security</span></span>

|<span data-ttu-id="e78c3-106">評估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="e78c3-106">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="e78c3-107">規劃 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="e78c3-107">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="e78c3-108">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="e78c3-108">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="e78c3-109">使用率 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="e78c3-109">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="e78c3-110">啟動評估</span><span class="sxs-lookup"><span data-stu-id="e78c3-110">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="e78c3-111">開始規劃</span><span class="sxs-lookup"><span data-stu-id="e78c3-111">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="e78c3-112">您在此處 ！</span><span class="sxs-lookup"><span data-stu-id="e78c3-112">You are here!</span></span>  <br/> [<span data-ttu-id="e78c3-113">下一步</span><span class="sxs-lookup"><span data-stu-id="e78c3-113">Next step</span></span>](group-your-ip-addresses-in-ocas.md) <br/> |[<span data-ttu-id="e78c3-114">開始使用</span><span class="sxs-lookup"><span data-stu-id="e78c3-114">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |

<span data-ttu-id="e78c3-115">Office 365 雲端 App 安全性存取原則啟用即時監視，並根據使用者、 位置、 裝置的雲端應用程式及應用程式的存取控制。</span><span class="sxs-lookup"><span data-stu-id="e78c3-115">Office 365 Cloud App Security access policies enable real-time monitoring and control over access to cloud apps based on user, location, device, and app.</span></span> <span data-ttu-id="e78c3-116">您可以建立任何裝置，包括未網域加入，並且不會管理 Windows Intune 推行至受管理的裝置的用戶端憑證或使用現有的憑證，例如協力廠商 MDM 憑證的裝置存取的原則。</span><span class="sxs-lookup"><span data-stu-id="e78c3-116">You can create access policies for any device, including devices that aren't domain joined, and not managed by Windows Intune by rolling out client certificates to managed devices or by using existing certificates, such as third-party MDM certificates.</span></span> <span data-ttu-id="e78c3-117">例如，您可以部署至受管理的裝置、 用戶端憑證，而然後封鎖來自不使用憑證的裝置的存取。</span><span class="sxs-lookup"><span data-stu-id="e78c3-117">For example, you can deploy client certificates to managed devices, and then block access from devices without a certificate.</span></span>

<span data-ttu-id="e78c3-118">而不是允許或封鎖存取完全， [工作階段](ocas-session-policies.md)原則 您可以允許存取時監視的工作階段及/或限制特定的工作階段的活動。</span><span class="sxs-lookup"><span data-stu-id="e78c3-118">Instead of allowing or blocking access completely, with [session policies](ocas-session-policies.md) you can allow access while monitoring the session and/or limit specific session activities.</span></span>

## <a name="prerequisites-to-using-access-policies"></a><span data-ttu-id="e78c3-119">若要使用存取原則的必要條件</span><span class="sxs-lookup"><span data-stu-id="e78c3-119">Prerequisites to using access policies</span></span>

- <span data-ttu-id="e78c3-120">Azure AD Premium P1 授權</span><span class="sxs-lookup"><span data-stu-id="e78c3-120">Azure AD Premium P1 license</span></span>

- <span data-ttu-id="e78c3-121">相關的應用程式應該是 [使用條件式存取應用程式控制部署](https://docs.microsoft.com/en-us/cloud-app-security/proxy-deployment-aad)</span><span class="sxs-lookup"><span data-stu-id="e78c3-121">The relevant apps should be [deployed with Conditional Access App Control](https://docs.microsoft.com/en-us/cloud-app-security/proxy-deployment-aad)</span></span>

- <span data-ttu-id="e78c3-122"> [Azure AD 條件式存取原則](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) 應具備將使用者重新導向至 Office 365 雲端 App 安全性，如下所示。</span><span class="sxs-lookup"><span data-stu-id="e78c3-122">An [Azure AD conditional access policy](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) should be in place that redirects users to Office 365 Cloud App Security, as described below.</span></span>

## <a name="create-an-azure-ad-conditional-access-policy"></a><span data-ttu-id="e78c3-123">建立 Azure AD 條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="e78c3-123">Create an Azure AD conditional access policy</span></span>

<span data-ttu-id="e78c3-124">Azure Active Directory 條件式存取原則與 Cloud App Security 工作階段原則適用於搭配檢查每個使用者工作階段，並決定每個應用程式的原則。</span><span class="sxs-lookup"><span data-stu-id="e78c3-124">Azure Active Directory conditional access policies and Cloud App Security session policies work in tandem to examine each user session and make policy decisions for each app.</span></span> <span data-ttu-id="e78c3-125">若要在 Azure AD 中設定的條件式存取原則，請遵循此程序：</span><span class="sxs-lookup"><span data-stu-id="e78c3-125">To set up a conditional access policy in Azure AD, follow this procedure:</span></span>

1. <span data-ttu-id="e78c3-126">設定 [Azure AD 條件式存取原則](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) 與使用者或群組的使用者與您想要與條件式存取應用程式控制項的控制項的應用程式的工作分派。</span><span class="sxs-lookup"><span data-stu-id="e78c3-126">Configure an [Azure AD conditional access policy](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) with assignments for user or group of users and the app you want to control with Conditional Access App Control.</span></span><br><span data-ttu-id="e78c3-127">附註： 已 [部署與條件式存取應用程式控制項](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad)僅應用程式 將會受到此原則。</span><span class="sxs-lookup"><span data-stu-id="e78c3-127">NOTE: Only apps that were [deployed with Conditional Access App Control](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad) will be affected by this policy.</span></span>

2. <span data-ttu-id="e78c3-128">將使用者路由傳送至 Office 365 雲端 App 安全性藉由選取 [ **使用條件式存取應用程式控制強制執行限制** 底下 **工作階段**。</span><span class="sxs-lookup"><span data-stu-id="e78c3-128">Route users to Office 365 Cloud App Security by selecting the **Use Conditional Access App Control enforced restrictions** under **Session**.</span></span>

## <a name="create-a-cloud-app-security-access-policy"></a><span data-ttu-id="e78c3-129">建立雲端 App 安全性存取原則</span><span class="sxs-lookup"><span data-stu-id="e78c3-129">Create a Cloud App Security access policy</span></span>

<span data-ttu-id="e78c3-130">若要建立新的存取原則，請遵循此程序：</span><span class="sxs-lookup"><span data-stu-id="e78c3-130">To create a new access policy, follow this procedure:</span></span>

1. <span data-ttu-id="e78c3-131">在 [入口網站中，選取 **控制項** 後面接著 **原則**。</span><span class="sxs-lookup"><span data-stu-id="e78c3-131">In the portal, select **Control** followed by **Policies**.</span></span>

2. <span data-ttu-id="e78c3-132">在 [ **原則** ] 頁面上，按一下 [ **建立原則** 選取 **存取原則**。</span><span class="sxs-lookup"><span data-stu-id="e78c3-132">In the **Policies** page, click **Create policy** and select **Access policy**.</span></span>

3. <span data-ttu-id="e78c3-133">在 [ **存取原則** ] 視窗中，指派原則，例如 *封鎖來自未受管理的裝置存取*的名稱。</span><span class="sxs-lookup"><span data-stu-id="e78c3-133">In the **Access policy** window, assign a name for your policy, such as *Block access from unmanaged devices*.</span></span>

4. <span data-ttu-id="e78c3-134">在 [ **比對下列所有的活動** ] 區段的 [ **活動來源**]，選取要套用至該原則的其他活動篩選。</span><span class="sxs-lookup"><span data-stu-id="e78c3-134">In the **Activities matching all of the following** section, Under **Activity source**, select additional activity filters to apply to the policy.</span></span> <span data-ttu-id="e78c3-135">篩選包含下列選項：</span><span class="sxs-lookup"><span data-stu-id="e78c3-135">Filters include the following options:</span></span>
    
    - <span data-ttu-id="e78c3-136">**裝置標記**： 使用此篩選器來識別未受管理的裝置。</span><span class="sxs-lookup"><span data-stu-id="e78c3-136">**Device tags**: Use this filter to identify unmanaged devices.</span></span>
    
    - <span data-ttu-id="e78c3-137">**位置**： 使用此篩選器來識別不明 （並因此風險） 的位置。</span><span class="sxs-lookup"><span data-stu-id="e78c3-137">**Location**: Use this filter to identify unknown (and therefore risky) locations.</span></span>
    
    - <span data-ttu-id="e78c3-138">**IP 位址**： 使用此篩選條件來篩選每個 IP 位址] 或 [使用先前指派的 IP 位址標記。</span><span class="sxs-lookup"><span data-stu-id="e78c3-138">**IP address**: Use this filter to filter per IP addresses or use previously assigned IP address tags.</span></span>
    
    - <span data-ttu-id="e78c3-139">**使用者代理程式標記**： 使用此篩選器啟用的啟發學習法來識別行動裝置和傳統型應用程式。</span><span class="sxs-lookup"><span data-stu-id="e78c3-139">**User agent tag**: Use this filter to enable the heuristic to identify mobile and desktop apps.</span></span> <span data-ttu-id="e78c3-140">此篩選器可以設定為等於或不等於。</span><span class="sxs-lookup"><span data-stu-id="e78c3-140">This filter can be set to equals or does not equal.</span></span> <span data-ttu-id="e78c3-141">值應該比照您每個雲端應用程式的行動裝置和傳統型應用程式。</span><span class="sxs-lookup"><span data-stu-id="e78c3-141">The values should be tested against your mobile and desktop apps for each cloud app.</span></span>

5. <span data-ttu-id="e78c3-142">在 [ **動作**] 下選取下列選項之一：</span><span class="sxs-lookup"><span data-stu-id="e78c3-142">Under **Actions**, select one of the following options:</span></span>
    
    - <span data-ttu-id="e78c3-143">**允許**： 設定此巨集指令，明確允許存取根據您所設定的原則篩選器。</span><span class="sxs-lookup"><span data-stu-id="e78c3-143">**Allow**: Set this action to explicitly allow access according to the policy filters you set.</span></span>
    
    - <span data-ttu-id="e78c3-144">**封鎖**： 設定此巨集指令來明確封鎖根據您所設定的原則篩選器的存取。</span><span class="sxs-lookup"><span data-stu-id="e78c3-144">**Block**: Set this action to explicitly block access according to the policy filters you set.</span></span>

6. <span data-ttu-id="e78c3-145">您可以 **建立的原則嚴重性與每個比對事件警示** 設定的警示限制並選取是否要為一封電子郵件及簡訊或警示。</span><span class="sxs-lookup"><span data-stu-id="e78c3-145">You can **Create an alert for each matching event with the policy's severity** and set an alert limit and select whether you want the alert as an email, a text message or both.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e78c3-146">後續步驟</span><span class="sxs-lookup"><span data-stu-id="e78c3-146">Next steps</span></span>

- [<span data-ttu-id="e78c3-147">將您的 IP 位址分組，以簡化 Office 365 雲端 App 安全性中的管理</span><span class="sxs-lookup"><span data-stu-id="e78c3-147">Group your IP addresses to simplify management in Office 365 Cloud App Security</span></span>](group-your-ip-addresses-in-ocas.md)