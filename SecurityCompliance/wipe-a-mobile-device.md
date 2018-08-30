---
title: 在 Office 365 抹除行動裝置
ms.author: dianef
author: dianef77
manager: scotv
ms.date: 6/11/2018
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- O365M_WipeDevice
- O365E_WipeDevice
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 9d727c7d-8b47-4499-bf24-d046b449214c
description: 您可以使用內建的行動裝置管理 Office 365 執行移除組織資訊、 選擇性清除或刪除行動裝置中的所有資訊並還原至其中心設定完全清除作業。
ms.openlocfilehash: d3eb28575924ca3bb4a647ae9af2f96b55116a53
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272498"
---
# <a name="wipe-a-mobile-device-in-office-365"></a><span data-ttu-id="35d55-103">在 Office 365 抹除行動裝置</span><span class="sxs-lookup"><span data-stu-id="35d55-103">Wipe a mobile device in Office 365</span></span>
  
<span data-ttu-id="35d55-104">您可以使用內建的行動裝置管理 Office 365 執行移除組織資訊、 選擇性清除或刪除行動裝置中的所有資訊並還原至其中心設定完全清除作業。</span><span class="sxs-lookup"><span data-stu-id="35d55-104">You can use built-in mobile device management for Office 365 to do a selective wipe to remove only organizational information, or a full wipe to delete all information from a mobile device and restore it to its factory settings.</span></span>
  
## <a name="what-to-know-before-you-begin"></a><span data-ttu-id="35d55-105">要知道您開始之前</span><span class="sxs-lookup"><span data-stu-id="35d55-105">What to know before you begin</span></span>

- <span data-ttu-id="35d55-p101">行動裝置可以儲存機密組織資訊，並提供您組織的 Office 365 資源的存取權。若要協助保護您的組織資訊，您可以執行完整抹除或選擇性抹除：</span><span class="sxs-lookup"><span data-stu-id="35d55-p101">Mobile devices can store sensitive organizational information and provide access to your organization's Office 365 resources. To help protect your organization's information, you can do a full wipe or a selective wipe:</span></span>
    
  - <span data-ttu-id="35d55-p102">**完整抹除**： 刪除使用者的行動裝置，包括已安裝應用程式、 照片和個人資訊的所有資料。抹除完成時，裝置會還原為其原廠值。</span><span class="sxs-lookup"><span data-stu-id="35d55-p102">**Full wipe**: Deletes all data on a user's mobile device, including installed applications, photos, and personal information. When the wipe is complete, the device is restored to its factory settings.</span></span> 
    
  - <span data-ttu-id="35d55-110">**選擇性擦去**： 移除僅組織資料和離開安裝應用程式、 照片和使用者的行動裝置上的個人資訊。</span><span class="sxs-lookup"><span data-stu-id="35d55-110">**Selective wipe**: Removes only organization data and leaves installed applications, photos, and personal information on a user's mobile device.</span></span> 
    
- <span data-ttu-id="35d55-111">清除裝置時 （完整抹除或選擇性抹除），當裝置已從受管理的裝置清單。</span><span class="sxs-lookup"><span data-stu-id="35d55-111">When a device is wiped (full wipe or selective wipe), the device is removed from the list of managed devices.</span></span>
    
