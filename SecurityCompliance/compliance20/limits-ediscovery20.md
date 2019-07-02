---
title: 高級 eDiscovery 限制
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 深入瞭解 Microsoft 365 中的高級 eDiscovery 解決方案的作用限制。 這包括案例限制、索引限制, 以及使用搜尋工具收集案例資料時的搜尋限制。
ms.openlocfilehash: 622d2669457a2a1e84909aadae9b653ca37684ce
ms.sourcegitcommit: 803baca9f99a6691fb41a3308e799752e4d8f20c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2019
ms.locfileid: "35222287"
---
# <a name="limits-in-advanced-ediscovery"></a>進階電子文件探索的限制

本文說明 Microsoft 365 中的高級 eDiscovery 解決方案的限制。

## <a name="case-limits"></a>案例限制

下表列出高級 eDiscovery 中案例的限制。

|**限制的描述**|**限制**|
|:-----|:-----|
|可以新增至案例的檔總數 (針對案例中的所有審閱集)。  <br/> |1 百萬  <br/> |
|每個負載集的總檔案大小。  <br/> |100 GB  <br/> |
|每日載入至案例的資料總量。<br/> |2 TB <br/> |
|每個案例的載入集數目上限。  <br/> |15  <br/> |
|每個案例的審閱集數目上限。  <br/> |名 <br/> |
|||

## <a name="indexing-limits"></a>索引限制

下表列出高級 eDiscovery 中的索引限制。

|**限制的描述**|**限制**|
  |:-----|:-----|
  |從單一檔案解壓縮的字元數上限。  <br/> |10000000<sup>1</sup> <br/> |
  |單一檔案的大小上限。   <br/> |100 MB<sup>1</sup> <br/> |
  |檔中內嵌專案的最大深度。  <br/> |25<sup>1</sup> <br/> |
  |光學字元辨識 (OCR) 所處理的檔案大小上限。  <br/> |24 MB<sup>1</sup> <br/> |  
|||

## <a name="search-limits"></a>搜尋限制

本節所述的限制與使用 [**搜尋**] 索引標籤上的 [搜尋工具] 來收集案例的資料有關。 如需詳細資訊, 請參閱[在高級 eDiscovery 中收集案例的資料](collecting-data-for-ediscovery.md)。

|**限制的描述**|**限制**|
|:-----|:-----|
|可在單一搜尋中搜尋的信箱或網站數目上限。  <br/> |無限制  <br/> |
|可以同時執行的最大搜尋數目。  <br/> |無限制  <br/> | 
|單一使用者可以同時開始的最大搜尋數目。  <br/> |10   <br/> | 
|搜尋查詢的最大字元數 (包括運算子和條件)。  <br/> |**信箱**: 10000<br/>**網站**: 4000 搜尋所有網站或2000時, 搜尋最多20個網站<sup>2</sup> <br/> |
|前置詞萬用字元的最小 Alpha 字元數。例如,**一\* **或**設定\***。 <br/> |萬  <br/> |  
|使用前置字元萬用字元來搜尋精確的片語, 或使用前置字元萬用字元和**NEAR**或**ONEAR**布林運算子時, 所傳回的最大變化。  <br/> |10000 <sup>3</sup> <br/> |
|搜尋的預覽頁面上顯示的每個使用者信箱的專案數上限。 隨即會顯示最新的專案。   <br/> |100  <br/> |
|預覽頁面上顯示的所有信箱中的專案數上限。  <br/> |1,000  <br/> |
|可預覽搜尋結果的信箱數目上限。  如果有超過1000個信箱包含符合搜尋查詢的專案, 則預覽時只可使用具有最多結果的前1000個信箱。<br/> |1,000  <br/> |
|在預覽頁面上顯示的 SharePoint 和商務用 OneDrive 網站中的專案數上限。 隨即會顯示最新的專案。  <br/> |200  <br/> |
|可預覽搜尋結果的 SharePoint 和商務用 OneDrive 網站數目上限。 如果有超過200個網站包含符合搜尋查詢的專案, 則預覽中只能有最多包含最多結果的200網站。  <br/> |200  <br/> |
|在預覽頁面上針對搜尋顯示的每個公用資料夾信箱的專案數上限。  <br/> |100  <br/> |
|在預覽頁面上顯示的搜尋的所有公用資料夾信箱專案中找到的專案數上限。  <br/> |200  <br/> |
|可以預覽搜尋結果的公用資料夾信箱數目上限。 如果有500個以上的公用資料夾信箱包含符合搜尋查詢的專案, 則預覽時只可使用具有最多結果的前500個信箱。  <br/> |500  <br/> |
|||

## <a name="viewer-limits"></a>檢視器限制

|**限制的描述**|**限制**|
  |:-----|:-----|
  |可在原生檢視器中查看的 Excel 檔案大小上限。  <br/> |4 MB  <br/> |
|||

## <a name="review-set-download-limits"></a>審閱設定的下載限制

|**限制的描述**|**限制**|
|:-----|:-----|
|從審閱集下載的檔案大小總計或檔數目上限。  <br/> |3 MB 或50檔<sup>4</sup>|
|||

<br/>
<br/>

> [!NOTE]
> <sup>1</sup>任何超過單一檔案限制的專案都會顯示為處理錯誤。<br/>
> <sup>2</sup>當搜尋 SharePoint 和商務用 OneDrive 位置時, 所搜尋之網站 url 中的字元會受到此限制。<br/>
> <sup>3</sup>若為非片語查詢 (不使用雙引號的關鍵字值), 我們會使用特殊的前置詞索引。 這會告訴我們檔中有一個字, 而不是在檔中發生的位置。 若要執行片語查詢 (使用雙引號的關鍵字值), 我們需要比較檔中的文字在檔中的位置。 這表示我們無法使用前置字元索引做為片語查詢。 在這種情況下, 我們會在內部使用首碼所擴充的所有可能文字來展開查詢;例如, **time\* **可以展開為 **"time or timer or time or time or timex or timeboxed or ..."**。 10000的限制是 word 可擴充的變化數目上限, 而不是符合查詢的檔數目上限。 非片語字詞沒有上限。<br/>
> <sup>4</sup>此限制適用于從審閱集中下載選取的檔。 它不會套用到從審閱集中匯出檔。 如需下載及匯出檔的詳細資訊, 請參閱[在高級 eDiscovery 中匯出事例資料](exporting-data-ediscover20.md)。 <br/>

