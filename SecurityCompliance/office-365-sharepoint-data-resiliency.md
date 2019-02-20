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
# <a name="sharepoint-online-data-resiliency"></a><span data-ttu-id="a825a-103">SharePoint Online 資料恢復能力</span><span class="sxs-lookup"><span data-stu-id="a825a-103">SharePoint Online Data Resiliency</span></span>
<span data-ttu-id="a825a-p101">主要這當中的 SharePoint Online 是一部分的不會有任何資料的單一複本。SharePoint Online 使用 SQL Server 複寫，這是一組的複製並散發資料和資料庫物件從一個資料庫至另一個，並再同步處理維持一致的資料庫之間的技術。</span><span class="sxs-lookup"><span data-stu-id="a825a-p101">A key principle for SharePoint Online is to never have a single copy of any piece of data. SharePoint Online uses SQL Server replication, which is a set of technologies for copying and distributing data and database objects from one database to another, and then synchronizing between databases to maintain consistency.</span></span> 

<span data-ttu-id="a825a-p102">例如，當使用者在 SharePoint Online 中儲存的檔案，檔案區塊、 加密，且儲存在 Azure Blob 存放區中。Azure Blob 服務提供用以確保資料完整性這兩個應用程式及傳輸層級的機制。本文章會詳細說明這些服務與用戶端觀點機制。MD5 檢查是選用的 PUT 和 GET 作業 ；不過，它提供用以確保資料完整性跨網路時使用 HTTP, 讀者閱讀設備。此外，由於 HTTPS 提供額外的傳輸層安全性 MD5 檢查，則不需要因為備援透過 HTTPS 連接時。Azure Blob 服務提供長期儲存媒體，並使用自己的完整性檢查預存的資料。提供 MD5 的互動的應用程式時所用的應用程式與服務之間傳輸資料透過 HTTP 時檢查資料的完整性。</span><span class="sxs-lookup"><span data-stu-id="a825a-p102">For example, when a user saves a file in SharePoint Online, the file is chunked, encrypted, and stored within Azure Blob storage. Azure Blob service provides mechanisms to ensure data integrity both at the application and transport layers. This post will detail these mechanisms from the service and client perspective. MD5 checking is optional on both PUT and GET operations; however, it does provide a convenience facility to ensure data integrity across the network when using HTTP. Additionally, since HTTPS provides transport layer security additional MD5 checking is not needed while connecting over HTTPS as it would be redundant. Azure Blob service provides a durable storage medium, and uses its own integrity checking for stored data. The MD5's that are used when interacting with an application are provided for checking the integrity of the data when transferring that data between the application and service via HTTP.</span></span> 

<span data-ttu-id="a825a-p103">若要確保資料完整性 Azure Blob 服務會使用 MD5 雜湊資料的幾種不同的最節省中。請務必了解如何這些值會計算、 傳輸、 儲存、 及最後強制執行適當地設計您的應用程式以使用其以提供資料完整性。如需詳細資訊，請參閱[Windows Azure Blob MD5 概觀 （英文）](http://blogs.msdn.com/b/windowsazurestorage/archive/2011/02/18/windows-azure-blob-md5-overview.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a825a-p103">To ensure data integrity the Azure Blob service uses MD5 hashes of the data in a couple different manners. It is important to understand how these values are calculated, transmitted, stored, and eventually enforced to appropriately design your application to utilize them to provide data integrity. For more information, see [Windows Azure Blob MD5 Overview](http://blogs.msdn.com/b/windowsazurestorage/archive/2011/02/18/windows-azure-blob-md5-overview.aspx).</span></span> 

<span data-ttu-id="a825a-p104">中繼資料指標的檔案中所儲存的 SQL Server 資料庫 （內容資料庫）。所有區塊 – 檔案、 檔案及更新的差異部分 – 儲存為 blob 在 Azure 的存放區中的隨機分散於多個 Azure 儲存帳戶。SQL 資料庫被架設在 RAID 10 儲存體陣列同步鏡像至另一個 RAID 10 存放裝置陣列相同的資料中心內的個別機架在其上。非同步的記錄傳送然後用以將資料複寫到第二個資料中心內的另一個 RAID 10 存放裝置陣列。除了使用 RAID 10 與同步和非同步複寫的資料保護、 排程的資料備份將被帶這也非同步複寫到第二個資料中心。</span><span class="sxs-lookup"><span data-stu-id="a825a-p104">Metadata and pointers to the file are stored in a SQL Server database (the content database). All the chunks – files, pieces of files, and update deltas – are stored as blobs in Azure storage that are randomly distributed across multiple Azure storage accounts. The SQL database is hosted on a RAID 10 storage array which is synchronously mirrored to another RAID 10 storage array in a separate rack within the same datacenter. Asynchronous log shipping is then used to replicate the data to another RAID 10 storage array in a second datacenter. In addition to protecting data with RAID 10 and synchronous and asynchronous replication, scheduled data backups are taken which are also asynchronously replicated to the second datacenter.</span></span> 

<span data-ttu-id="a825a-p105">在 SharePoint Online、 資料備份執行每隔 12 小時，且保留 14 天。SharePoint Online 也會使用包含成對的地理位置不同資料中心內的相同客戶資料位置區域 （例如芝加哥和 San 說的已佈建在美國其租用戶的客戶） 的熱待命系統設定為主動/主動。例如，有 live 做為其主要資料中心及以容錯移轉資料中心的 San 說有芝加哥、 live 做為其主要資料中心及芝加哥作為其容錯移轉資料中心有 San 說使用者的使用者。</span><span class="sxs-lookup"><span data-stu-id="a825a-p105">In SharePoint Online, data backups are performed every 12 hours and retained for 14 days. SharePoint Online also uses a hot standby system that includes paired geographically-separate datacenters within the same customer data location region (for example, Chicago and San Antonio for customers who have provisioned their tenant in the United States) configured as active/active. For example, there are live users that have Chicago as their primary datacenter and San Antonio as a failover datacenter, and live users that have San Antonio as their primary datacenter and Chicago as their failover datacenter.</span></span> 