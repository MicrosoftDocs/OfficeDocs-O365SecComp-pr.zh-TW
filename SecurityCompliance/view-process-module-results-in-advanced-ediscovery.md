---
title: 在 Office 365 進階電子文件探索中檢視處理程序模組結果
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c6f016cb-409f-4ae9-911c-1395cf0c86ea
description: '了解如何尋找 Office 365 進階 eDiscovery，包括任務狀態及摘要的程序中執行的程序模組的結果。  '
ms.openlocfilehash: 01093b0230aaf78ab7ccf1235f0874a0b69aa1bd
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526168"
---
# <a name="view-process-module-results-in-office-365-advanced-ediscovery"></a><span data-ttu-id="1d612-103">在 Office 365 進階電子文件探索中檢視處理程序模組結果</span><span class="sxs-lookup"><span data-stu-id="1d612-103">View Process module results in Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="1d612-104">**準備**之後\>初始化**程序**，您可以檢視進度和結果。</span><span class="sxs-lookup"><span data-stu-id="1d612-104">After **Prepare** \> **Process** is initiated, you can view progress and results.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1d612-p101">進階的 eDiscovery 需要您組織與進階規範附加元件或 E5 訂閱 Office 365 E3。如果您不具有該對應並想要嘗試進階的 eDiscovery，您還可以[註冊 Office 365 企業版 E5 的試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="1d612-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="process-task-status"></a><span data-ttu-id="1d612-107">程序的工作狀態</span><span class="sxs-lookup"><span data-stu-id="1d612-107">Process task status</span></span>

<span data-ttu-id="1d612-108">在 [**準備** \> **程序** \> **結果**] 頁面隨即顯示 （如果目前執行程序） 的目前狀態或最後一個程序狀態工作狀態下面範例所示。</span><span class="sxs-lookup"><span data-stu-id="1d612-108">In **Prepare** \> **Process** \> **Results**, the page shows the current status (if Process is currently running) or the last Process status task status as shown in the following example.</span></span>
  
![處理序模組的工作狀態](media/9430f9e7-a4dd-47c7-ac2e-2c6a60fc948b.png)
  
<span data-ttu-id="1d612-110">顯示的工作會根據選取的程序選項而異。</span><span class="sxs-lookup"><span data-stu-id="1d612-110">The displayed tasks may vary depending on the Process options selected.</span></span> 
  
- <span data-ttu-id="1d612-111">**庫存**： 進階的 eDiscovery 逐一查看所有程序所選取的檔案並執行基本的資料收集。</span><span class="sxs-lookup"><span data-stu-id="1d612-111">**Inventory**: Advanced eDiscovery iterates through all files selected for Process and performs basic data collection.</span></span>
    
- <span data-ttu-id="1d612-112">**計算簽章**： 計算 MD5 數位簽章。</span><span class="sxs-lookup"><span data-stu-id="1d612-112">**Calculate signatures**: Calculates the MD5 digital signatures.</span></span>
    
- <span data-ttu-id="1d612-p102">**組合擷取**： 擷取內部或內含複合檔案 (例如 PST、 ZIP、 MSG) 從檔案遞迴方式。解壓縮的檔案儲存在區分大小寫的資料夾。</span><span class="sxs-lookup"><span data-stu-id="1d612-p102">**Compounds extraction**: Extracts inner or contained files recursively from compound files (for example, PST, ZIP, MSG). Extracted files are stored in the case folder of the case.</span></span>
    
- <span data-ttu-id="1d612-115">**同步處理資料庫**： Internal database 程序。</span><span class="sxs-lookup"><span data-stu-id="1d612-115">**Synchronizing database**: Internal database process.</span></span>
    
- <span data-ttu-id="1d612-p103">**檔案複製**： 副本程序的檔案。永遠顯示這項工作，即使已選取 [進階的複製檔案] 選項。</span><span class="sxs-lookup"><span data-stu-id="1d612-p103">**File copy**: Copies Process files. This task is always displayed, even when the advanced Copy files option is selected.</span></span>
    
