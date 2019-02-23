---
title: 搜尋並刪除您的 Office 365 組織-Admin 說明中的電子郵件
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 3526fd06-b45f-445b-aed4-5ebd37b3762a
description: 使用搜尋並清除 Office 365 安全性功能&amp;規範中心來搜尋並刪除您組織中所有信箱的電子郵件訊息。
ms.openlocfilehash: ecdacd4e484d6de267e029b8e3fcdafc9b1fce4d
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223612"
---
# <a name="search-for-and-delete-email-messages-in-your-office-365-organization---admin-help"></a><span data-ttu-id="f03f4-103">搜尋並刪除您的 Office 365 組織-Admin 說明中的電子郵件</span><span class="sxs-lookup"><span data-stu-id="f03f4-103">Search for and delete email messages in your Office 365 organization - Admin Help</span></span>

<span data-ttu-id="f03f4-104">**本文適用於系統管理員。您試圖尋找您想要刪除的信箱中的項目請參閱[尋找訊息或具有立即搜尋的項目](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)**|</span><span class="sxs-lookup"><span data-stu-id="f03f4-104">**This article is for administrators. Are you trying to find items in your mailbox that you want to delete? See [Find a message or item with Instant Search](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)**|</span></span>
   
<span data-ttu-id="f03f4-p101">您可以使用 Office 365 中的 「 內容搜尋功能來搜尋並在組織中刪除所有信箱的電子郵件訊息。這可協助您尋找及移除潛在有害或高風險的電子郵件，例如：</span><span class="sxs-lookup"><span data-stu-id="f03f4-p101">You can use the Content Search feature in Office 365 to search for and delete an email message from all mailboxes in your organization. This can help you find and remove potentially harmful or high-risk email, such as:</span></span>
  
- <span data-ttu-id="f03f4-107">包含危險附件或病毒的郵件</span><span class="sxs-lookup"><span data-stu-id="f03f4-107">Messages that contain dangerous attachments or viruses</span></span>
    
- <span data-ttu-id="f03f4-108">網路釣魚郵件</span><span class="sxs-lookup"><span data-stu-id="f03f4-108">Phishing messages</span></span>
    
- <span data-ttu-id="f03f4-109">包含敏感資料的郵件</span><span class="sxs-lookup"><span data-stu-id="f03f4-109">Messages that contain sensitive data</span></span>
    
> [!CAUTION]
> <span data-ttu-id="f03f4-110">搜尋和清除是強大功能，可讓任何人指派刪除您組織中信箱的電子郵件訊息的必要權限。</span><span class="sxs-lookup"><span data-stu-id="f03f4-110">Search and purge is a powerful feature that allows anyone that is assigned the necessary permissions to delete email messages from mailboxes in your organization.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="f03f4-111">開始之前</span><span class="sxs-lookup"><span data-stu-id="f03f4-111">Before you begin</span></span>

