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
ms.openlocfilehash: 14efa58305e1963aa43c0c94fb208e5391c87119
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155065"
---
# <a name="export-documents-from-a-review-set"></a><span data-ttu-id="e4109-102">從檢閱集匯出文件</span><span class="sxs-lookup"><span data-stu-id="e4109-102">Export documents from a review set</span></span>

<span data-ttu-id="e4109-103">匯出內容從檢閱集可以透過 3 不同的方法來完成：</span><span class="sxs-lookup"><span data-stu-id="e4109-103">Exporting content from a review set can be accomplished via 3 different methods:</span></span>

## <a name="download"></a><span data-ttu-id="e4109-104">下載</span><span class="sxs-lookup"><span data-stu-id="e4109-104">Download</span></span>

<span data-ttu-id="e4109-105">下載提供簡單的方法，從原生格式設定的設定檢閱下載內容。</span><span class="sxs-lookup"><span data-stu-id="e4109-105">Download offers a simple way to download content from a review set in Native format.</span></span> <span data-ttu-id="e4109-106">它利用瀏覽器的資料傳輸功能，因此下載已準備好之後，就會顯示瀏覽器提示。</span><span class="sxs-lookup"><span data-stu-id="e4109-106">It leverages the browser’s data transfer features so a browser prompt will appear once a download is ready.</span></span> <span data-ttu-id="e4109-107">檔案下載使用此方法會壓縮成容器檔案，將項目層級的檔案。</span><span class="sxs-lookup"><span data-stu-id="e4109-107">Files downloaded using this method will be zipped into a container file and will be item level files.</span></span> <span data-ttu-id="e4109-108">這表示，如果您選取附件，您就會自動接收電子郵件包含附件。</span><span class="sxs-lookup"><span data-stu-id="e4109-108">This means that if you select an attachment, you will automatically receive the email with the attachment included.</span></span> <span data-ttu-id="e4109-109">同樣地，如果您選取 [已 excel 試算表內嵌於 word 文件，您會收到 word 文件與內嵌的 excel 試算表。</span><span class="sxs-lookup"><span data-stu-id="e4109-109">Similarly, if you select an excel spreadsheet that was embedded in a word document, you will receive the word document with the excel spreadsheet embedded.</span></span> <span data-ttu-id="e4109-110">已下載的項目會保留檔案屬性為可檢視的上次修改的日期。</span><span class="sxs-lookup"><span data-stu-id="e4109-110">Downloaded items will preserve the last modified date which can be viewed as a file property.</span></span>

<span data-ttu-id="e4109-111">若要下載的內容從檢閱設定，啟動選取您要下載，然後選取 [動作] 功能表底下的 [「 下載 」 的檔案。</span><span class="sxs-lookup"><span data-stu-id="e4109-111">To download content from a review set, start by selecting the files you want to download then select “Download” under the Actions menu.</span></span>

![說明自動產生之電腦的螢幕擷取畫面](../media/eDiscoDownload.png)

## <a name="export"></a><span data-ttu-id="e4109-113">匯出</span><span class="sxs-lookup"><span data-stu-id="e4109-113">Export</span></span>

<span data-ttu-id="e4109-114">匯出可讓使用者自訂隨附的下載套件中的內容。</span><span class="sxs-lookup"><span data-stu-id="e4109-114">Export allows users to customize the content that is included in the download package.</span></span> <span data-ttu-id="e4109-115">它提供設定] 頁面上使用下列設定：</span><span class="sxs-lookup"><span data-stu-id="e4109-115">It provides a configuration page with the following settings:</span></span>

### <a name="metadata-file"></a><span data-ttu-id="e4109-116">中繼資料檔案</span><span class="sxs-lookup"><span data-stu-id="e4109-116">Metadata file</span></span>

> <span data-ttu-id="e4109-117">這可視為您 「 載入檔案"，其中包含您匯出的檔案相關聯的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="e4109-117">This can be considered your “load file” that contains metadata associated with the files you exported.</span></span> <span data-ttu-id="e4109-118">如需中繼資料檔案中可用的欄位的清單，請參閱\[連結\]。</span><span class="sxs-lookup"><span data-stu-id="e4109-118">For a list of fields available in the metadata file, see \[link\].</span></span> <span data-ttu-id="e4109-119">此檔案通常可以 ingested 3<sup>rd</sup>廠商工具所傳輸。</span><span class="sxs-lookup"><span data-stu-id="e4109-119">This file can typically be ingested by 3<sup>rd</sup> party tools downstream.</span></span>

### <a name="tag-data"></a><span data-ttu-id="e4109-120">標記資料</span><span class="sxs-lookup"><span data-stu-id="e4109-120">Tag data</span></span>

> <span data-ttu-id="e4109-121">此內容會新增為中繼資料檔案中的欄位。</span><span class="sxs-lookup"><span data-stu-id="e4109-121">This content would be added as fields in the metadata file.</span></span> <span data-ttu-id="e4109-122">它包含所有檢閱組中套用的標籤資訊。</span><span class="sxs-lookup"><span data-stu-id="e4109-122">It contains all of the tag information applied in review sets.</span></span>

### <a name="text-files"></a><span data-ttu-id="e4109-123">文字檔</span><span class="sxs-lookup"><span data-stu-id="e4109-123">Text files</span></span>

> <span data-ttu-id="e4109-124">文字檔案可以產生的每個檢閱設定從匯出的檔案。</span><span class="sxs-lookup"><span data-stu-id="e4109-124">Text files can be generated for each file exported from a review set.</span></span> <span data-ttu-id="e4109-125">通常時間這些檔案所需的服務合作夥伴一部分 ingesting 資料到 3<sup>rd</sup>廠商工具傳輸。</span><span class="sxs-lookup"><span data-stu-id="e4109-125">Often times these files are required by service partners as part of ingesting data into 3<sup>rd</sup> party tools downstream.</span></span>

### <a name="redacted-files"></a><span data-ttu-id="e4109-126">Redacted 的檔案</span><span class="sxs-lookup"><span data-stu-id="e4109-126">Redacted files</span></span>

> <span data-ttu-id="e4109-127">如果檢閱期間所產生 redacted 的 Pdf，這些檔案匯出期間都使用。</span><span class="sxs-lookup"><span data-stu-id="e4109-127">If redacted PDFs are generated during review, these files are available during export.</span></span> <span data-ttu-id="e4109-128">使用者可以決定是否要匯出僅適用於原生檔案，或取代人民 Pdf 中具有與燒錄 redactions。</span><span class="sxs-lookup"><span data-stu-id="e4109-128">Users can decide whether to export native files only or to replace natives that have redactions with the burned in PDFs.</span></span>

### <a name="export-location"></a><span data-ttu-id="e4109-129">匯出的位置</span><span class="sxs-lookup"><span data-stu-id="e4109-129">Export Location</span></span>

> <span data-ttu-id="e4109-130">匯出的內容會傳遞至下列一項 Microsoft 提供您可以使用 Azure blob 或客戶的 blob，如果在匯出並提供詳細資料。</span><span class="sxs-lookup"><span data-stu-id="e4109-130">Exported content is delivered to either a Microsoft provided Azure blob or a customer’s blob can be used if the details are provided at export.</span></span>

## <a name="export-structure"></a><span data-ttu-id="e4109-131">匯出結構</span><span class="sxs-lookup"><span data-stu-id="e4109-131">Export Structure</span></span>

<span data-ttu-id="e4109-132">當內容來自檢閱設定匯出時，內容被組織中的下列結構。</span><span class="sxs-lookup"><span data-stu-id="e4109-132">When content is exported from a review set, the content is organized in the following structure.</span></span>

  - <span data-ttu-id="e4109-133">根資料夾 – 下載識別碼</span><span class="sxs-lookup"><span data-stu-id="e4109-133">Root folder – Download ID</span></span>
    
      - <span data-ttu-id="e4109-134">匯出\_載入\_file.csv = 中繼資料檔案</span><span class="sxs-lookup"><span data-stu-id="e4109-134">Export\_load\_file.csv = metadata file</span></span>
    
      - <span data-ttu-id="e4109-135">Summary.txt = 匯出統計資料摘要檔案</span><span class="sxs-lookup"><span data-stu-id="e4109-135">Summary.txt = a summary file with export statistics</span></span>
    
      - <span data-ttu-id="e4109-136">輸入\_或原生\_檔案 = 包含所有的原生檔案</span><span class="sxs-lookup"><span data-stu-id="e4109-136">Input\_or native\_files = contains all native files</span></span>
    
      - <span data-ttu-id="e4109-137">錯誤\_檔案 = 包含任何包含在匯出的錯誤檔案</span><span class="sxs-lookup"><span data-stu-id="e4109-137">Error\_files = contains any error files included in the export</span></span>
        
          - <span data-ttu-id="e4109-138">ExtractionError – csv 包含不正確地從父檔案解壓縮的任何的檔案可用的中繼資料</span><span class="sxs-lookup"><span data-stu-id="e4109-138">ExtractionError – a csv that contains any available metadata of files that were not properly extracted from parent files</span></span>
        
          - <span data-ttu-id="e4109-139">ProcessingError – 與處理錯誤的內容。</span><span class="sxs-lookup"><span data-stu-id="e4109-139">ProcessingError – content with processing errors.</span></span> <span data-ttu-id="e4109-140">此內容是表示如果附件時發生錯誤處理，包含附件的電子郵件將會包含在此資料夾的項目層級。</span><span class="sxs-lookup"><span data-stu-id="e4109-140">This content is item level meaning if an attachment experienced a processing error, the email that contains the attachment will be included in this folder.</span></span>
    
      - <span data-ttu-id="e4109-141">擷取\_文字\_檔案 = 包含所有在處理所產生的擷取的文字檔案。</span><span class="sxs-lookup"><span data-stu-id="e4109-141">Extracted\_text\_files = contains all of the extracted text files generated at processing.</span></span>

## <a name="review-set"></a><span data-ttu-id="e4109-142">檢閱設定</span><span class="sxs-lookup"><span data-stu-id="e4109-142">review set</span></span>

<span data-ttu-id="e4109-143">內容可以新增至另一個檢閱設定。</span><span class="sxs-lookup"><span data-stu-id="e4109-143">Content can be added to another review set.</span></span>