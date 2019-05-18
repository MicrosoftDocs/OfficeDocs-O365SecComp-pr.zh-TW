---
title: 將疑難排解郵件傳送至 Office 365
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 5/2/2016
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
ms.collection:
- M365-security-compliance
description: 本文提供寄件者嘗試傳送電子郵件給 Office 365 和 Office 365 客戶的大量郵件的最佳作法中的收件匣時遇到問題的疑難排解資訊。
ms.openlocfilehash: ecb5c407c793fa93bf6f64589531bb3cff3c3494
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34158215"
---
# <a name="troubleshooting-mail-sent-to-office-365"></a><span data-ttu-id="c554f-103">將疑難排解郵件傳送至 Office 365</span><span class="sxs-lookup"><span data-stu-id="c554f-103">Troubleshooting mail sent to Office 365</span></span>

<span data-ttu-id="c554f-104">本文提供寄件者嘗試傳送電子郵件給 Office 365 和 Office 365 客戶的大量郵件的最佳作法中的收件匣時遇到問題的疑難排解資訊。</span><span class="sxs-lookup"><span data-stu-id="c554f-104">This article provides troubleshooting information for senders who are experiencing issues when trying to send email to inboxes in Office 365 and best practices for bulk mailing to Office 365 customers.</span></span>
  
## <a name="troubleshooting-common-problems-with-mail-delivery-to-office-365"></a><span data-ttu-id="c554f-105">疑難排解郵件傳遞到 Office 365 的常見問題</span><span class="sxs-lookup"><span data-stu-id="c554f-105">Troubleshooting common problems with mail delivery to Office 365</span></span>

