---
title: 設定 EOP 的最佳作法
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: 遵循下列 Exchange Online Protection (EOP) 最佳作法建議，以成功完成設定並避免發生常見組態錯誤。
ms.openlocfilehash: ef58e2cd5a3ffdbbeb02124442c355974d174073
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027270"
---
# <a name="best-practices-for-configuring-eop"></a><span data-ttu-id="4a047-103">設定 EOP 的最佳作法</span><span class="sxs-lookup"><span data-stu-id="4a047-103">Best practices for configuring EOP</span></span>
  
<span data-ttu-id="4a047-p101">遵循下列 Exchange Online Protection (EOP) 最佳作法建議，以成功完成設定並避免發生常見組態錯誤。建議您使用預設組態設定作為一般規則。本主題假設您已完成安裝程序。若您尚未完成 EOP 安裝，請參閱 [設定 EOP 服務](set-up-your-eop-service.md)。</span><span class="sxs-lookup"><span data-stu-id="4a047-p101">Follow these best-practice recommendations for Exchange Online Protection (EOP) in order to set yourself up for success and avoid common configuration errors. We recommend using the default configuration settings as a general rule. This topic assumes that you've already completed the setup process. If you haven't completed EOP setup, see [Set up your EOP service](set-up-your-eop-service.md).</span></span>
  
## <a name="use-a-test-domain"></a><span data-ttu-id="4a047-108">使用測試網域</span><span class="sxs-lookup"><span data-stu-id="4a047-108">Use a test domain</span></span>

<span data-ttu-id="4a047-109">建議您使用測試網域、子網域或低容量網域試用服務功能，然後才在較高容量的實際執行網域上進行實作。</span><span class="sxs-lookup"><span data-stu-id="4a047-109">We recommend that you use a test domain, subdomain, or low volume domain for trying out service features before implementing them on your higher-volume, production domains.</span></span>
  
## <a name="synchronize-recipients"></a><span data-ttu-id="4a047-110">同步處理收件者</span><span class="sxs-lookup"><span data-stu-id="4a047-110">Synchronize recipients</span></span>

