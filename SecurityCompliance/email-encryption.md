---
title: Office 365 中的電子郵件加密
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c0d87cbe-6d65-4c03-88ad-5216ea5564e8
description: 比較 Office 365 包括 Office 郵件加密 (OME)、 S/MIME、 資訊版權管理 (IRM) 中的加密方式並了解傳輸層安全性 (TLS)。
ms.openlocfilehash: 92751bd34a3ff002d53a8b1d088d5d1ac3fcb078
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213366"
---
# <a name="email-encryption-in-office-365"></a><span data-ttu-id="692ce-103">Office 365 中的電子郵件加密</span><span class="sxs-lookup"><span data-stu-id="692ce-103">Email encryption in Office 365</span></span>

<span data-ttu-id="692ce-104">本文會比較 Office 365 包括 Office 郵件加密 (OME)、 S/MIME、 資訊版權管理 (IRM) 中的加密選項並介紹傳輸層安全性 (TLS)。</span><span class="sxs-lookup"><span data-stu-id="692ce-104">This article compares encryption options in Office 365 including Office Message Encryption (OME), S/MIME, Information Rights Management (IRM), and introduces Transport Layer Security (TLS).</span></span>
  
<span data-ttu-id="692ce-p101">Office 365 提供可協助您滿足業務需求的電子郵件安全性的多個加密選項。本文提供三種方式來加密 Office 365 中的電子郵件。若要深入了解 Office 365 中的所有安全性功能，請造訪[Office 365 信任中心](http://go.microsoft.com/fwlink/p/?LinkID=282470)。本文介紹加密說明 Office 365 中的安全電子郵件的 Office 365 管理員可使用三種類型：</span><span class="sxs-lookup"><span data-stu-id="692ce-p101">Office 365 delivers multiple encryption options to help you meet your business needs for email security. This article presents three ways to encrypt email in Office 365. If you want to learn more about all security features in Office 365, visit the [Office 365 Trust Center](http://go.microsoft.com/fwlink/p/?LinkID=282470). This article introduces the three types of encryption available for Office 365 administrators to help secure email in Office 365:</span></span>
  
- <span data-ttu-id="692ce-109">Office 郵件加密 (OME)。</span><span class="sxs-lookup"><span data-stu-id="692ce-109">Office Message Encryption (OME).</span></span>
    
- <span data-ttu-id="692ce-110">安全多用途網際網路郵件延伸 (S/MIME)。</span><span class="sxs-lookup"><span data-stu-id="692ce-110">Secure/Multipurpose Internet Mail Extensions (S/MIME).</span></span>
    
- <span data-ttu-id="692ce-111">資訊版權管理 (IRM)。</span><span class="sxs-lookup"><span data-stu-id="692ce-111">Information Rights Management (IRM).</span></span>
    
## <a name="what-is-email-encryption-and-how-does-office-365-use-it"></a><span data-ttu-id="692ce-112">什麼是電子郵件加密？Office 365 如何使用它？</span><span class="sxs-lookup"><span data-stu-id="692ce-112">What is email encryption and how does Office 365 use it?</span></span>

<span data-ttu-id="692ce-p102">加密是資訊的編碼僅授權的收件者可以解碼和取用資訊的程序。Office 365 使用加密兩種方式： 在服務] 並當做客戶控制項。在服務] 中加密預設會使用在 Office 365;您不需要設定的任何項目。例如，Office 365 使用傳輸層安全性 (TLS) 來加密的連線或兩部伺服器之間工作階段。</span><span class="sxs-lookup"><span data-stu-id="692ce-p102">Encryption is the process by which information is encoded so that only an authorized recipient can decode and consume the information. Office 365 uses encryption in two ways: in the service, and as a customer control. In the service, encryption is used in Office 365 by default; you don't have to configure anything. For example, Office 365 uses Transport Layer Security (TLS) to encrypt the connection, or session, between two servers.</span></span> 
  
<span data-ttu-id="692ce-117">以下是電子郵件加密通常的運作方式：</span><span class="sxs-lookup"><span data-stu-id="692ce-117">Here's how email encryption typically works:</span></span>
  
