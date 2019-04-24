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
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262925"
---
# <a name="core-principles-of-defense-against-denial-of-service-attacks"></a><span data-ttu-id="b7cfa-103">防禦拒絕服務攻擊的核心原則</span><span class="sxs-lookup"><span data-stu-id="b7cfa-103">Core Principles of Defense Against Denial-of-Service Attacks</span></span>

<span data-ttu-id="b7cfa-104">三個核心原則時防禦網路型 DoS 攻擊吸收、 偵測和補救。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-104">The three core principles when defending against network-based DoS attacks are Absorption, Detection, and Mitigation.</span></span>
<span data-ttu-id="b7cfa-105">吸收會發生情況之前偵測，以及偵測緩和措施之前發生。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-105">Absorption happens before detection, and detection happens before mitigation.</span></span> <span data-ttu-id="b7cfa-106">吸收是 DoS 攻擊的最佳防範。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-106">Absorption is the best defense against a DoS attacks.</span></span> <span data-ttu-id="b7cfa-107">如果無法偵測到的攻擊，它不能降低。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-107">If the attack can't be detected, it can't be mitigated.</span></span> <span data-ttu-id="b7cfa-108">但是，如果無法相同甚至是最小的 DoS 攻擊的命運，然後服務不會學到承受長，才能偵測到攻擊。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-108">But if even the smallest DoS attack can't be absorbed, then services aren't going to survive long enough for the attack to be detected.</span></span>

<span data-ttu-id="b7cfa-109">當然，其通常不是經濟可行的情況下用於大多數的組織購買必要吸收 DoS 攻擊的寬幅容量，因為這需要相當長的投資的技術和專門技術。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-109">Of course, it is generally not economically feasible for most organizations to purchase the excess capacity necessary to absorb DoS attacks, as this requires a considerable investment in technology and technical skills.</span></span> <span data-ttu-id="b7cfa-110">這會將下列其中一個安全性優點使用 Microsoft 雲端服務; 醒目提示真正的縮放比例，我們的服務可讓我們於我們雲端的客戶提供強式網路保護，以符合成本效益的方式。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-110">This highlights one of the security benefits of using Microsoft cloud services; the sheer scale of our services enables us to provide strong network protection to our cloud customers in a cost-effective manner.</span></span> <span data-ttu-id="b7cfa-111">但是，即使在我們的刻度，不過，仍必須有吸收、 偵測和補救之間取得平衡。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-111">But even at our scale, though, there must still be a balance between absorption, detection, and mitigation.</span></span> <span data-ttu-id="b7cfa-112">若要尋找的平衡，我們研究來估計我們需要多少吸收攻擊的成長率。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-112">To find that balance, we study an attack's growth rate to estimate how much we need to absorb.</span></span>

<span data-ttu-id="b7cfa-113">偵測是 cat-and-mouse 遊戲。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-113">Detection is a cat-and-mouse game.</span></span> <span data-ttu-id="b7cfa-114">您必須經常尋找新的方式人員會攻擊您或嘗試擊敗您的系統。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-114">You must constantly look for the new ways people are attacking you or trying to defeat your systems.</span></span> <span data-ttu-id="b7cfa-115">偵測-> 減輕-> 偵測-> 降低等是永久、 持續的狀態，將會無限期繼續。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-115">Detect -> Mitigate -> Detect -> Mitigate, etc., is a perpetual, persistent state that will continue indefinitely.</span></span>

## <a name="defending-against-dos-attacks"></a><span data-ttu-id="b7cfa-116">防禦拒絕服務攻擊</span><span class="sxs-lookup"><span data-stu-id="b7cfa-116">Defending Against DoS Attacks</span></span>

<span data-ttu-id="b7cfa-117">成功，以防範 DoS 攻擊，早期偵測是不可或缺的。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-117">To successfully defend against a DoS attack, early detection is essential.</span></span> <span data-ttu-id="b7cfa-118">藉由之前淹沒了系統偵測攻擊，防禦者可以執行回應計畫。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-118">By detecting an attack before the system is overwhelmed, defenders can execute a response plan.</span></span>

<span data-ttu-id="b7cfa-119">下列公式可協助大約時間 DoS 攻擊的影響：</span><span class="sxs-lookup"><span data-stu-id="b7cfa-119">The following formula will help approximate the time to impact of a DoS attack:</span></span>

   <span data-ttu-id="b7cfa-120">**最大容量 （以位元組/秒） / 成長率 （以位元組/秒） = 影響時間 （以位元組/秒）**</span><span class="sxs-lookup"><span data-stu-id="b7cfa-120">**Maximum Capacity (in bytes/sec) / Growth Rate (in bytes/sec) = Time to Impact (in bytes/sec)**</span></span>

<span data-ttu-id="b7cfa-121">若要偵測的時間就會發生時間的影響之後，則很可能 DoS 攻擊將會成功。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-121">If the time-to-detection occurs after time-to-impact, then it is likely the DoS attack will be successful.</span></span> <span data-ttu-id="b7cfa-122">如果要偵測時間發生之前的時間的影響，然後應保持遭受攻擊的服務，線上和可以存取，如果使用緩和措施策略。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-122">If the time-to-detection occurs before time-to-impact, then the services being attacked should remain online and accessible, if mitigation strategies are used.</span></span> <span data-ttu-id="b7cfa-123">因此，有可執行以抵禦拒絕服務攻擊的只有兩件事：</span><span class="sxs-lookup"><span data-stu-id="b7cfa-123">Thus, there are only two things that can be done to defend against DoS attacks:</span></span>
- <span data-ttu-id="b7cfa-124">若要引發的最大容量 （可輪流提供更多時間來偵測攻擊）; ceiling 增加容量或</span><span class="sxs-lookup"><span data-stu-id="b7cfa-124">Increase capacity to raise the ceiling of maximum capacity (which in turn provides more time to detect an attack); or</span></span>
- <span data-ttu-id="b7cfa-125">減少偵測的時間。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-125">Decrease the time to detect.</span></span>

<span data-ttu-id="b7cfa-126">增加容量有直接的會計影響。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-126">Increasing capacity has a direct fiscal impact.</span></span> <span data-ttu-id="b7cfa-127">Microsoft 建議的客戶開發至少基本吸收容量，以確保它們可以承受某種程度的 DoS 攻擊。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-127">Microsoft recommends that customers develop at least basic absorption capacity, to ensure that they can survive some level of DoS attack.</span></span> <span data-ttu-id="b7cfa-128">為每個客戶有自己的曝光度、 風險和財務 outlay 閾值而異客戶，實際吸收容量。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-128">The actual absorption capacity will vary from customer to customer, as each customer has their own thresholds for exposure, risk, and financial outlay.</span></span> <span data-ttu-id="b7cfa-129">最後，基於經濟原因，投資之上的研究和時間的方式來減少時間-偵測通常是最符合成本效益的措施。</span><span class="sxs-lookup"><span data-stu-id="b7cfa-129">Ultimately, for economic reasons, investments of research and time in ways to decrease time-to-detection are usually the most cost-effective defense.</span></span>
