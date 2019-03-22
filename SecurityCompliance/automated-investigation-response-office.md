---
title: 自動化的調查及回應 （空調） 與 Office 365 威脅情報
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/21/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 了解 Office 365 進階威脅防護中的自動化調查及回應功能。
ms.openlocfilehash: c2d5acd0bf26dc28b30f26488adf47de2c834fb6
ms.sourcegitcommit: a56128c7be5d59e976851c27301031e19fa1997d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/21/2019
ms.locfileid: "30736267"
---
# <a name="automated-investigation-and-response-air-with-office-365-threat-intelligence"></a><span data-ttu-id="8a62a-103">自動化的調查及回應 （空調） 與 Office 365 威脅情報</span><span class="sxs-lookup"><span data-stu-id="8a62a-103">Automated Investigation and Response (AIR) with Office 365 Threat Intelligence</span></span>

<span data-ttu-id="8a62a-104">自動化調查及回應 （空調） （即將推出[Office 365 威脅調查](office-365-ti.md)及回應功能） 可讓您執行自動化的調查並修復已知存在於今天的威脅。</span><span class="sxs-lookup"><span data-stu-id="8a62a-104">Automated Investigation and Response (AIR) (coming soon to [Office 365 Threat investigation and response capabilities](office-365-ti.md)) enables you to run automated investigation and remediation to well-known threats that exist today.</span></span> <span data-ttu-id="8a62a-105">閱讀本篇文章以取得空調，以及它如何協助組織更有效地降低威脅的概觀。</span><span class="sxs-lookup"><span data-stu-id="8a62a-105">Read this article to get an overview of AIR and how it can help your organization mitigate threats more effectively and efficiently.</span></span> <span data-ttu-id="8a62a-106">Tolearn 深入了解當航空將提供使用，請參閱[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)。</span><span class="sxs-lookup"><span data-stu-id="8a62a-106">Tolearn more about when AIR will be available, see the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

## <a name="alerts"></a><span data-ttu-id="8a62a-107">警示</span><span class="sxs-lookup"><span data-stu-id="8a62a-107">Alerts</span></span>

