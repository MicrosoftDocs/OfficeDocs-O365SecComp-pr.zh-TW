---
title: 形成查詢以搜尋儲存在網站上的敏感資料
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: 與資料外洩防護 (DLP) 在 SharePoint Online 中，您可以探索包含整個您的租用戶的敏感資料的文件。 探索文件之後，您可以與文件擁有者協力保護資料。 本主題可以協助您進行查詢，以搜尋敏感資料。
ms.openlocfilehash: 74914ec934ece773e7a9748dfc821cea7c84963c
ms.sourcegitcommit: ed822a776d3419853453583e882f3c61ca26d4b2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2019
ms.locfileid: "30410708"
---
# <a name="form-a-query-to-find-sensitive-data-stored-on-sites"></a>形成查詢以搜尋儲存在網站上的敏感資料

使用者經常會在網站上儲存敏感資料，例如信用卡號碼、身分證字號，或其他個人資料，長期下來，這會讓組織處於資料遺失的巨大風險中。 儲存在網站上的文件，包括 OneDrive for Business 網站-無法與組織外，無須資訊的存取權的人員共用。 與資料外洩防護 (DLP) 在 SharePoint Online 中，您可以探索包含整個您的租用戶的敏感資料的文件。 探索文件之後，您可以與文件擁有者協力保護資料。 本主題可以協助您進行查詢，以搜尋敏感資料。
  
