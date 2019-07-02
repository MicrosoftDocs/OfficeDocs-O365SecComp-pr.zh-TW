---
title: 形成查詢以搜尋儲存在網站上的敏感資料
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: 使用 SharePoint Online 中的資料遺失防護 (DLP), 您可以探索在整個租使用者中包含敏感性資料的檔。 探索文件之後，您可以與文件擁有者協力保護資料。 本主題可以協助您進行查詢，以搜尋敏感資料。
ms.openlocfilehash: 2e76be22ce97a90b86a2ea089464f9b526ae4b70
ms.sourcegitcommit: 0d5a863f48914eeaaf29f7d2a2022618de186247
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2019
ms.locfileid: "34078009"
---
# <a name="form-a-query-to-find-sensitive-data-stored-on-sites"></a>形成查詢以搜尋儲存在網站上的敏感資料

使用者經常會在網站上儲存敏感資料，例如信用卡號碼、身分證字號，或其他個人資料，長期下來，這會讓組織處於資料遺失的巨大風險中。 儲存在網站上的檔 (包括商務用 OneDrive 網站) 可以與組織外部的人員共用, 而不應該存取該資訊。 使用 SharePoint Online 中的資料遺失防護 (DLP), 您可以探索在整個租使用者中包含敏感性資料的檔。 探索文件之後，您可以與文件擁有者協力保護資料。 本主題可以協助您進行查詢，以搜尋敏感資料。
  
