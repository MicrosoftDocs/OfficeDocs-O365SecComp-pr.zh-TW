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
# <a name="export-documents-from-a-review-set"></a>從檢閱集匯出文件

您可以使用下列其中一種方法, 從審閱集中匯出簡報或外部考核的內容:

- [下載檔案](#download-documents-from-a-review-set)
 
- [匯出檔](#export-documents-from-a-review-set)

## <a name="download-documents-from-a-review-set"></a>從審閱集下載檔案

下載提供一種簡單的方法, 可從原生格式的審閱集下載內容。 它會利用瀏覽器的資料傳輸功能, 讓下載準備就緒後就會出現瀏覽器提示。 使用此方法下載的檔案會壓縮到容器檔案中, 並將成為專案層級檔案。 這表示如果您選取附件, 您會自動收到包含附件的電子郵件。 同樣地, 如果您選取內嵌在 word 檔中的 excel 試算表, 您會收到包含 excel 試算表的 word 檔。 下載的專案會保留上次修改的日期, 可以視為檔案屬性。

若要從審閱集中下載內容, 請先選取您想要下載的檔案, 然後選取 [動作] 功能表下的 [下載]。

![自動產生電腦描述的螢幕擷取畫面](../media/eDiscoDownload.png)

## <a name="export-documents-from-a-review-set"></a>從檢閱集匯出文件

匯出可讓使用者自訂下載套件所包含的內容。 它提供具有下列設定的設定頁面:

### <a name="metadata-file"></a>元資料檔案

這可以被視為您的「載入檔案」, 其中包含與匯出的檔案相關聯的中繼資料。 如需元資料檔案中可用的欄位清單, 請\[參閱\]link。 此檔案通常可由3個<sup>rd</sup>方程式的後續工具 ingested。

### <a name="tag-data"></a>標記資料

此內容會新增為元資料檔案中的欄位。 它包含所有在複查集中套用的標記資訊。

### <a name="text-files"></a>文字檔

可以為從審查集匯出的每個檔案產生文字檔。 通常, 服務合作夥伴會將這些檔案作為 ingesting 資料的一部分, 做為3個<sup>rd</sup>方程式的後續工具。

### <a name="redacted-files"></a>Redacted 檔案

如果在審閱期間產生 redacted 的 Pdf, 這些檔案會在匯出期間使用。 使用者可以決定是否僅匯出本機檔案, 或將具有密文的 natives 取代為 Pdf 中燒制。

### <a name="export-location"></a>匯出位置

如果在匯出時提供詳細資料, 則匯出的內容會傳遞至 Microsoft 提供的 Azure blob 或客戶的 blob。

### <a name="export-structure"></a>匯出結構

從審閱集匯出內容時, 會將內容組織在下列結構中。

  - 根資料夾–下載識別碼
    
      - 匯出\_load\_file .csv = metadata file
    
      - Summary = 包含匯出統計資料的摘要檔案
    
      - 輸入\_或原\_生檔案 = 包含所有原生檔案
    
      - 錯誤\_檔案 = 包含匯出所包含的任何錯誤檔案
        
          - ExtractionError –含有任何可用的中繼資料的 csv, 這些檔案未從父檔案正確解壓縮
        
          - ProcessingError –含有處理錯誤的內容。 此內容的專案層級表示如果附件發生處理錯誤, 包含附件的電子郵件會包含在此資料夾中。
    
      - 解壓縮\_的\_文字檔 = 包含處理時所產生的所有解壓縮文字檔。