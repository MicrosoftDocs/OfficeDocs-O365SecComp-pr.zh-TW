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
ms.openlocfilehash: a7e67fcc87867190f345c5dad14e38a473420eab
ms.sourcegitcommit: 1261a37c414111f869df5791548a768d853fda60
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/30/2019
ms.locfileid: "31004070"
---
# <a name="defending-against-denial-of-service-attacks-in-office-365"></a><span data-ttu-id="9fc95-103">防禦 Office 365 中的拒絕服務攻擊</span><span class="sxs-lookup"><span data-stu-id="9fc95-103">Defending Against Denial-of-Service Attacks in Office 365</span></span>

## <a name="introduction"></a><span data-ttu-id="9fc95-104">簡介</span><span class="sxs-lookup"><span data-stu-id="9fc95-104">Introduction</span></span>
<span data-ttu-id="9fc95-105">Microsoft 會傳遞超過 200 個雲端服務，包括 Microsoft Azure、 Microsoft Bing、 Microsoft Office 365、 Microsoft Dynamics 365、 Microsoft OneDrive、 Skype，及 Xbox Live 我們全域雲端中裝載高可信度電腦基礎結構基礎結構的 100 個以上的資料中心。</span><span class="sxs-lookup"><span data-stu-id="9fc95-105">Microsoft delivers a trustworthy infrastructure for more than 200 cloud services, including Microsoft Azure, Microsoft Bing, Microsoft Office 365, Microsoft Dynamics 365, Microsoft OneDrive, Skype, and Xbox Live that are hosted in our global cloud infrastructure of more than 100 datacenters.</span></span>

<span data-ttu-id="9fc95-106">重大的網際網路平台服務與許多顯著的網際網路內容提供雲端服務的全球組織，Microsoft 是駭客及其他惡意個人的大型、 常見目標。</span><span class="sxs-lookup"><span data-stu-id="9fc95-106">As a global organization with a significant Internet presence and many prominent Internet properties that provide cloud services, Microsoft is a large, common target for hackers and other malicious individuals.</span></span> <span data-ttu-id="9fc95-107">網路-用戶端與 Microsoft Cloud-之間的通訊層是下列其中一個惡意攻擊的最大目標。</span><span class="sxs-lookup"><span data-stu-id="9fc95-107">The network--the communication layer between clients and the Microsoft Cloud--is one of the biggest targets of malicious attacks.</span></span> <span data-ttu-id="9fc95-108">事實上，多年，Microsoft 已持續和持續在某種形式的網路型 cyberattack 之下。</span><span class="sxs-lookup"><span data-stu-id="9fc95-108">In fact, for many years, Microsoft has been continuously and persistently under some form of network-based cyberattack.</span></span> <span data-ttu-id="9fc95-109">在幾乎所有的時間，至少一個 Microsoft 的網際網路內容發生某種形式的攻擊。</span><span class="sxs-lookup"><span data-stu-id="9fc95-109">At almost all times, at least one of Microsoft's Internet properties is experiencing some form of attack.</span></span> <span data-ttu-id="9fc95-110">沒有可防禦這些攻擊的可靠和持續性降低系統，Microsoft 雲端服務就是離線，讓客戶無法使用。</span><span class="sxs-lookup"><span data-stu-id="9fc95-110">Without reliable and persistent mitigation systems that can defend against these attacks, Microsoft's cloud services would be offline and unavailable to customers.</span></span>

<span data-ttu-id="9fc95-111">Microsoft 會使用深度防禦安全性原則來保護其雲端服務及網路。</span><span class="sxs-lookup"><span data-stu-id="9fc95-111">Microsoft uses defense-in-depth security principles to protect its cloud services and networks.</span></span> 

