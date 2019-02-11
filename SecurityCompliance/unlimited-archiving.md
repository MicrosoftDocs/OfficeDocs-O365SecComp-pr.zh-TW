---
title: Office 365 中不受限制封存概觀
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 37cdbb02-a24a-4093-8bdb-2a7f0b3a19ee
description: 了解自動展開封存 Office 365 中，其會提供的 Exchange Online 信箱執行不受限制的封存儲存區。
ms.openlocfilehash: 83eb49b3f2a7da418b61e509f44023809ed396c3
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2019
ms.locfileid: "29740815"
---
# <a name="overview-of-unlimited-archiving-in-office-365"></a><span data-ttu-id="44dad-103">Office 365 中不受限制封存概觀</span><span class="sxs-lookup"><span data-stu-id="44dad-103">Overview of unlimited archiving in Office 365</span></span>

<span data-ttu-id="44dad-p101">Office 365 中封存信箱會提供使用者對其他信箱的儲存空間。啟用使用者的封存信箱後，最多 100 GB 的額外儲存空間使用。當達到 100 GB 儲存配額時，組織都封存信箱的要求額外儲存空間來連絡 Microsoft。那是不會再大小寫。Office 365 （稱為 「*自動展開封存*） 中的新不受限制封存功能提供不受限制的封存信箱中的儲存空間量。現在，當達到封存信箱中的儲存配額，Office 365 自動增加的封存，這表示使用者不會執行移出信箱的儲存空間和系統管理員不需要要求的封存信箱的額外儲存空間.</span><span class="sxs-lookup"><span data-stu-id="44dad-p101">In Office 365, archive mailboxes provide users with additional mailbox storage space. After a user's archive mailbox is enabled, up to 100 GB of additional storage is available. When the 100 GB storage quota is reached, organizations had to contact Microsoft to request additional storage space for an archive mailbox. That's no longer the case. The new unlimited archiving feature in Office 365 (called *auto-expanding archiving*) provides an unlimited amount of storage in archive mailboxes. Now, when the storage quota in the archive mailbox is reached, Office 365 automatically increases the size of the archive, which means that users won't run out of mailbox storage space and administrators won't have to request additional storage for archive mailboxes.</span></span>
  
