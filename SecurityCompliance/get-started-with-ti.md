---
title: 開始使用 Office 365 威脅調查與回應
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
description: 瞭解 Office 365 威脅調查和回應, 以及如何開始。
ms.openlocfilehash: 9be8e33be6445dc960c12c308c56bf9afc7fdd12
ms.sourcegitcommit: b9d8a43cb3afcdc8820bc9470c5707eff8fc6616
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/11/2019
ms.locfileid: "34852577"
---
# <a name="get-started-with-threat-investigation-and-response-office-365-advanced-threat-protection-plan-2"></a><span data-ttu-id="32fe5-103">開始使用威脅調查和回應 (Office 365 高級威脅防護方案 2)</span><span class="sxs-lookup"><span data-stu-id="32fe5-103">Get started with Threat Investigation and Response (Office 365 Advanced Threat Protection Plan 2)</span></span>

<span data-ttu-id="32fe5-104">如果您是組織的安全小組的一部分, 您可以使用 Office 365 威脅調查和回應功能來保護您的使用者免遭攻擊。</span><span class="sxs-lookup"><span data-stu-id="32fe5-104">If you are part of your organization's security team, you can use Office 365 Threat Investigation and Response capabilities to protect your users from attacks.</span></span> <span data-ttu-id="32fe5-105">Office 365 Advanced 威脅防護方案 2 (先前稱為 Office 365 威脅情報) 可協助安全性分析師和系統管理員, 根據您的 Office 365 環境中發生的情況, 讓使用者安全地冒泡, 並識別動作。</span><span class="sxs-lookup"><span data-stu-id="32fe5-105">Office 365 Advanced Threat Protection Plan 2 (formerly Office 365 Threat Intelligence) helps security analysts and administrators keep users safe by bubbling up insights and identifying action based on what is happening in their your Office 365 environment.</span></span> <span data-ttu-id="32fe5-106">這些真知灼見是根據威脅情報資料與系統的完整存放庫, 以找出與攻擊行為和可疑活動相符的模式。</span><span class="sxs-lookup"><span data-stu-id="32fe5-106">These insights are based on a comprehensive repository of threat intelligence data and systems to spot patterns that correspond to attack behaviors and suspicious activity.</span></span>
  
<span data-ttu-id="32fe5-107">請閱讀本文以深入瞭解威脅調查和回應, 以及如何開始。</span><span class="sxs-lookup"><span data-stu-id="32fe5-107">Read this article to learn more about threat investigation and response, and how to get started.</span></span>
  
## <a name="what-are-the-threat-investigation-and-response-capabilities-included-in-office-365"></a><span data-ttu-id="32fe5-108">Office 365 包含的威脅調查和回應功能是什麼？</span><span class="sxs-lookup"><span data-stu-id="32fe5-108">What are the Threat Investigation and Response capabilities included in Office 365?</span></span>

<span data-ttu-id="32fe5-109">威脅調查和回應功能可協助推動 Office 365 安全性&amp;與合規性中心提供的威脅和相關回應動作。</span><span class="sxs-lookup"><span data-stu-id="32fe5-109">Threat investigation and response capabilities help drive insights into threats and related response actions that are available in the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="32fe5-110">這些真知灼見可協助貴組織的安全小組保護 Office 365 使用者免遭電子郵件或檔案的攻擊。</span><span class="sxs-lookup"><span data-stu-id="32fe5-110">These insights can help your organization's security team protect Office 365 users from email or file based attacks.</span></span> <span data-ttu-id="32fe5-111">這些功能可協助監控信號, 並收集多個來源的資料, 例如使用者活動、驗證、電子郵件、已遭破壞的電腦, 以及安全性事件。</span><span class="sxs-lookup"><span data-stu-id="32fe5-111">The capabilities help monitor signals and gathers data from multiple sources, such as user activity, authentication, email, compromised PCs, and security incidents.</span></span> <span data-ttu-id="32fe5-112">商務決策者和 Office 365 全域系統管理員、安全性系統管理員和安全性分析師都可以使用此資訊來瞭解並回應 Office 365 使用者的威脅, 並保護其智慧財產權。</span><span class="sxs-lookup"><span data-stu-id="32fe5-112">Business decision makers and Office 365 global administrators, security administrators, and security analysts can all use this information to understand and respond to threats against Office 365 users and protect their intellectual property.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="32fe5-113">Office 365 威脅情報現在是 Office 365 的高級威脅防護方案 2, 以及額外的威脅防護功能。</span><span class="sxs-lookup"><span data-stu-id="32fe5-113">Office 365 Threat Intelligence is now Office 365 Advanced Threat Protection Plan 2, along with additional threat protection capabilities.</span></span> <span data-ttu-id="32fe5-114">若要深入瞭解, 請參閱[office 365 高級威脅防護方案和價格](https://products.office.com/exchange/advance-threat-protection), 以及[Office 365 高級威脅防護服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="32fe5-114">To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>
  
