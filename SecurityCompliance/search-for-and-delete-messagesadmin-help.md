---
title: 搜尋並刪除郵件 - 管理中心說明
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/20/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8c36bb03-e716-4fdd-9958-4aa7a2a1db42
description: 系統管理員可以使用 Search-mailbox 指令程式來搜尋使用者信箱，然後從信箱中刪除的郵件。
ms.openlocfilehash: a097b39aa179ed18c3d5426eeeacff204d48ee9b
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34158485"
---
# <a name="search-for-and-delete-messages---admin-help"></a><span data-ttu-id="ca77f-103">搜尋並刪除郵件 - 管理中心說明</span><span class="sxs-lookup"><span data-stu-id="ca77f-103">Search for and delete messages - Admin help</span></span>
  
<span data-ttu-id="ca77f-104">系統管理員可以使用**Search-mailbox**指令程式來搜尋使用者信箱，然後從信箱中刪除的郵件。</span><span class="sxs-lookup"><span data-stu-id="ca77f-104">Administrators can use the **Search-Mailbox** cmdlet to search user mailboxes and then delete messages from a mailbox.</span></span> 
  
<span data-ttu-id="ca77f-105">若要搜尋並刪除郵件在一個步驟中的，執行**Search-mailbox**指令程式搭配_DeleteContent_參數。</span><span class="sxs-lookup"><span data-stu-id="ca77f-105">To search and delete messages in one step, run the **Search-Mailbox** cmdlet with the  _DeleteContent_ switch.</span></span> <span data-ttu-id="ca77f-106">不過，當您這麼做，您不能預覽搜尋結果，或產生記錄檔，將搜尋所傳回的郵件，您可能會不小心刪除郵件，您不想。</span><span class="sxs-lookup"><span data-stu-id="ca77f-106">However, when you do this, you can't preview search results or generate a log of messages that will be returned by the search, and you may inadvertently delete messages that you didn't intend to.</span></span> <span data-ttu-id="ca77f-107">若要預覽記錄檔，在被刪除之前，在搜尋中找到的郵件，請執行**Search-mailbox**指令程式搭配_LogOnly_參數。</span><span class="sxs-lookup"><span data-stu-id="ca77f-107">To preview a log of the messages found in the search before they're deleted, run the **Search-Mailbox** cmdlet with the  _LogOnly_ switch.</span></span> 
  
<span data-ttu-id="ca77f-108">為額外的防護措施，您可以先將郵件複製到另一個信箱所使用的_TargetMailbox_和_TargetFolder_參數。</span><span class="sxs-lookup"><span data-stu-id="ca77f-108">As an additional safeguard, you can first copy the messages to another mailbox by using the  _TargetMailbox_ and  _TargetFolder_ parameters.</span></span> <span data-ttu-id="ca77f-109">執行此動作，您會保留一份已刪除的郵件，以便在需要時一次存取其。</span><span class="sxs-lookup"><span data-stu-id="ca77f-109">By doing this, you retain a copy of the deleted messages in case you need to access them again.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="ca77f-110">開始之前</span><span class="sxs-lookup"><span data-stu-id="ca77f-110">Before you begin</span></span>

- <span data-ttu-id="ca77f-111">預估完成時間：10 分鐘。</span><span class="sxs-lookup"><span data-stu-id="ca77f-111">Estimated time to complete: 10 minutes.</span></span> <span data-ttu-id="ca77f-112">實際的時間會視信箱和搜尋查詢的大小而異。</span><span class="sxs-lookup"><span data-stu-id="ca77f-112">The actual time may vary depending on the size of the mailbox and the search query.</span></span>
    
- <span data-ttu-id="ca77f-113">您無法使用 Exchange 系統管理中心 (EAC) 執行這些程序。</span><span class="sxs-lookup"><span data-stu-id="ca77f-113">You can't use the Exchange admin center (EAC) to perform these procedures.</span></span> <span data-ttu-id="ca77f-114">您必須使用命令介面。</span><span class="sxs-lookup"><span data-stu-id="ca77f-114">You must use the Shell.</span></span>
    
