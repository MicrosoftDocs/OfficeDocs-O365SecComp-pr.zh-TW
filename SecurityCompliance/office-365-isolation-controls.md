---
title: Office 365 隔離控制
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
description: '摘要: Office 365 內隔離控制項的說明。'
ms.openlocfilehash: 6f5980ae25b412cbbccc20ec3b5726b5a4ceed86
ms.sourcegitcommit: 7b5e4a7a51f3cdd741deb77a2d60a18e2316618d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/01/2019
ms.locfileid: "33520683"
---
# <a name="office-365-isolation-controls"></a>Office 365 隔離控制 

Microsoft 持續運作, 以確保 Office 365 的多租使用者架構支援企業級的安全性、機密性、隱私權、完整性、當地、國際和可用性[標準](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons)。 Microsoft 所提供之服務的規模和範圍, 可讓您使用重要的人工互動來管理 Office 365。 Office 365 服務是透過多個全域分散式資料中心提供, 每個都以高自動化的方式進行, 且需要人工觸控或任何存取客戶內容。 我們的員工會使用自動化的工具和高度安全的遠端存取, 來支援這些服務和資料中心。 如需有關如何在 Office 365 中運作大量服務的詳細資訊, 請參閱[office 365 FOR IT 專業人員的主題](https://channel9.msdn.com/Events/SharePoint-Conference/2014/SPC202)。

Office 365 是由多種服務所組成, 可提供重要的商務功能, 並參與整個 Office 365 的體驗。 這些服務都是獨立的, 且設計為彼此整合。

Office 365 的設計具有下列原則:

 - 以**[服務為導向的架構](https://msdn.microsoft.com/library/aa480021.aspx):** 以可交互操作服務的形式來設計及開發軟體, 以提供良好定義的商務功能。
 - **[運作安全性保證](http://www.microsoft.com/download/details.aspx?id=40872):** 一種架構, 其包含透過 microsoft 獨有的各種功能所取得的知識, 包括 Microsoft[安全性開發週期](https://www.microsoft.com/sdl/default.aspx)、 [microsoft 安全性回應中心](https://technet.microsoft.com/library/dn440717.aspx), 以及深入瞭解 cybersecurity 威脅環境。

Office 365 服務間相互運作, 但已設計好並執行, 因此可將它們部署並運作為自治服務, 彼此無關。 Microsoft segregates Office 365 的責任和責任領域, 以減少未經授權或無意間修改或濫用組織資產的機會。 Office 365 小組已定義角色, 作為綜合角色型存取控制機制的一部分。

## <a name="customer-content-isolation"></a>客戶內容隔離

租使用者中的所有客戶內容都是與其他承租人, 以及 Office 365 管理中所使用的作業和系統資料隔離。 在整個 Office 365 中會執行多種保護形式, 以降低受到任何 Office 365 服務或應用程式威脅的風險。 多種保護形式也會防止未經授權的存取租使用者或 Office 365 系統本身的資訊。

如需 Microsoft 如何在 Office 365 中實現租使用者資料邏輯隔離的相關資訊, 請參閱[office 365 中的租使用者隔離](office-365-tenant-isolation-overview.md)。
