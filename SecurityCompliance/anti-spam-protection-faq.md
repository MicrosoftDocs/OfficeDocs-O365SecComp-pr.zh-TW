---
title: 反垃圾郵件保護常見問題集
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
ms.assetid: c534a35d-b121-45da-9d0a-ce738ce51fce
description: 本主題提供有關反垃圾郵件保護的常見問題與解答。這些解答適用於 Microsoft Exchange Online 及 Exchange Online Protection (EOP) 客戶。
ms.openlocfilehash: 77b3dc26d55f75e7476a3b52a550174a3876c56f
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/21/2018
ms.locfileid: "23003072"
---
# <a name="anti-spam-protection-faq"></a><span data-ttu-id="50d4f-104">反垃圾郵件保護常見問題集</span><span class="sxs-lookup"><span data-stu-id="50d4f-104">Anti-spam protection FAQ</span></span>

<span data-ttu-id="50d4f-p102">本主題提供有關反垃圾郵件保護的常見問題與解答。這些解答適用於 Microsoft Exchange Online 及 Exchange Online Protection (EOP) 客戶。</span><span class="sxs-lookup"><span data-stu-id="50d4f-p102">This topic provides frequently asked questions and answers about anti-spam protection. Answers are applicable for Microsoft Exchange Online and Exchange Online Protection (EOP) customers.</span></span> 
  
