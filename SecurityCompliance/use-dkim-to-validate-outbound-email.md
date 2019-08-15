---
title: 在 Office 365 中將 DKIM 用於自訂網域中的電子郵件
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
ms.collection:
- M365-security-compliance
description: 摘要：本文說明如何在 Office 365 中使用網域金鑰識別郵件 (DKIM)，以確保目的地電子郵件系統會信任從您的自訂網域傳送的郵件。
ms.openlocfilehash: d47a1e629952d65acdd9ecf05e4e521684775ae9
ms.sourcegitcommit: d4acce11a26536b9d6ca71ba4933fc95136198a4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/15/2019
ms.locfileid: "36407922"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain-in-office-365"></a><span data-ttu-id="11bfd-103">使用 DKIM 驗證從您在 Office 365 中的自訂網域傳送的輸出電子郵件</span><span class="sxs-lookup"><span data-stu-id="11bfd-103">Use DKIM to validate outbound email sent from your custom domain in Office 365</span></span>

 <span data-ttu-id="11bfd-104">**摘要**：本文說明如何在 Office 365 中使用網域金鑰識別郵件 (DKIM)，以確保目的地電子郵件系統會信任從您的自訂網域對外傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="11bfd-104">**Summary:** This article describes how you use DomainKeys Identified Mail (DKIM) with Office 365 to ensure that destination email systems trust messages sent outbound from your custom domain.</span></span> 
  
<span data-ttu-id="11bfd-105">除了 SPF 和 DMARC 以外，您也應使用 DKIM，以避免詐騙程式傳送看似來自您的網域的郵件。</span><span class="sxs-lookup"><span data-stu-id="11bfd-105">You should use DKIM in addition to SPF and DMARC to help prevent spoofers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="11bfd-106">DKIM 可讓您在郵件標頭中將數位簽章新增到電子郵件訊息中。</span><span class="sxs-lookup"><span data-stu-id="11bfd-106">DKIM lets you add a digital signature to email messages in the message header.</span></span> <span data-ttu-id="11bfd-107">聽起來很複雜，但實則不然。</span><span class="sxs-lookup"><span data-stu-id="11bfd-107">Sounds complicated, but it's really not.</span></span> <span data-ttu-id="11bfd-108">在設定 DKIM 時，您會授權給網域，使其能夠使用密碼編譯驗證將其名稱簽署至電子郵件訊息，或建立關聯。</span><span class="sxs-lookup"><span data-stu-id="11bfd-108">When you configure DKIM, you authorize your domain to associate, or sign, its name to an email message by using cryptographic authentication.</span></span> <span data-ttu-id="11bfd-109">電子郵件系統在接收來自您網域的電子郵件時，可以利用此數位簽章來判斷所接收的內送電子郵件是否合法。</span><span class="sxs-lookup"><span data-stu-id="11bfd-109">Email systems that receive email from your domain can use this digital signature to help determine if incoming email that they receive is legitimate.</span></span>
  
<span data-ttu-id="11bfd-110">基本上，您可以使用私密金鑰為網域的外寄電子郵件中的標頭加密。</span><span class="sxs-lookup"><span data-stu-id="11bfd-110">Basically, you use a private key to encrypt the header in your domain's outgoing email.</span></span> <span data-ttu-id="11bfd-111">您可以將公開金鑰發佈至網域的 DNS 記錄，讓接收端伺服器用來解碼簽章。</span><span class="sxs-lookup"><span data-stu-id="11bfd-111">You publish a public key to your domain's DNS records that receiving servers can then use to decode the signature.</span></span> <span data-ttu-id="11bfd-112">他們可以使用公開金鑰來確認郵件確實來自於您，而不是他人冒充您的網域寄來的。</span><span class="sxs-lookup"><span data-stu-id="11bfd-112">They use the public key to verify that the messages are really coming from you and not coming from someone spoofing your domain.</span></span>
  
<span data-ttu-id="11bfd-113">Office 365 會自動為初始網域設定 DKIM。</span><span class="sxs-lookup"><span data-stu-id="11bfd-113">Office 365 automatically sets up DKIM for initial domains.</span></span> <span data-ttu-id="11bfd-114">初始網域是 Office 365 在您註冊服務時為您建立的網域，例如 contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="11bfd-114">The initial domain is the domain that Office 365 created for you when you signed up with the service, for example, contoso.onmicrosoft.com.</span></span> <span data-ttu-id="11bfd-115">您不需要執行任何操作，即可為初始網域設定 DKIM。</span><span class="sxs-lookup"><span data-stu-id="11bfd-115">You don't need to do anything to set up DKIM for your initial domain.</span></span> <span data-ttu-id="11bfd-116">如需網域的詳細資訊，請參閱[網域的常見問題集](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain)。</span><span class="sxs-lookup"><span data-stu-id="11bfd-116">For more information about external relay domains, see [Accepted Domains](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain).</span></span>
  
<span data-ttu-id="11bfd-117">您也可以選擇不為自訂網域進行任何 DKIM 設定。</span><span class="sxs-lookup"><span data-stu-id="11bfd-117">You can choose to do nothing about DKIM for your custom domain too.</span></span> <span data-ttu-id="11bfd-118">如果您未替自訂網域設定 DKIM，Office 365 將會為您的自訂網域建立私密和公開金鑰組、啟用 DKIM 簽章，並設定 Office 365 預設原則。</span><span class="sxs-lookup"><span data-stu-id="11bfd-118">If you do not set up DKIM for your custom domain, Office 365 creates a private and public key pair, enables DKIM signing, and then configures the Office 365 default policy for your custom domain.</span></span> <span data-ttu-id="11bfd-119">雖然這對大部分的 Office 365 客戶而言已足勘使用，但在下列情況下，您仍應手動為自訂網域設定 DKIM：</span><span class="sxs-lookup"><span data-stu-id="11bfd-119">While this is sufficient coverage for most Office 365 customers, you should manually configure DKIM for your custom domain in the following circumstances:</span></span>
  
