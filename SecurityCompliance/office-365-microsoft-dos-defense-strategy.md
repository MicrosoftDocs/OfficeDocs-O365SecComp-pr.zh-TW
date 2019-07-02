---
title: Office 365 DoS 防護策略
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 拒絕服務 (DoS) 攻擊的 Microsoft 防護策略。
ms.openlocfilehash: 0c046657ddd11412730c64bef475ba62e391c0bb
ms.sourcegitcommit: aa60a6cdf83c67576e858668d1182cd4fffeb5e0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2019
ms.locfileid: "33622363"
---
# <a name="office-365-denial-of-service-defense-strategy"></a>Office 365 拒絕服務防護策略

Microsoft 對於防禦網路型拒絕服務 (DoS) 攻擊的策略是唯一的, 因為我們的規模和全球使用量各不相同。 此規模可讓 Microsoft 使用策略和技術, 組織、提供者或客戶組織可能會相符。 DoS 策略的基礎是我們的全球目前狀態。 Microsoft 隨附 Internet provider、對等提供者 (公用和私人), 以及全球各地的私營公司。 這可讓 Microsoft 進行大量的網際網路服務, 並讓 Microsoft 能夠在大型表面區域內吸收攻擊。

鑒於這個獨特的本質, Microsoft 會使用不同于大型企業所使用之偵測和緩解程式。 此策略是以透過許多網路邊緣的偵測和全域分散緩解功能為基礎。 許多企業會使用協力廠商解決方案來偵測和緩解 edge 的攻擊。 隨著 Microsoft 的 edge 容量成長, 其對個別或特定邊的任何攻擊的重要性會變得很明顯。 因為這項獨特的設定, Microsoft 會將偵測和緩解元件分開。 Microsoft 會部署多層偵測系統, 以偵測更接近其飽和點的攻擊, 同時維持 edge 的全域緩解。 此策略可確保我們可以同時處理多個攻擊。

Microsoft 針對 DoS 攻擊所採用的最有效和低成本防護之一, 就是降低服務攻擊面。 不需要的流量會中斷網路邊緣, 而不會分析、處理和清理內嵌資料。

在具有公用網路的介面上, Microsoft 會使用特殊用途的安全裝置來進行防火牆、網路位址轉譯和 IP 篩選功能。 Microsoft 也使用全域同等成本多路徑 (ECMP) 路由。 全域 ECMP 路由是一種網路架構, 可確保有多個可到達服務的全域路徑。 使用這些多重路徑, 針對服務的攻擊會限制在發起攻擊的地區。 其他地區應該受到此攻擊的影響, 因為使用者會使用其他路徑來到達這些地區的服務。 Microsoft 也已開發出使用資料流程資料、效能計量及其他資訊的內部 DoS 關聯和偵測系統。 這是 Microsoft Azure 中的超大型雲端服務, 可分析從 Microsoft 網路和服務上的各種點收集的資料。 跨工作負載 DoS 事件回應小組識別小組中的角色和責任、升級的準則, 以及參與各種小組和事件處理的通訊協定。 這些解決方案提供以網路為基礎的防護 DoS 攻擊。

最後, 以雲端為基礎的工作負載會根據其通訊協定和頻寬使用方式來設定優化的閾值, 以唯一保護該工作負載。
