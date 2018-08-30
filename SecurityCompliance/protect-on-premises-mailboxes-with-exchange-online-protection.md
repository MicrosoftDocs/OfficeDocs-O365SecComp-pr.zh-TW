---
title: 保護與 Exchange Online Protection 的內部部署信箱
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/1/2017
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- GEU150
- GMA150
- GPA150
- MET150
ms.assetid: c5e95951-da67-4ec7-92c5-982abd477e69
description: 即使您要裝載某些或所有信箱內部，您仍然可以保護信箱與 Exchange Online Protection (EOP)。若要設定連接器，您的帳戶必須是 Office 365 全域管理員或 Exchange 公司管理員 （組織管理角色群組）。關於 Office 365 的權限如何與 Exchange 權限的資訊，請參閱在 Office 365 21vianet 21Vianet 來指派管理員角色。如果您的 Exchange 信箱的所有內部部署，請遵循下列步驟來設定 EOP 服務。
ms.openlocfilehash: 4751bb2183e61d292805d1799519644b77b08c2a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22527404"
---
# <a name="protect-on-premises-mailboxes-with-exchange-online-protection"></a><span data-ttu-id="380db-106">保護與 Exchange Online Protection 的內部部署信箱</span><span class="sxs-lookup"><span data-stu-id="380db-106">Protect on-premises mailboxes with Exchange Online Protection</span></span>

> [!NOTE]
> <span data-ttu-id="380db-107">本文僅適用於 Office 365 以中國的 21Vianet 所運作。</span><span class="sxs-lookup"><span data-stu-id="380db-107">This article applies only to Office 365 operated by 21Vianet in China.</span></span> 
  
