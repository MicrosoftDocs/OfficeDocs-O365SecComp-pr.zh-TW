---
title: 進階編製索引的調查資料
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 2e2077fa5ee5333a563470d5bcbb140364bc0ba2
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34150775"
---
# <a name="advanced-indexing-of-data-for-an-investigation"></a><span data-ttu-id="97366-102">進階編製索引的調查資料</span><span class="sxs-lookup"><span data-stu-id="97366-102">Advanced indexing of data for an investigation</span></span>

<span data-ttu-id="97366-103">Live 系統中的內容可以將多個原因包括影像、 不支援的檔案類型或時遇到索引檔案大小限制存在已部分編制索引。</span><span class="sxs-lookup"><span data-stu-id="97366-103">Content in the live system can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span> <span data-ttu-id="97366-104">當您正在處理的資料不要大高風險時，想要確定您的搜尋擷取您想要調查的所有資料。</span><span class="sxs-lookup"><span data-stu-id="97366-104">When you are dealing with high risk data spill, you want to make sure that your search captured all data that you want to investigate.</span></span> <span data-ttu-id="97366-105">感興趣的人員新增至資料調查後，已被視為的 Office 365 中的所有內容已局部編製索引都時，使其成為完整搜尋重新處理。</span><span class="sxs-lookup"><span data-stu-id="97366-105">When a person of interest is added to a Data investigation, any content in Office 365 that was deemed as partially indexed is re-processed to make it fully searchable.</span></span> <span data-ttu-id="97366-106">此程序稱為 「*進階編製索引*」。</span><span class="sxs-lookup"><span data-stu-id="97366-106">This process is called *Advanced indexing*.</span></span> 

<span data-ttu-id="97366-107">若要深入了解關於處理 Office 365 和已局部編製索引的項目中支援的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="97366-107">To learn more about processing support in Office 365 and partially indexed items, see:</span></span>

- <span data-ttu-id="97366-108">[在 [資料調查支援的檔案類型](supported-filetypes-datainvestigations.md)</span><span class="sxs-lookup"><span data-stu-id="97366-108">[Supported file types in Data Investigations](supported-filetypes-datainvestigations.md)</span></span>

- [<span data-ttu-id="97366-109">位於 Office 365 中內容搜尋的已局部編製索引項目</span><span class="sxs-lookup"><span data-stu-id="97366-109">Partially indexed items in Content Search in Office 365</span></span>](https://docs.microsoft.com/en-us/office365/securitycompliance/partially-indexed-items-in-content-search)

- [<span data-ttu-id="97366-110">Exchange 搜尋編製索引的檔案格式</span><span class="sxs-lookup"><span data-stu-id="97366-110">File formats indexed by Exchange Search</span></span>](https://docs.microsoft.com/en-us/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="97366-111">SharePoint Server 中預設編目的檔案副檔名及剖析的檔案類型</span><span class="sxs-lookup"><span data-stu-id="97366-111">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/en-us/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="97366-112">檢視進階索引的結果</span><span class="sxs-lookup"><span data-stu-id="97366-112">Viewing Advanced indexing results</span></span>

<span data-ttu-id="97366-113">進階的索引程序完成之後，您可以取得的重新處理效率了解。</span><span class="sxs-lookup"><span data-stu-id="97366-113">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of re-processing.</span></span>  <span data-ttu-id="97366-114">在檢視編製索引的感興趣的人員，圖形會列出所有的項目新增至*混合式索引*。</span><span class="sxs-lookup"><span data-stu-id="97366-114">In the People of interest indexing view, the graph lists all items added to the *hybrid index*.</span></span>  <span data-ttu-id="97366-115">混合式 index 是資料調查 （預覽） 重新處理的內容，儲存位置。</span><span class="sxs-lookup"><span data-stu-id="97366-115">The hybrid index is where Data Investigations (Preview) stores the re-processed content.</span></span>

<span data-ttu-id="97366-116">此圖形也包含需要修復的項目數與另一個圖形的檔案類型的錯誤。</span><span class="sxs-lookup"><span data-stu-id="97366-116">The graph also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="97366-117">如需詳細資訊，請參閱 <<c0>錯誤修復時處理資料。</span><span class="sxs-lookup"><span data-stu-id="97366-117">For more information, see [Error remediation when processing data](error-remediation.md).</span></span>

## <a name="updating-advanced-indexes-for-people-of-interest"></a><span data-ttu-id="97366-118">更新進階的索引感興趣的人員</span><span class="sxs-lookup"><span data-stu-id="97366-118">Updating Advanced indexes for people of interest</span></span>

<span data-ttu-id="97366-119">當感興趣的人員新增至資料調查後時，所有已局部編製索引的項目會重新處理。</span><span class="sxs-lookup"><span data-stu-id="97366-119">When a person of interest is added to a data investigation, all partially indexed items are re-processed.</span></span> <span data-ttu-id="97366-120">不過，經過一段時間，更局部編製索引的項目可能會新增至使用者的信箱或 OneDrive 帳戶。</span><span class="sxs-lookup"><span data-stu-id="97366-120">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="97366-121">視需要，您可以更新索引。</span><span class="sxs-lookup"><span data-stu-id="97366-121">When needed, you can update the indexes.</span></span>

> [!NOTE]
> <span data-ttu-id="97366-122">更新人員感興趣的索引是一個長時間執行的程序。</span><span class="sxs-lookup"><span data-stu-id="97366-122">Updating people of interest indexes is a long running process.</span></span> <span data-ttu-id="97366-123">最好不要更新索引中調查每天的一次以上。</span><span class="sxs-lookup"><span data-stu-id="97366-123">It's recommended that you don't update indexes more than once per day in an investigation.</span></span>
