---
title: 調查 Office 365 電子文件探索中已局部編製索引的項目
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/26/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid: MOE150
ms.assetid: 4e8ff113-6361-41e2-915a-6338a7e2a1ed
description: 部分編製索引的項目 （也是呼叫未建立索引項目） 的 Exchange 信箱項目和 SharePoint 的文件和 OneDrive 網站的因任何原因未完全編製索引內容的搜尋。針對本文中了解為何無法編製索引的搜尋項目，以及部分已編製索引的項目所傳回、 識別搜尋錯誤的部分已編製索引的項目，並使用 PowerShell 指令碼來判斷您的組織衝擊部分已編製索引的電子郵件項目。
ms.openlocfilehash: d8fec240964ad84b811221754060af3e342af01f
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295626"
---
# <a name="investigating-partially-indexed-items-in-office-365-ediscovery"></a>調查 Office 365 電子文件探索中已局部編製索引的項目

您執行從 Office 365 安全性內容搜尋&amp;規範中心自動包含部分已編製索引的項目中預估的搜尋結果時執行搜尋。部分已編製索引的項目是 Exchange 信箱項目及 SharePoint 和 OneDrive 上的商務網站因任何原因未完全編入搜尋索引的文件。大部分的電子郵件與網站的文件已成功編製索引因為其落在[編製索引的電子郵件的限制](limits-for-content-search.md#indexing-limits-for-email-messages)內。不過，某些項目超過這些索引的限制，並將部分編製索引。以下是其他項目為何無法編製索引的搜尋及部分已編製索引的項目執行內容的搜尋時所傳回的原因：
  
- 電子郵件已附加的檔案不能索引 ； 的檔案類型在大多數情況下，此檔案類型是[無法辨識或不支援為編製索引](partially-indexed-items-in-content-search.md#file-types-not-indexed-for-search)
    
- 電子郵件已如圖像檔 ； 有效的處理常式中，而附加的檔案這是部分已編製索引的電子郵件項目的最常見原因
    
- 太多檔案附加至電子郵件訊息
    
- 附加至電子郵件訊息的檔案會太大
    
- 支援的檔案類型編製索引，但在編製時發生錯誤的特定檔案
    
雖然它而異，大部分的 Office 365 組織客戶的內容低於 1%大量，擁有的內容低於 12%以部分編製索引的大小。大小與大量之間的差異的原因是較大的檔案具有較高的機率的含有不能完全索引的內容。
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a>部分已編製索引的項目計數為何變更搜尋？

Office 365 安全性執行內容的搜尋之後&amp;規範中心、 總數及大小的部分已編製索引的項目所搜尋的位置中列出的詳細統計資料中顯示的搜尋結果統計資料搜尋]。請注意這些稱為*編製索引的項目*中的搜尋統計資料。以下是會影響搜尋結果中傳回的部分已編製索引項目數的一些事項： 
  
- 如果項目部分編製索引和搜尋查詢會比對，它會包含在計數 （和大小） 的搜尋結果項目和部分已編製索引的項目。不過，該相同結果所匯出，項目是搜尋的只包含在搜尋結果; 集它具有不包含為部分已編製索引的項目。
    
- 如果您指定日期範圍的搜尋查詢 （包括其關鍵字查詢中） 或使用一項條件，不符合日期範圍內的任何部分已編製索引項目不包含在部分已編製索引項目的計數。只有部分已編製索引項目屬於日期範圍內已包含在部分已編製索引的項目計數。
    
 **附註：** 部分已編製索引的項目位於 SharePoint 與 OneDrive 網站*不*包含在搜尋的詳細統計資料中所顯示的部分已編製索引的項目評估。不過，當您將匯出的內容的搜尋結果可以匯出部分已編製索引的項目。例如，如果您只搜尋網站內容的搜尋評估的數字中部分已編製索引的項目會為零。 
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a>計算的部分已編製索引的項目在組織中的比率

若要了解您的組織衝擊至部分已編製索引的項目，您可以執行的所有信箱搜尋的所有內容 （使用空白的關鍵字查詢）。在下面的下列範例中，有 56,208 (4,830 MB) 完全編製索引項目和 470 (316 MB) 部分編製索引的項目。
  
![搜尋統計資料顯示的範例部分編製索引的項目](media/0f6a5cf7-4c98-44a0-a0dd-5aed67124641.png)
  
您可以使用下列計算判斷部分已編製索引的項目百分比。
  
 **若要計算的比例的組織中的部分已編製索引項目：**

`(Total number of partially indexed items/Total number of items) x 100`


`(470/56,208) x 100 = 0.84%`
 
使用上述範例中，從搜尋結果。 84%的所有信箱項目部分編製索引。
  
 **若要計算您組織中的部分已編製索引項目的大小的百分比：**

`(Size of all partially indexed items/Size of all items) x 100`

`(316 MB/4830 MB) x 100 = 6.54%`

因此在上述範例中，6.54] %的信箱項目總大小是來自部分已編製索引的項目。如先前所述，大部分客戶的內容低於 1%磁碟區，擁有的內容低於 12%以部分編製索引的大小的 Office 365 組織。