<span data-ttu-id="8a62a-108">[提醒](alert-policies.md#viewing-alerts)代表觸發程序的事件回應安全性作業小組工作流程。</span><span class="sxs-lookup"><span data-stu-id="8a62a-108">[Alerts](alert-policies.md#viewing-alerts) represent triggers for Security Operations team workflows for incident response.</span></span> <span data-ttu-id="8a62a-109">排列優先順序的調查，同時確保沒有威脅 unaddressed 提醒右集是一項挑戰。</span><span class="sxs-lookup"><span data-stu-id="8a62a-109">Prioritizing the right set of alerts for investigation while making sure no threats are unaddressed is challenging.</span></span> <span data-ttu-id="8a62a-110">時以手動方式執行提醒到調查，安全性作業小組必須搜尋，並與實體 （例如： 內容、 裝置及使用者） 相互關聯威脅的風險。</span><span class="sxs-lookup"><span data-stu-id="8a62a-110">When investigations into alerts are performed manually, Security Operations teams must hunt and correlate entities (e.g. content, devices and users) at risk from threats.</span></span> <span data-ttu-id="8a62a-111">這類任務及工作流程相當耗時且牽涉到多個工具和系統。</span><span class="sxs-lookup"><span data-stu-id="8a62a-111">Such tasks and workflows are very time consuming and involve multiple tools and systems.</span></span> <span data-ttu-id="8a62a-112">與空調、 調查及回應會自動完成到主要安全性和威脅管理警報自動觸發您安全性回應 playbooks。</span><span class="sxs-lookup"><span data-stu-id="8a62a-112">With AIR, investigation and response are automated into key security and threat management alerts that trigger your security response playbooks automatically.</span></span> 

<span data-ttu-id="8a62a-113">若要檢視提醒，在 Office 365 安全性 & 合規性中心中，選擇 [**提醒** > **檢視警示**。</span><span class="sxs-lookup"><span data-stu-id="8a62a-113">To view alerts, in the Office 365 Security & Compliance Center, choose **Alerts** > **View alerts**.</span></span>

![連結至調查的提醒](media/air-alerts-page-details.png) 

<span data-ttu-id="8a62a-115">選取警示若要檢視其詳細資料，並從該處，使用的**檢視調查**連結移至對應的[調查](#investigation-graph)。</span><span class="sxs-lookup"><span data-stu-id="8a62a-115">Select an alert to view its details, and from there, use the **View investigation** link to go to the corresponding [investigation](#investigation-graph).</span></span>

## <a name="security-playbooks"></a><span data-ttu-id="8a62a-116">安全性 playbooks</span><span class="sxs-lookup"><span data-stu-id="8a62a-116">Security playbooks</span></span>

<span data-ttu-id="8a62a-117">安全性 playbooks 所面臨的自動化 Microsoft 威脅防護中的核心的後端原則。</span><span class="sxs-lookup"><span data-stu-id="8a62a-117">Security playbooks are back-end policies that are at the heart of automation in Microsoft Threat Protection.</span></span> <span data-ttu-id="8a62a-118">常見的真實世界的安全性案例根據空調中提供安全性 playbooks。</span><span class="sxs-lookup"><span data-stu-id="8a62a-118">The security playbooks provided in AIR are based on common real-world security scenarios.</span></span> <span data-ttu-id="8a62a-119">當組織內就會觸發警示時，就會自動啟動安全性 playbook。</span><span class="sxs-lookup"><span data-stu-id="8a62a-119">A security playbook is launched automatically when an alert is triggered within your organization.</span></span> <span data-ttu-id="8a62a-120">之後會觸發警示，自動執行相關聯的 playbook。</span><span class="sxs-lookup"><span data-stu-id="8a62a-120">Once the alert triggers, the associated playbook is run automatically.</span></span> <span data-ttu-id="8a62a-121">Playbook 執行和調查] 中，查看所有關聯的中繼資料 （包括電子郵件、 使用者、 主旨、 寄件者等等），並根據其所發現的錯誤、 建議的動作，以控制並降低可以採取貴組織的安全性小組威脅。</span><span class="sxs-lookup"><span data-stu-id="8a62a-121">The playbook runs an investigation, looking at all the associated metadata (including email messages, users, subjects, senders, etc.) and, based on its findings, recommends a set of actions that your organization's security team can take to control and mitigate the threat.</span></span> 

<span data-ttu-id="8a62a-122">您會看到與空調安全性 playbooks 專為今天處理最常見的威脅該組織圖像。</span><span class="sxs-lookup"><span data-stu-id="8a62a-122">The security playbooks you'll get with AIR are designed to tackle the most frequent threats that organizations face today.</span></span> <span data-ttu-id="8a62a-123">他們根據安全性作業和事件回應小組，包括協助防禦 Microsoft 資產的輸入。</span><span class="sxs-lookup"><span data-stu-id="8a62a-123">They're based on input from Security Operations and Incident Response teams, including those who help defend Microsoft assets.</span></span>

### <a name="security-playbooks-are-rolling-out-in-phases"></a><span data-ttu-id="8a62a-124">安全性 playbooks 已推出階段</span><span class="sxs-lookup"><span data-stu-id="8a62a-124">Security playbooks are rolling out in phases</span></span>

<span data-ttu-id="8a62a-125">航空的一部分，安全性 playbooks 已推出階段</span><span class="sxs-lookup"><span data-stu-id="8a62a-125">As part of AIR, security playbooks are rolling out in phases</span></span>

- <span data-ttu-id="8a62a-126">**階段 1 (年 4 月 2019)**: Playbooks 包含安全性管理員檢閱和核准的建議。</span><span class="sxs-lookup"><span data-stu-id="8a62a-126">**Phase 1 (April 2019)**: Playbooks include recommendations that security administrators review and approve.</span></span> 

- <span data-ttu-id="8a62a-127">**階段 2 (年 6 月 2019)**: 安全性系統管理員將有選項可讓安全性 playbooks 不需要管理互動，自動採取行動。</span><span class="sxs-lookup"><span data-stu-id="8a62a-127">**Phase 2 (June 2019)**: Security administrators will have the option to allow security playbooks to take action automatically, without administrative interaction.</span></span>

<span data-ttu-id="8a62a-128">階段 1 將會包含下列 playbooks:</span><span class="sxs-lookup"><span data-stu-id="8a62a-128">Phase 1 will include the following playbooks:</span></span>
- <span data-ttu-id="8a62a-129">使用者報告的釣魚程式訊息</span><span class="sxs-lookup"><span data-stu-id="8a62a-129">User-reported phish message</span></span>
- <span data-ttu-id="8a62a-130">URL 按一下 verdict 變更和 ATP 安全連結封鎖覆寫</span><span class="sxs-lookup"><span data-stu-id="8a62a-130">URL click verdict change and ATP Safe Links block override</span></span>
- <span data-ttu-id="8a62a-131">惡意程式碼 ZAP</span><span class="sxs-lookup"><span data-stu-id="8a62a-131">Malware ZAP</span></span>
- <span data-ttu-id="8a62a-132">Phish ZAP</span><span class="sxs-lookup"><span data-stu-id="8a62a-132">Phish ZAP</span></span>
- <span data-ttu-id="8a62a-133">手動調查 （使用檔案總管）</span><span class="sxs-lookup"><span data-stu-id="8a62a-133">Manual investigations (using Explorer)</span></span>

<span data-ttu-id="8a62a-134">數個多個 playbooks 計劃階段 2 中。</span><span class="sxs-lookup"><span data-stu-id="8a62a-134">Several more playbooks are planned for Phase 2.</span></span>

### <a name="playbooks-include-investigation-and-recommendations"></a><span data-ttu-id="8a62a-135">Playbooks 包括調查與建議</span><span class="sxs-lookup"><span data-stu-id="8a62a-135">Playbooks include investigation and recommendations</span></span>

<span data-ttu-id="8a62a-136">每個 playbook 包括：</span><span class="sxs-lookup"><span data-stu-id="8a62a-136">Each playbook includes:</span></span> 
- <span data-ttu-id="8a62a-137">根和調查]，</span><span class="sxs-lookup"><span data-stu-id="8a62a-137">a root investigation,</span></span> 
- <span data-ttu-id="8a62a-138">若要搜尋其他潛在威脅下的步驟和</span><span class="sxs-lookup"><span data-stu-id="8a62a-138">steps to hunt down other potential threats, and</span></span> 
- <span data-ttu-id="8a62a-139">建議的威脅修復。</span><span class="sxs-lookup"><span data-stu-id="8a62a-139">recommended threat remediation.</span></span>

<span data-ttu-id="8a62a-140">每個高階步驟包括提供深層、 詳細又詳盡回應威脅時所執行的許多子步驟。</span><span class="sxs-lookup"><span data-stu-id="8a62a-140">Each high-level step includes many sub-steps that are executed to provide a deep, detailed, and exhaustive response to threats.</span></span>

## <a name="example-user-reported-phish-message"></a><span data-ttu-id="8a62a-141">範例： 使用者回報的釣魚程式訊息</span><span class="sxs-lookup"><span data-stu-id="8a62a-141">Example: User-reported phish message</span></span>

<span data-ttu-id="8a62a-142">當您組織中的使用者送出的電子郵件訊息，並向 Microsoft 報告所使用的[報告訊息增益集以進行 Outlook 或 Outlook Web Access](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="8a62a-142">When a user in your organization submits an email message and reports it to Microsoft by using the [Report Message add-in for Outlook or Outlook Web Access](enable-the-report-message-add-in.md).</span></span> <span data-ttu-id="8a62a-143">這樣會觸發系統架構資訊性警示，自動啟動 [調查 playbook。</span><span class="sxs-lookup"><span data-stu-id="8a62a-143">This triggers a system-based informational alert that automatically launches the investigation playbook.</span></span>

<span data-ttu-id="8a62a-144">在根調查階段中，會評估的電子郵件的各個層面。</span><span class="sxs-lookup"><span data-stu-id="8a62a-144">During the root investigation phase, various aspects of the email are assessed.</span></span> <span data-ttu-id="8a62a-145">這些包括：</span><span class="sxs-lookup"><span data-stu-id="8a62a-145">These include:</span></span>
- <span data-ttu-id="8a62a-146">可能需有哪些類型的威脅它決定;</span><span class="sxs-lookup"><span data-stu-id="8a62a-146">A determination about what type of threat it might be;</span></span>
- <span data-ttu-id="8a62a-147">寄件者; 它</span><span class="sxs-lookup"><span data-stu-id="8a62a-147">Who sent it;</span></span>
- <span data-ttu-id="8a62a-148">其中電子郵件寄件地 （傳送基礎結構）;</span><span class="sxs-lookup"><span data-stu-id="8a62a-148">Where the email was sent from (sending infrastructure);</span></span>
- <span data-ttu-id="8a62a-149">電子郵件的其他執行個體是否已傳遞或封鎖;</span><span class="sxs-lookup"><span data-stu-id="8a62a-149">Whether other instances of the email were delivered or blocked;</span></span>
- <span data-ttu-id="8a62a-150">從我們分析師; 評估</span><span class="sxs-lookup"><span data-stu-id="8a62a-150">An assessment from our analysts;</span></span>
- <span data-ttu-id="8a62a-151">是否任何已知的行銷活動; 相關聯的電子郵件</span><span class="sxs-lookup"><span data-stu-id="8a62a-151">Whether the email is associated with any known campaigns;</span></span>
- <span data-ttu-id="8a62a-152">等等。</span><span class="sxs-lookup"><span data-stu-id="8a62a-152">and more.</span></span>

<span data-ttu-id="8a62a-153">根調查完成後，playbook 會提供建議採取的動作清單。</span><span class="sxs-lookup"><span data-stu-id="8a62a-153">After the root investigation is complete, the playbook provides a list of recommended actions to take.</span></span>
  
<span data-ttu-id="8a62a-154">下一步]，執行步驟的幾個狩獵：</span><span class="sxs-lookup"><span data-stu-id="8a62a-154">Next, several hunting steps are executed:</span></span>

- <span data-ttu-id="8a62a-155">要搜尋其他電子郵件叢集中的類似電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="8a62a-155">Similar email messages in other email clusters are searched.</span></span>
- <span data-ttu-id="8a62a-156">其他平台，例如[Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)可共用接收的訊號。</span><span class="sxs-lookup"><span data-stu-id="8a62a-156">The signal is shared with other platforms, such as [Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection).</span></span>
- <span data-ttu-id="8a62a-157">決定上是否任何使用者按下透過可疑的電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="8a62a-157">A determination is made on whether any users have clicked through on the suspicious email message.</span></span>
- <span data-ttu-id="8a62a-158">檢查完成跨 Office 365 [EOP](eop/exchange-online-protection-eop.md)和[ATP](office-365-atp.md)是否有任何其他類似的訊息報告的使用者。</span><span class="sxs-lookup"><span data-stu-id="8a62a-158">A check is done across Office 365 [EOP](eop/exchange-online-protection-eop.md) and [ATP](office-365-atp.md) to see if there are any other similar messages reported by users.</span></span>
- <span data-ttu-id="8a62a-159">若要查看是否使用者已遭洩露完成查核。</span><span class="sxs-lookup"><span data-stu-id="8a62a-159">A check is done to see if a user has been compromised.</span></span> <span data-ttu-id="8a62a-160">這項檢查運用訊號跨[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)和[Azure Active Directory](https://docs.microsoft.com/azure/active-directory)，相互關聯的任何相關的事件或提醒。</span><span class="sxs-lookup"><span data-stu-id="8a62a-160">This check leverages signals across [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security) and [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlating any related events or alerts.</span></span> 

<span data-ttu-id="8a62a-161">狩獵階段風險和威脅指派給各種狩獵步驟。</span><span class="sxs-lookup"><span data-stu-id="8a62a-161">During the hunting phase, risks and threats are assigned to various hunting steps.</span></span>  

<span data-ttu-id="8a62a-162">修復為 playbook 的最後一個階段。</span><span class="sxs-lookup"><span data-stu-id="8a62a-162">Remediation is the final phase of the playbook.</span></span> <span data-ttu-id="8a62a-163">在這個階段，採取補救步驟為止，根據 theinvestigation 和狩獵階段。</span><span class="sxs-lookup"><span data-stu-id="8a62a-163">During this phase, remediation steps are taken, based on theinvestigation and hunting phases.</span></span>  

## <a name="getting-started"></a><span data-ttu-id="8a62a-164">快速入門</span><span class="sxs-lookup"><span data-stu-id="8a62a-164">Getting started</span></span>

<span data-ttu-id="8a62a-165">若要存取您調查，做為 Office 365 全域系統管理員或安全性系統管理員，移至 Office 365 安全性 & 合規性中心 ([https://protection.office.com](https://protection.office.com))，並登入。</span><span class="sxs-lookup"><span data-stu-id="8a62a-165">To access your investigations, as an Office 365 global administrator or security administrator, Go to the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span> <span data-ttu-id="8a62a-166">接著執行下列其中一項作業：</span><span class="sxs-lookup"><span data-stu-id="8a62a-166">Then, do one of the following:</span></span>

- <span data-ttu-id="8a62a-167">在左導覽中，移至 [**威脅管理** > **調查**。</span><span class="sxs-lookup"><span data-stu-id="8a62a-167">In the left navigation, go to **Threat management** > **Investigations**.</span></span>

    <span data-ttu-id="8a62a-168">或</span><span class="sxs-lookup"><span data-stu-id="8a62a-168">or</span></span>

- <span data-ttu-id="8a62a-169">威脅管理儀表板，請造訪 (在 [安全性 & 合規性中心，移至 [**威脅管理** > **儀表板**)。</span><span class="sxs-lookup"><span data-stu-id="8a62a-169">Visit the Threat management dashboard (In the Security & Compliance Center, go to **Threat management** > **Dashboard**).</span></span>

![空調 widget](media/air-widgets.png)

<span data-ttu-id="8a62a-171">[安全性儀表板](security-dashboard.md)的上方會出現您航空 widget。</span><span class="sxs-lookup"><span data-stu-id="8a62a-171">Your AIR widgets will appear across the top of the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="8a62a-172">選取 [開始] 小工具。</span><span class="sxs-lookup"><span data-stu-id="8a62a-172">Select a widget to get started.</span></span>

### <a name="automated-investigations"></a><span data-ttu-id="8a62a-173">自動化的調查</span><span class="sxs-lookup"><span data-stu-id="8a62a-173">Automated investigations</span></span>

<span data-ttu-id="8a62a-174">[自動化的調查] 頁面上顯示貴組織的調查和其目前狀態。</span><span class="sxs-lookup"><span data-stu-id="8a62a-174">The automated investigations page shows your organization's investigations and their current states.</span></span>

![空調主要調查頁面](media/air-maininvestigationpage.png) 
  
<span data-ttu-id="8a62a-176">您可以：</span><span class="sxs-lookup"><span data-stu-id="8a62a-176">You can:</span></span>
- <span data-ttu-id="8a62a-177">直接前往調查 （選取**調查識別碼**）。</span><span class="sxs-lookup"><span data-stu-id="8a62a-177">Navigate directly to an investigation (select an **Investigation ID**).</span></span>
- <span data-ttu-id="8a62a-178">套用篩選。</span><span class="sxs-lookup"><span data-stu-id="8a62a-178">Apply filters.</span></span> <span data-ttu-id="8a62a-179">選擇 [從**調查類型**、**時間範圍**、**狀態**或這些項目的組合。</span><span class="sxs-lookup"><span data-stu-id="8a62a-179">Choose from **Investigation Type**, **Time range**, **Status**, or a combination of these.</span></span>
- <span data-ttu-id="8a62a-180">將資料匯出至 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="8a62a-180">Export the data to a CSV file.</span></span>

### <a name="investigation-graph"></a><span data-ttu-id="8a62a-181">調查圖</span><span class="sxs-lookup"><span data-stu-id="8a62a-181">Investigation graph</span></span>

<span data-ttu-id="8a62a-182">當您開啟特定調查時，您會看到 [調查 graph] 頁面。</span><span class="sxs-lookup"><span data-stu-id="8a62a-182">When you open a specific investigation, you see the investigation graph page.</span></span> <span data-ttu-id="8a62a-183">此頁面會顯示所有不同的實體： 電子郵件、 使用者 （和其活動），以及已自動調查一部分警示所觸發的裝置。</span><span class="sxs-lookup"><span data-stu-id="8a62a-183">This page shows all the different entities: email messages, users (and their activities), and devices that were automatically investigated as part of the alert that was triggered.</span></span>

![空調調查 graph 頁面](media/air-investigationgraphpage.png)

<span data-ttu-id="8a62a-185">您可以：</span><span class="sxs-lookup"><span data-stu-id="8a62a-185">You can:</span></span>
- <span data-ttu-id="8a62a-186">取得目前調查的視覺化概觀。</span><span class="sxs-lookup"><span data-stu-id="8a62a-186">Get a visual overview of the current investigation.</span></span>
- <span data-ttu-id="8a62a-187">檢視調查計時的摘要。</span><span class="sxs-lookup"><span data-stu-id="8a62a-187">View a summary of the investigation timings.</span></span>
- <span data-ttu-id="8a62a-188">若要檢視該節點的詳細資料視覺效果中選取節點。</span><span class="sxs-lookup"><span data-stu-id="8a62a-188">Select a node in the visualization to view details for that node.</span></span>
- <span data-ttu-id="8a62a-189">若要檢視該索引標籤的詳細資訊，在頂端選取] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="8a62a-189">Select a tab across the top to view details for that tab.</span></span>

### <a name="alert-investigation"></a><span data-ttu-id="8a62a-190">警示調查</span><span class="sxs-lookup"><span data-stu-id="8a62a-190">Alert investigation</span></span>

<span data-ttu-id="8a62a-191">調查的 [**提醒**] 索引標籤中，您可以看到所有與調查有關的提醒。</span><span class="sxs-lookup"><span data-stu-id="8a62a-191">On the **Alerts** tab for an investigation, you can see all of the alerts relevant to the investigation.</span></span> <span data-ttu-id="8a62a-192">詳細資料包含觸發調查警示和其他警示，例如風險登入，大量下載等的相互關聯的調查。</span><span class="sxs-lookup"><span data-stu-id="8a62a-192">Details include the alert that triggered the investigation and other alerts, such as risky sign-in, mass download, etc., that are correlated to the investigation.</span></span> <span data-ttu-id="8a62a-193">此頁面上，從安全性分析師也可以檢視其他詳細資料上獲取個別警示。</span><span class="sxs-lookup"><span data-stu-id="8a62a-193">From this page, a security analyst can also view additional details on individual alerts.</span></span>

![產生提醒] 頁面上](media/air-investigationalertspage.png)

<span data-ttu-id="8a62a-195">您可以：</span><span class="sxs-lookup"><span data-stu-id="8a62a-195">You can:</span></span>
- <span data-ttu-id="8a62a-196">取得目前的觸發警示和任何相關聯的警示的視覺化概觀。</span><span class="sxs-lookup"><span data-stu-id="8a62a-196">Get a visual overview of the current triggering alert and any associated alerts.</span></span>
- <span data-ttu-id="8a62a-197">若要開啟 [顯示完整警示的詳細資訊的飛出視窗頁面清單中，選取 [警示。</span><span class="sxs-lookup"><span data-stu-id="8a62a-197">Select an alert in the list to open a fly-out page that shows full alert details.</span></span>

### <a name="email-investigation"></a><span data-ttu-id="8a62a-198">電子郵件調查</span><span class="sxs-lookup"><span data-stu-id="8a62a-198">Email investigation</span></span>

<span data-ttu-id="8a62a-199">在調查的**電子郵件**] 索引標籤中，您可以看到識別為調查的一部分的所有電子郵件叢集。</span><span class="sxs-lookup"><span data-stu-id="8a62a-199">On the **Email** tab for an investigation, you can see all the email clusters identified as part of the investigation.</span></span> 

<span data-ttu-id="8a62a-200">指定大量的電子郵件組織中的使用者傳送和接收的程序</span><span class="sxs-lookup"><span data-stu-id="8a62a-200">Given the sheer volume of email that users in an organization send and receive, the process of</span></span> 
- <span data-ttu-id="8a62a-201">根據類似的屬性，從郵件標頭、 內文、 URL 和附件; 叢集的電子郵件</span><span class="sxs-lookup"><span data-stu-id="8a62a-201">clustering email messages based on similar attributes from a message header, body, URL and attachment;</span></span> 
- <span data-ttu-id="8a62a-202">從良好的電子郵件; 分隔惡意電子郵件和</span><span class="sxs-lookup"><span data-stu-id="8a62a-202">separating malicious email from the good email; and</span></span> 
- <span data-ttu-id="8a62a-203">對惡意電子郵件採取的動作</span><span class="sxs-lookup"><span data-stu-id="8a62a-203">taking action on malicious email messages</span></span> 

<span data-ttu-id="8a62a-204">可能需要多個小時。</span><span class="sxs-lookup"><span data-stu-id="8a62a-204">can take many hours.</span></span> <span data-ttu-id="8a62a-205">空調現在會自動執行此程序，儲存您的組織安全性小組時間和精力。</span><span class="sxs-lookup"><span data-stu-id="8a62a-205">AIR now automates this process, saving your organization's security team time and effort.</span></span> 

<span data-ttu-id="8a62a-206">做為範例，請考慮下列影像。</span><span class="sxs-lookup"><span data-stu-id="8a62a-206">As an example, consider the following image.</span></span> <span data-ttu-id="8a62a-207">三個電子郵件的第一個叢集已被視為是釣魚程式。</span><span class="sxs-lookup"><span data-stu-id="8a62a-207">The first cluster of three email messages were deemed to be phish.</span></span> <span data-ttu-id="8a62a-208">類似郵件具有相同的 IP 和主旨的另一個叢集找不到，並且會被視為惡意，因為有些已識別為釣魚程式初始偵測期間。</span><span class="sxs-lookup"><span data-stu-id="8a62a-208">Another cluster of similar messages with the same IP and subject was found and is considered to be malicious, as some of them were identified as phish during initial detection.</span></span> 

![空調電子郵件調查] 頁面](media/air-investigationemailpage.png)

<span data-ttu-id="8a62a-210">您可以：</span><span class="sxs-lookup"><span data-stu-id="8a62a-210">You can:</span></span>
- <span data-ttu-id="8a62a-211">取得目前的叢集結果和威脅找到的視覺化概觀。</span><span class="sxs-lookup"><span data-stu-id="8a62a-211">Get a visual overview of the current clustering results and threats found.</span></span>
- <span data-ttu-id="8a62a-212">按一下 [叢集實體或威脅清單] 以開啟飛出視窗] 頁面上顯示的完整警示的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="8a62a-212">Click a cluster entity or a threat list to open a fly-out page that shows the full alert details.</span></span>

![空調調查的電子郵件與彈出式詳細資料](media/air-investigationemailpageflyoutdetails.png)

### <a name="user-investigation"></a><span data-ttu-id="8a62a-214">使用者調查</span><span class="sxs-lookup"><span data-stu-id="8a62a-214">User investigation</span></span>

<span data-ttu-id="8a62a-215">在 [**使用者**] 索引標籤中，您可以看到識別為調查的一部分的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="8a62a-215">On the **Users** tab, you can see all the users identified as part of the investigation.</span></span> 

<span data-ttu-id="8a62a-216">例如，在下列映像，空調已識別危害和異常根據新的收件匣規則所建立的指標。</span><span class="sxs-lookup"><span data-stu-id="8a62a-216">For example, in the following image, AIR has identified indicators of compromise and anomalies based on a new inbox rule that was created.</span></span> <span data-ttu-id="8a62a-217">調查的其他詳細資料 （辨識項） 都可以透過此索引標籤內的詳細檢視。</span><span class="sxs-lookup"><span data-stu-id="8a62a-217">Additional details (evidence) of the investigation are available through detailed views within this tab.</span></span>

![空調調查的使用者] 頁面](media/air-investigationuserspage.png)

<span data-ttu-id="8a62a-219">您可以：</span><span class="sxs-lookup"><span data-stu-id="8a62a-219">You can:</span></span>
- <span data-ttu-id="8a62a-220">取得已識別的使用者結果與風險找到的視覺化概觀。</span><span class="sxs-lookup"><span data-stu-id="8a62a-220">Get a visual overview of identified user results and risks found.</span></span>
- <span data-ttu-id="8a62a-221">選取使用者，若要開啟 [飛出視窗] 頁面上顯示的完整警示的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="8a62a-221">Select a user to open a fly-out page that shows the full alert details.</span></span>

### <a name="machine-investigation"></a><span data-ttu-id="8a62a-222">機器調查</span><span class="sxs-lookup"><span data-stu-id="8a62a-222">Machine investigation</span></span>

<span data-ttu-id="8a62a-223">**機器**索引標籤上，您可以看到識別為調查的一部分的所有機器。</span><span class="sxs-lookup"><span data-stu-id="8a62a-223">On the **Machines** tab, you can see all the machines identified as part of the investigation.</span></span> 

![空調調查機器頁面](media/air-investigationmachinepage.png)

<span data-ttu-id="8a62a-225">調查的一部分，空調相互關聯至裝置的電子郵件威脅。</span><span class="sxs-lookup"><span data-stu-id="8a62a-225">As part of the investigation, AIR correlates email threats to devices.</span></span> <span data-ttu-id="8a62a-226">例如，調查傳遞檔案之間的雜湊到[Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)調查。</span><span class="sxs-lookup"><span data-stu-id="8a62a-226">For example, an investigation passes a file hash across to [Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) to investigate.</span></span> <span data-ttu-id="8a62a-227">這可讓您的使用者相關機器的自動化調查，而且可協助確保已解決威脅，同時在雲端和在裝置。</span><span class="sxs-lookup"><span data-stu-id="8a62a-227">This allows for automated investigation of relevant machines for your users and helps to ensure that threats are addressed both in the cloud and across your devices.</span></span> 

<span data-ttu-id="8a62a-228">您可以：</span><span class="sxs-lookup"><span data-stu-id="8a62a-228">You can:</span></span>
- <span data-ttu-id="8a62a-229">取得目前機器和威脅找到的視覺化概觀。</span><span class="sxs-lookup"><span data-stu-id="8a62a-229">Get a visual overview of the current machines and threats found.</span></span>
- <span data-ttu-id="8a62a-230">選取 [若要開啟 [檢視電腦，到相關的[Windows Defender ATP 調查](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/automated-investigations-windows-defender-advanced-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="8a62a-230">Select a machine to open a view that into the related [Windows Defender ATP investigations](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/automated-investigations-windows-defender-advanced-threat-protection).</span></span>

### <a name="entity-investigation"></a><span data-ttu-id="8a62a-231">實體調查</span><span class="sxs-lookup"><span data-stu-id="8a62a-231">Entity investigation</span></span>

<span data-ttu-id="8a62a-232">在 [**實體**] 索引標籤上，您可以看到識別為調查的一部分的所有機器。</span><span class="sxs-lookup"><span data-stu-id="8a62a-232">On the **Entities** tab, you can see all the machines identified as part of the investigation.</span></span> 

<span data-ttu-id="8a62a-233">在這裡，您可以看到 investigated 的實體。</span><span class="sxs-lookup"><span data-stu-id="8a62a-233">Here, you can see the investigated entities.</span></span> <span data-ttu-id="8a62a-234">您可以檢視類型的實體，例如電子郵件、 叢集、 IP 位址、 使用者和更多詳細資料。</span><span class="sxs-lookup"><span data-stu-id="8a62a-234">You can see details of the types of entities, such as email messages, clusters, IP addresses, users, and more.</span></span> <span data-ttu-id="8a62a-235">您也可以查看多少實體進行分析，且威脅，與每個相關聯。</span><span class="sxs-lookup"><span data-stu-id="8a62a-235">You can also see how many entities were analyzed, and the threats that were associated with each.</span></span> 

![空調調查實體] 頁面上](media/air-investigationentitiespage.png)

<span data-ttu-id="8a62a-237">您可以：</span><span class="sxs-lookup"><span data-stu-id="8a62a-237">You can:</span></span>
- <span data-ttu-id="8a62a-238">取得調查實體和威脅找到的視覺化概觀。</span><span class="sxs-lookup"><span data-stu-id="8a62a-238">Get a visual overview of the investigation entities and threats found.</span></span>
- <span data-ttu-id="8a62a-239">選擇要開啟的飛出視窗頁面會顯示相關的實體詳細資料的實體。</span><span class="sxs-lookup"><span data-stu-id="8a62a-239">Select an entity to open a fly-out page that shows the related entity detail.</span></span>

![空調調查實體詳細資料](media/air-investigationsentitiespagedetails.png)

### <a name="playbook-log"></a><span data-ttu-id="8a62a-241">Playbook 記錄檔</span><span class="sxs-lookup"><span data-stu-id="8a62a-241">Playbook log</span></span>

<span data-ttu-id="8a62a-242">在 [**記錄**] 索引標籤中，您可以看到調查期間所發生的所有 playbook 步驟。</span><span class="sxs-lookup"><span data-stu-id="8a62a-242">On the **Log** tab, you can see all the playbook steps that have occurred during the investigation.</span></span> <span data-ttu-id="8a62a-243">記錄檔擷取空調一部分由 Office 365 威脅情報功能已完成的所有動作的完整詳細目錄。</span><span class="sxs-lookup"><span data-stu-id="8a62a-243">The log captures a complete inventory of all actions completed by Office 365 Threat Intelligence capabilities as part of AIR.</span></span> <span data-ttu-id="8a62a-244">它本身、 描述及的實際工期提供清楚的所有所採取的步驟，包括巨集指令檢視從開始到完成。</span><span class="sxs-lookup"><span data-stu-id="8a62a-244">It provides a clear view of all the steps taken, including the Action itself, a description and the duration of the actual from start to finish.</span></span> 

![空調調查記錄頁面](media/air-investigationlogpage.png)

<span data-ttu-id="8a62a-246">您可以：</span><span class="sxs-lookup"><span data-stu-id="8a62a-246">You can:</span></span>
- <span data-ttu-id="8a62a-247">取得看到所採取的 playbook 步驟的視覺化概觀。</span><span class="sxs-lookup"><span data-stu-id="8a62a-247">Get see a visual overview of the playbook steps taken.</span></span>
- <span data-ttu-id="8a62a-248">將結果匯出至 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="8a62a-248">Export the results to a CSV file.</span></span>
- <span data-ttu-id="8a62a-249">篩選的檢視。</span><span class="sxs-lookup"><span data-stu-id="8a62a-249">Filter the view.</span></span>

### <a name="recommended-actions"></a><span data-ttu-id="8a62a-250">建議的動作</span><span class="sxs-lookup"><span data-stu-id="8a62a-250">Recommended actions</span></span>

<span data-ttu-id="8a62a-251">在 [**動作**] 索引標籤中，您可以看到建議的修復後調查已完成的所有 playbook 動作。</span><span class="sxs-lookup"><span data-stu-id="8a62a-251">On the **Actions** tab, you can see all the playbook actions that are recommended for remediation after the investigation has completed.</span></span> 

<span data-ttu-id="8a62a-252">動作擷取 Microsoft 建議您採取調查結尾處的所有步驟的完整清單。</span><span class="sxs-lookup"><span data-stu-id="8a62a-252">Actions capture a complete list of all the steps Microsoft recommends you take at the end of a investigation.</span></span> <span data-ttu-id="8a62a-253">您可以藉由選取一或多個動作採取以下修復動作。</span><span class="sxs-lookup"><span data-stu-id="8a62a-253">You can take remediation actions here by selecting one or more actions.</span></span> <span data-ttu-id="8a62a-254">按一下 [**核准**可讓修復以開始。</span><span class="sxs-lookup"><span data-stu-id="8a62a-254">Clicking **Approve** will allow remediation to begin.</span></span> <span data-ttu-id="8a62a-255">（適當的權限可能會需要。</span><span class="sxs-lookup"><span data-stu-id="8a62a-255">(Appropriate permissions might be required.</span></span> <span data-ttu-id="8a62a-256">例如，安全性讀取者可以檢視動作，但不是核准。）</span><span class="sxs-lookup"><span data-stu-id="8a62a-256">For example, a Security Reader can view actions but not approve them.)</span></span>  

![空調調查動作] 頁面上](media/air-investigationactionspage.png)

<span data-ttu-id="8a62a-258">您可以：</span><span class="sxs-lookup"><span data-stu-id="8a62a-258">You can:</span></span>
- <span data-ttu-id="8a62a-259">取得 playbook 建議動作的視覺化概觀。</span><span class="sxs-lookup"><span data-stu-id="8a62a-259">Get a visual overview of the playbook-recommended actions.</span></span>
- <span data-ttu-id="8a62a-260">選取單一動作或多個動作。</span><span class="sxs-lookup"><span data-stu-id="8a62a-260">Select a single action or multiple actions.</span></span>
- <span data-ttu-id="8a62a-261">核准建議的動作。</span><span class="sxs-lookup"><span data-stu-id="8a62a-261">Approve recommended actions.</span></span> <span data-ttu-id="8a62a-262">（這些被入門立即註解。）</span><span class="sxs-lookup"><span data-stu-id="8a62a-262">(These are started immediately with comments.)</span></span>
- <span data-ttu-id="8a62a-263">將結果匯出至 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="8a62a-263">Export the results to a CSV file.</span></span>
- <span data-ttu-id="8a62a-264">篩選的檢視。</span><span class="sxs-lookup"><span data-stu-id="8a62a-264">Filter the view.</span></span>

## <a name="how-to-get-air"></a><span data-ttu-id="8a62a-265">如何取得航空</span><span class="sxs-lookup"><span data-stu-id="8a62a-265">How to get AIR</span></span>

<span data-ttu-id="8a62a-266">目前，空調是在預覽中。</span><span class="sxs-lookup"><span data-stu-id="8a62a-266">Currently, AIR is in preview.</span></span> <span data-ttu-id="8a62a-267">當使用者放開，航空將會包含在下列訂閱：</span><span class="sxs-lookup"><span data-stu-id="8a62a-267">When released, AIR will be included in the following subscriptions:</span></span>

- <span data-ttu-id="8a62a-268">Microsoft 365 企業版 E5</span><span class="sxs-lookup"><span data-stu-id="8a62a-268">Microsoft 365 Enterprise E5</span></span>
- <span data-ttu-id="8a62a-269">Office 365 企業版 E5</span><span class="sxs-lookup"><span data-stu-id="8a62a-269">Office 365 Enterprise E5</span></span>
- <span data-ttu-id="8a62a-270">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="8a62a-270">Microsoft Threat Protection</span></span>
- <span data-ttu-id="8a62a-271">Office 365 進階的威脅保護計劃 2</span><span class="sxs-lookup"><span data-stu-id="8a62a-271">Office 365 Advanced Threat Protection Plan 2</span></span>

<span data-ttu-id="8a62a-272">若要深入了解可用的功能，請造訪[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)。</span><span class="sxs-lookup"><span data-stu-id="8a62a-272">To learn more about feature availability, visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>
