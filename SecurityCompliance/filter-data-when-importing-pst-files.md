---
title: 篩選資料時將 PST 檔案匯入 Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/24/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid: MOE150
ms.assetid: 26af16df-34cd-4f4a-b893-bc1d2e74039e
description: '在 Office 365 匯入服務內使用新的智慧型匯入功能篩選的實際取得匯入至目標信箱項目。智慧型匯入可讓您主動決定何種資料匯入以及要保留背後的項目。智慧型匯入也提供前瞻您正在匯入至 Office 365 的資料。 '
ms.openlocfilehash: c90d9df62c7d8c411196b283acec37959fc95e57
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038196"
---
# <a name="filter-data-when-importing-pst-files-to-office-365"></a><span data-ttu-id="a2599-105">篩選資料時將 PST 檔案匯入 Office 365</span><span class="sxs-lookup"><span data-stu-id="a2599-105">Filter data when importing PST files to Office 365</span></span>

<span data-ttu-id="a2599-p102">使用 Office 365 匯入服務中的新的智慧型匯入功能來篩選實際取得匯入至目標信箱的 PST 檔案中的項目。以下是其運作方式：</span><span class="sxs-lookup"><span data-stu-id="a2599-p102">Use the new Intelligent Import feature in the Office 365 Import service to filter the items in PST files that actually get imported to the target mailboxes. Here's how it works:</span></span>
  
- <span data-ttu-id="a2599-108">建立並送出 PST 匯入工作後，PST 檔案上傳至 Microsoft 雲端 Azure 儲存區中。</span><span class="sxs-lookup"><span data-stu-id="a2599-108">After you create and submit a PST import job, PST files are uploaded to an Azure storage area in the Microsoft cloud.</span></span>
    
- <span data-ttu-id="a2599-109">Office 365 識別信箱項目和 PST 檔案中包含的不同郵件類型的保留時間下限，安全且安全的方式、 分析 PST 檔案中的資料。</span><span class="sxs-lookup"><span data-stu-id="a2599-109">Office 365 analyzes the data in the PST files, in a safe and secure manner, by identifying the age of the mailbox items and the different message types included in the PST files.</span></span>
    
