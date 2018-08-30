---
title: 防禦與 Office 365 中的拒絕服務攻擊
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Overview of 拒絕服務 (DoS) 攻擊。
ms.openlocfilehash: b5a51ae332b32142d9ab993a29763b2160c3ce97
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526146"
---
# <a name="defending-against-denial-of-service-attacks-in-office-365"></a>防禦與 Office 365 中的拒絕服務攻擊

## <a name="introduction"></a>簡介
Microsoft 提供超過 200 雲端服務，包括 Microsoft Azure、 Microsoft Bing、 Microsoft Office 365、 Microsoft Dynamics 365、 Microsoft OneDrive、 Skype、 和 Xbox Live 我們全域雲端中主控值得信任基礎的結構基礎結構的 100 個以上的資料中心。

為有重大的網際網路平台服務與許多重點的網際網路內容提供雲端服務的全域組織、 Microsoft 是駭客及其他惡意個人的大型、 常見目標。網路-用戶端與 Microsoft Cloud-之間的通訊層是其中一個惡意攻擊的最大目標。事實上，許多年度的 Microsoft 已持續並持續某些形式的網路型 cyberattack 下。在幾乎所有的時間，其中至少一個 Microsoft 的網際網路屬性發生某些形式的攻擊。沒有可防禦這些攻擊的可靠並持續性減輕系統、 Microsoft 雲端服務就是離線和客戶無法使用。

Microsoft 使用深入防禦安全性原則來保護其雲端服務及網路。 

## <a name="definition-and-symptoms-of-denial-of-service-attacks"></a>定義和拒絕服務攻擊的症狀
攻擊網路服務的其中一個方法是建立對服務的主機許多要求會使不勝負荷的網路和以拒絕合法的使用者服務的伺服器。這被稱為拒絕服務 (DoS) 攻擊。當攻擊由多個動作項目、 端點及/或向量執行時，它會稱為分散式的拒絕服務 (DDoS) 攻擊。雖然表示、 動機和目標而異，DoS 與 DDoS 攻擊通常包含人員或人員致力於防止網際網路網站或服務正常運作或在 all、 暫時或無限期。

[美國電腦緊急整備小組](https://www.us-cert.gov/)(US CERT) 會定義要包含的 DoS 攻擊的徵狀：
- 就慢速網路效能 (時開啟的檔案或存取網際網路網站)
- 期間無法使用的網站
- 無法存取網站
- 大幅增加接收的垃圾郵件
- 中斷連線的無線或有線網際網路連線
- 長期遺失的網站或任何網際網路服務的存取權

## <a name="related-topics"></a>相關主題
- [防禦阻斷服務攻擊的核心原則](office-365-core-principles-of-defense-against-dos-attacks.md)
- [Microsoft 的拒絕服務防禦策略](office-365-microsoft-dos-defense-strategy.md)
- [防禦抵禦拒絕服務攻擊的 Microsoft 雲端服務](office-365-defending-cloud-services-against-dos-attacks.md)
