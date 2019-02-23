---
title: 分析進階 eDiscovery (Preview) 中使用集中的資料
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
ms.openlocfilehash: ae024f423ac9b4ab9210ddfab519093a9fee3e42
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216793"
---
# <a name="analyze-data-in-a-working-set-in-advanced-ediscovery-preview"></a>分析進階 eDiscovery (Preview) 中使用集中的資料

大型收集文件數目時，它可以是很難將所有加以檢閱。進階的 eDiscovery （預覽） 提供工具來分析來降低文件檢閱沒有任何遺失的資訊，並協助您組織的文件一致的方式數量的文件的數。若要深入了解這些功能，請參閱：

- [近似重複項偵測](near-duplicates.md)
- [電子郵件威脅](email-threading.md)
- [佈景主題](themes.md)

若要分析使用集中的資料：

1. 設定分析您的案例。如需詳細資訊，請參閱 ＜ [Configure search 及分析設定](configure-search-analytics-settings.md)。
2. 開啟您想要分析的工作集。
3. 移至 「 管理工作集 」。
4. 按一下 ["分析"。

您可以在您的案例中檢查 [工作] 索引標籤中的分析的進度。

 分析完成之後，您可以檢視分析報表、 您使用內執行的查詢設定 （如需詳細資訊，請參閱[設定您的使用中查詢](working-set-search.md)） 分析的輸出並查看指定的文件 （如需詳細資訊，請參閱[相關的文件檢閱使用集中的資料](reviewing-data-in-working-set.md))。

## <a name="analytics-report"></a>分析報告

若要檢視您的工作集分析報告：

1. 開啟工作設定。
2. 移至 「 管理工作集 」。
3. 按一下 ["Report"。

報表有四種分析元件：

- 使用組中找不到**分解**-多少電子郵件、 附件及寬鬆的文件。

- **文件 （不含附件）** -多少寬鬆的文件已樞紐分析表、 唯一接近重複項目之樞紐分析表或另一個文件完全重複。

- **電子郵件**-多少電子郵件已 inclusives、 （含） 的複本、 （含) minuses，或上述任一個項目。

- **附件**-多少電子郵件附件中被唯一或重複內使用不同的電子郵件附件的設定。