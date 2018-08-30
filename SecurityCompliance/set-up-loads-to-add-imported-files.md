---
title: 在 Office 365 進階電子文件探索中設定載入要新增匯入的檔案
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
ms.assetid: 0e0a9d04-294f-4f54-8bf1-b32d81345126
description: '檢閱將匯入的檔案新增至最後一個已定義的負載或批次檔案，再執行相關性訓練 Office 365 進階 ediscovery 的步驟。  '
ms.openlocfilehash: 2c986578b969b671351930fd6939a90e3a821dc2
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22527276"
---
# <a name="set-up-loads-to-add-imported-files-in-office-365-advanced-ediscovery"></a><span data-ttu-id="e7e13-103">在 Office 365 進階電子文件探索中設定載入要新增匯入的檔案</span><span class="sxs-lookup"><span data-stu-id="e7e13-103">Set up loads to add imported files in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="e7e13-p101">進階的 eDiscovery 需要您組織與進階規範附加元件或 E5 訂閱 Office 365 E3。如果您不具有該對應並想要嘗試進階的 eDiscovery，您還可以[註冊 Office 365 企業版 E5 的試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="e7e13-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="e7e13-p102">進階 ediscovery 負載為新的批次的檔案新增至案例。根據預設，定義一個負載並所有匯入的檔案新增至其中。執行相關性訓練、 之前先匯入的檔案必須加入至負載。</span><span class="sxs-lookup"><span data-stu-id="e7e13-p102">In Advanced eDiscovery, a load is a new batch of files added to a case. By default, one load is defined and all imported files are added to it. Before performing Relevance training, imported files must be added to the load.</span></span> 
  
<span data-ttu-id="e7e13-109">請考慮下列情況：</span><span class="sxs-lookup"><span data-stu-id="e7e13-109">Consider the following scenarios:</span></span>
  
- <span data-ttu-id="e7e13-p103">新的檔案已知會類似案例的資料庫中，載入舊版檔案或檔案的上一個負載隨機組從檔案集合。在此例子中會將新增至目前的檔案載入的匯入的檔案。</span><span class="sxs-lookup"><span data-stu-id="e7e13-p103">New files are known to be similar to the previous files loaded to the case database, or the previous load of files was a random set from the file collection. In this instance, add the imported files to the current file load.</span></span>
    
- <span data-ttu-id="e7e13-p104">新的檔案會不同於先前的錯誤 （例如，從不同的來源），或有它們是相似或不同先前載入至沒有先備知識。在此案例中，將新增至新的檔案載入的匯入的檔案。進階的 eDiscovery 會將此辨識為循環載入案例、 叫用執行更新性程序、 鎖定相關性訓練及批次計算直到完成 Catch-up、 整合並經過訓練的新負載。</span><span class="sxs-lookup"><span data-stu-id="e7e13-p104">New files are different from previous ones (for example, from a different source), or you have no prior knowledge that they're similar or different to the previous loads. In this scenario, add the imported files to a new file load. Advanced eDiscovery recognizes this as a Rolling loads scenario, invokes a Catch-up process, locks Relevance training and Batch calculations until Catch-up is completed, and the new load is integrated and trained.</span></span> 
    
## <a name="adding-imported-files-to-the-current-load"></a><span data-ttu-id="e7e13-115">將匯入的檔案新增至目前的負載</span><span class="sxs-lookup"><span data-stu-id="e7e13-115">Adding imported files to the current load</span></span>

<span data-ttu-id="e7e13-p105">所有匯入的檔案必須新增至進階 ediscovery 處理負載。匯入的檔案會新增至最後一個定義的負載。如果您稍後匯入其他檔案，他們也必須被新增至負載。</span><span class="sxs-lookup"><span data-stu-id="e7e13-p105">All imported files must be added to a load to be processed in Advanced eDiscovery. Imported files are added to the last defined load. If you import additional files later, they also must be added to the load.</span></span>
  
1. <span data-ttu-id="e7e13-119">在**相關性\>相關性安裝**] 索引標籤中選取**負載**。</span><span class="sxs-lookup"><span data-stu-id="e7e13-119">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
    ![相關性設定負載索引標籤](media/278aac7f-655f-462f-852a-6baa5d818768.png)
  
