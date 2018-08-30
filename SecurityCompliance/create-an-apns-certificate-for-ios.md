---
title: 建立 APNs 憑證 iOS 裝置
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 8/5/2016
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- O365M_APNCertMDM
- O365E_APNCertMDM
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 522b43f4-a2ff-46f6-962a-dd4f47e546a7
description: 若要管理 iOS 裝置 iPad 和 Iphone 在行動裝置管理 Office 365，請遵循下列步驟，先建立一個 APNs 憑證。
ms.openlocfilehash: 28e8888d7dd57c3052cdcb5994725f11a5f0445f
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272048"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a>建立 APNs 憑證 iOS 裝置

 若要管理 Office 365 的 iPad 和 Iphone 在行動裝置管理的 iOS 裝置必須建立 APNs 憑證。 
  
若要這樣做，從 [**設定**] 連結入口網站頁面上遵循的步驟。(請移至**安全性&amp;規範中心** \> **安全性原則** \> **裝置管理** \> **管理設定**。)
  
![設定行動裝置管理必要和建議的步驟](media/d71e3c76-b6b9-4549-ade6-cbfab846d908.png)
  
1. **Configure iOS 裝置 APNs 憑證**] 旁邊選取 [**設定**]。
    
2. 選取 [**下載 CSR 檔案**並儲存至兩者的憑證簽署要求將記住您電腦上。 
    
    ![安裝 APN 憑證] 對話方塊](media/03aa8a24-e95c-4077-9b6b-ef76a86bafd7.png)
  
3. 選取 [**下一步**]。
    
4. 建立 APN 憑證。
    
  - 選取 [ **Apple APNS 入口網站**來開啟 Apple 推入憑證入口網站。 
    
    ![使用選取的 Apple APNS 入口網站安裝 APN 通知 cert 對話方塊](media/ce19f53c-f44a-470b-baf3-9278dfda2ba5.png)
  
  - 使用 Apple ID 登入
    
    > [!IMPORTANT]
    > 使用 Apple 識別碼即使管理帳戶的使用者離開會與您的組織中保留電子郵件帳戶相關聯的公司。因為您需要該是時候來更新憑證時所使用的相同識別碼儲存此識別碼。 
  
  - 選取 [**建立憑證**並接受**使用規定**。
    
  - **瀏覽**至您下載到您的電腦從 Office 365 和選取 [**上傳**的憑證簽署要求。
    
  - **下載**建立 Apple 推入憑證入口網站到您的電腦 APN 憑證。 
    
    > [!TIP]
    > 如果您無法下載憑證，重新整理瀏覽器。 
  
5. 前往 Office 365 並選取 [**下一步**取得**上傳 APNS 憑證**] 頁面。 
    
6. 瀏覽至您下載從 Apple 推入憑證入口網站的 APN 憑證。
    
    ![按一下 [瀏覽] 按鈕選取 APNS cert 從 Apple 下載](media/afe2849d-af23-4c55-9009-d8f25edaf6c0.png)
  
7. 選取 [**完成**]。
    
移回至**安全性&amp;規範中心** \> **安全性原則** \> **裝置管理** \> **管理設定**以完成安裝程式。 
  

