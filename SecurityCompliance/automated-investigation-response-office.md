---
title: 自動化的調查及回應 （空調） 與 Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/22/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 了解 Office 365 進階威脅防護中的自動化調查及回應功能。
ms.openlocfilehash: c6cfc03588e580382f673b2e9be8543bfcaf9ac1
ms.sourcegitcommit: f6073deec39a18581ed12abef18728417a52cdf4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/22/2019
ms.locfileid: "30747559"
---
# <a name="automated-investigation-and-response-air-with-office-365"></a><span data-ttu-id="5619f-103">自動化的調查及回應 （空調） 與 Office 365</span><span class="sxs-lookup"><span data-stu-id="5619f-103">Automated Investigation and Response (AIR) with Office 365</span></span>

<span data-ttu-id="5619f-104">自動化調查及回應 （空調） （即將推出[Office 365 威脅調查](office-365-ti.md)及回應功能） 可讓您執行自動化的調查並修復已知存在於今天的威脅。</span><span class="sxs-lookup"><span data-stu-id="5619f-104">Automated Investigation and Response (AIR) (coming soon to [Office 365 Threat investigation and response capabilities](office-365-ti.md)) enables you to run automated investigation and remediation to well-known threats that exist today.</span></span> <span data-ttu-id="5619f-105">閱讀本篇文章以取得的空調，以及如何可幫助您的組織和安全性作業小組降低威脅，更有效率地概觀。</span><span class="sxs-lookup"><span data-stu-id="5619f-105">Read this article to get an overview of AIR and how it can help your organization and security operations teams mitigate threats more effectively and efficiently.</span></span> <span data-ttu-id="5619f-106">若要深入了解當空調中的其他功能會變成可用，請參閱[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)。</span><span class="sxs-lookup"><span data-stu-id="5619f-106">To learn more about when additional features in AIR will be available, see the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

## <a name="alerts"></a><span data-ttu-id="5619f-107">警示</span><span class="sxs-lookup"><span data-stu-id="5619f-107">Alerts</span></span>

