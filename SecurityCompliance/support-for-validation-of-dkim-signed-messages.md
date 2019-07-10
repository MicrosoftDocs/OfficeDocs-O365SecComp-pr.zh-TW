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
# <a name="support-for-validation-of-dkim-signed-messages"></a>支援 DKIM 簽署郵件的驗證

Exchange Online Protection (EOP) 和 Exchange Online 均可支援 Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) 郵件的輸入驗證。DKIM 是驗證郵件是從其所謂的源頭網域傳送且未遭到其他人冒用的方法。它會將電子郵件連到負責進行傳送的組織。DKIM 驗證會自動用於所有透過 IPv6 通訊傳送的郵件。(如需 IPv6 支援的詳細資訊，請參閱[支援透過 IPv6 的匿名輸入電子郵件](support-for-anonymous-inbound-email-messages-over-ipv6.md)。)
  
DKIM 會驗證郵件標頭的 DKIM 簽章標頭中顯示的數位簽署郵件。DKIM 簽章驗證的結果會在符合 RFC 7001 的 Authentication-Results 標頭中加上戳記 ([用於指出郵件驗證狀態的郵件標頭欄位](https://www.rfc-editor.org/rfc/rfc7001.txt))。顯示的郵件標頭文字類似下列文字 (寄件者為 contoso.com)：
  
 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`
  
系統管理員可以建立 Exchange[郵件流程規則](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx)（也稱為傳輸規則） 來篩選在 DKIM 驗證結果上，或將郵件路由傳送做為所需。 
  

