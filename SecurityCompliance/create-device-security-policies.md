---
title: 建立及部署裝置安全性原則
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/9/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.NewDevicePolicy
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: d310f556-8bfb-497b-9bd7-fe3c36ea2fd6
description: '步驟來建立及部署安全性原則行動裝置管理的 Office 365 可協助保護免於未經授權存取 Office 365 組織的資訊。 '
ms.openlocfilehash: ab1fc1960a3e55eb3080dde7df0ec742c58b2cc7
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272068"
---
# <a name="create-and-deploy-device-security-policies"></a><span data-ttu-id="781c2-103">建立及部署裝置安全性原則</span><span class="sxs-lookup"><span data-stu-id="781c2-103">Create and deploy device security policies</span></span>

<span data-ttu-id="781c2-p101">您可以使用行動裝置管理 Office 365 建立協助保護免於未經授權存取您的組織資訊在 Office 365 的安全性原則。您可以將原則套用至任何的行動裝置，其中裝置的使用者具有適用的 Office 365 授權和已註冊 Office 365 中 MDM 裝置在組織中。</span><span class="sxs-lookup"><span data-stu-id="781c2-p101">You can use Mobile Device Management for Office 365 to create security policies that help protect your organization's information on Office 365 from unauthorized access. You can apply policies to any mobile device in your organization where the user of the device has an applicable Office 365 license and has enrolled the device in MDM for Office 365.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="781c2-106">開始之前</span><span class="sxs-lookup"><span data-stu-id="781c2-106">Before you begin</span></span>

- <span data-ttu-id="781c2-p102">了解裝置、 行動裝置應用程式和 Office 365 MDM 支援的安全性設定。請參閱[office 365 的行動裝置管理功能](capabilities-of-mobile-device-management.md)。</span><span class="sxs-lookup"><span data-stu-id="781c2-p102">Learn about the devices, mobile device apps, and security settings that MDM for Office 365 supports. See [Capabilities of Mobile Device Management for Office 365](capabilities-of-mobile-device-management.md).</span></span>
    