<span data-ttu-id="5619f-108">[提醒](alert-policies.md#viewing-alerts)代表觸發程序的事件回應安全性作業小組工作流程。</span><span class="sxs-lookup"><span data-stu-id="5619f-108">[Alerts](alert-policies.md#viewing-alerts) represent triggers for Security Operations team workflows for incident response.</span></span> <span data-ttu-id="5619f-109">排列優先順序的調查，同時確保沒有威脅 unaddressed 提醒右集是一項挑戰。</span><span class="sxs-lookup"><span data-stu-id="5619f-109">Prioritizing the right set of alerts for investigation while making sure no threats are unaddressed is challenging.</span></span> <span data-ttu-id="5619f-110">時以手動方式執行提醒到調查，安全性作業小組必須搜尋，並與實體 （例如： 內容、 裝置及使用者） 相互關聯威脅的風險。</span><span class="sxs-lookup"><span data-stu-id="5619f-110">When investigations into alerts are performed manually, Security Operations teams must hunt and correlate entities (e.g. content, devices and users) at risk from threats.</span></span> <span data-ttu-id="5619f-111">這類任務及工作流程相當耗時且牽涉到多個工具和系統。</span><span class="sxs-lookup"><span data-stu-id="5619f-111">Such tasks and workflows are very time consuming and involve multiple tools and systems.</span></span> <span data-ttu-id="5619f-112">與空調、 調查及回應會自動完成到主要安全性和威脅管理警報自動觸發您安全性回應 playbooks。</span><span class="sxs-lookup"><span data-stu-id="5619f-112">With AIR, investigation and response are automated into key security and threat management alerts that trigger your security response playbooks automatically.</span></span> 

<span data-ttu-id="5619f-113">在下列的單一事件所產生的警示的空調年 4 月 2019年中的初始版本中的警示原則會自動調查。</span><span class="sxs-lookup"><span data-stu-id="5619f-113">In the initial release of AIR in April 2019, alerts generated from following singel events alert policies will be auto-investigated.</span></span> 

1. <span data-ttu-id="5619f-114">偵測到有潛在的惡意 URL 點擊</span><span class="sxs-lookup"><span data-stu-id="5619f-114">A potentially malicious URL click was detected</span></span>
2. <span data-ttu-id="5619f-115">報告的釣魚程式 \* 作為使用者的電子郵件</span><span class="sxs-lookup"><span data-stu-id="5619f-115">Email reported by user as phish\*</span></span>
3. <span data-ttu-id="5619f-116">電子郵件包含惡意程式碼傳遞 \* 後移除</span><span class="sxs-lookup"><span data-stu-id="5619f-116">Email messages containing malware removed after delivery\*</span></span>
4. <span data-ttu-id="5619f-117">電子郵件訊息包含傳遞 \* 後移除的釣魚程式 Url</span><span class="sxs-lookup"><span data-stu-id="5619f-117">Email messages containing phish URLs removed after delivery\*</span></span>

<span data-ttu-id="5619f-118">\* 附註： 這些警示有已指派 」 提示資訊 」 嚴重性在安全性與合規性中心內的個別警示原則中關閉的電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="5619f-118">\*Note: These alerts have been assigned an "Informational" severity in the respective alert policies within the Security and Compliance Center with email notifications turned off.</span></span> <span data-ttu-id="5619f-119">這些可以開啟透過警示原則設定。</span><span class="sxs-lookup"><span data-stu-id="5619f-119">These can be turned on through the Alert policy configuration.</span></span>

<span data-ttu-id="5619f-120">若要檢視提醒，在 Office 365 安全性 & 合規性中心中，選擇 [**提醒** > **檢視警示**。</span><span class="sxs-lookup"><span data-stu-id="5619f-120">To view alerts, in the Office 365 Security & Compliance Center, choose **Alerts** > **View alerts**.</span></span> <span data-ttu-id="5619f-121">選取警示若要檢視其詳細資料，並從該處，使用的**檢視調查**連結移至對應的[調查](#investigation-graph)。</span><span class="sxs-lookup"><span data-stu-id="5619f-121">Select an alert to view its details, and from there, use the **View investigation** link to go to the corresponding [investigation](#investigation-graph).</span></span>

![連結至調查的提醒](media/air-alerts-page-details.png) 


## <a name="security-playbooks"></a><span data-ttu-id="5619f-123">安全性 playbooks</span><span class="sxs-lookup"><span data-stu-id="5619f-123">Security playbooks</span></span>

<span data-ttu-id="5619f-124">安全性 playbooks 所面臨的自動化 Microsoft 威脅防護中的核心的後端原則。</span><span class="sxs-lookup"><span data-stu-id="5619f-124">Security playbooks are back-end policies that are at the heart of automation in Microsoft Threat Protection.</span></span> <span data-ttu-id="5619f-125">常見的真實世界的安全性案例根據空調中提供安全性 playbooks。</span><span class="sxs-lookup"><span data-stu-id="5619f-125">The security playbooks provided in AIR are based on common real-world security scenarios.</span></span> <span data-ttu-id="5619f-126">當組織內就會觸發警示時，就會自動啟動安全性 playbook。</span><span class="sxs-lookup"><span data-stu-id="5619f-126">A security playbook is launched automatically when an alert is triggered within your organization.</span></span> <span data-ttu-id="5619f-127">之後會觸發警示，自動執行相關聯的 playbook。</span><span class="sxs-lookup"><span data-stu-id="5619f-127">Once the alert triggers, the associated playbook is run automatically.</span></span> <span data-ttu-id="5619f-128">Playbook 執行和調查] 中，查看所有關聯的中繼資料 （包括電子郵件、 使用者、 主旨、 寄件者等等），並根據其所發現的錯誤、 建議的動作，以控制並降低可以採取貴組織的安全性小組威脅。</span><span class="sxs-lookup"><span data-stu-id="5619f-128">The playbook runs an investigation, looking at all the associated metadata (including email messages, users, subjects, senders, etc.) and, based on its findings, recommends a set of actions that your organization's security team can take to control and mitigate the threat.</span></span> 

<span data-ttu-id="5619f-129">您會看到與空調安全性 playbooks 專為今天處理最常見的威脅該組織圖像。</span><span class="sxs-lookup"><span data-stu-id="5619f-129">The security playbooks you'll get with AIR are designed to tackle the most frequent threats that organizations face today.</span></span> <span data-ttu-id="5619f-130">他們根據安全性作業和事件回應小組，包括協助防禦 Microsoft 和我們的客戶資產的輸入。</span><span class="sxs-lookup"><span data-stu-id="5619f-130">They're based on input from Security Operations and Incident Response teams, including those who help defend Microsoft and our customers assets.</span></span>

### <a name="security-playbooks-are-rolling-out-in-phases"></a><span data-ttu-id="5619f-131">安全性 playbooks 已推出階段</span><span class="sxs-lookup"><span data-stu-id="5619f-131">Security playbooks are rolling out in phases</span></span>

<span data-ttu-id="5619f-132">航空的一部分，安全性 playbooks 已推出階段</span><span class="sxs-lookup"><span data-stu-id="5619f-132">As part of AIR, security playbooks are rolling out in phases</span></span>

- <span data-ttu-id="5619f-133">**階段 1 (年 4 月 2019)**: Playbooks 包含建議的安全性管理員檢閱和核准的動作。</span><span class="sxs-lookup"><span data-stu-id="5619f-133">**Phase 1 (April 2019)**: Playbooks include recommendations for actions that security administrators review and approve.</span></span> 

- <span data-ttu-id="5619f-134">**階段 2 (年 6 月 2019)**: 安全性系統管理員必須設定安全性 playbooks 不需要管理互動，自動採取動作的選項。</span><span class="sxs-lookup"><span data-stu-id="5619f-134">**Phase 2 (June 2019)**: Security administrators will have the option to configure security playbooks to take action automatically, without administrative interaction.</span></span>

<span data-ttu-id="5619f-135">階段 1 將會包含下列 playbooks:</span><span class="sxs-lookup"><span data-stu-id="5619f-135">Phase 1 will include the following playbooks:</span></span>
- <span data-ttu-id="5619f-136">使用者報告的釣魚程式訊息</span><span class="sxs-lookup"><span data-stu-id="5619f-136">User-reported phish message</span></span>
- <span data-ttu-id="5619f-137">URL 按一下 verdict 變更</span><span class="sxs-lookup"><span data-stu-id="5619f-137">URL click verdict change</span></span> 
- <span data-ttu-id="5619f-138">偵測到的惡意程式碼後傳遞 （惡意程式碼時能量光束）</span><span class="sxs-lookup"><span data-stu-id="5619f-138">Malware detected post-delivery (Malware ZAP)</span></span>
- <span data-ttu-id="5619f-139">釣魚程式偵測到後續傳遞 ZAP （Phish 時能量光束）</span><span class="sxs-lookup"><span data-stu-id="5619f-139">Phish detected post-delivery ZAP (Phish ZAP)</span></span>
- <span data-ttu-id="5619f-140">手動的電子郵件調查 （使用威脅總管）</span><span class="sxs-lookup"><span data-stu-id="5619f-140">Manual e-mail investigations (using Threat Explorer)</span></span>

<span data-ttu-id="5619f-141">數個其他 playbooks 計劃階段 2 中。</span><span class="sxs-lookup"><span data-stu-id="5619f-141">Several other playbooks are planned for Phase 2.</span></span>

### <a name="playbooks-include-investigation-and-recommendations"></a><span data-ttu-id="5619f-142">Playbooks 包括調查與建議</span><span class="sxs-lookup"><span data-stu-id="5619f-142">Playbooks include investigation and recommendations</span></span>

<span data-ttu-id="5619f-143">每個 playbook 包括：</span><span class="sxs-lookup"><span data-stu-id="5619f-143">Each playbook includes:</span></span> 
- <span data-ttu-id="5619f-144">根和調查]，</span><span class="sxs-lookup"><span data-stu-id="5619f-144">a root investigation,</span></span> 
- <span data-ttu-id="5619f-145">識別並對應其他潛在威脅，所採取的步驟和</span><span class="sxs-lookup"><span data-stu-id="5619f-145">steps taken to identify and correlate other potential threats, and</span></span> 
- <span data-ttu-id="5619f-146">建議的威脅修復動作。</span><span class="sxs-lookup"><span data-stu-id="5619f-146">recommended threat remediation actions.</span></span>

<span data-ttu-id="5619f-147">每個高階步驟包括提供深層、 詳細又詳盡回應威脅時所執行的許多子步驟。</span><span class="sxs-lookup"><span data-stu-id="5619f-147">Each high-level step includes many sub-steps that are executed to provide a deep, detailed, and exhaustive response to threats.</span></span>

## <a name="example-user-reported-phish-message"></a><span data-ttu-id="5619f-148">範例： 使用者回報的釣魚程式訊息</span><span class="sxs-lookup"><span data-stu-id="5619f-148">Example: User-reported phish message</span></span>

<span data-ttu-id="5619f-149">當您組織中的使用者送出的電子郵件訊息，並向 Microsoft 報告所使用的[報告訊息增益集以進行 Outlook 或 Outlook Web Access](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="5619f-149">When a user in your organization submits an email message and reports it to Microsoft by using the [Report Message add-in for Outlook or Outlook Web Access](enable-the-report-message-add-in.md).</span></span> <span data-ttu-id="5619f-150">這樣會觸發系統架構資訊性警示，自動啟動 [調查 playbook。</span><span class="sxs-lookup"><span data-stu-id="5619f-150">This triggers a system-based informational alert that automatically launches the investigation playbook.</span></span>

<span data-ttu-id="5619f-151">在根調查階段中，會評估的電子郵件的各個層面。</span><span class="sxs-lookup"><span data-stu-id="5619f-151">During the root investigation phase, various aspects of the email are assessed.</span></span> <span data-ttu-id="5619f-152">這些包括：</span><span class="sxs-lookup"><span data-stu-id="5619f-152">These include:</span></span>
- <span data-ttu-id="5619f-153">可能需有哪些類型的威脅它決定;</span><span class="sxs-lookup"><span data-stu-id="5619f-153">A determination about what type of threat it might be;</span></span>
- <span data-ttu-id="5619f-154">寄件者; 它</span><span class="sxs-lookup"><span data-stu-id="5619f-154">Who sent it;</span></span>
- <span data-ttu-id="5619f-155">其中電子郵件寄件地 （傳送基礎結構）;</span><span class="sxs-lookup"><span data-stu-id="5619f-155">Where the email was sent from (sending infrastructure);</span></span>
- <span data-ttu-id="5619f-156">電子郵件的其他執行個體是否已傳遞或封鎖;</span><span class="sxs-lookup"><span data-stu-id="5619f-156">Whether other instances of the email were delivered or blocked;</span></span>
- <span data-ttu-id="5619f-157">從我們分析師; 評估</span><span class="sxs-lookup"><span data-stu-id="5619f-157">An assessment from our analysts;</span></span>
- <span data-ttu-id="5619f-158">是否任何已知的行銷活動; 相關聯的電子郵件</span><span class="sxs-lookup"><span data-stu-id="5619f-158">Whether the email is associated with any known campaigns;</span></span>
- <span data-ttu-id="5619f-159">等等。</span><span class="sxs-lookup"><span data-stu-id="5619f-159">and more.</span></span>

<span data-ttu-id="5619f-160">根調查完成後，playbook 會提供建議採取的動作清單。</span><span class="sxs-lookup"><span data-stu-id="5619f-160">After the root investigation is complete, the playbook provides a list of recommended actions to take.</span></span>
  
<span data-ttu-id="5619f-161">接下來，數個威脅調查並狩獵步驟執行：</span><span class="sxs-lookup"><span data-stu-id="5619f-161">Next, several threat investigation and hunting steps are executed:</span></span>

- <span data-ttu-id="5619f-162">要搜尋其他電子郵件叢集中的類似電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="5619f-162">Similar email messages in other email clusters are searched.</span></span>
- <span data-ttu-id="5619f-163">其他平台，例如[Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)可共用接收的訊號。</span><span class="sxs-lookup"><span data-stu-id="5619f-163">The signal is shared with other platforms, such as [Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection).</span></span>
- <span data-ttu-id="5619f-164">決定在任何使用者是否按下透過任何可疑的電子郵件訊息中的連結。</span><span class="sxs-lookup"><span data-stu-id="5619f-164">A determination is made on whether any users have clicked through any links in suspicious email messages.</span></span>
- <span data-ttu-id="5619f-165">檢查完成跨 Office 365 Exchange Online Protection ([EOP]) (eop/exchange-線上-保護-eop.md) 和 Office 365 進階 Therat 保護 ([ATP]) (office-365-atp.md) 若要查看是否有任何其他類似的訊息所報告的使用者。</span><span class="sxs-lookup"><span data-stu-id="5619f-165">A check is done across Office 365 Exchange Online Protection ([EOP])(eop/exchange-online-protection-eop.md) and Office 365 Advanced Therat Protection ([ATP])(office-365-atp.md) to see if there are any other similar messages reported by users.</span></span>
- <span data-ttu-id="5619f-166">若要查看是否使用者已遭洩露完成查核。</span><span class="sxs-lookup"><span data-stu-id="5619f-166">A check is done to see if a user has been compromised.</span></span> <span data-ttu-id="5619f-167">這項檢查跨[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)和[Azure Active Directory](https://docs.microsoft.com/azure/active-directory)，相互關聯任何相關的使用者活動異常運用訊號。</span><span class="sxs-lookup"><span data-stu-id="5619f-167">This check leverages signals across [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security) and [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlating any related user activity anomalies.</span></span> 

<span data-ttu-id="5619f-168">狩獵階段風險和威脅指派給各種狩獵步驟。</span><span class="sxs-lookup"><span data-stu-id="5619f-168">During the hunting phase, risks and threats are assigned to various hunting steps.</span></span>  

<span data-ttu-id="5619f-169">修復為 playbook 的最後一個階段。</span><span class="sxs-lookup"><span data-stu-id="5619f-169">Remediation is the final phase of the playbook.</span></span> <span data-ttu-id="5619f-170">在這個階段，採取補救步驟為止，根據 theinvestigation 和狩獵階段。</span><span class="sxs-lookup"><span data-stu-id="5619f-170">During this phase, remediation steps are taken, based on theinvestigation and hunting phases.</span></span>  

## <a name="getting-started"></a><span data-ttu-id="5619f-171">快速入門</span><span class="sxs-lookup"><span data-stu-id="5619f-171">Getting started</span></span>

<span data-ttu-id="5619f-172">若要為 Office 365 全域系統管理員、 安全性系統管理員或安全性讀取者存取您調查，移至 Office 365 安全性 & 合規性中心 ([https://protection.office.com](https://protection.office.com))，並登入。</span><span class="sxs-lookup"><span data-stu-id="5619f-172">To access your investigations, as an Office 365 global administrator, security administrator, or security reader, Go to the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span> <span data-ttu-id="5619f-173">接著執行下列其中一項作業：</span><span class="sxs-lookup"><span data-stu-id="5619f-173">Then, do one of the following:</span></span>

- <span data-ttu-id="5619f-174">在左導覽中，移至 [**威脅管理** > **調查**。</span><span class="sxs-lookup"><span data-stu-id="5619f-174">In the left navigation, go to **Threat management** > **Investigations**.</span></span>

    <span data-ttu-id="5619f-175">或</span><span class="sxs-lookup"><span data-stu-id="5619f-175">or</span></span>

- <span data-ttu-id="5619f-176">威脅管理儀表板，請造訪 (在 [安全性 & 合規性中心，移至 [**威脅管理** > **儀表板**)。</span><span class="sxs-lookup"><span data-stu-id="5619f-176">Visit the Threat management dashboard (In the Security & Compliance Center, go to **Threat management** > **Dashboard**).</span></span>

![空調 widget](media/air-widgets.png)

<span data-ttu-id="5619f-178">[安全性儀表板](security-dashboard.md)的上方會出現您航空 widget。</span><span class="sxs-lookup"><span data-stu-id="5619f-178">Your AIR widgets will appear across the top of the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="5619f-179">選取 [開始] 小工具。</span><span class="sxs-lookup"><span data-stu-id="5619f-179">Select a widget to get started.</span></span>

<span data-ttu-id="5619f-180">您也可能會存取 invesitgation 直接從的相關警示。</span><span class="sxs-lookup"><span data-stu-id="5619f-180">You may also access an invesitgation directly from the related Alerts.</span></span>

### <a name="automated-investigations"></a><span data-ttu-id="5619f-181">自動化的調查</span><span class="sxs-lookup"><span data-stu-id="5619f-181">Automated investigations</span></span>

<span data-ttu-id="5619f-182">[自動化的調查] 頁面上顯示貴組織的調查和其目前狀態。</span><span class="sxs-lookup"><span data-stu-id="5619f-182">The automated investigations page shows your organization's investigations and their current states.</span></span>

![空調主要調查頁面](media/air-maininvestigationpage.png) 
  
<span data-ttu-id="5619f-184">您可以：</span><span class="sxs-lookup"><span data-stu-id="5619f-184">You can:</span></span>
- <span data-ttu-id="5619f-185">直接前往調查 （選取**調查識別碼**）。</span><span class="sxs-lookup"><span data-stu-id="5619f-185">Navigate directly to an investigation (select an **Investigation ID**).</span></span>
- <span data-ttu-id="5619f-186">套用篩選。</span><span class="sxs-lookup"><span data-stu-id="5619f-186">Apply filters.</span></span> <span data-ttu-id="5619f-187">選擇 [從**調查類型**、**時間範圍**、**狀態**或這些項目的組合。</span><span class="sxs-lookup"><span data-stu-id="5619f-187">Choose from **Investigation Type**, **Time range**, **Status**, or a combination of these.</span></span>
- <span data-ttu-id="5619f-188">將資料匯出至 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="5619f-188">Export the data to a CSV file.</span></span>

### <a name="investigation-graph"></a><span data-ttu-id="5619f-189">調查圖</span><span class="sxs-lookup"><span data-stu-id="5619f-189">Investigation graph</span></span>

<span data-ttu-id="5619f-190">當您開啟特定調查時，您會看到 [調查 graph] 頁面。</span><span class="sxs-lookup"><span data-stu-id="5619f-190">When you open a specific investigation, you see the investigation graph page.</span></span> <span data-ttu-id="5619f-191">此頁面會顯示所有不同的實體： 電子郵件、 使用者 （和其活動），以及已自動調查一部分警示所觸發的裝置。</span><span class="sxs-lookup"><span data-stu-id="5619f-191">This page shows all the different entities: email messages, users (and their activities), and devices that were automatically investigated as part of the alert that was triggered.</span></span>

![空調調查 graph 頁面](media/air-investigationgraphpage.png)

<span data-ttu-id="5619f-193">您可以：</span><span class="sxs-lookup"><span data-stu-id="5619f-193">You can:</span></span>
- <span data-ttu-id="5619f-194">取得目前調查的視覺化概觀。</span><span class="sxs-lookup"><span data-stu-id="5619f-194">Get a visual overview of the current investigation.</span></span>
- <span data-ttu-id="5619f-195">檢視調查計時的摘要。</span><span class="sxs-lookup"><span data-stu-id="5619f-195">View a summary of the investigation timings.</span></span>
- <span data-ttu-id="5619f-196">若要檢視該節點的詳細資料視覺效果中選取節點。</span><span class="sxs-lookup"><span data-stu-id="5619f-196">Select a node in the visualization to view details for that node.</span></span>
- <span data-ttu-id="5619f-197">若要檢視該索引標籤的詳細資訊，在頂端選取] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="5619f-197">Select a tab across the top to view details for that tab.</span></span>

### <a name="alert-investigation"></a><span data-ttu-id="5619f-198">警示調查</span><span class="sxs-lookup"><span data-stu-id="5619f-198">Alert investigation</span></span>

<span data-ttu-id="5619f-199">調查的 [**提醒**] 索引標籤中，您可以看到與調查有關的提醒。</span><span class="sxs-lookup"><span data-stu-id="5619f-199">On the **Alerts** tab for an investigation, you can see alerts relevant to the investigation.</span></span> <span data-ttu-id="5619f-200">詳細資料包含觸發調查警示和其他警示，例如風險登入，大量下載等的相互關聯的調查。</span><span class="sxs-lookup"><span data-stu-id="5619f-200">Details include the alert that triggered the investigation and other alerts, such as risky sign-in, mass download, etc., that are correlated to the investigation.</span></span> <span data-ttu-id="5619f-201">此頁面上，從安全性分析師也可以檢視其他詳細資料上獲取個別警示。</span><span class="sxs-lookup"><span data-stu-id="5619f-201">From this page, a security analyst can also view additional details on individual alerts.</span></span>

![產生提醒] 頁面上](media/air-investigationalertspage.png)

<span data-ttu-id="5619f-203">您可以：</span><span class="sxs-lookup"><span data-stu-id="5619f-203">You can:</span></span>
- <span data-ttu-id="5619f-204">取得目前的觸發警示和任何相關聯的警示的視覺化概觀。</span><span class="sxs-lookup"><span data-stu-id="5619f-204">Get a visual overview of the current triggering alert and any associated alerts.</span></span>
- <span data-ttu-id="5619f-205">若要開啟 [顯示完整警示的詳細資訊的飛出視窗頁面清單中，選取 [警示。</span><span class="sxs-lookup"><span data-stu-id="5619f-205">Select an alert in the list to open a fly-out page that shows full alert details.</span></span>

### <a name="email-investigation"></a><span data-ttu-id="5619f-206">電子郵件調查</span><span class="sxs-lookup"><span data-stu-id="5619f-206">Email investigation</span></span>

<span data-ttu-id="5619f-207">在調查的**電子郵件**] 索引標籤中，您可以看到識別為調查的一部分的所有電子郵件叢集。</span><span class="sxs-lookup"><span data-stu-id="5619f-207">On the **Email** tab for an investigation, you can see all the email clusters identified as part of the investigation.</span></span> 

<span data-ttu-id="5619f-208">指定大量的電子郵件組織中的使用者傳送和接收的程序</span><span class="sxs-lookup"><span data-stu-id="5619f-208">Given the sheer volume of email that users in an organization send and receive, the process of</span></span> 
- <span data-ttu-id="5619f-209">根據類似的屬性，從郵件標頭、 內文、 URL 和附件; 叢集的電子郵件</span><span class="sxs-lookup"><span data-stu-id="5619f-209">clustering email messages based on similar attributes from a message header, body, URL and attachment;</span></span> 
- <span data-ttu-id="5619f-210">從良好的電子郵件; 分隔惡意電子郵件和</span><span class="sxs-lookup"><span data-stu-id="5619f-210">separating malicious email from the good email; and</span></span> 
- <span data-ttu-id="5619f-211">對惡意電子郵件採取的動作</span><span class="sxs-lookup"><span data-stu-id="5619f-211">taking action on malicious email messages</span></span> 

<span data-ttu-id="5619f-212">可能需要多個小時。</span><span class="sxs-lookup"><span data-stu-id="5619f-212">can take many hours.</span></span> <span data-ttu-id="5619f-213">空調現在會自動執行此程序，儲存您的組織安全性小組時間和精力。</span><span class="sxs-lookup"><span data-stu-id="5619f-213">AIR now automates this process, saving your organization's security team time and effort.</span></span> 

<span data-ttu-id="5619f-214">做為範例，請考慮下列案例。</span><span class="sxs-lookup"><span data-stu-id="5619f-214">As an example, consider the following scenario.</span></span> <span data-ttu-id="5619f-215">三個電子郵件的第一個叢集已被視為是釣魚程式。</span><span class="sxs-lookup"><span data-stu-id="5619f-215">The first cluster of three email messages were deemed to be phish.</span></span> <span data-ttu-id="5619f-216">類似郵件具有相同的 IP 和主旨的另一個叢集已找到，而且視為惡意，有些已識別為釣魚程式初始偵測期間。</span><span class="sxs-lookup"><span data-stu-id="5619f-216">Another cluster of similar messages with the same IP and subject was found and considered  malicious, as some of them were identified as phish during initial detection.</span></span> 

![空調電子郵件調查] 頁面](media/air-investigationemailpage.png)

<span data-ttu-id="5619f-218">您可以：</span><span class="sxs-lookup"><span data-stu-id="5619f-218">You can:</span></span>
- <span data-ttu-id="5619f-219">取得目前的叢集結果和威脅找到的視覺化概觀。</span><span class="sxs-lookup"><span data-stu-id="5619f-219">Get a visual overview of the current clustering results and threats found.</span></span>
- <span data-ttu-id="5619f-220">按一下 [叢集實體或威脅清單] 以開啟飛出視窗] 頁面上顯示的完整警示的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="5619f-220">Click a cluster entity or a threat list to open a fly-out page that shows the full alert details.</span></span>

![空調調查的電子郵件與彈出式詳細資料](media/air-investigationemailpageflyoutdetails.png)

<span data-ttu-id="5619f-222">\* 附註： 在電子郵件的內容，您可能會看到大量異常威脅表面調查的一部分。</span><span class="sxs-lookup"><span data-stu-id="5619f-222">\*Note: In the context of email, you may see a volume anomaly threat surface as part of the investigation.</span></span> <span data-ttu-id="5619f-223">磁碟區異常指出相較於舊版項調查事件時間前後的類似電子郵件中的特殊圖文集。</span><span class="sxs-lookup"><span data-stu-id="5619f-223">A volume anomaly indicates a spike in similar emails around the investigation event time compared to earlier timeframes.</span></span> <span data-ttu-id="5619f-224">此特殊圖文集的特性類似的電子郵件流量 (例如主旨] 和 [寄件者的網域，本文相似性和寄件者 IP) 是一般的電子郵件行銷活動或攻擊的開始。</span><span class="sxs-lookup"><span data-stu-id="5619f-224">This spike in email traffic with similar characteristics (e.g. subject and sender domain, body similarity and sender IP) is typical of the start of email campaigns or attacks.</span></span> <span data-ttu-id="5619f-225">不過，大量和 spom 電子郵件行銷活動時間也共用這些特性。</span><span class="sxs-lookup"><span data-stu-id="5619f-225">However, bulk and spom email campaigns at times also share these characteristics.</span></span> <span data-ttu-id="5619f-226">磁碟區異常代表潛在威脅，並據此可能少數嚴重相較惡意程式碼或釣魚程式的威脅，用來識別的防毒引擎、 爆炸或惡意的信譽。</span><span class="sxs-lookup"><span data-stu-id="5619f-226">Volume anomalies represent a potential threat, and accordingly could be less severe compared to malware or phish threats that are identified using anti-virus engines, detonation or malicious reputation.</span></span>

### <a name="user-investigation"></a><span data-ttu-id="5619f-227">使用者調查</span><span class="sxs-lookup"><span data-stu-id="5619f-227">User investigation</span></span>

<span data-ttu-id="5619f-228">在 [**使用者**] 索引標籤中，您可以看到識別為調查的一部分的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="5619f-228">On the **Users** tab, you can see all the users identified as part of the investigation.</span></span> 

<span data-ttu-id="5619f-229">例如，在下列映像，空調已識別危害和異常根據新的收件匣規則所建立的指標。</span><span class="sxs-lookup"><span data-stu-id="5619f-229">For example, in the following image, AIR has identified indicators of compromise and anomalies based on a new inbox rule that was created.</span></span> <span data-ttu-id="5619f-230">調查的其他詳細資料 （辨識項） 可透過此危害的指標] 索引標籤內的詳細檢視，而且異常也可包含從[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)的異常偵測。</span><span class="sxs-lookup"><span data-stu-id="5619f-230">Additional details (evidence) of the investigation are available through detailed views within this tab. Indicators of compromise and anomalies may also include anomaly detections from [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span></span>

![空調調查的使用者] 頁面](media/air-investigationuserspage.png)

<span data-ttu-id="5619f-232">您可以：</span><span class="sxs-lookup"><span data-stu-id="5619f-232">You can:</span></span>
- <span data-ttu-id="5619f-233">取得已識別的使用者結果與風險找到的視覺化概觀。</span><span class="sxs-lookup"><span data-stu-id="5619f-233">Get a visual overview of identified user results and risks found.</span></span>
- <span data-ttu-id="5619f-234">選取使用者，若要開啟 [飛出視窗] 頁面上顯示的完整警示的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="5619f-234">Select a user to open a fly-out page that shows the full alert details.</span></span>

### <a name="machine-investigation"></a><span data-ttu-id="5619f-235">機器調查</span><span class="sxs-lookup"><span data-stu-id="5619f-235">Machine investigation</span></span>

<span data-ttu-id="5619f-236">**機器**索引標籤上，您可以看到識別為調查的一部分的所有機器。</span><span class="sxs-lookup"><span data-stu-id="5619f-236">On the **Machines** tab, you can see all the machines identified as part of the investigation.</span></span> 

![空調調查機器頁面](media/air-investigationmachinepage.png)

<span data-ttu-id="5619f-238">調查的一部分，空調相互關聯至裝置的電子郵件威脅。</span><span class="sxs-lookup"><span data-stu-id="5619f-238">As part of the investigation, AIR correlates email threats to devices.</span></span> <span data-ttu-id="5619f-239">例如，調查傳遞檔案之間的雜湊到[Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)調查。</span><span class="sxs-lookup"><span data-stu-id="5619f-239">For example, an investigation passes a file hash across to [Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) to investigate.</span></span> <span data-ttu-id="5619f-240">這可讓您的使用者相關機器的自動化調查，而且可協助確保已解決威脅，同時在雲端和在裝置。</span><span class="sxs-lookup"><span data-stu-id="5619f-240">This allows for automated investigation of relevant machines for your users and helps to ensure that threats are addressed both in the cloud and across your devices.</span></span> 

<span data-ttu-id="5619f-241">您可以：</span><span class="sxs-lookup"><span data-stu-id="5619f-241">You can:</span></span>
- <span data-ttu-id="5619f-242">取得目前機器和威脅找到的視覺化概觀。</span><span class="sxs-lookup"><span data-stu-id="5619f-242">Get a visual overview of the current machines and threats found.</span></span>
- <span data-ttu-id="5619f-243">選取 [若要開啟 [檢視電腦，到 Windows Defender ATP 安全中心相關的[Windows Defender ATP 調查](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/automated-investigations-windows-defender-advanced-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="5619f-243">Select a machine to open a view that into the related [Windows Defender ATP investigations](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/automated-investigations-windows-defender-advanced-threat-protection) in the Windows Defender ATP Security Center.</span></span>

### <a name="entity-investigation"></a><span data-ttu-id="5619f-244">實體調查</span><span class="sxs-lookup"><span data-stu-id="5619f-244">Entity investigation</span></span>

<span data-ttu-id="5619f-245">在 [**實體**] 索引標籤上，您可以看到識別為調查的一部分的所有機器。</span><span class="sxs-lookup"><span data-stu-id="5619f-245">On the **Entities** tab, you can see all the machines identified as part of the investigation.</span></span> 

<span data-ttu-id="5619f-246">在這裡，您可以看到 investigated 的實體。</span><span class="sxs-lookup"><span data-stu-id="5619f-246">Here, you can see the investigated entities.</span></span> <span data-ttu-id="5619f-247">您可以檢視類型的實體，例如電子郵件、 叢集、 IP 位址、 使用者和更多詳細資料。</span><span class="sxs-lookup"><span data-stu-id="5619f-247">You can see details of the types of entities, such as email messages, clusters, IP addresses, users, and more.</span></span> <span data-ttu-id="5619f-248">您也可以查看多少實體進行分析，且威脅，與每個相關聯。</span><span class="sxs-lookup"><span data-stu-id="5619f-248">You can also see how many entities were analyzed, and the threats that were associated with each.</span></span> 

![空調調查實體] 頁面上](media/air-investigationentitiespage.png)

<span data-ttu-id="5619f-250">您可以：</span><span class="sxs-lookup"><span data-stu-id="5619f-250">You can:</span></span>
- <span data-ttu-id="5619f-251">取得調查實體和威脅找到的視覺化概觀。</span><span class="sxs-lookup"><span data-stu-id="5619f-251">Get a visual overview of the investigation entities and threats found.</span></span>
- <span data-ttu-id="5619f-252">選擇要開啟的飛出視窗頁面會顯示相關的實體詳細資料的實體。</span><span class="sxs-lookup"><span data-stu-id="5619f-252">Select an entity to open a fly-out page that shows the related entity detail.</span></span>

![空調調查實體詳細資料](media/air-investigationsentitiespagedetails.png)

### <a name="playbook-log"></a><span data-ttu-id="5619f-254">Playbook 記錄檔</span><span class="sxs-lookup"><span data-stu-id="5619f-254">Playbook log</span></span>

<span data-ttu-id="5619f-255">在 [**記錄**] 索引標籤中，您可以看到調查期間所發生的所有 playbook 步驟。</span><span class="sxs-lookup"><span data-stu-id="5619f-255">On the **Log** tab, you can see all the playbook steps that have occurred during the investigation.</span></span> <span data-ttu-id="5619f-256">記錄檔擷取由 Office 365 自動調查功能完成空調一部分的所有動作的完整詳細目錄。</span><span class="sxs-lookup"><span data-stu-id="5619f-256">The log captures a complete inventory of all actions completed by Office 365 auto-investigation capabilities as part of AIR.</span></span> <span data-ttu-id="5619f-257">它本身、 描述及的實際工期提供清楚的所有所採取的步驟，包括巨集指令檢視從開始到完成。</span><span class="sxs-lookup"><span data-stu-id="5619f-257">It provides a clear view of all the steps taken, including the Action itself, a description and the duration of the actual from start to finish.</span></span> 

![空調調查記錄頁面](media/air-investigationlogpage.png)

<span data-ttu-id="5619f-259">您可以：</span><span class="sxs-lookup"><span data-stu-id="5619f-259">You can:</span></span>
- <span data-ttu-id="5619f-260">取得看到所採取的 playbook 步驟的視覺化概觀。</span><span class="sxs-lookup"><span data-stu-id="5619f-260">Get see a visual overview of the playbook steps taken.</span></span>
- <span data-ttu-id="5619f-261">將結果匯出至 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="5619f-261">Export the results to a CSV file.</span></span>
- <span data-ttu-id="5619f-262">篩選的檢視。</span><span class="sxs-lookup"><span data-stu-id="5619f-262">Filter the view.</span></span>

### <a name="recommended-actions"></a><span data-ttu-id="5619f-263">建議的動作</span><span class="sxs-lookup"><span data-stu-id="5619f-263">Recommended actions</span></span>

<span data-ttu-id="5619f-264">在 [**動作**] 索引標籤中，您可以看到建議的修復後調查已完成的所有 playbook 動作。</span><span class="sxs-lookup"><span data-stu-id="5619f-264">On the **Actions** tab, you can see all the playbook actions that are recommended for remediation after the investigation has completed.</span></span> 

<span data-ttu-id="5619f-265">動作擷取 Microsoft 建議您採取調查結尾處的步驟。</span><span class="sxs-lookup"><span data-stu-id="5619f-265">Actions capture the steps Microsoft recommends you take at the end of a investigation.</span></span> <span data-ttu-id="5619f-266">您可以藉由選取一或多個動作採取以下修復動作。</span><span class="sxs-lookup"><span data-stu-id="5619f-266">You can take remediation actions here by selecting one or more actions.</span></span> <span data-ttu-id="5619f-267">按一下 [**核准**可讓修復以開始。</span><span class="sxs-lookup"><span data-stu-id="5619f-267">Clicking **Approve** will allow remediation to begin.</span></span> <span data-ttu-id="5619f-268">（適當的權限將會需要。</span><span class="sxs-lookup"><span data-stu-id="5619f-268">(Appropriate permissions will be required.</span></span> <span data-ttu-id="5619f-269">例如，安全性讀取者可以檢視動作，但不是核准。）</span><span class="sxs-lookup"><span data-stu-id="5619f-269">For example, a Security Reader can view actions but not approve them.)</span></span>  

![空調調查動作] 頁面上](media/air-investigationactionspage.png)

<span data-ttu-id="5619f-271">您可以：</span><span class="sxs-lookup"><span data-stu-id="5619f-271">You can:</span></span>
- <span data-ttu-id="5619f-272">取得 playbook 建議動作的視覺化概觀。</span><span class="sxs-lookup"><span data-stu-id="5619f-272">Get a visual overview of the playbook-recommended actions.</span></span>
- <span data-ttu-id="5619f-273">選取單一動作或多個動作。</span><span class="sxs-lookup"><span data-stu-id="5619f-273">Select a single action or multiple actions.</span></span>
- <span data-ttu-id="5619f-274">核准或拒絕建議的動作與註解。</span><span class="sxs-lookup"><span data-stu-id="5619f-274">Approve or reject recommended actions with comments.</span></span>
- <span data-ttu-id="5619f-275">將結果匯出至 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="5619f-275">Export the results to a CSV file.</span></span>
- <span data-ttu-id="5619f-276">篩選的檢視。</span><span class="sxs-lookup"><span data-stu-id="5619f-276">Filter the view.</span></span>

## <a name="how-to-get-air"></a><span data-ttu-id="5619f-277">如何取得航空</span><span class="sxs-lookup"><span data-stu-id="5619f-277">How to get AIR</span></span>

<span data-ttu-id="5619f-278">目前，Office 365 空調是在預覽中。</span><span class="sxs-lookup"><span data-stu-id="5619f-278">Currently, Office 365 AIR is in preview.</span></span> <span data-ttu-id="5619f-279">Office 365 航空將包含在下列訂閱：</span><span class="sxs-lookup"><span data-stu-id="5619f-279">Office 365 AIR will be included in the following subscriptions:</span></span>

- <span data-ttu-id="5619f-280">Microsoft 365 企業版 E5</span><span class="sxs-lookup"><span data-stu-id="5619f-280">Microsoft 365 Enterprise E5</span></span>
- <span data-ttu-id="5619f-281">Office 365 企業版 E5</span><span class="sxs-lookup"><span data-stu-id="5619f-281">Office 365 Enterprise E5</span></span>
- <span data-ttu-id="5619f-282">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="5619f-282">Microsoft Threat Protection</span></span>
- <span data-ttu-id="5619f-283">Office 365 進階的威脅保護計劃 2</span><span class="sxs-lookup"><span data-stu-id="5619f-283">Office 365 Advanced Threat Protection Plan 2</span></span>

<span data-ttu-id="5619f-284">若要深入了解可用的功能，請造訪[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)。</span><span class="sxs-lookup"><span data-stu-id="5619f-284">To learn more about feature availability, visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>
