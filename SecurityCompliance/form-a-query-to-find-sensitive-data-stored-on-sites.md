---
title: 形成查詢以搜尋儲存在網站上的敏感資料
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 3019fbc5-7f15-4972-8d0e-dc182dc7f836
description: 與資料外洩防護 (DLP) SharePoint Online 中，您可以探索包含機密資料整個租用戶中的文件。之後探索文件，您可以使用以保護資料的文件擁有者。本主題可協助您的表單來搜尋機密資料的查詢。
ms.openlocfilehash: 3dc1081d4627f1a26c50eed84f733c31a3f6c194
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217233"
---
# <a name="form-a-query-to-find-sensitive-data-stored-on-sites"></a>形成查詢以搜尋儲存在網站上的敏感資料

使用者通常儲存機密資料，例如信用卡號碼、 社會安全編號，或個人，在他們的網站和一段時間這會暴露鍰等重要資料遺失的風險。儲存在網站上的文件 — 包括 OneDrive for Business 的網站-無法共用組織外不應該具有存取資訊的人員。與資料外洩防護 (DLP) SharePoint Online 中，您可以探索包含機密資料整個租用戶中的文件。之後探索文件，您可以使用以保護資料的文件擁有者。本主題可協助您的表單來搜尋機密資料的查詢。
  
