---
title: Office 365 處理資料損毀
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
description: 在 Office 365，以及 Microsoft 致力保護及復原資料損毀的說明。
ms.openlocfilehash: d33cb298c432db45d560e4c2876d9ac34ab9d6f4
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216543"
---
# <a name="dealing-with-data-corruption-in-office-365"></a>處理 Office 365 中的資料損毀

執行大型雲端服務的面對方面的其中一個是如何處理資料損毀授與大量資料和獨立的系統。資料損毀可以所造成：
- 應用程式或基礎結構的錯誤、 損毀某些或所有的應用程式狀態 
- 硬體問題的結果中的資料遺失或無法讀取資料 
- 人工作業錯誤 
- 惡意駭客和挾名員工 
- 在 [外部服務導致部分資料遺失的事件 

在資料完整性更彈性表示較少資料損毀事件，因為 Microsoft 具有內建以避免發生，以及系統及程序可讓我們若是如此復原資料從損毀的 Office 365 保護機制。檢查和處理程序存在於內不同增加對資料損毀恢復工程版本程序的階段包括：
- 系統設計
- 程式碼組織與結構 
- 程式碼檢閱 
- 單元測試、 整合測試及系統測試
- 來回線路測試/閘道 

Office 365 的實際執行環境中資料中心之間的對等複寫可確保該一律多份 live 任何資料。標準圖像和指令碼可用來復原遺失的伺服器和複寫的資料用來還原客戶資料。內建資料恢復檢查和程序，因為 Microsoft 維護備份僅限 Office 365 資訊系統文件 （包括安全性相關的文件） 使用 SharePoint Online 和我們內部的程式碼中的內建複寫來源軍火庫儲存機制工具。系統文件儲存在 SharePoint Online 和來源軍火庫包含系統和應用程式的圖像。SharePoint Online 和來源軍火庫使用版本設定與中複寫幾近即時地。 