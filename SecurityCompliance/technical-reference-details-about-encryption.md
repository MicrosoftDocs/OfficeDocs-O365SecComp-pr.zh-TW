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
ms.openlocfilehash: 69365b66479ab89a9c036fe489b4087d327460eb
ms.sourcegitcommit: e4ebef6aaf756eefb86c9f3a602cf75f5d344271
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/07/2018
ms.locfileid: "26026520"
---
# <a name="technical-reference-details-about-encryption-in-office-365"></a><span data-ttu-id="95bc0-103">關於 Office 365 中加密的技術參考細節</span><span class="sxs-lookup"><span data-stu-id="95bc0-103">Technical reference details about encryption in Office 365</span></span>

<span data-ttu-id="95bc0-p101">請參閱本文以了解憑證、 技術及 TLS 用於[Office 365 中的加密](encryption.md)cipher 套件。本文章也提供詳細資訊計劃被取代。</span><span class="sxs-lookup"><span data-stu-id="95bc0-p101">Refer to this article to learn about certificates, technologies, and TLS cipher suites used for [encryption in Office 365](encryption.md). This article also provides details about planned deprecations.</span></span>
  
- <span data-ttu-id="95bc0-106">如果您要尋找的概觀資訊，請參閱[Office 365 中的加密](encryption.md)。</span><span class="sxs-lookup"><span data-stu-id="95bc0-106">If you're looking for overview information, see [Encryption in Office 365](encryption.md).</span></span>
    
- <span data-ttu-id="95bc0-107">如果您正在尋找安裝程式的資訊，請參閱[Office 365 企業版中的加密設定](set-up-encryption.md)。</span><span class="sxs-lookup"><span data-stu-id="95bc0-107">If you're looking for setup information, see [Set up encryption in Office 365 Enterprise](set-up-encryption.md).</span></span>
    
## <a name="microsoft-office-365-certificate-ownership-and-management"></a><span data-ttu-id="95bc0-108">Microsoft Office 365 憑證擁有權和管理</span><span class="sxs-lookup"><span data-stu-id="95bc0-108">Microsoft Office 365 certificate ownership and management</span></span>

<span data-ttu-id="95bc0-109">您不需要購買或維護 Office 365 的憑證，因為 Microsoft 會使用自己的憑證。</span><span class="sxs-lookup"><span data-stu-id="95bc0-109">You do not need to purchase or maintain certificates for Office 365 because Microsoft uses its own certificates.</span></span>
  
## <a name="current-encryption-standards-and-planned-deprecations"></a><span data-ttu-id="95bc0-110">目前的加密標準 （英文） 及計劃被取代</span><span class="sxs-lookup"><span data-stu-id="95bc0-110">Current encryption standards and planned deprecations</span></span>

<span data-ttu-id="95bc0-p102">若要繼續提供最佳的類別加密的 Office 365、 Microsoft 定期檢閱支援的加密標準 （英文）。有時，我們需要取代舊的標準過期與因此較不安全文章清單。本主題會說明有關計劃被取代的目前支援的編碼器套件和其他標準以及詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="95bc0-p102">In order to continue to provide best-in-class encryption for Office 365, Microsoft regularly reviews supported encryption standards. Sometimes, we need to deprecate old standards as they become out of date and therefore less secure. This topic describes currently supported cipher suites and other standards as well as details about planned deprecations.</span></span>
  
## <a name="versions-of-tls-supported-by-office-365"></a><span data-ttu-id="95bc0-114">Office 365 支援的 TLS 版本</span><span class="sxs-lookup"><span data-stu-id="95bc0-114">Versions of TLS supported by Office 365</span></span>

<span data-ttu-id="95bc0-p103">傳輸層安全性 (TLS) 以及 TLS 之前的 SSL 都是密碼編譯通訊協定，它們使用安全性憑證來加密電腦之間的連線，進而透過網路保護通訊安全。Office 365 支援數個 TLS 版本，包括：</span><span class="sxs-lookup"><span data-stu-id="95bc0-p103">Transport Layer Security (TLS), and SSL that came before TLS, are cryptographic protocols that secure communication over a network by using security certificates to encrypt a connection between computers. Office 365 supports several versions of TLS, including:</span></span>
  
