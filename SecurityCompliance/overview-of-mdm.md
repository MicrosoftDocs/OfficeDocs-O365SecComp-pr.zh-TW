---
title: 行動裝置管理 (MDM) for Office 365 概觀
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
f1_keywords:
- O365M_MDMConfigDomains
- O365E_MDMConfigDomains
- ms.o365.cc.DevicePolicy
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: faa7d8e5-645d-4d59-839c-c8d4c1869e4a
description: 您可以管理並保護行動裝置時他們正在使用行動裝置管理 Office 365 的連線至 Office 365 組織。行動裝置 like 智慧型手機與平板電腦用來存取工作電子郵件、 行事曆、 連絡人、 與文件播放中同時務必使用員工取得任何時候、 從任何地方完成其工作的大組件。因此很重要的協助保護您的組織資訊時使用的裝置。您可以使用 Office 365 MDM 設定的裝置安全性原則和存取規則，以及如果他們正在遺失或竊抹除行動裝置。
ms.openlocfilehash: f06cef11b68ee0673f13c54738f07f4556495fdd
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272488"
---
# <a name="overview-of-mobile-device-management-mdm-for-office-365"></a><span data-ttu-id="8abfe-106">行動裝置管理 (MDM) for Office 365 概觀</span><span class="sxs-lookup"><span data-stu-id="8abfe-106">Overview of Mobile Device Management (MDM) for Office 365</span></span>

<span data-ttu-id="8abfe-p102">您可以管理並保護行動裝置時他們正在使用行動裝置管理 Office 365 的連線至 Office 365 組織。行動裝置 like 智慧型手機與平板電腦用來存取工作電子郵件、 行事曆、 連絡人、 與文件播放中同時務必使用員工取得任何時候、 從任何地方完成其工作的大組件。因此很重要的協助保護您的組織資訊時使用的裝置。您可以使用 Office 365 MDM 設定的裝置安全性原則和存取規則，以及如果他們正在遺失或竊抹除行動裝置。</span><span class="sxs-lookup"><span data-stu-id="8abfe-p102">You can manage and secure mobile devices when they're connected to your Office 365 organization by using Mobile Device Management for Office 365. Mobile devices like smartphones and tablets that are used to access work email, calendar, contacts, and documents play a big part in making sure that employees get their work done anytime, from anywhere. So it's critical that you help protect your organization's information when people use devices. You can use MDM for Office 365 to set device security policies and access rules, and to wipe mobile devices if they're lost or stolen.</span></span>
  
![在 Android 手機 MDM](media/69b9a9f6-13ac-4e36-99ca-95e82e0375aa.png)
  
## <a name="what-types-of-devices-can-you-manage"></a><span data-ttu-id="8abfe-112">您可以管理哪些類型的裝置？</span><span class="sxs-lookup"><span data-stu-id="8abfe-112">What types of devices can you manage?</span></span>

<span data-ttu-id="8abfe-p103">您可以使用 Office 365 MDM 管理許多類型的 Windows Phone、 Android、 iPhone 和 iPad 行動裝置。若要管理組織中的人員所使用的行動裝置，每位使用者必須具有適用的 Office 365 授權及使用者的裝置必須 MDM 中註冊 Office 365。</span><span class="sxs-lookup"><span data-stu-id="8abfe-p103">You can use MDM for Office 365 to manage many types of mobile devices like Windows Phone, Android, iPhone, and iPad. To manage mobile devices used by people in your organization, each person must have an applicable Office 365 license and their device must be enrolled in MDM for Office 365.</span></span> 
  
<span data-ttu-id="8abfe-115">若要查看 MDM for Office 365 支援的每一種裝置，請參閱[功能的行動裝置管理 Office 365](capabilities-of-mobile-device-management.md)。</span><span class="sxs-lookup"><span data-stu-id="8abfe-115">To see what MDM for Office 365 supports for each type of device, see [Capabilities of Mobile Device Management for Office 365](capabilities-of-mobile-device-management.md).</span></span>
  
## <a name="setup-steps-for-mdm"></a><span data-ttu-id="8abfe-116">MDM 的設定步驟</span><span class="sxs-lookup"><span data-stu-id="8abfe-116">Setup steps for MDM</span></span>

<span data-ttu-id="8abfe-p104">Office 365 全域管理員必須完成下列步驟來啟動及設定 Office 365 MDM。在[Office 365 MDM 設定](set-up-mobile-device-management.md)以查看詳細的步驟遵循主題中的指導。以下是快速摘要：</span><span class="sxs-lookup"><span data-stu-id="8abfe-p104">An Office 365 global admin must complete the following steps to activate and set up MDM for Office 365. Follow the guidance in the topic on [setting up MDM for Office 365](set-up-mobile-device-management.md) to see detailed steps. Here's a quick summary:</span></span> 
  
> <span data-ttu-id="8abfe-120">步驟 1： 啟動 Office 365 MDM 依照[設設定行動裝置管理 (MDM) in Office 365](set-up-mobile-device-management.md)中的步驟。</span><span class="sxs-lookup"><span data-stu-id="8abfe-120">Step 1: Activate MDM for Office 365 by following steps in the [Set up Mobile Device Management (MDM) in Office 365](set-up-mobile-device-management.md).</span></span>
    
