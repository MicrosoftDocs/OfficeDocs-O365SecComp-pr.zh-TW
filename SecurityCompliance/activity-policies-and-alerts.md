---
title: Office 365 雲端 App 安全性中的活動原則和警訊
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/28/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 367f25d3-10a0-4a91-bdae-70ebb7a79c98
description: 定義活動原則與 Office 365 雲端 App 安全性設定提醒，以特定活動，即會發生，或發生次數太頻繁時觸發。 透過設定以觸發提醒的原則，您可以通知，並監視特定活動。
ms.openlocfilehash: cfa58182ea35551ca3a3807c23e09c9f87c7be82
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32242708"
---
# <a name="activity-policies-and-alerts-in-office-365-cloud-app-security"></a><span data-ttu-id="4e55a-104">Office 365 雲端 App 安全性中的活動原則和警訊</span><span class="sxs-lookup"><span data-stu-id="4e55a-104">Activity policies and alerts in Office 365 Cloud App Security</span></span>

|<span data-ttu-id="4e55a-105">評估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="4e55a-105">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="4e55a-106">規劃 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="4e55a-106">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="4e55a-107">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="4e55a-107">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="4e55a-108">使用率 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="4e55a-108">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="4e55a-109">啟動評估</span><span class="sxs-lookup"><span data-stu-id="4e55a-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="4e55a-110">開始規劃</span><span class="sxs-lookup"><span data-stu-id="4e55a-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="4e55a-111">您在此處 ！</span><span class="sxs-lookup"><span data-stu-id="4e55a-111">You are here!</span></span>  <br/> [<span data-ttu-id="4e55a-112">下一步</span><span class="sxs-lookup"><span data-stu-id="4e55a-112">Next step</span></span>](anomaly-detection-policies-in-ocas.md) <br/> |[<span data-ttu-id="4e55a-113">開始使用</span><span class="sxs-lookup"><span data-stu-id="4e55a-113">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
<span data-ttu-id="4e55a-114">使用 Office 365 雲端 App 安全性，進階的雲端管理原則會觸發警示所發生的事件，或發生次數太頻繁的特定活動。</span><span class="sxs-lookup"><span data-stu-id="4e55a-114">With Office 365 Cloud App Security, advanced cloud management policies trigger alerts for specific activities that happen or happen too frequently.</span></span> <span data-ttu-id="4e55a-115">例如，假設使用者嘗試登入 Office 365 和 70 時間中一分鐘失敗。</span><span class="sxs-lookup"><span data-stu-id="4e55a-115">For example, suppose a user tries to sign in to Office 365 and fails 70 times in one minute.</span></span> <span data-ttu-id="4e55a-116">假設另一位使用者下載 7000 檔案，或看起來的身分登入從加拿大，當使用者應該要放在另一個位置。</span><span class="sxs-lookup"><span data-stu-id="4e55a-116">Suppose that another user downloads 7,000 files, or appears to be signed in from Canada, when that user is supposed to be in another location.</span></span> <span data-ttu-id="4e55a-117">或惡化，假設某個人的帳戶已遭洩露，而且攻擊者會使用該帳戶來存取貴組織的雲端應用程式和機密資料。</span><span class="sxs-lookup"><span data-stu-id="4e55a-117">Or worse, suppose that someone's account has been compromised, and an attacker is using that account to access your organization's cloud apps and sensitive data.</span></span>
  
<span data-ttu-id="4e55a-118">如果您是[全域系統管理員或安全性系統管理員](permissions-in-the-security-and-compliance-center.md)，活動警訊會通知您事件 like 這些時就會發生。</span><span class="sxs-lookup"><span data-stu-id="4e55a-118">If you are a [global administrator or security administrator](permissions-in-the-security-and-compliance-center.md), activity alerts notify you when events like these occur.</span></span> <span data-ttu-id="4e55a-119">您接著可以採取特定的動作，例如擱置的使用者帳戶，直到您可以調查發生了什麼事。</span><span class="sxs-lookup"><span data-stu-id="4e55a-119">You can then take specific actions, such as suspending a user account until you can investigate what happened.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4e55a-120">Office 365 雲端 App 安全性原則會不同於[警示中 Office 365 安全性原則&amp;合規性中心](alert-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="4e55a-120">Office 365 Cloud App Security policies are different from [alert policies in the Office 365 Security &amp; Compliance Center](alert-policies.md).</span></span> <span data-ttu-id="4e55a-121">本文所述的原則定義在 Office 365 雲端 App 安全性入口網站中，並可協助您更好的活動管理貴組織的雲端環境。</span><span class="sxs-lookup"><span data-stu-id="4e55a-121">The activity policies described in this article are defined in the Office 365 Cloud App Security portal, and can help you better manage your organization's cloud environment.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="4e55a-122">開始之前</span><span class="sxs-lookup"><span data-stu-id="4e55a-122">Before you begin</span></span>

<span data-ttu-id="4e55a-123">請確定：</span><span class="sxs-lookup"><span data-stu-id="4e55a-123">Make sure that:</span></span>
  
- <span data-ttu-id="4e55a-124">您的組織有[Office 365 雲端 App 安全性](office-365-cas-overview.md)，並服務已[開啟](turn-on-office-365-cas.md)。</span><span class="sxs-lookup"><span data-stu-id="4e55a-124">Your organization has [Office 365 Cloud App Security](office-365-cas-overview.md), and the service is [turned on](turn-on-office-365-cas.md).</span></span>
    
- <span data-ttu-id="4e55a-125">[稽核記錄](turn-audit-log-search-on-or-off.md)已為您的 Office 365 環境。</span><span class="sxs-lookup"><span data-stu-id="4e55a-125">[Audit logging](turn-audit-log-search-on-or-off.md) is turned on for your Office 365 environment.</span></span> 
    
- <span data-ttu-id="4e55a-126">您是全域系統管理員或 Office 365 的安全性系統管理員。</span><span class="sxs-lookup"><span data-stu-id="4e55a-126">You are a global administrator or security administrator for Office 365.</span></span>
    
## <a name="create-a-new-activity-policy"></a><span data-ttu-id="4e55a-127">建立新的活動原則</span><span class="sxs-lookup"><span data-stu-id="4e55a-127">Create a new activity policy</span></span>

1. <span data-ttu-id="4e55a-128">以全域管理員或安全性管理員中，移至 Cloud App Security 入口網站 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com))，並登入。</span><span class="sxs-lookup"><span data-stu-id="4e55a-128">As a global administrator or security administrator, go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span> <br><span data-ttu-id="4e55a-129">這會帶您前往 Office 365 雲端 App 安全性原則] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="4e55a-129">This takes you to the Office 365 Cloud App Security Policies page.</span></span><br><span data-ttu-id="4e55a-130">![當您移至 Office 365 雲端 App 安全性入口網站時，您以啟動 [原則] 頁面](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)</span><span class="sxs-lookup"><span data-stu-id="4e55a-130">![When you go to the Office 365 Cloud App Security portal, you start with the Policies page](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)</span></span>
  
