---
title: 在進階電子文件 （預覽） 中的工作集合中分析資料
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
ms.openlocfilehash: e3f3e863423fe4312a944eb6f04a58182e11665c
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32243234"
---
# <a name="analyze-data-in-a-working-set-in-advanced-ediscovery-preview"></a>在進階電子文件 （預覽） 中的工作集合中分析資料

大型收集文件數目時，它可以是很難全部加以檢閱。 進階電子文件 （預覽） 提供的工具來分析文件，以減少大量的文件沒有任何遺失的資訊，請檢閱，以及協助您組織的文件中以一致的方式的數字。 若要深入了解這些功能，請參閱：

- [近似重複項偵測](near-duplicates.md)
- [電子郵件威脅](email-threading.md)
- [佈景主題](themes.md)

若要分析工作集合中的資料：

1. 設定分析您的案例。 如需詳細資訊，請參閱 < <b0>Configure search 和分析設定</b0>。
2. 開啟您想要分析的工作集。
3. 移至 「 管理工作集 」。
4. 按一下 「 分析 」。

您可以在您的案例中檢查 [工作] 索引標籤中分析的進度。

 分析完成之後，您可以檢視分析報表中，執行的查詢，在您工作 （如需詳細資訊，請參閱[設定您的工作中查詢](working-set-search.md)） 分析的輸出上設定，請參閱相關的文件的指定的文件 （如需詳細資訊，請參閱[檢閱工作集合中的資料](reviewing-data-in-working-set.md))。

## <a name="analytics-report"></a>分析報告

若要檢視您的工作集分析報告：

1. 開啟您的工作集。
2. 移至 「 管理工作集 」。
3. 按一下 「 報告 」。

報表中包含從分析的四個元件：

- **分解**-多少電子郵件、 附件及寬鬆的文件中的工作集找不到。

- **文件 （不含附件）** -多少寬鬆的文件已樞紐分析表，唯一接近重複的樞紐分析表或完全重複的另一個文件。

- **電子郵件**-多少電子郵件已 inclusives、 內含的副本，內含 minuses，或無以上。

- **附件**-多少電子郵件附件是唯一或重複的工作集內的不同的電子郵件附件。