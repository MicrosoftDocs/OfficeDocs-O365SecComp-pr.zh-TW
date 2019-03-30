---
title: Overview of Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/22/2019
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 81f0ee9a-9645-45ab-ba56-de9cbccab475
description: 'Office 365 雲端 App 安全性可讓您深入了解可疑的活動在 Office 365 中，您可以調查可能有問題且，如有需要採取動作來解決安全性問題的情況。 '
ms.openlocfilehash: 960e4c75a4da13e1a0365f75d290cd18587abd58
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2019
ms.locfileid: "31001206"
---
# <a name="overview-of-office-365-cloud-app-security"></a><span data-ttu-id="f251b-103">Overview of Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f251b-103">Overview of Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="f251b-104">評估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="f251b-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="f251b-105">規劃 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="f251b-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="f251b-106">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="f251b-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="f251b-107">使用率 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="f251b-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f251b-108">您在此處 ！</span><span class="sxs-lookup"><span data-stu-id="f251b-108">You are here!</span></span>  <br/> [<span data-ttu-id="f251b-109">下一步</span><span class="sxs-lookup"><span data-stu-id="f251b-109">Next step</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="f251b-110">開始規劃</span><span class="sxs-lookup"><span data-stu-id="f251b-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="f251b-111">開始部署</span><span class="sxs-lookup"><span data-stu-id="f251b-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |[<span data-ttu-id="f251b-112">開始使用</span><span class="sxs-lookup"><span data-stu-id="f251b-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
> [!NOTE]
> <span data-ttu-id="f251b-113">Office 365 雲端 App 安全性是在 Office 365 企業版 E5。</span><span class="sxs-lookup"><span data-stu-id="f251b-113">Office 365 Cloud App Security is available in Office 365 Enterprise E5.</span></span> <span data-ttu-id="f251b-114">如果您的組織要使用另一個 Office 365 企業版訂閱，能以附加元件形式購買 Office 365 雲端 App 安全性。</span><span class="sxs-lookup"><span data-stu-id="f251b-114">If your organization is using another Office 365 Enterprise subscription, Office 365 Cloud App Security can be purchased as an add-on.</span></span> <span data-ttu-id="f251b-115">(以全域管理員，在 Microsoft 365 系統管理中心中，選擇 [**計費** \> **新增訂閱**。)如需詳細資訊，請參閱[Office 365 平台服務說明： Office 365 安全性&amp;合規性中心](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)並[購買或編輯商務用 Office 365 的附加元件](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on)。</span><span class="sxs-lookup"><span data-stu-id="f251b-115">(As a global administrator, in the Microsoft 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) and [Buy or edit an add-on for Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on).</span></span> 
  
<span data-ttu-id="f251b-116">Office 365 雲端 App 安全性能讓您洞悉可疑活動在 Office 365 中，您可以調查可能有問題且，如有需要採取動作來解決安全性問題的情況。</span><span class="sxs-lookup"><span data-stu-id="f251b-116">Office 365 Cloud App Security gives you insight into suspicious activity in Office 365 so you can investigate situations that are potentially problematic and, if needed, take action to address security issues.</span></span> <span data-ttu-id="f251b-117">與 Office 365 雲端 App 安全性，您可以接收的典型或可疑活動的觸發警示的通知，請參閱 < 如何在 Office 365 中的貴組織的資料存取和使用，暫停一直發生可疑活動的使用者帳戶，且需要當使用者在登入 Office 365 應用程式之後觸發警示。</span><span class="sxs-lookup"><span data-stu-id="f251b-117">With Office 365 Cloud App Security, you can receive notifications of triggered alerts for atypical or suspicious activities, see how your organization's data in Office 365 is accessed and used, suspend user accounts exhibiting suspicious activity, and require users to log back in to Office 365 apps after an alert has been triggered.</span></span> <span data-ttu-id="f251b-118">閱讀本篇文章以取得 Office 365 雲端 App 安全性功能的概觀。</span><span class="sxs-lookup"><span data-stu-id="f251b-118">Read this article to get an overview of Office 365 Cloud App Security features and capabilities.</span></span>
  
    
## <a name="how-to-find-the-office-365-cloud-app-security-portal"></a><span data-ttu-id="f251b-119">如何尋找 Office 365 雲端 App 安全性入口網站</span><span class="sxs-lookup"><span data-stu-id="f251b-119">How to find the Office 365 Cloud App Security portal</span></span>

> [!NOTE]
> <span data-ttu-id="f251b-120">若要存取 Office 365 雲端 App 安全性入口網站，您必須是 Office 365 全域系統管理員、 安全性系統管理員或安全性讀取者。</span><span class="sxs-lookup"><span data-stu-id="f251b-120">To access the Office 365 Cloud App Security portal, you must be an Office 365 global administrator, security administrator, or security reader.</span></span> <span data-ttu-id="f251b-121">若要深入了解，請參閱[中 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="f251b-121">To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
<span data-ttu-id="f251b-122">您可以透過 Office 365 雲端 App 安全性入口網站以移至[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)與登入。</span><span class="sxs-lookup"><span data-stu-id="f251b-122">You can get to the Office 365 Cloud App Security portal by going to [https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com) and signing in.</span></span> 

<span data-ttu-id="f251b-123">您也可以取得那里從 Office 365 安全性&amp;合規性中心。</span><span class="sxs-lookup"><span data-stu-id="f251b-123">You can also get there from the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="f251b-124">以下是一個很好的方法：</span><span class="sxs-lookup"><span data-stu-id="f251b-124">Here's one good way to do it:</span></span>
  
1. <span data-ttu-id="f251b-125">移至 [[https://protection.office.com](https://protection.office.com)和 Office 365 使用公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="f251b-125">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365.</span></span> <span data-ttu-id="f251b-126">(這會帶您前往安全性&amp;合規性中心。)</span><span class="sxs-lookup"><span data-stu-id="f251b-126">(This takes you to the Security &amp; Compliance Center.)</span></span>
    
2. <span data-ttu-id="f251b-127">安全性&amp;合規性中心，選擇 [**提醒** \> **管理進階提醒**。</span><span class="sxs-lookup"><span data-stu-id="f251b-127">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span> <br/><span data-ttu-id="f251b-128">![選擇 [管理進階提醒移至 Office 365 雲端 App 安全性](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span><span class="sxs-lookup"><span data-stu-id="f251b-128">![Choose Manage Advanced Alerts to go to Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span></span><br/><span data-ttu-id="f251b-129">（如果尚未啟用 Office 365 雲端 App 安全性，而您是全域系統管理員，[開啟 [Office 365 雲端 App 安全性](turn-on-office-365-cas.md)）。</span><span class="sxs-lookup"><span data-stu-id="f251b-129">(If Office 365 Cloud App Security is not yet enabled, and you are a global administrator, [turn on Office 365 Cloud App Security](turn-on-office-365-cas.md).)</span></span>
    
3. <span data-ttu-id="f251b-130">選擇 [**移至 Office 365 雲端 App 安全性**。</span><span class="sxs-lookup"><span data-stu-id="f251b-130">Choose **Go to Office 365 Cloud App Security**.</span></span> 
    
## <a name="policies"></a><span data-ttu-id="f251b-131">原則</span><span class="sxs-lookup"><span data-stu-id="f251b-131">Policies</span></span>

<span data-ttu-id="f251b-132">Office 365 雲端 App 安全性適用於為組織定義的原則。</span><span class="sxs-lookup"><span data-stu-id="f251b-132">Office 365 Cloud App Security works with the policies that are defined for your organization.</span></span> <span data-ttu-id="f251b-133">與 Office 365 雲端 App 安全性，您的組織會取得許多預先定義的異常偵測原則及數個活動原則範本。</span><span class="sxs-lookup"><span data-stu-id="f251b-133">With Office 365 Cloud App Security, your organization gets many predefined anomaly detection policies and several templates for activity policies.</span></span> <span data-ttu-id="f251b-134">這些原則被設計用於偵測一般異常行為，找出使用者登入風險的 IP 位址從、 偵測勒索軟體活動，偵測從非公司的 IP 位址和更多的系統管理員活動。</span><span class="sxs-lookup"><span data-stu-id="f251b-134">These policies are designed to detect general anomalies, identify users logging in from a risky IP address, detect ransomware activities, detect administrator activities from non-corporate IP addresses, and more.</span></span>
  
![在 CAS 入口網站中，選擇 [控制項]\>若要檢視或建立原則範本的範本](media/88f615b4-aa8a-480c-b239-323dfcd628e1.png)
  
<span data-ttu-id="f251b-136">檢視/使用原則範本，在 Office 365 雲端 App 安全性入口網站，移至**控制項** \> **範本**。</span><span class="sxs-lookup"><span data-stu-id="f251b-136">To view/use policy templates, in the Office 365 Cloud App Security portal, go to **Control** \> **Templates**.</span></span> 
  
![在 O365 CAS 入口網站中，選擇控制項](media/287c2ea9-5172-4697-8e0e-b9ab654105bc.png)
  
<span data-ttu-id="f251b-138">若要深入了解關於原則的詳細資訊，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="f251b-138">To learn more about policies, see the following resources:</span></span>
  
- [<span data-ttu-id="f251b-139">Office 365 雲端 App 安全性中的活動原則和警訊</span><span class="sxs-lookup"><span data-stu-id="f251b-139">Activity policies and alerts in Office 365 Cloud App Security</span></span>](activity-policies-and-alerts.md)
    
- [<span data-ttu-id="f251b-140">Office 365 雲端 App 安全性中的異常偵測原則</span><span class="sxs-lookup"><span data-stu-id="f251b-140">Anomaly detection policies in Office 365 Cloud App Security</span></span>](anomaly-detection-policies-in-ocas.md)
    
## <a name="alerts"></a><span data-ttu-id="f251b-141">警示</span><span class="sxs-lookup"><span data-stu-id="f251b-141">Alerts</span></span>

<span data-ttu-id="f251b-142">當已定義原則時，提醒通知您所偵測到可疑或典型活動。</span><span class="sxs-lookup"><span data-stu-id="f251b-142">When policies are defined, alerts notify you about suspicious or atypical activities that were detected.</span></span> <span data-ttu-id="f251b-143">若要檢視您組織的提醒，請選擇**提醒**在導覽列中跨螢幕頂端。</span><span class="sxs-lookup"><span data-stu-id="f251b-143">To view alerts for your organization, choose **Alerts** in the navigation bar across the top of the screen.</span></span> 
  
![在 [提醒] 頁面中，您可以看到所觸發的警示和採取任何動作。](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)
  
<span data-ttu-id="f251b-145">為會觸發警訊您可以檢閱若要深入了解什麼事。</span><span class="sxs-lookup"><span data-stu-id="f251b-145">As alerts are triggered you can review them to learn more about what is going on.</span></span> <span data-ttu-id="f251b-146">然後，如果仍然可疑活動，您可以採取動作。</span><span class="sxs-lookup"><span data-stu-id="f251b-146">Then, if the activity is still suspicious, you can take action.</span></span> <span data-ttu-id="f251b-147">例如，您可以通知使用者有關的問題，暫停從登入 Office 365 使用者或要求使用者在登入 Office 365 應用程式。</span><span class="sxs-lookup"><span data-stu-id="f251b-147">For example, you can notify a user about an issue, suspend a user from signing in to Office 365, or require a user to sign back in to Office 365 apps.</span></span>
  
<span data-ttu-id="f251b-148">若要深入了解提醒，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="f251b-148">To learn more about alerts, see the following resources:</span></span>
  
- [<span data-ttu-id="f251b-149">Office 365 雲端 App 安全性中的活動原則和警訊</span><span class="sxs-lookup"><span data-stu-id="f251b-149">Activity policies and alerts in Office 365 Cloud App Security</span></span>](activity-policies-and-alerts.md)
    
- [<span data-ttu-id="f251b-150">Office 365 雲端 App 安全性中的異常偵測原則</span><span class="sxs-lookup"><span data-stu-id="f251b-150">Anomaly detection policies in Office 365 Cloud App Security</span></span>](anomaly-detection-policies-in-ocas.md)
    
- [<span data-ttu-id="f251b-151">檢閱並對 Office 365 雲端 App 安全性警示採取動作</span><span class="sxs-lookup"><span data-stu-id="f251b-151">Review and take action on Office 365 Cloud App Security alerts</span></span>](review-office-365-cas-alerts.md)
    
## <a name="activity-logs"></a><span data-ttu-id="f251b-152">活動記錄檔</span><span class="sxs-lookup"><span data-stu-id="f251b-152">Activity logs</span></span>

<span data-ttu-id="f251b-153">在活動記錄檔] 頁面上，Office 365 雲端 App 安全性中檢視使用者活動的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f251b-153">View information about user activities on your Activity log page in Office 365 Cloud App Security.</span></span>
  
![在 O365 CAS 入口網站中，選擇 [Investigate\>活動記錄檔](media/ec19e77d-4e11-49fc-ab7c-0e8b0c29c93c.png)
  
<span data-ttu-id="f251b-155">若要前往此頁面上，在 Office 365 雲端 App 安全性入口網站中，前往 [**調查** \> **活動記錄檔**。</span><span class="sxs-lookup"><span data-stu-id="f251b-155">To get to this page, in the Office 365 Cloud App Security portal, go to **Investigate** \> **Activity log**.</span></span> 
  
![在 O365 CAS 入口網站中，選擇 [調查]。](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
<span data-ttu-id="f251b-157">您可以使用 Office 365 雲端 App 安全性，太使用您網站的流量記錄。</span><span class="sxs-lookup"><span data-stu-id="f251b-157">You can use your web traffic logs with Office 365 Cloud App Security, too.</span></span> <span data-ttu-id="f251b-158">更多詳細資料中所包含的記錄檔，您將有較佳的可見性使用者活動。</span><span class="sxs-lookup"><span data-stu-id="f251b-158">The more details that are included in those log files, the better visibility you'll have into user activity.</span></span> <span data-ttu-id="f251b-159">您可以使用從 Barracuda、 藍色外覆、 檢查點、 Cisco、 Clavister、 Dell SonicWALL、 Fortinet、 杜、 McAfee、 Microsoft、 Palo 琴奧圖、 Sophos、 Squid、 Websence、 Zscaler，和更多的記錄檔。</span><span class="sxs-lookup"><span data-stu-id="f251b-159">You can use log files from Barracuda, Blue Coat, Check Point, Cisco, Clavister, Dell SonicWALL, Fortinet, Juniper, McAfee, Microsoft, Palo Alto, Sophos, Squid, Websence, Zscaler, and more.</span></span>
  
[<span data-ttu-id="f251b-160">了解網頁流量記錄檔與資料來源的 Office 365 雲端 App 安全性</span><span class="sxs-lookup"><span data-stu-id="f251b-160">Learn about web traffic logs and data sources for Office 365 Cloud App Security</span></span>](web-traffic-logs-and-data-sources-for-ocas.md)
  
## <a name="oauth-apps"></a><span data-ttu-id="f251b-161">OAuth 應用程式</span><span class="sxs-lookup"><span data-stu-id="f251b-161">OAuth apps</span></span>

<span data-ttu-id="f251b-162">與 Office 365 雲端 App 安全性，您可以允許或防止您的組織使用協力廠商應用程式存取 Office 365 中的資料中的人員。</span><span class="sxs-lookup"><span data-stu-id="f251b-162">With Office 365 Cloud App Security, you can allow or prevent people in your organization to use third-party apps that access data in Office 365.</span></span>
  
![O365 CAS 中您可以從調查] 功能表存取 [管理 OAuth 應用程式] 頁面。](media/78272cda-986f-4b3b-bbbe-8c236c74f5d3.png)
  
<span data-ttu-id="f251b-164">若要前往此頁面上，移至**Investigate** \> **OAuth 應用程式**。</span><span class="sxs-lookup"><span data-stu-id="f251b-164">To get to this page, go to **Investigate** \> **OAuth apps**.</span></span> 
  
![在 O365 CAS 入口網站中，選擇 [調查]。](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
[<span data-ttu-id="f251b-166">使用 Office 365 雲端 App 安全性管理 OAuth 應用程式</span><span class="sxs-lookup"><span data-stu-id="f251b-166">Manage OAuth apps using Office 365 Cloud App Security</span></span>](manage-app-permissions-in-ocas.md)
  
## <a name="cloud-discovery-dashboard"></a><span data-ttu-id="f251b-167">雲端探索儀表板</span><span class="sxs-lookup"><span data-stu-id="f251b-167">Cloud Discovery Dashboard</span></span>

<span data-ttu-id="f251b-168">**雲端探索儀表板**，也稱為**產能應用程式探索**，顯示組織內的雲端應用程式使用狀況的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f251b-168">The **Cloud Discovery Dashboard**, also referred to as **Productivity App Discovery**, shows information about cloud app usage within your organization.</span></span> <span data-ttu-id="f251b-169">您可以檢視應用程式、 使用者、 流量、 交易，並請使用此儀表板的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f251b-169">You can view information about apps, users, traffic, transactions, and more using this dashboard.</span></span> <span data-ttu-id="f251b-170">在雲端探索儀表板的格式類似於下列影像：</span><span class="sxs-lookup"><span data-stu-id="f251b-170">The Cloud Discovery Dashboard resembles the following image:</span></span> 
  
![在 Office 365 CAS 入口網站中，選擇 [探索\>雲端探索儀表板](media/61269290-fd82-4d4b-8045-aea1ebc82287.png)
  
<span data-ttu-id="f251b-172">若要取得此儀表板，在 Office 365 雲端 App 安全性入口網站中，前往 [**探索** \> **雲端探索儀表板**。</span><span class="sxs-lookup"><span data-stu-id="f251b-172">To get to this dashboard, in the Office 365 Cloud App Security portal, go to **Discover** \> **Cloud Discovery dashboard**.</span></span> 
  
![在 Office 365 CAS 入口網站中，選擇 [探索](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
[<span data-ttu-id="f251b-174">檢閱 Office 365 雲端 App 安全性中的 App 探索結果</span><span class="sxs-lookup"><span data-stu-id="f251b-174">Review app discovery findings in Office 365 Cloud App Security</span></span>](review-app-discovery-findings-in-ocas.md)
  
## <a name="next-steps"></a><span data-ttu-id="f251b-175">後續步驟</span><span class="sxs-lookup"><span data-stu-id="f251b-175">Next steps</span></span>

- <span data-ttu-id="f251b-176">取得[Office 365 雲端 App 安全性使用情況和使用狀況指南](https://aka.ms/O365CASGuide)</span><span class="sxs-lookup"><span data-stu-id="f251b-176">Get the [Office 365 Cloud App Security Use Cases and Usage Guide](https://aka.ms/O365CASGuide)</span></span>
    
- [<span data-ttu-id="f251b-177">準備好使用 Office 365 雲端 App 安全性</span><span class="sxs-lookup"><span data-stu-id="f251b-177">Get ready for Office 365 Cloud App Security</span></span>](get-ready-for-office-365-cas.md)
    

