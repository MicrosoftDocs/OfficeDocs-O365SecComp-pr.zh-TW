---
title: Microsoft 365 中的資料調查 （預覽） 版本資訊
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 本文說明 Microsoft 365 中的進階 eDiscovery （預覽） 的新版本。
ms.openlocfilehash: 900031815ef1a2bbbd770c22db958659d8a0ef99
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30297026"
---
# <a name="release-notes-for-data-investigations-preview-in-microsoft-365"></a>Microsoft 365 中的資料調查 （預覽） 版本資訊

您可以使用新的資料調查 （預覽） 工具中的 [Microsoft 365 來分辨、 調查及修復資料的相關事件，例如資料 spillage 事件或內部調查。資料預覽公用調查提供早期的存取權的即將推出的功能和更新。若要取得早期的存取權的最新的功能，建立 Office 365 安全性 & 規範中心新將正在調查資料調查 (Preview) 中。若要了解如何，請參閱 ＜ [Manage Microsoft 365 中建立資料 spillage 事件](manage-data-spillage-incidents.md)。

## <a name="whats-new"></a>新功能 

- **調查**-您可以藉由建立調查群組搜尋和事件。管理人員可以存取調查新增或移除成員。 您也可以選取並標示最愛的調查。追蹤及監視活動內及使用新的儀表板調查不同。完成您調查之後，您可以關閉或予以刪除。

- **人員感興趣的**– 將使用者新增至調查的人員感興趣的身分時，您可以查看他們的信箱 OneDrive for Business 帳戶及 Microsoft 小組網站。您可以使用這些調查內容搜尋的範圍。若要進一步調查感興趣的人員，您也可以檢視稽核記錄相關的 Office 365 與其他 Microsoft 服務及其活動。

- **搜尋**– Create 整個組織搜尋使用各種搜尋條件。如果您知道使用者或想要搜尋的網站，您可以透過新增人員感興趣或搜尋建立精靈] 中指定的網站 」 位置的那些使用者來執行此動作。 

- **事件**– 建立新的支援事件，並新增您想要檢閱的搜尋結果。您可以檢閱個別的文件、 留下調查備忘稿加上註解和匯出結果將移至不同的環境。 

- **檢閱**– 使用的原生、 文字和附近原生檢視可供檢閱新增至事件的文件。您也可以套用至文件項目的分析的重複項目、 電子郵件執行緒及佈景主題可協助您檢閱事件的協助。 

- **Redact 標記，並加上註解**– Redact 文字套用標記，且當您檢閱文件註釋。
  
- **深層編製索引**– 如果有任何部分已編製索引的項目，這些會隨選重新編製索引，讓所有資料都將可供搜尋。

- **錯誤修復**– Remediate 或下載處理錯誤。這包括補救支援的大型檔案類型、 受密碼保護的檔案及編製索引的錯誤與相關的其他問題。 

- **工作**– 追蹤狀態長時間執行程序。

- **硬碟刪除的信箱項目**-在緊急情況下，您可能需要永久刪除錯位項目。為達成此目的，您可以執行**新增 ComplianceSearchAction-清除-PurgeType HardDelete**命令中安全性 & 規範中心 PowerShell 將永久移除信箱中的項目。如需詳細資訊，請參閱[新增 ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearchaction)。
