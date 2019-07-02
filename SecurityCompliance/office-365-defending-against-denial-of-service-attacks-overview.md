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
# <a name="defend-against-denial-of-service-attacks-in-office-365"></a><span data-ttu-id="c5bf5-103">防禦 Office 365 中的拒絕服務攻擊</span><span class="sxs-lookup"><span data-stu-id="c5bf5-103">Defend Against Denial-of-Service Attacks in Office 365</span></span>

## <a name="introduction"></a><span data-ttu-id="c5bf5-104">簡介</span><span class="sxs-lookup"><span data-stu-id="c5bf5-104">Introduction</span></span>

<span data-ttu-id="c5bf5-105">Microsoft 為超過100個資料中心的全域雲端基礎結構所主控的200雲端服務提供信任的基礎結構。</span><span class="sxs-lookup"><span data-stu-id="c5bf5-105">Microsoft delivers a trustworthy infrastructure for more than 200 cloud services hosted in a global cloud infrastructure of more than 100 datacenters.</span></span> <span data-ttu-id="c5bf5-106">這些包括：</span><span class="sxs-lookup"><span data-stu-id="c5bf5-106">These include:</span></span>

- <span data-ttu-id="c5bf5-107">Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="c5bf5-107">Microsoft Azure</span></span>
- <span data-ttu-id="c5bf5-108">Microsoft Bing</span><span class="sxs-lookup"><span data-stu-id="c5bf5-108">Microsoft Bing</span></span>
- <span data-ttu-id="c5bf5-109">Microsoft Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="c5bf5-109">Microsoft Dynamics 365</span></span>
- <span data-ttu-id="c5bf5-110">Microsoft Office 365</span><span class="sxs-lookup"><span data-stu-id="c5bf5-110">Microsoft Office 365</span></span>
- <span data-ttu-id="c5bf5-111">Microsoft OneDrive</span><span class="sxs-lookup"><span data-stu-id="c5bf5-111">Microsoft OneDrive</span></span>
- <span data-ttu-id="c5bf5-112">用 skype</span><span class="sxs-lookup"><span data-stu-id="c5bf5-112">Skype</span></span>
- <span data-ttu-id="c5bf5-113">Xbox Live</span><span class="sxs-lookup"><span data-stu-id="c5bf5-113">Xbox Live</span></span>

<span data-ttu-id="c5bf5-114">作為具有大量網際網路平臺的全球組織, 以及提供雲端服務的許多網路內容, Microsoft 是駭客及其他惡意人員的大型、常見的目標。</span><span class="sxs-lookup"><span data-stu-id="c5bf5-114">As a global organization with a significant Internet presence and many prominent Internet properties that provide cloud services, Microsoft is a large, common target for hackers and other malicious individuals.</span></span> <span data-ttu-id="c5bf5-115">用戶端與 Microsoft 雲端之間的網路通訊層是最大的惡意攻擊目標之一。</span><span class="sxs-lookup"><span data-stu-id="c5bf5-115">The network communication layer between clients and the Microsoft Cloud is one of the biggest targets of malicious attacks.</span></span> <span data-ttu-id="c5bf5-116">事實上, Microsoft 會持續且永久地採用某種形式的網路網路攻擊。</span><span class="sxs-lookup"><span data-stu-id="c5bf5-116">In fact, Microsoft is continuously and persistently under some form of network-based cyber-attack.</span></span> <span data-ttu-id="c5bf5-117">根據此, Microsoft 會使用縱深防禦的安全性原則來保護其雲端服務和網路。</span><span class="sxs-lookup"><span data-stu-id="c5bf5-117">In line with this, Microsoft uses defense-in-depth security principles to protect its cloud services and networks.</span></span> <span data-ttu-id="c5bf5-118">若沒有防禦這些攻擊的可靠和持續性緩解系統, Microsoft 的雲端服務將會離線且無法供客戶使用。</span><span class="sxs-lookup"><span data-stu-id="c5bf5-118">Without reliable and persistent mitigation systems that defend against these attacks, Microsoft's cloud services would be offline and unavailable to customers.</span></span>

## <a name="definition-and-symptoms-of-denial-of-service-attacks"></a><span data-ttu-id="c5bf5-119">拒絕服務攻擊的定義和徵兆</span><span class="sxs-lookup"><span data-stu-id="c5bf5-119">Definition and Symptoms of Denial-of-Service Attacks</span></span>

