---
title: Office 365 進階威脅保護的檢視報告
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/13/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection: M365-security-compliance
description: 了解如何尋找及使用報表的 Office 365 進階威脅保護安全性&amp;規範中心。
ms.openlocfilehash: a27fdf6c7d04a2526873047d4e2a33bb283878b3
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995224"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="7145f-103">Office 365 進階威脅保護的檢視報告</span><span class="sxs-lookup"><span data-stu-id="7145f-103">View reports for Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="7145f-p101">如果您的組織具有[Office 365 進階威脅保護](office-365-atp.md)(ATP) 且您具有[必要權限](#what-permissions-are-needed-to-view-these-reports)，您可以使用數個 ATP 報告安全性&amp;規範中心。(請移至**報表** \> **儀表板**。)</span><span class="sxs-lookup"><span data-stu-id="7145f-p101">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) and you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can use several ATP reports in the Security &amp; Compliance Center. (Go to **Reports** \> **Dashboard**.)</span></span>
  
![安全性&amp;規範中心儀表板可協助您看到其用於進階威脅保護](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
<span data-ttu-id="7145f-p102">ATP 報告包含[威脅保護狀態報表](#threat-protection-status-report)、 [ATP 檔案類型的報告](#atp-file-types-report)及[ATP 郵件處理報告](#atp-message-disposition-report)。本文說明 ATP 報告並包含連結至[其他報表檢視](#additional-reports-to-view)。</span><span class="sxs-lookup"><span data-stu-id="7145f-p102">ATP reports include the [Threat Protection Status report](#threat-protection-status-report), the [ATP File Types report](#atp-file-types-report), and the [ATP Message Disposition report](#atp-message-disposition-report). This article describes the ATP reports and includes links to [additional reports to view](#additional-reports-to-view).</span></span>
  
## <a name="threat-protection-status-report"></a><span data-ttu-id="7145f-109">威脅保護狀態報表</span><span class="sxs-lookup"><span data-stu-id="7145f-109">Threat Protection Status report</span></span>

<span data-ttu-id="7145f-p103">**威脅保護狀態**報表是結合惡意內容及惡意電子郵件偵測和封鎖的[Exchange Online Protection](eop/exchange-online-protection-overview.md) (EOP) 和[Office 365 ATP](office-365-atp.md)的相關資訊的單一檢視。此報表提供彙總惡意內容 （檔案或網站位址 (Url)） 封鎖的反惡意程式碼引擎、[零小時自動清除 (ZAP)](zero-hour-auto-purge.md)，與 ATP 功能，例如[ATP 安全連結](atp-safe-links.md)、 [ATP 安全的唯一的電子郵件數附件](atp-safe-attachments.md)，與[ATP 反網路釣魚功能](atp-anti-phishing.md)。</span><span class="sxs-lookup"><span data-stu-id="7145f-p103">The **Threat Protection Status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](eop/exchange-online-protection-overview.md) (EOP) and [Office 365 ATP](office-365-atp.md). The report provides an aggregated count of unique email messages with malicious content (files or website addresses (URLs)) blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and ATP features, such as [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing capabilities](atp-anti-phishing.md).</span></span>

> [!NOTE]
> <span data-ttu-id="7145f-p104">威脅保護狀態報表是供使用者具有[Office 365 ATP](office-365-atp.md)或[Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP);不過，ATP 客戶的威脅保護狀態報表中所顯示的資訊可能會包含超過 EOP 客戶可以看到不同的資料。例如，ATP 客戶的威脅保護狀態報表會包含[SharePoint Online、 OneDrive 或 Microsoft 小組中偵測到惡意檔案](atp-for-spo-odb-and-teams.md)的相關資訊。這類資訊是專屬於 ATP、，因此有 EOP，但不是 ATP 的客戶不會看到這些其威脅保護狀態報告的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="7145f-p104">A Threat Protection Status report is available to customers who have either [Office 365 ATP](office-365-atp.md) or [Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see. For example, the Threat Protection Status report for ATP customers will contain information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md). Such information is specific to ATP, so customers who have EOP but not ATP will not see those details in their Threat Protection Status report.</span></span>
  
<span data-ttu-id="7145f-115">若要檢視中的潛在威脅保護狀態報表[安全性&amp;規範中心](https://protection.office.com)、 移至 [**報表** \> **儀表板** \> **威脅保護狀態**。</span><span class="sxs-lookup"><span data-stu-id="7145f-115">To view the Threat Protection Status report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
  
![ATP 威脅保護狀態報表](media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
<span data-ttu-id="7145f-117">若要取得一天的詳細的狀態，將滑鼠停留在圖形。</span><span class="sxs-lookup"><span data-stu-id="7145f-117">To get detailed status for a day, hover over the graph.</span></span>
  
![工作日的 ATP 威脅保護狀態資料](media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
<span data-ttu-id="7145f-p105">根據預設，威脅保護狀態報表會顯示過去 7 天的資料。不過，您可以選擇 [**篩選器**並變更至 90 天的檢視資料的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="7145f-p105">By default, the Threat Protection Status report shows data for the past seven days. However, you can choose **Filters** and change the date range to view data for up to 90 days.</span></span> 
  
![ATP 威脅保護狀態篩選](media/4f703369-642b-402b-9758-b9c828283410.png)
  
<span data-ttu-id="7145f-122">您也可以使用 [**檢視資料**] 功能表來變更報表中所顯示的資訊。</span><span class="sxs-lookup"><span data-stu-id="7145f-122">You can also use the **View data by** menu to change what information is displayed in the report.</span></span> 
  
![檢視 ATP 威脅保護狀態報表的選項](media/4959bf8c-d192-4542-b00b-184e101e7513.png)
  
## <a name="atp-file-types-report"></a><span data-ttu-id="7145f-124">ATP 檔案類型的報告</span><span class="sxs-lookup"><span data-stu-id="7145f-124">ATP File Types report</span></span>

<span data-ttu-id="7145f-125">**ATP 檔案類型**報表顯示偵測到為惡意的[ATP 安全附件](atp-safe-attachments.md)的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="7145f-125">The **ATP File Types** report shows you the type of files detected as malicious by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>
  
<span data-ttu-id="7145f-126">若要檢視中的這份報告，[安全性&amp;規範中心](https://protection.office.com)、 移至 [**報表** \> **儀表板** \> **ATP 檔案類型**。</span><span class="sxs-lookup"><span data-stu-id="7145f-126">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP File Types**.</span></span>
  
![ATP 檔案類型的報告](media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
<span data-ttu-id="7145f-128">當您將滑鼠停留在特定的日子時，您可以看到分解為惡意已偵測到的[ATP 安全附件](atp-safe-attachments.md)的檔案類型及[反垃圾郵件&amp;Office 365 中的反惡意程式碼保護](anti-spam-and-anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="7145f-128">When you hover over a particular day, you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-spam &amp; anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
![ATP 檔案類型的一天的報告資料](media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## <a name="atp-message-disposition-report"></a><span data-ttu-id="7145f-130">ATP 郵件處理報告</span><span class="sxs-lookup"><span data-stu-id="7145f-130">ATP Message Disposition report</span></span>

<span data-ttu-id="7145f-131">**ATP 郵件處理**報告顯示的電子郵件訊息所偵測到為具有惡意內容所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="7145f-131">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span> 
  
<span data-ttu-id="7145f-132">若要檢視中的這份報告，[安全性&amp;規範中心](https://protection.office.com)、 移至 [**報表** \> **儀表板** \> **ATP 郵件處理**。</span><span class="sxs-lookup"><span data-stu-id="7145f-132">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP Message Disposition**.</span></span>
  
![ATP 郵件處理報告](media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
<span data-ttu-id="7145f-134">當您將滑鼠停留在圖表中的列時，您可以看到動作已偵測到的電子郵件採取的那天。</span><span class="sxs-lookup"><span data-stu-id="7145f-134">When you hover over a bar in the chart, you can see what actions were taken for detected email for that day.</span></span>
  
![工作日的 ATP 郵件處理報告資料](media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## <a name="additional-reports-to-view"></a><span data-ttu-id="7145f-136">若要檢視其他報告</span><span class="sxs-lookup"><span data-stu-id="7145f-136">Additional reports to view</span></span>

<span data-ttu-id="7145f-137">除了本文所述 ATP 報告、 數個其他報告可用，如下表所述：</span><span class="sxs-lookup"><span data-stu-id="7145f-137">In addition to the ATP reports described in this article, several other reports are available, as described in the following table:</span></span>

|<span data-ttu-id="7145f-138">報告類型</span><span class="sxs-lookup"><span data-stu-id="7145f-138">Report type</span></span>  |<span data-ttu-id="7145f-139">深入了解</span><span class="sxs-lookup"><span data-stu-id="7145f-139">Learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="7145f-140">**電子郵件安全性報表**，例如頂端的寄件者和收件者報告、 詐騙郵件報表及垃圾郵件偵測] 報告。</span><span class="sxs-lookup"><span data-stu-id="7145f-140">**Email security reports**, such as a Top Senders and Recipients report, a Spoof Mail report, and a Spam Detections report.</span></span> | <span data-ttu-id="7145f-141">[在 [安全性] 中檢視電子郵件安全性報表&amp;規範中心](view-email-security-reports.md)</span><span class="sxs-lookup"><span data-stu-id="7145f-141">[View email security reports in the Security &amp; Compliance Center](view-email-security-reports.md)</span></span>        |
|<span data-ttu-id="7145f-142">**瀏覽器**（也稱為威脅瀏覽器，這包含在[Office 365 威脅智慧](office-365-ti.md)）</span><span class="sxs-lookup"><span data-stu-id="7145f-142">**Explorer** (also referred to as Threat Explorer, this is included in [Office 365 Threat Intelligence](office-365-ti.md))</span></span>     | [<span data-ttu-id="7145f-143">使用瀏覽器安全性&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="7145f-143">Use Explorer in the Security &amp; Compliance Center</span></span>](use-explorer-in-security-and-compliance.md)        |
|<span data-ttu-id="7145f-p106">**EOP 和 ATP 結果**（這是您透過 PowerShell 產生自訂報告）。這份報告包含的資訊，例如網域、 日期、 事件類型、 Direction、 動作和訊息計數。</span><span class="sxs-lookup"><span data-stu-id="7145f-p106">**EOP and ATP results** (This is a custom report you generate by using PowerShell). This report contains information, such as Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>  | [<span data-ttu-id="7145f-146">取得 MailTrafficATPReport 指令程式參考 （英文)</span><span class="sxs-lookup"><span data-stu-id="7145f-146">Get-MailTrafficATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-mailtrafficatpreport?view=exchange-ps) |
|<span data-ttu-id="7145f-p107">**EOP 和 ATP 偵測**（這是您透過 PowerShell 產生自訂報告）。這份報告包含惡意檔案或 Url、 網路釣魚嘗試、 模擬、 及其他電子郵件或檔案中的潛在威脅詳細資料。</span><span class="sxs-lookup"><span data-stu-id="7145f-p107">**EOP and ATP detections** (This is a custom report you generate by using PowerShell). This report contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>   | [<span data-ttu-id="7145f-149">取得 MailDetailATPReport 指令程式參考 （英文)</span><span class="sxs-lookup"><span data-stu-id="7145f-149">Get-MailDetailATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-maildetailatpreport?view=exchange-ps)        |

  
## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="7145f-150">若要檢視 ATP 報告需要哪些權限？</span><span class="sxs-lookup"><span data-stu-id="7145f-150">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="7145f-151">若要檢視和使用本文所述的報告**您必須具有適當的角色指派給這兩種安全性&amp;規範中心及 Exchange 系統管理中心**。</span><span class="sxs-lookup"><span data-stu-id="7145f-151">In order to view and use the reports described in this article, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange Admin Center**.</span></span>

- <span data-ttu-id="7145f-152">Security&amp;規範中心，您必須具備一個指派的下列角色：</span><span class="sxs-lookup"><span data-stu-id="7145f-152">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="7145f-153">組織管理</span><span class="sxs-lookup"><span data-stu-id="7145f-153">Organization Management</span></span>
    - <span data-ttu-id="7145f-154">安全性管理員 (這可被指派在 Azure Active Directory 系統管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="7145f-154">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>
    - <span data-ttu-id="7145f-155">安全性讀者</span><span class="sxs-lookup"><span data-stu-id="7145f-155">Security Reader</span></span>

- <span data-ttu-id="7145f-156">Exchange online，您必須具備一個指派 Exchange 系統管理中心中的下列角色 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) 或使用 PowerShell cmdlet (請參閱[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))：</span><span class="sxs-lookup"><span data-stu-id="7145f-156">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span></span>
    - <span data-ttu-id="7145f-157">組織管理</span><span class="sxs-lookup"><span data-stu-id="7145f-157">Organization Management</span></span>
    - <span data-ttu-id="7145f-158">僅檢視組織管理</span><span class="sxs-lookup"><span data-stu-id="7145f-158">View-only Organization Management</span></span>
    - <span data-ttu-id="7145f-159">僅檢視收件者角色</span><span class="sxs-lookup"><span data-stu-id="7145f-159">View-Only Recipients role</span></span>
    - <span data-ttu-id="7145f-160">合規性管理</span><span class="sxs-lookup"><span data-stu-id="7145f-160">Compliance Management</span></span>

<span data-ttu-id="7145f-161">若要深入了解，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="7145f-161">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="7145f-162">Office 365 安全性權限&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="7145f-162">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="7145f-163">Exchange Online 中的功能權限</span><span class="sxs-lookup"><span data-stu-id="7145f-163">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="7145f-164">如果報表不顯示資料吗？</span><span class="sxs-lookup"><span data-stu-id="7145f-164">What if the reports aren't showing data?</span></span>

<span data-ttu-id="7145f-p108">如果您看不見資料 ATP 報告中，再次檢查您的原則已正確設定。您的組織必須[ATP 安全連結原則](set-up-atp-safe-links-policies.md)和[ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)定義 ATP protection 順序設為就地。另請參閱 ＜ [Office 365 中的反垃圾郵件和反惡意程式碼保護](anti-spam-and-anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="7145f-p108">If you are not seeing data in your ATP reports, double-check that your policies are set up correctly. Your organization must have [ATP Safe Links policies](set-up-atp-safe-links-policies.md) and [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place. Also see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="7145f-168">相關主題</span><span class="sxs-lookup"><span data-stu-id="7145f-168">Related topics</span></span>

[<span data-ttu-id="7145f-169">報告與 Office 365 安全性前瞻&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="7145f-169">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
<span data-ttu-id="7145f-170">[在 [安全性] 中建立報表的排程&amp;規範中心](create-a-schedule-for-a-report.md)</span><span class="sxs-lookup"><span data-stu-id="7145f-170">[Create a schedule for a report in the Security &amp; Compliance Center](create-a-schedule-for-a-report.md)</span></span>
  
[<span data-ttu-id="7145f-171">設定並下載安全性的自訂報告&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="7145f-171">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](set-up-and-download-a-custom-report.md)
  