## <a name="working-with-partially-indexed-items"></a>部分使用編製索引的項目

在的情況下您要檢查部分來驗證這些不包含下列相關資訊，您可以[將內容搜尋報表匯出](export-a-content-search-report.md)的項目包含部分已編製索引項目的相關資訊。當您將匯出的內容搜尋報告時，請務必選擇其中一個包含部分已編製索引的項目匯出選項。 
  
![選擇部分已編製索引的項目匯出的第二個或第三個選項](media/624a62b4-78f7-4329-ab5d-e62e3b369885.png)
  
當您匯出內容的搜尋結果或使用其中一個選項內容的搜尋報告時，匯出包含名為花很多 Items.csv 報表。這份報告包含大部分的資訊與 ResultsLog.csv 檔案 ； 相同但是花很多 Items.csv 檔案也包含兩個部分已編製索引項目的相關的欄位：**錯誤標記**和**錯誤屬性**。這些欄位包含每個部分已編製索引項目的索引錯誤的資訊。使用這兩個欄位中的資訊可協助您決定針對特定索引錯誤影響您調查。若是如此，您可以執行目標內容搜尋與匯出及擷取特定的電子郵件訊息與 SharePoint 或 OneDrive 文件，讓您可以檢查其決定是否它們與您正在調查相關。如需逐步說明，請參閱 ＜ [Prepare for Office 365 中的目標內容搜尋 CSV 檔案](csv-file-for-an-id-list-content-search.md)。
  
 **附註：** 編製索引的 Items.csv 檔案還包含名為**錯誤類型**和**錯誤訊息**的欄位。這些是舊版欄位包含**錯誤標記**和**錯誤屬性**欄位中，但具有較少的詳細資訊的資訊類似的資訊。您可以放心地忽略這些舊版的欄位。 
  
## <a name="errors-related-to-partially-indexed-items"></a>與部分已編製索引的項目相關的錯誤

錯誤標記所組成的資訊、 錯誤和檔案類型的兩個部分。例如，在此錯誤/filetype 配對：

```
 parseroutputsize_xls
```

   
 `parseroutputsize`錯誤與`xls`是發生錯誤之檔案的檔案類型。案例皆未辨識的檔案類型或檔案類型不帶不會套用到錯誤，您會看到值`noformat`取代此檔案類型。 
  
以下是原因的編製索引的錯誤和錯誤的可能描述的清單。
  
|**錯誤標記**|**描述**|
|:-----|:-----|
| `attachmentcount` <br/> |電子郵件有太多的附件，以及這些附件的一些未處理。  <br/> |
| `attachmentdepth` <br/> |內容擷取器和文件剖析器找到太多層的巢狀其他附件的附件。這些附件的一些不處理。  <br/> |
| `attachmentrms` <br/> |附件失敗解碼因為與其受 RMS 保護。  <br/> |
| `attachmentsize` <br/> |附加至電子郵件訊息檔太大及無法處理。  <br/> |
| `indexingtruncated` <br/> |當撰寫之已處理的電子郵件至索引，其中一個索引的屬性太大而且已被截斷。截斷的屬性列示於錯誤屬性欄位。  <br/> |
| `invalidunicode` <br/> |電子郵件訊息中包含無法處理為有效的 Unicode 文字。這個項目編製索引可能不完整。  <br/> |
| `parserencrypted` <br/> |加密附件或電子郵件的內容，和 Office 365 無法建立解碼內容。  <br/> |
| `parsererror` <br/> |分析處理時發生未知的錯誤。這通常會產生軟體錯誤或服務損毀。  <br/> |
| `parserinputsize` <br/> |會在附件已太大剖析器處理，以及該附件的剖析沒有發生或未完成。  <br/> |
| `parsermalformed` <br/> |附件格式不正確，而且無法剖析器所處理。此結果從可以舊檔案格式相容軟體或病毒假冒設為某個項目比其他宣告所建立的檔案。  <br/> |
| `parseroutputsize` <br/> |附件的剖析的輸出太大而必須將會遭到截斷。  <br/> |
| `parserunknowntype` <br/> |會在附件有 Office 365 無法偵測的檔案類型。  <br/> |
| `parserunsupportedtype` <br/> |會在附件有 Office 365could 偵測，但剖析該檔案類型不支援的檔案類型。  <br/> |
| `propertytoobig` <br/> |電子郵件屬性的值在 Exchange 儲存區已經太大而無法擷取並無法處理郵件。這通常只會以電子郵件訊息的本文屬性。  <br/> |
| `retrieverrms` <br/> |內容擷取器無法解碼 RMS 受保護的郵件。  <br/> |
| `wordbreakertruncated` <br/> |太多字已編製索引期間識別文件中。到達限制時停止處理屬性與屬性會遭到截斷。  <br/> |
   
