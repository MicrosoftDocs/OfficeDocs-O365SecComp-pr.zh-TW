---
title: 在 Office 365 進階電子文件探索中執行處理程序模組及載入資料
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c87bb0e5-301c-4d1d-958e-aabeb7990f44
description: '了解如何使用 Office 365 安全性&amp;規範中心以存取 Office 365 進階 eDiscovery 及執行程序模組中的案例。  '
ms.openlocfilehash: 95c73c034ed2ffa1c45f9aacd8463c497a842859
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217603"
---
# <a name="run-the-process-module-and-load-data-in-office-365-advanced-ediscovery"></a><span data-ttu-id="01820-103">在 Office 365 進階電子文件探索中執行處理程序模組及載入資料</span><span class="sxs-lookup"><span data-stu-id="01820-103">Run the Process module and load data in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="01820-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="01820-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="01820-106">本節中的 [進階的 eDiscovery 程序模組的功能。</span><span class="sxs-lookup"><span data-stu-id="01820-106">This section describes the functionality of the Advanced eDiscovery Process module.</span></span> 
  
<span data-ttu-id="01820-p102">除了檔案資料檔案類型、 副檔名、 位置或路徑、 建立日期及時間、 author、 okay、 和主旨等的中繼資料可以載入至進階 eDiscovery 及儲存的每個案例。有些中繼資料會計算進階 eDiscovery，例如原生檔案會載入時。</span><span class="sxs-lookup"><span data-stu-id="01820-p102">In addition to file data, metadata such as file type, extension, location or path, creation date and time, author, custodian, and subject, can be loaded into Advanced eDiscovery and saved for each case. Some metadata is calculated by Advanced eDiscovery, for example, when native files are loaded.</span></span> 
  
<span data-ttu-id="01820-p103">進階的 eDiscovery 提供系統的中繼資料值，例如接近重複群組或相關性分數。由系統管理員就可以新增其他中繼資料，例如檔案註釋。</span><span class="sxs-lookup"><span data-stu-id="01820-p103">Advanced eDiscovery provides system metadata values, such as Near-duplicate groupings or Relevance scores. Other metadata, such as file annotations, can be added by the Administrator.</span></span> 
  
## <a name="running-process"></a><span data-ttu-id="01820-111">執行程序</span><span class="sxs-lookup"><span data-stu-id="01820-111">Running Process</span></span>

> [!NOTE]
> <span data-ttu-id="01820-p104">批次指派編號檔案程序期間允許的檔案追蹤。批次數目也可讓重新處理選項的程序批次的識別。其他篩選器可用來篩選的批次數目和工作階段。</span><span class="sxs-lookup"><span data-stu-id="01820-p104">Batch numbers are assigned to a file during Process to allow the tracking of files. The batch number also enables identification of Process batches for reprocessing options. Additional filters are available for filtering by batch number and sessions.</span></span> 
  
<span data-ttu-id="01820-115">請執行下列步驟來執行程序。</span><span class="sxs-lookup"><span data-stu-id="01820-115">Perform the following steps to run Process.</span></span>
  
