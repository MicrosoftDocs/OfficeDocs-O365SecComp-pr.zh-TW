---
title: Exchange Online Protection 概觀
ms.author: tracyp
author: MSFTTracyp
manager: laurawi
ms.date: 01/31/2019
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
description: Microsoft Exchange Online Protection (EOP) 是雲端式的電子郵件篩選服務，它能協助組織抵禦垃圾郵件和惡意軟體，同時也包括預防組織發生訊息原則違規的功能。
ms.openlocfilehash: 3f00cc07058bd2399732299b3221ebd4258dc5ff
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341624"
---
# <a name="exchange-online-protection-overview"></a><span data-ttu-id="ddcda-103">Exchange Online Protection 概觀</span><span class="sxs-lookup"><span data-stu-id="ddcda-103">Exchange Online Protection overview</span></span>

<span data-ttu-id="ddcda-p101">Microsoft Exchange Online Protection (EOP) 是雲端式的電子郵件篩選服務，它能協助組織抵禦垃圾郵件和惡意程式碼，同時也包括預防組織發生訊息原則違規的功能。EOP 能簡化訊息環境的管理，減輕維護內部部署硬體和軟體所衍生的繁重負擔。</span><span class="sxs-lookup"><span data-stu-id="ddcda-p101">Microsoft Exchange Online Protection (EOP) is a cloud-based email filtering service that helps protect your organization against spam and malware, and includes features to safeguard your organization from messaging-policy violations. EOP can simplify the management of your messaging environment and alleviate many of the burdens that come with maintaining on-premises hardware and software.</span></span>
  
<span data-ttu-id="ddcda-106">下列是您可以使用 EOP 來保護郵件的主要方法：</span><span class="sxs-lookup"><span data-stu-id="ddcda-106">The following are the primary ways you can use EOP for messaging protection:</span></span>
  
- <span data-ttu-id="ddcda-107">**在獨立案例中**EOP 提供雲端式電子郵件保護，為您的內部部署 Microsoft Exchange Server 2013 環境、 舊式 Exchange Server 版本，或任何其他內部部署 SMTP 電子郵件解決方案。</span><span class="sxs-lookup"><span data-stu-id="ddcda-107">**In a standalone scenario** EOP provides cloud-based email protection for your on-premises Microsoft Exchange Server 2013 environment, legacy Exchange Server versions, or for any other on-premises SMTP email solution.</span></span> 
    
- <span data-ttu-id="ddcda-108">**作為 Microsoft Exchange Online 的一部分** 根據預設，EOP 會保護 Microsoft Exchange Online 雲端託管信箱。</span><span class="sxs-lookup"><span data-stu-id="ddcda-108">**As a part of Microsoft Exchange Online** By default, EOP protects Microsoft Exchange Online cloud-hosted mailboxes.</span></span> 
    
- <span data-ttu-id="ddcda-109">**在混合部署中** EOP 可以設定為保護您的郵件環境，並在您混合使用內部部署及雲端信箱時控制郵件路由傳送。</span><span class="sxs-lookup"><span data-stu-id="ddcda-109">**In a hybrid deployment** EOP can be configured to protect your messaging environment and control mail routing when you have a mix of on-premises and cloud mailboxes.</span></span> 
    
## <a name="how-eop-works"></a><span data-ttu-id="ddcda-110">EOP 的運作方式</span><span class="sxs-lookup"><span data-stu-id="ddcda-110">How EOP works</span></span>

<span data-ttu-id="ddcda-111">若要了解 EOP 的運作方式，查看它如何處理傳入電子郵件很有幫助：</span><span class="sxs-lookup"><span data-stu-id="ddcda-111">To understand how EOP works, it helps to see how it processes incoming email:</span></span>
  
![EOP 電子郵件處理](../media/EOP-email-processing.png)
  
