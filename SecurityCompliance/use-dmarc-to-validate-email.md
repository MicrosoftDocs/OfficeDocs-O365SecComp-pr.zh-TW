---
title: 使用 DMARC 來驗證 Office 365 電子郵件
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/9/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.custom: TN2DMC
ms.assetid: 4a05898c-b8e4-4eab-bd70-ee912e349737
description: '以網域為基礎的郵件驗證、報告和一致性 (DMARC) 搭配寄件者原則架構 (SPF) 和網域金鑰識別郵件 (DKIM) 來驗證郵件寄件者，並確保目的地電子郵件系統信任您網域傳送的郵件。 '
ms.openlocfilehash: 199ab67d17152fc0c4ed6b9f87cde66beaf913d5
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/21/2018
ms.locfileid: "23003222"
---
# <a name="use-dmarc-to-validate-email-in-office-365"></a><span data-ttu-id="2c0f6-103">使用 DMARC 來驗證 Office 365 電子郵件</span><span class="sxs-lookup"><span data-stu-id="2c0f6-103">Use DMARC to validate email in Office 365</span></span>

<span data-ttu-id="2c0f6-p101">Domain-based 訊息驗證，Reporting，and Conformance [DMARC)](https://dmarc.org)適用於以驗證郵件寄件者，並確定目的地的電子郵件系統信任寄件者的郵件的寄件者原則架構 (SPF) 和 DomainKeys 識別郵件 (DKIM)您的網域。實作與 SPF 和 DKIM DMARC 提供其他保護詐騙和網路釣魚電子郵件。DMARC 協助接收的郵件系統決定如何處理郵件會從您網域傳送未通過 SPF 或 DKIM 檢查。</span><span class="sxs-lookup"><span data-stu-id="2c0f6-p101">Domain-based Message Authentication, Reporting, and Conformance [DMARC)](https://dmarc.org) works with Sender Policy Framework (SPF) and DomainKeys Identified Mail (DKIM) to authenticate mail senders and ensure that destination email systems trust messages sent from your domain. Implementing DMARC with SPF and DKIM provides additional protection against spoofing and phishing email. DMARC helps receiving mail systems determine what to do with messages sent from your domain that fail SPF or DKIM checks.</span></span> 
  
## <a name="how-do-spf-and-dmarc-work-together-to-protect-email-in-office-365"></a><span data-ttu-id="2c0f6-107">SPF 和 DMARC 如何共同運作以保護 Office 365 的電子郵件？</span><span class="sxs-lookup"><span data-stu-id="2c0f6-107">How do SPF and DMARC work together to protect email in Office 365?</span></span>
<span data-ttu-id="2c0f6-108"><a name="SPFandDMARC"> </a></span><span class="sxs-lookup"><span data-stu-id="2c0f6-108"></span></span>

 <span data-ttu-id="2c0f6-p102">電子郵件訊息可能包含多個建立者或寄件者地址。這些地址可用於不同用途。例如以下地址：</span><span class="sxs-lookup"><span data-stu-id="2c0f6-p102">An email message may contain multiple originator, or sender, addresses. These addresses are used for different purposes. For example, consider these addresses:</span></span> 
  
- <span data-ttu-id="2c0f6-p103">**「郵件寄件者」地址**可識別寄件者，並指定如果郵件傳遞發生任何問題時要傳送回傳通知的位置 (如未傳遞通知)。這會顯示在電子郵件訊息的信封部分，而且通常不會由電子郵件應用程式顯示。這有時稱為 5321.MailFrom 地址或反向路徑地址。</span><span class="sxs-lookup"><span data-stu-id="2c0f6-p103">**"Mail From" address** Identifies the sender and specifies where to send return notices if any problems occur with the delivery of the message, such as non-delivery notices. This appears in the envelope portion of an email message and is not usually displayed by your email application. This is sometimes called the 5321.MailFrom address or the reverse-path address.</span></span>
    
- <span data-ttu-id="2c0f6-p104">**「寄件者」地址**是由您的郵件應用程式顯示為寄件者地址的地址。此地址可識別電子郵件的作者。也就是負責撰寫郵件的使用者或系統信箱。這有時稱為 5322.From 地址。</span><span class="sxs-lookup"><span data-stu-id="2c0f6-p104">**"From" address** The address displayed as the From address by your mail application. This address identifies the author of the email. That is, the mailbox of the person or system responsible for writing the message. This is sometimes called the 5322.From address.</span></span>
    
<span data-ttu-id="2c0f6-p105">SPF 會針對指定的網域使用 DNS TXT 記錄來提供授權的傳送 IP 位址清單。一般而言，SPF 檢查只會針對 5321.MailFrom 地址執行。這表示當您單獨使用 SPF 時不會驗證 5322.From 地址。這會導致使用者收到的郵件可能通過 SPF 檢查，但卻具有冒名的 5322.From 寄件者地址。例如，請看以下 SMTP 文字記錄：</span><span class="sxs-lookup"><span data-stu-id="2c0f6-p105">SPF uses a DNS TXT record to provide a list of authorized sending IP addresses for a given domain. Normally, SPF checks are only performed against the 5321.MailFrom address. This means that the 5322.From address is not authenticated when you use SPF by itself. This allows for a scenario where a user can receive a message which passes an SPF check but has a spoofed 5322.From sender address. For example, consider this SMTP transcript:</span></span>
  
```
S: Helo woodgrovebank.com
S: Mail from: phish@phishing.contoso.com
S: Rcpt to: astobes@tailspintoys.com
S: data
S: To: "Andrew Stobes" <astobes@tailspintoys.com>
S: From: "Woodgrove Bank Security" <security@woodgrovebank.com>
S: Subject: Woodgrove Bank - Action required
S:
S: Greetings User,
S: 
S: We need to verify your banking details.
S: Please click the following link to verify that we have the right information for your account.
S: 
S: http://short.url/woodgrovebank/updateaccount/12-121.aspx
S:
S: Thank you,
S: Woodgrove Bank
S: .

```

<span data-ttu-id="2c0f6-124">在此文字記錄中，寄件者地址如下：</span><span class="sxs-lookup"><span data-stu-id="2c0f6-124">In this transcript, the sender addresses are as follows:</span></span>
  
- <span data-ttu-id="2c0f6-125">郵件寄件者地址 (5321.MailFrom): phish@phishing.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2c0f6-125">Mail from address (5321.MailFrom): phish@phishing.contoso.com</span></span>
    
- <span data-ttu-id="2c0f6-126">寄件者地址 (5322.From): security@woodgrovebank.com</span><span class="sxs-lookup"><span data-stu-id="2c0f6-126">From address (5322.From): security@woodgrovebank.com</span></span>
    
<span data-ttu-id="2c0f6-p106">如果您設定了 SPF，接收方伺服器會針對郵件寄件者地址 phish@phishing.contoso.com 執行檢查。如果郵件是來自網域 phishing.contoso.com 的有效來源，則 SPF 檢查會通過。由於電子郵件用戶端只會顯示寄件者地址，使用者會看到此郵件是來自 security@woodgrovebank.com。如果單獨使用 SPF，則一律不會驗證 woodgrovebank.com 的有效性。</span><span class="sxs-lookup"><span data-stu-id="2c0f6-p106">If you configured SPF, then the receiving server performs a check against the Mail from address phish@phishing.contoso.com. If the message came from a valid source for the domain phishing.contoso.com then the SPF check passes. Since the email client only displays the From address, the user sees that this message came from security@woodgrovebank.com. With SPF alone, the validity of woodgrovebank.com was never authenticated.</span></span>
  
<span data-ttu-id="2c0f6-p107">若您使用 DMARC，則接收方伺服器也會針對寄件者地址執行檢查。在上述案例中，如果有 woodgrovebank.com 的 DMARC TXT 記錄，則針對寄件者地址的檢查不會通過。</span><span class="sxs-lookup"><span data-stu-id="2c0f6-p107">When you use DMARC, the receiving server also performs a check against the From address. In the example above, if there is a DMARC TXT record in place for woodgrovebank.com, then the check against the From address fails.</span></span>
  
## <a name="what-is-a-dmarc-txt-record"></a><span data-ttu-id="2c0f6-133">什麼是 DMARC TXT 記錄？</span><span class="sxs-lookup"><span data-stu-id="2c0f6-133">What is a DMARC TXT record?</span></span>
<span data-ttu-id="2c0f6-134"><a name="WhatisDMARC"> </a></span><span class="sxs-lookup"><span data-stu-id="2c0f6-134"></span></span>

<span data-ttu-id="2c0f6-p108">如同 SPF 的 DNS 記錄，DMARC 的記錄是 DNS 文字 (TXT) 記錄，其有助於防止詐騙和網路釣魚。您在 DNS 中發佈 DMARC TXT 記錄。DMARC TXT 記錄會根據宣稱為傳送網域的擁有者來驗證電子郵件作者的 IP 位址，藉以驗證電子郵件訊息的原始位置。 DMARC TXT 記錄可識別已獲授權的輸出電子郵件伺服器。目的地電子郵件系統接著會驗證收到的郵件是否來自於已獲授權的輸出電子郵件伺服器。</span><span class="sxs-lookup"><span data-stu-id="2c0f6-p108">Like the DNS records for SPF, the record for DMARC is a DNS text (TXT) record that helps prevent spoofing and phishing. You publish DMARC TXT records in DNS. DMARC TXT records validate the origin of email messages by verifying the IP address of an email's author against the alleged owner of the sending domain. The DMARC TXT record identifies authorized outbound email servers. Destination email systems can then verify that messages they receive originate from authorized outbound email servers.</span></span>
  
<span data-ttu-id="2c0f6-140">Microsoft 的 DMARC TXT 記錄看起來如下：</span><span class="sxs-lookup"><span data-stu-id="2c0f6-140">Microsoft's DMARC TXT record looks something like this:</span></span>
  
```
_dmarc.microsoft.com.   3600    IN      TXT     "v=DMARC1; p=none; pct=100; rua=mailto:d@rua.agari.com; ruf=mailto:d@ruf.agari.com; fo=1" 

```

<span data-ttu-id="2c0f6-p109">Microsoft 會將其 DMARC 報告傳送給協力廠商 [Agari](https://agari.com)。 Agari 會收集並分析 DMARC 報告。</span><span class="sxs-lookup"><span data-stu-id="2c0f6-p109">Microsoft sends its DMARC reports to [Agari](https://agari.com), a 3rd party. Agari collects and analyzes DMARC reports.</span></span>
  
## <a name="implement-dmarc-for-inbound-mail"></a><span data-ttu-id="2c0f6-143">為輸入郵件實作 DMARC</span><span class="sxs-lookup"><span data-stu-id="2c0f6-143">Implement DMARC for inbound mail</span></span>
<span data-ttu-id="2c0f6-144"><a name="implementDMARCinbound"> </a></span><span class="sxs-lookup"><span data-stu-id="2c0f6-144"></span></span>

<span data-ttu-id="2c0f6-p110">您不需要為 Office 365 中收到的郵件執行任何動作來設定 DMARC。我們已經為您處理好所有事項。如果想了解未通過 DMARC 檢查的郵件將會如何，請參閱 [Office 365 如何處理未通過 DMARC 的輸入電子郵件](use-dmarc-to-validate-email.md#inbounddmarcfail)。</span><span class="sxs-lookup"><span data-stu-id="2c0f6-p110">You don't have to do a thing to set up DMARC for mail that you receive in Office 365. We've taken care of everything for you. If you want to learn what happens to mail that fails to pass our DMARC checks, see [How Office 365 handles inbound email that fails DMARC](use-dmarc-to-validate-email.md#inbounddmarcfail).</span></span>
  
## <a name="implement-dmarc-for-outbound-mail-from-office-365"></a><span data-ttu-id="2c0f6-148">為 Office 365 的輸出郵件實作 DMARC</span><span class="sxs-lookup"><span data-stu-id="2c0f6-148">Implement DMARC for outbound mail from Office 365</span></span>
<span data-ttu-id="2c0f6-149"><a name="implementDMARCoutbound"> </a></span><span class="sxs-lookup"><span data-stu-id="2c0f6-149"></span></span>

<span data-ttu-id="2c0f6-p111">如果您使用 Office 365 但未使用自訂網域，也就是您使用的是 onmicrosoft.com，則您不需要執行任何動作來為組織設定或實作 DMARC。已為您設定 SPF，且 Office 365 會自動產生輸出郵件的 DKIM 簽章。如需有關此簽章的詳細資訊，請參閱 [DKIM 與 Office 365 的預設行為](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)。</span><span class="sxs-lookup"><span data-stu-id="2c0f6-p111">If you use Office 365 but you aren't using a custom domain, that is, you use onmicrosoft.com, you don't need to do anything else to configure or implement DMARC for your organization. SPF is already set up for you and Office 365 automatically generates a DKIM signature for your outgoing mail. For more information about this signature, see [Default behavior for DKIM and Office 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span></span>
  
 <span data-ttu-id="2c0f6-p112">如果您有自訂網域，或除了 Office 365 還有使用內部部署 Exchange 伺服器，您需要為輸出郵件手動實作 DMARC。為您的自訂網域實作 DMARC 包含下列步驟：</span><span class="sxs-lookup"><span data-stu-id="2c0f6-p112">If you have a custom domain or you are using on-premises Exchange servers in addition to Office 365, you need to manually implement DMARC for your outbound mail. Implementing DMARC for your custom domain includes these steps:</span></span> 
  
- [<span data-ttu-id="2c0f6-155">步驟 1：找出您網域的郵件有效來源</span><span class="sxs-lookup"><span data-stu-id="2c0f6-155">Step 1: Identify valid sources of mail for your domain</span></span>](use-dmarc-to-validate-email.md#IdentifyValidSources)
    
- [<span data-ttu-id="2c0f6-156">步驟 2：為 Office 365 中的網域設定 SPF</span><span class="sxs-lookup"><span data-stu-id="2c0f6-156">Step 2: Set up SPF for your domain in Office 365</span></span>](use-dmarc-to-validate-email.md#ConfigSPF)
    
- [<span data-ttu-id="2c0f6-157">步驟 3：為 Office 365 中的自訂網域設定 DKIM</span><span class="sxs-lookup"><span data-stu-id="2c0f6-157">Step 3: Set up DKIM for your custom domain in Office 365</span></span>](use-dmarc-to-validate-email.md#ConfigDKIM)
    
- [<span data-ttu-id="2c0f6-158">步驟 4：為 Office 365 中的網域形成 DMARC TXT 記錄</span><span class="sxs-lookup"><span data-stu-id="2c0f6-158">Step 4: Form the DMARC TXT record for your domain in Office 365</span></span>](use-dmarc-to-validate-email.md#CreateDMARCRecord)
    
### <a name="step-1-identify-valid-sources-of-mail-for-your-domain"></a><span data-ttu-id="2c0f6-159">步驟 1：找出您網域的郵件有效來源</span><span class="sxs-lookup"><span data-stu-id="2c0f6-159">Step 1: Identify valid sources of mail for your domain</span></span>
<span data-ttu-id="2c0f6-160"><a name="IdentifyValidSources"> </a></span><span class="sxs-lookup"><span data-stu-id="2c0f6-160"></span></span>

<span data-ttu-id="2c0f6-p113">如果您已設定 SPF，則已完成此步驟。不過，針對 DMARC 還有其他考量。在識別您網域的郵件來源時，有兩個必須回答的問題：</span><span class="sxs-lookup"><span data-stu-id="2c0f6-p113">If you have already set up SPF then you have already gone through this exercise. However, for DMARC, there are additional considerations. When identifying sources of mail for your domain there are two questions you need to answer:</span></span>
  
- <span data-ttu-id="2c0f6-164">哪些 IP 位址會從我的網域傳送郵件？</span><span class="sxs-lookup"><span data-stu-id="2c0f6-164">What IP addresses send messages from my domain?</span></span>
    
- <span data-ttu-id="2c0f6-165">針對由第三方代表我所傳送的郵件，5321.MailFrom 和 5322.From 網域相符嗎？</span><span class="sxs-lookup"><span data-stu-id="2c0f6-165">For mail sent from third parties on my behalf, will the 5321.MailFrom and 5322.From domains match?</span></span>
    
### <a name="step-2-set-up-spf-for-your-domain-in-office-365"></a><span data-ttu-id="2c0f6-166">步驟 2：為 Office 365 中的網域設定 SPF</span><span class="sxs-lookup"><span data-stu-id="2c0f6-166">Step 2: Set up SPF for your domain in Office 365</span></span>
<span data-ttu-id="2c0f6-167"><a name="ConfigSPF"> </a></span><span class="sxs-lookup"><span data-stu-id="2c0f6-167"></span></span>

<span data-ttu-id="2c0f6-168">現在您有所有有效寄件者的清單，您可以按照步驟到 [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。</span><span class="sxs-lookup"><span data-stu-id="2c0f6-168">Now that you have a list of all your valid senders you can follow the steps to [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span>
  
<span data-ttu-id="2c0f6-169">例如，假設 contoso.com 從 Exchange Online 傳送郵件，其為 IP 位址為 192.168.0.1 的內部部署 Exchange 伺服器和 IP 位址為 192.168.100.100 的 Web 應用程式，則 SPF TXT 記錄呈現如下：</span><span class="sxs-lookup"><span data-stu-id="2c0f6-169">For example, assuming contoso.com sends mail from Exchange Online, an on-premises Exchange server whose IP address is 192.168.0.1, and a web application whose IP address is 192.168.100.100, the SPF TXT record would look like this:</span></span>
  
```
contoso.com  IN  TXT  " v=spf1 ip4:192.168.0.1 ip4:192.168.100.100 include:spf.protection.outlook.com -all"
```

<span data-ttu-id="2c0f6-170">最佳作法是，請確定 SPF TXT 記錄包括第三方寄件者。</span><span class="sxs-lookup"><span data-stu-id="2c0f6-170">As a best practice, ensure that your SPF TXT record takes into account third-party senders.</span></span>
  
### <a name="step-3-set-up-dkim-for-your-custom-domain-in-office-365"></a><span data-ttu-id="2c0f6-171">步驟 3：為 Office 365 中的自訂網域設定 DKIM</span><span class="sxs-lookup"><span data-stu-id="2c0f6-171">Step 3: Set up DKIM for your custom domain in Office 365</span></span>
<span data-ttu-id="2c0f6-172"><a name="ConfigDKIM"> </a></span><span class="sxs-lookup"><span data-stu-id="2c0f6-172"></span></span>

<span data-ttu-id="2c0f6-p114">設定好 SPF 後，您需要設定 DKIM。DKIM 可讓您在郵件標頭中將數位簽章新增到電子郵件訊息中。如果您未設定 DKIM 而讓 Office 365 為您的網域使用預設 DKIM 設定，DMARC 可能會失敗。這是因為預設 DKIM 設定會使用初始的 onmicrosoft.com 網域作為 5322.From 地址，而不是您的自訂網域。這會導致所有從您的網域傳送的電子郵件中 5321.MailFrom 與 5322.From 地址不相符。</span><span class="sxs-lookup"><span data-stu-id="2c0f6-p114">Once you have set up SPF, you need to set up DKIM. DKIM lets you add a digital signature to email messages in the message header. If you do not set up DKIM and instead allow Office 365 to use the default DKIM configuration for your domain, DMARC may fail. This is because the default DKIM configuration uses your initial onmicrosoft.com domain as the 5322.From address, not your custom domain. This forces a mismatch between the 5321.MailFrom and the 5322.From addresses in all email sent from your domain.</span></span>
  
<span data-ttu-id="2c0f6-p115">如果有代表您傳送郵件的第三方寄件者，且其傳送的郵件中 5321.MailFrom 和 5322.From 地址不相符，則該電子郵件的 DMARC 將會失敗。若要避免此問題，您必須特別針對第三方寄件者設定網域 DKIM。這可讓 Office 365 驗證來自此第三方服務的電子郵件。 不過，這也讓 Yahoo、Gmail 和 Comcast 等信箱可以驗證由第三方傳送給他們的電子郵件，如同由您所傳送的電子郵件。這樣的好處在於，它能讓客戶對您的網域建立信任，無論客戶的信箱位於何處，同時 Office 365 不會因詐騙而將郵件標示為垃圾郵件，因為郵件已通過您網域的驗證檢查。</span><span class="sxs-lookup"><span data-stu-id="2c0f6-p115">If you have third-party senders that send mail on your behalf and the mail they send has mismatched 5321.MailFrom and 5322.From addresses, DMARC will fail for that email. To avoid this, you need to set up DKIM for your domain specifically with that third-party sender. This allows Office 365 to authenticate email from this 3rd-party service. However, it also allows others, for example, Yahoo, Gmail, and Comcast, to verify email sent to them by the third-party as if it was email sent by you. This is beneficial because it allows your customers to build trust with your domain no matter where their mailbox is located, and at the same time Office 365 won't mark a message as spam due to spoofing because it passes authentication checks for your domain.</span></span>
  
<span data-ttu-id="2c0f6-183">有關為網域設定 DKIM 的相關指示，包括如何為第三方寄件者設定 DKIM 以避免詐騙網域，請參閱 [使用 DKIM 驗證從您在 Office 365 中的自訂網域傳送的輸出電子郵件](use-dkim-to-validate-outbound-email.md)。</span><span class="sxs-lookup"><span data-stu-id="2c0f6-183">For instructions on setting up DKIM for your domain, including how to set up DKIM for third-party senders so they can spoof your domain, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>
  
### <a name="step-4-form-the-dmarc-txt-record-for-your-domain-in-office-365"></a><span data-ttu-id="2c0f6-184">步驟 4：為 Office 365 中的網域形成 DMARC TXT 記錄</span><span class="sxs-lookup"><span data-stu-id="2c0f6-184">Step 4: Form the DMARC TXT record for your domain in Office 365</span></span>
<span data-ttu-id="2c0f6-185"><a name="CreateDMARCRecord"> </a></span><span class="sxs-lookup"><span data-stu-id="2c0f6-185"></span></span>

<span data-ttu-id="2c0f6-p116">雖然還有其他此處未提及的語法選項，以下是 Office 365 最常使用的選項。以下列格式為您的網域形成 DMARC TXT 記錄：</span><span class="sxs-lookup"><span data-stu-id="2c0f6-p116">Although there are other syntax options that are not mentioned here, these are the most commonly used options for Office 365. Form the DMARC TXT record for your domain in the format:</span></span>
  
```
_dmarc.domainTTL IN TXT "v=DMARC1; pct=100; p=policy
```

<span data-ttu-id="2c0f6-188">其中：</span><span class="sxs-lookup"><span data-stu-id="2c0f6-188">where:</span></span>
  
-  <span data-ttu-id="2c0f6-p117">*網域*  是您想要保護的網域。根據預設，記錄會保護該網域及所有子網域的郵件。例如，如果您指定 _dmarc.contoso.com，DMARC 會保護此網域及所有子網域的郵件，例如 housewares.contoso.com 或 plumbing.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="2c0f6-p117">*domain*  is the domain you want to protect. By default, the record protects mail from the domain and all subdomains. For example, if you specify _dmarc.contoso.com, then DMARC protects mail from the domain and all subdomains, such as housewares.contoso.com or plumbing.contoso.com.</span></span> 
    
-  <span data-ttu-id="2c0f6-p118">*TTL*  一律相當於一小時。TTL 所使用的單位，無論是小時 (1 小時)、分鐘 (60 分鐘) 或秒 (3600 秒)，會取決於您的網域註冊機構。</span><span class="sxs-lookup"><span data-stu-id="2c0f6-p118">*TTL*  should always be the equivalent of one hour. The unit used for TTL, either hours (1 hour), minutes (60 minutes), or seconds (3600 seconds), will vary depending on the registrar for your domain.</span></span> 
    
- <span data-ttu-id="2c0f6-194">pct=100 指出這項規則應 100% 用於電子郵件。</span><span class="sxs-lookup"><span data-stu-id="2c0f6-194">pct=100 indicates that this rule should be used for 100% of email.</span></span>
    
-  <span data-ttu-id="2c0f6-p119">*原則*  可指定若 DMARC 失敗時，您想要接收方伺服器遵循的原則。您可以將原則設定為 [無]、[隔離] 或 [拒絕]。</span><span class="sxs-lookup"><span data-stu-id="2c0f6-p119">*policy*  specifies what policy you want the receiving server to follow if DMARC fails. You can set the policy to none, quarantine, or reject.</span></span> 
    
<span data-ttu-id="2c0f6-197">如需使用選項的相關資訊，請參閱[在 Office 365 中實作 DMARC 的最佳作法](use-dmarc-to-validate-email.md#DMARCbestpractices)以熟悉概念。</span><span class="sxs-lookup"><span data-stu-id="2c0f6-197">For information about which options to use, become familiar with the concepts in [Best practices for implementing DMARC in Office 365](use-dmarc-to-validate-email.md#DMARCbestpractices).</span></span>
  
<span data-ttu-id="2c0f6-198">範例：</span><span class="sxs-lookup"><span data-stu-id="2c0f6-198">Examples:</span></span>
  
<span data-ttu-id="2c0f6-199">原則設為 [無]</span><span class="sxs-lookup"><span data-stu-id="2c0f6-199">Policy set to none</span></span>
  
```
_dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=none"
```

<span data-ttu-id="2c0f6-200">原則設為 [隔離]</span><span class="sxs-lookup"><span data-stu-id="2c0f6-200">Policy set to quarantine</span></span>
  
```
_dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=quarantine"
```

<span data-ttu-id="2c0f6-201">原則設為 [拒絕]</span><span class="sxs-lookup"><span data-stu-id="2c0f6-201">Policy set to reject</span></span>
  
```
_dmarc.contoso.com  3600 IN  TXT  "v=DMARC1; p=reject"
```

<span data-ttu-id="2c0f6-p120">一旦您已形成記錄，您需要在網域註冊機構中更新記錄。如需將 DMARC TXT 記錄新增至 Office 365 的 DNS 記錄之相關指示，請參閱[在管理 DNS 記錄時建立 Office 365 的 DNS 記錄](https://support.office.com/article/Create-DNS-records-for-Office-365-when-you-manage-your-DNS-records-b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23)。</span><span class="sxs-lookup"><span data-stu-id="2c0f6-p120">Once you have formed your record, you need to update the record at your domain registrar. For instructions on adding the DMARC TXT record to your DNS records for Office 365, see [Create DNS records for Office 365 when you manage your DNS records](https://support.office.com/article/Create-DNS-records-for-Office-365-when-you-manage-your-DNS-records-b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23).</span></span>
  
## <a name="best-practices-for-implementing-dmarc-in-office-365"></a><span data-ttu-id="2c0f6-204">在 Office 365 中實作 DMARC 的最佳作法</span><span class="sxs-lookup"><span data-stu-id="2c0f6-204">Best practices for implementing DMARC in Office 365</span></span>
<span data-ttu-id="2c0f6-205"><a name="DMARCbestpractices"> </a></span><span class="sxs-lookup"><span data-stu-id="2c0f6-205"></span></span>

<span data-ttu-id="2c0f6-p121">您可以逐步實作 DMARC，而不影響郵件流程的其餘部分。建立和實作首度發行計劃，並依照下列步驟進行。首先在子網域執行這些步驟，然後是其他子網域，最後是組織中的頂層網域，再移至下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="2c0f6-p121">You can implement DMARC gradually without impacting the rest of your mail flow. Create and implement a roll out plan that follows these steps. Do each of these steps first with a sub-domain, then other sub-domains, and finally with the top-level domain in your organization before moving on to the next step.</span></span>
  
1. <span data-ttu-id="2c0f6-209">監控實作 DMARC 的影響</span><span class="sxs-lookup"><span data-stu-id="2c0f6-209">Monitor the impact of implementing DMARC</span></span>
    
    <span data-ttu-id="2c0f6-p122">從簡易的監視模式記錄開始，其可用於子網域或要求 DMARC 接收器向您傳送使用該網域的郵件相關統計資料之網域。監視模式記錄是已將原則設為無 (p=無) 的 DMARC TXT 記錄。許多公司發佈 p=無的 DMARC TXT 記錄，是由於不確定發佈限制較嚴格的 DMARC 原則可能會損失多少電子郵件。</span><span class="sxs-lookup"><span data-stu-id="2c0f6-p122">Start with a simple monitoring-mode record for a sub-domain or domain that requests that DMARC receivers send you statistics about messages that they see using that domain. A monitoring-mode record is a DMARC TXT record that has its policy set to none (p=none). Many companies publish a DMARC TXT record with p=none because they are unsure about how much email they may lose by publishing a more restrictive DMARC policy.</span></span> 
    
    <span data-ttu-id="2c0f6-p123">即使在您實作 SPF 或 DKIM 於郵件基礎結構之前，您即可這麼做。不過，如此將無法有效使用 DMARC 來隔離或拒絕郵件，直到您也同時實作 SPF 和 DKIM。當您引入 SPF 和 DKIM，透過 DMARC 所產生的報告會提供通過這些檢查的郵件以及未通過的數量和來源。您可以輕鬆查看有多少合法傳輸被其涵蓋或未涵蓋，並對問題進行疑難排解。您也會開始看到詐騙郵件送出的數量，及其從何處而來。</span><span class="sxs-lookup"><span data-stu-id="2c0f6-p123">You can do this even before you've implemented SPF or DKIM in your messaging infrastructure. However, you won't be able to effectively quarantine or reject mail by using DMARC until you also implement SPF and DKIM. As you introduce SPF and DKIM, the reports generated through DMARC will provide the numbers and sources of messages that pass these checks, and those that don't. You can easily see how much of your legitimate traffic is or isn't covered by them, and troubleshoot any problems. You'll also begin to see how many fraudulent messages are being sent, and from where.</span></span>
    
2. <span data-ttu-id="2c0f6-218">要求外部郵件系統隔離未通過 DMARC 的郵件</span><span class="sxs-lookup"><span data-stu-id="2c0f6-218">Request that external mail systems quarantine mail that fails DMARC</span></span>
    
    <span data-ttu-id="2c0f6-p124">當您相信您所有或大部分的合法傳輸都受到 SPF 及 DKIM 的保護，且您了解實作 DMARC 的影響後，您可以實作隔離原則。隔離原則是已將原則設為隔離 (p=隔離) 的 DMARC TXT 記錄。執行此動作即是要求 DMARC 接收器將來自您網域中未通過 DMARC 的郵件放至本機相等於垃圾郵件的資料夾，而不是客戶的收件匣。</span><span class="sxs-lookup"><span data-stu-id="2c0f6-p124">When you believe that all or most of your legitimate traffic is protected by SPF and DKIM, and you understand the impact of implementing DMARC, you can implement a quarantine policy. A quarantine policy is a DMARC TXT record that has its policy set to quarantine (p=quarantine). By doing this, you are asking DMARC receivers to put messages from your domain that fail DMARC into the local equivalent of a spam folder instead of your customers' inboxes.</span></span>
    
3. <span data-ttu-id="2c0f6-222">要求外部郵件系統不接受未通過 DMARC 的郵件</span><span class="sxs-lookup"><span data-stu-id="2c0f6-222">Request that external mail systems not accept messages that fail DMARC</span></span>
    
    <span data-ttu-id="2c0f6-p125">最後一個步驟是實作拒絕原則。拒絕原則是已將原則設為拒絕 (p=拒絕) 的 DMARC TXT 記錄。執行此動作即是要求 DMARC 接收器不接受未通過 DMARC 檢查的郵件。</span><span class="sxs-lookup"><span data-stu-id="2c0f6-p125">The final step is implementing a reject policy. A reject policy is a DMARC TXT record that has its policy set to reject (p=reject). When you do this, you're asking DMARC receivers not to accept messages that fail the DMARC checks.</span></span> 
    
## <a name="how-office-365-handles-outbound-email-that-fails-dmarc"></a><span data-ttu-id="2c0f6-226">Office 365 如何處理未通過 DMARC 的輸出電子郵件</span><span class="sxs-lookup"><span data-stu-id="2c0f6-226">How Office 365 handles outbound email that fails DMARC</span></span>
<span data-ttu-id="2c0f6-227"><a name="outbounddmarcfail"> </a></span><span class="sxs-lookup"><span data-stu-id="2c0f6-227"></span></span>

<span data-ttu-id="2c0f6-p126">如果郵件是從 Office 365 輸出和失敗 DMARC，且您已將原則設定為 p = 隔離或 p = 拒絕，透過[高風險傳遞集區的外寄郵件](high-risk-delivery-pool-for-outbound-messages.md)路由傳送郵件。沒有外寄電子郵件的覆寫。</span><span class="sxs-lookup"><span data-stu-id="2c0f6-p126">If a message is outbound from Office 365 and fails DMARC, and you have set the policy to p=quarantine or p=reject, the message is routed through the [High-risk delivery pool for outbound messages](high-risk-delivery-pool-for-outbound-messages.md). There is no override for outbound email.</span></span>
  
<span data-ttu-id="2c0f6-p127">如果您發佈 DMARC 拒絕原則 (p=拒絕)，Office 365 中的其他客戶將無法詐騙您的網域，因為透過服務轉送輸出郵件時，郵件無法通過您網域的 SPF 或 DKIM。 不過，如果您確實發佈 DMARC 拒絕原則，但未透過 Office 365 驗證所有電子郵件，某些輸入電子郵件可能會被標示為垃圾郵件 (如上所述)，或如果您未發佈 SPF 並嘗試透過服務轉送輸出，則郵件會被拒絕。 例如，在形成 DMARC TXT 記錄時，如果您忘記包含某些代表您網域傳送郵件的伺服器及應用程式之 IP 位址，就會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="2c0f6-p127">If you publish a DMARC reject policy (p=reject), no other customer in Office 365 can spoof your domain because messages will not be able to pass SPF or DKIM for your domain when relaying a message outbound through the service. However, if you do publish a DMARC reject policy but don't have all of your email authenticated through Office 365, some of it may be marked as spam for inbound email (as described above), or it will be rejected if you do not publish SPF and try to relay it outbound through the service. This happens, for example, if you forget to include some of the IP addresses for servers and apps that send mail on behalf of your domain when you form your DMARC TXT record.</span></span>
  
## <a name="how-office-365-handles-inbound-email-that-fails-dmarc"></a><span data-ttu-id="2c0f6-233">Office 365 如何處理未通過 DMARC 的輸入電子郵件</span><span class="sxs-lookup"><span data-stu-id="2c0f6-233">How Office 365 handles inbound email that fails DMARC</span></span>
<span data-ttu-id="2c0f6-234"><a name="inbounddmarcfail"> </a></span><span class="sxs-lookup"><span data-stu-id="2c0f6-234"></span></span>

<span data-ttu-id="2c0f6-p128">如果傳送伺服器的 DMARC 原則是 p=拒絕，則 EOP 會將郵件標示為垃圾郵件，而不是拒絕此郵件。換句話說，針對輸入電子郵件，Office 365 會以相同方式處理 p=拒絕和 p=隔離。</span><span class="sxs-lookup"><span data-stu-id="2c0f6-p128">If the DMARC policy of the sending server is p=reject, EOP marks the message as spam instead of rejecting it. In other words, for inbound email, Office 365 treats p=reject and p=quarantine the same way.</span></span>
  
<span data-ttu-id="2c0f6-p129">Office 365 如此設定，是因為某些合法的電子郵件可能無法通過 DMARC。比方說，如果郵件傳送至郵寄清單，然後再將郵件轉送至清單中的所有參與者，則此郵件可能無法通過 DMARC。如果 Office 365 拒絕這些郵件，可能會遺失合法的電子郵件，而且無法再擷取回來。 相反地，這些郵件仍無法通過 DMARC，但其會標示為垃圾郵件而不會被拒絕。如有需要，使用者仍可在收件匣中透過下列方法取得這些郵件：</span><span class="sxs-lookup"><span data-stu-id="2c0f6-p129">Office 365 is configured like this because some legitimate email may fail DMARC. For example, a message might fail DMARC if it is sent to a mailing list that then relays the message to all list participants. If Office 365 rejected these messages, people could lose legitimate email and have no way to retrieve it. Instead, these messages will still fail DMARC but they will be marked as spam and not rejected. If desired, users can still get these messages in their inbox through these methods:</span></span>
  
- <span data-ttu-id="2c0f6-242">使用者使用電子郵件用戶端來個別新增安全寄件者</span><span class="sxs-lookup"><span data-stu-id="2c0f6-242">Users add safe senders individually by using their email client</span></span>
    
- <span data-ttu-id="2c0f6-243">系統管理員為所有使用者建立 Exchange 傳輸規則 (ETR)，以允許這些特定寄件者的郵件。</span><span class="sxs-lookup"><span data-stu-id="2c0f6-243">Administrators create an Exchange transport rule (ETR) for all users that allows messages for those particular senders.</span></span> 
    
## <a name="troubleshooting-your-dmarc-implementation"></a><span data-ttu-id="2c0f6-244">對 DMARC 實作進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="2c0f6-244">Troubleshooting your DMARC implementation</span></span>
<span data-ttu-id="2c0f6-245"><a name="dmarctroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="2c0f6-245"></span></span>

<span data-ttu-id="2c0f6-246">如果您已設定網域的 MX 記錄，其中 EOP 並非第一個項目，則不會針對您的網域強制 DMARC 失敗。</span><span class="sxs-lookup"><span data-stu-id="2c0f6-246">If you have configured your domain's MX records where EOP is not the first entry, DMARC failures will not be enforced for your domain.</span></span> 
  
<span data-ttu-id="2c0f6-p130">如果您是 Office 365 的客戶，且您網域的主要 MX 記錄並未指向 EOP，則您不會取得 DMARC 的效益。比方說，如果您將 MX 記錄指向內部部署郵件伺服器，並使用連接器將電子郵件路由傳送至 EOP，則不適用 DMARC。在此案例中，接收方網域是您其中一個公認的網域，但 EOP 不是主要的 MX。例如，假設 contoso.com 將其 MX 指向本身，並使用 EOP 作為次要 MX 記錄，contoso.com 的 MX 記錄會如下所示：</span><span class="sxs-lookup"><span data-stu-id="2c0f6-p130">If you're an Office 365 customer, and your domain's primary MX record does not point to EOP, you will not get the benefits of DMARC. For example, DMARC won't work if you point the MX record to your on-premises mail server and then route email to EOP by using a connector. In this scenario, the receiving domain is one of your Accepted-Domains but EOP is not the primary MX. For example, suppose contoso.com points its MX at itself and uses EOP as a secondary MX record, contoso.com's MX record looks like the following:</span></span>
  
```
contoso.com     3600   IN  MX  0  mail.contoso.com
contoso.com     3600   IN  MX  10 contoso-com.mail.protection.outlook.com

```

<span data-ttu-id="2c0f6-p131">All、 或最多只電子郵件會先會路由傳送到 mail.contoso.com 自主要 MX，且郵件會取得路由傳送至 EOP。在某些情況下，可能不甚至是列為進行封鎖 EOP MX 記錄所有並設定連接器路由傳送電子郵件只是連接資訊。EOP 無法完成 DMARC 驗證的第一個項目。它只會確保驗證，因為我們不能某些上-內部部署/非-O365 的所有伺服器將會都執行 DMARC 檢查。 DMARC 是合格強制執行客戶的網域 (不 server) 當您設定 DMARC TXT 記錄，但自行接收伺服器實際執行的強制執行。 如果您設定為接收伺服器 eop，EOP 會執行 DMARC 強制執行。</span><span class="sxs-lookup"><span data-stu-id="2c0f6-p131">All, or most, email will first be routed to mail.contoso.com since it's the primary MX, and then mail will get routed to EOP. In some cases, you might not even list EOP as an MX record at all and simply hook up connectors to route your email. EOP does not have to be the first entry for DMARC validation to be done. It just ensures the validation, as we cannot be certain that all on-premise/non-O365 servers will do DMARC checks.  DMARC is eligible to be enforced for a customer’s domain (not server) when you set up the DMARC TXT record, but it is up to the receiving server to actually do the enforcement.  If you set up EOP as the receiving server, then EOP does the DMARC enforcement.</span></span>

  
## <a name="for-more-information"></a><span data-ttu-id="2c0f6-257">相關資訊</span><span class="sxs-lookup"><span data-stu-id="2c0f6-257">For more information</span></span>
<span data-ttu-id="2c0f6-258"><a name="sectionSection8"> </a></span><span class="sxs-lookup"><span data-stu-id="2c0f6-258"></span></span>

<span data-ttu-id="2c0f6-p132">需要 DMARC 的相關資訊？下列資源可以幫些忙。</span><span class="sxs-lookup"><span data-stu-id="2c0f6-p132">Want more information about DMARC? These resources can help.</span></span>
  
- <span data-ttu-id="2c0f6-261">[反垃圾郵件訊息標頭](anti-spam-message-headers.md) 包含 Office 365 針對 DMARC 檢查所使用的語法及標頭欄位。</span><span class="sxs-lookup"><span data-stu-id="2c0f6-261">[Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Office 365 for DMARC checks.</span></span> 
    
- <span data-ttu-id="2c0f6-262">從 M[3](https://www.m3aawg.org/activities/training/dmarc-training-series)AAWG (傳訊、惡意程式碼、行動裝置反不當使用工作群組) 參與 <sup>DMARC 訓練系列課程</sup>。</span><span class="sxs-lookup"><span data-stu-id="2c0f6-262">Take the [DMARC Training Series](https://www.m3aawg.org/activities/training/dmarc-training-series) from M <sup>3</sup>AAWG (Messaging, Malware, Mobile Anti-Abuse Working Group).</span></span>
    
- <span data-ttu-id="2c0f6-263">在 [dmarcian](https://space.dmarcian.com/deployment/) 使用檢查清單。</span><span class="sxs-lookup"><span data-stu-id="2c0f6-263">Use the checklist at [dmarcian](https://space.dmarcian.com/deployment/).</span></span>
    
- <span data-ttu-id="2c0f6-264">直接前往來源 [DMARC.org](https://dmarc.org)。</span><span class="sxs-lookup"><span data-stu-id="2c0f6-264">Go directly to the source at [DMARC.org](https://dmarc.org).</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2c0f6-265">See also</span><span class="sxs-lookup"><span data-stu-id="2c0f6-265">See also</span></span>
<span data-ttu-id="2c0f6-266"><a name="sectionSection8"> </a></span><span class="sxs-lookup"><span data-stu-id="2c0f6-266"></span></span>

[<span data-ttu-id="2c0f6-267">Office 365 可防止詐騙所使用的寄件者原則架構 (SPF)</span><span class="sxs-lookup"><span data-stu-id="2c0f6-267">How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing</span></span>](how-office-365-uses-spf-to-prevent-spoofing.md)
  
[<span data-ttu-id="2c0f6-268">在 Office 365 中設定 SPF 以協助防止詐騙</span><span class="sxs-lookup"><span data-stu-id="2c0f6-268">Set up SPF in Office 365 to help prevent spoofing</span></span>](set-up-spf-in-office-365-to-help-prevent-spoofing.md)
  
[<span data-ttu-id="2c0f6-269">使用 DKIM 驗證從您在 Office 365 中的自訂網域傳送的輸出電子郵件</span><span class="sxs-lookup"><span data-stu-id="2c0f6-269">Use DKIM to validate outbound email sent from your custom domain in Office 365</span></span>](use-dkim-to-validate-outbound-email.md)