- <span data-ttu-id="a2599-p103">如果分析已完成資料已準備好要匯入，您必須或修剪藉由設定控制哪些資料取得匯入的篩選器來匯入資料的 PST 檔案中的所有資料匯入選項。例如，您可以選擇：</span><span class="sxs-lookup"><span data-stu-id="a2599-p103">When the analysis is complete and the data is ready to import, you have the option to import all data in the PST files as is or trim the data that's imported by setting filters that control what data gets imported. For example, you can choose to:</span></span>
    
  - <span data-ttu-id="a2599-112">匯入特定保留的項的目。</span><span class="sxs-lookup"><span data-stu-id="a2599-112">Import only items of a certain age.</span></span>
    
  - <span data-ttu-id="a2599-113">選取 [匯入訊息類型。</span><span class="sxs-lookup"><span data-stu-id="a2599-113">Import selected message types.</span></span>
    
  - <span data-ttu-id="a2599-114">排除特定人員所傳送或接收的郵件。</span><span class="sxs-lookup"><span data-stu-id="a2599-114">Exclude messages sent or received by specific people.</span></span>
    
- <span data-ttu-id="a2599-115">設定篩選設定之後，Office 365 匯入符合目標信箱匯入工作中所指定的篩選準則的資料。</span><span class="sxs-lookup"><span data-stu-id="a2599-115">After you configure the filter settings, Office 365 imports only the data that meets the filtering criteria to the target mailboxes specified in the import job.</span></span>
    
<span data-ttu-id="a2599-116">下圖顯示智慧型匯入程序，並會醒目提示您執行的工作與 Office 365 所執行的工作。</span><span class="sxs-lookup"><span data-stu-id="a2599-116">The following graphic shows the Intelligent Import process, and highlights the tasks you perform and the tasks performed by Office 365.</span></span>
  
![Office 365 中的智慧型匯入程序](media/f2ec309b-11f5-48f2-939c-a6ff72152d14.png)
  
## <a name="before-you-begin"></a><span data-ttu-id="a2599-118">開始之前</span><span class="sxs-lookup"><span data-stu-id="a2599-118">Before you begin</span></span>

- <span data-ttu-id="a2599-p104">本主題中的步驟假設您已建立 PST 匯入工作匯入 Office 365 服務中使用網路上傳或磁碟機傳送。如需逐步說明，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="a2599-p104">The steps in this topic assume that you've created a PST import job in the Office 365 Import service by using network upload or drive shipping. For step-by-step instructions, see one of the following topics:</span></span>
    
  - [<span data-ttu-id="a2599-121">使用網路上傳將 PST 檔案匯入 Office 365</span><span class="sxs-lookup"><span data-stu-id="a2599-121">Use network upload to import PST files to Office 365</span></span>](use-network-upload-to-import-pst-files.md)
    
  - [<span data-ttu-id="a2599-122">使用磁碟機運送將 PST 檔案匯入 Office 365</span><span class="sxs-lookup"><span data-stu-id="a2599-122">Use drive shipping to import PST files to Office 365</span></span>](use-drive-shipping-to-import-pst-files-to-office-365.md)
    
- <span data-ttu-id="a2599-p105">使用網路上傳建立匯入工作之後，請在匯入的匯入工作的狀態頁面上的 Office 365 安全性&amp;規範中心設為**進行中的分析**，這表示 Office 365 分析 PST 檔案中的資料，上傳。按一下 [**重新整理**![重新整理](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png)更新匯入工作的狀態。</span><span class="sxs-lookup"><span data-stu-id="a2599-p105">After you create an import job by using network upload, the status for the import job on the Import page in Office 365 Security &amp; Compliance Center is set to **Analysis in progress**, which means that Office 365 is analyzing the data in the PST files that you uploaded. Click **Refresh**![refresh](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) to update the status for the import job.</span></span> 
    
- <span data-ttu-id="a2599-125">傳送匯入工作的磁碟機，資料會分析由 Office 365 後 Microsoft 資料中心人員接聽您的硬碟與 PST 檔案上傳至您的組織的 Azure 儲存區。</span><span class="sxs-lookup"><span data-stu-id="a2599-125">For drive shipping import jobs, the data will be analyzed by Office 365 after Microsoft data center personnel receive your hard drive and upload the PST files to the Azure storage area for your organization.</span></span>
  
## <a name="filter-data-that-gets-imported-to-mailboxes"></a><span data-ttu-id="a2599-126">篩選會取得匯入至信箱的資料</span><span class="sxs-lookup"><span data-stu-id="a2599-126">Filter data that gets imported to mailboxes</span></span>

<span data-ttu-id="a2599-127">您已建立後 PST 匯入工作，請遵循下列步驟之前進行篩選資料匯入 Office 365]。</span><span class="sxs-lookup"><span data-stu-id="a2599-127">After you've created a PST import job, follow these steps to filter the data before you import it to Office 365.</span></span>
  
1. <span data-ttu-id="a2599-128">移至 [[https://protection.office.com/](https://protection.office.com/)並登入使用 Office 365 組織中系統管理員帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="a2599-128">Go to [https://protection.office.com/](https://protection.office.com/) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="a2599-129">Office 365 安全性的左窗格中&amp;規範中心，按一下 [**資料控管** \> **匯入**。</span><span class="sxs-lookup"><span data-stu-id="a2599-129">In the left pane of the Office 365 Security &amp; Compliance Center, click **Data governance** \> **Import**.</span></span>
    
    <span data-ttu-id="a2599-p106">在 [**匯入**] 頁面上列出您組織的匯入工作。請注意**完成分析**的**狀態**] 欄值會指出有已由 Office 365 分析並準備好讓您匯入的匯入工作。</span><span class="sxs-lookup"><span data-stu-id="a2599-p106">The import jobs for your organization are listed on the **Import** page. Note that the **Analysis completed** value in the **Status** column indicates the import jobs that have been analyzed by Office 365 and are ready for you to import.</span></span> 
    
    ![分析完成狀態表示 Office 365 有分析 PST 檔案中的資料](media/de5294f4-f0ba-4b92-a48a-a4b32b6da490.png)
  
3. <span data-ttu-id="a2599-133">按一下 [**準備好要匯入 Office 365**您想要完成的匯入工作。</span><span class="sxs-lookup"><span data-stu-id="a2599-133">Click **Ready to import to Office 365** for the import job that you want to complete.</span></span> 
    
    <span data-ttu-id="a2599-134">飛入] 頁面會顯示與 PST 檔案的相關資訊及匯入工作的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="a2599-134">A fly out page is displayed with information about the PST files and other information about the import job.</span></span>
    
4. <span data-ttu-id="a2599-135">按一下 [**匯入至 Office 365**。</span><span class="sxs-lookup"><span data-stu-id="a2599-135">Click **Import to Office 365**.</span></span>
    
    <span data-ttu-id="a2599-p107">會顯示 [**篩選資料**] 頁面。包含資料前瞻相關匯入工作，包括資料的保留天數的相關資訊的 PST 檔案中的資料。</span><span class="sxs-lookup"><span data-stu-id="a2599-p107">The **Filter your data** page is displayed. It contains data insights about the data in the PST files for the import job, including information about the age of the data.</span></span> 
    
    ![篩選資料] 頁面會顯示資料觀點的 PST 檔案匯入工作](media/3b537ec0-25a4-45a4-96d5-a429e2a33128.png)
  
5. <span data-ttu-id="a2599-139">根據您想要是否修剪匯入的資料到 Office 365 底下**您要篩選資料吗？**，執行下列其中一個動作：</span><span class="sxs-lookup"><span data-stu-id="a2599-139">Based on whether or not you want to trim the data that's imported to Office 365, under **Do you want to filter your data?**, do one of the following:</span></span>
    
    <span data-ttu-id="a2599-p108">a.按一下 [**是，我要匯入之前加以篩選**修剪您匯入資料] 和 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="a2599-p108">a. Click **Yes, I want to filter it before importing** to trim the data that you import, and then click **Next**.</span></span>
    
    <span data-ttu-id="a2599-142">**Office 365] 頁面上的匯入資料**] 頁面上會從 Office 365 執行分析的詳細的資料前瞻一起顯示。</span><span class="sxs-lookup"><span data-stu-id="a2599-142">The **Import data to Office 365 page** page is displayed with detailed data insights from the analysis that Office 365 performed.</span></span> 
    
    ![Office 365 會顯示從其分析的 PST 檔案的詳細的資料觀點](media/4881205f-0288-4c32-a440-37e2160295f2.png)
  
    <span data-ttu-id="a2599-p109">在此頁面上圖顯示要匯入的資料量。PST 檔案中找到的每個郵件類型的資訊會顯示在此圖形。您可以將游標滑鼠停留在每個長條圖，以顯示該郵件類型的特定資訊。也有不同的保留時間下限值依據 PST 檔案的分析的下拉式清單。當您在下拉式清單中選取存留期時，此圖形會更新以顯示所選的存留期的匯入資料量。</span><span class="sxs-lookup"><span data-stu-id="a2599-p109">The graph on this page shows the amount of data that will be imported. Information about each message type found in the PST files is displayed in the graph. You can hover the cursor over each bar to display specific information about that message type. There is also a drop-down list with different age values based on the analysis of the PST files. When you select an age in the drop-down list, the graph is updated to show how much data will be imported for the selected age.</span></span> 
    
    <span data-ttu-id="a2599-p110">b。 若要設定其他篩選器以減少匯入的資料，請按一下 [**更多的篩選選項**。</span><span class="sxs-lookup"><span data-stu-id="a2599-p110">b. To configure addition filters to reduce the amount of data that's imported, click **More filtering options**.</span></span>
    
    ![修剪匯入的資料 [更多選項] 頁面上設定篩選](media/3f8d68c3-3fe2-4b4e-9488-b368b98fa9fe.png)
  
    <span data-ttu-id="a2599-152">您可以設定這些篩選器：</span><span class="sxs-lookup"><span data-stu-id="a2599-152">You can configure these filters:</span></span>
    
      - <span data-ttu-id="a2599-p111">**存留期**-選取要匯入保留時間下限因此唯一項目會指定保留時間比還要新。請參閱如需 Office 365 如何判斷**保留**篩選存留期 bucket 詳細說明[的詳細資訊](filter-data-when-importing-pst-files.md#moreinfo)] 區段。</span><span class="sxs-lookup"><span data-stu-id="a2599-p111">**Age** - Select an age so only items that are newer than the specified age will be imported. See the [More information](filter-data-when-importing-pst-files.md#moreinfo) section for a description about how Office 365 determines the age buckets for the **Age** filter.</span></span> 
    
      - <span data-ttu-id="a2599-p112">**類型**-此區段會顯示在匯入工作的 PST 檔案中找到的所有郵件類型。您可以取消核取您要排除的郵件類型] 旁的方塊。請注意您無法排除此訊息類型。請參閱清單[的詳細資訊](filter-data-when-importing-pst-files.md#moreinfo)] 區段的 [其他] 類別中隨附的信箱項目。</span><span class="sxs-lookup"><span data-stu-id="a2599-p112">**Type** - This section shows all the message types that were found in the PST files for the import job. You can uncheck a box next to a message type that you want to exclude. Note that you can't exclude the Other message type. See the [More information](filter-data-when-importing-pst-files.md#moreinfo) section for a list of mailbox items that are included in the Other category.</span></span> 
    
      - <span data-ttu-id="a2599-p113">**使用者**-您可以排除郵件已傳送或接收到特定的人員。若要排除人員會出現在 [從： 欄位，設:] 欄位中，] 或 [副本:] 欄位的訊息，按一下該收件者類型旁的 [**排除的使用者**。按一下 [**新增**] 類型之人員的電子郵件地址 （SMTP 位址）![圖示](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)將它們新增至已排除的收件者的類型的使用者清單，然後按 [**儲存**] 以儲存已排除的使用者清單。</span><span class="sxs-lookup"><span data-stu-id="a2599-p113">**Users** - You can exclude messages that are sent or received by specific people. To exclude people who appear in the From: field, To: field, or the Cc: field of messages, click **Exclude users** next to that recipient type. Type the email address (SMTP address) of the person, click **Add**![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) to add them to the list of excluded users for that recipient type, and then click **Save** to save the list of excluded users.</span></span> 
    
        > [!NOTE]
        > <span data-ttu-id="a2599-p114">Office 365 不會顯示資料的觀點所產生的設定**使用者**的篩選器。不過，如果您將此篩選来排除特定人員所傳送或接收的郵件，這些訊息會排除在實際匯入程序期間。</span><span class="sxs-lookup"><span data-stu-id="a2599-p114">Office 365 doesn't show data insights that result from setting the **People** filter. However, if you set this filter to exclude messages sent or received by specific people, those messages will be excluded during the actual import process.</span></span> 
  
    <span data-ttu-id="a2599-p115">c.按一下 [**套用\*\*\*\*其他篩選選項**飛入] 以儲存您的篩選設定] 頁面中。</span><span class="sxs-lookup"><span data-stu-id="a2599-p115">c. Click **Apply** in the **More filtering options** fly out page to save your filter settings.</span></span> 
    
    <span data-ttu-id="a2599-p116">根據您的篩選設定更新**至 Office 365 的匯入資料**] 頁面上的觀點的資料，包括要匯入資料的總量根據篩選設定。請注意，也會顯示篩選器設定的摘要。您可以按一下 [**編輯**] 旁的篩選器在必要時變更設定。</span><span class="sxs-lookup"><span data-stu-id="a2599-p116">The data insights on the **Import data to Office 365** page are updated based on your filter settings, including the total amount of data that will be imported based on the filter settings. Note that a summary of the filter settings is also shown. You can click **Edit** next to a filter to change the setting if necessary.</span></span> 
    
    ![根據您的篩選設定更新資料觀點](media/897e20fb-3b13-44c3-9d56-9f330750f2a3.png)
  
    <span data-ttu-id="a2599-p117">d.按一下 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="a2599-p117">d. Click **Next**.</span></span>
    
    <span data-ttu-id="a2599-p118">狀態 」 頁面會隨即顯示顯示篩選設定。同樣地，您可以編輯的任何篩選器設定。</span><span class="sxs-lookup"><span data-stu-id="a2599-p118">A status page is displayed showing your filter settings. Again, you can edit any of the filter settings.</span></span>
    
    <span data-ttu-id="a2599-p119">e.按一下 [**匯入資料**以啟動匯入]。請注意會顯示 [要匯入資料的總量。</span><span class="sxs-lookup"><span data-stu-id="a2599-p119">e. Click **Import data** to start the import . Note that the total amount of data that will be imported is displayed.</span></span> 
    
    <span data-ttu-id="a2599-177">或</span><span class="sxs-lookup"><span data-stu-id="a2599-177">Or</span></span>
    
    <span data-ttu-id="a2599-p120">a.[PST 檔案中的所有資料匯入 Office 365 的 [**否，我要匯入每個項目**] 和 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="a2599-p120">a. Click **No, I want to import everything** to import all data in the PST files to Office 365, and then click **Next**.</span></span>
    
    <span data-ttu-id="a2599-p121">b.在**匯入至 Office 365 的資料**] 頁面上按一下 [啟動匯入的 [**匯入資料**]。請注意會顯示 [要匯入資料的總量。</span><span class="sxs-lookup"><span data-stu-id="a2599-p121">b. On the **Import data to Office 365** page, click **Import data** to start the import. Note that the total amount of data that will be imported is displayed.</span></span> 
    
6. <span data-ttu-id="a2599-p122">在 [**匯入**] 頁面上，按一下 [**重新整理**![重新整理](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png)。匯入工作的狀態會顯示在 [**狀態**] 欄中。</span><span class="sxs-lookup"><span data-stu-id="a2599-p122">On the **Import** page, click **Refresh** ![refresh](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png). The status for the import job is displayed in the **Status** column.</span></span> 
    
7. <span data-ttu-id="a2599-185">按一下匯入該工作以顯示更多詳細的資訊，例如每個 PST 檔案與您所設定的篩選器設定的狀態。</span><span class="sxs-lookup"><span data-stu-id="a2599-185">Click the import the job to display more detailed information, such as the status for each PST file and the filter settings that you configured.</span></span>

  
## <a name="more-information"></a><span data-ttu-id="a2599-186">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="a2599-186">More information</span></span>

- <span data-ttu-id="a2599-p123">Office 365 如何決定保留篩選的增量？當 Office 365 分析 PST 檔案時，則它會在每個項目的送出或收到的時間戳記 （如果項目已傳送和接收 timestamp，便會選取的最早日期）。然後 Office 365 的時間戳記的年份值會查看並比較判斷項目的存留期為目前日期。這些年齡然後用於下拉式清單中的值為**保留**篩選。例如，如果 PST 檔案具有來自 2016年、 2015、 和 2014、 郵件則中**保留**篩選值會是**1 年**、 **2 年**、 及**3 年**。</span><span class="sxs-lookup"><span data-stu-id="a2599-p123">How does Office 365 determine the increments for the age filter? When Office 365 analyzes a PST file, it looks at the sent or received time stamp of each item (if an item has both a sent and received timestamp, the oldest date is selected). Then Office 365 looks at the year value for that timestamp and compares it to the current date to determine the age of the item. These ages are then used as the values in the drop-down list for the **Age** filter. For example, if a PST file has messages from 2016, 2015, and 2014, then values in the **Age** filter would be **1 year**, **2 years**, and **3 years**.</span></span>
    
- <span data-ttu-id="a2599-p124">下表列出**其他**類別中 [**其他選項**飛入] 頁面上的**類型**篩選中包含的郵件類型 （請參閱前一個程序的步驟 5b）。目前，您無法在當您匯入 Office 365 的 Pst 排除"其他"類別中的項目。</span><span class="sxs-lookup"><span data-stu-id="a2599-p124">The following table lists the message types that are included in the **Other** category in the **Type** filter on the **More options** fly out page (see Step 5b in the previous procedure). Currently, you can't exclude items in the "Other" category when you import PSTs to Office 365.</span></span> 
    
    |<span data-ttu-id="a2599-194">**郵件類別識別項**</span><span class="sxs-lookup"><span data-stu-id="a2599-194">**Message class ID**</span></span>|<span data-ttu-id="a2599-195">**使用此郵件類別的信箱項目**</span><span class="sxs-lookup"><span data-stu-id="a2599-195">**Mailbox items that use this message class**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="a2599-196">IPM。活動</span><span class="sxs-lookup"><span data-stu-id="a2599-196">IPM.Activity</span></span>  <br/> |<span data-ttu-id="a2599-197">日誌項目</span><span class="sxs-lookup"><span data-stu-id="a2599-197">Journal entries</span></span>  <br/> |
    |<span data-ttu-id="a2599-198">IPM。文件</span><span class="sxs-lookup"><span data-stu-id="a2599-198">IPM.Document</span></span>  <br/> |<span data-ttu-id="a2599-199">文件及檔案 （未附加至電子郵件訊息）</span><span class="sxs-lookup"><span data-stu-id="a2599-199">Documents and files (not attached to an email message)</span></span>  <br/> |
    |<span data-ttu-id="a2599-200">IPM。檔案</span><span class="sxs-lookup"><span data-stu-id="a2599-200">IPM.File</span></span>  <br/> |<span data-ttu-id="a2599-201">（與 IPM 相同。文件）</span><span class="sxs-lookup"><span data-stu-id="a2599-201">(same as IPM.Document)</span></span>  <br/> |
    |<span data-ttu-id="a2599-202">IPM。Note.IMC.Notification</span><span class="sxs-lookup"><span data-stu-id="a2599-202">IPM.Note.IMC.Notification</span></span>  <br/> |<span data-ttu-id="a2599-203">傳送網際網路郵件連線，這是 Exchange Server 到網際網路的閘道的報告</span><span class="sxs-lookup"><span data-stu-id="a2599-203">Reports sent by Internet Mail Connect, which is the Exchange Server gateway to the Internet</span></span>  <br/> |
    |<span data-ttu-id="a2599-204">IPM。Note.Microsoft.Fax</span><span class="sxs-lookup"><span data-stu-id="a2599-204">IPM.Note.Microsoft.Fax</span></span>  <br/> |<span data-ttu-id="a2599-205">傳真訊息</span><span class="sxs-lookup"><span data-stu-id="a2599-205">Fax messages</span></span>  <br/> |
    |<span data-ttu-id="a2599-206">IPM。Note.Rules.Oof.Template.Microsoft</span><span class="sxs-lookup"><span data-stu-id="a2599-206">IPM.Note.Rules.Oof.Template.Microsoft</span></span>  <br/> |<span data-ttu-id="a2599-207">不在辦公室的自動回覆郵件</span><span class="sxs-lookup"><span data-stu-id="a2599-207">Out-of-office auto-reply messages</span></span>  <br/> |
    |<span data-ttu-id="a2599-208">IPM。Note.Rules.ReplyTemplate.Microsoft</span><span class="sxs-lookup"><span data-stu-id="a2599-208">IPM.Note.Rules.ReplyTemplate.Microsoft</span></span>  <br/> |<span data-ttu-id="a2599-209">收件匣規則所傳送的回覆</span><span class="sxs-lookup"><span data-stu-id="a2599-209">Replies sent by an inbox rule</span></span>  <br/> |
    |<span data-ttu-id="a2599-210">IPM。OLE。類別</span><span class="sxs-lookup"><span data-stu-id="a2599-210">IPM.OLE.Class</span></span>  <br/> |<span data-ttu-id="a2599-211">例外日期的週期性約會</span><span class="sxs-lookup"><span data-stu-id="a2599-211">Exceptions for a recurring series</span></span>  <br/> |
    |<span data-ttu-id="a2599-212">IPM。Recall.Report</span><span class="sxs-lookup"><span data-stu-id="a2599-212">IPM.Recall.Report</span></span>  <br/> |<span data-ttu-id="a2599-213">郵件回收報告</span><span class="sxs-lookup"><span data-stu-id="a2599-213">Message recall reports</span></span>  <br/> |
    |<span data-ttu-id="a2599-214">IPM。遠端</span><span class="sxs-lookup"><span data-stu-id="a2599-214">IPM.Remote</span></span>  <br/> |<span data-ttu-id="a2599-215">遠端郵件</span><span class="sxs-lookup"><span data-stu-id="a2599-215">Remote mail messages</span></span>  <br/> |
    |<span data-ttu-id="a2599-216">IPM。報告</span><span class="sxs-lookup"><span data-stu-id="a2599-216">IPM.Report</span></span>  <br/> |<span data-ttu-id="a2599-217">項目狀態報表</span><span class="sxs-lookup"><span data-stu-id="a2599-217">Item status reports</span></span>  <br/> |
