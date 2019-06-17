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
description: 系統管理員可以使用搜尋信箱 Cmdlet 來搜尋使用者信箱, 然後刪除信箱中的郵件。
ms.openlocfilehash: 1288679c7abb643c020d5b1a2a08ae64b7cb403f
ms.sourcegitcommit: d20defdcf2ac643f0c8c1f2761b0b7f4f4090e5c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2019
ms.locfileid: "34957415"
---
# <a name="search-for-and-delete-messages---admin-help"></a><span data-ttu-id="215a5-103">搜尋並刪除郵件 - 管理中心說明</span><span class="sxs-lookup"><span data-stu-id="215a5-103">Search for and delete messages - Admin help</span></span>
  
<span data-ttu-id="215a5-104">系統管理員可以使用**搜尋信箱**Cmdlet 來搜尋使用者信箱, 然後刪除信箱中的郵件。</span><span class="sxs-lookup"><span data-stu-id="215a5-104">Administrators can use the **Search-Mailbox** cmdlet to search user mailboxes and then delete messages from a mailbox.</span></span> 
  
<span data-ttu-id="215a5-105">若要在一個步驟中搜尋並刪除郵件, 請使用_DeleteContent_參數執行**搜尋信箱**Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="215a5-105">To search and delete messages in one step, run the **Search-Mailbox** cmdlet with the  _DeleteContent_ switch.</span></span> <span data-ttu-id="215a5-106">不過, 當您執行此動作時, 您無法預覽搜尋結果或產生搜尋所傳回的訊息記錄, 而且可能會不慎刪除您不想要的郵件。</span><span class="sxs-lookup"><span data-stu-id="215a5-106">However, when you do this, you can't preview search results or generate a log of messages that will be returned by the search, and you may inadvertently delete messages that you didn't intend to.</span></span> <span data-ttu-id="215a5-107">若要在刪除之前預覽搜尋中找到的郵件, 請使用_LogOnly_參數執行**搜尋信箱**Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="215a5-107">To preview a log of the messages found in the search before they're deleted, run the **Search-Mailbox** cmdlet with the  _LogOnly_ switch.</span></span> 
  
<span data-ttu-id="215a5-108">作為額外的保護措施, 您可以先使用_TargetMailbox_和_TargetFolder_參數, 將郵件複製到另一個信箱。</span><span class="sxs-lookup"><span data-stu-id="215a5-108">As an additional safeguard, you can first copy the messages to another mailbox by using the  _TargetMailbox_ and  _TargetFolder_ parameters.</span></span> <span data-ttu-id="215a5-109">如此一來, 您會保留已刪除郵件的複本, 以防您需要再次存取這些郵件。</span><span class="sxs-lookup"><span data-stu-id="215a5-109">By doing this, you retain a copy of the deleted messages in case you need to access them again.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="215a5-110">開始之前</span><span class="sxs-lookup"><span data-stu-id="215a5-110">Before you begin</span></span>

- <span data-ttu-id="215a5-111">預估完成時間：10 分鐘。</span><span class="sxs-lookup"><span data-stu-id="215a5-111">Estimated time to complete: 10 minutes.</span></span> <span data-ttu-id="215a5-112">根據信箱和搜尋查詢的大小而定, 實際時間可能會有所不同。</span><span class="sxs-lookup"><span data-stu-id="215a5-112">The actual time may vary depending on the size of the mailbox and the search query.</span></span>
    
- <span data-ttu-id="215a5-113">您無法使用 Exchange 系統管理中心 (EAC) 執行這些程式。</span><span class="sxs-lookup"><span data-stu-id="215a5-113">You can't use the Exchange admin center (EAC) to perform these procedures.</span></span> <span data-ttu-id="215a5-114">您必須使用命令介面。</span><span class="sxs-lookup"><span data-stu-id="215a5-114">You must use the Shell.</span></span>
    
