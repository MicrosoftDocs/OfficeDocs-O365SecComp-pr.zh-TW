---
title: 疑難排解與 MDM 的裝置註冊 Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 11/17/2015
ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: c863b2bf-45f3-483a-ba05-29fc7f4d6434
description: 如果您正在執行發生問題當您嘗試在行動裝置管理 (MDM) 的裝置註冊 Office 365 時，嘗試向下問題追蹤此處所列的步驟。如果的一般步驟不修正此問題，請參閱之一的更新版本的裝置類型的特定步驟。
ms.openlocfilehash: 490259fc623b38ab5ad6cf8553c5074c77b77426
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272108"
---
# <a name="troubleshoot-device-enrollment-with-mdm-for-office-365"></a><span data-ttu-id="9846d-104">疑難排解與 MDM 的裝置註冊 Office 365</span><span class="sxs-lookup"><span data-stu-id="9846d-104">Troubleshoot device enrollment with MDM for Office 365</span></span>

<span data-ttu-id="9846d-p102">如果您正在執行發生問題當您嘗試在行動裝置管理 (MDM) 的裝置註冊 Office 365 時，嘗試向下問題追蹤此處所列的步驟。如果的一般步驟不修正此問題，請參閱之一的更新版本的裝置類型的特定步驟。</span><span class="sxs-lookup"><span data-stu-id="9846d-p102">If you're running into issues when you try to enroll a device in Mobile Device Management (MDM) for Office 365, try the steps listed here to track down the problem. If the general steps don't fix the issue, see one of the later sections with specific steps for your device type.</span></span>
  
## <a name="steps-to-try-first"></a><span data-ttu-id="9846d-107">若要先嘗試的步驟</span><span class="sxs-lookup"><span data-stu-id="9846d-107">Steps to try first</span></span>

<span data-ttu-id="9846d-108">若要啟動，請檢查下列事項：</span><span class="sxs-lookup"><span data-stu-id="9846d-108">To start, check the following:</span></span>
  
- <span data-ttu-id="9846d-109">請確定裝置不已經註冊與其他的行動裝置管理提供者，例如 Intune。</span><span class="sxs-lookup"><span data-stu-id="9846d-109">Make sure that the device is not already enrolled with another mobile device management provider, such as Intune.</span></span>
    
- <span data-ttu-id="9846d-110">請確定裝置設定正確的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="9846d-110">Make sure that the device is set to the correct date and time.</span></span>
    
- <span data-ttu-id="9846d-111">切換至不同的 Wi-fi 或行動裝置上的網路。</span><span class="sxs-lookup"><span data-stu-id="9846d-111">Switch to a different Wi-Fi or cellular network on the device.</span></span>
    
- <span data-ttu-id="9846d-112">Android 或 iOS 裝置解除安裝再重新安裝 Intune 的公司入口網站應用程式在裝置上。</span><span class="sxs-lookup"><span data-stu-id="9846d-112">For Android or iOS devices, uninstall and reinstall the Intune Company Portal app on the device.</span></span>
    
## <a name="ios-phone-or-tablet"></a><span data-ttu-id="9846d-113">iOS 電話或平板電腦</span><span class="sxs-lookup"><span data-stu-id="9846d-113">iOS phone or tablet</span></span>

