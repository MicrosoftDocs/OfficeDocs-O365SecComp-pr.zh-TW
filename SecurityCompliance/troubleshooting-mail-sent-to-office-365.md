---
title: 將疑難排解郵件傳送艮 Office 365
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 5/2/2016
ms.audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
ms.collection:
- M365-security-compliance
description: 本文提供寄件者嘗試傳送電子郵件給收件匣中 Office 365 與大量郵件給 Office 365 客戶的最佳作法時所發生問題的疑難排解的資訊。
ms.openlocfilehash: cfb3901b930b63ef8a33391c673a32a73eaa1b07
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30276293"
---
# <a name="troubleshooting-mail-sent-to-office-365"></a><span data-ttu-id="c788f-103">將疑難排解郵件傳送艮 Office 365</span><span class="sxs-lookup"><span data-stu-id="c788f-103">Troubleshooting mail sent to Office 365</span></span>

<span data-ttu-id="c788f-104">本文提供寄件者嘗試傳送電子郵件給收件匣中 Office 365 與大量郵件給 Office 365 客戶的最佳作法時所發生問題的疑難排解的資訊。</span><span class="sxs-lookup"><span data-stu-id="c788f-104">This article provides troubleshooting information for senders who are experiencing issues when trying to send email to inboxes in Office 365 and best practices for bulk mailing to Office 365 customers.</span></span>
  
## <a name="troubleshooting-common-problems-with-mail-delivery-to-office-365"></a><span data-ttu-id="c788f-105">疑難排解 Office 365 的郵件傳遞的常見問題</span><span class="sxs-lookup"><span data-stu-id="c788f-105">Troubleshooting common problems with mail delivery to Office 365</span></span>

<span data-ttu-id="c788f-106">選擇其中一個這些常遇到的問題。</span><span class="sxs-lookup"><span data-stu-id="c788f-106">Choose from one of these commonly encountered issues.</span></span>
  
