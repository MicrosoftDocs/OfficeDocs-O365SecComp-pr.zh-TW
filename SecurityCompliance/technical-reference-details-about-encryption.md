---
title: 關於 Office 365 中加密的技術參考細節
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 03/29/2019
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 862cbe93-4268-4ef9-ba79-277545ecf221
description: 在 Office 365 中檢視加密的相關的技術詳細資料。
ms.openlocfilehash: afe077fdedb3e01e5658d27a13e17ae3a3ab5929
ms.sourcegitcommit: 1261a37c414111f869df5791548a768d853fda60
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/30/2019
ms.locfileid: "31004250"
---
# <a name="technical-reference-details-about-encryption-in-office-365"></a>關於 Office 365 中加密的技術參考細節

請參閱本篇文章以了解憑證、 技術及 TLS 加密套件用於[Office 365 中的加密](encryption.md)。 本文也提供詳細資料計劃取代。
  
- 如果您正在尋找概觀資訊，請參閱[Office 365 中的加密](encryption.md)。
- 如果您正在尋找安裝程式的資訊，請參閱 <<c0>設定 Office 365 企業版中的加密。
- 如需特定版本的 Windows 支援的加密套件的資訊，請參閱 < <b0>TLS/SSL (Schannel SSP) 中的加密套件</b0>。
    
## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Microsoft Office 365 憑證擁有權和管理

您不需要購買或維護 Office 365 的憑證，因為 Microsoft 會使用自己的憑證。
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>目前的加密標準與計劃的取代

才能繼續提供最佳的類別加密的 Office 365，Microsoft 會定期檢閱支援的加密標準。 有時候，我們需要取代舊的標準時，他們就過期並因此較不安全。 本主題會說明有關規劃取代目前支援的加密套件和其他標準，以及詳細資料。 

## <a name="fips-compliance-for-office-365"></a>Office 365 的 FIPS 相容性
所有 Office 365 所支援的加密套件會都使用下 FIPS 140-2 可接受的演算法。 Office 365 會繼承 FIPS 驗證從 Windows （透過 Schannel)。 如需 Schannel 資訊，請參閱 < <b0>TLS/SSL (Schannel SSP) 中的加密套件</b0>。
  
## <a name="versions-of-tls-supported-by-office-365"></a>Office 365 支援的 TLS 版本

傳輸層安全性 (TLS) 以及 TLS 之前的 SSL 都是密碼編譯通訊協定，它們使用安全性憑證來加密電腦之間的連線，進而透過網路保護通訊安全。Office 365 支援數個 TLS 版本，包括：
  
- TLS 1.2 版 (TLS 1.2)
    
- TLS 1.1 版 (TLS 1.1)
    
