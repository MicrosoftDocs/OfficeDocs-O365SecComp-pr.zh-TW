---
title: 設定 EOP 服務
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/23/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: d74c6ddf-11b0-43ee-b298-8bb0340895f0
description: 本主題說明如何設定 Microsoft Exchange Online Protection (EOP)。如果您從 Office 365 網域精靈進入這裡，而您不希望使用 Exchange Online Protection 的話，請回到 Office 365 網域精靈。如果您正在尋找如何設定連接器的詳細資訊，請參閱Configure mail flow using connectors in Office 365。
ms.openlocfilehash: 6c9e3becf0f86deeee92ec7cf336bdbd950ac5e2
ms.sourcegitcommit: f49ab866e21da83a0be6cb23ab7b6b4366a6a7ee
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "25715899"
---
# <a name="set-up-your-eop-service"></a><span data-ttu-id="faf63-105">設定 EOP 服務</span><span class="sxs-lookup"><span data-stu-id="faf63-105">Set up your EOP service</span></span>

<span data-ttu-id="faf63-p102">本主題說明如何設定 Microsoft Exchange Online Protection (EOP)。如果您從 Office 365 網域精靈進入這裡，而您不希望使用 Exchange Online Protection 的話，請回到 Office 365 網域精靈。如果您正在尋找如何設定連接器的詳細資訊，請參閱[Configure mail flow using connectors in Office 365](http://technet.microsoft.com/library/854b5a50-4462-4836-a092-37e208d29624.aspx)。</span><span class="sxs-lookup"><span data-stu-id="faf63-p102">This topic explains how to set up Microsoft Exchange Online Protection (EOP). If you landed here from the Office 365 domains wizard, go back to the Office 365 domains wizard if you don't want to use Exchange Online Protection. If you're looking for more information on how to configure connectors, see [Configure mail flow using connectors in Office 365](http://technet.microsoft.com/library/854b5a50-4462-4836-a092-37e208d29624.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="faf63-p103">本主題假設您擁有內部部署信箱，且您想要使用 EOP 來保護這些信箱 (稱為獨立案例)。如果您想要使用 Exchange Online 在雲端中裝載所有的信箱，並不需要完成本主題中所有的步驟。請移至 [Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286312) 來註冊及購買雲端信箱。如果您想要將一部分信箱裝載在內部部署、一部分信箱裝載在雲端中，這稱為 混合案例。這需要更進階的郵件流程設定。[Exchange Server 2013 Hybrid Deployments](http://technet.microsoft.com/library/59e32000-4fcf-417f-a491-f1d8f9aeef9b.aspx)會說明混合郵件流程，並提供一些說明相關設定方式的連結。</span><span class="sxs-lookup"><span data-stu-id="faf63-p103">This topic assumes you have on-premises mailboxes and you want to protect them with EOP, which is known as a standalone scenario. If you want to host all of your mailboxes in the cloud with Exchange Online, you don't have to complete all of the steps in this topic. Go to [Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286312) to sign up and purchase cloud mailboxes. If you want to host some of your mailboxes on premises and some in the cloud, this is known as a hybrid scenario. It requires more advanced mail-flow settings. [Exchange Server 2013 Hybrid Deployments](http://technet.microsoft.com/library/59e32000-4fcf-417f-a491-f1d8f9aeef9b.aspx) explains hybrid mail flow and has links to resources that show how to set it up.</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="faf63-115">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="faf63-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="faf63-116">完成此工作的預估時間：1 小時</span><span class="sxs-lookup"><span data-stu-id="faf63-116">Estimated time to complete this task: 1 hour</span></span>
    
- <span data-ttu-id="faf63-p104">若要設定連接器，您的帳戶必須是 Office 365 全域管理員或 Exchange 公司管理員 (組織管理角色群組)。如需 Office 365 權限與 Exchange 權限之關係的相關資訊，請參閱 [Office 365 中的權限](https://go.microsoft.com/fwlink/p/?LinkID=335814)。</span><span class="sxs-lookup"><span data-stu-id="faf63-p104">To configure connectors, your account must be an Office 365 Global Admin, or an Exchange Company Administrator (the Organization Management role group). For information about how Office 365 permissions relate to Exchange permissions, see [Permissions in Office 365](https://go.microsoft.com/fwlink/p/?LinkID=335814).</span></span>
    
- <span data-ttu-id="faf63-119">如果您尚未註冊 EOP，請造訪 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?LinkId=282660)，並選擇購買或試用服務。</span><span class="sxs-lookup"><span data-stu-id="faf63-119">If you haven't signed up for EOP, visit [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?LinkId=282660) and choose to buy or try the service.</span></span> 
    
- <span data-ttu-id="faf63-120">如需適用於此主題中程序的快速鍵相關資訊，請參閱 **Keyboard shortcuts in Exchange 2013**。</span><span class="sxs-lookup"><span data-stu-id="faf63-120">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
> [!TIP]
> <span data-ttu-id="faf63-p105">有問題嗎？在 Exchange 論壇中尋求協助。 論壇的網址為：[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)或 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。</span><span class="sxs-lookup"><span data-stu-id="faf63-p105">Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="how-do-you-do-this"></a><span data-ttu-id="faf63-124">該怎麼做？</span><span class="sxs-lookup"><span data-stu-id="faf63-124">How do you do this?</span></span>

### <a name="step-1-use-the-office-365-admin-center-to-add-and-verify-your-domain"></a><span data-ttu-id="faf63-125">步驟 1：使用 Office 365 系統管理中心 新增及確認您的網域</span><span class="sxs-lookup"><span data-stu-id="faf63-125">Step 1: Use the Office 365 admin center to add and verify your domain</span></span>

1. <span data-ttu-id="faf63-126">在 Office 365 系統管理中心中，瀏覽至您的網域新增至服務的**安裝程式**。</span><span class="sxs-lookup"><span data-stu-id="faf63-126">In the Office 365 admin center, navigate to **Setup** to add your domain to the service.</span></span> 
    
    <span data-ttu-id="faf63-p106">不確定要前往何處尋找 Office 365 系統管理中心？請參閱[關於 Office 365 系統管理中心](https://go.microsoft.com/fwlink/p/?LinkId=521888)以深入了解。</span><span class="sxs-lookup"><span data-stu-id="faf63-p106">Not sure where to find the Office 365 admin center? Learn more at [About the Office 365 admin center](https://go.microsoft.com/fwlink/p/?LinkId=521888).</span></span>
    
2. <span data-ttu-id="faf63-129">請遵循這些步驟，將適用的 DNS 記錄新增到 DNS 主機提供者，以便驗證網域擁有權。</span><span class="sxs-lookup"><span data-stu-id="faf63-129">Follow the steps to add the applicable DNS records to your DNS-hosting provider in order to verify domain ownership.</span></span>
    
> [!TIP]
> <span data-ttu-id="faf63-130">當您新增網域至此服務並設定 DNS 時，[新增網域至 Office 365](https://support.office.com/en-us/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611) 和 [建立 Office 365 的 DNS 記錄](https://support.office.com/en-us/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)，是有用的參考資源。</span><span class="sxs-lookup"><span data-stu-id="faf63-130">[Add your domain to Office 365](https://support.office.com/en-us/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611) and [Create DNS records for Office 365](https://support.office.com/en-us/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166) are helpful resources to reference as you add your domain to the service and configure DNS.</span></span> 
  
### <a name="step-2-add-recipients-and-optionally-enable-dbeb"></a><span data-ttu-id="faf63-131">步驟 2：新增收件者並選擇性地啟用 DBEB</span><span class="sxs-lookup"><span data-stu-id="faf63-131">Step 2: Add recipients and optionally enable DBEB</span></span>

<span data-ttu-id="faf63-p107">在設定您的郵件來進出 EOP 服務之前，建議您將收件者新增至服務。有許多種作法，請參閱＜[管理 EOP 中的郵件使用者](manage-mail-users-in-eop.md)＞。另外，如果您要啟用目錄架構邊緣封鎖 (DBEB)，以便在服務內新增收件者之後強制驗證收件者，則必須將網域類型設為「授權」。如需 DBEB 的相關資訊，請參閱[Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx)。</span><span class="sxs-lookup"><span data-stu-id="faf63-p107">Before configuring your mail to flow to and from the EOP service, we recommend adding your recipients to the service. There are several ways in which you can do this, as documented in [Manage mail users in EOP](manage-mail-users-in-eop.md). Also, if you want to enable Directory Based Edge Blocking (DBEB) in order to enforce recipient verification within the service after adding your recipients, you need to set your domain type to Authoritative. For more information about DBEB, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx).</span></span>
  
### <a name="step-3-use-the-eac-to-set-up-mail-flow"></a><span data-ttu-id="faf63-136">步驟 3：使用 EAC 來設定郵件流程</span><span class="sxs-lookup"><span data-stu-id="faf63-136">Step 3: Use the EAC to set up mail flow</span></span>

<span data-ttu-id="faf63-p108">在 Exchange 系統管理中心 (EAC) 中建立連接器，以啟用 EOP 與您內部部署郵件伺服器之間的郵件流程。如需詳細指示，請參閱 [Set up connectors to route mail between Office 365 and your own email servers](http://technet.microsoft.com/library/2e93fd60-a5ef-4e64-8e62-2b862b2d1033.aspx)。</span><span class="sxs-lookup"><span data-stu-id="faf63-p108">Create connectors in the Exchange admin center (EAC) that enable mail flow between EOP and your on-premises mail servers. For detailed instructions, see [Set up connectors to route mail between Office 365 and your own email servers](http://technet.microsoft.com/library/2e93fd60-a5ef-4e64-8e62-2b862b2d1033.aspx).</span></span>
  
#### <a name="how-do-you-know-this-task-worked"></a><span data-ttu-id="faf63-139">如何才能了解此工作是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="faf63-139">How do you know this task worked?</span></span>

<span data-ttu-id="faf63-p109">使用 Remote Connectivity Analyzer 執行用來檢查服務與您環境間之郵件流程的測試。如需詳細資訊，請參閱[Testing Mail Flow with the Remote Connectivity Analyzer](http://technet.microsoft.com/library/6c8c2964-d553-4329-8166-6e508dd63fa0.aspx)中的「使用 Remote Connectivity Analyzer 來測試電子郵件傳遞」一節。</span><span class="sxs-lookup"><span data-stu-id="faf63-p109">Use the Remote Connectivity Analyzer to run a test that checks mail flow between the service and your environment. For more information, see the "Use the Remote Connectivity Analyzer to test email delivery" section in [Testing Mail Flow with the Remote Connectivity Analyzer](http://technet.microsoft.com/library/6c8c2964-d553-4329-8166-6e508dd63fa0.aspx).</span></span>
  
### <a name="step-4-allow-inbound-port-25-smtp-access"></a><span data-ttu-id="faf63-142">步驟 4：允許輸入連接埠 25 SMTP 存取</span><span class="sxs-lookup"><span data-stu-id="faf63-142">Step 4: Allow inbound port 25 SMTP access</span></span>

<span data-ttu-id="faf63-p110">設定連接器之後，請等待 72 小時以允許傳播 DNS 記錄更新。接著限制防火牆或郵件伺服器上的通訊埠 25 SMTP 流量，以僅接受來自 EOP 資料中心的郵件 (尤其是來自 [Exchange Online Protection IP 位址](exchange-online-protection-ip-addresses.md) 所列 IP 位址的郵件)。這會限制您可接收的輸入郵件範圍，以保護內部部署環境的安全。此外，若您在郵件伺服器上進行設定，以控制允許連線執行郵件轉送的 IP 位址，請一併更新這些設定。</span><span class="sxs-lookup"><span data-stu-id="faf63-p110">After you configured connectors, wait 72 hours to allow propagation of your DNS-record updates. Following this, restrict inbound port-25 SMTP traffic on your firewall or mail servers to accept mail only from the EOP datacenters, specifically from the IP addresses listed at [Exchange Online Protection IP addresses](exchange-online-protection-ip-addresses.md). This protects your on-premises environment by limiting the scope of inbound messages you can receive. Additionally, if you have settings on your mail server that control the IP addresses allowed to connect for mail relay, update those settings as well.</span></span>
  
> [!TIP]
> <span data-ttu-id="faf63-p111">將 SMTP 伺服器的連線時間設定設為超過 60 秒。此設定適用於大部分情況，例如在傳送具有大型附件的郵件時可稍許延遲。</span><span class="sxs-lookup"><span data-stu-id="faf63-p111">Configure settings on the SMTP server with a connection time out of 60 seconds. This setting is acceptable for most situations, allowing for some delay in the case of a message sent with a large attachment, for instance.</span></span> 
  
### <a name="step-5-use-the-shell-to-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a><span data-ttu-id="faf63-149">步驟 5：使用命令介面確定垃圾郵件路由傳送至每個使用者的垃圾電子郵件資料夾</span><span class="sxs-lookup"><span data-stu-id="faf63-149">Step 5: Use the Shell to ensure that spam is routed to each user's junk email folder</span></span>

<span data-ttu-id="faf63-p112">若要確保垃圾郵件 （垃圾郵件） 郵件正確地傳送至每位使用者的垃圾郵件資料夾，您必須執行一些設定步驟。[確定垃圾郵件會路由傳送至每位使用者的垃圾郵件] 資料夾](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)中提供的步驟。</span><span class="sxs-lookup"><span data-stu-id="faf63-p112">To ensure that spam (junk) email is routed correctly to each user's Junk Email folder, you must perform a couple of configuration steps. The steps are provided in [Ensure that spam is routed to each user's Junk Email folder](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span>
  
<span data-ttu-id="faf63-p113">如果您不想將郵件移至每位使用者的垃圾郵件] 資料夾，您可以選擇另一個巨集指令來編輯您在 Exchange 系統管理中心中的內容篩選原則。如需詳細資訊，請參閱[設定垃圾郵件篩選器原則](../configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="faf63-p113">If you don't want to move messages to each user's Junk Email folder, you may choose another action by editing your content filter policies in the Exchange admin center. For more information, see [Configure your spam filter policies](../configure-your-spam-filter-policies.md).</span></span>
  
### <a name="step-6-use-the-office-365-admin-center-to-point-your-mx-record-to-eop"></a><span data-ttu-id="faf63-154">步驟 6：使用 Office 365 系統管理中心 將您的 MX 記錄指向 EOP</span><span class="sxs-lookup"><span data-stu-id="faf63-154">Step 6: Use the Office 365 admin center to point your MX record to EOP</span></span>

<span data-ttu-id="faf63-p114">遵循 Office 365 網域組態步驟來更新網域的 MX 記錄，讓您的輸入電子郵件流過 EOP。請務必直接將 MX 記錄指向 EOP 而非讓協力廠商篩選服務將郵件轉送至 EOP。如需詳細資訊，請再次參照[建立 Office 365 的 DNS 記錄](https://go.microsoft.com/fwlink/p/?LinkId=304219)。</span><span class="sxs-lookup"><span data-stu-id="faf63-p114">Follow the Office 365 domain configuration steps to update your MX record for your domain, so that your inbound email flows through EOP. Be sure to point your MX record directly to EOP as opposed to having a third-party filtering service relay email to EOP. For more information, you can again reference [Create DNS records for Office 365](https://go.microsoft.com/fwlink/p/?LinkId=304219).</span></span>
  
#### <a name="how-do-you-know-this-task-worked"></a><span data-ttu-id="faf63-158">如何才能了解此工作是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="faf63-158">How do you know this task worked?</span></span>

<span data-ttu-id="faf63-p115">使用 Remote Connectivity Analyzer 執行用來驗證您 MX 記錄的測試。如需詳細資訊，請參閱[Testing Mail Flow with the Remote Connectivity Analyzer](http://technet.microsoft.com/library/6c8c2964-d553-4329-8166-6e508dd63fa0.aspx)中的「使用 Remote Connectivity Analyzer 來測試 MX 記錄和輸出連接器」一節。</span><span class="sxs-lookup"><span data-stu-id="faf63-p115">Use the Remote Connectivity Analyzer to run a test that verifies your MX record. For more information, see the "Use the Remote Connectivity Analyzer to test your MX record and Outbound connector" section in [Testing Mail Flow with the Remote Connectivity Analyzer](http://technet.microsoft.com/library/6c8c2964-d553-4329-8166-6e508dd63fa0.aspx).</span></span> 
  
<span data-ttu-id="faf63-p116">到目前為止，您已確定有正確設定的輸出內部部署連接器可用來進行服務傳遞，並已確認 MX 記錄是指向 EOP。現在您可以選擇執行下列其他測試，以確認服務能夠成功將電子郵件傳遞至您的內部部署環境：</span><span class="sxs-lookup"><span data-stu-id="faf63-p116">At this point, you've verified service delivery for a properly configured Outbound on-premises connector, and you've verified that your MX record is pointing to EOP. You can now choose to run the following additional tests to verify that an email will be successfully delivered by the service to your on-premises environment:</span></span>
  
- <span data-ttu-id="faf63-163">在 Remote Connectivity Analyzer 中，按一下 **[Office 365]** 索引標籤，然後執行位於 **[網際網路電子郵件測試]** 底下的 **[輸入 SMTP 電子郵件]** 測試。</span><span class="sxs-lookup"><span data-stu-id="faf63-163">In the Remote Connectivity Analyzer, click the **Office 365** tab, and then run the **Inbound SMTP Email** test located under **Internet Email Tests**.</span></span> 
    
- <span data-ttu-id="faf63-p117">從任何其網域符合您新增至此服務之網域的 Web 式電子郵件帳戶，傳送電子郵件給您組織中的郵件收件者。使用 Microsoft Outlook 或其他電子郵件用戶端，確認郵件已傳遞至內部部署信箱。</span><span class="sxs-lookup"><span data-stu-id="faf63-p117">Send an email message from any web-based email account to a mail recipient in your organization whose domain matches the domain you added to the service. Confirm delivery of the message to the on-premises mailbox using Microsoft Outlook or another email client.</span></span>
    
- <span data-ttu-id="faf63-166">如果您想要執行輸出電子郵件測試，可以從組織中的使用者傳送電子郵件到 Web 式電子郵件帳戶，再確認郵件是否已收到。</span><span class="sxs-lookup"><span data-stu-id="faf63-166">If you want to run an outbound email test, you can send an email message from a user in your organization to a web-based email account and confirm that the message is received.</span></span>
    
> [!TIP]
> <span data-ttu-id="faf63-p118">當您完成設定時，不需要執行額外步驟即可讓 EOP 移除垃圾郵件和惡意軟體。EOP 會自動移除垃圾郵件和惡意軟體。不過，您可以根據本身的商務需求來微調 EAC 中的設定。如需詳細資訊，請參閱 [Anti-Spam and Anti-Malware Protection](http://technet.microsoft.com/library/93c6c227-7442-4293-b64d-ec8f15c928db.aspx)。 > 現在您的服務在執行中，建議您閱讀[設定 EOP 的最佳作法](best-practices-for-configuring-eop.md)，其中會說明設定好 EOP 後的建議設定和注意事項。</span><span class="sxs-lookup"><span data-stu-id="faf63-p118">When you've completed your setup, you don't have to perform extra steps to make EOP remove spam and malware. EOP removes spam and malware automatically. However, you can fine tune your settings in the EAC, based on your business requirements. For more information, see [Anti-Spam and Anti-Malware Protection](http://technet.microsoft.com/library/93c6c227-7442-4293-b64d-ec8f15c928db.aspx). > Now that your service is running, we recommend reading [Best practices for configuring EOP](best-practices-for-configuring-eop.md), which describes recommended settings and considerations for after you set up EOP.</span></span> 
  

