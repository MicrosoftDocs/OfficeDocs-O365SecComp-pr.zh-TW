---
title: 以系統管理員身分找到並釋放被隔離的郵件
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 6/16/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ab95bf17-bb09-4dd1-9990-ddd02ddecf05
ms.collection:
- M365-security-compliance
description: 本主題說明如何 Exchange Online 和 Exchange Online Protection (EOP) 系統管理員可以尋找、 釋出，並回報被隔離的郵件在 Exchange 系統管理中心 (EAC) 上。
ms.openlocfilehash: aec067169b343ed186d506ed33c29385a7dc6450
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341784"
---
# <a name="find-and-release-quarantined-messages-as-an-administrator"></a><span data-ttu-id="287fc-103">以系統管理員身分找到並釋放被隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="287fc-103">Find and release quarantined messages as an administrator</span></span>

<span data-ttu-id="287fc-p101">本主題說明如何 Exchange Online 和 Exchange Online Protection (EOP) 系統管理員可以尋找、 釋出，並回報被隔離的郵件在 Exchange 系統管理中心 (EAC) 上。Office 365 會指示 [隔離郵件因為被判定為垃圾郵件或符合郵件流程規則 （也稱為傳輸規則）。</span><span class="sxs-lookup"><span data-stu-id="287fc-p101">This topic describes how Exchange Online and Exchange Online Protection (EOP) admins can find, release, and report on quarantined messages in the Exchange admin center (EAC). Office 365 directs messages to quarantine either because they were identified as spam or they matched a mail flow rule (also known as a transport rule).</span></span> 
  
<span data-ttu-id="287fc-p102">使用安全性<b0></b0>合規性中心，而不是 EAC 中完成任何這些工作，以及檢視和使用已傳送至隔離區，因為它們包含惡意程式碼的郵件。如需詳細資訊，請參閱 < <b1>Office 365 中的隔離電子郵件</b1>。</span><span class="sxs-lookup"><span data-stu-id="287fc-p102">Use the Security &amp; Compliance Center instead of the EAC to complete any of these tasks as well as view and work with messages that were sent to quarantine because they contain malware. For more information, see [Quarantine email messages in Office 365](https://support.office.com/article/Quarantine-email-messages-in-Office-365-4c234874-015e-4768-8495-98fcccfc639b).</span></span>
  
<span data-ttu-id="287fc-p103">隔離的郵件會列在 EAC 中的 [**隔離**] 頁面上。根據預設，郵件會依最新到最舊的在**收到日期**] 欄位。也列出每封郵件的**寄件者**、**主旨**及**到期日**的值。您可以排序這些任一欄位按一下欄標頭。如果您按一下欄標題，第二次，就會回復的排序順序。[**隔離**] 頁面上會顯示 500 封郵件的最大值。</span><span class="sxs-lookup"><span data-stu-id="287fc-p103">Quarantined messages are listed on the **quarantine** page in EAC. By default, messages are sorted from newest to oldest on the **RECEIVED** field. **SENDER**, **SUBJECT**, and **EXPIRES** values are also listed for each message. You can sort on any of these fields by clicking their headers. If you click a column header a second time, the sort order reverses. The **quarantine** page displays a maximum of 500 messages.</span></span> 
  
<span data-ttu-id="287fc-p104">您可以檢視清單中的所有隔離的郵件，或者您可以藉由指定篩選準則搜尋特定郵件 （篩選也可以協助減少您結果集，如果您有超過 500 封郵件）。後搜尋並找到特定隔離的郵件，您可以檢視郵件的詳細資料。您還可以：</span><span class="sxs-lookup"><span data-stu-id="287fc-p104">You can view a list of all quarantined messages, or you can search for specific messages by specifying filter criteria (filtering can also help reduce your result set if you have more than 500 messages). After searching for and locating a specific quarantined message, you can view details about the message. You can also:</span></span>
  
- <span data-ttu-id="287fc-p105">郵件釋出給一或多個收件者，並選擇性地向 Microsoft 垃圾郵件分析小組，小組會評估和分析此郵件為誤判 （非垃圾郵件） 的郵件報告。根據分析結果，您可能會調整全服務垃圾郵件內容篩選規則，以允許郵件通過。</span><span class="sxs-lookup"><span data-stu-id="287fc-p105">Release the message to one or more recipients, and optionally report it as a false positive (not junk) message to the Microsoft Spam Analysis Team, who will evaluate and analyze the message. Depending on the results of the analysis, the service-wide spam content filter rules may be adjusted to allow the message through.</span></span>
    
- <span data-ttu-id="287fc-119">釋出郵件並允許未來的所有郵件來自該寄件者。</span><span class="sxs-lookup"><span data-stu-id="287fc-119">Release the message and allow all future messages from that sender.</span></span>
    
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="287fc-120">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="287fc-120">What do you need to know before you begin?</span></span>
<span data-ttu-id="287fc-121"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="287fc-121"></span></span>

- <span data-ttu-id="287fc-p106">您必須獲指派權限，才能執行此程序或各個程序。若要查看您需要的權限，請參閱[Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主題中的 「 隔離 」 項目。</span><span class="sxs-lookup"><span data-stu-id="287fc-p106">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Quarantine" entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span> 
    
- <span data-ttu-id="287fc-p107">您可以釋出或多個郵件報告一次 [**隔離**] 頁面。或者您可以建立遠端 Windows PowerShell 指令碼，以完成這項工作。使用[Get-quarantinemessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx)指令程式來搜尋郵件，並釋放這些[Release-quarantinemessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx)指令程式。</span><span class="sxs-lookup"><span data-stu-id="287fc-p107">You can release or report multiple messages at once on the **quarantine** page. Alternatively you can create a remote Windows PowerShell script to accomplish this task. Use the [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) cmdlet to search for messages, and the [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) cmdlet to release them.</span></span> 
    
- <span data-ttu-id="287fc-127">如需適用於此主題中程序的快速鍵相關資訊，請參閱 **Exchange 系統管理中心的鍵盤快速鍵**。</span><span class="sxs-lookup"><span data-stu-id="287fc-127">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
> [!TIP]
> <span data-ttu-id="287fc-p108">有問題嗎？在 Exchange 論壇中尋求協助。 論壇的網址為：[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)或 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。</span><span class="sxs-lookup"><span data-stu-id="287fc-p108">Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="use-advanced-search-to-filter-and-locate-quarantined-messages"></a><span data-ttu-id="287fc-131">使用進階搜尋來篩選和尋找隔離郵件</span><span class="sxs-lookup"><span data-stu-id="287fc-131">Use advanced search to filter and locate quarantined messages</span></span>
<span data-ttu-id="287fc-132"><a name="BKMK_UseAdvancedSearchtoFilterMessages"> </a></span><span class="sxs-lookup"><span data-stu-id="287fc-132"></span></span>

<span data-ttu-id="287fc-p109">在 Exchange 系統管理中心 (EAC)，您可以使用進階搜尋，根據數個不同條件來篩選隔離的郵件。這些條件可以分開使用，也可以一起使用。搜尋將會提供符合所有篩選準則的郵件清單。</span><span class="sxs-lookup"><span data-stu-id="287fc-p109">In the Exchange admin center (EAC), you can filter quarantined items based on several different conditions using advanced search. You can use these conditions separately or in combination with one another. The search will provide a list of messages that meet all your filter criteria.</span></span>
  
1. <span data-ttu-id="287fc-136">在 EAC 中，瀏覽至 [**保護** \> **隔離區**，然後按一下 [**進階的搜尋**。</span><span class="sxs-lookup"><span data-stu-id="287fc-136">In EAC, navigate to **Protection** \> **quarantine**, and then click **Advanced search**.</span></span>
    
2. <span data-ttu-id="287fc-p110">在 [**進階搜尋**] 視窗中，選取下列條件的任何組合。選取 [關聯] 核取方塊以啟用每個條件。不支援萬用字元。</span><span class="sxs-lookup"><span data-stu-id="287fc-p110">In the **Advanced search** window, select any combination of the following conditions. Select the associated check box to enable each condition. Wildcards aren't supported.</span></span> 
    
1. <span data-ttu-id="287fc-p111">**訊息識別碼**您可以使用此參數來執行特定郵件的目標式的搜尋。例如，如果特定郵件傳送者]，或適用於您組織中的使用者，但它永不到達其目的地，您可以搜尋使用郵件追蹤功能的郵件。如需詳細資訊，請參閱[執行訊息追蹤和檢視結果](http://technet.microsoft.com/library/74a9fc59-7e0e-4832-baf9-2a86418b0079.aspx)。如果您發現郵件已傳送至隔離區，可能是因為它符合規則，或已識別為垃圾郵件，您可以再輕鬆地此郵件中找到隔離區藉由指定其訊息識別碼。請務必包括完整的郵件識別碼字串。這可能包括角括弧 (\<\>)。</span><span class="sxs-lookup"><span data-stu-id="287fc-p111">**Message ID** You can use this parameter to perform a targeted search for a specific message. For example, if a specific message is sent by, or intended for, a user in your organization, but it never reaches its destination, you can search for the message using the message trace feature. For details, see [Run a Message Trace and View Results](http://technet.microsoft.com/library/74a9fc59-7e0e-4832-baf9-2a86418b0079.aspx). If you discover that the message was sent to the quarantine, perhaps because it matched a rule or was identified as spam, you can then easily find this message in the quarantine by specifying its Message ID. Be sure to include the full Message ID string. This might include angle brackets (\<\>).</span></span> 
    
2. <span data-ttu-id="287fc-146">**寄件者電子郵件地址** 指定寄送郵件人員的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="287fc-146">**Sender email address** Specify the email address of the person who sent the message.</span></span> 
    
3. <span data-ttu-id="287fc-147">**收件者電子郵件地址** 指定郵件預定收件者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="287fc-147">**Recipient email address** Specify the email address of the intended recipient of the message.</span></span> 
    
4. <span data-ttu-id="287fc-148">**主旨** 指定郵件的主旨行文字。</span><span class="sxs-lookup"><span data-stu-id="287fc-148">**Subject** Specify the subject line text of the message.</span></span> 
    
5. <span data-ttu-id="287fc-149">**接收**您可以選取過去 24 小時 （**今天**）、 過去一週 （**最近 7 天**）、 過去 48 小時 （**最近 2 天**）、 內由隔離收到郵件，或者您可以選取的自訂時間間隔期間的郵件。接收到隔離區。</span><span class="sxs-lookup"><span data-stu-id="287fc-149">**Received** You can select that the message was received by quarantine within the past 24 hours ( **Today**), within the past 48 hours ( **Last 2 days**), within the past week ( **Last 7 days**), or you can select a custom time interval during which the message was received by the quarantine.</span></span> 
    
6. <span data-ttu-id="287fc-150">**到期**您可以選取從隔離區在未來 24 小時 （**今天**）、 一週 （**未來 7 天**）、 未來 48 小時 （**未來 2 天**）、 內刪除的郵件，或您可以選取的自訂時間間隔期間的郵件將從隔離刪除。</span><span class="sxs-lookup"><span data-stu-id="287fc-150">**Expires** You can select that the message will be deleted from quarantine within the next 24 hours ( **Today**), within the next 48 hours ( **Next 2 days**), within the next week ( **Next 7 days**), or you can select a custom time interval during which the message will be deleted from quarantine.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="287fc-p112">根據預設，垃圾郵件隔離的郵件會保留在隔離區 15 天時符合郵件流程規則的隔離的郵件會保留在隔離區 7 天的。在這段時間後，Office 365 刪除郵件，而無法加以擷取。符合郵件流程規則的隔離郵件的保留期間不是可設定的。不過，可以降低垃圾郵件隔離的郵件的保留期間，透過內容篩選原則中的 [**保留垃圾郵件 （天） 的**設定。如需詳細資訊，請參閱[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="287fc-p112">By default, spam-quarantined messages are kept in quarantine for 15 days, while quarantined messages that matched a mail flow rule are kept in the quarantine for 7 days. After this period of time Office 365 deletes the messages and they are not retrievable. The retention period for quarantined messages that matched a mail flow rule is not configurable. However, the retention period for spam-quarantined messages can be lowered via the **Retain spam for (days)** setting in your content filter policies. For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span> 
  
7. <span data-ttu-id="287fc-156">**型別**您可以指定是否要搜尋被隔離的郵件會被識別為**垃圾郵件**，或是搜尋符合郵件流程規則 （**傳輸規則**） 的郵件。</span><span class="sxs-lookup"><span data-stu-id="287fc-156">**Type** You can specify whether to search for quarantined messages that have been identified as **Spam**, or whether to search for messages that matched a mail flow rule (**Transport rule**).</span></span>
    
3. <span data-ttu-id="287fc-157">按一下 **[確定]**，開始執行進階搜尋。</span><span class="sxs-lookup"><span data-stu-id="287fc-157">Click **OK** to start running the advanced search.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="287fc-158">若要清除搜尋準則並檢視隔離中的所有郵件，請清除 **[進階搜尋]** 視窗中的所有核取方塊，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="287fc-158">To clear your search criteria and view all messages in the quarantine, clear all the check boxes in the **Advanced search** window, and then click **OK**.</span></span> 
  
<span data-ttu-id="287fc-p113">搜尋郵件後，符合您指定之準則的結果會顯示在使用者介面中。EAC 中最多可以顯示 500 封郵件。</span><span class="sxs-lookup"><span data-stu-id="287fc-p113">After searching for messages, the results that match your specified criteria will display in the user interface. A maximum of 500 messages can be displayed in the EAC.</span></span> 
  
## <a name="view-details-about-a-specific-quarantined-message"></a><span data-ttu-id="287fc-161">檢視特定隔離郵件的詳細資料</span><span class="sxs-lookup"><span data-stu-id="287fc-161">View details about a specific quarantined message</span></span>
<span data-ttu-id="287fc-162"><a name="BKMK_ViewDetailsAboutaSpecificQuarantinedMessage"> </a></span><span class="sxs-lookup"><span data-stu-id="287fc-162"></span></span>

<span data-ttu-id="287fc-163">找到特定隔離的郵件之後 [**隔離**] 頁面上，您可以檢視其詳細資料。</span><span class="sxs-lookup"><span data-stu-id="287fc-163">After locating a specific quarantined message on the **quarantine** page, you can view details about it.</span></span> 
  
1. <span data-ttu-id="287fc-164">在 [**隔離**] 頁面上，選取特定郵件，畫面右邊的詳細資料窗格中會顯示該郵件的屬性摘要。</span><span class="sxs-lookup"><span data-stu-id="287fc-164">On the **quarantine** page, select a specific message and a summary of the properties of that message appear in the details pane on the right side of the screen.</span></span> 
    
    <span data-ttu-id="287fc-165">**[郵件狀態]** 值如下：</span><span class="sxs-lookup"><span data-stu-id="287fc-165">The **Message status** values are as follows:</span></span> 
    
  - <span data-ttu-id="287fc-166">**型別**表示郵件是否已被識別為**垃圾郵件**或符合郵件流程規則 （**傳輸規則**）。</span><span class="sxs-lookup"><span data-stu-id="287fc-166">**Type** Denotes whether the message has been identified as **Spam** or matched a mail flow rule (**Transport rule**).</span></span>
    
  - <span data-ttu-id="287fc-167">**到期** 將從隔離刪除此郵件的日期。</span><span class="sxs-lookup"><span data-stu-id="287fc-167">**Expires** The date when the message will be deleted from the quarantine.</span></span> 
    
    <span data-ttu-id="287fc-168">**[郵件詳細資料]** 值如下：</span><span class="sxs-lookup"><span data-stu-id="287fc-168">The **Message details** values are as follows:</span></span> 
    
  - <span data-ttu-id="287fc-169">**寄件者** 傳送郵件之人員的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="287fc-169">**Sender** The email address of the person who sent the message.</span></span> 
    
  - <span data-ttu-id="287fc-170">**主旨** 郵件的主旨行文字。</span><span class="sxs-lookup"><span data-stu-id="287fc-170">**Subject** The subject line text of the message.</span></span> 
    
  - <span data-ttu-id="287fc-171">**收到日期** 隔離收到郵件的日期。</span><span class="sxs-lookup"><span data-stu-id="287fc-171">**Received** The date on which the message was received by the quarantine.</span></span> 
    
  - <span data-ttu-id="287fc-172">**大小** 郵件的大小，單位為 KB，如果郵件大小超過 999 KB 則為 MB。</span><span class="sxs-lookup"><span data-stu-id="287fc-172">**Size** The size of the message, in kilobytes (KB), or, if the message size is greater than 999 KBs, in megabytes (MB).</span></span> 
    
  - <span data-ttu-id="287fc-p114">**檢視郵件標頭**按一下此連結以開啟 [**郵件標頭**] 對話方塊，可讓您檢視郵件標頭文字。您也可以將郵件標頭文字複製到剪貼簿，並將它貼到[郵件標頭分析器](https://testconnectivity.microsoft.com/?tabid=mha)。一次在郵件標頭分析器工具中，按一下 [**分析標頭**以便擷取標頭的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="287fc-p114">**View message header** Click this link to open the **message header** dialog box, which lets you view the message header text. You can also copy the message header text to your clipboard and paste it into the [Message Header Analyzer](https://testconnectivity.microsoft.com/?tabid=mha). Once in the Message Header Analyzer tool, click **Analyze headers** in order to retrieve information about the header.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="287fc-176">如需服務所插入之特定反垃圾郵件郵件標頭欄位的相關資訊，請參閱[反垃圾郵件訊息標頭](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="287fc-176">For information about specific anti-spam message header fields inserted by the service, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span> 
  
  - <span data-ttu-id="287fc-177">**預覽電子郵件訊息**按一下此連結可以檢閱訊息的文字。</span><span class="sxs-lookup"><span data-stu-id="287fc-177">**Preview email message** Click this link to review the text of the message.</span></span> 
    
2. <span data-ttu-id="287fc-178">如果您按兩下隔離郵件，則會開啟 **[隔離郵件]** 視窗並顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="287fc-178">If you double-click a quarantined message, the **Quarantined message** window opens and displays the following information:</span></span> 
    
  - <span data-ttu-id="287fc-179">**已釋放** 已釋放其郵件的所有電子郵件地址清單 (若有的話)。</span><span class="sxs-lookup"><span data-stu-id="287fc-179">**Released to** A list of all email addresses to whom the message has been released, if any.</span></span> 
    
  - <span data-ttu-id="287fc-p115">**尚未發行至**對象不已釋放郵件，如果有任何的所有電子郵件地址清單。您可以按一下 [**發行**] 連結以釋出郵件;如需釋出郵件的詳細資訊，請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="287fc-p115">**Not yet released to** A list of all email addresses to whom the message has not been released, if any. You can click the **Release to** link in order to release the message; for more information about releasing a message, see the next section.</span></span> 
    
  - <span data-ttu-id="287fc-182">**郵件識別碼** 在郵件標頭中找到的網際網路郵件識別碼 (也稱為用戶端識別碼)。</span><span class="sxs-lookup"><span data-stu-id="287fc-182">**Message ID** The Internet Message ID (also known as the Client ID) found in the header of the message.</span></span> 
    
    <span data-ttu-id="287fc-183">按一下 **[關閉]** 返回主要隔離窗格。</span><span class="sxs-lookup"><span data-stu-id="287fc-183">Click **Close** to return to the main quarantine pane.</span></span> 
    
## <a name="release-messages-from-quarantine"></a><span data-ttu-id="287fc-184">釋放隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="287fc-184">Release messages from quarantine</span></span>
<span data-ttu-id="287fc-185"><a name="sectionSection3"> </a></span><span class="sxs-lookup"><span data-stu-id="287fc-185"></span></span>

<span data-ttu-id="287fc-186">如果您想要釋出到收件者的郵件，是您的選項：</span><span class="sxs-lookup"><span data-stu-id="287fc-186">If you want to release messages to recipients, your options are:</span></span>
  
- [<span data-ttu-id="287fc-187">釋出隔離的郵件，並允許將來的郵件寄件者</span><span class="sxs-lookup"><span data-stu-id="287fc-187">Release a quarantined message and allow future messages from the sender</span></span>](find-and-release-quarantined-messages-as-an-administrator.md#Releasequarantinedmessageallowfuturemessagesfromsender)
    
- [<span data-ttu-id="287fc-188">釋出隔離的郵件給特定收件者而不將其報告為誤判</span><span class="sxs-lookup"><span data-stu-id="287fc-188">Release a quarantined message to specific recipients without reporting it as a false positive</span></span>](find-and-release-quarantined-messages-as-an-administrator.md#Releasequarantinedmessagetospecificrecipientswithoutreportingasfalsepositive)
    
- [<span data-ttu-id="287fc-189">釋出給所有收件者的一或多個隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="287fc-189">Release one or more quarantined messages to all recipients</span></span>](find-and-release-quarantined-messages-as-an-administrator.md#Releaseoneormorequarantinedmessagestoallrecipients)
    
- [<span data-ttu-id="287fc-190">釋出給所有收件者及報告誤判的一或多個隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="287fc-190">Release one or more quarantined messages to all recipients and report false positives</span></span>](find-and-release-quarantined-messages-as-an-administrator.md#Releaseoneormorequarantinedmessagestoallrecipientsandreportfalsepositives)
    
### <a name="release-a-quarantined-message-and-allow-future-messages-from-the-sender"></a><span data-ttu-id="287fc-191">釋出隔離的郵件，並允許將來的郵件寄件者</span><span class="sxs-lookup"><span data-stu-id="287fc-191">Release a quarantined message and allow future messages from the sender</span></span>
<span data-ttu-id="287fc-192"><a name="Releasequarantinedmessageallowfuturemessagesfromsender"> </a></span><span class="sxs-lookup"><span data-stu-id="287fc-192"></span></span>

1. <span data-ttu-id="287fc-193">在 EAC 中，瀏覽至 [**保護** \> **隔離**。</span><span class="sxs-lookup"><span data-stu-id="287fc-193">In EAC, navigate to **Protection** \> **quarantine**.</span></span>
    
2. <span data-ttu-id="287fc-194">按一下以選取它，然後按一下 [**釋出郵件**] 圖示，如下列螢幕擷取畫面所示的郵件。</span><span class="sxs-lookup"><span data-stu-id="287fc-194">Click on a message to select it and then click the **Release Message** icon as shown in the following screen shot.</span></span> 
  
![顯示隔離頁面，其中會反白顯示發行訊息圖示，並顯示發行選項](media/36ee081f-3e30-40c9-8ce3-240cee1970cc.png)
  
<span data-ttu-id="287fc-196">從下拉式清單中，按一下 [**選取的郵件釋出，並允許寄件者**。</span><span class="sxs-lookup"><span data-stu-id="287fc-196">Click **Release selected message and allow sender** from the drop-down list.</span></span> 
    
3. <span data-ttu-id="287fc-p116">[**釋出郵件並允許寄件者**] 對話方塊隨即開啟。或者，您可以選擇以回報給 Microsoft，然後按一下 [**釋出，並允許**。郵件就會釋出給所有收件者地址來並將允許從此寄件者的所有未來郵件。不過，如果此郵件遭隔離因郵件流程規則或封鎖寄件者，寄件者將會繼續將來的郵件遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="287fc-p116">The **release message and allow sender** dialog box opens. Optionally, you can choose to report the message to Microsoft, then click **release and allow**. The message will be released to all recipients it's addressed to and all future messages from this sender will be allowed. However, if this message was quarantined because of a mail flow rule or blocked sender, the sender will continue to be blocked for future messages.</span></span> 
    
### <a name="release-a-quarantined-message-to-specific-recipients-without-reporting-it-as-a-false-positive"></a><span data-ttu-id="287fc-201">釋出隔離的郵件給特定收件者而不將其報告為誤判</span><span class="sxs-lookup"><span data-stu-id="287fc-201">Release a quarantined message to specific recipients without reporting it as a false positive</span></span>
<span data-ttu-id="287fc-202"><a name="Releasequarantinedmessagetospecificrecipientswithoutreportingasfalsepositive"> </a></span><span class="sxs-lookup"><span data-stu-id="287fc-202"></span></span>

1. <span data-ttu-id="287fc-203">在 EAC 中，瀏覽至 [**保護** \> **隔離**。</span><span class="sxs-lookup"><span data-stu-id="287fc-203">In EAC, navigate to **Protection** \> **quarantine**.</span></span>
    
2. <span data-ttu-id="287fc-204">選取一則訊息，按一下 [**釋出郵件**] 圖示，，然後從下拉式清單中按一下 [**郵件釋出給特定收件者**。</span><span class="sxs-lookup"><span data-stu-id="287fc-204">Select a message, click the **Release Message** icon, and then click **Release message to specific recipients** from the drop-down list.</span></span> 
    
3. <span data-ttu-id="287fc-205">在 **[釋出郵件]** 對話方塊中，選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="287fc-205">In the **release message** dialog box, select one of the following options:</span></span> 
    
  - <span data-ttu-id="287fc-p117">**將郵件釋出給所有收件者** 如果您選取此選項，請注意，您只能將郵件釋出給同一位收件者一次。如果收件者先前已收到郵件，系統不會再將郵件釋出給該名收件者。</span><span class="sxs-lookup"><span data-stu-id="287fc-p117">**Release message to all recipients** When you select this option, be aware that a message cannot be released more than once to the same recipient. If a recipient has previously received the message, it will not be released again to that recipient.</span></span> 
    
  - <span data-ttu-id="287fc-p118">**郵件釋出給指定收件者**選取 [對象可以釋出郵件的收件者]。由於每個收件者只發行一次一則訊息，只有中收件者對象發行會出現在此清單。支援多重選取範圍。您的收件者選擇之後，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="287fc-p118">**Release message to specified recipients** Select the recipient(s) to whom the message can be released. Because a message can only be released once to each recipient, only recipients to whom it can be released appear in this list. Multi-selection is supported. After making your recipient selections, click **add**.</span></span>
    
4. <span data-ttu-id="287fc-212">按一下 **[釋出]**。</span><span class="sxs-lookup"><span data-stu-id="287fc-212">Click **release**.</span></span> 
    
<span data-ttu-id="287fc-213">如果您按一下 [**重新整理**![重新整理圖示](media/ITPro-EAC-RefreshIcon.gif)圖示來重新整理您的資料，然後連按兩下郵件，您應該會看到，它已釋出給預定的收件者。</span><span class="sxs-lookup"><span data-stu-id="287fc-213">If you click the **Refresh**![Refresh Icon](media/ITPro-EAC-RefreshIcon.gif) icon to refresh your data, and then double-click the message, you should see that it's been released to the intended recipients.</span></span> 
  
### <a name="release-one-or-more-quarantined-messages-to-all-recipients"></a><span data-ttu-id="287fc-214">釋出給所有收件者的一或多個隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="287fc-214">Release one or more quarantined messages to all recipients</span></span>
<span data-ttu-id="287fc-215"><a name="Releaseoneormorequarantinedmessagestoallrecipients"> </a></span><span class="sxs-lookup"><span data-stu-id="287fc-215"></span></span>

1. <span data-ttu-id="287fc-216">在 EAC 中，瀏覽至 [**保護** \> **隔離**。</span><span class="sxs-lookup"><span data-stu-id="287fc-216">In EAC, navigate to **Protection** \> **quarantine**.</span></span>
    
2. <span data-ttu-id="287fc-p119">按一下以選取它，或使用 shift 鍵來選取多個郵件訊息。然後按一下 [**釋出郵件**] 圖示。</span><span class="sxs-lookup"><span data-stu-id="287fc-p119">Click on a message to select it, or use the shift key to select multiple messages. Then click the **Release Message** icon.</span></span> 
    
3. <span data-ttu-id="287fc-219">從下拉式清單中按一下 [**發行給所有收件者所選的郵件**]。</span><span class="sxs-lookup"><span data-stu-id="287fc-219">Click **Release selected message(s) to ALL recipients** from the drop-down list.</span></span> 
    
4. <span data-ttu-id="287fc-p120">[警告] 對話方塊隨即開啟。閱讀警告，如果您想要繼續，請選取 **[是]** 。當您選取此選項時，請注意，郵件無法再釋出一次以上相同的收件者。如果收件者先前已收到郵件，它將不會釋放再次給該收件者。</span><span class="sxs-lookup"><span data-stu-id="287fc-p120">The warning dialog box opens. Read the warning and select **Yes** if you want to proceed. When you select this option, be aware that a message cannot be released more than once to the same recipient. If a recipient has previously received the message, it will not be released again to that recipient.</span></span> 
    
### <a name="release-one-or-more-quarantined-messages-to-all-recipients-and-report-false-positives"></a><span data-ttu-id="287fc-224">釋出給所有收件者及報告誤判的一或多個隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="287fc-224">Release one or more quarantined messages to all recipients and report false positives</span></span>
<span data-ttu-id="287fc-225"><a name="Releaseoneormorequarantinedmessagestoallrecipientsandreportfalsepositives"> </a></span><span class="sxs-lookup"><span data-stu-id="287fc-225"></span></span>

1. <span data-ttu-id="287fc-226">在 EAC 中，瀏覽至 [**保護** \> **隔離**。</span><span class="sxs-lookup"><span data-stu-id="287fc-226">In EAC, navigate to **Protection** \> **quarantine**.</span></span>
    
2. <span data-ttu-id="287fc-p121">按一下以選取它，或使用 shift 鍵來選取多個郵件訊息。然後按一下 [**釋出郵件**] 圖示。</span><span class="sxs-lookup"><span data-stu-id="287fc-p121">Click on a message to select it, or use the shift key to select multiple messages. Then click the **Release Message** icon.</span></span> 
    
3. <span data-ttu-id="287fc-229">從下拉式清單中，按一下 [**發行選取郵件並報告為誤判**。</span><span class="sxs-lookup"><span data-stu-id="287fc-229">Click **Release selected message(s) and report as false positive** from the drop-down list.</span></span> 
    
4. <span data-ttu-id="287fc-p122">[警告] 對話方塊隨即開啟。閱讀警告，如果您想要繼續，請選取 **[是]** 。當您選取此選項時，請注意，郵件無法再釋出一次以上相同的收件者。如果收件者先前已收到郵件，它將不會釋放再次給該收件者。</span><span class="sxs-lookup"><span data-stu-id="287fc-p122">The warning dialog box opens. Read the warning and select **Yes** if you want to proceed. When you select this option, be aware that a message cannot be released more than once to the same recipient. If a recipient has previously received the message, it will not be released again to that recipient.</span></span> 
    
     <span data-ttu-id="287fc-p123">當您選擇此選項時，郵件將會釋出給所有收件者未收到。如果是垃圾郵件隔離的郵件，它也會報告給 Microsoft 垃圾郵件分析小組，小組會評估和分析此郵件。根據分析結果，您可能會調整全服務垃圾郵件內容篩選規則，以允許郵件通過。</span><span class="sxs-lookup"><span data-stu-id="287fc-p123">When you choose this option, the message will be released to all recipients who have not yet received it. If it's a spam-quarantined message, it will also be reported to the Microsoft Spam Analysis Team, who will evaluate and analyze the message. Depending on the results of the analysis, the service-wide spam content filter rules may be adjusted to allow the message through.</span></span> 
    
> [!TIP]
> <span data-ttu-id="287fc-237">協助確保郵件不會標示為垃圾郵件遵循[如何協助確保郵件不會標示為垃圾郵件](how-to-help-ensure-that-a-message-isn-t-marked-as-spam.md)中的步驟。</span><span class="sxs-lookup"><span data-stu-id="287fc-237">Help ensure that a message isn't marked as spam by following the steps in [How to help ensure that a message isn't marked as spam](how-to-help-ensure-that-a-message-isn-t-marked-as-spam.md).</span></span> 
  
<span data-ttu-id="287fc-238">如果您按一下 [**重新整理**![重新整理圖示](media/ITPro-EAC-RefreshIcon.gif)圖示來重新整理您的資料，然後連按兩下郵件，您應該會看到，它已釋出給預定的收件者。</span><span class="sxs-lookup"><span data-stu-id="287fc-238">If you click the **Refresh**![Refresh Icon](media/ITPro-EAC-RefreshIcon.gif) icon to refresh your data, and then double-click the message, you should see that it's been released to the intended recipients.</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="287fc-239">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="287fc-239">For more information</span></span>
<span data-ttu-id="287fc-240"><a name="sectionSection4"> </a></span><span class="sxs-lookup"><span data-stu-id="287fc-240"></span></span>

[<span data-ttu-id="287fc-241">隔離常見問題集</span><span class="sxs-lookup"><span data-stu-id="287fc-241">Quarantine FAQ</span></span>](quarantine-faq.md)
  

