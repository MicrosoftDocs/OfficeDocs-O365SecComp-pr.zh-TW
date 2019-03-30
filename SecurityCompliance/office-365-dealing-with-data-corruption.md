---
title: Office 365 處理資料損毀
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
description: 在 Office 365 和 Microsoft 的努力防護和復原的資料損毀的說明。
ms.openlocfilehash: 9bf55243399ecd9f01f736e2da70d7c07231fa63
ms.sourcegitcommit: 1261a37c414111f869df5791548a768d853fda60
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/30/2019
ms.locfileid: "31004090"
---
# <a name="dealing-with-data-corruption-in-office-365"></a>處理 Office 365 中的資料損毀

下列其中一個執行大規模的雲端服務的一項挑戰層面是如何處理資料損毀，提供大量資料且獨立的系統。 可能會因資料損毀：
- 應用程式或基礎結構的錯誤，損毀部分或全部的應用程式的狀態 
- 硬體問題，導致資料遺失或無法讀取資料 
- 人類的作業錯誤 
- 惡意的駭客和挾的員工 
- 在 [外部服務導致部分資料遺失的事件 

更高的恢復功能資料完整性表示較少的資料損毀事件，因為 Microsoft 已內建 Office 365 保護機制，以避免發生，以及系統及程序，讓我們如果是的話，復原資料損毀。 檢查和處理程序存在於內工程發行程序增加對資料損毀的恢復能力的各種階段包括：
- 系統設計
- 程式碼部署組織與結構 
- 程式碼檢閱 
- 單元測試、 整合測試，以及系統測試
- 行程線路測試/門 

在 Office 365 實際執行環境中，資料中心之間的對等網路複寫可確保有多份 live 的任何資料。 標準影像和指令碼可用來復原遺失的伺服器，並用來還原客戶資料複寫的資料。 內建資料恢復檢查及處理程序，因為 Microsoft 的維護備份僅限 Office 365 資訊系統文件 （包括安全性相關的文件），使用 SharePoint Online 和內部程式碼中的內建複寫來源軍火庫存放庫工具。 系統文件儲存在 SharePoint Online 中，而且來源軍火庫包含系統和應用程式的影像。 SharePoint Online 與來源軍火庫使用版本設定，並且會在複寫幾近即時。 