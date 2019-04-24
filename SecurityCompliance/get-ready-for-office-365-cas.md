---
title: 準備好使用 Office 365 雲端 App 安全性
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.date: 02/15/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: d9ee4d67-f2b3-42b4-9c9e-c4529904990a
description: 開始使用 Office 365 雲端 App 安全性
ms.openlocfilehash: 89718adcbb7c77735db3009937d887e88d4a8bc3
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32254010"
---
# <a name="get-ready-for-office-365-cloud-app-security"></a><span data-ttu-id="88010-103">準備好使用 Office 365 雲端 App 安全性</span><span class="sxs-lookup"><span data-stu-id="88010-103">Get ready for Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="88010-104">評估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="88010-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="88010-105">規劃 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="88010-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="88010-106">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="88010-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="88010-107">使用率 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="88010-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="88010-108">啟動評估</span><span class="sxs-lookup"><span data-stu-id="88010-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |<span data-ttu-id="88010-109">您在此處 ！</span><span class="sxs-lookup"><span data-stu-id="88010-109">You are here!</span></span>  <br/> [<span data-ttu-id="88010-110">下一步</span><span class="sxs-lookup"><span data-stu-id="88010-110">Next step</span></span>](turn-on-office-365-cas.md) <br/> |[<span data-ttu-id="88010-111">開始部署</span><span class="sxs-lookup"><span data-stu-id="88010-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |[<span data-ttu-id="88010-112">開始使用</span><span class="sxs-lookup"><span data-stu-id="88010-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
<span data-ttu-id="88010-113">當您準備來開啟，並為您的組織實作 Office 365 雲端 App 安全性，有一些事項需要考量。</span><span class="sxs-lookup"><span data-stu-id="88010-113">As you prepare to turn on and implement Office 365 Cloud App Security for your organization, there are a few things to take into account.</span></span> <span data-ttu-id="88010-114">使用本文做為指南，規劃 Office 365 雲端 App 安全性。</span><span class="sxs-lookup"><span data-stu-id="88010-114">Use this article as a guide to plan for Office 365 Cloud App Security.</span></span>
    
## <a name="step-1-identify-and-protect-your-global-and-security-administrator-accounts"></a><span data-ttu-id="88010-115">步驟 1： 識別和保護您的全域和安全性系統管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="88010-115">Step 1: Identify and protect your global and security administrator accounts</span></span>

<span data-ttu-id="88010-116">全域系統管理員、 安全性管理員和安全性讀取者可以存取檢視原則、 檢閱提醒，並使用報告在 Office 365 雲端 App 安全性入口網站。</span><span class="sxs-lookup"><span data-stu-id="88010-116">Global administrators, security administrators, and security readers can access the Office 365 Cloud App Security portal to view policies, review alerts, and use reports.</span></span> <span data-ttu-id="88010-117">全域系統管理員和安全性系統管理員可以定義原則，並採取其他動作，以保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="88010-117">Global administrators and security administrators can define policies and take other actions to protect your organization.</span></span> <span data-ttu-id="88010-118">(如需詳細資訊，請參閱[中 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。)檢閱您的組織為了預防萬一，有更高權限的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="88010-118">(For more information, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).) Review your organization's user accounts that have elevated permissions as a precaution.</span></span> 
  
 <span data-ttu-id="88010-119">**[保護您的 Office 365 全域系統管理員帳戶](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)**。</span><span class="sxs-lookup"><span data-stu-id="88010-119">**[Protect your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)**.</span></span> 
  
## <a name="step-2-turn-on-audit-logging-for-your-organization"></a><span data-ttu-id="88010-120">步驟 2： 開啟稽核記錄為您的組織</span><span class="sxs-lookup"><span data-stu-id="88010-120">Step 2: Turn on audit logging for your organization</span></span>

<span data-ttu-id="88010-121">為了讓 Office 365 雲端 App 安全性運作正確，必須先開啟稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="88010-121">In order for Office 365 Cloud App Security to work correct, audit logging must be turned on.</span></span> <span data-ttu-id="88010-122">這通常是由 Exchange Online 的系統管理員或全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="88010-122">This is typically done by an Exchange Online administrator or a global administrator.</span></span>
  
 <span data-ttu-id="88010-123">**[開啟 Office 365 稽核記錄搜尋的開啟或關閉](turn-audit-log-search-on-or-off.md)**。</span><span class="sxs-lookup"><span data-stu-id="88010-123">**[Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md)**.</span></span> 
  
