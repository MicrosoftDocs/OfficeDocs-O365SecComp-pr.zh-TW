---
title: Office 365 雲端 App 安全性中的活動原則和警訊
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/26/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 367f25d3-10a0-4a91-bdae-70ebb7a79c98
description: 定義活動原則與 Office 365 雲端應用程式的安全性設定以特定活動發生或太常發生時觸發提醒。藉由設定原則以觸發提醒，您可通知及監視特定的活動。
ms.openlocfilehash: a239e2bf453a01bf852a702a66cb2f09c02b8c96
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272368"
---
# <a name="activity-policies-and-alerts-in-office-365-cloud-app-security"></a><span data-ttu-id="0068d-104">Office 365 雲端 App 安全性中的活動原則和警訊</span><span class="sxs-lookup"><span data-stu-id="0068d-104">Activity policies and alerts in Office 365 Cloud App Security</span></span>

<span data-ttu-id="0068d-105">Office 365 進階安全性管理現在是 Office 365 雲端應用程式安全性。</span><span class="sxs-lookup"><span data-stu-id="0068d-105">Office 365 Advanced Security Management is now Office 365 Cloud App Security.</span></span>
  
|<span data-ttu-id="0068d-106">評估 * *\>**</span><span class="sxs-lookup"><span data-stu-id="0068d-106">****Evaluation** \>**</span></span>|<span data-ttu-id="0068d-107">規劃 * *\>**</span><span class="sxs-lookup"><span data-stu-id="0068d-107">****Planning** \>**</span></span>|<span data-ttu-id="0068d-108">部署 * *\>**</span><span class="sxs-lookup"><span data-stu-id="0068d-108">****Deployment** \>**</span></span>|<span data-ttu-id="0068d-109">使用率 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="0068d-109">****Utilization****</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="0068d-110">啟動評估</span><span class="sxs-lookup"><span data-stu-id="0068d-110">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="0068d-111">開始規劃</span><span class="sxs-lookup"><span data-stu-id="0068d-111">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="0068d-112">您在此處 ！</span><span class="sxs-lookup"><span data-stu-id="0068d-112">You are here!</span></span>  <br/> [<span data-ttu-id="0068d-113">下一步</span><span class="sxs-lookup"><span data-stu-id="0068d-113">Next step</span></span>](anomaly-detection-policies-in-ocas.md) <br/> |[<span data-ttu-id="0068d-114">開始使用</span><span class="sxs-lookup"><span data-stu-id="0068d-114">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
<span data-ttu-id="0068d-p102">與 Office 365 雲端應用程式安全性] 進階的雲端管理的原則會觸發發生或太常發生特定活動的提醒。例如，假設使用者嘗試登入 Office 365 和一分鐘內 70 時間會失敗。假設另一位使用者下載 7000 檔案，或出現在進行登入加拿大，當使用者應該要放在另一個位置。或糟的是，假設已遭洩露某個人的帳戶，而且攻擊者使用該帳戶存取您的組織的雲端應用程式和機密資料。</span><span class="sxs-lookup"><span data-stu-id="0068d-p102">With Office 365 Cloud App Security, advanced cloud management policies trigger alerts for specific activities that happen or happen too frequently. For example, suppose a user tries to sign in to Office 365 and fails 70 times in one minute. Suppose that another user downloads 7,000 files, or appears to be signed in from Canada, when that user is supposed to be in another location. Or worse, suppose that someone's account has been compromised, and an attacker is using that account to access your organization's cloud apps and sensitive data.</span></span>
  
<span data-ttu-id="0068d-p103">如果您是在[全域管理員或安全性管理員](permissions-in-the-security-and-compliance-center.md)、 活動提醒通知您時事件 like 這些發生。您可以採取例如直到調查有何擱置的使用者帳戶的特定動作。</span><span class="sxs-lookup"><span data-stu-id="0068d-p103">If you are a [global administrator or security administrator](permissions-in-the-security-and-compliance-center.md), activity alerts notify you when events like these occur. You can then take specific actions, such as suspending a user account until you can investigate what happened.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0068d-p104">Office 365 雲端應用程式安全性原則是不同[警示 Office 365 安全性原則&amp;規範中心](alert-policies.md)。活動本文所述的原則在 Office 365 雲端應用程式安全性入口網站中所定義及可協助您更有效管理組織的雲端環境。</span><span class="sxs-lookup"><span data-stu-id="0068d-p104">Office 365 Cloud App Security policies are different from [alert policies in the Office 365 Security &amp; Compliance Center](alert-policies.md). The activity policies described in this article are defined in the Office 365 Cloud App Security portal, and can help you better manage your organization's cloud environment.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="0068d-123">開始之前</span><span class="sxs-lookup"><span data-stu-id="0068d-123">Before you begin</span></span>

