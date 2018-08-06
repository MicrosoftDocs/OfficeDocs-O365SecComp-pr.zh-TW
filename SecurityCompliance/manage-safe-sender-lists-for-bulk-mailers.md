---
title: 管理大量此刻的安全寄件者清單
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: d48db4a3-9fbe-45e2-bbaa-1017ffdf96f8
description: 如果您想要使用安全的寄件者清單，您應該了解 Exchange Online Protection (EOP) 和 Outlook 處理以不同方式處理。此服務會區分安全的寄件者和網域來檢查 RFC 5321.MailFrom 地址和 RFC 5322.From 地址時 Outlook 將 RFC 5322.From 位址新增至使用者的安全寄件者清單。(請注意： 此服務會封鎖的寄件者和網域檢查 5321.MailFrom 位址] 及 [5322.From 位址。)
ms.openlocfilehash: e5d6f8440281d527e7ea1846416b785beda25f1c
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026540"
---
# <a name="manage-safe-sender-lists-for-bulk-mailers"></a>管理大量此刻的安全寄件者清單

如果您想要使用安全的寄件者清單，您應該了解 Exchange Online Protection (EOP) 和 Outlook 處理以不同方式處理。此服務會區分安全的寄件者和網域來檢查 RFC 5321.MailFrom 地址和 RFC 5322.From 地址時 Outlook 將 RFC 5322.From 位址新增至使用者的安全寄件者清單。(請注意： 此服務會封鎖的寄件者和網域檢查 5321.MailFrom 位址] 及 [5322.From 位址。)
  
SMTP 郵件的地址，又稱為 RFC 5321.MailFrom 地址是用來執行 SPF 檢查電子郵件地址如果郵件無法傳遞、 退回的郵件傳遞至其中的路徑。但是若要指定不同的投資路徑地址寄件者的有可能是根據預設，放入郵件標頭中的投資路徑此電子郵件地址。
  
From： 郵件標頭，又稱為 RFC 5322.From 地址的地址是例如 Outlook 的郵件用戶端中所顯示的電子郵件地址。
  
有多少時間、 5321.MailFrom 和 5322.From 位址都相同。這是一般的人對人通訊。不過，當代表其他人傳送電子郵件，會經常不同位址。這通常是因為最常的大量電子郵件訊息。
  
例如，假設航空 Blue Yonder Airlines 具有縮減出 Margie 的旅行傳送出其電子郵件通知。再收到訊息收件匣中的寄件者 blueyonder@news.blueyonderairlines.com。在此例中 5321.MailFrom 位址 blueyonder.airlines@margiestravel.com，且 blueyonder@news.blueyonderairlines.com 是這是您在 Outlook 中看到其中一個 5322.From 地址。因為服務遵守區別發音 RFC 5322.From 地址，若要防止此訊息快速篩選只可以在 Outlook 中的安全寄件者為新增 RFC 5322.From 地址。
  

