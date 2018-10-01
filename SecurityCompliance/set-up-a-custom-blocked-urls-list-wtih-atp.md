---
title: 設定自訂封鎖 Url 清單使用 Office 365 ATP 安全連結
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
description: 閱讀本文以了解如何設定您的組織使用 Office 365 進階威脅保護封鎖 Url 的清單。封鎖的 Url 將會套用至電子郵件與根據您 ATP 安全連結原則的 Office 文件。
ms.openlocfilehash: 36d295e6924d2e9972c185657885fa25bd96bf08
ms.sourcegitcommit: 7032830867eb3fc71760e04b8342aff174c5d757
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/01/2018
ms.locfileid: "25353249"
---
# <a name="set-up-a-custom-blocked-urls-list-using-office-365-atp-safe-links"></a>設定自訂封鎖 Url 清單使用 Office 365 ATP 安全連結

與[Office 365 進階威脅保護](office-365-atp.md)(ATP)，您的組織可以自訂的網站位址 (Url) 會封鎖清單。當封鎖 URL 時，人員封鎖 URL 的連結按一下 [將被帶往類似下列影像[警告] 頁面上](atp-safe-links-warning-pages.md)： 
  
![封鎖此站台](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
封鎖的 Url 清單定義組織的 Office 365 安全性小組、 與 Office 365 ATP 安全連結原則所涵蓋組織中的每個人都適用於該清單。 
  
閱讀本文以了解如何為[ATP Office 365 中的安全連結](atp-safe-links.md)設定您的組織自訂封鎖 Url 的清單。
  
## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a>檢視或編輯封鎖 Url 的自訂清單

[Office 365 中的 ATP 安全連結](atp-safe-links.md)會使用多個清單，包括您的組織自訂封鎖的 Url 的清單。如果您擁有的必要權限，您可以設定您的組織自訂清單。藉由編輯貴組織的預設安全連結原則達成此目的。
  
1. 移至 [[https://protection.office.com](https://protection.office.com)和登入工作或學校帳戶。 
    
2. 在左導覽列中， **Threat management**] 下選擇 [**原則** \> **安全的連結**。
    
3. **套用至整個組織的原則**] 區段中選取 [**預設**]，然後選擇**編輯**（[編輯] 按鈕以鉛筆）。 
    
    ![按一下 [編輯] 以編輯您的預設原則的安全連結保護](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)
  
    這是您前往檢視您的封鎖 Url 的清單。請注意在第一筆、 您將不會有任何列出的 Url。
    
    ![封鎖的 Url 清單預設會套用至整個組織的安全連結原則。](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)
  
4. 選取 [**輸入有效的 URL** ] 方塊中，然後輸入 URL 並選擇 [加號 （+）。以下是一些事項謹記下列事項： 
    
  - 您可以指定僅限網域的 URL (例如`contoso.com`或`tailspintoys.com`)。這將會封鎖點閱上任何包含網域的 URL。
    
  - 不包含正斜線 ( **/**) 結尾的 URL。例如，而不是輸入`http://www.contoso.com/`、 輸入`http://www.contoso.com`。
    
  - 您可以包含多達三個萬用字元星號 (\*) 每個 URL。下表列出有一些您可以輸入及什麼 effect 這些項目範例。
    
|**範例項目**|**及其作用**|
|:-----|:-----|
|`contoso.com`或`*contoso.com*`  <br/> |封鎖的網域子網域，且路徑，例如`https://www.contoso.com`、 `http://sub.contoso.com`、 和`http://contoso.com/abc`  <br/> |
|`http://contoso.com/a`  <br/> |封鎖網站`http://contoso.com/a`但沒有其他子路徑 like`http://contoso.com/a/b`  <br/> |
|`http://contoso.com/a*`  <br/> |封鎖網站`http://contoso.com/a`及其他子路徑 like`http://contoso.com/a/b`  <br/> |
   
5. 在螢幕右下角新增 Url、 完成時，選擇 [**儲存**]。
    
## <a name="what-if-i-want-to-define-exceptions-for-certain-users-in-my-organization"></a>怎麼辦？ 在我的組織中定義的特定使用者的例外狀況

如果您想要能夠檢視 Url 可能會封鎖其他人的特定群組，您可以指定套用至特定收件者 ATP 安全連結原則。請參閱 ＜ [Set up 自訂 「 未修正"Url 清單使用 ATP 安全的連結](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)。
  
## <a name="related-topics"></a>相關主題

[Office 365 進階威脅防護](office-365-atp.md)
  
[Office 365 中的 ATP 安全連結](atp-safe-links.md)
  
[設定 Office 365 中的 ATP 安全連結原則](set-up-atp-safe-links-policies.md)
  
[Office 365 中的 ATP 安全附件](atp-safe-attachments.md)

[Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)
  