<span data-ttu-id="44dad-110">如需逐步說明的開啟自動展開封存，請參閱[啟用 Office 365 中沒有限制之封存](enable-unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="44dad-110">For step-by-step instructions for turning on auto-expanding archiving, see [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="44dad-p102">自動展開封存也支援共用的信箱。若要啟用共用信箱的封存，Exchange Online 計劃 2 授權或 Exchange Online 計劃 1 授權來搭配 Exchange Online 封存的授權，則需要。</span><span class="sxs-lookup"><span data-stu-id="44dad-p102">Auto-expanding archiving also supports shared mailboxes. To enable the archive for a shared mailbox, an Exchange Online Plan 2 license or an Exchange Online Plan 1 license with an Exchange Online Archiving license is required.</span></span> 
  
## <a name="how-auto-expanding-archiving-works"></a><span data-ttu-id="44dad-113">如何自動展開封存的運作</span><span class="sxs-lookup"><span data-stu-id="44dad-113">How auto-expanding archiving works</span></span>

<span data-ttu-id="44dad-p103">為先前所述]、 [其他信箱使用者的封存信箱啟用時建立的儲存空間。啟用自動展開封存時，Office 365 定期檢查封存信箱的大小。當封存信箱取得接近其儲存限制時，Office 365 會自動建立封存的額外儲存空間。如果使用者是執行此額外儲存空間不足，Office 365 會將更多儲存空間新增至使用者的封存。此程序就會發生自動，這表示系統管理員不需要要求其他封存存放區] 或 [管理自動展開封存。</span><span class="sxs-lookup"><span data-stu-id="44dad-p103">As previously explained, additional mailbox storage space is created when a user's archive mailbox is enabled. When auto-expanding archiving is enabled, Office 365 periodically checks the size of the archive mailbox. When an archive mailbox gets close to its storage limit, Office 365 automatically creates additional storage space for the archive. If the user runs out of this additional storage space, Office 365 adds more storage space to the user's archive. This process happens automatically, which means administrators don't have to request additional archive storage or manage auto-expanding archiving.</span></span> 
  
<span data-ttu-id="44dad-119">以下是程序的快速概觀 （英文）。</span><span class="sxs-lookup"><span data-stu-id="44dad-119">Here's a quick overview of the process.</span></span>
  
![自動展開封存程序概觀](media/74355385-d990-44fe-8a87-6c3639d1f63f.png)
  
1. <span data-ttu-id="44dad-p104">使用者信箱或共用的信箱啟用封存。建立封存信箱與 100 GB 的存放區空間、 且封存信箱的警告配額設為 90 GB。</span><span class="sxs-lookup"><span data-stu-id="44dad-p104">Archiving is enabled for a user mailbox or a shared mailbox. An archive mailbox with 100 GB of storage space is created, and the warning quota for the archive mailbox is set to 90 GB.</span></span>
    
2. <span data-ttu-id="44dad-p105">系統管理員啟用自動展開封存信箱。當封存信箱 （包括可復原的項目] 資料夾） 達到 90 GB，它會轉換為自動展開封存，然後 Office 365 新增至封存儲存空間。請注意其可採取的額外儲存空間來佈建多達 30 天。</span><span class="sxs-lookup"><span data-stu-id="44dad-p105">An administrator enables auto-expanding archiving for the mailbox. Then, when the archive mailbox (including the Recoverable Items folder) reaches 90 GB, it's converted to an auto-expanding archive, and Office 365 adds storage space to the archive. Note that it can take up to 30 days for the additional storage space to be provisioned.</span></span>
    
3. <span data-ttu-id="44dad-126">Office 365 自動封存在必要時將更多儲存空間。</span><span class="sxs-lookup"><span data-stu-id="44dad-126">Office 365 automatically adds more storage space to the archive when necessary.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="44dad-p106">如果信箱處於保留狀態或指派給 Office 365 保留原則、 封存信箱儲存配額增加為 110 GB 時自動展開封存已啟用。同樣地，增加封存警告配額為 100 GB。</span><span class="sxs-lookup"><span data-stu-id="44dad-p106">If a mailbox is placed on hold or assigned to an Office 365 retention policy, the storage quota for the archive maibox is increased to 110 GB when auto-expanding archiving is enabled. Similarly, the archive warning quota is increased to 100 GB.</span></span>

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a><span data-ttu-id="44dad-129">新取得移至其他封存儲存空間？</span><span class="sxs-lookup"><span data-stu-id="44dad-129">What gets moved to the additional archive storage space?</span></span>

<span data-ttu-id="44dad-p107">若要有效使用自動展開封存儲存，可能會取得移動資料夾。Office 365 會決定哪些資料夾要取得移動額外儲存空間新增至封存時。移動資料夾時，在 Outlook 中的資料夾清單的封存部分原始資料夾下自動建立子資料夾。這個新的子資料夾會指向已移動的項目。Office 365 使用命名此資料夾的命名慣例是**\<資料夾名稱\>_yyyy （建立上 mmm dd，yyyy h_mm）**，其中：</span><span class="sxs-lookup"><span data-stu-id="44dad-p107">To make efficient use of auto-expanding archive storage, folders might get moved. Office 365 determines which folders get moved when additional storage is added to the archive. When a folder is moved, a subfolder is automatically created under the original folder in the archive portion of the folder list in Outlook. This new subfolder points to the items that were moved. The naming convention that Office 365 uses to name this folder is **\<folder name\>_yyyy (Created on mmm dd, yyyy h_mm)**, where:</span></span> 
  
- <span data-ttu-id="44dad-135">**yyyy**是收到的郵件] 資料夾中的年份。</span><span class="sxs-lookup"><span data-stu-id="44dad-135">**yyyy** is the year the messages in the folder were received.</span></span> 
    
- <span data-ttu-id="44dad-136">**mmm dd，yyyy h_m**是日期與時間的子資料夾以 UTC 格式，根據使用者的時區和地區設定在 Outlook 中的建立的 Office 365。</span><span class="sxs-lookup"><span data-stu-id="44dad-136">**mmm dd, yyyy h_m** is the date and time that the subfolder was created by Office 365, in UTC format, based on the user's time zone and regional settings in Outlook.</span></span> 
    
