---
title: 設定使用 Office 365 ATP Safe Links 自訂封鎖 Url 清單
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
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
ms.collection:
- M365-security-compliance
description: 了解如何設定的組織使用 Office 365 進階威脅防護的封鎖 Url 清單。 封鎖的 Url 會套用至電子郵件和 Office 文件，根據您的 ATP 安全連結原則。
ms.openlocfilehash: c5444e644a35688ea626004fbc6865df4ae645f9
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32264511"
---
# <a name="set-up-a-custom-blocked-urls-list-using-office-365-atp-safe-links"></a>設定使用 Office 365 ATP Safe Links 自訂封鎖 Url 清單

> [!IMPORTANT]
> 本文適用於商務版客戶。 如果您是家庭使用者尋找關於在 Outlook 中的安全連結的資訊，請參閱 <<c0>進階 Outlook.com 安全性。

使用[Office 365 進階威脅防護](office-365-atp.md)(ATP)，您的組織可以有自訂的網站位址 (Url) 會封鎖清單。 時封鎖 URL，按一下 [封鎖的 URL 連結的人員將被帶往[警告] 頁面上](atp-safe-links-warning-pages.md)，在類似下列映像的： 
  
![此網站會遭到封鎖](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
封鎖的 Url 清單由貴組織的 Office 365 安全性小組，所定義，該清單適用於 Office 365 ATP 安全連結原則所涵蓋組織中的每個人。 
  
閱讀本篇文章以了解如何為[Office 365 中的 ATP 安全連結](atp-safe-links.md)設定貴組織的自訂封鎖 Url 清單。
  
## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a>檢視或編輯自訂封鎖 Url 清單

[在 Office 365 中的 ATP 安全連結](atp-safe-links.md)會使用多個清單，包括您的組織自訂封鎖的 Url 清單。 如果您有必要的權限，您可以設定貴組織的自訂清單。 要這麼做，藉由編輯您的組織預設安全連結原則。

若要編輯 （或定義） ATP 原則，您必須獲指派其中一個，如下表所述的角色： 

|角色  |位置/方式指派  |
|---------|---------|
|Office 365 全域系統管理員 |若要購買 Office 365 註冊的人員是預設的全域系統管理員。 （請參閱[關於 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)，以了解更多）。         |
|安全性系統管理員 |Azure Active Directory 系統管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online 組織管理 |Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>或 <br>  PowerShell cmdlet (請參閱[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |

> [!TIP]
> 若要深入了解角色和權限，請參閱[中 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。

### <a name="to-view-or-edit-a-custom-blocked-urls-list"></a>若要檢視或編輯自訂封鎖的 Url 清單
  
1. 移至 [[https://protection.office.com](https://protection.office.com)並以您的公司或學校帳戶登入。 
    
2. 在左側導覽中，**威脅管理**] 下選擇 [**原則** \> **安全連結**。
    
3. 在 [**套用到整個組織的原則**] 區段中，選取 [**預設**]，然後選擇 [**編輯**（[編輯] 按鈕以鉛筆）。<br/>![按一下 [編輯] 以編輯您的預設原則，安全連結保護](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)<br/>這可讓您檢視您的封鎖 Url 清單。 首先，您可能沒有任何這裡列出的 Url。<br/>![封鎖預設安全連結原則中的 Url 清單](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)
  
4. 選取 [**輸入有效的 URL** ] 方塊中，輸入的 URL，然後選擇 [加號 (**+**)。 

5. 當您完成新增 Url、 在螢幕的右下角，選擇 [**儲存**]。
    
## <a name="a-few-things-to-keep-in-mind"></a>牢記的一些事項

當您將 Url 新增至清單時，請注意下列幾點： 

- 不包含正斜線 ( **/**) 結尾的 URL。 例如，而不是輸入`http://www.contoso.com/`，輸入`http://www.contoso.com`。
    
- 您可以指定僅限網域的 URL (例如`contoso.com`或`tailspintoys.com`)。 這將會封鎖點選上任何包含網域的 URL。

- 您可以指定子網域 (例如`toys.contoso.com*`) 而不會封鎖的完整網域 (例如`contoso.com`)。 這會封鎖按一下任何包含子網域的 URL，但它不會封鎖點選為包含完整的網域的 URL。  
    
- 您可以包含最多三個萬用字元星號 (\*) 每個 URL。 下表列出您可以輸入和功能會影響這些項目的一些範例有。
    
|**範例項目**|**其用途**|
|:-----|:-----|
|`contoso.com` 或 `*contoso.com*`  <br/> |封鎖的網域、 子網域和路徑，例如： `https://www.contoso.com`、 `http://sub.contoso.com`，和`http://contoso.com/abc`  <br/> |
|`http://contoso.com/a`  <br/> |封鎖網站，使`http://contoso.com/a`，但沒有其他子路徑 like`http://contoso.com/a/b`  <br/> |
|`http://contoso.com/a*`  <br/> |封鎖網站，使`http://contoso.com/a`和其他子路徑 like`http://contoso.com/a/b`  <br/> |
|`http://toys.contoso.com*`  <br/> |區塊的子網域 (在本例中為 「 toys 」)，但允許點選其他網域的 url (例如`http://contoso.com`或`http://home.contoso.com`)。  <br/> |
   

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a>如何在組織中定義的特定使用者的例外狀況

如果您想要能夠檢視 Url 可能會封鎖其他人的特定群組，您可以指定套用至特定收件者的 ATP 安全連結原則。 請參閱 <<c0>設定自訂 「 不要重寫 」 Url 清單使用 ATP 安全連結。
  

