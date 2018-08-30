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
# <a name="wipe-a-mobile-device-in-office-365"></a>在 Office 365 抹除行動裝置
  
您可以使用內建的行動裝置管理 Office 365 執行移除組織資訊、 選擇性清除或刪除行動裝置中的所有資訊並還原至其中心設定完全清除作業。
  
## <a name="what-to-know-before-you-begin"></a>要知道您開始之前

- 行動裝置可以儲存機密組織資訊，並提供您組織的 Office 365 資源的存取權。若要協助保護您的組織資訊，您可以執行完整抹除或選擇性抹除：
    
  - **完整抹除**： 刪除使用者的行動裝置，包括已安裝應用程式、 照片和個人資訊的所有資料。抹除完成時，裝置會還原為其原廠值。 
    
  - **選擇性擦去**： 移除僅組織資料和離開安裝應用程式、 照片和使用者的行動裝置上的個人資訊。 
    
- 清除裝置時 （完整抹除或選擇性抹除），當裝置已從受管理的裝置清單。
    
- 您可以設定自動擦去 （完全清除） 的行動裝置管理原則裝置之後使用者未成功嘗試輸入裝置的密碼特定的次數。請遵循的步驟[建立及部署裝置安全性原則](create-device-security-policies.md)。
    
- 如果您想要知道新使用者經驗都清除其裝置時，請參閱[功能的使用者和裝置影響？](wipe-a-mobile-device.md#BKMK_Impact)。
    
## <a name="wipe-a-mobile-device"></a>行動裝置

1. 移至 [[![按一下這裡以移至 Office 365 系統管理中心。](media/e00ba917-c3fb-4173-b344-43eb5c7eeb15.png)](https://portal.office.com/adminportal/home)。

2. 移至 [[移至 Office 365 安全性&amp;規範中心](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8)\> **資料外洩防護** \> **裝置管理**。
    
3. 選取您想要清除的裝置。
    
4. 選取您要執行遠端清除的類型。
    
  - 若要設為選擇性抹除並刪除僅 Office 365 組織資訊，在右窗格中，選取 [**選擇性擦去**]。
    
  - 若要設為完全清除並還原裝置以其原廠值，在右窗格中，選取 [**完整擦去**]。
    
![選取裝置，然後選擇 [不要將清除類型。](media/ac940abe-0c4a-404e-a842-a1ad2af13ce3.png)
  
5. 選取 **[是]** 確認。 
    
直到抹除完成後，**裝置狀態**會顯示為**RetirePending**或**RetireIssued**。
  
### <a name="how-do-i-know-it-worked"></a>如何知道這是否正常運作？

您無法再將看到的受管理的裝置清單中的行動裝置。
  
## <a name="why-would-you-want-to-wipe-a-device"></a>為什麼要選擇您要清除裝置？

有幾個理由清除裝置：
  
- 智慧型手機與平板電腦等行動裝置會變得更多的全功能所有的時間。這表示會在使用者儲存機密公司的資訊 （例如個人識別碼或 2 私人 3 機密通訊） 和存取在行進比較容易。如果其中一個行動裝置遺失或竊、 立即清除裝置能夠協助防止從結束的一面貴組織的資訊。
    
- 當使用者離開組織與在 MDM 中註冊 Office 365 的個人裝置時，有助於防止從依照選擇性抹除不必與該使用者的組織資訊。
    
- 如果您的組織為使用者提供行動裝置，您可能需要重新指派裝置的時候。完整抹除裝置之前先將它指派給新的使用者可幫助確保會刪除舊的擁有者任何機密資訊。
    
## <a name="whats-the-user-and-device-impact"></a>新功能的使用者和裝置的影響

清除立即傳送至行動裝置。裝置也會標示為不相容的 AAD。
  
下表說明內容已針對每個裝置類型時選擇性地清除裝置時。
  
|**內容的影響**|**Windows Phone 8.1**|**iOS 7.1+**|**Android 4+**|
|:-----|:-----|:-----|:-----|
|公司入口網站應用程式\*解除安裝。  <br/> |不適用  <br/> |✔  <br/> |不適用  <br/> |
|應用程式的存取控制其中的 MDM 支援的 Office 365 所主控的 office 365 應用程式資料是已移除 （目前 Outlook 和 OneDrive for Business）。應用程式不會移除。  <br/> Outlook for Android 不會移除快取的電子郵件。  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
|在裝置上不再強制執行原則設定已套用 MDM 由 Office 365 的裝置和使用者可以變更的設定。  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
|移除 MDM 所建立的 Office 365 的電子郵件設定檔並刪除裝置上快取的電子郵件。  <br/> |不適用  <br/> |✔  <br/> |不適用  <br/> |
   
> [!NOTE]
> \*公司入口網站應用程式為可用 iOS 應用程式商店及 Android 裝置播放存放區。 
  
## <a name="related-content"></a>相關內容

[管理 Office 365 中的行動裝置](set-up-mobile-device-management.md)
  

