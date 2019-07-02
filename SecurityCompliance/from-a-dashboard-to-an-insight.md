---
title: 逐步解說 - 從儀表板到深入解析
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/4/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 703c41df-b3e2-4e7e-9eeb-1a0b8d60fb56
ms.collection:
- M365-security-compliance
description: 瞭解如何從儀表板前往安全性&amp;與規範中心中建議的動作。
ms.openlocfilehash: 40f927ff394bc5a79e62eea7048bf2a48617cd90
ms.sourcegitcommit: 0d5a863f48914eeaaf29f7d2a2022618de186247
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2019
ms.locfileid: "34078019"
---
# <a name="walkthrough---from-a-dashboard-to-an-insight"></a><span data-ttu-id="5685c-103">逐步解說 - 從儀表板到深入解析</span><span class="sxs-lookup"><span data-stu-id="5685c-103">Walkthrough - From a dashboard to an insight</span></span>

<span data-ttu-id="5685c-104">如果您是[Office 365 安全性&amp;合規性中心的報表和深入](reports-and-insights-in-security-and-compliance.md)瞭解, 可能會有助您瞭解如何輕鬆從儀表板流覽至真知灼見和建議的動作。</span><span class="sxs-lookup"><span data-stu-id="5685c-104">If you're new to [reports and insights in the Office 365 Security &amp; Compliance Center](reports-and-insights-in-security-and-compliance.md), it might help to see how you can easily navigate from a dashboard to an insight and recommended actions.</span></span> 
  
