---
title: 建立搜尋查詢
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
ms.openlocfilehash: a33ecb6e1a2549b6bdc3bde9897b8a75e742b482
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151925"
---
# <a name="build-search-queries"></a>建立搜尋查詢

在建置查詢，您可以使用各種關鍵字和條件來定義要尋找的項目。

## <a name="keyword-searches"></a>關鍵字搜尋

在 [**關鍵字**] 方塊中輸入搜尋查詢。 您可以指定關鍵字、例如傳送和接收日期的郵件屬性，或者例如檔案名稱或文件上次變更的日期的文件屬性。 您可以使用更複雜的查詢，使用布林運算子，例如**AND**、**或**、**不**、 和**NEAR**。 您也可以搜尋 （如社會安全編號） 中的文件或外部共用的文件中搜尋的敏感資訊。 如果您將 [關鍵字] 方塊保留空白，位於指定的內容位置中的所有內容將會都包含在搜尋結果中。
    
或者，您可以按一下**顯示關鍵字清單**] 核取方塊並輸入每一列中的關鍵字。 如果您這麼做時，每一列上的關鍵字來類似功能中建立搜尋查詢的**OR**運算子邏輯運算子 ( **c:s**) 連線。 
    
為什麼要使用關鍵字清單？ 您可以取得顯示多少個項目比對每個關鍵字的統計資料。 這可協助您快速找出哪些關鍵字是最 （和至少） 有效。 您也可以使用 （以括號括住） 的關鍵字文句] 列中。 如需搜尋統計資料的詳細資訊，請參閱 <<c0>搜尋統計資料。

## <a name="conditions"></a>條件
    
您可以新增搜尋條件縮小搜尋範圍，並傳回更精細的結果集。 每個條件將子句新增至搜尋查詢，建立及執行當您啟動搜尋。 條件以邏輯方式是透過類似功能**AND**運算子邏輯運算子 (**c:c**) 連接至 （在 [關鍵字] 方塊中指定） 的關鍵字查詢。 這表示項目必須符合的關鍵字查詢和結果中包含的一或多個條件。 這就是條件如何協助您縮小搜尋結果。 清單和說明您可以在搜尋查詢中使用的條件，請參閱 「 搜尋條件 」 一節中[關鍵字查詢和搜尋條件的內容搜尋](../keyword-queries-and-search-conditions.md#search-conditions)。


