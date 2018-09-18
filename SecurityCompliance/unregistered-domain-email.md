---
title: 取消登錄的網域電子郵件
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 09/17/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
description: 如果傳送大量取消登錄的網域電子郵件，則會執行快速封鎖電子郵件的風險。請閱讀本篇文章以深入了解。
ms.openlocfilehash: f2b60f492197bf0dadb702a1c3f184c2d7e56bf1
ms.sourcegitcommit: 7b85c22fc85ec19e4b44a07e91bfa9ade768185a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2018
ms.locfileid: "23998597"
---
# <a name="unregistered-domain-email-what-you-need-to-know"></a><span data-ttu-id="97261-104">取消登錄的網域電子郵件： 您需要知道什麼</span><span class="sxs-lookup"><span data-stu-id="97261-104">Unregistered Domain Email: What you need to know</span></span>

<span data-ttu-id="97261-p102">Office 365 允許以轉送某些郵件透過 Exchange Online Protection (EOP) 的租用戶。當使用者擁有的 Office 365 信箱與外部有人傳送電子郵件給其但電子郵件轉寄設定使其回到使用者的外部信箱，就是一個受支援的範例。這是最常見其中學生要利用其個人電子郵件介面但仍屬學校相關的電子郵件的教育環境中。另一個例子是當客戶混合式案例，且已傳送電子郵件移出 EOP 的內部伺服器。</span><span class="sxs-lookup"><span data-stu-id="97261-p102">Office 365 allows for tenants to relay some messages through Exchange Online Protection (EOP). One supported example of this would be when users have an Office 365 mailbox and someone external sends them email but email forwarding is configured so that it goes back out to the user's external mailbox. This is most common in education environments where students want to leverage their personal email interface but still get emails related to school. Another example is when customers are in a hybrid scenario and have on-premise servers that send email out of EOP.</span></span>

## <a name="problems-with-unregistered-domains"></a><span data-ttu-id="97261-109">取消登錄的網域的問題</span><span class="sxs-lookup"><span data-stu-id="97261-109">Problems with unregistered domains</span></span>

<span data-ttu-id="97261-p103">內部部署伺服器取得危害和最後轉送大量的不在 EOP 的垃圾郵件時的問題。在幾乎所有的情況下，右連接器已設定但從取消登錄、 也稱為取消提供這項、 網域傳送電子郵件。Office 365 沒有可合理的郵件來自取消登錄的網域]，但應在您計劃傳送出的每個網域系統管理中心設定公認的網域。</span><span class="sxs-lookup"><span data-stu-id="97261-p103">The problem is when on-premise servers get compromised and end up relaying a large volume of spam out of EOP. In almost all cases, the right connectors are set up but email is being sent from unregistered, also known as unprovisioned, domains. Office 365 does allow a reasonable amount of mail to come from unregistered domains, but an Accepted Domain should be configured in the Admin Center for each domain you plan on sending out of.</span></span>

<span data-ttu-id="97261-p104">一旦危害，承租人會禁止傳送輸出郵件取消登錄的網域。使用者會收到未傳遞報告 (NDR) 表示：</span><span class="sxs-lookup"><span data-stu-id="97261-p104">Once compromised, tenants will be prevented from sending outbound mail for unregistered domains. Users will receive a Non-Delivery Report (NDR) that states:</span></span>

- <span data-ttu-id="97261-p105">550 5.7.750 服務無法使用。傳送取消登錄的網域從封鎖的用戶端</span><span class="sxs-lookup"><span data-stu-id="97261-p105">550 5.7.750 Service unavailable. Client blocked from sending from unregistered domains</span></span>

## <a name="unblocking-tenant-in-order-to-send-again"></a><span data-ttu-id="97261-117">若要一次傳送解除封鎖租用戶</span><span class="sxs-lookup"><span data-stu-id="97261-117">Unblocking tenant in order to send again</span></span>

<span data-ttu-id="97261-118">有您需要執行如果您要取得封鎖來自取消登錄的網域傳送的一些事項：</span><span class="sxs-lookup"><span data-stu-id="97261-118">There are several things you need to do if you get blocked for sending from unregistered domains:</span></span>

1. <span data-ttu-id="97261-p106">請確定所有的網域註冊 Office 365 系統管理中心中。您可以找到更多的資訊[如下](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。</span><span class="sxs-lookup"><span data-stu-id="97261-p106">Make sure that you register all of your domains in Office 365 admin center. More information can be found [here](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

2. <span data-ttu-id="97261-p107">鎖定您的內部伺服器和確認他們不遭到入侵。有許多因素相關這裡，特別是如果這些是協力廠商伺服器，但您必須要能夠確定所有郵件離開該伺服器都是合法。</span><span class="sxs-lookup"><span data-stu-id="97261-p107">Lock down your on-premise servers and ensure that they are not compromised. There are many factors involved here, especially if these are third-party servers, but you will need to be able to make sure all mail leaving that server is legitimate.</span></span>

<span data-ttu-id="97261-p108">一旦完成，您必須連絡 Microsoft 支援並要求要取得您一次傳送來自取消登錄的網域解除封鎖的租用戶。 提供錯誤碼相當有用，但是您將需要證明您的環境安全且不會在一次傳送垃圾郵件。您可以找到更多的資訊[如下](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online)。</span><span class="sxs-lookup"><span data-stu-id="97261-p108">Once done, you will need to call Microsoft Support and ask to get your tenant unblocked to send from unregistered domains again.  Providing the error code is helpful, but you will need to prove that your environment is secured and that spam will not be sent again. More information can be found [here](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online).</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="97261-126">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="97261-126">For more information</span></span>

[<span data-ttu-id="97261-127">Office 365 電子郵件的反垃圾郵件保護</span><span class="sxs-lookup"><span data-stu-id="97261-127">Office 365 email anti-spam protection</span></span>](anti-spam-protection.md)

[<span data-ttu-id="97261-128">Office 365 中的電子郵件未傳遞回報</span><span class="sxs-lookup"><span data-stu-id="97261-128">Email non-delivery reports in Office 365</span></span>](https://support.office.com/article/email-non-delivery-reports-in-office-365-51daa6b9-2e35-49c4-a0c9-df85bf8533c3)

[<span data-ttu-id="97261-129">設定信箱的郵件轉寄</span><span class="sxs-lookup"><span data-stu-id="97261-129">Configure email forwarding for a mailbox</span></span>](https://docs.microsoft.com/en-us/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[<span data-ttu-id="97261-130">如何將多功能裝置或應用程式設定為使用 Office 365 傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="97261-130">How to set up a multifunction device or application to send email using Office 365</span></span>](https://support.office.com/en-us/article/How-to-set-up-a-multifunction-device-or-application-to-send-email-using-Office-365-69f58e99-c550-4274-ad18-c805d654b4c4)

<span data-ttu-id="97261-131">[管理公認的網域在 Exchange Online](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。</span><span class="sxs-lookup"><span data-stu-id="97261-131">[Manage accepted domains in Exchange Online](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>