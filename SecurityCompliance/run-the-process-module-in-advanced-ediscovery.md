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
# <a name="run-the-process-module-in-office-365-advanced-ediscovery"></a>在 Office 365 進階電子文件探索中執行處理程序模組

Case 檔案載入至進階 eDiscovery**準備**期間\>**程序**。 
  
> [!NOTE]
> 進階的 eDiscovery 需要您組織與進階規範附加元件或 E5 訂閱 Office 365 E3。如果您不具有該對應並想要嘗試進階的 eDiscovery，您還可以[註冊 Office 365 企業版 E5 的試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
## <a name="guidelines-preparing-data-for-advanced-ediscovery"></a>指導方針： 準備資料進階 ediscovery （英文）

- **品質**： 清楚識別區分檔案母體大小寫改變功能。
    
- **載入**： 檔案載入進階 ediscovery 可存取的位置。
    
- **檔案識別碼**： 進階 ediscovery 的唯一檔案識別碼。如果沒有檔案識別碼匯入、 進階的 eDiscovery 會自動產生的識別碼。如果您對應的識別碼在後續的程序負載，並將其他路徑對應比在初始的程序負載、 進階的 eDiscovery 會取代路徑 （而不是新增新的檔案項目）。識別碼可以做匯出程序中的參照。識別碼值不應該是"-1"。
    
- **MD5**： 此簽章用來區分 （這兩個檔案不被視為完全重複除非有相同的 MD5） 的檔案。根據預設，進階的 eDiscovery 來計算 MD5 的檔案。文字檔案載入的檔案時，建議您載入及對應，而不是計算進階 ediscovery 的原始 MD5 值。
    
- **檔案類型和名稱**：
    
  - 進階的 eDiscovery 可處理的各種格式的檔案並將載入的原生檔案擷取成標準格式，例如\*。TXT、 HTML、 或。文字檔案的 XML。 處理會比原生檔案快一點。解壓縮的文字檔案儲存在 case 資料夾。
    
  - 不載入無法擷取，如系統檔案或圖形的圖像的檔案。這些檔案可能會延遲處理。
    
  - 確認大幅名為檔案名稱及路徑正確無誤。
    
- **檔案路徑**： 進階的 eDiscovery 可載入檔案路徑長度最多 400 個字元。
    
- **文字擷取**： 擷取原生檔案，以及一般文字的文字時也解壓縮下列： 隱藏的文字 （Excel 和.doc） 隱藏資料行 (Excel) 追蹤的變更 (.doc) 演講者備忘稿 (.ppt) 內嵌物件 （例如，Excel 中的物件.ppt）。這些可檢視中的文字編輯器。
    
- **搜尋時忽略的文字**： 定義此選用功能時執行程序之後，而之前分析。搜尋時忽略文字應該使用小心，因為它使用可能會降低檔案分析的效能。
    
- **多國語系文字**： 進階的 eDiscovery 目前未處理的標記、 okay，以及問題的多語系名稱。
    
- **中繼資料**： 決定是否要以供未來參照，例如日期範圍、 檔案大小、 檔案類型區分資料庫中儲存 okay、 和主旨的中繼資料。檔案已載入而不重新執行庫存或新增重新處理負荷之後可以載入中繼資料。 
    
  - 如果檔案原本已載入的路徑，當稍後匯入中繼資料對應 [路徑] 欄。有可能依識別碼檔案參照和對應的不同的路徑。這是有用的案例的檔案路徑變更時。
    
  - 如果檔案原本已載入的檔案識別碼，對應識別碼] 欄中載入的中繼資料時。路徑 （而非識別碼） 所參照的檔案會導致檔案要重新載入具有不同的識別碼。進階的 eDiscovery 建立檔案的複本而是該載入的中繼資料的現有的檔案。
    
- **系列**： 即無法再將載入系列沒有與其父系 （標題的系列）。 
    
- **檔案大小**： 沒有大小沒有限制的進階 ediscovery 載入的檔案。進行分析 （分析、 相關性等），限制為 5,242,880 擷取文字字元。會略過較大的檔案 （例如相關性，在檔案不會參與相關性訓練程序及批次計算後未收到相關性分數）。
    
- **檔案數量**： 沒有可處理單一案例中的檔案數目沒有建議的限制。效能取決於您的系統的資源。 
    
## <a name="filtering-files"></a>篩選檔案

使用者定義的標籤可以與一組檔案來排除程序或其他工作相關聯。每個程序工作階段相關聯批次的識別碼。雖然批次識別碼看不到相關性專家、 可達成此目的使用搜尋公用程式來新增目前的批次的篩選及標記的使用者定義的標籤與所有適當的檔案。 
  
## <a name="see-also"></a>另請參閱

[Office 365 進階電子文件探索](office-365-advanced-ediscovery.md)
  
[執行的程序模組，並將資料載入](run-the-process-module-and-load-data-in-advanced-ediscovery.md)
  
[檢視程序模組結果](view-process-module-results-in-advanced-ediscovery.md)

