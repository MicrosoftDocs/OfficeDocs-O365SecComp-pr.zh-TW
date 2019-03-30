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
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2019
ms.locfileid: "31000266"
---
# <a name="search-for-and-delete-email-messages-in-your-office-365-organization---admin-help"></a><span data-ttu-id="8117d-103">搜尋並刪除 Office 365 組織的系統管理說明中的電子郵件</span><span class="sxs-lookup"><span data-stu-id="8117d-103">Search for and delete email messages in your Office 365 organization - Admin Help</span></span>

<span data-ttu-id="8117d-104">**本文適用於系統管理員。您試圖尋找您想要刪除的信箱中的項目？請參閱[尋找郵件或在使用立即搜尋的項目](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)**|</span><span class="sxs-lookup"><span data-stu-id="8117d-104">**This article is for administrators. Are you trying to find items in your mailbox that you want to delete? See [Find a message or item with Instant Search](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)**|</span></span>
   
<span data-ttu-id="8117d-105">您可以使用 Office 365 中的 「 內容搜尋 」 功能來搜尋並刪除所有的信箱中的電子郵件訊息，您組織中。</span><span class="sxs-lookup"><span data-stu-id="8117d-105">You can use the Content Search feature in Office 365 to search for and delete an email message from all mailboxes in your organization.</span></span> <span data-ttu-id="8117d-106">這可協助您尋找並移除可能有害或高風險的電子郵件，例如：</span><span class="sxs-lookup"><span data-stu-id="8117d-106">This can help you find and remove potentially harmful or high-risk email, such as:</span></span>
  
- <span data-ttu-id="8117d-107">包含危險附件或病毒的郵件</span><span class="sxs-lookup"><span data-stu-id="8117d-107">Messages that contain dangerous attachments or viruses</span></span>
    
- <span data-ttu-id="8117d-108">網路釣魚郵件</span><span class="sxs-lookup"><span data-stu-id="8117d-108">Phishing messages</span></span>
    
- <span data-ttu-id="8117d-109">包含敏感資料的郵件</span><span class="sxs-lookup"><span data-stu-id="8117d-109">Messages that contain sensitive data</span></span>
    
> [!CAUTION]
> <span data-ttu-id="8117d-110">搜尋及清除是一個強大的功能，可讓任何人都被指派來自您組織中的信箱刪除電子郵件訊息的必要權限。</span><span class="sxs-lookup"><span data-stu-id="8117d-110">Search and purge is a powerful feature that allows anyone that is assigned the necessary permissions to delete email messages from mailboxes in your organization.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="8117d-111">開始之前</span><span class="sxs-lookup"><span data-stu-id="8117d-111">Before you begin</span></span>

