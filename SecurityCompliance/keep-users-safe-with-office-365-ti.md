---
title: 保護您的 Office 365 使用者安全與 Office 365 威脅調查及回應功能
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/13/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3387bfc3-028a-42f4-8133-4cbecfaab812
ms.collection:
- M365-security-compliance
description: 了解 Office 365 威脅調查及回應功能如何協助貴組織偵測入侵和威脅，快速地降低，以及復原威脅。
ms.openlocfilehash: 51d776fe2ed5957016028451c1f7dcd1812973c3
ms.sourcegitcommit: 0d5a863f48914eeaaf29f7d2a2022618de186247
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2019
ms.locfileid: "34077259"
---
# <a name="keep-your-office-365-users-safe-with-office-365-threat-investigation-and-response-capabilities"></a><span data-ttu-id="2dc89-103">保護您的 Office 365 使用者安全與 Office 365 威脅調查及回應功能</span><span class="sxs-lookup"><span data-stu-id="2dc89-103">Keep your Office 365 users safe with Office 365 Threat Investigation and Response capabilities</span></span>

## <a name="overview"></a><span data-ttu-id="2dc89-104">概觀</span><span class="sxs-lookup"><span data-stu-id="2dc89-104">Overview</span></span>

<span data-ttu-id="2dc89-105">您知道哪些 Office 365 使用者受到攻擊，或惡化-危害嗎？</span><span class="sxs-lookup"><span data-stu-id="2dc89-105">Do you know which of your Office 365 users are under attack, or worse - compromised?</span></span> <span data-ttu-id="2dc89-106">知道如何減輕及復原免於遭受攻擊的目標使用者？</span><span class="sxs-lookup"><span data-stu-id="2dc89-106">Do know how to mitigate and recover from attacks that are targeting your users?</span></span> <span data-ttu-id="2dc89-107">您知道您可以完全與已在 Office 365 中可用的安全性功能嗎？</span><span class="sxs-lookup"><span data-stu-id="2dc89-107">Did you know you can do exactly this with security capabilities that are already available to you in Office 365?</span></span> 
  
