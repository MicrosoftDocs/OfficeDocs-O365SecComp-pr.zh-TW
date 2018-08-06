---
title: 為郵件簽章和加密的 S/MIME
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 887c710b-0ec6-4ff0-8065-5f05f74afef3
description: S/MIME 可讓您加密電子郵件與數位簽章它們。當您使用 S/MIME 與電子郵件訊息時，它可協助的人員接收該訊息是特定看到其收件匣中是完全入門寄件者的郵件。
ms.openlocfilehash: 3ce95132476417df8949cdc12f2d825047f6b76d
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027590"
---
# <a name="smime-for-message-signing-and-encryption"></a>為郵件簽章和加密的 S/MIME

S/MIME (安全多用途網際網路郵件延伸) 是一種被廣為接受的方法，更具體來說是通訊協定，可用來傳送已數位簽署和加密的郵件。S/MIME 可讓您將電子郵件加密和進行數位簽署。對電子郵件使用 S/MIME 時，可讓收件者確定收件匣裡的郵件確實為寄件者所寄出。也可讓收件者確定郵件來自特定的寄件者，而不是由其他人假冒寄件者。為了達到此目的，S/MIME 提供密碼編譯的安全性服務，例如驗證、訊息完整性和來源不可否認性 (使用數位簽章)。另外還可加強電子郵件通訊的隱私性和資料安全性 (使用加密)。如需 S/MIME 在電子郵件方面的歷史和架構的完整背景資訊，請參閱＜[瞭解 S/MIME](https://go.microsoft.com/fwlink/?LinkID=393948)＞。 
  
身為系統管理員，如果您管理的信箱在 Exchange 2013 SP1 或 Exchange Online (Office 365 的一部分) 中，您可以在組織中啟用 S/MIME 安全性。請使用 Exchange 管理命令介面並參考以下各連結主題的指引來設定 S/MIME。不論是 Exchange 2013 SP1 或 Exchange Online，若要在支援的 Outlook 或 ActiveSync 版本中使用 S/MIME，組織中的使用者必須有針對簽署和加密用途所發出的憑證，以及發佈至內部部署 Active Directory 網域服務 (AD DS) 的資料。AD DS 必須位於您可掌控的實際位置上的電腦，而不是在遠端設備或網際網路某處的雲端式服務上。如需 AD DS 的詳細資訊，請參閱＜[Active Directory 網域服務](https://go.microsoft.com/fwlink/?LinkID=394064)＞。
  
## <a name="supported-scenarios-and-technical-considerations"></a>支援的案例和技術考量
<a name="sectionSection0"> </a>

如果組織使用 Exchange 2013 SP1 或 Exchange Online，您可以設定 S/MIME 供下列任何端點使用： 
  
- Outlook 2010
    
- Outlook 2013
    
- Outlook Web App
    
- Exchange ActiveSync (EAS)
    
對每個端點設定 S/MIME 時所採取的步驟，視您選擇何者而稍有不同。通常需要完成下列步驟：
  
- 安裝以 Windows 為基礎的憑證授權單位，並且設定公開金鑰基礎結構，來核發 S/MIME 憑證。也支援協力廠商憑證提供者所發出的憑證。如需詳細資訊，請參閱 [Active Directory 憑證服務概觀](https://technet.microsoft.com/library/hh831740.aspx)。
    
- 在內部部署 AD DS 帳戶的 UserSMIMECertificate 和/或 UserCertificate 屬性中發佈使用者憑證。
    
- 在 Exchange Online 組織中，使用適當的 DirSync 版本，將使用者憑證從 AD DS 同步至 Azure Active Directory。這些憑證會從 Azure Active Directory 同步至 Exchange Online 目錄，並於加密寄給收件者的郵件時使用。
    
- 設定虛擬憑證集合以驗證 S/MIME。OWA 會使用此資訊來驗證電子郵件的簽章，以確保電子郵件是以信任的憑證所簽署。
    
- 設定 Outlook 或 EAS 端點來使用 S/MIME。 
    
## <a name="setup-smime-with-outlook-web-app"></a>設定 Outlook Web App 的 S/MIME
<a name="sectionSection1"> </a>

設定 Exchange 2013 SP1 或 Exchange Online 的 Outlook Web App 來使用 S/MIME 包含下列幾個主要步驟：
  
1. [設定 Outlook Web App 的 S/MIME 設定](configure-s-mime-settings-for-outlook-web-app.md)
    
2. [設定驗證 S/MIME 的虛擬憑證集合](set-up-virtual-certificate-collection-to-validate-s-mime.md)
    
3. [將使用者憑證同步至 Office 365 進行 S/MIME](sync-user-certificates-to-office-365-for-s-mime.md)此步驟僅適用於 Exchange Online。 
    
## <a name="related-message-encryption-technologies"></a>相關郵件加密技術
<a name="sectionSection2"> </a>

郵件安全性已變得越來越重要，因此系統管理員必須了解安全郵件的原則和概念。由於有越來越多各式各樣的防護技術 (例如 S/MIME) 問世，所以了解這一方面的資訊再重要不過。若要深入了解 S/MIME 及其於電子郵件上的運作，請參閱＜[瞭解 S/MIME](https://go.microsoft.com/fwlink/?LinkID=393948)＞。各種加密技術可搭配運作，以為靜止和傳輸中的郵件提供保護。S/MIME 可以與下列技術同時運作，但彼此並不具依存關係：
  
> **傳輸層安全性 (TLS)** 會加密電子郵件伺服器之間的通道或路由，以協助防止側錄和竊聽。 
    
> **安全通訊端層 (SSL)** 會加密電子郵件用戶端與 Office 365 伺服器之間的連線。 
    
> **BitLocker** 會加密資料中心硬碟上的資料，因此如果有人未獲授權就存取，便無法讀取資料。 
    
### <a name="smime-compared-with-office-365-message-encryption"></a>S/MIME 與 Office 365 郵件加密的比較

S/MIME 需要憑證和發佈基礎結構 (常用於企業對企業及企業對消費者情況)。在 S/MIME 中，由使用者控制密碼編譯金鑰，且在他們所傳送的每一封郵件上，都可選擇是否使用金鑰。電子郵件程式 (例如 Outlook) 會搜尋受信任的根憑證授單位，以進行數位簽署並驗證簽章。Office 365 郵件加密是系統管理員 (而不是個別使用者) 可設定的原則型加密服務，可將傳送給組織內外任何人的郵件加密。它是以 Azure 版權管理 (RMS) 為基礎的線上服務，且不依賴任何公開金鑰基礎結構。Office 365 郵件加密還提供其他功能，例如以組織的品牌來自訂郵件。如需 Office 365 郵件加密的相關資訊，請參閱 [Office 365 郵件加密](https://go.microsoft.com/fwlink/?LinkID=392525)。
  
## <a name="more-information"></a>其他資訊
<a name="sectionSection3"> </a>

[Outlook Web App](http://technet.microsoft.com/library/3814b665-01e8-4881-9a44-163f14789ee4.aspx)
  
[安全郵件 (2000)](https://technet.microsoft.com/en-us/library/cc962043.aspx)
  

