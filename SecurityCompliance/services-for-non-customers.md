---
title: 服務的非客戶傳送郵件到 Office 365
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 5/2/2016
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 19fd3e0f-8dbf-4049-a810-2c8ee6cefd48
ms.collection:
- M365-security-compliance
description: 若要協助維護使用者的電子郵件使用中的信任，Microsoft 已放置就地各種不同的原則和技術，以協助保護我們的使用者。
ms.openlocfilehash: 868f5491ae9433e115090567b40abcd39ef2ebf8
ms.sourcegitcommit: 5eb664b6ecef94aef4018a75684ee4ae66c486bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/08/2019
ms.locfileid: "30492792"
---
# <a name="services-for-non-customers-sending-mail-to-office-365"></a><span data-ttu-id="b45c2-103">服務的非客戶傳送郵件到 Office 365</span><span class="sxs-lookup"><span data-stu-id="b45c2-103">Services for non-customers sending mail to Office 365</span></span>
  
<span data-ttu-id="b45c2-104">電子郵件濫用、 垃圾郵件和詐騙電子郵件 （網路釣魚） 繼續 burden 整個電子郵件生態系統。</span><span class="sxs-lookup"><span data-stu-id="b45c2-104">Email abuse, junk email, and fraudulent emails (phishing) continue to burden the entire email ecosystem.</span></span> <span data-ttu-id="b45c2-105">若要協助維護使用者的電子郵件使用中的信任，Microsoft 已放置就地各種不同的原則和技術，以協助保護我們的使用者。</span><span class="sxs-lookup"><span data-stu-id="b45c2-105">To help maintain user trust in the use of email, Microsoft has put in place various policies and technologies to help protect our users.</span></span> <span data-ttu-id="b45c2-106">不過，Microsoft 了解合法電子郵件不應該造成負面的影響。</span><span class="sxs-lookup"><span data-stu-id="b45c2-106">However, Microsoft understands that legitimate email should not be negatively affected.</span></span> <span data-ttu-id="b45c2-107">因此，我們已建立服務，以協助改善其能夠傳遞電子郵件給 Office 365 使用者藉由主動管理其傳送信譽寄件者的套件。</span><span class="sxs-lookup"><span data-stu-id="b45c2-107">Therefore, we have established a suite of services to help senders improve their ability to deliver email to Office 365 users by proactively managing their sending reputation.</span></span>
  
<span data-ttu-id="b45c2-108">本概觀提供即使您不是 Office 365 客戶，我們提供給您的組織優點的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="b45c2-108">This overview provides information about benefits we provide to your organization even if you aren't an Office 365 customer.</span></span>
  
## <a name="sender-solutions"></a><span data-ttu-id="b45c2-109">寄件者的解決方案</span><span class="sxs-lookup"><span data-stu-id="b45c2-109">Sender solutions</span></span>
<span data-ttu-id="b45c2-110"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="b45c2-110"></span></span>