<span data-ttu-id="44dad-137">下列螢幕擷取畫面顯示的資料夾清單之前和之後郵件會自動展開封存中移。</span><span class="sxs-lookup"><span data-stu-id="44dad-137">The following screen shots show a folder list before and after messages are moved in an auto-expanded archive.</span></span>
  
 <span data-ttu-id="44dad-138">**新增額外儲存空間之前**</span><span class="sxs-lookup"><span data-stu-id="44dad-138">**Before additional storage is added**</span></span>
  
![資料夾清單] 的前已佈建自動展開封存的封存信箱](media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)
  
 <span data-ttu-id="44dad-140">**新增額外儲存空間之後**</span><span class="sxs-lookup"><span data-stu-id="44dad-140">**After additional storage is added**</span></span>
  
![資料夾清單中的封存信箱之後自動展開封存已佈建](media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)
  
## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a><span data-ttu-id="44dad-142">Outlook 需求存取自動展開封存中的項目</span><span class="sxs-lookup"><span data-stu-id="44dad-142">Outlook requirements for accessing items in an auto-expanded archive</span></span>

<span data-ttu-id="44dad-143">若要存取儲存在自動展開封存中的郵件，使用者必須使用下列 Outlook 用戶端之一：</span><span class="sxs-lookup"><span data-stu-id="44dad-143">To access messages that are stored in an auto-expanded archive, users have to use one of the following Outlook clients:</span></span>
  
- <span data-ttu-id="44dad-144">Outlook 2016 或 Outlook 2019 windows</span><span class="sxs-lookup"><span data-stu-id="44dad-144">Outlook 2016 or Outlook 2019 for Windows</span></span>
    
- <span data-ttu-id="44dad-145">Outlook 網頁版</span><span class="sxs-lookup"><span data-stu-id="44dad-145">Outlook on the web</span></span> 
    
- <span data-ttu-id="44dad-146">Outlook 2016 或 Outlook 2019 for Mac</span><span class="sxs-lookup"><span data-stu-id="44dad-146">Outlook 2016 or Outlook 2019 for Mac</span></span> 
    
> [!NOTE]
> <span data-ttu-id="44dad-p108">Outlook 2013 使用者可以原本已儲存封存信箱的存取項目。他們將無法存取項目移至其他封存存放區。</span><span class="sxs-lookup"><span data-stu-id="44dad-p108">Outlook 2013 users can only access items that were originally stored in their archive mailbox. They won't be able to access items that are moved to additional archive storage.</span></span> 
  
<span data-ttu-id="44dad-149">以下是使用 Outlook 或 Outlook 存取郵件中自動展開封存儲存在 web 上的時所應考量事項。</span><span class="sxs-lookup"><span data-stu-id="44dad-149">Here are some things to consider when using Outlook or Outlook on the web to access messages stored in an auto-expanded archive.</span></span>
  
- <span data-ttu-id="44dad-150">您可以存取您的封存信箱，包括類已移至 [自動展開存放區] 區域中的任何資料夾。</span><span class="sxs-lookup"><span data-stu-id="44dad-150">You can access any folder in your archive mailbox, including ones that were moved to the auto-expanded storage area.</span></span>
    
- <span data-ttu-id="44dad-p109">您可以搜尋已移至其他儲存區只能由搜尋資料夾本身的項目。這表示您必須選取資料夾清單] 以選取 [**目前的資料夾**選項為搜尋範圍中的 [封存] 資料夾。同樣地，如果自動展開儲存區中的資料夾包含子資料夾，您必須分別搜尋每一個子資料夾。</span><span class="sxs-lookup"><span data-stu-id="44dad-p109">You can search for items that were moved to an additional storage area only by searching the folder itself. This means you have to select the archive folder in the folder list to select the **Current Folder** option as the search scope. Similarly, if a folder in an auto-expanded storage area contains subfolders, you have to search each subfolder separately.</span></span> 
    
- <span data-ttu-id="44dad-154">Outlook 中的項目計數和 （在 Outlook 和 Outlook web 上的） 的讀取/未閱讀計數自動展開封存中可能不正確。</span><span class="sxs-lookup"><span data-stu-id="44dad-154">Item counts in Outlook and Read/Unread counts (in Outlook and Outlook on the web ) in an auto-expanded archive might not be accurate.</span></span>
    
- <span data-ttu-id="44dad-155">您可以刪除自動展開存放區] 區域中，會指向子資料夾中的項目，但無法刪除資料夾本身。</span><span class="sxs-lookup"><span data-stu-id="44dad-155">You can delete items in a subfolder that points to an auto-expanded storage area, but the folder itself can't be deleted.</span></span>
    
