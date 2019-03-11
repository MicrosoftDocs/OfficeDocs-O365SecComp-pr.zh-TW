---
title: 使用 DKIM 在 Office 365 中的自訂網域中的電子郵件
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.custom: TN2DMC
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
ms.collection:
- M365-security-compliance
description: 摘要： 本文將告訴您如何使用 DomainKeys Identified Mail (DKIM) 與 Office 365 來確保目的地電子郵件系統信任自您自訂網域傳送的郵件。
ms.openlocfilehash: 28e529038cefc955da4c76309d169a9f3b5e4a23
ms.sourcegitcommit: 74ad22a5c6c3c9d9324f0f97070909e323a4e9cf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/11/2019
ms.locfileid: "30524077"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain-in-office-365"></a><span data-ttu-id="be5b7-103">使用 DKIM 驗證從您在 Office 365 中的自訂網域傳送的輸出電子郵件</span><span class="sxs-lookup"><span data-stu-id="be5b7-103">Use DKIM to validate outbound email sent from your custom domain in Office 365</span></span>

 <span data-ttu-id="be5b7-104">**摘要：** 本文將告訴您如何使用 DomainKeys Identified Mail (DKIM) 與 Office 365 來確保目的地電子郵件系統信任自您自訂網域傳送輸出郵件。</span><span class="sxs-lookup"><span data-stu-id="be5b7-104">**Summary:** This article describes how you use DomainKeys Identified Mail (DKIM) with Office 365 to ensure that destination email systems trust messages sent outbound from your custom domain.</span></span> 
  
<span data-ttu-id="be5b7-105">您應該使用 DKIM 除了 SPF 和 DMARC，協助防範 spoofers 傳送看起來就來自您網域的郵件。</span><span class="sxs-lookup"><span data-stu-id="be5b7-105">You should use DKIM in addition to SPF and DMARC to help prevent spoofers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="be5b7-106">DKIM 可讓您在郵件標頭中將數位簽章新增到電子郵件訊息中。</span><span class="sxs-lookup"><span data-stu-id="be5b7-106">DKIM lets you add a digital signature to email messages in the message header.</span></span> <span data-ttu-id="be5b7-107">聲音很複雜，但實際上不是。</span><span class="sxs-lookup"><span data-stu-id="be5b7-107">Sounds complicated, but it's really not.</span></span> <span data-ttu-id="be5b7-108">當您設定 DKIM 時，您授權您的網域建立關聯，或登入，它使用密碼編譯驗證電子郵件訊息的名稱。</span><span class="sxs-lookup"><span data-stu-id="be5b7-108">When you configure DKIM, you authorize your domain to associate, or sign, its name to an email message by using cryptographic authentication.</span></span> <span data-ttu-id="be5b7-109">接收來自您網域的電子郵件的電子郵件系統可以使用此數位簽章，以協助您判斷所接收內送電子郵件是否合法。</span><span class="sxs-lookup"><span data-stu-id="be5b7-109">Email systems that receive email from your domain can use this digital signature to help determine if incoming email that they receive is legitimate.</span></span>
  
<span data-ttu-id="be5b7-110">基本上，您可以使用私人金鑰來加密您的網域外寄電子郵件中的標頭。</span><span class="sxs-lookup"><span data-stu-id="be5b7-110">Basically, you use a private key to encrypt the header in your domain's outgoing email.</span></span> <span data-ttu-id="be5b7-111">您可以發佈公開金鑰接收伺服器可以再使用解碼簽章的網域的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="be5b7-111">You publish a public key to your domain's DNS records that receiving servers can then use to decode the signature.</span></span> <span data-ttu-id="be5b7-112">他們使用公開金鑰，驗證郵件真的來自您然後不來自詐騙網域的人員。</span><span class="sxs-lookup"><span data-stu-id="be5b7-112">They use the public key to verify that the messages are really coming from you and not coming from someone spoofing your domain.</span></span>
  
<span data-ttu-id="be5b7-113">Office 365 會自動設定 dkim 初始網域。</span><span class="sxs-lookup"><span data-stu-id="be5b7-113">Office 365 automatically sets up DKIM for initial domains.</span></span> <span data-ttu-id="be5b7-114">當您使用的服務，例如，contoso.onmicrosoft.com 註冊 Office 365 建立您的網域為初始網域。</span><span class="sxs-lookup"><span data-stu-id="be5b7-114">The initial domain is the domain that Office 365 created for you when you signed up with the service, for example, contoso.onmicrosoft.com.</span></span> <span data-ttu-id="be5b7-115">您不需要執行任何動作來為初始網域設定 dkim。</span><span class="sxs-lookup"><span data-stu-id="be5b7-115">You don't need to do anything to set up DKIM for your initial domain.</span></span> <span data-ttu-id="be5b7-116">如需網域的詳細資訊，請參閱[網域的常見問題集](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain)。</span><span class="sxs-lookup"><span data-stu-id="be5b7-116">For more information about domains, see [Domains FAQ](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain).</span></span>
  
<span data-ttu-id="be5b7-117">您可以選擇執行任何關於 DKIM 動作的自訂網域。</span><span class="sxs-lookup"><span data-stu-id="be5b7-117">You can choose to do nothing about DKIM for your custom domain too.</span></span> <span data-ttu-id="be5b7-118">如果您未執行的自訂網域設定 dkim，Office 365 建立私密與公開金鑰組、 啟用 DKIM 簽章，並設定您的自訂網域的 Office 365 預設原則。</span><span class="sxs-lookup"><span data-stu-id="be5b7-118">If you do not set up DKIM for your custom domain, Office 365 creates a private and public key pair, enables DKIM signing, and then configures the Office 365 default policy for your custom domain.</span></span> <span data-ttu-id="be5b7-119">雖然這是對於大多數的 Office 365 客戶的足夠涵蓋範圍，您應該手動設定 DKIM 您自訂的網域，在下列情況：</span><span class="sxs-lookup"><span data-stu-id="be5b7-119">While this is sufficient coverage for most Office 365 customers, you should manually configure DKIM for your custom domain in the following circumstances:</span></span>
  