<span data-ttu-id="2dc89-108">[Office 365 威脅調查及回應](office-365-ti.md)是 Office 365 E5 訂閱 （做為 Office 365 進階威脅防護計劃 2 的一部分） 中包含的功能套件。</span><span class="sxs-lookup"><span data-stu-id="2dc89-108">[Office 365 Threat Investigation and Response](office-365-ti.md) is a suite of capabilities included in your Office 365 E5 subscription (as part of Office 365 Advanced Threat Protection Plan 2).</span></span> <span data-ttu-id="2dc89-109">Office 365 威脅調查及回應功能有幫助社交事件 for 解析度的平均時間減少 80%的 Microsoft IT 和案例的輸送量增加每個月相較於先前的 2 季 37%！</span><span class="sxs-lookup"><span data-stu-id="2dc89-109">Office 365 Threat Investigation and Response capabilities have helped Microsoft IT reduce average time to resolution for social engineering incidents by 80%, and increased case throughput by 37% per month compared to the previous 2 quarters!</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="2dc89-110">威脅調查及回應功能 （前身為 Office 365 威脅情報） 現在是 Office 365 進階威脅防護計劃 2，以及其他威脅保護功能的一部分。</span><span class="sxs-lookup"><span data-stu-id="2dc89-110">Threat Investigation and Response capabilities (formerly known as Office 365 Threat Intelligence) are now a part of Office 365 Advanced Threat Protection Plan 2, along with additional threat protection capabilities.</span></span> <span data-ttu-id="2dc89-111">若要深入了解，請參閱[Office 365 進階威脅防護方案和價格](https://products.office.com/exchange/advance-threat-protection)和[Office 365 進階威脅防護服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="2dc89-111">To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>
  
<span data-ttu-id="2dc89-112">我們最近新增了新功能，協助改善如何偵測及復原威脅 ！</span><span class="sxs-lookup"><span data-stu-id="2dc89-112">We've recently added new capabilities to help improve how you can detect and recover from threats!</span></span> <span data-ttu-id="2dc89-113">以下是快速的逐步執行的方式更新的威脅調查及回應功能可以讓您更有效率。</span><span class="sxs-lookup"><span data-stu-id="2dc89-113">Here's a quick walk through of how the updated Threat investigation and response capabilities can make you even more efficient.</span></span>
  
## <a name="detect-intrusions-and-threats"></a><span data-ttu-id="2dc89-114">偵測入侵和威脅</span><span class="sxs-lookup"><span data-stu-id="2dc89-114">Detect intrusions and threats</span></span>

<span data-ttu-id="2dc89-115">[檔案總管](use-explorer-in-security-and-compliance.md)（也稱為威脅總管） 可協助安全性系統管理員和分析師識別並了解是您企業內，因為可以由像安全的表面上無害使用者組態規避即使最複雜的安全性設定的威脅寄件者 whitelists。</span><span class="sxs-lookup"><span data-stu-id="2dc89-115">[Explorer](use-explorer-in-security-and-compliance.md) (also referred to as Threat Explorer) helps security admins and analysts identify and understand threats that are active in your enterprise because even the most complex security settings can be circumvented by seemingly innocuous user configurations like safe sender whitelists.</span></span> <span data-ttu-id="2dc89-116">瀏覽器協助 Office 365 全域或安全性系統管理員快速決定使用者是否已遭到惡意程式碼或釣魚程式的威脅。</span><span class="sxs-lookup"><span data-stu-id="2dc89-116">Explorer helps Office 365 global or security admins quickly determine whether users have been compromised by threats such as malware or phish.</span></span> <span data-ttu-id="2dc89-117">這有助於優先順序哪些使用者最風險的威脅和必要的回應。</span><span class="sxs-lookup"><span data-stu-id="2dc89-117">This helps prioritize which users are most at risk for a threat and the requisite response.</span></span> 
  
<span data-ttu-id="2dc89-118">Explorer 也可協助系統管理員瀏覽使用者與郵件之間的關係。</span><span class="sxs-lookup"><span data-stu-id="2dc89-118">Explorer also helps admins navigate the relationships between users and mail.</span></span> <span data-ttu-id="2dc89-119">了解已損毀的特定郵件的？</span><span class="sxs-lookup"><span data-stu-id="2dc89-119">Know of a particular mail that was bad?</span></span> <span data-ttu-id="2dc89-120">搜尋它以查看哪些使用者接收郵件，然後遵循一系列的事件，並查看這些使用者依次做了什麼。</span><span class="sxs-lookup"><span data-stu-id="2dc89-120">Search for it to see what users received the mail, then follow the series of events and see what those users in turn have done.</span></span>

<span data-ttu-id="2dc89-121">如果您還沒有這些功能，[立即試用](https://aka.ms/tryo365threatintel3)！</span><span class="sxs-lookup"><span data-stu-id="2dc89-121">If you don't already have these capabilties, [try it now](https://aka.ms/tryo365threatintel3)!</span></span> <span data-ttu-id="2dc89-122">取得並[了深入了解 Office 365 威脅調查及回應](https://aka.ms/readmoreabouto365threatintel)。</span><span class="sxs-lookup"><span data-stu-id="2dc89-122">And [learn more about Office 365 Threat Investigation and Response](https://aka.ms/readmoreabouto365threatintel).</span></span>
  
![在 Office 365 中，惡意程式碼系列的色彩編碼的威脅總管的螢幕擷取畫面](media/591338dd-252a-437d-b5f2-87aa42e74b0c.png)
  
## <a name="quickly-mitigate-and-recover-from-threats"></a><span data-ttu-id="2dc89-124">快速減輕和復原的威脅</span><span class="sxs-lookup"><span data-stu-id="2dc89-124">Quickly mitigate and recover from threats</span></span>

<span data-ttu-id="2dc89-125">安全性系統管理員已識別發生可疑或惡意其租用戶中的情形之後, 他們可以快速地包含並回應**事件架構**與該威脅。</span><span class="sxs-lookup"><span data-stu-id="2dc89-125">Once security admins have identified something suspicious or malicious happening in their tenant, they can quickly contain and respond to that threat with the **Incident Framework**.</span></span> <span data-ttu-id="2dc89-126">垃圾的郵件與按一下群組，並快速地從您的使用者信箱中移除電子郵件。</span><span class="sxs-lookup"><span data-stu-id="2dc89-126">Group unwanted messages with one-click and quickly remove the email messages from your user's mailboxes.</span></span> 
  
 <span data-ttu-id="2dc89-127">**更新：** 我們已新增若要直接從事件 Framework 刪除 （軟性或硬刪除） 電子郵件的能力。</span><span class="sxs-lookup"><span data-stu-id="2dc89-127">**UPDATE:** We've added the ability to delete (soft or hard delete) emails directly from the Incident Framework.</span></span> <span data-ttu-id="2dc89-128">先前的系統管理員只能無法移動郵件至使用者的垃圾郵件] 資料夾，其中使用者無法復原的項目。</span><span class="sxs-lookup"><span data-stu-id="2dc89-128">Previously administrators could only move mails to a user's junk folder, where users could recover the item.</span></span> <span data-ttu-id="2dc89-129">具有新發行的刪除功能，您可以現在是確定惡意或垃圾郵件會永久移除。</span><span class="sxs-lookup"><span data-stu-id="2dc89-129">With the newly released Delete capabilities, you can now be sure that a malicious or unwanted mail is removed permanently.</span></span> 
  
<span data-ttu-id="2dc89-130">如果您還沒有這些功能，[立即試用](https://aka.ms/tryo365threatintel3)！</span><span class="sxs-lookup"><span data-stu-id="2dc89-130">If you don't already have these capabilities, [try it now](https://aka.ms/tryo365threatintel3)!</span></span> <span data-ttu-id="2dc89-131">取得並[了深入了解 Office 365 威脅調查及回應能力](https://aka.ms/readmoreabouto365threatintel)。</span><span class="sxs-lookup"><span data-stu-id="2dc89-131">And [learn more about Office 365 Threat Investigation and Response capabilities](https://aka.ms/readmoreabouto365threatintel).</span></span>
  
![事件修復工作的電子郵件清單的螢幕擷取畫面](media/9d8452d3-d8d2-4b26-81f9-76396e08dd17.png)
  
## <a name="leverage-the-threat-telemetry-of-microsoft"></a><span data-ttu-id="2dc89-133">利用 Microsoft 威脅遙測</span><span class="sxs-lookup"><span data-stu-id="2dc89-133">Leverage the threat telemetry of Microsoft</span></span>

<span data-ttu-id="2dc89-134">Office 365 威脅調查及回應能力供電 Microsoft 智慧型安全性圖形的資料。</span><span class="sxs-lookup"><span data-stu-id="2dc89-134">Office 365 Threat Investigation and Response capabilities are powered with data from the Microsoft Intelligent Security Graph.</span></span> <span data-ttu-id="2dc89-135">此圖形取得最新的威脅訊號，可從 1 億 Windows 裝置、 450 20 億個每月的 Azure 登入，以及 Office 365 中的 400 20 億個每月電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="2dc89-135">The graph acquires the latest threat signal from over 1 billion Windows devices, 450 billion monthly Azure logins, and 400 billion monthly email messages in Office 365.</span></span> <span data-ttu-id="2dc89-136">此 unrivaled 的威脅訊號是什麼讓客戶租用戶來說相當重要有影響其組織的潛在威脅的完整檢視系統管理員和安全性分析師廣泛的可視性。</span><span class="sxs-lookup"><span data-stu-id="2dc89-136">This unrivaled threat signal is what gives the broad visibility into a customer tenant that is crucial for admins and security analysts to have a complete view of the threats impacting their organization.</span></span> 
  
   
## <a name="why-use-office-365-threat-investigation-and-response-capabilities"></a><span data-ttu-id="2dc89-137">為什麼要使用 Office 365 威脅調查及回應功能？</span><span class="sxs-lookup"><span data-stu-id="2dc89-137">Why use Office 365 Threat Investigation and Response capabilities?</span></span>

<span data-ttu-id="2dc89-138">Gartner 估計 cybersecurity 上已花費在 2017 單獨透過 $90B。</span><span class="sxs-lookup"><span data-stu-id="2dc89-138">Gartner estimates that in 2017 alone over $90B was spent on cybersecurity.</span></span> <span data-ttu-id="2dc89-139">Sid Deshpande，主要的研究分析師 Gartner，在引號做為指出該 「 業界 shift 鍵，以偵測及回應...</span><span class="sxs-lookup"><span data-stu-id="2dc89-139">Sid Deshpande, principal research analyst at Gartner, is quoted as saying that "the industry's shift to detection and response …</span></span> <span data-ttu-id="2dc89-140">傳送清除郵件防護是難度，除非它繫結到偵測及回應功能 」。</span><span class="sxs-lookup"><span data-stu-id="2dc89-140">sends a clear message that prevention is futile unless it is tied into a detection and response capability."</span></span> <span data-ttu-id="2dc89-141">威脅 investigtion 回應是不可或缺的一部分每家企業產品組合的服務，並可供成為獨立服務或的 Office 365 E5。</span><span class="sxs-lookup"><span data-stu-id="2dc89-141">Threat investigtion and response is a critical part of every enterprise's portfolio of services, and can be consumed as standalone service or as part of Office 365 E5.</span></span>
  
## <a name="whats-next"></a><span data-ttu-id="2dc89-142">下一步是什麼</span><span class="sxs-lookup"><span data-stu-id="2dc89-142">What's Next</span></span>

- <span data-ttu-id="2dc89-143">深入了解 Office 365 威脅調查及回應功能在此記錄的工作階段：[保持往前的 Office 365 的網路攻擊](https://myignite.microsoft.com/videos/53723)</span><span class="sxs-lookup"><span data-stu-id="2dc89-143">Learn more about Office 365 Threat Investigation and response capabilities  in this recorded session: [Stay Ahead of the Cyberattacks with Office 365](https://myignite.microsoft.com/videos/53723)</span></span>
    
- <span data-ttu-id="2dc89-144">[試用 Office 365 威脅調查及回應能力時立即](https://aka.ms/tryo365threatintel3)開始今天 Office E5 試用版或 ！</span><span class="sxs-lookup"><span data-stu-id="2dc89-144">[Try out Office 365 Threat Investigation and Response capabilities now](https://aka.ms/tryo365threatintel3) or begin your Office E5 trial today!</span></span> 
    

