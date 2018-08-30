---
title: 在 Office 365 中建立訴訟暫止狀態
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 39db1659-0b12-4243-a21c-2614512dcb44
ms.openlocfilehash: 18b3b3a42e5671b1507522c89faaa4ae34198831
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22527150"
---
# <a name="create-a-litigation-hold-in-office-365"></a><span data-ttu-id="6cd21-102">在 Office 365 中建立訴訟暫止狀態</span><span class="sxs-lookup"><span data-stu-id="6cd21-102">Create a Litigation Hold in Office 365</span></span>

<span data-ttu-id="6cd21-p101">將信箱置於訴訟暫止狀態保留所有信箱內容，包括已刪除的項目和已修改項目的原始版本。您將使用者信箱置於訴訟暫止狀態，使用者的封存信箱中的內容 （如果已啟用） 是也會保留。當您建立保留時，您可以指定保留期間 （也稱為*時間型保留*） 使刪除及修改過的項目會在指定期間內保留與永久刪除信箱。您可以只會無限期保留內容或者 （稱為*無限保留*） 或直到訴訟暫止狀態已移除。如果您指定保留持續時間期間，它會計算日期接收郵件或建立信箱項目。</span><span class="sxs-lookup"><span data-stu-id="6cd21-p101">You can place a mailbox on Litigation Hold to retain all mailbox content, including deleted items and the original versions of modified items. When you place a user mailbox on Litigation Hold, content in the user's archive mailbox (if it's enabled) is also retained. When you create a hold, you can specify a hold duration (also called a *time-based hold*) so that deleted and modified items are retained for a specified period and then permanently deleted from the mailbox. Or you can just retain content indefinitely (called an *infinite hold*) or until the Litigation Hold is removed. If you do specify a hold duration period, it's calculated from the date a message is received or a mailbox item is created.</span></span> 
  
<span data-ttu-id="6cd21-108">以下是您建立訴訟暫止狀態時會發生什麼情況。</span><span class="sxs-lookup"><span data-stu-id="6cd21-108">Here's what happens when you create a Litigation Hold.</span></span>
  
- <span data-ttu-id="6cd21-109">永久刪除之使用者的項目會保留在使用者的信箱 [可復原的項目] 資料夾中的保留期間。</span><span class="sxs-lookup"><span data-stu-id="6cd21-109">Items that are permanently deleted by the user are retained in the Recoverable Items folder in the user's mailbox for the duration of the hold.</span></span>
    
- <span data-ttu-id="6cd21-110">會在使用者將從 [可復原的項目] 資料夾清除的項目都會保留的保留期間。</span><span class="sxs-lookup"><span data-stu-id="6cd21-110">Items that are purged from the Recoverable Items folder by the user are retained for the duration of the hold.</span></span>
    
- <span data-ttu-id="6cd21-111">儲存配額可復原的項目] 資料夾是從 30 GB 增加為 110 GB。</span><span class="sxs-lookup"><span data-stu-id="6cd21-111">The storage quota for the Recoverable Items folder is increased from 30 GB to 110 GB.</span></span>
    
- <span data-ttu-id="6cd21-112">在使用者的主要和封存信箱中的項目保留</span><span class="sxs-lookup"><span data-stu-id="6cd21-112">Items in the user's primary and the archive mailboxes are retained</span></span>
    
## <a name="before-you-begin"></a><span data-ttu-id="6cd21-113">開始之前</span><span class="sxs-lookup"><span data-stu-id="6cd21-113">Before you begin</span></span>

- <span data-ttu-id="6cd21-p102">Exchange Online 的信箱置於訴訟暫止狀態，它必須被指派 Exchange Online 計劃 2 授權。如果信箱指派 Exchange Online 計劃 1 授權，您必須將其放入個別 Exchange Online 封存授權保留指派。</span><span class="sxs-lookup"><span data-stu-id="6cd21-p102">To place an Exchange Online mailbox on Litigation Hold, it must be assigned an Exchange Online Plan 2 license. If a mailbox is assigned an Exchange Online Plan 1 license, you would have to assign it a separate Exchange Online Archiving license to place it on hold.</span></span>
    

## <a name="place-a-mailbox-on-litigation-hold-in-the-office-365-admin-center"></a><span data-ttu-id="6cd21-116">將信箱置於訴訟保留在 Office 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="6cd21-116">Place a mailbox on Litigation Hold in the Office 365 admin center</span></span>

<span data-ttu-id="6cd21-117">以下是置於訴訟暫止狀態使用 Office 365 系統管理中心信箱的步驟。</span><span class="sxs-lookup"><span data-stu-id="6cd21-117">Here are the steps to place a maibox on Litigation Hold using the Office 365 admin center.</span></span>

