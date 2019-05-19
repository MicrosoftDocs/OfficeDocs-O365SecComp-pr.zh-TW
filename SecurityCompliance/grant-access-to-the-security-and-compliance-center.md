---
title: 讓使用者能夠存取 Office 365 安全性&amp;合規性中心
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: 使用者必須獲指派 Office 365 安全性中的權限&amp;合規性中心之前他們可以管理其安全性或規範功能。
ms.openlocfilehash: aa0d1e9af6eb547bbb145d06cabfc431028ec4f0
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154295"
---
# <a name="give-users-access-to-the-office-365-security-amp-compliance-center"></a>讓使用者能夠存取 Office 365 安全性&amp;合規性中心

使用者必須獲指派 Office 365 安全性中的權限&amp;合規性中心之前他們可以管理其安全性或規範功能。 為 Office 365 全域系統管理員或安全性 OrganizationManagement 角色群組的成員&amp;合規性中心，您可以授與這些權限給使用者。 使用者只能管理您授予權利給他們的安全性或符合性功能。 
  
如需不同的權限您可以授予使用者安全性&amp;合規性中心，嗎？ 請查看[中 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您必須是 Office 365 全域系統管理員或安全性 OrganizationManagement 角色群組的成員&amp;合規性中心，以完成本文中的步驟。
    
- 基於安全性的角色群組&amp;合規性中心可能會有類似的角色群組的名稱，在 Exchange Online 中，但是兩者並不相同。 
    
- Exchange Online 和安全性之間不會共用角色群組成員資格&amp;合規性中心。
    
## <a name="use-the-office-365-admin-center-to-give-another-user-access-to-the-security-amp-compliance-center"></a>使用 Office 365 系統管理中心將另一個使用者存取權授與安全性&amp;合規性中心

1. [登入 Office 365 並移至系統管理中心](https://go.microsoft.com/fwlink/p/?LinkId=525275)。
    
2. 在 Office 365 系統管理中心中，開啟 [**系統管理中心**，然後按一下**安全性&amp;規範**。 
    
3. 安全性&amp;合規性中心，移至 [**權限**。
    
4. 從清單中，選擇 [角色群組，您想要新增使用者並按一下 [**編輯**![編輯圖示](media/O365_MDM_CreatePolicy_EditIcon.gif)。
    
5. 在角色群組的 [屬性] 頁面 [**成員**] 底下，按一下 [**新增**![加入圖示](media/ITPro-EAC-AddIcon.gif)選取名稱您想要新增的使用者 （或使用者）。 
    
6. 當您已選取的所有使用者想要新增至角色群組，請按一下 [**新增-\> ** ]，然後 **[確定]**。
    
7. 按一下 [儲存]，將變更儲存到角色群組。 
    
### <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？

1. 安全性&amp;合規性中心，移至 [**權限**。
    
2. 從清單中，選取要檢視的成員的角色群組。
    
3. 在右側，在 [角色群組的詳細資訊，您可以檢視角色群組的成員。
    
## <a name="use-powershell-to-give-another-user-access-to-the-security-amp-compliance-center"></a>使用 PowerShell 將另一個使用者存取權授與安全性&amp;合規性中心

1. [連線至 Office 365 安全性 & 合規性中心 PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。
    
2. 使用 **Add-RoleGroupMember** 命令，以將使用者新增至組織管理角色，如下列範例所示。 
    
  ```
  Add-RoleGroupMember -Identity "OrganizationManagement" -Member MatildaS
  
  ```

 **參數**
  
- _-Identity_ 是要新增成員的角色群組。 
    
- _成員_是要新增至角色群組的信箱、 萬用安全性群組 (USG) 或電腦。 您一次只能指定一個成員。 
    
如需詳細的語法及參數的詳細資訊，請參閱[Add-rolegroupmember](https://go.microsoft.com/fwlink/p/?LinkId=510859)。
  
### <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？

若要確認您已給予使用者存取安全性&amp;合規性中心，組織管理角色群組中，檢視的成員使用**Get-rolegroupmember**指令程式，在下列範例所示。 
  
```
Get-RoleGroupMember -Identity "OrganizationManagement"

```

如需詳細的語法及參數的詳細資訊，請參閱[Get-rolegroupmember](https://go.microsoft.com/fwlink/p/?LinkId=510860)。
  

