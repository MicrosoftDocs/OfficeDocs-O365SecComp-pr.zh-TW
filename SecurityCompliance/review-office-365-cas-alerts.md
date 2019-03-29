---
title: 檢閱並對 Office 365 雲端 App 安全性中的警示採取動作
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
ms.assetid: 97e9c3d9-df89-458e-924b-369becee5532
description: 使用 Office 365 雲端 App 安全性中的 [提醒] 頁面上，檢視潛在的問題，並採取動作。 您可以關閉或解決的警示，並如有必要，擱置的使用者帳戶。
ms.openlocfilehash: 701d80c3f890115c6c403fff21d2d0444d71c95a
ms.sourcegitcommit: 1658be51e2c21ed23bc4467a98af74300a45b975
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/26/2019
ms.locfileid: "30862465"
---
# <a name="review-and-take-action-on-alerts-in-office-365-cloud-app-security"></a><span data-ttu-id="d3d6d-104">檢閱並對 Office 365 雲端 App 安全性中的警示採取動作</span><span class="sxs-lookup"><span data-stu-id="d3d6d-104">Review and take action on alerts in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="d3d6d-105">評估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="d3d6d-105">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="d3d6d-106">規劃 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="d3d6d-106">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="d3d6d-107">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="d3d6d-107">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="d3d6d-108">使用率 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="d3d6d-108">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="d3d6d-109">啟動評估</span><span class="sxs-lookup"><span data-stu-id="d3d6d-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="d3d6d-110">開始規劃</span><span class="sxs-lookup"><span data-stu-id="d3d6d-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="d3d6d-111">開始部署</span><span class="sxs-lookup"><span data-stu-id="d3d6d-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="d3d6d-112">您在此處 ！</span><span class="sxs-lookup"><span data-stu-id="d3d6d-112">You are here!</span></span>  <br/> [<span data-ttu-id="d3d6d-113">後續步驟</span><span class="sxs-lookup"><span data-stu-id="d3d6d-113">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="d3d6d-114">您可以使用 Office 365 雲端 App 安全性中的 [提醒] 頁面上，檢視潛在的問題，並如有需要採取動作。</span><span class="sxs-lookup"><span data-stu-id="d3d6d-114">You can use the Alerts page in Office 365 Cloud App Security to view potential issues and, if needed, take action.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d3d6d-115">您必須是全域系統管理員或安全性系統管理員來執行本文中的工作。</span><span class="sxs-lookup"><span data-stu-id="d3d6d-115">You must be a global administrator or security administrator to perform the tasks in this article.</span></span> <span data-ttu-id="d3d6d-116">請參閱[中的 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="d3d6d-116">See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="how-to-get-to-the-alerts-page"></a><span data-ttu-id="d3d6d-117">如何取得 [提醒] 頁面上</span><span class="sxs-lookup"><span data-stu-id="d3d6d-117">How to get to the Alerts page</span></span>

1. <span data-ttu-id="d3d6d-118">移至 Cloud App Security 入口網站 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com))，並登入。</span><span class="sxs-lookup"><span data-stu-id="d3d6d-118">Go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span>
  
2. <span data-ttu-id="d3d6d-119">在跨螢幕頂端導覽列中，選擇 [**提醒**]。</span><span class="sxs-lookup"><span data-stu-id="d3d6d-119">In the navigation bar across the top of the screen, choose **Alerts**.</span></span><br/><span data-ttu-id="d3d6d-120">![在 [提醒] 頁面中，您可以看到所觸發的警示和採取任何動作。](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)</span><span class="sxs-lookup"><span data-stu-id="d3d6d-120">![On the Alerts page, you can see alerts that were triggered and any actions taken.](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)</span></span>
 
