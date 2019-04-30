---
title: Microsoft Compliance Manager 版本資訊
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft Compliance Manager 是在 Microsoft 服務信任入口網站中的可用工作流程為基礎的風險評估工具。 合規性管理員可讓您追蹤、 指派及驗證與 Microsoft 雲端服務相關的法規合規性活動。
ms.openlocfilehash: 5e18445e3f9ad2848f18174788ec6dd40bc4a178
ms.sourcegitcommit: 696c1ed6b270be3f9da7395b49a7d8fec98e6db0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2019
ms.locfileid: "33473038"
---
# <a name="release-notes-for-compliance-manager-preview"></a>版本資訊的合規性管理員 （預覽）

公開預覽的合規性管理員為您提供搶先即將推出的功能和更新。

您可以使用[服務信任入口網站](https://servicetrust.microsoft.com)上更新的[合規性管理員](https://servicetrust.microsoft.com/ComplianceManager)」 來追蹤、 指派，並確認與 Microsoft 雲端服務相關的法規合規性活動。

## <a name="whats-new-in-compliance-manager-preview"></a>What's new 合規性管理員中 （預覽）

- **整合與 Microsoft 安全分數：** 合規性管理員可藉由將客戶管理動作對應到超過 50 個安全分數動作支援與[Microsoft 安全分數](microsoft-secure-score.md)的整合。 當您完成安全分數對應巨集指令時，會自動更新對應的合規性管理員動作。

- **匯入自訂的 「 評估 」:** 除了內建的評估，合規性管理員現在可支援匯入自訂的範本，讓您可以建立自訂的 「 評估 」 的任何產品或服務以及任何標準或法規。

- **動作項目：** 動作項目現在的個別項目，而且許多包括來自 Microsoft 安全分數 Graph API 的遙測集合。 請儘可能技術巨集指令建議現在有適用的設定] 頁面上的連結 Office 365 服務中。

- **租用戶管理：** 管理新的資料元素合規性管理員中 （預覽） 的新介面：
    - **維度：** 檢視、 新增並自訂的中繼資料的範本、 評估以及動作項目，可讓您建立自訂的樞紐分析表的篩選器。
    - **擁有者：** 指定每個動作項目擁有者。
    - **客戶動作：** 管理動作項目包含在合規性管理員 （預覽） 的完整清單，並啟用/停用安全分數監控整合在一起安全分數的動作項目。

- **更新合規性分數**： 方法具有變更以支援透過 Microsoft 安全分數進行同步處理。 計分系統會移除 Microsoft 管理控制項信用額度，並完全著重完成的客戶管理控制措施。

## <a name="known-issues-in-compliance-manager-preview"></a>已知的問題合規性管理員中 （預覽）

下列各節討論在即將發行的合規性管理員中解析的已知的問題。

### <a name="compliance-score"></a>合規性分數

- 時的動作項目都標示為**不在範圍中**，指派動作項目，分數不是排除合規性分數計算。 標示為**不在範圍中**的動作項目應該不會增加您的合規性分數。

### <a name="microsoft-managed-controls"></a>Microsoft 管理控制措施

- Microsoft 管理控制措施的測試日期不會出現在 UI 中，即使納入評估。 若要查看測試日期的詳細資訊，您必須先匯出評估。

### <a name="customization"></a>自訂

- 新增自訂控制項可讓將新的控制項新增至現有的控制項系列，但不允許您將新增新的控制項系列。
- 此版本不支援連結動作項目新增動作項目或評估控制項。
- 如果您建立的自訂動作，您無法編輯或刪除它。

### <a name="control-families-not-shown-in-assessments"></a>不會顯示在 「 評估 」 控制項系列

- 當您匯入範本時，所有評估都根據範本會反映是範本的一部份的所有控制項系列。 但是，如果您新增至範本的新控制項系列，任何現有 「 評估 」 不會反映所做的變更。 僅限關閉更新的範本建立新的評估會反映所做的變更。

### <a name="filters"></a>篩選

- 篩選動作項目或控制項時，不一致地產生正確的結果。

### <a name="templates"></a>範本

- 封存的範本可編輯，而且它們不應該是可編輯。
- 當他們不應該評估建立允許鎖定的範本。 鎖定範本是用來防止其被用來建立評估。

### <a name="export"></a>匯出

- 範本匯出至 JSON 失敗時的範本狀態設為**匯入**或**擱置中的核准**。

### <a name="supported-browsers"></a>支援的瀏覽器

- 支援最新版的 Microsoft Edge、 Chrome 和 Safari。
- 可能會有更新的資料不會在重新整理瀏覽器直到出現的執行個體。
- Microsoft Edge 的預覽版本不支援，但有任何已知的問題。
- 不支援 Internet Explorer。

### <a name="session-timeout"></a>工作階段逾時

- 當工作階段逾時，可能會出現 「 發生錯誤 」 錯誤。 若要解決，移至[合規性管理員中](https://servicetrust.microsoft.com/ComplianceManager)，並再次登入。