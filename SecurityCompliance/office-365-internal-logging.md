---
title: Office 365 的 Office 365 工程內部記錄
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 說明如何內部登入的 Office 365 工程小組運作。
ms.openlocfilehash: cf11a52541f6434a580435688db0f986f670bd31
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/20/2019
ms.locfileid: "30090755"
---
# <a name="internal-logging-for-office-365-engineering"></a>Office 365 工程內部記錄
除了事件及記錄資料可供客戶，也有內部的記錄資料集合系統可供 Office 365 工程師。許多不同類型的記錄資料從 Office 365 的伺服器上傳至運算服務呼叫宇宙 internal，big 資料。每個服務小組可將稽核記錄檔從其各自的伺服器上傳到宇宙資料庫中的彙總及分析。此資料傳送發生透過 FIPS 140-2-驗證 TLS 連線特別核准的連接埠和通訊協定使用專屬的自動化工具呼叫 Office 資料載入器 (ODL)。Office 365 中使用收集的工具與程序稽核記錄不允許永久或不能取消變更原始稽核記錄的內容或時間順序。

服務小組作為宇宙集中存放庫進行分析的應用程式使用量測量系統以及操作效能，並尋找異常和可能表示問題或安全性問題的模式。每個服務小組上傳的基準記錄檔的宇宙，將根據他們尋求分析，通常包含：
- 事件記錄檔
- AppLocker 記錄檔
- 效能資料
- System Center data
- 詳細通話記錄
- 經驗品質資料
- IIS Web 伺服器記錄檔
- SQL Server 記錄檔
- Syslog 資料
- 安全性稽核記錄

再將資料上傳到宇宙、 ODL 應用程式使用清除 service 模糊任何欄位包含客戶資料，例如承租人資訊及使用者識別資訊，並將這些欄位取代雜湊值。修正，然後上載到宇宙匿名及雜湊記錄檔]。服務小組針對宇宙中的相互關聯之通知，並回報其資料執行範圍的查詢。服務小組 ； 取決於宇宙中的稽核記錄檔資料保留期間大部分的稽核記錄檔資料會保留期為 90 天或更久支援安全性附隨調查並符合法規保留需求。

存取 Office 365 資料儲存在宇宙僅限於授權的人員。Microsoft 限制服務小組成員負責稽核功能有限的子集的稽核功能的管理。這些小組成員能夠修改或刪除資料從宇宙、 和沒有宇宙的記錄機制的所有修訂已錄製並進行稽核。

每個服務小組的授權以進行特定分析特定應用程式存取其記錄資料以供分析。例如，Office 365 安全性小組使用宇宙透過專屬的事件記錄剖析器的資料與相互關聯、 通知及 Office 365 實際執行環境中產生可採取的報告可能可疑的活動。此資料從報表可用以更正弱點，並改善服務的整體效能。如果特定的通知或報告需要進一步調查、 服務人員可以要求資料匯回至 Office 365 服務。自特定的記錄檔匯入從宇宙中加密和服務人員沒有解密機碼的權限、 目標記錄以程式設計方式通過解密服務授權的服務人員傳回範圍的結果。從這個練習找到任何弱點報告和擴大使用 Microsoft 的標準安全性附隨管理通道。
