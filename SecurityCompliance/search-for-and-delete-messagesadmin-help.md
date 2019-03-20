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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8c36bb03-e716-4fdd-9958-4aa7a2a1db42
description: 系統管理員可以使用 Search-mailbox 指令程式來搜尋使用者信箱，然後從信箱中刪除的郵件。
ms.openlocfilehash: abf7e7f39fe719ecc6c23565e284c01aed8822ee
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693482"
---
# <a name="search-for-and-delete-messages---admin-help"></a>搜尋並刪除郵件 - 管理中心說明
  
系統管理員可以使用**Search-mailbox**指令程式來搜尋使用者信箱，然後從信箱中刪除的郵件。 
  
若要搜尋並刪除郵件在一個步驟中的，執行**Search-mailbox**指令程式搭配_DeleteContent_參數。 不過，當您這麼做，您不能預覽搜尋結果，或產生記錄檔，將搜尋所傳回的郵件，您可能會不小心刪除郵件，您不想。 若要預覽記錄檔，在被刪除之前，在搜尋中找到的郵件，請執行**Search-mailbox**指令程式搭配_LogOnly_參數。 
  
為額外的防護措施，您可以先將郵件複製到另一個信箱所使用的_TargetMailbox_和_TargetFolder_參數。 執行此動作，您會保留一份已刪除的郵件，以便在需要時一次存取其。 
  
## <a name="before-you-begin"></a>開始之前

- 預估完成時間：10 分鐘。 實際的時間會視信箱和搜尋查詢的大小而異。
    
- 您無法使用 Exchange 系統管理中心 (EAC) 執行這些程序。 您必須使用命令介面。
    
- 您必須獲指派這兩個下列管理角色來搜尋並刪除使用者的信箱中的郵件：
    
  - **信箱搜尋**-此角色可讓您跨組織中的多信箱搜尋的郵件。 根據預設，系統管理員不會被指派這個角色。 若要將您自己這個角色指派，讓您可以搜尋的信箱，請將自己新增為 「 探索管理角色群組的成員。 請參閱[新增使用者至探索管理角色群組](http://technet.microsoft.com/library/729e09d8-614b-431f-ae04-ae41fb4c628e.aspx)。
    
  - **信箱匯入 / 匯出**-此角色可讓您從使用者的信箱刪除郵件。 根據預設，此角色不指派給任何角色群組。 若要從使用者的信箱刪除郵件，您可以將信箱匯入匯出角色新增至 「 組織管理 」 角色群組。 如需詳細資訊，請參閱[管理角色群組](http://technet.microsoft.com/library/ab9b7a3b-bf67-4ba1-bde5-8e6ac174b82c.aspx)的 「 新增角色至角色群組 」 一節。 
    
- 如果您要刪除的郵件的信箱已啟用單一項目復原，您必須先停用功能。 如需詳細資訊，請參閱 [為信箱啟用或停用單一項目復原](http://technet.microsoft.com/library/2e7f1bcd-8395-45ad-86ce-22868bd46af0.aspx)。
    
- 如果您要刪除的郵件的信箱處於保留狀態，我們建議您檢查與您的記錄管理或移除保留及刪除信箱內容之前的法務部門。 取得核准後，請依照下列主題中的 < <b0>Clean Up the Recoverable Items Folder</b0>所列出的步驟。
    
- 您可以搜尋 10000 個信箱使用**Search-mailbox**指令程式的最大值。 如果您是 Exchange Online 組織，而且有 10000 個以上的信箱，您可以使用符合性搜尋功能 （或對應的**New-compliancesearch** cmdlet） 來搜尋信箱數目不受限制。 然後您可以使用**New-compliancesearchaction** cmdlet 來刪除符合性搜尋所傳回的郵件。 如需詳細資訊，請參閱[搜尋並刪除電子郵件訊息從 Office 365 組織](https://go.microsoft.com/fwlink/p/?LinkId=786856)。
    
- 如果您使用包含在搜尋查詢 （ *SearchQuery*參數），此**Search-mailbox** cmdlet 會傳回最大值為 10000 個項目在搜尋結果中。 因此如果您包含在搜尋查詢，您可能必須執行**Search-mailbox**命令多次，以刪除 10000 個以上的項目。 
    
- 當您執行**Search-mailbox**指令程式時，也會搜尋使用者的封存信箱。 同樣地，當您使用**Search-mailbox**指令程式搭配_DeleteContent_參數時，會刪除主要的封存信箱中的項目。 若要避免這種情況，您可以包含*DoNotIncludeArchive*參數。 此外，我們建議您不要使用_DeleteContent_參數刪除的郵件在 Exchange Online 已啟用，因為可能會發生意外的遺失資料自動展開封存信箱。 
    
## <a name="search-messages-and-log-the-search-results"></a>搜尋郵件並記錄搜尋結果

本範例會搜尋 April Stewart 的信箱包含"Your bank statement"字詞的郵件的 [主旨] 欄位中，並將搜尋結果記錄系統管理員的信箱之 SearchAndDeleteLog 資料夾中。 不複製到郵件，或從目標信箱中刪除。
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

本範例會針對含有附加的檔案，包含檔案名稱的字"特洛伊木馬 」，而且將日誌郵件傳送給系統管理員的信箱的任何類型的郵件在組織中搜尋所有信箱。
  
```
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery attachment:trojan* -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

如需詳細的語法及參數資訊，請參閱 [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx)。
  
 
## <a name="search-and-delete-messages"></a>搜尋並刪除郵件

本範例會在 [主旨] 欄位中搜尋 April Stewart 的信箱包含"Your bank statement"字詞的郵件，並從來源信箱刪除郵件，而不將搜尋結果複製到另一個資料夾。 如先前所述，您必須獲指派 「 信箱匯入 / 匯出管理角色，以從使用者的信箱刪除郵件。
  
> [!IMPORTANT]
> 當您使用**Search-mailbox**指令程式搭配_DeleteContent_參數時，郵件會永久刪除來源信箱。 永久刪除的郵件之前，建議您可以使用_LogOnly_參數來產生記錄檔，其被刪除，或在從來源信箱刪除之前，將郵件複製到另一個信箱之前，在搜尋中找到的郵件。 
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -DeleteContent
```

本範例會搜尋 April Stewart 的信箱包含"Your bank statement"字詞的郵件的 [主旨] 欄位中，將搜尋結果複製到資料夾中的信箱的 Aprilstewart-deletedmessages，再-DeletedMessages 並刪除來自April 的信箱。
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox "BackupMailbox" -TargetFolder "AprilStewart-DeletedMessages" -LogLevel Full -DeleteContent
```

本範例會在郵件主旨行是"Download this file"，組織中搜尋所有信箱，然後永久刪除。 
  
```
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery 'Subject:"Download this file"' -DeleteContent
```

如需詳細的語法及參數資訊，請參閱 [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx)。

## <a name="using-the--loglevel-full-parameter"></a>使用-LogLevel Full 參數

在某些在前一個範例中，[ _LogLevel_參數，使用`Full`值用來登**Search-mailbox** cmdlet 所傳回的結果的詳細的資訊。 包含此參數時，電子郵件訊息建立，並傳送至_TargetMailbox_參數所指定的信箱。 （這是名為搜尋 Results.csv CSV 格式的檔案） 的記錄檔會附加到這個電子郵件訊息，且會位於_TargetFolder_參數所指定的資料夾。 記錄檔包含您執行**Search-mailbox**指令程式時，會將搜尋結果中包含每一封郵件的資料列。 
