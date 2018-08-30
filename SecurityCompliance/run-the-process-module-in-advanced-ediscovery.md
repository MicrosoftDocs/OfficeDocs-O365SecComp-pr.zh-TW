---
title: 在 Office 365 進階電子文件探索中執行處理程序模組
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
ms.assetid: dbc1e251-0596-443b-ac9b-f398ba955b73
description: '了解做準備 case 檔案的 Office 365 資料分析與 Office 365 進階 eDiscovery 的準則。  '
ms.openlocfilehash: 52b1dce9fb778c6628d90c39135f0c93f08134d7
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22527304"
---
# <a name="run-the-process-module-in-office-365-advanced-ediscovery"></a><span data-ttu-id="7b0c1-103">在 Office 365 進階電子文件探索中執行處理程序模組</span><span class="sxs-lookup"><span data-stu-id="7b0c1-103">Run the Process module in Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="7b0c1-104">Case 檔案載入至進階 eDiscovery**準備**期間\>**程序**。</span><span class="sxs-lookup"><span data-stu-id="7b0c1-104">Case files are loaded into the Advanced eDiscovery during **Prepare** \> **Process**.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7b0c1-p101">進階的 eDiscovery 需要您組織與進階規範附加元件或 E5 訂閱 Office 365 E3。如果您不具有該對應並想要嘗試進階的 eDiscovery，您還可以[註冊 Office 365 企業版 E5 的試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="7b0c1-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="guidelines-preparing-data-for-advanced-ediscovery"></a><span data-ttu-id="7b0c1-107">指導方針： 準備資料進階 ediscovery （英文）</span><span class="sxs-lookup"><span data-stu-id="7b0c1-107">Guidelines: Preparing data for Advanced eDiscovery</span></span>

- <span data-ttu-id="7b0c1-108">**品質**： 清楚識別區分檔案母體大小寫改變功能。</span><span class="sxs-lookup"><span data-stu-id="7b0c1-108">**Quality**: Clearly identify the case file population pertinent to the case.</span></span>
    
- <span data-ttu-id="7b0c1-109">**載入**： 檔案載入進階 ediscovery 可存取的位置。</span><span class="sxs-lookup"><span data-stu-id="7b0c1-109">**Loads**: Load the files into a location that is accessible to Advanced eDiscovery.</span></span>
    
- <span data-ttu-id="7b0c1-p102">**檔案識別碼**： 進階 ediscovery 的唯一檔案識別碼。如果沒有檔案識別碼匯入、 進階的 eDiscovery 會自動產生的識別碼。如果您對應的識別碼在後續的程序負載，並將其他路徑對應比在初始的程序負載、 進階的 eDiscovery 會取代路徑 （而不是新增新的檔案項目）。識別碼可以做匯出程序中的參照。識別碼值不應該是"-1"。</span><span class="sxs-lookup"><span data-stu-id="7b0c1-p102">**File ID**: A unique file identifier in Advanced eDiscovery. If no file identifier is imported, Advanced eDiscovery automatically generates the ID. If you map the ID in a subsequent Process load, and map a different path than in the initial Process load, Advanced eDiscovery will replace the path (rather than add a new file entry). The ID can be used as a reference in the Export process. The ID value should not be "-1".</span></span>
    
- <span data-ttu-id="7b0c1-p103">**MD5**： 此簽章用來區分 （這兩個檔案不被視為完全重複除非有相同的 MD5） 的檔案。根據預設，進階的 eDiscovery 來計算 MD5 的檔案。文字檔案載入的檔案時，建議您載入及對應，而不是計算進階 ediscovery 的原始 MD5 值。</span><span class="sxs-lookup"><span data-stu-id="7b0c1-p103">**MD5**: This signature is used to differentiate between files (two files are not considered exact duplicates unless they have the same MD5). By default, Advanced eDiscovery calculates the MD5 of files. When the loaded files are text files, it is recommended to load and map the original MD5 value instead of calculating it in Advanced eDiscovery.</span></span>
    
