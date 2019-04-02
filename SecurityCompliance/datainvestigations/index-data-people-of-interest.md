---
title: 進階編製索引的調查資料
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
ms.openlocfilehash: 9537cf743b89da7167ce3a37a5915027f4eb717a
ms.sourcegitcommit: 2c5834235c32b2616e1813ce24eeb3419a09629f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2019
ms.locfileid: "31030006"
---
# <a name="advanced-indexing-of-data-for-an-investigation"></a>進階編製索引的調查資料

Live 系統中的內容可以將多個原因包括影像、 不支援的檔案類型或時遇到索引檔案大小限制存在已部分編制索引。 當您正在處理的資料不要大高風險時，想要確定您的搜尋擷取您想要調查的所有資料。 感興趣的人員新增至資料調查後，已被視為的 Office 365 中的所有內容已局部編製索引都時，使其成為完整搜尋重新處理。 此程序稱為 「*進階編製索引*」。 

若要深入了解關於處理 Office 365 和已局部編製索引的項目中支援的詳細資訊，請參閱：

- [在 [資料調查支援的檔案類型](supported-filetypes-datainvestigations.md)

- [位於 Office 365 中內容搜尋的已局部編製索引項目](https://docs.microsoft.com/en-us/office365/securitycompliance/partially-indexed-items-in-content-search)

- [Exchange 搜尋編製索引的檔案格式](https://docs.microsoft.com/en-us/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [SharePoint Server 中預設編目的檔案副檔名及剖析的檔案類型](https://docs.microsoft.com/en-us/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>檢視進階索引的結果

進階的索引程序完成之後，您可以取得的重新處理效率了解。  在檢視編製索引的感興趣的人員，圖形會列出所有的項目新增至*混合式索引*。  混合式 index 是資料調查 （預覽） 重新處理的內容，儲存位置。

此圖形也包含需要修復的項目數與另一個圖形的檔案類型的錯誤。 如需詳細資訊，請參閱 <<c0>錯誤修復時處理資料。

## <a name="updating-advanced-indexes-for-people-of-interest"></a>更新進階的索引感興趣的人員

當感興趣的人員新增至資料調查後時，所有已局部編製索引的項目會重新處理。 不過，經過一段時間，更局部編製索引的項目可能會新增至使用者的信箱或 OneDrive 帳戶。  視需要，您可以更新索引。

> [!NOTE]
> 更新人員感興趣的索引是一個長時間執行的程序。 最好不要更新索引中調查每天的一次以上。
