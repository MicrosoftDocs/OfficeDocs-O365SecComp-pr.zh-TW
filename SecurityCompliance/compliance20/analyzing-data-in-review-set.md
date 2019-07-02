---
title: 在高級 eDiscovery 中分析審閱集中的資料
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
ms.openlocfilehash: b331bba76f45a11a4d1c8c0552b27759cf49608a
ms.sourcegitcommit: e323610df2df71c84f536e8a38650d33d8069e41
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2019
ms.locfileid: "34703806"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a>在高級 eDiscovery 中分析審閱集中的資料

當收集的檔數很大時, 很難完全查看。 Advanced eDiscovery 提供許多工具來分析檔, 以減少不遺失資訊的檔數量, 並協助您以一致的方式組織檔。 若要深入瞭解這些功能, 請參閱:

- [近似重複項偵測](near-duplicates.md)

- [電子郵件執行緒](email-threading.md)

- [佈景主題](themes.md)

若要分析審閱集中的資料:

1. 設定您案例的分析設定。 如需詳細資訊, 請參閱[設定搜尋和分析設定](configure-search-analytics-settings.md)。

2. 開啟您要分析的檢查集。

3. 按一下 [**管理審閱集**]。

4. **針對 [審閱集**] 按一下 [執行分析]。

您可以在案例的 [**工作**] 索引標籤上檢查分析進度。

 分析完成之後, 您可以查看分析報告、在分析輸出的檢查集內執行查詢 (請參閱您的[審閱集中的查詢](review-set-search.md)), 並查看指定檔的相關檔 (請參閱檢查[審閱集中的資料](reviewing-data-in-review-set.md))。

## <a name="analytics-report"></a>分析報告

若要查看審查集的分析報告:

1. 開啟 [檢查集]。

2. 按一下 [**管理審閱集**]。

3. 按一下 [**查看報告**]。

報告中有四個元件可供分析:

- **細目**-在審閱集中找到的電子郵件、附件和鬆散檔數目。

- **檔 (不包括附件)** -大量的鬆散檔、樞紐分析表的重復資料, 或是其他檔的完全相同的複本。

- **電子**郵件-inclusives 的電子郵件數目、包含的副本、包含的 minuses, 或上述都不是。

- **附件**-審閱集中其他電子郵件附件的電子郵件附件數目是唯一或重複的。