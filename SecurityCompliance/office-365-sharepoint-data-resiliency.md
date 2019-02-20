---
title: Office 365 的 SharePoint 資料恢復能力
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
description: 在 SharePoint Online 在 Office 365 中的資料恢復能力的概觀。
ms.openlocfilehash: c550cb6572cb71b53cd544af64339129f72b888f
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/20/2019
ms.locfileid: "30090885"
---
# <a name="sharepoint-online-data-resiliency"></a>SharePoint Online 資料恢復能力
主要這當中的 SharePoint Online 是一部分的不會有任何資料的單一複本。SharePoint Online 使用 SQL Server 複寫，這是一組的複製並散發資料和資料庫物件從一個資料庫至另一個，並再同步處理維持一致的資料庫之間的技術。 

例如，當使用者在 SharePoint Online 中儲存的檔案，檔案區塊、 加密，且儲存在 Azure Blob 存放區中。Azure Blob 服務提供用以確保資料完整性這兩個應用程式及傳輸層級的機制。本文章會詳細說明這些服務與用戶端觀點機制。MD5 檢查是選用的 PUT 和 GET 作業 ；不過，它提供用以確保資料完整性跨網路時使用 HTTP, 讀者閱讀設備。此外，由於 HTTPS 提供額外的傳輸層安全性 MD5 檢查，則不需要因為備援透過 HTTPS 連接時。Azure Blob 服務提供長期儲存媒體，並使用自己的完整性檢查預存的資料。提供 MD5 的互動的應用程式時所用的應用程式與服務之間傳輸資料透過 HTTP 時檢查資料的完整性。 

若要確保資料完整性 Azure Blob 服務會使用 MD5 雜湊資料的幾種不同的最節省中。請務必了解如何這些值會計算、 傳輸、 儲存、 及最後強制執行適當地設計您的應用程式以使用其以提供資料完整性。如需詳細資訊，請參閱[Windows Azure Blob MD5 概觀 （英文）](http://blogs.msdn.com/b/windowsazurestorage/archive/2011/02/18/windows-azure-blob-md5-overview.aspx)。 

中繼資料指標的檔案中所儲存的 SQL Server 資料庫 （內容資料庫）。所有區塊 – 檔案、 檔案及更新的差異部分 – 儲存為 blob 在 Azure 的存放區中的隨機分散於多個 Azure 儲存帳戶。SQL 資料庫被架設在 RAID 10 儲存體陣列同步鏡像至另一個 RAID 10 存放裝置陣列相同的資料中心內的個別機架在其上。非同步的記錄傳送然後用以將資料複寫到第二個資料中心內的另一個 RAID 10 存放裝置陣列。除了使用 RAID 10 與同步和非同步複寫的資料保護、 排程的資料備份將被帶這也非同步複寫到第二個資料中心。 

在 SharePoint Online、 資料備份執行每隔 12 小時，且保留 14 天。SharePoint Online 也會使用包含成對的地理位置不同資料中心內的相同客戶資料位置區域 （例如芝加哥和 San 說的已佈建在美國其租用戶的客戶） 的熱待命系統設定為主動/主動。例如，有 live 做為其主要資料中心及以容錯移轉資料中心的 San 說有芝加哥、 live 做為其主要資料中心及芝加哥作為其容錯移轉資料中心有 San 說使用者的使用者。 