2. <span data-ttu-id="e7e13-p106">**包含檔案**： 選取要包含的檔案] 選項。根據預設，將檔案新增至目前的負載根據 「 所有檔案"母體。</span><span class="sxs-lookup"><span data-stu-id="e7e13-p106">**Include files**: Select an option for files to include. By default, adding files to the current load is based on the "All files" population.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="e7e13-p107">所有可用的 culled 的檔案載入相關性。如果您打算要載入僅為可用的檔案的子集，請先洽詢支援，如載入備有不良影響相關性訓練。</span><span class="sxs-lookup"><span data-stu-id="e7e13-p107">Load all available culled files into Relevance. If you plan to load only a subset of the available files, please first consult with Support, as loading subsets can adversely affect Relevance training.</span></span> 
  
3. <span data-ttu-id="e7e13-125">在**載入管理**] 中選取負載。</span><span class="sxs-lookup"><span data-stu-id="e7e13-125">In **Loads management**, select a load.</span></span>
    
4. <span data-ttu-id="e7e13-p108">按一下 [**新增檔案**]。將檔案新增至負載，並會顯示確認訊息。</span><span class="sxs-lookup"><span data-stu-id="e7e13-p108">Click **Add files**. The files are added to the load and a confirmation message is displayed.</span></span> 
    
5. <span data-ttu-id="e7e13-128">按一下 [確定]****。</span><span class="sxs-lookup"><span data-stu-id="e7e13-128">Click **OK**.</span></span>
    
<span data-ttu-id="e7e13-129">將檔案的訓練檔案現在進階 ediscovery 相關性處理。</span><span class="sxs-lookup"><span data-stu-id="e7e13-129">The files can now be processed in Advanced eDiscovery Relevance for training the files.</span></span>
  
## <a name="editing-a-load-name-within-a-case"></a><span data-ttu-id="e7e13-130">編輯內案例的載入名稱</span><span class="sxs-lookup"><span data-stu-id="e7e13-130">Editing a load name within a case</span></span>

<span data-ttu-id="e7e13-131">如果變更負載名稱，建議使用重要的大小寫的名稱。</span><span class="sxs-lookup"><span data-stu-id="e7e13-131">If changing the load name, it is recommended to use a name that is significant to the case.</span></span>
  
1. <span data-ttu-id="e7e13-132">在**相關性\>相關性安裝**] 索引標籤中選取**負載**。</span><span class="sxs-lookup"><span data-stu-id="e7e13-132">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
2. <span data-ttu-id="e7e13-p109">從**負載管理**] 清單中選取負載，並按一下 [**編輯**] 圖示。編輯負載視窗會隨即顯示。</span><span class="sxs-lookup"><span data-stu-id="e7e13-p109">From the **Loads management** list, select a load and click the **Edit** icon. The Edit load window is displayed.</span></span> 
    
3. <span data-ttu-id="e7e13-135">輸入變更，然後再按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="e7e13-135">Enter the changes, and then click **OK**.</span></span>
    
## <a name="adding-imported-files-to-a-new-load"></a><span data-ttu-id="e7e13-136">將匯入的檔案新增至新的負載</span><span class="sxs-lookup"><span data-stu-id="e7e13-136">Adding imported files to a new load</span></span>

<span data-ttu-id="e7e13-137">啟動相關性訓練或執行批次計算之後, 可能會想要匯入及處理其他組檔案。</span><span class="sxs-lookup"><span data-stu-id="e7e13-137">After starting Relevance training or performing Batch calculation, you may want to import and process an additional set of files.</span></span> 
  
<span data-ttu-id="e7e13-p110">期間 Catch-up，您可以建立、 標記，以及分析 Catch-up 集。進階的 eDiscovery 比較其評估的相關及非相關檔案中先前載入至新的負載。根據結果，系統提示您進行 Catch-up 決策若有需要，和進階 eDiscovery 提供建議根據給付的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="e7e13-p110">During Catch-up, you can create, tag, and analyze the Catch-up set. Advanced eDiscovery compares its assessment of Relevant and Non-Relevant files in the new load to those in previous loads. Based on the results, you are prompted to make Catch-up decisions, if necessary, and Advanced eDiscovery provides recommendations based on the accrued Relevance information.</span></span> 
  