|<span data-ttu-id="b45c2-111">**服務**</span><span class="sxs-lookup"><span data-stu-id="b45c2-111">**Service**</span></span>|<span data-ttu-id="b45c2-112">**效益**</span><span class="sxs-lookup"><span data-stu-id="b45c2-112">**Benefits**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b45c2-113">此線上說明內容</span><span class="sxs-lookup"><span data-stu-id="b45c2-113">This online help content</span></span>  <br/> | <span data-ttu-id="b45c2-114">提供：</span><span class="sxs-lookup"><span data-stu-id="b45c2-114">Provides:</span></span>  <br/>  <span data-ttu-id="b45c2-115">傳遞至 EOP 使用者的通訊與相關的任何問題起點</span><span class="sxs-lookup"><span data-stu-id="b45c2-115">A starting point for any questions related to delivering communications to EOP users</span></span>  <br/>  <span data-ttu-id="b45c2-116">包含簡單的線上指南與我們的原則和需求</span><span class="sxs-lookup"><span data-stu-id="b45c2-116">Includes a simple online guide with our policies and requirements</span></span>  <br/>  <span data-ttu-id="b45c2-117">垃圾郵件篩選器與 Microsoft 所採用的驗證技術概觀</span><span class="sxs-lookup"><span data-stu-id="b45c2-117">An overview of the junk email filters and authentication technologies employed by Microsoft</span></span>  <br/> |
|[<span data-ttu-id="b45c2-118">Microsoft 支援</span><span class="sxs-lookup"><span data-stu-id="b45c2-118">Microsoft support</span></span>](services-for-non-customers.md#AboutSupport) <br/> |<span data-ttu-id="b45c2-119">提供自助和呈報支援傳遞問題。</span><span class="sxs-lookup"><span data-stu-id="b45c2-119">Provides self-help and escalation support for delivery issues.</span></span>  <br/> |
|[<span data-ttu-id="b45c2-120">Office 365 反垃圾郵件 IP 取消列出入口網站</span><span class="sxs-lookup"><span data-stu-id="b45c2-120">Office 365 Anti-Spam IP Delist Portal</span></span>](services-for-non-customers.md#DelistPortal) <br/> |<span data-ttu-id="b45c2-121">一套工具來送出 IP 取消列出要求。</span><span class="sxs-lookup"><span data-stu-id="b45c2-121">A tool to submit IP delist request.</span></span> <span data-ttu-id="b45c2-122">送出這個要求之前是以確保來自 IP 有問題的任何進一步郵件不是沒有不當或惡意寄件者的責任。</span><span class="sxs-lookup"><span data-stu-id="b45c2-122">Before submitting this request it is the sender's responsibility to ensure that any further mail originating from the IP in question is not abusive or malicious.</span></span>  <br/> |
|[<span data-ttu-id="b45c2-123">濫用和垃圾郵件報告源自於 Exchange Online 的垃圾電子郵件</span><span class="sxs-lookup"><span data-stu-id="b45c2-123">Abuse and spam reporting for junk email originating from Exchange Online</span></span>](services-for-non-customers.md#ReportOurJunk) <br/> |<span data-ttu-id="b45c2-124">會不斷垃圾郵件和其他的垃圾郵件防止傳送從 Exchange Online 和雜亂網際網路和您的郵件系統。</span><span class="sxs-lookup"><span data-stu-id="b45c2-124">Keeps spam and other unwanted mail from being sent from Exchange Online and cluttering up the Internet and your mail system.</span></span>  <br/> |
   
## <a name="microsoft-support"></a><span data-ttu-id="b45c2-125">Microsoft 支援</span><span class="sxs-lookup"><span data-stu-id="b45c2-125">Microsoft support</span></span>
<span data-ttu-id="b45c2-126"><a name="AboutSupport"> </a></span><span class="sxs-lookup"><span data-stu-id="b45c2-126"></span></span>

<span data-ttu-id="b45c2-127">Microsoft 提供了數個人員無法傳送郵件到 Office 365 收件匣的支援選項。</span><span class="sxs-lookup"><span data-stu-id="b45c2-127">Microsoft offers several support options for people having trouble sending mail to Office 365 inboxes.</span></span> <span data-ttu-id="b45c2-128">我們建議您：</span><span class="sxs-lookup"><span data-stu-id="b45c2-128">We recommend that you:</span></span>
  
- <span data-ttu-id="b45c2-129">請遵循您會收到任何未傳遞回報中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="b45c2-129">Follow the instructions in any non-delivery report you receive.</span></span>
    
- <span data-ttu-id="b45c2-130">請參閱[疑難排解郵件傳送到 Office 365](troubleshooting-mail-sent-to-office-365.md)中的非客戶會遇到最常見的問題。</span><span class="sxs-lookup"><span data-stu-id="b45c2-130">Check out the most common problems that non-customers encounter in [Troubleshooting mail sent to Office 365](troubleshooting-mail-sent-to-office-365.md).</span></span>
    
- <span data-ttu-id="b45c2-131">用於[Office 365 取消列出入口網站](https://sender.office.com)將要求提交至已從封鎖寄件者清單中移除您 IP。</span><span class="sxs-lookup"><span data-stu-id="b45c2-131">Use the [Office 365 delist portal](https://sender.office.com) to submit a request to have your IP removed from the blocked sender's list.</span></span> 
    
- <span data-ttu-id="b45c2-132">閱讀[Microsoft 社群論壇](https://community.office365.com/en-us/f/)。</span><span class="sxs-lookup"><span data-stu-id="b45c2-132">Read the [Microsoft community forums](https://community.office365.com/en-us/f/).</span></span>
    
- <span data-ttu-id="b45c2-133">請連絡您嘗試使用另一種方法的電子郵件，並請他們連絡 Microsoft 支援服務，並開啟支援票證代替您 Office 365 客戶。</span><span class="sxs-lookup"><span data-stu-id="b45c2-133">Contact the Office 365 customer you're trying to email using another method and ask them to contact Microsoft Support and open a support ticket on your behalf.</span></span> <span data-ttu-id="b45c2-134">在某些情況下，基於法規因素而，Microsoft 支援服務必須彼此直接寄件者擁有遭到封鎖的 IP 空間。</span><span class="sxs-lookup"><span data-stu-id="b45c2-134">In some cases, for legal reasons, Microsoft Support must communicate directly with the sender who owns the IP space that is being blocked.</span></span> <span data-ttu-id="b45c2-135">不過，非客戶通常無法開啟支援票證。</span><span class="sxs-lookup"><span data-stu-id="b45c2-135">However, non-customers typically can't open support tickets.</span></span>
    
     <span data-ttu-id="b45c2-136">如需 Office 365 連絡 Microsoft 技術支援的詳細資訊，請參閱 <<c0>支援>。</span><span class="sxs-lookup"><span data-stu-id="b45c2-136">For more information about Microsoft Technical support for Office 365, see [Support](https://technet.microsoft.com/library/office-365-support.aspx).</span></span>
    
## <a name="office-365-anti-spam-ip-delist-portal"></a><span data-ttu-id="b45c2-137">Office 365 反垃圾郵件 IP 取消列出入口網站</span><span class="sxs-lookup"><span data-stu-id="b45c2-137">Office 365 Anti-Spam IP Delist Portal</span></span>
<span data-ttu-id="b45c2-138"><a name="DelistPortal"> </a></span><span class="sxs-lookup"><span data-stu-id="b45c2-138"></span></span>

<span data-ttu-id="b45c2-139">這是您可以使用您自己從 Office 365 封鎖寄件者清單中移除自助入口網站。</span><span class="sxs-lookup"><span data-stu-id="b45c2-139">This is a self-service portal you can use to remove yourself from the Office 365 blocked senders list.</span></span> <span data-ttu-id="b45c2-140">如果您是您收到錯誤訊息，當您嘗試傳送電子郵件給其電子郵件地址是在 Office 365 中的收件者，而您不認為您此入口網站應使用。</span><span class="sxs-lookup"><span data-stu-id="b45c2-140">Use this portal if you are you getting an error message when you try to send an email to a recipient whose email address is in Office 365 and you don't think you should be.</span></span> <span data-ttu-id="b45c2-141">如需詳細資訊，請參閱[使用取消列入入口網站，將自己從 Office 365 的已封鎖寄件者清單中移除](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)。</span><span class="sxs-lookup"><span data-stu-id="b45c2-141">For more information, see [Use the delist portal to remove yourself from the Office 365 blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>
  
## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a><span data-ttu-id="b45c2-142">濫用和垃圾郵件報告源自於 Exchange Online 的垃圾電子郵件</span><span class="sxs-lookup"><span data-stu-id="b45c2-142">Abuse and spam reporting for junk email originating from Exchange Online</span></span>
<span data-ttu-id="b45c2-143"><a name="ReportOurJunk"> </a></span><span class="sxs-lookup"><span data-stu-id="b45c2-143"></span></span>

<span data-ttu-id="b45c2-144">有時 Office 365 是由協力廠商用來傳送垃圾郵件中的我們字詞的使用與原則違規情形。</span><span class="sxs-lookup"><span data-stu-id="b45c2-144">Sometimes Office 365 is used by third parties to send junk email, in violation of our terms of use and policy.</span></span> <span data-ttu-id="b45c2-145">如果您收到任何垃圾電子郵件從 Office 365，您可以報告這些郵件到[junk@office365.microsoft.com](mailto:junk@office365.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="b45c2-145">If you receive any junk email from Office 365, you can report these messages to [junk@office365.microsoft.com](mailto:junk@office365.microsoft.com).</span></span> <span data-ttu-id="b45c2-146">請附加違規的郵件，包括完整的郵件標頭中，以 RFC 5322 或 ARF 格式。</span><span class="sxs-lookup"><span data-stu-id="b45c2-146">Please attach the offending messages, including the full message header, in RFC 5322 or ARF format.</span></span> <span data-ttu-id="b45c2-147">Outlook web 使用者可以使用回報垃圾郵件的內建工具。</span><span class="sxs-lookup"><span data-stu-id="b45c2-147">Outlook on the web users can use built-in tools to report junk email.</span></span> <span data-ttu-id="b45c2-148">如詳細資訊，請參閱[報告垃圾郵件和網路釣魚詐騙網頁型 Outlook 中](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="b45c2-148">For information, see [Report junk email and phishing scams in Outlook on the web ](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md).</span></span>
  

