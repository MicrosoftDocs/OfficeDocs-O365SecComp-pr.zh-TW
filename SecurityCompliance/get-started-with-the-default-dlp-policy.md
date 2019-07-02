---
title: 開始使用預設的 DLP 原則
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 8/10/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e0ada764-6422-4b44-9472-513bed04837b
ms.collection:
- M365-security-compliance
description: 在您建立第一次資料遺失防護 (DLP) 原則之前, DLP 會協助使用預設原則來保護您的機密資訊。 此預設原則及其建議 (如下所示) 可在您的組織外的人員共用包含信用卡號碼的電子郵件或檔時通知您, 以協助保護您的敏感內容。
ms.openlocfilehash: a14e2c9c1f833552c11e55ec76f6f804e0311479
ms.sourcegitcommit: 0d5a863f48914eeaaf29f7d2a2022618de186247
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2019
ms.locfileid: "34077919"
---
# <a name="get-started-with-the-default-dlp-policy"></a><span data-ttu-id="9e543-104">開始使用預設的 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="9e543-104">Get started with the default DLP policy</span></span>

<span data-ttu-id="9e543-105">在您建立第一次資料遺失防護 (DLP) 原則之前, DLP 會協助使用預設原則來保護您的機密資訊。</span><span class="sxs-lookup"><span data-stu-id="9e543-105">Before you even create your first data loss prevention (DLP) policy, DLP is helping to protect your sensitive information with a default policy.</span></span> <span data-ttu-id="9e543-106">此預設原則及其建議 (如下所示) 可在您的組織外的人員共用包含信用卡號碼的電子郵件或檔時通知您, 以協助保護您的敏感內容。</span><span class="sxs-lookup"><span data-stu-id="9e543-106">This default policy and its recommendation (shown below) help keep your sensitive content secure by notifying you when email or documents containing a credit card number were shared with someone outside your organization.</span></span> <span data-ttu-id="9e543-107">您會在安全性\*\*\*\* &amp;與合規性中心的首頁看到此建議。</span><span class="sxs-lookup"><span data-stu-id="9e543-107">You'll see this recommendation on the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="9e543-108">您可以使用此小工具快速查看共用的機密資訊的時間和數量, 然後只需按一次或兩次, 以精煉預設的 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="9e543-108">You can use this widget to quickly view when and how much sensitive information was shared, and then refine the default DLP policy in just a click or two.</span></span> <span data-ttu-id="9e543-109">您也可以隨時編輯預設的 DLP 原則, 因為它是完全可自訂的。</span><span class="sxs-lookup"><span data-stu-id="9e543-109">You can also edit the default DLP policy at any time because it's fully customizable.</span></span> <span data-ttu-id="9e543-110">請注意, 如果您先看不到建議, 請嘗試在 [**建議的**位置] 區段的底部再按一下 [ **+** ]。</span><span class="sxs-lookup"><span data-stu-id="9e543-110">Note that if you don't see the recommendation at first, try clicking **+More** at the bottom of the **Recommended for you** section.</span></span> 
  
