---
title: 使用 Office 365 的自動化調查和回應 (AIR)
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/25/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 深入瞭解 Office 365 的高級威脅防護中的自動化調查和回應功能。
ms.openlocfilehash: 4d611d9549ed3f5cda06274ea9209cdc6350ba7b
ms.sourcegitcommit: bac1b5be5db381e6f8d8f652cff1f8ef4d7f6330
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2019
ms.locfileid: "35233330"
---
# <a name="automated-investigation-and-response-air-with-office-365"></a><span data-ttu-id="948d5-103">使用 Office 365 的自動化調查和回應 (AIR)</span><span class="sxs-lookup"><span data-stu-id="948d5-103">Automated Investigation and Response (AIR) with Office 365</span></span>

<span data-ttu-id="948d5-104">自動化調查和回應 (AIR) (目前在公用預覽中, 是許多[Office 365 威脅調查和回應功能](office-365-ti.md)中的一項) 可讓您對目前存在的已知威脅執行自動化調查和修復。</span><span class="sxs-lookup"><span data-stu-id="948d5-104">Automated Investigation and Response (AIR) (currently in public preview as one of many [Office 365 Threat investigation and response capabilities](office-365-ti.md)) enables you to run automated investigation and remediation to well-known threats that exist today.</span></span> <span data-ttu-id="948d5-105">請閱讀本文以取得空氣的總覽, 以及它如何協助您的組織和安全性作業小組更有效率且更有效率地緩解威脅。</span><span class="sxs-lookup"><span data-stu-id="948d5-105">Read this article to get an overview of AIR and how it can help your organization and security operations teams mitigate threats more effectively and efficiently.</span></span> 

<span data-ttu-id="948d5-106">若要深入瞭解何時可以使用 AIR 功能, 請參閱[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)。</span><span class="sxs-lookup"><span data-stu-id="948d5-106">To learn more about when  AIR features will be available, see the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

## <a name="alerts"></a><span data-ttu-id="948d5-107">警示</span><span class="sxs-lookup"><span data-stu-id="948d5-107">Alerts</span></span>

