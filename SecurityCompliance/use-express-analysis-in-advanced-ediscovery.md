---
title: 在 Office 365 進階電子文件探索中使用快速分析
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 50580099-3dc0-44a1-a9b6-5ca6d396316b
description: 了解如何執行 Office 365 進階 eDiscovery 的 Express 分析模式
ms.openlocfilehash: a71e6775b1116e805e455815dca53a727d887809
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526617"
---
# <a name="use-express-analysis-in-office-365-advanced-ediscovery"></a><span data-ttu-id="97b5c-103">在 Office 365 進階電子文件探索中使用快速分析</span><span class="sxs-lookup"><span data-stu-id="97b5c-103">Use Express Analysis in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="97b5c-p101">進階的 eDiscovery 需要您組織與進階規範附加元件或 E5 訂閱 Office 365 E3。如果您不具有該對應並想要嘗試進階的 eDiscovery，您還可以[註冊 Office 365 企業版 E5 的試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="97b5c-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="97b5c-106">您可以使用**Express 分析**快速分析案例及匯出結果。</span><span class="sxs-lookup"><span data-stu-id="97b5c-106">You can use **Express analysis** to quickly analyze a case and export the results.</span></span> 
  
<span data-ttu-id="97b5c-p102">您可以使用 express 分析計算接近重複項目和電子郵件執行緒計算佈景主題。您也可以設定[Express 分析的進階的設定](use-express-analysis-in-advanced-ediscovery.md#BK_AdvancedSettings)] 中的佈景主題、 文件相似性和匯出檔案的特定參數。</span><span class="sxs-lookup"><span data-stu-id="97b5c-p102">You can use express analysis to calculate near-duplicates and email threads and calculate themes. You can also set certain parameters for themes, document similarity and the export files in the [Advanced settings for Express analysis](use-express-analysis-in-advanced-ediscovery.md#BK_AdvancedSettings).</span></span>
  
## <a name="run-express-analysis"></a><span data-ttu-id="97b5c-109">執行 Express 分析</span><span class="sxs-lookup"><span data-stu-id="97b5c-109">Run Express analysis</span></span>

1. <span data-ttu-id="97b5c-110">**Express 分析**(1) 索引標籤中，選取 [啟用容器 * * Express 分析 * * (2) 和 [**進階設定**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="97b5c-110">In the **Express analysis** (1) tab, select a container to enable the ** Express analysis ** (2), and **Advanced settings** buttons.</span></span> 
    
    ![Express 分析] 頁面的螢幕擷取畫面](media/60009974-5d1f-4971-8ebe-e5ec74e7fd2a.jpg)
  
2. <span data-ttu-id="97b5c-112">[**分析] 參數**：</span><span class="sxs-lookup"><span data-stu-id="97b5c-112">Under **Analyze parameters**:</span></span>
    
  - <span data-ttu-id="97b5c-p103">如果您想要執行分析] 核取**計算接近重複項目及電子郵件執行緒**。預設會選取它。</span><span class="sxs-lookup"><span data-stu-id="97b5c-p103">Check **Calculate near-duplicates and email threads** if you want to run the analysis. It is selected by default.</span></span> 
    
  - <span data-ttu-id="97b5c-p104">檢查處理所有檔案並將佈景主題指派給他們的**計算佈景主題**。預設會選取它。</span><span class="sxs-lookup"><span data-stu-id="97b5c-p104">Check **Calculate Themes** to process all files and assign themes to them. It is selected by default.</span></span> 
    
3. <span data-ttu-id="97b5c-117">**匯出目的**：</span><span class="sxs-lookup"><span data-stu-id="97b5c-117">Under **Export destination**:</span></span>
    
  - <span data-ttu-id="97b5c-118">檢查下載至您的本機電腦的 [**下載至本機電腦**。</span><span class="sxs-lookup"><span data-stu-id="97b5c-118">Check **Download to local machine** to download to your local computer.</span></span> 
    
  - <span data-ttu-id="97b5c-119">如果您檢查**匯出至使用者定義的 Azure blob**然後您也可以指定容器 URL 及 SAS 權杖。</span><span class="sxs-lookup"><span data-stu-id="97b5c-119">If you check **Export to user-defined Azure blob** then you can also specify a container URL and SAS token.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="97b5c-p105">一旦匯出套件儲存至使用者定義的 Azure blob、 資料不再受管理的進階 eDiscovery。它被管理 Azure blob。這表示如果您刪除案例，匯出的檔案仍會維持在 Azure blob。</span><span class="sxs-lookup"><span data-stu-id="97b5c-p105">Once an export package is stored to the user defined Azure blob, the data is no longer managed by Advanced eDiscovery. it is managed by the Azure blob. This means if you delete the case, the exported files will still remain on the Azure blob.</span></span> 
  
  - <span data-ttu-id="97b5c-123">**儲存 SAS 權杖未來匯出工作階段**： 如果檢查，要 SAS 權杖加密供日後使用進階的 eDiscovery 內部資料庫中。</span><span class="sxs-lookup"><span data-stu-id="97b5c-123">**Save SAS token for future export session**: If checked, the SAS token will be encrypted in the Advanced eDiscovery's internal database for future use.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="97b5c-p106">目前 SAS 權杖會在每個月後到期。如果您嘗試下載您要復原最後一個工作階段有多個月之後，然後再次匯出。</span><span class="sxs-lookup"><span data-stu-id="97b5c-p106">Currently the SAS token expires after a month. If you try to download after more than a month you have to undo last session, then export again.</span></span> 
  
4. <span data-ttu-id="97b5c-126">要啟動 express 分析與預設設定，選擇 [ **Express 分析**，並會顯示 [**工作狀態**] 頁面</span><span class="sxs-lookup"><span data-stu-id="97b5c-126">To start the express analysis with default settings, choose **Express analysis**, and the **Task status** page will display</span></span> 
    
    <span data-ttu-id="97b5c-127">在 [**工作狀態**] 頁面即可展開**程序**、**分析**及**匯出**] 索引標籤以顯示 express 執行的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="97b5c-127">On the **Task status** page you can expand the **Process**, **Analyze** and **Export** tabs to display details about the express run.</span></span> 
    
    ![這個螢幕擷取畫面的進階 eDiscovery Express 分析工作狀態] 頁面](media/bf30ab02-9828-4a6d-a485-0babc2c49ae5.jpg)
  
5. <span data-ttu-id="97b5c-129">選擇 [ **Express 分析摘要**] 頁面上列出執行的詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="97b5c-129">Choose the **Express analysis summary** page to list detailed information about the run.</span></span> 
    
    <span data-ttu-id="97b5c-p107">在 [ **Express 分析摘要**] 頁面的底端，選擇 [下載分析檔案 tp 本機電腦的**下載上次的工作階段**。您會先下載 eDiscovery 匯出工具並貼至 eDiscovery 匯出工具匯出金鑰。</span><span class="sxs-lookup"><span data-stu-id="97b5c-p107">On the bottom of the **Express analysis summary** page, choose **Download last session** to download the analysis files tp your local computer. You will first have to download eDiscovery Export tool and paste the Export key to the eDiscovery Export tool.</span></span> 
    
## <a name="advanced-settings-for-express-analysis"></a><span data-ttu-id="97b5c-132">進階的設定 Express 分析</span><span class="sxs-lookup"><span data-stu-id="97b5c-132">Advanced settings for Express analysis</span></span>
<span data-ttu-id="97b5c-133"><a name="BK_AdvancedSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="97b5c-133"></span></span>

<span data-ttu-id="97b5c-134">您可以選擇性地設定來變更預設 Express 分析參數的 [**進階設定**。</span><span class="sxs-lookup"><span data-stu-id="97b5c-134">You can optionally set **Advanced settings** to change the default Express analysis parameters.</span></span> 
  
1. <span data-ttu-id="97b5c-135">在 [**分析**] 區段中：</span><span class="sxs-lookup"><span data-stu-id="97b5c-135">In the **Analyze** section:</span></span> 
    
  - <span data-ttu-id="97b5c-136">在**接近重複項目及電子郵件執行緒**，輸入**文件相似性**值，或接受預設值是 65%。</span><span class="sxs-lookup"><span data-stu-id="97b5c-136">In the **Near duplicates and email threads**, enter the **Document similarity** value, or accept the default of 65%.</span></span> 
    
  - <span data-ttu-id="97b5c-p108">在 [**佈景主題的最大數目**輸入或選取建立佈景主題數目的值。預設值為 200。</span><span class="sxs-lookup"><span data-stu-id="97b5c-p108">In the **Max number of themes** enter or select a value for the number of themes to create. The default is 200.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="97b5c-p109">增加的佈景主題數目會影響效能，如一般化佈景主題的能力。佈景主題數目較高、 更細微它們。例如，如果 50 佈景主題的一組包含如"籃球、 Spurs、 Clippers、 Lakers"； 將佈景主題300 佈景主題可能會包含不同的佈景主題："Spurs"，"Clippers"，"Lakers"。如果您有無佈景主題的認知"籃球"並使用 ECA 這項功能，看不到佈景主題 」 籃球 」 可能是很有用。但是，如果處理有太多的佈景主題，您可能會永遠不會看到的字"籃球"並可能不知道該 Spurs 和 Clippers 是很好的籃球佈景主題可供檢閱，而不是移入的項目會開機並用於字形。</span><span class="sxs-lookup"><span data-stu-id="97b5c-p109">Increasing the number of themes affects performance, as well as the ability of a theme to generalize. The higher the number of themes, the more granular they are. For example, if a set of 50 themes include a theme such as "Basketball, Spurs, Clippers, Lakers"; 300 themes may include separate themes: "Spurs", "Clippers", "Lakers". If you had no awareness of the theme "Basketball" and use this feature for ECA, seeing the theme "Basketball" could be useful. But, if the processing had too many themes, you may never see the word "Basketball" and may not know that Spurs and Clippers are good Basketball themes to review, rather than items that go on boots and used for hair.</span></span> 
  
  - <span data-ttu-id="97b5c-p110">在 [**建議追蹤佈景主題**中選擇 [**修改**建議來控制處理的佈景主題的佈景主題文字。進階的 eDiscovery 將重心在這些建議的字詞與嘗試建立一或多個相關的佈景主題，根據"最高的佈景主題數目 」 設定。</span><span class="sxs-lookup"><span data-stu-id="97b5c-p110">In the **Suggested themes** choose **Modify** to suggest theme words to control Themes processing. Advanced eDiscovery will focus on these suggested words and try to create one or more relevant themes, based on the "Max number of themes" settings.</span></span> 
    
    <span data-ttu-id="97b5c-p111">例如，若建議的單字"computer"，且您指定作為"佈景主題的最大數目""2"，進階的 eDiscovery 會嘗試產生兩個單字"computer"與相關的佈景主題。佈景主題的兩個可能會是"電腦軟體"和"電腦 hardware"，例如。</span><span class="sxs-lookup"><span data-stu-id="97b5c-p111">For example, if the suggested word is "computer", and you specified "2" as the "Max number of Themes", Advanced eDiscovery will try to generate two themes that relate to the word "computer". The two themes might be "computer software" and "computer hardware", for example.</span></span>
    
    ![新增建議的佈景主題](media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
  - <span data-ttu-id="97b5c-149">**模式**從下拉式清單中選取**佈景主題**選項：</span><span class="sxs-lookup"><span data-stu-id="97b5c-149">**Mode** From the drop-down list, select a **Themes** option:</span></span> 
    
  - <span data-ttu-id="97b5c-150">**建立並套用模型**： 計算的模型檔案的線段的佈景主題，然後將它們之間的檔案。</span><span class="sxs-lookup"><span data-stu-id="97b5c-150">**Create and apply model**: Calculates themes by models from a segment of the files and then distributes files among them.</span></span>
    
  - <span data-ttu-id="97b5c-p112">**建立模型**： 從檔案的線段的佈景主題模型來計算。套用處理所得的餘數檔案已完成另外另一次。</span><span class="sxs-lookup"><span data-stu-id="97b5c-p112">**Create model**: Calculates a themes model from a segment of the files. The Apply process of dividing files is done separately at another time.</span></span>
    
  - <span data-ttu-id="97b5c-p113">**套用模型**： 此選項只會顯示是否先前建立及尚未套用模型。這會劃分為基礎的佈景主題檔案。</span><span class="sxs-lookup"><span data-stu-id="97b5c-p113">**Apply model**: This option is only shown if a model was created previously and not yet applied. This will divide the files based on the themes.</span></span>
    
2. <span data-ttu-id="97b5c-155">在 [**匯出**] 區段中：</span><span class="sxs-lookup"><span data-stu-id="97b5c-155">In the **Export** section:</span></span> 
    
1. <span data-ttu-id="97b5c-156">在 [**選取匯出批次**中：</span><span class="sxs-lookup"><span data-stu-id="97b5c-156">In the **Select export batch**:</span></span>
    
  - <span data-ttu-id="97b5c-157">從**匯出批次**] 清單中，選取批次名稱，或將結果匯出至匯出批次 01、 （預設批次）。</span><span class="sxs-lookup"><span data-stu-id="97b5c-157">From the **Export batch** list, select the batch name or export results to Export batch 01, (the default batch).</span></span> 
    
  - <span data-ttu-id="97b5c-p114">若要匯出之新檔案新增至現有案例的結果，繼續執行您目前的批次。批次中建立工作階段、 選取相同的批次數目，並按一下 [**建立匯出工作階段**您可以以累加方式將相同參數匯出成先前的批次，請使用此選項。</span><span class="sxs-lookup"><span data-stu-id="97b5c-p114">To export results for new files that you added to an existing case, continue with your current batch. To create a session in the batch, select the same batch number and click **Create export session** You can use this option to export the same parameters as the previous batch, in an incremental manner.</span></span> 
    
  - <span data-ttu-id="97b5c-p115">若要匯出至新的批次，請按一下 [**新增**![新增圖示](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)及**批次名稱**] 中輸入新名稱 （或接受預設值） 和**批次描述**中的描述。按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="97b5c-p115">To export to a new batch, click **Add**![add icon](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) and enter a new name in **Batch name** (or accept the default) and a description in **Batch description**. Click **OK**.</span></span>
    
  - <span data-ttu-id="97b5c-162">若要編輯的批次名稱或描述，選取中**匯出批次**名稱、 按一下 [**編輯**![編輯圖示](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png)，並修改欄位。</span><span class="sxs-lookup"><span data-stu-id="97b5c-162">To edit a batch name or description, select the name in **Export batch**, click **Edit** ![Edit icon](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png), and then modify the fields.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="97b5c-p116">您已執行匯出批次的工作階段之後，他們無法刪除。此外，僅部分參數可以編輯之後執行第一個工作階段。</span><span class="sxs-lookup"><span data-stu-id="97b5c-p116">After you've run sessions for an export batch, they cannot be deleted. In addition, only some parameters can be edited once the first session is run.</span></span> 
  
  - <span data-ttu-id="97b5c-165">若要建立的重複匯出批次，請選擇 [**重複匯出批次**![建立重複匯出批次圖示](media/3f6d5f59-e842-4946-a493-473528af0119.jpg)並在 [控制台] 中輸入名稱和描述的重複的批次。</span><span class="sxs-lookup"><span data-stu-id="97b5c-165">To create a duplicate export batch, choose **Duplicate export batch**![Create a duplicate export batch icon](media/3f6d5f59-e842-4946-a493-473528af0119.jpg) and enter a name and a description for the duplicate batch in the panel.</span></span> 
    
  - <span data-ttu-id="97b5c-166">若要刪除匯出批次，請選擇 [**刪除**![刪除匯出批次圖示](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg)。</span><span class="sxs-lookup"><span data-stu-id="97b5c-166">To delete an export batch, choose **Delete**![Delete an export batch icon](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg).</span></span>
    
  - <span data-ttu-id="97b5c-167">若要檢視的批次的歷程記錄，請選擇 [**批次歷程記錄**![檢視歷程記錄圖示](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg)。</span><span class="sxs-lookup"><span data-stu-id="97b5c-167">To view the history of a batch, choose **Batch history**![View history icon](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg).</span></span>
    
2. <span data-ttu-id="97b5c-p117">[定義 p **opulation:** 選取**包括上方相關性截止分數的檔案**和/或**精選匯出批次**如果您想要微調匯出批次的設定。如果您選取 [**包括上方相關性截止分數的檔案**、 已啟用**問題**，以及如果檔案的相關性分數為高於所選問題截止分數，然後將檔案匯出。除非排除的將匯出的檔案 '**檢閱**篩選。如果您選取 [**精選匯出批次**，然後再**取消 dupe**和**Filter by '檢閱' 欄位**選項] 按鈕隨即啟用。如果您選擇**取消 dupe**，然後重複檔案將會是篩選出根據所定義的原則： [案例層級 （預設值）： 從重複檔案在整個案例中的每個集，所有但一個檔案將會被取消 duped。Okay 層級： 從重複檔案的相同 okay 每組，所有但一個檔案將會被取消 duped。使用匯出輸出中重複的所有檔案的記錄。如果您選擇**Filter by '供檢閱'** 欄位，選取 [**修改] 底下的中繼資料**輸入您 **'供檢閱'** 欄位設定。選取要納入套件內容的來源檔案**包含輸入的檔案**。您可以清除此選項可加速匯出程序。請注意會匯出在任何情況下的原生檔案。</span><span class="sxs-lookup"><span data-stu-id="97b5c-p117">Under Define p **opulation:** Select **Include only files above Relevance cut-off score** and/or **Refine export batch** if you want to fine-tune the settings for your export batch. If you select **Include only files above Relevance cut-off score**, then the **Issue** is enabled, and if the file's relevance score is higher than the cut-off score for the selected issue, then the file is exported. The file will be exported unless it's excluded by the ' **For review** filter. If you select **Refine export batch**, then the **De-dupe** and **Filter by 'For review' field** radio buttons are enabled. If you choose **De-dupe**, then duplicates files will be filtered-out according to the policy defined: [Case level (default): from every set of duplicate files in the entire case, all but one file will be de-duped. Custodian level: from every set of duplicate files of the same custodian, all but one file will be de-duped. A record of all duplicate files is available in export output. If you choose **Filter by 'For review'** field, select **Modify under Metadata** to enter your **'For review'** field settings. Select **Include input files**to include source files in the package content. You can clear this option to speed up the export process. Note that the Native files will be exported in any case.</span></span>
    
3. <span data-ttu-id="97b5c-179">**定義中繼資料**、 底下選取 [從下列選項 （一次每個工作階段） 的 [**匯出範本**] 清單中。</span><span class="sxs-lookup"><span data-stu-id="97b5c-179">Under **Define metadata**, select from the following options in the **Export template** list (once per session).</span></span> 
    
  - <span data-ttu-id="97b5c-p118">**標準**： 基本組資料的項目、 中繼資料、 及屬性。匯入資料已處理的進階 eDiscovery 並將資料匯出至已包含的檔案系統上傳時使用此選項。根據預設，匯出資料行是建立和填滿的範本。</span><span class="sxs-lookup"><span data-stu-id="97b5c-p118">**Standard**: Basic set of data items, metadata, and properties. Use this option when import data was already processed in Advanced eDiscovery and export data is uploaded to a system that already contains the files. By default, export template columns are created and filled.</span></span>
    
  - <span data-ttu-id="97b5c-p119">**所有**： 整組包括所有處理資料以及分析與相關性分數的標準中繼資料。此範本時所需進階的 eDiscovery 執行處理及檔案資料上傳至外部系統的第一次。</span><span class="sxs-lookup"><span data-stu-id="97b5c-p119">**All**: Full set of standard metadata including all processing data, as well as Analyze and Relevance scores. This template is required when Advanced eDiscovery performs the processing and file data is uploaded to an external system for the first time.</span></span>
    
  - <span data-ttu-id="97b5c-185">**問題**： 選取 [**所有問題**] 或都選取您建立的特定問題。</span><span class="sxs-lookup"><span data-stu-id="97b5c-185">**Issues**: Select **All Issues** or select a particular issue you have created.</span></span> 
    
<span data-ttu-id="97b5c-186">選擇 **[確定]** 以儲存進階的設定] 以使用預設值的 [**還原成預設值**或 [**取消**] 取消 [設定進階的設定。</span><span class="sxs-lookup"><span data-stu-id="97b5c-186">Choose **OK**to save the advanced settings, **Restore defaults** to use default values, or **Cancel** to cancel setting the advanced settings.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="97b5c-187">另請參閱</span><span class="sxs-lookup"><span data-stu-id="97b5c-187">See also</span></span>
<span data-ttu-id="97b5c-188"><a name="BK_AdvancedSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="97b5c-188"></span></span>

[<span data-ttu-id="97b5c-189">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="97b5c-189">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)

