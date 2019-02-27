---
title: 搜尋並刪除郵件 - 管理中心說明
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/20/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8c36bb03-e716-4fdd-9958-4aa7a2a1db42
description: 系統管理員可以使用 Search-Mailbox Cmdlet 來搜尋使用者信箱，然後刪除信箱中的郵件。
ms.openlocfilehash: 718a23f649843420ccfd924be72752a99278da4c
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30297126"
---
# <a name="search-for-and-delete-messages---admin-help"></a><span data-ttu-id="1ac05-103">搜尋並刪除郵件 - 管理中心說明</span><span class="sxs-lookup"><span data-stu-id="1ac05-103">Search for and delete messages - Admin help</span></span>
  
<span data-ttu-id="1ac05-104">系統管理員可以使用 **Search-Mailbox** Cmdlet 來搜尋使用者信箱，然後刪除信箱中的郵件。</span><span class="sxs-lookup"><span data-stu-id="1ac05-104">Administrators can use the **Search-Mailbox** cmdlet to search user mailboxes and then delete messages from a mailbox.</span></span> 
  
<span data-ttu-id="1ac05-p101">若要搜尋和刪除郵件在一個步驟中的，執行**Search-mailbox**指令程式搭配_DeleteContent_參數。不過，當您這麼做時，您無法預覽搜尋結果或產生的搜尋將傳回的訊息記錄且可能不小心刪除您不想要的郵件。若要預覽郵件刪除之前搜尋中找到的記錄檔，請執行**Search-mailbox**指令程式搭配_LogOnly_參數。</span><span class="sxs-lookup"><span data-stu-id="1ac05-p101">To search and delete messages in one step, run the **Search-Mailbox** cmdlet with the  _DeleteContent_ switch. However, when you do this, you can't preview search results or generate a log of messages that will be returned by the search, and you may inadvertently delete messages that you didn't intend to. To preview a log of the messages found in the search before they're deleted, run the **Search-Mailbox** cmdlet with the  _LogOnly_ switch.</span></span> 
  
<span data-ttu-id="1ac05-p102">為其他的保護，您可以先將郵件複製到另一個信箱所使用的_TargetMailbox_和_TargetFolder_參數。依照此您會保留一份已刪除的郵件以防需要再次存取它們。</span><span class="sxs-lookup"><span data-stu-id="1ac05-p102">As an additional safeguard, you can first copy the messages to another mailbox by using the  _TargetMailbox_ and  _TargetFolder_ parameters. By doing this, you retain a copy of the deleted messages in case you need to access them again.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="1ac05-110">開始之前</span><span class="sxs-lookup"><span data-stu-id="1ac05-110">Before you begin</span></span>

- <span data-ttu-id="1ac05-p103">預估完成時間：10 分鐘。實際時間可能視信箱大小和搜尋查詢而有所不同。</span><span class="sxs-lookup"><span data-stu-id="1ac05-p103">Estimated time to complete: 10 minutes. The actual time may vary depending on the size of the mailbox and the search query.</span></span>
    
- <span data-ttu-id="1ac05-p104">您不能使用 Exchange 管理中心 (EAC) 執行這些程序。您必須使用命令介面。</span><span class="sxs-lookup"><span data-stu-id="1ac05-p104">You can't use the Exchange admin center (EAC) to perform these procedures. You must use the Shell.</span></span>
    
