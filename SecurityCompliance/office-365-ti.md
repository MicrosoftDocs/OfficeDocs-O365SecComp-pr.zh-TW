---
title: Office 365 威脅調查及回應
ms.author: deniseb
author: denisebmsft
manager: laurawi
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
description: 瞭解 Office 365 中的威脅情報功能如何協助您研究組織的威脅、回應惡意程式碼、網路釣魚和其他 Office 365 已偵測到的攻擊, 以及搜尋威脅指標.
ms.openlocfilehash: c8b0815368e80151f8ee55161b9bcbaa98065228
ms.sourcegitcommit: b9d8a43cb3afcdc8820bc9470c5707eff8fc6616
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/11/2019
ms.locfileid: "34852807"
---
# <a name="office-365-threat-investigation-and-response"></a><span data-ttu-id="61580-103">Office 365 威脅調查及回應</span><span class="sxs-lookup"><span data-stu-id="61580-103">Office 365 threat investigation and response</span></span>

<span data-ttu-id="61580-104">Office 365 中的威脅調查和回應功能 [ [Advanced 威脅防護](office-365-atp.md)] 可協助安全性分析師和系統管理員以下列方式保護組織的 Office 365 使用者:</span><span class="sxs-lookup"><span data-stu-id="61580-104">Threat investigation and response capabilities in [Office 365 Advanced Threat Protection](office-365-atp.md) help security analysts and administrators protect their organization's Office 365 users by:</span></span>
  
1. <span data-ttu-id="61580-105">方便您識別、監視和瞭解攻擊</span><span class="sxs-lookup"><span data-stu-id="61580-105">Making it easy to identify, monitor and understand attacks</span></span>
    
2. <span data-ttu-id="61580-106">協助快速解決 Exchange Online、SharePoint Online、商務用 OneDrive 和 Microsoft 團隊中的威脅</span><span class="sxs-lookup"><span data-stu-id="61580-106">Helping to quickly address threats in Exchange Online, SharePoint Online, OneDrive for Business and Microsoft Teams</span></span>
    
3. <span data-ttu-id="61580-107">提供真知灼見和知識以協助防止對其組織的攻擊</span><span class="sxs-lookup"><span data-stu-id="61580-107">Providing insights and knowledge to help prevent attacks against their organization</span></span>