![已命名的小工具會進一步保護共用內容](media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a><span data-ttu-id="9e543-112">查看報表並精煉預設的 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="9e543-112">View the report and refine the default DLP policy</span></span>

<span data-ttu-id="9e543-113">當 widget 顯示使用者與組織外部人員共用敏感資訊時, 請選擇 [**精簡 DLP 原則**] 底部。</span><span class="sxs-lookup"><span data-stu-id="9e543-113">When the widget shows you that users have shared sensitive information with people outside your organization, choose **Refine DLP policy** at the bottom.</span></span> 
  
<span data-ttu-id="9e543-114">詳細報告顯示在過去30天內共用包含信用卡號碼的內容的時間和數量。</span><span class="sxs-lookup"><span data-stu-id="9e543-114">The detailed report shows you when and how much content containing credit card numbers was shared in the past 30 days.</span></span> <span data-ttu-id="9e543-115">請注意, 規則相符可能需要最多48小時才能顯示在 widget 中。</span><span class="sxs-lookup"><span data-stu-id="9e543-115">Note that rule matches can take up to 48 hours to show up in the widget.</span></span>
  
<span data-ttu-id="9e543-116">為了協助保護機密資訊, 預設的 DLP 原則:</span><span class="sxs-lookup"><span data-stu-id="9e543-116">To help protect the sensitive information, the default DLP policy:</span></span>
  
- <span data-ttu-id="9e543-117">在 Exchange、SharePoint 和 OneDrive 中包含至少一張信用卡號碼的內容與組織外部人員共用時, 會偵測到此內容。</span><span class="sxs-lookup"><span data-stu-id="9e543-117">Detects when content in Exchange, SharePoint, and OneDrive that contains at least one credit card number is shared with people outside your organization.</span></span>
    
- <span data-ttu-id="9e543-118">顯示原則提示, 並在使用者嘗試與組織外部的人員共用此機密資訊時, 將電子郵件通知傳送給使用者。</span><span class="sxs-lookup"><span data-stu-id="9e543-118">Shows a policy tip and sends an email notification to users when they attempt to share this sensitive information with people outside your organization.</span></span> <span data-ttu-id="9e543-119">如需這些選項的詳細資訊, 請參閱[傳送電子郵件通知及顯示 DLP 原則的原則提示](use-notifications-and-policy-tips.md)。</span><span class="sxs-lookup"><span data-stu-id="9e543-119">For more information on these options, see [Send email notifications and show policy tips for DLP policies](use-notifications-and-policy-tips.md).</span></span>
    
- <span data-ttu-id="9e543-120">產生詳細的活動報告, 讓您可以追蹤與組織外的人員共用內容的人員, 以及他們的情況。</span><span class="sxs-lookup"><span data-stu-id="9e543-120">Generates detailed activity reports so that you can track things like who shared the content with people outside your organization and when they did it.</span></span> <span data-ttu-id="9e543-121">您可以使用[DLP 報告](view-the-dlp-reports.md)和[審核記錄資料](search-the-audit-log-in-security-and-compliance.md)(其中**活動** = **DLP**) 來查看此資訊。</span><span class="sxs-lookup"><span data-stu-id="9e543-121">You can use the [DLP reports](view-the-dlp-reports.md) and [audit log data](search-the-audit-log-in-security-and-compliance.md) (where **Activity** = **DLP**) to see this information.</span></span>
    
<span data-ttu-id="9e543-122">若要快速精煉預設的 DLP 原則, 您可以選擇讓它擁有:</span><span class="sxs-lookup"><span data-stu-id="9e543-122">To quickly refine the default DLP policy, you can choose to have it:</span></span>
  
- <span data-ttu-id="9e543-123">當使用者與組織外部人員共用此機密資訊時, 傳送您的附隨報告電子郵件。</span><span class="sxs-lookup"><span data-stu-id="9e543-123">Send you an incident report email when users share this sensitive information with people outside your organization.</span></span>
    
- <span data-ttu-id="9e543-124">將其他使用者新增至電子郵件附隨報告。</span><span class="sxs-lookup"><span data-stu-id="9e543-124">Add other users to the email incident report.</span></span>
    
- <span data-ttu-id="9e543-125">封鎖對包含機密資訊的內容的存取, 但允許使用者在需要時覆寫及共用或傳送。</span><span class="sxs-lookup"><span data-stu-id="9e543-125">Block access to the content containing the sensitive information, but allow the user to override and share or send if they need to.</span></span>
    
<span data-ttu-id="9e543-126">如需有關附隨報告或限制存取的詳細資訊, 請參閱[資料遺失防護原則的總覽](data-loss-prevention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="9e543-126">For more information on incident reports or restricting access, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
<span data-ttu-id="9e543-127">如果您想要稍後變更這些選項, 您可以隨時編輯預設的 DLP 原則-請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="9e543-127">If you want to change these options later, you can edit the default DLP policy at any time - see the next section.</span></span>
  
![名為進一步保護共用內容的小工具設定](media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a><span data-ttu-id="9e543-129">編輯預設的 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="9e543-129">Edit the default DLP policy</span></span>

<span data-ttu-id="9e543-130">此原則命名為**預設的 Office 365 DLP 原則**, 並顯示在&amp;安全性與合規性中心的 [**原則**] 頁面的 [**資料遺失防護**] 底下。</span><span class="sxs-lookup"><span data-stu-id="9e543-130">This policy is named **Default Office 365 DLP policy** and appears under **Data loss prevention** on the **Policy** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="9e543-131">此原則可完全自訂, 與您從頭開始建立的任何 DLP 原則相同。</span><span class="sxs-lookup"><span data-stu-id="9e543-131">This policy is fully customizable, the same as any DLP policy that you create yourself from scratch.</span></span> <span data-ttu-id="9e543-132">您也可以關閉或刪除原則, 如此一來, 您的使用者就不會再收到原則提示或電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="9e543-132">You can also turn off or delete the policy, so that your users no longer receive policy tips or email notifications.</span></span>
  
![名為「預設 Office 365 DLP 原則」的 DLP 原則](media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a><span data-ttu-id="9e543-134">當構件有且未出現時</span><span class="sxs-lookup"><span data-stu-id="9e543-134">When the widget does and does not appear</span></span>

<span data-ttu-id="9e543-135">&amp; [安全性規範中心] 首頁的 [**建議使用**] 區段中會顯示名\*\*\*\* 為 [**進一步保護共用內容**] 的小工具。</span><span class="sxs-lookup"><span data-stu-id="9e543-135">The widget named **Further protect shared content** appears in the **Recommended for you** section of the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="9e543-136">只有在下列情況時才會顯示此小工具:</span><span class="sxs-lookup"><span data-stu-id="9e543-136">This widget appears only when:</span></span>
  
- <span data-ttu-id="9e543-137">安全性&amp;合規性中心或 Exchange 系統管理中心沒有資料遺失防護原則。</span><span class="sxs-lookup"><span data-stu-id="9e543-137">There are no data loss prevention policies in the Security &amp; Compliance Center or Exchange admin center.</span></span> <span data-ttu-id="9e543-138">這個小工具是用來協助您開始使用 DLP, 因此如果您已經擁有 DLP 原則, 就不會顯示。</span><span class="sxs-lookup"><span data-stu-id="9e543-138">This widget is intended to help you get started with DLP, so it doesn't appear if you already have DLP policies.</span></span>
    
- <span data-ttu-id="9e543-139">在過去30天內, 包含至少一張信用卡的內容已與組織外部的人員共用。</span><span class="sxs-lookup"><span data-stu-id="9e543-139">Content containing least one credit card has been shared with someone outside your organization in the past 30 days.</span></span>
    
<span data-ttu-id="9e543-140">請注意, 規則比對最多可能需要48小時才能供 widget 使用, 因此在偵測到外部共用敏感資訊後, 可能需要最多兩天的時間, 才會出現建議。</span><span class="sxs-lookup"><span data-stu-id="9e543-140">Note that rule matches can take up to 48 hours to be available to the widget, so after sensitive information shared externally is detected, it may take up to two days for the recommendation to appear.</span></span>
  
<span data-ttu-id="9e543-141">最後, 在您使用 widget 來精煉預設的 DLP 原則之後, 該小工具就會從**首頁**消失。</span><span class="sxs-lookup"><span data-stu-id="9e543-141">Finally, after you use the widget to refine the default DLP policy, the widget disappears from the **Home** page.</span></span> 
  

