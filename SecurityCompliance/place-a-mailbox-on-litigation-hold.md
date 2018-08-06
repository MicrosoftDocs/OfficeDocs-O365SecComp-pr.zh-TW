---
title: 將信箱設為訴訟暫止
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/18/2016
ms.audience: End User
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: adee4621-3626-4aec-aa53-00b35ff0d0b0
description: '將信箱置於訴訟暫止狀態以保留所有信箱內容，包括已刪除的項目和已修改項目的原始版本。 '
ms.openlocfilehash: 8f440f5fc0bc7dafd639bdf8136808aa2f3bd35f
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026440"
---
# <a name="place-a-mailbox-on-litigation-hold"></a>將信箱設為訴訟暫止
 
將信箱設為訴訟暫止狀態以保留所有信箱內容，包括已刪除的項目和已修改項目的原始版本。當您將使用者的信箱設為訴訟暫止，使用者封存信箱 (若已啟用) 中的內容也會處於暫止狀態。已刪除和修改過的項目會保留一段指定的期間，或直到信箱退出「訴訟暫止」狀態為止。[In-Place eDiscovery](http://technet.microsoft.com/library/6377cb7a-3416-4e15-8571-c45d2160fc6f.aspx) 搜尋時會傳回這類信箱項目。 
  
> [!IMPORTANT]
> 訴訟資料暫留會保留在使用者的信箱 [可復原的項目] 資料夾中的項目。根據數量和大小的項目刪除或經過修改，可能會快速增加信箱 [可復原的項目] 資料夾的大小。可復原的項目] 資料夾是預設設定高配額。在 Exchange Online 中，此配額自動增加當您將信箱置於訴訟暫止狀態。在 Exchange Server 2013，我們建議您監視會放在訴訟暫止狀態以確保未達到的可復原的項目配額限制每週為基礎的信箱。 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？
<a name="sectionSection0"> </a>

- 預估完成時間：5 分鐘
    
- 訴訟暫止設定可能需要最多 60 分鐘才會生效。
    
- 您必須獲得權限才能執行此程序或程序。若您需要哪些權限，請參閱[訊息原則及符合性權限](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx)主題中的 「 就地保留 」 項目。 
    
- Exchange Online 的信箱置於訴訟暫止狀態，它必須被指派 Exchange Online (Plan 2) 授權。如果信箱指派 Exchange Online (計劃 1) 的授權，您必須將其放入個別 Exchange Online 封存授權保留指派。
    
- 如先前所述，當您置於訴訟保留使用者的信箱使用者的封存信箱中的內容也處於保留狀態。如果在 Exchange 混合部署的內部部署主要信箱上放置訴訟暫止狀態、 雲端式封存信箱 （若啟用） 也被處於保留狀態。
    
- 在 Exchange Online 中，[可復原的項目] 資料夾的配額自動增加為 100 GB 當您將信箱置於訴訟暫止狀態。此資料夾的預設大小為 30 GB。
    
