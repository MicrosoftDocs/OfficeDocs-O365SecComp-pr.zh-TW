---
title: Office 365 雲端 App 安全性概觀
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/22/2019
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 81f0ee9a-9645-45ab-ba56-de9cbccab475
description: 'Office 365 雲端應用程式安全性可讓您算可疑活動在 Office 365 中讓您可以調查可能有問題且，如果需要採取動作可解決安全性問題的情況。 '
ms.openlocfilehash: edce16edca822bed30c78f34cf141b23f2b2fb8c
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2019
ms.locfileid: "29382546"
---
# <a name="overview-of-office-365-cloud-app-security"></a><span data-ttu-id="d47c4-103">Office 365 雲端 App 安全性概觀</span><span class="sxs-lookup"><span data-stu-id="d47c4-103">Overview of Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="d47c4-104">評估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="d47c4-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="d47c4-105">規劃 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="d47c4-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="d47c4-106">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="d47c4-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="d47c4-107">使用率 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="d47c4-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d47c4-108">您在此處 ！</span><span class="sxs-lookup"><span data-stu-id="d47c4-108">You are here!</span></span>  <br/> [<span data-ttu-id="d47c4-109">下一步</span><span class="sxs-lookup"><span data-stu-id="d47c4-109">Next step</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="d47c4-110">開始規劃</span><span class="sxs-lookup"><span data-stu-id="d47c4-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="d47c4-111">開始部署</span><span class="sxs-lookup"><span data-stu-id="d47c4-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |[<span data-ttu-id="d47c4-112">開始使用</span><span class="sxs-lookup"><span data-stu-id="d47c4-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
> [!NOTE]
> <span data-ttu-id="d47c4-p101">在 Office 365 企業版 E5 中使用 office 365 雲端應用程式安全性。如果貴組織要使用另一個 Office 365 企業版訂閱，可做為附加元件購買 Office 365 雲端應用程式安全性。(全域管理員在 Office 365 系統管理中心中，選擇 [**計費** \> **新增訂閱**。)如需詳細資訊，請參閱[Office 365 平台服務說明： Office 365 安全性&amp;規範中心](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)和[購買或編輯企業版的 Office 365 的附加元件](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on)。</span><span class="sxs-lookup"><span data-stu-id="d47c4-p101">Office 365 Cloud App Security is available in Office 365 Enterprise E5. If your organization is using another Office 365 Enterprise subscription, Office 365 Cloud App Security can be purchased as an add-on. (As a global administrator, in the Office 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) and [Buy or edit an add-on for Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on).</span></span> 
  
<span data-ttu-id="d47c4-p102">Office 365 雲端應用程式安全性可讓您深入了解可疑活動在 Office 365 中讓您可以調查可能有問題且，如果需要採取動作可解決安全性問題的情況。與 Office 365 雲端應用程式安全性] 您可以接收通知的公休或可疑活動的觸發提醒，請參閱如何在 Office 365 組織的資料是存取和使用擱置呈現可疑活動的使用者帳戶，且需要若要重新登入 Office 365 應用程式之後觸發通知使用者。請閱讀本篇文章以取得 Office 365 雲端應用程式安全性特性與功能的概觀。</span><span class="sxs-lookup"><span data-stu-id="d47c4-p102">Office 365 Cloud App Security gives you insight into suspicious activity in Office 365 so you can investigate situations that are potentially problematic and, if needed, take action to address security issues. With Office 365 Cloud App Security, you can receive notifications of triggered alerts for atypical or suspicious activities, see how your organization's data in Office 365 is accessed and used, suspend user accounts exhibiting suspicious activity, and require users to log back in to Office 365 apps after an alert has been triggered. Read this article to get an overview of Office 365 Cloud App Security features and capabilities.</span></span>
  
    
## <a name="how-to-find-the-office-365-cloud-app-security-portal"></a><span data-ttu-id="d47c4-119">如何尋找 Office 365 雲端應用程式安全性入口網站</span><span class="sxs-lookup"><span data-stu-id="d47c4-119">How to find the Office 365 Cloud App Security portal</span></span>

