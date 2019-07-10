---
title: 自動化的調查及回應 （空調） 與 Office 365
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 06/25/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 了解 Office 365 進階威脅防護中的自動化調查及回應功能。
ms.openlocfilehash: 3e74fd7a12727880164797f076d254416325713a
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2019
ms.locfileid: "35598519"
---
# <a name="automated-investigation-and-response-air-with-office-365"></a><span data-ttu-id="7b707-103">自動化的調查及回應 （空調） 與 Office 365</span><span class="sxs-lookup"><span data-stu-id="7b707-103">Automated Investigation and Response (AIR) with Office 365</span></span>

<span data-ttu-id="7b707-104">自動化的調查及回應 （空調） （目前處於為下列其中一個許多[Office 365 威脅調查及回應功能](office-365-ti.md)的公用預覽） 可讓您執行自動化的調查並修復已知存在於今天的威脅。</span><span class="sxs-lookup"><span data-stu-id="7b707-104">Automated Investigation and Response (AIR) (currently in public preview as one of many [Office 365 Threat investigation and response capabilities](office-365-ti.md)) enables you to run automated investigation and remediation to well-known threats that exist today.</span></span> <span data-ttu-id="7b707-105">閱讀本篇文章以取得的空調，以及如何可幫助您的組織和安全性作業小組降低威脅，更有效率地概觀。</span><span class="sxs-lookup"><span data-stu-id="7b707-105">Read this article to get an overview of AIR and how it can help your organization and security operations teams mitigate threats more effectively and efficiently.</span></span> 

<span data-ttu-id="7b707-106">若要深入了解當空調功能會變成可用，請參閱[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)。</span><span class="sxs-lookup"><span data-stu-id="7b707-106">To learn more about when  AIR features will be available, see the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

## <a name="alerts"></a><span data-ttu-id="7b707-107">警示</span><span class="sxs-lookup"><span data-stu-id="7b707-107">Alerts</span></span>