<span data-ttu-id="c5bf5-120">攻擊網路服務的一種方法, 就是建立許多對服務主機的要求, 以使網路和伺服器不會遭到合法使用者的服務。</span><span class="sxs-lookup"><span data-stu-id="c5bf5-120">One way to attack network services is to create many requests against service hosts to overwhelm the network and servers to deny service to legitimate users.</span></span> <span data-ttu-id="c5bf5-121">這稱為「拒絕服務」 (DoS) 攻擊。</span><span class="sxs-lookup"><span data-stu-id="c5bf5-121">This is referred to as a denial-of-service (DoS) attack.</span></span> <span data-ttu-id="c5bf5-122">當由多個演員、端點和/或向量執行攻擊時, 會將其稱為分散式阻斷服務 (DDoS) 攻擊。</span><span class="sxs-lookup"><span data-stu-id="c5bf5-122">When the attack is performed by multiple actors, endpoints, and/or vectors, it is referred to as a distributed denial-of-service (DDoS) attack.</span></span> <span data-ttu-id="c5bf5-123">雖然方法、motives 和目標各不相同, 但 DoS 和 DDoS 攻擊通常是由防止網際網路網站或服務正常運作, 或暫時或無限期的努力所構成。</span><span class="sxs-lookup"><span data-stu-id="c5bf5-123">Although the means, motives, and targets vary, DoS and DDoS attacks generally consist of efforts to prevent an Internet site or service from functioning correctly or at all, either temporarily or indefinitely.</span></span>

<span data-ttu-id="c5bf5-124">[美國電腦緊急就緒小組](https://www.us-cert.gov/)(美國) 會定義 DoS 攻擊的表現, 包括:</span><span class="sxs-lookup"><span data-stu-id="c5bf5-124">The [United States Computer Emergency Readiness Team](https://www.us-cert.gov/) (US-CERT) defines symptoms of DoS attacks to include:</span></span>

- <span data-ttu-id="c5bf5-125">網路效能較慢 (開啟檔案或存取網際網路網站時)</span><span class="sxs-lookup"><span data-stu-id="c5bf5-125">Unusually slow network performance (when opening files or accessing Internet sites)</span></span>
- <span data-ttu-id="c5bf5-126">網站不可用</span><span class="sxs-lookup"><span data-stu-id="c5bf5-126">Unavailability of a Web site</span></span>
- <span data-ttu-id="c5bf5-127">無法存取網站</span><span class="sxs-lookup"><span data-stu-id="c5bf5-127">Inability to access a Web site</span></span>
- <span data-ttu-id="c5bf5-128">收到垃圾郵件大幅增加</span><span class="sxs-lookup"><span data-stu-id="c5bf5-128">Dramatic increase in received spam</span></span>
- <span data-ttu-id="c5bf5-129">無線或有線網際網路連線的連接</span><span class="sxs-lookup"><span data-stu-id="c5bf5-129">Disconnection of a wireless or wired Internet connection</span></span>
- <span data-ttu-id="c5bf5-130">長期失去存取網站或任何網際網路服務的許可權</span><span class="sxs-lookup"><span data-stu-id="c5bf5-130">Long-term loss of access to the Web or any Internet services</span></span>

## <a name="related-topics"></a><span data-ttu-id="c5bf5-131">相關主題</span><span class="sxs-lookup"><span data-stu-id="c5bf5-131">Related Topics</span></span>

- [<span data-ttu-id="c5bf5-132">防禦阻斷服務攻擊的核心原則</span><span class="sxs-lookup"><span data-stu-id="c5bf5-132">Core Principles of Defense Against Denial-of-Service Attacks</span></span>](office-365-core-principles-of-defense-against-dos-attacks.md)
- [<span data-ttu-id="c5bf5-133">Microsoft 的拒絕服務防護策略</span><span class="sxs-lookup"><span data-stu-id="c5bf5-133">Microsoft's Denial-of-Service Defense Strategy</span></span>](office-365-microsoft-dos-defense-strategy.md)
- [<span data-ttu-id="c5bf5-134">防禦拒絕服務攻擊的 Microsoft 雲端服務</span><span class="sxs-lookup"><span data-stu-id="c5bf5-134">Defending Microsoft Cloud Services Against Denial-of-Service Attacks</span></span>](office-365-defending-cloud-services-against-dos-attacks.md)
