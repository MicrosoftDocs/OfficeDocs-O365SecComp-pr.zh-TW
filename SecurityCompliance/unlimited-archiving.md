---
title: 在 Office 365 中的無限制封存概觀
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 37cdbb02-a24a-4093-8bdb-2a7f0b3a19ee
description: 了解自動展開封存在 Office 365 中，可提供無限制的封存儲存 Exchange Online 信箱。
ms.openlocfilehash: bf79ec35fe1ee55702f8a3715d62f102d1d88632
ms.sourcegitcommit: 73f1db241c0686020167d43442e7b07a2199ea3a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/28/2019
ms.locfileid: "36658129"
---
# <a name="overview-of-unlimited-archiving-in-office-365"></a><span data-ttu-id="0adde-103">在 Office 365 中的無限制封存概觀</span><span class="sxs-lookup"><span data-stu-id="0adde-103">Overview of unlimited archiving in Office 365</span></span>

<span data-ttu-id="0adde-104">在 Office 365 中封存信箱提供使用者額外信箱儲存空間。</span><span class="sxs-lookup"><span data-stu-id="0adde-104">In Office 365, archive mailboxes provide users with additional mailbox storage space.</span></span> <span data-ttu-id="0adde-105">啟用使用者的封存信箱之後，最多 100 GB 的額外儲存空間使用。</span><span class="sxs-lookup"><span data-stu-id="0adde-105">After a user's archive mailbox is enabled, up to 100 GB of additional storage is available.</span></span> <span data-ttu-id="0adde-106">在過去，當已達到 100 GB 的儲存配額，組織必須與 Microsoft 連絡到的封存信箱的要求額外儲存空間。</span><span class="sxs-lookup"><span data-stu-id="0adde-106">In the past, when the 100 GB storage quota was reached, organizations had to contact Microsoft to request additional storage space for an archive mailbox.</span></span> <span data-ttu-id="0adde-107">這不再是這種情況。</span><span class="sxs-lookup"><span data-stu-id="0adde-107">That's no longer the case.</span></span>

<span data-ttu-id="0adde-108">（稱為*自動展開封存*） 的 Office 365 中的無限制封存功能提供最多 1 TB 的封存信箱中的額外儲存空間。</span><span class="sxs-lookup"><span data-stu-id="0adde-108">The unlimited archiving feature in Office 365 (called *auto-expanding archiving*) provides up to 1 TB of additional storage in archive mailboxes.</span></span> <span data-ttu-id="0adde-109">達到封存信箱中的儲存配額時，Office 365 會自動增加的封存，這表示使用者不會用盡信箱儲存空間和系統管理員不需要要求封存信箱的額外儲存空間。</span><span class="sxs-lookup"><span data-stu-id="0adde-109">When the storage quota in the archive mailbox is reached, Office 365 automatically increases the size of the archive, which means that users won't run out of mailbox storage space and administrators won't have to request additional storage for archive mailboxes.</span></span>
  