<span data-ttu-id="7b707-108">[提醒](alert-policies.md#viewing-alerts)代表觸發程序適用於安全性事件回應作業小組工作流程。</span><span class="sxs-lookup"><span data-stu-id="7b707-108">[Alerts](alert-policies.md#viewing-alerts) represent triggers for security operations team workflows for incident response.</span></span> <span data-ttu-id="7b707-109">排列優先順序的調查，同時確保沒有威脅 unaddressed 提醒右組是一項挑戰。</span><span class="sxs-lookup"><span data-stu-id="7b707-109">Prioritizing the right set of alerts for investigation, while making sure no threats are unaddressed is challenging.</span></span> <span data-ttu-id="7b707-110">時以手動方式執行提醒到調查，安全性作業小組必須搜尋，並與實體 （例如： 內容、 裝置及使用者） 相互關聯威脅的風險。</span><span class="sxs-lookup"><span data-stu-id="7b707-110">When investigations into alerts are performed manually, Security Operations teams must hunt and correlate entities (e.g. content, devices and users) at risk from threats.</span></span> <span data-ttu-id="7b707-111">這類任務及工作流程相當耗時且牽涉到多個工具和系統。</span><span class="sxs-lookup"><span data-stu-id="7b707-111">Such tasks and workflows are very time consuming and involve multiple tools and systems.</span></span> <span data-ttu-id="7b707-112">與空調、 調查及回應會自動完成到主要安全性和威脅管理警報自動觸發您安全性回應 playbooks。</span><span class="sxs-lookup"><span data-stu-id="7b707-112">With AIR, investigation and response are automated into key security and threat management alerts that trigger your security response playbooks automatically.</span></span> 

<span data-ttu-id="7b707-113">在 2019 年 4 月中的空調初始版本中，從下列警示原則會自動-調查的單一事件產生警示。</span><span class="sxs-lookup"><span data-stu-id="7b707-113">In the initial release of AIR in April 2019, alerts generated from following single events alert policies will be auto-investigated.</span></span> 

1. <span data-ttu-id="7b707-114">偵測到有潛在的惡意 URL 點擊</span><span class="sxs-lookup"><span data-stu-id="7b707-114">A potentially malicious URL click was detected</span></span>
2. <span data-ttu-id="7b707-115">報告的釣魚程式 \* 作為使用者的電子郵件</span><span class="sxs-lookup"><span data-stu-id="7b707-115">Email reported by user as phish\*</span></span>
3. <span data-ttu-id="7b707-116">電子郵件包含惡意程式碼傳遞 \* 後移除</span><span class="sxs-lookup"><span data-stu-id="7b707-116">Email messages containing malware removed after delivery\*</span></span>
4. <span data-ttu-id="7b707-117">電子郵件訊息包含傳遞 \* 後移除的釣魚程式 Url</span><span class="sxs-lookup"><span data-stu-id="7b707-117">Email messages containing phish URLs removed after delivery\*</span></span>

> [!NOTE]
> <span data-ttu-id="7b707-118">這些警示已指派中安全性 & 合規性中心內的個別警示原則 」 提示資訊 」 嚴重性關閉的電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="7b707-118">These alerts have been assigned an "Informational" severity in the respective alert policies within the Security & Compliance Center with email notifications turned off.</span></span> <span data-ttu-id="7b707-119">這些可以開啟透過警示原則設定。</span><span class="sxs-lookup"><span data-stu-id="7b707-119">These can be turned on through the Alert policy configuration.</span></span>

<span data-ttu-id="7b707-120">若要檢視提醒，安全性 & 合規性中心中，選擇 [**提醒** > **檢視警示**。</span><span class="sxs-lookup"><span data-stu-id="7b707-120">To view alerts, in the Security & Compliance Center, choose **Alerts** > **View alerts**.</span></span> <span data-ttu-id="7b707-121">選取警示若要檢視其詳細資料，並從該處，使用的**檢視調查**連結移至對應的[調查](#investigation-graph)。</span><span class="sxs-lookup"><span data-stu-id="7b707-121">Select an alert to view its details, and from there, use the **View investigation** link to go to the corresponding [investigation](#investigation-graph).</span></span> <span data-ttu-id="7b707-122">請注意預設將資訊警示隱藏 [警示] 檢視中。</span><span class="sxs-lookup"><span data-stu-id="7b707-122">Note that informational alerts are hidden in the alert view by default.</span></span> <span data-ttu-id="7b707-123">若要查看它們，您需要變更篩選功能，包括資訊警示的警示。</span><span class="sxs-lookup"><span data-stu-id="7b707-123">To see them, you need to change the alert filtering to include informational alerts.</span></span>

<span data-ttu-id="7b707-124">如果您的組織管理您的安全性提醒透過警示管理系統、 服務管理系統或安全性資訊和事件管理 (SIEM) 的系統，您可以透過 [電子郵件通知，或是透過[該系統傳送 Office 365 警示Office 365 管理活動 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)。</span><span class="sxs-lookup"><span data-stu-id="7b707-124">If your organization manages your security alerts through a alert management system, service management system, or Security Information and Event Management (SIEM) system, you can send Office 365 alerts to that system via either email notification or via the [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> <span data-ttu-id="7b707-125">透過電子郵件或 API 調查警示通知會包含連結來存取安全性 & 合規性中心，啟用快速瀏覽到調查指派的安全性系統管理員中的警示。</span><span class="sxs-lookup"><span data-stu-id="7b707-125">The investigation alert notifications via email or API will include links to access the alerts in the Security & Compliance Center, enabling the assigned security administrator to navigate quickly to the investigation.</span></span>

![連結至調查的提醒](media/air-alerts-page-details.png) 


## <a name="security-playbooks"></a><span data-ttu-id="7b707-127">安全性 playbooks</span><span class="sxs-lookup"><span data-stu-id="7b707-127">Security playbooks</span></span>

<span data-ttu-id="7b707-128">安全性 playbooks 所面臨的自動化 Microsoft 威脅防護中的核心的後端原則。</span><span class="sxs-lookup"><span data-stu-id="7b707-128">Security playbooks are back-end policies that are at the heart of automation in Microsoft Threat Protection.</span></span> <span data-ttu-id="7b707-129">常見的真實世界的安全性案例根據空調中提供安全性 playbooks。</span><span class="sxs-lookup"><span data-stu-id="7b707-129">The security playbooks provided in AIR are based on common real-world security scenarios.</span></span> <span data-ttu-id="7b707-130">當組織內就會觸發警示時，就會自動啟動安全性 playbook。</span><span class="sxs-lookup"><span data-stu-id="7b707-130">A security playbook is launched automatically when an alert is triggered within your organization.</span></span> <span data-ttu-id="7b707-131">之後會觸發警示，自動執行相關聯的 playbook。</span><span class="sxs-lookup"><span data-stu-id="7b707-131">Once the alert triggers, the associated playbook is run automatically.</span></span> <span data-ttu-id="7b707-132">Playbook 執行和調查]，查看所有關聯的中繼資料 （包括電子郵件、 使用者、 主旨、 寄件者等）。</span><span class="sxs-lookup"><span data-stu-id="7b707-132">The playbook runs an investigation, looking at all the associated metadata (including email messages, users, subjects, senders, etc.).</span></span> <span data-ttu-id="7b707-133">根據 playbook 所發現的錯誤，空調建議一組的動作，貴組織的安全性小組可以採取控制項，並降低威脅。</span><span class="sxs-lookup"><span data-stu-id="7b707-133">Based on the playbook's findings, AIR recommends a set of actions that your organization's security team can take to control and mitigate the threat.</span></span> 

<span data-ttu-id="7b707-134">您會看到與空調安全性 playbooks 專為今天處理最常見的威脅該組織圖像。</span><span class="sxs-lookup"><span data-stu-id="7b707-134">The security playbooks you'll get with AIR are designed to tackle the most frequent threats that organizations face today.</span></span> <span data-ttu-id="7b707-135">他們根據安全性作業和事件回應小組，包括協助防禦 Microsoft 和我們的客戶資產的輸入。</span><span class="sxs-lookup"><span data-stu-id="7b707-135">They're based on input from Security Operations and Incident Response teams, including those who help defend Microsoft and our customers assets.</span></span>

### <a name="security-playbooks-are-rolling-out-in-phases"></a><span data-ttu-id="7b707-136">安全性 playbooks 已推出階段</span><span class="sxs-lookup"><span data-stu-id="7b707-136">Security playbooks are rolling out in phases</span></span>

<span data-ttu-id="7b707-137">航空的一部分，安全性 playbooks 已推出階段</span><span class="sxs-lookup"><span data-stu-id="7b707-137">As part of AIR, security playbooks are rolling out in phases</span></span>

- <span data-ttu-id="7b707-138">**階段 1 (年 4 月 2019)**: Playbooks 包含建議的安全性管理員檢閱和核准的動作。</span><span class="sxs-lookup"><span data-stu-id="7b707-138">**Phase 1 (April 2019)**: Playbooks include recommendations for actions that security administrators review and approve.</span></span> <span data-ttu-id="7b707-139">階段 1 將會包含下列 playbooks:</span><span class="sxs-lookup"><span data-stu-id="7b707-139">Phase 1 will include the following playbooks:</span></span>
    - <span data-ttu-id="7b707-140">使用者報告的釣魚程式訊息</span><span class="sxs-lookup"><span data-stu-id="7b707-140">User-reported phish message</span></span>
    - <span data-ttu-id="7b707-141">URL 按一下 verdict 變更</span><span class="sxs-lookup"><span data-stu-id="7b707-141">URL click verdict change</span></span> 
    - <span data-ttu-id="7b707-142">偵測到的惡意程式碼後傳遞 （惡意程式碼時能量光束）</span><span class="sxs-lookup"><span data-stu-id="7b707-142">Malware detected post-delivery (Malware ZAP)</span></span>
    - <span data-ttu-id="7b707-143">釣魚程式偵測到後續傳遞 ZAP （Phish 時能量光束）</span><span class="sxs-lookup"><span data-stu-id="7b707-143">Phish detected post-delivery ZAP (Phish ZAP)</span></span>
    - <span data-ttu-id="7b707-144">手動的電子郵件調查 （使用威脅總管）</span><span class="sxs-lookup"><span data-stu-id="7b707-144">Manual e-mail investigations (using Threat Explorer)</span></span>

- <span data-ttu-id="7b707-145">**階段 2 （2019年的第二個半）**： 幾個新 playbooks 和 playbook 改良，加上的選項來設定安全性 playbooks 安全性管理員才會自動沒有系統管理互動的某些動作。</span><span class="sxs-lookup"><span data-stu-id="7b707-145">**Phase 2 (second half of 2019)**: Several new playbooks and playbook improvements, plus the option for security administrators to configure security playbooks to take some actions automatically without administrative interaction.</span></span> 

### <a name="playbooks-include-investigation-and-recommendations"></a><span data-ttu-id="7b707-146">Playbooks 包括調查與建議</span><span class="sxs-lookup"><span data-stu-id="7b707-146">Playbooks include investigation and recommendations</span></span>

<span data-ttu-id="7b707-147">每個 playbook 包括：</span><span class="sxs-lookup"><span data-stu-id="7b707-147">Each playbook includes:</span></span> 
- <span data-ttu-id="7b707-148">根和調查]，</span><span class="sxs-lookup"><span data-stu-id="7b707-148">a root investigation,</span></span> 
- <span data-ttu-id="7b707-149">識別並對應其他潛在威脅，所採取的步驟和</span><span class="sxs-lookup"><span data-stu-id="7b707-149">steps taken to identify and correlate other potential threats, and</span></span> 
- <span data-ttu-id="7b707-150">建議的威脅修復動作。</span><span class="sxs-lookup"><span data-stu-id="7b707-150">recommended threat remediation actions.</span></span>

<span data-ttu-id="7b707-151">每個高階步驟包括提供深層、 詳細又詳盡回應威脅時所執行的許多子步驟。</span><span class="sxs-lookup"><span data-stu-id="7b707-151">Each high-level step includes many sub-steps that are executed to provide a deep, detailed, and exhaustive response to threats.</span></span>

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a><span data-ttu-id="7b707-152">範例： 使用者回報的釣魚程式訊息啟動調查 playbook</span><span class="sxs-lookup"><span data-stu-id="7b707-152">Example: A user-reported phish message launches an investigation playbook</span></span>

<span data-ttu-id="7b707-153">當您組織中的使用者送出的電子郵件訊息和報告至 Microsoft，請使用[報告訊息增益集以進行 Outlook 或 Outlook Web Access](enable-the-report-message-add-in.md)，報告也會傳送到您的系統，且使用者報告檢視中顯示在檔案總管。</span><span class="sxs-lookup"><span data-stu-id="7b707-153">When a user in your organization submits an email message and reports it to Microsoft by using the [Report Message add-in for Outlook or Outlook Web Access](enable-the-report-message-add-in.md), the report is also sent to your system and is visible in Explorer in the User-reported view.</span></span> <span data-ttu-id="7b707-154">此使用者回報郵件現在會觸發系統架構資訊警示，這會自動啟動 [調查 playbook。</span><span class="sxs-lookup"><span data-stu-id="7b707-154">This user-reported message now triggers a system-based informational alert, which automatically launches the investigation playbook.</span></span>

<span data-ttu-id="7b707-155">在根調查階段中，會評估的電子郵件的各個層面。</span><span class="sxs-lookup"><span data-stu-id="7b707-155">During the root investigation phase, various aspects of the email are assessed.</span></span> <span data-ttu-id="7b707-156">這些包括：</span><span class="sxs-lookup"><span data-stu-id="7b707-156">These include:</span></span>
- <span data-ttu-id="7b707-157">可能需有哪些類型的威脅它決定;</span><span class="sxs-lookup"><span data-stu-id="7b707-157">A determination about what type of threat it might be;</span></span>
- <span data-ttu-id="7b707-158">寄件者; 它</span><span class="sxs-lookup"><span data-stu-id="7b707-158">Who sent it;</span></span>
- <span data-ttu-id="7b707-159">其中電子郵件寄件地 （傳送基礎結構）;</span><span class="sxs-lookup"><span data-stu-id="7b707-159">Where the email was sent from (sending infrastructure);</span></span>
- <span data-ttu-id="7b707-160">電子郵件的其他執行個體是否已傳遞或封鎖;</span><span class="sxs-lookup"><span data-stu-id="7b707-160">Whether other instances of the email were delivered or blocked;</span></span>
- <span data-ttu-id="7b707-161">從我們分析師; 評估</span><span class="sxs-lookup"><span data-stu-id="7b707-161">An assessment from our analysts;</span></span>
- <span data-ttu-id="7b707-162">是否任何已知的行銷活動; 相關聯的電子郵件</span><span class="sxs-lookup"><span data-stu-id="7b707-162">Whether the email is associated with any known campaigns;</span></span>
- <span data-ttu-id="7b707-163">等等。</span><span class="sxs-lookup"><span data-stu-id="7b707-163">and more.</span></span>

<span data-ttu-id="7b707-164">根調查完成後，playbook 會提供建議的動作，才會在原始的電子郵件和與它相關聯的實體清單。</span><span class="sxs-lookup"><span data-stu-id="7b707-164">After the root investigation is complete, the playbook provides a list of recommended actions to take on the original email and entities associated with it.</span></span>
  
<span data-ttu-id="7b707-165">接下來，數個威脅調查並狩獵步驟執行：</span><span class="sxs-lookup"><span data-stu-id="7b707-165">Next, several threat investigation and hunting steps are executed:</span></span>

- <span data-ttu-id="7b707-166">要搜尋其他電子郵件叢集中的類似電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="7b707-166">Similar email messages in other email clusters are searched.</span></span>
- <span data-ttu-id="7b707-167">其他平台，例如[Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)可共用接收的訊號。</span><span class="sxs-lookup"><span data-stu-id="7b707-167">The signal is shared with other platforms, such as [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span></span>
- <span data-ttu-id="7b707-168">決定在任何使用者是否按下可疑的電子郵件訊息中任何前往惡意連結。</span><span class="sxs-lookup"><span data-stu-id="7b707-168">A determination is made on whether any users have clicked through any malicious links in suspicious email messages.</span></span>
- <span data-ttu-id="7b707-169">檢查完成跨 Office 365 Exchange Online Protection ([EOP](eop/exchange-online-protection-eop.md)) 和 Office 365 進階威脅防護 ([ATP](office-365-atp.md))，以查看是否有任何其他類似的訊息報告的使用者。</span><span class="sxs-lookup"><span data-stu-id="7b707-169">A check is done across Office 365 Exchange Online Protection ([EOP](eop/exchange-online-protection-eop.md)) and Office 365 Advanced Threat Protection ([ATP](office-365-atp.md)) to see if there are any other similar messages reported by users.</span></span>
- <span data-ttu-id="7b707-170">若要查看是否使用者已遭洩露完成查核。</span><span class="sxs-lookup"><span data-stu-id="7b707-170">A check is done to see if a user has been compromised.</span></span> <span data-ttu-id="7b707-171">這項檢查跨[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)和[Azure Active Directory](https://docs.microsoft.com/azure/active-directory)，相互關聯任何相關的使用者活動異常運用訊號。</span><span class="sxs-lookup"><span data-stu-id="7b707-171">This check leverages signals across [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security) and [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlating any related user activity anomalies.</span></span> 

<span data-ttu-id="7b707-172">狩獵階段風險和威脅指派給各種狩獵步驟。</span><span class="sxs-lookup"><span data-stu-id="7b707-172">During the hunting phase, risks and threats are assigned to various hunting steps.</span></span> 

<span data-ttu-id="7b707-173">修復為 playbook 的最後一個階段。</span><span class="sxs-lookup"><span data-stu-id="7b707-173">Remediation is the final phase of the playbook.</span></span> <span data-ttu-id="7b707-174">在這個階段，採取補救步驟為止，根據調查和狩獵階段。</span><span class="sxs-lookup"><span data-stu-id="7b707-174">During this phase, remediation steps are taken, based on the investigation and hunting phases.</span></span> 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a><span data-ttu-id="7b707-175">範例： 安全性系統管理員會觸發從威脅總管調查</span><span class="sxs-lookup"><span data-stu-id="7b707-175">Example: A security administrator triggers an investigation from Threat Explorer</span></span>

<span data-ttu-id="7b707-176">除了警示所觸發的自動調查，貴組織的安全性作業小組可以觸發自動進行調查，從[威脅總管](use-explorer-in-security-and-compliance.md)] 中檢視。</span><span class="sxs-lookup"><span data-stu-id="7b707-176">In addition to automatic investigations that are triggered by an alert, your organization's security operations team can trigger an automatic investigation from a view in [Threat Explorer](use-explorer-in-security-and-compliance.md).</span></span>

<span data-ttu-id="7b707-177">例如，假設您正在檢視的資料在檔案總管中關於使用者報告的郵件。</span><span class="sxs-lookup"><span data-stu-id="7b707-177">For example, suppose that you are viewing data in Explorer about user-reported messages.</span></span> <span data-ttu-id="7b707-178">您可以在結果清單中選取項目，然後按一下 [**調查]**。</span><span class="sxs-lookup"><span data-stu-id="7b707-178">You can select an item in the list of results, and then click **Investigate**.</span></span>

![使用者報告中的郵件檔案總管與調查] 按鈕](media/Explorer-UserReported-Investigate.png)

<span data-ttu-id="7b707-180">另一個範例，假設您正在檢視包含惡意程式碼，偵測到的電子郵件的相關資料，並有幾個偵測為包含惡意程式碼的電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="7b707-180">As another example, suppose you are viewing data about email messages detected as containing malware, and there are several email messages detected as containing malware.</span></span> <span data-ttu-id="7b707-181">您可以選取 [**電子郵件**] 索引標籤，選取一或多個電子郵件訊息，然後在 [**動作**] 功能表上選取 [**調查]**。</span><span class="sxs-lookup"><span data-stu-id="7b707-181">You can select the **Email** tab, select one or more email messages, and then, on the **Actions** menu, select **Investigate**.</span></span> 

![在檔案總管中開始進行調查，惡意程式碼](media/Explorer-Malware-Email-ActionsInvestigate.png)

<span data-ttu-id="7b707-183">類似於 playbooks 觸發警示的通知，會觸發從瀏覽器中檢視的自動調查包含根目錄和調查]，以找出並相互關聯的威脅，步驟及建議的動作來減輕這些威脅。</span><span class="sxs-lookup"><span data-stu-id="7b707-183">Similar to playbooks triggered by an alert, automatic investigations that are triggered from a view in Explorer include a root investigation, steps to identify and correlate threats, and recommended actions to mitigate those threats.</span></span>

## <a name="get-started"></a><span data-ttu-id="7b707-184">開始使用</span><span class="sxs-lookup"><span data-stu-id="7b707-184">Get started</span></span>

<span data-ttu-id="7b707-185">若要為 Office 365 全域系統管理員、 安全性系統管理員或安全性讀取者存取您調查，移至安全性 & 合規性中心 ([https://protection.office.com](https://protection.office.com))，並登入。</span><span class="sxs-lookup"><span data-stu-id="7b707-185">To access your investigations, as an Office 365 global administrator, security administrator, or security reader, go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span> <span data-ttu-id="7b707-186">接著執行下列其中一項作業：</span><span class="sxs-lookup"><span data-stu-id="7b707-186">Then, do one of the following:</span></span>

- <span data-ttu-id="7b707-187">在左側導覽中，前往 [**提醒** > **檢視提醒**，開啟其中一個調查與相關的提醒，然後按一下 [警示彈出式視窗底部的 [**檢視調查**] 連結。</span><span class="sxs-lookup"><span data-stu-id="7b707-187">In the left navigation, go to **Alerts** > **View alerts**, open one of the investigation related alerts, then click the **View investigation** link at the bottom of the alert flyout.</span></span> 

    <span data-ttu-id="7b707-188">或</span><span class="sxs-lookup"><span data-stu-id="7b707-188">or</span></span>

- <span data-ttu-id="7b707-189">在左導覽中，移至 [**威脅管理** > **調查**。</span><span class="sxs-lookup"><span data-stu-id="7b707-189">In the left navigation, go to **Threat management** > **Investigations**.</span></span>

    <span data-ttu-id="7b707-190">或</span><span class="sxs-lookup"><span data-stu-id="7b707-190">or</span></span>

- <span data-ttu-id="7b707-191">威脅管理儀表板，請造訪 (在 [安全性 & 合規性中心，移至 [**威脅管理** > **儀表板**)。</span><span class="sxs-lookup"><span data-stu-id="7b707-191">Visit the Threat management dashboard (In the Security & Compliance Center, go to **Threat management** > **Dashboard**).</span></span>

![空調 widget](media/air-widgets.png)

<span data-ttu-id="7b707-193">[安全性儀表板](security-dashboard.md)的上方會出現您航空 widget。</span><span class="sxs-lookup"><span data-stu-id="7b707-193">Your AIR widgets will appear across the top of the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="7b707-194">選取 [開始] 小工具。</span><span class="sxs-lookup"><span data-stu-id="7b707-194">Select a widget to get started.</span></span>

<span data-ttu-id="7b707-195">您也可能會存取調查直接從的相關警示。</span><span class="sxs-lookup"><span data-stu-id="7b707-195">You may also access an investigation directly from the related Alerts.</span></span>

### <a name="automated-investigations"></a><span data-ttu-id="7b707-196">自動化的調查</span><span class="sxs-lookup"><span data-stu-id="7b707-196">Automated investigations</span></span>

<span data-ttu-id="7b707-197">[自動化的調查] 頁面上顯示貴組織的調查和其目前狀態。</span><span class="sxs-lookup"><span data-stu-id="7b707-197">The automated investigations page shows your organization's investigations and their current states.</span></span>

![空調主要調查頁面](media/air-maininvestigationpage.png) 
  
<span data-ttu-id="7b707-199">您可以：</span><span class="sxs-lookup"><span data-stu-id="7b707-199">You can:</span></span>
- <span data-ttu-id="7b707-200">直接前往調查 （選取**調查識別碼**）。</span><span class="sxs-lookup"><span data-stu-id="7b707-200">Navigate directly to an investigation (select an **Investigation ID**).</span></span>
- <span data-ttu-id="7b707-201">套用篩選。</span><span class="sxs-lookup"><span data-stu-id="7b707-201">Apply filters.</span></span> <span data-ttu-id="7b707-202">選擇 [從**調查類型**、**時間範圍**、**狀態**或這些項目的組合。</span><span class="sxs-lookup"><span data-stu-id="7b707-202">Choose from **Investigation Type**, **Time range**, **Status**, or a combination of these.</span></span>
- <span data-ttu-id="7b707-203">將資料匯出至 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="7b707-203">Export the data to a CSV file.</span></span>

<span data-ttu-id="7b707-204">調查狀態表示分析和動作的進度。</span><span class="sxs-lookup"><span data-stu-id="7b707-204">The investigation status indicates the progress of the analysis and actions.</span></span> <span data-ttu-id="7b707-205">隨著調查執行，狀態會變更，指出是否威脅找不到，以及指出是否已核准的動作。</span><span class="sxs-lookup"><span data-stu-id="7b707-205">As the investigation runs, the status will change to indicate whether threats were found, as well as indicate whether actions have been approved.</span></span> 
- <span data-ttu-id="7b707-206">**起始**： 調查已排入佇列推出開始</span><span class="sxs-lookup"><span data-stu-id="7b707-206">**Starting**: The investigation is queued to begin soon</span></span>
- <span data-ttu-id="7b707-207">**執行**： 調查已啟動，並且正在進行其 ' 分析</span><span class="sxs-lookup"><span data-stu-id="7b707-207">**Running**: The investigation has started and is conducting its' analysis</span></span>
- <span data-ttu-id="7b707-208">**否威脅找到**： 調查已完成其 ' 分析，並沒有威脅找不到</span><span class="sxs-lookup"><span data-stu-id="7b707-208">**No Threats Found**: The investigation has completed its' analysis and no threats were found</span></span>
- <span data-ttu-id="7b707-209">**終止前所需的系統**： 調查已不關閉，並將在 7 天後過期</span><span class="sxs-lookup"><span data-stu-id="7b707-209">**Terminated By System**: The investigation was not closed and expired after 7 days</span></span>
- <span data-ttu-id="7b707-210">**擱置中的巨集指令**： 調查找到威脅與建議的動作</span><span class="sxs-lookup"><span data-stu-id="7b707-210">**Pending Action**: The investigation found threats with actions recommended</span></span>
- <span data-ttu-id="7b707-211">**威脅找到**： 調查找到威脅，但威脅沒有空調內可用的動作</span><span class="sxs-lookup"><span data-stu-id="7b707-211">**Threats Found**: The investigation found threats, but the threats do not have actions available within AIR</span></span>
- <span data-ttu-id="7b707-212">**Remediated**: investgation 完成，並完全修復 （已核准所有動作）</span><span class="sxs-lookup"><span data-stu-id="7b707-212">**Remediated**: The investgation finished and was fully remediated (all actions were approved)</span></span>
- <span data-ttu-id="7b707-213">**部分修復**： 調查完成，並建議的動作的一些已核准</span><span class="sxs-lookup"><span data-stu-id="7b707-213">**Partially Remediated**: The investigation finished and some of the recommended actions were approved</span></span>
- <span data-ttu-id="7b707-214">**終止前所需的使用者**： 系統管理員終止調查</span><span class="sxs-lookup"><span data-stu-id="7b707-214">**Terminated By User**: An admin terminated the investigation</span></span>
- <span data-ttu-id="7b707-215">**失敗**： 無法到達在威脅結論調查期間發生錯誤</span><span class="sxs-lookup"><span data-stu-id="7b707-215">**Failed**: An error occurred during the investigation that prevented it from reaching a conclusion on threats</span></span>
- <span data-ttu-id="7b707-216">**排入佇列的節流設定**： 調查正在等候由於系統處理限制 （以保護服務效能） 的分析</span><span class="sxs-lookup"><span data-stu-id="7b707-216">**Queued By Throttling**: The investigation is waiting for analysis due to system processing limitations (to protect service performance)</span></span>
- <span data-ttu-id="7b707-217">**終止前所需的節流設定**： 調查無法完成中有足夠的時間，因為調查磁碟區及處理限制的系統。</span><span class="sxs-lookup"><span data-stu-id="7b707-217">**Terminated By Throttling**: The investigation could not be completed in sufficient time due to investigation volume and system processing limitations.</span></span> <span data-ttu-id="7b707-218">您可以重新觸發調查，選取 [檔案總管中的 [電子郵件，然後選取調查巨集指令。</span><span class="sxs-lookup"><span data-stu-id="7b707-218">You can re-trigger the investigation by selecting the email in Explorer and selecting the Investigate action.</span></span>

### <a name="investigation-graph"></a><span data-ttu-id="7b707-219">調查圖</span><span class="sxs-lookup"><span data-stu-id="7b707-219">Investigation graph</span></span>

<span data-ttu-id="7b707-220">當您開啟特定調查時，您會看到 [調查 graph] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7b707-220">When you open a specific investigation, you see the investigation graph page.</span></span> <span data-ttu-id="7b707-221">此頁面會顯示所有不同的實體： 電子郵件、 使用者 （和其活動），以及已自動調查一部分警示所觸發的裝置。</span><span class="sxs-lookup"><span data-stu-id="7b707-221">This page shows all the different entities: email messages, users (and their activities), and devices that were automatically investigated as part of the alert that was triggered.</span></span>

![空調調查 graph 頁面](media/air-investigationgraphpage.png)

<span data-ttu-id="7b707-223">您可以：</span><span class="sxs-lookup"><span data-stu-id="7b707-223">You can:</span></span>
- <span data-ttu-id="7b707-224">取得目前調查的視覺化概觀。</span><span class="sxs-lookup"><span data-stu-id="7b707-224">Get a visual overview of the current investigation.</span></span>
- <span data-ttu-id="7b707-225">檢視調查工期的摘要。</span><span class="sxs-lookup"><span data-stu-id="7b707-225">View a summary of the investigation duration.</span></span>
- <span data-ttu-id="7b707-226">若要檢視該節點的詳細資料視覺效果中選取節點。</span><span class="sxs-lookup"><span data-stu-id="7b707-226">Select a node in the visualization to view details for that node.</span></span>
- <span data-ttu-id="7b707-227">若要檢視該索引標籤的詳細資訊，在頂端選取] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="7b707-227">Select a tab across the top to view details for that tab.</span></span>

### <a name="alert-investigation"></a><span data-ttu-id="7b707-228">警示調查</span><span class="sxs-lookup"><span data-stu-id="7b707-228">Alert investigation</span></span>

<span data-ttu-id="7b707-229">調查的 [**提醒**] 索引標籤中，您可以看到與調查有關的提醒。</span><span class="sxs-lookup"><span data-stu-id="7b707-229">On the **Alerts** tab for an investigation, you can see alerts relevant to the investigation.</span></span> <span data-ttu-id="7b707-230">詳細資料包含觸發調查警示和其他警示，例如風險登入，大量下載等的相互關聯的調查。</span><span class="sxs-lookup"><span data-stu-id="7b707-230">Details include the alert that triggered the investigation and other alerts, such as risky sign-in, mass download, etc., that are correlated to the investigation.</span></span> <span data-ttu-id="7b707-231">此頁面上，從安全性分析師也可以檢視其他詳細資料上獲取個別警示。</span><span class="sxs-lookup"><span data-stu-id="7b707-231">From this page, a security analyst can also view additional details on individual alerts.</span></span>

![產生提醒] 頁面上](media/air-investigationalertspage.png)

<span data-ttu-id="7b707-233">您可以：</span><span class="sxs-lookup"><span data-stu-id="7b707-233">You can:</span></span>
- <span data-ttu-id="7b707-234">取得目前的觸發警示和任何相關聯的警示的視覺化概觀。</span><span class="sxs-lookup"><span data-stu-id="7b707-234">Get a visual overview of the current triggering alert and any associated alerts.</span></span>
- <span data-ttu-id="7b707-235">若要開啟 [顯示完整警示的詳細資訊的飛出視窗頁面清單中，選取 [警示。</span><span class="sxs-lookup"><span data-stu-id="7b707-235">Select an alert in the list to open a fly-out page that shows full alert details.</span></span>

### <a name="email-investigation"></a><span data-ttu-id="7b707-236">電子郵件調查</span><span class="sxs-lookup"><span data-stu-id="7b707-236">Email investigation</span></span>

<span data-ttu-id="7b707-237">在調查的**電子郵件**] 索引標籤中，您可以看到電子郵件被識別為調查的一部分的所有叢集。</span><span class="sxs-lookup"><span data-stu-id="7b707-237">On the **Email** tab for an investigation, you can see all the clusters of email identified as part of the investigation.</span></span> 

<span data-ttu-id="7b707-238">指定大量的電子郵件組織中的使用者傳送和接收的程序</span><span class="sxs-lookup"><span data-stu-id="7b707-238">Given the sheer volume of email that users in an organization send and receive, the process of</span></span> 
- <span data-ttu-id="7b707-239">根據類似的屬性，從郵件標頭、 內文、 URL 和附件; 叢集的電子郵件</span><span class="sxs-lookup"><span data-stu-id="7b707-239">clustering email messages based on similar attributes from a message header, body, URL and attachments;</span></span> 
- <span data-ttu-id="7b707-240">從良好的電子郵件; 分隔惡意電子郵件和</span><span class="sxs-lookup"><span data-stu-id="7b707-240">separating malicious email from the good email; and</span></span> 
- <span data-ttu-id="7b707-241">對惡意電子郵件採取的動作</span><span class="sxs-lookup"><span data-stu-id="7b707-241">taking action on malicious email messages</span></span> 

<span data-ttu-id="7b707-242">可能需要多個小時。</span><span class="sxs-lookup"><span data-stu-id="7b707-242">can take many hours.</span></span> <span data-ttu-id="7b707-243">空調現在會自動執行此程序，儲存您的組織安全性小組時間和精力。</span><span class="sxs-lookup"><span data-stu-id="7b707-243">AIR now automates this process, saving your organization's security team time and effort.</span></span> 

<span data-ttu-id="7b707-244">可能會在電子郵件分析步驟期間識別的電子郵件叢集的兩種不同類型： 相似性叢集，與標記叢集。</span><span class="sxs-lookup"><span data-stu-id="7b707-244">Two different types of email clusters may be identified during the email analysis step: similarity clusters, and indicator clusters.</span></span> 
- <span data-ttu-id="7b707-245">相似性叢集會包含類似的寄件者和內容屬性的電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="7b707-245">Similarity clusters are email messages that contain similar sender and content attributes.</span></span> <span data-ttu-id="7b707-246">這些叢集會評估為惡意內容根據原始偵測結果。</span><span class="sxs-lookup"><span data-stu-id="7b707-246">These clusters are evaluated for malicious content based on the original detection findings.</span></span> <span data-ttu-id="7b707-247">包含足夠惡意偵測電子郵件叢集會被視為惡意。</span><span class="sxs-lookup"><span data-stu-id="7b707-247">Email clusters that contain enough malicious detections will be considered malicious.</span></span>
- <span data-ttu-id="7b707-248">標記叢集是包含相同指示器實體 （檔案雜湊或 URL） 從原始的電子郵件的電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="7b707-248">Indicator clusters are email messages that contain the same indicator entity (file hash or URL) from the original email.</span></span> <span data-ttu-id="7b707-249">時的原始的檔案/URL 實體便會被視為惡意，空調會套用標記 verdict 到整個叢集的電子郵件訊息包含的實體。</span><span class="sxs-lookup"><span data-stu-id="7b707-249">When the original file/URL entity is identified as malicious, AIR will apply the indicator verdict to the entire cluster of email messages containing that entity.</span></span> <span data-ttu-id="7b707-250">為檔案識別為惡意程式碼會代表叢集中的電子郵件訊息包含該檔案會視為惡意程式碼的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="7b707-250">As a file identified as malware will mean that the cluster of email messages containing that file will be treated as malware email messages.</span></span>

<span data-ttu-id="7b707-251">叢集的目標是要尋找由攻擊或活動的一部分的相同寄件者所傳送的其他相關的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="7b707-251">The goal of clustering is to find other related email messages that are sent by the same sender as part of an attack or a campaign.</span></span>

<span data-ttu-id="7b707-252">[**電子郵件**] 索引標籤也會顯示電子郵件項目相關的調查，例如使用者回報的電子郵件的詳細資訊，原始的電子郵件報告，電子郵件訊息 zapped 因為惡意程式碼/釣魚程式等等。</span><span class="sxs-lookup"><span data-stu-id="7b707-252">The **Email** tab will also show email items related to the investigation, such as the user-reported email details, the original email reported, the email message(s) zapped due to malware/phish, etc.</span></span>

<span data-ttu-id="7b707-253">在 [電子郵件] 索引標籤上目前所識別的電子郵件計數代表顯示在 [**電子郵件**] 索引標籤上的所有電子郵件訊息的總和。因為電子郵件將會出現在多個叢集，實際電子郵件訊息總數識別 （和受影響的補救動作） 會跨所有叢集與原始收件者的電子郵件是唯一的電子郵件訊息存在的計數郵件。</span><span class="sxs-lookup"><span data-stu-id="7b707-253">The email count identified on the email tab currently represents the sum total of all email messages shown on the **Email** tab. Since email messages will be present in multiple clusters, the actual total count of email messages identified (and affected by remediation actions) will be the count of unique email messages present across all of the clusters and original recipients' email messages.</span></span> 

<span data-ttu-id="7b707-254">檔案總管和空調計數上每個收件者為基礎的電子郵件，因為安全性結果、 動作和傳遞位置會根據每個收件者而有所不同。</span><span class="sxs-lookup"><span data-stu-id="7b707-254">Both Explorer and AIR count email messages on a per recipient basis, since the security verdicts, actions, and delivery locations will vary on a per recipient basis.</span></span> <span data-ttu-id="7b707-255">因此原始電子郵件傳送給三個使用者都會視為總共三個電子郵件，而不是一個電子郵件。</span><span class="sxs-lookup"><span data-stu-id="7b707-255">Thus an original email sent to three users will count as a total of three email messages instead of one email.</span></span> <span data-ttu-id="7b707-256">請注意那里可能會取得一封電子郵件的其中的情況下被計算兩個或更多時間，因為電子郵件可能會在其上有多個動作，而且可能會有多個電子郵件複本一次的所有動作會都發生。</span><span class="sxs-lookup"><span data-stu-id="7b707-256">Note there may be cases where an email gets counted two or more times, since the email may have multiple actions on it and there may be multiple copies of the email once all actions occur.</span></span> <span data-ttu-id="7b707-257">例如時，傳遞偵測到惡意程式碼電子郵件可能會導致封鎖 （隔離） 電子郵件以及已被取代的電子郵件 （威脅檔案取代警告： 檔案，再傳遞到使用者的信箱）。</span><span class="sxs-lookup"><span data-stu-id="7b707-257">For example a malware email that is detected at delivery may result in both a blocked (quarantined) email and a replaced email (threat file replaced with an warning file, then delivered to user's mailbox).</span></span> <span data-ttu-id="7b707-258">因為實際上，有兩個副本的電子郵件系統中-這些可能同時會計算叢集計數中。</span><span class="sxs-lookup"><span data-stu-id="7b707-258">Since there are literally two copies of the email in the system - these may both be counted in cluster counts.</span></span> 

<span data-ttu-id="7b707-259">電子郵件計數計算調查的同時，和某些計數的重新計算當您開啟調查延伸顯示 （根據基準查詢）。</span><span class="sxs-lookup"><span data-stu-id="7b707-259">Email counts are calculated at the time of the investigation and some counts are re-calculated when you open investigation flyouts (based on an underlying query).</span></span> <span data-ttu-id="7b707-260">電子郵件計算所顯示的電子郵件] 索引標籤上的電子郵件叢集，並在叢集彈出式視窗上所顯示的電子郵件數量值的計算調查次。</span><span class="sxs-lookup"><span data-stu-id="7b707-260">The email counts shown for the email clusters on the email tab and the email quantity value shown on cluster flyout are calculated at the time of investigation.</span></span> <span data-ttu-id="7b707-261">在叢集彈出式視窗中，[電子郵件] 索引標籤的底端顯示的電子郵件計數，以及在檔案總管中顯示的電子郵件訊息的計數會反映在調查的初始分析後收到電子郵件。</span><span class="sxs-lookup"><span data-stu-id="7b707-261">The email count shown at the bottom of the email tab of the cluster flyout, as well as the count of email messages shown in Explorer will reflect email messages received after the investigation's initial analysis.</span></span> <span data-ttu-id="7b707-262">因此顯示 10 的電子郵件的原始數量電子郵件叢集會顯示電子郵件清單總數的 15 5 的多個電子郵件訊息送達之間調查分析階段和系統管理員檢閱調查時。</span><span class="sxs-lookup"><span data-stu-id="7b707-262">Thus an email cluster that shows an original quantity of 10 email messages would show an email list total of 15 when 5 more email messages arrive between the investigation analysis phase and when the admin reviews the investigation.</span></span> <span data-ttu-id="7b707-263">顯示完成這兩個不同的檢視中的計數來指出電子郵件影響調查和到時間現行的目前影響次該修復為止。</span><span class="sxs-lookup"><span data-stu-id="7b707-263">Showing both counts in different views is done to indicate the email impact at the time of investigation and the current impact up until the time that remediation is run.</span></span>

<span data-ttu-id="7b707-264">做為範例，請考慮下列案例。</span><span class="sxs-lookup"><span data-stu-id="7b707-264">As an example, consider the following scenario.</span></span> <span data-ttu-id="7b707-265">三個電子郵件的第一個叢集已被視為是釣魚程式。</span><span class="sxs-lookup"><span data-stu-id="7b707-265">The first cluster of three email messages were deemed to be phish.</span></span> <span data-ttu-id="7b707-266">類似郵件具有相同的 IP 和主旨的另一個叢集已找到，而且視為惡意，有些已識別為釣魚程式初始偵測期間。</span><span class="sxs-lookup"><span data-stu-id="7b707-266">Another cluster of similar messages with the same IP and subject was found and considered malicious, as some of them were identified as phish during initial detection.</span></span> 

![空調電子郵件調查] 頁面](media/air-investigationemailpage.png)

<span data-ttu-id="7b707-268">您可以：</span><span class="sxs-lookup"><span data-stu-id="7b707-268">You can:</span></span>
- <span data-ttu-id="7b707-269">取得目前的叢集結果和威脅找到的視覺化概觀。</span><span class="sxs-lookup"><span data-stu-id="7b707-269">Get a visual overview of the current clustering results and threats found.</span></span>
- <span data-ttu-id="7b707-270">按一下 [叢集實體或威脅清單] 以開啟飛出視窗] 頁面上顯示的完整警示的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="7b707-270">Click a cluster entity or a threat list to open a fly-out page that shows the full alert details.</span></span>
- <span data-ttu-id="7b707-271">進一步調查的電子郵件叢集按一下頂端的 '電子郵件叢集詳細資料] 索引標籤上的 '在檔案總管中開啟' 連結</span><span class="sxs-lookup"><span data-stu-id="7b707-271">Further investigate the email cluster by clicking the 'Open in Explorer' link at the top of the 'Email cluster details' tab</span></span>

![空調調查的電子郵件與彈出式詳細資料](media/air-investigationemailpageflyoutdetails.png)

<span data-ttu-id="7b707-273">\* 附註： 在電子郵件的內容，您可能會看到大量異常威脅表面調查的一部分。</span><span class="sxs-lookup"><span data-stu-id="7b707-273">\*Note: In the context of email, you may see a volume anomaly threat surface as part of the investigation.</span></span> <span data-ttu-id="7b707-274">磁碟區異常指出相較於舊版項調查事件時間前後的類似電子郵件訊息中的特殊圖文集。</span><span class="sxs-lookup"><span data-stu-id="7b707-274">A volume anomaly indicates a spike in similar email messages around the investigation event time compared to earlier timeframes.</span></span> <span data-ttu-id="7b707-275">此特殊圖文集的特性類似的電子郵件流量 (例如主旨] 和 [寄件者的網域，本文相似性和寄件者 IP) 是一般的電子郵件行銷活動或攻擊的開始。</span><span class="sxs-lookup"><span data-stu-id="7b707-275">This spike in email traffic with similar characteristics (e.g. subject and sender domain, body similarity and sender IP) is typical of the start of email campaigns or attacks.</span></span> <span data-ttu-id="7b707-276">不過，大量、 垃圾郵件和合法電子郵件行銷活動常共用這些特性。</span><span class="sxs-lookup"><span data-stu-id="7b707-276">However, bulk, spam, and legitimate email campaigns commonly share these characteristics.</span></span> <span data-ttu-id="7b707-277">磁碟區異常代表潛在威脅，並據此可能少數嚴重相較惡意程式碼或釣魚程式的威脅，用來識別的防毒引擎、 爆炸或惡意的信譽。</span><span class="sxs-lookup"><span data-stu-id="7b707-277">Volume anomalies represent a potential threat, and accordingly could be less severe compared to malware or phish threats that are identified using anti-virus engines, detonation or malicious reputation.</span></span>

### <a name="user-investigation"></a><span data-ttu-id="7b707-278">使用者調查</span><span class="sxs-lookup"><span data-stu-id="7b707-278">User investigation</span></span>

<span data-ttu-id="7b707-279">在 [**使用者**] 索引標籤中，您可以看到識別為調查的一部分的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="7b707-279">On the **Users** tab, you can see all the users identified as part of the investigation.</span></span> <span data-ttu-id="7b707-280">使用者將會出現在調查時沒有事件或使用者可能會受到影響，或遭到盜用的指示。</span><span class="sxs-lookup"><span data-stu-id="7b707-280">Users will appear in the investigation when there is an event or indication that the user may be affected or compromised.</span></span>

<span data-ttu-id="7b707-281">例如，在下列映像，空調已識別危害和異常根據新的收件匣規則所建立的指標。</span><span class="sxs-lookup"><span data-stu-id="7b707-281">For example, in the following image, AIR has identified indicators of compromise and anomalies based on a new inbox rule that was created.</span></span> <span data-ttu-id="7b707-282">調查的其他詳細資料 （辨識項） 可透過此危害的指標] 索引標籤內的詳細檢視，而且異常也可包含從[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)的異常偵測。</span><span class="sxs-lookup"><span data-stu-id="7b707-282">Additional details (evidence) of the investigation are available through detailed views within this tab. Indicators of compromise and anomalies may also include anomaly detections from [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span></span>

![空調調查的使用者] 頁面](media/air-investigationuserspage.png)

<span data-ttu-id="7b707-284">您可以：</span><span class="sxs-lookup"><span data-stu-id="7b707-284">You can:</span></span>
- <span data-ttu-id="7b707-285">取得已識別的使用者結果與風險找到的視覺化概觀。</span><span class="sxs-lookup"><span data-stu-id="7b707-285">Get a visual overview of identified user results and risks found.</span></span>
- <span data-ttu-id="7b707-286">選取使用者，若要開啟 [飛出視窗] 頁面上顯示的完整警示的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="7b707-286">Select a user to open a fly-out page that shows the full alert details.</span></span>

### <a name="machine-investigation"></a><span data-ttu-id="7b707-287">機器調查</span><span class="sxs-lookup"><span data-stu-id="7b707-287">Machine investigation</span></span>

<span data-ttu-id="7b707-288">**機器**索引標籤上，您可以看到識別為調查的一部分的所有機器。</span><span class="sxs-lookup"><span data-stu-id="7b707-288">On the **Machines** tab, you can see all the machines identified as part of the investigation.</span></span> 

![空調調查機器頁面](media/air-investigationmachinepage.png)

<span data-ttu-id="7b707-290">調查的一部分，空調相互關聯至裝置的電子郵件威脅。</span><span class="sxs-lookup"><span data-stu-id="7b707-290">As part of the investigation, AIR correlates email threats to devices.</span></span> <span data-ttu-id="7b707-291">例如，調查遞給惡意檔案雜湊跨[Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection
)調查。</span><span class="sxs-lookup"><span data-stu-id="7b707-291">For example, an investigation passes a malicious file hash across to [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection
) to investigate.</span></span> <span data-ttu-id="7b707-292">這可讓您的使用者，以協助確保已解決威脅，在雲端和跨端點相關機器的自動化調查。</span><span class="sxs-lookup"><span data-stu-id="7b707-292">This allows for automated investigation of relevant machines for your users, to help ensure that threats are addressed both in the cloud and across your endpoints.</span></span> 

<span data-ttu-id="7b707-293">您可以：</span><span class="sxs-lookup"><span data-stu-id="7b707-293">You can:</span></span>
- <span data-ttu-id="7b707-294">取得目前機器和威脅找到的視覺化概觀。</span><span class="sxs-lookup"><span data-stu-id="7b707-294">Get a visual overview of the current machines and threats found.</span></span>
- <span data-ttu-id="7b707-295">選取 [若要開啟 [檢視電腦，到 Microsoft defender 資訊安全中心中相關的[Microsoft Defender ATP 調查](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)。</span><span class="sxs-lookup"><span data-stu-id="7b707-295">Select a machine to open a view that into the related [Microsoft Defender ATP investigations](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) in the Microsoft Defender Security Center.</span></span>

### <a name="entity-investigation"></a><span data-ttu-id="7b707-296">實體調查</span><span class="sxs-lookup"><span data-stu-id="7b707-296">Entity investigation</span></span>

<span data-ttu-id="7b707-297">在 [**實體**] 索引標籤上，您可以看到識別為調查的一部分的所有實體。</span><span class="sxs-lookup"><span data-stu-id="7b707-297">On the **Entities** tab, you can see all the entities identified as part of the investigation.</span></span> 

<span data-ttu-id="7b707-298">在這裡，您可以看到的調查實體與類型的實體，例如電子郵件、 叢集、 IP 位址、 使用者和更多詳細資料。</span><span class="sxs-lookup"><span data-stu-id="7b707-298">Here, you can see the investigated entities and details of the types of entities, such as email messages, clusters, IP addresses, users, and more.</span></span> <span data-ttu-id="7b707-299">您也可以查看多少實體進行分析，且威脅，與每個相關聯。</span><span class="sxs-lookup"><span data-stu-id="7b707-299">You can also see how many entities were analyzed, and the threats that were associated with each.</span></span> 

![空調調查實體] 頁面上](media/air-investigationentitiespage.png)

<span data-ttu-id="7b707-301">您可以：</span><span class="sxs-lookup"><span data-stu-id="7b707-301">You can:</span></span>
- <span data-ttu-id="7b707-302">取得調查實體和威脅找到的視覺化概觀。</span><span class="sxs-lookup"><span data-stu-id="7b707-302">Get a visual overview of the investigation entities and threats found.</span></span>
- <span data-ttu-id="7b707-303">選取要開啟飛出視窗] 頁面顯示相關的實體詳細資料的實體。</span><span class="sxs-lookup"><span data-stu-id="7b707-303">Select an entity to open a fly-out page that shows the related entity details.</span></span>

![空調調查實體詳細資料](media/air-investigationsentitiespagedetails.png)

### <a name="playbook-log"></a><span data-ttu-id="7b707-305">Playbook 記錄檔</span><span class="sxs-lookup"><span data-stu-id="7b707-305">Playbook log</span></span>

<span data-ttu-id="7b707-306">在 [**記錄**] 索引標籤中，您可以看到調查期間所發生的所有 playbook 步驟。</span><span class="sxs-lookup"><span data-stu-id="7b707-306">On the **Log** tab, you can see all the playbook steps that have occurred during the investigation.</span></span> <span data-ttu-id="7b707-307">記錄檔擷取由 Office 365 自動調查功能完成空調一部分的所有動作的完整詳細目錄。</span><span class="sxs-lookup"><span data-stu-id="7b707-307">The log captures a complete inventory of all actions completed by Office 365 auto-investigation capabilities as part of AIR.</span></span> <span data-ttu-id="7b707-308">它本身、 描述及的實際工期提供清楚的所有所採取的步驟，包括巨集指令檢視從開始到完成。</span><span class="sxs-lookup"><span data-stu-id="7b707-308">It provides a clear view of all the steps taken, including the action itself, a description, and the duration of the actual from start to finish.</span></span> 

![空調調查記錄頁面](media/air-investigationlogpage.png)

<span data-ttu-id="7b707-310">您可以：</span><span class="sxs-lookup"><span data-stu-id="7b707-310">You can:</span></span>
- <span data-ttu-id="7b707-311">取得看到所採取的 playbook 步驟的視覺化概觀。</span><span class="sxs-lookup"><span data-stu-id="7b707-311">Get see a visual overview of the playbook steps taken.</span></span>
- <span data-ttu-id="7b707-312">將結果匯出至 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="7b707-312">Export the results to a CSV file.</span></span>
- <span data-ttu-id="7b707-313">篩選的檢視。</span><span class="sxs-lookup"><span data-stu-id="7b707-313">Filter the view.</span></span>

### <a name="recommended-actions"></a><span data-ttu-id="7b707-314">建議的動作</span><span class="sxs-lookup"><span data-stu-id="7b707-314">Recommended actions</span></span>

<span data-ttu-id="7b707-315">在 [**動作**] 索引標籤中，您可以看到建議的修復後調查已完成的所有 playbook 動作。</span><span class="sxs-lookup"><span data-stu-id="7b707-315">On the **Actions** tab, you can see all the playbook actions that are recommended for remediation after the investigation has completed.</span></span> 

<span data-ttu-id="7b707-316">動作擷取 Microsoft 建議您採取調查結尾處的步驟。</span><span class="sxs-lookup"><span data-stu-id="7b707-316">Actions capture the steps Microsoft recommends you take at the end of a investigation.</span></span> <span data-ttu-id="7b707-317">您可以藉由選取一或多個動作採取以下修復動作。</span><span class="sxs-lookup"><span data-stu-id="7b707-317">You can take remediation actions here by selecting one or more actions.</span></span> <span data-ttu-id="7b707-318">按一下 [**核准**可讓修復以開始。</span><span class="sxs-lookup"><span data-stu-id="7b707-318">Clicking **Approve** will allow remediation to begin.</span></span> <span data-ttu-id="7b707-319">（所需的適當的權限-'搜尋及清除' 角色，才能執行從檔案總管和空調）。</span><span class="sxs-lookup"><span data-stu-id="7b707-319">(Appropriate permissions are needed - the 'Search And Purge' role is required to run actions from Explorer and AIR).</span></span> <span data-ttu-id="7b707-320">例如，安全性讀取者可以檢視動作，而不是核准它們。</span><span class="sxs-lookup"><span data-stu-id="7b707-320">For example, a Security Reader can view actions but not approve them.</span></span> <span data-ttu-id="7b707-321">請注意-不需要核准的每個動作。</span><span class="sxs-lookup"><span data-stu-id="7b707-321">Note - you do not have to approve every action.</span></span> <span data-ttu-id="7b707-322">如果您不一致的建議的動作，或您的組織未選擇特定類型的動作-然後您可以選擇 [以**拒絕**動作或只需加以略過，並不採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="7b707-322">If you do not agree with the recommended action or your organization does not choose certain types of actions - then you can either choose to **Reject** the actions or simply ignore them and take no action.</span></span> <span data-ttu-id="7b707-323">核准及/或拒絕的所有動作會讓調查完全關閉，而離開某些動作完成時，會導致調查狀態變更為部分修復的狀態。</span><span class="sxs-lookup"><span data-stu-id="7b707-323">Approving and/or rejecting all actions will let the investigation fully close, while leaving some actions incomplete will result in the investigation status changing to a partially remediated state.</span></span>

![空調調查動作] 頁面上](media/air-investigationactionspage.png)

<span data-ttu-id="7b707-325">您可以：</span><span class="sxs-lookup"><span data-stu-id="7b707-325">You can:</span></span>
- <span data-ttu-id="7b707-326">取得 playbook 建議動作的視覺化概觀。</span><span class="sxs-lookup"><span data-stu-id="7b707-326">Get a visual overview of the playbook-recommended actions.</span></span>
- <span data-ttu-id="7b707-327">選取單一動作或多個動作。</span><span class="sxs-lookup"><span data-stu-id="7b707-327">Select a single action or multiple actions.</span></span>
- <span data-ttu-id="7b707-328">核准或拒絕建議的動作與註解。</span><span class="sxs-lookup"><span data-stu-id="7b707-328">Approve or reject recommended actions with comments.</span></span>
- <span data-ttu-id="7b707-329">將結果匯出至 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="7b707-329">Export the results to a CSV file.</span></span>
- <span data-ttu-id="7b707-330">篩選的檢視。</span><span class="sxs-lookup"><span data-stu-id="7b707-330">Filter the view.</span></span>

## <a name="how-to-get-air"></a><span data-ttu-id="7b707-331">如何取得航空</span><span class="sxs-lookup"><span data-stu-id="7b707-331">How to get AIR</span></span>

<span data-ttu-id="7b707-332">目前，Office 365 空調功能是在預覽。</span><span class="sxs-lookup"><span data-stu-id="7b707-332">Currently, Office 365 AIR features are in preview.</span></span> <span data-ttu-id="7b707-333">通常有 Office 365 空調功能將會包含在下列訂閱：</span><span class="sxs-lookup"><span data-stu-id="7b707-333">When generally available, Office 365 AIR features will be included in the following subscriptions:</span></span>

- <span data-ttu-id="7b707-334">Microsoft 365 企業版 E5</span><span class="sxs-lookup"><span data-stu-id="7b707-334">Microsoft 365 Enterprise E5</span></span>
- <span data-ttu-id="7b707-335">Office 365 企業版 E5</span><span class="sxs-lookup"><span data-stu-id="7b707-335">Office 365 Enterprise E5</span></span>
- <span data-ttu-id="7b707-336">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="7b707-336">Microsoft Threat Protection</span></span>
- <span data-ttu-id="7b707-337">Office 365 進階的威脅保護計劃 2</span><span class="sxs-lookup"><span data-stu-id="7b707-337">Office 365 Advanced Threat Protection Plan 2</span></span>

<span data-ttu-id="7b707-338">若要深入了解可用的功能，請造訪[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)。</span><span class="sxs-lookup"><span data-stu-id="7b707-338">To learn more about feature availability, visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>
