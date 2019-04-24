---
title: Microsoft 365 進階 eDiscovery （預覽） 的概觀
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
description: 本文說明 Microsoft 365 進階 eDiscovery （預覽） 的新版本。
ms.openlocfilehash: 2296f4ee1867cacc90eada9e5f12888a8ea0d242
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32252467"
---
# <a name="overview-of-advanced-ediscovery-preview-in-microsoft-365"></a>Microsoft 365 進階 eDiscovery （預覽） 的概觀

Microsoft 已剛發行 Office 365 中現有的 eDiscovery 功能為基礎的更新進階電子文件探索工具的預覽版本。 此預覽版本中，名為*進階電子文件 （預覽）*，提供的端對端工作流程，以保留、 收集、 檢閱、 分析和匯出回應您的組織內部和外部調查的內容。 

## <a name="alignment-with-edrm"></a>使用 EDRM 的對齊方式

進階電子文件 （預覽） 的內建工作流程配合電子文件探索處理程序所述的電子搜索參照模型 (EDRM)。 

![電子探索參照模型 (EDRM)](../media/EDRMv1.png)

（受 edrm.net 影像來源。 來源影像進行下創意共用以 3.0 Unported 授權可用。）

在高的層級，以下方式進階電子文件 （預覽） 支援 EDRM 工作流程：

- **識別**-之後您識別潛在調查感興趣的人員，您可以將其新增為 custodians （也稱為*資料 custodians*，因為他們可能擁有與調查有關的資訊） 以進階eDiscovery （預覽） 案例。 使用者可新增為 custodians 之後，很容易保留、 收集和檢閱 custodian 文件。

- **保留**的保留和保護調查與相關資料的進階電子文件探索 （預覽） 可讓您保留法律案例中 custodians 相關聯的資料來源。 您也可以保留上放置非 custodial 資料。 此外，進階電子文件 （預覽） 具有內建的通訊工作流程，因此您可以將合法持有通知傳送給 custodians 和追蹤其認可。

- **集合**對您識別 （並保留） 與調查有關的資料來源之後，您可以使用進階電子文件 （預覽） 搜尋及收集的即時資料的內建的搜尋工具，從 custodial 資料來源 （和非 custodial資料來源，如果有的話），可能會與案件相關。

