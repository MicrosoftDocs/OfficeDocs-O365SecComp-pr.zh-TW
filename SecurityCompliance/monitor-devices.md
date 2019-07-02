---
title: Microsoft 365 安全中心的裝置監視與報告
description: 說明如何讓您的裝置在組織中保持安全、最新和找出潛在威脅
keywords: 安全性、惡意程式碼、Microsoft 365、M365、security center、monitor、report、devices
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: 44fd28a0ba2ec72d999c89d183d85ccb496903ec
ms.sourcegitcommit: b9d8a43cb3afcdc8820bc9470c5707eff8fc6616
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/11/2019
ms.locfileid: "34852867"
---
# <a name="device-monitoring-and-reporting-in-microsoft-365-security-center"></a><span data-ttu-id="2c5be-104">Microsoft 365 安全中心的裝置監視與報告</span><span class="sxs-lookup"><span data-stu-id="2c5be-104">Device monitoring and reporting in Microsoft 365 security center</span></span>

<span data-ttu-id="2c5be-105">在 Microsoft 365 安全中心中, 讓您的裝置安全、最新和找出潛在威脅。</span><span class="sxs-lookup"><span data-stu-id="2c5be-105">Keep your devices secure, up-to-date, and spot potential threats in the Microsoft 365 security center.</span></span>

## <a name="view-device-alerts"></a><span data-ttu-id="2c5be-106">查看裝置警示</span><span class="sxs-lookup"><span data-stu-id="2c5be-106">View device alerts</span></span>

<span data-ttu-id="2c5be-107">從 Microsoft Defender ATP 取得裝置上有關違規活動及其他威脅的最新通知 (可使用 E5 授權)。</span><span class="sxs-lookup"><span data-stu-id="2c5be-107">Get up-to-date alerts about breach activity and other threats on your devices from Microsoft Defender ATP (available with an E5 license).</span></span> <span data-ttu-id="2c5be-108">Microsoft 365 安全中心使用您喜歡的工作流程, 以較高的層次來監視這些警示。</span><span class="sxs-lookup"><span data-stu-id="2c5be-108">Microsoft 365 security center effectively monitors these alerts at a high level using your preferred workflow.</span></span>

### <a name="monitor-high-impact-alerts"></a><span data-ttu-id="2c5be-109">監視高影響警示</span><span class="sxs-lookup"><span data-stu-id="2c5be-109">Monitor high-impact alerts</span></span>

<span data-ttu-id="2c5be-110">每個 Microsoft Defender ATP 警示都有相對應的嚴重性 (高、中、低或資訊), 指出對您的網路可能造成的影響 (如果不是自動)。</span><span class="sxs-lookup"><span data-stu-id="2c5be-110">Each Microsoft Defender ATP alert has a corresponding severity—high, medium, low, or informational—that indicates its potential impact to your network if left unattended.</span></span>  

