---
title: 建立適用於 iOS 裝置 APNs 憑證
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 8/5/2016
audience: Admin
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
ms.openlocfilehash: 17dae3e02520cdac2b1381039844d1657b12c4eb
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153755"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a>建立適用於 iOS 裝置 APNs 憑證

 若要管理像在 iPad 和 Iphone 在行動裝置管理的 iOS 裝置的 Office 365 中，您必須建立 APNs 憑證。 
  
若要這麼做，請依照從 [**設定**] 連結在入口網站] 頁面上。 (移至**安全性&amp;合規性中心** \> **安全性原則** \> **裝置管理** \> **管理設定**。)
  
![設定行動裝置管理必要和建議的步驟](media/d71e3c76-b6b9-4549-ade6-cbfab846d908.png)
  
1. Next to **Configure a APNs Certificate for iOS devices**, select **Set up**.
    
2. Select **Download your CSR file** and save the Certificate signing request to a somewhere on your computer that you'll remember. 
    
    ![安裝 APN 憑證] 對話方塊](media/03aa8a24-e95c-4077-9b6b-ef76a86bafd7.png)
  
3.  Select **Next**. 
    
4.  Create an APN certificate.
    
  - Select **Apple APNS Portal** to open the Apple Push Certificates Portal.  
    
    ![使用選取的 Apple APNS 入口網站安裝 APN 通知憑證對話方塊](media/ce19f53c-f44a-470b-baf3-9278dfda2ba5.png)
  
  - Sign in with an Apple ID.
    
    > [!IMPORTANT]
    > Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate. 
  
  - Select **Create a Certificate** and accept the **Terms of Use**.
    
  - **Browse** to the Certificate signing request you downloaded to your computer from Office 365 and select **Upload**.
    
  - **Download** the APN certificate created by the Apple Push Certificate Portal to your computer. 
    
    > [!TIP]
    > If you're having trouble downloading the certificate, refresh your browser. 
  
5. Go back to Office 365 and select **Next** to get to the **Upload APNS certificate** page. 
    
6.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.
    
    ![按一下 [瀏覽] 按鈕，選取您從 Apple 下載 APNS 憑證](media/afe2849d-af23-4c55-9009-d8f25edaf6c0.png)
  
7. Select **Finish**.
    
移至**安全性&amp;合規性中心** \> **安全性原則** \> **裝置管理** \> **管理設定**，以完成安裝。 
  

