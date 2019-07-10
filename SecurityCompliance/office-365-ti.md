---
title: Office 365 威脅調查及回應
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 03/18/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 32405da5-bee1-4a4b-82e5-8399df94c512
ms.collection:
- M365-security-compliance
description: 了解如何在 Office 365 進階威脅防護的威脅智慧功能可協助您研究針對貴組織的潛在威脅、 回應惡意程式碼、 網路釣魚和其他 Office 365 已經偵測出代表您的攻擊，搜尋的威脅指標。
ms.openlocfilehash: 7e0ce37b33ea2c019005585fd70107145fbfc8aa
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2019
ms.locfileid: "35598079"
---
# <a name="office-365-threat-investigation-and-response"></a><span data-ttu-id="d4523-103">Office 365 威脅調查及回應</span><span class="sxs-lookup"><span data-stu-id="d4523-103">Office 365 threat investigation and response</span></span>

<span data-ttu-id="d4523-104">威脅調查和[Office 365 進階威脅防護](office-365-atp.md)中的回應功能有助於安全性分析師和系統管理員保護其組織的 Office 365 使用者使用：</span><span class="sxs-lookup"><span data-stu-id="d4523-104">Threat investigation and response capabilities in [Office 365 Advanced Threat Protection](office-365-atp.md) help security analysts and administrators protect their organization's Office 365 users by:</span></span>
  
1. <span data-ttu-id="d4523-105">以方便識別、 監視及了解攻擊</span><span class="sxs-lookup"><span data-stu-id="d4523-105">Making it easy to identify, monitor and understand attacks</span></span>
    
2. <span data-ttu-id="d4523-106">協助快速地址威脅在 Exchange Online、 SharePoint Online、 OneDrive for Business 和 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d4523-106">Helping to quickly address threats in Exchange Online, SharePoint Online, OneDrive for Business and Microsoft Teams</span></span>
    
3. <span data-ttu-id="d4523-107">提供見解和協助防止對其組織的攻擊的知識</span><span class="sxs-lookup"><span data-stu-id="d4523-107">Providing insights and knowledge to help prevent attacks against their organization</span></span>

4. <span data-ttu-id="d4523-108">自動化的調查及回應架構的關鍵電子郵件威脅</span><span class="sxs-lookup"><span data-stu-id="d4523-108">Automated investigation and response for critical email based threats</span></span>
    
 
## <a name="whats-changing"></a><span data-ttu-id="d4523-109">什麼有什麼變更？</span><span class="sxs-lookup"><span data-stu-id="d4523-109">What's changing?</span></span>

<span data-ttu-id="d4523-110">以前，Office 365 威脅情報隨附於訂閱，例如 Office 365 E5。</span><span class="sxs-lookup"><span data-stu-id="d4523-110">Formerly, Office 365 Threat Intelligence was included in subscriptions, such as Office 365 E5.</span></span> <span data-ttu-id="d4523-111">這是仍案例中，為威脅調查及回應功能現在是 Office 365 進階威脅防護計劃 2 的一部分 （和這隨附於 Office 365 E5）。</span><span class="sxs-lookup"><span data-stu-id="d4523-111">This is still the case, as threat investigation and response capabilities are now part of Office 365 Advanced Threat Protection Plan 2 (and this is included in Office 365 E5).</span></span> 

