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
# <a name="sharepoint-online-data-deletion-in-office-365"></a><span data-ttu-id="9eb9f-103">Office 365 中的 SharePoint Online 資料刪除</span><span class="sxs-lookup"><span data-stu-id="9eb9f-103">SharePoint Online Data Deletion in Office 365</span></span>

<span data-ttu-id="9eb9f-p101">SharePoint Online 為抽象應用程式資料庫中的程式碼儲存物件。當使用者上傳至 SharePoint Online 檔案時，該檔案是反組譯轉譯成應用程式碼與多個資料庫儲存在多個資料表中。在 SharePoint Online 客戶上傳的所有內容分成區塊，加密 （可能具有多個 AES 256 位元索引鍵），且分散於資料中心。特定詳細區塊和加密程序的詳細資訊，請參閱[Microsoft 雲端中的加密](office-365-encryption-in-the-microsoft-cloud-overview.md)。若要防止資料遺失的 SharePoint Online 提供資料保護服務。尤其是備份執行每隔 12 小時，且保留 14 天。</span><span class="sxs-lookup"><span data-stu-id="9eb9f-p101">SharePoint Online stores objects as abstracted code within application databases. When a user uploads a file to SharePoint Online, that file is disassembled and translated into application code and stored in multiple tables across multiple databases. In SharePoint Online, all content that a customer uploads is broken into chunks, encrypted (potentially with multiple AES 256-bit keys), and distributed across the datacenter. For specific details about the chunking and encryption process, see [Encryption in the Microsoft Cloud](office-365-encryption-in-the-microsoft-cloud-overview.md). Data protection services are provided to prevent the loss of SharePoint Online data. Specifically, backups are performed every 12 hours and retained for 14 days.</span></span>

<span data-ttu-id="9eb9f-p102">當您刪除內容從 SharePoint Online 網站時，因此無法立即遭到刪除。它傳送至網站資源回收筒，其中將其還原，視。（請參閱[還原刪除的項目從網站集合資源回收筒](https://support.office.com/article/Restore-deleted-items-from-the-site-collection-recycle-bin-5fa924ee-16d7-487b-9a0a-021b9062d14b)還原步驟。）預設網站資源回收筒保留時間是即將 90 天。如果您從網站資源回收筒刪除內容，其會傳送到網站集合資源回收筒，且 30 天的保留時間。系統管理員就可以設定要保留在資源回收筒中的事項的時間長度但在該請假、 預設的保留期間是即將 90 天。網站資源回收筒儲存計算對網站集合的儲存配額和[清單檢視臨界值](https://support.office.com/article/List-View-Threshold-b8588dae-9387-48c2-9248-c24122f07c59)。</span><span class="sxs-lookup"><span data-stu-id="9eb9f-p102">When you delete content from a SharePoint Online site, it's not deleted immediately. It's sent to a Site Recycle Bin, where it can be restored, if needed. (See [Restore deleted items from the site collection recycle bin](https://support.office.com/article/Restore-deleted-items-from-the-site-collection-recycle-bin-5fa924ee-16d7-487b-9a0a-021b9062d14b) for restore steps.) The default Site Recycle Bin retention time is about 90 days. If you delete content from a Site Recycle Bin, it's sent to the Site Collection Recycle Bin, which has a retention time of 30 days. The length of time to keep things in the recycle bin can be configured by an administrator, but in the absence of that, the default retention period is about 90 days. The site recycle bin storage counts against site collection storage quota and the [List View Threshold](https://support.office.com/article/List-View-Threshold-b8588dae-9387-48c2-9248-c24122f07c59).</span></span>

<span data-ttu-id="9eb9f-116">當您刪除網站集合時，您正在也會刪除網站集合，包括所有內容和使用者資訊中的階層：</span><span class="sxs-lookup"><span data-stu-id="9eb9f-116">When you delete a site collection, you're also deleting the hierarchy of sites in the collection, including all content and user information:</span></span>
- <span data-ttu-id="9eb9f-117">文件及文件庫</span><span class="sxs-lookup"><span data-stu-id="9eb9f-117">Documents and document libraries</span></span>
- <span data-ttu-id="9eb9f-118">清單及清單資料</span><span class="sxs-lookup"><span data-stu-id="9eb9f-118">Lists and list data</span></span>
- <span data-ttu-id="9eb9f-119">網站組態設定</span><span class="sxs-lookup"><span data-stu-id="9eb9f-119">Site configuration settings</span></span>
- <span data-ttu-id="9eb9f-120">站台或及其子網站相關的角色與安全性資訊</span><span class="sxs-lookup"><span data-stu-id="9eb9f-120">Role and security information that is related to the site or its subsites</span></span>
- <span data-ttu-id="9eb9f-121">子網站的最上層網站、 其內容和使用者資訊</span><span class="sxs-lookup"><span data-stu-id="9eb9f-121">Subsites of the top-level website, their contents, and user information</span></span>

<span data-ttu-id="9eb9f-p103">刪除網站集合之前，建議您檢閱您計劃概述資料備份排程維護 microsoft SharePoint Online 網站 SharePoint Online 服務說明。也請注意，從備份還原可以是只針對網站集合或子網站，不的檔案、 清單或文件庫。如果您需要復原以外，使用資源回收筒。</span><span class="sxs-lookup"><span data-stu-id="9eb9f-p103">Before you delete a site collection, we recommend you review the SharePoint Online Service Description for your plan, which outlines the data backup schedule maintained by Microsoft for SharePoint Online sites. Also note that restorations from backups can are only for site collections or sub-sites, not for files, lists, or libraries. If you need to recover those, use the Recycle Bin.</span></span>

<span data-ttu-id="9eb9f-p104">如果您不小心刪除網站集合，它可以還原網站集合資源回收筒的網站集合管理員 30 天內。如果您需要還原 30 天後的網站集合，它可還原 microsoft 從 30 天的到期日的 14 天內所連絡 Microsoft 透過服務要求。</span><span class="sxs-lookup"><span data-stu-id="9eb9f-p104">If you accidentally delete a site collection, it can be restored from the Site Collection Recycle Bin by a Site Collection Administrator within 30 days. If you need a site collection restored after 30 days, it can be restored by Microsoft within 14 days from the 30-day expiration by contacting Microsoft via a Service Request.</span></span>

<span data-ttu-id="9eb9f-p105">使用者清除網站資源回收筒中刪除的項目和保留和備份期間到期，或系統管理員永久刪除網站集合使用[Remove-spodeletedsite cmdlet 可](https://docs.microsoft.com/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps)完全刪除時發生。硬碟使用者刪除時 （永久刪除，或清除） 從 SharePoint Online 內容的已刪除的區塊的所有加密金鑰也會一併都刪除。在先前儲存已刪除的區塊的磁碟上封鎖被標示為未使用與可重複使用。</span><span class="sxs-lookup"><span data-stu-id="9eb9f-p105">Hard deletion occurs when a user purges deleted items from the Site Recycle Bin, and the retention and backup periods expire, or when an administrator permanently deletes a site collection using the [Remove-SPODeletedSite cmdlet](https://docs.microsoft.com/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps). When a user hard deletes (permanently deletes, or purges) content from SharePoint Online, all encryption keys for the deleted chunks are also deleted. The blocks on the disks that previously stored the deleted chunks are marked as unused and available for re-use.</span></span>
