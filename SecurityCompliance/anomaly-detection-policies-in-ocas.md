---
title: Office 365 雲端 App 安全性中的異常偵測原則
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/15/2019
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 88935b4e-dcb1-47f1-8aca-1bf8fb069db6
description: 'Office 365 雲端應用程式安全性異常偵測原則使用內建的演算法可協助從抽出潛在的問題。您應該會有至少一個異常偵測原則] 中，您可以使用篩選器來調整 （當您建立它）。 '
ms.openlocfilehash: a3c7fb16ab10b0bcfaca444093e4e1f52468f0c8
ms.sourcegitcommit: 8679937354c1d8870ecd41519a59d2d7468c23c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2019
ms.locfileid: "30087362"
---
# <a name="anomaly-detection-policies-in-office-365-cloud-app-security"></a><span data-ttu-id="14ad6-104">Office 365 雲端 App 安全性中的異常偵測原則</span><span class="sxs-lookup"><span data-stu-id="14ad6-104">Anomaly detection policies in Office 365 Cloud App Security</span></span>

|<span data-ttu-id="14ad6-105">評估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="14ad6-105">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="14ad6-106">規劃 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="14ad6-106">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="14ad6-107">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="14ad6-107">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="14ad6-108">使用率 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="14ad6-108">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="14ad6-109">啟動評估</span><span class="sxs-lookup"><span data-stu-id="14ad6-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="14ad6-110">開始規劃</span><span class="sxs-lookup"><span data-stu-id="14ad6-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="14ad6-111">您在此處 ！</span><span class="sxs-lookup"><span data-stu-id="14ad6-111">You are here!</span></span>  <br/> [<span data-ttu-id="14ad6-112">下一步</span><span class="sxs-lookup"><span data-stu-id="14ad6-112">Next step</span></span>](ocas-conditional-access-app-control.md) <br/> |[<span data-ttu-id="14ad6-113">開始使用</span><span class="sxs-lookup"><span data-stu-id="14ad6-113">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
<span data-ttu-id="14ad6-114">Office 365 雲端應用程式安全性開頭[版本 116 Microsoft 雲端應用程式安全性](new-in-office-365-cas-2018.md#office-365-cloud-app-security-release-116)，包括數個預先定義的異常偵測原則原則 （"現成可用"），包括使用者和實體行為上有無分析 (UEBA) 和學習 （毫升） 的電腦。</span><span class="sxs-lookup"><span data-stu-id="14ad6-114">Beginning with [Microsoft Cloud App Security release 116](new-in-office-365-cas-2018.md#office-365-cloud-app-security-release-116), Office 365 Cloud App Security includes several predefined anomaly detection policies ("out of the box") that include user and entity behavioral analytics (UEBA) and machine learning (ML).</span></span>
  
![若要檢視您異常偵測原則，請選擇 [控制\>原則。](media/9663baa5-98bf-45e0-9458-6e572b43ec72.png)
  
<span data-ttu-id="14ad6-p102">這些異常偵測原則提供立即偵測、 目標許多行為上有無異常為您的使用者在機器和裝置連線到您的網路之間提供立即的結果。此外，新的原則會公開可協助您加速調查程序，包含持續威脅的雲端應用程式安全性偵測引擎的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="14ad6-p102">These anomaly detection policies provide immediate results by providing immediate detections, targeting numerous behavioral anomalies across your users and the machines and devices connected to your network. In addition, the new policies expose more data from the Cloud App Security detection engine to help you speed up the investigation process and contain ongoing threats.</span></span>
  
<span data-ttu-id="14ad6-118">為 Office 365 全域管理員或安全性管理員，您可以檢閱及必要時修改可用來搭配 Office 365 雲端應用程式安全性的預設原則。</span><span class="sxs-lookup"><span data-stu-id="14ad6-118">As an Office 365 global administrator or security administrator, you can review, and if necessary, revise the default policies that are available with Office 365 Cloud App Security.</span></span>
  
 > [!IMPORTANT]
> <span data-ttu-id="14ad6-p103">有七 （7） 天的期間異常行為提醒不會觸發初始學習期間。異常偵測演算法已最佳化來減少 false 正數的提醒數目。</span><span class="sxs-lookup"><span data-stu-id="14ad6-p103">There is an initial learning period of seven (7) days during which anomalous behavior alerts are not triggered. The anomaly detection algorithm is optimized to reduce the number of false positive alerts.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="14ad6-121">開始之前</span><span class="sxs-lookup"><span data-stu-id="14ad6-121">Before you begin</span></span>

<span data-ttu-id="14ad6-122">請確定：</span><span class="sxs-lookup"><span data-stu-id="14ad6-122">Make sure that:</span></span>
  
- <span data-ttu-id="14ad6-123">您的組織具有[Office 365 雲端應用程式安全性](office-365-cas-overview.md)] 和服務已[開啟](turn-on-office-365-cas.md)。</span><span class="sxs-lookup"><span data-stu-id="14ad6-123">Your organization has [Office 365 Cloud App Security](office-365-cas-overview.md), and the service is [turned on](turn-on-office-365-cas.md).</span></span>
    
- <span data-ttu-id="14ad6-124">[稽核記錄](turn-audit-log-search-on-or-off.md)已開啟的 Office 365 環境。</span><span class="sxs-lookup"><span data-stu-id="14ad6-124">[Audit logging](turn-audit-log-search-on-or-off.md) is turned on for your Office 365 environment.</span></span> 
    
- <span data-ttu-id="14ad6-125">您已為全域管理員或 Office 365 的安全性管理員。</span><span class="sxs-lookup"><span data-stu-id="14ad6-125">You are a global administrator or security administrator for Office 365.</span></span>
    
## <a name="view-your-anomaly-detection-policies"></a><span data-ttu-id="14ad6-126">檢視您異常偵測原則</span><span class="sxs-lookup"><span data-stu-id="14ad6-126">View your anomaly detection policies</span></span>

1. <span data-ttu-id="14ad6-127">以全域管理員或安全性管理員中，移至雲端應用程式安全性入口網站 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="14ad6-127">As a global administrator or security administrator, go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span><br><span data-ttu-id="14ad6-128">這會帶您至 [Office 365 雲端應用程式的安全性原則] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="14ad6-128">This takes you to the Office 365 Cloud App Security Policies page.</span></span>
    
2. <span data-ttu-id="14ad6-129">在 [**類型**] 清單中選擇 [**異常偵測原則**]。</span><span class="sxs-lookup"><span data-stu-id="14ad6-129">In the **TYPE** list, choose **Anomaly detection policy**.</span></span><br><span data-ttu-id="14ad6-130">貴組織的預設值 （或現有） 顯示異常偵測原則。</span><span class="sxs-lookup"><span data-stu-id="14ad6-130">Your organization's default (or existing) anomaly detection policies are displayed.</span></span><br><span data-ttu-id="14ad6-131">![Office 365 雲端 App 安全性中的異常偵測原則](media/2e0ee770-787a-4d4a-bea8-389dc765d4c6.png)</span><span class="sxs-lookup"><span data-stu-id="14ad6-131">![Anomaly detection policies in Office 365 Cloud App Security](media/2e0ee770-787a-4d4a-bea8-389dc765d4c6.png)</span></span>
  
3. <span data-ttu-id="14ad6-132">選取要檢視或編輯其設定的原則。</span><span class="sxs-lookup"><span data-stu-id="14ad6-132">Select a policy to review or edit its settings.</span></span>
    
4. <span data-ttu-id="14ad6-133">選擇 [**更新**] 以儲存變更。</span><span class="sxs-lookup"><span data-stu-id="14ad6-133">Choose **Update** to save your changes.</span></span> 
    
## <a name="learn-more-about-anomaly-detection-policies"></a><span data-ttu-id="14ad6-134">深入了解異常偵測原則</span><span class="sxs-lookup"><span data-stu-id="14ad6-134">Learn more about anomaly detection policies</span></span>

<span data-ttu-id="14ad6-p104">異常偵測原則會自動啟用;不過，Office 365 雲端應用程式安全性有哪些不是所有異常期間偵測警示所引發的七天的初始學習期間。之後，每個工作階段會比較當使用者已作用中的活動、 IP 位址、 裝置、 等偵測的過去月及這些活動風險分數。這些偵測屬於探索異常偵測引擎的設定檔環境及觸發提醒表示已在您的組織活動學到的基準。這些偵測也運用機器學習演算法設計用來設定檔的使用者和登入模式來減少誤判。</span><span class="sxs-lookup"><span data-stu-id="14ad6-p104">Anomaly detection policies are automatically enabled; however, Office 365 Cloud App Security has an initial learning period of seven days during which not all anomaly detection alerts are raised. After that, each session is compared to the activity, when users were active, IP addresses, devices, etc. detected over the past month and the risk score of these activities. These detections are part of the heuristic anomaly detection engine that profiles your environment and triggers alerts with respect to a baseline that was learned on your organization's activity. These detections also leverage machine learning algorithms designed to profile the users and log-in patterns to reduce false positives.</span></span>
  
<span data-ttu-id="14ad6-p105">異常偵測到掃描使用者活動。透過查看超過 30 不同風險指標，分為多個風險因素，risky IP 位址、 登入失敗、 系統活動、 非使用中帳戶、 位置、 無法運用旅行、 裝置和使用者代理程式及活動率等評估風險。</span><span class="sxs-lookup"><span data-stu-id="14ad6-p105">Anomalies are detected by scanning user activity. The risk is evaluated by looking at over 30 different risk indicators, grouped into multiple risk factors, such as risky IP address, login failures, admin activity, inactive accounts, location, impossible travel, device and user agent, and activity rate.</span></span>
  
<span data-ttu-id="14ad6-p106">根據原則結果，安全性提醒會觸發。Office 365 雲端應用程式安全性尋找在 Office 365 中每個使用者工作階段，並在提醒您每當發生變化不同從您的組織的基準或從使用者的一般活動。</span><span class="sxs-lookup"><span data-stu-id="14ad6-p106">Based on the policy results, security alerts are triggered. Office 365 Cloud App Security looks at every user session in Office 365, and alerts you whenever something happens that is different from the baseline of your organization or from a user's regular activity.</span></span>
  
<span data-ttu-id="14ad6-143">下表說明預設異常偵測原則、 所執行的動作，以及它們的運作方式。</span><span class="sxs-lookup"><span data-stu-id="14ad6-143">The following table describes the default anomaly detection policies, what they do, and how they work.</span></span>
  
|<span data-ttu-id="14ad6-144">**異常偵測原則名稱**</span><span class="sxs-lookup"><span data-stu-id="14ad6-144">**Anomaly detection policy name**</span></span>|<span data-ttu-id="14ad6-145">**運作方式**</span><span class="sxs-lookup"><span data-stu-id="14ad6-145">**How it works**</span></span>|
|:-----|:-----|
|<span data-ttu-id="14ad6-146">無法運用旅行</span><span class="sxs-lookup"><span data-stu-id="14ad6-146">Impossible travel</span></span>  <br/> |<span data-ttu-id="14ad6-p107">會識別兩個使用者活動 （為單一或多個工作階段） 源自遠距位置小於時間期間內它可能需要花旅行社從第一個位置的第二個，指出使用者不同使用者正在使用的相同認證。此偵測如何運用學習明顯"誤判"貢獻無法運用旅行條件，例如 Vpn 和定期組織中的其他使用者所使用的位置會略過的演算法機器。偵測有七天的期間它可學習新使用者的活動模式的初始學習期間。</span><span class="sxs-lookup"><span data-stu-id="14ad6-p107">Identifies two user activities (is a single or multiple sessions) originating from geographically distant locations within a time period shorter than the time it would have taken the user to travel from the first location to the second, indicating that a different user is using the same credentials. This detection leverages a machine learning algorithm that ignores obvious "false positives" contributing to the impossible travel condition, such as VPNs and locations regularly used by other users in the organization. The detection has an initial learning period of seven days during which it learns a new user's activity pattern.</span></span>  <br/> |
|<span data-ttu-id="14ad6-150">從非經常性國家/地區的活動</span><span class="sxs-lookup"><span data-stu-id="14ad6-150">Activity from infrequent country</span></span>  <br/> |<span data-ttu-id="14ad6-p108">若要判斷最新及非經常性位置會考慮過去的活動位置。異常偵測引擎會儲存在組織中使用者所使用的上一個位置相關資訊。從已不最近或永不造訪由使用者或組織中任何使用者的位置活動時發生觸發提醒。</span><span class="sxs-lookup"><span data-stu-id="14ad6-p108">Considers past activity locations to determine new and infrequent locations. The anomaly detection engine stores information about previous locations used by users in the organization. An alert is triggered when an activity occurs from a location that was not recently or never visited by the user or by any user in the organization.</span></span>  <br/> |
|<span data-ttu-id="14ad6-154">從匿名的 IP 位址的活動</span><span class="sxs-lookup"><span data-stu-id="14ad6-154">Activity from anonymous IP addresses</span></span>  <br/> |<span data-ttu-id="14ad6-p109">識別使用者已被識別為匿名的 proxy IP 位址的 IP 位址從作用中。想要隱藏使用者的裝置 IP 位址，以及可能會使用惡意的人使用這些 proxy。此偵測如何運用學習減少"誤判 」，例如正確標記廣泛組織中的使用者所使用的 IP 位址的演算法機器。</span><span class="sxs-lookup"><span data-stu-id="14ad6-p109">Identifies that users were active from an IP address that has been identified as an anonymous proxy IP address. These proxies are used by people who want to hide their device's IP address, and may be used for malicious intent. This detection leverages a machine learning algorithm that reduces "false positives", such as mis-tagged IP addresses that are widely used by users in the organization.</span></span>  <br/> |
|<span data-ttu-id="14ad6-158">從可疑的 IP 位址的活動</span><span class="sxs-lookup"><span data-stu-id="14ad6-158">Activity from suspicious IP addresses</span></span>  <br/> |<span data-ttu-id="14ad6-p110">識別使用者已被識別為 risky 由 Microsoft Threat 智慧 IP 位址從作用中。這些 IP 位址參與惡意活動的 Botnet C&amp;C，而且可能會指出入侵的帳戶。此偵測如何運用學習減少"誤判 」，例如正確標記廣泛組織中的使用者所使用的 IP 位址的演算法機器。</span><span class="sxs-lookup"><span data-stu-id="14ad6-p110">Identifies that users were active from an IP address that has been identified as risky by Microsoft Threat Intelligence. These IP addresses are involved in malicious activities, such as Botnet C&amp;C, and may indicate compromised account. This detection leverages a machine learning algorithm that reduces "false positives", such as mis-tagged IP addresses that are widely used by users in the organization.</span></span>  <br/> |
|<span data-ttu-id="14ad6-162">不尋常活動 （由使用者）</span><span class="sxs-lookup"><span data-stu-id="14ad6-162">Unusual activities (by user)</span></span>  <br/> | <span data-ttu-id="14ad6-163">識別使用者執行不尋常的活動，例如：</span><span class="sxs-lookup"><span data-stu-id="14ad6-163">Identifies users who perform unusual activities, such as:</span></span>  <br/>  <span data-ttu-id="14ad6-164">-多個檔案下載</span><span class="sxs-lookup"><span data-stu-id="14ad6-164">--Multiple file downloads</span></span>  <br/>  <span data-ttu-id="14ad6-165">-檔案共用的活動</span><span class="sxs-lookup"><span data-stu-id="14ad6-165">--File sharing activities</span></span>  <br/>  <span data-ttu-id="14ad6-166">-檔案刪除活動</span><span class="sxs-lookup"><span data-stu-id="14ad6-166">--File deletion activities</span></span>  <br/>  <span data-ttu-id="14ad6-167">-模擬活動</span><span class="sxs-lookup"><span data-stu-id="14ad6-167">--Impersonation activities</span></span>  <br/>  <span data-ttu-id="14ad6-168">-管理活動</span><span class="sxs-lookup"><span data-stu-id="14ad6-168">--Administrative activities</span></span>  <br/>  <span data-ttu-id="14ad6-p111">這些原則尋找活動內單一工作階段相對於基線學會，這可能表示上破壞嘗試。這些偵測運用學習設定檔的使用者登入模式的演算法機器並減少誤判。這些偵測屬於探索異常偵測引擎的設定檔環境及觸發提醒表示已在您的組織活動學到的基準。</span><span class="sxs-lookup"><span data-stu-id="14ad6-p111">These policies look for activities within a single session with respect to the baseline learned, which could indicate on a breach attempt. These detections leverage a machine learning algorithm that profiles the users log on pattern and reduces false positives. These detections are part of the heuristic anomaly detection engine that profiles your environment and triggers alerts with respect to a baseline that was learned on your organization's activity.</span></span>  <br/> |
|<span data-ttu-id="14ad6-172">多個失敗的登入嘗試次數</span><span class="sxs-lookup"><span data-stu-id="14ad6-172">Multiple failed login attempts</span></span>  <br/> |<span data-ttu-id="14ad6-173">失敗的單一工作階段中的多個登入嘗試的使用者會識別相對於學到的基準，這可能表示上破壞嘗試。</span><span class="sxs-lookup"><span data-stu-id="14ad6-173">Identifies users that failed multiple login attempts in a single session with respect to the baseline learned, which could indicate on a breach attempt.</span></span>  <br/> |
   
## <a name="triage-anomaly-detection-alerts"></a><span data-ttu-id="14ad6-174">分辨異常偵測警示</span><span class="sxs-lookup"><span data-stu-id="14ad6-174">Triage anomaly detection alerts</span></span>

<span data-ttu-id="14ad6-p112">當提醒甚至，您可以快速分辨這些提醒並決定哪些先處理。具有內容的通知可讓您查看更大的圖片，並決定是否遭到惡意的某個項目確實正在進行的活動。使用下列程序開始探索提醒：</span><span class="sxs-lookup"><span data-stu-id="14ad6-p112">As alerts come in, you can triage those alerts quickly and determine which ones to handle first. Having context for an alert enables you to see the bigger picture and determine whether something malicious is indeed happening. Use the following procedure to get started exploring an alert:</span></span>
  
1. <span data-ttu-id="14ad6-178">以全域管理員或安全性管理員中，移至雲端應用程式安全性入口網站 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="14ad6-178">As a global administrator or security administrator, go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span> 
    
2. <span data-ttu-id="14ad6-179">選擇 [以檢視您提醒的**提醒**。</span><span class="sxs-lookup"><span data-stu-id="14ad6-179">Choose **Alerts** to view your alerts.</span></span> 
    
3. <span data-ttu-id="14ad6-180">若要取得快顯通知，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="14ad6-180">To get context for an alert, follow these steps:</span></span>
    
4. <span data-ttu-id="14ad6-181">選擇**調查** \> **活動記錄檔**。</span><span class="sxs-lookup"><span data-stu-id="14ad6-181">Choose **Investigate** \> **Activity log**.</span></span>
    
5. <span data-ttu-id="14ad6-p113">選取項目，例如使用者或 IP 位址。如此會開啟相關的見解抽屜。</span><span class="sxs-lookup"><span data-stu-id="14ad6-p113">Select an item, such as a user or IP address. This opens the relevant insights drawer.</span></span><br>![您可以在活動記錄檔調查 IP 位址。](media/32a727c5-e406-4fe2-9443-c1a7fb6628fc.png)
  
6. <span data-ttu-id="14ad6-185">在相關的見解抽屜中，按一下 [可用的命令，例如**顯示如下**一節中的圖示。</span><span class="sxs-lookup"><span data-stu-id="14ad6-185">In the relevant insights drawer, click an available command, such as an icon in the **SHOW SIMILAR** section.</span></span><br> <span data-ttu-id="14ad6-186">![按一下 [時鐘] 圖示以查看所選活動的 48 小時內執行的活動](media/c6c96aa0-98e5-4205-8873-45f8d6fd0843.png)</span><span class="sxs-lookup"><span data-stu-id="14ad6-186">![Click the clock icon to see activities performed within 48 hours of a selected activity](media/c6c96aa0-98e5-4205-8873-45f8d6fd0843.png)</span></span>
  
7. <span data-ttu-id="14ad6-187">深入了解選取的項目來繼續探索表示項目詳細資料。</span><span class="sxs-lookup"><span data-stu-id="14ad6-187">Gain insight about the selected item by continuing to explore details for that item.</span></span>
    
<span data-ttu-id="14ad6-p114">在多個登入失敗通知可能確實可疑，因此可以表示潛在的暴力破解攻擊。但是，這類通知也可以是應用程式設定錯誤，導致設為良性 true 誤判提醒。如果您看到其他可疑活動與多重失敗 logins 提醒，就會危害帳戶的較高機率。例如，假設為多個失敗登通知後面接活動從 TOR IP 位址和無法運用旅行活動危害這兩個強式指標。您甚至可能會看到相同的使用者執行大量下載 （英文） 活動，這通常是執行 exfiltration 資料的攻擊者的指標。它的之類的可探索 Office 365 雲端應用程式安全性檢視和分辨您提醒，並採取動作在需要時。</span><span class="sxs-lookup"><span data-stu-id="14ad6-p114">An alert on multiple failed logins might indeed be suspicious, and can indicate a potential brute-force attack. However, such an alert can also be an application misconfiguration, causing the alert to be a benign true positive. If you see a multiple-failed-logins alert with additional suspicious activities, then there is a higher probability that an account is compromised. For example, suppose that a multiple-failed-login alert is followed by activity from a TOR IP address and impossible travel activity, both strong indicators of compromise. You might even see that the same user performed a mass download activity, which is often an indicator of the attacker performing exfiltration of data. It's things like that that you can explore in Office 365 Cloud App Security to view and triage your alerts, and take action where needed.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="14ad6-194">後續步驟</span><span class="sxs-lookup"><span data-stu-id="14ad6-194">Next steps</span></span>

- [<span data-ttu-id="14ad6-195">部署 Office 365 應用程式的設定格式化的條件的 Access 應用程式控制項</span><span class="sxs-lookup"><span data-stu-id="14ad6-195">Deploy Conditional Access App Control for Office 365 apps</span></span>](ocas-deploy-conditional-access-app-control.md)

- [<span data-ttu-id="14ad6-196">群組簡化管理 IP 位址</span><span class="sxs-lookup"><span data-stu-id="14ad6-196">Group your IP addresses to simplify management</span></span>](group-your-ip-addresses-in-ocas.md)

- [<span data-ttu-id="14ad6-197">整合 SIEM server</span><span class="sxs-lookup"><span data-stu-id="14ad6-197">Integrate your SIEM server</span></span>](integrate-your-siem-server-with-office-365-cas.md)
    
- [<span data-ttu-id="14ad6-198">檢閱並採取行動提醒</span><span class="sxs-lookup"><span data-stu-id="14ad6-198">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
    