<span data-ttu-id="e7e13-141">滾動載入及執行更新性功能會而異，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e7e13-141">Rolling Loads and Catch-up functionality varies as follows:</span></span> 
  
- <span data-ttu-id="e7e13-142">批次計算後匯入新的檔案載入、 時進階的 eDiscovery 決定以何種程度檔案分成下列類別：</span><span class="sxs-lookup"><span data-stu-id="e7e13-142">When you import a new file load after Batch calculation, Advanced eDiscovery determines to what extent the files fall into one of the following categories:</span></span>
    
  - <span data-ttu-id="e7e13-143">類似 （同質性）： 相關性訓練新、 自訂循，則不需要和從上一個負載累算知識可以套用"原狀"至新的負載。</span><span class="sxs-lookup"><span data-stu-id="e7e13-143">Similar (homogeneous): A new, custom round of Relevance training is not required and the knowledge accrued from the previous load can be applied "as is" to the new load.</span></span> 
    
  - <span data-ttu-id="e7e13-144">Distinct （異質性）： 相關性訓練新、 自訂循是必要的而且無法套用從舊的負載累算知識。</span><span class="sxs-lookup"><span data-stu-id="e7e13-144">Distinct (heterogeneous): A new, custom round of Relevance training is required, and the knowledge accrued from the previous load cannot be applied.</span></span> 
    
    <span data-ttu-id="e7e13-145">將這些字詞參照的層次的相似性的負載之間，而非中載入的檔案。</span><span class="sxs-lookup"><span data-stu-id="e7e13-145">These terms refer to the level of similarity of files between loads and not within the loads.</span></span> 
    
- <span data-ttu-id="e7e13-p111">匯入新的檔案載入期間 （之前批次計算） 的相關性訓練、 時 Catch-up 可讓您繼續聯合的檔案設定相關性訓練。進階的 eDiscovery 不評估新的負載為類似或不同從舊的負載。它只是收集新負載的相關資訊，並讓相關性訓練以繼續新增及先前設定的檔案。</span><span class="sxs-lookup"><span data-stu-id="e7e13-p111">When importing a new file load during Relevance training (before Batch calculation), Catch-up enables you to continue Relevance training on the united file set. Advanced eDiscovery does not estimate whether the new load is similar to or distinct from the previous load. It simply collects information about the new load and enables Relevance training to continue on the new and previous sets of files.</span></span> 
    
- <span data-ttu-id="e7e13-149">如有多個問題的相關性訓練以及問題批次計算後，Catch-up 程序會執行一次的所有問題和結果會計算並顯示每個問題。</span><span class="sxs-lookup"><span data-stu-id="e7e13-149">When there are multiple issues in Relevance training as well as issues after Batch calculation, the Catch-up process is performed once for all issues, and the results are calculated and displayed for each issue.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e7e13-p112">Catch-up 樣本大小而有所不同。它取決相對於先前載入的新負載大小及數目新增新的負載之前完成的範例。Catch-up 範例通常是一組 200 至 2000 檔案從新的負載。</span><span class="sxs-lookup"><span data-stu-id="e7e13-p112">The size of the Catch-up sample may vary. It depends on the size of the new load relative to the previous loads, and on the number of samples completed before adding the new load. The Catch-up sample is typically a set of 200 to 2,000 files from the new load.</span></span> 
  
> [!TIP]
> <span data-ttu-id="e7e13-p113">Catch-up 會停止任何其他工作並需要個別的檔案標記及檢閱。因此，您可以減少負荷大型的批次中新增新的檔案時。</span><span class="sxs-lookup"><span data-stu-id="e7e13-p113">Catch-up stops any other tasks and requires individual file tagging and review. Therefore, you can reduce overhead when you add new files in large batches.</span></span> 
  
## <a name="adding-a-new-file-load-using-catch-up-and-rolling-loads"></a><span data-ttu-id="e7e13-155">新增新的檔案載入使用執行更新性和循環載入</span><span class="sxs-lookup"><span data-stu-id="e7e13-155">Adding a new file load using Catch-up and Rolling loads</span></span>

