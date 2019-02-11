---
title: 推出 Office 365 雲端 App 安全性後的使用活動
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/28/2019
ms.audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 86f414ad-81de-4703-b40a-c6615bbe9108
description: 您已設定好並導 Office 365 雲端應用程式安全性之後，您將要先執行某些工作，請確定您的設定正確且您準備就緒定期檢閱 （英文）。
ms.openlocfilehash: 71b6793f2e325fcba3431ba5157640b29814ad30
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2019
ms.locfileid: "29603704"
---
# <a name="utilization-activities-after-rolling-out-office-365-cloud-app-security"></a><span data-ttu-id="1995b-103">推出 Office 365 雲端 App 安全性後的使用活動</span><span class="sxs-lookup"><span data-stu-id="1995b-103">Utilization activities after rolling out Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="1995b-104">評估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="1995b-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="1995b-105">規劃 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="1995b-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="1995b-106">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="1995b-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="1995b-107">使用率 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="1995b-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="1995b-108">啟動評估</span><span class="sxs-lookup"><span data-stu-id="1995b-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="1995b-109">開始規劃</span><span class="sxs-lookup"><span data-stu-id="1995b-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="1995b-110">開始部署</span><span class="sxs-lookup"><span data-stu-id="1995b-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="1995b-111">您在此處 ！</span><span class="sxs-lookup"><span data-stu-id="1995b-111">You are here!</span></span>  <br/> [<span data-ttu-id="1995b-112">下一步</span><span class="sxs-lookup"><span data-stu-id="1995b-112">Next step</span></span>](review-office-365-cas-alerts.md) <br/> |
   
