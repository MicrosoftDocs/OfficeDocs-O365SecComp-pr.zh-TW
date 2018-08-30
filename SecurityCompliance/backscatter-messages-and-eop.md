---
title: 非法回應郵件與 EOP
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
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
description: 非法回應郵件已傳送的郵件伺服器，通常是因為傳入的垃圾郵件的自動化的彈跳訊息。Backscatterer DNSBL 是非法回應郵件傳送的 IP 位址清單。不是垃圾郵件] 清單中，然後我們不嘗試從 Backscatterer DNSBL 移除伺服器。
ms.openlocfilehash: 2ab5c6a3bec347446452acd3bdfd8c5d309994a9
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002678"
---
# <a name="backscatter-messages-and-eop"></a><span data-ttu-id="ce654-105">非法回應郵件與 EOP</span><span class="sxs-lookup"><span data-stu-id="ce654-105">Backscatter messages and EOP</span></span>

<span data-ttu-id="ce654-p102">非法回應郵件已傳送的郵件伺服器，通常是因為傳入的垃圾郵件的自動化的彈跳訊息。Exchange Online Protection (EOP) 為垃圾郵件篩選服務，因為電子郵件傳送給不存在的收件者和其他可疑的目的地會拒絕我們的服務。在這種情況下，EOP 會產生未傳遞回報 (NDR) 訊息並將其傳遞"者 」。因為垃圾郵件寄件經常使用偽造或無效 」 的 「 地址中其訊息，可能會造成非法回應郵件要傳送 NDR 的寄件者地址。在這種情況下，與 EOP 網路相關聯的外寄伺服器可能會列在 Backscatterer DNS 封鎖清單 (DNSBL)。Backscatterer DNSBL 是非法回應郵件傳送的 IP 位址清單。不是垃圾郵件] 清單中，然後我們不嘗試從 Backscatterer DNSBL 移除伺服器。</span><span class="sxs-lookup"><span data-stu-id="ce654-p102">Backscatter messages are the automated bounce messages that are sent by mail servers, typically as a result of incoming spam. Because Exchange Online Protection (EOP) is a spam filtering service, email messages sent to nonexistent recipients and to other suspicious destinations are rejected by our service. When this happens, EOP generates a non-delivery report (NDR) message and delivers it back to the "sender." Because spammers frequently use a forged or invalid "From" address in their messages, the sender address to which the NDR is sent may result in a backscatter message. When this happens, outgoing servers that are associated with the EOP network may be listed on the Backscatterer DNS Block List (DNSBL). The Backscatterer DNSBL is a list of IP addresses that send backscatter messages. It isn't a spammer list, and we don't try to remove our servers from the Backscatterer DNSBL.</span></span> 
  
> [!TIP]
> <span data-ttu-id="ce654-p103">根據 Backscatterer 網站的指示，該服務的設定或用法不建議對所有傳入的郵件使用拒絕模式。而是應該在安全模式中使用。如需實作正確非法回應設定的相關資訊，請造訪 [Backscatterer.org 網站](http://www.backscatterer.org/?target=usage)。</span><span class="sxs-lookup"><span data-stu-id="ce654-p103">According to the instructions on the Backscatterer website, the use of reject mode for all incoming mail isn't a recommended configuration or use of that service. It should be used in safe mode instead. For more information about implementing the correct backscatter configuration, visit the [Backscatterer.org website](http://www.backscatterer.org/?target=usage).</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="ce654-116">相關資訊</span><span class="sxs-lookup"><span data-stu-id="ce654-116">For more information</span></span>

[<span data-ttu-id="ce654-117">Backscatterer.org IP 清單</span><span class="sxs-lookup"><span data-stu-id="ce654-117">The Backscatterer.org IP list</span></span>](https://blogs.msdn.com/b/tzink/archive/2012/08/22/the-backscatterer-org-ip-list.aspx)
  
<span data-ttu-id="ce654-118">請參閱 ＜[進階垃圾郵件篩選選項](advanced-spam-filtering-asf-options.md)的"NDR 非法回應 」 項目</span><span class="sxs-lookup"><span data-stu-id="ce654-118">See the "NDR backscatter" entry in [Advanced spam filtering  options](advanced-spam-filtering-asf-options.md)</span></span>
  

