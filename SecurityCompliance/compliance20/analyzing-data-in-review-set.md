---
title: 在進階電子文件探索中設定檢閱中分析資料
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
ms.openlocfilehash: c765234e1aa0738415f66f90b66ebce0fcab2505
ms.sourcegitcommit: 4ce350f8f3eb597587945a8ac9b33e9793440c64
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/01/2019
ms.locfileid: "33527129"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a>在進階電子文件探索中設定檢閱中分析資料

大型收集文件數目時，它可以是很難全部加以檢閱。 進階電子文件提供數個工具來分析文件，以減少大量的文件沒有任何遺失的資訊，請檢閱，以及協助您組織的文件中以一致的方式。 若要深入了解這些功能，請參閱：

- [近似重複項偵測](near-duplicates.md)

- [電子郵件執行緒](email-threading.md)

- [佈景主題](themes.md)

若要分析檢閱集中的資料：

1. 設定分析您的案例。 如需詳細資訊，請參閱 < <b0>Configure search 和分析設定</b0>。

2. 開啟您想要分析檢閱設定。

3. 按一下 [**管理檢視設定**]。

4. 按一下 [**分析**]。

您可以檢查 analysis 案例的**工作**] 索引標籤上的進度。

 分析完成之後，您可以檢視分析報表中，執行查詢中分析的輸出上您檢閱設定 （請參閱[設定內檢閱查詢](review-set-search.md)），並查看相關的文件的指定的文件 （請參閱[檢閱資料中的檢閱設定](reviewing-data-in-review-set.md)）。

## <a name="analytics-report"></a>分析報告

若要檢視檢閱設定分析報告：

1. 開啟 [檢閱設定]。

2. 按一下 [**管理檢視設定**]。

3. 按一下 [**報告**]。

報表中包含從分析的四個元件：

- 檢閱集合中找不到**分解**-多少電子郵件訊息、 附件及寬鬆的文件。

- **文件 （不含附件）** -多少寬鬆的文件已樞紐分析表，唯一接近重複的樞紐分析表或完全重複的另一個文件。

- **電子郵件**-多少電子郵件訊息所 inclusives、 內含的副本，內含 minuses，或無以上。

- **附件**-多少電子郵件附件是唯一或重複的另一個電子郵件附件中檢閱設定。