---
title: Office 365 威脅調查及回應
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/18/2019
ms.audience: Admin
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
ms.openlocfilehash: 6f7e6e0a49bb4035458af2e9d7e45fd954a1f9fc
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32265395"
---
# <a name="office-365-threat-investigation-and-response"></a><span data-ttu-id="1f62e-103">Office 365 威脅調查及回應</span><span class="sxs-lookup"><span data-stu-id="1f62e-103">Office 365 threat investigation and response</span></span>

<span data-ttu-id="1f62e-104">威脅調查和[Office 365 進階威脅防護](office-365-atp.md)中的回應功能有助於安全性分析師和系統管理員保護其組織的 Office 365 使用者使用：</span><span class="sxs-lookup"><span data-stu-id="1f62e-104">Threat investigation and response capabilities in [Office 365 Advanced Threat Protection](office-365-atp.md) help security analysts and administrators protect their organization's Office 365 users by:</span></span>
  
1. <span data-ttu-id="1f62e-105">以方便識別、 監視及了解攻擊</span><span class="sxs-lookup"><span data-stu-id="1f62e-105">Making it easy to identify, monitor and understand attacks</span></span>
    
2. <span data-ttu-id="1f62e-106">協助快速地址威脅在 Exchange Online、 SharePoint Online、 OneDrive for Business 和 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1f62e-106">Helping to quickly address threats in Exchange Online, SharePoint Online, OneDrive for Business and Microsoft Teams</span></span>
    
3. <span data-ttu-id="1f62e-107">提供見解和協助防止對其組織的攻擊的知識</span><span class="sxs-lookup"><span data-stu-id="1f62e-107">Providing insights and knowledge to help prevent attacks against their organization</span></span>