- <span data-ttu-id="be5b7-120">您有 Office 365 中的多個自訂網域</span><span class="sxs-lookup"><span data-stu-id="be5b7-120">You have more than one custom domain in Office 365</span></span>
    
- <span data-ttu-id="be5b7-121">您要太設定 DMARC （建議使用）</span><span class="sxs-lookup"><span data-stu-id="be5b7-121">You're going to set up DMARC too (recommended)</span></span>
    
- <span data-ttu-id="be5b7-122">您想要控制您的私密金鑰</span><span class="sxs-lookup"><span data-stu-id="be5b7-122">You want control over your private key</span></span>
    
- <span data-ttu-id="be5b7-123">您想要自訂您的 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="be5b7-123">You want to customize your CNAME records</span></span>
    
- <span data-ttu-id="be5b7-124">您想要設定 DKIM 機碼超出協力廠商網域，例如原始的電子郵件，如果您使用協力廠商大量郵件寄件者。</span><span class="sxs-lookup"><span data-stu-id="be5b7-124">You want to set up DKIM keys for email originating out of a third-party domain, for example, if you use a third-party bulk mailer.</span></span>
    
<span data-ttu-id="be5b7-125">本文內容：</span><span class="sxs-lookup"><span data-stu-id="be5b7-125">In this article:</span></span>
  
