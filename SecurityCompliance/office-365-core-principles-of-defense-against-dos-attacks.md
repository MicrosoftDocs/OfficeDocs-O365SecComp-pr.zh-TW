---
title: 防禦措施來拒絕服務攻擊的 office 365 核心原則
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 如何 Microsoft 使用吸收、 偵測和減輕在其防禦拒絕服務 (DoS) 攻擊的核心原則。
ms.openlocfilehash: e313d5514e9bc493db78bebffca24a0fae4cbca7
ms.sourcegitcommit: a64af0ebd0b03e4a5e60a33e9108c44c7d74f356
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2019
ms.locfileid: "29741096"
---
# <a name="core-principles-of-defense-against-denial-of-service-attacks"></a><span data-ttu-id="1e221-103">防禦阻斷服務攻擊的核心原則</span><span class="sxs-lookup"><span data-stu-id="1e221-103">Core Principles of Defense Against Denial-of-Service Attacks</span></span>

<span data-ttu-id="1e221-p101">三個核心原則時防禦網路型 DoS 攻擊吸收、 偵測和減輕。吸收發生前偵測，並偵測減輕之前發生。吸收是 DoS 攻擊最佳的防禦。如果無法偵測到攻擊，它不能降低。但如果不能相同甚至是最小的 DoS 攻擊的命運，然後服務未將倖免於長的來偵測出攻擊。</span><span class="sxs-lookup"><span data-stu-id="1e221-p101">The three core principles when defending against network-based DoS attacks are Absorption, Detection, and Mitigation. Absorption happens before detection, and detection happens before mitigation. Absorption is the best defense against a DoS attacks. If the attack can't be detected, it can't be mitigated. But if even the smallest DoS attack can't be absorbed, then services aren't going to survive long enough for the attack to be detected.</span></span>

<span data-ttu-id="1e221-p102">當然，其通常不是經濟合適用於大多數的組織如這需要在技術和專門技術也不少投資購買必要吸收 DoS 攻擊的額外容量。這會醒目提示其中一個使用 Microsoft 雲端服務 ； 安全性優點我們服務十足規模可讓我們為我們雲端客戶強式網路防護提供符合成本效益的方式。但是我們規模即使儘管如此，還是必須有吸收、 偵測和減輕之間的平衡。若要尋找該達到負載平衡，我們研究來評估我們需要多少吸收攻擊成長率。</span><span class="sxs-lookup"><span data-stu-id="1e221-p102">Of course, it is generally not economically feasible for most organizations to purchase the excess capacity necessary to absorb DoS attacks, as this requires a considerable investment in technology and technical skills. This highlights one of the security benefits of using Microsoft cloud services; the sheer scale of our services enables us to provide strong network protection to our cloud customers in a cost-effective manner. But even at our scale, though, there must still be a balance between absorption, detection, and mitigation. To find that balance, we study an attack's growth rate to estimate how much we need to absorb.</span></span>

<span data-ttu-id="1e221-p103">偵測是 cat-and-mouse 的遊戲。您必須正比尋找新的方式人員所攻擊您或嘗試擊敗系統。偵測-> 減輕-> 偵測-> 降低、 等會無限期會繼續永久、 持續性狀態。</span><span class="sxs-lookup"><span data-stu-id="1e221-p103">Detection is a cat-and-mouse game. You must constantly look for the new ways people are attacking you or trying to defeat your systems. Detect -> Mitigate -> Detect -> Mitigate, etc., is a perpetual, persistent state that will continue indefinitely.</span></span>

## <a name="defending-against-dos-attacks"></a><span data-ttu-id="1e221-116">防禦 DoS 攻擊</span><span class="sxs-lookup"><span data-stu-id="1e221-116">Defending Against DoS Attacks</span></span>

<span data-ttu-id="1e221-p104">若要成功防禦 DoS 攻擊，早期偵測是基本。由之前系統超過負荷偵測攻擊、 防禦者可執行回應計畫。</span><span class="sxs-lookup"><span data-stu-id="1e221-p104">To successfully defend against a DoS attack, early detection is essential. By detecting an attack before the system is overwhelmed, defenders can execute a response plan.</span></span>

<span data-ttu-id="1e221-119">下列公式可協助大約時間 DoS 攻擊的影響：</span><span class="sxs-lookup"><span data-stu-id="1e221-119">The following formula will help approximate the time to impact of a DoS attack:</span></span>

   <span data-ttu-id="1e221-120">**最大容量 （以位元組/秒） / 成長速率 （以位元組/秒） = 影響的時間 （以位元組/秒）**</span><span class="sxs-lookup"><span data-stu-id="1e221-120">**Maximum Capacity (in bytes/sec) / Growth Rate (in bytes/sec) = Time to Impact (in bytes/sec)**</span></span>

<span data-ttu-id="1e221-p105">如果時間-影響之後再很有可能發生的來偵測時間 DoS 攻擊將會成功。如果要偵測時間發生前次-影響，然後遭受攻擊的服務應該要保留線上和可以存取，如果減輕策略都使用。即得出有可執行以抵禦 DoS 攻擊的只有兩件事：</span><span class="sxs-lookup"><span data-stu-id="1e221-p105">If the time-to-detection occurs after time-to-impact, then it is likely the DoS attack will be successful. If the time-to-detection occurs before time-to-impact, then the services being attacked should remain online and accessible, if mitigation strategies are used. Thus, there are only two things that can be done to defend against DoS attacks:</span></span>
- <span data-ttu-id="1e221-124">若要引發的最大容量 （以提供更多時間來偵測攻擊）; ceiling 增加容量或</span><span class="sxs-lookup"><span data-stu-id="1e221-124">Increase capacity to raise the ceiling of maximum capacity (which in turn provides more time to detect an attack); or</span></span>
- <span data-ttu-id="1e221-125">減少偵測的時間。</span><span class="sxs-lookup"><span data-stu-id="1e221-125">Decrease the time to detect.</span></span>

<span data-ttu-id="1e221-p106">增加容量有直接的會計影響。Microsoft 建議客戶開發至少基本吸收容量，以確保它們可倖免於 DoS 攻擊的一些層級。由於每個客戶具備的曝光度、 風險及財務 outlay 自己臨界值而異客戶客戶、 實際吸收容量。最終，基於經濟原因投資研究 （英文） 與以減少時間來偵測方式的時間通常是最符合成本效益的防禦。</span><span class="sxs-lookup"><span data-stu-id="1e221-p106">Increasing capacity has a direct fiscal impact. Microsoft recommends that customers develop at least basic absorption capacity, to ensure that they can survive some level of DoS attack. The actual absorption capacity will vary from customer to customer, as each customer has their own thresholds for exposure, risk, and financial outlay. Ultimately, for economic reasons, investments of research and time in ways to decrease time-to-detection are usually the most cost-effective defense.</span></span>