- <span data-ttu-id="8117d-112">若要建立並執行內容搜尋，您必須是 「 **eDiscovery 管理員**」 角色群組的成員，或被指派 「**符合性搜尋**管理 」 角色。</span><span class="sxs-lookup"><span data-stu-id="8117d-112">To create and run a Content Search, you have to be a member of the **eDiscovery Manager** role group or be assigned the **Compliance Search** management role.</span></span> <span data-ttu-id="8117d-113">若要刪除的郵件，您必須是 「**組織管理**」 角色群組的成員，或是獲指派 「**搜尋及清除**的管理角色。</span><span class="sxs-lookup"><span data-stu-id="8117d-113">To delete messages, you have to be a member of the **Organization Management** role group or be assigned the **Search And Purge** management role.</span></span> <span data-ttu-id="8117d-114">如需將使用者新增至角色群組的詳細資訊，請參閱[讓使用者能夠存取安全性與合規性中心](grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="8117d-114">For information about adding users to a role group, see [Give users access to the security and compliance center](grant-access-to-the-security-and-compliance-center.md).</span></span>
    
- <span data-ttu-id="8117d-115">您必須使用安全性 & 合規性中心 PowerShell 來刪除郵件。</span><span class="sxs-lookup"><span data-stu-id="8117d-115">You have to use Security & Compliance Center PowerShell to delete messages.</span></span> <span data-ttu-id="8117d-116">如需如何連線指示，請參閱[步驟 2](#step-2-connect-to-security--compliance-center-powershell) 。</span><span class="sxs-lookup"><span data-stu-id="8117d-116">See [Step 2](#step-2-connect-to-security--compliance-center-powershell) for instructions about how to connect.</span></span>
    
- <span data-ttu-id="8117d-117">每個信箱的 10 個項目最多可以一次移除。</span><span class="sxs-lookup"><span data-stu-id="8117d-117">A maximum of 10 items per mailbox can be removed at one time.</span></span> <span data-ttu-id="8117d-118">因為搜尋和移除郵件的功能應該是事件回應工具，此限制可以協助確保從信箱快速移除郵件。</span><span class="sxs-lookup"><span data-stu-id="8117d-118">Because the capability to search for and remove messages is intended to be an incident-response tool, this limit helps ensure that messages are quickly removed from mailboxes.</span></span> <span data-ttu-id="8117d-119">這項功能不是用來清除使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="8117d-119">This feature isn't intended to clean up user mailboxes.</span></span> <span data-ttu-id="8117d-120">若要刪除超過 10 個項目，您可以在 Exchange Online PowerShell 中使用**Search-mailbox DeleteContent**命令。</span><span class="sxs-lookup"><span data-stu-id="8117d-120">To delete more than 10 items, you can use the **Search-Mailbox -DeleteContent** command in Exchange Online PowerShell.</span></span> <span data-ttu-id="8117d-121">請參閱[搜尋並刪除郵件-系統管理說明](search-for-and-delete-messagesadmin-help.md)。</span><span class="sxs-lookup"><span data-stu-id="8117d-121">See [Search for and delete messages - Admin help](search-for-and-delete-messagesadmin-help.md).</span></span>
    
- <span data-ttu-id="8117d-122">您可以用來執行搜尋刪除的項目，並清除巨集指令在內容搜尋的信箱數目上限為 50000。</span><span class="sxs-lookup"><span data-stu-id="8117d-122">The maximum number of mailboxes in a Content Search that you can delete items in by doing a search and purge action is 50,000.</span></span> <span data-ttu-id="8117d-123">如果內容搜尋 （您在[步驟 1](#step-1-create-a-content-search-to-find-the-message-to-delete)中建立） 有超過 50000 個來源信箱，將會失敗的清除動作 （您在步驟 3 中建立）。</span><span class="sxs-lookup"><span data-stu-id="8117d-123">If the Content Search (that you create in [Step 1](#step-1-create-a-content-search-to-find-the-message-to-delete)) has more than 50,000 source mailboxes, the purge action (that you create in Step 3) will fail.</span></span> <span data-ttu-id="8117d-124">請參閱上執行搜尋祕訣[的詳細資訊](#more-information)一節，並清除超過 50000 個信箱上的作業。</span><span class="sxs-lookup"><span data-stu-id="8117d-124">See the [More information](#more-information) section for a tip on performing a search and purge operation on more than 50,000 mailboxes.</span></span> 
    
- <span data-ttu-id="8117d-125">本文中的程序只可以用來刪除 Exchange Online 信箱和公用資料夾中的項目。</span><span class="sxs-lookup"><span data-stu-id="8117d-125">The procedure in this article can only be used to delete items in Exchange Online mailboxes and public folders.</span></span> <span data-ttu-id="8117d-126">您無法使用它來刪除內容從 SharePoint 或 OneDrive for Business 網站。</span><span class="sxs-lookup"><span data-stu-id="8117d-126">You can't use it to delete content from SharePoint or OneDrive for Business sites.</span></span>
    
## <a name="step-1-create-a-content-search-to-find-the-message-to-delete"></a><span data-ttu-id="8117d-127">步驟 1：建立內容搜尋來尋找要刪除的郵件</span><span class="sxs-lookup"><span data-stu-id="8117d-127">Step 1: Create a Content Search to find the message to delete</span></span>

<span data-ttu-id="8117d-128">第一個步驟是建立和執行內容搜尋，以尋找您想要從組織中的信箱移除的郵件。</span><span class="sxs-lookup"><span data-stu-id="8117d-128">The first step is to create and run a Content Search to find the message that you want to remove from mailboxes in your organization.</span></span> <span data-ttu-id="8117d-129">使用安全性 & 合規性中心，或執行**New-compliancesearch**和**Start-compliancesearch** cmdlet，您可以建立搜尋。</span><span class="sxs-lookup"><span data-stu-id="8117d-129">You can create the search by using the Security & Compliance Center or by running the **New-ComplianceSearch** and **Start-ComplianceSearch** cmdlets.</span></span> <span data-ttu-id="8117d-130">針對此搜尋將會執行刪除符合查詢的郵件**New-compliancesearchaction-清除**命令在[步驟 3](#step-3-delete-the-message)。</span><span class="sxs-lookup"><span data-stu-id="8117d-130">The messages that match the query for this search will be deleted by running the **New-ComplianceSearchAction -Purge** command in [Step 3](#step-3-delete-the-message).</span></span> <span data-ttu-id="8117d-131">如需建立內容搜尋和設定搜尋查詢的詳細資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="8117d-131">For information about creating a Content Search and configuring search queries, see the following topics:</span></span> 
  
- [<span data-ttu-id="8117d-132">Office 365 中的內容搜尋</span><span class="sxs-lookup"><span data-stu-id="8117d-132">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="8117d-133">內容搜尋的關鍵字查詢</span><span class="sxs-lookup"><span data-stu-id="8117d-133">Keyword queries for Content Search</span></span>](keyword-queries-and-search-conditions.md)
    
- [<span data-ttu-id="8117d-134">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="8117d-134">New-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearch)
    
- [<span data-ttu-id="8117d-135">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="8117d-135">Start-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/Start-ComplianceSearch)
    
> [!NOTE]
> <span data-ttu-id="8117d-136">您在此步驟中建立內容搜尋中搜尋的內容位置不能包含 SharePoint 或 OneDrive for Business 網站。</span><span class="sxs-lookup"><span data-stu-id="8117d-136">The content locations that are searched in the Content Search that you create in this step can't include SharePoint or OneDrive for Business sites.</span></span> <span data-ttu-id="8117d-137">您可以將用於電子郵件的內容搜尋中包含僅信箱與公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="8117d-137">You can include only mailboxes and public folders in a Content Search that will be used to email messages.</span></span> <span data-ttu-id="8117d-138">如果內容搜尋中包含的網站，您會收到錯誤，在步驟 3 中執行**New-compliancesearchaction** cmdlet 時即可。</span><span class="sxs-lookup"><span data-stu-id="8117d-138">If the Content Search includes sites, you'll receive an error in Step 3 when you run the **New-ComplianceSearchAction** cmdlet.</span></span> 
  
### <a name="tips-for-finding-messages-to-remove"></a><span data-ttu-id="8117d-139">尋找要移除的郵件的提示</span><span class="sxs-lookup"><span data-stu-id="8117d-139">Tips for finding messages to remove</span></span>

<span data-ttu-id="8117d-p109">搜尋查詢的目標是將搜尋結果縮減為只有您想要移除的郵件。以下是一些提示：</span><span class="sxs-lookup"><span data-stu-id="8117d-p109">The goal of the search query is to narrow the results of the search to only the message or messages that you want to remove. Here are some tips:</span></span>
  
- <span data-ttu-id="8117d-142">如果您知道郵件主旨行中使用的確切文字或片語，請在搜尋查詢中使用 **Subject** 屬性。</span><span class="sxs-lookup"><span data-stu-id="8117d-142">If you know the exact text or phrase used in the subject line of the message, use the **Subject** property in the search query.</span></span> 
    
- <span data-ttu-id="8117d-143">如果您知道郵件的實際日期 (或日期範圍)，請在搜尋查詢中包含 **Received** 屬性。</span><span class="sxs-lookup"><span data-stu-id="8117d-143">If you know that exact date (or date range) of the message, include the **Received** property in the search query.</span></span> 
    
- <span data-ttu-id="8117d-144">如果您知道郵件的寄件者，請在搜尋查詢中包含 **From** 屬性。</span><span class="sxs-lookup"><span data-stu-id="8117d-144">If you know who sent the message, include the **From** property in the search query.</span></span> 
    
- <span data-ttu-id="8117d-145">預覽搜尋結果，以確認內容搜尋僅傳回您想要刪除的郵件。</span><span class="sxs-lookup"><span data-stu-id="8117d-145">Preview the search results to verify that the search returned only the message (or messages) that you want to delete.</span></span>
    
- <span data-ttu-id="8117d-146">使用搜尋預估統計資料 （顯示於詳細資料窗格的搜尋] 安全性 & 合規性中心或使用[Get-compliancesearch](https://go.microsoft.com/fwlink/p/?LinkId=517934) cmdlet） 來取得結果的總計數。</span><span class="sxs-lookup"><span data-stu-id="8117d-146">Use the search estimate statistics (displayed in the details pane of the search in the Security & Compliance Center or by using the [Get-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517934) cmdlet) to get a count of the total number of results.</span></span> 
    
<span data-ttu-id="8117d-147">以下是尋找可疑電子郵件訊息的兩個查詢範例。</span><span class="sxs-lookup"><span data-stu-id="8117d-147">Here are two examples of queries to find suspicious email messages.</span></span>
  
- <span data-ttu-id="8117d-148">此查詢傳回 2016 年 4 月 13 日和 2016 年 4 月 14 日之間使用者所接收的郵件，且在主旨列中包含文字「動作」和「必要」。</span><span class="sxs-lookup"><span data-stu-id="8117d-148">This query returns messages that were received by users between April 13, 2016 and April 14, 2016 and that contain the words "action" and "required" in the subject line.</span></span>
    
    ```
    (Received:4/13/2016..4/14/2016) AND (Subject:'Action required')
    ```
   
- <span data-ttu-id="8117d-149">此查詢傳回 chatsuwloginsset12345@outlook.com 所送出的郵件，且在主旨列中包含精準字詞「更新您的帳戶資訊」。</span><span class="sxs-lookup"><span data-stu-id="8117d-149">This query returns messages that were sent by chatsuwloginsset12345@outlook.com and that contain the exact phrase "Update your account information" in the subject line.</span></span>
    
    ```
    (From:chatsuwloginsset12345@outlook.com) AND (Subject:"Update your account information")
    ```

## <a name="step-2-connect-to-security--compliance-center-powershell"></a><span data-ttu-id="8117d-150">步驟 2： 連線到安全性 & 合規性中心 PowerShell</span><span class="sxs-lookup"><span data-stu-id="8117d-150">Step 2: Connect to Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="8117d-151">下一步是連線至您的組織的安全性 & 合規性中心 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="8117d-151">The next step is to connect to Security & Compliance Center PowerShell for your organization.</span></span> <span data-ttu-id="8117d-152">如需逐步指示，請參閱[連線到安全性 & 合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="8117d-152">For step-by-step instructions, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>
  
<span data-ttu-id="8117d-153">如果您的 Office 365 帳戶使用多重要素驗證 (MFA)，或同盟驗證，您無法使用上一個主題上連接到安全性 & 合規性中心 PowerShell 中的指示。</span><span class="sxs-lookup"><span data-stu-id="8117d-153">If your Office 365 account uses multi-factor authentication (MFA) or federated authentication, you can't use the instructions in the previous topic on connecting to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="8117d-154">相反地，請參閱主題中的 <<c0>連接到安全性 &amp; 合規性中心 PowerShell 中使用多重要素驗證的指示。</span><span class="sxs-lookup"><span data-stu-id="8117d-154">Instead, see the instructions in the topic [Connect to Security & Compliance Center PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell).</span></span>
  
## <a name="step-3-delete-the-message"></a><span data-ttu-id="8117d-155">步驟 3： 刪除郵件</span><span class="sxs-lookup"><span data-stu-id="8117d-155">Step 3: Delete the message</span></span>

<span data-ttu-id="8117d-156">您已建立並精簡內容搜尋來傳回的訊息，您想要移除，並且連線到安全性 & 合規性中心 PowerShell 之後，最後一個步驟是執行**New-compliancesearchaction** cmdlet 來刪除郵件。</span><span class="sxs-lookup"><span data-stu-id="8117d-156">After you've created and refined a Content Search to return the message that you want to remove and are connected to Security & Compliance Center PowerShell, the final step is to run the **New-ComplianceSearchAction** cmdlet to delete the message.</span></span> <span data-ttu-id="8117d-157">您可以虛-或實刪除郵件。</span><span class="sxs-lookup"><span data-stu-id="8117d-157">You can soft- or hard-delete the message.</span></span> <span data-ttu-id="8117d-158">虛刪除的郵件會移至使用者的 [可復原的項目] 資料夾，並保留已刪除的項目保留期間到期之前。</span><span class="sxs-lookup"><span data-stu-id="8117d-158">A soft-deleted message is moved to a user's Recoverable Items folder and retained until the deleted item retention period expires.</span></span> <span data-ttu-id="8117d-159">實刪除的郵件標示為永久移除信箱，並將會永久移除受管理的資料夾助理員處理信箱時的下一個時間。</span><span class="sxs-lookup"><span data-stu-id="8117d-159">Hard-deleted messages are marked for permanent removal from the mailbox and will be permanently removed the next time the mailbox is processed by the Managed Folder Assistant.</span></span> <span data-ttu-id="8117d-160">如果信箱已啟用單一項目復原，已刪除的項目保留期間到期後，將會永久移除實刪除的項目。</span><span class="sxs-lookup"><span data-stu-id="8117d-160">If single item recovery is enabled for the mailbox, hard-deleted items will be permanently removed after the deleted item retention period expires.</span></span> <span data-ttu-id="8117d-161">如果信箱處於保留狀態，已刪除的郵件會保留直到項目的保留期間到期或從信箱移除保留為止。</span><span class="sxs-lookup"><span data-stu-id="8117d-161">If a mailbox is placed on hold, deleted messages are preserved until the hold duration for the item expires or until the hold is removed from the mailbox.</span></span>
  
<span data-ttu-id="8117d-162">在下列範例中，命令將虛刪除名為 「 移除網路釣魚郵件 」 的內容搜尋所傳回的搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="8117d-162">In the following example, the command will soft-delete the search results returned by a Content Search named "Remove Phishing Message".</span></span> 

```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType SoftDelete
```

<span data-ttu-id="8117d-163">若要實刪除 「 移除網路釣魚郵件 」 的內容搜尋所傳回的項目，您會執行此命令：</span><span class="sxs-lookup"><span data-stu-id="8117d-163">To hard-deleted the items returned by the  "Remove Phishing Message" content search, you would run this command:</span></span>

```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType HardDelete
```

<span data-ttu-id="8117d-164">請注意，當您執行上述命令虛-或實刪除的郵件， *SearchName*參數所指定的搜尋您在步驟 1 中建立內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="8117d-164">Note that when you run the previous command to soft- or hard-delete messages, the search specified by the  *SearchName*  parameter is the Content Search that you created in Step 1.</span></span> 
  
<span data-ttu-id="8117d-165">如需詳細資訊，請參閱 < <b0>New-compliancesearchaction</b0>。</span><span class="sxs-lookup"><span data-stu-id="8117d-165">For more information, see [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearchAction).</span></span>

## <a name="more-information"></a><span data-ttu-id="8117d-166">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="8117d-166">More information</span></span>

- <span data-ttu-id="8117d-167">**您該如何取得搜尋狀態和移除作業？**</span><span class="sxs-lookup"><span data-stu-id="8117d-167">**How do you get status on the search and remove operation?**</span></span>

    <span data-ttu-id="8117d-168">執行 **Get-ComplianceSearchAction** 以取得刪除作業的狀態。</span><span class="sxs-lookup"><span data-stu-id="8117d-168">Run the **Get-ComplianceSearchAction** to get the status on the delete operation.</span></span> <span data-ttu-id="8117d-169">請注意，當您執行**New-compliancesearchaction** cmdlet 時建立的物件名為使用此格式： `<name of Content Search>_Purge`。</span><span class="sxs-lookup"><span data-stu-id="8117d-169">Note that the object that is created when you run the **New-ComplianceSearchAction** cmdlet is named using this format:  `<name of Content Search>_Purge`.</span></span> 
    
- <span data-ttu-id="8117d-170">**刪除郵件之後會發生什麼事？**</span><span class="sxs-lookup"><span data-stu-id="8117d-170">**What happens after you delete a message?**</span></span>

   <span data-ttu-id="8117d-171">與已刪除的郵件`New-ComplianceSearchAction -Purge -PurgeType HardDelete`命令移至 [清除] 資料夾，並無法供使用者存取。</span><span class="sxs-lookup"><span data-stu-id="8117d-171">A message that's deleted with the  `New-ComplianceSearchAction -Purge -PurgeType HardDelete` command is moved to the Purges folder and can't be accessed by the user.</span></span> <span data-ttu-id="8117d-172">將郵件移至 [清除] 資料夾之後，郵件會保留已刪除的項目保留期間的持續期間，如果信箱已啟用單一項目復原。</span><span class="sxs-lookup"><span data-stu-id="8117d-172">After the message is moved to the Purges folder, the message is retained for the duration of the deleted item retention period if single item recovery is enabled for the mailbox.</span></span> <span data-ttu-id="8117d-173">（在 Office 365 中，單一項目復原是預設啟用時建立新的信箱。）已刪除的項目保留期間到期之後，郵件會標示為永久刪除，並會從 Office 365 清除受管理的資料夾助理員處理信箱時的下一個時間。</span><span class="sxs-lookup"><span data-stu-id="8117d-173">(In Office 365, single item recovery is enabled by default when a new mailbox is created.) After the deleted item retention period expires, the message is marked for permanent deletion and will be purged from Office 365 the next time the mailbox is processed by the Managed Folder assistant.</span></span> 

   <span data-ttu-id="8117d-174">如果您使用`New-ComplianceSearchAction -Purge -PurgeType SoftDelete`命令，郵件會移至使用者的 [可復原的項目] 資料夾中的 [刪除] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="8117d-174">If you use the `New-ComplianceSearchAction -Purge -PurgeType SoftDelete` command, messages are moved to the Deletions folder in the user's Recoverable Items folder.</span></span> <span data-ttu-id="8117d-175">它不是立即清除從 Office 365。</span><span class="sxs-lookup"><span data-stu-id="8117d-175">It isn't immediately purged from Office 365.</span></span> <span data-ttu-id="8117d-176">使用者可以根據為信箱設定的刪除項目保留期間，在持續時間之內復原 [刪除的郵件] 資料夾中的郵件。</span><span class="sxs-lookup"><span data-stu-id="8117d-176">The user can recover messages in the Deleted Items folder for the duration based on the deleted item retention period configured for the mailbox.</span></span> <span data-ttu-id="8117d-177">此保留期間到期 (或者如果使用者在到期之前清除郵件) 之後，郵件會移至 [清除] 資料夾且使用者無法再存取。</span><span class="sxs-lookup"><span data-stu-id="8117d-177">After this retention period expires (or if user purges the message before it expires), the message is moved to the Purges folder and can no longer be accessed by the user.</span></span> <span data-ttu-id="8117d-178">一次中 [清除] 資料夾中，郵件會保留期間根據對信箱設定，如果信箱已啟用單一項目復原已刪除的項目保留期間。</span><span class="sxs-lookup"><span data-stu-id="8117d-178">Once in the Purges folder, the message is retained for the duration based on the deleted item retention period configured for the mailbox if single items recovery is enabled for the mailbox.</span></span> <span data-ttu-id="8117d-179">（在 Office 365 中，單一項目復原是預設啟用時建立新的信箱。）已刪除的項目保留期間到期之後，郵件會標示為永久刪除，並會從 Office 365 清除受管理的資料夾助理員處理信箱時的下一個時間。</span><span class="sxs-lookup"><span data-stu-id="8117d-179">(In Office 365, single item recovery is enabled by default when a new mailbox is created.) After the deleted item retention period expires, the message is marked for permanent deletion and will be purged from Office 365 the next time that the mailbox is processed by the Managed Folder assistant.</span></span> 
    
- <span data-ttu-id="8117d-180">**如果您有超過 50000 個信箱刪除郵件？**</span><span class="sxs-lookup"><span data-stu-id="8117d-180">**What if you have to delete a message from more than 50,000 mailboxes?**</span></span>

    <span data-ttu-id="8117d-181">如先前所述，您可以執行搜尋，並清除作業最多 50000 個信箱。</span><span class="sxs-lookup"><span data-stu-id="8117d-181">As previously stated, you can perform a search and purge operation on a maximum of 50,000 mailboxes.</span></span> <span data-ttu-id="8117d-182">如果您必須執行搜尋及清除超過 50000 個信箱上的作業，請考慮建立暫存的搜尋權限篩選器，會降低會搜尋以少於 50000 個信箱的信箱數目。</span><span class="sxs-lookup"><span data-stu-id="8117d-182">If you have to do a search and purge operation on more than 50,000 mailboxes, consider creating temporary search permissions filters that would reduce the number of mailboxes that would be searched to less than 50,000 mailboxes.</span></span> <span data-ttu-id="8117d-183">例如，如果您的組織中包含不同部門、 狀態或國家/地區中的信箱，您可以建立下列其中一個組織中搜尋信箱子集這些信箱內容為基礎的信箱搜尋權限篩選器。</span><span class="sxs-lookup"><span data-stu-id="8117d-183">For example, if your organization contains mailboxes in different departments, states, or countries, you can create a mailbox search permissions filter based on one of those mailbox properties to search a subset of mailboxes in your organization.</span></span> <span data-ttu-id="8117d-184">建立搜尋權限篩選器之後，您應建立搜尋 （在步驟 1 中所述），然後再刪除的郵件，（在步驟 3 中所述）。</span><span class="sxs-lookup"><span data-stu-id="8117d-184">After you create the search permissions filter, you would create the search (described in Step 1) and then delete the message (described in Step 3).</span></span> <span data-ttu-id="8117d-185">然後您可以編輯搜尋及清除一組不同的信箱中的郵件篩選器。</span><span class="sxs-lookup"><span data-stu-id="8117d-185">Then you can edit the filter to search for and purge messages in a different set of mailboxes.</span></span> <span data-ttu-id="8117d-186">如需建立搜尋權限篩選器的詳細資訊，請參閱 <<c0>設定的權限篩選內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="8117d-186">For more information about creating search permissions filters, see [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md).</span></span>
    
- <span data-ttu-id="8117d-187">**會刪除包含在搜尋結果中的未編製索引項目？**</span><span class="sxs-lookup"><span data-stu-id="8117d-187">**Will unindexed items included in the search results be deleted?**</span></span>

    <span data-ttu-id="8117d-188">否，' New-compliancesearchaction-清除命令不會刪除未編製索引的項目。</span><span class="sxs-lookup"><span data-stu-id="8117d-188">No, the  \`New-ComplianceSearchAction -Purge command doesn't delete unindexed items.</span></span> 
    
- <span data-ttu-id="8117d-189">**如果從已處於就地保留或訴訟暫止狀態或指派給 Office 365 保留原則的信箱刪除郵件，會發生什麼事？**</span><span class="sxs-lookup"><span data-stu-id="8117d-189">**What happens if a message is deleted from a mailbox that has been placed on In-Place Hold or Litigation Hold or is assigned to an Office 365 retention policy?**</span></span>

    <span data-ttu-id="8117d-190">會清除郵件，並將其移至 [清除] 資料夾之後，郵件會保留直到保留期間到期為止。</span><span class="sxs-lookup"><span data-stu-id="8117d-190">After the message is purged and moved to the Purges folder, the message is retained until the hold duration expires.</span></span> <span data-ttu-id="8117d-191">如果保留期間是無限，則會保留項目直到移除保留或變更保留持續時間為止。</span><span class="sxs-lookup"><span data-stu-id="8117d-191">If the hold duration is unlimited, then items are retained until the hold is removed or the hold duration is changed.</span></span>
    
- <span data-ttu-id="8117d-192">**原因是搜尋並移除除以不同的安全性與合規性中心角色群組之間的工作流程？**</span><span class="sxs-lookup"><span data-stu-id="8117d-192">**Why is the search and remove workflow divided among different security and compliance center role groups?**</span></span>

    <span data-ttu-id="8117d-193">如先前所述，使用者必須是「eDiscovery 管理員」角色群組的成員，或者獲指派「符合性搜尋」管理角色才能搜尋信箱。</span><span class="sxs-lookup"><span data-stu-id="8117d-193">As previously explained, a person has to be a member of the eDiscovery Manager role group or be assigned the Compliance Search management role to search mailboxes.</span></span> <span data-ttu-id="8117d-194">若要刪除郵件，該人員必須是「組織管理」角色群組的成員，或者獲指派「搜尋及清除」管理角色。</span><span class="sxs-lookup"><span data-stu-id="8117d-194">To delete messages, a person has to be a member of the Organization Management role group or be assigned the Search And Purge management role.</span></span> <span data-ttu-id="8117d-195">這樣就可以控制誰能夠在組織中搜尋信箱以及誰能夠刪除郵件。</span><span class="sxs-lookup"><span data-stu-id="8117d-195">This makes it possible to control who can search mailboxes in the organization and who can delete messages.</span></span> 
