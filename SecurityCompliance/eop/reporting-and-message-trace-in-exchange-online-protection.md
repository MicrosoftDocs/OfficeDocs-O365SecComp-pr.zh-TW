---
title: Exchange Online Protection 的報告與訊息追蹤
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 12/18/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
description: Microsoft Exchange Online Protection (EOP) 提供許多不同的報告，可協助您判斷貴組織的整體狀態與健全狀況。還有可協助您疑難排解特定事件 (例如郵件未抵達其預定收件者) 的工具，以及有助於符合規範需求的稽核報告。下表將說明 EOP 系統管理員可以使用的報告和疑難排解工具。
ms.openlocfilehash: 01a09b2b4b72161352af3793686c6cc888e44e29
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027140"
---
# <a name="reporting-and-message-trace-in-exchange-online-protection"></a><span data-ttu-id="22f57-105">Exchange Online Protection 的報告與訊息追蹤</span><span class="sxs-lookup"><span data-stu-id="22f57-105">Reporting and message trace in Exchange Online Protection</span></span>

<span data-ttu-id="22f57-p102">Microsoft Exchange Online Protection (EOP) 提供許多不同的報告可協助您決定的整體狀態和組織的狀況。也有工具來協助您疑難排解特定事件 （例如郵件給其預定的收件者無法到達） 和稽核報告來協助規範需求。</span><span class="sxs-lookup"><span data-stu-id="22f57-p102">Microsoft Exchange Online Protection (EOP) offers many different reports that can help you determine the overall status and health of your organization. There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span> 

## <a name="usage-reports"></a><span data-ttu-id="22f57-108">使用情況報告</span><span class="sxs-lookup"><span data-stu-id="22f57-108">Usage reports</span></span>

<span data-ttu-id="22f57-109">**Office 365 群組活動**檢視建立及使用 Office 365 群組數目的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="22f57-109">**Office 365 groups activity** View information about the number of Office 365 groups that are created and used.</span></span>  

<span data-ttu-id="22f57-110">**電子郵件活動**檢視傳送、 接收和讀取整個組織中與特定使用者的郵件數目的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="22f57-110">**Email activity** View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>  

<span data-ttu-id="22f57-p103">**電子郵件應用程式使用狀況**檢視所使用的電子郵件應用程式的相關資訊。這包括每個應用程式的連線總數和要連線的 Outlook 版本。</span><span class="sxs-lookup"><span data-stu-id="22f57-p103">**Email app usage** View information about the email apps that are used. This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>  

<span data-ttu-id="22f57-113">**信箱使用量**檢視所使用的儲存區的相關資訊、 配額使用率、 項目計數及信箱的最後活動 （傳送或讀取的活動）。</span><span class="sxs-lookup"><span data-stu-id="22f57-113">**Mailbox usage** View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="22f57-114">請參閱下列資源如需詳細資訊：</span><span class="sxs-lookup"><span data-stu-id="22f57-114">See the following resources for more information:</span></span>