- <span data-ttu-id="1d612-p104">**文字擷取**： 進階的 eDiscovery 原生檔案時，會使用 DTSearch 這些檔案從擷取的文字。這些檔案解壓縮的文字會儲存為 [案件] 資料夾中的文字檔案。</span><span class="sxs-lookup"><span data-stu-id="1d612-p104">**Text extraction**: When there are native files, Advanced eDiscovery extracts text from these files using DTSearch. The extracted text of these files is stored as text files in the case folder.</span></span>
    
- <span data-ttu-id="1d612-120">**更新的中繼資料**： 處理載入的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="1d612-120">**Updating metadata**: Processes the loaded metadata.</span></span> 
    
- <span data-ttu-id="1d612-121">**Finalizing**： 完成之資料的內部處理載入案例檔案 （例如識別錯誤及成功檔案）。</span><span class="sxs-lookup"><span data-stu-id="1d612-121">**Finalizing**: Internal processing that finalizes data of loaded case files (for example, identify error and success files).</span></span> 
    
<span data-ttu-id="1d612-p105">任務狀態： 工作完成後顯示。執行工作時，會顯示執行持續時間。</span><span class="sxs-lookup"><span data-stu-id="1d612-p105">Task status: Displayed after task completion. While tasks are running, run duration is displayed.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1d612-124">已完成的工作可能也會包含總計完成處理的檔案或含有錯誤的檔案。</span><span class="sxs-lookup"><span data-stu-id="1d612-124">Completed tasks may also include totals for files that completed processing or files with errors.</span></span> 
  