> [!NOTE]
> <span data-ttu-id="d3d6d-121">雲端 App 安全性提醒也會顯示在 Office 365 安全性 & 合規性中心 (前往**提醒** > **檢視警示**。</span><span class="sxs-lookup"><span data-stu-id="d3d6d-121">Cloud App Security alerts are also visible in the Office 365 Security & Compliance Center (go to **Alerts** > **View alerts**.</span></span> <span data-ttu-id="d3d6d-122">目前，不過，您必須先解決這些 Cloud App Security 入口網站和 Office 365 安全性 & 合規性中心中的警示。</span><span class="sxs-lookup"><span data-stu-id="d3d6d-122">Currently, however, you must resolve these alerts in both the Cloud App Security portal and the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="d3d6d-123">若要深入了解，請參閱[檢視 Cloud App Security 警示](alert-policies.md#viewing-cloud-app-security-alerts)）。</span><span class="sxs-lookup"><span data-stu-id="d3d6d-123">To learn more, see [Viewing Cloud App Security alerts](alert-policies.md#viewing-cloud-app-security-alerts).)</span></span> 
 
## <a name="review-and-handle-alerts"></a><span data-ttu-id="d3d6d-124">檢閱及控點通知</span><span class="sxs-lookup"><span data-stu-id="d3d6d-124">Review and handle alerts</span></span>

<span data-ttu-id="d3d6d-125">警示可協助您找出您可能想要更進一步調查與 Office 365 雲端環境中的活動。</span><span class="sxs-lookup"><span data-stu-id="d3d6d-125">Alerts help you identify activities in your Office 365 cloud environment that you might want to investigate further.</span></span> <span data-ttu-id="d3d6d-126">您也可能決定要建立新的原則或編輯現有的原則，根據您看到的通知。</span><span class="sxs-lookup"><span data-stu-id="d3d6d-126">You might also decide to create new policies or edit existing policies based on the alerts you see.</span></span> <span data-ttu-id="d3d6d-127">例如，如果您看到從怪異位置登入系統管理員，您可能決定設定防止系統管理員登入 Office 365 從特定位置的原則。</span><span class="sxs-lookup"><span data-stu-id="d3d6d-127">For example, if you see an administrator logging on from a strange location, you may decide to set up a policy that prevents administrators from signing in to Office 365 from certain locations.</span></span>
  
> [!TIP]
> <span data-ttu-id="d3d6d-128">讓您可以先管理最重要的您可以篩選依**類別**] 或 [依**嚴重性**的警示。</span><span class="sxs-lookup"><span data-stu-id="d3d6d-128">You can filter the alerts by **Category** or by **Severity** so you can manage the most important ones first.</span></span> 
  
<span data-ttu-id="d3d6d-129">在每個警示，查看項目會導致它讓您可以決定要採取什麼動作。</span><span class="sxs-lookup"><span data-stu-id="d3d6d-129">For each alert, look into what caused it so you can decide what action to take.</span></span> <span data-ttu-id="d3d6d-130">若要查看警示的更多詳細資料，要採取的動作，例如解決警示或擱置的使用者帳戶，選擇 [若要開啟 [詳細資料] 頁面上警示。</span><span class="sxs-lookup"><span data-stu-id="d3d6d-130">To see more details about an alert and to take action, such as resolving the alert or suspending a users account, choose the alert to open a details page.</span></span> <span data-ttu-id="d3d6d-131">在 [詳細資料] 頁面中，您可以檢閱活動記錄檔、 帳戶及警示，相關的使用者，並採取動作如下所示：</span><span class="sxs-lookup"><span data-stu-id="d3d6d-131">On the details page, you can review the activity log, accounts, and users that are related to the alert, and take actions such as the following:</span></span>
  
- <span data-ttu-id="d3d6d-132">**關閉**如果警示誤判，關閉它。</span><span class="sxs-lookup"><span data-stu-id="d3d6d-132">**Dismiss** If the alert was a false positive, dismiss it.</span></span> <span data-ttu-id="d3d6d-133">您可以選擇新增註解解釋您關閉的原因。</span><span class="sxs-lookup"><span data-stu-id="d3d6d-133">You can optionally add a comment explaining why you dismissed it.</span></span> 
    
- <span data-ttu-id="d3d6d-134">**解決警示**如果警示所觸發的活動，您知道不威脅、 加以解決。</span><span class="sxs-lookup"><span data-stu-id="d3d6d-134">**Resolve alert** If the alert was triggered by an activity that you know isn't a threat, resolve it.</span></span> <span data-ttu-id="d3d6d-135">您可以選擇性地新增說明為什麼您解決的註解。</span><span class="sxs-lookup"><span data-stu-id="d3d6d-135">You can optionally add a comment explaining why you resolved it.</span></span> 
    
- <span data-ttu-id="d3d6d-136">**暫停**如果您懷疑未經授權的正負號的帳戶，例如某人時您知道該人員從另一個國家/地區登入集實際位於本機 office，您可以[暫停帳戶](suspend-or-restore-an-account-in-ocas.md)時，要調查什麼事。</span><span class="sxs-lookup"><span data-stu-id="d3d6d-136">**Suspend** If you suspect unauthorized sign ins on an account, for example, someone signing in from another country when you know that person is physically at a local office, you can [suspend the account](suspend-or-restore-an-account-in-ocas.md) while you investigate what's going on.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="d3d6d-137">後續步驟</span><span class="sxs-lookup"><span data-stu-id="d3d6d-137">Next steps</span></span>

- [<span data-ttu-id="d3d6d-138">調查活動</span><span class="sxs-lookup"><span data-stu-id="d3d6d-138">Investigate an activity</span></span>](investigate-an-activity-in-office-365-cas.md)
    
- [<span data-ttu-id="d3d6d-139">暫停或還原使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="d3d6d-139">Suspend or restore a user account</span></span>](suspend-or-restore-an-account-in-ocas.md)
    
- <span data-ttu-id="d3d6d-140">檢視支援的[網頁流量記錄及資料來源](web-traffic-logs-and-data-sources-for-ocas.md)的清單</span><span class="sxs-lookup"><span data-stu-id="d3d6d-140">View a list of supported [Web traffic logs and data sources](web-traffic-logs-and-data-sources-for-ocas.md)</span></span>
    
- <span data-ttu-id="d3d6d-141">檢閱您[的 Office 365 雲端 App 安全性的使用率活動](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="d3d6d-141">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

