---
title: 垃圾郵件信賴等級
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/2/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
description: 當電子郵件訊息會通過垃圾郵件篩選其指派的垃圾郵件計分。該分數會對應到個別的垃圾郵件信賴等級 (SCL) 為與 X 標頭中加上戳記。服務採取動作時取決於的 scl 垃圾郵件信賴解譯的訊息。下表來篩選和預設採取的動作是針對每個評等的內送郵件上解譯不同 SCL 評等。
ms.openlocfilehash: cd33f440828761ab8cb496d9eff07288d974514c
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026280"
---
# <a name="spam-confidence-levels"></a><span data-ttu-id="732c5-106">垃圾郵件信賴等級</span><span class="sxs-lookup"><span data-stu-id="732c5-106">Spam confidence levels</span></span>

<span data-ttu-id="732c5-p102">當電子郵件訊息會通過垃圾郵件篩選其指派的垃圾郵件計分。該分數會對應到個別的垃圾郵件信賴等級 (SCL) 為與 X 標頭中加上戳記。服務採取動作時取決於的 scl 垃圾郵件信賴解譯的訊息。下表來篩選和預設採取的動作是針對每個評等的內送郵件上解譯不同 SCL 評等。</span><span class="sxs-lookup"><span data-stu-id="732c5-p102">When an email message goes through spam filtering it is assigned a spam score. That score is mapped to an individual Spam Confidence Level (SCL) rating and stamped in an X-header. The service takes actions upon the messages depending upon the spam confidence interpretation of the SCL rating. The following table shows how the different SCL ratings are interpreted by the filters and the default action that is taken on inbound messages for each rating.</span></span>
  
|<span data-ttu-id="732c5-111">**Scl**</span><span class="sxs-lookup"><span data-stu-id="732c5-111">**SCL Rating**</span></span>|<span data-ttu-id="732c5-112">**垃圾郵件信賴解譯**</span><span class="sxs-lookup"><span data-stu-id="732c5-112">**Spam Confidence Interpretation**</span></span>|<span data-ttu-id="732c5-113">**將預設動作**</span><span class="sxs-lookup"><span data-stu-id="732c5-113">**Default Action**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="732c5-114">-1</span><span class="sxs-lookup"><span data-stu-id="732c5-114">-1</span></span>  <br/> |<span data-ttu-id="732c5-115">非垃圾郵件來自 [安全的寄件者、 安全的收件者或安全列出 IP 位址 （信任的合作夥伴）</span><span class="sxs-lookup"><span data-stu-id="732c5-115">Non-spam coming from a safe sender, safe recipient, or safe listed IP address (trusted partner)</span></span>  <br/> |<span data-ttu-id="732c5-116">將郵件傳遞至收件者的收件匣。</span><span class="sxs-lookup"><span data-stu-id="732c5-116">Deliver the message to the recipients' inbox.</span></span>  <br/> |
|<span data-ttu-id="732c5-117">0、 1</span><span class="sxs-lookup"><span data-stu-id="732c5-117">0, 1</span></span>  <br/> |<span data-ttu-id="732c5-118">非垃圾郵件因為已掃描郵件，並決定要全新</span><span class="sxs-lookup"><span data-stu-id="732c5-118">Non-spam because the message was scanned and determined to be clean</span></span>  <br/> |<span data-ttu-id="732c5-119">將郵件傳遞至收件者的收件匣。</span><span class="sxs-lookup"><span data-stu-id="732c5-119">Deliver the message to the recipients' inbox.</span></span>  <br/> |
|<span data-ttu-id="732c5-120">5、 6</span><span class="sxs-lookup"><span data-stu-id="732c5-120">5, 6</span></span>  <br/> | <span data-ttu-id="732c5-121">垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="732c5-121">Spam</span></span>  <br/> |<span data-ttu-id="732c5-122">將郵件傳遞至收件者的垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="732c5-122">Deliver the message to the recipients' Junk Email folder.</span></span>  <br/> |
|<span data-ttu-id="732c5-123">7，8 9</span><span class="sxs-lookup"><span data-stu-id="732c5-123">7, 8, 9</span></span>  <br/> |<span data-ttu-id="732c5-124">高度信賴垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="732c5-124">High confidence spam</span></span>  <br/> |<span data-ttu-id="732c5-125">將郵件傳遞至收件者的垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="732c5-125">Deliver the message to the recipients' Junk Email folder.</span></span>  <br/> |
   
> [!TIP]
> <span data-ttu-id="732c5-p103">服務未設定 SCL 評等的 2、 3、 4、 7 和 8。5 或 6 的 scl 會被視為可疑的垃圾郵件，這是某些較不是比 scl 為 9、 會視為某些垃圾郵件的垃圾郵件。垃圾郵件和高信賴垃圾郵件的不同動作可以透過您在 Exchange 系統管理中心中的內容篩選原則設定。如需詳細資訊，請參閱[設定垃圾郵件篩選器原則](configure-your-spam-filter-policies.md)。您也可以設定與特定條件相符使用傳輸規則[使用郵件流程規則將郵件中的垃圾郵件信賴等級 (SCL)](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)中所述的郵件的 scl。如果您使用的傳輸規則來設定 SCL 7、 8 或 9 的訊息會視為高信賴垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="732c5-p103">SCL ratings of 2, 3, 4, 7, and 8 are not set by the service. An SCL rating of 5 or 6 is considered suspected spam, which is less certain to be spam than an SCL rating of 9, which is considered certain spam. Different actions for spam and high confidence spam can be configured via your content filter policies in the Exchange admin center. For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md). You can also set the SCL rating for messages that match specific conditions by using Transport rules, as described in [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md). If you use a transport rule to set SCL of 7, 8, or 9 the message will be treated as high confidence spam.</span></span> 
  
||
|:-----|
|<span data-ttu-id="732c5-p104">![LinkedIn Learning 的短圖示](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **初次使用 Office 365？**         探索 LinkedIn Learning 提供的 **Office 365 admins and IT pros** 免費影片課程。</span><span class="sxs-lookup"><span data-stu-id="732c5-p104">![The short icon for LinkedIn Learning](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Office 365?**         Discover free video courses for **Office 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span> |
   

