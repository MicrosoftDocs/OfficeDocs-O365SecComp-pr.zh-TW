---
title: 在 Office 365 中的非使用中信箱的概觀
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
description: 了解保留離職員工的信箱內容，藉由轉變成非使用中信箱的信箱。 您可以藉由將信箱置於訴訟暫止狀態或將 Office 365 保留原則套用至信箱與對應的 Office 365 帳戶，然後移除來這麼做。
ms.openlocfilehash: 58bcc888af0d1ae92cf9d86e116fe287e7c2316c
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152715"
---
# <a name="overview-of-inactive-mailboxes-in-office-365"></a>在 Office 365 中的非使用中信箱的概觀

您的組織可能需要將其保留組織之後保留先前的員工電子郵件。 根據您的組織保留需求，您可能需要幾個月數或年後結束工作，或您可能需要無限期保留信箱內容的保留信箱內容。 不論多久您需要保留電子郵件，您可以建立非使用中信箱 Office 365 保留離職員工的信箱中。 
  
## <a name="what-are-inactive-mailboxes"></a>什麼是不在作用中的信箱？

當員工離開組織 （或連上延伸請假） 時，您可以移除其 Office 365 帳戶。 員工的信箱資料會保留 30 天後帳戶遭到移除。 在此期間，您仍然可以復原信箱資料取消刪除帳戶。 30 天之後，資料會永久移除。
  
但如果您的組織需要保留離職員工信箱內容，您可以將信箱變成非使用中信箱將信箱置於訴訟暫止狀態或 Office 365 保留原則套用到安全性 & 合規性中心中的信箱然後移除對應的 Office 365 帳戶。 The contents of an inactive mailbox are retained for the duration of the Litigation Hold placed on the mailbox or the retention period of the Office 365 retention policy applied to it before the mailbox was deleted. You can still recover the corresponding user account for a 30-day period. 不過，30 天後，非使用中的信箱會保留在 Office 365 直到移除保留或保留原則。 
  
> [!NOTE]
> 我們已將 2017 年 7 月 1 日的期限延後，以建立新的「就地保留」來建立非使用中的信箱。但到今年年底或明年年初，您將無法在 Exchange Online 中建立新的「就地保留」。到時，只有「訴訟資料暫留」和 Office 365 保留原則可以用來建立非使用中的信箱。不過，仍會支援「就地保留」上現有的非使用中信箱，並且您可以繼續管理非使用信箱上的「就地保留」。這包括變更「就地保留」期間，以及透過移除「就地保留」永久刪除非使用中的信箱。 
 
  
## <a name="inactive-mailboxes-and-office-365-retention-policies"></a>非使用中信箱和 Office 365 保留原則

除了訴訟暫止狀態，安全 & 合規性中心內使用新的 Office 365 保留原則功能已停用信箱的另一種方法。 To use a retention policy to make an inactive mailbox: 
  
- 它具有 （因為 Skype 相關的內容會儲存在使用者的信箱中） 可套用到 Exchange 信箱或商務用 Skype位置。 
    
- 已設定要保留內容或保留，然後刪除內容。 如果保留原則設定為只刪除內容時，將原則套用至信箱將不會成為刪除信箱時不在作用中。
    
- 它可以是查詢為基礎，讓它會保留在符合搜尋查詢的項目。 
    
如需設定Office 365保留原則的詳細資訊，請參閱 ＜ [Overview of Office 365 中的保留原則](retention-policies.md)。
  
如果您使用保留原則來進行非使用中信箱時，Office 365 會繼續處理非使用中信箱的保留原則。 這表示如果保留原則設定來保持不變，然後刪除內容，將移至可復原的項目資料夾保留期間到期時, 和最後清除從非使用中的信箱項目。 如果Office 365保留原則不設定成已刪除的項目，尚未被永久刪除之使用者所 （之前進行信箱不在作用中） 的項目不會移至 [可復原的項目] 資料夾與將會保留無限期之後信箱成為非使用中。 
  
您可能會考慮建立專用於非使用中信箱Office 365保留原則。以下是執行這項工作原因及謹記下列事項。
  
- 您可以設定保留信箱內容僅只要符合先前員工貴組織的需求所需的保留原則。
    
- 它是一個好方法來識別非使用中信箱的保留原則只會套用至非使用中信箱因為。
    
