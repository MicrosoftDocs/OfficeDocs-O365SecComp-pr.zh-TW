---
title: 執行分析以更快速地調查
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
ms.openlocfilehash: 7462b415c2e5b0a66c08bb9b5abb647f366e9785
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153655"
---
# <a name="run-analytics-to-investigate-faster"></a>執行分析以更快速地調查

大型辨識項集合時，它可能很難全部加以檢閱。 一群證據通常包含相同或類似的電子郵件或文件的多個副本。 資料調查 （預覽） 提供了數分析工具，可協助您降低需要檢閱沒有任何遺失的資訊中的文件數量。 若要深入了解這些功能，請參閱：

- [近似重複項偵測](near-duplicates.md)

- [電子郵件執行緒](email-threading.md)

- [佈景主題](themes.md)

若要分析辨識項集合中的資料：

1. 設定您調查分析。 如需詳細資訊，請參閱 < <b0>Configure search 和分析設定</b0>。

2. 開啟辨識項集合。

3. 按一下 [**管理證據**。

4. [**分析**，按一下 [**分析]**。

您可以在您調查檢查分析**工作**] 索引標籤上的進度。 觸發工作類型是名為**執行分析**。

 分析完成之後，您可以查看完全重複或近似重複項目在檢閱文件位於右側的 [資訊] 面板。 若要選取您要檢視文件的所有重複項目，您可以輕鬆地執行使用此面板。 若要深入了解此面板上的其他功能，請參閱 <<c0>在辨識項的檢閱資料。 

您也可以執行額外的查詢中使用的佈景主題例如分析輸出您證據。 如需詳細資訊，請參閱 <<c0>查詢中的辨識項的資料。

## <a name="analytics-report"></a>分析報告

若要檢視您的辨識項分析報告：

1. 開啟辨識項集合。

2. 按一下 [**管理證據**。

3. [**分析**，按一下 [**檢視報告**。

報表中包含從分析的四個元件：

- **分解**-的未經處理的電子郵件、 附件，並找到辨識項集合中的文件數。

- **電子郵件**-eamil inclusives、 內含 minuses、 內含的副本，或沒有任何一個以上的郵件數目。
   - Inclusives： 最後一封電子郵件執行緒，包含所有舊的歷程記錄，而且需要檢閱中。
   - 內含 minuses： 需要檢閱的訊息中的執行緒，其中包含一或多不同的附件。
   - 內含的副本： 是另一個 （含） 或減號 （主旨和內文） 的訊息內含的複本的訊息。

- **附件**-都是唯一的電子郵件附件數] 或 [重複項目中相同的不同的電子郵件附件的證據相同。

- **文件 （不含電子郵件附件）** -唯一需要檢閱，例如近似重複組最代表性文件或完全重複的另一個文件的文件數目）。