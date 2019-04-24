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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 使用關鍵字和條件來縮小搜尋範圍時搜尋資料時使用 Microsoft 365 中的資料進行調查。
ms.openlocfilehash: eeca1bf7ff89d1b7f79ceeed3334668e354f035a
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262881"
---
# <a name="build-search-queries"></a>建立搜尋查詢

在建置搜尋查詢時，您可以使用關鍵字來尋找特定的內容和條件來縮小搜尋以返回您調查與最相關的項目的範圍。

![使用關鍵字和條件來縮小搜尋結果](../media/SearchQueryBox.png)

## <a name="keyword-searches"></a>關鍵字搜尋

在搜尋查詢中的 [**關鍵字**] 方塊中輸入關鍵字查詢。 您可以指定關鍵字、 電子郵件內容，（例如傳送和接收日期） 或文件內容 （例如檔案名稱或上次變更文件的日期）。 您可以使用更複雜的查詢，使用布林運算子，例如**AND**、**或**、**不**、 和**NEAR**。 您也可以在 SharePoint 和 OneDrive （不在電子郵件） 或搜尋的外部共用的文件中的文件中搜尋的敏感資訊 （例如社會安全編號）。 如果您將 [**關鍵字**] 方塊保留空白，位於指定的內容位置中的所有內容將會都包含在搜尋結果中。
    
或者，您可以按一下**顯示關鍵字清單**] 核取方塊並輸入關鍵字或每一列中的關鍵字文句。 如果您這麼做時，由邏輯運算子 （這當成*c:s*） 中建立搜尋查詢的**OR**運算子類似功能連線每一列中的關鍵字。 這表示包含任何資料列中的任何關鍵字的項目將會包含在搜尋結果。

![使用 [關鍵字] 清單以取得在查詢中每個關鍵字統計資料](../media/KeywordListSearch.png)

為什麼要使用關鍵字清單？ 您可以取得顯示多少個項目比對關鍵字清單中的每個關鍵字的統計資料。 這可協助您快速找出最 （和至少） 有效的關鍵字。 您也可以使用關鍵字片語 （圍繞括號） 中 [關鍵字] 清單中的資料列。 如需搜尋統計資料的詳細資訊，請參閱 <<c0>搜尋統計資料。

> [!NOTE]
> 若要協助減少大型關鍵字清單所導致的問題，您正在限制最多 20 列在 [關鍵字] 清單中的項目。

## <a name="conditions"></a>條件
    
您可以新增搜尋條件縮小搜尋範圍，並傳回更精細的結果集。 每個條件將子句新增至搜尋查詢，建立及執行當您啟動搜尋。 條件是以邏輯方式連線到 （在 [關鍵字] 方塊中指定） 的關鍵字查詢邏輯運算子 （這當成*c:c*） 都與**AND**運算子相似的功能。 這表示項目必須符合的關鍵字查詢和搜尋結果中包含的一或多個條件。 這就是條件如何協助您縮小搜尋結果。 清單和說明您可以在搜尋查詢中使用的條件，請參閱 「 搜尋條件 」 一節中[關鍵字查詢和搜尋條件](../keyword-queries-and-search-conditions.md#search-conditions)。
