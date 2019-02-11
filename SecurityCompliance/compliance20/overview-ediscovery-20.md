---
title: Microsoft 365 中的進階 eDiscovery （預覽） 的概觀
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 本文說明 Microsoft 365 中的進階 eDiscovery （預覽） 的新版本。
ms.openlocfilehash: cb82541037983ca21cefbefb7f72fffa3b054373
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2019
ms.locfileid: "29706154"
---
# <a name="overview-of-advanced-ediscovery-preview-in-microsoft-365"></a><span data-ttu-id="9db1c-103">Microsoft 365 中的進階 eDiscovery （預覽） 的概觀</span><span class="sxs-lookup"><span data-stu-id="9db1c-103">Overview of Advanced eDiscovery (Preview) in Microsoft 365</span></span>

<span data-ttu-id="9db1c-p101">Microsoft 剛已發行 Office 365 中的現有 eDiscovery 功能已更新的進階的 eDiscovery 工具的 preview 版本。這個預覽版本中，呼叫*進階的 eDiscovery （預覽）*，提供保留、 收集、 檢閱、 分析和匯出至您的組織內部和外部調查回應的內容端對端工作流程。</span><span class="sxs-lookup"><span data-stu-id="9db1c-p101">Microsoft has just released a preview version of the updated Advanced eDiscovery tool that builds on the existing eDiscovery capabilities in Office 365. This preview version, called *Advanced eDiscovery (Preview)*, provides an end-to-end workflow to preserve, collect, review, analyze, and export content that's responsive to your organization's internal and external investigations.</span></span> 

## <a name="alignment-with-edrm"></a><span data-ttu-id="9db1c-106">使用 EDRM 的對齊方式</span><span class="sxs-lookup"><span data-stu-id="9db1c-106">Alignment with EDRM</span></span>

<span data-ttu-id="9db1c-107">進階 eDiscovery （預覽） 的內建工作流程對齊 eDiscovery 程序所述來電子搜索參照模型 (EDRM)。</span><span class="sxs-lookup"><span data-stu-id="9db1c-107">The built-in workflow of Advanced eDiscovery (Preview) aligns with the eDiscovery process outlined by the Electronic Discovery Reference Model (EDRM).</span></span> 

![電子化搜索參照模型 (EDRM)](../media/EDRMv1.png)

<span data-ttu-id="9db1c-p102">（受 edrm.net 圖像來源。來源影像已供小小寫指南短片屬性 3.0 Unported 授權。）</span><span class="sxs-lookup"><span data-stu-id="9db1c-p102">(Image source courtesy of edrm.net. The source image was made available under Creative Commons Attribution 3.0 Unported License.)</span></span>

<span data-ttu-id="9db1c-111">在高的層級，以下方式進階 eDiscovery （預覽） 支援 EDRM 工作流程：</span><span class="sxs-lookup"><span data-stu-id="9db1c-111">At a high level, here's how Advanced eDiscovery (Preview) supports the EDRM workflow:</span></span>

