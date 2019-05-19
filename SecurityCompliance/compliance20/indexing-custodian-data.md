---
title: 進階的監管人資料索引
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
ms.openlocfilehash: be163d3272dbe027cb0f4b4b4fe379bf28fa5a85
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151755"
---
# <a name="advanced-indexing-of-custodian-data"></a>進階的監管人資料索引

Custodian 會新增至進階電子文件探索案例中，已被視為的 Office 365 中的所有內容已局部編製索引都時，使其成為完整搜尋重新處理。  此程序稱為 「*進階編製索引*」。 內容可以是已局部編製索引數量的原因包括影像、 不支援的檔案類型或時遇到索引檔案大小限制存在。

若要深入了解關於處理 Office 365 和已局部編製索引的項目中支援的詳細資訊，請參閱：

- [在進階電子文件中支援的檔案類型](supported-filetypes-ediscovery20.md)
- [位於 Office 365 中內容搜尋的已局部編製索引項目](https://docs.microsoft.com/en-us/office365/securitycompliance/partially-indexed-items-in-content-search)
- [Exchange 搜尋編製索引的檔案格式](https://docs.microsoft.com/en-us/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)
- [SharePoint Server 中預設編目的檔案副檔名及剖析的檔案類型](https://docs.microsoft.com/en-us/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>檢視進階索引的結果

進階的索引程序完成之後，您可以取得的重新處理效率了解。  在 Custodian 編製索引] 檢視中，此圖形會列出所有的項目新增至*混合式索引*。  混合式索引是進階電子文件重新處理的內容，儲存位置。

此圖形也包含需要修復的項目數與另一個圖形的檔案類型的錯誤。 如需詳細資訊，請參閱 <<c0>錯誤修復時處理資料。

## <a name="updating-advanced-indexes-for-custodians"></a>更新 custodians 進階的索引

當 custodian 加入至進階電子文件探索案例時，所有已局部編製索引的項目會重新處理。 不過，經過一段時間，更局部編製索引的項目可能會新增至使用者的信箱或 OneDrive 帳戶。  視需要，您可以更新索引。

> [!NOTE]
> 更新 custodian 索引是一個長時間執行的程序。 最好不要更新索引每天案例中的一次以上。
