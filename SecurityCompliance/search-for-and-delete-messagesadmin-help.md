---
title: 搜尋並刪除郵件 - 管理中心說明
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8c36bb03-e716-4fdd-9958-4aa7a2a1db42
description: 系統管理員可以使用搜尋信箱 Cmdlet 來搜尋使用者信箱, 然後刪除信箱中的郵件。
ms.openlocfilehash: bb375bc7a3273e78acb44807e51a1cee0261e7af
ms.sourcegitcommit: f2798d46acfbd56314e809cd3fe0350be807e420
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2019
ms.locfileid: "35014745"
---
# <a name="search-for-and-delete-messages---admin-help"></a>搜尋並刪除郵件 - 管理中心說明
  
系統管理員可以使用**搜尋信箱**Cmdlet 來搜尋使用者信箱, 然後刪除信箱中的郵件。 
  
若要在一個步驟中搜尋並刪除郵件, 請使用_DeleteContent_參數執行**搜尋信箱**Cmdlet。 不過, 當您執行此動作時, 您無法預覽搜尋結果或產生搜尋所傳回的訊息記錄, 而且可能會不慎刪除您不想要的郵件。 若要在刪除之前預覽搜尋中找到的郵件, 請使用_LogOnly_參數執行**搜尋信箱**Cmdlet。 
  
作為額外的保護措施, 您可以先使用_TargetMailbox_和_TargetFolder_參數, 將郵件複製到另一個信箱。 如此一來, 您會保留已刪除郵件的複本, 以防您需要再次存取這些郵件。 
  
## <a name="before-you-begin"></a>開始之前

- 預估完成時間：10 分鐘。 根據信箱和搜尋查詢的大小而定, 實際時間可能會有所不同。
    
- 您無法使用 Exchange 系統管理中心 (EAC) 執行這些程式。 您必須使用命令介面。
    
