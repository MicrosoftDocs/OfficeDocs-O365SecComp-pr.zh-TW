---
title: 從工作集匯出文件
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 815b92b13ed09d8aec64f5207f1c82d910e2dce0
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32252044"
---
# <a name="export-documents-from-a-working-set"></a>從工作集匯出文件

匯出內容從工作集可以透過 3 不同的方法來完成：

## <a name="download"></a>下載

下載提供簡單的方法，從原生格式設定的設定工作下載內容。 它利用瀏覽器的資料傳輸功能，因此下載已準備好之後，就會顯示瀏覽器提示。 檔案下載使用此方法會壓縮成容器檔案，將項目層級的檔案。 這表示，如果您選取附件，您就會自動接收電子郵件包含附件。 同樣地，如果您選取 [已 excel 試算表內嵌於 word 文件，您會收到 word 文件與內嵌的 excel 試算表。 已下載的項目會保留檔案屬性為可檢視的上次修改的日期。

若要從工作集下載內容，請啟動選取您要下載，然後選取 「 下載 」 下 [動作] 功能表的檔案。

![說明自動產生之電腦的螢幕擷取畫面](../media/eDiscoDownload.png)

## <a name="export"></a>匯出

匯出可讓使用者自訂隨附的下載套件中的內容。 它提供設定] 頁面上使用下列設定：

### <a name="metadata-file"></a>中繼資料檔案

> 這可視為您 「 載入檔案"，其中包含您匯出的檔案相關聯的中繼資料。 如需中繼資料檔案中可用的欄位的清單，請參閱\[連結\]。 此檔案通常可以 ingested 3<sup>rd</sup>廠商工具所傳輸。

### <a name="tag-data"></a>標記資料

> 此內容會新增為中繼資料檔案中的欄位。 它包含所有的工作集套用的標籤資訊。

### <a name="text-files"></a>文字檔

> 文字檔案可以產生的每個工作集從匯出的檔案。 通常時間這些檔案所需的服務合作夥伴一部分 ingesting 資料到 3<sup>rd</sup>廠商工具傳輸。

### <a name="redacted-files"></a>Redacted 的檔案

> 如果檢閱期間所產生 redacted 的 Pdf，這些檔案匯出期間都使用。 使用者可以決定是否要匯出僅適用於原生檔案，或取代人民 Pdf 中具有與燒錄 redactions。

### <a name="export-location"></a>匯出的位置

> 匯出的內容會傳遞至下列一項 Microsoft 提供您可以使用 Azure blob 或客戶的 blob，如果在匯出並提供詳細資料。

## <a name="export-structure"></a>匯出結構

當內容從工作集匯出時，內容被組織中的下列結構。

  - 根資料夾 – 下載識別碼
    
      - 匯出\_載入\_file.csv = 中繼資料檔案
    
      - Summary.txt = 匯出統計資料摘要檔案
    
      - 輸入\_或原生\_檔案 = 包含所有的原生檔案
    
      - 錯誤\_檔案 = 包含任何包含在匯出的錯誤檔案
        
          - ExtractionError – csv 包含不正確地從父檔案解壓縮的任何的檔案可用的中繼資料
        
          - ProcessingError – 與處理錯誤的內容。 此內容是表示如果附件時發生錯誤處理，包含附件的電子郵件將會包含在此資料夾的項目層級。
    
      - 擷取\_文字\_檔案 = 包含所有在處理所產生的擷取的文字檔案。

## <a name="working-set"></a>工作集

內容可以新增至另一個工作集。