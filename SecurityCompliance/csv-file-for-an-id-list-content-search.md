---
title: 準備 Office 365 中的內容搜尋識別碼清單的 CSV 檔案
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/21/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid: MOE150
ms.assetid: 82c97bb4-2b64-4edc-804d-cedbda525d22
description: 使用 Results.csv 或花很多 Items.csv 檔案從現有的內容搜尋來建立識別碼清單搜尋會傳回特定電子郵件訊息。識別碼清單搜尋通常可用來傳回部分已編製索引的信箱項目。
ms.openlocfilehash: 558a8512ed133995b2cc1d0d8b78fd7f08d11168
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296736"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search-in-office-365"></a><span data-ttu-id="020c2-104">準備 Office 365 中的內容搜尋識別碼清單的 CSV 檔案</span><span class="sxs-lookup"><span data-stu-id="020c2-104">Prepare a CSV file for an ID list Content Search in Office 365</span></span>

<span data-ttu-id="020c2-p102">您可以搜尋特定信箱的電子郵件及其他使用 Exchange 識別碼清單的信箱項目。若要建立 （正式稱為 「 目標的搜尋 」） 的識別碼清單搜尋，您提交識別特定信箱的項目要搜尋的逗號分隔的值 (CSV) 檔案。此 CSV 檔案中使用**Results.csv**檔案或匯出內容的搜尋結果或從內容的搜尋報告與現有的內容搜尋匯出時所包含的**花很多 Items.csv**檔案。然後您編輯一個指出搜尋，然後建立新的識別碼清單中搜尋和提交 CSV 檔案的特定項目這些檔案。</span><span class="sxs-lookup"><span data-stu-id="020c2-p102">You can search for specific mailbox email messages and other mailbox items using a list of Exchange IDs. To create an ID list search (formally called a targeted search), you submit a comma separated value (CSV) file that identifies the specific mailbox items to search for. For this CSV file you use the **Results.csv** file or the **Unindexed Items.csv** file that are included when you export the Content Search results or export a Content Search report from and existing Content Search. Then you edit one of these files to indicate the specific items to search for, and then create a new ID list search and submit the CSV file.</span></span> 
  
<span data-ttu-id="020c2-109">以下是建立識別碼清單中搜尋的程序的快速概觀。</span><span class="sxs-lookup"><span data-stu-id="020c2-109">Here's a quick overview of the process for creating an ID list search.</span></span>
  
1. <span data-ttu-id="020c2-110">建立並執行新的或導引式的內容搜尋安全性&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="020c2-110">Create and run a new or guided Content Search in the Security &amp; Compliance Center.</span></span>
    
2. <span data-ttu-id="020c2-p103">匯出內容的搜尋結果或匯出內容的搜尋報告。如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="020c2-p103">Export the content search results or export the content search report. For more information, see:</span></span>
    
    - [<span data-ttu-id="020c2-113">從 Office 365 安全性匯出內容的搜尋結果&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="020c2-113">Export Content Search results from the Office 365 Security &amp; Compliance Center</span></span>](export-search-results.md)
    
    - [<span data-ttu-id="020c2-114">匯出內容搜尋報告</span><span class="sxs-lookup"><span data-stu-id="020c2-114">Export a Content Search report</span></span>](export-a-content-search-report.md)
    
