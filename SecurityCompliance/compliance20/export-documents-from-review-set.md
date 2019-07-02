---
title: 從檢閱集匯出文件
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
ms.openlocfilehash: 7c1daccab799b3967c6b8c1d577060d062c05a70
ms.sourcegitcommit: e323610df2df71c84f536e8a38650d33d8069e41
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2019
ms.locfileid: "34703786"
---
# <a name="export-documents-from-a-review-set"></a><span data-ttu-id="6fa54-102">從檢閱集匯出文件</span><span class="sxs-lookup"><span data-stu-id="6fa54-102">Export documents from a review set</span></span>

<span data-ttu-id="6fa54-103">您可以使用下列其中一種方法, 從審閱集中匯出簡報或外部考核的內容:</span><span class="sxs-lookup"><span data-stu-id="6fa54-103">You can export content for presentation or external review from a review set by one of the following methods:</span></span>

- [<span data-ttu-id="6fa54-104">下載檔案</span><span class="sxs-lookup"><span data-stu-id="6fa54-104">Download documents</span></span>](#download-documents-from-a-review-set)
 
- [<span data-ttu-id="6fa54-105">匯出檔</span><span class="sxs-lookup"><span data-stu-id="6fa54-105">Export documents</span></span>](#export-documents-from-a-review-set)

## <a name="download-documents-from-a-review-set"></a><span data-ttu-id="6fa54-106">從審閱集下載檔案</span><span class="sxs-lookup"><span data-stu-id="6fa54-106">Download documents from a review set</span></span>

<span data-ttu-id="6fa54-107">下載提供一種簡單的方法, 可從原生格式的審閱集下載內容。</span><span class="sxs-lookup"><span data-stu-id="6fa54-107">Download offers a simple way to download content from a review set in Native format.</span></span> <span data-ttu-id="6fa54-108">它會利用瀏覽器的資料傳輸功能, 讓下載準備就緒後就會出現瀏覽器提示。</span><span class="sxs-lookup"><span data-stu-id="6fa54-108">It leverages the browser’s data transfer features so a browser prompt will appear once a download is ready.</span></span> <span data-ttu-id="6fa54-109">使用此方法下載的檔案會壓縮到容器檔案中, 並將成為專案層級檔案。</span><span class="sxs-lookup"><span data-stu-id="6fa54-109">Files downloaded using this method will be zipped into a container file and will be item level files.</span></span> <span data-ttu-id="6fa54-110">這表示如果您選取附件, 您會自動收到包含附件的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="6fa54-110">This means that if you select an attachment, you will automatically receive the email with the attachment included.</span></span> <span data-ttu-id="6fa54-111">同樣地, 如果您選取內嵌在 word 檔中的 excel 試算表, 您會收到包含 excel 試算表的 word 檔。</span><span class="sxs-lookup"><span data-stu-id="6fa54-111">Similarly, if you select an excel spreadsheet that was embedded in a word document, you will receive the word document with the excel spreadsheet embedded.</span></span> <span data-ttu-id="6fa54-112">下載的專案會保留上次修改的日期, 可以視為檔案屬性。</span><span class="sxs-lookup"><span data-stu-id="6fa54-112">Downloaded items will preserve the last modified date which can be viewed as a file property.</span></span>

<span data-ttu-id="6fa54-113">若要從審閱集中下載內容, 請先選取您想要下載的檔案, 然後選取 [動作] 功能表下的 [下載]。</span><span class="sxs-lookup"><span data-stu-id="6fa54-113">To download content from a review set, start by selecting the files you want to download then select “Download” under the Actions menu.</span></span>

![自動產生電腦描述的螢幕擷取畫面](../media/eDiscoDownload.png)

## <a name="export-documents-from-a-review-set"></a><span data-ttu-id="6fa54-115">從檢閱集匯出文件</span><span class="sxs-lookup"><span data-stu-id="6fa54-115">Export documents from a review set</span></span>

<span data-ttu-id="6fa54-116">匯出可讓使用者自訂下載套件所包含的內容。</span><span class="sxs-lookup"><span data-stu-id="6fa54-116">Export allows users to customize the content that is included in the download package.</span></span> <span data-ttu-id="6fa54-117">它提供具有下列設定的設定頁面:</span><span class="sxs-lookup"><span data-stu-id="6fa54-117">It provides a configuration page with the following settings:</span></span>

### <a name="metadata-file"></a><span data-ttu-id="6fa54-118">元資料檔案</span><span class="sxs-lookup"><span data-stu-id="6fa54-118">Metadata file</span></span>

<span data-ttu-id="6fa54-119">這可以被視為您的「載入檔案」, 其中包含與匯出的檔案相關聯的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="6fa54-119">This can be considered your “load file” that contains metadata associated with the files you exported.</span></span> <span data-ttu-id="6fa54-120">如需元資料檔案中可用的欄位清單, 請\[參閱\]link。</span><span class="sxs-lookup"><span data-stu-id="6fa54-120">For a list of fields available in the metadata file, see \[link\].</span></span> <span data-ttu-id="6fa54-121">此檔案通常可由3個<sup>rd</sup>方程式的後續工具 ingested。</span><span class="sxs-lookup"><span data-stu-id="6fa54-121">This file can typically be ingested by 3<sup>rd</sup> party tools downstream.</span></span>

### <a name="tag-data"></a><span data-ttu-id="6fa54-122">標記資料</span><span class="sxs-lookup"><span data-stu-id="6fa54-122">Tag data</span></span>

<span data-ttu-id="6fa54-123">此內容會新增為元資料檔案中的欄位。</span><span class="sxs-lookup"><span data-stu-id="6fa54-123">This content would be added as fields in the metadata file.</span></span> <span data-ttu-id="6fa54-124">它包含所有在複查集中套用的標記資訊。</span><span class="sxs-lookup"><span data-stu-id="6fa54-124">It contains all of the tag information applied in review sets.</span></span>

### <a name="text-files"></a><span data-ttu-id="6fa54-125">文字檔</span><span class="sxs-lookup"><span data-stu-id="6fa54-125">Text files</span></span>

<span data-ttu-id="6fa54-126">可以為從審查集匯出的每個檔案產生文字檔。</span><span class="sxs-lookup"><span data-stu-id="6fa54-126">Text files can be generated for each file exported from a review set.</span></span> <span data-ttu-id="6fa54-127">通常, 服務合作夥伴會將這些檔案作為 ingesting 資料的一部分, 做為3個<sup>rd</sup>方程式的後續工具。</span><span class="sxs-lookup"><span data-stu-id="6fa54-127">Often times these files are required by service partners as part of ingesting data into 3<sup>rd</sup> party tools downstream.</span></span>

### <a name="redacted-files"></a><span data-ttu-id="6fa54-128">Redacted 檔案</span><span class="sxs-lookup"><span data-stu-id="6fa54-128">Redacted files</span></span>

<span data-ttu-id="6fa54-129">如果在審閱期間產生 redacted 的 Pdf, 這些檔案會在匯出期間使用。</span><span class="sxs-lookup"><span data-stu-id="6fa54-129">If redacted PDFs are generated during review, these files are available during export.</span></span> <span data-ttu-id="6fa54-130">使用者可以決定是否僅匯出本機檔案, 或將具有密文的 natives 取代為 Pdf 中燒制。</span><span class="sxs-lookup"><span data-stu-id="6fa54-130">Users can decide whether to export native files only or to replace natives that have redactions with the burned in PDFs.</span></span>

### <a name="export-location"></a><span data-ttu-id="6fa54-131">匯出位置</span><span class="sxs-lookup"><span data-stu-id="6fa54-131">Export Location</span></span>

<span data-ttu-id="6fa54-132">如果在匯出時提供詳細資料, 則匯出的內容會傳遞至 Microsoft 提供的 Azure blob 或客戶的 blob。</span><span class="sxs-lookup"><span data-stu-id="6fa54-132">Exported content is delivered to either a Microsoft provided Azure blob or a customer’s blob can be used if the details are provided at export.</span></span>

### <a name="export-structure"></a><span data-ttu-id="6fa54-133">匯出結構</span><span class="sxs-lookup"><span data-stu-id="6fa54-133">Export Structure</span></span>

<span data-ttu-id="6fa54-134">從審閱集匯出內容時, 會將內容組織在下列結構中。</span><span class="sxs-lookup"><span data-stu-id="6fa54-134">When content is exported from a review set, the content is organized in the following structure.</span></span>

  - <span data-ttu-id="6fa54-135">根資料夾–下載識別碼</span><span class="sxs-lookup"><span data-stu-id="6fa54-135">Root folder – Download ID</span></span>
    
      - <span data-ttu-id="6fa54-136">匯出\_load\_file .csv = metadata file</span><span class="sxs-lookup"><span data-stu-id="6fa54-136">Export\_load\_file.csv = metadata file</span></span>
    
      - <span data-ttu-id="6fa54-137">Summary = 包含匯出統計資料的摘要檔案</span><span class="sxs-lookup"><span data-stu-id="6fa54-137">Summary.txt = a summary file with export statistics</span></span>
    
      - <span data-ttu-id="6fa54-138">輸入\_或原\_生檔案 = 包含所有原生檔案</span><span class="sxs-lookup"><span data-stu-id="6fa54-138">Input\_or native\_files = contains all native files</span></span>
    
      - <span data-ttu-id="6fa54-139">錯誤\_檔案 = 包含匯出所包含的任何錯誤檔案</span><span class="sxs-lookup"><span data-stu-id="6fa54-139">Error\_files = contains any error files included in the export</span></span>
        
          - <span data-ttu-id="6fa54-140">ExtractionError –含有任何可用的中繼資料的 csv, 這些檔案未從父檔案正確解壓縮</span><span class="sxs-lookup"><span data-stu-id="6fa54-140">ExtractionError – a csv that contains any available metadata of files that were not properly extracted from parent files</span></span>
        
          - <span data-ttu-id="6fa54-141">ProcessingError –含有處理錯誤的內容。</span><span class="sxs-lookup"><span data-stu-id="6fa54-141">ProcessingError – content with processing errors.</span></span> <span data-ttu-id="6fa54-142">此內容的專案層級表示如果附件發生處理錯誤, 包含附件的電子郵件會包含在此資料夾中。</span><span class="sxs-lookup"><span data-stu-id="6fa54-142">This content is item level meaning if an attachment experienced a processing error, the email that contains the attachment will be included in this folder.</span></span>
    
      - <span data-ttu-id="6fa54-143">解壓縮\_的\_文字檔 = 包含處理時所產生的所有解壓縮文字檔。</span><span class="sxs-lookup"><span data-stu-id="6fa54-143">Extracted\_text\_files = contains all of the extracted text files generated at processing.</span></span>