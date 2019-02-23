---
title: Office 365 SharePoint Online 資料刪除
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 在 SharePoint Online 中的資料刪除說明。
ms.openlocfilehash: 6d4989bc4b503309ba50237a164bffebaff1e7af
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218423"
---
# <a name="sharepoint-online-data-deletion-in-office-365"></a>Office 365 中的 SharePoint Online 資料刪除

SharePoint Online 為抽象應用程式資料庫中的程式碼儲存物件。當使用者上傳至 SharePoint Online 檔案時，該檔案是反組譯轉譯成應用程式碼與多個資料庫儲存在多個資料表中。在 SharePoint Online 客戶上傳的所有內容分成區塊，加密 （可能具有多個 AES 256 位元索引鍵），且分散於資料中心。特定詳細區塊和加密程序的詳細資訊，請參閱[Microsoft 雲端中的加密](office-365-encryption-in-the-microsoft-cloud-overview.md)。 

在 SharePoint Online 中的項目會保留從您從其原始位置刪除時間 93 天。它們留網站資源回收筒中的整個時間，除非有人刪除該處或該資源回收筒會清空。在此情況下，項目移至網站集合資源回收筒，它們留的其餘部分 93 天的位置。還原刪除的項目相關資訊，請參閱[還原資源回收筒的 SharePoint 網站中的項目](https://support.office.com/en-us/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
)並[還原已刪除網站集合資源回收筒中的項目](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b)。無法在 SharePoint Online 可設定資源回收筒保留時間。

當您刪除網站集合時，您也要刪除網站集合和其內的所有內容中的階層：
- 文件及文件庫
- 清單及清單資料
- 網站組態設定
- 站台或及其子網站相關的角色與安全性資訊
- 子網站的最上層網站、 其內容和使用者資訊

如果您不小心刪除網站集合，可以還原通用或 SharePoint admin 使用 SharePoint 管理中心。 

硬碟刪除發生於使用者會清除已刪除的項目從網站集合資源回收筒、 保留和備份期間到期，或系統管理員永久刪除使用[Remove-spodeletedsite cmdlet 可](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps)在網站集合時。硬碟使用者刪除時 （永久刪除，或清除） 從 SharePoint Online 內容的已刪除的區塊的所有加密金鑰也會一併都刪除。在先前儲存已刪除的區塊的磁碟上封鎖被標示為未使用與可重複使用。
