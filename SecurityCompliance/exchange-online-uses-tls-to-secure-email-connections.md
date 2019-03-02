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
# <a name="how-exchange-online-uses-tls-to-secure-email-connections-in-office-365"></a><span data-ttu-id="ca639-104">Exchange Online 如何使用 TLS 來保護 Office 365 中的電子郵件連線</span><span class="sxs-lookup"><span data-stu-id="ca639-104">How Exchange Online uses TLS to secure email connections in Office 365</span></span>

<span data-ttu-id="ca639-p102">了解如何 Exchange Online 和 Office 365 使用傳輸層安全性 (TLS) 和轉寄密碼 (FS) 來保護電子郵件通訊。也會提供關於由 Microsoft Exchange Online 的發出的憑證資訊。</span><span class="sxs-lookup"><span data-stu-id="ca639-p102">Learn how Exchange Online and Office 365 use Transport Layer Security (TLS) and Forward Secrecy (FS) to secure email communications. Also provides information about the certificate issued by Microsoft for Exchange Online.</span></span>
  
## <a name="tls-basics-for-office-365-and-exchange-online"></a><span data-ttu-id="ca639-107">Office 365 和 Exchange Online 的 TLS 基本概念</span><span class="sxs-lookup"><span data-stu-id="ca639-107">TLS basics for Office 365 and Exchange Online</span></span>

<span data-ttu-id="ca639-p103">傳輸層安全性 (TLS) 和 TLS，之前的 SSL 是密碼編譯通訊協定，透過網路的安全通訊所使用的安全性憑證來加密電腦之間的連線。TLS 會取代 Secure Sockets Layer (SSL) 和通常稱為 SSL 3.1。針對 Exchange Online，我們會使用 TLS 來加密我們的 Exchange 伺服器之間連線的連線，我們的 Exchange 伺服器與其他伺服器，例如您的內部部署 Exchange 伺服器或收件者的郵件伺服器之間。一旦已加密的連線，則會透過加密通道傳送透過該連線傳送的所有資料。不過，如果您轉寄透過 TLS 加密的連線已傳送的郵件，該郵件不一定會加密。這是因為簡單來說，TLS 不會加密郵件，只要連線。</span><span class="sxs-lookup"><span data-stu-id="ca639-p103">Transport Layer Security (TLS), and SSL that came before TLS, are cryptographic protocols that secure communication over a network by using security certificates to encrypt a connection between computers. TLS supersedes Secure Sockets Layer (SSL) and is often referred to as SSL 3.1. For Exchange Online, we use TLS to encrypt the connections between our Exchange servers and the connections between our Exchange servers and other servers such as your on-premises Exchange servers or your recipients' mail servers. Once the connection is encrypted, all data sent through that connection is sent through the encrypted channel. However, if you forward a message that was sent through a TLS-encrypted connection, that message isn't necessarily encrypted. This is because, in simple terms, TLS doesn't encrypt the message, just the connection.</span></span>
  
<span data-ttu-id="ca639-p104">如果您想要加密郵件，便需要使用能加密郵件內容的加密技術，如 Office 郵件加密之類的技術。如需 Office 365 郵件加密選項的相關資訊，請參閱 [Email encryption in Office 365](email-encryption.md) 及 [Office 365 Message Encryption (OME)](ome.md)。</span><span class="sxs-lookup"><span data-stu-id="ca639-p104">If you want to encrypt the message you need to use an encryption technology that encrypts the message contents, for example, something like Office Message Encryption. See [Email encryption in Office 365](email-encryption.md) and [Office 365 Message Encryption (OME)](ome.md) for information on message encryption options in Office 365.</span></span> 
  
<span data-ttu-id="ca639-p105">我們建議您想要設定 Office 365 與內部部署組織或另一個組織，例如協力廠商之間的對應關係的安全通道的情況下使用 TLS。Exchange Online 一律會嘗試先使用 TLS 來保護您的電子郵件，但無法永遠執行這項操作如果另一方並不提供 TLS 安全性。繼續閱讀以了解如何保護您的內部部署伺服器或重要的協力廠商的所有郵件，以及在使用*連接器*。</span><span class="sxs-lookup"><span data-stu-id="ca639-p105">We recommend using TLS in situations where you want to set up a secure channel of correspondence between Office 365 and your on-premises organization or another organization, such as a partner. Exchange Online always attempts to use TLS first to secure your email but cannot always do this if the other party does not offer TLS security. Keep reading to find out how you can secure all mail to your on-premises servers or important partners by using  *connectors*.</span></span> 
  
