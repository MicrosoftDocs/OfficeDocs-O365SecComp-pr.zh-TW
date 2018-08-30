---
title: Office 365 中的 ATP 防網路釣魚功能
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5076d0f6-7a59-4d6c-bd07-ba95033f0682
description: ATP 反網路釣魚被提供 Office 365 進階威脅保護的一部分。ATP 反網路釣魚適用於搭配模擬偵測演算法的機器學習模型的一組提供保護商品和矛網路釣魚攻擊的內送郵件。所有訊息都是因偵測網路釣魚郵件，以及用來防止各種使用者和網域模擬攻擊的進階演算法一組經過訓練的機器學習模型廣泛設定而異。ATP 反網路釣魚保護您的組織根據至原則之設定的 Office 365 全域或安全性管理員。
ms.openlocfilehash: cff25316f9a03bdfafd195eb408584ab8bca6343
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526593"
---
# <a name="atp-anti-phishing-capabilities-in-office-365"></a>Office 365 中的 ATP 防網路釣魚功能

ATP 反網路釣魚被提供[Office 365 進階威脅保護](https://technet.microsoft.com/en-us/library/exchange-online-advanced-threat-protection-service-description.aspx)的一部分。ATP 反網路釣魚適用於搭配模擬偵測演算法的機器學習模型的一組提供保護商品和矛網路釣魚攻擊的內送郵件。所有訊息都是因偵測網路釣魚郵件，以及用來防止各種使用者和網域模擬攻擊的進階演算法一組經過訓練的機器學習模型廣泛設定而異。ATP 反網路釣魚保護您的組織根據至原則之設定的 Office 365 全域或安全性管理員。
  
若要深入了解，請參閱[Set up Office 365 中的 ATP 反網路釣魚原則](set-up-atp-anti-phishing-policies.md)。
  
> [!NOTE]
> ATP 反網路釣魚只有在進階威脅 Protection，可用的 Office 365 企業版 E5。如果貴組織要使用另一個 Office 365 企業版訂閱，可做為附加元件購買進階威脅保護。(以全域管理員在 Office 365 系統管理中心中，選擇 [**計費** \> **新增訂閱**。)如需計劃選項的詳細資訊，請參閱[比較各種 Office 365 商務計劃](https://go.microsoft.com/fwlink/?linkid=844053)。 
    
## <a name="how-atp-anti-phishing-works"></a>ATP 反網路釣魚的運作方式
<a name="Howantiphishworks"> </a>

ATP 反網路釣魚會檢查郵件可能是網路釣魚指標的內送郵件。每當使用者是原則所涵蓋 ATP （安全附件、 安全的連結或反網路釣魚） 學習分析決定如果原則可套用至郵件與適當的動作是郵件的模型的多部電腦來評估傳入訊息進行設定的原則為基礎。
  
ATP 反網路釣魚讓 Office 365 全域管理員或安全性管理員可定義提供理想的網路釣魚攻擊包含模擬的使用者或網域的原則。（或兩者）。Office 365 全域管理員或安全性管理員定義哪些使用者和網域應保護免受模擬攻擊使用下列任一原則內的使用者或網域或使用信箱智慧固定的清單。信箱智慧是使用者的電子郵件習慣及個人連絡人的進階的知識。ATP 可學習如何每個個別的使用者會與其他組織內外的使用者通訊和建立這些關係的對應設定。本藍圖可讓 ATP 了解如何確定右邊的郵件會被識別為模擬的詳細資訊。
  
ATP 反網路釣魚原則可套用到特定的一段的人員或組織中的群組或整個網域或所有自訂的網域。若要深入了解，請參閱[Set up Office 365 中的 ATP 反網路釣魚原則](set-up-atp-anti-phishing-policies.md)。
  
## <a name="how-to-get-atp-anti-phishing"></a>如何取得 ATP 反網路釣魚
<a name="Howtogetantiphish"> </a>

ATP 反網路釣魚是進階威脅保護，其中包含在 Office 365 企業版 E5 的一部分。進階的威脅保護也能以 Office 365 企業版 E1 或 Office 365 企業版 E3 的附加元件形式購買。如需計劃選項的詳細資訊，請參閱[比較各種 Office 365 商務計劃](https://go.microsoft.com/fwlink/?linkid=844053)。
  
ATP 反網路釣魚適用於當反網路釣魚原則，例如模擬為基礎的原則設定。（請參閱[Set up Office 365 中的 ATP 反網路釣魚原則](set-up-atp-anti-phishing-policies.md)）。
  
## <a name="how-to-know-if-atp-anti-phishing-is-in-place"></a>如何知道 ATP 反網路釣魚是否就緒
<a name="IsantiphishOn"> </a>

ATP 反網路釣魚原則必須定義保護作用中的順序。ATP 反網路釣魚機器學習模型為作用中使用者的使用者必須已定義的安全附件、 安全的連結或反網路釣魚原則的一部分。下表說明幾個範例案例。在每個這些範例中，組織使用 Office 365 企業版 E5，其中包含進階威脅保護。
  
|**範例案例**|**ATP 反網路釣魚沒有在此例中套用吗？**|
|:-----|:-----|
|Pat 的組織具有 Office 365 企業版 E5，但無人已定義 ATP 安全附件、 ATP 安全連結或尚未進階網路釣魚 ATP 的任何原則。|[否]。雖然有提供功能，必須至少一個 ATP 原則定義學習模型 ATP 電腦運作的順序。進行模擬 ATP 反網路釣魚原則也必須備妥。|
|Lee 是在 Contoso sales 部門的員工。Lee 的組織中進行的財務員工僅適用於具有 ATP 反網路釣魚原則。|[否]。在此例中 ATP 反網路釣魚 （機器模型和模擬保護） 會套用至 finance 員工但不是會包括銷售部門的其他員工。|
|昨天、 Jean 的組織在 Office 365 系統管理員設定套用至所有員工 ATP 反網路釣魚原則。稍早今天 Jean 接收電子郵件訊息內含該原則所涵蓋模擬。|[是]。在這個範例中，Jean 已授權的進階威脅保護，並已定義包含 Jean ATP 反網路釣魚原則。它通常採用的新原則才會生效跨資料中心來; 約 30 分鐘因為在此例中通過一天、 原則應作用中。|
   
## <a name="related-topics"></a>相關主題
<a name="IsantiphishOn"> </a>

[Office 365 進階威脅防護](office-365-atp.md)
  
[Office 365 的反網路釣魚保護](anti-phishing-protection.md)
  
[設定 Office 365 中的 ATP 反網路釣魚原則](set-up-atp-anti-phishing-policies.md)
  
[Office 365 中的 ATP 安全連結](atp-safe-links.md)
  
[設定 Office 365 中的 ATP 安全連結原則](set-up-atp-safe-links-policies.md)
  
[Office 365 中的 ATP 安全附件](atp-safe-attachments.md)
  
[設定 Office 365 中的 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)
  
[進階威脅保護的檢視報告](view-reports-for-atp.md)
  

