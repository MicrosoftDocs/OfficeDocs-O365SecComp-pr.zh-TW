---
title: 設定 Office 365 ATP 安全連結原則
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
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
description: 若要防止惡意連結在 Word、 Excel、 PowerPoint 及 Visio 檔案，以及電子郵件訊息中的組織設定安全連結原則。
ms.openlocfilehash: d02866b7ab9a4da30a14aa0c55a42935926e99e3
ms.sourcegitcommit: 1658be51e2c21ed23bc4467a98af74300a45b975
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/26/2019
ms.locfileid: "30862475"
---
# <a name="set-up-office-365-atp-safe-links-policies"></a>設定 Office 365 ATP 安全連結原則

> [!IMPORTANT]
> 本文適用於 Office 365 企業版客戶。 如果您使用 Outlook.com、 Office 365 家用版、 Office 365 個人或，而且您正在尋找在 Outlook 中的安全連結的相關資訊，請參閱 <<c0>進階 Outlook.com 安全性。

[ATP 安全連結](atp-safe-links.md)， [Office 365 進階威脅防護](office-365-atp.md)(ATP) 功能可協助保護組織免於用於網路釣魚和其他攻擊的惡意連結。 如果您有必要[Office 365 安全性的權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)，您可以設定 ATP 安全連結原則以協助確保，當使用者按一下 [網站位址 (Url)，保護您的組織。 ATP 安全連結原則可以設定要掃描電子郵件中的 Url 和 Office 文件中的 Url。
  
[新功能會都將持續加入到 ATP](office-365-atp.md#new-features-in-office-365-atp)。 當新增新功能，您可能需要進行調整，以您現有的 ATP 安全連結原則。

## <a name="what-to-do"></a>要執行的動作 
  
1. 請先檢閱必要條件。
    
2. 檢閱並編輯預設的 ATP 安全連結原則套用至所有人。 例如，您可以[設定 ATP 安全連結您自訂封鎖 Url 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)。
    
3. 新增或編輯的特定電子郵件收件者，包括[設定自訂 「 不要重寫 」 Url 清單 ATP 安全連結](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)原則。
    
4. 了解 ATP 安全連結原則選項 （本文），包括設定最近的變更。
    
## <a name="step-1-review-the-prerequisites"></a>步驟 1： 檢閱必要條件

- 請確定您的組織有[Office 365 進階威脅防護](office-365-atp.md)。
    
- 請確定您具有必要的權限。 若要定義 （或編輯） ATP 原則，您必須獲指派適當的角色。 下表說明一些範例： <br>

    |角色  |位置/方式指派  |
    |---------|---------|
    |Office 365 全域系統管理員 |若要購買 Office 365 註冊的人員是預設的全域系統管理員。 （請參閱[關於 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)，以了解更多）。         |
    |安全性系統管理員 |Azure Active Directory 系統管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
    |Exchange Online 組織管理 |Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>或  <br>  PowerShell cmdlet (請參閱[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |

    若要深入了解角色和權限，請參閱[中 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。

- 請確定 Office 用戶端已設定為使用[新式驗證](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)（這是在 Office 文件中的 ATP 安全連結保護）。
    
- [了解 ATP 安全連結原則選項](#step-4-learn-about-atp-safe-links-policy-options)（本文）。 

- 允許最多 30 分鐘，即會散佈至所有 Office 365 資料中心新增或更新原則。
    
## <a name="step-2-define-or-review-the-atp-safe-links-policy-that-applies-to-everyone"></a>步驟 2： 定義 （或檢閱） 適用於所有人的 ATP 安全連結原則

當您有[Office 365 進階威脅防護](office-365-atp.md)時，您必須套用至貴組織使用者的預設 ATP 安全連結原則。 請務必檢閱，以及如有需要編輯您的預設原則。
  
1. 移至 [[https://protection.office.com](https://protection.office.com)並以您的公司或學校帳戶登入。 
    
2. 在左側導覽中，**威脅管理**] 下選擇 [**原則\>****安全連結**。
    
3. 在 [**套用到整個組織的原則**] 區段中，選取 [**預設**]，然後選擇 [**編輯**（[編輯] 按鈕以鉛筆）。<br/>![按一下 [編輯] 以編輯您的預設原則，安全連結保護](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)
  
4. 在 [**封鎖下列 Url** ] 區段中，指定您想要防止人員而無法從組織中的一或多個 Url。 （請參閱[設定自訂封鎖 Url 清單使用 ATP 安全連結](set-up-a-custom-blocked-urls-list-wtih-atp.md)）。
    
5. 中 **，將套用到內容以外的電子郵件設定**] 區段中，選取 （或清除） [您想要使用的選項。 （我們建議您選取的所有選項）。 
    
6. 選擇 [**儲存**]。
    
## <a name="step-3-add-or-edit-atp-safe-links-policies-that-apply-to-specific-email-recipients"></a>步驟 3： 新增 （或編輯） 套用至特定的電子郵件收件者的 ATP 安全連結原則

您已檢閱 （或編輯） 適用於所有人的預設 ATP 安全連結原則之後下, 一步是定義會套用至特定收件者的其他原則。 例如，您也可以定義其他原則，以指定例外狀況至您的預設原則。 
  
1. 移至 [[https://protection.office.com](https://protection.office.com)並以您的公司或學校帳戶登入。 
    
2. 在左側導覽中，**威脅管理**] 下選擇 [**原則**]。
    
3. 選擇 [**安全連結**]。
    
4. 在 [**原則套用至特定收件者**] 區段中，選擇 [**新增]** ([新增] 按鈕的格式類似於加上加號 ( **+**))。<br/>![選擇 [新增若要將特定電子郵件收件者的安全連結原則](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
5. 指定原則的名稱、描述及設定。<br/>**範例：** 若要設定的原則名為 「 沒有直接點選 「 不允許按特定網站沒有 ATP 安全連結保護您組織中的特定群組中的人員，您可以指定下列建議設定： 
    
  - 在 [**名稱**] 方塊中，輸入沒有直接點選。
    
  - 在 [**描述**] 方塊中，輸入描述類似，防止人員從按一下透過沒有 ATP 安全連結驗證網站的特定群組中。
    
  - 在 [**選取動作**] 區段中，選擇 [**上**]。
    
  - 選取 [**使用安全附件以掃描可下載內容**]。
    
  - 如果使用此選項，則選取 [**套用到組織內傳送郵件的安全連結**]。
    
  - 選取 [**不允許使用者透過按一下原始 url**。
    
  - （這是選用的）在 [**不要重寫下列 Url** ] 區段中，指定會視為是可在您的組織中安全的一個或多個 Url。 （請參閱[設定自訂 「 不要重寫 」 Url 清單使用 ATP 安全連結](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)）
    
  - 在**套用至**] 區段中，選擇 [**收件者是的成員**，然後再選擇您想要包含在原則中的群組。 選擇 [**新增**]，然後選擇 [**確定]**。
    
6. 選擇 [**儲存**]。
    
## <a name="step-4-learn-about-atp-safe-links-policy-options"></a>步驟 4： 了解 ATP 安全連結原則選項

當您設定或編輯您的 ATP 安全連結原則時，會看到數個選項可用。 您會知道這些選項為何下, 表說明每一個，其效果。 請記住，有兩個主要的幾種類型的定義或編輯的 ATP 安全連結原則：
- 適用於所有人;[預設原則](#default-policy-options)和  
- 額外的[特定收件者原則](#policies-that-apply-to-specific-email-recipients) 

### <a name="default-policy-options"></a>預設原則選項

預設原則選項套用至您的組織中的每個人。

|此選項  |執行動作  |
|---------|---------|
| **封鎖下列 Url** <br/>    | 可讓您的組織有自訂清單的自動封鎖的 Url。 當使用者按一下此清單中的 URL 時，他們將予以說明為什麼封鎖 URL 的[警告頁面](atp-safe-links-warning-pages.md)。 若要了解更多，請參閱[設定自訂封鎖 Url 清單使用 Office 365 ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md)。 |
| **Office 365 專業增強版、 Office for iOS 和 Android** <br/>    | ATP 安全連結保護選取此選項時，會套用至 Windows 或 Mac 作業系統]、 [iOS 或 Android 裝置上的 Office 文件視窗，然後 Office Online （線上 Word、 PowerPoint Online、 Excel Online 中，在 Visio 2016 上的 Word、 Excel 及 PowerPoint 檔案中的 Url和 OneNote Online 中），提供使用者已登入 Office 365。 |
| **當使用者按一下 ATP 安全連結不追蹤** <br/>  | 選取此選項時，請按一下 [資料]，如 Word、 Excel、 PowerPoint 及 Visio 文件中的 Url 不會儲存。  <br/> |
|**不要讓使用者按一下原始 url 的 ATP 安全連結** <br/> |選取此選項時，使用者無法繼續處理過[警告頁面](atp-safe-links-warning-pages.md)判定為惡意 URL。  <br/> |

### <a name="policies-that-apply-to-specific-email-recipients"></a>套用至特定的電子郵件收件者原則

|此選項  |執行動作  |
|---------|---------|
|**關閉** <br/> |不會掃描電子郵件訊息中的 Url。  <br/> 可讓您定義的例外狀況規則，例如不會掃描特定群組的收件者的電子郵件訊息中 Url 的規則。  <br/> |
|**On** <br/> |修正 Url 路由使用者可透過 ATP 安全連結保護，當使用者按一下電子郵件訊息中的 Url。  <br/> 檢查時按下針對遭封鎖或惡意 Url 清單的 URL。  <br/> |
|**使用安全附件以掃描可下載內容** <br/> |選取此選項時，會掃描可下載內容所指向的 Url。  <br/> |
|**套用到組織內傳送郵件的安全連結** <br/> | 當可用及選取此選項即 ATP 安全連結保護會套用到您組織所提供的電子郵件帳戶中的人員之間傳送的郵件會裝載於 Office 365 的電子郵件。  <br/> |
|**不追蹤使用者點選** <br/> |選取此選項時，請按一下 [資料]，如未儲存來自外部寄件者的電子郵件中的 Url。 目前不支援 URL 按一下追蹤組織內傳送的電子郵件內的連結。  <br/> |
|**不允許使用者按一下原始 URL** <br/> |選取此選項時，使用者無法繼續處理過[警告頁面](atp-safe-links-warning-pages.md)判定為惡意 URL。  <br/> |
|**不要重寫下列 Url** <br/> |只要在離開 Url。 會保留不需要掃描您的組織中的電子郵件收件者的特定群組的安全 Url 的自訂清單。  請參閱 <<c0>設定自訂 「 不要重寫 」 Url 清單使用 ATP 安全連結如需詳細資訊，包括最近的變更，以支援萬用字元星號 (<b1></b1>)。  <br/> |
   
## <a name="next-steps"></a>後續步驟

一旦您 ATP 安全連結原則已備妥，您可以看到 ATP 運作為貴組織中檢視報告。 請參閱若要了解更多的下列資源：

- [檢視 Office 365 進階威脅防護報告](view-reports-for-atp.md)

- [使用檔案總管中的安全性&amp;合規性中心](use-explorer-in-security-and-compliance.md)

掌握即將 ATP 的新功能。 請造訪[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)，並了解[新功能，將會新增 ATP](office-365-atp.md#new-features-in-office-365-atp)。