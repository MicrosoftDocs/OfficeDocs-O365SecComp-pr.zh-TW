---
title: 進階的監管人資料索引
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
ms.openlocfilehash: 1521aadca42c8119ae341065865b227fb16ffcf3
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295026"
---
# <a name="advanced-indexing-of-custodian-data"></a>進階的監管人資料索引

當 okay 加入至進階的 eDiscovery （預覽） 案例時，已被視為的 Office 365 中的任何內容部分編製索引是以提供完整搜尋重新處理。 此程序會呼叫*進階編製索引*。內容可以是部分編製索引的原因包括存在圖像、 不受支援的檔案類型或索引檔案大小限制時所發生的數量。

若要深入了解處理 Office 365 及部分已編製索引的項目中的支援，請參閱：

- [進階在 eDiscovery 中支援的檔案類型](supported-filetypes-ediscovery20.md)
- [位於 Office 365 中內容搜尋的已局部編製索引項目](https://docs.microsoft.com/en-us/office365/securitycompliance/partially-indexed-items-in-content-search)
- [Exchange 搜尋編製索引的檔案格式](https://docs.microsoft.com/en-us/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)
- [SharePoint Server 中預設編目的檔案副檔名及剖析的檔案類型](https://docs.microsoft.com/en-us/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>檢視進階索引的結果

進階索引程序完成後，您可以取得效益的重新處理的知識。 在 Okay 編製索引] 檢視中此圖形會列出所有的項目新增至*混合索引*。 混合式索引為進階的 eDiscovery （預覽） 儲存重新處理的內容的位置。

此圖形也包含要求修復的項目數與另一個圖形的檔案類型的錯誤。如需詳細資訊，請參閱[錯誤補救時處理資料](error-remediation.md)。

## <a name="updating-advanced-indexes-for-custodians"></a>更新 custodians 進階的索引

當 okay 加入至進階的 eDiscovery （預覽） 案例時，部分已編製索引的所有項目會重新處理。不過，經過一段時間，更多部分已編製索引的項目可能會新增至使用者的信箱或 OneDrive 帳戶。 當需要，您可以更新索引。

> [!NOTE]
> 更新 okay 索引為長時間執行的程序。建議不要更新索引萬一每天的一次以上。
