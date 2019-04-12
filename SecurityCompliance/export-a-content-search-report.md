---
title: 匯出內容搜尋報告
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExportReport
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9
description: 而不是匯出實際的安全性 & 在 Office 365 規範中心中的內容搜尋結果，您可以只匯出搜尋結果報告。 報告中包含搜尋結果和詳細資訊，會匯出每個項目的相關文件的摘要。
ms.openlocfilehash: 57c8a9be5c53998570f6ff15a49df69e27745e26
ms.sourcegitcommit: 6c9340e4eb221bf81472ff3f1ae25ae21aaf5297
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/11/2019
ms.locfileid: "31813924"
---
# <a name="export-a-content-search-report"></a><span data-ttu-id="e7ffe-104">匯出內容搜尋報告</span><span class="sxs-lookup"><span data-stu-id="e7ffe-104">Export a Content Search report</span></span>

<span data-ttu-id="e7ffe-105">而不是匯出搜尋結果一組完整的安全性 & 合規性中心中的內容搜尋從 （和內容搜尋與 eDiscovery 案例相關聯），您可以只匯出您匯出搜尋時，要產生相同報告結果。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-105">Instead of exporting the full set of search results from a Content Search in the Security & Compliance Center (and from a Content Search that's associated with an eDiscovery case), you can just export the same reports that are generated when you export search results.</span></span>
  
<span data-ttu-id="e7ffe-106">當您匯出報告時，它會下載至具有相同名稱內容搜尋，但，後面會加 *_ReportsOnly*資料夾。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-106">When you export a report, it's downloaded to a folder that has the same name as the Content Search, but that's appended with  *_ReportsOnly*  .</span></span> <span data-ttu-id="e7ffe-107">例如，如果內容搜尋名稱為*ContosoCase0815* ，報表會下載至名為*ContosoCase0815_ReportsOnly*的資料夾。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-107">For example, if the Content Search is named  *ContosoCase0815*  , then the report is downloaded to a folder named  *ContosoCase0815_ReportsOnly*  .</span></span> <span data-ttu-id="e7ffe-108">報告中包含的文件清單，請參閱[在報告中包含的內容](#whats-included-in-the-report)。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-108">For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e7ffe-109">開始之前</span><span class="sxs-lookup"><span data-stu-id="e7ffe-109">Before you begin</span></span>

- <span data-ttu-id="e7ffe-110">若要匯出內容搜尋報告，您必須獲指派 「 安全性 & 合規性中心中的符合性搜尋管理角色。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-110">To export a Content Search report, you have to be assigned the Compliance Search management role in the Security & Compliance Center.</span></span> <span data-ttu-id="e7ffe-111">此角色指派至內建的 eDiscovery 管理員與組織管理角色群組。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-111">This role is assigned to the built-in eDiscovery Manager and Organization Management role groups.</span></span> <span data-ttu-id="e7ffe-112">它不是由預設指派給 「 組織管理 」 角色群組。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-112">It isn't assigned by default to the Organization Management role group.</span></span> <span data-ttu-id="e7ffe-113">如需詳細資訊，請參閱[指派 eDiscovery 權限](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-113">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="e7ffe-114">當您匯出報告時，資料會暫時儲存在 Microsoft cloud 中的唯一 Windows Azure 存放區域之前就會下載到本機電腦。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-114">When you export a report, the data is temporarily stored in a unique Windows Azure storage area in the Microsoft cloud before it's downloaded to your local computer.</span></span> <span data-ttu-id="e7ffe-115">確定您的組織可以連線到 Azure，也就是在端點**\*。 blob.core.windows.net** （萬用字元代表您匯出的唯一識別碼）。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-115">Be sure your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export).</span></span> <span data-ttu-id="e7ffe-116">建立後的兩週時，會從 Azure 存放區刪除搜尋結果資料。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-116">The search results data is deleted from the Azure storage area two weeks after it's created.</span></span> 
    