- <span data-ttu-id="7b0c1-118">**檔案類型和名稱**：</span><span class="sxs-lookup"><span data-stu-id="7b0c1-118">**File type and name**:</span></span>
    
  - <span data-ttu-id="7b0c1-p104">進階的 eDiscovery 可處理的各種格式的檔案並將載入的原生檔案擷取成標準格式，例如\*。TXT、 HTML、 或。文字檔案的 XML。 處理會比原生檔案快一點。解壓縮的文字檔案儲存在 case 資料夾。</span><span class="sxs-lookup"><span data-stu-id="7b0c1-p104">Advanced eDiscovery can process files of various formats and extract loaded native files into a standard format, such as \*.TXT, HTML, or .XML. Processing of text files is faster than native files. Extracted text files are stored in the case folder.</span></span>
    
  - <span data-ttu-id="7b0c1-p105">不載入無法擷取，如系統檔案或圖形的圖像的檔案。這些檔案可能會延遲處理。</span><span class="sxs-lookup"><span data-stu-id="7b0c1-p105">Do not load files that cannot be extracted, such as system files or graphic images. These files may delay processing.</span></span>
    
  - <span data-ttu-id="7b0c1-124">確認大幅名為檔案名稱及路徑正確無誤。</span><span class="sxs-lookup"><span data-stu-id="7b0c1-124">Verify that file names are significantly named and paths are correct.</span></span>
    
- <span data-ttu-id="7b0c1-125">**檔案路徑**： 進階的 eDiscovery 可載入檔案路徑長度最多 400 個字元。</span><span class="sxs-lookup"><span data-stu-id="7b0c1-125">**File path**: Advanced eDiscovery can load files with path lengths up to 400 characters.</span></span>
    
- <span data-ttu-id="7b0c1-p106">**文字擷取**： 擷取原生檔案，以及一般文字的文字時也解壓縮下列： 隱藏的文字 （Excel 和.doc） 隱藏資料行 (Excel) 追蹤的變更 (.doc) 演講者備忘稿 (.ppt) 內嵌物件 （例如，Excel 中的物件.ppt）。這些可檢視中的文字編輯器。</span><span class="sxs-lookup"><span data-stu-id="7b0c1-p106">**Text extraction**: When extracting text from native files, in addition to normal text, the following are also extracted: hidden text (Excel and .doc), hidden columns (Excel), track changes (.doc), speaker notes (.ppt), embedded objects (for example, Excel objects in a .ppt). These can be viewed in the Text editor.</span></span>
    
- <span data-ttu-id="7b0c1-p107">**搜尋時忽略的文字**： 定義此選用功能時執行程序之後，而之前分析。搜尋時忽略文字應該使用小心，因為它使用可能會降低檔案分析的效能。</span><span class="sxs-lookup"><span data-stu-id="7b0c1-p107">**Ignore Text**: This optional feature is defined after Process is run and before Analyze. Ignore text should be used with caution because its use may reduce the performance of file analysis.</span></span>
    
- <span data-ttu-id="7b0c1-130">**多國語系文字**： 進階的 eDiscovery 目前未處理的標記、 okay，以及問題的多語系名稱。</span><span class="sxs-lookup"><span data-stu-id="7b0c1-130">**Multilingual text**: Advanced eDiscovery does not currently handle multilingual names for tags, custodian, and issues.</span></span>
    
