---
title: 未註冊的網域的電子郵件
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 10/17/2018
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: 如果您傳送大量的未註冊的網域的電子郵件，則會執行您取得封鎖的電子郵件的風險。 閱讀本篇文章以了解更多。
ms.openlocfilehash: 21c403c8072902565f63048782b06c531cdbceb0
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32263985"
---
# <a name="unregistered-domain-email-what-you-need-to-know"></a><span data-ttu-id="d1379-104">未註冊的網域電子郵件： 您要知道什麼</span><span class="sxs-lookup"><span data-stu-id="d1379-104">Unregistered Domain Email: What you need to know</span></span>

<span data-ttu-id="d1379-105">Office 365 允許轉送某些郵件透過 Exchange Online Protection (EOP) 的租用戶。</span><span class="sxs-lookup"><span data-stu-id="d1379-105">Office 365 allows for tenants to relay some messages through Exchange Online Protection (EOP).</span></span> <span data-ttu-id="d1379-106">當使用者擁有 Office 365 信箱和外部的人員傳送他們電子郵件，但使其回到使用者的外部信箱設定電子郵件轉寄功能，就是一個支援的範例。</span><span class="sxs-lookup"><span data-stu-id="d1379-106">One supported example of this would be when users have an Office 365 mailbox and someone external sends them email but email forwarding is configured so that it goes back out to the user's external mailbox.</span></span> <span data-ttu-id="d1379-107">這是最常見的學生，想要利用其個人電子郵件介面，但仍取得電子郵件與學校相關的教育版環境中。</span><span class="sxs-lookup"><span data-stu-id="d1379-107">This is most common in education environments where students want to leverage their personal email interface but still get emails related to school.</span></span> <span data-ttu-id="d1379-108">另一個例子是客戶在混合式案例，並有傳送超出 EOP 的電子郵件的內部部署伺服器時。</span><span class="sxs-lookup"><span data-stu-id="d1379-108">Another example is when customers are in a hybrid scenario and have on-premises servers that send email out of EOP.</span></span>

## <a name="problems-with-unregistered-domains"></a><span data-ttu-id="d1379-109">問題未註冊的網域</span><span class="sxs-lookup"><span data-stu-id="d1379-109">Problems with unregistered domains</span></span>

<span data-ttu-id="d1379-110">問題時，內部部署伺服器取得危害和最終轉送大量超出 EOP 垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="d1379-110">The problem is when on-premises servers get compromised and end up relaying a large volume of spam out of EOP.</span></span> <span data-ttu-id="d1379-111">在大多數情況下，右連接器已設定，但未註冊，也就是取消提供這項，網域從要傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="d1379-111">In almost all cases, the right connectors are set up but email is being sent from unregistered, also known as unprovisioned, domains.</span></span> <span data-ttu-id="d1379-112">Office 365，並讓合理的郵件來自未註冊的網域，但應在您計劃傳送出的每個網域的系統管理中心中設定公認的網域。</span><span class="sxs-lookup"><span data-stu-id="d1379-112">Office 365 does allow a reasonable amount of mail to come from unregistered domains, but an Accepted Domain should be configured in the Admin Center for each domain you plan on sending out of.</span></span>

<span data-ttu-id="d1379-113">一旦危害，租用戶就禁止傳送未註冊的網域的輸出郵件。</span><span class="sxs-lookup"><span data-stu-id="d1379-113">Once compromised, tenants will be prevented from sending outbound mail for unregistered domains.</span></span> <span data-ttu-id="d1379-114">使用者會收到未傳遞回報 (NDR) 表示：</span><span class="sxs-lookup"><span data-stu-id="d1379-114">Users will receive a Non-Delivery Report (NDR) that states:</span></span>

- <span data-ttu-id="d1379-115">550 5.7.750 服務無法使用。</span><span class="sxs-lookup"><span data-stu-id="d1379-115">550 5.7.750 Service unavailable.</span></span> <span data-ttu-id="d1379-116">封鎖來自未註冊的網域傳送的用戶端</span><span class="sxs-lookup"><span data-stu-id="d1379-116">Client blocked from sending from unregistered domains</span></span>

## <a name="unblocking-tenant-in-order-to-send-again"></a><span data-ttu-id="d1379-117">若要重新傳送解除封鎖租用戶</span><span class="sxs-lookup"><span data-stu-id="d1379-117">Unblocking tenant in order to send again</span></span>