- 您可以快速找出指派給組織中的非使用中信箱的保留原則。 This will make it easier to change the retention (or deletion) settings if necessary. 它也會讓它永久刪除非使用中的信箱，因為您可以只是它從原則移除使用安全性 & 合規性中心的工作變得更容易。 否則，您必須使用 Exchange Online PowerShell 來從非使用中的信箱中移除 [訴訟暫止狀態或安全性 & 合規性中心 PowerShell 從整個組織的 Office 365 保留原則中排除不在作用中的信箱。
    
- 如果您建立專用於非使用中信箱Office 365保留原則，您可以新增最多達 1000 個信箱原則。如果您是非常大型的組織，您可能必須建立多個Office 365保留原則，以用於非使用中的信箱。

> [!CAUTION]
> 如果您使用保留原則來停用信箱時，請勿變更或移除信箱的使用者主體名稱 (UPN) 後，再刪除對應的 Office 365 使用者帳戶。 此外，請勿變更主要 SMTP 位址 （也就衍生自 UPN） 或從之前進行非使用中信箱與信箱關聯的次要 SMTP 地址的清單中移除此電子郵件地址。 如果您變更 UPN 或電子郵件地址 （已指派給信箱的保留原則套用至其次），然後刪除若要停用信箱的使用者帳戶，您無法刪除非使用中信箱，當您不再需要保留 it。 這是因為您無法移除使用 UPN 或電子郵件地址 （若要識別非使用中的信箱），不同於存在時的保留原則一開始會套用到信箱的保留原則中的非使用中信箱。 如需刪除非使用中信箱的詳細資訊，請參閱[刪除非使用中信箱 Office 365 中](delete-an-inactive-mailbox.md)。
  
## <a name="inactive-mailboxes-and-ediscovery-case-holds"></a>不在作用中信箱和 eDiscovery 案件保留

如果與安全性 & 合規性中心中的 eDiscovery 案例相關聯保留信箱，然後該信箱或刪除使用者的 Office 365 帳戶，信箱將會變為作用中的信箱。 However, we don't recommend using eDiscovery case holds to make a mailbox inactive. That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue. At some point, a legal case will probably end and the holds associated with the case will be removed and the eDiscovery case will be closed. In fact, if a hold that's placed on an inactive mailbox is associated with an eDiscovery case, and then the hold is released or the eDiscovery case is closed (or deleted), the inactive mailbox will be permanently deleted. Additionally, you can't create a time-based eDiscovery hold. That's means content in an inactive mailbox will be retained forever or until the hold is removed and the inactive mailbox is deleted. Therefore, we recommend using a Litigation Hold or an Office 365 retention policy for inactive mailboxes.
  
如需 eDiscovery 案例和保留的詳細資訊，請參閱 < <b0>eDiscovery 案例</b0>。
  
## <a name="inactive-mailboxes-and-office-365-labels"></a>非使用中信箱和 Office 365 標籤

Office 365標籤有助於分類管理在組織中的電子郵件資料並強制執行該分類為基礎的保留規則。標籤可以套用至電子郵件項目由使用者手動或自動將管理員及電子郵件項目只能有單一標籤指派給它。如果使用者的信箱中的單一電子郵件項目已指派給它和信箱的標籤或刪除使用者Office 365帳戶，信箱將成為非使用中的信箱。類似於 eDiscovery 案件保留，我們不建議使用標籤來讓信箱成為非使用中。但是，我們建議您是使用訴訟暫止狀態或Office 365保留原則。請注意但如果是標籤，可能不知道標籤已套用至電子郵件項目及刪除使用者帳戶時然後不經意進行非使用中的信箱。 
  
如需標籤的詳細資訊，請參閱 ＜ [Overview of Office 365 中的標籤](labels.md)。
  
## <a name="inactive-mailboxes-and-exchange-mrm-retention-policies"></a>非使用中信箱和 Exchange MRM 保留原則

如果它成為非使用中時，Exchange 保留原則 （通訊記錄管理或 MRM，功能在 Exchange Online） 套用至信箱，會將任何刪除原則 （也就是設定以**刪除**保留動作的保留標記）繼續處理非使用中信箱上。 這表示與刪除原則標記的項目要移至 [可復原的項目] 資料夾保留期間到期時。 保留期間到期時將這些項目已清除從非使用中的信箱。 如果不在作用中信箱的未指定保留持續時間，則會無限期保留復原的項目] 資料夾中的項目。 
  
相反地，會略過任何封存原則 （也就是以**MoveToArchive** ： 保留動作設定的保留標記） 所隨附指派給非使用中信箱的保留原則。 這表示在非使用中信箱與封存原則標記的項目仍然在主要信箱的保留期間到期時。 它們不被移至封存信箱或封存信箱中 [可復原的項目] 資料夾。 他們將會無限期保留。 
  
