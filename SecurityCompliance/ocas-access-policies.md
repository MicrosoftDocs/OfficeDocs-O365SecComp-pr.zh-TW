---
title: Office 365 雲端應用程式安全性存取原則
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.reviewer: alesibov
ms.audience: Admin
ms.topic: reference
ms.date: 02/14/2019
ms.service: o365-administration
localization_priority: Normal
description: Office 365 雲端應用程式安全性存取原則啟用即時監視和存取使用者、 位置、 裝置為基礎的雲端應用程式及應用程式的控制權。您可以建立任何裝置，包括不網域加入，並啟用受管理的裝置的用戶端憑證或使用現有的憑證，例如協力廠商 MDM 憑證未受 Windows Intune 的裝置存取的原則。例如，您可以部署用戶端憑證以受管理的裝置，然後封鎖來自沒有憑證的裝置存取。
ms.openlocfilehash: bb4404793647c65ab8addc148e6efe24242f3079
ms.sourcegitcommit: 8679937354c1d8870ecd41519a59d2d7468c23c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2019
ms.locfileid: "30103308"
---
# <a name="access-policies-in-office-365-cloud-app-security"></a><span data-ttu-id="87f3d-105">Office 365 雲端應用程式安全性存取原則</span><span class="sxs-lookup"><span data-stu-id="87f3d-105">Access policies in Office 365 Cloud App Security</span></span>

