---
title: EOP 排入佇列、延後和退回的訊息常見問題集
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
description: 本主題提供有關已排入佇列、延遲，或在 Microsoft Exchange Online Protection (EOP) 篩選程序中退回之郵件的常見問題解答。
ms.openlocfilehash: e8fdb07d11a1f540e94b82730eb848a97f51523a
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693202"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a><span data-ttu-id="9d8bf-103">EOP 排入佇列、延後和退回的訊息常見問題集</span><span class="sxs-lookup"><span data-stu-id="9d8bf-103">EOP queued, deferred, and bounced messages FAQ</span></span>

<span data-ttu-id="9d8bf-104">本主題提供有關已排入佇列、延遲，或在 Microsoft Exchange Online Protection (EOP) 篩選程序中退回之郵件的常見問題解答。</span><span class="sxs-lookup"><span data-stu-id="9d8bf-104">This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Microsoft Exchange Online Protection (EOP) filtering process.</span></span>
  
 <span data-ttu-id="9d8bf-105">**問：為何將郵件排入佇列？**</span><span class="sxs-lookup"><span data-stu-id="9d8bf-105">**Q. Why is mail queuing?**</span></span>
  
<span data-ttu-id="9d8bf-p101">答：如果服務無法連線到傳遞的收件者伺服器，郵件會排入佇列或延遲。如果從收件者的網路傳回 500 系列錯誤，它不會延遲郵件。</span><span class="sxs-lookup"><span data-stu-id="9d8bf-p101">A. Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery. It will not defer messages if a 500-series error is returned from the recipient network.</span></span>
  
 <span data-ttu-id="9d8bf-109">**問：如何延遲郵件？**</span><span class="sxs-lookup"><span data-stu-id="9d8bf-109">**Q. How does a message become deferred?**</span></span>
  
<span data-ttu-id="9d8bf-p102">答：當收件者伺服器的連線無法建立，而且收件者的伺服器傳回連接逾時、連線被拒絕或 400 系列錯誤等「暫存失敗」時，就會保留郵件。如果發生永久性失敗 (例如 500 系列錯誤)，郵件就會傳回給寄件者。</span><span class="sxs-lookup"><span data-stu-id="9d8bf-p102">A. Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error. If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.</span></span>
  
 <span data-ttu-id="9d8bf-113">**問：郵件維持延遲的時間有多長，而重試間隔時間有多長？**</span><span class="sxs-lookup"><span data-stu-id="9d8bf-113">**Q. How long does a message remain in deferral and what is the retry interval?**</span></span>
  
<span data-ttu-id="9d8bf-114">答：是。</span><span class="sxs-lookup"><span data-stu-id="9d8bf-114">A.</span></span> <span data-ttu-id="9d8bf-115">延期的郵件會留在我們佇列中 2 天。</span><span class="sxs-lookup"><span data-stu-id="9d8bf-115">Messages in deferral will remain in our queues for 2 days.</span></span> <span data-ttu-id="9d8bf-116">郵件重試次數乃是根據我們從收件者的郵件系統所取回的錯誤。</span><span class="sxs-lookup"><span data-stu-id="9d8bf-116">Message retry attempts are based on the error we get back from the recipient's mail system.</span></span> <span data-ttu-id="9d8bf-117">第一個的幾個 deferrals 是 15 分鐘或更少，與後續的重試 （透過下一個半十幾個） 透過多個最大值為 60 分鐘重試增加間隔。</span><span class="sxs-lookup"><span data-stu-id="9d8bf-117">The first few deferrals are 15 minutes or less, with subsequent retries (over the next half dozen or so) increasing the interval over multiple retries to a max of 60 minutes.</span></span> <span data-ttu-id="9d8bf-118">間隔期間擴充是動態的考慮像佇列大小和內部郵件優先順序的多個變數。</span><span class="sxs-lookup"><span data-stu-id="9d8bf-118">The interval duration expansion is dynamic, taking into consideration multiple variables like queue sizes and internal message priority.</span></span> <span data-ttu-id="9d8bf-119">在基本，它是 15 分鐘 （或更少） 若要開始，然後展開從該處透過下一步的幾個小時到最大 60 分鐘。</span><span class="sxs-lookup"><span data-stu-id="9d8bf-119">In basic, it's 15 minutes (or less) to start, then expanding from there over the next few hours to 60 mins max.</span></span>
  
 <span data-ttu-id="9d8bf-120">**問：還原您的電子郵件伺服器後，已排入佇列的郵件如何散佈？**</span><span class="sxs-lookup"><span data-stu-id="9d8bf-120">**Q. After your email server is restored, how are queued messages distributed?**</span></span>
  
<span data-ttu-id="9d8bf-p104">答：您的電子郵件伺服器還原後，所有排入佇列的郵件會在伺服器無法使用時，自動根據他們被接收與排入佇列的順序自動進行處理。</span><span class="sxs-lookup"><span data-stu-id="9d8bf-p104">A. After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable.</span></span> 
  