- <span data-ttu-id="f03f4-p102">若要建立並執行內容的搜尋，您必須是**eDiscovery 管理員**角色群組的成員或**規範搜尋**管理角色指派。若要刪除的郵件，您必須是 「**組織管理**角色群組的成員或**搜尋和清除**管理角色指派。如需將使用者新增至角色群組的資訊，請參閱[授與使用者存取 Office 365 安全性 & 規範中心](grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="f03f4-p102">To create and run a Content Search, you have to be a member of the **eDiscovery Manager** role group or be assigned the **Compliance Search** management role. To delete messages, you have to be a member of the **Organization Management** role group or be assigned the **Search And Purge** management role. For information about adding users to a role group, see [Give users access to the Office 365 Security & Compliance Center](grant-access-to-the-security-and-compliance-center.md).</span></span>
    
- <span data-ttu-id="f03f4-p103">您必須使用安全性 & 規範中心 PowerShell 刪除的郵件。請參閱[Step 2](#step-2-connect-to-security-amp-compliance-center-powershell)的連線方式的相關指示。</span><span class="sxs-lookup"><span data-stu-id="f03f4-p103">You have to use Security & Compliance Center PowerShell to delete messages. See [Step 2](#step-2-connect-to-security-amp-compliance-center-powershell) for instructions about how to connect.</span></span>
    
- <span data-ttu-id="f03f4-p104">每個信箱的 10 個項目最多可以一次移除。搜尋並移除郵件的功能為了要事件回應工具，因為此限制可協助確保從信箱快速地移除訊息。此功能並未清除 [使用者信箱適用對象。若要刪除超過 10 個項目，您可以使用**Search-mailbox DeleteContent**命令在 Exchange Online PowerShell。請參閱[搜尋和刪除郵件-Admin 說明](search-for-and-delete-messagesadmin-help.md)。</span><span class="sxs-lookup"><span data-stu-id="f03f4-p104">A maximum of 10 items per mailbox can be removed at one time. Because the capability to search for and remove messages is intended to be an incident-response tool, this limit helps ensure that messages are quickly removed from mailboxes. This feature isn't intended to clean up user mailboxes. To delete more than 10 items, you can use the **Search-Mailbox -DeleteContent** command in Exchange Online PowerShell. See [Search for and delete messages - Admin help](search-for-and-delete-messagesadmin-help.md).</span></span>
    
- <span data-ttu-id="f03f4-p105">內容搜尋您可以刪除項目中的搜尋並清除巨集指令中的信箱數目上限為 50000。如果內容搜尋 （您在[步驟 1](#step-1-create-a-content-search-to-find-the-message-to-delete)中建立） 有超過 50000 個來源信箱，將會失敗的清除動作 （您在步驟 3 中建立）。請參閱[的詳細資訊](#more-information)] 區段中的提示上執行搜尋並清除超過 50000 個信箱上的作業。</span><span class="sxs-lookup"><span data-stu-id="f03f4-p105">The maximum number of mailboxes in a Content Search that you can delete items in by doing a search and purge action is 50,000. If the Content Search (that you create in [Step 1](#step-1-create-a-content-search-to-find-the-message-to-delete)) has more than 50,000 source mailboxes, the purge action (that you create in Step 3) will fail. See the [More information](#more-information) section for a tip on performing a search and purge operation on more than 50,000 mailboxes.</span></span> 
    
- <span data-ttu-id="f03f4-p106">本文中的程序只可以用來刪除 Exchange Online 信箱和公用資料夾中的項目。您無法使用它來刪除內容 SharePoint 或 OneDrive for Business 的網站。</span><span class="sxs-lookup"><span data-stu-id="f03f4-p106">The procedure in this article can only be used to delete items in Exchange Online mailboxes and public folders. You can't use it to delete content from SharePoint or OneDrive for Business sites.</span></span>
    
## <a name="step-1-create-a-content-search-to-find-the-message-to-delete"></a><span data-ttu-id="f03f4-127">步驟 1：建立內容搜尋來尋找要刪除的郵件</span><span class="sxs-lookup"><span data-stu-id="f03f4-127">Step 1: Create a Content Search to find the message to delete</span></span>

<span data-ttu-id="f03f4-p107">第一個步驟是建立及執行內容的搜尋來尋找您想要移除您組織中信箱的郵件。您可以使用 [安全性] 來建立搜尋&amp;規範中心或執行**新增 ComplianceSearch**和**開始 ComplianceSearch**指令程式。符合查詢的此搜尋將執行刪除的郵件**新增 ComplianceSearchAction-清除**命令在[步驟 3](#step-3-delete-the-message)。如需建立內容的搜尋及設定搜尋查詢，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="f03f4-p107">The first step is to create and run a Content Search to find the message that you want to remove from mailboxes in your organization. You can create the search by using the Security &amp; Compliance Center or by running the **New-ComplianceSearch** and **Start-ComplianceSearch** cmdlets. The messages that match the query for this search will be deleted by running the **New-ComplianceSearchAction -Purge** command in [Step 3](#step-3-delete-the-message). For information about creating a Content Search and configuring search queries, see the following topics:</span></span> 
  
- [<span data-ttu-id="f03f4-132">Office 365 中的內容搜尋</span><span class="sxs-lookup"><span data-stu-id="f03f4-132">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="f03f4-133">內容搜尋的關鍵字查詢</span><span class="sxs-lookup"><span data-stu-id="f03f4-133">Keyword queries for Content Search</span></span>](keyword-queries-and-search-conditions.md)
    
- [<span data-ttu-id="f03f4-134">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="f03f4-134">New-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearch)
    
- [<span data-ttu-id="f03f4-135">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="f03f4-135">Start-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/Start-ComplianceSearch)
    
> [!NOTE]
> <span data-ttu-id="f03f4-p108">您在此步驟中建立的內容搜尋中搜尋的內容位置不能包含 SharePoint 或 OneDrive for Business 的網站。您可以將用於電子郵件訊息內容搜尋中包含只信箱與公用資料夾。如果內容搜尋包含網站，將會收到錯誤步驟 3 中執行**新增 ComplianceSearchAction**指令程式時。</span><span class="sxs-lookup"><span data-stu-id="f03f4-p108">The content locations that are searched in the Content Search that you create in this step can't include SharePoint or OneDrive for Business sites. You can include only mailboxes and public folders in a Content Search that will be used to email messages. If the Content Search includes sites, you'll receive an error in Step 3 when you run the **New-ComplianceSearchAction** cmdlet.</span></span> 
  
### <a name="tips-for-finding-messages-to-remove"></a><span data-ttu-id="f03f4-139">尋找要移除的郵件的提示</span><span class="sxs-lookup"><span data-stu-id="f03f4-139">Tips for finding messages to remove</span></span>

<span data-ttu-id="f03f4-p109">搜尋查詢的目標是將搜尋結果縮減為只有您想要移除的郵件。以下是一些提示：</span><span class="sxs-lookup"><span data-stu-id="f03f4-p109">The goal of the search query is to narrow the results of the search to only the message or messages that you want to remove. Here are some tips:</span></span>
  
- <span data-ttu-id="f03f4-142">如果您知道郵件主旨行中使用的確切文字或片語，請在搜尋查詢中使用 **Subject** 屬性。</span><span class="sxs-lookup"><span data-stu-id="f03f4-142">If you know the exact text or phrase used in the subject line of the message, use the **Subject** property in the search query.</span></span> 
    
- <span data-ttu-id="f03f4-143">如果您知道郵件的實際日期 (或日期範圍)，請在搜尋查詢中包含 **Received** 屬性。</span><span class="sxs-lookup"><span data-stu-id="f03f4-143">If you know that exact date (or date range) of the message, include the **Received** property in the search query.</span></span> 
    
- <span data-ttu-id="f03f4-144">如果您知道郵件的寄件者，請在搜尋查詢中包含 **From** 屬性。</span><span class="sxs-lookup"><span data-stu-id="f03f4-144">If you know who sent the message, include the **From** property in the search query.</span></span> 
    
- <span data-ttu-id="f03f4-145">預覽搜尋結果，以確認內容搜尋僅傳回您想要刪除的郵件。</span><span class="sxs-lookup"><span data-stu-id="f03f4-145">Preview the search results to verify that the search returned only the message (or messages) that you want to delete.</span></span>
    
- <span data-ttu-id="f03f4-146">使用搜尋評估統計資料 (搜尋安全性的詳細資料窗格中顯示&amp;規範中心或使用[Get ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517934)指令程式來) 若要取得的結果總數計數。</span><span class="sxs-lookup"><span data-stu-id="f03f4-146">Use the search estimate statistics (displayed in the details pane of the search in the Security &amp; Compliance Center or by using the [Get-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517934) cmdlet) to get a count of the total number of results.</span></span> 
    
<span data-ttu-id="f03f4-147">以下是尋找可疑電子郵件訊息的兩個查詢範例。</span><span class="sxs-lookup"><span data-stu-id="f03f4-147">Here are two examples of queries to find suspicious email messages.</span></span>
  
- <span data-ttu-id="f03f4-148">此查詢傳回 2016 年 4 月 13 日和 2016 年 4 月 14 日之間使用者所接收的郵件，且在主旨列中包含文字「動作」和「必要」。</span><span class="sxs-lookup"><span data-stu-id="f03f4-148">This query returns messages that were received by users between April 13, 2016 and April 14, 2016 and that contain the words "action" and "required" in the subject line.</span></span>
    
    ```
    (Received:4/13/2016..4/14/2016) AND (Subject:'Action required')
    ```
   
- <span data-ttu-id="f03f4-149">此查詢傳回 chatsuwloginsset12345@outlook.com 所送出的郵件，且在主旨列中包含精準字詞「更新您的帳戶資訊」。</span><span class="sxs-lookup"><span data-stu-id="f03f4-149">This query returns messages that were sent by chatsuwloginsset12345@outlook.com and that contain the exact phrase "Update your account information" in the subject line.</span></span>
    
    ```
    (From:chatsuwloginsset12345@outlook.com) AND (Subject:"Update your account information")
    ```

## <a name="step-2-connect-to-security--compliance-center-powershell"></a><span data-ttu-id="f03f4-150">步驟 2： 連線至安全性 & 規範中心 PowerShell</span><span class="sxs-lookup"><span data-stu-id="f03f4-150">Step 2: Connect to Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="f03f4-p110">下一步是連線至您的組織的安全性 & 規範中心 PowerShell。如需逐步說明，請參閱[連線至 Office 365 安全性&amp;規範中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f03f4-p110">The next step is to connect to Security & Compliance Center PowerShell for your organization. For step-by-step instructions, see [Connect to Office 365 Security &amp; Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>
  
<span data-ttu-id="f03f4-p111">如果您的 Office 365 帳戶使用多重要素驗證 (MFA) 或同盟驗證，您無法使用先前在連線至安全性 & 規範中心 PowerShell 主題中的指示。但是，請參閱[連線至 Office 365 安全性 & 規範中心 PowerShell 使用多重要素驗證](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell)主題中的指示。</span><span class="sxs-lookup"><span data-stu-id="f03f4-p111">If your Office 365 account uses multi-factor authentication (MFA) or federated authentication, you can't use the instructions in the previous topic on connecting to Security & Compliance Center PowerShell. Instead, see the instructions in the topic [Connect to Office 365 Security & Compliance Center PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell).</span></span>
  
## <a name="step-3-delete-the-message"></a><span data-ttu-id="f03f4-155">步驟 3： 刪除郵件</span><span class="sxs-lookup"><span data-stu-id="f03f4-155">Step 3: Delete the message</span></span>

<span data-ttu-id="f03f4-p112">您已建立並精簡內容搜尋以傳回您想要移除並連接到安全性訊息之後&amp;規範中心 PowerShell 中的最後一個步驟是執行**新增 ComplianceSearchAction** cmdlet 來刪除郵件。您可以虛或硬-刪除郵件。虛刪除的郵件會移至使用者的 [可復原的項目] 資料夾及保留，直到刪除項目保留期間到期為止。硬碟已刪除的郵件標記為永久移除從信箱並將會永久移除受管理的資料夾助理員處理此信箱的下一次。如果信箱啟用單一項目復原，則硬碟已刪除的項目將永久移除後刪除項目保留期間到期。如果信箱處於保留狀態，刪除的郵件會保留項目的保留期間到期直到或從信箱移除保留為止。</span><span class="sxs-lookup"><span data-stu-id="f03f4-p112">After you've created and refined a Content Search to return the message that you want to remove and are connected to Security &amp; Compliance Center PowerShell, the final step is to run the **New-ComplianceSearchAction** cmdlet to delete the message. You can soft- or hard-delete the message. A soft-deleted message is moved to a user's Recoverable Items folder and retained until the deleted item retention period expires. Hard-deleted messages are marked for permanent removal from the mailbox and will be permanently removed the next time the mailbox is processed by the Managed Folder Assistant. If single item recovery is enabled for the mailbox, hard-deleted items will be permanently removed after the deleted item retention period expires. If a mailbox is placed on hold, deleted messages are preserved until the hold duration for the item expires or until the hold is removed from the mailbox.</span></span>
  
<span data-ttu-id="f03f4-162">在下列範例中，此命令將會虛刪除名為"移除網路釣魚 Message"的內容搜尋所傳回的搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="f03f4-162">In the following example, the command will soft-delete the search results returned by a Content Search named "Remove Phishing Message".</span></span> 

```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType SoftDelete
```

<span data-ttu-id="f03f4-163">硬碟-刪除"移除網路釣魚訊息 「 內容搜尋傳回的項目，則會執行此命令：</span><span class="sxs-lookup"><span data-stu-id="f03f4-163">To hard-deleted the items returned by the  "Remove Phishing Message" content search, you would run this command:</span></span>

```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType HardDelete
```

<span data-ttu-id="f03f4-164">請注意當您執行上述命令虛或硬-刪除郵件時，搜尋*SearchName*參數所指定之內容的搜尋您在步驟 1 中建立的。</span><span class="sxs-lookup"><span data-stu-id="f03f4-164">Note that when you run the previous command to soft- or hard-delete messages, the search specified by the  *SearchName*  parameter is the Content Search that you created in Step 1.</span></span> 
  
<span data-ttu-id="f03f4-165">如需詳細資訊，請參閱[新增 ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearchAction)。</span><span class="sxs-lookup"><span data-stu-id="f03f4-165">For more information, see [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearchAction).</span></span>

## <a name="more-information"></a><span data-ttu-id="f03f4-166">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="f03f4-166">More information</span></span>

- <span data-ttu-id="f03f4-167">**如何取得的搜尋狀態及移除作業嗎？**</span><span class="sxs-lookup"><span data-stu-id="f03f4-167">**How do you get status on the search and remove operation?**</span></span>

    <span data-ttu-id="f03f4-p113">執行**Get ComplianceSearchAction**以取得刪除作業狀態。請注意當您執行**新增 ComplianceSearchAction**指令程式時所建立的物件名為使用此格式： `<name of Content Search>_Purge`。</span><span class="sxs-lookup"><span data-stu-id="f03f4-p113">Run the **Get-ComplianceSearchAction** to get the status on the delete operation. Note that the object that is created when you run the **New-ComplianceSearchAction** cmdlet is named using this format:  `<name of Content Search>_Purge`.</span></span> 
    
- <span data-ttu-id="f03f4-170">**刪除郵件之後會發生什麼事？**</span><span class="sxs-lookup"><span data-stu-id="f03f4-170">**What happens after you delete a message?**</span></span>

   <span data-ttu-id="f03f4-p114">使用已刪除的訊息`New-ComplianceSearchAction -Purge -PurgeType HardDelete`命令移至 [清除] 資料夾，且無法供使用者存取。將郵件移至 [清除] 資料夾之後，郵件會保留已刪除的項目保留期間的持續期間如果單一項目復原已啟用信箱。（Office 365 的單一項目復原預設會啟用時建立新的信箱。）刪除項目保留期間到期後，標記為永久刪除郵件，並將來自 Office 365 清除信箱由受管理的資料夾助理員處理下一次。</span><span class="sxs-lookup"><span data-stu-id="f03f4-p114">A message that's deleted with the  `New-ComplianceSearchAction -Purge -PurgeType HardDelete` command is moved to the Purges folder and can't be accessed by the user. After the message is moved to the Purges folder, the message is retained for the duration of the deleted item retention period if single item recovery is enabled for the mailbox. (In Office 365, single item recovery is enabled by default when a new mailbox is created.) After the deleted item retention period expires, the message is marked for permanent deletion and will be purged from Office 365 the next time the mailbox is processed by the Managed Folder assistant.</span></span> 

   <span data-ttu-id="f03f4-p115">如果您使用`New-ComplianceSearchAction -Purge -PurgeType SoftDelete`命令郵件會移到使用者的 [可復原的項目] 資料夾中的 [刪除] 資料夾。它不是立即清除來自 Office 365。使用者可以設定信箱已刪除的項目保留期間為基礎的持續期間復原刪除的郵件] 資料夾中的郵件。此保留期間到期 （或如果使用者清除前的郵件會到期後），郵件移至 [清除] 資料夾，並不會再使用者存取。一次 [清除] 資料夾中郵件會保留已刪除的項目保留期間如果單一項目復原已啟用信箱的信箱設定為基礎的工期。（Office 365 的單一項目復原預設會啟用時建立新的信箱。）刪除項目保留期間到期後，標記為永久刪除郵件，並將來自 Office 365 清除信箱由受管理的資料夾助理員處理下一次。</span><span class="sxs-lookup"><span data-stu-id="f03f4-p115">If you use the `New-ComplianceSearchAction -Purge -PurgeType SoftDelete` command, messages are moved to the Deletions folder in the user's Recoverable Items folder. It isn't immediately purged from Office 365. The user can recover messages in the Deleted Items folder for the duration based on the deleted item retention period configured for the mailbox. After this retention period expires (or if user purges the message before it expires), the message is moved to the Purges folder and can no longer be accessed by the user. Once in the Purges folder, the message is retained for the duration based on the deleted item retention period configured for the mailbox if single items recovery is enabled for the mailbox. (In Office 365, single item recovery is enabled by default when a new mailbox is created.) After the deleted item retention period expires, the message is marked for permanent deletion and will be purged from Office 365 the next time that the mailbox is processed by the Managed Folder assistant.</span></span> 
    
- <span data-ttu-id="f03f4-180">**如果您必須刪除超過 50000 個信箱的郵件吗？**</span><span class="sxs-lookup"><span data-stu-id="f03f4-180">**What if you have to delete a message from more than 50,000 mailboxes?**</span></span>

    <span data-ttu-id="f03f4-p116">先前所述，您可以執行搜尋，並清除最大值為 50000 信箱上的作業。如果您有執行搜尋並清除超過 50000 個信箱上的作業，請考慮建立暫存搜尋權限篩選就會降低會小於 50000 信箱搜尋的信箱數目。例如，如果您的組織會包含不同部門、 states 或國家的信箱，您可以建立根據其中這些信箱来搜尋的內容信箱的子集您組織中的信箱搜尋的權限篩選器。建立搜尋權限篩選之後，您會建立 （在步驟 1 中所述） 搜尋，然後刪除郵件 （步驟 3 中所述）。然後您可以編輯的篩選來搜尋並清除一組不同的信箱中的郵件。如需建立搜尋權限篩選器的詳細資訊，請參閱 ＜ [Configure 權限的內容搜尋篩選](permissions-filtering-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="f03f4-p116">As previously stated, you can perform a search and purge operation on a maximum of 50,000 mailboxes. If you have to do a search and purge operation on more than 50,000 mailboxes, consider creating temporary search permissions filters that would reduce the number of mailboxes that would be searched to less than 50,000 mailboxes. For example, if your organization contains mailboxes in different departments, states, or countries, you can create a mailbox search permissions filter based on one of those mailbox properties to search a subset of mailboxes in your organization. After you create the search permissions filter, you would create the search (described in Step 1) and then delete the message (described in Step 3). Then you can edit the filter to search for and purge messages in a different set of mailboxes. For more information about creating search permissions filters, see [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md).</span></span>
    
- <span data-ttu-id="f03f4-187">**將會刪除包含在搜尋結果中編製索引的項目吗？**</span><span class="sxs-lookup"><span data-stu-id="f03f4-187">**Will unindexed items included in the search results be deleted?**</span></span>

    <span data-ttu-id="f03f4-188">否，' 新增 ComplianceSearchAction-Purge 命令不會刪除編製索引的項目。</span><span class="sxs-lookup"><span data-stu-id="f03f4-188">No, the  \`New-ComplianceSearchAction -Purge command doesn't delete unindexed items.</span></span> 
    
- <span data-ttu-id="f03f4-189">**如果從已處於就地保留或訴訟暫止狀態或指派給 Office 365 保留原則的信箱刪除郵件發生什麼情況？**</span><span class="sxs-lookup"><span data-stu-id="f03f4-189">**What happens if a message is deleted from a mailbox that has been placed on In-Place Hold or Litigation Hold or is assigned to an Office 365 retention policy?**</span></span>

    <span data-ttu-id="f03f4-p117">郵件已清除，並移至 [清除資料夾之後，郵件會保留直到保留期間到期。若無限制保留持續時間，則會保留項目，直到移除保留或變更的保留期間。</span><span class="sxs-lookup"><span data-stu-id="f03f4-p117">After the message is purged and moved to the Purges folder, the message is retained until the hold duration expires. If the hold duration is unlimited, then items are retained until the hold is removed or the hold duration is changed.</span></span>
    
- <span data-ttu-id="f03f4-192">**為什麼要選擇搜尋及移除這些分散不同安全性 & 規範中心角色群組的工作流程？**</span><span class="sxs-lookup"><span data-stu-id="f03f4-192">**Why is the search and remove workflow divided among different Security & Compliance Center role groups?**</span></span>

    <span data-ttu-id="f03f4-p118">如先前所述人員有 eDiscovery 管理員角色群組的成員或來搜尋信箱的規範搜尋管理角色指派。若要刪除的郵件，人員必須是 「 組織管理角色群組的成員或搜尋和清除管理角色指派。這可讓控制項誰可在組織中搜尋信箱和誰可以刪除郵件。</span><span class="sxs-lookup"><span data-stu-id="f03f4-p118">As previously explained, a person has to be a member of the eDiscovery Manager role group or be assigned the Compliance Search management role to search mailboxes. To delete messages, a person has to be a member of the Organization Management role group or be assigned the Search And Purge management role. This makes it possible to control who can search mailboxes in the organization and who can delete messages.</span></span> 
