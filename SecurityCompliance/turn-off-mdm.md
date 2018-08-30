---
title: 如何關閉 Office 365 中的行動裝置管理
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
- GPA150
- MET150
ms.assetid: 2709cafb-0a8b-44bc-8494-7e2fccfa2b19
description: 請遵循下列步驟來停止 MDM 原則與 Office 365 組織中的行動裝置要強制執行。
ms.openlocfilehash: 6b8f0036ed999b10263f5cc074df27175769e604
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272218"
---
# <a name="how-to-turn-off-mobile-device-management-in-office-365"></a>如何關閉 Office 365 中的行動裝置管理

有效地關閉 MDM for Office 365，您可以組群的人 （安全性群組所定義） 移除裝置管理原則，或移除自己的原則。 
  
- 透過從您已建立的裝置原則移除使用者安全性群組中移除使用者的群組。 
    
- 停用 MDM 所有人來移除所有 MDM 裝置原則。 
    
這些選項會在您的組織中移除 MDM 強制執行裝置。然而，您不能只是"解除佈建"MDM for Office 365 後您已設定它。
  
> [!IMPORTANT]
> 請注意在使用者的裝置上的影響當您從原則中移除使用者安全性群組或移除自己的原則。例如，電子郵件設定檔和快取的電子郵件可能會移除，根據裝置。請參閱：[功能的不同的裝置類型上的安全性原則影響吗？](create-device-security-policies.md#what-is-the-impact-of-security-policies-on-different-device-types)
  
## <a name="remove-user-security-groups-from-mdm-device-policies"></a>從 MDM 裝置原則中移除使用者安全性群組

1. 移至 [**安全性&amp;規範中心**\> **資料外洩防護** \> **裝置安全性原則**。
    
2. 選取裝置原則]，然後按一下 [![編輯圖示](media/O365-MDM-CreatePolicy-EditIcon.gif)**編輯原則**。
    
3. [**部署**中，按一下 [ **-移除**。
    
    在 [**群組**] 選取 [安全性] 群組。
    
4.  按一下 [**移除**]。
    
5. 按一下 [儲存]****。
    
## <a name="remove-mdm-device-policies"></a>移除 MDM 裝置原則

1. 移至 [**安全性&amp;規範中心**\> **安全性原則** \> **裝置安全性原則**。
    
2. 選取裝置原則]，然後再按一下![映像的資源回收筒可圖示。](media/b8bfa783-c0b5-46d9-9570-8a385088e8fe.png) **刪除原則**。
    
3. 在 [**警告**] 對話方塊中按一下 [**是**]。 
    