- <span data-ttu-id="11bfd-120">您在 Office 365 中有多個自訂網域</span><span class="sxs-lookup"><span data-stu-id="11bfd-120">You have more than one custom domain in Office 365</span></span>
    
- <span data-ttu-id="11bfd-121">您也將設定 DMARC (建議選項)</span><span class="sxs-lookup"><span data-stu-id="11bfd-121">You're going to set up DMARC too (recommended)</span></span>
    
- <span data-ttu-id="11bfd-122">您想要控管私密金鑰</span><span class="sxs-lookup"><span data-stu-id="11bfd-122">You want control over your private key</span></span>
    
- <span data-ttu-id="11bfd-123">您想要自訂 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="11bfd-123">You want to customize your CNAME records</span></span>
    
- <span data-ttu-id="11bfd-124">您想要為來自於第三方網域的電子郵件設定 DKIM，例如，當您使用第三方大量郵件寄件者時。</span><span class="sxs-lookup"><span data-stu-id="11bfd-124">You want to set up DKIM keys for email originating out of a third-party domain, for example, if you use a third-party bulk mailer.</span></span>
    
<span data-ttu-id="11bfd-125">本文內容：</span><span class="sxs-lookup"><span data-stu-id="11bfd-125">In this article:</span></span>
  
- [<span data-ttu-id="11bfd-126">DKIM 在 Office 365 中防止惡意詐騙的效用為何優於單獨使用 SPF</span><span class="sxs-lookup"><span data-stu-id="11bfd-126">How DKIM works better than SPF alone to prevent malicious spoofing in Office 365</span></span>](use-dkim-to-validate-outbound-email.md#HowDKIMWorks)
    
- [<span data-ttu-id="11bfd-127">在 Office 365 中手動設定 DKIM 時需執行哪些作業</span><span class="sxs-lookup"><span data-stu-id="11bfd-127">What you need to do to manually set up DKIM in Office 365</span></span>](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)
    
- [<span data-ttu-id="11bfd-128">為 Office 365 中的多個自訂網域設定 DKIM</span><span class="sxs-lookup"><span data-stu-id="11bfd-128">To configure DKIM for more than one custom domain in Office 365</span></span>](use-dkim-to-validate-outbound-email.md#DKIMMultiDomain)
    
- [<span data-ttu-id="11bfd-129">在 Office 365 中停用自訂網域 DKIM 簽署原則</span><span class="sxs-lookup"><span data-stu-id="11bfd-129">Disabling the DKIM signing policy for a custom domain in Office 365</span></span>](use-dkim-to-validate-outbound-email.md#DisableDKIMSigningPolicy)
    
- <span data-ttu-id="11bfd-130">[DKIM 和 Office 365 的預設行為](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)</span><span class="sxs-lookup"><span data-stu-id="11bfd-130">For more information about this signature, see [Default behavior for DKIM and Office 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span></span>
    
- [<span data-ttu-id="11bfd-131">設定 DKIM，讓第三方服務可代表您的自訂網域傳送 (或偽造) 電子郵件</span><span class="sxs-lookup"><span data-stu-id="11bfd-131">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>](use-dkim-to-validate-outbound-email.md#SetUp3rdPartyspoof)
    
- <span data-ttu-id="11bfd-132">[後續步驟：為 Office 365 設定 DKIM 之後](use-dkim-to-validate-outbound-email.md#DKIMNextSteps)</span><span class="sxs-lookup"><span data-stu-id="11bfd-132">[](use-dkim-to-validate-outbound-email.md#DKIMNextSteps)Next steps: After you set up SPF for Office 365</span></span>
    
## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing-in-office-365"></a><span data-ttu-id="11bfd-133">DKIM 在 Office 365 中防止惡意詐騙的效用為何優於單獨使用 SPF</span><span class="sxs-lookup"><span data-stu-id="11bfd-133">How DKIM works better than SPF alone to prevent malicious spoofing in Office 365</span></span>
<span data-ttu-id="11bfd-134"><a name="HowDKIMWorks"> </a></span><span class="sxs-lookup"><span data-stu-id="11bfd-134"></span></span>

<span data-ttu-id="11bfd-135">SPF 會在郵件信封中新增資訊，但 DKIM 則會為郵件標頭中的簽章加密。</span><span class="sxs-lookup"><span data-stu-id="11bfd-135">SPF adds information to a message envelope but DKIM actually encrypts a signature within the message header.</span></span> <span data-ttu-id="11bfd-136">當您轉寄郵件時，轉寄端伺服器可能會將該郵件信封的某些部分移除掉。</span><span class="sxs-lookup"><span data-stu-id="11bfd-136">When you forward a message, portions of that message's envelope can be stripped away by the forwarding server.</span></span> <span data-ttu-id="11bfd-137">由於數位簽章是電子郵件標頭的一部分，會存留在電子郵件訊息內，因此即使郵件已轉寄，DKIM 仍可運作，如下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="11bfd-137">Since the digital signature stays with the email message because it's part of the email header, DKIM works even when a message has been forwarded as shown in the following example.</span></span>
  
![流程圖顯示當 SPF 檢查不通過時，轉送的訊息會傳遞 DKIM 驗證](media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)
  
<span data-ttu-id="11bfd-139">在此範例中，如果您只為您的網域發佈 SPF TXT 記錄，收件者的郵件伺服器可能會將您的電子郵件標示為垃圾郵件，並產生誤判的結果。</span><span class="sxs-lookup"><span data-stu-id="11bfd-139">In this example, if you had only published an SPF TXT record for your domain, the recipient's mail server could have marked your email as spam and generated a false positive result.</span></span> <span data-ttu-id="11bfd-140">在此案例中，加入 DKIM 將可減少誤判垃圾郵件的報告。</span><span class="sxs-lookup"><span data-stu-id="11bfd-140">The addition of DKIM in this scenario reduces false positive spam reporting.</span></span> <span data-ttu-id="11bfd-141">由於 DKIM 也使用公開金鑰密碼編譯進行驗證，而非僅使用 IP 位址，因此我們認為 DKIM 是遠優於 SPF 的驗證形式。</span><span class="sxs-lookup"><span data-stu-id="11bfd-141">Because DKIM relies on public key cryptography to authenticate and not just IP addresses, DKIM is considered a much stronger form of authentication than SPF.</span></span> <span data-ttu-id="11bfd-142">我們建議您在部署中應同時使用 SPF 和 DKIM 以及 DMARC。</span><span class="sxs-lookup"><span data-stu-id="11bfd-142">We recommend using both SPF and DKIM, as well as DMARC in your deployment.</span></span>
  
<span data-ttu-id="11bfd-143">重要事實：DKIM 會使用私密金鑰將加密的簽章插入郵件標頭中。</span><span class="sxs-lookup"><span data-stu-id="11bfd-143">The nitty gritty: DKIM uses a private key to insert an encrypted signature into the message headers.</span></span> <span data-ttu-id="11bfd-144">登入網域 (或輸出網域) 會在標頭中插入作為 **d=** 欄位的值。</span><span class="sxs-lookup"><span data-stu-id="11bfd-144">The signing domain, or outbound domain, is inserted as the value of the **d=** field in the header.</span></span> <span data-ttu-id="11bfd-145">驗證網域 (或收件者網域) 隨後會使用 **d=** 欄位來查閱來自 DNS 的公開金鑰，並驗證郵件。</span><span class="sxs-lookup"><span data-stu-id="11bfd-145">The verifying domain, or recipient's domain, then use the **d=** field to look up the public key from DNS and authenticate the message.</span></span> <span data-ttu-id="11bfd-146">如果郵件通過驗證，即通過 DKIM 檢查。</span><span class="sxs-lookup"><span data-stu-id="11bfd-146">If the message is verified, the DKIM check passes.</span></span> 
  
## <a name="what-you-need-to-do-to-manually-set-up-dkim-in-office-365"></a><span data-ttu-id="11bfd-147">在 Office 365 中手動設定 DKIM 時需執行哪些作業</span><span class="sxs-lookup"><span data-stu-id="11bfd-147">What you need to do to manually set up DKIM in Office 365</span></span>
<span data-ttu-id="11bfd-148"><a name="SetUpDKIMO365"> </a></span><span class="sxs-lookup"><span data-stu-id="11bfd-148"></span></span>

<span data-ttu-id="11bfd-149">若要設定 DKIM，您應完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="11bfd-149">To configure DKIM, you will complete these steps:</span></span>
  
- [<span data-ttu-id="11bfd-150">將兩個 CNAME 記錄發佈至您在 DNS 中的自訂網域</span><span class="sxs-lookup"><span data-stu-id="11bfd-150">Publish two CNAME records for your custom domain in DNS</span></span>](use-dkim-to-validate-outbound-email.md#Publish2CNAME)
    
- <span data-ttu-id="11bfd-151">[為 Office 365 中的自訂網域啟用 DKIM 簽署](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)</span><span class="sxs-lookup"><span data-stu-id="11bfd-151">[](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)Step 3: Set up DKIM for your custom domain in Office 365</span></span>
    
### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a><span data-ttu-id="11bfd-152">將兩個 CNAME 記錄發佈至您在 DNS 中的自訂網域</span><span class="sxs-lookup"><span data-stu-id="11bfd-152">Publish two CNAME records for your custom domain in DNS</span></span>
<span data-ttu-id="11bfd-153"><a name="Publish2CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="11bfd-153"></span></span>

<span data-ttu-id="11bfd-154">對於要在 DNS 中新增 DKIM 簽章的每個網域，您必須發佈兩個 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="11bfd-154">For each domain for which you want to add a DKIM signature in DNS, you need to publish two CNAME records.</span></span> 

<span data-ttu-id="11bfd-155">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="11bfd-155">Run the following command:</span></span>    
   
    New-DkimSigningConfig -DomainName <domain> -Enabled $false
       
    Get-DkimSigningConfig -DomainName domain | fl Selector1CNAME, Selector2CNAME
    
<span data-ttu-id="11bfd-156">建立在 Get-DkimSigningConfig 輸出中參考的 CNAME</span><span class="sxs-lookup"><span data-stu-id="11bfd-156">Create CNAMEs referenced in Get-DkimSigningConfig output</span></span>
    
    Set-DkimSigningConfig -DomainName domain -Enabled $true
    
<span data-ttu-id="11bfd-157">您 DNS 中的 CNAME 記錄會指向已建立、且 Office 365 的 Microsoft DNS 伺服器的 DNS 中已有的 A 記錄。</span><span class="sxs-lookup"><span data-stu-id="11bfd-157">The CNAME records in your DNS will point to already created A records that exist in DNS on the Microsoft DNS servers for Office 365.</span></span>
  
<span data-ttu-id="11bfd-158">Office 365 會自動使用您建立的兩個記錄執行自動金鑰輪換。</span><span class="sxs-lookup"><span data-stu-id="11bfd-158">Office 365 performs automatic key rotation using the two records that you establish.</span></span> <span data-ttu-id="11bfd-159">如果您在 Office 365 中除了初始網域以外也佈建了自訂網域，則必須為每個額外的網域發佈兩個 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="11bfd-159">If you have provisioned custom domains in addition to the initial domain in Office 365, you must publish two CNAME records for each additional domain.</span></span> <span data-ttu-id="11bfd-160">因此，如果您有兩個網域，您必須發佈兩個額外的 CNAME 記錄，依此類推。</span><span class="sxs-lookup"><span data-stu-id="11bfd-160">So, if you have two domains, you must publish two additional CNAME records, and so on.</span></span>
  
<span data-ttu-id="11bfd-161">CNAME 記錄應使用下列格式。</span><span class="sxs-lookup"><span data-stu-id="11bfd-161">Use the following format for the CNAME records.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="11bfd-162">如果您是我們的 GCC High 客戶，我們會以不同的方式計算 _domainGuid_！</span><span class="sxs-lookup"><span data-stu-id="11bfd-162">If you are one of our GCC High customers, we calculate _domainGuid_ differently!</span></span> <span data-ttu-id="11bfd-163">我們在計算 _domainGuid_ 時不會查閱您 _initialDomain_ 的 MX 記錄，而是會直接從自訂的網域計算。</span><span class="sxs-lookup"><span data-stu-id="11bfd-163">Instead of looking up the MX record for your _initialDomain_ to calculate _domainGuid_, instead we calculate it directly from the customized domain.</span></span> <span data-ttu-id="11bfd-164">例如，如果您的自訂網域是 "contoso.com"，則您的 domainGuid 會變成 "contoso-com"，任何句點都會取代為虛線。</span><span class="sxs-lookup"><span data-stu-id="11bfd-164">For example, if your customized domain is “contoso.com” your domainGuid becomes “contoso-com”, any periods are replaced with a dash.</span></span> <span data-ttu-id="11bfd-165">因此，無論您的 initialDomain 指向哪個 MX 記錄，您都將一律使用上述方法來計算在您的 CNAME 記錄中使用的 domainGuid。</span><span class="sxs-lookup"><span data-stu-id="11bfd-165">So, regardless of what MX record your initialDomain points to, you’ll always use the above method to calculate the domainGuid to use in your CNAME records.</span></span>

  
```
Host name:          selector1._domainkey
Points to address or value: selector1-<domainGUID>._domainkey.<initialDomain> 
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: selector2-<domainGUID>._domainkey.<initialDomain> 
TTL:                3600
```

<span data-ttu-id="11bfd-166">其中：</span><span class="sxs-lookup"><span data-stu-id="11bfd-166">Where:</span></span>
  
- <span data-ttu-id="11bfd-167">Office 365 的選取器將一律為 "selector1" 或 "selector2"。</span><span class="sxs-lookup"><span data-stu-id="11bfd-167">For Office 365, the selectors will always be "selector1" or "selector2".</span></span> 
    
- <span data-ttu-id="11bfd-168">_domainGUID_ 會與您自訂網域的自訂 MX 記錄中顯示於 mail.protection.outlook.com 前面的 _domainGUID_ 相同。</span><span class="sxs-lookup"><span data-stu-id="11bfd-168">_domainGUID_ is the same as the _domainGUID_ in the customized MX record for your custom domain that appears before mail.protection.outlook.com.</span></span> <span data-ttu-id="11bfd-169">例如，在網域 contoso.com 的下列 MX 記錄中，_domainGUID_ 為 contoso-com：</span><span class="sxs-lookup"><span data-stu-id="11bfd-169">For example, in the following MX record for the domain contoso.com, the _domainGUID_ is contoso-com:</span></span> 
    
    ```
    contoso.com.  3600  IN  MX   5 contoso-com.mail.protection.outlook.com
    ```

- <span data-ttu-id="11bfd-170">_initialDomain_ 是您註冊 Office 365 時所使用的網域。</span><span class="sxs-lookup"><span data-stu-id="11bfd-170">_initialDomain_ is the domain that you used when you signed up for Office 365.</span></span> <span data-ttu-id="11bfd-171">初始網域的結尾一律為 onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="11bfd-171">Initial domains always end in onmicrosoft.com.</span></span> <span data-ttu-id="11bfd-172">如需如何判斷初始網域的相關資訊，請參閱[網域的常見問題集](https://support.office.com/article/1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain)。</span><span class="sxs-lookup"><span data-stu-id="11bfd-172">For information about determining your initial domain, see [Domains FAQ](https://support.office.com/article/1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain).</span></span>
    
<span data-ttu-id="11bfd-173">例如，如果您的初始網域為 cohovineyardandwinery.onmicrosoft.com，並且有兩個自訂網域 cohovineyard.com 和 cohowinery.com，則必須為每個額外的網域各設定兩個 CNAME 記錄，因此共計四個 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="11bfd-173">For example, if you have an initial domain of cohovineyardandwinery.onmicrosoft.com, and two custom domains cohovineyard.com and cohowinery.com, you would need to set up two CNAME records for each additional domain, for a total of four CNAME records.</span></span>
  
```
Host name:          selector1._domainkey
Points to address or value: selector1-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: selector2-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:          selector1._domainkey
Points to address or value: selector1-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com 
TTL:                3600
 
Host name:          selector2._domainkey
Points to address or value: selector2-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com 
TTL:                3600
```

### <a name="enable-dkim-signing-for-your-custom-domain-in-office-365"></a><span data-ttu-id="11bfd-174">為 Office 365 中的自訂網域啟用 DKIM 簽署</span><span class="sxs-lookup"><span data-stu-id="11bfd-174">Step 3: Set up DKIM for your custom domain in Office 365</span></span>
<span data-ttu-id="11bfd-175"><a name="EnableDKIMinO365"> </a></span><span class="sxs-lookup"><span data-stu-id="11bfd-175"></span></span>

<span data-ttu-id="11bfd-176">在 DNS 中發佈 CNAME 記錄後，您即可透過 Office 365 啟用 DKIM 簽署。</span><span class="sxs-lookup"><span data-stu-id="11bfd-176">Once you have published the CNAME records in DNS, you are ready to enable DKIM signing through Office 365.</span></span> <span data-ttu-id="11bfd-177">您可以透過 Microsoft 365 系統管理中心或使用 PowerShell 來執行此作業。</span><span class="sxs-lookup"><span data-stu-id="11bfd-177">You can do this either through the Microsoft 365 admin center or by using PowerShell.</span></span>
  
#### <a name="to-enable-dkim-signing-for-your-custom-domain-through-the-admin-center"></a><span data-ttu-id="11bfd-178">透過系統管理中心為自訂網域啟用 DKIM 簽署</span><span class="sxs-lookup"><span data-stu-id="11bfd-178">To enable DKIM signing for your custom domain through the admin center</span></span>

1. <span data-ttu-id="11bfd-179">以工作或學校帳戶[登入 Office 365](https://support.office.microsoft.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="11bfd-179">[Sign in to Office 365](https://support.office.microsoft.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) with your work or school account.</span></span> 
    
2. <span data-ttu-id="11bfd-180">選取左上角的應用程式啟動器圖示，然後選擇 [管理員]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="11bfd-180">Select the app launcher icon in the upper-left and choose **Admin**.</span></span>
    
3. <span data-ttu-id="11bfd-181">在導覽的左下角展開 [管理員]\*\*\*\*，然後選擇 [Exchange]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="11bfd-181">In the lower-left navigation, expand **Admin** and choose **Compliance**.</span></span>
    
4. <span data-ttu-id="11bfd-182">移至 [保護]\*\*\*\* \> [dkim]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="11bfd-182">Go to **Protection** \> **dkim**.</span></span>
    
5. <span data-ttu-id="11bfd-183">選取要啟用 DKIM 的網域，然後，針對 [使用 DKIM 簽章簽署此網域的郵件]\*\*\*\*，選擇 [啟用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="11bfd-183">Select the domain for which you want to enable DKIM and then, for **Sign messages for this domain with DKIM signatures**, choose **Enable**.</span></span> <span data-ttu-id="11bfd-184">對每個自訂網域重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="11bfd-184">Repeat this step for each custom domain.</span></span>
    
#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a><span data-ttu-id="11bfd-185">使用 PowerShell 為自訂網域啟用 DKIM 簽署</span><span class="sxs-lookup"><span data-stu-id="11bfd-185">To enable DKIM signing for your custom domain by using PowerShell</span></span>

1. <span data-ttu-id="11bfd-186">[連線至 Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289.aspx) (機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="11bfd-186">[Connect to Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289.aspx).</span></span>
    
2. <span data-ttu-id="11bfd-187">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="11bfd-187">Run the following command:</span></span>
    
    ```
    Set-DkimSigningConfig -DomainName <domain> -Enabled $true
    ```

   <span data-ttu-id="11bfd-188">其中，_domain_ 是要啟用 DKIM 簽署的自訂網域名稱。</span><span class="sxs-lookup"><span data-stu-id="11bfd-188">Where _domain_ is the name of the custom domain that you want to enable DKIM signing for.</span></span> 
    
   <span data-ttu-id="11bfd-189">以網域 contoso.com 為例：</span><span class="sxs-lookup"><span data-stu-id="11bfd-189">For example, for the domain contoso.com:</span></span>
    
    ```
    Set-DkimSigningConfig -DomainName contoso.com -Enabled $true
    ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-office-365"></a><span data-ttu-id="11bfd-190">確認已為 Office 365 正確設定 DKIM 簽章</span><span class="sxs-lookup"><span data-stu-id="11bfd-190">To Confirm DKIM signing is configured properly for Office 365</span></span>

<span data-ttu-id="11bfd-191">請稍待幾分鐘，再依照下列步驟來確認您已正確設定 DKIM。</span><span class="sxs-lookup"><span data-stu-id="11bfd-191">Wait a few minutes before you follow these steps to confirm that you have properly configured DKIM.</span></span> <span data-ttu-id="11bfd-192">這可讓關於網域的 DKIM 資訊有時間散佈到整個網路。</span><span class="sxs-lookup"><span data-stu-id="11bfd-192">This allows time for the DKIM information about the domain to be spread throughout the network.</span></span>
  
- <span data-ttu-id="11bfd-193">從已啟用 Office 365 DKIM 的網域內包含的帳戶，傳送郵件到另一個電子郵件帳戶，例如 outlook.com 或 Hotmail.com。</span><span class="sxs-lookup"><span data-stu-id="11bfd-193">Send a message from an account within your Office 365 DKIM-enabled domain to another email account such as outlook.com or Hotmail.com.</span></span>
    
- <span data-ttu-id="11bfd-194">請勿使用 aol.com 帳戶進行測試。</span><span class="sxs-lookup"><span data-stu-id="11bfd-194">Do not use an aol.com account for testing purposes.</span></span> <span data-ttu-id="11bfd-195">在通過 SPF 檢查的情況下，AOL 可能會略過 DKIM 檢查。</span><span class="sxs-lookup"><span data-stu-id="11bfd-195">AOL may skip the DKIM check if the SPF check passes.</span></span> <span data-ttu-id="11bfd-196">這將使您的測試失去效用。</span><span class="sxs-lookup"><span data-stu-id="11bfd-196">This will nullify your test.</span></span>
    
- <span data-ttu-id="11bfd-197">開啟郵件並查看標頭。</span><span class="sxs-lookup"><span data-stu-id="11bfd-197">Open the message and look at the header.</span></span> <span data-ttu-id="11bfd-198">檢視郵件標頭的指示會隨著您的郵件用戶端而不同。</span><span class="sxs-lookup"><span data-stu-id="11bfd-198">Instructions for viewing the header for the message will vary depending on your messaging client.</span></span> <span data-ttu-id="11bfd-199">如需在 Outlook 中檢視郵件標題的相關指示，請參閱[檢視電子郵件訊息標頭](https://support.office.com/article/CD039382-DC6E-4264-AC74-C048563D212C)。</span><span class="sxs-lookup"><span data-stu-id="11bfd-199">For instructions on viewing message headers in Outlook, see [View e-mail message headers](https://support.office.com/article/CD039382-DC6E-4264-AC74-C048563D212C).</span></span>

  <span data-ttu-id="11bfd-200">DKIM 簽署的郵件會包含您在發佈 CNAME 項目時所定義的主機名稱和網域。</span><span class="sxs-lookup"><span data-stu-id="11bfd-200">The DKIM-signed message will contain the host name and domain you defined when you published the CNAME entries.</span></span> <span data-ttu-id="11bfd-201">郵件會如下列範例所示：</span><span class="sxs-lookup"><span data-stu-id="11bfd-201">The message will look something like this example:</span></span> 
    
    ```
    From: Example User <example@contoso.com> 
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed; 
        s=selector1; d=contoso.com; t=1429912795; 
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type; 
        bh=<body hash>; 
        b=<signed field>;
    ```

- <span data-ttu-id="11bfd-202">查看 Authentication-Results 標頭。</span><span class="sxs-lookup"><span data-stu-id="11bfd-202">Look for the Authentication-Results header.</span></span> <span data-ttu-id="11bfd-203">雖然每個接收服務分別使用稍有不同的格式為內送郵件加上戳記，但結果應會包含類似於 **DKIM=pass** 或 **DKIM=OK** 的項目。</span><span class="sxs-lookup"><span data-stu-id="11bfd-203">While each receiving service uses a slightly different format to stamp the incoming mail, the result should include something like **DKIM=pass** or **DKIM=OK**.</span></span> 
    
## <a name="to-configure-dkim-for-more-than-one-custom-domain-in-office-365"></a><span data-ttu-id="11bfd-204">為 Office 365 中的多個自訂網域設定 DKIM</span><span class="sxs-lookup"><span data-stu-id="11bfd-204">To configure DKIM for more than one custom domain in Office 365</span></span>
<span data-ttu-id="11bfd-205"><a name="DKIMMultiDomain"> </a></span><span class="sxs-lookup"><span data-stu-id="11bfd-205"></span></span>

<span data-ttu-id="11bfd-206">如果您日後決定要新增另一個自訂網域，且您想要為新的網域啟用 DKIM，您必須為每個網域完成本文所述的步驟。</span><span class="sxs-lookup"><span data-stu-id="11bfd-206">If at some point in the future you decide to add another custom domain and you want to enable DKIM for the new domain, you must complete the steps in this article for each domain.</span></span> <span data-ttu-id="11bfd-207">明確而言，請完成[在 Office 365 中手動設定 DKIM 時需執行哪些作業](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)中的所有步驟。</span><span class="sxs-lookup"><span data-stu-id="11bfd-207">Specifically, complete all steps in [What you need to do to manually set up DKIM in Office 365](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).</span></span>
  
## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain-in-office-365"></a><span data-ttu-id="11bfd-208">在 Office 365 中停用自訂網域 DKIM 簽署原則</span><span class="sxs-lookup"><span data-stu-id="11bfd-208">Disabling the DKIM signing policy for a custom domain in Office 365</span></span>
<span data-ttu-id="11bfd-209"><a name="DisableDKIMSigningPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="11bfd-209"></span></span>

<span data-ttu-id="11bfd-210">停用簽署原則並不會完全停用 DKIM。</span><span class="sxs-lookup"><span data-stu-id="11bfd-210">Disabling the signing policy does not completely disable DKIM.</span></span> <span data-ttu-id="11bfd-211">一段時間後，Office 365 會自動為您的網域套用預設的 Office 365 原則。</span><span class="sxs-lookup"><span data-stu-id="11bfd-211">After a period of time, Office 365 will automatically apply the default Office 365 policy for your domain.</span></span> <span data-ttu-id="11bfd-212">如需詳細資訊，請參閱 [DKIM 與 Office 365 的預設行為](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)。</span><span class="sxs-lookup"><span data-stu-id="11bfd-212">For more information about this signature, see [Default behavior for DKIM and Office 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span></span>
  
### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a><span data-ttu-id="11bfd-213">使用 Windows PowerShell 停用 DKIM 簽署原則</span><span class="sxs-lookup"><span data-stu-id="11bfd-213">To disable the DKIM signing policy by using Windows PowerShell</span></span>

1. <span data-ttu-id="11bfd-214">[連線至 Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289.aspx) (機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="11bfd-214">[Connect to Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289.aspx).</span></span>
    
2. <span data-ttu-id="11bfd-215">為您要停用 DKIM 簽署的每個網域執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="11bfd-215">Run one of the following commands for each domain for which you want to disable DKIM signing.</span></span>
    
    ```
    $p=Get-DkimSigningConfig -identity <domain>
    $p[0] | set-DkimSigningConfig -enabled $false
    ```

   <span data-ttu-id="11bfd-216">例如：</span><span class="sxs-lookup"><span data-stu-id="11bfd-216">For example:</span></span>
    
    ```
    $p=Get-DkimSigningConfig -identity contoso.com
    $p[0] | set-DkimSigningConfig -enabled $false
    ```

   <span data-ttu-id="11bfd-217">或</span><span class="sxs-lookup"><span data-stu-id="11bfd-217">Or</span></span>
    
    ```
    Set-DkimSigningConfig -identity $p[<number>].identity -enabled $false
    ```

    <span data-ttu-id="11bfd-218">其中，_number_ 是原則的索引。</span><span class="sxs-lookup"><span data-stu-id="11bfd-218">Where _number_ is the index of the policy.</span></span> <span data-ttu-id="11bfd-219">例如：</span><span class="sxs-lookup"><span data-stu-id="11bfd-219">For example:</span></span> 
    
    ```
    Set-DkimSigningConfig -identity $p[0].identity -enabled $false
    ```

## <a name="default-behavior-for-dkim-and-office-365"></a><span data-ttu-id="11bfd-220">DKIM 和 Office 365 的預設行為</span><span class="sxs-lookup"><span data-stu-id="11bfd-220">For more information about this signature, see Default behavior for DKIM and Office 365.</span></span>
<span data-ttu-id="11bfd-221"><a name="DefaultDKIMbehavior"> </a></span><span class="sxs-lookup"><span data-stu-id="11bfd-221"></span></span>

<span data-ttu-id="11bfd-222">若您未啟用 DKIM，Office 365 將為您的預設網域自動建立 1024 位元 DKIM 公開金鑰，我們在資料中心內部儲存的相關私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="11bfd-222">If you do not enable DKIM, Office 365 automatically creates a 1024-bit DKIM public key for your default domain and the associated private key which we store internally in our datacenter.</span></span> <span data-ttu-id="11bfd-223">根據預設，對於未設定原則的網域，Office 365 會使用預設的簽署組態。</span><span class="sxs-lookup"><span data-stu-id="11bfd-223">By default, Office 365 uses a default signing configuration for domains that do not have a policy in place.</span></span> <span data-ttu-id="11bfd-224">這表示，如果您未自行設定 DKIM，Office 365 將會使用預設原則，以及為了替您的網域啟用 DKIM 而建立的金鑰。</span><span class="sxs-lookup"><span data-stu-id="11bfd-224">This means that if you do not set up DKIM yourself, Office 365 will use its default policy and keys it creates in order to enable DKIM for your domain.</span></span>
  
<span data-ttu-id="11bfd-225">此外，如果您在啟用 DKIM 簽署後加以停用，在經過一段時間後，Office 365 將會自動為您的網域套用 Office 365 預設原則。</span><span class="sxs-lookup"><span data-stu-id="11bfd-225">Also, if you disable DKIM signing after enabling it, after a period of time, Office 365 will automatically apply the Office 365 default policy for your domain.</span></span>
  
<span data-ttu-id="11bfd-226">在下列範例中，假設 fabrikam.com 的 DKIM 是由 Office 365 所啟用，而不是網域的系統管理員所啟用的。</span><span class="sxs-lookup"><span data-stu-id="11bfd-226">In the following example, suppose that DKIM for fabrikam.com was enabled by Office 365, not by the administrator of the domain.</span></span> <span data-ttu-id="11bfd-227">這表示必要的 CNAME 不存在於 DNS 中。</span><span class="sxs-lookup"><span data-stu-id="11bfd-227">This means that the required CNAMEs do not exist in DNS.</span></span> <span data-ttu-id="11bfd-228">在來自此網域的電子郵件中，DKIM 簽章會顯示如下：</span><span class="sxs-lookup"><span data-stu-id="11bfd-228">DKIM signatures for email from this domain will look something like this:</span></span>
  
```
From: Second Example <second.example@fabrikam.com> 
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed; 
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795; 
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type; 
    bh=<body hash>; 
    b=<signed field>;
```

<span data-ttu-id="11bfd-229">在此範例中，主機名稱和網域會包含 CNAME 在網域系統管理員已為 fabrikam.com 啟用 DKIM 簽署時所將指向的值。</span><span class="sxs-lookup"><span data-stu-id="11bfd-229">In this example, the host name and domain contain the values to which the CNAME would point if DKIM-signing for fabrikam.com had been enabled by the domain administrator.</span></span> <span data-ttu-id="11bfd-230">最後，每一則從 Office 365 傳送的郵件都會由 DKIM 簽署。</span><span class="sxs-lookup"><span data-stu-id="11bfd-230">Eventually, every single message sent from Office 365 will be DKIM-signed.</span></span> <span data-ttu-id="11bfd-231">如果您自行啟用 DKIM，網域將會與「寄件者:」位址中的網域相同；在此案例中為 fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="11bfd-231">If you enable DKIM yourself, the domain will be the same as the domain in the From: address, in this case fabrikam.com.</span></span> <span data-ttu-id="11bfd-232">若未自行啟用，則網域會不同，且會改用組織的初始網域。</span><span class="sxs-lookup"><span data-stu-id="11bfd-232">If you don't, it will not align and instead will use your organization's initial domain.</span></span> <span data-ttu-id="11bfd-233">如需如何判斷初始網域的相關資訊，請參閱[網域的常見問題集](https://support.office.com/article/1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain)。</span><span class="sxs-lookup"><span data-stu-id="11bfd-233">For information about determining your initial domain, see [Domains FAQ](https://support.office.com/article/1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain).</span></span>
  
## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a><span data-ttu-id="11bfd-234">設定 DKIM，讓第三方服務可代表您的自訂網域傳送 (或偽造) 電子郵件</span><span class="sxs-lookup"><span data-stu-id="11bfd-234">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>
<span data-ttu-id="11bfd-235"><a name="SetUp3rdPartyspoof"> </a></span><span class="sxs-lookup"><span data-stu-id="11bfd-235"></span></span>

<span data-ttu-id="11bfd-236">某些大量電子郵件服務提供者或軟體即服務提供者，會允許您為來自於其服務的電子郵件設定 DKIM 金鑰。</span><span class="sxs-lookup"><span data-stu-id="11bfd-236">Some bulk email service providers, or software-as-a-service providers, let you set up DKIM keys for email that originates from their service.</span></span> <span data-ttu-id="11bfd-237">若要設定所需的 DNS 記錄，您必須與第三方提供者進行協調。</span><span class="sxs-lookup"><span data-stu-id="11bfd-237">This requires coordination between yourself and the third-party in order to set up the necessary DNS records.</span></span> <span data-ttu-id="11bfd-238">每個組織的設定方式都不盡相同。</span><span class="sxs-lookup"><span data-stu-id="11bfd-238">No two organizations do it exactly the same way.</span></span> <span data-ttu-id="11bfd-239">具體程序完全取決於組織。</span><span class="sxs-lookup"><span data-stu-id="11bfd-239">Instead, the process depends entirely on the organization.</span></span>
  
<span data-ttu-id="11bfd-240">若已為 contoso.com 和 bulkemailprovider.com 正確設定 DKIM，郵件可能會如下列範例所示：</span><span class="sxs-lookup"><span data-stu-id="11bfd-240">An example message showing a properly configured DKIM for contoso.com and bulkemailprovider.com might look like this:</span></span>
  
```
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

<span data-ttu-id="11bfd-241">在此範例中，若要達到此結果：</span><span class="sxs-lookup"><span data-stu-id="11bfd-241">In this example, in order to achieve this result:</span></span>
  
1. <span data-ttu-id="11bfd-242">大量電子郵件提供者為 Contoso 提供 DKIM 公開金鑰。</span><span class="sxs-lookup"><span data-stu-id="11bfd-242">Bulk Email Provider gave Contoso a public DKIM key.</span></span>
    
2. <span data-ttu-id="11bfd-243">Contoso 將 DKIM 金鑰發佈至其 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="11bfd-243">Contoso published the DKIM key to its DNS record.</span></span>
    
3. <span data-ttu-id="11bfd-244">傳送電子郵件時，大量電子郵件提供者以對應的私密金鑰簽署金鑰。</span><span class="sxs-lookup"><span data-stu-id="11bfd-244">When sending email, Bulk Email Provider signs the key with the corresponding private key.</span></span> <span data-ttu-id="11bfd-245">藉由此動作，大量電子郵件提供者將 DKIM 簽署附加至郵件標頭。</span><span class="sxs-lookup"><span data-stu-id="11bfd-245">By doing so, Bulk Email Provider attached the DKIM signature to the message header.</span></span>
    
4. <span data-ttu-id="11bfd-246">接收端電子郵件系統針對郵件的「寄件者:」(5322.From) 位址驗證 DKIM-Signature d=\<domain\> 值，以執行 DKIM 檢查。</span><span class="sxs-lookup"><span data-stu-id="11bfd-246">Receiving email systems perform a DKIM check by authenticating the DKIM-Signature d=\<domain\> value against the domain in the From: (5322.From) address of the message.</span></span> <span data-ttu-id="11bfd-247">在此範例中，這些值符合：</span><span class="sxs-lookup"><span data-stu-id="11bfd-247">In this example, the following values are used:</span></span>
    
    <span data-ttu-id="11bfd-248">sender@**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="11bfd-248">sender@**contoso.com**</span></span>
    
    <span data-ttu-id="11bfd-249">d=**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="11bfd-249">d=**contoso.com**</span></span>
    
## <a name="next-steps-after-you-set-up-dkim-for-office-365"></a><span data-ttu-id="11bfd-250">後續步驟：為 Office 365 設定 DKIM 之後</span><span class="sxs-lookup"><span data-stu-id="11bfd-250">Next steps: After you set up SPF for Office 365</span></span>
<span data-ttu-id="11bfd-251"><a name="DKIMNextSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="11bfd-251"></span></span>

<span data-ttu-id="11bfd-252">雖然 DKIM 可協助您防範詐騙，但 DKIM 與 SPF 和 DMARC 搭配運作時，效果會更好。</span><span class="sxs-lookup"><span data-stu-id="11bfd-252">Although DKIM is designed to help prevent spoofing, DKIM works better with SPF and DMARC.</span></span> <span data-ttu-id="11bfd-253">設定 DKIM 之後，如果您尚未設定 SPF，應加以設定。</span><span class="sxs-lookup"><span data-stu-id="11bfd-253">Once you have set up DKIM, if you have not already set up SPF you should do so.</span></span> <span data-ttu-id="11bfd-254">如需 SPF 的快速簡介並快速設定，請參閱[在 Office 365 中設定 SPF 以協助防止詐騙](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。</span><span class="sxs-lookup"><span data-stu-id="11bfd-254">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="11bfd-255">如需更深入了解 Office 365 如何使用 SPF 或是進行疑難排解或非標準的部署 (例如混合式部署)，請先參閱 [Office 365 如何使用寄件者原則架構 (SPF) 防止詐騙](how-office-365-uses-spf-to-prevent-spoofing.md)。</span><span class="sxs-lookup"><span data-stu-id="11bfd-255">For a more in-depth understanding of how Office 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="11bfd-256">接下來，請參閱[在 Office 365 中使用 DMARC 來驗證電子郵件](use-dmarc-to-validate-email.md)。</span><span class="sxs-lookup"><span data-stu-id="11bfd-256">Next, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="11bfd-257">[反垃圾郵件訊息標頭](anti-spam-message-headers.md)包含 Office 365 針對 DKIM 檢查所使用的語法及標頭欄位。</span><span class="sxs-lookup"><span data-stu-id="11bfd-257">[Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Office 365 for DMARC checks.</span></span> 
  

