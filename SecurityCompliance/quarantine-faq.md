---
title: 隔離常見問題集
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/16/2017
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
description: 本主題提供有關託管隔離區的常見問題與解答。
ms.openlocfilehash: 6aebeadc5155cbdb8cbeeb73e29c8b8cb0d53767
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027080"
---
# <a name="quarantine-faq"></a><span data-ttu-id="bfb95-103">隔離常見問題集</span><span class="sxs-lookup"><span data-stu-id="bfb95-103">Quarantine FAQ</span></span>

<span data-ttu-id="bfb95-p101">本主題提供有關託管隔離區的常見問題與解答。這些解答適用於 Microsoft Exchange Online 及 Exchange Online Protection 客戶。</span><span class="sxs-lookup"><span data-stu-id="bfb95-p101">This topic provides frequently asked questions and answers about the hosted quarantine. Answers are applicable for Microsoft Exchange Online and Exchange Online Protection customers.</span></span>
  
 <span data-ttu-id="bfb95-106">**問： 如何管理隔離區中的惡意程式碼隔離的郵件？**</span><span class="sxs-lookup"><span data-stu-id="bfb95-106">**Q. How do I manage malware-quarantined messages in quarantine?**</span></span>
  
<span data-ttu-id="bfb95-p102">您需要使用安全性&amp;規範中心以檢視及使用傳送至隔離因為它們包含惡意程式碼的郵件。如需詳細資訊，請參閱[Office 365 中的隔離電子郵件訊息](https://support.office.com/en-US/article/Quarantine-email-messages-in-Office-365-4c234874-015e-4768-8495-98fcccfc639b)。</span><span class="sxs-lookup"><span data-stu-id="bfb95-p102">You need to use the Security &amp; Compliance Center in order to view and work with messages that were sent to quarantine because they contain malware. For more information, see [Quarantine email messages in Office 365](https://support.office.com/en-US/article/Quarantine-email-messages-in-Office-365-4c234874-015e-4768-8495-98fcccfc639b).</span></span>
  
 <span data-ttu-id="bfb95-109">**問：如何設定服務以將因垃圾郵件而遭到隔離的郵件傳送至隔離區？**</span><span class="sxs-lookup"><span data-stu-id="bfb95-109">**Q. How do I configure the service to send spam-quarantined messages to the quarantine?**</span></span>
  
<span data-ttu-id="bfb95-p103">A.預設會經過內容篩選的郵件會傳送給收件者的 [垃圾郵件] 資料夾。不過，系統管理員可以設定為將垃圾郵件隔離的郵件傳送至隔離區的內容篩選原則。如需可在經過內容篩選的郵件執行的不同動作的詳細資訊，請參閱[設定垃圾郵件篩選器原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="bfb95-p103">A. By default, content-filtered messages are sent to the recipients Junk Email folder. However, admins can configure content filter policies to send spam-quarantined messages to the quarantine instead. For more information about the different actions that can be performed on content-filtered messages, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
  
 <span data-ttu-id="bfb95-114">**問：此服務是否可讓系統管理員和使用者管理被當成垃圾郵件隔離的郵件？**</span><span class="sxs-lookup"><span data-stu-id="bfb95-114">**Q. Does the service have administrator and end user management of spam-quarantined messages?**</span></span>
  
<span data-ttu-id="bfb95-p104">答：如果您是系統管理員，您可以在 Exchange 系統管理中心 (EAC) 中搜尋及檢視關於所有隔離電子郵件的詳細資訊。找到郵件後，您可以將該郵件釋出給特定使用者，並可選擇向 Microsoft 垃圾郵件分析小組報告該郵件為誤判 (非垃圾郵件)。如需詳細資訊，請參閱 [以系統管理員身分找到並釋放被隔離的郵件](find-and-release-quarantined-messages-as-an-administrator.md)。</span><span class="sxs-lookup"><span data-stu-id="bfb95-p104">A. As an administrator, you can search for and view details about all quarantined email messages in the Exchange admin center (EAC). After locating the message, you can release it to specific users and optionally report it as a false positive (not junk) to the Microsoft Spam Analysis Team. For more information, see [Find and release quarantined messages as an administrator](find-and-release-quarantined-messages-as-an-administrator.md).</span></span>
  
<span data-ttu-id="bfb95-119">如果您是使用者，則可以透過下列項目管理自己被當成垃圾郵件隔離的郵件：</span><span class="sxs-lookup"><span data-stu-id="bfb95-119">As an end user, you can manage your own spam-quarantined messages via:</span></span> 
  
- <span data-ttu-id="bfb95-p105">垃圾郵件隔離使用者介面。如需詳細資訊，請參閱 [Find and Release Quarantined Messages (End Users)](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx)。</span><span class="sxs-lookup"><span data-stu-id="bfb95-p105">The spam quarantine user interface. For more information, see [Find and Release Quarantined Messages (End Users)](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx).</span></span>
        
 <span data-ttu-id="bfb95-122">**問：如何授權使用者存取垃圾郵件隔離區？**</span><span class="sxs-lookup"><span data-stu-id="bfb95-122">**Q. How do I grant access to the spam quarantine for my end users?**</span></span>
  
<span data-ttu-id="bfb95-p106">A.若要存取使用者垃圾郵件隔離區，使用者必須具備有效的 Office 365 使用者識別碼和密碼。保護內部部署信箱的 EOP 客戶必須是有效的電子郵件使用者透過目錄同步處理或 EAC 建立。如需管理使用者的詳細資訊，EOP 系統管理員可以參照[在 EOP 中的管理郵件使用者](eop/manage-mail-users-in-eop.md)。對於 EOP 獨立版客戶，我們建議使用目錄同步處理以及如何啟用目錄架構邊緣封鎖;如需詳細資訊，請參閱[使用 Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx)。</span><span class="sxs-lookup"><span data-stu-id="bfb95-p106">A. In order to access the end user spam quarantine, end users must have a valid Office 365 user ID and password. EOP customers protecting on-premises mailboxes must be valid email users created via directory synchronization or the EAC. For more information about managing users, EOP admins can refer to [Manage mail users in EOP](eop/manage-mail-users-in-eop.md). For EOP standalone customers, we recommend using directory synchronization and enabling Directory Based Edge Blocking; for more information, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx).</span></span>
  
 <span data-ttu-id="bfb95-128">**問：不是垃圾郵件的項目是否會傳送到隔離區？**</span><span class="sxs-lookup"><span data-stu-id="bfb95-128">**Q. Can anything other than spam be sent to the quarantine?**</span></span>
  
<span data-ttu-id="bfb95-p107">答：符合傳輸規則的郵件也會傳送到系統管理員隔離區 (如果這是設定要執行的動作)。使用者隔離區僅供隔離垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="bfb95-p107">A. Messages that match a transport rule can also be sent to the administrator quarantine, if that's the configured action. The end user quarantine is for spam only.</span></span>
  
 <span data-ttu-id="bfb95-132">**問：郵件會保留在隔離區中多久？**</span><span class="sxs-lookup"><span data-stu-id="bfb95-132">**Q. For how long are messages kept in the quarantine?**</span></span>
  
<span data-ttu-id="bfb95-p108">A.預設垃圾郵件隔離的郵件會保留在隔離區 15 天時被隔離的郵件符合傳輸規則為 7 天存留在隔離區中。在這段時間內的郵件會刪除並不是可擷取。無法可設定隔離的郵件符合傳輸規則的保留期間。不過，透過 **（天） 的保留天數垃圾郵件**設定內容篩選器原則中可以降低垃圾郵件隔離的郵件的保留期間。如需詳細資訊，請參閱[設定垃圾郵件篩選器原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="bfb95-p108">A. By default, spam-quarantined messages are kept in the quarantine for 15 days, while quarantined messages that matched a transport rule are kept in the quarantine for 7 days. After this period of time the messages are deleted and are not retrievable. The retention period for quarantined messages that matched a transport rule is not configurable. However, the retention period for spam-quarantined messages can be lowered via the **Retain spam for (days)** setting in your content filter policies. For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
  
 <span data-ttu-id="bfb95-139">**問：我可以一次釋出或報告多個隔離的郵件嗎？**</span><span class="sxs-lookup"><span data-stu-id="bfb95-139">**Q. Can I release or report more than one quarantined message at a time?**</span></span>
  
<span data-ttu-id="bfb95-p109">A 無法在 EAC 中或使用者垃圾郵件隔離區中目前無法釋出或一次回報多個郵件的能力。不過，系統管理員可以建立遠端 Windows PowerShell 指令碼來完成此工作。使用[Get-quarantinemessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx)指令程式來搜尋的郵件，以及[版本 QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx)指令程式來釋放它們。</span><span class="sxs-lookup"><span data-stu-id="bfb95-p109">A. The ability to release or report multiple messages at once is not currently available in the EAC or the end user spam quarantine. However, admins can create a remote Windows PowerShell script to accomplish this task. Use the [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) cmdlet to search for messages, and the [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) cmdlet to release them.</span></span> 
  
 <span data-ttu-id="bfb95-144">**問：搜尋隔離的郵件時是否支援萬用字元？我可以搜尋特定網域的隔離郵件嗎？**</span><span class="sxs-lookup"><span data-stu-id="bfb95-144">**Q. Are wildcards supported when searching for quarantined messages? Can I search for quarantined messages for a specific domain?**</span></span>
  
<span data-ttu-id="bfb95-p110">答：在 Exchange 系統管理中心指定搜尋準則時不支援萬用字元。例如，在搜尋寄件者時，您必須指定完整的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="bfb95-p110">A. Wildcards are not supported when specifying search criteria in the Exchange admin center. For example, when searching for a sender, you must specify the full email address.</span></span>
  
<span data-ttu-id="bfb95-148">系統管理員可以使用遠端 Windows PowerShell，指定 [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) 指令程式在特定網域 (例如 contoso.com) 中搜尋隔離的郵件：</span><span class="sxs-lookup"><span data-stu-id="bfb95-148">Using remote Windows PowerShell, admins can specify the [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) cmdlet to search for quarantined messages for a specific domain (for example, contoso.com):</span></span> 
  
```
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```

<span data-ttu-id="bfb95-p111">結果可以傳遞至 [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) 指令程式。請加上 -ReleaseToAll 參數，以將郵件釋出給所有收件者。郵件一經釋出，就無法再釋出一次。</span><span class="sxs-lookup"><span data-stu-id="bfb95-p111">The results can be passed to the [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) cmdlet. Include the -ReleaseToAll parameter to release the message to all recipients. Once a message is released, it can't be released again.</span></span> 
  
```
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```