- <span data-ttu-id="9db1c-p103">**識別**-之後找出潛在的調查感興趣的人員，您可以將其新增為 custodians （也稱為*資料 custodians*，因為他們可能擁有與調查有關的資訊） 至進階eDiscovery （預覽） 案例。使用者會新增為 custodians 之後，很容易保留、 收集和檢閱 okay 文件。</span><span class="sxs-lookup"><span data-stu-id="9db1c-p103">**Identification** - After you identify potential persons of interest in an investigation, you can add them as custodians (also called *data custodians*, because they may possess information that's relevant to the investigation) to a Advanced eDiscovery (Preview) case. After users are added as custodians, it's easy to preserve, collect, and review custodian documents.</span></span>

- <span data-ttu-id="9db1c-p104">**保留**-保留並保護資料的相關調查、 進階的 eDiscovery （預覽） 可讓您將合法持有萬一 custodians 與相關聯之資料來源上。您也可以保留上放置非 custodial 資料。此外，進階的 eDiscovery （預覽） 具有內建的通訊工作流程，讓您可以將合法持有通知傳送給 custodians 並追蹤其認可。</span><span class="sxs-lookup"><span data-stu-id="9db1c-p104">**Preservation** - To preserve and protect data that's relevant to an investigation, Advanced eDiscovery (Preview) lets you place a legal hold on the data sources that are associated with the custodians in a case. You can also place non-custodial data on hold. Additionally, Advanced eDiscovery (Preview) has a built-in communications workflow so you can send a legal hold notifications to custodians and track their acknowledgments.</span></span>

- <span data-ttu-id="9db1c-117">**集合**-您找出 （並保留） 與調查有關的資料來源之後，您可以使用進階的 eDiscovery （預覽） 搜尋及收集的即時資料中的內建搜尋工具，custodial 的資料來源 （和非 custodial資料來源而言，如果有的話） 可能是相關的大小寫。</span><span class="sxs-lookup"><span data-stu-id="9db1c-117">**Collection** - After you identified (and preserved) the data sources relevant to the investigation, you can use the built-in search tool in Advanced eDiscovery (Preview) search for and collect live data from the custodial data sources (and non-custodial data sources, if applicable) that may be relevant to the case.</span></span>

- <span data-ttu-id="9db1c-p105">**處理**-已收集案例相關的所有資料之後下, 一步是程序的進一步檢閱和分析。進階的 ediscovery （預覽），這表示您 「 集合 」 階段中所識別的就地資料複製到 Azure 儲存位置 （稱為*工作集*），可提供讓您使用之靜態檢視的大小寫資料。</span><span class="sxs-lookup"><span data-stu-id="9db1c-p105">**Processing** - After you've collected all data relevant to the case, the next step is process it for further review and analysis. In Advanced eDiscovery (Preview), this means the in-place data that you identified in the collection phase is copied to Azure storage location (called a *working set*), which provides you with a static view of the case data.</span></span> 
 
- <span data-ttu-id="9db1c-120">**檢閱**-資料已新增至工作之後，您可以檢視特定文件及執行其他查詢以</span><span class="sxs-lookup"><span data-stu-id="9db1c-120">**Review** - After data has been added to a working set, you can view specific documents and run additional queries to</span></span>  
 
- <span data-ttu-id="9db1c-p106">**分析**-進階 eDiscovery （預覽） 提供整合式的分析工具可協助您 cull 從您決定使用集中的資料不是與調查有關。除了以減少相關的資料量、 換頁 eDiscovery （預覽） 也可幫助您儲存 legal review 成本來可讓您組織內容以進行檢閱程序更容易且更有效率。</span><span class="sxs-lookup"><span data-stu-id="9db1c-p106">**Analysis** - Advanced eDiscovery (Preview) provides integrated analytics tools that helps you cull data from the working set that you determine isn't relevant to the investigation. In addition to reducing the volume of relevant data, Advance eDiscovery (Preview) also helps you save legal review costs by letting you organize content to make the review process easier and more efficient.</span></span>

- <span data-ttu-id="9db1c-p107">**實際執行**和**簡報**-備妥之後，您可以將文件匯出為 legal review 工作組中。您可以將其原生格式或 EDRM 指定格式的文件匯出讓他們可以匯入協力廠商檢閱應用程式。</span><span class="sxs-lookup"><span data-stu-id="9db1c-p107">**Production** and **Presentation** - When you're ready, you can export documents from a working set for legal review. You can export documents in their native format or in an EDRM-specified format so they can be imported into third-party review applications.</span></span>

## <a name="advanced-ediscovery-preview-workflow"></a><span data-ttu-id="9db1c-125">進階的 eDiscovery （預覽） 工作流程</span><span class="sxs-lookup"><span data-stu-id="9db1c-125">Advanced eDiscovery (Preview) workflow</span></span>

<span data-ttu-id="9db1c-p108">下列各節說明每個進階 eDiscovery (Preview) 中的內建工作流程中的步驟。下列螢幕擷取畫面顯示名為*產品責任 2019002*案例 [**首頁**] 索引標籤。請注意在頁面頂端的 [工作流程] 索引標籤的順序來對齊 EDRM 程序。</span><span class="sxs-lookup"><span data-stu-id="9db1c-p108">The following sections describe each step in the built-in workflow in Advanced eDiscovery (Preview). The following screenshot shows the **Home** tab of a case named *Product Liability 2019002*. Note the workflow tabs at the top of the page are sequenced to align with the EDRM process.</span></span> 

<span data-ttu-id="9db1c-129">如需進階的 eDiscovery (Preview) 中的端對端工作流程的詳細資訊，請參閱此[影片的 Microsoft 機制](https://go.microsoft.com/fwlink/?linkid=2066133)。</span><span class="sxs-lookup"><span data-stu-id="9db1c-129">For more information about the end-to-end workflow in Advanced eDiscovery (Preview), see this [Microsoft Mechanics video](https://go.microsoft.com/fwlink/?linkid=2066133).</span></span> 

![進階 eDiscovery (Preview) 中的索引標籤遵循 EDRM 工作流程](../media/aedisco-homepage-1.png)

## <a name="managing-custodians"></a><span data-ttu-id="9db1c-131">管理監管人</span><span class="sxs-lookup"><span data-stu-id="9db1c-131">Managing custodians</span></span>

<span data-ttu-id="9db1c-p109">使用 [ **Custodians** ] 索引標籤新增及管理已識別為人員感興趣的大小寫的人員。新增 custodians 之後，您可以快速地執行 okay 相關動作等 okay 資料來源上放置合法的操作方法、 信箱等 OneDrive 帳戶與 custodians、 通訊及搜尋 okay 資料來源收集內容這是案例相關。做為案例的進度，很容易新增新 custodians 或釋出 custodians 從大小寫。如需詳細資訊，請參閱 ＜ [Work with custodians 進階 eDiscovery (Preview) 中](managing-custodians.md)。</span><span class="sxs-lookup"><span data-stu-id="9db1c-p109">Use the **Custodians** tab to add and manage the people that you've identified as persons of interest in the case. When you add custodians, you can quickly perform custodian-related actions such as placing a legal how on custodian data sources, such as their mailbox and OneDrive account, communicating with custodians, and searching custodian data sources to collect content that's relevant to the case. As as the case progress, it's easy to add new custodians or release custodians from the case. For more information, see [Work with custodians in Advanced eDiscovery (Preview)](managing-custodians.md).</span></span>

## <a name="managing-legal-hold-notifications"></a><span data-ttu-id="9db1c-136">管理合法持有通知</span><span class="sxs-lookup"><span data-stu-id="9db1c-136">Managing legal hold notifications</span></span>

<span data-ttu-id="9db1c-p110">使用 [**通訊**] 索引標籤來管理與大小寫的 custodians 通訊的程序。合法持有明會指示 custodians 来保留任何可能案例相關的內容。法律小組必須能夠追蹤的通知已收到、 讀取、 並認可 custodians。進階 eDiscovery (Preview) 中的通訊工作流程可讓您建立及傳送初始通知、 提醒、 版本通知和呈報如果 custodians 失敗確認保留通知。如需詳細資訊，請參閱 ＜ [Work with 進階 eDiscovery (Preview) 中的通訊](managing-custodian-communications.md)。</span><span class="sxs-lookup"><span data-stu-id="9db1c-p110">Use the **Communications** tab to manage the process of communicating with the custodians in the case. A legal hold notice instructs custodians to preserve any content that may be relevant to the case. Legal teams must be able to track that notices have been received, read, and acknowledged by custodians. The communications workflow in Advanced eDiscovery (Preview) allows you create and send initial notifications, reminders, release notices, and escalations if custodians fail to acknowledge a hold notification. For more information, see [Work with communications in Advanced eDiscovery (Preview)](managing-custodian-communications.md).</span></span>

## <a name="managing-content-preservation"></a><span data-ttu-id="9db1c-142">管理內容保留</span><span class="sxs-lookup"><span data-stu-id="9db1c-142">Managing content preservation</span></span>

<span data-ttu-id="9db1c-p111">當您新增 okay 案例時，您必須保留置於 custodial 資料選項。使用 [**保留**] 索引標籤來管理建立當您新增 custodians 及管理其他法律保留保留與大小寫 ； 關聯例如，您可以找出並將保留在非 custodial 資料來源。您也可以編輯案例中的所有暫止並進行查詢式保留以便符合查詢的內容處於保留狀態 ；例如，您無法新增日期範圍至保留使僅包含的內容已建立於特定日期範圍中保留。您也可以取得統計資料的保留的內容、 移除之後當您不再案例相關的保留或予以刪除。如需詳細資訊，請參閱[管理保留進階 eDiscovery (Preview) 中](managing-holds.md)。</span><span class="sxs-lookup"><span data-stu-id="9db1c-p111">When you add a custodian to a case, you have the option to place a hold on custodial data. Use the **Holds** tab to manage the hold created when you add custodians and manage additional legal holds associated with the case; for example, you can identify and place a hold on non-custodial data sources. You can also edit any hold in the case and make it a query-based hold so that only the content that matches the query is placed on hold; for example, you could add a date range to the hold so that only content that was created within a specific date ranged in preserved. You can also get statistics on content that's on hold, remove the hold after when it's no longer relevant to the case, or delete it. For more information, see [Manage holds in Advanced eDiscovery (Preview)](managing-holds.md).</span></span>

## <a name="indexing-custodian-data"></a><span data-ttu-id="9db1c-148">編製索引 okay 資料</span><span class="sxs-lookup"><span data-stu-id="9db1c-148">Indexing custodian data</span></span>

<span data-ttu-id="9db1c-p112">新增案例 okay 與對應的 custodial 資料來源，okay 的資料來源的任何部分已編製索引項目會重新編製索引 （藉由呼叫*進階編製索引*的程序）。這允許 custodial 內容，例如圖像、 不支援的檔案類型及其他可能未編製索引的內容執行搜尋以收集案例相關的資料時要完全可供搜尋。使用 [**處理**] 索引標籤來監視進階編製索引和修正程式處理錯誤 （使用處理序 calle*錯誤補救*） 的狀態如需詳細資訊，請參閱[修正進階 eDiscovery (Preview) 中的處理錯誤](processing-data-for-case.md)。</span><span class="sxs-lookup"><span data-stu-id="9db1c-p112">When you add a custodian and the corresponding custodial data sources to a case, any partially indexed item from a custodian data source is re-indexed (by a process called *Advanced indexing*). This allow custodial content such as images, unsupported file types, and other potentially un-indexed content to be fully searchable when you run searches to collect data that's relevant to the case. Use the **Processing** tab to monitor the status of Advanced indexing and fix processing errors (using a process calle *error remediation*.) For more information, see [Fix processing errors in Advanced eDiscovery (Preview)](processing-data-for-case.md).</span></span>

## <a name="collecting-case-data"></a><span data-ttu-id="9db1c-152">收集案例資料</span><span class="sxs-lookup"><span data-stu-id="9db1c-152">Collecting case data</span></span>

<span data-ttu-id="9db1c-p113">使用 [**搜尋**] 索引標籤來搜尋就地 custodial 搜尋及非 custodial 資料來源中建立 Office 365 案例相關的內容。您可建立並執行查詢為基礎的搜尋 （使用關鍵字和條件） 來識別設定電子郵件和文件相關大小寫與您想要進一步檢閱和分析中的 eDiscovery 工作流程中的後續步驟。您可以建立與案例相關聯的一或多個搜尋。此外，您可以使用搜尋工具預覽範例文件和檢視搜尋統計資料可以協助調整以及改善搜尋結果。一旦您正在滿足搜尋結果包含的所有資料案例相關、 將搜尋結果新增到工作組供進一步檢閱、 分析和必要的話，挑選。如需詳細資訊，請參閱[收集資料的進階 eDiscovery (Preview) 中的案例](collecting-data-for-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="9db1c-p113">Use the **Searches** tab to create searches to search the in-place custodial and non-custodial data sources in Office 365 for content that is relevant to the case. You can create and run query-based searches (using keywords and conditions) to identify a set email messages and documents that are relevant to the case and the  you want to further review and analyze in subsequent steps in the eDiscovery workflow. You can create one or more searches associated with the case. Additionally, you can use the search tool to preview sample documents and view search statistics that may help refine and improve the search results. Once you're satisfied that the search results contain the all the data relevant to the case, you add the search results to a working set for further review, analysis and if necessary, culling. For more information, see [Collect data for a case in Advanced eDiscovery (Preview)](collecting-data-for-ediscovery.md).</span></span>

## <a name="reviewing-and-analyzing-case-data"></a><span data-ttu-id="9db1c-159">檢閱和分析案例的資料</span><span class="sxs-lookup"><span data-stu-id="9db1c-159">Reviewing and analyzing case data</span></span>

<span data-ttu-id="9db1c-p114">使用 [**處理設定**] 索引標籤或檢閱和分析您已從即時系統收集並新增至工作集的內容。*工作集*是靜態集合 （換言之，觀點離線複本） 的 custodial 資料 (如果適用的話，非 custodial 資料) 您收集在 eDiscovery 工作流程的上一個階段。搜尋結果新增至工作集之後，程序就會觸發檔案擷取容器、 擷取中繼資料，並會擷取文字。完成此程序時，系統會建立新索引的所有資料從 custodians 收集並新增至工作設定。一旦資料新增至工作集，您可以執行額外的查詢來縮小範圍的大小寫的資料、 做為文字或原生檔案格式檢視資料和加上註解、 redact、 和標籤文件中的工作設定。此外，您可以執行進階的分析例如識別文件重複、 電子郵件超執行緒，和佈景主題。一旦您已經下列只是案例相關的資料，可以直接下載下載文件或將它們匯出檔案的中繼資料、 註釋、 和任何標記。如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="9db1c-p114">Use the **Working sets** tab or review and analyze the content that you've collected from the live system and added to a working set. A *working set* is a static collection (in other words, an offline copy of dat) of custodial data (and if applicable, non-custodial data ) that you collected in the previous phase of the eDiscovery workflow. When you add search results to a working set, a process is triggered that extracts files from containers, extracts metadata, and extracts text. When this process is complete, the system builds a new index of all the data collected from custodians and added to the working set. Once the data is added to the working set, you can run additional queries to narrow the case data, view data as text or in the native file format, and annotate, redact, and tag documents in the working set. Additionally, you can perform advanced analytics such as identify document duplication, email threading, and themes. Once you've culled the data to only what is relevant to the case, you can either download download documents directly or export them along with file metadata, annotations, and any tags. For more information, see:</span></span>

  - [<span data-ttu-id="9db1c-168">檢閱 case 進階 eDiscovery (Preview) 中的資料</span><span class="sxs-lookup"><span data-stu-id="9db1c-168">Review case data in Advanced eDiscovery (Preview)</span></span>](reviewing-data-in-working-set.md)
  - [<span data-ttu-id="9db1c-169">分析進階 eDiscovery (Preview) 中使用集中的資料</span><span class="sxs-lookup"><span data-stu-id="9db1c-169">Analyze data in a working set in Advanced eDiscovery (Preview)</span></span>](analyzing-data-in-working-set.md)

## <a name="exporting-data-for-review-and-presentation"></a><span data-ttu-id="9db1c-170">匯出資料的檢閱和簡報</span><span class="sxs-lookup"><span data-stu-id="9db1c-170">Exporting data for review and presentation</span></span>

<span data-ttu-id="9db1c-p115">將資料匯出從工作集之後，請使用 [**匯出**] 索引標籤來管理匯出工作並下載工作組中的資料。當您將匯出的工作集時，將資料上傳至 Azure 儲存位置，然後供下載至本機電腦。您可以取得位置和儲存評估需要下載 [**匯出**] 索引標籤上的匯出的資料的索引鍵。如需詳細資訊，請參閱 ＜ [case 進階 ediscovery (Preview) 資料匯出](exporting-data-ediscover20.md)。</span><span class="sxs-lookup"><span data-stu-id="9db1c-p115">After you export the data from a working set, use the **Exports** tab to manage an export job and download data from a working set. When you export a working set, the data is uploaded to an Azure storage location and then is available to be downloaded to a local computer. You can obtain the location and storage assess key necessary to download the exported data on the **Exports** tab. For more information, see [Export case data in Advanced eDiscovery (Preview)](exporting-data-ediscover20.md).</span></span>

## <a name="managing-jobs"></a><span data-ttu-id="9db1c-174">管理工作</span><span class="sxs-lookup"><span data-stu-id="9db1c-174">Managing jobs</span></span>

<span data-ttu-id="9db1c-p116">使用 [**工作**] 索引標籤來監視長時間執行程序的案例相關之工作已起始、 做為重新編製索引的搜尋、 搜尋、 及匯出。例如，您可能會建立新的搜尋包含大量資料來源的 [**搜尋**] 索引標籤。在 [**工作**] 索引標籤上顯示此搜尋程序的狀態。如需詳細資訊，請參閱 ＜[進階 eDiscovery (Preview) 中的管理工作](managing-jobs-ediscovery20.md)。</span><span class="sxs-lookup"><span data-stu-id="9db1c-p116">Use the **Jobs** tab to monitor long-running processes for case-related tasks that you've initiated, searches as re-indexing, searches, and exports. For example, you might create a new search on the **Searches** tab that includes a large number of data sources. The status of this search process is displayed on the **Jobs** tab. For more information, see [Manage jobs in Advanced eDiscovery (Preview)](managing-jobs-ediscovery20.md).</span></span>

## <a name="configuring-case-settings"></a><span data-ttu-id="9db1c-178">設定案例設定</span><span class="sxs-lookup"><span data-stu-id="9db1c-178">Configuring case settings</span></span>

<span data-ttu-id="9db1c-p117">使用 [**設定**] 索引標籤的設定整個大小寫的設定。這包括新增成員至大小寫、 關閉或刪除案例及設定搜尋與分析的行為。如需詳細資訊，請參閱 ＜[設定進階 eDiscovery (Preview) 中的案例設定](configuring-case-settings-ediscovery20.md)。</span><span class="sxs-lookup"><span data-stu-id="9db1c-p117">Use the **Settings** tab for configure case-wide settings. This includes adding members to a case, closing or deleting a case, and configuring search and analytics behavior. For more information, see [Configure case settings in Advanced eDiscovery (Preview)](configuring-case-settings-ediscovery20.md).</span></span>

