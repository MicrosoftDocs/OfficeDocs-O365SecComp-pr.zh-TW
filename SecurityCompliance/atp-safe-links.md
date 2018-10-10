---
title: Office 365 ATP 安全連結
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: overview
f1_keywords:
- "197503"
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: 安全的連結功能所提供 Office 文件和電子郵件訊息中的超連結的時間按一下 [的驗證。若要從網路釣魚和其他攻擊保護您的組織使用安全的連結。
ms.openlocfilehash: 75703cbe6b6a5a5d102570288bb20e6814d095fc
ms.sourcegitcommit: 099bbfb1d16b251fd5cf18ec6515faaf9a989176
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/09/2018
ms.locfileid: "25454370"
---
# <a name="office-365-atp-safe-links"></a>Office 365 ATP 安全連結

## <a name="overview-of-office-365-atp-safe-links"></a>Overview of Office 365 ATP 安全連結

Office 365 ATP 安全連結 （ATP 安全連結） （搭配[Office 365 ATP 安全附件](atp-safe-attachments.md)） 是一組提供的[Office 365 進階威脅保護](office-365-atp.md)企業組織的一部分的安全性功能。ATP 安全連結可協助保護您的組織所提供的[電子郵件](#how-atp-safe-links-works-with-email)和[Office 文件](#how-atp-safe-links-works-with-office-documents)中的網址 (Url) 的時間按一下 [驗證。保護是透過[ATP 安全連結原則](set-up-atp-safe-links-policies.md)設定 Office 365 安全性小組的定義。 
  
一旦您 ATP 安全連結原則已備妥、 Office 365 全域管理員、 安全性管理員及安全性讀取者可以在[進階威脅保護的檢視報告](view-reports-for-atp.md)。這些報告中的資訊可協助您需要進一步的步驟來保護您的組織或研究安全性事件的安全性小組。
         
### <a name="how-atp-safe-links-works-with-urls-in-email"></a>ATP 安全連結中的運作方式與 Url 電子郵件

在高層級，以下是 ATP 安全連結 protection 中的運作方式的 Url （架設在 Office 365 中，不在內部部署） 的電子郵件：
  
1. 人員接收電子郵件訊息，部份只包含 Url。
    
2. 所有電子郵件通過 Exchange Online Protection，其中網際網路通訊協定 (IP) 及信封篩選、 簽章型惡意程式碼保護，反垃圾郵件和反惡意軟體篩選器會套用。 
    
3. 電子郵件會進入人的收件匣。
    
4. 使用者登入 Office 365 中，並移至其電子郵件收件匣。
    
5. 使用者開啟電子郵件訊息，並按一下在電子郵件訊息的 URL。
    
6. ATP 安全連結功能立即檢查才能開啟之網站的 URL。為封鎖惡意或安全可識別的 URL。
    
    - 如果 URL 包含在[自訂 「 未修正"Url 清單](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)將套用至使用者原則的網站，網站會隨即開啟。 
    
    - 如果組織的[自訂封鎖的 Url 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)中包含的網站 URL，[警告] 頁面](atp-safe-links-warning-pages.md)隨即開啟。 
    
    - 如果已決定要惡意的網站 URL，[警告] 頁面](atp-safe-links-warning-pages.md)隨即開啟。 
    
    - 如果您的組織[ATP 安全連結原則](set-up-atp-safe-links-policies.md)中已掃描這類內容和 URL 會前往可下載的檔案，則會檢查可下載的檔案。 
    
    - 如果 URL 決定要安全，網站會隨即開啟。
    
### <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a>ATP 安全連結中的運作方式與 Url 的 Office 文件

在高層級，以下是 ATP 安全連結 protection 中的運作方式 Url 的 Office 365 ProPlus 應用程式 （Word、 Excel 及 PowerPoint Windows 或 Mac 上 iOS 或 Android 裝置、 Windows、 OneNote Online 與 Office Online 上的 Visio 的 Office 應用程式上的目前版本）：
  
1. 人員在其電腦、 智慧型手機、 或平板電腦上安裝 Office 365 ProPlus。（或者，使用 Office Online 在其瀏覽器）。
    
2. 使用者開啟 Word、 Excel、 PowerPoint 或 Visio 並登入 Office 365 企業版使用其工作或學校的帳戶。文件包含 Url。
    
3. 當使用者按一下在文件中的 URL 時、 連結會檢查 ATP 安全連結服務。
    
  - 如果 URL 包含在[自訂 「 未修正"Url 清單](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)將套用至使用者原則的網站，該使用者會對網站進行。 
    
  - 如果組織的[自訂封鎖的 Url 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)中包含的網站 URL，使用者會前往[警告] 頁面](atp-safe-links-warning-pages.md)。
    
  - 如果已決定要惡意的網站 URL，使用者會前往[警告] 頁面](atp-safe-links-warning-pages.md)。
    
  - 如果[ATP 安全連結原則](set-up-atp-safe-links-policies.md)中已掃描這類下載項目和 URL 會前往可下載的檔案，則會檢查可下載的檔案。 
    
  - 如果 URL 會被視為安全，使用者會進行瀏覽網站。