4. <span data-ttu-id="61580-108">針對重要的電子郵件威脅進行自動化調查和回應</span><span class="sxs-lookup"><span data-stu-id="61580-108">Automated investigation and response for critical email based threats</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="61580-109">**Office 365 Advanced 威脅防護和威脅調查與回應 (先前稱為 office 365 威脅情報) 現在是 office 365 高級威脅防護方案 2**, 以及中所含的額外威脅防護功能。某些訂閱, 例如[microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise/home)、 [microsoft 365 商務](https://www.microsoft.com/microsoft-365/business)版、Office 365 E5、office 365 A5 等等。如果您的組織有不含 Office 365 ATP 的訂閱, 您可能會將 ATP 作為附加元件購買。</span><span class="sxs-lookup"><span data-stu-id="61580-109">**Office 365 Advanced Threat Protection and Threat Investigation and Response (previously known as Office 365 Threat Intelligence) are now Office 365 Advanced Threat Protection Plan 2**, along with additional threat protection capabilities included in in certain subscriptions, such as [Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 E5, Office 365 A5, etc. If your organization has a subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on.</span></span> <span data-ttu-id="61580-110">如需詳細資訊, 請參閱[office 365 高級威脅防護方案和價格](https://products.office.com/exchange/advance-threat-protection), 以及[Office 365 的高級威脅防護服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)。</span><span class="sxs-lookup"><span data-stu-id="61580-110">For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp).</span></span> 
  
## <a name="whats-changing"></a><span data-ttu-id="61580-111">有什麼變更？</span><span class="sxs-lookup"><span data-stu-id="61580-111">What's changing?</span></span>

<span data-ttu-id="61580-112">以前, Office 365 威脅情報包含在訂閱中, 例如 Office 365 E5。</span><span class="sxs-lookup"><span data-stu-id="61580-112">Formerly, Office 365 Threat Intelligence was included in subscriptions, such as Office 365 E5.</span></span> <span data-ttu-id="61580-113">因為威脅調查和回應功能現在是 Office 365 高級威脅防護方案 2 (在 Office 365 E5 中的一部分), 所以這種情況仍然是如此。</span><span class="sxs-lookup"><span data-stu-id="61580-113">This is still the case, as threat investigation and response capabilities are now part of Office 365 Advanced Threat Protection Plan 2 (and this is included in Office 365 E5).</span></span> 

<span data-ttu-id="61580-114">此外, Office 365 威脅情報先前是以 Office 365 for business 客戶的附加元件形式購買。</span><span class="sxs-lookup"><span data-stu-id="61580-114">In addition, Office 365 Threat Intelligence was formerly available for purchase as an add-on for Office 365 for business customers.</span></span> <span data-ttu-id="61580-115">現在, Office 365 Advanced 威脅防護方案2中包含這些功能, 以及 Office 365 高級威脅防護方案1中的所有功能。</span><span class="sxs-lookup"><span data-stu-id="61580-115">Now, these capabilities are included in Office 365 Advanced Threat Protection Plan 2 (along with all the features in Office 365 Advanced Threat Protection Plan 1).</span></span> <span data-ttu-id="61580-116">若要深入瞭解, 請參閱[Office 365 高級威脅防護方案和價格](https://products.office.com/exchange/advance-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="61580-116">To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection).</span></span>

<span data-ttu-id="61580-117">以下是所有這種方法的含義:</span><span class="sxs-lookup"><span data-stu-id="61580-117">Here's what all this means:</span></span>

- <span data-ttu-id="61580-118">**如果您的組織已有 Office 365 E5**, 則您已經有了高級威脅防護計畫 2, 包括威脅調查和回應功能。</span><span class="sxs-lookup"><span data-stu-id="61580-118">**If your organization already has Office 365 E5**, then you already have Advanced Threat Protection Plan 2, and this includes threat investigation and response capabilities.</span></span>

- <span data-ttu-id="61580-119">**如果您的組織先前有 office 365 威脅情報 (但非 office 365 的高級威脅防護) 做**為其他 Office 365 訂閱的附加元件, 則您現在會有 Office 365 Advanced 威脅防護方案 2, 這包括威脅調查和回應功能。</span><span class="sxs-lookup"><span data-stu-id="61580-119">**If your organization previously had Office 365 Threat Intelligence (but not Office 365 Advanced Threat Protection) as an add-on** to another Office 365 subscription, then you will now have Office 365 Advanced Threat Protection Plan 2, and this includes threat investigation and response capabilities.</span></span> 

- <span data-ttu-id="61580-120">**如果您的組織先前有 office 365 高級威脅防護 (但不是 office 365 威脅情報) 做**為其他 Office 365 訂閱的附加元件, 則您現在會有 Office 365 Advanced 威脅防護方案1。</span><span class="sxs-lookup"><span data-stu-id="61580-120">**If your organization previously had Office 365 Advanced Threat Protection (but not Office 365 Threat Intelligence) as an add-on** to another Office 365 subscription, then you will now have Office 365 Advanced Threat Protection Plan 1.</span></span> <span data-ttu-id="61580-121">這包括 Office 365 Advanced 威脅防護方案 1, (但不是威脅調查和回應功能)。</span><span class="sxs-lookup"><span data-stu-id="61580-121">This includes Office 365 Advanced Threat Protection Plan 1, (but not threat investigation and response capabilities).</span></span>

<span data-ttu-id="61580-122">如需詳細資訊, 請參閱[office 365 Advanced 威脅防護方案和價格](https://products.office.com/exchange/advance-threat-protection), 以及[Office 365 的高級威脅防護服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)</span><span class="sxs-lookup"><span data-stu-id="61580-122">For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)</span></span>

## <a name="get-started-with-threat-investigation-and-response-capabilities"></a><span data-ttu-id="61580-123">開始使用威脅調查和回應功能</span><span class="sxs-lookup"><span data-stu-id="61580-123">Get started with threat investigation and response capabilities</span></span>

<span data-ttu-id="61580-124">您可以使用下列資源深入瞭解 Office 365 中的威脅調查和回應功能, 以及如何使用它讓組織中的人員更安全。</span><span class="sxs-lookup"><span data-stu-id="61580-124">Use the following resources to learn more about threat investigation and response capabilities in Office 365, and how you can use it to keep people in your organization safer.</span></span>
  
- <span data-ttu-id="61580-125">[開始使用威脅調查和回應](get-started-with-ti.md)(這包含所需角色的相關資訊)</span><span class="sxs-lookup"><span data-stu-id="61580-125">[Get started with Threat Investigation and Response](get-started-with-ti.md) (this includes information about required roles)</span></span> 
    
- [<span data-ttu-id="61580-126">瞭解威脅追蹤器-新增和值得注意的</span><span class="sxs-lookup"><span data-stu-id="61580-126">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)

- [<span data-ttu-id="61580-127">使用自動化調查和回應 (空中) 功能節省時間和精力</span><span class="sxs-lookup"><span data-stu-id="61580-127">Save time and effort with Automated Investigation and Response (AIR) capabilities</span></span>](automated-investigation-response-office.md)

- [<span data-ttu-id="61580-128">使用威脅瀏覽器 (或即時偵測) 來識別和調查電子郵件和檔案中的惡意內容</span><span class="sxs-lookup"><span data-stu-id="61580-128">Use Threat Explorer (or real-time detections) to identify and investigate malicious content in email and files</span></span>](threat-explorer.md)
    
- [<span data-ttu-id="61580-129">尋找並調查傳送的惡意電子郵件</span><span class="sxs-lookup"><span data-stu-id="61580-129">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
    
- [<span data-ttu-id="61580-130">使用攻擊模擬器來模擬攻擊並增加使用者認知度</span><span class="sxs-lookup"><span data-stu-id="61580-130">Use Attack Simulator to simulate attacks and increase user awareness</span></span>](attack-simulator.md)
    
- [<span data-ttu-id="61580-131">整合威脅調查和回應功能與 Microsoft Defender Advanced 威脅防護</span><span class="sxs-lookup"><span data-stu-id="61580-131">Integrate Threat Investigation and Response capabilities with Microsoft Defender Advanced Threat Protection</span></span>](integrate-office-365-ti-with-wdatp.md)
    
## <a name="related-topics"></a><span data-ttu-id="61580-132">相關主題</span><span class="sxs-lookup"><span data-stu-id="61580-132">Related topics</span></span>

[<span data-ttu-id="61580-133">威脅總管檢視</span><span class="sxs-lookup"><span data-stu-id="61580-133">Threat Explorer views</span></span>](threat-explorer-views.md)

[<span data-ttu-id="61580-134">防止 Office 365 中的威脅</span><span class="sxs-lookup"><span data-stu-id="61580-134">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="61580-135">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="61580-135">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="61580-136">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="61580-136">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
 
