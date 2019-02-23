---
title: 建立及管理 Office 365 中的非使用中信箱
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 296a02bd-ebde-4022-900e-547acf38ddd7
description: 您可以建立 Office 365 中的非使用中的信箱將保留或 Office 365 保留原則套用至信箱並再將其刪除對應的 Office 365 使用者帳戶。保留或保留原則套用至其已進行非使用中之前的期間，會保留不在作用中的信箱中的項目。若要永久刪除非作用中的信箱，只是移除保留或保留原則。
ms.openlocfilehash: 8f798873da7d787b54932438e81aebf2dfe85181
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217773"
---
# <a name="create-and-manage-inactive-mailboxes-in-office-365"></a><span data-ttu-id="8e87f-105">建立及管理 Office 365 中的非使用中信箱</span><span class="sxs-lookup"><span data-stu-id="8e87f-105">Create and manage inactive mailboxes in Office 365</span></span>

<span data-ttu-id="8e87f-p102">Office 365 可以讓您保留已刪除信箱的內容。此功能會呼叫[不在作用中的信箱](inactive-mailboxes-in-office-365.md)。非使用中信箱可讓您保留先前的員工電子郵件之後他們離開貴組織。訴訟暫止狀態或 Office 365 保留原則時信箱會變成非作用中 (建立 Office 365 安全性&amp;規範中心) 對應的 Office 365 使用者帳戶會在刪除之前會套用至信箱。不在作用中信箱的內容會保留它進行非使用中之前被指定信箱的保留期間。這可讓系統管理員、 法務人員及記錄經理可以使用內容的搜尋安全性&amp;規範中心來搜尋並匯出非使用中信箱的內容。非使用中信箱無法接收電子郵件及未出現在您的組織共用的通訊錄或其他清單。</span><span class="sxs-lookup"><span data-stu-id="8e87f-p102">Office 365 makes it possible for you to retain the contents of deleted mailboxes. This feature is called [inactive mailboxes](inactive-mailboxes-in-office-365.md). Inactive mailboxes allow you to retain former employees' email after they leave your organization. A mailbox becomes inactive when a Litigation Hold or an Office 365 retention policy (created in the Office 365 Security &amp; Compliance Center) is applied to the mailbox before the corresponding Office 365 user account is deleted. The contents of an inactive mailbox are retained for the duration of the hold that was placed on the mailbox before it was made inactive. This allows administrators, compliance officers, and records managers to use Content Search in the Security &amp; Compliance Center to search and export the contents of an inactive mailbox. Inactive mailboxes can't receive email and aren't displayed in your organization's shared address book or other lists.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8e87f-p103">我們已將 2017 年 7 月 1 日的期限延後，以建立新的「就地保留」來建立非使用中的信箱。但到今年年底或明年年初，您將無法在 Exchange Online 中建立新的「就地保留」。到時，只有「訴訟資料暫留」和 Office 365 保留原則可以用來建立非使用中的信箱。不過，仍會支援「就地保留」上現有的非使用中信箱，並且您可以繼續管理非使用信箱上的「就地保留」。這包括變更「就地保留」期間，以及透過移除「就地保留」永久刪除非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="8e87f-p103">We've postponed the July 1, 2017 deadline for creating new In-Place Holds to make a mailbox inactive. But later this year or early next year, you won't be able to create new In-Place Holds in Exchange Online. At that time, only Litigation Holds and Office 365 retention policies can be used to create an inactive mailbox. However, existing inactive mailboxes that are on In-Place Hold will still be supported, and you can continue to manage the In-Place Holds on inactive mailboxes. This includes changing the duration of an In-Place Hold and permanently deleting an inactive mailbox by removing the In-Place Hold.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="8e87f-118">開始之前</span><span class="sxs-lookup"><span data-stu-id="8e87f-118">Before you begin</span></span>

