---
title: 搜尋 Office 365 稽核記錄來疑難排解常見的案例
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
- MET150
- MOE150
description: 您可以使用 Office 365 稽核記錄搜尋工具來協助您疑難排解常見問題，例如調查洩漏的帳戶或找出誰設定信箱的電子郵件轉寄。
ms.openlocfilehash: bf07df7ef0767e525ca3e6ff7f5ce4c637880b80
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296766"
---
# <a name="search-the-office-365-audit-log-to-troubleshoot-common-scenarios"></a><span data-ttu-id="e1863-103">搜尋 Office 365 稽核記錄來疑難排解常見的案例</span><span class="sxs-lookup"><span data-stu-id="e1863-103">Search the Office 365 audit log to troubleshoot common scenarios</span></span>

<span data-ttu-id="e1863-p101">本文說明如何使用 Office 365 稽核記錄搜尋工具來協助您疑難排解一般支援案例。這包括使用稽核記錄，以：</span><span class="sxs-lookup"><span data-stu-id="e1863-p101">This article describes how to use the Office 365 audit log search tool to help you troubleshoot common support scenarios. This includes using the audit log to:</span></span>

- <span data-ttu-id="e1863-106">尋找可用來存取洩漏的帳戶之電腦的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="e1863-106">Find the IP address of the computer used to access a compromised account</span></span>
- <span data-ttu-id="e1863-107">決定誰設定信箱的電子郵件轉寄</span><span class="sxs-lookup"><span data-stu-id="e1863-107">Determine who set up email forwarding for a mailbox</span></span>
- <span data-ttu-id="e1863-108">決定使用者是否刪除信箱中的電子郵件項目</span><span class="sxs-lookup"><span data-stu-id="e1863-108">Determine if a user deleted email items in their mailbox</span></span>
- <span data-ttu-id="e1863-109">判斷使用者建立收件匣規則</span><span class="sxs-lookup"><span data-stu-id="e1863-109">Determine if a user created an inbox rule</span></span>

## <a name="using-the-office-365-audit-log-search-tool"></a><span data-ttu-id="e1863-110">使用 Office 365 稽核記錄搜尋工具</span><span class="sxs-lookup"><span data-stu-id="e1863-110">Using the Office 365 audit log search tool</span></span>

<span data-ttu-id="e1863-p102">每個本文所述的疑難排解案例根據使用 Office 365 安全性 & 規範中心中的稽核記錄搜尋工具。本節列出搜尋稽核記錄所需的權限，並說明的步驟來存取並執行稽核記錄搜尋。每個案例一節提供如何設定稽核記錄搜尋查詢及要符合搜尋準則的稽核記錄中的詳細資訊中尋找的項目相關的特定指示。</span><span class="sxs-lookup"><span data-stu-id="e1863-p102">Each of the troubleshooting scenarios described in this article are based on using the audit log search tool in the Office 365 Security & Compliance Center. This section lists the permissions required to search the audit log and describes the steps to access and run audit log searches. Each scenario section provides specific guidance about how to configure an audit log search query and what to look for in the detailed information in the audit records that match the search criteria.</span></span>

### <a name="permissions-required-to-use-the-audit-log-search-tool"></a><span data-ttu-id="e1863-114">若要使用稽核記錄搜尋工具所需的權限</span><span class="sxs-lookup"><span data-stu-id="e1863-114">Permissions required to use the audit log search tool</span></span>

