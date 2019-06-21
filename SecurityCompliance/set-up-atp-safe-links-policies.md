---
title: 設定 Office 365 ATP 安全連結原則
ms.author: deniseb
author: denisebmsft
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/26/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: 設定安全連結原則, 以保護您的組織免受 Word、Excel、PowerPoint 和 Visio 檔案中的惡意連結, 以及電子郵件訊息。
ms.openlocfilehash: 505508771ae1e630d7d34fde9ee1525d19bd5039
ms.sourcegitcommit: b00c8fe1827d24f055a3076c10f284ff9ee3e04b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/20/2019
ms.locfileid: "35113257"
---
# <a name="set-up-office-365-atp-safe-links-policies"></a>設定 Office 365 ATP 安全連結原則

> [!IMPORTANT]
> 本文適用于擁有[Office 365 高級威脅防護](office-365-atp.md)的商務客戶。 如果您是尋找 Outlook 中安全連結相關資訊的家庭使用者, 請參閱[Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)。

[ATP 安全連結](atp-safe-links.md)( [Office 365 高級威脅防護](office-365-atp.md)(ATP) 的功能) 可以協助您的組織抵禦網路釣魚和其他攻擊中所使用的惡意連結。 如果您有[Office 365 安全性&amp;與合規性中心](permissions-in-the-security-and-compliance-center.md)的必要許可權, 您可以設定 ATP 安全連結原則, 以協助確保當人員按一下 [網頁位址 (url)] 時, 您的組織受到保護。 您可以設定您的 ATP 安全連結原則, 以掃描 Office 檔中的電子郵件和 Url 中的 Url。
  