2. <span data-ttu-id="4e55a-131">按一下 [**建立原則**]，然後選取 [**活動原則**。</span><span class="sxs-lookup"><span data-stu-id="4e55a-131">Click **Create policy**, and then select **Activity policy**.</span></span><br><span data-ttu-id="4e55a-132">![當您建立原則 O365 CAS 中時，您可以選擇之間的活動原則和異常偵測原則。](media/79f34535-ddf9-4a5b-a0a3-8766bf9c174c.png)</span><span class="sxs-lookup"><span data-stu-id="4e55a-132">![When you create a policy in O365 CAS, you can choose between Activity policies and Anomaly Detection policies.](media/79f34535-ddf9-4a5b-a0a3-8766bf9c174c.png)</span></span>
  
3. <span data-ttu-id="4e55a-133">在 [**建立活動原則**] 頁面上，指定**原則名稱**與**描述**。</span><span class="sxs-lookup"><span data-stu-id="4e55a-133">On the **Create activity policy** page, specify the **Policy name** and **Description**.</span></span> <span data-ttu-id="4e55a-134">若要依據您的原則的預設範本上，選擇其中一個的**原則範本**] 清單中，或建立您自己的原則，而不使用範本。</span><span class="sxs-lookup"><span data-stu-id="4e55a-134">To base your policy on a default template, choose one in the **Policy template** list, or create your own policy without using a template.</span></span><br><span data-ttu-id="4e55a-135">![您可以使用 Office 365 雲端 App 安全性建立活動原則。](media/4083a76f-7074-4d6a-8200-6d76d49259d7.png)</span><span class="sxs-lookup"><span data-stu-id="4e55a-135">![You can create activity policies with Office 365 Cloud App Security.](media/4083a76f-7074-4d6a-8200-6d76d49259d7.png)</span></span>
  
