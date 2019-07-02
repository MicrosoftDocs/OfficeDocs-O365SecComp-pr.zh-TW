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
description: 拒絕服務 (DoS) 攻擊的概述。
ms.openlocfilehash: df3ab233271f02b91f16f8954972a61000bf4d3b
ms.sourcegitcommit: aa60a6cdf83c67576e858668d1182cd4fffeb5e0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2019
ms.locfileid: "33622473"
---
# <a name="defend-against-denial-of-service-attacks-in-office-365"></a>防禦 Office 365 中的拒絕服務攻擊

## <a name="introduction"></a>簡介

Microsoft 為超過100個資料中心的全域雲端基礎結構所主控的200雲端服務提供信任的基礎結構。 這些包括：

- Microsoft Azure
- Microsoft Bing
- Microsoft Dynamics 365
- Microsoft Office 365
- Microsoft OneDrive
- 用 skype
- Xbox Live

作為具有大量網際網路平臺的全球組織, 以及提供雲端服務的許多網路內容, Microsoft 是駭客及其他惡意人員的大型、常見的目標。 用戶端與 Microsoft 雲端之間的網路通訊層是最大的惡意攻擊目標之一。 事實上, Microsoft 會持續且永久地採用某種形式的網路網路攻擊。 根據此, Microsoft 會使用縱深防禦的安全性原則來保護其雲端服務和網路。 若沒有防禦這些攻擊的可靠和持續性緩解系統, Microsoft 的雲端服務將會離線且無法供客戶使用。

## <a name="definition-and-symptoms-of-denial-of-service-attacks"></a>拒絕服務攻擊的定義和徵兆

攻擊網路服務的一種方法, 就是建立許多對服務主機的要求, 以使網路和伺服器不會遭到合法使用者的服務。 這稱為「拒絕服務」 (DoS) 攻擊。 當由多個演員、端點和/或向量執行攻擊時, 會將其稱為分散式阻斷服務 (DDoS) 攻擊。 雖然方法、motives 和目標各不相同, 但 DoS 和 DDoS 攻擊通常是由防止網際網路網站或服務正常運作, 或暫時或無限期的努力所構成。

[美國電腦緊急就緒小組](https://www.us-cert.gov/)(美國) 會定義 DoS 攻擊的表現, 包括:

- 網路效能較慢 (開啟檔案或存取網際網路網站時)
- 網站不可用
- 無法存取網站
- 收到垃圾郵件大幅增加
- 無線或有線網際網路連線的連接
- 長期失去存取網站或任何網際網路服務的許可權

## <a name="related-topics"></a>相關主題

- [防禦阻斷服務攻擊的核心原則](office-365-core-principles-of-defense-against-dos-attacks.md)
- [Microsoft 的拒絕服務防護策略](office-365-microsoft-dos-defense-strategy.md)
- [防禦拒絕服務攻擊的 Microsoft 雲端服務](office-365-defending-cloud-services-against-dos-attacks.md)
