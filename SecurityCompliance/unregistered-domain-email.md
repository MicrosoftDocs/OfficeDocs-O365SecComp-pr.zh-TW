---
title: 取消登錄的網域電子郵件
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/17/2018
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
description: 如果傳送大量取消登錄的網域電子郵件，則會執行快速封鎖電子郵件的風險。請閱讀本篇文章以深入了解。
ms.openlocfilehash: bef39780438a6d9669354bddaed391b2364badf8
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220773"
---
# <a name="unregistered-domain-email-what-you-need-to-know"></a><span data-ttu-id="ed947-104">取消登錄的網域電子郵件： 您需要知道什麼</span><span class="sxs-lookup"><span data-stu-id="ed947-104">Unregistered Domain Email: What you need to know</span></span>

<span data-ttu-id="ed947-p102">Office 365 允許以轉送某些郵件透過 Exchange Online Protection (EOP) 的租用戶。當使用者擁有的 Office 365 信箱與外部有人傳送電子郵件給其但電子郵件轉寄設定使其回到使用者的外部信箱，就是一個受支援的範例。這是最常見其中學生要利用其個人電子郵件介面但仍屬學校相關的電子郵件的教育環境中。另一個例子是當客戶混合式案例，且已傳送電子郵件移出 EOP 的內部伺服器。</span><span class="sxs-lookup"><span data-stu-id="ed947-p102">Office 365 allows for tenants to relay some messages through Exchange Online Protection (EOP). One supported example of this would be when users have an Office 365 mailbox and someone external sends them email but email forwarding is configured so that it goes back out to the user's external mailbox. This is most common in education environments where students want to leverage their personal email interface but still get emails related to school. Another example is when customers are in a hybrid scenario and have on-premises servers that send email out of EOP.</span></span>

## <a name="problems-with-unregistered-domains"></a><span data-ttu-id="ed947-109">取消登錄的網域的問題</span><span class="sxs-lookup"><span data-stu-id="ed947-109">Problems with unregistered domains</span></span>

<span data-ttu-id="ed947-p103">內部部署伺服器取得危害和最後轉送大量的垃圾郵件移出 EOP 時問題。在幾乎所有的情況下，右連接器已設定但從取消登錄、 也稱為取消提供這項、 網域傳送電子郵件。Office 365 沒有可合理的郵件來自取消登錄的網域]，但應在您計劃傳送出的每個網域系統管理中心設定公認的網域。</span><span class="sxs-lookup"><span data-stu-id="ed947-p103">The problem is when on-premises servers get compromised and end up relaying a large volume of spam out of EOP. In almost all cases, the right connectors are set up but email is being sent from unregistered, also known as unprovisioned, domains. Office 365 does allow a reasonable amount of mail to come from unregistered domains, but an Accepted Domain should be configured in the Admin Center for each domain you plan on sending out of.</span></span>

<span data-ttu-id="ed947-p104">一旦危害，承租人會禁止傳送輸出郵件取消登錄的網域。使用者會收到未傳遞報告 (NDR) 表示：</span><span class="sxs-lookup"><span data-stu-id="ed947-p104">Once compromised, tenants will be prevented from sending outbound mail for unregistered domains. Users will receive a Non-Delivery Report (NDR) that states:</span></span>

- <span data-ttu-id="ed947-p105">550 5.7.750 服務無法使用。傳送取消登錄的網域從封鎖的用戶端</span><span class="sxs-lookup"><span data-stu-id="ed947-p105">550 5.7.750 Service unavailable. Client blocked from sending from unregistered domains</span></span>

## <a name="unblocking-tenant-in-order-to-send-again"></a><span data-ttu-id="ed947-117">若要一次傳送解除封鎖租用戶</span><span class="sxs-lookup"><span data-stu-id="ed947-117">Unblocking tenant in order to send again</span></span>

<span data-ttu-id="ed947-118">有您需要執行如果您要取得封鎖來自取消登錄的網域傳送的一些事項：</span><span class="sxs-lookup"><span data-stu-id="ed947-118">There are several things you need to do if you get blocked for sending from unregistered domains:</span></span>

1. <span data-ttu-id="ed947-p106">請確定所有的網域註冊 Office 365 系統管理中心中。您可以找到更多的資訊[如下](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。</span><span class="sxs-lookup"><span data-stu-id="ed947-p106">Make sure that you register all of your domains in Office 365 admin center. More information can be found [here](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

2. <span data-ttu-id="ed947-p107">尋找不尋常的連接器。惡意執行者通常會在您的 Office 365 租用戶傳送垃圾郵件中建立新的輸入的連接器。在檢查您的連接器的詳細資訊可以找到[以下](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="ed947-p107">Look for unusual connectors. Malicious actors will often create new inbound connectors in your Office 365 tenant to send spam. More information on checking your connectors can be found [here](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps).</span></span> 

3. <span data-ttu-id="ed947-124">鎖定的內部伺服器和確認他們不遭到入侵。</span><span class="sxs-lookup"><span data-stu-id="ed947-124">Lock down your on-premises servers and ensure that they are not compromised.</span></span>

> [!TIP]
> <span data-ttu-id="ed947-p108">有許多因素相關這裡，特別是如果這些是協力廠商伺服器。無論如何，您將需要能夠確認離開伺服器的所有郵件都是否合法。</span><span class="sxs-lookup"><span data-stu-id="ed947-p108">There are many factors involved here, especially if these are third-party servers. Regardless, you will need to be able confirm that  all mail leaving your servers are legitimate.</span></span>

4. <span data-ttu-id="ed947-p109">一旦完成，您必須連絡 Microsoft 支援並要求要取得您一次傳送來自取消登錄的網域解除封鎖的租用戶。 提供錯誤碼相當有用，但是您將需要證明您的環境安全且不會在一次傳送垃圾郵件。開啟支援案例的詳細資訊可以找到[以下](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online)。</span><span class="sxs-lookup"><span data-stu-id="ed947-p109">Once done, you will need to call Microsoft Support and ask to get your tenant unblocked to send from unregistered domains again.  Providing the error code is helpful, but you will need to prove that your environment is secured and that spam will not be sent again. More information on opening a support case can be found [here](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online).</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="ed947-130">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="ed947-130">For more information</span></span>

[<span data-ttu-id="ed947-131">Office 365 電子郵件的反垃圾郵件保護</span><span class="sxs-lookup"><span data-stu-id="ed947-131">Office 365 email anti-spam protection</span></span>](anti-spam-protection.md)

[<span data-ttu-id="ed947-132">Office 365 中的電子郵件未傳遞回報</span><span class="sxs-lookup"><span data-stu-id="ed947-132">Email non-delivery reports in Office 365</span></span>](https://support.office.com/article/email-non-delivery-reports-in-office-365-51daa6b9-2e35-49c4-a0c9-df85bf8533c3)

[<span data-ttu-id="ed947-133">設定信箱的電子郵件轉寄功能</span><span class="sxs-lookup"><span data-stu-id="ed947-133">Configure email forwarding for a mailbox</span></span>](https://docs.microsoft.com/en-us/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[<span data-ttu-id="ed947-134">如何將多功能裝置或應用程式設定為使用 Office 365 傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="ed947-134">How to set up a multifunction device or application to send email using Office 365</span></span>](https://support.office.com/en-us/article/How-to-set-up-a-multifunction-device-or-application-to-send-email-using-Office-365-69f58e99-c550-4274-ad18-c805d654b4c4)

<span data-ttu-id="ed947-135">[管理公認的網域在 Exchange Online](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。</span><span class="sxs-lookup"><span data-stu-id="ed947-135">[Manage accepted domains in Exchange Online](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>
