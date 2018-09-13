---
title: 保留原則概觀
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 5e377752-700d-4870-9b6d-12bfc12d2423
description: 透過保留原則，您可以主動決定要保留內容、刪除內容，還是兩者 (保留然後刪除內容)；將單一原則套用到整個組織或只套用到特定位置或使用者；以及將原則套用到所有內容或只套用到符合特定條件的內容
ms.openlocfilehash: 82def4182607e6dde4f9d6612cdb93f6f8564f2a
ms.sourcegitcommit: edf5db9357c0d34573f8cc406314525ef10d1eb9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/28/2018
ms.locfileid: "23230015"
---
# <a name="overview-of-retention-policies"></a><span data-ttu-id="0e9b1-103">保留原則概觀</span><span class="sxs-lookup"><span data-stu-id="0e9b1-103">Overview of retention policies</span></span>

<span data-ttu-id="0e9b1-p101">對大多數組織來說，其資料 (電子郵件、文件、即時訊息等) 的數量和複雜性日益增加。有效管理或控管此資訊至關重要，因為您需要：</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p101">For most organizations, the volume and complexity of their data is increasing daily - email, documents, instant messages, and more. Effectively managing or governing this information is important because you need to:</span></span>
  
- <span data-ttu-id="0e9b1-106">**主動遵守產業規範和內部原則**，需要您將某些內容至少保留一段時間，例如，Sarbanes-Oxley 法案可能需要您將某些類型的內容保留七年。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-106">**Comply proactively with industry regulations and internal policies** that require you to retain content for a minimum period of time - for example, the Sarbanes-Oxley Act might require you to retain certain types of content for seven years.</span></span> 
    
- <span data-ttu-id="0e9b1-107">**降低發生訴訟或安全性漏洞的風險**，方法為永久刪除您不再需要保留的舊內容。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-107">**Reduce your risk in the event of litigation or a security breach** by permanently deleting old content that you're no longer required to keep.</span></span> 
    
- <span data-ttu-id="0e9b1-108">**協助貴組織有效分享知識並提高靈活度**，方法為確保使用者只使用目前和相關的內容。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-108">**Help your organization to share knowledge effectively and be more agile** by ensuring that your users work only with content that's current and relevant to them.</span></span> 
    
<span data-ttu-id="0e9b1-p102">Office 365 中的保留原則可協助您實現所有這些目標。管理內容通常需要下列兩個動作：</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p102">A retention policy in Office 365 can help you achieve all of these goals. Managing content commonly requires two actions:</span></span>
  
- <span data-ttu-id="0e9b1-111">**保留**內容，以便無法在保留期間結束之前將其永久刪除。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-111">**Retaining** content so that it can't be permanently deleted before the end of the retention period.</span></span> 
    
- <span data-ttu-id="0e9b1-112">在保留期間結束之前，永久**刪除**內容。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-112">**Deleting** content permanently at the end of the retention period.</span></span> 
    
<span data-ttu-id="0e9b1-113">透過保留原則，您可以：</span><span class="sxs-lookup"><span data-stu-id="0e9b1-113">With a retention policy, you can:</span></span>
  
- <span data-ttu-id="0e9b1-114">主動決定要保留內容、刪除內容，還是兩者 (保留然後刪除內容)。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-114">Decide proactively whether to retain content, delete content, or both - retain and then delete the content.</span></span>
    
- <span data-ttu-id="0e9b1-115">將單一原則套用到整個組織或只套用到特定位置或使用者。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-115">Apply a single policy to the entire organization or just specific locations or users.</span></span>
    
- <span data-ttu-id="0e9b1-116">將原則套用到所有內容或只套用到符合特定條件的內容，例如包含特定關鍵字或[特定類型的敏感資訊](what-the-sensitive-information-types-look-for.md)的內容。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-116">Apply a policy to all content or just content meeting certain conditions, such as content containing specific keywords or [specific types of sensitive information](what-the-sensitive-information-types-look-for.md).</span></span>
    
<span data-ttu-id="0e9b1-p103">當內容受限於保留原則時，人員可以繼續編輯及使用的內容，一樣不會變更，因為內容保留在其原始位置。但在某人編輯或刪除受限於原則的內容時，將會有複本儲存至安全位置，在原則仍然有效時會持續進行保留。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p103">When content is subject to a preservation policy, people can continue to edit and work with the content as if nothing’s changed because the content’s preserved in place, in its original location. But if someone edits or deletes content that’s subject to the policy, a copy is saved to a secure location where it’s preserved while the policy is in effect.</span></span>
  
<span data-ttu-id="0e9b1-p104">最後，有些組織可能需要遵守法規，例如證券交易委員會 (SEC) 法規 17a-4，要求在保留原則開啟之後，不能關閉或執行較不嚴格的限制。若要滿足這個需求，您可以使用「保留鎖定」。原則鎖定之後，任何人 (包括系統管理員) 均無法關閉原則或執行較不嚴格的限制。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p104">Finally, some organizations may need to comply with rules defined by regulatory bodies such as the Securities and Exchange Commission (SEC) Rule 17a-4, which requires that after a preservation policy is turned on, it cannot be turned off or made less restrictive. To meet this requirement, you can use Preservation Lock. After a policy’s been locked, no one -- including the administrator -- can turn off the policy or make it less restrictive.</span></span>
  
<span data-ttu-id="0e9b1-122">您可以在 Office 365 安全性與合規性中心的 [保留]**** 頁面上建立及管理保留原則。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-122">You create and manage DLP policies on the Data loss prevention page in the Office 365 Compliance Center.</span></span> 
  
![安全性與合規性中心內的保留頁面](media/107fc33a-6a29-44d1-85e4-0efef0544147.png)
  
> [!NOTE]
> <span data-ttu-id="0e9b1-p105">若要在保留原則中包含 Exchange Online 信箱，必須指派 Exchange Online 方案 2 授權給信箱。如果指派 Exchange Online 方案 1 授權給信箱，您必須為它指派另一個 Exchange Online 封存授權，才能將它包含在保留原則中。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p105">To include an Exchange Online mailbox in a retention policy, the mailbox must be assigned an Exchange Online Plan 2 license. If a mailbox is assigned an Exchange Online Plan 1 license, you would have to assign it a separate Exchange Online Archiving license to include it in a retention policy.</span></span> 
  
## <a name="how-a-retention-policy-works-with-content-in-place"></a><span data-ttu-id="0e9b1-126">保留原則如何就地使用內容</span><span class="sxs-lookup"><span data-stu-id="0e9b1-126">How a preservation policy works with content in place</span></span>

<span data-ttu-id="0e9b1-p106">當您在保留原則中包括網站或信箱這類的位置時，內容仍會留在其原始位置。使用者可以繼續使用其文件或郵件，一樣不會變更。但在他們編輯或刪除原則中包含的內容時，系統會保留內容的複本，與您套用原則時存在的內容相同。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p106">When you include a location such as a site or mailbox in a retention policy, the content remains in its original location. People can continue to work with their documents or mail as if nothing's changed. But if they edit or delete content that's included in the policy, a copy of the content as it existed when you applied the policy is retained.</span></span>
  
<span data-ttu-id="0e9b1-p107">對於網站，當使用者編輯或刪除原始內容時，原始內容的複本會保留在文件保留庫；對於電子郵件和公用資料夾，複本會保留在 [可復原的項目] 資料夾中。大部分人員看不到這些安全位置和保留內容。使用保留原則時，人員甚至不知道其內容受到原則約束。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p107">For sites, a copy of the original content is retained in the Preservation Hold library when users edit or delete it; for email and public folders, the copy is retained in the Recoverable Items folder. These secure locations and the retained content are not visible to most people. With a retention policy, people do not even need to know that their content is subject to the policy.</span></span>
  
<span data-ttu-id="0e9b1-133">附註：</span><span class="sxs-lookup"><span data-stu-id="0e9b1-133">Notes:</span></span>
  
- <span data-ttu-id="0e9b1-134">Skype 內容儲存在 Exchange 中，在此會根據訊息類型 (電子郵件或交談) 套用原則。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-134">Skype content is stored in Exchange, where the policy is applied based on message type (email or conversation).</span></span>
    
- <span data-ttu-id="0e9b1-135">套用到 Office 365 群組的保留原則同時包含群組信箱和網站。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-135">A retention policy applied to an Office 365 group includes both the group mailbox and site.</span></span>
    