- <span data-ttu-id="95bc0-117">TLS 1.2 版 (TLS 1.2)</span><span class="sxs-lookup"><span data-stu-id="95bc0-117">TLS version 1.2 (TLS 1.2)</span></span>
    
- <span data-ttu-id="95bc0-118">TLS 1.1 版 (TLS 1.1)</span><span class="sxs-lookup"><span data-stu-id="95bc0-118">TLS version 1.1 (TLS 1.1)</span></span>
    
- <span data-ttu-id="95bc0-119">TLS 1.0 版 (TLS 1.0)</span><span class="sxs-lookup"><span data-stu-id="95bc0-119">TLS version 1.0 (TLS 1.0)</span></span>
    
 <span data-ttu-id="95bc0-p104">TLS 1.0 與 TLS 1.1 支援將會過時 2018 年 10 月 31、。請參閱[Deprecating 支援 TLS 1.0 和 1.1 及這表示您](technical-reference-details-about-encryption.md#TLS11and12deprecation)如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="95bc0-p104">TLS 1.0 and TLS 1.1 support will be deprecated October 31, 2018. See [Deprecating support for TLS 1.0 and 1.1 and what this means for you](technical-reference-details-about-encryption.md#TLS11and12deprecation) for more information.</span></span> 
  
## <a name="deprecating-support-for-tls-10-and-11-and-what-this-means-for-you"></a><span data-ttu-id="95bc0-122">廢棄的 TLS 1.0 和 1.1 及這表示您的支援</span><span class="sxs-lookup"><span data-stu-id="95bc0-122">Deprecating support for TLS 1.0 and 1.1 and what this means for you</span></span>
<span data-ttu-id="95bc0-123"><a name="TLS11and12deprecation"> </a></span><span class="sxs-lookup"><span data-stu-id="95bc0-123"></span></span>

<span data-ttu-id="95bc0-p105">2018 年 10 月 31 到 Office 365 不再支援 TLS 1.0 和 1.1 版。這表示 Microsoft 不會修正新用戶端、 裝置或使用 TLS 1.0 和 1.1 版連線至 Office 365 服務中找到的問題。</span><span class="sxs-lookup"><span data-stu-id="95bc0-p105">As of October 31, 2018, Office 365 will no longer support TLS 1.0 and 1.1. This means that Microsoft will not fix new issues that are found in clients, devices, or services that connect to Office 365 by using TLS 1.0 and 1.1.</span></span>

<span data-ttu-id="95bc0-p106">請注意這並不代表 Office 365 將會封鎖 TLS 1.0 和 1.1 連線。沒有官方停用或移除 TLS 1.0 和 1.1 版客戶連線 TLS 服務中的日期。最終取代日期會由客戶遙測及還不知道。進行決策之後，會有宣告事先六個月除非我們成為知道的已知危害、 在此情況下我們可能必須擔任小於六個月保護客戶使用的服務。</span><span class="sxs-lookup"><span data-stu-id="95bc0-p106">Note This doesn't mean Office 365 will block TLS 1.0 and 1.1 connections. There is no official date for disabling or removing TLS 1.0 and 1.1 in the TLS service for customer connections. The eventual deprecation date will be determined by customer telemetry and is not yet known. After a decision is made, there will be an announcement six months in advance unless we become aware of a known compromise, in which case we may have to act in less than six months to protect customers who use the services.</span></span>

<span data-ttu-id="95bc0-p107">您應該確定所有的用戶端對伺服器和瀏覽器伺服器組合到 Office 365 服務使用 TLS 1.2 （或更新版本） 來維護連線。您可能必須更新特定用戶端對伺服器與伺服器瀏覽器組合。這對您所做的影響的相關資訊，請參閱[強制 TLS 1.2 版 Office 365 中使用的準備](https://support.microsoft.com/en-us/help/4057306/preparing-for-tls-1-2-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="95bc0-p107">You should make sure that all client-server and browser-server combinations use TLS 1.2 (or a later version) to maintain connection to Office 365 services. You may have to update certain client-server and browser-server combinations. For information about how this impacts you, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/en-us/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>
  
## <a name="deprecating-support-for-3des"></a><span data-ttu-id="95bc0-133">廢棄 3DES 的支援</span><span class="sxs-lookup"><span data-stu-id="95bc0-133">Deprecating support for 3DES</span></span>
<span data-ttu-id="95bc0-134"><a name="TLS11and12deprecation"> </a></span><span class="sxs-lookup"><span data-stu-id="95bc0-134"></span></span>

<span data-ttu-id="95bc0-p108">從 2018 年 10 月 31 Office 365 不再支援 3DES 加密套件使用 Office 365 的通訊。更明確 Office 365 不再支援 TLS_RSA_WITH_3DES_EDE_CBC_SHA 編碼器套件。用戶端和伺服器通訊 O365 之後此日期必須支援至少一個更安全 cipher 列在本主題 （請參閱[TLS 密碼支援的 Office 365 套裝軟體](technical-reference-details-about-encryption.md#TLSCipherSuites)）。</span><span class="sxs-lookup"><span data-stu-id="95bc0-p108">As of October 31, 2018, Office 365 will no longer support the use of 3DES cipher suites for communication to Office 365. More specifically, Office 365 will no longer support the TLS_RSA_WITH_3DES_EDE_CBC_SHA cipher suite. Clients and servers communicating with O365 after this date must support at least one of the more secure ciphers listed in this topic (see [TLS cipher suites supported by Office 365](technical-reference-details-about-encryption.md#TLSCipherSuites)).</span></span>
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a><span data-ttu-id="95bc0-138">Office 365 不再支援 SHA-1 憑證</span><span class="sxs-lookup"><span data-stu-id="95bc0-138">Deprecating SHA-1 certificate support in Office 365</span></span>
<span data-ttu-id="95bc0-139"><a name="TLS11and12deprecation"> </a></span><span class="sxs-lookup"><span data-stu-id="95bc0-139"></span></span>

<span data-ttu-id="95bc0-p109">年 6 月 2016 Office 365 不再接受輸出或輸入連線的 sha-1 憑證。如果您目前的憑證鏈結中具有 sha-1 使用憑證，您必須更新使用 SHA-1-2 (安全雜湊演算法 2) 或更有力的雜湊演算法鏈結。</span><span class="sxs-lookup"><span data-stu-id="95bc0-p109">As of June 2016, Office 365 no longer accepts a SHA-1 certificate for outbound or inbound connections. If you are currently using a certificate with SHA-1 in the certificate chain, you will need to update the chain to use SHA-2 (Secure Hash Algorithm 2) or a stronger hashing algorithm.</span></span>
  
## <a name="deprecating-rc4-support-in-office-365"></a><span data-ttu-id="95bc0-142">Office 365 不再支援 RC4</span><span class="sxs-lookup"><span data-stu-id="95bc0-142">Deprecating RC4 support in Office 365</span></span>
<span data-ttu-id="95bc0-143"><a name="TLS11and12deprecation"> </a></span><span class="sxs-lookup"><span data-stu-id="95bc0-143"></span></span>

<span data-ttu-id="95bc0-144">2015 年 7 月，已中止對下列 RC4 加密套件的支援：</span><span class="sxs-lookup"><span data-stu-id="95bc0-144">In July 2015, support for the following RC4 cipher suites was discontinued:</span></span>
  
- <span data-ttu-id="95bc0-145">TLS_RSA_WITH_RC4_128_SHA</span><span class="sxs-lookup"><span data-stu-id="95bc0-145">TLS_RSA_WITH_RC4_128_SHA</span></span>
    
- <span data-ttu-id="95bc0-146">TLS_RSA_WITH_RC4_128_MD5</span><span class="sxs-lookup"><span data-stu-id="95bc0-146">TLS_RSA_WITH_RC4_128_MD5</span></span>
    
## <a name="deprecating-secure-sockets-layer-ssl-30-support-in-office-365"></a><span data-ttu-id="95bc0-147">廢棄 Office 365 的 Secure Sockets Layer (SSL) 3.0 的支援</span><span class="sxs-lookup"><span data-stu-id="95bc0-147">Deprecating Secure Sockets Layer (SSL) 3.0 support in Office 365</span></span>
<span data-ttu-id="95bc0-148"><a name="TLS11and12deprecation"> </a></span><span class="sxs-lookup"><span data-stu-id="95bc0-148"></span></span>

<span data-ttu-id="95bc0-p110">啟動 2014 年 12 月 1 日開始支援的 Secure Sockets Layer (SSL) 3.0、 前置 TLS 來停用 Office 365。如需詳細資訊，請參閱 ＜ [Security advisory 3009008](https://technet.microsoft.com/library/security/3009008.aspx)。如需如何確保指示用戶端使用 TLS 1.0 或更高，若要停用 SSL 3.0，請參閱[保護 SSL 3.0 弱點](http://blogs.office.com/2014/10/29/protecting-ssl-3-0-vulnerability/)。</span><span class="sxs-lookup"><span data-stu-id="95bc0-p110">Starting December 1, 2014, Office 365 began disabling support for Secure Sockets Layer (SSL) 3.0, the predecessor to TLS. For more information, see [Security advisory 3009008](https://technet.microsoft.com/library/security/3009008.aspx). For instructions on how to ensure clients are using TLS 1.0 or higher and to disable SSL 3.0, see [Protecting SSL 3.0 vulnerability](http://blogs.office.com/2014/10/29/protecting-ssl-3-0-vulnerability/).</span></span>
  
## <a name="tls-cipher-suites-supported-by-office-365"></a><span data-ttu-id="95bc0-152">Office 365 支援 TLS 加密套件</span><span class="sxs-lookup"><span data-stu-id="95bc0-152">TLS cipher suites supported by Office 365</span></span>
<span data-ttu-id="95bc0-153"><a name="TLSCipherSuites"> </a></span><span class="sxs-lookup"><span data-stu-id="95bc0-153"></span></span>

<span data-ttu-id="95bc0-p111">加密套件是 TLS 用來建立安全連線的加密演算法集合。下表依強度列出 Office 365 支援的加密套件，強度最大的加密套件列在最上面。Office 365 在收到連線要求時，會先嘗試使用最上面的加密套件進行連線，如果不成功，則嘗試清單中的第二個加密套件，依此類推。當 Office 365 傳送連線要求給另一部伺服器或用戶端時，則全由接收端的伺服器或用戶端選擇加密套件，或是否使用 TLS。</span><span class="sxs-lookup"><span data-stu-id="95bc0-p111">A cipher suite is a collection of encryption algorithms that TLS uses to establish secure connections. Cipher suites supported by Office 365 are listed in the following table in order of strength with the strongest cipher suite listed first. When Office 365 receives a connection request, Office 365 first attempts to connect using the topmost cipher suite then, if unsuccessful, tries the second cipher suite in the list and so on down the list. When Office 365 sends a connection request to another server or to a client, it's up to the receiving server or client to choose the cipher suite or whether TLS will be used at all.</span></span>
  
|<span data-ttu-id="95bc0-158">**通訊協定**</span><span class="sxs-lookup"><span data-stu-id="95bc0-158">**Protocols**</span></span>|<span data-ttu-id="95bc0-159">**加密套件名稱**</span><span class="sxs-lookup"><span data-stu-id="95bc0-159">**Cipher suite name**</span></span>|<span data-ttu-id="95bc0-160">**金鑰交換演算法/強度**</span><span class="sxs-lookup"><span data-stu-id="95bc0-160">**Key exchange algorithm/Strength**</span></span>|<span data-ttu-id="95bc0-161">**完整轉寄密碼支援**</span><span class="sxs-lookup"><span data-stu-id="95bc0-161">**Perfect Forward Secrecy support**</span></span>|<span data-ttu-id="95bc0-162">**驗證演算法/強度**</span><span class="sxs-lookup"><span data-stu-id="95bc0-162">**Authentication algorithm/Strength**</span></span>|<span data-ttu-id="95bc0-163">**加密/強度**</span><span class="sxs-lookup"><span data-stu-id="95bc0-163">**Cipher/Strength**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="95bc0-164">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="95bc0-164">TLS 1.2</span></span>  <br/> |<span data-ttu-id="95bc0-165">TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384</span><span class="sxs-lookup"><span data-stu-id="95bc0-165">TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384</span></span>  <br/> |<span data-ttu-id="95bc0-166">ECDH/192</span><span class="sxs-lookup"><span data-stu-id="95bc0-166">ECDH/192</span></span>  <br/> |<span data-ttu-id="95bc0-167">是</span><span class="sxs-lookup"><span data-stu-id="95bc0-167">Yes</span></span>  <br/> |<span data-ttu-id="95bc0-168">RSA/112</span><span class="sxs-lookup"><span data-stu-id="95bc0-168">RSA/112</span></span>  <br/> |<span data-ttu-id="95bc0-169">AES/256</span><span class="sxs-lookup"><span data-stu-id="95bc0-169">AES/256</span></span>  <br/> |
|<span data-ttu-id="95bc0-170">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="95bc0-170">TLS 1.2</span></span>  <br/> |<span data-ttu-id="95bc0-171">TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256</span><span class="sxs-lookup"><span data-stu-id="95bc0-171">TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256</span></span>  <br/> |<span data-ttu-id="95bc0-172">ECDH/128</span><span class="sxs-lookup"><span data-stu-id="95bc0-172">ECDH/128</span></span>  <br/> |<span data-ttu-id="95bc0-173">是</span><span class="sxs-lookup"><span data-stu-id="95bc0-173">Yes</span></span>  <br/> |<span data-ttu-id="95bc0-174">RSA/112</span><span class="sxs-lookup"><span data-stu-id="95bc0-174">RSA/112</span></span>  <br/> |<span data-ttu-id="95bc0-175">AES/128</span><span class="sxs-lookup"><span data-stu-id="95bc0-175">AES/128</span></span>  <br/> |
|<span data-ttu-id="95bc0-176">TLS 1.0、1.1、1.2</span><span class="sxs-lookup"><span data-stu-id="95bc0-176">TLS 1.0, 1.1, 1.2</span></span>  <br/> |<span data-ttu-id="95bc0-177">TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA_P384</span><span class="sxs-lookup"><span data-stu-id="95bc0-177">TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA_P384</span></span>  <br/> |<span data-ttu-id="95bc0-178">ECDH/192</span><span class="sxs-lookup"><span data-stu-id="95bc0-178">ECDH/192</span></span>  <br/> |<span data-ttu-id="95bc0-179">是</span><span class="sxs-lookup"><span data-stu-id="95bc0-179">Yes</span></span>  <br/> |<span data-ttu-id="95bc0-180">RSA/112</span><span class="sxs-lookup"><span data-stu-id="95bc0-180">RSA/112</span></span>  <br/> |<span data-ttu-id="95bc0-181">AES/256</span><span class="sxs-lookup"><span data-stu-id="95bc0-181">AES/256</span></span>  <br/> |
|<span data-ttu-id="95bc0-182">TLS 1.0、1.1、1.2</span><span class="sxs-lookup"><span data-stu-id="95bc0-182">TLS 1.0, 1.1, 1.2</span></span>  <br/> |<span data-ttu-id="95bc0-183">TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA_P256</span><span class="sxs-lookup"><span data-stu-id="95bc0-183">TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA_P256</span></span>  <br/> |<span data-ttu-id="95bc0-184">ECDH/128</span><span class="sxs-lookup"><span data-stu-id="95bc0-184">ECDH/128</span></span>  <br/> |<span data-ttu-id="95bc0-185">是</span><span class="sxs-lookup"><span data-stu-id="95bc0-185">Yes</span></span>  <br/> |<span data-ttu-id="95bc0-186">RSA/112</span><span class="sxs-lookup"><span data-stu-id="95bc0-186">RSA/112</span></span>  <br/> |<span data-ttu-id="95bc0-187">AES/128</span><span class="sxs-lookup"><span data-stu-id="95bc0-187">AES/128</span></span>  <br/> |
|<span data-ttu-id="95bc0-188">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="95bc0-188">TLS 1.2</span></span>  <br/> |<span data-ttu-id="95bc0-189">TLS_RSA_WITH_AES_256_CBC_SHA256</span><span class="sxs-lookup"><span data-stu-id="95bc0-189">TLS_RSA_WITH_AES_256_CBC_SHA256</span></span>  <br/> |<span data-ttu-id="95bc0-190">RSA/112</span><span class="sxs-lookup"><span data-stu-id="95bc0-190">RSA/112</span></span>  <br/> |<span data-ttu-id="95bc0-191">否</span><span class="sxs-lookup"><span data-stu-id="95bc0-191">No</span></span>  <br/> |<span data-ttu-id="95bc0-192">RSA/112</span><span class="sxs-lookup"><span data-stu-id="95bc0-192">RSA/112</span></span>  <br/> |<span data-ttu-id="95bc0-193">AES/256</span><span class="sxs-lookup"><span data-stu-id="95bc0-193">AES/256</span></span>  <br/> |
|<span data-ttu-id="95bc0-194">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="95bc0-194">TLS 1.2</span></span>  <br/> |<span data-ttu-id="95bc0-195">TLS_RSA_WITH_AES_128_CBC_SHA256</span><span class="sxs-lookup"><span data-stu-id="95bc0-195">TLS_RSA_WITH_AES_128_CBC_SHA256</span></span>  <br/> |<span data-ttu-id="95bc0-196">RSA/112</span><span class="sxs-lookup"><span data-stu-id="95bc0-196">RSA/112</span></span>  <br/> |<span data-ttu-id="95bc0-197">否</span><span class="sxs-lookup"><span data-stu-id="95bc0-197">No</span></span>  <br/> |<span data-ttu-id="95bc0-198">RSA/112</span><span class="sxs-lookup"><span data-stu-id="95bc0-198">RSA/112</span></span>  <br/> |<span data-ttu-id="95bc0-199">AES/128</span><span class="sxs-lookup"><span data-stu-id="95bc0-199">AES/128</span></span>  <br/> |
|<span data-ttu-id="95bc0-200">TLS 1.0、1.1、1.2</span><span class="sxs-lookup"><span data-stu-id="95bc0-200">TLS 1.0, 1.1, 1.2</span></span>  <br/> |<span data-ttu-id="95bc0-201">TLS_RSA_WITH_AES_256_CBC_SHA</span><span class="sxs-lookup"><span data-stu-id="95bc0-201">TLS_RSA_WITH_AES_256_CBC_SHA</span></span>  <br/> |<span data-ttu-id="95bc0-202">RSA/112</span><span class="sxs-lookup"><span data-stu-id="95bc0-202">RSA/112</span></span>  <br/> |<span data-ttu-id="95bc0-203">否</span><span class="sxs-lookup"><span data-stu-id="95bc0-203">No</span></span>  <br/> |<span data-ttu-id="95bc0-204">RSA/112</span><span class="sxs-lookup"><span data-stu-id="95bc0-204">RSA/112</span></span>  <br/> |<span data-ttu-id="95bc0-205">AES/256</span><span class="sxs-lookup"><span data-stu-id="95bc0-205">AES/256</span></span>  <br/> |
|<span data-ttu-id="95bc0-206">TLS 1.0、1.1、1.2</span><span class="sxs-lookup"><span data-stu-id="95bc0-206">TLS 1.0, 1.1, 1.2</span></span>  <br/> |<span data-ttu-id="95bc0-207">TLS_RSA_WITH_AES_128_CBC_SHA</span><span class="sxs-lookup"><span data-stu-id="95bc0-207">TLS_RSA_WITH_AES_128_CBC_SHA</span></span>  <br/> |<span data-ttu-id="95bc0-208">RSA/112</span><span class="sxs-lookup"><span data-stu-id="95bc0-208">RSA/112</span></span>  <br/> |<span data-ttu-id="95bc0-209">否</span><span class="sxs-lookup"><span data-stu-id="95bc0-209">No</span></span>  <br/> |<span data-ttu-id="95bc0-210">RSA/112</span><span class="sxs-lookup"><span data-stu-id="95bc0-210">RSA/112</span></span>  <br/> |<span data-ttu-id="95bc0-211">AES/128</span><span class="sxs-lookup"><span data-stu-id="95bc0-211">AES/128</span></span>  <br/> |
|<span data-ttu-id="95bc0-212">TLS 1.0、1.1、1.2</span><span class="sxs-lookup"><span data-stu-id="95bc0-212">TLS 1.0, 1.1, 1.2</span></span>  <br/> |<span data-ttu-id="95bc0-213">TLS_RSA_WITH_3DES_EDE_CBC_SHA</span><span class="sxs-lookup"><span data-stu-id="95bc0-213">TLS_RSA_WITH_3DES_EDE_CBC_SHA</span></span>  <br/> |<span data-ttu-id="95bc0-214">RSA/112</span><span class="sxs-lookup"><span data-stu-id="95bc0-214">RSA/112</span></span>  <br/> |<span data-ttu-id="95bc0-215">否</span><span class="sxs-lookup"><span data-stu-id="95bc0-215">No</span></span>  <br/> |<span data-ttu-id="95bc0-216">RSA/112</span><span class="sxs-lookup"><span data-stu-id="95bc0-216">RSA/112</span></span>  <br/> |<span data-ttu-id="95bc0-217">3DES/192</span><span class="sxs-lookup"><span data-stu-id="95bc0-217">3DES/192</span></span>  <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="95bc0-218">相關主題</span><span class="sxs-lookup"><span data-stu-id="95bc0-218">Related topics</span></span>
<span data-ttu-id="95bc0-219"><a name="TLSCipherSuites"> </a></span><span class="sxs-lookup"><span data-stu-id="95bc0-219"></span></span>

[<span data-ttu-id="95bc0-220">Office 365 中的加密</span><span class="sxs-lookup"><span data-stu-id="95bc0-220">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="95bc0-221">設定 Office 365 企業版中的加密</span><span class="sxs-lookup"><span data-stu-id="95bc0-221">Set up encryption in Office 365 Enterprise</span></span>](set-up-encryption.md)
  
<span data-ttu-id="95bc0-222">[在 [Windows 安全性狀態更新 TLS 1.0 Schannel 實作： 2015 年 11 月 24、](https://support.microsoft.com/kb/3117336)</span><span class="sxs-lookup"><span data-stu-id="95bc0-222">[Schannel implementation of TLS 1.0 in Windows security status update: November 24, 2015](https://support.microsoft.com/kb/3117336)</span></span>
  
[<span data-ttu-id="95bc0-223">TLS/SSL 的密碼編譯加強 (Windows IT 中心)</span><span class="sxs-lookup"><span data-stu-id="95bc0-223">TLS/SSL Cryptographic Enhancements (Windows IT Center)</span></span>](https://technet.microsoft.com/en-us/library/cc766285%28v=ws.10%29.aspx)
  

