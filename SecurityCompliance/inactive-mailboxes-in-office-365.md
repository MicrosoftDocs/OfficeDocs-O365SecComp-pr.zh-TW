---
title: Office 365 中的非使用中信箱概覽
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 1fbd74e8-7a60-4157-afe8-fe79f05d2038
description: 瞭解如何將信箱變成非使用中的信箱, 以保留先前員工的信箱內容。 您可以將信箱設為訴訟暫止狀態, 或將 Office 365 保留原則套用至信箱, 然後移除對應的 Office 365 帳戶, 以達到此目的。
ms.openlocfilehash: acfe0a3d8f3865cf0e30a938970235bf31dfbce4
ms.sourcegitcommit: 6bb40cf53374eaaae8da0a469f0248b1163184a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/07/2019
ms.locfileid: "34767344"
---
# <a name="overview-of-inactive-mailboxes-in-office-365"></a>Office 365 中的非使用中信箱概覽

您的組織可能需要將其保留組織之後保留先前的員工電子郵件。 根據您的組織保留需求，您可能需要幾個月數或年後結束工作，或您可能需要無限期保留信箱內容的保留信箱內容。 無論您需要保留電子郵件的時間長短, 您可以在 Office 365 中建立非使用中的信箱, 以保留前一名員工的信箱。 
  
## <a name="what-are-inactive-mailboxes"></a>什麼是不在作用中的信箱？

當員工離開您的組織 (或在延伸時請假) 時, 您可以移除其 Office 365 帳戶。 員工的信箱資料會保留30天后移除帳戶。 在此期間內, 您仍可以撤銷復原帳戶, 以復原信箱資料。 30天后, 會永久移除資料。
  
但是, 如果您的組織需要保留之前員工的信箱內容, 您可以將信箱置於訴訟暫止狀態, 或將 Office 365 保留原則套用至安全性 & 規範中心中的信箱, 以將信箱轉換為非使用中信箱。, 然後移除對應的 Office 365 帳戶。 The contents of an inactive mailbox are retained for the duration of the Litigation Hold placed on the mailbox or the retention period of the Office 365 retention policy applied to it before the mailbox was deleted. You can still recover the corresponding user account for a 30-day period. 不過, 在30天后, 非使用中的信箱會保留在 Office 365 直到保留或保留原則移除為止。 
  
> [!NOTE]
> 我們已將 2017 年 7 月 1 日的期限延後，以建立新的「就地保留」來建立非使用中的信箱。但到今年年底或明年年初，您將無法在 Exchange Online 中建立新的「就地保留」。到時，只有「訴訟資料暫留」和 Office 365 保留原則可以用來建立非使用中的信箱。不過，仍會支援「就地保留」上現有的非使用中信箱，並且您可以繼續管理非使用信箱上的「就地保留」。這包括變更「就地保留」期間，以及透過移除「就地保留」永久刪除非使用中的信箱。 
 
  
## <a name="inactive-mailboxes-and-office-365-retention-policies"></a>非使用中信箱和 Office 365 保留原則

除了訴訟暫止之外, 使用安全性 & 合規性中心內的新 Office 365 保留原則功能, 也是將信箱設為非使用中的另一種方式。 To use a retention policy to make an inactive mailbox: 
  
- 必須將其設定為保留內容或保留, 然後刪除內容。 如果保留原則設定為只刪除內容時，將原則套用至信箱將不會成為刪除信箱時不在作用中。

- 它具有 （因為 Skype 相關的內容會儲存在使用者的信箱中） 可套用到 Exchange 信箱或商務用 Skype位置。 
    
- 它可以是查詢為基礎，讓它會保留在符合搜尋查詢的項目。 
    
如需設定Office 365保留原則的詳細資訊，請參閱 ＜ [Overview of Office 365 中的保留原則](retention-policies.md)。
  
如果您使用保留原則來進行非使用中的信箱, Office 365 會繼續處理非使用中信箱的保留原則。 這表示如果保留原則設定來保持不變，然後刪除內容，將移至可復原的項目資料夾保留期間到期時, 和最後清除從非使用中的信箱項目。 如果Office 365保留原則不設定成已刪除的項目，尚未被永久刪除之使用者所 （之前進行信箱不在作用中） 的項目不會移至 [可復原的項目] 資料夾與將會保留無限期之後信箱成為非使用中。 
  
您可能會考慮建立專用於非使用中信箱Office 365保留原則。以下是執行這項工作原因及謹記下列事項。
  
- 您可以設定保留信箱內容僅只要符合先前員工貴組織的需求所需的保留原則。
    
- 因為保留原則只會套用至非使用中的信箱, 所以識別非使用中信箱的方法很好。
    
