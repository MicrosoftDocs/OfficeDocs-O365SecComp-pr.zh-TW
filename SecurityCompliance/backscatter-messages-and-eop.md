---
title: 非法回應郵件與 EOP
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
description: 非法回應郵件已傳送的郵件伺服器，通常是因為傳入的垃圾郵件的自動化的彈跳訊息。Backscatterer DNSBL 是非法回應郵件傳送的 IP 位址清單。不是垃圾郵件] 清單中，然後我們不嘗試從 Backscatterer DNSBL 移除伺服器。
ms.openlocfilehash: 2ab5c6a3bec347446452acd3bdfd8c5d309994a9
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002678"
---
# <a name="backscatter-messages-and-eop"></a>非法回應郵件與 EOP

非法回應郵件已傳送的郵件伺服器，通常是因為傳入的垃圾郵件的自動化的彈跳訊息。Exchange Online Protection (EOP) 為垃圾郵件篩選服務，因為電子郵件傳送給不存在的收件者和其他可疑的目的地會拒絕我們的服務。在這種情況下，EOP 會產生未傳遞回報 (NDR) 訊息並將其傳遞"者 」。因為垃圾郵件寄件經常使用偽造或無效 」 的 「 地址中其訊息，可能會造成非法回應郵件要傳送 NDR 的寄件者地址。在這種情況下，與 EOP 網路相關聯的外寄伺服器可能會列在 Backscatterer DNS 封鎖清單 (DNSBL)。Backscatterer DNSBL 是非法回應郵件傳送的 IP 位址清單。不是垃圾郵件] 清單中，然後我們不嘗試從 Backscatterer DNSBL 移除伺服器。 
  
> [!TIP]
> 根據 Backscatterer 網站的指示，該服務的設定或用法不建議對所有傳入的郵件使用拒絕模式。而是應該在安全模式中使用。如需實作正確非法回應設定的相關資訊，請造訪 [Backscatterer.org 網站](http://www.backscatterer.org/?target=usage)。 
  
## <a name="for-more-information"></a>相關資訊

[Backscatterer.org IP 清單](https://blogs.msdn.com/b/tzink/archive/2012/08/22/the-backscatterer-org-ip-list.aspx)
  
請參閱 ＜[進階垃圾郵件篩選選項](advanced-spam-filtering-asf-options.md)的"NDR 非法回應 」 項目
  

