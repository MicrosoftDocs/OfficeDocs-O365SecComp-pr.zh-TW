---
title: 使用 Office 365 ATP 安全連結, 設定自訂的不重新寫入 Url 清單
ms.author: deniseb
author: denisebmsft
manager: laurawi
audience: Admin
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
description: 當您設定 ATP 安全連結原則時, 可以包含 [不修正] 的 Url 清單, 讓組織中的某些人能夠造訪您的清單中所包含的網站。
ms.openlocfilehash: a7f8f041832d7d5935ea959073d2b11cc6bdcf53
ms.sourcegitcommit: 4fedeb06a6e7796096fc6279cfb091c7b89d484d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/31/2019
ms.locfileid: "34652726"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-office-365-atp-safe-links"></a>使用 Office 365 ATP 安全連結, 設定自訂的不重新寫入 Url 清單

> [!IMPORTANT]
> 本文適用于擁有[Office 365 高級威脅防護](office-365-atp.md)的商務客戶。 如果您是尋找 Outlook 中安全連結相關資訊的家庭使用者, 請參閱[Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)。

透過[Office 365 高級威脅防護](office-365-atp.md)(ATP), 您的組織可以有[自訂封鎖的 url](set-up-a-custom-blocked-urls-list-wtih-atp.md), 例如, 當使用者按一下電子郵件訊息或特定 Office 檔中的網頁位址 (url) 時, 這些 url 就不會傳送至這些 url。 您的組織也可以為組織中的特定群組提供自訂「不要重寫」清單。 「不要重新寫入」清單可讓某些人造訪[Office 365 中的 ATP 安全連結](atp-safe-links.md)所封鎖的 url。 
  
本文說明如何指定從 ATP 安全連結掃描中排除的 Url 清單, 以及請記住的一些重要要點。

## <a name="set-up-a-do-not-rewrite-list"></a>設定「不要重寫」清單

ATP 安全連結保護使用數個清單, 包括您組織的封鎖 Url 清單和「不要重寫」清單中的例外狀況。 如果您有必要的許可權, 您可以設定您的自訂「不要重寫」清單。 當您新增或編輯適用于組織中特定收件者的安全連結原則時, 就會執行此動作。 

若要編輯 (或定義) ATP 原則, 您必須獲指派下表所述的其中一個角色:

|角色  |指派的位置/方式  |
|---------|---------|
|Office 365 全域系統管理員 |註冊購買 Office 365 的人員預設為全域系統管理員。 (請參閱[關於 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)以深入瞭解。)         |
|安全性系統管理員 |Azure Active Directory 系統管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online 組織管理 |Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>或 <br>  PowerShell Cmdlet (請參閱[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |

> [!TIP]
> 若要深入瞭解角色和許可權, 請參閱[Office 365 安全性&amp;與合規性中心的許可權](permissions-in-the-security-and-compliance-center.md)。

### <a name="to-view-or-edit-a-custom-do-not-rewrite-urls-list"></a>若要查看或編輯自訂「不要重寫」 Url 清單
  
1. 移至[https://protection.office.com](https://protection.office.com) , 並使用您的公司或學校帳戶登入。 
    
2. 在左側導覽中, 在 [**威脅管理** \> **原則** \> **安全連結**] 底下。
    
3. 在 [套用**至特定**收件者的原則] 區段中, 選擇 [**新增**] ([新增**+**] 按鈕類似加號 ()) 來建立新的原則。 (或者, 您也可以編輯現有的原則)。<br/>![選擇 [新增] 以新增特定電子郵件收件者的安全連結原則](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
4. 指定原則的名稱和描述。
    
5. 在 [**不要重新寫入下列 url** ] 區段中, 選取 [**輸入有效的 url** ] 方塊, 然後輸入 URL, 然後選擇加號 (+)。 
    
6. 在 [套用**至**] 區段中, 選擇 [**收件者是的成員**], 然後選擇您要包含在原則中的群組。 選擇 [**新增**], 然後選擇 **[確定]**。
    
7. 完成新增 Url 之後, 請在螢幕的右下角選擇 [**儲存**]。
    
> [!NOTE]
> 請務必檢查您組織的已封鎖 Url 的自訂清單。 請參閱[使用 ATP 安全連結設定自訂封鎖的 url 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)。 
  
## <a name="important-points-to-keep-in-mind"></a>需要記住的重要要點

- 您在「不要重寫」清單中指定的任何 Url 都會從 ATP 安全連結中排除, 以掃描您指定的收件者。
 
- 當您為 ATP 安全連結原則指定「不要重寫」清單時, 最多可以包含三個萬用字元星號 (\*)。 會假設\*萬用字元 () `contoso.com`, 例如, 不明確包含首碼或子域之類的專案, 例如`http://`或。 `https://` 這表示專案, 例如`contoso.com`類似于您`*contoso.com*`的「不要重寫」清單。

- 如果您的 [不要重新寫入] 清單中已經有 Url 清單, 請務必檢查該清單, 並視需要新增萬用字元。 例如, 如果您現有的清單中有類似`http://contoso.com/a`的專案, 而且您想要在`http://contoso.com/a/b`您的原則中包含類似的子路徑, 請在您的`http://contoso.com/a*`專案中新增萬用字元, 讓它看起來像這樣。
    
- 不要在您在「不要重寫」清單中指定的 Url 中包含正斜線 (/)。 例如, 請輸入`contoso.com/` `contoso.com`, 而不是在「不要重寫」清單中輸入。
    
下表列出您可以輸入之專案的範例, 以及這些專案有何影響。
    
|**範例專案**|**功能**|
|:-----|:-----|
|`*contoso.com*`  <br/> |允許特定收件者造訪網域、子域和路徑, 例如`http://www.contoso.com`、 `https://www.contoso.com` `https://maps.contoso.com`、或`http://www.contoso.com/a`  <br/> |
|`http://contoso.com/a`  <br/> |允許特定收件者造訪類似`http://contoso.com/a`的網站, 但不允許像這樣的子路徑`http://contoso.com/a/b`  <br/> |
|`http://contoso.com/a*`  <br/> |允許特定的收件者造訪像`http://contoso.com/a`這樣的子網站和子路徑`http://contoso.com/a/b`  <br/> |
   
 