- 您將能夠快速識別指派給組織中非使用中信箱的保留原則。 This will make it easier to change the retention (or deletion) settings if necessary. 它也會更容易永久刪除非使用中的信箱, 因為您只需使用安全性 & 合規性中心從原則中移除該信箱即可。 否則, 您必須使用 Exchange Online PowerShell 來移除非使用中信箱的訴訟暫止狀態, 或使用安全性 & 合規性中心 PowerShell, 從全組織的 Office 365 保留原則中排除非使用中的信箱。
    
- 如果您建立專用於非使用中信箱Office 365保留原則，您可以新增最多達 1000 個信箱原則。如果您是非常大型的組織，您可能必須建立多個Office 365保留原則，以用於非使用中的信箱。

> [!CAUTION]
> 如果您使用保留原則將信箱設為非使用中, 請不要在刪除對應的 Office 365 使用者帳戶之前, 變更或移除信箱的使用者主要名稱 (UPN)。 此外, 請不要變更主要 SMTP 位址 (派生自 UPN), 或從與信箱關聯的次要 SMTP 地址清單中移除此電子郵件地址, 然後再將信箱設為非使用中。 如果您變更 UPN 或電子郵件地址 (在套用保留原則時指派給該信箱), 然後刪除該使用者帳戶, 使該信箱成為非使用中信箱, 當您不再需要保留我時, 就無法刪除非使用中的信箱。\t\t. 這是因為您無法使用 UPN 或電子郵件地址 (識別非使用中的信箱) 從保留原則中移除非使用中的信箱, 而這些信箱是在保留原則最初套用至信箱時存在的。 如需刪除非使用中信箱的詳細資訊, 請參閱[刪除 Office 365 中的非使用中信箱](delete-an-inactive-mailbox.md)。
  
## <a name="inactive-mailboxes-and-ediscovery-case-holds"></a>不在作用中信箱和 eDiscovery 案件保留

如果在安全性 & 規範中心內與 eDiscovery 案例相關聯的保留會放置在信箱上, 然後刪除信箱或使用者的 Office 365 帳戶, 則信箱將變成非使用中信箱。 However, we don't recommend using eDiscovery case holds to make a mailbox inactive. That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue. At some point, a legal case will probably end and the holds associated with the case will be removed and the eDiscovery case will be closed. In fact, if a hold that's placed on an inactive mailbox is associated with an eDiscovery case, and then the hold is released or the eDiscovery case is closed (or deleted), the inactive mailbox will be permanently deleted. Additionally, you can't create a time-based eDiscovery hold. That's means content in an inactive mailbox will be retained forever or until the hold is removed and the inactive mailbox is deleted. Therefore, we recommend using a Litigation Hold or an Office 365 retention policy for inactive mailboxes.
  
如需 eDiscovery 案例和保留的詳細資訊, 請參閱[eDiscovery 案例](ediscovery-cases.md)。
  
## <a name="inactive-mailboxes-and-office-365-labels"></a>非使用中信箱和 Office 365 標籤

Office 365標籤有助於分類管理在組織中的電子郵件資料並強制執行該分類為基礎的保留規則。 標籤可以套用至電子郵件項目由使用者手動或自動將管理員及電子郵件項目只能有單一標籤指派給它。 如果使用者信箱中的單一電子郵件專案已指派標籤 (且其設定為保留或保留, 然後刪除專案), 且信箱或使用者的 Office 365 帳戶已被刪除, 則信箱將變成非使用中信箱。 類似於 eDiscovery 案件保留，我們不建議使用標籤來讓信箱成為非使用中。 但是，我們建議您是使用訴訟暫止狀態或Office 365保留原則。 請注意但如果是標籤，可能不知道標籤已套用至電子郵件項目及刪除使用者帳戶時然後不經意進行非使用中的信箱。 
  
如需標籤的詳細資訊，請參閱 ＜ [Overview of Office 365 中的標籤](labels.md)。
  
## <a name="inactive-mailboxes-and-exchange-mrm-retention-policies"></a>非使用中信箱和 Exchange MRM 保留原則

如果 Exchange 保留原則 (Exchange Online 中的通訊記錄管理, 或 MRM) 已套用至非使用中的信箱, 則任何刪除原則 (以 [**刪除**保留] 動作設定的保留標記) 將會繼續在非使用中信箱上進行處理。 這表示與刪除原則標記的項目要移至 [可復原的項目] 資料夾保留期間到期時。 保留期間到期時將這些項目已清除從非使用中的信箱。 如果不在作用中信箱的未指定保留持續時間，則會無限期保留復原的項目] 資料夾中的項目。 
  
相反地, 會忽略指派給非作用中信箱之保留原則中所包含的任何封存原則 (以**MoveToArchive**保留動作設定的保留標記)。 這表示在非使用中信箱與封存原則標記的項目仍然在主要信箱的保留期間到期時。 它們不被移至封存信箱或封存信箱中 [可復原的項目] 資料夾。 他們將會無限期保留。 
  
