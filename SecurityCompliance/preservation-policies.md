---
title: 保留原則的概觀
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 4/3/2017
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid: MET150
ms.assetid: 9c3b1d52-40ce-4ba3-a520-9ae0be15538a
description: 遵守產業規定或內部原則、 組織想要的特定期間內保留內容。與 Office 365 中的保留原則，您可以保留網站、 信箱及公用資料夾的內容無限期或特定持續時間。您也可以篩選將會保留所提供的關鍵字或日期範圍，縮減結果的內容。
ms.openlocfilehash: a26b85a563dd0e6f9ed8a70bfe9a310fc89a50f2
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272458"
---
# <a name="overview-of-preservation-policies"></a><span data-ttu-id="c59eb-105">保留原則的概觀</span><span class="sxs-lookup"><span data-stu-id="c59eb-105">Overview of preservation policies</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c59eb-p102">如果您已使用保留原則，該原則已經自動轉換成是沒有進行之所有事項的保留原則的新功能的保留原則 」 等等。保留原則會繼續運作，並保留您的內容而不需要從您的任何變更。您可以在 [**保留**] 頁面上找到這些原則安全性&amp;規範中心。如需詳細資訊，請參閱[保留原則有何吗？](retention-policies.md#what-happened-to-preservation-policies)</span><span class="sxs-lookup"><span data-stu-id="c59eb-p102">If you were using a preservation policy, that policy has been automatically converted to a retention policy, which is a new feature that does everything a preservation policy does and more. The preservation policy will continue to work and preserve your content without requiring any changes from you. You can find these policies on the **Retention** page in the Security &amp; Compliance Center. For more information, see [What happened to preservation policies?](retention-policies.md#what-happened-to-preservation-policies)</span></span>
  
<span data-ttu-id="c59eb-p103">遵守產業規定或內部原則、 組織想要的特定期間內保留內容。與 Office 365 中的保留原則，您可以保留網站、 信箱及公用資料夾的內容無限期或特定持續時間。您也可以篩選將會保留所提供的關鍵字或日期範圍，縮減結果的內容。</span><span class="sxs-lookup"><span data-stu-id="c59eb-p103">To comply with industry regulations or internal policies, organizations want to preserve content for a certain period of time. With a preservation policy in Office 365, you can preserve content in sites, mailboxes, and public folders indefinitely or for a specific duration. You can also filter the content that will be preserved by supplying keywords or a date range to narrow the results.</span></span>
  
<span data-ttu-id="c59eb-113">例如，您可以保留特定信箱的七個 years、 屬於 「 業務 」 部門的網站中的內容及進一步縮小說出您想要保留的最後兩個年度只包含特定內容的 [原則範圍用戶端之間的名稱。</span><span class="sxs-lookup"><span data-stu-id="c59eb-113">For example, you can preserve the content in specific mailboxes and sites belonging to the Sales Department for seven years, and further narrow the scope of the policy by saying that you want to preserve only content from the last two years that contains a specific client's name.</span></span>
  
<span data-ttu-id="c59eb-p104">受限於保留原則的內容時，人員可以繼續編輯和好像 nothing 變更的內容保留在其原始位置中的位置，因為搭配內容。但如果有人編輯或刪除受限於原則的內容，它保留原則處於作用中時在安全的位置來儲存複本。</span><span class="sxs-lookup"><span data-stu-id="c59eb-p104">When content is subject to a preservation policy, people can continue to edit and work with the content as if nothing's changed because the content's preserved in place, in its original location. But if someone edits or deletes content that's subject to the policy, a copy is saved to a secure location where it's preserved while the policy is in effect.</span></span>
  
<span data-ttu-id="c59eb-p105">最後，有些組織可能需要遵守如美國證券業 and Exchange 委員會 （秒） 規則條例 17a-4，需要的保留原則會在開啟之後，它無法關閉或進行限制較少的法規本文所定義的規則。若要符合下列需求，您可以使用保留鎖定。原則的鎖定之後，沒有人 — 包括系統管理員 — 可以關閉原則或進行限制較少。</span><span class="sxs-lookup"><span data-stu-id="c59eb-p105">Finally, some organizations may need to comply with rules defined by regulatory bodies such as the Securities and Exchange Commission (SEC) Rule 17a-4, which requires that after a preservation policy is turned on, it cannot be turned off or made less restrictive. To meet this requirement, you can use Preservation Lock. After a policy's been locked, no one—including the administrator—can turn off the policy or make it less restrictive.</span></span>
  
<span data-ttu-id="c59eb-119">建立及管理 Office 365 安全性 [保留] 頁面上的保留原則&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="c59eb-119">You create and manage preservation policies on the Retention page in the Office 365 Security &amp; Compliance Center.</span></span>
  
![保留] 頁面上的 Office 365 安全性&amp;規範中心](media/edb2e228-efff-4619-89d1-8665b5f38639.png)
  