<span data-ttu-id="0068d-124">請確定：</span><span class="sxs-lookup"><span data-stu-id="0068d-124">Make sure that:</span></span>
  
- <span data-ttu-id="0068d-125">您的組織具有[Office 365 雲端應用程式安全性](office-365-cas-overview.md)] 和服務已[開啟](turn-on-office-365-cas.md)。</span><span class="sxs-lookup"><span data-stu-id="0068d-125">Your organization has [Office 365 Cloud App Security](office-365-cas-overview.md), and the service is [turned on](turn-on-office-365-cas.md).</span></span>
    
- <span data-ttu-id="0068d-126">[稽核記錄](turn-audit-log-search-on-or-off.md)已開啟的 Office 365 環境。</span><span class="sxs-lookup"><span data-stu-id="0068d-126">[Audit logging](turn-audit-log-search-on-or-off.md) is turned on for your Office 365 environment.</span></span> 
    
- <span data-ttu-id="0068d-127">您已為全域管理員或 Office 365 的安全性管理員。</span><span class="sxs-lookup"><span data-stu-id="0068d-127">You are a global administrator or security administrator for Office 365.</span></span>
    
## <a name="create-a-new-activity-policy"></a><span data-ttu-id="0068d-128">建立新的活動原則</span><span class="sxs-lookup"><span data-stu-id="0068d-128">Create a new activity policy</span></span>