<span data-ttu-id="d1379-118">有您不必執行如果您要取得封鎖來自未註冊的網域傳送的一些事項：</span><span class="sxs-lookup"><span data-stu-id="d1379-118">There are several things you need to do if you get blocked for sending from unregistered domains:</span></span>

1. <span data-ttu-id="d1379-119">請確定您網域的所有註冊 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="d1379-119">Make sure that you register all of your domains in Microsoft 365 admin center.</span></span> <span data-ttu-id="d1379-120">詳細資訊，請參閱[以下](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。</span><span class="sxs-lookup"><span data-stu-id="d1379-120">More information can be found [here](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

2. <span data-ttu-id="d1379-121">尋找不尋常的連接器。</span><span class="sxs-lookup"><span data-stu-id="d1379-121">Look for unusual connectors.</span></span> <span data-ttu-id="d1379-122">惡意動作項目通常會傳送垃圾郵件您 Office 365 租用戶中建立新的輸入的連接器。</span><span class="sxs-lookup"><span data-stu-id="d1379-122">Malicious actors will often create new inbound connectors in your Office 365 tenant to send spam.</span></span> <span data-ttu-id="d1379-123">檢查您的連接器的詳細資訊可以找到[以下](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="d1379-123">More information on checking your connectors can be found [here](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps).</span></span> 

3. <span data-ttu-id="d1379-124">鎖定您的內部部署伺服器，並確定他們沒有遭到盜用。</span><span class="sxs-lookup"><span data-stu-id="d1379-124">Lock down your on-premises servers and ensure that they are not compromised.</span></span>

> [!TIP]
> <span data-ttu-id="d1379-125">有許多因素所涉及在這裡，尤其是協力廠商的伺服器。</span><span class="sxs-lookup"><span data-stu-id="d1379-125">There are many factors involved here, especially if these are third-party servers.</span></span> <span data-ttu-id="d1379-126">無論如何，您將需要能夠確認是合法的所有郵件離開您的伺服器。</span><span class="sxs-lookup"><span data-stu-id="d1379-126">Regardless, you will need to be able confirm that  all mail leaving your servers are legitimate.</span></span>

4. <span data-ttu-id="d1379-127">完成時，您必須連絡 Microsoft 支援服務，並要求以取得您的租用戶解除封鎖再次傳送來自未註冊的網域。</span><span class="sxs-lookup"><span data-stu-id="d1379-127">Once done, you will need to call Microsoft Support and ask to get your tenant unblocked to send from unregistered domains again.</span></span>  <span data-ttu-id="d1379-128">提供錯誤碼很有幫助，但您想要證明您的環境受到保護，且不會在一次傳送垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="d1379-128">Providing the error code is helpful, but you will need to prove that your environment is secured and that spam will not be sent again.</span></span> <span data-ttu-id="d1379-129">在開啟支援案例的詳細資訊可以找到[以下](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online)。</span><span class="sxs-lookup"><span data-stu-id="d1379-129">More information on opening a support case can be found [here](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online).</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="d1379-130">相關資訊</span><span class="sxs-lookup"><span data-stu-id="d1379-130">For more information</span></span>

[<span data-ttu-id="d1379-131">Office 365 電子郵件的反垃圾郵件保護</span><span class="sxs-lookup"><span data-stu-id="d1379-131">Office 365 email anti-spam protection</span></span>](anti-spam-protection.md)

[<span data-ttu-id="d1379-132">Office 365 中的電子郵件未傳遞回報</span><span class="sxs-lookup"><span data-stu-id="d1379-132">Email non-delivery reports in Office 365</span></span>](https://support.office.com/article/email-non-delivery-reports-in-office-365-51daa6b9-2e35-49c4-a0c9-df85bf8533c3)

[<span data-ttu-id="d1379-133">設定信箱的電子郵件轉寄功能</span><span class="sxs-lookup"><span data-stu-id="d1379-133">Configure email forwarding for a mailbox</span></span>](https://docs.microsoft.com/en-us/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[<span data-ttu-id="d1379-134">如何將多功能裝置或應用程式設定為使用 Office 365 傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="d1379-134">How to set up a multifunction device or application to send email using Office 365</span></span>](https://support.office.com/en-us/article/How-to-set-up-a-multifunction-device-or-application-to-send-email-using-Office-365-69f58e99-c550-4274-ad18-c805d654b4c4)

<span data-ttu-id="d1379-135">[管理公認的網域在 Exchange Online](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。</span><span class="sxs-lookup"><span data-stu-id="d1379-135">[Manage accepted domains in Exchange Online](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>