- <span data-ttu-id="215a5-115">您必須被指派下列兩個管理角色, 才能在使用者的信箱中搜尋並刪除郵件:</span><span class="sxs-lookup"><span data-stu-id="215a5-115">You need to be assigned both of the following management roles to search for and delete messages in users' mailboxes:</span></span>
    
  - <span data-ttu-id="215a5-116">**信箱搜尋**-此角色可讓您在組織中搜尋多個信箱的郵件。</span><span class="sxs-lookup"><span data-stu-id="215a5-116">**Mailbox Search**- This role allows you to search for messages across multiple mailboxes in your organization.</span></span> <span data-ttu-id="215a5-117">根據預設，系統管理員不會被指派這個角色。</span><span class="sxs-lookup"><span data-stu-id="215a5-117">Administrators aren't assigned this role by default.</span></span> <span data-ttu-id="215a5-118">若要指派此角色給自己, 讓您可以搜尋信箱, 請將自己新增為「探索管理」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="215a5-118">To assign yourself this role so that you can search mailboxes, add yourself as a member of the Discovery Management role group.</span></span> <span data-ttu-id="215a5-119">請參閱[將使用者新增至探索管理角色群組](http://technet.microsoft.com/library/729e09d8-614b-431f-ae04-ae41fb4c628e.aspx)。</span><span class="sxs-lookup"><span data-stu-id="215a5-119">See [Add a User to the Discovery Management Role Group](http://technet.microsoft.com/library/729e09d8-614b-431f-ae04-ae41fb4c628e.aspx).</span></span>
    
  - <span data-ttu-id="215a5-120">**信箱匯入匯出**-此角色可讓您從使用者的信箱刪除郵件。</span><span class="sxs-lookup"><span data-stu-id="215a5-120">**Mailbox Import Export** - This role allows you to delete messages from a user's mailbox.</span></span> <span data-ttu-id="215a5-121">根據預設, 此角色不會指派給任何角色群組。</span><span class="sxs-lookup"><span data-stu-id="215a5-121">By default, this role isn't assigned to any role group.</span></span> <span data-ttu-id="215a5-122">若要從使用者的信箱刪除郵件, 您可以將信箱匯入匯出角色新增至「組織管理」角色群組。</span><span class="sxs-lookup"><span data-stu-id="215a5-122">To delete messages from users' mailboxes, you can add the Mailbox Import Export role to the Organization Management role group.</span></span> <span data-ttu-id="215a5-123">如需詳細資訊, 請參閱[Manage Role Groups](http://technet.microsoft.com/library/ab9b7a3b-bf67-4ba1-bde5-8e6ac174b82c.aspx)中的「新增角色至角色群組」一節。</span><span class="sxs-lookup"><span data-stu-id="215a5-123">For more information, see the "Add a role to a role group" section in [Manage Role Groups](http://technet.microsoft.com/library/ab9b7a3b-bf67-4ba1-bde5-8e6ac174b82c.aspx) .</span></span> 
    
