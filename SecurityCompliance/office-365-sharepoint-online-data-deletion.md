---
title: Office 365 SharePoint Online 資料刪除
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
description: 在 SharePoint Online 中的資料刪除的說明。
ms.openlocfilehash: 3b49174a3ef97445061bdf33f15ea76e84161175
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262365"
---
# <a name="sharepoint-online-data-deletion-in-office-365"></a><span data-ttu-id="0644c-103">Office 365 中的 SharePoint Online 資料刪除</span><span class="sxs-lookup"><span data-stu-id="0644c-103">SharePoint Online Data Deletion in Office 365</span></span>

<span data-ttu-id="0644c-104">SharePoint Online 會將物件儲存為抽象應用程式資料庫中的程式碼。</span><span class="sxs-lookup"><span data-stu-id="0644c-104">SharePoint Online stores objects as abstracted code within application databases.</span></span> <span data-ttu-id="0644c-105">當使用者將檔案上傳至 SharePoint Online 時，該檔案是反組譯轉譯成應用程式程式碼和多個資料庫儲存在多個資料表中。</span><span class="sxs-lookup"><span data-stu-id="0644c-105">When a user uploads a file to SharePoint Online, that file is disassembled and translated into application code and stored in multiple tables across multiple databases.</span></span> <span data-ttu-id="0644c-106">在 SharePoint Online 中，客戶上傳的所有內容分成區塊，加密 （可能有多個 AES 256 位元金鑰），且分配到資料中心。</span><span class="sxs-lookup"><span data-stu-id="0644c-106">In SharePoint Online, all content that a customer uploads is broken into chunks, encrypted (potentially with multiple AES 256-bit keys), and distributed across the datacenter.</span></span> <span data-ttu-id="0644c-107">如需區塊和加密程序的特定詳細資訊，請參閱 < <b0>Microsoft Cloud 中的加密</b0>。</span><span class="sxs-lookup"><span data-stu-id="0644c-107">For specific details about the chunking and encryption process, see [Encryption in the Microsoft Cloud](office-365-encryption-in-the-microsoft-cloud-overview.md).</span></span> 

<span data-ttu-id="0644c-108">在 SharePoint Online 中，項目會保留您刪除其原始位置的時間從 93 天。</span><span class="sxs-lookup"><span data-stu-id="0644c-108">In SharePoint Online, items are retained for 93 days from the time you delete them from their original location.</span></span> <span data-ttu-id="0644c-109">它們留網站資源回收筒中的整個時間，除非有人會將其刪除從該處或清空該資源回收筒]。</span><span class="sxs-lookup"><span data-stu-id="0644c-109">They stay in the site Recycle Bin the entire time, unless someone deletes them from there or empties that Recycle Bin.</span></span> <span data-ttu-id="0644c-110">在此情況下，項目移至網站集合資源回收筒，它們留 93 天的其餘部分。</span><span class="sxs-lookup"><span data-stu-id="0644c-110">In that case, the items go to the site collection Recycle Bin, where they stay for the remainder of the 93 days.</span></span> <span data-ttu-id="0644c-111">還原刪除的項目相關資訊，請參閱[在 SharePoint 網站資源回收筒還原項目](https://support.office.com/en-us/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
)，並[還原已刪除的網站集合資源回收筒中的項目](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b)。</span><span class="sxs-lookup"><span data-stu-id="0644c-111">For info about restoring deleted items, see [Restore items in the Recycle Bin of a SharePoint site](https://support.office.com/en-us/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
) and [Restore deleted items from the site collection recycle bin](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b).</span></span> <span data-ttu-id="0644c-112">無法在 SharePoint Online 中設定的資源回收筒保留時間。</span><span class="sxs-lookup"><span data-stu-id="0644c-112">The Recycle Bin retention time is not configurable in SharePoint Online.</span></span>

<span data-ttu-id="0644c-113">當您刪除網站集合時，您也要刪除網站集合，以及它們的所有內容的階層：</span><span class="sxs-lookup"><span data-stu-id="0644c-113">When you delete a site collection, you're also deleting the hierarchy of sites in the collection, and all content within them:</span></span>
- <span data-ttu-id="0644c-114">文件及文件庫</span><span class="sxs-lookup"><span data-stu-id="0644c-114">Documents and document libraries</span></span>
- <span data-ttu-id="0644c-115">清單及清單資料</span><span class="sxs-lookup"><span data-stu-id="0644c-115">Lists and list data</span></span>
- <span data-ttu-id="0644c-116">網站組態設定</span><span class="sxs-lookup"><span data-stu-id="0644c-116">Site configuration settings</span></span>
- <span data-ttu-id="0644c-117">若要在網站或子網站相關的角色與安全性資訊</span><span class="sxs-lookup"><span data-stu-id="0644c-117">Role and security information that is related to the site or its subsites</span></span>
- <span data-ttu-id="0644c-118">子網站的最上層的網站、 其內容，以及使用者資訊</span><span class="sxs-lookup"><span data-stu-id="0644c-118">Subsites of the top-level website, their contents, and user information</span></span>

<span data-ttu-id="0644c-119">如果您不小心刪除網站集合，可以還原全域或 SharePoint 系統管理員使用 SharePoint 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="0644c-119">If you accidentally delete a site collection, it can be restored by a global or SharePoint admin using the SharePoint admin center.</span></span> 

<span data-ttu-id="0644c-120">當使用者會清除從網站集合資源回收筒，刪除的項目保留和備份期間到期，或系統管理員永久刪除網站集合使用[Remove-spodeletedsite cmdlet](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps)時，就會發生實刪除。</span><span class="sxs-lookup"><span data-stu-id="0644c-120">Hard deletion occurs when a user purges deleted items from the site collection Recycle Bin, when the retention and backup periods expire, or when an administrator permanently deletes a site collection using the [Remove-SPODeletedSite cmdlet](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps).</span></span> <span data-ttu-id="0644c-121">當硬碟使用者刪除 （永久刪除，或清除） 內容從 SharePoint Online，所有的加密金鑰的已刪除的區塊也會遭到刪除。</span><span class="sxs-lookup"><span data-stu-id="0644c-121">When a user hard deletes (permanently deletes, or purges) content from SharePoint Online, all encryption keys for the deleted chunks are also deleted.</span></span> <span data-ttu-id="0644c-122">先前儲存已刪除的區塊的磁碟上的區塊標示為未使用，並可供重複使用。</span><span class="sxs-lookup"><span data-stu-id="0644c-122">The blocks on the disks that previously stored the deleted chunks are marked as unused and available for re-use.</span></span>