## <a name="how-to-get-atp-safe-links-protection"></a>如何取得 ATP 安全連結保護

ATP 安全連結功能是[進階威脅保護](office-365-atp.md)，其中包含在 Office 365 企業版 E5、 Microsoft 365 業務及 Microsoft 365 企業版的一部分。如果貴組織要使用另一個 Office 365 企業版訂閱，可做為附加元件購買進階威脅保護。如需詳細資訊，請參閱[Office 365 平台服務說明： Office 365 安全性&amp;規範中心](https://technet.microsoft.com/en-us/library/dn933793.aspx)和[購買或編輯企業版的 Office 365 的附加元件](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6)。
  
ATP 安全連結功能已啟用：
  
- **ATP 安全連結原則已設定**用於電子郵件和 Word、 Excel、 PowerPoint 及 Visio 文件。（請參閱[Set up ATP Office 365 中的安全連結原則](set-up-atp-safe-links-policies.md)）。

- **Office 365 用戶端應用程式設定為使用經過驗證**。（請參閱[Office 2016 現代驗證](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)）。 
    
- **使用者已登入 Office 365**使用其工作或學校的帳戶。（請參閱[登入 Office 或 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426)）。
    
- **貴組織的電子郵件裝載 Office 365 中**，不在內部伺服器。 
    
### <a name="how-to-make-sure-atp-safe-links-protection-is-in-place"></a>如何讓確定 ATP 安全連結保護已備妥

請參閱 ATP 安全連結保護您的組織的運作方式的其中一個好方法是檢視[進階威脅 Protection 的報告](view-reports-for-atp.md)。此外，以全域管理員或安全性管理員，請務必檢閱您[ATP 安全連結原則](set-up-atp-safe-links-policies.md)。ATP 安全連結原則會決定是否保護適用於電子郵件訊息中有超連結只或 Url 中的 Office 文件。

### <a name="example-scenarios-where-atp-safe-links-protection-might-or-might-not-be-in-place"></a>ATP 安全連結保護可能的位置或可能不是備妥的範例案例
  
下表說明 ATP 安全連結保護可能的位置或備妥可能不是幾個案例。（在所有這些情況下，我們假設組織有 Office 365 企業版 E5。）
  
|**範例案例**|**ATP 安全連結保護沒有在此例中套用吗？**|
|:-----|:-----|
|Jean 是群組的有 ATP 安全連結原則涵蓋 Url 電子郵件和 Office 文件中的成員。Jean 有人傳送，開啟 PowerPoint 簡報，然後按一下 [在簡報中的 URL。  <br/> |[是]。定義 ATP 安全連結原則套用至 Jean 的群組、 Jean 的電子郵件、 和 Jean 隨即開啟，只要 Jean 登入的 Word、 Excel、 PowerPoint 或 Visio 文件及 Windows、 iOS 或 Android 裝置上使用 Office 365 ProPlus。  <br/> |
|Chris 的組織，不通用或安全性管理員已尚未定義任何 ATP 安全連結原則。Chris 會收到電子郵件包含惡意網站的 URL。Chris 會察覺不到 URL 為惡意並按一下連結。  <br/> |[否]。針對在組織中所有人涵蓋 Url 的預設原則必須定義備妥要保護的順序。  <br/> |
|Pat 的組織，不通用或安全性管理員已定義或尚未編輯的任何 ATP 安全連結原則。Pat 開啟 Word 文件並按一下檔案中的 URL。  <br/> |包含 Office 文件的 [否]。 的原則必須定義備妥要保護的順序。請參閱 ＜ [Set up Office 365 中的 ATP 安全連結原則](set-up-atp-safe-links-policies.md)。<br/> |
|Lee 的組織具有的 ATP 安全連結原則`http://tailspintoys.com`列為封鎖網站。Lee 接收電子郵件訊息內含 URL `http://tailspintoys.com/aboutus/trythispage`。Lee 點選 URL。<br/> |整個網站與所有的清單中包括它的子頁面是否封鎖 Url 而定。請參閱 ＜ [Set up 自訂封鎖 Url 清單使用 ATP 安全的連結](set-up-a-custom-blocked-urls-list-wtih-atp.md)。<br/> |
|李明、 Jean 的同事將電子郵件傳送至 Jean、 不知道電子郵件包含惡意 URL。  <br/> |針對在組織內傳送的電子郵件是否定義 ATP 安全連結原則而定。請參閱 ＜ [Set up Office 365 中的 ATP 安全連結原則](set-up-atp-safe-links-policies.md)。<br/> |

## <a name="new-features-are-continually-being-added-to-atp-safe-links"></a>新功能所需要經常新增至 ATP 安全連結

我們會繼續新增 ATP 安全連結的新功能。有時 ATP 安全連結原則以檢閱和更新為呼叫的新功能。以下是數個範例：
  
- 從開始落後年 10 月 2017年，ATP 安全連結保護會延伸至 Url 中電子郵件時的 Url 是以套用至 Office 365 ProPlus 的文件，例如 Word、 Excel、 PowerPoint 及 Visio 在 Windows，以及 Office iOS 及 Android 裝置上的應用程式。（請確定您使用[Office 的現代驗證](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)）。
    
- 從開始年 3 月 2018年，ATP 安全連結保護會延伸至套用至組織內的人員之間所寄送的電子郵件。（請務必[檢閱](set-up-atp-safe-links-policies.md)並編輯 ATP 安全連結原則）。
 
- 從開始 2018年第二個半，ATP 安全連結保護會延伸至套用至 Office Online （線上 Word、 Excel Online、 PowerPoint Online 和 OneNote Online） 和 Office 365 ProPlus mac 上的 Url（請務必[檢閱](set-up-atp-safe-links-policies.md)並編輯 ATP 安全連結原則）。

- 開始在 9 月 2018年、 [Office 365 ATP 警告頁面](atp-safe-links-warning-pages.md)] 功能的新的色彩配置、 詳細資訊及能夠繼續而不管網站授與警告和建議。 
 
- 開始在年 10 月 2018年及後續的幾個月內啟用，當使用者使用 Outlook Web 應用程式 (OWA) 或 Outlook、 ATP 安全連結轉譯原始 Url 不會修正 Url。（我們呼叫此原生連結可見性）。

   
## <a name="related-topics"></a>相關主題

[Office 365 進階威脅防護](office-365-atp.md)
  
[設定 Office 365 中的 ATP 安全連結原則](set-up-atp-safe-links-policies.md)
  
[Office 365 中的 ATP 安全附件](atp-safe-attachments.md)
  
[Office 365 中的 ATP 防網路釣魚功能](atp-anti-phishing.md)
  
[進階威脅保護的檢視報告](view-reports-for-atp.md)
  