[新功能會持續新增至 ATP](office-365-atp.md#new-features-in-office-365-atp)。 新增新功能後, 您可能需要調整現有的 ATP 安全連結原則。

## <a name="what-to-do"></a>待辦事項 
  
1. 檢查必要條件。
    
2. 查看和編輯適用于所有人的預設 ATP 安全連結原則。 例如, 您可以[為 ATP 安全連結設定您的自訂封鎖 url 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)。
    
3. 新增或編輯特定電子郵件收件者的原則, 包括[為 ATP 安全連結設定您的自訂「不要重寫」 url 清單](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)。
    
4. 瞭解 ATP 安全連結原則選項 (在本文中), 包括最近變更的設定。
    
## <a name="step-1-review-the-prerequisites"></a>步驟 1: 檢查必要條件

- 請確定您的組織有[Office 365 高級威脅防護](office-365-atp.md)。
    
- 請確定您有必要的許可權。 若要定義 (或編輯) ATP 原則, 您必須獲指派適當的角色。 下表說明一些範例: <br>

    |角色  |指派的位置/方式  |
    |---------|---------|
    |Office 365 全域系統管理員 |註冊購買 Office 365 的人員預設為全域系統管理員。 (請參閱[關於 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)以深入瞭解。)         |
    |安全性系統管理員 |Azure Active Directory 系統管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
    |Exchange Online 組織管理 |Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>或 <br>  PowerShell Cmdlet (請參閱[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |

    若要深入瞭解角色和許可權, 請參閱[Office 365 安全性&amp;與合規性中心的許可權](permissions-in-the-security-and-compliance-center.md)。

- 請確定 Office 用戶端已設定為使用[新式驗證](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)(這是針對 Office 檔中的 ATP 安全連結保護)。
    
- [瞭解 ATP 安全連結原則選項](#step-4-learn-about-atp-safe-links-policy-options)(在本文中)。 

- 最多可允許30分鐘, 以將新的或更新的原則傳播至所有 Office 365 資料中心。
    
## <a name="step-2-define-or-review-the-atp-safe-links-policy-that-applies-to-everyone"></a>步驟 2: 定義 (或查看) 適用于所有人的 ATP 安全連結原則

當您有[Office 365 高級威脅防護](office-365-atp.md)時, 您會有一個預設的 ATP 安全連結原則, 適用于您組織中的每個人。 請務必檢查, 如有需要, 請編輯您的預設原則。
  
1. 移至[https://protection.office.com](https://protection.office.com) , 並使用您的公司或學校帳戶登入。 
    
2. 在左側導覽中的 [**威脅管理**] 下, 選擇 [**原則\> ** **安全連結**]。
    
3. 在 [**適用于整個組織的原則**] 區段中, 選取 [**預設**], **** 然後選擇 [編輯] ([編輯] 按鈕就像是鉛筆)。<br/>![按一下 [編輯] 以編輯安全連結保護的預設原則](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)
  
4. 在 [**封鎖下列 url** ] 區段中, 指定您想要讓組織中的人員無法造訪的一或多個 url。 (請參閱[使用 ATP 安全連結設定自訂封鎖的 url 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md))。
    
5. 在 [**電子郵件以外的內容套用設定**] 區段中, 選取 (或清除) 您要使用的選項。 (我們建議您選取所有選項。) 
    
6. 選擇 [**儲存**]。
    
## <a name="step-3-add-or-edit-atp-safe-links-policies-that-apply-to-specific-email-recipients"></a>步驟 3: 新增 (或編輯) 適用于特定電子郵件收件者的 ATP 安全連結原則

在您檢查 (或編輯) 適用于所有人的預設 ATP 安全連結原則之後, 下一步是定義將會套用至特定收件者的其他原則。 例如, 您可以透過定義其他原則來指定預設原則的例外狀況。 
  
1. 移至[https://protection.office.com](https://protection.office.com) , 並使用您的公司或學校帳戶登入。 
    
2. 在左側導覽中的 [**威脅管理**] 下, 選擇 [**原則**]。
    
3. 選擇 [**安全連結**]。
    
4. 在 [套用**至特定**收件者的原則] 區段中, 選擇 [**新增**] ([新增**+**] 按鈕就像加號符號 ())。<br/>![選擇 [新增] 以新增特定電子郵件收件者的安全連結原則](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
5. 指定原則的名稱、描述及設定。<br/>**範例:** 若要設定名為「不直接按下」的原則, 但不允許您組織中特定群組的人員按一下至特定網站, 而不允許任何 ATP 安全連結保護, 您可以指定下列建議設定: 
    
  - 在 [**名稱**] 方塊中, 輸入 [無直接按一下]。
    
  - 在 [**描述**] 方塊中, 輸入如所示的描述, 以防止特定群組中的人員按一下以透過不使用 ATP 安全連結驗證的網站。
    
  - 在 [**選取動作**] 區段中, 選擇 [**開啟**]。
    
  - 選取 [**使用安全附件掃描可下載的內容**]。
    
  - 如果可使用此選項, 請選取 **[套用安全連結至組織內傳送的郵件**]。
    
  - 選取 [不**允許使用者按一下以原始 URL**]。
    
  - (這是選用的)在 [**不要重新寫入下列 url** ] 區段中, 指定一或多個被視為對您組織是安全的 url。 (請參閱[設定自訂「不要重寫」 url 清單使用 ATP 安全連結](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md))
    
  - 在 [套用**至**] 區段中, 選擇 [**收件者是的成員**], 然後選擇您要包含在原則中的群組。 選擇 [**新增**], 然後選擇 **[確定]**。
    
6. 選擇 [**儲存**]。
    
## <a name="step-4-learn-about-atp-safe-links-policy-options"></a>步驟 4: 瞭解 ATP 安全連結原則選項

當您設定或編輯您的 ATP 安全連結原則時, 會看到幾個可用選項。 如果您想知道這些選項是什麼, 下表會說明每個選項及其效果。 請記住, 有兩種主要的 ATP 安全連結原則可供定義或編輯:
- 套用至所有人的[預設原則](#default-policy-options);並  
- 特定收件者[的其他原則](#policies-that-apply-to-specific-email-recipients) 

### <a name="default-policy-options"></a>預設原則選項

預設原則選項適用于您組織中的每個人。

|此選項  |執行動作  |
|---------|---------|
| **封鎖下列 Url** <br/>    | 可讓您的組織擁有自動封鎖的自訂 Url 清單。 當使用者按一下此清單中的 URL 時, 會出現[警告頁面](atp-safe-links-warning-pages.md), 說明 URL 被封鎖的原因。 若要深入瞭解, 請參閱[使用 Office 365 ATP 安全連結設定自訂封鎖的 url 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)。 |
| **Office 365 專業增強版, Office for iOS 和 Android** <br/>    | 選取此選項時, 會將 ATP 安全連結保護套用至 Windows 或 Mac OS 上的 Word、Excel 及 PowerPoint 檔案中的 Url、iOS 上的 Office 檔、在 Windows 上的 Visio 2016, 以及 Office 應用程式的 web 版本 (Word、PowerPoint、Excel 及OneNote), 前提是使用者已登入 Office 365。 |
| **不要追蹤使用者按一下 ATP 安全連結的時間** <br/>  | 選取此選項時, 不會儲存 Word、Excel、PowerPoint 及 Visio 檔中的 Url 資料。  <br/> |
|**不要讓使用者點擊至原始 URL 的 ATP 安全連結** <br/> |選取此選項時, 使用者將無法繼續進行 [[警告] 頁面](atp-safe-links-warning-pages.md)到決定為惡意的 URL。  <br/> |

### <a name="policies-that-apply-to-specific-email-recipients"></a>適用于特定電子郵件收件者的原則

|此選項  |執行動作  |
|---------|---------|
|**關閉** <br/> |不掃描電子郵件中的 Url。  <br/> 可讓您定義例外規則, 例如不會掃描特定收件者群組之電子郵件中的 Url 的規則。  <br/> |
|**On** <br/> |在使用者按一下電子郵件訊息中的 Url 時, 會將 Url 寫入使用 ATP 安全連結保護來路由使用者。  <br/> 針對封鎖或惡意 Url 的清單, 來檢查 URL。  <br/> |
|**使用安全附件掃描可下載的內容** <br/> |選取此選項時, 會掃描指向可下載內容的 Url。  <br/> |
|**將安全連結套用至組織內傳送的郵件** <br/> | 當此選項可供使用並選取時, 會將 ATP 安全連結保護套用至組織中的人員所傳送的電子郵件, 前提是電子郵件帳戶是在 Office 365 中主控。  <br/> |
|**不追蹤使用者按一下** <br/> |選取此選項時, 不會儲存 [來自外部寄件者的電子郵件中的 Url 的資料]。 目前不支援在組織內傳送的電子郵件訊息中, 按一下 [追蹤連結]。  <br/> |
|**不要允許使用者按一下 [原始 URL]。** <br/> |選取此選項時, 使用者將無法繼續進行 [[警告] 頁面](atp-safe-links-warning-pages.md)到決定為惡意的 URL。  <br/> |
|**不要重新寫入下列 Url** <br/> |會將 Url 保留原樣。 保留自訂的安全 Url 清單, 不需要掃描組織中特定的電子郵件收件者群組。  如需詳細資訊, 請參閱[設定自訂「不要重寫」 url 清單](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)(包括支援萬用字元星號 (\*) 的最新變更)。  <br/> |
   
## <a name="next-steps"></a>後續步驟

一旦您的 ATP 安全連結原則已準備就緒, 您就可以透過查看報表來瞭解 ATP 在 orgnization 中的運作方式。 若要深入瞭解, 請參閱下列資源:

- [查看 Office 365 的報告高級威脅防護](view-reports-for-atp.md)

- [在安全性&amp;與合規性中心使用 Explorer](use-explorer-in-security-and-compliance.md)

隨時掌握 ATP 的新功能。 請造訪[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap?filters=O365), 瞭解要[新增至 ATP 的新功能](office-365-atp.md#new-features-in-office-365-atp)。