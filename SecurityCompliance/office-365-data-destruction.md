---
title: Office 365 資料銷毀
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
description: 關於 Office 365 資料中心磁片磁碟機和伺服器之回收、處置或銷毀的 Microsoft 原則。
ms.openlocfilehash: d94a4ff5f240bfbfcd690e6247869f0edc88059f
ms.sourcegitcommit: aa60a6cdf83c67576e858668d1182cd4fffeb5e0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2019
ms.locfileid: "33622243"
---
# <a name="office-365-data-destruction"></a>Office 365 資料銷毀

## <a name="physical-data-destruction"></a>實體資料銷毀

Microsoft 有資料處理標準原則, 可解決磁片磁碟機的回收和處置, 以及失敗或淘汰伺服器的情況。 在重複使用任何 Office 365 磁片磁碟機之前, Microsoft 會執行實際的淨化程式, 與國家標準和技術特別發行的出版物 800-88 ([NIST SP 800-88 準則進行媒體淨化](http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-88r1.pdf)) 一致。 由於 Office 365 中的所有磁片磁碟機都是使用 BitLocker 大量層級加密進行加密, 因此在技術上不需要使用 NIST SP 800-88 相容性的擦除。 不過, Microsoft 會執行此程式。

在 Office 365 資料中心內使用的失敗磁片會受到 ISO 處理常式的實際損毀和審核。 資產類型決定適當的處置方法。 對於無法清除的硬碟, Microsoft 會使用析構程式來銷毀媒體, 並不可能的復原資訊。 例如, 磁片實際被損毀、pulverized 或 incinerated。 Microsoft 會保留所有銷毀記錄, 並在 Office 365 內重複使用的伺服器上執行類似的淨化程式。 這些指導方針包含電子和實體的淨化。

每個資料中心都使用內部網站實際銷毀程式來處理其磁片。 針對磁片處理所指定之儲存介質的安全箱位於資料中心的每個區域。 每個安全的 bin 工作站都有視頻監控監控。 一旦釋放的空間約達 50%, 網站服務小組就會與實體安全小組聯絡, 以協調移除。 網站服務人員和安全性辦公室會移除安全處置 bin, 並將它放在指定的安全儲存區中。 在處置期間, 管理對貼裝置之資料處理的原則和程式會進行例行測試, 包括確保已核准受破壞之機器狀況的程式。

在資料析構程式中, 會以符合 NIST 800-88 (如果可能) 的方式清除磁片, 然後將其置於工業碎和實際 demolished。 Microsoft 為離開資料中心的資產提供責任, 使其成為使用 NIST SP 800-88 一致的清理/清除、資產銷毀、加密、正確清查、追蹤, 以及保護在傳輸期間的保管環節。 此程式是透過封閉電視來監視, 並在完成時發出銷毀憑證。

Microsoft 會使用來自[極端通訊協定解決方案](http://www.enterprisedataerasure.com/)(EPS) 的資料擦除單位。 EPS 軟體支援用於清理和清除/安全擦除的 NIST SP 800-88 需求。 在清理或銷毀之前, 會由 Microsoft 資產管理員建立清查。 如果供應商用於損毀, 則廠商會針對銷毀的每個資產 (由資產管理員驗證), 提供損毀憑證。

## <a name="virtual-data-destruction"></a>虛擬資料銷毀

Microsoft 具有資料處理原則和程式, 可解決資料的有效虛擬銷毀, 以防止在服務租使用者之間不正當的資料共用, 或在服務中實刪除後可供存取。 從一個租使用者中的服務刪除的資料無法存取其他服務租使用者, 即使有任何基礎實體儲存重新指派時也是如此。 這是多重虛擬化和分散技術用來擴充虛擬環境的複合效果, 以及每個服務租使用者 (例如[頁面清空](https://docs.microsoft.com/office365/securitycompliance/office-365-exchange-online-data-deletion#page-zeroing)) 中應用程式的使用中刪除行為, 以及所需的結果。媒體和應用程式內容加密程式。