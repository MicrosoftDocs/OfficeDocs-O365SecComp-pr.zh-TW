---
title: 管理裝置註冊 Office 365 中的行動裝置管理
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/12/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 28dd276b-beeb-4c5b-8b22-7551186127fe
description: 請遵循下列步驟來設定設定行動裝置管理 (MDM) Office 365 中。
ms.openlocfilehash: 3a84b6904b866e07eb4efabe0f39041b282d0ba9
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272308"
---
# <a name="manage-devices-enrolled-in-mobile-device-management-in-office-365"></a>管理裝置註冊 Office 365 中的行動裝置管理

Office 365 內建的行動裝置管理可協助您保護及管理使用者的行動裝置 Iphone、 Ipad、 Androids、 like 及 Windows 電話。第一個步驟是登入 Office 365 和[設定 Office 365 MDM](set-up-mobile-device-management.md)。 
  
您已設定它，人員在組織中之後必須在服務中的 [[註冊其裝置](enroll-your-mobile-device.md)。然後您可以使用 Office 365 MDM 來協助管理組織中的裝置。例如，您可以使用裝置安全性原則來限制存取電子郵件或其他服務、 檢視裝置報告及裝置。您通常會前往[移至 Office 365 安全性&amp;規範中心](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8)執行這些工作。 
  
## <a name="device-management-tasks"></a>裝置管理工作

若要取得以裝置管理控制台]，請遵循下列步驟。 
  
1. 移至 Office 365 系統管理員中心。
    
2. 將 [搜尋] 欄位中輸入行動裝置管理和**行動裝置管理**從清單中選取的結果。 
    
    ![O365 搜尋欄位中的類型行動裝置管理員](media/e2e2f1c0-e543-431a-959b-e26c2ba328a7.png)
  
您已安裝的 Office 365 中取得 MDM 後，以下是如何在組織中管理行動裝置。 
  
|**若要執行…**|**執行**|
|:-----|:-----|
|清除裝置資料  <br/> |在裝置管理] 面板中，選取*裝置名稱*，然後**完整抹除**刪除所有資訊或刪除組織資訊僅在裝置上的 [**選擇性擦去**。  <br/> 請參閱[Office 365 的裝置](wipe-a-mobile-device.md)。  <br/> |
|使不受支援的裝置無法使用 Exchange ActiveSync 存取 Exchange 電子郵件  <br/> |在 [裝置管理] 面板中選取 [**封鎖**]。  <br/> |
|設定裝置原則就像密碼需求和安全性設定  <br/> |在 [裝置管理] 面板中按一下 [ \> **裝置安全性原則** \> **新增 +**。  <br/> 請參閱[建立及部署裝置安全性原則](create-device-security-policies.md)。  <br/> |
|檢視的封鎖的裝置清單  <br/> |裝置管理台中底下**選取 [檢視]** 選取 [**封鎖**]。  <br/> ||
|為使用者或使用者群組解除封鎖不相容或不支援的裝置  <br/> | 您可以根據您的情況下以解除封鎖不相容的裝置數種方式。選擇下列其中一項：<br/>  移除 [安全性] 群組原則已套用至使用者。移至**Office 365 系統管理中心** \> **群組**，然後選取 [* 群組名稱 *。按一下 [**編輯成員與系統管理員**。<br/>  使用者必須是從裝置原則成員的 [安全性] 群組中移除。移至 [**安全性&amp;規範中心**\> **安全性原則** \> **裝置安全性原則**。選取 [* 裝置原則名稱 *，然後按一下 [**編輯**![編輯圖示](media/O365_MDM_CreatePolicy_EditIcon.gif) \> **部署**。<br/>  解除封鎖所有不相容的裝置的裝置原則。移至 [**安全性&amp;規範中心**\> **安全性原則** \> **裝置安全性原則**。選取*裝置原則名稱*，然後按一下 [**編輯**![編輯圖示](media/O365_MDM_CreatePolicy_EditIcon.gif) \> **存取需求**。選取 [**允許存取和報告的衝突**。<br/>  若要解除封鎖不符合或不受支援的裝置的使用者或使用者群組，請前往 [移至**安全性&amp;規範中心**\> **安全性原則** \> **裝置管理** \> **管理裝置存取設定**.新增與您想要排除正在成員安全性群組封鎖至 Office 365 的存取。請參閱[建立、 編輯或刪除 Office 365 系統管理中心的 [安全性] 群組](https://support.office.com/article/55c96b32-e086-4c9e-948b-a018b44510cb)。<br/> |
|取得組織中裝置的相關詳細資料  <br/> |若要取得例如哪些裝置是參加授權及符合裝置安全性原則的詳細資訊，請遵循[取得由 MDM 管理裝置的相關詳細資料](get-details-about-mdm-managed-devices.md)中所述的步驟。  <br/> |
|讓 MDM 不再管理其裝置中移除使用者  <br/> |編輯 [安全性] 群組具有 MDM 若要移除之使用者的裝置管理原則。請參閱[建立、 編輯或刪除 Office 365 系統管理中心的 [安全性] 群組](https://support.office.com/article/55c96b32-e086-4c9e-948b-a018b44510cb)。<br/> 若要移除所有 Office 365 使用者 MDM，請參閱[關閉行動裝置管理 Office 365 中](turn-off-mdm.md)。  <br/> |
   

