---
title: 外寄郵件的高風險傳遞集區
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/24/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
description: 如果客戶的電子郵件系統已遭洩露惡意程式碼或惡意的垃圾郵件攻擊，它會傳送到裝載的篩選服務的輸出垃圾郵件，這可能會導致所列在協力廠商封鎖的 Office 365 資料中心伺服器的 IP 位址列出。
ms.openlocfilehash: 856db53b105379ea3e606e39bf3c2612afa803c3
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026620"
---
# <a name="high-risk-delivery-pool-for-outbound-messages"></a><span data-ttu-id="60f4b-103">外寄郵件的高風險傳遞集區</span><span class="sxs-lookup"><span data-stu-id="60f4b-103">High-risk delivery pool for outbound messages</span></span>

<span data-ttu-id="60f4b-p101">如果客戶的電子郵件系統已遭洩露惡意程式碼或惡意的垃圾郵件攻擊，它會傳送到裝載的篩選服務的輸出垃圾郵件，這可能會導致所列在協力廠商封鎖的 Office 365 資料中心伺服器的 IP 位址列出。執行動作的目的地伺服器未使用託管的篩選服務，但不要使用這些封鎖清單、 拒絕所有從任何已新增至這些清單的主控篩選 IP 位址傳送電子郵件。若要避免此問題，超出垃圾郵件臨界值的所有外寄郵件傳送到高風險傳遞集區。此第二的外寄電子郵件集區僅用於傳送可能的低品質的郵件。這有助於保護網路的其餘部分傳送較可能導致遭封鎖的傳送端 IP 位址的郵件。</span><span class="sxs-lookup"><span data-stu-id="60f4b-p101">When a customer's email system has been compromised by malware or a malicious spam attack, and it's sending outbound spam through the hosted filtering service, this can result in the IP addresses of the Office 365 data center servers being listed on third-party block lists. Destination servers that do not use the hosted filtering service, but do use these block lists, reject all email sent from any of the hosted filtering IP addresses that have been added to those lists. To prevent this, all outbound messages that exceed the spam threshold are sent through a high-risk delivery pool. This secondary outbound email pool is only used to send messages that may be of low quality. This helps to protect the rest of the network from sending messages that are more likely to result in the sending IP address being blocked.</span></span>
  
<span data-ttu-id="60f4b-p102">專用高風險傳遞集區的使用有助於確保標準輸出的集區只會將傳送至高品質的是已知的郵件。使用此次要 IP 集區有助於減少要新增至封鎖清單的一般輸出 IP 集區的機率。要放置在封鎖清單中的高風險傳遞集區的可能性會維持風險。這是根據設計。</span><span class="sxs-lookup"><span data-stu-id="60f4b-p102">The use of a dedicated high-risk delivery pool helps ensure that the normal outbound pool is only sending messages that are known to be of a high-quality. Using this secondary IP pool helps to reduce the probability of the normal outbound-IP pool being added to a blocked list. The possibility of the high-risk delivery pool being placed on a blocked list remains a risk. This is by design.</span></span>
  
<span data-ttu-id="60f4b-113">郵件的傳送端網域其中有無提供您網域的 IP 位址的地址記錄 （記錄） 並無 MX 記錄，這樣有助於應該會收到 DNS 中特定網域的郵件伺服器直接郵件，永遠都透過不論其垃圾郵件處理高風險傳遞集區。</span><span class="sxs-lookup"><span data-stu-id="60f4b-113">Messages where the sending domain has no address record (A record), which gives you the IP address of the domain, and no MX record, which helps direct mail to the servers that should receive the mail for a particular domain in the DNS, are always routed through the high-risk delivery pool regardless of their spam disposition.</span></span>
  
## <a name="understanding-delivery-status-notification-dsn-messages"></a><span data-ttu-id="60f4b-114">了解傳遞狀態通知 (DSN) 郵件</span><span class="sxs-lookup"><span data-stu-id="60f4b-114">Understanding Delivery Status Notification (DSN) messages</span></span>

<span data-ttu-id="60f4b-115">輸出高風險傳遞集區可管理所有 「 被退回 」 或 「 失敗 」 (DSN) 郵件的傳遞。</span><span class="sxs-lookup"><span data-stu-id="60f4b-115">The outbound high-risk delivery pool manages the delivery for all "bounced" or "failed" (DSN) messages.</span></span>
  
<span data-ttu-id="60f4b-116">DSN 郵件激增的可能原因包括下列：</span><span class="sxs-lookup"><span data-stu-id="60f4b-116">Possible causes for a surge in DSN messages include the following:</span></span>
  
- <span data-ttu-id="60f4b-117">詐騙活動影響到使用服務的其中一位客戶</span><span class="sxs-lookup"><span data-stu-id="60f4b-117">A spoofing campaign affecting one of the customers using the service</span></span>
    
- <span data-ttu-id="60f4b-118">目錄搜集攻擊</span><span class="sxs-lookup"><span data-stu-id="60f4b-118">A directory harvest attack</span></span>
    
- <span data-ttu-id="60f4b-119">垃圾郵件攻擊</span><span class="sxs-lookup"><span data-stu-id="60f4b-119">A spam attack</span></span>
    
- <span data-ttu-id="60f4b-120">惡意 SMTP 伺服器</span><span class="sxs-lookup"><span data-stu-id="60f4b-120">A rogue SMTP server</span></span>
    
<span data-ttu-id="60f4b-p103">所有的這些問題可能會導致突然增加的服務正在處理的 DSN 訊息數。次數，這些 DSN 郵件顯示為以其他電子郵件伺服器和服務的垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="60f4b-p103">All of these issues can result in a sudden increase in the number of DSN messages being processed by the service. Many times, these DSN messages appear to be spam to other email servers and services.</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="60f4b-123">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="60f4b-123">For more information</span></span>

[<span data-ttu-id="60f4b-124">設定輸出垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="60f4b-124">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="60f4b-125">反垃圾郵件保護常見問題集</span><span class="sxs-lookup"><span data-stu-id="60f4b-125">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
  