- <span data-ttu-id="1ac05-115">您必須同時被指派下列管理角色，才能在使用者的信箱中搜尋並刪除郵件：</span><span class="sxs-lookup"><span data-stu-id="1ac05-115">You need to be assigned both of the following management roles to search for and delete messages in users' mailboxes:</span></span>
    
  - <span data-ttu-id="1ac05-p105">**信箱搜尋**此角色可讓您跨組織中的多個信箱搜尋的郵件。系統管理員未指派此角色預設。若要指派自行此角色，讓您可以搜尋信箱，新增您探索管理角色群組的成員身分自己。請參閱[新增至探索管理角色群組的使用者](http://technet.microsoft.com/library/729e09d8-614b-431f-ae04-ae41fb4c628e.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1ac05-p105">**Mailbox Search**- This role allows you to search for messages across multiple mailboxes in your organization. Administrators aren't assigned this role by default. To assign yourself this role so that you can search mailboxes, add yourself as a member of the Discovery Management role group. See [Add a User to the Discovery Management Role Group](http://technet.microsoft.com/library/729e09d8-614b-431f-ae04-ae41fb4c628e.aspx).</span></span>
    
  - <span data-ttu-id="1ac05-p106">**信箱匯入 / 匯出**-此角色可讓您刪除使用者信箱的郵件。根據預設，此角色不被指派給任何角色群組。若要刪除的郵件從使用者的信箱，您可以將信箱匯入 / 匯出角色新增至組織管理角色群組。如需詳細資訊，請參閱 ＜[管理角色群組](http://technet.microsoft.com/library/ab9b7a3b-bf67-4ba1-bde5-8e6ac174b82c.aspx)的 「 將角色新增至角色群組 」 一節。</span><span class="sxs-lookup"><span data-stu-id="1ac05-p106">**Mailbox Import Export** - This role allows you to delete messages from a user's mailbox. By default, this role isn't assigned to any role group. To delete messages from users' mailboxes, you can add the Mailbox Import Export role to the Organization Management role group. For more information, see the "Add a role to a role group" section in [Manage Role Groups](http://technet.microsoft.com/library/ab9b7a3b-bf67-4ba1-bde5-8e6ac174b82c.aspx) .</span></span> 
    
- <span data-ttu-id="1ac05-p107">如果您要從中刪除郵件的信箱已啟用單一項目復原，則必須先停用該功能。如需詳細資訊，請參閱[Enable or disable single item recovery for a mailbox](http://technet.microsoft.com/library/2e7f1bcd-8395-45ad-86ce-22868bd46af0.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1ac05-p107">If the mailbox from which you want to delete messages has single item recovery enabled, you must first disable the feature. For more information, see [Enable or disable single item recovery for a mailbox](http://technet.microsoft.com/library/2e7f1bcd-8395-45ad-86ce-22868bd46af0.aspx).</span></span>
    
- <span data-ttu-id="1ac05-p108">如果您要從中刪除郵件的信箱處於保留狀態，建議您先與記錄管理或法務部門確認，然後再移除保留並刪除信箱內容。獲得核准之後，請依照[Clean Up the Recoverable Items Folder](http://technet.microsoft.com/library/82c310f8-de2f-46f2-8e1a-edb6055d6e69.aspx)主題中所列的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="1ac05-p108">If the mailbox from which you want to delete messages is placed on hold, we recommend that you check with your records management or legal department before removing the hold and deleting the mailbox content. After you obtain approval, follow the steps listed in the topic [Clean Up the Recoverable Items Folder](http://technet.microsoft.com/library/82c310f8-de2f-46f2-8e1a-edb6055d6e69.aspx).</span></span>
    
- <span data-ttu-id="1ac05-p109">您可以搜尋最大值為 10000 個信箱使用**Search-mailbox**指令程式。如果您正在 Exchange Online 組織並擁有超過 10000 個信箱，您可以使用搜尋的信箱數目不受限制的規範搜尋功能 （或相對應**新增 ComplianceSearch**指令程式）。然後您可用於**新增 ComplianceSearchAction**指令程式刪除規範搜尋傳回的訊息。如需詳細資訊，請參閱[搜尋和刪除電子郵件訊息從 Office 365 組織](https://go.microsoft.com/fwlink/p/?LinkId=786856)。</span><span class="sxs-lookup"><span data-stu-id="1ac05-p109">You can search a maximum of 10,000 mailboxes using the **Search-Mailbox** cmdlet. If you're an Exchange Online organization and have more than 10,000 mailboxes, you can use the Compliance Search feature (or the corresponding **New-ComplianceSearch** cmdlet) to search an unlimited number of mailboxes. Then you can use the **New-ComplianceSearchAction** cmdlet to delete the messages returned by a compliance search. For more information, see [Search for and delete email messages from your Office 365 organization](https://go.microsoft.com/fwlink/p/?LinkId=786856).</span></span>
    
- <span data-ttu-id="1ac05-p110">如果您包括在搜尋查詢 （使用*SearchQuery*參數）， **Search-mailbox**指令程式會在搜尋結果中傳回最大值為 10000 個項目。因此如果您包括在搜尋查詢時，您可能必須執行**搜尋信箱**命令多次刪除 10000 個以上的項目。</span><span class="sxs-lookup"><span data-stu-id="1ac05-p110">If you include a search query (by using the  *SearchQuery*  parameter), the **Search-Mailbox** cmdlet will return a maximum of 10,000 items in the search results. Therefore if you include a search query, you might have to run the **Search-Mailbox** command multiple times to delete more than 10,000 items.</span></span> 
    
- <span data-ttu-id="1ac05-p111">當您執行**Search-mailbox**指令程式也要搜尋使用者的封存信箱。同樣地，當您使用**Search-mailbox**指令程式搭配_DeleteContent_參數將會刪除主要封存信箱中的項目。若要避免此問題，您可以包含*DoNotIncludeArchive*參數。此外，我們建議不建議您使用_DeleteContent_參數刪除的郵件在 Exchange Online 已啟用因為可能會發生未預期的資料遺失自動展開封存信箱。</span><span class="sxs-lookup"><span data-stu-id="1ac05-p111">The user's archive mailbox will also be searched when you run the **Search-Mailbox** cmdlet. Similarly, items in the primary archive mailbox will be deleted when you use the **Search-Mailbox** cmdlet with the  _DeleteContent_ switch. To prevent this, you can include the  *DoNotIncludeArchive*  switch. Also, we recommend that you don't use the  _DeleteContent_ switch to delete messages in Exchange Online mailboxes that have auto-expanding archiving enabled because unexpected data loss may occur.</span></span> 
    
## <a name="search-messages-and-log-the-search-results"></a><span data-ttu-id="1ac05-138">搜尋郵件並記錄搜尋結果</span><span class="sxs-lookup"><span data-stu-id="1ac05-138">Search messages and log the search results</span></span>

<span data-ttu-id="1ac05-p112">此範例會搜尋 April Stewart 的信箱中 [主旨] 欄位中包含 "Your bank statement" 字詞的郵件，並將搜尋結果記錄在系統管理員信箱的 SearchAndDeleteLog 資料夾中。不會將郵件複製到目標信箱或從中刪除。</span><span class="sxs-lookup"><span data-stu-id="1ac05-p112">This example searches April Stewart's mailbox for messages that contain the phrase "Your bank statement" in the Subject field and logs the search results in the SearchAndDeleteLog folder of the administrator's mailbox. Messages aren't copied to or deleted from the target mailbox.</span></span>
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

<span data-ttu-id="1ac05-141">此範例會在組織的所有信箱中搜尋檔名中含有 "Trojan" 一字之任何附加檔案類型的郵件，並傳送一則記錄檔訊息到系統管理員的信箱。</span><span class="sxs-lookup"><span data-stu-id="1ac05-141">This example searches all mailboxes in the organization for messages that have any type of attached file that contains the word "Trojan" in the filename and sends a log message to the administrator's mailbox.</span></span>
  
```
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery attachment:trojan* -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

<span data-ttu-id="1ac05-142">如需詳細的語法及參數資訊，請參閱 [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1ac05-142">For detailed syntax and parameter information, see [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx).</span></span>
  
 
## <a name="search-and-delete-messages"></a><span data-ttu-id="1ac05-143">搜尋和刪除郵件</span><span class="sxs-lookup"><span data-stu-id="1ac05-143">Search and delete messages</span></span>

<span data-ttu-id="1ac05-p113">此範例會搜尋 April Stewart 的信箱中 [主旨] 欄位中包含 "Your bank statement" 字詞的郵件，並從來源信箱刪除這些郵件，而不將搜尋結果複製到其他資料夾。如先前所述，您必須取得「信箱匯入匯出」管理角色，才能刪除使用者信箱中的郵件。 。</span><span class="sxs-lookup"><span data-stu-id="1ac05-p113">This example searches April Stewart's mailbox for messages that contain the phrase "Your bank statement" in the Subject field and deletes the messages from the source mailbox without copying the search results to another folder. As previously explained, you need to be assigned the Mailbox Import Export management role to delete messages from a user's mailbox.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1ac05-p114">當您使用**Search-mailbox**指令程式搭配_DeleteContent_參數時，會永久從來源信箱刪除訊息。永久刪除郵件之前，建議您也使用_LogOnly_參數來產生的記錄搜尋中找到他們正在刪除或之前刪除來源信箱將郵件複製到另一個信箱之前的郵件。</span><span class="sxs-lookup"><span data-stu-id="1ac05-p114">When you use the **Search-Mailbox** cmdlet with the  _DeleteContent_ switch, messages are permanently deleted from the source mailbox. Before you permanently delete messages, we recommend that you either use the  _LogOnly_ switch to generate a log of the messages found in the search before they're deleted or copy the messages to another mailbox before deleting them from the source mailbox.</span></span> 
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -DeleteContent
```

<span data-ttu-id="1ac05-148">此範例會搜尋 April Stewart 的信箱中 [主旨] 欄位中包含 "Your bank statement" 字詞的郵件、將搜尋結果複製到 BackupMailbox 信箱的 AprilStewart-DeletedMessages 資料夾中，然後再從 April 的信箱刪除郵件。</span><span class="sxs-lookup"><span data-stu-id="1ac05-148">This example searches April Stewart's mailbox for messages that contain the phrase "Your bank statement" in the Subject field, copies the search results to the folder AprilStewart-DeletedMessages in the mailbox BackupMailbox, and deletes the messages from April's mailbox.</span></span>
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox "BackupMailbox" -TargetFolder "AprilStewart-DeletedMessages" -LogLevel Full -DeleteContent
```

<span data-ttu-id="1ac05-149">此範例會在組織的所有信箱中搜尋主旨行是 "Download this file" 的郵件，然後永久刪除這些郵件。 </span><span class="sxs-lookup"><span data-stu-id="1ac05-149">This example searches all mailboxes in the organization for messages with the subject line "Download this file", and then permanently deletes them.</span></span> 
  
```
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery 'Subject:"Download this file"' -DeleteContent
```

<span data-ttu-id="1ac05-150">如需詳細的語法及參數資訊，請參閱 [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1ac05-150">For detailed syntax and parameter information, see [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx).</span></span>

## <a name="using-the--loglevel-full-parameter"></a><span data-ttu-id="1ac05-151">使用 -LogLevel Full 參數</span><span class="sxs-lookup"><span data-stu-id="1ac05-151">Using the -LogLevel Full parameter</span></span>

<span data-ttu-id="1ac05-p115">在某些先前範例_LogLevel_參數與`Full`值可用來記錄有關使用**Search-mailbox** cmdlet 傳回結果的詳細的資訊。當包含此參數時，請電子郵件訊息建立及傳送給_TargetMailbox_參數所指定的信箱。（這是名為搜尋 Results.csv CSV 格式的檔案） 的記錄檔案附加到此電子郵件訊息，並將位於_TargetFolder_參數所指定的資料夾。記錄檔包含當您執行**Search-mailbox**指令程式搜尋結果中包含的每封郵件的列。</span><span class="sxs-lookup"><span data-stu-id="1ac05-p115">In some of the previous examples, the  _LogLevel_ parameter, with the  `Full` value is used to log detailed information about the results returned by the **Search-Mailbox** cmdlet. When you included this parameter, an email message is created and sent to the mailbox specified by the  _TargetMailbox_ parameter. The log file (which is a CSV-formatted file named Search Results.csv) is attached to this email message, and will be located in the folder specified by the  _TargetFolder_ parameter. The log file contains a row for each message that's included in the search results when you run the **Search-Mailbox** cmdlet.</span></span> 
