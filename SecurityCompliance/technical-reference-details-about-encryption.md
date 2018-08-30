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
# <a name="technical-reference-details-about-encryption-in-office-365"></a><span data-ttu-id="065b1-103">關於 Office 365 中加密的技術參考細節</span><span class="sxs-lookup"><span data-stu-id="065b1-103">Technical reference details about encryption in Office 365</span></span>

<span data-ttu-id="065b1-p101">請參閱本文以了解憑證、 技術及 TLS 用於[Office 365 中的加密](encryption.md)cipher 套件。本文章也提供詳細資訊計劃被取代。</span><span class="sxs-lookup"><span data-stu-id="065b1-p101">Refer to this article to learn about certificates, technologies, and TLS cipher suites used for [encryption in Office 365](encryption.md). This article also provides details about planned deprecations.</span></span>
  
- <span data-ttu-id="065b1-106">如果您要尋找的概觀資訊，請參閱[Office 365 中的加密](encryption.md)。</span><span class="sxs-lookup"><span data-stu-id="065b1-106">If you're looking for overview information, see [Encryption in Office 365](encryption.md).</span></span>
    
- <span data-ttu-id="065b1-107">如果您正在尋找安裝程式的資訊，請參閱[Office 365 企業版中的加密設定](set-up-encryption.md)。</span><span class="sxs-lookup"><span data-stu-id="065b1-107">If you're looking for setup information, see [Set up encryption in Office 365 Enterprise](set-up-encryption.md).</span></span>
    
## <a name="microsoft-office-365-certificate-ownership-and-management"></a><span data-ttu-id="065b1-108">Microsoft Office 365 憑證擁有權和管理</span><span class="sxs-lookup"><span data-stu-id="065b1-108">Microsoft Office 365 certificate ownership and management</span></span>

<span data-ttu-id="065b1-109">您不需要購買或維護 Office 365 的憑證，因為 Microsoft 會使用自己的憑證。</span><span class="sxs-lookup"><span data-stu-id="065b1-109">You do not need to purchase or maintain certificates for Office 365 because Microsoft uses its own certificates.</span></span>
  
## <a name="current-encryption-standards-and-planned-deprecations"></a><span data-ttu-id="065b1-110">目前的加密標準 （英文） 及計劃被取代</span><span class="sxs-lookup"><span data-stu-id="065b1-110">Current encryption standards and planned deprecations</span></span>

<span data-ttu-id="065b1-p102">若要繼續提供最佳的類別加密的 Office 365、 Microsoft 定期檢閱支援的加密標準 （英文）。有時，我們需要取代舊的標準過期與因此較不安全文章清單。本主題會說明有關計劃被取代的目前支援的編碼器套件和其他標準以及詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="065b1-p102">In order to continue to provide best-in-class encryption for Office 365, Microsoft regularly reviews supported encryption standards. Sometimes, we need to deprecate old standards as they become out of date and therefore less secure. This topic describes currently supported cipher suites and other standards as well as details about planned deprecations.</span></span>
  
## <a name="versions-of-tls-supported-by-office-365"></a><span data-ttu-id="065b1-114">Office 365 支援的 TLS 版本</span><span class="sxs-lookup"><span data-stu-id="065b1-114">Versions of TLS supported by Office 365</span></span>

<span data-ttu-id="065b1-p103">傳輸層安全性 (TLS) 以及 TLS 之前的 SSL 都是密碼編譯通訊協定，它們使用安全性憑證來加密電腦之間的連線，進而透過網路保護通訊安全。Office 365 支援數個 TLS 版本，包括：</span><span class="sxs-lookup"><span data-stu-id="065b1-p103">Transport Layer Security (TLS), and SSL that came before TLS, are cryptographic protocols that secure communication over a network by using security certificates to encrypt a connection between computers. Office 365 supports several versions of TLS, including:</span></span>
  
- <span data-ttu-id="065b1-117">TLS 1.2 版 (TLS 1.2)</span><span class="sxs-lookup"><span data-stu-id="065b1-117">TLS version 1.2 (TLS 1.2)</span></span>
    
- <span data-ttu-id="065b1-118">TLS 1.1 版 (TLS 1.1)</span><span class="sxs-lookup"><span data-stu-id="065b1-118">TLS version 1.1 (TLS 1.1)</span></span>
    
