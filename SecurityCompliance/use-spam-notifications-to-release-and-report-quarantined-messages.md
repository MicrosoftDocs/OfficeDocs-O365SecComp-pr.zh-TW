---
title: 利用 Office 365 中的使用者垃圾郵件通知來釋放並回報被隔離的郵件
ms.author: tracyp
author: MSFTTracyP
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
ms.collection:
- M365-security-compliance
description: 如果您的系統管理員可讓使用者的通知，您會收到通知訊息，其中列出傳送至您的信箱已識別為垃圾郵件、 大量或網路釣魚郵件提交之郵件。 您可以釋出或回報郵件之後收到通知。
ms.openlocfilehash: 7f68b70298fca7d8ed5f5e5b8dc9c727c3a6a6c1
ms.sourcegitcommit: 5eb664b6ecef94aef4018a75684ee4ae66c486bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/08/2019
ms.locfileid: "30492722"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a><span data-ttu-id="2381d-104">利用 Office 365 中的使用者垃圾郵件通知來釋放並回報被隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="2381d-104">Use user spam notifications to release and report quarantined messages in Office 365</span></span>

<span data-ttu-id="2381d-105">如果您的系統管理員可讓使用者的垃圾郵件通知，您會收到通知訊息，列出寄送至您信箱的已識別為垃圾郵件而遭到隔離的郵件。</span><span class="sxs-lookup"><span data-stu-id="2381d-105">If your admin enables spam notifications for users, you'll receive a notification message that lists messages addressed to your mailbox that were identified as spam and quarantined instead.</span></span>
  
> [!TIP]
> <span data-ttu-id="2381d-106">如果您是系統管理員且想来啟用此功能，您可以選擇選項時您[修改預設的反垃圾郵件原則](https://go.microsoft.com/fwlink/?LinkId=800313)。</span><span class="sxs-lookup"><span data-stu-id="2381d-106">If you're an administrator and want to enable this feature, you can choose the option when you [modify a default anti-spam policy](https://go.microsoft.com/fwlink/?LinkId=800313).</span></span> 
  
<span data-ttu-id="2381d-107">您收到的訊息包括清單中的垃圾郵件隔離的郵件，您有的日期和時間 （全球定位時間或 UTC） 的最後一則訊息數目。</span><span class="sxs-lookup"><span data-stu-id="2381d-107">The message you receive includes the number of spam-quarantined messages you have, and the date and time (in Universal Coordinated Time or UTC) of the last message in the list.</span></span> <span data-ttu-id="2381d-108">清單會包含每一封郵件的下列項目：</span><span class="sxs-lookup"><span data-stu-id="2381d-108">The list includes the following for each message:</span></span>
  
- <span data-ttu-id="2381d-109">**寄件者**傳送名稱和電子郵件地址將隔離的郵件。</span><span class="sxs-lookup"><span data-stu-id="2381d-109">**Sender** The send name and email address of the quarantined message.</span></span> 
    
- <span data-ttu-id="2381d-110">**主旨** 隔離之郵件的主旨行文字。</span><span class="sxs-lookup"><span data-stu-id="2381d-110">**Subject** The subject line text of the quarantined message.</span></span> 
    
- <span data-ttu-id="2381d-111">**日期** 郵件遭隔離時的日期和時間 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="2381d-111">**Date** The date and time (in UTC) that the message was quarantined.</span></span> 
    
- <span data-ttu-id="2381d-112">**大小**(Kb) 郵件的大小。</span><span class="sxs-lookup"><span data-stu-id="2381d-112">**Size** The size of the message, in kilobytes (KBs).</span></span> 
    
<span data-ttu-id="2381d-113">目前，有兩種您可以對隔離的郵件採取的動作：</span><span class="sxs-lookup"><span data-stu-id="2381d-113">Currently, there are two actions you can take with a quarantined message:</span></span>
  
- <span data-ttu-id="2381d-114">**釋出到收件匣**選擇此選項，即可將郵件傳送至收件匣，讓您可以檢視。</span><span class="sxs-lookup"><span data-stu-id="2381d-114">**Release to Inbox** Choose this to send the message to your inbox, where you can view it.</span></span> 
    
- <span data-ttu-id="2381d-115">**報告為不是垃圾郵件**選擇此選項以傳送郵件的副本給 Microsoft 進行分析。</span><span class="sxs-lookup"><span data-stu-id="2381d-115">**Report as Not Junk** Choose this to send a copy of the message to Microsoft for analysis.</span></span> <span data-ttu-id="2381d-116">垃圾郵件小組會評估及分析郵件，並且根據分析結果來調整反垃圾郵件篩選規則以允許此郵件通過。</span><span class="sxs-lookup"><span data-stu-id="2381d-116">The spam team evaluates and analyzes the message, and, depending on the results of the analysis, adjusts the anti-spam filter rules to allow the message through.</span></span> 
    
<span data-ttu-id="2381d-117">請注意下列事項：</span><span class="sxs-lookup"><span data-stu-id="2381d-117">Be aware of the following:</span></span>
  
- <span data-ttu-id="2381d-118">因為它們符合郵件流程規則遭到隔離的郵件不會包含在使用者隔離的郵件。</span><span class="sxs-lookup"><span data-stu-id="2381d-118">Messages that are quarantined because they matched a mail flow rule are not included in user quarantined messages.</span></span> <span data-ttu-id="2381d-119">該訊息只會列出因垃圾郵件而遭到隔離的郵件。</span><span class="sxs-lookup"><span data-stu-id="2381d-119">Only spam-quarantined messages are listed.</span></span>
    
- <span data-ttu-id="2381d-120">您只能釋出郵件並將其報告為誤判 (非垃圾郵件)   一次。</span><span class="sxs-lookup"><span data-stu-id="2381d-120">You can only release a message and report it as a false positive (not junk) once.</span></span>
    