- 訴訟資料暫留保留已刪除的項目和也會直到撤除保留已修改項目的原始版本。您可以選擇指定保留期間指定的時間期間內保留信箱項目。如果您指定保留持續時間期間，它會計算日期接收郵件或建立信箱項目。若要保留符合您所指定之的準則的項目，請使用就地保留來建立查詢式保留。如需詳細資訊，請參閱[建立或移除就地保留](http://technet.microsoft.com/library/9d5d8d37-a053-4830-9cb1-6e1ede25e963.aspx)。
    
- 若要使用命令介面來保留上放置 Exchange Online 信箱，您必須使用 Exchange Online PowerShell。如需詳細資訊，請參閱[Connect to Exchange Online Using Remote PowerShell。](http://technet.microsoft.com/library/c8bea338-6c1a-4bdf-8de0-7895d427ee5b.aspx)
    
- 不支援將公用資料夾信箱設為訴訟暫止。您必須使用就地保留來保留公用資料夾。
    
## <a name="use-the-eac-to-place-a-mailbox-on-litigation-hold"></a>使用 EAC 將信箱設為訴訟暫止
<a name="sectionSection1"> </a>

1. 移至 [**收件者** \> **信箱**。
    
2. 在使用者信箱清單中，按一下您想要置於訴訟暫止狀態、 信箱和 [**編輯**![編輯圖示](media/ITPro-EAC-EditIcon.png)。
    
3. 在信箱內容頁面上，按一下 [**信箱功能。**
    
4. 下**訴訟暫止狀態： 已停用**，按一下 [**啟用**信箱置於訴訟暫止狀態。 
    
5. 在**訴訟暫止狀態**] 頁面上輸入下列選用資訊： 
    
  - **訴訟保留持續時間 （天）** 使用此方塊可指定信箱處於訴訟暫止狀態時，長保留信箱項目。信箱項目會接收或建立日期被計算持續時間。如果您保留此方塊空白，項目會保留無限期或直到移除保留為止。用於持續時間指定天數。 
    
  - **附註**使用此方塊來通知他們的信箱處於訴訟暫止狀態的使用者。附註如果將會出現在使用者的信箱他們正在使用 Outlook 2010 或更新版本。 
    
  - **URL**使用此方塊可將使用者導向至訴訟暫止狀態的詳細資訊的網站。如果其於使用 Outlook 2010 或更新版本，此 URL 會出現在使用者的信箱。 
    
6. **訴訟暫止狀態**] 頁面上按一下 [**儲存**，然後按一下 [**儲存**] 信箱內容頁。 
  
## <a name="use-the-shell-to-place-a-mailbox-on-litigation-hold-indefinitely"></a>使用命令介面將信箱設為無限期訴訟暫止
<a name="sectionSection2"> </a>

本範例會將信箱 bsuneja@contoso.com 設為訴訟暫止。系統會無限期保留信箱中的項目，或將項目保留到移除保留為止。
  
```
Set-Mailbox bsuneja@contoso.com -LitigationHoldEnabled $true
```

> [!NOTE]
> 當您將信箱設為無限期訴訟暫止狀態 (藉由不指定時間週期)， _LitigationHoldDuration_ 屬性信箱的值會設為  `Unlimited`。 
  
## <a name="use-the-shell-to-place-a-mailbox-on-litigation-hold-and-preserve-items-for-a-specified-duration"></a>使用命令介面將信箱設為訴訟暫止，並在指定的期間保留項目
<a name="sectionSection3"> </a>

本範例會將信箱 bsuneja@contoso.com 設為訴訟暫止，並保留項目 2555 天 (約 7 年)。 
  
```
Set-Mailbox bsuneja@contoso.com -LitigationHoldEnabled $true -LitigationHoldDuration 2555
```

## <a name="use-the-shell-to-place-all-mailboxes-on-litigation-hold-for-a-specified-duration"></a>使用命令介面將所有信箱針對指定的期間設為訴訟暫止
<a name="sectionSection4"> </a>

您的組織可能需要將所有信箱資料保留一段特定時間。將組織中的所有信箱設為訴訟暫止狀態之前，請考慮下列事項：
  
本範例會將組織中的所有使用者信箱設為一年 (365 天) 的訴訟暫止。
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -LitigationHoldEnabled $true -LitigationHoldDuration 365
```

範例使用 [Get-Mailbox](http://technet.microsoft.com/library/8a5a6eb9-4a75-47f9-ae3b-a3ba251cf9a8.aspx) Cmdlet 來擷取組織中的所有信箱，指定收件者篩選器來包含所有使用者信箱，然後將信箱清單傳給 [Set-Mailbox](http://technet.microsoft.com/library/a0d413b9-d949-4df6-ba96-ac0906dedae2.aspx) Cmdlet 以啟用訴訟暫止及保留期間。  
  
若要將所有使用者信箱設為無限期保留，執行上一個命令，但不要包含  _LitigationHoldDuration_ 參數。 
  
請參閱[詳細資訊](#moreinfo.md)一節，以查看使用篩選器中的其他收件者屬性來包含或排除一或多個信箱的範例。 
  
## <a name="use-the-shell-to-remove-a-mailbox-from-litigation-hold"></a>使用命令介面從訴訟暫止中移除信箱
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
    
1. 移至 [**收件者** \> **信箱**。
    
2. 在使用者信箱清單中，按一下您想要確認的訴訟暫止狀態設定的信箱和 [**編輯**![編輯圖示](media/ITPro-EAC-EditIcon.png)。
    
3. 在信箱內容頁面上，按一下 [**信箱功能。**
    
4. 在 [**訴訟暫止狀態**，確認已啟用保留。
    
5. 按一下 [**檢視詳細資料]** 以確認信箱已放置在訴訟暫止狀態以及由誰時。您也可以確認或變更的選用值**訴訟保留持續時間 （天）**，**請注意**及**URL** ] 方塊。 
    
- 在命令介面中，執行下列任一命令：
    
  ```
  Get-Mailbox <name of mailbox> | FL LitigationHold*
  ```

    或
    
  ```
  Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | FL Name,LitigationHold*
  ```

    若信箱設為無限期訴訟暫止狀態， _LitigationHoldDuration_ 屬性信箱的值會設為  `Unlimited`。
    
## <a name="more-information"></a>其他資訊
<a name="moreinfo"> </a>

- 如果貴組織要求所有信箱資料必須保留一段特定時間，在您將組織中的所有信箱設為訴訟暫止之前，請考慮下列事項。
    
  - 當您使用上一個命令來保留組織的所有信箱 (或符合指定收件者篩選器的部分信箱)，只有在您執行命令時存在的信箱會被保留。如果您後來建立新的信箱，您必須再次執行此命令來保留新信箱。如果您經常建立新的信箱，您可以將命令當做排程工作，依需要而經常執行。
    
  - 將所有信箱都放置在訴訟暫止狀態可能大幅影響信箱大小。在 Exchange Server 2013 部署組織中規劃足夠的儲存以符合您的組織保留需求。
    
  - 可復原的項目] 資料夾有其專屬的儲存量限制，因此在資料夾中的項目不計算至接近信箱儲存限制。如先前所述的一段時間保留信箱資料將會產生使用者的信箱中 [可復原的項目] 資料夾的成長和封存。為了容納此增加的 Exchange Online，可復原的項目] 資料夾的配額自動從增加 30 GB 為 100 GB 當您將信箱置於訴訟暫止狀態。 
    
    在 Exchange Server 2013]、 [可復原的項目] 資料夾的預設儲存量限制也是 30 GB。我們建議您定期監視以確定它不會到達此限制此資料夾的大小。如需詳細資訊，請參閱 ＜ [Recoverable Items Folder](http://technet.microsoft.com/library/efc48fb4-2ed8-4d05-93af-f3505fbc389d.aspx)。
    
- 要保留所有信箱的上一個命令會使用會傳回所有使用者信箱的收件者篩選。您可以使用其他收件者的屬性來傳回您可以再透過管線傳到**Set-mailbox**指令程式置於訴訟保留這些信箱的特定信箱的清單。 
    
    以下是一些範例使用**Get-mailbox**與**Get-recipient**指令程式來傳回常見的使用者或信箱內容為基礎的信箱的子集。下列範例會假設相關信箱內容 （例如_CustomAttributeN_或_部門_） 已填入。
    
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
    