- <span data-ttu-id="35d55-p103">您可以設定自動擦去 （完全清除） 的行動裝置管理原則裝置之後使用者未成功嘗試輸入裝置的密碼特定的次數。請遵循的步驟[建立及部署裝置安全性原則](create-device-security-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="35d55-p103">You can set up a mobile device management policy that automatically wipes (full wipe) a device after the user unsuccessfully tries to enter the device's password a specific number of times. Follow the steps in [Create and deploy device security policies](create-device-security-policies.md).</span></span>
    
- <span data-ttu-id="35d55-114">如果您想要知道新使用者經驗都清除其裝置時，請參閱[功能的使用者和裝置影響？](wipe-a-mobile-device.md#BKMK_Impact)。</span><span class="sxs-lookup"><span data-stu-id="35d55-114">If you want to know what a user will experience when you wipe their device, see [What's the user and device impact?](wipe-a-mobile-device.md#BKMK_Impact).</span></span>
    
## <a name="wipe-a-mobile-device"></a><span data-ttu-id="35d55-115">行動裝置</span><span class="sxs-lookup"><span data-stu-id="35d55-115">Wipe a mobile device</span></span>

1. <span data-ttu-id="35d55-116">移至 [[![按一下這裡以移至 Office 365 系統管理中心。](media/e00ba917-c3fb-4173-b344-43eb5c7eeb15.png)](https://portal.office.com/adminportal/home)。</span><span class="sxs-lookup"><span data-stu-id="35d55-116">Go to the [![Click here to go to the Office 365 admin center.](media/e00ba917-c3fb-4173-b344-43eb5c7eeb15.png)](https://portal.office.com/adminportal/home).</span></span>

2. <span data-ttu-id="35d55-117">移至 [[移至 Office 365 安全性&amp;規範中心](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8)\> **資料外洩防護** \> **裝置管理**。</span><span class="sxs-lookup"><span data-stu-id="35d55-117">Go to [Go to the Office 365 Security &amp; Compliance Center](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8)\> **Data loss prevention** \> **Device management**.</span></span>
    
3. <span data-ttu-id="35d55-118">選取您想要清除的裝置。</span><span class="sxs-lookup"><span data-stu-id="35d55-118">Select the device you want to wipe.</span></span>
    
4. <span data-ttu-id="35d55-119">選取您要執行遠端清除的類型。</span><span class="sxs-lookup"><span data-stu-id="35d55-119">Select the type of remote wipe you want to do.</span></span>
    
  - <span data-ttu-id="35d55-120">若要設為選擇性抹除並刪除僅 Office 365 組織資訊，在右窗格中，選取 [**選擇性擦去**]。</span><span class="sxs-lookup"><span data-stu-id="35d55-120">To do a selective wipe and delete only Office 365 organization information, in the right pane, select **Selective wipe**.</span></span>
    
  - <span data-ttu-id="35d55-121">若要設為完全清除並還原裝置以其原廠值，在右窗格中，選取 [**完整擦去**]。</span><span class="sxs-lookup"><span data-stu-id="35d55-121">To do a full wipe and restore the device to its factory settings, in the right pane, select **Full wipe**.</span></span>
    
![選取裝置，然後選擇 [不要將清除類型。](media/ac940abe-0c4a-404e-a842-a1ad2af13ce3.png)
  
5. <span data-ttu-id="35d55-123">選取 **[是]** 確認。</span><span class="sxs-lookup"><span data-stu-id="35d55-123">Select **Yes** to confirm.</span></span> 
    
<span data-ttu-id="35d55-124">直到抹除完成後，**裝置狀態**會顯示為**RetirePending**或**RetireIssued**。</span><span class="sxs-lookup"><span data-stu-id="35d55-124">Until the wipe finishes, the **Device status** will show as **RetirePending** or **RetireIssued**.</span></span>
  
### <a name="how-do-i-know-it-worked"></a><span data-ttu-id="35d55-125">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="35d55-125">How do I know it worked?</span></span>

<span data-ttu-id="35d55-126">您無法再將看到的受管理的裝置清單中的行動裝置。</span><span class="sxs-lookup"><span data-stu-id="35d55-126">You'll no longer see the mobile device in the list of managed devices.</span></span>
  
## <a name="why-would-you-want-to-wipe-a-device"></a><span data-ttu-id="35d55-127">為什麼要選擇您要清除裝置？</span><span class="sxs-lookup"><span data-stu-id="35d55-127">Why would you want to wipe a device?</span></span>

<span data-ttu-id="35d55-128">有幾個理由清除裝置：</span><span class="sxs-lookup"><span data-stu-id="35d55-128">There are several reasons for wiping devices:</span></span>
  
- <span data-ttu-id="35d55-p104">智慧型手機與平板電腦等行動裝置會變得更多的全功能所有的時間。這表示會在使用者儲存機密公司的資訊 （例如個人識別碼或 2 私人 3 機密通訊） 和存取在行進比較容易。如果其中一個行動裝置遺失或竊、 立即清除裝置能夠協助防止從結束的一面貴組織的資訊。</span><span class="sxs-lookup"><span data-stu-id="35d55-p104">Mobile devices like smartphones and tablets are becoming more full-featured all the time. This means it's easier for your users to store sensitive corporate information (such as personal identification or confidential communications) and access it on the go. If one of these mobile devices is lost or stolen, wiping the device immediately can help prevent your organization's information from ending up in the wrong hands.</span></span>
    
- <span data-ttu-id="35d55-132">當使用者離開組織與在 MDM 中註冊 Office 365 的個人裝置時，有助於防止從依照選擇性抹除不必與該使用者的組織資訊。</span><span class="sxs-lookup"><span data-stu-id="35d55-132">When a user leaves the organization with a personal device that is enrolled in MDM for Office 365, you can help prevent organizational information from going with that user by doing a selective wipe.</span></span>
    
- <span data-ttu-id="35d55-p105">如果您的組織為使用者提供行動裝置，您可能需要重新指派裝置的時候。完整抹除裝置之前先將它指派給新的使用者可幫助確保會刪除舊的擁有者任何機密資訊。</span><span class="sxs-lookup"><span data-stu-id="35d55-p105">If your organization provides mobile devices to users, you might need to reassign devices from time to time. Doing a full wipe on a device before assigning it to a new user helps ensures that any sensitive information from the previous owner is deleted.</span></span>
    
## <a name="whats-the-user-and-device-impact"></a><span data-ttu-id="35d55-135">新功能的使用者和裝置的影響</span><span class="sxs-lookup"><span data-stu-id="35d55-135">What's the user and device impact?</span></span>

<span data-ttu-id="35d55-p106">清除立即傳送至行動裝置。裝置也會標示為不相容的 AAD。</span><span class="sxs-lookup"><span data-stu-id="35d55-p106">The wipe is sent immediately to the mobile device. The device is also marked as not compliant in AAD.</span></span>
  
<span data-ttu-id="35d55-138">下表說明內容已針對每個裝置類型時選擇性地清除裝置時。</span><span class="sxs-lookup"><span data-stu-id="35d55-138">The following table describes what content is removed for each device type when a device is selectively wiped.</span></span>
  
|<span data-ttu-id="35d55-139">**內容的影響**</span><span class="sxs-lookup"><span data-stu-id="35d55-139">**Content impact**</span></span>|<span data-ttu-id="35d55-140">**Windows Phone 8.1**</span><span class="sxs-lookup"><span data-stu-id="35d55-140">**Windows Phone 8.1**</span></span>|<span data-ttu-id="35d55-141">**iOS 7.1+**</span><span class="sxs-lookup"><span data-stu-id="35d55-141">**iOS 7.1+**</span></span>|<span data-ttu-id="35d55-142">**Android 4+**</span><span class="sxs-lookup"><span data-stu-id="35d55-142">**Android 4+**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="35d55-143">公司入口網站應用程式\*解除安裝。</span><span class="sxs-lookup"><span data-stu-id="35d55-143">Company Portal app\* is uninstalled.</span></span>  <br/> |<span data-ttu-id="35d55-144">不適用</span><span class="sxs-lookup"><span data-stu-id="35d55-144">N/A</span></span>  <br/> |<span data-ttu-id="35d55-145">✔</span><span class="sxs-lookup"><span data-stu-id="35d55-145">✔</span></span>  <br/> |<span data-ttu-id="35d55-146">不適用</span><span class="sxs-lookup"><span data-stu-id="35d55-146">N/A</span></span>  <br/> |
|<span data-ttu-id="35d55-p107">應用程式的存取控制其中的 MDM 支援的 Office 365 所主控的 office 365 應用程式資料是已移除 （目前 Outlook 和 OneDrive for Business）。應用程式不會移除。</span><span class="sxs-lookup"><span data-stu-id="35d55-p107">Office 365 app data hosted by apps where access control is supported by MDM for Office 365 is removed (currently Outlook and OneDrive for Business). The apps are not removed.</span></span>  <br/> <span data-ttu-id="35d55-149">Outlook for Android 不會移除快取的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="35d55-149">Outlook for Android does not remove cached emails.</span></span>  <br/> |<span data-ttu-id="35d55-150">✔</span><span class="sxs-lookup"><span data-stu-id="35d55-150">✔</span></span>  <br/> |<span data-ttu-id="35d55-151">✔</span><span class="sxs-lookup"><span data-stu-id="35d55-151">✔</span></span>  <br/> |<span data-ttu-id="35d55-152">✔</span><span class="sxs-lookup"><span data-stu-id="35d55-152">✔</span></span>  <br/> |
|<span data-ttu-id="35d55-153">在裝置上不再強制執行原則設定已套用 MDM 由 Office 365 的裝置和使用者可以變更的設定。</span><span class="sxs-lookup"><span data-stu-id="35d55-153">Policy settings that were applied by MDM for Office 365 to devices are no longer enforced on the device and users can change the settings.</span></span>  <br/> |<span data-ttu-id="35d55-154">✔</span><span class="sxs-lookup"><span data-stu-id="35d55-154">✔</span></span>  <br/> |<span data-ttu-id="35d55-155">✔</span><span class="sxs-lookup"><span data-stu-id="35d55-155">✔</span></span>  <br/> |<span data-ttu-id="35d55-156">✔</span><span class="sxs-lookup"><span data-stu-id="35d55-156">✔</span></span>  <br/> |
|<span data-ttu-id="35d55-157">移除 MDM 所建立的 Office 365 的電子郵件設定檔並刪除裝置上快取的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="35d55-157">Email profiles created by MDM for Office 365 are removed and cached email on the device is deleted.</span></span>  <br/> |<span data-ttu-id="35d55-158">不適用</span><span class="sxs-lookup"><span data-stu-id="35d55-158">N/A</span></span>  <br/> |<span data-ttu-id="35d55-159">✔</span><span class="sxs-lookup"><span data-stu-id="35d55-159">✔</span></span>  <br/> |<span data-ttu-id="35d55-160">不適用</span><span class="sxs-lookup"><span data-stu-id="35d55-160">N/A</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="35d55-161">\*公司入口網站應用程式為可用 iOS 應用程式商店及 Android 裝置播放存放區。</span><span class="sxs-lookup"><span data-stu-id="35d55-161">\* Company Portal app is available at the App Store for iOS and the Play Store for Android devices.</span></span> 
  
## <a name="related-content"></a><span data-ttu-id="35d55-162">相關內容</span><span class="sxs-lookup"><span data-stu-id="35d55-162">Related content</span></span>

[<span data-ttu-id="35d55-163">管理 Office 365 中的行動裝置</span><span class="sxs-lookup"><span data-stu-id="35d55-163">Manage mobile devices in Office 365</span></span>](set-up-mobile-device-management.md)
  

