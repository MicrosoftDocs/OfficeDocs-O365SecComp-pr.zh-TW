---
title: Office 365 中的資料復原
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
description: 了解 Microsoft Office 365 中的資料恢復能力。
ms.openlocfilehash: 126e00c53e578b287538617a0e1ad84ae86ce7f1
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/20/2019
ms.locfileid: "30090535"
---
# <a name="data-resiliency-in-office-365"></a>Office 365 中的資料復原

## <a name="introduction"></a>簡介
授與雲端運算複雜性質、 Microsoft 是記住它不是萬一是否會出錯，但而時。我們設計我們雲端服務來提高可靠性與時不要出錯上客戶負面的影響降到最低。我們已移動超過傳統策略依賴複雜的實體基礎結構，且我們具有內建備援直接我們雲端服務。我們會使用較不複雜的實體基礎結構和多智慧型軟體的組建資料恢復到我們服務與我們的客戶提供高可用性的組合。 

## <a name="resiliency-and-recoverability-are-built-in"></a>恢復能力和復原能力是內建 
建置在恢復能力和復原開頭基礎的基礎結構和處理程序會在某些失敗的假設： 硬體 （基礎結構） 將會失敗且人們將出錯，軟體會有錯誤。雖然是正確說軟體開發人員未思考下列事項雲端之前，一般 IT 實作中會如何處理這些問題已非常不同雲端之前： 
- 首先，硬體和基礎結構的保護設定已顯著。這意味著具有與所需的 99.99%可靠性大幅能力及網路備援的資料中心及伺服器已實作與硬體為主叢集、 雙電源供應器、 雙網路介面和類似。 
- 其次，程序是最重要的。作業小組維護嚴謹的程序，已採用 windows、 變更，而且通常是重要的專案管理負荷。 
- 第三部署所需冰河腳步的位置。部署程式碼不含擁有來源原本用意等候修補程式版本及主要版本釋放所需的硬體更換及重要的資金 outlay。此外，若要更正問題只有一個方法是回復。即得出大多數 IT 組織會部署只有主要版本以避免來保持最新的工作。 
- 最後，部署系統的小數位數以及其 interconnectedness 的層級是在過去更加較現在是。 

今天、 客戶的預期 microsoft 連續創新在不影響之下品質，以及這是其中一個原因為何使用恢復能力與復原能力記住建置 Microsoft 的服務和軟體。 

## <a name="office-365-data-resiliency-principles"></a>Office 365 資料恢復原則 
恢復能力指的是承受特定類型的失敗且尚未保持 [完整功能的客戶面向從雲端架構服務的能力。資料恢復表示的 Office 365 中發生什麼失敗，不論重要的客戶資料會維持不變並不會影響。以結尾之 Office 365 服務已設計筆五個特定恢復原則： 
- 沒有要徑和非要徑資料。非要徑 （例如，是否訊息所讀取的 xml 資料） 可以放在極罕見的失敗情況。應該在極大的成本保護重要資料 （例如電子郵件訊息的客戶資料）。設計目標，為已傳遞的郵件一定是關鍵，且之類的郵件是否被讀取非要徑。 
- 客戶資料的副本必須分為不同容錯區域或當許多盡 （例如資料中心，可供單一認證 （程序、 伺服器或運算子） 存取） 錯誤的網域隔離失敗。 
- 要徑的客戶資料必須監視針對失敗的完整性、 一致性、 隔離、 持續性 (ACID) 的任何部分。 
- 客戶資料必須保護免受損毀。其必須是主動掃描或受監視、 可，以及可復原。 
- 從客戶動作的大部分資料遺失結果所以讓客戶能夠在他們自己使用 GUI，讓它們可以還原意外刪除的項目復原。 
 
透過這些原則搭配完善測試及驗證，我們雲端服務建立 Office 365 可以為符合及超過需求的客戶同時確保連續的創新與改進的平台。 

## <a name="related-links"></a>相關的連結

- [處理資料損毀](office-365-dealing-with-data-corruption.md)
- [惡意程式碼與勒索軟體防護](office-365-malware-and-ransomware-protection.md)
- [監視及自我修復](office-365-monitoring-and-self-healing.md)
- [Exchange 資料恢復能力](office-365-exchange-data-resiliency.md)
- [SharePoint 資料恢復能力](office-365-sharepoint-data-resiliency.md)