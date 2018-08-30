---
title: 關於 Office 365 中加密的技術參考細節
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/12/2018
ms.audience: ITPro
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 862cbe93-4268-4ef9-ba79-277545ecf221
description: 檢視關於 Office 365 中的加密技術詳細資料。
ms.openlocfilehash: d86692119f7558d74e2083165b4eb6ab4a07da70
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22527156"
---
# <a name="technical-reference-details-about-encryption-in-office-365"></a>關於 Office 365 中加密的技術參考細節

請參閱本文以了解憑證、 技術及 TLS 用於[Office 365 中的加密](encryption.md)cipher 套件。本文章也提供詳細資訊計劃被取代。
  
- 如果您要尋找的概觀資訊，請參閱[Office 365 中的加密](encryption.md)。
    
- 如果您正在尋找安裝程式的資訊，請參閱[Office 365 企業版中的加密設定](set-up-encryption.md)。
    
## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Microsoft Office 365 憑證擁有權和管理

您不需要購買或維護 Office 365 的憑證，因為 Microsoft 會使用自己的憑證。
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>目前的加密標準 （英文） 及計劃被取代

若要繼續提供最佳的類別加密的 Office 365、 Microsoft 定期檢閱支援的加密標準 （英文）。有時，我們需要取代舊的標準過期與因此較不安全文章清單。本主題會說明有關計劃被取代的目前支援的編碼器套件和其他標準以及詳細資訊。
  
## <a name="versions-of-tls-supported-by-office-365"></a>Office 365 支援的 TLS 版本

傳輸層安全性 (TLS) 以及 TLS 之前的 SSL 都是密碼編譯通訊協定，它們使用安全性憑證來加密電腦之間的連線，進而透過網路保護通訊安全。Office 365 支援數個 TLS 版本，包括：
  
- TLS 1.2 版 (TLS 1.2)
    
- TLS 1.1 版 (TLS 1.1)
    
- TLS 1.0 版 (TLS 1.0)
    
 TLS 1.0 與 TLS 1.1 支援將會過時 2018 年 10 月 31、。請參閱[Deprecating 支援 TLS 1.0 和 1.1 及這表示您](technical-reference-details-about-encryption.md#TLS11and12deprecation)如需詳細資訊。 
  
## <a name="deprecating-support-for-tls-10-and-11-and-what-this-means-for-you"></a>廢棄的 TLS 1.0 和 1.1 及這表示您的支援
<a name="TLS11and12deprecation"> </a>

重要的變更會傳入 for Office 365 的支援的加密選項。2018 年 10 月 31 到 Office 365 不再支援使用 TLS 1.0 或 1.1 for Office 365 的通訊。一旦 Office 365 deprecates 支援下列通訊協定，所有通訊，請從 Office 365 的伺服器都必須使用 TLS 1.2。這對您所做的影響的相關資訊，請參閱[強制 TLS 1.2 版 Office 365 中使用的準備](https://support.microsoft.com/en-us/help/4057306/preparing-for-tls-1-2-in-office-365)。伺服器和用戶端通訊的 O365 這個日期之後必須支援 TLS 1.2。
  
## <a name="deprecating-support-for-3des"></a>廢棄 3DES 的支援
<a name="TLS11and12deprecation"> </a>

從 2018 年 10 月 31 Office 365 不再支援 3DES 加密套件使用 Office 365 的通訊。更明確 Office 365 不再支援 TLS_RSA_WITH_3DES_EDE_CBC_SHA 編碼器套件。用戶端和伺服器通訊 O365 之後此日期必須支援至少一個更安全 cipher 列在本主題 （請參閱[TLS 密碼支援的 Office 365 套裝軟體](technical-reference-details-about-encryption.md#TLSCipherSuites)）。
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Office 365 不再支援 SHA-1 憑證
<a name="TLS11and12deprecation"> </a>

年 6 月 2016 Office 365 不再接受輸出或輸入連線的 sha-1 憑證。如果您目前的憑證鏈結中具有 sha-1 使用憑證，您必須更新使用 SHA-1-2 (安全雜湊演算法 2) 或更有力的雜湊演算法鏈結。
  
## <a name="deprecating-rc4-support-in-office-365"></a>Office 365 不再支援 RC4
<a name="TLS11and12deprecation"> </a>

2015 年 7 月，已中止對下列 RC4 加密套件的支援：
  
- TLS_RSA_WITH_RC4_128_SHA
    
- TLS_RSA_WITH_RC4_128_MD5
    
## <a name="deprecating-secure-sockets-layer-ssl-30-support-in-office-365"></a>廢棄 Office 365 的 Secure Sockets Layer (SSL) 3.0 的支援
<a name="TLS11and12deprecation"> </a>

啟動 2014 年 12 月 1 日開始支援的 Secure Sockets Layer (SSL) 3.0、 前置 TLS 來停用 Office 365。如需詳細資訊，請參閱 ＜ [Security advisory 3009008](https://technet.microsoft.com/library/security/3009008.aspx)。如需如何確保指示用戶端使用 TLS 1.0 或更高，若要停用 SSL 3.0，請參閱[保護 SSL 3.0 弱點](http://blogs.office.com/2014/10/29/protecting-ssl-3-0-vulnerability/)。
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>Office 365 支援 TLS 加密套件
<a name="TLSCipherSuites"> </a>

加密套件是 TLS 用來建立安全連線的加密演算法集合。下表依強度列出 Office 365 支援的加密套件，強度最大的加密套件列在最上面。Office 365 在收到連線要求時，會先嘗試使用最上面的加密套件進行連線，如果不成功，則嘗試清單中的第二個加密套件，依此類推。當 Office 365 傳送連線要求給另一部伺服器或用戶端時，則全由接收端的伺服器或用戶端選擇加密套件，或是否使用 TLS。
  
|**通訊協定**|**加密套件名稱**|**金鑰交換演算法/強度**|**完整轉寄密碼支援**|**驗證演算法/強度**|**加密/強度**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384  <br/> |ECDH/192  <br/> |是  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256  <br/> |ECDH/128  <br/> |是  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA_P384  <br/> |ECDH/192  <br/> |是  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA_P256  <br/> |ECDH/128  <br/> |是  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256  <br/> |RSA/112  <br/> |否  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256  <br/> |RSA/112  <br/> |否  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA  <br/> |RSA/112  <br/> |否  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA  <br/> |RSA/112  <br/> |否  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_3DES_EDE_CBC_SHA  <br/> |RSA/112  <br/> |否  <br/> |RSA/112  <br/> |3DES/192  <br/> |
   
## <a name="related-topics"></a>相關主題
<a name="TLSCipherSuites"> </a>

[Office 365 中的加密](encryption.md)
  
[設定 Office 365 企業版中的加密](set-up-encryption.md)
  
[在 [Windows 安全性狀態更新 TLS 1.0 Schannel 實作： 2015 年 11 月 24、](https://support.microsoft.com/kb/3117336)
  
[TLS/SSL 的密碼編譯加強 (Windows IT 中心)](https://technet.microsoft.com/en-us/library/cc766285%28v=ws.10%29.aspx)
  