- <span data-ttu-id="ca77f-115">您必須獲指派這兩個下列管理角色來搜尋並刪除使用者的信箱中的郵件：</span><span class="sxs-lookup"><span data-stu-id="ca77f-115">You need to be assigned both of the following management roles to search for and delete messages in users' mailboxes:</span></span>
    
  - <span data-ttu-id="ca77f-116">**信箱搜尋**-此角色可讓您跨組織中的多信箱搜尋的郵件。</span><span class="sxs-lookup"><span data-stu-id="ca77f-116">**Mailbox Search**- This role allows you to search for messages across multiple mailboxes in your organization.</span></span> <span data-ttu-id="ca77f-117">根據預設，系統管理員不會被指派這個角色。</span><span class="sxs-lookup"><span data-stu-id="ca77f-117">Administrators aren't assigned this role by default.</span></span> <span data-ttu-id="ca77f-118">若要將您自己這個角色指派，讓您可以搜尋的信箱，請將自己新增為 「 探索管理角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="ca77f-118">To assign yourself this role so that you can search mailboxes, add yourself as a member of the Discovery Management role group.</span></span> <span data-ttu-id="ca77f-119">請參閱[新增使用者至探索管理角色群組](http://technet.microsoft.com/library/729e09d8-614b-431f-ae04-ae41fb4c628e.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ca77f-119">See [Add a User to the Discovery Management Role Group](http://technet.microsoft.com/library/729e09d8-614b-431f-ae04-ae41fb4c628e.aspx).</span></span>
    
  - <span data-ttu-id="ca77f-120">**信箱匯入 / 匯出**-此角色可讓您從使用者的信箱刪除郵件。</span><span class="sxs-lookup"><span data-stu-id="ca77f-120">**Mailbox Import Export** - This role allows you to delete messages from a user's mailbox.</span></span> <span data-ttu-id="ca77f-121">根據預設，此角色不指派給任何角色群組。</span><span class="sxs-lookup"><span data-stu-id="ca77f-121">By default, this role isn't assigned to any role group.</span></span> <span data-ttu-id="ca77f-122">若要從使用者的信箱刪除郵件，您可以將信箱匯入匯出角色新增至 「 組織管理 」 角色群組。</span><span class="sxs-lookup"><span data-stu-id="ca77f-122">To delete messages from users' mailboxes, you can add the Mailbox Import Export role to the Organization Management role group.</span></span> <span data-ttu-id="ca77f-123">如需詳細資訊，請參閱[管理角色群組](http://technet.microsoft.com/library/ab9b7a3b-bf67-4ba1-bde5-8e6ac174b82c.aspx)的 「 新增角色至角色群組 」 一節。</span><span class="sxs-lookup"><span data-stu-id="ca77f-123">For more information, see the "Add a role to a role group" section in [Manage Role Groups](http://technet.microsoft.com/library/ab9b7a3b-bf67-4ba1-bde5-8e6ac174b82c.aspx) .</span></span> 
    
