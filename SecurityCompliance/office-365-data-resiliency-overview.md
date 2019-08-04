---
title: Office 365 中的資料復原
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
description: 了解 Microsoft Office 365 中的資料復原。
ms.openlocfilehash: 90edfe1a7e2baac172fcd9b8cc36163b8130484b
ms.sourcegitcommit: f0d23e57b00f07cef5b1b2d366eaeeeacda37e3e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/18/2019
ms.locfileid: "35786678"
---
# <a name="data-resiliency-in-office-365"></a>Office 365 中的資料復原

## <a name="introduction"></a>簡介
給定的雲端運算複雜的性質，Microsoft 會隨時注意，即無法的大小寫如果經常會發生錯誤，但而時。 我們來設計我們的雲端服務最大化可靠性和執行出錯時對客戶負面的影響降至最低。 我們已經移動超過傳統策略依賴複雜的實體基礎結構，以及我們已內建備援直接我們雲端服務。 我們使用較不複雜的實體基礎結構和多智慧型軟體，會將資料復原建置到我們的服務和我們的客戶提供高可用性的組合。 

## <a name="resiliency-and-recoverability-are-built-in"></a>恢復能力和恢復能力是內建 
建置在恢復能力和復原開頭為基礎的基礎結構和處理程序會在某個時間點失敗的假設： 硬體 （基礎結構） 將會失敗、 人類會使錯誤，以及軟體會有錯誤。 而是說軟體開發人員並非思考之前雲端這些項目不正確，這些問題的一般 IT 實作的已處理已之前雲端極為不同： 
- 首先，硬體和基礎結構的防護措施有明顯。 這表示有資料中心所需的 99.99%可靠性大幅電源與網路備援及伺服器已實作與硬體型叢集、 雙重電源供應器、 雙網路介面及類似。 
- 其次，程序是最重要的。 作業小組維護嚴格的程序，採用 windows，已的變更，而且通常已明顯的專案管理負荷。 
- 第三，部署所需冰河步調的地方。 部署的程式碼而擁有來源表示等待修補程式版本，而且主要版本釋放更換所涉及的硬體和重大的資金 outlay。 此外，若要修正問題的唯一方法就是回復。 因此，大多數 IT 組織會部署只有主要版本，以避免以保有最新的工作。 
- 最後，已部署的系統的小數位數以及其 interconnectedness 程度已在過去小很多比它現在是。 

現今，客戶預期來自 Microsoft 的連續創新而不會危害品質]，且這是與恢復能力和恢復能力記住為什麼內建 Microsoft 的服務和軟體的原因之一。 

## <a name="office-365-data-resiliency-principles"></a>Office 365 資料恢復能力原則 
恢復能力指的是承受某些類型的失敗，且尚未保持 [完整功能從客戶的觀點來看雲端式服務的能力。 資料恢復表示，無論發生何種失敗時在 Office 365 重要客戶資料仍會保留不變，不會受到影響。 為此，Office 365 服務都已設計大約五個特定恢復能力原則： 
- 沒有要徑和非關鍵資料。 非重大的資料 （例如，是否已讀取郵件） 可以在極罕見的失敗情況下捨棄。 重要資料 （例如，例如電子郵件訊息的客戶資料） 都必須保護極端的費用。 設計目標，已傳遞的郵件一律很重要，且之類的郵件是否被讀取非關鍵。 
- 客戶資料的副本必須分成不同的容錯區域或為許多盡可能 （例如，資料中心，可供存取的單一認證 （程序、 伺服器或運算子）） 容錯網域提供故障隔離。 
- 重要的客戶資料必須會監聽您的失敗的完整性、 一致性、 隔離、 主從 (ACID) 的任何部分。 
- 從損毀，必須保護客戶資料。 它必須是主動掃描或受監視、 修復，以及可復原。 
- 最多資料遺失結果從客戶動作，因此讓客戶能夠上自己使用 GUI，讓他們能夠還原意外刪除的項目復原。 
 
透過這些原則，再加上完善測試和驗證，我們雲端服務的建置 Office 365 就能符合，以及超過客戶的需求，同時確保持續性的創新及改進的平台。 

## <a name="related-links"></a>相關連結

- [處理資料損毀](office-365-dealing-with-data-corruption.md)
- [惡意程式碼與勒索軟體防護](office-365-malware-and-ransomware-protection.md)
- [監視及自我修復](office-365-monitoring-and-self-healing.md)
- [Exchange 資料恢復](office-365-exchange-data-resiliency.md)
- [SharePoint 資料恢復](office-365-sharepoint-data-resiliency.md)