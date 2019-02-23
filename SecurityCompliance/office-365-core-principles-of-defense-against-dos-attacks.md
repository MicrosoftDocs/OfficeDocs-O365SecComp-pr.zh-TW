---
title: 防禦措施來拒絕服務攻擊的 office 365 核心原則
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
description: 如何 Microsoft 使用吸收、 偵測和減輕在其防禦拒絕服務 (DoS) 攻擊的核心原則。
ms.openlocfilehash: dfe179924f7414b0120697023f3daf7e6b6661b6
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216003"
---
# <a name="core-principles-of-defense-against-denial-of-service-attacks"></a>防禦阻斷服務攻擊的核心原則

三個核心原則時防禦網路型 DoS 攻擊吸收、 偵測和減輕。吸收發生前偵測，並偵測減輕之前發生。吸收是 DoS 攻擊最佳的防禦。如果無法偵測到攻擊，它不能降低。但如果不能相同甚至是最小的 DoS 攻擊的命運，然後服務未將倖免於長的來偵測出攻擊。

當然，其通常不是經濟合適用於大多數的組織如這需要在技術和專門技術也不少投資購買必要吸收 DoS 攻擊的額外容量。這會醒目提示其中一個使用 Microsoft 雲端服務 ； 安全性優點我們服務十足規模可讓我們為我們雲端客戶強式網路防護提供符合成本效益的方式。但是我們規模即使儘管如此，還是必須有吸收、 偵測和減輕之間的平衡。若要尋找該達到負載平衡，我們研究來評估我們需要多少吸收攻擊成長率。

偵測是 cat-and-mouse 的遊戲。您必須正比尋找新的方式人員所攻擊您或嘗試擊敗系統。偵測-> 減輕-> 偵測-> 降低、 等會無限期會繼續永久、 持續性狀態。

## <a name="defending-against-dos-attacks"></a>防禦 DoS 攻擊

若要成功防禦 DoS 攻擊，早期偵測是基本。由之前系統超過負荷偵測攻擊、 防禦者可執行回應計畫。

下列公式可協助大約時間 DoS 攻擊的影響：

   **最大容量 （以位元組/秒） / 成長速率 （以位元組/秒） = 影響的時間 （以位元組/秒）**

如果時間-影響之後再很有可能發生的來偵測時間 DoS 攻擊將會成功。如果要偵測時間發生前次-影響，然後遭受攻擊的服務應該要保留線上和可以存取，如果減輕策略都使用。即得出有可執行以抵禦 DoS 攻擊的只有兩件事：
- 若要引發的最大容量 （以提供更多時間來偵測攻擊）; ceiling 增加容量或
- 減少偵測的時間。

增加容量有直接的會計影響。Microsoft 建議客戶開發至少基本吸收容量，以確保它們可倖免於 DoS 攻擊的一些層級。由於每個客戶具備的曝光度、 風險及財務 outlay 自己臨界值而異客戶客戶、 實際吸收容量。最終，基於經濟原因投資研究 （英文） 與以減少時間來偵測方式的時間通常是最符合成本效益的防禦。