> [!NOTE]
> <span data-ttu-id="1995b-p101">在 Office 365 企業版 E5 中使用 office 365 雲端應用程式安全性。如果貴組織要使用另一個 Office 365 企業版訂閱，可做為附加元件購買 Office 365 雲端應用程式安全性。(全域管理員在 Office 365 系統管理中心中，選擇 [**計費** \> **新增訂閱**。)如需詳細資訊，請參閱[Office 365 平台服務說明： Office 365 安全性&amp;規範中心](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)和[購買或編輯企業版的 Office 365 的附加元件](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6)。</span><span class="sxs-lookup"><span data-stu-id="1995b-p101">Office 365 Cloud App Security is available in Office 365 Enterprise E5. If your organization is using another Office 365 Enterprise subscription, Office 365 Cloud App Security can be purchased as an add-on. (As a global administrator, in the Office 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) and [Buy or edit an add-on for Office 365 for business](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span></span> 
  
<span data-ttu-id="1995b-116">您已設定好並設定 Office 365 雲端應用程式安全性之後，您將要執行特定使用率工作做為 Office 365 全域管理員或組織的安全性管理員。</span><span class="sxs-lookup"><span data-stu-id="1995b-116">After you have set up and configured Office 365 Cloud App Security, you'll want to perform certain utilization tasks as an Office 365 global administrator or security administrator for your organization.</span></span> 

<span data-ttu-id="1995b-p102">執行這些工作，您將會協助確保已正確設定 Office 365 雲端應用程式安全性、 原則是最新以及組織實現來自 Office 365 的值。使用本文做指南可協助您規劃這些工作。</span><span class="sxs-lookup"><span data-stu-id="1995b-p102">By performing these tasks, you'll help ensure that Office 365 Cloud App Security is configured correctly, your policies are up to date, and your organization realizes value from Office 365. Use this article as a guide to help you plan for these tasks.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1995b-p103">您必須是全域管理員或安全性管理員可執行本文所述的工作。若要深入了解，請參閱[Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="1995b-p103">You must be a global administrator or security administrator to perform the tasks described in this article. To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
    
## <a name="activities-after-the-initial-configuration-and-rollout-of-office-365-cloud-app-security"></a><span data-ttu-id="1995b-121">初始設定資料庫和 Office 365 雲端應用程式安全性導入後的活動</span><span class="sxs-lookup"><span data-stu-id="1995b-121">Activities after the initial configuration and rollout of Office 365 Cloud App Security</span></span>

<span data-ttu-id="1995b-122">設定 Office 365 雲端應用程式安全性且導，以全域管理員或安全性管理員之後必須考慮一些事項：</span><span class="sxs-lookup"><span data-stu-id="1995b-122">After Office 365 Cloud App Security is configured and rolled out, as a global administrator or security administrators, you have several things to consider:</span></span>
  
- <span data-ttu-id="1995b-123">工作需要新增至 IT 部門行事曆？</span><span class="sxs-lookup"><span data-stu-id="1995b-123">What tasks need to be added to the IT department calendar?</span></span>
    
- <span data-ttu-id="1995b-124">您如何確定 Office 365 雲端應用程式安全性設定成使用一段時間的正確設定的原則？</span><span class="sxs-lookup"><span data-stu-id="1995b-124">How can you make sure Office 365 Cloud App Security is configured to use the right set of policies over time?</span></span>
    
- <span data-ttu-id="1995b-125">您應設定 IT 管理鏈結傳送何種摘要資訊？</span><span class="sxs-lookup"><span data-stu-id="1995b-125">What kinds of summary information should you send up the IT management chain?</span></span>
    
<span data-ttu-id="1995b-126">下表簡短摘要的進行中您要執行的工作和定期您應該考慮將新增至您的 IT 部門行事曆的工作。</span><span class="sxs-lookup"><span data-stu-id="1995b-126">The following table briefly summarizes the ongoing tasks you'll want to perform and periodic tasks you should consider adding to your IT department's calendar.</span></span>
  
|<span data-ttu-id="1995b-127">**進行中的工作**</span><span class="sxs-lookup"><span data-stu-id="1995b-127">**Ongoing tasks**</span></span>|<span data-ttu-id="1995b-128">**定期工作**</span><span class="sxs-lookup"><span data-stu-id="1995b-128">**Periodic tasks**</span></span>|
|:-----|:-----|
| <span data-ttu-id="1995b-129">監視您所要傳送提醒訊息的電子郵件帳戶</span><span class="sxs-lookup"><span data-stu-id="1995b-129">Monitor the email accounts to which you are sending alert messages</span></span>  <br/>  <span data-ttu-id="1995b-130">如需新電腦攻擊最新資訊監視器產業 cybersecurity 新聞摘要</span><span class="sxs-lookup"><span data-stu-id="1995b-130">Monitor industry cybersecurity news feeds for the latest information about new cyber attacks</span></span>  <br/>  <span data-ttu-id="1995b-131">對安全性警訊識別及解決安全性事件及風險</span><span class="sxs-lookup"><span data-stu-id="1995b-131">Act on security alerts to identify and address security incidents and risks</span></span>  <br/>  <span data-ttu-id="1995b-132">摘要說明每個安全性事件和集中的記錄檔中的解決方法</span><span class="sxs-lookup"><span data-stu-id="1995b-132">Summarize each security incident and resolution in a central log</span></span>  <br/> | <span data-ttu-id="1995b-133">執行的特別色異常的 Office 365 雲端應用程式安全性提醒的每月或每季檢閱和分析趨勢</span><span class="sxs-lookup"><span data-stu-id="1995b-133">Perform monthly or quarterly reviews of Office 365 Cloud App Security alerts to spot anomalies and analyze trends</span></span>  <br/>  <span data-ttu-id="1995b-134">執行每月或每季審核的您現有的 Office 365 雲端應用程式安全性原則来包含在 Office 365 雲端應用程式安全性和地址的新 cyberattacks 和趨勢 cybersecurity 的增強功能</span><span class="sxs-lookup"><span data-stu-id="1995b-134">Perform monthly or quarterly reviews of your existing Office 365 Cloud App Security policies to include enhancements in Office 365 Cloud App Security and address new cyberattacks and trends in cybersecurity</span></span>  <br/> |
   
<span data-ttu-id="1995b-135">根據您的組織大小及監視和維護安全性成長感興趣，您可以針對包含您 IT 管理鏈結編譯每月摘要：</span><span class="sxs-lookup"><span data-stu-id="1995b-135">Depending on your organization's size and interest in monitoring and maintaining a security stature, you can compile a monthly summary for your IT management chain that includes:</span></span>
  
- <span data-ttu-id="1995b-136">不同類型的識別與 Office 365 雲端應用程式安全性的安全性事件</span><span class="sxs-lookup"><span data-stu-id="1995b-136">The different types of security incidents identified with Office 365 Cloud App Security</span></span>
    
- <span data-ttu-id="1995b-137">從集中的記錄的安全性事件，例如偵測到的事件數的摘要資訊</span><span class="sxs-lookup"><span data-stu-id="1995b-137">Summary information from your central log of the security incidents, such as number of incidents detected</span></span>
    
- <span data-ttu-id="1995b-138">警示趨勢和所定址的方式</span><span class="sxs-lookup"><span data-stu-id="1995b-138">Alert trends and how they were addressed</span></span>
    
- <span data-ttu-id="1995b-139">最新的 cybersecurity 趨勢</span><span class="sxs-lookup"><span data-stu-id="1995b-139">The latest cybersecurity trends</span></span>
    
- <span data-ttu-id="1995b-140">Office 365 雲端應用程式安全性原則的變更與使用者對其影響的建議</span><span class="sxs-lookup"><span data-stu-id="1995b-140">Recommendations for Office 365 Cloud App Security policy changes and their impact on end users</span></span>
    
## <a name="activities-after-time-has-passed-since-rolling-out-office-365-cloud-app-security"></a><span data-ttu-id="1995b-141">自啟用 Office 365 雲端應用程式安全性時間之後的活動</span><span class="sxs-lookup"><span data-stu-id="1995b-141">Activities after time has passed since rolling out Office 365 Cloud App Security</span></span>

<span data-ttu-id="1995b-142">如果由於您一開始設定或維護您的 Office 365 雲端應用程式安全性原則通過時間的時間的量，執行下列步驟來得到以反映貴組織的安全性目標與目前的功能的設定Office 365 雲端應用程式安全性：</span><span class="sxs-lookup"><span data-stu-id="1995b-142">If a protracted amount of time has passed since you initially configured or maintained your Office 365 Cloud App Security policies, take the following steps to get back to a configuration that reflects your organization's security goals and the current capabilities of Office 365 Cloud App Security:</span></span>
  
1. <span data-ttu-id="1995b-143">判斷 Office 365 雲端應用程式安全性的最後一個組態變更的日期。</span><span class="sxs-lookup"><span data-stu-id="1995b-143">Determine the date of the last configuration change for Office 365 Cloud App Security.</span></span>
    
2. <span data-ttu-id="1995b-p104">了解您目前的 Office 365 雲端應用程式安全性設定並視需要調整這些原則。例如，請確定您知道通知寄往何處透過電子郵件。</span><span class="sxs-lookup"><span data-stu-id="1995b-p104">Understand your current Office 365 Cloud App Security configuration and adjust those policies as needed. For example, make sure you know where alerts are being sent via email.</span></span>
    
3. <span data-ttu-id="1995b-146">請參閱[Office 365 雲端應用程式安全性的新功能](new-in-office-365-cas.md)的產品變更自從上次設定 Office 365 雲端應用程式安全性。</span><span class="sxs-lookup"><span data-stu-id="1995b-146">See [what's new in Office 365 Cloud App Security](new-in-office-365-cas.md) for product changes since you last configured Office 365 Cloud App Security.</span></span> 
    
4. <span data-ttu-id="1995b-147">執行 Office 365 雲端應用程式安全性警告和記錄檔放到特別色異常的分析及分析的趨勢。</span><span class="sxs-lookup"><span data-stu-id="1995b-147">Perform an analysis of Office 365 Cloud App Security alerts and logs to spot anomalies and analyze trends.</span></span>
    
5. <span data-ttu-id="1995b-148">檢查產業 cybersecurity 趨勢成為注意的最新的安全性威脅。</span><span class="sxs-lookup"><span data-stu-id="1995b-148">Check industry cybersecurity trends to become aware of the latest security threats.</span></span>
    
6. <span data-ttu-id="1995b-p105">執行分析對目前設定的 Office 365 雲端應用程式安全性原則需要的變更。加入 Office 365 雲端應用程式安全性功能的變更、 目前的異常和 cybersecurity 趨勢。建議變更現有原則或建立新的原則。</span><span class="sxs-lookup"><span data-stu-id="1995b-p105">Perform an analysis of the changes that need to be made to the current set of Office 365 Cloud App Security policies. Incorporate Office 365 Cloud App Security feature changes, current anomalies, and cybersecurity trends. Recommend changes to existing policies or the creation of new policies.</span></span>
    
7. <span data-ttu-id="1995b-p106">進行的計劃實作原則的變更。通訊 (socialize) 與您的使用者所需的建議變更的後果。</span><span class="sxs-lookup"><span data-stu-id="1995b-p106">Make a plan for implementing the policy changes. Communicate (socialize) the consequences of the proposed changes with your end users as needed.</span></span>
    
8. <span data-ttu-id="1995b-154">實作的 Office 365 雲端應用程式安全性原則變更。</span><span class="sxs-lookup"><span data-stu-id="1995b-154">Implement the Office 365 Cloud App Security policy changes.</span></span>
    
9. <span data-ttu-id="1995b-155">監視使用者意見與 Office 365 雲端應用程式安全性提醒及一段時間調整原則。</span><span class="sxs-lookup"><span data-stu-id="1995b-155">Monitor end user feedback and Office 365 Cloud App Security alerts and adjust policies over time.</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="1995b-156">後續步驟</span><span class="sxs-lookup"><span data-stu-id="1995b-156">Next steps</span></span>

- [<span data-ttu-id="1995b-157">調查活動</span><span class="sxs-lookup"><span data-stu-id="1995b-157">Investigate an activity</span></span>](investigate-an-activity-in-office-365-cas.md)
    
- [<span data-ttu-id="1995b-158">擱置或還原使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="1995b-158">Suspend or restore a user account</span></span>](suspend-or-restore-an-account-in-ocas.md)
    
- [<span data-ttu-id="1995b-159">管理 OAuth 應用程式</span><span class="sxs-lookup"><span data-stu-id="1995b-159">Manage OAuth apps</span></span>](manage-app-permissions-in-ocas.md)
    
- [<span data-ttu-id="1995b-160">檢閱 Office 365 雲端 App 安全性中的 App 探索結果</span><span class="sxs-lookup"><span data-stu-id="1995b-160">Review app discovery findings in Office 365 Cloud App Security</span></span>](review-app-discovery-findings-in-ocas.md)
    
- <span data-ttu-id="1995b-161">檢視支援的[網頁流量記錄檔與資料來源](web-traffic-logs-and-data-sources-for-ocas.md)的清單</span><span class="sxs-lookup"><span data-stu-id="1995b-161">View a list of supported [Web traffic logs and data sources](web-traffic-logs-and-data-sources-for-ocas.md)</span></span>
    