- <span data-ttu-id="7b0c1-p108">**中繼資料**： 決定是否要以供未來參照，例如日期範圍、 檔案大小、 檔案類型區分資料庫中儲存 okay、 和主旨的中繼資料。檔案已載入而不重新執行庫存或新增重新處理負荷之後可以載入中繼資料。</span><span class="sxs-lookup"><span data-stu-id="7b0c1-p108">**Metadata**: Determine if there is metadata that you want to save in the case database for future reference, such as date range, file size, file type, custodian, and subject. Metadata can be loaded after files were already loaded without rerunning the inventory or adding reprocessing overhead.</span></span> 
    
  - <span data-ttu-id="7b0c1-p109">如果檔案原本已載入的路徑，當稍後匯入中繼資料對應 [路徑] 欄。有可能依識別碼檔案參照和對應的不同的路徑。這是有用的案例的檔案路徑變更時。</span><span class="sxs-lookup"><span data-stu-id="7b0c1-p109">If the files were originally loaded by path, map the path column when later importing metadata. It is possible to refer to the file by ID and to map a different path. This is a useful scenario when the file paths change.</span></span>
    
  - <span data-ttu-id="7b0c1-p110">如果檔案原本已載入的檔案識別碼，對應識別碼] 欄中載入的中繼資料時。路徑 （而非識別碼） 所參照的檔案會導致檔案要重新載入具有不同的識別碼。進階的 eDiscovery 建立檔案的複本而是該載入的中繼資料的現有的檔案。</span><span class="sxs-lookup"><span data-stu-id="7b0c1-p110">If the files were originally loaded by File ID, map the ID column when loading metadata. Referring to the file by path (instead of ID) will cause files to be re-loaded with a different ID. Advanced eDiscovery creates copies of the files rather that loading metadata of the existing files.</span></span>
    
- <span data-ttu-id="7b0c1-139">**系列**： 即無法再將載入系列沒有與其父系 （標題的系列）。</span><span class="sxs-lookup"><span data-stu-id="7b0c1-139">**Families**: It is not possible to load a family without its parent (head of family).</span></span> 
    
- <span data-ttu-id="7b0c1-p111">**檔案大小**： 沒有大小沒有限制的進階 ediscovery 載入的檔案。進行分析 （分析、 相關性等），限制為 5,242,880 擷取文字字元。會略過較大的檔案 （例如相關性，在檔案不會參與相關性訓練程序及批次計算後未收到相關性分數）。</span><span class="sxs-lookup"><span data-stu-id="7b0c1-p111">**File size**: There is no limitation on the size of files loaded to Advanced eDiscovery. For analysis (Analyze, Relevance, etc.), the limit is 5,242,880 characters of extracted text. Larger files are ignored (for example, in Relevance, files do not participate in the Relevance training process and do not receive a Relevance score after batch calculation).</span></span>
    
- <span data-ttu-id="7b0c1-p112">**檔案數量**： 沒有可處理單一案例中的檔案數目沒有建議的限制。效能取決於您的系統的資源。</span><span class="sxs-lookup"><span data-stu-id="7b0c1-p112">**File quantity**: There is no recommended limit on the number of files that can be handled in a single case. Performance depends on the resources of your system.</span></span> 
    
## <a name="filtering-files"></a><span data-ttu-id="7b0c1-145">篩選檔案</span><span class="sxs-lookup"><span data-stu-id="7b0c1-145">Filtering files</span></span>

<span data-ttu-id="7b0c1-p113">使用者定義的標籤可以與一組檔案來排除程序或其他工作相關聯。每個程序工作階段相關聯批次的識別碼。雖然批次識別碼看不到相關性專家、 可達成此目的使用搜尋公用程式來新增目前的批次的篩選及標記的使用者定義的標籤與所有適當的檔案。</span><span class="sxs-lookup"><span data-stu-id="7b0c1-p113">A user-defined label can be associated with a set of files to exclude them from Process or other tasks. Each Process session is associated with a batch ID. Although the batch ID is not visible to the expert in Relevance, this can be done using a search utility, by adding a filter for the current batch and tagging all appropriate files with a user-defined label.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="7b0c1-149">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7b0c1-149">See also</span></span>

[<span data-ttu-id="7b0c1-150">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="7b0c1-150">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="7b0c1-151">執行的程序模組，並將資料載入</span><span class="sxs-lookup"><span data-stu-id="7b0c1-151">Running the Process module and loading data</span></span>](run-the-process-module-and-load-data-in-advanced-ediscovery.md)
  
[<span data-ttu-id="7b0c1-152">檢視程序模組結果</span><span class="sxs-lookup"><span data-stu-id="7b0c1-152">Viewing Process module results</span></span>](view-process-module-results-in-advanced-ediscovery.md)

