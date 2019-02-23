---
title: 建立搜尋查詢
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 8e7f3d798d3b6cfe25d57b941ed2be1d8d5e92b6
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216983"
---
# <a name="build-search-queries"></a>建立搜尋查詢

在建置您的查詢，您可以使用各種關鍵字和條件來定義要尋找的項目。

## <a name="keyword-searches"></a>關鍵字搜尋

在 [**關鍵字**] 方塊中輸入搜尋查詢。您可以指定關鍵字，訊息屬性例如傳送及接收日期或文件內容，例如檔案名稱或上次變更文件的日期。您可以使用較複雜的查詢使用布林運算子，例如**AND**、**或**、**不**及**NEAR**。您也可以搜尋文件或搜尋功能已從外部共用的文件中的機密資訊 （例如社會安全編號）。如果 [關鍵字] 方塊中保留空白，將會在搜尋結果中包含位於指定之內容的位置中的所有內容。
    
或者，您可以按一下 [**顯示關鍵字清單**] 核取方塊和類型中的每一列的關鍵字。如果您這樣做，在每一列的關鍵字連接的作用與**OR**運算子會建立搜尋查詢中相似的邏輯運算子 ( **c:s**) 所連接。 
    
為什麼要選擇使用 [關鍵字] 清單？您可以取得顯示多少個項目比對每個關鍵字的統計資料。這可協助您快速識別出哪些關鍵字是最 （且至少） 有效。您也可以使用 （以括弧括住） 的關鍵字文句] 列中。如需搜尋統計資料的詳細資訊，請參閱 ＜[搜尋統計資料](search-statistics.md)。

## <a name="conditions"></a>條件
    
您可以新增要將搜尋縮小並傳回結果集更精簡的搜尋條件。每個條件將子句新增至搜尋查詢，建立及執行當您啟動搜尋。條件是以邏輯方式連線到 （在 [關鍵字] 方塊中指定） 的關鍵字查詢類似的作用**和**運算子的邏輯運算子 （**列**）。這表示項目必須滿足的關鍵字查詢與結果中包含的一或多個條件。這是條件，縮減結果協助的方式。清單和說明您可以在搜尋查詢中使用的條件，請參閱 「 搜尋條件 」 一節[關鍵字查詢和搜尋條件的內容搜尋](../keyword-queries-and-search-conditions.md#search-conditions)。


