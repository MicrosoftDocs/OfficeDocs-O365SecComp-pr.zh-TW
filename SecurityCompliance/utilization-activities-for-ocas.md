---
title: 推出 Office 365 雲端 App 安全性後的使用活動
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/28/2019
ms.audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 86f414ad-81de-4703-b40a-c6615bbe9108
description: 您已設定好並導入 Office 365 雲端 App 安全性後，您會想要執行特定工作，請確定您的組態正確，且您準備就緒定期檢閱。
ms.openlocfilehash: 232de4df1d1eb4debdddcee2c1d8672d1aeb4b21
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2019
ms.locfileid: "30999946"
---
# <a name="utilization-activities-after-rolling-out-office-365-cloud-app-security"></a><span data-ttu-id="e5612-103">推出 Office 365 雲端 App 安全性後的使用活動</span><span class="sxs-lookup"><span data-stu-id="e5612-103">Utilization activities after rolling out Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="e5612-104">評估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="e5612-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="e5612-105">規劃 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="e5612-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="e5612-106">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="e5612-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="e5612-107">使用率 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="e5612-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="e5612-108">啟動評估</span><span class="sxs-lookup"><span data-stu-id="e5612-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="e5612-109">開始規劃</span><span class="sxs-lookup"><span data-stu-id="e5612-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="e5612-110">開始部署</span><span class="sxs-lookup"><span data-stu-id="e5612-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="e5612-111">您在此處 ！</span><span class="sxs-lookup"><span data-stu-id="e5612-111">You are here!</span></span>  <br/> [<span data-ttu-id="e5612-112">下一步</span><span class="sxs-lookup"><span data-stu-id="e5612-112">Next step</span></span>](review-office-365-cas-alerts.md) <br/> |
   