- TLS 1.0 版 (TLS 1.0)
    
 TLS 1.0 和 TLS 1.1 支援將會過時 2018 年 10 月 31 日。 如需詳細資訊，請參閱[Deprecating 支援 TLS 1.0 和 1.1 版及這對您](technical-reference-details-about-encryption.md#TLS11and12deprecation)。 
  
## <a name="deprecating-support-for-tls-10-and-11-and-what-this-means-for-you"></a>不再支援 TLS 1.0 及 1.1 版及這對您的
<a name="TLS11and12deprecation"> </a>

自 2018 年 10 月 31 日，Office 365 不再支援 TLS 1.0 和 1.1 版。 這表示 Microsoft 不會修正新用戶端、 裝置或使用 TLS 1.0 和 1.1，連線至 Office 365 服務中找到的問題。

請注意這並不表示 Office 365 會封鎖 TLS 1.0 和 1.1 版的連線。 沒有正式日期停用或移除客戶連線的 TLS 服務中的 TLS 1.0 和 1.1 版。 最終 deprecation > 日期必須由客戶遙測和還不知道。 會決定之後，會有宣告事先六個月除非我們在發現已知危害，在這種情況下，我們可能會有擔任小於六個月來保護使用服務的客戶。

您應該要確定所有用戶端伺服器和瀏覽器伺服器組合到 Office 365 服務，使用 TLS 1.2 （或更新版本） 維護的連線。 您可能要更新特定用戶端伺服器和瀏覽器伺服器的組合。 如需如何影響您的資訊，請參閱 <<c0>準備強制使用 Office 365 中的 TLS 1.2。
  
## <a name="deprecating-support-for-3des"></a>3DES 支援
<a name="TLS11and12deprecation"> </a>

自 2018 年 10 月 31 日，Office 365 不再支援 3DES 加密套件使用 Office 365 的通訊。 更具體而言，Office 365 不再支援 TLS_RSA_WITH_3DES_EDE_CBC_SHA 加密套件。 2019 年 2 月 28 日，因為此加密套件已停用 Office 365 中。 本主題中列出的用戶端和伺服器與 O365 通訊，此日期必須支援至少一個更安全的 cipher 之後 （請參閱[TLS 密碼支援的 Office 365 套件](technical-reference-details-about-encryption.md#TLSCipherSuites)）。
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Office 365 不再支援 SHA-1 憑證
<a name="TLS11and12deprecation"> </a>

截至年 6 月 2016、 Office 365 不再接受傳出或傳入連線的 sha-1 憑證。 如果您目前的憑證鏈結中與 sha-1 使用憑證，您必須更新使用 sha-2 (安全雜湊演算法 2) 或更有力的雜湊演算法的鏈結。
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>Office 365 所支援的 TLS 加密套件
<a name="TLSCipherSuites"> </a>

加密套件是 TLS 用來建立安全連線的加密演算法集合。 Office 365 所支援的加密套件詳列於下表中的強度順序與要先列出最強的加密套件。 當 Office 365 收到連線要求時，Office 365 會先嘗試使用最上面的加密套件進行連線，如果不成功，則嘗試清單中的第二個加密套件，依此類推。 當 Office 365 傳送連線要求給另一部伺服器或用戶端時，則全由接收端的伺服器或用戶端選擇加密套件，或是否使用 TLS。

> [!IMPORTANT]
> 請注意，TLS 版本取代，並，已被取代的版本*不應該使用*較新版本可用位置。 換句話說，任何地方它已經在此列出該 TLS 1.0、 1.1 和 1.2 版所支援中，選擇*最新*版本 (TLS 1.2)。
  
|**通訊協定**|**加密套件名稱**|**金鑰交換演算法/強度**|**完整轉寄密碼支援**|**驗證演算法/強度**|**加密/強度**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384  <br/> |ECDH/192  <br/> |是  <br/> |RSA/112  <br/> |使用 AES/256  <br/> |
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256  <br/> |ECDH/128 個  <br/> |是  <br/> |RSA/112  <br/> |使用 AES/128 個  <br/> |
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384  <br/> |ECDH/192  <br/> |是  <br/> |RSA/112  <br/> |使用 AES/256  <br/> |
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256  <br/> |ECDH/128 個  <br/> |是  <br/> |RSA/112  <br/> |使用 AES/128 個  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA_P384  <br/> |ECDH/192  <br/> |是  <br/> |RSA/112  <br/> |使用 AES/256  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA_P256  <br/> |ECDH/128 個  <br/> |是  <br/> |RSA/112  <br/> |使用 AES/128 個  <br/> |
|TLS 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256  <br/> |RSA/112  <br/> |否  <br/> |RSA/112  <br/> |使用 AES/256  <br/> |
|TLS 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256  <br/> |RSA/112  <br/> |否  <br/> |RSA/112  <br/> |使用 AES/128 個  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA  <br/> |RSA/112  <br/> |否  <br/> |RSA/112  <br/> |使用 AES/256  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA  <br/> |RSA/112  <br/> |否  <br/> |RSA/112  <br/> |使用 AES/128 個  <br/> |
   
## <a name="related-topics"></a>相關主題
[在 Windows 10 v1607 TLS 加密套件](https://docs.microsoft.com/windows/desktop/SecAuthN/tls-cipher-suites-in-windows-10-v1607)

[Office 365 中的加密](encryption.md)
  
[設定 Office 365 企業版中的加密](set-up-encryption.md)
  
[在 [Windows 安全性狀態更新的 TLS 1.0 的 Schannel 實作： 2015 年 11 月 24 日](https://support.microsoft.com/kb/3117336)
  
[TLS/SSL 加密增強功能 (Windows IT 中心)](https://technet.microsoft.com/en-us/library/cc766285%28v=ws.10%29.aspx)
  