### <a name="content-in-onedrive-accounts-and-sharepoint-sites"></a><span data-ttu-id="0e9b1-136">OneDrive 帳戶和 SharePoint 網站中的內容</span><span class="sxs-lookup"><span data-stu-id="0e9b1-136">Content in OneDrive accounts and SharePoint sites</span></span>

<span data-ttu-id="0e9b1-p108">保留原則是在網站層級套用。在保留原則中包含 SharePoint 網站或 OneDrive 帳戶時，即會建立文件保留庫。大部分的使用者都無法檢視文件保留庫，因為只有網站集合管理員才能檢視文件保留庫。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p108">A preservation policy is applied at the level of a site. When you include a site in a preservation policy, a Preservation Hold library is created, if one doesn’t already exist. Most users can’t view the Preservation Hold library because it’s visible only to site collection owners.</span></span>
  
<span data-ttu-id="0e9b1-p109">如有使用者嘗試變更或刪除受限於保留原則的網站內容，保留原則會先檢查內容在套用原則後是否有所變更。如果這是套用保留原則後的第一次變更，保留原則會先將內容複製到文件保留庫，然後允許使用者變更或刪除原始內容。請注意，網站中的任何內容都可複製到文件保留庫，即使內容不符合保留原則所使用的查詢亦然。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p109">If a person attempts to change or delete content in a site that’s subject to a preservation policy, first the policy checks whether the content’s been changed since the policy was applied. If this is the first change since the preservation policy was applied, the policy copies the content to the Preservation Hold library, and then allows the person to change or delete the original content. Note that any content in the site can be copied to the Preservation Hold library, even if the content does not match the filter of the query used by the preservation policy.</span></span>
  
<span data-ttu-id="0e9b1-p110">接著，計時器工作會清除文件保留庫。計時器工作會定期執行，並比較文件保留庫中的所有內容與網站上保留原則所使用的所有查詢。除非內容至少符合一個查詢，否則計時器工作將從文件保留庫中永久刪除該內容。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p110">Then a timer job cleans up the Preservation Hold library. The timer job runs periodically and compares all content in the Preservation Hold library to the filters used by the preservation policies on the site. Unless content matches at least one of the filters, the timer job permanently deletes the content from the Preservation Hold library.</span></span>
  
<span data-ttu-id="0e9b1-p111">前述機制適用於在套用保留原則時即存在的內容。除此之外，任何在網站納入保留原則後才在網站中建立或新增的內容，在刪除之後仍將保留。不過，新內容在第一次編輯時並不會複製到文件保留庫，而只有在刪除時才會。若要保留所有檔案版本，您必須開啟版本設定 — 請參閱以下關於版本的章節。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p111">The previous applies to content that exists when the preservation policy is applied. In addition, any new content that’s created or added to the site after it was included in the policy will be preserved after deletion. However, new content isn’t copied to the Preservation Hold library the first time it’s edited, only when it’s deleted. To preserve versions for all files, you need to turn on versioning – see the later section on versioning.</span></span>
  
<span data-ttu-id="0e9b1-p112">請注意，如果使用者嘗試刪除受限於保留原則的文件庫、清單、資料夾或網站，將會收到錯誤訊息。第一次移動或刪除資料夾中任何受限於原則的檔案時，使用者可以刪除資料夾。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p112">Note that a user will receive an error if they try to delete a library, list, folder, or site that's subject to a retention policy. A user can delete a folder if they first move or delete any files in the folder that are subject to the policy.</span></span>
  
![SharePoint 和 OneDrive 中的保留流程圖](media/858702f8-5a09-4464-86d0-3b16fed800f3.png)
  
<span data-ttu-id="0e9b1-153">將保留原則指派給 OneDrive 帳戶或 SharePoint 網站之後，內容可以依循下列兩個途徑之一：</span><span class="sxs-lookup"><span data-stu-id="0e9b1-153">After a retention policy is assigned to a OneDrive account or SharePoint site, content can follow one of two paths:</span></span>
  
1. <span data-ttu-id="0e9b1-p113">在保留期間，**如果已修改或刪除內容**，則會在文件保留庫中建立指派保留原則時存在之原始內容的複本。在那裡，計時器工作會定期執行，並識別保留期間已過期的項目，然後在保留期間結束後的七天內永久刪除這些項目。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p113">**If the content is modified or deleted** during the retention period, a copy of the original content as it existed when the retention policy was assigned is created in the Preservation Hold library. There, a timer job runs periodically and identifies items whose retention period has expired, and these items are permanently deleted within seven days of the end of the retention period.</span></span> 
    
2. <span data-ttu-id="0e9b1-p114">在保留期間，**如果未修改或刪除內容**，則內容會在保留期間結束時移至第一階段資源回收筒。如果使用者從該處刪除內容，或清空此資源回收筒 (也稱為清除)，則文件會移至第二階段資源回收筒。93 天保留期間涵蓋了第一和第二階段資源回收筒。在 93 天保留期間結束時，將永久刪除第一或第二階段資源回收筒中的文件。請注意，資源回收筒未編製索引，因此搜尋不會在該處尋找內容。這表示，eDiscovery 保留無法在資源回收筒中找到任何內容來保留。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p114">**If the content is not modified or deleted** during the retention period, it's moved to the first-stage Recycle Bin at the end of the retention period. If a user deletes the content from there or empties this Recycle Bin (also known as purging), the document is moved to the second-stage Recycle Bin. A 93-day retention period spans both the first- and second-stage recycle bins. At the end of 93 days, the document is permanently deleted from wherever it resides, in either the first- or second-stage Recycle Bin. Note that the Recycle Bin is not indexed and therefore searches do not find content there. This means that an eDiscovery hold can't locate any content in the Recycle Bin in order to hold it.</span></span> 
    
### <a name="content-in-mailboxes-and-public-folders"></a><span data-ttu-id="0e9b1-161">信箱與公用資料夾中的內容</span><span class="sxs-lookup"><span data-stu-id="0e9b1-161">Content in mailboxes and public folders</span></span>

<span data-ttu-id="0e9b1-p115">對於使用者的信箱、行事曆和其他項目，保留原則會在信箱層級套用。對於公用資料夾，保留原則會套用在資料夾層級套用，而不是信箱層級。信箱和公用資料夾都是使用 [可復原的項目] 資料夾來保留項目。已指派 eDiscovery 權限的人員可以檢視其他使用者的 [可復原的項目] 資料夾中的項目。 </span><span class="sxs-lookup"><span data-stu-id="0e9b1-p115">For a user's mail and other items, a preservation policy is applied at the level of a mailbox. For a public folder, a preservation policy is applied at the folder level, not the mailbox level. Both a mailbox and a public folder use the Recoverable Items folder to preserve items. Only people that have been assigned eDiscovery permissions can view another user's Recoverable Items folder.</span></span>
  
<span data-ttu-id="0e9b1-p116">根據預設，當使用者刪除 [刪除的郵件] 資料夾以外的資料夾中的郵件時，該郵件會移至 [刪除的郵件] 資料夾。當使用者刪除 [刪除的郵件] 資料夾中的項目時，郵件會移至 [可復原的項目] 資料夾。此外，使用者可以將任何資料夾中的項目虛刪除 (SHIFT+DELETE)，這會略過 [刪除的郵件] 資料夾，並將項目直接移至 [可復原的項目] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p116">By default, when a person deletes a message from a folder other than the Deleted Items folder, the message is moved to the Deleted Items folder. When a person deletes an item from the Deleted Items folder, the message is moved to the Recoverable Items folder and disappears from the user’s view. In addition, a person can soft delete an item (SHIFT+DELETE) in any folder, which bypasses the Deleted Items folder and places the item directly in the Recoverable Items folder.</span></span>
  
<span data-ttu-id="0e9b1-p117">程序會定期評估 [可復原的項目] 資料夾中的項目。如果項目不符合至少一個保留原則的規則，則系統會從 [可復原的項目] 資料夾中永久刪除項目 (也稱為硬刪除)。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p117">A process periodically evaluates items in the Recoverable Items folder. If an item doesn't match the rules of at least one retention policy, the item is permanently deleted (also called hard deleted) from the Recoverable Items folder.</span></span>
  
