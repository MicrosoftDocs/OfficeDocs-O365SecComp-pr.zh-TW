---
title: 開始使用 Office 365 威脅調查及回應
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/19/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 38e9b67f-d188-490f-bc91-a1ae4b270441
ms.collection:
- M365-security-compliance
description: 了解 Office 365 威脅調查及回應以及如何開始。
ms.openlocfilehash: b003805b5732710df88d45662c2a71d6014640e0
ms.sourcegitcommit: 2b46fba650df8d252b1dd2b3c3f080a383183a06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/23/2019
ms.locfileid: "34408338"
---
# <a name="get-started-with-threat-investigation-and-response-office-365-advanced-threat-protection-plan-2"></a><span data-ttu-id="3b012-103">開始使用威脅調查及回應 (Office 365 進階威脅防護計劃 2)</span><span class="sxs-lookup"><span data-stu-id="3b012-103">Get started with Threat Investigation and Response (Office 365 Advanced Threat Protection Plan 2)</span></span>

<span data-ttu-id="3b012-104">如果您是貴組織的安全性小組的一部分，您可以使用 Office 365 威脅調查及回應功能來保護您的使用者免於遭受攻擊。</span><span class="sxs-lookup"><span data-stu-id="3b012-104">If you are part of your organization's security team, you can use Office 365 Threat Investigation and Response capabilities to protect your users from attacks.</span></span> <span data-ttu-id="3b012-105">Office 365 進階威脅防護計劃 2 （先前稱為 Office 365 威脅情報） 有助於安全性分析師和由昇見解，讓使用者安全的系統管理員，並識別項目為基礎的巨集指令中的情形其 Office 365 環境。</span><span class="sxs-lookup"><span data-stu-id="3b012-105">Office 365 Advanced Threat Protection Plan 2 (formerly Office 365 Threat Intelligence) helps security analysts and administrators keep users safe by bubbling up insights and identifying action based on what is happening in their your Office 365 environment.</span></span> <span data-ttu-id="3b012-106">這些觀點根據威脅智慧資料和系統以對應至行為和可疑活動來進行攻擊的特別色模式的完整儲存機制。</span><span class="sxs-lookup"><span data-stu-id="3b012-106">These insights are based on a comprehensive repository of threat intelligence data and systems to spot patterns that correspond to attack behaviors and suspicious activity.</span></span>
  
<span data-ttu-id="3b012-107">閱讀本篇文章以深入了解威脅調查及回應，以及如何開始。</span><span class="sxs-lookup"><span data-stu-id="3b012-107">Read this article to learn more about threat investigation and response, and how to get started.</span></span>
  
## <a name="what-are-the-threat-investigation-and-response-capabilities-included-in-office-365"></a><span data-ttu-id="3b012-108">什麼是 Office 365 中所含的威脅調查及回應功能？</span><span class="sxs-lookup"><span data-stu-id="3b012-108">What are the Threat Investigation and Response capabilities included in Office 365?</span></span>

<span data-ttu-id="3b012-109">調查及回應功能可協助威脅與相關的回應動作的 Office 365 安全性中可用的磁碟機深入了解威脅&amp;合規性中心。</span><span class="sxs-lookup"><span data-stu-id="3b012-109">Threat investigation and response capabilities help drive insights into threats and related response actions that are available in the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="3b012-110">這些深入資訊可協助貴組織的安全性小組防止 Office 365 使用者的電子郵件或檔案型的攻擊。</span><span class="sxs-lookup"><span data-stu-id="3b012-110">These insights can help your organization's security team protect Office 365 users from email or file based attacks.</span></span> <span data-ttu-id="3b012-111">功能說明監視器信號，並從多個來源，例如使用者活動、 驗證、 電子郵件、 遭入侵的電腦，以及安全性事件收集資料。</span><span class="sxs-lookup"><span data-stu-id="3b012-111">The capabilities help monitor signals and gathers data from multiple sources, such as user activity, authentication, email, compromised PCs, and security incidents.</span></span> <span data-ttu-id="3b012-112">商務決策者和 Office 365 全域系統管理員、 安全性管理員和安全性分析師所有可用這項資訊來了解及回應威脅針對 Office 365 使用者並保護其智慧財產。</span><span class="sxs-lookup"><span data-stu-id="3b012-112">Business decision makers and Office 365 global administrators, security administrators, and security analysts can all use this information to understand and respond to threats against Office 365 users and protect their intellectual property.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3b012-113">Office 365 威脅情報現在是 Office 365 進階威脅防護計劃 2，以及其他威脅保護功能。</span><span class="sxs-lookup"><span data-stu-id="3b012-113">Office 365 Threat Intelligence is now Office 365 Advanced Threat Protection Plan 2, along with additional threat protection capabilities.</span></span> <span data-ttu-id="3b012-114">若要深入了解，請參閱[Office 365 進階威脅防護方案和價格](https://products.office.com/exchange/advance-threat-protection)和[Office 365 進階威脅防護服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="3b012-114">To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>
  
