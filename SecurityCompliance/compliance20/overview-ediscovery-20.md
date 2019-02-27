---
title: Microsoft 365 中的進階 eDiscovery （預覽） 的概觀
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
description: 本文說明 Microsoft 365 中的進階 eDiscovery （預覽） 的新版本。
ms.openlocfilehash: e2d89c2b8499c8818bececc4414182a6db689fb6
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30297016"
---
# <a name="overview-of-advanced-ediscovery-preview-in-microsoft-365"></a>Microsoft 365 中的進階 eDiscovery （預覽） 的概觀

Microsoft 剛已發行 Office 365 中的現有 eDiscovery 功能已更新的進階的 eDiscovery 工具的 preview 版本。這個預覽版本中，呼叫*進階的 eDiscovery （預覽）*，提供保留、 收集、 檢閱、 分析和匯出至您的組織內部和外部調查回應的內容端對端工作流程。 

## <a name="alignment-with-edrm"></a>使用 EDRM 的對齊方式

進階 eDiscovery （預覽） 的內建工作流程對齊 eDiscovery 程序所述來電子搜索參照模型 (EDRM)。 

![電子化搜索參照模型 (EDRM)](../media/EDRMv1.png)

（受 edrm.net 圖像來源。來源影像已供小小寫指南短片屬性 3.0 Unported 授權。）

在高的層級，以下方式進階 eDiscovery （預覽） 支援 EDRM 工作流程：

- **識別**-之後找出潛在的調查感興趣的人員，您可以將其新增為 custodians （也稱為*資料 custodians*，因為他們可能擁有與調查有關的資訊） 至進階eDiscovery （預覽） 案例。使用者會新增為 custodians 之後，很容易保留、 收集和檢閱 okay 文件。

- **保留**-保留並保護資料的相關調查、 進階的 eDiscovery （預覽） 可讓您將合法持有萬一 custodians 與相關聯之資料來源上。您也可以保留上放置非 custodial 資料。此外，進階的 eDiscovery （預覽） 具有內建的通訊工作流程，讓您可以將合法持有通知傳送給 custodians 並追蹤其認可。

- **集合**-您找出 （並保留） 與調查有關的資料來源之後，您可以使用進階的 eDiscovery （預覽） 搜尋及收集的即時資料中的內建搜尋工具，custodial 的資料來源 （和非 custodial資料來源而言，如果有的話） 可能是相關的大小寫。

- **處理**-已收集案例相關的所有資料之後下, 一步是程序的進一步檢閱和分析。進階的 ediscovery （預覽），這表示您 「 集合 」 階段中所識別的就地資料複製到 Azure 儲存位置 （稱為*工作集*），可提供讓您使用之靜態檢視的大小寫資料。 
 
- **檢閱**-資料已新增至工作之後，您可以檢視特定文件及執行其他查詢以  
 
- **分析**-進階 eDiscovery （預覽） 提供整合式的分析工具可協助您 cull 從您決定使用集中的資料不是與調查有關。除了以減少相關的資料量、 換頁 eDiscovery （預覽） 也可幫助您儲存 legal review 成本來可讓您組織內容以進行檢閱程序更容易且更有效率。

- **實際執行**和**簡報**-備妥之後，您可以將文件匯出為 legal review 工作組中。您可以將其原生格式或 EDRM 指定格式的文件匯出讓他們可以匯入協力廠商檢閱應用程式。

## <a name="advanced-ediscovery-preview-workflow"></a>進階的 eDiscovery （預覽） 工作流程

下列各節說明每個進階 eDiscovery (Preview) 中的內建工作流程中的步驟。下列螢幕擷取畫面顯示名為*產品責任 2019002*案例 [**首頁**] 索引標籤。請注意在頁面頂端的 [工作流程] 索引標籤的順序來對齊 EDRM 程序。 