|<span data-ttu-id="87f3d-106">評估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="87f3d-106">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="87f3d-107">規劃 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="87f3d-107">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="87f3d-108">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="87f3d-108">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="87f3d-109">使用率 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="87f3d-109">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="87f3d-110">啟動評估</span><span class="sxs-lookup"><span data-stu-id="87f3d-110">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="87f3d-111">開始規劃</span><span class="sxs-lookup"><span data-stu-id="87f3d-111">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="87f3d-112">您在此處 ！</span><span class="sxs-lookup"><span data-stu-id="87f3d-112">You are here!</span></span>  <br/> [<span data-ttu-id="87f3d-113">下一步</span><span class="sxs-lookup"><span data-stu-id="87f3d-113">Next step</span></span>](group-your-ip-addresses-in-ocas.md) <br/> |[<span data-ttu-id="87f3d-114">開始使用</span><span class="sxs-lookup"><span data-stu-id="87f3d-114">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |

<span data-ttu-id="87f3d-p102">Office 365 雲端應用程式安全性存取原則啟用即時監視和存取使用者、 位置、 裝置為基礎的雲端應用程式及應用程式的控制權。您可以建立任何裝置，包括不網域加入，並啟用受管理的裝置的用戶端憑證或使用現有的憑證，例如協力廠商 MDM 憑證未受 Windows Intune 的裝置存取的原則。例如，您可以部署用戶端憑證以受管理的裝置，然後封鎖來自沒有憑證的裝置存取。</span><span class="sxs-lookup"><span data-stu-id="87f3d-p102">Office 365 Cloud App Security access policies enable real-time monitoring and control over access to cloud apps based on user, location, device, and app. You can create access policies for any device, including devices that aren't domain joined, and not managed by Windows Intune by rolling out client certificates to managed devices or by using existing certificates, such as third-party MDM certificates. For example, you can deploy client certificates to managed devices, and then block access from devices without a certificate.</span></span>

<span data-ttu-id="87f3d-118">而不是允許或封鎖存取完全、 [工作階段的原則](ocas-session-policies.md)與 您可以監視工作階段和/或限制特定的工作階段活動時允許存取。</span><span class="sxs-lookup"><span data-stu-id="87f3d-118">Instead of allowing or blocking access completely, with [session policies](ocas-session-policies.md) you can allow access while monitoring the session and/or limit specific session activities.</span></span>

## <a name="prerequisites-to-using-access-policies"></a><span data-ttu-id="87f3d-119">若要使用存取原則的必要條件</span><span class="sxs-lookup"><span data-stu-id="87f3d-119">Prerequisites to using access policies</span></span>

- <span data-ttu-id="87f3d-120">Azure AD Premium P1 授權</span><span class="sxs-lookup"><span data-stu-id="87f3d-120">Azure AD Premium P1 license</span></span>

- <span data-ttu-id="87f3d-121">相關的應用程式應該是 [部署與設定格式化的條件的 Access 應用程式控制項](https://docs.microsoft.com/en-us/cloud-app-security/proxy-deployment-aad)</span><span class="sxs-lookup"><span data-stu-id="87f3d-121">The relevant apps should be [deployed with Conditional Access App Control](https://docs.microsoft.com/en-us/cloud-app-security/proxy-deployment-aad)</span></span>

- <span data-ttu-id="87f3d-122"> [Azure AD 條件式存取原則](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) 應該將使用者重新導向至 Office 365 雲端應用程式安全性] 的位置如下所示。</span><span class="sxs-lookup"><span data-stu-id="87f3d-122">An [Azure AD conditional access policy](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) should be in place that redirects users to Office 365 Cloud App Security, as described below.</span></span>

## <a name="create-an-azure-ad-conditional-access-policy"></a><span data-ttu-id="87f3d-123">建立 Azure AD 條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="87f3d-123">Create an Azure AD conditional access policy</span></span>

<span data-ttu-id="87f3d-p103">Azure Active Directory 設定格式化的條件存取原則與雲端應用程式安全性工作階段的原則中運作 tandem 檢查每個使用者工作階段並決定每個應用程式的原則。若要在 Azure AD 設定條件式存取原則，請遵循此程序：</span><span class="sxs-lookup"><span data-stu-id="87f3d-p103">Azure Active Directory conditional access policies and Cloud App Security session policies work in tandem to examine each user session and make policy decisions for each app. To set up a conditional access policy in Azure AD, follow this procedure:</span></span>

1. <span data-ttu-id="87f3d-126">設定 [Azure AD 條件式存取原則](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) 使用者或群組的使用者與您想要使用設定格式化的條件的 Access 應用程式控制項的控制項的應用程式的工作分派。</span><span class="sxs-lookup"><span data-stu-id="87f3d-126">Configure an [Azure AD conditional access policy](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) with assignments for user or group of users and the app you want to control with Conditional Access App Control.</span></span><br><span data-ttu-id="87f3d-127">請注意： 唯一的應用程式已 [部署與設定格式化的條件的 Access 應用程式控制項](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad) 將會受到此原則。</span><span class="sxs-lookup"><span data-stu-id="87f3d-127">NOTE: Only apps that were [deployed with Conditional Access App Control](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad) will be affected by this policy.</span></span>

2. <span data-ttu-id="87f3d-128">選取 [ **使用設定格式化的條件存取應用程式控制強制執行限制**路由使用者傳送至 Office 365 雲端應用程式安全性 下 **工作階段**。</span><span class="sxs-lookup"><span data-stu-id="87f3d-128">Route users to Office 365 Cloud App Security by selecting the **Use Conditional Access App Control enforced restrictions** under **Session**.</span></span>

## <a name="create-a-cloud-app-security-access-policy"></a><span data-ttu-id="87f3d-129">建立雲端應用程式安全性存取原則</span><span class="sxs-lookup"><span data-stu-id="87f3d-129">Create a Cloud App Security access policy</span></span>

<span data-ttu-id="87f3d-130">若要建立新的存取原則，請遵循此程序：</span><span class="sxs-lookup"><span data-stu-id="87f3d-130">To create a new access policy, follow this procedure:</span></span>

1. <span data-ttu-id="87f3d-131">在 [入口網站中，選取 **控制項** 後面 **的原則**。</span><span class="sxs-lookup"><span data-stu-id="87f3d-131">In the portal, select **Control** followed by **Policies**.</span></span>

2. <span data-ttu-id="87f3d-132">在 [ **原則** ] 頁面上，按一下 [ **建立原則** 並選取 [ **存取原則**。</span><span class="sxs-lookup"><span data-stu-id="87f3d-132">In the **Policies** page, click **Create policy** and select **Access policy**.</span></span>

3. <span data-ttu-id="87f3d-133">在 [ **存取原則** ] 視窗中，指派為您的原則，例如 *封鎖從未受管理的裝置存取*的名稱。</span><span class="sxs-lookup"><span data-stu-id="87f3d-133">In the **Access policy** window, assign a name for your policy, such as *Block access from unmanaged devices*.</span></span>

4. <span data-ttu-id="87f3d-p104">在 **符合下列所有的活動** ] 區段的 [ **活動來源**，請選取要套用至原則的其他活動篩選器。篩選包含下列選項：</span><span class="sxs-lookup"><span data-stu-id="87f3d-p104">In the **Activities matching all of the following** section, Under **Activity source**, select additional activity filters to apply to the policy. Filters include the following options:</span></span>
    
    - <span data-ttu-id="87f3d-136">**裝置標記**： 使用此篩選器來識別未受管理的裝置。</span><span class="sxs-lookup"><span data-stu-id="87f3d-136">**Device tags**: Use this filter to identify unmanaged devices.</span></span>
    
    - <span data-ttu-id="87f3d-137">**位置**： 使用此篩選器來識別不明 （與因此 risky） 的位置。</span><span class="sxs-lookup"><span data-stu-id="87f3d-137">**Location**: Use this filter to identify unknown (and therefore risky) locations.</span></span>
    
    - <span data-ttu-id="87f3d-138">**IP 位址**： 使用此篩選來篩選每個 IP 位址] 或 [使用先前指派的 IP 位址標記。</span><span class="sxs-lookup"><span data-stu-id="87f3d-138">**IP address**: Use this filter to filter per IP addresses or use previously assigned IP address tags.</span></span>
    
    - <span data-ttu-id="87f3d-p105">**使用者代理程式 tag**： 使用此篩選器以啟用大概識別行動裝置與桌面應用程式。此篩選器可以設定為等於或不等於。值應比照您各個雲端應用程式的行動電話和桌面應用程式。</span><span class="sxs-lookup"><span data-stu-id="87f3d-p105">**User agent tag**: Use this filter to enable the heuristic to identify mobile and desktop apps. This filter can be set to equals or does not equal. The values should be tested against your mobile and desktop apps for each cloud app.</span></span>

5. <span data-ttu-id="87f3d-142">[ **動作**] 下選取下列選項之一：</span><span class="sxs-lookup"><span data-stu-id="87f3d-142">Under **Actions**, select one of the following options:</span></span>
    
    - <span data-ttu-id="87f3d-143">**允許**： 設定為明確允許根據您所設定的原則篩選器來存取此巨集指令。</span><span class="sxs-lookup"><span data-stu-id="87f3d-143">**Allow**: Set this action to explicitly allow access according to the policy filters you set.</span></span>
    
    - <span data-ttu-id="87f3d-144">**封鎖**： 設定為明確封鎖根據您所設定的原則篩選器來存取此巨集指令。</span><span class="sxs-lookup"><span data-stu-id="87f3d-144">**Block**: Set this action to explicitly block access according to the policy filters you set.</span></span>

6. <span data-ttu-id="87f3d-145">您可以 **建立原則的嚴重性與每個相符的事件通知** 設定提醒的限制並選取您要做為電子郵件、 文字訊息或這兩者的警示。</span><span class="sxs-lookup"><span data-stu-id="87f3d-145">You can **Create an alert for each matching event with the policy's severity** and set an alert limit and select whether you want the alert as an email, a text message or both.</span></span>

## <a name="next-steps"></a><span data-ttu-id="87f3d-146">後續步驟</span><span class="sxs-lookup"><span data-stu-id="87f3d-146">Next steps</span></span>

- [<span data-ttu-id="87f3d-147">將您的 IP 位址分組，以簡化 Office 365 雲端 App 安全性中的管理</span><span class="sxs-lookup"><span data-stu-id="87f3d-147">Group your IP addresses to simplify management in Office 365 Cloud App Security</span></span>](group-your-ip-addresses-in-ocas.md)