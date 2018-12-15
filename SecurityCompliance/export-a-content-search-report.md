---
title: 匯出內容搜尋報告
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExportReport
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9
description: 而不是實際的 Office 365 安全性內容的搜尋結果匯出&amp;規範中心，您可以只將匯出的搜尋結果報表。報表會包含在搜尋結果和每個項目會匯出的詳細資訊與文件的摘要。
ms.openlocfilehash: e15c6550d58701abe9b268455deca0aef60265fb
ms.sourcegitcommit: 1bc36cd57ab1604f057e2b5d336cf1893ba00125
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/15/2018
ms.locfileid: "27283139"
---
# <a name="export-a-content-search-report"></a><span data-ttu-id="c0287-104">匯出內容搜尋報告</span><span class="sxs-lookup"><span data-stu-id="c0287-104">Export a Content Search report</span></span>

<span data-ttu-id="c0287-105">而不是匯出完整的搜尋結果從 Office 365 安全性內容搜尋&amp;規範中心 （及內容搜尋與 eDiscovery 案例相關聯的），您可以只將匯出是同一個報表產生何時您匯出搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="c0287-105">Instead of exporting the full set of search results from a Content Search in the Office 365 Security &amp; Compliance Center (and from a Content Search that's associated with an eDiscovery case), you can just export the same reports that are generated when you export search results.</span></span>
  
<span data-ttu-id="c0287-p102">當您將報表匯出時，它會下載至具有相同名稱內容的搜尋，但會附加 *_ReportsOnly*的資料夾。例如，如果內容搜尋名稱為*ContosoCase0815* ，報表會下載至名為*ContosoCase0815_ReportsOnly*的資料夾。包含報表中的文件的清單，請參閱[報告中提供的功能](#whats-included-in-the-report)。</span><span class="sxs-lookup"><span data-stu-id="c0287-p102">When you export a report, it's downloaded to a folder that has the same name as the Content Search, but that's appended with  *_ReportsOnly*  . For example, if the Content Search is named  *ContosoCase0815*  , then the report is downloaded to a folder named  *ContosoCase0815_ReportsOnly*  . For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c0287-109">開始之前</span><span class="sxs-lookup"><span data-stu-id="c0287-109">Before you begin</span></span>

- <span data-ttu-id="c0287-p103">若要匯出內容搜尋報告，您必須要指派給 Office 365 安全性規範搜尋管理角色&amp;規範中心。此角色指派給內建的 eDiscovery 管理員和組織管理角色群組。它不是預設指派給組織管理角色群組。如需詳細資訊，請參閱[指派 Office 365 安全性 eDiscovery 權限&amp;規範中心](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="c0287-p103">To export a Content Search report, you have to be assigned the Compliance Search management role in the Office 365 Security &amp; Compliance Center. This role is assigned to the built-in eDiscovery Manager and Organization Management role groups. It isn't assigned by default to the Organization Management role group. For more information, see [Assign eDiscovery permissions in the Office 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="c0287-p104">當您將報表匯出資料會暫時儲存在 Microsoft cloud 中唯一 Windows Azure 的儲存區之前就會下載至您的本機電腦。請確定您的組織可以連線到 Azure，這是在端點**\*。 blob.core.windows.net** （萬用字元代表您匯出的唯一識別碼）。會在建立之後的兩週刪除搜尋結果資料從 Azure 儲存區。</span><span class="sxs-lookup"><span data-stu-id="c0287-p104">When you export a report, the data is temporarily stored in a unique Windows Azure storage area in the Microsoft cloud before it's downloaded to your local computer. Be sure your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export). The search results data is deleted from the Azure storage area two weeks after it's created.</span></span> 
    
- <span data-ttu-id="c0287-117">您要用來匯出搜尋結果的電腦必須符合下列系統需求：</span><span class="sxs-lookup"><span data-stu-id="c0287-117">The computer you use to export the search results has to meet the following system requirements:</span></span>
    
  - <span data-ttu-id="c0287-118">Windows 7 和更新版本的 32 或 64 位元版本


</span><span class="sxs-lookup"><span data-stu-id="c0287-118">32- or 64-bit versions of Windows 7 and later versions</span></span>
    
  - <span data-ttu-id="c0287-119">Microsoft.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="c0287-119">Microsoft .NET Framework 4.7</span></span>
    
  - <span data-ttu-id="c0287-120">支援的瀏覽器：</span><span class="sxs-lookup"><span data-stu-id="c0287-120">A supported browser:</span></span>
    
    - <span data-ttu-id="c0287-121">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c0287-121">Microsoft Edge</span></span>
    
      <span data-ttu-id="c0287-122">或 </span><span class="sxs-lookup"><span data-stu-id="c0287-122">or</span></span>
    
    - <span data-ttu-id="c0287-123">Microsoft Internet Explorer 10 或更新版本</span><span class="sxs-lookup"><span data-stu-id="c0287-123">Microsoft Internet Explorer 10 and later versions</span></span>
    
    <span data-ttu-id="c0287-p105">**附註：** Microsoft 不會製造協力廠商擴充功能或 ClickOnce 應用程式的附加元件。不支援將匯出使用不受支援的瀏覽器與協力廠商擴充功能或附加元件的搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="c0287-p105">**Note:** Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications. Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span> 

- <span data-ttu-id="c0287-p106">如果內容的搜尋所傳回的結果的估計總大小超過 20&nbsp;TB、 匯出報表將會失敗。若要成功匯出報表，請嘗試縮小範圍並重新執行搜尋結果的估計的大小小於 20 讓&nbsp;TB。</span><span class="sxs-lookup"><span data-stu-id="c0287-p106">If the estimated total size of the results returned by a Content Search exceeds 20&nbsp;TB, exporting the report will fail. To successfully export the report, try to narrow the scope and re-run the search so the estimated size of the results is less than 20&nbsp;TB.</span></span>

## <a name="generate-and-download-a-content-search-report"></a><span data-ttu-id="c0287-128">產生及下載的內容搜尋報告</span><span class="sxs-lookup"><span data-stu-id="c0287-128">Generate and download a Content Search report</span></span>

<span data-ttu-id="c0287-129">產生及下載的內容搜尋報表的步驟是非常類似實際匯出搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="c0287-129">The steps to generate and download a Content Search report are very similar to actually exporting search results.</span></span>
  
## <a name="step-1-generate-the-report-for-export"></a><span data-ttu-id="c0287-130">步驟 1： 產生匯出的報告</span><span class="sxs-lookup"><span data-stu-id="c0287-130">Step 1: Generate the report for export</span></span>

<span data-ttu-id="c0287-p107">第一個步驟是準備報表下載到電腦匯出。當您報表，報表文件上傳至 Azure 中儲存區是由 Microsoft 雲端。</span><span class="sxs-lookup"><span data-stu-id="c0287-p107">The first step is to prepare the report for downloading to your computer exporting. When you the report, the report documents are uploaded to an Azure storage area in the Microsoft cloud.</span></span>
  
1. <span data-ttu-id="c0287-133">移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="c0287-133">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="c0287-134">使用公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="c0287-134">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="c0287-135">在安全性與合規性中心的左窗格中，按一下 [搜尋與調查]\*\*\*\* \> [內容搜尋]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c0287-135">In the left pane of the Security &amp; Compliance Center, click **Search &amp; investigation** \> **Content search**.</span></span>
    
4. <span data-ttu-id="c0287-136">在 [**內容搜尋**] 頁面上選取 [搜尋。</span><span class="sxs-lookup"><span data-stu-id="c0287-136">On the **Content search** page, select a search.</span></span> 
    
5. <span data-ttu-id="c0287-137">在 [詳細資料] 窗格中，[**匯出至電腦的報告**，請按一下 [**產生報表**。</span><span class="sxs-lookup"><span data-stu-id="c0287-137">In the details pane, under **Export report to a computer**, click **Generate report**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c0287-p108">如果超過 7 天的搜尋結果，系統會提示您更新的搜尋結果。如果發生這種情況，取消匯出、 選取搜尋的詳細資料] 窗格中按一下 [**更新搜尋結果**並更新結果之後再啟動報表匯出。</span><span class="sxs-lookup"><span data-stu-id="c0287-p108">If the results for a search are older than 7 days, you are prompted to update the search results. If this happens, cancel the export, click **Update search results** in the details pane for the selected search, and then start the report export again after the results are updated.</span></span> 
  
6. <span data-ttu-id="c0287-140">在**將報表匯出**] 索引標籤下**包含這些項目] 搜尋中的**，選擇下列選項之一：</span><span class="sxs-lookup"><span data-stu-id="c0287-140">On the **Export a report** page, under **Include these items from the search**, choose one of the following options:</span></span>
    
    - <span data-ttu-id="c0287-141">僅匯出已編製索引的項目</span><span class="sxs-lookup"><span data-stu-id="c0287-141">Export only indexed items</span></span>
    
    - <span data-ttu-id="c0287-142">匯出已編製索引和未編製索引的項目</span><span class="sxs-lookup"><span data-stu-id="c0287-142">Export indexed and unindexed items</span></span>
    
    - <span data-ttu-id="c0287-143">僅匯出未編製索引的項目</span><span class="sxs-lookup"><span data-stu-id="c0287-143">Export only unindexed items</span></span>
    
    <span data-ttu-id="c0287-144">如需編製索引的項目的詳細資訊，請參閱[部分編製索引內容的搜尋中的項目](partially-indexed-items-in-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="c0287-144">For more information about unindexed items, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>
    
7. <span data-ttu-id="c0287-p109">選擇要包含的所有版本的 SharePoint 文件的搜尋統計資料。只有當內容來源的搜尋包含 SharePoint 或 OneDrive for Business 的網站會出現此選項。</span><span class="sxs-lookup"><span data-stu-id="c0287-p109">Choose to include search statistics for all versions of SharePoint documents. This option appears only if the content sources of the search includes SharePoint or OneDrive for Business sites.</span></span>
    
8. <span data-ttu-id="c0287-147">按一下 [**產生報表**。</span><span class="sxs-lookup"><span data-stu-id="c0287-147">Click **Generate report**.</span></span>
    
    <span data-ttu-id="c0287-p110">搜尋結果報表已備妥下載，這表示報表文件將上傳至 Microsoft 雲端中的 [Azure 存放區] 區域。備妥可供下載報表時，請**下載報告**連結將顯示 [**匯出至電腦的報告**詳細資料窗格中。</span><span class="sxs-lookup"><span data-stu-id="c0287-p110">The search results report is prepared for downloading, which means the report documents will be uploaded to the Azure storage area in the Microsoft cloud. When the report is ready for download, the **Download report** link is displayed under **Export report to a computer** in the details pane.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="c0287-p111">您也可以將報表匯出內容的搜尋與 eDiscovery 案例相關聯的。若要這樣做，請移至**搜尋&amp;調查** \> **eDiscovery**選取案例中，然後按一下 [**編輯**![編輯圖示](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。在 [**搜尋**] 頁面上選取 [搜尋] 和 [**匯出**![匯出搜尋結果圖示](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **將報表匯出**。</span><span class="sxs-lookup"><span data-stu-id="c0287-p111">You can also export a report for a Content Search that's associated with an eDiscovery case. To do this, go to **Search &amp; investigation** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif). On the **Searches** page, select a search, and then click **Export** ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **Export a report**.</span></span> 
  
## <a name="step-2-download-the-report"></a><span data-ttu-id="c0287-153">步驟 2： 下載報告</span><span class="sxs-lookup"><span data-stu-id="c0287-153">Step 2: Download the report</span></span>

<span data-ttu-id="c0287-154">下一步是從 Azure 儲存區的報表下載至本機電腦。</span><span class="sxs-lookup"><span data-stu-id="c0287-154">The next step is to download the report from the Azure storage area to your local computer.</span></span>
  
1. <span data-ttu-id="c0287-155">在搜尋您產生的報告、 [**匯出至電腦的報告**詳細資料窗格中，按一下 [**下載報告**]。</span><span class="sxs-lookup"><span data-stu-id="c0287-155">In the details pane for the search that you generated the report for, under **Export report to a computer**, click **Download report**.</span></span>
    
    <span data-ttu-id="c0287-156">[**下載報告**] 頁面上會顯示並包含下列資訊直到報告下載到您的電腦。</span><span class="sxs-lookup"><span data-stu-id="c0287-156">The **Download report** page is displayed and contains the following information about the report till be downloaded to your computer.</span></span> 
    
    - <span data-ttu-id="c0287-157">將下載的項目數目。</span><span class="sxs-lookup"><span data-stu-id="c0287-157">The number of items that will be downloaded.</span></span>
    
    - <span data-ttu-id="c0287-158">將下載的項目估計總數。</span><span class="sxs-lookup"><span data-stu-id="c0287-158">The estimated total size of the items that will be downloaded.</span></span>
    
    - <span data-ttu-id="c0287-p112">將匯出編製索引或未建立索引。項目已辨識的格式、 加密，或未編製索引的其他原因會花很多項目。</span><span class="sxs-lookup"><span data-stu-id="c0287-p112">Whether indexed or unindexed will be exported. Unindexed items are items that have an recognized format, are encrypted, or weren't indexed for other reasons.</span></span>
    
    - <span data-ttu-id="c0287-161">是否下載 SharePoint 文件的版本。</span><span class="sxs-lookup"><span data-stu-id="c0287-161">Whether or not versions of SharePoint documents will be downloaded.</span></span>
    
    - <span data-ttu-id="c0287-p113">報表匯出程序的狀態。您可以啟動即使未完成的報表準備下載報告。</span><span class="sxs-lookup"><span data-stu-id="c0287-p113">The status of the report export process. You can start downloading the report even if the preparation of the report isn't complete.</span></span>
    
2. <span data-ttu-id="c0287-p114">**匯出金鑰**，請按一下 [**複製到剪貼簿**。您將在步驟 5 中使用此機碼下載報表。</span><span class="sxs-lookup"><span data-stu-id="c0287-p114">Under **Export key**, click **Copy to clipboard**. You will use this key in step 5 to download the report.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c0287-166">因為任何人都可以安裝並啟動 eDiscovery 匯出工具，再使用此機碼下載搜尋報告，請務必採取預防措施就像您會保護密碼或其他安全性相關的資訊保護此機碼。</span><span class="sxs-lookup"><span data-stu-id="c0287-166">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span> 
  
3. <span data-ttu-id="c0287-167">按一下 [**下載報告**。</span><span class="sxs-lookup"><span data-stu-id="c0287-167">Click **Download report**.</span></span>
    
4. <span data-ttu-id="c0287-168">如果系統提示您安裝**MicrosoftOffice 365 eDiscovery 匯出工具**，請按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="c0287-168">If you're prompted to install the **MicrosoftOffice 365 eDiscovery Export Tool**, click **Install**.</span></span>
    
5. <span data-ttu-id="c0287-169">在**eDiscovery 匯出工具**中，貼上您在步驟 2 中適當的方塊中複製的匯出金鑰。</span><span class="sxs-lookup"><span data-stu-id="c0287-169">In the **eDiscovery Export Tool**, paste the export key that you copied in step 2 in the appropriate box.</span></span>
    
6. <span data-ttu-id="c0287-170">按一下 [**瀏覽]** 以指定您要下載報告的位置。</span><span class="sxs-lookup"><span data-stu-id="c0287-170">Click **Browse** to specify the location where you want to download the report.</span></span> 
    
7. <span data-ttu-id="c0287-171">按一下 [開始]\*\*\*\* 將搜尋結果下載至您的電腦。</span><span class="sxs-lookup"><span data-stu-id="c0287-171">Click **Start** to download the search results to your computer.</span></span> 
    
    <span data-ttu-id="c0287-p115">**EDiscovery 匯出工具**會顯示狀態資訊匯出程序，包括評估會有數 （與大小） 的其餘的項目下載。匯出程序完成時，您可以存取已下載的所在位置的檔案。</span><span class="sxs-lookup"><span data-stu-id="c0287-p115">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded. When the export process is complete, you can access the files in the location where they were downloaded.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="c0287-p116">您可以下載報告的內容搜尋與 eDiscovery 案例相關聯。若要這樣做，請移至**搜尋&amp;調查** \> **eDiscovery**選取案例中，然後按一下 [**編輯**![編輯圖示](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。在 [**匯出**] 頁面上選取 [匯出報表] 和 [**下載報告**詳細資料窗格中。</span><span class="sxs-lookup"><span data-stu-id="c0287-p116">You can download the report for a Content Search that's associated with an eDiscovery case. To do this, go to **Search &amp; investigation** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif). On the **Exports** page, select an report export, and then click **Download report** in the details pane.</span></span> 
  
## <a name="whats-included-in-the-report"></a><span data-ttu-id="c0287-177">報告中提供的功能</span><span class="sxs-lookup"><span data-stu-id="c0287-177">What's included in the report</span></span>

<span data-ttu-id="c0287-178">如果您產生匯出相關內容的搜尋結果報表，下載下列文件：</span><span class="sxs-lookup"><span data-stu-id="c0287-178">When you generate and export a report about the results of a Content Search, the following documents are downloaded:</span></span>
  
- <span data-ttu-id="c0287-p117">**匯出摘要**-Excel 文件包含匯出的摘要。這包括資訊例如所搜尋的內容來源數目、 從每個內容的位置、 估計項目數、 實際的將匯出的項目數的搜尋結果數目以及評估及實際大小的項目將匯出的。</span><span class="sxs-lookup"><span data-stu-id="c0287-p117">**Export Summary** - An Excel document that contains a summary of the export. This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="c0287-p118">如果您包括編製索引的項目匯出報表時，編製索引的項目數是預估的搜尋結果的總數與下載的搜尋結果 （如果您已將搜尋結果匯出） 中所列的總數匯出摘要報告。換句話說，將下載的項目總數等於評估結果總數及編製索引的項目總數。</span><span class="sxs-lookup"><span data-stu-id="c0287-p118">If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the Export Summary report. In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items.</span></span> 
  
- <span data-ttu-id="c0287-183">**資訊清單**-內含搜尋結果中包含每個項目的相關資訊 （以 XML 格式） 的資訊清單檔案。</span><span class="sxs-lookup"><span data-stu-id="c0287-183">**Manifest** - A manifest file (in XML format) that contains information about each item included in the search results.</span></span> 
    
- <span data-ttu-id="c0287-p119">**結果**集的 Excel 文件包含一列的每個已編製索引的項目會匯出與搜尋結果的資訊。為電子郵件、 結果記錄檔包含每個郵件的資訊包括：</span><span class="sxs-lookup"><span data-stu-id="c0287-p119">**Results** - An Excel document that contains a row with information about each indexed item that would be exported with the search results. For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="c0287-186">來源信箱中訊息的位置 (包括訊息位於主要或封存信箱)。</span><span class="sxs-lookup"><span data-stu-id="c0287-186">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="c0287-187">送出或收到郵件的日期。</span><span class="sxs-lookup"><span data-stu-id="c0287-187">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="c0287-188">郵件的主旨行。</span><span class="sxs-lookup"><span data-stu-id="c0287-188">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="c0287-189">郵件的寄件者和收件者。</span><span class="sxs-lookup"><span data-stu-id="c0287-189">The sender and recipients of the message.</span></span>
    
    <span data-ttu-id="c0287-190">文件從 SharePoint 和 OneDrive for Business 網站的結果記錄檔包含每個文件的資訊包括：</span><span class="sxs-lookup"><span data-stu-id="c0287-190">For documents from SharePoint and OneDrive for Business sites, the Results log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="c0287-191">文件的 URL。</span><span class="sxs-lookup"><span data-stu-id="c0287-191">The URL for the document.</span></span>
    
  - <span data-ttu-id="c0287-192">文件庫所在之網站集合的 URL。</span><span class="sxs-lookup"><span data-stu-id="c0287-192">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="c0287-193">上次修改文件的日期。</span><span class="sxs-lookup"><span data-stu-id="c0287-193">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="c0287-194">(位於結果記錄檔中的 [主旨] 欄) 的文件名稱。</span><span class="sxs-lookup"><span data-stu-id="c0287-194">The name of the document (which is located in the Subject column in the result log).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c0287-195">**結果**報表中的列數應該是等於會下載減去**編製索引的項目**] 報告中所列的項目數總計的搜尋結果的總數。</span><span class="sxs-lookup"><span data-stu-id="c0287-195">The number of rows in the **Results** report should be equal to the total number of search results that would be downloaded minus the total number of items listed in the **Unindexed Items** report.</span></span> 
  
- <span data-ttu-id="c0287-p120">**編製索引的項目**-Excel 文件包含將搜尋結果中包含任何編製索引項目的相關資訊。如果您未包含編製索引的項目時產生搜尋結果報表，這份報告仍會下載，但會是空的。</span><span class="sxs-lookup"><span data-stu-id="c0287-p120">**Unindexed Items** - An Excel document that contains information about any unindexed items that would be included in the search results. If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span>