- <span data-ttu-id="215a5-124">如果您要刪除郵件的信箱已啟用單一專案復原, 則必須先停用該功能。</span><span class="sxs-lookup"><span data-stu-id="215a5-124">If the mailbox from which you want to delete messages has single item recovery enabled, you must first disable the feature.</span></span> <span data-ttu-id="215a5-125">如需詳細資訊，請參閱 [為信箱啟用或停用單一項目復原](http://technet.microsoft.com/library/2e7f1bcd-8395-45ad-86ce-22868bd46af0.aspx)。</span><span class="sxs-lookup"><span data-stu-id="215a5-125">For more information, see [Enable or disable single item recovery for a mailbox](http://technet.microsoft.com/library/2e7f1bcd-8395-45ad-86ce-22868bd46af0.aspx).</span></span>
    
- <span data-ttu-id="215a5-126">如果您想要刪除郵件的來源信箱處於暫止狀態, 建議您先與您的記錄管理或法律部門核實, 然後再移除保留和刪除信箱內容。</span><span class="sxs-lookup"><span data-stu-id="215a5-126">If the mailbox from which you want to delete messages is placed on hold, we recommend that you check with your records management or legal department before removing the hold and deleting the mailbox content.</span></span> <span data-ttu-id="215a5-127">取得核准之後, 請遵循本主題中所列的步驟[清除 [可復原的專案] 資料夾](http://technet.microsoft.com/library/82c310f8-de2f-46f2-8e1a-edb6055d6e69.aspx)。</span><span class="sxs-lookup"><span data-stu-id="215a5-127">After you obtain approval, follow the steps listed in the topic [Clean Up the Recoverable Items Folder](http://technet.microsoft.com/library/82c310f8-de2f-46f2-8e1a-edb6055d6e69.aspx).</span></span>
    
- <span data-ttu-id="215a5-128">您可以使用**搜尋信箱**Cmdlet 來搜尋最多10000個信箱。</span><span class="sxs-lookup"><span data-stu-id="215a5-128">You can search a maximum of 10,000 mailboxes using the **Search-Mailbox** cmdlet.</span></span> <span data-ttu-id="215a5-129">如果您是 Exchange Online 組織且有超過10000個信箱, 您可以使用符合性搜尋功能 (或對應的**new-compliancesearch 指令程式**) 來搜尋不限數量的信箱。</span><span class="sxs-lookup"><span data-stu-id="215a5-129">If you're an Exchange Online organization and have more than 10,000 mailboxes, you can use the Compliance Search feature (or the corresponding **New-ComplianceSearch** cmdlet) to search an unlimited number of mailboxes.</span></span> <span data-ttu-id="215a5-130">然後, 您可以使用**new-compliancesearchaction** Cmdlet 來刪除符合性搜尋所傳回的郵件。</span><span class="sxs-lookup"><span data-stu-id="215a5-130">Then you can use the **New-ComplianceSearchAction** cmdlet to delete the messages returned by a compliance search.</span></span> <span data-ttu-id="215a5-131">如需詳細資訊, 請參閱[搜尋並刪除 Office 365 組織中的電子郵件](https://go.microsoft.com/fwlink/p/?LinkId=786856)。</span><span class="sxs-lookup"><span data-stu-id="215a5-131">For more information, see [Search for and delete email messages from your Office 365 organization](https://go.microsoft.com/fwlink/p/?LinkId=786856).</span></span>
    
- <span data-ttu-id="215a5-132">如果您包含搜尋查詢 (使用*SearchQuery*參數), 則**搜尋信箱**Cmdlet 會在搜尋結果中傳回最多10000個專案。</span><span class="sxs-lookup"><span data-stu-id="215a5-132">If you include a search query (by using the  *SearchQuery*  parameter), the **Search-Mailbox** cmdlet will return a maximum of 10,000 items in the search results.</span></span> <span data-ttu-id="215a5-133">因此, 如果您包含搜尋查詢, 您可能需要多次執行**搜尋信箱**命令, 以刪除10000個以上的專案。</span><span class="sxs-lookup"><span data-stu-id="215a5-133">Therefore if you include a search query, you might have to run the **Search-Mailbox** command multiple times to delete more than 10,000 items.</span></span> 
    
- <span data-ttu-id="215a5-134">當您執行**搜尋信箱**Cmdlet 時, 也會搜尋使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="215a5-134">The user's archive mailbox will also be searched when you run the **Search-Mailbox** cmdlet.</span></span> <span data-ttu-id="215a5-135">同樣地, 當您將**搜尋信箱**Cmdlet 與_DeleteContent_參數搭配使用時, 會刪除主要封存信箱中的專案。</span><span class="sxs-lookup"><span data-stu-id="215a5-135">Similarly, items in the primary archive mailbox will be deleted when you use the **Search-Mailbox** cmdlet with the  _DeleteContent_ switch.</span></span> <span data-ttu-id="215a5-136">若要避免這種情況, 您可以包含*DoNotIncludeArchive*參數。</span><span class="sxs-lookup"><span data-stu-id="215a5-136">To prevent this, you can include the  *DoNotIncludeArchive*  switch.</span></span>
    
## <a name="search-messages-and-log-the-search-results"></a><span data-ttu-id="215a5-137">搜尋郵件並記錄搜尋結果</span><span class="sxs-lookup"><span data-stu-id="215a5-137">Search messages and log the search results</span></span>

<span data-ttu-id="215a5-138">此範例會在 [主旨] 欄位中搜尋包含「您的銀行對帳單」片語的郵件, 並在系統管理員信箱的 SearchAndDeleteLog 資料夾中記錄搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="215a5-138">This example searches April Stewart's mailbox for messages that contain the phrase "Your bank statement" in the Subject field and logs the search results in the SearchAndDeleteLog folder of the administrator's mailbox.</span></span> <span data-ttu-id="215a5-139">不會將郵件複製到目標信箱, 也不會從目標信箱中刪除。</span><span class="sxs-lookup"><span data-stu-id="215a5-139">Messages aren't copied to or deleted from the target mailbox.</span></span>
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

<span data-ttu-id="215a5-140">此範例會在組織中的所有信箱中搜尋包含檔案名中包含 "特洛伊木馬" 一詞的郵件, 並將記錄訊息傳送至系統管理員的信箱。</span><span class="sxs-lookup"><span data-stu-id="215a5-140">This example searches all mailboxes in the organization for messages that have any type of attached file that contains the word "Trojan" in the filename and sends a log message to the administrator's mailbox.</span></span>
  
```
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery attachment:trojan* -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

<span data-ttu-id="215a5-141">如需詳細的語法及參數資訊，請參閱 [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx)。</span><span class="sxs-lookup"><span data-stu-id="215a5-141">For detailed syntax and parameter information, see [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx).</span></span>
  
 
## <a name="search-and-delete-messages"></a><span data-ttu-id="215a5-142">搜尋和刪除郵件</span><span class="sxs-lookup"><span data-stu-id="215a5-142">Search and delete messages</span></span>

<span data-ttu-id="215a5-143">此範例會在 [主旨] 欄位中搜尋包含片語「您的銀行對帳單」的郵件, 並從來源信箱中刪除郵件, 而不將搜尋結果複製到另一個資料夾。</span><span class="sxs-lookup"><span data-stu-id="215a5-143">This example searches April Stewart's mailbox for messages that contain the phrase "Your bank statement" in the Subject field and deletes the messages from the source mailbox without copying the search results to another folder.</span></span> <span data-ttu-id="215a5-144">如先前所述, 您必須獲指派「信箱匯入匯出」管理角色, 才能從使用者信箱中刪除郵件。</span><span class="sxs-lookup"><span data-stu-id="215a5-144">As previously explained, you need to be assigned the Mailbox Import Export management role to delete messages from a user's mailbox.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="215a5-145">當您將**搜尋信箱**Cmdlet 與_DeleteContent_參數搭配使用時, 會永久刪除來源信箱中的郵件。</span><span class="sxs-lookup"><span data-stu-id="215a5-145">When you use the **Search-Mailbox** cmdlet with the  _DeleteContent_ switch, messages are permanently deleted from the source mailbox.</span></span> <span data-ttu-id="215a5-146">在您永久刪除郵件之前, 建議您先使用_LogOnly_參數來產生在搜尋之前找到的訊息記錄, 然後再將郵件複製到另一個信箱, 然後再從來源信箱中刪除它們。</span><span class="sxs-lookup"><span data-stu-id="215a5-146">Before you permanently delete messages, we recommend that you either use the  _LogOnly_ switch to generate a log of the messages found in the search before they're deleted or copy the messages to another mailbox before deleting them from the source mailbox.</span></span> 
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -DeleteContent
```

<span data-ttu-id="215a5-147">本範例會在 [主旨] 欄位中搜尋包含「您的銀行對帳單」片語的郵件的 Stewart 信箱, 並將搜尋結果複製到信箱 BackupMailbox 中的資料夾 AprilStewart-DeletedMessages, 並將郵件從April 的信箱。</span><span class="sxs-lookup"><span data-stu-id="215a5-147">This example searches April Stewart's mailbox for messages that contain the phrase "Your bank statement" in the Subject field, copies the search results to the folder AprilStewart-DeletedMessages in the mailbox BackupMailbox, and deletes the messages from April's mailbox.</span></span>
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox "BackupMailbox" -TargetFolder "AprilStewart-DeletedMessages" -LogLevel Full -DeleteContent
```

<span data-ttu-id="215a5-148">本範例會搜尋組織中的所有信箱, 以取得主旨行「下載這個檔案」的郵件, 然後將它們永久刪除。</span><span class="sxs-lookup"><span data-stu-id="215a5-148">This example searches all mailboxes in the organization for messages with the subject line "Download this file", and then permanently deletes them.</span></span> 
  
```
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery 'Subject:"Download this file"' -DeleteContent
```

<span data-ttu-id="215a5-149">如需詳細的語法及參數資訊，請參閱 [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx)。</span><span class="sxs-lookup"><span data-stu-id="215a5-149">For detailed syntax and parameter information, see [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx).</span></span>

## <a name="using-the--loglevel-full-parameter"></a><span data-ttu-id="215a5-150">使用-LogLevel Full 參數</span><span class="sxs-lookup"><span data-stu-id="215a5-150">Using the -LogLevel Full parameter</span></span>

<span data-ttu-id="215a5-151">在先前的某些範例中, _LogLevel_參數會使用`Full`值來記錄**搜尋信箱**指令程式所傳回之結果的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="215a5-151">In some of the previous examples, the  _LogLevel_ parameter, with the  `Full` value is used to log detailed information about the results returned by the **Search-Mailbox** cmdlet.</span></span> <span data-ttu-id="215a5-152">當您加入此參數時, 會建立電子郵件訊息, 並將其傳送至_TargetMailbox_參數所指定的信箱。</span><span class="sxs-lookup"><span data-stu-id="215a5-152">When you included this parameter, an email message is created and sent to the mailbox specified by the  _TargetMailbox_ parameter.</span></span> <span data-ttu-id="215a5-153">記錄檔 (稱為「搜尋結果 .csv」的 CSV 格式化檔) 會附加到此電子郵件, 並會位於_TargetFolder_參數所指定的資料夾中。</span><span class="sxs-lookup"><span data-stu-id="215a5-153">The log file (which is a CSV-formatted file named Search Results.csv) is attached to this email message, and will be located in the folder specified by the  _TargetFolder_ parameter.</span></span> <span data-ttu-id="215a5-154">當您執行**搜尋信箱**Cmdlet 時, 記錄檔會包含搜尋結果中所包含的每一封郵件所在的列。</span><span class="sxs-lookup"><span data-stu-id="215a5-154">The log file contains a row for each message that's included in the search results when you run the **Search-Mailbox** cmdlet.</span></span> 
