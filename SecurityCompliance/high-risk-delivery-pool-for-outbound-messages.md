---
title: 外寄郵件的高風險傳遞集區
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/24/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
description: 如果客戶的電子郵件系統已遭洩露惡意程式碼或惡意的垃圾郵件攻擊，它會傳送到裝載的篩選服務的輸出垃圾郵件，這可能會導致所列在協力廠商封鎖的 Office 365 資料中心伺服器的 IP 位址列出。
ms.openlocfilehash: 856db53b105379ea3e606e39bf3c2612afa803c3
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026620"
---
# <a name="high-risk-delivery-pool-for-outbound-messages"></a>外寄郵件的高風險傳遞集區

如果客戶的電子郵件系統已遭洩露惡意程式碼或惡意的垃圾郵件攻擊，它會傳送到裝載的篩選服務的輸出垃圾郵件，這可能會導致所列在協力廠商封鎖的 Office 365 資料中心伺服器的 IP 位址列出。執行動作的目的地伺服器未使用託管的篩選服務，但不要使用這些封鎖清單、 拒絕所有從任何已新增至這些清單的主控篩選 IP 位址傳送電子郵件。若要避免此問題，超出垃圾郵件臨界值的所有外寄郵件傳送到高風險傳遞集區。此第二的外寄電子郵件集區僅用於傳送可能的低品質的郵件。這有助於保護網路的其餘部分傳送較可能導致遭封鎖的傳送端 IP 位址的郵件。
  
專用高風險傳遞集區的使用有助於確保標準輸出的集區只會將傳送至高品質的是已知的郵件。使用此次要 IP 集區有助於減少要新增至封鎖清單的一般輸出 IP 集區的機率。要放置在封鎖清單中的高風險傳遞集區的可能性會維持風險。這是根據設計。
  
郵件的傳送端網域其中有無提供您網域的 IP 位址的地址記錄 （記錄） 並無 MX 記錄，這樣有助於應該會收到 DNS 中特定網域的郵件伺服器直接郵件，永遠都透過不論其垃圾郵件處理高風險傳遞集區。
  
## <a name="understanding-delivery-status-notification-dsn-messages"></a>了解傳遞狀態通知 (DSN) 郵件

輸出高風險傳遞集區可管理所有 「 被退回 」 或 「 失敗 」 (DSN) 郵件的傳遞。
  
DSN 郵件激增的可能原因包括下列：
  
- 詐騙活動影響到使用服務的其中一位客戶
    
- 目錄搜集攻擊
    
- 垃圾郵件攻擊
    
- 惡意 SMTP 伺服器
    
所有的這些問題可能會導致突然增加的服務正在處理的 DSN 訊息數。次數，這些 DSN 郵件顯示為以其他電子郵件伺服器和服務的垃圾郵件。
  
## <a name="for-more-information"></a>如需詳細資訊

[設定輸出垃圾郵件原則](configure-the-outbound-spam-policy.md)
  
[反垃圾郵件保護常見問題集](anti-spam-protection-faq.md)
  