## <a name="get-acquainted-with-the-threat-dashboard-explorer-and-incidents"></a><span data-ttu-id="32fe5-115">熟悉威脅儀表板、Explorer 和事件</span><span class="sxs-lookup"><span data-stu-id="32fe5-115">Get acquainted with the Threat dashboard, Explorer, and Incidents</span></span>

<span data-ttu-id="32fe5-116">安全性&amp;合規性中心內的這些威脅調查和回應功能面, 是一組工具和回應工作流程, 包括[威脅儀表板](#threat-dashboard)、[威脅 Explorer](#threat-explorer)、[事件](get-started-with-ti.md#incidents)、[攻擊模擬](attack-simulator.md)和自動調查 & 回應。</span><span class="sxs-lookup"><span data-stu-id="32fe5-116">These threat investigation and response capabilities surface in the Security &amp; Compliance Center, as a set of tools and response workflows, including the [threat dashboard](#threat-dashboard), [Threat Explorer](#threat-explorer), [Incidents](get-started-with-ti.md#incidents), [Attack Simulator](attack-simulator.md), and Automated Investigations & Response.</span></span>
  
### <a name="threat-dashboard"></a><span data-ttu-id="32fe5-117">威脅儀表板</span><span class="sxs-lookup"><span data-stu-id="32fe5-117">Threat dashboard</span></span>

<span data-ttu-id="32fe5-118">使用 [威脅] 儀表板 (也稱為 [安全性][儀表板](security-dashboard.md)), 快速查看已解決的威脅, 並以視覺方式向企業決策者報告 Office 365 服務如何保護您的業務。</span><span class="sxs-lookup"><span data-stu-id="32fe5-118">Use the Threat dashboard (this is also referred to as the [Security dashboard](security-dashboard.md)) to quickly see what threats have been addressed, and as a visual way to report to business decision makers how Office 365 services are securing your business.</span></span>
  
![威脅儀表板](media/ce013a31-3f80-4d09-bb95-bfb7623b8bc4.png)
  
<span data-ttu-id="32fe5-120">若要查看和使用此儀表板, 請&amp;在安全性與合規性中心, 移至 [**威脅管理** \> ]**儀表板**。</span><span class="sxs-lookup"><span data-stu-id="32fe5-120">To view and use this dashboard, in the Security &amp; Compliance Center, go to **Threat management** \> **Dashboard**.</span></span>
  
### <a name="threat-explorer"></a><span data-ttu-id="32fe5-121">威脅總管</span><span class="sxs-lookup"><span data-stu-id="32fe5-121">Threat Explorer</span></span>

<span data-ttu-id="32fe5-122">使用[威脅瀏覽器 (和即時偵測)](threat-explorer.md)來分析威脅、查看一段時間內的攻擊量, 以及依威脅系列、攻擊者基礎結構等等分析資料。</span><span class="sxs-lookup"><span data-stu-id="32fe5-122">Use the [Threat Explorer (and real-time detections)](threat-explorer.md) to analyze threats, see the volume of attacks over time, and analyze data by threat families, attacker infrastructure, and more.</span></span> <span data-ttu-id="32fe5-123">威脅瀏覽器 (也稱為 Explorer) 是任何安全性分析師的調查工作流程的開始位置。</span><span class="sxs-lookup"><span data-stu-id="32fe5-123">Threat Explorer (also referred to as Explorer) is the starting place for any security analyst's investigation workflow.</span></span>
  
![威脅瀏覽器](media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png)
  
<span data-ttu-id="32fe5-125">若要查看和使用此報告, 請在&amp;安全性與合規性中心, 移至 [**威脅管理** \> **瀏覽器**]。</span><span class="sxs-lookup"><span data-stu-id="32fe5-125">To view and use this report, in the Security &amp; Compliance Center, go to **Threat management** \> **Explorer**.</span></span>
  
 ### <a name="incidents"></a><span data-ttu-id="32fe5-126">故障</span><span class="sxs-lookup"><span data-stu-id="32fe5-126">Incidents</span></span>

<span data-ttu-id="32fe5-127">使用事件清單 (這也稱為「調查」) 來查看飛行安全性事件的清單。</span><span class="sxs-lookup"><span data-stu-id="32fe5-127">Use the Incidents list (this is also called Investigations) to see a list of in flight security incidents.</span></span> <span data-ttu-id="32fe5-128">事件用來追蹤威脅, 例如可疑的電子郵件訊息, 以及進行進一步的調查和修復。</span><span class="sxs-lookup"><span data-stu-id="32fe5-128">Incidents are used to track threats such as suspicious email messages, and to conduct further investigation and remediation.</span></span>
  
![Office 365 中的目前威脅事件清單](media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png)
  
<span data-ttu-id="32fe5-130">若要查看您組織的目前事件清單, &amp;請在安全性與合規性中心, 移至 [**威脅管理** \> **審查** \> **事件**]。</span><span class="sxs-lookup"><span data-stu-id="32fe5-130">To view the list of current incidents for your organization, in the Security &amp; Compliance Center, go to **Threat management** \> **Review** \> **Incidents**.</span></span>
  
![在安全性&amp;與合規性中心中, 選擇\> [威脅管理審查]](media/e0f46454-fa38-40f0-a120-b595614d1d22.png)
  
## <a name="learn-more-about-malware-amp-threats"></a><span data-ttu-id="32fe5-132">深入瞭解惡意&amp;代碼威脅</span><span class="sxs-lookup"><span data-stu-id="32fe5-132">Learn more about Malware &amp; Threats</span></span>

<span data-ttu-id="32fe5-133">作為 Office 365 高級威脅防護方案2選項的一部分, 安全性分析師可以查看已知威脅的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="32fe5-133">As part of the Office 365 Advanced Threat Protection Plan 2 offering, security analysts can review details about a known threat.</span></span> <span data-ttu-id="32fe5-134">若要判斷是否有額外的預防措施/步驟可讓使用者保持安全, 這是很有用的。</span><span class="sxs-lookup"><span data-stu-id="32fe5-134">This is useful to determine whether there are additional preventative measures/steps that can be taken to keep users safe.</span></span>
  
![顯示最近威脅相關資訊的安全性趨勢](media/11e7d40d-139b-4c56-8d52-c091c8654151.png) 
  
## <a name="how-do-we-get-these-threat-investigation-and-response-capabilities"></a><span data-ttu-id="32fe5-136">如何取得這些威脅調查和回應功能？</span><span class="sxs-lookup"><span data-stu-id="32fe5-136">How do we get these Threat investigation and response capabilities?</span></span>

<span data-ttu-id="32fe5-137">Office 365 的威脅 Invesigation 和回應功能包含在 Office 365 高級威脅防護方案2和企業版 E5 中。</span><span class="sxs-lookup"><span data-stu-id="32fe5-137">Office 365 Threat Invesigation and Response capabilities are included in Office 365 Advanced Threat Protection Plan 2 and Enterprise E5.</span></span> 

> [!TIP]
> <span data-ttu-id="32fe5-138">如果您的組織有 Office 365 訂閱, 但未包含這些威脅調查和回應功能, 您可以使用 Office 365 高級威脅防護, 以附加元件形式購買。</span><span class="sxs-lookup"><span data-stu-id="32fe5-138">If your organization has an Office 365 subscription that does not include these threat investigation and response capabilities, you can purchase these as an add-on along with Office 365 Advanced Threat Protection.</span></span> <span data-ttu-id="32fe5-139">如需規劃選項的詳細資訊, 請參閱[office 365 Platform 服務說明: office &amp; 365 安全性合規性中心](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)和[購買或編輯商務用 Office 365 的附加](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on)元件。</span><span class="sxs-lookup"><span data-stu-id="32fe5-139">For more information about plan options, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) and [Buy or edit an add-on for Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on).</span></span>
  