- <span data-ttu-id="44dad-156">您無法復原從自動展開儲存區中已刪除的項目使用的復原刪除的郵件功能。</span><span class="sxs-lookup"><span data-stu-id="44dad-156">You can't use the Recover Deleted Items feature to recover an item that was deleted from an auto-expanded storage area.</span></span>
  
## <a name="auto-expanding-archiving-and-other-office-365-compliance-features"></a><span data-ttu-id="44dad-157">自動展開封存和其他 Office 365 的符合性功能</span><span class="sxs-lookup"><span data-stu-id="44dad-157">Auto-expanding archiving and other Office 365 compliance features</span></span>

<span data-ttu-id="44dad-158">本節說明自動展開封存和其他 Office 365 規範和資料控管功能之間的功能。</span><span class="sxs-lookup"><span data-stu-id="44dad-158">This section explains the functionality between auto-expanding archiving and other Office 365 compliance and data governance features.</span></span>
  
- <span data-ttu-id="44dad-159">**eDiscovery** -使用 Office 365 eDiscovery 工具，例如內容搜尋] 或 [就地 eDiscovery 自動展開封存中的額外儲存空間區域時也會搜尋。</span><span class="sxs-lookup"><span data-stu-id="44dad-159">**eDiscovery** - When you use an Office 365 eDiscovery tool, such as Content Search or In-Place eDiscovery, the additional storage areas in an auto-expanded archive are also searched.</span></span>
    
- <span data-ttu-id="44dad-160">**保留**-時讓信箱處於功能使用工具，例如訴訟暫止狀態 Exchange 線上] 或 [eDiscovery 案例包含，也是位於自動展開封存 Office 365 安全性 & 內容的規範中心中的保留原則處於保留狀態。</span><span class="sxs-lookup"><span data-stu-id="44dad-160">**Retention** - When you put a mailbox on hold by using tools such as Litigation Hold in Exchange Online or eDiscovery case holds and retention policies in the Office 365 Security & Compliance Center, content located in an auto-expanded archive is also placed on hold.</span></span>
    
- <span data-ttu-id="44dad-161">**通訊記錄管理 (MRM)** -如果您在 Exchange Online 中使用 MRM 刪除原則永久刪除過期的信箱項目、 到期的項目位於自動展開封存也都會刪除。</span><span class="sxs-lookup"><span data-stu-id="44dad-161">**Messaging records management (MRM)** - If you use MRM deletion policies in Exchange Online to permanently delete expired mailbox items, expired items located in the auto-expanded archive will also be deleted.</span></span>
    
- <span data-ttu-id="44dad-p110">**匯入服務**-您可以使用匯入 Office 365 服務至 PST 檔案匯入的使用者自動展開封存。您可以在使用者的封存信箱 PST 檔案匯最大 100 GB 的資料。</span><span class="sxs-lookup"><span data-stu-id="44dad-p110">**Import service** - You can use the Office 365 Import service to import PST files to a user's auto-expanded archive. You can import up to 100 GB of data from PST files to the user's archive mailbox.</span></span> 

## <a name="more-information"></a><span data-ttu-id="44dad-164">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="44dad-164">More information</span></span>

<span data-ttu-id="44dad-165">如需自動展開封存，請參閱更多技術詳細資料[Office 365： 自動展開封存常見問題集](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/)。</span><span class="sxs-lookup"><span data-stu-id="44dad-165">For more technical details about auto-expanding archiving, see [Office 365: Auto-Expanding Archives FAQ](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/).</span></span>