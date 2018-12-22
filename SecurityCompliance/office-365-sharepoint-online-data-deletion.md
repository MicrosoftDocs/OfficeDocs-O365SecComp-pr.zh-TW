---
title: Office 365 SharePoint Online 資料刪除
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 在 SharePoint Online 中的資料刪除說明。
ms.openlocfilehash: 8a84859ce170a4c3ca713c751aef2b6d5b911c55
ms.sourcegitcommit: 29ba4c36af8e90ddc8d885863ef25bac2cffbe94
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2018
ms.locfileid: "27411159"
---
# <a name="sharepoint-online-data-deletion-in-office-365"></a><span data-ttu-id="5c602-103">Office 365 中的 SharePoint Online 資料刪除</span><span class="sxs-lookup"><span data-stu-id="5c602-103">SharePoint Online Data Deletion in Office 365</span></span>

<span data-ttu-id="5c602-p101">SharePoint Online 為抽象應用程式資料庫中的程式碼儲存物件。當使用者上傳至 SharePoint Online 檔案時，該檔案是反組譯轉譯成應用程式碼與多個資料庫儲存在多個資料表中。在 SharePoint Online 客戶上傳的所有內容分成區塊，加密 （可能具有多個 AES 256 位元索引鍵），且分散於資料中心。特定詳細區塊和加密程序的詳細資訊，請參閱[Microsoft 雲端中的加密](office-365-encryption-in-the-microsoft-cloud-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="5c602-p101">SharePoint Online stores objects as abstracted code within application databases. When a user uploads a file to SharePoint Online, that file is disassembled and translated into application code and stored in multiple tables across multiple databases. In SharePoint Online, all content that a customer uploads is broken into chunks, encrypted (potentially with multiple AES 256-bit keys), and distributed across the datacenter. For specific details about the chunking and encryption process, see [Encryption in the Microsoft Cloud](office-365-encryption-in-the-microsoft-cloud-overview.md).</span></span> 

<span data-ttu-id="5c602-p102">在 SharePoint Online 中的項目會保留從您從其原始位置刪除時間 93 天。它們留網站資源回收筒中的整個時間，除非有人刪除該處或該資源回收筒會清空。在此情況下，項目移至網站集合資源回收筒，它們留的其餘部分 93 天的位置。還原刪除的項目相關資訊，請參閱[還原資源回收筒的 SharePoint 網站中的項目](https://support.office.com/en-us/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
)並[還原已刪除網站集合資源回收筒中的項目](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b)。無法在 SharePoint Online 可設定資源回收筒保留時間。</span><span class="sxs-lookup"><span data-stu-id="5c602-p102">In SharePoint Online, items are retained for 93 days from the time you delete them from their original location. They stay in the site Recycle Bin the entire time, unless someone deletes them from there or empties that Recycle Bin. In that case, the items go to the site collection Recycle Bin, where they stay for the remainder of the 93 days. For info about restoring deleted items, see [Restore items in the Recycle Bin of a SharePoint site](https://support.office.com/en-us/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
) and [Restore deleted items from the site collection recycle bin](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b). The Recycle Bin retention time is not configurable in SharePoint Online.</span></span>

<span data-ttu-id="5c602-113">當您刪除網站集合時，您也要刪除網站集合和其內的所有內容中的階層：</span><span class="sxs-lookup"><span data-stu-id="5c602-113">When you delete a site collection, you're also deleting the hierarchy of sites in the collection, and all content within them:</span></span>
- <span data-ttu-id="5c602-114">文件及文件庫</span><span class="sxs-lookup"><span data-stu-id="5c602-114">Documents and document libraries</span></span>
- <span data-ttu-id="5c602-115">清單及清單資料</span><span class="sxs-lookup"><span data-stu-id="5c602-115">Lists and list data</span></span>
- <span data-ttu-id="5c602-116">網站組態設定</span><span class="sxs-lookup"><span data-stu-id="5c602-116">Site configuration settings</span></span>
- <span data-ttu-id="5c602-117">站台或及其子網站相關的角色與安全性資訊</span><span class="sxs-lookup"><span data-stu-id="5c602-117">Role and security information that is related to the site or its subsites</span></span>
- <span data-ttu-id="5c602-118">子網站的最上層網站、 其內容和使用者資訊</span><span class="sxs-lookup"><span data-stu-id="5c602-118">Subsites of the top-level website, their contents, and user information</span></span>

<span data-ttu-id="5c602-119">如果您不小心刪除網站集合，可以還原通用或 SharePoint admin 使用 SharePoint 管理中心。</span><span class="sxs-lookup"><span data-stu-id="5c602-119">If you accidentally delete a site collection, it can be restored by a global or SharePoint admin using the SharePoint admin center.</span></span> 

<span data-ttu-id="5c602-p103">硬碟刪除發生於使用者會清除已刪除的項目從網站集合資源回收筒、 保留和備份期間到期，或系統管理員永久刪除使用[Remove-spodeletedsite cmdlet 可](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps)在網站集合時。硬碟使用者刪除時 （永久刪除，或清除） 從 SharePoint Online 內容的已刪除的區塊的所有加密金鑰也會一併都刪除。在先前儲存已刪除的區塊的磁碟上封鎖被標示為未使用與可重複使用。</span><span class="sxs-lookup"><span data-stu-id="5c602-p103">Hard deletion occurs when a user purges deleted items from the site collection Recycle Bin, when the retention and backup periods expire, or when an administrator permanently deletes a site collection using the [Remove-SPODeletedSite cmdlet](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps). When a user hard deletes (permanently deletes, or purges) content from SharePoint Online, all encryption keys for the deleted chunks are also deleted. The blocks on the disks that previously stored the deleted chunks are marked as unused and available for re-use.</span></span>