## <a name="how-exchange-online-uses-tls-between-exchange-online-customers"></a><span data-ttu-id="ca639-119">Exchange Online 如何在 Exchange Online 客戶之間使用 TLS</span><span class="sxs-lookup"><span data-stu-id="ca639-119">How Exchange Online uses TLS between Exchange Online customers</span></span>

<span data-ttu-id="ca639-p106">Exchange Online 伺服器一律會使用 TLS 1.2 加密連往資料中心內其他 Exchange Online 伺服器的連線。當您傳送郵件給 Office 365 組織內的收件者時，該電子郵件會自動透過使用 TLS 加密的連線來傳送。同時，所有傳送給其他 Office 365 客戶的電子郵件，都會透過使用 TLS 加密並使用轉寄密碼保護的連線來傳送。</span><span class="sxs-lookup"><span data-stu-id="ca639-p106">Exchange Online servers always encrypt connections to other Exchange Online servers in our datacenters with TLS 1.2. When you send mail to a recipient that is within your Office 365 organization, that email is automatically sent over a connection that is encrypted using TLS. Also, all email that you send to other Office 365 customers is sent over connections that are encrypted using TLS and are secured using Forward Secrecy.</span></span>
  
## <a name="how-office-365-uses-tls-between-office-365-and-external-trusted-partners"></a><span data-ttu-id="ca639-123">Office 365 如何使用 Office 365 及外部、 受信任的協力廠商之間的 TLS</span><span class="sxs-lookup"><span data-stu-id="ca639-123">How Office 365 uses TLS between Office 365 and external, trusted partners</span></span>

<span data-ttu-id="ca639-p107">根據預設，Exchange Online 一律使用隨機 TLS。這表示 Exchange Online 一律會嘗試先，加密連線與最安全的 TLS 版本運作的 TLS cipher 運送途中清單向下，直到找到一個在其上雙方可以同意。除非您已設定 Exchange Online，以確定透過安全連線僅傳送給該收件者的郵件，然後依預設郵件將傳送未加密如果收件者的組織不支援 TLS 加密。隨機 TLS 是大部分的公司已足夠。不過，擁有規範需求，例如醫療、 銀行業或政府組織的商務用，您可以設定 Exchange Online 若需要，請或強制 TLS。如需相關指示，請參閱 <<c0>使用 Office 365 中的連接器設定郵件流程。</span><span class="sxs-lookup"><span data-stu-id="ca639-p107">By default, Exchange Online always uses opportunistic TLS. This means Exchange Online always tries to encrypt connections with the most secure version of TLS first, then works its way down the list of TLS ciphers until it finds one on which both parties can agree. Unless you have configured Exchange Online to ensure that messages to that recipient are only sent through secure connections, then by default the message will be sent unencrypted if the recipient organization doesn't support TLS encryption. Opportunistic TLS is sufficient for most businesses. However, for business that have compliance requirements such as medical, banking, or government organizations, you can configure Exchange Online to require, or force, TLS. For instructions, see [Configure mail flow using connectors in Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx).</span></span>
  
<span data-ttu-id="ca639-p108">如果您決定組織和受信任的夥伴組織之間設定 TLS，Exchange Online 可以使用強制的 TLS 來建立受信任的通訊通道。強制的 TLS 要求夥伴組織到 Exchange Online 的安全性憑證驗證才能傳送郵件給您。您的合作夥伴將需要管理自己的憑證，才能執行此動作。在 Exchange Online 中，我們會使用連接器來保護您免於受到非法存取之前抵達收件者的電子郵件提供者傳送的郵件。如需使用連接器來設定郵件流程的詳細資訊，請參閱 <<c0>使用 Office 365 中的連接器設定郵件流程。</span><span class="sxs-lookup"><span data-stu-id="ca639-p108">If you decide to configure TLS between your organization and a trusted partner organization, Exchange Online can use forced TLS to create trusted channels of communication. Forced TLS requires your partner organization to authenticate to Exchange Online with a security certificate in order to send mail to you. Your partner will need to manage their own certificates in order to do this. In Exchange Online, we use connectors to protect messages that you send from unauthorized access before they arrive at the recipient's email provider. For information on using connectors to configure mail flow, see [Configure mail flow using connectors in Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx).</span></span>
  
## <a name="tls-and-hybrid-exchange-server-deployments"></a><span data-ttu-id="ca639-135">TLS 和混合 Exchange Server 部署</span><span class="sxs-lookup"><span data-stu-id="ca639-135">TLS and hybrid Exchange Server deployments</span></span>

