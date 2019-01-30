---
title: 搜尋統計資料
ms.author: markjjo
author: esclee
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: c5b7caff3550d42d84408d6b4e966655b8341123
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607588"
---
# <a name="search-statistics"></a>搜尋統計資料
您可以驗證您的搜尋結果的其中一個方法是要查看周圍以確保它們對齊與您的預期結果的統計資料。搜尋完成時，搜尋的詳細資訊彈出式上顯示高層級的統計資料：
- 數字及擷取搜尋的項目量
- 數目與大量的部分編製索引/未建立索引在搜尋位置中找到的項目
- 搜尋的信箱及位置的數目。以檢視詳細統計資料，請按一下 ["統計資料 」 搜尋的詳細資訊彈出式。

## <a name="summary"></a>摘要
在摘要檢視中，您可以看到位置類型 (例如 Exchange) 來細分的搜尋結果。每個位置類型，您可以看到：
- 位置鎖符合搜尋條件的項目數目
- 從下列位置符合搜尋條件的項目數
- 總量符合搜尋條件的項目。

## <a name="top-locations"></a>上方的位置
在上方的位置檢視中，您會看到最符合項目的個別位置。針對每個位置中，您會看到：
- 位置名稱 (例如 SharePoint URL)
- 位置類型
- 比對搜尋條件的項目數
- 總量符合搜尋條件的項目。

## <a name="queries"></a>查詢
如果您已在查詢中使用 (c:s) 關鍵字] 或 [關鍵字列，您可以看到分解為您在每個位置類型的查詢檢視中的查詢。每個位置類型，您會看到：
- 組件： 此資料行必須單字"主要"或"關鍵字"。「 主要"表示 [列在整個查詢中，提供統計資料而"關鍵字"表示一種查詢元件。
- 查詢： 的實際查詢元件之列參照。如果"主要"組件，這是整個查詢;如果組件 」 關鍵字"，您會看到其中一個查詢元件。
  - （透過未指定任何關鍵字） 中搜尋所有 contentin 信箱的實際查詢是 (大小 > = 0)，所以會傳回所有的項目
  - 當您搜尋 SharePoint Online 和 OneDrive 商務網站時，會新增兩個下列元件：
    - 不 IsExternalContent:1-從內部部署 SharePoint 組織排除任何內容
    - 不 isOneNotePage： 1-排除所有 OneNote 檔案因為這些是任何符合搜尋查詢的文件的重複項目。
- 位置鎖符合搜尋條件的項目數目
- 從下列位置符合搜尋條件的項目數
- 比對搜尋條件的項目總數 volumne。

## <a name="refiners"></a>精簡器
Exchange 信箱的精簡器檢視可讓您依 ItemClass、 寄件者和收件者的其他分類。針對每個精簡器及位置的值，您可以參閱文件數目所傳回的搜尋。