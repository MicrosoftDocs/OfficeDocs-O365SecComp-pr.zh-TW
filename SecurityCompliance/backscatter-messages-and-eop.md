---
title: 非法回應郵件與 EOP
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: 非法回應郵件所傳送的郵件伺服器，通常是因為傳入的垃圾郵件自動的退回的郵件。 非法回應 DNSBL 是一份傳送非法回應郵件的 IP 位址清單。 它不是濫發垃圾郵件者清單，我們不會嘗試從非法回應 DNSBL 移除我們的伺服器。
ms.openlocfilehash: 7581255ce4e68f6eb661df280ecb0cb94b7515ef
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693362"
---
# <a name="backscatter-messages-and-eop"></a><span data-ttu-id="2d6c0-105">非法回應郵件與 EOP</span><span class="sxs-lookup"><span data-stu-id="2d6c0-105">Backscatter messages and EOP</span></span>

<span data-ttu-id="2d6c0-106">非法回應郵件所傳送的郵件伺服器，通常是因為傳入的垃圾郵件自動的退回的郵件。</span><span class="sxs-lookup"><span data-stu-id="2d6c0-106">Backscatter messages are the automated bounce messages that are sent by mail servers, typically as a result of incoming spam.</span></span> <span data-ttu-id="2d6c0-107">因為 Exchange Online Protection (EOP) 是垃圾郵件篩選服務，我們的服務會拒絕傳送至不存在收件者及其他可疑目的地的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="2d6c0-107">Because Exchange Online Protection (EOP) is a spam filtering service, email messages sent to nonexistent recipients and to other suspicious destinations are rejected by our service.</span></span> <span data-ttu-id="2d6c0-108">發生此情況時，EOP 產生未傳遞回報 (NDR) 郵件並傳回給「寄件者」。</span><span class="sxs-lookup"><span data-stu-id="2d6c0-108">When this happens, EOP generates a non-delivery report (NDR) message and delivers it back to the "sender."</span></span> <span data-ttu-id="2d6c0-109">因為濫發垃圾郵件者經常在郵件中利用偽造或無效的「寄件者」地址，NDR 所寄到的寄件者地址可能會導致非法回應郵件。</span><span class="sxs-lookup"><span data-stu-id="2d6c0-109">Because spammers frequently use a forged or invalid "From" address in their messages, the sender address to which the NDR is sent may result in a backscatter message.</span></span> <span data-ttu-id="2d6c0-110">發生此情況時，與 EOP 網路相關聯的外寄伺服器可能會列在非法回應 DNS 封鎖清單 (DNSBL) 中。</span><span class="sxs-lookup"><span data-stu-id="2d6c0-110">When this happens, outgoing servers that are associated with the EOP network may be listed on the Backscatterer DNS Block List (DNSBL).</span></span> <span data-ttu-id="2d6c0-111">非法回應 DNSBL 是一份傳送非法回應郵件的 IP 位址清單。</span><span class="sxs-lookup"><span data-stu-id="2d6c0-111">The Backscatterer DNSBL is a list of IP addresses that send backscatter messages.</span></span> <span data-ttu-id="2d6c0-112">它不是濫發垃圾郵件者清單，我們不會嘗試從非法回應 DNSBL 移除我們的伺服器。</span><span class="sxs-lookup"><span data-stu-id="2d6c0-112">It isn't a spammer list, and we don't try to remove our servers from the Backscatterer DNSBL.</span></span> 
  
> [!TIP]
> <span data-ttu-id="2d6c0-p103">根據 Backscatterer 網站的指示，該服務的設定或用法不建議對所有傳入的郵件使用拒絕模式。而是應該在安全模式中使用。如需實作正確非法回應設定的相關資訊，請造訪 [Backscatterer.org 網站](http://www.backscatterer.org/?target=usage)。</span><span class="sxs-lookup"><span data-stu-id="2d6c0-p103">According to the instructions on the Backscatterer website, the use of reject mode for all incoming mail isn't a recommended configuration or use of that service. It should be used in safe mode instead. For more information about implementing the correct backscatter configuration, visit the [Backscatterer.org website](http://www.backscatterer.org/?target=usage).</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="2d6c0-116">相關資訊</span><span class="sxs-lookup"><span data-stu-id="2d6c0-116">For more information</span></span>

[<span data-ttu-id="2d6c0-117">Backscatterer.org IP 清單</span><span class="sxs-lookup"><span data-stu-id="2d6c0-117">The Backscatterer.org IP list</span></span>](https://blogs.msdn.com/b/tzink/archive/2012/08/22/the-backscatterer-org-ip-list.aspx)
  
<span data-ttu-id="2d6c0-118">請參閱 <<c0>進階垃圾郵件篩選選項中的 「 NDR 非法回應 」 項目</span><span class="sxs-lookup"><span data-stu-id="2d6c0-118">See the "NDR backscatter" entry in [Advanced spam filtering  options](advanced-spam-filtering-asf-options.md)</span></span>
  