1. <span data-ttu-id="32fe5-140">如果是 Office 365 全域系統管理員, 請[https://admin.microsoft.com](https://admin.microsoft.com)移至, 並使用 office 365 的公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="32fe5-140">As an Office 365 global administrator, go to [https://admin.microsoft.com](https://admin.microsoft.com) and sign in using your work or school account for Office 365.</span></span> 
    
2. <span data-ttu-id="32fe5-141">選擇 [系統**管理** \> **帳單**] 以查看您目前的訂閱所包含的內容。</span><span class="sxs-lookup"><span data-stu-id="32fe5-141">Choose **Admin** \> **Billing** to see what your current subscription includes.</span></span> 
    - <span data-ttu-id="32fe5-142">如果您看到**office 365 企業版 E5**, 表示您的組織有 Office 365 高級威脅防護方案 2 (包括威脅調查和回應功能)。</span><span class="sxs-lookup"><span data-stu-id="32fe5-142">If you see **Office 365 Enterprise E5**, then your organization has Office 365 Advanced Threat Protection Plan 2 (which includes threat investigation and response capabilities).</span></span> 
    - <span data-ttu-id="32fe5-143">如果您看到不同的訂閱, 例如**Office 365 Enterprise E3**或**Office 365 企業版 E1**, 請考慮新增 Office 365 Advanced 威脅防護方案2。</span><span class="sxs-lookup"><span data-stu-id="32fe5-143">If you see a different subscription, such as **Office 365 Enterprise E3** or **Office 365 Enterprise E1**, consider adding Office 365 Advanced Threat Protection Plan 2.</span></span> <span data-ttu-id="32fe5-144">(若要這麼做, 請選擇 [ **+ 新增訂閱**]。)</span><span class="sxs-lookup"><span data-stu-id="32fe5-144">(To do that, choose **+ Add subscription**.)</span></span>
    
3. <span data-ttu-id="32fe5-145">在 Microsoft 365 系統管理中心, 選擇 [**使用者** \> ] [作用中**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="32fe5-145">In the Microsoft 365 admin center, choose **Users** \> **Active users**.</span></span>
    
5. <span data-ttu-id="32fe5-146">將 Office 365 高級威脅防護方案2授權指派給所有作用中的使用者。</span><span class="sxs-lookup"><span data-stu-id="32fe5-146">Assign Office 365 Advanced Threat Protection Plan 2 licenses to all active users.</span></span> <span data-ttu-id="32fe5-147">(只有擁有這項授權的使用者才會顯示在報表中, 例如 Explorer)。</span><span class="sxs-lookup"><span data-stu-id="32fe5-147">(Only users who have a license for this will show up in reports, such as Explorer.)</span></span>
    
6. <span data-ttu-id="32fe5-148">將角色指派給組織中要使用 Office 365 高級威脅防護的人員。</span><span class="sxs-lookup"><span data-stu-id="32fe5-148">Assign roles to people in your organization who will be working with the Office 365 Advanced Threat Protection.</span></span> <span data-ttu-id="32fe5-149">請參閱[授與使用者存取 Office 365 安全性&amp;與規範中心的許可權](grant-access-to-the-security-and-compliance-center.md), 並參照下表:</span><span class="sxs-lookup"><span data-stu-id="32fe5-149">See [Give users access to the Office 365 Security &amp; Compliance Center](grant-access-to-the-security-and-compliance-center.md), and refer to the following table:</span></span><br/>

  |<span data-ttu-id="32fe5-150">**若要執行此動作 .。。**</span><span class="sxs-lookup"><span data-stu-id="32fe5-150">**To do this activity...**</span></span> <br/> |<span data-ttu-id="32fe5-151">**您必須擁有其中一個角色**</span><span class="sxs-lookup"><span data-stu-id="32fe5-151">**You must have one of these roles**</span></span> <br/> |  
  |:-----|:-----|
  |<span data-ttu-id="32fe5-152">使用 [威脅] 儀表板 (或新的[安全性儀表板](security-dashboard.md))</span><span class="sxs-lookup"><span data-stu-id="32fe5-152">Use the Threat dashboard (or the new [Security dashboard](security-dashboard.md))</span></span><br/> <span data-ttu-id="32fe5-153">查看最近或目前威脅的相關資訊</span><span class="sxs-lookup"><span data-stu-id="32fe5-153">View information about recent or current threats</span></span>  <br/> |<span data-ttu-id="32fe5-154">Office 365 全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="32fe5-154">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="32fe5-155">安全性系統管理員 (在安全性&amp;與合規性中心中指派)</span><span class="sxs-lookup"><span data-stu-id="32fe5-155">Security Administrator (assigned in the Security &amp; Compliance Center)</span></span>  <br/> <span data-ttu-id="32fe5-156">安全性讀取器 (在安全性&amp;與合規性中心中指派)</span><span class="sxs-lookup"><span data-stu-id="32fe5-156">Security Reader (assigned in the Security &amp; Compliance Center)</span></span>  <br/> |
  |<span data-ttu-id="32fe5-157">使用[威脅瀏覽器 (和即時偵測)](threat-explorer.md)來分析威脅</span><span class="sxs-lookup"><span data-stu-id="32fe5-157">Use [Threat Explorer (and real-time detections)](threat-explorer.md) to analyze threats</span></span>  <br/> |<span data-ttu-id="32fe5-158">Office 365 全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="32fe5-158">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="32fe5-159">安全性系統管理員 (在安全性&amp;與合規性中心中指派)</span><span class="sxs-lookup"><span data-stu-id="32fe5-159">Security Administrator (assigned in the Security &amp; Compliance Center)</span></span>  <br/> <span data-ttu-id="32fe5-160">安全性讀取器 (在安全性&amp;與合規性中心中指派)</span><span class="sxs-lookup"><span data-stu-id="32fe5-160">Security Reader (assigned in the Security &amp; Compliance Center)</span></span>  <br/> |
  |<span data-ttu-id="32fe5-161">查看事件 (也稱為調查)</span><span class="sxs-lookup"><span data-stu-id="32fe5-161">View Incidents (also referred to as Investigations)</span></span> <br/> <span data-ttu-id="32fe5-162">將電子郵件訊息新增至事件</span><span class="sxs-lookup"><span data-stu-id="32fe5-162">Add email messages to an incident</span></span>  <br/> |<span data-ttu-id="32fe5-163">Office 365 全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="32fe5-163">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="32fe5-164">安全性系統管理員 (在安全性&amp;與合規性中心中指派)</span><span class="sxs-lookup"><span data-stu-id="32fe5-164">Security Administrator (assigned in the Security &amp; Compliance Center)</span></span>  <br/> <span data-ttu-id="32fe5-165">安全性讀取器 (在安全性&amp;與合規性中心中指派)</span><span class="sxs-lookup"><span data-stu-id="32fe5-165">Security Reader (assigned in the Security &amp; Compliance Center)</span></span>  <br/> |
  |<span data-ttu-id="32fe5-166">觸發事件中的電子郵件動作</span><span class="sxs-lookup"><span data-stu-id="32fe5-166">Trigger email actions in an incident</span></span>  <br/> <span data-ttu-id="32fe5-167">尋找並刪除可疑的電子郵件</span><span class="sxs-lookup"><span data-stu-id="32fe5-167">Find and delete suspicious email messages</span></span>  <br/> |<span data-ttu-id="32fe5-168">Office 365 全域系統管理員或安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="32fe5-168">Office 365 Global Administrator or Security Administrator</span></span>  <br/> <span data-ttu-id="32fe5-169">上述其中一個角色, 以及搜尋和清除 (在安全性&amp;與合規性中心中指派)</span><span class="sxs-lookup"><span data-stu-id="32fe5-169">One of the roles above and Search and Purge (assigned in the Security &amp; Compliance Center)</span></span>  <br/> |
  |<span data-ttu-id="32fe5-170">使用 Microsoft Defender ATP 整合 Office 365 高級威脅防護方案2</span><span class="sxs-lookup"><span data-stu-id="32fe5-170">Integrate Office 365 Advanced Threat Protection Plan 2 with Microsoft Defender ATP</span></span>  <br/> <span data-ttu-id="32fe5-171">整合 Office 365 Advanced 威脅防護方案2與 SIEM server</span><span class="sxs-lookup"><span data-stu-id="32fe5-171">Integrate Office 365 Advanced Threat Protection Plan 2 with a SIEM server</span></span>  <br/> |<span data-ttu-id="32fe5-172">Office 365 全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="32fe5-172">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="32fe5-173">安全性系統管理員 (在安全性&amp;與合規性中心中指派)</span><span class="sxs-lookup"><span data-stu-id="32fe5-173">Security Administrator (assigned in the Security &amp; Compliance Center)</span></span>  <br/> <span data-ttu-id="32fe5-174">在其他應用程式中指派適當的角色 (例如 Microsoft Defender Security Center 或 SIEM server)</span><span class="sxs-lookup"><span data-stu-id="32fe5-174">Appropriate role assigned in additional applications (such as Microsoft Defender Security Center or a SIEM server)</span></span>  <br/> |
   
<span data-ttu-id="32fe5-175">如需角色、角色群組及許可權的詳細資訊, 請參閱[Office 365 安全性&amp;與合規性中心的許可權](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="32fe5-175">For information about roles, role groups, and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="32fe5-176">後續步驟</span><span class="sxs-lookup"><span data-stu-id="32fe5-176">Next steps</span></span>

- [<span data-ttu-id="32fe5-177">瞭解威脅追蹤器-新增和值得注意的</span><span class="sxs-lookup"><span data-stu-id="32fe5-177">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)
    
- [<span data-ttu-id="32fe5-178">尋找並調查已傳遞的惡意電子郵件 (Office 365 威脅調查和回應)</span><span class="sxs-lookup"><span data-stu-id="32fe5-178">Find and investigate malicious email that was delivered (Office 365 Threat Investigation and Response)</span></span>](investigate-malicious-email-that-was-delivered.md)
    
- [<span data-ttu-id="32fe5-179">整合 Office 365 威脅調查, 並使用 Microsoft Defender Advanced 威脅防護進行回應</span><span class="sxs-lookup"><span data-stu-id="32fe5-179">Integrate Office 365 Threat Investigation and Response with Microsoft Defender Advanced Threat Protection</span></span>](integrate-office-365-ti-with-wdatp.md)
    
- [<span data-ttu-id="32fe5-180">深入瞭解攻擊模擬器</span><span class="sxs-lookup"><span data-stu-id="32fe5-180">Learn about Attack Simulator</span></span>](attack-simulator.md)
  

