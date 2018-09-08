---
title: 從封鎖清單移除使用者、 網域或 IP 位址傳送垃圾電子郵件之後
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 09/05/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
description: 如果使用者持續傳送電子郵件訊息從歸類為垃圾郵件的 Office 365，他們會封鎖傳送任何詳細訊息。
ms.openlocfilehash: ff5bb010f45b0c89e08239f0e37885bd7ae5c7cd
ms.sourcegitcommit: 234a22c61859133ed5e7988a9551a569781518a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/07/2018
ms.locfileid: "23875785"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a>從封鎖清單移除使用者、 網域或 IP 位址傳送垃圾電子郵件之後

如果使用者持續傳送電子郵件訊息從歸類為垃圾郵件的 Office 365，他們會封鎖傳送任何詳細訊息。 
  
當封鎖寄件者時傳送電子郵件訊息時，他們會收到未傳遞報告 （NDR 或無法將郵件傳送的電子郵件），提供有解除封鎖本身所採取的步驟的特定資訊。
  
不僅可以個別使用者被封鎖服務，但特定網站、 網域及也也會遭到封鎖的 IP 位址。在某些情況下，網域或網站可以新增至封鎖清單只是因為它們顯示在垃圾郵件訊息。身為 Office 365 管理員，您可以嘗試取得使用者、 網站、 網域及從協力廠商封鎖清單中移除的 IP 位址。使用本主題底部表格中的連結來連絡每個協力廠商，然後依照指示。如果 Office 365 外的某個人無法將郵件傳送至您的 Office 365 帳戶，其帳戶可能已結束外部封鎖的寄件者清單上。Office 365 外部的使用者可以嘗試使用[自助取消列出的入口網站](https://technet.microsoft.com/library/mt661881%28v=exchg.150%29.aspx)從封鎖的寄件者清單中移除其本身。
  
您可以設定輸出垃圾郵件，讓您取得 anotification 時的 Office 365 使用者禁止傳送電子郵件被分類為垃圾郵件。與使用者的信箱問題已解決之後，您可以移除該寄件者在區塊。
  
## <a name="unblock-a-blocked-office-365-email-account"></a>解除封鎖封鎖的 Office 365 電子郵件帳戶

您完成此工作中的 Office 365 的安全性與規範中心 」 (SCC)。如需詳細資訊 SCC [[移至 [Office 365 安全性及規範中心](go-to-the-securitycompliance-center.md)]。

1. 使用工作或學校的帳戶具備 Office 365 全域管理員權限，登入 Office 365 安全性和規範中心及在左側清單中，依序展開 [ **Threat Management**，並選擇 [**檢閱**，然後選擇 [**限制使用者**。
    
    > [!TIP]
    > 若要直接移至 [**限制使用者**頁面的安全性&amp;規範中心使用此 URL: >[https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)

2. 此頁面可包含被封鎖傳送郵件給組織外的使用者清單。 尋找您想要移除限制上，然後按一下 [**解除**的使用者。

3. 按一下 [**是]** 確認變更。 
    
> [!NOTE]
> 有限制的帳戶可以解除封鎖承租人管理員的次數如果已超過此限制的使用者，就會出現錯誤訊息。然後您必須連絡支援人員以解除封鎖使用者。 
  
## <a name="third-party-block-lists"></a>協力廠商封鎖清單

|**清單名稱**|**取消列出的入口網站**|**相關資訊**|
|:-----|:-----|:-----|
|URIBL  <br/> |[https://admin.uribl.com/?section=lookup](https://admin.uribl.com/?section=lookup) <br/> |[URIBL 網站](https://uribl.com/) <br/> |
|SURBL  <br/> |[http://www.surbl.org/surbl-analysis](http://www.surbl.org/surbl-analysis) <br/> |[SURBL URI 信譽資料簡介](http://www.surbl.org/) <br/> |
|Spamhaus  <br/> |[https://www.spamhaus.org/lookup/](https://www.spamhaus.org/lookup/) <br/> |[了解 DNSBL 篩選](https://www.spamhaus.org/whitepapers/dnsbl_function/) <br/> |
|invaluement  <br/> |[http://dnsbl.invaluement.com/lookup/](http://dnsbl.invaluement.com/lookup/) <br/> |[invaluement 反垃圾郵件清單](http://dnsbl.invaluement.com/) <br/> |
|Phishtank  <br/> |[https://www.phishtank.com/](https://www.phishtank.com/) <br/> |[PhishTank 常見問題集](https://www.phishtank.com/faq.php) <br/> |
   
> [!NOTE]
> Exchange Online Protection 也會使用第三方封鎖清單的垃圾郵件篩選。 
   
## <a name="for-more-information"></a>如需詳細資訊

[設定輸出垃圾郵件原則](configure-the-outbound-spam-policy.md)
  
[外寄郵件的高風險傳遞集區](high-risk-delivery-pool-for-outbound-messages.md)

[使用取消列出入口網站，將您自己從 Office 365 封鎖寄件者清單中移除](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)
  

  