如需進階的 eDiscovery (Preview) 中的端對端工作流程的詳細資訊，請參閱此[影片的 Microsoft 機制](https://go.microsoft.com/fwlink/?linkid=2066133)。 

![進階 eDiscovery (Preview) 中的索引標籤遵循 EDRM 工作流程](../media/aedisco-homepage-1.png)

## <a name="managing-custodians"></a>管理監管人

使用 [ **Custodians** ] 索引標籤新增及管理已識別為人員感興趣的大小寫的人員。新增 custodians 之後，您可以快速地執行 okay 相關動作等 okay 資料來源上放置合法的操作方法、 信箱等 OneDrive 帳戶與 custodians、 通訊及搜尋 okay 資料來源收集內容這是案例相關。做為案例的進度，很容易新增新 custodians 或釋出 custodians 從大小寫。如需詳細資訊，請參閱 ＜ [Work with custodians 進階 eDiscovery (Preview) 中](managing-custodians.md)。

## <a name="managing-legal-hold-notifications"></a>管理合法持有通知

使用 [**通訊**] 索引標籤來管理與大小寫的 custodians 通訊的程序。合法持有明會指示 custodians 来保留任何可能案例相關的內容。法律小組必須能夠追蹤的通知已收到、 讀取、 並認可 custodians。進階 eDiscovery (Preview) 中的通訊工作流程可讓您建立及傳送初始通知、 提醒、 版本通知和呈報如果 custodians 失敗確認保留通知。如需詳細資訊，請參閱 ＜ [Work with 進階 eDiscovery (Preview) 中的通訊](managing-custodian-communications.md)。

## <a name="managing-content-preservation"></a>管理內容保留

當您新增 okay 案例時，您必須保留置於 custodial 資料選項。使用 [**保留**] 索引標籤來管理建立當您新增 custodians 及管理其他法律保留保留與大小寫 ； 關聯例如，您可以找出並將保留在非 custodial 資料來源。您也可以編輯案例中的所有暫止並進行查詢式保留以便符合查詢的內容處於保留狀態 ；例如，您無法新增日期範圍至保留使僅包含的內容已建立於特定日期範圍中保留。您也可以取得統計資料的保留的內容、 移除之後當您不再案例相關的保留或予以刪除。如需詳細資訊，請參閱[管理保留進階 eDiscovery (Preview) 中](managing-holds.md)。

## <a name="indexing-custodian-data"></a>編製索引 okay 資料

新增案例 okay 與對應的 custodial 資料來源，okay 的資料來源的任何部分已編製索引項目會重新編製索引 （藉由呼叫*進階編製索引*的程序）。這允許 custodial 內容，例如圖像、 不支援的檔案類型及其他可能未編製索引的內容執行搜尋以收集案例相關的資料時要完全可供搜尋。使用 [**處理**] 索引標籤來監視進階編製索引和修正程式處理錯誤 （使用處理序 calle*錯誤補救*） 的狀態如需詳細資訊，請參閱[修正進階 eDiscovery (Preview) 中的處理錯誤](processing-data-for-case.md)。

## <a name="collecting-case-data"></a>收集案例資料

使用 [**搜尋**] 索引標籤來搜尋就地 custodial 搜尋及非 custodial 資料來源中建立 Office 365 案例相關的內容。您可建立並執行查詢為基礎的搜尋 （使用關鍵字和條件） 來識別設定電子郵件和文件相關大小寫與您想要進一步檢閱和分析中的 eDiscovery 工作流程中的後續步驟。您可以建立與案例相關聯的一或多個搜尋。此外，您可以使用搜尋工具預覽範例文件和檢視搜尋統計資料可以協助調整以及改善搜尋結果。一旦您正在滿足搜尋結果包含的所有資料案例相關、 將搜尋結果新增到工作組供進一步檢閱、 分析和必要的話，挑選。如需詳細資訊，請參閱[收集資料的進階 eDiscovery (Preview) 中的案例](collecting-data-for-ediscovery.md)。

## <a name="reviewing-and-analyzing-case-data"></a>檢閱和分析案例的資料

使用 [**處理設定**] 索引標籤或檢閱和分析您已從即時系統收集並新增至工作集的內容。*工作集*是靜態集合 （換言之，觀點離線複本） 的 custodial 資料 (如果適用的話，非 custodial 資料) 您收集在 eDiscovery 工作流程的上一個階段。搜尋結果新增至工作集之後，程序就會觸發檔案擷取容器、 擷取中繼資料，並會擷取文字。完成此程序時，系統會建立新索引的所有資料從 custodians 收集並新增至工作設定。一旦資料新增至工作集，您可以執行額外的查詢來縮小範圍的大小寫的資料、 做為文字或原生檔案格式檢視資料和加上註解、 redact、 和標籤文件中的工作設定。此外，您可以執行進階的分析例如識別文件重複、 電子郵件超執行緒，和佈景主題。一旦您已經下列只是案例相關的資料，可以直接下載下載文件或將它們匯出檔案的中繼資料、 註釋、 和任何標記。如需詳細資訊，請參閱：

  - [檢閱 case 進階 eDiscovery (Preview) 中的資料](reviewing-data-in-working-set.md)
  - [分析進階 eDiscovery (Preview) 中使用集中的資料](analyzing-data-in-working-set.md)

## <a name="exporting-data-for-review-and-presentation"></a>匯出資料的檢閱和簡報

將資料匯出從工作集之後，請使用 [**匯出**] 索引標籤來管理匯出工作並下載工作組中的資料。當您將匯出的工作集時，將資料上傳至 Azure 儲存位置，然後供下載至本機電腦。您可以取得位置和儲存評估需要下載 [**匯出**] 索引標籤上的匯出的資料的索引鍵。如需詳細資訊，請參閱 ＜ [case 進階 ediscovery (Preview) 資料匯出](exporting-data-ediscover20.md)。

## <a name="managing-jobs"></a>管理工作

使用 [**工作**] 索引標籤來監視長時間執行程序的案例相關之工作已起始、 做為重新編製索引的搜尋、 搜尋、 及匯出。例如，您可能會建立新的搜尋包含大量資料來源的 [**搜尋**] 索引標籤。在 [**工作**] 索引標籤上顯示此搜尋程序的狀態。如需詳細資訊，請參閱 ＜[進階 eDiscovery (Preview) 中的管理工作](managing-jobs-ediscovery20.md)。

## <a name="configuring-case-settings"></a>設定案例設定

使用 [**設定**] 索引標籤的設定整個大小寫的設定。這包括新增成員至大小寫、 關閉或刪除案例及設定搜尋與分析的行為。如需詳細資訊，請參閱 ＜[設定進階 eDiscovery (Preview) 中的案例設定](configuring-case-settings-ediscovery20.md)。

