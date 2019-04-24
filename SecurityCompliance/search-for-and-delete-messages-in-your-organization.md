---
title: 搜尋並刪除 Office 365 組織的系統管理說明中的電子郵件
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 3526fd06-b45f-445b-aed4-5ebd37b3762a
description: 使用搜尋及清除安全性 & 來搜尋並刪除貴組織中的所有信箱的電子郵件訊息的 Office 365 規範中心中的功能。
ms.openlocfilehash: c6fa0d09852016b918375dbff5a19468886d86b3
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32265345"
---
# <a name="search-for-and-delete-email-messages-in-your-office-365-organization---admin-help"></a>搜尋並刪除 Office 365 組織的系統管理說明中的電子郵件

**本文適用於系統管理員。您試圖尋找您想要刪除的信箱中的項目？請參閱[尋找郵件或在使用立即搜尋的項目](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)**|
   
您可以使用 Office 365 中的 「 內容搜尋 」 功能來搜尋並刪除所有的信箱中的電子郵件訊息，您組織中。 這可協助您尋找並移除可能有害或高風險的電子郵件，例如：
  
- 包含危險附件或病毒的郵件
    
- 網路釣魚郵件
    
- 包含敏感資料的郵件
    
> [!CAUTION]
> 搜尋及清除是一個強大的功能，可讓任何人都被指派來自您組織中的信箱刪除電子郵件訊息的必要權限。 
  
## <a name="before-you-begin"></a>開始之前

- 若要建立並執行內容搜尋，您必須是 「 **eDiscovery 管理員**」 角色群組的成員，或被指派 「**符合性搜尋**管理 」 角色。 若要刪除的郵件，您必須是 「**組織管理**」 角色群組的成員，或是獲指派 「**搜尋及清除**的管理角色。 如需將使用者新增至角色群組的詳細資訊，請參閱[讓使用者能夠存取安全性與合規性中心](grant-access-to-the-security-and-compliance-center.md)。
    
