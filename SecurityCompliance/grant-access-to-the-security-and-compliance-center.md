---
title: 讓使用者能夠存取 Office 365 安全性&amp;規範中心
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/18/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: 使用者必須被指派 Office 365 安全性權限&amp;規範中心之前他們可以管理任一其安全性或規範功能。
ms.openlocfilehash: 5055c64d914e15a6570c339ade48bb8f7e802ea7
ms.sourcegitcommit: a56fa2e184a2662fd8a7881ccea0891e9a26d497
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/11/2018
ms.locfileid: "27221064"
---
# <a name="give-users-access-to-the-office-365-security-amp-compliance-center"></a>讓使用者能夠存取 Office 365 安全性&amp;規範中心

使用者必須被指派 Office 365 安全性權限&amp;規範中心之前他們可以管理任一其安全性或規範功能。為 Office 365 全域管理員或安全性 OrganizationManagement 角色群組的成員&amp;規範中心，您可以指定給這些權限的使用者。使用者僅能管理您授與存取權的安全性或規範功能。 
  
您可以針對不同的權限的詳細資訊給使用者安全性&amp;規範中心、 取出[Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您必須是 Office 365 全域管理員或安全性 OrganizationManagement 角色群組的成員&amp;規範中心，以完成本文中的步驟。
    
- 角色群組的安全性&amp;規範中心可能會有類似給角色群組的名稱在 Exchange Online 中，但它們不相同。 
    
- Exchange Online 與安全性之間不共用角色群組成員資格&amp;規範中心。
    
## <a name="use-the-office-365-admin-center-to-give-another-user-access-to-the-security-amp-compliance-center"></a>使用 Office 365 系統管理中心來授與其他使用者存取安全性&amp;規範中心

1. [登入 Office 365 以及移至 [系統管理中心](https://go.microsoft.com/fwlink/p/?LinkId=525275)。
    
2. 在 Office 365 系統管理中心中，開啟 [**系統管理置中**] 和 [**安全性&amp;規範**。 
    
3. 安全性&amp;規範中心，請移至 [**權限**。
    
4. 從清單中選擇您要新增使用者並按一下 [**編輯**角色群組![編輯圖示](media/O365_MDM_CreatePolicy_EditIcon.gif)。
    
5. 在 [**成員**] 底下的角色群組的內容頁面上，按一下 [**新增**![新增圖示](media/ITPro-EAC-AddIcon.gif)選取名稱想要新增的使用者 （或使用者）。 
    
6. 當您已選取的所有使用者想要新增至角色群組，請按一下 [**新增-\> ** ] 和 [然後 **[確定]**。
    
7. 按一下 [**儲存**] 以將所做的變更儲存到角色群組。 
    
### <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？

1. 安全性&amp;規範中心，請移至 [**權限**。
    
2. 從清單中選取要檢視成員的角色群組。
    
3. 在向右的角色群組的詳細資訊，您可以檢視角色群組的成員。
    
## <a name="use-powershell-to-give-another-user-access-to-the-security-amp-compliance-center"></a>使用 PowerShell 來授與其他使用者存取安全性&amp;規範中心

1. [連線至 Office 365 的安全性與規範中心 PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。
    
2. 使用 **Add-RoleGroupMember** 命令，以將使用者新增至組織管理角色，如下列範例所示。 
    
  ```
  Add-RoleGroupMember -Identity "OrganizationManagement" -Member MatildaS
  
  ```

 **參數**
  
- _-Identity_ 是要新增成員的角色群組。 
    
- _成員_是要新增至角色群組的信箱、 萬用安全性群組 (USG) 或電腦。您可以指定只有一個成員一次。 
    
如需詳細的語法及參數的詳細資訊，請參閱[Add-rolegroupmember](https://go.microsoft.com/fwlink/p/?LinkId=510859)。
  
### <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？

若要確認您已指定的使用者存取安全性&amp;規範中心使用**Get-rolegroupmember**指令程式檢視組織管理角色群組中的成員在下列範例所示。 
  
```
Get-RoleGroupMember -Identity "OrganizationManagement"

```

如需詳細的語法及參數的詳細資訊，請參閱[Get-rolegroupmember](https://go.microsoft.com/fwlink/p/?LinkId=510860)。
  