- **處理**-您收集了與案件相關的所有資料之後下, 一步是處理它進一步檢閱和分析。 在 [進階電子文件 （預覽），這表示您在 「 集合 」 階段中識別的就地資料複製到 Azure 儲存體位置 （稱為*工作集*），可提供讓您的案例資料之靜態檢視。 
 
- **檢閱**-資料已新增至工作之後，您可以檢視特定的文件，並執行額外的查詢，以減少資料與最相關的大小寫。 此外，您可以加上註解和標記特定文件。
 
- **分析**-進階電子文件探索 （預覽） 提供整合式的分析工具，可協助您進一步 cull 您決定的工作集的資料不與調查有關的。 除了減少相關的資料量，進階電子文件探索 （預覽） 也可協助您節省合法檢閱成本，可讓您組織要檢閱程序更簡單且更有效率的內容。

- **實際執行**和**簡報**-當您準備就緒之後，您可以從工作集合法檢閱匯出文件。 您可以匯出以其原生格式或 EDRM 指定格式的文件，讓他們可以匯入協力廠商檢閱應用程式。

## <a name="advanced-ediscovery-preview-workflow"></a>進階電子文件 （預覽） 的工作流程

下列各節說明每個進階電子文件 （預覽） 中的內建工作流程中的步驟。 下列螢幕擷取畫面顯示名為*產品責任 2019002*案例 [**首頁**] 索引標籤。 請注意在頁面頂端的 [工作流程] 索引標籤的順序來對齊 EDRM 程序。 

如需進階電子文件 （預覽） 中的端對端工作流程的詳細資訊，請參閱此[影片的 Microsoft 機制](https://go.microsoft.com/fwlink/?linkid=2066133)。 

![在 [進階電子文件 （預覽） 的定位點遵循 EDRM 工作流程](../media/aedisco-homepage-1.png)

## <a name="managing-custodians"></a>管理 custodians

使用 [ **Custodians** ] 索引標籤來新增和管理您已識別為人員案例感興趣的人員。 當您新增 custodians 時，您可以快速地執行 custodian 相關的動作，例如置於 custodian 資料來源，例如他們的信箱和 OneDrive 帳戶中的合法持有、 與 custodians、 通訊及搜尋 custodian 資料來源收集內容這是與案件相關。 大小寫的進度，很容易新增新 custodians 或釋出 custodians 從案例。 如需詳細資訊，請參閱 < <b0>Work with custodians 進階電子文件 （預覽） 中</b0>。

## <a name="managing-legal-hold-notifications"></a>管理合法持有通知

使用 [**通訊**] 索引標籤來管理的情況下 custodians 與通訊的程序。 合法持有通知會指示 custodians 來保留可能與案件相關的任何內容。 法律小組必須能夠追蹤，通知已收到、 讀取、 並由 custodians 認可。 進階電子文件 （預覽） 中的通訊工作流程可讓您建立和傳送初始通知、 提醒、 發行通知和呈報 custodians 無法認可保留通知。 如需詳細資訊，請參閱 <<c0>使用進階電子文件 （預覽） 中的通訊。

## <a name="managing-content-preservation"></a>管理內容保留

當您新增 custodian 案例時，您必須保留 custodial 資料的選項。 使用 [**保留**] 索引標籤來管理保留建立當您新增 custodians，以及如何管理與案例相關聯的額外合法持有 （例如，您可以找出並保留非 custodial 資料來源）。 您也可以編輯任何保留的情況下，並讓查詢式保留符合查詢的內容會置於保留。 例如，您可以新增至保留的日期範圍，讓特定日期中建立的內容遠距中保留。 您也可以保留的內容取得統計資料、 之後不再是相關的情況下，移除保留或刪除它。 如需詳細資訊，請參閱 <<c0>管理保留在 [進階電子文件 (Preview)>。

## <a name="indexing-custodian-data"></a>Custodian 資料編製索引

當您新增 custodian 與對應的 custodial 資料來源的情況下時，從 custodian 資料來源的任何已局部編製索引項目是重新編製索引 （藉由呼叫*進階編製索引*的程序）。 這可讓 custodial 的內容，例如影像、 不支援的檔案類型，以及其他可能未編製索引內容是完全可搜尋，當您執行搜尋來收集資料的情況。 使用 [**處理**] 索引標籤來監視狀態的進階編製索引和修正處理錯誤 （使用稱為*錯誤修復*程序）。如需詳細資訊，請參閱[修正進階電子文件 （預覽） 中的處理錯誤](processing-data-for-case.md)。

## <a name="collecting-case-data"></a>收集案例資料

使用 [**搜尋**] 索引標籤建立搜尋來搜尋 Office 365 中的就地 custodial 和非 custodial 資料來源與案件相關的內容。 您可以建立及執行查詢為基礎的搜尋 （使用關鍵字和條件），以找出電子郵件和文件，與案件相關且想要進一步檢閱和分析中的 eDiscovery 工作流程的後續步驟中的一組。 您可以建立與案例相關聯的一個或多個搜尋。 此外，您可以使用 「 搜尋 」 工具來預覽範例文件和檢視搜尋統計資料可協助您改善，並改善搜尋結果。 一旦您正在符合搜尋結果包含與案件相關的所有資料，您將搜尋結果新增至工作集，供進一步檢閱，分析和如有必要，挑選。 如需詳細資訊，請參閱[收集資料的進階電子文件 （預覽） 中的案例](collecting-data-for-ediscovery.md)。

## <a name="reviewing-and-analyzing-case-data"></a>檢閱和分析案例資料

用於檢閱和分析已從 live 系統收集並新增至工作集之內容的**工作集**] 索引標籤。 *工作集*是靜態 custodial 資料的資料 （換言之，資料離線複本） 的集合 (如果適用的話，非 custodial 資料)，您收集在前一個階段中的 eDiscovery 工作流程。 當您將搜尋結果新增至工作集時，就會觸發程序，將檔案解壓縮來自容器、 擷取中繼資料，並擷取文字。 完成此程序時，系統會建立新的索引的所有資料係收集自 custodians 並新增至工作集。 資料會新增至工作集之後，您可以執行其他查詢以縮小案例的資料、 檢視資料，做為文字或原生檔案格式，並加上註解、 redact，並標記文件中的工作設定。 此外，您可以執行進階的分析，例如識別文件重複、 電子郵件執行緒，和佈景主題。 您已下列只會與案件相關的資料之後，您可以直接下載文件或將它們匯出以及檔案中繼資料、 註釋和任何標記。 如需詳細資訊，請參閱：

  - [檢閱在 [進階電子文件 （預覽） 的案例資料](reviewing-data-in-working-set.md)
  - [在進階電子文件 （預覽） 中的工作集合中分析資料](analyzing-data-in-working-set.md)

## <a name="exporting-data-for-review-and-presentation"></a>匯出資料，經過審閱和簡報

從工作集匯出資料之後，使用 [**匯出**] 索引標籤來管理匯出工作並下載資料從工作集。 當您匯出工作集時，資料上傳至 Azure 儲存體位置，則可被下載到本機電腦上。 您可以取得位置，並儲存評估需要下載匯出的資料，在 [**匯出**] 索引標籤上的索引鍵。如需詳細資訊，請參閱[匯出案例資料在進階電子文件 （預覽）](exporting-data-ediscover20.md)。

## <a name="managing-jobs"></a>管理工作

使用 [**工作**] 索引標籤來監視案例相關的工作，您已初始化的長時間執行程序。 工作的範例包括有關重新編製索引、 搜尋和匯出。 例如，您可能包含大量資料來源的 [**搜尋**] 索引標籤上建立新的搜尋。 此搜尋程序的狀態會顯示在 [<b0>工作</b0>] 索引標籤上。如需詳細資訊，請參閱 <<c1>進階電子文件 （預覽） 中的管理工作。

## <a name="configuring-case-settings"></a>設定的區分大小設定

使用 [**設定**] 索引標籤設定整個案例的設定。 這包括將成員新增至的情況下，關閉或刪除情況下，並設定搜尋並分析的行為。 如需詳細資訊，請參閱 <<c0>設定進階電子文件 （預覽） 中的案例設定。