- [<span data-ttu-id="c788f-107">您管理 IP 和網域的已傳送信譽吗？</span><span class="sxs-lookup"><span data-stu-id="c788f-107">Are you managing your IP and domain's sending reputation?</span></span>](troubleshooting-mail-sent-to-office-365.md#ManageRep)
    
- [<span data-ttu-id="c788f-108">是您傳送電子郵件從新的 IP 位址吗？</span><span class="sxs-lookup"><span data-stu-id="c788f-108">Are you sending email from new IP addresses?</span></span>](troubleshooting-mail-sent-to-office-365.md#NewIPs)
    
- [<span data-ttu-id="c788f-109">確認您的 DNS 設定正確</span><span class="sxs-lookup"><span data-stu-id="c788f-109">Confirm that your DNS is set up correctly</span></span>](troubleshooting-mail-sent-to-office-365.md#ConfirmDNSsetup)
    
- [<span data-ttu-id="c788f-110">請確定該您不要未通告自行為非路由傳送的 IP</span><span class="sxs-lookup"><span data-stu-id="c788f-110">Ensure that you do not advertise yourself as a non-routable IP</span></span>](troubleshooting-mail-sent-to-office-365.md#NoReverseDNS)
    
- [<span data-ttu-id="c788f-111">您收到未傳遞回報 (NDR) 時傳送電子郵件給 Office 365 的使用者</span><span class="sxs-lookup"><span data-stu-id="c788f-111">You received a non-delivery report (NDR) when sending email to a user in Office 365</span></span>](troubleshooting-mail-sent-to-office-365.md#NDRInbound)
    
- [<span data-ttu-id="c788f-112">在 EOP 中的收件者垃圾資料夾中的 「 我的電子郵件登陸</span><span class="sxs-lookup"><span data-stu-id="c788f-112">My email landed in the recipient's junk folder in EOP</span></span>](troubleshooting-mail-sent-to-office-365.md#JunkMailBox)
    
- [<span data-ttu-id="c788f-113">從我的 IP 位址的流量會由 EOP 節流的處理</span><span class="sxs-lookup"><span data-stu-id="c788f-113">Traffic from my IP address is throttled by EOP</span></span>](troubleshooting-mail-sent-to-office-365.md#AllowEOPIPs)
    
### <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a><span data-ttu-id="c788f-114">您管理 IP 和網域的已傳送信譽吗？</span><span class="sxs-lookup"><span data-stu-id="c788f-114">Are you managing your IP and domain's sending reputation?</span></span>
<span data-ttu-id="c788f-115"><a name="ManageRep"> </a></span><span class="sxs-lookup"><span data-stu-id="c788f-115"></span></span>

<span data-ttu-id="c788f-p101">EOP 篩選技術的設計被用來提供的 Microsoft Office 365 與 Exchange Server、 Microsoft Office Outlook 和 Windows Live Mail 像其他 Microsoft 產品的反垃圾郵件保護設定。我們也運用 SPF、 DKIM，以及 DMARC;電子郵件詐騙和網路釣魚問題說明地址的驗證技術來確認網域傳送的電子郵件有權執行這項操作。數目相關的傳送端 IP、 網域、 驗證、 清單正確性、 抱怨率、 內容及其他因素會影響 EOP 篩選。這些，其中一個主要因素下寄件者信譽主導和其能夠傳送電子郵件是其垃圾郵件抱怨速率。</span><span class="sxs-lookup"><span data-stu-id="c788f-p101">EOP filtering technologies are designed to provide anti-spam protections for Microsoft Office 365 as well as other Microsoft products like Exchange Server, Microsoft Office Outlook, and Windows Live Mail. We also leverage SPF, DKIM, and DMARC; email authentication technologies that help address the problem of spoofing and phishing by verifying that the domain sending the email is authorized to do so. EOP filtering is influenced by a number of factors related to the sending IP, domain, authentication, list accuracy, complaint rates, content and more. Of these, one of the principal factors in driving down a sender's reputation and their ability to deliver email is their junk email complaint rate.</span></span> 
  
### <a name="are-you-sending-email-from-new-ip-addresses"></a><span data-ttu-id="c788f-120">是您傳送電子郵件從新的 IP 位址吗？</span><span class="sxs-lookup"><span data-stu-id="c788f-120">Are you sending email from new IP addresses?</span></span>
<span data-ttu-id="c788f-121"><a name="NewIPs"> </a></span><span class="sxs-lookup"><span data-stu-id="c788f-121"></span></span>

<span data-ttu-id="c788f-p102">IP 位址不先前用來傳送電子郵件通常不需要我們系統中的內建任何信譽。因此，從新的 Ip 的電子郵件是很可能會遇到傳遞問題。一旦 IP 具有內建未傳送垃圾郵件的聲譽、 EOP 通常會允許較佳的電子郵件傳遞經驗。</span><span class="sxs-lookup"><span data-stu-id="c788f-p102">IP addresses not previously used to send email typically don't have any reputation built up in our systems. As a result, emails from new IPs are more likely to experience delivery issues. Once the IP has built a reputation for not sending spam, EOP will typically allow for a better email delivery experience.</span></span>
  
<span data-ttu-id="c788f-p103">通常會驗證在現有 SPF 記錄下方的網域新增的新 Ip 體驗新增的繼承網域的傳送端信譽的一些優點。如果您的網域具有良好傳送信譽新 Ip 可能會遇到速度較快費時。新的 IP 將能感受到完全 ramped 內幾週或更早根據磁碟區、 清單正確性和垃圾郵件抱怨率。</span><span class="sxs-lookup"><span data-stu-id="c788f-p103">New IPs that are added for domains that are authenticated under existing SPF records typically experience the added benefit of inheriting some of the domain's sending reputation. If your domain has a good sending reputation new IPs may experience a faster ramp up time. A new IP can expect to be fully ramped within a couple of weeks or sooner depending on volume, list accuracy, and junk email complaint rates.</span></span>
  
### <a name="confirm-that-your-dns-is-set-up-correctly"></a><span data-ttu-id="c788f-128">確認您的 DNS 設定正確</span><span class="sxs-lookup"><span data-stu-id="c788f-128">Confirm that your DNS is set up correctly</span></span>
<span data-ttu-id="c788f-129"><a name="ConfirmDNSsetup"> </a></span><span class="sxs-lookup"><span data-stu-id="c788f-129"></span></span>

<span data-ttu-id="c788f-130">如需如何建立及維護 DNS 記錄，其中包括所需的郵件路由、 MX 記錄的指示您必須連絡您的 DNS 主機供應商。</span><span class="sxs-lookup"><span data-stu-id="c788f-130">For instructions about how to create and maintain DNS records, including the MX record required for mail routing, you will need to contact your DNS hosting provider.</span></span>
  
### <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a><span data-ttu-id="c788f-131">請確定該您不要未通告自行為非路由傳送的 IP</span><span class="sxs-lookup"><span data-stu-id="c788f-131">Ensure that you do not advertise yourself as a non-routable IP</span></span>
<span data-ttu-id="c788f-132"><a name="NoReverseDNS"> </a></span><span class="sxs-lookup"><span data-stu-id="c788f-132"></span></span>

<span data-ttu-id="c788f-p104">我們可以不接受電子郵件的寄件者失敗反向 DNS 查閱。在某些情況下，合法的寄件者 advertise 其本身不正確地為非網際網路路由傳送 IP 嘗試開啟的連線至 EOP 時。保留供私人 （非可路由） 網路的 IP 位址包括：</span><span class="sxs-lookup"><span data-stu-id="c788f-p104">We may not accept email from senders who fail a reverse-DNS lookup. In some cases, legitimate senders advertise themselves incorrectly as a non-internet routable IP when attempting to open a connection to EOP. IP addresses that are reserved for private (non-routable) networking include:</span></span>
  
- <span data-ttu-id="c788f-136">192.168.0.0/16 (或 192.168.0.0-192.168.255.255)</span><span class="sxs-lookup"><span data-stu-id="c788f-136">192.168.0.0/16 (or 192.168.0.0 - 192.168.255.255)</span></span>
    
- <span data-ttu-id="c788f-137">10.0.0.0/8 (或 10.0.0.0-10.255.255.255)</span><span class="sxs-lookup"><span data-stu-id="c788f-137">10.0.0.0/8 (or 10.0.0.0 - 10.255.255.255)</span></span>
    
- <span data-ttu-id="c788f-138">172.16.0.0/11 (或 172.16.0.0-172.31.255.255)</span><span class="sxs-lookup"><span data-stu-id="c788f-138">172.16.0.0/11 (or 172.16.0.0 - 172.31.255.255)</span></span>
    
### <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a><span data-ttu-id="c788f-139">您收到未傳遞回報 (NDR) 時傳送電子郵件給 Office 365 的使用者</span><span class="sxs-lookup"><span data-stu-id="c788f-139">You received a non-delivery report (NDR) when sending email to a user in Office 365</span></span>
<span data-ttu-id="c788f-140"><a name="NDRInbound"> </a></span><span class="sxs-lookup"><span data-stu-id="c788f-140"></span></span>

<span data-ttu-id="c788f-p105">一些傳遞問題是由 Microsoft 遭封鎖的寄件者的 IP 位址的結果或因為的使用者帳戶識別為由於上述的垃圾郵件活動而禁用寄件者。如果您有收到錯誤 NDR，先遵循解決問題的 NDR 郵件中的任何指示。</span><span class="sxs-lookup"><span data-stu-id="c788f-p105">Some delivery issues are the result of the sender's IP address being blocked by Microsoft or because the user account is identified as banned sender due to previous spam activity. If you believe that you have received the NDR in error, first follow any instructions in the NDR message to resolve the issue.</span></span> 
  
<span data-ttu-id="c788f-143">在您收到的錯誤的詳細資訊，請參閱中[的 Dsn 和 Ndr 內部部署 Exchange 2013 和 Office 365 中](http://technet.microsoft.com/library/8e91de84-76fa-49b2-898c-c5eface76560.aspx)的 SMTP 錯誤碼的完整清單。</span><span class="sxs-lookup"><span data-stu-id="c788f-143">For more information about the error you received, see the complete list of SMTP error codes in [DSNs and NDRs in On-Premises Exchange 2013 and Office 365](http://technet.microsoft.com/library/8e91de84-76fa-49b2-898c-c5eface76560.aspx).</span></span>
  
 <span data-ttu-id="c788f-144">例如，如果您收到下列 NDR，即表示傳送端 IP 位址已封鎖 microsoft。</span><span class="sxs-lookup"><span data-stu-id="c788f-144">For example, if you receive the following NDR, it indicates that the sending IP address was blocked by Microsoft.</span></span> 
  
 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`
  
<span data-ttu-id="c788f-145">若要要求從這份清單的 [移除]，您可以[使用 delist 入口網站來將自己從 Office 365 封鎖的寄件者清單中移除](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)。</span><span class="sxs-lookup"><span data-stu-id="c788f-145">To request removal from this list, you can [Use the delist portal to remove yourself from the Office 365 blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>
  
### <a name="my-email-landed-in-the-recipients-junk-folder-in-eop"></a><span data-ttu-id="c788f-146">在 EOP 中的收件者垃圾資料夾中的 「 我的電子郵件登陸</span><span class="sxs-lookup"><span data-stu-id="c788f-146">My email landed in the recipient's junk folder in EOP</span></span>
<span data-ttu-id="c788f-147"><a name="JunkMailBox"> </a></span><span class="sxs-lookup"><span data-stu-id="c788f-147"></span></span>

<span data-ttu-id="c788f-p106">如果透過 EOP 錯誤訊息識別為垃圾郵件，您可以使用送出這個誤判郵件給 Microsoft 垃圾郵件分析小組，將評估和分析之郵件的收件者。根據此分析結果，整個服務的垃圾郵件內容篩選規則可能會調整以允許透過訊息。您可以使用電子郵件來提交給 Microsoft 的不應歸類為垃圾郵件的郵件。時這麼做，請務必使用下列程序中的步驟。</span><span class="sxs-lookup"><span data-stu-id="c788f-p106">If a message was incorrectly identified as spam by EOP, you can work with the recipient to submit this false positive message to the Microsoft Spam Analysis Team, who will evaluate and analyze the message. Depending on the results of the analysis, the service-wide spam content filter rules may be adjusted to allow the message through. You use email to submit messages to Microsoft that should not be classified as spam. When doing so, be sure to use the steps in the following procedure.</span></span>
  
### <a name="to-use-email-to-submit-false-positive-messages-to-the-microsoft-spam-analysis-team"></a><span data-ttu-id="c788f-152">若要使用電子郵件來提交誤判的郵件到 Microsoft 垃圾郵件分析小組</span><span class="sxs-lookup"><span data-stu-id="c788f-152">To use email to submit false positive messages to the Microsoft Spam Analysis Team</span></span>

1. <span data-ttu-id="c788f-153">儲存您想要當作非垃圾郵件提交的郵件。</span><span class="sxs-lookup"><span data-stu-id="c788f-153">Save the message you want to submit as non-spam.</span></span>
    
2. <span data-ttu-id="c788f-154">建立新的空白郵件，然後在其中附加非垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="c788f-154">Create a new, blank message and attach the non-spam message to it.</span></span>
    
    <span data-ttu-id="c788f-155">您可以在必要時附加多個非垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="c788f-155">You can attach multiple non-spam messages if needed.</span></span>
    
3. <span data-ttu-id="c788f-156">複製原始郵件的主旨行並貼到新郵件的主旨行中。</span><span class="sxs-lookup"><span data-stu-id="c788f-156">Copy and paste the original message subject line into the new message subject line.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c788f-157">將新郵件的內文保留空白。</span><span class="sxs-lookup"><span data-stu-id="c788f-157">Leave the body of the new message empty.</span></span> 
  
4. <span data-ttu-id="c788f-158">將新郵件傳送到 [not_junk@office365.microsoft.com](mailto:not_junk@office365.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="c788f-158">Send your new message to [not_junk@office365.microsoft.com](mailto:not_junk@office365.microsoft.com).</span></span>
    
### <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a><span data-ttu-id="c788f-159">從我的 IP 位址的流量會由 EOP 節流的處理</span><span class="sxs-lookup"><span data-stu-id="c788f-159">Traffic from my IP address is throttled by EOP</span></span>
<span data-ttu-id="c788f-160"><a name="AllowEOPIPs"> </a></span><span class="sxs-lookup"><span data-stu-id="c788f-160"></span></span>

<span data-ttu-id="c788f-161">如果您收到 NDR 中指出的 EOP IP 位址是正在會由節流處理 EOP，例如：</span><span class="sxs-lookup"><span data-stu-id="c788f-161">If you receive an NDR from EOP that indicates that your IP address is being throttled by EOP, for example:</span></span>
  
 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`
  
<span data-ttu-id="c788f-p107">您會收到 NDR 是因為已偵測到可疑活動來自 IP 位址和它已暫時受到限制時所要進一步評估。如果透過評估清除懷疑，則會不久消除這個限制。</span><span class="sxs-lookup"><span data-stu-id="c788f-p107">You received the NDR because suspicious activity has been detected from the IP address and it has been temporarily restricted while it is being further evaluated. If the suspicion is cleared through evaluation, this restriction will be lifted shortly.</span></span>
  
### <a name="i-cant-receive-email-from-senders-in-office-365"></a><span data-ttu-id="c788f-164">我無法接收電子郵件從 Office 365 中的寄件者</span><span class="sxs-lookup"><span data-stu-id="c788f-164">I can't receive email from senders in Office 365</span></span>
<span data-ttu-id="c788f-165"><a name="AllowEOPIPs"> </a></span><span class="sxs-lookup"><span data-stu-id="c788f-165"></span></span>

 <span data-ttu-id="c788f-p108">若要從我們使用者接收郵件，請確定您的網路允許來自 EOP 會使用在我們的資料中心的 IP 位址的連線。如需詳細資訊，請參閱[Exchange Online Protection IP 位址](eop/exchange-online-protection-ip-addresses.md)。</span><span class="sxs-lookup"><span data-stu-id="c788f-p108">In order to receive messages from our users, make sure your network allows connections from the IP addresses that EOP uses in our datacenters. For more information, see [Exchange Online Protection IP addresses](eop/exchange-online-protection-ip-addresses.md).</span></span> 
  
## <a name="best-practices-for-bulk-emailing-to-office-365-users"></a><span data-ttu-id="c788f-168">大量以電子郵件傳送至 Office 365 使用者的最佳作法</span><span class="sxs-lookup"><span data-stu-id="c788f-168">Best practices for bulk emailing to Office 365 users</span></span>
<span data-ttu-id="c788f-169"><a name="BulkMailer"> </a></span><span class="sxs-lookup"><span data-stu-id="c788f-169"></span></span>

<span data-ttu-id="c788f-170">如果您經常進行大量電子郵件活動至 Office 365 使用者並想要確保您的電子郵件送達安全與即時的方式，請遵循本節中的秘訣。</span><span class="sxs-lookup"><span data-stu-id="c788f-170">If you often conduct bulk email campaigns to Office 365 users and want to ensure that your emails arrive in a safe and timely manner, follow the tips in this section.</span></span>
  
### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a><span data-ttu-id="c788f-171">確定 [自： 名稱會反映誰傳送郵件</span><span class="sxs-lookup"><span data-stu-id="c788f-171">Ensure that the From: name reflects who is sending the message</span></span>

<span data-ttu-id="c788f-p109">主旨應何種郵件的簡短摘要是關於、 與郵件內文應該清楚且簡潔地指出可以、 服務或產品功能的相關。例如：</span><span class="sxs-lookup"><span data-stu-id="c788f-p109">The Subject should be a brief summary of what the message is about, and the message body should clearly and succinctly indicate what the offering, service, or product is about. For example:</span></span>
  
<span data-ttu-id="c788f-174">更正</span><span class="sxs-lookup"><span data-stu-id="c788f-174">Correct</span></span>
  
 ` From: marketing@shoppershandbag.com `
  
 `Subject: Updated catalog for the Christmas season!`
  
<span data-ttu-id="c788f-175">不正確</span><span class="sxs-lookup"><span data-stu-id="c788f-175">Incorrect</span></span>
  
 `From: someone@outlook.com`
  
 `Subject: Catalogs`
  
<span data-ttu-id="c788f-176">變得容易讓它知道您屬於人員與您所執行的動作、 較少的難度會有傳遞到大部分的垃圾郵件篩選器。</span><span class="sxs-lookup"><span data-stu-id="c788f-176">The easier you make it for people to know who you are and what you are doing, the less difficulty you will have delivering through most spam filters.</span></span>
  
### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a><span data-ttu-id="c788f-177">一律包含 campaign 電子郵件中的 [取消訂閱選項</span><span class="sxs-lookup"><span data-stu-id="c788f-177">Always include an unsubscribe option in campaign emails</span></span>

<span data-ttu-id="c788f-p110">行銷電子郵件、 特別新聞稿一律應該包含未來的電子郵件從取消訂閱的方式。例如：</span><span class="sxs-lookup"><span data-stu-id="c788f-p110">Marketing emails, especially newsletters, should always include a way of unsubscribing from future emails. For example:</span></span>
  
 `This email was sent to example@contoso.com by sender@fabrikam.com.`
  
 `Update Profile/Email Address | Instant removal with SafeUnsubscribe™ | Privacy Policy`
  
<span data-ttu-id="c788f-p111">某些寄件者包含這個選項需要特定別名與 「 取消訂閱"主旨中傳送電子郵件的收件者。這是不試試至單鍵上例中。如果您選擇不要需要傳送郵件的收件者，請確定當他們按一下 [連結] 時所需的所有欄位都會預先填入。</span><span class="sxs-lookup"><span data-stu-id="c788f-p111">Some senders include this option by requiring recipients to send an email to a certain alias with "Unsubscribe" in the subject. This is not preferable to the one-click example above. If you do choose to require recipients to send a mail, ensure that when they click the link, all the required fields are pre-populated.</span></span>
  
### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a><span data-ttu-id="c788f-183">使用雙重加入確認程序中選項的行銷電子郵件或電子報註冊</span><span class="sxs-lookup"><span data-stu-id="c788f-183">Use the double opt-in option for marketing email or newsletter registration</span></span>

<span data-ttu-id="c788f-p112">如果公司需要或鼓勵使用者將其連絡人資訊登錄才可存取您的產品或服務，建議此業界最佳作法。有些公司讓它自動註冊行銷電子郵件使用者的作法或 e-新聞稿期間註冊程序，但這會被視為在電子郵件篩選的世界的問題行銷作法。</span><span class="sxs-lookup"><span data-stu-id="c788f-p112">This industry best practice is recommended if your company requires or encourages users to register their contact information in order to access your product or services. Some companies make it a practice to automatically sign up their users for marketing emails or e-newsletters during the registration process, but this is considered a questionable marketing practice in the world of email filtering.</span></span>
  
<span data-ttu-id="c788f-186">註冊程序期間如果的"Yes，請將您的電子報傳送我"或"Yes，請傳送我特別優惠"] 核取方塊已選取 [依預設，使用者不會關閉注意所可能不小心註冊行銷電子郵件或不一樣的新聞稿想要接收。</span><span class="sxs-lookup"><span data-stu-id="c788f-186">During the registration process, if the "Yes, please send me your newsletter" or "Yes, please send me special offers" checkbox is selected by default, users who do not pay close attention may unintentionally sign up for marketing email or newsletters that they do not want to receive.</span></span>
  
 <span data-ttu-id="c788f-p113">我們建議雙重加入確認程序中選項而這表示行銷郵件或新聞稿的核取方塊會依預設未核取。此外之後已送出註冊表單，, 驗證電子郵件傳送給 url 以允許他們確認其決策接收行銷郵件使用者。</span><span class="sxs-lookup"><span data-stu-id="c788f-p113">We recommend the double opt-in option instead, which means that the checkbox for marketing emails or newsletters is unchecked by default. Additionally, once the registration form has been submitted, a verification email is sent to the user with a URL that allows them to confirm their decision to receive marketing emails.</span></span> 
  
 <span data-ttu-id="c788f-189">這有助於確保只有那些使用者想要接收行銷電子郵件簽署的電子郵件後續清除行銷作法任何問題電子郵件的傳送端的公司。</span><span class="sxs-lookup"><span data-stu-id="c788f-189">This helps ensure that only those users who want to receive marketing email are signed up for the emails, subsequently clearing the sending company of any questionable email marketing practices.</span></span> 
  
### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a><span data-ttu-id="c788f-190">確認電子郵件訊息內容透明且便於追蹤</span><span class="sxs-lookup"><span data-stu-id="c788f-190">Ensure that email message content is transparent and traceable</span></span>

<span data-ttu-id="c788f-p114">同樣重要會傳送電子郵件的方式就網址中包含的內容。當建立電子郵件的內容，請使用下列最佳作法以確保您的電子郵件未標示的電子郵件篩選服務：</span><span class="sxs-lookup"><span data-stu-id="c788f-p114">Just as important as the way the emails are sent is the content they contain. When creating email content, use the following best practices to ensure that your emails will not be flagged by email filtering services:</span></span>
  
- <span data-ttu-id="c788f-193">當電子郵件要求收件者將寄件者新增至通訊錄、 它應該清楚狀態的這類動作不保證郵件傳遞。</span><span class="sxs-lookup"><span data-stu-id="c788f-193">When the email message requests that recipients add the sender to the address book, it should clearly state that such action is not a guarantee of delivery.</span></span>
    
- <span data-ttu-id="c788f-p115">重新導向郵件的內文中包含應類似和一致的並不多與具有不同。在此上下文中重新導向是指引從郵件，例如連結和文件的任何項目。如果您有許多的廣告或取消訂閱連結或更新設定檔連結，他們應該所有指向相同的網域。例如：</span><span class="sxs-lookup"><span data-stu-id="c788f-p115">Redirects included in the body of the message should be similar and consistent, and not multiple and varied. A redirect in this context is anything that points away from the message, such as links and documents. If you have a lot of advertising or Unsubscribe links or Update the Profile links, they should all point to the same domain. For example:</span></span>
    
    <span data-ttu-id="c788f-198">更正</span><span class="sxs-lookup"><span data-stu-id="c788f-198">Correct</span></span>
    
     `unsubscribe.bulkmailer.com`
    
     `profile.bulkmailer.com`
    
     `options.bulkmailer.com`
    
    <span data-ttu-id="c788f-199">不正確</span><span class="sxs-lookup"><span data-stu-id="c788f-199">Incorrect</span></span>
    
     `unsubscribe.bulkmailer.com`
    
     `profiles.excite.com`
    
     `options.yahoo.com`
    
- <span data-ttu-id="c788f-200">避免使用大的影像和附件，或是察覺組成映像的郵件內容。</span><span class="sxs-lookup"><span data-stu-id="c788f-200">Avoid content with large images and attachments, or messages that are solely composed of an image.</span></span>
    
- <span data-ttu-id="c788f-201">您的公眾隱私權或 P3P 設定應該清楚狀態追蹤像素 （web bug 或指標） 其目前狀態。</span><span class="sxs-lookup"><span data-stu-id="c788f-201">Your public privacy or P3P settings should clearly state the presence of tracking pixels (web bugs or beacons).</span></span>
    
### <a name="remove-incorrect-email-aliases-from-your-databases"></a><span data-ttu-id="c788f-202">從資料庫移除不正確的電子郵件別名</span><span class="sxs-lookup"><span data-stu-id="c788f-202">Remove incorrect email aliases from your databases</span></span>

<span data-ttu-id="c788f-p116">在您建立彈跳後的資料庫中任何電子郵件別名是不必要然後您外寄電子郵件風險的進一步無法在電子郵件篩選服務。請確定您的電子郵件資料庫是最新狀態。</span><span class="sxs-lookup"><span data-stu-id="c788f-p116">Any email alias in your database that creates a bounce-back is unnecessary and puts your outbound emails at risk for further scrutiny by email filtering services. Ensure that your email database is up-to-date.</span></span>
  