- [<span data-ttu-id="22f57-115">Office 365 系統管理中心-Office 365 中會報告群組</span><span class="sxs-lookup"><span data-stu-id="22f57-115">Office 365 Reports in the admin center - Office 365 groups</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861610) 
- [<span data-ttu-id="22f57-116">Office 365 系統管理中心報告的-電子郵件活動</span><span class="sxs-lookup"><span data-stu-id="22f57-116">Office 365 Reports in the Admin Center - Email activity</span></span>](https://go.microsoft.com/fwlink/p/?linkid=859706) 
- [<span data-ttu-id="22f57-117">Office 365 系統管理中心報告的-電子郵件應用程式使用狀況</span><span class="sxs-lookup"><span data-stu-id="22f57-117">Office 365 Reports in the Admin Center - Email apps usage</span></span>](https://go.microsoft.com/fwlink/p/?linkid=859707)
- [<span data-ttu-id="22f57-118">Office 365 系統管理中心報告的-信箱使用量</span><span class="sxs-lookup"><span data-stu-id="22f57-118">Office 365 Reports in the Admin Center - Mailbox usage</span></span>](https://go.microsoft.com/fwlink/p/?linkid=859708)

## <a name="security-amp-compliance-reports-in-the-office-365-admin-center"></a><span data-ttu-id="22f57-119">安全性&amp;Office 365 系統管理中心中的規範報告</span><span class="sxs-lookup"><span data-stu-id="22f57-119">Security &amp; compliance reports in the Office 365 admin center</span></span>

<span data-ttu-id="22f57-120">這些增強的報告提供的互動式報表體驗若是 EOP 管理員，包括摘要資訊和向下切入如需詳細資訊的能力。</span><span class="sxs-lookup"><span data-stu-id="22f57-120">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>  

<span data-ttu-id="22f57-121">**進階威脅保護 (ATP)** 檢視資訊安全連結和安全附件因受到 ATP 的一部分。</span><span class="sxs-lookup"><span data-stu-id="22f57-121">**Advanced Threat Protection (ATP)** View information about safe links and safe attachments that are part of ATP.</span></span>  

<span data-ttu-id="22f57-122">**EOP**檢視有關惡意程式碼偵測、 詐騙的郵件、 垃圾郵件偵測及從您的組織的郵件流程的資訊。</span><span class="sxs-lookup"><span data-stu-id="22f57-122">**EOP** View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>  

[<span data-ttu-id="22f57-123">檢視進階威脅保護與 Exchange Online Protection 的報告</span><span class="sxs-lookup"><span data-stu-id="22f57-123">View reports for Advanced Threat Protection and Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/p/?linkid=852409) 

##<a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="22f57-124">使用 Microsoft Graph 的自訂報告</span><span class="sxs-lookup"><span data-stu-id="22f57-124">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="22f57-125">以程式設計方式建立[使用 Microsoft Graph 中的 Office 365 流量報告](https://go.microsoft.com/fwlink/p/?linkid=865135)的副中可用的 Office 365 系統管理中心使用 Microsoft Graph 查看報告</span><span class="sxs-lookup"><span data-stu-id="22f57-125">Programmatically create reports that are available in the Office 365 admin center by using Microsoft Graph  See the subtopics of [Working with Office 365 usage reports in Microsoft Graph](https://go.microsoft.com/fwlink/p/?linkid=865135)</span></span> 

##<a name="custom-reports-using-reporting-web-services"></a><span data-ttu-id="22f57-126">使用報告 Web 服務的自訂報告</span><span class="sxs-lookup"><span data-stu-id="22f57-126">Custom reports using reporting web services</span></span>

<span data-ttu-id="22f57-127">以程式設計方式從可用 Exchange Online Protection PowerShell 使用 REST/ODATA2 查詢篩選報告指令程式建立報表。</span><span class="sxs-lookup"><span data-stu-id="22f57-127">Programmatically create reports from the available Exchange Online Protection PowerShell reporting cmdlets by using REST/ODATA2 query filtering.</span></span>

<span data-ttu-id="22f57-128">請參閱[Office 365 報告 Web 服務](https://go.microsoft.com/fwlink/p/?LinkId=279926)</span><span class="sxs-lookup"><span data-stu-id="22f57-128">See [Office 365 Reporting Web Services](https://go.microsoft.com/fwlink/p/?LinkId=279926)</span></span> 

##<a name="message-trace"></a><span data-ttu-id="22f57-129">郵件追蹤</span><span class="sxs-lookup"><span data-stu-id="22f57-129">Message trace</span></span>

<span data-ttu-id="22f57-p104">當出差經由 EOP，線段電子郵件訊息。您可以決定電子郵件訊息若已接收、 拒絕、 延遲、 或服務所傳送。它也會顯示動作所採取的郵件上之前它達到其最終狀態。</span><span class="sxs-lookup"><span data-stu-id="22f57-p104">Follows email messages as they travel through EOP. You can determine if an email message was received, rejected, deferred, or delivered by the service. It also shows what actions were taken on the message before it reached its final status.</span></span>  

<span data-ttu-id="22f57-133">您可以使用這項資訊來快速回答使用者的問題、 疑難排解郵件流程問題、 驗證原則的變更，並連絡技術支援人員以取得協助的必要性。</span><span class="sxs-lookup"><span data-stu-id="22f57-133">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>  

<span data-ttu-id="22f57-134">請參閱[追蹤電子郵件](http://technet.microsoft.com/library/0c83cde6-5b09-4106-8587-c200cdc59094.aspx)</span><span class="sxs-lookup"><span data-stu-id="22f57-134">See [Trace an Email Message](http://technet.microsoft.com/library/0c83cde6-5b09-4106-8587-c200cdc59094.aspx)</span></span> 

## <a name="audit-logging"></a><span data-ttu-id="22f57-135">稽核記錄</span><span class="sxs-lookup"><span data-stu-id="22f57-135">Audit logging</span></span>

<span data-ttu-id="22f57-p105">追蹤特定對您組織管理員所做的變更。這些報告可協助您疑難排解設定問題或尋找安全性或規範相關問題的原因。 請參閱[在 EOP 中的稽核報告](auditing-reports-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="22f57-p105">Tracks specific changes made by admins to your organization. These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.  see [Auditing reports in EOP](auditing-reports-in-eop.md)</span></span> 


## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="22f57-139">報告和郵件追蹤資料的可用性與延遲</span><span class="sxs-lookup"><span data-stu-id="22f57-139">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="22f57-140">下表說明可使用 EOP 報告和郵件追蹤資料的時間及時間長短。</span><span class="sxs-lookup"><span data-stu-id="22f57-140">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="22f57-141">**報告類型**</span><span class="sxs-lookup"><span data-stu-id="22f57-141">**Report type**</span></span> <br/> |<span data-ttu-id="22f57-142">**資料可用時間 (回顧期間)**</span><span class="sxs-lookup"><span data-stu-id="22f57-142">**Data available for (look back period)**</span></span> <br/> |<span data-ttu-id="22f57-143">**延遲**</span><span class="sxs-lookup"><span data-stu-id="22f57-143">**Latency**</span></span> <br/> |
|<span data-ttu-id="22f57-144">郵件保護摘要報告</span><span class="sxs-lookup"><span data-stu-id="22f57-144">Mail protection summary reports</span></span>  <br/> |<span data-ttu-id="22f57-145">90 天</span><span class="sxs-lookup"><span data-stu-id="22f57-145">90 days</span></span>  <br/> |<span data-ttu-id="22f57-p106">郵件資料彙總大部分會在 24 到 48 小時內完成。部分次要的增量彙總變更最多存在 5 天。</span><span class="sxs-lookup"><span data-stu-id="22f57-p106">Message data aggregation is mostly complete within 24-48 hours. Some minor incremental aggregated changes may occur for up to 5 days.</span></span>  <br/> |
|<span data-ttu-id="22f57-148">郵件保護詳細資料報告</span><span class="sxs-lookup"><span data-stu-id="22f57-148">Mail protection detail reports</span></span>  <br/> |<span data-ttu-id="22f57-149">90 天</span><span class="sxs-lookup"><span data-stu-id="22f57-149">90 days</span></span>  <br/> |<span data-ttu-id="22f57-p107">針對 7 天內的詳細資料，資料應於 24 小時內出現，但可能要等到 48 小時後才完成。部分次要的增量變更最多存在 5 天。</span><span class="sxs-lookup"><span data-stu-id="22f57-p107">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours. Some minor incremental changes may occur for up to 5 days.</span></span>  <br/> <span data-ttu-id="22f57-152">若要檢視超過 7 天之郵件的詳細資料報告，結果可能需要幾個小時。</span><span class="sxs-lookup"><span data-stu-id="22f57-152">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>  <br/> |
|<span data-ttu-id="22f57-153">郵件追蹤資料</span><span class="sxs-lookup"><span data-stu-id="22f57-153">Message trace data</span></span>  <br/> |<span data-ttu-id="22f57-154">90 天</span><span class="sxs-lookup"><span data-stu-id="22f57-154">90 days</span></span>  <br/> |<span data-ttu-id="22f57-155">針對 7 天內的郵件執行郵件追蹤時，郵件應於 5 到 30 分鐘內出現。</span><span class="sxs-lookup"><span data-stu-id="22f57-155">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span>  <br/> <span data-ttu-id="22f57-156">針對超過 7 天的郵件執行郵件追蹤時，結果可能需要幾個小時。</span><span class="sxs-lookup"><span data-stu-id="22f57-156">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="22f57-157">資料可用性和延遲性都相同是否透過 Office 365 系統管理中心或遠端 PowerShell 來要求。</span><span class="sxs-lookup"><span data-stu-id="22f57-157">Data availability and latency is the same whether requested via the Office 365 admin center or remote PowerShell.</span></span> 
  