- <span data-ttu-id="8e87f-p104">若要停用信箱，它必須被指派 Exchange Online 計劃 2 授權使訴訟暫止狀態或 Office 365 保留原則可套用至信箱會在刪除之前。Exchange Online 計劃 2 授權是 Office 365 企業版 E3 和 E5 訂閱的一部分。如果信箱指派 Exchange Online 計劃 1 授權 （這是 Office 365 企業版 E1 訂閱的一部分），您必須將使保留可套用至信箱會在刪除之前將其指派不同的 Exchange Online 封存授權。如需詳細資訊，請參閱[Exchange Online 封存](https://go.microsoft.com/fwlink/p/?LinkId=286153)。</span><span class="sxs-lookup"><span data-stu-id="8e87f-p104">To make a mailbox inactive, it must be assigned an Exchange Online Plan 2 license so that a Litigation Hold or an Office 365 retention policy can be applied to the mailbox before it's deleted. Exchange Online Plan 2 licenses are part of an Office 365 Enterprise E3 and E5 subscriptions. If a mailbox is assigned an Exchange Online Plan 1 license (which is part of an Office 365 Enterprise E1 subscription), you would have to assign it a separate Exchange Online Archiving license so that a hold can be applied to the mailbox before it's deleted. For more information, see [Exchange Online Archiving](https://go.microsoft.com/fwlink/p/?LinkId=286153).</span></span>
    
- <span data-ttu-id="8e87f-p105">刪除對應的 Office 365 使用者帳戶之後將可以使用 [刪除的 Exchange Online 信箱相關聯的授權。然後您可以[指派給 Office 365 中的商務使用者的授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)給另一個使用者。</span><span class="sxs-lookup"><span data-stu-id="8e87f-p105">The license associated with the deleted Exchange Online mailbox will be available after you delete the corresponding Office 365 user account. You can then [Assign licenses to users in Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) to another user.</span></span> 
    
- <span data-ttu-id="8e87f-p106">如果訴訟暫止狀態或 Office 365 保留原則不套用到信箱會在刪除之前內容不會是信箱的保留或可供搜尋。不過，刪除排程、 30 天內可復原已刪除的信箱但信箱和其內容會永久刪除 30 天後如果它不復原。</span><span class="sxs-lookup"><span data-stu-id="8e87f-p106">If a Litigation Hold or an Office 365 retention policy isn't applied to a mailbox before it's deleted, the contents of the mailbox won't be retained or discoverable. However, the deleted mailbox can be recovered within 30 days of deletion, but the mailbox and its contents will be permanently deleted after 30 days if it isn't recovered.</span></span>
    
- <span data-ttu-id="8e87f-p107">如需訴訟暫止狀態的詳細資訊，請參閱[就地保留和訴訟暫止狀態](https://go.microsoft.com/fwlink/p/?LinkId=846124)。如需關於 Office 365 安全性的保留原則&amp;規範中心，請參閱[Overview of Office 365 中的保留原則](retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="8e87f-p107">For more information about Litigation Hold, see [In-Place Hold and Litigation Hold](https://go.microsoft.com/fwlink/p/?LinkId=846124). For more information about Office 365 retention policies in the Security &amp; Compliance Center, see [Overview of retention policies in Office 365](retention-policies.md).</span></span>
  
## <a name="create-an-inactive-mailbox"></a><span data-ttu-id="8e87f-129">建立非使用中信箱</span><span class="sxs-lookup"><span data-stu-id="8e87f-129">Create an inactive mailbox</span></span>

<span data-ttu-id="8e87f-p108">讓信箱不在作用中包含兩個步驟： 1） 將放置信箱訴訟暫止狀態或 Office 365 保留原則套用到其中，和 2） 刪除信箱或相對應的 Office 365 使用者帳戶。不在作用中信箱後，直到移除保留或保留原則將會保留其內容。</span><span class="sxs-lookup"><span data-stu-id="8e87f-p108">Making a mailbox inactive involves two steps: 1) placing the mailbox on Litigation Hold or applying an Office 365 retention policy to it, and 2) deleting the mailbox or corresponding Office 365 user account. After the mailbox is inactive, its contents are retained until the hold or retention policy is removed.</span></span>
  
### <a name="step-1-place-a-mailbox-on-litigation-hold-or-apply-an-office-365-retention-policy"></a><span data-ttu-id="8e87f-132">步驟 1： 將信箱置於訴訟暫止狀態或適用於 Office 365 保留原則</span><span class="sxs-lookup"><span data-stu-id="8e87f-132">Step 1: Place a mailbox on Litigation Hold or apply an Office 365 retention policy</span></span>

<span data-ttu-id="8e87f-p109">訴訟暫止狀態將信箱設定或套用 Office 365 保留原則會在刪除之前會保留信箱中的內容。這兩種類型的保留會保留所有信箱內容，包括已刪除的項目和已修改項目的原始版本。已刪除及修改過的項目會保留在非使用中的信箱在指定的期間內或直到您永久刪除非使用中信箱移除套用至非使用中信箱的保留或保留原則。</span><span class="sxs-lookup"><span data-stu-id="8e87f-p109">Placing a mailbox on Litigation Hold or applying an Office 365 retention policy retains the contents in the mailbox before it's deleted. Both types of holds will retain all mailbox content, including deleted items and original versions of modified items. Deleted and modified items are retained in the inactive mailbox for a specified period, or until you permanently delete the inactive mailbox by removing the hold or retention policy that's applied to the inactive mailbox.</span></span>
  
<span data-ttu-id="8e87f-136">如果保留已處於信箱或 Office 365 保留原則已套用到信箱，則您只需要是步驟 2 所述刪除對應的 Office 365 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="8e87f-136">If a hold is already placed on a mailbox, or if an Office 365 retention policy is already applied to a mailbox, then all you have to do is delete the corresponding Office 365 user account as explained in Step 2.</span></span>
  
<span data-ttu-id="8e87f-137">將信箱設定訴訟暫止狀態或將 Office 365 保留原則套用的逐步程序，請參閱：</span><span class="sxs-lookup"><span data-stu-id="8e87f-137">For step-by-step procedures for placing a mailbox on Litigation Hold or applying an Office 365 retention policy, see:</span></span>
  
- [<span data-ttu-id="8e87f-138">將信箱設定為訴訟資料暫留狀態</span><span class="sxs-lookup"><span data-stu-id="8e87f-138">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/?linkid=856286)
    
- [<span data-ttu-id="8e87f-139">Office 365 中的保留原則的概觀</span><span class="sxs-lookup"><span data-stu-id="8e87f-139">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
> [!NOTE]
> <span data-ttu-id="8e87f-p110">訴訟保留與 Office 365 的保留原則，您可以建立無限期保留或在時間型保留。在無限期保留，不在作用中信箱的內容將永久，保留或直到移除保留或直到變更保留持續時間。保留或保留原則移除 （假設信箱已遭刪除超過 30 天） 後，將目標記為要永久刪除非使用中信箱和信箱的內容不再是保留或可供搜尋。時間型保留或 Office 365 保留原則，您會指定保留的期限。此持續時間是每個項目和信箱項目所接收或建立日期開始。保留信箱項目到期以及該項目移至或非使用中的信箱中的可復原的項目] 資料夾位於之後，此項目會永久刪除 （清除） 從非使用中信箱後刪除項目保留期間到期。</span><span class="sxs-lookup"><span data-stu-id="8e87f-p110">For Litigation Holds and Office 365 retention policies, you can create an indefinite hold or on a time-based hold. In an indefinite hold, the contents of the inactive mailbox will be retained forever, or until the hold is removed or until the hold duration is changed. After the hold or retention policy is removed (assuming that the mailbox was deleted more than 30 days ago), the inactive mailbox will be marked for permanent deletion and the contents of the mailbox will no longer be retained or discoverable. In a time-based hold or Office 365 retention policy, you specify the duration of the hold. This duration is on a per-item basis and is calculated from the date a mailbox item was received or created. After the hold expires for a mailbox item, and that item moved to or is located in the Recoverable Items folder in the inactive mailbox, the item is permanently deleted (purged) from the inactive mailbox after the deleted item retention period expires.</span></span> 
  
### <a name="step-2-delete-the-mailbox"></a><span data-ttu-id="8e87f-146">步驟 2：刪除信箱</span><span class="sxs-lookup"><span data-stu-id="8e87f-146">Step 2: Delete the mailbox</span></span>

<span data-ttu-id="8e87f-p111">信箱處於保留狀態或 Office 365 保留原則套用至其之後下, 一步是以刪除信箱。若要刪除信箱的最佳方式是要刪除對應的 Office 365 使用者帳戶在 Office 365 系統管理中心。刪除 Office 365 使用者帳戶的相關資訊，請參閱[刪除您組織中的使用者](https://support.office.com/article/d5155593-3bac-4d8d-9d8b-f4513a81479e)。</span><span class="sxs-lookup"><span data-stu-id="8e87f-p111">After the mailbox is placed on hold or an Office 365 retention policy is applied to it, the next step is to delete the mailbox. The best way to delete a mailbox is to delete the corresponding Office 365 user account in the Office 365 admin center. For information about deleting Office 365 user accounts, see [Delete a user from your organization](https://support.office.com/article/d5155593-3bac-4d8d-9d8b-f4513a81479e).</span></span>
  
> [!NOTE]
> <span data-ttu-id="8e87f-p112">您也可以在 Exchange Online PowerShell 中使用**Remove-mailbox**指令程式刪除信箱。如需詳細資訊，請參閱[刪除或還原使用者信箱在 Exchange Online](https://go.microsoft.com/fwlink/?linkid=856287)。</span><span class="sxs-lookup"><span data-stu-id="8e87f-p112">You can also delete the mailbox by using the **Remove-Mailbox** cmdlet in Exchange Online PowerShell. For more information, see [Delete or restore user mailboxes in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856287).</span></span> 
  

## <a name="view-a-list-of-inactive-mailboxes"></a><span data-ttu-id="8e87f-152">檢視非使用中信箱的清單</span><span class="sxs-lookup"><span data-stu-id="8e87f-152">View a list of inactive mailboxes</span></span>


<span data-ttu-id="8e87f-153">若要檢視您組織中的非使用中信箱的清單：</span><span class="sxs-lookup"><span data-stu-id="8e87f-153">To view a list of the inactive mailboxes in your organization:</span></span>
  
1. <span data-ttu-id="8e87f-154">移至 [[https://protection.office.com/](https://protection.office.com/)並登入使用 Office 365 組織中系統管理員帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="8e87f-154">Go to [https://protection.office.com/](https://protection.office.com/) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="8e87f-155">在 [安全性] 的左窗格中&amp;規範中心，按一下 [**資料控管** \> \* \* 保留 \* \*。</span><span class="sxs-lookup"><span data-stu-id="8e87f-155">In the left pane of the Security &amp; Compliance Center, click **Data governance** \> \*\* Retention \*\*.</span></span>
    
3. <span data-ttu-id="8e87f-156">在 [**保留**] 頁面上按一下 [**更多**![導覽列省略符號](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif)，然後按一下 [**非使用中的信箱**。</span><span class="sxs-lookup"><span data-stu-id="8e87f-156">On the **Retention** page, click **More**![Navigation Bar ellipses](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif), and then click **Inactive mailboxes**.</span></span>
    
    ![在 [保留] 頁面上，按一下 [更多及 [非使用中信箱移轉至顯示不在作用中信箱的清單](media/761bd90c-3e37-48f9-b1b9-479e90fea267.png)
  
    <span data-ttu-id="8e87f-p113">會顯示 [**非使用中信箱**] 頁面。請注意顯示組織中不在作用中的信箱總數。</span><span class="sxs-lookup"><span data-stu-id="8e87f-p113">The **Inactive mailboxes** page is displayed. Note the total number of inactive mailboxes in your organization is displayed.</span></span> 
    
    ![會顯示您組織中的所有非使用中信箱的清單](media/57d9d183-0c6c-4bd8-82e7-115f7b7b6de7.png)
  
<span data-ttu-id="8e87f-161">或者，您可以執行下列命令在 Exchange Online PowerShell 來顯示不在作用中信箱的清單。</span><span class="sxs-lookup"><span data-stu-id="8e87f-161">Alternatively, you can run the following command in Exchange Online PowerShell to display the list of inactive mailboxes.</span></span>

```
 Get-Mailbox -InactiveMailboxOnly | FT DisplayName,PrimarySMTPAddress,WhenSoftDeleted
```

<span data-ttu-id="8e87f-162">您可以按一下 [![匯出搜尋結果圖示](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png)**匯出**檢視或下載 CSV 檔案包含您組織中不在作用中信箱的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="8e87f-162">You can click ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **Export** to view or download a CSV file that contains additional information about the inactive mailboxes in your organization.</span></span> 
  
<span data-ttu-id="8e87f-p114">您也可以執行下列命令以將非使用中信箱的清單和其他資訊匯出至 CSV 檔案。在這個範例中，目前目錄中建立 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="8e87f-p114">You can also run the following command to export the list of inactive mailboxes and other information to a CSV file. In this example, the CSV file is created in the current directory.</span></span>

```
Get-Mailbox -InactiveMailboxOnly | Select Displayname,PrimarySMTPAddress,DistinguishedName,ExchangeGuid,WhenSoftDeleted | Export-Csv InactiveMailboxes.csv -NoType
```
   
> [!NOTE]
> <span data-ttu-id="8e87f-p115">有可能不在作用中的信箱可能會有相同的 SMTP 地址為作用中使用者信箱。在此例中**DistinguishedName**或**ExchangeGuid**屬性的值可以用來唯一地識別非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="8e87f-p115">It's possible that an inactive mailbox may have the same SMTP address as an active user mailbox. In this case, the value of the **DistinguishedName** or **ExchangeGuid** property can be used to uniquely identify an inactive mailbox.</span></span> 
  
## <a name="search-and-export-the-contents-of-an-inactive-mailbox"></a><span data-ttu-id="8e87f-167">搜尋並匯出非使用中信箱的內容</span><span class="sxs-lookup"><span data-stu-id="8e87f-167">Search and export the contents of an inactive mailbox</span></span>

<span data-ttu-id="8e87f-p116">您可以使用 「 內容搜尋工具安全性存取非使用中信箱的內容&amp;規範中心。當您搜尋非使用中的信箱時，您可以建立關鍵字搜尋查詢，搜尋特定的項目或您可以傳回非使用中信箱的完整內容。您可以預覽搜尋結果或將搜尋結果匯出至 Outlook 資料 (PST) 檔案或以個別的電子郵件訊息方式。搜尋信箱及匯出搜尋結果的逐步程序，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="8e87f-p116">You can access the contents of the inactive mailbox by using the Content Search tool in the Security &amp; Compliance Center. When you search an inactive mailbox, you can create a keyword search query to search for specific items or you can return the entire contents of the inactive mailbox. You can preview the search results or export the search results to an Outlook Data (PST) file or as individual email messages. For step-by-step procedures for searching mailboxes and exporting search results, see the following topics:</span></span>
  
- [<span data-ttu-id="8e87f-172">Office 365 中的內容搜尋</span><span class="sxs-lookup"><span data-stu-id="8e87f-172">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="8e87f-173">從 Office 365 安全性匯出內容的搜尋結果&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="8e87f-173">Export Content Search results from the Office 365 Security &amp; Compliance Center</span></span>](export-search-results.md)
    
<span data-ttu-id="8e87f-174">以下是搜尋非使用中信箱時請牢記的一些事項。</span><span class="sxs-lookup"><span data-stu-id="8e87f-174">Here are a few things to keep in mind when searching inactive mailboxes.</span></span>
  
- <span data-ttu-id="8e87f-175">如果內容搜尋包含使用者信箱，該信箱再進行非使用中內容的搜尋會繼續搜尋不在作用中的信箱時變成非使用中之後重新執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="8e87f-175">If a content search includes a user mailbox and that mailbox is then made inactive, the content search will continue to search the inactive mailbox when you re-run the search after it becomes inactive.</span></span>
    
- <span data-ttu-id="8e87f-p117">在某些情況下，使用者可能會有作用中的信箱，而非使用中的信箱具有相同的 SMTP 地址。在此例中，只選取作為內容的搜尋位置的特定信箱拼寫須符合。換句話說，如果您將使用者的信箱新增到搜尋，您不能假設其作用中且非使用中的信箱拼寫須符合;要搜尋的明確新增到搜尋的信箱。</span><span class="sxs-lookup"><span data-stu-id="8e87f-p117">In some cases, a user may have an active mailbox and an inactive mailbox that have the same SMTP address. In this case, only the specific mailbox that you select as a location for a content search will be searched. In other words, if you add a user's mailbox to a search, you can't assume that both their active and inactive mailboxes will be searched; only the mailbox that you explicitly add to the search will be searched.</span></span>
    
- <span data-ttu-id="8e87f-p118">我們強烈建議您避免擁有作用中信箱和非使用中的信箱使用相同的 SMTP 地址。如果您需要重複使用的目前指派給非使用中信箱的 SMTP 位址，我們建議您復原非使用中的信箱或非使用中信箱的內容還原至作用中的信箱 （或 [作用中信箱的封存），然後刪除非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="8e87f-p118">We strongly recommend that you avoid having an active mailbox and inactive mailbox with the same SMTP address. If you need to reuse the SMTP address that is currently assigned to an inactive mailbox, we recommend that you recover the inactive mailbox or restore the contents of an inactive mailbox to an active mailbox (or the archive of an active mailbox), and then delete the inactive mailbox.</span></span>
    
## <a name="change-the-hold-duration-for-an-inactive-mailbox"></a><span data-ttu-id="8e87f-181">變更非使用中信箱的保留期間</span><span class="sxs-lookup"><span data-stu-id="8e87f-181">Change the hold duration for an inactive mailbox</span></span>

<span data-ttu-id="8e87f-p119">進行不在作用中信箱之後，您可以變更保留或 Office 365 保留原則套用至非使用中信箱的工期。如需逐步程序，請參閱 ＜ [Change Office 365 中不在作用中信箱的保留期間](change-the-hold-duration-for-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="8e87f-p119">After a mailbox is made inactive, you can change the duration of the hold or the Office 365 retention policy applied to the inactive mailbox. For step-by-step procedures, see [Change the hold duration for an inactive mailbox in Office 365](change-the-hold-duration-for-an-inactive-mailbox.md).</span></span>
  
## <a name="recover-an-inactive-mailbox"></a><span data-ttu-id="8e87f-184">復原非使用中的信箱</span><span class="sxs-lookup"><span data-stu-id="8e87f-184">Recover an inactive mailbox</span></span>

<span data-ttu-id="8e87f-p120">如果先前的員工會傳回您組織中，或將新的員工雇用採取 departed 員工的工作職責，您可以復原不在作用中信箱的內容。當您復原不在作用中的信箱時，信箱轉換成新的信箱、 保留的內容和非使用中的信箱資料夾結構，及信箱連結至新的使用者帳戶。它會復原之後，非使用中的信箱不存在。逐步程序及詳細資訊發生問題時復原不在作用中的信箱，請參閱[Office 365 中的不在作用中信箱復原](recover-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="8e87f-p120">If a former employee returns to your organization, or if a new employee is hired to take on the job responsibilities of the departed employee, you can recover the contents of the inactive mailbox. When you recover an inactive mailbox, the mailbox is converted to a new mailbox, the contents and folder structure of the inactive mailbox are retained, and the mailbox is linked to a new user account. After it's recovered, the inactive mailbox no longer exists. For step-by-step procedures and more information about happens when you recover an inactive mailbox, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
  
## <a name="restore-the-contents-of-an-inactive-mailbox-to-another-mailbox"></a><span data-ttu-id="8e87f-189">還原至另一個信箱不在作用中信箱的內容</span><span class="sxs-lookup"><span data-stu-id="8e87f-189">Restore the contents of an inactive mailbox to another mailbox</span></span>

<span data-ttu-id="8e87f-p121">如果另一位員工採用在先前的員工、 工作職責或另一個人需要存取非使用中信箱的內容，您可以還原 （或合併） 至現有的信箱不在作用中信箱的內容。當您還原非使用中信箱內容複製到另一個信箱。非使用中的信箱，則會保留與會維持不在作用中的信箱。非使用中信箱仍可搜尋使用 eDiscovery、 其內容可以還原至另一個信箱或復原或刪除日後。如需逐步程序，請參閱[還原 Office 365 中的非使用中信箱](restore-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="8e87f-p121">If another employee takes on the job responsibilities of a former employee, or if another person needs access to the contents of the inactive mailbox, you can restore (or merge) the contents of the inactive mailbox to an existing mailbox. When you restore an inactive mailbox, the contents are copied to another mailbox. The inactive mailbox is retained and remains an inactive mailbox. The inactive mailbox can still be searched using eDiscovery, its contents can be restored to another mailbox, or it can be recovered or deleted at a later date. For step-by-step procedures, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>
  
## <a name="delete-an-inactive-mailbox"></a><span data-ttu-id="8e87f-195">刪除非使用中的信箱</span><span class="sxs-lookup"><span data-stu-id="8e87f-195">Delete an inactive mailbox</span></span>

<span data-ttu-id="8e87f-p122">如果您不再需要保留非使用中信箱的內容，您可以永久刪除非使用中信箱移除保留或移除 Office 365 保留原則套用至非使用中的信箱。如果信箱已遭刪除超過 30 天，信箱加以標示為永久刪除之後移除保留與信箱會變成無法修復。如果在過去 30 天內刪除信箱，則您仍可以復原信箱之後移除保留或保留原則。逐步程序移除保留或要永久刪除非作用中信箱的 Office 365 保留原則，請參閱[刪除非作用中的信箱在 Office 365 中](delete-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="8e87f-p122">If you no longer need to retain the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold or removing the Office 365 retention policy applied to the inactive mailbox. If the mailbox was deleted more than 30 days ago, the mailbox will be marked for permanent deletion after you remove the hold, and the mailbox will become non-recoverable. If the mailbox was deleted within the last 30 days, you can still recover the mailbox after removing the hold or retention policy. For step-by-step procedures for removing a hold or a Office 365 retention policy to permanently delete an inactive mailbox, see [Delete an inactive mailbox in Office 365](delete-an-inactive-mailbox.md).</span></span>