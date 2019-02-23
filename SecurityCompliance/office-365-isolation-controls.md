---
title: Office 365 隔離控制措施
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
description: 摘要： 在 Office 365 中的隔離控制項的說明。
ms.openlocfilehash: a6ff2b11ea02334a6c47317cbb77b8d47207b552
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217313"
---
# <a name="office-365-isolation-controls"></a>Office 365 隔離控制措施 

若要確認 Office 365 的多重租用戶架構支援企業層級安全性、 機密性、 隱私權、 完整性及可用性[標準](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons)，以及本機和以國際標準的 Microsoft 持續運作。指定的範圍及提供的 Microsoft 服務範圍，是說過很難且非經濟如果大幅人工互動需要管理 Office 365。Office 365 服務提供透過多個全域分散式資料中心、 高度自動化的方式，其中的資料中心操作極少需要人工觸控且甚至是較少的作業需要客戶內容的存取權。我們人員支援這些服務及使用自動化的工具資料中心及高度安全的遠端存取。部分的詳細資訊如何大規模服務被 21vianet Office 365，請參閱[幕後作業查看適用於 IT 專業人員的 Office 365 後置](https://channel9.msdn.com/Events/SharePoint-Conference/2014/SPC202)中。

Office 365 被組成多個服務，提供重要的商務功能及參與整個 Office 365 經驗。每個這些服務的設計目的是自給自足與彼此互相整合。Office 365 設計與[本篇架構](https://msdn.microsoft.com/library/aa480021.aspx)，這會定義為設計及開發軟體的互通性服務提供定義完善的商務功能和[操作的安全性表單中的原則保證](http://www.microsoft.com/download/details.aspx?id=40872)，同時知識 framework 獲得透過各種不同的是 Microsoft，包括 Microsoft[安全性開發週期](https://www.microsoft.com/sdl/default.aspx)、 [Microsoft 安全性回應中心](https://technet.microsoft.com/library/dn440717.aspx)、 及深層專用的功能cybersecurity 威脅橫向感知。

Office 365 服務彼此相互溝通，但他們正在設計和實作可以部署和操作為自發式服務，彼此獨立。Microsoft 區分責任及區域的 Office 365 以減少未經授權或無意修改的機會責任或誤用的組織資產。Office 365 小組已定義的角色全方位的角色型存取控制機制的一部分。

## <a name="customer-content-isolation"></a>客戶內容隔離
屬於租用戶的所有客戶內容都是隔離從其他租用戶和管理 Office 365 中使用的作業與系統資料。Office 任何的 365 Office 365 服務或應用程式或任何取得未經授權存取承租人或 Office 365 系統本身的資訊洩露風險降至最低整個已經實作多個表單的保護。如需 Microsoft 如何實作邏輯隔離的 Office 365 租用戶資料，請參閱 ＜[在 Office 365 租用戶隔離](office-365-tenant-isolation-overview.md)。