- <span data-ttu-id="9846d-114">請確定您已[設定 APNs 憑證](https://support.office.com/article/522b43f4-a2ff-46f6-962a-dd4f47e546a7)。</span><span class="sxs-lookup"><span data-stu-id="9846d-114">Make sure that you've [set up an APNs certificate](https://support.office.com/article/522b43f4-a2ff-46f6-962a-dd4f47e546a7).</span></span>
    
- <span data-ttu-id="9846d-p103">在**設定** \> **一般** \> **設定檔**（或**裝置管理**），請確定未已經安裝**管理設定檔**。如果它是將它移除。</span><span class="sxs-lookup"><span data-stu-id="9846d-p103">In **Settings** \> **General** \> **Profile** (or **Device Management**), make sure that a **Management Profile** is not already installed. If it is, remove it.</span></span> 
    
- <span data-ttu-id="9846d-117">如果您看到錯誤訊息，「 裝置無法註冊，"登入 Office 365，並確定包含 Exchange Online 授權具有已指派給裝置登入的使用者。</span><span class="sxs-lookup"><span data-stu-id="9846d-117">If you see the error message, "Device failed to enroll," sign in to Office 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>
    
- <span data-ttu-id="9846d-118">如果您看到錯誤訊息，「 設定檔安裝失敗，"嘗試下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="9846d-118">If you see the error message, "Profile failed to install," try one of the following:</span></span>
    
  - <span data-ttu-id="9846d-119">請確定 Safari 已在裝置上的預設瀏覽器並 cookie 並未停用。</span><span class="sxs-lookup"><span data-stu-id="9846d-119">Make sure that Safari is the default browser on the device, and that cookies are not disabled.</span></span>
    
  - <span data-ttu-id="9846d-120">重新啟動裝置，然後瀏覽至 [portal.manage.microsoft.com、 登入您的 Office 365 使用者識別碼和密碼，並嘗試手動安裝之設定檔。</span><span class="sxs-lookup"><span data-stu-id="9846d-120">Reboot the device, then navigate to portal.manage.microsoft.com, sign in with your Office 365 user ID and password, and attempt to install the profile manually.</span></span>
    
## <a name="windows-rt-tablet"></a><span data-ttu-id="9846d-121">Windows RT 平板電腦</span><span class="sxs-lookup"><span data-stu-id="9846d-121">Windows RT tablet</span></span>

- <span data-ttu-id="9846d-122">請確定您的網域是[設定為與 MDM 搭配 Office 365 中](set-up-mobile-device-management.md)。</span><span class="sxs-lookup"><span data-stu-id="9846d-122">Make sure that your domain is [set up in Office 365 to work with MDM](set-up-mobile-device-management.md).</span></span>
    
- <span data-ttu-id="9846d-123">請確定該使用者會**開啟在**選擇而不是選擇**加入**。</span><span class="sxs-lookup"><span data-stu-id="9846d-123">Make sure that the user is choosing **Turn On** rather than choosing **Join**.</span></span>
    
## <a name="windows-phone"></a><span data-ttu-id="9846d-124">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="9846d-124">Windows Phone</span></span>

- <span data-ttu-id="9846d-125">請確定您的網域是[設定為與 MDM 搭配 Office 365 中](set-up-mobile-device-management.md)。</span><span class="sxs-lookup"><span data-stu-id="9846d-125">Make sure that your domain is [set up in Office 365 to work with MDM](set-up-mobile-device-management.md).</span></span>
    
- <span data-ttu-id="9846d-126">請確定裝置執行的 Windows 8.1 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="9846d-126">Make sure the device is running Windows 8.1 or later.</span></span>
    
## <a name="android-phone-or-tablet"></a><span data-ttu-id="9846d-127">Android 電話或平板電腦</span><span class="sxs-lookup"><span data-stu-id="9846d-127">Android phone or tablet</span></span>

- <span data-ttu-id="9846d-128">請確定裝置執行的 Android 4.0 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="9846d-128">Make sure the device is running Android 4.0 or later.</span></span>
    
- <span data-ttu-id="9846d-129">如果您看到錯誤訊息，"我們無法註冊此裝置，"登入 Office 365，並確定包含 Exchange Online 授權具有已指派給裝置登入的使用者。</span><span class="sxs-lookup"><span data-stu-id="9846d-129">If you see the error message, "We couldn't enroll this device," sign in to Office 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>
    
- <span data-ttu-id="9846d-130">檢查**通知區域**在裝置上查看是否有任何必要的使用者動作待並如果是，請先完成動作。</span><span class="sxs-lookup"><span data-stu-id="9846d-130">Check the **Notification Area** on the device to see if any required end-user actions are pending, and if they are, complete the actions.</span></span> 
    

