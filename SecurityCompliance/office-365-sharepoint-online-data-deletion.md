---
title: Office 365 SharePoint Online 資料刪除
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
description: 在 SharePoint Online 中的資料刪除說明。
ms.openlocfilehash: c281f6de9cd9e4978ac4a6997333d71d8835420f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526350"
---
# <a name="sharepoint-online-data-deletion-in-office-365"></a>Office 365 中的 SharePoint Online 資料刪除

SharePoint Online 為抽象應用程式資料庫中的程式碼儲存物件。當使用者上傳至 SharePoint Online 檔案時，該檔案是反組譯轉譯成應用程式碼與多個資料庫儲存在多個資料表中。在 SharePoint Online 客戶上傳的所有內容分成區塊，加密 （可能具有多個 AES 256 位元索引鍵），且分散於資料中心。特定詳細區塊和加密程序的詳細資訊，請參閱[Microsoft 雲端中的加密](office-365-encryption-in-the-microsoft-cloud-overview.md)。若要防止資料遺失的 SharePoint Online 提供資料保護服務。尤其是備份執行每隔 12 小時，且保留 14 天。

當您刪除內容從 SharePoint Online 網站時，因此無法立即遭到刪除。它傳送至網站資源回收筒，其中將其還原，視。（請參閱[還原刪除的項目從網站集合資源回收筒](https://support.office.com/article/Restore-deleted-items-from-the-site-collection-recycle-bin-5fa924ee-16d7-487b-9a0a-021b9062d14b)還原步驟。）預設網站資源回收筒保留時間是即將 90 天。如果您從網站資源回收筒刪除內容，其會傳送到網站集合資源回收筒，且 30 天的保留時間。系統管理員就可以設定要保留在資源回收筒中的事項的時間長度但在該請假、 預設的保留期間是即將 90 天。網站資源回收筒儲存計算對網站集合的儲存配額和[清單檢視臨界值](https://support.office.com/article/List-View-Threshold-b8588dae-9387-48c2-9248-c24122f07c59)。

當您刪除網站集合時，您正在也會刪除網站集合，包括所有內容和使用者資訊中的階層：
- 文件及文件庫
- 清單及清單資料
- 網站組態設定
- 站台或及其子網站相關的角色與安全性資訊
- 子網站的最上層網站、 其內容和使用者資訊

刪除網站集合之前，建議您檢閱您計劃概述資料備份排程維護 microsoft SharePoint Online 網站 SharePoint Online 服務說明。也請注意，從備份還原可以是只針對網站集合或子網站，不的檔案、 清單或文件庫。如果您需要復原以外，使用資源回收筒。

如果您不小心刪除網站集合，它可以還原網站集合資源回收筒的網站集合管理員 30 天內。如果您需要還原 30 天後的網站集合，它可還原 microsoft 從 30 天的到期日的 14 天內所連絡 Microsoft 透過服務要求。

使用者清除網站資源回收筒中刪除的項目和保留和備份期間到期，或系統管理員永久刪除網站集合使用[Remove-spodeletedsite cmdlet 可](https://docs.microsoft.com/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps)完全刪除時發生。硬碟使用者刪除時 （永久刪除，或清除） 從 SharePoint Online 內容的已刪除的區塊的所有加密金鑰也會一併都刪除。在先前儲存已刪除的區塊的磁碟上封鎖被標示為未使用與可重複使用。
