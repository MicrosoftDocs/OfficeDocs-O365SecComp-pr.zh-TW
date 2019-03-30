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
description: 如何使用 Microsoft 利用吸收、 偵測和補救中其防禦拒絕服務 (DoS) 攻擊的核心原則。
ms.openlocfilehash: bbfffeaeb66fc83e80c274be9550a95dc8bd3f0d
ms.sourcegitcommit: 1261a37c414111f869df5791548a768d853fda60
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/30/2019
ms.locfileid: "31004100"
---
# <a name="core-principles-of-defense-against-denial-of-service-attacks"></a>防禦阻斷服務攻擊的核心原則

三個核心原則時防禦網路型 DoS 攻擊吸收、 偵測和補救。
吸收會發生情況之前偵測，以及偵測緩和措施之前發生。 吸收是 DoS 攻擊的最佳防範。 如果無法偵測到的攻擊，它不能降低。 但是，如果無法相同甚至是最小的 DoS 攻擊的命運，然後服務不會學到承受長，才能偵測到攻擊。

當然，其通常不是經濟可行的情況下用於大多數的組織購買必要吸收 DoS 攻擊的寬幅容量，因為這需要相當長的投資的技術和專門技術。 這會將下列其中一個安全性優點使用 Microsoft 雲端服務; 醒目提示真正的縮放比例，我們的服務可讓我們於我們雲端的客戶提供強式網路保護，以符合成本效益的方式。 但是，即使在我們的刻度，不過，仍必須有吸收、 偵測和補救之間取得平衡。 若要尋找的平衡，我們研究來估計我們需要多少吸收攻擊的成長率。

偵測是 cat-and-mouse 遊戲。 您必須經常尋找新的方式人員會攻擊您或嘗試擊敗您的系統。 偵測-> 減輕-> 偵測-> 降低等是永久、 持續的狀態，將會無限期繼續。

## <a name="defending-against-dos-attacks"></a>防禦拒絕服務攻擊

成功，以防範 DoS 攻擊，早期偵測是不可或缺的。 藉由之前淹沒了系統偵測攻擊，防禦者可以執行回應計畫。

下列公式可協助大約時間 DoS 攻擊的影響：

   **最大容量 （以位元組/秒） / 成長率 （以位元組/秒） = 影響時間 （以位元組/秒）**

若要偵測的時間就會發生時間的影響之後，則很可能 DoS 攻擊將會成功。 如果要偵測時間發生之前的時間的影響，然後應保持遭受攻擊的服務，線上和可以存取，如果使用緩和措施策略。 因此，有可執行以抵禦拒絕服務攻擊的只有兩件事：
- 若要引發的最大容量 （可輪流提供更多時間來偵測攻擊）; ceiling 增加容量或
- 減少偵測的時間。

增加容量有直接的會計影響。 Microsoft 建議的客戶開發至少基本吸收容量，以確保它們可以承受某種程度的 DoS 攻擊。 為每個客戶有自己的曝光度、 風險和財務 outlay 閾值而異客戶，實際吸收容量。 最後，基於經濟原因，投資之上的研究和時間的方式來減少時間-偵測通常是最符合成本效益的措施。
