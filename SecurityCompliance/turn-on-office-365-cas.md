---
title: 開啟 Office 365 雲端 App 安全性
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ba919c73-d021-404d-9850-eec57e78678c
description: 閱讀本篇文章以了解如何在 Office 365 雲端 App 安全性，提供雲端 App 安全性，在 Microsoft Azure 中開啟。
ms.openlocfilehash: 1227545b1e4d1521dc1820342f09aabdf16ec2c6
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32264125"
---
# <a name="turn-on-office-365-cloud-app-security"></a><span data-ttu-id="058e5-103">開啟 Office 365 雲端 App 安全性</span><span class="sxs-lookup"><span data-stu-id="058e5-103">Turn on Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="058e5-104">評估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="058e5-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="058e5-105">規劃 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="058e5-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="058e5-106">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="058e5-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="058e5-107">使用率 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="058e5-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="058e5-108">啟動評估</span><span class="sxs-lookup"><span data-stu-id="058e5-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="058e5-109">開始規劃</span><span class="sxs-lookup"><span data-stu-id="058e5-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="058e5-110">您在此處 ！</span><span class="sxs-lookup"><span data-stu-id="058e5-110">You are here!</span></span>  <br/> [<span data-ttu-id="058e5-111">下一步</span><span class="sxs-lookup"><span data-stu-id="058e5-111">Next step</span></span>](activity-policies-and-alerts.md) <br/> |[<span data-ttu-id="058e5-112">開始使用</span><span class="sxs-lookup"><span data-stu-id="058e5-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
  
## <a name="turn-on-office-365-cloud-app-security"></a><span data-ttu-id="058e5-113">開啟 Office 365 雲端 App 安全性</span><span class="sxs-lookup"><span data-stu-id="058e5-113">Turn on Office 365 Cloud App Security</span></span>

> [!IMPORTANT]
> <span data-ttu-id="058e5-114">您必須是全域系統管理員或安全性系統管理員可執行下列工作。</span><span class="sxs-lookup"><span data-stu-id="058e5-114">You must be a global administrator or security administrator to perform the following task.</span></span> <span data-ttu-id="058e5-115">若要深入了解，請參閱[中 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="058e5-115">To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> <span data-ttu-id="058e5-116">為了讓 Office 365 雲端 App 安全性運作正確，**必須開啟稽核記錄功能**適用於 Office 365 環境。</span><span class="sxs-lookup"><span data-stu-id="058e5-116">In order for Office 365 Cloud App Security to work correct, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="058e5-117">如需詳細資訊，請參閱[開啟 Office 365 稽核記錄搜尋的開啟或關閉](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="058e5-117">For more information, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span> 
  
1. <span data-ttu-id="058e5-118">以全域管理員或安全性管理員中，移至[https://protection.office.com](https://security.microsoft.com)和 Office 365 使用公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="058e5-118">As a global administrator or security administrator, go to [https://protection.office.com](https://security.microsoft.com) and sign in using your work or school account for Office 365.</span></span> <span data-ttu-id="058e5-119">(這會帶您前往安全性&amp;合規性中心。)</span><span class="sxs-lookup"><span data-stu-id="058e5-119">(This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="058e5-120">前往 [**提醒** \> **管理進階提醒**。</span><span class="sxs-lookup"><span data-stu-id="058e5-120">Go to **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="058e5-121">選取 [**開啟 Office 365 雲端 App 安全性**]。</span><span class="sxs-lookup"><span data-stu-id="058e5-121">Select **Turn on Office 365 Cloud App Security**.</span></span>
    
4. <span data-ttu-id="058e5-122">選擇 [**移至 Office 365 雲端 App 安全性**。</span><span class="sxs-lookup"><span data-stu-id="058e5-122">Choose **Go to Office 365 Cloud App Security**.</span></span><br/><span data-ttu-id="058e5-123">![安全性&amp;合規性中心，選擇 [管理進階提醒移至 Office 365 雲端 App 安全性](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span><span class="sxs-lookup"><span data-stu-id="058e5-123">![In the Security &amp; Compliance Center, choose Manage Advanced Alerts to go to Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span></span><br/><span data-ttu-id="058e5-124">這將帶您至 Office 365 雲端 App 安全性入口網站，您可以在其中檢視報表和建立或編輯您的原則。</span><span class="sxs-lookup"><span data-stu-id="058e5-124">This takes you to the Office 365 Cloud App Security portal, where you can view reports and create or edit your policies.</span></span>

<span data-ttu-id="058e5-125">您已開啟 Office 365 雲端 App 安全性後，您可以造訪移至 Cloud App Security 入口網站[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)與登入。</span><span class="sxs-lookup"><span data-stu-id="058e5-125">After you have turned on Office 365 Cloud App Security, you can go to the Cloud App Security portal by visiting [https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com) and signing in.</span></span>
    
> [!NOTE]
> <span data-ttu-id="058e5-126">當您開啟 Office 365 雲端 App 安全性時，您的 Office 365 使用者帳戶和使用者活動的稽核資訊會被轉接至[Microsoft Cloud App Security](https://aka.ms/whatiscas)。</span><span class="sxs-lookup"><span data-stu-id="058e5-126">When you turn on Office 365 Cloud App Security, auditing information about your Office 365 user accounts and user activities is transferred to [Microsoft Cloud App Security](https://aka.ms/whatiscas).</span></span> <span data-ttu-id="058e5-127">這可讓 Office 365 來提供進階的提醒、 篩選和其他功能，因此您可以取得資訊並採取動作的相關可疑活動。</span><span class="sxs-lookup"><span data-stu-id="058e5-127">This allows Office 365 to provide advanced alerts, filtering, and other features so you can get information and take action about suspicious activities.</span></span> 
  
## <a name="next-steps"></a><span data-ttu-id="058e5-128">後續步驟</span><span class="sxs-lookup"><span data-stu-id="058e5-128">Next steps</span></span>

- [<span data-ttu-id="058e5-129">活動原則</span><span class="sxs-lookup"><span data-stu-id="058e5-129">Activity policies</span></span>](activity-policies-and-alerts.md)
    
- [<span data-ttu-id="058e5-130">異常偵測原則</span><span class="sxs-lookup"><span data-stu-id="058e5-130">Anomaly detection policies</span></span>](anomaly-detection-policies-in-ocas.md)
    
- [<span data-ttu-id="058e5-131">將 SIEM 伺服器整合</span><span class="sxs-lookup"><span data-stu-id="058e5-131">Integrate your SIEM server</span></span>](integrate-your-siem-server-with-office-365-cas.md)
    
- [<span data-ttu-id="058e5-132">您的 IP 位址，以簡化管理群組</span><span class="sxs-lookup"><span data-stu-id="058e5-132">Group your IP addresses to simplify management</span></span>](group-your-ip-addresses-in-ocas.md)
    

