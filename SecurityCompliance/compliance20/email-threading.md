---
title: 電子郵件威脅
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
ms.openlocfilehash: a3c4f940c34a9c51bf58107d10e04d0ed60f28a8
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213423"
---
# <a name="email-threading"></a>電子郵件威脅

請考慮有一段移的電子郵件交談。在大多數的情況下的執行緒上的最後一個電子郵件將會包含所有上述的電子郵件 ； 的內容檢閱的最後一個電子郵件會授與交談執行緒中發生的完整內容。電子郵件超執行緒會識別這類電子郵件，讓檢閱者可以檢閱收集文件的分數沒有遺失任何內容。

## <a name="what-does-email-threading-do"></a>電子郵件執行緒做什麼？

每個電子郵件和 desconstructs 電子郵件超執行緒會剖析其個別郵件;每個電子郵件是個別郵件的鏈結。然後，它分析判斷電子郵件是否有唯一內容或如果鏈結完全包含在不同的電子郵件工作集內的所有電子郵件。在結尾處電子郵件會分成四個類別：

- **Inclusive**： 電子郵件中的最後一個郵件具有唯一的內容，且電子郵件的所有其他的內容完全包含在此電子郵件的電子郵件中所包含的附件。


- **減去 Inclusive**： 電子郵件中的最後一個郵件具有唯一的內容，但是電子郵件不包含一些其他的內容完全包含在此電子郵件的電子郵件中所包含的附件。

- **（含） 的複本**： 完全複本 （含）/（含） 減去電子郵件

- **無**： 此電子郵件的內容完全包含至少一個電子郵件中的標示為 （含）/（含） 減號。

## <a name="how-is-it-different-from-conversations-in-outlook"></a>如何是否與 Outlook 中交談不同？
一眼這聲音非常類似於 Outlook 中的交談群組。但是，有一些重要差異。請考慮將兩個交談; got 分叉電子郵件交談例如，某人回應 「 讓交談中的最後兩個電子郵件兩者都有唯一的內容不交談中的最新的電子郵件。

Outlook 仍會群組在單一對話 ； 將電子郵件讀取的最後一個電子郵件會平均遺失也包含唯一內容倒數第二個電子郵件的內容。因為電子郵件超執行緒會剖析取出每個電子郵件到個別元件並比較它們、 電子郵件超執行緒會標示這兩個最後兩個電子郵件 inclusives，確保將不會漏接任何內容只要您閱讀所有電子郵件標示為 （含）。