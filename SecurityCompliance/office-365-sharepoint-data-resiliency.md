---
title: Office 365 的 SharePoint 資料復原
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
description: 在 Office 365 中 SharePoint Online 資料恢復能力的概觀。
ms.openlocfilehash: 19eb7c3d0918d022d8adb427282b1faae8c6f4e9
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32260781"
---
# <a name="sharepoint-online-data-resiliency"></a>SharePoint Online 資料恢復
SharePoint online 重要原則是永遠不會有的任何資料片段的單一複本。 SharePoint Online 會使用 SQL Server 複寫，也就是一組的複製及散佈資料和資料庫物件從一個資料庫到另一個，並再同步處理維持一致的資料庫間的技術。 

例如，當使用者在 SharePoint Online 中儲存檔案，檔案會區塊、 加密，並儲存內 Azure Blob 儲存。 Azure Blob 服務提供用以確保資料完整性這兩個應用程式和傳輸層級的機制。 這篇文章將詳細說明這些機制就服務和用戶端的觀點。 檢查 MD5 是選用的 PUT 與 GET 作業;不過，它提供用以確保資料完整性跨網路時使用 HTTP 的便利設施。 此外，由於 HTTPS 提供額外的傳輸層安全性 MD5 檢查，就不需要時透過 HTTPS 連線，因為備援。 Azure Blob 服務提供長期儲存媒體，並使用它自己的完整性檢查已儲存的資料。 MD5 的互動的應用程式時所使用的被提供應用程式與服務之間傳送的資料，透過 HTTP 時檢查資料的完整性。 

若要確保資料完整性 Azure Blob 服務會使用 MD5 雜湊資料的幾種不同的最節省中。 請務必了解如何這些值計算、 傳輸、 儲存，且最後會強制執行適當地設計您的應用程式，利用它們提供資料的完整性。 如需詳細資訊，請參閱[Windows Azure Blob MD5 概觀](http://blogs.msdn.com/b/windowsazurestorage/archive/2011/02/18/windows-azure-blob-md5-overview.aspx)。 

中繼資料和檔案的指標會儲存在 SQL Server 資料庫 （內容資料庫）。 所有的區塊 – 檔案、 檔案及更新的差異部分 – 儲存為 Azure 儲存體中會隨機分散到多個 Azure 儲存體帳戶的 blob。 SQL 資料庫裝載於同步鏡像以於不同機架相同資料中心內的另一個 RAID 10 存放裝置陣列 RAID 10 存放裝置陣列。 非同步記錄傳送然後用來將資料複寫到另一個 RAID 10 儲存體陣列的第二個資料中心內。 除了保護 RAID 10 與同步與非同步複寫的資料，排程的資料備份會採取這也以非同步方式複寫到第二個資料中心。 

在 SharePoint Online 中，資料備份會執行每隔 12 小時，並且保留 14 天。 SharePoint Online 也會使用熱待命系統包含成對的地理位置不同資料中心內的相同客戶資料位置區域 （例如，芝加哥和 San 說的已佈建其租用戶在美國境內的客戶）設定為主動/主動。 例如，有 live 使用者為其主要資料中心及以容錯移轉資料中心的 San 說芝加哥且 live 具有 San 說他們的主要資料中心和芝加哥作為其容錯移轉資料中心的使用者。 