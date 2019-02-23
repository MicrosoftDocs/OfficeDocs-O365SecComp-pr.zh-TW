---
title: 為 Office 365 應用程式部署條件式存取應用程式控制
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.reviewer: alesibov
ms.audience: Admin
ms.topic: reference
ms.date: 02/14/2019
ms.service: O365-seccomp
localization_priority: Normal
description: 請遵循下列步驟來設定 Office 365 雲端應用程式的安全性設定格式化的條件 Access 應用程式控制項所控制的 Azure AD Office 365 應用程式。
ms.openlocfilehash: cfb3d885fdfaf0e4698b1f8f9a0e13baacf43f66
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30221053"
---
# <a name="deploy-conditional-access-app-control-for-office-365-apps"></a><span data-ttu-id="756e6-103">為 Office 365 應用程式部署條件式存取應用程式控制</span><span class="sxs-lookup"><span data-stu-id="756e6-103">Deploy Conditional Access App Control for Office 365 apps</span></span>

|<span data-ttu-id="756e6-104">評估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="756e6-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="756e6-105">規劃 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="756e6-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="756e6-106">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="756e6-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="756e6-107">使用率 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="756e6-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="756e6-108">啟動評估</span><span class="sxs-lookup"><span data-stu-id="756e6-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="756e6-109">開始規劃</span><span class="sxs-lookup"><span data-stu-id="756e6-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="756e6-110">您在此處 ！</span><span class="sxs-lookup"><span data-stu-id="756e6-110">You are here!</span></span>  <br/> [<span data-ttu-id="756e6-111">後續步驟</span><span class="sxs-lookup"><span data-stu-id="756e6-111">Next step</span></span>](ocas-session-policies.md) <br/> |[<span data-ttu-id="756e6-112">開始使用</span><span class="sxs-lookup"><span data-stu-id="756e6-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |

<span data-ttu-id="756e6-113">請遵循下列步驟來設定 Office 365 雲端應用程式的安全性設定格式化的條件 Access 應用程式控制項所控制的 Azure AD Office 365 應用程式。</span><span class="sxs-lookup"><span data-stu-id="756e6-113">Follow these steps to configure Azure AD Office 365 apps to be controlled by Office 365 Cloud App Security Conditional Access App Control.</span></span>

<span data-ttu-id="756e6-114">**步驟 1： [建立 Azure AD 條件式存取測試原則](#step-1-create-an-azure-ad-conditional-access-test-policy)**</span><span class="sxs-lookup"><span data-stu-id="756e6-114">**Step 1: [Create an Azure AD conditional access test policy](#step-1-create-an-azure-ad-conditional-access-test-policy)**</span></span>

<span data-ttu-id="756e6-115">**步驟 2： [使用中應用程式的原則範圍內的使用者登入](#step-2-sign-in-with-a-user-scoped-to-the-policy-in-the-apps)**</span><span class="sxs-lookup"><span data-stu-id="756e6-115">**Step 2: [Sign in with a user scoped to the policy in the apps](#step-2-sign-in-with-a-user-scoped-to-the-policy-in-the-apps)**</span></span>

<span data-ttu-id="756e6-116">**步驟 3： 如果您沒有在 Azure AD 中選取的內建的雲端應用程式安全性原則或您想要將原則套用至非精選應用程式 [設定進階的雲端應用程式安全性入口網站中的控制項](#step-3-configure-advanced-controls-in-the-cloud-app-security-portal)**</span><span class="sxs-lookup"><span data-stu-id="756e6-116">**Step 3: If you did not select a built-in Cloud App Security policy in Azure AD or if you want to apply the policy to a non-featured app, [Configure advanced controls in the Cloud App Security portal](#step-3-configure-advanced-controls-in-the-cloud-app-security-portal)**</span></span>

<span data-ttu-id="756e6-117">**步驟 4：[測試部署](#step-4-test-the-deployment)**</span><span class="sxs-lookup"><span data-stu-id="756e6-117">**Step 4: [Test the deployment](#step-4-test-the-deployment)**</span></span>

> [!IMPORTANT]
> <span data-ttu-id="756e6-118">若要部署設定格式化的條件的 Access 應用程式控制項 for Office 365 應用程式，您需要有效 [的 Azure AD Premium P1 授權](https://docs.microsoft.com/azure/active-directory/license-users-groups) 以及 Office 365 雲端應用程式安全性授權。</span><span class="sxs-lookup"><span data-stu-id="756e6-118">To deploy Conditional Access App Control for Office 365 apps, you need a valid [license for Azure AD Premium P1](https://docs.microsoft.com/azure/active-directory/license-users-groups) as well as a Office 365 Cloud App Security license.</span></span>

## <a name="step-1-create-an-azure-ad-conditional-access-test-policy"></a><span data-ttu-id="756e6-119">步驟 1： 建立 Azure AD 條件式存取測試原則</span><span class="sxs-lookup"><span data-stu-id="756e6-119">Step 1: Create an Azure AD conditional access test policy</span></span> 

1. <span data-ttu-id="756e6-120">在 Azure Active Directory、 [ **安全性**] 下按一下 [ **設定格式化的條件**的存取。</span><span class="sxs-lookup"><span data-stu-id="756e6-120">In Azure Active Directory, under **Security**, click on **Conditional access**.</span></span>

2. <span data-ttu-id="756e6-121">按一下 [ **新原則** 並建立新的原則。</span><span class="sxs-lookup"><span data-stu-id="756e6-121">Click **New policy** and create a new policy.</span></span>

3. <span data-ttu-id="756e6-122">在 [測試原則、 **使用者**] 底下指派一個測試使用者或可用於初始登入和驗證的使用者。</span><span class="sxs-lookup"><span data-stu-id="756e6-122">In the TEST policy, under **Users**, assign a test user or user that can be used for an initial sign-on and verification.</span></span>

4. <span data-ttu-id="756e6-123">在測試原則、 **雲端應用程式**中指定您想要的應用程式到控制項具有設定格式化的條件的 Access 應用程式控制項。</span><span class="sxs-lookup"><span data-stu-id="756e6-123">In the TEST policy, under **Cloud app**, assign the apps you want to control with Conditional Access App Control.</span></span>

5. <span data-ttu-id="756e6-p101">[ **工作階段**，將原則設定為使用其中一個內建的原則 **只監視** 或 **封鎖下載**。選取 [ **使用自訂原則**或者 設定進階的原則中的雲端應用程式安全性入口網站。</span><span class="sxs-lookup"><span data-stu-id="756e6-p101">Under **Session**, set the policy to use either of the built-in policies, **Monitor only** or **Block downloads**. Or select **Use custom policy** to set an advanced policy in the Cloud App Security portal.</span></span>

6. <span data-ttu-id="756e6-126">新增任何適用的 **條件指派** 或 **授與控制項** （選用）。</span><span class="sxs-lookup"><span data-stu-id="756e6-126">Add any applicable **Condition assignments** or **Grant controls** (optional).</span></span>

> ![Azure AD 條件式存取](media/image1.png)

## <a name="step-2-sign-in-with-a-user-scoped-to-the-policy-in-the-apps"></a><span data-ttu-id="756e6-128">步驟 2： 使用者登入的範圍設為應用程式中的原則</span><span class="sxs-lookup"><span data-stu-id="756e6-128">Step 2: Sign in with a user scoped to the policy in the apps</span></span> 

<span data-ttu-id="756e6-p102">您已建立原則之後，請登入該原則中設定每個應用程式。請確定您使用登入的原則中設定的使用者。確定至現有的工作階段的第一個正負號。</span><span class="sxs-lookup"><span data-stu-id="756e6-p102">After you've created the policy, sign in to each app configured in that policy. Make sure you sign in using a user configured in the policy. Make sure to first sign out of existing sessions.</span></span>

<span data-ttu-id="756e6-p103">雲端應用程式安全性將同步處理原則的詳細資訊到其伺服器進行登入每個新的應用程式。這可能需要多達一分鐘。</span><span class="sxs-lookup"><span data-stu-id="756e6-p103">Cloud App Security will sync your policy details to its servers for each new app you log in to. This may take up to one minute.</span></span>

## <a name="step-3-configure-advanced-controls-in-the-cloud-app-security-portal"></a><span data-ttu-id="756e6-134">步驟 3： 設定進階的雲端應用程式安全性入口網站中的控制項</span><span class="sxs-lookup"><span data-stu-id="756e6-134">Step 3: Configure advanced controls in the Cloud App Security portal</span></span> 

<span data-ttu-id="756e6-135">上述的指示幫助您建立直接在 Azure AD 的內建的雲端應用程式安全性原則精選的應用程式。</span><span class="sxs-lookup"><span data-stu-id="756e6-135">The instructions above helped you create a built-in Cloud App Security policy for featured apps directly in Azure AD.</span></span>

<span data-ttu-id="756e6-136">若要設定的進階的原則，請建立 [存取原則](ocas-access-policies.md) 或 [工作階段原則](ocas-session-policies.md) Office 365 雲端應用程式安全性入口網站中。</span><span class="sxs-lookup"><span data-stu-id="756e6-136">To configure an advanced policy, create an [access policy](ocas-access-policies.md) or a [session policy](ocas-session-policies.md) in the Office 365 Cloud App Security portal.</span></span>

### <a name="to-identify-devices-using-client-certificates-this-is-optional"></a><span data-ttu-id="756e6-137">識別裝置使用 （這是選用的） 的用戶端憑證：</span><span class="sxs-lookup"><span data-stu-id="756e6-137">To identify devices using client certificates (this is optional):</span></span>

1. <span data-ttu-id="756e6-138">移至 [設定商旅並選擇 [ **裝置識別碼**。</span><span class="sxs-lookup"><span data-stu-id="756e6-138">Go to the settings cog and choose **Device identification**.</span></span>

2. <span data-ttu-id="756e6-139">上傳一或多個根或中繼憑證。</span><span class="sxs-lookup"><span data-stu-id="756e6-139">Upload one or more root or intermediate certificates.</span></span>

3. <span data-ttu-id="756e6-140">憑證上傳之後，您可以建立存取原則及工作階段的原則根據 **裝置標記**及 **有效的用戶端憑證**。</span><span class="sxs-lookup"><span data-stu-id="756e6-140">After the certificate is uploaded, you can create access policies and session policies based on **Device tag** and **Valid client certificate**.</span></span>

![設定格式化的條件的 access 應用程式控制項裝置識別碼](media/image2.png)

> [!NOTE]
> <span data-ttu-id="756e6-142">憑證只是來自使用者要求的工作階段符合使用有效的用戶端憑證篩選器原則。</span><span class="sxs-lookup"><span data-stu-id="756e6-142">A certificate is only requested from a user if the session matches a policy that uses the valid client certificate filter.</span></span>
> 
## <a name="step-4-test-the-deployment"></a><span data-ttu-id="756e6-143">步驟 4： 測試部署</span><span class="sxs-lookup"><span data-stu-id="756e6-143">Step 4: Test the deployment</span></span> 

1. <span data-ttu-id="756e6-p104">先登出任何現有的工作階段。然後，嘗試登入已成功部署每個應用程式。使用 Azure AD 中所設定的原則會比對的使用者登入。</span><span class="sxs-lookup"><span data-stu-id="756e6-p104">First sign out of any existing sessions. Then, try to sign in to each app that was successfully deployed. Sign in using a user that matches the policy configured in Azure AD.</span></span>

2. <span data-ttu-id="756e6-147">雲端應用程式安全性入口網站、 **調查**、 底下選取 [ **活動記錄檔**，並確定登入活動擷取每個應用程式。</span><span class="sxs-lookup"><span data-stu-id="756e6-147">In the Cloud App Security portal, under **Investigate**, select **Activity log**, and make sure the login activities are captured for each app.</span></span>

3. <span data-ttu-id="756e6-148">您可以依序按一下 [ **進階**] 上再使用 **來源相當於 [存取控制**來篩選篩選。</span><span class="sxs-lookup"><span data-stu-id="756e6-148">You can filter by clicking on **Advanced**, and then filtering using **Source equals Access control**.</span></span>

4. <span data-ttu-id="756e6-p105">建議您登入來自 managed 和 unmanaged 裝置的行動電話和桌面應用程式。這是確定活動會適當地擷取活動記錄檔中。若要確認已正確擷取活動，按一下 [單一登入登入活動上以便開啟活動抽屜。請確定 **使用者代理程式標記** 正確反映 [裝置是否 （這表示行動裝置或桌面應用程式） 的原生用戶端或裝置是否在受管理的裝置 （相容，網域加入，或有效的用戶端憑證）。</span><span class="sxs-lookup"><span data-stu-id="756e6-p105">It's recommended that you sign into mobile and desktop apps from managed and unmanaged devices. This is to make sure that the activities are properly captured in the activity log. To verify that the activity is properly captured, click on a single sign-on log on activity so that it opens the activity drawer. Make sure the **User agent tag** properly reflects whether the device is a native client (meaning either a mobile or desktop app) or the device is a managed device (compliant, domain joined, or valid client certificate).</span></span>

> [!NOTE]
> <span data-ttu-id="756e6-p106">部署之後，您無法移除應用程式的 [設定格式化的條件的 Access 應用程式 Control] 頁面。只要您不需要在應用程式設定的工作階段或存取原則，設定格式化的條件的 Access 應用程式控制項將不會變更任何應用程式的行為。</span><span class="sxs-lookup"><span data-stu-id="756e6-p106">After it is deployed, you can't remove an app from the Conditional Access App Control page. As long as you don't set a session or access policy on the app, the Conditional Access App Control won't change any behavior for the app.</span></span>

## <a name="next-steps"></a><span data-ttu-id="756e6-155">後續步驟</span><span class="sxs-lookup"><span data-stu-id="756e6-155">Next steps</span></span>

- [<span data-ttu-id="756e6-156">深入了解 Office 365 雲端應用程式安全性的工作階段原則</span><span class="sxs-lookup"><span data-stu-id="756e6-156">Learn about session policies in Office 365 Cloud App Security</span></span>](ocas-session-policies.md)

- [<span data-ttu-id="756e6-157">深入了解 Office 365 雲端應用程式安全性存取原則</span><span class="sxs-lookup"><span data-stu-id="756e6-157">Learn about access policies in Office 365 Cloud App Security</span></span>](ocas-access-policies.md) 

- [<span data-ttu-id="756e6-158">將您的 IP 位址分組，以簡化 Office 365 雲端 App 安全性中的管理</span><span class="sxs-lookup"><span data-stu-id="756e6-158">Group your IP addresses to simplify management in Office 365 Cloud App Security</span></span>](group-your-ip-addresses-in-ocas.md)