> [!NOTE]
> <span data-ttu-id="c59eb-p106">保留原則中包括 Exchange Online 信箱，信箱必須指派 Exchange Online 計劃 2 授權。如果信箱指派 Exchange Online 計劃 1 授權，您必須將其指派要包含在保留原則中的不同 Exchange Online 封存授權。</span><span class="sxs-lookup"><span data-stu-id="c59eb-p106">To include an Exchange Online mailbox in a preservation policy, the mailbox must be assigned an Exchange Online Plan 2 license. If a mailbox is assigned an Exchange Online Plan 1 license, you would have to assign it a separate Exchange Online Archiving license to include it in a preservation policy.</span></span> 
  
## <a name="how-a-preservation-policy-works-with-content-in-place"></a><span data-ttu-id="c59eb-123">保留原則對原有內容的運作方式</span><span class="sxs-lookup"><span data-stu-id="c59eb-123">How a preservation policy works with content in place</span></span>

<span data-ttu-id="c59eb-p107">當您納入網站、 信箱或公用資料夾的保留原則時、 內容仍會保留在其原始位置。人員可以繼續使用其文件或郵件，但它的內容複本存在於初始化原則時就能保存。網站、 內容的保留在保留保留文件庫 ；信箱及公用資料夾，內容的保留在 [可復原的項目] 資料夾中。這些安全的位置和保留的內容看不到大部分的人員。與保留原則、 人員即使不必知道其內容會受限於原則。</span><span class="sxs-lookup"><span data-stu-id="c59eb-p107">When you include a site, mailbox, or public folder in a preservation policy, the content remains in its original location. People can continue to work with their documents or mail, but a copy of the content as it existed when you initiated the policy is preserved. For sites, content's preserved in the Preservation Hold library; for mailboxes and public folders, content's preserved in the Recoverable Items folder. These secure locations and the preserved content are not visible to most people. With a preservation policy, people do not even need to know their content is subject to the policy.</span></span>
  
![圖表顯示保留原則的運作方式](media/2c1dd82b-84e0-49e0-ab46-d017df297040.png)
  
### <a name="site-content"></a><span data-ttu-id="c59eb-130">站台內容</span><span class="sxs-lookup"><span data-stu-id="c59eb-130">Site content</span></span>

<span data-ttu-id="c59eb-p108">保留原則套用之站台層級。當您在 [保留原則包含站台時，會建立保留保留文件庫，如果已不存在。因為只有網站集合擁有者可以看到大部分使用者無法檢視保留保留文件庫。</span><span class="sxs-lookup"><span data-stu-id="c59eb-p108">A preservation policy is applied at the level of a site. When you include a site in a preservation policy, a Preservation Hold library is created, if one doesn't already exist. Most users can't view the Preservation Hold library because it's visible only to site collection owners.</span></span>
  
<span data-ttu-id="c59eb-p109">如果使用者嘗試變更或刪除受限於保留原則的站台的內容，先將原則檢查之後所套用之原則的內容是否的已變更。如果這是第一次變更套用保留原則之後，原則將內容複製到保留保留文件庫，然後允許以變更或刪除原始內容的人員。請注意複製到保留保留文件庫的任何網站中的內容即使內容與保留原則所用的查詢篩選條件不符。</span><span class="sxs-lookup"><span data-stu-id="c59eb-p109">If a person attempts to change or delete content in a site that's subject to a preservation policy, first the policy checks whether the content's been changed since the policy was applied. If this is the first change since the preservation policy was applied, the policy copies the content to the Preservation Hold library, and then allows the person to change or delete the original content. Note that any content in the site can be copied to the Preservation Hold library, even if the content does not match the filter of the query used by the preservation policy.</span></span>
  
<span data-ttu-id="c59eb-p110">接著，計時器工作會清除文件保留庫。計時器工作會定期執行，並比較文件保留庫中的所有內容與站台的保留原則所使用的篩選器。除非內容至少符合一項篩選條件，否則計時器工作將從文件保留庫中永久刪除該內容。</span><span class="sxs-lookup"><span data-stu-id="c59eb-p110">Then a timer job cleans up the Preservation Hold library. The timer job runs periodically and compares all content in the Preservation Hold library to the filters used by the preservation policies on the site. Unless content matches at least one of the filters, the timer job permanently deletes the content from the Preservation Hold library.</span></span>
  
<span data-ttu-id="c59eb-p111">上一個適用於已存在時套用保留原則的內容。此外之後刪除, 則會保留任何建立或新增至網站後已包含在原則的新內容。不過，新的內容不被複製到保留保留文件庫中之第一個次加以編輯時，只有時將其刪除。若要保留的所有檔案的版本，您需要開啟版本設定，請參閱版本上的 [更新] 區段中。</span><span class="sxs-lookup"><span data-stu-id="c59eb-p111">The previous applies to content that exists when the preservation policy is applied. In addition, any new content that's created or added to the site after it was included in the policy will be preserved after deletion. However, new content isn't copied to the Preservation Hold library the first time it's edited, only when it's deleted. To preserve versions for all files, you need to turn on versioning—see the later section on versioning.</span></span>
  
### <a name="mailbox-and-public-folder-content"></a><span data-ttu-id="c59eb-144">信箱及公用資料夾伺服器</span><span class="sxs-lookup"><span data-stu-id="c59eb-144">Mailbox and public folder content</span></span>

<span data-ttu-id="c59eb-p112">對於使用者的信箱和其他項目，保留原則會在信箱層級套用。對於公用資料夾，保留原則會套用在資料夾層級套用，而不是信箱層級。信箱和公用資料夾都是使用 [可復原的項目] 資料夾來保留項目。已指派 eDiscovery 權限的人員可以檢視其他使用者的 [可復原的項目] 資料夾。 </span><span class="sxs-lookup"><span data-stu-id="c59eb-p112">For a user's mail and other items, a preservation policy is applied at the level of a mailbox. For a public folder, a preservation policy is applied at the folder level, not the mailbox level. Both a mailbox and a public folder use the Recoverable Items folder to preserve items. Only people that have been assigned eDiscovery permissions can view another user's Recoverable Items folder.</span></span> 
  
<span data-ttu-id="c59eb-p113">根據預設，人員從 [刪除的郵件] 資料夾中，以外的資料夾刪除郵件時將郵件移至刪除的項目] 資料夾。人員從 [刪除的郵件] 資料夾刪除項目、 時郵件移至 [可復原的項目] 資料夾，並從使用者的檢視就會消失。此外，人員軟可以刪除任何資料夾中，以略過已刪除的項目] 資料夾，並將項目放直接在 [可復原的項目] 資料夾中的項目 (SHIFT + DELETE)。</span><span class="sxs-lookup"><span data-stu-id="c59eb-p113">By default, when a person deletes a message from a folder other than the Deleted Items folder, the message is moved to the Deleted Items folder. When a person deletes an item from the Deleted Items folder, the message is moved to the Recoverable Items folder and disappears from the user's view. In addition, a person can soft delete an item (SHIFT+DELETE) in any folder, which bypasses the Deleted Items folder and places the item directly in the Recoverable Items folder.</span></span>
  