<span data-ttu-id="5685c-105">這是安全性&amp;合規性中心的數個演練之一。</span><span class="sxs-lookup"><span data-stu-id="5685c-105">This is one of several walkthroughs for the Security &amp; Compliance Center.</span></span> <span data-ttu-id="5685c-106">若要查看其他演練, 請參閱[相關主題](#related-topics)一節。</span><span class="sxs-lookup"><span data-stu-id="5685c-106">To see additional walkthroughs, see the [Related topics](#related-topics) section.</span></span> 
  
## <a name="walkthrough-from-a-dashboard-to-an-insight"></a><span data-ttu-id="5685c-107">逐步解說: 從儀表板到洞察力</span><span class="sxs-lookup"><span data-stu-id="5685c-107">Walkthrough: From a dashboard to an insight</span></span>

<span data-ttu-id="5685c-108">讓我們逐步流覽從儀表板到報表的流程, 以深入瞭解。</span><span class="sxs-lookup"><span data-stu-id="5685c-108">Let's walk through the flow from a dashboard to a report to an insight and action.</span></span> <span data-ttu-id="5685c-109">(這是一個簡短的[欺騙智慧](learn-about-spoof-intelligence.md)範例)。</span><span class="sxs-lookup"><span data-stu-id="5685c-109">(This is a brief [spoof intelligence](learn-about-spoof-intelligence.md) example.)</span></span> 
  
1. <span data-ttu-id="5685c-110">我們從[安全性&amp;合規性中心](https://protection.office.com)的 [安全性] 儀表板開始。</span><span class="sxs-lookup"><span data-stu-id="5685c-110">We begin with the Security dashboard in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="5685c-111">(移至 [**威脅管理** \> ]**儀表板**)。)</span><span class="sxs-lookup"><span data-stu-id="5685c-111">(Go to **Threat management** \> **Dashboard**.)</span></span><br><span data-ttu-id="5685c-112">![在安全性&amp;與合規性中心中, 選擇\> [威脅管理] 儀表板](media/05a38660-eb13-4960-a266-11809c453d95.png)</span><span class="sxs-lookup"><span data-stu-id="5685c-112">![In the Security &amp; Compliance Center, choose Threat management \> Dashboard](media/05a38660-eb13-4960-a266-11809c453d95.png)</span></span><br>
  
2. <span data-ttu-id="5685c-113">在 [**洞察力**] 列中, 我們注意到指出我們需要檢查某些網域可能可疑的資訊。</span><span class="sxs-lookup"><span data-stu-id="5685c-113">In the **Insights** row, we notice an insight indicating we need to review some domains that might be suspicious.</span></span> <span data-ttu-id="5685c-114">(在 [**洞察力**] 列中, 按一下 [**網域配對**]。)</span><span class="sxs-lookup"><span data-stu-id="5685c-114">(In the **Insights** row, click **Domain pairs**.)</span></span><br><span data-ttu-id="5685c-115">![真知灼見資料列提及可能的哄騙問題](media/dd1d0cb3-3201-45d7-b41d-18a0944fe85d.png)</span><span class="sxs-lookup"><span data-stu-id="5685c-115">![The Insights row mentions potential spoofing concerns](media/dd1d0cb3-3201-45d7-b41d-18a0944fe85d.png)</span></span><br>
  
3. <span data-ttu-id="5685c-116">我們會取得與哄騙情報相關的活動清單。</span><span class="sxs-lookup"><span data-stu-id="5685c-116">We get a list of activities related to spoof intelligence.</span></span> <span data-ttu-id="5685c-117">在這些情況下, 電子郵件的傳送方式似乎來自我們的組織, 但實際上是從另一個組織傳送。</span><span class="sxs-lookup"><span data-stu-id="5685c-117">These are instances where email messages were sent that look like they came from our organization but were, in fact, sent from another organization.</span></span> <span data-ttu-id="5685c-118">目標是要判斷是否已授權偽造的郵件。</span><span class="sxs-lookup"><span data-stu-id="5685c-118">The goal is to determine whether the spoofed messages are authorized or not.</span></span><br><span data-ttu-id="5685c-119">![欺騙情報洞察力](media/a2e2b4fd-0c1e-499f-8401-cf3089da82fa.png)</span><span class="sxs-lookup"><span data-stu-id="5685c-119">![Spoof intelligence insights](media/a2e2b4fd-0c1e-499f-8401-cf3089da82fa.png)</span></span><br><span data-ttu-id="5685c-120">在此清單中, 我們可以依郵件計數、偽造的上次偵測日期來排序資訊, 等等。</span><span class="sxs-lookup"><span data-stu-id="5685c-120">In this list, we can sort the information by message count, date the spoofing was last detected, and more.</span></span> <span data-ttu-id="5685c-121">(按一下 [資料行標題], 例如 [**訊息計數**] 或 [**最後一次看到**的], 查看排序的運作方式)</span><span class="sxs-lookup"><span data-stu-id="5685c-121">(Click column headings, such as **Message count** or **Last seen** to see how sorting works.)</span></span> 
    
4. <span data-ttu-id="5685c-122">選取清單中的專案會開啟 [詳細資料] 窗格, 我們可以在其中看到其他資訊, 包括偵測到的類似電子郵件。</span><span class="sxs-lookup"><span data-stu-id="5685c-122">Selecting an item in the list opens a details pane where we can see additional information, including similar email messages that were detected.</span></span> <span data-ttu-id="5685c-123">(按一下清單中的專案, 並查看資訊和建議。)</span><span class="sxs-lookup"><span data-stu-id="5685c-123">(Click an item in the list, and review the information and recommendations.)</span></span><br>![選取專案會開啟詳細資料窗格](media/7ad1faa5-6ca2-474e-a609-eb275e0a8e59.png)<br>
  
5. <span data-ttu-id="5685c-125">請注意, 在窗格頂端, 我們有選項可將寄件者新增至組織的允許寄件者清單。</span><span class="sxs-lookup"><span data-stu-id="5685c-125">Notice that at the top of the pane, we have the option to add the sender to our organization's allowed senders list.</span></span> <span data-ttu-id="5685c-126">(請不要選取 [**新增至 ' AllowedtoSpoof ' 寄件者允許清單**, 直到您確定要這麼做。</span><span class="sxs-lookup"><span data-stu-id="5685c-126">(Do not select **Add to 'AllowedtoSpoof' sender allow list** until you are sure you want to do this.</span></span> <span data-ttu-id="5685c-127">[深入瞭解欺騙情報](learn-about-spoof-intelligence.md)。)</span><span class="sxs-lookup"><span data-stu-id="5685c-127">[Learn more about spoof intelligence](learn-about-spoof-intelligence.md).)</span></span><br><span data-ttu-id="5685c-128">![您可以授權寄件者](media/caf0c20a-6047-486d-8060-5a229a3de49f.png)</span><span class="sxs-lookup"><span data-stu-id="5685c-128">![You can authorize a sender](media/caf0c20a-6047-486d-8060-5a229a3de49f.png)</span></span>
  
<span data-ttu-id="5685c-129">如此一來, 我們就可以從儀表板移至真知灼見和建議的動作。</span><span class="sxs-lookup"><span data-stu-id="5685c-129">In this way, we can move from a dashboard to insights and recommended actions.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="5685c-130">相關主題</span><span class="sxs-lookup"><span data-stu-id="5685c-130">Related topics</span></span>

[<span data-ttu-id="5685c-131">逐步解說: 從深入瞭解到詳細報告</span><span class="sxs-lookup"><span data-stu-id="5685c-131">Walkthrough: From an insight to a detailed report</span></span>](from-an-insight-to-a-detailed-report.md)
  
[<span data-ttu-id="5685c-132">逐步解說: 從詳細報告到深入瞭解</span><span class="sxs-lookup"><span data-stu-id="5685c-132">Walkthrough: From a detailed report to an insight</span></span>](from-a-detailed-report-to-an-insight.md)
  