> [!NOTE]
> <span data-ttu-id="e5612-113">Office 365 雲端 App 安全性是在 Office 365 企業版 E5。</span><span class="sxs-lookup"><span data-stu-id="e5612-113">Office 365 Cloud App Security is available in Office 365 Enterprise E5.</span></span> <span data-ttu-id="e5612-114">如果您的組織要使用另一個 Office 365 企業版訂閱，能以附加元件形式購買 Office 365 雲端 App 安全性。</span><span class="sxs-lookup"><span data-stu-id="e5612-114">If your organization is using another Office 365 Enterprise subscription, Office 365 Cloud App Security can be purchased as an add-on.</span></span> <span data-ttu-id="e5612-115">(以全域管理員，在 Microsoft 365 系統管理中心中，選擇 [**計費** \> **新增訂閱**。)如需詳細資訊，請參閱[Office 365 平台服務說明： Office 365 安全性&amp;合規性中心](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)並[購買或編輯商務用 Office 365 的附加元件](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6)。</span><span class="sxs-lookup"><span data-stu-id="e5612-115">(As a global administrator, in the Microsoft 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) and [Buy or edit an add-on for Office 365 for business](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span></span> 
  
<span data-ttu-id="e5612-116">您已安裝並設定為 Office 365 雲端 App 安全性之後，您會想要做為 Office 365 全域系統管理員或組織的安全性管理員執行特定使用率工作。</span><span class="sxs-lookup"><span data-stu-id="e5612-116">After you have set up and configured Office 365 Cloud App Security, you'll want to perform certain utilization tasks as an Office 365 global administrator or security administrator for your organization.</span></span> 

<span data-ttu-id="e5612-117">藉由執行這些工作，您將會協助確定已正確設定 Office 365 雲端 App 安全性、 您的原則是最新狀態，且您的組織實現從 Office 365 的值。</span><span class="sxs-lookup"><span data-stu-id="e5612-117">By performing these tasks, you'll help ensure that Office 365 Cloud App Security is configured correctly, your policies are up to date, and your organization realizes value from Office 365.</span></span> <span data-ttu-id="e5612-118">使用本文做為指南，以協助您規劃這些工作。</span><span class="sxs-lookup"><span data-stu-id="e5612-118">Use this article as a guide to help you plan for these tasks.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e5612-119">您必須是全域系統管理員或安全性系統管理員可執行本文所述的工作。</span><span class="sxs-lookup"><span data-stu-id="e5612-119">You must be a global administrator or security administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="e5612-120">若要深入了解，請參閱[中 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="e5612-120">To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
    
## <a name="activities-after-the-initial-configuration-and-rollout-of-office-365-cloud-app-security"></a><span data-ttu-id="e5612-121">初始設定資料庫和首度發行的 Office 365 雲端 App 安全性後的活動</span><span class="sxs-lookup"><span data-stu-id="e5612-121">Activities after the initial configuration and rollout of Office 365 Cloud App Security</span></span>

<span data-ttu-id="e5612-122">Office 365 雲端 App 安全性過設定，並導入，以全域管理員或安全性系統管理員之後, 您就必須考量的一些事項：</span><span class="sxs-lookup"><span data-stu-id="e5612-122">After Office 365 Cloud App Security is configured and rolled out, as a global administrator or security administrators, you have several things to consider:</span></span>
  
- <span data-ttu-id="e5612-123">工作需要新增至 IT 部門行事曆嗎？</span><span class="sxs-lookup"><span data-stu-id="e5612-123">What tasks need to be added to the IT department calendar?</span></span>
    
- <span data-ttu-id="e5612-124">您將如何確定 Office 365 雲端 App 安全性設定為使用正確的一組原則經過一段時間？</span><span class="sxs-lookup"><span data-stu-id="e5612-124">How can you make sure Office 365 Cloud App Security is configured to use the right set of policies over time?</span></span>
    
- <span data-ttu-id="e5612-125">您應該 IT 管理達到鏈，添加傳送何種摘要資訊？</span><span class="sxs-lookup"><span data-stu-id="e5612-125">What kinds of summary information should you send up the IT management chain?</span></span>
    
<span data-ttu-id="e5612-126">下表摘要說明您會想要執行的進行中工作，您應該考慮將新增至您的 IT 部門的行事曆的定期工作。</span><span class="sxs-lookup"><span data-stu-id="e5612-126">The following table briefly summarizes the ongoing tasks you'll want to perform and periodic tasks you should consider adding to your IT department's calendar.</span></span>
  
|<span data-ttu-id="e5612-127">**進行中的工作**</span><span class="sxs-lookup"><span data-stu-id="e5612-127">**Ongoing tasks**</span></span>|<span data-ttu-id="e5612-128">**定期工作**</span><span class="sxs-lookup"><span data-stu-id="e5612-128">**Periodic tasks**</span></span>|
|:-----|:-----|
| <span data-ttu-id="e5612-129">監視您要傳送提醒訊息的電子郵件帳戶</span><span class="sxs-lookup"><span data-stu-id="e5612-129">Monitor the email accounts to which you are sending alert messages</span></span>  <br/>  <span data-ttu-id="e5612-130">如需關於新的網路攻擊的最新資訊監視器產業 cybersecurity 新聞摘要</span><span class="sxs-lookup"><span data-stu-id="e5612-130">Monitor industry cybersecurity news feeds for the latest information about new cyber attacks</span></span>  <br/>  <span data-ttu-id="e5612-131">對識別和解決安全性事件和風險的安全性警示</span><span class="sxs-lookup"><span data-stu-id="e5612-131">Act on security alerts to identify and address security incidents and risks</span></span>  <br/>  <span data-ttu-id="e5612-132">將摘要說明每個安全性事件和中央的記錄檔中的解決方法</span><span class="sxs-lookup"><span data-stu-id="e5612-132">Summarize each security incident and resolution in a central log</span></span>  <br/> | <span data-ttu-id="e5612-133">執行的特別色異常的 Office 365 雲端 App 安全性提醒的每月或每季檢閱及分析趨勢</span><span class="sxs-lookup"><span data-stu-id="e5612-133">Perform monthly or quarterly reviews of Office 365 Cloud App Security alerts to spot anomalies and analyze trends</span></span>  <br/>  <span data-ttu-id="e5612-134">執行每月或每季檢閱您現有的 Office 365 雲端 App 安全性原則，以在 Office 365 雲端 App 安全性和地址的新網路攻擊和趨勢 cybersecurity 中包含的增強功能</span><span class="sxs-lookup"><span data-stu-id="e5612-134">Perform monthly or quarterly reviews of your existing Office 365 Cloud App Security policies to include enhancements in Office 365 Cloud App Security and address new cyberattacks and trends in cybersecurity</span></span>  <br/> |
   
<span data-ttu-id="e5612-135">根據貴組織的大小和監視和維護安全性成長感興趣，您可以針對包含您 IT 管理鏈結編譯每月摘要：</span><span class="sxs-lookup"><span data-stu-id="e5612-135">Depending on your organization's size and interest in monitoring and maintaining a security stature, you can compile a monthly summary for your IT management chain that includes:</span></span>
  
- <span data-ttu-id="e5612-136">不同類型的識別與 Office 365 雲端 App 安全性的安全性事件</span><span class="sxs-lookup"><span data-stu-id="e5612-136">The different types of security incidents identified with Office 365 Cloud App Security</span></span>
    
- <span data-ttu-id="e5612-137">從中央的記錄檔的安全性事件，例如偵測的事件數目的摘要資訊</span><span class="sxs-lookup"><span data-stu-id="e5612-137">Summary information from your central log of the security incidents, such as number of incidents detected</span></span>
    
- <span data-ttu-id="e5612-138">警示的趨勢和已處理的方式</span><span class="sxs-lookup"><span data-stu-id="e5612-138">Alert trends and how they were addressed</span></span>
    
- <span data-ttu-id="e5612-139">最新的 cybersecurity 趨勢</span><span class="sxs-lookup"><span data-stu-id="e5612-139">The latest cybersecurity trends</span></span>
    
- <span data-ttu-id="e5612-140">Office 365 雲端 App 安全性原則變更與使用者對其影響建議</span><span class="sxs-lookup"><span data-stu-id="e5612-140">Recommendations for Office 365 Cloud App Security policy changes and their impact on end users</span></span>
    
## <a name="activities-after-time-has-passed-since-rolling-out-office-365-cloud-app-security"></a><span data-ttu-id="e5612-141">活動之後的時間經過自推出 Office 365 雲端 App 安全性</span><span class="sxs-lookup"><span data-stu-id="e5612-141">Activities after time has passed since rolling out Office 365 Cloud App Security</span></span>

<span data-ttu-id="e5612-142">如果一開始設定或維護 Office 365 雲端 App 安全性原則之後，已經過了一段時間的時間，，採取下列步驟，以得到反映出貴組織的安全性目標和現有的功能設定Office 365 雲端 App 安全性：</span><span class="sxs-lookup"><span data-stu-id="e5612-142">If a protracted amount of time has passed since you initially configured or maintained your Office 365 Cloud App Security policies, take the following steps to get back to a configuration that reflects your organization's security goals and the current capabilities of Office 365 Cloud App Security:</span></span>
  
1. <span data-ttu-id="e5612-143">決定 Office 365 雲端 App 安全性上次進行組態變更的日期。</span><span class="sxs-lookup"><span data-stu-id="e5612-143">Determine the date of the last configuration change for Office 365 Cloud App Security.</span></span>
    
2. <span data-ttu-id="e5612-144">了解您目前的 Office 365 雲端 App 安全性設定，並視需要調整這些原則。</span><span class="sxs-lookup"><span data-stu-id="e5612-144">Understand your current Office 365 Cloud App Security configuration and adjust those policies as needed.</span></span> <span data-ttu-id="e5612-145">例如，請確定您知道其中要透過電子郵件傳送提醒。</span><span class="sxs-lookup"><span data-stu-id="e5612-145">For example, make sure you know where alerts are being sent via email.</span></span>
    
3. <span data-ttu-id="e5612-146">自您上次設定 Office 365 雲端 App 安全性後，請參閱[what's new in Office 365 雲端 App 安全性](new-in-office-365-cas.md)產品變更。</span><span class="sxs-lookup"><span data-stu-id="e5612-146">See [what's new in Office 365 Cloud App Security](new-in-office-365-cas.md) for product changes since you last configured Office 365 Cloud App Security.</span></span> 
    
4. <span data-ttu-id="e5612-147">執行 Office 365 雲端 App 安全性提醒及特別色異常的記錄檔的分析及分析趨勢。</span><span class="sxs-lookup"><span data-stu-id="e5612-147">Perform an analysis of Office 365 Cloud App Security alerts and logs to spot anomalies and analyze trends.</span></span>
    
5. <span data-ttu-id="e5612-148">請檢查以發現的最新的安全性威脅的產業 cybersecurity 趨勢。</span><span class="sxs-lookup"><span data-stu-id="e5612-148">Check industry cybersecurity trends to become aware of the latest security threats.</span></span>
    
6. <span data-ttu-id="e5612-149">執行分析，需要對目前的 Office 365 雲端 App 安全性原則進行的變更。</span><span class="sxs-lookup"><span data-stu-id="e5612-149">Perform an analysis of the changes that need to be made to the current set of Office 365 Cloud App Security policies.</span></span> <span data-ttu-id="e5612-150">整合 Office 365 雲端 App 安全性功能變更、 目前的異常及 cybersecurity 趨勢。</span><span class="sxs-lookup"><span data-stu-id="e5612-150">Incorporate Office 365 Cloud App Security feature changes, current anomalies, and cybersecurity trends.</span></span> <span data-ttu-id="e5612-151">建議變更現有的原則或建立新的原則。</span><span class="sxs-lookup"><span data-stu-id="e5612-151">Recommend changes to existing policies or the creation of new policies.</span></span>
    
7. <span data-ttu-id="e5612-152">進行的計劃實作原則的變更。</span><span class="sxs-lookup"><span data-stu-id="e5612-152">Make a plan for implementing the policy changes.</span></span> <span data-ttu-id="e5612-153">溝通 (socialize) 與視您使用者的建議變更的後果。</span><span class="sxs-lookup"><span data-stu-id="e5612-153">Communicate (socialize) the consequences of the proposed changes with your end users as needed.</span></span>
    
8. <span data-ttu-id="e5612-154">實作 Office 365 雲端 App 安全性原則變更。</span><span class="sxs-lookup"><span data-stu-id="e5612-154">Implement the Office 365 Cloud App Security policy changes.</span></span>
    
9. <span data-ttu-id="e5612-155">監視使用者意見反應和 Office 365 雲端 App 安全性提醒，並經過一段時間調整原則。</span><span class="sxs-lookup"><span data-stu-id="e5612-155">Monitor end user feedback and Office 365 Cloud App Security alerts and adjust policies over time.</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="e5612-156">後續步驟</span><span class="sxs-lookup"><span data-stu-id="e5612-156">Next steps</span></span>

- [<span data-ttu-id="e5612-157">調查活動</span><span class="sxs-lookup"><span data-stu-id="e5612-157">Investigate an activity</span></span>](investigate-an-activity-in-office-365-cas.md)
    
- [<span data-ttu-id="e5612-158">暫停或還原使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="e5612-158">Suspend or restore a user account</span></span>](suspend-or-restore-an-account-in-ocas.md)
    
- [<span data-ttu-id="e5612-159">管理 OAuth 應用程式</span><span class="sxs-lookup"><span data-stu-id="e5612-159">Manage OAuth apps</span></span>](manage-app-permissions-in-ocas.md)
    
- [<span data-ttu-id="e5612-160">檢閱 Office 365 雲端 App 安全性中的 App 探索結果</span><span class="sxs-lookup"><span data-stu-id="e5612-160">Review app discovery findings in Office 365 Cloud App Security</span></span>](review-app-discovery-findings-in-ocas.md)
    
- <span data-ttu-id="e5612-161">檢視支援的[網頁流量記錄及資料來源](web-traffic-logs-and-data-sources-for-ocas.md)的清單</span><span class="sxs-lookup"><span data-stu-id="e5612-161">View a list of supported [Web traffic logs and data sources](web-traffic-logs-and-data-sources-for-ocas.md)</span></span>
    

