---
title: Office 365 Microsoft DoS 防禦策略
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
description: Microsoft 的防禦策略與拒絕服務 (DoS) 攻擊的概觀。
ms.openlocfilehash: 0b0cf20e6282c85ede05edda3979ae5a7295ac78
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/20/2019
ms.locfileid: "30090815"
---
# <a name="microsofts-denial-of-service-defense-strategy"></a><span data-ttu-id="e4311-103">Microsoft 的拒絕服務防禦策略</span><span class="sxs-lookup"><span data-stu-id="e4311-103">Microsoft's Denial-of-Service Defense Strategy</span></span>

<span data-ttu-id="e4311-p101">Microsoft 的策略防禦網路型拒絕服務 (DoS) 攻擊是因為我們的規模與全域足跡有點唯一的。此規模可讓 Microsoft 運用策略和技術 （提供者或客戶組織） 的幾個組織可以符合。我們 DoS 策略的基石利用我們通用的目前狀態。Microsoft 會請與我們分享大幅網際網路平台服務 （其中到撰寫本文將加倍圍繞每隔 18 個月） 全世界的企業與網際網路提供者、 對等的提供者 （公用及私人） 及私人。有這類大型的目前狀態可讓 Microsoft 不同非常大的介面區吸收攻擊。</span><span class="sxs-lookup"><span data-stu-id="e4311-p101">Microsoft's strategy for defending against network-based denial-of-service (DoS) attacks is somewhat unique due to our scale and global footprint. This scale allows Microsoft to utilize strategies and techniques that few organizations (providers or customer organizations) can match. The cornerstone of our DoS strategy is leveraging our global presence. Microsoft engages with Internet providers, peering providers (public and private), and private corporations all over the world, giving us a significant Internet presence (which as of this writing, doubles around every 18 months). Having such a large presence enables Microsoft to absorb attacks across a very large surface area.</span></span>

<span data-ttu-id="e4311-p102">授與我們的獨特本質，Microsoft 使用偵測與減輕方式處理程序與不同的大型企業所用的那些值。我們的策略根據區分偵測與減輕方式，以及全域、 分散式減輕透過我們許多邊緣。許多企業使用協力廠商解決方案以偵測並降低攻擊緣。為我們 edge 容量成長得，它會變成清除任何個人或特定的邊緣攻擊的意義是非常低。因為我們唯一的設定，我們已分隔偵測及減輕元件。我們已部署，可讓我們偵測同時又不緣全域減輕攻擊更接近其飽和度點至多層偵測。這項策略可確保我們可以處理多個同時進行的攻擊。</span><span class="sxs-lookup"><span data-stu-id="e4311-p102">Given our unique nature, Microsoft uses detection and mitigation processes that differ from those used by large enterprises. Our strategy is based on a separation of detection and mitigation, as well as global, distributed mitigation through our many edges. Many enterprises use third-party solutions which detect and mitigate attacks at the edge. As our edge capacity grew, it became clear that the significance of any attack against individual or particular edges was very low. Because of our unique configuration, we have separated the detection and mitigation components. We have deployed multi-tiered detection that enables us to detect attacks closer to their saturation points while maintaining global mitigation at the edge. This strategy ensures we can handle multiple simultaneous attacks.</span></span>

<span data-ttu-id="e4311-p103">其中一個採用 Microsoft DoS 攻擊對最有效且低成本防禦是減少我們攻擊。如此可讓我們不想要的流量 drop 邊緣而不需分析、 處理並 raid-50 資料內嵌。</span><span class="sxs-lookup"><span data-stu-id="e4311-p103">One of the most effective and low-cost defenses employed by Microsoft against DoS attacks is to reduce our attack surface. Doing so enables us to drop unwanted traffic at the edge, as opposed to analyzing, processing and scrubbing the data inline.</span></span>

<span data-ttu-id="e4311-p104">與公用網路介面，在 Microsoft 會使用特殊用途安全性裝置防火牆、 網路位址轉譯，以及 IP 篩選功能。我們也會使用通用等於成本多重路徑 (ECMP) 路由。通用 ECMP 路由是可確保有多個全域路徑 reach 服務的網路架構。利用這些多個路徑，來服務攻擊應該限制在區域從中攻擊於 – 其他地區應該不會受此攻擊、 影響為一般使用者會使用其他路徑來連絡這些區域中的服務。我們也已經開發我們自己內部 DoS 相互關聯及偵測系統使用流量資料、 效能評量及其他資訊。這是 Microsoft Azure 的方式分析資料收集從各種點上 Microsoft 網路內執行 hyperscale 雲端服務與服務。跨工作量 DoS 應計小組識別的角色與責任整個小組、 呈報、 的準則與著讓各種小組與事件處理的通訊協定。這些解決方案提供網路型理想的 DoS 攻擊。</span><span class="sxs-lookup"><span data-stu-id="e4311-p104">At the interface with the public network, Microsoft uses special-purpose security devices for firewall, network address translation, and IP filtering functions. We also use global equal-cost multi-path (ECMP) routing. Global ECMP routing is a network framework that ensures there are multiple global paths to reach a service. Thanks to these multiple paths, an attack against the service should be limited to the region from which the attack originates – other regions should be unaffected by this attack, as end users would use other paths to reach the service in those regions. We have also developed our own internal DoS correlation and detection system that uses flow data, performance metrics and other information. This is a hyperscale cloud service running within Microsoft Azure which analyzes data collected from various points on Microsoft networks and services. A cross-workload DoS incident response team identifies the roles and responsibilities across teams, the criteria for escalations, and the protocols for engaging various teams and for incident handling. These solutions provide network-based protection against DoS attacks.</span></span>

<span data-ttu-id="e4311-126">最後，根據其通訊協定的最佳化臨界值來設定雲端式工作量和頻寬使用量需要唯一保護的工作負載。</span><span class="sxs-lookup"><span data-stu-id="e4311-126">Finally, cloud-based workloads are configured with optimized thresholds based on their protocol and bandwidth usage needs to uniquely protect that workload.</span></span>