1. <span data-ttu-id="6cd21-118">移至 [https://portal.office.com/adminportal/home並使用您的全域管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="6cd21-118">Go to https://portal.office.com/adminportal/home and sign in using your global administrator account.</span></span>
2. <span data-ttu-id="6cd21-119">按一下 [**使用者** > 的左的功能窗格中的**作用中使用者**。</span><span class="sxs-lookup"><span data-stu-id="6cd21-119">Click **Users** > **Active users** in the left navigation pane.</span></span>
3. <span data-ttu-id="6cd21-120">選取您想要置於訴訟保留其信箱的使用者。</span><span class="sxs-lookup"><span data-stu-id="6cd21-120">Select the user whose mailbox you want to place on Litigation Hold.</span></span>
4. <span data-ttu-id="6cd21-121">彈出式] 索引標籤上 [**郵件設定**] 和 [**訴訟暫止狀態**] 旁的 [**編輯**。</span><span class="sxs-lookup"><span data-stu-id="6cd21-121">On the fly-out page, click **Mail settings**, and then click **Edit** next to **Litigation hold**.</span></span>
5. <span data-ttu-id="6cd21-122">在**訴訟暫止狀態**] 頁面上按一下 [開啟訴訟暫止狀態並完成會顯示下列選用設定切換：</span><span class="sxs-lookup"><span data-stu-id="6cd21-122">On the **Litigation hold** page, click the toggle to turn on Litigation Hold and complete the following optional settings that are displayed:</span></span>
 
    ![O365_LitigationHold1.png](media/O365-LitigationHold1.png)

    <span data-ttu-id="6cd21-p103">a.**保留期間 （天）** -使用此方塊來建立時間型保留與指定信箱處於訴訟暫止狀態時，長保留信箱項目。信箱項目會接收或建立日期被計算持續時間。如果您保留此方塊空白，項目會保留無限期或直到移除保留為止。用於持續時間指定天數。</span><span class="sxs-lookup"><span data-stu-id="6cd21-p103">a. **Hold duration (days)** - Use this box to create a time-based hold and specify how long mailbox items are held when the mailbox is placed on Litigation Hold. The duration is calculated from the date a mailbox item is received or created. If you leave this box blank, items are held indefinitely or until the hold is removed. Use days to specify the duration.</span></span>
    
    <span data-ttu-id="6cd21-p104">b.**附註**-使用此方塊來通知的使用者他們的信箱處於訴訟暫止狀態。附註如果將會出現在使用者的信箱中的 [帳戶資訊] 頁面上所使用的 Outlook 2010 或更新版本。若要存取此頁面上，使用者可以按一下 [在 Outlook 中的**檔案**。</span><span class="sxs-lookup"><span data-stu-id="6cd21-p104">b. **Note** - Use this box to inform the user their mailbox is on Litigation Hold. The note will appear on the Account Information page in the user's mailbox if they're using Outlook 2010 or later. To access this page, users can click **File** in Outlook.</span></span>
     
    <span data-ttu-id="6cd21-p105">c. **Web 頁面**-使用此方塊可將使用者導向至訴訟暫止狀態的詳細資訊的網站。如果其於使用 Outlook 2010 或更新版本上使用者的信箱中的 [帳戶資訊] 頁面上會出現此 URL。若要存取此頁面上，使用者可以按一下 [在 Outlook 中的**檔案**。</span><span class="sxs-lookup"><span data-stu-id="6cd21-p105">c. **Web page** - Use this box to direct the user to a website for more information about Litigation Hold. This URL appears on the Account Information page in the user's mailbox if they are using Outlook 2010 or later. To access this page, users can click **File** in Outlook.</span></span>
 
6. <span data-ttu-id="6cd21-137">按一下 [**儲存**] 以建立訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="6cd21-137">Click **Save** to create the Litigation Hold.</span></span>

<span data-ttu-id="6cd21-138">建立保留之後，在彈出式] 頁面上的信箱設定會顯示的訴訟暫止狀態在已開啟選取的使用者。</span><span class="sxs-lookup"><span data-stu-id="6cd21-138">After you create the hold, the mail settings on the fly-out page shows that Litigation Hold is turned on for the selected user.</span></span>

![O365_LitigationHold2.png](media/O365-LitigationHold2.png)

<span data-ttu-id="6cd21-140">如需建立及管理訴訟保留及使用 Exchange Online PowerShell 大量建立訴訟保留的詳細資訊，請參閱[Place 在訴訟暫止狀態的信箱](https://docs.microsoft.com/office365/SecurityCompliance/place-a-mailbox-on-litigation-hold)。</span><span class="sxs-lookup"><span data-stu-id="6cd21-140">For more information about creating and managing Litigation Holds and using Exchange Online PowerShell to bulk-create Litigation Holds, see [Place a mailbox on Litigation Hold](https://docs.microsoft.com/office365/SecurityCompliance/place-a-mailbox-on-litigation-hold).</span></span>
