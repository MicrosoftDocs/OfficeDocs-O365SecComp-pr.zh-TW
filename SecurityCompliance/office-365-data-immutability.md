---
title: Office 365 資料永久性
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 定義及說明 Office 365 中的資料永久性。
ms.openlocfilehash: bc9805be446ad1d696e20a4bee6e449b311970fe
ms.sourcegitcommit: aa60a6cdf83c67576e858668d1182cd4fffeb5e0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2019
ms.locfileid: "33622443"
---
# <a name="immutability-in-office-365"></a>Office 365 中的不變性

法規遵循、內部控管需求或訴訟風險需要組織, 才能在可探索的表單中保留電子郵件和相關聯的資料。 系統中的所有資料都必須可供搜尋, 且無法銷毀或變更。 這是業界標準的詞彙。

傳統的不可變性方法通常是透過將電子郵件移至個別、唯讀的儲存位置來運作。 雖然這類系統會服務保留信箱專案進行探索, 但通常會因從習慣的每日工作流程移除保留的專案而影響使用者經驗。 針對 IT 專業人員, 這個不間斷的方法需要部署和持續維護個別的伺服器和儲存基礎結構。 探索是以郵件系統外部的工具來執行, 並包含相關聯的部署和維護成本。

透過就地保留和保留原則功能, 在 Office 365 和其服務中, 您可以保留和保留許多類別的內送、內部及外寄資料。 這包括:

- 輸入和輸出電子郵件通訊
- 包含在電子郵件表單或共用的線上檔中的書籍和記錄
- 會議邀請
- 傳真
- 立即訊息
- 線上會議期間共用的檔
- 語音信箱

此外, Microsoft 已開發附加元件功能, 以允許透過與協力廠商資料捕獲和管理解決方案的整合, 從其他來源封存[資料](https://support.office.com/article/Archiving-third-party-data-in-Office-365-0ce338d5-3666-4a18-86ab-c6910ff408cc)。 匯入協力廠商資料之後, 您可以將 Office 365 規範功能套用至資料, 包括:

- [訴訟暫止](create-a-litigation-hold.md)
- [就地 eDiscovery 和保留](manage-legal-investigations.md)
- [合規性搜尋](search-for-content.md)
- [就地封存](enable-archive-mailboxes.md)
- [信箱審核](enable-mailbox-auditing.md)
- [保留原則](retention-policies.md)

例如, 當信箱處於訴訟暫止狀態時, 會保留協力廠商資料。 您可以使用就地 eDiscovery 或符合性搜尋來搜尋協力廠商資料。 或者, 您也可以將封存和保留原則套用至協力廠商資料, 就像您可以使用 Microsoft 資料一樣。 封存 Office 365 中的協力廠商資料可協助您的組織遵守政府和法規原則。

Office 365 中的封存可提供證券和 Exchange 傭金 (SEC) 規則17a-4 相容的儲存空間。 Office 365 會使用就地保留原則和保留原則 (包括保留鎖定), 保留所有以不可改寫、不可讀寫的格式收集的資料。

特別是：

- 使用上述保留原則儲存的所有記錄會保留在一般使用者 purview 的專用儲存區中。 只有獲授權的使用者可以存取及搜尋這些記錄, 但無法變更或清除它們。
- 每個專案的中繼資料包含計算保留期間所使用的時間戳記。 當接收或建立新專案, 且無法修改或移除中繼資料時, 會套用時間戳記。
- Office 365 中的封存功能可讓使用者合併不同的保留原則和保留動作, 以建立更細微的保留原則。 這些原則會定義保留專案的類型或位置, 以及保留期間。
- 保留鎖定功能可讓使用者選擇是否要將原則設為限制性原則。 限制性原則可防止任何人能夠移除、停用或對保留原則進行任何變更。 這表示一旦啟用保留鎖定, 就無法停用, 而且不會有任何可在其下使用保留原則所收集之現有保管人的資料, 在此情況下可能會覆寫、修改、清除或刪除任何機制。保留期間。 此外, 依保留鎖定設定的保留期間可能無法縮短或減少。 不過, 在法律需求繼續保留儲存的資料時, 可能會被加長, 如上述所述。 保留鎖定可確保沒有任何人 (甚至是系統管理員或具有特定控制存取權的人) 可能會變更設定或覆寫或清除已儲存的資料, 並讓 Office 365 中的封存與 SEC 2003 版本中的指導方針相符規則17a-4。

若要瞭解 Office 365 如何協助您符合法規義務, 特別是與規則17a-4 需求有關, 請參閱此[白皮書](https://go.microsoft.com/fwlink/?linkid=830440), 涵蓋 Exchange online 封存、SharePoint Online、商務用 OneDrive 和商務用 Skype。 該白皮書也提供 Office 365 封存功能和功能的深入分析, 以依據 SEC Rule 17a-4 下的每個需求, 並示範 Office 365 封存可如何讓他們符合這些需求需要.