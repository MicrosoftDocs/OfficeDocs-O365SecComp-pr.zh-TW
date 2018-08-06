---
title: 搜尋並刪除郵件 - 管理中心說明
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/20/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 8c36bb03-e716-4fdd-9958-4aa7a2a1db42
description: 系統管理員可以使用 Search-Mailbox Cmdlet 來搜尋使用者信箱，然後刪除信箱中的郵件。
ms.openlocfilehash: ed110c4a3e36a93970af99e9548aa293d94307fd
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026580"
---
# <a name="search-for-and-delete-messages---admin-help"></a>搜尋並刪除郵件 - 管理中心說明
  
系統管理員可以使用 **Search-Mailbox** Cmdlet 來搜尋使用者信箱，然後刪除信箱中的郵件。 
  
若要搜尋和刪除郵件在一個步驟中的，執行**Search-mailbox**指令程式搭配_DeleteContent_參數。不過，當您這麼做時，您無法預覽搜尋結果或產生的搜尋將傳回的訊息記錄且可能不小心刪除您不想要的郵件。若要預覽郵件刪除之前搜尋中找到的記錄檔，請執行**Search-mailbox**指令程式搭配_LogOnly_參數。 
  
為其他的保護，您可以先將郵件複製到另一個信箱所使用的_TargetMailbox_和_TargetFolder_參數。依照此您會保留一份已刪除的郵件以防需要再次存取它們。 
  
## <a name="what-do-i-need-to-know-before-i-begin"></a>開始前需要瞭解什麼？
<a name="sectionSection0"> </a>

- 預估完成時間：10 分鐘。實際時間可能視信箱大小和搜尋查詢而有所不同。
    
- 您不能使用 Exchange 管理中心 (EAC) 執行這些程序。您必須使用命令介面。
    