- <span data-ttu-id="e7ffe-117">您用來匯出搜尋結果的電腦必須符合下列系統需求：</span><span class="sxs-lookup"><span data-stu-id="e7ffe-117">The computer you use to export the search results has to meet the following system requirements:</span></span>
    
  - <span data-ttu-id="e7ffe-118">32 位元或 64 位元版本的 Windows 7 和更新版本</span><span class="sxs-lookup"><span data-stu-id="e7ffe-118">32- or 64-bit versions of Windows 7 and later versions</span></span>
    
  - <span data-ttu-id="e7ffe-119">Microsoft.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="e7ffe-119">Microsoft .NET Framework 4.7</span></span>
    
  - <span data-ttu-id="e7ffe-120">支援的瀏覽器：</span><span class="sxs-lookup"><span data-stu-id="e7ffe-120">A supported browser:</span></span>
    
    - <span data-ttu-id="e7ffe-121">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="e7ffe-121">Microsoft Edge</span></span>
    
      <span data-ttu-id="e7ffe-122">或</span><span class="sxs-lookup"><span data-stu-id="e7ffe-122">or</span></span>
    
    - <span data-ttu-id="e7ffe-123">Microsoft Internet Explorer 10 或更新版本</span><span class="sxs-lookup"><span data-stu-id="e7ffe-123">Microsoft Internet Explorer 10 and later versions</span></span>
    
    <span data-ttu-id="e7ffe-124">**附註：** Microsoft 不會製造廠商分機或 ClickOnce 應用程式的附加元件。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-124">**Note:** Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications.</span></span> <span data-ttu-id="e7ffe-125">不支援匯出不受支援的瀏覽器使用協力廠商分機或附加元件的搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-125">Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span> 

- <span data-ttu-id="e7ffe-126">如果內容搜尋所傳回的結果估計總大小超過 20 個&nbsp;TB，匯出報告將會失敗。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-126">If the estimated total size of the results returned by a Content Search exceeds 20&nbsp;TB, exporting the report will fail.</span></span> <span data-ttu-id="e7ffe-127">若要成功匯出報告，請嘗試以縮小範圍，然後重新執行搜尋，因此評估的結果的大小會小於 20&nbsp;TB。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-127">To successfully export the report, try to narrow the scope and re-run the search so the estimated size of the results is less than 20&nbsp;TB.</span></span>