1. <span data-ttu-id="0068d-129">以全域管理員或安全性管理員中，移至[https://protection.office.com](https://protection.office.com)並使用您工作或學校的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="0068d-129">As a global administrator or security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account.</span></span> 
    
2. <span data-ttu-id="0068d-130">安全性&amp;規範中心選擇**提醒** \> **管理進階提醒**。</span><span class="sxs-lookup"><span data-stu-id="0068d-130">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="0068d-131">選擇 [**移至 Office 365 的雲端應用程式安全性**]。</span><span class="sxs-lookup"><span data-stu-id="0068d-131">Choose **Go to Office 365 Cloud App Security**.</span></span>
    
    <span data-ttu-id="0068d-132">這會帶您至 [Office 365 雲端應用程式的安全性原則] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="0068d-132">This takes you to the Office 365 Cloud App Security Policies page.</span></span>
    
    ![當您移至 Office 365 雲端應用程式安全性入口網站時，啟動 [原則] 頁面上](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)
  
4. <span data-ttu-id="0068d-134">按一下 [**建立原則**]，然後選取 [**活動原則**。</span><span class="sxs-lookup"><span data-stu-id="0068d-134">Click **Create policy**, and then select **Activity policy**.</span></span>
    
    ![當您建立原則 O365 CAS 中時，您可以選擇活動原則與異常偵測原則之間。](media/79f34535-ddf9-4a5b-a0a3-8766bf9c174c.png)
  
5. <span data-ttu-id="0068d-p105">在 [**建立活動原則**] 頁面上指定**原則名稱**和**描述**。若要根據預設範本您的原則，選擇 [**原則範本**] 清單中的其中一種或不使用範本建立您自己的原則。</span><span class="sxs-lookup"><span data-stu-id="0068d-p105">On the **Create activity policy** page, specify the **Policy name** and **Description**. To base your policy on a default template, choose one in the **Policy template** list, or create your own policy without using a template.</span></span> 
    
    ![您可以建立活動原則與 Office 365 雲端應用程式安全性。](media/4083a76f-7074-4d6a-8200-6d76d49259d7.png)
  
6. <span data-ttu-id="0068d-p106">選擇 [**原則嚴重性**（Low、 Medium 或 High） 的措施如何嚴重很您如果此原則會觸發提醒。這可協助您篩選提醒時要檢閱其更新版本。</span><span class="sxs-lookup"><span data-stu-id="0068d-p106">Choose a **Policy severity** (Low, Medium, or High) that measures how serious it is to you if this policy triggers an alert. This will help you filter alerts when you're reviewing them later.</span></span> 
    
7. <span data-ttu-id="0068d-p107">選擇此原則的**類別**。這可協助您篩選和排序已觸發提醒或群組原則您要檢閱其進行變更時。</span><span class="sxs-lookup"><span data-stu-id="0068d-p107">Choose a **Category** for this policy. This will help you filter and sort alerts that have been triggered, or to group policies when you're reviewing them to make changes.</span></span> 
    
8. <span data-ttu-id="0068d-143">若要設定其他動作或會觸發此原則為基礎的提醒的評量選擇**活動篩選器**。</span><span class="sxs-lookup"><span data-stu-id="0068d-143">Choose **Activity filters** to set up other actions or metrics that will trigger an alert based on this policy.</span></span> 
    
9. <span data-ttu-id="0068d-144">在 [**活動符合參數**，指定是否原則違規會在單一活動符合篩選器] 時才會觸發或指定的數目的重複活動才之前警示的觸發程序。</span><span class="sxs-lookup"><span data-stu-id="0068d-144">Under **Activity match parameters**, specify whether a policy violation will be triggered when a single activity matches the filters, or if a specified number of repeated activities is required before the alert triggers.</span></span>
    
    <span data-ttu-id="0068d-145">如果您選取 [**重複活動**，指定的時間圖文框的活動和是否違規會計算的特定應用程式內的使用者或任何應用程式的同一個使用者。</span><span class="sxs-lookup"><span data-stu-id="0068d-145">If you select **Repeated activity**, specify the number of activities, the time frame, and whether a violation will count for a user within a specific app or for the same user with any app.</span></span>
    
10. <span data-ttu-id="0068d-146">（選用） 您可以選取**建立通知**以建立其他的提醒從 （透過電子郵件、 文字訊息或兩者） 此原則會收到通知。</span><span class="sxs-lookup"><span data-stu-id="0068d-146">Optionally, you can select **Create alert** to create additional alerts to receive notifications from this policy (via email, text message, or both).</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="0068d-147">請確定您的電子郵件供應商不會封鎖從 no-reply@cloudappsecurity.com 傳送的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="0068d-147">Make sure that your email provider doesn't block emails sent from no-reply@cloudappsecurity.com.</span></span> 
  
11. <span data-ttu-id="0068d-148">選擇 [暫停使用者或需要一次登入 Office 365 應用程式的使用者就會觸發提醒時應採取的**動作**。</span><span class="sxs-lookup"><span data-stu-id="0068d-148">Choose the **Actions** that should be taken when an alert is triggered to suspend the user or require the user to sign in again to Office 365 apps.</span></span> 
    
12. <span data-ttu-id="0068d-149">選擇 [**建立**] 完成建立您的原則。</span><span class="sxs-lookup"><span data-stu-id="0068d-149">Choose **Create** to finish creating your policy.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="0068d-150">後續步驟</span><span class="sxs-lookup"><span data-stu-id="0068d-150">Next steps</span></span>
<span data-ttu-id="0068d-151"><a name="nextsteps"> </a></span><span class="sxs-lookup"><span data-stu-id="0068d-151"></span></span>

- [<span data-ttu-id="0068d-152">異常偵測原則</span><span class="sxs-lookup"><span data-stu-id="0068d-152">Anomaly detection policies</span></span>](anomaly-detection-policies-in-ocas.md)
    
- [<span data-ttu-id="0068d-153">整合 SIEM server</span><span class="sxs-lookup"><span data-stu-id="0068d-153">Integrate your SIEM server</span></span>](integrate-your-siem-server-with-office-365-cas.md)
    
- [<span data-ttu-id="0068d-154">檢閱並採取行動提醒</span><span class="sxs-lookup"><span data-stu-id="0068d-154">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="0068d-155">群組簡化管理 IP 位址</span><span class="sxs-lookup"><span data-stu-id="0068d-155">Group your IP addresses to simplify management</span></span>](group-your-ip-addresses-in-ocas.md)
    