> <span data-ttu-id="8abfe-121">步驟 2： 設定 MDM 由該指令程式的 Office 365 例如建立管理 iOS 裝置 APNs 憑證和新增網域至支援 Windows phone 的網域名稱系統 (DNS) 記錄。</span><span class="sxs-lookup"><span data-stu-id="8abfe-121">Step 2: Set up MDM for Office 365 by, for example, creating an APNs certificate to manage iOS devices and adding a Domain Name System (DNS) record for your domain to support Windows phones.</span></span>
    
> <span data-ttu-id="8abfe-p105">步驟 3： 建立裝置原則並將其套用至使用者群組。當您這麼做時，您的使用者將會得到[其裝置上的註冊訊息](enroll-your-mobile-device.md)。和其裝置完成他們已註冊，將會限制您已針對這些設定的原則。</span><span class="sxs-lookup"><span data-stu-id="8abfe-p105">Step 3: Create device policies and apply them to groups of users. When you do this, your users will get an [enrollment message on their device](enroll-your-mobile-device.md). And when they've completed enrollment, their devices will be restricted by the policies you've set up for them.</span></span>
    
    ![Creating an MDN device policy under Device security policies](media/fbcdbecd-0016-42f1-81a9-9fbad610da90.png)
  
## <a name="device-management-tasks"></a><span data-ttu-id="8abfe-125">裝置管理工作</span><span class="sxs-lookup"><span data-stu-id="8abfe-125">Device management tasks</span></span>

<span data-ttu-id="8abfe-p106">您已安裝的 Office 365 中取得 MDM 與您的使用者已註冊其裝置後，您可以管理裝置、 封鎖的存取，或清除裝置中，視。深入了解[一些常見的裝置管理工作](manage-devices-in-mdm.md)，包括完成工作的位置。</span><span class="sxs-lookup"><span data-stu-id="8abfe-p106">After you've got MDM for Office 365 set up and your users have enrolled their devices, you can manage the devices, block access, or wipe a device, if needed. Learn more about [some common device management tasks](manage-devices-in-mdm.md), including where to complete the tasks.</span></span>
  
## <a name="other-ways-to-manage-devices-and-apps"></a><span data-ttu-id="8abfe-128">管理裝置和應用程式的其他方式</span><span class="sxs-lookup"><span data-stu-id="8abfe-128">Other ways to manage devices and apps</span></span>

<span data-ttu-id="8abfe-129">如果您需要更多的功能比 for Office 365 MDM 包括、 取出此[MDM 和 Microsoft Intune 的功能比較](choose-between-mdm-and-intune.md)查看如果 Intune 訂閱會符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="8abfe-129">If you need more functionality than MDM for Office 365 includes, check out this [comparison of MDM and Microsoft Intune features](choose-between-mdm-and-intune.md) to see if an Intune subscription would meet your organization's needs.</span></span> 
  
<span data-ttu-id="8abfe-p107">如果您只需要行動應用程式的管理 (MAM)，或許更新他們自己的裝置上的工時專案的人員 Intune 提供其他除了註冊和管理裝置] 選項。Intune 訂閱可讓您設定 MAM 原則使用 Azure 入口網站中，即使人的裝置不會註冊 Intune。請參閱 ＜ [Protect 應用程式資料 MAM 原則 （英文）](https://go.microsoft.com/fwlink/?LinkId=825439)。</span><span class="sxs-lookup"><span data-stu-id="8abfe-p107">If you just need mobile app management (MAM), perhaps for people updating work projects on their own devices, Intune provides another option besides enrolling and managing devices. An Intune subscription allows you to set up MAM policies by using the Azure portal, even if people's devices aren't enrolled in Intune. See [Protect app data using MAM policies](https://go.microsoft.com/fwlink/?LinkId=825439).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8abfe-133">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8abfe-133">See also</span></span>

[<span data-ttu-id="8abfe-134">取得裝置 MDM 所管理的相關詳細資料</span><span class="sxs-lookup"><span data-stu-id="8abfe-134">Get details about devices managed by MDM</span></span>](get-details-about-mdm-managed-devices.md)

[<span data-ttu-id="8abfe-135">針對 Office 365 設定 MDM</span><span class="sxs-lookup"><span data-stu-id="8abfe-135">Set up MDM for Office 365</span></span>](set-up-mobile-device-management.md)
  
[<span data-ttu-id="8abfe-136">註冊 MDM 在行動裝置</span><span class="sxs-lookup"><span data-stu-id="8abfe-136">Enroll mobile devices in MDM</span></span>](enroll-your-mobile-device.md)
  
[<span data-ttu-id="8abfe-137">管理裝置註冊 MDM</span><span class="sxs-lookup"><span data-stu-id="8abfe-137">Manage devices enrolled in MDM</span></span>](manage-devices-in-mdm.md)