<span data-ttu-id="c59eb-p114">當信箱納入保留原則時，刪除的項目會移至 [可復原的項目] 資料夾中的 DiscoveryHold 資料夾。當信箱助理員定期處理信箱時，將會評估此資料夾中的郵件。除非內容至少符合一項保留原則所使用的篩選條件，否則信箱助理員將從 [可復原的項目] 資料夾中永久刪除該內容。</span><span class="sxs-lookup"><span data-stu-id="c59eb-p114">When a mailbox is included in a preservation policy, deleted items are moved to the DiscoveryHold folder inside the Recoverable Items folder. When the mailbox assistant periodically processes the mailbox, it evaluates messages in this folder. Unless content matches at least one of the filters used by a preservation policy, the mailbox assistant permanently deletes the content from the Recoverable Items folder.</span></span>
  
<span data-ttu-id="c59eb-p115">[可復原的項目] 資料夾也包含版本] 資料夾。當使用者嘗試變更特定內容的信箱項目 — 主旨，例如 body、 附件、 寄件者和收件者或傳送或接收郵件的日期-原始項目的複本儲存至版本資料夾，認可變更之前。發生的每個後續的變更。移除保留原則後，在 [版本] 資料夾中的副本所移除的信箱助理員。</span><span class="sxs-lookup"><span data-stu-id="c59eb-p115">The Recoverable Items folder also contains a Versions folder. When a person attempts to change certain properties of a mailbox item—such as the subject, body, attachments, senders and recipients, or date sent or received for a message—a copy of the original item is saved to the Versions folder before the change is committed. This happens for each subsequent change. After the preservation policy is removed, copies in the Versions folder are removed by the mailbox assistant.</span></span>
  
### <a name="where-a-preservation-policy-is-stored"></a><span data-ttu-id="c59eb-159">儲存保留原則的位置</span><span class="sxs-lookup"><span data-stu-id="c59eb-159">Where a preservation policy is stored</span></span>

<span data-ttu-id="c59eb-160">當您建立保留原則時，它會集中儲存安全性&amp;規範中心與再部署至不同的原則包含，例如網站、 信箱及公用資料夾的內容來源。</span><span class="sxs-lookup"><span data-stu-id="c59eb-160">When you create a preservation policy, it's stored centrally in the Security &amp; Compliance Center and then deployed to the different content sources that the policy includes, such as sites, mailboxes, and public folders.</span></span>
  
<span data-ttu-id="c59eb-p116">保留原則部署到這些內容來源之後，該原則的運作方式與 eDiscovery 就地保留完全相同。如需就地保留的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="c59eb-p116">After a preservation policy is deployed to those content sources, the policy works exactly the same as an eDiscovery in-place hold. For more information on in-place holds, see:</span></span>
  
