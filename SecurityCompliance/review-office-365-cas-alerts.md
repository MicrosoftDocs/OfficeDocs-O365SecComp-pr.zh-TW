---
title: 檢閱並對 Office 365 雲端 App 安全性中的警示採取動作
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
ms.assetid: 97e9c3d9-df89-458e-924b-369becee5532
description: 使用 Office 365 雲端應用程式安全性提醒] 頁面上檢視潛在的問題，採取的動作。您可以關閉或解析提醒，並如有必要，擱置的使用者帳戶。
ms.openlocfilehash: 62431adc73354e573978781f120a11746aef08d9
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526141"
---
# <a name="review-and-take-action-on-alerts-in-office-365-cloud-app-security"></a><span data-ttu-id="b7f40-104">檢閱並對 Office 365 雲端 App 安全性中的警示採取動作</span><span class="sxs-lookup"><span data-stu-id="b7f40-104">Review and take action on alerts in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="b7f40-105">評估 * *\>**</span><span class="sxs-lookup"><span data-stu-id="b7f40-105">****Evaluation** \>**</span></span>|<span data-ttu-id="b7f40-106">規劃 * *\>**</span><span class="sxs-lookup"><span data-stu-id="b7f40-106">****Planning** \>**</span></span>|<span data-ttu-id="b7f40-107">部署 * *\>**</span><span class="sxs-lookup"><span data-stu-id="b7f40-107">****Deployment** \>**</span></span>|<span data-ttu-id="b7f40-108">使用率 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="b7f40-108">****Utilization****</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="b7f40-109">啟動評估</span><span class="sxs-lookup"><span data-stu-id="b7f40-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="b7f40-110">開始規劃</span><span class="sxs-lookup"><span data-stu-id="b7f40-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="b7f40-111">開始部署</span><span class="sxs-lookup"><span data-stu-id="b7f40-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="b7f40-112">您在此處 ！</span><span class="sxs-lookup"><span data-stu-id="b7f40-112">You are here!</span></span>  <br/> [<span data-ttu-id="b7f40-113">後續步驟</span><span class="sxs-lookup"><span data-stu-id="b7f40-113">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="b7f40-114">您可以使用 Office 365 雲端應用程式安全性的提醒] 頁面上檢視潛在的問題和必要時，採取動作。</span><span class="sxs-lookup"><span data-stu-id="b7f40-114">You can use the Alerts page in Office 365 Cloud App Security to view potential issues and, if needed, take action.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b7f40-p102">您必須是讓全域管理員或安全性管理員執行本文中的工作。請參閱[中的 Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="b7f40-p102">You must be a global administrator or security administrator to perform the tasks in this article. See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="how-to-get-to-the-alerts-page"></a><span data-ttu-id="b7f40-117">如何取得提醒] 頁面上</span><span class="sxs-lookup"><span data-stu-id="b7f40-117">How to get to the Alerts page</span></span>

