---
title: 設定 Office 365 組織中信箱的封存及刪除原則
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/9/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MBS150
- BCS160
ms.assetid: ec3587e4-7b4a-40fb-8fb8-8aa05aeae2ce
description: 建立封存及刪除原則會自動將項目移至使用者的封存信箱的 Office 365 中。
ms.openlocfilehash: 807488f9ec7088adccdf1fc111d67b9dab8e0a38
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526830"
---
# <a name="set-up-an-archive-and-deletion-policy-for-mailboxes-in-your-office-365-organization"></a><span data-ttu-id="ffdc4-103">設定 Office 365 組織中信箱的封存及刪除原則</span><span class="sxs-lookup"><span data-stu-id="ffdc4-103">Set up an archive and deletion policy for mailboxes in your Office 365 organization</span></span>

 <span data-ttu-id="ffdc4-104">**本文適用於系統管理員。想要新增至您的信箱中的項目封存和保留原則嗎？請參閱[將電子郵件的保留原則指派](https://support.office.com/article/3e5fd2dc-633f-4a38-b313-b31b81f7cf7a) | [企業網路上的 Outlook 中的保留和封存原則](https://support.office.com/article/465372e4-e16b-47db-bee0-aba44799085e)**</span><span class="sxs-lookup"><span data-stu-id="ffdc4-104">**This article is for administrators. Want to add archive and retention policies to items in your mailbox? See [Assign retention policy to email messages](https://support.office.com/article/3e5fd2dc-633f-4a38-b313-b31b81f7cf7a) | [Retention and archive policies in Outlook on the web for business](https://support.office.com/article/465372e4-e16b-47db-bee0-aba44799085e)**</span></span>
  
<span data-ttu-id="ffdc4-p101">在 Office 365 中，您可以建立的封存及刪除原則會自動將項目移至使用者的封存信箱與自動刪除信箱中的項目。您可以這麼做所建立的保留原則 ' s 後段特定時間內且也會刪除項目從信箱後達到特定存留期限制指派給信箱與使用者的封存信箱的移動項目。決定哪些項目已移動或刪除並發生該情況時所呼叫的保留標記實際規則。保留標記連結到接下來是指派給使用者的信箱的保留原則。保留標記會套用至個別郵件和使用者的信箱資料夾的保留設定。它會定義多久一則訊息仍會保留在信箱與郵件達到指定的保留時間時不會採取哪些動作。當郵件達到其保留期間時，它也會移至使用者的封存信箱或將其刪除。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-p101">In Office 365, you can create an archiving and deletion policy that automatically moves items to a user's archive mailbox and automatically deletes items from the mailbox. You can do this by creating a retention policy that' s assigned to mailboxes, and moves items to a user's archive mailbox after a certain period of time and that also deletes items from the mailbox after they reach a certain age limit. The actual rules that determine what items are moved or deleted and when that happens are called retention tags. Retention tags are linked to a retention policy, that in turn is assigned to a user's mailbox. A retention tag applies retention settings to individual messages and folders in a user's mailbox. It defines how long a message remains in the mailbox and what action is taken when the message reaches the specified retention age. When a message reaches its retention age, it's either moved to the user's archive mailbox or it's deleted.</span></span> 
  
<span data-ttu-id="ffdc4-p102">本主題中的步驟會設定名為 [高山門牌虛構組織封存和保留原則。設定此原則包含下列工作：</span><span class="sxs-lookup"><span data-stu-id="ffdc4-p102">The steps in this topic will set up an archiving and retention policy for a fictitious organization named Alpine House. Setting up this policy includes the following tasks:</span></span>
  
- <span data-ttu-id="ffdc4-p103">讓組織中的每位使用者的封存信箱。這讓使用者加入信箱儲存區，且需要以便將保留原則可將項目移至封存信箱。它也讓我們所移動的使用者存放區封存資訊的項目封存信箱。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-p103">Enabling an archive mailbox for every user in the organization. This gives users addition mailbox storage, and is required so that a retention policy can move items to the archive mailbox. It also let's a user store archival information by moving items to their archive mailbox.</span></span> 
    
- <span data-ttu-id="ffdc4-117">建立三個自訂的保留標記，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="ffdc4-117">Creating three custom retention tags that do the following:</span></span> 
    
  - <span data-ttu-id="ffdc4-p104">自動移動項目是 3 年舊使用者的封存信箱。將項目移至封存信箱釋出空間以使用者的主要信箱。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-p104">Automatically moves items that are 3 years old to the user's archive mailbox. Moving items to the archive mailbox frees up space in a user's primary mailbox.</span></span>
    
  - <span data-ttu-id="ffdc4-p105">自動刪除舊的 5 年是從 [刪除的郵件] 資料夾的項目。這也釋出空間以使用者的主要信箱。使用者必須有機會視復原這些項目。請參閱如需詳細資訊[的詳細資訊](set-up-an-archive-and-deletion-policy-for-mailboxes.md#moreinfo)] 區段中的註腳。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-p105">Automatically deletes items that are 5 years old from the Deleted Items folder. This also frees up space in the user's primary mailbox. User's will have the opportunity to recover these items if necessary. See the footnote in the [More information](set-up-an-archive-and-deletion-policy-for-mailboxes.md#moreinfo) section for more details.</span></span> 
    
  - <span data-ttu-id="ffdc4-p106">自動 （和永久） 會刪除舊來自這兩個主要的 7 年和封存信箱的項目。因為規範要求，而某些組織所需的一段時間保留電子郵件。這段時間到期後，組織可能會想要永久移除這些項目的使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-p106">Automatically (and permanently) deletes items that are 7 years old from both the primary and archive mailbox. Because of compliance regulations, some organization's are required to retain email for a certain period of time. After this time period expires, an organization might want to permanently remove these items user mailboxes.</span></span> 
    
- <span data-ttu-id="ffdc4-p107">建立新的保留原則並將新的自訂保留標籤加入至其中。此外，您也將內建的保留標記新增至新的保留原則。這包括個人標記的使用者可以將指派給他們的信箱中的項目。您也將會新增從使用者的主要信箱中的 [可復原的項目] 資料夾的項目移至封存信箱中 [可復原的項目] 資料夾的保留標記。這可幫助釋出空間中使用者的 [可復原的項目] 資料夾時他們的信箱處於保留狀態。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-p107">Creating a new retention policy and adding the new custom retention tags to it. Additionally, you'll also add built-in retention tags to the new retention policy. This includes personal tags that users can assign to items in their mailbox. You'll also add a retention tag that moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in their archive mailbox. This helps free up space in a user's Recoverable Items folder when their mailbox is placed on hold.</span></span>
    
<span data-ttu-id="ffdc4-p108">您可以遵循某些或所有本篇文章以設定您的組織中信箱的封存及刪除原則中的步驟。我們建議您實作在組織中所有信箱之前測試此程序在幾個信箱。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-p108">You can follow some or all of the steps in this article to set up an archive and deletion policy for mailboxes in your own organization. We recommend that you test this process on a few mailboxes before implementing it on all mailboxes in your organization.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="ffdc4-134">開始之前</span><span class="sxs-lookup"><span data-stu-id="ffdc4-134">Before you begin</span></span>

- <span data-ttu-id="ffdc4-135">您必須是 Office 365 組織中全域管理員，才能執行本主題中的步驟。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-135">You have to be a global administrator in your Office 365 organization to perform the steps in this topic.</span></span> 
    
-  <span data-ttu-id="ffdc4-p109">如果您在 Office 365 中建立新的使用者帳戶指派給使用者的 Exchange Online 授權，信箱會自動建立的使用者。建立信箱之後，其具有自動指派名為預設 MRM 原則的預設保留原則。在本文中，您會建立新的保留原則，然後將其指派給使用者的信箱，並取代預設 MRM 原則。信箱可以有指派給它在任何時候只有一個保留原則。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-p109">When you create a new user account in Office 365 and assign the user an Exchange Online license, a mailbox is automatically created for the user. When the mailbox is created, it's automatically assigned a default retention policy, named Default MRM Policy. In this article, you will create a new retention policy and then assign it to user mailboxes, replacing the Default MRM policy. A mailbox can have only one retention policy assigned to it at any one time.</span></span>
    
- <span data-ttu-id="ffdc4-140">若要深入了解保留標記和保留原則在 Exchange Online，請參閱[保留標記和保留原則](https://go.microsoft.com/fwlink/p/?LinkId=404424)。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-140">To learn more about retention tags and retention policies in Exchange Online, see [Retention tags and retention policies](https://go.microsoft.com/fwlink/p/?LinkId=404424).</span></span>
    
## <a name="step-1-enable-archive-mailboxes-for-users"></a><span data-ttu-id="ffdc4-141">步驟 1： 啟用封存信箱的使用者</span><span class="sxs-lookup"><span data-stu-id="ffdc4-141">Step 1: Enable archive mailboxes for users</span></span>

<span data-ttu-id="ffdc4-p110">第一個步驟是讓組織中每個使用者的封存信箱。具有使保留標記與 「 移到封存 」 保留動作可以移動項目保留期間到期後要啟用使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-p110">The first step is to enable the archive mailbox for each user in your organization. A user's archive mailbox has to be enabled so that a retention tag with a "Move to Archive" retention action can move the item after the retention age expires.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ffdc4-p111">可以啟用封存信箱的這個程序期間隨時剛才為他們正在之前完成程序啟用在某個時間點。如果未啟用封存信箱，任何已指派給它的封存原則的項目會不採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-p111">You can enable archive mailboxes any time during this process, just as long as they're enabled at some point before you complete the process. If an archive mailbox isn't enabled, no action is taken on any items that have an archive policy assigned to it.</span></span> 
  
1. <span data-ttu-id="ffdc4-146">移至 [ [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-146">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="ffdc4-147">登入 Office 365 全域管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-147">Sign in to Office 365 using your global administrator account.</span></span>
    
    
3. <span data-ttu-id="ffdc4-148">安全性&amp;規範管理中心，移至**資料控管** \> **封存**。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-148">In the Security &amp; Compliance Center, go to **Data governance** \> **Archive**.</span></span>
    
    <span data-ttu-id="ffdc4-149">顯示在組織中信箱的清單及對應的封存信箱是否啟用或停用。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-149">A list of the mailboxes in your organization is displayed and whether the corresponding archive mailbox is enabled or disabled.</span></span> 
    
4. <span data-ttu-id="ffdc4-150">依序按一下 [第一個清單中，按住**Shift**鍵，然後按一下清單中的最後一個選取所有的信箱。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-150">Select all the mailboxes by clicking on the first one in the list, holding down the **Shift** key, and then clicking the last one in the list.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="ffdc4-p112">這個步驟假設已啟用不封存信箱。有任何信箱以啟用封存，請按住**Ctrl**鍵並按一下 [已停用的封存信箱每個信箱。或者您可以按一下 [排序依據是否啟用或停用來讓您輕鬆將選取的信箱的封存信箱的資料列的 [**封存信箱**] 欄標題。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-p112">This step assumes that no archive mailboxes are enabled. If you have any mailboxes with the archive enabled, hold down the **Ctrl** key and click each mailbox that has a disabled archive mailbox. Or you can click the **Archive mailbox** column header to sort the rows based on whether the archive mailbox is enabled or disabled to make it easier to select mailboxes.</span></span> 
  
5. <span data-ttu-id="ffdc4-154">在 [詳細資料] 窗格中 [**大量編輯**] 下按一下 [**啟用**。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-154">In the details pane, under **Bulk Edit**, click **Enable**.</span></span>
    
    <span data-ttu-id="ffdc4-p113">會顯示一則警告預警超過兩個年度的項目將會移至新的封存信箱。這是因為預設保留原則在建立時指派新的使用者信箱已有 2 年的保留時間封存預設原則標記。您將在步驟 2 中建立的自訂封存預設原則標記有 3 年的保留期間。這表示 3 年的項目或更舊要移至封存信箱。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-p113">A warning is displayed saying that items that are older than two years will be moved to the new archive mailbox. This is because the default retention policy that's assigned a new user mailbox when it's created has an archive default policy tag that has a retention age of 2 years. The custom archive default policy tag that you'll create in Step 2 has a retention age of 3 years. That means items that are 3 years or older will be moved to the archive mailbox.</span></span>
    
6. <span data-ttu-id="ffdc4-159">按一下 [**是]** 以關閉警告訊息並啟動程序以啟用封存信箱的每個選取的信箱。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-159">Click **Yes** to close the warning message and start the process to enable the archive mailbox for each selected mailbox.</span></span> 
    
7. <span data-ttu-id="ffdc4-160">程序完成時，請按一下 [**重新整理**![重新整理](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png)更新 [**封存**] 頁面上的清單。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-160">When the process is complete, click **Refresh** ![refresh](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) to update the list on the **Archive** page.</span></span> 
    
    <span data-ttu-id="ffdc4-161">所有使用者的組織中已都啟用封存信箱。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-161">The archive mailbox is enabled for all user's in your organization.</span></span>
    
    ![啟用封存信箱與信箱清單](media/61a7cb97-1bed-4808-aa5f-b6b761cfa8de.png)
  
8. <span data-ttu-id="ffdc4-p114">保留安全性&amp;規範中心開啟。您將下一個步驟中使用它。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-p114">Leave the Security &amp; Compliance Center open. You'll use it in the next step.</span></span>
    
## <a name="step-2-create-new-retention-tags-for-the-archive-and-deletion-policies"></a><span data-ttu-id="ffdc4-165">步驟 2： 建立新的封存及刪除原則的保留標記</span><span class="sxs-lookup"><span data-stu-id="ffdc4-165">Step 2: Create new retention tags for the archive and deletion policies</span></span>

<span data-ttu-id="ffdc4-166">在此步驟中，您將建立先前所述的三個自訂的保留標記。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-166">In this step, you'll create the three custom retention tags that were previously described.</span></span>
  
- <span data-ttu-id="ffdc4-167">高山門牌 3 年移至封存 （自訂的封存原則）</span><span class="sxs-lookup"><span data-stu-id="ffdc4-167">Alpine House 3 Year Move to Archive (custom archive policy)</span></span>
    
- <span data-ttu-id="ffdc4-168">高山門牌 7 年永久刪除 （自訂的刪除原則）</span><span class="sxs-lookup"><span data-stu-id="ffdc4-168">Alpine House 7 Year Permanently Delete (custom deletion policy)</span></span>
    
- <span data-ttu-id="ffdc4-169">高山門牌刪除項目 5 年刪除並允許復原 （已刪除的項目] 資料夾的自訂標記）</span><span class="sxs-lookup"><span data-stu-id="ffdc4-169">Alpine House Deleted Items 5 Years Delete and Allow Recovery (custom tag for the Deleted Items folder)</span></span>
    
<span data-ttu-id="ffdc4-170">若要建立新的保留標記，您將 Exchange Online 組織中使用 Exchange 系統管理中心 (EAC)。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-170">To create new retention tags, you'll use the Exchange admin center (EAC) in your Exchange Online organization.</span></span>
  
1. <span data-ttu-id="ffdc4-171">安全性&amp;規範中心按一下左上角，在應用程式啟動器] 和 [**系統管理**並排顯示。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-171">In the Security &amp; Compliance Center, click the app launcher  in the upper left corner, and then click the **Admin** tile .</span></span> 
    
2. <span data-ttu-id="ffdc4-172">在 Office 365 系統管理中心的左的功能窗格、 [**系統置中**，和 [ **Exchange**。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-172">In the left navigation pane of the Office 365 admin center, click **Admin centers**, and then click **Exchange**.</span></span>
    
    ![這個螢幕擷取畫面顯示管理 Office 365 系統管理中心置中展開的選項和 Exchange 選取。](media/47399df2-0bc4-42e2-b183-07750a46bc68.png)
  
3. <span data-ttu-id="ffdc4-174">在 EAC 中，移至 [**規範管理** \> **保留標記**</span><span class="sxs-lookup"><span data-stu-id="ffdc4-174">In the EAC, go to **Compliance management** \> **Retention tags**</span></span>
    
    <span data-ttu-id="ffdc4-175">您的組織的保留標記清單隨即顯示。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-175">A list of the retention tags for your organization is displayed.</span></span>
    
### <a name="create-a-custom-archive-default-policy-tag"></a><span data-ttu-id="ffdc4-176">建立自訂的封存預設原則標記</span><span class="sxs-lookup"><span data-stu-id="ffdc4-176">Create a custom archive default policy tag</span></span>
  
<span data-ttu-id="ffdc4-177">首先，您將建立自訂的封存預設原則標記 (DPT) 可將郵件移至封存信箱在之後 3 年。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-177">First, you'll create a custom archive default policy tag (DPT) that will move items to the archive mailbox after 3 years.</span></span> 
  
1. <span data-ttu-id="ffdc4-178">在**保留標記**] 頁面上，按一下 [**新的 tag**![圖示](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)，然後選取 [**自動套用整個信箱 （預設值）**。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-178">On the **Retention tags** page, click **New tag**![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif), and then select **applied automatically to entire mailbox (default)**.</span></span> 
    
2. <span data-ttu-id="ffdc4-179">在**整個信箱 （預設值） 會自動套用的新標籤**] 頁面上，填妥下列欄位：</span><span class="sxs-lookup"><span data-stu-id="ffdc4-179">On the **New tag applied automatically to entire mailbox (default)** page, complete the following fields:</span></span> 
    
    ![若要建立新的封存預設原則標記的設定](media/41c0a43c-9c72-44e0-8947-da0831896432.png)
  
1. <span data-ttu-id="ffdc4-181">**名稱**輸入新的保留標記的名稱。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-181">**Name** Type a name for the new retention tag.</span></span> 
    
2. <span data-ttu-id="ffdc4-182">**保留動作**選取 [將項目移至封存信箱的保留期間到期時的 [**移至封存**]。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-182">**Retention action** Select **Move to Archive** to move items to the archive mailbox when the retention period expires.</span></span> 
    
3. <span data-ttu-id="ffdc4-p115">**保留期間**選取**此項目達到下列年齡 （天數） 時**，並再輸入 [持續時間內的保留期間。此案例中，項目要移至封存信箱後 1095 天 （3 年）。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-p115">**Retention period** Select **When the item reaches the following age (in days)**, and then enter the duration of the retention period. For this scenario, items will be moved to the archive mailbox after 1095 days (3 years).</span></span>
    
4. <span data-ttu-id="ffdc4-185">**註解**（選用）輸入說明自訂保留標記的用途的註解。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-185">**Comment** (Optional) Type a comment that explains the purpose of the custom retention tag.</span></span> 
    
3. <span data-ttu-id="ffdc4-186">按一下 [**儲存**] 以建立自訂的封存 DPT。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-186">Click **Save** to create the custom archive DPT.</span></span> 
    
    <span data-ttu-id="ffdc4-187">新的封存 DPT 會顯示在清單中的保留標記。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-187">The new archive DPT is displayed in the list of retention tags.</span></span>
    
### <a name="create-a-custom-deletion-default-policy-tag"></a><span data-ttu-id="ffdc4-188">建立自訂刪除預設原則標記</span><span class="sxs-lookup"><span data-stu-id="ffdc4-188">Create a custom deletion default policy tag</span></span>
  
<span data-ttu-id="ffdc4-189">接下來，您將建立另一個自訂 DPT 但以此會永久刪除項目之後 7 年的刪除原則。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-189">Next, you'll create another custom DPT but this one will be a deletion policy that permanently deletes items after 7 years.</span></span>
  
1. <span data-ttu-id="ffdc4-190">在**保留標記**] 頁面上，按一下 [**新的 tag**![圖示](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)，然後選取 [**自動套用整個信箱 （預設值）**。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-190">On the **Retention tags** page, click **New tag**![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif), and then select **applied automatically to entire mailbox (default)**.</span></span> 
    
2. <span data-ttu-id="ffdc4-191">在**整個信箱 （預設值） 會自動套用的新標籤**] 頁面上，填妥下列欄位：</span><span class="sxs-lookup"><span data-stu-id="ffdc4-191">On the **New tag applied automatically to entire mailbox (default)** page, complete the following fields:</span></span> 
    
    ![若要建立新的刪除預設原則標記的設定](media/f1f0ff62-eec9-4824-8e7c-d93dcfb09a79.png)
  
1. <span data-ttu-id="ffdc4-193">**名稱**輸入新的保留標記的名稱。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-193">**Name** Type a name for the new retention tag.</span></span> 
    
2. <span data-ttu-id="ffdc4-194">**保留動作**選取要保留期間到期時清除信箱中的項目**永久刪除**]。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-194">**Retention action** Select **Permanently Delete** to purge items from the mailbox when the retention period expires.</span></span> 
    
3. <span data-ttu-id="ffdc4-p116">**保留期間**選取**此項目達到下列年齡 （天數） 時**，並再輸入 [持續時間內的保留期間。此案例中，將 2555 天 （7 年） 後清除項目。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-p116">**Retention period** Select **When the item reaches the following age (in days)**, and then enter the duration of the retention period. For this scenario, items will be purged after 2555 days (7 years).</span></span>
    
4. <span data-ttu-id="ffdc4-197">**註解**（選用）輸入說明自訂保留標記的用途的註解。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-197">**Comment** (Optional) Type a comment that explains the purpose of the custom retention tag.</span></span> 
    
3. <span data-ttu-id="ffdc4-198">按一下 [**儲存**] 以建立自訂的刪除 DPT。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-198">Click **Save** to create the custom deletion DPT.</span></span> 
    
    <span data-ttu-id="ffdc4-199">新的刪除 DPT 會顯示在清單中的保留標記。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-199">The new deletion DPT is displayed in the list of retention tags.</span></span>
    
### <a name="create-a-custom-retention-policy-tag-for-the-deleted-items-folder"></a><span data-ttu-id="ffdc4-200">建立自訂的保留原則標記刪除項目] 資料夾</span><span class="sxs-lookup"><span data-stu-id="ffdc4-200">Create a custom retention policy tag for the Deleted Items folder</span></span>
  
<span data-ttu-id="ffdc4-p117">上次將建立的保留標記是自訂的保留原則標記 （印） 刪除的項目] 資料夾。此標籤將 5 年後刪除 [刪除的郵件] 資料夾中的項目，並提供當使用者可以使用復原刪除的郵件工具來復原的項目復原期間。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-p117">The last retention tag that you'll create is a custom retention policy tag (RPT) for the Deleted Items folder. This tag will delete items in the Deleted Items folder after 5 years, and provides a recovery period when users can use the Recover Deleted Items tool to recover an item.</span></span>
  
1. <span data-ttu-id="ffdc4-203">在**保留標記**] 頁面上，按一下 [**新的 tag** ![圖示](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)，然後選取 [**自動套用預設資料夾**。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-203">On the **Retention tags** page, click **New tag** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif), and then select **applied automatically to a default folder**.</span></span> 
    
2. <span data-ttu-id="ffdc4-204">在**自動套用預設資料夾的新標籤**] 頁面上，填妥下列欄位：</span><span class="sxs-lookup"><span data-stu-id="ffdc4-204">On the **New tag applied automatically to a default folder** page, complete the following fields:</span></span> 
    
    ![若要建立新的保留原則標記刪除項目] 資料夾的設定](media/6f3104bd-5edb-48ac-884d-5fe13d81dd1d.png)
  
1. <span data-ttu-id="ffdc4-206">**名稱**輸入新的保留標記的名稱。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-206">**Name** Type a name for the new retention tag.</span></span> 
    
2. <span data-ttu-id="ffdc4-207">**套用此標籤下的預設資料夾**在下拉式清單中，選取 [**刪除的項目**]。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-207">**Apply this tag to the following default folder** In the drop-down list, select **Deleted Items**.</span></span>
    
3. <span data-ttu-id="ffdc4-208">**保留動作**選取 [**刪除並允許復原**刪除的項目保留期間到期，但允許使用者刪除項目保留期間 （預設為 14 天） 中復原刪除的項目。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-208">**Retention action** Select **Delete and Allow Recovery** to delete items when the retention period expires, but allow users to recover a deleted item within the deleted item retention period (which by default is 14 days).</span></span> 
    
4. <span data-ttu-id="ffdc4-p118">**保留期間**選取**此項目達到下列年齡 （天數） 時**，並再輸入 [持續時間內的保留期間。此案例中，將 1825 天 （5 年） 後刪除項目。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-p118">**Retention period** Select **When the item reaches the following age (in days)**, and then enter the duration of the retention period. For this scenario, items will be deleted after 1825 days (5 years).</span></span>
    
5. <span data-ttu-id="ffdc4-211">**註解**（選用）輸入說明自訂保留標記的用途的註解。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-211">**Comment** (Optional) Type a comment that explains the purpose of the custom retention tag.</span></span> 
    
3. <span data-ttu-id="ffdc4-212">按一下 [**儲存**] 以建立自訂的印刪除項目] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-212">Click **Save** to create the custom RPT for the Deleted Items folder.</span></span> 
    
    <span data-ttu-id="ffdc4-213">新印會顯示在清單中的保留標記。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-213">The new RPT is displayed in the list of retention tags.</span></span>

## <a name="step-3-create-a-new-retention-policy"></a><span data-ttu-id="ffdc4-214">步驟 3： 建立新的保留原則</span><span class="sxs-lookup"><span data-stu-id="ffdc4-214">Step 3: Create a new retention policy</span></span>

<span data-ttu-id="ffdc4-p119">建立自訂的保留標記之後下, 一步是建立新的保留原則並新增保留標記。您將新增您在步驟 2 中建立的三個自訂的保留標記及第一節中所提及的內建標記。在步驟 4 中，您將使用者信箱指派這個新的保留原則。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-p119">After you create the custom retention tags, the next step is to create a new retention policy and add the retention tags. You'll add the three custom retention tags that you created in Step 2, and the built-in tags that were mentioned in the first section. In Step 4, you'll assign this new retention policy to user mailboxes.</span></span>
  
1. <span data-ttu-id="ffdc4-218">在 EAC 中，移至 [**規範管理** \> **保留原則**。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-218">In the EAC, go to **Compliance management** \> **Retention policies**.</span></span>
    
2. <span data-ttu-id="ffdc4-219">在 [**保留原則**] 頁面上，按一下 [**新增**![圖示](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-219">On the **Retention policies** page, click **New** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif).</span></span>
    
3. <span data-ttu-id="ffdc4-220">在 [**名稱**] 方塊中輸入新的保留原則 ； 的名稱例如，**高山門牌封存及刪除原則**。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-220">In the **Name** box, type a name for the new retention policy; for example, **Alpine House Archive and Deletion Policy**.</span></span> 
    
4. <span data-ttu-id="ffdc4-221">[**保留標記**，按一下 [**新增**![圖示](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-221">Under **Retention tags**, click **Add** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif).</span></span>
    
    <span data-ttu-id="ffdc4-p120">在組織中的保留標記清單隨即顯示。請注意您在步驟 2 中建立自訂標籤的顯示。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-p120">A list of the retention tags in your organization is displayed. Note the custom tags that you created in Step 2 are displayed.</span></span>
    
5. <span data-ttu-id="ffdc4-p121">新增要醒目提示的 9 保留標記中 （這些標記所述的[詳細資訊](set-up-an-archive-and-deletion-policy-for-mailboxes.md#moreinfo)] 區段中的更詳細地） 下列螢幕擷取畫面。若要新增其保留標記，加以選取並再按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-p121">Add the 9 retention tags that are highlighted in the following screenshot (these tags are described in more detail in the [More information](set-up-an-archive-and-deletion-policy-for-mailboxes.md#moreinfo) section). To add a retention tag, select it and then click **Add**.</span></span> 
    
    ![將保留標籤加入至新的保留原則](media/d8e87176-0716-4238-9e6a-7c4af35541dc.png)
  
    > [!TIP]
    > <span data-ttu-id="ffdc4-227">您可以選取多個保留標記按住**Ctrl**鍵，然後按一下 [每個標籤。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-227">You can select multiple retention tags by holding down the **Ctrl** key and then clicking each tag.</span></span> 
  
6. <span data-ttu-id="ffdc4-228">您已新增保留標記之後，請按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-228">After you've added the retention tags, click **OK**.</span></span>
    
7. <span data-ttu-id="ffdc4-229">在 [**新的保留原則**] 頁面上按一下 [**儲存**] 以建立新的原則。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-229">On the **New retention policy** page, click **Save** to create the new policy.</span></span> 
    
    <span data-ttu-id="ffdc4-p122">新的保留原則會顯示在清單中。選取以顯示連結至其詳細資料窗格中的保留標記。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-p122">The new retention policy is displayed in the list. Select it to display the retention tags linked to it in the details pane.</span></span>
    
    ![新的保留原則和連結的保留標記的清單](media/63bc45e6-110b-4dc9-a85f-8eb1961a8258.png)
  
## <a name="step-4-assign-the-new-retention-policy-to-user-mailboxes"></a><span data-ttu-id="ffdc4-233">步驟 4： 將新的保留原則指派給使用者的信箱</span><span class="sxs-lookup"><span data-stu-id="ffdc4-233">Step 4: Assign the new retention policy to user mailboxes</span></span>

<span data-ttu-id="ffdc4-p123">建立新的信箱之後，名為預設 MRM 原則的保留原則是預設指派給它。在此步驟中，您將會取代此保留原則 （因為信箱只能有一個保留原則指派給它） 指派新您在步驟 3 至使用者信箱組織中建立的保留原則。這個步驟假設您將在組織中所有信箱指派新原則。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-p123">When a new mailbox is created, a retention policy named Default MRM policy is assigned to it by default. In this step, you'll replace this retention policy (because a mailbox can have only one retention policy assigned to it) by assigning the new retention policy that you created in Step 3 to the user mailboxes in your organization. This step assumes that you'll assign the new policy to all mailboxes in your organization.</span></span>
  
1. <span data-ttu-id="ffdc4-237">在 EAC 中，前往 [收件者]****\>[信箱]****。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-237">In the EAC, go to **Recipients** \> **Mailboxes**.</span></span>
    
    <span data-ttu-id="ffdc4-238">在組織中的所有使用者信箱清單隨即顯示。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-238">A list of all user mailboxes in your organization is displayed.</span></span> 
    
2. <span data-ttu-id="ffdc4-239">依序按一下 [第一個清單中，按住**Shift**鍵，然後按一下清單中的最後一個選取所有的信箱。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-239">Select all the mailboxes by clicking on the first one in the list, holding down the **Shift** key, and then clicking the last one in the list.</span></span> 
    
3. <span data-ttu-id="ffdc4-240">在 EAC 中，[**大量編輯**] 下右邊的詳細資料窗格中按一下 [**更多選項**]。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-240">In the details pane on the right side of the EAC, under **Bulk Edit**, click **More options**.</span></span>
    
4. <span data-ttu-id="ffdc4-241">[**保留原則**] 下按一下 [**更新**]。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-241">Under **Retention Policy**, click **Update**.</span></span>
    
5. <span data-ttu-id="ffdc4-242">在 [**大量指派保留原則**] 頁面上**選取 [保留原則**] 下拉式清單中，選取您在步驟 3 ； 建立保留原則例如，**高山門牌封存與保留原則**。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-242">On the **Bulk assign retention policy** page, in the **Select the retention policy** drop-down list, select the retention policy that you created in Step 3; for example, **Alpine House Archive and Retention Policy**.</span></span>
    
6. <span data-ttu-id="ffdc4-243">按一下 [**儲存**] 以儲存新的保留原則指派]。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-243">Click **Save** to save the new retention policy assignment.</span></span> 
    
7. <span data-ttu-id="ffdc4-244">若要確認新的保留原則已指派給信箱，您可以執行下列動作： 選取 [信箱] 頁面上的信箱，然後按一下 [編輯。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-244">To verify that the new retention policy was assigned to mailboxes, you can do the following: select a mailbox on the Mailboxes page, and then click Edit.</span></span> 
    
1. <span data-ttu-id="ffdc4-245">選取 [**信箱**] 頁面上的信箱，然後按一下 [**編輯**![編輯](media/d7dc7e5f-17a1-4eb9-b42d-487db59e2e21.png)。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-245">Select a mailbox on the **Mailboxes** page, and then click **Edit** ![Edit](media/d7dc7e5f-17a1-4eb9-b42d-487db59e2e21.png).</span></span> 
    
2. <span data-ttu-id="ffdc4-246">在所選使用者信箱內容頁面上，按一下 [**信箱功能**]。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-246">On the mailbox properties page for the selected user, click **Mailbox features**.</span></span>
    
    <span data-ttu-id="ffdc4-247">新原則指派給信箱的名稱會顯示在 [**保留原則**] 下拉式清單中。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-247">The name of the new policy assigned to the mailbox is displayed in the **Retention policy** drop-down list.</span></span> 
    

  
## <a name="optional-step-5-run-the-managed-folder-assistant-to-apply-the-new-settings"></a><span data-ttu-id="ffdc4-248">（選用）步驟 5： 執行受管理的資料夾助理員來套用新的設定</span><span class="sxs-lookup"><span data-stu-id="ffdc4-248">(Optional) Step 5: Run the Managed Folder Assistant to apply the new settings</span></span>
<span data-ttu-id="ffdc4-249"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="ffdc4-249"></span></span>

<span data-ttu-id="ffdc4-p124">將新的保留原則套用至步驟 4 中的信箱之後，可能很 7 天在 Exchange Online 新的保留設定套用至信箱。這是因為程序呼叫的受管理的資料夾助理員的程序信箱一次每 7 天。而非等候受管理的資料夾助理員執行，您可以強制此執行發生在 Exchange Online PowerShell **Start-managedfolderassistant**指令程式。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-p124">After you apply the new retention policy to mailboxes in Step 4, it can take up to 7 days in Exchange Online for the new retention settings to be applied to the mailboxes. This is because a process called the Managed Folder Assistant processes mailboxes once every 7 days. Instead of waiting for the Managed Folder Assistant to run, you can force this to happen by running the the **Start-ManagedFolderAssistant** cmdlet in Exchange Online PowerShell.</span></span> 
  
 <span data-ttu-id="ffdc4-p125">**當您執行受管理的資料夾助理員會發生什麼事？** 檢查信箱中的項目，並決定是否它們受限於保留套用保留原則中的設定。它然後具有適當保留標記，標受限於保留的項目，然後採取指定的保留動作保留保留天數舊的項目。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-p125">**What happens when you run the Managed Folder Assistant?** It applies the settings in the retention policy by inspecting items in the mailbox and determining whether they're subject to retention. It then stamps items subject to retention with the appropriate retention tag, and then takes the specified retention action on items past their retention age.</span></span> 
  
<span data-ttu-id="ffdc4-256">以下是連線至 Exchange Online PowerShell 中，然後執行您組織中每個信箱上的 [受管理的資料夾助理員的步驟。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-256">Here are the steps to connect to Exchange Online PowerShell, and then run the Managed Folder Assistant on every mailbox in your organization.</span></span>
  
1. <span data-ttu-id="ffdc4-257">在您的本機電腦上開啟 Windows PowerShell，並執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-257">On your local computer, open Windows PowerShell and run the following command.</span></span>
    
    ```
    $UserCredential = Get-Credential
    ```

    <span data-ttu-id="ffdc4-258">在**Windows PowerShell 認證要求**] 對話方塊中，輸入使用者名稱與您的 Office 365 全域管理員帳戶的密碼並再按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-258">In the **Windows PowerShell Credential Request** dialog box, type the user name and password for your Office 365 global admin account, and then click **OK**.</span></span>
    
2. <span data-ttu-id="ffdc4-259">執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-259">Run the following command.</span></span>
    
    ```
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    ```

3. <span data-ttu-id="ffdc4-260">執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-260">Run the following command.</span></span>
    
    ```
    Import-PSSession $Session
    ```

4. <span data-ttu-id="ffdc4-261">若要確認您已連線至 Exchange Online 組織，執行下列命令以取得貴組織中所有信箱的清單：</span><span class="sxs-lookup"><span data-stu-id="ffdc4-261">To verify that you're connected to your Exchange Online organization, run the following command to get a list of all the mailboxes in your organization.</span></span>
    
    ```
    Get-Mailbox
    ```

    > [!NOTE]
    > <span data-ttu-id="ffdc4-262">如需詳細資訊或如果您無法連線到您的 Exchange Online 組織，請參閱[使用遠端 PowerShell 連線到 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=517283)。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-262">For more information or if you have problems connecting to your Exchange Online organization, see [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283).</span></span> 
  
5. <span data-ttu-id="ffdc4-263">執行下列兩個命令，以啟動 [在組織中的 [受管理的資料夾助理員的所有使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-263">Run the following two commands to start the Managed Folder Assistant for all user mailboxes in your organization.</span></span>
    
    ```
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    ```

    ```
    $Mailboxes.Identity | Start-ManagedFolderAssistant
    ```

<span data-ttu-id="ffdc4-p126">這是它 ！您已設定高山門牌組織封存及刪除原則。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-p126">That's it! You've set up an archive and deletion policy for the Alpine House organization.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="ffdc4-266">其他資訊</span><span class="sxs-lookup"><span data-stu-id="ffdc4-266">More information</span></span>
<span data-ttu-id="ffdc4-267"><a name="moreinfo"> </a></span><span class="sxs-lookup"><span data-stu-id="ffdc4-267"></span></span>

- <span data-ttu-id="ffdc4-p127">計算保留時間的方式信箱項目保留期間的計算傳遞的日期或建立日期等草稿未傳送的郵件項目，但使用者所建立的。受管理的資料夾助理員處理信箱中的項目、 時加上戳記開始日期和到期的所有具有與刪除並允許復原] 或 [永久刪除保留動作的保留標記的項目。已封存標記的項目是 move date 加上戳記。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-p127">How is retention age calculated? The retention age of mailbox items is calculated from the date of delivery or the date of creation for items such as draft messages that aren't sent but are created by the user. When the Managed Folder Assistant processes items in a mailbox, it stamps a start date and an expiration date for all items that have retention tags with the Delete and Allow Recovery or Permanently Delete retention action. Items that have an archive tag are stamped with a move date.</span></span> 
    
- <span data-ttu-id="ffdc4-272">下表提供每個新增至自訂的保留原則是由遵循本主題中所建立的保留標記的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-272">The following table provides more information about each retention tag that is added to the custom retention policy that was created by following the steps in this topic.</span></span>
    
    |<span data-ttu-id="ffdc4-273">**保留標記**</span><span class="sxs-lookup"><span data-stu-id="ffdc4-273">**Retention tag**</span></span>|<span data-ttu-id="ffdc4-274">**此標籤的沒有**</span><span class="sxs-lookup"><span data-stu-id="ffdc4-274">**What this tag does**</span></span>|<span data-ttu-id="ffdc4-275">**內建或自訂？**</span><span class="sxs-lookup"><span data-stu-id="ffdc4-275">**Built-in or custom?**</span></span>|<span data-ttu-id="ffdc4-276">**類型**</span><span class="sxs-lookup"><span data-stu-id="ffdc4-276">**Type**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ffdc4-277">高山門牌 3 年移至封存</span><span class="sxs-lookup"><span data-stu-id="ffdc4-277">Alpine House 3 Year Move to Archive</span></span>  <br/> |<span data-ttu-id="ffdc4-278">會移動 1095 天 （3 年） 至封存信箱的項目。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-278">Moves items that are 1095 days (3 years) old to the archive mailbox.</span></span>  <br/> |<span data-ttu-id="ffdc4-279">自訂 (請參閱[步驟 2： 建立新的封存及刪除原則的保留標記](set-up-an-archive-and-deletion-policy-for-mailboxes.md#step3))</span><span class="sxs-lookup"><span data-stu-id="ffdc4-279">Custom (See [Step 2: Create new retention tags for the archive and deletion policies](set-up-an-archive-and-deletion-policy-for-mailboxes.md#step3) )</span></span>  <br/> |<span data-ttu-id="ffdc4-280">預設原則標記 （封存）;此標籤會自動套用至整個信箱。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-280">Default Policy Tag (archive); this tag is automatically applied to the entire mailbox.</span></span>  <br/> |
    |<span data-ttu-id="ffdc4-281">高山門牌 7 年永久刪除</span><span class="sxs-lookup"><span data-stu-id="ffdc4-281">Alpine House 7 Year Permanently Delete</span></span>  <br/> |<span data-ttu-id="ffdc4-282">永久刪除主要信箱或封存信箱中的項目時發出 7 年舊。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-282">Permanently deletes items in the primary mailbox or the archive mailbox when they are 7 years old.</span></span>  <br/> |<span data-ttu-id="ffdc4-283">自訂 (請參閱[步驟 2： 建立新的封存及刪除原則的保留標記](set-up-an-archive-and-deletion-policy-for-mailboxes.md#step3))</span><span class="sxs-lookup"><span data-stu-id="ffdc4-283">Custom (See [Step 2: Create new retention tags for the archive and deletion policies](set-up-an-archive-and-deletion-policy-for-mailboxes.md#step3) )</span></span>  <br/> |<span data-ttu-id="ffdc4-284">預設原則標記 （刪除）;此標籤會自動套用至整個信箱。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-284">Default Policy Tag (deletion); this tag is automatically applied to the entire mailbox.</span></span>  <br/> |
    |<span data-ttu-id="ffdc4-285">高山門牌刪除項目 5 年刪除並允許復原</span><span class="sxs-lookup"><span data-stu-id="ffdc4-285">Alpine House Deleted Items 5 Years Delete and Allow Recovery</span></span>  <br/> |<span data-ttu-id="ffdc4-p128">是舊 5 年刪除的郵件資料夾刪除項目。使用者可復原設定在刪除後的 14 天這些項的目。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ffdc4-p128">Deletes items from the Deleted Items folder that are 5 years old. Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="ffdc4-288">自訂 (請參閱[步驟 2： 建立新的封存及刪除原則的保留標記](set-up-an-archive-and-deletion-policy-for-mailboxes.md#step3))</span><span class="sxs-lookup"><span data-stu-id="ffdc4-288">Custom (See [Step 2: Create new retention tags for the archive and deletion policies](set-up-an-archive-and-deletion-policy-for-mailboxes.md#step3) )</span></span>  <br/> |<span data-ttu-id="ffdc4-289">保留原則標記 （已刪除項目）;此標籤會自動套用到 [刪除的項目] 資料夾中的項目。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-289">Retention Policy Tag (Deleted Items); this tag is automatically applied to items in the Deleted items folder.</span></span>  <br/> |
    |<span data-ttu-id="ffdc4-290">可復原的項目 14 天移至封存</span><span class="sxs-lookup"><span data-stu-id="ffdc4-290">Recoverable Items 14 days Move to Archive</span></span>  <br/> |<span data-ttu-id="ffdc4-291">移至封存信箱中 [可復原的項目] 資料夾的 14 天內都已在 [可復原的項目] 資料夾中的項目。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-291">Moves items that have been in the Recoverable Items folder for 14 days to the Recoverable Items folder in the archive mailbox.</span></span>  <br/> |<span data-ttu-id="ffdc4-292">內建</span><span class="sxs-lookup"><span data-stu-id="ffdc4-292">Built-in</span></span>  <br/> |<span data-ttu-id="ffdc4-293">保留原則標記 （可復原的項目）;此標籤會自動套用到可復原的項目] 資料夾中的項目。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-293">Retention Policy Tag (Recoverable Items); this tag is automatically applied to items in the Recoverable Items folder.</span></span>  <br/> |
    |<span data-ttu-id="ffdc4-294">垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="ffdc4-294">Junk Email</span></span>  <br/> |<span data-ttu-id="ffdc4-p129">永久刪除已在垃圾郵件] 資料夾中的 30 天的項目。使用者可復原設定在刪除後的 14 天這些項的目。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ffdc4-p129">Permanently deletes items that have been in the Junk Email folder for 30 days. Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="ffdc4-297">內建</span><span class="sxs-lookup"><span data-stu-id="ffdc4-297">Built-in</span></span>  <br/> |<span data-ttu-id="ffdc4-298">保留原則標記 （垃圾郵件）;此標籤會自動套用到垃圾郵件] 資料夾中的項目。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-298">Retention Policy Tag (Junk Email); this tag is automatically applied to items in Junk Email folder.</span></span>  <br/> |
    |<span data-ttu-id="ffdc4-299">1 個月刪除</span><span class="sxs-lookup"><span data-stu-id="ffdc4-299">1 Month Delete</span></span>  <br/> |<span data-ttu-id="ffdc4-p130">永久刪除 30 天的項目。使用者可復原設定在刪除後的 14 天這些項的目。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ffdc4-p130">Permanently deletes items that are 30 days old. Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="ffdc4-302">內建</span><span class="sxs-lookup"><span data-stu-id="ffdc4-302">Built-in</span></span>  <br/> |<span data-ttu-id="ffdc4-303">個人;使用者可以套用此標籤。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-303">Personal; this tag can be applied by users.</span></span>  <br/> |
    |<span data-ttu-id="ffdc4-304">1 年刪除</span><span class="sxs-lookup"><span data-stu-id="ffdc4-304">1 Year Delete</span></span>  <br/> |<span data-ttu-id="ffdc4-p131">永久刪除 365 天的項目。使用者可復原設定在刪除後的 14 天這些項的目。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ffdc4-p131">Permanently deletes items that are 365 days old. Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="ffdc4-307">內建</span><span class="sxs-lookup"><span data-stu-id="ffdc4-307">Built-in</span></span>  <br/> |<span data-ttu-id="ffdc4-308">個人;使用者可以套用此標籤。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-308">Personal; this tag can be applied by users.</span></span>  <br/> |
    |<span data-ttu-id="ffdc4-309">永不刪除</span><span class="sxs-lookup"><span data-stu-id="ffdc4-309">Never Delete</span></span>  <br/> |<span data-ttu-id="ffdc4-310">此標籤避免保留原則所要刪除的項目。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-310">This tag prevent items from being deleted by a retention policy.</span></span>  <br/> |<span data-ttu-id="ffdc4-311">內建</span><span class="sxs-lookup"><span data-stu-id="ffdc4-311">Built-in</span></span>  <br/> |<span data-ttu-id="ffdc4-312">個人;使用者可以套用此標籤。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-312">Personal; this tag can be applied by users.</span></span>  <br/> |
    |<span data-ttu-id="ffdc4-313">個人 1 年移至封存</span><span class="sxs-lookup"><span data-stu-id="ffdc4-313">Personal 1 year move to archive</span></span>  <br/> |<span data-ttu-id="ffdc4-314">1 年後中移至封存信箱項目。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-314">Moves items to the archive mailbox after 1 year.</span></span>  <br/> |<span data-ttu-id="ffdc4-315">內建</span><span class="sxs-lookup"><span data-stu-id="ffdc4-315">Built-in</span></span>  <br/> |<span data-ttu-id="ffdc4-316">個人;使用者可以套用此標籤。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-316">Personal; this tag can be applied by users.</span></span>  <br/> |
   
    > <span data-ttu-id="ffdc4-p132"><sup>\*</sup>使用者可以使用 Outlook 和 Outlook Web App 中復原刪除的郵件工具在刪除項目保留期間內，其預設值為 14 天在 Exchange Online 中復原刪除的項目。系統管理員可以使用 Windows PowerShell 來增加最大值為 30 天內刪除項目保留期間。如需詳細資訊，請參閱：[復原已刪除的 Outlook for Windows 中的項目](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)及[變更 Exchange Online 信箱的刪除項目保留期間](https://go.microsoft.com/fwlink/p/?LinkId=286940)</span><span class="sxs-lookup"><span data-stu-id="ffdc4-p132"><sup>\*</sup> Users can use the Recover Deleted Items tool in Outlook and Outlook Web App to recover a deleted item within the deleted item retention period, which by default is 14 days in Exchange Online. An administrator can use Windows PowerShell to increase the deleted item retention period to a maximum of 30 days. For more information, see: [Recover deleted items in Outlook for Windows](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce) and [Change the deleted item retention period for a mailbox in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286940)</span></span>
  
- <span data-ttu-id="ffdc4-p133">使用 [**可復原的項目 14 天移至封存**保留標籤有助於免費中使用者的主要信箱 [可復原的項目] 資料夾中的儲存空間。這在使用者信箱處於保留狀態，這表示不屬於永久刪除使用者信箱時很有用。不將項目移至封存信箱，很可能會達到儲存配額主要信箱中的 [可復原的項目] 資料夾。如需此憑證與如何避免它的詳細資訊，請參閱[增加保留上的信箱配額可復原的項目](https://go.microsoft.com/fwlink/p/?LinkId=786479)。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-p133">Using the **Recoverable Items 14 days Move to Archive** retention tag helps free up storage space in the Recoverable Items folder in the user's primary mailbox. This is useful when a user's mailbox is placed on hold, which means nothing is ever permanently deleted the user's mailbox. Without moving items to the archive mailbox, it's possible the storage quota for the Recoverable Items folder in the primary mailbox will be reached. For more information about this and how to avoid it, see [Increase the Recoverable Items quota for mailboxes on hold](https://go.microsoft.com/fwlink/p/?LinkId=786479).</span></span>