1. <span data-ttu-id="01820-116">[開啟的 Office 365 安全性&amp;規範中心](go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="01820-116">[Open the Office 365 Security &amp; Compliance Center](go-to-the-securitycompliance-center.md) .</span></span> 
    
2. <span data-ttu-id="01820-117">移至 [**搜尋&amp;調查** \> **eDiscovery** ] 和 [**移至 [進階 eDiscovery**。</span><span class="sxs-lookup"><span data-stu-id="01820-117">Go to **Search &amp; investigation** \> **eDiscovery** and then click **Go to Advanced eDiscovery**.</span></span>
    
3. <span data-ttu-id="01820-118">進階 eDiscovery 中選取適當的案例中顯示的**情況下**] 頁面上，按一下 [**移至 [大小寫**。</span><span class="sxs-lookup"><span data-stu-id="01820-118">In Advanced eDiscovery, select the appropriate case in the displayed **Cases** page and click **Go to case**.</span></span>
    
4. <span data-ttu-id="01820-119">在 [**準備** \> **程序** \> **安裝程式**、 選取清單中的可用容器的容器。</span><span class="sxs-lookup"><span data-stu-id="01820-119">In **Prepare** \> **Process** \> **Setup**, select a container from the list of available containers.</span></span>
    
    ![按一下 [新增至大小寫的搜尋結果的程序](media/50bdc55c-d378-4881-b302-31ef785fa359.png)
  
5. <span data-ttu-id="01820-121">如果您想要作為植入的檔案或前標記檔案新增容器，請按一下 [**進階設定...** ]。</span><span class="sxs-lookup"><span data-stu-id="01820-121">Click **Advanced settings...** if you want to add the container as seed files or as pre-tagged files.</span></span> 
    
    <span data-ttu-id="01820-p105">使用加速問題的訓練與低豐富植入的檔案 (通常是 2%或更少)。針對植入的檔案，建議您選取各種確定相關的檔案和程序的相關 20 50 種子個別 （太多植入檔案可以扭曲相關性結果） 的問題。將訓練問題相同者所應該檢閱植入的檔案。</span><span class="sxs-lookup"><span data-stu-id="01820-p105">Use seed files to accelerate training for issues with low richness (usually 2%, or less). For seed files, it is recommended that you select a variety of distinctly relevant files and process about 20-50 seeds per issue (too many seed files can skew Relevance results). Seed files should be reviewed by the same person who will train the issue.</span></span>
    
    <span data-ttu-id="01820-p106">使用預先標記的檔案來自動化相關性訓練。您應該標記至少 1500 檔案，並保持的非相關的檔案與圖形成比例集合新增至相關性相同。這些檔案應該手動標記，以及您應該有信心以標記的品質。</span><span class="sxs-lookup"><span data-stu-id="01820-p106">Use pre-tagged files to automate Relevance training. You should tag at least 1,500 files, and keep the proportion of relevant to non-relevant files the same as in the collection added to Relevance. These files should be manually tagged, and you should be confident in the quality of tagging.</span></span>
    
    ![這個螢幕擷取畫面的進階設定] 頁面上處理批次檔案](media/3c25cb78-4484-41e5-bd34-3753c7ab6cf2.jpg)
  
  - <span data-ttu-id="01820-129">在 [**植入**] 區段中：</span><span class="sxs-lookup"><span data-stu-id="01820-129">In the **Seed** section:</span></span> 
    
    <span data-ttu-id="01820-p107">選擇 [**標示為植入的檔案**，將容器標示為植入的檔案。您也需要選擇將它們從**問題**下拉式指派每個問題。從**標籤**] 下拉式清單中選擇**相關**或**不相關**。</span><span class="sxs-lookup"><span data-stu-id="01820-p107">Choose **Mark as seed files** to mark the container as seed files. You also need choose to assign them per issue from the **For issue** drop-down. Choose either **Relevant** or **Not relevant** from the **Tag** drop-down.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="01820-133">一旦您作為**植入**設定檔，您無法將它們標示為**預先標記**。</span><span class="sxs-lookup"><span data-stu-id="01820-133">Once you set files as **Seed**, you cannot mark them as **Pre-tagged**.</span></span> 
  
  - <span data-ttu-id="01820-134">在 [**預先標記的檔案**] 區段中：</span><span class="sxs-lookup"><span data-stu-id="01820-134">In the **Pre-tagged files** section:</span></span> 
    
    <span data-ttu-id="01820-p108">選擇 [**標示為預先標記檔案**標示為預先標記檔案的容器。您也需要將它們從**問題**下拉式指派每個問題。從**標籤**] 下拉式清單中選擇**相關**或**不相關**。</span><span class="sxs-lookup"><span data-stu-id="01820-p108">Choose **Mark as pre-tagged files** to mark the container as pre-tagged files. You also need to assign them per issue from the **For issue** drop-down. Choose either **Relevant** or **Not relevant** from the **Tag** drop-down.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="01820-138">一旦您為**預先標記**設定檔，您無法將其標示為**植入**。</span><span class="sxs-lookup"><span data-stu-id="01820-138">Once you set files as **Pre-tagged**, you cannot mark them as **Seed**.</span></span> 
  
  - <span data-ttu-id="01820-p109">在 [**電子郵件標記**] 區段中。已處理的電子郵件的哪一部分要標示為植入或前已標記的設定。</span><span class="sxs-lookup"><span data-stu-id="01820-p109">In the **Email tagging** section. set which part of a processed email are to be marked as Seed or Pre-tagged.</span></span> 
    
6. <span data-ttu-id="01820-p110">若要開始，按一下 [**程序**。完成時，會顯示的程序結果。</span><span class="sxs-lookup"><span data-stu-id="01820-p110">To begin, click **Process**. When completed, the Process results are displayed.</span></span>
    
7. <span data-ttu-id="01820-143">（選用）如果您需要將指派給特定 okay 的資料來源，您可以新增和編輯中**Custodians** okay 名稱\> **Custodians**中的**管理**] 和 [指派 custodians \> **指派**。</span><span class="sxs-lookup"><span data-stu-id="01820-143">(Optional) If you need to assign data sources to a specific custodian, you can add and edit custodian names in **Custodians** \> **Manage** and assign custodians in **Custodians** \> **Assign**.</span></span> 
    
<span data-ttu-id="01820-144">如果您新增至案例，然後您可以處理一次。</span><span class="sxs-lookup"><span data-stu-id="01820-144">If you add to the case, then you can process again.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="01820-145">另請參閱</span><span class="sxs-lookup"><span data-stu-id="01820-145">See also</span></span>

[<span data-ttu-id="01820-146">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="01820-146">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="01820-147">檢視程序模組結果</span><span class="sxs-lookup"><span data-stu-id="01820-147">Viewing Process module results</span></span>](view-process-module-results-in-advanced-ediscovery.md)

