---
title: Exchange Online 如何使用 TLS 來保護 Office 365 中的電子郵件連線
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/2/2018
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4cde0cda-3430-4dc0-b489-f2c0736c929f
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: 了解如何 Exchange Online 和 Office 365 使用傳輸層安全性 (TLS) 和轉寄密碼 (FS) 來保護電子郵件通訊。也會由 Microsoft Exchange Online 的發出的憑證的相關資訊。
ms.openlocfilehash: e80f477c807f3a7ad5f751e0987b191024c816d9
ms.sourcegitcommit: 03054baf50c1dd5cd9ca6a9bd5d056f3db98f964
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/01/2019
ms.locfileid: "30354625"
---
# <a name="how-exchange-online-uses-tls-to-secure-email-connections-in-office-365"></a>Exchange Online 如何使用 TLS 來保護 Office 365 中的電子郵件連線

了解如何 Exchange Online 和 Office 365 使用傳輸層安全性 (TLS) 和轉寄密碼 (FS) 來保護電子郵件通訊。也會提供關於由 Microsoft Exchange Online 的發出的憑證資訊。
  
## <a name="tls-basics-for-office-365-and-exchange-online"></a>Office 365 和 Exchange Online 的 TLS 基本概念

傳輸層安全性 (TLS) 和 TLS，之前的 SSL 是密碼編譯通訊協定，透過網路的安全通訊所使用的安全性憑證來加密電腦之間的連線。TLS 會取代 Secure Sockets Layer (SSL) 和通常稱為 SSL 3.1。針對 Exchange Online，我們會使用 TLS 來加密我們的 Exchange 伺服器之間連線的連線，我們的 Exchange 伺服器與其他伺服器，例如您的內部部署 Exchange 伺服器或收件者的郵件伺服器之間。一旦已加密的連線，則會透過加密通道傳送透過該連線傳送的所有資料。不過，如果您轉寄透過 TLS 加密的連線已傳送的郵件，該郵件不一定會加密。這是因為簡單來說，TLS 不會加密郵件，只要連線。
  
如果您想要加密郵件，便需要使用能加密郵件內容的加密技術，如 Office 郵件加密之類的技術。如需 Office 365 郵件加密選項的相關資訊，請參閱 [Email encryption in Office 365](email-encryption.md) 及 [Office 365 Message Encryption (OME)](ome.md)。 
  
我們建議您想要設定 Office 365 與內部部署組織或另一個組織，例如協力廠商之間的對應關係的安全通道的情況下使用 TLS。Exchange Online 一律會嘗試先使用 TLS 來保護您的電子郵件，但無法永遠執行這項操作如果另一方並不提供 TLS 安全性。繼續閱讀以了解如何保護您的內部部署伺服器或重要的協力廠商的所有郵件，以及在使用*連接器*。 
  
## <a name="how-exchange-online-uses-tls-between-exchange-online-customers"></a>Exchange Online 如何在 Exchange Online 客戶之間使用 TLS

Exchange Online 伺服器一律會使用 TLS 1.2 加密連往資料中心內其他 Exchange Online 伺服器的連線。當您傳送郵件給 Office 365 組織內的收件者時，該電子郵件會自動透過使用 TLS 加密的連線來傳送。同時，所有傳送給其他 Office 365 客戶的電子郵件，都會透過使用 TLS 加密並使用轉寄密碼保護的連線來傳送。
  
## <a name="how-office-365-uses-tls-between-office-365-and-external-trusted-partners"></a>Office 365 如何使用 Office 365 及外部、 受信任的協力廠商之間的 TLS

根據預設，Exchange Online 一律使用隨機 TLS。這表示 Exchange Online 一律會嘗試先，加密連線與最安全的 TLS 版本運作的 TLS cipher 運送途中清單向下，直到找到一個在其上雙方可以同意。除非您已設定 Exchange Online，以確定透過安全連線僅傳送給該收件者的郵件，然後依預設郵件將傳送未加密如果收件者的組織不支援 TLS 加密。隨機 TLS 是大部分的公司已足夠。不過，擁有規範需求，例如醫療、 銀行業或政府組織的商務用，您可以設定 Exchange Online 若需要，請或強制 TLS。如需相關指示，請參閱 <<c0>使用 Office 365 中的連接器設定郵件流程。
  
如果您決定組織和受信任的夥伴組織之間設定 TLS，Exchange Online 可以使用強制的 TLS 來建立受信任的通訊通道。強制的 TLS 要求夥伴組織到 Exchange Online 的安全性憑證驗證才能傳送郵件給您。您的合作夥伴將需要管理自己的憑證，才能執行此動作。在 Exchange Online 中，我們會使用連接器來保護您免於受到非法存取之前抵達收件者的電子郵件提供者傳送的郵件。如需使用連接器來設定郵件流程的詳細資訊，請參閱 <<c0>使用 Office 365 中的連接器設定郵件流程。
  
## <a name="tls-and-hybrid-exchange-server-deployments"></a>TLS 和混合 Exchange Server 部署