> [!TIP]
> <span data-ttu-id="1d612-p106">"取消"提供可用來停止處理程序執行並再回復到先前的資料填入的復原選項或儲存處理的資料。回復會清除所有處理的資料。如果您不想將已處理的資料遺失 （例如，您計劃重新載入這些檔案），選取 ["取消"選項此視窗中的選擇不要回復。</span><span class="sxs-lookup"><span data-stu-id="1d612-p106">"Cancel" provides a rollback option to stop Process execution and then roll back to the previous data population or saved processed data. Rollback clears all processed data. If you do not want the processed data to be lost (for example, you plan to reload these files), select the "Cancel" option in this window to choose not to roll back.</span></span> 
  
## <a name="process-summary"></a><span data-ttu-id="1d612-128">程序摘要</span><span class="sxs-lookup"><span data-stu-id="1d612-128">Process summary</span></span>

<span data-ttu-id="1d612-129">在 [準備\>程序\>結果\>程序摘要、 分解載入的檔案結果的顯示根據成功檔案處理和錯誤的結果。</span><span class="sxs-lookup"><span data-stu-id="1d612-129">In Prepare \> Process \> Results \> Process summary, a breakdown of loaded file results is displayed according to successful file processing and error results.</span></span>
  
<span data-ttu-id="1d612-130">Panes 呈現匯入的檔案統計資料的圖形展示，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1d612-130">The panes present a graphical display of imported file statistics, as follows:</span></span>
  
- <span data-ttu-id="1d612-131">**程序摘要累計**d： 所有檔案的大小寫。</span><span class="sxs-lookup"><span data-stu-id="1d612-131">**Process summary accumulate**d: All files in the case.</span></span>
    
- <span data-ttu-id="1d612-132">**上次處理摘要**： 從最後一個工作階段或巨集指令載入的檔案。</span><span class="sxs-lookup"><span data-stu-id="1d612-132">**Process summary last**: Files loaded from the last session or action.</span></span> 
    
- <span data-ttu-id="1d612-133">**最後的系列**： 系列產品資訊 （如果有的話） 的大小寫。</span><span class="sxs-lookup"><span data-stu-id="1d612-133">**Families last**: Family information in the case (if any).</span></span>
    
- <span data-ttu-id="1d612-134">如果**植入**檔案新增、 植入的檔案數目會列於每個已定義的檔案的問題。</span><span class="sxs-lookup"><span data-stu-id="1d612-134">If **Seed** files were added, the number of seed files is listed per issue that was defined for the files.</span></span> 
    
    <span data-ttu-id="1d612-135">如果**植入**檔案的標示失敗，也記下。</span><span class="sxs-lookup"><span data-stu-id="1d612-135">If the marking of **Seed** files failed, that is also noted.</span></span> 
    
- <span data-ttu-id="1d612-136">如果**前標記**檔案新增、 前已標記的檔案數目會列於每個已定義的檔案的問題。</span><span class="sxs-lookup"><span data-stu-id="1d612-136">If **Pre-tagged** files were added, the number of pre-tagged files is listed per issue that was defined for the files.</span></span> 
    
    <span data-ttu-id="1d612-137">如果**前標記**檔案的標示失敗，也記下。</span><span class="sxs-lookup"><span data-stu-id="1d612-137">If the marking of **Pre-tagged** files failed, that is also noted.</span></span> 
    
![處理序模組摘要](media/2086a691-9e3d-4117-beb2-a5c3a9a4cc94.png)
  
## <a name="process-summary-accumulated-and-last-charts"></a><span data-ttu-id="1d612-139">程序摘要累積版本和上一個圖表</span><span class="sxs-lookup"><span data-stu-id="1d612-139">Process summary accumulated and last charts</span></span>

<span data-ttu-id="1d612-140">左的列包含來源 + 解壓縮的檔案： 這是所有檔案找到。</span><span class="sxs-lookup"><span data-stu-id="1d612-140">The left bar includes Source + extracted files: which is all files found.</span></span> 
  
<span data-ttu-id="1d612-141">右橫條圖、 處理，包括：</span><span class="sxs-lookup"><span data-stu-id="1d612-141">The right bar, Processed, includes:</span></span>
  
- <span data-ttu-id="1d612-142">檔案載入錯誤</span><span class="sxs-lookup"><span data-stu-id="1d612-142">Files with load errors</span></span>
    
- <span data-ttu-id="1d612-143">成功載入的檔案，其中可能包含：</span><span class="sxs-lookup"><span data-stu-id="1d612-143">Successfully loaded files, which may include:</span></span> 
    
  - <span data-ttu-id="1d612-144">**現有**： 現在載入再次 （包括重複項目） 及之前已載入的檔案。</span><span class="sxs-lookup"><span data-stu-id="1d612-144">**Existing**: Files that were loaded before and are now loaded again (including duplicates).</span></span>
    
  - <span data-ttu-id="1d612-145">**文字**： 具有文字的唯一檔案。</span><span class="sxs-lookup"><span data-stu-id="1d612-145">**Text**: Unique files with text.</span></span>
    
  - <span data-ttu-id="1d612-146">**非文字**： 清空文字檔、 空白的原生文字檔案、 原生非文字檔案。</span><span class="sxs-lookup"><span data-stu-id="1d612-146">**Non-text**: Empty text files, empty native text files, native non-text files.</span></span> 
    
  - <span data-ttu-id="1d612-147">**重複的**s 重複檔案的文字。</span><span class="sxs-lookup"><span data-stu-id="1d612-147">**Duplicate**s: Duplicate files with text.</span></span>
    
## <a name="last-process-errors"></a><span data-ttu-id="1d612-148">最後一個程序錯誤</span><span class="sxs-lookup"><span data-stu-id="1d612-148">Last process errors</span></span>

<span data-ttu-id="1d612-149">在 [準備\>程序\>結果\>會顯示最後一個程序錯誤，最後一個工作階段或執行的動作中發生之錯誤的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="1d612-149">In Prepare \> Process \> Results \> Last process errors, details of the errors in the last session or action performed are displayed.</span></span>
  
![處理序模組錯誤](media/4771d0f4-4217-445a-9ba4-8b6541c5ad09.png)
  
## <a name="see-also"></a><span data-ttu-id="1d612-151">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1d612-151">See also</span></span>

[<span data-ttu-id="1d612-152">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="1d612-152">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="1d612-153">執行的程序模組，並將資料載入</span><span class="sxs-lookup"><span data-stu-id="1d612-153">Running the Process module and loading data</span></span>](run-the-process-module-and-load-data-in-advanced-ediscovery.md)

