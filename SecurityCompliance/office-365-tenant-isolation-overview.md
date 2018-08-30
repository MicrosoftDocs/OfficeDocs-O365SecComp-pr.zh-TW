---
title: 在 Office 365 租用戶隔離
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
ms.collection: Strat_O365_Enterprise
description: Microsoft 如何強制執行 Office 365 租用戶隔離的摘要。
ms.openlocfilehash: fcf66ee65c2a4cfdf73ae0eac77f54bd555d059d
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526816"
---
# <a name="tenant-isolation-in-office-365"></a>在 Office 365 租用戶隔離

其中一個雲端運算同時許多客戶之間的共用、 常見的基礎架構的概念、 而導致的規模的主要好處。此概念稱為*多重租用*。Microsoft 持續運作來確保我們雲端服務多承租人架構支援企業層級安全性、 機密性、 隱私權、 完整性及可用性的標準。

根據重大的投資和收集哪些[高可信度電腦運算](https://www.microsoft.com/en-us/twc/default.aspx)及[安全性開發技術支援週期](http://www.microsoft.com/security/sdl/default.aspx)的經驗，Microsoft 雲端服務所設計與所有的租用戶會加入到所有可能有害的假設其他的承租人與我們已實作安全性措施阻止影響安全性或服務的另一個承租人或存取另一個承租人的內容從一個承租人的動作。

維護租用戶隔離多承租人環境中的兩個主要目標是：
1.  防止外的洩或未經授權的存取到客戶內容不同的承租人;與
2.  防止一個承租人的動作有不良影響的另一個承租人的服務

整個可防止從危及系統的 Office 365 服務或應用程式或取得未經授權的存取權的其他承租人或本身，包括 Office 365 系統資訊的客戶的 Office 365 中已實作多個表單的保護：
- Office 365 服務的每個租用戶中的客戶內容的邏輯隔離是透過 Azure Active Directory 授權和角色型存取控制來達成。
- SharePoint Online 提供資料儲存區層級的隔離機制。
- Microsoft 使用嚴格的實體安全性、 背景檢測及多重分層的加密策略來保護機密性和客戶內容完整性。所有的 Office 365 資料中心有生物特徵存取控制項，具有最要求棕櫚列印至實體的存取。此外，所有美國型 Microsoft 員工已順利完成所需標準背景] 核取雇用程序的一部分。如需有關用於系統管理存取 Office 365 中的控制項的詳細資訊，請參閱[Office 365 系統管理存取控制項](office-365-administrative-access-controls-overview.md)。
- Office 365 使用服務端技術加密客戶內容靜態及傳輸，包括 BitLocker，每個檔案加密的傳輸層安全性 (TLS) 及網際網路通訊協定安全性 (IPsec)。如需 Office 365 中的加密特定的詳細資訊，請參閱[Office 365 中的資料加密技術](office-365-encryption-in-the-microsoft-cloud-overview.md)。

在一起，上述模式保護提供提供威脅保護和減輕等於提供單獨的實體隔離的強大的邏輯隔離控制項。

## <a name="related-links"></a>相關的連結
- [Azure Active Directory 中的隔離與存取控制](office-365-isolation-in-azure-active-directory.md)
- [Office Graph 與 Delve 中的租用戶隔離](office-365-isolation-in-graph-and-delve.md)
- [Office 365 搜尋中的租用戶隔離](office-365-isolation-in-office-365-search.md)
- [Office 365 影片中的租用戶隔離](office-365-isolation-in-office-365-video.md)
- [資源限制](office-365-resource-limits.md)
- [監視及測試租用戶界限](office-365-monitoring-and-testing.md)
- [Office 365 中的隔離與存取控制](office-365-isolation-in-office-365.md)