---
title: Office 365 ATP 安全連結
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.date: 03/05/2019
ms.topic: overview
f1_keywords:
- "197503"
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: 安全連結功能提供 Office 文件和電子郵件訊息中的超連結的時間按一下 [的驗證。 若要從網路釣魚和其他攻擊保護您的組織使用安全連結。
ms.openlocfilehash: 340faca2c869f051325babcb51b6cb6c976c98c8
ms.sourcegitcommit: ed822a776d3419853453583e882f3c61ca26d4b2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2019
ms.locfileid: "30410718"
---
# <a name="office-365-atp-safe-links"></a>Office 365 ATP 安全連結

## <a name="overview-of-office-365-atp-safe-links"></a>Office 365 ATP 安全連結概觀

> [!IMPORTANT]
> 本文適用於 Office 365 企業版客戶。 如果您使用 Outlook.com、 Office 365 家用版、 Office 365 個人或，而且您正在尋找在 Outlook 中的安全連結的相關資訊，請參閱 <<c0>進階 Outlook.com 安全性。

Office 365 ATP 安全連結 （[進階威脅防護](office-365-atp.md)的一部分） 可協助保護您的組織藉由提供的[電子郵件](#how-atp-safe-links-works-with-email)和[Office 文件](#how-atp-safe-links-works-with-office-documents)中的網址 (Url) 的時間按一下 [驗證。 保護是透過[ATP 安全連結原則](set-up-atp-safe-links-policies.md)設定 Office 365 安全性小組的定義。 
  
一旦您 ATP 安全連結原則已備妥，Office 365 全域系統管理員、 安全性管理員和安全性讀取者可以[檢視報告，進階威脅防護](view-reports-for-atp.md)。 這些報告中的資訊可協助您採取進一步的步驟，以保護您的組織或研究安全性事件的安全性小組。

為[ATP 會新增新的功能](office-365-atp.md#new-features-in-office-365-atp)，您的 Office 365 安全性小組可以新增或編輯您的組織[ATP 安全連結原則](set-up-atp-safe-links-policies.md)。 此外，您可能會注意到的變更和增強功能，例如我們新修訂的[警告頁面](atp-safe-links-warning-pages.md)以及在 Outlook 中呈現的原生連結。
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a>ATP 安全連結的運作方式與 Url 以電子郵件

在高的層級，以下是 ATP 安全連結保護中的運作方式的 Url （裝載於 Office 365，不在內部） 的電子郵件：
  
1. 人員會收到電子郵件訊息，其中有些包含的 Url。
    
2. 所有電子郵件通過 Exchange Online Protection，其中網際網路通訊協定 (IP) 及信封篩選，簽章型惡意程式碼防護，反垃圾郵件和反惡意軟體篩選器。 
    
3. 電子郵件會送達人民收件匣。
    
4. 使用者登入 Office 365，並移至其電子郵件收件匣。
    
5. 使用者開啟電子郵件訊息，並按一下電子郵件訊息中的 URL。
    
6. ATP 安全連結功能立即檢查才能開啟之網站的 URL。 URL 被識別為惡意，/ 安全封鎖。
    
    - 如果 URL 包含在[自訂 「 不要重寫 」 Url 清單](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)將套用至使用者原則的網站，網站會隨即開啟。 
    
    - 組織[自訂封鎖的 Url 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)中包含的網站 URL 時，會開啟[警告] 頁面](atp-safe-links-warning-pages.md)。 
    
    - 已判定為惡意的網站 URL 時，會開啟[警告] 頁面](atp-safe-links-warning-pages.md)。 
    
    - 如果 URL 會前往可下載的檔案，且貴組織的[ATP 安全連結原則](set-up-atp-safe-links-policies.md)設定可掃描這類內容，會檢查可下載的檔案。 
    
    - 如果 URL 會決定為了安全起見，網站會隨即開啟。
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a>ATP 安全連結的運作方式與 Url 中的 Office 文件

在高的層級，以下是 ATP 安全連結保護中的運作方式 Url 的 Office 365 專業增強版應用程式 （目前版本的 Word、 Excel 及 PowerPoint Windows 或 Mac、 iOS 或 Android 裝置，Visio 在 Windows、 OneNote Online 和 Office Online 上的 Office 應用程式上）：
  
1. 人員在其電腦、 智慧型手機或平板電腦上安裝 Office 365 專業增強版。 （或者，他們會使用 Office Online 在其瀏覽器中）。
    
2. 使用者開啟 Word、 Excel、 PowerPoint 或 Visio，並為 Office 365 企業版使用其公司或學校帳戶登入。 文件中包含的 Url。
    
3. 當使用者在 [文件中的 URL 時，連結會檢查 ATP 安全連結服務。
    
      - 如果 URL 是包含在[自訂 「 不要重寫 」 Url 清單](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)將套用至使用者原則的網站，該使用者不會採取至網站。 
    
      - URL 是包含在組織的[自訂封鎖的 Url 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)的網站，如果使用者不會採取至[警告頁面](atp-safe-links-warning-pages.md)。
    
      - 如果已決定為惡意的網站 URL，使用者會採取至[警告頁面](atp-safe-links-warning-pages.md)。
    
      - 如果 URL 會前往可下載的檔案，且[ATP 安全連結原則](set-up-atp-safe-links-policies.md)設定可掃描這類的下載項目，會檢查可下載的檔案。 
    
      - URL 會被視為安全，如果使用者不會採取至網站。

## <a name="how-to-get-atp-safe-links-protection"></a>如何取得 ATP 安全連結保護

**首先，請確定您的訂閱包含[進階威脅防護](office-365-atp.md)**。 ATP 隨附於在 [訂閱，例如[Microsoft 365 企業版](https://www.microsoft.com/microsoft-365/enterprise/home)、 [Microsoft 365 商務版](https://www.microsoft.com/microsoft-365/business)、 Office 365 企業版 E5、 Office 365 教育版 A5 等。如果貴組織擁有不包含 Office 365 ATP 的 Office 365 訂閱，您可能可以當作附加元件購買 ATP。 如需詳細資訊，請參閱下列資源： 

- [Office 365 進階威脅防護方案和價格](https://products.office.com/exchange/advance-threat-protection)

- [Office 365 進階的威脅防護服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) 
  
**接下來，確定已定義的 ATP 安全連結原則**。 （請參閱[設定 Office 365 ATP 安全連結原則](set-up-atp-safe-links-policies.md)）。ATP 安全連結功能已啟用：
  
- ATP 安全連結原則設定電子郵件和 Office 文件。 （請參閱[設定 Office 365 中的 ATP 安全連結原則](set-up-atp-safe-links-policies.md)）。

- Office 365 用戶端應用程式都設定為使用新式驗證 （這是在 Office 文件中的 ATP 安全連結保護）。 （請參閱[適用於 Office 2016 的新式驗證](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)）。 
    
- 使用者已登入 Office 365 中，使用其公司或學校帳戶。 （請參閱[登入 Office 或 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426)）。
    
- 貴組織的電子郵件通過 Exchange Online Protection。  

**也請確定您具有必要權限**。 若要定義 （或編輯） ATP 原則，您必須獲指派適當的角色。 下表說明一些範例：

|角色  |位置/方式指派  |
|---------|---------|
|Office 365 全域系統管理員 |若要購買 Office 365 註冊的人員是預設的全域系統管理員。 （請參閱[關於 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)，以了解更多）。         |
|安全性系統管理員 |Azure Active Directory 系統管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online 組織管理 |Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>或 <br>  PowerShell cmdlet (請參閱[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |
    
## <a name="how-to-make-sure-atp-safe-links-protection-is-in-place"></a>如何讓確定 ATP 安全連結保護已經準備就緒

以全域管理員或安全性系統管理員，請務必定期檢閱您的[ATP 安全連結原則](set-up-atp-safe-links-policies.md)。 ATP 安全連結原則決定是否保護套用至電子郵件訊息中的超連結只，或 Url Office 文件中。

ATP 安全連結原則已備妥之後，可以看到貴組織的安全性小組您的組織由[進階威脅防護的檢視報表](view-reports-for-atp.md)ATP 安全連結保護正常運作的方式，請參閱。 

## <a name="example-scenarios"></a>範例案例
  
下表說明 ATP 安全連結保護其中可能或可能無法就地幾個案例。 （在所有這些情況下，我們假設該組織有 Office 365 企業版 E5。）
  
|**範例案例**|**ATP 安全連結保護不會在此情況下套用嗎？**|
|:-----|:-----|
|Jean 是群組的有涵蓋 Url 電子郵件和 Office 文件中的 ATP 安全連結原則成員。 Jean 有人傳送時，開啟 PowerPoint 簡報，然後按一下 [在簡報中的 URL。  <br/> |可以。 所定義的 ATP 安全連結原則套用到 Jean 的群組、 Jean 的電子郵件，並 Jean 隨即開啟，只要 Jean 登入的 Word、 Excel、 PowerPoint 或 Visio 文件和 Windows、 iOS 或 Android 裝置上使用 Office 365 專業增強版。  <br/> |
|Chris 的組織，不全域或安全性中的系統管理員已尚未定義任何 ATP 安全連結原則。 Chris 會收到一封電子郵件包含惡意網站的 URL。 Chris 是察覺不到 URL 為惡意，並按下的連結。  <br/> |否。 對組織中的每個人都涵蓋 Url 的預設原則必須定義要就地保護的順序。  <br/> |
|在 Pat 的組織，不全域或安全性系統管理員已定義，或尚未編輯任何 ATP 安全連結原則。 Pat 開啟 Word 文件，並按一下 [在檔案中的 URL。  <br/> |否。 原則，其中包含 Office 文件必須定義要就地保護的順序。 請參閱 <<c0>設定 Office 365 中的 ATP 安全連結原則。  <br/> |
|Lee 的組織已有的 ATP 安全連結原則`http://tailspintoys.com`列為遭到封鎖的網站。 Lee 收到電子郵件訊息包含的 URL `http://tailspintoys.com/aboutus/trythispage`。 Lee 按一下 URL。  <br/> |這取決於是否整個網站及其所有的清單中包含它的子頁面封鎖 Url。 請參閱 <<c0>設定自訂封鎖 Url 清單使用 ATP 安全連結。  <br/> |
|李明，Jean 的同事，將電子郵件傳送至 Jean，不了解電子郵件包含惡意 URL。  <br/> |這取決於是否 ATP 安全連結原則所定義的組織內傳送的電子郵件。 請參閱 <<c0>設定 Office 365 中的 ATP 安全連結原則。  <br/> |


  

