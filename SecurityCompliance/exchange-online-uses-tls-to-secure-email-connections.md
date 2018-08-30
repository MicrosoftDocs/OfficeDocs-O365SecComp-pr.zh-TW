---
title: Exchange Online 如何使用 TLS 來保護 Office 365 中的電子郵件連線
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/2/2018
ms.audience: ITPro
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 4cde0cda-3430-4dc0-b489-f2c0736c929f
description: 了解 Exchange Online 與 Office 365 使用傳輸層安全性 (TLS) 和轉寄加密 (FS) 來保護電子郵件通訊。也取得由 Microsoft 發行 Exchange Online 的憑證的相關資訊。
ms.openlocfilehash: 079a6f574838f5710dbbbcb53726799abfae1d3a
ms.sourcegitcommit: ddfa0ac1f8ef95a78dcc1468241ef29363d56b5b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/30/2018
ms.locfileid: "23520142"
---
# <a name="how-exchange-online-uses-tls-to-secure-email-connections-in-office-365"></a>Exchange Online 如何使用 TLS 來保護 Office 365 中的電子郵件連線

了解 Exchange Online 與 Office 365 使用傳輸層安全性 (TLS) 和轉寄加密 (FS) 來保護電子郵件通訊。也提供由 Microsoft 發行 Exchange Online 的憑證的相關資訊。
  
## <a name="tls-basics-for-office-365-and-exchange-online"></a>Office 365 和 Exchange Online 的 TLS 基本概念

傳輸層安全性 (TLS) 和 TLS] 之前發生的 SSL 是透過網路的安全通訊加密各電腦間的連線使用安全性憑證的密碼編譯通訊協定。TLS 替代 Secure Sockets Layer (SSL) 和通常稱為 SSL 3.1。Exchange Online 中，我們使用 TLS 之間適用的 Exchange 伺服器和連線加密連線 Exchange 伺服器和例如您的內部部署 Exchange 伺服器或收件者的郵件伺服器的其他伺服器之間。之後，加密連線傳送到該連線的所有資料會都傳送到加密通道。不過，如果您正向透過 TLS 加密連線已傳送的訊息，該郵件不是一定加密。這是因為簡單合約 TLS 不會加密的郵件只是連線。
  
如果您想要加密郵件，便需要使用能加密郵件內容的加密技術，如 Office 郵件加密之類的技術。如需 Office 365 郵件加密選項的相關資訊，請參閱 [Email encryption in Office 365](email-encryption.md) 及 [Office 365 Message Encryption (OME)](ome.md)。 
  
我們建議在您想要用來設定 Office 365 與內部部署組織或另一個組織協力廠商之間的對應關係的安全通道的情況下使用 TLS。Exchange Online 一律先嘗試使用 TLS 來保護您的電子郵件，但不能永遠如果這麼做其他廠商沒有提供 TLS 安全性。繼續閱讀以了解如何使用*連接器*保護安全給您的內部伺服器或重要的協力廠商的所有郵件。 
  
## <a name="how-exchange-online-uses-tls-between-exchange-online-customers"></a>Exchange Online 如何在 Exchange Online 客戶之間使用 TLS

Exchange Online 伺服器一律會使用 TLS 1.2 加密連往資料中心內其他 Exchange Online 伺服器的連線。當您傳送郵件給 Office 365 組織內的收件者時，該電子郵件會自動透過使用 TLS 加密的連線來傳送。同時，所有傳送給其他 Office 365 客戶的電子郵件，都會透過使用 TLS 加密並使用轉寄密碼保護的連線來傳送。
  
## <a name="how-office-365-uses-tls-between-office-365-and-external-trusted-partners"></a>Office 365 如何使用 Office 365 與外部、 受信任的協力廠商之間的 TLS

根據預設，Exchange Online 一定會使用隨機 TLS。這表示 Exchange Online 一律會嘗試先加密於最安全部署版的 TLS 連線則直到找到一個雙方可以同意所在的運作方式 TLS cipher 清單向下的其方式。除非您已設定 Exchange Online 以確保透過安全連線僅傳送給該收件者的郵件，然後依預設會將訊息傳送未加密萬一收件者的組織不支援 TLS 加密。隨機 TLS 」 即足以大部分的企業版。不過，有規範需求例如醫療、 銀行業或政府組織的企業版，您可以設定 Exchange Online 要求，或強制 TLS。指示，請參閱[使用 Office 365 中的連接器設定郵件流程](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx)。
  
如果您決定貴組織和受信任的協力廠商組織之間設定 TLS，Exchange Online 可用於強制的 TLS 建立受信任的通訊通道。強制的 TLS 需要協力廠商組織若要將郵件傳送給您驗證 Exchange online 安全性憑證。為了執行這項作業管理自己的憑證必須您協力廠商。在 Exchange Online 中，我們可以使用連接器來保護您免於未經授權存取他們送達收件者的電子郵件供應商在之前傳送的郵件。如需使用連接器來設定郵件流程，請參閱[使用 Office 365 中的連接器設定郵件流程](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx)。
  
## <a name="tls-and-hybrid-exchange-server-deployments"></a>TLS 和混合 Exchange Server 部署

