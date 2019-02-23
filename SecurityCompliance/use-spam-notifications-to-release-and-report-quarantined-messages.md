---
title: 利用 Office 365 中的使用者垃圾郵件通知來釋放並回報被隔離的郵件
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/12/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
description: 如果您的系統可讓使用者的通知，您會收到列出訊息傳送給您的信箱已識別為垃圾郵件、 大量或網路釣魚郵件通知訊息。您可以釋出或報告的郵件之後被通知。
ms.openlocfilehash: eb51d8f73ff00781b74cfba4e580668710ce7a76
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216393"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a><span data-ttu-id="d4fc0-104">利用 Office 365 中的使用者垃圾郵件通知來釋放並回報被隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="d4fc0-104">Use user spam notifications to release and report quarantined messages in Office 365</span></span>

<span data-ttu-id="d4fc0-105">如果您的系統可讓使用者的垃圾郵件通知，您會收到通知訊息，列出寄給您的信箱已識別為垃圾郵件及改用隔離的郵件。</span><span class="sxs-lookup"><span data-stu-id="d4fc0-105">If your admin enables spam notifications for users, you'll receive a notification message that lists messages addressed to your mailbox that were identified as spam and quarantined instead.</span></span>
  
> [!TIP]
> <span data-ttu-id="d4fc0-106">如果您是系統管理員和想来啟用此功能，您可以選擇選項當您[修改預設的反垃圾郵件原則](https://go.microsoft.com/fwlink/?LinkId=800313)。</span><span class="sxs-lookup"><span data-stu-id="d4fc0-106">If you're an administrator and want to enable this feature, you can choose the option when you [modify a default anti-spam policy](https://go.microsoft.com/fwlink/?LinkId=800313).</span></span> 
  
<span data-ttu-id="d4fc0-p102">您會收到的郵件包括清單中的垃圾郵件隔離的郵件您擁有的日期和時間 （以國際標準時間或 UTC） 的最後一則訊息數。清單會包含每個郵件的下列項目：</span><span class="sxs-lookup"><span data-stu-id="d4fc0-p102">The message you receive includes the number of spam-quarantined messages you have, and the date and time (in Universal Coordinated Time or UTC) of the last message in the list. The list includes the following for each message:</span></span>
  
- <span data-ttu-id="d4fc0-109">**寄件者**隔離之郵件的傳送名稱和電子郵件位址。</span><span class="sxs-lookup"><span data-stu-id="d4fc0-109">**Sender** The send name and email address of the quarantined message.</span></span> 
    
- <span data-ttu-id="d4fc0-110">**主旨** 隔離之郵件的主旨行文字。</span><span class="sxs-lookup"><span data-stu-id="d4fc0-110">**Subject** The subject line text of the quarantined message.</span></span> 
    
- <span data-ttu-id="d4fc0-111">**日期** 郵件遭隔離時的日期和時間 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="d4fc0-111">**Date** The date and time (in UTC) that the message was quarantined.</span></span> 
    
- <span data-ttu-id="d4fc0-112">**大小**(Kb) 之郵件的大小。</span><span class="sxs-lookup"><span data-stu-id="d4fc0-112">**Size** The size of the message, in kilobytes (KBs).</span></span> 
    
<span data-ttu-id="d4fc0-113">目前有兩個所能使用隔離的郵件採取的動作：</span><span class="sxs-lookup"><span data-stu-id="d4fc0-113">Currently, there are two actions you can take with a quarantined message:</span></span>
  
- <span data-ttu-id="d4fc0-114">**釋出到收件匣**選擇此選項可將郵件傳送給收件匣，其中您可以檢視。</span><span class="sxs-lookup"><span data-stu-id="d4fc0-114">**Release to Inbox** Choose this to send the message to your inbox, where you can view it.</span></span> 
    
- <span data-ttu-id="d4fc0-p103">**為不是垃圾郵件報告**選擇此選項可將郵件的複本傳送給 Microsoft 進行分析。垃圾郵件小組評估及分析郵件並、 分析結果，視會調整以允許透過訊息的反垃圾郵件篩選規則。</span><span class="sxs-lookup"><span data-stu-id="d4fc0-p103">**Report as Not Junk** Choose this to send a copy of the message to Microsoft for analysis. The spam team evaluates and analyzes the message, and, depending on the results of the analysis, adjusts the anti-spam filter rules to allow the message through.</span></span> 
    
<span data-ttu-id="d4fc0-117">請注意下列事項：</span><span class="sxs-lookup"><span data-stu-id="d4fc0-117">Be aware of the following:</span></span>
  
- <span data-ttu-id="d4fc0-p104">因為它們相符的郵件流程規則隔離的郵件並不包含使用者隔離的郵件。列出僅垃圾郵件隔離的郵件。</span><span class="sxs-lookup"><span data-stu-id="d4fc0-p104">Messages that are quarantined because they matched a mail flow rule are not included in user quarantined messages. Only spam-quarantined messages are listed.</span></span>
    
- <span data-ttu-id="d4fc0-120">您只能釋出郵件並將其報告為誤判 (非垃圾郵件)   一次。</span><span class="sxs-lookup"><span data-stu-id="d4fc0-120">You can only release a message and report it as a false positive (not junk) once.</span></span>
    