1. <span data-ttu-id="b7f40-118">以全域管理員或安全性管理員中，移至[https://protection.office.com](https://protection.office.com)並使用您工作或學校的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="b7f40-118">As a global administrator or security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account.</span></span> 
    
2. <span data-ttu-id="b7f40-119">安全性&amp;規範中心選擇**提醒** \> **管理進階提醒**。</span><span class="sxs-lookup"><span data-stu-id="b7f40-119">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="b7f40-120">選擇 [**移至 Office 365 的雲端應用程式安全性**]。</span><span class="sxs-lookup"><span data-stu-id="b7f40-120">Choose **Go to Office 365 Cloud App Security**.</span></span>
    
    ![安全性&amp;規範中心選擇管理進階警告移至 Office 365 雲端應用程式安全性](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)
  
4. <span data-ttu-id="b7f40-122">在不同螢幕頂端導覽列中，選擇 [**提醒**]。</span><span class="sxs-lookup"><span data-stu-id="b7f40-122">In the navigation bar across the top of the screen, choose **Alerts**.</span></span>
    
    ![在 [提醒] 頁面中，您可以看到所觸發的警告與採取任何動作。](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)
  
## <a name="review-and-handle-alerts"></a><span data-ttu-id="b7f40-124">檢閱及控點提醒</span><span class="sxs-lookup"><span data-stu-id="b7f40-124">Review and handle alerts</span></span>

<span data-ttu-id="b7f40-p103">提醒可協助您識別您要進一步調查的 Office 365 雲端環境中的活動。您也可以決定建立新的原則或編輯現有的原則根據您會看到提醒。例如，如果您看到從怪異位置登入系統管理員，您可能會決定防止從特定位置登入 Office 365 系統管理員的原則設定。</span><span class="sxs-lookup"><span data-stu-id="b7f40-p103">Alerts help you identify activities in your Office 365 cloud environment that you might want to investigate further. You might also decide to create new policies or edit existing policies based on the alerts you see. For example, if you see an administrator logging on from a strange location, you may decide to set up a policy that prevents administrators from signing in to Office 365 from certain locations.</span></span>
  
> [!TIP]
> <span data-ttu-id="b7f40-128">您可以篩選提醒依**類別**] 或 [依**嚴重性**讓您可以先管理最重要的。</span><span class="sxs-lookup"><span data-stu-id="b7f40-128">You can filter the alerts by **Category** or by **Severity** so you can manage the most important ones first.</span></span> 
  
<span data-ttu-id="b7f40-p104">針對每個通知中，尋找到項目會造成它讓您可以決定要採取的動作。若要查看通知的更多詳細資料，並採取動作，例如解決警示或暫止的使用者帳戶，選擇 [開啟詳細資料] 頁面上的提醒。在詳細資料] 頁面上，您可以檢閱活動記錄檔、 帳戶及使用者的相關警示中，並採取下列動作：</span><span class="sxs-lookup"><span data-stu-id="b7f40-p104">For each alert, look into what caused it so you can decide what action to take. To see more details about an alert and to take action, such as resolving the alert or suspending a users account, choose the alert to open a details page. On the details page, you can review the activity log, accounts, and users that are related to the alert, and take actions such as the following:</span></span>
  
- <span data-ttu-id="b7f40-p105">**關閉**如果警示誤判，關閉它。您可以選擇性地新增註解解釋解除為何。</span><span class="sxs-lookup"><span data-stu-id="b7f40-p105">**Dismiss** If the alert was a false positive, dismiss it. You can optionally add a comment explaining why you dismissed it.</span></span> 
    
- <span data-ttu-id="b7f40-p106">**解決通知**如果所觸發提醒您知道活動不是威脅、 加以解決。您可以選擇性地新增註解解釋解析為何。</span><span class="sxs-lookup"><span data-stu-id="b7f40-p106">**Resolve alert** If the alert was triggered by an activity that you know isn't a threat, resolve it. You can optionally add a comment explaining why you resolved it.</span></span> 
    
- <span data-ttu-id="b7f40-136">**暫停**如果您認為未經授權的登入帳戶，例如某人時您知道該名人員從另一個國家 （地區） 登入集實際位於本機 office 時，您還可以[暫停帳戶](suspend-or-restore-an-account-in-ocas.md)時您調查什麼下來的動作。</span><span class="sxs-lookup"><span data-stu-id="b7f40-136">**Suspend** If you suspect unauthorized sign ins on an account, for example, someone signing in from another country when you know that person is physically at a local office, you can [suspend the account](suspend-or-restore-an-account-in-ocas.md) while you investigate what's going on.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="b7f40-137">後續步驟</span><span class="sxs-lookup"><span data-stu-id="b7f40-137">Next steps</span></span>

- [<span data-ttu-id="b7f40-138">調查活動</span><span class="sxs-lookup"><span data-stu-id="b7f40-138">Investigate an activity</span></span>](investigate-an-activity-in-office-365-cas.md)
    
- [<span data-ttu-id="b7f40-139">擱置或還原使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="b7f40-139">Suspend or restore a user account</span></span>](suspend-or-restore-an-account-in-ocas.md)
    
- <span data-ttu-id="b7f40-140">檢視支援的[網頁流量記錄檔與資料來源](web-traffic-logs-and-data-sources-for-ocas.md)的清單</span><span class="sxs-lookup"><span data-stu-id="b7f40-140">View a list of supported [Web traffic logs and data sources](web-traffic-logs-and-data-sources-for-ocas.md)</span></span>
    
- <span data-ttu-id="b7f40-141">檢閱您[的 Office 365 雲端應用程式安全性使用率活動](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="b7f40-141">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