## <a name="step-3-go-to-the-office-365-cloud-app-security-portal"></a><span data-ttu-id="88010-124">步驟 3： 移至 Office 365 雲端 App 安全性入口網站</span><span class="sxs-lookup"><span data-stu-id="88010-124">Step 3: Go to the Office 365 Cloud App Security portal</span></span>

<span data-ttu-id="88010-125">您可以透過 Office 365 雲端 App 安全性入口網站以移至[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)與登入。</span><span class="sxs-lookup"><span data-stu-id="88010-125">You can get to the Office 365 Cloud App Security portal by going to [https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com) and signing in.</span></span> 

<span data-ttu-id="88010-126">您也可以取得那里從 Office 365 安全性&amp;合規性中心。</span><span class="sxs-lookup"><span data-stu-id="88010-126">You can also get there from the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="88010-127">以下是一個很好的方法：</span><span class="sxs-lookup"><span data-stu-id="88010-127">Here's one good way to do it:</span></span>

1. <span data-ttu-id="88010-128">移至 [[https://protection.office.com](https://protection.office.com)並登入。</span><span class="sxs-lookup"><span data-stu-id="88010-128">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="88010-129">(這會帶您前往安全性&amp;合規性中心。)</span><span class="sxs-lookup"><span data-stu-id="88010-129">(This takes you to the Security &amp; Compliance Center.)</span></span>
    
2. <span data-ttu-id="88010-130">前往 [**提醒** \> **管理進階提醒**。</span><span class="sxs-lookup"><span data-stu-id="88010-130">Go to **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="88010-131">選擇 [移至 Office 365 雲端 App 安全性入口網站的 [**移至 Office 365 雲端 App 安全性**。</span><span class="sxs-lookup"><span data-stu-id="88010-131">Choose **Go to Office 365 Cloud App Security** to go to the Office 365 Cloud App Security portal.</span></span><br> <span data-ttu-id="88010-132">![選擇 [管理進階提醒移至 Office 365 雲端 App 安全性](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span><span class="sxs-lookup"><span data-stu-id="88010-132">![Choose Manage Advanced Alerts to go to Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span></span><br><span data-ttu-id="88010-133">當您移至 Office 365 雲端 App 安全性入口網站時，您會看到的第一頁會是下列影像的格式類似於 [原則] 頁面上：</span><span class="sxs-lookup"><span data-stu-id="88010-133">When you go to the Office 365 Cloud App Security portal, the first page you see is the Policies page, which resembles the following image:</span></span><br><span data-ttu-id="88010-134">![當您移至 Office 365 雲端 App 安全性入口網站時，您以啟動 [原則] 頁面](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)</span><span class="sxs-lookup"><span data-stu-id="88010-134">![When you go to the Office 365 Cloud App Security portal, you start with the Policies page](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)</span></span><br>
  
## <a name="step-4-define-policies-and-set-up-alerts-amp-actions"></a><span data-ttu-id="88010-135">步驟 4： 定義原則並設定提醒&amp;動作</span><span class="sxs-lookup"><span data-stu-id="88010-135">Step 4: Define policies and set up alerts &amp; actions</span></span>

<span data-ttu-id="88010-136">全域系統管理員和安全性系統管理員定義原則在 Office 365 雲端 App 安全性中。</span><span class="sxs-lookup"><span data-stu-id="88010-136">Global administrators and security administrators define policies in Office 365 Cloud App Security.</span></span> <span data-ttu-id="88010-137">在定義原則的過程中，警告與動作也會設定。</span><span class="sxs-lookup"><span data-stu-id="88010-137">During the process of defining policies, alerts and actions are also set.</span></span> <span data-ttu-id="88010-138">警示是標準為基礎的通知出現在檢視中或透過電子郵件傳送。</span><span class="sxs-lookup"><span data-stu-id="88010-138">An alert is a criteria-based notification that appears in a view or is sent via email.</span></span> 
  
<span data-ttu-id="88010-139">有兩種類型的 Office 365 雲端 App 安全性中的警示： 偵測到可疑活動的異常偵測警示和活動警訊，所定義的可能是典型組織的活動。</span><span class="sxs-lookup"><span data-stu-id="88010-139">There are two types of alerts in Office 365 Cloud App Security: anomaly detection alerts that detect suspicious activity, and activity alerts, which are defined for activities that might be atypical for your organization.</span></span> <span data-ttu-id="88010-140">Office 365 環境中，是為您的組織不尋常的活動時，警示通知全域系統管理員和安全性系統管理員。</span><span class="sxs-lookup"><span data-stu-id="88010-140">Alerts notify global administrators and security administrators when there's an activity in your Office 365 environment that's unusual for your organization.</span></span>
  
<span data-ttu-id="88010-141">請參閱若要了解更多的下列資源：</span><span class="sxs-lookup"><span data-stu-id="88010-141">See the following resources to learn more:</span></span>
  
- [<span data-ttu-id="88010-142">Office 365 雲端 App 安全性中的活動原則和警訊</span><span class="sxs-lookup"><span data-stu-id="88010-142">Activity policies and alerts in Office 365 Cloud App Security</span></span>](activity-policies-and-alerts.md)
    
- [<span data-ttu-id="88010-143">Office 365 雲端 App 安全性中的異常偵測原則</span><span class="sxs-lookup"><span data-stu-id="88010-143">Anomaly detection policies in Office 365 Cloud App Security</span></span>](anomaly-detection-policies-in-ocas.md)
    
- [<span data-ttu-id="88010-144">檢閱並對 Office 365 雲端 App 安全性警示採取動作</span><span class="sxs-lookup"><span data-stu-id="88010-144">Review and take action on Office 365 Cloud App Security alerts</span></span>](review-office-365-cas-alerts.md)
    

## <a name="step-5-set-up-conditional-access-app-control"></a><span data-ttu-id="88010-145">步驟 5： 設定條件式存取應用程式控制</span><span class="sxs-lookup"><span data-stu-id="88010-145">Step 5: Set up Conditional Access App Control</span></span>

<span data-ttu-id="88010-146">設定和強制執行組織的應用程式，根據特定條件，例如哪些使用者可以使用哪些應用程式上的控制項和位置。</span><span class="sxs-lookup"><span data-stu-id="88010-146">Set up and enforce controls on your organization's apps, based on certain conditions, such as which users can use what apps, and where.</span></span> <span data-ttu-id="88010-147">定義使用者應用程式存取及工作階段原則，以判斷是否機密文件可以下載及加密，封鎖特定應用程式的存取，設定為唯讀模式的特定應用程式]，並將使用者工作階段限制從非公司網路。</span><span class="sxs-lookup"><span data-stu-id="88010-147">Define user app access and session policies to determine whether sensitive documents can be downloaded and encrypted, block access to certain apps, set up read-only mode for certain apps, and restrict user sessions from non-corporate networks.</span></span>

<span data-ttu-id="88010-148">請參閱若要了解更多的下列資源：</span><span class="sxs-lookup"><span data-stu-id="88010-148">See the following resources to learn more:</span></span>

- [<span data-ttu-id="88010-149">使用 Office 365 雲端 App 安全性條件式存取應用程式控制來保護應用程式</span><span class="sxs-lookup"><span data-stu-id="88010-149">Protect apps with Office 365 Cloud App Security Conditional Access App Control</span></span>](ocas-conditional-access-app-control.md)

- [<span data-ttu-id="88010-150">為 Office 365 應用程式部署條件式存取應用程式控制</span><span class="sxs-lookup"><span data-stu-id="88010-150">Deploy Conditional Access App Control for Office 365 apps</span></span>](ocas-deploy-conditional-access-app-control.md)

## <a name="step-6-learn-about-your-organizations-cloud-usage"></a><span data-ttu-id="88010-151">步驟 6︰ 了解貴組織雲端使用方式</span><span class="sxs-lookup"><span data-stu-id="88010-151">Step 6: Learn about your organization's cloud usage</span></span>

<span data-ttu-id="88010-152">為全域系統管理員、 安全性系統管理員或安全性讀取者，您可以了解貴組織的雲端流量透過報告和雲端探索儀表板 （也稱為產能應用程式探索）。</span><span class="sxs-lookup"><span data-stu-id="88010-152">As a global administrator, security administrator, or security reader, you can learn about your organization's cloud usage through reports and a Cloud Discovery dashboard (also called Productivity App Discovery).</span></span> <span data-ttu-id="88010-153">這個儀表板會顯示使用者、 應用程式、 web 流量及風險層級的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="88010-153">This dashboard shows information about users, apps, web traffic, and risk levels.</span></span>
  
![在 Office 365 CAS 入口網站中，選擇 [探索\>雲端探索儀表板](media/61269290-fd82-4d4b-8045-aea1ebc82287.png)
  
<span data-ttu-id="88010-155">若要移至產能應用程式探索儀表板中的 Office 365 雲端 App 安全性入口網站中，選擇 [**探索** \> **雲端探索儀表板**。</span><span class="sxs-lookup"><span data-stu-id="88010-155">To go to the Productivity App Discovery dashboard, in the Office 365 Cloud App Security portal, choose **Discover** \> **Cloud Discovery dashboard**.</span></span>
  
![在 Office 365 CAS 入口網站中，選擇 [探索](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
<span data-ttu-id="88010-157">若要填入報告與所需的資訊上, 傳您的記錄檔，從貴組織的防火牆和 proxy。</span><span class="sxs-lookup"><span data-stu-id="88010-157">To populate reports with the information you need, upload your log files from your organization's firewalls and proxies.</span></span> <span data-ttu-id="88010-158">若要深入了解，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="88010-158">To learn more, see the following resources:</span></span>
  
- [<span data-ttu-id="88010-159">在 Office 365 雲端 App 安全性建立 app 探索報表</span><span class="sxs-lookup"><span data-stu-id="88010-159">Create app discovery reports in Office 365 Cloud App Security</span></span>](create-app-discovery-reports-in-ocas.md)
    
- [<span data-ttu-id="88010-160">檢閱 Office 365 雲端 App 安全性中的 App 探索結果</span><span class="sxs-lookup"><span data-stu-id="88010-160">Review app discovery findings in Office 365 Cloud App Security</span></span>](review-app-discovery-findings-in-ocas.md)
    
## <a name="step-7-manage-apps-that-your-organization-is-using-to-access-office-365"></a><span data-ttu-id="88010-161">步驟 7： 管理您的組織用來存取 Office 365 的應用程式</span><span class="sxs-lookup"><span data-stu-id="88010-161">Step 7: Manage apps that your organization is using to access Office 365</span></span>

<span data-ttu-id="88010-162">以全域管理員或安全性系統管理員，您可以管理應用程式，例如自訂應用程式或協力廠商應用程式，其與 Office 365 的裝置上使用您組織中的人員。</span><span class="sxs-lookup"><span data-stu-id="88010-162">As a global administrator or security administrator, you can manage apps, such as custom apps or third-party apps, that people in your organization are using on their devices with Office 365.</span></span> <span data-ttu-id="88010-163">例如，假設有人已下載他們想要使用與 Office 365 的自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="88010-163">For example, suppose that someone has downloaded a custom app they want to use with Office 365.</span></span> <span data-ttu-id="88010-164">您可以檢閱人員使用的應用程式、 禁止使用不受信任的應用程式，或將應用程式標示為核准您追蹤的目的。</span><span class="sxs-lookup"><span data-stu-id="88010-164">You can review the apps people are using, ban untrusted apps, or mark apps as approved for your tracking purposes.</span></span> <span data-ttu-id="88010-165">[使用 Office 365 雲端 App 安全性管理 OAuth 應用程式](manage-app-permissions-in-ocas.md)。</span><span class="sxs-lookup"><span data-stu-id="88010-165">[Manage OAuth apps using Office 365 Cloud App Security](manage-app-permissions-in-ocas.md).</span></span>
  
## <a name="step-8-create-a-maintenance-plan"></a><span data-ttu-id="88010-166">步驟 8： 建立維護計劃</span><span class="sxs-lookup"><span data-stu-id="88010-166">Step 8: Create a maintenance plan</span></span>

<span data-ttu-id="88010-167">您已安裝並設定為 Office 365 雲端 App 安全性之後，您會想要做為 Office 365 全域系統管理員或組織的安全性管理員執行特定使用率工作。</span><span class="sxs-lookup"><span data-stu-id="88010-167">After you have set up and configured Office 365 Cloud App Security, you'll want to perform certain utilization tasks as an Office 365 global administrator or security administrator for your organization.</span></span>
<span data-ttu-id="88010-168">藉由執行這些工作，您將會協助確定已正確設定 Office 365 雲端 App 安全性、 您的原則是最新狀態，且您的組織實現從 Office 365 的值。</span><span class="sxs-lookup"><span data-stu-id="88010-168">By performing these tasks, you'll help ensure that Office 365 Cloud App Security is configured correctly, your policies are up to date, and your organization realizes value from Office 365.</span></span> <span data-ttu-id="88010-169">使用本文做為指南，以協助您規劃這些工作。</span><span class="sxs-lookup"><span data-stu-id="88010-169">Use this article as a guide to help you plan for these tasks.</span></span> <span data-ttu-id="88010-170">[推出 Office 365 雲端 App 安全性後的使用率活動](utilization-activities-for-ocas.md)，請參閱。</span><span class="sxs-lookup"><span data-stu-id="88010-170">See [Utilization activities after rolling out Office 365 Cloud App Security](utilization-activities-for-ocas.md).</span></span>

## <a name="optional-step-9-use-your-siem-server-with-office-365-cloud-app-security"></a><span data-ttu-id="88010-171">（選用）步驟 9： 使用 SIEM 伺服器與 Office 365 雲端 App 安全性</span><span class="sxs-lookup"><span data-stu-id="88010-171">(Optional) Step 9: Use your SIEM server with Office 365 Cloud App Security</span></span>

<span data-ttu-id="88010-172">您的組織使用的安全性資訊和事件管理 (SIEM) 伺服器？</span><span class="sxs-lookup"><span data-stu-id="88010-172">Is your organization using a security information and event management (SIEM) server?</span></span> <span data-ttu-id="88010-173">Office 365 雲端 App 安全性，現在可以整合與 SIEM 伺服器啟用集中式監視的提醒。</span><span class="sxs-lookup"><span data-stu-id="88010-173">Office 365 Cloud App Security can now integrate with your SIEM server to enable centralized monitoring of alerts.</span></span> <span data-ttu-id="88010-174">整合與 SIEM 服務可讓您更妥善地維護您的一般安全性工作流程、 自動化安全性程序及助益之間雲端時保護您的雲端應用程式，以及內部事件。</span><span class="sxs-lookup"><span data-stu-id="88010-174">Integrating with a SIEM service allows you to better protect your cloud applications while maintaining your usual security workflow, automating security procedures and correlating between cloud-based and on-premises events.</span></span> <span data-ttu-id="88010-175">SIEM 代理程式會在您的伺服器上執行、 提取提醒從 Office 365 雲端 App 安全性，並會那些警示串流傳送至 SIEM 伺服器。</span><span class="sxs-lookup"><span data-stu-id="88010-175">The SIEM agent runs on your server, pulls alerts from Office 365 Cloud App Security, and streams those alerts into your SIEM server.</span></span> <span data-ttu-id="88010-176">請參閱[Office 365 雲端 App 安全性與 SIEM 整合](integrate-your-siem-server-with-office-365-cas.md)。</span><span class="sxs-lookup"><span data-stu-id="88010-176">See [SIEM integration with Office 365 Cloud App Security](integrate-your-siem-server-with-office-365-cas.md).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="88010-177">後續步驟</span><span class="sxs-lookup"><span data-stu-id="88010-177">Next steps</span></span>

- [<span data-ttu-id="88010-178">開啟 Office 365 雲端 App 安全性</span><span class="sxs-lookup"><span data-stu-id="88010-178">Turn on Office 365 Cloud App Security</span></span>](turn-on-office-365-cas.md)
    
- <span data-ttu-id="88010-179">請試著您可以在此示範 Office 365 雲端 App 安全性的強大功能，並建立的概念證明的實踐經驗我們[測試實驗室指南](https://docs.microsoft.com/office365/enterprise/cloud-app-security-for-your-office-365-dev-test-environment)。</span><span class="sxs-lookup"><span data-stu-id="88010-179">Try our [Test Lab Guide](https://docs.microsoft.com/office365/enterprise/cloud-app-security-for-your-office-365-dev-test-environment) for a hands-on experience where you can demonstrate the powerful features of Office 365 Cloud App Security and create a proof of concept.</span></span> 
    