- <span data-ttu-id="781c2-p103">建立包含您想要部署的原則的 Office 365 使用者的安全性群組與使用者您可能會想要排除在所封鎖的 Office 365 的存取。建議您為組織部署新的原則之前，測試將原則部署至少數使用者。您可以建立並使用包含剛自行或小型數字 Office 365 的使用者可以測試之原則的安全性群組。若要深入了解安全性群組，請參閱[建立、 編輯或刪除安全性群組](https://go.microsoft.com/fwlink/p/?LinkId=518555)。</span><span class="sxs-lookup"><span data-stu-id="781c2-p103">Create security groups that include Office 365 users that you want to deploy policies to and for users that you might want to exclude from being blocked access to Office 365. We recommend that before you deploy a new policy to your organization, you test the policy by deploying it to a small number of users. You can create and use a security group that includes just yourself or a small number Office 365 users that can test the policy for you. To learn more about security groups, see [Create, edit, or delete a security group](https://go.microsoft.com/fwlink/p/?LinkId=518555).</span></span>
    
- <span data-ttu-id="781c2-p104">**重要：** 您可以建立行動裝置原則之前，您必須啟動及設定 MDM for Office 365。請參閱[office 365 的行動裝置管理的概觀](overview-of-mdm.md)。</span><span class="sxs-lookup"><span data-stu-id="781c2-p104">**Important:** Before you can create a mobile device policy, you must activate and set up MDM for Office 365. See [Overview of Mobile Device Management for Office 365](overview-of-mdm.md).</span></span>
    
- <span data-ttu-id="781c2-115">若要建立及部署 Office 365 中的行動裝置管理原則，您必須是 Office 365 全域管理]。請參閱[中的 Office 365 安全性權限&amp;規範中心](https://support.office.com/article/d10608af-7934-490a-818e-e68f17d0e9c1)。</span><span class="sxs-lookup"><span data-stu-id="781c2-115">To create and deploy mobile device management policies in Office 365, you need to be an Office 365 global admin. See [Permissions in the Office 365 Security &amp; Compliance Center](https://support.office.com/article/d10608af-7934-490a-818e-e68f17d0e9c1).</span></span>
    
- <span data-ttu-id="781c2-p105">在部署原則之前，可讓您知道 MDM 的裝置註冊 Office 365 的潛在影響的組織。根據您如何設定原則，不相容的裝置存取 Office 365 也會遭到封鎖，並刪除資料，包括已安裝應用程式、 照片和註冊的裝置上的個人資訊。</span><span class="sxs-lookup"><span data-stu-id="781c2-p105">Before you deploy policies, let your organization know the potential impacts of enrolling a device in MDM for Office 365. Depending on how you set up the policies, noncompliant devices can be blocked from accessing Office 365 and data, including installed applications, photos, and personal information on an enrolled device, can be deleted.</span></span>
    
> [!NOTE]
> <span data-ttu-id="781c2-p106">Exchange ActiveSync 行動裝置信箱原則和裝置存取規則在 Exchange 系統管理中心中建立的原則和 MDM 中建立的 Office 365 的存取規則會覆寫。裝置在 MDM 中註冊 Office 365 之後，都會被忽略任何 Exchange ActiveSync 行動裝置信箱原則 」 或 「 裝置存取規則套用至裝置。若要深入了解 Exchange ActiveSync，請參閱[Exchange Online 中的 Exchange ActiveSync](https://go.microsoft.com/fwlink/p/?LinkId=524380)。</span><span class="sxs-lookup"><span data-stu-id="781c2-p106">Policies and access rules created in MDM for Office 365 will override Exchange ActiveSync mobile device mailbox policies and device access rules created in the Exchange admin center. After a device is enrolled in MDM for Office 365, any Exchange ActiveSync mobile device mailbox policy or device access rule applied to the device will be ignored. To learn more about Exchange ActiveSync, see [Exchange ActiveSync in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=524380).</span></span> 
  
## <a name="step-1-create-a-security-policy-and-deploy-to-a-test-group"></a><span data-ttu-id="781c2-121">步驟 1： 建立安全性原則和部署至測試群組</span><span class="sxs-lookup"><span data-stu-id="781c2-121">Step 1: Create a security policy and deploy to a test group</span></span>

<span data-ttu-id="781c2-p107">您可以啟動之前，請確定已啟動並設定 Office 365 MDM。請參閱[概觀 （英文） 的行動裝置管理 Office 365](overview-of-mdm.md)的指示。</span><span class="sxs-lookup"><span data-stu-id="781c2-p107">Before you can start, make sure you have activated and set up MDM for Office 365. See [Overview of Mobile Device Management for Office 365](overview-of-mdm.md) for instructions.</span></span> 
  
1. <span data-ttu-id="781c2-124">在 [安全性] 中的 Office 365 中&amp;規範管理中心，移至 [**資料外洩防護** \> **裝置安全性原則**。</span><span class="sxs-lookup"><span data-stu-id="781c2-124">In Office 365, in the Security &amp; Compliance Center, go to **Data loss prevention** \> **Device security policies**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="781c2-125">僅之後已啟動行動裝置管理**裝置安全性原則**會出現的功能表中。</span><span class="sxs-lookup"><span data-stu-id="781c2-125">The **Device security policies** will appear in the menu only after you have activated Mobile device management.</span></span> 
  
2. <span data-ttu-id="781c2-126">選擇 [ **+ 建立原則**。</span><span class="sxs-lookup"><span data-stu-id="781c2-126">Choose **+ Create a policy**.</span></span>
    
    ![建立裝置安全性原則] 下的 MDN 裝置原則](media/fbcdbecd-0016-42f1-81a9-9fbad610da90.png)
  
3. <span data-ttu-id="781c2-128">指定新原則的**名稱**和**描述**，然後選擇 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="781c2-128">Specify a **Name** and **Description** for the new policy, and then choose **Next**.</span></span>
    
    ![設定裝置安全性原則的名稱](media/d382e845-4a7f-4f72-8a09-813ea4cbd0c4.png)
  
4. <span data-ttu-id="781c2-130">在**您要在裝置上有哪些需求？** ] 頁面上，指定您想要套用至行動裝置在您的組織中的需求，然後選擇 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="781c2-130">On the **What requirements do you want to have on devices?** page, specify the requirements you want applied to mobile devices in your organization, and then choose **Next**.</span></span>
    
    ![[設定] 頁面上的裝置安全性原則](media/186b3bd5-5e3d-4059-978f-94113111a8ca.png)
  
5. <span data-ttu-id="781c2-132">在**您想要設定吗？** ] 頁面上，指定您想要套用至行動裝置在您的組織中任何其他需求，然後選擇 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="781c2-132">On the **What do you want to configure?** page, specify any additional requirements you want applied to mobile devices in your organization, and then choose **Next**.</span></span>
    
6. <span data-ttu-id="781c2-133">在**您想要立即套用此原則吗？** ] 頁面上，並選擇 [ **]**，然後選擇 [ **+ 新增**。</span><span class="sxs-lookup"><span data-stu-id="781c2-133">On the **Do you want to apply this policy now?** page, choose **Yes**, and then choose **+ Add**.</span></span> 
    
    ![新增原則](media/89ab7cab-1b7a-4c78-9aa6-3db7d7667f8e.png)
  
7. <span data-ttu-id="781c2-135">選取 [將其部署至您的組織與然後選擇 [**新增**之前測試其原則的群組。</span><span class="sxs-lookup"><span data-stu-id="781c2-135">Select the group(s) who will test the policy before you deploy it to your organization, and then choose **Add**.</span></span>
    
8. <span data-ttu-id="781c2-136">選擇 [下一步]****。</span><span class="sxs-lookup"><span data-stu-id="781c2-136">Choose **Next**.</span></span>
    
9. <span data-ttu-id="781c2-137">檢閱並確認新的裝置原則的詳細資訊，然後選擇**建立此原則**。</span><span class="sxs-lookup"><span data-stu-id="781c2-137">Review and confirm the details of the new device policy, and then choose **Create this policy**.</span></span>
    
    ![選擇 [建立此原則以完成建立裝置原則](media/e410bcf3-8a36-44ed-9fea-00e742db06fb.png)
  
10. <span data-ttu-id="781c2-139">按一下 [關閉]****。</span><span class="sxs-lookup"><span data-stu-id="781c2-139">Click **Close**.</span></span>
    
<span data-ttu-id="781c2-p108">原則可套用至每位使用者必須推送至使用者的裝置在下次登入 Office 365 使用使用者的行動裝置的原則。如果使用者尚未套用至使用者的行動裝置之前的原則，然後部署原則之後他們會得到通知包括[步驟註冊並啟動 Office 365 MDM](https://go.microsoft.com/fwlink/?LinkId=615272)其裝置上。直到完成註冊，存取權的電子郵件、 OneDrive 及其他服務將會受限。完成註冊使用 Intune 的公司入口網站應用程式之後，他們必須能夠使用的服務與原則將會套用至使用者的裝置。</span><span class="sxs-lookup"><span data-stu-id="781c2-p108">Each user that the policy applies to will have the policy pushed to their device the next time they sign in to Office 365 using their mobile device. If users haven't had a policy applied to their mobile device before, then after you deploy the policy, they'll get a notification on their device that includes the [steps to enroll and activate MDM for Office 365](https://go.microsoft.com/fwlink/?LinkId=615272). Until they complete enrollment, access to email, OneDrive, and other services will be restricted. After they complete enrollment using the Intune Company Portal app, they'll be able to use the services and the policy will be applied to their device.</span></span>
  
## <a name="step-2-verify-your-policy-works"></a><span data-ttu-id="781c2-144">步驟 2： 確認您的原則運作</span><span class="sxs-lookup"><span data-stu-id="781c2-144">Step 2: Verify your policy works</span></span>

<span data-ttu-id="781c2-145">您已建立的安全性原則之後，就應該檢查原則運作如預期般部署至組織之前。</span><span class="sxs-lookup"><span data-stu-id="781c2-145">After you've created a security policy, you should check that the policy works as you expect before you deploy it to your organization.</span></span>
  
1. <span data-ttu-id="781c2-146">在 Office 365 中，移至**安全性&amp;規範中心** \> **資料外洩防護** \> **裝置管理**。</span><span class="sxs-lookup"><span data-stu-id="781c2-146">In Office 365, go to **Security &amp; Compliance Center** \> **Data loss prevention** \> **Device management**.</span></span>
    
2. <span data-ttu-id="781c2-p109">在**Office 365 的行動裝置管理**] 頁面上，勾選 [已套用原則的使用者裝置的狀態。您可以篩選或排序的**所有**檢視所有的裝置或**封鎖**檢視封鎖的裝置。</span><span class="sxs-lookup"><span data-stu-id="781c2-p109">On the **Mobile Device Management for Office 365** page, Check the status of user devices that have the policy applied. You can filter or sort by **All** to view all devices, or **Blocked** to view blocked devices.</span></span> 
    
    ![檢視受 MDM 裝置](media/5c9fd069-b716-40d8-9b36-f9cfeae2139f.png)
  
3. <span data-ttu-id="781c2-p110">您也可以執行完整或選擇性的抹除裝置上。指示，請參閱[Office 365 的行動裝置](wipe-a-mobile-device.md)。</span><span class="sxs-lookup"><span data-stu-id="781c2-p110">You can also do a full or selective wipe on the device. For instructions, see [Wipe a mobile device in Office 365](wipe-a-mobile-device.md).</span></span>
    
## <a name="step-3-deploy-a-policy-to-your-organization"></a><span data-ttu-id="781c2-152">步驟 3： 部署至您的組織的原則</span><span class="sxs-lookup"><span data-stu-id="781c2-152">Step 3: Deploy a policy to your organization</span></span>

<span data-ttu-id="781c2-153">您已建立的行動裝置原則並確認其運作如預期般運作後，則會部署至您的組織。</span><span class="sxs-lookup"><span data-stu-id="781c2-153">After you've created a mobile device policy and verified that it works as expected, deploy it to your organization.</span></span>
  
1. <span data-ttu-id="781c2-154">在 Office 365 中，移至**安全性&amp;規範中心** \> **資料外洩防護**\> **裝置安全性原則**。</span><span class="sxs-lookup"><span data-stu-id="781c2-154">In Office 365, go to **Security &amp; Compliance Center** \> **Data loss prevention**\> **Device security policies**.</span></span>
    
2. <span data-ttu-id="781c2-155">選取您想要部署的原則和選擇中的 [**編輯原則** \<_原則名稱_\>面板。  </span><span class="sxs-lookup"><span data-stu-id="781c2-155">Select the policy you want to deploy, and choose **Edit policy** in the \<  _policy name_\> panel.</span></span>
    
3. <span data-ttu-id="781c2-156">選取 **[部署]** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="781c2-156">Select the **Deployment** tab.</span></span> 
    
4. <span data-ttu-id="781c2-157">在 [**部署**] 索引標籤中選擇 [**是**上方**選取下列其中一個或多個安全性群組且包含您要套用此原則的人員**] 與 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="781c2-157">In the **Deployment** tab, choose **Yes** above **Select one or more security groups that contain the people you want to apply this policy to** and then **Add**.</span></span>
    
  - <span data-ttu-id="781c2-p111">在 [**選取群組**] 面板中，您可以搜尋要新增的群組，您可以當做篩選依據別名或顯示名稱。您也可以從 [**群組**] 清單中新增的現有群組。</span><span class="sxs-lookup"><span data-stu-id="781c2-p111">On the **Select Group** panel, you can search for a group to add, you can filter either by alias or by display name. You can also add an existing group from the **Groups** list.</span></span> 
    
    <span data-ttu-id="781c2-160">您可以新增要套用之原則的多個群組。</span><span class="sxs-lookup"><span data-stu-id="781c2-160">You can add multiple groups to apply the policy to.</span></span>
    
    <span data-ttu-id="781c2-161">選擇 [控制台] 之底部上的 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="781c2-161">Choose **Add** on the bottom of the panel.</span></span> 
    
5. <span data-ttu-id="781c2-162">[**部署**] 索引標籤上選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="781c2-162">Choose **Save** on the **Deployment** tab.</span></span> 
    
    ![為組織部署 MDM 原則。](media/dc3e7fe5-201a-4e45-abe3-fc93e0b59028.png)
  
<span data-ttu-id="781c2-p112">原則可套用至每位使用者必須推送至使用者的裝置在下次登入 Office 365 從使用者的行動裝置的原則。如果使用者尚未套用至使用者的行動裝置的原則，其將註冊並針對 MDM 啟動 Office 365 步驟[要取得其裝置上的通知](https://go.microsoft.com/fwlink/?LinkId=615272)。他們在註冊完成後，該原則會套用至使用者的裝置。</span><span class="sxs-lookup"><span data-stu-id="781c2-p112">Each user that the policy applies to will have the policy pushed to their device the next time they sign in to Office 365 from their mobile device. If users haven't had a policy applied to their mobile device, they'll [get a notification on their device](https://go.microsoft.com/fwlink/?LinkId=615272) with steps to enroll and activate it for MDM for Office 365. After they've completed the enrollment, the policy will be applied to their device.</span></span> 
  
## <a name="step-4-block-email-access-for-unsupported-devices"></a><span data-ttu-id="781c2-167">步驟 4： 封鎖存取電子郵件不受支援的裝置</span><span class="sxs-lookup"><span data-stu-id="781c2-167">Step 4: Block email access for unsupported devices</span></span>

<span data-ttu-id="781c2-p113">為了安全貴組織的資訊，您應封鎖不支援 MDM for Office 365 的行動裝置的 Office 365 電子郵件應用程式存取。請參閱[Office 365 的內建行動裝置管理功能](capabilities-of-mobile-device-management.md)所支援的裝置清單。若要執行這項作業：</span><span class="sxs-lookup"><span data-stu-id="781c2-p113">To help secure your organization's information, you should block app access to Office 365 email for mobile devices that are not supported by MDM for Office 365. See [Capabilities of built-in Mobile Device Management for Office 365](capabilities-of-mobile-device-management.md) for a list of devices that are supported. To do this:</span></span> 
  
1. <span data-ttu-id="781c2-171">移至 [安全性&amp;規範中心\>**資料外洩防護**\> **裝置安全性原則**。</span><span class="sxs-lookup"><span data-stu-id="781c2-171">Go to Security &amp; Compliance Center\> **Data loss prevention**\> **Device security policies**.</span></span>
    
2. <span data-ttu-id="781c2-172">選取 [**管理整個組織的裝置存取設定**。</span><span class="sxs-lookup"><span data-stu-id="781c2-172">Select **Manage organization-wide device access settings**.</span></span>
    
    ![移至 [規範中心\>裝置並按一下 [管理裝置存取設定連結。](media/b9f4da3c-dfa5-4913-8482-42a077cb4f56.png)
  
3. <span data-ttu-id="781c2-174">若要封鎖不受支援的裝置，請選擇 [**封鎖**下**如果裝置不受支援的 Office 365 MDM 執行您想要允許或封鎖它無法使用 Exchange 帳戶以存取貴組織的電子郵件** \> **儲存**。</span><span class="sxs-lookup"><span data-stu-id="781c2-174">To block unsupported devices, choose **Block** under **If a device isn't supported by MDM for Office 365, do you want to allow or block it from using an Exchange account to access your organization's email** \> **Save**.</span></span>
  
## <a name="step-5-choose-security-groups-to-be-excluded-from-conditional-access-checks"></a><span data-ttu-id="781c2-175">步驟 5：選擇不要進行條件存取檢查的安全性群組</span><span class="sxs-lookup"><span data-stu-id="781c2-175">Step 5: Choose security groups to be excluded from conditional access checks</span></span>

<span data-ttu-id="781c2-p114">如果您不想某些人在他們的行動裝置上進行條件存取檢查，且您已經針對這些人建立一或多個安全性群組，請在此新增安全性群組。系統不會針對這些群組中的人，強制在他們支援的行動裝置上執行任何原則。</span><span class="sxs-lookup"><span data-stu-id="781c2-p114">If you want to exclude some people from conditional access checks on their mobile devices and you've created one or more security groups for those people, add the security groups here. The people in these groups will not have any policies enforced for their supported mobile devices.</span></span>
  
1. <span data-ttu-id="781c2-178">移至 [安全性&amp;規範中心\>**資料外洩防護**\> **裝置安全性原則**。</span><span class="sxs-lookup"><span data-stu-id="781c2-178">Go to Security &amp; Compliance Center\> **Data loss prevention**\> **Device security policies**.</span></span>
    
2. <span data-ttu-id="781c2-179">選取 [**管理整個組織的裝置存取設定**。</span><span class="sxs-lookup"><span data-stu-id="781c2-179">Select **Manage organization-wide device access settings**.</span></span>
    
    ![移至 [規範中心\>裝置並按一下 [管理裝置存取設定連結。](media/b9f4da3c-dfa5-4913-8482-42a077cb4f56.png)
  
3. <span data-ttu-id="781c2-p115">選取 [**新增**] 以新增 [安全性] 群組具有您想要從要排除的使用者封鎖至 Office 365 的存取。當使用者已新增至這份清單中時，他們必須能夠存取 Office 365 電子郵件時使用不受支援的裝置。</span><span class="sxs-lookup"><span data-stu-id="781c2-p115">Select **Add** to add the security group that has users that you'd like to exclude from being blocked access to Office 365. When a user has been added to this list, they'll be able to access Office 365 email when using an unsupported device.</span></span> 
    
4. <span data-ttu-id="781c2-183">選取您想要使用 [**選取群組**] 面板中的 [安全性] 群組。</span><span class="sxs-lookup"><span data-stu-id="781c2-183">Select the security group you want to use in the **Select group** panel.</span></span> 
    
5. <span data-ttu-id="781c2-184">選取 [名稱] 中，然後**新增** \> **儲存**。</span><span class="sxs-lookup"><span data-stu-id="781c2-184">Select the name, and then **Add** \> **Save**.</span></span>
    
6. <span data-ttu-id="781c2-185">在**整個組織的裝置存取設定**] 面板中，選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="781c2-185">On the **Organization-wide device access settings** panel, choose **Save**.</span></span>
  
## <a name="what-is-the-impact-of-security-policies-on-different-device-types"></a><span data-ttu-id="781c2-186">安全性原則對於不同的裝置類型有何影響？</span><span class="sxs-lookup"><span data-stu-id="781c2-186">What is the impact of security policies on different device types?</span></span>

<span data-ttu-id="781c2-p116">當您將原則套用至使用者裝置時，每個裝置所受到的影響會隨著裝置類型而有所不同。請參閱下表中的範例，瞭解原則對於不同裝置的影響。</span><span class="sxs-lookup"><span data-stu-id="781c2-p116">When you apply a policy to user devices, the impact on each device varies somewhat between different device types. See the following table for examples of the impact of policies on different devices.</span></span>
  


|<span data-ttu-id="781c2-189">**安全性原則**</span><span class="sxs-lookup"><span data-stu-id="781c2-189">**Security Policy**</span></span>|<span data-ttu-id="781c2-190">**Windows Phone 8.1 +**</span><span class="sxs-lookup"><span data-stu-id="781c2-190">**Windows Phone 8.1+**</span></span>|<span data-ttu-id="781c2-191">**Android 4+**</span><span class="sxs-lookup"><span data-stu-id="781c2-191">**Android 4+**</span></span>|<span data-ttu-id="781c2-192">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="781c2-192">**Samsung Knox**</span></span>|<span data-ttu-id="781c2-193">**IOS 6 +**</span><span class="sxs-lookup"><span data-stu-id="781c2-193">**IOS 6+**</span></span>|<span data-ttu-id="781c2-194">**附註**</span><span class="sxs-lookup"><span data-stu-id="781c2-194">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="781c2-195">需要加密備份</span><span class="sxs-lookup"><span data-stu-id="781c2-195">Require encrypted backup</span></span>  <br/> |<span data-ttu-id="781c2-196">✖</span><span class="sxs-lookup"><span data-stu-id="781c2-196">✖</span></span>  <br/> |<span data-ttu-id="781c2-197">✖</span><span class="sxs-lookup"><span data-stu-id="781c2-197">✖</span></span>  <br/> |<span data-ttu-id="781c2-198">✔</span><span class="sxs-lookup"><span data-stu-id="781c2-198">✔</span></span>  <br/> |<span data-ttu-id="781c2-199">✔</span><span class="sxs-lookup"><span data-stu-id="781c2-199">✔</span></span>  <br/> |<span data-ttu-id="781c2-200">需要 IOS 加密備份。</span><span class="sxs-lookup"><span data-stu-id="781c2-200">IOS encrypted backup required.</span></span>  <br/> |
|<span data-ttu-id="781c2-201">封鎖雲端備份</span><span class="sxs-lookup"><span data-stu-id="781c2-201">Block cloud backup</span></span>  <br/> |<span data-ttu-id="781c2-202">✖</span><span class="sxs-lookup"><span data-stu-id="781c2-202">✖</span></span>  <br/> |<span data-ttu-id="781c2-203">✔</span><span class="sxs-lookup"><span data-stu-id="781c2-203">✔</span></span>  <br/> |<span data-ttu-id="781c2-204">✔</span><span class="sxs-lookup"><span data-stu-id="781c2-204">✔</span></span>  <br/> |<span data-ttu-id="781c2-205">✔</span><span class="sxs-lookup"><span data-stu-id="781c2-205">✔</span></span>  <br/> |<span data-ttu-id="781c2-206">封鎖 Android 上的 Google 備份 (呈現灰色)、iOS 上的雲端備份。</span><span class="sxs-lookup"><span data-stu-id="781c2-206">Block Google backup on Android (grayed out), cloud backup on iOS.</span></span>  <br/> |
|<span data-ttu-id="781c2-207">封鎖文件同步處理</span><span class="sxs-lookup"><span data-stu-id="781c2-207">Block document synchronization</span></span>  <br/> |<span data-ttu-id="781c2-208">✖</span><span class="sxs-lookup"><span data-stu-id="781c2-208">✖</span></span>  <br/> |<span data-ttu-id="781c2-209">✖</span><span class="sxs-lookup"><span data-stu-id="781c2-209">✖</span></span>  <br/> |<span data-ttu-id="781c2-210">✖</span><span class="sxs-lookup"><span data-stu-id="781c2-210">✖</span></span>  <br/> |<span data-ttu-id="781c2-211">✔</span><span class="sxs-lookup"><span data-stu-id="781c2-211">✔</span></span>  <br/> |<span data-ttu-id="781c2-212">iOS：封鎖雲端中的文件。</span><span class="sxs-lookup"><span data-stu-id="781c2-212">iOS: Block documents in the cloud.</span></span>  <br/> |
|<span data-ttu-id="781c2-213">封鎖相片同步處理</span><span class="sxs-lookup"><span data-stu-id="781c2-213">Block photo synchronization</span></span>  <br/> |<span data-ttu-id="781c2-214">✖</span><span class="sxs-lookup"><span data-stu-id="781c2-214">✖</span></span>  <br/> |<span data-ttu-id="781c2-215">✖</span><span class="sxs-lookup"><span data-stu-id="781c2-215">✖</span></span>  <br/> |<span data-ttu-id="781c2-216">✖</span><span class="sxs-lookup"><span data-stu-id="781c2-216">✖</span></span>  <br/> |<span data-ttu-id="781c2-217">✔</span><span class="sxs-lookup"><span data-stu-id="781c2-217">✔</span></span>  <br/> |<span data-ttu-id="781c2-218">iOS (原生)：封鎖相片串流。</span><span class="sxs-lookup"><span data-stu-id="781c2-218">iOS (native): Block Photo Stream.</span></span>  <br/> |
|<span data-ttu-id="781c2-219">封鎖螢幕擷取畫面</span><span class="sxs-lookup"><span data-stu-id="781c2-219">Block screen capture</span></span>  <br/> |<span data-ttu-id="781c2-220">✔</span><span class="sxs-lookup"><span data-stu-id="781c2-220">✔</span></span>  <br/> |<span data-ttu-id="781c2-221">X</span><span class="sxs-lookup"><span data-stu-id="781c2-221">X</span></span>  <br/> |<span data-ttu-id="781c2-222">✔</span><span class="sxs-lookup"><span data-stu-id="781c2-222">✔</span></span>  <br/> |<span data-ttu-id="781c2-223">✔</span><span class="sxs-lookup"><span data-stu-id="781c2-223">✔</span></span>  <br/> |<span data-ttu-id="781c2-224">在嘗試時遭封鎖。</span><span class="sxs-lookup"><span data-stu-id="781c2-224">Blocked when attempted.</span></span>  <br/> |
|<span data-ttu-id="781c2-225">封鎖視訊會議</span><span class="sxs-lookup"><span data-stu-id="781c2-225">Block video conference</span></span>  <br/> |<span data-ttu-id="781c2-226">✖</span><span class="sxs-lookup"><span data-stu-id="781c2-226">✖</span></span>  <br/> |<span data-ttu-id="781c2-227">✖</span><span class="sxs-lookup"><span data-stu-id="781c2-227">✖</span></span>  <br/> |<span data-ttu-id="781c2-228">✖</span><span class="sxs-lookup"><span data-stu-id="781c2-228">✖</span></span>  <br/> |<span data-ttu-id="781c2-229">✔</span><span class="sxs-lookup"><span data-stu-id="781c2-229">✔</span></span>  <br/> |<span data-ttu-id="781c2-230">FaceTime 在 iOS 上遭封鎖，Skype 或其他項目則否。</span><span class="sxs-lookup"><span data-stu-id="781c2-230">FaceTime blocked on iOS, not Skype or others.</span></span>  <br/> |
|<span data-ttu-id="781c2-231">封鎖診斷資料的傳送</span><span class="sxs-lookup"><span data-stu-id="781c2-231">Block sending diagnostic data</span></span>  <br/> |<span data-ttu-id="781c2-232">✖</span><span class="sxs-lookup"><span data-stu-id="781c2-232">✖</span></span>  <br/> |<span data-ttu-id="781c2-233">X</span><span class="sxs-lookup"><span data-stu-id="781c2-233">X</span></span>  <br/> |<span data-ttu-id="781c2-234">✔</span><span class="sxs-lookup"><span data-stu-id="781c2-234">✔</span></span>  <br/> |<span data-ttu-id="781c2-235">✔</span><span class="sxs-lookup"><span data-stu-id="781c2-235">✔</span></span>  <br/> |<span data-ttu-id="781c2-236">在 Android 上封鎖 Google 當機報告的傳送。</span><span class="sxs-lookup"><span data-stu-id="781c2-236">Block sending Google crash report on Android.</span></span>  <br/> |
|<span data-ttu-id="781c2-237">封鎖對應用程式市集的存取</span><span class="sxs-lookup"><span data-stu-id="781c2-237">Block access to app store</span></span>  <br/> |<span data-ttu-id="781c2-238">✔</span><span class="sxs-lookup"><span data-stu-id="781c2-238">✔</span></span>  <br/> |<span data-ttu-id="781c2-239">X</span><span class="sxs-lookup"><span data-stu-id="781c2-239">X</span></span>  <br/> |<span data-ttu-id="781c2-240">✔</span><span class="sxs-lookup"><span data-stu-id="781c2-240">✔</span></span>  <br/> |<span data-ttu-id="781c2-241">✔</span><span class="sxs-lookup"><span data-stu-id="781c2-241">✔</span></span>  <br/> |<span data-ttu-id="781c2-242">應用程式市集圖示未出現在 Android 首頁上、在 Windows 上停用、在 iOS 上未顯示。</span><span class="sxs-lookup"><span data-stu-id="781c2-242">App store icon missing on Android home page, disabled on Windows, missing on iOS.</span></span>  <br/> |
|<span data-ttu-id="781c2-243">應用程式市集需要密碼</span><span class="sxs-lookup"><span data-stu-id="781c2-243">Require password for app store</span></span>  <br/> |<span data-ttu-id="781c2-244">✖</span><span class="sxs-lookup"><span data-stu-id="781c2-244">✖</span></span>  <br/> |<span data-ttu-id="781c2-245">✖</span><span class="sxs-lookup"><span data-stu-id="781c2-245">✖</span></span>  <br/> |<span data-ttu-id="781c2-246">✖</span><span class="sxs-lookup"><span data-stu-id="781c2-246">✖</span></span>  <br/> |<span data-ttu-id="781c2-247">✔</span><span class="sxs-lookup"><span data-stu-id="781c2-247">✔</span></span>  <br/> |<span data-ttu-id="781c2-248">iOS：ITunes 購物需要密碼。</span><span class="sxs-lookup"><span data-stu-id="781c2-248">iOS: Password required for iTunes purchases.</span></span>  <br/> |
|<span data-ttu-id="781c2-249">封鎖卸除式存放裝置的連線</span><span class="sxs-lookup"><span data-stu-id="781c2-249">Block connection to removable storage</span></span>  <br/> |<span data-ttu-id="781c2-250">✔</span><span class="sxs-lookup"><span data-stu-id="781c2-250">✔</span></span>  <br/> |<span data-ttu-id="781c2-251">X</span><span class="sxs-lookup"><span data-stu-id="781c2-251">X</span></span>  <br/> |<span data-ttu-id="781c2-252">✔</span><span class="sxs-lookup"><span data-stu-id="781c2-252">✔</span></span>  <br/> |<span data-ttu-id="781c2-253">NA</span><span class="sxs-lookup"><span data-stu-id="781c2-253">NA</span></span>  <br/> |<span data-ttu-id="781c2-254">Android：SD 記憶卡在 [設定] 中會呈現為灰色，Windows 會通知使用者該處安裝的應用程式無法使用</span><span class="sxs-lookup"><span data-stu-id="781c2-254">Android: SD card will be grayed out in settings, Windows notifies user, apps installed there are not available</span></span>  <br/> |
|<span data-ttu-id="781c2-255">封鎖藍芽連線</span><span class="sxs-lookup"><span data-stu-id="781c2-255">Block Bluetooth connection</span></span>  <br/> |<span data-ttu-id="781c2-256">✔</span><span class="sxs-lookup"><span data-stu-id="781c2-256">✔</span></span>  <br/> |\*\*\*  <br/> |\*\*\*  <br/> |<span data-ttu-id="781c2-257">✖</span><span class="sxs-lookup"><span data-stu-id="781c2-257">✖</span></span>  <br/> |<span data-ttu-id="781c2-p117">\*\*\*我們不能作為在 android （英文） 上的設定來停用 BlueTooth。我們停用需要 BlueTooth 的所有交易的而： 進階音訊通訊、 音訊/視訊遠端控制、 免手持裝置、 耳機、 電話簿存取及序列連接埠。使用任何以上時小型吐司訊息就會出現在頁面底部。</span><span class="sxs-lookup"><span data-stu-id="781c2-p117">\*\*\*We can't disable BlueTooth as a setting on Android. Instead, we disable all the transactions that require BlueTooth: Advanced Audio Distribution, Audio/Video Remote Control, hands-free devices, headset, Phone Book Access, and Serial Port. A small toast message appears at the bottom of the page when any of these are used.</span></span>  <br/> |
   
## <a name="what-happens-when-you-delete-a-policy-or-remove-a-user-from-the-policy"></a><span data-ttu-id="781c2-261">當您刪除原則或從原則中移除使用者時，會發生什麼情況？</span><span class="sxs-lookup"><span data-stu-id="781c2-261">What happens when you delete a policy or remove a user from the policy?</span></span>

<span data-ttu-id="781c2-p118">當您刪除原則或移除的原則已部署至群組中的使用者時，從使用者的裝置可能會移除原則設定、 Office 365 電子郵件設定檔及快取的電子郵件。請參閱下表來查看功能已移除對於不同的裝置類型：</span><span class="sxs-lookup"><span data-stu-id="781c2-p118">When you delete a policy or remove a user from a group to which the policy was deployed to, the policy settings, Office 365 email profile and cached emails may be removed from the user's device. See the following table to see what is removed for the different device types:</span></span>
  
|<span data-ttu-id="781c2-264">**移除的項目**</span><span class="sxs-lookup"><span data-stu-id="781c2-264">**What's removed**</span></span>|<span data-ttu-id="781c2-265">**Windows Phone 8.1 +**</span><span class="sxs-lookup"><span data-stu-id="781c2-265">**Windows Phone 8.1+**</span></span>|<span data-ttu-id="781c2-266">**iOS 6 +**</span><span class="sxs-lookup"><span data-stu-id="781c2-266">**iOS 6+**</span></span>|<span data-ttu-id="781c2-267">**Android 4 + （包括 Samsung Knox）**</span><span class="sxs-lookup"><span data-stu-id="781c2-267">**Android 4+ (including Samsung Knox)**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="781c2-268">受管理的電子郵件設定檔\*</span><span class="sxs-lookup"><span data-stu-id="781c2-268">Managed email profiles\*</span></span>  <br/> |<span data-ttu-id="781c2-269">✖</span><span class="sxs-lookup"><span data-stu-id="781c2-269">✖</span></span>  <br/> |<span data-ttu-id="781c2-270">✔</span><span class="sxs-lookup"><span data-stu-id="781c2-270">✔</span></span>  <br/> |<span data-ttu-id="781c2-271">✖</span><span class="sxs-lookup"><span data-stu-id="781c2-271">✖</span></span>  <br/> |
|<span data-ttu-id="781c2-272">原則設定</span><span class="sxs-lookup"><span data-stu-id="781c2-272">Policy settings</span></span>  <br/> |<span data-ttu-id="781c2-273">✔</span><span class="sxs-lookup"><span data-stu-id="781c2-273">✔</span></span>  <br/>           <span data-ttu-id="781c2-274">**[封鎖裝置傳送診斷資料]** 除外。</span><span class="sxs-lookup"><span data-stu-id="781c2-274">Except for **Block sending diagnostic data from device.**</span></span> <br/> |<span data-ttu-id="781c2-275">✔</span><span class="sxs-lookup"><span data-stu-id="781c2-275">✔</span></span>  <br/> |<span data-ttu-id="781c2-276">✖</span><span class="sxs-lookup"><span data-stu-id="781c2-276">✖</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="781c2-277">\*如果原則已部署選項與**受管理的電子郵件設定檔**] 選取受管理的電子郵件設定檔並於該設定檔將會從使用者的裝置刪除快取電子郵件。</span><span class="sxs-lookup"><span data-stu-id="781c2-277">\*If the policy was deployed with the option **Email profile is managed** selected, then the managed email profile and cached emails in that profile will be deleted from the user's device.</span></span> 
  
<span data-ttu-id="781c2-p119">已移除的原則套用至每位使用者必須從使用者的裝置中移除使用者的行動裝置使用 MDM 檢查 Office 365 的下一次的原則。如果您要部署新的原則套用至這些使用者的裝置，其將提示您重新註冊 Office 365 的 [在 MDM。</span><span class="sxs-lookup"><span data-stu-id="781c2-p119">Each user that the removed policy applied to will have the policy removed from their device the next time their mobile device checks in with MDM for Office 365 . If you deploy a new policy that applies to these users' devices, they'll be prompted to re-enroll in MDM for Office 365.</span></span>
  
<span data-ttu-id="781c2-280">您也可以[裝置](wipe-a-mobile-device.md)、 其中一個完全，或選擇性地清除之裝置的組織資訊。</span><span class="sxs-lookup"><span data-stu-id="781c2-280">You can also [wipe a device](wipe-a-mobile-device.md), either completely, or selectively wipe organizational information from the device.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="781c2-281">相關主題</span><span class="sxs-lookup"><span data-stu-id="781c2-281">Related Topics</span></span>

[<span data-ttu-id="781c2-282">Office 365 的行動裝置管理概觀</span><span class="sxs-lookup"><span data-stu-id="781c2-282">Overview of Mobile Device Management for Office 365</span></span>](overview-of-mdm.md)
  
[<span data-ttu-id="781c2-283">Office 365 的行動裝置管理功能</span><span class="sxs-lookup"><span data-stu-id="781c2-283">Capabilities of Mobile Device Management for Office 365</span></span>](capabilities-of-mobile-device-management.md)
  