- <span data-ttu-id="e7ffe-128">匯出內容搜尋報告針對匯出執行在同一時間和匯出單一使用者可以執行的最大數目的最大數目的計數。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-128">Exporting Content Search reports counts against the maximum number of exports running at the same time and the maximum number of exports that a single user can run.</span></span> <span data-ttu-id="e7ffe-129">如需匯出限制的詳細資訊，請參閱[匯出內容搜尋結果](export-search-results.md#export-limits)。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-129">For more information about export limits, see [Export Content Search results](export-search-results.md#export-limits).</span></span>

## <a name="generate-and-download-a-content-search-report"></a><span data-ttu-id="e7ffe-130">產生與下載內容搜尋報告</span><span class="sxs-lookup"><span data-stu-id="e7ffe-130">Generate and download a Content Search report</span></span>

<span data-ttu-id="e7ffe-131">若要產生並下載內容搜尋報告的步驟是非常類似於實際匯出搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-131">The steps to generate and download a Content Search report are very similar to actually exporting search results.</span></span>
  
## <a name="step-1-generate-the-report-for-export"></a><span data-ttu-id="e7ffe-132">步驟 1： 產生匯出的報告</span><span class="sxs-lookup"><span data-stu-id="e7ffe-132">Step 1: Generate the report for export</span></span>

<span data-ttu-id="e7ffe-133">第一個步驟是準備下載至您的電腦匯出報告。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-133">The first step is to prepare the report for downloading to your computer exporting.</span></span> <span data-ttu-id="e7ffe-134">當您報表，報表文件上傳至 Azure 存放裝置區域中的 microsoft 雲端。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-134">When you the report, the report documents are uploaded to an Azure storage area in the Microsoft cloud.</span></span>
  
1. <span data-ttu-id="e7ffe-135">移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-135">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="e7ffe-136">使用公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-136">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="e7ffe-137">在 [安全性 & 合規性中心的左窗格中，按一下 [**搜尋** \> **內容搜尋**。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-137">In the left pane of the Security & Compliance Center, click **Search** \> **Content search**.</span></span>
    
4. <span data-ttu-id="e7ffe-138">在 [**內容搜尋**] 頁面上，選取搜尋。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-138">On the **Content search** page, select a search.</span></span> 
    
5. <span data-ttu-id="e7ffe-139">在 [詳細資料] 窗格中，[**匯出至電腦的報告**，請按一下 [**產生報表**。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-139">In the details pane, under **Export report to a computer**, click **Generate report**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e7ffe-140">如果搜尋結果超過 7 天，系統會提示您更新搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-140">If the results for a search are older than 7 days, you are prompted to update the search results.</span></span> <span data-ttu-id="e7ffe-141">如果發生這種情況，取消匯出、 選取搜尋詳細資料窗格中按一下 [**更新搜尋結果**，並更新結果之後再開始執行報表匯出。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-141">If this happens, cancel the export, click **Update search results** in the details pane for the selected search, and then start the report export again after the results are updated.</span></span> 
  
6. <span data-ttu-id="e7ffe-142">在**匯出報告**] 頁面的 [**包含從搜尋這些項目**，請選擇下列選項之一：</span><span class="sxs-lookup"><span data-stu-id="e7ffe-142">On the **Export a report** page, under **Include these items from the search**, choose one of the following options:</span></span>
    
    - <span data-ttu-id="e7ffe-143">匯出已編製索引的項目</span><span class="sxs-lookup"><span data-stu-id="e7ffe-143">Export only indexed items</span></span>
    
    - <span data-ttu-id="e7ffe-144">匯出已編製索引和未編製索引的項目</span><span class="sxs-lookup"><span data-stu-id="e7ffe-144">Export indexed and unindexed items</span></span>
    
    - <span data-ttu-id="e7ffe-145">匯出未編製索引的項目</span><span class="sxs-lookup"><span data-stu-id="e7ffe-145">Export only unindexed items</span></span>
    
    <span data-ttu-id="e7ffe-146">如需未編製索引的項目的詳細資訊，請參閱 <<c0>已局部編製索引內容搜尋中的項目。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-146">For more information about unindexed items, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>
    
7. <span data-ttu-id="e7ffe-147">選擇要包含的所有版本的 SharePoint 文件的搜尋統計資料。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-147">Choose to include search statistics for all versions of SharePoint documents.</span></span> <span data-ttu-id="e7ffe-148">搜尋的內容來源包含 SharePoint 或 OneDrive for Business 網站時，才會出現這個選項。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-148">This option appears only if the content sources of the search includes SharePoint or OneDrive for Business sites.</span></span>
    
8. <span data-ttu-id="e7ffe-149">按一下 [**產生報告**。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-149">Click **Generate report**.</span></span>
    
    <span data-ttu-id="e7ffe-150">搜尋結果報告，已備妥下載，這表示報表文件將會上傳至 Microsoft 雲端中的 [Azure 儲存體] 區域。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-150">The search results report is prepared for downloading, which means the report documents will be uploaded to the Azure storage area in the Microsoft cloud.</span></span> <span data-ttu-id="e7ffe-151">準備好進行下載報告時，**下載報告**] 連結會在 [詳細資料] 窗格中顯示下**匯出報告到電腦**。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-151">When the report is ready for download, the **Download report** link is displayed under **Export report to a computer** in the details pane.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="e7ffe-152">您也可以匯出報告與 eDiscovery 案例相關聯的內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-152">You can also export a report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="e7ffe-153">若要這麼做，請前往 [ **eDiscovery** \> **eDiscovery**]，選取情況下，然後按一下 [**編輯**![編輯圖示](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-153">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="e7ffe-154">在 [**搜尋**] 頁面上，選取 [搜尋]，然後按一下 [**匯出**![匯出搜尋結果圖示](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **匯出報告**。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-154">On the **Searches** page, select a search, and then click **Export** ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **Export a report**.</span></span> 
  
## <a name="step-2-download-the-report"></a><span data-ttu-id="e7ffe-155">步驟 2： 下載報告</span><span class="sxs-lookup"><span data-stu-id="e7ffe-155">Step 2: Download the report</span></span>

<span data-ttu-id="e7ffe-156">下一步是到本機電腦的 Azure 儲存體區域下載報告。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-156">The next step is to download the report from the Azure storage area to your local computer.</span></span>
  
1. <span data-ttu-id="e7ffe-157">在您產生的報告，在 [**匯出至電腦的報告**] 下的搜尋詳細資料窗格中，按一下 [**下載報告**]。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-157">In the details pane for the search that you generated the report for, under **Export report to a computer**, click **Download report**.</span></span>
    
    <span data-ttu-id="e7ffe-158">[**下載報告**] 頁面上會顯示，並包含下列資訊到該報表下載到您的電腦。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-158">The **Download report** page is displayed and contains the following information about the report till be downloaded to your computer.</span></span> 
    
    - <span data-ttu-id="e7ffe-159">將下載的項目數。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-159">The number of items that will be downloaded.</span></span>
    
    - <span data-ttu-id="e7ffe-160">預估的大小總計將下載的項目。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-160">The estimated total size of the items that will be downloaded.</span></span>
    
    - <span data-ttu-id="e7ffe-161">將匯出是否編製索引，或未建立索引。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-161">Whether indexed or unindexed will be exported.</span></span> <span data-ttu-id="e7ffe-162">未編製索引的項目是具有可辨識的格式、 加密，或因為其他原因而未建立索引的項目。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-162">Unindexed items are items that have an recognized format, are encrypted, or weren't indexed for other reasons.</span></span>
    
    - <span data-ttu-id="e7ffe-163">是否會下載 SharePoint 文件的版本。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-163">Whether or not versions of SharePoint documents will be downloaded.</span></span>
    
    - <span data-ttu-id="e7ffe-164">報表匯出程序的狀態。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-164">The status of the report export process.</span></span> <span data-ttu-id="e7ffe-165">您可以開始下載報告，即使尚未完成要求報告的準備工作。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-165">You can start downloading the report even if the preparation of the report isn't complete.</span></span>
    
2. <span data-ttu-id="e7ffe-166">**匯出金鑰**，請按一下 [**複製到剪貼簿**。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-166">Under **Export key**, click **Copy to clipboard**.</span></span> <span data-ttu-id="e7ffe-167">若要下載報告，您將在步驟 5 中使用此機碼。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-167">You will use this key in step 5 to download the report.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e7ffe-168">因為任何人都可以安裝和啟動 eDiscovery 匯出工具]，然後使用此機碼若要下載搜尋報告，請務必採取預防措施來保護此機碼，就像您會保護密碼或其他安全性相關的資訊。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-168">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span> 
  
3. <span data-ttu-id="e7ffe-169">按一下 [**下載報告**]。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-169">Click **Download report**.</span></span>
    
4. <span data-ttu-id="e7ffe-170">如果系統提示您安裝**MicrosoftOffice 365 eDiscovery 匯出工具**，請按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-170">If you're prompted to install the **MicrosoftOffice 365 eDiscovery Export Tool**, click **Install**.</span></span>
    
5. <span data-ttu-id="e7ffe-171">在**eDiscovery 匯出工具**中，貼上您在步驟 2 中適當的方塊中複製的匯出金鑰。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-171">In the **eDiscovery Export Tool**, paste the export key that you copied in step 2 in the appropriate box.</span></span>
    
6. <span data-ttu-id="e7ffe-172">按一下 [**瀏覽]** 以指定您要下載報告的位置。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-172">Click **Browse** to specify the location where you want to download the report.</span></span> 
    
7. <span data-ttu-id="e7ffe-173">按一下 [開始]\*\*\*\* 將搜尋結果下載至您的電腦。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-173">Click **Start** to download the search results to your computer.</span></span> 
    
    <span data-ttu-id="e7ffe-174">**EDiscovery 匯出工具**會顯示在匯出程序，包括的估計項目數量 （及大小） 的其餘項目若要下載的狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-174">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded.</span></span> <span data-ttu-id="e7ffe-175">匯出程序完成時，您可以存取已下載的所在位置的檔案。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-175">When the export process is complete, you can access the files in the location where they were downloaded.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="e7ffe-176">您可以下載報告與 eDiscovery 案例相關聯的內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-176">You can download the report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="e7ffe-177">若要這麼做，請前往 [ **eDiscovery** \> **eDiscovery**]，選取情況下，然後按一下 [**編輯**![編輯圖示](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-177">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="e7ffe-178">在 [**匯出**] 頁面上，選取報表匯出，，然後按一下 [詳細資料窗格中的 [**下載報告**。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-178">On the **Exports** page, select an report export, and then click **Download report** in the details pane.</span></span> 
  
## <a name="whats-included-in-the-report"></a><span data-ttu-id="e7ffe-179">在報告中包含的內容</span><span class="sxs-lookup"><span data-stu-id="e7ffe-179">What's included in the report</span></span>

<span data-ttu-id="e7ffe-180">當產生並匯出內容搜尋結果的相關報告時，下載下列文件：</span><span class="sxs-lookup"><span data-stu-id="e7ffe-180">When you generate and export a report about the results of a Content Search, the following documents are downloaded:</span></span>
  
- <span data-ttu-id="e7ffe-181">**匯出摘要**-包含在匯出摘要的 Excel 文件。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-181">**Export Summary** - An Excel document that contains a summary of the export.</span></span> <span data-ttu-id="e7ffe-182">這包括所搜尋的內容來源數目、 每個內容的位置、 估計的項目數目、 實際數目會匯出的項目從搜尋結果數目以及估計與實際的項目大小等資訊會匯出的。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-182">This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="e7ffe-183">匯出報告時，您就會包含未編製索引的項目，未編製索引的項目數目是否包含下載的搜尋結果 （如果您是要匯出搜尋結果） 中所列的總數和總數預估的搜尋結果中匯出摘要報告。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-183">If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the Export Summary report.</span></span> <span data-ttu-id="e7ffe-184">換句話說，也會下載的項目數總計等於總數預估結果及未編製索引的項目總數。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-184">In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items.</span></span> 
  
- <span data-ttu-id="e7ffe-185">**資訊清單**的資訊清單中的檔案 （XML 格式），其中包含搜尋結果中包含每個項目的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-185">**Manifest** - A manifest file (in XML format) that contains information about each item included in the search results.</span></span> 
    
- <span data-ttu-id="e7ffe-186">**結果**-Excel 文件，其中包含具有會在搜尋結果匯出每個已編製索引項目的相關資訊的資料列。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-186">**Results** - An Excel document that contains a row with information about each indexed item that would be exported with the search results.</span></span> <span data-ttu-id="e7ffe-187">電子郵件，結果記錄檔會包含每個郵件的資訊包括：</span><span class="sxs-lookup"><span data-stu-id="e7ffe-187">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="e7ffe-188">來源信箱中的郵件的位置 (包括郵件是否處於主要或封存信箱)。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-188">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="e7ffe-189">郵件已傳送或接收的日期。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-189">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="e7ffe-190">從郵件主旨行。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-190">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="e7ffe-191">寄件者和收件者的郵件。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-191">The sender and recipients of the message.</span></span>
    
    <span data-ttu-id="e7ffe-192">文件的 SharePoint 和 OneDrive for Business 網站，結果記錄檔包含每個文件的資訊包括：</span><span class="sxs-lookup"><span data-stu-id="e7ffe-192">For documents from SharePoint and OneDrive for Business sites, the Results log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="e7ffe-193">文件的 URL。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-193">The URL for the document.</span></span>
    
  - <span data-ttu-id="e7ffe-194">文件所在之網站集合的 URL。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-194">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="e7ffe-195">上次修改文件的日期。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-195">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="e7ffe-196">（這位於結果記錄檔中的 [主旨] 欄） 的文件的名稱。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-196">The name of the document (which is located in the Subject column in the result log).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e7ffe-197">**結果**報告中的資料列數目必須等於會列在**未編製索引的項目**報告中的項目總數減下載的搜尋結果的總數。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-197">The number of rows in the **Results** report should be equal to the total number of search results that would be downloaded minus the total number of items listed in the **Unindexed Items** report.</span></span> 
  
- <span data-ttu-id="e7ffe-198">**未編製索引的項目**-Excel 文件，其中包含未編製索引的項目會包含在搜尋結果的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-198">**Unindexed Items** - An Excel document that contains information about any unindexed items that would be included in the search results.</span></span> <span data-ttu-id="e7ffe-199">如果您未包含未編製索引的項目，在產生搜尋結果報告時，這份報告仍會被下載時，但會是空的。</span><span class="sxs-lookup"><span data-stu-id="e7ffe-199">If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span>
