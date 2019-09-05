---
title: 防禦 Office 365 中的拒絕服務攻擊
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
description: 拒絕服務 (DoS) 攻擊的概觀。
ms.openlocfilehash: 94f87a11f396cb8ef09fd6d670d73ba8d1e88eda
ms.sourcegitcommit: 4a2bde56178609e75c1ad7ecad2db5e049fc0c45
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/05/2019
ms.locfileid: "36761659"
---
# <a name="defend-against-denial-of-service-attacks-in-office-365"></a>防禦 Office 365 中的拒絕服務攻擊

## <a name="introduction"></a>簡介

Microsoft 會傳遞 200 位以上的雲端服務中的全域雲端基礎結構的 100 個以上的資料中心主控高可信度電腦基礎結構。 這些包括：

- Microsoft Azure
- Microsoft Bing
- Microsoft Dynamics 365
- Microsoft Office 365
- Microsoft OneDrive
- Skype
- Xbox Live

重大的網際網路平台服務與許多顯著的網際網路內容提供雲端服務的全球組織，Microsoft 是駭客及其他惡意個人的大型、 常見目標。 用戶端與 Microsoft 雲端之間的網路通訊層是下列其中一個惡意攻擊的最大目標。 事實上，Microsoft 會持續和持續在某種形式的網路型 cyberattack 下。 內嵌，Microsoft 會使用深度防禦安全性原則來保護其雲端服務及網路。 防禦這些攻擊的可靠和持續性降低系統，而 Microsoft 雲端服務就是離線，讓客戶無法使用。

## <a name="definition-and-symptoms-of-denial-of-service-attacks"></a>定義和拒絕服務攻擊的徵狀

網路服務來進行攻擊的一種方式是建立許多要求對服務主機壓制網路和拒絕合法的使用者提供服務的伺服器。 這稱為拒絕服務 (DoS) 攻擊。 藉由多個動作項目、 端點] 及/或向量執行攻擊時，它被稱為分散式的拒絕服務 (DDoS) 攻擊。 雖然表示、 動機和目標而有所不同，DoS 和 DDoS 攻擊通常包含以防止網際網路網站或服務無法正確運作，或在所有，暫時或無限期的努力。

[美國電腦緊急整備小組](https://www.us-cert.gov/)(US CERT) 會定義要包含的 DoS 攻擊的徵狀：

- 特別慢速網路效能 (時開啟的檔案或存取的網際網路網站)
- 二者皆無法使用的網站
- 無法存取的網站
- 大幅增加接收到的垃圾郵件
- 中斷連線的無線或有線的網際網路連線
- 長期遺失的網頁或任何網際網路服務的存取權

## <a name="related-topics"></a>相關主題

- [防禦阻斷服務攻擊的核心原則](office-365-core-principles-of-defense-against-dos-attacks.md)
- [Microsoft 的拒絕服務攻擊防禦策略](office-365-microsoft-dos-defense-strategy.md)
- [防禦拒絕服務攻擊的 Microsoft 雲端服務](office-365-defending-cloud-services-against-dos-attacks.md)