<span data-ttu-id="4a047-p102">若您的組織在內部部署的 Active Directory 環境中已有使用者帳戶，則可將這些帳戶同步處理至雲端的 Azure Active Directory。建議使用目錄同步作業。若要深入了解使用目錄同步作業的好處及其設定步驟，請參閱 [管理 EOP 中的郵件使用者](manage-mail-users-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="4a047-p102">If your organization has existing user accounts in an on-premisesActive Directory environment, you can synchronize those accounts to Azure Active Directory in the cloud. Using directory synchronization is recommended. To learn more about the benefits of using directory synchronization, and the steps for setting it up, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>
  
## <a name="spf-record-customization-to-help-prevent-spoofing"></a><span data-ttu-id="4a047-114">協助防止詐騙的 SPF 記錄自訂</span><span class="sxs-lookup"><span data-stu-id="4a047-114">SPF record customization to help prevent spoofing</span></span>

<span data-ttu-id="4a047-p103">當您設定好 EOP 時，您加入 SPF （寄件者原則架構） 記錄 EOP 的 DNS 記錄。SPF 記錄協助防止詐騙。如需如何 SPF 記錄可防止詐騙及如何將您的內部 IP 位址新增至 SPF 記錄的詳細資訊，請參閱 ＜ [Set up SPF 避免詐騙的 Office 365 中](../set-up-spf-in-office-365-to-help-prevent-spoofing.md)。</span><span class="sxs-lookup"><span data-stu-id="4a047-p103">When you set up EOP, you added an SPF (sender policy framework) record for EOP to your DNS records. The SPF record helps prevent spoofing. For more information about how an SPF record prevents spoofing and how you can add your on-premises IP addresses to the SPF record, see [Set up SPF in Office 365 to help prevent spoofing](../set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> 
  
## <a name="set-anti-spam-options"></a><span data-ttu-id="4a047-118">設定反垃圾郵件選項</span><span class="sxs-lookup"><span data-stu-id="4a047-118">Set anti-spam options</span></span>

<span data-ttu-id="4a047-p104">管理您的連線篩選設定將 IP 位址新增至 IP 允許和 IP 封鎖清單，並選取 [**啟用安全清單**選項，應減少誤判 （歸類為垃圾郵件的良好郵件） 的數目會收到。深入瞭解[設定連線篩選原則](../configure-the-connection-filter-policy.md)。適用於整個組織的多個垃圾郵件設定，看看[如何協助確保郵件未標示為垃圾郵件](https://go.microsoft.com/fwlink/p/?LinkId=534224)或[封鎖郵件垃圾郵件與 Office 365 垃圾郵件篩選避免 false 負數的問題](https://go.microsoft.com/fwlink/p/?LinkId=534225)。如果您有管理員層級控制與您想要防止誤判或 false 負片，這些是很有幫助。</span><span class="sxs-lookup"><span data-stu-id="4a047-p104">Mange your connection filter settings by adding IP addresses to IP Allow and IP Block lists, and by selecting the **Enable safe list** option, which should reduce the number of false positives (good mail that's classified as spam) you receive. Learn more at [Configure the connection filter policy](../configure-the-connection-filter-policy.md). For more spam settings that apply to the whole organization, take a look at [How to help ensure that a message isn't marked as spam](https://go.microsoft.com/fwlink/p/?LinkId=534224) or [Block email spam with the Office 365 spam filter to prevent false negative issues](https://go.microsoft.com/fwlink/p/?LinkId=534225). These are helpful if you have administrator-level control and you want to prevent false positives or false negatives.</span></span>
  
<span data-ttu-id="4a047-p105">管理內容篩選器來檢閱並選擇性地變更預設的設定。例如，您可以變更動作垃圾郵件偵測到的郵件會發生什麼事。如果您想要執行及垃圾郵件篩選不積極方法，您可以設定進階垃圾郵件篩選選項。我們建議您測試這些選項先之前實作它們在實際執行環境中 （藉由開啟其） 建議擔心網路釣魚的組織開啟**SPF 記錄： 完全未通過**] 選項。深入了解，[設定您的垃圾郵件篩選器原則](../configure-your-spam-filter-policies.md)及[進階垃圾郵件篩選選項](../advanced-spam-filtering-asf-options.md)。</span><span class="sxs-lookup"><span data-stu-id="4a047-p105">Manage your content filters by reviewing and optionally changing the default settings. For example, you can change the action for what happens to spam-detected messages. If you want to pursue an aggressive approach to spam filtering, you can configure advanced spam filtering  options. We recommend that you test these options first before implementing them in your production environment (by turning them on) It's recommended that organizations who are concerned about phishing turn on the **SPF record: hard fail** option. Learn more at [Configure your spam filter policies](../configure-your-spam-filter-policies.md) and [Advanced spam filtering  options](../advanced-spam-filtering-asf-options.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4a047-p106">如果您使用預設內容篩選動作，**移至 [垃圾郵件] 資料夾的郵件**，以確保此動作會搭配內部部署信箱，您必須設定 Exchange 郵件流程規則，也稱為傳輸規則在您內部部署偵測新增的 EOP 的垃圾郵件標頭的伺服器。如需詳細資訊，請參閱[確定垃圾郵件會路由傳送至每位使用者的垃圾郵件] 資料夾](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="4a047-p106">If you are using the default content filter action, **Move message to Junk Email folder**, in order to ensure that this action will work with on-premises mailboxes, you must configure Exchange mail flow rules, also called transport rules, on your on-premises servers to detect spam headers added by EOP. For details, see [Ensure that spam is routed to each user's Junk Email folder](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> 
  
<span data-ttu-id="4a047-130">我們建議您檢閱[反垃圾郵件保護常見問題集](../anti-spam-protection-faq.md)，包括輸出郵寄最佳作法章節內容，以協助確保順利傳送輸出郵件。</span><span class="sxs-lookup"><span data-stu-id="4a047-130">We recommend that you review the [Anti-spam protection FAQ](../anti-spam-protection-faq.md), including the outbound mailing best practices section, which will help ensure that your outbound mail is delivered.</span></span>
  
<span data-ttu-id="4a047-p107">您可以送出 false 負片 （垃圾郵件） 以及誤判 （非垃圾郵件） 給 Microsoft 進行分析的數種方式。如需詳細資訊，請參閱[提交垃圾郵件、 非垃圾郵件和網路釣魚詐騙郵件訊息給 Microsoft 進行分析](../submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)。</span><span class="sxs-lookup"><span data-stu-id="4a047-p107">You can submit false negatives (spam) and false positives (non-spam) to Microsoft for analysis in several ways. For details, see [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](../submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).</span></span>
  
## <a name="set-anti-malware-options"></a><span data-ttu-id="4a047-133">設定反惡意程式碼選項</span><span class="sxs-lookup"><span data-stu-id="4a047-133">Set anti-malware options</span></span>

<span data-ttu-id="4a047-p108">檢閱並進行微調您在 Exchange 系統 center(EAC) 中的惡意程式碼篩選設定。[設定反惡意程式碼原則](../configure-anti-malware-policies.md)深入了解。我們也建議您閱讀其他的常見問題與解答相關我們[反惡意程式碼保護常見問題集](../anti-malware-protection-faq-eop.md)中的反惡意程式碼保護的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="4a047-p108">Review and fine tune your malware filter settings in the Exchange admin center(EAC). Learn more at [Configure anti-malware policies](../configure-anti-malware-policies.md). We also recommend reading about other frequently asked questions and answers pertaining to anti-malware protection in our [Anti-malware protection FAQ ](../anti-malware-protection-faq-eop.md).</span></span>
  
<span data-ttu-id="4a047-p109">如果您擔心包含惡意程式碼的可執行檔案，您可以建立會封鎖任何具有可執行內容之電子郵件附件的 Exchange 郵件流程規則。請遵循[如何透過 Exchange Online Protection 中的檔案附件封鎖降低惡意程式碼的威脅](https://support.microsoft.com/kb/2959596)，以封鎖列在[Use mail flow rules to inspect message attachments](http://technet.microsoft.com/library/874d1c78-a8ec-4938-b388-d3208c2fa971.aspx)中「傳輸規則檢查支援的可執行檔案類型」下的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="4a047-p109">If you're concerned about executable files containing malware, you can create an Exchange mail flow rule that blocks any email attachment that has executable content. Follow the steps in [How to reduce malware threats through file attachment blocking in Exchange Online Protection](https://support.microsoft.com/kb/2959596) in order to block the file types listed under "Supported executable file types for transport rule inspection" in [Use mail flow rules to inspect message attachments](http://technet.microsoft.com/library/874d1c78-a8ec-4938-b388-d3208c2fa971.aspx).</span></span>
  
<span data-ttu-id="4a047-p110">您可以在 EAC 中使用一般的附件類型篩選。選取 [**保護** \> **惡意軟體篩選器**。您可以建立 Exchange 郵件流程規則，也稱為傳輸規則，封鎖任何具有可執行內容的電子郵件附件。</span><span class="sxs-lookup"><span data-stu-id="4a047-p110">You can use the Common Attachment Types Filter in the EAC. Select **protection** \> **malware filters**. You can create an Exchange mail flow rule, also known as transport rule, that blocks any email attachment that has executable content.</span></span> 
  
<span data-ttu-id="4a047-p111">增加 protection 也建議您使用郵件流程規則封鎖某些或所有下列副檔名： ade、 adp、 ani、 bas、 bat、 chm、 cmd、 com、 cpl、 crt、 hlp、 ht、 hta、 inf、 集、 isp、 工作、 js、 jse、 lnk、 mda、 mdb、 mde、 mdz、 msc、 msi、 msp、 mst、 pcd、 reg、 scr、 sct、 shs、 url、 vb、 vbe、 vbs、 wsc 才有、 wsf、 wsh。這可以使用**任何附件副檔名包括這些字詞**條件來完成。</span><span class="sxs-lookup"><span data-stu-id="4a047-p111">For increased protection, we also recommend using mail flow rules to block some or all of the following extensions: ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh. This can be done by using the **Any attachment file extension includes these words** condition.</span></span> 
  
<span data-ttu-id="4a047-p112">系統管理員和使用者可以提交通過篩選器的惡意程式碼，或者提交您認為錯誤識別為惡意程式碼的檔案，將其傳送給 Microsoft 以進行分析。如需詳細資訊，請參閱[Submitting malware and non-malware to Microsoft for analysis](../submitting-malware-and-non-malware-to-microsoft-for-analysis.md)。</span><span class="sxs-lookup"><span data-stu-id="4a047-p112">Administrators and end users can submit malware that made it past the filters, or submit a file that you think was incorrectly identified as malware, by sending it to Microsoft for analysis. For more information, see [Submitting malware and non-malware to Microsoft for analysis](../submitting-malware-and-non-malware-to-microsoft-for-analysis.md).</span></span>
  
## <a name="create-mail-flow-rules"></a><span data-ttu-id="4a047-146">建立郵件流程規則</span><span class="sxs-lookup"><span data-stu-id="4a047-146">Create mail flow rules</span></span>

<span data-ttu-id="4a047-147">建立郵件流程規則 (也叫做傳輸規則或自訂篩選條件) 以符合您的商務需求。</span><span class="sxs-lookup"><span data-stu-id="4a047-147">Create mail flow rules, also called transport rules or custom filters, to meet your business needs.</span></span>
  
<span data-ttu-id="4a047-p113">當您部署至實際執行環境的新規則時，選取其中一個測試模式先查看規則的影響。一旦您滿意所規則會處理預期的方式、 規則模式變更為 [**強制**。</span><span class="sxs-lookup"><span data-stu-id="4a047-p113">When you deploy a new rule to production, select one of the test modes first to see the effect of the rule. Once you are satisfied that the rule is working in the manner intended, change the rule mode to **Enforce**.</span></span>
  
<span data-ttu-id="4a047-150">當您部署新規則時，請考慮新增額外的**產生附隨報告**來監視巨集指令中的規則動作。</span><span class="sxs-lookup"><span data-stu-id="4a047-150">When you deploy new rules, consider adding the additional action of **Generate Incident Report** to monitor the rule in action.</span></span> 
  
<span data-ttu-id="4a047-p114">若您使用混合式部署組態，亦即組織有一部分是內部部署，而另一部分部署在 Office 365 中，則您可以建立規則以整體套用至整個組織。若要這麼做，使用內部部署與 Office 365 部署中都可使用的條件。雖然大部分的條件在這兩種部署中都可使用，但有少數僅適用於特定的部署案例。若要深入了解，請參閱[Mail flow or Transport rules](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4a047-p114">If you are in a hybrid deployment configuration, with part of your organization on-premises and part in Office 365, you can create rules that apply to the entire organization. To do this, use conditions that are available both on-premises and in Office 365. While most conditions are available in both deployments, there is a small set that is specific to a particular deployment scenario. Learn more at [Mail flow or Transport rules](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx).</span></span>
  
<span data-ttu-id="4a047-p115">如果您要對組織內流通的郵件檢查電子郵件附件，您可以設定郵件流程規則。然後，根據其附件的內容或特性，對已檢查的郵件採取動作。若要深入了解，請參閱 [Use mail flow rules to inspect message attachments](http://technet.microsoft.com/library/874d1c78-a8ec-4938-b388-d3208c2fa971.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4a047-p115">If you want to inspect email attachments for messages in-transit within your organization, you can do this by setting up mail flow rules. Then, take action on the messages that were inspected based on the content or characteristics of those attachments. Learn more at [Use mail flow rules to inspect message attachments](http://technet.microsoft.com/library/874d1c78-a8ec-4938-b388-d3208c2fa971.aspx).</span></span>
  
### <a name="phishing-and-spoofing-prevention"></a><span data-ttu-id="4a047-158">預防網路釣魚和詐騙</span><span class="sxs-lookup"><span data-stu-id="4a047-158">Phishing and Spoofing Prevention</span></span>

<span data-ttu-id="4a047-p116">您可以藉由偵測個人資訊是在何時以電子郵件離開組織，以改善防網路釣魚保護。例如，您可以在郵件流程規則中使用下列規則運算式，以偵測可能危害隱私的個人財務資料或資訊傳輸。</span><span class="sxs-lookup"><span data-stu-id="4a047-p116">You can improve anti-phishing protection by the detecting when personal information exits the organization in email. For example, you can use the following regular expressions in mail flow rules to detect transmission of personal financial data or information that may compromise privacy:</span></span>
  
- <span data-ttu-id="4a047-161">\d\d\d\d\s\d\d\d\d\s\d\d\d\d\s\d\d\d\d (MasterCard Visa)</span><span class="sxs-lookup"><span data-stu-id="4a047-161">\d\d\d\d\s\d\d\d\d\s\d\d\d\d\s\d\d\d\d (MasterCard Visa)</span></span>
    
- <span data-ttu-id="4a047-162">\d\d\d\d\s\d\d\d\d\d\d\s\d\d\d\d\d (American Express)</span><span class="sxs-lookup"><span data-stu-id="4a047-162">\d\d\d\d\s\d\d\d\d\d\d\s\d\d\d\d\d (American Express)</span></span>
    
- <span data-ttu-id="4a047-163">\d\d\d\d\d\d\d\d\d\d\d\d\d\d\d\d (任何 16 位數的數字)</span><span class="sxs-lookup"><span data-stu-id="4a047-163">\d\d\d\d\d\d\d\d\d\d\d\d\d\d\d\d (any 16-digit number)</span></span>
    
- <span data-ttu-id="4a047-164">\d\d\d\-\d\d\-\d\d\d\d (社會安全編號)</span><span class="sxs-lookup"><span data-stu-id="4a047-164">\d\d\d\-\d\d\-\d\d\d\d (Social Security Numbers)</span></span>
    
<span data-ttu-id="4a047-p117">封鎖似乎是從自己網域所傳送的內送惡意電子郵件，也可以減少成功的垃圾郵件和網路釣魚活動。例如，您可以建立郵件流程規則，拒絕郵件由貴公司網域傳送到相同的公司網域，以封鎖這種類型的寄件者偽造。</span><span class="sxs-lookup"><span data-stu-id="4a047-p117">Successful spam and phishing campaigns can also be reduced by blocking inbound, malicious emails that appear to have been sent from your own domain. For example, you can create a mail flow rule that rejects messages from your company domain sent to the same company domain to block this type of sender forgery.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="4a047-p118">我們建議只有在您確定您網域中的合法電子郵件不是從網際網路傳送至您的郵件伺服器時，才建立此拒絕規則。當郵件從貴組織中的使用者傳送給外部收件者，隨後又轉寄給貴組織中的其他收件者時，可能會發生這種情形。</span><span class="sxs-lookup"><span data-stu-id="4a047-p118">We recommend creating this reject rule only in cases where you are certain that no legitimate email from your domain is sent from the Internet to your mail server. This can happen in cases where a message is sent from a user in your organization to an outside recipient and subsequently forwarded to another recipient in your organization.</span></span> 
  
### <a name="extension-blocking"></a><span data-ttu-id="4a047-169">副檔名封鎖</span><span class="sxs-lookup"><span data-stu-id="4a047-169">Extension Blocking</span></span>

<span data-ttu-id="4a047-p119">如果您擔心包含惡意程式碼的可執行檔，您可以設定反惡意程式碼原則來封鎖任何具有可執行內容的電子郵件附件。請遵循[設定反惡意程式碼原則](../configure-anti-malware-policies.md)中的步驟。</span><span class="sxs-lookup"><span data-stu-id="4a047-p119">If you're concerned about executable files containing malware, you can configure anti-malware policies to block any email attachment that has executable content. Follow the steps in [Configure anti-malware policies](../configure-anti-malware-policies.md).</span></span>
  
<span data-ttu-id="4a047-172">為了增加防護，我們也建議封鎖下列部分或所有副檔名：ade、adp、ani、bas、bat、chm、cmd、com、cpl、crt、hlp、ht、hta、inf、ins、isp、job、js、jse、lnk、mda、mdb、mde、mdz、msc、msi、msp、mst、pcd、reg、scr、sct、shs、url、vb、vbe、vbs、wsc、wsf、wsh。</span><span class="sxs-lookup"><span data-stu-id="4a047-172">For increased protection, we also recommend that you block some or all of the following extensions: ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh.</span></span>
  
## <a name="reporting-and-troubleshooting"></a><span data-ttu-id="4a047-173">報告和疑難排解</span><span class="sxs-lookup"><span data-stu-id="4a047-173">Reporting and troubleshooting</span></span>

<span data-ttu-id="4a047-p120">使用 Office 365 系統管理中心的報告，對一般問題和趨勢進行疑難排解。使用訊息追蹤工具，尋找關於訊息的單點特定資料。請參閱[Exchange Online Protection 的報告與訊息追蹤](reporting-and-message-trace-in-exchange-online-protection.md)，以深入了解報告功能。請參閱[Trace an Email Message](http://technet.microsoft.com/library/0c83cde6-5b09-4106-8587-c200cdc59094.aspx)，以深入了解郵件追蹤工具。</span><span class="sxs-lookup"><span data-stu-id="4a047-p120">Troubleshoot general issues and trends by using the reports in the Office 365 admin center. Find single point specific data about a message by using the message trace tool. Learn more about reporting at [Reporting and message trace in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md). Learn more about the message trace tool at [Trace an Email Message](http://technet.microsoft.com/library/0c83cde6-5b09-4106-8587-c200cdc59094.aspx).</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="4a047-178">相關資訊</span><span class="sxs-lookup"><span data-stu-id="4a047-178">For more information</span></span>

[<span data-ttu-id="4a047-179">EOP 一般常見問題集</span><span class="sxs-lookup"><span data-stu-id="4a047-179">EOP general FAQ</span></span>](eop-general-faq.md)
  
[<span data-ttu-id="4a047-180">EOP 的說明和支援</span><span class="sxs-lookup"><span data-stu-id="4a047-180">Help and support for EOP</span></span>](help-and-support-for-eop.md)
  
[<span data-ttu-id="4a047-181">EOP 快速入門影片</span><span class="sxs-lookup"><span data-stu-id="4a047-181">Videos for getting started with EOP</span></span>](videos-for-getting-started-with-eop.md)
  
[<span data-ttu-id="4a047-182">如何協助確保郵件不會標示為垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="4a047-182">How to help ensure that a message isn't marked as spam</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[<span data-ttu-id="4a047-183">利用 Office 365 垃圾郵件篩選器封鎖電子郵件垃圾郵件以避免誤判正常</span><span class="sxs-lookup"><span data-stu-id="4a047-183">Block email spam with the Office 365 spam filter to prevent false negative issues</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=534225)
  

