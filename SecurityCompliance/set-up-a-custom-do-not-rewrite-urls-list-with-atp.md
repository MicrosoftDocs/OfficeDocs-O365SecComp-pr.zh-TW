---
title: 設定使用 Office 365 ATP 安全連結的自訂不要-not-修正 Url 清單
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
description: 當您設定好您 ATP 安全連結原則時，您可以包含不要 not 修正 ' 要讓組織中某些使用者瀏覽您在您的清單中包含的網站 Url 的清單。
ms.openlocfilehash: 5eb2d09f1d1d77fa9d6ffdb9f14ba9e7522da287
ms.sourcegitcommit: d6a28c4f6db6a676ca960173e8ff8f17d4aa1c4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2019
ms.locfileid: "29755284"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-office-365-atp-safe-links"></a>設定使用 Office 365 ATP 安全連結的自訂不要-not-修正 Url 清單

與[Office 365 進階威脅保護](office-365-atp.md)(ATP)，您的組織可以[自訂封鎖的 Url](set-up-a-custom-blocked-urls-list-wtih-atp.md)如此人員時在 web 上按一下 [位址 (Url) 中有電子郵件訊息或特定 Office 文件、 其禁止移至這些 Url。您的組織也可以在組織中有特定群組中 「 未修正"的自訂清單。"不 rewrite"清單可讓有些人以造訪否則封鎖透過[ATP Office 365 中的安全連結](atp-safe-links.md)的 Url。 
  
本文說明如何在指定的清單中所排除的 ATP 安全連結掃描，和幾個重點牢記的 Url。

## <a name="set-up-a-do-not-rewrite-list"></a>設定 「 未修正 」 清單

ATP 安全連結保護使用多個清單，包括您的組織已封鎖的 Url 清單和 「 未修正"例外狀況的清單。如果您擁有的必要權限，您可以設定自訂的 「 未修正 」 清單。當您新增或編輯套用至組織中特定收件者的安全連結原則，您可以這麼做。 

若要編輯 （或定義） ATP 原則，您必須具有角色如下表所示的其中一個：

|角色  |Where/如何指派  |
|---------|---------|
|Office 365 全域管理員 |若要購買 Office 365 設定簽署者為預設的全域系統管理員。（請參閱若要深入了[解 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)）。         |
|安全性管理員 |Azure Active Directory 系統管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online 組織管理 |Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>或 <br>  PowerShell cmdlet (請參閱[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |

> [!TIP]
> 若要深入了解角色和權限，請參閱[Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。

### <a name="to-view-or-edit-a-custom-do-not-rewrite-urls-list"></a>若要檢視或編輯自訂 「 未修正"Url 清單
  
1. 移至 [[https://protection.office.com](https://protection.office.com)和登入工作或學校帳戶。 
    
2. 在左導覽列中，[ **Threat management** \> **原則** \> **安全的連結**。
    
3. 在 [**原則套用至特定收件者**] 區段中選擇 [**新增**] ([新增] 按鈕的格式類似於加號 ( **+**)) 來建立新的原則。（或者，您可以編輯現有的原則。）<br/>![選擇 [新增] 可為特定電子郵件收件者新增的安全連結原則](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
4. 指定的名稱和描述您的原則。
    
5. **未修正下列 Url** ] 區段中選取 [**輸入有效的 URL** ] 方塊中，然後輸入 URL，然後選擇 [加號 （+）。 
    
6. **套用至**] 區段中選擇 [**收件者是成員**，然後按您想要包含在您的原則中的群組。選擇 [**新增**]，然後選擇 [ **[確定]**。
    
7. 在螢幕右下角新增 Url、 完成時，選擇 [**儲存**]。
    
> [!NOTE]
> 請務必檢閱您的組織自訂清單之已封鎖的 Url。請參閱 ＜ [Set up 自訂封鎖 Url 清單使用 ATP 安全的連結](set-up-a-custom-blocked-urls-list-wtih-atp.md)。 
  
## <a name="important-points-to-keep-in-mind"></a>請記住的重要事項

- 您指定的收件者所掃描的 ATP 安全連結不包含任何您在 「 未修正"] 清單中指定的 Url。
 
- 當您指定"未修正"ATP 安全連結原則的清單時，您可以包含多達三個萬用字元星號 (\*)。萬用字元 (\*) 會假設其值的項目如`contoso.com`，這不明確包含前置字元或子網域，如`http://`或`https://`。這表示項目，例如`contoso.com`類似於`*contoso.com*`您 「 未修正"的清單。

- 如果您已"未修正 」 清單中的 Url 清單，請務必檢閱該清單並視情況新增萬用字元。例如，如果您現有的清單項目，像是`http://contoso.com/a`與您想要包含子路徑 like`http://contoso.com/a/b`在您的原則中加入萬用字元項目讓它看起來像是`http://contoso.com/a*`。
    
- 不要"未修正 」 清單中指定的 Url 中包含正斜線 （/）。例如，而不是輸入`contoso.com/`您 「 未修正 」 清單中，輸入`contoso.com`。
    
具有下表列出您可以輸入和範例什麼 effect 這些項目。
    
|**範例項目**|**及其作用**|
|:-----|:-----|
|`*contoso.com*`  <br/> |允許特定收件者瀏覽網域、 子網域，以及路徑，例如`http://www.contoso.com`、 `https://www.contoso.com`、 `https://maps.contoso.com`，或`http://www.contoso.com/a`  <br/> |
|`http://contoso.com/a`  <br/> |允許特定收件者類似的網站瀏覽`http://contoso.com/a`，但不是個子路徑 like`http://contoso.com/a/b`  <br/> |
|`http://contoso.com/a*`  <br/> |允許特定收件者類似的網站瀏覽`http://contoso.com/a`及 like 個子路徑`http://contoso.com/a/b`  <br/> |
   
 