- <span data-ttu-id="065b1-119">TLS 1.0 版 (TLS 1.0)</span><span class="sxs-lookup"><span data-stu-id="065b1-119">TLS version 1.0 (TLS 1.0)</span></span>
    
 <span data-ttu-id="065b1-p104">TLS 1.0 與 TLS 1.1 支援將會過時 2018 年 10 月 31、。請參閱[Deprecating 支援 TLS 1.0 和 1.1 及這表示您](technical-reference-details-about-encryption.md#TLS11and12deprecation)如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="065b1-p104">TLS 1.0 and TLS 1.1 support will be deprecated October 31, 2018. See [Deprecating support for TLS 1.0 and 1.1 and what this means for you](technical-reference-details-about-encryption.md#TLS11and12deprecation) for more information.</span></span> 
  
## <a name="deprecating-support-for-tls-10-and-11-and-what-this-means-for-you"></a><span data-ttu-id="065b1-122">廢棄的 TLS 1.0 和 1.1 及這表示您的支援</span><span class="sxs-lookup"><span data-stu-id="065b1-122">Deprecating support for TLS 1.0 and 1.1 and what this means for you</span></span>
<span data-ttu-id="065b1-123"><a name="TLS11and12deprecation"> </a></span><span class="sxs-lookup"><span data-stu-id="065b1-123"></span></span>

<span data-ttu-id="065b1-p105">重要的變更會傳入 for Office 365 的支援的加密選項。2018 年 10 月 31 到 Office 365 不再支援使用 TLS 1.0 或 1.1 for Office 365 的通訊。一旦 Office 365 deprecates 支援下列通訊協定，所有通訊，請從 Office 365 的伺服器都必須使用 TLS 1.2。這對您所做的影響的相關資訊，請參閱[強制 TLS 1.2 版 Office 365 中使用的準備](https://support.microsoft.com/en-us/help/4057306/preparing-for-tls-1-2-in-office-365)。伺服器和用戶端通訊的 O365 這個日期之後必須支援 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="065b1-p105">Important changes are coming to supported encryption options for Office 365. As of October 31, 2018, Office 365 will no longer support the use of TLS 1.0 or 1.1 for communication to Office 365. Once Office 365 deprecates support for these protocols, all communication to and from Office 365 servers will need to use TLS 1.2. For information about how this impacts you, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/en-us/help/4057306/preparing-for-tls-1-2-in-office-365). Servers and clients communicating with O365 after this date must support TLS 1.2.</span></span>
  
## <a name="deprecating-support-for-3des"></a><span data-ttu-id="065b1-129">廢棄 3DES 的支援</span><span class="sxs-lookup"><span data-stu-id="065b1-129">Deprecating support for 3DES</span></span>
<span data-ttu-id="065b1-130"><a name="TLS11and12deprecation"> </a></span><span class="sxs-lookup"><span data-stu-id="065b1-130"></span></span>

<span data-ttu-id="065b1-p106">從 2018 年 10 月 31 Office 365 不再支援 3DES 加密套件使用 Office 365 的通訊。更明確 Office 365 不再支援 TLS_RSA_WITH_3DES_EDE_CBC_SHA 編碼器套件。用戶端和伺服器通訊 O365 之後此日期必須支援至少一個更安全 cipher 列在本主題 （請參閱[TLS 密碼支援的 Office 365 套裝軟體](technical-reference-details-about-encryption.md#TLSCipherSuites)）。</span><span class="sxs-lookup"><span data-stu-id="065b1-p106">As of October 31, 2018, Office 365 will no longer support the use of 3DES cipher suites for communication to Office 365. More specifically, Office 365 will no longer support the TLS_RSA_WITH_3DES_EDE_CBC_SHA cipher suite. Clients and servers communicating with O365 after this date must support at least one of the more secure ciphers listed in this topic (see [TLS cipher suites supported by Office 365](technical-reference-details-about-encryption.md#TLSCipherSuites)).</span></span>
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a><span data-ttu-id="065b1-134">Office 365 不再支援 SHA-1 憑證</span><span class="sxs-lookup"><span data-stu-id="065b1-134">Deprecating SHA-1 certificate support in Office 365</span></span>
<span data-ttu-id="065b1-135"><a name="TLS11and12deprecation"> </a></span><span class="sxs-lookup"><span data-stu-id="065b1-135"></span></span>

<span data-ttu-id="065b1-p107">年 6 月 2016 Office 365 不再接受輸出或輸入連線的 sha-1 憑證。如果您目前的憑證鏈結中具有 sha-1 使用憑證，您必須更新使用 SHA-1-2 (安全雜湊演算法 2) 或更有力的雜湊演算法鏈結。</span><span class="sxs-lookup"><span data-stu-id="065b1-p107">As of June 2016, Office 365 no longer accepts a SHA-1 certificate for outbound or inbound connections. If you are currently using a certificate with SHA-1 in the certificate chain, you will need to update the chain to use SHA-2 (Secure Hash Algorithm 2) or a stronger hashing algorithm.</span></span>
  
## <a name="deprecating-rc4-support-in-office-365"></a><span data-ttu-id="065b1-138">Office 365 不再支援 RC4</span><span class="sxs-lookup"><span data-stu-id="065b1-138">Deprecating RC4 support in Office 365</span></span>
<span data-ttu-id="065b1-139"><a name="TLS11and12deprecation"> </a></span><span class="sxs-lookup"><span data-stu-id="065b1-139"></span></span>

<span data-ttu-id="065b1-140">2015 年 7 月，已中止對下列 RC4 加密套件的支援：</span><span class="sxs-lookup"><span data-stu-id="065b1-140">In July 2015, support for the following RC4 cipher suites was discontinued:</span></span>
  
- <span data-ttu-id="065b1-141">TLS_RSA_WITH_RC4_128_SHA</span><span class="sxs-lookup"><span data-stu-id="065b1-141">TLS_RSA_WITH_RC4_128_SHA</span></span>
    
- <span data-ttu-id="065b1-142">TLS_RSA_WITH_RC4_128_MD5</span><span class="sxs-lookup"><span data-stu-id="065b1-142">TLS_RSA_WITH_RC4_128_MD5</span></span>
    
## <a name="deprecating-secure-sockets-layer-ssl-30-support-in-office-365"></a><span data-ttu-id="065b1-143">廢棄 Office 365 的 Secure Sockets Layer (SSL) 3.0 的支援</span><span class="sxs-lookup"><span data-stu-id="065b1-143">Deprecating Secure Sockets Layer (SSL) 3.0 support in Office 365</span></span>
<span data-ttu-id="065b1-144"><a name="TLS11and12deprecation"> </a></span><span class="sxs-lookup"><span data-stu-id="065b1-144"></span></span>

<span data-ttu-id="065b1-p108">啟動 2014 年 12 月 1 日開始支援的 Secure Sockets Layer (SSL) 3.0、 前置 TLS 來停用 Office 365。如需詳細資訊，請參閱 ＜ [Security advisory 3009008](https://technet.microsoft.com/library/security/3009008.aspx)。如需如何確保指示用戶端使用 TLS 1.0 或更高，若要停用 SSL 3.0，請參閱[保護 SSL 3.0 弱點](http://blogs.office.com/2014/10/29/protecting-ssl-3-0-vulnerability/)。</span><span class="sxs-lookup"><span data-stu-id="065b1-p108">Starting December 1, 2014, Office 365 began disabling support for Secure Sockets Layer (SSL) 3.0, the predecessor to TLS. For more information, see [Security advisory 3009008](https://technet.microsoft.com/library/security/3009008.aspx). For instructions on how to ensure clients are using TLS 1.0 or higher and to disable SSL 3.0, see [Protecting SSL 3.0 vulnerability](http://blogs.office.com/2014/10/29/protecting-ssl-3-0-vulnerability/).</span></span>
  
## <a name="tls-cipher-suites-supported-by-office-365"></a><span data-ttu-id="065b1-148">Office 365 支援 TLS 加密套件</span><span class="sxs-lookup"><span data-stu-id="065b1-148">TLS cipher suites supported by Office 365</span></span>
<span data-ttu-id="065b1-149"><a name="TLSCipherSuites"> </a></span><span class="sxs-lookup"><span data-stu-id="065b1-149"></span></span>

<span data-ttu-id="065b1-p109">加密套件是 TLS 用來建立安全連線的加密演算法集合。下表依強度列出 Office 365 支援的加密套件，強度最大的加密套件列在最上面。Office 365 在收到連線要求時，會先嘗試使用最上面的加密套件進行連線，如果不成功，則嘗試清單中的第二個加密套件，依此類推。當 Office 365 傳送連線要求給另一部伺服器或用戶端時，則全由接收端的伺服器或用戶端選擇加密套件，或是否使用 TLS。</span><span class="sxs-lookup"><span data-stu-id="065b1-p109">A cipher suite is a collection of encryption algorithms that TLS uses to establish secure connections. Cipher suites supported by Office 365 are listed in the following table in order of strength with the strongest cipher suite listed first. When Office 365 receives a connection request, Office 365 first attempts to connect using the topmost cipher suite then, if unsuccessful, tries the second cipher suite in the list and so on down the list. When Office 365 sends a connection request to another server or to a client, it's up to the receiving server or client to choose the cipher suite or whether TLS will be used at all.</span></span>
  
|<span data-ttu-id="065b1-154">**通訊協定**</span><span class="sxs-lookup"><span data-stu-id="065b1-154">**Protocols**</span></span>|<span data-ttu-id="065b1-155">**加密套件名稱**</span><span class="sxs-lookup"><span data-stu-id="065b1-155">**Cipher suite name**</span></span>|<span data-ttu-id="065b1-156">**金鑰交換演算法/強度**</span><span class="sxs-lookup"><span data-stu-id="065b1-156">**Key exchange algorithm/Strength**</span></span>|<span data-ttu-id="065b1-157">**完整轉寄密碼支援**</span><span class="sxs-lookup"><span data-stu-id="065b1-157">**Perfect Forward Secrecy support**</span></span>|<span data-ttu-id="065b1-158">**驗證演算法/強度**</span><span class="sxs-lookup"><span data-stu-id="065b1-158">**Authentication algorithm/Strength**</span></span>|<span data-ttu-id="065b1-159">**加密/強度**</span><span class="sxs-lookup"><span data-stu-id="065b1-159">**Cipher/Strength**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="065b1-160">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="065b1-160">TLS 1.2</span></span>  <br/> |<span data-ttu-id="065b1-161">TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384</span><span class="sxs-lookup"><span data-stu-id="065b1-161">TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384</span></span>  <br/> |<span data-ttu-id="065b1-162">ECDH/192</span><span class="sxs-lookup"><span data-stu-id="065b1-162">ECDH/192</span></span>  <br/> |<span data-ttu-id="065b1-163">是</span><span class="sxs-lookup"><span data-stu-id="065b1-163">Yes</span></span>  <br/> |<span data-ttu-id="065b1-164">RSA/112</span><span class="sxs-lookup"><span data-stu-id="065b1-164">RSA/112</span></span>  <br/> |<span data-ttu-id="065b1-165">AES/256</span><span class="sxs-lookup"><span data-stu-id="065b1-165">AES/256</span></span>  <br/> |
|<span data-ttu-id="065b1-166">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="065b1-166">TLS 1.2</span></span>  <br/> |<span data-ttu-id="065b1-167">TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256</span><span class="sxs-lookup"><span data-stu-id="065b1-167">TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256</span></span>  <br/> |<span data-ttu-id="065b1-168">ECDH/128</span><span class="sxs-lookup"><span data-stu-id="065b1-168">ECDH/128</span></span>  <br/> |<span data-ttu-id="065b1-169">是</span><span class="sxs-lookup"><span data-stu-id="065b1-169">Yes</span></span>  <br/> |<span data-ttu-id="065b1-170">RSA/112</span><span class="sxs-lookup"><span data-stu-id="065b1-170">RSA/112</span></span>  <br/> |<span data-ttu-id="065b1-171">AES/128</span><span class="sxs-lookup"><span data-stu-id="065b1-171">AES/128</span></span>  <br/> |
|<span data-ttu-id="065b1-172">TLS 1.0、1.1、1.2</span><span class="sxs-lookup"><span data-stu-id="065b1-172">TLS 1.0, 1.1, 1.2</span></span>  <br/> |<span data-ttu-id="065b1-173">TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA_P384</span><span class="sxs-lookup"><span data-stu-id="065b1-173">TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA_P384</span></span>  <br/> |<span data-ttu-id="065b1-174">ECDH/192</span><span class="sxs-lookup"><span data-stu-id="065b1-174">ECDH/192</span></span>  <br/> |<span data-ttu-id="065b1-175">是</span><span class="sxs-lookup"><span data-stu-id="065b1-175">Yes</span></span>  <br/> |<span data-ttu-id="065b1-176">RSA/112</span><span class="sxs-lookup"><span data-stu-id="065b1-176">RSA/112</span></span>  <br/> |<span data-ttu-id="065b1-177">AES/256</span><span class="sxs-lookup"><span data-stu-id="065b1-177">AES/256</span></span>  <br/> |
|<span data-ttu-id="065b1-178">TLS 1.0、1.1、1.2</span><span class="sxs-lookup"><span data-stu-id="065b1-178">TLS 1.0, 1.1, 1.2</span></span>  <br/> |<span data-ttu-id="065b1-179">TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA_P256</span><span class="sxs-lookup"><span data-stu-id="065b1-179">TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA_P256</span></span>  <br/> |<span data-ttu-id="065b1-180">ECDH/128</span><span class="sxs-lookup"><span data-stu-id="065b1-180">ECDH/128</span></span>  <br/> |<span data-ttu-id="065b1-181">是</span><span class="sxs-lookup"><span data-stu-id="065b1-181">Yes</span></span>  <br/> |<span data-ttu-id="065b1-182">RSA/112</span><span class="sxs-lookup"><span data-stu-id="065b1-182">RSA/112</span></span>  <br/> |<span data-ttu-id="065b1-183">AES/128</span><span class="sxs-lookup"><span data-stu-id="065b1-183">AES/128</span></span>  <br/> |
|<span data-ttu-id="065b1-184">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="065b1-184">TLS 1.2</span></span>  <br/> |<span data-ttu-id="065b1-185">TLS_RSA_WITH_AES_256_CBC_SHA256</span><span class="sxs-lookup"><span data-stu-id="065b1-185">TLS_RSA_WITH_AES_256_CBC_SHA256</span></span>  <br/> |<span data-ttu-id="065b1-186">RSA/112</span><span class="sxs-lookup"><span data-stu-id="065b1-186">RSA/112</span></span>  <br/> |<span data-ttu-id="065b1-187">否</span><span class="sxs-lookup"><span data-stu-id="065b1-187">No</span></span>  <br/> |<span data-ttu-id="065b1-188">RSA/112</span><span class="sxs-lookup"><span data-stu-id="065b1-188">RSA/112</span></span>  <br/> |<span data-ttu-id="065b1-189">AES/256</span><span class="sxs-lookup"><span data-stu-id="065b1-189">AES/256</span></span>  <br/> |
|<span data-ttu-id="065b1-190">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="065b1-190">TLS 1.2</span></span>  <br/> |<span data-ttu-id="065b1-191">TLS_RSA_WITH_AES_128_CBC_SHA256</span><span class="sxs-lookup"><span data-stu-id="065b1-191">TLS_RSA_WITH_AES_128_CBC_SHA256</span></span>  <br/> |<span data-ttu-id="065b1-192">RSA/112</span><span class="sxs-lookup"><span data-stu-id="065b1-192">RSA/112</span></span>  <br/> |<span data-ttu-id="065b1-193">否</span><span class="sxs-lookup"><span data-stu-id="065b1-193">No</span></span>  <br/> |<span data-ttu-id="065b1-194">RSA/112</span><span class="sxs-lookup"><span data-stu-id="065b1-194">RSA/112</span></span>  <br/> |<span data-ttu-id="065b1-195">AES/128</span><span class="sxs-lookup"><span data-stu-id="065b1-195">AES/128</span></span>  <br/> |
|<span data-ttu-id="065b1-196">TLS 1.0、1.1、1.2</span><span class="sxs-lookup"><span data-stu-id="065b1-196">TLS 1.0, 1.1, 1.2</span></span>  <br/> |<span data-ttu-id="065b1-197">TLS_RSA_WITH_AES_256_CBC_SHA</span><span class="sxs-lookup"><span data-stu-id="065b1-197">TLS_RSA_WITH_AES_256_CBC_SHA</span></span>  <br/> |<span data-ttu-id="065b1-198">RSA/112</span><span class="sxs-lookup"><span data-stu-id="065b1-198">RSA/112</span></span>  <br/> |<span data-ttu-id="065b1-199">否</span><span class="sxs-lookup"><span data-stu-id="065b1-199">No</span></span>  <br/> |<span data-ttu-id="065b1-200">RSA/112</span><span class="sxs-lookup"><span data-stu-id="065b1-200">RSA/112</span></span>  <br/> |<span data-ttu-id="065b1-201">AES/256</span><span class="sxs-lookup"><span data-stu-id="065b1-201">AES/256</span></span>  <br/> |
|<span data-ttu-id="065b1-202">TLS 1.0、1.1、1.2</span><span class="sxs-lookup"><span data-stu-id="065b1-202">TLS 1.0, 1.1, 1.2</span></span>  <br/> |<span data-ttu-id="065b1-203">TLS_RSA_WITH_AES_128_CBC_SHA</span><span class="sxs-lookup"><span data-stu-id="065b1-203">TLS_RSA_WITH_AES_128_CBC_SHA</span></span>  <br/> |<span data-ttu-id="065b1-204">RSA/112</span><span class="sxs-lookup"><span data-stu-id="065b1-204">RSA/112</span></span>  <br/> |<span data-ttu-id="065b1-205">否</span><span class="sxs-lookup"><span data-stu-id="065b1-205">No</span></span>  <br/> |<span data-ttu-id="065b1-206">RSA/112</span><span class="sxs-lookup"><span data-stu-id="065b1-206">RSA/112</span></span>  <br/> |<span data-ttu-id="065b1-207">AES/128</span><span class="sxs-lookup"><span data-stu-id="065b1-207">AES/128</span></span>  <br/> |
|<span data-ttu-id="065b1-208">TLS 1.0、1.1、1.2</span><span class="sxs-lookup"><span data-stu-id="065b1-208">TLS 1.0, 1.1, 1.2</span></span>  <br/> |<span data-ttu-id="065b1-209">TLS_RSA_WITH_3DES_EDE_CBC_SHA</span><span class="sxs-lookup"><span data-stu-id="065b1-209">TLS_RSA_WITH_3DES_EDE_CBC_SHA</span></span>  <br/> |<span data-ttu-id="065b1-210">RSA/112</span><span class="sxs-lookup"><span data-stu-id="065b1-210">RSA/112</span></span>  <br/> |<span data-ttu-id="065b1-211">否</span><span class="sxs-lookup"><span data-stu-id="065b1-211">No</span></span>  <br/> |<span data-ttu-id="065b1-212">RSA/112</span><span class="sxs-lookup"><span data-stu-id="065b1-212">RSA/112</span></span>  <br/> |<span data-ttu-id="065b1-213">3DES/192</span><span class="sxs-lookup"><span data-stu-id="065b1-213">3DES/192</span></span>  <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="065b1-214">相關主題</span><span class="sxs-lookup"><span data-stu-id="065b1-214">Related topics</span></span>
<span data-ttu-id="065b1-215"><a name="TLSCipherSuites"> </a></span><span class="sxs-lookup"><span data-stu-id="065b1-215"></span></span>

[<span data-ttu-id="065b1-216">Office 365 中的加密</span><span class="sxs-lookup"><span data-stu-id="065b1-216">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="065b1-217">設定 Office 365 企業版中的加密</span><span class="sxs-lookup"><span data-stu-id="065b1-217">Set up encryption in Office 365 Enterprise</span></span>](set-up-encryption.md)
  
<span data-ttu-id="065b1-218">[在 [Windows 安全性狀態更新 TLS 1.0 Schannel 實作： 2015 年 11 月 24、](https://support.microsoft.com/kb/3117336)</span><span class="sxs-lookup"><span data-stu-id="065b1-218">[Schannel implementation of TLS 1.0 in Windows security status update: November 24, 2015](https://support.microsoft.com/kb/3117336)</span></span>
  
[<span data-ttu-id="065b1-219">TLS/SSL 的密碼編譯加強 (Windows IT 中心)</span><span class="sxs-lookup"><span data-stu-id="065b1-219">TLS/SSL Cryptographic Enhancements (Windows IT Center)</span></span>](https://technet.microsoft.com/en-us/library/cc766285%28v=ws.10%29.aspx)
  

