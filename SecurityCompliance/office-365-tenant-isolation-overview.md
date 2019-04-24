---
title: Office 365 中的租用戶隔離
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
description: Microsoft 如何強制執行 Office 365 租用戶隔離摘要。
ms.openlocfilehash: 87fd8cddce830ef58bcaa08462d6bcb120d1e05f
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262375"
---
# <a name="tenant-isolation-in-office-365"></a>Office 365 中的租用戶隔離

雲端運算同時許多客戶之間的共用共通的基礎結構的概念，而導致的規模的主要好處之一。 此概念稱為*多重租用*。 Microsoft 持續運作，以確保我們雲端服務的多重租用戶架構支援企業層級安全性、 機密性、 隱私權、 完整性和可用性標準。

根據重大投資和從[高可信度電腦運算](https://www.microsoft.com/en-us/twc/default.aspx)」 和 「[安全性開發生命週期](http://www.microsoft.com/security/sdl/default.aspx)中收集到的體驗，Microsoft 雲端服務的設計與所有租用戶是所有潛在惡意假設其他租用戶，以及我們已實作的安全性措施，以避免影響的安全性或服務，另一個租用戶，或存取另一個租用戶的內容從一個租用戶的動作。

維護多承租人環境中的租用戶隔離的兩個主要目標如下：
1.  防止外的洩或未經授權的存取，客戶內容給承租人;和
2.  防止一個租用戶的動作有不良影響的服務，另一個租用戶

整個 Office 365 來防止從危及系統的 Office 365 服務或應用程式或未經授權存取的其他租用戶或本身，包括 Office 365 系統資訊的客戶，已經實作多個表單的保護：
- Office 365 服務的每個租用戶中的客戶內容的邏輯隔離，達成透過 Azure Active Directory 授權和角色型存取控制。
- SharePoint Online 提供資料隔離機制儲存層級。
- Microsoft 會使用嚴密的實體安全性、 背景檢測和多層次的加密策略來保護的機密安全和完整性的客戶內容。 所有 Office 365 資料中心都有生物識別的存取控制，以最要求棕櫚列印到實體存取。 此外，所有美國 Microsoft 員工都順利完成所需的標準背景檢查僱用程序的一部分。 如需有關用於 Office 365 中的系統管理存取權的控制項的詳細資訊，請參閱 < <b0>Office 365 系統管理存取控制</b0>。
- Office 365 會使用加密靜止和傳輸，包括 BitLocker，每一檔案加密中的客戶內容的服務端技術傳輸層安全性 (TLS) 及網際網路通訊協定安全性 (IPsec)。 如需 Office 365 中加密的特定詳細資訊，請參閱 <<c0>在 Office 365 中的資料加密技術。

在一起，以上所列的保護提供強大的邏輯隔離控制項，可提供威脅防護和補救等於所提供的單獨的實體隔離。

## <a name="related-links"></a>相關連結
- [Azure Active Directory 中的隔離與存取控制](office-365-isolation-in-azure-active-directory.md)
- [Office Graph 與 Delve 中的租用戶隔離](office-365-isolation-in-graph-and-delve.md)
- [Office 365 搜尋中的租用戶隔離](office-365-isolation-in-office-365-search.md)
- [Office 365 影片中的租用戶隔離](office-365-isolation-in-office-365-video.md)
- [資源限制](office-365-resource-limits.md)
- [監視及測試租用戶界限](office-365-monitoring-and-testing.md)
- [Office 365 中的隔離與存取控制](office-365-isolation-in-office-365.md)