---
title: 預設的 DLP 原則快速入門
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/10/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e0ada764-6422-4b44-9472-513bed04837b
description: 您甚至是建立您第一資料外洩防護 (DLP) 原則之前，DLP 協助保護您的機密資訊與預設原則。此預設的原則和敏感內容安全的電子郵件或文件包含信用卡卡號碼時通知您已與組織外部人員共用其建議 （如下所示） 說明保留。
ms.openlocfilehash: 3182abcc825c8e27da83ebfb64ed8b2cba6ebcb3
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341314"
---
# <a name="get-started-with-the-default-dlp-policy"></a><span data-ttu-id="7d652-104">預設的 DLP 原則快速入門</span><span class="sxs-lookup"><span data-stu-id="7d652-104">Get started with the default DLP policy</span></span>

<span data-ttu-id="7d652-p102">您甚至是建立您第一資料外洩防護 (DLP) 原則之前，DLP 協助保護您的機密資訊與預設原則。此預設的原則和敏感內容安全的電子郵件或文件包含信用卡卡號碼時通知您已與組織外部人員共用其建議 （如下所示） 說明保留。您會看到這項建議在**首頁**上的安全性&amp;合規性中心。</span><span class="sxs-lookup"><span data-stu-id="7d652-p102">Before you even create your first data loss prevention (DLP) policy, DLP is helping to protect your sensitive information with a default policy. This default policy and its recommendation (shown below) help keep your sensitive content secure by notifying you when email or documents containing a credit card number were shared with someone outside your organization. You'll see this recommendation on the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="7d652-p103">您可以使用此 widget 快速檢視時機與討論方向共用多少機密資訊，然後調整 [預設的 DLP 原則，只要按一下或兩個。您也可以編輯任何時候預設的 DLP 原則，因為它是完全可自訂。請注意，如果您沒有看到一開始，建議嘗試按一下 [ **+ 詳細**底部的 [**為您的建議**] 區段中。</span><span class="sxs-lookup"><span data-stu-id="7d652-p103">You can use this widget to quickly view when and how much sensitive information was shared, and then refine the default DLP policy in just a click or two. You can also edit the default DLP policy at any time because it's fully customizable. Note that if you don't see the recommendation at first, try clicking **+More** at the bottom of the **Recommended for you** section.</span></span> 
  
![名為進一步的 widget 保護共用的內容](media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a><span data-ttu-id="7d652-112">檢視報表，並調整預設的 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="7d652-112">View the report and refine the default DLP policy</span></span>

<span data-ttu-id="7d652-113">當] 小工具會顯示使用者已與組織外部人員共用機密資訊時，請底部選擇**調整 DLP 原則**。</span><span class="sxs-lookup"><span data-stu-id="7d652-113">When the widget shows you that users have shared sensitive information with people outside your organization, choose **Refine DLP policy** at the bottom.</span></span> 
  
<span data-ttu-id="7d652-p104">詳細的報告顯示過去 30 天內何時和如何共用包含信用卡號碼的內容量。請注意規則相符項目可能需要多達 48 小時] 小工具上顯示。</span><span class="sxs-lookup"><span data-stu-id="7d652-p104">The detailed report shows you when and how much content containing credit card numbers was shared in the past 30 days. Note that rule matches can take up to 48 hours to show up in the widget.</span></span>
  
<span data-ttu-id="7d652-116">若要協助保護敏感資訊，也就是預設的 DLP 原則：</span><span class="sxs-lookup"><span data-stu-id="7d652-116">To help protect the sensitive information, the default DLP policy:</span></span>
  
- <span data-ttu-id="7d652-117">偵測與組織外部人員共用 Exchange、 SharePoint 和 OneDrive 包含至少一個信用卡號碼中的內容。</span><span class="sxs-lookup"><span data-stu-id="7d652-117">Detects when content in Exchange, SharePoint, and OneDrive that contains at least one credit card number is shared with people outside your organization.</span></span>
    
- <span data-ttu-id="7d652-p105">顯示原則提示，並將電子郵件通知傳送給使用者，當他們嘗試與組織外部人員共用機密資訊。如需有關這些選項的詳細資訊，請參閱[傳送電子郵件通知並顯示原則提示的 DLP 原則](use-notifications-and-policy-tips.md)。</span><span class="sxs-lookup"><span data-stu-id="7d652-p105">Shows a policy tip and sends an email notification to users when they attempt to share this sensitive information with people outside your organization. For more information on these options, see [Send email notifications and show policy tips for DLP policies](use-notifications-and-policy-tips.md).</span></span>
    
- <span data-ttu-id="7d652-p106">讓您可以追蹤之類的使用者與組織外部人員共用內容及他們沒有的時，會產生詳細的活動報告。您可以使用[DLP 報告](view-the-dlp-reports.md)和[稽核記錄檔資料](search-the-audit-log-in-security-and-compliance.md)(其中**活動** = **DLP**) 若要查看此資訊。</span><span class="sxs-lookup"><span data-stu-id="7d652-p106">Generates detailed activity reports so that you can track things like who shared the content with people outside your organization and when they did it. You can use the [DLP reports](view-the-dlp-reports.md) and [audit log data](search-the-audit-log-in-security-and-compliance.md) (where **Activity** = **DLP**) to see this information.</span></span>
    
