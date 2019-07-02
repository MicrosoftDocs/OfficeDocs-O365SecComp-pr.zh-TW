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
# <a name="core-principles-of-defense-against-denial-of-service-attacks"></a><span data-ttu-id="36b93-103">防禦拒絕服務攻擊的核心原則</span><span class="sxs-lookup"><span data-stu-id="36b93-103">Core Principles of Defense Against Denial-of-Service Attacks</span></span>

<span data-ttu-id="36b93-104">防禦網路型 DoS 攻擊時, 三個核心原則是吸收、偵測和緩解。</span><span class="sxs-lookup"><span data-stu-id="36b93-104">The three core principles when defending against network-based DoS attacks are Absorption, Detection, and Mitigation.</span></span> <span data-ttu-id="36b93-105">在偵測之前會發生吸收, 並在緩解之前進行偵測。</span><span class="sxs-lookup"><span data-stu-id="36b93-105">Absorption happens before detection, and detection happens before mitigation.</span></span> <span data-ttu-id="36b93-106">[吸收] 是對 DoS 攻擊的最佳防護。</span><span class="sxs-lookup"><span data-stu-id="36b93-106">Absorption is the best defense against a DoS attack.</span></span> <span data-ttu-id="36b93-107">如果無法偵測到攻擊, 則無法緩解攻擊。</span><span class="sxs-lookup"><span data-stu-id="36b93-107">If the attack can't be detected, it can't be mitigated.</span></span> <span data-ttu-id="36b93-108">但是, 如果您無法吸收最小的 DoS 攻擊, 則服務的持續時間可能不足, 無法偵測到攻擊。</span><span class="sxs-lookup"><span data-stu-id="36b93-108">But if even the smallest DoS attack can't be absorbed, then services aren't going to survive long enough for the attack to be detected.</span></span>

<span data-ttu-id="36b93-109">大部分組織都無法購買大量的容量來吸收 DoS 攻擊, 因為這需要大量的技術和技術技能投資。</span><span class="sxs-lookup"><span data-stu-id="36b93-109">It is not economically feasible for most organizations to purchase excess capacity to absorb DoS attacks, as this requires a considerable investment in technology and technical skills.</span></span> <span data-ttu-id="36b93-110">這會強調使用 Microsoft 雲端服務的其中一項安全性優勢。</span><span class="sxs-lookup"><span data-stu-id="36b93-110">This highlights one of the security benefits of using Microsoft cloud services.</span></span> <span data-ttu-id="36b93-111">Microsoft 服務的巨大規模會以經濟划算的方式, 為雲端客戶提供強大的網路保護。</span><span class="sxs-lookup"><span data-stu-id="36b93-111">The sheer scale of Microsoft services provides strong network protection to cloud customers in a cost-effective manner.</span></span> <span data-ttu-id="36b93-112">即使是大規模, 也必須在吸收、偵測和緩解之間取得平衡。</span><span class="sxs-lookup"><span data-stu-id="36b93-112">But even at a large scale, there must be a balance between absorption, detection, and mitigation.</span></span> <span data-ttu-id="36b93-113">若要找出這種平衡, Microsoft 會研究攻擊的成長率, 以估計 Microsoft 需要吸收多少內容。</span><span class="sxs-lookup"><span data-stu-id="36b93-113">To find that balance, Microsoft studies attack growth rates to estimate how much Microsoft needs to absorb.</span></span>

<span data-ttu-id="36b93-114">偵測是一種 cat 和滑鼠遊戲。</span><span class="sxs-lookup"><span data-stu-id="36b93-114">Detection is a cat-and-mouse game.</span></span> <span data-ttu-id="36b93-115">您必須持續尋找新的使用者受到攻擊的方式, 並嘗試擊敗您的系統。</span><span class="sxs-lookup"><span data-stu-id="36b93-115">You must constantly look for new ways people are attack and try to defeat your systems.</span></span> <span data-ttu-id="36b93-116">偵測-> 緩解-> 偵測-> 緩解, 等等, 是永久且持久的狀態, 會無限期繼續。</span><span class="sxs-lookup"><span data-stu-id="36b93-116">Detect -> Mitigate -> Detect -> Mitigate, etc., is a perpetual, persistent state that continues indefinitely.</span></span>

