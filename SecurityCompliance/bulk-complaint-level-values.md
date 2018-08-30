---
title: 大量抱怨層級值
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 3/5/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
description: 大量此刻會傳送模式、 內容建立和清單取得作法而有所不同。有些是很好的大量此刻傳送想要其訂閱者的相關內容的郵件。這些訊息產生一些客訴由收件者。其他大量此刻來路不明的傳送訊息密切類似垃圾郵件和收件者從產生許多客訴。為了區別這些類型的大量此刻，來自大量此刻郵件指派給大量抱怨層級 (BCL) 評等。產生客訴是 BCL 評等介於 1 到 9 根據方式可能大量郵件處理程式而定。具有分級 BCL 9 的寄件者是 BCL 3 的分級則是可能性來產生許多客訴可能產生許多客訴從收件者]。Microsoft 識別大宗郵件，並決定適當的 BCL 使用內部及協力廠商的來源。此評等會公開在 X-Microsoft 反垃圾郵件標頭中的每封郵件。如需此郵件標頭的詳細資訊，請參閱反垃圾郵件郵件標頭。
ms.openlocfilehash: c4100b0d289398d9333369071c9886309f2abcb4
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/21/2018
ms.locfileid: "23003052"
---
# <a name="bulk-complaint-level-values"></a><span data-ttu-id="9a93e-112">大量抱怨層級值</span><span class="sxs-lookup"><span data-stu-id="9a93e-112">Bulk Complaint Level values</span></span>

<span data-ttu-id="9a93e-p102">大量此刻會傳送模式、 內容建立和清單取得作法而有所不同。有些是很好的大量此刻傳送想要其訂閱者的相關內容的郵件。這些訊息產生一些客訴由收件者。其他大量此刻來路不明的傳送訊息密切類似垃圾郵件和收件者從產生許多客訴。為了區別這些類型的大量此刻，來自大量此刻郵件指派給大量抱怨層級 (BCL) 評等。產生客訴是 BCL 評等介於 1 到 9 根據方式可能大量郵件處理程式而定。具有分級 BCL 9 的寄件者是 BCL 3 的分級則是可能性來產生許多客訴可能產生許多客訴從收件者]。Microsoft 識別大宗郵件，並決定適當的 BCL 使用內部及協力廠商的來源。此評等會公開在**X-Microsoft 反垃圾郵件**標頭中的每封郵件。如需此郵件標頭的詳細資訊，請參閱[反垃圾郵件郵件標頭](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="9a93e-p102">Bulk mailers vary in their sending patterns, content creation, and list acquisition practices. Some are good bulk mailers that send wanted messages with relevant content to their subscribers. These messages generate few complaints from recipients. Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients. To distinguish these types of bulk mailers, messages from bulk mailers are assigned a Bulk Complaint Level (BCL) rating. BCL ratings range from 1 to 9 depending on how likely the bulk mailer is to generate complaints. A sender that has a rating of BCL 9 is likely to generate many complaints from recipients, whereas a rating of BCL 3 is unlikely to generate many complaints. Microsoft uses both internal and third-party sources to identify bulk mail and determine the appropriate BCL. This rating is exposed in the **X-Microsoft-Antispam** header of every message. For more information about this message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span> 
  
<span data-ttu-id="9a93e-123">您可以使用 BCL 值來設定所需的層級大量篩選您的組織需要遵循[設定垃圾郵件篩選器原則](configure-your-spam-filter-policies.md)中的步驟。</span><span class="sxs-lookup"><span data-stu-id="9a93e-123">You can use BCL values to set the desired level of bulk filtering your organization requires by following the steps in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
  
<span data-ttu-id="9a93e-p103">更多 BCL 值新增，且會包含以下未來。下表列出並說明目前正在使用中的 BCL 值。</span><span class="sxs-lookup"><span data-stu-id="9a93e-p103">More BCL values are being added and will be included here in the future. The following table lists and describes the BCL values that are currently in use.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="9a93e-126">**BCL 值**</span><span class="sxs-lookup"><span data-stu-id="9a93e-126">**BCL Value**</span></span> <br/> |<span data-ttu-id="9a93e-127">**描述**</span><span class="sxs-lookup"><span data-stu-id="9a93e-127">**Description**</span></span> <br/> |
|<span data-ttu-id="9a93e-128">0</span><span class="sxs-lookup"><span data-stu-id="9a93e-128">0</span></span>  <br/> |<span data-ttu-id="9a93e-129">郵件不是從大量寄件者。</span><span class="sxs-lookup"><span data-stu-id="9a93e-129">The message isn't from a bulk sender.</span></span>  <br/> |
|<span data-ttu-id="9a93e-130">1，2 3</span><span class="sxs-lookup"><span data-stu-id="9a93e-130">1, 2, 3</span></span>  <br/> |<span data-ttu-id="9a93e-131">郵件是從產生一些客訴大量寄件者。</span><span class="sxs-lookup"><span data-stu-id="9a93e-131">The message is from a bulk sender that generates few complaints.</span></span>  <br/> |
|<span data-ttu-id="9a93e-132">4、 5、 6、 7</span><span class="sxs-lookup"><span data-stu-id="9a93e-132">4, 5, 6, 7</span></span>  <br/> |<span data-ttu-id="9a93e-133">郵件是來自大量寄件者所產生的抱怨混合數字。</span><span class="sxs-lookup"><span data-stu-id="9a93e-133">The message is from a bulk sender that generates a mixed number of complaints.</span></span>  <br/> |
|<span data-ttu-id="9a93e-134">8、 9</span><span class="sxs-lookup"><span data-stu-id="9a93e-134">8, 9</span></span>  <br/> |<span data-ttu-id="9a93e-135">郵件是來自大量寄件者所產生的抱怨高數量</span><span class="sxs-lookup"><span data-stu-id="9a93e-135">The message is from a bulk sender that generates a high number of complaints</span></span>  <br/> |
   

