---
title: 將信箱設為訴訟暫止
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/18/2016
ms.audience: End User
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid: ''
ms.assetid: adee4621-3626-4aec-aa53-00b35ff0d0b0
description: '將信箱置於訴訟暫止來保留所有信箱內容，包括已刪除的項目和已修改項目的原始版本。 '
ms.openlocfilehash: a4d0939ffed32a8442b4b705bd15804b9f3eb7ea
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693122"
---
# <a name="place-a-mailbox-on-litigation-hold"></a>將信箱設為訴訟暫止
 
將信箱置於訴訟暫止來保留所有信箱內容，包括已刪除的項目和已修改項目的原始版本。 當您將使用者 ' 信箱訴訟暫止中使用者的封存信箱 （如果已啟用） 的內容也會處於暫止。 已刪除和修改過的項目會保留一段指定的期間，或直到信箱退出「訴訟暫止」狀態為止。 [就地 eDiscovery](http://technet.microsoft.com/library/6377cb7a-3416-4e15-8571-c45d2160fc6f.aspx)搜尋時會傳回這類信箱項目。 
  
> [!IMPORTANT]
> 訴訟暫止會保留使用者信箱 [可復原的項目] 資料夾中的項目。 根據刪除或修改的項目數量和大小，信箱 [可復原的項目] 資料夾的大小可能會快速增加。 [可復原的項目] 資料夾預設以高配額設定。 在 Exchange Online 中，將信箱置於訴訟暫止時，自動會增加此配額。 在 Exchange Server 2013，我們建議您監控處於訴訟暫止週以確保它們不會達到 [可復原的項目配額的限制的信箱。 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？
<a name="sectionSection0"> </a>

- 預估完成時間：5 分鐘
    
- 訴訟暫止設定可能需要最多 60 分鐘才會生效。
    
- 您必須已獲指派權限，才能執行此程序或這些程序。 若要查看您需要的權限，請參閱[通訊原則及符合性權限](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx)主題中的 「 就地保留 」 項目。 
    
- 若要啟用 Exchange Online 信箱訴訟暫止，它必須指派 Exchange Online (Plan 2) 授權。 如果信箱指派 Exchange Online (方案 1) 的授權，您必須指派不同 Exchange Online Archiving 授權，才能將它放在保留它。
    
- 如先前所述，當您將使用者的信箱上的 [訴訟暫止中使用者的封存信箱的內容也會處於暫止。 如果您訴訟暫止保留上放置在 Exchange 混合式部署中內部部署主要信箱，雲端式封存信箱 （若啟用） 也會處於保留狀態。
    
- 在 Exchange Online 中，[可復原的項目] 資料夾的配額會自動增加到 100GB 當您將信箱置於訴訟暫止。 此資料夾的預設大小為 30 GB。
    
- 訴訟暫止狀態會保留刪除的項目，也會保留已修改項目的原始版本，直到移除暫止狀態為止。 您可以選擇指定保留期間，這會使信箱項目保留一段指定的時間週期。 若您指定暫止持續時間，則將自接收訊息或建立信箱項目的日期開始計算。 若要保留符合指定的準則的項目，請使用就地保留來建立查詢式保留。 如需詳細資訊，請參閱[建立或移除就地保留](http://technet.microsoft.com/library/9d5d8d37-a053-4830-9cb1-6e1ede25e963.aspx)。
    
- 若要使用命令介面將 Exchange Online 信箱置於保留，您必須使用 Exchange Online PowerShell。 如需詳細資訊，請參閱[使用遠端 PowerShell 連線到 Exchange Online](http://technet.microsoft.com/library/c8bea338-6c1a-4bdf-8de0-7895d427ee5b.aspx)。
    
- 將 [公用資料夾信箱置於 [訴訟暫止不支援。 您必須使用就地保留功能來保留公用資料夾。
    
## <a name="use-the-eac-to-place-a-mailbox-on-litigation-hold"></a>使用 EAC 將信箱設為訴訟暫止
<a name="sectionSection1"> </a>

1. 前往 [**收件者** \> **信箱**。
    
2. 在使用者信箱清單中，按一下您想要放置訴訟暫止的信箱，然後按一下 [**編輯**![編輯圖示](media/ITPro-EAC-EditIcon.gif)。
    
3. 在信箱內容頁面上，按一下 [**的信箱功能。**
    
4. [**訴訟暫止： 停用**，按一下 [**啟用**]，以讓信箱處於訴訟暫止狀態。 
    
5. 在 [**訴訟暫止**] 頁面上，輸入下列選擇性資訊： 
    
  - **訴訟暫止持續時間 （天）** 使用此方塊來指定當信箱處於訴訟暫止的信箱項目保留多久。 持續時間自接收或建立信箱項目的日期開始計算。 如果您將此方塊保留空白，則會無限期保留項目，或將項目保留到移除保留為止。 請使用天數為單位來指定持續時間。 
    
  - **附註**使用此方塊告知使用者他們的信箱處於訴訟暫止狀態。 附註將會出現在使用者的信箱中，如果他們使用 Outlook 2010 或更新版本。 
    
  - **URL**使用此方塊可將使用者導向至網站，使其訴訟暫止狀態的詳細資訊。 如果他們使用 Outlook 2010 或更新版本，此 URL 會出現在使用者的信箱。 
    
6. 在 [**訴訟暫止**] 頁面上，按一下 [**儲存**，然後按一下 [信箱內容] 頁面上的 [**儲存**。 
  
## <a name="use-the-shell-to-place-a-mailbox-on-litigation-hold-indefinitely"></a>使用命令介面來啟用信箱無限期訴訟暫止
<a name="sectionSection2"> </a>

本範例會將信箱 bsuneja@contoso.com 設為訴訟暫止。系統會無限期保留信箱中的項目，或將項目保留到移除保留為止。
  
```
Set-Mailbox bsuneja@contoso.com -LitigationHoldEnabled $true
```

> [!NOTE]
> 當您將信箱設為無限期訴訟暫止狀態 (藉由不指定時間週期)， _LitigationHoldDuration_ 屬性信箱的值會設為  `Unlimited`。 
  
## <a name="use-the-shell-to-place-a-mailbox-on-litigation-hold-and-preserve-items-for-a-specified-duration"></a>使用命令介面將信箱設為訴訟暫止，並於指定期間內保留項目
<a name="sectionSection3"> </a>

本範例會將信箱 bsuneja@contoso.com 設為訴訟暫止，並保留項目 2555 天 (約 7 年)。 
  
```
Set-Mailbox bsuneja@contoso.com -LitigationHoldEnabled $true -LitigationHoldDuration 2555
```

## <a name="use-the-shell-to-place-all-mailboxes-on-litigation-hold-for-a-specified-duration"></a>使用命令介面來啟用所有信箱訴訟暫止於指定期間內
<a name="sectionSection4"> </a>

您的組織可能需要一段特定時間，保留所有信箱資料。 您將所有信箱置於訴訟暫止組織之前，請考慮下列項目：
  
本範例會將一年 （365 天） 的訴訟暫止組織中的所有使用者信箱。
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -LitigationHoldEnabled $true -LitigationHoldDuration 365
```

此範例使用[Get-mailbox](http://technet.microsoft.com/library/8a5a6eb9-4a75-47f9-ae3b-a3ba251cf9a8.aspx)指令程式來擷取組織中的所有信箱、 指定收件者篩選器，包括所有的使用者信箱，並再以管線傳輸至[Set-mailbox](http://technet.microsoft.com/library/a0d413b9-d949-4df6-ba96-ac0906dedae2.aspx)指令程式，以啟用訴訟暫止的信箱清單和保留持續時間。 
  
若要將所有使用者信箱設為無限期保留，執行上一個命令，但不要包含  _LitigationHoldDuration_ 參數。 
  
請參閱[詳細資訊](#moreinfo.md)一節，以查看使用篩選器中的其他收件者屬性來包含或排除一或多個信箱的範例。 
  
## <a name="use-the-shell-to-remove-a-mailbox-from-litigation-hold"></a>使用命令介面從訴訟暫止移除信箱
<a name="sectionSection5"> </a>

本範例會從訴訟暫止移除信箱 bsuneja@contoso.com。
  
```
Set-Mailbox bsuneja@contoso.com -LitigationHoldEnabled $false
```

P
## <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？
<a name="sectionSection6"> </a>

若要確認是否已成功將信箱設為訴訟暫止，請進行下列其中一項：
  
- 在 EAC 中：
    
1. 前往 [**收件者** \> **信箱**。
    
2. 在使用者信箱清單中，按一下您想確認訴訟暫止設定的信箱，然後按一下 [**編輯**![編輯圖示](media/ITPro-EAC-EditIcon.gif)。
    
3. 在信箱內容頁面上，按一下 [**的信箱功能。**
    
4. 在 [**訴訟暫止狀態**，確認已啟用保留。
    
5. 按一下 [**檢視詳細資料]** 來確認信箱已處於訴訟暫止及由誰。 您也可以確認或變更的值在選擇性**訴訟暫止持續時間 （天）**，**附註**，以及**URL** ] 方塊。 
    
- 在命令介面中執行下列其中一個下列命令：
    
  ```
  Get-Mailbox <name of mailbox> | FL LitigationHold*
  ```

    或
    
  ```
  Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | FL Name,LitigationHold*
  ```

    若信箱設為無限期訴訟暫止狀態， _LitigationHoldDuration_ 屬性信箱的值會設為  `Unlimited`。
    
## <a name="more-information"></a>詳細資訊
<a name="moreinfo"> </a>

- 如果貴組織要求所有信箱資料必須保留一段特定時間，在您將組織中的所有信箱設為訴訟暫止之前，請考慮下列事項。
    
  - 當您使用上一個命令來保留組織的所有信箱 (或符合指定收件者篩選器的部分信箱)，只有在您執行命令時存在的信箱會被保留。如果您後來建立新的信箱，您必須再次執行此命令來保留新信箱。如果您經常建立新的信箱，您可以將命令當做排程工作，依需要而經常執行。
    
  - 將所有信箱設為訴訟暫止可能對信箱大小造成重大影響。 在 Exchange Server 2013 組織中，請規劃足夠的儲存空間，以符合組織的保留需求。
    
  - [可復原的項目] 資料夾本身有其儲存限制，所以資料夾中的項目不計入信箱儲存限制中。 如同先前所解說，長時間保留信箱資料會導致使用者信箱和封存中 [可復原的項目] 資料夾的大小增加。 若要容納此增加在 Exchange Online，[可復原的項目] 資料夾的配額會自動增加從 30 GB 至 100 GB 將信箱置於訴訟暫止時。 
    
    在 Exchange Server 2013 中，[可復原的項目] 資料夾的預設儲存量限制也是 30 GB。 建議您定期監視此資料夾大小，以確保未達到限制。 如需詳細資訊，請參閱 < <b0>Recoverable Items Folder</b0>。
    
- 要保留所有信箱的前一個命令，是使用會傳回所有使用者信箱的收件者篩選器。 您可以使用其他收件者的屬性以傳回您然後輸送至**Set-mailbox** cmdlet 以將這些信箱上的 [訴訟暫止狀態的特定信箱的清單。 
    
    以下是一些使用**Get-mailbox**和**Get-recipient**指令程式可傳回根據一般使用者或信箱內容的信箱子集的範例。 這些範例假設相關的信箱屬性 (例如  _CustomAttributeN_ 或  _Department_) 皆已填入。
    
  ```
  Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'CustomAttribute15 -eq "OneYearLitigationHold"'
  ```

  ```
  Get-Recipient -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'Department -eq "HR"'
  ```

  ```
  Get-Recipient -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'PostalCode -eq "98052"'
  ```

  ```
  Get-Recipient -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'StateOrProvince -eq "WA"'
  ```

  ```
  Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -ne "DiscoveryMailbox"}
  ```

    您可以在篩選器中使用其他使用者信箱屬性來包含或排除信箱。如需詳細資訊，請參閱[Filterable Properties for the -Filter Parameter](http://technet.microsoft.com/library/b02b0005-2fb6-4bc2-8815-305259fa5432.aspx)。
    

