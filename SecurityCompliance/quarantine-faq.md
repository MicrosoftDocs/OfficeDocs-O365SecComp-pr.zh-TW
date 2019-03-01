---
title: 隔離常見問題集
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 6/16/2017
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
description: 本主題提供有關託管隔離區的常見問題與解答。
ms.openlocfilehash: 9f9b16a92b8ef8105a9439972ebed54111b227c6
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341174"
---
# <a name="quarantine-faq"></a><span data-ttu-id="e9886-103">隔離常見問題集</span><span class="sxs-lookup"><span data-stu-id="e9886-103">Quarantine FAQ</span></span>

<span data-ttu-id="e9886-p101">本主題提供有關託管隔離區的常見問題與解答。這些解答適用於 Microsoft Exchange Online 及 Exchange Online Protection 客戶。</span><span class="sxs-lookup"><span data-stu-id="e9886-p101">This topic provides frequently asked questions and answers about the hosted quarantine. Answers are applicable for Microsoft Exchange Online and Exchange Online Protection customers.</span></span>
  
 <span data-ttu-id="e9886-106">**問： 如何管理隔離區中的惡意程式碼隔離的郵件？**</span><span class="sxs-lookup"><span data-stu-id="e9886-106">**Q. How do I manage malware-quarantined messages in quarantine?**</span></span>
  
