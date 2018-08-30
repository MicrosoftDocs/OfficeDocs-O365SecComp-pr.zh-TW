---
title: 支援 DKIM 簽署郵件的驗證
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
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
description: Exchange Online Protection (EOP) 和 Exchange Online 均可支援 Domain Keys Identified Mail (DKIM) 郵件的輸入驗證。DKIM 是驗證郵件是從其所謂的源頭網域傳送且未遭到其他人冒用的方法。它會將電子郵件連到負責進行傳送的組織。DKIM 驗證會自動用於所有透過 IPv6 通訊傳送的郵件。(如需 IPv6 支援的詳細資訊，請參閱支援透過 IPv6 的匿名輸入電子郵件。)
ms.openlocfilehash: d2fab69847732bb7ed54f943d2c7845e06084936
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002252"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>支援 DKIM 簽署郵件的驗證

Exchange Online Protection (EOP) 和 Exchange Online 均可支援 Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) 郵件的輸入驗證。DKIM 是驗證郵件是從其所謂的源頭網域傳送且未遭到其他人冒用的方法。它會將電子郵件連到負責進行傳送的組織。DKIM 驗證會自動用於所有透過 IPv6 通訊傳送的郵件。(如需 IPv6 支援的詳細資訊，請參閱[支援透過 IPv6 的匿名輸入電子郵件](support-for-anonymous-inbound-email-messages-over-ipv6.md)。)
  
DKIM 會驗證郵件標頭的 DKIM 簽章標頭中顯示的數位簽署郵件。DKIM 簽章驗證的結果會在符合 RFC 7001 的 Authentication-Results 標頭中加上戳記 ([用於指出郵件驗證狀態的郵件標頭欄位](https://www.rfc-editor.org/rfc/rfc7001.txt))。顯示的郵件標頭文字類似下列文字 (寄件者為 contoso.com)：
  
 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`
  
系統管理員可以在 DKIM 驗證結果上建立 Exchange [Transport Rules](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx)，以視需要篩選或路由傳送郵件。 
  

