---
title: Office 365 進階威脅保護的檢視報告
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
description: 了解如何尋找及使用報表的 Office 365 進階威脅保護安全性&amp;規範中心。
ms.openlocfilehash: 4a76c6a5b888142dc4c35af432fa61916145d648
ms.sourcegitcommit: 099bbfb1d16b251fd5cf18ec6515faaf9a989176
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/09/2018
ms.locfileid: "25454300"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="0dc21-103">Office 365 進階威脅保護的檢視報告</span><span class="sxs-lookup"><span data-stu-id="0dc21-103">View reports for Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="0dc21-p101">如果您的組織具有[Office 365 進階威脅保護](office-365-atp.md)(ATP) 且您具有[必要權限](#what-permissions-are-needed-to-view-these-reports)，您可以使用數個 ATP 報告安全性&amp;規範中心。(請移至**報表** \> **儀表板**。)</span><span class="sxs-lookup"><span data-stu-id="0dc21-p101">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) and you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can use several ATP reports in the Security &amp; Compliance Center. (Go to **Reports** \> **Dashboard**.)</span></span>
  
![安全性&amp;規範中心儀表板可協助您看到其用於進階威脅保護](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
<span data-ttu-id="0dc21-p102">ATP 報告包含[威脅保護狀態報表](#threat-protection-status-report)、 [ATP 檔案類型的報告](#atp-file-types-report)及[ATP 郵件處理報告](#atp-message-disposition-report)。本文說明 ATP 報告並包含連結至[其他報表檢視](#additional-reports-to-view)。</span><span class="sxs-lookup"><span data-stu-id="0dc21-p102">ATP reports include the [Threat protection status report](#threat-protection-status-report), the [ATP File Types report](#atp-file-types-report), and the [ATP Message Disposition report](#atp-message-disposition-report). This article describes the ATP reports and includes links to [additional reports to view](#additional-reports-to-view).</span></span>
  
## <a name="threat-protection-status-report"></a><span data-ttu-id="0dc21-109">威脅保護狀態報表</span><span class="sxs-lookup"><span data-stu-id="0dc21-109">Threat protection status report</span></span>

<span data-ttu-id="0dc21-p103">**威脅保護狀態**報表是結合惡意內容及惡意電子郵件偵測和封鎖的 Exchange Online 與進階威脅保護的相關資訊的單一檢視。此報表提供惡意內容 （檔案或 Url） 反惡意程式碼引擎、[零小時自動清除 (ZAP)](zero-hour-auto-purge.md)，與進階威脅保護功能，例如[ATP 安全連結](atp-safe-links.md)、 [ATP 所封鎖的唯一的電子郵件訊息的彙總的計數安全的附件](atp-safe-attachments.md)，與[Office 365 的 ATP 反網路釣魚功能](atp-anti-phishing.md)。</span><span class="sxs-lookup"><span data-stu-id="0dc21-p103">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by Exchange Online and Advanced Threat Protection. The report provides an aggregated count of unique email messages with malicious content (files or URLs) blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Advanced Threat Protection features, such as [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing capabilities in Office 365](atp-anti-phishing.md).</span></span>
  
<span data-ttu-id="0dc21-112">若要檢視安全性威脅保護狀態報表&amp;規範管理中心，移至**報表** \> **儀表板** \> **威脅保護狀態**。</span><span class="sxs-lookup"><span data-stu-id="0dc21-112">To view the Threat protection status report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **Threat protection status**.</span></span>
  
![ATP 威脅保護狀態報表](media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
<span data-ttu-id="0dc21-114">若要取得一天的詳細的狀態，將滑鼠停留在圖形。</span><span class="sxs-lookup"><span data-stu-id="0dc21-114">To get detailed status for a day, hover over the graph.</span></span>
  
![工作日的 ATP 威脅保護狀態資料](media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
<span data-ttu-id="0dc21-p104">根據預設，威脅保護狀態報表會顯示過去 7 天的資料。不過，您可以選擇 [**篩選器**並變更至 90 天的檢視資料的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="0dc21-p104">By default, the Threat protection status report shows data for the past seven days. However, you can choose **Filters** and change the date range to view data for up to 90 days.</span></span> 
  
![ATP 威脅保護狀態篩選](media/4f703369-642b-402b-9758-b9c828283410.png)
  
<span data-ttu-id="0dc21-119">您也可以使用 [**檢視資料**] 功能表來變更報表中所顯示的資訊。</span><span class="sxs-lookup"><span data-stu-id="0dc21-119">You can also use the **View data by** menu to change what information is displayed in the report.</span></span> 
  
![檢視 ATP 威脅保護狀態報表的選項](media/4959bf8c-d192-4542-b00b-184e101e7513.png)
  
## <a name="atp-file-types-report"></a><span data-ttu-id="0dc21-121">ATP 檔案類型的報告</span><span class="sxs-lookup"><span data-stu-id="0dc21-121">ATP File Types report</span></span>

<span data-ttu-id="0dc21-122">**ATP 檔案類型**報表顯示偵測到為惡意的[ATP 安全附件](atp-safe-attachments.md)的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="0dc21-122">The **ATP File Types** report shows you the type of files detected as malicious by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>
  
<span data-ttu-id="0dc21-123">若要檢視這份報告，安全性&amp;規範管理中心，移至**報表** \> **儀表板** \> **ATP 檔案類型**。</span><span class="sxs-lookup"><span data-stu-id="0dc21-123">To view this report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **ATP File Types**.</span></span>
  
![ATP 檔案類型的報告](media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
<span data-ttu-id="0dc21-125">當您將滑鼠停留在特定的日子時，您可以看到分解為惡意已偵測到的[ATP 安全附件](atp-safe-attachments.md)的檔案類型及[反垃圾郵件&amp;Office 365 中的反惡意程式碼保護](anti-spam-and-anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="0dc21-125">When you hover over a particular day, you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-spam &amp; anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
![ATP 檔案類型的一天的報告資料](media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## <a name="atp-message-disposition-report"></a><span data-ttu-id="0dc21-127">ATP 郵件處理報告</span><span class="sxs-lookup"><span data-stu-id="0dc21-127">ATP Message Disposition report</span></span>

<span data-ttu-id="0dc21-128">**ATP 郵件處理**報告顯示的電子郵件訊息所偵測到為具有惡意內容所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="0dc21-128">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span> 
  
<span data-ttu-id="0dc21-129">若要檢視這份報告，安全性&amp;規範管理中心，移至**報表** \> **儀表板** \> **ATP 郵件處理**。</span><span class="sxs-lookup"><span data-stu-id="0dc21-129">To view this report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **ATP Message Disposition**.</span></span>
  
![ATP 郵件處理報告](media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
<span data-ttu-id="0dc21-131">當您將滑鼠停留在圖表中的列時，您可以看到動作已偵測到的電子郵件採取的那天。</span><span class="sxs-lookup"><span data-stu-id="0dc21-131">When you hover over a bar in the chart, you can see what actions were taken for detected email for that day.</span></span>
  
![工作日的 ATP 郵件處理報告資料](media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## <a name="additional-reports-to-view"></a><span data-ttu-id="0dc21-133">若要檢視其他報告</span><span class="sxs-lookup"><span data-stu-id="0dc21-133">Additional reports to view</span></span>

<span data-ttu-id="0dc21-p105">除了本文所述 ATP 報告[電子郵件安全性報告](view-email-security-reports.md)中可用的安全性&amp;規範中心。電子郵件安全性報告包含[頂端的寄件者和收件者報告](view-email-security-reports.md#top-senders-and-recipients-report)、[詐騙郵件報告](view-email-security-reports.md#spoof-mail-report)、[垃圾郵件偵測] 報告](view-email-security-reports.md#spam-detections-report)及更多。</span><span class="sxs-lookup"><span data-stu-id="0dc21-p105">In addition to the ATP reports described in this article, [email security reports](view-email-security-reports.md) are available in the Security &amp; Compliance Center. Email security reports include a [Top Senders and Recipients report](view-email-security-reports.md#top-senders-and-recipients-report), a [Spoof Mail report](view-email-security-reports.md#spoof-mail-report), a [Spam Detections report](view-email-security-reports.md#spam-detections-report), and more.</span></span>
  
<span data-ttu-id="0dc21-136">與您的組織有[Office 365 威脅智慧](office-365-ti.md)，如果您也可以[使用瀏覽器安全性&amp;規範中心](use-explorer-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="0dc21-136">And, if your organization has [Office 365 Threat Intelligence](office-365-ti.md), you can also [Use Explorer in the Security &amp; Compliance Center](use-explorer-in-security-and-compliance.md).</span></span>
  
## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="0dc21-137">若要檢視 ATP 報告需要哪些權限？</span><span class="sxs-lookup"><span data-stu-id="0dc21-137">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="0dc21-138">若要檢視及使用本文所述的報告，您必須具備適當的角色指派安全性&amp;規範中心及 Exchange 系統管理中心中。</span><span class="sxs-lookup"><span data-stu-id="0dc21-138">In order to view and use the reports described in this article, you must have an appropriate role assigned in the Security &amp; Compliance Center and in the Exchange Admin Center.</span></span>
  
|<span data-ttu-id="0dc21-139">**角色群組**</span><span class="sxs-lookup"><span data-stu-id="0dc21-139">**Role group**</span></span>|<span data-ttu-id="0dc21-140">**其中指派**</span><span class="sxs-lookup"><span data-stu-id="0dc21-140">**Where assigned**</span></span>|<span data-ttu-id="0dc21-141">**深入了解**</span><span class="sxs-lookup"><span data-stu-id="0dc21-141">**Learn more**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="0dc21-142">下列其中之一：</span><span class="sxs-lookup"><span data-stu-id="0dc21-142">One of the following:</span></span>  <br/>  <span data-ttu-id="0dc21-143">組織管理</span><span class="sxs-lookup"><span data-stu-id="0dc21-143">Organization Management</span></span>  <br/>  <span data-ttu-id="0dc21-144">安全性管理員</span><span class="sxs-lookup"><span data-stu-id="0dc21-144">Security Administrator</span></span>  <br/>  <span data-ttu-id="0dc21-145">安全性讀者</span><span class="sxs-lookup"><span data-stu-id="0dc21-145">Security Reader</span></span>  <br/> |<span data-ttu-id="0dc21-146">安全性&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="0dc21-146">Security &amp; Compliance Center</span></span>  <br/> |[<span data-ttu-id="0dc21-147">Office 365 安全性權限&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="0dc21-147">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md) <br/> |
| <span data-ttu-id="0dc21-148">下列其中之一：</span><span class="sxs-lookup"><span data-stu-id="0dc21-148">One of the following:</span></span>  <br/>  <span data-ttu-id="0dc21-149">組織管理</span><span class="sxs-lookup"><span data-stu-id="0dc21-149">Organization Management</span></span>  <br/>  <span data-ttu-id="0dc21-150">僅限檢視組織管理</span><span class="sxs-lookup"><span data-stu-id="0dc21-150">View-only Organization Management</span></span>  <br/>  <span data-ttu-id="0dc21-151">僅檢視收件者角色</span><span class="sxs-lookup"><span data-stu-id="0dc21-151">View-Only Recipients role</span></span>  <br/>  <span data-ttu-id="0dc21-152">規範管理</span><span class="sxs-lookup"><span data-stu-id="0dc21-152">Compliance Management</span></span>  <br/> |<span data-ttu-id="0dc21-153">Exchange 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="0dc21-153">Exchange Admin Center</span></span>  <br/> |[<span data-ttu-id="0dc21-154">Exchange Online 中的功能權限</span><span class="sxs-lookup"><span data-stu-id="0dc21-154">Feature permissions in Exchange Online</span></span>](https://technet.microsoft.com/library/jj200673%28v=exchg.150%29.aspx) <br/> |
   
## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="0dc21-155">如果報表不顯示資料吗？</span><span class="sxs-lookup"><span data-stu-id="0dc21-155">What if the reports aren't showing data?</span></span>

<span data-ttu-id="0dc21-p106">如果您看不見的資料在報告中，再次檢查您的原則已正確設定。您的組織必須[ATP 安全連結原則](set-up-atp-safe-links-policies.md)和[ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)定義 ATP protection 順序設為就地。另請參閱 ＜ [Office 365 中的反垃圾郵件和反惡意程式碼保護](anti-spam-and-anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="0dc21-p106">If you are not seeing data in your reports, double-check that your policies are set up correctly. Your organization must have [ATP Safe Links policies](set-up-atp-safe-links-policies.md) and [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place. Also see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="0dc21-159">相關主題</span><span class="sxs-lookup"><span data-stu-id="0dc21-159">Related topics</span></span>

[<span data-ttu-id="0dc21-160">報告與 Office 365 安全性前瞻&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="0dc21-160">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
<span data-ttu-id="0dc21-161">[在 [安全性] 中建立報表的排程&amp;規範中心](create-a-schedule-for-a-report.md)</span><span class="sxs-lookup"><span data-stu-id="0dc21-161">[Create a schedule for a report in the Security &amp; Compliance Center](create-a-schedule-for-a-report.md)</span></span>
  
[<span data-ttu-id="0dc21-162">設定並下載安全性的自訂報告&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="0dc21-162">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](set-up-and-download-a-custom-report.md)
  