## <a name="definition-and-symptoms-of-denial-of-service-attacks"></a><span data-ttu-id="9fc95-112">定義和拒絕服務攻擊的徵狀</span><span class="sxs-lookup"><span data-stu-id="9fc95-112">Definition and Symptoms of Denial-of-Service Attacks</span></span>
<span data-ttu-id="9fc95-113">網路服務來進行攻擊的一種方式是建立許多要求對服務的主機壓制網路和拒絕合法的使用者提供服務的伺服器。</span><span class="sxs-lookup"><span data-stu-id="9fc95-113">One way to attack network services is to create many requests against a service's hosts to overwhelm the network and servers to deny service to legitimate users.</span></span> <span data-ttu-id="9fc95-114">這稱為拒絕服務 (DoS) 攻擊。</span><span class="sxs-lookup"><span data-stu-id="9fc95-114">This is referred to as a denial-of-service (DoS) attack.</span></span> <span data-ttu-id="9fc95-115">藉由多個動作項目、 端點] 及/或向量執行攻擊時，它被稱為分散式的拒絕服務 (DDoS) 攻擊。</span><span class="sxs-lookup"><span data-stu-id="9fc95-115">When the attack is performed by multiple actors, endpoints, and/or vectors, it is referred to as a distributed denial-of-service (DDoS) attack.</span></span> <span data-ttu-id="9fc95-116">雖然表示、 動機和目標而有所不同，DoS 和 DDoS 攻擊通常所組成的人員或人員的工作，以防止網際網路網站或服務正常運作，或在 all，暫時或無限期。</span><span class="sxs-lookup"><span data-stu-id="9fc95-116">Although the means, motives, and targets vary, DoS and DDoS attacks generally consist of the efforts of a person or persons to prevent an Internet site or service from functioning correctly or at all, either temporarily or indefinitely.</span></span>

<span data-ttu-id="9fc95-117">[美國電腦緊急整備小組](https://www.us-cert.gov/)(US CERT) 會定義要包含的 DoS 攻擊的徵狀：</span><span class="sxs-lookup"><span data-stu-id="9fc95-117">The [United States Computer Emergency Readiness Team](https://www.us-cert.gov/) (US-CERT) defines symptoms of DoS attacks to include:</span></span>
- <span data-ttu-id="9fc95-118">特別慢速網路效能 (時開啟的檔案或存取的網際網路網站)</span><span class="sxs-lookup"><span data-stu-id="9fc95-118">Unusually slow network performance (when opening files or accessing Internet sites)</span></span>
- <span data-ttu-id="9fc95-119">二者皆無法使用的網站</span><span class="sxs-lookup"><span data-stu-id="9fc95-119">Unavailability of a Web site</span></span>
- <span data-ttu-id="9fc95-120">無法存取的網站</span><span class="sxs-lookup"><span data-stu-id="9fc95-120">Inability to access a Web site</span></span>
- <span data-ttu-id="9fc95-121">大幅增加接收到的垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="9fc95-121">Dramatic increase in received spam</span></span>
- <span data-ttu-id="9fc95-122">中斷連線的無線或有線的網際網路連線</span><span class="sxs-lookup"><span data-stu-id="9fc95-122">Disconnection of a wireless or wired Internet connection</span></span>
- <span data-ttu-id="9fc95-123">長期遺失的網頁或任何網際網路服務的存取權</span><span class="sxs-lookup"><span data-stu-id="9fc95-123">Long-term loss of access to the Web or any Internet services</span></span>

## <a name="related-topics"></a><span data-ttu-id="9fc95-124">相關主題</span><span class="sxs-lookup"><span data-stu-id="9fc95-124">Related Topics</span></span>
- [<span data-ttu-id="9fc95-125">防禦阻斷服務攻擊的核心原則</span><span class="sxs-lookup"><span data-stu-id="9fc95-125">Core Principles of Defense Against Denial-of-Service Attacks</span></span>](office-365-core-principles-of-defense-against-dos-attacks.md)
- [<span data-ttu-id="9fc95-126">Microsoft 的拒絕服務攻擊防禦策略</span><span class="sxs-lookup"><span data-stu-id="9fc95-126">Microsoft's Denial-of-Service Defense Strategy</span></span>](office-365-microsoft-dos-defense-strategy.md)
- [<span data-ttu-id="9fc95-127">防禦拒絕服務攻擊的 Microsoft 雲端服務</span><span class="sxs-lookup"><span data-stu-id="9fc95-127">Defending Microsoft Cloud Services Against Denial-of-Service Attacks</span></span>](office-365-defending-cloud-services-against-dos-attacks.md)
