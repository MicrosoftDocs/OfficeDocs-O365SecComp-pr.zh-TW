---
title: 管理大量郵件寄件者的安全寄件者清單
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d48db4a3-9fbe-45e2-bbaa-1017ffdf96f8
ms.collection:
- M365-security-compliance
description: 如果您想要使用安全的寄件者清單，您應該了解 Exchange Online Protection (EOP) 和 Outlook 處理以不同方式處理。此服務會區分安全的寄件者和網域來檢查 RFC 5321.MailFrom 地址和 RFC 5322.From 地址時 Outlook 將 RFC 5322.From 位址新增至使用者的安全寄件者清單。(請注意： 此服務會封鎖的寄件者和網域檢查 5321.MailFrom 位址] 及 [5322.From 位址。)
ms.openlocfilehash: 27d635ec93dd04df8ebf22d5d3d8f8ead4b7bcf8
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30276133"
---
# <a name="manage-safe-sender-lists-for-bulk-mailers"></a><span data-ttu-id="29990-105">管理大量郵件寄件者的安全寄件者清單</span><span class="sxs-lookup"><span data-stu-id="29990-105">Manage safe sender lists for bulk mailers</span></span>

<span data-ttu-id="29990-p102">如果您想要使用安全的寄件者清單，您應該了解 Exchange Online Protection (EOP) 和 Outlook 處理以不同方式處理。此服務會區分安全的寄件者和網域來檢查 RFC 5321.MailFrom 地址和 RFC 5322.From 地址時 Outlook 將 RFC 5322.From 位址新增至使用者的安全寄件者清單。(請注意： 此服務會封鎖的寄件者和網域檢查 5321.MailFrom 位址] 及 [5322.From 位址。)</span><span class="sxs-lookup"><span data-stu-id="29990-p102">If you want to use safe sender lists, you should know that Exchange Online Protection (EOP) and Outlook handle processing differently. The service respects safe senders and domains by inspecting the RFC 5321.MailFrom address and the RFC 5322.From address, while Outlook adds the RFC 5322.From address to a user's safe sender list. (Note: The service inspects both the 5321.MailFrom address and 5322.From address for blocked senders and domains.)</span></span>
  
<span data-ttu-id="29990-p103">SMTP 郵件的地址，又稱為 RFC 5321.MailFrom 地址是用來執行 SPF 檢查電子郵件地址如果郵件無法傳遞、 退回的郵件傳遞至其中的路徑。但是若要指定不同的投資路徑地址寄件者的有可能是根據預設，放入郵件標頭中的投資路徑此電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="29990-p103">The SMTP MAIL FROM address, otherwise known as the RFC 5321.MailFrom address, is the email address that's used to perform SPF checks, and if the mail can't be delivered, the path to which the bounced message is delivered. It's this email address that is placed into the Return-Path in the message headers by default, though it's possible for the sender to designate a different Return-Path address.</span></span>
  
<span data-ttu-id="29990-111">From： 郵件標頭，又稱為 RFC 5322.From 地址的地址是例如 Outlook 的郵件用戶端中所顯示的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="29990-111">The From: address in the message headers, otherwise known as the RFC 5322.From address, is the email address that is displayed in the mail client such as Outlook.</span></span>
  
<span data-ttu-id="29990-p104">有多少時間、 5321.MailFrom 和 5322.From 位址都相同。這是一般的人對人通訊。不過，當代表其他人傳送電子郵件，會經常不同位址。這通常是因為最常的大量電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="29990-p104">Much of the time, the 5321.MailFrom and 5322.From addresses are the same. This is typical for person-to-person communication. However, when email is sent on behalf of someone else, the addresses are frequently different. This usually happens most often for bulk email messages.</span></span>
  
<span data-ttu-id="29990-p105">例如，假設航空 Blue Yonder Airlines 具有縮減出 Margie 的旅行傳送出其電子郵件通知。再收到訊息收件匣中的寄件者 blueyonder@news.blueyonderairlines.com。在此例中 5321.MailFrom 位址 blueyonder.airlines@margiestravel.com，且 blueyonder@news.blueyonderairlines.com 是這是您在 Outlook 中看到其中一個 5322.From 地址。因為服務遵守區別發音 RFC 5322.From 地址，若要防止此訊息快速篩選只可以在 Outlook 中的安全寄件者為新增 RFC 5322.From 地址。</span><span class="sxs-lookup"><span data-stu-id="29990-p105">For example, suppose that the airline Blue Yonder Airlines has contracted out Margie's Travel to send out its email advertising. You then get a message in your inbox from sender blueyonder@news.blueyonderairlines.com. In this case, the 5321.MailFrom address is blueyonder.airlines@margiestravel.com, and blueyonder@news.blueyonderairlines.com is the 5322.From address which is the one you see in Outlook. Because the service respects the RFC 5322.From address, to prevent this message from getting filtered, you can simply add the RFC 5322.From address as a safe sender in Outlook.</span></span>
  

