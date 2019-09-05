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
# <a name="defend-against-denial-of-service-attacks-in-office-365"></a><span data-ttu-id="7fa97-103">防禦 Office 365 中的拒絕服務攻擊</span><span class="sxs-lookup"><span data-stu-id="7fa97-103">Defend Against Denial-of-Service Attacks in Office 365</span></span>

## <a name="introduction"></a><span data-ttu-id="7fa97-104">簡介</span><span class="sxs-lookup"><span data-stu-id="7fa97-104">Introduction</span></span>

<span data-ttu-id="7fa97-105">Microsoft 會傳遞 200 位以上的雲端服務中的全域雲端基礎結構的 100 個以上的資料中心主控高可信度電腦基礎結構。</span><span class="sxs-lookup"><span data-stu-id="7fa97-105">Microsoft delivers a trustworthy infrastructure for more than 200 cloud services hosted in a global cloud infrastructure of more than 100 datacenters.</span></span> <span data-ttu-id="7fa97-106">這些包括：</span><span class="sxs-lookup"><span data-stu-id="7fa97-106">These include:</span></span>

- <span data-ttu-id="7fa97-107">Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="7fa97-107">Microsoft Azure</span></span>
- <span data-ttu-id="7fa97-108">Microsoft Bing</span><span class="sxs-lookup"><span data-stu-id="7fa97-108">Microsoft Bing</span></span>
- <span data-ttu-id="7fa97-109">Microsoft Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="7fa97-109">Microsoft Dynamics 365</span></span>
- <span data-ttu-id="7fa97-110">Microsoft Office 365</span><span class="sxs-lookup"><span data-stu-id="7fa97-110">Microsoft Office 365</span></span>
- <span data-ttu-id="7fa97-111">Microsoft OneDrive</span><span class="sxs-lookup"><span data-stu-id="7fa97-111">Microsoft OneDrive</span></span>
- <span data-ttu-id="7fa97-112">Skype</span><span class="sxs-lookup"><span data-stu-id="7fa97-112">Skype</span></span>
- <span data-ttu-id="7fa97-113">Xbox Live</span><span class="sxs-lookup"><span data-stu-id="7fa97-113">Xbox Live</span></span>

<span data-ttu-id="7fa97-114">重大的網際網路平台服務與許多顯著的網際網路內容提供雲端服務的全球組織，Microsoft 是駭客及其他惡意個人的大型、 常見目標。</span><span class="sxs-lookup"><span data-stu-id="7fa97-114">As a global organization with a significant Internet presence and many prominent Internet properties that provide cloud services, Microsoft is a large, common target for hackers and other malicious individuals.</span></span> <span data-ttu-id="7fa97-115">用戶端與 Microsoft 雲端之間的網路通訊層是下列其中一個惡意攻擊的最大目標。</span><span class="sxs-lookup"><span data-stu-id="7fa97-115">The network communication layer between clients and the Microsoft Cloud is one of the biggest targets of malicious attacks.</span></span> <span data-ttu-id="7fa97-116">事實上，Microsoft 會持續和持續在某種形式的網路型 cyberattack 下。</span><span class="sxs-lookup"><span data-stu-id="7fa97-116">In fact, Microsoft is continuously and persistently under some form of network-based cyberattack.</span></span> <span data-ttu-id="7fa97-117">內嵌，Microsoft 會使用深度防禦安全性原則來保護其雲端服務及網路。</span><span class="sxs-lookup"><span data-stu-id="7fa97-117">In line with this, Microsoft uses defense-in-depth security principles to protect its cloud services and networks.</span></span> <span data-ttu-id="7fa97-118">防禦這些攻擊的可靠和持續性降低系統，而 Microsoft 雲端服務就是離線，讓客戶無法使用。</span><span class="sxs-lookup"><span data-stu-id="7fa97-118">Without reliable and persistent mitigation systems that defend against these attacks, Microsoft's cloud services would be offline and unavailable to customers.</span></span>

## <a name="definition-and-symptoms-of-denial-of-service-attacks"></a><span data-ttu-id="7fa97-119">定義和拒絕服務攻擊的徵狀</span><span class="sxs-lookup"><span data-stu-id="7fa97-119">Definition and Symptoms of Denial-of-Service Attacks</span></span>