<span data-ttu-id="d4523-112">此外，Office 365 威脅情報做為 Office 365 商務版客戶的附加元件已以前可供購買。</span><span class="sxs-lookup"><span data-stu-id="d4523-112">In addition, Office 365 Threat Intelligence was formerly available for purchase as an add-on for Office 365 for business customers.</span></span> <span data-ttu-id="d4523-113">現在，這些功能包含在 Office 365 進階威脅防護計劃 2 （以及在 Office 365 進階威脅防護計劃 1 中的所有功能）。</span><span class="sxs-lookup"><span data-stu-id="d4523-113">Now, these capabilities are included in Office 365 Advanced Threat Protection Plan 2 (along with all the features in Office 365 Advanced Threat Protection Plan 1).</span></span> <span data-ttu-id="d4523-114">若要深入了解，請參閱[Office 365 進階威脅防護方案和價格](https://products.office.com/exchange/advance-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="d4523-114">To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection).</span></span>

<span data-ttu-id="d4523-115">以下是所有這表示：</span><span class="sxs-lookup"><span data-stu-id="d4523-115">Here's what all this means:</span></span>

- <span data-ttu-id="d4523-116">**如果貴組織已有 Office 365 E5**，那麼您已經有進階威脅防護計劃 2，而這包括威脅調查及回應功能。</span><span class="sxs-lookup"><span data-stu-id="d4523-116">**If your organization already has Office 365 E5**, then you already have Advanced Threat Protection Plan 2, and this includes threat investigation and response capabilities.</span></span>

- <span data-ttu-id="d4523-117">**如果您的組織已有 Office 365 威脅情報 （但不是 Office 365 進階威脅防護） 當作附加元件**以另一個的 Office 365 訂閱，然後將現在有 Office 365 進階威脅防護計劃 2，及這包括威脅調查及回應功能。</span><span class="sxs-lookup"><span data-stu-id="d4523-117">**If your organization previously had Office 365 Threat Intelligence (but not Office 365 Advanced Threat Protection) as an add-on** to another Office 365 subscription, then you will now have Office 365 Advanced Threat Protection Plan 2, and this includes threat investigation and response capabilities.</span></span> 

- <span data-ttu-id="d4523-118">**如果您的組織已有 Office 365 進階威脅防護 （但不是 Office 365 威脅情報） 當作附加元件**以另一個的 Office 365 訂閱，然後現在有 Office 365 進階威脅防護計劃 1。</span><span class="sxs-lookup"><span data-stu-id="d4523-118">**If your organization previously had Office 365 Advanced Threat Protection (but not Office 365 Threat Intelligence) as an add-on** to another Office 365 subscription, then you will now have Office 365 Advanced Threat Protection Plan 1.</span></span> <span data-ttu-id="d4523-119">這包括 Office 365 進階威脅防護方案 1，（但不是威脅分析調查及回應功能）。</span><span class="sxs-lookup"><span data-stu-id="d4523-119">This includes Office 365 Advanced Threat Protection Plan 1, (but not threat investigation and response capabilities).</span></span>

<span data-ttu-id="d4523-120">如需詳細資訊，請參閱[Office 365 進階威脅防護方案和價格](https://products.office.com/exchange/advance-threat-protection)與[Office 365 進階威脅防護服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)</span><span class="sxs-lookup"><span data-stu-id="d4523-120">For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)</span></span>

## <a name="get-started-with-threat-investigation-and-response-capabilities"></a><span data-ttu-id="d4523-121">威脅調查及回應功能快速入門</span><span class="sxs-lookup"><span data-stu-id="d4523-121">Get started with threat investigation and response capabilities</span></span>

<span data-ttu-id="d4523-122">若要深入了解威脅調查及回應功能，在 Office 365，以及如何使用它來保留組織中的人員更安全，請使用下列資源。</span><span class="sxs-lookup"><span data-stu-id="d4523-122">Use the following resources to learn more about threat investigation and response capabilities in Office 365, and how you can use it to keep people in your organization safer.</span></span>
  
- <span data-ttu-id="d4523-123">[開始使用威脅調查及回應](get-started-with-ti.md)（這包括必要的角色的相關資訊）</span><span class="sxs-lookup"><span data-stu-id="d4523-123">[Get started with Threat Investigation and Response](get-started-with-ti.md) (this includes information about required roles)</span></span> 
    
- [<span data-ttu-id="d4523-124">了解威脅追蹤器-新增和值得注意</span><span class="sxs-lookup"><span data-stu-id="d4523-124">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)

- [<span data-ttu-id="d4523-125">節省時間和精力自動化調查及回應 （空調） 功能</span><span class="sxs-lookup"><span data-stu-id="d4523-125">Save time and effort with Automated Investigation and Response (AIR) capabilities</span></span>](automated-investigation-response-office.md)

- <span data-ttu-id="d4523-126">[使用以找出並調查的電子郵件和檔案中的惡意內容威脅總管] （或即時偵測）](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="d4523-126">[Use Threat Explorer (or real-time detections) to identify and investigate malicious content in email and files](threat-explorer.md)</span></span>
    
- [<span data-ttu-id="d4523-127">尋找並調查傳送的惡意電子郵件</span><span class="sxs-lookup"><span data-stu-id="d4523-127">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
    
- [<span data-ttu-id="d4523-128">用於模擬的攻擊，並增加使用者的認知的攻擊模擬器</span><span class="sxs-lookup"><span data-stu-id="d4523-128">Use Attack Simulator to simulate attacks and increase user awareness</span></span>](attack-simulator.md)
    
- [<span data-ttu-id="d4523-129">整合 Microsoft Defender 進階威脅防護的威脅調查及回應能力</span><span class="sxs-lookup"><span data-stu-id="d4523-129">Integrate Threat Investigation and Response capabilities with Microsoft Defender Advanced Threat Protection</span></span>](integrate-office-365-ti-with-wdatp.md)
    
## <a name="related-topics"></a><span data-ttu-id="d4523-130">相關主題</span><span class="sxs-lookup"><span data-stu-id="d4523-130">Related topics</span></span>

[<span data-ttu-id="d4523-131">威脅總管檢視</span><span class="sxs-lookup"><span data-stu-id="d4523-131">Threat Explorer views</span></span>](threat-explorer-views.md)

[<span data-ttu-id="d4523-132">防範 Office 365 中的威脅</span><span class="sxs-lookup"><span data-stu-id="d4523-132">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="d4523-133">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="d4523-133">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="d4523-134">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="d4523-134">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
 