<span data-ttu-id="ddcda-p102">傳入郵件最初會通過連線篩選，可檢查寄件者信譽，並會檢查有惡意程式碼的郵件。大部分的垃圾郵件是在此時，並由 EOP 刪除。郵件會繼續透過原則篩選，針對您建立或強制執行從範本的自訂郵件流程規則 （也稱為傳輸規則） 來評估郵件。例如，您可以從特定寄件者的郵件送達時，傳送通知給管理員的規則。（資料遺失防護檢查也會發生這個時候，如果您有可用的功能; 如需功能可用性的相關資訊，請參閱[Exchange Online Protection 服務說明](https://go.microsoft.com/fwlink/p/?LinkId=320619)。）接下來，郵件通過內容篩選，其中的內容會檢查專門用語或內容常見垃圾郵件。郵件判定為垃圾郵件內容篩選可傳送至使用者的垃圾郵件資料夾或隔離區，在 [其他選項，請根據您的設定之間。郵件順利通過這些保護層級的所有之後，它會傳遞至收件者。</span><span class="sxs-lookup"><span data-stu-id="ddcda-p102">An incoming message initially passes through connection filtering, which checks the sender's reputation and inspects the message for malware. The majority of spam is stopped at this point and deleted by EOP. Messages continue through policy filtering, where messages are evaluated against custom mail flow rules (also known as transport rules) that you create or enforce from a template. For example, you can have a rule that sends a notification to a manager when mail arrives from a specific sender. (Data loss prevention checks also occur at this point, if you have that feature; for information about feature availability, see the [Exchange Online Protection Service Description](https://go.microsoft.com/fwlink/p/?LinkId=320619).) Next, messages pass through content filtering, where content is checked for terminology or properties common to spam. A message determined to be spam by the content filter can be sent to a user's Junk Email folder or to the quarantine, among other options, based on your settings. After a message passes all of these protection layers successfully, it's delivered to the recipient.</span></span>
  
### <a name="eop-datacenters"></a><span data-ttu-id="ddcda-120">EOP 資料中心</span><span class="sxs-lookup"><span data-stu-id="ddcda-120">EOP datacenters</span></span>

<span data-ttu-id="ddcda-p103">EOP 會在用於提供最佳可用性的全球資料中心網路上執行。例如，如果資料中心變成無法使用，則會將電子郵件自動路由傳送至其他資料中心，而不會中斷服務。每一個資料中心的伺服器都會代表您接受郵件，在您的組織與網際網路之間提供隔離層，進而減少伺服器上的負載。透過這個高可用性的網路，Microsoft 可以確保電子郵件及時送達您的組織。</span><span class="sxs-lookup"><span data-stu-id="ddcda-p103">EOP runs on a worldwide network of datacenters that are designed to provide the best availability. For example, if a datacenter becomes unavailable, email messages are automatically routed to another datacenter without any interruption in service. Servers in each datacenter accept messages on your behalf, providing a layer of separation between your organization and the Internet, thereby reducing load on your servers. Through this highly available network, Microsoft can ensure that email reaches your organization in a timely manner.</span></span> 
  
<span data-ttu-id="ddcda-p104">EOP 會在資料中心之間執行負載平衡，但只在一個區域內。如果您佈建在一個區域中，則會以該區域的郵件路由來處理您的所有郵件。下列清單顯示 EOP 資料中心的地區郵件路由運作方式：</span><span class="sxs-lookup"><span data-stu-id="ddcda-p104">EOP performs load balancing between datacenters but only within a region. If you're provisioned in one region all your messages will be processed using the mail routing for that region. The following list shows the how regional mail routing works for the EOP datacenters:</span></span>
  
    
- <span data-ttu-id="ddcda-128">在歐洲、中東和非洲 (EMEA)，所有 Exchange Online 信箱都位於 EMEA 資料中心，且所有郵件都透過 EMEA 資料中心傳送供 EOP 篩選。</span><span class="sxs-lookup"><span data-stu-id="ddcda-128">In Europe, the Middle East, and Africa (EMEA), all Exchange Online mailboxes are located in EMEA datacenters, and all messages are routed through EMEA datacenters for EOP filtering.</span></span>
    
- <span data-ttu-id="ddcda-129">在亞太地區 (APAC)，所有的 Exchange Online 信箱都位於 APAC 資料中心，但郵件會透過 APAC 資料中心，供 EOP 篩選目前路由傳送。</span><span class="sxs-lookup"><span data-stu-id="ddcda-129">In Asia-Pacific (APAC), all Exchange Online mailboxes are located in APAC datacenters, but messages are currently routed through APAC datacenters for EOP filtering.</span></span>

- <span data-ttu-id="ddcda-p105">美洲，所有 Exchange Online 信箱都位於美國資料中心，除了可用的巴西和智利資料中心的南美洲和加拿大可用的加拿大資料中心中。透過 EOP 篩選; 本機資料中心會路由傳送所有電子郵件，包括南美洲和加拿大客戶的郵件quaratined 電子郵件會儲存在租用戶所在的資料中心。</span><span class="sxs-lookup"><span data-stu-id="ddcda-p105">In the Americas, all Exchange Online mailboxes are located in U.S. datacenters, with the exception of South America where datacenters in Brazil and Chile are used and in Canada where datacenters in Canada are used. All email messages, including messages for customers in South America and Canada, are routed through local datacenters for EOP filtering; quaratined email is stored in the datacenter where the tenant is located.</span></span>
    
- <span data-ttu-id="ddcda-132">在歐洲、中東和非洲 (EMEA)，所有 Exchange Online 信箱都位於 EMEA 資料中心，且所有郵件都透過 EMEA 資料中心傳送供 EOP 篩選。</span><span class="sxs-lookup"><span data-stu-id="ddcda-132">In Europe, the Middle East, and Africa (EMEA), all Exchange Online mailboxes are located in EMEA datacenters, and all messages are routed through EMEA datacenters for EOP filtering.</span></span>
    
- <span data-ttu-id="ddcda-133">在亞太地區 (APAC)，所有的 Exchange Online 信箱都位於 APAC 資料中心，以及目前會透過 APAC 資料中心，供 EOP 篩選會路由傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="ddcda-133">In Asia-Pacific (APAC), all Exchange Online mailboxes are located in APAC datacenters, and messages are currently routed through APAC datacenters for EOP filtering.</span></span>
    
- <span data-ttu-id="ddcda-134">至於政府社群雲端 (GCC)，所有 Exchange Online 信箱都位於美國資料中心，且所有郵件都透過美國資料中心傳送供 EOP 篩選。</span><span class="sxs-lookup"><span data-stu-id="ddcda-134">For the Government Community Cloud (GCC), all Exchange Online mailboxes are located in U.S. datacenters and all messages are routed through U.S. datacenters for EOP filtering.</span></span>
    
## <a name="eop-plans-and-features"></a><span data-ttu-id="ddcda-135">EOP 方案和功能</span><span class="sxs-lookup"><span data-stu-id="ddcda-135">EOP plans and features</span></span>

<span data-ttu-id="ddcda-136">以下是可用的 EOP 訂閱方案：</span><span class="sxs-lookup"><span data-stu-id="ddcda-136">The following are the available EOP subscription plans:</span></span>
  
- <span data-ttu-id="ddcda-137">**EOP 獨立** EOP 會保護您的內部部署信箱。</span><span class="sxs-lookup"><span data-stu-id="ddcda-137">**EOP standalone** Where EOP protects your on-premises mailboxes.</span></span> 
    
- <span data-ttu-id="ddcda-138">**Exchange Online 中的 EOP 功能** EOP 會保護您的 Exchange Online 雲端託管信箱。</span><span class="sxs-lookup"><span data-stu-id="ddcda-138">**EOP features in Exchange Online** Where EOP protects your Exchange Online cloud-hosted mailboxes.</span></span> 
    
- <span data-ttu-id="ddcda-139">**Exchange Enterprise CAL with Services** EOP 會保護您的內部部署信箱 (如 EOP 獨立版)，並包含資料外洩防護 (DLP) 和使用 Web 服務的報告。</span><span class="sxs-lookup"><span data-stu-id="ddcda-139">**Exchange Enterprise CAL with Services** Where EOP protects your on-premises mailboxes, like EOP standalone, and includes data loss prevention (DLP) and reporting using web services.</span></span> 
    
<span data-ttu-id="ddcda-140">如需所有 EOP 訂閱方案之需求、重要限制和功能可用性的相關資訊，請參閱 [Exchange Online Protection 服務描述](https://go.microsoft.com/fwlink/p/?LinkId=320619)。</span><span class="sxs-lookup"><span data-stu-id="ddcda-140">For information about requirements, important limits, and feature availability across all EOP subscription plans, see the [Exchange Online Protection Service Description](https://go.microsoft.com/fwlink/p/?LinkId=320619).</span></span>
  
## <a name="setting-up-eop"></a><span data-ttu-id="ddcda-141">設定 EOP</span><span class="sxs-lookup"><span data-stu-id="ddcda-141">Setting up EOP</span></span>

<span data-ttu-id="ddcda-p106">設定 EOP 可以很簡單，對於具有一些符合性規則的小型組織來說，更是如此。不過，如果您的組織是具有多個網域、自訂符合性規則或混合郵件流程的大型組織，則在進行設定時可能需要更加詳盡的規劃及更多的時間。</span><span class="sxs-lookup"><span data-stu-id="ddcda-p106">Setting up EOP can be simple, especially in the case of a small organization with a handful of compliance rules. However, if you have a large organization with multiple domains, custom compliance rules, or hybrid mail flow, set up can take more planning and time.</span></span>
  
<span data-ttu-id="ddcda-144">如果已購買 EOP，請參閱[設定 EOP 服務](set-up-your-eop-service.md)，以確保完成所有必要的 EOP 設定步驟，來保護郵件環境。</span><span class="sxs-lookup"><span data-stu-id="ddcda-144">If you've already purchased EOP, see [Set up your EOP service](set-up-your-eop-service.md) to ensure that you complete all the steps necessary to configure EOP to protect your messaging environment.</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="ddcda-145">相關資訊</span><span class="sxs-lookup"><span data-stu-id="ddcda-145">For more information</span></span>

[<span data-ttu-id="ddcda-146">EOP 功能</span><span class="sxs-lookup"><span data-stu-id="ddcda-146">EOP features</span></span>](eop-features.md)
  
[<span data-ttu-id="ddcda-147">EOP 快速入門影片</span><span class="sxs-lookup"><span data-stu-id="ddcda-147">Videos for getting started with EOP</span></span>](videos-for-getting-started-with-eop.md)
  
[<span data-ttu-id="ddcda-148">EOP 一般常見問題集</span><span class="sxs-lookup"><span data-stu-id="ddcda-148">EOP general FAQ</span></span>](eop-general-faq.md)
  
[<span data-ttu-id="ddcda-149">EOP 排入佇列、延後和退回的訊息常見問題集</span><span class="sxs-lookup"><span data-stu-id="ddcda-149">EOP queued, deferred, and bounced messages FAQ</span></span>](eop-queued-deferred-and-bounced-messages-faq.md)
  
[<span data-ttu-id="ddcda-150">委派管理常見問題集</span><span class="sxs-lookup"><span data-stu-id="ddcda-150">Delegated administration FAQ</span></span>](delegated-administration-faq.md)
  
[<span data-ttu-id="ddcda-151">將網域及設定從某個 EOP 組織移到另一個 EOP 組織</span><span class="sxs-lookup"><span data-stu-id="ddcda-151">Move domains and settings from one EOP organization to another EOP organization</span></span>](move-domains-and-settings-from-one-eop-organization-to-another-eop-organization.md)
  