## <a name="creating-an-inactive-mailbox"></a>建立非使用中的信箱

若要停用信箱，它必須被指派Exchange Online (Plan 2) 授權使訴訟暫止狀態或Office 365保留原則可套用至信箱會在刪除之前。 刪除信箱之後, 就可以將其相關聯的 Exchange Online 授權指派給新的使用者。 不在作用中的信箱不需要持續進行的授權。
  
下表摘要說明程序，讓不同保留案例的非使用中信箱。 如需詳細資訊, 請參閱[在 Office 365 中管理非使用中的信箱](create-and-manage-inactive-mailboxes.md)。
  
|**自。。。**|**執行此動作 .。。**|**結果**|
|:-----|:-----|:-----|
|只有在員工離職之後無限期保留信箱內容  <br/> | 將信箱設為訴訟暫止, 或將 Office 365 保留原則 (設定為保留內容) 套用至信箱。  <br/>  不要將保留持續時間指定為訴訟暫止狀態或未設定刪除項目 ； Office 365保留原則或者您可以使用永久保留項目保留原則。  <br/>  移除使用者的Office 365帳戶。  <br/> |非使用中信箱的所有內容 (包括 [可復原的專案] 資料夾中的專案) 會無限期保留。  <br/> |
|信箱內容保留特定的一段之後員工離職然後予以刪除  <br/> | 將 Office 365 保留原則套用至信箱。  <br/>  將保留原則設定為保留, 然後在保留期間到期時刪除專案。  <br/>  移除使用者的Office 365帳戶。  <br/> |當信箱專案的保留期間到期時, 專案會移至 [可復原的專案] 資料夾, 然後在刪除的專案保留期間 (Exchange 信箱) 到期時, 永久刪除 (清除) 從非使用中信箱。 您可以根據接收或建立信箱專案的原始日期或上次修改時間, 來設定 Office 365 保留原則的保留期間。  <br/> |
   
**附注:** 如果已在信箱上進行訴訟保留, 或如果 Office 365 保留原則 (設定為保留或保留, 然後刪除內容) 已套用至信箱, 則您必須做的就是刪除對應的 Office 365 使用者帳戶, 以建立非使用中的信箱。 
  
## <a name="managing-inactive-mailboxes"></a>管理非使用中信箱

您讓信箱成為非使用中之後，您可以在非使用中的信箱上執行各種管理工作。
  
- **變更非使用中信箱的保留期間**將信箱設為非使用中狀態後, 您可以變更套用至非使用中信箱的訴訟暫止或 Office 365 保留原則的保留期間。 如需逐步程式, 請參閱[在 Office 365 中變更非使用中信箱的保留期間](change-the-hold-duration-for-an-inactive-mailbox.md)。

  > [!NOTE]
  > 您無法將其他保留原則套用至非使用中的信箱。 您只可以變更套用至非使用中信箱之現有保留原則的保留期間。
    
- **復原非使用中的信箱**如果離職員工 (或缺勤的員工) 傳回您的組織, 或雇用新的員工來承擔離職員工的工作責任, 您可以復原非使用中信箱的內容。 當您復原不在作用中的信箱時，信箱轉換成新的信箱、 保留的內容和非使用中的信箱資料夾結構，及信箱連結至新的使用者帳戶。 它會復原之後，非使用中的信箱不存在。 如需逐步程式及復原非使用中信箱時所發生之情況的相關資訊, 請參閱[復原 Office 365 中的非使用中信箱](recover-an-inactive-mailbox.md)。
    
- **還原非使用中的信箱**如果另一位員工承擔離職員工的工作責任, 或其他人需要存取非使用中信箱的內容, 您可以將非使用中信箱的內容還原 (或合併) 到現有信箱。 當您還原非使用中信箱內容複製到另一個信箱。 非使用中的信箱，則會保留與會維持不在作用中的信箱。 非使用中信箱仍可搜尋使用 eDiscovery 工具、 其內容可以還原至另一個信箱和復原或刪除日後。 如需逐步程式, 請參閱[在 Office 365 中還原非使用中的信箱](restore-an-inactive-mailbox.md)。
    
- **刪除非使用中的信箱**當您不再需要保留非使用中信箱的內容時, 您可以移除所有已套用至非使用中信箱的保留或 Office 365 保留原則, 永久刪除該信箱。 如果信箱進行非使用中超過 30 天之內，它會標示為永久刪除之後移除保留。 如果信箱可在過去 30 天內不在作用中，您可以使其成為使用一次之後移除保留或保留原則。 如需逐步程式, 請參閱[刪除 Office 365 中的非使用中信箱](delete-an-inactive-mailbox.md)。