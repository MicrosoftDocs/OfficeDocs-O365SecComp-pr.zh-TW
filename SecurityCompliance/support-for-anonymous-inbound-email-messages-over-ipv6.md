---
title: 支援透過 IPv6 的匿名輸入電子郵件
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/4/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
description: Exchange Online Protection (EOP) 和 Exchange Online 支援接收透過傳輸層安全性 (TLS) 進行不傳送郵件的寄件者的 IPv6 通訊的匿名輸入的電子郵件。您可以選擇加入-中接收訊息透過 IPv6 向 UNRESOLVED_TOKEN_VAL(exMCSS) 要求此功能開啟在 Office 365 系統管理中心https://portal.office.com/adminportal/home] 及 [支援]，再然後按一下 [新增服務要求)。如果您沒有加入確認程序-在您將繼續透過 IPv4 接收訊息的 IPv6。
ms.openlocfilehash: 93575c57bb6eac5e0f92066dab3e6ed8b5f4b215
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/21/2018
ms.locfileid: "23003012"
---
# <a name="support-for-anonymous-inbound-email-messages-over-ipv6"></a>支援透過 IPv6 的匿名輸入電子郵件

Exchange Online Protection (EOP) 和 Exchange Online 支援接收透過傳輸層安全性 (TLS) 進行不傳送郵件的寄件者的 IPv6 通訊的匿名輸入的電子郵件。您可以選擇加入-中接收訊息透過 IPv6 向 UNRESOLVED_TOKEN_VAL(exMCSS) 要求此功能開啟在 Office 365 系統管理中心[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)] 及 [**支援**]，再然後按一下 [**新增服務要求**)。如果您沒有加入確認程序-在您將繼續透過 IPv4 接收訊息的 IPv6。
  
透過 IPv6 將郵件傳輸至服務的寄件者必須符合下列兩項需求：
  
1. 傳送 IPv6 地址必須具備有效的 PTR 記錄 (傳送 IPv6 地址的 [反向 DNS 記錄](https://en.wikipedia.org/wiki/Reverse_DNS_lookup))。 
    
2. 寄件者必須通過 SPF 驗證 (定義於 [RFC 7208](https://tools.ietf.org/html/rfc7208)) 或 [DKIM 驗證](http://dkim.org/) (定義於 [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt))。
    
符合這些需求是必要項目無論您選擇入 IPv6 之前的設定。如果符合這兩個需求、 郵件都會通過一般電子郵件訊息服務所提供的篩選。如果不符合其中一個或其他，郵件會被拒絕使用其中一個下列 450 回應：
  
-  `450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.`
    
-  `450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.`
    
如果您未選擇透過 IPv6 接收郵件，而寄件者藉由手動連線到郵件伺服器以試圖強制透過 IPv6 傳送郵件，則此郵件會遭到拒絕並出現類似下面的 550 回應：
  
 `550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.`
  
## <a name="for-more-information"></a>相關資訊

[支援 DKIM 簽署郵件的驗證](support-for-validation-of-dkim-signed-messages.md)
  