## <a name="creating-an-inactive-mailbox"></a>建立非使用中的信箱

若要停用信箱，它必須被指派Exchange Online (Plan 2) 授權使訴訟暫止狀態或Office 365保留原則可套用至信箱會在刪除之前。 在刪除信箱後，已與它相關聯的 Exchange Online 授權可指派給新的使用者。 不在作用中的信箱不需要持續進行的授權。
  
下表摘要說明程序，讓不同保留案例的非使用中信箱。 如需詳細資訊，請參閱 <<c0>在 Office 365 中的管理非使用中信箱。
  
|**若要...**|**執行此動作...]**|**結果**|
|:-----|:-----|:-----|
|只有在員工離職之後無限期保留信箱內容  <br/> | 信箱置於訴訟暫止狀態或Office 365保留原則套用至信箱。  <br/>  不要將保留持續時間指定為訴訟暫止狀態或未設定刪除項目 ； Office 365保留原則或者您可以使用永久保留項目保留原則。  <br/>  移除使用者的Office 365帳戶。  <br/> |非使用中信箱，在 [可復原的項目] 資料夾中包含的項目中的所有內容會無限期都保留。  <br/> |
|信箱內容保留特定的一段之後員工離職然後予以刪除  <br/> | Office 365 保留原則套用至信箱。  <br/>  設定保留，然後刪除項目，在保留期間到期時將保留原則。  <br/>  移除使用者的Office 365帳戶。  <br/> |當某個信箱項目的保留期間到期時，項目移至 [可復原的項目] 資料夾，然後再永久刪除 （清除） 從非使用中信箱 （適用於 Exchange 信箱） 的已刪除的項目保留期間到期時。 可設定之 Office 365 保留原則的保留期間根據原始日期信箱項目所接收或建立，或上次修改的日期。  <br/> |
   
**附註：** 如果在信箱上已放置訴訟暫止狀態或 Office 365 保留原則已套用至其，您只需要是刪除對應的 Office 365 使用者帳戶，來建立非使用中的信箱。 
  
## <a name="managing-inactive-mailboxes"></a>管理非使用中信箱

您讓信箱成為非使用中之後，您可以在非使用中的信箱上執行各種管理工作。
  
- **變更非使用中信箱的保留期間**信箱進行非使用中之後，您可以變更套用至非使用中信箱的訴訟暫止狀態或 Office 365 保留原則的保留期間。 如需逐步程序，請參閱[變更 Office 365 中的非使用中信箱的保留期間](change-the-hold-duration-for-an-inactive-mailbox.md)。

  > [!NOTE]
  > 您無法將其他保留原則套用至非使用中的信箱。 您只可以變更現有保留原則套用至非使用中信箱的保留期間。
    
- **復原非使用中信箱**如果將離職員工 （或在請假員工） 傳回至您的組織或新進員工雇用採取離職員工的工作職責，您可以復原非使用中信箱的內容。 當您復原不在作用中的信箱時，信箱轉換成新的信箱、 保留的內容和非使用中的信箱資料夾結構，及信箱連結至新的使用者帳戶。 它會復原之後，非使用中的信箱不存在。 如需逐步程序及復原非使用中信箱時，會發生什麼情況的資訊，請參閱[復原非使用中信箱 Office 365 中](recover-an-inactive-mailbox.md)。
    
- **還原非使用中信箱**如果另一位員工承擔離職員工，工作職責或其他人員需要存取非使用中信箱的內容，您可以還原 （或合併） 到現有的信箱不在作用中信箱的內容。 當您還原非使用中信箱內容複製到另一個信箱。 非使用中的信箱，則會保留與會維持不在作用中的信箱。 非使用中信箱仍可搜尋使用 eDiscovery 工具、 其內容可以還原至另一個信箱和復原或刪除日後。 如需逐步程序，請參閱 <<c0>還原 Office 365 中的非使用中信箱。
    
- **刪除非使用中信箱**當您不再需要保留非使用中信箱的內容時，您可以藉由移除所有保留或 Office 365 保留原則套用至非使用中信箱永久刪除它。 如果信箱進行非使用中超過 30 天之內，它會標示為永久刪除之後移除保留。 如果信箱可在過去 30 天內不在作用中，您可以使其成為使用一次之後移除保留或保留原則。 如需逐步程序，請參閱[刪除非使用中信箱 Office 365 中](delete-an-inactive-mailbox.md)。