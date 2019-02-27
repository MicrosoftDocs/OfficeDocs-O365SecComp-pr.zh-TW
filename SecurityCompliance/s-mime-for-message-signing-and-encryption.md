---
title: S/MIME 郵件簽章與 Exchange Online 中的加密
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 887c710b-0ec6-4ff0-8065-5f05f74afef3
description: 系統管理員可了解 Exchange Online 中使用 S/MIME。
ms.openlocfilehash: 163ae5686adf934f07ee26717fa0b4998ddf3363
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296796"
---
# <a name="smime-for-message-signing-and-encryption-in-exchange-online"></a>S/MIME 郵件簽章與 Exchange Online 中的加密

S/MIME （安全/多用途網際網路郵件延伸） 是廣泛可接受的方法 （或更精確的通訊協定） 傳送以數位方式簽署和已加密郵件。S/MIME 可讓您加密電子郵件與數位簽章它們。當您使用 S/MIME 與電子郵件訊息時，它可協助的人員接收該訊息是特定看到其收件匣中是完全入門寄件者的郵件。它也可隨附郵件來自特定寄件者而不寄件者假冒他人協助接收設為特定訊息的人員。若要這樣做，S/MIME 提供密碼編譯安全性服務如驗證、 訊息完整性及不可否認性的 （使用數位簽章） 的原點而言。它也可協助提升隱私權與 （使用加密） 的資料安全性的電子郵件。如需歷程記錄和架構的 S/MIME 郵件的內容中的更完整背景，請參閱[了解 S/MIME](https://go.microsoft.com/fwlink/?LinkID=393948)。

身為 Exchange Online 管理員，您可以在組織中啟用之信箱的 S/MIME 式安全性。若要設定來使用 S/MIME 中使用以下連結搭配 Exchange Online PowerShell 主題中的指導。若要在支援的電子郵件用戶端使用 S/MIME，貴組織中的使用者必須進行簽署和加密憑證以及發佈至您內部部署 Active Directory 網域服務 (AD DS) 的資料。AD DS 必須位於您控制實體位置和不在遠端設備或網際網路上的某處的雲端架構服務的電腦上。如需 AD DS 的詳細資訊，請參閱 ＜ [Active Directory 網域服務](https://go.microsoft.com/fwlink/?LinkID=394064)。

## <a name="supported-scenarios-and-technical-considerations"></a>支援的案例和技術考量

您可以設定 S/MIME 供任何下列的結束點：

- Outlook 2010 或更新版本

- 網頁型 Outlook (先前為 Outlook Web App)

- Exchange ActiveSync (EAS)

所需遵循這些結束點的每個設定來使用 S/MIME 的步驟是稍有不同。一般而言，您必須執行下列步驟：

- 安裝以 Windows 為基礎的憑證授權單位，並且設定公開金鑰基礎結構，來核發 S/MIME 憑證。也支援協力廠商憑證提供者所發出的憑證。如需詳細資訊，請參閱 [Active Directory 憑證服務概觀](https://technet.microsoft.com/library/hh831740.aspx)。

- 在內部部署中發佈使用者憑證 AD DS 帳戶的**UserSMIMECertificate**和/或**UserCertificate**屬性。

- 在 Exchange Online 組織中，使用適當的 DirSync 版本，將使用者憑證從 AD DS 同步至 Azure Active Directory。這些憑證會從 Azure Active Directory 同步至 Exchange Online 目錄，並於加密寄給收件者的郵件時使用。

- 為了驗證 S/MIME 設定的虛擬憑證集合。此資訊使用網路上的 Outlook 驗證電子郵件和確認它已由受信任的憑證簽署的簽章時。

- 設定 Outlook 或 EAS 端點來使用 S/MIME。

## <a name="setup-smime-with-outlook-on-the-web"></a>設定 S/MIME 網路上的 Outlook

Exchange Online 與 Outlook web 上的設定來使用 S/MIME 包含下列主要步驟：

1. [設定 Outlook 網頁版的 S/MIME 設定](configure-s-mime-settings-for-outlook-web-app.md)

2. [設定虛擬憑證集合以驗證 S/MIME](set-up-virtual-certificate-collection-to-validate-s-mime.md)

3. [將使用者憑證同步至 Office 365 進行 S/MIME 處理](sync-user-certificates-to-office-365-for-s-mime.md)

## <a name="related-message-encryption-technologies"></a>相關郵件加密技術

當郵件安全性變得更重要，admins 需要了解原則與概念的安全通訊。此了解特別重要的是因為成長各種保護相關技術 （包括 S/MIME） 可用的。若要了解更多有關 S/MIME 與電子郵件的內容中的運作方式，請參閱[了解 S/MIME](https://go.microsoft.com/fwlink/?LinkID=393948)。各種加密技術共同運作來提供的 rest 和傳送過程中的郵件保護。S/MIME 可以同時使用下列技術，但不是取決於其：

- **傳輸層安全性 (TLS)** 會加密電子郵件伺服器之間的通道或路由，以協助防止側錄和竊聽。

- **安全通訊端層 (SSL)** 會加密電子郵件用戶端與 Office 365 伺服器之間的連線。

- **BitLocker** 會加密資料中心硬碟上的資料，因此如果有人未獲授權就存取，便無法讀取資料。

### <a name="smime-compared-with-office-365-message-encryption"></a>S/MIME 與 Office 365 郵件加密的比較

S/MIME 需要憑證和發佈基礎結構 (常用於企業對企業及企業對消費者情況)。在 S/MIME 中，由使用者控制密碼編譯金鑰，且在他們所傳送的每一封郵件上，都可選擇是否使用金鑰。電子郵件程式 (例如 Outlook) 會搜尋受信任的根憑證授單位，以進行數位簽署並驗證簽章。Office 365 郵件加密是系統管理員 (而不是個別使用者) 可設定的原則型加密服務，可將傳送給組織內外任何人的郵件加密。它是以 Azure 版權管理 (RMS) 為基礎的線上服務，且不依賴任何公開金鑰基礎結構。Office 365 郵件加密還提供其他功能，例如以組織的品牌來自訂郵件。如需 Office 365 郵件加密的相關資訊，請參閱 [Office 365 郵件加密](https://go.microsoft.com/fwlink/?LinkID=392525)。

## <a name="more-information"></a>其他資訊

[網頁型 Outlook](http://technet.microsoft.com/library/3814b665-01e8-4881-9a44-163f14789ee4.aspx)

[安全郵件 (2000)](https://technet.microsoft.com/en-us/library/cc962043.aspx)