4. <span data-ttu-id="1f62e-108">自動化的調查及回應架構的關鍵電子郵件威脅</span><span class="sxs-lookup"><span data-stu-id="1f62e-108">Automated investigation and response for critical email based threats</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="1f62e-109">**Office 365 進階威脅防護和威脅調查及回應 （先前稱為 Office 365 威脅情報） 是現在 Office 365 進階威脅防護計劃 2**，以及中納入其他威脅保護功能特定的訂閱，例如[Microsoft 365 企業版](https://www.microsoft.com/microsoft-365/enterprise/home)、 [Microsoft 365 商務版](https://www.microsoft.com/microsoft-365/business)、 Office 365 企業版 E5、 Office 365 教育版 A5 等。如果貴組織擁有不包含 Office 365 ATP 的訂閱，您可能可以當作附加元件購買 ATP。</span><span class="sxs-lookup"><span data-stu-id="1f62e-109">**Office 365 Advanced Threat Protection and Threat Investigation and Response (previously known as Office 365 Threat Intelligence) are now Office 365 Advanced Threat Protection Plan 2**, along with additional threat protection capabilities included in in certain subscriptions, such as [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, Office 365 Education A5, etc. If your organization has a subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on.</span></span> <span data-ttu-id="1f62e-110">如需詳細資訊，請參閱[Office 365 進階威脅防護方案和價格](https://products.office.com/exchange/advance-threat-protection)和[Office 365 進階威脅防護服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)。</span><span class="sxs-lookup"><span data-stu-id="1f62e-110">For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp).</span></span> 
  
## <a name="whats-changing"></a><span data-ttu-id="1f62e-111">什麼有什麼變更？</span><span class="sxs-lookup"><span data-stu-id="1f62e-111">What's changing?</span></span>

<span data-ttu-id="1f62e-112">以前，Office 365 威脅情報隨附於訂閱，例如 Office 365 企業版 E5。</span><span class="sxs-lookup"><span data-stu-id="1f62e-112">Formerly, Office 365 Threat Intelligence was included in subscriptions, such as Office 365 Enterprise E5.</span></span> <span data-ttu-id="1f62e-113">這是仍案例中，為威脅調查及回應功能現在是 Office 365 進階威脅防護計劃 2 的一部分 （和這隨附於 Office 365 企業版 E5）。</span><span class="sxs-lookup"><span data-stu-id="1f62e-113">This is still the case, as threat investigation and response capabilities are now part of Office 365 Advanced Threat Protection Plan 2 (and this is included in Office 365 Enterprise E5).</span></span> 

<span data-ttu-id="1f62e-114">此外，Office 365 威脅情報做為 Office 365 商務版客戶的附加元件已以前可供購買。</span><span class="sxs-lookup"><span data-stu-id="1f62e-114">In addition, Office 365 Threat Intelligence was formerly available for purchase as an add-on for Office 365 for business customers.</span></span> <span data-ttu-id="1f62e-115">現在，這些功能包含在 Office 365 進階威脅防護計劃 2 （以及在 Office 365 進階威脅防護計劃 1 中的所有功能）。</span><span class="sxs-lookup"><span data-stu-id="1f62e-115">Now, these capabilities are included in Office 365 Advanced Threat Protection Plan 2 (along with all the features in Office 365 Advanced Threat Protection Plan 1).</span></span> <span data-ttu-id="1f62e-116">若要深入了解，請參閱[Office 365 進階威脅防護方案和價格](https://products.office.com/exchange/advance-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="1f62e-116">To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection).</span></span>

<span data-ttu-id="1f62e-117">以下是所有這表示：</span><span class="sxs-lookup"><span data-stu-id="1f62e-117">Here's what all this means:</span></span>

- <span data-ttu-id="1f62e-118">**如果貴組織已有 Office 365 企業版 E5**，然後您已經有進階威脅防護計劃 2，而這包括威脅調查及回應功能。</span><span class="sxs-lookup"><span data-stu-id="1f62e-118">**If your organization already has Office 365 Enterprise E5**, then you already have Advanced Threat Protection Plan 2, and this includes threat investigation and response capabilities.</span></span>

- <span data-ttu-id="1f62e-119">**如果您的組織已有 Office 365 威脅情報 （但不是 Office 365 進階威脅防護） 當作附加元件**以另一個的 Office 365 訂閱，然後將現在有 Office 365 進階威脅防護計劃 2，及這包括威脅調查及回應功能。</span><span class="sxs-lookup"><span data-stu-id="1f62e-119">**If your organization previously had Office 365 Threat Intelligence (but not Office 365 Advanced Threat Protection) as an add-on** to another Office 365 subscription, then you will now have Office 365 Advanced Threat Protection Plan 2, and this includes threat investigation and response capabilities.</span></span> 

- <span data-ttu-id="1f62e-120">**如果您的組織已有 Office 365 進階威脅防護 （但不是 Office 365 威脅情報） 當作附加元件**以另一個的 Office 365 訂閱，然後現在有 Office 365 進階威脅防護計劃 1。</span><span class="sxs-lookup"><span data-stu-id="1f62e-120">**If your organization previously had Office 365 Advanced Threat Protection (but not Office 365 Threat Intelligence) as an add-on** to another Office 365 subscription, then you will now have Office 365 Advanced Threat Protection Plan 1.</span></span> <span data-ttu-id="1f62e-121">這包括 Office 365 進階威脅防護方案 1，（但不是威脅分析調查及回應功能）。</span><span class="sxs-lookup"><span data-stu-id="1f62e-121">This includes Office 365 Advanced Threat Protection Plan 1, (but not threat investigation and response capabilities).</span></span>

<span data-ttu-id="1f62e-122">如需詳細資訊，請參閱[Office 365 進階威脅防護方案和價格](https://products.office.com/exchange/advance-threat-protection)與[Office 365 進階威脅防護服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)</span><span class="sxs-lookup"><span data-stu-id="1f62e-122">For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)</span></span>

## <a name="get-started-with-threat-investigation-and-response-capabilities"></a><span data-ttu-id="1f62e-123">威脅調查及回應功能快速入門</span><span class="sxs-lookup"><span data-stu-id="1f62e-123">Get started with threat investigation and response capabilities</span></span>

<span data-ttu-id="1f62e-124">若要深入了解威脅調查及回應功能，在 Office 365，以及如何使用它來保留組織中的人員更安全，請使用下列資源。</span><span class="sxs-lookup"><span data-stu-id="1f62e-124">Use the following resources to learn more about threat investigation and response capabilities in Office 365, and how you can use it to keep people in your organization safer.</span></span>
  
- <span data-ttu-id="1f62e-125">[開始使用威脅調查及回應](get-started-with-ti.md)（這包括必要的角色的相關資訊）</span><span class="sxs-lookup"><span data-stu-id="1f62e-125">[Get started with Threat Investigation and Response](get-started-with-ti.md) (this includes information about required roles)</span></span> 
    
- [<span data-ttu-id="1f62e-126">了解威脅追蹤器-新增和值得注意</span><span class="sxs-lookup"><span data-stu-id="1f62e-126">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)

- [<span data-ttu-id="1f62e-127">自動化的調查及回應 （空調） 與 Office 365 威脅情報</span><span class="sxs-lookup"><span data-stu-id="1f62e-127">Automated Investigation and Response (AIR) with Office 365 Threat Intelligence</span></span>](automated-investigation-response-office.md)

- [<span data-ttu-id="1f62e-128">使用中的安全性威脅總管&amp;合規性中心</span><span class="sxs-lookup"><span data-stu-id="1f62e-128">Use Threat Explorer in the Security &amp; Compliance Center</span></span>](use-explorer-in-security-and-compliance.md)
    
- [<span data-ttu-id="1f62e-129">尋找並調查傳送的惡意電子郵件</span><span class="sxs-lookup"><span data-stu-id="1f62e-129">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
    
- [<span data-ttu-id="1f62e-130">使用攻擊模擬器</span><span class="sxs-lookup"><span data-stu-id="1f62e-130">Use Attack Simulator</span></span>](attack-simulator.md)
    
- [<span data-ttu-id="1f62e-131">整合 Windows Defender 進階威脅防護的威脅調查及回應</span><span class="sxs-lookup"><span data-stu-id="1f62e-131">Integrate Threat Investigation and Response with Windows Defender Advanced Threat Protection</span></span>](integrate-office-365-ti-with-wdatp.md)
    
## <a name="related-topics"></a><span data-ttu-id="1f62e-132">相關主題</span><span class="sxs-lookup"><span data-stu-id="1f62e-132">Related topics</span></span>

[<span data-ttu-id="1f62e-133">威脅總管檢視</span><span class="sxs-lookup"><span data-stu-id="1f62e-133">Threat Explorer views</span></span>](threat-explorer-views.md)

[<span data-ttu-id="1f62e-134">防範 Office 365 中的威脅</span><span class="sxs-lookup"><span data-stu-id="1f62e-134">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="1f62e-135">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="1f62e-135">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="1f62e-136">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="1f62e-136">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
 
