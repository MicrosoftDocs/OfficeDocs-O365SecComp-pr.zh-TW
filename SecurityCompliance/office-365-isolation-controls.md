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
description: 摘要： 在 Office 365 隔離控制措施的說明。
ms.openlocfilehash: ceb64bc3f0a50b8e1d21f03f8621e4cc715c8f75
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262635"
---
# <a name="office-365-isolation-controls"></a>Office 365 隔離控制 

Microsoft 持續運作來確保 Office 365 的多重租用戶架構可支援企業層級安全性、 機密性、 隱私權、 完整性和可用性[標準](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons)，以及本機和國際標準。 指定比例] 和 [Microsoft 所提供的服務的範圍，將會很難和非經濟如果重大的人力互動需要管理 Office 365。 透過多個全域分散式資料中心，高度自動化的方式，其中極少的資料中心作業需要人工少許，且即使較少的作業需要客戶內容存取權提供 office 365 服務。 我們工作人員支援這些服務和資料中心使用自動化的工具和高度安全的遠端存取。 針對某些詳細瞭解大規模的服務會在 Office 365 中，請參閱[場景查看適用於 IT 專業人員的 Office 365 後](https://channel9.msdn.com/Events/SharePoint-Conference/2014/SPC202)運作。

Office 365 被組成多項服務會提供重要的商務功能，並且參與整個 Office 365 體驗。 每個這些服務的設計目的是獨立的並與彼此整合。 Office 365 的設計是與[推動架構](https://msdn.microsoft.com/library/aa480021.aspx)，這指設計和開發軟體提供完善定義的商務功能，以及[操作安全性的互通性服務的表單中的原則保證](http://www.microsoft.com/download/details.aspx?id=40872)，納入知識 framework 獲得透過各種對 Microsoft，包括 Microsoft[安全性開發生命週期](https://www.microsoft.com/sdl/default.aspx)、 [Microsoft 安全性回應中心](https://technet.microsoft.com/library/dn440717.aspx)，以及太深都是唯一的功能cybersecurity 威脅橫向感知。

Office 365 服務彼此相互溝通，但它們是設計及實作，讓他們可以部署與運作成為獨立服務，彼此獨立。 Microsoft 隔離，並職責劃分和 for Office 365 來降低未經授權或無意修改的機會責任範圍或組織的資產不當使用。 Office 365 小組已定義的角色，完整的角色型存取控制機制的一部分。

## <a name="customer-content-isolation"></a>客戶的內容加以隔離
屬於租用戶的所有客戶內容都會隔離從其他租用戶和管理 Office 365 中所使用的作業及系統資料。 已實作多個表單的保護整個 Office 任何的 365 Office 365 服務或應用程式，或任何租用的租用戶或 Office 365 系統本身的資訊未經授權的存取危害的風險降至最低。 如需 Microsoft 如何實作 Office 365 中的租用戶資料的邏輯隔離資訊，請參閱 <<c0>在 Office 365 中的租用戶隔離。
