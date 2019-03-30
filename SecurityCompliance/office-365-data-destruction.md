---
title: Office 365 資料毀損
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
description: 關於回收、 處置或損毀的 Office 365 資料中心的磁碟機和伺服器的 Microsoft 原則的概觀。
ms.openlocfilehash: fec6065434fa9fa555a057c68eca60082225652c
ms.sourcegitcommit: 1261a37c414111f869df5791548a768d853fda60
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/30/2019
ms.locfileid: "31004140"
---
# <a name="office-365-data-destruction"></a>Office 365 資料毀損

## <a name="physical-data-destruction"></a>實體資料毀損

Microsoft 的資料處理標準的原則可能會位址回收和處置的磁碟機和失敗或淘汰的伺服器。 然後再重新使用 Office 365 內任何磁碟機，Microsoft 會執行與國家標準與技術 Special Publication 800-88 （[NIST SP 800-88 指導方針媒體病毒掃描](http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-88r1.pdf)一致實體的病毒掃描程序). 在 Office 365 中的所有磁碟機都加密使用 BitLocker 磁碟區層級加密，因此實際上，NIST SP 800-88-相容清除是不必要的。 不過，它仍然會執行由 Microsoft。

無法在 Office 365 資料中心實體損毀及稽核透過 ISO 程序中使用的磁碟。 依據資產類型來決定適當的處理方式。 針對無法抹除的硬碟，Microsoft 會使用摧毀媒體毀損程序 （例如 disintegrates、 pulverizes，或 incinerates），並呈現資訊的復原無法執行。 Microsoft 也會保留毀損的所有記錄。 Microsoft 正在重新使用 Office 365 內的伺服器上執行類似的病毒掃描程序。 這些指導方針包含電子版與實體的病毒掃描。

使用實際銷毀程序所執行含有正在損毀的磁碟資料中心內的離站處置無法重複使用的磁碟機。 儲存媒體指定處置會放在安全位於每個區域資料中心的紙匣。 每個安全 bin 站台的監視可以視訊監視。 一旦處置 bin 達到大約 50%容量，網站服務小組連絡人實體安全性小組，以協調移除它。 網站服務人員然後移除處置紙匣] 底下護衛安全性長，直到它會被放置在等著資料毀損的安全的存放區。 原則和控管自己期間處置具有裝置資料的處理程序將會定期測試包括程序，確保機器核准毀損的條件。

資料毀損程序，磁碟會先清除 NIST 800-88 （如果可能的話），相容的方式，然後它放入工業碎機，實際摧毀。 Microsoft 的維護離開使用 NIST SP 800-88 一致清除/清除、 資產毀損、 加密、 準確清查、 追蹤，以及傳輸期間保護的監管鏈，資料中心資產的責任。 此程序透過關閉電路電視監視及毀損憑證發行完成時。

Microsoft 會使用資料清除單位，從[極端的通訊協定解決方案](http://www.enterprisedataerasure.com/)(EPS)。 EPS 軟體支援 NIST SP 800-88 需求清除和清除/安全清除。 之前清除或損毀，詳細目錄是由 Microsoft 資產管理員所建立。 如果廠商用於毀損，廠商所提供毀損的損毀，每個資產來驗證的資產管理員的憑證。

## <a name="virtual-data-destruction"></a>虛擬資料毀損

Microsoft 有資料處理原則和程序也解決有效的虛擬損毀的資料進行保護，以在服務中實刪除之後不當共用服務租用戶或之間正在存取資料的可能性。 會從一個租用戶中的服務中刪除的資料不存取另一個服務租用戶，即使部分或全部的相同的基礎實體儲存裝置稍後重新指派。 這是用來擴充虛擬環境的多個虛擬化及分散情形技術的效果，計算結果、 作用中刪除內每個服務租用戶 （例如[分頁清空](https://docs.microsoft.com/office365/securitycompliance/office-365-exchange-online-data-deletion#page-zeroing)），和必要的應用程式的行為媒體和應用程式的內容加密程序。