---
title: Microsoft 365 中的高級 eDiscovery 解決方案概述
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
description: 本文說明 Microsoft 365 中的新版本的高級 eDiscovery。
ms.openlocfilehash: 44bbc871295cb6b621ed6ee286c8dcd2c1cc1716
ms.sourcegitcommit: ecc823c2a4f1465114cf1d3a4630e31c47779ddc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2019
ms.locfileid: "35079387"
---
# <a name="overview-of-the-advanced-ediscovery-solution-in-microsoft-365"></a>Microsoft 365 中的高級 eDiscovery 解決方案概述

Microsoft 365 中的高級 eDiscovery 解決方案是在 Office 365 中現有的 eDiscovery 和分析功能所建立。 這個新的解決方案稱為「*高級 eDiscovery*」, 可提供端對端工作流程, 以保留、收集、審閱、分析及匯出回應貴組織內部和外部調查的內容。 它也可讓法律團隊管理整個合法持有通知工作流程, 以與案例中的保管人進行通訊。 

## <a name="alignment-with-edrm"></a>與 EDRM 對齊

高級 eDiscovery 的內建工作流程會與電子探索參考模型 (EDRM) 所概述的 eDiscovery 程式一致。 

![電子探索參考模型 (EDRM)](../media/EDRMv1.png)

(圖像來源 edrm.net。 來源映射可在創造性 Commons 歸屬 3.0 Unported 授權下取得。)

在較高的層次, 以下是高級 eDiscovery 支援 EDRM 工作流程的方式:

- **識別**–在您識別調查中可能感興趣的人員之後, 您可以將其新增為保管人 (也稱為「*資料保管人*」, 因為它們可能會擁有與調查相關的資訊) 至 [高級]eDiscovery 案例。 將使用者新增為保管人後, 就很容易保留、收集並審查保管人檔。

- **保留**–若要保留和保護與調查相關的資料, 高級 eDiscovery 可讓您在案例中對保管人相關聯的資料來源進行合法保留。 您也可以將非 custodial 資料保留。 高級 eDiscovery 也有內建的通訊工作流程, 因此您可以傳送合法的保留通知給保管人, 並追蹤其確認。

- **集合**–在您識別 (並保留) 與調查相關的資料來源之後, 您可以在高級 eDiscovery 搜尋中使用內建搜尋工具, 並從 custodial 資料來源 (和非 custodial 資料來源) 中收集即時資料。如果適用), 可能會與案例相關。

- **處理**–在您收集所有與案例相關的資料之後, 下一步是處理它, 以進一步審查和分析。 在 [Advanced eDiscovery] 中, 您在集合階段中所識別的就地資料會複製到 Azure 儲存位置 (稱為「*審閱集*」), 以提供事例資料的靜態視圖。 
 
- **考核**–將資料新增至審閱集之後, 您可以查看特定檔並執行另一個查詢, 以將資料縮減為與案例最相關的資料。 此外, 也可以為特定檔加上批註和標記。
 
- **分析**–高級 eDiscovery 提供整合式分析工具, 可協助您進一步從您判斷出的檢查集合中挑選資料, 而不與調查相關。 除了減少相關資料的數量之外, 提前 eDiscovery 也可協助您組織內容, 讓審查程式更簡單且更有效率, 以協助您儲存法律考評成本。

- **實際**執行和**簡報**–當您準備好時, 您可以從審查集中匯出檔, 以進行法律考評。 您可以以原生格式或以 EDRM 指定的格式匯出檔, 以便匯入協力廠商的審閱應用程式。

## <a name="advanced-ediscovery-workflow"></a>高級 eDiscovery 工作流程

下列各節說明在高級 eDiscovery 中內建工作流程的每個步驟。 下列螢幕擷取畫面顯示名為「*產品責任 2019002*」之案例的 [**首頁**] 索引標籤。 請注意, 頁面頂端的 [工作流程] 索引標籤會順序排列, 以符合 EDRM 程式。 

