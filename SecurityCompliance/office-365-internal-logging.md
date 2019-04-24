---
title: Office 365 的 Office 365 工程內部記錄
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
description: 說明如何內部登記錄的 Office 365 工程團隊運作。
ms.openlocfilehash: e8798d4c6d4ba7393612f9a2b22bc282956a2aa9
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262675"
---
# <a name="internal-logging-for-office-365-engineering"></a>Office 365 工程內部記錄
除了事件和供客戶使用的記錄資料，還有就可使用 Office 365 工程內部記錄資料集合系統。 許多不同類型的記錄資料從 Office 365 伺服器上傳至運算稱為宇宙服務內部、 大的資料。 每個服務小組會將稽核記錄檔，從其各自的伺服器上傳至宇宙資料庫以進行彙總及分析。 FIPS 140-2-驗證 TLS 連線特別核准的連接埠和通訊協定使用一個稱為 Office 資料載入器 (ODL) 的專屬的自動化工具，就會發生此資料傳送。 工具在 Office 365 中用來收集和處理程序的稽核記錄不允許永久，或者不能取消變更原始稽核記錄的內容或時間排序。

服務小組會使用為集中存放庫宇宙，以進行分析的應用程式使用量，以測量系統以及操作效能，並尋找異常和可能表示問題或安全性問題的模式。 每個服務小組上傳的基準之記錄到宇宙，根據他們正在分析時，通常包含下列：
- 事件記錄檔
- AppLocker 記錄檔
- 效能資料
- System Center data
- 詳細通話記錄
- 經驗品質資料
- IIS 網頁伺服器記錄檔
- SQL Server 記錄檔
- Syslog 資料
- 安全性稽核記錄檔

之前將資料上傳到宇宙，ODL 應用程式使用清除 service 模糊任何包含客戶資料，例如租用戶資訊及使用者識別資訊的欄位，並將這些欄位取代雜湊值。 將匿名與雜湊記錄會修正，然後上傳到宇宙。 服務小組針對相互關聯，警示，以及報告其資料在宇宙執行範圍的查詢。 宇宙中的稽核記錄資料保留期間取決於服務小組;若要支援安全性事件調查並以符合法規保留需求，大部分的稽核記錄資料會保留 90 天或更久。

存取 Office 365 資料儲存在宇宙只有授權的人員。 Microsoft 服務負責稽核功能的小組成員少部分限制的稽核功能的管理。 這些小組成員不需要修改或刪除資料從宇宙，能夠與宇宙記錄機制的所有變更都記錄及稽核。

每個服務小組進行授權以進行特定分析特定應用程式以存取其記錄資料以供分析。 例如，Office 365 安全性小組使用資料從宇宙專屬的事件記錄剖析器透過相互關聯，提醒，並在 Office 365 的實際執行環境中產生可採取動作可能可疑的活動報告。 更正弱點，並改善服務的整體效能，會使用此資料的報告。 如果特定提醒或報表時，需要進一步調查，服務人員可以要求資料，匯入回至 Office 365 服務。 自特定的記錄檔從宇宙匯入在加密，服務人員不需要存取解密金鑰，目標記錄檔以程式設計方式通過範圍的結果傳回授權的服務人員解密服務。 此作業中找到任何弱點報告，以及擴大使用 Microsoft 的標準安全性事件管理通道。