> [!TIP]
> <span data-ttu-id="50d4f-p103">問題與回答關於安全的寄件者和封鎖的寄件者清單，請參閱[安全寄件者和封鎖寄件者清單在 Exchange Online](safe-sender-and-blocked-sender-lists-faq.md)。問題與回答有關隔離區，請參閱[隔離常見問題集](quarantine-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="50d4f-p103">For questions and answers about safe sender and blocked sender lists, see [Safe sender and blocked sender lists in Exchange Online](safe-sender-and-blocked-sender-lists-faq.md). For questions and answers about the quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span> 
  
 <span data-ttu-id="50d4f-109">**問：偵測到的垃圾郵件預設會受到怎麼樣的處理？**</span><span class="sxs-lookup"><span data-stu-id="50d4f-109">**Q. By default, what happens to a spam-detected message?**</span></span>
  
<span data-ttu-id="50d4f-p104">答： **若為輸入郵件：** 大部分的垃圾郵件是由連線篩選根據寄件者 IP 位址予以刪除。然後服務就會檢查郵件的內容。依預設，依內容篩選出的垃圾郵件會傳送至收件者的 [垃圾郵件] 資料夾。您可以變更此動作。例如，您可以設定內容篩選原則，選擇將垃圾郵件訊息傳送至隔離區。</span><span class="sxs-lookup"><span data-stu-id="50d4f-p104">A. **For inbound messages:** The majority of spam is deleted via connection filtering, which is based on the IP address of the sender. The service then inspects the contents of the message. By default, content-filtered spam is sent to the recipient's Junk Email folder. You can change this action. For example, you can choose to send spam messages to the quarantine instead by configuring the content filter policy.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="50d4f-p105">若為 EOP 獨立版客戶：若要確保 **[將郵件移至垃圾郵件資料夾]** 動作能夠在內部部署信箱中運作，您必須在內部部署伺服器上設定兩項 Exchange 傳輸規則，以偵測由 EOP 新增的垃圾郵件標頭。如需詳細資訊，請參閱 [確定垃圾郵件路由傳送至每一個使用者的垃圾郵件資料夾](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="50d4f-p105">For EOP standalone customers: In order to ensure that the **Move message to Junk Email folder** action will work with on-premises mailboxes, you must configure two Exchange Transport rules on your on-premises servers to detect spam headers added by EOP. For details, see [Ensure that spam is routed to each user's Junk Email folder](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> 
  
 <span data-ttu-id="50d4f-118">**若為輸出郵件：** 郵件已透過較高風險傳遞集區路由傳送或已退回並未傳遞，在此情況下，寄件者應該會收到傳遞狀態通知 (DSN) 郵件，從中得知此郵件無法傳遞。</span><span class="sxs-lookup"><span data-stu-id="50d4f-118">**For outbound messages:** The message is either routed through the higher risk delivery pool or is bounced and not delivered, in which case the sender should receive a delivery status notification (DSN) message telling them that the message couldn't be delivered.</span></span> 
  
 <span data-ttu-id="50d4f-119">**問什麼是零時差垃圾郵件及如何為該服務所處理？**</span><span class="sxs-lookup"><span data-stu-id="50d4f-119">**Q. What's a zero-day spam variant and how is it handled by the service?**</span></span>
  
<span data-ttu-id="50d4f-p106">A.零時差垃圾郵件 variant 是第一代、 先前未知的垃圾郵件永不已經擷取或分析，variant 因此我們垃圾郵件的內容篩選器尚未沒有可用於偵測它的任何資訊。零時差垃圾郵件之後範例會擷取利用及分析我們垃圾郵件分析師如果它符合垃圾郵件分類的準則，我們垃圾郵件內容篩選器會更新偵測，以及它不再具有視為"零時差。 」(**附註：** 如果您收到一則訊息，可能是零時差垃圾郵件變數，以協助我們改善服務，請提交給 Microsoft 使用其中一個方法所述[提交垃圾郵件、 非垃圾郵件和網路釣魚詐騙郵件訊息給 Microsoft 的郵件分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)。)</span><span class="sxs-lookup"><span data-stu-id="50d4f-p106">A. A zero-day spam variant is a first generation, previously unknown variant of spam that's never been captured or analyzed, so our spam content filters don't yet have any information available for detecting it. After a zero-day spam sample is captured and analyzed by our spam analysts, if it meets the spam classification criteria, our spam content filters are updated to detect it, and it's no longer considered "zero-day." ( **Note:** If you receive a message that may be a zero-day spam variant, in order to help us improve the service, please submit the message to Microsoft using one of the methods described in [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).)</span></span>
  
 <span data-ttu-id="50d4f-124">**問：我是否需要將此服務設定為提供反垃圾郵件保護？**</span><span class="sxs-lookup"><span data-stu-id="50d4f-124">**Q. Do I need to configure the service to provide anti-spam protection?**</span></span>
  
<span data-ttu-id="50d4f-p107">答：在您註冊此服務並新增自己的網域後，此服務即會透過預設的反垃圾郵件原則對整個公司啟用垃圾郵件篩選功能。預設的原則已調整為無須進行任何額外設定 (除了針對 EOP 獨立版客戶提及的上述例外狀況)，即可保護您。如果您是系統管理員，您可以編輯預設的反垃圾郵件原則，使其確切符合貴組織的需求。若要提高精確性，您也可以建立自訂的內容篩選原則，並套用至組織中指定的使用者、群組或網域。自訂原則一律優先於預設原則，但您可以變更自訂原則的優先順序 (亦即執行順序)。</span><span class="sxs-lookup"><span data-stu-id="50d4f-p107">A. After you sign up for the service and add your domain, spam filtering is automatically enabled company-wide through the default anti-spam policies. The default policies are tuned to protect you without needing any additional configuration (aside from the exception noted above for EOP standalone customers). As an admin, you can edit the default anti-spam policies so that they're tailored to best meet the needs of your organization. For greater granularity, you can also create custom content filter policies and apply them to specified users, groups, or domains in your organization. Custom policies always take precedence over the default policy, but you can change the priority (that is, the running order) of your custom policies.</span></span>
  
<span data-ttu-id="50d4f-131">如需設定反垃圾郵件原則的相關資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="50d4f-131">For more about configuring your anti-spam policies, see the following topics:</span></span>
  
[<span data-ttu-id="50d4f-132">設定連線篩選原則</span><span class="sxs-lookup"><span data-stu-id="50d4f-132">Configure the connection filter policy</span></span>](configure-the-connection-filter-policy.md)
  
[<span data-ttu-id="50d4f-133">設定您的垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="50d4f-133">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
[<span data-ttu-id="50d4f-134">設定輸出垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="50d4f-134">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
 <span data-ttu-id="50d4f-135">**問：如果我對反垃圾郵件原則進行變更並儲存變更，這些變更經過多久才會生效？**</span><span class="sxs-lookup"><span data-stu-id="50d4f-135">**Q. If I make a change to an anti-spam policy, how long does it take after I save my changes for them to take effect?**</span></span>
  
<span data-ttu-id="50d4f-p108">答：最多可能需要 1 小時，變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="50d4f-p108">A. It may take up to 1 hour for the changes to take effect.</span></span>
  
 <span data-ttu-id="50d4f-138">**問：大量電子郵件篩選功能是否會自動啟用？**</span><span class="sxs-lookup"><span data-stu-id="50d4f-138">**Q. Is bulk email filtering automatically enabled?**</span></span>
  
<span data-ttu-id="50d4f-p109">A.根據預設，會啟用進階垃圾郵件篩選選項**大宗郵件**對於新客戶。已移轉的客戶，此設定將符合您的 FOPE 設定。如需大量電子郵件的詳細資訊，請參閱[垃圾郵件與大量電子郵件之間的差異為何吗？](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="50d4f-p109">A. By default, the **Bulk mail** advanced spam filtering option is enabled for new customers. For migrated customers, this setting will match your FOPE configuration. For more information about bulk email, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>
  
 <span data-ttu-id="50d4f-143">**問：此服務是否提供 URL 篩選？**</span><span class="sxs-lookup"><span data-stu-id="50d4f-143">**Q. Does the service provide URL filtering?**</span></span>
  
<span data-ttu-id="50d4f-p110">答：是，此服務有 URL 篩選器可檢查郵件內的 URL。如果偵測到與已知垃圾郵件或惡意內容相關聯的 URL，則會將郵件標示為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="50d4f-p110">A. Yes the service has a URL filter that checks for URLs within messages. If URLs associated with known spam or malicious content are detected then the message is marked as spam.</span></span>
  
 <span data-ttu-id="50d4f-147">**問：客戶可以如何使用此服務將誤判正常 (是垃圾郵件) 和誤判 (非垃圾郵件) 的郵件傳送給 Microsoft？**</span><span class="sxs-lookup"><span data-stu-id="50d4f-147">**Q. How can customers using the service send false negative (spam) and false positive (non-spam) messages to Microsoft?**</span></span>
  
<span data-ttu-id="50d4f-p111">A.垃圾郵件和非垃圾郵件可以送出給 Microsoft 進行分析的數種方式。如需詳細資訊，請參閱[提交垃圾郵件、 非垃圾郵件和網路釣魚詐騙郵件訊息給 Microsoft 進行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)。</span><span class="sxs-lookup"><span data-stu-id="50d4f-p111">A. Spam and non-spam messages can be submitted to Microsoft for analysis in several ways. For more information, see [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).</span></span> 
  
 <span data-ttu-id="50d4f-151">**問：我是否可以取得垃圾郵件報告？**</span><span class="sxs-lookup"><span data-stu-id="50d4f-151">**Q. Can I get spam reports?**</span></span>
  
<span data-ttu-id="50d4f-p112">A 是，例如您可以取得垃圾郵件偵測] 報告在 Office 365 系統管理中心。這份報告顯示垃圾郵件大量為唯一的郵件計數。如需報告的詳細資訊，請參閱下列連結：</span><span class="sxs-lookup"><span data-stu-id="50d4f-p112">A. Yes, for example you can get a spam detection report in the Office 365 admin center. This report shows spam volume as a count of unique messages. For more information about reporting, see the following links:</span></span>
  
<span data-ttu-id="50d4f-156">Exchange Online 客戶： [Monitoring，Reporting，and 郵件追蹤在 Exchange Online](http://technet.microsoft.com/library/87bdeeae-bd80-4a3b-95c5-62fbaf97c2e8.aspx)</span><span class="sxs-lookup"><span data-stu-id="50d4f-156">Exchange Online customers: [Monitoring, Reporting, and Message Tracing in Exchange Online](http://technet.microsoft.com/library/87bdeeae-bd80-4a3b-95c5-62fbaf97c2e8.aspx)</span></span>
  
<span data-ttu-id="50d4f-157">Exchange Online Protection 客戶：[在 Exchange Online Protection 報告與訊息追蹤](eop/reporting-and-message-trace-in-exchange-online-protection.md)</span><span class="sxs-lookup"><span data-stu-id="50d4f-157">Exchange Online Protection customers: [Reporting and message trace in Exchange Online Protection](eop/reporting-and-message-trace-in-exchange-online-protection.md)</span></span>
  
 <span data-ttu-id="50d4f-158">**問：有人寄郵件給我，但我找不到。我懷疑該郵件可能被當成垃圾郵件。是否有工具可讓我查明？**</span><span class="sxs-lookup"><span data-stu-id="50d4f-158">**Q. Someone sent me a message and I can't find it. I suspect that it may have been detected as spam. Is there a tool that I can use to find out?**</span></span>
  
<span data-ttu-id="50d4f-p113">答：有的，郵件追蹤工具可讓您追蹤通過此服務的電子郵件，以了解這些電子郵件的處理情形。如需關於如何使用郵件追蹤工具來查出郵件為何被標示為垃圾郵件的詳細資訊，請參閱[郵件是否被標示為垃圾郵件？](http://technet.microsoft.com/library/aa49e3f9-a5b1-4410-aac2-ddbbf3f5bfb2.aspx#BKMB_Whywasamessagemarkedasspam)</span><span class="sxs-lookup"><span data-stu-id="50d4f-p113">A. Yes, the message trace tool enables you to follow email messages as they pass through the service, in order to find out what happened to them. For more information about how to use the message trace tool to find out why a message was marked as spam, see [Was a message marked as spam? ](http://technet.microsoft.com/library/aa49e3f9-a5b1-4410-aac2-ddbbf3f5bfb2.aspx#BKMB_Whywasamessagemarkedasspam)</span></span>
  
 <span data-ttu-id="50d4f-162">**問：如果我的使用者對外傳送垃圾郵件，此服務是否會對我的郵件進行節流 (速率限制)？**</span><span class="sxs-lookup"><span data-stu-id="50d4f-162">**Q. Will the service throttle (rate limit) my mail if my users send outbound spam?**</span></span>
  
<span data-ttu-id="50d4f-p114">A.如果一半以上之郵件的傳送來自使用者透過在特定時間內 （例如每小時） 服務由 Office 365 決定設為垃圾郵件，使用者將會禁止傳送郵件。在大多數情況下，如果外寄郵件決定設為垃圾郵件，它會路由傳送到高風險傳遞集區，以減少要新增至封鎖清單的一般輸出 IP 集區的機率。</span><span class="sxs-lookup"><span data-stu-id="50d4f-p114">A. If more than half of the mail that is sent from a user through the service within a certain time frame (for example, per hour), is determined to be spam by Office 365, the user will be blocked from sending messages. In most cases, if an outbound message is determined to be spam, it is routed through the high-risk delivery pool, which reduces the probability of the normal outbound-IP pool being added to a block list.</span></span>
  
<span data-ttu-id="50d4f-p115">您可以傳送通知給指定的電子郵件地址時封鎖的寄件者傳送輸出垃圾郵件。如需此設定的詳細資訊，請參閱 ＜ [Configure 輸出垃圾郵件原則](configure-the-outbound-spam-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="50d4f-p115">You can send a notification to a specified email address when a sender is blocked sending outbound spam. For more information about this setting, see [Configure the outbound spam policy](configure-the-outbound-spam-policy.md).</span></span>
  
 <span data-ttu-id="50d4f-168">**問：我是否可以將 Exchange Online 搭配第三方反垃圾郵件和反惡意程式碼提供者來使用？**</span><span class="sxs-lookup"><span data-stu-id="50d4f-168">**Q. Can I use a third-party anti-spam and anti-malware provider in conjunction with Exchange Online?**</span></span>
  
<span data-ttu-id="50d4f-p116">答：可以，您可以設定其他垃圾郵件和惡意程式碼篩選服務來保護 Exchange Online 信箱。若要對輸入郵件執行此動作，您必須將 MX 記錄變更為指向第三方提供者，以將電子郵件重新導向至第三方提供者，然後將郵件重新導向至 EOP 進行其他處理。若要對輸出郵件執行此動作，請將郵件傳遞目的地設定為第三方提供者 (智慧主機)，如[Scenario: Outbound Smart Hosting](http://technet.microsoft.com/library/431b3f02-4efd-4bd3-94e7-eecd03f8ef5e.aspx)所述。</span><span class="sxs-lookup"><span data-stu-id="50d4f-p116">A. Yes, you may configure another spam and malware filtering service to protect your Exchange Online mailboxes. To do this for inbound mail, you should redirect your email messages to the third-party provider by changing your MX records to point to the third-party provider, and then redirect the messages to EOP for additional processing. To do this for outbound mail, please configure the message delivery destination to the third-party provider (smart host), as shown in [Scenario: Outbound Smart Hosting](http://technet.microsoft.com/library/431b3f02-4efd-4bd3-94e7-eecd03f8ef5e.aspx).</span></span>
  
 <span data-ttu-id="50d4f-173">**問：Microsoft 是否有任何關於如何自我保護以免於網路釣魚詐騙的文件？**</span><span class="sxs-lookup"><span data-stu-id="50d4f-173">**Q. Does Microsoft have any documentation about how I can protect myself from phishing scams?**</span></span>
  
<span data-ttu-id="50d4f-p117">答：有的，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="50d4f-p117">A. Yes we do, please consult the following articles:</span></span>
  
[<span data-ttu-id="50d4f-176">取得網路釣魚詐騙、樂透詐騙及其他類型詐騙的協助</span><span class="sxs-lookup"><span data-stu-id="50d4f-176">Get help with phishing scams, lottery fraud, and other types of scams</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=325606)
  
[<span data-ttu-id="50d4f-177">電子郵件和網路詐騙：如何協助自我保護</span><span class="sxs-lookup"><span data-stu-id="50d4f-177">Email and web scams: How to help protect yourself</span></span>](http://go.microsoft.com/fwlink/p/?LinkID=325607)
  
 <span data-ttu-id="50d4f-178">**問：是否會調查垃圾郵件與惡意程式碼郵件的傳送人，或是將其轉交給執法單位？**</span><span class="sxs-lookup"><span data-stu-id="50d4f-178">**Q. Are spam and malware messages being investigated as to who sent them, or being transferred to law enforcement entities?**</span></span>
  
<span data-ttu-id="50d4f-p118">答：雖然我們偶爾會調查特別危險或具破壞性的垃圾郵件或攻擊行動，並追捕其幕後黑手，但此服務的重心主要放在偵測及移除垃圾郵件與惡意程式碼。這之中牽涉到與法律和數位犯罪單位合作打擊濫發垃圾郵件者所控制的殭屍網路 (Botnet)、阻止濫發垃圾郵件者使用服務 (如果他們使用服務來傳送輸出電子郵件)，以及將資訊轉交給執法單位以起訴犯罪行為。</span><span class="sxs-lookup"><span data-stu-id="50d4f-p118">A. The service focuses on spam and malware detection and removal, though we may occasionally investigate especially dangerous or damaging spam or attack campaigns and pursue the perpetrators. This may involve working with our legal and digital crime units to take down a spammer botnet, blocking the spammer from using the service (if they're using it for sending outbound email), and passing the information on to law enforcement for criminal prosecution.</span></span>
  
 <span data-ttu-id="50d4f-182">**問：對外傳送電子郵件時有哪些最佳做法，可確保我的郵件都能順利傳遞？**</span><span class="sxs-lookup"><span data-stu-id="50d4f-182">**Q. What are a set of best outbound mailing practices that will ensure that my mail is delivered?**</span></span>
  
<span data-ttu-id="50d4f-p119">答：以下提供的指導方針，是對外傳送電子郵件時的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="50d4f-p119">A. The guidelines presented below are best practices for sending outbound email messages.</span></span>
  
1. <span data-ttu-id="50d4f-185">**電子郵件的傳送端網域應在 DNS 中獲得解析。**</span><span class="sxs-lookup"><span data-stu-id="50d4f-185">**The sending domain of the email should resolve in DNS.**</span></span>
    
    <span data-ttu-id="50d4f-p120">例如，如果寄件者是 user@example.com，網域 example.com 解析為 IP 位址 192.0.43.10 傳送。如果傳送端網域的記錄並沒有 MX 記錄在 DNS 中，服務會透過其較高風險傳遞集區不論郵件的內容為 [垃圾郵件路由傳送郵件。如需較高風險傳遞集區的詳細資訊，請參閱 ＜[高風險傳遞集區的外寄郵件](high-risk-delivery-pool-for-outbound-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="50d4f-p120">For example, if the sender is user@example.com, the domain example.com resolves to the IP address 192.0.43.10. If a sending domain has no A-record and no MX record in DNS, the service will route the message through its higher risk delivery pool regardless of whether or not the content of the message is spam. For more information about the higher risk delivery pool, see [High-risk delivery pool for outbound messages](high-risk-delivery-pool-for-outbound-messages.md).</span></span> 
    
2. <span data-ttu-id="50d4f-189">**輸出郵件伺服器的傳送端 IP 位址應具有反向 DNS (PTR) 項目。**</span><span class="sxs-lookup"><span data-stu-id="50d4f-189">**The sending IP address of the outbound mail server should have a reverse DNS (PTR) entry.**</span></span>
    
    <span data-ttu-id="50d4f-190">例如，如果從 IP 位址 192.0.43.10 傳送，此 IP 的反向 DNS 項目是 43-10.any.icann.org。</span><span class="sxs-lookup"><span data-stu-id="50d4f-190">For example, if sending from the IP address 192.0.43.10, the reverse DNS entry for this IP is 43-10.any.icann.org.</span></span> 
    
3. <span data-ttu-id="50d4f-191">**HELO/EHLO 與 MAIL FROM 命令應一致，且以網域名稱而非 IP 位址的形式存在。**</span><span class="sxs-lookup"><span data-stu-id="50d4f-191">**The HELO/EHLO and MAIL FROM commands should be consistent and be present in the form of a domain name rather than an IP address.**</span></span>
    
    <span data-ttu-id="50d4f-192">HELO/EHLO 命令應設定成符合傳送端 IP 位址的反向 DNS，讓網域在郵件標頭的各個部分間都能保持相同。</span><span class="sxs-lookup"><span data-stu-id="50d4f-192">The HELO/EHLO command should be configured to match the reverse DNS of the sending IP address so that the domain remains the same across the various parts of the message headers.</span></span>
    
4. <span data-ttu-id="50d4f-193">**確實 DNS 中已設定適當的 SPF 記錄。**</span><span class="sxs-lookup"><span data-stu-id="50d4f-193">**Ensure that proper SPF records are set up in DNS.**</span></span>
    
    <span data-ttu-id="50d4f-p121">SPF 記錄是一項驗證機制，可驗證從某個網域傳送的郵件是否真的來自該網域而不是詐騙郵件。如需 SPF 記錄的詳細資訊，請參閱下列連結：</span><span class="sxs-lookup"><span data-stu-id="50d4f-p121">SPF records are a mechanism for validating that mail sent from a domain really is coming from that domain and is not spoofed. For more information about SPF records, see the following links:</span></span>
    
    [<span data-ttu-id="50d4f-196">在 Office 365 中設定 SPF 以協助防止詐騙</span><span class="sxs-lookup"><span data-stu-id="50d4f-196">Set up SPF in Office 365 to help prevent spoofing</span></span>](set-up-spf-in-office-365-to-help-prevent-spoofing.md)
    
    [<span data-ttu-id="50d4f-197">建立 Office 365 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="50d4f-197">Create DNS records for Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkID=275414)
    
5. <span data-ttu-id="50d4f-198">**使用 DKIM 簽署電子郵件時，應以寬鬆的規範簽署。**</span><span class="sxs-lookup"><span data-stu-id="50d4f-198">**Signing email with DKIM, sign with relaxed canonicalization.**</span></span>
    
    <span data-ttu-id="50d4f-p122">如果寄件者要使用 Domain Keys Identified Mail (DKIM) 簽署其郵件，並且要透過此服務傳送輸出郵件，他們應使用寬鬆的標頭規範演算法進行簽署。若使用嚴格的標頭規範進行簽署，簽章可能會在通過此服務時失效。</span><span class="sxs-lookup"><span data-stu-id="50d4f-p122">If a sender wants to sign their messages using Domain Keys Identified Mail (DKIM) and they want to send outbound mail through the service, they should sign using the relaxed header canonicalization algorithm. Signing with strict header canonicalization may invalidate the signature when it passes through the service.</span></span>
    
6. <span data-ttu-id="50d4f-201">**網域擁有者應在 WHOIS 資料庫中具有正確的資訊。**</span><span class="sxs-lookup"><span data-stu-id="50d4f-201">**Domain owners should have accurate information in the WHOIS database.**</span></span>
    
    <span data-ttu-id="50d4f-202">如此可識別網域的擁有者，以及如何輸入可靠的母公司、連絡點與名稱伺服器來連絡這些擁有者。</span><span class="sxs-lookup"><span data-stu-id="50d4f-202">This identifies the owners of the domain and how to contact them by entering the stable parent company, point of contact, and name servers.</span></span>
    
7. <span data-ttu-id="50d4f-203">**若為大量郵件寄件者，[寄件者:]名稱應該反映郵件的傳送者是誰，而郵件的主旨行應該顯示郵件內容的簡短摘要。**</span><span class="sxs-lookup"><span data-stu-id="50d4f-203">**For bulk mailers, the From: name should reflect who is sending the message, while the subject line of the message should be a brief summary on what the message is about.**</span></span>
    
    <span data-ttu-id="50d4f-p123">郵件內文應明確指出所提供的優惠、服務或產品。 例如，如果寄件者為 Contoso 公司寄出大量郵件，其電子郵件的 [寄件者] 與 [主旨] 應類似如下：</span><span class="sxs-lookup"><span data-stu-id="50d4f-p123">The message body should have a clear indication of the offering, service, or product. For example, if a sender is sending out a bulk mailing for the Contoso company, the following is what the email From and Subject should resemble:</span></span>
    
    <span data-ttu-id="50d4f-206">From:marketing@contoso.com</span><span class="sxs-lookup"><span data-stu-id="50d4f-206">From: marketing@contoso.com</span></span>
    
    <span data-ttu-id="50d4f-207">主旨：聖誕節商品最新型錄！</span><span class="sxs-lookup"><span data-stu-id="50d4f-207">Subject: New updated catalog for the Christmas season!</span></span> 
    
    <span data-ttu-id="50d4f-208">以下是說明性不足的錯誤範例：</span><span class="sxs-lookup"><span data-stu-id="50d4f-208">The following is an example of what not to do because it is not descriptive:</span></span>
    
    <span data-ttu-id="50d4f-209">From:user@hotmail.com</span><span class="sxs-lookup"><span data-stu-id="50d4f-209">From: user@hotmail.com</span></span>
    
    <span data-ttu-id="50d4f-210">主旨：型錄</span><span class="sxs-lookup"><span data-stu-id="50d4f-210">Subject: Catalogs</span></span>
    
8. <span data-ttu-id="50d4f-211">**如果傳送大量郵件給眾多收件者，且郵件屬於電子報格式，則應於郵件的最下方提供取消訂閱的方式。**</span><span class="sxs-lookup"><span data-stu-id="50d4f-211">**If sending a bulk mailing to many recipients and the message is in newsletter format, there should be a way of unsubscribing at the bottom of the message.**</span></span>
    
    <span data-ttu-id="50d4f-212">取消訂閱選項應類似如下：</span><span class="sxs-lookup"><span data-stu-id="50d4f-212">The unsubscribe option should resemble the following:</span></span>
    
    <span data-ttu-id="50d4f-p124">本郵件由 sender@fabrikam.com 傳送給 example@contoso.com。更新個人資料/電子郵件地址 | 使用 **SafeUnsubscribe** 立即取消訂閱 | 隱私權原則</span><span class="sxs-lookup"><span data-stu-id="50d4f-p124">This message was sent to example@contoso.com by sender@fabrikam.com. Update Profile/Email Address | Instant removal with **SafeUnsubscribe**™ | Privacy Policy</span></span>
    
9. <span data-ttu-id="50d4f-215">**如果傳送大量電子郵件，則應使用雙重加入確認程序來執行清單的取得。如果您是大量郵件的寄件者，雙重加入確認程序會是業界的最佳做法。**</span><span class="sxs-lookup"><span data-stu-id="50d4f-215">**If sending bulk email, list acquisition should be performed using double opt-in. If you are a bulk mailer, double opt-in is an industry best practice.**</span></span>
    
    <span data-ttu-id="50d4f-216">採用雙重加入確認程序時，使用者必須執行兩個動作，才能註冊行銷郵件：</span><span class="sxs-lookup"><span data-stu-id="50d4f-216">Double opt-in is the practice of requiring a user to take two actions to sign up for marketing mail:</span></span>
    
1. <span data-ttu-id="50d4f-217">首先，使用者必須點選原先未勾選的核取方塊，表示他們選擇要進一步接收行銷者提供的產品服務或電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="50d4f-217">Once when the user clicks on a previously unchecked check box where they opt-in to receive further offers or email messages from the marketer.</span></span>
    
2. <span data-ttu-id="50d4f-218">其次，行銷者會將確認電子郵件傳送至使用者提供的電子郵件地址，要求使用者點選具有時效性的連結，以完成確認動作。</span><span class="sxs-lookup"><span data-stu-id="50d4f-218">A second time when the marketer sends a confirmation email to the user's provided email address asking them to click on a time-sensitive link that will complete their confirmation.</span></span>
    
    <span data-ttu-id="50d4f-219">使用雙重加入確認程序，大量電子郵件寄件者可建立良好聲譽。</span><span class="sxs-lookup"><span data-stu-id="50d4f-219">Using double opt-in builds a good reputation for bulk email senders.</span></span>
    
10. <span data-ttu-id="50d4f-220">**大量郵件寄件者應建立清楚透明的內容，以示負責：**</span><span class="sxs-lookup"><span data-stu-id="50d4f-220">**Bulk senders should create transparent content for which they can be held accountable:**</span></span>
    
1. <span data-ttu-id="50d4f-221">在請收件者將寄件者加入通訊錄的用語中，應明確指出這個加入動作並不保證郵件可以成功送達。</span><span class="sxs-lookup"><span data-stu-id="50d4f-221">Verbiage requesting that recipients add the sender to the address book should clearly state that such action is not a guarantee of delivery.</span></span>
    
2. <span data-ttu-id="50d4f-222">在郵件內文中建構重新導向連結時，請使用一致的連結樣式。</span><span class="sxs-lookup"><span data-stu-id="50d4f-222">When constructing redirects in the body of the message, use a consistent link style.</span></span>
    
3. <span data-ttu-id="50d4f-223">不要傳送龐大的影像或附件，或是純由影像呈現的郵件。</span><span class="sxs-lookup"><span data-stu-id="50d4f-223">Don't send large images or attachments, or messages that are solely composed of an image.</span></span>
    
4. <span data-ttu-id="50d4f-224">使用追蹤像素 (Web Bug 或指標) 時，請在您的公眾隱私權或 P3P 設定中明確指出有這些項目存在。</span><span class="sxs-lookup"><span data-stu-id="50d4f-224">When employing tracking pixels (web bugs or beacons), clearly state their presence in your public privacy or P3P settings.</span></span>
    
11. <span data-ttu-id="50d4f-225">**讓輸出的傳遞狀態通知有適當的格式。**</span><span class="sxs-lookup"><span data-stu-id="50d4f-225">**Format outbound delivery status notifications.**</span></span>
    
    <span data-ttu-id="50d4f-226">在產生傳遞狀態通知訊息時，寄件者應遵循 [RFC 3464](https://go.microsoft.com/fwlink/?LinkId=279715) 中指定的退回格式。</span><span class="sxs-lookup"><span data-stu-id="50d4f-226">When generating delivery status notification messages, senders should follow the format of a bounce as specified in [RFC 3464](https://go.microsoft.com/fwlink/?LinkId=279715).</span></span>
    
12. <span data-ttu-id="50d4f-227">**移除因使用者不存在而使郵件退回的電子郵件地址。**</span><span class="sxs-lookup"><span data-stu-id="50d4f-227">**Remove bounced email addresses for non-existent users.**</span></span>
    
    <span data-ttu-id="50d4f-p125">如果您收到 NDR，指出某電子郵件地址已不再使用，請從您的清單中移除不存在的電子郵件別名。電子郵件地址會隨時間變更，而且使用者有時會棄之不用。</span><span class="sxs-lookup"><span data-stu-id="50d4f-p125">If you receive an NDR indicating that an email address is no longer in use, remove the non-existent email alias from your list. Email addresses change over time, and people sometimes discard them.</span></span>
    
13. <span data-ttu-id="50d4f-230">**使用 Hotmail 的智慧型網路資料服務 (SNDS) 程式。**</span><span class="sxs-lookup"><span data-stu-id="50d4f-230">**Use Hotmail's Smart Network Data Services (SNDS) program.**</span></span>
    
    <span data-ttu-id="50d4f-p126">Hotmail 使用名為智慧型網路資料服務的程式，供寄件者查看使用者所提交的投訴。SNDS 是對 Hotmail 傳遞問題進行疑難排解時的主要入口網站。</span><span class="sxs-lookup"><span data-stu-id="50d4f-p126">Hotmail uses a program called Smart Network Data Services that allows senders to check complaints submitted by end users. The SNDS is the primary portal for troubleshooting delivery problems to Hotmail.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="50d4f-233">相關資訊</span><span class="sxs-lookup"><span data-stu-id="50d4f-233">For more information</span></span>

[<span data-ttu-id="50d4f-234">Office 365 電子郵件反垃圾郵件保護</span><span class="sxs-lookup"><span data-stu-id="50d4f-234">Office 365 Email Anti-Spam Protection</span></span>](https://support.office.com/article/6a601501-a6a8-4559-b2e7-56b59c96a586)
  
[<span data-ttu-id="50d4f-235">安全寄件者和封鎖寄件者清單在 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="50d4f-235">Safe sender and blocked sender lists in Exchange Online</span></span>](safe-sender-and-blocked-sender-lists-faq.md)
  
[<span data-ttu-id="50d4f-236">反垃圾郵件訊息標頭</span><span class="sxs-lookup"><span data-stu-id="50d4f-236">Anti-spam message headers</span></span>](anti-spam-message-headers.md)
  
[<span data-ttu-id="50d4f-237">非法回應郵件與 EOP</span><span class="sxs-lookup"><span data-stu-id="50d4f-237">Backscatter messages and EOP</span></span>](backscatter-messages-and-eop.md)
  