## <a name="get-acquainted-with-the-threat-dashboard-explorer-and-incidents"></a><span data-ttu-id="3b012-115">先熟悉威脅儀表板、 總管] 中和事件</span><span class="sxs-lookup"><span data-stu-id="3b012-115">Get acquainted with the Threat dashboard, Explorer, and Incidents</span></span>

<span data-ttu-id="3b012-116">這些威脅調查及回應功能呈現安全性&amp;合規性中心，為一組工具和回應系統工作流程，包括[威脅儀表板](#threat-dashboard)中，[威脅總管](#threat-explorer)，[事件](get-started-with-ti.md#incidents)，[攻擊模擬器](attack-simulator.md)，和自動化調查 & 回應。</span><span class="sxs-lookup"><span data-stu-id="3b012-116">These threat investigation and response capabilities surface in the Security &amp; Compliance Center, as a set of tools and response workflows, including the [threat dashboard](#threat-dashboard), [Threat Explorer](#threat-explorer), [Incidents](get-started-with-ti.md#incidents), [Attack Simulator](attack-simulator.md), and Automated Investigations & Response.</span></span>
  
### <a name="threat-dashboard"></a><span data-ttu-id="3b012-117">威脅儀表板</span><span class="sxs-lookup"><span data-stu-id="3b012-117">Threat dashboard</span></span>

<span data-ttu-id="3b012-118">若要快速查看 [已解決的威脅，使用威脅儀表板 （這也稱為[安全性儀表板](security-dashboard.md)），並報告商務決策者的視覺方式如何 Office 365 服務會保護您的業務。</span><span class="sxs-lookup"><span data-stu-id="3b012-118">Use the Threat dashboard (this is also referred to as the [Security dashboard](security-dashboard.md)) to quickly see what threats have been addressed, and as a visual way to report to business decision makers how Office 365 services are securing your business.</span></span>
  
![威脅儀表板](media/ce013a31-3f80-4d09-bb95-bfb7623b8bc4.png)
  
<span data-ttu-id="3b012-120">若要檢視和使用此儀表板，安全性&amp;合規性中心，移至**威脅管理** \> **儀表板**。</span><span class="sxs-lookup"><span data-stu-id="3b012-120">To view and use this dashboard, in the Security &amp; Compliance Center, go to **Threat management** \> **Dashboard**.</span></span>
  
### <a name="threat-explorer"></a><span data-ttu-id="3b012-121">威脅總管</span><span class="sxs-lookup"><span data-stu-id="3b012-121">Threat Explorer</span></span>

<span data-ttu-id="3b012-122">使用<b0>威脅總管 （和即時偵測）</b0>分析威脅、 經過一段時間，請參閱 < 的攻擊的磁碟區及分析資料威脅系列、 攻擊者基礎結構，等等。</span><span class="sxs-lookup"><span data-stu-id="3b012-122">Use the [Threat Explorer (and real-time detections)](threat-explorer.md) to analyze threats, see the volume of attacks over time, and analyze data by threat families, attacker infrastructure, and more.</span></span> <span data-ttu-id="3b012-123">威脅總管 （也稱為總管） 是任何安全性分析師調查工作流程的起始位置。</span><span class="sxs-lookup"><span data-stu-id="3b012-123">Threat Explorer (also referred to as Explorer) is the starting place for any security analyst's investigation workflow.</span></span>
  
![威脅總管](media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png)
  
<span data-ttu-id="3b012-125">若要檢視和使用此報告中，安全性&amp;合規性中心，移至**威脅管理** \> **總管**。</span><span class="sxs-lookup"><span data-stu-id="3b012-125">To view and use this report, in the Security &amp; Compliance Center, go to **Threat management** \> **Explorer**.</span></span>
  
 ### <a name="incidents"></a><span data-ttu-id="3b012-126">事件</span><span class="sxs-lookup"><span data-stu-id="3b012-126">Incidents</span></span>

<span data-ttu-id="3b012-127">若要查看的航班安全性事件中使用 （這也稱為調查） 事件清單。</span><span class="sxs-lookup"><span data-stu-id="3b012-127">Use the Incidents list (this is also called Investigations) to see a list of in flight security incidents.</span></span> <span data-ttu-id="3b012-128">事件用來追蹤可疑電子郵件訊息，例如威脅及以進行進一步調查和修復。</span><span class="sxs-lookup"><span data-stu-id="3b012-128">Incidents are used to track threats such as suspicious email messages, and to conduct further investigation and remediation.</span></span>
  
![在 Office 365 中的目前威脅事件的清單](media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png)
  
<span data-ttu-id="3b012-130">若要檢視您組織中，目前事件的清單中安全性&amp;合規性中心，移至**威脅管理** \> **檢閱** \> **事件**。</span><span class="sxs-lookup"><span data-stu-id="3b012-130">To view the list of current incidents for your organization, in the Security &amp; Compliance Center, go to **Threat management** \> **Review** \> **Incidents**.</span></span>
  
![安全性&amp;合規性中心，選擇 [威脅管理\>檢閱](media/e0f46454-fa38-40f0-a120-b595614d1d22.png)
  
## <a name="learn-more-about-malware-amp-threats"></a><span data-ttu-id="3b012-132">深入了解惡意程式碼&amp;威脅</span><span class="sxs-lookup"><span data-stu-id="3b012-132">Learn more about Malware &amp; Threats</span></span>

<span data-ttu-id="3b012-133">Office 365 進階威脅防護計劃 2 方案的一部分，安全性分析師可以檢閱詳細已知的威脅。</span><span class="sxs-lookup"><span data-stu-id="3b012-133">As part of the Office 365 Advanced Threat Protection Plan 2 offering, security analysts can review details about a known threat.</span></span> <span data-ttu-id="3b012-134">這很有用，判斷是否有其他預防措施/採取的步驟可以讓使用者安全。</span><span class="sxs-lookup"><span data-stu-id="3b012-134">This is useful to determine whether there are additional preventative measures/steps that can be taken to keep users safe.</span></span>
  
![顯示最近的威脅的相關資訊的安全性趨勢](media/11e7d40d-139b-4c56-8d52-c091c8654151.png) 
  
## <a name="how-do-we-get-these-threat-investigation-and-response-capabilities"></a><span data-ttu-id="3b012-136">我們要如何取得這些威脅調查及回應功能？</span><span class="sxs-lookup"><span data-stu-id="3b012-136">How do we get these Threat investigation and response capabilities?</span></span>

<span data-ttu-id="3b012-137">Office 365 威脅 Invesigation 和回應功能會包含在 Office 365 進階威脅防護計劃 2 和企業版 E5。</span><span class="sxs-lookup"><span data-stu-id="3b012-137">Office 365 Threat Invesigation and Response capabilities are included in Office 365 Advanced Threat Protection Plan 2 and Enterprise E5.</span></span> 

> [!TIP]
> <span data-ttu-id="3b012-138">如果您的組織有 Office 365 訂閱不包含這些威脅調查及回應功能，您可以將這些以以及 Office 365 進階威脅防護的附加元件形式購買。</span><span class="sxs-lookup"><span data-stu-id="3b012-138">If your organization has an Office 365 subscription that does not include these threat investigation and response capabilities, you can purchase these as an add-on along with Office 365 Advanced Threat Protection.</span></span> <span data-ttu-id="3b012-139">如需計劃選項的詳細資訊，請參閱[Office 365 平台服務說明： Office 365 安全性&amp;合規性中心](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)並[購買或編輯商務用 Office 365 的附加元件](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on)。</span><span class="sxs-lookup"><span data-stu-id="3b012-139">For more information about plan options, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) and [Buy or edit an add-on for Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on).</span></span>
  
1. <span data-ttu-id="3b012-140">身為 Office 365 全域管理員，請移至[https://admin.microsoft.com](https://admin.microsoft.com)和 Office 365 使用公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="3b012-140">As an Office 365 global administrator, go to [https://admin.microsoft.com](https://admin.microsoft.com) and sign in using your work or school account for Office 365.</span></span> 
    
2. <span data-ttu-id="3b012-141">選擇 [**管理**\>若要查看您目前的訂閱所包含的**帳單**。</span><span class="sxs-lookup"><span data-stu-id="3b012-141">Choose **Admin** \> **Billing** to see what your current subscription includes.</span></span> 
    - <span data-ttu-id="3b012-142">如果您看到**Office 365 企業版 E5**，您的組織有 Office 365 進階威脅防護計劃 2 （其中包含威脅調查及回應功能）。</span><span class="sxs-lookup"><span data-stu-id="3b012-142">If you see **Office 365 Enterprise E5**, then your organization has Office 365 Advanced Threat Protection Plan 2 (which includes threat investigation and response capabilities).</span></span> 
    - <span data-ttu-id="3b012-143">如果您看到不同的訂閱，例如**Office 365 企業版 E3**或**Office 365 企業版 E1**，請考慮新增 Office 365 進階威脅防護計劃 2。</span><span class="sxs-lookup"><span data-stu-id="3b012-143">If you see a different subscription, such as **Office 365 Enterprise E3** or **Office 365 Enterprise E1**, consider adding Office 365 Advanced Threat Protection Plan 2.</span></span> <span data-ttu-id="3b012-144">(若要這麼做，請選擇 [ **+ 新增訂閱**)。</span><span class="sxs-lookup"><span data-stu-id="3b012-144">(To do that, choose **+ Add subscription**.)</span></span>
    
3. <span data-ttu-id="3b012-145">在 Microsoft 365 系統管理中心中，選擇 [**使用者** \> **作用中的使用者**。</span><span class="sxs-lookup"><span data-stu-id="3b012-145">In the Microsoft 365 admin center, choose **Users** \> **Active users**.</span></span>
    
5. <span data-ttu-id="3b012-146">將 Office 365 進階威脅防護計劃 2 授權指派給所有作用中使用者。</span><span class="sxs-lookup"><span data-stu-id="3b012-146">Assign Office 365 Advanced Threat Protection Plan 2 licenses to all active users.</span></span> <span data-ttu-id="3b012-147">（只有已獲授權，此功能的使用者會顯示在報告中，例如檔案總管。）</span><span class="sxs-lookup"><span data-stu-id="3b012-147">(Only users who have a license for this will show up in reports, such as Explorer.)</span></span>
    
6. <span data-ttu-id="3b012-148">將角色指派給您組織中，將會使用 Office 365 進階威脅防護的人員。</span><span class="sxs-lookup"><span data-stu-id="3b012-148">Assign roles to people in your organization who will be working with the Office 365 Advanced Threat Protection.</span></span> <span data-ttu-id="3b012-149">請參閱[讓使用者能夠存取 Office 365 安全性&amp;合規性中心](grant-access-to-the-security-and-compliance-center.md)，與下表，請參閱：</span><span class="sxs-lookup"><span data-stu-id="3b012-149">See [Give users access to the Office 365 Security &amp; Compliance Center](grant-access-to-the-security-and-compliance-center.md), and refer to the following table:</span></span><br/>

  |<span data-ttu-id="3b012-150">**若要執行這項活動...]**</span><span class="sxs-lookup"><span data-stu-id="3b012-150">**To do this activity...**</span></span> <br/> |<span data-ttu-id="3b012-151">**您必須具有下列其中一個這些角色**</span><span class="sxs-lookup"><span data-stu-id="3b012-151">**You must have one of these roles**</span></span> <br/> |  
  |:-----|:-----|
  |<span data-ttu-id="3b012-152">使用威脅儀表板 （或新的[安全性儀表板](security-dashboard.md)）</span><span class="sxs-lookup"><span data-stu-id="3b012-152">Use the Threat dashboard (or the new [Security dashboard](security-dashboard.md))</span></span><br/> <span data-ttu-id="3b012-153">檢視最新或目前威脅的相關資訊</span><span class="sxs-lookup"><span data-stu-id="3b012-153">View information about recent or current threats</span></span>  <br/> |<span data-ttu-id="3b012-154">Office 365 全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="3b012-154">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="3b012-155">安全性系統管理員 (指派安全性&amp;合規性中心)</span><span class="sxs-lookup"><span data-stu-id="3b012-155">Security Administrator (assigned in the Security &amp; Compliance Center)</span></span>  <br/> <span data-ttu-id="3b012-156">安全性讀取者 (指派安全性&amp;合規性中心)</span><span class="sxs-lookup"><span data-stu-id="3b012-156">Security Reader (assigned in the Security &amp; Compliance Center)</span></span>  <br/> |
  |<span data-ttu-id="3b012-157">使用[威脅總管 （和即時偵測）](threat-explorer.md)來分析威脅</span><span class="sxs-lookup"><span data-stu-id="3b012-157">Use [Threat Explorer (and real-time detections)](threat-explorer.md) to analyze threats</span></span>  <br/> |<span data-ttu-id="3b012-158">Office 365 全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="3b012-158">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="3b012-159">安全性系統管理員 (指派安全性&amp;合規性中心)</span><span class="sxs-lookup"><span data-stu-id="3b012-159">Security Administrator (assigned in the Security &amp; Compliance Center)</span></span>  <br/> <span data-ttu-id="3b012-160">安全性讀取者 (指派安全性&amp;合規性中心)</span><span class="sxs-lookup"><span data-stu-id="3b012-160">Security Reader (assigned in the Security &amp; Compliance Center)</span></span>  <br/> |
  |<span data-ttu-id="3b012-161">檢視事件 （也稱為調查）</span><span class="sxs-lookup"><span data-stu-id="3b012-161">View Incidents (also referred to as Investigations)</span></span> <br/> <span data-ttu-id="3b012-162">將電子郵件訊息新增至事件</span><span class="sxs-lookup"><span data-stu-id="3b012-162">Add email messages to an incident</span></span>  <br/> |<span data-ttu-id="3b012-163">Office 365 全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="3b012-163">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="3b012-164">安全性系統管理員 (指派安全性&amp;合規性中心)</span><span class="sxs-lookup"><span data-stu-id="3b012-164">Security Administrator (assigned in the Security &amp; Compliance Center)</span></span>  <br/> <span data-ttu-id="3b012-165">安全性讀取者 (指派安全性&amp;合規性中心)</span><span class="sxs-lookup"><span data-stu-id="3b012-165">Security Reader (assigned in the Security &amp; Compliance Center)</span></span>  <br/> |
  |<span data-ttu-id="3b012-166">在事件中觸發電子郵件動作</span><span class="sxs-lookup"><span data-stu-id="3b012-166">Trigger email actions in an incident</span></span>  <br/> <span data-ttu-id="3b012-167">找出並刪除可疑的電子郵件</span><span class="sxs-lookup"><span data-stu-id="3b012-167">Find and delete suspicious email messages</span></span>  <br/> |<span data-ttu-id="3b012-168">Office 365 全域管理員或安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="3b012-168">Office 365 Global Administrator or Security Administrator</span></span>  <br/> <span data-ttu-id="3b012-169">下列其中一個以上的角色和搜尋及清除 (指派安全性&amp;合規性中心)</span><span class="sxs-lookup"><span data-stu-id="3b012-169">One of the roles above and Search and Purge (assigned in the Security &amp; Compliance Center)</span></span>  <br/> |
  |<span data-ttu-id="3b012-170">整合 Office 365 進階的威脅防護計劃 2 與 Windows Defender 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="3b012-170">Integrate Office 365 Advanced Threat Protection Plan 2 with Windows Defender Advanced Threat Protection</span></span>  <br/> <span data-ttu-id="3b012-171">與 SIEM 伺服器整合 Office 365 進階威脅防護計劃 2</span><span class="sxs-lookup"><span data-stu-id="3b012-171">Integrate Office 365 Advanced Threat Protection Plan 2 with a SIEM server</span></span>  <br/> |<span data-ttu-id="3b012-172">Office 365 全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="3b012-172">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="3b012-173">安全性系統管理員 (指派安全性&amp;合規性中心)</span><span class="sxs-lookup"><span data-stu-id="3b012-173">Security Administrator (assigned in the Security &amp; Compliance Center)</span></span>  <br/> <span data-ttu-id="3b012-174">適當的角色指派中額外的應用程式 （例如 Windows Defender 進階威脅防護入口網站或 SIEM 伺服器）</span><span class="sxs-lookup"><span data-stu-id="3b012-174">Appropriate role assigned in additional applications (such as Windows Defender Advanced Threat Protection portal or a SIEM server)</span></span>  <br/> |
   
<span data-ttu-id="3b012-175">角色、 角色群組和權限的相關資訊，請參閱[中 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="3b012-175">For information about roles, role groups, and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="3b012-176">後續步驟</span><span class="sxs-lookup"><span data-stu-id="3b012-176">Next steps</span></span>

- [<span data-ttu-id="3b012-177">了解威脅追蹤器-新增和值得注意</span><span class="sxs-lookup"><span data-stu-id="3b012-177">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)
    
- [<span data-ttu-id="3b012-178">尋找並調查惡意電子郵件已傳遞 （Office 365 威脅調查及回應）</span><span class="sxs-lookup"><span data-stu-id="3b012-178">Find and investigate malicious email that was delivered (Office 365 Threat Investigation and Response)</span></span>](investigate-malicious-email-that-was-delivered.md)
    
- [<span data-ttu-id="3b012-179">Office 365 威脅調查及回應整合 Windows Defender 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="3b012-179">Integrate Office 365 Threat Investigation and Response with Windows Defender Advanced Threat Protection</span></span>](integrate-office-365-ti-with-wdatp.md)
    
- [<span data-ttu-id="3b012-180">了解攻擊模擬器</span><span class="sxs-lookup"><span data-stu-id="3b012-180">Learn about Attack Simulator</span></span>](attack-simulator.md)
  