如果您要管理混合 Exchange 部署，您的內部部署 Exchange 伺服器需求，來驗證 Office 365 才能傳送郵件給收件者的信箱使用的安全性憑證是只能在 Office 365。因此，您需要管理您的內部部署 Exchange 伺服器您自己的安全性憑證。您必須也安全地儲存，及維護這些伺服器憑證。如需管理混合式部署中的憑證的詳細資訊，請參閱 <<c0>混合式部署的憑證需求。
  
## <a name="how-to-set-up-forced-tls-for-exchange-online-in-office-365"></a>如何在 Office 365 中設定 Exchange Online 的強制 TLS

Exchange Online 的客戶，為了讓工作的強制 TLS 來保護所有的傳送和接收電子郵件，您要設定多個需要透過 TLS 的連接器。您將需要一個連接器，電子郵件傳送至使用者信箱並從使用者信箱傳送的電子郵件的另一個連接器。在 Exchange 系統管理中心，在 Office 365 中建立這些連接器。如需相關指示，請參閱 <<c0>使用 Office 365 中的連接器設定郵件流程。
  
## <a name="tls-certificate-information-for-exchange-online"></a>Exchange Online 的 TLS 憑證資訊

下表說明 Exchange Online 使用的憑證資訊。如果您的業務合作夥伴設定其電子郵件伺服器上的強制 TLS，您必須提供這項資訊給他們。請注意，基於安全性考量，我們憑證並變更的時候。我們已在我們的資料中心內來導入更新我們憑證。新的憑證是從 2018 年 9 月 3 日有效。
  
 **從 2018 年 9 月 3 日有效目前的憑證資訊**
  
|**屬性**|**值**|
|:-----|:-----|
|憑證授權單位根發行者  <br/> |GlobalSign 根 CA – R1 <br/> |
|憑證名稱  <br/> |mail.protection.outlook.com  <br/> |
|組織  <br/> |Microsoft Corporation  <br/> |
|組織單位  <br/> |  <br/> |
|憑證金鑰強度  <br/> |2048  <br/> |
   
 **已被取代的憑證資訊起直到 2018 年 9 月 3 日**
  
為了協助確保順利轉移，我們將會繼續提供舊的憑證資訊供您參考一些時間，不過，您應該使用目前的憑證資訊現在開始。
  
****

|**屬性**|**值**|
|:-----|:-----|
|憑證授權單位根發行者  <br/> |Baltimore CyberTrust Root  <br/> |
|憑證名稱  <br/> |mail.protection.outlook.com  <br/> |
|組織  <br/> |Microsoft Corporation  <br/> |
|組織單位  <br/> |Microsoft Corporation  <br/> |
|憑證金鑰強度  <br/> |2048  <br/> |
   
## <a name="prepare-for-the-new-exchange-online-certificate"></a>準備新的 Exchange Online 憑證

新的憑證是由不同的憑證授權單位 (CA) 發出從 Exchange Online 使用的前一個憑證。因此，您可能需要執行某些動作，才能使用新的憑證。

新的憑證需要連線至新的 CA 一部分驗證憑證的端點。若要執行這項操作失敗可能會導致郵件流程所造成負面影響。保護您具有僅限可讓郵件伺服器的防火牆伺服器連線與特定目的地的郵件如果您要檢查您的伺服器是否能夠驗證新的憑證。若要確認您的伺服器可以使用新的憑證，請完成下列步驟：

1. 連線至您使用 Windows PowerShell 在本機 Exchange 伺服器，然後執行下列命令：  
  `certutil -URL http://crl.globalsign.com/gsorganizationvalsha2g3.crl`
2. 在出現的視窗中，選擇 [**擷取**]。
3. 公用程式完成其檢查時就會傳回狀態。如果狀態會顯示 **[確定]**，您的郵件伺服器可以成功驗證新的憑證。如果不是，您需要判斷造成失敗的連線。大部分情況下，您需要更新的防火牆設定。需要存取的端點的完整清單包括：
    - ocsp.globalsign.com
     - crl.globalsign.com
     - secure.globalsign.com   

一般而言，您會收到更新自動透過 Windows 更新您的根憑證。不過有某些部署中防止這些更新會自動發生的地方有額外的安全性。在這些鎖定的部署中其中 Windows Update 無法自動更新的根憑證，您必須確定將正確的根 CA 憑證已安裝，請完成下列步驟：
1.  連線至您使用 Windows PowerShell 在本機 Exchange 伺服器，然後執行下列命令：  
  `certmgr.msc`
2. [**受信任的根憑證授權單位/憑證**，請先確認已列出新的憑證。

## <a name="get-more-information-about-tls-and-office-365"></a>取得 TLS 和 Office 365 的詳細資訊

支援的加密套件清單，請參閱[關於 Office 365 中加密的技術參考細節](technical-reference-details-about-encryption.md)。
  
[為夥伴組織的安全郵件流程設定連接器](https://technet.microsoft.com/library/dn751021%28v=exchg.150%29.aspx)
  
[具有增強的電子郵件安全性的連接器](https://technet.microsoft.com/library/261d92e4-7371-4555-b781-2062b5bb5278.aspx)
  
[Office 365 中的加密](encryption.md)
  