<span data-ttu-id="948d5-108">[警示](alert-policies.md#viewing-alerts)代表安全性作業的觸發器, 小組工作流程的事件回應。</span><span class="sxs-lookup"><span data-stu-id="948d5-108">[Alerts](alert-policies.md#viewing-alerts) represent triggers for security operations team workflows for incident response.</span></span> <span data-ttu-id="948d5-109">將一組適當的提醒設為優先調查, 並確定沒有威脅是 unaddressed 的挑戰。</span><span class="sxs-lookup"><span data-stu-id="948d5-109">Prioritizing the right set of alerts for investigation, while making sure no threats are unaddressed is challenging.</span></span> <span data-ttu-id="948d5-110">手動執行提醒時, 安全性作業小組必須尋找和關聯實體 (例如內容、裝置及使用者) 面臨的威脅。</span><span class="sxs-lookup"><span data-stu-id="948d5-110">When investigations into alerts are performed manually, Security Operations teams must hunt and correlate entities (e.g. content, devices and users) at risk from threats.</span></span> <span data-ttu-id="948d5-111">這類工作與工作流程非常耗時, 且包含多個工具和系統。</span><span class="sxs-lookup"><span data-stu-id="948d5-111">Such tasks and workflows are very time consuming and involve multiple tools and systems.</span></span> <span data-ttu-id="948d5-112">使用 AIR、調查和回應可自動化到重要的安全性和威脅管理提醒, 以自動觸發您的安全性回應行動手冊。</span><span class="sxs-lookup"><span data-stu-id="948d5-112">With AIR, investigation and response are automated into key security and threat management alerts that trigger your security response playbooks automatically.</span></span> 

<span data-ttu-id="948d5-113">在2019年4月的第一版空中推出時, 會自動調查由下列單一事件警示原則產生的警示。</span><span class="sxs-lookup"><span data-stu-id="948d5-113">In the initial release of AIR in April 2019, alerts generated from following single events alert policies will be auto-investigated.</span></span> 

1. <span data-ttu-id="948d5-114">偵測到可能惡意的 URL 按一下</span><span class="sxs-lookup"><span data-stu-id="948d5-114">A potentially malicious URL click was detected</span></span>
2. <span data-ttu-id="948d5-115">使用者將電子郵件報告為網路釣魚網路 \*</span><span class="sxs-lookup"><span data-stu-id="948d5-115">Email reported by user as phish\*</span></span>
3. <span data-ttu-id="948d5-116">包含在傳遞後移除的惡意程式碼的電子郵件</span><span class="sxs-lookup"><span data-stu-id="948d5-116">Email messages containing malware removed after delivery\*</span></span>
4. <span data-ttu-id="948d5-117">包含在傳遞後移除之網路釣魚 Url 的電子郵件</span><span class="sxs-lookup"><span data-stu-id="948d5-117">Email messages containing phish URLs removed after delivery\*</span></span>

> [!NOTE]
> <span data-ttu-id="948d5-118">這些警示會在安全性 & 合規性中心內的個別警示原則中指派「資訊」嚴重性, 並關閉電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="948d5-118">These alerts have been assigned an "Informational" severity in the respective alert policies within the Security & Compliance Center with email notifications turned off.</span></span> <span data-ttu-id="948d5-119">您可以透過 [警示原則] 設定來開啟這些設定。</span><span class="sxs-lookup"><span data-stu-id="948d5-119">These can be turned on through the Alert policy configuration.</span></span>

<span data-ttu-id="948d5-120">若要查看提醒, 請在安全性 & 規範中心中, 選擇 [**警示** > ] [**查看警示**]。</span><span class="sxs-lookup"><span data-stu-id="948d5-120">To view alerts, in the Security & Compliance Center, choose **Alerts** > **View alerts**.</span></span> <span data-ttu-id="948d5-121">選取警示以查看其詳細資料, 然後從那裡使用 [**查看調查**] 連結來移至對應的[調查](#investigation-graph)。</span><span class="sxs-lookup"><span data-stu-id="948d5-121">Select an alert to view its details, and from there, use the **View investigation** link to go to the corresponding [investigation](#investigation-graph).</span></span> <span data-ttu-id="948d5-122">請注意, 預設會在警示查看中隱藏資訊性警示。</span><span class="sxs-lookup"><span data-stu-id="948d5-122">Note that informational alerts are hidden in the alert view by default.</span></span> <span data-ttu-id="948d5-123">若要查看, 您必須變更警示篩選, 以包含資訊性警示。</span><span class="sxs-lookup"><span data-stu-id="948d5-123">To see them, you need to change the alert filtering to include informational alerts.</span></span>

<span data-ttu-id="948d5-124">如果您的組織透過警示管理系統、服務管理系統或安全性資訊和事件管理 (SIEM) 系統365來管理您的安全性警示, 您可以透過電子郵件通知或[透過Office 365 管理活動 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)。</span><span class="sxs-lookup"><span data-stu-id="948d5-124">If your organization manages your security alerts through a alert management system, service management system, or Security Information and Event Management (SIEM) system, you can send Office 365 alerts to that system via either email notification or via the [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> <span data-ttu-id="948d5-125">透過電子郵件或 API 的調查警示通知會包含連結, 以存取安全性 & 規範中心中的警示, 讓指派的安全性系統管理員能快速流覽到調查。</span><span class="sxs-lookup"><span data-stu-id="948d5-125">The investigation alert notifications via email or API will include links to access the alerts in the Security & Compliance Center, enabling the assigned security administrator to navigate quickly to the investigation.</span></span>

![連結至調查的警示](media/air-alerts-page-details.png) 


## <a name="security-playbooks"></a><span data-ttu-id="948d5-127">安全性行動手冊</span><span class="sxs-lookup"><span data-stu-id="948d5-127">Security playbooks</span></span>

<span data-ttu-id="948d5-128">安全性行動手冊是在 Microsoft 威脅防護中, 以自動化為核心的後端原則。</span><span class="sxs-lookup"><span data-stu-id="948d5-128">Security playbooks are back-end policies that are at the heart of automation in Microsoft Threat Protection.</span></span> <span data-ttu-id="948d5-129">AIR 中所提供的安全性行動技巧是根據常見的實際安全性案例。</span><span class="sxs-lookup"><span data-stu-id="948d5-129">The security playbooks provided in AIR are based on common real-world security scenarios.</span></span> <span data-ttu-id="948d5-130">在組織內觸發提醒時, 會自動啟動安全性行動手冊。</span><span class="sxs-lookup"><span data-stu-id="948d5-130">A security playbook is launched automatically when an alert is triggered within your organization.</span></span> <span data-ttu-id="948d5-131">警示觸發後, 會自動執行相關聯的行動手冊。</span><span class="sxs-lookup"><span data-stu-id="948d5-131">Once the alert triggers, the associated playbook is run automatically.</span></span> <span data-ttu-id="948d5-132">行動手冊會執行調查, 查看所有相關聯的中繼資料 (包括電子郵件訊息、使用者、主旨、寄件者等等)。</span><span class="sxs-lookup"><span data-stu-id="948d5-132">The playbook runs an investigation, looking at all the associated metadata (including email messages, users, subjects, senders, etc.).</span></span> <span data-ttu-id="948d5-133">根據行動手冊的結果, AIR 建議您組織的安全小組可採取的一組動作來控制和降低威脅。</span><span class="sxs-lookup"><span data-stu-id="948d5-133">Based on the playbook's findings, AIR recommends a set of actions that your organization's security team can take to control and mitigate the threat.</span></span> 

<span data-ttu-id="948d5-134">您可以使用 AIR 取得的安全性行動行動, 是為了處理目前組織面臨的最常見威脅。</span><span class="sxs-lookup"><span data-stu-id="948d5-134">The security playbooks you'll get with AIR are designed to tackle the most frequent threats that organizations face today.</span></span> <span data-ttu-id="948d5-135">他們是以安全性作業和事件回應小組的輸入為基礎, 包括協助保護 Microsoft 和客戶資產的人員。</span><span class="sxs-lookup"><span data-stu-id="948d5-135">They're based on input from Security Operations and Incident Response teams, including those who help defend Microsoft and our customers assets.</span></span>

### <a name="security-playbooks-are-rolling-out-in-phases"></a><span data-ttu-id="948d5-136">安全性行動手冊是分階段推出</span><span class="sxs-lookup"><span data-stu-id="948d5-136">Security playbooks are rolling out in phases</span></span>

<span data-ttu-id="948d5-137">在空氣中, 安全性行動手冊會分階段推出</span><span class="sxs-lookup"><span data-stu-id="948d5-137">As part of AIR, security playbooks are rolling out in phases</span></span>

- <span data-ttu-id="948d5-138">**階段 1 (2019 年4月)**: 行動手冊包含安全性系統管理員審查及核准之動作的建議。</span><span class="sxs-lookup"><span data-stu-id="948d5-138">**Phase 1 (April 2019)**: Playbooks include recommendations for actions that security administrators review and approve.</span></span> <span data-ttu-id="948d5-139">階段1將包含下列行動手冊:</span><span class="sxs-lookup"><span data-stu-id="948d5-139">Phase 1 will include the following playbooks:</span></span>
    - <span data-ttu-id="948d5-140">使用者報告的網路釣魚郵件</span><span class="sxs-lookup"><span data-stu-id="948d5-140">User-reported phish message</span></span>
    - <span data-ttu-id="948d5-141">URL 按一下 [判定變更]</span><span class="sxs-lookup"><span data-stu-id="948d5-141">URL click verdict change</span></span> 
    - <span data-ttu-id="948d5-142">偵測到傳遞後的惡意程式碼 (惡意程式碼 ZAP)</span><span class="sxs-lookup"><span data-stu-id="948d5-142">Malware detected post-delivery (Malware ZAP)</span></span>
    - <span data-ttu-id="948d5-143">釣魚程式偵測到傳遞後的 ZAP (網路釣魚 ZAP)</span><span class="sxs-lookup"><span data-stu-id="948d5-143">Phish detected post-delivery ZAP (Phish ZAP)</span></span>
    - <span data-ttu-id="948d5-144">手動電子郵件調查 (使用威脅瀏覽器)</span><span class="sxs-lookup"><span data-stu-id="948d5-144">Manual e-mail investigations (using Threat Explorer)</span></span>

- <span data-ttu-id="948d5-145">**階段 2 (2019 的下半年)**: 有幾個新的行動手冊和行動手冊, 以及安全性系統管理員可設定安全性行動的選項, 以自動執行某些動作, 而不需要管理互動。</span><span class="sxs-lookup"><span data-stu-id="948d5-145">**Phase 2 (second half of 2019)**: Several new playbooks and playbook improvements, plus the option for security administrators to configure security playbooks to take some actions automatically without administrative interaction.</span></span> 

### <a name="playbooks-include-investigation-and-recommendations"></a><span data-ttu-id="948d5-146">行動手冊包括調查和建議</span><span class="sxs-lookup"><span data-stu-id="948d5-146">Playbooks include investigation and recommendations</span></span>

<span data-ttu-id="948d5-147">每位行動手冊都包含:</span><span class="sxs-lookup"><span data-stu-id="948d5-147">Each playbook includes:</span></span> 
- <span data-ttu-id="948d5-148">根調查,</span><span class="sxs-lookup"><span data-stu-id="948d5-148">a root investigation,</span></span> 
- <span data-ttu-id="948d5-149">識別及關聯其他潛在威脅所採取的步驟, 以及</span><span class="sxs-lookup"><span data-stu-id="948d5-149">steps taken to identify and correlate other potential threats, and</span></span> 
- <span data-ttu-id="948d5-150">建議的威脅修復動作。</span><span class="sxs-lookup"><span data-stu-id="948d5-150">recommended threat remediation actions.</span></span>

<span data-ttu-id="948d5-151">每個高階步驟都包含許多執行的子步驟, 以提供對威脅的深入、詳細和詳盡的回應。</span><span class="sxs-lookup"><span data-stu-id="948d5-151">Each high-level step includes many sub-steps that are executed to provide a deep, detailed, and exhaustive response to threats.</span></span>

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a><span data-ttu-id="948d5-152">範例: 使用者報告的網路釣魚訊息啟動調查行動手冊</span><span class="sxs-lookup"><span data-stu-id="948d5-152">Example: A user-reported phish message launches an investigation playbook</span></span>

<span data-ttu-id="948d5-153">當貴組織中的使用者使用[Outlook 或 Outlook Web Access 的報告訊息增益集](enable-the-report-message-add-in.md)提交電子郵件訊息並向 Microsoft 報告時, 此報告也會傳送至您的系統, 而且會在使用者彙報的視圖中顯示于 Explorer 中。</span><span class="sxs-lookup"><span data-stu-id="948d5-153">When a user in your organization submits an email message and reports it to Microsoft by using the [Report Message add-in for Outlook or Outlook Web Access](enable-the-report-message-add-in.md), the report is also sent to your system and is visible in Explorer in the User-reported view.</span></span> <span data-ttu-id="948d5-154">此使用者報告的訊息現在會觸發以系統為基礎的資訊報警, 這會自動啟動調查行動手冊。</span><span class="sxs-lookup"><span data-stu-id="948d5-154">This user-reported message now triggers a system-based informational alert, which automatically launches the investigation playbook.</span></span>

<span data-ttu-id="948d5-155">在根調查階段期間, 會評估電子郵件的各個層面。</span><span class="sxs-lookup"><span data-stu-id="948d5-155">During the root investigation phase, various aspects of the email are assessed.</span></span> <span data-ttu-id="948d5-156">這些包括：</span><span class="sxs-lookup"><span data-stu-id="948d5-156">These include:</span></span>
- <span data-ttu-id="948d5-157">判斷可能是何種威脅類型;</span><span class="sxs-lookup"><span data-stu-id="948d5-157">A determination about what type of threat it might be;</span></span>
- <span data-ttu-id="948d5-158">寄件者:</span><span class="sxs-lookup"><span data-stu-id="948d5-158">Who sent it;</span></span>
- <span data-ttu-id="948d5-159">傳送電子郵件的位置 (傳送基礎結構);</span><span class="sxs-lookup"><span data-stu-id="948d5-159">Where the email was sent from (sending infrastructure);</span></span>
- <span data-ttu-id="948d5-160">是否已傳遞或封鎖電子郵件的其他實例;</span><span class="sxs-lookup"><span data-stu-id="948d5-160">Whether other instances of the email were delivered or blocked;</span></span>
- <span data-ttu-id="948d5-161">我們分析師的評估;</span><span class="sxs-lookup"><span data-stu-id="948d5-161">An assessment from our analysts;</span></span>
- <span data-ttu-id="948d5-162">電子郵件是否與任何已知的市場活動相關聯;</span><span class="sxs-lookup"><span data-stu-id="948d5-162">Whether the email is associated with any known campaigns;</span></span>
- <span data-ttu-id="948d5-163">等等。</span><span class="sxs-lookup"><span data-stu-id="948d5-163">and more.</span></span>

<span data-ttu-id="948d5-164">完成根調查後, 行動手冊會提供建議動作的清單, 以供與 it 相關聯的原始電子郵件和實體使用。</span><span class="sxs-lookup"><span data-stu-id="948d5-164">After the root investigation is complete, the playbook provides a list of recommended actions to take on the original email and entities associated with it.</span></span>
  
<span data-ttu-id="948d5-165">接下來, 會執行數個威脅調查和搜尋步驟:</span><span class="sxs-lookup"><span data-stu-id="948d5-165">Next, several threat investigation and hunting steps are executed:</span></span>

- <span data-ttu-id="948d5-166">搜尋其他電子郵件群集中的類似電子郵件。</span><span class="sxs-lookup"><span data-stu-id="948d5-166">Similar email messages in other email clusters are searched.</span></span>
- <span data-ttu-id="948d5-167">信號會與其他平臺共用, 例如[Microsoft DEFENDER ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="948d5-167">The signal is shared with other platforms, such as [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span></span>
- <span data-ttu-id="948d5-168">決定是否有任何使用者按一下過可疑電子郵件中的任何惡意連結。</span><span class="sxs-lookup"><span data-stu-id="948d5-168">A determination is made on whether any users have clicked through any malicious links in suspicious email messages.</span></span>
- <span data-ttu-id="948d5-169">您可以在 Office 365 Exchange Online Protection ([EOP](eop/exchange-online-protection-eop.md)) 和 Office 365 高級威脅防護 ([ATP](office-365-atp.md)) 上進行檢查, 以查看使用者是否會報告其他類似的訊息。</span><span class="sxs-lookup"><span data-stu-id="948d5-169">A check is done across Office 365 Exchange Online Protection ([EOP](eop/exchange-online-protection-eop.md)) and Office 365 Advanced Threat Protection ([ATP](office-365-atp.md)) to see if there are any other similar messages reported by users.</span></span>
- <span data-ttu-id="948d5-170">進行檢查以查看使用者是否遭到破壞。</span><span class="sxs-lookup"><span data-stu-id="948d5-170">A check is done to see if a user has been compromised.</span></span> <span data-ttu-id="948d5-171">此檢查會利用[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)與[Azure Active Directory](https://docs.microsoft.com/azure/active-directory)之間的信號, 關聯任何相關的使用者活動異常。</span><span class="sxs-lookup"><span data-stu-id="948d5-171">This check leverages signals across [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security) and [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlating any related user activity anomalies.</span></span> 

<span data-ttu-id="948d5-172">在搜尋階段期間, 會將風險和威脅指派給各種搜尋步驟。</span><span class="sxs-lookup"><span data-stu-id="948d5-172">During the hunting phase, risks and threats are assigned to various hunting steps.</span></span> 

<span data-ttu-id="948d5-173">修復是行動手冊的最後階段。</span><span class="sxs-lookup"><span data-stu-id="948d5-173">Remediation is the final phase of the playbook.</span></span> <span data-ttu-id="948d5-174">在這個階段期間, 會根據調查和搜尋階段採取補救措施。</span><span class="sxs-lookup"><span data-stu-id="948d5-174">During this phase, remediation steps are taken, based on the investigation and hunting phases.</span></span> 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a><span data-ttu-id="948d5-175">範例: 安全性系統管理員觸發來自威脅瀏覽器的調查</span><span class="sxs-lookup"><span data-stu-id="948d5-175">Example: A security administrator triggers an investigation from Threat Explorer</span></span>

<span data-ttu-id="948d5-176">除了由警示觸發的自動調查之外, 貴組織的安全性作業小組也可以在[威脅瀏覽器](use-explorer-in-security-and-compliance.md)的視圖中觸發自動調查。</span><span class="sxs-lookup"><span data-stu-id="948d5-176">In addition to automatic investigations that are triggered by an alert, your organization's security operations team can trigger an automatic investigation from a view in [Threat Explorer](use-explorer-in-security-and-compliance.md).</span></span>

<span data-ttu-id="948d5-177">例如, 假設您在瀏覽器中查看使用者所報告的郵件。</span><span class="sxs-lookup"><span data-stu-id="948d5-177">For example, suppose that you are viewing data in Explorer about user-reported messages.</span></span> <span data-ttu-id="948d5-178">您可以選取結果清單中的專案, 然後按一下 [**調查**]。</span><span class="sxs-lookup"><span data-stu-id="948d5-178">You can select an item in the list of results, and then click **Investigate**.</span></span>

![使用調查按鈕瀏覽器中的使用者報告訊息](media/Explorer-UserReported-Investigate.png)

<span data-ttu-id="948d5-180">另一個範例是, 假設您要查看偵測到包含惡意程式碼的電子郵件相關資料, 而且有數封電子郵件被偵測為包含惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="948d5-180">As another example, suppose you are viewing data about email messages detected as containing malware, and there are several email messages detected as containing malware.</span></span> <span data-ttu-id="948d5-181">您可以選取 [**電子郵件**] 索引標籤, 選取一或多封電子郵件, 然後在 [**動作**] 功能表上, 選取 [**調查**]。</span><span class="sxs-lookup"><span data-stu-id="948d5-181">You can select the **Email** tab, select one or more email messages, and then, on the **Actions** menu, select **Investigate**.</span></span> 

![開始調查瀏覽器中的惡意程式碼](media/Explorer-Malware-Email-ActionsInvestigate.png)

<span data-ttu-id="948d5-183">類似于警示所觸發的行動行動, 從 Explorer 中的視圖觸發的自動調查包括根調查、識別和關聯威脅的步驟, 以及建議的動作以緩解這些威脅。</span><span class="sxs-lookup"><span data-stu-id="948d5-183">Similar to playbooks triggered by an alert, automatic investigations that are triggered from a view in Explorer include a root investigation, steps to identify and correlate threats, and recommended actions to mitigate those threats.</span></span>

## <a name="get-started"></a><span data-ttu-id="948d5-184">開始使用</span><span class="sxs-lookup"><span data-stu-id="948d5-184">Get started</span></span>

<span data-ttu-id="948d5-185">若要存取您的調查, 作為 Office 365 全域系統管理員、安全性系統管理員或安全性讀者, 請移至安全性 & 規範[https://protection.office.com](https://protection.office.com)中心 () 並登入。</span><span class="sxs-lookup"><span data-stu-id="948d5-185">To access your investigations, as an Office 365 global administrator, security administrator, or security reader, go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span> <span data-ttu-id="948d5-186">接著執行下列其中一項作業：</span><span class="sxs-lookup"><span data-stu-id="948d5-186">Then, do one of the following:</span></span>

- <span data-ttu-id="948d5-187">在左側導覽中, 移至 [**提醒** > ] [**查看提醒**], 開啟其中一個調查相關的警示, 然後按一下 [警示] 彈出底部的 [**查看調查**] 連結。</span><span class="sxs-lookup"><span data-stu-id="948d5-187">In the left navigation, go to **Alerts** > **View alerts**, open one of the investigation related alerts, then click the **View investigation** link at the bottom of the alert flyout.</span></span> 

    <span data-ttu-id="948d5-188">或</span><span class="sxs-lookup"><span data-stu-id="948d5-188">or</span></span>

- <span data-ttu-id="948d5-189">在左側導覽中, 移至 [**威脅管理** > **調查**]。</span><span class="sxs-lookup"><span data-stu-id="948d5-189">In the left navigation, go to **Threat management** > **Investigations**.</span></span>

    <span data-ttu-id="948d5-190">或</span><span class="sxs-lookup"><span data-stu-id="948d5-190">or</span></span>

- <span data-ttu-id="948d5-191">造訪 [威脅管理] 儀表板 (在安全性 & 規範中心中, 移至 [**威脅管理** > ]**儀表板**)。</span><span class="sxs-lookup"><span data-stu-id="948d5-191">Visit the Threat management dashboard (In the Security & Compliance Center, go to **Threat management** > **Dashboard**).</span></span>

![空氣小元件](media/air-widgets.png)

<span data-ttu-id="948d5-193">您的空氣小元件會出現在 [[安全性] 儀表板](security-dashboard.md)的頂端。</span><span class="sxs-lookup"><span data-stu-id="948d5-193">Your AIR widgets will appear across the top of the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="948d5-194">選取要開始使用的小工具。</span><span class="sxs-lookup"><span data-stu-id="948d5-194">Select a widget to get started.</span></span>

<span data-ttu-id="948d5-195">您也可以直接從相關的警示存取調查。</span><span class="sxs-lookup"><span data-stu-id="948d5-195">You may also access an investigation directly from the related Alerts.</span></span>

### <a name="automated-investigations"></a><span data-ttu-id="948d5-196">自動化調查</span><span class="sxs-lookup"><span data-stu-id="948d5-196">Automated investigations</span></span>

<span data-ttu-id="948d5-197">[自動調查] 頁面會顯示貴組織的調查及其目前狀態。</span><span class="sxs-lookup"><span data-stu-id="948d5-197">The automated investigations page shows your organization's investigations and their current states.</span></span>

![空氣的主要調查頁面](media/air-maininvestigationpage.png) 
  
<span data-ttu-id="948d5-199">您可以：</span><span class="sxs-lookup"><span data-stu-id="948d5-199">You can:</span></span>
- <span data-ttu-id="948d5-200">直接流覽至調查 (選取**調查識別碼**)。</span><span class="sxs-lookup"><span data-stu-id="948d5-200">Navigate directly to an investigation (select an **Investigation ID**).</span></span>
- <span data-ttu-id="948d5-201">套用篩選。</span><span class="sxs-lookup"><span data-stu-id="948d5-201">Apply filters.</span></span> <span data-ttu-id="948d5-202">選擇 [從**調查類型**]、[**時間範圍**]、[**狀態**] 或 [組合]。</span><span class="sxs-lookup"><span data-stu-id="948d5-202">Choose from **Investigation Type**, **Time range**, **Status**, or a combination of these.</span></span>
- <span data-ttu-id="948d5-203">將資料匯出至 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="948d5-203">Export the data to a CSV file.</span></span>

<span data-ttu-id="948d5-204">調查狀態會指出分析的進度和動作。</span><span class="sxs-lookup"><span data-stu-id="948d5-204">The investigation status indicates the progress of the analysis and actions.</span></span> <span data-ttu-id="948d5-205">當調查執行時, 狀態會變更以指出是否找到威脅, 以及指出是否已核准動作。</span><span class="sxs-lookup"><span data-stu-id="948d5-205">As the investigation runs, the status will change to indicate whether threats were found, as well as indicate whether actions have been approved.</span></span> 
- <span data-ttu-id="948d5-206">**開始**: 調查已排入佇列, 即將開始</span><span class="sxs-lookup"><span data-stu-id="948d5-206">**Starting**: The investigation is queued to begin soon</span></span>
- <span data-ttu-id="948d5-207">**正在**執行: 調查已開始, 正在進行分析</span><span class="sxs-lookup"><span data-stu-id="948d5-207">**Running**: The investigation has started and is conducting its' analysis</span></span>
- <span data-ttu-id="948d5-208">**找不到威脅**: 調查已完成其分析, 而且找不到任何威脅</span><span class="sxs-lookup"><span data-stu-id="948d5-208">**No Threats Found**: The investigation has completed its' analysis and no threats were found</span></span>
- <span data-ttu-id="948d5-209">**由系統終止**: 調查未關閉且在7天后過期</span><span class="sxs-lookup"><span data-stu-id="948d5-209">**Terminated By System**: The investigation was not closed and expired after 7 days</span></span>
- <span data-ttu-id="948d5-210">**擱置的動作**: 調查發現有建議採取動作的威脅</span><span class="sxs-lookup"><span data-stu-id="948d5-210">**Pending Action**: The investigation found threats with actions recommended</span></span>
- <span data-ttu-id="948d5-211">**發現威脅**: 調查發現威脅, 但威脅沒有在 AIR 中提供的動作</span><span class="sxs-lookup"><span data-stu-id="948d5-211">**Threats Found**: The investigation found threats, but the threats do not have actions available within AIR</span></span>
- <span data-ttu-id="948d5-212">已**修正**: investgation 已完成且已完全修正 (所有動作都已核准)</span><span class="sxs-lookup"><span data-stu-id="948d5-212">**Remediated**: The investgation finished and was fully remediated (all actions were approved)</span></span>
- <span data-ttu-id="948d5-213">**部分修正**: 調查已完成且部分建議的動作已核准</span><span class="sxs-lookup"><span data-stu-id="948d5-213">**Partially Remediated**: The investigation finished and some of the recommended actions were approved</span></span>
- <span data-ttu-id="948d5-214">**由使用者終止**: 系統管理員已終止調查</span><span class="sxs-lookup"><span data-stu-id="948d5-214">**Terminated By User**: An admin terminated the investigation</span></span>
- <span data-ttu-id="948d5-215">**失敗**: 調查期間發生錯誤, 導致其無法達到威脅的結論</span><span class="sxs-lookup"><span data-stu-id="948d5-215">**Failed**: An error occurred during the investigation that prevented it from reaching a conclusion on threats</span></span>
- <span data-ttu-id="948d5-216">**依節流排入佇列**: 調查因系統處理限制而等待分析 (以保護服務效能)</span><span class="sxs-lookup"><span data-stu-id="948d5-216">**Queued By Throttling**: The investigation is waiting for analysis due to system processing limitations (to protect service performance)</span></span>
- <span data-ttu-id="948d5-217">**由節流終止**: 因為調查量和系統處理限制, 無法在足夠的時間內完成調查。</span><span class="sxs-lookup"><span data-stu-id="948d5-217">**Terminated By Throttling**: The investigation could not be completed in sufficient time due to investigation volume and system processing limitations.</span></span> <span data-ttu-id="948d5-218">您可以在瀏覽器中選取電子郵件, 然後選取 [調查] 動作, 以重新觸發調查。</span><span class="sxs-lookup"><span data-stu-id="948d5-218">You can re-trigger the investigation by selecting the email in Explorer and selecting the Investigate action.</span></span>

### <a name="investigation-graph"></a><span data-ttu-id="948d5-219">調查圖形</span><span class="sxs-lookup"><span data-stu-id="948d5-219">Investigation graph</span></span>

<span data-ttu-id="948d5-220">當您開啟特定調查時, 您會看到 [調查圖形] 頁面。</span><span class="sxs-lookup"><span data-stu-id="948d5-220">When you open a specific investigation, you see the investigation graph page.</span></span> <span data-ttu-id="948d5-221">此頁面會顯示所有不同的實體: 電子郵件、使用者 (及其活動), 以及在觸發的警示中自動調查的裝置。</span><span class="sxs-lookup"><span data-stu-id="948d5-221">This page shows all the different entities: email messages, users (and their activities), and devices that were automatically investigated as part of the alert that was triggered.</span></span>

![AIR 調查圖形頁面](media/air-investigationgraphpage.png)

<span data-ttu-id="948d5-223">您可以：</span><span class="sxs-lookup"><span data-stu-id="948d5-223">You can:</span></span>
- <span data-ttu-id="948d5-224">取得目前調查的視覺效果。</span><span class="sxs-lookup"><span data-stu-id="948d5-224">Get a visual overview of the current investigation.</span></span>
- <span data-ttu-id="948d5-225">查看調查期間的摘要。</span><span class="sxs-lookup"><span data-stu-id="948d5-225">View a summary of the investigation duration.</span></span>
- <span data-ttu-id="948d5-226">選取視覺效果中的節點, 以查看該節點的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="948d5-226">Select a node in the visualization to view details for that node.</span></span>
- <span data-ttu-id="948d5-227">選取頂端的索引標籤, 以查看該索引標籤的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="948d5-227">Select a tab across the top to view details for that tab.</span></span>

### <a name="alert-investigation"></a><span data-ttu-id="948d5-228">警示調查</span><span class="sxs-lookup"><span data-stu-id="948d5-228">Alert investigation</span></span>

<span data-ttu-id="948d5-229">在調查的 [**警示**] 索引標籤上, 您可以看到與調查相關的警示。</span><span class="sxs-lookup"><span data-stu-id="948d5-229">On the **Alerts** tab for an investigation, you can see alerts relevant to the investigation.</span></span> <span data-ttu-id="948d5-230">詳細資料包含觸發調查的警示, 以及與調查相關的其他提醒, 例如有風險的登入、大量下載等等。</span><span class="sxs-lookup"><span data-stu-id="948d5-230">Details include the alert that triggered the investigation and other alerts, such as risky sign-in, mass download, etc., that are correlated to the investigation.</span></span> <span data-ttu-id="948d5-231">在此頁面中, 安全性分析師也可以查看個別警示的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="948d5-231">From this page, a security analyst can also view additional details on individual alerts.</span></span>

![[AIR 警示] 頁面](media/air-investigationalertspage.png)

<span data-ttu-id="948d5-233">您可以：</span><span class="sxs-lookup"><span data-stu-id="948d5-233">You can:</span></span>
- <span data-ttu-id="948d5-234">取得目前觸發警示及任何相關警示的視覺效果。</span><span class="sxs-lookup"><span data-stu-id="948d5-234">Get a visual overview of the current triggering alert and any associated alerts.</span></span>
- <span data-ttu-id="948d5-235">在清單中選取警示, 以開啟顯示完整警示詳細資料的飛出頁面。</span><span class="sxs-lookup"><span data-stu-id="948d5-235">Select an alert in the list to open a fly-out page that shows full alert details.</span></span>

### <a name="email-investigation"></a><span data-ttu-id="948d5-236">電子郵件調查</span><span class="sxs-lookup"><span data-stu-id="948d5-236">Email investigation</span></span>

<span data-ttu-id="948d5-237">在調查的 [**電子郵件**] 索引標籤上, 您可以看到識別為調查一部分的所有電子郵件。</span><span class="sxs-lookup"><span data-stu-id="948d5-237">On the **Email** tab for an investigation, you can see all the clusters of email identified as part of the investigation.</span></span> 

<span data-ttu-id="948d5-238">針對組織中的使用者所傳送和接收的大量電子郵件,</span><span class="sxs-lookup"><span data-stu-id="948d5-238">Given the sheer volume of email that users in an organization send and receive, the process of</span></span> 
- <span data-ttu-id="948d5-239">根據郵件頭、內文、URL 和附件等類似的屬性, 來聚簇電子郵件訊息;</span><span class="sxs-lookup"><span data-stu-id="948d5-239">clustering email messages based on similar attributes from a message header, body, URL and attachments;</span></span> 
- <span data-ttu-id="948d5-240">將惡意電子郵件與良好的電子郵件分開;並</span><span class="sxs-lookup"><span data-stu-id="948d5-240">separating malicious email from the good email; and</span></span> 
- <span data-ttu-id="948d5-241">對惡意電子郵件採取動作</span><span class="sxs-lookup"><span data-stu-id="948d5-241">taking action on malicious email messages</span></span> 

<span data-ttu-id="948d5-242">可能需要數小時的時間。</span><span class="sxs-lookup"><span data-stu-id="948d5-242">can take many hours.</span></span> <span data-ttu-id="948d5-243">現在, AIR 會自動化此程式, 儲存貴組織的安全性小組時間和精力。</span><span class="sxs-lookup"><span data-stu-id="948d5-243">AIR now automates this process, saving your organization's security team time and effort.</span></span> 

<span data-ttu-id="948d5-244">在電子郵件分析步驟中, 可能會識別兩種不同類型的電子郵件叢集: 相似性叢集和指標叢集。</span><span class="sxs-lookup"><span data-stu-id="948d5-244">Two different types of email clusters may be identified during the email analysis step: similarity clusters, and indicator clusters.</span></span> 
- <span data-ttu-id="948d5-245">相似性叢集是包含類似寄件者和內容屬性的電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="948d5-245">Similarity clusters are email messages that contain similar sender and content attributes.</span></span> <span data-ttu-id="948d5-246">根據原始偵測結果來評估這些叢集的惡意內容。</span><span class="sxs-lookup"><span data-stu-id="948d5-246">These clusters are evaluated for malicious content based on the original detection findings.</span></span> <span data-ttu-id="948d5-247">包含足夠惡意偵測的電子郵件群集會被視為惡意的。</span><span class="sxs-lookup"><span data-stu-id="948d5-247">Email clusters that contain enough malicious detections will be considered malicious.</span></span>
- <span data-ttu-id="948d5-248">指示器叢集是電子郵件訊息, 包含原始電子郵件的相同指示器實體 (檔案雜湊或 URL)。</span><span class="sxs-lookup"><span data-stu-id="948d5-248">Indicator clusters are email messages that contain the same indicator entity (file hash or URL) from the original email.</span></span> <span data-ttu-id="948d5-249">當原始檔案/URL 實體被識別為惡意時, AIR 會對包含該實體的電子郵件的整個叢集套用指標判定。</span><span class="sxs-lookup"><span data-stu-id="948d5-249">When the original file/URL entity is identified as malicious, AIR will apply the indicator verdict to the entire cluster of email messages containing that entity.</span></span> <span data-ttu-id="948d5-250">在識別為惡意程式碼的檔案中, 會表示包含該檔案的電子郵件的叢集會被視為惡意程式碼電子郵件。</span><span class="sxs-lookup"><span data-stu-id="948d5-250">As a file identified as malware will mean that the cluster of email messages containing that file will be treated as malware email messages.</span></span>

<span data-ttu-id="948d5-251">叢集的目標是尋找其他相關的電子郵件, 這些訊息是由相同寄件者所傳送, 作為攻擊或活動的一部分。</span><span class="sxs-lookup"><span data-stu-id="948d5-251">The goal of clustering is to find other related email messages that are sent by the same sender as part of an attack or a campaign.</span></span>

<span data-ttu-id="948d5-252">[**電子郵件**] 索引標籤也會顯示與調查相關的電子郵件專案, 例如使用者報告的電子郵件詳細資料、原始電子郵件報告、電子郵件訊息 (zapped 由於惡意程式碼/網路釣魚) 等等。</span><span class="sxs-lookup"><span data-stu-id="948d5-252">The **Email** tab will also show email items related to the investigation, such as the user-reported email details, the original email reported, the email message(s) zapped due to malware/phish, etc.</span></span>

<span data-ttu-id="948d5-253">[電子郵件] 索引標籤上所識別的電子郵件計數目前代表 [**電子郵件**] 索引標籤上顯示的所有電子郵件總數。因為電子郵件會出現在多個叢集中, 所以所識別之電子郵件的實際總數 (並受到修正動作影響) 將會是所有叢集和原始收件者的電子郵件中所顯示的唯一電子郵件總數。郵件.</span><span class="sxs-lookup"><span data-stu-id="948d5-253">The email count identified on the email tab currently represents the sum total of all email messages shown on the **Email** tab. Since email messages will be present in multiple clusters, the actual total count of email messages identified (and affected by remediation actions) will be the count of unique email messages present across all of the clusters and original recipients' email messages.</span></span> 

<span data-ttu-id="948d5-254">因為安全性 verdicts、動作和傳遞位置會因每個收件者而異, 因此每個收件者的 Explorer 和 AIR 的電子郵件訊息都會有所不同。</span><span class="sxs-lookup"><span data-stu-id="948d5-254">Both Explorer and AIR count email messages on a per recipient basis, since the security verdicts, actions, and delivery locations will vary on a per recipient basis.</span></span> <span data-ttu-id="948d5-255">因此, 傳送給三個使用者的原始電子郵件會算作三個電子郵件的總數, 而不是一個電子郵件。</span><span class="sxs-lookup"><span data-stu-id="948d5-255">Thus an original email sent to three users will count as a total of three email messages instead of one email.</span></span> <span data-ttu-id="948d5-256">附注: 可能會有一或多個電子郵件被計入兩次以上的情況, 因為電子郵件可能會有多個動作, 而且可能會有多個電子郵件副本發生所有動作。</span><span class="sxs-lookup"><span data-stu-id="948d5-256">Note there may be cases where an email gets counted two or more times, since the email may have multiple actions on it and there may be multiple copies of the email once all actions occur.</span></span> <span data-ttu-id="948d5-257">例如, 在傳遞時偵測到惡意程式碼的電子郵件可能會導致封鎖 (隔離的) 電子郵件和取代的電子郵件 (以警告檔取代的威脅檔案, 然後傳遞至使用者的信箱)。</span><span class="sxs-lookup"><span data-stu-id="948d5-257">For example a malware email that is detected at delivery may result in both a blocked (quarantined) email and a replaced email (threat file replaced with an warning file, then delivered to user's mailbox).</span></span> <span data-ttu-id="948d5-258">由於系統中的電子郵件有兩個複本, 因此它們都可能會在叢集計數中計算在內。</span><span class="sxs-lookup"><span data-stu-id="948d5-258">Since there are literally two copies of the email in the system - these may both be counted in cluster counts.</span></span> 

<span data-ttu-id="948d5-259">電子郵件計數會在調查時進行計算, 當您開啟調查 flyouts 時, 會重新計算某些計數 (根據基礎查詢)。</span><span class="sxs-lookup"><span data-stu-id="948d5-259">Email counts are calculated at the time of the investigation and some counts are re-calculated when you open investigation flyouts (based on an underlying query).</span></span> <span data-ttu-id="948d5-260">在調查時, 會在 [電子郵件] 索引標籤上顯示的電子郵件, 以及在 [叢集] 快顯視窗中顯示的電子郵件數量詞所顯示的電子郵件計數。</span><span class="sxs-lookup"><span data-stu-id="948d5-260">The email counts shown for the email clusters on the email tab and the email quantity value shown on cluster flyout are calculated at the time of investigation.</span></span> <span data-ttu-id="948d5-261">在 [叢集] 快顯視窗的 [電子郵件] 索引標籤底部顯示的電子郵件計數, 以及瀏覽器中所顯示的電子郵件數目, 會反映在調查初始分析之後收到的電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="948d5-261">The email count shown at the bottom of the email tab of the cluster flyout, as well as the count of email messages shown in Explorer will reflect email messages received after the investigation's initial analysis.</span></span> <span data-ttu-id="948d5-262">因此, 顯示原始數量10封電子郵件的電子郵件叢集, 會顯示15個電子郵件清單, 當調查分析階段和系統管理員審閱調查時, 就會顯示15個電子郵件清單總計15。</span><span class="sxs-lookup"><span data-stu-id="948d5-262">Thus an email cluster that shows an original quantity of 10 email messages would show an email list total of 15 when 5 more email messages arrive between the investigation analysis phase and when the admin reviews the investigation.</span></span> <span data-ttu-id="948d5-263">在不同的視圖中顯示計數會完成, 以指出調查時的電子郵件影響, 以及目前的影響, 直到執行補救的時間為止。</span><span class="sxs-lookup"><span data-stu-id="948d5-263">Showing both counts in different views is done to indicate the email impact at the time of investigation and the current impact up until the time that remediation is run.</span></span>

<span data-ttu-id="948d5-264">例如, 請考慮下列案例。</span><span class="sxs-lookup"><span data-stu-id="948d5-264">As an example, consider the following scenario.</span></span> <span data-ttu-id="948d5-265">三個電子郵件的第一個叢集被視為網路釣魚。</span><span class="sxs-lookup"><span data-stu-id="948d5-265">The first cluster of three email messages were deemed to be phish.</span></span> <span data-ttu-id="948d5-266">已找到另一個具有相同 IP 和主旨的訊息, 並將其視為惡意, 因為在初始偵測期間, 有部分使用者被識別為網路釣魚。</span><span class="sxs-lookup"><span data-stu-id="948d5-266">Another cluster of similar messages with the same IP and subject was found and considered malicious, as some of them were identified as phish during initial detection.</span></span> 

![空中電子郵件調查頁面](media/air-investigationemailpage.png)

<span data-ttu-id="948d5-268">您可以：</span><span class="sxs-lookup"><span data-stu-id="948d5-268">You can:</span></span>
- <span data-ttu-id="948d5-269">取得目前的聚集結果和發現威脅的視覺效果。</span><span class="sxs-lookup"><span data-stu-id="948d5-269">Get a visual overview of the current clustering results and threats found.</span></span>
- <span data-ttu-id="948d5-270">按一下叢集實體或威脅清單, 開啟顯示完整警示詳細資料的飛出頁面。</span><span class="sxs-lookup"><span data-stu-id="948d5-270">Click a cluster entity or a threat list to open a fly-out page that shows the full alert details.</span></span>
- <span data-ttu-id="948d5-271">按一下 [電子郵件叢集詳細資料] 索引標籤頂端的 [在 Explorer 中開啟] 連結, 進一步調查電子郵件叢集</span><span class="sxs-lookup"><span data-stu-id="948d5-271">Further investigate the email cluster by clicking the 'Open in Explorer' link at the top of the 'Email cluster details' tab</span></span>

![使用飛出詳細資料的 AIR 調查電子郵件](media/air-investigationemailpageflyoutdetails.png)

<span data-ttu-id="948d5-273">\* 附注: 在電子郵件的內容中, 您可能會看到大量的異常威脅表面, 做為調查的一部分。</span><span class="sxs-lookup"><span data-stu-id="948d5-273">\*Note: In the context of email, you may see a volume anomaly threat surface as part of the investigation.</span></span> <span data-ttu-id="948d5-274">大量的異常會指出與較舊的時程表相較于調查事件時間的類似電子郵件中的尖峰。</span><span class="sxs-lookup"><span data-stu-id="948d5-274">A volume anomaly indicates a spike in similar email messages around the investigation event time compared to earlier timeframes.</span></span> <span data-ttu-id="948d5-275">這種具有類似特性的電子郵件流量 (例如主旨和寄件者網域、本文相似性和寄件者 IP) 通常是電子郵件活動或攻擊的開始。</span><span class="sxs-lookup"><span data-stu-id="948d5-275">This spike in email traffic with similar characteristics (e.g. subject and sender domain, body similarity and sender IP) is typical of the start of email campaigns or attacks.</span></span> <span data-ttu-id="948d5-276">不過, 大量、垃圾郵件和合法的電子郵件活動通常會共用這些特性。</span><span class="sxs-lookup"><span data-stu-id="948d5-276">However, bulk, spam, and legitimate email campaigns commonly share these characteristics.</span></span> <span data-ttu-id="948d5-277">大量異常代表潛在的威脅, 因此與使用反病毒引擎、引爆或惡意信譽識別的惡意程式碼或網路釣魚威脅相較低。</span><span class="sxs-lookup"><span data-stu-id="948d5-277">Volume anomalies represent a potential threat, and accordingly could be less severe compared to malware or phish threats that are identified using anti-virus engines, detonation or malicious reputation.</span></span>

### <a name="user-investigation"></a><span data-ttu-id="948d5-278">使用者調查</span><span class="sxs-lookup"><span data-stu-id="948d5-278">User investigation</span></span>

<span data-ttu-id="948d5-279">在 [**使用者**] 索引標籤上, 您可以看到所有識別為調查一部分的使用者。</span><span class="sxs-lookup"><span data-stu-id="948d5-279">On the **Users** tab, you can see all the users identified as part of the investigation.</span></span> <span data-ttu-id="948d5-280">當有事件或指出使用者可能會受到影響或遭到破壞時, 就會出現在調查中的使用者。</span><span class="sxs-lookup"><span data-stu-id="948d5-280">Users will appear in the investigation when there is an event or indication that the user may be affected or compromised.</span></span>

<span data-ttu-id="948d5-281">例如, 在下列影像中, AIR 會根據建立的新收件匣規則, 識別出損標及不確定的情況。</span><span class="sxs-lookup"><span data-stu-id="948d5-281">For example, in the following image, AIR has identified indicators of compromise and anomalies based on a new inbox rule that was created.</span></span> <span data-ttu-id="948d5-282">您可以透過此索引標籤中的詳細資訊, 取得調查的其他詳細資料 (證據)。破壞性和異常的指標也可能包含[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)的異常偵測。</span><span class="sxs-lookup"><span data-stu-id="948d5-282">Additional details (evidence) of the investigation are available through detailed views within this tab. Indicators of compromise and anomalies may also include anomaly detections from [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span></span>

![AIR 調查使用者頁面](media/air-investigationuserspage.png)

<span data-ttu-id="948d5-284">您可以：</span><span class="sxs-lookup"><span data-stu-id="948d5-284">You can:</span></span>
- <span data-ttu-id="948d5-285">取得已識別的使用者結果和發現風險的視覺效果。</span><span class="sxs-lookup"><span data-stu-id="948d5-285">Get a visual overview of identified user results and risks found.</span></span>
- <span data-ttu-id="948d5-286">選取使用者來開啟顯示完整警示詳細資料的飛出頁面。</span><span class="sxs-lookup"><span data-stu-id="948d5-286">Select a user to open a fly-out page that shows the full alert details.</span></span>

### <a name="machine-investigation"></a><span data-ttu-id="948d5-287">機器調查</span><span class="sxs-lookup"><span data-stu-id="948d5-287">Machine investigation</span></span>

<span data-ttu-id="948d5-288">在 [**電腦**] 索引標籤上, 您可以看到識別為部分調查的所有機器。</span><span class="sxs-lookup"><span data-stu-id="948d5-288">On the **Machines** tab, you can see all the machines identified as part of the investigation.</span></span> 

![AIR 調查電腦頁面](media/air-investigationmachinepage.png)

<span data-ttu-id="948d5-290">作為調查的一部分, AIR 會將電子郵件威脅與裝置相關聯。</span><span class="sxs-lookup"><span data-stu-id="948d5-290">As part of the investigation, AIR correlates email threats to devices.</span></span> <span data-ttu-id="948d5-291">例如, 調查會將惡意檔案雜湊傳遞至[Microsoft DEFENDER ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection
) , 以進行調查。</span><span class="sxs-lookup"><span data-stu-id="948d5-291">For example, an investigation passes a malicious file hash across to [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection
) to investigate.</span></span> <span data-ttu-id="948d5-292">這可讓您針對使用者自動調查相關的機器, 以協助確保在雲端和您的端點上都解決威脅。</span><span class="sxs-lookup"><span data-stu-id="948d5-292">This allows for automated investigation of relevant machines for your users, to help ensure that threats are addressed both in the cloud and across your endpoints.</span></span> 

<span data-ttu-id="948d5-293">您可以：</span><span class="sxs-lookup"><span data-stu-id="948d5-293">You can:</span></span>
- <span data-ttu-id="948d5-294">取得所找到的目前電腦和威脅的視覺效果。</span><span class="sxs-lookup"><span data-stu-id="948d5-294">Get a visual overview of the current machines and threats found.</span></span>
- <span data-ttu-id="948d5-295">選取機器, 以開啟 Microsoft Defender 安全中心的相關[Microsoft DEFENDER ATP 調查](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)中的視圖。</span><span class="sxs-lookup"><span data-stu-id="948d5-295">Select a machine to open a view that into the related [Microsoft Defender ATP investigations](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) in the Microsoft Defender Security Center.</span></span>

### <a name="entity-investigation"></a><span data-ttu-id="948d5-296">實體調查</span><span class="sxs-lookup"><span data-stu-id="948d5-296">Entity investigation</span></span>

<span data-ttu-id="948d5-297">在 [**實體**] 索引標籤上, 您可以看到所有識別為調查一部分的實體。</span><span class="sxs-lookup"><span data-stu-id="948d5-297">On the **Entities** tab, you can see all the entities identified as part of the investigation.</span></span> 

<span data-ttu-id="948d5-298">您可以在這裡查看已調查的實體, 以及實體類型的詳細資料, 例如電子郵件、叢集、IP 位址、使用者等等。</span><span class="sxs-lookup"><span data-stu-id="948d5-298">Here, you can see the investigated entities and details of the types of entities, such as email messages, clusters, IP addresses, users, and more.</span></span> <span data-ttu-id="948d5-299">您也可以查看已分析的實體數目, 以及與每個實體相關聯的威脅。</span><span class="sxs-lookup"><span data-stu-id="948d5-299">You can also see how many entities were analyzed, and the threats that were associated with each.</span></span> 

![AIR 調查實體頁面](media/air-investigationentitiespage.png)

<span data-ttu-id="948d5-301">您可以：</span><span class="sxs-lookup"><span data-stu-id="948d5-301">You can:</span></span>
- <span data-ttu-id="948d5-302">取得找到的調查實體和威脅的視覺效果。</span><span class="sxs-lookup"><span data-stu-id="948d5-302">Get a visual overview of the investigation entities and threats found.</span></span>
- <span data-ttu-id="948d5-303">選取實體以開啟顯示相關實體詳細資料的飛出頁面。</span><span class="sxs-lookup"><span data-stu-id="948d5-303">Select an entity to open a fly-out page that shows the related entity details.</span></span>

![空中調查實體詳細資料](media/air-investigationsentitiespagedetails.png)

### <a name="playbook-log"></a><span data-ttu-id="948d5-305">行動手冊記錄檔</span><span class="sxs-lookup"><span data-stu-id="948d5-305">Playbook log</span></span>

<span data-ttu-id="948d5-306">在 [**記錄**] 索引標籤上, 您可以看到調查期間所發生的所有行動手冊步驟。</span><span class="sxs-lookup"><span data-stu-id="948d5-306">On the **Log** tab, you can see all the playbook steps that have occurred during the investigation.</span></span> <span data-ttu-id="948d5-307">記錄會捕獲 Office 365 自動調查功能所完成之所有動作的完整清查, 做為空氣的一部分。</span><span class="sxs-lookup"><span data-stu-id="948d5-307">The log captures a complete inventory of all actions completed by Office 365 auto-investigation capabilities as part of AIR.</span></span> <span data-ttu-id="948d5-308">它提供所有採取步驟的清晰視圖, 包括動作本身、描述, 以及實際從開始到完成的持續時間。</span><span class="sxs-lookup"><span data-stu-id="948d5-308">It provides a clear view of all the steps taken, including the action itself, a description, and the duration of the actual from start to finish.</span></span> 

![AIR 調查記錄頁面](media/air-investigationlogpage.png)

<span data-ttu-id="948d5-310">您可以：</span><span class="sxs-lookup"><span data-stu-id="948d5-310">You can:</span></span>
- <span data-ttu-id="948d5-311">取得行動手冊步驟的視覺效果。</span><span class="sxs-lookup"><span data-stu-id="948d5-311">Get see a visual overview of the playbook steps taken.</span></span>
- <span data-ttu-id="948d5-312">將結果匯出至 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="948d5-312">Export the results to a CSV file.</span></span>
- <span data-ttu-id="948d5-313">篩選視圖。</span><span class="sxs-lookup"><span data-stu-id="948d5-313">Filter the view.</span></span>

### <a name="recommended-actions"></a><span data-ttu-id="948d5-314">建議的動作</span><span class="sxs-lookup"><span data-stu-id="948d5-314">Recommended actions</span></span>

<span data-ttu-id="948d5-315">在 [**動作**] 索引標籤上, 您可以在調查完成後, 看到修正建議的所有行動手冊動作。</span><span class="sxs-lookup"><span data-stu-id="948d5-315">On the **Actions** tab, you can see all the playbook actions that are recommended for remediation after the investigation has completed.</span></span> 

<span data-ttu-id="948d5-316">動作會捕獲 Microsoft 建議您在調查結束時採取的步驟。</span><span class="sxs-lookup"><span data-stu-id="948d5-316">Actions capture the steps Microsoft recommends you take at the end of a investigation.</span></span> <span data-ttu-id="948d5-317">您可以選取一或多個動作來採取補救動作。</span><span class="sxs-lookup"><span data-stu-id="948d5-317">You can take remediation actions here by selecting one or more actions.</span></span> <span data-ttu-id="948d5-318">按一下 [**核准**], 即可開始修復。</span><span class="sxs-lookup"><span data-stu-id="948d5-318">Clicking **Approve** will allow remediation to begin.</span></span> <span data-ttu-id="948d5-319">(需要適當的許可權-必須有「搜尋和清除」角色, 才可從 Explorer 和 AIR 執行動作。</span><span class="sxs-lookup"><span data-stu-id="948d5-319">(Appropriate permissions are needed - the 'Search And Purge' role is required to run actions from Explorer and AIR).</span></span> <span data-ttu-id="948d5-320">例如, 安全性讀者可以查看動作但不能核准。</span><span class="sxs-lookup"><span data-stu-id="948d5-320">For example, a Security Reader can view actions but not approve them.</span></span> <span data-ttu-id="948d5-321">附注-您不需要核准每個動作。</span><span class="sxs-lookup"><span data-stu-id="948d5-321">Note - you do not have to approve every action.</span></span> <span data-ttu-id="948d5-322">如果您不同意建議的動作, 或您的組織未選擇特定的動作類型, 則您可以選擇**拒絕**動作, 或只是略過並不採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="948d5-322">If you do not agree with the recommended action or your organization does not choose certain types of actions - then you can either choose to **Reject** the actions or simply ignore them and take no action.</span></span> <span data-ttu-id="948d5-323">核准和/或拒絕所有動作, 即可完全關閉, 而保留某些動作將會導致調查狀態變更為部分修正的狀態。</span><span class="sxs-lookup"><span data-stu-id="948d5-323">Approving and/or rejecting all actions will let the investigation fully close, while leaving some actions incomplete will result in the investigation status changing to a partially remediated state.</span></span>

![空中調查動作頁面](media/air-investigationactionspage.png)

<span data-ttu-id="948d5-325">您可以：</span><span class="sxs-lookup"><span data-stu-id="948d5-325">You can:</span></span>
- <span data-ttu-id="948d5-326">取得行動手冊-建議動作的視覺效果。</span><span class="sxs-lookup"><span data-stu-id="948d5-326">Get a visual overview of the playbook-recommended actions.</span></span>
- <span data-ttu-id="948d5-327">選取單一動作或多個動作。</span><span class="sxs-lookup"><span data-stu-id="948d5-327">Select a single action or multiple actions.</span></span>
- <span data-ttu-id="948d5-328">使用批註核准或拒絕建議的動作。</span><span class="sxs-lookup"><span data-stu-id="948d5-328">Approve or reject recommended actions with comments.</span></span>
- <span data-ttu-id="948d5-329">將結果匯出至 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="948d5-329">Export the results to a CSV file.</span></span>
- <span data-ttu-id="948d5-330">篩選視圖。</span><span class="sxs-lookup"><span data-stu-id="948d5-330">Filter the view.</span></span>

## <a name="how-to-get-air"></a><span data-ttu-id="948d5-331">如何取得空中</span><span class="sxs-lookup"><span data-stu-id="948d5-331">How to get AIR</span></span>

<span data-ttu-id="948d5-332">目前, Office 365 AIR 功能是在預覽中。</span><span class="sxs-lookup"><span data-stu-id="948d5-332">Currently, Office 365 AIR features are in preview.</span></span> <span data-ttu-id="948d5-333">當您公開時, Office 365 AIR 功能將會包含在下列訂閱中:</span><span class="sxs-lookup"><span data-stu-id="948d5-333">When generally available, Office 365 AIR features will be included in the following subscriptions:</span></span>

- <span data-ttu-id="948d5-334">Microsoft 365 企業版 E5</span><span class="sxs-lookup"><span data-stu-id="948d5-334">Microsoft 365 Enterprise E5</span></span>
- <span data-ttu-id="948d5-335">Office 365 企業版 E5</span><span class="sxs-lookup"><span data-stu-id="948d5-335">Office 365 Enterprise E5</span></span>
- <span data-ttu-id="948d5-336">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="948d5-336">Microsoft Threat Protection</span></span>
- <span data-ttu-id="948d5-337">Office 365 高級威脅防護方案2</span><span class="sxs-lookup"><span data-stu-id="948d5-337">Office 365 Advanced Threat Protection Plan 2</span></span>

<span data-ttu-id="948d5-338">若要深入瞭解功能的可用性, 請造訪[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)。</span><span class="sxs-lookup"><span data-stu-id="948d5-338">To learn more about feature availability, visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>