> [!NOTE]
> 電子化探索或 eDiscovery 和 DLP 是高階功能，需要[SharePoint Online 方案 2](https://go.microsoft.com/fwlink/?LinkId=510080)。 
  
## <a name="forming-a-basic-dlp-query"></a>形成基本 DLP 查詢

基本 DLP 查詢是由三個部分組成：SensitiveType、計數範圍及信賴範圍。 下圖中，所示**SensitiveType:"\<類型\>」** 是必要的兩者**|\<計算範圍\>** 和**|\<信賴範圍\>** 是選擇性的。 
  
![查詢範例分為必要和選用](media/DLP-query-example-text.png)
  
### <a name="sensitive-type---required"></a>敏感類型 - 必要

那麼各個部分分別是什麼？ SharePoint DLP queries 通常開頭屬性`SensitiveType:"`和資訊類型的[敏感資訊類型詳細目錄](https://go.microsoft.com/fwlink/?LinkID=509999)，名稱和結尾`"`。 您也可以使用您為組織建立[自訂機密資訊類型](create-a-custom-sensitive-information-type.md)的名稱。 例如，您可能要尋找包含信用卡號碼的文件。 在這類工作執行個體，您會使用下列格式： `SensitiveType:"Credit Card Number"`。 因為您未包含計數範圍或信賴範圍，該查詢會傳回信用卡號碼會偵測到每個文件。 這是您可以執行的最簡單的查詢，會傳回最多結果。 請記住，敏感類型的拼字和空格有影響。 
  
### <a name="ranges---optional"></a>範圍 - 選用

下一步] 兩個部分都範圍，讓我們快速檢查某個範圍的外觀。 在 SharePoint DLP queries，基本的範圍由兩個英文句點隔開的兩個數字這看起來像這樣： `[number]..[number]`。 比方說，如果`10..20`是使用，該範圍會擷取介於 10 到 20 的數字。 有許多不同的範圍組合，本主題涵蓋其中一些組合。 
  
讓我們將計數範圍新增至查詢。 您可以使用 count 範圍，定義文件需要包含才能包含在查詢結果中的敏感資訊的發生次數。 例如，如果您想要傳回只包含完全五個信用卡號碼的文件查詢，請使用這個： `SensitiveType:"Credit Card Number|5"`。 計數範圍也可以協助您識別有高度風險的文件。 例如，您的組織可能會將具有 5 個以上信用卡號碼的文件視為高風險。 若要尋找橫此準則的文件，您會使用此查詢： `SensitiveType:"Credit Card Number|5.."`。 或者，您可以找到具有五個文件或更少信用卡卡號等使用此查詢： `SensitiveType:"Credit Card Number|..5"`。 
  
#### <a name="confidence-range"></a>信賴範圍

最後，信賴範圍是已偵測之敏感類型實際符合的信賴等級。 信賴範圍值的運作方式與計數範圍類似。 您不用包含計數範圍也可以形成查詢。 例如，若要搜尋的任何數量的信用卡卡號的文件-只要信賴範圍為 85%或更高版本，您可以使用此查詢： `SensitiveType:"Credit Card Number|*|85.."`。 
  
> [!IMPORTANT]
> 星號 ( `*`) 是萬用字元表示任何值運作。 您可以使用萬用字元 ( `*`) 是計數範圍中或在信賴範圍，但不是在敏感類型。 
  
### <a name="additional-query-properties-and-search-operators-available-in-the-ediscovery-center"></a>可以在 eDiscovery 中心取得的其他查詢屬性和搜尋運算子

在 SharePoint 中的 DLP 也引進 LastSensitiveContentScan 屬性，可協助您搜尋掃描在特定時間範圍內的檔案。 如需與查詢範例`LastSensitiveContentScan`屬性，請參閱下一節中的[複雜查詢的範例](form-a-query-to-find-sensitive-data-stored-on-sites.md#BKMK_ExamplesOfComplexQueries)。 
  
您可以使用 DLP 特有的屬性，來建立查詢時，不僅標準 SharePoint eDiscovery 搜尋內容例如：`Author`或`FileExtension`。 您可以使用運算子來建立複雜查詢。 可用的屬性和運算子的清單，請參閱 <<c0>使用搜尋屬性和運算子與 eDiscovery部落格文章。 
  
## <a name="examples-of-complex-queries"></a>範例

下列範例會使用不同的敏感類型、 屬性及運算子來說明如何您還可以調整您的查詢來尋找完全您要尋找的。
  
|**Query**|**說明**|
|:-----|:-----|
| `SensitiveType:"International Banking Account Number (IBAN)"` <br/> |名稱可能看起來有些怪異因為它是這麼久，但它是該敏感類型的正確名稱。 請務必使用 509999[敏感資訊類型詳細目錄](https://go.microsoft.com/fwlink/?LinkID=509999)。 您也可以使用您為組織建立[自訂機密資訊類型](create-a-custom-sensitive-information-type.md)的名稱。  <br/> |
| ' SensitiveType:"Credit Card Number|1..4294967295|1..100"' <br/> |這會傳回文件至少一個相符項目敏感類型"Credit Card Number"。 每個範圍的值分別是最小值與最大值。 簡單的方式來撰寫此查詢是`SensitiveType:"Credit Card Number"`，但其中是何樂趣？  <br/> |
| ' SensitiveType:"Credit Card Number| 5..25"AND LastSensitiveContentScan:"8/11/2018..8/13/2018 」 ' <br/> |這會從 2018 年 8 月 11 日到 2018 年 8 月 13 日傳回 5 25 個信用卡號碼已掃描的文件。  <br/> |
| ' SensitiveType:"Credit Card Number| 5..25"AND LastSensitiveContentScan:"8/11/2018..8/13/2018 」 不 FileExtension:XLSX' <br/> |這會從 2018 年 8 月 11 日到 2018 年 8 月 13 日傳回 5 25 個信用卡號碼已掃描的文件。 XLSX 副檔名的檔案不包含在查詢結果中。  `FileExtension`是您可以在查詢中包含的許多屬性之一。 如需詳細資訊，請參閱 <<c0>使用搜尋屬性和運算子與 eDiscovery。  <br/> |
| `SensitiveType:"Credit Card Number" OR SensitiveType:"U.S. Social Security Number (SSN)"` <br/> |這會傳回包含信用卡號碼或身分證字號的文件。  <br/> |
   
## <a name="examples-of-queries-to-avoid"></a>範例

並非所有查詢都可以同等建立。 下表提供不適用於 SharePoint 中的 DLP 的查詢的範例，並說明原因。
  
|**不受支援的查詢**|**原因**|
|:-----|:-----|
| ' SensitiveType:"Credit Card Number|.."` <br/> |您必須至少新增一個數值。  <br/> |
| `SensitiveType:"NotARule"` <br/> |「 NotARule 」 不是有效的敏感類型名稱。 在 DLP queries 運作僅[敏感資訊類型詳細目錄](https://go.microsoft.com/fwlink/?LinkID=509999)中的名稱。  <br/> |
| ' SensitiveType:"Credit Card Number|0 」 ' <br/> |零不是有效的最小值或指定範圍中的最大值。  <br/> |
| `SensitiveType:"Credit Card Number"` <br/> |很可能很難看見，但沒有空白字元額外之間 」 信用卡 」 和 「 卡片 」，可以加快查詢無效。 使用[敏感資訊類型詳細目錄](https://go.microsoft.com/fwlink/?LinkID=509999)中的確切敏感類型名稱。  <br/> |
| ' SensitiveType:"Credit Card Number|1.。 3 」 ' <br/> |雙句號部分不應該以空格分隔。  <br/> |
| ' SensitiveType:"Credit Card Number| |1.|80.."' <br/> |有太多管道分隔符號 （|). 請改為按照此格式: ' SensitiveType:"Credit Card Number|1.|80.."' <br/> |
| ' SensitiveType:"Credit Card Number|1.|80..101"' <br/> |因為信賴值表示百分比，他們不能超過 100。 請改為選擇 1 到 100 的數字。  <br/> |
   
## <a name="for-more-information"></a>如需詳細資訊

[機密資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)
  
[在 Office 365 安全性執行內容搜尋&amp;合規性中心](run-a-content-search-in-the-security-and-compliance-center.md)
  
[內容搜尋的關鍵字查詢與搜尋條件](keyword-queries-and-search-conditions.md)
  