<span data-ttu-id="380db-p102">即使您要裝載某些或所有信箱內部，您仍然可以保護信箱與 Exchange Online Protection (EOP)。若要設定連接器，您的帳戶必須是 Office 365 全域管理員或 Exchange 公司管理員 （組織管理角色群組）。關於 Office 365 的權限如何與 Exchange 權限的資訊，請參閱[在 Office 365 21vianet 21Vianet 來指派管理員角色](https://support.office.com/article/d58b8089-cbfd-41ec-b64c-9cfcbef495ac)。如果您的 Exchange 信箱的所有內部部署，請遵循下列步驟來設定 EOP 服務。</span><span class="sxs-lookup"><span data-stu-id="380db-p102">Even if you plan to host some or all of your mailboxes on-premises, you can still protect the mailboxes with Exchange Online Protection (EOP). To configure connectors, your account must be an Office 365 Global Admin, or an Exchange Company Administrator (the Organization Management role group). For information about how Office 365 permissions relate to Exchange permissions, see [Assigning admin roles in Office 365 operated by 21Vianet](https://support.office.com/article/d58b8089-cbfd-41ec-b64c-9cfcbef495ac). If all of your Exchange mailboxes are on-premise, follow these steps to set up your EOP service.</span></span> 
  
## <a name="step-1-use-the-office-365-admin-center-to-add-and-verify-your-domain"></a><span data-ttu-id="380db-112">步驟 1：使用 Office 365 系統管理中心 新增及確認您的網域</span><span class="sxs-lookup"><span data-stu-id="380db-112">Step 1: Use the Office 365 admin center to add and verify your domain</span></span>

1. <span data-ttu-id="380db-113">在 Office 365 系統管理中心中，瀏覽至 [設定您的網域新增至服務。</span><span class="sxs-lookup"><span data-stu-id="380db-113">In the Office 365 admin center, navigate to Setup to add your domain to the service.</span></span>
    
2.  <span data-ttu-id="380db-114">遵循以便驗證網域擁有權將適用的 DNS 記錄新增至您的 DNS 主機供應商入口網站中的步驟。</span><span class="sxs-lookup"><span data-stu-id="380db-114">Follow the steps in the portal to add the applicable DNS records to your DNS-hosting provider in order to verify domain ownership.</span></span> 
    
> [!TIP]
> <span data-ttu-id="380db-115">[新增您的網域和使用者在 Office 365 的 21Vianet 21vianet](https://support.office.com/article/1cd4839b-d051-46b8-ab9b-bc7752024e78)和[建立 DNS 記錄的 Office 365 管理 DNS 記錄時](https://support.office.com/article/0669bf14-414d-4f51-8231-6b710ce7980b)所參照當您新增網域至此服務並設定 DNS 的實用資源。</span><span class="sxs-lookup"><span data-stu-id="380db-115">[Add your domain and users to Office 365 operated by 21Vianet](https://support.office.com/article/1cd4839b-d051-46b8-ab9b-bc7752024e78) and [Create DNS records for Office 365 when you manage your DNS records](https://support.office.com/article/0669bf14-414d-4f51-8231-6b710ce7980b) are helpful resources to reference as you add your domain to the service and configure DNS.</span></span> 
  
### <a name="step-2-add-recipients-and-configure-the-domain-type"></a><span data-ttu-id="380db-116">步驟 2：新增收件者和設定網域類型</span><span class="sxs-lookup"><span data-stu-id="380db-116">Step 2: Add recipients and configure the domain type</span></span>

<span data-ttu-id="380db-p103">在設定您的郵件來進出 EOP 服務之前，建議您將收件者新增至服務。有許多種作法，請參閱＜[管理 EOP 中的郵件使用者](https://go.microsoft.com/fwlink/?LinkId=506782)＞。另外，如果您要啟用目錄架構邊緣封鎖 (DBEB)，以便在服務內新增收件者之後強制驗證收件者，則必須將網域類型設為「授權」。如需 DBEB 的相關資訊，請參閱[Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://go.microsoft.com/fwlink/?LinkId=506781)。</span><span class="sxs-lookup"><span data-stu-id="380db-p103">Before configuring your mail to flow to and from the EOP service, we recommend adding your recipients to the service. There are several ways in which you can do this, as documented in [Manage mail users in EOP](https://go.microsoft.com/fwlink/?LinkId=506782). Also, if you want to enable Directory Based Edge Blocking (DBEB) in order to enforce recipient verification within the service after adding your recipients, you need to set your domain type to Authoritative. For more information about DBEB, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://go.microsoft.com/fwlink/?LinkId=506781).</span></span>
  
## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a><span data-ttu-id="380db-121">步驟 3：使用 EAC 來設定郵件流程</span><span class="sxs-lookup"><span data-stu-id="380db-121">Step 3: Use the EAC to set up mail flow</span></span>

<span data-ttu-id="380db-p104">啟用 EOP 與內部部署郵件伺服器之間的郵件流程 Exchange 系統管理中心 (EAC) 中建立連接器。如需詳細指示，請參閱[建立所需連接器來設定經由 EOP 的基本的電子郵件流程](https://go.microsoft.com/fwlink/?LinkId=506780)。</span><span class="sxs-lookup"><span data-stu-id="380db-p104">Create connectors in the Exchange admin center (EAC) that enable mail flow between EOP and your on-premises mail servers. For detailed instructions, see [Create required connectors to set up basic email flow through EOP](https://go.microsoft.com/fwlink/?LinkId=506780).</span></span>
  
 <span data-ttu-id="380db-124">如何才能了解此工作是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="380db-124">How do you know this task worked?</span></span> 
  
 <span data-ttu-id="380db-p105">使用 Remote Connectivity Analyzer 來執行測試，以檢查服務] 和 [您的環境之間的郵件流程。如需詳細資訊，請參閱 「 使用 Remote Connectivity Analyzer 來測試電子郵件傳遞 」 一節中[測試與遠端連線分析程式郵件流程](https://go.microsoft.com/fwlink/?LinkId=506784)。</span><span class="sxs-lookup"><span data-stu-id="380db-p105">Use the Remote Connectivity Analyzer to run a test that checks mail flow between the service and your environment. For more information, see the "Use the Remote Connectivity Analyzer to test email delivery" section in [Test mail flow with the Remote Connectivity Analyzer](https://go.microsoft.com/fwlink/?LinkId=506784).</span></span>
  
## <a name="step-4-allow-inbound-port-25-smtp-access"></a><span data-ttu-id="380db-127">步驟 4：允許輸入連接埠 25 SMTP 存取</span><span class="sxs-lookup"><span data-stu-id="380db-127">Step 4: Allow inbound port 25 SMTP access</span></span>

<span data-ttu-id="380db-p106">設定連接器之後，等待允許您的 DNS 記錄更新的傳播 72 個小時。下列，限制在防火牆或郵件伺服器接受郵件僅來自 EOP 資料中心，特別是從列在[Url 和 IP 位址範圍的 21Vianet 來運作 Office 365](https://support.office.com/article/5c47c07d-f9b6-4b78-a329-bfdc1b6da7a0#__exchange_online_protection)的 IP 位址上輸入連接埠 25 SMTP 流量。這會用來保護您的內部部署環境限制可接收內送郵件的範圍。此外，如果您有設定信箱伺服器上，以控制允許的郵件轉送連線的 IP 位址、 更新以及的那些設定。</span><span class="sxs-lookup"><span data-stu-id="380db-p106">After you configured connectors, wait 72 hours to allow propagation of your DNS-record updates. Following this, restrict inbound port-25 SMTP traffic on your firewall or mail servers to accept mail only from the EOP datacenters, specifically from the IP addresses listed at [URLs and IP address ranges for Office 365 operated by 21Vianet](https://support.office.com/article/5c47c07d-f9b6-4b78-a329-bfdc1b6da7a0#__exchange_online_protection). This protects your on-premises environment by limiting the scope of inbound messages you can receive. Additionally, if you have settings on your mail server that control the IP addresses allowed to connect for mail relay, update those settings as well.</span></span>
  
> [!TIP]
> <span data-ttu-id="380db-p107">將 SMTP 伺服器的連線時間設定設為超過 60 秒。此設定適用於大部分情況，例如在傳送具有大型附件的郵件時可稍許延遲。</span><span class="sxs-lookup"><span data-stu-id="380db-p107">Configure settings on the SMTP server with a connection time out of 60 seconds. This setting is acceptable for most situations, allowing for some delay in the case of a message sent with a large attachment, for instance.</span></span> 
  
## <a name="step-5-use-the-shell-to-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a><span data-ttu-id="380db-134">步驟 5：使用命令介面確定垃圾郵件路由傳送至每個使用者的垃圾電子郵件資料夾</span><span class="sxs-lookup"><span data-stu-id="380db-134">Step 5: Use the Shell to ensure that spam is routed to each user's junk email folder</span></span>

<span data-ttu-id="380db-p108">若要確保垃圾郵件 （垃圾郵件） 郵件正確地傳送至每位使用者的垃圾郵件資料夾，您必須執行一些設定步驟。[確定垃圾郵件會路由傳送至每位使用者的垃圾郵件] 資料夾](https://go.microsoft.com/fwlink/?LinkId=506804)中提供的步驟。如果您不想將郵件移至每位使用者的垃圾郵件] 資料夾，您可以選擇另一個巨集指令來編輯您在 Exchange 系統管理中心中的內容篩選原則。如需詳細資訊，請參閱 ＜ [Configure Content Filter Policies](https://go.microsoft.com/fwlink/?LinkId=506805)。</span><span class="sxs-lookup"><span data-stu-id="380db-p108">To ensure that spam (junk) email is routed correctly to each user's Junk Email folder, you must perform a couple of configuration steps. The steps are provided in [Ensure that spam is routed to each user's Junk Email folder](https://go.microsoft.com/fwlink/?LinkId=506804). If you don't want to move messages to each user's Junk Email folder, you may choose another action by editing your content filter policies in the Exchange admin center. For more information, see [Configure Content Filter Policies](https://go.microsoft.com/fwlink/?LinkId=506805).</span></span> 
  
## <a name="step-6-use-the-office-365-admin-center-to-point-your-mx-record-to-eop"></a><span data-ttu-id="380db-139">步驟 6：使用 Office 365 系統管理中心 將您的 MX 記錄指向 EOP</span><span class="sxs-lookup"><span data-stu-id="380db-139">Step 6: Use the Office 365 admin center to point your MX record to EOP</span></span>

<span data-ttu-id="380db-p109">遵循的 Office 365 網域組態步驟來更新您的 MX 記錄您的網域，以便內送電子郵件通過 EOP。如需詳細資訊，您可以一次參照[的 Office 365 管理 DNS 記錄時建立 DNS 記錄](https://support.office.com/article/0669bf14-414d-4f51-8231-6b710ce7980b)。</span><span class="sxs-lookup"><span data-stu-id="380db-p109">Follow the Office 365 domain configuration steps to update your MX record for your domain, so that your inbound email flows through EOP. For more information, you can again reference [Create DNS records for Office 365 when you manage your DNS records](https://support.office.com/article/0669bf14-414d-4f51-8231-6b710ce7980b).</span></span>
  
<span data-ttu-id="380db-142">如何才能了解此工作是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="380db-142">How do you know this task worked?</span></span>
  
 <span data-ttu-id="380db-p110">使用 Remote Connectivity Analyzer 來執行測試，確認您的 MX 記錄。如需詳細資訊，請參閱 「 使用 Remote Connectivity Analyzer 來測試 MX 記錄和輸出連接器 」 一節中[測試與遠端連線分析程式郵件流程](https://go.microsoft.com/fwlink/?LinkId=506784)。</span><span class="sxs-lookup"><span data-stu-id="380db-p110">Use the Remote Connectivity Analyzer to run a test that verifies your MX record. For more information, see the "Use the Remote Connectivity Analyzer to test your MX record and Outbound connector" section in [Test mail flow with the Remote Connectivity Analyzer](https://go.microsoft.com/fwlink/?LinkId=506784).</span></span> 
  
<span data-ttu-id="380db-p111">到目前為止，您已確定有正確設定的輸出內部部署連接器可用來進行服務傳遞，並已確認 MX 記錄是指向 EOP。現在您可以選擇執行下列其他測試，以確認服務能夠成功將電子郵件傳遞至您的內部部署環境：</span><span class="sxs-lookup"><span data-stu-id="380db-p111">At this point, you've verified service delivery for a properly configured Outbound on-premises connector, and you've verified that your MX record is pointing to EOP. You can now choose to run the following additional tests to verify that an email will be successfully delivered by the service to your on-premises environment:</span></span>
  
- <span data-ttu-id="380db-147">在 Remote Connectivity Analyzer 中，按一下 **[Office 365]** 索引標籤，然後執行位於 **[網際網路電子郵件測試]** 底下的 **[輸入 SMTP 電子郵件]** 測試。</span><span class="sxs-lookup"><span data-stu-id="380db-147">In the Remote Connectivity Analyzer, click the **Office 365** tab, and then run the **Inbound SMTP Email** test located under **Internet Email Tests**.</span></span>
    
- <span data-ttu-id="380db-p112">從任何其網域符合您新增至此服務之網域的 Web 式電子郵件帳戶，傳送電子郵件給您組織中的郵件收件者。使用 Microsoft Outlook 或其他電子郵件用戶端，確認郵件已傳遞至內部部署信箱。</span><span class="sxs-lookup"><span data-stu-id="380db-p112">Send an email message from any web-based email account to a mail recipient in your organization whose domain matches the domain you added to the service. Confirm delivery of the message to the on-premises mailbox using Microsoft Outlook or another email client.</span></span>
    
- <span data-ttu-id="380db-150">如果您想要執行輸出電子郵件測試，可以從組織中的使用者傳送電子郵件到 Web 式電子郵件帳戶，再確認郵件是否已收到。</span><span class="sxs-lookup"><span data-stu-id="380db-150">If you want to run an outbound email test, you can send an email message from a user in your organization to a web-based email account and confirm that the message is received.</span></span>
    
## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a><span data-ttu-id="380db-151">比較不通用： 信箱內部部署和雲端中混合式設定</span><span class="sxs-lookup"><span data-stu-id="380db-151">Less common: A hybrid setup with mailboxes on-premises and in the cloud</span></span>

<span data-ttu-id="380db-p113">如果您有 Exchange 信箱的內部部署與一個或多個信箱在 Exchange Online 中雲端，您必須在*混合式*設定。在混合式設定中，例如功能空閒/忙碌行事曆共用和郵件路由傳送您內部部署中的共同作業和雲端環境。您可能已經在混合式設定備妥轉換至 Exchange Online 信箱時。不同 EOP 獨立保護設定混合式環境。</span><span class="sxs-lookup"><span data-stu-id="380db-p113">If you have Exchange mailboxes on-premises and one or more mailboxes in the cloud in Exchange Online, you have a  *hybrid*  setup. In a hybrid setup, features such as free/busy calendar sharing and mail routing work together in your on-premises and cloud environments. You might have a hybrid setup in place while you transition mailboxes to Exchange Online. A hybrid environment is set up differently than EOP standalone protection.</span></span> 
  
<span data-ttu-id="380db-p114">您可能會選擇利用雲端式電子郵件的員工大部分的混合式案例。您可以這麼做時也裝載一些信箱的內部;例如，針對您法務部門。</span><span class="sxs-lookup"><span data-stu-id="380db-p114">You might choose a hybrid scenario to take advantage of cloud-based email for most of your employees. You can do this while also hosting some mailboxes on-premises; for example, for your legal department.</span></span> 
  
<span data-ttu-id="380db-p115">在混合式設定可能會很複雜，但有許多好處。若要深入了解設定與 Exchange 的混合式案例，請參閱[Office 365 21vianet 21Vianet 來設定 Exchange 混合部署功能](https://support.office.com/article/26e7cc26-c980-4cc5-a082-c333de544b6d)。</span><span class="sxs-lookup"><span data-stu-id="380db-p115">A hybrid setup can be complex, but it has many benefits. To learn more about setting up hybrid scenarios with Exchange, see [Configuring Exchange hybrid deployment features with Office 365 operated by 21Vianet](https://support.office.com/article/26e7cc26-c980-4cc5-a082-c333de544b6d).</span></span>
  