- <span data-ttu-id="c59eb-163">[EDiscovery 與就地保留概觀](https://go.microsoft.com/fwlink/p/?LinkID=404352)(SharePoint Online)</span><span class="sxs-lookup"><span data-stu-id="c59eb-163">[Overview of eDiscovery and in-place holds](https://go.microsoft.com/fwlink/p/?LinkID=404352) (SharePoint Online)</span></span> 
    
- <span data-ttu-id="c59eb-164">[就地保留和訴訟資料暫留](https://go.microsoft.com/fwlink/p/?LinkID=404353)(Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="c59eb-164">[In-Place Hold and Litigation Hold](https://go.microsoft.com/fwlink/p/?LinkID=404353) (Exchange Online)</span></span> 
    
- <span data-ttu-id="c59eb-165">[可復原的項目] 資料夾](https://go.microsoft.com/fwlink/p/?LinkID=404354)(Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="c59eb-165">[Recoverable Items Folder](https://go.microsoft.com/fwlink/p/?LinkID=404354) (Exchange Online)</span></span> 
    
### <a name="preservation-policy-vs-ediscovery-hold"></a><span data-ttu-id="c59eb-166">相對於 eDiscovery 保留的保留原則</span><span class="sxs-lookup"><span data-stu-id="c59eb-166">Preservation policy vs. eDiscovery hold</span></span>

<span data-ttu-id="c59eb-167">當這些功能的保留的內容，這些功能不應混淆因為他們有不同的用途：</span><span class="sxs-lookup"><span data-stu-id="c59eb-167">While it's true that both of these features hold content, these features should not be confused because they serve different purposes:</span></span>
  
- <span data-ttu-id="c59eb-p117">**如果您需要保留內容保留需求的一部分，請使用保留原則。** 例如，如果您需要七個年度的內容保留為保留計畫的一部分，請使用保留原則。保留原則可以在特定時間期間內保留內容及該時段結尾的內容會自動從釋出該原則。使無人可以關閉原則或進行限制較少，也可能會鎖定該原則。EDiscovery 保留無法鎖定或指定時段。此外，將保留原則通常會有持續時間為年、 eDiscovery 保留為暫時以及通常會持續僅持續時間內的法律案例時。</span><span class="sxs-lookup"><span data-stu-id="c59eb-p117">**If you need to preserve content as part of a retention requirement, use a preservation policy.** For example, if you need to retain content for seven years as part of your retention plan, use a preservation policy. A preservation policy can preserve content for a specific time period, and at the end of that time period, the content's automatically released from the policy. The policy can also be locked so that no one can turn off the policy or make it less restrictive. An eDiscovery hold cannot be locked or specify a time period. Also, a preservation policy commonly has a duration of years, while an eDiscovery hold is temporary and commonly lasts only the duration of a legal case.</span></span> 
    
    <span data-ttu-id="c59eb-174">此外，您可以建立保留原則不需額外的步驟可能需要 eDiscovery，例如建立的情況下，新增成員，或執行內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="c59eb-174">In addition, you can create a preservation policy without the additional steps that eDiscovery may require, such as creating cases, adding members, or doing content searches.</span></span>
    
- <span data-ttu-id="c59eb-p118">**如果您需要保留內容法律或 eDiscovery 需求的一部分，請使用 eDiscovery 保留。** 例如，如果您需要的特定位置保留內容的法律要求的一部分，請使用 eDiscovery 保留。在 eDiscovery 案例相關的內容是通常機密或權限，因此不同的情況下可限制在不同的成員。此外，eDiscovery 支援可儲存、 預覽、 分析與進階 eDiscovery 的內容搜尋或有結果匯出。</span><span class="sxs-lookup"><span data-stu-id="c59eb-p118">**If you need to hold content as part of a legal or eDiscovery requirement, use an eDiscovery hold.** For example, if you need to hold content in specific locations as part of a legal request, use an eDiscovery hold. In eDiscovery, the content relevant to a case is typically sensitive or privileged, so different cases can be restricted to different members. In addition, eDiscovery supports content searches that can be saved, previewed, analyzed with Advanced eDiscovery, or have the results exported.</span></span> 
    
    <span data-ttu-id="c59eb-p119">與保留原則，不同 eDiscovery 保留無法指定一段時間-eDiscovery 保留為作用中直到您關閉它或予以刪除。此外，您無法鎖定 eDiscovery 保留。</span><span class="sxs-lookup"><span data-stu-id="c59eb-p119">Unlike a preservation policy, an eDiscovery hold cannot specify a time period - an eDiscovery hold is in effect until you turn it off or delete it. Also, an eDiscovery hold cannot be locked.</span></span>
    
## <a name="how-a-preservation-policy-works-with-document-versions-in-a-site"></a><span data-ttu-id="c59eb-181">保留原則對站台中各文件版本的運作方式</span><span class="sxs-lookup"><span data-stu-id="c59eb-181">How a preservation policy works with document versions in a site</span></span>

<span data-ttu-id="c59eb-p120">保留原則不會自動保留在網站中的文件的所有版本。若要這樣做，您需要開啟網站中的文件庫的版本設定。如需詳細資訊，請參閱[啟用和設定清單或文件庫的版本設定](https://go.microsoft.com/fwlink/p/?LinkID=404350)。</span><span class="sxs-lookup"><span data-stu-id="c59eb-p120">A preservation policy doesn't automatically preserve all versions of a document in a site. To do so, you need to turn on versioning for the document libraries in the site. For more information, see [Enable and configure versioning for a list or library](https://go.microsoft.com/fwlink/p/?LinkID=404350).</span></span>
  
<span data-ttu-id="c59eb-185">如果要保留網站從刪除文件及文件版本設定已開啟的文件庫，會保留已刪除的文件的所有版本。</span><span class="sxs-lookup"><span data-stu-id="c59eb-185">If a document is deleted from a site that's being preserved and document versioning is turned on for the library, all versions of the deleted document are preserved.</span></span> 
  
<span data-ttu-id="c59eb-p121">如果未開啟文件版本設定及項目受限於數個保留原則，就能保存的版本是屬於目前時每個保留原則會生效。例如，如果版本 27 的項目是最新網站會保留第一個的時間和版本 51 時是最新網站時保有第二次版本 27 及 51 會保留。</span><span class="sxs-lookup"><span data-stu-id="c59eb-p121">If document versioning isn't turned on and an item is subject to several preservation policies, the version that's preserved is the one that's current when each preservation policy takes effect. For example, if version 27 of an item is the most recent when the site is preserved the first time, and version 51 is the most recent when the site is preserved the second time, versions 27 and 51 are preserved.</span></span>
  
## <a name="filtering-a-preservation-policy"></a><span data-ttu-id="c59eb-188">篩選保留原則</span><span class="sxs-lookup"><span data-stu-id="c59eb-188">Filtering a preservation policy</span></span>

<span data-ttu-id="c59eb-189">您可以在原則中新增關鍵字或日期範圍，以縮減受限於保留原則的內容數。</span><span class="sxs-lookup"><span data-stu-id="c59eb-189">You can narrow down the content subject to a preservation policy by adding keywords or a date range to the policy.</span></span> 
  
![建立保留原則時，使用關鍵字和日期範圍做為篩選條件](media/603cef40-8f7c-4140-956f-28c092273582.png)
  
### <a name="filter-by-using-keywords"></a><span data-ttu-id="c59eb-191">使用關鍵字篩選</span><span class="sxs-lookup"><span data-stu-id="c59eb-191">Filter by using keywords</span></span>

<span data-ttu-id="c59eb-p122">保留原則支援關鍵字查詢語言 (KQL)。例如，您可以使用基本運算子 like AND 和或是，您可以執行接近搜尋"wingtip NEAR(30) marketing"其中用來識別結果"wingtip"所在的"sales"的 30 個字元內。關鍵字查詢可協助您識別並保留相關的內容。</span><span class="sxs-lookup"><span data-stu-id="c59eb-p122">A preservation policy supports Keyword Query Language (KQL). For example, you can use basic operators like AND and OR, and you can do a proximity search where "wingtip NEAR(30) marketing" identifies results where "wingtip" is within 30 characters of "marketing". A keyword query helps you to identify and preserve just the relevant content.</span></span>
  
### <a name="filter-by-using-a-date-range"></a><span data-ttu-id="c59eb-195">使用日期範圍篩選</span><span class="sxs-lookup"><span data-stu-id="c59eb-195">Filter by using a date range</span></span>

<span data-ttu-id="c59eb-p123">您也可以篩選保留原則，使其僅保存特定日期範圍內的內容。郵件的日期會與接收日期相關聯，文件和站台的日期則與修改日期相關聯。這表示，內容中若包含在特定日期範圍內、或是開始或結束日期之前或之後接收到的郵件和修改過的文件，就是您可以保存的內容。</span><span class="sxs-lookup"><span data-stu-id="c59eb-p123">You can also filter the policy so that it preserves only content within a specific date range. For messages, the date is relative to the received date, and for documents and sites, the date is relative to the modified date. This means you can preserve content that includes mail received and documents modified within a specific date range or before or after a start or end date.</span></span>
  
## <a name="preserving-content-for-a-specific-period-of-time"></a><span data-ttu-id="c59eb-199">將內容保留特定的一段時間</span><span class="sxs-lookup"><span data-stu-id="c59eb-199">Preserving content for a specific period of time</span></span>

<span data-ttu-id="c59eb-p124">在保留原則中，您可以無限期地保留內容，或保留特定的數天、月或年。請注意，保留內容的持續期間會從內容的存留期計算出來，而不是從保留原則的建立日期起算。</span><span class="sxs-lookup"><span data-stu-id="c59eb-p124">With a preservation policy, you can preserve content indefinitely or for a specific number of days, months, or years. Note that the duration for how long content is preserved is calculated from the age of the content, not from when the preservation policy is created.</span></span> 
  
<span data-ttu-id="c59eb-p125">例如，如果您想要保留的七個年度的網站內容與中的文件該站台尚未六個年度中已修改、 文件則會保留僅另一年如果它不會修改。如果再次編輯文件、 文件的期間的計算從新的上次修改日期，並它將會保留的另一個七個年。</span><span class="sxs-lookup"><span data-stu-id="c59eb-p125">For example, if you want to preserve content in a site for seven years, and a document in that site hasn't been modified in six years, the document will be preserved for only another year if it's not modified. If the document is edited again, the age of the document is calculated from the new last modified date, and it will be preserved for another seven years.</span></span>
  
<span data-ttu-id="c59eb-p126">同理，如果您要將信箱中的內容保留七年，而某郵件是六年前送入信箱的，則該郵件只會再保留一年，除非其接收日期經過修改。接收日期修改後，郵件的新版本會依照其進行編輯前的原狀保存在 [可復原的項目] 資料夾中，而郵件的存留期則會從新的接收日期起算，因而會再保留七年。</span><span class="sxs-lookup"><span data-stu-id="c59eb-p126">Similarly, if you want to preserve content in a mailbox for seven years, and a message was sent six years ago, the message will be preserved for only one year unless the date received is modified. In this case, a new version of the message as it existed before it was edited is preserved in the Recoverable Items folder, and the age of the message is calculated from the new date received, and it will be preserved for another seven years.</span></span>
  
![新保留原則的持續時間設定](media/455aac78-4c29-4dbb-93a2-b431b99002d9.png)
  
## <a name="locking-a-preservation-policy"></a><span data-ttu-id="c59eb-207">鎖定保留原則</span><span class="sxs-lookup"><span data-stu-id="c59eb-207">Locking a preservation policy</span></span>

<span data-ttu-id="c59eb-p127">有些組織可能需要遵守如美國證券業 and Exchange 委員會 （秒） 規則條例 17a-4，需要的保留原則會在開啟之後，它無法關閉或進行限制較少的法規本文所定義的規則。使用保留鎖定您可以讓鎖定之原則的任何人 — 包括系統管理員 — 可以關閉原則或進行限制較少。</span><span class="sxs-lookup"><span data-stu-id="c59eb-p127">Some organizations may need to comply with rules defined by regulatory bodies such as the Securities and Exchange Commission (SEC) Rule 17a-4, which requires that after a preservation policy is turned on, it cannot be turned off or made less restrictive. With Preservation Lock, you can lock the policy so that no one—including the administrator—can turn off the policy or make it less restrictive.</span></span>
  
<span data-ttu-id="c59eb-p128">鎖定原則之後，沒有人可以將它關閉或從原則移除內容。且並非可能要修改或刪除受限於期間保留原則的內容。原則的鎖定之後，您可以修改的保留原則的唯一方式是將內容新增至其或延伸其持續時間。鎖定的原則可增加或延伸，但它不能是降低] 或 [已關閉。</span><span class="sxs-lookup"><span data-stu-id="c59eb-p128">After a policy's been locked, no one can turn it off or remove content from the policy. And it's not possible to modify or delete content that's subject to the policy during the preservation period. After the policy's been locked, the only ways you can modify the preservation policy are by adding content to it or extending its duration. A locked policy can be increased or extended, but it can't be reduced or turned off.</span></span>
  
<span data-ttu-id="c59eb-214">因此，鎖定的保留原則之前，很重要您了解您的組織的規範需求及您請勿鎖定原則，直到您是特定它是您的需要。</span><span class="sxs-lookup"><span data-stu-id="c59eb-214">Therefore, before you lock a preservation policy, it's critical that you understand your organization's compliance requirements, and that you do not lock a policy until you are certain that it's what you need.</span></span>
  
![開啟 [保留鎖定] 的選項](media/cf9cc070-ddfb-469c-a47e-f88005a82fe4.png)
  
## <a name="turning-off-a-preservation-policy"></a><span data-ttu-id="c59eb-216">關閉 [保留原則</span><span class="sxs-lookup"><span data-stu-id="c59eb-216">Turning off a preservation policy</span></span>

<span data-ttu-id="c59eb-p129">如果您選擇不要鎖定的保留原則，您可以在任何時候，包括原則所指定的時間週期結束之前釋放它。若要這樣做，只是關閉該原則。</span><span class="sxs-lookup"><span data-stu-id="c59eb-p129">If you choose not to lock the preservation policy, you can release it at any time, including before the end of the time period specified by the policy. To do so, just turn off the policy.</span></span>
  
![關閉 [安全性] 的 [保留] 頁面上的保留原則的選項&amp;規範中心](media/fdb44455-da01-4480-8fa6-0e3b29b1f535.png)
  
<span data-ttu-id="c59eb-p130">不過，您無法刪除保留原則時仍在作用中的 [原則。若要刪除的保留原則，請先關閉和刪除原則，然後。</span><span class="sxs-lookup"><span data-stu-id="c59eb-p130">However, you can't delete a preservation policy while the policy's still active. To delete a preservation policy, first turn off and then delete the policy.</span></span>
  
<span data-ttu-id="c59eb-p131">關閉的保留原則後，受限於該原則保留保留文件庫或可復原的項目] 資料夾中的所有項目是適合標準清除前述的程序。請注意這表示該原則中發行的項目不會立即刪除;而這些都維持保留保留文件庫或可復原的項目] 資料夾中的程序定期清除文件庫或資料夾。</span><span class="sxs-lookup"><span data-stu-id="c59eb-p131">After you turn off a preservation policy, all items subject to that policy in the Preservation Hold library or Recoverable Items folder are eligible for the standard cleanup process described earlier. Note that this means that items released from a policy are not immediately deleted; instead, they remain in the Preservation Hold library or Recoverable Items folder until the process periodically cleans up the library or folder.</span></span>
  
## <a name="using-preservation-policies-with-retention-policies-and-document-deletion-policies"></a><span data-ttu-id="c59eb-224">將保留原則 (preservation policy) 與保留原則 (retention policy) 和文件刪除原則搭配使用</span><span class="sxs-lookup"><span data-stu-id="c59eb-224">Using preservation policies with retention policies and document deletion policies</span></span>

<span data-ttu-id="c59eb-p132">保留原則 (preservation policy) 可確保內容能無限期或在特定的一段時間內保存，而信箱的保留原則 (retention policy) 和站台的文件刪除原則則可確保內容會在特定的一段時間後刪除。如果您需要在固定的一段時間內保有內容，您可以將保留原則 (preservation policy) 與保留原則 (retention policy) 或刪除原則搭配使用。</span><span class="sxs-lookup"><span data-stu-id="c59eb-p132">A preservation policy ensures that content is preserved indefinitely or for a specific period of time, while a retention policy for a mailbox and a document deletion policy for a site ensures that content is deleted after a specific period of time. If you need to retain content for a fixed period of time, you can use a preservation policy in conjunction with a retention or deletion policy.</span></span> 
  
### <a name="site-content"></a><span data-ttu-id="c59eb-227">站台內容</span><span class="sxs-lookup"><span data-stu-id="c59eb-227">Site content</span></span>

<span data-ttu-id="c59eb-p133">對於站台，您可以搭配使用保留原則與文件刪除原則。例如，您可以在文件修改後將其保留五年，然後設定會在文件前次修改的五年之後加以刪除的刪除原則。</span><span class="sxs-lookup"><span data-stu-id="c59eb-p133">For a site, you can use a preservation policy in conjunction with a document deletion policy. For example, you could preserve documents for five years after they are modified, and then set up a deletion policy to delete them five years after they were last modified.</span></span>
  
<span data-ttu-id="c59eb-p134">如果文件刪除原則會刪除受限於保留原則的內容，則仍會保留保留文件庫中保留內容。例如如果保留原則的兩個年度會保留內容，但文件刪除原則一年後刪除內容，則仍會保留任何已刪除的內容。如需詳細資訊，請參閱 ＜ [Overview of 文件刪除原則](https://support.office.com/article/55e8d858-f278-482b-a198-2e62d6a2e6e5)。</span><span class="sxs-lookup"><span data-stu-id="c59eb-p134">If a document deletion policy deletes content that's subject to a preservation policy, the content will still be preserved in the Preservation Hold library. For example, if a preservation policy preserves content for two years, but a document deletion policy deletes content after one year, any content that's deleted will still be preserved. For more information, see [Overview of document deletion policies](https://support.office.com/article/55e8d858-f278-482b-a198-2e62d6a2e6e5).</span></span>
  
### <a name="mailbox-content"></a><span data-ttu-id="c59eb-233">信箱內容</span><span class="sxs-lookup"><span data-stu-id="c59eb-233">Mailbox content</span></span>

<span data-ttu-id="c59eb-p135">信箱，您可以合併以保留原則有單一的預設原則標記的保留原則。例如，您無法七個年度的保留信箱項目而然後設定刪除這些七個年後他們所接收 （適用於郵件） 或 （適用於未傳送，例如備忘稿的項目） 建立保留原則。保留原則可確保該取得已刪除的項目會保留為至少指定工期排時保留原則可確保結尾處的這段時間內刪除的信箱項目。如需詳細資訊，請參閱[保留標記和保留原則](https://go.microsoft.com/fwlink/p/?LinkID=404351)。</span><span class="sxs-lookup"><span data-stu-id="c59eb-p135">For a mailbox, you can combine a preservation policy with a retention policy that has a single default policy tag. For example, you could preserve mailbox items for seven years, and then set up a retention policy to delete them seven years after they were received (for messages) or created (for items that aren't sent, like notes). The preservation policy ensures that items that get deleted are preserved for at least the specified duration, while the retention policy ensures that mailbox items are deleted at the end of that period. For more information, see [Retention tags and retention policies](https://go.microsoft.com/fwlink/p/?LinkID=404351).</span></span>
  
## <a name="permissions"></a><span data-ttu-id="c59eb-238">權限</span><span class="sxs-lookup"><span data-stu-id="c59eb-238">Permissions</span></span>

<span data-ttu-id="c59eb-239">將會使用安全性規範小組成員&amp;規範中心來建立保留原則需要的權限：</span><span class="sxs-lookup"><span data-stu-id="c59eb-239">Members of your compliance team who will use the Security &amp; Compliance Center to create preservation policies need permissions to the:</span></span>
  
-  <span data-ttu-id="c59eb-240">Office 365 安全性&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="c59eb-240">Office 365 Security &amp; Compliance Center</span></span> 
    
- <span data-ttu-id="c59eb-241">具有需要保留內容的站台</span><span class="sxs-lookup"><span data-stu-id="c59eb-241">Sites with content that needs to be preserved</span></span>
    
- <span data-ttu-id="c59eb-242">具有需要保留內容的信箱</span><span class="sxs-lookup"><span data-stu-id="c59eb-242">Mailboxes with content that needs to be preserved</span></span>
    
### <a name="office-365-security-amp-compliance-center"></a><span data-ttu-id="c59eb-243">Office 365 安全性&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="c59eb-243">Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="c59eb-244">您想要能夠法規遵循主管和其他人存取授與安全性租用戶系統管理員身分&amp;規範中心，但不授與之所有權限的租用戶管理]。如需詳細資訊，請參閱[Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="c59eb-244">As a tenant admin, you want to be able to give compliance officers and other people access to the Security &amp; Compliance Center, without giving them all of the permissions of a tenant admin. For more information, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  
### <a name="sites"></a><span data-ttu-id="c59eb-245">網站</span><span class="sxs-lookup"><span data-stu-id="c59eb-245">Sites</span></span>

<span data-ttu-id="c59eb-p136">您的法規小組成員 (建立保留原則) 需要套用原則的網站集合的權限。此外，如果法務人員也建立文件刪除原則，則他們需要在其中建立和儲存文件刪除原則的規範原則中心網站集合的權限。我們建議您：</span><span class="sxs-lookup"><span data-stu-id="c59eb-p136">Members of your compliance team who create preservation policies need permissions to the site collections to which policies will be applied. In addition, if compliance officers also create document deletion policies, they need permissions to the Compliance Policy Center site collection where document deletion policies are created and stored. We recommend that you:</span></span>
  
1. <span data-ttu-id="c59eb-p137">建立包含規範原則中心 」 的所有使用者的安全性群組 — 很有可能規範原則管理小組。如需詳細資訊，請參閱[Manage Mail-Enabled 安全性群組](https://go.microsoft.com/fwlink/p/?LinkID=404345)。</span><span class="sxs-lookup"><span data-stu-id="c59eb-p137">Create a security group that contains all users of the Compliance Policy Center — most likely your compliance policy-management team. See [Manage Mail-Enabled Security Groups](https://go.microsoft.com/fwlink/p/?LinkID=404345) for more information.</span></span> 
    
2. <span data-ttu-id="c59eb-p138">在 [規範原則中心] 中，新增 [安全性] 群組的網站集合擁有者群組。如需詳細資訊，請參閱[網站集合管理員的權限](https://go.microsoft.com/fwlink/p/?LinkID=404346)。</span><span class="sxs-lookup"><span data-stu-id="c59eb-p138">In the Compliance Policy Center, add the security group to the site collection Owners group. See [Permissions for site collection administrators](https://go.microsoft.com/fwlink/p/?LinkID=404346) for more information.</span></span> 
    
3. <span data-ttu-id="c59eb-253">在您需要指派保留原則的每個站台集合中，將安全性群組新增至站台集合訪客群組 (讀取權限)。</span><span class="sxs-lookup"><span data-stu-id="c59eb-253">In each site collection to which you need to assign preservation policies, add the security group to the site collection Visitors group (read permissions).</span></span>
    
### <a name="mailboxes-and-public-folders"></a><span data-ttu-id="c59eb-254">信箱與公用資料夾</span><span class="sxs-lookup"><span data-stu-id="c59eb-254">Mailboxes and public folders</span></span>

<span data-ttu-id="c59eb-255">若要將保留原則套用至信箱，法務人員至少需要該信箱的讀取權限。</span><span class="sxs-lookup"><span data-stu-id="c59eb-255">To apply a preservation policy to a mailbox, compliance officers need at least read permissions for that mailbox.</span></span> 
  
<span data-ttu-id="c59eb-256">若要將保留原則套用至公用資料夾，法務人員至少需要所有公用資料夾的讀取權限。</span><span class="sxs-lookup"><span data-stu-id="c59eb-256">To apply a preservation policy to a public folder, compliance officers need at least read permissions for all of the public folders.</span></span>
  

