---
title: 隔離常見問題集
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 6/16/2017
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
description: 本主題提供有關託管隔離區的常見問題與解答。
ms.openlocfilehash: 9a9673b3360a9a8b6bf837e09b49aca7a38e2172
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693262"
---
# <a name="quarantine-faq"></a><span data-ttu-id="21637-103">隔離常見問題集</span><span class="sxs-lookup"><span data-stu-id="21637-103">Quarantine FAQ</span></span>

<span data-ttu-id="21637-p101">本主題提供有關託管隔離區的常見問題與解答。這些解答適用於 Microsoft Exchange Online 及 Exchange Online Protection 客戶。</span><span class="sxs-lookup"><span data-stu-id="21637-p101">This topic provides frequently asked questions and answers about the hosted quarantine. Answers are applicable for Microsoft Exchange Online and Exchange Online Protection customers.</span></span>
  
 <span data-ttu-id="21637-106">**問： 如何管理隔離區中的惡意程式碼隔離的郵件？**</span><span class="sxs-lookup"><span data-stu-id="21637-106">**Q. How do I manage malware-quarantined messages in quarantine?**</span></span>
  
<span data-ttu-id="21637-107">您必須使用安全性&amp;以檢視並處理郵件已傳送至隔離區，因為它們包含惡意程式碼的合規性中心。</span><span class="sxs-lookup"><span data-stu-id="21637-107">You need to use the Security &amp; Compliance Center in order to view and work with messages that were sent to quarantine because they contain malware.</span></span> <span data-ttu-id="21637-108">如需詳細資訊，請參閱 < <b0>Office 365 中的隔離電子郵件</b0>。</span><span class="sxs-lookup"><span data-stu-id="21637-108">For more information, see [Quarantine email messages in Office 365](https://support.office.com/article/Quarantine-email-messages-in-Office-365-4c234874-015e-4768-8495-98fcccfc639b).</span></span>
  
 <span data-ttu-id="21637-109">**問：如何設定服務以將因垃圾郵件而遭到隔離的郵件傳送至隔離區？**</span><span class="sxs-lookup"><span data-stu-id="21637-109">**Q. How do I configure the service to send spam-quarantined messages to the quarantine?**</span></span>
  
<span data-ttu-id="21637-110">答：是。</span><span class="sxs-lookup"><span data-stu-id="21637-110">A.</span></span> <span data-ttu-id="21637-111">根據預設，內容篩選的郵件會傳送至 [收件者的垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="21637-111">By default, content-filtered messages are sent to the recipients Junk Email folder.</span></span> <span data-ttu-id="21637-112">不過，系統管理員可以設定內容篩選原則，以將垃圾郵件隔離的郵件傳送至隔離區。</span><span class="sxs-lookup"><span data-stu-id="21637-112">However, admins can configure content filter policies to send spam-quarantined messages to the quarantine instead.</span></span> <span data-ttu-id="21637-113">如需可以在內容篩選的郵件執行的不同動作的詳細資訊，請參閱 <<c0>設定垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="21637-113">For more information about the different actions that can be performed on content-filtered messages, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
  
 <span data-ttu-id="21637-114">**問：此服務是否可讓系統管理員和使用者管理被當成垃圾郵件隔離的郵件？**</span><span class="sxs-lookup"><span data-stu-id="21637-114">**Q. Does the service have administrator and end user management of spam-quarantined messages?**</span></span>
  
<span data-ttu-id="21637-p104">答：如果您是系統管理員，您可以在 Exchange 系統管理中心 (EAC) 中搜尋及檢視關於所有隔離電子郵件的詳細資訊。找到郵件後，您可以將該郵件釋出給特定使用者，並可選擇向 Microsoft 垃圾郵件分析小組報告該郵件為誤判 (非垃圾郵件)。如需詳細資訊，請參閱 [以系統管理員身分找到並釋放被隔離的郵件](find-and-release-quarantined-messages-as-an-administrator.md)。</span><span class="sxs-lookup"><span data-stu-id="21637-p104">A. As an administrator, you can search for and view details about all quarantined email messages in the Exchange admin center (EAC). After locating the message, you can release it to specific users and optionally report it as a false positive (not junk) to the Microsoft Spam Analysis Team. For more information, see [Find and release quarantined messages as an administrator](find-and-release-quarantined-messages-as-an-administrator.md).</span></span>
  
<span data-ttu-id="21637-119">如果您是使用者，則可以透過下列項目管理自己被當成垃圾郵件隔離的郵件：</span><span class="sxs-lookup"><span data-stu-id="21637-119">As an end user, you can manage your own spam-quarantined messages via:</span></span> 
  
- <span data-ttu-id="21637-120">垃圾郵件隔離使用者介面。</span><span class="sxs-lookup"><span data-stu-id="21637-120">The spam quarantine user interface.</span></span> <span data-ttu-id="21637-121">如需詳細資訊，請參閱 [Find and Release Quarantined Messages (End Users)](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx)。</span><span class="sxs-lookup"><span data-stu-id="21637-121">For more information, see [Find and Release Quarantined Messages (End Users)](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx).</span></span>
        
 <span data-ttu-id="21637-122">**問：如何授權使用者存取垃圾郵件隔離區？**</span><span class="sxs-lookup"><span data-stu-id="21637-122">**Q. How do I grant access to the spam quarantine for my end users?**</span></span>
  
<span data-ttu-id="21637-123">答：是。</span><span class="sxs-lookup"><span data-stu-id="21637-123">A.</span></span> <span data-ttu-id="21637-124">若要存取使用者垃圾郵件隔離區，使用者必須具有有效的 Office 365 使用者識別碼和密碼。</span><span class="sxs-lookup"><span data-stu-id="21637-124">In order to access the end user spam quarantine, end users must have a valid Office 365 user ID and password.</span></span> <span data-ttu-id="21637-125">保護內部部署信箱的 EOP 客戶必須是透過目錄同步處理或 EAC 建立的有效電子郵件使用者。</span><span class="sxs-lookup"><span data-stu-id="21637-125">EOP customers protecting on-premises mailboxes must be valid email users created via directory synchronization or the EAC.</span></span> <span data-ttu-id="21637-126">如需管理使用者的詳細資訊，EOP 系統管理員可以參閱[管理 EOP 中的郵件使用者](eop/manage-mail-users-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="21637-126">For more information about managing users, EOP admins can refer to [Manage mail users in EOP](eop/manage-mail-users-in-eop.md).</span></span> <span data-ttu-id="21637-127">對於 EOP 獨立客戶，則建議使用目錄同步處理並啟用目錄架構邊緣封鎖；如需詳細資訊，請參閱[使用目錄架構邊緣封鎖以拒絕傳送至無效收件者的郵件](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx)。</span><span class="sxs-lookup"><span data-stu-id="21637-127">For EOP standalone customers, we recommend using directory synchronization and enabling Directory Based Edge Blocking; for more information, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx).</span></span>
  
 <span data-ttu-id="21637-128">**問：不是垃圾郵件的項目是否會傳送到隔離區？**</span><span class="sxs-lookup"><span data-stu-id="21637-128">**Q. Can anything other than spam be sent to the quarantine?**</span></span>
  
<span data-ttu-id="21637-129">答：是。</span><span class="sxs-lookup"><span data-stu-id="21637-129">A.</span></span> <span data-ttu-id="21637-130">符合郵件流程規則 （也稱為傳輸規則） 的郵件也傳送至管理員隔離區，如果是設定的動作。</span><span class="sxs-lookup"><span data-stu-id="21637-130">Messages that match a mail flow rule (also known as a transport rule) can also be sent to the administrator quarantine, if that's the configured action.</span></span> <span data-ttu-id="21637-131">垃圾郵件只是使用者隔離區。</span><span class="sxs-lookup"><span data-stu-id="21637-131">The end user quarantine is for spam only.</span></span>
  
 <span data-ttu-id="21637-132">**問：郵件會保留在隔離區中多久？**</span><span class="sxs-lookup"><span data-stu-id="21637-132">**Q. For how long are messages kept in the quarantine?**</span></span>
  
<span data-ttu-id="21637-133">答：是。</span><span class="sxs-lookup"><span data-stu-id="21637-133">A.</span></span> <span data-ttu-id="21637-134">根據預設，垃圾郵件隔離的郵件會保留在隔離區 30 天，而被隔離的郵件符合郵件流程規則會保留在隔離區 7 天。</span><span class="sxs-lookup"><span data-stu-id="21637-134">By default, spam-quarantined messages are kept in the quarantine for 30 days, while quarantined messages that matched a mail flow rule are kept in the quarantine for 7 days.</span></span> <span data-ttu-id="21637-135">超過這段時間後，郵件就會遭到刪除，而無法加以擷取。</span><span class="sxs-lookup"><span data-stu-id="21637-135">After this period of time the messages are deleted and are not retrievable.</span></span> <span data-ttu-id="21637-136">符合郵件流程規則的隔離郵件的保留期間不是可設定的。</span><span class="sxs-lookup"><span data-stu-id="21637-136">The retention period for quarantined messages that matched a mail flow rule is not configurable.</span></span> <span data-ttu-id="21637-137">不過，您可以透過內容篩選原則的 **[保留垃圾郵件的天數]** 設定，縮短垃圾郵件隔離郵件的保留期限。</span><span class="sxs-lookup"><span data-stu-id="21637-137">However, the retention period for spam-quarantined messages can be lowered via the **Retain spam for (days)** setting in your content filter policies.</span></span> <span data-ttu-id="21637-138">如需詳細資訊，請參閱[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="21637-138">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
  
 <span data-ttu-id="21637-139">**問：我可以一次釋出或報告多個隔離的郵件嗎？**</span><span class="sxs-lookup"><span data-stu-id="21637-139">**Q. Can I release or report more than one quarantined message at a time?**</span></span>
  
<span data-ttu-id="21637-140">答：是。</span><span class="sxs-lookup"><span data-stu-id="21637-140">A.</span></span> <span data-ttu-id="21637-141">無法在 EAC 中或使用者垃圾郵件隔離區中目前可用版本或一次回報多封郵件的能力。</span><span class="sxs-lookup"><span data-stu-id="21637-141">The ability to release or report multiple messages at once is not currently available in the EAC or the end user spam quarantine.</span></span> <span data-ttu-id="21637-142">不過，系統管理員可以建立遠端 Windows PowerShell 指令碼，以完成這項工作。</span><span class="sxs-lookup"><span data-stu-id="21637-142">However, admins can create a remote Windows PowerShell script to accomplish this task.</span></span> <span data-ttu-id="21637-143">使用[Get-quarantinemessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx)指令程式來搜尋郵件，並釋放這些[Release-quarantinemessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx)指令程式。</span><span class="sxs-lookup"><span data-stu-id="21637-143">Use the [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) cmdlet to search for messages, and the [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) cmdlet to release them.</span></span> 
  
 <span data-ttu-id="21637-144">**問：搜尋隔離的郵件時是否支援萬用字元？我可以搜尋特定網域的隔離郵件嗎？**</span><span class="sxs-lookup"><span data-stu-id="21637-144">**Q. Are wildcards supported when searching for quarantined messages? Can I search for quarantined messages for a specific domain?**</span></span>
  
<span data-ttu-id="21637-p110">答：在 Exchange 系統管理中心指定搜尋準則時不支援萬用字元。例如，在搜尋寄件者時，您必須指定完整的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="21637-p110">A. Wildcards are not supported when specifying search criteria in the Exchange admin center. For example, when searching for a sender, you must specify the full email address.</span></span>
  
<span data-ttu-id="21637-148">系統管理員可以使用遠端 Windows PowerShell，指定 [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) 指令程式在特定網域 (例如 contoso.com) 中搜尋隔離的郵件：</span><span class="sxs-lookup"><span data-stu-id="21637-148">Using remote Windows PowerShell, admins can specify the [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) cmdlet to search for quarantined messages for a specific domain (for example, contoso.com):</span></span> 
  
```
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```

<span data-ttu-id="21637-p111">結果可以傳遞至 [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) 指令程式。請加上 -ReleaseToAll 參數，以將郵件釋出給所有收件者。郵件一經釋出，就無法再釋出一次。</span><span class="sxs-lookup"><span data-stu-id="21637-p111">The results can be passed to the [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) cmdlet. Include the -ReleaseToAll parameter to release the message to all recipients. Once a message is released, it can't be released again.</span></span> 
  
```
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```