如需高級 eDiscovery 中端對端工作流程的詳細資訊, 請參閱這個[Microsoft 機械的影片](https://go.microsoft.com/fwlink/?linkid=2066133)。 

![高級 eDiscovery 中的索引標籤遵循 EDRM 工作流程](../media/aedisco-homepage-1.png)

## <a name="managing-custodians"></a>管理保管人

使用 [**保管人**] 索引標籤來新增和管理您在案例中識別為感興趣人員的人員。 當您新增保管人時, 您可以快速執行保管人相關的動作, 例如對保管人資料來源進行合法保留、與保管人進行通訊, 以及搜尋保管人資料來源, 以收集與案例相關的內容。 隨著案例的進展, 您可以輕鬆地從案例中新增保管人或版本的保管人。 如需詳細資訊, 請參閱[在高級 eDiscovery 中使用保管人](managing-custodians.md)。

## <a name="managing-legal-hold-notifications"></a>管理法律保留通知

使用 [**通訊**] 索引標籤, 在案例中管理與保管人進行通訊的處理常式。 法律保留通知會指示保管人保留與案例相關的任何內容。 法律小組必須能夠追蹤由保管人所接收、閱讀和認可的通知。 當保管人無法認可保留通知時, 可讓您建立和傳送初始通知、提醒、發行通知和升級的通訊工作流程。 如需詳細資訊, 請參閱使用[高級 eDiscovery 中的通訊](managing-custodian-communications.md)。

## <a name="managing-content-preservation"></a>管理內容保留

當您將系統管理員新增至案例時, 您可以保留 custodial 資料。 使用 [**保留**] 索引標籤來管理當您新增保管人時所建立的保留, 以及管理與案例相關的其他法律保留;例如, 您可以在非 custodial 的資料來源上識別並放置保留。 您也可以在案例中編輯任何保留, 並讓其成為查詢式保留, 以保留符合查詢的內容。 例如, 您可以將日期範圍新增至保留, 僅保留在特定日期範圍內建立的內容。 您也可以取得待保留內容的統計資料, 並在其不再與案例相關的情況下移除保留, 或將它刪除。 如需詳細資訊, 請參閱[Advanced eDiscovery 中的管理保留](managing-holds.md)。

## <a name="indexing-custodian-data"></a>索引保管人資料

當您將保管人和對應的 custodial 資料來源新增至案例時, 系統會由名為*Advanced*indexed 的程式, 重新編制保管人資料來源中任何已編制索引的專案的索引。 這可讓 custodial 內容 (例如影像、不支援的檔案類型, 以及其他可能未編制索引的內容可在您執行搜尋來收集資料時, 完全可供搜尋)。 使用 [**處理**] 索引標籤來監視高級索引的狀態, 並使用稱為「*錯誤修正*」的程式修正處理錯誤。 如需詳細資訊, 請參閱[在高級 eDiscovery 中修正處理錯誤](processing-data-for-case.md)。

## <a name="collecting-case-data"></a>收集案例資料

使用 [**搜尋**] 索引標籤來建立搜尋, 以搜尋 Office 365 中的就地 custodial 和非 custodial 資料來源, 以取得與案例相關的內容。 您可以建立及執行查詢式搜尋 (使用關鍵字和條件) 來識別與案例相關的一組電子郵件訊息和檔, 以及您想要在 eDiscovery 工作流程的後續步驟中進一步查看和分析。 您可以建立一或多個與案例相關聯的搜尋。 您也可以使用搜尋工具來預覽範例檔, 並查看搜尋統計資料, 以協助您精煉和改善搜尋結果。 當您滿意搜尋結果時, 會包含與案例相關的所有資料, 並將搜尋結果新增至審閱集, 以進一步審閱、分析及剔除。 如需詳細資訊, 請參閱[在高級 eDiscovery 中收集案例的資料](collecting-data-for-ediscovery.md)。

## <a name="reviewing-and-analyzing-case-data"></a>審閱和分析案例資料

使用 [**審閱集**] 索引標籤可查看和分析您從即時系統收集到的內容, 並新增至審閱集。 *檢查集*是 custodial 資料 (也就是資料的離線副本) 的靜態集合, 這些資料是您在 eDiscovery 工作流程的上一階段收集的資料 (以及適用的非 custodial 資料)。 當您將搜尋結果新增至審閱集時, 會觸發從容器提取檔案、提取中繼資料及解壓縮文字的程式。 此程式完成時, 系統會為從保管人收集的所有資料建立新的索引, 並將其新增至審閱集。 將資料新增至審閱集之後, 您可以執行更多的查詢來縮小事例資料、以文字或原生檔案格式來查看資料, 以及在審閱集中批註、標記密文和標記檔。 您也可以執行高級分析, 例如識別檔案複製、電子郵件執行緒和主題。 將資料 culled 至與案例相關的內容之後, 您可以直接下載檔案, 或將它們連同檔案中繼資料、批註及任何標記一起匯出。 如需詳細資訊，請參閱：

 –[瞭解高級 ediscovery 中的案例資料](reviewing-data-in-review-set.md)–在[高級 ediscovery 中分析審閱集中的資料](analyzing-data-in-review-set.md)

## <a name="exporting-data-for-review-and-presentation"></a>匯出資料以供審閱和簡報

從審查集匯出資料之後, 請使用 [**匯出**] 索引標籤來管理匯出工作, 並從審閱集中下載資料。 當您匯出審閱集時, 會將資料上傳至 Azure 儲存位置, 然後即可下載到本機電腦。 您可以在 [**匯出**] 索引標籤上, 取得下載匯出資料所需的儲存評估金鑰。如需詳細資訊, 請參閱[在高級 eDiscovery 中匯出案例資料](exporting-data-ediscover20.md)。

## <a name="managing-jobs"></a>管理工作

使用 [**工作**] 索引標籤來監視已啟動之案例相關工作的長時間執行程式。 工作的範例包括與重建索引、搜尋及匯出案例資料相關的範例。 例如, 如果您在包含許多資料來源的 [**搜尋**] 索引標籤上建立搜尋, 就會在 [**工作**] 索引標籤上顯示此搜尋程式的狀態。如需詳細資訊, 請參閱[管理高級 eDiscovery 中的工作](managing-jobs-ediscovery20.md)。

## <a name="configuring-case-settings"></a>設定案例設定

使用 [**設定**] 索引標籤來設定全案例設定。 這包括將成員新增至案例、關閉或刪除案例, 以及設定搜尋和分析設定。 如需詳細資訊, 請參閱[在高級 eDiscovery 中設定案例設定](configuring-case-settings-ediscovery20.md)。
