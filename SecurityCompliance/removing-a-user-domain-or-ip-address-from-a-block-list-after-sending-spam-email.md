---
title: 從封鎖清單移除使用者、 網域或 IP 位址傳送垃圾電子郵件之後
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/01/2018
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
ms.openlocfilehash: 0f58f9f2270c8be38b3ea2ea81f04656eb10e7fb
ms.sourcegitcommit: 83406a3258e722020e46a82bbf4bc9d5d8a326ca
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/01/2018
ms.locfileid: "25899654"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a>從封鎖清單移除使用者、 網域或 IP 位址傳送垃圾電子郵件之後

如果使用者持續傳送電子郵件訊息從歸類為垃圾郵件的 Office 365，他們會封鎖傳送任何詳細訊息。使用者將會列在為損壞的撥出寄件者的服務，也會收到未傳遞報告 (NDR) 表示：

- 因為未被視為有效的寄件者無法傳遞郵件。最常見原因是您的電子郵件地址可疑的垃圾郵件的傳送和它已不再允許傳送到組織外的郵件。如需協助連絡電子郵件系統。 遠端伺服器傳回 '550 5.1.8 「 拒絕存取 」、 損壞的撥出寄件者 」

您可以設定您的輸出垃圾郵件原則設定，讓您在 Office 365 使用者禁止傳送電子郵件時收到通知。與使用者的信箱問題已解決之後，您可以移除該寄件者在區塊。
  
## <a name="unblock-a-blocked-office-365-email-account"></a>解除封鎖封鎖的 Office 365 電子郵件帳戶

您完成此工作中的 Office 365 的安全性與規範中心 」 (SCC)。如需詳細資訊 SCC [[移至 [Office 365 安全性及規範中心](go-to-the-securitycompliance-center.md)]。

1. 使用工作或學校的帳戶具備 Office 365 全域管理員權限，登入 Office 365 安全性和規範中心及在左側清單中，依序展開 [ **Threat Management**，並選擇 [**檢閱**，然後選擇 [**限制使用者**。
    
    > [!TIP]
    > 若要直接移至**受限制的使用者**] 頁面 （前身為巨集指令中心） 安全性&amp;規範中心使用此 URL: >[https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)

2. 此頁面可包含被封鎖傳送郵件給組織外的使用者清單。 尋找您想要移除限制上，然後按一下 [**解除**的使用者。

3. 按一下 [**是]** 確認變更。 
    
> [!NOTE]
> 有限制的帳戶可以解除封鎖承租人管理員的次數如果已超過此限制的使用者，就會出現錯誤訊息。然後您必須連絡支援人員以解除封鎖使用者。</br></br> 可能需要多達 1 小時之前使用者不封鎖。
  
## <a name="third-party-block-lists"></a>協力廠商封鎖清單

Exchange Online Protection 也會使用第三方封鎖清單來提升決策的垃圾郵件篩選。使用者、 網站、 網域及 IP 位址可以新增要封鎖只是為了垃圾郵件訊息中出現的清單。為 Office 365 系統管理員應該嘗試取得如果所屬您移除的協力廠商清單提供者從這些物件。

> [!NOTE]
> 如果 Office 365 外的某個人無法將郵件傳送至您的 Office 365 帳戶，其帳戶可能會在外部封鎖的寄件者清單。Office 365 外部的使用者可以嘗試使用[自助取消列出的入口網站](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis)中移除其本身。 

## <a name="for-more-information"></a>如需詳細資訊

[回應洩漏電子郵件帳戶](responding-to-a-compromised-email-account.md)

[設定輸出垃圾郵件原則](configure-the-outbound-spam-policy.md)
  
[外寄郵件的高風險傳遞集區](high-risk-delivery-pool-for-outbound-messages.md)

  

  