4. <span data-ttu-id="4e55a-136">選擇 [**原則嚴重性**（低、 中或高） 來測量如何嚴重是您如果此原則會觸發警示。</span><span class="sxs-lookup"><span data-stu-id="4e55a-136">Choose a **Policy severity** (Low, Medium, or High) that measures how serious it is to you if this policy triggers an alert.</span></span> <span data-ttu-id="4e55a-137">這可協助您篩選提醒，當您在稍後檢閱它們。</span><span class="sxs-lookup"><span data-stu-id="4e55a-137">This will help you filter alerts when you're reviewing them later.</span></span> 
    
5. <span data-ttu-id="4e55a-138">選擇**類別**，此原則。</span><span class="sxs-lookup"><span data-stu-id="4e55a-138">Choose a **Category** for this policy.</span></span> <span data-ttu-id="4e55a-139">這可協助您篩選和排序提醒已被觸發，或當您要檢閱這些變更的群組原則。</span><span class="sxs-lookup"><span data-stu-id="4e55a-139">This will help you filter and sort alerts that have been triggered, or to group policies when you're reviewing them to make changes.</span></span> 
    
6. <span data-ttu-id="4e55a-140">若要設定其他動作或就會觸發警示根據此原則的計量，請選擇 [**活動篩選**]。</span><span class="sxs-lookup"><span data-stu-id="4e55a-140">Choose **Activity filters** to set up other actions or metrics that will trigger an alert based on this policy.</span></span> 
    
7. <span data-ttu-id="4e55a-141">在 [**活動符合參數**，指定是否將觸發原則違規情形，當單一活動符合篩選器，或指定的數目的重複的活動，都必須先警示的觸發程序。</span><span class="sxs-lookup"><span data-stu-id="4e55a-141">Under **Activity match parameters**, specify whether a policy violation will be triggered when a single activity matches the filters, or if a specified number of repeated activities is required before the alert triggers.</span></span><br><span data-ttu-id="4e55a-142">如果您選取 [**重複活動**，指定的活動，在時間範圍，以及是否違規會計算特定應用程式內的使用者，或透過任何應用程式相同的使用者。</span><span class="sxs-lookup"><span data-stu-id="4e55a-142">If you select **Repeated activity**, specify the number of activities, the time frame, and whether a violation will count for a user within a specific app or for the same user with any app.</span></span>
    
8. <span data-ttu-id="4e55a-143">或者，您可以選取**建立警示**來建立其他提醒給該原則 （透過電子郵件、 文字訊息，或兩者） 中會收到通知。</span><span class="sxs-lookup"><span data-stu-id="4e55a-143">Optionally, you can select **Create alert** to create additional alerts to receive notifications from this policy (via email, text message, or both).</span></span><br><span data-ttu-id="4e55a-144">**請確定您的電子郵件提供者不會封鎖寄件者的電子郵件`no-reply@cloudappsecurity.com`**。</span><span class="sxs-lookup"><span data-stu-id="4e55a-144">**Make sure that your email provider doesn't block emails sent from `no-reply@cloudappsecurity.com`**.</span></span> 
  
9. <span data-ttu-id="4e55a-145">選擇 [擱置使用者或要求使用者再次登入 Office 365 應用程式就會觸發警示時應採取的**動作**。</span><span class="sxs-lookup"><span data-stu-id="4e55a-145">Choose the **Actions** that should be taken when an alert is triggered to suspend the user or require the user to sign in again to Office 365 apps.</span></span> 
    
10. <span data-ttu-id="4e55a-146">選擇 [**建立**] 以完成建立您的原則。</span><span class="sxs-lookup"><span data-stu-id="4e55a-146">Choose **Create** to finish creating your policy.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="4e55a-147">後續步驟</span><span class="sxs-lookup"><span data-stu-id="4e55a-147">Next steps</span></span>

- [<span data-ttu-id="4e55a-148">異常偵測原則</span><span class="sxs-lookup"><span data-stu-id="4e55a-148">Anomaly detection policies</span></span>](anomaly-detection-policies-in-ocas.md)
    
- [<span data-ttu-id="4e55a-149">將 SIEM 伺服器整合</span><span class="sxs-lookup"><span data-stu-id="4e55a-149">Integrate your SIEM server</span></span>](integrate-your-siem-server-with-office-365-cas.md)
    
- [<span data-ttu-id="4e55a-150">檢閱並採取相應動作提醒</span><span class="sxs-lookup"><span data-stu-id="4e55a-150">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="4e55a-151">您的 IP 位址，以簡化管理群組</span><span class="sxs-lookup"><span data-stu-id="4e55a-151">Group your IP addresses to simplify management</span></span>](group-your-ip-addresses-in-ocas.md)
    