<span data-ttu-id="ca639-p109">如果您要管理混合 Exchange 部署，您的內部部署 Exchange 伺服器需求，來驗證 Office 365 才能傳送郵件給收件者的信箱使用的安全性憑證是只能在 Office 365。因此，您需要管理您的內部部署 Exchange 伺服器您自己的安全性憑證。您必須也安全地儲存，及維護這些伺服器憑證。如需管理混合式部署中的憑證的詳細資訊，請參閱 <<c0>混合式部署的憑證需求。</span><span class="sxs-lookup"><span data-stu-id="ca639-p109">If you are managing a hybrid Exchange deployment, your on-premises Exchange server needs to authenticate to Office 365 using a security certificate in order to send mail to recipients whose mailboxes are only in Office 365. As a result, you need to manage your own security certificates for your on-premises Exchange servers. You must also securely store and maintain these server certificates. For more information about managing certificates in hybrid deployments, see [Certificate requirements for hybrid deployments](https://technet.microsoft.com/library/hh563848%28v=exchg.150%29.aspx).</span></span>
  
## <a name="how-to-set-up-forced-tls-for-exchange-online-in-office-365"></a><span data-ttu-id="ca639-140">如何在 Office 365 中設定 Exchange Online 的強制 TLS</span><span class="sxs-lookup"><span data-stu-id="ca639-140">How to set up forced TLS for Exchange Online in Office 365</span></span>

<span data-ttu-id="ca639-p110">Exchange Online 的客戶，為了讓工作的強制 TLS 來保護所有的傳送和接收電子郵件，您要設定多個需要透過 TLS 的連接器。您將需要一個連接器，電子郵件傳送至使用者信箱並從使用者信箱傳送的電子郵件的另一個連接器。在 Exchange 系統管理中心，在 Office 365 中建立這些連接器。如需相關指示，請參閱 <<c0>使用 Office 365 中的連接器設定郵件流程。</span><span class="sxs-lookup"><span data-stu-id="ca639-p110">For Exchange Online customers, in order for forced TLS to work to secure all of your sent and received email, you need to set up more than one connector that requires TLS. You'll need one connector for email sent to your user mailboxes and another connector for email sent from your user mailboxes. Create these connectors in the Exchange admin center in Office 365. For instructions, see [Configure mail flow using connectors in Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx).</span></span>
  
## <a name="tls-certificate-information-for-exchange-online"></a><span data-ttu-id="ca639-145">Exchange Online 的 TLS 憑證資訊</span><span class="sxs-lookup"><span data-stu-id="ca639-145">TLS certificate information for Exchange Online</span></span>

<span data-ttu-id="ca639-p111">下表說明 Exchange Online 使用的憑證資訊。如果您的業務合作夥伴設定其電子郵件伺服器上的強制 TLS，您必須提供這項資訊給他們。請注意，基於安全性考量，我們憑證並變更的時候。我們已在我們的資料中心內來導入更新我們憑證。新的憑證是從 2018 年 9 月 3 日有效。</span><span class="sxs-lookup"><span data-stu-id="ca639-p111">The certificate information used by Exchange Online is described in the following table. If your business partner is setting up forced TLS on their email server, you will need to provide this information to them. Be aware that for security reasons, our certificates do change from time to time. We have rolled out an update to our certificate within our datacenters. The new certificate is valid from September 3, 2018.</span></span>
  
 <span data-ttu-id="ca639-151">**從 2018 年 9 月 3 日有效目前的憑證資訊**</span><span class="sxs-lookup"><span data-stu-id="ca639-151">**Current certificate information valid from September 3, 2018**</span></span>
  
|<span data-ttu-id="ca639-152">**屬性**</span><span class="sxs-lookup"><span data-stu-id="ca639-152">**Attribute**</span></span>|<span data-ttu-id="ca639-153">**值**</span><span class="sxs-lookup"><span data-stu-id="ca639-153">**Value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ca639-154">憑證授權單位根發行者</span><span class="sxs-lookup"><span data-stu-id="ca639-154">Certificate authority root issuer</span></span>  <br/> |<span data-ttu-id="ca639-155">GlobalSign 根 CA – R1</span><span class="sxs-lookup"><span data-stu-id="ca639-155">GlobalSign Root CA – R1</span></span> <br/> |
|<span data-ttu-id="ca639-156">憑證名稱</span><span class="sxs-lookup"><span data-stu-id="ca639-156">Certificate name</span></span>  <br/> |<span data-ttu-id="ca639-157">mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ca639-157">mail.protection.outlook.com</span></span>  <br/> |
|<span data-ttu-id="ca639-158">組織</span><span class="sxs-lookup"><span data-stu-id="ca639-158">Organization</span></span>  <br/> |<span data-ttu-id="ca639-159">Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="ca639-159">Microsoft Corporation</span></span>  <br/> |
|<span data-ttu-id="ca639-160">組織單位</span><span class="sxs-lookup"><span data-stu-id="ca639-160">Organization unit</span></span>  <br/> |  <br/> |
|<span data-ttu-id="ca639-161">憑證金鑰強度</span><span class="sxs-lookup"><span data-stu-id="ca639-161">Certificate key strength</span></span>  <br/> |<span data-ttu-id="ca639-162">2048</span><span class="sxs-lookup"><span data-stu-id="ca639-162">2048</span></span>  <br/> |
   
 <span data-ttu-id="ca639-163">**已被取代的憑證資訊起直到 2018 年 9 月 3 日**</span><span class="sxs-lookup"><span data-stu-id="ca639-163">**Deprecated certificate information valid until September 3, 2018**</span></span>
  
<span data-ttu-id="ca639-164">為了協助確保順利轉移，我們將會繼續提供舊的憑證資訊供您參考一些時間，不過，您應該使用目前的憑證資訊現在開始。</span><span class="sxs-lookup"><span data-stu-id="ca639-164">To help ensure a smooth transition, we will continue to provide the old certificate information for your reference for some time, however, you should use the current certificate information from now on.</span></span>
  
****

|<span data-ttu-id="ca639-165">**屬性**</span><span class="sxs-lookup"><span data-stu-id="ca639-165">**Attribute**</span></span>|<span data-ttu-id="ca639-166">**值**</span><span class="sxs-lookup"><span data-stu-id="ca639-166">**Value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ca639-167">憑證授權單位根發行者</span><span class="sxs-lookup"><span data-stu-id="ca639-167">Certificate authority root issuer</span></span>  <br/> |<span data-ttu-id="ca639-168">Baltimore CyberTrust Root</span><span class="sxs-lookup"><span data-stu-id="ca639-168">Baltimore CyberTrust Root</span></span>  <br/> |
|<span data-ttu-id="ca639-169">憑證名稱</span><span class="sxs-lookup"><span data-stu-id="ca639-169">Certificate name</span></span>  <br/> |<span data-ttu-id="ca639-170">mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ca639-170">mail.protection.outlook.com</span></span>  <br/> |
|<span data-ttu-id="ca639-171">組織</span><span class="sxs-lookup"><span data-stu-id="ca639-171">Organization</span></span>  <br/> |<span data-ttu-id="ca639-172">Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="ca639-172">Microsoft Corporation</span></span>  <br/> |
|<span data-ttu-id="ca639-173">組織單位</span><span class="sxs-lookup"><span data-stu-id="ca639-173">Organization unit</span></span>  <br/> |<span data-ttu-id="ca639-174">Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="ca639-174">Microsoft Corporation</span></span>  <br/> |
|<span data-ttu-id="ca639-175">憑證金鑰強度</span><span class="sxs-lookup"><span data-stu-id="ca639-175">Certificate key strength</span></span>  <br/> |<span data-ttu-id="ca639-176">2048</span><span class="sxs-lookup"><span data-stu-id="ca639-176">2048</span></span>  <br/> |
   
## <a name="prepare-for-the-new-exchange-online-certificate"></a><span data-ttu-id="ca639-177">準備新的 Exchange Online 憑證</span><span class="sxs-lookup"><span data-stu-id="ca639-177">Prepare for the new Exchange Online certificate</span></span>

<span data-ttu-id="ca639-p112">新的憑證是由不同的憑證授權單位 (CA) 發出從 Exchange Online 使用的前一個憑證。因此，您可能需要執行某些動作，才能使用新的憑證。</span><span class="sxs-lookup"><span data-stu-id="ca639-p112">The new certificate is issued by a different certificate authority (CA) from the previous certificate used by Exchange Online. As a result, you may need to perform some actions in order to use the new certificate.</span></span>

<span data-ttu-id="ca639-p113">新的憑證需要連線至新的 CA 一部分驗證憑證的端點。若要執行這項操作失敗可能會導致郵件流程所造成負面影響。保護您具有僅限可讓郵件伺服器的防火牆伺服器連線與特定目的地的郵件如果您要檢查您的伺服器是否能夠驗證新的憑證。若要確認您的伺服器可以使用新的憑證，請完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="ca639-p113">The new certificate requires connecting to the endpoints of the new CA as part of validating the certificate. Failure to do so can result in mail flow being negatively affected. If you protect your mail servers with firewalls that only let the mail servers connect with certain destinations you need to check if your server is able to validate the new certificate. To confirm that your server can use the new certificate, complete these steps:</span></span>

1. <span data-ttu-id="ca639-184">連線至您使用 Windows PowerShell 在本機 Exchange 伺服器，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ca639-184">Connect to your local Exchange Server using Windows PowerShell and then run the following command:</span></span>  
  `certutil -URL http://crl.globalsign.com/gsorganizationvalsha2g3.crl`
2. <span data-ttu-id="ca639-185">在出現的視窗中，選擇 [**擷取**]。</span><span class="sxs-lookup"><span data-stu-id="ca639-185">On the window that appears, choose **Retrieve**.</span></span>
3. <span data-ttu-id="ca639-p114">公用程式完成其檢查時就會傳回狀態。如果狀態會顯示 **[確定]**，您的郵件伺服器可以成功驗證新的憑證。如果不是，您需要判斷造成失敗的連線。大部分情況下，您需要更新的防火牆設定。需要存取的端點的完整清單包括：</span><span class="sxs-lookup"><span data-stu-id="ca639-p114">When the utility completes its check it returns a status. If the status displays **OK**, then your mail server can successfully validate the new certificate. If not, you need to determine what is causing the connections to fail. Most likely, you need to update the settings of a firewall. The full list of endpoints that need to be accessed include:</span></span>
    - <span data-ttu-id="ca639-191">ocsp.globalsign.com</span><span class="sxs-lookup"><span data-stu-id="ca639-191">ocsp.globalsign.com</span></span>
     - <span data-ttu-id="ca639-192">crl.globalsign.com</span><span class="sxs-lookup"><span data-stu-id="ca639-192">crl.globalsign.com</span></span>
     - <span data-ttu-id="ca639-193">secure.globalsign.com</span><span class="sxs-lookup"><span data-stu-id="ca639-193">secure.globalsign.com</span></span>   

<span data-ttu-id="ca639-p115">一般而言，您會收到更新自動透過 Windows 更新您的根憑證。不過有某些部署中防止這些更新會自動發生的地方有額外的安全性。在這些鎖定的部署中其中 Windows Update 無法自動更新的根憑證，您必須確定將正確的根 CA 憑證已安裝，請完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="ca639-p115">Normally, you receive updates to your root certificates automatically through Windows Update. However some deployments have additional security in place that prevents these updates from occurring automatically. In these locked-down deployments where Windows Update can't automatically update root certificates, you need to ensure that the correct root CA certificate is installed by completing these steps:</span></span>
1.  <span data-ttu-id="ca639-197">連線至您使用 Windows PowerShell 在本機 Exchange 伺服器，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ca639-197">Connect to your local Exchange Server using Windows PowerShell and then run the following command:</span></span>  
  `certmgr.msc`
2. <span data-ttu-id="ca639-198">[**受信任的根憑證授權單位/憑證**，請先確認已列出新的憑證。</span><span class="sxs-lookup"><span data-stu-id="ca639-198">Under **Trusted Root Certification Authority/Certificates**, confirm that the new certificate is listed.</span></span>

## <a name="get-more-information-about-tls-and-office-365"></a><span data-ttu-id="ca639-199">取得 TLS 和 Office 365 的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="ca639-199">Get more information about TLS and Office 365</span></span>

<span data-ttu-id="ca639-200">支援的加密套件清單，請參閱[關於 Office 365 中加密的技術參考細節](technical-reference-details-about-encryption.md)。</span><span class="sxs-lookup"><span data-stu-id="ca639-200">For a list of supported cipher suites, see [Technical reference details about encryption in Office 365](technical-reference-details-about-encryption.md).</span></span>
  
[<span data-ttu-id="ca639-201">為夥伴組織的安全郵件流程設定連接器</span><span class="sxs-lookup"><span data-stu-id="ca639-201">Set up connectors for secure mail flow with a partner organization</span></span>](https://technet.microsoft.com/library/dn751021%28v=exchg.150%29.aspx)
  
[<span data-ttu-id="ca639-202">具有增強的電子郵件安全性的連接器</span><span class="sxs-lookup"><span data-stu-id="ca639-202">Connectors with enhanced email security</span></span>](https://technet.microsoft.com/library/261d92e4-7371-4555-b781-2062b5bb5278.aspx)
  
[<span data-ttu-id="ca639-203">Office 365 中的加密</span><span class="sxs-lookup"><span data-stu-id="ca639-203">Encryption in Office 365</span></span>](encryption.md)
  