<span data-ttu-id="c554f-106">選擇 [從下列其中一個這些常遇到的問題。</span><span class="sxs-lookup"><span data-stu-id="c554f-106">Choose from one of these commonly encountered issues.</span></span>
  
- [<span data-ttu-id="c554f-107">您管理您的 IP 和網域的傳送信譽嗎？</span><span class="sxs-lookup"><span data-stu-id="c554f-107">Are you managing your IP and domain's sending reputation?</span></span>](troubleshooting-mail-sent-to-office-365.md#ManageRep)
    
- [<span data-ttu-id="c554f-108">從新的 IP 位址是您傳送電子郵件？</span><span class="sxs-lookup"><span data-stu-id="c554f-108">Are you sending email from new IP addresses?</span></span>](troubleshooting-mail-sent-to-office-365.md#NewIPs)
    
- [<span data-ttu-id="c554f-109">確認您的 DNS 設定正確</span><span class="sxs-lookup"><span data-stu-id="c554f-109">Confirm that your DNS is set up correctly</span></span>](troubleshooting-mail-sent-to-office-365.md#ConfirmDNSsetup)
    
- [<span data-ttu-id="c554f-110">確定，您不要未通告自行為非可路由的 IP</span><span class="sxs-lookup"><span data-stu-id="c554f-110">Ensure that you do not advertise yourself as a non-routable IP</span></span>](troubleshooting-mail-sent-to-office-365.md#NoReverseDNS)
    
- [<span data-ttu-id="c554f-111">您收到未傳遞回報 (NDR) 時傳送電子郵件給 Office 365 中的使用者</span><span class="sxs-lookup"><span data-stu-id="c554f-111">You received a non-delivery report (NDR) when sending email to a user in Office 365</span></span>](troubleshooting-mail-sent-to-office-365.md#NDRInbound)
    
- [<span data-ttu-id="c554f-112">我的電子郵件進入 EOP 中的收件者的垃圾郵件資料夾中</span><span class="sxs-lookup"><span data-stu-id="c554f-112">My email landed in the recipient's junk folder in EOP</span></span>](troubleshooting-mail-sent-to-office-365.md#JunkMailBox)
    
- [<span data-ttu-id="c554f-113">從我的 IP 位址的流量節流透過 EOP</span><span class="sxs-lookup"><span data-stu-id="c554f-113">Traffic from my IP address is throttled by EOP</span></span>](troubleshooting-mail-sent-to-office-365.md#AllowEOPIPs)
    
### <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a><span data-ttu-id="c554f-114">您管理您的 IP 和網域的傳送信譽嗎？</span><span class="sxs-lookup"><span data-stu-id="c554f-114">Are you managing your IP and domain's sending reputation?</span></span>
<span data-ttu-id="c554f-115"><a name="ManageRep"> </a></span><span class="sxs-lookup"><span data-stu-id="c554f-115"></span></span>

<span data-ttu-id="c554f-116">EOP 篩選技術被設計來提供 Microsoft Office 365，以及 Exchange Server、 Microsoft Office Outlook 及 Windows Live Mail 等其他 Microsoft 產品的反垃圾郵件保護。</span><span class="sxs-lookup"><span data-stu-id="c554f-116">EOP filtering technologies are designed to provide anti-spam protections for Microsoft Office 365 as well as other Microsoft products like Exchange Server, Microsoft Office Outlook, and Windows Live Mail.</span></span> <span data-ttu-id="c554f-117">我們也會利用 SPF，DKIM、 DMARC;電子郵件驗證技術，可協助解決問題的詐騙和網路釣魚藉由驗證傳送電子郵件的網域有權執行這項操作。</span><span class="sxs-lookup"><span data-stu-id="c554f-117">We also leverage SPF, DKIM, and DMARC; email authentication technologies that help address the problem of spoofing and phishing by verifying that the domain sending the email is authorized to do so.</span></span> <span data-ttu-id="c554f-118">EOP 篩選會受到許多因素相關的傳送端 IP、 網域、 驗證、 清單正確性、 抱怨率、 內容等等。</span><span class="sxs-lookup"><span data-stu-id="c554f-118">EOP filtering is influenced by a number of factors related to the sending IP, domain, authentication, list accuracy, complaint rates, content and more.</span></span> <span data-ttu-id="c554f-119">這些項目，其中一個主要因素，向寄件者信譽下主導及其能夠傳送電子郵件是垃圾郵件抱怨比率。</span><span class="sxs-lookup"><span data-stu-id="c554f-119">Of these, one of the principal factors in driving down a sender's reputation and their ability to deliver email is their junk email complaint rate.</span></span> 
  
### <a name="are-you-sending-email-from-new-ip-addresses"></a><span data-ttu-id="c554f-120">從新的 IP 位址是您傳送電子郵件？</span><span class="sxs-lookup"><span data-stu-id="c554f-120">Are you sending email from new IP addresses?</span></span>
<span data-ttu-id="c554f-121"><a name="NewIPs"> </a></span><span class="sxs-lookup"><span data-stu-id="c554f-121"></span></span>

<span data-ttu-id="c554f-122">IP 位址不先前用來傳送電子郵件通常不需要在我們的系統，建置任何信譽。</span><span class="sxs-lookup"><span data-stu-id="c554f-122">IP addresses not previously used to send email typically don't have any reputation built up in our systems.</span></span> <span data-ttu-id="c554f-123">因此，從新 Ip 的電子郵件會更有可能發生傳遞問題。</span><span class="sxs-lookup"><span data-stu-id="c554f-123">As a result, emails from new IPs are more likely to experience delivery issues.</span></span> <span data-ttu-id="c554f-124">一旦 IP 具有內建信譽不傳送垃圾郵件，EOP 通常會允許較佳的電子郵件傳遞經驗。</span><span class="sxs-lookup"><span data-stu-id="c554f-124">Once the IP has built a reputation for not sending spam, EOP will typically allow for a better email delivery experience.</span></span>
  
<span data-ttu-id="c554f-125">新增的網域的一般驗證下現有的 SPF 記錄的新 Ip 體驗繼承的網域的傳送信譽一些的好處。</span><span class="sxs-lookup"><span data-stu-id="c554f-125">New IPs that are added for domains that are authenticated under existing SPF records typically experience the added benefit of inheriting some of the domain's sending reputation.</span></span> <span data-ttu-id="c554f-126">如果您的網域有良好傳送信譽新 Ip 可能會遇到的時間更需要費時。</span><span class="sxs-lookup"><span data-stu-id="c554f-126">If your domain has a good sending reputation new IPs may experience a faster ramp up time.</span></span> <span data-ttu-id="c554f-127">新的 IP 可以預期會完全 ramped 幾週或更快速地根據磁碟區、 清單正確性和垃圾郵件抱怨率。</span><span class="sxs-lookup"><span data-stu-id="c554f-127">A new IP can expect to be fully ramped within a couple of weeks or sooner depending on volume, list accuracy, and junk email complaint rates.</span></span>
  
### <a name="confirm-that-your-dns-is-set-up-correctly"></a><span data-ttu-id="c554f-128">確認您的 DNS 設定正確</span><span class="sxs-lookup"><span data-stu-id="c554f-128">Confirm that your DNS is set up correctly</span></span>
<span data-ttu-id="c554f-129"><a name="ConfirmDNSsetup"> </a></span><span class="sxs-lookup"><span data-stu-id="c554f-129"></span></span>

<span data-ttu-id="c554f-130">如需如何建立及維護 DNS 記錄，其中包括郵件路由，所需的 MX 記錄指示您必須連絡您的 DNS 主機服務提供者。</span><span class="sxs-lookup"><span data-stu-id="c554f-130">For instructions about how to create and maintain DNS records, including the MX record required for mail routing, you will need to contact your DNS hosting provider.</span></span>
  
### <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a><span data-ttu-id="c554f-131">確定，您不要未通告自行為非可路由的 IP</span><span class="sxs-lookup"><span data-stu-id="c554f-131">Ensure that you do not advertise yourself as a non-routable IP</span></span>
<span data-ttu-id="c554f-132"><a name="NoReverseDNS"> </a></span><span class="sxs-lookup"><span data-stu-id="c554f-132"></span></span>

<span data-ttu-id="c554f-133">我們可能不會接受來自失敗反向 DNS 查閱寄件者的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="c554f-133">We may not accept email from senders who fail a reverse-DNS lookup.</span></span> <span data-ttu-id="c554f-134">在某些情況下，合法的寄件者通知本身不正確地為非網際網路可路由傳送 IP 嘗試開啟的連線至 EOP 時。</span><span class="sxs-lookup"><span data-stu-id="c554f-134">In some cases, legitimate senders advertise themselves incorrectly as a non-internet routable IP when attempting to open a connection to EOP.</span></span> <span data-ttu-id="c554f-135">IP 位址，則保留給私人 （非可路由） 的網路功能包括：</span><span class="sxs-lookup"><span data-stu-id="c554f-135">IP addresses that are reserved for private (non-routable) networking include:</span></span>
  
- <span data-ttu-id="c554f-136">192.168.0.0/16 (或 192.168.0.0-192.168.255.255)</span><span class="sxs-lookup"><span data-stu-id="c554f-136">192.168.0.0/16 (or 192.168.0.0 - 192.168.255.255)</span></span>
    
- <span data-ttu-id="c554f-137">10.0.0.0/8 (或 10.0.0.0-10.255.255.255)</span><span class="sxs-lookup"><span data-stu-id="c554f-137">10.0.0.0/8 (or 10.0.0.0 - 10.255.255.255)</span></span>
    
- <span data-ttu-id="c554f-138">172.16.0.0/11 (或 172.16.0.0-172.31.255.255)</span><span class="sxs-lookup"><span data-stu-id="c554f-138">172.16.0.0/11 (or 172.16.0.0 - 172.31.255.255)</span></span>
    
### <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a><span data-ttu-id="c554f-139">您收到未傳遞回報 (NDR) 時傳送電子郵件給 Office 365 中的使用者</span><span class="sxs-lookup"><span data-stu-id="c554f-139">You received a non-delivery report (NDR) when sending email to a user in Office 365</span></span>
<span data-ttu-id="c554f-140"><a name="NDRInbound"> </a></span><span class="sxs-lookup"><span data-stu-id="c554f-140"></span></span>

<span data-ttu-id="c554f-141">某些傳遞問題是由 Microsoft 遭到封鎖的寄件者的 IP 位址的結果，或是因為使用者帳戶視為禁用的寄件者，因為先前的垃圾郵件活動。</span><span class="sxs-lookup"><span data-stu-id="c554f-141">Some delivery issues are the result of the sender's IP address being blocked by Microsoft or because the user account is identified as banned sender due to previous spam activity.</span></span> <span data-ttu-id="c554f-142">如果您有收到錯誤 NDR，先遵循解決問題，請將 NDR 訊息的指示進行。</span><span class="sxs-lookup"><span data-stu-id="c554f-142">If you believe that you have received the NDR in error, first follow any instructions in the NDR message to resolve the issue.</span></span> 
  
<span data-ttu-id="c554f-143">在您收到的錯誤的詳細資訊，請參閱中[的 Dsn 和 Ndr 內部部署 Exchange 2013 和 Office 365 中](http://technet.microsoft.com/library/8e91de84-76fa-49b2-898c-c5eface76560.aspx)的 SMTP 錯誤碼的完整清單。</span><span class="sxs-lookup"><span data-stu-id="c554f-143">For more information about the error you received, see the complete list of SMTP error codes in [DSNs and NDRs in On-Premises Exchange 2013 and Office 365](http://technet.microsoft.com/library/8e91de84-76fa-49b2-898c-c5eface76560.aspx).</span></span>
  
 <span data-ttu-id="c554f-144">例如，如果您收到下列 NDR，它表示傳送端 IP 位址已封鎖的 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="c554f-144">For example, if you receive the following NDR, it indicates that the sending IP address was blocked by Microsoft.</span></span> 
  
 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`
  
<span data-ttu-id="c554f-145">若要要求從此清單時移除，您可以[使用取消列出入口網站將您自己從 Office 365 封鎖寄件者清單移除](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)。</span><span class="sxs-lookup"><span data-stu-id="c554f-145">To request removal from this list, you can [Use the delist portal to remove yourself from the Office 365 blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>
  
### <a name="my-email-landed-in-the-recipients-junk-folder-in-eop"></a><span data-ttu-id="c554f-146">我的電子郵件進入 EOP 中的收件者的垃圾郵件資料夾中</span><span class="sxs-lookup"><span data-stu-id="c554f-146">My email landed in the recipient's junk folder in EOP</span></span>
<span data-ttu-id="c554f-147"><a name="JunkMailBox"> </a></span><span class="sxs-lookup"><span data-stu-id="c554f-147"></span></span>

<span data-ttu-id="c554f-148">如果郵件被誤判為垃圾郵件透過 EOP，您可以使用收件者送出此誤判郵件給 Microsoft 垃圾郵件分析小組，小組會評估和分析此郵件。</span><span class="sxs-lookup"><span data-stu-id="c554f-148">If a message was incorrectly identified as spam by EOP, you can work with the recipient to submit this false positive message to the Microsoft Spam Analysis Team, who will evaluate and analyze the message.</span></span> <span data-ttu-id="c554f-149">我們可以根據分析的結果調整全服務的垃圾郵件內容篩選規則，以便允許郵件通行。</span><span class="sxs-lookup"><span data-stu-id="c554f-149">Depending on the results of the analysis, the service-wide spam content filter rules may be adjusted to allow the message through.</span></span> <span data-ttu-id="c554f-150">您可以使用電子郵件來提交郵件提交給 Microsoft，不應歸類為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="c554f-150">You use email to submit messages to Microsoft that should not be classified as spam.</span></span> <span data-ttu-id="c554f-151">這麼做時，請務必使用下列程序中的步驟。</span><span class="sxs-lookup"><span data-stu-id="c554f-151">When doing so, be sure to use the steps in the following procedure.</span></span>
  
### <a name="to-use-email-to-submit-false-positive-messages-to-the-microsoft-spam-analysis-team"></a><span data-ttu-id="c554f-152">若要使用電子郵件來提交誤判的郵件給 Microsoft 垃圾郵件分析小組</span><span class="sxs-lookup"><span data-stu-id="c554f-152">To use email to submit false positive messages to the Microsoft Spam Analysis Team</span></span>

1. <span data-ttu-id="c554f-153">儲存您想要當作非垃圾郵件提交的郵件。</span><span class="sxs-lookup"><span data-stu-id="c554f-153">Save the message you want to submit as non-spam.</span></span>
    
2. <span data-ttu-id="c554f-154">建立新的空白郵件，然後在其中附加非垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="c554f-154">Create a new, blank message and attach the non-spam message to it.</span></span>
    
    <span data-ttu-id="c554f-155">如有需要您可以附加多個非垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="c554f-155">You can attach multiple non-spam messages if needed.</span></span>
    
3. <span data-ttu-id="c554f-156">複製原始郵件的主旨行並貼到新郵件的主旨行中。</span><span class="sxs-lookup"><span data-stu-id="c554f-156">Copy and paste the original message subject line into the new message subject line.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c554f-157">將新郵件的內文保留空白。</span><span class="sxs-lookup"><span data-stu-id="c554f-157">Leave the body of the new message empty.</span></span> 
  
4. <span data-ttu-id="c554f-158">將新郵件傳送到 [not_junk@office365.microsoft.com](mailto:not_junk@office365.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="c554f-158">Send your new message to [not_junk@office365.microsoft.com](mailto:not_junk@office365.microsoft.com).</span></span>
    
### <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a><span data-ttu-id="c554f-159">從我的 IP 位址的流量節流透過 EOP</span><span class="sxs-lookup"><span data-stu-id="c554f-159">Traffic from my IP address is throttled by EOP</span></span>
<span data-ttu-id="c554f-160"><a name="AllowEOPIPs"> </a></span><span class="sxs-lookup"><span data-stu-id="c554f-160"></span></span>

<span data-ttu-id="c554f-161">如果您收到 NDR，以指出 EOP 從您的 IP 位址會受到節流透過 EOP，例如：</span><span class="sxs-lookup"><span data-stu-id="c554f-161">If you receive an NDR from EOP that indicates that your IP address is being throttled by EOP, for example:</span></span>
  
 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`
  
<span data-ttu-id="c554f-162">因為已偵測到可疑活動來自 IP 位址，而且它已暫時限制正在深入評估時，您會收到 NDR。</span><span class="sxs-lookup"><span data-stu-id="c554f-162">You received the NDR because suspicious activity has been detected from the IP address and it has been temporarily restricted while it is being further evaluated.</span></span> <span data-ttu-id="c554f-163">如果透過評估清除懷疑，則會立刻得以實現這項限制。</span><span class="sxs-lookup"><span data-stu-id="c554f-163">If the suspicion is cleared through evaluation, this restriction will be lifted shortly.</span></span>
  
### <a name="i-cant-receive-email-from-senders-in-office-365"></a><span data-ttu-id="c554f-164">我無法接收電子郵件從 Office 365 中的寄件者</span><span class="sxs-lookup"><span data-stu-id="c554f-164">I can't receive email from senders in Office 365</span></span>
<span data-ttu-id="c554f-165"><a name="AllowEOPIPs"> </a></span><span class="sxs-lookup"><span data-stu-id="c554f-165"></span></span>

 <span data-ttu-id="c554f-166">若要從我們的使用者接收郵件，請確定您的網路允許來自 EOP 使用我們的資料中心 IP 位址的連線。</span><span class="sxs-lookup"><span data-stu-id="c554f-166">In order to receive messages from our users, make sure your network allows connections from the IP addresses that EOP uses in our datacenters.</span></span> <span data-ttu-id="c554f-167">如需詳細資訊，請參閱 < <b0>Exchange Online Protection IP 位址</b0>。</span><span class="sxs-lookup"><span data-stu-id="c554f-167">For more information, see [Exchange Online Protection IP addresses](eop/exchange-online-protection-ip-addresses.md).</span></span> 
  
## <a name="best-practices-for-bulk-emailing-to-office-365-users"></a><span data-ttu-id="c554f-168">大量以電子郵件傳送給 Office 365 使用者的最佳做法</span><span class="sxs-lookup"><span data-stu-id="c554f-168">Best practices for bulk emailing to Office 365 users</span></span>
<span data-ttu-id="c554f-169"><a name="BulkMailer"> </a></span><span class="sxs-lookup"><span data-stu-id="c554f-169"></span></span>

<span data-ttu-id="c554f-170">如果您經常進行大量電子郵件行銷活動，Office 365 使用者，而且想要確保您的電子郵件送達安全即時而可靠的方式，請遵循本節中的提示。</span><span class="sxs-lookup"><span data-stu-id="c554f-170">If you often conduct bulk email campaigns to Office 365 users and want to ensure that your emails arrive in a safe and timely manner, follow the tips in this section.</span></span>
  
### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a><span data-ttu-id="c554f-171">確定 [從： 名稱會反映出誰傳送給郵件</span><span class="sxs-lookup"><span data-stu-id="c554f-171">Ensure that the From: name reflects who is sending the message</span></span>

<span data-ttu-id="c554f-172">查看郵件的簡短摘要是關於，和郵件內文應清楚且簡潔地指出供應項目、 服務或產品為何有關，應該是主旨。</span><span class="sxs-lookup"><span data-stu-id="c554f-172">The Subject should be a brief summary of what the message is about, and the message body should clearly and succinctly indicate what the offering, service, or product is about.</span></span> <span data-ttu-id="c554f-173">例如：</span><span class="sxs-lookup"><span data-stu-id="c554f-173">For example:</span></span>
  
<span data-ttu-id="c554f-174">修正</span><span class="sxs-lookup"><span data-stu-id="c554f-174">Correct</span></span>
  
 ` From: marketing@shoppershandbag.com `
  
 `Subject: Updated catalog for the Christmas season!`
  
<span data-ttu-id="c554f-175">不正確</span><span class="sxs-lookup"><span data-stu-id="c554f-175">Incorrect</span></span>
  
 `From: someone@outlook.com`
  
 `Subject: Catalogs`
  
<span data-ttu-id="c554f-176">更容易讓其他人知道您是誰，而您所執行的動作、 較少的困難度您傳遞到大部分的垃圾郵件篩選器。</span><span class="sxs-lookup"><span data-stu-id="c554f-176">The easier you make it for people to know who you are and what you are doing, the less difficulty you will have delivering through most spam filters.</span></span>
  
### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a><span data-ttu-id="c554f-177">一律包含活動電子郵件中的 [取消訂閱選項</span><span class="sxs-lookup"><span data-stu-id="c554f-177">Always include an unsubscribe option in campaign emails</span></span>

<span data-ttu-id="c554f-178">行銷電子郵件，尤其是新聞稿、 應該一律包含取消訂閱未來的電子郵件的方式。</span><span class="sxs-lookup"><span data-stu-id="c554f-178">Marketing emails, especially newsletters, should always include a way of unsubscribing from future emails.</span></span> <span data-ttu-id="c554f-179">例如：</span><span class="sxs-lookup"><span data-stu-id="c554f-179">For example:</span></span>
  
 `This email was sent to example@contoso.com by sender@fabrikam.com.`
  
 `Update Profile/Email Address | Instant removal with SafeUnsubscribe™ | Privacy Policy`
  
<span data-ttu-id="c554f-180">某些寄件者藉由要求收件者傳送一封電子郵件給特定別名與 「 取消訂閱 「 主旨中包含此選項。</span><span class="sxs-lookup"><span data-stu-id="c554f-180">Some senders include this option by requiring recipients to send an email to a certain alias with "Unsubscribe" in the subject.</span></span> <span data-ttu-id="c554f-181">這不是優先於按一下上述範例中。</span><span class="sxs-lookup"><span data-stu-id="c554f-181">This is not preferable to the one-click example above.</span></span> <span data-ttu-id="c554f-182">如果您選擇需要收件者傳送郵件，確保當他們按一下連結時，所有必要的欄位會預先填入。</span><span class="sxs-lookup"><span data-stu-id="c554f-182">If you do choose to require recipients to send a mail, ensure that when they click the link, all the required fields are pre-populated.</span></span>
  
### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a><span data-ttu-id="c554f-183">用於行銷電子郵件或電子報註冊雙重加入確認程序集選項</span><span class="sxs-lookup"><span data-stu-id="c554f-183">Use the double opt-in option for marketing email or newsletter registration</span></span>

<span data-ttu-id="c554f-184">如果貴公司需要或鼓勵使用者註冊其連絡人資訊才可存取您的產品或服務，建議使用這個業界最佳作法。</span><span class="sxs-lookup"><span data-stu-id="c554f-184">This industry best practice is recommended if your company requires or encourages users to register their contact information in order to access your product or services.</span></span> <span data-ttu-id="c554f-185">某些公司使其作法是自動註冊其使用者行銷電子郵件或 e-電子報期間註冊程序，但這會被視為可疑行銷作法是在世界中的電子郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="c554f-185">Some companies make it a practice to automatically sign up their users for marketing emails or e-newsletters during the registration process, but this is considered a questionable marketing practice in the world of email filtering.</span></span>
  
<span data-ttu-id="c554f-186">註冊過程中，如果的"為 [是]，請傳送您的新聞稿給我 」 或 「 為 [是]，請傳送給我特別優惠"] 核取方塊已選取預設，不請密切注意的使用者可能會不小心註冊行銷電子郵件或不是這樣的電子報要接收。</span><span class="sxs-lookup"><span data-stu-id="c554f-186">During the registration process, if the "Yes, please send me your newsletter" or "Yes, please send me special offers" checkbox is selected by default, users who do not pay close attention may unintentionally sign up for marketing email or newsletters that they do not want to receive.</span></span>
  
 <span data-ttu-id="c554f-187">我們建議雙重加入確認程序集選項相反地，這表示行銷電子郵件或電子報的核取方塊會依預設已取消核取。</span><span class="sxs-lookup"><span data-stu-id="c554f-187">We recommend the double opt-in option instead, which means that the checkbox for marketing emails or newsletters is unchecked by default.</span></span> <span data-ttu-id="c554f-188">此外，一旦註冊表單已送出，驗證電子郵件傳送給使用者，並讓他們能確認其決策，以接收行銷電子郵件的 URL。</span><span class="sxs-lookup"><span data-stu-id="c554f-188">Additionally, once the registration form has been submitted, a verification email is sent to the user with a URL that allows them to confirm their decision to receive marketing emails.</span></span> 
  
 <span data-ttu-id="c554f-189">這有助於確保，僅限的使用者想要接收行銷電子郵件已註冊之電子郵件，隨後清除任何可疑的電子郵件行銷作法傳送公司。</span><span class="sxs-lookup"><span data-stu-id="c554f-189">This helps ensure that only those users who want to receive marketing email are signed up for the emails, subsequently clearing the sending company of any questionable email marketing practices.</span></span> 
  
### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a><span data-ttu-id="c554f-190">確保電子郵件訊息內容是透明和追蹤</span><span class="sxs-lookup"><span data-stu-id="c554f-190">Ensure that email message content is transparent and traceable</span></span>

<span data-ttu-id="c554f-191">同樣重要會傳送電子郵件的方式是所包含的內容。</span><span class="sxs-lookup"><span data-stu-id="c554f-191">Just as important as the way the emails are sent is the content they contain.</span></span> <span data-ttu-id="c554f-192">當建立電子郵件內容，請使用下列最佳作法以確保您的電子郵件未標示的電子郵件篩選服務：</span><span class="sxs-lookup"><span data-stu-id="c554f-192">When creating email content, use the following best practices to ensure that your emails will not be flagged by email filtering services:</span></span>
  
- <span data-ttu-id="c554f-193">當電子郵件訊息要求收件者加入通訊錄中的寄件者，它應該清楚狀態，這類巨集指令並不保證郵件的傳遞。</span><span class="sxs-lookup"><span data-stu-id="c554f-193">When the email message requests that recipients add the sender to the address book, it should clearly state that such action is not a guarantee of delivery.</span></span>
    
- <span data-ttu-id="c554f-194">郵件內文中包含的重新導向應該類似和一致，且不多，具有不同。</span><span class="sxs-lookup"><span data-stu-id="c554f-194">Redirects included in the body of the message should be similar and consistent, and not multiple and varied.</span></span> <span data-ttu-id="c554f-195">在此上下文中重新導向是指開訊息，例如連結與文件的任何值。</span><span class="sxs-lookup"><span data-stu-id="c554f-195">A redirect in this context is anything that points away from the message, such as links and documents.</span></span> <span data-ttu-id="c554f-196">如果您有很多廣告或取消訂閱連結或更新設定檔的連結，請他們應該所有指向相同的網域。</span><span class="sxs-lookup"><span data-stu-id="c554f-196">If you have a lot of advertising or Unsubscribe links or Update the Profile links, they should all point to the same domain.</span></span> <span data-ttu-id="c554f-197">例如：</span><span class="sxs-lookup"><span data-stu-id="c554f-197">For example:</span></span>
    
    <span data-ttu-id="c554f-198">修正</span><span class="sxs-lookup"><span data-stu-id="c554f-198">Correct</span></span>
    
     `unsubscribe.bulkmailer.com`
    
     `profile.bulkmailer.com`
    
     `options.bulkmailer.com`
    
    <span data-ttu-id="c554f-199">不正確</span><span class="sxs-lookup"><span data-stu-id="c554f-199">Incorrect</span></span>
    
     `unsubscribe.bulkmailer.com`
    
     `profiles.excite.com`
    
     `options.yahoo.com`
    
- <span data-ttu-id="c554f-200">避免使用大型影像和附件，或是察覺組成映像的郵件內容。</span><span class="sxs-lookup"><span data-stu-id="c554f-200">Avoid content with large images and attachments, or messages that are solely composed of an image.</span></span>
    
- <span data-ttu-id="c554f-201">您的公眾隱私權或 P3P 設定應該清楚狀態追蹤像素 （web bug 或指標） 的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="c554f-201">Your public privacy or P3P settings should clearly state the presence of tracking pixels (web bugs or beacons).</span></span>
    
### <a name="remove-incorrect-email-aliases-from-your-databases"></a><span data-ttu-id="c554f-202">從資料庫移除不正確的電子郵件別名</span><span class="sxs-lookup"><span data-stu-id="c554f-202">Remove incorrect email aliases from your databases</span></span>

<span data-ttu-id="c554f-203">在您建立退回後的資料庫中的任何電子郵件別名不是必要的並透過電子郵件篩選服務將外寄的電子郵件放在進一步審查的風險。</span><span class="sxs-lookup"><span data-stu-id="c554f-203">Any email alias in your database that creates a bounce-back is unnecessary and puts your outbound emails at risk for further scrutiny by email filtering services.</span></span> <span data-ttu-id="c554f-204">請確定您的電子郵件資料庫是最新狀態。</span><span class="sxs-lookup"><span data-stu-id="c554f-204">Ensure that your email database is up-to-date.</span></span>
  