錯誤欄位說明哪些欄位受到錯誤標記] 欄位中所列之處理錯誤。如果您例如搜尋屬性`subject`或`participants`，錯誤訊息的本文中將不會影響您的搜尋結果。這有助於決定完全哪些您可能需要進一步調查的部分已編製索引項目時。
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a>若要判斷您的組織衝擊部分已編製索引的電子郵件項目的使用 PowerShell 指令碼

下列步驟顯示如何執行 PowerShell 指令碼會搜尋所有的 Exchange 信箱中的所有項目和 （依計數以及由大小） 將會產生您組織的比例的部分已編製索引的電子郵件項目有關的報表並顯示的項目數 （和其檔案類型） 的每個索引所發生的錯誤。使用在前一節中的錯誤標記描述來識別索引的錯誤。
  
1. 使用.ps1; filename 尾碼將下列文字儲存到 Windows PowerShell 指令碼檔案例如， `PartiallyIndexedItems.ps1`。

```
  write-host "**************************************************"
  write-host "     Office 365 Security &amp; Compliance Center      " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "   eDiscovery Partially Indexed Item Statistics   " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "**************************************************"
  " " 
  # Create a search with Error Tags Refinders enabled
  Remove-ComplianceSearch "RefinerTest" -Confirm:$false -ErrorAction 'SilentlyContinue'
  New-ComplianceSearch -Name "RefinerTest" -ContentMatchQuery "size>0" -RefinerNames ErrorTags -ExchangeLocation ALL
  Start-ComplianceSearch "RefinerTest"
  # Loop while search is in progress
  do{
      Write-host "Waiting for search to complete..."
      Start-Sleep -s 5
      $complianceSearch = Get-ComplianceSearch "RefinerTest"
  }while ($complianceSearch.Status -ne 'Completed')
  $refiners = $complianceSearch.Refiners | ConvertFrom-Json
  $errorTagProperties = $refiners.Entries | Get-Member -MemberType NoteProperty
  $partiallyIndexedRatio = $complianceSearch.UnindexedItems / $complianceSearch.Items
  $partiallyIndexedSizeRatio = $complianceSearch.UnindexedSize / $complianceSearch.Size
  " "
  "===== Partially indexed items ====="
  "         Total          Ratio"
  "Count    {0:N0}{1:P2}" -f $complianceSearch.Items.ToString("N0").PadRight(15, " "), $partiallyIndexedRatio
  "Size(GB) {0:N2}{1:P2}" -f ($complianceSearch.Size / 1GB).ToString("N2").PadRight(15, " "), $partiallyIndexedSizeRatio
  " "
  Write-Host ===== Reasons for partially indexed items =====
  foreach($errorTagProperty in $errorTagProperties)
  {
      $name = $refiners.Entries.($errorTagProperty.Name).Name
      $count = $refiners.Entries.($errorTagProperty.Name).TotalCount
      $frag = $name.Split("{_}")
      $errorTag = $frag[0]
      $fileType = $frag[1]
      if ($errorTag -ne $lastErrorTag)
      {
          $errorTag
      }
      "    " + $fileType + " => " + $count
      $lastErrorTag = $errorTag
  }
  
```
   
2. [連線至 Office 365 安全性&amp;規範中心 PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627084)。
    
3. 安全性&amp;規範中心 PowerShell 中移至您在步驟 1 中，儲存指令碼的資料夾，然後執行指令碼 ；例如：

    ```
    .\PartiallyIndexedItems.ps1
    ```
   
以下是範例於指令碼所傳回的輸出。
  
![從指令碼所產生您組織的曝光度至部分已編製索引的電子郵件項目上的報表輸出範例](media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)
  
注意下列事項：
  
1. 總人數及的電子郵件項目大小與您的組織比例的部分已編製索引的電子郵件項目 （依計數以及由大小）
    
2. 清單錯誤標記及對應的檔案類型發生錯誤。
  
## <a name="see-also"></a>另請參閱

[位於 Office 365 中內容搜尋的已局部編製索引項目](partially-indexed-items-in-content-search.md)
