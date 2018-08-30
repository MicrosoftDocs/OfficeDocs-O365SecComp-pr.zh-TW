---
title: 常見問題集有關行動裝置管理 Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/30/2016
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 3871f99c-c9db-4a23-86f9-902c1b02f58d
description: 本文包含常見問題有關行動裝置管理 (MDM) for Office 365，可協助您管理並保護 Office 365 中的行動裝置功能。
ms.openlocfilehash: 6c4a5b3603d392b3d83769cd0f17450ce70565be
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272268"
---
# <a name="frequently-asked-questions-about-mobile-device-management-for-office-365"></a>常見問題集有關行動裝置管理 Office 365

本文包含常見問題有關行動裝置管理 (MDM) for Office 365，可協助您管理並保護 Office 365 中的行動裝置功能。
  
## <a name="faqs"></a>常見問題集

- [如何取得 MDM for Office 365？在 Office 365 系統管理中心中看不到](#how-can-i-get-mdm-for-office-365-i-dont-see-it-in-the-office-365-admin-center)
    
- [如何可以使用快速入門中 MDM 裝置管理](#how-can-i-get-started-with-device-management-in-mdm)
    
- [嘗試設定 MDM 但似乎停滯。Office 365 服務健康狀況具有"佈建 」 一段已顯示。我可以做什麼？](#im-trying-to-set-up-mdm-but-it-seems-stuck-the-office-365-service-health-has-been-showing-provisioning-for-a-while-what-can-i-do)
    
- [如果裝置註冊失敗，我可以做什麼？](#what-can-i-do-if-device-enrollment-fails)
    
- [Intune 與 Office 365 MDM 之間的差異為何？](#whats-the-difference-between-intune-and-mdm-for-office-365)
    
- [原則如何運作的 MDM？如何設定這些？停用吗？](#how-do-policies-work-for-mdm-how-do-i-set-them-up-disable-them)
    
- [可以使用從切換 Exchange ActiveSync 裝置管理至 MDM for Office 365 吗？](#can-i-switch-from-exchange-activesync-device-management-to-mdm-for-office-365)
    
- [設定 MDM 但現在我想要移除它。什麼是步驟？](#i-set-up-mdm-but-now-i-want-to-remove-it-what-are-the-steps)
    
- [仍然需要協助](#still-need-help)
    
## <a name="how-can-i-get-mdm-for-office-365-i-dont-see-it-in-the-office-365-admin-center"></a>如何取得 MDM for Office 365？在 Office 365 系統管理中心中看不到

我們已完成這項功能啟用 Office 365 的客戶。**裝置管理**] 索引標籤中尋找[移至 Office 365 安全性&amp;規範中心](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8)。如果您未看見它，請讓我們知道。請參閱[仍需要說明嗎？](#still-need-help)，與我們將協助您開始。 
  
## <a name="how-can-i-get-started-with-device-management-in-mdm"></a>如何可以使用快速入門中 MDM 裝置管理

有四個步驟開始使用 office 365 （了集中[設定行動裝置管理 (MDM) in Office 365](set-up-mobile-device-management.md)的詳細資訊） MDM：
  
1. **啟動 MDM.** 移至 [[移至 Office 365 安全性&amp;規範中心](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8)選取**裝置管理**。按一下 [**我們開始吧**開始進行的啟用程序。 
    
2. **MDM 完成設定**。這可能需要 APNs 憑證設定和 DNS 記錄的更新為您的網域。 
    
3. **建立原則**。建立裝置管理原則，並將它們套用到已[設定在安全性群組中](create-device-security-policies.md)的使用者群組。我們建議在您開始部署到小型測試群組原則。安全性&amp;規範中心、 選取的**裝置安全性原則**。
    
4. **使用者註冊裝置。** 使用者已有原則套用至其系統會提示[註冊其裝置](enroll-your-mobile-device.md)嘗試存取 Office 365 資料 （例如使用其電子郵件用戶端） 時。 
    
## <a name="im-trying-to-set-up-mdm-but-it-seems-stuck-the-office-365-service-health-has-been-showing-provisioning-for-a-while-what-can-i-do"></a>嘗試設定 MDM 但似乎停滯。Office 365 服務健康狀況具有"佈建 」 一段已顯示。我可以做什麼？

可能需要一些時間讓您學會服務。佈建完成時，您會看見行動裝置管理 Office 365] 頁面上。如果您已等待的 24 小時及狀態仍是 [**佈建**，請參閱[仍需要說明嗎？](#still-need-help)及我們將會協助找出問題的功能。 
  
## <a name="what-can-i-do-if-device-enrollment-fails"></a>如果裝置註冊失敗，我可以做什麼？

如果您無法取得註冊的裝置，先嘗試檢查下列：
  
- 請確定裝置不已經註冊與其他的行動裝置管理提供者，例如 Intune。
    
- 請確定裝置設定正確的日期與時間。
    
- 切換至不同的 Wi-fi 或行動裝置上的網路。
    
- Android 或 iOS 裝置解除安裝再重新安裝 Intune 的公司入口網站應用程式在裝置上。
    
如果註冊仍無法正常運作，[請嘗試其他疑難排解步驟](troubleshoot-mdm.md)。
  
## <a name="whats-the-difference-between-intune-and-mdm-for-office-365"></a>Intune 與 Office 365 MDM 之間的差異為何？

這兩個 MDM for Office 365 及 Intune 提供雲端式方案管理組織中的裝置。使用此[並排顯示比較](choose-between-mdm-and-intune.md)這兩項服務以協助您決定使用 Intune 或 MDM for Office 365 是否適合您。 
  
## <a name="how-do-policies-work-for-mdm-how-do-i-set-them-up-disable-them"></a>原則如何運作的 MDM？如何設定這些？停用吗？

針對 MDM 完成初始安裝 Office 365，您[建立的原則，並套用至使用者群組](create-device-security-policies.md)中的之後[移至 Office 365 安全性&amp;規範中心](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8)。原則套用至使用者的原則會要求使用者在註冊 Office 365 的 MDM 在其裝置裝置可用來存取 Office 365 資料之前。設定 「 原則會決定行動裝置，例如頻率必須重設密碼或是否需要資料加密設定。 
  
我們提供[建立及部署裝置安全性原則](create-device-security-policies.md)的逐步指示。您在 [安全性] 中建立的原則&amp;規範中心，而且您可以停用一或多個原則回到安全性&amp;規範中心及編輯原則可移除套用的群組。或者您可以選擇不要完全移除原則。
  
如果您想要排除特定使用者群組受到影響的原則，您可以將群組新增至排除群組。安全性&amp;規範中心，在 [**裝置**] 索引標籤上選取 [**管理裝置存取設定**] 並再新增至群組**是否有任何您想要排除的存取控制的安全性群組？** ] 區段中。 
  
## <a name="can-i-switch-from-exchange-activesync-device-management-to-mdm-for-office-365"></a>可以使用從切換 Exchange ActiveSync 裝置管理至 MDM for Office 365 吗？

如果您已經使用[Exchange ActiveSync 原則](https://go.microsoft.com/fwlink/?LinkId=615145)來管理行動裝置，您可以啟動 Office 365 使用 MDM[設定行動裝置管理 (MDM) Office 365 中](set-up-mobile-device-management.md)遵循的步驟。
  
當您套用您的 Office 365 使用者群組建立 MDM 的原則時，這些原則會覆寫 Exchange ActiveSync 行動裝置信箱原則與您先前已建立在 Exchange 系統管理中心這些使用者的裝置存取規則。 
  
裝置在 MDM 中註冊 Office 365 之後，都會被忽略任何 Exchange ActiveSync 行動裝置信箱原則 」 或 「 裝置存取規則套用至裝置。
  
## <a name="i-set-up-mdm-but-now-i-want-to-remove-it-what-are-the-steps"></a>設定 MDM 但現在我想要移除它。什麼是步驟？

然而，您不能只是"解除佈建"MDM for Office 365 後您已設定它。但是您可以從您已建立的裝置原則中移除使用者安全性群組來移除其為使用者群組。或者，停用它的任何人移除裝置原則，讓他們未備妥並不會強制執行。了解[如何關閉行動裝置管理 Office 365 中](turn-off-mdm.md)。
  
## <a name="still-need-help"></a>仍然需要說明嗎？

[![從 Office 365 社群論壇取得協助](media/12a746cc-184b-4288-908c-f718ce9c4ba5.png)](https://go.microsoft.com/fwlink/p/?LinkId=518605)
  
[![系統管理員：登入並建立服務要求](media/10862798-181d-47a5-ae4f-3f8d5a2874d4.png)]( https://go.microsoft.com/fwlink/p/?LinkId=519124)
  
[![系統管理員：呼叫支援](media/9f262e67-e8c9-4fc0-85c2-b3f4cfbc064e.png)](https://go.microsoft.com/fwlink/p/?LinkID=518322)
  

  