## <a name="defending-against-dos-attacks"></a><span data-ttu-id="36b93-117">防禦 DoS 攻擊</span><span class="sxs-lookup"><span data-stu-id="36b93-117">Defending Against DoS Attacks</span></span>

<span data-ttu-id="36b93-118">若要順利防禦 DoS 攻擊, 及早偵測是很重要的。</span><span class="sxs-lookup"><span data-stu-id="36b93-118">To successfully defend against a DoS attack, early detection is essential.</span></span> <span data-ttu-id="36b93-119">在系統不足的情況下偵測攻擊, defenders 可以執行回應計畫。</span><span class="sxs-lookup"><span data-stu-id="36b93-119">By detecting an attack before the system is overwhelmed, defenders can execute a response plan.</span></span>

<span data-ttu-id="36b93-120">下列公式可協助接近 DoS 攻擊的影響時間:</span><span class="sxs-lookup"><span data-stu-id="36b93-120">The following formula helps approximate the time to impact of a DoS attack:</span></span>

   <span data-ttu-id="36b93-121">**容量上限 (位元組/秒)/增長率 (以位元組/秒為單位) = 影響時間 (位元組/秒)**</span><span class="sxs-lookup"><span data-stu-id="36b93-121">**Maximum Capacity (in bytes/sec) / Growth Rate (in bytes/sec) = Time to Impact (in bytes/sec)**</span></span>

<span data-ttu-id="36b93-122">如果在影響時間後發生時間偵測, 則 DoS 攻擊可能會成功。</span><span class="sxs-lookup"><span data-stu-id="36b93-122">If the time-to-detection occurs after time-to-impact, it is likely the DoS attack will be successful.</span></span> <span data-ttu-id="36b93-123">如果在影響時間之前發生偵測時間, 則受攻擊的服務應該保持線上, 且在使用緩解策略時可供存取。</span><span class="sxs-lookup"><span data-stu-id="36b93-123">If the time-to-detection occurs before time-to-impact, the attacked services should remain online and accessible if mitigation strategies are used.</span></span> <span data-ttu-id="36b93-124">因此, 有兩個方法可以防範 DoS 攻擊:</span><span class="sxs-lookup"><span data-stu-id="36b93-124">Thus, there are only two things that can be done to defend against DoS attacks:</span></span>

- <span data-ttu-id="36b93-125">增加容量以提升最大容量的上限 (進而提供更多時間來偵測攻擊);等於</span><span class="sxs-lookup"><span data-stu-id="36b93-125">Increase capacity to raise the ceiling of maximum capacity (which in turn provides more time to detect an attack); or</span></span>
- <span data-ttu-id="36b93-126">減少偵測的時間。</span><span class="sxs-lookup"><span data-stu-id="36b93-126">Decrease the time to detect.</span></span>

<span data-ttu-id="36b93-127">增加容量會對直接會計產生影響。</span><span class="sxs-lookup"><span data-stu-id="36b93-127">Increasing capacity has a direct fiscal impact.</span></span> <span data-ttu-id="36b93-128">Microsoft 建議客戶至少開發基本的最大容量, 以確保其能經受一定層級的 DoS 攻擊。</span><span class="sxs-lookup"><span data-stu-id="36b93-128">Microsoft recommends that customers develop at least basic absorption capacity to ensure that they can survive some level of DoS attack.</span></span> <span data-ttu-id="36b93-129">實際的吸收容量因客戶而異, 因為每個客戶都有自己的暴露、風險和財務 outlay 的臨界值。</span><span class="sxs-lookup"><span data-stu-id="36b93-129">The actual absorption capacity varies from customer to customer, as each customer has their own thresholds for exposure, risk, and financial outlay.</span></span> <span data-ttu-id="36b93-130">基於經濟原因, 在研究和時間減少偵測偵測的方法, 通常是最具成本效益的防護。</span><span class="sxs-lookup"><span data-stu-id="36b93-130">For economic reasons, investments in research and time for ways to decrease time-to-detection are usually the most cost-effective defense.</span></span>
