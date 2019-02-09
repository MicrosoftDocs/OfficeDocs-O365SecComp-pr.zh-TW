---
title: Office 365 中的 ATP 防網路釣魚功能
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5076d0f6-7a59-4d6c-bd07-ba95033f0682
description: ATP 反網路釣魚是 Office 365 進階威脅保護的一部分。ATP 反網路釣魚適用於搭配模擬偵測演算法的機器學習模型的一組提供保護商品和矛網路釣魚攻擊的內送郵件。所有訊息都是因偵測網路釣魚郵件，以及用來防止各種使用者和網域模擬攻擊的進階演算法一組經過訓練的機器學習模型廣泛設定而異。
ms.openlocfilehash: c3e44a313bf9c823fbfda138fc5a10294993d509
ms.sourcegitcommit: c1c41744c2de89c9e172f817c8f73bb0ada81a58
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2019
ms.locfileid: "29792268"
---
# <a name="atp-anti-phishing-capabilities-in-office-365"></a>Office 365 中的 ATP 防網路釣魚功能

ATP 反網路釣魚是[Office 365 進階威脅保護](office-365-atp.md)的一部分。ATP 反網路釣魚適用於搭配模擬偵測演算法的機器學習模型的一組提供保護商品和矛網路釣魚攻擊的內送郵件。所有訊息都是因偵測網路釣魚郵件，以及用來防止各種使用者和網域模擬攻擊的進階演算法一組經過訓練的機器學習模型廣泛設定而異。ATP 反網路釣魚保護您的組織根據至原則之設定的 Office 365 全域或安全性管理員。
  
若要深入了解，請參閱[Set up Office 365 中的反網路釣魚原則](set-up-anti-phishing-policies.md)。
  
> [!NOTE]
> ATP 反網路釣魚只有在進階威脅 Protection，其中包含在訂閱，例如[Microsoft 365 企業版](https://www.microsoft.com/microsoft-365/enterprise/home)、 [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)、 Office 365 企業版 E5、 Office 365 教育版 A5 等。如果您的組織有不包含 Office 365 ATP Office 365 訂閱，可能可以做為附加元件購買 ATP。如需詳細資訊，請參閱[Office 365 進階威脅保護計劃和價格](https://products.office.com/exchange/advance-threat-protection)和[Office 365 進階威脅 Protection 服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。

## <a name="how-atp-anti-phishing-works"></a>ATP 反網路釣魚的運作方式

ATP 反網路釣魚會檢查郵件可能是網路釣魚指標的內送郵件。每當使用者是原則所涵蓋 ATP （安全附件、 安全的連結或反網路釣魚） 學習分析決定如果原則可套用至郵件與適當的動作是郵件的模型的多部電腦來評估傳入訊息進行設定的原則為基礎。
  
ATP 反網路釣魚讓 Office 365 全域管理員或安全性管理員可定義提供理想的網路釣魚攻擊包含模擬的使用者或網域的原則。（或兩者）。Office 365 全域管理員或安全性管理員定義哪些使用者和網域應保護免受模擬攻擊使用下列任一原則內的使用者或網域或使用信箱智慧固定的清單。信箱智慧是使用者的電子郵件習慣及個人連絡人的進階的知識。ATP 可學習如何每個個別的使用者會與其他組織內外的使用者通訊和建立這些關係的對應設定。本藍圖可讓 ATP 了解如何確定右邊的郵件會被識別為模擬的詳細資訊。
  
ATP 反網路釣魚原則可套用到特定的一段的人員或組織中的群組或整個網域或所有自訂的網域。若要深入了解，請參閱[Set up Office 365 中的反網路釣魚原則](set-up-anti-phishing-policies.md)。
  
## <a name="how-to-get-atp-anti-phishing"></a>如何取得 ATP 反網路釣魚

ATP 反網路釣魚功能屬於[進階威脅保護](office-365-atp.md);不過，當反網路釣魚原則會定義套用 ATP 反網路釣魚保護。（一個範例是模擬為基礎的原則）。請參閱 ＜ [Set up Office 365 中的反網路釣魚原則](set-up-anti-phishing-policies.md)。
  
## <a name="how-to-know-if-atp-anti-phishing-is-in-place"></a>如何知道 ATP 反網路釣魚是否就緒

ATP 反網路釣魚原則必須定義 protection 設為 [作用中的順序。檢查這第一次以確認保護已備妥。

此外，報表可用來顯示服務組織的運作方式。若要深入了解，請參閱[Office 365 進階威脅保護的檢視報告](view-reports-for-atp.md)。

ATP 反網路釣魚機器學習作用中的特定使用者的模型，使用者必須已定義的[ATP 安全附件功能](atp-safe-attachments.md)、 [ATP 安全連結](atp-safe-links.md)或 ATP 反網路釣魚原則的一部分。 

下表說明幾個範例案例。在每個這些範例中，組織使用 Office 365 企業版 E5，其中包含進階威脅保護。
  
|**範例案例**|**ATP 反網路釣魚沒有在此例中套用吗？**|
|:-----|:-----|
|Pat 的組織具有 Office 365 企業版 E5，但無人已定義 ATP 安全附件、 ATP 安全連結或尚未進階網路釣魚 ATP 的任何原則。|[否]。雖然有提供功能，必須至少一個 ATP 原則定義學習模型 ATP 電腦運作的順序。進行模擬 ATP 反網路釣魚原則也必須備妥。|
|Lee 是在 Contoso sales 部門的員工。Lee 的組織中進行的財務員工僅適用於具有 ATP 反網路釣魚原則。|[否]。在此例中 ATP 反網路釣魚 （機器模型和模擬保護） 會套用至 finance 員工但不是會包括銷售部門的其他員工。|
|昨天、 Jean 的組織在 Office 365 系統管理員設定套用至所有員工 ATP 反網路釣魚原則。稍早今天 Jean 接收電子郵件訊息內含該原則所涵蓋模擬。|[是]。在這個範例中，Jean 已授權的進階威脅保護，並已定義包含 Jean ATP 反網路釣魚原則。它通常採用的新原則才會生效跨資料中心來; 約 30 分鐘因為在此例中通過一天、 原則應作用中。|

## <a name="related-topics"></a>相關主題

[Office 365 進階威脅防護](office-365-atp.md)
  
[Office 365 的反網路釣魚保護](anti-phishing-protection.md)
  
[設定 Office 365 中的反網路釣魚原則](set-up-anti-phishing-policies.md)
  
[Office 365 中的 ATP 安全連結](atp-safe-links.md)
  
[設定 Office 365 中的 ATP 安全連結原則](set-up-atp-safe-links-policies.md)
  
[Office 365 中的 ATP 安全附件](atp-safe-attachments.md)
  
[設定 Office 365 中的 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)
  
[進階威脅保護的檢視報告](view-reports-for-atp.md)
