---
title: Office 365 電子郵件的反垃圾郵件保護
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
description: 了解反垃圾郵件設定和篩選可協助您避免在 Exchange Online 與 Office 365 中的垃圾郵件。取得 Office 365 太多垃圾郵件吗？您可以自訂您的垃圾郵件篩選和反垃圾郵件原則設定。
ms.openlocfilehash: 2d8f433cabda4408da2e29b7bc6570e09e6989dd
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223422"
---
# <a name="office-365-email-anti-spam-protection"></a><span data-ttu-id="64648-105">Office 365 電子郵件的反垃圾郵件保護</span><span class="sxs-lookup"><span data-stu-id="64648-105">Office 365 email anti-spam protection</span></span>

<span data-ttu-id="64648-p102">您擔心太多 Office 365 中的垃圾郵件吗？我們已內建多個垃圾郵件篩選您的 Office 365 或 Exchange Online Protection (EOP) 服務，因此從您會收到您第一封郵件可用來保護電子郵件。以協助防止 Office 365 中的垃圾郵件，您可能會想要變更保護設定來處理您的組織中的特定問題 — 說出您要接收來自特定寄件者許多的垃圾郵件例如 — 或至只可調整您的設定，讓它們自訂最佳開會組織的需求。為達成此目的，您可以變更 Office 365 安全性的反垃圾郵件設定&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="64648-p102">Are you concerned about too much spam in Office 365? We've built multiple spam filters into your Office 365 or Exchange Online Protection (EOP) service, so your email is protected from the moment you receive your first message. In order to help prevent spam in Office 365, you may want to change a protection setting to deal with a specific issue in your organization—say you're receiving a lot of spam from a particular sender, for example—or to simply fine tune your settings so that they're tailored to best meet the needs of your organization. To do this, you can change anti-spam settings in the Office 365 Security &amp; Compliance Center.</span></span>
  
