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
search.appverid:
- MET150
ms.assetid: 887c710b-0ec6-4ff0-8065-5f05f74afef3
description: S/MIME 可讓您加密電子郵件與數位簽章它們。當您使用 S/MIME 與電子郵件訊息時，它可協助的人員接收該訊息是特定看到其收件匣中是完全入門寄件者的郵件。
ms.openlocfilehash: 26c50fb6e4d1b07b7dba26948ae46e7f36eeaec5
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002762"
---
# <a name="smime-for-message-signing-and-encryption"></a><span data-ttu-id="b45f3-104">為郵件簽章和加密的 S/MIME</span><span class="sxs-lookup"><span data-stu-id="b45f3-104">S/MIME for message signing and encryption</span></span>

<span data-ttu-id="b45f3-p102">S/MIME (安全多用途網際網路郵件延伸) 是一種被廣為接受的方法，更具體來說是通訊協定，可用來傳送已數位簽署和加密的郵件。S/MIME 可讓您將電子郵件加密和進行數位簽署。對電子郵件使用 S/MIME 時，可讓收件者確定收件匣裡的郵件確實為寄件者所寄出。也可讓收件者確定郵件來自特定的寄件者，而不是由其他人假冒寄件者。為了達到此目的，S/MIME 提供密碼編譯的安全性服務，例如驗證、訊息完整性和來源不可否認性 (使用數位簽章)。另外還可加強電子郵件通訊的隱私性和資料安全性 (使用加密)。如需 S/MIME 在電子郵件方面的歷史和架構的完整背景資訊，請參閱＜[瞭解 S/MIME](https://go.microsoft.com/fwlink/?LinkID=393948)＞。</span><span class="sxs-lookup"><span data-stu-id="b45f3-p102">S/MIME (Secure/Multipurpose Internet Mail Extensions) is a widely accepted method, or more precisely a protocol, for sending digitally signed and encrypted messages. S/MIME allows you to encrypt emails and digitally sign them. When you use S/MIME with an email message, it helps the people who receive that message to be certain that what they see in their inbox is the exact message that started with the sender. It will also help people who receive messages to be certain that the message came from the specific sender and not from someone pretending to be the sender. To do this, S/MIME provides for cryptographic security services such as authentication, message integrity, and non-repudiation of origin (using digital signatures). It also helps enhance privacy and data security (using encryption) for electronic messaging. For a more complete background about the history and architecture of S/MIME in the context of email, see [Understanding S/MIME](https://go.microsoft.com/fwlink/?LinkID=393948).</span></span> 
  
<span data-ttu-id="b45f3-p103">身為系統管理員，如果您管理的信箱在 Exchange 2013 SP1 或 Exchange Online (Office 365 的一部分) 中，您可以在組織中啟用 S/MIME 安全性。請使用 Exchange 管理命令介面並參考以下各連結主題的指引來設定 S/MIME。不論是 Exchange 2013 SP1 或 Exchange Online，若要在支援的 Outlook 或 ActiveSync 版本中使用 S/MIME，組織中的使用者必須有針對簽署和加密用途所發出的憑證，以及發佈至內部部署 Active Directory 網域服務 (AD DS) 的資料。AD DS 必須位於您可掌控的實際位置上的電腦，而不是在遠端設備或網際網路某處的雲端式服務上。如需 AD DS 的詳細資訊，請參閱＜[Active Directory 網域服務](https://go.microsoft.com/fwlink/?LinkID=394064)＞。</span><span class="sxs-lookup"><span data-stu-id="b45f3-p103">As an administrator, you can enable S/MIME-based security for your organization if you have mailboxes in either Exchange 2013 SP1 or Exchange Online, a part of Office 365. Use the guidance in the topics linked here along with the Exchange Management Shell to set up S/MIME. To use S/MIME in supported versions of Outlook or ActiveSync, with either Exchange 2013 SP1 or Exchange Online, the users in your organization must have certificates issued for signing and encryption purposes and data published to your on-premises Active Directory Domain Service (AD DS). Your AD DS must be located on computers at a physical location that you control and not at a remote facility or cloud-based service somewhere on the internet. For more information about AD DS, see [Active Directory Domain Services](https://go.microsoft.com/fwlink/?LinkID=394064).</span></span>
  
## <a name="supported-scenarios-and-technical-considerations"></a><span data-ttu-id="b45f3-117">支援的案例和技術考量</span><span class="sxs-lookup"><span data-stu-id="b45f3-117">Supported scenarios and technical considerations</span></span>
<span data-ttu-id="b45f3-118"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="b45f3-118"></span></span>

<span data-ttu-id="b45f3-119">如果組織使用 Exchange 2013 SP1 或 Exchange Online，您可以設定 S/MIME 供下列任何端點使用：</span><span class="sxs-lookup"><span data-stu-id="b45f3-119">If your organization uses either Exchange 2013 SP1 or Exchange Online, you can set up S/MIME to work with any of the following end points:</span></span> 
  
- <span data-ttu-id="b45f3-120">Outlook 2010</span><span class="sxs-lookup"><span data-stu-id="b45f3-120">Outlook 2010</span></span>
    
- <span data-ttu-id="b45f3-121">Outlook 2013</span><span class="sxs-lookup"><span data-stu-id="b45f3-121">Outlook 2013</span></span>
    
- <span data-ttu-id="b45f3-122">Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="b45f3-122">Outlook Web App</span></span>
    
- <span data-ttu-id="b45f3-123">Exchange ActiveSync (EAS)</span><span class="sxs-lookup"><span data-stu-id="b45f3-123">Exchange ActiveSync (EAS)</span></span>
    
<span data-ttu-id="b45f3-p104">對每個端點設定 S/MIME 時所採取的步驟，視您選擇何者而稍有不同。通常需要完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="b45f3-p104">The steps that you follow to set up S/MIME with each of these end points is slightly different depending on which you choose. Generally, you will need to accomplish the following:</span></span>
  
- <span data-ttu-id="b45f3-p105">安裝以 Windows 為基礎的憑證授權單位，並且設定公開金鑰基礎結構，來核發 S/MIME 憑證。也支援協力廠商憑證提供者所發出的憑證。如需詳細資訊，請參閱 [Active Directory 憑證服務概觀](https://technet.microsoft.com/library/hh831740.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b45f3-p105">Install a Windows-based Certification Authority and set up a public key infrastructure to issue S/MIME certificates. Certificates issued by third-party certificate providers are also supported. For details, see [Active Directory Certificate Services Overview](https://technet.microsoft.com/library/hh831740.aspx).</span></span>
    
- <span data-ttu-id="b45f3-129">在內部部署 AD DS 帳戶的 UserSMIMECertificate 和/或 UserCertificate 屬性中發佈使用者憑證。</span><span class="sxs-lookup"><span data-stu-id="b45f3-129">Publish the user certificate in an on-premises AD DS account in the UserSMIMECertificate and/or UserCertificate attributes.</span></span>
    
- <span data-ttu-id="b45f3-p106">在 Exchange Online 組織中，使用適當的 DirSync 版本，將使用者憑證從 AD DS 同步至 Azure Active Directory。這些憑證會從 Azure Active Directory 同步至 Exchange Online 目錄，並於加密寄給收件者的郵件時使用。</span><span class="sxs-lookup"><span data-stu-id="b45f3-p106">For Exchange Online organizations, synchronize the user certificates from AD DS to Azure Active Directory by using an appropriate version of DirSync. These certificates will then get synchronized from Azure Active Directory to Exchange Online directory and will be used when encrypting a message to a recipient.</span></span>
    
- <span data-ttu-id="b45f3-p107">設定虛擬憑證集合以驗證 S/MIME。OWA 會使用此資訊來驗證電子郵件的簽章，以確保電子郵件是以信任的憑證所簽署。</span><span class="sxs-lookup"><span data-stu-id="b45f3-p107">Set up a virtual certificate collection in order to validate S/MIME. This information is used by OWA when validating the signature of an email and ensuring that it was signed by a trusted certificate.</span></span>
    
- <span data-ttu-id="b45f3-134">設定 Outlook 或 EAS 端點來使用 S/MIME。</span><span class="sxs-lookup"><span data-stu-id="b45f3-134">Set up the Outlook or EAS end point to use S/MIME.</span></span> 
    
## <a name="setup-smime-with-outlook-web-app"></a><span data-ttu-id="b45f3-135">設定 Outlook Web App 的 S/MIME</span><span class="sxs-lookup"><span data-stu-id="b45f3-135">Setup S/MIME with Outlook Web App</span></span>
<span data-ttu-id="b45f3-136"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="b45f3-136"></span></span>

<span data-ttu-id="b45f3-137">設定 Exchange 2013 SP1 或 Exchange Online 的 Outlook Web App 來使用 S/MIME 包含下列幾個主要步驟：</span><span class="sxs-lookup"><span data-stu-id="b45f3-137">Setting up S/MIME for Exchange 2013 SP1 or Exchange Online with Outlook Web App involves the following key steps:</span></span>
  
1. [<span data-ttu-id="b45f3-138">設定 Outlook Web App 的 S/MIME 設定</span><span class="sxs-lookup"><span data-stu-id="b45f3-138">Configure S/MIME settings for Outlook Web App</span></span>](configure-s-mime-settings-for-outlook-web-app.md)
    
2. [<span data-ttu-id="b45f3-139">設定虛擬憑證集合以驗證 S/MIME</span><span class="sxs-lookup"><span data-stu-id="b45f3-139">Set up virtual certificate collection to validate S/MIME</span></span>](set-up-virtual-certificate-collection-to-validate-s-mime.md)
    
3. <span data-ttu-id="b45f3-140">[將使用者憑證同步至 Office 365 進行 S/MIME](sync-user-certificates-to-office-365-for-s-mime.md)此步驟僅適用於 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="b45f3-140">[Sync user certificates to Office 365 for S/MIME](sync-user-certificates-to-office-365-for-s-mime.md) This step applies to Exchange Online only.</span></span> 
    
## <a name="related-message-encryption-technologies"></a><span data-ttu-id="b45f3-141">相關郵件加密技術</span><span class="sxs-lookup"><span data-stu-id="b45f3-141">Related message encryption technologies</span></span>
<span data-ttu-id="b45f3-142"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="b45f3-142"></span></span>

<span data-ttu-id="b45f3-p108">郵件安全性已變得越來越重要，因此系統管理員必須了解安全郵件的原則和概念。由於有越來越多各式各樣的防護技術 (例如 S/MIME) 問世，所以了解這一方面的資訊再重要不過。若要深入了解 S/MIME 及其於電子郵件上的運作，請參閱＜[瞭解 S/MIME](https://go.microsoft.com/fwlink/?LinkID=393948)＞。各種加密技術可搭配運作，以為靜止和傳輸中的郵件提供保護。S/MIME 可以與下列技術同時運作，但彼此並不具依存關係：</span><span class="sxs-lookup"><span data-stu-id="b45f3-p108">As message security becomes more important, administrators need to understand the principles and concepts of secure messaging. This understanding is especially important because of the growing variety of protection-related technologies, such as S/MIME, that have become available. To understand more about S/MIME and how it works in context of email, see [Understanding S/MIME](https://go.microsoft.com/fwlink/?LinkID=393948). A variety of encryption technologies work together to provide protection for messages at rest and in-transit. S/MIME can work simultaneously with the following technologies but is not dependent on them:</span></span>
  
> <span data-ttu-id="b45f3-148">**傳輸層安全性 (TLS)** 會加密電子郵件伺服器之間的通道或路由，以協助防止側錄和竊聽。</span><span class="sxs-lookup"><span data-stu-id="b45f3-148">**Transport Layer Security (TLS)** encrypts the tunnel or the route between email servers in order to help prevent snooping and eavesdropping.</span></span> 
    
> <span data-ttu-id="b45f3-149">**安全通訊端層 (SSL)** 會加密電子郵件用戶端與 Office 365 伺服器之間的連線。</span><span class="sxs-lookup"><span data-stu-id="b45f3-149">**Secure Sockets Layer (SSL)** encrypts the connection between email clients and Office 365 servers.</span></span> 
    
> <span data-ttu-id="b45f3-150">**BitLocker** 會加密資料中心硬碟上的資料，因此如果有人未獲授權就存取，便無法讀取資料。</span><span class="sxs-lookup"><span data-stu-id="b45f3-150">**BitLocker** encrypts the data on a hard drive in a datacenter so that if someone gets unauthorized access, they can't read it.</span></span> 
    
### <a name="smime-compared-with-office-365-message-encryption"></a><span data-ttu-id="b45f3-151">S/MIME 與 Office 365 郵件加密的比較</span><span class="sxs-lookup"><span data-stu-id="b45f3-151">S/MIME compared with Office 365 Message Encryption</span></span>

<span data-ttu-id="b45f3-p109">S/MIME 需要憑證和發佈基礎結構 (常用於企業對企業及企業對消費者情況)。在 S/MIME 中，由使用者控制密碼編譯金鑰，且在他們所傳送的每一封郵件上，都可選擇是否使用金鑰。電子郵件程式 (例如 Outlook) 會搜尋受信任的根憑證授單位，以進行數位簽署並驗證簽章。Office 365 郵件加密是系統管理員 (而不是個別使用者) 可設定的原則型加密服務，可將傳送給組織內外任何人的郵件加密。它是以 Azure 版權管理 (RMS) 為基礎的線上服務，且不依賴任何公開金鑰基礎結構。Office 365 郵件加密還提供其他功能，例如以組織的品牌來自訂郵件。如需 Office 365 郵件加密的相關資訊，請參閱 [Office 365 郵件加密](https://go.microsoft.com/fwlink/?LinkID=392525)。</span><span class="sxs-lookup"><span data-stu-id="b45f3-p109">S/MIME requires a certificate and publishing infrastructure that is often used in business-to-business and business-to-consumer situations. The user controls the cryptographic keys in S/MIME and can choose whether to use them for each message they send. Email programs such as Outlook search a trusted root certificate authority location to perform digital signing and verification of the signature. Office 365 Message Encryption is a policy-based encryption service that can be configured by an administrator, and not an individual user, to encrypt mail sent to anyone inside or outside of the organization. It's an online service that's built on Azure Rights Management (RMS) and does not rely on a public key infrastructure. Office 365 Message Encryption also provides additional capabilities, such as the capability to customize the mail with organization's brand. For more information about Office 365 Message Encryption, see [Office 365 Message Encryption](https://go.microsoft.com/fwlink/?LinkID=392525).</span></span>
  
## <a name="more-information"></a><span data-ttu-id="b45f3-159">其他資訊</span><span class="sxs-lookup"><span data-stu-id="b45f3-159">More information</span></span>
<span data-ttu-id="b45f3-160"><a name="sectionSection3"> </a></span><span class="sxs-lookup"><span data-stu-id="b45f3-160"></span></span>

[<span data-ttu-id="b45f3-161">Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="b45f3-161">Outlook Web App</span></span>](http://technet.microsoft.com/library/3814b665-01e8-4881-9a44-163f14789ee4.aspx)
  
[<span data-ttu-id="b45f3-162">安全郵件 (2000)</span><span class="sxs-lookup"><span data-stu-id="b45f3-162">Secure Mail (2000)</span></span>](https://technet.microsoft.com/en-us/library/cc962043.aspx)
  

