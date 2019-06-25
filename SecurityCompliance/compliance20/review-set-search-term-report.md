---
title: 產生審閱集的搜尋字詞報告
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
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: 877c0017359ab9193c4cae81cbef4240909053a8
ms.sourcegitcommit: e323610df2df71c84f536e8a38650d33d8069e41
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2019
ms.locfileid: "34714992"
---
# <a name="generate-search-term-report-for-a-review-set"></a>產生審閱集的搜尋字詞報告

在 eDiscovery 中, 查詢檔最常使用的條件之一是使用關鍵字搜尋字詞。 透過識別包含特定關鍵字的檔 (也稱為*字詞*), 對案例而言很重要, 因此檢閱者可以開始深入瞭解其所面臨的情況。 在 Microsoft 365 的 [Advanced eDiscovery] 中, 您可以在檢查集內的儲存查詢上產生搜尋字詞報告, 以完成此項作業。

## <a name="step-1-create-a-saved-query-in-the-review-set"></a>步驟 1: 在考核集中建立已儲存的查詢

若要產生有意義的搜尋字詞報告, 請建立儲存的查詢, 以定義要產生搜尋字詞報告的審閱集中的一組檔。 例如, 您可以使用日期範圍或實際的搜尋字詞集合 (使用關鍵字條件卡片) 來建立查詢。 若要深入瞭解評審集查詢, 請參閱[查詢評審集中的資料](review-set-search.md)。

## <a name="step-2-generate-a-search-term-report"></a>步驟 2: 產生搜尋字詞報告

有兩種不同的方式可以產生搜尋字詞報告: 透過您在步驟1中建立的已儲存查詢的快顯功能表, 或透過搜尋字詞報告管理主控台。

- 若要使用快顯功能表, 請開啟您在步驟1中所建立之已儲存查詢的快顯功能表, 然後按一下 [**產生搜尋字詞報告**]。

- 若要使用管理主控台, 請移至 [**管理審閱集] > View search term reports**], 按一下 [**新增**], 然後選取您在步驟1中建立的已儲存查詢。

然後, 輸入您想要報告的字詞, 並以分行符號隔開;如果您在步驟1中建立的已儲存查詢使用關鍵字條件卡, 飛入頁面將會預先填入所儲存查詢中所使用的第一個關鍵字條件卡中的字詞。

然後, 選取最多三個樞軸進行報告, 然後按一下 [**產生**], 這會啟動搜尋字詞報告產生工作。

### <a name="what-is-a-pivot"></a>何謂資料透視？

「轉動」是如何組織報表。 請考慮下列範例。

- 已儲存的查詢會檢索10份檔: doc1 到 doc10。

- doc1、doc2、doc3、doc4、doc5、doc6 和 doc7 包含「eDiscovery」一詞。

- doc6、doc7、doc8、doc9 和 doc10 包含「調查」這一字。

- doc1、doc3、doc5、doc7、doc9 是來自保管人 A。

- doc2、doc4、doc6、doc8、doc10 是來自保管人 B。

在這種情況下, 如果您要在保管人上產生「eDiscovery」和「調查」的搜尋字詞報告, 並在保管人上進行資料透視, 則搜尋字詞報告的組織方式如下:

- 「eDiscovery」-保管人 A: 4 份檔

- 「eDiscovery」-管理員 B: 3 份檔

- 「調查」-管理員 A: 2 份檔

- 「調查」-管理員 B: 3 份檔

## <a name="step-3-download-report"></a>步驟 3: 下載報表

在搜尋字詞管理主控台中, 您可以追蹤先前建立之搜尋字詞報告工作的狀態。 工作完成後, 您可以按一下 [搜尋字詞] 報表的列, 然後按一下 [下載], 這會以 CSV 格式下載搜尋字詞報告。 每個專案會有一個資料列 (搜尋字詞、樞軸) 元組, 而每一列會包含下列資訊:

- 已檢索的檔數目為何？

- 搜尋字詞在整個檔中找到多少次？

- 檢索的檔總量是多少？

- 已檢索的族數目為何？

- 這些系列的總檔數目是多少, 包括沒有搜尋字詞的檔？

- 以上的總容量是多少？