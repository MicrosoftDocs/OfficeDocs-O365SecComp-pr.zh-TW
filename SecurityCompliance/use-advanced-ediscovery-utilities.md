---
title: 使用 Office 365 進階電子文件探索公用程式
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
ms.assetid: 66ca9993-75f4-4724-aea2-5a0719b660c1
description: '了解 Office 365 進階 eDiscovery，包括案例的記錄檔中的公用程式、 清除資料、 處理錯誤、 修改相關性及透明度分析。  '
ms.openlocfilehash: a68c98dd353971fcaa13fdc6b8e12bcf00c2faf0
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526236"
---
# <a name="use-office-365-advanced-ediscovery-utilities"></a><span data-ttu-id="64f43-103">使用 Office 365 進階電子文件探索公用程式</span><span class="sxs-lookup"><span data-stu-id="64f43-103">Use Office 365 Advanced eDiscovery utilities</span></span>

> [!NOTE]
> <span data-ttu-id="64f43-p101">進階的 eDiscovery 需要您組織與進階規範附加元件或 E5 訂閱 Office 365 E3。如果您不具有該對應並想要嘗試進階的 eDiscovery，您還可以[註冊 Office 365 企業版 E5 的試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="64f43-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="64f43-106">會顯示與進階 eDiscovery 提供公用程式取決於內容和使用者角色。</span><span class="sxs-lookup"><span data-stu-id="64f43-106">The utilities that are displayed and available in Advanced eDiscovery depend on context and user roles.</span></span>
  
## <a name="case-log"></a><span data-ttu-id="64f43-107">案例的記錄檔</span><span class="sxs-lookup"><span data-stu-id="64f43-107">Case log</span></span>

<span data-ttu-id="64f43-p102">Case 記錄提供應用程式處理活動追蹤、 疑難排解、 及處理錯誤和警告可以使用詳細的的清單。記錄檔可產生與儲存在本機上的主機或伺服器，或直接傳送至電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="64f43-p102">The Case log provides a detailed list of application processing activities, which can be used for tracking, troubleshooting, and for addressing errors and warnings. The log can be generated and stored locally on the host or server, or sent directly to an email address.</span></span>
  
<span data-ttu-id="64f43-p103">記錄檔也可以下載至用戶端電腦。用戶端的下載選項可能會啟用或停用根據設定及使用者角色。</span><span class="sxs-lookup"><span data-stu-id="64f43-p103">The log file can also be downloaded to the client's computer. The client download option may be enabled or disabled according to configuration and user role.</span></span>
  
1. <span data-ttu-id="64f43-112">在功能表列中，按一下 [ **Cogwheel**圖示。</span><span class="sxs-lookup"><span data-stu-id="64f43-112">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="64f43-113">在**設定和公用程式\>公用程式**] 索引標籤，選取 [ **Case 記錄\>安裝**。</span><span class="sxs-lookup"><span data-stu-id="64f43-113">In the **Settings and utilities \> Utilities** tab, select **Case log \> Setup**.</span></span>
    
3. <span data-ttu-id="64f43-114">選取**的記錄等級**如下所示：</span><span class="sxs-lookup"><span data-stu-id="64f43-114">Select the **Log level** as follows:</span></span> 
    
  - <span data-ttu-id="64f43-p104">**標準**： 包括基本的記錄資料。此選項進行監控，通常需要，否則建議應該才能使用。</span><span class="sxs-lookup"><span data-stu-id="64f43-p104">**Standard**: Includes the basic log data. This option is usually necessary for monitoring, and should be used unless recommended otherwise.</span></span>
    
  - <span data-ttu-id="64f43-117">**最小**： 只能用於非常大的情況下，而且會傳回最新的資料。</span><span class="sxs-lookup"><span data-stu-id="64f43-117">**Minimal**: Used for very large cases, and returns only the latest data.</span></span>
    
4. <span data-ttu-id="64f43-p105">按一下 [**執行案例記錄檔**。產生記錄檔並顯示路徑。在 [工作狀態] 窗格中顯示目前和最後一個任務的任務進度資訊。</span><span class="sxs-lookup"><span data-stu-id="64f43-p105">Click **Run Case log**. The log is generated and path is displayed. The task progress information for the current and last task is displayed in the Task status pane.</span></span>
    
## <a name="clear-data"></a><span data-ttu-id="64f43-121">清除資料</span><span class="sxs-lookup"><span data-stu-id="64f43-121">Clear data</span></span>

<span data-ttu-id="64f43-p106">必要時刪除或重新初始化案例資料，就必須初始化的資料庫執行個體。清除資料公用程式 case 資料庫、 文字檔、 case 資料夾與累積的結果刪除所有指定的項目。函數只可由系統管理員執行。</span><span class="sxs-lookup"><span data-stu-id="64f43-p106">If it is necessary to delete or reinitialize case data, the database instance must be initialized. The Clear data utility deletes all specified entries from the case database, text files, case folder, and accumulated results. The function can only be performed by an administrator.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="64f43-p107">此巨集指令可逆並不會清除所有的相關性標記和專家所執行的分析。必要時儲存資料的備份。超重度請小心使用此選項。刪除標記及排名檔案可能會影響結果的相關性。</span><span class="sxs-lookup"><span data-stu-id="64f43-p107">This action is not reversible and will clear all Relevance tagging and analysis performed by the expert. Save a backup of data, if necessary. Use this option with extreme care. Deleting tagged and ranked files can impact the Relevance results.</span></span> 
  
1. <span data-ttu-id="64f43-129">在功能表列中，按一下 [ **Cogwheel**圖示。</span><span class="sxs-lookup"><span data-stu-id="64f43-129">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="64f43-130">在**設定和公用程式\>公用程式**] 索引標籤，選取 [**清除資料\>安裝**。</span><span class="sxs-lookup"><span data-stu-id="64f43-130">In the **Settings and utilities \> Utilities** tab, select **Clear data \> Setup**.</span></span>
    
3. <span data-ttu-id="64f43-131">選取要初始化的資訊的選項：</span><span class="sxs-lookup"><span data-stu-id="64f43-131">Select an option for the information to initialize:</span></span>
    
  - <span data-ttu-id="64f43-p108">**相關性**： 會刪除所有已完成相關性，包括定義載入及載入的檔案關聯的工作。它會刪除所有範例及標記。</span><span class="sxs-lookup"><span data-stu-id="64f43-p108">**Relevance**: Deletes all work done in Relevance, including definition of loads and association of files to loads. It deletes all samples and tagging.</span></span>
    
  - <span data-ttu-id="64f43-134">**接近重複項目及電子郵件執行緒**： 會刪除所有分析資訊的接近重複項目及電子郵件執行緒。</span><span class="sxs-lookup"><span data-stu-id="64f43-134">**Near-duplicates and email threads**: Deletes all analysis information of near-duplicates and email threads.</span></span>
    
  - <span data-ttu-id="64f43-135">**佈景主題**： 刪除佈景主題相關的資料。</span><span class="sxs-lookup"><span data-stu-id="64f43-135">**Themes**: Deletes themes-related data.</span></span>
    
  - <span data-ttu-id="64f43-136">**匯出歷程記錄**： 刪除的匯出批次的歷程記錄資訊。</span><span class="sxs-lookup"><span data-stu-id="64f43-136">**Export history**: Deletes history information of Export batches.</span></span>
    
4. <span data-ttu-id="64f43-p109">按一下 [**清除資料**。會清除區分大小資料。在 [**工作狀態**] 窗格中顯示目前和最後一個任務的任務進度資訊。</span><span class="sxs-lookup"><span data-stu-id="64f43-p109">Click **Clear data**. The case data is cleared. The task progress information for the current and last task is displayed in the **Task status** pane.</span></span> 
    
## <a name="modify-relevance"></a><span data-ttu-id="64f43-140">修改相關性</span><span class="sxs-lookup"><span data-stu-id="64f43-140">Modify Relevance</span></span>

<span data-ttu-id="64f43-141">本節說明如何將略過或回復相關性範例。</span><span class="sxs-lookup"><span data-stu-id="64f43-141">This section describes how to skip or roll back a Relevance sample.</span></span>
  
1. <span data-ttu-id="64f43-142">在功能表列中，按一下 [ **Cogwheel**圖示。</span><span class="sxs-lookup"><span data-stu-id="64f43-142">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="64f43-143">在**設定和公用程式\>公用程式**] 索引標籤中選取 [**修改相關性**。</span><span class="sxs-lookup"><span data-stu-id="64f43-143">In the **Settings and utilities \> Utilities** tab, select **Modify relevance**.</span></span>
    
3. <span data-ttu-id="64f43-144">選取選項：</span><span class="sxs-lookup"><span data-stu-id="64f43-144">Select from the options:</span></span> 
    
  - <span data-ttu-id="64f43-p110">**略過目前範例-目前的使用者**： 這會標記，以**略過**，執行公用程式的使用者開啟案例的範例中的所有無標記的檔案。相關性處理將不會在已標記為**略過**的檔案上執行。</span><span class="sxs-lookup"><span data-stu-id="64f43-p110">**Skip current sample - for current user**: This will tag, as **Skip**, all untagged files in the open case sample of the user running the utility. Relevance processing will not be performed on files tagged as **Skip**.</span></span>
    
  - <span data-ttu-id="64f43-p111">**略過目前範例-所有開啟的範例**： 這會標記，以**略過**，所有無標記的檔案所有開啟的範例中的所有使用者。如果使用者目前已標記範例不建議此選項。</span><span class="sxs-lookup"><span data-stu-id="64f43-p111">**Skip current sample - all open samples**: This will tag, as **Skip**, all untagged files in all open samples for all users. This option is not recommended if users are currently tagging samples.</span></span>
    
  - <span data-ttu-id="64f43-p112">**回復最後一個範例**： 上一次完成訓練範例將會回復，不論是否為之前或之後"計算"程序的相關性。不允許執行更新性範例復原。</span><span class="sxs-lookup"><span data-stu-id="64f43-p112">**Roll back last sample**: The last completed Relevance training sample will be rolled back, regardless of whether it is before or after the "Calculate" process. Rollback of a catch-up sample is not allowed.</span></span>
    
4. <span data-ttu-id="64f43-151">按一下 [**執行**] 以執行。</span><span class="sxs-lookup"><span data-stu-id="64f43-151">Click **Execute** to run.</span></span> 
    
## <a name="transparency-analysis"></a><span data-ttu-id="64f43-152">透明分析</span><span class="sxs-lookup"><span data-stu-id="64f43-152">Transparency analysis</span></span>

<span data-ttu-id="64f43-p113">透明分析公用程式可讓檔案和其指派的相關性分數的詳細的檢視。報表可用例行性] 核取或進行比較的相關性與相關性指派進階 eDiscovery 人工檢閱者所定義的檔案。</span><span class="sxs-lookup"><span data-stu-id="64f43-p113">The Transparency analysis utility enables a detailed view of files and their assigned Relevance score. The report can be used as a sanity check or to compare the relevance of a file defined by a human reviewer as compared to the relevance assigned by Advanced eDiscovery.</span></span> 
  
<span data-ttu-id="64f43-p114">除了相關性分數進階的 eDiscovery 會計算並指派關鍵字的關鍵字內容，請考慮的寬度。檔案的相同字可以指派不同的寬度，視內容和位置而定。使用色彩強度從黃色延伸到深橙色和 varying 灰網底的提高規模標示每個關鍵字。色彩編碼用於以視覺方式指出字的相對正數或負比重相關性分數。</span><span class="sxs-lookup"><span data-stu-id="64f43-p114">In addition to Relevance scores, Advanced eDiscovery calculates and assigns keyword weights that consider the keyword context. The same word in a file can be assigned different weights, depending on context and location. Each keyword is marked using an increasing scale of color intensity ranging from yellow to dark orange and varying shades of gray. Color coding is used to visually indicate the word's relative positive or negative contribution to the Relevance score.</span></span> 
  
<span data-ttu-id="64f43-159">在多個問題 case 案例中，可產生透明度分析報表的每個問題。</span><span class="sxs-lookup"><span data-stu-id="64f43-159">In a multiple-issue case scenario, a Transparency analysis report can be generated for each issue.</span></span>
  
1. <span data-ttu-id="64f43-160">在功能表列中，按一下 [ **Cogwheel**圖示。</span><span class="sxs-lookup"><span data-stu-id="64f43-160">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="64f43-161">在**設定和公用程式\>公用程式**] 索引標籤，選取 [**透明度分析\>安裝**。</span><span class="sxs-lookup"><span data-stu-id="64f43-161">In the **Settings and utilities \> Utilities** tab, select **Transparency analysis \> Setup**.</span></span>
    
3. <span data-ttu-id="64f43-162">在 [* * 檔案識別碼 * *，輸入檔案的檔案識別碼來處理。</span><span class="sxs-lookup"><span data-stu-id="64f43-162">In ** File ID **, enter the file ID of the file to process.</span></span>
    
4. <span data-ttu-id="64f43-163">[**問題**] 清單中選取的改變功能的問題。</span><span class="sxs-lookup"><span data-stu-id="64f43-163">In the **Issue** list, select the pertinent issue.</span></span> 
    
5. <span data-ttu-id="64f43-p115">按一下 [**透明的分析**。完成後，會顯示透明分析報表的檔案，它會顯示特別標示的關鍵字色彩與整體相關性分數的相互關聯。</span><span class="sxs-lookup"><span data-stu-id="64f43-p115">Click **Transparency analysis**. Upon completion, the Transparency analysis report for the file is displayed, which shows how the marked keyword colors correlate to the overall Relevance score.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="64f43-166">另請參閱</span><span class="sxs-lookup"><span data-stu-id="64f43-166">See also</span></span>

[<span data-ttu-id="64f43-167">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="64f43-167">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="64f43-168">定義案例和承租人設定</span><span class="sxs-lookup"><span data-stu-id="64f43-168">Defining case and tenant settings</span></span>](define-case-and-tenant-settings-in-advanced-ediscovery.md)

