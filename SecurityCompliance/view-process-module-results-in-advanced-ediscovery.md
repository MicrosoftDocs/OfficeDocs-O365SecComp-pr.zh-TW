---
title: 在 Office 365 進階電子文件探索中檢視處理程序模組結果
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c6f016cb-409f-4ae9-911c-1395cf0c86ea
description: '了解如何尋找 Office 365 進階 eDiscovery，包括任務狀態及摘要的程序中執行的程序模組的結果。  '
ms.openlocfilehash: 0393cde78e559036d92b9ac48245afafc974a8b2
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218053"
---
# <a name="view-process-module-results-in-office-365-advanced-ediscovery"></a>在 Office 365 進階電子文件探索中檢視處理程序模組結果

**準備**之後\>初始化**程序**，您可以檢視進度和結果。 
  
> [!NOTE]
> 進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
## <a name="process-task-status"></a>程序的工作狀態

在 [**準備** \> **程序** \> **結果**] 頁面隨即顯示 （如果目前執行程序） 的目前狀態或最後一個程序狀態工作狀態下面範例所示。
  
![處理序模組的工作狀態](media/9430f9e7-a4dd-47c7-ac2e-2c6a60fc948b.png)
  
顯示的工作會根據選取的程序選項而異。 
  
- **庫存**： 進階的 eDiscovery 逐一查看所有程序所選取的檔案並執行基本的資料收集。
    
- **計算簽章**： 計算 MD5 數位簽章。
    
- **組合擷取**： 擷取內部或內含複合檔案 (例如 PST、 ZIP、 MSG) 從檔案遞迴方式。解壓縮的檔案儲存在區分大小寫的資料夾。
    
- **同步處理資料庫**： Internal database 程序。
    
- **檔案複製**： 副本程序的檔案。永遠顯示這項工作，即使已選取 [進階的複製檔案] 選項。
    
- **文字擷取**： 進階的 eDiscovery 原生檔案時，會使用 DTSearch 這些檔案從擷取的文字。這些檔案解壓縮的文字會儲存為 [案件] 資料夾中的文字檔案。
    
- **更新的中繼資料**： 處理載入的中繼資料。 
    
- **Finalizing**： 完成之資料的內部處理載入案例檔案 （例如識別錯誤及成功檔案）。 
    
任務狀態： 工作完成後顯示。執行工作時，會顯示執行持續時間。
  
> [!NOTE]
> 已完成的工作可能也會包含總計完成處理的檔案或含有錯誤的檔案。 
  
> [!TIP]
> "取消"提供可用來停止處理程序執行並再回復到先前的資料填入的復原選項或儲存處理的資料。回復會清除所有處理的資料。如果您不想將已處理的資料遺失 （例如，您計劃重新載入這些檔案），選取 ["取消"選項此視窗中的選擇不要回復。 
  
## <a name="process-summary"></a>程序摘要

在 [準備\>程序\>結果\>程序摘要、 分解載入的檔案結果的顯示根據成功檔案處理和錯誤的結果。
  
Panes 呈現匯入的檔案統計資料的圖形展示，如下所示：
  
- **程序摘要累計**d： 所有檔案的大小寫。
    
- **上次處理摘要**： 從最後一個工作階段或巨集指令載入的檔案。 
    
- **最後的系列**： 系列產品資訊 （如果有的話） 的大小寫。
    
- 如果**植入**檔案新增、 植入的檔案數目會列於每個已定義的檔案的問題。 
    
    如果**植入**檔案的標示失敗，也記下。 
    
- 如果**前標記**檔案新增、 前已標記的檔案數目會列於每個已定義的檔案的問題。 
    
    如果**前標記**檔案的標示失敗，也記下。 
    
![處理序模組摘要](media/2086a691-9e3d-4117-beb2-a5c3a9a4cc94.png)
  
## <a name="process-summary-accumulated-and-last-charts"></a>程序摘要累積版本和上一個圖表

左的列包含來源 + 解壓縮的檔案： 這是所有檔案找到。 
  
右橫條圖、 處理，包括：
  
- 檔案載入錯誤
    
- 成功載入的檔案，其中可能包含： 
    
  - **現有**： 現在載入再次 （包括重複項目） 及之前已載入的檔案。
    
  - **文字**： 具有文字的唯一檔案。
    
  - **非文字**： 清空文字檔、 空白的原生文字檔案、 原生非文字檔案。 
    
  - **重複的**s 重複檔案的文字。
    
## <a name="last-process-errors"></a>最後一個程序錯誤

在 [準備\>程序\>結果\>會顯示最後一個程序錯誤，最後一個工作階段或執行的動作中發生之錯誤的詳細資訊。
  
![處理序模組錯誤](media/4771d0f4-4217-445a-9ba4-8b6541c5ad09.png)
  
## <a name="see-also"></a>另請參閱

[Office 365 進階電子文件探索](office-365-advanced-ediscovery.md)
  
[執行的程序模組，並將資料載入](run-the-process-module-and-load-data-in-advanced-ediscovery.md)

