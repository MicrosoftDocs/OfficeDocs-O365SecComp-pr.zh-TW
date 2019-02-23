---
title: 適用於 Project Server 的 GDPR
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
description: 深入了解如何在內部部署 Project Server 中解決 GDPR 需求。
ms.openlocfilehash: 67097cdab4fdab31537cf4b6dd27ce17234c2bdc
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30219013"
---
# <a name="gdpr-for-project-server"></a>適用於 Project Server 的 GDPR

Project Server 會使用自訂指令碼來匯出及編輯 Project Web App 中的使用者資料。基本程序為：

1.  在您的伺服器陣列中尋找 Project Web App 網站。

2.  在包含使用者的每個網站中尋找專案。

3.  匯出及檢閱您想要檢閱的資料類型。

4.  視需要編輯資料。

下列文章會詳細說明這些步驟：

- [從 Project Server 匯出使用者資料](/Project/export-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)

- [從 Project Server 刪除使用者資料](/Project/delete-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)


請注意，Project Server 是以 SharePoint Server 為基礎來建置的，並且會將事件記錄到 SharePoint ULS 記錄和使用狀況資料庫。如需詳細資訊，請參閱 [SharePoint Server 的 GDPR](gdpr-for-sharepoint-server.md)。