<span data-ttu-id="7d652-122">若要快速修改預設的 DLP 原則，您可以選擇讓它：</span><span class="sxs-lookup"><span data-stu-id="7d652-122">To quickly refine the default DLP policy, you can choose to have it:</span></span>
  
- <span data-ttu-id="7d652-123">您傳送附隨報告電子郵件時的使用者與組織外部人員共用機密資訊。</span><span class="sxs-lookup"><span data-stu-id="7d652-123">Send you an incident report email when users share this sensitive information with people outside your organization.</span></span>
    
- <span data-ttu-id="7d652-124">將其他使用者新增至電子郵件附隨報告。</span><span class="sxs-lookup"><span data-stu-id="7d652-124">Add other users to the email incident report.</span></span>
    
- <span data-ttu-id="7d652-125">封鎖存取內容包含敏感資訊，但允許使用者覆寫和共用或傳送如果他們需要。</span><span class="sxs-lookup"><span data-stu-id="7d652-125">Block access to the content containing the sensitive information, but allow the user to override and share or send if they need to.</span></span>
    
<span data-ttu-id="7d652-126">如需有關附隨報告或限制存取的詳細資訊，請參閱 <<c0>資料外洩防護原則概觀。</span><span class="sxs-lookup"><span data-stu-id="7d652-126">For more information on incident reports or restricting access, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
<span data-ttu-id="7d652-127">如果您想要稍後變更這些選項，您可以編輯預設的 DLP 原則隨時-請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="7d652-127">If you want to change these options later, you can edit the default DLP policy at any time - see the next section.</span></span>
  
![設定名為進一步的 widget 保護共用的內容](media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a><span data-ttu-id="7d652-129">編輯預設的 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="7d652-129">Edit the default DLP policy</span></span>

<span data-ttu-id="7d652-130">此原則名為 「**預設 Office 365 DLP 原則**，並出現在 [**資料外洩防護**] 下的安全性**原則**] 頁面上&amp;合規性中心。</span><span class="sxs-lookup"><span data-stu-id="7d652-130">This policy is named **Default Office 365 DLP policy** and appears under **Data loss prevention** on the **Policy** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="7d652-p107">此原則可完全自訂，任何，從頭開始建立您自己的 DLP 原則相同。您也可以關閉或刪除原則，使您的使用者不會再收到原則提示或電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="7d652-p107">This policy is fully customizable, the same as any DLP policy that you create yourself from scratch. You can also turn off or delete the policy, so that your users no longer receive policy tips or email notifications.</span></span>
  
![名為預設的 Office 365 DLP 原則的 DLP 原則](media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a><span data-ttu-id="7d652-134">當] 小工具會以及不會出現</span><span class="sxs-lookup"><span data-stu-id="7d652-134">When the widget does and does not appear</span></span>

<span data-ttu-id="7d652-135">Widget 名為**進一步保護共用的內容**會出現在 [**為您的建議**] 區段中的 [**首頁**] 頁面上的安全性&amp;合規性中心。</span><span class="sxs-lookup"><span data-stu-id="7d652-135">The widget named **Further protect shared content** appears in the **Recommended for you** section of the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="7d652-136">此 widget 出現僅當：</span><span class="sxs-lookup"><span data-stu-id="7d652-136">This widget appears only when:</span></span>
  
- <span data-ttu-id="7d652-p108">安全性中有沒有資料外洩防護原則&amp;合規性中心或 Exchange 系統管理中心。此 widget 被要幫助您快速入門 DLP 時，讓它不會出現，如果您已經有 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="7d652-p108">There are no data loss prevention policies in the Security &amp; Compliance Center or Exchange admin center. This widget is intended to help you get started with DLP, so it doesn't appear if you already have DLP policies.</span></span>
    
- <span data-ttu-id="7d652-139">包含至少一個信用卡內容已與過去 30 天內組織外部人員共用。</span><span class="sxs-lookup"><span data-stu-id="7d652-139">Content containing least one credit card has been shared with someone outside your organization in the past 30 days.</span></span>
    
<span data-ttu-id="7d652-140">請注意規則相符項目可能需要多達 48 小時可] 小工具，讓外部共用的敏感資訊偵測到程式碼之後，可能需要最多兩天的顯示的建議。</span><span class="sxs-lookup"><span data-stu-id="7d652-140">Note that rule matches can take up to 48 hours to be available to the widget, so after sensitive information shared externally is detected, it may take up to two days for the recommendation to appear.</span></span>
  
<span data-ttu-id="7d652-141">最後，您使用 [] 小工具來調整預設的 DLP 原則之後，[] 小工具會消失從 [**首頁**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7d652-141">Finally, after you use the widget to refine the default DLP policy, the widget disappears from the **Home** page.</span></span> 
  