- [<span data-ttu-id="be5b7-126">DKIM 優於單獨以防止 Office 365 中的惡意詐騙的 SPF 運作的方式</span><span class="sxs-lookup"><span data-stu-id="be5b7-126">How DKIM works better than SPF alone to prevent malicious spoofing in Office 365</span></span>](use-dkim-to-validate-outbound-email.md#HowDKIMWorks)
    
- [<span data-ttu-id="be5b7-127">必須執行手動設定 dkim Office 365 中的項目</span><span class="sxs-lookup"><span data-stu-id="be5b7-127">What you need to do to manually set up DKIM in Office 365</span></span>](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)
    
- [<span data-ttu-id="be5b7-128">若要為 Office 365 中的多個自訂網域設定 DKIM</span><span class="sxs-lookup"><span data-stu-id="be5b7-128">To configure DKIM for more than one custom domain in Office 365</span></span>](use-dkim-to-validate-outbound-email.md#DKIMMultiDomain)
    
- [<span data-ttu-id="be5b7-129">停用的 DKIM 簽章原則在 Office 365 中的自訂網域</span><span class="sxs-lookup"><span data-stu-id="be5b7-129">Disabling the DKIM signing policy for a custom domain in Office 365</span></span>](use-dkim-to-validate-outbound-email.md#DisableDKIMSigningPolicy)
    
- [<span data-ttu-id="be5b7-130">DKIM 與 Office 365 的預設行為</span><span class="sxs-lookup"><span data-stu-id="be5b7-130">Default behavior for DKIM and Office 365</span></span>](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)
    
- [<span data-ttu-id="be5b7-131">使第三方服務可以傳送或詐騙，代表您的自訂網域的電子郵件設定 dkim</span><span class="sxs-lookup"><span data-stu-id="be5b7-131">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>](use-dkim-to-validate-outbound-email.md#SetUp3rdPartyspoof)
    
- [<span data-ttu-id="be5b7-132">後續步驟： 為 Office 365 設定 dkim 之後</span><span class="sxs-lookup"><span data-stu-id="be5b7-132">Next steps: After you set up DKIM for Office 365</span></span>](use-dkim-to-validate-outbound-email.md#DKIMNextSteps)
    
## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing-in-office-365"></a><span data-ttu-id="be5b7-133">DKIM 優於單獨以防止 Office 365 中的惡意詐騙的 SPF 運作的方式</span><span class="sxs-lookup"><span data-stu-id="be5b7-133">How DKIM works better than SPF alone to prevent malicious spoofing in Office 365</span></span>
<span data-ttu-id="be5b7-134"><a name="HowDKIMWorks"> </a></span><span class="sxs-lookup"><span data-stu-id="be5b7-134"></span></span>

<span data-ttu-id="be5b7-135">SPF 會將資訊新增到郵件信封，但實際上 DKIM 加密的郵件標頭中的簽章。</span><span class="sxs-lookup"><span data-stu-id="be5b7-135">SPF adds information to a message envelope but DKIM actually encrypts a signature within the message header.</span></span> <span data-ttu-id="be5b7-136">當您將郵件轉寄時，該訊息的信封部分可以是轉送伺服器離開附件。</span><span class="sxs-lookup"><span data-stu-id="be5b7-136">When you forward a message, portions of that message's envelope can be stripped away by the forwarding server.</span></span> <span data-ttu-id="be5b7-137">數位簽章保持電子郵件訊息，因為它是電子郵件標頭的一部分，因為適用於 DKIM，即使當郵件已轉寄在下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="be5b7-137">Since the digital signature stays with the email message because it's part of the email header, DKIM works even when a message has been forwarded as shown in the following example.</span></span>
  
![流程圖顯示當 SPF 檢查不通過時，轉送的訊息會傳遞 DKIM 驗證](media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)
  
<span data-ttu-id="be5b7-139">在這個範例中，如果您僅有發佈的 SPF TXT 記錄為您的網域，收件者的郵件伺服器可能已標示為您的電子郵件為垃圾郵件，並產生，則為 false 正值的結果。</span><span class="sxs-lookup"><span data-stu-id="be5b7-139">In this example, if you had only published an SPF TXT record for your domain, the recipient's mail server could have marked your email as spam and generated a false positive result.</span></span> <span data-ttu-id="be5b7-140">在此案例中額外的 DKIM 可降低，則為 false 正數垃圾郵件報告。</span><span class="sxs-lookup"><span data-stu-id="be5b7-140">The addition of DKIM in this scenario reduces false positive spam reporting.</span></span> <span data-ttu-id="be5b7-141">DKIM 依賴公開金鑰加密來驗證和不只是 IP 位址，因為 DKIM 會被視為更強形式的驗證 SPF 比。</span><span class="sxs-lookup"><span data-stu-id="be5b7-141">Because DKIM relies on public key cryptography to authenticate and not just IP addresses, DKIM is considered a much stronger form of authentication than SPF.</span></span> <span data-ttu-id="be5b7-142">我們建議使用 SPF 和 DKIM，以及您在部署中的 DMARC。</span><span class="sxs-lookup"><span data-stu-id="be5b7-142">We recommend using both SPF and DKIM, as well as DMARC in your deployment.</span></span>
  
<span data-ttu-id="be5b7-143">講述至今： DKIM 使用私人金鑰來加密的簽章插入郵件標頭。</span><span class="sxs-lookup"><span data-stu-id="be5b7-143">The nitty gritty: DKIM uses a private key to insert an encrypted signature into the message headers.</span></span> <span data-ttu-id="be5b7-144">簽署的網域或撥出的網域，會插入的值為**d =** 在標頭] 欄位。</span><span class="sxs-lookup"><span data-stu-id="be5b7-144">The signing domain, or outbound domain, is inserted as the value of the **d=** field in the header.</span></span> <span data-ttu-id="be5b7-145">驗證網域] 或 [收件者的網域，然後使用**d =** 從 DNS 查閱的公開金鑰，並驗證郵件] 欄位。</span><span class="sxs-lookup"><span data-stu-id="be5b7-145">The verifying domain, or recipient's domain, then use the **d=** field to look up the public key from DNS and authenticate the message.</span></span> <span data-ttu-id="be5b7-146">如果郵件驗證，會傳遞 DKIM 檢查。</span><span class="sxs-lookup"><span data-stu-id="be5b7-146">If the message is verified, the DKIM check passes.</span></span> 
  
## <a name="what-you-need-to-do-to-manually-set-up-dkim-in-office-365"></a><span data-ttu-id="be5b7-147">必須執行手動設定 dkim Office 365 中的項目</span><span class="sxs-lookup"><span data-stu-id="be5b7-147">What you need to do to manually set up DKIM in Office 365</span></span>
<span data-ttu-id="be5b7-148"><a name="SetUpDKIMO365"> </a></span><span class="sxs-lookup"><span data-stu-id="be5b7-148"></span></span>

<span data-ttu-id="be5b7-149">若要設定 DKIM，您將完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="be5b7-149">To configure DKIM, you will complete these steps:</span></span>
  
- [<span data-ttu-id="be5b7-150">在 DNS 中發佈自訂網域的兩筆 CNAME 的記錄</span><span class="sxs-lookup"><span data-stu-id="be5b7-150">Publish two CNAME records for your custom domain in DNS</span></span>](use-dkim-to-validate-outbound-email.md#Publish2CNAME)
    
- [<span data-ttu-id="be5b7-151">啟用 DKIM 簽章的 Office 365 中的自訂網域</span><span class="sxs-lookup"><span data-stu-id="be5b7-151">Enable DKIM signing for your custom domain in Office 365</span></span>](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)
    
### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a><span data-ttu-id="be5b7-152">在 DNS 中發佈自訂網域的兩筆 CNAME 的記錄</span><span class="sxs-lookup"><span data-stu-id="be5b7-152">Publish two CNAME records for your custom domain in DNS</span></span>
<span data-ttu-id="be5b7-153"><a name="Publish2CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="be5b7-153"></span></span>

<span data-ttu-id="be5b7-154">針對您想要新增的 DKIM 簽章在 DNS 中每個網域，您需要發佈兩筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="be5b7-154">For each domain for which you want to add a DKIM signature in DNS, you need to publish two CNAME records.</span></span> <span data-ttu-id="be5b7-155">CNAME 記錄是由 DNS 用來指定網域的正式名稱是另一個網域名稱的別名。</span><span class="sxs-lookup"><span data-stu-id="be5b7-155">A CNAME record is used by DNS to specify that the canonical name of a domain is an alias for another domain name.</span></span> <span data-ttu-id="be5b7-156">CNAME 記錄應建立公開提供的 DNS 伺服器，為您自訂的網域上。</span><span class="sxs-lookup"><span data-stu-id="be5b7-156">The CNAME records should be created on the publicly available DNS servers for your customized domains.</span></span> <span data-ttu-id="be5b7-157">在您的 DNS 中的 CNAME 記錄會指向已存在於記錄 DNS 中建立 Microsoft DNS 伺服器上的 Office 365。</span><span class="sxs-lookup"><span data-stu-id="be5b7-157">The CNAME records in your DNS will point to already created A records that exist in DNS on the Microsoft DNS servers for Office 365.</span></span>
  
 <span data-ttu-id="be5b7-158">Office 365 會執行自動索引鍵的旋轉角度，使用您建立兩筆記錄。</span><span class="sxs-lookup"><span data-stu-id="be5b7-158">Office 365 performs automatic key rotation using the two records that you establish.</span></span> <span data-ttu-id="be5b7-159">如果您有佈建除了 Office 365 中的初始網域的自訂網域，您必須發佈其他每個網域的兩筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="be5b7-159">If you have provisioned custom domains in addition to the initial domain in Office 365, you must publish two CNAME records for each additional domain.</span></span> <span data-ttu-id="be5b7-160">因此，如果您有兩個網域，您必須發佈兩個額外 CNAME 記錄，依此類推。</span><span class="sxs-lookup"><span data-stu-id="be5b7-160">So, if you have two domains, you must publish two additional CNAME records, and so on.</span></span>
  
<span data-ttu-id="be5b7-161">使用下列格式的 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="be5b7-161">Use the following format for the CNAME records.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="be5b7-162">如果您是下列其中一個我們 GCC 高的客戶，我們計算_domainGuid_不同 ！</span><span class="sxs-lookup"><span data-stu-id="be5b7-162">If you are one of our GCC High customers, we calculate _domainGuid_ differently!</span></span> <span data-ttu-id="be5b7-163">而不是查閱的 MX 記錄，來計算_domainGuid_您_initialDomain_ ，改為我們加以計算直接從自訂的網域。</span><span class="sxs-lookup"><span data-stu-id="be5b7-163">Instead of looking up the MX record for your _initialDomain_ to calculate _domainGuid_, instead we calculate it directly from the customized domain.</span></span> <span data-ttu-id="be5b7-164">例如，如果您自訂的網域是 「 contoso.com 」 您 domainGuid 會變成 「 contoso com 」，任何期間取代連字號。</span><span class="sxs-lookup"><span data-stu-id="be5b7-164">For example, if your customized domain is “contoso.com” your domainGuid becomes “contoso-com”, any periods are replaced with a dash.</span></span> <span data-ttu-id="be5b7-165">因此，不論何種 MX 記錄您 initialDomain 指向，您將一律使用上述方法來計算筆 CNAME 記錄中使用 domainGuid。</span><span class="sxs-lookup"><span data-stu-id="be5b7-165">So, regardless of what MX record your initialDomain points to, you’ll always use the above method to calculate the domainGuid to use in your CNAME records.</span></span>

  
```
Host name:          selector1._domainkey
Points to address or value: selector1-<domainGUID>._domainkey.<initialDomain> 
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: selector2-<domainGUID>._domainkey.<initialDomain> 
TTL:                3600
```

<span data-ttu-id="be5b7-166">其中：</span><span class="sxs-lookup"><span data-stu-id="be5b7-166">Where:</span></span>
  
- <span data-ttu-id="be5b7-167">針對 Office 365 中，選取器一定會 「 selector1 」 或 「 selector2 」。</span><span class="sxs-lookup"><span data-stu-id="be5b7-167">For Office 365, the selectors will always be "selector1" or "selector2".</span></span> 
    
- <span data-ttu-id="be5b7-168">_domainGUID_是_domainGUID_自訂 MX 記錄的自訂網域出現之前 mail.protection.outlook.com 中相同。</span><span class="sxs-lookup"><span data-stu-id="be5b7-168">_domainGUID_ is the same as the _domainGUID_ in the customized MX record for your custom domain that appears before mail.protection.outlook.com.</span></span> <span data-ttu-id="be5b7-169">例如，在網域 contoso.com 的下列 MX 記錄， _domainGUID_是 contoso com:</span><span class="sxs-lookup"><span data-stu-id="be5b7-169">For example, in the following MX record for the domain contoso.com, the _domainGUID_ is contoso-com:</span></span> 
    
    ```
    contoso.com.  3600  IN  MX   5 contoso-com.mail.protection.outlook.com
    ```

- <span data-ttu-id="be5b7-170">_initialDomain_是您的 Office 365 註冊時所用的網域。</span><span class="sxs-lookup"><span data-stu-id="be5b7-170">_initialDomain_ is the domain that you used when you signed up for Office 365.</span></span> <span data-ttu-id="be5b7-171">初始網域一律以.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="be5b7-171">Initial domains always end in onmicrosoft.com.</span></span> <span data-ttu-id="be5b7-172">如需決定初始網域資訊，請參閱[網域的常見問題集](https://support.office.com/article/1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain)。</span><span class="sxs-lookup"><span data-stu-id="be5b7-172">For information about determining your initial domain, see [Domains FAQ](https://support.office.com/article/1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain).</span></span>
    
<span data-ttu-id="be5b7-173">例如，如果您有 cohovineyardandwinery.onmicrosoft.com，初始網域和兩個自訂網域 cohovineyard.com cohowinery.com，您必須設定其他每個網域，總共四筆 CNAME 記錄的兩筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="be5b7-173">For example, if you have an initial domain of cohovineyardandwinery.onmicrosoft.com, and two custom domains cohovineyard.com and cohowinery.com, you would need to set up two CNAME records for each additional domain, for a total of four CNAME records.</span></span>
  
```
Host name:          selector1._domainkey
Points to address or value: **selector1-cohovineyard-com**._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: **selector2-cohovineyard-com**._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:          selector1._domainkey
Points to address or value: **selector1-cohowinery-com**._domainkey.cohovineyardandwinery.onmicrosoft.com 
TTL:                3600
 
Host name:          selector2._domainkey
Points to address or value: **selector2-cohowinery-com**._domainkey.cohovineyardandwinery.onmicrosoft.com 
TTL:                3600
```

### <a name="enable-dkim-signing-for-your-custom-domain-in-office-365"></a><span data-ttu-id="be5b7-174">啟用 DKIM 簽章的 Office 365 中的自訂網域</span><span class="sxs-lookup"><span data-stu-id="be5b7-174">Enable DKIM signing for your custom domain in Office 365</span></span>
<span data-ttu-id="be5b7-175"><a name="EnableDKIMinO365"> </a></span><span class="sxs-lookup"><span data-stu-id="be5b7-175"></span></span>

<span data-ttu-id="be5b7-176">一旦您已經在 DNS 中發佈的 CNAME 記錄，您準備好要啟用 DKIM 簽署透過 Office 365。</span><span class="sxs-lookup"><span data-stu-id="be5b7-176">Once you have published the CNAME records in DNS, you are ready to enable DKIM signing through Office 365.</span></span> <span data-ttu-id="be5b7-177">您可以透過 Office 365 系統管理中心或使用 PowerShell 來執行這項操作。</span><span class="sxs-lookup"><span data-stu-id="be5b7-177">You can do this either through the Office 365 admin center or by using PowerShell.</span></span>
  
#### <a name="to-enable-dkim-signing-for-your-custom-domain-through-the-office-365-admin-center"></a><span data-ttu-id="be5b7-178">若要啟用 DKIM 簽章的自訂網域透過 Office 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="be5b7-178">To enable DKIM signing for your custom domain through the Office 365 admin center</span></span>

1. <span data-ttu-id="be5b7-179">使用您的 公司或學校帳戶[登入 Office 365](https://support.office.microsoft.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="be5b7-179">[Sign in to Office 365](https://support.office.microsoft.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) with your work or school account.</span></span> 
    
2. <span data-ttu-id="be5b7-180">選取左上角的應用程式啟動器圖示，然後選擇 [管理員]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="be5b7-180">Select the app launcher icon in the upper-left and choose **Admin**.</span></span>
    
3. <span data-ttu-id="be5b7-181">左下導覽中，依序展開 [**系統管理員**，並選擇 [ **Exchange**]。</span><span class="sxs-lookup"><span data-stu-id="be5b7-181">In the lower-left navigation, expand **Admin** and choose **Exchange**.</span></span>
    
4. <span data-ttu-id="be5b7-182">移至 [**保護** \> **dkim**。</span><span class="sxs-lookup"><span data-stu-id="be5b7-182">Go to **Protection** \> **dkim**.</span></span>
    
5. <span data-ttu-id="be5b7-183">選取您要啟用 DKIM，然後為**此網域的 DKIM 簽章簽署郵件**，選擇 [**啟用**的網域。</span><span class="sxs-lookup"><span data-stu-id="be5b7-183">Select the domain for which you want to enable DKIM and then, for **Sign messages for this domain with DKIM signatures**, choose **Enable**.</span></span> <span data-ttu-id="be5b7-184">針對每個自訂網域重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="be5b7-184">Repeat this step for each custom domain.</span></span>
    
#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a><span data-ttu-id="be5b7-185">若要啟用 DKIM 簽章的自訂網域，藉由使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="be5b7-185">To enable DKIM signing for your custom domain by using PowerShell</span></span>

1. <span data-ttu-id="be5b7-186">[連線至 Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289.aspx) (機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="be5b7-186">[Connect to Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289.aspx).</span></span>
    
2. <span data-ttu-id="be5b7-187">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="be5b7-187">Run the following command:</span></span>
    
    ```
    New-DkimSigningConfig -DomainName <domain> -Enabled $true
    ```

   <span data-ttu-id="be5b7-188">其中_網域_是您想要啟用 DKIM 簽章的自訂網域名稱。</span><span class="sxs-lookup"><span data-stu-id="be5b7-188">Where _domain_ is the name of the custom domain that you want to enable DKIM signing for.</span></span> 
    
   <span data-ttu-id="be5b7-189">例如，針對 contoso.com 網域：</span><span class="sxs-lookup"><span data-stu-id="be5b7-189">For example, for the domain contoso.com:</span></span>
    
    ```
    New-DkimSigningConfig -DomainName contoso.com -Enabled $true
    ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-office-365"></a><span data-ttu-id="be5b7-190">若要確認的 DKIM 簽章已正確設定為 Office 365</span><span class="sxs-lookup"><span data-stu-id="be5b7-190">To Confirm DKIM signing is configured properly for Office 365</span></span>

<span data-ttu-id="be5b7-191">請稍候幾分鐘時間才能遵循這些步驟來確認您已正確設定 DKIM。</span><span class="sxs-lookup"><span data-stu-id="be5b7-191">Wait a few minutes before you follow these steps to confirm that you have properly configured DKIM.</span></span> <span data-ttu-id="be5b7-192">這可讓散佈到整個網路網域的 DKIM 資訊的時間。</span><span class="sxs-lookup"><span data-stu-id="be5b7-192">This allows time for the DKIM information about the domain to be spread throughout the network.</span></span>
  
- <span data-ttu-id="be5b7-193">從傳送訊息內啟用 Office 365 DKIM 的網域帳戶到另一個電子郵件帳戶，例如 outlook.com 或 Hotmail.com。</span><span class="sxs-lookup"><span data-stu-id="be5b7-193">Send a message from an account within your Office 365 DKIM-enabled domain to another email account such as outlook.com or Hotmail.com.</span></span>
    
- <span data-ttu-id="be5b7-194">請勿 aol.com 帳戶為了進行測試。</span><span class="sxs-lookup"><span data-stu-id="be5b7-194">Do not use an aol.com account for testing purposes.</span></span> <span data-ttu-id="be5b7-195">AOL 可能會略過 DKIM 檢查如果 SPF 檢查會通過。</span><span class="sxs-lookup"><span data-stu-id="be5b7-195">AOL may skip the DKIM check if the SPF check passes.</span></span> <span data-ttu-id="be5b7-196">這將會進行造成您的測試。</span><span class="sxs-lookup"><span data-stu-id="be5b7-196">This will nullify your test.</span></span>
    
- <span data-ttu-id="be5b7-197">開啟的郵件，然後查看 [標頭。</span><span class="sxs-lookup"><span data-stu-id="be5b7-197">Open the message and look at the header.</span></span> <span data-ttu-id="be5b7-198">檢視郵件的標頭指示會視您的郵件用戶端而異。</span><span class="sxs-lookup"><span data-stu-id="be5b7-198">Instructions for viewing the header for the message will vary depending on your messaging client.</span></span> <span data-ttu-id="be5b7-199">如需在 Outlook 中檢視郵件標頭指示，請參閱 <<c0>檢視電子郵件訊息標頭。</span><span class="sxs-lookup"><span data-stu-id="be5b7-199">For instructions on viewing message headers in Outlook, see [View e-mail message headers](https://support.office.com/article/CD039382-DC6E-4264-AC74-C048563D212C).</span></span>

  <span data-ttu-id="be5b7-200">DKIM 簽章的郵件會包含主機名稱與網域您定義當您發佈的 CNAME 項目。</span><span class="sxs-lookup"><span data-stu-id="be5b7-200">The DKIM-signed message will contain the host name and domain you defined when you published the CNAME entries.</span></span> <span data-ttu-id="be5b7-201">郵件看起來如下列範例：</span><span class="sxs-lookup"><span data-stu-id="be5b7-201">The message will look something like this example:</span></span> 
    
    ```
    From: Example User <example@contoso.com> 
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed; 
        s=selector1; d=contoso.com; t=1429912795; 
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type; 
        bh=<body hash>; 
        b=<signed field>;
    ```

- <span data-ttu-id="be5b7-202">尋找 Authentication-results 標頭。</span><span class="sxs-lookup"><span data-stu-id="be5b7-202">Look for the Authentication-Results header.</span></span> <span data-ttu-id="be5b7-203">雖然每個接收服務會使用稍有不同的格式，內送郵件加上戳記，結果應該包含類似**DKIM = 傳遞**或**DKIM = 確定**。</span><span class="sxs-lookup"><span data-stu-id="be5b7-203">While each receiving service uses a slightly different format to stamp the incoming mail, the result should include something like **DKIM=pass** or **DKIM=OK**.</span></span> 
    
## <a name="to-configure-dkim-for-more-than-one-custom-domain-in-office-365"></a><span data-ttu-id="be5b7-204">若要為 Office 365 中的多個自訂網域設定 DKIM</span><span class="sxs-lookup"><span data-stu-id="be5b7-204">To configure DKIM for more than one custom domain in Office 365</span></span>
<span data-ttu-id="be5b7-205"><a name="DKIMMultiDomain"> </a></span><span class="sxs-lookup"><span data-stu-id="be5b7-205"></span></span>

<span data-ttu-id="be5b7-206">如果有些時候您決定在未來新增另一個自訂的網域，而且您想要啟用 DKIM 的新網域，您必須完成本文的每個網域中的步驟。</span><span class="sxs-lookup"><span data-stu-id="be5b7-206">If at some point in the future you decide to add another custom domain and you want to enable DKIM for the new domain, you must complete the steps in this article for each domain.</span></span> <span data-ttu-id="be5b7-207">具體而言，完成所有步驟，[必須執行手動設定 dkim Office 365 中的項目](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)。</span><span class="sxs-lookup"><span data-stu-id="be5b7-207">Specifically, complete all steps in [What you need to do to manually set up DKIM in Office 365](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).</span></span>
  
## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain-in-office-365"></a><span data-ttu-id="be5b7-208">停用的 DKIM 簽章原則在 Office 365 中的自訂網域</span><span class="sxs-lookup"><span data-stu-id="be5b7-208">Disabling the DKIM signing policy for a custom domain in Office 365</span></span>
<span data-ttu-id="be5b7-209"><a name="DisableDKIMSigningPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="be5b7-209"></span></span>

<span data-ttu-id="be5b7-210">停用簽章原則不完全停用 DKIM。</span><span class="sxs-lookup"><span data-stu-id="be5b7-210">Disabling the signing policy does not completely disable DKIM.</span></span> <span data-ttu-id="be5b7-211">在一段時間，Office 365 會自動套用預設的 Office 365 原則，為您的網域。</span><span class="sxs-lookup"><span data-stu-id="be5b7-211">After a period of time, Office 365 will automatically apply the default Office 365 policy for your domain.</span></span> <span data-ttu-id="be5b7-212">如需詳細資訊，請參閱[預設 DKIM 與 Office 365 的行為](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)。</span><span class="sxs-lookup"><span data-stu-id="be5b7-212">For more information, see [Default behavior for DKIM and Office 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span></span>
  
### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a><span data-ttu-id="be5b7-213">若要停用的 DKIM 簽章原則使用 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="be5b7-213">To disable the DKIM signing policy by using Windows PowerShell</span></span>

1. <span data-ttu-id="be5b7-214">[連線至 Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289.aspx) (機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="be5b7-214">[Connect to Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289.aspx).</span></span>
    
2. <span data-ttu-id="be5b7-215">執行下列其中一個您想要停用 DKIM 簽章的每個網域的下列命令。</span><span class="sxs-lookup"><span data-stu-id="be5b7-215">Run one of the following commands for each domain for which you want to disable DKIM signing.</span></span>
    
    ```
    $p=Get-DkimSigningConfig -identity <domain>
    $p[0] | set-DkimSigningConfig -enabled $false
    ```

   <span data-ttu-id="be5b7-216">例如：</span><span class="sxs-lookup"><span data-stu-id="be5b7-216">For example:</span></span>
    
    ```
    $p=Get-DkimSigningConfig -identity contoso.com
    $p[0] | set-DkimSigningConfig -enabled $false
    ```

   <span data-ttu-id="be5b7-217">或</span><span class="sxs-lookup"><span data-stu-id="be5b7-217">Or</span></span>
    
    ```
    Set-DkimSigningConfig -identity $p[<number>].identity -enabled $false
    ```

    <span data-ttu-id="be5b7-218">_數字_所在之原則的索引。</span><span class="sxs-lookup"><span data-stu-id="be5b7-218">Where _number_ is the index of the policy.</span></span> <span data-ttu-id="be5b7-219">例如：</span><span class="sxs-lookup"><span data-stu-id="be5b7-219">For example:</span></span> 
    
    ```
    Set-DkimSigningConfig -identity $p[0].identity -enabled $false
    ```

## <a name="default-behavior-for-dkim-and-office-365"></a><span data-ttu-id="be5b7-220">DKIM 與 Office 365 的預設行為</span><span class="sxs-lookup"><span data-stu-id="be5b7-220">Default behavior for DKIM and Office 365</span></span>
<span data-ttu-id="be5b7-221"><a name="DefaultDKIMbehavior"> </a></span><span class="sxs-lookup"><span data-stu-id="be5b7-221"></span></span>

<span data-ttu-id="be5b7-222">如果您不啟用 DKIM，Office 365 會自動建立的自訂網域的 1024年位元 DKIM 公用金鑰] 和 [關聯的私密金鑰我們在內部儲存在我們的資料中心。</span><span class="sxs-lookup"><span data-stu-id="be5b7-222">If you do not enable DKIM, Office 365 automatically creates a 1024-bit DKIM public key for your custom domain and the associated private key which we store internally in our datacenter.</span></span> <span data-ttu-id="be5b7-223">根據預設，Office 365 會使用預設的簽章的網域的就地沒有原則設定。</span><span class="sxs-lookup"><span data-stu-id="be5b7-223">By default, Office 365 uses a default signing configuration for domains that do not have a policy in place.</span></span> <span data-ttu-id="be5b7-224">這表示，如果您沒有設定 dkim 自行，Office 365 會使用其預設原則，才能啟用您的網域的 DKIM，它會建立的機碼。</span><span class="sxs-lookup"><span data-stu-id="be5b7-224">This means that if you do not set up DKIM yourself, Office 365 will use its default policy and keys it creates in order to enable DKIM for your domain.</span></span>
  
<span data-ttu-id="be5b7-225">此外，如果您停用 DKIM 簽署後，啟用在一段時間後，Office 365 會自動套用您網域的 Office 365 預設原則。</span><span class="sxs-lookup"><span data-stu-id="be5b7-225">Also, if you disable DKIM signing after enabling it, after a period of time, Office 365 will automatically apply the Office 365 default policy for your domain.</span></span>
  
<span data-ttu-id="be5b7-226">在下列範例中，假設為 fabrikam.com 的 DKIM 已啟用 Office 365，而不是依網域的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="be5b7-226">In the following example, suppose that DKIM for fabrikam.com was enabled by Office 365, not by the administrator of the domain.</span></span> <span data-ttu-id="be5b7-227">這表示，所需的 Cname 不存在於 DNS。</span><span class="sxs-lookup"><span data-stu-id="be5b7-227">This means that the required CNAMEs do not exist in DNS.</span></span> <span data-ttu-id="be5b7-228">從這個網域的電子郵件的 DKIM 簽章看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="be5b7-228">DKIM signatures for email from this domain will look something like this:</span></span>
  
```
From: Second Example <second.example@fabrikam.com> 
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed; 
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795; 
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type; 
    bh=<body hash>; 
    b=<signed field>;
```

<span data-ttu-id="be5b7-229">在這個範例中，網域與主機名稱包含要 CNAME 會指向如果 DKIM 簽章為 fabrikam.com 有網域管理員所啟用的值。</span><span class="sxs-lookup"><span data-stu-id="be5b7-229">In this example, the host name and domain contain the values to which the CNAME would point if DKIM-signing for fabrikam.com had been enabled by the domain administrator.</span></span> <span data-ttu-id="be5b7-230">最後，從 Office 365 傳送每封郵件將會 DKIM 簽章。</span><span class="sxs-lookup"><span data-stu-id="be5b7-230">Eventually, every single message sent from Office 365 will be DKIM-signed.</span></span> <span data-ttu-id="be5b7-231">如果您自行啟用 DKIM，網域將會在 [從網域相同： 地址，在此案例的 fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="be5b7-231">If you enable DKIM yourself, the domain will be the same as the domain in the From: address, in this case fabrikam.com.</span></span> <span data-ttu-id="be5b7-232">如果您不等待，它會對齊，並會改用貴組織的初始網域。</span><span class="sxs-lookup"><span data-stu-id="be5b7-232">If you don't, it will not align and instead will use your organization's initial domain.</span></span> <span data-ttu-id="be5b7-233">如需決定初始網域資訊，請參閱[網域的常見問題集](https://support.office.com/article/1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain)。</span><span class="sxs-lookup"><span data-stu-id="be5b7-233">For information about determining your initial domain, see [Domains FAQ](https://support.office.com/article/1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain).</span></span>
  
## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a><span data-ttu-id="be5b7-234">使第三方服務可以傳送或詐騙，代表您的自訂網域的電子郵件設定 dkim</span><span class="sxs-lookup"><span data-stu-id="be5b7-234">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>
<span data-ttu-id="be5b7-235"><a name="SetUp3rdPartyspoof"> </a></span><span class="sxs-lookup"><span data-stu-id="be5b7-235"></span></span>

<span data-ttu-id="be5b7-236">某些大量電子郵件服務提供者或軟體為-服務提供者，可讓您設定 DKIM 機碼來自其服務的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="be5b7-236">Some bulk email service providers, or software-as-a-service providers, let you set up DKIM keys for email that originates from their service.</span></span> <span data-ttu-id="be5b7-237">這需要您自己和協力廠商之間協調才能設定必要的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="be5b7-237">This requires coordination between yourself and the third-party in order to set up the necessary DNS records.</span></span> <span data-ttu-id="be5b7-238">沒有兩個組織中進行這完全相同的方式。</span><span class="sxs-lookup"><span data-stu-id="be5b7-238">No two organizations do it exactly the same way.</span></span> <span data-ttu-id="be5b7-239">相反地，處理程序取決於整個組織。</span><span class="sxs-lookup"><span data-stu-id="be5b7-239">Instead, the process depends entirely on the organization.</span></span>
  
<span data-ttu-id="be5b7-240">顯示 contoso.com 和 bulkemailprovider.com 正確設定的 DKIM 範例郵件看起來可能如下：</span><span class="sxs-lookup"><span data-stu-id="be5b7-240">An example message showing a properly configured DKIM for contoso.com and bulkemailprovider.com might look like this:</span></span>
  
```
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

<span data-ttu-id="be5b7-241">在這個範例中，以達到此結果：</span><span class="sxs-lookup"><span data-stu-id="be5b7-241">In this example, in order to achieve this result:</span></span>
  
1. <span data-ttu-id="be5b7-242">大量電子郵件供應商 Contoso 公開金鑰 DKIM。</span><span class="sxs-lookup"><span data-stu-id="be5b7-242">Bulk Email Provider gave Contoso a public DKIM key.</span></span>
    
2. <span data-ttu-id="be5b7-243">Contoso 發佈至其 DNS 記錄的 DKIM 機碼。</span><span class="sxs-lookup"><span data-stu-id="be5b7-243">Contoso published the DKIM key to its DNS record.</span></span>
    
3. <span data-ttu-id="be5b7-244">時傳送電子郵件，大量電子郵件提供者會在具有相對應之私密金鑰的機碼。</span><span class="sxs-lookup"><span data-stu-id="be5b7-244">When sending email, Bulk Email Provider signs the key with the corresponding private key.</span></span> <span data-ttu-id="be5b7-245">如此一來，大量電子郵件提供者會附加到郵件標頭的 DKIM 簽章。</span><span class="sxs-lookup"><span data-stu-id="be5b7-245">By doing so, Bulk Email Provider attached the DKIM signature to the message header.</span></span>
    
4. <span data-ttu-id="be5b7-246">接收的電子郵件系統來執行 DKIM 檢查驗證 DKIM 簽章 d =\<網域\>根據在 [從網域值: (5322.From) 地址的郵件。</span><span class="sxs-lookup"><span data-stu-id="be5b7-246">Receiving email systems perform a DKIM check by authenticating the DKIM-Signature d=\<domain\> value against the domain in the From: (5322.From) address of the message.</span></span> <span data-ttu-id="be5b7-247">在這個範例中，兩個值相符：</span><span class="sxs-lookup"><span data-stu-id="be5b7-247">In this example, the values match:</span></span>
    
    <span data-ttu-id="be5b7-248">寄件者 @**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="be5b7-248">sender@**contoso.com**</span></span>
    
    <span data-ttu-id="be5b7-249">d =**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="be5b7-249">d=**contoso.com**</span></span>
    
## <a name="next-steps-after-you-set-up-dkim-for-office-365"></a><span data-ttu-id="be5b7-250">後續步驟： 為 Office 365 設定 dkim 之後</span><span class="sxs-lookup"><span data-stu-id="be5b7-250">Next steps: After you set up DKIM for Office 365</span></span>
<span data-ttu-id="be5b7-251"><a name="DKIMNextSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="be5b7-251"></span></span>

<span data-ttu-id="be5b7-252">雖然 DKIM 設計來協助防止詐騙，DKIM 更妥善地運作搭配 SPF 和 DMARC。</span><span class="sxs-lookup"><span data-stu-id="be5b7-252">Although DKIM is designed to help prevent spoofing, DKIM works better with SPF and DMARC.</span></span> <span data-ttu-id="be5b7-253">一旦您已設定 DKIM，如果您還沒有已設定好 SPF 應執行此作業。</span><span class="sxs-lookup"><span data-stu-id="be5b7-253">Once you have set up DKIM, if you have not already set up SPF you should do so.</span></span> <span data-ttu-id="be5b7-254">快速介紹 SPF，並讓其快速設定，請參閱[設定 spf 以協助防止詐騙的 Office 365 中](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。</span><span class="sxs-lookup"><span data-stu-id="be5b7-254">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="be5b7-255">如需更深入了解的 Office 365 如何使用 SPF，或疑難排解或非標準的部署，例如混合式部署，啟動與[Office 365 如何使用寄件者原則架構 (SPF)，來防止詐騙](how-office-365-uses-spf-to-prevent-spoofing.md)。</span><span class="sxs-lookup"><span data-stu-id="be5b7-255">For a more in-depth understanding of how Office 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="be5b7-256">接下來，請參閱[使用 DMARC 來驗證 Office 365 電子郵件](use-dmarc-to-validate-email.md)。</span><span class="sxs-lookup"><span data-stu-id="be5b7-256">Next, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="be5b7-257">[反垃圾郵件郵件標頭](anti-spam-message-headers.md)包含針對 DKIM 檢查 Office 365 所使用的語法及標頭欄位。</span><span class="sxs-lookup"><span data-stu-id="be5b7-257">[Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Office 365 for DKIM checks.</span></span> 
  