3. <span data-ttu-id="020c2-p104">編輯**Results.csv**檔案或**花很多 Items.csv**並找出您想要包含在識別碼清單中搜尋特定的信箱項目。請參閱準備 CSV 檔案的識別碼清單中搜尋的[指示](#prepare-the-csv-file-for-an-id-list-search)。</span><span class="sxs-lookup"><span data-stu-id="020c2-p104">Edit the **Results.csv** file or the **Unindexed Items.csv** and identify the specific mailbox items that you want to include in the ID list search. See the [instructions](#prepare-the-csv-file-for-an-id-list-search) for preparing a CSV file for an ID list search.</span></span> 
    
4. <span data-ttu-id="020c2-p105">建立新的識別碼清單搜尋 （請參閱[指示](#create-an-id-list-search)） 並送出您所準備的 CSV 檔案。建立搜尋查詢只會搜尋 CSV 檔案中所選取的項目。</span><span class="sxs-lookup"><span data-stu-id="020c2-p105">Create a new ID list search (see the [instructions](#create-an-id-list-search)) and submit the CSV file that you prepared. The search query that's created will only search for the items selected in the CSV file.</span></span>
    
> [!NOTE]
> <span data-ttu-id="020c2-p106">僅支援的信箱項目識別碼清單中搜尋。您無法搜尋的 SharePoint 和 OneDrive 文件中的識別碼清單搜尋。</span><span class="sxs-lookup"><span data-stu-id="020c2-p106">ID list searches are only supported for mailbox items. You can't search for SharePoint and OneDrive documents in an ID list search.</span></span> 
  
 <span data-ttu-id="020c2-p107">**為什麼要選擇建立識別碼清單搜尋？** 如果您是無法判斷回應**Results.csv**或**花很多 Items.csv**檔案中的中繼資料為基礎的 eDiscovery 要求項目時，您可以使用的識別碼清單搜尋來尋找、 預覽，，然後將匯出若要判斷是否已定義的項目回應正在調查的大小寫。識別碼清單搜尋通常可用來搜尋並傳回一組特定的編製索引的項目。</span><span class="sxs-lookup"><span data-stu-id="020c2-p107">**Why create an ID list search?** If you're unable to determine if an item is responsive to an eDiscovery request based on the metadata in the **Results.csv** or **Unindexed Items.csv** files, you can use an ID list search to find, preview, and then export that item to determine if it's responsive to the case you're investigating. ID list searches are typically used to search for and return a specific set of unindexed items.</span></span> 
  
## <a name="prepare-the-csv-file-for-an-id-list-search"></a><span data-ttu-id="020c2-124">準備 CSV 檔案的識別碼清單中搜尋</span><span class="sxs-lookup"><span data-stu-id="020c2-124">Prepare the CSV file for an ID list search</span></span>

<span data-ttu-id="020c2-p108">您將匯出的搜尋結果或內容的搜尋報表之後，您可以執行下列步驟來準備 CSV 檔案的識別碼清單中搜尋。此 CSV 檔案會識別每個項目識別碼清單搜尋中。</span><span class="sxs-lookup"><span data-stu-id="020c2-p108">After you export the search results or report for a content search, you can perform the following steps to prepare the CSV file for an ID list search. This CSV file will identify every item in the ID list search.</span></span>
  
<span data-ttu-id="020c2-p109">請注意您可以使用 CSV 檔案中包含 SharePoint 網站及 OneDrive 帳戶搜尋但是您可以選取 [*只有*識別碼清單中搜尋的信箱項目。如果您選取文件在 SharePoint 或 OneDrive、 CSV 檔案將會失敗驗證時建立識別碼清單中搜尋。</span><span class="sxs-lookup"><span data-stu-id="020c2-p109">Note that you can use a CSV file from a search that included SharePoint sites and OneDrive accounts, but you can select  *only*  mailbox items for an ID list search. If you select a document in SharePoint or OneDrive, the CSV file will fail validation when you create an ID list search.</span></span> 
  
1. <span data-ttu-id="020c2-129">在 Excel 中開啟**Results.csv**或**花很多 Items.csv**檔案。</span><span class="sxs-lookup"><span data-stu-id="020c2-129">Open the **Results.csv** or **Unindexed Items.csv** file in Excel.</span></span> 
    
2. <span data-ttu-id="020c2-p110">插入新欄並將其命名為**選取**。並不重要插入資料行的位置。為了方便，請考慮插入左邊的第一欄。</span><span class="sxs-lookup"><span data-stu-id="020c2-p110">Insert a new column and name it **Selected**. It doesn't matter where you insert the column. For convenience, consider inserting it to the left of the first column.</span></span>
    
3. <span data-ttu-id="020c2-p111">在 [**選取**] 欄中輸入 **[是]** 中的儲存格會對應至您想要搜尋的項目。針對您想要搜尋的每個項目重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="020c2-p111">In the **Selected** column, type **Yes** in the cell that corresponds to the item that you want to search for. Repeat this step for every item that you want to search for.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="020c2-p112">當您在 Excel 中開啟的 CSV 檔案時，**文件識別碼**] 欄中的資料格式會變更為**一般**。這會產生工程型註解中顯示的項目之文件識別碼。例如，"481037338205"的識別碼會顯示為"4.81037E + 11"的文件您必須執行下一個步驟來變更的資料格式的**文件識別碼**] 欄的**號碼**來還原正確的格式的文件識別碼。如果您不這麼做，會使用 CSV 檔案的識別碼清單搜尋將會失敗。</span><span class="sxs-lookup"><span data-stu-id="020c2-p112">When you open the CSV file in Excel, the data format for the **Document ID** column is changed to **General**. This results in displaying the document ID for an item in scientific notation. For example, the document ID of "481037338205" is displayed as "4.81037E+11" You have to perform the next steps to change the data format of the **Document ID** column to **Number** to restore the correct format for the document ID. If you don't do this, the ID list search that uses the CSV file will fail.</span></span> 
  
4. <span data-ttu-id="020c2-139">以滑鼠右鍵按一下 [整個**文件識別碼**] 欄，並選取**儲存格格式**。</span><span class="sxs-lookup"><span data-stu-id="020c2-139">Right-click the entire **Document ID** column and select **Format Cells**.</span></span>
    
5. <span data-ttu-id="020c2-140">在 [**類別**] 方塊中，按一下 [**數字**。</span><span class="sxs-lookup"><span data-stu-id="020c2-140">In the **Category** box, click **Number**.</span></span>
    
6. <span data-ttu-id="020c2-p113">變更的小數位數設為**0**，然後再按一下 **[確定]** 以儲存變更。請注意 [文件識別碼] 欄中的值會變更為 [數字。</span><span class="sxs-lookup"><span data-stu-id="020c2-p113">Change the number of decimal places to **0**, and then click **OK** to save your changes. Notice that the values in the Document ID column are changed to numbers.</span></span> 
    
    <span data-ttu-id="020c2-143">以下是範例 CSV 檔案已經準備好要送出識別碼清單內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="020c2-143">Here's an example of the a CSV file that's ready to be submitted for a ID list content search.</span></span>
    
    ![CSV 檔案的目標內容搜尋的範例](media/8371b8cb-1638-496e-9be1-fe1565757d67.png)
  
7. <span data-ttu-id="020c2-p114">另存 CSV 檔案或使用 [**另存新檔**儲存的檔案與不同的檔案名稱。在這兩種情況下，請務必使用 CSV 格式儲存檔案。</span><span class="sxs-lookup"><span data-stu-id="020c2-p114">Save the CSV file or use **Save As** to the save the file with different file name. In both cases, be sure to save the file with the CSV format.</span></span> 
  
## <a name="create-an-id-list-search"></a><span data-ttu-id="020c2-147">建立識別碼清單中搜尋</span><span class="sxs-lookup"><span data-stu-id="020c2-147">Create an ID list search</span></span>

<span data-ttu-id="020c2-148">下一步是建立新的識別碼清單內容搜尋並送出在上一個步驟準備 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="020c2-148">The next step is to create a new ID list Content Search and submit the CSV file that you prepared in the previous step.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="020c2-p115">您應建立識別碼清單搜尋不得超過 2 天後內容搜尋從匯出的結果或報表。如果搜尋結果或報告其中匯出 2 天以上，您應該重新匯出的搜尋結果或產生更新的 CSV 檔案的報表。然後您可以準備其中一個更新的 CSV 檔案並使用它來建立識別碼清單中搜尋。</span><span class="sxs-lookup"><span data-stu-id="020c2-p115">You should create an ID list search no more than 2 days after exporting the results or report from a Content Search. If the search results or report where exported more than 2 days ago, you should re-export the search results or report to generate updated CSV files. Then you can prepare one of the updated CSV files and use it to create an ID list search.</span></span> 
  
1. <span data-ttu-id="020c2-152">安全性&amp;規範管理中心，移至**搜尋&amp;調查** \> **內容搜尋**。</span><span class="sxs-lookup"><span data-stu-id="020c2-152">In the Security &amp; Compliance Center, go to **Search &amp; investigation** \> **Content search**.</span></span>
    
2. <span data-ttu-id="020c2-153">在 [**搜尋**] 頁面上，按一下 [箭號下一步]![新增圖示](media/8ee52980-254b-440b-99a2-18d068de62d3.gif)**新的搜尋**，然後按一下 [**搜尋依據識別碼清單**。</span><span class="sxs-lookup"><span data-stu-id="020c2-153">On the **Search** page, click the arrow next to ![Add icon](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New search**, and then click **Search by ID List**.</span></span>
    
    ![從新的 [搜尋] 下拉式清單中按一下 [依識別碼清單的搜尋](media/e65f9942-09b2-4127-865e-e64029a590df.png)
  
3. <span data-ttu-id="020c2-155">**識別碼清單來搜尋**彈出式、 上命名為搜尋 （並選擇性地說明它） 然後按一下 [**瀏覽**並在上一個步驟中選取您所準備的 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="020c2-155">On the **Search by ID List** flyout, name the search (and optionally describe it) and then click **Browse** and select the CSV file that you prepared in the previous step.</span></span> 
    
    <span data-ttu-id="020c2-p116">Office 365 嘗試驗證 CSV 檔案。如果驗證失敗時，會顯示錯誤訊息，可能會協助您疑難排解驗證錯誤。CSV 檔案具有成功驗證來建立識別碼清單中搜尋。</span><span class="sxs-lookup"><span data-stu-id="020c2-p116">Office 365 attempts to validate the CSV file. If the validation is unsuccessful, an error message is displayed that might help you troubleshoot the validation errors. The CSV file has to be successfully validated to create an ID list search.</span></span>
    
4. <span data-ttu-id="020c2-159">之後 CSV 檔案會成功驗證、 按一下 [**搜尋**] 以建立識別碼清單中搜尋。</span><span class="sxs-lookup"><span data-stu-id="020c2-159">After the CSV file is successfully validated, click **Search** to create the ID list search.</span></span> 
    
    <span data-ttu-id="020c2-160">以下是預估的搜尋結果及產生的識別碼清單搜尋查詢的範例。</span><span class="sxs-lookup"><span data-stu-id="020c2-160">Here's an example of the estimated search results and the query that's generated for an ID list search.</span></span>
    
    ![在詳細資料窗格中搜尋目標內容的搜尋的查詢](media/dbd9e570-c04b-4056-a8a7-37e9916ec683.png)
  
    <span data-ttu-id="020c2-162">請注意 [識別碼] 搜尋的統計資料中顯示的估計項目數應符合您所選取 CSV 檔案中的項目數。</span><span class="sxs-lookup"><span data-stu-id="020c2-162">Note that the number of estimated items displayed in statistics for the ID search should match the number of items that you selected in the CSV file.</span></span>
    
5. <span data-ttu-id="020c2-163">預覽或匯出識別碼清單搜尋傳回的項目。</span><span class="sxs-lookup"><span data-stu-id="020c2-163">Preview or export the items returned by the ID list search.</span></span>
    
> [!NOTE]
> <span data-ttu-id="020c2-p117">如果您將信箱移動後建立識別碼清單搜尋，搜尋查詢不會傳回指定的項目。那是因為信箱項目**DocumentId**屬性已變更移動信箱時。在極罕見的執行個體中移動信箱時建立的識別碼清單搜尋之後，您應建立新的內容搜尋 （或更新現有的內容搜尋的搜尋結果），然後匯出搜尋結果] 或 [回報至產生更新可用的 CSV 檔案 若要建立新的識別碼清單中搜尋。</span><span class="sxs-lookup"><span data-stu-id="020c2-p117">If you move a mailbox after creating an ID list search, the query for the search won't return the specified items. That's because the **DocumentId** property for mailbox items are changed when a mailbox is moved. In the rare instance when a mailbox is moved after you create an ID list search, you should create a new content search (or update the search results for the existing content search) and then export the search results or report to generate updated CSV files that can be used to create a new ID list search.</span></span> 
