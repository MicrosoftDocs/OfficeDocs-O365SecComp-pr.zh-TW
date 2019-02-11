---
title: 在 Office 365 進階電子文件探索中匯出結果
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
ms.assetid: a9951a07-10b3-48cb-b37a-0ffaa24931ad
description: '了解如何定義要用於匯出結果從 Office 365 進階 eDiscovery，包括指定匯出批次參數的程序的選項。 '
ms.openlocfilehash: 49dab9820735af3bf5c322fc531c78a6baab2f8e
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2019
ms.locfileid: "29559046"
---
# <a name="export-results-in-office-365-advanced-ediscovery"></a><span data-ttu-id="b9583-103">在 Office 365 進階電子文件探索中匯出結果</span><span class="sxs-lookup"><span data-stu-id="b9583-103">Export results in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="b9583-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="b9583-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="b9583-106">本主題說明進階的 eDiscovery 匯出的安裝程式選項。</span><span class="sxs-lookup"><span data-stu-id="b9583-106">This topic describes the Advanced eDiscovery Export Setup options.</span></span>
  
 <span data-ttu-id="b9583-107">**本主題內容：**</span><span class="sxs-lookup"><span data-stu-id="b9583-107">**In this topic:**</span></span>
  
- [<span data-ttu-id="b9583-108">定義匯出批次和工作階段</span><span class="sxs-lookup"><span data-stu-id="b9583-108">Defining export batches and sessions</span></span>](export-results-in-advanced-ediscovery.md#BK_Define)
    
- [<span data-ttu-id="b9583-109">累加及其他匯出</span><span class="sxs-lookup"><span data-stu-id="b9583-109">Incremental and additional exports</span></span>](export-results-in-advanced-ediscovery.md#BK_IncrementalReports)
    
- [<span data-ttu-id="b9583-110">設定批次匯出參數</span><span class="sxs-lookup"><span data-stu-id="b9583-110">Set up batch export parameters</span></span>](export-results-in-advanced-ediscovery.md#BK_SetUpExport)
    
- [<span data-ttu-id="b9583-111">匯出報告輸出檔案</span><span class="sxs-lookup"><span data-stu-id="b9583-111">Export report output files</span></span>](export-results-in-advanced-ediscovery.md#BK_ExportOutputFIles)
    
## <a name="defining-export-batches-and-sessions"></a><span data-ttu-id="b9583-112">定義匯出批次和工作階段</span><span class="sxs-lookup"><span data-stu-id="b9583-112">Defining export batches and sessions</span></span>
<span data-ttu-id="b9583-113"><a name="BK_Define"> </a></span><span class="sxs-lookup"><span data-stu-id="b9583-113"></span></span>

<span data-ttu-id="b9583-p102">匯出批次允許匯出處理使用一組已定義的參數。進階的 eDiscovery 可讓您定義來自訂每個匯出的批次。</span><span class="sxs-lookup"><span data-stu-id="b9583-p102">An export batch allows export processing using a set of defined parameters. Advanced eDiscovery enables you to define batches to customize each export.</span></span>
  
<span data-ttu-id="b9583-p103">參數定義每個匯出批次。案例的第一個批次的預設會建立名為 「 匯出批次 01"的批次。您也可以編輯的批次名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="b9583-p103">Parameters are defined per export batch. A batch named "Export batch 01" is created by default for the first batch of a case. You can also edit the batch name and description.</span></span>
  
<span data-ttu-id="b9583-119">匯出工作階段是進階 eDiscovery 匯出匯出批次中執行。</span><span class="sxs-lookup"><span data-stu-id="b9583-119">An export session is an execution of Advanced eDiscovery Export within an export batch.</span></span>
  
## <a name="incremental-and-additional-exports"></a><span data-ttu-id="b9583-120">累加及其他匯出</span><span class="sxs-lookup"><span data-stu-id="b9583-120">Incremental and additional exports</span></span>
<span data-ttu-id="b9583-121"><a name="BK_IncrementalReports"> </a></span><span class="sxs-lookup"><span data-stu-id="b9583-121"></span></span>

<span data-ttu-id="b9583-p104">您可以執行多個匯出工作階段中匯出批次，以確保結果一致根據同一個匯出範本和參數。批次中每個工作階段，您可以將匯出分析的新處理案例資料及處理每個"逐漸"。</span><span class="sxs-lookup"><span data-stu-id="b9583-p104">You can run multiple export sessions within an export batch, to ensure consistent results based on the same export template and parameters. For each session within a batch, you can export analytics for newly processed case data and process each "incrementally."</span></span>
  
<span data-ttu-id="b9583-p105">若要匯出使用一組不同的參數，您需要建立新的批次。新的批次中第一個工作階段會產生處理案例為止，不論這些檔案所匯入及處理透過一或多個匯入檔案的結果。每個批次重新計算樞紐分析表、 相似性、 inclusives 等。工作階段使用批次所定義的參數和樞紐分析表、 相似性、 inclusives 等的每個工作階段執行不重新計算。</span><span class="sxs-lookup"><span data-stu-id="b9583-p105">In order to export using a different set of parameters, you first need to create a new batch. The first session in the new batch will produce results for files processed in the case so far, whether or not these files were imported and processed over one or multiple Imports. Each batch recalculates pivots, similarity, inclusives, etc. Sessions use the parameters defined for the batch and do not recalculate pivots, similarity, inclusives, etc. for each session execution.</span></span>
  
<span data-ttu-id="b9583-p106">例如，假設已匯入案例和其資料分析。以擷取接近重複項目及電子郵件執行緒累加資料的結果，請按一下 [先前用來將資料匯出同一批次中的 [**建立匯出工作階段**]。</span><span class="sxs-lookup"><span data-stu-id="b9583-p106">For example, assume a case was imported and its data analyzed. In order to retrieve Near-duplicates and Email Threading results for the incremental data, click **Create export session** in the same batch that was previously used to export data.</span></span> 
  
## <a name="set-up-batch-export-parameters"></a><span data-ttu-id="b9583-129">設定批次匯出參數</span><span class="sxs-lookup"><span data-stu-id="b9583-129">Set up batch export parameters</span></span>
<span data-ttu-id="b9583-130"><a name="BK_SetUpExport"> </a></span><span class="sxs-lookup"><span data-stu-id="b9583-130"></span></span>

<span data-ttu-id="b9583-p107">EDiscovery 匯出工具來進階 eDiscovery 搜尋結果匯出至本機電腦。若要增加的資料傳輸輸送量與提升並匯出程序，您可以在您使用匯出搜尋結果的電腦上設定 Windows 登錄設定。如果您想要增加下載速度，設定登錄前設定設定匯出參數。如需詳細資訊，請參閱[增加匯出 eDiscovery 搜尋結果從 Office 365 時的下載速度](increase-download-speeds-when-exporting-ediscovery-results.md)。</span><span class="sxs-lookup"><span data-stu-id="b9583-p107">The eDiscovery Export Tool is used to export search results from Advanced eDiscovery to your local computer. To increase the data transfer throughput and speed-up the export process, you can configure a Windows Registry setting on the computer that you use to export the search results. If you'd like to increase the download speed, configure the registry setting before you set up the export parameters. For more information, see [Increase the download speed when exporting eDiscovery search results from Office 365](increase-download-speeds-when-exporting-ediscovery-results.md).</span></span>
  
1. <span data-ttu-id="b9583-135">進階 eDiscovery 中選取 [大小寫並按一下 [**匯出** \> **安裝程式**。</span><span class="sxs-lookup"><span data-stu-id="b9583-135">In Advanced eDiscovery, select a Case and click **Export** \> **Setup**.</span></span>
    
    - <span data-ttu-id="b9583-136">從**匯出批次**] 清單中，選取批次名稱，或將結果匯出至匯出批次 01、 （預設批次）。</span><span class="sxs-lookup"><span data-stu-id="b9583-136">From the **Export batch** list, select the batch name or export results to Export batch 01, (the default batch).</span></span> 
    
    - <span data-ttu-id="b9583-p108">若要匯出之新檔案新增至現有案例的結果，繼續執行您目前的批次。批次中建立工作階段、 選取相同的批次數目，並按一下 [**建立匯出工作階段**您可以以累加方式將相同參數匯出成先前的批次，請使用此選項。</span><span class="sxs-lookup"><span data-stu-id="b9583-p108">To export results for new files that you added to an existing case, continue with your current batch. To create a session in the batch, select the same batch number and click **Create export session** You can use this option to export the same parameters as the previous batch, in an incremental manner.</span></span> 
    
    - <span data-ttu-id="b9583-p109">若要匯出至新的批次，請按一下 [**新增**![新增圖示](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)及**批次名稱**] 中輸入新名稱 （或接受預設值） 和**批次描述**中的描述。按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="b9583-p109">To export to a new batch, click **Add** ![add icon](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)and enter a new name in **Batch name** (or accept the default) and a description in **Batch description**. Click **OK**.</span></span>
    
    - <span data-ttu-id="b9583-141">若要編輯的批次名稱或描述，選取中**匯出批次**名稱、 按一下 [**編輯**![編輯圖示](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png)，並修改欄位。</span><span class="sxs-lookup"><span data-stu-id="b9583-141">To edit a batch name or description, select the name in **Export batch**, click **Edit** ![Edit icon](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png), and then modify the fields.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="b9583-p110">您已執行匯出批次的工作階段之後，他們無法刪除。此外，僅部分參數可以編輯之後執行第一個工作階段。</span><span class="sxs-lookup"><span data-stu-id="b9583-p110">After you've run sessions for an export batch, they cannot be deleted. In addition, only some parameters can be edited once the first session is run.</span></span> 
  
    - <span data-ttu-id="b9583-144">若要建立的重複匯出批次，請選擇 [**重複匯出批次**![建立重複匯出批次圖示](media/3f6d5f59-e842-4946-a493-473528af0119.jpg)並在 [控制台] 中輸入名稱和描述的重複的批次。</span><span class="sxs-lookup"><span data-stu-id="b9583-144">To create a duplicate export batch, choose **Duplicate export batch** ![Create a duplicate export batch icon](media/3f6d5f59-e842-4946-a493-473528af0119.jpg) and enter a name and a description for the duplicate batch in the panel.</span></span> 
    
    - <span data-ttu-id="b9583-145">若要刪除匯出批次，請選擇 [**刪除**![刪除匯出批次圖示](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg)。</span><span class="sxs-lookup"><span data-stu-id="b9583-145">To delete an export batch, choose **Delete** ![Delete an export batch icon](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg).</span></span>
    
    - <span data-ttu-id="b9583-146">若要檢視的批次的歷程記錄，請選擇 [**批次歷程記錄**![檢視歷程記錄圖示](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg)。</span><span class="sxs-lookup"><span data-stu-id="b9583-146">To view the history of a batch, choose **Batch history** ![View history icon](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg).</span></span>
    
2. <span data-ttu-id="b9583-147">[**母體**、 選取**包括上方相關性截止分數的檔案**和/或**精選匯出批次**如果您想要微調匯出批次的設定。</span><span class="sxs-lookup"><span data-stu-id="b9583-147">Under **Population**, select **Include only files above Relevance cut-off score** and/or **Refine export batch** if you want to fine-tune the settings for your export batch.</span></span> 
    
3. <span data-ttu-id="b9583-p111">如果您選取 [**包括上方相關性截止分數的檔案**，會啟用**問題**。如果選取問題截止分數大於檔案的相關性分數，除非排除 '供檢閱' 篩選器所要匯出檔案。</span><span class="sxs-lookup"><span data-stu-id="b9583-p111">If you select **Include only files above Relevance cut-off score**, then the **Issue** is enabled. If the file's relevance score is higher than the cut-off score for the selected issue, the file will be exported unless it's excluded by the 'For review' filter.</span></span> 
  
    <span data-ttu-id="b9583-p112">如果您選取 [**精選匯出批次**，**取消 dupe**及篩選所 '檢閱' 欄位選項按鈕隨即啟用。如果您選擇**取消 dupe**，然後重複檔案將會根據所定義的原則來篩選掉 [案例層級 （預設值）： 從重複檔案在整個案例中的每個集，所有但一個檔案將會被取消 duped。Okay 層級： 從重複檔案的相同 okay 每組，所有但一個檔案將會被取消 duped。]匯出輸出中包含所有的重複檔案的記錄。如果您選擇**Filter by '供檢閱'** 欄位，選取 [**修改] 底下的中繼資料**輸入您 **'供檢閱'** 欄位設定。選取要納入套件內容的來源檔案**包含輸入的檔案**。您可以清除此設定可加速匯出程序。請注意會匯出在任何情況下的原生檔案。</span><span class="sxs-lookup"><span data-stu-id="b9583-p112">If you select **Refine export batch**, the **De-dupe** and Filter by 'For review' field radio buttons are enabled. If you choose **De-dupe**, then duplicate files will be filtered out according to the policy defined [Case level (default): from every set of duplicate files in the entire case, all but one file will be de-duped. Custodian level: from every set of duplicate files of the same custodian, all but one file will be de-duped.] The export output contains a record of all duplicate files. If you choose **Filter by 'For review'** field, select **Modify under Metadata** to enter your **'For review'** field settings. Select **Include input files** to include source files in the package content. You can clear this setting to speed up the export process. Note that the Native files will be exported in any case.</span></span> 
    
4. <span data-ttu-id="b9583-157">**中繼資料**、 下選取 [從下列選項中**匯出範本**] 清單中 （一次每個工作階段）。</span><span class="sxs-lookup"><span data-stu-id="b9583-157">Under **Metadata**, select from the following options in the **Export template** list (once per session).</span></span> 
    
    - <span data-ttu-id="b9583-p113">**標準**： 基本組資料的項目、 中繼資料、 及屬性。匯入資料已處理的進階 eDiscovery 並將資料匯出至已包含的檔案系統上傳時使用此選項。根據預設，匯出資料行是建立和填滿的範本。</span><span class="sxs-lookup"><span data-stu-id="b9583-p113">**Standard**: Basic set of data items, metadata, and properties. Use this option when import data was already processed in Advanced eDiscovery and export data is uploaded to a system that already contains the files. By default, export template columns are created and filled.</span></span>
    
    - <span data-ttu-id="b9583-p114">**所有**： 整組包括所有處理資料以及分析與相關性分數的標準中繼資料。此範本時所需進階的 eDiscovery 執行處理及檔案資料上傳至外部系統的第一次。</span><span class="sxs-lookup"><span data-stu-id="b9583-p114">**All**: Full set of standard metadata including all processing data, as well as Analyze and Relevance scores. This template is required when Advanced eDiscovery performs the processing and file data is uploaded to an external system for the first time.</span></span>
    
    - <span data-ttu-id="b9583-163">**問題**： 選取 [**所有問題**] 或都選取您建立的特定問題。</span><span class="sxs-lookup"><span data-stu-id="b9583-163">**Issues**: Select **All Issues** or select a particular issue you have created.</span></span> 
    
5. <span data-ttu-id="b9583-164">在 [**目的地**]：</span><span class="sxs-lookup"><span data-stu-id="b9583-164">Under **Destination**:</span></span>
    
    - <span data-ttu-id="b9583-165">**下載至本機電腦**</span><span class="sxs-lookup"><span data-stu-id="b9583-165">**Download to local machine**</span></span>
    
    - <span data-ttu-id="b9583-166">**匯出至使用者定義的 Azure blob**： 如果這檢查，您可以指定容器 URL 及 SAS 權杖。</span><span class="sxs-lookup"><span data-stu-id="b9583-166">**Export to user-defined Azure blob**: If this is checked, you can specify a container URL and SAS token.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="b9583-p115">一旦匯出套件儲存至使用者定義的 Azure blob、 進階 eDiscovery ； 不再管理資料它被管理 Azure blob。這表示如果您刪除案例，匯出的檔案仍會維持在 Azure blob。</span><span class="sxs-lookup"><span data-stu-id="b9583-p115">Once an export package is stored to the user defined Azure blob, the data is no longer managed by Advanced eDiscovery; it's managed by the Azure blob. This means if you delete the case, the exported files will still remain on the Azure blob.</span></span> 
  
    - <span data-ttu-id="b9583-169">**儲存 SAS 權杖未來匯出工作階段**： 如果檢查，要 SAS 權杖加密供日後使用進階的 eDiscovery 內部資料庫中。</span><span class="sxs-lookup"><span data-stu-id="b9583-169">**Save SAS token for future export session**: If checked, the SAS token will be encrypted in the Advanced eDiscovery's internal database for future use.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="b9583-p116">目前 SAS 權杖會在每個月後到期。如果您嘗試下載您要復原最後一個工作階段有多個月之後，然後再次匯出。</span><span class="sxs-lookup"><span data-stu-id="b9583-p116">Currently the SAS token expires after a month. If you try to download after more than a month you have to undo last session, then export again.</span></span> 
  
6. <span data-ttu-id="b9583-172">按一下 [**修改**設定 '供檢閱' 欄位設定]。</span><span class="sxs-lookup"><span data-stu-id="b9583-172">Click **Modify** to set the 'for review' field settings.</span></span> 
    
    ![匯出批次的檢閱欄位設定為設定](media/39451aba-f6fe-4a01-8ed0-0be6a6ce889a.png)
  
   - <span data-ttu-id="b9583-p117">[**檢閱] 欄位設定**、**選取案例**下拉清單中，選取案例和範圍的檢閱。根據您的選取範圍會顯示設定。</span><span class="sxs-lookup"><span data-stu-id="b9583-p117">Under **For review field settings**, in **Select scenario** pull-down list, select the scenario and scope of the review. The settings are displayed based on your selection.</span></span>
    
      - <span data-ttu-id="b9583-176">**檢閱所有**（預設值）： 預設選取所有的電子郵件、 附件及文件。</span><span class="sxs-lookup"><span data-stu-id="b9583-176">**Review all** (default): All emails, attachments, and documents are selected by default.</span></span> 
    
      - <span data-ttu-id="b9583-177">**檢閱一組中的所有唯一內容**： 電子郵件中的唯一附件 Inclusives 及唯一 （含） 的副本，設定層級、 代表性完全重複的每一組。</span><span class="sxs-lookup"><span data-stu-id="b9583-177">**Review all unique content in a set**: Inclusives and unique inclusive copies, unique attachments in email set level, representative from every set of exact duplicates.</span></span>
    
      - <span data-ttu-id="b9583-178">**檢閱一組-無 （含） 的複本中的所有唯一內容**： Inclusives、 電子郵件中的唯一附件設定層級、 代表性完全重複的每一組。</span><span class="sxs-lookup"><span data-stu-id="b9583-178">**Review all unique content in a set - no inclusive copies**: Inclusives, unique attachments in email set level, representative from every set of exact duplicates.</span></span>
    
      - <span data-ttu-id="b9583-179">**檢閱所有唯一內容及相關系列檔**： Inclusives、 電子郵件設定層級、 服務代表洽談完全重複的每一組中的唯一附件展開到包含系列的檔案。</span><span class="sxs-lookup"><span data-stu-id="b9583-179">**Review all unique content and related family files**: Inclusives, unique attachments in email set level, representative from every set of exact duplicates, expand to include family files.</span></span>
    
      - <span data-ttu-id="b9583-p118">**自訂**（可讓您定義的選項] 對話方塊中）： 預設會保留目前的選取項目並啟用所有的對話方塊選項，允許其選取項目。如果您選取這個選項，然後自訂 [電子郵件、 文件、 附件的設定及其他。</span><span class="sxs-lookup"><span data-stu-id="b9583-p118">**Custom** (allows you to define the options in the dialog): The default is to keep current selections and enable all dialog options, to allow their selection. If you select this option, you can then customize the settings for emails, documents, attachments and miscellaneous.</span></span>
    
    - <span data-ttu-id="b9583-182">在 [**電子郵件**，選取您想要匯出的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="b9583-182">Under **Emails**, select the emails you want to export.</span></span>
    
      - <span data-ttu-id="b9583-183">**所有電子郵件**： （預設值） 不會選取所有的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="b9583-183">**All emails**: (default) All emails are selected.</span></span>
    
      - <span data-ttu-id="b9583-184">**Inclusives**: （含） 的電子郵件執行緒的最後一個電子郵件而且它包含所有其他電子郵件從執行緒。</span><span class="sxs-lookup"><span data-stu-id="b9583-184">**Inclusives**: An inclusive email is a last email of a thread, and it contains all the other emails from the thread.</span></span>
    
      - <span data-ttu-id="b9583-185">**Inclusives 和唯一的 （含） 副本**: （含） 的複本，並具有相同的主旨、 本文和附件; inclusives唯一的 （含） 副本是唯一的這些電子郵件的複本。</span><span class="sxs-lookup"><span data-stu-id="b9583-185">**Inclusives and unique inclusive copies**: Inclusive copies and inclusives with the same subject, body and attachments; unique inclusive copies are unique copies of these emails .</span></span>
    
    - <span data-ttu-id="b9583-186">在 [**文件**選取您想要匯出的文件。</span><span class="sxs-lookup"><span data-stu-id="b9583-186">Under **Documents**, select the documents you want to export.</span></span> 
    
      - <span data-ttu-id="b9583-187">**所有文件**： （預設值） 會選取所有文件。</span><span class="sxs-lookup"><span data-stu-id="b9583-187">**All documents**: (default) All documents are selected.</span></span>
    
      - <span data-ttu-id="b9583-188">**樞紐分析表**： 選擇作為代表性接近重複項目組，通常用於當做基準檢閱集的檔案。</span><span class="sxs-lookup"><span data-stu-id="b9583-188">**Pivots**: A file chosen as representative of near-duplicates set, which is typically used as the baseline when reviewing the set.</span></span>
    
      - <span data-ttu-id="b9583-189">**從完全重複每組代表性**： 唯一接近重複檔案 （包括 [樞紐分析表）。</span><span class="sxs-lookup"><span data-stu-id="b9583-189">**Representative from every set of exact duplicates**: Unique near-duplicate files (including the pivot).</span></span>
    
    - <span data-ttu-id="b9583-190">在 [**附件**，選取您想要匯出的附件。</span><span class="sxs-lookup"><span data-stu-id="b9583-190">Under **Attachments**, select the attachments you want to export.</span></span> 
    
      - <span data-ttu-id="b9583-191">**所有附件**: （預設值） 會選取所有附件。</span><span class="sxs-lookup"><span data-stu-id="b9583-191">**All attachments**: (default) All attachments are selected.</span></span>
    
      - <span data-ttu-id="b9583-192">**在案例層級的唯一附件**： 中指定之案例的唯一的附件檔案。</span><span class="sxs-lookup"><span data-stu-id="b9583-192">**Unique attachment in case level**: Unique attachment files within the specified case.</span></span>
    
      - <span data-ttu-id="b9583-193">**電子郵件中的唯一附件設定層級**： 中指定的電子郵件案例的唯一的附件檔案。</span><span class="sxs-lookup"><span data-stu-id="b9583-193">**Unique attachment in email set level**: Unique attachment files within the specified email case.</span></span>
    
   - <span data-ttu-id="b9583-p119">下**Micellaneous**，您可以選擇**將附件文件**、**將文件的電子郵件**，或**展開包含系列的檔案**。當您選擇**展開包含系列檔案**，檢閱標幟的每個檔案時，也會標示相同系列的所有檔案。</span><span class="sxs-lookup"><span data-stu-id="b9583-p119">Under**Micellaneous**, you can choose to **Treat attachments as documents**, **Treat emails as documents**, or **Expand to include family files**. When you choose **Expand to include family files**, for each file that is flagged for review, all files of the same family will also be flagged.</span></span>
    
7. <span data-ttu-id="b9583-196">選擇 [**儲存**] 以儲存設定。</span><span class="sxs-lookup"><span data-stu-id="b9583-196">Choose **Save** to save the settings.</span></span> 
    
8. <span data-ttu-id="b9583-197">指定匯出參數後，啟動匯出批次，請按一下 [**建立匯出工作階段**]。</span><span class="sxs-lookup"><span data-stu-id="b9583-197">After you specify export parameters, to start export batch, click **Create export session**.</span></span>
    
    <span data-ttu-id="b9583-p120">在匯出期間狀態會顯示在 [**工作狀態**。結果會顯示在**匯出摘要**。</span><span class="sxs-lookup"><span data-stu-id="b9583-p120">During export, the status is displayed in **Task status**. The results are displayed in **Export summary**.</span></span>
    
9. <span data-ttu-id="b9583-200">在 [**檔案下載**] 視窗中，按一下 [**複製到剪貼簿**複製匯出金鑰]。</span><span class="sxs-lookup"><span data-stu-id="b9583-200">In the **Download files** window, click **Copy to clipboard** to copy the Export key.</span></span> 
    
    ![下載檔案](media/99cf2c13-4954-479f-9741-80d7458c1a15.png)
  
10. <span data-ttu-id="b9583-202">按一下 [關閉]。</span><span class="sxs-lookup"><span data-stu-id="b9583-202">Click **Close**.</span></span> 
    
    <span data-ttu-id="b9583-203">啟動 eDiscovery 匯出工具。</span><span class="sxs-lookup"><span data-stu-id="b9583-203">The eDiscovery Export Tool is started.</span></span>
    
    ![eDiscovery 匯出工具](media/705756ca-ee97-4d24-b70f-8b23513f6d11.gif)
  
11. <span data-ttu-id="b9583-205">**EDiscovery 匯出工具**：</span><span class="sxs-lookup"><span data-stu-id="b9583-205">In the **eDiscovery Export Tool**:</span></span>
    
    -  <span data-ttu-id="b9583-206">在**貼上共用存取簽章的會用來連線至來源**，在步驟 7 中該 youcopied 到剪貼簿貼入匯出金鑰。</span><span class="sxs-lookup"><span data-stu-id="b9583-206">In **Paste the Shared Access Signature that will be used to connect to the source**, paste the Export key that youcopied to the clipboard in step 7.</span></span>
    
    - <span data-ttu-id="b9583-207">按一下 [**瀏覽**至選取的儲存在本機電腦上的已下載的匯出檔案的目標位置。</span><span class="sxs-lookup"><span data-stu-id="b9583-207">Click **Browse** to select the target location for storing the downloaded export files on the local machine.</span></span> 
    
    - <span data-ttu-id="b9583-p121">按一下 [**啟動**]。匯出檔案下載至本機電腦。如果您在步驟 4 中選擇**匯出至使用者定義的 Azure blob** ，工作階段匯出至您選擇的 Blob 存放區 URL 目的地。</span><span class="sxs-lookup"><span data-stu-id="b9583-p121">Click **Start**.The export files are downloaded to the local machine. If you chose **Export to user-defined Azure blob** in step 4, the session is exported to a Blob storage URL destination of your choosing.</span></span>
    
<span data-ttu-id="b9583-210">匯出報表中的欄位的完整說明，請參閱[匯出報表欄位](export-report-fields-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="b9583-210">For a full description of the fields in the export report, see [Export report fields](export-report-fields-in-advanced-ediscovery.md).</span></span>
  
## <a name="export-report-output-files"></a><span data-ttu-id="b9583-211">匯出報告輸出檔案</span><span class="sxs-lookup"><span data-stu-id="b9583-211">Export report output files</span></span>
<span data-ttu-id="b9583-212"><a name="BK_ExportOutputFIles"> </a></span><span class="sxs-lookup"><span data-stu-id="b9583-212"></span></span>

<span data-ttu-id="b9583-213">下表列出當您執行匯出批次時所產生的輸出檔。</span><span class="sxs-lookup"><span data-stu-id="b9583-213">The following table lists the output files that are generated when you run an Export batch.</span></span>
  
|<span data-ttu-id="b9583-214">**檔案名稱**</span><span class="sxs-lookup"><span data-stu-id="b9583-214">**File name**</span></span>|<span data-ttu-id="b9583-215">**檔案類型**</span><span class="sxs-lookup"><span data-stu-id="b9583-215">**File type**</span></span>|<span data-ttu-id="b9583-216">**描述**</span><span class="sxs-lookup"><span data-stu-id="b9583-216">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b9583-217">匯出摘要</span><span class="sxs-lookup"><span data-stu-id="b9583-217">Export summary</span></span>  <br/> |<span data-ttu-id="b9583-218">csv</span><span class="sxs-lookup"><span data-stu-id="b9583-218">csv</span></span>  <br/> |<span data-ttu-id="b9583-219">EDiscovery 匯出工具所產生的記錄檔。</span><span class="sxs-lookup"><span data-stu-id="b9583-219">A log file generated by the eDiscovery Export Tool.</span></span>  <br/> |
|<span data-ttu-id="b9583-220">追蹤</span><span class="sxs-lookup"><span data-stu-id="b9583-220">Trace</span></span>  <br/> |<span data-ttu-id="b9583-221">txt</span><span class="sxs-lookup"><span data-stu-id="b9583-221">txt</span></span>  <br/> |<span data-ttu-id="b9583-222">EDiscovery 匯出工具所產生的記錄檔。</span><span class="sxs-lookup"><span data-stu-id="b9583-222">A log file generated by the eDiscovery Export Tool.</span></span>  <br/> |
|<span data-ttu-id="b9583-223">解壓縮的文字檔案</span><span class="sxs-lookup"><span data-stu-id="b9583-223">Extracted text files</span></span>  <br/> |<span data-ttu-id="b9583-224">檔案資料夾</span><span class="sxs-lookup"><span data-stu-id="b9583-224">File folder</span></span>  <br/> |<span data-ttu-id="b9583-225">包含匯出的檔案解壓縮的文字檔案的資料夾。</span><span class="sxs-lookup"><span data-stu-id="b9583-225">Folder that contains the extracted text files of the exported files.</span></span>  <br/> |
|<span data-ttu-id="b9583-226">輸入或原生檔案</span><span class="sxs-lookup"><span data-stu-id="b9583-226">Input or native files</span></span>  <br/> |<span data-ttu-id="b9583-227">檔案資料夾</span><span class="sxs-lookup"><span data-stu-id="b9583-227">File folder</span></span>  <br/> |<span data-ttu-id="b9583-228">包含原生和輸入檔案的匯出檔案的資料夾。</span><span class="sxs-lookup"><span data-stu-id="b9583-228">Folder that contains the native and input files of the exported files.</span></span>  <br/> |
|<span data-ttu-id="b9583-229">將清單匯出</span><span class="sxs-lookup"><span data-stu-id="b9583-229">Export list</span></span>  <br/> |<span data-ttu-id="b9583-230">xlsx</span><span class="sxs-lookup"><span data-stu-id="b9583-230">xlsx</span></span>  <br/> |<span data-ttu-id="b9583-p122">Xlsx 格式匯出的檔案中繼資料。在檔案中的欄位會根據範本使用者選取来匯出。必要時，建立一些檔案、 每個包含 100-150 K 資料列。如果特定值包含超過為 Excel 儲存格可以包含多個字元 （目前的限制為 32767 個字元），則此值將會調整以允許的最大長度。如果值調整、 儲存格的背景色彩為紅色這表示使用者。 」電子郵件參與者"，則可以超過長度限制，欄位的範例電子郵件傳送給大型通訊群組。如需詳細資訊輸出欄位，請參閱[匯出報表欄位](export-report-fields-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="b9583-p122">Exported files metadata in xlsx format. Fields in files are according to template user selects to export. If needed, several files are created, each contains 100-150K rows. If a certain value contains more characters than an Excel cell can contain (currently the limit is 32,767 characters), then the value will be trimmed to the maximum length allowed. If a value is trimmed, the cell's background color is red to indicate this to the user."Email participants" is an example of a field that can exceed the length limit, if the email was sent to a large distribution. See [Export report fields](export-report-fields-in-advanced-ediscovery.md) for details about the output fields.  </span></span><br/> |
|<span data-ttu-id="b9583-237">載入檔案</span><span class="sxs-lookup"><span data-stu-id="b9583-237">Load file</span></span>  <br/> |<span data-ttu-id="b9583-238">csv</span><span class="sxs-lookup"><span data-stu-id="b9583-238">csv</span></span>  <br/> |<span data-ttu-id="b9583-p123">匯出的檔案中繼資料載入到不同的應用程式的 csv 格式。在檔案中的欄位會根據範本使用者選取来匯出。</span><span class="sxs-lookup"><span data-stu-id="b9583-p123">Exported files metadata in csv format for loading into a different application. Fields in files are according to template user selects to export.</span></span>  <br/> |
|<span data-ttu-id="b9583-241">成功標記</span><span class="sxs-lookup"><span data-stu-id="b9583-241">Success indicator</span></span>  <br/> |<span data-ttu-id="b9583-242">txt</span><span class="sxs-lookup"><span data-stu-id="b9583-242">txt</span></span>  <br/> |<span data-ttu-id="b9583-p124">只建立匯出至第 3 協力廠商對 Azure blob 時。如果匯出完全成功，就會建立該檔案。發生失敗，或部分將不會建立成功檔案。檔案會建立在根資料夾中允許在不同的匯出批次/工作階段狀態的自動的追蹤。這是空的檔案。其名稱是： TenantId_CaseId_ExternalCaseId_CaseName_ExportBatchId_SessionId_DateTime.txt。</span><span class="sxs-lookup"><span data-stu-id="b9583-p124">Only created when exporting to a 3rd party Azure blob. If export succeed completely, the file will be created. In case of failure, or partial success the file will not be created. File will be created in the root folder, allowing automated tracking on different Export batches/sessions statuses. This is an empty file. Its name is: TenantId_CaseId_ExternalCaseId_CaseName_ExportBatchId_SessionId_DateTime.txt.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="b9583-249">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b9583-249">See also</span></span>

[<span data-ttu-id="b9583-250">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="b9583-250">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="b9583-251">檢視批次歷程記錄和匯出過去的結果</span><span class="sxs-lookup"><span data-stu-id="b9583-251">Viewing batch history and exporting past results</span></span>](view-batch-history-and-export-past-results.md)
  
[<span data-ttu-id="b9583-252">快速設定 Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="b9583-252">Quick setup for Office 365 Advanced eDiscovery</span></span>](quick-setup-for-advanced-ediscovery.md)

[<span data-ttu-id="b9583-253">匯出報告欄位</span><span class="sxs-lookup"><span data-stu-id="b9583-253">Export report fields</span></span>](export-report-fields-in-advanced-ediscovery.md)
  
[<span data-ttu-id="b9583-254">匯出 eDiscovery 搜尋結果從 Office 365 時所增加的下載速度</span><span class="sxs-lookup"><span data-stu-id="b9583-254">Increase the download speed when exporting eDiscovery search results from Office 365</span></span>](increase-download-speeds-when-exporting-ediscovery-results.md)