- <span data-ttu-id="692ce-118">加密，或當郵件傳送過程中將無法讀取加密文字、 寄件者的電腦上或是由中央伺服器轉換純文字郵件時。</span><span class="sxs-lookup"><span data-stu-id="692ce-118">A message is encrypted, or transformed from plain text into unreadable ciphertext, either on the sender's machine, or by a central server while the message is in transit.</span></span>
    
- <span data-ttu-id="692ce-119">為傳送過程中以防止以防攔截郵件所讀取時郵件仍會保留在加密文字。</span><span class="sxs-lookup"><span data-stu-id="692ce-119">The message remains in ciphertext while it's in transit in order to protect it from being read in case the message is intercepted.</span></span>
    
- <span data-ttu-id="692ce-120">一旦收件者收到郵件時，會以下列兩種方式之一將郵件轉換回可閱讀的純文字：</span><span class="sxs-lookup"><span data-stu-id="692ce-120">Once the message is received by the recipient, the message is transformed back into readable plain text in one of two ways:</span></span>
    
  - <span data-ttu-id="692ce-121">收件者的電腦會使用金鑰解密郵件，或</span><span class="sxs-lookup"><span data-stu-id="692ce-121">The recipient's machine uses a key to decrypt the message, or</span></span>
    
  - <span data-ttu-id="692ce-122">中央伺服器解密的郵件收件者，代表後驗證收件者的身分識別。</span><span class="sxs-lookup"><span data-stu-id="692ce-122">A central server decrypts the message on behalf of the recipient, after validating the recipient's identity.</span></span>
    
<span data-ttu-id="692ce-123">如需有關 Office 365 保護伺服器之間的通訊的安全的詳細資訊，例如組織內 Office 365 或 Office 365 與 Office 365 外部信任的業務合作夥伴之間[如何 Exchange Online，請參閱使用 TLS 安全的電子郵件在 Office 365 的連線](exchange-online-uses-tls-to-secure-email-connections.md)。</span><span class="sxs-lookup"><span data-stu-id="692ce-123">For more information on how Office 365 secures communication between servers, such as between organizations within Office 365 or between Office 365 and a trusted business partner outside of Office 365, see [How Exchange Online uses TLS to secure email connections in Office 365](exchange-online-uses-tls-to-secure-email-connections.md).</span></span>
  
