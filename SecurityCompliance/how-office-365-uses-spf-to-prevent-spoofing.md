---
title: Office 365 可防止詐騙所使用的寄件者原則架構 (SPF)
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 12/15/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3aff33c5-1416-4867-a23b-e0c0c5b4d2be
ms.collection:
- M365-security-compliance
description: 摘要： 本文說明如何 Office 365 使用 DNS 中以確定目的地的電子郵件系統信任從自訂網域傳送的郵件寄件者原則架構 (SPF) TXT 記錄。這適用於從 Office 365 傳送的輸出郵件。從 Office 365 傳送至 Office 365 中的收件者的郵件將會一律傳遞 SPF。
ms.openlocfilehash: 76267f89744b696185022a2bb036dcde09dfcde5
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30276103"
---
# <a name="how-office-365-uses-sender-policy-framework-spf-to-prevent-spoofing"></a><span data-ttu-id="fa380-105">Office 365 可防止詐騙所使用的寄件者原則架構 (SPF)</span><span class="sxs-lookup"><span data-stu-id="fa380-105">How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing</span></span>

 <span data-ttu-id="fa380-p102">**摘要：** 本文說明如何 Office 365 使用 DNS 中以確定目的地的電子郵件系統信任從自訂網域傳送的郵件寄件者原則架構 (SPF) TXT 記錄。這適用於從 Office 365 傳送的輸出郵件。從 Office 365 傳送至 Office 365 中的收件者的郵件將會一律傳遞 SPF。</span><span class="sxs-lookup"><span data-stu-id="fa380-p102">**Summary:** This article describes how Office 365 uses the Sender Policy Framework (SPF) TXT record in DNS to ensure that destination email systems trust messages sent from your custom domain. This applies to outbound mail sent from Office 365. Messages sent from Office 365 to a recipient within Office 365 will always pass SPF.</span></span> 
  
<span data-ttu-id="fa380-p103">SPF TXT 記錄會是確認送出的電子郵件的網域名稱的 DNS 記錄，以協助防止詐騙和網路釣魚。SPF 驗證確認對 alleged 的傳送端網域擁有者的寄件者的 IP 位址的電子郵件訊息的原點而言。</span><span class="sxs-lookup"><span data-stu-id="fa380-p103">An SPF TXT record is a DNS record that helps prevent spoofing and phishing by verifying the domain name from which email messages are sent. SPF validates the origin of email messages by verifying the IP address of the sender against the alleged owner of the sending domain.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="fa380-p104">SPF 記錄類型已在 2014年中取代由網際網路工程工作強制 (IETF)。而是確定在 DNS 中使用 TXT 記錄，發佈 SPF 資訊。本文的其餘部分使用清楚字詞 SPF TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="fa380-p104">SPF record types were deprecated by the Internet Engineering Task Force (IETF) in 2014. Instead, ensure that you use TXT records in DNS to publish your SPF information. The rest of this article uses the term SPF TXT record for clarity.</span></span> 
  
