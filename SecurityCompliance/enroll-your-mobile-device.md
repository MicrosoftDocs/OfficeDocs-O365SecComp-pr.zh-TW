---
title: 註冊 Office 365 的行動裝置
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 6/25/2018
ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
ms.assetid: c8ac722d-dcaf-4135-8345-3e6327f5d3c5
description: 您可以使用 Office 365 服務與您的裝置之前，您可能需要遵循下列步驟以註冊在行動裝置管理的 Office 365 (MDM)。當您新增您的工作或學校至您的裝置的電子郵件帳戶的第一次，您可以這麼做。
ms.openlocfilehash: 0584309770cb978a5051bc84082de6e6be0b989e
ms.sourcegitcommit: 2cf7f5bb282c971d33e00f65d9982a3f14aec74e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/27/2018
ms.locfileid: "26706347"
---
# <a name="enroll-your-mobile-device-in-office-365"></a><span data-ttu-id="fa528-104">註冊 Office 365 的行動裝置</span><span class="sxs-lookup"><span data-stu-id="fa528-104">Enroll your mobile device in Office 365</span></span>

<span data-ttu-id="fa528-p102">使用您的電話、 平板電腦及其他行動裝置工作是更好的方式來保持在最得知和處理商務專案時您正在離開辦公室。您可以使用 Office 365 服務與您的裝置之前，您可能需要先註冊它在行動裝置管理的 Office 365 (MDM) 使用 Microsoft Intune 的公司入口網站。</span><span class="sxs-lookup"><span data-stu-id="fa528-p102">Using your phone, tablet, and other mobile devices for work is a great way to stay informed and work on business projects while you're away from the office. Before you can use Office 365 services with your device, you may need to first enroll it in Mobile Device Management for Office 365 (MDM) using Microsoft Intune Company Portal.</span></span>
  