<span data-ttu-id="e1863-p103">您必須指派 「 僅檢視稽核記錄 」 或 「 稽核記錄角色在 Exchange Online 搜尋 Office 365 稽核記錄。根據預設，這些角色被指派給 Exchange 系統管理中心的 [**權限**] 頁面上相符性管理] 和 [組織管理角色群組。如需詳細資訊，請參閱[管理角色群組在 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkID=730688)。</span><span class="sxs-lookup"><span data-stu-id="e1863-p103">You have to be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online to search the Office 365 audit log. By default, these roles are assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center. For more information, see [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkID=730688).</span></span>

### <a name="running-audit-log-searches"></a><span data-ttu-id="e1863-118">執行稽核記錄搜尋</span><span class="sxs-lookup"><span data-stu-id="e1863-118">Running audit log searches</span></span>

<span data-ttu-id="e1863-p104">本節說明建立和執行稽核記錄搜尋基礎。本文中的每個疑難排解案例中使用這些指示為起點。如需詳細的逐步指示，請參閱 ＜[的搜尋稽核登入 Office 365 安全性 & 規範中心](search-the-audit-log-in-security-and-compliance.md#step-1-run-an-audit-log-search)。</span><span class="sxs-lookup"><span data-stu-id="e1863-p104">This section describes the basics for creating and running audit log searches. Use these instructions as a starting point for each troubleshooting scenario in this article. For more detailed step-by-step instructions, see [Search the audit log in the Office 365 Security & Compliance Center ](search-the-audit-log-in-security-and-compliance.md#step-1-run-an-audit-log-search).</span></span>

1. <span data-ttu-id="e1863-122">移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="e1863-122">Go to [https://protection.office.com](https://protection.office.com).</span></span>
  
2. <span data-ttu-id="e1863-123">使用公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="e1863-123">Sign in to Office 365 using your work or school account.</span></span>

3. <span data-ttu-id="e1863-124">在 [安全性 & 規範中心的左窗格中，按一下 [**搜尋 & 調查** > **稽核記錄搜尋**。</span><span class="sxs-lookup"><span data-stu-id="e1863-124">In the left pane of the Security & Compliance Center, click **Search & investigation** > **Audit log search**.</span></span>
    
    <span data-ttu-id="e1863-125">會顯示 [**稽核記錄搜尋**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="e1863-125">The **Audit log search** page is displayed.</span></span> 
    
    ![設定準則，然後按一下 [搜尋] 執行搜尋](media/8639d09c-2843-44e4-8b4b-9f45974ff7f1.png)
  
4. <span data-ttu-id="e1863-p105">您可以設定下列搜尋準則。注意： 此文章中的每個疑難排解案例會建議設定這些欄位的特定指示。</span><span class="sxs-lookup"><span data-stu-id="e1863-p105">You can configure the following search criteria. Note that each troubleshooting scenario in this article will recommend specific guidance for configuring these fields.</span></span>
    
    <span data-ttu-id="e1863-p106">a.**活動**-[下拉式清單，以顯示您可以搜尋的活動。執行搜尋之後，會顯示只選取活動的稽核記錄。選取 [**顯示所有的活動的結果**會顯示所有符合搜尋準則的活動的結果。您也必須將此欄位留白在某些疑難排解案例。</span><span class="sxs-lookup"><span data-stu-id="e1863-p106">a. **Activities** - Click the drop-down list to display the activities that you can search for. After you run the search, only the audit records for the selected activities are displayed. Selecting **Show results for all activities** will display results for all activities that meet the other search criteria. You'll also have to leave this field blank in some of the troubleshooting scenarios.</span></span>
    
    <span data-ttu-id="e1863-p107">b.**開始日期**] 及 [**結束日期**-選取以顯示該期間內發生之事件的日期和時間範圍。預設會選取過去 7 天。以國際標準時間 (UTC) 格式所呈現的日期和時間。您可以指定的最大的日期範圍為 90 天。</span><span class="sxs-lookup"><span data-stu-id="e1863-p107">b. **Start date** and **End date** - Select a date and time range to display the events that occurred within that period. The last seven days are selected by default. The date and time are presented in Coordinated Universal Time (UTC) format. The maximum date range that you can specify is 90 days.</span></span>

    <span data-ttu-id="e1863-p108">c.**使用者**在此方塊和再選取一或多個使用者按一下 [顯示搜尋結果的。選取您在此方塊中選取的使用者所執行的活動的稽核記錄所顯示的結果清單中。保留此方塊空白以傳回組織中的所有使用者 （及服務帳戶） 的項目。</span><span class="sxs-lookup"><span data-stu-id="e1863-p108">c. **Users** - Click in this box and then select one or more users to display search results for. Audit records for the selected activity performed by the users you select in this box are displayed in the list of results. Leave this box blank to return entries for all users (and service accounts) in your organization.</span></span>
    
    <span data-ttu-id="e1863-p109">d.**檔案、 資料夾或網站**-輸入某些或所有搜尋資料夾包含指定之的關鍵字的檔案相關的活動的檔案或資料夾名稱。您也可以指定的檔案或資料夾的 URL。如果您使用的 URL，請確定此類型的完整的 URL 路徑或如果您只需要輸入 URL 部分不會包含任何特殊字元或空格。保留此方塊空白以傳回組織中的所有檔案及資料夾的項目。此欄位空白中所有的疑難排解案例本文中的記事。</span><span class="sxs-lookup"><span data-stu-id="e1863-p109">d. **File, folder, or site** - Type some or all of a file or folder name to search for activity related to the file of folder that contains the specified keyword. You can also specify a URL of a file or folder. If you use a URL, be sure the type the full URL path or if you just type a portion of the URL, don't include any special characters or spaces. Leave this box blank to return entries for all files and folders in your organization. Note that this field is left blank in all the troubleshooting scenarios in this article.</span></span>
    
5. <span data-ttu-id="e1863-149">按一下 [**搜尋**來執行使用搜尋準則的 [搜尋]。</span><span class="sxs-lookup"><span data-stu-id="e1863-149">Click **Search** to run the search using your search criteria.</span></span> 
    
    <span data-ttu-id="e1863-p110">會載入搜尋結果，並在幾分鐘之後時顯示下**結果\*\*\*\*稽核記錄搜尋**] 頁面上。每個的下列各節會提供有關要查看特定的疑難排解案例的事項指引。</span><span class="sxs-lookup"><span data-stu-id="e1863-p110">The search results are loaded, and after a few moments they are displayed under **Results** on the **Audit log search** page. Each to the following sections will provide guidance about things to look for the specific troubleshooting scenario.</span></span>

    <span data-ttu-id="e1863-152">如需檢視、 篩選或匯出稽核記錄搜尋結果的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="e1863-152">For more information about viewing, filtering, or exporting audit log search results, see:</span></span>

    - [<span data-ttu-id="e1863-153">檢視搜尋結果</span><span class="sxs-lookup"><span data-stu-id="e1863-153">View search results</span></span>](search-the-audit-log-in-security-and-compliance.md#step-2-view-the-search-results)
    - [<span data-ttu-id="e1863-154">篩選搜尋結果</span><span class="sxs-lookup"><span data-stu-id="e1863-154">Filter search results</span></span>](search-the-audit-log-in-security-and-compliance.md#step-3-filter-the-search-results)
    - [<span data-ttu-id="e1863-155">匯出搜尋結果</span><span class="sxs-lookup"><span data-stu-id="e1863-155">Export search results</span></span>](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file)

## <a name="finding-the-ip-address-of-the-computer-used-to-access-a-compromised-account"></a><span data-ttu-id="e1863-156">尋找可用來存取洩漏的帳戶之電腦的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="e1863-156">Finding the IP address of the computer used to access a compromised account</span></span>

<span data-ttu-id="e1863-p111">對應至執行的任何使用者活動的 IP 位址包含在大部分的稽核記錄中。稽核記錄中也包含使用的用戶端的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="e1863-p111">The IP address corresponding to an activity performed by any user is included in most audit records. Information about the client used is also included in the audit record.</span></span>

<span data-ttu-id="e1863-159">以下是如何設定此案例的稽核記錄搜尋查詢：</span><span class="sxs-lookup"><span data-stu-id="e1863-159">Here's how to configure an audit log search query for this scenario:</span></span>

<span data-ttu-id="e1863-p112">**活動**-如果您案例相關，選取要搜尋特定的活動。疑難排解洩漏帳戶，請考慮選取 [ **Exchange 信箱活動**的**使用者登入信箱**活動。這會傳回顯示登入信箱時所使用的 IP 位址的稽核記錄。否則請將此欄位留白以傳回所有的活動的稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="e1863-p112">**Activities** - If relevant to your case, select a specific activity to search for. For troubleshooting compromised accounts, consider selecting the **User signed in to mailbox** activity under **Exchange mailbox activities**. This will return auditing records showing the IP address that was use when signing in to the mailbox. Otherwise, leave this field blank to return audit records for all activities.</span></span> 

> [!TIP]
> <span data-ttu-id="e1863-p113">此欄位留白將會傳回**UserLoggedIn**活動表示某人已登入 Office 365 使用者帳戶的 Azure Active Directory 活動。使用篩選搜尋結果中顯示**UserLoggedIn**稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="e1863-p113">Leaving this field blank will  return **UserLoggedIn** activities, which is an Azure Active Directory activity that indicates that someone has signed in to an Office 365 user account. Use filtering in the search results to display the **UserLoggedIn** audit records.</span></span>

<span data-ttu-id="e1863-166">**開始日期**和**結束日期**-選取適用於您正在調查的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="e1863-166">**Start date** and **End date** - Select a date range that's applicable to your investigation.</span></span>

<span data-ttu-id="e1863-p114">**使用者**-如果您正在調查洩漏的帳戶，選取其帳戶已危害的使用者。這會傳回該使用者帳戶所執行的活動的稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="e1863-p114">**Users** - If you're investigating a compromised account, select the user whose account was compromised. This will return audit records for activities performed by that user account.</span></span>

<span data-ttu-id="e1863-169">**檔案、 資料夾或網站**層離開此欄位空白。</span><span class="sxs-lookup"><span data-stu-id="e1863-169">**File, folder, or site** - Leave this field blank.</span></span>

<span data-ttu-id="e1863-p115">執行搜尋之後，每個活動的 IP 位址會顯示在搜尋結果中的 [ **IP 位址**] 欄位。按一下 [檢視彈出式] 頁面上的詳細的資訊將搜尋結果中的記錄。</span><span class="sxs-lookup"><span data-stu-id="e1863-p115">After you run the search, the IP address for each activity is displayed in the **IP address** column in the search results. Click the record in the search results to view more detailed information on the flyout page.</span></span>

## <a name="determining-who-set-up-email-forwarding-for-a-mailbox"></a><span data-ttu-id="e1863-172">決定誰設定信箱的電子郵件轉寄</span><span class="sxs-lookup"><span data-stu-id="e1863-172">Determining who set up email forwarding for a mailbox</span></span>

<span data-ttu-id="e1863-p116">當電子郵件轉寄設定信箱時，就會傳送給信箱的電子郵件轉寄給另一個信箱。郵件可以轉接至企業內或組織外的使用者。時在信箱上設定電子郵件轉寄，基礎 Exchange Online 指令程式用為**Set-mailbox**。</span><span class="sxs-lookup"><span data-stu-id="e1863-p116">When email forwarding is configured for a mailbox, email messages that are sent to the mailbox are forwarded to another mailbox. Messages can be forwarded to users inside or outside of your organization. When email forwarding is set up on a mailbox, the underlying Exchange Online cmdlet that's used is **Set-Mailbox**.</span></span>

<span data-ttu-id="e1863-176">以下是如何設定此案例的稽核記錄搜尋查詢：</span><span class="sxs-lookup"><span data-stu-id="e1863-176">Here's how to configure an audit log search query for this scenario:</span></span>

<span data-ttu-id="e1863-p117">**活動**-保留空白，讓搜尋傳回的所有活動的稽核記錄此欄位。這會傳回任何必要稽核與**Set-mailbox**指令程式相關的記錄。</span><span class="sxs-lookup"><span data-stu-id="e1863-p117">**Activities** - Leave this field blank so that the search returns audit records for all activities. This is necessary to return any audit records related to the **Set-Mailbox** cmdlet.</span></span>

<span data-ttu-id="e1863-179">**開始日期**和**結束日期**-選取適用於您正在調查的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="e1863-179">**Start date** and **End date** - Select a date range that's applicable to your investigation.</span></span>

<span data-ttu-id="e1863-p118">**使用者**-除非您正在調查的電子郵件轉寄特定使用者的問題，此欄位請保留空白。這可協助您識別如果電子郵件轉寄已設定的任何使用者。</span><span class="sxs-lookup"><span data-stu-id="e1863-p118">**Users** - Unless you're investigating a email forwarding issue for a specific user, leave this field blank. This will help you identify if email forwarding was set up for any user.</span></span>

<span data-ttu-id="e1863-182">**檔案、 資料夾或網站**層離開此欄位空白。</span><span class="sxs-lookup"><span data-stu-id="e1863-182">**File, folder, or site** - Leave this field blank.</span></span>

<span data-ttu-id="e1863-p119">執行搜尋之後，按一下 [搜尋結果頁面上的**篩選結果**。在 [**活動**] 欄標題] 方塊中輸入**Set-mailbox**使僅有稽核記錄的相關**Set-mailbox**指令程式會顯示。</span><span class="sxs-lookup"><span data-stu-id="e1863-p119">After you run the search, click **Filter results** on the search results page. In the box under **Activity** column header, type **Set-Mailbox** so that only audit records related to the **Set-Mailbox** cmdlet are displayed.</span></span>

![篩選稽核記錄搜尋的結果](media/emailforwarding1.png)

<span data-ttu-id="e1863-p120">此時，您必須查看每個稽核記錄，以判斷活動會與電子郵件轉寄的詳細資料。按一下 [顯示**詳細資料**彈出式] 頁面的稽核記錄，然後按一下 [**詳細資訊**。下列螢幕擷取畫面及描述重點信箱已設定指出電子郵件轉寄的資訊。</span><span class="sxs-lookup"><span data-stu-id="e1863-p120">At this point, you have to look at the details of each audit record to determine if the activity is related to email forwarding. Click the audit record to display the **Details** flyout page, and then click **More information**. The following screenshot and descriptions highlights the information that indicates email forwarding was set on the mailbox.</span></span>

![稽核記錄的詳細的資訊](media/emailforwarding2.png)

<span data-ttu-id="e1863-p121">a. **ObjectId**欄位中，已設定電子郵件轉寄的信箱的別名上會顯示。這個信箱也會顯示在 [**項目**] 欄中的搜尋結果頁面上。</span><span class="sxs-lookup"><span data-stu-id="e1863-p121">a. In the **ObjectId** field, the alias of the mailbox that email forwarding was set on is displayed. This mailbox is also displayed on the **Item** column in the search results page.</span></span>

<span data-ttu-id="e1863-p122">b.在 [**參數**] 欄位值*ForwardingSmtpAddress*會表示上信箱的電子郵件轉寄尚未設定。在此範例中是郵件轉寄給電子郵件地址 mike@contoso.com，這是 alpinehouse.onmicrosoft.com 組織外部。</span><span class="sxs-lookup"><span data-stu-id="e1863-p122">b. In the **Parameters** field, The value *ForwardingSmtpAddress* indicates that email forward has been set on the mailbox. In this example, mail is being forwarded to the email address mike@contoso.com, which is outside of the alpinehouse.onmicrosoft.com organization.</span></span>

<span data-ttu-id="e1863-p123">c*則為 True*值*DeliverToMailboxAndForward*參數表示郵件傳送到 sarad@alpinehouse.onmicrosoft.com*及*的複本會轉寄給*ForwardingSmtpAddress 所指定的電子郵件地址*參數，在本例中為 mike@contoso.com。如果*DeliverToMailboxAndForward*參數的值設為*False*，然後電子郵件僅遞給*ForwardingSmtpAddress*參數所指定的地址。它不會傳遞至**ObjectId** ] 欄位中所指定的信箱。</span><span class="sxs-lookup"><span data-stu-id="e1863-p123">c. The *True* value for the *DeliverToMailboxAndForward* parameter indicates that a copy of message delivered to sarad@alpinehouse.onmicrosoft.com *and* is forwarded to the email address specified by the *ForwardingSmtpAddress* parameter, which in this example is mike@contoso.com. If the value for the *DeliverToMailboxAndForward* parameter is set to *False*, then email is only forwarded to the address specified by the *ForwardingSmtpAddress* parameter. It's not delivered to the mailbox specified in the **ObjectId** field.</span></span>

<span data-ttu-id="e1863-p124">d. **UserId**欄位指出**ObjectId**欄位] 欄位中所指定的信箱設定電子郵件轉寄的使用者。這位使用者也會顯示在搜尋結果頁面上的 [**使用者**] 欄中。在此例中看來之信箱的擁有者其信箱上設定電子郵件轉寄。</span><span class="sxs-lookup"><span data-stu-id="e1863-p124">d. The **UserId** field indicates the user who set email forwarding on the mailbox specified in the **ObjectId** field field. This user is also displayed in the **User** column on the search results page. In this case, it seems that the owner of the mailbox set email forwarding on her mailbox.</span></span>

<span data-ttu-id="e1863-204">如果您決定不應該信箱上設定電子郵件轉寄，您可以在 Exchange Online PowerShell 中執行下列命令來移除：</span><span class="sxs-lookup"><span data-stu-id="e1863-204">If you determine that email forwarding shouldn't be set on the mailbox, you can remove it by running the following command in Exchange Online PowerShell:</span></span>

```
Set-Mailbox <mailbox alias> -ForwardingSmtpAddress $null 
```

<span data-ttu-id="e1863-205">請參閱[Set-mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)相關電子郵件轉寄的參數的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="e1863-205">See the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) article for more information about the parameters related to email forwarding.</span></span>

## <a name="determining-if-a-user-deleted-email-items"></a><span data-ttu-id="e1863-206">決定使用者是否刪除電子郵件項目</span><span class="sxs-lookup"><span data-stu-id="e1863-206">Determining if a user deleted email items</span></span>

<span data-ttu-id="e1863-p125">刪除稽核記錄檔記錄有關之前電子郵件項目儲存至 Office 365 稽核記錄檔、 在組織中每個使用者信箱啟用信箱稽核具有。此外，SoftDelete 和 HardDelete 信箱動作已啟用稽核。指示，請參閱[啟用信箱稽核 Office 365 中](enable-mailbox-auditing.md)。如果使用者已啟用信箱稽核，請使用下列步驟來搜尋稽核記錄已刪除的電子郵件項目的相關的事件。</span><span class="sxs-lookup"><span data-stu-id="e1863-p125">Before audit log records about deleted email items are saved to the Office 365 audit log, mailbox auditing has to be enabled for each user mailbox in your organization. Additionally, the SoftDelete and HardDelete mailbox actions have to be enabled for auditing. For instructions, see [Enable mailbox auditing in Office 365](enable-mailbox-auditing.md). If mailbox auditing is already enabled for users, use the following steps to search the audit log for events related to deleted email items.</span></span>

<span data-ttu-id="e1863-211">以下是如何設定此案例的稽核記錄搜尋查詢：</span><span class="sxs-lookup"><span data-stu-id="e1863-211">Here's how to configure an audit log search query for this scenario:</span></span>

<span data-ttu-id="e1863-212">**活動**-下**Exchange 信箱活動**選取一或兩個下列活動：</span><span class="sxs-lookup"><span data-stu-id="e1863-212">**Activities** - Under **Exchange mailbox activities**, select one or both of the following activities:</span></span>

- <span data-ttu-id="e1863-p126">**從 [刪除的郵件] 資料夾刪除的郵件**-此活動會對應至**SoftDelete**信箱稽核巨集指令。此活動也會記錄使用者選取它，並按下**Shift + Delete**永久刪除項目。永久刪除項目之後，使用者可以復原它直到刪除項目保留期間到期。</span><span class="sxs-lookup"><span data-stu-id="e1863-p126">**Deleted messages from Deleted Items folder** -  This activity corresponds to the **SoftDelete** mailbox auditing action. This activity is also logged when a user permanently deletes an item by selecting it and pressing **Shift+Delete**. After an item is permanently deleted, the user can recover it until the deleted item retention period expires.</span></span>

- <span data-ttu-id="e1863-p127">**從信箱 Purged 郵件**-此活動會對應至**HardDelete**信箱稽核巨集指令。這會記錄時使用者清除項目從 [可復原的項目] 資料夾。系統管理員可以使用在 Office 365 安全性 & 規範中心內容搜尋工具來搜尋並保留清除復原的項目直到刪除項目保留期間到期或更久是否為使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="e1863-p127">**Purged messages from mailbox** - This activity corresponds to the **HardDelete** mailbox auditing action. This is logged when a user purges an item from the Recoverable Items folder. Admins can use the Content Search tool in the Office 365 Security & Compliance Center to search for and recover purged items until the deleted item retention period expires or longer if the user's mailbox is on hold.</span></span>

<span data-ttu-id="e1863-219">**開始日期**和**結束日期**-選取適用於您正在調查的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="e1863-219">**Start date** and **End date** - Select a date range that's applicable to your investigation.</span></span>

<span data-ttu-id="e1863-p128">**使用者**-如果您在此欄位中選取使用者、 稽核記錄搜尋工具會傳回由指定使用者已刪除的郵件 （SoftDeleted 或 HardDeleted） 的電子郵件項目的稽核記錄。在某些情況下，刪除電子郵件的使用者可能不是信箱擁有者。</span><span class="sxs-lookup"><span data-stu-id="e1863-p128">**Users** - If you select a user in this field, the audit log search tool will return audit records for email items that were deleted (SoftDeleted or HardDeleted) by the user you specify. In some cases, the user who deletes an email might not be the mailbox owner.</span></span>

<span data-ttu-id="e1863-222">**檔案、 資料夾或網站**層離開此欄位空白。</span><span class="sxs-lookup"><span data-stu-id="e1863-222">**File, folder, or site** - Leave this field blank.</span></span>

<span data-ttu-id="e1863-p129">執行搜尋之後，您可篩選搜尋結果顯示稽核記錄的硬碟已刪除的項目或的虛刪除項目。按一下 [顯示**詳細資料**彈出式] 頁面的稽核記錄，然後按一下 [**詳細資訊**。已刪除的項目，例如主旨行及時所刪除之項目的位置的其他資訊會顯示在 [ **AffectedItems** ] 欄位。下列螢幕擷取畫面顯示虛刪除的項目及硬碟已刪除的項目**AffectedItems**欄位的範例。</span><span class="sxs-lookup"><span data-stu-id="e1863-p129">After you run the search, you can filter the search results to display the audit records for soft-deleted items or for hard-deleted items. Click the audit record to display the **Details** flyout page, and then click **More information**. Additional information about the deleted item, such as the subject line and the location of the item when it was deleted, is displayed in the **AffectedItems** field. The following screenshots show an example of the **AffectedItems** field from a soft-deleted item and a hard-deleted item.</span></span>

<span data-ttu-id="e1863-227">**虛刪除項目的 AffectedItems 欄位的範例**</span><span class="sxs-lookup"><span data-stu-id="e1863-227">**Example of AffectedItems field for soft-deleted item**</span></span>

![虛刪除項目的稽核記錄](media/softdeleteditem.png)

<span data-ttu-id="e1863-229">**硬碟已刪除的項目 AffectedItems 欄位的範例**</span><span class="sxs-lookup"><span data-stu-id="e1863-229">**Example of AffectedItems field for hard-deleted item**</span></span>

![硬碟已刪除電子郵件項目的稽核記錄](media/harddeleteditem.png)

### <a name="recovering-deleted-email-items"></a><span data-ttu-id="e1863-231">復原刪除的電子郵件項目</span><span class="sxs-lookup"><span data-stu-id="e1863-231">Recovering deleted email items</span></span>

<span data-ttu-id="e1863-p130">如果刪除的項目保留期間未過期的使用者可以復原虛刪除的項目。在 Exchange Online 中，預設已刪除的項目保留期間為 14 天，但系統管理員可以增加此設定最大值為 30 天。[復原刪除的項目或網路上的 Outlook 電子郵件](https://support.office.com/article/Recover-deleted-items-or-email-in-Outlook-Web-App-C3D8FC15-EEEF-4F1C-81DF-E27964B7EDD4)本文的指示在復原點使用者刪除項目。</span><span class="sxs-lookup"><span data-stu-id="e1863-p130">Users can recover soft-deleted items if the deleted items retention period has not expired. In Exchange Online, the default deleted items retention period is 14 days, but admins can increase this setting to a maximum of 30 days. Point users to the [Recover deleted items or email in Outlook on the web](https://support.office.com/article/Recover-deleted-items-or-email-in-Outlook-Web-App-C3D8FC15-EEEF-4F1C-81DF-E27964B7EDD4) article for instructions on recovering deleted items.</span></span>

<span data-ttu-id="e1863-p131">如先前所述，系統管理員可能會無法復原硬碟已刪除的項目如果已刪除的項目保留期間未過期或信箱時保留，直到保留期間到期的項目保留在此情況下。當您執行內容的搜尋時，虛刪除與硬刪除 [可復原的項目] 資料夾中的項目會傳回搜尋結果中符合搜尋查詢。如需執行內容的搜尋的詳細資訊，請參閱[Office 365 中的內容搜尋](content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="e1863-p131">As previously explained, admins might be able to recover hard-deleted items if the deleted item retention period has not expired or if the mailbox is on hold, in which case items are retained until the hold duration expires. When you run a content search, soft-deleted and hard-deleted items in the Recoverable Items folder are returned in the search results if they match the search query. For more information about running content searches, see [Content Search in Office 365](content-search.md).</span></span>

> [!TIP]
> <span data-ttu-id="e1863-238">若要搜尋的已刪除的電子郵件項目，搜尋全部或部分的主旨行中的稽核記錄的**AffectedItems**欄位所顯示。</span><span class="sxs-lookup"><span data-stu-id="e1863-238">To search for deleted email items, search for all or part of the subject line that's displayed in the **AffectedItems** field in the audit record.</span></span>

## <a name="determining-if-a-user-created-an-inbox-rule"></a><span data-ttu-id="e1863-239">決定使用者是否建立收件匣規則</span><span class="sxs-lookup"><span data-stu-id="e1863-239">Determining if a user created an inbox rule</span></span>

<span data-ttu-id="e1863-p132">當使用者建立自己的 Exchange Online 信箱的收件匣規則時、 相對應的稽核記錄會儲存在稽核記錄。如需收件匣規則的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="e1863-p132">When users create an inbox rule for their Exchange Online mailbox, a corresponding audit record is saved to the audit log. For more information about inbox rules, see:</span></span>

- [<span data-ttu-id="e1863-242">使用網路上的 Outlook 中的收件匣規則</span><span class="sxs-lookup"><span data-stu-id="e1863-242">Use inbox rules in Outlook on the web</span></span>](https://support.office.com/article/use-inbox-rules-in-outlook-on-the-web-8400435c-f14e-4272-9004-1548bb1848f2)
- [<span data-ttu-id="e1863-243">使用規則管理在 Outlook 中的電子郵件</span><span class="sxs-lookup"><span data-stu-id="e1863-243">Manage email messages in Outlook by using rules</span></span>](https://support.office.com/article/Manage-email-messages-by-using-rules-C24F5DEA-9465-4DF4-AD17-A50704D66C59)

<span data-ttu-id="e1863-244">以下是如何設定此案例的稽核記錄搜尋查詢：</span><span class="sxs-lookup"><span data-stu-id="e1863-244">Here's how to configure an audit log search query for this scenario:</span></span>

<span data-ttu-id="e1863-245">**活動**- **Exchange 信箱活動**，選取 [ **New-inboxrule 建立/修改/啟用/停用收件匣規則**。</span><span class="sxs-lookup"><span data-stu-id="e1863-245">**Activities** - Under **Exchange mailbox activities**, select **New-InboxRule Create/modify/enable/disable inbox rule**.</span></span>

<span data-ttu-id="e1863-246">**開始日期**和**結束日期**-選取適用於您正在調查的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="e1863-246">**Start date** and **End date** - Select a date range that's applicable to your investigation.</span></span>

<span data-ttu-id="e1863-p133">**使用者**-除非您正在調查的特定使用者，將此欄位留白。這可協助您識別新任何使用者所設定的收件匣規則。</span><span class="sxs-lookup"><span data-stu-id="e1863-p133">**Users** - Unless you're investigating a specific user, leave this field blank. This will help you identify new inbox rules set up by any user.</span></span>

<span data-ttu-id="e1863-249">**檔案、 資料夾或網站**層離開此欄位空白。</span><span class="sxs-lookup"><span data-stu-id="e1863-249">**File, folder, or site** - Leave this field blank.</span></span>

<span data-ttu-id="e1863-p134">執行搜尋之後，此活動的任何稽核記錄會顯示在搜尋結果中。按一下 [顯示**詳細資料**彈出式] 頁面的稽核記錄，然後按一下 [**的詳細資訊**。收件匣規則設定的相關資訊會顯示在 [**參數**] 欄位。下列螢幕擷取畫面及描述醒目提示收件匣規則的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="e1863-p134">After you run the search, any audit records for this activity are displayed in the search results. Click an audit record to display the **Details** flyout page, and then click **More information**. Information about the inbox rule settings are displayed in the **Parameters** field. The following screenshot and descriptions highlights the information about inbox rules.</span></span>

![新的收件匣規則的稽核記錄](media/NewInboxRuleRecord.png)

<span data-ttu-id="e1863-p135">a. **ObjectId**欄位中，會顯示收件匣規則的完整名稱。此名稱包含使用者的信箱 (例如 SaraD) 的別名和收件匣規則 （例如"移動郵件從系統"） 的名稱。</span><span class="sxs-lookup"><span data-stu-id="e1863-p135">a. In the **ObjectId** field, the full name of the inbox rule is displayed. This name includes the alias of the user's mailbox (for example, SaraD) and the name of the inbox rule (for example, "Move messages from admin").</span></span>

<span data-ttu-id="e1863-p136">b.在 [**參數**] 欄位會顯示收件匣規則的條件。在這個範例中，*從*參數指定的條件。定義*從*參數的值會指出收件匣規則會對 admin@alpinehouse.onmicrosoft.com 所傳送的電子郵件。可以用來定義的收件匣規則條件的參數的完整清單，請參閱[New-inboxrule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-inboxrule)文章。</span><span class="sxs-lookup"><span data-stu-id="e1863-p136">b. In the **Parameters** field, the condition of the inbox rule is displayed. In this example, the condition is specified by the *From* parameter. The value defined for the *From* parameter indicates that the inbox rule acts on email sent by admin@alpinehouse.onmicrosoft.com. For a complete list of the parameters that can be used to define conditions of inbox rules, see the [New-InboxRule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-inboxrule) article.</span></span>

<span data-ttu-id="e1863-p137">c. *MoveToFolder*參數指定的收件匣規則動作 ；在這個範例中，從 admin@alpinehouse.onmicrosoft.com 接收的郵件會移至名為*AdminSearch*資料夾。也請參閱[New-inboxrule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-inboxrule)的完整清單可以用來定義的收件匣規則動作的參數。</span><span class="sxs-lookup"><span data-stu-id="e1863-p137">c. The *MoveToFolder* parameter specifies the action for the inbox rule; in this example, messages received from admin@alpinehouse.onmicrosoft.com are moved to the folder named *AdminSearch*. Also see the [New-InboxRule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-inboxrule) article for a complete list of parameters that can used to define the action of an inbox rule.</span></span>

<span data-ttu-id="e1863-p138">d. **UserId**欄位指出建立**ObjectId** field 中指定的收件匣規則的使用者。這位使用者也會顯示在搜尋結果頁面上的 [**使用者**] 欄中。</span><span class="sxs-lookup"><span data-stu-id="e1863-p138">d. The **UserId** field indicate the user who created the inbox rule specified in the **ObjectId** field. This user is also displayed in the **User** column on the search results page.</span></span>