---
title: 建立 APNs 憑證 iOS 裝置
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
description: 若要管理 iOS 裝置 iPad 和 Iphone 在行動裝置管理 Office 365，請遵循下列步驟，先建立一個 APNs 憑證。
ms.openlocfilehash: 5f82690f0add5f1aae95a089d9cdfc0b320ae596
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220453"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="5b011-103">建立 APNs 憑證 iOS 裝置</span><span class="sxs-lookup"><span data-stu-id="5b011-103">Create an APNs Certificate for iOS devices</span></span>

 <span data-ttu-id="5b011-104">若要管理 Office 365 的 iPad 和 Iphone 在行動裝置管理的 iOS 裝置必須建立 APNs 憑證。</span><span class="sxs-lookup"><span data-stu-id="5b011-104">To manage iOS devices like iPad and iPhones in Mobile Device Management for Office 365 you must create an APNs certificate.</span></span> 
  
<span data-ttu-id="5b011-p101">若要這樣做，從 [**設定**] 連結入口網站頁面上遵循的步驟。(請移至**安全性&amp;規範中心** \> **安全性原則** \> **裝置管理** \> **管理設定**。)</span><span class="sxs-lookup"><span data-stu-id="5b011-p101">To do this, follow the steps from the **Set up** link on the portal page. (Go to **Security &amp; Compliance Center** \> **Security policies** \> **Device management** \> **Manage settings**.)</span></span>
  
![設定行動裝置管理必要和建議的步驟](media/d71e3c76-b6b9-4549-ade6-cbfab846d908.png)
  
1. <span data-ttu-id="5b011-108">**Configure iOS 裝置 APNs 憑證**] 旁邊選取 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="5b011-108">Next to **Configure a APNs Certificate for iOS devices**, select **Set up**.</span></span>
    
2. <span data-ttu-id="5b011-109">選取 [**下載 CSR 檔案**並儲存至兩者的憑證簽署要求將記住您電腦上。</span><span class="sxs-lookup"><span data-stu-id="5b011-109">Select **Download your CSR file** and save the Certificate signing request to a somewhere on your computer that you'll remember.</span></span> 
    
    ![安裝 APN 憑證] 對話方塊](media/03aa8a24-e95c-4077-9b6b-ef76a86bafd7.png)
  
3. <span data-ttu-id="5b011-111">選取 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="5b011-111">Select **Next**.</span></span>
    
4. <span data-ttu-id="5b011-112">建立 APN 憑證。</span><span class="sxs-lookup"><span data-stu-id="5b011-112">Create an APN certificate.</span></span>
    
  - <span data-ttu-id="5b011-113">選取 [ **Apple APNS 入口網站**來開啟 Apple 推入憑證入口網站。</span><span class="sxs-lookup"><span data-stu-id="5b011-113">Select **Apple APNS Portal** to open the Apple Push Certificates Portal.</span></span> 
    
    ![使用選取的 Apple APNS 入口網站安裝 APN 通知 cert 對話方塊](media/ce19f53c-f44a-470b-baf3-9278dfda2ba5.png)
  
  - <span data-ttu-id="5b011-115">使用 Apple ID 登入</span><span class="sxs-lookup"><span data-stu-id="5b011-115">Sign in with an Apple ID.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="5b011-p102">使用 Apple 識別碼即使管理帳戶的使用者離開會與您的組織中保留電子郵件帳戶相關聯的公司。因為您需要該是時候來更新憑證時所使用的相同識別碼儲存此識別碼。</span><span class="sxs-lookup"><span data-stu-id="5b011-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span> 
  
  - <span data-ttu-id="5b011-118">選取 [**建立憑證**並接受**使用規定**。</span><span class="sxs-lookup"><span data-stu-id="5b011-118">Select **Create a Certificate** and accept the **Terms of Use**.</span></span>
    
  - <span data-ttu-id="5b011-119">**瀏覽**至您下載到您的電腦從 Office 365 和選取 [**上傳**的憑證簽署要求。</span><span class="sxs-lookup"><span data-stu-id="5b011-119">**Browse** to the Certificate signing request you downloaded to your computer from Office 365 and select **Upload**.</span></span>
    
  - <span data-ttu-id="5b011-120">**下載**建立 Apple 推入憑證入口網站到您的電腦 APN 憑證。</span><span class="sxs-lookup"><span data-stu-id="5b011-120">**Download** the APN certificate created by the Apple Push Certificate Portal to your computer.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="5b011-121">如果您無法下載憑證，重新整理瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="5b011-121">If you're having trouble downloading the certificate, refresh your browser.</span></span> 
  
5. <span data-ttu-id="5b011-122">前往 Office 365 並選取 [**下一步**取得**上傳 APNS 憑證**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="5b011-122">Go back to Office 365 and select **Next** to get to the **Upload APNS certificate** page.</span></span> 
    
6. <span data-ttu-id="5b011-123">瀏覽至您下載從 Apple 推入憑證入口網站的 APN 憑證。</span><span class="sxs-lookup"><span data-stu-id="5b011-123">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>
    
    ![按一下 [瀏覽] 按鈕選取 APNS cert 從 Apple 下載](media/afe2849d-af23-4c55-9009-d8f25edaf6c0.png)
  
7. <span data-ttu-id="5b011-125">選取 [**完成**]。</span><span class="sxs-lookup"><span data-stu-id="5b011-125">Select **Finish**.</span></span>
    
<span data-ttu-id="5b011-126">移回至**安全性&amp;規範中心** \> **安全性原則** \> **裝置管理** \> **管理設定**以完成安裝程式。</span><span class="sxs-lookup"><span data-stu-id="5b011-126">Go back to **Security &amp; Compliance Center** \> **Security policies** \> **Device management** \> **Manage settings** to complete setup.</span></span> 
  