1. <span data-ttu-id="e7e13-156">在**相關性\>相關性安裝**] 索引標籤中選取**負載**。</span><span class="sxs-lookup"><span data-stu-id="e7e13-156">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
2. <span data-ttu-id="e7e13-p114">**載入管理**] 下按一下 [**+** 新增負載的圖示。會顯示確認訊息。</span><span class="sxs-lookup"><span data-stu-id="e7e13-p114">Under **Loads management**, click the **+** icon to add a load. A confirmation message is displayed.</span></span> 
    
3. <span data-ttu-id="e7e13-p115">按一下 [**是]** 繼續。會顯示 [**新增新載入**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="e7e13-p115">Click **Yes** to continue. The **Add new load** dialog is displayed.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="e7e13-161">如果動作所執行的上一個負載您只能加入新的負載。</span><span class="sxs-lookup"><span data-stu-id="e7e13-161">You can only add a new load if actions were performed to the previous load.</span></span> 
  
4. <span data-ttu-id="e7e13-p116">在**新增新載入**] 對話方塊中**載入名稱**與**描述**輸入資訊，然後按一下 [**確定]**。進階的 eDiscovery 會新增新的負載。</span><span class="sxs-lookup"><span data-stu-id="e7e13-p116">In the **Add new load** dialog, type information in **Load name** and **Description** and then click **OK**. Advanced eDiscovery adds a new load.</span></span>
    
5. <span data-ttu-id="e7e13-p117">若要匯入新的負載檔案，請按一下 [**新增檔案**]。所有的新檔案新增到此負載。進階的 eDiscovery 匯入檔案之後，它會辨識循環載入案例並指出 Catch-up 作為下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="e7e13-p117">To import the new load file, click **Add files**. All new files are added to this load. After Advanced eDiscovery imports the files, it recognizes the Rolling loads scenario and indicates Catch-up as the next step.</span></span>
    
6. <span data-ttu-id="e7e13-167">按一下 [ **Catch-up**底部的 [] 對話方塊中執行分析藍本。</span><span class="sxs-lookup"><span data-stu-id="e7e13-167">Click **Catch-up** at the bottom of the dialog to run the scenario.</span></span> 
    
    <span data-ttu-id="e7e13-168">若要允許並行檔案標示的所有問題會建立單一的 Catch-up 組，通常包含新的負載 200 至 2000 檔案。</span><span class="sxs-lookup"><span data-stu-id="e7e13-168">A single Catch-up set, typically containing 200 to 2,000 files from the new load, is created for all issues to allow concurrent file tagging.</span></span>
    
    <span data-ttu-id="e7e13-169">詳細資料所提供有關載入會類似或不同、 進階的 eDiscovery 是否已合併或自動分割載入及資訊下一個步驟中有關處理。</span><span class="sxs-lookup"><span data-stu-id="e7e13-169">Details are provided about whether loads are similar or distinct, whether Advanced eDiscovery merged or split the loads automatically, and information regarding processing in the next step.</span></span>
    
    <span data-ttu-id="e7e13-p118">您可以再標記檔案並執行的計算作業。標記啟用相關性以判斷是否相似或不同負載，並讓您可以繼續使用上一組新的檔案。</span><span class="sxs-lookup"><span data-stu-id="e7e13-p118">You can then tag files and run a calculate operation. The tagging enables Relevance to determine if loads are similar or distinct and enables you to continue working on the new set of files.</span></span>
    
7. <span data-ttu-id="e7e13-172">檢閱 Catch-up 設定之後，檢視**相關性\>追蹤**Catch-up 結果。</span><span class="sxs-lookup"><span data-stu-id="e7e13-172">After the Catch-up set is reviewed, view **Relevance \> Track** for the Catch-up results.</span></span> 
    
1. <span data-ttu-id="e7e13-173">如果新的檔案載入已新增相關性訓練期間**繼續訓練**（亦即，此問題有未尚未經過批次計算），為下一個步驟中的，無論 Catch-up 結果。</span><span class="sxs-lookup"><span data-stu-id="e7e13-173">If the new file load was added during Relevance training (meaning, the issue has not yet gone through Batch calculation), **Continue training** is the next step, regardless of the Catch-up results.</span></span> 
    
    <span data-ttu-id="e7e13-p119">為一個負載處理最新及先前載入並相關性訓練繼續聯合組上。您現在完成此程序，而且可以持續相關性訓練。</span><span class="sxs-lookup"><span data-stu-id="e7e13-p119">The new and previous loads are processed as one load and Relevance training continues on the united set. You are now finished with this procedure and can continue Relevance training.</span></span> 
    
2. <span data-ttu-id="e7e13-176">如果批次計算後新增新的負載，請執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="e7e13-176">If the new load was added after Batch calculation, proceed to the following steps.</span></span>
    
8. <span data-ttu-id="e7e13-177">批次計算後新增新載入進階的 eDiscovery 會決定索引的新負載為類似或從先前載入的不同，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e7e13-177">For new loads added after Batch calculation, Advanced eDiscovery determines if the new load is similar to or distinct from previous loads, as follows:</span></span>
    
1. <span data-ttu-id="e7e13-p120">如果載入找不到要類似： 不需要任何額外的相關性訓練。儀表板顯示建議的下一步是執行 * * 批次計算 * * 再次來計算相關性分數的新的負載。找不到要是相近，因此可以為新的檔案上執行上一個類別器分析的負載。</span><span class="sxs-lookup"><span data-stu-id="e7e13-p120">If loads were found to be similar: No additional Relevance training is necessary. The dashboard shows the recommended next step is to run ** Batch calculation ** again to calculate Relevance scores for the new load. Loads were found to be similar, so the previous classifier analysis can be run on the new files.</span></span> 
    
2. <span data-ttu-id="e7e13-p121">如果設為不同找不到載入： 不需要更多相關性訓練與下一步是 Catch-up 決策。選取 Catch-up 決策如下所示：</span><span class="sxs-lookup"><span data-stu-id="e7e13-p121">If loads were found to be distinct: More Relevance training is necessary and the next step is Catch-up decision. Select a Catch-up decision as follows:</span></span>
    
    <span data-ttu-id="e7e13-p122">如果您選取 [**合併負載**、 進階的 eDiscovery 合併舊版與新載入訓練組。雖然第一次載入八月份批次計算，則需要更多訓練。繼續一起訓練最新及先前載入。批次計算再執行一次並應忽略先前的批次計算分數。選擇此選項時相關性分數的現有載入可以重新計算，例如時的現有檔案載入檢閱尚未啟動。</span><span class="sxs-lookup"><span data-stu-id="e7e13-p122">If you select **Merge loads**, Advanced eDiscovery merges previous and new loads for the training set. Although the first load went through Batch calculation, more training is needed. Continue training new and previous loads together. Batch calculation will then run again and the previous Batch calculation scores should be ignored. Choose this selection when Relevance scores for existing loads can be recalculated, for example, when review of existing file loads has not started.</span></span>
    
    <span data-ttu-id="e7e13-p123">如果您選取 [**分割載入**，繼續相關性訓練只在新的負載。在此執行個體，舊的批次計算分數會保持原狀。選擇這個選項現有的相關性分數的現有載入無法重新計算，例如，如果已經啟動檢閱現有的負載。相關性分數的插入點開啟分別管理並無法合併。</span><span class="sxs-lookup"><span data-stu-id="e7e13-p123">If you select **Split loads**, continue Relevance training only on the new load. In this instance, previous Batch calculation scores will remain as is. Choose this option when existing Relevance scores for existing loads cannot be recalculated, for example, if review of existing loads has already started. Relevance scores are managed separately from this point onward and cannot be merged.</span></span>
    
3. <span data-ttu-id="e7e13-192">按一下 [**繼續訓練**。</span><span class="sxs-lookup"><span data-stu-id="e7e13-192">Click **Continue training**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e7e13-193">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e7e13-193">See also</span></span>

[<span data-ttu-id="e7e13-194">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="e7e13-194">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="e7e13-195">定義的問題和指派使用者</span><span class="sxs-lookup"><span data-stu-id="e7e13-195">Defining issues and assigning users</span></span>](define-issues-and-assign-users.md)
  
[<span data-ttu-id="e7e13-196">定義反白顯示關鍵字和進階選項</span><span class="sxs-lookup"><span data-stu-id="e7e13-196">Defining highlighted keywords and advanced options</span></span>](define-highlighted-keywords-and-advanced-options.md)