<span data-ttu-id="fa528-p103">組織都會選擇 MDM 員工可以使用其行動裝置存取安全工作電子郵件、 行事曆和文件時商業保護重要資料及符合其法規需求。[解 Office 365 中的 MDM](https://support.office.com/article/overview-of-mobile-device-management-mdm-for-office-365-faa7d8e5-645d-4d59-839c-c8d4c1869e4a)。</span><span class="sxs-lookup"><span data-stu-id="fa528-p103">Organizations choose MDM so that employees can use their mobile devices to securely access work email, calendars, and documents while the business secures important data and meets their compliance requirements. [Learn about MDM in Office 365](https://support.office.com/article/overview-of-mobile-device-management-mdm-for-office-365-faa7d8e5-645d-4d59-839c-c8d4c1869e4a).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fa528-p104">當您註冊您的裝置中 MDM for Office 365 時，您可能需要設定密碼，以及讓公司組織裝置的選項。裝置資料抹除可執行 （從 Office 365 系統管理中心），例如，若要從裝置中移除所有資料如果密碼輸入不正確地太多次或使用條款會中斷。</span><span class="sxs-lookup"><span data-stu-id="fa528-p104">When you enroll your device in MDM for Office 365, you might be required to set up a password, together with allowing the option for your work organization to wipe the device. A device wipe can be performed (from the Office 365 admin center), for example, to remove all data from the device if the password is entered incorrectly too many times or if usage terms are broken.</span></span> 
  
 <span data-ttu-id="fa528-111">**支援的裝置**</span><span class="sxs-lookup"><span data-stu-id="fa528-111">**Supported devices**</span></span>
  
<span data-ttu-id="fa528-p105">MDM 和 InTune 適用於大部分，但並非所有的行動裝置。以下被支援 MDM 與 Office 365。</span><span class="sxs-lookup"><span data-stu-id="fa528-p105">MDM and InTune works with most, but not all, mobile devices. The following are supported with MDM for Office 365.</span></span>
  
- <span data-ttu-id="fa528-114">iOS 7.1 或更新版本</span><span class="sxs-lookup"><span data-stu-id="fa528-114">iOS 7.1 or later</span></span>
    
- <span data-ttu-id="fa528-115">Android 4 或更新版本</span><span class="sxs-lookup"><span data-stu-id="fa528-115">Android 4 or later</span></span>
    
- <span data-ttu-id="fa528-116">Windows 8.1 （電話和 PC） 和稍後要包含 Windows 10</span><span class="sxs-lookup"><span data-stu-id="fa528-116">Windows 8.1 (Phone and PC) and later to include Windows 10</span></span>
    
- <span data-ttu-id="fa528-117">Windows 10</span><span class="sxs-lookup"><span data-stu-id="fa528-117">Windows 10</span></span>
    
<span data-ttu-id="fa528-118">如果您的裝置未列出上方，且您需要使用 MDM 與 Intune、 連絡工作或學校管理員。</span><span class="sxs-lookup"><span data-stu-id="fa528-118">If your device is not listed above, and you need to use it with MDM and Intune, contact your work or school administrator.</span></span>
  
> [!TIP]
> <span data-ttu-id="fa528-119">如果您無法註冊您的裝置，請參閱：[使用 Office 365 MDM 疑難排解裝置註冊](https://support.office.com/article/Troubleshoot-device-enrollment-with-MDM-for-Office-365-c863b2bf-45f3-483a-ba05-29fc7f4d6434)。</span><span class="sxs-lookup"><span data-stu-id="fa528-119">If you're having trouble enrolling your device, see: [Troubleshoot device enrollment with MDM for Office 365](https://support.office.com/article/Troubleshoot-device-enrollment-with-MDM-for-Office-365-c863b2bf-45f3-483a-ba05-29fc7f4d6434).</span></span> 
  
## <a name="set-up-your-mobile-device-with-intune-and-mdm-for-office-365"></a><span data-ttu-id="fa528-120">設定行動裝置與 Intune 和 MDM for Office 365</span><span class="sxs-lookup"><span data-stu-id="fa528-120">Set up your mobile device with Intune and MDM for Office 365</span></span>

<span data-ttu-id="fa528-121">Intune 的公司入口網站可讓管理 Office 365 及 MDM.裝置</span><span class="sxs-lookup"><span data-stu-id="fa528-121">The Intune Company Portal enables a device to be managed by Office 365 and MDM.</span></span>
  
### <a name="iphone-or-ipad"></a><span data-ttu-id="fa528-122">iPhone 或 iPad</span><span class="sxs-lookup"><span data-stu-id="fa528-122">iPhone or iPad</span></span>

> [!TIP]
> <span data-ttu-id="fa528-p106">您不能傳送及接收電子郵件之前完成此步驟。移至 Apple 應用程式存放區、 下載及安裝**Intune 的公司入口網站**。請參閱 ＜ [Set up iOS 裝置存取公司資源](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios)。</span><span class="sxs-lookup"><span data-stu-id="fa528-p106">You won't be able to send and receive email until you complete this step. Go to the Apple App Store, download and install **Intune Company Portal**. See [Set up iOS device access to your company resources](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios).</span></span> 
    
### <a name="android-phone-or-tablet"></a><span data-ttu-id="fa528-126">Android 電話或平板電腦</span><span class="sxs-lookup"><span data-stu-id="fa528-126">Android phone or tablet</span></span>

> [!TIP]
> <span data-ttu-id="fa528-p107">您不能傳送及接收電子郵件之前完成此步驟。移至 Google 播放存放區、 下載及安裝 Intune 的公司入口網站。請參閱[註冊您的 Intune 的 Android 裝置](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android)。</span><span class="sxs-lookup"><span data-stu-id="fa528-p107">You won't be able to send and receive email until you complete this step. Go to the Google Play store, download and install Intune Company Portal. See [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android).</span></span> 
    
## <a name="whats-next"></a><span data-ttu-id="fa528-130">下一步是什麼</span><span class="sxs-lookup"><span data-stu-id="fa528-130">What's next</span></span>

<span data-ttu-id="fa528-131">您的裝置在 MDM 中註冊 Office 365 之後，您就可以開始使用裝置上的 Office 應用程式來處理的電子郵件、 行事曆、 連絡人及文件。</span><span class="sxs-lookup"><span data-stu-id="fa528-131">After your device is enrolled in MDM for Office 365, you can start using Office apps on your device to work with email, calendar, contacts, and documents.</span></span>
  