<span data-ttu-id="64648-p103">本文適用於 Office 365 系統管理員的。如果您不是系統管理員，但您是 Office 365 使用者，您想要了解如何處理垃圾郵件您收到這不是您在這裡尋找文章。但是，如果您使用的 PC Outlook 或 Outlook for Mac，開始使用[垃圾郵件篩選工具的概觀](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)。如果您使用 Outlook web 上的，開始使用[了解垃圾郵件和網路釣魚](https://support.office.com/article/86c1d76f-4d5a-4967-9647-35665dc17c31)。</span><span class="sxs-lookup"><span data-stu-id="64648-p103">This article is intended for Office 365 administrators. If you're not an administrator, but you are an Office 365 user and you want to learn how to deal with spam you receive, this isn't the article you're looking for. Instead, if you use Outlook for PC or Outlook for Mac, start with [Overview of the Junk Email Filter](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089). If you use Outlook on the web, start with [Learn about junk email and phishing](https://support.office.com/article/86c1d76f-4d5a-4967-9647-35665dc17c31).</span></span>
  
## <a name="these-options-help-you-prevent-spam-in-office-365"></a><span data-ttu-id="64648-114">這些選項可協助您避免在 Office 365 中的垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="64648-114">These options help you prevent spam in Office 365</span></span>

 <span data-ttu-id="64648-p104">**連線篩選。** 當您使用的連線篩選時，Office 365 檢查允許取得訊息之前的寄件者信譽。您可以建立的 [允許] 清單或安全的寄件者] 清單中，以確保您收到來自特定 IP 位址或 IP 位址範圍傳送給您每封郵件。您也可以建立用來封鎖郵件，稱為封鎖清單中的 IP 位址清單。如需詳細資訊，請參閱[設定連線篩選原則](https://technet.microsoft.com/library/jj200718%28v=exchg.150%29.aspx)。如果您擔心在 Office 365 中的垃圾郵件，請使用連線以協助防止垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="64648-p104">**Connection filtering.** When you use connection filtering, Office 365 checks the reputation of the sender before allowing a message to get through. You can create an allow list, or safe sender list, to make sure you receive every message sent to you from a specific IP address or IP address range. You can also create a list of IP addresses from which to block messages, called a block list. For more information, see [Configure the Connection Filter Policy](https://technet.microsoft.com/library/jj200718%28v=exchg.150%29.aspx). If you're concerned about spam in Office 365, use connection filtering to help prevent spam.</span></span>
  
<span data-ttu-id="64648-p105">如有 Office 365 企業版 E5 或已購買進階威脅保護 (ATP) 授權客戶、 連線篩選用以詐騙智慧建立允許與封鎖的寄件者詐騙網域的清單。如需詳細資訊，請參閱[了解更多關於詐騙智慧](https://go.microsoft.com/fwlink/?LinkID=735009)。</span><span class="sxs-lookup"><span data-stu-id="64648-p105">For customers who have Office 365 Enterprise E5 or have purchased Advanced Threat Protection (ATP) licenses, connection filtering is used by spoof intelligence to create allow and block lists of senders who are spoofing your domain. For more information, see [Learn more about spoof intelligence](https://go.microsoft.com/fwlink/?LinkID=735009).</span></span>
  
 <span data-ttu-id="64648-p106">**垃圾郵件篩選。** Office 365 的郵件特性與垃圾郵件一致使用檢查垃圾郵件篩選。您可以變更會被識別為垃圾郵件的郵件上進行，並選擇是否要篩選以特定語言編寫或寄自特定國家或地區的郵件的動作。您也可以開啟進階垃圾郵件篩選選項，如果您想要執行及垃圾郵件篩選不積極方法。此外，您可以設定使用者垃圾郵件通知時對象為他們的訊息傳送至隔離區改用通知使用者。（將郵件傳送至隔離區是其中一個可設定的動作）。從這些通知，使用者可以釋出誤判並向 Microsoft 報告進行分析。如需詳細資訊，請參閱[設定垃圾郵件篩選器原則](https://go.microsoft.com/fwlink/p/?LinkId=617147)。若要協助防止 Office 365 中的垃圾郵件，請使用垃圾郵件篩選，如果您擔心太多 Office 365 中的垃圾郵件、 使用連線以協助防止垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="64648-p106">**Spam filtering.** Office 365 checks for message characteristics consistent with spam by using spam filtering. You can change what actions to take on messages identified as spam, and choose whether to filter messages written in specific languages, or sent from specific countries or regions. You can also turn on advanced spam filtering options if you want to pursue an aggressive approach to spam filtering. Additionally, you can configure end-user spam notifications to inform users when messages intended for them were sent to the quarantine instead. (Sending messages to the quarantine is one of the configurable actions.) From these notifications, end users can release false positives and report them to Microsoft for analysis. For more information, see [Configure your spam filter policies](https://go.microsoft.com/fwlink/p/?LinkId=617147). In order to help prevent spam in Office 365, use spam filtering, if you're concerned about too much spam in Office 365, use connection filtering to help prevent spam.</span></span>
  
> [!NOTE]
> <span data-ttu-id="64648-p107">如 EOP 獨立版客戶： 根據預設，EOP 垃圾郵件篩選器將垃圾郵件偵測到的郵件傳送至每個收件者的垃圾郵件] 資料夾。不過，以確保**將郵件移至 [垃圾郵件] 資料夾**動作將會使用內部部署信箱，您必須設定兩個 Exchange 傳輸規則來偵測垃圾郵件標頭新增 EOP 的內部部署伺服器上。如需詳細資訊，請參閱[確定垃圾郵件會路由傳送至每位使用者的垃圾郵件] 資料夾](https://technet.microsoft.com/library/jj837173%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="64648-p107">For EOP standalone customers: By default, the EOP spam filters send spam-detected messages to each recipients' Junk Email folder. However, in order to ensure that the **Move message to Junk Email folder** action will work with on-premises mailboxes, you must configure two Exchange transport rules on your on-premises servers to detect spam headers added by EOP. For details, see [Ensure that spam is routed to each user's Junk Email folder](https://technet.microsoft.com/library/jj837173%28v=exchg.150%29.aspx).</span></span> 
  
## <a name="extra-information-if-you-receive-too-much-spam-in-office-365"></a><span data-ttu-id="64648-134">如果您在 Office 365 中收到太多垃圾郵件的額外資訊</span><span class="sxs-lookup"><span data-stu-id="64648-134">Extra information if you receive too much spam in Office 365</span></span>

<span data-ttu-id="64648-135">下列視訊提供設定垃圾郵件篩選 EOP 中的概觀。</span><span class="sxs-lookup"><span data-stu-id="64648-135">The following video provides an overview of configuring spam filtering in EOP.</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/608be94c-d763-4c47-af94-99e7cb277713?autoplay=false]
  
<span data-ttu-id="64648-136">如需詳細資訊，請參閱 ＜ [Configure 垃圾郵件篩選器原則](https://go.microsoft.com/fwlink/p/?LinkId=617147)主題。</span><span class="sxs-lookup"><span data-stu-id="64648-136">For more details, see the [Configure spam filter policies](https://go.microsoft.com/fwlink/p/?LinkId=617147) topic.</span></span>
  
## <a name="check-your-outgoing-messages-to-prevent-spam-in-office-365"></a><span data-ttu-id="64648-137">檢查您的外寄郵件以避免在 Office 365 中的垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="64648-137">Check your outgoing messages to prevent spam in Office 365</span></span>

 <span data-ttu-id="64648-p108">**輸出篩選。** Office 365 也進行檢查以確認您的使用者對外傳送垃圾郵件。例如，使其傳送垃圾郵件，讓我們建立呼叫*輸出篩選*的理想的惡意程式碼可能會取得感染使用者的電腦。您無法關閉輸出篩選，但是您可以設定[設定輸出垃圾郵件原則](https://technet.microsoft.com/library/jj200737%28v=exchg.150%29.aspx)所述的設定。如果您擔心太多 Office 365 中的垃圾郵件，用於輸出篩選協助防止在 Exchange Online 中的垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="64648-p108">**Outbound filtering.** Office 365 also checks to make sure that your users don't send spam. For instance, a user's computer may get infected with malware that causes it to send spam messages, so we build protection against that called  *outbound filtering*  . You can't turn off outbound filtering, but you can configure the settings described in [Configure the outbound spam policy](https://technet.microsoft.com/library/jj200737%28v=exchg.150%29.aspx). If you're concerned about too much spam in Office 365, use outbound filtering to help prevent spam in Exchange Online.</span></span>
  
## <a name="beyond-the-basics-more-ways-to-prevent-spam-in-office-365"></a><span data-ttu-id="64648-143">超過基本概念： 若要防止在 Office 365 中的垃圾郵件更多的方式</span><span class="sxs-lookup"><span data-stu-id="64648-143">Beyond the basics: More ways to prevent spam in Office 365</span></span>

 <span data-ttu-id="64648-p109">**郵件流程規則。** 如果您想要超越內建的垃圾郵件篩選及建立自訂規則的企業原則、*[郵件流程規則](https://technet.microsoft.com/library/jj919238%28v=exchg.150%29.aspx)*，也稱為*傳輸規則*根據、 會協助您的另一個篩選器會防止在 Office 365 中的垃圾郵件。例如，您可用於郵件流程規則中[使用設定垃圾郵件信賴等級 (SCL) 中的郵件的郵件流程規則](https://technet.microsoft.com/library/dn798345%28v=exchg.150%29.aspx)所述設定的垃圾郵件信賴等級 (SCL) 值符合特定條件的郵件。</span><span class="sxs-lookup"><span data-stu-id="64648-p109">**Mail flow rules.** If you want to go beyond built-in spam filtering and create custom rules that are based on your business policies,  *[mail flow rules](https://technet.microsoft.com/library/jj919238%28v=exchg.150%29.aspx)*, also called  *transport rules*, are another filter that help you prevent spam in Office 365. For example, you can use mail flow rules to set the spam confidence level (SCL) value for messages that match specific conditions, as described in [Use mail flow rules to set the spam confidence level (SCL) in messages](https://technet.microsoft.com/library/dn798345%28v=exchg.150%29.aspx).</span></span>
  
 <span data-ttu-id="64648-p110">**電子郵件的驗證。** 使用網域名稱系統 (DNS) 將可驗證資訊新增至相關的電子郵件寄件者的電子郵件訊息的技術稱為電子郵件的驗證。系統管理員可以進行更進階的 Office 365 使用這些電子郵件的驗證方法：</span><span class="sxs-lookup"><span data-stu-id="64648-p110">**Email authentication.** Techniques that use the Domain Name System (DNS) to add verifiable information to email messages about the sender of an email message are called email authentication. More advanced Office 365 admins can make use of these email authentication methods:</span></span>
  
- <span data-ttu-id="64648-p111">**寄件者原則架構 (SPF)。** SPF 驗證確認對 alleged 的傳送端網域擁有者的寄件者的 IP 位址的電子郵件訊息的原點而言。快速介紹 SPF 以及要取得其快速地設定，請參閱[Set up SPF 避免詐騙的 Office 365 中](https://technet.microsoft.com/library/dn789058%28v=exchg.150%29.aspx)。更深入了解 Office 365 如何使用 SPF，或者例如混合部署的疑難排解或非標準部署開始使用[Office 365 如何使用寄件者原則架構 (SPF) 若要防止詐騙](https://technet.microsoft.com/library/mt712724%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="64648-p111">**Sender Policy Framework (SPF).** SPF validates the origin of email messages by verifying the IP address of the sender against the alleged owner of the sending domain. For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Office 365 to help prevent spoofing](https://technet.microsoft.com/library/dn789058%28v=exchg.150%29.aspx). For a more in-depth understanding of how Office 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](https://technet.microsoft.com/library/mt712724%28v=exchg.150%29.aspx).</span></span>

- <span data-ttu-id="64648-p112">**DomainKeys 識別郵件 (DKIM)。** DKIM 可讓您附加至您傳送電子郵件訊息標頭中的電子郵件的數位簽章。從您的網域接收電子郵件的電子郵件系統來決定其接收內送電子郵件是否合法使用此數位簽章。如需 DKIM 與 Office 365 的資訊，請參閱[使用 DKIM 驗證自 Office 365 中您網域傳送的輸出電子郵件](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="64648-p112">**DomainKeys Identified Mail (DKIM).** DKIM lets you attach a digital signature to email messages in the message header of emails you send. Email systems that receive email from your domain use this digital signature to determine if incoming email that they receive is legitimate. For information about DKIM and Office 365, see [Use DKIM to validate outbound email sent from your domain in Office 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx).</span></span>

- <span data-ttu-id="64648-p113">**網域式訊息驗證、 報告和符合性 (DMARC)。** 接收的郵件系統的 DMARC 協助決定如何處理失敗 SPF 或 DKIM 檢查，並提供其他的信任層級的電子郵件協力廠商的郵件。如需設定 DMARC 資訊，請參閱[使用 DMARC 來驗證 Office 365 中的電子郵件](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="64648-p113">**Domain-based Message Authentication, Reporting, and Conformance (DMARC).** DMARC helps receiving mail systems determine what to do with messages that fail SPF or DKIM checks and provides another level of trust for your email partners. For information on setting up DMARC, see [Use DMARC to validate email in Office 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).</span></span>

<span data-ttu-id="64648-161">如果您擔心垃圾郵件、 網路釣魚和詐騙 Office 365 中，使用 SPF、 DKIM、 和 DMARC 一起以協助防止垃圾郵件和詐騙不想要。</span><span class="sxs-lookup"><span data-stu-id="64648-161">If you're concerned about spam, phishing, and spoofing in Office 365, use SPF, DKIM, and DMARC together to help prevent spam and unwanted spoofing.</span></span>
  
 <span data-ttu-id="64648-p114">**使用者受管理的設定。** 如果您正在尋找使用者如何管理自己的垃圾郵件設定的相關資訊，查看[概觀垃圾郵件篩選工具](https://go.microsoft.com/fwlink/?LinkId=270065)（適用於 Microsoft Outlook 使用者） 或[解垃圾郵件和網路釣魚](https://go.microsoft.com/fwlink/?LinkId=270068)（適用於 web 使用者在 Outlook)。如果您使用 EOP 來保護內部部署信箱，請務必以確保這些設定會同步處理至服務使用目錄同步處理。如需設定目錄同步作業的詳細資訊，請參閱在[EOP 中的管理郵件使用者](https://technet.microsoft.com/library/dn636911%28v=exchg.150%29.aspx)的 「 使用目錄同步作業管理郵件使用者 」。</span><span class="sxs-lookup"><span data-stu-id="64648-p114">**End-user managed settings.** If you're looking for information about how end users can manage their own spam settings, check out [Overview of the Junk Email Filter](https://go.microsoft.com/fwlink/?LinkId=270065) (for Microsoft Outlook users) or [Learn about Junk email and phishing](https://go.microsoft.com/fwlink/?LinkId=270068) (for Outlook on the web users). If you're using EOP to protect on-premises mailboxes, be sure to use directory synchronization to ensure that these settings are synced to the service. For more information about setting up directory synchronization, see "Use directory synchronization to manage mail users" in [Manage mail users in EOP](https://technet.microsoft.com/library/dn636911%28v=exchg.150%29.aspx).</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="64648-166">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="64648-166">For more information</span></span>

[<span data-ttu-id="64648-167">部落格： 為什麼沒有垃圾郵件和網路釣魚取得透過 Office 365？</span><span class="sxs-lookup"><span data-stu-id="64648-167">Blog: Why does spam and phishing get through Office 365?</span></span>](https://go.microsoft.com/fwlink/?LinkId=528179 )
  
[<span data-ttu-id="64648-168">反垃圾郵件保護常見問題集</span><span class="sxs-lookup"><span data-stu-id="64648-168">Anti-Spam Protection FAQ</span></span>](https://technet.microsoft.com/library/jj937231%28v=exchg.150%29.aspx)
  
[<span data-ttu-id="64648-169">使用安全清單或其他技術防止誤判電子郵件標示為垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="64648-169">Prevent false positive email marked as spam with a safelist or other techniques</span></span>](prevent-email-from-being-marked-as-spam-0.md)
  
[<span data-ttu-id="64648-170">如何設定 Office 365 垃圾郵件篩選可協助封鎖垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="64648-170">How to set up Office 365 spam filtering to help block junk messages</span></span>](block-email-spam-to-prevent-false-negatives.md)
  
[<span data-ttu-id="64648-171">什麼是垃圾郵件與大量電子郵件的差異？</span><span class="sxs-lookup"><span data-stu-id="64648-171">What's the Difference Between Junk Email and Bulk Email?</span></span>](https://technet.microsoft.com/library/dn720441%28v=exchg.150%29.aspx)
  
[<span data-ttu-id="64648-172">反垃圾郵件訊息標頭</span><span class="sxs-lookup"><span data-stu-id="64648-172">Anti-spam message headers</span></span>](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx)
  
[<span data-ttu-id="64648-173">非法回應郵件與 EOP</span><span class="sxs-lookup"><span data-stu-id="64648-173">Backscatter Messages and EOP</span></span>](https://technet.microsoft.com/library/dn499795%28v=exchg.150%29.aspx)

## <a name="more-resources"></a><span data-ttu-id="64648-174">其他資源</span><span class="sxs-lookup"><span data-stu-id="64648-174">More resources</span></span>

[<span data-ttu-id="64648-175">從 Office 365 社群論壇獲得協助</span><span class="sxs-lookup"><span data-stu-id="64648-175">Get help from the Office 365 community forums</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=518605)
  
[<span data-ttu-id="64648-176">管理員：登入及建立服務要求</span><span class="sxs-lookup"><span data-stu-id="64648-176">Admins: Sign in and create a service request</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=519124)
  
[<span data-ttu-id="64648-177">管理員：連絡支援人員</span><span class="sxs-lookup"><span data-stu-id="64648-177">Admins: Call Support</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=518322)
