---
title: 支援 DKIM 簽署郵件的驗證
ms.author: krowley
author: kccross
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
description: 了解 DKIM 驗證簽署 Exchange Online Protection 和 Exchange Online 中的郵件
ms.openlocfilehash: 22f0d1c4fdd6b1e159db732d6ef3d956efbf99c9
ms.sourcegitcommit: 75b985b2574f4be70cf352498ea300b3d99dd338
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2018
ms.locfileid: "26255828"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>支援 DKIM 簽署郵件的驗證

Exchange Online Protection (EOP) 和 Exchange Online 均可支援 Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) 郵件的輸入驗證。DKIM 是驗證郵件是從其所謂的源頭網域傳送且未遭到其他人冒用的方法。它會將電子郵件連到負責進行傳送的組織。DKIM 驗證會自動用於所有透過 IPv6 通訊傳送的郵件。(如需 IPv6 支援的詳細資訊，請參閱[支援透過 IPv6 的匿名輸入電子郵件](support-for-anonymous-inbound-email-messages-over-ipv6.md)。)
  
DKIM 會驗證郵件標頭的 DKIM 簽章標頭中顯示的數位簽署郵件。DKIM 簽章驗證的結果會在符合 RFC 7001 的 Authentication-Results 標頭中加上戳記 ([用於指出郵件驗證狀態的郵件標頭欄位](https://www.rfc-editor.org/rfc/rfc7001.txt))。顯示的郵件標頭文字類似下列文字 (寄件者為 contoso.com)：
  
 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`
  
系統管理員可以建立 Exchange[郵件流程規則](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx)（也稱為傳輸規則） 來篩選在 DKIM 驗證結果上或路由傳送訊息做為所需。 
  