<span data-ttu-id="0adde-110">如需逐步指示的開啟自動展開封存，請參閱[啟用 Office 365 中的無限制封存](enable-unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="0adde-110">For step-by-step instructions for turning on auto-expanding archiving, see [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="0adde-111">自動展開封存也支援共用信箱。</span><span class="sxs-lookup"><span data-stu-id="0adde-111">Auto-expanding archiving also supports shared mailboxes.</span></span> <span data-ttu-id="0adde-112">若要啟用信箱的共用信箱的封存，Exchange Online Plan 2 授權或具有 Exchange Online Archiving 授權的 Exchange Online Plan 1 授權就需要。</span><span class="sxs-lookup"><span data-stu-id="0adde-112">To enable the archive for a shared mailbox, an Exchange Online Plan 2 license or an Exchange Online Plan 1 license with an Exchange Online Archiving license is required.</span></span> 
  
## <a name="how-auto-expanding-archiving-works"></a><span data-ttu-id="0adde-113">如何自動展開封存的運作</span><span class="sxs-lookup"><span data-stu-id="0adde-113">How auto-expanding archiving works</span></span>

<span data-ttu-id="0adde-114">為先前所述的其他信箱啟用使用者的封存信箱時，會建立儲存空間。</span><span class="sxs-lookup"><span data-stu-id="0adde-114">As previously explained, additional mailbox storage space is created when a user's archive mailbox is enabled.</span></span> <span data-ttu-id="0adde-115">啟用自動展開封存時，Office 365 會定期檢查封存信箱的大小。</span><span class="sxs-lookup"><span data-stu-id="0adde-115">When auto-expanding archiving is enabled, Office 365 periodically checks the size of the archive mailbox.</span></span> <span data-ttu-id="0adde-116">當封存信箱取得接近其儲存限制時，Office 365 會自動建立封存信箱的額外儲存空間。</span><span class="sxs-lookup"><span data-stu-id="0adde-116">When an archive mailbox gets close to its storage limit, Office 365 automatically creates additional storage space for the archive mailbox.</span></span> <span data-ttu-id="0adde-117">此額外的空間會呼叫*輔助封存*。</span><span class="sxs-lookup"><span data-stu-id="0adde-117">This additional space is called an *auxiliary archive*.</span></span> <span data-ttu-id="0adde-118">如果使用者執行輔助封存中的儲存空間不足，Office 365 會自動加入新的輔助封存。</span><span class="sxs-lookup"><span data-stu-id="0adde-118">If the user runs out of storage space in an auxiliary archive, Office 365 will automatically add a new auxiliary archive.</span></span> <span data-ttu-id="0adde-119">Office 365 會新增最多 1 TB 的額外儲存空間總計的 20 輔助封存。</span><span class="sxs-lookup"><span data-stu-id="0adde-119">Office 365 will add a maximum of 20 auxiliary archives for a total of 1 TB of addtional storage.</span></span> <span data-ttu-id="0adde-120">這表示系統管理員不需要管理自動展開封存此程序會自動發生。</span><span class="sxs-lookup"><span data-stu-id="0adde-120">This process happens automatically, which means administrators don't have to manage auto-expanding archiving.</span></span> 
  
<span data-ttu-id="0adde-121">以下是程序的簡要概觀。</span><span class="sxs-lookup"><span data-stu-id="0adde-121">Here's a quick overview of the process.</span></span>
  
![自動展開封存程序概觀](media/74355385-d990-44fe-8a87-6c3639d1f63f.png)
  
1. <span data-ttu-id="0adde-123">使用者信箱或共用的信箱啟用封存。</span><span class="sxs-lookup"><span data-stu-id="0adde-123">Archiving is enabled for a user mailbox or a shared mailbox.</span></span> <span data-ttu-id="0adde-124">會建立封存信箱具有 100 GB 的儲存空間，且封存信箱的 [警告] 配額設為 90 GB。</span><span class="sxs-lookup"><span data-stu-id="0adde-124">An archive mailbox with 100 GB of storage space is created, and the warning quota for the archive mailbox is set to 90 GB.</span></span>
    
2. <span data-ttu-id="0adde-125">系統管理員可讓自動展開封存信箱。</span><span class="sxs-lookup"><span data-stu-id="0adde-125">An administrator enables auto-expanding archiving for the mailbox.</span></span> <span data-ttu-id="0adde-126">當封存信箱 （包括 [可復原的項目] 資料夾） 達到 90 GB 時，則會轉換成自動展開封存，與 Office 365 會儲存空間新增至封存。</span><span class="sxs-lookup"><span data-stu-id="0adde-126">When the archive mailbox (including the Recoverable Items folder) reaches 90 GB, it's converted to an auto-expanding archive, and Office 365 adds storage space to the archive.</span></span> <span data-ttu-id="0adde-127">請注意，可能需要最多 30 天來佈建額外的儲存空間。</span><span class="sxs-lookup"><span data-stu-id="0adde-127">Note that it can take up to 30 days for the additional storage space to be provisioned.</span></span>

> [!NOTE]
> <span data-ttu-id="0adde-128">如果信箱會處於暫止狀態或指派給 Office 365 保留原則，啟用自動展開封存時增加封存信箱的儲存配額為 110 GB。</span><span class="sxs-lookup"><span data-stu-id="0adde-128">If a mailbox is placed on hold or assigned to an Office 365 retention policy, the storage quota for the archive maibox is increased to 110 GB when auto-expanding archiving is enabled.</span></span> <span data-ttu-id="0adde-129">同樣地，封存警告配額增加到 100GB。</span><span class="sxs-lookup"><span data-stu-id="0adde-129">Similarly, the archive warning quota is increased to 100 GB.</span></span>
    
3. <span data-ttu-id="0adde-130">Office 365 會自動新增更多儲存空間，必要時。</span><span class="sxs-lookup"><span data-stu-id="0adde-130">Office 365 automatically adds more storage space when necessary.</span></span> <span data-ttu-id="0adde-131">如先前所述，Office 365 會新增多達 20 輔助封存，最多 1 TB 的額外的封存儲存空間。</span><span class="sxs-lookup"><span data-stu-id="0adde-131">As previously stated, Office 365 will add up to 20 auxiliary archives, for a maximum of 1 TB of additional archive storage space.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0adde-132">自動展開封存才支援信箱用於個別使用者 （或共用信箱） 不會超過 1 GB，每天成長率。</span><span class="sxs-lookup"><span data-stu-id="0adde-132">Auto-expanding archive is only supported for mailboxes used for individual users (or shared mailboxes) with a growth rate that doesn't exceed 1 GB per day.</span></span> <span data-ttu-id="0adde-133">使用者的封存信箱僅供該使用者使用。</span><span class="sxs-lookup"><span data-stu-id="0adde-133">A user's archive mailbox is intended for just that user.</span></span> <span data-ttu-id="0adde-134">不允許使用日誌、 傳輸規則或自動轉寄規則將郵件複製到封存信箱。</span><span class="sxs-lookup"><span data-stu-id="0adde-134">Using journaling, transport rules, or auto-forwarding rules to copy messages to an archive mailbox is not permitted.</span></span> <span data-ttu-id="0adde-135">Microsoft 保留在使用者封存信箱中用來儲存其他使用者之封存資料的執行個體中拒絕不受限封存的權限。</span><span class="sxs-lookup"><span data-stu-id="0adde-135">Microsoft reserves the right to deny unlimited archiving in instances where a user's archive mailbox is used to store archive data for other users.</span></span>

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a><span data-ttu-id="0adde-136">項目取得移至其他封存儲存空間？</span><span class="sxs-lookup"><span data-stu-id="0adde-136">What gets moved to the additional archive storage space?</span></span>

<span data-ttu-id="0adde-137">若要有效使用自動展開封存儲存，可能會移動資料夾。</span><span class="sxs-lookup"><span data-stu-id="0adde-137">To make efficient use of auto-expanding archive storage, folders might get moved.</span></span> <span data-ttu-id="0adde-138">Office 365 會決定哪些資料夾取得移至封存新增額外的儲存空間時。</span><span class="sxs-lookup"><span data-stu-id="0adde-138">Office 365 determines which folders get moved when additional storage is added to the archive.</span></span> <span data-ttu-id="0adde-139">移動資料夾時，原始資料夾中的 [封存在 Outlook 中的資料夾清單部分中自動建立子資料夾。</span><span class="sxs-lookup"><span data-stu-id="0adde-139">When a folder is moved, a subfolder is automatically created under the original folder in the archive portion of the folder list in Outlook.</span></span> <span data-ttu-id="0adde-140">這個新的子資料夾會指向已移動的項目。</span><span class="sxs-lookup"><span data-stu-id="0adde-140">This new subfolder points to the items that were moved.</span></span> <span data-ttu-id="0adde-141">Office 365 使用來命名此資料夾的命名慣例為**\<資料夾名稱\>_yyyy （上建立 mmm dd，yyyy h_mm）**，其中：</span><span class="sxs-lookup"><span data-stu-id="0adde-141">The naming convention that Office 365 uses to name this folder is **\<folder name\>_yyyy (Created on mmm dd, yyyy h_mm)**, where:</span></span> 
  
- <span data-ttu-id="0adde-142">**yyyy**是所收到的郵件] 資料夾中的年份。</span><span class="sxs-lookup"><span data-stu-id="0adde-142">**yyyy** is the year the messages in the folder were received.</span></span> 
    
- <span data-ttu-id="0adde-143">**mmm dd，yyyy h_m**是子資料夾由 Office 365 中，建立以 UTC 格式，根據使用者的時區和 Outlook 中的地區設定的時間與日期。</span><span class="sxs-lookup"><span data-stu-id="0adde-143">**mmm dd, yyyy h_m** is the date and time that the subfolder was created by Office 365, in UTC format, based on the user's time zone and regional settings in Outlook.</span></span> 
    
<span data-ttu-id="0adde-144">下列螢幕擷取畫面顯示的資料夾清單前面和後面的郵件會移自動展開封存中。</span><span class="sxs-lookup"><span data-stu-id="0adde-144">The following screen shots show a folder list before and after messages are moved in an auto-expanded archive.</span></span>
  
 <span data-ttu-id="0adde-145">**之前新增額外儲存空間**</span><span class="sxs-lookup"><span data-stu-id="0adde-145">**Before additional storage is added**</span></span>
  
![之前已佈建自動展開封存的封存信箱的資料夾清單](media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)
  
 <span data-ttu-id="0adde-147">**之後新增額外儲存空間**</span><span class="sxs-lookup"><span data-stu-id="0adde-147">**After additional storage is added**</span></span>
  
![之後已佈建自動展開封存的封存信箱的資料夾清單](media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)
  
## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a><span data-ttu-id="0adde-149">Outlook 需求，來存取自動展開封存中的項目</span><span class="sxs-lookup"><span data-stu-id="0adde-149">Outlook requirements for accessing items in an auto-expanded archive</span></span>

<span data-ttu-id="0adde-150">若要存取儲存在自動展開封存的郵件，使用者必須使用下列其中一個下列 Outlook 用戶端：</span><span class="sxs-lookup"><span data-stu-id="0adde-150">To access messages that are stored in an auto-expanded archive, users have to use one of the following Outlook clients:</span></span>
  
- <span data-ttu-id="0adde-151">Outlook 2016 或 Windows 版 Outlook 2019</span><span class="sxs-lookup"><span data-stu-id="0adde-151">Outlook 2016 or Outlook 2019 for Windows</span></span>
    
- <span data-ttu-id="0adde-152">Outlook 網頁版</span><span class="sxs-lookup"><span data-stu-id="0adde-152">Outlook on the web</span></span> 
    
- <span data-ttu-id="0adde-153">Outlook 2016 或 Outlook for Mac 的 2019</span><span class="sxs-lookup"><span data-stu-id="0adde-153">Outlook 2016 or Outlook 2019 for Mac</span></span> 
    
> [!NOTE]
> <span data-ttu-id="0adde-154">Outlook 2013 使用者可以只存取的項目，原本已儲存在其封存信箱。</span><span class="sxs-lookup"><span data-stu-id="0adde-154">Outlook 2013 users can only access items that were originally stored in their archive mailbox.</span></span> <span data-ttu-id="0adde-155">他們將無法存取的項目移至其他封存儲存]。</span><span class="sxs-lookup"><span data-stu-id="0adde-155">They won't be able to access items that are moved to additional archive storage.</span></span> 
  
<span data-ttu-id="0adde-156">以下是使用 Outlook 或 Outlook 來存取郵件中自動展開封存儲存網頁時要考慮的事項。</span><span class="sxs-lookup"><span data-stu-id="0adde-156">Here are some things to consider when using Outlook or Outlook on the web to access messages stored in an auto-expanded archive.</span></span>
  
- <span data-ttu-id="0adde-157">您可以存取封存信箱時，包括已移至自動展開存放區中的任何資料夾。</span><span class="sxs-lookup"><span data-stu-id="0adde-157">You can access any folder in your archive mailbox, including ones that were moved to the auto-expanded storage area.</span></span>
    
- <span data-ttu-id="0adde-158">您可以搜尋的只是藉由搜尋資料夾本身已移至其他儲存區的項目。</span><span class="sxs-lookup"><span data-stu-id="0adde-158">You can search for items that were moved to an additional storage area only by searching the folder itself.</span></span> <span data-ttu-id="0adde-159">這表示您必須選取 [封存] 資料夾在資料夾清單中選取 [**目前的資料夾**選項作為搜尋範圍。</span><span class="sxs-lookup"><span data-stu-id="0adde-159">This means you have to select the archive folder in the folder list to select the **Current Folder** option as the search scope.</span></span> <span data-ttu-id="0adde-160">同樣地，如果自動展開存放區中的資料夾含有子資料夾，您必須個別搜尋每個子資料夾。</span><span class="sxs-lookup"><span data-stu-id="0adde-160">Similarly, if a folder in an auto-expanded storage area contains subfolders, you have to search each subfolder separately.</span></span> 
    
- <span data-ttu-id="0adde-161">Outlook 中的項目計數，而且可能無法正確自動展開封存中的讀取/未讀計數 （在 Outlook 和 outlook 網頁版）。</span><span class="sxs-lookup"><span data-stu-id="0adde-161">Item counts in Outlook and Read/Unread counts (in Outlook and Outlook on the web ) in an auto-expanded archive might not be accurate.</span></span>
    
- <span data-ttu-id="0adde-162">您可以刪除指向自動展開存放裝置] 區域中，子資料夾中的項目，但不能刪除資料夾本身。</span><span class="sxs-lookup"><span data-stu-id="0adde-162">You can delete items in a subfolder that points to an auto-expanded storage area, but the folder itself can't be deleted.</span></span>
    
- <span data-ttu-id="0adde-163">您無法使用 [復原刪除的項目] 功能來復原已從自動展開存放區刪除的項目。</span><span class="sxs-lookup"><span data-stu-id="0adde-163">You can't use the Recover Deleted Items feature to recover an item that was deleted from an auto-expanded storage area.</span></span>
  
## <a name="auto-expanding-archiving-and-other-office-365-compliance-features"></a><span data-ttu-id="0adde-164">自動展開封存和其他 Office 365 合規性功能</span><span class="sxs-lookup"><span data-stu-id="0adde-164">Auto-expanding archiving and other Office 365 compliance features</span></span>

<span data-ttu-id="0adde-165">本章節說明自動展開封存和其他 Office 365 合規性和資料控管功能之間的功能。</span><span class="sxs-lookup"><span data-stu-id="0adde-165">This section explains the functionality between auto-expanding archiving and other Office 365 compliance and data governance features.</span></span>
  
- <span data-ttu-id="0adde-166">也會搜尋**電子文件探索**-當您使用 Office 365 電子文件探索工具，例如內容搜尋] 或 [就地 eDiscovery，自動展開封存中的額外儲存空間區域。</span><span class="sxs-lookup"><span data-stu-id="0adde-166">**eDiscovery** - When you use an Office 365 eDiscovery tool, such as Content Search or In-Place eDiscovery, the additional storage areas in an auto-expanded archive are also searched.</span></span>
    
- <span data-ttu-id="0adde-167">**保留**-當您讓信箱處於 [保留使用例如訴訟暫止的工具在 Exchange 線上] 或 [eDiscovery 案例保留與位於自動展開封存的保留原則中的安全性與合規性中心，內容也會處於暫止。</span><span class="sxs-lookup"><span data-stu-id="0adde-167">**Retention** - When you put a mailbox on hold by using tools such as Litigation Hold in Exchange Online or eDiscovery case holds and retention policies in the security and compliance center, content located in an auto-expanded archive is also placed on hold.</span></span>
    
- <span data-ttu-id="0adde-168">**通訊記錄管理 (MRM)** -如果您在 Exchange Online 中使用 MRM 刪除原則來永久刪除過期的信箱項目，過期的項目位於自動展開封存也會一併刪除。</span><span class="sxs-lookup"><span data-stu-id="0adde-168">**Messaging records management (MRM)** - If you use MRM deletion policies in Exchange Online to permanently delete expired mailbox items, expired items located in the auto-expanded archive will also be deleted.</span></span>
    
- <span data-ttu-id="0adde-169">**匯入服務**-您可以使用 Office 365 匯入服務將 PST 檔案匯入使用者的自動展開封存。</span><span class="sxs-lookup"><span data-stu-id="0adde-169">**Import service** - You can use the Office 365 Import service to import PST files to a user's auto-expanded archive.</span></span> <span data-ttu-id="0adde-170">您可以到使用者的封存信箱，最多 100 GB 的資料匯入從 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="0adde-170">You can import up to 100 GB of data from PST files to the user's archive mailbox.</span></span> 

## <a name="more-information"></a><span data-ttu-id="0adde-171">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="0adde-171">More information</span></span>

<span data-ttu-id="0adde-172">如需自動展開封存，請參閱詳細技術的詳細資訊[Office 365： 自動展開封存常見問題集](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/)。</span><span class="sxs-lookup"><span data-stu-id="0adde-172">For more technical details about auto-expanding archiving, see [Office 365: Auto-Expanding Archives FAQ](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/).</span></span>
