---
title: 在 Office 365 系統管理員身分管理隔離的郵件和檔案
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 09/05/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
description: '以系統管理員，您可以檢視、 釋出，並報告誤判隔離的郵件在 Office 365 中。您可以設定原則，讓 Office 365 篩選郵件並傳送至隔離下列幾個原因： 因為他們已識別為垃圾郵件、 大量、 網路釣魚、 惡意程式碼、 或因為其符合某個 [郵件流程規則。 '
ms.openlocfilehash: 67fb4ac8e3a5fd443efb04d4f74e9844d2fa8c86
ms.sourcegitcommit: f7fff49ae0b1c3056faa58d73c1070cb4e638fbf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/25/2018
ms.locfileid: "25018877"
---
# <a name="manage-quarantined-messages-and-files-as-an-administrator-in-office-365"></a><span data-ttu-id="7a3ef-104">在 Office 365 系統管理員身分管理隔離的郵件和檔案</span><span class="sxs-lookup"><span data-stu-id="7a3ef-104">Manage quarantined messages and files as an administrator in Office 365</span></span>

<span data-ttu-id="7a3ef-p102">以系統管理員，您可以檢視、 釋出，並刪除隔離的郵件和報告誤判隔離的郵件在 Office 365 中。您也可以檢視、 下載及刪除隔離的檔案擷取適用換頁威脅保護 (ATP) SharePoint Online、 OneDrive for Business 和 Microsoft 小組。您可以設定原則，讓 Office 365 篩選郵件並傳送至隔離下列幾個原因： 因為他們已識別為垃圾郵件、 大量郵件網路釣魚郵件，其中包含惡意程式碼、 或因為其符合某個 [郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p102">As an admin, you can view, release, and delete quarantined messages, and report false positive quarantined messages in Office 365. You can also view, download, and delete quarantined files captured by Advance Threat Protection (ATP) for SharePoint Online, OneDrive for Business, and Microsoft Teams. You can set up policies so that Office 365 filters messages and sends them to quarantine for several reasons: Because they were identified as spam, bulk mail, phishing mail, containing malware, or because they matched a mail flow rule.</span></span>
  
<span data-ttu-id="7a3ef-p103">根據預設，Office 365 傳送網路釣魚郵件包含惡意程式碼的直接至隔離的郵件。除非您已設定原則以將傳送給他們隔離其他篩選後的郵件傳送到使用者的垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p103">By default, Office 365 sends phishing messages and messages containing malware directly to quarantine. Other filtered messages are sent to users' Junk Email folder unless you set up a policy to send them to quarantine.</span></span>
  
<span data-ttu-id="7a3ef-110">您必須在 Office 365 中使用 [傳送至其他使用者的隔離郵件和使用隔離檔案系統管理員權限。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-110">You must have admin permissions in Office 365 to work with quarantined messages that were sent to other users and to work with quarantined files.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7a3ef-p104">根據預設，垃圾郵件、 大量、 惡意程式碼、 網路釣魚、 及因為它們相符的郵件流程規則已隔離的郵件中保留隔離 30 天。您可以自訂安全性的反垃圾郵件設定] 中的隔離時間&amp;規範中心。當 Office 365 會從隔離刪除郵件時，您無法回復取得。如果想您可以在您的反垃圾郵件篩選器原則中變更隔離郵件的保留的期間。如需詳細資訊，請參閱本文中的[設定隔離保留期限](manage-quarantined-messages-and-files.md#BKMK_ModQuarantineTime)。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p104">By default, spam, bulk, malware, phishing, and messages that were quarantined because they matched a mail flow rule are kept in quarantine for 30 days. You can customize the quarantine time in anti-spam settings in the Security &amp; Compliance Center. When Office 365 deletes a message from quarantine, you can't get it back. If you like, you can change the retention period for quarantined messages in your anti-spam filter policies. For more information, see [Setting the quarantine retention period](manage-quarantined-messages-and-files.md#BKMK_ModQuarantineTime) in this article.</span></span> 
  
## <a name="view-your-organizations-quarantined-messages"></a><span data-ttu-id="7a3ef-116">檢視您的組織隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="7a3ef-116">View your organization's quarantined messages</span></span>

1. <span data-ttu-id="7a3ef-117">使用 Office 365 組織中具有全域系統管理員權限的工作或學校帳戶，登入 Office 365，並[移至 「 安全性及規範中心 」](go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-117">Using a work or school account that has global administrator privileges in your Office 365 organization, sign into Office 365 and [go to the Security and Compliance Center](go-to-the-securitycompliance-center.md).</span></span>
    
2. <span data-ttu-id="7a3ef-118">在左側清單中，依序展開 [ **Threat Management**，並選擇 [**檢閱**，然後選擇 [**隔離**。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-118">In the list on the left, expand **Threat Management**, choose **Review**, and then choose **Quarantine**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="7a3ef-119">若要直接移至 [**隔離**] 頁面上的 [安全性]&amp;規範中心使用此 URL: >[https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span><span class="sxs-lookup"><span data-stu-id="7a3ef-119">To go directly to the **Quarantine** page in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span></span>
  
    <span data-ttu-id="7a3ef-p105">根據預設，安全性&amp;規範中心顯示所有已隔離的電子郵件為垃圾郵件。郵件是從最新到最舊依據排序收到郵件的**日期**。**寄件者**、**主旨**和 （在**到期日**） 的到期日期也會顯示每則訊息。您可以按一下 [對應] 欄標題 ； 排序欄位按一下欄標題第二次反向的排序順序。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p105">By default, the Security &amp; Compliance Center displays all email messages that have been quarantined as spam. The messages are sorted from newest to oldest based on the **Date** the message was received. **Sender**, **Subject**, and the expiration date (under **Expires** ) are also displayed for each message. You can sort on a field by clicking the corresponding column header; click a column header a second time to reverse the sort order.</span></span> 
    
3. <span data-ttu-id="7a3ef-p106">您可以檢視清單中所有的隔離郵件，或您可能會降低結果集中的篩選。您可以只執行大量作業最多 100 個項目，所以篩選也可以協助減少您如果您有多個所設定的結果。可以快速篩選郵件單一隔離原因而從頁面頂端的篩選選擇選項。選項包括：</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p106">You can view a list of all quarantined messages, or you can reduce the result set by filtering. You can only do bulk operations on up to 100 items, so filtering can also help reduce your result set if you have more than that. You can quickly filter messages for a single quarantine reason by choosing an option from the filter at the top of the page. Options include:</span></span>
    
  - <span data-ttu-id="7a3ef-128">識別為垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="7a3ef-128">Mail identified as spam</span></span>
    
  - <span data-ttu-id="7a3ef-129">郵件隔離因為符合 （也稱為傳輸規則） 的郵件流程規則所設定的原則</span><span class="sxs-lookup"><span data-stu-id="7a3ef-129">Mail quarantined because it matched a policy set by a mail flow rule (also called a transport rule)</span></span>
    
  - <span data-ttu-id="7a3ef-130">郵件會被識別為大宗郵件</span><span class="sxs-lookup"><span data-stu-id="7a3ef-130">Mail identified as bulk mail</span></span>
    
  - <span data-ttu-id="7a3ef-131">郵件會被識別為網路釣魚郵件</span><span class="sxs-lookup"><span data-stu-id="7a3ef-131">Mail identified as phishing mail</span></span>
    
  - <span data-ttu-id="7a3ef-132">因為包含惡意程式碼隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="7a3ef-132">Mail quarantined because it contains malware</span></span>
    
<span data-ttu-id="7a3ef-p107">此外，以系統管理員，您可以選擇您的組織的所有郵件，或是僅傳送給您的訊息篩選。結束的使用者可以僅檢視及使用 [傳送給他們的訊息。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p107">In addition, as an admin, you can choose to filter all messages for your organization or only messages sent to you. End users can only view and work with messages sent to them.</span></span>
  
<span data-ttu-id="7a3ef-p108">您也可以篩選結果來尋找特定的郵件。提示，請參閱[來篩選結果和尋找隔離的郵件和檔案](manage-quarantined-messages-and-files.md#BKMK_AdvSearch)本文中。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p108">You can also filter your results to find specific messages. For tips, see [To filter results and find quarantined messages and files](manage-quarantined-messages-and-files.md#BKMK_AdvSearch) in this article.</span></span> 
  
<span data-ttu-id="7a3ef-137">找到特定隔離的郵件之後，按一下 [檢視詳細資訊，郵件並採取動作，例如釋放到某個人的信箱郵件。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-137">After you find a specific quarantined message, click the message to view details about it, and take actions, like releasing the message to someone's mailbox.</span></span>
  
## <a name="view-your-organizations-quarantined-files"></a><span data-ttu-id="7a3ef-138">檢視您的組織隔離的檔案</span><span class="sxs-lookup"><span data-stu-id="7a3ef-138">View your organization's quarantined files</span></span>

1. <span data-ttu-id="7a3ef-139">使用 Office 365 組織中具有全域系統管理員權限的工作或學校帳戶，登入 Office 365，並[移至 「 安全性及規範中心 」](go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-139">Using a work or school account that has global administrator privileges in your Office 365 organization, sign in to Office 365 and [go to the Security and Compliance Center](go-to-the-securitycompliance-center.md).</span></span>
    
2. <span data-ttu-id="7a3ef-140">在左邊，依序展開 [ **Threat Management**，並選擇 [**檢閱**，然後選擇 [**隔離**。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-140">On the left, expand **Threat Management**, choose **Review**, and then choose **Quarantine**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="7a3ef-141">若要直接移至 [**隔離**] 頁面上的 [安全性]&amp;規範中心使用此 URL: >[https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span><span class="sxs-lookup"><span data-stu-id="7a3ef-141">To go directly to the **Quarantine** page in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span></span>
  
3. <span data-ttu-id="7a3ef-p109">根據預設，頁面會顯示隔離的電子郵件訊息。若要檢視隔離的檔案，設定篩選器顯示的**檔案**，因為**惡意程式碼**隔離頁面頂端。您必須在 Office 365 中使用隔離檔案系統管理員權限。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p109">By default, the page displays quarantined email messages. To view quarantined files, set the filters at the top of the page to show **files**, quarantined due to **malware**. You must have admin permissions in Office 365 to work with quarantined files.</span></span> 
    
4. <span data-ttu-id="7a3ef-p110">檔案會排序從最新到最舊根據上檔案遭隔離時的日期。**使用者**上次修改檔案並將**服務**要張貼檔案，**檔案名稱**、**位置**、**檔案大小**及到期日期 （**到期日**） 也會列出每個檔案。您可以按一下標頭; 排序欄位按一下欄標題第二次反向的排序順序。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p110">The files are sorted from newest to oldest based on the date the file was quarantined. The **User** who last modified the file, the **Service** to which the file was posted, the **File Name**, **Location**, **File Size**, and the expiration date ( **Expires**) are also listed for each file. You can sort on a field by clicking a header; click a column header a second time to reverse the sort order.</span></span>
    
<span data-ttu-id="7a3ef-p111">您可以檢視清單中的所有隔離檔案，或您可篩選搜尋特定的檔案。類似郵件，您可以只執行大量作業最多 100 個項目。目前的安全性&amp;規範中心可讓您檢視和管理因為他們已經被識別為包含惡意程式碼會在隔離區中的檔案。提示，請參閱[來篩選結果和尋找隔離的郵件和檔案](manage-quarantined-messages-and-files.md#BKMK_AdvSearch)本文中。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p111">You can view a list of all quarantined files, or you can search for specific files by filtering. Just like messages, you can only do bulk operations on up to 100 items. Currently, the Security &amp; Compliance Center lets you view and manage files that are in quarantine because they have been identified as containing malware. For tips, see [To filter results and find quarantined messages and files](manage-quarantined-messages-and-files.md#BKMK_AdvSearch) in this article.</span></span> 
  
## <a name="to-filter-results-and-find-quarantined-messages-and-files"></a><span data-ttu-id="7a3ef-152">來篩選結果和尋找隔離的郵件和檔案</span><span class="sxs-lookup"><span data-stu-id="7a3ef-152">To filter results and find quarantined messages and files</span></span>
<span data-ttu-id="7a3ef-153"><a name="BKMK_AdvSearch"> </a></span><span class="sxs-lookup"><span data-stu-id="7a3ef-153"></span></span>

<span data-ttu-id="7a3ef-p112">根據您的設定，可能會有許多的隔離的郵件和檔案。若要尋找的特定郵件或檔案或一組郵件或檔案，您可以篩選依據的其他資訊的各種不同的隔離項目。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p112">Depending on your settings, there may be a lot of quarantined messages and files. To find a specific message or file or set of messages or files, you can filter quarantined items based on a variety of additional information.</span></span>
  
1. <span data-ttu-id="7a3ef-156">在 [**隔離**] 頁面上確認頂端列的篩選器設定視需要顯示訊息或檔案：</span><span class="sxs-lookup"><span data-stu-id="7a3ef-156">On the **Quarantine** page, ensure that the top row of filters is set to display messages or files as appropriate:</span></span> 
    
  - <span data-ttu-id="7a3ef-157">若要搜尋的檔案，設定篩選器顯示的**檔案**因為**惡意程式碼**隔離。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-157">To search for files, set the filters to show **files** quarantined due to **malware**.</span></span>
    
    <span data-ttu-id="7a3ef-158">隔離檔案] 頁面上會顯示所有隔離的檔案而不只是以顯示您自己的不論您的告訴 it。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-158">For quarantined files, the page displays all quarantined files, not just your own, regardless of what you tell it to show.</span></span>
    
  - <span data-ttu-id="7a3ef-p113">若要搜尋的隔離郵件，將篩選器以顯示**所有**或**僅我\*\*\*\*電子郵件**。最後一個篩選器] 中選擇隔離之郵件的類型，您在這裡尋找。您可以搜尋隔離的郵件被識別為**垃圾郵件**、 相符的郵件流程或**傳輸規則**、**大宗**郵件、**網路釣魚**郵件或**惡意程式碼**的郵件的郵件。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p113">To search for quarantined messages, set filters to show **all** or **only my** **email**. For the last filter choose the type of quarantined message that you're looking for. You can search for quarantined messages that have been identified as **spam**, for messages that matched a mail flow or **transport rule**, **bulk** mail, **phishing** mail, or mail that contains **malware**.</span></span>
    
2. <span data-ttu-id="7a3ef-p114">在 [**排序結果所**選擇的篩選或您想要使用搜尋下拉式清單中的篩選器。選項會依據您所搜尋的檔案或訊息而有所不同。在搜尋欄位中不支援萬用字元這一次。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p114">Under **Sort results by**, choose the filter or filters you want to use to search from the drop-down lists. The options vary based on whether you are searching for files or messages. Wildcards are not supported in search fields at this time.</span></span>
    
    <span data-ttu-id="7a3ef-p115">檔案和訊息，您可以選擇依日期篩選郵件或檔案被送至隔離。您可以指定日期或含時間的日期範圍。您也可以在其的檔案或訊息將會從隔離刪除您也可以使用的篩選組合的到期日期篩選搜尋結果。若要搜尋的到期日，選擇 [**進階的篩選**]。[**到期日**，您可以選擇將從隔離刪除下一個 24 小時內 （**今天**） 下, 一步 （**下一步 7 天**） 在下一週內 48 小時 （**下一步 2 天**） 內的郵件或您可以選取自訂的時間間隔。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p115">For both files and messages, you can choose to filter by the date the message or file was sent to quarantine. You can specify the date or a date range, including the time. You can also filter your search results by the expiration date on which the file or message will be deleted from quarantine, or you can use a combination of filters. To search by expiration date, choose **Advanced filter**. Under **Expires**, you can select messages that will be deleted from quarantine within the next 24 hours ( **Today**), within the next 48 hours ( **Next 2 days**), within the next week ( **Next 7 days**), or you can select a custom time interval.</span></span>
    
    <span data-ttu-id="7a3ef-170">郵件，您會擁有下列其他選項：</span><span class="sxs-lookup"><span data-stu-id="7a3ef-170">For messages, you have the following additional options:</span></span>
    
  - <span data-ttu-id="7a3ef-p116">**郵件識別碼**。使用此項來識別特定的郵件時您知道訊息識別碼。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p116">**Message ID**. Use this to identify a specific message when you know the message ID.</span></span> 
    
    <span data-ttu-id="7a3ef-p117">例如，如果特定郵件是由傳送或適合您的組織中的使用者，但它永不到達其目的地，您可以搜尋郵件使用郵件追蹤 （請參閱[執行郵件追蹤和檢視結果](https://go.microsoft.com/fwlink/?LinkId=799737)）。如果您發現郵件被送至隔離，可能是因為它符合郵件流程規則或已識別為垃圾郵件，您可以再輕鬆找到此訊息隔離區中指定其訊息識別碼。請務必包含完整的訊息識別碼字串。這可能會包含角括弧 (\<\>)，例如：</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p117">For example, if a specific message is sent by, or intended for, a user in your organization, but it never reached its destination, you can search for the message by using a message trace (see [Run a Message trace and View Results](https://go.microsoft.com/fwlink/?LinkId=799737)). If you discover that the message was sent to quarantine, perhaps because it matched a mail flow rule or was identified as spam, you can then easily find this message in quarantine by specifying its message ID. Be sure to include the full message ID string. This might include angle brackets (\<\>), for example:</span></span>
    
    <span data-ttu-id="7a3ef-177">\<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com\></span><span class="sxs-lookup"><span data-stu-id="7a3ef-177">\<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com\></span></span>
    
  - <span data-ttu-id="7a3ef-p118">**寄件者電子郵件地址**。選擇篩選單一寄件者電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p118">**Sender email address**. Choose to filter by a single sender email address.</span></span> 
    
  - <span data-ttu-id="7a3ef-p119">**收件者電子郵件地址**。選擇篩選單一收件者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p119">**Recipient email address**. Choose to filter by a single recipient email address.</span></span> 
    
  - <span data-ttu-id="7a3ef-p120">**主旨**。輸入您要尋找的電子郵件地址的主旨。由於不支援萬用字元搜尋，您必須使用的搜尋順序整個郵件主旨的結果中傳回的訊息。搜尋不區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p120">**Subject**. Enter the subject of an email address you want to find. Since wildcard searching is not supported, you must use the entire subject of the message in order for search to return the message in the results. The search is not case-sensitive.</span></span> 
    
## <a name="view-details-about-quarantined-messages-and-files"></a><span data-ttu-id="7a3ef-186">檢視詳細資料隔離的郵件和檔案</span><span class="sxs-lookup"><span data-stu-id="7a3ef-186">View details about quarantined messages and files</span></span>
<span data-ttu-id="7a3ef-187"><a name="BKMK_ViewDetails"> </a></span><span class="sxs-lookup"><span data-stu-id="7a3ef-187"></span></span>

<span data-ttu-id="7a3ef-188">當您選取 [隔離] 清單中顯示的項目時，您會看見其**詳細資料**窗格中的屬性摘要安全性右側&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-188">When you select an item displayed in the quarantine list, you'll see a summary of its properties in the **Details** pane on the right side of the Security &amp; Compliance Center.</span></span> 
  
 <span data-ttu-id="7a3ef-189">**顯示的隔離郵件的詳細資訊**</span><span class="sxs-lookup"><span data-stu-id="7a3ef-189">**Details displayed for quarantined messages**</span></span>
  
- <span data-ttu-id="7a3ef-p121">**郵件識別碼**。郵件的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p121">**Message ID**. The unique identifier for the message.</span></span> 
    
- <span data-ttu-id="7a3ef-p122">**寄件者地址**。誰傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p122">**Sender Address**. Who sent the message.</span></span> 
    
- <span data-ttu-id="7a3ef-p123">**接收到**。日期和時間收到郵件。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p123">**Received**. The date and time the message was received.</span></span> 
    
- <span data-ttu-id="7a3ef-p124">**主旨**。郵件的主旨行文字。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p124">**Subject**. The text of the subject line of the message.</span></span> 
    
- <span data-ttu-id="7a3ef-p125">**類型**。會顯示一則訊息是否被識別為**垃圾郵件**、**大量**、 **Phish**、 相符的郵件流程 (規則**傳輸規則**），或已識別為包含**惡意程式碼**。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p125">**Type**. Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule ( **Transport rule**), or was identified as containing **Malware**.</span></span>
    
- <span data-ttu-id="7a3ef-p126">**會到期**。日期及時間時將會自動刪除郵件從隔離區。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p126">**Expires**. The date and time when the message will automatically be deleted from quarantine.</span></span> 
    
- <span data-ttu-id="7a3ef-p127">**若要發行**。所有電子郵件地址 （如果有的話） 給其中具有已釋放郵件。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p127">**Released to**. All email addresses (if any) to which the message has been released.</span></span> 
    
- <span data-ttu-id="7a3ef-p128">**尚未釋出到**。所有的電子郵件地址 （如果有的話） 的郵件尚未已釋放。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p128">**Not yet released to**. All email addresses (if any) to which the message has not yet been released.</span></span> 
    
 <span data-ttu-id="7a3ef-206">**顯示隔離檔案的詳細資料**</span><span class="sxs-lookup"><span data-stu-id="7a3ef-206">**Details displayed for quarantined files**</span></span>
  
- <span data-ttu-id="7a3ef-207">**檔案名稱**隔離區中的檔案名稱。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-207">**File Name** The name of the file in quarantine.</span></span> 
    
- <span data-ttu-id="7a3ef-208">**網站路徑**Office 365 中定義的檔案位置的 URL。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-208">**Site path** URL that defines the location of the file in Office 365.</span></span> 
    
- <span data-ttu-id="7a3ef-209">**偵測到的日期 / 時間**日期及時間遭隔離時的檔案。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-209">**Detected Date / Time** The date and time the file was quarantined.</span></span> 
    
- <span data-ttu-id="7a3ef-210">**過期**郵件從隔離區的刪除時的日期。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-210">**Expires** The date when the message will be deleted from quarantine.</span></span> 
    
- <span data-ttu-id="7a3ef-p129">**所偵測到**用來偵測惡意程式碼檔案中的方法。這可以是 Microsoft 的反惡意程式碼引擎或 ATP （進階威脅保護）。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p129">**Detected By** The method used to detect the malware in the file. This can be either ATP (Advanced Threat Protection) or Microsoft's anti-malware engine.</span></span> 
    
- <span data-ttu-id="7a3ef-213">**發行**說明檔案已經發行。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-213">**Released** Describes whether or not the file has been released.</span></span> 
    
- <span data-ttu-id="7a3ef-214">**惡意程式碼名稱**系列以及檔案中偵測到惡意程式碼的名稱。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-214">**Malware Name** Family and name of the malware detected in the file.</span></span> 
    
- <span data-ttu-id="7a3ef-215">**文件識別碼**文件的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-215">**Document ID** A unique identifier for the document.</span></span> 
    
- <span data-ttu-id="7a3ef-216">**檔案大小**Kb 的檔案大小。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-216">**File Size** The size of the file in KB.</span></span> 
    
- <span data-ttu-id="7a3ef-217">**組織**貴組織的 Office 365 中的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-217">**Organization** Your organization's unique ID in Office 365.</span></span> 
    
- <span data-ttu-id="7a3ef-218">**藉由修改**工作或學校上次修改檔案的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-218">**Modified By** The work or school account of the user who last modified the file.</span></span> 
    
- <span data-ttu-id="7a3ef-219">**檔案大小**Kb 的檔案大小。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-219">**File Size** The size of the file in KB.</span></span> 
    
- <span data-ttu-id="7a3ef-p130">**SHA256 雜湊**檔案的雜湊。您可以使用此查詢他們可能有或調查 else 其中檔案可能會在您的環境中其他信譽存放區。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p130">**SHA256 Hash** The hash of the file. You can use this to look up other reputation stores you may have or investigate where else the file might be in your environment.</span></span> 
    
## <a name="managing-messages-and-files-in-quarantine"></a><span data-ttu-id="7a3ef-222">管理郵件和隔離區中的檔案</span><span class="sxs-lookup"><span data-stu-id="7a3ef-222">Managing messages and files in quarantine</span></span>
<span data-ttu-id="7a3ef-223"><a name="BKMK_ManageQuarantinedItem"> </a></span><span class="sxs-lookup"><span data-stu-id="7a3ef-223"></span></span>

<span data-ttu-id="7a3ef-224">選取 [訊息] 或 [群組的郵件之後必須將訊息管理隔離區中的數個選項。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-224">After you select a message or group of messages you have several options for managing messages in quarantine.</span></span>
  
- <span data-ttu-id="7a3ef-p131">不執行任何動作。如果您選擇不執行任何動作，郵件將會刪除 Office 365 自動後到期。根據預設，垃圾郵件、 大量、 惡意程式碼、 網路釣魚和隔離因為它們相符的郵件流程規則的訊息中保留隔離 30 天。當 Office 365 會從隔離刪除郵件時，您無法回復取得。如果想中，您可以變更隔離郵件的保留的期間 **（天） 的保留天數垃圾郵件**設定反垃圾郵件原則中。如需詳細資訊，請參閱本文中的[設定隔離保留期限](manage-quarantined-messages-and-files.md#BKMK_ModQuarantineTime)。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p131">Do nothing. If you choose to do nothing, the message will be deleted by Office 365 automatically upon expiration. By default, spam, bulk, malware, phishing, and messages quarantined because they matched a mail flow rule are kept in quarantine for 30 days. When Office 365 deletes a message from quarantine, you can't get it back. If you like, you can change the retention period for quarantined messages by configuring the **Retain spam for (days)** setting in your anti-spam policies. For more information, see [Setting the quarantine retention period](manage-quarantined-messages-and-files.md#BKMK_ModQuarantineTime) in this article.</span></span> 
    
- <span data-ttu-id="7a3ef-p132">**檢視郵件標頭**選擇此連結可以看到訊息標頭文字。若要分析深度中的頁首、 訊息標頭文字複製到剪貼簿，然後按**Microsoft 訊息標頭 Analyzer**前往 Remote Connectivity Analyzer （以滑鼠右鍵按一下與如果您不想要保留 Office 選擇 [**新增] 索引標籤中開啟**365 才能完成這項工作)。貼入放入頁面的郵件標頭郵件標頭分析器] 區段中，選擇 [**分析標頭**。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p132">**View message header** Choose this link to see the message header text. To analyze the header in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Office 365 to complete this task).Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**.</span></span>
    
- <span data-ttu-id="7a3ef-p133">**預覽訊息**可讓您原始，請參閱或郵件內文文字的 HTML 版本。在 [HTML] 檢視中會停用的連結。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p133">**Preview message** Lets you see raw or HTML versions of the message body text. In the HTML view, links are disabled.</span></span> 
    
- <span data-ttu-id="7a3ef-p134">**下載郵件**或**下載檔案**。選擇此選項可郵件或檔案下載到本機的裝置。您將需要確認您了解與之前將允許，從隔離區下載項目相關聯的風險。您指定的資料夾.eml 格式所儲存的郵件。隔離的檔案都儲存在其原始格式。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p134">**Download message** or **Download file**. Choose this option to download a copy of the message or file to your local device. You'll need to confirm that you understand the risks associated with downloading items from quarantine before you'll be allowed to do so. Messages are saved in .eml format to a folder you specify. Quarantined files are saved in their original format.</span></span>
    
- <span data-ttu-id="7a3ef-p135">**刪除**如果您想立即刪除而不是等待設定 Office 365 的到期日期隔離的項目 （或一組項目）。若要刪除訊息或檔案中的，[隔離] 清單中選取的項目，然後選擇 [**刪除**。若要一次刪除多個項目，[隔離] 清單中選取的項目左側的核取方塊，然後在出現**大量動作**頁面上，選擇**刪除所選的郵件**] 或 [**刪除選取的檔案**。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p135">**Delete** If you want, you can immediately delete a quarantined item (or set of items) instead of waiting for the expiration date set by Office 365. To delete a message or file, in the quarantine list, select the item and then choose **Delete**. To delete multiple items at once, select the checkbox to the left of the items in the quarantine list, and then on the **Bulk actions** page that appears, choose **Delete selected messages** or **Delete selected files**.</span></span>
    
- <span data-ttu-id="7a3ef-243">**版本**釋出隔離的項目 （或一組項目） 並向 Microsoft 報告為錯誤地隔離 （誤判） 的項目。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-243">**Release** Release a quarantined item (or set of items) and report the items as falsely quarantined (false positives) to Microsoft.</span></span> 
    
    <span data-ttu-id="7a3ef-p136">若要釋放並回報單一郵件或檔案中的，[隔離] 清單中選取的項目中選擇 [**釋出檔案**或**郵件釋出**。在 [下一步] 頁面上，確定已選取 [**報表訊息給 Microsoft 進行分析**或**報告給 Microsoft 進行分析的檔案**。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p136">To release and report a single message or file, in the quarantine list, select the item, choose **Release file** or **Release message**. On the next page, ensure that **report messages to Microsoft for analysis** or **report files to Microsoft for analysis** is selected.</span></span> 
    
    <span data-ttu-id="7a3ef-p137">若要一次釋放多個項目 [隔離] 清單中選取的項目左側的核取方塊，然後在出現**大量動作**頁面上，選擇**版本的檔案**或**釋出的郵件**。在 [下一步] 頁面上，確定已選取 [**報表訊息給 Microsoft 進行分析**或**報告給 Microsoft 進行分析的檔案**。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p137">To release multiple items at once, select the checkbox to the left of the items in the quarantine list, and then on the **Bulk actions** page that appears, choose **Release files** or **Release messages**. On the next page, ensure that **report messages to Microsoft for analysis** or **report files to Microsoft for analysis** is selected.</span></span> 
    
<span data-ttu-id="7a3ef-248">當您正在釋放訊息時，請注意下列：</span><span class="sxs-lookup"><span data-stu-id="7a3ef-248">When you're releasing messages, be aware of the following:</span></span>
  
- <span data-ttu-id="7a3ef-p138">當您同時執行多個郵件大量版本時，郵件已發行給所有原本已識別收件者。如果您只想釋出僅限給特定收件者的郵件，您需要一次釋出的郵件一個與個別識別收件者。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p138">When you perform a bulk release of multiple messages at once, the messages are released to all originally identified recipients. If you only want to release messages only to specific recipients, you need to release the messages one at a time and identify the recipients individually.</span></span>
    
- <span data-ttu-id="7a3ef-251">郵件無法多次發行到相同的收件者。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-251">A message cannot be released more than once to the same recipient.</span></span>
    
- <span data-ttu-id="7a3ef-252">當您正在釋放給多個收件者的訊息時，只有收件者先前未收到訊息會顯示在潛在的收件者清單。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-252">When you're releasing a message to more than one recipient, only recipients who have not previously received the message will appear in the list of potential recipients.</span></span>
    
- <span data-ttu-id="7a3ef-p139">當您選擇報告誤判，如果您釋出的郵件已隔離為垃圾郵件、 大量、 網路釣魚，或含有惡意程式碼時，郵件將也會報告給 Microsoft 的垃圾郵件分析小組。小組會評估及分析郵件，然後根據此分析結果，整個服務的垃圾郵件內容篩選規則可能會調整以允許透過訊息。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p139">When you choose to report false positives, if the message or messages you release were quarantined as spam, bulk, phishing, or as containing malware, the message will also be reported to the Microsoft Spam Analysis Team. The team will evaluate and analyze the message, and, depending on the results of the analysis, the service-wide spam content filter rules may be adjusted to allow the message through.</span></span>
    
## <a name="setting-the-quarantine-retention-period"></a><span data-ttu-id="7a3ef-255">設定隔離保留期限</span><span class="sxs-lookup"><span data-stu-id="7a3ef-255">Setting the quarantine retention period</span></span>
<span data-ttu-id="7a3ef-256"><a name="BKMK_ModQuarantineTime"> </a></span><span class="sxs-lookup"><span data-stu-id="7a3ef-256"></span></span>

<span data-ttu-id="7a3ef-p140">您可以設定多久訊息及取值在到期之前，將會保留在隔離區中的檔案。預設、 隔離項目會保留 30 天。您設定此為您建立的每個原則設定。您也可以修改預設原則本文所述的值。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p140">You can configure how long messages and files will remain in quarantine before they expire. By default, quarantined items are kept for 30 days. You configure this setting for each policy that you create. You can also modify the value for the default policy as described in this article.</span></span> 
  
### <a name="to-modify-the-quarantine-retention-period-for-the-default-spam-filter-policy-in-the-security-and-compliance-center"></a><span data-ttu-id="7a3ef-261">若要修改預設的垃圾郵件篩選器原則隔離保留期限中的安全性和規範中心</span><span class="sxs-lookup"><span data-stu-id="7a3ef-261">To modify the quarantine retention period for the default spam filter policy in the Security and Compliance Center</span></span>

1. <span data-ttu-id="7a3ef-262">使用 Office 365 組織中具有全域系統管理員權限的工作或學校帳戶，登入 Office 365，並[移至 「 安全性及規範中心 」](go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-262">Using a work or school account that has global administrator privileges in your Office 365 organization, sign in to Office 365 and [go to the Security and Compliance Center](go-to-the-securitycompliance-center.md).</span></span>
    
2. <span data-ttu-id="7a3ef-263">在左邊，依序展開 [ **Threat Management**、 選擇 [**原則**]，然後選擇**反垃圾郵件**。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-263">On the left, expand **Threat Management**, choose **Policy**, and then choose **Anti-spam**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="7a3ef-264">若要直接移至 [安全性] 中的**反垃圾郵件**] 頁面上&amp;規範中心使用此 URL: >[https://protection.office.com/?hash=/antispam](https://protection.office.com/?hash=/antispam)</span><span class="sxs-lookup"><span data-stu-id="7a3ef-264">To go directly to the **anti-spam** page in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/?hash=/antispam](https://protection.office.com/?hash=/antispam)</span></span>
  
3. <span data-ttu-id="7a3ef-265">選擇 [**自訂**] 以顯示 [**自訂設定**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-265">Choose **Custom** to display the **Custom settings** tab.</span></span> 
    
4. <span data-ttu-id="7a3ef-266">依序展開 [**預設的垃圾郵件篩選器原則 (一律 ON)** ] 列。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-266">Expand the **Default spam filter policy (always ON)** row.</span></span> 
    
5. <span data-ttu-id="7a3ef-p141">選擇 [**編輯原則**]。預設垃圾郵件篩選器原則的設定出現在新的頁面。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p141">Choose **Edit policy**. The settings for the default spam filter policy appear in a new page.</span></span>
    
6. <span data-ttu-id="7a3ef-269">依序展開 [**垃圾郵件和大量動作**。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-269">Expand **Spam and bulk actions**.</span></span>
    
7. <span data-ttu-id="7a3ef-p142">在 [**隔離** **（天） 的保留天數垃圾郵件**] 文字方塊中輸入您想要保留郵件和檔案隔離區中的 Office 365 的時間量。預設值為 30 天。這也是最大值。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-p142">Under **Quarantine**, in the **Retain spam for (days)** text box, enter the amount of time you want Office 365 to retain messages and files in quarantine. The default is 30 days. This is also the maximum.</span></span> 
    
8. <span data-ttu-id="7a3ef-273">選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="7a3ef-273">Choose **Save**.</span></span>
    

