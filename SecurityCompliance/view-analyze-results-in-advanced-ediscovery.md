---
title: 在 Office 365 進階電子文件探索中檢視分析結果
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
ms.assetid: 5974f3c2-89fe-4c5f-ac7b-57f214437f7e
description: '了解 Office 365 進階 eDiscovery，包括定義顯示的任務的選項以檢視分析程序的結果的位置。  '
ms.openlocfilehash: 990bcbb3c6626521d40f7ce057c764200d5047b5
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218823"
---
# <a name="view-analyze-results-in-office-365-advanced-ediscovery"></a>在 Office 365 進階電子文件探索中檢視分析結果

> [!NOTE]
> 進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
進階 eDiscovery 中進行中及結果分析程序可檢視中顯示各種如下所示。
  
## <a name="view-analyze-task-status"></a>檢視分析任務狀態

在**準備\>分析\>結果\>任務狀態**、 期間和之後分析程序執行顯示狀態。 
  
![分析工作狀態](media/d0372978-ce08-4f4e-a1fc-aa918ae44364.png)
  
顯示的工作會根據選取的選項而異。 
  
- **ND/ET： 安裝程式**： 例如準備執行、 設定執行與案例的參數。
    
- **ND/ET: ND 計算**： 檔案的程序接近重複分析。
    
- **ND/ET: ET 計算**： 執行電子郵件執行緒分析在整個電子郵件設定。
    
- **ND/ET： 樞紐分析表和相似之處**： 執行 [樞紐分析表和檔案相似性處理。
    
- **ND/ET： 中繼資料更新**： 完成新資料庫中的檔案上收集的資料。
    
- **佈景主題： 佈景主題計算**： 執行佈景主題分析。（顯示唯有在選取了）。
    
- **工作狀態**： 這一行會顯示在工作完成之後。執行工作時，會顯示執行持續時間。
    
> [!NOTE]
> 分析的結果接近重複項目和電子郵件執行緒 （ND 和 ED） 適用於處理的文件數。它不包括完全重複的檔案。 
  
## <a name="view-near-duplicates-and-email-threads-status"></a>檢視接近重複項目和電子郵件執行緒狀態

**目標**母體結果在目標母體中顯示文件、 電子郵件、 附件及錯誤的數目。 
  
**文件**結果顯示樞紐分析表、 唯一附近-重複項目及完全重複的檔案的數目。 
  
**電子郵件**結果會顯示 （含）、 減去唯一 （含） 的副本 （含） 的數目與其餘的電子郵件訊息。不同類型的電子郵件結果是： 
  
- **Inclusive**: （含） 的電子郵件是在電子郵件執行緒 [終止] 節點並包含該執行緒的所有先前的歷程記錄。因此，檢閱者可以安全地聚焦 （含） 的電子郵件，而不需要讀取執行緒中先前的訊息。 
    
- **減去 Inclusive**： 如果沒有聯 （含） 郵件的父系的一或多個不同的附件 （含） 的電子郵件指定為 （含） 減號。在這個 context、 向上位於電子郵件執行緒或交談的郵件都使用父項的字詞包含在該特定 （含） 的電子郵件。檢閱者可以使用減去指示做訊號但它不需要檢閱的 （含） 的電子郵件父系的內容，它可能會很有用檢閱 （含） 的路徑父系相關聯的附件 （含）。 
    
- **（含） 的複本**： （含） 的電子郵件指定為 （含） 的複本時之複本的另一則訊息標示為 （含） 或減去 （含）。換句話說，此訊息有相同的主旨和當成另一個 （含） 的訊息本文並因此、 共同位於相同的節點。因為 （含） 複製郵件包含相同的內容，他們可以通常略過檢閱程序。 
    
- **其他**： 這表示不包含任何唯一的內容與因此不屬於任何舊的三種類別的電子郵件。不需要檢閱這些電子郵件訊息。如果郵件含有不在稍後 （含） 電子郵件的附件，附件可能需要檢閱。這會指定存在減去執行緒內的電子郵件 （含）。
    
**附件**結果顯示附件，根據這類為唯一的類型和重複項目的數目。 
  
![近似重複項目和電子郵件執行緒](media/54491303-0ee3-4739-b42e-d1ee486842fd.png)
  
## <a name="see-also"></a>另請參閱

[Office 365 進階電子文件探索](office-365-advanced-ediscovery.md)
  
[了解文件相似性](understand-document-similarity-in-advanced-ediscovery.md)
  
[設定分析選項](set-analyze-options-in-advanced-ediscovery.md)
  
[設定搜尋時忽略的文字](set-ignore-text-in-advanced-ediscovery.md)
  
[設定分析進階設定](view-analyze-results-in-advanced-ediscovery.md)