<span data-ttu-id="0e9b1-p118">當使用者嘗試變更信箱項目的特定內容時 (例如主旨、內文、附件、寄件者和收件者，或是傳送或接收郵件的日期)，在認可變更之前，會先將原始項目的複本儲存至 [可復原的項目] 資料夾。後續每次變更時都會執行此動作。在保留期間結束時，即會永久刪除 [可復原的項目] 資料夾中的複本。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p118">The Recoverable Items folder also contains a Versions folder. When a person attempts to change certain properties of a mailbox item -- such as the subject, body, attachments, senders and recipients, or date sent or received for a message  -- a copy of the original item is saved to the Versions folder before the change is committed. This happens for each subsequent change. After the preservation policy is removed, copies in the Versions folder are removed by the mailbox assistant.</span></span>
  
<span data-ttu-id="0e9b1-p119">如果使用者離職，且其信箱包含在保留原則中，則一旦刪除使用者的 Office 365 帳戶，信箱就會變成非作用中信箱。非作用中信箱的內容仍受限於信箱在變成非作用中之前放置在其上的任何保留原則，而且 eDiscovery 可搜尋此內容。如需詳細資訊，請參閱 [Exchange Online 中的非作用中信箱](https://go.microsoft.com/fwlink/?linkid=846909) (機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p119">If a user leaves your organization, and their mailbox is included in a retention policy, the mailbox becomes an inactive mailbox when the user's Office 365 account is deleted. The contents of an inactive mailbox are still subject to any retention policy that was placed on the mailbox before it was made inactive, and the contents are available to an eDiscovery search. For more information, see [Inactive mailboxes in Exchange Online](https://go.microsoft.com/fwlink/?linkid=846909).</span></span>
  
![電子郵件和公用資料夾中的保留流程圖](media/88f174cc-bbf4-4305-93d7-0515f496c8f9.png)
  
<span data-ttu-id="0e9b1-178">將保留原則指派給信箱或公用資料夾之後，內容可以依循下列兩個途徑之一：</span><span class="sxs-lookup"><span data-stu-id="0e9b1-178">After a retention policy is assigned to a mailbox or public folder, content can follow one of two paths:</span></span>
  
1. <span data-ttu-id="0e9b1-p120">在保留期間，**如果使用者已永久修改或刪除項目** (按 SHIFT+DELETE 或從 [刪除的郵件] 中刪除)，則項目會移至 (或在編輯的情況下複製到) [可復原的項目] 資料夾。在那裡，此程序會定期執行，並識別其保留期間已過期的項目，而且會在保留期間結束後的 14 天內永久刪除這些項目。請注意，14 天是預設設定，但它最多可設為 30 天。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p120">**If the item is modified or permanently deleted** by the user (either SHIFT+DELETE or deleted from Deleted Items) during the retention period, the item is moved (or copied, in the case of edit) to the Recoverable Items folder. There, a process runs periodically and identifies items whose retention period has expired, and these items are permanently deleted within 14 days of the end of the retention period. Note that 14 days is the default setting, but it can be configured up to 30 days.</span></span> 
    
2. <span data-ttu-id="0e9b1-p121">在保留期間，**如果未修改或刪除項目**，則相同的程序會在信箱中的所有資料夾上定期執行，並識別其保留期間已過期的項目，而且會在保留期間結束後的 14 天內永久刪除這些項目。請注意，14 天是預設設定，但它最多可設為 30 天。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p121">**If the item is not modified or deleted** during the retention period, the same process runs periodically on all folders in the mailbox and identifies items whose retention period has expired, and these items are permanently deleted within 14 days of the end of the retention period. Note that 14 days is the default setting but it can be configured up to 30 days.</span></span> 
    
## <a name="how-a-retention-policy-works-with-document-versions-in-a-site"></a><span data-ttu-id="0e9b1-184">保留原則如何使用網站中的文件版本</span><span class="sxs-lookup"><span data-stu-id="0e9b1-184">How a preservation policy works with document versions in a site</span></span>

<span data-ttu-id="0e9b1-p122">版本設定是 SharePoint Online 和商務用 OneDrive 中所有文件庫的功能。根據預設，版本設定會保留至少一百個主要版本，但您也可以提高此限制。如需詳細資訊，請參閱[啟用和設定清單或文件庫的版本設定](https://support.office.com/article/1555d642-23ee-446a-990a-bcab618c7a37)。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p122">Versioning is a feature of all document libraries in SharePoint Online and OneDrive for Business. By default, versioning retains a minimum of one hundred major versions, though you can increase this limit. For more information, see [Enable and configure versioning for a list or library](https://support.office.com/article/1555d642-23ee-446a-990a-bcab618c7a37).</span></span>
  
<span data-ttu-id="0e9b1-p123">保留原則會保留 SharePoint 網站或 OneDrive 帳戶中文件的所有版本。每次編輯或刪除受限於保留原則的文件時，版本會複製到文件保留庫。文件保留庫中文件的每個版本都會以個別項目存在，並有自己的保留期間：</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p123">A retention policy retains all versions of a document in a SharePoint site or OneDrive account. Each time a document subject to a retention policy is edited or deleted, a version is copied to the Preservation Hold library. Each version of a document in the Preservation Hold library exists as a separate item with its own retention period:</span></span>
  
- <span data-ttu-id="0e9b1-p124">如果保留原則是以建立內容的時間為基礎，則每個版本都有與原始文件相同的到期日。原始文件及其版本都在相同時間到期。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p124">If the retention policy is based on when the content was created, each version has the same expiration date as the original document. The original document and its versions all expire at the same time.</span></span>
    
- <span data-ttu-id="0e9b1-p125">如果保留原則根據內容的前次修改時間，則每個版本都有自己的到期日，而此到期日根據為了建立該版本而修改原始文件的時間。原始文件及其版本彼此單獨到期。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p125">If the retention policy is based on when the content was last modified, each version has its own expiration date based on when the original document was modified to create that version. The original documents and its versions expire independently of each other.</span></span>
    
## <a name="retaining-content-for-a-specific-period-of-time"></a><span data-ttu-id="0e9b1-195">將內容保留特定的一段時間</span><span class="sxs-lookup"><span data-stu-id="0e9b1-195">Preserving content for a specific period of time</span></span>

<span data-ttu-id="0e9b1-p126">透過保留原則，您可以無限期保留內容，或將內容保留特定的天數、月數或年數。請注意，保留內容的持續時間是從內容的存留期，而不是從套用保留原則的時間算起。您可以選擇存留期根據內容的建立時間，還是內容的前次修改時間 (適用於 OneDrive 和 SharePoint)。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p126">With a retention policy, you can retain content indefinitely or for a specific number of days, months, or years. Note that the duration for how long content is retained is calculated from the age of the content, not from when the retention policy is applied. You can choose whether the age is based on when the content was created or (for OneDrive and SharePoint) when it was last modified.</span></span>
  
<span data-ttu-id="0e9b1-p127">例如，如果您想要將網站中的內容自從前次前次修改後保留七年，而且該網站中的某文件已有六年未曾修改，則若該文件後續仍未修改，則只會再保留一年。如果該文件重新編輯，則其存留期將會從新的前次修改日期算起，因而會再保留七年。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p127">For example, if you want to preserve content in a site for seven years, and a document in that site hasn’t been modified in six years, the document will be preserved for only another year if it’s not modified. If the document is edited again, the age of the document is calculated from the new last modified date, and it will be preserved for another seven years.</span></span>
  
<span data-ttu-id="0e9b1-p128">同樣地，如果您想要將信箱中的內容保留七年，而且六年前已傳送某訊息，則該訊息只會保留一年。對於 Exchange 內容，時間一律根據接收或傳送的日期 (它們是相同的)。根據前次修改時間保留內容僅適用於 OneDrive 和 SharePoint 中的網站內容。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p128">Similarly, if you want to retain content in a mailbox for seven years, and a message was sent six years ago, the message will be retained for only one year. For Exchange content, the age is always based on the date received or sent (they are the same). Retaining content based on when it was last modified applies only to site content in OneDrive and SharePoint.</span></span>
  
<span data-ttu-id="0e9b1-p129">您可以選擇是否要在保留期間結束時永久刪除內容。保留原則也可以僅刪除舊內容，而不保留它 - 請參閱下節。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p129">You can choose whether you want the content to be permanently deleted at the end of the retention period. A retention policy can also simply delete old content without retaining it - see the next section.</span></span>
  
![保留設定頁面](media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)
  
## <a name="deleting-content-thats-older-than-a-specific-age"></a><span data-ttu-id="0e9b1-207">刪除早於特定存留期的內容</span><span class="sxs-lookup"><span data-stu-id="0e9b1-207">Deleting content that's older than a specific age</span></span>

<span data-ttu-id="0e9b1-208">保留原則可以同時保留，然後刪除內容，或僅刪除舊內容，而不保留它。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-208">A retention policy can both retain and then delete content, or simply delete old content without retaining it.</span></span>
  
<span data-ttu-id="0e9b1-209">如果您的保留原則刪 內容，請務必了解，文件刪除原則所指定的期限並不是從指派原則的時間算起，而是從建立或修改內容的時間算起。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-209">If your retention policy deletes content, it's important to understand that the time period specified for a retention policy is calculated from the time when the content was created or modified, not the time since the policy was assigned.</span></span>
  
![刪除設定](media/042f9571-96f4-458f-8f38-fad3ed68ed31.png)
  
<span data-ttu-id="0e9b1-p130">例如，假設您建立三年後刪除內容的保留原則，然後將該原則指派給所有 OneDrive 帳戶，其中包含許多四或五年前建立的內容。在此情況下，第一次指派保留原則後，很快就會刪除大量的內容。基於這個原因，**刪除內容的保留原則可以對您的內容產生相當大的影響**。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p130">For example, suppose that you create a retention policy that deletes content after three years, and then assign that policy to all OneDrive accounts, which contain a lot of content that was created four or five years ago. In this case, a lot of content will be deleted soon after assigning the retention policy for the first time. For this reason, **a retention policy that deletes content can have a considerable impact on your content**.</span></span> 
  
<span data-ttu-id="0e9b1-p131">因此，在第一次將保留原則指派給網站之前，您應先考量現有內容的存留期，以及原則對該內容可能造成的影響。您也可以在指派新原則之前先與使用者溝通，讓他們有時間評估可能的影響。請注意，只在您建立保留原則之前，檢閱其設定時才會出現此警告。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p131">Therefore, before you assign a policy to a site for the first time, you should first consider the age of the existing content and how the policy may impact that existing content. You may also want to communicate the new policy to site owners before assigning it, to give them time to assess the possible impact.</span></span>
  
![有關刪除內容的警告](media/59c26b19-3628-4cc1-9a73-a05127a8e81b.png)
  
## <a name="advanced-settings-that-apply-a-policy-only-to-content-that-meets-certain-conditions"></a><span data-ttu-id="0e9b1-218">只將原則套用到符合特定條件之內容的進階設定</span><span class="sxs-lookup"><span data-stu-id="0e9b1-218">Advanced settings that apply a policy only to content that meets certain conditions</span></span>

<span data-ttu-id="0e9b1-219">保留原則可以套用至其包含之位置中的所有內容，或您可以選擇只將保留原則套用到包含特定關鍵字或[特定類型的敏感資訊](what-the-sensitive-information-types-look-for.md)的內容。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-219">A retention policy can apply to all content in the locations that it includes, or you can choose to apply a retention policy only to content that contains specific keywords or [specific types of sensitive information](what-the-sensitive-information-types-look-for.md).</span></span>
  
![進階保留選項](media/e8d9dd42-c062-4e8b-a2ca-bffe3ea298e0.png)
  
### <a name="retain-content-that-contains-specific-keywords"></a><span data-ttu-id="0e9b1-221">保留包含特定關鍵字的內容</span><span class="sxs-lookup"><span data-stu-id="0e9b1-221">Retain content that contains specific keywords</span></span>

<span data-ttu-id="0e9b1-p132">您可以只將保留原則套用至符合特定條件的內容，然後只對該內容採取保留動作。可使用的條件現在支援將保留原則套用至包含特定字詞或片語的內容。您可以使用 AND、OR、NOT 等搜尋運算子來精簡查詢。如需這些運算子的詳細資訊，請參閱[內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md) (機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p132">You can apply a retention policy only to content that satisfies certain conditions, and then take retention actions on just that content. The conditions available now support applying a retention policy to content that contains specific words or phrases. You can refine your query by using search operators like AND, OR, and NOT. For more information on these operators, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
<span data-ttu-id="0e9b1-226">即將推出對新增可搜尋屬性 (例如 **subject:**) 的支援。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-226">Support for adding searchable properties (for example, **subject:**) is coming soon.</span></span>
  
<span data-ttu-id="0e9b1-227">請注意，查詢型保留會使用搜尋索引來識別內容。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-227">Note that query-based retention uses the search index to identify content.</span></span>
  
![查詢編輯器](media/2c31b412-922e-4a88-89e4-5175c23d9b5f.png)
  
### <a name="retain-content-that-contains-sensitive-information"></a><span data-ttu-id="0e9b1-229">保留包含敏感資訊的內容</span><span class="sxs-lookup"><span data-stu-id="0e9b1-229">Retain content that contains sensitive information</span></span>

<span data-ttu-id="0e9b1-p133">您也可以只將保留原則套用至包含[特定類型的敏感資訊](what-the-sensitive-information-types-look-for.md)的內容。例如，您可以選擇只將唯一的保留需求套用至包含個人識別資訊 (PII) 的內容，例如納稅人身分識別碼、社會安全編號或護照號碼。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p133">You can also apply a retention policy only to content that contains [specific types of sensitive information](what-the-sensitive-information-types-look-for.md). For example, you can choose to apply unique retention requirements only to content that contains personally identifiable information (PII) such as taxpayer identification numbers, social security numbers, or passport numbers.</span></span>
  
![敏感資訊類型頁面](media/8b104819-d185-4d58-b6b3-d06e82686a05.png)
  
<span data-ttu-id="0e9b1-233">附註：</span><span class="sxs-lookup"><span data-stu-id="0e9b1-233">Notes:</span></span>
  
- <span data-ttu-id="0e9b1-234">敏感資訊的進階保留不適用於 Exchange 公用資料夾或商務用 Skype，因為這些位置不支援敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-234">Advanced retention for sensitive information doesn't apply to Exchange public folders or Skype for Business because those locations don't support sensitive information types.</span></span>
    
- <span data-ttu-id="0e9b1-p134">您應該了解 Exchange Online 會使用傳輸規則來識別敏感資訊，因此這僅適用於傳輸中的郵件，不適用於已儲存在信箱中的所有項目。對於 Exchange Online，這表示保留原則可以識別敏感資訊，並只對在原則套用至信箱**之後**收到的訊息採取保留動作。(請注意，上一節所述的查詢型保留並沒有這項限制，因為它會使用搜尋索引來識別內容)。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p134">You should understand that Exchange Online uses transport rules to identify sensitive information, so this works only on messages in transit — not on all items already stored in a mailbox. For Exchange Online, this means that a retention policy can identify sensitive information and take retention actions only on messages that are received **after** the policy is applied to the mailbox. (Note that query-based retention described in the previous section doesn't have this limitation because it uses the search index to identify content.)</span></span> 
    
## <a name="applying-a-retention-policy-to-an-entire-organization-or-specific-locations"></a><span data-ttu-id="0e9b1-238">將保留原則套用到整個組織或特定位置</span><span class="sxs-lookup"><span data-stu-id="0e9b1-238">Applying a retention policy to an entire organization or specific locations</span></span>

<span data-ttu-id="0e9b1-239">您可以輕鬆地將保留原則套用到整個組織、整個位置，或只套用到特定位置或使用者。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-239">You can easily apply a retention policy to an entire organization, entire locations, or only to specific locations or users.</span></span>
  
### <a name="org-wide-policy"></a><span data-ttu-id="0e9b1-240">全組織原則</span><span class="sxs-lookup"><span data-stu-id="0e9b1-240">Org-wide policy</span></span>

<span data-ttu-id="0e9b1-241">保留原則的最強大功能之一，就是它會根據預設套用至 Office 365 中的各個位置，包括：</span><span class="sxs-lookup"><span data-stu-id="0e9b1-241">One of the most powerful features of a retention policy is that by default it applies to locations across Office 365, including:</span></span>
  
- <span data-ttu-id="0e9b1-242">Exchange 電子郵件</span><span class="sxs-lookup"><span data-stu-id="0e9b1-242">Exchange email</span></span>
    
- <span data-ttu-id="0e9b1-243">SharePoint 網站</span><span class="sxs-lookup"><span data-stu-id="0e9b1-243">SharePoint sites</span></span>
    
- <span data-ttu-id="0e9b1-244">OneDrive 帳戶</span><span class="sxs-lookup"><span data-stu-id="0e9b1-244">OneDrive for Business accounts</span></span>
    
- <span data-ttu-id="0e9b1-p135">Office 365 群組 (套用到群組的信箱、網站和文件中的內容。即將推出對 Planner、Yammer 和 CRM 中內容的支援。)</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p135">Office 365 groups (applies to content in the group's mailbox, site, and documents. Support for content in Planner, Yammer, and CRM is coming soon.)</span></span>
    
- <span data-ttu-id="0e9b1-247">Exchange 公用資料夾</span><span class="sxs-lookup"><span data-stu-id="0e9b1-247">Exchange public folders</span></span>
    
![所有位置選項](media/c343bd8e-42ac-4f17-a338-36f3c9598a86.png)
  
<span data-ttu-id="0e9b1-249">全組織保留原則的其他重要功能包含：</span><span class="sxs-lookup"><span data-stu-id="0e9b1-249">Other important features of an org-wide retention policy include:</span></span>
  
- <span data-ttu-id="0e9b1-250">原則可以包含的信箱或網站數目沒有任何限制。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-250">There is no limit to the number of mailboxes or sites the policy can include.</span></span>
    
- <span data-ttu-id="0e9b1-251">對於 Exchange，在套用原則後建立的任何新信箱都會自動繼承此原則。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-251">For Exchange, any new mailbox created after the policy is applied will automatically inherit the policy.</span></span>
    
<span data-ttu-id="0e9b1-252">不過，每個租用戶最多可有 10 個組合的全組織原則和整個位置原則 (請參閱下一節)。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-252">However, there is a limit of 10 org-wide policies and entire-location policies combined (see next section) per tenant.</span></span>
  
### <a name="a-policy-that-applies-to-entire-locations"></a><span data-ttu-id="0e9b1-253">套用到整個組織的原則</span><span class="sxs-lookup"><span data-stu-id="0e9b1-253">A policy that applies to entire locations</span></span>

<span data-ttu-id="0e9b1-p136">當選擇位置時，您可以輕鬆地包含或排除整個位置，例如 Exchange 電子郵件或 OneDrive 帳戶。若要這麼做，只需將該位置的 [狀態]**** 切換為開啟或關閉。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p136">When you choose locations, you can easily include or exclude an entire location, such as Exchange email or OneDrive accounts. To do so, simply toggle the **Status** of that location on or off.</span></span> 
  
<span data-ttu-id="0e9b1-p137">如同全組織原則一般，若原則套用到整個位置的任何組合，則原則可以包含的信箱或網站數目沒有限制。例如，如果原則包含所有 Exchange 電子郵件和所有 SharePoint 網站，則所有網站和信箱都會包含在內，無論有多少。對於 Exchange，套用原則後建立的任何新信箱都會自動繼承此原則。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p137">Like an org-wide policy, if a policy applies to any combination of entire locations, there is no limit to the number of mailboxes or sites the policy can include. For example, if a policy includes all Exchange email and all SharePoint sites, all sites and mailboxes will be included, no matter how many. And for Exchange, any new mailbox created after the policy is applied will automatically inherit the policy.</span></span>
  
<span data-ttu-id="0e9b1-259">不過，每個租用戶最多可有 10 個組合的全組織原則和整個位置原則。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-259">However, there is a limit of 10 org-wide policies and entire-location policies combined per tenant.</span></span>
  
![選擇位置頁面](media/6ac0c2d6-1abf-4690-b3f6-9ca506887ba3.png)
  
### <a name="a-policy-with-specific-inclusions-or-exclusions"></a><span data-ttu-id="0e9b1-261">具有特定包含或排除的原則</span><span class="sxs-lookup"><span data-stu-id="0e9b1-261">A policy with specific inclusions or exclusions</span></span>

<span data-ttu-id="0e9b1-p138">您也可以將保留原則套用至特定使用者。若要這麼做，請將該位置的 [狀態]**** 切換為開啟，然後使用連結來包含或排除特定使用者、Office 365 群組或位置。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p138">You can also apply a retention policy to specific users. To do so, toggle the **Status** of that location on, and then use the links to include or exclude specific users, Office 365 groups, or locations.</span></span> 
  
<span data-ttu-id="0e9b1-264">不過請注意，包含或排除超過 1000 個特定使用者的保留原則有下列限制：</span><span class="sxs-lookup"><span data-stu-id="0e9b1-264">However, note that the following limits exist for a retention policy that includes or excludes over 1,000 specific users:</span></span>
  
- <span data-ttu-id="0e9b1-265">這類保留原則最多可包含 1,000 個信箱和 100 個網站。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-265">A preservation policy can contain no more than 10,000 mailboxes and 100 sites.</span></span>
    
- <span data-ttu-id="0e9b1-266">一個租用戶最多可包含 1,000 個這類保留原則。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-266">A tenant can contain no more than 1,000 preservation policies.</span></span>
    
<span data-ttu-id="0e9b1-267">雖然有這些限制，但請了解您可以套用全組織原則或套用到整個位置的原則來超過這些限制。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-267">Although these limits exist, understand that you can get over these limits by applying either an org-wide policy or a policy that applies to entire locations.</span></span>
  
### <a name="skype-locations"></a><span data-ttu-id="0e9b1-268">Skype 位置</span><span class="sxs-lookup"><span data-stu-id="0e9b1-268">Skype locations</span></span>

<span data-ttu-id="0e9b1-269">不同於 Exchange 電子郵件，您無法僅將 Skype 位置的狀態切換為開啟，即可包含所有使用者，但您可以開啟該位置，然後手動選擇您想要保留其交談的使用者。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-269">Unlike Exchange email, you can't simply toggle the status of the Skype location on to include all users, but you can turn on that location and then manually choose the users whose conversations you want to retain.</span></span>
  
<span data-ttu-id="0e9b1-p139">選擇商務用 Skype 使用者時，您可以選取直欄標題中的 [名稱]**** 方塊，來快速地包含所有使用者 - 不過，請務必了解每個使用者在原則中都會算成特定包含。因此，如果包含超過 1,000 個使用者，則會套用上一節中提到的限制。在這裡選取所有 Skype 使用者，不等同於根據預設全組織原則能夠包含所有 Skype 使用者。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p139">When you choose Skype for Business users, you can quickly include all users by selecting the **Name** box in the column header - however, it's important to understand that each user counts as a specific inclusion in the policy. Therefore, if you include over 1,000 users, the limits noted in the previous section apply. Selecting all Skype users here is not the same as if an org-wide policy were able to include all Skype users by default.</span></span> 
  
![選擇 Skype 使用者頁面](media/f1742493-741a-4142-a564-d7d41ab0236a.png)
  
<span data-ttu-id="0e9b1-p140">請注意，**交談歷程記錄** (Outlook 中的資料夾) 是與 Skype 封存無關的功能。使用者可以關閉**交談歷程記錄**，但會執行 Skype 的封存，方法為將 Skype 交談的複本儲存在使用者無法存取但 eDiscovery 可以使用的隱藏資料夾中。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p140">Note that **Conversation History**, a folder in Outlook, is a feature that has nothing to do with Skype archiving. **Conversation History** can be turned off by the end user, but archiving for Skype is done by storing a copy of Skype conversations in a hidden folder that is inaccessible to the user but available to eDiscovery.</span></span> 
  
### <a name="teams-locations"></a><span data-ttu-id="0e9b1-276">Teams 位置</span><span class="sxs-lookup"><span data-stu-id="0e9b1-276">Teams locations</span></span>

<span data-ttu-id="0e9b1-p141">您可以使用保留原則來保留 Teams 中的聊天和通道訊息。Teams 聊天儲存在涉及聊天的每個使用者之信箱的隱藏資料夾中，而 Teams 通道訊息則儲存在團隊的群組信箱中類似的隱藏資料夾中。不過，請務必了解 Teams 會使用 Azure 提供的聊天服務，其中也會儲存此資料，而且根據預設這項服務會永遠儲存該資料。基於這個原因，我們強烈建議您使用 Teams 位置來保留和刪除 Teams 資料。使用 Teams 位置會同時從 Exchange 信箱和基礎 Azure 提供的聊天服務中永久刪除資料。如需詳細資訊，請參閱 [Microsoft Teams 中的安全性及合規性概觀](https://go.microsoft.com/fwlink/?linkid=871258) (英文)。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p141">You can use a retention policy to retain chats and channel messages in Teams. Teams chats are stored in a hidden folder in the mailbox of each user included in the chat, and Teams channel messages are stored in a similar hidden folder in the group mailbox for the team. However, it's important to understand that Teams uses an Azure-powered chat service that also stores this data, and by default this service stores the data forever. For this reason, we strongly recommend that you use the Teams location to retain and delete Teams data. Using the Teams location will permanently delete data from both the Exchange mailboxes and the underlying Azure-powered chat service. For more information, see [Overview of security and compliance in Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=871258).</span></span>
  
<span data-ttu-id="0e9b1-p142">請注意，套用到 Exchange 或 Office 365 群組位置中使用者或群組信箱的保留原則不會影響 Teams 聊天和頻道訊息。即使 Teams 聊天和通道訊息儲存在 Exchange 中，它們也只會受到套用至 Teams 位置的保留原則影響。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p142">Note that Teams chats and channel messages are not affected by retention policies applied to user or group mailboxes in the Exchange or Office 365 groups locations. Even though Teams chats and channel messages are stored in Exchange, they're affected only by a retention policy that's applied to the Teams location.</span></span>
  
<span data-ttu-id="0e9b1-p143">我們仍在致力於 Teams 中的保留，而且即將推出額外的功能。與此同時，以下是需要注意的一些限制：</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p143">We're still working on retention in Teams, and additional features are coming. In the meantime, here are a few limitations to be aware of:</span></span>
  
- <span data-ttu-id="0e9b1-p144">**Teams 需要個別的保留原則** 當您建立保留原則，並在 Teams 位置上切換為開啟時，所有其他位置都會切換為關閉。包含 Teams 的保留原則只能包含 Teams，不得包含其他位置。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p144">**Teams require a separate retention policy** When you create a retention policy and toggle on the Teams location, all other locations toggle off. A retention policy that includes Teams can include only Teams and no other locations.</span></span> 
    
- <span data-ttu-id="0e9b1-289">**Teams 不包含在全組織原則中** 如果建立全組織原則，則不會包含 Teams，因為它們需要個別的保留原則。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-289">**Teams are not included in an org-wide policy** If you create an org-wide policy, Teams are not included because they require a separate retention policy.</span></span> 
    
- <span data-ttu-id="0e9b1-p145">**Teams 不支援進階保留** 當建立保留原則時，如果您選擇[只將原則套用到符合某些條件之內容進階設定](retention-policies.md#advanced)，則無法使用 Teams 位置。此時，Teams 中的保留適用於所有聊天和通道訊息內容。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p145">**Teams doesn't support advanced retention** When you create a retention policy, if you choose the [Advanced settings that apply a policy only to content that meets certain conditions](retention-policies.md#advanced), the Teams location is not available. At this time, retention in Teams applies to all of the chat and channel message content.</span></span>
    
- <span data-ttu-id="0e9b1-p146">**只能刪除至少保留 30 天的 Teams 內容** 目前不支援建立一個原則來刪除保留不到 30 天的 Teams 內容。如果想要將此原則套用至 Teams 內容，請指定等於或大於 30 天的保留期間。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p146">**Teams content must be at least 30 days old to be deleted** At this time, creating a policy to delete Teams content that's less than 30 days old is not supported. If you want this policy to apply to Teams content, specify a retention period that's equal to or greater than 30 days.</span></span> 
    
- <span data-ttu-id="0e9b1-p147">**Teams 最多可能需要 30 天來清除保留的內容** 套用至 Teams 的保留原則將刪除所有相關儲存位置中的內容。不過，一經啟動之後，Teams 用戶端可能就需要最多 30 天，根據保留原則清除內容。但是，即使內容仍會出現在 Teams 用戶端中，但在保留期間結束時，該內容不會出現在內容搜尋或 eDiscovery 中。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p147">**Teams may take up to 30 days to clean up retained content** A retention policy applied to Teams will delete the content from all relevant storage locations. However, immediately after launch, it may take up to 30 days for Teams clients to clean up content based on the retention policy. But even though content still appears in the Teams clients, that content will not appear in content search or eDiscovery after the end of the retention period.</span></span> 
    
<span data-ttu-id="0e9b1-p148">在 Team 中，聊天中共用的檔案儲存在共用檔案之使用者的 OneDrive 帳戶中。上傳至通道的檔案儲存在 Team 的 SharePoint 網站中。因此，若要保留或刪除 Team 中的檔案，您需要建立保留原則，套用至 SharePoint 和 OneDrive 位置。如果您想要將原則僅套用至特定團隊的檔案，則您可以選擇 Team 的 SharePoint 網站，以及 Team 中使用者的 OneDrive 帳戶。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p148">In a Team, files that are shared in chat are stored in the OneDrive account of the user who shared the file. Files that are uploaded into channels are stored in the SharePoint site for the Team. Therefore, to retain or delete files in a Team, you need to create a retention policy that applies to the SharePoint and OneDrive locations. If you want to apply a policy to the files of just a specific team, you can choose the SharePoint site for the Team and the OneDrive accounts of users in the Team.</span></span>
  
<span data-ttu-id="0e9b1-301">套用到 Teams 的保留原則可以使用[保留鎖定](retention-policies.md#locking)。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-301">A retention policy that applies to Teams can use [Preservation Lock](retention-policies.md#locking).</span></span>
  
![聊天和通道訊息的 Teams 位置](media/127345da-e802-4b3a-afc7-6e354dc3f409.png)
  
## <a name="excluding-specific-types-of-exchange-items-from-a-retention-policy"></a><span data-ttu-id="0e9b1-303">從保留原則中排除特定類型的 Exchange 項目</span><span class="sxs-lookup"><span data-stu-id="0e9b1-303">Excluding specific types of Exchange items from a retention policy</span></span>
<span data-ttu-id="0e9b1-p149">您可以使用 PowerShell，從保留原則中排除特定類型的 Exchange 項目。例如，您可以排除語音信箱訊息、 IM 交談，以及信箱中的其他 商務用 Skype Online 內容。您也可以排除行事曆、附註和工作項目。僅使用 PowerShell 才能提供此功能；建立保留原則時，無法在 UI 中提供它。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p149">By using PowerShell, you can exclude specific types of Exchange items from a retention policy. For example, you can exclude voicemail messages, IM conversations, and other Skype for Business Online content in mailboxes. You can also exclude calendar, note, and task items. This capability is available only by using PowerShell; it's not available in the UI when you create a retention policy.</span></span>
  
<span data-ttu-id="0e9b1-p150">若要這麼做，請使用 `New-RetentionComplianceRule` 和 `Set-RetentionComplianceRule` Cmdlet 中的 `ExcludedItemClasses` 參數。如需 PowerShell 的詳細資訊，請參閱下節[尋找保留原則的 PowerShell Cmdlet](retention-policies.md#powershell)。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p150">To do this, use the  `ExcludedItemClasses` parameter of the  `New-RetentionComplianceRule` and  `Set-RetentionComplianceRule` cmdlets. For more information about PowerShell, see the below section [Find the PowerShell cmdlets for retention policies](retention-policies.md#powershell).</span></span>
  
## <a name="locking-a-retention-policy"></a><span data-ttu-id="0e9b1-310">鎖定保留原則</span><span class="sxs-lookup"><span data-stu-id="0e9b1-310">Locking a preservation policy</span></span>
<span data-ttu-id="0e9b1-p151">有些組織可能需要遵守由監管機構定義的法規，例如證券交易委員會 (SEC) 法規 17a-4，要求在保留原則開啟之後，不能關閉或執行較不嚴格的限制。使用「保留鎖定」，您可以鎖定原則，讓任何人 (包括系統管理員) 均無法關閉原則或執行較不嚴格的限制。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p151">Some organizations may need to comply with rules defined by regulatory bodies such as the Securities and Exchange Commission (SEC) Rule 17a-4, which requires that after a preservation policy is turned on, it cannot be turned off or made less restrictive. With Preservation Lock, you can lock the policy so that no one -- including the administrator -- can turn off the policy or make it less restrictive.</span></span>
  
<span data-ttu-id="0e9b1-p152">鎖定原則之後，任何人均無法關閉它，或從原則中移除位置。也不能修改或刪除在保留期間受限於原則的內容。鎖定原則之後，修改保留原則的唯一方式是藉由在其中新增位置，或延長其持續時間。鎖定的原則可以增加或擴充，但是無法減少或關閉。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p152">After a policy’s been locked, no one -- including the administrator -- can turn off, disable, or remove content from the policy. And it’s not possible to modify or delete content that’s subject to the policy during the preservation period. After the policy’s been locked, the only ways you can modify the preservation policy are by adding content to it or extending its duration. A locked policy can be increased or extended, but it can’t be reduced, disabled, or turned off.</span></span>
  
<span data-ttu-id="0e9b1-317">因此，在您鎖定保留原則之前，**務必**了解您組織的法規需求，並且**不要鎖定原則**，除非您確定它是您需要的原則。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-317">Therefore, before you lock a preservation policy, it’s critical that you understand your organization’s compliance requirements, and that you do not lock a policy until you are certain that it’s what you need.</span></span>
  
<span data-ttu-id="0e9b1-p153">您只能使用 PowerShell 來鎖定保留原則。請使用 `New-RetentionCompliancePolicy` 或 `Set-RetentionCompliancePolicy` Cmdlet 中的 `RestrictiveRetention` 參數。如需 PowerShell 的詳細資訊，請參閱下節[尋找保留原則的 PowerShell Cmdlet](retention-policies.md#powershell)。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p153">You can lock a retention policy only by using PowerShell. Use the  `RestrictiveRetention` parameter of the  `New-RetentionCompliancePolicy` or  `Set-RetentionCompliancePolicy` cmdlet. For more information about PowerShell, see the below section [Find the PowerShell cmdlets for retention policies](retention-policies.md#powershell).</span></span>
  
## <a name="the-principles-of-retention-or-what-takes-precedence"></a><span data-ttu-id="0e9b1-321">原則保留，哪一個優先？</span><span class="sxs-lookup"><span data-stu-id="0e9b1-321">The principles of retention, or what takes precedence?</span></span>

<span data-ttu-id="0e9b1-p154">很有可能內容會套用多個保留原則，這些原則各有不同的動作 (保留、刪除或兩者) 和保留期間。哪一個優先？請放心，最低限度，由一個原則保留的內容不會被另一個原則永久刪除。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p154">It's possible or even likely that content might have several retention policies applied to it, each with a different action (retain, delete, or both) and retention period. What takes precedence? At the highest level, rest assured that content being retained by one policy can't be permanently deleted by another policy.</span></span>
  
![原則保留圖](media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
<span data-ttu-id="0e9b1-326">若要了解不同的保留原則如何套用至內容，請記住以下保留原則：</span><span class="sxs-lookup"><span data-stu-id="0e9b1-326">To understand how different retention policies are applied to content, keep these principles of retention in mind:</span></span>
  
1. <span data-ttu-id="0e9b1-p155">**保留優先於刪除。** 假設一個保留原則要在 3 年後刪除 Exchange 電子郵件，但另一個保留原則要保留 Exchange 電子郵件 5 年再刪除。任何達到 3 年的內容會遭到刪除，在使用者檢視中看不到它們，但仍會保留在 [可復原的項目] 資料夾，直到內容達到 5 年，便會永久刪除。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p155">**Retention wins over deletion.** Suppose that one retention policy says to delete Exchange email after three years, but another retention policy says to retain Exchange email for five years and then delete it. Any content that reaches three years old will be deleted and hidden from the users' view, but still retained in the Recoverable Items folder until the content reaches five years old, when it will be permanently deleted.</span></span> 
    
2. <span data-ttu-id="0e9b1-p156">**最長保留期間優先。** 如果內容套用多個保留內容的原則，則會一直保留到最長保留期間結束為止。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p156">**The longest retention period wins.** If content's subject to multiple policies that retain content, it will be retained until the end of the longest retention period.</span></span> 
    
3. <span data-ttu-id="0e9b1-p157">**明確包含優先於隱含包含。** 意思是：</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p157">**Explicit inclusion wins over implicit inclusion.** This means:</span></span> 
    
    1. <span data-ttu-id="0e9b1-p158">如果包含保留設定的標籤是由使用者手動指派給項目 (例如 Exchange 電子郵件或 OneDrive 文件)，則此標籤優先於在網站或信箱層級指派的原則，並優先於文件庫指派的預設標籤。例如，如果明確標籤要保留 10 年，但指派給網站的原則只要保留 5 年，則標籤優先。請注意，自動套用的標籤會被視為隱含而不是明確，因為它們是由 Office 365 自動套用。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p158">If a label with retention settings is manually assigned by a user to an item, such as an Exchange email or OneDrive document, that label takes precedence over both a policy assigned at the site or mailbox level and a default label assigned by the document library. For example, if the explicit label says to retain for ten years, but the policy assigned to the site says to retain for only five years, the label takes precedence. Note that auto-apply labels are considered implicit, not explicit, because they're applied automatically by Office 365.</span></span>
    
    2. <span data-ttu-id="0e9b1-337">如果保留原則包含特定位置 (例如特定使用者的信箱或商務用 OneDrive 帳戶)，則此原則優先於其他套用至所有使用者信箱或商務用 OneDrive 帳戶但未特地包含該使用者信箱的保留原則。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-337">If a retention policy includes a specific location, such as a specific user's mailbox or OneDrive for Business account, that policy takes precedence over another retention policy that applies to all users' mailboxes or OneDrive for Business accounts but doesn't specifically include that user's mailbox.</span></span>
    
4. <span data-ttu-id="0e9b1-p159">**最短刪除期間優先。** 同樣地，如果內容套用多個刪除內容的原則 (無保留)，則會在最短保留期間結束時刪除。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p159">**The shortest deletion period wins.** Similarly, if content's subject to multiple policies that delete content (with no retention), it will be deleted at the end of the shortest retention period.</span></span> 
    
<span data-ttu-id="0e9b1-340">了解保留原則從上到下的仲裁流程：如果所有原則或標籤套用的規則都在同一個層級，則流程會移到下一個層級來決定套用規則的優先順序。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-340">Understand that the principles of retention work as a tie-breaking flow from top to bottom: If the rules applied by all policies or labels are the same at one level, the flow moves down to the next level to determine precedence for which rule is applied.</span></span>
  
<span data-ttu-id="0e9b1-p160">最後，保留原則或標籤無法永久刪除 eDiscovery 保留的任何內容。保留解除時，這些內容便再度符合上述的清理程序。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p160">Finally, a retention policy or label cannot permanently delete any content that's on hold for eDiscovery. When the hold is released, the content again becomes eligible for the cleanup process described above.</span></span>
  
## <a name="use-a-retention-policy-instead-of-these-features"></a><span data-ttu-id="0e9b1-343">使用保留原則，而不是這些功能</span><span class="sxs-lookup"><span data-stu-id="0e9b1-343">Use a retention policy instead of these features</span></span>

<span data-ttu-id="0e9b1-p161">單一保留原則可以輕鬆地套用到 Office 365 中的整個組織和位置，包括 Exchange Online、SharePoint Online、商務用 OneDrive 和 Office 365 群組。如果您需要保留或刪除 Office 365 中任何位置的內容，則我們建議您使用保留原則。(您也可以使用標籤與保留設定搭配 - 如需詳細資訊，請參閱[標籤概觀](labels.md) (英文)。)</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p161">A single retention policy can easily apply to an entire organization and locations across Office 365, including Exchange Online, SharePoint Online, OneDrive for Business, and Office 365 groups. If you need to retain or delete content anywhere in Office 365, we recommend that you use a retention policy. (You can also use labels with retention settings - for more information, see [Overview of labels](labels.md).)</span></span>
  
<span data-ttu-id="0e9b1-p162">有數個其他功能，先前用來保留或刪除 Office 365 中的內容。列示於下。這些功能將繼續並排使用在安全性與合規性中心建立的保留原則和標籤。但繼續進行時，如需控管資料，我們建議您使用保留原則或標籤，而不是所有這些功能。保留原則是可以同時在 Office 365 保留和刪除資料的唯一功能。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p162">There are several other features that have previously been used to retain or delete content in Office 365. These are listed below. These features will continue to work side by side with retention policies and labels created in the Security &amp; Compliance Center. But moving forward, for data governance, we recommend that you use a retention policy or labels instead of all of these features. A retention policy is the only feature that can both retain and delete content across Office 365.</span></span>
  
### <a name="exchange-online"></a><span data-ttu-id="0e9b1-352">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0e9b1-352">Exchange Online</span></span>

- <span data-ttu-id="0e9b1-353">[管理 Office 365 安全性與合規性中心的 eDiscovery 案例](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da) (機器翻譯) (eDiscovery 保留)</span><span class="sxs-lookup"><span data-stu-id="0e9b1-353">Manage eDiscovery cases in the Office 365 Security & Compliance Center</span></span> 
    
- <span data-ttu-id="0e9b1-354">[就地保留與訴訟暫止](https://go.microsoft.com/fwlink/?linkid=846124) (機器翻譯) (eDiscovery 保留)</span><span class="sxs-lookup"><span data-stu-id="0e9b1-354">[In-Place Hold and Litigation Hold](https://go.microsoft.com/fwlink/?linkid=846124)</span></span> 
    
- <span data-ttu-id="0e9b1-355">[保留標記和保留原則](https://go.microsoft.com/fwlink/?linkid=846125) (機器翻譯)，又稱為[郵件記錄管理 (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (機器翻譯) (僅限刪除)</span><span class="sxs-lookup"><span data-stu-id="0e9b1-355">[Retention tags and retention policies](https://go.microsoft.com/fwlink/?linkid=846125), also known as [messaging records management (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (Deletion only)</span></span> 
    
### <a name="sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="0e9b1-356">SharePoint Online 和商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="0e9b1-356">SharePoint Online and OneDrive for Business</span></span>

- <span data-ttu-id="0e9b1-357">[管理 Office 365 安全性與合規性中心的 eDiscovery 案例](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da) (機器翻譯) (eDiscovery 保留)</span><span class="sxs-lookup"><span data-stu-id="0e9b1-357">Manage eDiscovery cases in the Office 365 Security & Compliance Center</span></span> 
    
- <span data-ttu-id="0e9b1-358">[在 eDiscovery 中心將內容新增至案例及保留來源](https://support.office.com/article/54d70de9-1ec2-4325-84f3-aeb588554479) (機器翻譯) (eDiscovery 保留)</span><span class="sxs-lookup"><span data-stu-id="0e9b1-358">[Add content to a case and place sources on hold in the eDiscovery Center](https://support.office.com/article/54d70de9-1ec2-4325-84f3-aeb588554479)</span></span> 
    
- <span data-ttu-id="0e9b1-359">[文件刪除原則的概觀](https://support.office.com/article/55e8d858-f278-482b-a198-2e62d6a2e6e5) (僅限刪除)</span><span class="sxs-lookup"><span data-stu-id="0e9b1-359">Overview of document deletion policies</span></span> 
    
- <span data-ttu-id="0e9b1-360">[設定就地記錄管理](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (保留)</span><span class="sxs-lookup"><span data-stu-id="0e9b1-360">[Configuring in place records management](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (Retention)</span></span> 
    
- <span data-ttu-id="0e9b1-361">[網站關閉及刪除的使用原則](https://support.office.com/article/a8280d82-27fd-48c5-9adf-8a5431208ba5) (僅限刪除)</span><span class="sxs-lookup"><span data-stu-id="0e9b1-361">[Use policies for site closure and deletion](https://support.office.com/article/a8280d82-27fd-48c5-9adf-8a5431208ba5) (Deletion only)</span></span> 
    
- <span data-ttu-id="0e9b1-362">[資料管理原則](intro-to-info-mgmt-policies.md) (機器翻譯) (僅限刪除)</span><span class="sxs-lookup"><span data-stu-id="0e9b1-362">[Information management policies](intro-to-info-mgmt-policies.md) (Deletion only)</span></span> 
    
<span data-ttu-id="0e9b1-p163">請注意，如果您先前為了控管資料而使用任何 eDiscovery 保留，則應該對主動合規性改用保留原則。您應該只對 eDiscovery 使用在安全性與合規性中心建立的保留。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p163">Note that if you've previously used any of the eDiscovery holds for the purpose of data governance, you should instead use a retention policy for proactive compliance. You should use a hold created in the Security &amp; Compliance Center only for eDiscovery.</span></span>
  
### <a name="retention-policies-override-information-management-policies"></a><span data-ttu-id="0e9b1-365">保留原則會覆寫資訊管理原則</span><span class="sxs-lookup"><span data-stu-id="0e9b1-365">Retention policies override information management policies</span></span>

<span data-ttu-id="0e9b1-p164">在 SharePoint 網站中，您可以使用[資訊管理原則](intro-to-info-mgmt-policies.md)来保留內容。如果您將在安全性與合規性中心建立的保留原則套用至已對清單或文件庫使用內容類型原則或資訊管理原則的網站，則在保留原則生效時，會忽略這些原則。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p164">In SharePoint sites, you may be using [information management policies](intro-to-info-mgmt-policies.md) to retain content. If you apply a retention policy created in the Security and Compliance Center to a site that already uses content type policies or information management policies for a list or library, those policies are ignored while the retention policy is in effect.</span></span> 
  
## <a name="what-happened-to-preservation-policies"></a><span data-ttu-id="0e9b1-368">保留原則發生了什麼情況？</span><span class="sxs-lookup"><span data-stu-id="0e9b1-368">What happened to preservation policies?</span></span>

<span data-ttu-id="0e9b1-p165">如果您是使用保留原則，則該原則會自動轉換為只使用保留動作的保留原則 - 此原則並不會刪除內容。保留原則會繼續運作，並保留您的內容，而不需要您進行任何變更。您可以在安全性與合規性中心的 [保留]**** 頁面中找到這些原則。您可以編輯保留原則來變更保留期間，但無法進行其他變更，例如新增或移除位置。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p165">If you were using a preservation policy, that policy has been automatically converted to a retention policy that uses only the retain action - the policy won't delete content. The preservation policy will continue to work and preserve your content without requiring any changes from you. You can find these policies on the **Retention** page in the Security &amp; Compliance Center. You can edit a preservation policy to change the retention period, but you can't make other changes, such as adding or removing locations.</span></span> 
  
## <a name="permissions"></a><span data-ttu-id="0e9b1-373">權限</span><span class="sxs-lookup"><span data-stu-id="0e9b1-373">Permissions</span></span>

<span data-ttu-id="0e9b1-p166">您的合規性小組中將建立保留原則的成員必須具備安全性與合規性中心的權限。根據預設，租用戶管理員將可存取此位置，並且可直接讓法務人員與其他人存取安全性與合規性中心，而不需要為其提供租用戶管理員的所有權限。若要這麼做，我們建議您：移至安全性與合規性中心的 [權限]**** 頁面，編輯 [合規性管理員]**** 角色群組，將該成員加入此角色群組。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p166">Members of your compliance team who will create retention policies need permissions to the Security &amp; Compliance Center. By default, your tenant admin will have access to this location and can give compliance officers and other people access to the Security &amp; Compliance Center, without giving them all of the permissions of a tenant admin. To do this, we recommend that you go to the **Permissions** page of the Security &amp; Compliance Center, edit the **Compliance Administrator** role group, and add members to that role group.</span></span> 
  
<span data-ttu-id="0e9b1-376">如需詳細資訊，請參閱[讓使用者能夠存取 Office 365 安全性與合規性中心](grant-access-to-the-security-and-compliance-center.md) (機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-376">See [Give users access to the Office 365 Security &amp; Compliance Center](grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="0e9b1-p167">需要這些權限才能建立及套用保留原則。原則強制執行不需要內容的存取權。</span><span class="sxs-lookup"><span data-stu-id="0e9b1-p167">These permissions are required only to create and apply a DLP policy. Policy enforcement does not require access to the content.</span></span>
  
## <a name="find-the-powershell-cmdlets-for-retention-policies"></a><span data-ttu-id="0e9b1-379">尋找保留原則的 PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="0e9b1-379">Find the PowerShell cmdlets for retention policies</span></span>

<span data-ttu-id="0e9b1-380">若要使用保留原則 Cmdlet，您需要：</span><span class="sxs-lookup"><span data-stu-id="0e9b1-380">To use the retention policy cmdlets, you need to:</span></span>
  
1. <span data-ttu-id="0e9b1-381">[使用遠端 PowerShell 連線到 Office 365 安全性與合規性中心](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="0e9b1-381">For connection instructions for Security  Compliance Center PowerShell, click [Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409).</span></span>
    
2. <span data-ttu-id="0e9b1-382">使用這些 [Office 365 安全性與合規性中心 Cmdlet](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="0e9b1-382">Use these [Office 365 Security &amp; Compliance Center cmdlets](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)</span></span>
    
## <a name="more-information"></a><span data-ttu-id="0e9b1-383">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="0e9b1-383">More information</span></span>

- <span data-ttu-id="0e9b1-384">[標籤概觀](labels.md) (英文)</span><span class="sxs-lookup"><span data-stu-id="0e9b1-384">[Overview of labels](labels.md)</span></span>
    