> [!NOTE]
> 電子查詢或 eDiscovery, 以及 DLP 是需要[SharePoint Online 方案 2](https://go.microsoft.com/fwlink/?LinkId=510080)的高級功能。 
  
## <a name="forming-a-basic-dlp-query"></a>形成基本 DLP 查詢

基本 DLP 查詢是由三個部分組成：SensitiveType、計數範圍及信賴範圍。 如下圖所示, **SensitiveType: "\<\>type"** 是必要的, 而且**|\<計數範圍\> **和**|\<信賴範圍\> **都是選用的。 
  
![查詢範例分為必要和選用](media/DLP-query-example-text.png)
  
### <a name="sensitive-type---required"></a>敏感類型 - 必要

那麼各個部分分別是什麼？ SharePoint DLP 查詢通常是以屬性`SensitiveType:"`和[敏感資訊類型清單](https://go.microsoft.com/fwlink/?LinkID=509999)中的資訊類型名稱開始, 並以結尾。 `"` 您也可以使用您為組織建立的[自訂機密資訊類型](create-a-custom-sensitive-information-type.md)的名稱。 例如，您可能要尋找包含信用卡號碼的文件。 在這種情況下, 您可以使用下列格式: `SensitiveType:"Credit Card Number"`。 因為您未包含計數範圍或信賴範圍, 所以查詢會傳回偵測到信用卡號碼的每一份檔。 這是您可以執行的最簡單的查詢，會傳回最多結果。 請記住，敏感類型的拼字和空格有影響。 
  
### <a name="ranges---optional"></a>範圍 - 選用

接下來的兩個部分都是範圍, 讓我們快速檢查範圍的外觀。 在 SharePoint DLP 查詢中, 基本範圍是以兩個句點隔開的兩個數字來表示, 如下所`[number]..[number]`示: 例如, 如果`10..20`使用, 則該範圍會從10到20捕獲數位。 有許多不同的範圍組合，本主題涵蓋其中一些組合。 
  
讓我們將計數範圍新增至查詢。 您可以使用 count 範圍來定義在查詢結果中包含檔之前必須包含的機密資訊的發生次數。 例如, 如果您希望查詢只傳回正好包含五個信用卡號碼的檔, 請使用下列程式: `SensitiveType:"Credit Card Number|5"`。 計數範圍也可以協助您識別有高度風險的文件。 例如，您的組織可能會將具有 5 個以上信用卡號碼的文件視為高風險。 若要尋找符合此準則的檔, 您可以使用下列`SensitiveType:"Credit Card Number|5.."`查詢: 或者, 您可以使用下列查詢, 尋找具有五個或更少信用卡號碼的`SensitiveType:"Credit Card Number|..5"`檔:。 
  
#### <a name="confidence-range"></a>信賴範圍

最後，信賴範圍是已偵測之敏感類型實際符合的信賴等級。 信賴範圍值的運作方式與計數範圍類似。 您不用包含計數範圍也可以形成查詢。 例如, 若要搜尋具有任何數目信用卡號碼的檔, 只要信賴範圍為 85% 或更高, 您就可以使用此查詢: `SensitiveType:"Credit Card Number|*|85.."`。 
  
> [!IMPORTANT]
> 星號 ( `*`) 是萬用字元, 表示任何值都可以使用。 您可以在計數範圍或信賴`*`範圍中使用萬用字元 (), 但不能以敏感類型使用萬用字元。 
  
### <a name="additional-query-properties-and-search-operators-available-in-the-ediscovery-center"></a>可以在 eDiscovery 中心取得的其他查詢屬性和搜尋運算子

在 SharePoint 中, DLP 也會引入 LastSensitiveContentScan 屬性, 可協助您搜尋特定時間範圍內所掃描的檔案。 如需`LastSensitiveContentScan`屬性的查詢範例, 請參閱下一節中[複雜查詢的範例](#examples-of-complex-queries)。 
  
您可以使用 DLP 特有的屬性來建立查詢, 也可以使用標準的 SharePoint eDiscovery 搜尋屬性 (例如`Author`或`FileExtension`)。 您可以使用運算子來建立複雜查詢。 如需可用的屬性和運算子清單, 請參閱[使用搜尋屬性和運算子搭配 eDiscovery](https://go.microsoft.com/fwlink/?LinkId=510093)博客文章。 
  
## <a name="examples-of-complex-queries"></a>範例

下列範例會使用不同的機密類型、屬性及運算子, 來說明如何精簡查詢, 以精確尋找您要尋找的專案。
  
|**Query**|**說明**|
|:-----|:-----|
| `SensitiveType:"International Banking Account Number (IBAN)"` <br/> |此名稱可能看起來很奇怪, 因為它很長, 但是該敏感類型的正確名稱。 請務必使用[機密資訊類型清單](https://go.microsoft.com/fwlink/?LinkID=509999)中的確切名稱。 您也可以使用您為組織建立的[自訂機密資訊類型](create-a-custom-sensitive-information-type.md)的名稱。  <br/> |
| `SensitiveType:"Credit Card Number|1..4294967295|1..100"` <br/> |這會傳回與機密類型「信用卡號碼」至少有一個相符的檔。 每個範圍的值分別是最小值與最大值。 更簡單的方法來撰寫此查詢`SensitiveType:"Credit Card Number"`, 但是其中的有趣之處在于什麼？  <br/> |
| `SensitiveType:"Credit Card Number| 5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018"` <br/> |這會傳回從5-25 年8月11日到2018年8月13日 (2018) 掃描的信用卡號碼的檔。  <br/> |
| `SensitiveType:"Credit Card Number| 5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018" NOT FileExtension:XLSX` <br/> |這會傳回從5-25 年8月11日到2018年8月13日 (2018) 掃描的信用卡號碼的檔。 具有 .XLSX 副檔名的檔案不會包含在查詢結果中。  `FileExtension`是其中一個可包含在查詢中的屬性。 如需詳細資訊, 請參閱搭配[EDiscovery 使用搜尋屬性和運算子](https://go.microsoft.com/fwlink/?LinkId=510093)。  <br/> |
| `SensitiveType:"Credit Card Number" OR SensitiveType:"U.S. Social Security Number (SSN)"` <br/> |這會傳回包含信用卡號碼或身分證字號的文件。  <br/> |
   
## <a name="examples-of-queries-to-avoid"></a>範例

並非所有查詢都可以同等建立。 下表提供在 SharePoint 中無法搭配 DLP 使用的查詢範例, 並說明原因。
  
|**不受支援的查詢**|**原因**|
|:-----|:-----|
| `SensitiveType:"Credit Card Number|.."` <br/> |您必須至少新增一個數值。  <br/> |
| `SensitiveType:"NotARule"` <br/> |"NotARule" 不是有效的機密類型名稱。 在 DLP 查詢中, 只有[機密資訊類型](https://go.microsoft.com/fwlink/?LinkID=509999)的名稱可供使用。  <br/> |
| `SensitiveType:"Credit Card Number|0"` <br/> |零不是有效的範圍中的最小值或最大值。  <br/> |
| `SensitiveType:"Credit Card Number"` <br/> |可能很難看到, 但是在 "信用卡" 和 "卡片" 之間有額外的空白, 使查詢無效。 從[敏感資訊類型的清單](https://go.microsoft.com/fwlink/?LinkID=509999)中, 使用完全機密的類型名稱。  <br/> |
| `SensitiveType:"Credit Card Number|1. .3"` <br/> |兩個期間部分不能以空格隔開。  <br/> |
| `SensitiveType:"Credit Card Number| |1..|80.."` <br/> |有太多的管道定界符 (|). 請改為遵循此格式:`SensitiveType: "Credit Card Number|1..|80.."` <br/> |
| `SensitiveType:"Credit Card Number|1..|80..101"` <br/> |因為置信度值代表百分比, 所以不能超過100。 請改為選擇 1 到 100 的數字。  <br/> |
   
## <a name="for-more-information"></a>相關資訊

[機密資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)
  
[在 Office 365 安全性&amp;與合規性中心執行內容搜尋](run-a-content-search-in-the-security-and-compliance-center.md)
  
[內容搜尋的關鍵字查詢與搜尋條件](keyword-queries-and-search-conditions.md)
  