> [!NOTE]
> <span data-ttu-id="d47c4-p103">若要存取 Office 365 雲端應用程式安全性入口網站，您必須是 Office 365 全域管理員、 安全性管理員或安全性讀者。若要深入了解，請參閱[Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="d47c4-p103">To access the Office 365 Cloud App Security portal, you must be an Office 365 global administrator, security administrator, or security reader. To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
<span data-ttu-id="d47c4-122">您可以取得 Office 365 雲端應用程式安全性入口網站移至[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)及登入。</span><span class="sxs-lookup"><span data-stu-id="d47c4-122">You can get to the Office 365 Cloud App Security portal by going to [https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com) and signing in.</span></span> 

<span data-ttu-id="d47c4-p104">您也可以取得那里從 Office 365 安全性&amp;規範中心。以下是執行它的其中一個好方法：</span><span class="sxs-lookup"><span data-stu-id="d47c4-p104">You can also get there from the Office 365 Security &amp; Compliance Center. Here's one good way to do it:</span></span>
  
1. <span data-ttu-id="d47c4-p105">移至 [[https://protection.office.com](https://protection.office.com)及使用 Office 365 工作或學校帳戶登入。(這會引導您安全性&amp;規範中心。)</span><span class="sxs-lookup"><span data-stu-id="d47c4-p105">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. (This takes you to the Security &amp; Compliance Center.)</span></span>
    
2. <span data-ttu-id="d47c4-127">安全性&amp;規範中心選擇**提醒** \> **管理進階提醒**。</span><span class="sxs-lookup"><span data-stu-id="d47c4-127">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span> <br/><span data-ttu-id="d47c4-128">![選擇 [管理進階警告移至 Office 365 雲端應用程式安全性](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span><span class="sxs-lookup"><span data-stu-id="d47c4-128">![Choose Manage Advanced Alerts to go to Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span></span><br/><span data-ttu-id="d47c4-129">（如果尚未未啟用 Office 365 雲端應用程式安全性，而且會[開啟 [Office 365 雲端應用程式安全性](turn-on-office-365-cas.md)全域系統管理員）。</span><span class="sxs-lookup"><span data-stu-id="d47c4-129">(If Office 365 Cloud App Security is not yet enabled, and you are a global administrator, [turn on Office 365 Cloud App Security](turn-on-office-365-cas.md).)</span></span>
    
3. <span data-ttu-id="d47c4-130">選擇 [**移至 Office 365 的雲端應用程式安全性**]。</span><span class="sxs-lookup"><span data-stu-id="d47c4-130">Choose **Go to Office 365 Cloud App Security**.</span></span> 
    
## <a name="policies"></a><span data-ttu-id="d47c4-131">Policies</span><span class="sxs-lookup"><span data-stu-id="d47c4-131">Policies</span></span>

<span data-ttu-id="d47c4-p106">Office 365 雲端應用程式安全性適用於您組織所定義的原則。與 Office 365 雲端應用程式安全性]，您的組織會取得許多預先定義的異常偵測原則與數個活動的原則範本。這些原則的設計被用來偵測一般異常、 識別 risky 的 IP 位址從登入的使用者、 偵測 ransomware 活動、 偵測來自非公司的 IP 位址和更多的系統管理員活動。</span><span class="sxs-lookup"><span data-stu-id="d47c4-p106">Office 365 Cloud App Security works with the policies that are defined for your organization. With Office 365 Cloud App Security, your organization gets many predefined anomaly detection policies and several templates for activity policies. These policies are designed to detect general anomalies, identify users logging in from a risky IP address, detect ransomware activities, detect administrator activities from non-corporate IP addresses, and more.</span></span>
  
![CAS 入口網站中選擇 [控制\>來檢視或建立原則範本的範本](media/88f615b4-aa8a-480c-b239-323dfcd628e1.png)
  
<span data-ttu-id="d47c4-136">檢視/使用中的 Office 365 雲端應用程式安全性入口網站原則範本，請移至**控制項** \> **範本**。</span><span class="sxs-lookup"><span data-stu-id="d47c4-136">To view/use policy templates, in the Office 365 Cloud App Security portal, go to **Control** \> **Templates**.</span></span> 
  
![在 O365 CAS 入口網站中選擇控制項](media/287c2ea9-5172-4697-8e0e-b9ab654105bc.png)
  
<span data-ttu-id="d47c4-138">若要深入了解原則，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="d47c4-138">To learn more about policies, see the following resources:</span></span>
  
- [<span data-ttu-id="d47c4-139">Office 365 雲端 App 安全性中的活動原則和警訊</span><span class="sxs-lookup"><span data-stu-id="d47c4-139">Activity policies and alerts in Office 365 Cloud App Security</span></span>](activity-policies-and-alerts.md)
    
- [<span data-ttu-id="d47c4-140">Office 365 雲端 App 安全性中的異常偵測原則</span><span class="sxs-lookup"><span data-stu-id="d47c4-140">Anomaly detection policies in Office 365 Cloud App Security</span></span>](anomaly-detection-policies-in-ocas.md)
    
## <a name="alerts"></a><span data-ttu-id="d47c4-141">警報</span><span class="sxs-lookup"><span data-stu-id="d47c4-141">Alerts</span></span>

<span data-ttu-id="d47c4-p107">時所定義的原則，提醒通知您需可疑或公休所偵測到的活動。若要檢視您組織的提醒，請選擇**提醒**導覽列中不同螢幕頂端。</span><span class="sxs-lookup"><span data-stu-id="d47c4-p107">When policies are defined, alerts notify you about suspicious or atypical activities that were detected. To view alerts for your organization, choose **Alerts** in the navigation bar across the top of the screen.</span></span> 
  
![在 [提醒] 頁面中，您可以看到所觸發的警告與採取任何動作。](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)
  
<span data-ttu-id="d47c4-p108">當觸發提醒您可以檢閱若要深入了解的項目將要。然後，若仍可疑活動，您可以採取動作。例如，您可以通知使用者有關問題，暫停登入 Office 365 中的使用者或需要使用者再次登入 Office 365 應用程式。</span><span class="sxs-lookup"><span data-stu-id="d47c4-p108">As alerts are triggered you can review them to learn more about what is going on. Then, if the activity is still suspicious, you can take action. For example, you can notify a user about an issue, suspend a user from signing in to Office 365, or require a user to sign back in to Office 365 apps.</span></span>
  
<span data-ttu-id="d47c4-148">若要深入了解提醒，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="d47c4-148">To learn more about alerts, see the following resources:</span></span>
  
- [<span data-ttu-id="d47c4-149">Office 365 雲端 App 安全性中的活動原則和警訊</span><span class="sxs-lookup"><span data-stu-id="d47c4-149">Activity policies and alerts in Office 365 Cloud App Security</span></span>](activity-policies-and-alerts.md)
    
- [<span data-ttu-id="d47c4-150">Office 365 雲端 App 安全性中的異常偵測原則</span><span class="sxs-lookup"><span data-stu-id="d47c4-150">Anomaly detection policies in Office 365 Cloud App Security</span></span>](anomaly-detection-policies-in-ocas.md)
    
- [<span data-ttu-id="d47c4-151">檢閱並在 Office 365 雲端應用程式安全性警訊採取動作</span><span class="sxs-lookup"><span data-stu-id="d47c4-151">Review and take action on Office 365 Cloud App Security alerts</span></span>](review-office-365-cas-alerts.md)
    
## <a name="activity-logs"></a><span data-ttu-id="d47c4-152">活動記錄檔</span><span class="sxs-lookup"><span data-stu-id="d47c4-152">Activity logs</span></span>

<span data-ttu-id="d47c4-153">在 Office 365 雲端應用程式安全性您活動記錄檔] 頁面上檢視使用者活動的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d47c4-153">View information about user activities on your Activity log page in Office 365 Cloud App Security.</span></span>
  
![在 O365 CAS 入口網站中選擇 [調查\>活動記錄檔](media/ec19e77d-4e11-49fc-ab7c-0e8b0c29c93c.png)
  
<span data-ttu-id="d47c4-155">若要取得這個] 頁面上，在 Office 365 雲端應用程式安全性入口網站中移至**調查** \> **活動記錄檔**。</span><span class="sxs-lookup"><span data-stu-id="d47c4-155">To get to this page, in the Office 365 Cloud App Security portal, go to **Investigate** \> **Activity log**.</span></span> 
  
![在 O365 CAS 入口網站中選擇 [調查]。](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
<span data-ttu-id="d47c4-p109">您可以使用 web 流量記錄檔太與 Office 365 雲端應用程式安全性]。更多詳細資料中所包含的記錄檔，必須將使用者活動的較佳的可見性。您可以使用 Barracuda、 藍色外覆、 檢查點、 Cisco、 Clavister、 Dell SonicWALL、 Fortinet、 Juniper、 McAfee、 Microsoft、 Palo Alto、 Sophos、 Squid、 Websence、 Zscaler、 及更多的記錄檔案。</span><span class="sxs-lookup"><span data-stu-id="d47c4-p109">You can use your web traffic logs with Office 365 Cloud App Security, too. The more details that are included in those log files, the better visibility you'll have into user activity. You can use log files from Barracuda, Blue Coat, Check Point, Cisco, Clavister, Dell SonicWALL, Fortinet, Juniper, McAfee, Microsoft, Palo Alto, Sophos, Squid, Websence, Zscaler, and more.</span></span>
  
[<span data-ttu-id="d47c4-160">了解網頁流量記錄檔與資料來源的 Office 365 雲端應用程式安全性</span><span class="sxs-lookup"><span data-stu-id="d47c4-160">Learn about web traffic logs and data sources for Office 365 Cloud App Security</span></span>](web-traffic-logs-and-data-sources-for-ocas.md)
  
## <a name="oauth-apps"></a><span data-ttu-id="d47c4-161">OAuth 應用程式</span><span class="sxs-lookup"><span data-stu-id="d47c4-161">OAuth apps</span></span>

<span data-ttu-id="d47c4-162">與 Office 365 雲端應用程式安全性]，您可以允許或防止使用協力廠商應用程式存取 Office 365 中的資料在組織中的人員。</span><span class="sxs-lookup"><span data-stu-id="d47c4-162">With Office 365 Cloud App Security, you can allow or prevent people in your organization to use third-party apps that access data in Office 365.</span></span>
  
![O365 CAS 中您可以從調查] 功能表存取 [管理 OAuth 應用程式] 頁面。](media/78272cda-986f-4b3b-bbbe-8c236c74f5d3.png)
  
<span data-ttu-id="d47c4-164">若要取得這個] 頁面上，移至**調查** \> **OAuth 應用程式**。</span><span class="sxs-lookup"><span data-stu-id="d47c4-164">To get to this page, go to **Investigate** \> **OAuth apps**.</span></span> 
  
![在 O365 CAS 入口網站中選擇 [調查]。](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
[<span data-ttu-id="d47c4-166">使用 Office 365 雲端 App 安全性管理 OAuth 應用程式</span><span class="sxs-lookup"><span data-stu-id="d47c4-166">Manage OAuth apps using Office 365 Cloud App Security</span></span>](manage-app-permissions-in-ocas.md)
  
## <a name="cloud-discovery-dashboard"></a><span data-ttu-id="d47c4-167">雲端探索儀表板</span><span class="sxs-lookup"><span data-stu-id="d47c4-167">Cloud Discovery Dashboard</span></span>

<span data-ttu-id="d47c4-p110">**雲端探索儀表板**，又稱為**產能應用程式探索**，顯示組織內的雲端應用程式使用方式的相關資訊。您可以檢視應用程式、 使用者、 流量、 交易，以及其他使用此儀表板的相關資訊。雲端探索儀表板的格式類似於下列影像：</span><span class="sxs-lookup"><span data-stu-id="d47c4-p110">The **Cloud Discovery Dashboard**, also referred to as **Productivity App Discovery**, shows information about cloud app usage within your organization. You can view information about apps, users, traffic, transactions, and more using this dashboard. The Cloud Discovery Dashboard resembles the following image:</span></span> 
  
![在 Office 365 CAS 入口網站中選擇 [搜索\>雲端探索儀表板](media/61269290-fd82-4d4b-8045-aea1ebc82287.png)
  
<span data-ttu-id="d47c4-172">若要取得此儀表板，在 Office 365 雲端應用程式安全性入口網站中移至 [**搜索** \> **雲端探索儀表板**。</span><span class="sxs-lookup"><span data-stu-id="d47c4-172">To get to this dashboard, in the Office 365 Cloud App Security portal, go to **Discover** \> **Cloud Discovery dashboard**.</span></span> 
  
![在 Office 365 CAS 入口網站中選擇 [搜索](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
[<span data-ttu-id="d47c4-174">檢閱 Office 365 雲端 App 安全性中的 App 探索結果</span><span class="sxs-lookup"><span data-stu-id="d47c4-174">Review app discovery findings in Office 365 Cloud App Security</span></span>](review-app-discovery-findings-in-ocas.md)
  
## <a name="next-steps"></a><span data-ttu-id="d47c4-175">後續步驟</span><span class="sxs-lookup"><span data-stu-id="d47c4-175">Next steps</span></span>

- <span data-ttu-id="d47c4-176">取得[Office 365 雲端應用程式安全性使用案例] 和 [使用狀況指南](https://aka.ms/O365CASGuide)</span><span class="sxs-lookup"><span data-stu-id="d47c4-176">Get the [Office 365 Cloud App Security Use Cases and Usage Guide](https://aka.ms/O365CASGuide)</span></span>
    
- [<span data-ttu-id="d47c4-177">準備好使用 Office 365 雲端 App 安全性</span><span class="sxs-lookup"><span data-stu-id="d47c4-177">Get ready for Office 365 Cloud App Security</span></span>](get-ready-for-office-365-cas.md)
    