<span data-ttu-id="fa380-p105">網域系統管理員在 DNS 中的 TXT 記錄中發佈 SPF 資訊。SPF 資訊會識別授權的外寄電子郵件伺服器。目的地的電子郵件系統確認郵件來自已授權的外寄電子郵件伺服器。如果您已熟悉 SPF，或具有簡單的部署，並只需要知道要併入的 Office 365 的 DNS 中將 SPF TXT 記錄項目，您可以前往[SPF 避免詐騙的 Office 365 中設定](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。如果您沒有為 Office 365 中完全託管的部署或您想 SPF 的運作方式或如何疑難排解 Office 365 SPF、 保留讀取的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="fa380-p105">Domain administrators publish SPF information in TXT records in DNS. The SPF information identifies authorized outbound email servers. Destination email systems verify that messages originate from authorized outbound email servers. If you are already familiar with SPF, or you have a simple deployment, and just need to know what to include in your SPF TXT record in DNS for Office 365, you can go to [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md). If you do not have a deployment that is fully-hosted in Office 365, or you want more information about how SPF works or how to troubleshoot SPF for Office 365, keep reading.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fa380-p106">之前，您都將不同的 SPF TXT 記錄新增至自訂網域也使用 SharePoint Online。已不再需要。這項變更應減少結束的垃圾郵件] 資料夾中的 SharePoint Online 通知訊息的風險。您不需要進行任何變更立即，但如果您收到"太多查閱服務 」 錯誤，請修改 SPF TXT 記錄[設定 SPF 避免詐騙的 Office 365 中](set-up-spf-in-office-365-to-help-prevent-spoofing.md)所述。</span><span class="sxs-lookup"><span data-stu-id="fa380-p106">Previously, you had to add a different SPF TXT record to your custom domain if you also used SharePoint Online. This is no longer required. This change should reduce the risk of SharePoint Online notification messages ending up in the Junk Email folder. You do not need to make any changes immediately, but if you receive the "too many lookups" error, modify your SPF TXT record as described in [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> 
     
## <a name="how-spf-works-to-prevent-spoofing-and-phishing-in-office-365"></a><span data-ttu-id="fa380-123">若要防止詐騙及 Office 365 中的網路釣魚 SPF 的運作方式</span><span class="sxs-lookup"><span data-stu-id="fa380-123">How SPF works to prevent spoofing and phishing in Office 365</span></span>
<span data-ttu-id="fa380-124"><a name="HowSPFWorks"> </a></span><span class="sxs-lookup"><span data-stu-id="fa380-124"></span></span>

<span data-ttu-id="fa380-p107">SPF 會決定允許使用代表網域傳送的寄件者。如果寄件者不允許若要這樣做，亦即如果電子郵件失敗 SPF 檢查在接收伺服器上，在該伺服器上設定的垃圾郵件原則會決定如何處理郵件。</span><span class="sxs-lookup"><span data-stu-id="fa380-p107">SPF determines whether or not a sender is permitted to send on behalf of a domain. If the sender is not permitted to do so, that is, if the email fails the SPF check on the receiving server, the spam policy configured on that server determines what to do with the message.</span></span>
  
<span data-ttu-id="fa380-p108">每個 SPF TXT 記錄包含三個部分： 宣告很 SPF TXT 記錄，允許將郵件傳送從您的網域和可以傳送您的網域代理和強制執行規則的外部網域的 IP 位址。您需要有效的 SPF TXT 記錄中的所有三個。本文說明如何形成 SPF TXT 記錄，並提供使用 Office 365 中服務的最佳作法。若要將記錄發佈至 DNS 上使用網域註冊機構指示連結也提供。</span><span class="sxs-lookup"><span data-stu-id="fa380-p108">Each SPF TXT record contains three parts: the declaration that it is an SPF TXT record, the IP addresses that are allowed to send mail from your domain and the external domains that can send on your domain's behalf, and an enforcement rule. You need all three in a valid SPF TXT record. This article describes how you form your SPF TXT record and provides best practices for working with the services in Office 365. Links to instructions on working with your domain registrar to publish your record to DNS are also provided.</span></span>
  
### <a name="spf-basics-ip-addresses-allowed-to-send-from-your-custom-domain"></a><span data-ttu-id="fa380-131">SPF 基本概念： 傳送自訂網域從允許的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="fa380-131">SPF basics: IP addresses allowed to send from your custom domain</span></span>
<span data-ttu-id="fa380-132"><a name="SPFBasicsIPaddresses"> </a></span><span class="sxs-lookup"><span data-stu-id="fa380-132"></span></span>

<span data-ttu-id="fa380-133">請仔細 SPF 規則的基本語法：</span><span class="sxs-lookup"><span data-stu-id="fa380-133">Take a look at the basic syntax for an SPF rule:</span></span>
  
<span data-ttu-id="fa380-134">v = spf1 \<IP\> \<強制執行規則\></span><span class="sxs-lookup"><span data-stu-id="fa380-134">v=spf1 \<IP\> \<enforcement rule\></span></span>
  
<span data-ttu-id="fa380-135">例如，假設下列 SPF 規則存在 contoso.com：</span><span class="sxs-lookup"><span data-stu-id="fa380-135">For example, let's say the following SPF rule exists for contoso.com:</span></span>
  
<span data-ttu-id="fa380-136">v = spf1 \<IP 位址 #1\> \<IP 位址 #2\> \<#3 的 IP 位址\>\<強制執行規則\></span><span class="sxs-lookup"><span data-stu-id="fa380-136">v=spf1 \<IP address #1\> \<IP address #2\> \<IP address #3\> \<enforcement rule\></span></span>
  
<span data-ttu-id="fa380-137">在這個範例中，SPF 規則會指示為只接受來自網域 contoso.com 的這些 IP 位址的郵件的接收電子郵件伺服器：</span><span class="sxs-lookup"><span data-stu-id="fa380-137">In this example, the SPF rule instructs the receiving email server to only accept mail from these IP addresses for the domain contoso.com:</span></span>
  
- <span data-ttu-id="fa380-138">#1 的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="fa380-138">IP address #1</span></span>
    
- <span data-ttu-id="fa380-139">#2] 的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="fa380-139">IP address #2</span></span>
    
- <span data-ttu-id="fa380-140">#3 的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="fa380-140">IP address #3</span></span>
    
<span data-ttu-id="fa380-p109">此 SPF 規則會告知接收的電子郵件伺服器的訊息而言從 contoso.com，但不是會從一個下列三個 IP 位址，如果接收伺服器應該強制執行規則套用至郵件。強制執行規則通常是其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="fa380-p109">This SPF rule tells the receiving email server that if a message comes from contoso.com, but not from one of these three IP addresses, the receiving server should apply the enforcement rule to the message. The enforcement rule is usually one of these options:</span></span>
  
- <span data-ttu-id="fa380-p110">**完全未通過。** 使用標示郵件 '完全未通過' 郵件信封中並遵循此類型的郵件的接收伺服器設定的垃圾郵件原則。</span><span class="sxs-lookup"><span data-stu-id="fa380-p110">**Hard fail.** Mark the message with 'hard fail' in the message envelope and then follow the receiving server's configured spam policy for this type of message.</span></span> 
    
- <span data-ttu-id="fa380-p111">**柔 fail。** 標示郵件信封中的 '軟體失敗 」 的郵件。一般而言，將這些郵件傳送繼續設定電子郵件伺服器。大部分一般使用者看不到此標記。</span><span class="sxs-lookup"><span data-stu-id="fa380-p111">**Soft fail.** Mark the message with 'soft fail' in the message envelope. Typically, email servers are configured to deliver these messages anyway. Most end users do not see this mark.</span></span> 
    
- <span data-ttu-id="fa380-p112">**中性。** 不執行任何動作，也就是，不標示郵件信封。這通常是針對測試用途已保留且很少使用。</span><span class="sxs-lookup"><span data-stu-id="fa380-p112">**Neutral.** Do nothing, that is, do not mark the message envelope. This is usually reserved for testing purposes and is rarely used.</span></span> 
    
<span data-ttu-id="fa380-p113">下列範例會顯示在不同情況下 SPF 的運作方式。在下列範例中，contoso.com 是寄件者和 woodgrovebank.com 是受話方。</span><span class="sxs-lookup"><span data-stu-id="fa380-p113">The following examples show how SPF works in different situations. In these examples, contoso.com is the sender and woodgrovebank.com is the receiver.</span></span>
  
### <a name="example-1-email-authentication-of-a-message-sent-directly-from-sender-to-receiver"></a><span data-ttu-id="fa380-154">範例 1： 電子郵件驗證的直接從寄件者傳送給收件者的訊息</span><span class="sxs-lookup"><span data-stu-id="fa380-154">Example 1: Email authentication of a message sent directly from sender to receiver</span></span>
<span data-ttu-id="fa380-155"><a name="spfExample1"> </a></span><span class="sxs-lookup"><span data-stu-id="fa380-155"></span></span>

<span data-ttu-id="fa380-156">SPF 最適合時接收來自寄件者的路徑是直接，例如：</span><span class="sxs-lookup"><span data-stu-id="fa380-156">SPF works best when the path from sender to receiver is direct, for example:</span></span>
  
![流程圖顯示 SPF 如何驗證直接從伺服器傳送至伺服器的電子郵件。](media/835c20a7-ed4c-49c4-91fe-b8ebb3e452a1.jpg)
  
<span data-ttu-id="fa380-158">當 woodgrovebank.com 收到郵件 SPF TXT 記錄 contoso.com 的 IP 位址 #1 時，郵件通過 SPF 檢查並通過驗證。</span><span class="sxs-lookup"><span data-stu-id="fa380-158">When woodgrovebank.com receives the message, if IP address #1 is in the SPF TXT record for contoso.com, the message passes the SPF check and is authenticated.</span></span>
  
### <a name="example-2-spoofed-sender-address-fails-the-spf-check"></a><span data-ttu-id="fa380-159">範例 2： 詐騙寄件者地址 SPF 檢查失敗</span><span class="sxs-lookup"><span data-stu-id="fa380-159">Example 2: Spoofed sender address fails the SPF check</span></span>
<span data-ttu-id="fa380-160"><a name="spfExample2"> </a></span><span class="sxs-lookup"><span data-stu-id="fa380-160"></span></span>

<span data-ttu-id="fa380-161">假設 phisher 都會詐騙 contoso.com 的方式：</span><span class="sxs-lookup"><span data-stu-id="fa380-161">Suppose a phisher finds a way to spoof contoso.com:</span></span>
  
![流程圖顯示 SPF 如何驗證從詐騙的伺服器所傳送之電子郵件。](media/235dac3d-cdc5-466e-86e0-37b5979de198.jpg)
  
<span data-ttu-id="fa380-163">由於未 contoso.com 的 SPF TXT 記錄 IP 位址 #12，則郵件失敗 SPF 檢查並接收者可以選擇將其標示為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="fa380-163">Since IP address #12 is not in contoso.com's SPF TXT record, the message fails the SPF check and the receiver may choose to mark it as spam.</span></span>
  
### <a name="example-3-spf-and-forwarded-messages"></a><span data-ttu-id="fa380-164">範例 3： SPF 和轉寄的郵件</span><span class="sxs-lookup"><span data-stu-id="fa380-164">Example 3: SPF and forwarded messages</span></span>
<span data-ttu-id="fa380-165"><a name="spfExample3"> </a></span><span class="sxs-lookup"><span data-stu-id="fa380-165"></span></span>

<span data-ttu-id="fa380-p114">有一項缺點 SPF 是它不會處理已轉寄電子郵件時。例如，假設 woodgrovebank.com 在使用者已經將所有的電子郵件傳送至 outlook.com 帳戶設定轉接規則：</span><span class="sxs-lookup"><span data-stu-id="fa380-p114">One drawback of SPF is that it doesn't work when an email has been forwarded. For example, suppose the user at woodgrovebank.com has set up a forwarding rule to send all email to an outlook.com account:</span></span>
  
![流程圖顯示 SPF 在訊息被轉送時無法驗證電子郵件。](media/6e92acd6-463e-4a1b-8327-fb1cf861f356.jpg)
  
<span data-ttu-id="fa380-p115">郵件原本通過 SPF 檢查在 woodgrovebank.com 但因為 IP #25 不是 contoso.com 的 SPF TXT 記錄失敗在 outlook.com SPF] 核取。Outlook.com 可能會再將郵件標示為垃圾郵件。若要解決此問題，使用 SPF 一起使用 DKIM 等 DMARC 其他電子郵件的驗證方法。</span><span class="sxs-lookup"><span data-stu-id="fa380-p115">The message originally passes the SPF check at woodgrovebank.com but it fails the SPF check at outlook.com because IP #25 is not in contoso.com's SPF TXT record. Outlook.com might then mark the message as spam. To work around this problem, use SPF in conjunction with other email authentication methods such as DKIM and DMARC.</span></span>
  
### <a name="spf-basics-including-third-party-domains-that-can-send-mail-on-behalf-of-your-domain"></a><span data-ttu-id="fa380-172">SPF 基本概念： 包含可以代表您網域傳送郵件的協力廠商網域</span><span class="sxs-lookup"><span data-stu-id="fa380-172">SPF basics: Including third-party domains that can send mail on behalf of your domain</span></span>
<span data-ttu-id="fa380-173"><a name="SPFBasicsIncludes"> </a></span><span class="sxs-lookup"><span data-stu-id="fa380-173"></span></span>

<span data-ttu-id="fa380-p116">除了 IP 位址，您也可以設定將 SPF TXT 記錄包含為寄件者的網域。這些會做為"包含"陳述式加入至 SPF TXT 記錄。例如，contoso.com 可能會想要包含所有 contoso.net 和 contoso.org 這也擁有的郵件伺服器的 IP 位址。若要這樣做，contoso.com 發佈的 SPF TXT 記錄看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="fa380-p116">In addition to IP addresses, you can also configure your SPF TXT record to include domains as senders. These are added to the SPF TXT record as "include" statements. For example, contoso.com might want to include all of the IP addresses of the mail servers from contoso.net and contoso.org which it also owns. To do this, contoso.com publishes an SPF TXT record that looks like this:</span></span>
  
```
IN TXT "v=spf1 include:contoso.net include:contoso.org -all"
```

<span data-ttu-id="fa380-p117">時接收伺服器會看到此記錄在 DNS 中，它也會執行 DNS 查閱 contoso.net 以及然後 contoso.org SPF TXT 記錄上。如果發現其他包含陳述式內 contoso.net 或 contoso.org 記錄、 將太遵循這些。以協助防止拒絕服務等攻擊、 單一電子郵件的 DNS 查詢最大數目為 10。每個包含陳述式代表其他的 DNS 查閱。如果郵件超過 10 個限制，訊息就會失敗 SPF。一旦郵件達到此限制，根據已接收的伺服器，讓寄件者可能會收到訊息表示郵件產生 「 太多查閱"或"已超出最大躍點郵件"。如何避免此問題的秘訣，請參閱[疑難排解： SPF Office 365 中的最佳作法](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot)。</span><span class="sxs-lookup"><span data-stu-id="fa380-p117">When the receiving server sees this record in DNS, it also performs a DNS lookup on the SPF TXT record for contoso.net and then for contoso.org. If it finds an additional include statement within the records for contoso.net or contoso.org, it will follow those too. In order to help prevent denial of service attacks, the maximum number of DNS lookups for a single email message is 10. Each include statement represents an additional DNS lookup. If a message exceeds the 10 limit, the message fails SPF. Once a message reaches this limit, depending on the way the receiving server is configured, the sender may receive a message that states that the message generated "too many lookups" or that the "maximum hop count for the message has been exceeded". For tips on how to avoid this, see [Troubleshooting: Best practices for SPF in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).</span></span>
  
## <a name="requirements-for-your-spf-txt-record-and-office-365"></a><span data-ttu-id="fa380-184">SPF TXT 記錄和 Office 365 的需求</span><span class="sxs-lookup"><span data-stu-id="fa380-184">Requirements for your SPF TXT record and Office 365</span></span>
<span data-ttu-id="fa380-185"><a name="SPFReqsinO365"> </a></span><span class="sxs-lookup"><span data-stu-id="fa380-185"></span></span>

<span data-ttu-id="fa380-p118">如果您設定好郵件設定 Office 365 時，您已經建立識別 Microsoft 訊息伺服器作為合法來源網域中的郵件的 SPF TXT 記錄。此記錄可能看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="fa380-p118">If you set up mail when you set up Office 365, you already created an SPF TXT record that identifies the Microsoft messaging servers as a legitimate source of mail for your domain. This record probably looks like this:</span></span>
  
```
v=spf1 include:spf.protection.outlook.com -all
```

<span data-ttu-id="fa380-188">如果您是完全託管 Office 365 客戶，也就是您傳送輸出的郵件沒有內部部署郵件伺服器，這是您要發佈的 Office 365 唯一 SPF TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="fa380-188">If you're a fully-hosted Office 365 customer, that is, you have no on-premises mail servers that send outbound mail, this is the only SPF TXT record that you need to publish for Office 365.</span></span>
  
<span data-ttu-id="fa380-189">如果您有混合式部署 （也就是您有一些信箱的內部和一些主控的 Office 365 中），或如果您是 Exchange Online Protection (EOP) 獨立客戶 （亦即您的組織使用 EOP 來保護您的內部部署信箱），您應該在 DNS SPF TXT 記錄中新增您的內部邊緣部署郵件伺服器的每個輸出的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="fa380-189">If you have a hybrid deployment (that is, you have some mailboxes on-premises and some hosted in Office 365), or if you're an Exchange Online Protection (EOP) standalone customer (that is, your organization uses EOP to protect your on-premises mailboxes), you should add the outbound IP address for each of your on-premises edge mail servers to the SPF TXT record in DNS.</span></span>
  
## <a name="form-your-spf-txt-record-for-office-365"></a><span data-ttu-id="fa380-190">Office 365 的表單 SPF TXT 記錄</span><span class="sxs-lookup"><span data-stu-id="fa380-190">Form your SPF TXT record for Office 365</span></span>
<span data-ttu-id="fa380-191"><a name="FormYourSPF"> </a></span><span class="sxs-lookup"><span data-stu-id="fa380-191"></span></span>

<span data-ttu-id="fa380-p119">若要建立的自訂網域 SPF TXT 記錄中使用本文中的語法資訊。雖然有其他語法選項不此處所提及，這些是最常使用選項。一旦您已建立您的記錄，您需要更新在網域註冊機構的記錄。</span><span class="sxs-lookup"><span data-stu-id="fa380-p119">Use the syntax information in this article to form the SPF TXT record for your custom domain. Although there are other syntax options that are not mentioned here, these are the most commonly used options. Once you have formed your record, you need to update the record at your domain registrar.</span></span>
  
<span data-ttu-id="fa380-p120">網域相關的資訊需要加入 Office 365，請參閱[所需的 SPF 外部 DNS 記錄](https://support.office.com/article/External-Domain-Name-System-records-for-Office-365-c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0?ui=en-US&amp;rs=en-US&amp;ad=US)。用於更新 SPF (TXT) 記錄您的網域註冊機構的[逐步指示](https://office.microsoft.com/en-us/office365-suite-help/create-dns-records-for-office-365-HA102851099.aspx?CTT=5&amp;origin=HA102818404)。如果未列出您註冊機構，您必須連絡這些分別以了解如何更新記錄。</span><span class="sxs-lookup"><span data-stu-id="fa380-p120">For information about the domains you will need to include for Office 365, see [External DNS records required for SPF](https://support.office.com/article/External-Domain-Name-System-records-for-Office-365-c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0?ui=en-US&amp;rs=en-US&amp;ad=US). Use the [step-by-step instructions](https://office.microsoft.com/en-us/office365-suite-help/create-dns-records-for-office-365-HA102851099.aspx?CTT=5&amp;origin=HA102818404) for updating SPF (TXT) records for your domain registrar. If your registrar is not listed, you will need to contact them separately to learn how to update your record.</span></span> 
  
### <a name="spf-txt-record-syntax-for-office-365"></a><span data-ttu-id="fa380-198">Office 365 的 SPF TXT 記錄語法</span><span class="sxs-lookup"><span data-stu-id="fa380-198">SPF TXT record syntax for Office 365</span></span>
<span data-ttu-id="fa380-199"><a name="SPFSyntaxO365"> </a></span><span class="sxs-lookup"><span data-stu-id="fa380-199"></span></span>

<span data-ttu-id="fa380-200">Office 365 的一般 SPF TXT 記錄會有下列的語法：</span><span class="sxs-lookup"><span data-stu-id="fa380-200">A typical SPF TXT record for Office 365 has the following syntax:</span></span>
  
```
v=spf1 [<ip4>|<ip6>:<IP address>] [include:<domain name>] <enforcement rule>
```

<span data-ttu-id="fa380-201">例如：</span><span class="sxs-lookup"><span data-stu-id="fa380-201">For example:</span></span>
  
```
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 include:spf.protection.outlook.com -all
```

<span data-ttu-id="fa380-202">其中：</span><span class="sxs-lookup"><span data-stu-id="fa380-202">where:</span></span>
  
- <span data-ttu-id="fa380-p121">**v = spf1**需要。這會做為 SPF TXT 記錄定義 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="fa380-p121">**v=spf1** is required. This defines the TXT record as an SPF TXT record.</span></span> 
    
- <span data-ttu-id="fa380-p122">**ip4**表示您目前已使用 IP 版本 4 地址。**ip6**表示您目前已使用 IP 版本 6 位址。如果您使用 IPv6 IP 位址，以取代**ip4** **ip6**在本文中的範例。您也可以指定 IP 位址範圍使用 CIDR 表示法，例如**ip4:192.168.0.1/26**。</span><span class="sxs-lookup"><span data-stu-id="fa380-p122">**ip4** indicates that you are using IP version 4 addresses. **ip6** indicates that you are using IP version 6 addresses. If you are using IPv6 IP addresses, replace **ip4** with **ip6** in the examples in this article. You can also specify IP address ranges using CIDR notation, for example **ip4:192.168.0.1/26**.</span></span>
    
-  <span data-ttu-id="fa380-p123">_IP 位址_是您想要新增至 SPF TXT 記錄的 IP 位址。通常，這是您組織的外寄郵件伺服器的 IP 位址。您可以列出多個輸出郵件伺服器。如需詳細資訊，請參閱[範例： SPF TXT 記錄的多個輸出內部部署郵件伺服器與 Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365)。</span><span class="sxs-lookup"><span data-stu-id="fa380-p123">_IP address_ is the IP address that you want to add to the SPF TXT record. Usually, this is the IP address of the outbound mail server for your organization. You can list multiple outbound mail servers. For more information, see [Example: SPF TXT record for multiple outbound on-premises mail servers and Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365).</span></span>
    
-  <span data-ttu-id="fa380-p124">_網域名稱_是您想要新增為合法的寄件者的網域。您應該包含 Office 365 的網域名稱的清單，請參閱[所需的 SPF 外部 DNS 記錄](https://support.office.com/article/External-Domain-Name-System-records-for-Office-365-c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="fa380-p124">_domain name_ is the domain you want to add as a legitimate sender. For a list of domain names you should include for Office 365, see [External DNS records required for SPF](https://support.office.com/article/External-Domain-Name-System-records-for-Office-365-c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
    
- <span data-ttu-id="fa380-215">強制執行規則通常是下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="fa380-215">Enforcement rule is usually one of the following:</span></span>
    
  - <span data-ttu-id="fa380-216">-all</span><span class="sxs-lookup"><span data-stu-id="fa380-216">-all</span></span>
    
    <span data-ttu-id="fa380-p125">會指出完全未通過。如果您知道授權的 IP 位址的所有網域，其列出 SPF TXT 記錄中並使用-全部 （完全未通過） 辨識符號。此外，如果您只使用 SPF，也就是您不使用 DMARC 或 DKIM、 您應該使用-所有辨識符號。我們建議您一律使用此辨識符號。</span><span class="sxs-lookup"><span data-stu-id="fa380-p125">Indicates hard fail. If you know all of the authorized IP addresses for your domain, list them in the SPF TXT record and use the -all (hard fail) qualifier. Also, if you are only using SPF, that is, you are not using DMARC or DKIM, you should use the -all qualifier. We recommend that you use always this qualifier.</span></span>
    
  - <span data-ttu-id="fa380-221">~ 所有</span><span class="sxs-lookup"><span data-stu-id="fa380-221">~all</span></span>
    
    <span data-ttu-id="fa380-p126">會指出軟體失敗。如果您不確定您擁有的 IP 位址的完整清單，則應該使用 ~ 所有 （軟體失敗） 辨識符號。此外，如果您使用 DMARC 搭配 p = 隔離或 p = 拒絕，則您可以使用 ~ 所有。否則請使用-所有。</span><span class="sxs-lookup"><span data-stu-id="fa380-p126">Indicates soft fail. If you're not sure that you have the complete list of IP addresses, then you should use the ~all (soft fail) qualifier. Also, if you are using DMARC with p=quarantine or p=reject, then you can use ~all. Otherwise, use -all.</span></span>
    
  - <span data-ttu-id="fa380-226">吗？ 所有</span><span class="sxs-lookup"><span data-stu-id="fa380-226">?all</span></span>
    
    <span data-ttu-id="fa380-p127">會指出相關。在測試 SPF 時使用此選項。不建議您在實際部署中使用此辨識符號。</span><span class="sxs-lookup"><span data-stu-id="fa380-p127">Indicates neutral. This is used when testing SPF. We do not recommend that you use this qualifier in your live deployment.</span></span>
    
### <a name="example-spf-txt-record-to-use-when-all-of-your-mail-is-sent-by-office-365"></a><span data-ttu-id="fa380-230">範例： SPF TXT 記錄時所要使用您的信箱的所有已傳送的 Office 365</span><span class="sxs-lookup"><span data-stu-id="fa380-230">Example: SPF TXT record to use when all of your mail is sent by Office 365</span></span>
<span data-ttu-id="fa380-231"><a name="ExampleSPFNoSP"> </a></span><span class="sxs-lookup"><span data-stu-id="fa380-231"></span></span>

<span data-ttu-id="fa380-232">如果您的信箱的所有傳送由 Office 365，請使用此 SPF TXT 記錄中：</span><span class="sxs-lookup"><span data-stu-id="fa380-232">If all of your mail is sent by Office 365, use this in your SPF TXT record:</span></span>
  
```
v=spf1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-a-hybrid-scenario-with-one-on-premises-exchange-server-and-office-365"></a><span data-ttu-id="fa380-233">範例： SPF TXT 記錄的混合式案例使用下列一個內部部署 Exchange Server 與 Office 365</span><span class="sxs-lookup"><span data-stu-id="fa380-233">Example: SPF TXT record for a hybrid scenario with one on-premises Exchange Server and Office 365</span></span>
<span data-ttu-id="fa380-234"><a name="ExampleSPFHybridOneExchangeServer"> </a></span><span class="sxs-lookup"><span data-stu-id="fa380-234"></span></span>

<span data-ttu-id="fa380-235">在混合環境中，如果您的內部部署 Exchange 伺服器的 IP 位址為 192.168.0.1，才能設定 SPF 強制執行規則為完全未通過，表單 SPF TXT 記錄，如下所示：</span><span class="sxs-lookup"><span data-stu-id="fa380-235">In a hybrid environment, if the IP address of your on-premises Exchange Server is 192.168.0.1, in order to set the SPF enforcement rule to hard fail, form the SPF TXT record as follows:</span></span>
  
```
v=spf1 ip4:192.168.0.1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-multiple-outbound-on-premises-mail-servers-and-office-365"></a><span data-ttu-id="fa380-236">範例： SPF TXT 記錄的多個輸出內部部署郵件伺服器與 Office 365</span><span class="sxs-lookup"><span data-stu-id="fa380-236">Example: SPF TXT record for multiple outbound on-premises mail servers and Office 365</span></span>
<span data-ttu-id="fa380-237"><a name="ExampleSPFMultipleMailServerO365"> </a></span><span class="sxs-lookup"><span data-stu-id="fa380-237"></span></span>

<span data-ttu-id="fa380-p128">如果您有多個輸出郵件伺服器，包括 SPF TXT 記錄中的每個郵件伺服器的 IP 位址和使用後面加上一個空格分隔每個 IP 位址"ip4:"陳述式。例如：</span><span class="sxs-lookup"><span data-stu-id="fa380-p128">If you have multiple outbound mail servers, include the IP address for each mail server in the SPF TXT record and separate each IP address with a space followed by an "ip4:" statement. For example:</span></span>
  
```
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 ip4:192.168.0.3 include:spf.protection.outlook.com -all
```

## <a name="next-steps-set-up-spf-for-office-365"></a><span data-ttu-id="fa380-240">後續步驟： 針對 Office 365 設定 SPF</span><span class="sxs-lookup"><span data-stu-id="fa380-240">Next steps: Set up SPF for Office 365</span></span>
<span data-ttu-id="fa380-241"><a name="SPFNextSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="fa380-241"></span></span>

<span data-ttu-id="fa380-242">已成形 SPF TXT 記錄的一次，請遵循[設定 SPF 避免詐騙的 Office 365 中](set-up-spf-in-office-365-to-help-prevent-spoofing.md)將它新增至您的網域中的步驟。</span><span class="sxs-lookup"><span data-stu-id="fa380-242">Once you have formulated your SPF TXT record, follow the steps in [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) to add it to your domain.</span></span> 
  
<span data-ttu-id="fa380-p129">雖然 SPF 專門設計來協助防止詐騙，但有詐騙技術 （英文） 無法防止該 SPF。若要防止這些，一旦您已設定好 SPF，您也應該 for Office 365 設定 DKIM 和 DMARC。若要開始，請參閱[使用 DKIM 驗證從您在 Office 365 中的自訂網域傳送的輸出電子郵件](use-dkim-to-validate-outbound-email.md)。接下來，請參閱[使用 DMARC 來驗證 Office 365 中的電子郵件](use-dmarc-to-validate-email.md)。</span><span class="sxs-lookup"><span data-stu-id="fa380-p129">Although SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against. In order to protect against these, once you have set up SPF, you should also configure DKIM and DMARC for Office 365. To get started, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md). Next, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span>
  
## <a name="troubleshooting-best-practices-for-spf-in-office-365"></a><span data-ttu-id="fa380-247">疑難排解： 的 SPF Office 365 中的最佳作法</span><span class="sxs-lookup"><span data-stu-id="fa380-247">Troubleshooting: Best practices for SPF in Office 365</span></span>
<span data-ttu-id="fa380-248"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="fa380-248"></span></span>

<span data-ttu-id="fa380-p130">您只能建立一個 SPF TXT 記錄的自訂網域。建立多筆記錄會產生的循環配置資源狀況和 SPF 將會失敗。若要避免此問題，您可以建立的每一個子網域不同的記錄。例如，建立一筆記錄的 contoso.com 和 bulkmail.contoso.com 的另一筆記錄。</span><span class="sxs-lookup"><span data-stu-id="fa380-p130">You can only create one SPF TXT record for your custom domain. Creating multiple records causes a round robin situation and SPF will fail. To avoid this, you can create separate records for each subdomain. For example, create one record for contoso.com and another record for bulkmail.contoso.com.</span></span>
  
<span data-ttu-id="fa380-p131">如果再傳遞電子郵件訊息會造成超過 10 個 DNS 查詢，接收的郵件伺服器會回應以永久錯誤，也稱為_permerror_，並導致失敗 SPF 檢查郵件。接收伺服器也可能會回應以未傳遞回報 (NDR) 包含類似下列的錯誤：</span><span class="sxs-lookup"><span data-stu-id="fa380-p131">If an email message causes more than 10 DNS lookups before it is delivered, the receiving mail server will respond with a permanent error, also called a  _permerror_, and cause the message to fail the SPF check. The receiving server may also respond with a non-delivery report (NDR) that contains an error similar to these:</span></span>
  
- <span data-ttu-id="fa380-255">郵件超過一個躍點計數。</span><span class="sxs-lookup"><span data-stu-id="fa380-255">The message exceeded the hop count.</span></span>
    
- <span data-ttu-id="fa380-256">訊息需要太多查閱。</span><span class="sxs-lookup"><span data-stu-id="fa380-256">The message required too many lookups.</span></span>
    
## <a name="avoiding-the-too-many-lookups-error-when-you-use-third-party-domains-with-office-365"></a><span data-ttu-id="fa380-257">當您使用協力廠商網域與 Office 365 時避免"太多查閱服務 」 錯誤</span><span class="sxs-lookup"><span data-stu-id="fa380-257">Avoiding the "too many lookups" error when you use third-party domains with Office 365</span></span>
<span data-ttu-id="fa380-258"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="fa380-258"></span></span>

<span data-ttu-id="fa380-p132">協力廠商網域的某些 SPF TXT 記錄直接接收伺服器可執行 DNS 查閱的數目。例如，在此寫入時間 Salesforce.com 包含 5 其記錄中包含陳述式：</span><span class="sxs-lookup"><span data-stu-id="fa380-p132">Some SPF TXT records for third-party domains direct the receiving server to perform a large number of DNS lookups. For example, at the time of this writing, Salesforce.com contains 5 include statements in its record:</span></span>
  
```
v=spf1 include:_spf.google.com
include:_spfblock.salesforce.com
include:_qa.salesforce.com
include:_spfblock1.salesforce.com
include:spf.mandrillapp.com mx ~all
```

<span data-ttu-id="fa380-p133">若要避免發生錯誤，您可以實作任何人傳送大量郵件，例如已特別針對此目的而使用子網域的其中一個原則。您再定義不同 SPF TXT 記錄包含大量電子郵件的子網域。</span><span class="sxs-lookup"><span data-stu-id="fa380-p133">To avoid the error, you can implement a policy where anyone sending bulk email, for example, has to use a subdomain specifically for this purpose. You then define a different SPF TXT record for the subdomain that includes the bulk email.</span></span>
  
 <span data-ttu-id="fa380-p134">在某些情況下，salesforce.com 範例類似您必須使用網域中您 SPF TXT 記錄，但在其他情況下，與協力廠商可能已經建立您要用於此目的而子網域。例如，exacttarget.com 已建立您要用於 SPF TXT 記錄是子網域：</span><span class="sxs-lookup"><span data-stu-id="fa380-p134">In some cases, like the salesforce.com example, you have to use the domain in your SPF TXT record, but in other cases, the third-party may have already created a subdomain for you to use for this purpose. For example, exacttarget.com has created a subdomain that you need to use for your SPF TXT record:</span></span> 
  
```
cust-spf.exacttarget.com
```

<span data-ttu-id="fa380-265">當您在 SPF TXT 記錄中包含與協力廠商網域時，您需要確認具有哪些網域或子網域使用，以避免執行到 10 個查閱限制協力廠商。</span><span class="sxs-lookup"><span data-stu-id="fa380-265">When you include third-party domains in your SPF TXT record, you need to confirm with the third-party which domain or subdomain to use in order to avoid running into the 10 lookup limit.</span></span>
  
## <a name="how-to-view-your-current-spf-txt-record-and-determine-the-number-of-lookups-that-it-requires"></a><span data-ttu-id="fa380-266">如何檢視目前的 SPF TXT 記錄並決定需要的查詢數目</span><span class="sxs-lookup"><span data-stu-id="fa380-266">How to view your current SPF TXT record and determine the number of lookups that it requires</span></span>
<span data-ttu-id="fa380-267"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="fa380-267"></span></span>

<span data-ttu-id="fa380-p135">您可以使用 nslookup 來檢視您的 DNS 記錄，其中包括 SPF TXT 記錄。或者，如果您偏好，有許多免費的線上工具提供可用來檢視您 SPF TXT 記錄的內容。透過查看 SPF TXT 記錄並接在鏈結包含陳述式和重新導向，您可決定記錄需要多少 DNS 查閱。某些線上工具將偶數計數並顯示這些查閱。追蹤的此號碼可協助防止從您的組織從觸發永久錯誤、 permerror 從未接收伺服器傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="fa380-p135">You can use nslookup to view your DNS records, including your SPF TXT record. Or, if you prefer, there are a number of free, online tools available that you can use to view the contents of your SPF TXT record. By looking at your SPF TXT record and following the chain of include statements and redirects, you can determine how many DNS lookups the record requires. Some online tools will even count and display these lookups for you. Keeping track of this number will help prevent messages sent from your organization from triggering a permanent error, called a permerror, from the receiving server.</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="fa380-273">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="fa380-273">For more information</span></span>
<span data-ttu-id="fa380-274"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="fa380-274"></span></span>

<span data-ttu-id="fa380-p136">需要協助新增 TXT SPF 記錄吗？使用來更新在常用的網域註冊機構各種 SPF (TXT) 記錄的[逐步指示](https://office.microsoft.com/en-us/office365-suite-help/create-dns-records-for-office-365-HA102851099.aspx?CTT=5&amp;origin=HA102818404)。[反垃圾郵件郵件標頭](anti-spam-message-headers.md)包含 SPF 檢查 Office 365 所使用的語法和標頭欄位。</span><span class="sxs-lookup"><span data-stu-id="fa380-p136">Need help adding the SPF TXT record? [Step-by-step instructions](https://office.microsoft.com/en-us/office365-suite-help/create-dns-records-for-office-365-HA102851099.aspx?CTT=5&amp;origin=HA102818404) for updating SPF (TXT) records at a variety of popular domain registrars is available. [Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Office 365 for SPF checks.</span></span> 
  