> [!NOTE]
> 電子化搜索或 eDiscovery 及 DLP 是 premium 功能需要進行[SharePoint Online 計劃 2](https://go.microsoft.com/fwlink/?LinkId=510080)。 
  
## <a name="forming-a-basic-dlp-query"></a>形成基本 DLP 查詢

有三個部分構成的基本的 DLP 查詢： SensitiveType、 計算範圍和信賴的範圍。如下圖所示下， **SensitiveType:"\<類型\>"** 是必要的並同時**|\<計算的範圍\>** 和**|\<信賴範圍\>** 皆為選用。 
  
![查詢範例分為必要和選用](media/DLP-query-example-text.png)
  
### <a name="sensitive-type---required"></a>敏感類型 - 必要

那麼每一個部分是什麼？使用屬性通常是開始 SharePoint DLP 查詢`SensitiveType:"`和資訊類型名稱的[敏感資訊類型詳細目錄](https://go.microsoft.com/fwlink/?LinkID=509999)，且結尾為`"`。您也可以使用您為組織建立[自訂的敏感資訊類型](create-a-custom-sensitive-information-type.md)的名稱。例如，您可能會尋找包含信用卡數字的文件。在這種執行個體，您可以使用下列格式： `SensitiveType:"Credit Card Number"`。因為您沒有加入計數範圍或信賴範圍、 該查詢會傳回信用卡號會偵測到每個文件。這是最簡單的查詢，您可以執行，並且會傳回大部分的結果。請記住，拼字檢查及機密類型的間距很重要。 
  
### <a name="ranges---optional"></a>範圍 - 選用

下一步] 兩個部分都範圍，讓我們快速檢查某個範圍的外觀。在 SharePoint DLP 查詢基本的範圍會以表示以兩個句號分隔的兩個號碼這看起來像這樣： `[number]..[number]`。例如，如果`10..20`會使用該範圍會擷取介於 10%到 20 的數字。有許多不同的範圍組合及幾種本主題。 
  
我們將計數範圍新增至查詢。您可以使用 count 範圍定義中的文件必須包含在查詢結果中包含之前的機密資訊的次數。例如，如果您想要傳回含有完全五個信用卡號的文件查詢，請使用此： `SensitiveType:"Credit Card Number|5"`。Count 範圍也可以協助您識別造成的風險高度的文件。例如，您的組織可能高風險考慮五個或多個信用卡號與文件。若要尋找並排列此準則的文件，您可以使用此查詢： `SensitiveType:"Credit Card Number|5.."`。或者，您可以找到五個文件或更少使用此查詢信用卡片號碼： `SensitiveType:"Credit Card Number|..5"`。 
  
#### <a name="confidence-range"></a>信賴範圍

最後，confidence 範圍是信賴偵測到的機密類型的實際相符項目層級。信賴範圍的值的運作方式很類似計算的範圍。您可以表單查詢而不需納入計數範圍。例如，若要搜尋的任意數量的信用卡號與文件 — 只要信賴範圍是從 85%或更高-您可以使用此查詢： `SensitiveType:"Credit Card Number|*|85.."`。 
  
> [!IMPORTANT]
> 星號 ( `*`) 是表示任何值的運作的萬用字元。您可以使用萬用字元 ( `*`) [計數範圍中或在信賴範圍中但不是在機密的類型。 
  
### <a name="additional-query-properties-and-search-operators-available-in-the-ediscovery-center"></a>可以在 eDiscovery 中心取得的其他查詢屬性和搜尋運算子

在 SharePoint 中的 DLP 也介紹 LastSensitiveContentScan 屬性，可協助您搜尋特定的時間範圍內所掃描的檔案。使用查詢範例`LastSensitiveContentScan`屬性，請參閱下一節中的[複雜查詢範例](form-a-query-to-find-sensitive-data-stored-on-sites.md#BKMK_ExamplesOfComplexQueries)。 
  
您可以如使用 DLP 特有的屬性來建立查詢時，不僅標準 SharePoint eDiscovery 搜尋屬性`Author`或`FileExtension`。您可以使用運算子來建立複雜的查詢。可用的屬性和運算子清單，請參閱 ＜[使用搜尋屬性與使用 eDiscovery 運算子](https://go.microsoft.com/fwlink/?LinkId=510093)部落格文章。 
  
## <a name="examples-of-complex-queries"></a>範例

下列範例會使用不同的機密類型、 屬性及運算子來說明您可以在如何讓您查詢以尋找完全您正在尋找的項目。
  
|**查詢**|**說明**|
|:-----|:-----|
| `SensitiveType:"International Banking Account Number (IBAN)"` <br/> |因為它是這麼久，但該機密類型的正確名稱似乎怪異名稱。請務必使用[敏感資訊類型詳細目錄](https://go.microsoft.com/fwlink/?LinkID=509999)中的實際名稱。您也可以使用您為組織建立[自訂的敏感資訊類型](create-a-custom-sensitive-information-type.md)的名稱。<br/> |
| `SensitiveType:"Credit Card Number|1..4294967295|1..100"` <br/> |這會具有至少一個相符的文件傳回成機密類型"信用卡號"。每個範圍的值是個別的最小和最大值。更簡單的方法來撰寫此查詢是`SensitiveType:"Credit Card Number"`，但所在中的樂趣吗？<br/> |
| `SensitiveType:"Credit Card Number| 5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018"` <br/> |這會從 2018 年 8 月 11、 透過 2018 年 8 月 13、 傳回 5-25 信用卡號所掃描的文件。  <br/> |
| `SensitiveType:"Credit Card Number| 5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018" NOT FileExtension:XLSX` <br/> |這會從 2018 年 8 月 11、 透過 2018 年 8 月 13、 傳回 5-25 信用卡號所掃描的文件。XLSX 副檔名的檔案不包含在查詢結果。 `FileExtension`是其中一個可以包含在查詢中的許多屬性。如需詳細資訊，請參閱[使用搜尋屬性與使用 eDiscovery 的運算子](https://go.microsoft.com/fwlink/?LinkId=510093)。<br/> |
| `SensitiveType:"Credit Card Number" OR SensitiveType:"U.S. Social Security Number (SSN)"` <br/> |這會傳回包含信用卡號碼或身分證字號的文件。  <br/> |
   
## <a name="examples-of-queries-to-avoid"></a>範例

並非所有的查詢會建立相等。下表提供範例不使用 DLP SharePoint 中的查詢，並說明為何。
  
|**不受支援的查詢**|**原因**|
|:-----|:-----|
| `SensitiveType:"Credit Card Number|.."` <br/> |您必須至少新增一個數值。  <br/> |
| `SensitiveType:"NotARule"` <br/> |"NotARule"不是有效的機密類型名稱。DLP 查詢中運作僅[敏感資訊類型詳細目錄](https://go.microsoft.com/fwlink/?LinkID=509999)中的名稱。<br/> |
| `SensitiveType:"Credit Card Number|0"` <br/> |最小值或範圍中的最大值為零而言無效。  <br/> |
| `SensitiveType:"Credit Card Number"` <br/> |很可能很難將看到，但是沒有額外"信用"和"卡片"讓查詢無效之間的空格。使用[敏感資訊類型詳細目錄](https://go.microsoft.com/fwlink/?LinkID=509999)中的確切機密類型名稱。<br/> |
| `SensitiveType:"Credit Card Number|1. .3"` <br/> |不應該以空格分隔的兩個週期部分。  <br/> |
| `SensitiveType:"Credit Card Number| |1..|80.."` <br/> |有太多管道分隔符號 （|).請改為遵循此格式：`SensitiveType: "Credit Card Number|1..|80.."` <br/> |
| `SensitiveType:"Credit Card Number|1..|80..101"` <br/> |信賴值都代表百分比，因為它們不能超過 100。而是介於 1 到 100 選擇數字。  <br/> |
   
## <a name="for-more-information"></a>如需詳細資訊

[機密資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)
  
[Office 365 安全性執行內容的搜尋&amp;規範中心](run-a-content-search-in-the-security-and-compliance-center.md)
  
[內容搜尋的關鍵字查詢與搜尋條件](keyword-queries-and-search-conditions.md)
  

