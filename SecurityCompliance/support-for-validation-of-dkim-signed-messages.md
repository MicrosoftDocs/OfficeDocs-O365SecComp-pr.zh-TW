---
title: 支援 DKIM 簽署郵件的驗證
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: 了解的驗證的 DKIM 簽署郵件在 Exchange Online Protection 和 Exchange Online
ms.openlocfilehash: 88a01944dd215ff3b6f22a266a12145927f89e0a
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2019
ms.locfileid: "35600706"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a><span data-ttu-id="ef281-103">支援 DKIM 簽署郵件的驗證</span><span class="sxs-lookup"><span data-stu-id="ef281-103">Support for validation of DKIM signed messages</span></span>

<span data-ttu-id="ef281-p101">Exchange Online Protection (EOP) 和 Exchange Online 均可支援 Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) 郵件的輸入驗證。DKIM 是驗證郵件是從其所謂的源頭網域傳送且未遭到其他人冒用的方法。它會將電子郵件連到負責進行傳送的組織。DKIM 驗證會自動用於所有透過 IPv6 通訊傳送的郵件。(如需 IPv6 支援的詳細資訊，請參閱[支援透過 IPv6 的匿名輸入電子郵件](support-for-anonymous-inbound-email-messages-over-ipv6.md)。)</span><span class="sxs-lookup"><span data-stu-id="ef281-p101">Exchange Online Protection (EOP) and Exchange Online support inbound validation of Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) messages. DKIM is a method for validating that a message was sent from the domain it says it originated from and that it was not spoofed by someone else. It ties an email message to the organization responsible for sending it. DKIM verification is automatically used for all messages sent over IPv6 communications. (For more information about IPv6 support, see [Support for anonymous inbound email messages over IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span></span>
  
<span data-ttu-id="ef281-p102">DKIM 會驗證郵件標頭的 DKIM 簽章標頭中顯示的數位簽署郵件。DKIM 簽章驗證的結果會在符合 RFC 7001 的 Authentication-Results 標頭中加上戳記 ([用於指出郵件驗證狀態的郵件標頭欄位](https://www.rfc-editor.org/rfc/rfc7001.txt))。顯示的郵件標頭文字類似下列文字 (寄件者為 contoso.com)：</span><span class="sxs-lookup"><span data-stu-id="ef281-p102">DKIM validates a digitally signed message that appears in the DKIM-Signature header in the message headers. The results of a DKIM-Signature validation is stamped in the Authentication-Results header which conforms with RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt)). The message header text appears similar to the following (where contoso.com is the sender):</span></span>
  
 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`
  
<span data-ttu-id="ef281-112">系統管理員可以建立 Exchange[郵件流程規則](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx)（也稱為傳輸規則） 來篩選在 DKIM 驗證結果上，或將郵件路由傳送做為所需。</span><span class="sxs-lookup"><span data-stu-id="ef281-112">Admins can create Exchange [mail flow rules](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx) (also known as transport rules) on the results of a DKIM validation to filter or route messages as needed.</span></span> 
  

