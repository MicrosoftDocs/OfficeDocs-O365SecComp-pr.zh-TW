---
title: S/MIME 郵件簽章與 Exchange Online 中的加密
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 887c710b-0ec6-4ff0-8065-5f05f74afef3
description: 系統管理員可了解 Exchange Online 中使用 S/MIME。
ms.openlocfilehash: 163ae5686adf934f07ee26717fa0b4998ddf3363
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296796"
---
# <a name="smime-for-message-signing-and-encryption-in-exchange-online"></a><span data-ttu-id="f6007-103">S/MIME 郵件簽章與 Exchange Online 中的加密</span><span class="sxs-lookup"><span data-stu-id="f6007-103">S/MIME for message signing and encryption in Exchange Online</span></span>

<span data-ttu-id="f6007-p101">S/MIME （安全/多用途網際網路郵件延伸） 是廣泛可接受的方法 （或更精確的通訊協定） 傳送以數位方式簽署和已加密郵件。S/MIME 可讓您加密電子郵件與數位簽章它們。當您使用 S/MIME 與電子郵件訊息時，它可協助的人員接收該訊息是特定看到其收件匣中是完全入門寄件者的郵件。它也可隨附郵件來自特定寄件者而不寄件者假冒他人協助接收設為特定訊息的人員。若要這樣做，S/MIME 提供密碼編譯安全性服務如驗證、 訊息完整性及不可否認性的 （使用數位簽章） 的原點而言。它也可協助提升隱私權與 （使用加密） 的資料安全性的電子郵件。如需歷程記錄和架構的 S/MIME 郵件的內容中的更完整背景，請參閱[了解 S/MIME](https://go.microsoft.com/fwlink/?LinkID=393948)。</span><span class="sxs-lookup"><span data-stu-id="f6007-p101">S/MIME (Secure/Multipurpose Internet Mail Extensions) is a widely accepted method (or more precisely, a protocol) for sending digitally signed and encrypted messages. S/MIME allows you to encrypt emails and digitally sign them. When you use S/MIME with an email message, it helps the people who receive that message to be certain that what they see in their inbox is the exact message that started with the sender. It will also help people who receive messages to be certain that the message came from the specific sender and not from someone pretending to be the sender. To do this, S/MIME provides for cryptographic security services such as authentication, message integrity, and non-repudiation of origin (using digital signatures). It also helps enhance privacy and data security (using encryption) for electronic messaging. For a more complete background about the history and architecture of S/MIME in the context of email, see [Understanding S/MIME](https://go.microsoft.com/fwlink/?LinkID=393948).</span></span>

<span data-ttu-id="f6007-p102">身為 Exchange Online 管理員，您可以在組織中啟用之信箱的 S/MIME 式安全性。若要設定來使用 S/MIME 中使用以下連結搭配 Exchange Online PowerShell 主題中的指導。若要在支援的電子郵件用戶端使用 S/MIME，貴組織中的使用者必須進行簽署和加密憑證以及發佈至您內部部署 Active Directory 網域服務 (AD DS) 的資料。AD DS 必須位於您控制實體位置和不在遠端設備或網際網路上的某處的雲端架構服務的電腦上。如需 AD DS 的詳細資訊，請參閱 ＜ [Active Directory 網域服務](https://go.microsoft.com/fwlink/?LinkID=394064)。</span><span class="sxs-lookup"><span data-stu-id="f6007-p102">As an Exchange Online admin, you can enable S/MIME-based security for the mailboxes in your organization. Use the guidance in the topics linked here along with Exchange Online PowerShell to set up S/MIME. To use S/MIME in supported email clients, the users in your organization must have certificates issued for signing and encryption purposes and data published to your on-premises Active Directory Domain Service (AD DS). Your AD DS must be located on computers at a physical location that you control and not at a remote facility or cloud-based service somewhere on the internet. For more information about AD DS, see [Active Directory Domain Services](https://go.microsoft.com/fwlink/?LinkID=394064).</span></span>

## <a name="supported-scenarios-and-technical-considerations"></a><span data-ttu-id="f6007-116">支援的案例和技術考量</span><span class="sxs-lookup"><span data-stu-id="f6007-116">Supported scenarios and technical considerations</span></span>

<span data-ttu-id="f6007-117">您可以設定 S/MIME 供任何下列的結束點：</span><span class="sxs-lookup"><span data-stu-id="f6007-117">You can set up S/MIME to work with any of the following end points:</span></span>

- <span data-ttu-id="f6007-118">Outlook 2010 或更新版本</span><span class="sxs-lookup"><span data-stu-id="f6007-118">Outlook 2010 or later</span></span>

- <span data-ttu-id="f6007-119">網頁型 Outlook (先前為 Outlook Web App)</span><span class="sxs-lookup"><span data-stu-id="f6007-119">Outlook on the web (formerly known as Outlook Web App)</span></span>

- <span data-ttu-id="f6007-120">Exchange ActiveSync (EAS)</span><span class="sxs-lookup"><span data-stu-id="f6007-120">Exchange ActiveSync (EAS)</span></span>

<span data-ttu-id="f6007-p103">所需遵循這些結束點的每個設定來使用 S/MIME 的步驟是稍有不同。一般而言，您必須執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="f6007-p103">The steps that you follow to set up S/MIME with each of these end points is slightly different. Generally, you will need to do the following steps:</span></span>

- <span data-ttu-id="f6007-p104">安裝以 Windows 為基礎的憑證授權單位，並且設定公開金鑰基礎結構，來核發 S/MIME 憑證。也支援協力廠商憑證提供者所發出的憑證。如需詳細資訊，請參閱 [Active Directory 憑證服務概觀](https://technet.microsoft.com/library/hh831740.aspx)。</span><span class="sxs-lookup"><span data-stu-id="f6007-p104">Install a Windows-based Certification Authority and set up a public key infrastructure to issue S/MIME certificates. Certificates issued by third-party certificate providers are also supported. For details, see [Active Directory Certificate Services Overview](https://technet.microsoft.com/library/hh831740.aspx).</span></span>

- <span data-ttu-id="f6007-126">在內部部署中發佈使用者憑證 AD DS 帳戶的**UserSMIMECertificate**和/或**UserCertificate**屬性。</span><span class="sxs-lookup"><span data-stu-id="f6007-126">Publish the user certificate in an on-premises AD DS account in the **UserSMIMECertificate** and/or **UserCertificate** attributes.</span></span>

- <span data-ttu-id="f6007-p105">在 Exchange Online 組織中，使用適當的 DirSync 版本，將使用者憑證從 AD DS 同步至 Azure Active Directory。這些憑證會從 Azure Active Directory 同步至 Exchange Online 目錄，並於加密寄給收件者的郵件時使用。</span><span class="sxs-lookup"><span data-stu-id="f6007-p105">For Exchange Online organizations, synchronize the user certificates from AD DS to Azure Active Directory by using an appropriate version of DirSync. These certificates will then get synchronized from Azure Active Directory to Exchange Online directory and will be used when encrypting a message to a recipient.</span></span>

- <span data-ttu-id="f6007-p106">為了驗證 S/MIME 設定的虛擬憑證集合。此資訊使用網路上的 Outlook 驗證電子郵件和確認它已由受信任的憑證簽署的簽章時。</span><span class="sxs-lookup"><span data-stu-id="f6007-p106">Set up a virtual certificate collection in order to validate S/MIME. This information is used by Outlook on the web when validating the signature of an email and ensuring that it was signed by a trusted certificate.</span></span>

- <span data-ttu-id="f6007-131">設定 Outlook 或 EAS 端點來使用 S/MIME。</span><span class="sxs-lookup"><span data-stu-id="f6007-131">Set up the Outlook or EAS end point to use S/MIME.</span></span>

## <a name="setup-smime-with-outlook-on-the-web"></a><span data-ttu-id="f6007-132">設定 S/MIME 網路上的 Outlook</span><span class="sxs-lookup"><span data-stu-id="f6007-132">Setup S/MIME with Outlook on the web</span></span>

<span data-ttu-id="f6007-133">Exchange Online 與 Outlook web 上的設定來使用 S/MIME 包含下列主要步驟：</span><span class="sxs-lookup"><span data-stu-id="f6007-133">Setting up S/MIME for Exchange Online with Outlook on the web involves the following key steps:</span></span>

1. [<span data-ttu-id="f6007-134">設定 Outlook 網頁版的 S/MIME 設定</span><span class="sxs-lookup"><span data-stu-id="f6007-134">Configure S/MIME settings for Outlook on the web</span></span>](configure-s-mime-settings-for-outlook-web-app.md)

2. [<span data-ttu-id="f6007-135">設定虛擬憑證集合以驗證 S/MIME</span><span class="sxs-lookup"><span data-stu-id="f6007-135">Set up virtual certificate collection to validate S/MIME</span></span>](set-up-virtual-certificate-collection-to-validate-s-mime.md)

3. [<span data-ttu-id="f6007-136">將使用者憑證同步至 Office 365 進行 S/MIME 處理</span><span class="sxs-lookup"><span data-stu-id="f6007-136">Sync user certificates to Office 365 for S/MIME</span></span>](sync-user-certificates-to-office-365-for-s-mime.md)

## <a name="related-message-encryption-technologies"></a><span data-ttu-id="f6007-137">相關郵件加密技術</span><span class="sxs-lookup"><span data-stu-id="f6007-137">Related message encryption technologies</span></span>

<span data-ttu-id="f6007-p107">當郵件安全性變得更重要，admins 需要了解原則與概念的安全通訊。此了解特別重要的是因為成長各種保護相關技術 （包括 S/MIME） 可用的。若要了解更多有關 S/MIME 與電子郵件的內容中的運作方式，請參閱[了解 S/MIME](https://go.microsoft.com/fwlink/?LinkID=393948)。各種加密技術共同運作來提供的 rest 和傳送過程中的郵件保護。S/MIME 可以同時使用下列技術，但不是取決於其：</span><span class="sxs-lookup"><span data-stu-id="f6007-p107">As message security becomes more important, admins need to understand the principles and concepts of secure messaging. This understanding is especially important because of the growing variety of protection-related technologies (including S/MIME) that are available. To understand more about S/MIME and how it works in context of email, see [Understanding S/MIME](https://go.microsoft.com/fwlink/?LinkID=393948). A variety of encryption technologies work together to provide protection for messages at rest and in-transit. S/MIME can work simultaneously with the following technologies but is not dependent on them:</span></span>

- <span data-ttu-id="f6007-143">**傳輸層安全性 (TLS)** 會加密電子郵件伺服器之間的通道或路由，以協助防止側錄和竊聽。</span><span class="sxs-lookup"><span data-stu-id="f6007-143">**Transport Layer Security (TLS)** encrypts the tunnel or the route between email servers in order to help prevent snooping and eavesdropping.</span></span>

- <span data-ttu-id="f6007-144">**安全通訊端層 (SSL)** 會加密電子郵件用戶端與 Office 365 伺服器之間的連線。</span><span class="sxs-lookup"><span data-stu-id="f6007-144">**Secure Sockets Layer (SSL)** encrypts the connection between email clients and Office 365 servers.</span></span>

- <span data-ttu-id="f6007-145">**BitLocker** 會加密資料中心硬碟上的資料，因此如果有人未獲授權就存取，便無法讀取資料。</span><span class="sxs-lookup"><span data-stu-id="f6007-145">**BitLocker** encrypts the data on a hard drive in a datacenter so that if someone gets unauthorized access, they can't read it.</span></span>

### <a name="smime-compared-with-office-365-message-encryption"></a><span data-ttu-id="f6007-146">S/MIME 與 Office 365 郵件加密的比較</span><span class="sxs-lookup"><span data-stu-id="f6007-146">S/MIME compared with Office 365 Message Encryption</span></span>

<span data-ttu-id="f6007-p108">S/MIME 需要憑證和發佈基礎結構 (常用於企業對企業及企業對消費者情況)。在 S/MIME 中，由使用者控制密碼編譯金鑰，且在他們所傳送的每一封郵件上，都可選擇是否使用金鑰。電子郵件程式 (例如 Outlook) 會搜尋受信任的根憑證授單位，以進行數位簽署並驗證簽章。Office 365 郵件加密是系統管理員 (而不是個別使用者) 可設定的原則型加密服務，可將傳送給組織內外任何人的郵件加密。它是以 Azure 版權管理 (RMS) 為基礎的線上服務，且不依賴任何公開金鑰基礎結構。Office 365 郵件加密還提供其他功能，例如以組織的品牌來自訂郵件。如需 Office 365 郵件加密的相關資訊，請參閱 [Office 365 郵件加密](https://go.microsoft.com/fwlink/?LinkID=392525)。</span><span class="sxs-lookup"><span data-stu-id="f6007-p108">S/MIME requires a certificate and publishing infrastructure that is often used in business-to-business and business-to-consumer situations. The user controls the cryptographic keys in S/MIME and can choose whether to use them for each message they send. Email programs such as Outlook search a trusted root certificate authority location to perform digital signing and verification of the signature. Office 365 Message Encryption is a policy-based encryption service that can be configured by an administrator, and not an individual user, to encrypt mail sent to anyone inside or outside of the organization. It's an online service that's built on Azure Rights Management (RMS) and does not rely on a public key infrastructure. Office 365 Message Encryption also provides additional capabilities, such as the capability to customize the mail with organization's brand. For more information about Office 365 Message Encryption, see [Office 365 Message Encryption](https://go.microsoft.com/fwlink/?LinkID=392525).</span></span>

## <a name="more-information"></a><span data-ttu-id="f6007-154">其他資訊</span><span class="sxs-lookup"><span data-stu-id="f6007-154">More information</span></span>

[<span data-ttu-id="f6007-155">網頁型 Outlook</span><span class="sxs-lookup"><span data-stu-id="f6007-155">Outlook on the web</span></span>](http://technet.microsoft.com/library/3814b665-01e8-4881-9a44-163f14789ee4.aspx)

[<span data-ttu-id="f6007-156">安全郵件 (2000)</span><span class="sxs-lookup"><span data-stu-id="f6007-156">Secure Mail (2000)</span></span>](https://technet.microsoft.com/en-us/library/cc962043.aspx)
