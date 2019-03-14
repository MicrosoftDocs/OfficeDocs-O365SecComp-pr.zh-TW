---
title: Office 365 中的 ATP 防網路釣魚功能
ms.author: tracyp
author: MSFTTracyp
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5076d0f6-7a59-4d6c-bd07-ba95033f0682
ms.collection:
- M365-security-compliance
description: ATP 防網路釣魚是 Office 365 進階威脅防護的一部分。 ATP 防網路釣魚將機器學習模型搭配模擬偵測演算法的一組套用於內送郵件提供保護市售和矛網路釣魚攻擊。 所有郵件都都會受到機器學習模型來偵測網路釣魚郵件，以及一組用來防範各種不同的使用者和網域模擬攻擊的進階演算法訓練廣泛設定。
ms.openlocfilehash: 25e7845ab7d16b0766636006f2c55debfee2f9f9
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30276373"
---
# <a name="atp-anti-phishing-capabilities-in-office-365"></a>Office 365 中的 ATP 防網路釣魚功能

ATP 防網路釣魚是[Office 365 進階威脅防護](office-365-atp.md)的一部分。 ATP 防網路釣魚將機器學習模型搭配模擬偵測演算法的一組套用於內送郵件提供保護市售和矛網路釣魚攻擊。 所有郵件都都會受到機器學習模型來偵測網路釣魚郵件，以及一組用來防範各種不同的使用者和網域模擬攻擊的進階演算法訓練廣泛設定。 ATP 防網路釣魚保護您的組織根據至原則] 下，由您的 Office 365 全域或安全性管理員設定。
  
若要深入了解，請參閱 <<c0>設定 Office 365 中的反網路釣魚原則。
  
> [!NOTE]
> ATP 防網路釣魚只有在進階威脅防護，這包含在訂閱，例如[Microsoft 365 企業版](https://www.microsoft.com/microsoft-365/enterprise/home)、 [Microsoft 365 商務版](https://www.microsoft.com/microsoft-365/business)、 Office 365 企業版 E5、 Office 365 教育版 A5 等。如果貴組織擁有不包含 Office 365 ATP 的 Office 365 訂閱，您可能可以當作附加元件購買 ATP。 如需詳細資訊，請參閱[Office 365 進階威脅防護方案和價格](https://products.office.com/exchange/advance-threat-protection)和[Office 365 進階威脅防護服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。

## <a name="how-atp-anti-phishing-works"></a>ATP 防網路釣魚的運作方式

ATP 防網路釣魚檢查內送郵件的郵件可能是網路釣魚的指標。 每當使用者涵蓋的 ATP 原則 （安全附件、 安全連結或反網路釣魚） 時，內送郵件會評估由多部機器學習模型，分析此郵件若要判斷是否將原則套用至郵件，以及適當的巨集指令採取，根據設定的原則。
  
ATP 防網路釣魚讓 Office 365 全域系統管理員或安全性系統管理員可以定義包含模擬的使用者或網域的網路釣魚攻擊防護的原則。 （或兩者）。 Office 365 全域系統管理員或安全性系統管理員定義哪些使用者和網域應該要防止使用模擬攻擊原則內的使用者或網域，或使用信箱智慧固定的清單。 信箱智慧是進階了解使用者的電子郵件習慣與個人連絡人。 ATP 可學習如何每個個別的使用者會與其他組織內部和外部的使用者進行通訊，並建立備份這些關聯性的分佈圖。 此對應可讓 ATP 了解有關如何確保正確的郵件會被識別為模擬的更多詳細資訊。
  
ATP 防網路釣魚原則可以套用至一組特定的人員或組織中的群組或整個網域或所有的自訂網域。 若要深入了解，請參閱 <<c0>設定 Office 365 中的反網路釣魚原則。
  
## <a name="how-to-get-atp-anti-phishing"></a>如何取得 ATP 防網路釣魚

ATP 防網路釣魚功能是[進階威脅防護](office-365-atp.md)功能; 的一部分不過，ATP 防網路釣魚保護套用時反網路釣魚原則所定義。 （其中一個範例是模擬為基礎的原則）。請參閱 <<c0>設定 Office 365 中的反網路釣魚原則。
  
## <a name="how-to-know-if-atp-anti-phishing-is-in-place"></a>如何知道 ATP 防網路釣魚是否已經準備就緒

ATP 防網路釣魚原則必須在才能生效讓防護中定義。 請檢查此選項，第一次即可確認防護已經準備就緒。

此外，報告可用於顯示服務的組織的運作方式。 若要深入了解，請參閱[View reports for Office 365 進階威脅防護。](view-reports-for-atp.md)

ATP 防網路釣魚機器學習模型為作用中的特定使用者，該使用者必須已定義的[ATP 安全附件](atp-safe-attachments.md)， [ATP 安全連結](atp-safe-links.md)或 ATP 防網路釣魚原則的一部分。 

下表說明幾個範例案例。 在每個這些範例中，組織使用 Office 365 企業版 E5，包括進階威脅防護。
  
|**範例案例**|**ATP 防網路釣魚不會在此情況下套用嗎？**|
|:-----|:-----|
|Pat 的組織有 Office 365 企業版 E5，但沒有其他已定義的 ATP 安全附件，ATP 安全連結或 ATP 尚未進階網路釣魚的任何原則。|否。 雖然功能可供使用，至少一個 ATP 原則必須定義為了讓 ATP 機器學習模型來運作。 模擬的 ATP 防網路釣魚原則也必須就緒。|
|Lee 是在 contoso 公司銷售部門中的員工。 Lee 的組織具有的 ATP 防網路釣魚原則在適用於僅限財務員工的位置。|否。 在此情況下，ATP 防網路釣魚 （機器模型和模擬保護） 會套用至 finance 員工，但其他員工，包括銷售部門中，不會。|
|昨天，Office 365 系統管理員在設定 ATP 防網路釣魚原則套用至所有員工的 Jean 的組織。 稍早今天 Jean 接收電子郵件訊息，其中包含該原則所涵蓋模擬。|可以。 在這個範例中，Jean 已授權的進階威脅防護，並且包含 Jean ATP 防網路釣魚原則已定義。 它通常採用大約 30 分鐘，才會生效跨資料中心; 新的原則因為已在此情況下通過一天，該原則應生效。|

## <a name="related-topics"></a>相關主題

[Office 365 進階威脅防護](office-365-atp.md)
  
[Office 365 的反網路釣魚保護](anti-phishing-protection.md)
  
[設定 Office 365 中的反網路釣魚原則](set-up-anti-phishing-policies.md)
  
[在 Office 365 中的 ATP 安全連結](atp-safe-links.md)
  
[設定 Office 365 中的 ATP 安全連結原則](set-up-atp-safe-links-policies.md)
  
[在 Office 365 中的 ATP 安全附件](atp-safe-attachments.md)
  
[設定 Office 365 中的 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)
  
[進階威脅防護檢視報告](view-reports-for-atp.md)