如果您正在管理混合 Exchange 部署，您的內部部署 Exchange server 需求來驗證 Office 365 中，若要將郵件傳送給收件者的信箱使用安全性憑證是只在 Office 365 中。因此，您需要管理您的內部部署 Exchange 伺服器的安全性憑證。您也可安全地必須儲存及維護這些伺服器的憑證。如需有關管理混合部署中的憑證的詳細資訊，請參閱[混合部署的憑證需求](https://technet.microsoft.com/library/hh563848%28v=exchg.150%29.aspx)。
  
## <a name="how-to-set-up-forced-tls-for-exchange-online-in-office-365"></a>如何在 Office 365 中設定 Exchange Online 的強制 TLS

Exchange Online 客戶運作的強制 TLS 的順序來保護所有傳送和接收電子郵件，您需要設定多個需要 TLS 的連接器。您將需要一個連接器的電子郵件傳送至使用者信箱並從使用者信箱傳送的電子郵件的另一個連接器。在 Exchange 系統管理中心 Office 365 中建立這些連接器。指示，請參閱[使用 Office 365 中的連接器設定郵件流程](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx)。
  
## <a name="tls-certificate-information-for-exchange-online"></a>Exchange Online 的 TLS 憑證資訊

下表說明 Exchange Online 所使用的憑證資訊。如果您的業務合作夥伴會設定其電子郵件伺服器上強制 TLS，您必須提供此資訊給他們。請注意基於安全性理由，我們憑證不要變更的時候。我們已導更新到我們憑證我們資料中心內。新的憑證是從 2018 年 9 月 3、 有效的。
  
 **有效 2018 年 9 月 3，從目前的憑證資訊**
  
|**屬性**|**值**|
|:-----|:-----|
|憑證授權單位根發行者  <br/> |GlobalSign 根 CA – R1 <br/> |
|憑證名稱  <br/> |mail.protection.outlook.com  <br/> |
|組織  <br/> |Microsoft Corporation  <br/> |
|組織單位  <br/> |  <br/> |
|憑證金鑰強度  <br/> |2048  <br/> |
   
 **有效截止 2018 年 9 月 3、 被取代的憑證資訊**
  
為了協助確保順利地轉換，我們會繼續提供您參考的舊憑證資訊的一些時間，不過，您應該使用目前的憑證資訊從現在起。
  
****

|**屬性**|**值**|
|:-----|:-----|
|憑證授權單位根發行者  <br/> |Baltimore CyberTrust Root  <br/> |
|憑證名稱  <br/> |mail.protection.outlook.com  <br/> |
|組織  <br/> |Microsoft Corporation  <br/> |
|組織單位  <br/> |Microsoft Corporation  <br/> |
|憑證金鑰強度  <br/> |2048  <br/> |
   
## <a name="prepare-for-the-new-exchange-online-certificate"></a>準備新的 Exchange Online 憑證

將新的憑證是不同的憑證授權單位 (CA) 所發出使用 Exchange Online 的上一個憑證。因此，您可能需要執行某些動作以使用新的憑證。

將新的憑證必須連線至新的 CA 驗證憑證的一部分的端點。若要執行這項操作失敗可能會導致郵件流程所造成負面影響。如果您來保護您的信箱伺服器具有僅限可讓郵件伺服器的防火牆連接與特定目的地您需要檢查您的伺服器是否能夠驗證新的憑證。若要確認您的伺服器可以使用新的憑證，請完成下列步驟：

1. 連線至本機 Exchange 伺服器使用 Windows PowerShell 並再執行下列命令：  
  `certutil -URL http://crl.globalsign.com/gsorganizationvalsha2g3.crl`
2. 在出現視窗中，選擇 [**擷取**。
3. 公用程式完成其檢查時則會傳回狀態。如果狀態會顯示 **[確定]**，您的郵件伺服器可以成功驗證新的憑證。如果不是，您必須先判斷造成失敗的連線。很有可能您需要更新的防火牆設定。需要可存取的端點的完整清單包括：
    - ocsp.globalsign.com
     - crl.globalsign.com
     - secure.globalsign.com   

一般而言，您會收到更新以透過 Windows Update 自動根憑證。某些部署然而其他安全性防止自動發生這些更新的位置。在這些鎖定部署中所在的 Windows Update 無法自動更新根憑證，您必須確定安裝正確的根 CA 憑證是由完成下列步驟：
1.  連線至本機 Exchange 伺服器使用 Windows PowerShell 並再執行下列命令：  
  `certmgr.msc`
2. [**信任的根憑證授權單位/憑證**]，確認新的憑證已列。

## <a name="get-more-information-about-tls-and-office-365"></a>取得 TLS 和 Office 365 的詳細資訊

支援的編碼器套件的清單，請參閱[Office 365 中加密的相關的技術參考 （英文） 詳細資料](technical-reference-details-about-encryption.md)。
  
[為夥伴組織的安全郵件流程設定連接器](https://technet.microsoft.com/library/dn751021%28v=exchg.150%29.aspx)
  
[具有增強的電子郵件安全性的連接器](https://technet.microsoft.com/library/261d92e4-7371-4555-b781-2062b5bb5278.aspx)
  
[Office 365 中的加密](encryption.md)
  

