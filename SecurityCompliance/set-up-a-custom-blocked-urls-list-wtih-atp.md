---
title: 使用 Office 365 ATP 安全連結設定自訂封鎖的 Url 清單
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
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
ms.collection:
- M365-security-compliance
description: 瞭解如何使用 Office 365 高級威脅防護來設定組織的封鎖 Url 清單。 封鎖的 Url 會根據您的 ATP 安全連結原則, 套用至電子郵件和 Office 檔。
ms.openlocfilehash: 4856d0ae76318c99a9c9c2404ef8a4cd700e4953
ms.sourcegitcommit: 4fedeb06a6e7796096fc6279cfb091c7b89d484d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/31/2019
ms.locfileid: "34652716"
---
# <a name="set-up-a-custom-blocked-urls-list-using-office-365-atp-safe-links"></a>使用 Office 365 ATP 安全連結設定自訂封鎖的 Url 清單

> [!IMPORTANT]
> 本文適用于擁有[Office 365 高級威脅防護](office-365-atp.md)的商務客戶。 如果您是尋找 Outlook 中安全連結相關資訊的家庭使用者, 請參閱[Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)。

透過[Office 365 高級威脅防護](office-365-atp.md)(ATP), 您的組織可以有已封鎖的網站位址 (url) 自訂清單。 當鎖定 URL 時, 按一下封鎖 URL 連結的人員會進入[警告頁面](atp-safe-links-warning-pages.md), 如下圖所示: 
  
![此網站被封鎖](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
封鎖的 Url 清單是由貴組織的 Office 365 安全小組所定義, 而且此清單適用于 Office 365 ATP 安全連結原則所涵蓋的組織中的所有人。 
  
如需瞭解如何為[Office 365 中的 ATP 安全連結](atp-safe-links.md)設定您組織的自訂封鎖 url 清單, 請閱讀本文。
  
## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a>查看或編輯已封鎖 Url 的自訂清單

[Office 365 中的 ATP 安全連結](atp-safe-links.md)使用數個清單, 包括您組織的自訂封鎖 url 清單。 如果您有必要的許可權, 您可以設定您組織的自訂清單。 您可以編輯組織的預設安全連結原則來執行這項操作。

若要編輯 (或定義) ATP 原則, 您必須獲指派下表所述的其中一個角色: 

|角色  |指派的位置/方式  |
|---------|---------|
|Office 365 全域系統管理員 |註冊購買 Office 365 的人員預設為全域系統管理員。 (請參閱[關於 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)以深入瞭解。)         |
|安全性系統管理員 |Azure Active Directory 系統管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online 組織管理 |Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>或 <br>  PowerShell Cmdlet (請參閱[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |

> [!TIP]
> 若要深入瞭解角色和許可權, 請參閱[Office 365 安全性&amp;與合規性中心的許可權](permissions-in-the-security-and-compliance-center.md)。

### <a name="to-view-or-edit-a-custom-blocked-urls-list"></a>若要查看或編輯自訂封鎖的 Url 清單
  
1. 移至[https://protection.office.com](https://protection.office.com) , 並使用您的公司或學校帳戶登入。 
    
2. 在左側導覽中的 [**威脅管理**] 下, 選擇 [**原則** \> **安全連結**]。
    
3. 在 [**適用于整個組織的原則**] 區段中, 選取 [**預設**], **** 然後選擇 [編輯] ([編輯] 按鈕就像是鉛筆)。<br/>![按一下 [編輯] 以編輯安全連結保護的預設原則](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)<br/>這可讓您查看封鎖的 Url 清單。 首先, 您可能不會在這裡列出任何 Url。<br/>![預設安全連結原則中的封鎖 Url 清單](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)
  
4. 選取 [**輸入有效的 url** ] 方塊, 輸入 URL, 然後選擇加號 (**+**)。 

5. 完成新增 Url 之後, 請在螢幕的右下角選擇 [**儲存**]。
    
## <a name="a-few-things-to-keep-in-mind"></a>請記住一些事項

當您將 Url 新增至清單時, 請牢記下列要點: 

- 不要在 URL 的結尾加入正**/** 斜線 ()。 例如, 您不用輸入`http://www.contoso.com/`, 而是`http://www.contoso.com`輸入。
    
- 您可以指定僅限網域的 URL (例如`contoso.com`或`tailspintoys.com`)。 這會封鎖任何包含網域的 URL 上的按一下。

- 您可以指定子域 (如`toys.contoso.com*`), 但不封鎖完整網域 (例如`contoso.com`)。 這會封鎖按一下任何包含子域的 URL, 但不會封鎖按一下包含完整網域的 URL。  
    
- 每個 URL 最多可以包含三個\*萬用字元星號 ()。 下表列出您可以輸入之專案的一些範例, 以及這些專案有何影響。
    
|**範例專案**|**功能**|
|:-----|:-----|
|`contoso.com` 或 `*contoso.com*`  <br/> |封鎖網域、子域及路徑, 例如`https://www.contoso.com`、和`http://sub.contoso.com``http://contoso.com/abc`  <br/> |
|`http://contoso.com/a`  <br/> |封鎖網站`http://contoso.com/a` , 但不會封鎖其他的子路徑, 如`http://contoso.com/a/b`  <br/> |
|`http://contoso.com/a*`  <br/> |封鎖網站`http://contoso.com/a`和其他子路徑, 如`http://contoso.com/a/b`  <br/> |
|`http://toys.contoso.com*`  <br/> |封鎖子域 (在此情況下為 "玩具"), 但允許按一下其他網域 Url ( `http://contoso.com`如`http://home.contoso.com`或)。  <br/> |
   

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a>如何為組織中的特定使用者定義例外狀況

如果您想要讓某些群組能夠查看其他人可能會封鎖的 Url, 您可以指定適用于特定收件者的 ATP 安全連結原則。 請參閱[設定自訂「不要重寫」 url 清單使用 ATP 安全連結](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)。
  