<span data-ttu-id="e9886-p102">您必須使用安全性<b0></b0>以檢視並處理郵件已傳送至隔離區，因為它們包含惡意程式碼的合規性中心。如需詳細資訊，請參閱 < <b1>Office 365 中的隔離電子郵件</b1>。</span><span class="sxs-lookup"><span data-stu-id="e9886-p102">You need to use the Security &amp; Compliance Center in order to view and work with messages that were sent to quarantine because they contain malware. For more information, see [Quarantine email messages in Office 365](https://support.office.com/article/Quarantine-email-messages-in-Office-365-4c234874-015e-4768-8495-98fcccfc639b).</span></span>
  
 <span data-ttu-id="e9886-109">**問：如何設定服務以將因垃圾郵件而遭到隔離的郵件傳送至隔離區？**</span><span class="sxs-lookup"><span data-stu-id="e9886-109">**Q. How do I configure the service to send spam-quarantined messages to the quarantine?**</span></span>
  
<span data-ttu-id="e9886-p103">答： 根據預設，內容篩選的郵件會傳送至 [收件者的垃圾郵件] 資料夾。不過，系統管理員可以設定內容篩選原則，以將垃圾郵件隔離的郵件傳送至隔離區。如需可以在內容篩選的郵件執行的不同動作的詳細資訊，請參閱 <<c0>設定垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="e9886-p103">A. By default, content-filtered messages are sent to the recipients Junk Email folder. However, admins can configure content filter policies to send spam-quarantined messages to the quarantine instead. For more information about the different actions that can be performed on content-filtered messages, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
  
 <span data-ttu-id="e9886-114">**問：此服務是否可讓系統管理員和使用者管理被當成垃圾郵件隔離的郵件？**</span><span class="sxs-lookup"><span data-stu-id="e9886-114">**Q. Does the service have administrator and end user management of spam-quarantined messages?**</span></span>
  
<span data-ttu-id="e9886-p104">答：如果您是系統管理員，您可以在 Exchange 系統管理中心 (EAC) 中搜尋及檢視關於所有隔離電子郵件的詳細資訊。找到郵件後，您可以將該郵件釋出給特定使用者，並可選擇向 Microsoft 垃圾郵件分析小組報告該郵件為誤判 (非垃圾郵件)。如需詳細資訊，請參閱 [以系統管理員身分找到並釋放被隔離的郵件](find-and-release-quarantined-messages-as-an-administrator.md)。</span><span class="sxs-lookup"><span data-stu-id="e9886-p104">A. As an administrator, you can search for and view details about all quarantined email messages in the Exchange admin center (EAC). After locating the message, you can release it to specific users and optionally report it as a false positive (not junk) to the Microsoft Spam Analysis Team. For more information, see [Find and release quarantined messages as an administrator](find-and-release-quarantined-messages-as-an-administrator.md).</span></span>
  
<span data-ttu-id="e9886-119">如果您是使用者，則可以透過下列項目管理自己被當成垃圾郵件隔離的郵件：</span><span class="sxs-lookup"><span data-stu-id="e9886-119">As an end user, you can manage your own spam-quarantined messages via:</span></span> 
  
- <span data-ttu-id="e9886-p105">垃圾郵件隔離使用者介面。如需詳細資訊，請參閱 [Find and Release Quarantined Messages (End Users)](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e9886-p105">The spam quarantine user interface. For more information, see [Find and Release Quarantined Messages (End Users)](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx).</span></span>
        
 <span data-ttu-id="e9886-122">**問：如何授權使用者存取垃圾郵件隔離區？**</span><span class="sxs-lookup"><span data-stu-id="e9886-122">**Q. How do I grant access to the spam quarantine for my end users?**</span></span>
  
<span data-ttu-id="e9886-p106">答： 以存取使用者垃圾郵件隔離區，使用者必須具有有效的 Office 365 使用者識別碼和密碼。保護內部部署信箱的 EOP 客戶必須是有效的電子郵件使用者透過目錄同步處理或 EAC 建立。如需管理使用者的詳細資訊，EOP 系統管理員可以參閱[管理 EOP 中的郵件使用者](eop/manage-mail-users-in-eop.md)。為 EOP 獨立版客戶，我們建議使用目錄同步處理，並啟用目錄架構邊緣封鎖;如需詳細資訊，請參閱[使用 Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e9886-p106">A. In order to access the end user spam quarantine, end users must have a valid Office 365 user ID and password. EOP customers protecting on-premises mailboxes must be valid email users created via directory synchronization or the EAC. For more information about managing users, EOP admins can refer to [Manage mail users in EOP](eop/manage-mail-users-in-eop.md). For EOP standalone customers, we recommend using directory synchronization and enabling Directory Based Edge Blocking; for more information, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx).</span></span>
  
 <span data-ttu-id="e9886-128">**問：不是垃圾郵件的項目是否會傳送到隔離區？**</span><span class="sxs-lookup"><span data-stu-id="e9886-128">**Q. Can anything other than spam be sent to the quarantine?**</span></span>
  
<span data-ttu-id="e9886-p107">答： 郵件符合郵件流程規則 （也稱為傳輸規則） 也傳送至管理員隔離區，如果這是設定的動作。垃圾郵件只是使用者隔離區。</span><span class="sxs-lookup"><span data-stu-id="e9886-p107">A. Messages that match a mail flow rule (also known as a transport rule) can also be sent to the administrator quarantine, if that's the configured action. The end user quarantine is for spam only.</span></span>
  
 <span data-ttu-id="e9886-132">**問：郵件會保留在隔離區中多久？**</span><span class="sxs-lookup"><span data-stu-id="e9886-132">**Q. For how long are messages kept in the quarantine?**</span></span>
  
<span data-ttu-id="e9886-p108">答： 依預設，垃圾郵件隔離的郵件會保留在隔離區 30 天，而被隔離的郵件符合郵件流程規則會保留在隔離區 7 天。在這段時間後的郵件會刪除，而且而無法加以擷取。符合郵件流程規則的隔離郵件的保留期間不是可設定的。不過，可以降低垃圾郵件隔離的郵件的保留期間，透過內容篩選原則中的 [**保留垃圾郵件 （天） 的**設定。如需詳細資訊，請參閱[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e9886-p108">A. By default, spam-quarantined messages are kept in the quarantine for 30 days, while quarantined messages that matched a mail flow rule are kept in the quarantine for 7 days. After this period of time the messages are deleted and are not retrievable. The retention period for quarantined messages that matched a mail flow rule is not configurable. However, the retention period for spam-quarantined messages can be lowered via the **Retain spam for (days)** setting in your content filter policies. For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
  
 <span data-ttu-id="e9886-139">**問：我可以一次釋出或報告多個隔離的郵件嗎？**</span><span class="sxs-lookup"><span data-stu-id="e9886-139">**Q. Can I release or report more than one quarantined message at a time?**</span></span>
  
<span data-ttu-id="e9886-p109">答： 釋出或一次報表多封郵件很不目前無法使用 EAC 或使用者垃圾郵件隔離區中。不過，系統管理員可以建立遠端 Windows PowerShell 指令碼，以完成這項工作。使用[Get-quarantinemessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx)指令程式來搜尋郵件，並釋放這些[Release-quarantinemessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx)指令程式。</span><span class="sxs-lookup"><span data-stu-id="e9886-p109">A. The ability to release or report multiple messages at once is not currently available in the EAC or the end user spam quarantine. However, admins can create a remote Windows PowerShell script to accomplish this task. Use the [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) cmdlet to search for messages, and the [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) cmdlet to release them.</span></span> 
  
 <span data-ttu-id="e9886-144">**問：搜尋隔離的郵件時是否支援萬用字元？我可以搜尋特定網域的隔離郵件嗎？**</span><span class="sxs-lookup"><span data-stu-id="e9886-144">**Q. Are wildcards supported when searching for quarantined messages? Can I search for quarantined messages for a specific domain?**</span></span>
  
<span data-ttu-id="e9886-p110">答：在 Exchange 系統管理中心指定搜尋準則時不支援萬用字元。例如，在搜尋寄件者時，您必須指定完整的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="e9886-p110">A. Wildcards are not supported when specifying search criteria in the Exchange admin center. For example, when searching for a sender, you must specify the full email address.</span></span>
  
<span data-ttu-id="e9886-148">系統管理員可以使用遠端 Windows PowerShell，指定 [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) 指令程式在特定網域 (例如 contoso.com) 中搜尋隔離的郵件：</span><span class="sxs-lookup"><span data-stu-id="e9886-148">Using remote Windows PowerShell, admins can specify the [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) cmdlet to search for quarantined messages for a specific domain (for example, contoso.com):</span></span> 
  
```
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```

<span data-ttu-id="e9886-p111">結果可以傳遞至 [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) 指令程式。請加上 -ReleaseToAll 參數，以將郵件釋出給所有收件者。郵件一經釋出，就無法再釋出一次。</span><span class="sxs-lookup"><span data-stu-id="e9886-p111">The results can be passed to the [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) cmdlet. Include the -ReleaseToAll parameter to release the message to all recipients. Once a message is released, it can't be released again.</span></span> 
  
```
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```


