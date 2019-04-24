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
description: 了解如何 Exchange Online 和 Office 365 使用傳輸層安全性 (TLS) 和轉寄密碼 (FS) 來保護電子郵件通訊。 也會由 Microsoft Exchange Online 的發出的憑證的相關資訊。
ms.openlocfilehash: e80f477c807f3a7ad5f751e0987b191024c816d9
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32255631"
---
# <a name="how-exchange-online-uses-tls-to-secure-email-connections-in-office-365"></a>Exchange Online 如何使用 TLS 來保護 Office 365 中的電子郵件連線

了解如何 Exchange Online 和 Office 365 使用傳輸層安全性 (TLS) 和轉寄密碼 (FS) 來保護電子郵件通訊。 也會提供關於由 Microsoft Exchange Online 的發出的憑證資訊。
  
## <a name="tls-basics-for-office-365-and-exchange-online"></a>Office 365 和 Exchange Online 的 TLS 基本概念

TLS 之前的傳輸層安全性 (TLS) 和 SSL 是密碼編譯通訊協定，該協定使用安全性憑證來加密電腦之間的連線以保護透過網路進行的通訊。 TLS 取代了安全通訊端層 (SSL)，且往往被稱為 SSL 3.1。 針對 Exchange Online，我們會使用 TLS 來加密我們的 Exchange 伺服器之間連線的連線，我們的 Exchange 伺服器與其他伺服器，例如您的內部部署 Exchange 伺服器或收件者的郵件伺服器之間。 一旦連線經過加密，所有透過該連線傳送的資料將會透過加密通道傳送。 不過，若轉寄透過 TLS 加密連線所傳送的郵件，該郵件則不一定會加密。 這是因為簡單來說，TLS 不會加密郵件，只要連線。
  
如果您想要加密郵件，便需要使用能加密郵件內容的加密技術，如 Office 郵件加密之類的技術。 如需 Office 365 郵件加密選項的相關資訊，請參閱 [Email encryption in Office 365](email-encryption.md) 及 [Office 365 Message Encryption (OME)](ome.md)。 
  
我們建議您想要設定 Office 365 與內部部署組織或另一個組織，例如協力廠商之間的對應關係的安全通道的情況下使用 TLS。 Exchange Online 一律會先嘗試使用 TLS 來保護您的電子郵件，但如果另一方沒有提供 TLS 安全性，則無法一律如此進行。 繼續閱讀以了解如何保護您的內部部署伺服器或重要的協力廠商的所有郵件，以及在使用*連接器*。 
  
## <a name="how-exchange-online-uses-tls-between-exchange-online-customers"></a>Exchange Online 如何在 Exchange Online 客戶之間使用 TLS

Exchange Online 伺服器一律會使用 TLS 1.2 加密連往資料中心內其他 Exchange Online 伺服器的連線。當您傳送郵件給 Office 365 組織內的收件者時，該電子郵件會自動透過使用 TLS 加密的連線來傳送。同時，所有傳送給其他 Office 365 客戶的電子郵件，都會透過使用 TLS 加密並使用轉寄密碼保護的連線來傳送。
  
## <a name="how-office-365-uses-tls-between-office-365-and-external-trusted-partners"></a>Office 365 如何使用 Office 365 及外部、 受信任的協力廠商之間的 TLS

根據預設，Exchange Online 一律會使用「隨機 TLS」。 這表示 Exchange Online 一律會先嘗試使用最安全的 TLS 版本加密連線，如果無法成功，便在 TLS 加密清單中尋找下一順位的版本，直到找到雙方都能同意的版本。 除非您已設定 Exchange Online，以確定透過安全連線僅傳送給該收件者的郵件，然後依預設郵件將傳送未加密如果收件者的組織不支援 TLS 加密。 隨機 TLS 對大多數企業而言已足夠。 不過，擁有規範需求，例如醫療、 銀行業或政府組織的商務用，您可以設定 Exchange Online 若需要，請或強制 TLS。 如需相關指示，請參閱 <<c0>使用 Office 365 中的連接器設定郵件流程。
  
如果您決定在所屬組織與信任的合作夥伴組織之間設定 TLS，Exchange Online 可以使用「強制 TLS」建立信任的通訊通道。 強制 TLS 會要求合作夥伴組織必須使用安全性憑證向 Exchange Online 進行驗證，才能傳送郵件給您。 您的合作夥伴必須管理自己的憑證，才能執行此動作。 在 Exchange Online 中，我們會使用連接器來保護您免於受到非法存取之前抵達收件者的電子郵件提供者傳送的郵件。 如需使用連接器來設定郵件流程的詳細資訊，請參閱 <<c0>使用 Office 365 中的連接器設定郵件流程。
  
