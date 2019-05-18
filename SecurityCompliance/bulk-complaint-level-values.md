---
title: 大量抱怨層級值
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 3/5/2015
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: 大量郵件寄件者在其傳送模式、 內容建立，與清單取得作法差異。 有些是很好的大量郵件寄件者傳送原本到其訂閱者的相關內容的郵件。 這些訊息會產生一些抱怨收件者。 其他大量郵件寄件者傳送仔細看起來像垃圾郵件和收件者產生許多抱怨的來路不明的郵件。 若要區分這些類型的大量郵件寄件者，來自大量郵件寄件者的郵件會指派大量抱怨層級 (BCL) 分級。 BCL 分級介於 1 到 9 根據方式可能會大量郵件寄件者是產生抱怨。 寄件者已分級為 BCL 9 是可能會從收件者產生許多抱怨，而分級為 BCL 3 不太可能會產生許多抱怨。 Microsoft 會使用內部和協力廠商來源，以找出大量郵件，並決定適當的 BCL。 此分級會公開在 X-Microsoft 反垃圾郵件標頭中的每一封郵件。 如需有關此訊息標頭的詳細資訊，請參閱 < 反垃圾郵件郵件標頭。
ms.openlocfilehash: 490823f045e2e3fcf6b537d9717ab12abc323da6
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152125"
---
# <a name="bulk-complaint-level-values"></a><span data-ttu-id="f2769-112">大量抱怨層級值</span><span class="sxs-lookup"><span data-stu-id="f2769-112">Bulk Complaint Level values</span></span>

<span data-ttu-id="f2769-113">大量郵件寄件者在其傳送模式、 內容建立，與清單取得作法差異。</span><span class="sxs-lookup"><span data-stu-id="f2769-113">Bulk mailers vary in their sending patterns, content creation, and list acquisition practices.</span></span> <span data-ttu-id="f2769-114">有些是很好的大量郵件寄件者傳送原本到其訂閱者的相關內容的郵件。</span><span class="sxs-lookup"><span data-stu-id="f2769-114">Some are good bulk mailers that send wanted messages with relevant content to their subscribers.</span></span> <span data-ttu-id="f2769-115">這些訊息會產生一些抱怨收件者。</span><span class="sxs-lookup"><span data-stu-id="f2769-115">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="f2769-116">其他大量郵件寄件者傳送仔細看起來像垃圾郵件和收件者產生許多抱怨的來路不明的郵件。</span><span class="sxs-lookup"><span data-stu-id="f2769-116">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="f2769-117">若要區分這些類型的大量郵件寄件者，來自大量郵件寄件者的郵件會指派大量抱怨層級 (BCL) 分級。</span><span class="sxs-lookup"><span data-stu-id="f2769-117">To distinguish these types of bulk mailers, messages from bulk mailers are assigned a Bulk Complaint Level (BCL) rating.</span></span> <span data-ttu-id="f2769-118">BCL 分級介於 1 到 9 根據方式可能會大量郵件寄件者是產生抱怨。</span><span class="sxs-lookup"><span data-stu-id="f2769-118">BCL ratings range from 1 to 9 depending on how likely the bulk mailer is to generate complaints.</span></span> <span data-ttu-id="f2769-119">寄件者已分級為 BCL 9 是可能會從收件者產生許多抱怨，而分級為 BCL 3 不太可能會產生許多抱怨。</span><span class="sxs-lookup"><span data-stu-id="f2769-119">A sender that has a rating of BCL 9 is likely to generate many complaints from recipients, whereas a rating of BCL 3 is unlikely to generate many complaints.</span></span> <span data-ttu-id="f2769-120">Microsoft 會使用內部和協力廠商來源，以找出大量郵件，並決定適當的 BCL。</span><span class="sxs-lookup"><span data-stu-id="f2769-120">Microsoft uses both internal and third-party sources to identify bulk mail and determine the appropriate BCL.</span></span> <span data-ttu-id="f2769-121">此分級會公開在**X-Microsoft 反垃圾郵件**標頭中的每一封郵件。</span><span class="sxs-lookup"><span data-stu-id="f2769-121">This rating is exposed in the **X-Microsoft-Antispam** header of every message.</span></span> <span data-ttu-id="f2769-122">如需有關此訊息標頭的詳細資訊，請參閱 <<c0>反垃圾郵件郵件標頭。</span><span class="sxs-lookup"><span data-stu-id="f2769-122">For more information about this message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span> 
  
<span data-ttu-id="f2769-123">您可以使用 BCL 值來設定所需的層級，大量篩選您的組織需要遵循的步驟中[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="f2769-123">You can use BCL values to set the desired level of bulk filtering your organization requires by following the steps in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
  
<span data-ttu-id="f2769-124">多個 BCL 值新增，並將會包含以下在未來。</span><span class="sxs-lookup"><span data-stu-id="f2769-124">More BCL values are being added and will be included here in the future.</span></span> <span data-ttu-id="f2769-125">下表列出並說明目前正在使用中的 BCL 值。</span><span class="sxs-lookup"><span data-stu-id="f2769-125">The following table lists and describes the BCL values that are currently in use.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f2769-126">**BCL 值**</span><span class="sxs-lookup"><span data-stu-id="f2769-126">**BCL Value**</span></span> <br/> |<span data-ttu-id="f2769-127">**描述**</span><span class="sxs-lookup"><span data-stu-id="f2769-127">**Description**</span></span> <br/> |
|<span data-ttu-id="f2769-128">0</span><span class="sxs-lookup"><span data-stu-id="f2769-128">0</span></span>  <br/> |<span data-ttu-id="f2769-129">郵件不是來自大量寄件者。</span><span class="sxs-lookup"><span data-stu-id="f2769-129">The message isn't from a bulk sender.</span></span>  <br/> |
|<span data-ttu-id="f2769-130">1、 2、 3</span><span class="sxs-lookup"><span data-stu-id="f2769-130">1, 2, 3</span></span>  <br/> |<span data-ttu-id="f2769-131">郵件是來自會產生一些抱怨大量寄件者。</span><span class="sxs-lookup"><span data-stu-id="f2769-131">The message is from a bulk sender that generates few complaints.</span></span>  <br/> |
|<span data-ttu-id="f2769-132">4、 5、 6、 7</span><span class="sxs-lookup"><span data-stu-id="f2769-132">4, 5, 6, 7</span></span>  <br/> |<span data-ttu-id="f2769-133">郵件是來自大量寄件者所產生的抱怨混合數字。</span><span class="sxs-lookup"><span data-stu-id="f2769-133">The message is from a bulk sender that generates a mixed number of complaints.</span></span>  <br/> |
|<span data-ttu-id="f2769-134">8, 9</span><span class="sxs-lookup"><span data-stu-id="f2769-134">8, 9</span></span>  <br/> |<span data-ttu-id="f2769-135">郵件是來自會產生大量抱怨的大量寄件者</span><span class="sxs-lookup"><span data-stu-id="f2769-135">The message is from a bulk sender that generates a high number of complaints</span></span>  <br/> |
   