<span data-ttu-id="692ce-124">請觀看此影片簡介[Office 365 中的加密](https://www.youtube.com/watch?v=KmfxCd5ublI)。</span><span class="sxs-lookup"><span data-stu-id="692ce-124">Watch this video for an introduction to [Encryption in Office 365](https://www.youtube.com/watch?v=KmfxCd5ublI).</span></span>
  
## <a name="comparing-email-encryption-options-available-in-office-365"></a><span data-ttu-id="692ce-125">比較 Office 365 中提供的電子郵件加密選項</span><span class="sxs-lookup"><span data-stu-id="692ce-125">Comparing email encryption options available in Office 365</span></span>

||![OME 的說明概念圖](media/2bf27b5e-bbb3-46d1-95bf-884dc27a746c.png)|![IRM 的說明概念圖](media/9c0cc444-9448-40c6-b244-8fcc593a64e0.png)|![SMIME 的說明概念圖](media/ae4613a8-c17e-47e1-8e13-12e891e43744.png)|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="692ce-129">這是什麼？</span><span class="sxs-lookup"><span data-stu-id="692ce-129">What is it?</span></span>|<span data-ttu-id="692ce-p103">Office 365 郵件加密 (OME) 是內建於 Azure 版權管理 (Azure RMS) 的服務，可讓您將加密的電子郵件傳送給組織內部或外部的人，無論目的地電子郵件地址為何 (Gmail、Yahoo! Mail、Outlook.com 等)。</span><span class="sxs-lookup"><span data-stu-id="692ce-p103">Office 365 Message Encryption (OME) is a service built on Azure Rights Management (Azure RMS) that lets you send encrypted email to people inside or outside your organization, regardless of the destination email address (Gmail, Yahoo! Mail, Outlook.com, etc.).</span></span>  <br/> <span data-ttu-id="692ce-p104">身為管理員，您可以設定用以定義加密條件的傳輸規則。當使用者傳送符合規則的郵件時，會自動套用加密。</span><span class="sxs-lookup"><span data-stu-id="692ce-p104">As an admin, you can set up transport rules that define the conditions for encryption. When a user sends a message that matches a rule, encryption is applied automatically.</span></span>  <br/> <span data-ttu-id="692ce-p105">若要檢視加密的郵件，收件者可以取得單次密碼、 登入 Microsoft 帳戶或登入工作或學校與 Office 365 相關聯的帳戶。收件者也可以傳送加密的回覆。它們不需要檢視加密的郵件或傳送回覆加密的 Office 365 訂閱。</span><span class="sxs-lookup"><span data-stu-id="692ce-p105">To view encrypted messages, recipients can either get a one-time passcode, sign in with a Microsoft account, or sign in with a work or school account associated with Office 365. Recipients can also send encrypted replies. They don't need an Office 365 subscription to view encrypted messages or send encrypted replies.</span></span>|<span data-ttu-id="692ce-p106">IRM 是加密解決方案，也可對電子郵件套用使用限制。這有助於防止敏感資訊被未經授權的人員列印、轉寄或複製。</span><span class="sxs-lookup"><span data-stu-id="692ce-p106">IRM is an encryption solution that also applies usage restrictions to email messages. It helps prevent sensitive information from being printed, forwarded, or copied by unauthorized people.</span></span>  <br/> <span data-ttu-id="692ce-139">Office 365 中的 IRM 功能使用 Azure 版權管理 (Azure RMS)。 
</span><span class="sxs-lookup"><span data-stu-id="692ce-139">IRM capabilities in Office 365 use Azure Rights Management (Azure RMS).</span></span>|<span data-ttu-id="692ce-p107">S/MIME 是一種憑證型加密解決方案可讓您加密及數位簽署的訊息。訊息加密有助於確保只有預定的收件者可以開啟及讀取郵件。數位簽章可協助收件者驗證寄件者的身分識別。</span><span class="sxs-lookup"><span data-stu-id="692ce-p107">S/MIME is a certificate-based encryption solution that allows you to both encrypt and digitally sign a message. The message encryption helps ensure that only the intended recipient can open and read the message. A digital signature helps the recipient validate the identity of the sender.</span></span>  <br/> <span data-ttu-id="692ce-143">數位簽章和郵件加密之所以可行，皆因為使用了唯一數位憑證，此憑證包含用於驗證數位簽章及加密或解密郵件的金鑰。</span><span class="sxs-lookup"><span data-stu-id="692ce-143">Both digital signatures and message encryption are made possible through the use of unique digital certificates that contain the keys for verifying digital signatures and encrypting or decrypting messages.</span></span>  <br/> <span data-ttu-id="692ce-p108">若要使用 S/MIME，您必須公用金鑰檔案上每個收件者。收件者必須維持必須保持安全自己私人機碼。如果收件者的私密金鑰遭到洩漏，收件者必須以取得新的私密金鑰和轉散佈給所有可能的寄件者的公開金鑰。</span><span class="sxs-lookup"><span data-stu-id="692ce-p108">To use S/MIME, you must have public keys on file for each recipient. Recipients have to maintain their own private keys, which must remain secure. If a recipient's private keys are compromised, the recipient needs to get a new private key and redistribute public keys to all potential senders.</span></span>|
|<span data-ttu-id="692ce-147">能做什麼？</span><span class="sxs-lookup"><span data-stu-id="692ce-147">What does it do?</span></span>|<span data-ttu-id="692ce-148">OME：</span><span class="sxs-lookup"><span data-stu-id="692ce-148">OME:</span></span>  <br/>  <span data-ttu-id="692ce-149">將傳送給內部或外部收件者的郵件加密。</span><span class="sxs-lookup"><span data-stu-id="692ce-149">Encrypts messages sent to internal or external recipients.</span></span>  <br/>  <span data-ttu-id="692ce-p109">可讓使用者將加密的郵件傳送至任何電子郵件地址，包括 Outlook.com、Yahoo!Mail 和 Gmail。</span><span class="sxs-lookup"><span data-stu-id="692ce-p109">Allows users to send encrypted messages to any email address, including Outlook.com, Yahoo! Mail, and Gmail.</span></span>  <br/>  <span data-ttu-id="692ce-152">可讓您，以系統管理員，以自訂檢視入口網站以反映您的組織品牌的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="692ce-152">Allows you, as an admin, to customize the email viewing portal to reflect your organization's brand.</span></span>  <br/>  <span data-ttu-id="692ce-153">Microsoft 安全地管理並儲存機碼，因此您不需要。</span><span class="sxs-lookup"><span data-stu-id="692ce-153">Microsoft securely manages and stores the keys, so you don't have to.</span></span>  <br/>  <span data-ttu-id="692ce-154">只要可以在瀏覽器中開啟加密的郵件 (以 HTML 附件傳送)，就不需要任何特殊的用戶端軟體。</span><span class="sxs-lookup"><span data-stu-id="692ce-154">No special client side software is needed as long as the encrypted message (sent as an HTML attachment) can be opened in a browser.</span></span>|<span data-ttu-id="692ce-155">IRM：</span><span class="sxs-lookup"><span data-stu-id="692ce-155">IRM:</span></span>  <br/>  <span data-ttu-id="692ce-156">利用加密和使用限制為電子郵件和附件提供線上和離線保護。</span><span class="sxs-lookup"><span data-stu-id="692ce-156">Uses encryption and usage restrictions to provide online and offline protection for email messages and attachments.</span></span>  <br/>  <span data-ttu-id="692ce-157">可讓身為管理員的您能夠設定傳輸規則或 Outlook 保護規則，以自動將 IRM 套用至選取的郵件。</span><span class="sxs-lookup"><span data-stu-id="692ce-157">Gives you, as an admin, the ability to set up transport rules or Outlook protection rules to automatically apply IRM to select messages.</span></span>  <br/>  <span data-ttu-id="692ce-158">可讓使用者手動套用 Outlook 或 Outlook web （前身為 Outlook Web App） 上的範本。</span><span class="sxs-lookup"><span data-stu-id="692ce-158">Lets users manually apply templates in Outlook or Outlook on the web (formerly known as Outlook Web App).</span></span>|<span data-ttu-id="692ce-159">S/MIME 以數位簽章解決寄件者驗證，以加密解決郵件機密性。</span><span class="sxs-lookup"><span data-stu-id="692ce-159">S/MIME addresses sender authentication with digital signatures, and message confidentiality with encryption.</span></span>|
|<span data-ttu-id="692ce-160">不能做什麼？</span><span class="sxs-lookup"><span data-stu-id="692ce-160">What does it not do?</span></span>|<span data-ttu-id="692ce-p110">OME 不會讓您將流量限制套用至郵件。例如，您無法使用它來停止轉寄或列印加密的郵件的收件者。</span><span class="sxs-lookup"><span data-stu-id="692ce-p110">OME doesn't let you apply usage restrictions to messages. For example, you can't use it to stop a recipient from forwarding or printing an encrypted message.</span></span>|<span data-ttu-id="692ce-p111">某些應用程式可能無法支援 IRM 電子郵件的所有裝置上。如需這些結構元件及其他產品支援 IRM 電子郵件的詳細資訊，請參閱[用戶端裝置功能](https://technet.microsoft.com/library/dn655136.aspx#BKMK_ClientCapabilities)。</span><span class="sxs-lookup"><span data-stu-id="692ce-p111">Some applications may not support IRM emails on all devices. For more information about these and other products that support IRM email, see [Client device capabilities](https://technet.microsoft.com/library/dn655136.aspx#BKMK_ClientCapabilities).</span></span>|<span data-ttu-id="692ce-165">S/MIME 不允許惡意程式碼、 垃圾郵件或原則掃描加密的郵件。</span><span class="sxs-lookup"><span data-stu-id="692ce-165">S/MIME doesn't allow encrypted messages to be scanned for malware, spam, or policies.</span></span>|
|<span data-ttu-id="692ce-166">建議和範例案例</span><span class="sxs-lookup"><span data-stu-id="692ce-166">Recommendations and example scenarios</span></span>|<span data-ttu-id="692ce-p112">我們建議使用 OME 當您想要將機密的商務資訊傳送至您的組織外部人員不論是消費者或其他企業版。例如：</span><span class="sxs-lookup"><span data-stu-id="692ce-p112">We recommend using OME when you want to send sensitive business information to people outside your organization, whether they're consumers or other businesses. For example:</span></span>  <br/>  <span data-ttu-id="692ce-169">銀行員工將信用卡帳單傳送給客戶</span><span class="sxs-lookup"><span data-stu-id="692ce-169">A bank employee sending credit card statements to customers</span></span>  <br/>  <span data-ttu-id="692ce-170">將醫療記錄傳送給病患府 office</span><span class="sxs-lookup"><span data-stu-id="692ce-170">A doctor's office sending medical records to a patient</span></span>  <br/>  <span data-ttu-id="692ce-171">律師將機密的法律資訊傳送給其他律師</span><span class="sxs-lookup"><span data-stu-id="692ce-171">An attorney sending confidential legal information to another attorney</span></span>|<span data-ttu-id="692ce-p113">當您想要套用使用限制以及加密時，我們建議使用 IRM。例如：</span><span class="sxs-lookup"><span data-stu-id="692ce-p113">We recommend using IRM when you want to apply usage restrictions as well as encryption. For example:</span></span>  <br/>  <span data-ttu-id="692ce-174">將機密的詳細資訊傳送至其小組需一項新產品經理適用於"不要轉寄 」] 選項。</span><span class="sxs-lookup"><span data-stu-id="692ce-174">A manager sending confidential details to her team about a new product applies the "Do Not Forward" option.</span></span>  <br/>  <span data-ttu-id="692ce-175">行政人員需要與其他公司共用投標提案，其中一個附件是由使用 Office 365 的夥伴提供，電子郵件和附件皆需要受到保護。</span><span class="sxs-lookup"><span data-stu-id="692ce-175">An executive needs to share a bid proposal with another company, which includes an attachment from a partner who is using Office 365, and require both the email and the attachment to be protected.</span></span>|<span data-ttu-id="692ce-176">我們建議使用 S/MIME 組織或收件者的組織需要則為 true 的對等加密時發生。</span><span class="sxs-lookup"><span data-stu-id="692ce-176">We recommend using S/MIME when either your organization or the recipient's organization requires true peer-to-peer encryption.</span></span>  <br/>  <span data-ttu-id="692ce-177">S/MIME 最常用於下列情況：</span><span class="sxs-lookup"><span data-stu-id="692ce-177">S/MIME is most commonly used in the following scenarios:</span></span>  <br/>  <span data-ttu-id="692ce-178">政府機構與其他政府機關通訊</span><span class="sxs-lookup"><span data-stu-id="692ce-178">Government agencies communicating with other government agencies</span></span>  <br/>  <span data-ttu-id="692ce-179">企業與政府機構通訊</span><span class="sxs-lookup"><span data-stu-id="692ce-179">A business communicating with a government agency</span></span>|
   
## <a name="what-encryption-options-are-available-for-my-office-365-subscription"></a><span data-ttu-id="692ce-180">我的 Office 365 訂閱有哪些加密選項？</span><span class="sxs-lookup"><span data-stu-id="692ce-180">What encryption options are available for my Office 365 subscription?</span></span>

<span data-ttu-id="692ce-p114">如需 Office 365 郵件加密選項訂閱請參閱[Exchange Online 服務說明](https://technet.microsoft.com/en-us/library/exchange-online-service-description.aspx)。這裡，您可以找到下列加密功能的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="692ce-p114">For information about email encryption options for your Office 365 subscription see the [Exchange Online service description](https://technet.microsoft.com/en-us/library/exchange-online-service-description.aspx). Here, you can find information about the following encryption features:</span></span>
  
- <span data-ttu-id="692ce-183">Azure RMS，包括 IRM 功能和 OME</span><span class="sxs-lookup"><span data-stu-id="692ce-183">Azure RMS, including both IRM capabilities and OME</span></span>
    
- <span data-ttu-id="692ce-184">S/MIME</span><span class="sxs-lookup"><span data-stu-id="692ce-184">S/MIME</span></span>
    
- <span data-ttu-id="692ce-185">TLS</span><span class="sxs-lookup"><span data-stu-id="692ce-185">TLS</span></span>
    
- <span data-ttu-id="692ce-186">靜態資料的加密 (透過 BitLocker)</span><span class="sxs-lookup"><span data-stu-id="692ce-186">Encryption of data at rest (through BitLocker)</span></span>
    
## <a name="what-about-encryption-for-data-at-rest"></a><span data-ttu-id="692ce-187">靜態資料的加密呢？</span><span class="sxs-lookup"><span data-stu-id="692ce-187">What about encryption for data at rest?</span></span>

<span data-ttu-id="692ce-p115">「 靜態資料 」 指的是不是主動傳輸的資料。Office 365 中靜態電子郵件資料是使用 BitLocker 磁碟加密來加密。BitLocker 加密 Office 365 提供增強型的理想的未經授權存取的資料中心的硬碟。若要深入了解，請參閱[BitLocker 概觀 （英文）](https://go.microsoft.com/fwlink/p/?LinkId=394737)。</span><span class="sxs-lookup"><span data-stu-id="692ce-p115">"Data at rest" refers to data that isn't actively in transit. In Office 365, email data at rest is encrypted using BitLocker Drive Encryption. BitLocker encrypts the hard drives in Office 365 datacenters to provide enhanced protection against unauthorized access. To learn more, see [BitLocker Overview](https://go.microsoft.com/fwlink/p/?LinkId=394737).</span></span>
  
## <a name="more-information-about-email-encryption-options-in-office-365"></a><span data-ttu-id="692ce-192">Office 365 中的電子郵件加密選項的相關資訊</span><span class="sxs-lookup"><span data-stu-id="692ce-192">More information about email encryption options in Office 365</span></span>

<span data-ttu-id="692ce-193">如需本文中電子郵件加密選項以及 TLS 的詳細資訊，請參閱這些文件：</span><span class="sxs-lookup"><span data-stu-id="692ce-193">For more information about the email encryption options in this article as well as TLS, see these articles:</span></span>
  
 <span data-ttu-id="692ce-194">**OME**</span><span class="sxs-lookup"><span data-stu-id="692ce-194">**OME**</span></span>
  
[<span data-ttu-id="692ce-195">Office 365 郵件加密 (OME)</span><span class="sxs-lookup"><span data-stu-id="692ce-195">Office 365 Message Encryption (OME)</span></span>](ome.md)
  
 <span data-ttu-id="692ce-196">**IRM**</span><span class="sxs-lookup"><span data-stu-id="692ce-196">**IRM**</span></span>
  
[<span data-ttu-id="692ce-197">Exchange Online 中的資訊版權管理</span><span class="sxs-lookup"><span data-stu-id="692ce-197">Information Rights Management in Exchange Online</span></span>](https://technet.microsoft.com/en-us/library/jj983436%28v=exchg.150%29.aspx)
  
[<span data-ttu-id="692ce-198">Azure 版權管理新功能</span><span class="sxs-lookup"><span data-stu-id="692ce-198">What is Azure Rights Management?</span></span>](https://technet.microsoft.com/library/jj585026)
  
 <span data-ttu-id="692ce-199">**S/MIME**</span><span class="sxs-lookup"><span data-stu-id="692ce-199">**S/MIME**</span></span>
  
[<span data-ttu-id="692ce-200">可用於訊息簽署和加密的 S/MIME</span><span class="sxs-lookup"><span data-stu-id="692ce-200">S/MIME for message signing and encryption</span></span>](https://technet.microsoft.com/library/dn626158)
  
[<span data-ttu-id="692ce-201">了解 S/MIME</span><span class="sxs-lookup"><span data-stu-id="692ce-201">Understanding S/MIME</span></span>](https://technet.microsoft.com/library/aa995740%28v=exchg.65%29.aspx)
  
[<span data-ttu-id="692ce-202">了解公用密碼編譯</span><span class="sxs-lookup"><span data-stu-id="692ce-202">Understanding Public Key Cryptography</span></span>](https://technet.microsoft.com/library/aa998077%28v=exchg.65%29.aspx)
  
 <span data-ttu-id="692ce-203">**TLS**</span><span class="sxs-lookup"><span data-stu-id="692ce-203">**TLS**</span></span>
  
[<span data-ttu-id="692ce-204">Office 365 中使用連接器來設定自訂郵件流程</span><span class="sxs-lookup"><span data-stu-id="692ce-204">Configure custom mail flow by using connectors in Office 365</span></span>](https://technet.microsoft.com/en-us/library/jj723138%28v=exchg.150%29.aspx)
  