- <span data-ttu-id="ca77f-124">如果您要刪除的郵件的信箱已啟用單一項目復原，您必須先停用功能。</span><span class="sxs-lookup"><span data-stu-id="ca77f-124">If the mailbox from which you want to delete messages has single item recovery enabled, you must first disable the feature.</span></span> <span data-ttu-id="ca77f-125">如需詳細資訊，請參閱 [為信箱啟用或停用單一項目復原](http://technet.microsoft.com/library/2e7f1bcd-8395-45ad-86ce-22868bd46af0.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ca77f-125">For more information, see [Enable or disable single item recovery for a mailbox](http://technet.microsoft.com/library/2e7f1bcd-8395-45ad-86ce-22868bd46af0.aspx).</span></span>
    
- <span data-ttu-id="ca77f-126">如果您要刪除的郵件的信箱處於保留狀態，我們建議您檢查與您的記錄管理或移除保留及刪除信箱內容之前的法務部門。</span><span class="sxs-lookup"><span data-stu-id="ca77f-126">If the mailbox from which you want to delete messages is placed on hold, we recommend that you check with your records management or legal department before removing the hold and deleting the mailbox content.</span></span> <span data-ttu-id="ca77f-127">取得核准後，請依照下列主題中的 < <b0>Clean Up the Recoverable Items Folder</b0>所列出的步驟。</span><span class="sxs-lookup"><span data-stu-id="ca77f-127">After you obtain approval, follow the steps listed in the topic [Clean Up the Recoverable Items Folder](http://technet.microsoft.com/library/82c310f8-de2f-46f2-8e1a-edb6055d6e69.aspx).</span></span>
    
- <span data-ttu-id="ca77f-128">您可以搜尋 10000 個信箱使用**Search-mailbox**指令程式的最大值。</span><span class="sxs-lookup"><span data-stu-id="ca77f-128">You can search a maximum of 10,000 mailboxes using the **Search-Mailbox** cmdlet.</span></span> <span data-ttu-id="ca77f-129">如果您是 Exchange Online 組織，而且有 10000 個以上的信箱，您可以使用符合性搜尋功能 （或對應的**New-compliancesearch** cmdlet） 來搜尋信箱數目不受限制。</span><span class="sxs-lookup"><span data-stu-id="ca77f-129">If you're an Exchange Online organization and have more than 10,000 mailboxes, you can use the Compliance Search feature (or the corresponding **New-ComplianceSearch** cmdlet) to search an unlimited number of mailboxes.</span></span> <span data-ttu-id="ca77f-130">然後您可以使用**New-compliancesearchaction** cmdlet 來刪除符合性搜尋所傳回的郵件。</span><span class="sxs-lookup"><span data-stu-id="ca77f-130">Then you can use the **New-ComplianceSearchAction** cmdlet to delete the messages returned by a compliance search.</span></span> <span data-ttu-id="ca77f-131">如需詳細資訊，請參閱[搜尋並刪除電子郵件訊息從 Office 365 組織](https://go.microsoft.com/fwlink/p/?LinkId=786856)。</span><span class="sxs-lookup"><span data-stu-id="ca77f-131">For more information, see [Search for and delete email messages from your Office 365 organization](https://go.microsoft.com/fwlink/p/?LinkId=786856).</span></span>
    
- <span data-ttu-id="ca77f-132">如果您使用包含在搜尋查詢 （ *SearchQuery*參數），此**Search-mailbox** cmdlet 會傳回最大值為 10000 個項目在搜尋結果中。</span><span class="sxs-lookup"><span data-stu-id="ca77f-132">If you include a search query (by using the  *SearchQuery*  parameter), the **Search-Mailbox** cmdlet will return a maximum of 10,000 items in the search results.</span></span> <span data-ttu-id="ca77f-133">因此如果您包含在搜尋查詢，您可能必須執行**Search-mailbox**命令多次，以刪除 10000 個以上的項目。</span><span class="sxs-lookup"><span data-stu-id="ca77f-133">Therefore if you include a search query, you might have to run the **Search-Mailbox** command multiple times to delete more than 10,000 items.</span></span> 
    
- <span data-ttu-id="ca77f-134">當您執行**Search-mailbox**指令程式時，也會搜尋使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="ca77f-134">The user's archive mailbox will also be searched when you run the **Search-Mailbox** cmdlet.</span></span> <span data-ttu-id="ca77f-135">同樣地，當您使用**Search-mailbox**指令程式搭配_DeleteContent_參數時，會刪除主要的封存信箱中的項目。</span><span class="sxs-lookup"><span data-stu-id="ca77f-135">Similarly, items in the primary archive mailbox will be deleted when you use the **Search-Mailbox** cmdlet with the  _DeleteContent_ switch.</span></span> <span data-ttu-id="ca77f-136">若要避免這種情況，您可以包含*DoNotIncludeArchive*參數。</span><span class="sxs-lookup"><span data-stu-id="ca77f-136">To prevent this, you can include the  *DoNotIncludeArchive*  switch.</span></span> <span data-ttu-id="ca77f-137">此外，我們建議您不要使用_DeleteContent_參數刪除的郵件在 Exchange Online 已啟用，因為可能會發生意外的遺失資料自動展開封存信箱。</span><span class="sxs-lookup"><span data-stu-id="ca77f-137">Also, we recommend that you don't use the  _DeleteContent_ switch to delete messages in Exchange Online mailboxes that have auto-expanding archiving enabled because unexpected data loss may occur.</span></span> 
    
## <a name="search-messages-and-log-the-search-results"></a><span data-ttu-id="ca77f-138">搜尋郵件並記錄搜尋結果</span><span class="sxs-lookup"><span data-stu-id="ca77f-138">Search messages and log the search results</span></span>

<span data-ttu-id="ca77f-139">本範例會搜尋 April Stewart 的信箱包含"Your bank statement"字詞的郵件的 [主旨] 欄位中，並將搜尋結果記錄系統管理員的信箱之 SearchAndDeleteLog 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="ca77f-139">This example searches April Stewart's mailbox for messages that contain the phrase "Your bank statement" in the Subject field and logs the search results in the SearchAndDeleteLog folder of the administrator's mailbox.</span></span> <span data-ttu-id="ca77f-140">不複製到郵件，或從目標信箱中刪除。</span><span class="sxs-lookup"><span data-stu-id="ca77f-140">Messages aren't copied to or deleted from the target mailbox.</span></span>
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

<span data-ttu-id="ca77f-141">本範例會針對含有附加的檔案，包含檔案名稱的字"特洛伊木馬 」，而且將日誌郵件傳送給系統管理員的信箱的任何類型的郵件在組織中搜尋所有信箱。</span><span class="sxs-lookup"><span data-stu-id="ca77f-141">This example searches all mailboxes in the organization for messages that have any type of attached file that contains the word "Trojan" in the filename and sends a log message to the administrator's mailbox.</span></span>
  
```
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery attachment:trojan* -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

<span data-ttu-id="ca77f-142">如需詳細的語法及參數資訊，請參閱 [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ca77f-142">For detailed syntax and parameter information, see [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx).</span></span>
  
 
## <a name="search-and-delete-messages"></a><span data-ttu-id="ca77f-143">搜尋並刪除郵件</span><span class="sxs-lookup"><span data-stu-id="ca77f-143">Search and delete messages</span></span>

<span data-ttu-id="ca77f-144">本範例會在 [主旨] 欄位中搜尋 April Stewart 的信箱包含"Your bank statement"字詞的郵件，並從來源信箱刪除郵件，而不將搜尋結果複製到另一個資料夾。</span><span class="sxs-lookup"><span data-stu-id="ca77f-144">This example searches April Stewart's mailbox for messages that contain the phrase "Your bank statement" in the Subject field and deletes the messages from the source mailbox without copying the search results to another folder.</span></span> <span data-ttu-id="ca77f-145">如先前所述，您必須獲指派 「 信箱匯入 / 匯出管理角色，以從使用者的信箱刪除郵件。</span><span class="sxs-lookup"><span data-stu-id="ca77f-145">As previously explained, you need to be assigned the Mailbox Import Export management role to delete messages from a user's mailbox.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ca77f-146">當您使用**Search-mailbox**指令程式搭配_DeleteContent_參數時，郵件會永久刪除來源信箱。</span><span class="sxs-lookup"><span data-stu-id="ca77f-146">When you use the **Search-Mailbox** cmdlet with the  _DeleteContent_ switch, messages are permanently deleted from the source mailbox.</span></span> <span data-ttu-id="ca77f-147">永久刪除的郵件之前，建議您可以使用_LogOnly_參數來產生記錄檔，其被刪除，或在從來源信箱刪除之前，將郵件複製到另一個信箱之前，在搜尋中找到的郵件。</span><span class="sxs-lookup"><span data-stu-id="ca77f-147">Before you permanently delete messages, we recommend that you either use the  _LogOnly_ switch to generate a log of the messages found in the search before they're deleted or copy the messages to another mailbox before deleting them from the source mailbox.</span></span> 
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -DeleteContent
```

<span data-ttu-id="ca77f-148">本範例會搜尋 April Stewart 的信箱包含"Your bank statement"字詞的郵件的 [主旨] 欄位中，將搜尋結果複製到資料夾中的信箱的 Aprilstewart-deletedmessages，再-DeletedMessages 並刪除來自April 的信箱。</span><span class="sxs-lookup"><span data-stu-id="ca77f-148">This example searches April Stewart's mailbox for messages that contain the phrase "Your bank statement" in the Subject field, copies the search results to the folder AprilStewart-DeletedMessages in the mailbox BackupMailbox, and deletes the messages from April's mailbox.</span></span>
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox "BackupMailbox" -TargetFolder "AprilStewart-DeletedMessages" -LogLevel Full -DeleteContent
```

<span data-ttu-id="ca77f-149">本範例會在郵件主旨行是"Download this file"，組織中搜尋所有信箱，然後永久刪除。</span><span class="sxs-lookup"><span data-stu-id="ca77f-149">This example searches all mailboxes in the organization for messages with the subject line "Download this file", and then permanently deletes them.</span></span> 
  
```
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery 'Subject:"Download this file"' -DeleteContent
```

<span data-ttu-id="ca77f-150">如需詳細的語法及參數資訊，請參閱 [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ca77f-150">For detailed syntax and parameter information, see [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx).</span></span>

## <a name="using-the--loglevel-full-parameter"></a><span data-ttu-id="ca77f-151">使用-LogLevel Full 參數</span><span class="sxs-lookup"><span data-stu-id="ca77f-151">Using the -LogLevel Full parameter</span></span>

<span data-ttu-id="ca77f-152">在某些在前一個範例中，[ _LogLevel_參數，使用`Full`值用來登**Search-mailbox** cmdlet 所傳回的結果的詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="ca77f-152">In some of the previous examples, the  _LogLevel_ parameter, with the  `Full` value is used to log detailed information about the results returned by the **Search-Mailbox** cmdlet.</span></span> <span data-ttu-id="ca77f-153">包含此參數時，電子郵件訊息建立，並傳送至_TargetMailbox_參數所指定的信箱。</span><span class="sxs-lookup"><span data-stu-id="ca77f-153">When you included this parameter, an email message is created and sent to the mailbox specified by the  _TargetMailbox_ parameter.</span></span> <span data-ttu-id="ca77f-154">（這是名為搜尋 Results.csv CSV 格式的檔案） 的記錄檔會附加到這個電子郵件訊息，且會位於_TargetFolder_參數所指定的資料夾。</span><span class="sxs-lookup"><span data-stu-id="ca77f-154">The log file (which is a CSV-formatted file named Search Results.csv) is attached to this email message, and will be located in the folder specified by the  _TargetFolder_ parameter.</span></span> <span data-ttu-id="ca77f-155">記錄檔包含您執行**Search-mailbox**指令程式時，會將搜尋結果中包含每一封郵件的資料列。</span><span class="sxs-lookup"><span data-stu-id="ca77f-155">The log file contains a row for each message that's included in the search results when you run the **Search-Mailbox** cmdlet.</span></span> 
