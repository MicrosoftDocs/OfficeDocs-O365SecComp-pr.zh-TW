---
title: 設定自訂的修正-無法執行-Url 清單，使用 Office 365 ATP 安全連結
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
ms.collection:
- M365-security-compliance
description: 當您設定 ATP 安全連結原則時，您可以包含 do not 修正 ' 若要讓組織中的部分使用者造訪網站時，您在清單中包含的 Url 清單。
ms.openlocfilehash: 006dab44054f9cb707bb13d158588ab6606fab5c
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32264448"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-office-365-atp-safe-links"></a>設定自訂的修正-無法執行-Url 清單，使用 Office 365 ATP 安全連結

> [!IMPORTANT]
> 本文適用於商務版客戶。 如果您是家庭使用者尋找關於在 Outlook 中的安全連結的資訊，請參閱 <<c0>進階 Outlook.com 安全性。

使用[Office 365 進階威脅防護](office-365-atp.md)(ATP)，您的組織可以有[自訂封鎖的 Url](set-up-a-custom-blocked-urls-list-wtih-atp.md)中，如此當人員在 web 上按一下 [位址 (Url) 的電子郵件或特定的 Office 文件中，他們會禁止移至這些 Url。 您的組織也可以在組織中具有特定群組的自訂 「 不要重寫 」 清單。 「 不要重寫 」 清單讓某些人員能瀏覽否則封鎖由[Office 365 中的 ATP 安全連結](atp-safe-links.md)的 Url。 
  
本文說明如何指定的 Url 所排除的 ATP 安全連結掃描，和幾個重點謹記清單。

## <a name="set-up-a-do-not-rewrite-list"></a>設定 「 不可修正 」 清單

ATP 安全連結保護使用多個清單，包括您的組織封鎖的 Url 清單及 「 不要重寫 」 清單例外狀況。 如果您有必要的權限，您可以設定自訂 「 不要重寫 」 清單。 當您新增或編輯套用至組織中特定收件者的安全連結原則，您可以這麼做。 

若要編輯 （或定義） ATP 原則，您必須獲指派其中一個，如下表所述的角色：

|角色  |位置/方式指派  |
|---------|---------|
|Office 365 全域系統管理員 |若要購買 Office 365 註冊的人員是預設的全域系統管理員。 （請參閱[關於 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)，以了解更多）。         |
|安全性系統管理員 |Azure Active Directory 系統管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online 組織管理 |Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>或 <br>  PowerShell cmdlet (請參閱[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |

> [!TIP]
> 若要深入了解角色和權限，請參閱[中 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。

### <a name="to-view-or-edit-a-custom-do-not-rewrite-urls-list"></a>若要檢視或編輯自訂 「 不要重寫 」 Url 清單
  
1. 移至 [[https://protection.office.com](https://protection.office.com)並以您的公司或學校帳戶登入。 
    
2. 在左側導覽中，[**威脅管理** \> **原則** \> **安全連結**。
    
3. 在 [**原則套用至特定收件者**] 區段中，選擇 [**新增]** ([新增] 按鈕的格式類似於加上加號 ( **+**)) 來建立新的原則。 （或者，您可以編輯現有的原則。）<br/>![選擇 [新增若要將特定電子郵件收件者的安全連結原則](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
4. 指定的名稱和描述您的原則。
    
5. 中**不要重寫下列 Url** ] 區段中，選取 [**輸入有效的 URL** ] 方塊中，然後輸入 URL，然後選擇 [加號 （+）。 
    
6. 在**套用至**] 區段中，選擇 [**收件者是的成員**，然後再選擇您想要包含在原則中的群組。 選擇 [**新增**]，然後選擇 [**確定]**。
    
7. 當您完成新增 Url、 在螢幕的右下角，選擇 [**儲存**]。
    
> [!NOTE]
> 請務必檢閱您的組織自訂封鎖 Url 清單。 請參閱 <<c0>設定自訂封鎖 Url 清單使用 ATP 安全連結。 
  
## <a name="important-points-to-keep-in-mind"></a>請記住的重要事項

- 在 「 不要重寫 」 清單中指定任何 Url 中所排除的 ATP 安全連結掃描的收件者，您指定。
 
- 當您指定 「 不要重寫 」 清單中的 ATP 安全連結原則時，您可以包含最多三個萬用字元星號 (\*)。 使用萬用字元 (\*) 例如，假設為項目`contoso.com`，這不明確包含前置詞或子網域，like`http://`或`https://`。 這表示項目，例如：`contoso.com`類似於`*contoso.com*`「 不要重寫 」 清單。

- 如果您已在 「 不要重寫 」 清單中的 Url 清單，請務必檢閱該清單，並新增為適當的萬用字元。 例如，如果您現有的清單項目 like`http://contoso.com/a`及您想要包含子路徑，例如`http://contoso.com/a/b`在您的原則，萬用字元加入您的項目，讓它看起來像是`http://contoso.com/a*`。
    
- 不要在您指定 「 不要重寫 」 清單中的 Url 中包含正斜線 （/）。 例如，而不是輸入`contoso.com/`在 「 不要重寫 」 清單中，輸入`contoso.com`。
    
下列表格清單範例，您可以輸入和功能會影響這些項目有。
    
|**範例項目**|**其用途**|
|:-----|:-----|
|`*contoso.com*`  <br/> |允許特定收件者，請造訪網域、 子網域，以及路徑，例如： `http://www.contoso.com`、 `https://www.contoso.com`、 `https://maps.contoso.com`，或`http://www.contoso.com/a`  <br/> |
|`http://contoso.com/a`  <br/> |可讓特定的收件者，以瀏覽網站，例如`http://contoso.com/a`，但不是個子路徑 like`http://contoso.com/a/b`  <br/> |
|`http://contoso.com/a*`  <br/> |可讓特定的收件者，以瀏覽網站，例如`http://contoso.com/a`和子路徑 like`http://contoso.com/a/b`  <br/> |
   
 