## <a name="tls-and-hybrid-exchange-server-deployments"></a>TLS 和混合 Exchange Server 部署

若要管理混合 Exchange 部署，您的內部部署 Exchange 伺服器需要使用安全性憑證向 Office 365 驗證，才能傳送郵件給信箱只位在 Office 365 內的收件者。 因此，您需要管理您的內部部署 Exchange 伺服器您自己的安全性憑證。 您也必須安全地儲存和維護這些伺服器憑證。 如需管理混合式部署中的憑證的詳細資訊，請參閱 <<c0>混合式部署的憑證需求。
  
## <a name="how-to-set-up-forced-tls-for-exchange-online-in-office-365"></a>如何在 Office 365 中設定 Exchange Online 的強制 TLS

Exchange Online 客戶若想要使用強制 TLS 保護所有傳送和接收的電子郵件，需要設定多個需要 TLS 的連接器。 一個連接器用於傳送給使用者信箱的電子郵件，另一個連接器用於從使用者信箱寄出的電子郵件。 請在 Office 365 中的 Exchange 系統管理中心建立這些連接器。 如需相關指示，請參閱 <<c0>使用 Office 365 中的連接器設定郵件流程。
  
## <a name="tls-certificate-information-for-exchange-online"></a>Exchange Online 的 TLS 憑證資訊

下表說明 Exchange Online 使用的憑證資訊。 如果您的商業夥伴要在其電子郵件伺服器上設定的強制 TLS，您必須提供這項資訊給他們。 請注意，基於安全性考量，我們的憑證會隨時變更。 我們已在我們的資料中心內來導入更新我們憑證。 新的憑證是從 2018 年 9 月 3 日有效。
  
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

新的憑證是由不同的憑證授權單位 (CA) 發出從 Exchange Online 使用的前一個憑證。 因此，您可能需要執行某些動作，才能使用新的憑證。

新的憑證需要連線至新的 CA 一部分驗證憑證的端點。 若要執行這項操作失敗可能會導致郵件流程所造成負面影響。 保護您具有僅限可讓郵件伺服器的防火牆伺服器連線與特定目的地的郵件如果您要檢查您的伺服器是否能夠驗證新的憑證。 若要確認您的伺服器可以使用新的憑證，請完成下列步驟：

1. 連線至您使用 Windows PowerShell 在本機 Exchange 伺服器，然後執行下列命令：  
  `certutil -URL http://crl.globalsign.com/gsorganizationvalsha2g3.crl`
2. 在出現的視窗中，選擇 [**擷取**]。
3. 公用程式完成其檢查時就會傳回狀態。 如果狀態會顯示 **[確定]**，您的郵件伺服器可以成功驗證新的憑證。 如果不是，您需要判斷造成失敗的連線。 大部分情況下，您需要更新的防火牆設定。 需要存取的端點的完整清單包括：
    - ocsp.globalsign.com
     - crl.globalsign.com
     - secure.globalsign.com   

一般而言，您會收到更新自動透過 Windows 更新您的根憑證。 不過有某些部署中防止這些更新會自動發生的地方有額外的安全性。 在這些鎖定的部署中其中 Windows Update 無法自動更新的根憑證，您必須確定將正確的根 CA 憑證已安裝，請完成下列步驟：
1.  連線至您使用 Windows PowerShell 在本機 Exchange 伺服器，然後執行下列命令：  
  `certmgr.msc`
2. [**受信任的根憑證授權單位/憑證**，請先確認已列出新的憑證。

## <a name="get-more-information-about-tls-and-office-365"></a>取得 TLS 和 Office 365 的詳細資訊

支援的加密套件清單，請參閱[關於 Office 365 中加密的技術參考細節](technical-reference-details-about-encryption.md)。
  
[為夥伴組織的安全郵件流程設定連接器](https://technet.microsoft.com/library/dn751021%28v=exchg.150%29.aspx)
  
[具有增強的電子郵件安全性的連接器](https://technet.microsoft.com/library/261d92e4-7371-4555-b781-2062b5bb5278.aspx)
  
[Office 365 中的加密](encryption.md)
  