<span data-ttu-id="7fa97-120">網路服務來進行攻擊的一種方式是建立許多要求對服務主機壓制網路和拒絕合法的使用者提供服務的伺服器。</span><span class="sxs-lookup"><span data-stu-id="7fa97-120">One way to attack network services is to create many requests against service hosts to overwhelm the network and servers to deny service to legitimate users.</span></span> <span data-ttu-id="7fa97-121">這稱為拒絕服務 (DoS) 攻擊。</span><span class="sxs-lookup"><span data-stu-id="7fa97-121">This is referred to as a denial-of-service (DoS) attack.</span></span> <span data-ttu-id="7fa97-122">藉由多個動作項目、 端點] 及/或向量執行攻擊時，它被稱為分散式的拒絕服務 (DDoS) 攻擊。</span><span class="sxs-lookup"><span data-stu-id="7fa97-122">When the attack is performed by multiple actors, endpoints, and/or vectors, it is referred to as a distributed denial-of-service (DDoS) attack.</span></span> <span data-ttu-id="7fa97-123">雖然表示、 動機和目標而有所不同，DoS 和 DDoS 攻擊通常包含以防止網際網路網站或服務無法正確運作，或在所有，暫時或無限期的努力。</span><span class="sxs-lookup"><span data-stu-id="7fa97-123">Although the means, motives, and targets vary, DoS and DDoS attacks generally consist of efforts to prevent an Internet site or service from functioning correctly or at all, either temporarily or indefinitely.</span></span>

<span data-ttu-id="7fa97-124">[美國電腦緊急整備小組](https://www.us-cert.gov/)(US CERT) 會定義要包含的 DoS 攻擊的徵狀：</span><span class="sxs-lookup"><span data-stu-id="7fa97-124">The [United States Computer Emergency Readiness Team](https://www.us-cert.gov/) (US-CERT) defines symptoms of DoS attacks to include:</span></span>

- <span data-ttu-id="7fa97-125">特別慢速網路效能 (時開啟的檔案或存取的網際網路網站)</span><span class="sxs-lookup"><span data-stu-id="7fa97-125">Unusually slow network performance (when opening files or accessing Internet sites)</span></span>
- <span data-ttu-id="7fa97-126">二者皆無法使用的網站</span><span class="sxs-lookup"><span data-stu-id="7fa97-126">Unavailability of a Web site</span></span>
- <span data-ttu-id="7fa97-127">無法存取的網站</span><span class="sxs-lookup"><span data-stu-id="7fa97-127">Inability to access a Web site</span></span>
- <span data-ttu-id="7fa97-128">大幅增加接收到的垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="7fa97-128">Dramatic increase in received spam</span></span>
- <span data-ttu-id="7fa97-129">中斷連線的無線或有線的網際網路連線</span><span class="sxs-lookup"><span data-stu-id="7fa97-129">Disconnection of a wireless or wired Internet connection</span></span>
- <span data-ttu-id="7fa97-130">長期遺失的網頁或任何網際網路服務的存取權</span><span class="sxs-lookup"><span data-stu-id="7fa97-130">Long-term loss of access to the Web or any Internet services</span></span>

## <a name="related-topics"></a><span data-ttu-id="7fa97-131">相關主題</span><span class="sxs-lookup"><span data-stu-id="7fa97-131">Related Topics</span></span>

- [<span data-ttu-id="7fa97-132">防禦阻斷服務攻擊的核心原則</span><span class="sxs-lookup"><span data-stu-id="7fa97-132">Core Principles of Defense Against Denial-of-Service Attacks</span></span>](office-365-core-principles-of-defense-against-dos-attacks.md)
- [<span data-ttu-id="7fa97-133">Microsoft 的拒絕服務攻擊防禦策略</span><span class="sxs-lookup"><span data-stu-id="7fa97-133">Microsoft's Denial-of-Service Defense Strategy</span></span>](office-365-microsoft-dos-defense-strategy.md)
- [<span data-ttu-id="7fa97-134">防禦拒絕服務攻擊的 Microsoft 雲端服務</span><span class="sxs-lookup"><span data-stu-id="7fa97-134">Defending Microsoft Cloud Services Against Denial-of-Service Attacks</span></span>](office-365-defending-cloud-services-against-dos-attacks.md)
