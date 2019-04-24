---
title: 建立適用於 iOS 裝置 APNs 憑證
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 8/5/2016
ms.audience: Admin
ms.topic: article
f1_keywords:
- O365M_APNCertMDM
- O365E_APNCertMDM
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 522b43f4-a2ff-46f6-962a-dd4f47e546a7
description: 若要管理像在 iPad 和 Iphone 在行動裝置管理的 iOS 裝置的 Office 365，請遵循下列步驟，先建立 APNs 憑證。
ms.openlocfilehash: 5f82690f0add5f1aae95a089d9cdfc0b320ae596
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32258613"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="be650-103">建立適用於 iOS 裝置 APNs 憑證</span><span class="sxs-lookup"><span data-stu-id="be650-103">Create an APNs Certificate for iOS devices</span></span>

 <span data-ttu-id="be650-104">若要管理像在 iPad 和 Iphone 在行動裝置管理的 iOS 裝置的 Office 365 中，您必須建立 APNs 憑證。</span><span class="sxs-lookup"><span data-stu-id="be650-104">To manage iOS devices like iPad and iPhones in Mobile Device Management for Office 365 you must create an APNs certificate.</span></span> 
  
<span data-ttu-id="be650-105">若要這麼做，請依照從 [**設定**] 連結在入口網站] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="be650-105">To do this, follow the steps from the **Set up** link on the portal page.</span></span> <span data-ttu-id="be650-106">(移至**安全性&amp;合規性中心** \> **安全性原則** \> **裝置管理** \> **管理設定**。)</span><span class="sxs-lookup"><span data-stu-id="be650-106">(Go to **Security &amp; Compliance Center** \> **Security policies** \> **Device management** \> **Manage settings**.)</span></span>
  
![設定行動裝置管理必要和建議的步驟](media/d71e3c76-b6b9-4549-ade6-cbfab846d908.png)
  
1. <span data-ttu-id="be650-108">Next to **Configure a APNs Certificate for iOS devices**, select **Set up**.</span><span class="sxs-lookup"><span data-stu-id="be650-108">Next to **Configure a APNs Certificate for iOS devices**, select **Set up**.</span></span>
    
2. <span data-ttu-id="be650-109">Select **Download your CSR file** and save the Certificate signing request to a somewhere on your computer that you'll remember.</span><span class="sxs-lookup"><span data-stu-id="be650-109">Select **Download your CSR file** and save the Certificate signing request to a somewhere on your computer that you'll remember.</span></span> 
    
    ![安裝 APN 憑證] 對話方塊](media/03aa8a24-e95c-4077-9b6b-ef76a86bafd7.png)
  
3. <span data-ttu-id="be650-111"> Select *\*Next*\*. </span><span class="sxs-lookup"><span data-stu-id="be650-111">Select **Next**.</span></span>
    
4. <span data-ttu-id="be650-112"> Create an APN certificate.</span><span class="sxs-lookup"><span data-stu-id="be650-112">Create an APN certificate.</span></span>
    
  - <span data-ttu-id="be650-113">Select **Apple APNS Portal** to open the Apple Push Certificates Portal. </span><span class="sxs-lookup"><span data-stu-id="be650-113">Select **Apple APNS Portal** to open the Apple Push Certificates Portal.</span></span> 
    
    ![使用選取的 Apple APNS 入口網站安裝 APN 通知憑證對話方塊](media/ce19f53c-f44a-470b-baf3-9278dfda2ba5.png)
  
  - <span data-ttu-id="be650-115">Sign in with an Apple ID.</span><span class="sxs-lookup"><span data-stu-id="be650-115">Sign in with an Apple ID.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="be650-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span><span class="sxs-lookup"><span data-stu-id="be650-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span> 
  
  - <span data-ttu-id="be650-118">Select **Create a Certificate** and accept the **Terms of Use**.</span><span class="sxs-lookup"><span data-stu-id="be650-118">Select **Create a Certificate** and accept the **Terms of Use**.</span></span>
    
  - <span data-ttu-id="be650-119">**Browse** to the Certificate signing request you downloaded to your computer from Office 365 and select **Upload**.</span><span class="sxs-lookup"><span data-stu-id="be650-119">**Browse** to the Certificate signing request you downloaded to your computer from Office 365 and select **Upload**.</span></span>
    
  - <span data-ttu-id="be650-120">**Download** the APN certificate created by the Apple Push Certificate Portal to your computer.</span><span class="sxs-lookup"><span data-stu-id="be650-120">**Download** the APN certificate created by the Apple Push Certificate Portal to your computer.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="be650-121">If you're having trouble downloading the certificate, refresh your browser.</span><span class="sxs-lookup"><span data-stu-id="be650-121">If you're having trouble downloading the certificate, refresh your browser.</span></span> 
  
5. <span data-ttu-id="be650-122">Go back to Office 365 and select **Next** to get to the **Upload APNS certificate** page.</span><span class="sxs-lookup"><span data-stu-id="be650-122">Go back to Office 365 and select **Next** to get to the **Upload APNS certificate** page.</span></span> 
    
6. <span data-ttu-id="be650-123"> Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span><span class="sxs-lookup"><span data-stu-id="be650-123">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>
    
    ![按一下 [瀏覽] 按鈕，選取您從 Apple 下載 APNS 憑證](media/afe2849d-af23-4c55-9009-d8f25edaf6c0.png)
  
7. <span data-ttu-id="be650-125">Select **Finish**.</span><span class="sxs-lookup"><span data-stu-id="be650-125">Select **Finish**.</span></span>
    
<span data-ttu-id="be650-126">移至**安全性&amp;合規性中心** \> **安全性原則** \> **裝置管理** \> **管理設定**，以完成安裝。</span><span class="sxs-lookup"><span data-stu-id="be650-126">Go back to **Security &amp; Compliance Center** \> **Security policies** \> **Device management** \> **Manage settings** to complete setup.</span></span> 
  