- 您必須同時被指派下列管理角色，才能在使用者的信箱中搜尋並刪除郵件：
    
  - **信箱搜尋**此角色可讓您跨組織中的多個信箱搜尋的郵件。系統管理員未指派此角色預設。若要指派自行此角色，讓您可以搜尋信箱，新增您探索管理角色群組的成員身分自己。請參閱[新增至探索管理角色群組的使用者](http://technet.microsoft.com/library/729e09d8-614b-431f-ae04-ae41fb4c628e.aspx)。
    
  - **信箱匯入 / 匯出**此角色可讓您刪除使用者信箱的郵件。根據預設，此角色不被指派給任何角色群組。若要刪除的郵件從使用者的信箱，您可以將信箱匯入 / 匯出角色新增至組織管理角色群組。如需詳細資訊，請參閱 ＜[管理角色群組](http://technet.microsoft.com/library/ab9b7a3b-bf67-4ba1-bde5-8e6ac174b82c.aspx)的 「 將角色新增至角色群組 」 一節。 
    
- 如果您要從中刪除郵件的信箱已啟用單一項目復原，則必須先停用該功能。如需詳細資訊，請參閱[Enable or disable single item recovery for a mailbox](http://technet.microsoft.com/library/2e7f1bcd-8395-45ad-86ce-22868bd46af0.aspx)。
    
- 如果您要從中刪除郵件的信箱處於保留狀態，建議您先與記錄管理或法務部門確認，然後再移除保留並刪除信箱內容。獲得核准之後，請依照[Clean Up the Recoverable Items Folder](http://technet.microsoft.com/library/82c310f8-de2f-46f2-8e1a-edb6055d6e69.aspx)主題中所列的步驟進行。
    
- 您可以搜尋最大值為 10000 個信箱使用**Search-mailbox**指令程式。如果您正在 Exchange Online 組織並擁有超過 10000 個信箱，您可以使用搜尋的信箱數目不受限制的規範搜尋功能 （或相對應**新增 ComplianceSearch**指令程式）。然後您可用於**新增 ComplianceSearchAction**指令程式刪除規範搜尋傳回的訊息。如需詳細資訊，請參閱[搜尋和刪除電子郵件訊息從 Office 365 組織](https://go.microsoft.com/fwlink/p/?LinkId=786856)。
    
- 如果您包括在搜尋查詢 （使用*SearchQuery*參數）， **Search-mailbox**指令程式會在搜尋結果中傳回最大值為 10000 個項目。因此如果您包括在搜尋查詢時，您可能必須執行**搜尋信箱**命令多次刪除 10000 個以上的項目。 
    
- 當您執行**Search-mailbox**指令程式也要搜尋使用者的封存信箱。同樣地，當您使用**Search-mailbox**指令程式搭配_DeleteContent_參數將會刪除主要封存信箱中的項目。若要避免此問題，您可以包含*DoNotIncludeArchive*參數。此外，我們建議不建議您使用_DeleteContent_參數刪除的郵件在 Exchange Online 已啟用因為可能會發生未預期的資料遺失自動展開封存信箱。 
    
## <a name="search-messages-and-log-the-search-results"></a>搜尋郵件並記錄搜尋結果
<a name="sectionSection1"> </a>

此範例會搜尋 April Stewart 的信箱中 [主旨] 欄位中包含 "Your bank statement" 字詞的郵件，並將搜尋結果記錄在系統管理員信箱的 SearchAndDeleteLog 資料夾中。不會將郵件複製到目標信箱或從中刪除。
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

此範例會在組織的所有信箱中搜尋檔名中含有 "Trojan" 一字之任何附加檔案類型的郵件，並傳送一則記錄檔訊息到系統管理員的信箱。
  
```
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery attachment:trojan* -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

如需詳細的語法及參數資訊，請參閱 [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx)。
  
[回到頁首](search-for-and-delete-messagesadmin-help.md#top)
  
## <a name="search-and-delete-messages"></a>搜尋和刪除郵件
<a name="sectionSection2"> </a>

此範例會搜尋 April Stewart 的信箱中 [主旨] 欄位中包含 "Your bank statement" 字詞的郵件，並從來源信箱刪除這些郵件，而不將搜尋結果複製到其他資料夾。如先前所述，您必須取得「信箱匯入匯出」管理角色，才能刪除使用者信箱中的郵件。 。
  
> [!IMPORTANT]
> 當您使用**Search-mailbox**指令程式搭配_DeleteContent_參數時，會永久從來源信箱刪除訊息。永久刪除郵件之前，建議您也使用_LogOnly_參數來產生的記錄搜尋中找到他們正在刪除或之前刪除來源信箱將郵件複製到另一個信箱之前的郵件。 
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -DeleteContent
```

此範例會搜尋 April Stewart 的信箱中 [主旨] 欄位中包含 "Your bank statement" 字詞的郵件、將搜尋結果複製到 BackupMailbox 信箱的 AprilStewart-DeletedMessages 資料夾中，然後再從 April 的信箱刪除郵件。
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox "BackupMailbox" -TargetFolder "AprilStewart-DeletedMessages" -LogLevel Full -DeleteContent
```

此範例會在組織的所有信箱中搜尋主旨行是 "Download this file" 的郵件，然後永久刪除這些郵件。  
  
```
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery 'Subject:"Download this file"' -DeleteContent
```

如需詳細的語法及參數資訊，請參閱 [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx)。
  
[回到頁首](search-for-and-delete-messagesadmin-help.md#top)
  
## <a name="using-the--loglevel-full-parameter"></a>使用 -LogLevel Full 參數
<a name="sectionSection3"> </a>

在某些先前範例_LogLevel_參數與`Full`值可用來記錄有關使用**Search-mailbox** cmdlet 傳回結果的詳細的資訊。當包含此參數時，請電子郵件訊息建立及傳送給_TargetMailbox_參數所指定的信箱。（這是名為搜尋 Results.csv CSV 格式的檔案） 的記錄檔案附加到此電子郵件訊息，並將位於_TargetFolder_參數所指定的資料夾。記錄檔包含當您執行**Search-mailbox**指令程式搜尋結果中包含的每封郵件的列。 
  

