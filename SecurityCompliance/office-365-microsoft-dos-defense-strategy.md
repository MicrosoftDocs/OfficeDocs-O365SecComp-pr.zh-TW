---
title: Office 365 Microsoft DoS 攻擊防禦策略
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Microsoft 的攻擊防禦策略以因應拒絕服務 (DoS) 攻擊的概觀。
ms.openlocfilehash: acc0c74ae9ed434d4718d7b8b3bd9429b3245d46
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262545"
---
# <a name="microsofts-denial-of-service-defense-strategy"></a>Microsoft 的拒絕服務攻擊防禦策略

Microsoft 的防禦網路為基礎的拒絕服務 (DoS) 攻擊的策略是因為我們的規模和全域磁碟使用量稍有唯一的。 此擴充可讓 Microsoft，以利用一些 （提供者或客戶組織） 的組織可以比對的技術與策略。 我們 DoS 策略的基石利用我們全域顯示狀態。 Microsoft 凝聚與網際網路提供者、 對等的提供者 （公用和私人） 和私人公司使得全球，與我們分享重大網際網路平台服務 （其中截至撰寫本文時，將加倍周圍每 18 個月）。 具有這類大型的目前狀態，可讓 Microsoft，以不同非常大型的表面區域吸收攻擊。

指定我們的獨特性質，Microsoft 會使用不同於所用的大型企業偵測和緩和措施的程序。 我們的策略根據我們許多邊緣透過偵測和緩和措施，以及全域、 分散式補償方式區隔。 許多企業使用協力廠商解決方案可偵測並降低在邊緣的攻擊。 我們 edge 容量成長，因為它變成清除個人或特定的邊緣任何攻擊的意義是非常低。 由於我們唯一的組態，我們已分隔偵測和補救元件。 我們已部署可讓我們來偵測其飽和度點來攻擊更接近維持在邊緣全域降低的多層偵測。 這項策略可確保我們可以處理多個同時的攻擊。

下列其中一個最有效且低成本的防禦措施採用 microsoft DoS 攻擊會減少我們攻擊。 這樣可讓我們在邊緣，而非分析、 處理及清除資料內嵌 drop 不想要的流量。

在公用網路的介面，Microsoft 會使用特殊用途安全性裝置防火牆、 網路位址轉譯及 IP 篩選函式。 我們也會使用全域等於成本多重路徑 (ECMP) 路由。 全域 ECMP 路由是網路架構，以確保有多個全域的路徑，以達到服務。 感謝下列多個路徑，該服務攻擊會受限於區域從中攻擊源自 – 其他地區應為受到此類攻擊，使用者會使用其他路徑來連絡這些區域中的服務。 我們也已經開發自己內部 DoS 相互關聯及偵測系統使用流量資料、 效能計量及其他資訊。 這是在其中分析資料收集從各種點在 Microsoft 網路上的 Microsoft Azure 中執行獲得認證的超大型雲端服務與服務。 跨工作負載 DoS 事件回應小組會識別跨小組、 擴大、 準則和吸引各種小組與事件處理的通訊協定的角色和責任。 這些解決方案提供網路為基礎的保護，不受 DoS 攻擊。

最後，最佳化其通訊協定為基礎的臨界值來設定雲端工作負載和頻寬使用量需要唯一保護該工作負載。