- 您必須使用安全性 & 合規性中心 PowerShell 來刪除郵件。 如需如何連線指示，請參閱[步驟 2](#step-2-connect-to-security--compliance-center-powershell) 。
    
- 每個信箱的 10 個項目最多可以一次移除。 因為搜尋和移除郵件的功能應該是事件回應工具，此限制可以協助確保從信箱快速移除郵件。 這項功能不是用來清除使用者信箱。 若要刪除超過 10 個項目，您可以在 Exchange Online PowerShell 中使用**Search-mailbox DeleteContent**命令。 請參閱[搜尋並刪除郵件-系統管理說明](search-for-and-delete-messagesadmin-help.md)。
    
- 您可以用來執行搜尋刪除的項目，並清除巨集指令在內容搜尋的信箱數目上限為 50000。 如果內容搜尋 （您在[步驟 1](#step-1-create-a-content-search-to-find-the-message-to-delete)中建立） 有超過 50000 個來源信箱，將會失敗的清除動作 （您在步驟 3 中建立）。 請參閱上執行搜尋祕訣[的詳細資訊](#more-information)一節，並清除超過 50000 個信箱上的作業。 
    
- 本文中的程序只可以用來刪除 Exchange Online 信箱和公用資料夾中的項目。 您無法使用它來刪除內容從 SharePoint 或 OneDrive for Business 網站。
    
## <a name="step-1-create-a-content-search-to-find-the-message-to-delete"></a>步驟 1：建立內容搜尋來尋找要刪除的郵件

第一個步驟是建立和執行內容搜尋，以尋找您想要從組織中的信箱移除的郵件。 使用安全性 & 合規性中心，或執行**New-compliancesearch**和**Start-compliancesearch** cmdlet，您可以建立搜尋。 針對此搜尋將會執行刪除符合查詢的郵件**New-compliancesearchaction-清除**命令在[步驟 3](#step-3-delete-the-message)。 如需建立內容搜尋和設定搜尋查詢的詳細資訊，請參閱下列主題： 
  
- [Office 365 中的內容搜尋](content-search.md)
    
- [內容搜尋的關鍵字查詢](keyword-queries-and-search-conditions.md)
    
- [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearch)
    
- [Start-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/Start-ComplianceSearch)
    
> [!NOTE]
> 您在此步驟中建立內容搜尋中搜尋的內容位置不能包含 SharePoint 或 OneDrive for Business 網站。 您可以將用於電子郵件的內容搜尋中包含僅信箱與公用資料夾。 如果內容搜尋中包含的網站，您會收到錯誤，在步驟 3 中執行**New-compliancesearchaction** cmdlet 時即可。 
  
### <a name="tips-for-finding-messages-to-remove"></a>尋找要移除的郵件的提示

搜尋查詢的目標是將搜尋結果縮減為只有您想要移除的郵件。以下是一些提示：
  
- 如果您知道郵件主旨行中使用的確切文字或片語，請在搜尋查詢中使用 **Subject** 屬性。 
    
- 如果您知道郵件的實際日期 (或日期範圍)，請在搜尋查詢中包含 **Received** 屬性。 
    
- 如果您知道郵件的寄件者，請在搜尋查詢中包含 **From** 屬性。 
    
- 預覽搜尋結果，以確認內容搜尋僅傳回您想要刪除的郵件。
    
- 使用搜尋預估統計資料 （顯示於詳細資料窗格的搜尋] 安全性 & 合規性中心或使用[Get-compliancesearch](https://go.microsoft.com/fwlink/p/?LinkId=517934) cmdlet） 來取得結果的總計數。 
    
以下是尋找可疑電子郵件訊息的兩個查詢範例。
  
- 此查詢傳回 2016 年 4 月 13 日和 2016 年 4 月 14 日之間使用者所接收的郵件，且在主旨列中包含文字「動作」和「必要」。
    
    ```
    (Received:4/13/2016..4/14/2016) AND (Subject:'Action required')
    ```
   
- 此查詢傳回 chatsuwloginsset12345@outlook.com 所送出的郵件，且在主旨列中包含精準字詞「更新您的帳戶資訊」。
    
    ```
    (From:chatsuwloginsset12345@outlook.com) AND (Subject:"Update your account information")
    ```

## <a name="step-2-connect-to-security--compliance-center-powershell"></a>步驟 2： 連線到安全性 & 合規性中心 PowerShell

下一步是連線至您的組織的安全性 & 合規性中心 PowerShell。 如需逐步指示，請參閱[連線到安全性 & 合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。
  
如果您的 Office 365 帳戶使用多重要素驗證 (MFA)，或同盟驗證，您無法使用上一個主題上連接到安全性 & 合規性中心 PowerShell 中的指示。 相反地，請參閱主題中的 <<c0>連接到安全性 &amp; 合規性中心 PowerShell 中使用多重要素驗證的指示。
  
## <a name="step-3-delete-the-message"></a>步驟 3： 刪除郵件

您已建立並精簡內容搜尋來傳回的訊息，您想要移除，並且連線到安全性 & 合規性中心 PowerShell 之後，最後一個步驟是執行**New-compliancesearchaction** cmdlet 來刪除郵件。 您可以虛-或實刪除郵件。 虛刪除的郵件會移至使用者的 [可復原的項目] 資料夾，並保留已刪除的項目保留期間到期之前。 實刪除的郵件標示為永久移除信箱，並將會永久移除受管理的資料夾助理員處理信箱時的下一個時間。 如果信箱已啟用單一項目復原，已刪除的項目保留期間到期後，將會永久移除實刪除的項目。 如果信箱處於保留狀態，已刪除的郵件會保留直到項目的保留期間到期或從信箱移除保留為止。
  
在下列範例中，命令將虛刪除名為 「 移除網路釣魚郵件 」 的內容搜尋所傳回的搜尋結果。 

```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType SoftDelete
```

若要實刪除 「 移除網路釣魚郵件 」 的內容搜尋所傳回的項目，您會執行此命令：

```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType HardDelete
```

請注意，當您執行上述命令虛-或實刪除的郵件， *SearchName*參數所指定的搜尋您在步驟 1 中建立內容搜尋。 
  
如需詳細資訊，請參閱 < <b0>New-compliancesearchaction</b0>。

## <a name="more-information"></a>詳細資訊

- **您該如何取得搜尋狀態和移除作業？**

    執行 **Get-ComplianceSearchAction** 以取得刪除作業的狀態。 請注意，當您執行**New-compliancesearchaction** cmdlet 時建立的物件名為使用此格式： `<name of Content Search>_Purge`。 
    
- **刪除郵件之後會發生什麼事？**

   與已刪除的郵件`New-ComplianceSearchAction -Purge -PurgeType HardDelete`命令移至 [清除] 資料夾，並無法供使用者存取。 將郵件移至 [清除] 資料夾之後，郵件會保留已刪除的項目保留期間的持續期間，如果信箱已啟用單一項目復原。 （在 Office 365 中，單一項目復原是預設啟用時建立新的信箱。）已刪除的項目保留期間到期之後，郵件會標示為永久刪除，並會從 Office 365 清除受管理的資料夾助理員處理信箱時的下一個時間。 

   如果您使用`New-ComplianceSearchAction -Purge -PurgeType SoftDelete`命令，郵件會移至使用者的 [可復原的項目] 資料夾中的 [刪除] 資料夾。 它不是立即清除從 Office 365。 使用者可以根據為信箱設定的刪除項目保留期間，在持續時間之內復原 [刪除的郵件] 資料夾中的郵件。 此保留期間到期 (或者如果使用者在到期之前清除郵件) 之後，郵件會移至 [清除] 資料夾且使用者無法再存取。 一次中 [清除] 資料夾中，郵件會保留期間根據對信箱設定，如果信箱已啟用單一項目復原已刪除的項目保留期間。 （在 Office 365 中，單一項目復原是預設啟用時建立新的信箱。）已刪除的項目保留期間到期之後，郵件會標示為永久刪除，並會從 Office 365 清除受管理的資料夾助理員處理信箱時的下一個時間。 
    
- **如果您有超過 50000 個信箱刪除郵件？**

    如先前所述，您可以執行搜尋，並清除作業最多 50000 個信箱。 如果您必須執行搜尋及清除超過 50000 個信箱上的作業，請考慮建立暫存的搜尋權限篩選器，會降低會搜尋以少於 50000 個信箱的信箱數目。 例如，如果您的組織中包含不同部門、 狀態或國家/地區中的信箱，您可以建立下列其中一個組織中搜尋信箱子集這些信箱內容為基礎的信箱搜尋權限篩選器。 建立搜尋權限篩選器之後，您應建立搜尋 （在步驟 1 中所述），然後再刪除的郵件，（在步驟 3 中所述）。 然後您可以編輯搜尋及清除一組不同的信箱中的郵件篩選器。 如需建立搜尋權限篩選器的詳細資訊，請參閱 <<c0>設定的權限篩選內容搜尋。
    
- **會刪除包含在搜尋結果中的未編製索引項目？**

    否，' New-compliancesearchaction-清除命令不會刪除未編製索引的項目。 
    
- **如果從已處於就地保留或訴訟暫止狀態或指派給 Office 365 保留原則的信箱刪除郵件，會發生什麼事？**

    會清除郵件，並將其移至 [清除] 資料夾之後，郵件會保留直到保留期間到期為止。 如果保留期間是無限，則會保留項目直到移除保留或變更保留持續時間為止。
    
- **原因是搜尋並移除除以不同的安全性與合規性中心角色群組之間的工作流程？**

    如先前所述，使用者必須是「eDiscovery 管理員」角色群組的成員，或者獲指派「符合性搜尋」管理角色才能搜尋信箱。 若要刪除郵件，該人員必須是「組織管理」角色群組的成員，或者獲指派「搜尋及清除」管理角色。 這樣就可以控制誰能夠在組織中搜尋信箱以及誰能夠刪除郵件。 
