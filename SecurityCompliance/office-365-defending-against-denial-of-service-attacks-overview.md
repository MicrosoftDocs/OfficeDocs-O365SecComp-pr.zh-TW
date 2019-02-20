---
title: 防禦與 Office 365 中的拒絕服務攻擊
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Overview of 拒絕服務 (DoS) 攻擊。
ms.openlocfilehash: cd099bcb225cfa5dd1f44f14d4b7813bef8f7442
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/20/2019
ms.locfileid: "30091015"
---
# <a name="defending-against-denial-of-service-attacks-in-office-365"></a><span data-ttu-id="fa847-103">防禦與 Office 365 中的拒絕服務攻擊</span><span class="sxs-lookup"><span data-stu-id="fa847-103">Defending Against Denial-of-Service Attacks in Office 365</span></span>

## <a name="introduction"></a><span data-ttu-id="fa847-104">簡介</span><span class="sxs-lookup"><span data-stu-id="fa847-104">Introduction</span></span>
<span data-ttu-id="fa847-105">Microsoft 提供超過 200 雲端服務，包括 Microsoft Azure、 Microsoft Bing、 Microsoft Office 365、 Microsoft Dynamics 365、 Microsoft OneDrive、 Skype、 和 Xbox Live 我們全域雲端中主控值得信任基礎的結構基礎結構的 100 個以上的資料中心。</span><span class="sxs-lookup"><span data-stu-id="fa847-105">Microsoft delivers a trustworthy infrastructure for more than 200 cloud services, including Microsoft Azure, Microsoft Bing, Microsoft Office 365, Microsoft Dynamics 365, Microsoft OneDrive, Skype, and Xbox Live that are hosted in our global cloud infrastructure of more than 100 datacenters.</span></span>

<span data-ttu-id="fa847-p101">為有重大的網際網路平台服務與許多重點的網際網路內容提供雲端服務的全域組織、 Microsoft 是駭客及其他惡意個人的大型、 常見目標。網路-用戶端與 Microsoft Cloud-之間的通訊層是其中一個惡意攻擊的最大目標。事實上，許多年度的 Microsoft 已持續並持續某些形式的網路型 cyberattack 下。在幾乎所有的時間，其中至少一個 Microsoft 的網際網路屬性發生某些形式的攻擊。沒有可防禦這些攻擊的可靠並持續性減輕系統、 Microsoft 雲端服務就是離線和客戶無法使用。</span><span class="sxs-lookup"><span data-stu-id="fa847-p101">As a global organization with a significant Internet presence and many prominent Internet properties that provide cloud services, Microsoft is a large, common target for hackers and other malicious individuals. The network--the communication layer between clients and the Microsoft Cloud--is one of the biggest targets of malicious attacks. In fact, for many years, Microsoft has been continuously and persistently under some form of network-based cyberattack. At almost all times, at least one of Microsoft's Internet properties is experiencing some form of attack. Without reliable and persistent mitigation systems that can defend against these attacks, Microsoft's cloud services would be offline and unavailable to customers.</span></span>

<span data-ttu-id="fa847-111">Microsoft 使用深入防禦安全性原則來保護其雲端服務及網路。</span><span class="sxs-lookup"><span data-stu-id="fa847-111">Microsoft uses defense-in-depth security principles to protect its cloud services and networks.</span></span> 

## <a name="definition-and-symptoms-of-denial-of-service-attacks"></a><span data-ttu-id="fa847-112">定義和拒絕服務攻擊的症狀</span><span class="sxs-lookup"><span data-stu-id="fa847-112">Definition and Symptoms of Denial-of-Service Attacks</span></span>
<span data-ttu-id="fa847-p102">攻擊網路服務的其中一個方法是建立對服務的主機許多要求會使不勝負荷的網路和以拒絕合法的使用者服務的伺服器。這被稱為拒絕服務 (DoS) 攻擊。當攻擊由多個動作項目、 端點及/或向量執行時，它會稱為分散式的拒絕服務 (DDoS) 攻擊。雖然表示、 動機和目標而異，DoS 與 DDoS 攻擊通常包含人員或人員致力於防止網際網路網站或服務正常運作或在 all、 暫時或無限期。</span><span class="sxs-lookup"><span data-stu-id="fa847-p102">One way to attack network services is to create many requests against a service's hosts to overwhelm the network and servers to deny service to legitimate users. This is referred to as a denial-of-service (DoS) attack. When the attack is performed by multiple actors, endpoints, and/or vectors, it is referred to as a distributed denial-of-service (DDoS) attack. Although the means, motives, and targets vary, DoS and DDoS attacks generally consist of the efforts of a person or persons to prevent an Internet site or service from functioning correctly or at all, either temporarily or indefinitely.</span></span>

<span data-ttu-id="fa847-117">[美國電腦緊急整備小組](https://www.us-cert.gov/)(US CERT) 會定義要包含的 DoS 攻擊的徵狀：</span><span class="sxs-lookup"><span data-stu-id="fa847-117">The [United States Computer Emergency Readiness Team](https://www.us-cert.gov/) (US-CERT) defines symptoms of DoS attacks to include:</span></span>
- <span data-ttu-id="fa847-118">就慢速網路效能 (時開啟的檔案或存取網際網路網站)</span><span class="sxs-lookup"><span data-stu-id="fa847-118">Unusually slow network performance (when opening files or accessing Internet sites)</span></span>
- <span data-ttu-id="fa847-119">期間無法使用的網站</span><span class="sxs-lookup"><span data-stu-id="fa847-119">Unavailability of a Web site</span></span>
- <span data-ttu-id="fa847-120">無法存取網站</span><span class="sxs-lookup"><span data-stu-id="fa847-120">Inability to access a Web site</span></span>
- <span data-ttu-id="fa847-121">大幅增加接收的垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="fa847-121">Dramatic increase in received spam</span></span>
- <span data-ttu-id="fa847-122">中斷連線的無線或有線網際網路連線</span><span class="sxs-lookup"><span data-stu-id="fa847-122">Disconnection of a wireless or wired Internet connection</span></span>
- <span data-ttu-id="fa847-123">長期遺失的網站或任何網際網路服務的存取權</span><span class="sxs-lookup"><span data-stu-id="fa847-123">Long-term loss of access to the Web or any Internet services</span></span>

## <a name="related-topics"></a><span data-ttu-id="fa847-124">相關主題</span><span class="sxs-lookup"><span data-stu-id="fa847-124">Related Topics</span></span>
- [<span data-ttu-id="fa847-125">防禦阻斷服務攻擊的核心原則</span><span class="sxs-lookup"><span data-stu-id="fa847-125">Core Principles of Defense Against Denial-of-Service Attacks</span></span>](office-365-core-principles-of-defense-against-dos-attacks.md)
- [<span data-ttu-id="fa847-126">Microsoft 的拒絕服務防禦策略</span><span class="sxs-lookup"><span data-stu-id="fa847-126">Microsoft's Denial-of-Service Defense Strategy</span></span>](office-365-microsoft-dos-defense-strategy.md)
- [<span data-ttu-id="fa847-127">防禦抵禦拒絕服務攻擊的 Microsoft 雲端服務</span><span class="sxs-lookup"><span data-stu-id="fa847-127">Defending Microsoft Cloud Services Against Denial-of-Service Attacks</span></span>](office-365-defending-cloud-services-against-dos-attacks.md)
