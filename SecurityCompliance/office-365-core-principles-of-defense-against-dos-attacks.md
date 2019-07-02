---
title: Office 365 防禦拒絕服務攻擊的核心原則
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
description: Microsoft 如何在防禦拒絕服務 (DoS) 攻擊的情況下, 利用吸收、偵測和緩解的核心原則。
ms.openlocfilehash: 48ed52b496a3288d62b0f0c434fe18df8e1ff44b
ms.sourcegitcommit: aa60a6cdf83c67576e858668d1182cd4fffeb5e0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2019
ms.locfileid: "33622293"
---
# <a name="core-principles-of-defense-against-denial-of-service-attacks"></a>防禦拒絕服務攻擊的核心原則

防禦網路型 DoS 攻擊時, 三個核心原則是吸收、偵測和緩解。 在偵測之前會發生吸收, 並在緩解之前進行偵測。 [吸收] 是對 DoS 攻擊的最佳防護。 如果無法偵測到攻擊, 則無法緩解攻擊。 但是, 如果您無法吸收最小的 DoS 攻擊, 則服務的持續時間可能不足, 無法偵測到攻擊。

大部分組織都無法購買大量的容量來吸收 DoS 攻擊, 因為這需要大量的技術和技術技能投資。 這會強調使用 Microsoft 雲端服務的其中一項安全性優勢。 Microsoft 服務的巨大規模會以經濟划算的方式, 為雲端客戶提供強大的網路保護。 即使是大規模, 也必須在吸收、偵測和緩解之間取得平衡。 若要找出這種平衡, Microsoft 會研究攻擊的成長率, 以估計 Microsoft 需要吸收多少內容。

偵測是一種 cat 和滑鼠遊戲。 您必須持續尋找新的使用者受到攻擊的方式, 並嘗試擊敗您的系統。 偵測-> 緩解-> 偵測-> 緩解, 等等, 是永久且持久的狀態, 會無限期繼續。

## <a name="defending-against-dos-attacks"></a>防禦 DoS 攻擊

若要順利防禦 DoS 攻擊, 及早偵測是很重要的。 在系統不足的情況下偵測攻擊, defenders 可以執行回應計畫。

下列公式可協助接近 DoS 攻擊的影響時間:

   **容量上限 (位元組/秒)/增長率 (以位元組/秒為單位) = 影響時間 (位元組/秒)**

如果在影響時間後發生時間偵測, 則 DoS 攻擊可能會成功。 如果在影響時間之前發生偵測時間, 則受攻擊的服務應該保持線上, 且在使用緩解策略時可供存取。 因此, 有兩個方法可以防範 DoS 攻擊:

- 增加容量以提升最大容量的上限 (進而提供更多時間來偵測攻擊);等於
- 減少偵測的時間。

增加容量會對直接會計產生影響。 Microsoft 建議客戶至少開發基本的最大容量, 以確保其能經受一定層級的 DoS 攻擊。 實際的吸收容量因客戶而異, 因為每個客戶都有自己的暴露、風險和財務 outlay 的臨界值。 基於經濟原因, 在研究和時間減少偵測偵測的方法, 通常是最具成本效益的防護。
