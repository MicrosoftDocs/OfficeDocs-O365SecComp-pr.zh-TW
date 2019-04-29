---
title: 為 Office 365 應用程式部署條件式存取應用程式控制
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.reviewer: alesibov
ms.audience: Admin
ms.topic: reference
ms.date: 02/27/2019
ms.service: O365-seccomp
localization_priority: Normal
description: 請遵循下列步驟來設定 Azure AD Office 365 應用程式連接至 Office 365 雲端 App 安全性條件式存取應用程式控制加以控制。
ms.openlocfilehash: 74cc415220282491694bf417a6761fd43a6d3521
ms.sourcegitcommit: e23b84ef4eee9cccec7205826b71ddfe9aaac2f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/28/2019
ms.locfileid: "33402941"
---
# <a name="deploy-conditional-access-app-control-for-office-365-apps"></a><span data-ttu-id="e4973-103">為 Office 365 應用程式部署條件式存取應用程式控制</span><span class="sxs-lookup"><span data-stu-id="e4973-103">Deploy Conditional Access App Control for Office 365 apps</span></span>

|<span data-ttu-id="e4973-104">評估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="e4973-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="e4973-105">規劃 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="e4973-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="e4973-106">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="e4973-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="e4973-107">使用率 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="e4973-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="e4973-108">啟動評估</span><span class="sxs-lookup"><span data-stu-id="e4973-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="e4973-109">開始規劃</span><span class="sxs-lookup"><span data-stu-id="e4973-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="e4973-110">您在此處 ！</span><span class="sxs-lookup"><span data-stu-id="e4973-110">You are here!</span></span>  <br/> [<span data-ttu-id="e4973-111">後續步驟</span><span class="sxs-lookup"><span data-stu-id="e4973-111">Next step</span></span>](ocas-session-policies.md) <br/> |[<span data-ttu-id="e4973-112">開始使用</span><span class="sxs-lookup"><span data-stu-id="e4973-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |

<span data-ttu-id="e4973-113">請遵循下列步驟來設定 Azure AD Office 365 應用程式連接至 Office 365 雲端 App 安全性條件式存取應用程式控制加以控制。</span><span class="sxs-lookup"><span data-stu-id="e4973-113">Follow these steps to configure Azure AD Office 365 apps to be controlled by Office 365 Cloud App Security Conditional Access App Control.</span></span>

<span data-ttu-id="e4973-114">**步驟 1： [建立 Azure AD 條件式存取測試原則](#step-1-create-an-azure-ad-conditional-access-test-policy)**</span><span class="sxs-lookup"><span data-stu-id="e4973-114">**Step 1: [Create an Azure AD conditional access test policy](#step-1-create-an-azure-ad-conditional-access-test-policy)**</span></span>

<span data-ttu-id="e4973-115">**步驟 2： [使用中應用程式的原則的範圍限定在使用者登入。](#step-2-sign-in-with-a-user-scoped-to-the-policy-in-the-apps)**</span><span class="sxs-lookup"><span data-stu-id="e4973-115">**Step 2: [Sign in with a user scoped to the policy in the apps](#step-2-sign-in-with-a-user-scoped-to-the-policy-in-the-apps)**</span></span>

<span data-ttu-id="e4973-116">**步驟 3： 如果您未在 Azure AD 中選取的內建的雲端 App 安全性原則，或如果您想要將原則套用至非精選應用程式， [設定進階 Cloud App Security 入口網站中的控制項](#step-3-configure-advanced-controls-in-the-cloud-app-security-portal)**</span><span class="sxs-lookup"><span data-stu-id="e4973-116">**Step 3: If you did not select a built-in Cloud App Security policy in Azure AD or if you want to apply the policy to a non-featured app, [Configure advanced controls in the Cloud App Security portal](#step-3-configure-advanced-controls-in-the-cloud-app-security-portal)**</span></span>

<span data-ttu-id="e4973-117">**步驟 4：[測試部署](#step-4-test-the-deployment)**</span><span class="sxs-lookup"><span data-stu-id="e4973-117">**Step 4: [Test the deployment](#step-4-test-the-deployment)**</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e4973-118">若要部署條件式存取應用程式控制 Office 365 應用程式，您需要有效的 [授權 Azure AD Premium P1](https://docs.microsoft.com/azure/active-directory/license-users-groups) 以及 Office 365 雲端 App 安全性授權。</span><span class="sxs-lookup"><span data-stu-id="e4973-118">To deploy Conditional Access App Control for Office 365 apps, you need a valid [license for Azure AD Premium P1](https://docs.microsoft.com/azure/active-directory/license-users-groups) as well as a Office 365 Cloud App Security license.</span></span>

## <a name="step-1-create-an-azure-ad-conditional-access-test-policy"></a><span data-ttu-id="e4973-119">步驟 1： 建立 Azure AD 條件式存取測試原則</span><span class="sxs-lookup"><span data-stu-id="e4973-119">Step 1: Create an Azure AD conditional access test policy</span></span> 

1. <span data-ttu-id="e4973-120">在 Azure Active Directory，在 [ **安全性**] 下按一下 [ **條件式**存取]。</span><span class="sxs-lookup"><span data-stu-id="e4973-120">In Azure Active Directory, under **Security**, click on **Conditional access**.</span></span>

2. <span data-ttu-id="e4973-121">按一下 [ **新增原則** 並建立新的原則。</span><span class="sxs-lookup"><span data-stu-id="e4973-121">Click **New policy** and create a new policy.</span></span>

3. <span data-ttu-id="e4973-122">在測試原則] 之下 **的使用者**，將指派的測試使用者或使用者可以用於初始登入和驗證。</span><span class="sxs-lookup"><span data-stu-id="e4973-122">In the TEST policy, under **Users**, assign a test user or user that can be used for an initial sign-on and verification.</span></span>

4. <span data-ttu-id="e4973-123">在測試原則] 之下 **雲端應用程式**，請將您想要的應用程式指派給與條件式存取應用程式控制項的控制項。</span><span class="sxs-lookup"><span data-stu-id="e4973-123">In the TEST policy, under **Cloud app**, assign the apps you want to control with Conditional Access App Control.</span></span>

5. <span data-ttu-id="e4973-124">[ **工作階段**中，將原則設定為使用其中一個內建的原則， **只有監視器** 或 **封鎖下載**。</span><span class="sxs-lookup"><span data-stu-id="e4973-124">Under **Session**, set the policy to use either of the built-in policies, **Monitor only** or **Block downloads**.</span></span> <span data-ttu-id="e4973-125">或選取 [ **使用自訂原則** Cloud App Security 入口網站中設定的進階的原則。</span><span class="sxs-lookup"><span data-stu-id="e4973-125">Or select **Use custom policy** to set an advanced policy in the Cloud App Security portal.</span></span>

6. <span data-ttu-id="e4973-126">新增任何適用的 **條件指派** 或 **授與控制項** （選用）。</span><span class="sxs-lookup"><span data-stu-id="e4973-126">Add any applicable **Condition assignments** or **Grant controls** (optional).</span></span>

> ![Azure AD 條件式存取](media/OCASimage1.png)

## <a name="step-2-sign-in-with-a-user-scoped-to-the-policy-in-the-apps"></a><span data-ttu-id="e4973-128">步驟 2： 使用中應用程式的原則的範圍限定在使用者登入</span><span class="sxs-lookup"><span data-stu-id="e4973-128">Step 2: Sign in with a user scoped to the policy in the apps</span></span> 

<span data-ttu-id="e4973-129">您建立原則之後，登入該原則中設定每個應用程式。</span><span class="sxs-lookup"><span data-stu-id="e4973-129">After you've created the policy, sign in to each app configured in that policy.</span></span> <span data-ttu-id="e4973-130">請確定您使用登入的原則中設定的使用者。</span><span class="sxs-lookup"><span data-stu-id="e4973-130">Make sure you sign in using a user configured in the policy.</span></span> <span data-ttu-id="e4973-131">請確定第一個現有的工作階段登出。</span><span class="sxs-lookup"><span data-stu-id="e4973-131">Make sure to first sign out of existing sessions.</span></span>

<span data-ttu-id="e4973-132">Cloud App Security 會同步處理原則的詳細資訊，其伺服器的登入每個新的應用程式。</span><span class="sxs-lookup"><span data-stu-id="e4973-132">Cloud App Security will sync your policy details to its servers for each new app you log in to.</span></span> <span data-ttu-id="e4973-133">這可能需要長達 1 分鐘。</span><span class="sxs-lookup"><span data-stu-id="e4973-133">This may take up to one minute.</span></span>

## <a name="step-3-configure-advanced-controls-in-the-cloud-app-security-portal"></a><span data-ttu-id="e4973-134">步驟 3： 設定進階 Cloud App Security 入口網站中的控制項</span><span class="sxs-lookup"><span data-stu-id="e4973-134">Step 3: Configure advanced controls in the Cloud App Security portal</span></span> 

<span data-ttu-id="e4973-135">上述的指示可以幫助您直接在 Azure AD 中建立內建 Cloud App Security 原則精選應用程式。</span><span class="sxs-lookup"><span data-stu-id="e4973-135">The instructions above helped you create a built-in Cloud App Security policy for featured apps directly in Azure AD.</span></span>

<span data-ttu-id="e4973-136">若要設定的進階的原則，請建立 [存取原則](ocas-access-policies.md) 或 [工作階段原則](ocas-session-policies.md) 在 Office 365 雲端 App 安全性入口網站中。</span><span class="sxs-lookup"><span data-stu-id="e4973-136">To configure an advanced policy, create an [access policy](ocas-access-policies.md) or a [session policy](ocas-session-policies.md) in the Office 365 Cloud App Security portal.</span></span>

### <a name="to-identify-devices-using-client-certificates-this-is-optional"></a><span data-ttu-id="e4973-137">若要識別裝置使用 （這是選用的） 的用戶端憑證：</span><span class="sxs-lookup"><span data-stu-id="e4973-137">To identify devices using client certificates (this is optional):</span></span>

1. <span data-ttu-id="e4973-138">移至設定商旅，然後選擇 [ **裝置識別碼**。</span><span class="sxs-lookup"><span data-stu-id="e4973-138">Go to the settings cog and choose **Device identification**.</span></span>

2. <span data-ttu-id="e4973-139">上傳一或多個根 ca 或中繼憑證。</span><span class="sxs-lookup"><span data-stu-id="e4973-139">Upload one or more root or intermediate certificates.</span></span>

3. <span data-ttu-id="e4973-140">憑證上傳之後，您可以建立存取原則和工作階段的原則，根據 **裝置標記**及 **有效的用戶端憑證]**。</span><span class="sxs-lookup"><span data-stu-id="e4973-140">After the certificate is uploaded, you can create access policies and session policies based on **Device tag** and **Valid client certificate**.</span></span>

![條件式存取應用程式控制項的裝置識別碼](media/OCASimage2.png)

> [!NOTE]
> <span data-ttu-id="e4973-142">只有，從使用者來要求憑證，如果工作階段符合使用有效的用戶端憑證篩選器原則。</span><span class="sxs-lookup"><span data-stu-id="e4973-142">A certificate is only requested from a user if the session matches a policy that uses the valid client certificate filter.</span></span>
> 
## <a name="step-4-test-the-deployment"></a><span data-ttu-id="e4973-143">步驟 4： 測試部署</span><span class="sxs-lookup"><span data-stu-id="e4973-143">Step 4: Test the deployment</span></span> 

1. <span data-ttu-id="e4973-144">任何現有的工作階段中第一個登出。</span><span class="sxs-lookup"><span data-stu-id="e4973-144">First sign out of any existing sessions.</span></span> <span data-ttu-id="e4973-145">然後，嘗試登入已成功部署每個應用程式。</span><span class="sxs-lookup"><span data-stu-id="e4973-145">Then, try to sign in to each app that was successfully deployed.</span></span> <span data-ttu-id="e4973-146">使用以符合設定 Azure AD 中的原則的使用者登入。</span><span class="sxs-lookup"><span data-stu-id="e4973-146">Sign in using a user that matches the policy configured in Azure AD.</span></span>

2. <span data-ttu-id="e4973-147">在 Cloud App Security 入口網站中，[ **調查]**，選取 **活動記錄檔**，並確定每個應用程式擷取登入活動。</span><span class="sxs-lookup"><span data-stu-id="e4973-147">In the Cloud App Security portal, under **Investigate**, select **Activity log**, and make sure the login activities are captured for each app.</span></span>

3. <span data-ttu-id="e4973-148">您可以篩選上的 [ **進階**]，然後使用 **來源等於存取控制**進行篩選。</span><span class="sxs-lookup"><span data-stu-id="e4973-148">You can filter by clicking on **Advanced**, and then filtering using **Source equals Access control**.</span></span>

4. <span data-ttu-id="e4973-149">建議您登入從 managed 和 unmanaged 裝置的行動裝置和傳統型應用程式。</span><span class="sxs-lookup"><span data-stu-id="e4973-149">It's recommended that you sign into mobile and desktop apps from managed and unmanaged devices.</span></span> <span data-ttu-id="e4973-150">這是為了確保活動會正確擷取活動記錄檔中。</span><span class="sxs-lookup"><span data-stu-id="e4973-150">This is to make sure that the activities are properly captured in the activity log.</span></span> <span data-ttu-id="e4973-151">若要確認正確擷取活動，請按一下單一登入功能登入活動，讓它會開啟活動抽屜。</span><span class="sxs-lookup"><span data-stu-id="e4973-151">To verify that the activity is properly captured, click on a single sign-on log on activity so that it opens the activity drawer.</span></span> <span data-ttu-id="e4973-152">請確定 **使用者代理程式標記** 正確地反映 [裝置是否 （亦即行動裝置或桌面應用程式） 的原生用戶端或裝置是受管理的裝置 （相容，網域加入，或有效的用戶端憑證）。</span><span class="sxs-lookup"><span data-stu-id="e4973-152">Make sure the **User agent tag** properly reflects whether the device is a native client (meaning either a mobile or desktop app) or the device is a managed device (compliant, domain joined, or valid client certificate).</span></span>

> [!NOTE]
> <span data-ttu-id="e4973-153">部署之後，您無法移除應用程式，從 [條件式存取應用程式控制] 頁面。</span><span class="sxs-lookup"><span data-stu-id="e4973-153">After it is deployed, you can't remove an app from the Conditional Access App Control page.</span></span> <span data-ttu-id="e4973-154">只要您不需要在應用程式上設定工作階段或存取原則，條件式存取應用程式控制也不會變更任何應用程式的行為。</span><span class="sxs-lookup"><span data-stu-id="e4973-154">As long as you don't set a session or access policy on the app, the Conditional Access App Control won't change any behavior for the app.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e4973-155">後續步驟</span><span class="sxs-lookup"><span data-stu-id="e4973-155">Next steps</span></span>

- [<span data-ttu-id="e4973-156">了解 Office 365 雲端 App 安全性中的工作階段原則</span><span class="sxs-lookup"><span data-stu-id="e4973-156">Learn about session policies in Office 365 Cloud App Security</span></span>](ocas-session-policies.md)

- [<span data-ttu-id="e4973-157">了解 Office 365 雲端 App 安全性中的存取原則</span><span class="sxs-lookup"><span data-stu-id="e4973-157">Learn about access policies in Office 365 Cloud App Security</span></span>](ocas-access-policies.md) 

- [<span data-ttu-id="e4973-158">將您的 IP 位址分組，以簡化 Office 365 雲端 App 安全性中的管理</span><span class="sxs-lookup"><span data-stu-id="e4973-158">Group your IP addresses to simplify management in Office 365 Cloud App Security</span></span>](group-your-ip-addresses-in-ocas.md)