- 您必須被指派下列兩個管理角色, 才能在使用者的信箱中搜尋並刪除郵件:
    
  - **信箱搜尋**-此角色可讓您在組織中搜尋多個信箱的郵件。 根據預設，系統管理員不會被指派這個角色。 若要指派此角色給自己, 讓您可以搜尋信箱, 請將自己新增為「探索管理」角色群組的成員。 請參閱[將使用者新增至探索管理角色群組](http://technet.microsoft.com/library/729e09d8-614b-431f-ae04-ae41fb4c628e.aspx)。
    
  - **信箱匯入匯出**-此角色可讓您從使用者的信箱刪除郵件。 根據預設, 此角色不會指派給任何角色群組。 若要從使用者的信箱刪除郵件, 您可以將信箱匯入匯出角色新增至「組織管理」角色群組。 如需詳細資訊, 請參閱[Manage Role Groups](http://technet.microsoft.com/library/ab9b7a3b-bf67-4ba1-bde5-8e6ac174b82c.aspx)中的「新增角色至角色群組」一節。 
    
- 如果您要刪除郵件的信箱已啟用單一專案復原, 則必須先停用該功能。 如需詳細資訊，請參閱 [為信箱啟用或停用單一項目復原](http://technet.microsoft.com/library/2e7f1bcd-8395-45ad-86ce-22868bd46af0.aspx)。
    
- 如果您想要刪除郵件的來源信箱處於暫止狀態, 建議您先與您的記錄管理或法律部門核實, 然後再移除保留和刪除信箱內容。 取得核准之後, 請遵循本主題中所列的步驟[清除 [可復原的專案] 資料夾](http://technet.microsoft.com/library/82c310f8-de2f-46f2-8e1a-edb6055d6e69.aspx)。
    
- 您可以使用**搜尋信箱**Cmdlet 來搜尋最多10000個信箱。 如果您是 Exchange Online 組織且有超過10000個信箱, 您可以使用符合性搜尋功能 (或對應的**new-compliancesearch 指令程式**) 來搜尋不限數量的信箱。 然後, 您可以使用**new-compliancesearchaction** Cmdlet 來刪除符合性搜尋所傳回的郵件。 如需詳細資訊, 請參閱[搜尋並刪除 Office 365 組織中的電子郵件](https://go.microsoft.com/fwlink/p/?LinkId=786856)。
    
- 如果您包含搜尋查詢 (使用*SearchQuery*參數), 則**搜尋信箱**Cmdlet 會在搜尋結果中傳回最多10000個專案。 因此, 如果您包含搜尋查詢, 您可能需要多次執行**搜尋信箱**命令, 以刪除10000個以上的專案。 
    
- 當您執行**搜尋信箱**Cmdlet 時, 也會搜尋使用者的封存信箱。 同樣地, 當您將**搜尋信箱**Cmdlet 與_DeleteContent_參數搭配使用時, 會刪除主要封存信箱中的專案。 若要避免這種情況, 您可以包含*DoNotIncludeArchive*參數。
    
## <a name="search-messages-and-log-the-search-results"></a>搜尋郵件並記錄搜尋結果

此範例會在 [主旨] 欄位中搜尋包含「您的銀行對帳單」片語的郵件, 並在系統管理員信箱的 SearchAndDeleteLog 資料夾中記錄搜尋結果。 不會將郵件複製到目標信箱, 也不會從目標信箱中刪除。
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

此範例會在組織中的所有信箱中搜尋包含檔案名中包含 "特洛伊木馬" 一詞的郵件, 並將記錄訊息傳送至系統管理員的信箱。
  
```
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery attachment:trojan* -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

如需詳細的語法及參數資訊，請參閱 [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx)。
  
 
## <a name="search-and-delete-messages"></a>搜尋和刪除郵件

此範例會在 [主旨] 欄位中搜尋包含片語「您的銀行對帳單」的郵件, 並從來源信箱中刪除郵件, 而不將搜尋結果複製到另一個資料夾。 如先前所述, 您必須獲指派「信箱匯入匯出」管理角色, 才能從使用者信箱中刪除郵件。
  
> [!IMPORTANT]
> 當您將**搜尋信箱**Cmdlet 與_DeleteContent_參數搭配使用時, 會永久刪除來源信箱中的郵件。 在您永久刪除郵件之前, 建議您先使用_LogOnly_參數來產生在搜尋之前找到的訊息記錄, 然後再將郵件複製到另一個信箱, 然後再從來源信箱中刪除它們。 
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -DeleteContent
```

本範例會在 [主旨] 欄位中搜尋包含「您的銀行對帳單」片語的郵件的 Stewart 信箱, 並將搜尋結果複製到信箱 BackupMailbox 中的資料夾 AprilStewart-DeletedMessages, 並將郵件從April 的信箱。
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox "BackupMailbox" -TargetFolder "AprilStewart-DeletedMessages" -LogLevel Full -DeleteContent
```

本範例會搜尋組織中的所有信箱, 以取得主旨行「下載這個檔案」的郵件, 然後將它們永久刪除。 
  
```
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery 'Subject:"Download this file"' -DeleteContent
```

如需詳細的語法及參數資訊，請參閱 [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx)。

## <a name="using-the--loglevel-full-parameter"></a>使用-LogLevel Full 參數

在先前的某些範例中, _LogLevel_參數會使用`Full`值來記錄**搜尋信箱**指令程式所傳回之結果的詳細資訊。 當您加入此參數時, 會建立電子郵件訊息, 並將其傳送至_TargetMailbox_參數所指定的信箱。 記錄檔 (稱為「搜尋結果 .csv」的 CSV 格式化檔) 會附加到此電子郵件, 並會位於_TargetFolder_參數所指定的資料夾中。 當您執行**搜尋信箱**Cmdlet 時, 記錄檔會包含搜尋結果中所包含的每一封郵件所在的列。 