<span data-ttu-id="2c5be-111">使用**裝置警示嚴重度**卡片, 特別是針對更嚴重且可能需要立即回應的提醒。</span><span class="sxs-lookup"><span data-stu-id="2c5be-111">Use the **Device alert severity** card to focus specifically on alerts that are more severe and might require immediate response.</span></span> <span data-ttu-id="2c5be-112">您可以從這個卡片來查看 Microsoft Defender 安全中心入口網站上的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="2c5be-112">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![裝置警示嚴重卡](./media/security-docs/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a><span data-ttu-id="2c5be-114">瞭解警示的來源</span><span class="sxs-lookup"><span data-stu-id="2c5be-114">Understand sources of alerts</span></span>

<span data-ttu-id="2c5be-115">Microsoft Defender ATP 會利用各種安全性感應器和智慧來源中的資料, 來產生警示。</span><span class="sxs-lookup"><span data-stu-id="2c5be-115">Microsoft Defender ATP leverages data from a broad range of security sensors and intelligence sources to generate alerts.</span></span> <span data-ttu-id="2c5be-116">例如, 它可以從 Windows Defender 防病毒和協力廠商反惡意程式碼使用偵測資訊, 以及透過 web 服務 API 提供的自訂威脅情報。</span><span class="sxs-lookup"><span data-stu-id="2c5be-116">For example, it can use detection information from Windows Defender Antivirus and third-party antimalware, as well as your own custom threat intelligence provided through the web service API.</span></span>

<span data-ttu-id="2c5be-117">**裝置警示偵測**的來源卡片顯示依來源進行的警示散佈。</span><span class="sxs-lookup"><span data-stu-id="2c5be-117">The **Device alert detection** sources card shows the distribution of alerts by source.</span></span> <span data-ttu-id="2c5be-118">這張卡片可協助您追蹤與特定來源相關的活動, 特別是自訂來源。</span><span class="sxs-lookup"><span data-stu-id="2c5be-118">This card can help you track activity related to certain sources, particularly your custom sources.</span></span> <span data-ttu-id="2c5be-119">您也可以使用此功能, 將來自未設定為自動封鎖惡意活動或元件之感應器的警示集中在。</span><span class="sxs-lookup"><span data-stu-id="2c5be-119">You can also use this to focus on alerts coming from sensors that are not configured to automatically block malicious activity or components.</span></span>

![裝置警示偵測來源卡](./media/security-docs/device-alert-detection-sources.png)

<span data-ttu-id="2c5be-121">您可以從這個卡片來查看 Microsoft Defender 安全中心入口網站上的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="2c5be-121">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a><span data-ttu-id="2c5be-122">瞭解觸發警示的威脅類型</span><span class="sxs-lookup"><span data-stu-id="2c5be-122">Understand the types of threats that trigger alerts</span></span>

<span data-ttu-id="2c5be-123">Microsoft Defender ATP 會將每個警示排序為一個類別, 代表攻擊鏈中的特定階段或威脅元件類型。</span><span class="sxs-lookup"><span data-stu-id="2c5be-123">Microsoft Defender ATP sorts each alert into a category representing a certain stage in the attack chain or a type of threat component.</span></span> <span data-ttu-id="2c5be-124">例如, 偵測到的威脅活動可能會分類為「側向移動」, 以表示活動企圖到達網路上的其他裝置, 且有可能在攻擊者取得初始 foothold 之後發生。</span><span class="sxs-lookup"><span data-stu-id="2c5be-124">For example, detected threat activity might be categorized into “lateral movement” to indicate that the activity involved an attempt to reach other devices on the network and has likely occurred after attackers have gained an initial foothold.</span></span> <span data-ttu-id="2c5be-125">偵測到威脅元件時, 可能會被視為「惡意軟體」, 或更特別是「勒索軟體」、「認證竊取」或其他類型的惡意或不需要的軟體。</span><span class="sxs-lookup"><span data-stu-id="2c5be-125">When detected, a threat component might either be classified broadly as “malware” or more specifically as “ransomware”, “credential stealing” or other types of malicious or unwanted software.</span></span>

<span data-ttu-id="2c5be-126">**裝置威脅類別**卡片會將提醒分散至這些類別。</span><span class="sxs-lookup"><span data-stu-id="2c5be-126">The **Device threat categories** card shows the distribution of alerts into these categories.</span></span> <span data-ttu-id="2c5be-127">您可以使用此資訊來識別威脅活動, 例如認證竊取時的嘗試, 這可能會比社交工程的嘗試更明顯的影響。</span><span class="sxs-lookup"><span data-stu-id="2c5be-127">You can use this information to identify threat activity, such as attempts at credential theft, which can have more significant impact compared to attempts at social engineering, for example.</span></span> <span data-ttu-id="2c5be-128">您也可以使用此程式來監視勒索軟體之類的潛在破壞性威脅。</span><span class="sxs-lookup"><span data-stu-id="2c5be-128">You can also use this to monitor for potentially destructive threats like ransomware.</span></span>

![裝置威脅類別卡片](./media/security-docs/device-threat-categories.png)

### <a name="monitor-active-alerts"></a><span data-ttu-id="2c5be-130">監視使用中的警示</span><span class="sxs-lookup"><span data-stu-id="2c5be-130">Monitor active alerts</span></span>

<span data-ttu-id="2c5be-131">**裝置警示狀態**卡指出尚未解決且可能需要注意的警示數目。</span><span class="sxs-lookup"><span data-stu-id="2c5be-131">The **Device alert status** card indicates the number of alerts that have not been resolved and might require attention.</span></span> <span data-ttu-id="2c5be-132">您可以從這個卡片來查看 Microsoft Defender 安全中心入口網站上的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="2c5be-132">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![裝置警示狀態卡片](./media/security-docs/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a><span data-ttu-id="2c5be-134">監視已解析警示的分類</span><span class="sxs-lookup"><span data-stu-id="2c5be-134">Monitor classification of resolved alerts</span></span>

<span data-ttu-id="2c5be-135">當您解決 Microsoft Defender ATP 警示時, 您的安全性員工可以指定警示是否已驗證為:</span><span class="sxs-lookup"><span data-stu-id="2c5be-135">When resolving a Microsoft Defender ATP alert, your security staff can specify whether an alert has been verified as:</span></span>

* <span data-ttu-id="2c5be-136">真正的警示, 識別實際的違規活動或威脅元件</span><span class="sxs-lookup"><span data-stu-id="2c5be-136">A true alert that identifies actual breach activity or threat components</span></span>
* <span data-ttu-id="2c5be-137">偵測到正常活動的錯誤警示</span><span class="sxs-lookup"><span data-stu-id="2c5be-137">A false alert that has incorrectly detected normal activity</span></span>

<span data-ttu-id="2c5be-138">**裝置警示分類**卡片會顯示您解決的警示是否已分類為 true 或 false 警示。</span><span class="sxs-lookup"><span data-stu-id="2c5be-138">The **Device alert classification** card shows whether your resolved alerts have been classified as true or false alerts.</span></span> <span data-ttu-id="2c5be-139">您可以從這個卡片來查看 Microsoft Defender 安全中心入口網站上的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="2c5be-139">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

<span data-ttu-id="2c5be-140">附注: 在某些情況下, 特定警示無法使用分類資訊。</span><span class="sxs-lookup"><span data-stu-id="2c5be-140">Note: In some cases, classification information is unavailable for certain alerts.</span></span>

![裝置警示分類卡片](./media/security-docs/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a><span data-ttu-id="2c5be-142">監視已解決之警示的決定</span><span class="sxs-lookup"><span data-stu-id="2c5be-142">Monitor determination of resolved alerts</span></span>

<span data-ttu-id="2c5be-143">除了將警示設為 true 或 false 時, 您的安全性人員還可以提供判斷, 指出驗證警示時所找到之正常或惡意活動的類型。</span><span class="sxs-lookup"><span data-stu-id="2c5be-143">In addition to classifying whether an alert is true or false during resolution, your security staff can provide a determination, indicating the type of normal or malicious activity that was found while validating the alert.</span></span>

<span data-ttu-id="2c5be-144">**裝置警示決定**卡顯示針對每個警示所提供的決定, 特別是:</span><span class="sxs-lookup"><span data-stu-id="2c5be-144">The **Device alert determination** card shows the determination provided for each alert, specifically:</span></span>

* <span data-ttu-id="2c5be-145">**APT** – advanced persistent 威脅, 表示偵測到的活動或威脅元件是複雜破壞的一部分, 其設計是為了在受影響的網路中取得 foothold</span><span class="sxs-lookup"><span data-stu-id="2c5be-145">**APT** – advanced persistent threat, indicating that the detected activity or threat component is part of a sophisticated breach designed to gain a foothold in the affected network</span></span>  
* <span data-ttu-id="2c5be-146">**惡意**代碼-惡意檔案或程式碼</span><span class="sxs-lookup"><span data-stu-id="2c5be-146">**Malware** – malicious file or code</span></span>
* <span data-ttu-id="2c5be-147">**安全性人員**–安全性人員所執行的一般活動</span><span class="sxs-lookup"><span data-stu-id="2c5be-147">**Security personnel** – normal activity performed by security staff</span></span>
* <span data-ttu-id="2c5be-148">**安全性測試**–旨在模擬實際威脅並預期觸發安全性感應器及產生警示的活動或元件</span><span class="sxs-lookup"><span data-stu-id="2c5be-148">**Security testing** – activity or components designed to simulate actual threats and expected to trigger security sensors and generate alerts</span></span>
* <span data-ttu-id="2c5be-149">不**需要的軟體**–應用程式和其他不被視為惡意的軟體, 但違反原則或可接受的使用標準</span><span class="sxs-lookup"><span data-stu-id="2c5be-149">**Unwanted software** – apps and other software that are not considered malicious, but otherwise violate policy or acceptable use standards</span></span>
* <span data-ttu-id="2c5be-150">**其他**–不屬於所提供類型的任何其他決定</span><span class="sxs-lookup"><span data-stu-id="2c5be-150">**Others** – any other determination that does not fall under the provided types</span></span>

<span data-ttu-id="2c5be-151">您可以從這個卡片來查看 Microsoft Defender 安全中心的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="2c5be-151">From this card, you can view more information in Microsoft Defender Security Center.</span></span>

![裝置警示確定卡](./media/security-docs/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a><span data-ttu-id="2c5be-153">瞭解哪些裝置面臨風險</span><span class="sxs-lookup"><span data-stu-id="2c5be-153">Understand which devices are at risk</span></span>

<span data-ttu-id="2c5be-154">**裝置保護**顯示裝置的風險層級。</span><span class="sxs-lookup"><span data-stu-id="2c5be-154">**Device protection** shows the risk level for devices.</span></span> <span data-ttu-id="2c5be-155">風險等級是以裝置上警示的類型和嚴重性之類的因素為基礎。</span><span class="sxs-lookup"><span data-stu-id="2c5be-155">The risk level is based on factors such as the type and severity of alerts on the device.</span></span>

![裝置保護卡](./media/security-docs/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a><span data-ttu-id="2c5be-157">監視及報告 Intune 管理裝置的狀態</span><span class="sxs-lookup"><span data-stu-id="2c5be-157">Monitor and report status of Intune-managed devices</span></span>

<span data-ttu-id="2c5be-158">下列報告包含已在 Intune 中註冊裝置的資料。</span><span class="sxs-lookup"><span data-stu-id="2c5be-158">The following reports contain data from devices enrolled in Intune.</span></span> <span data-ttu-id="2c5be-159">Unenrolled 裝置中的資料不包含在內。</span><span class="sxs-lookup"><span data-stu-id="2c5be-159">Data from unenrolled devices is not included.</span></span> <span data-ttu-id="2c5be-160">只有全域系統管理員才能查看這些卡片。</span><span class="sxs-lookup"><span data-stu-id="2c5be-160">Only Global Administrators can view these cards.</span></span>

<span data-ttu-id="2c5be-161">Intune 註冊的裝置資料包括:</span><span class="sxs-lookup"><span data-stu-id="2c5be-161">Intune enrolled device data includes:</span></span>

* <span data-ttu-id="2c5be-162">裝置合規性</span><span class="sxs-lookup"><span data-stu-id="2c5be-162">Device compliance</span></span>
* <span data-ttu-id="2c5be-163">具有主動惡意程式碼的裝置</span><span class="sxs-lookup"><span data-stu-id="2c5be-163">Devices with active malware</span></span>
* <span data-ttu-id="2c5be-164">裝置上的惡意程式碼類型</span><span class="sxs-lookup"><span data-stu-id="2c5be-164">Types of malware on devices</span></span>
* <span data-ttu-id="2c5be-165">裝置上的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="2c5be-165">Malware on devices</span></span>
* <span data-ttu-id="2c5be-166">包含惡意軟體偵測的裝置</span><span class="sxs-lookup"><span data-stu-id="2c5be-166">Devices with malware detections</span></span>
* <span data-ttu-id="2c5be-167">包含惡意軟體偵測的使用者</span><span class="sxs-lookup"><span data-stu-id="2c5be-167">Users with malware detections</span></span>

### <a name="monitor-device-compliance"></a><span data-ttu-id="2c5be-168">監視裝置合規性</span><span class="sxs-lookup"><span data-stu-id="2c5be-168">Monitor device compliance</span></span>

<span data-ttu-id="2c5be-169">**裝置合規性**顯示已在 Intune 中註冊的裝置, 符合設定原則。</span><span class="sxs-lookup"><span data-stu-id="2c5be-169">**Device compliance** shows how many devices that are enrolled in Intune comply with configuration policies.</span></span>

![裝置合規性卡](./media/security-docs/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a><span data-ttu-id="2c5be-171">探索含有惡意軟體偵測的裝置</span><span class="sxs-lookup"><span data-stu-id="2c5be-171">Discover devices with malware detections</span></span>

<span data-ttu-id="2c5be-172">**裝置惡意軟體**偵測提供的 Intune 註冊裝置數目尚未因擱置的動作而未完全解決 (重新開機、完整掃描或手動使用者動作), 或修復動作未順利完成。</span><span class="sxs-lookup"><span data-stu-id="2c5be-172">**Device malware detections** provides the number of Intune enrolled devices with malware that have not been fully resolved due to pending actions—a restart, a full scan or manual user actions—or if the remediation action did not complete successfully.</span></span>

![裝置惡意軟體偵測卡](./media/security-docs/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a><span data-ttu-id="2c5be-174">瞭解偵測到的惡意程式碼類型</span><span class="sxs-lookup"><span data-stu-id="2c5be-174">Understand the types of malware detected</span></span>

<span data-ttu-id="2c5be-175">**裝置上的惡意程式碼類型**顯示在 Intune 上註冊的裝置上偵測到的不同類型惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="2c5be-175">**Types of malware on devices** shows different kinds of malware that have been detected on devices enrolled in Intune.</span></span> <span data-ttu-id="2c5be-176">您可以在 Microsoft 365 安全中心中調查每種類型。</span><span class="sxs-lookup"><span data-stu-id="2c5be-176">You can investigate each type in Microsoft 365 security center.</span></span>

![裝置卡上的惡意程式碼類型](./media/security-docs/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a><span data-ttu-id="2c5be-178">瞭解在您的裝置上偵測到的特定惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="2c5be-178">Understand the specific malware detected on your devices</span></span>

<span data-ttu-id="2c5be-179">**裝置上的惡意**代碼會提供在您的裝置上偵測到之特定惡意程式碼的清單。</span><span class="sxs-lookup"><span data-stu-id="2c5be-179">**Malware on devices** provides a list of the specific malware detected on your devices.</span></span>

![裝置卡上的惡意程式碼](./media/security-docs/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a><span data-ttu-id="2c5be-181">瞭解哪些裝置的惡意程式碼最多</span><span class="sxs-lookup"><span data-stu-id="2c5be-181">Understand which devices have the most malware</span></span>

<span data-ttu-id="2c5be-182">**包含惡意**代碼的裝置會顯示哪些裝置的惡意軟體偵測最多。</span><span class="sxs-lookup"><span data-stu-id="2c5be-182">**Devices with malware detections** shows which devices have the most malware detections.</span></span> <span data-ttu-id="2c5be-183">在 Microsoft 365 安全性中心, 您可以調查惡意程式碼是使用中的, 誰會使用裝置, 以及其在 Intune 中的管理狀態。</span><span class="sxs-lookup"><span data-stu-id="2c5be-183">In Microsoft 365 security center, you can investigate whether malware is active, who uses the device, and its management status in Intune.</span></span>

![包含惡意軟體偵測卡的裝置](./media/security-docs/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a><span data-ttu-id="2c5be-185">瞭解哪些使用者具有最具惡意程式碼的裝置</span><span class="sxs-lookup"><span data-stu-id="2c5be-185">Understand which users have devices with the most malware</span></span>

<span data-ttu-id="2c5be-186">**使用惡意軟體**偵測的使用者會顯示具有最多惡意程式碼偵測之裝置的使用者。</span><span class="sxs-lookup"><span data-stu-id="2c5be-186">**Users with malware detections** shows users with devices that had the most malware detections.</span></span> <span data-ttu-id="2c5be-187">在 Microsoft 365 安全性中心, 您可以查看每個使用者所指派的裝置數目, 以及每個裝置和惡意軟體類型的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="2c5be-187">In Microsoft 365 security center, you can see how many devices are assigned to each user and more information about each device and the type of malware.</span></span>

![具有惡意軟體偵測卡的使用者](./media/security-docs/users-with-malware-detections.png)

## <a name="monitor-and-manage-asr-rule-deployment-and-detections"></a><span data-ttu-id="2c5be-189">監視及管理 ASR 規則部署和偵測</span><span class="sxs-lookup"><span data-stu-id="2c5be-189">Monitor and manage ASR rule deployment and detections</span></span>

<span data-ttu-id="2c5be-190">[攻擊面減少 (ASR) 規則](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard)可協助防止由 exploit 搜尋所使用的動作和應用程式, 以感染電腦。</span><span class="sxs-lookup"><span data-stu-id="2c5be-190">[Attack Surface Reduction (ASR) rules](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard) help prevent actions and apps that are typically used by exploit-seeking malware to infect machines.</span></span> <span data-ttu-id="2c5be-191">這些規則會控制可執行檔的執行時間和執行方式。</span><span class="sxs-lookup"><span data-stu-id="2c5be-191">These rules control when and how executables can run.</span></span> <span data-ttu-id="2c5be-192">例如, 您可以防止 JavaScript 或 VBScript 啟動下載的可執行檔、封鎖來自 Office 宏的 WIN32 API 呼叫, 或封鎖從 USB 磁片磁碟機執行的程式。</span><span class="sxs-lookup"><span data-stu-id="2c5be-192">For example, you can prevent JavaScript or VBScript from launching a downloaded executable, block Win32 API calls from Office macros, or block processes that run from USB drives.</span></span>

![攻擊面縮減卡](./media/security-docs/attack-surface-reduction-rules.png)

<span data-ttu-id="2c5be-194">**攻擊面減少規則**卡片概述如何在您的裝置上部署規則。</span><span class="sxs-lookup"><span data-stu-id="2c5be-194">The **Attack surface reduction rules** card provides an overview of the deployment of rules across your devices.</span></span>

<span data-ttu-id="2c5be-195">卡片上的頂端列顯示在下列部署模式中的裝置總數:</span><span class="sxs-lookup"><span data-stu-id="2c5be-195">The top bar on the card shows the total number of devices that are in the following deployment modes:</span></span>

* <span data-ttu-id="2c5be-196">**封鎖模式**–至少有一個規則設定為封鎖偵測活動的裝置</span><span class="sxs-lookup"><span data-stu-id="2c5be-196">**Block mode** – devices with at least one rule configured to block detected activity</span></span>
* <span data-ttu-id="2c5be-197">**核查模式**–未設定規則的裝置, 以封鎖偵測到的活動, 但至少有一個規則集來審核偵測到的活動</span><span class="sxs-lookup"><span data-stu-id="2c5be-197">**Audit mode** – devices with no rules set to block detected activity, but has at least one rule set to audit detected activity</span></span>  
* <span data-ttu-id="2c5be-198">**Off** -關閉所有 ASR 規則的裝置</span><span class="sxs-lookup"><span data-stu-id="2c5be-198">**Off** – devices with all ASR rules turned off</span></span>

<span data-ttu-id="2c5be-199">此卡片的下方部分會依規則顯示裝置上的設定。</span><span class="sxs-lookup"><span data-stu-id="2c5be-199">The lower part of this card shows settings by rule across your devices.</span></span> <span data-ttu-id="2c5be-200">每個條碼會指出設定為封鎖或審核偵測或已完全關閉規則的裝置數目。</span><span class="sxs-lookup"><span data-stu-id="2c5be-200">Each bar indicates the number of devices that are set to block or audit detection or have the rule completely turned off.</span></span>

### <a name="view-asr-detections"></a><span data-ttu-id="2c5be-201">查看 ASR 偵測</span><span class="sxs-lookup"><span data-stu-id="2c5be-201">View ASR detections</span></span>

<span data-ttu-id="2c5be-202">若要在您的網路中查看 ASR 規則偵測的詳細資訊, 請選取 [在**攻擊面減少規則**卡上**查看**偵測]。</span><span class="sxs-lookup"><span data-stu-id="2c5be-202">To view detailed information about ASR rule detections in your network, select **View detections** on the **Attack surface reduction rules** card.</span></span> <span data-ttu-id="2c5be-203">將\*\*\*\* 會開啟 [詳細報告] 頁面中的 [偵測] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="2c5be-203">The **Detections** tab in the detailed report page will open.</span></span>

![偵測索引標籤](./media/security-docs/detections-tab.png)

<span data-ttu-id="2c5be-205">頁面頂端的圖表會顯示已封鎖或已審核的時間堆疊偵測偵測偵測。</span><span class="sxs-lookup"><span data-stu-id="2c5be-205">The chart at the top of the page shows detections over time stacking detections that were either blocked or audited.</span></span> <span data-ttu-id="2c5be-206">底部的表格列出最近的偵測。</span><span class="sxs-lookup"><span data-stu-id="2c5be-206">The table at the bottom lists the most recent detections.</span></span> <span data-ttu-id="2c5be-207">請在資料表上使用下列資訊, 瞭解偵測的本質:</span><span class="sxs-lookup"><span data-stu-id="2c5be-207">Use the following information on the table to understand the nature of the detections:</span></span>

* <span data-ttu-id="2c5be-208">偵測**到**檔案–檔案 (通常是腳本或檔, 其內容會觸發置疑的攻擊活動)</span><span class="sxs-lookup"><span data-stu-id="2c5be-208">**Detected file** – the file, typically a script or a document, whose contents triggered the suspected attack activity</span></span>
* <span data-ttu-id="2c5be-209">**規則**名稱, 描述規則設計所要攔截的攻擊活動。</span><span class="sxs-lookup"><span data-stu-id="2c5be-209">**Rule** – name describing the attack activities the rule is designed to catch.</span></span> <span data-ttu-id="2c5be-210">閱讀關於現有 ASR 規則的資訊</span><span class="sxs-lookup"><span data-stu-id="2c5be-210">Read about existing ASR rules</span></span>
* <span data-ttu-id="2c5be-211">**來源應用**程式–載入或執行內容觸發可疑攻擊活動的應用程式。</span><span class="sxs-lookup"><span data-stu-id="2c5be-211">**Source app** – the application that loaded or executed content triggering the suspected attack activity.</span></span> <span data-ttu-id="2c5be-212">這可能是合法的應用程式, 例如網頁瀏覽器、Office 應用程式, 或像是 PowerShell 的系統工具。</span><span class="sxs-lookup"><span data-stu-id="2c5be-212">This could be a legitimate application, such as web browser, an Office application, or a system tool like PowerShell</span></span>
* <span data-ttu-id="2c5be-213">**Publisher** –發行來源應用程式的廠商</span><span class="sxs-lookup"><span data-stu-id="2c5be-213">**Publisher** – the vendor that released the source app</span></span>

### <a name="review-device-asr-rule-settings"></a><span data-ttu-id="2c5be-214">檢查裝置 ASR 規則設定</span><span class="sxs-lookup"><span data-stu-id="2c5be-214">Review device ASR rule settings</span></span>

<span data-ttu-id="2c5be-215">在 [**攻擊面減少規則**報告] 頁面中, 移\*\*\*\* 至 [設定] 索引標籤, 以查看個別裝置的規則設定。</span><span class="sxs-lookup"><span data-stu-id="2c5be-215">In the **Attack surface reduction rules** report page, go to the **Configuration** tab to review rule settings for individual devices.</span></span> <span data-ttu-id="2c5be-216">選取裝置以取得每個規則在封鎖模式、稽核模式或完全關閉時的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="2c5be-216">Select a device to get detailed information about whether each rule is in block mode, audit mode, or turned off entirely.</span></span>

![設定索引標籤](./media/security-docs/configuration-tab.png)

<span data-ttu-id="2c5be-218">Microsoft Intune 提供您 ASR 規則的管理功能。</span><span class="sxs-lookup"><span data-stu-id="2c5be-218">Microsoft Intune provides management functionality for your ASR rules.</span></span> <span data-ttu-id="2c5be-219">如果您想要更新您的設定, \*\*\*\* 請選取 [在] 索引標籤中的 [**設定裝置**], 以開啟 Intune 上的裝置管理。</span><span class="sxs-lookup"><span data-stu-id="2c5be-219">If you want to update your settings, select **Get started** under **Configure devices** in the tab to open device management on Intune.</span></span>

### <a name="exclude-files-from-asr-rules"></a><span data-ttu-id="2c5be-220">從 ASR 規則排除檔案</span><span class="sxs-lookup"><span data-stu-id="2c5be-220">Exclude files from ASR rules</span></span>

<span data-ttu-id="2c5be-221">Microsoft 365 security center[會收集您可能想](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/troubleshoot-asr#add-exclusions-for-a-false-positive)要因攻擊面減少規則而從偵測中排除的檔案名。</span><span class="sxs-lookup"><span data-stu-id="2c5be-221">Microsoft 365 security center collects the names of the [files you might want to exclude](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/troubleshoot-asr#add-exclusions-for-a-false-positive) from detections by attack surface reduction rules.</span></span> <span data-ttu-id="2c5be-222">透過排除檔案, 您可以減少 false 肯定偵測, 並更自信地在區塊模式中部署攻擊面減少規則。</span><span class="sxs-lookup"><span data-stu-id="2c5be-222">By excluding files, you can reduce false positive detections and more confidently deploy attack surface reduction rules in block mode.</span></span>

<span data-ttu-id="2c5be-223">排除專案是在 Microsoft Intune 上管理, 但 Microsoft 365 security center 會提供分析工具, 以協助您瞭解檔案。</span><span class="sxs-lookup"><span data-stu-id="2c5be-223">The exclusions are managed on Microsoft Intune, but Microsoft 365 security center provides an analysis tool to help you understand the files.</span></span> <span data-ttu-id="2c5be-224">若要開始收集要排除的檔案, 請移至 [**攻擊面減少規則**報告] 頁面中的 [**新增排除**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="2c5be-224">To start collecting files for exclusion, go to the **Add exclusions** tab in the **Attack surface reduction rules** report page.</span></span>

>[!NOTE]  
><span data-ttu-id="2c5be-225">此工具會依據所有攻擊面減少規則來分析偵測, 但[只有部分規則支援排除](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules)。</span><span class="sxs-lookup"><span data-stu-id="2c5be-225">The tool analyzes detections by all attack surface reduction rules, but [only some rules support exclusions](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules).</span></span>

![新增排除] 索引標籤](./media/security-docs/add-exclusions-tab.png)

<span data-ttu-id="2c5be-227">此表格列出攻擊面減少規則所偵測到的所有檔案名。</span><span class="sxs-lookup"><span data-stu-id="2c5be-227">The table lists all the file names detected by your attack surface reduction rules.</span></span> <span data-ttu-id="2c5be-228">您可以選取檔案, 以查看排除這些檔案的影響:</span><span class="sxs-lookup"><span data-stu-id="2c5be-228">You can select files to review the impact of excluding them:</span></span>

* <span data-ttu-id="2c5be-229">偵測數目減少</span><span class="sxs-lookup"><span data-stu-id="2c5be-229">How many fewer detections</span></span>
* <span data-ttu-id="2c5be-230">最少的裝置報告偵測</span><span class="sxs-lookup"><span data-stu-id="2c5be-230">How many fewer devices report the detections</span></span>

<span data-ttu-id="2c5be-231">若要取得所選檔案的完整路徑以進行排除的清單, 請選取 [**取得排除路徑**]。</span><span class="sxs-lookup"><span data-stu-id="2c5be-231">To get a list of the selected files with their full paths for exclusion, select **Get exclusion paths**.</span></span>

<span data-ttu-id="2c5be-232">**從 Windows 本機安全性授權子系統 (lsass.exe) 偷竊**的 ASR 規則封鎖認證的記錄檔, 會將來源應用程式**lsass.exe**(如偵測到的檔案) 捕獲為標準的系統檔案。</span><span class="sxs-lookup"><span data-stu-id="2c5be-232">Logs for the ASR rule **Block credential stealing from the Windows local security authority subsystem (lsass.exe)** capture the source app **lsass.exe**, a normal system file, as the detected file.</span></span> <span data-ttu-id="2c5be-233">因此, 產生的排除路徑清單會包含此檔案。</span><span class="sxs-lookup"><span data-stu-id="2c5be-233">As a result, the generated list of exclusion paths will include this file.</span></span> <span data-ttu-id="2c5be-234">若要排除觸發此規則的檔案, 而不是**lsass.exe**, 請使用來源應用程式的路徑, 而不要使用偵測到的檔案。</span><span class="sxs-lookup"><span data-stu-id="2c5be-234">To exclude the file that triggered this rule instead of **lsass.exe**, use the path to the source app instead of the detected file.</span></span>

<span data-ttu-id="2c5be-235">若要尋找來源應用程式, 請針對此特定規則執行下列[高級搜尋查詢](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting)(由規則識別碼 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2):</span><span class="sxs-lookup"><span data-stu-id="2c5be-235">To locate the source app, run the following [advanced hunting query](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) for this specific rule (identified by rule ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2):</span></span>

```MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| where AdditionalFields contains "9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2"
| project InitiatingProcessFolderPath, InitiatingProcessFileName
```

#### <a name="check-files-for-exclusion"></a><span data-ttu-id="2c5be-236">檢查檔案是否有排除</span><span class="sxs-lookup"><span data-stu-id="2c5be-236">Check files for exclusion</span></span>
<span data-ttu-id="2c5be-237">從 ASR 排除檔案之前, 建議您檢查檔案, 以判斷它是否確實不是惡意的。</span><span class="sxs-lookup"><span data-stu-id="2c5be-237">Before excluding a file from ASR, we recommend that you inspect the file to determine if it is indeed not malicious.</span></span>

<span data-ttu-id="2c5be-238">若要查看檔案, 請使用 Microsoft Defender 安全中心上的 [檔案[資訊] 頁面](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files)。</span><span class="sxs-lookup"><span data-stu-id="2c5be-238">To review a file, use the [file information page](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) on Microsoft Defender Security Center.</span></span> <span data-ttu-id="2c5be-239">此頁面提供傳播資訊, 以及 VirusTotal 防病毒偵測比率。</span><span class="sxs-lookup"><span data-stu-id="2c5be-239">The page provides prevalence information as well as the VirusTotal antivirus detection ratio.</span></span> <span data-ttu-id="2c5be-240">您也可以使用頁面提交檔案進行深入分析。</span><span class="sxs-lookup"><span data-stu-id="2c5be-240">You can also use the page to submit the file for deep analysis.</span></span>

<span data-ttu-id="2c5be-241">若要在 Microsoft Defender 安全中心找到偵測到的檔案, 請使用下列高級搜尋查詢搜尋所有 ASR 偵測:</span><span class="sxs-lookup"><span data-stu-id="2c5be-241">To locate a detected file in Microsoft Defender Security Center, search for all ASR detections using the following advanced hunting query:</span></span>

```MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| project FolderPath, FileName, SHA1, InitiatingProcessFolderPath, InitiatingProcessFileName, InitiatingProcessSHA1
```

<span data-ttu-id="2c5be-242">在結果中使用**SHA1**或**InitiatingProcessSHA1** , 以使用 Microsoft Defender 安全中心的通用搜尋列來搜尋檔案。</span><span class="sxs-lookup"><span data-stu-id="2c5be-242">Use the **SHA1** or the **InitiatingProcessSHA1** in the results to search for the file using the universal search bar in Microsoft Defender Security Center.</span></span>
