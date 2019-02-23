---
title: Office 365 資料毀損
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Microsoft 的原則有關的回收、 處置或損毀的 Office 365 datacenter 磁碟機與伺服器的概觀。
ms.openlocfilehash: 6b9f6bacfa1c3bf5ee6c8cb76bc5a394812b49be
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220783"
---
# <a name="office-365-data-destruction"></a>Office 365 資料毀損

## <a name="physical-data-destruction"></a>實體資料毀損

Microsoft 有位址回收和處置磁碟機和失敗或淘汰伺服器的資料處理標準原則。然後再重新使用 Office 365 內任何磁碟機，Microsoft 會執行與國際標準協會和技術特殊出版物 800-88 （[NIST SP 800-88 的指導方針媒體病毒掃描](http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-88r1.pdf)一致的實體的病毒掃描程序).Office 365 中的所有磁碟機都加密使用 BitLocker 磁碟區層級加密，因此作法是在 NIST SP 800-88-相容清除沒有必要。儘管如此，它仍然被執行 microsoft。

無法實際移除和稽核 ISO 程序透過資料中心的 Office 365 中使用的磁碟。資產類型取決於處置適當方法。無法多次的硬碟，Microsoft 使用終結媒體此解構程序 （例如 disintegrates、 pulverizes，或 incinerates） 並呈現資訊的復原之前。Microsoft 也會保留所有記錄的損毀。Microsoft 均已重新使用 Office 365 中的伺服器上執行類似的病毒掃描程序。這些指導方針包含電子版與實體的病毒掃描。

不能重複使用的磁碟機都會予以處置所執行含有正在終結磁碟的資料中心內的離站實際銷毀程序。指定的處置的儲存媒體會放在安全筒位於每個區域中的資料中心中。每個安全的紙匣總機監視的視訊監視。一旦處置筒到達大約 50%容量、 網站服務小組連絡人的實體安全性小組協調其移除。直到它會處於著資料毀損的安全的儲存區域網站服務人員則會移除下護衛安全主管處置紙匣。原則和管理資料並且裝置具有處置期間的處理程序會定期測試包括程序，以確保機器解構已核准的條件。

資料解構程序中的方式來使用 NIST 800-88 （請盡可能） 相容先清除磁碟，然後它會放入業界碎機和實體摧毀。Microsoft 維護資產離開使用 NIST SP 800 88 一致清除/清除、 資產解構、 加密、 正確清查、 追蹤及傳輸期間的一連串的監督保護的資料中心的責任。此程序透過關閉電路電視監視和解構憑證發出完成時。

Microsoft 會使用資料清除單位從[超重度通訊協定解決方案](http://www.enterprisedataerasure.com/)(EPS)。EPS 軟體支援 NIST SP 800 88 需求清除與清除/安全清除。在清除或解構存貨會建立 Microsoft 資產管理員。如果解構使用廠商，則廠商提供的解構終結，每個資產的資產管理員已驗證的憑證。

## <a name="virtual-data-destruction"></a>虛擬資料毀損

Microsoft 已處理的原則與也地址的資料以防止資料在服務中的硬碟刪除之後不當共用服務租用戶或之間所存取的可能性有效虛擬解構的程序的資料。即使某些或所有相同的基礎實體儲存裝置稍後重新指派不可以存取至另一個服務租用戶從一個租用戶中的服務已刪除的資料。這是用來擴充虛擬環境的多個虛擬化及分散技術的計算效果結果、 作用中刪除的應用程式 （例如[分頁清空](https://docs.microsoft.com/office365/securitycompliance/office-365-exchange-online-data-deletion#page-zeroing)），每個服務租用戶和必要的行為媒體及應用程式內容加密程序。