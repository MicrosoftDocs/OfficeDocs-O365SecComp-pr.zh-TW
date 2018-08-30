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
# <a name="troubleshoot-device-enrollment-with-mdm-for-office-365"></a>疑難排解與 MDM 的裝置註冊 Office 365

如果您正在執行發生問題當您嘗試在行動裝置管理 (MDM) 的裝置註冊 Office 365 時，嘗試向下問題追蹤此處所列的步驟。如果的一般步驟不修正此問題，請參閱之一的更新版本的裝置類型的特定步驟。
  
## <a name="steps-to-try-first"></a>若要先嘗試的步驟

若要啟動，請檢查下列事項：
  
- 請確定裝置不已經註冊與其他的行動裝置管理提供者，例如 Intune。
    
- 請確定裝置設定正確的日期與時間。
    
- 切換至不同的 Wi-fi 或行動裝置上的網路。
    
- Android 或 iOS 裝置解除安裝再重新安裝 Intune 的公司入口網站應用程式在裝置上。
    
## <a name="ios-phone-or-tablet"></a>iOS 電話或平板電腦

- 請確定您已[設定 APNs 憑證](https://support.office.com/article/522b43f4-a2ff-46f6-962a-dd4f47e546a7)。
    
- 在**設定** \> **一般** \> **設定檔**（或**裝置管理**），請確定未已經安裝**管理設定檔**。如果它是將它移除。 
    
- 如果您看到錯誤訊息，「 裝置無法註冊，"登入 Office 365，並確定包含 Exchange Online 授權具有已指派給裝置登入的使用者。
    
- 如果您看到錯誤訊息，「 設定檔安裝失敗，"嘗試下列其中一項：
    
  - 請確定 Safari 已在裝置上的預設瀏覽器並 cookie 並未停用。
    
  - 重新啟動裝置，然後瀏覽至 [portal.manage.microsoft.com、 登入您的 Office 365 使用者識別碼和密碼，並嘗試手動安裝之設定檔。
    
## <a name="windows-rt-tablet"></a>Windows RT 平板電腦

- 請確定您的網域是[設定為與 MDM 搭配 Office 365 中](set-up-mobile-device-management.md)。
    
- 請確定該使用者會**開啟在**選擇而不是選擇**加入**。
    
## <a name="windows-phone"></a>Windows Phone

- 請確定您的網域是[設定為與 MDM 搭配 Office 365 中](set-up-mobile-device-management.md)。
    
- 請確定裝置執行的 Windows 8.1 或更新版本。
    
## <a name="android-phone-or-tablet"></a>Android 電話或平板電腦

- 請確定裝置執行的 Android 4.0 或更新版本。
    
- 如果您看到錯誤訊息，"我們無法註冊此裝置，"登入 Office 365，並確定包含 Exchange Online 授權具有已指派給裝置登入的使用者。
    
- 檢查**通知區域**在裝置上查看是否有任何必要的使用者動作待並如果是，請先完成動作。 
    

