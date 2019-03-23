---
title: Office 365 的反詐騙保護
ms.author: tracyp
author: MSFTtracyp
manager: laurawi
ms.date: 3/6/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
search.appverid:
- MET150
ms.assetid: d24bb387-c65d-486e-93e7-06a4f1a436c0
ms.collection:
- M365-security-compliance
- Strat_O365_IP
ms.custom: TopSMBIssues
localization_priority: Priority
description: 本文說明 Office 365 如何減少使用偽造寄件者網域的網路釣魚攻擊，即詐騙網域。 其達成目的的方式是透過分析郵件，和封鎖無法使用標準電子郵件驗證方法或其他寄件者信譽技術來進行驗證的郵件。 採用此項變更是為了減少 Office 365 中的組織所暴露的網路釣魚攻擊數量。
ms.openlocfilehash: 8b308e4b5ce651632834884c12a4500989b43bf5
ms.sourcegitcommit: f6073deec39a18581ed12abef18728417a52cdf4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/22/2019
ms.locfileid: "30747579"
---
# <a name="anti-spoofing-protection-in-office-365"></a><span data-ttu-id="c48be-105">Office 365 的反詐騙保護</span><span class="sxs-lookup"><span data-stu-id="c48be-105">Anti-spoofing protection in Office 365</span></span>

<span data-ttu-id="c48be-106">本文說明 Office 365 如何減少使用偽造寄件者網域的網路釣魚攻擊，即詐騙網域。</span><span class="sxs-lookup"><span data-stu-id="c48be-106">This article describes how Office 365 mitigates against phishing attacks that use forged sender domains, that is, domains that are spoofed.</span></span> <span data-ttu-id="c48be-107">其達成目的的方式是透過分析郵件，和封鎖無法使用標準電子郵件驗證方法或其他寄件者信譽技術來進行驗證的郵件。</span><span class="sxs-lookup"><span data-stu-id="c48be-107">It accomplishes this by analyzing the messages and blocking the ones that cannot be authenticated using standard email authentication methods, nor other sender reputation techniques.</span></span> <span data-ttu-id="c48be-108">採用此項變更是為了減少 Office 365 中的組織所暴露的網路釣魚攻擊數量。</span><span class="sxs-lookup"><span data-stu-id="c48be-108">This change was implemented to reduce the number of phishing attacks to which organizations in Office 365 are exposed.</span></span>
  
<span data-ttu-id="c48be-109">本文也會說明進行此項變更的原因、客戶如何準備進行此變更、如何查看將受影響的郵件、如何回報郵件、如何緩解誤報情況，以及 Microsoft 的寄件人應如何預備此項變更。</span><span class="sxs-lookup"><span data-stu-id="c48be-109">This article also describes why this change is being made, how customers can prepare for this change, how to view messages that will be affected, how to report on messages, how to mitigate false positives, as well as how senders to Microsoft should prepare for this change.</span></span>
  
<span data-ttu-id="c48be-110">Microsoft 的反詐騙技術最初部署在具有 Office 365 企業版 E5 訂閱，或已為其訂閱購買 Office 365 進階威脅防護 (ATP) 附加元件的組織中。</span><span class="sxs-lookup"><span data-stu-id="c48be-110">Microsoft's anti-spoofing technology was initially deployed to its organizations that had an Office 365 Enterprise E5 subscription or had purchased the Office 365 Advanced Threat Protection (ATP) add-on for their subscription.</span></span> <span data-ttu-id="c48be-111">自 2018 年 10 月起，我們會將防護擴充至擁有 Exchange Online Protection (EOP) 的組織中。</span><span class="sxs-lookup"><span data-stu-id="c48be-111">As of October, 2018 we extended the protection to organizations that have Exchange Online Protection (EOP) as well.</span></span> <span data-ttu-id="c48be-112">此外，由於我們所有的篩選器皆會相互學習，所以 Outlook.com使用者也可能會受到影響。</span><span class="sxs-lookup"><span data-stu-id="c48be-112">Additionally, because of the way all of our filters learn from each other, Outlook.com users may also be affected.</span></span>
  
## <a name="how-spoofing-is-used-in-phishing-attacks"></a><span data-ttu-id="c48be-113">網路釣魚攻擊中的詐騙方式</span><span class="sxs-lookup"><span data-stu-id="c48be-113">How spoofing is used in phishing attacks</span></span>

<span data-ttu-id="c48be-114">為保護使用者，Microsoft 嚴正看待網路釣魚攻擊。</span><span class="sxs-lookup"><span data-stu-id="c48be-114">When it comes to protecting its users, Microsoft takes the threat of phishing seriously.</span></span> <span data-ttu-id="c48be-115">垃圾郵件製造者和網路釣魚者常用的技術之一就是詐騙，也就是偽造寄件者，讓郵件看起來源自非實際來源的其他人或其他地方。</span><span class="sxs-lookup"><span data-stu-id="c48be-115">One of the techniques that spammers and phishers commonly use is spoofing, which is when the sender is forged, and a message appears to originate from someone or somewhere other than the actual source.</span></span> <span data-ttu-id="c48be-116">這是設計來取得使用者認證的網路釣魚攻擊的慣用伎倆。</span><span class="sxs-lookup"><span data-stu-id="c48be-116">This technique is often used in phishing campaigns designed to obtain user credentials.</span></span> <span data-ttu-id="c48be-117">Microsoft 的反詐騙技術會特別檢查 [寄件者:標頭]，其會顯示在像 Outlook 這類的電子郵件用戶端中。</span><span class="sxs-lookup"><span data-stu-id="c48be-117">Microsoft's Anti-spoof technology specifically examines forgery of the 'From: header' which is the one that shows up in an email client like Outlook.</span></span> <span data-ttu-id="c48be-118">當 Microsoft 高度確信 [寄件者:標頭] 遭到偽造時，它會將該郵件標識為詐騙郵件。</span><span class="sxs-lookup"><span data-stu-id="c48be-118">When Microsoft has high confidence that the From: header is spoofed, it identifies the message as a spoof.</span></span>
  
<span data-ttu-id="c48be-119">詐騙郵件對實際使用者有兩個負面影響：</span><span class="sxs-lookup"><span data-stu-id="c48be-119">Spoofing messages have two negative implications for real life users:</span></span>
  
### <a name="1-spoofed-messages-deceive-users"></a><span data-ttu-id="c48be-120">1. 詐騙郵件欺騙使用者</span><span class="sxs-lookup"><span data-stu-id="c48be-120">1. Spoofed messages deceive users</span></span>
  
<span data-ttu-id="c48be-121">首先，詐騙郵件會誘騙使用者按下連結並給予其憑證，下載惡意程式碼或回覆具有敏感內容的郵件 (後者稱為商務電子郵件入侵)。</span><span class="sxs-lookup"><span data-stu-id="c48be-121">First, a spoofed message may trick a user into clicking a link and giving up their credentials, downloading malware, or replying to a message with sensitive content (the latter of which is known as Business Email Compromise).</span></span> <span data-ttu-id="c48be-122">例如，以下是假冒寄件者為 msoutlook94@service.outlook.com 的網路釣魚郵件：</span><span class="sxs-lookup"><span data-stu-id="c48be-122">For example, the following is a phishing message with a spoofed sender of msoutlook94@service.outlook.com:</span></span>
  
![冒充 service.outlook.com 的網路釣魚郵件](media/1a441f21-8ef7-41c7-90c0-847272dc5350.jpg)
  
<span data-ttu-id="c48be-124">上述郵件並不是真正從 service.outlook.com 寄出的郵件，而是網路釣魚者所偽造的郵件。</span><span class="sxs-lookup"><span data-stu-id="c48be-124">The above did not actually come from service.outlook.com, but instead was spoofed by the phisher to make it look like it did.</span></span> <span data-ttu-id="c48be-125">這封郵件試圖誘騙使用者按下郵件內的連結。</span><span class="sxs-lookup"><span data-stu-id="c48be-125">It is attempting to trick a user into clicking the link within the message.</span></span>
  
<span data-ttu-id="c48be-126">下個範例是假冒的 contoso.com：</span><span class="sxs-lookup"><span data-stu-id="c48be-126">The next example is spoofing contoso.com:</span></span>
  
![網路釣魚郵件 - 商務電子郵件入侵](media/da15adaa-708b-4e73-8165-482fc9182090.jpg)
  
<span data-ttu-id="c48be-128">郵件看起來合法，但實際上卻是偽造的。</span><span class="sxs-lookup"><span data-stu-id="c48be-128">The message looks legitimate, but in fact is a spoof.</span></span> <span data-ttu-id="c48be-129">這封網路釣魚郵件是一種商務電子郵件入侵，也就是網路釣魚的子類別。</span><span class="sxs-lookup"><span data-stu-id="c48be-129">This phishing message is a type of Business Email Compromise which is a subcategory of phishing.</span></span>

### <a name="2-users-confuse-real-messages-for-fake-ones"></a><span data-ttu-id="c48be-130">2. 使用者無法分辨真假郵件</span><span class="sxs-lookup"><span data-stu-id="c48be-130">2. Users confuse real messages for fake ones</span></span>
  
<span data-ttu-id="c48be-131">第二，詐騙郵件會讓使用者產生不確定感，他們知道什麼是網路釣魚郵件，但卻無法分辨真實郵件和詐騙郵件之間的差異。</span><span class="sxs-lookup"><span data-stu-id="c48be-131">Second, spoofed messages create uncertainty for users who know about phishing messages but cannot tell the difference between a real message and spoofed one.</span></span> <span data-ttu-id="c48be-132">例如，下列是來自 Microsoft 安全性帳戶電子郵件地址的實際密碼重設郵件範例：</span><span class="sxs-lookup"><span data-stu-id="c48be-132">For example, the following is an example of an actual password reset from the Microsoft Security account email address:</span></span>
  
![Microsoft 合法密碼重設](media/58a3154f-e83d-4f86-bcfe-ae9e8c87bd37.jpg)
  
<span data-ttu-id="c48be-134">上述郵件確實是來自 Microsoft，但使用者仍然還是會收到誘騙使用者按下連結並給予其憑證，下載惡意程式碼或回覆具有敏感內容的網路釣魚郵件。</span><span class="sxs-lookup"><span data-stu-id="c48be-134">The above message did come from Microsoft, but at the same time, users are used to getting phishing messages that may trick a user into clicking a link and giving up their credentials, downloading malware, or replying to a message with sensitive content.</span></span> <span data-ttu-id="c48be-135">因為分辨真實密碼重設郵件與假冒郵件有其難度，許多使用者會略過這些郵件、將它們回報為垃圾郵件或在不應該的情況下，將這些郵件回報給 Microsoft 為遺漏的網路釣魚詐騙。</span><span class="sxs-lookup"><span data-stu-id="c48be-135">Because it is difficult to tell the difference between a real password reset and a fake one, many users ignore these messages, report them as spam, or unnecessarily report the messages back to Microsoft as missed phishing scams.</span></span>

<span data-ttu-id="c48be-136">為了阻止詐騙郵件，電子郵件篩選產業已開發出諸如 [SPF](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)、[DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email) 和 [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email) 等電子郵件驗證通訊協定。</span><span class="sxs-lookup"><span data-stu-id="c48be-136">To stop spoofing, the email filtering industry has developed email authentication protocols such as [SPF](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing), [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email), and [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email).</span></span> <span data-ttu-id="c48be-137">DMARC 使用通過 SPF 或 DKIM 的網域，透過檢查郵件寄件者來防止假冒 - 使用者可在其電子郵件用戶端看到郵件寄件者 (在上述範例為 service.outlook.com、outlook.com 和 accountprotection.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="c48be-137">DMARC prevents spoofing examining a message's sender - the one that the user sees in their email client (in the examples above, this is service.outlook.com, outlook.com, and accountprotection.microsoft.com) - with the domain that passed SPF or DKIM.</span></span> <span data-ttu-id="c48be-138">也就是說，使用者看到的網域已經過驗證，因此郵件非為詐騙郵件。</span><span class="sxs-lookup"><span data-stu-id="c48be-138">That is, the domain that the user sees has been authenticated and is therefore not spoofed.</span></span> <span data-ttu-id="c48be-139">如需完整討論內容，請參閱本文稍後的*了解為什麼電子郵件驗證不一定能夠阻止詐騙*一節。</span><span class="sxs-lookup"><span data-stu-id="c48be-139">For a more complete discussion, see the section "*Understanding why email authentication is not always enough to stop spoofing"*  later on in this article.</span></span>
  
<span data-ttu-id="c48be-140">不過，問題在於電子郵件驗證記錄並非強制必要的。</span><span class="sxs-lookup"><span data-stu-id="c48be-140">However, the problem is that email authentication records are optional, not required.</span></span> <span data-ttu-id="c48be-141">因此，雖然採用強式驗證原則的網域 (如 microsoft.com 和 skype.com) 可防止詐騙，但是發佈較弱的驗證原則、或甚至完全未採用任何原則的網域就成了詐騙目標。截至 2018 年 3 月，在財富雜誌前 500 大公司的網域中，只有 9% 發佈強式的電子郵件驗證原則。</span><span class="sxs-lookup"><span data-stu-id="c48be-141">Therefore, while domains with strong authentication policies like microsoft.com and skype.com are protected from spoofing, domains that publish weaker authentication policies, or no policy at all, are targets for being spoofed.As of March 2018, only 9% of domains of companies in the Fortune 500 publish strong email authentication policies.</span></span> <span data-ttu-id="c48be-142">剩下 91% 則可能受網路釣魚者的詐騙，且可能傳送郵件到使用者端來欺騙使用者，除非電子郵件篩選器使用另外的原則進行偵測：</span><span class="sxs-lookup"><span data-stu-id="c48be-142">The remaining 91% may be spoofed by a phisher, and unless the email filter detects it using another policy, may be delivered to an end user and deceive them:</span></span>
  
![財富雜誌前 500 大公司採用的 DMARC 原則](media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)
  
<span data-ttu-id="c48be-144">不在財富雜誌前 500 大中的中小型企業，有發佈強式電子郵件驗證原則的比例更少，且北美和西歐地區以外的網域具有強式電子郵件驗證原則的比例同樣很少。</span><span class="sxs-lookup"><span data-stu-id="c48be-144">The proportion of small-to-medium sized companies that are not in the Fortune 500 that publish strong email authentication policies is smaller, and smaller still for domains that are outside of North America and western Europe.</span></span>
  
<span data-ttu-id="c48be-145">這是個嚴重的問題，因為企業可能沒意識到電子郵件驗證的功用，但網路釣魚者卻瞭若指掌並利用這項缺口。</span><span class="sxs-lookup"><span data-stu-id="c48be-145">This is a big problem because while enterprises may not be aware of how email authentication works, phishers do understand and take advantage of the lack of it.</span></span>
  
<span data-ttu-id="c48be-146">如需設定 SPF、DKIM 和 DMARC 的相關資訊，請參閱本文稍後的 *Office 365 的客戶*這一節。</span><span class="sxs-lookup"><span data-stu-id="c48be-146">For information on setting up SPF, DKIM, and DMARC, see the section "*Customers of Office 365"*  later on in this document.</span></span> 
  
## <a name="stopping-spoofing-with-implicit-email-authentication"></a><span data-ttu-id="c48be-147">使用隱含的電子郵件驗證防止詐騙</span><span class="sxs-lookup"><span data-stu-id="c48be-147">Stopping spoofing with implicit email authentication</span></span>

<span data-ttu-id="c48be-148">因為網路釣魚和魚叉式網路釣魚這類問題的發生，以及強式電子郵件驗證原則的採用率有限，Microsoft 持續開發各項功能來保護客戶。</span><span class="sxs-lookup"><span data-stu-id="c48be-148">Because phishing and spear phishing is such a problem, and because of the limited adoption of strong email authentication policies, Microsoft continues to invest in capabilities to protect its customers.</span></span> <span data-ttu-id="c48be-149">因此，Microsoft 已開始採用*隱含的電子郵件驗證*，如果網域未進行驗證，Microsoft 會將它視為它已發佈電子郵件驗證記錄，並在未通過時對其進行相應處理。</span><span class="sxs-lookup"><span data-stu-id="c48be-149">Therefore, Microsoft is moving ahead with  *implicit email authentication* - if a domain doesn't authenticate, Microsoft will treat it as if it had published email authentication records and treat it accordingly if it doesn't pass.</span></span> 
  
<span data-ttu-id="c48be-150">為此，Microsoft 為一般電子郵件驗證建置了大量擴充功能，包括寄件者信譽、寄件者/收件者歷史記錄、行為分析和其他先進技術。</span><span class="sxs-lookup"><span data-stu-id="c48be-150">To accomplish this, Microsoft has built numerous extensions to regular email authentication including sender reputation, sender/recipient history, behavioral analysis, and other advanced techniques.</span></span> <span data-ttu-id="c48be-151">傳送郵件的網域若未發佈電子郵件驗證，該郵件將被標示為詐騙郵件，除非郵件包含其他能指出其合法性的訊號。</span><span class="sxs-lookup"><span data-stu-id="c48be-151">A message sent from a domain that doesn't publish email authentication will be marked as spoof unless it contains other signals to indicate that it is legitimate.</span></span>
  
<span data-ttu-id="c48be-152">如此一來，使用者就能確信他們所收到的電子郵件未遭到假冒，寄件者也能放心，沒有人會冒充他們的網域，而 Office 365 的客戶也能提供更完善的防護，如冒充防護。</span><span class="sxs-lookup"><span data-stu-id="c48be-152">By doing this, end users can have confidence that an email sent to them has not been spoofed, senders can be confident that nobody is impersonating their domain, and customers of Office 365 can offer even better protection such as Impersonation protection.</span></span>
  
<span data-ttu-id="c48be-153">若要查看 Microsoft 的一般公告，請參閱[網路釣魚的範圍第 2 部分 - Office 365 中增強的反詐騙保護](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209) (英文)。</span><span class="sxs-lookup"><span data-stu-id="c48be-153">To see Microsoft's general announcement, see [A Sea of Phish Part 2 - Enhanced Anti-spoofing in Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).</span></span>
  
## <a name="identifying-that-a-message-is-classified-as-spoofed"></a><span data-ttu-id="c48be-154">識別分類為詐騙郵件的郵件</span><span class="sxs-lookup"><span data-stu-id="c48be-154">Identifying that a message is classified as spoofed</span></span>

### <a name="composite-authentication"></a><span data-ttu-id="c48be-155">複合驗證</span><span class="sxs-lookup"><span data-stu-id="c48be-155">Composite authentication</span></span>

<span data-ttu-id="c48be-156">雖然 SPF、DKIM 和 DMARC 本身是很有幫助，但是如果郵件沒有明確驗證記錄，它們不會傳達足夠的驗證狀態。</span><span class="sxs-lookup"><span data-stu-id="c48be-156">While SPF, DKIM, and DMARC are all useful by themselves, they don't communicate enough authentication status in the event a message has no explicit authentication records.</span></span> <span data-ttu-id="c48be-157">因此，Microsoft 開發了一種演算法，將多個訊號組合成一個稱為「複合驗證」的單一值，或簡稱為 compauth。</span><span class="sxs-lookup"><span data-stu-id="c48be-157">Therefore, Microsoft has developed an algorithm that combines multiple signals into a single value called Composite Authentication, or compauth for short.</span></span> <span data-ttu-id="c48be-158">系統會在 Office 365 客戶的郵件標頭的 *Authentication-Results* 標頭中，註記 compauth 值。</span><span class="sxs-lookup"><span data-stu-id="c48be-158">Customers in Office 365 have compauth values stamped into the *Authentication-Results* header in the message headers.</span></span> 
  
```
Authentication-Results:
  compauth=<fail|pass|softpass|none> reason=<yyy>

```

|<span data-ttu-id="c48be-159">**CompAuth 結果**</span><span class="sxs-lookup"><span data-stu-id="c48be-159">**CompAuth result**</span></span>|<span data-ttu-id="c48be-160">**描述**</span><span class="sxs-lookup"><span data-stu-id="c48be-160">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c48be-161">失敗</span><span class="sxs-lookup"><span data-stu-id="c48be-161">fail</span></span>|<span data-ttu-id="c48be-162">郵件未通過明確驗證 (傳送網域明確地在 DNS 中發佈記錄) 或隱含驗證 (傳送網域未在 DNS 中發佈記錄，因此 Office 365 將結果內插為已發佈記錄)。</span><span class="sxs-lookup"><span data-stu-id="c48be-162">Message failed explicit authentication (sending domain published records explicitly in DNS) or implicit authentication (sending domain did not publish records in DNS, so Office 365 interpolated the result as if it had published records).</span></span>|
|<span data-ttu-id="c48be-163">通過</span><span class="sxs-lookup"><span data-stu-id="c48be-163">pass</span></span>|<span data-ttu-id="c48be-164">郵寄通過明確驗證 (郵件通過 DMARC 或 [Best Guess Passed DMARC](https://blogs.msdn.microsoft.com/tzink/2015/05/06/what-is-dmarc-bestguesspass-in-office-365)) 或信賴度高的隱含驗證 (傳送網域未發佈電子郵件驗證記錄，但 Office 365 具有強式後端訊號，指出郵件可能合法)。</span><span class="sxs-lookup"><span data-stu-id="c48be-164">Message passed explicit authentication (message passed DMARC, or [Best Guess Passed DMARC](https://blogs.msdn.microsoft.com/tzink/2015/05/06/what-is-dmarc-bestguesspass-in-office-365)) or implicit authentication with high confidence (sending domain does not publish email authentication records, but Office 365 has strong backend signals to indicate the message is likely legitimate).</span></span>|
|<span data-ttu-id="c48be-165">softpass</span><span class="sxs-lookup"><span data-stu-id="c48be-165">softpass</span></span>|<span data-ttu-id="c48be-166">郵件通過信賴度低到中的隱含驗證 (傳送網域未發佈電子郵件驗證，但 Office 365 具有後端訊號，指出郵件為合法，但訊號的強度較弱)。</span><span class="sxs-lookup"><span data-stu-id="c48be-166">Message passed implicit authentication with low-to-medium confidence (sending domain does not publish email authentication, but Office 365 has backend signals to indicate the message is legitimate but the strength of the signal is weaker).</span></span>|
|<span data-ttu-id="c48be-167">無</span><span class="sxs-lookup"><span data-stu-id="c48be-167">none</span></span>|<span data-ttu-id="c48be-168">郵件未進行驗證 (或有進行驗證，但不符合)，但因為寄件者信譽或其他因素而未套用複合驗證。</span><span class="sxs-lookup"><span data-stu-id="c48be-168">Message did not authenticate (or it did authenticate but did not align), but composite authentication not applied due to sender reputation or other factors.</span></span>|
   
|||
|:-----|:-----|
|<span data-ttu-id="c48be-169">**原因**</span><span class="sxs-lookup"><span data-stu-id="c48be-169">**Reason**</span></span>|<span data-ttu-id="c48be-170">**描述**</span><span class="sxs-lookup"><span data-stu-id="c48be-170">**Description**</span></span>|
|<span data-ttu-id="c48be-171">0xx</span><span class="sxs-lookup"><span data-stu-id="c48be-171">0xx</span></span>|<span data-ttu-id="c48be-172">郵件未通過複合驗證。</span><span class="sxs-lookup"><span data-stu-id="c48be-172">Message failed composite authentication.</span></span><br/><span data-ttu-id="c48be-173">**000** 表示郵件未通過 DMARC，並產生拒絕或隔離動作。</span><span class="sxs-lookup"><span data-stu-id="c48be-173">**000** means the message failed DMARC with an action of reject or quarantine.</span></span>  <br/><span data-ttu-id="c48be-174">**001** 表示郵件未通過隱含電子郵件驗證。</span><span class="sxs-lookup"><span data-stu-id="c48be-174">**001** means the message failed implicit email authentication.</span></span> <span data-ttu-id="c48be-175">這表示，傳送網域未發佈電子郵件驗證記錄，或是有發佈，但是擁有較弱的失敗原則 (SPF 非封鎖性失敗或中性，DMARC 原則為 p=none)。</span><span class="sxs-lookup"><span data-stu-id="c48be-175">This means that the sending domain did not have email authentication records published, or if they did, they had a weaker failure policy (SPF soft fail or neutral, DMARC policy of p=none).</span></span>  <br/><span data-ttu-id="c48be-176">**002** 代表組織擁有的寄件者/網域配對原則明確禁止傳送詐騙電子郵件，這項設定是由系統管理員手動設定。</span><span class="sxs-lookup"><span data-stu-id="c48be-176">**002** means the organization has a policy for the sender/domain pair that is explicitly prohibited from sending spoofed email, this setting is manually set by an administrator.</span></span>  <br/><span data-ttu-id="c48be-177">**010** 表示郵件未通過 DMARC，並產生拒絕或隔離動作，而傳送網域是組織接受的其中一個網域 (為 self-to-self 或 intra-org, spoofing 的一部分)。</span><span class="sxs-lookup"><span data-stu-id="c48be-177">**010** means the message failed DMARC with an action of reject or quarantine, and the sending domain is one of your organization's accepted-domains (this is part of self-to-self, or intra-org, spoofing).</span></span>  <br/><span data-ttu-id="c48be-178">**011** 表示郵件未通過隱含的電子郵件驗證，而傳送網域是組織接受的其中一個網域 (為自我詐騙，或稱為組織內部詐騙的一部分)。</span><span class="sxs-lookup"><span data-stu-id="c48be-178">**011** means the message failed implicit email authentication, and the sending domain is one of your organization's accepted domains (this is part of self-to-self, or intra-org, spoofing).</span></span>|
|<span data-ttu-id="c48be-179">其他所有代碼 (1xx、2xx、3xx、4xx、5xx)</span><span class="sxs-lookup"><span data-stu-id="c48be-179">All other codes (1xx, 2xx, 3xx, 4xx, 5xx)</span></span>|<span data-ttu-id="c48be-180">對應於不同內部代碼，說明為何郵件通過隱含驗證，或未進行驗證但卻未採取動作的原因。</span><span class="sxs-lookup"><span data-stu-id="c48be-180">Corresponds to various internal codes for why a message passed implicit authentication, or had no authentication but no action was applied.</span></span>|
   
<span data-ttu-id="c48be-181">透過查看郵件標頭，系統管理員甚至使用者可以判斷 Office 365如何做出寄件者可能被假冒的結論。</span><span class="sxs-lookup"><span data-stu-id="c48be-181">By looking at the headers of a message, an administrator or even an end user can determine how Office 365 arrives at the conclusion that the sender may be spoofed.</span></span>
  
### <a name="differentiating-between-different-types-of-spoofing"></a><span data-ttu-id="c48be-182">區分不同類型的詐騙</span><span class="sxs-lookup"><span data-stu-id="c48be-182">Differentiating between different types of spoofing</span></span>

<span data-ttu-id="c48be-183">Microsoft 將詐騙郵件區分為兩種類型：</span><span class="sxs-lookup"><span data-stu-id="c48be-183">Microsoft differentiates between two different types of spoofing messages:</span></span>
  
 <span data-ttu-id="c48be-184">**組織內部詐騙**</span><span class="sxs-lookup"><span data-stu-id="c48be-184">**Intra-org spoofing**</span></span>
  
<span data-ttu-id="c48be-185">也稱為自我詐騙，當寄件者地址中的網域與收件者網域相同或相符時 (當收件者網域是組織[接受的網域](https://technet.microsoft.com/zh-TW/library/jj945194%28v=exchg.150%29.aspx)之一時)，就會發生這種情況；或者，當寄件者地址中的網域是同一組織的一部分時。</span><span class="sxs-lookup"><span data-stu-id="c48be-185">Also known as self-to-self spoofing, this occurs when the domain in the From: address is the same as, or aligns with, the recipient domain (when recipient domain is one of your organization's [Accepted Domains](https://technet.microsoft.com/zh-TW/library/jj945194%28v=exchg.150%29.aspx)); or, when the domain in the From: address is part of the same organization.</span></span>
  
<span data-ttu-id="c48be-186">例如，下列寄件者和收件者來自相同網域 (contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="c48be-186">For example, the following has sender and recipient from the same domain (contoso.com).</span></span> <span data-ttu-id="c48be-187">在電子郵件地址間插入空格以防止垃圾郵件機器人從此網頁進行收集)：</span><span class="sxs-lookup"><span data-stu-id="c48be-187">Spaces are inserted into the email address to prevent spambot harvesting on this page):</span></span>
  
<span data-ttu-id="c48be-188">寄件者: sender @ contoso.com</span><span class="sxs-lookup"><span data-stu-id="c48be-188">From: sender @ contoso.com</span></span>
  
<span data-ttu-id="c48be-189">收件者: recipient @ contoso.com</span><span class="sxs-lookup"><span data-stu-id="c48be-189">To: recipient @ contoso.com</span></span>
  
<span data-ttu-id="c48be-190">下列寄件者和收件者網域與組織網域相符 (fabrikam.com)：</span><span class="sxs-lookup"><span data-stu-id="c48be-190">The following has the sender and recipient domains aligning with the organizational domain (fabrikam.com):</span></span>
  
<span data-ttu-id="c48be-191">寄件者: sender @ foo.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="c48be-191">From: sender @ foo.fabrikam.com</span></span>
  
<span data-ttu-id="c48be-192">收件者: recipient @ bar.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="c48be-192">To: recipient @ bar.fabrikam.com</span></span>
  
<span data-ttu-id="c48be-193">下列寄件者和收件者網域不同 (microsoft.com 和 bing.com)，但他們屬於同個組織 (也就是，他們同屬於組織接受的網域)：</span><span class="sxs-lookup"><span data-stu-id="c48be-193">The following sender and recipient domains are different (microsoft.com and bing.com), but they belong to the same organization (that is, both are part of the organization's Accepted Domains):</span></span>
  
<span data-ttu-id="c48be-194">寄件者: sender @ microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c48be-194">From: sender @ microsoft.com</span></span>
  
<span data-ttu-id="c48be-195">收件者: recipient @ bing.com</span><span class="sxs-lookup"><span data-stu-id="c48be-195">To: recipient @ bing.com</span></span>
  
<span data-ttu-id="c48be-196">未通過組織內部詐騙的郵件，其標頭包含下列值：</span><span class="sxs-lookup"><span data-stu-id="c48be-196">Messages that fail intra-org spoofing contain the following values in the headers:</span></span>
  
<span data-ttu-id="c48be-197">X-Forefront-Antispam-Report: ...CAT:SPM/HSPM/PHSH;...SFTY:9.11</span><span class="sxs-lookup"><span data-stu-id="c48be-197">X-Forefront-Antispam-Report: ...CAT:SPM/HSPM/PHSH;...SFTY:9.11</span></span>
  
<span data-ttu-id="c48be-198">CAT 是郵件類別，一般會註記為 SPM (垃圾郵件)，但偶而會註記為 HSPM (信賴度高的垃圾郵件) 或 PHISH (網路釣魚)，係根據郵件內發現的其他模式類型而定。</span><span class="sxs-lookup"><span data-stu-id="c48be-198">The CAT is the category of the message, and it is normally stamped as SPM (spam), but occasionally may be HSPM (high confidence spam) or PHISH (phishing) depending upon what other types of patterns occur in the message.</span></span>
  
<span data-ttu-id="c48be-199">SFTY 是郵件安全層級，第一個數字 (9) 表示郵件是網路釣魚，而點之後的第二組數字 (11) 表示其為組織內部詐騙。</span><span class="sxs-lookup"><span data-stu-id="c48be-199">The SFTY is the safety level of the message, the first digit (9) means the message is phishing, and second set of digits after the dot (11) means it is intra-org spoofing.</span></span>
  
<span data-ttu-id="c48be-200">尚未提供「複合驗證」特定的原因碼來表示組織內部詐騙，將於 2018 下半年加以註記 (時間表未定)。</span><span class="sxs-lookup"><span data-stu-id="c48be-200">There is no specific reason code for Composite Authentication for intra-org spoofing, that will be stamped later in 2018 (timeline not yet defined).</span></span>
  
 <span data-ttu-id="c48be-201">**跨網域詐騙**</span><span class="sxs-lookup"><span data-stu-id="c48be-201">**Cross-domain spoofing**</span></span>
  
<span data-ttu-id="c48be-202">當收件者地址中的傳送網域是接收組織的外部網域時，就會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="c48be-202">This occurs when the sending domain in the From: address is an external domain to the receiving organization.</span></span> <span data-ttu-id="c48be-203">因為跨網域詐騙在標頭會包含下列值，因此郵件未通過複合驗證：</span><span class="sxs-lookup"><span data-stu-id="c48be-203">Messages that fail Composite Authentication due to cross-domain spoofing contain the following values in the headers:</span></span>
  
<span data-ttu-id="c48be-204">Authentication-Results: …</span><span class="sxs-lookup"><span data-stu-id="c48be-204">Authentication-Results: …</span></span> <span data-ttu-id="c48be-205">compauth=fail reason=000/001</span><span class="sxs-lookup"><span data-stu-id="c48be-205">compauth=fail reason=000/001</span></span>
  
<span data-ttu-id="c48be-206">X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.22</span><span class="sxs-lookup"><span data-stu-id="c48be-206">X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.22</span></span>
  
<span data-ttu-id="c48be-207">在這兩種情況下，郵件中會註記下列紅色安全提示，或依照收件者信箱語言自訂的相同提示：</span><span class="sxs-lookup"><span data-stu-id="c48be-207">In both cases, the following red safety tip is stamped in the message, or an equivalent that is customized to the recipient mailbox's language:</span></span>
  
![紅色安全提示 - 詐騙偵測](media/a366156a-14e8-4c14-bfe5-2031b21936f8.jpg)
  
<span data-ttu-id="c48be-209">透過查看收件者地址並了解收件者電子郵件的內容，或者透過檢查電子郵件標頭，您才能分辨內部組織詐騙和跨網域詐騙。</span><span class="sxs-lookup"><span data-stu-id="c48be-209">It's only by looking at the From: address and knowing what your recipient email is, or by inspecting the email headers, that you can differentiate between intra-org and cross-domain spoofing.</span></span>
  
## <a name="how-customers-of-office-365-can-prepare-themselves-for-the-new-anti-spoofing-protection"></a><span data-ttu-id="c48be-210">Office 365 客戶如何預備自己，以採用全新的反詐騙防護</span><span class="sxs-lookup"><span data-stu-id="c48be-210">How customers of Office 365 can prepare themselves for the new anti-spoofing protection</span></span>

### <a name="information-for-administrators"></a><span data-ttu-id="c48be-211">適用於系統管理員的資訊</span><span class="sxs-lookup"><span data-stu-id="c48be-211">Information for administrators</span></span>

<span data-ttu-id="c48be-212">身為 Office 365 組織的系統管理員，您應該留意一些重要資訊。</span><span class="sxs-lookup"><span data-stu-id="c48be-212">As an administrator of an organization in Office 365, there are several key pieces of information you should be aware of.</span></span>
  
### <a name="understanding-why-email-authentication-is-not-always-enough-to-stop-spoofing"></a><span data-ttu-id="c48be-213">了解為什麼電子郵件驗證不一定能夠阻止詐騙</span><span class="sxs-lookup"><span data-stu-id="c48be-213">Understanding why email authentication is not always enough to stop spoofing</span></span>

<span data-ttu-id="c48be-214">新的反詐騙防護依賴電子郵件驗證 (SPF、DKIM 和 DMARC) 不要將郵件標示為詐騙郵件。</span><span class="sxs-lookup"><span data-stu-id="c48be-214">The new anti-spoofing protection relies on email authentication (SPF, DKIM, and DMARC) to not mark a message as spoofing.</span></span> <span data-ttu-id="c48be-215">常見的範例是，傳送網域永不發佈 SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="c48be-215">A common example is when a sending domain has never published SPF records.</span></span> <span data-ttu-id="c48be-216">如果沒有 SPF 記錄，或未正確設定 SPF 記錄，已傳送的郵件會被標示為詐騙郵件，除非 Microsoft 的後端情報指出該郵件為合法。</span><span class="sxs-lookup"><span data-stu-id="c48be-216">If there are no SPF records or they are incorrectly set up, a sent message will be marked as spoofed unless Microsoft has back-end intelligence that says the message is legitimate.</span></span>
  
<span data-ttu-id="c48be-217">例如，在部署反詐騙功能之前，郵件可能看起來會像下面一樣，沒有 SPF 記錄、沒有 DKIM 記錄，也沒有 DMARC記錄：</span><span class="sxs-lookup"><span data-stu-id="c48be-217">For example, prior to anti-spoofing being deployed, a message may have looked like the following with no SPF record, no DKIM record, and no DMARC record:</span></span> 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```
<span data-ttu-id="c48be-218">部署反詐騙功能之後，如果您有 Office 365 企業版 E5、EOP 或 ATP，則會加註 compauth 值：</span><span class="sxs-lookup"><span data-stu-id="c48be-218">After anti-spoofing, if you have Office 365 Enterprise E5, EOP, or ATP, the compauth value is stamped:</span></span>
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com; compauth=fail reason=001
From: sender @ example.com
To: receiver @ contoso.com

```

<span data-ttu-id="c48be-219">如果 example.com 設定了 SPF 記錄，但未設定 DKIM 記錄，郵件可能會通過複合驗證，因為通過 SPF 的網域與寄件者地址中的網域相符：</span><span class="sxs-lookup"><span data-stu-id="c48be-219">If example.com fixed this by setting up an SPF record but not a DKIM record, this would pass composite authentication because the domain that passed SPF aligned with the domain in the From: address:</span></span> 
  
```
Authentication-Results: spf=pass (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

<span data-ttu-id="c48be-220">或者，如果設定了 DKIM 記錄，但未設定 SPF 記錄，郵件還是會通過複合驗證，因為通過 DKIM-Signature 的網域與寄件者地址中的網域相符：</span><span class="sxs-lookup"><span data-stu-id="c48be-220">Or, if they set up a DKIM record but not an SPF record, this would also pass composite authentication because the domain in the DKIM-Signature that passed aligned with the domain in the From: address:</span></span> 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.example.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

<span data-ttu-id="c48be-221">不過，網路釣魚者也可能會設定 SPF 和 DKIM，並使用自己的網域來簽署郵件，但在寄件者地址中指定不同的網域。</span><span class="sxs-lookup"><span data-stu-id="c48be-221">However, a phisher may also set up SPF and DKIM and sign the message with their own domain, but specify a different domain in the From: address.</span></span> <span data-ttu-id="c48be-222">SPF 或 DKIM 都未要求網域與寄件者地址中的網域相符，因此除非 example.com 發佈了 DMARC 記錄，否則使用 DMARC 不會將郵件標示為詐騙：</span><span class="sxs-lookup"><span data-stu-id="c48be-222">Neither SPF nor DKIM requires the domain to align with the domain in the From: address, so unless example.com published DMARC records, this would not be marked as a spoof using DMARC:</span></span> 
  
```
Authentication-Results: spf=pass (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```

<span data-ttu-id="c48be-223">在電子郵件用戶端 (Outlook、網頁版 Outlook 或任何其他電子郵件用戶端) 中，只會顯示寄件者網域，不會顯示 SPF 或 DKIM 中的網域，這可能會誤導使用者認為郵件是來自 example.com，但實際上郵件來自 maliciousDomain.com。</span><span class="sxs-lookup"><span data-stu-id="c48be-223">In the email client (Outlook, Outlook on the web, or any other email client), only the From: domain is displayed, not the domain in the SPF or DKIM, and that can mislead the user into thinking the message came from example.com, but actually came from maliciousDomain.com.</span></span>
  
![郵件已通過驗證，但寄件者網域未與通過 SPF 或 DKIM 的網域相符](media/a9b5ab2a-dfd3-47c6-8ee8-e3dab2fae528.jpg)
  
<span data-ttu-id="c48be-225">為此，Office 365 要求寄件者地址中的網域與 SPF 或 DKIM 簽章中的網域相符，若未相符，則會包含某些其他內部訊號，來指出該郵件為合法郵件。</span><span class="sxs-lookup"><span data-stu-id="c48be-225">For that reason, Office 365 requires that the domain in the From: address aligns with the domain in the SPF or DKIM signature, and if it doesn't, contains some other internal signals that indicates that the message is legitimate.</span></span> <span data-ttu-id="c48be-226">否則，郵件的 compauth 會失敗。</span><span class="sxs-lookup"><span data-stu-id="c48be-226">Otherwise, the message would be a compauth fail.</span></span> 
  
```
Authentication-Results: spf=none (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: sender@contoso.com
To: someone@example.com
```

<span data-ttu-id="c48be-227">因此，Office 365 反詐騙會阻止沒有驗證的網域、阻止設定驗證，但寄件者地址中的網域不相符的網域，因為這是使用者看到的網域並會相信這就是郵件的寄件者。</span><span class="sxs-lookup"><span data-stu-id="c48be-227">Thus, Office 365 anti-spoofing protects against domains with no authentication, and against domains who set up authentication but mismatch against the domain in the From: address as that is the one that the user sees and believes is the sender of the message.</span></span> <span data-ttu-id="c48be-228">這在組織外部的網域，以及組織內的網域都是如此。</span><span class="sxs-lookup"><span data-stu-id="c48be-228">This is true both of domains external to your organization, as well as domains within your organization.</span></span>
  
<span data-ttu-id="c48be-229">因此，如果您曾經收到未通過複合驗證的郵件被標示為詐騙郵件，即使郵件已通過 SPF 和 DKIM，這是因為通過 SPF 和 DKIM 的網域與寄件者地址中的網域不相符。</span><span class="sxs-lookup"><span data-stu-id="c48be-229">Therefore, if you ever receive a message that failed composite authentication and is marked as spoofed, even though the message passed SPF and DKIM, it's because the domain that passed SPF and DKIM are not aligned with the domain in the From: address.</span></span>
  
### <a name="understanding-changes-in-how-spoofed-emails-are-treated"></a><span data-ttu-id="c48be-230">了解詐騙電子郵件處理方式的變化</span><span class="sxs-lookup"><span data-stu-id="c48be-230">Understanding changes in how spoofed emails are treated</span></span>

<span data-ttu-id="c48be-231">目前，對於 Office 365 中的所有組織 - ATP 和非 ATP - 未通過 DMARC 的郵件若套用拒絕或隔離原則，將被標示為垃圾郵件，並且通常會採取信賴度高的垃圾郵件動作，有時候則採取一般垃圾郵件動作 (取決於是否有其他垃圾郵件規則首將它識別為垃圾郵件)。</span><span class="sxs-lookup"><span data-stu-id="c48be-231">Currently, for all organizations in Office 365 - ATP and non-ATP - messages that fail DMARC with a policy of reject or quarantine are marked as spam and usually take the high confidence spam action, or sometimes the regular spam action (depending on whether other spam rules first identify it as spam).</span></span> <span data-ttu-id="c48be-232">組織內部詐騙偵測會採取一般垃圾郵件動作。</span><span class="sxs-lookup"><span data-stu-id="c48be-232">Intra-org spoof detections take the regular spam action.</span></span> <span data-ttu-id="c48be-233">不需要啟用此行為，也不能停用此行為。</span><span class="sxs-lookup"><span data-stu-id="c48be-233">This behavior does not need to be enabled, nor can it be disabled.</span></span>
  
<span data-ttu-id="c48be-234">但是，對於跨網域詐騙郵件，在此變更之前，它們會經過一般垃圾郵件、網路釣魚和惡意程式碼檢查，如果篩選器的其他部分將其標示為可疑，則會將它們分別標記為垃圾郵件、網路釣魚或惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="c48be-234">However, for cross-domain spoofing messages, before this change they would go through regular spam, phish, and malware checks and if other parts of the filter identified them as suspicious, would mark them as spam, phish, or malware respectively.</span></span> <span data-ttu-id="c48be-235">透過新的跨網域詐騙防護，在預設情況下，任何無法通過驗證的郵件都將採取 [防網路釣魚] \> [反詐騙] 原則中定義的動作。</span><span class="sxs-lookup"><span data-stu-id="c48be-235">With the new cross-domain spoofing protection, any message that can't be authenticated will, by default, take the action defined in the Anti-phishing \> Anti-spoofing policy.</span></span> <span data-ttu-id="c48be-236">如果其中一項未定義，就會將郵件移到使用者的 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="c48be-236">If one is not defined, it will be moved to a users Junk Email folder.</span></span> <span data-ttu-id="c48be-237">在某些情況下，還會在較可疑的郵件上新增紅色安全提示。</span><span class="sxs-lookup"><span data-stu-id="c48be-237">In some cases, more suspicious messages will also have the red safety tip added to the message.</span></span>
  
<span data-ttu-id="c48be-238">這可能會導致之前標示為垃圾郵件的某些郵件仍被標示為垃圾郵件，但現在還會顯示紅色安全提示；在其他情況下，之前標示為非垃圾郵件的郵件將開始被標示垃圾郵件 (CAT:SPOOF)，並新增紅色安全提示。</span><span class="sxs-lookup"><span data-stu-id="c48be-238">This may result in some messages that were previously marked as spam still getting marked as spam but will now also have a red safety tip; in other cases, messages that were previously marked as non-spam will start getting marked as spam (CAT:SPOOF) with a red safety tip added.</span></span> <span data-ttu-id="c48be-239">在其他情況下，將所有垃圾郵件和網路釣魚郵件移到隔離區的客戶現在會看到這些郵件轉到 [垃圾郵件] 資料夾 (此行為可變更，請參閱[變更您的反詐騙設定](#changing-your-anti-spoofing-settings))。</span><span class="sxs-lookup"><span data-stu-id="c48be-239">In still other cases, customers that were moving all spam and phish to the quarantine would now see them going to the Junk Mail Folder (this behavior can be changed, see [Changing your anti-spoofing settings](#changing-your-anti-spoofing-settings)).</span></span>
  
<span data-ttu-id="c48be-240">假冒郵件有多種不同的方式 (請參閱本文稍早所述的的[區分不同類型的詐騙](#differentiating-between-different-types-of-spoofing))，但是截至 2018 年 3 月，Office 365 處理這些郵件的方式尚未統一。</span><span class="sxs-lookup"><span data-stu-id="c48be-240">There are multiple different ways a message can be spoofed (see  [Differentiating between different types of spoofing](#differentiating-between-different-types-of-spoofing) earlier in this article) but as of March 2018 the way Office 365 treats these messages is not yet unified.</span></span> <span data-ttu-id="c48be-241">下表快速摘要跨網域詐騙防護這個新行為：</span><span class="sxs-lookup"><span data-stu-id="c48be-241">The following table is a quick summary, with Cross-domain spoofing protection being new behavior:</span></span> 
  
|<span data-ttu-id="c48be-242">**詐騙類型**</span><span class="sxs-lookup"><span data-stu-id="c48be-242">**Type of spoof**</span></span>|<span data-ttu-id="c48be-243">**類別**</span><span class="sxs-lookup"><span data-stu-id="c48be-243">**Category**</span></span>|<span data-ttu-id="c48be-244">**是否新增安全提示？**</span><span class="sxs-lookup"><span data-stu-id="c48be-244">**Safety tip added?**</span></span>|<span data-ttu-id="c48be-245">**適用對象**</span><span class="sxs-lookup"><span data-stu-id="c48be-245">**Applies to**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c48be-246">DMARC 失敗 (隔離或拒絕)</span><span class="sxs-lookup"><span data-stu-id="c48be-246">DMARC fail (quarantine or reject)</span></span>  <br/> |<span data-ttu-id="c48be-247">HSPM (預設)，也可以是 SPM 或 PHSH</span><span class="sxs-lookup"><span data-stu-id="c48be-247">HSPM (default), may also be SPM or PHSH</span></span>  <br/> |<span data-ttu-id="c48be-248">否 (還沒有)</span><span class="sxs-lookup"><span data-stu-id="c48be-248">No (not yet)</span></span>  <br/> |<span data-ttu-id="c48be-249">所有 Office 365 客戶，Outlook.com</span><span class="sxs-lookup"><span data-stu-id="c48be-249">All Office 365 customers, Outlook.com</span></span>  <br/> |
|<span data-ttu-id="c48be-250">自我</span><span class="sxs-lookup"><span data-stu-id="c48be-250">Self-to-self</span></span>  <br/> |<span data-ttu-id="c48be-251">SPM</span><span class="sxs-lookup"><span data-stu-id="c48be-251">SPM</span></span>  <br/> |<span data-ttu-id="c48be-252">是</span><span class="sxs-lookup"><span data-stu-id="c48be-252">Yes</span></span>  <br/> |<span data-ttu-id="c48be-253">所有 Office 365 組織，Outlook.com</span><span class="sxs-lookup"><span data-stu-id="c48be-253">All Office 365 organizations, Outlook.com</span></span>  <br/> |
|<span data-ttu-id="c48be-254">跨網域</span><span class="sxs-lookup"><span data-stu-id="c48be-254">Cross-domain</span></span>  <br/> |<span data-ttu-id="c48be-255">詐騙</span><span class="sxs-lookup"><span data-stu-id="c48be-255">SPOOF</span></span>  <br/> |<span data-ttu-id="c48be-256">是</span><span class="sxs-lookup"><span data-stu-id="c48be-256">Yes</span></span>  <br/> |<span data-ttu-id="c48be-257">Office 365 進階威脅防護 (ATP) 與 E5 客戶</span><span class="sxs-lookup"><span data-stu-id="c48be-257">Office 365 Advanced Threat Protection and E5 customers</span></span>  <br/> |

### <a name="changing-your-anti-spoofing-settings"></a><span data-ttu-id="c48be-258">變更您的反詐騙設定</span><span class="sxs-lookup"><span data-stu-id="c48be-258">Changing your anti-spoofing settings</span></span>

<span data-ttu-id="c48be-259">若要建立或更新 (跨網域) 反詐騙設定，請瀏覽至 [安全性與合規性中心] 中的 [威脅管理] \> [原則] 索引標籤下的 [防網路釣魚] \>[反詐騙] 設定。</span><span class="sxs-lookup"><span data-stu-id="c48be-259">To create or update your (cross-domain) anti-spoofing settings, navigate to the Anti-phishing \> Anti-spoofing settings under the Threat Management \> Policy tab in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="c48be-260">如果您之前從未建立過任何防網路釣魚設定，您必須建立一個新：</span><span class="sxs-lookup"><span data-stu-id="c48be-260">If you have never created any anti-phishing settings, you will need to create one:</span></span>
  
![防網路釣魚 - 建立新原則](media/9337ec91-270e-4fa7-9dfa-a51a2d1eb95e.jpg)
  
<span data-ttu-id="c48be-262">如果您已建立，則可以加以選取來修改：</span><span class="sxs-lookup"><span data-stu-id="c48be-262">If you've already created one, you can select it to modify it:</span></span>
  
![防網路釣魚 - 修改現有原則](media/75457a7c-882e-4984-80d1-21a12b42c53a.jpg)
  
<span data-ttu-id="c48be-264">選取您剛剛建立的原則，然後繼續進行[深入了解詐騙情報](learn-about-spoof-intelligence.md)中所述的步驟。</span><span class="sxs-lookup"><span data-stu-id="c48be-264">Select the policy you just created and proceed through the steps as described in [Learn more about spoof intelligence](learn-about-spoof-intelligence.md).</span></span>
  
![啟用或停用反詐騙功能](media/c49e2147-c954-443c-9144-1cbd139e1166.jpg)
  
![啟用或停用反詐騙安全提示](media/eec7c407-31fc-4f73-8325-307d82d1fb53.jpg)
  
<span data-ttu-id="c48be-267">若要使用 PowerShell 建立新原則：</span><span class="sxs-lookup"><span data-stu-id="c48be-267">To create a new policy by using PowerShell:</span></span> 
  
```powershell
$org = Get-OrganizationConfig
$name = "My first anti-phishing policy for " + $org.Name
# Note: The name should not exclude 64 characters, including spaces.
# If it does, you will need to pick a smaller name.
# Next, create a new anti-phishing policy with the default values
New-AntiphishPolicy -Name $Name
# Select the domains to scope it to
# Multiple domains are specified in a comma-separated list
$domains = "domain1.com, domain2.com, domain3.com"
# Next, create the anti-phishing rule, scope it to the anti-phishing rule
New-AntiphishRule -Name $name -AntiphishPolicy $name -RecipientDomainIs $domains
```

<span data-ttu-id="c48be-268">您可以使用 PowerShell 並遵照 [Set-AntiphishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy?view=exchange-ps) 文件中的指示來修改防網路釣魚原則參數。</span><span class="sxs-lookup"><span data-stu-id="c48be-268">You may then modify the anti-phishing policy parameters using PowerShell, following the documentation at [Set-AntiphishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy?view=exchange-ps).</span></span> <span data-ttu-id="c48be-269">您可以指定 $name 做為參數：</span><span class="sxs-lookup"><span data-stu-id="c48be-269">You may specify the $name as a parameter:</span></span>
  
```powershell
Set-AntiphishPolicy -Identity $name <fill in rest of parameters>
```

<span data-ttu-id="c48be-270">2018 年下半年，就不需要由您來建立預設原則，系統會為您建立一個涵蓋組織內所有收件者的原則，因此您就不需手動指定 (在最終實作前，以下螢幕擷取畫面有可能變更。)</span><span class="sxs-lookup"><span data-stu-id="c48be-270">Later in 2018, rather than you having to create a default policy, one will be created for you that is scoped to all the recipients in your organization so you don't have to specify it manually (the screenshots below are subject to change before the final implementation).</span></span>
  
![防網路釣魚的預設原則](media/1f27a0bf-e202-4e12-bbac-24baf013c8f9.jpg)
  
<span data-ttu-id="c48be-272">不同於您所建立的原則，您無法刪除預設原則、修改它的優先順序，或選擇要納入範圍的使用者、網域或群組。</span><span class="sxs-lookup"><span data-stu-id="c48be-272">Unlike a policy that you create, you cannot delete the default policy, modify its priority, or choose which users, domains, or groups to scope it to.</span></span>
  
![防網路釣魚預設原則的詳細資訊](media/30c21ceb-df52-4c93-aa65-f44a55dc1009.jpg)
  
<span data-ttu-id="c48be-274">若要使用 PowerShell 設定預設的防護功能：</span><span class="sxs-lookup"><span data-stu-id="c48be-274">To set up your default protection by using PowerShell:</span></span>
  
```powershell
$defaultAntiphishPolicy = Get-AntiphishPolicy | ? {$_.IsDefault -eq $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement <$true|$false>
```

<span data-ttu-id="c48be-275">只有當 Office 365 前面有另一台郵件伺服器或多台伺服器，您才應該停用反詐騙防護功能 (詳細資料，請參閱「停用反詐騙功能的合法案例」)。</span><span class="sxs-lookup"><span data-stu-id="c48be-275">You should only disable anti-spoofing protection if you have another mail server or servers in front of Office 365 (see Legitimate scenarios to disable anti-spoofing for more details).</span></span>
  
```powershell
$defaultAntiphishPolicy = Get-AntiphishiPolicy | ? {$_.IsDefault $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement $false 

```
> [!IMPORTANT]
> <span data-ttu-id="c48be-276">如果電子郵件路徑中的第一躍點是 Office 365，且有太多合法電子郵件被標示為詐騙郵件，您應該先設定允許傳送詐騙電子郵件到您網域的寄件者 (請參閱*管理傳送未經驗證電子郵件的合法寄件者*)。</span><span class="sxs-lookup"><span data-stu-id="c48be-276">If the first hop in your email path is Office 365, and you are getting too many legitimate emails marked as spoof, you should first set up your senders that are allowed to send spoofed email to your domain (see the section  *"Managing legitimate senders who are sending unauthenticated email"*  ).</span></span> <span data-ttu-id="c48be-277">如果還是發生太多誤判 (也就是合法郵件被標示為詐騙郵件)，我們則不建議停用反詐騙防護功能。</span><span class="sxs-lookup"><span data-stu-id="c48be-277">If you are still getting too many false positives (that is, legitimate messages marked as spoof), we do NOT recommend disabling anti-spoofing protection altogether.</span></span> <span data-ttu-id="c48be-278">但是，我們建議您選擇基本防護，不要選擇高度防護。</span><span class="sxs-lookup"><span data-stu-id="c48be-278">Instead, we recommend choosing Basic instead of High protection.</span></span> <span data-ttu-id="c48be-279">處理誤判總比將組織暴露在詐騙電子郵件下好，因為後者長期下來可能會耗費相當可觀的成本。</span><span class="sxs-lookup"><span data-stu-id="c48be-279">It is better to work through false positives than to expose your organization to spoofed email which could end up imposing significantly higher costs in the long term.</span></span>

### <a name="managing-legitimate-senders-who-are-sending-unauthenticated-email"></a><span data-ttu-id="c48be-280">管理傳送未經驗證電子郵件的合法寄件者</span><span class="sxs-lookup"><span data-stu-id="c48be-280">Managing legitimate senders who are sending unauthenticated email</span></span>

<span data-ttu-id="c48be-281">Office 365 會追蹤誰傳送未經驗證電子郵件到您的組織。</span><span class="sxs-lookup"><span data-stu-id="c48be-281">Office 365 keeps track of who is sending unauthenticated email to your organization.</span></span> <span data-ttu-id="c48be-282">如果該服務認為寄件者不合法，則會標示為 *compauth* 失敗。</span><span class="sxs-lookup"><span data-stu-id="c48be-282">If the service thinks the sender is not legitimate, it will mark it as a *compauth* failure.</span></span> <span data-ttu-id="c48be-283">雖然需要根據郵件所套用的反詐騙原則，此郵件還是會分類為詐騙郵件。</span><span class="sxs-lookup"><span data-stu-id="c48be-283">This will be classified as SPOOF although it depends on your anti-spoofing policy that was applied to the message.</span></span>
  
<span data-ttu-id="c48be-284">不過，身為系統管理員，您可以指定可傳送詐騙電子郵件的寄件者，來覆寫 Office 365 決策。</span><span class="sxs-lookup"><span data-stu-id="c48be-284">However, as an administrator, you can specify which senders are permitted to send spoofed email, overriding Office 365's decision.</span></span>
  
<span data-ttu-id="c48be-285">**方法 1 - 如果您的組織擁有該網域，請設定電子郵件驗證**</span><span class="sxs-lookup"><span data-stu-id="c48be-285">**Method 1 - If your organization owns the domain, set up email authentication**</span></span>
  
<span data-ttu-id="c48be-286">在您擁有多個租用戶，或與多個租用戶互動的情況下，這個方法可用來解決組織內部詐騙和跨網域詐騙。</span><span class="sxs-lookup"><span data-stu-id="c48be-286">This method can be used to resolve intra-org spoofing, and cross-domain spoofing in cases where you own or interact with multiple tenants.</span></span> <span data-ttu-id="c48be-287">其也有助於解決跨網域詐騙，您在其中傳送郵件給 Office 365 內的客戶，以及主控於其他提供者的第三方。</span><span class="sxs-lookup"><span data-stu-id="c48be-287">It also helps resolve cross-domain spoofing where you send to other customers within Office 365, and also third parties that are hosted in other providers.</span></span>
  
<span data-ttu-id="c48be-288">如需詳細資訊，請參閱 [Office 365 的客戶](#customers-of-office-365)。</span><span class="sxs-lookup"><span data-stu-id="c48be-288">For more details, see [Customers of Office 365](#customers-of-office-365).</span></span>

<span data-ttu-id="c48be-289">**方法 2 - 使用詐騙情報來設定允許傳送未經驗證電子郵件的寄件者**</span><span class="sxs-lookup"><span data-stu-id="c48be-289">**Method 2 - Use Spoof intelligence to configure permitted senders of unauthenticated email**</span></span>
  
<span data-ttu-id="c48be-290">您也可以使用[詐騙情報](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf)來允許寄件者將未經驗證的郵件傳送至您的組織。</span><span class="sxs-lookup"><span data-stu-id="c48be-290">You can also use [Spoof Intelligence](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf) to permit senders to transmit unauthenticated messages to your organization.</span></span> 
  
<span data-ttu-id="c48be-291">對外部網域來說，詐騙使用者是寄件者地址中的網域，而傳送基礎架構則是傳送 IP 位置 (分為 /24 CIDR 範圍) 或 PTR 記錄的組織網域 (在以下螢幕擷取畫面中，傳送 IP 可能是131.107.18.4，其 PTR 記錄是 outbound.mail.protection.outlook.com，這將顯示為傳送基礎架構的 outlook.com)。</span><span class="sxs-lookup"><span data-stu-id="c48be-291">For external domains, the spoofed user is the domain in the From address, while the sending infrastructure is either the sending IP address (divided up into /24 CIDR ranges), or the organizational domain of the PTR record (in the screenshot below, the sending IP might be 131.107.18.4 whose PTR record is outbound.mail.protection.outlook.com, and this would show up as outlook.com for the sending infrastructure).</span></span>
  
<span data-ttu-id="c48be-292">若要允許此寄件者傳送未經驗證的電子郵件，請將 [否] \*\*\*\* 變更為 [是]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c48be-292">To permit this sender to send unauthenticated email, change the **No** to a **Yes**.</span></span>
  
![設定反詐騙允許的寄件者](media/d4334921-d820-4334-8217-788279701e94.jpg)
  
<span data-ttu-id="c48be-294">您也可以使用 PowerShell 以允許特定寄件者偽造您的網域：</span><span class="sxs-lookup"><span data-stu-id="c48be-294">You can also use PowerShell to allow specific sender to spoof your domain:</span></span>
  
```powershell
$file = "C:\My Documents\Summary Spoofed Internal Domains and Senders.csv"
```

```powershell
Get-PhishFilterPolicy -Detailed -SpoofAllowBlockList -SpoofType External | Export-CSV $file
```

![從 Powershell 設定冒名寄件者](media/0e27ffcf-a5db-4c43-a19b-fa62326d5118.jpg)
  
<span data-ttu-id="c48be-296">在上一個影像中，新增了額外的分行符號，讓這個螢幕擷取畫面顯示為最適大小。</span><span class="sxs-lookup"><span data-stu-id="c48be-296">In the previous image, additional line breaks have been added to make this screenshot fit.</span></span> <span data-ttu-id="c48be-297">一般來說，所有值會顯示在同一行。</span><span class="sxs-lookup"><span data-stu-id="c48be-297">Normally, all the values would appear on a single line.</span></span>
  
<span data-ttu-id="c48be-298">編輯檔案並尋找對應至 outlook.com 和 bing.com 的行，並將 AllowedToSpoof 項目從 No 變更為 Yes：</span><span class="sxs-lookup"><span data-stu-id="c48be-298">Edit the file and look for the line that corresponds to outlook.com and bing.com, and change the AllowedToSpoof entry from No to Yes:</span></span>
  
![在 Powershell 中將 spoof allow 設定為 Yes](media/62340452-62d3-4958-9ce9-afe5275a870d.jpg)
  
<span data-ttu-id="c48be-300">儲存檔案，然後再執行：</span><span class="sxs-lookup"><span data-stu-id="c48be-300">Save the file, and then run:</span></span>
  
```powershell
$UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
```

<span data-ttu-id="c48be-301">現在，這能讓 bing.com 從 \*.outlook.com 傳送未經驗證的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="c48be-301">This will now allow bing.com to send unauthenticated email from \*.outlook.com.</span></span>

<span data-ttu-id="c48be-302">**方法 3 - 為寄件者/收件者配對建立允許項目**</span><span class="sxs-lookup"><span data-stu-id="c48be-302">**Method 3 - Create an allow entry for the sender/recipient pair**</span></span>
  
<span data-ttu-id="c48be-303">您也可以選擇略過篩選特定寄件者的所有垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="c48be-303">You can also choose to bypass all spam filtering for a particular sender.</span></span> <span data-ttu-id="c48be-304">如需詳細資訊，請參閱[如何在 Office 365 中安全地將寄件者新增至允許清單](https://blogs.msdn.microsoft.com/tzink/2017/11/29/how-to-securely-add-a-sender-to-an-allow-list-in-office-365/) (英文)。</span><span class="sxs-lookup"><span data-stu-id="c48be-304">For more details, see [How to securely add a sender to an allow list in Office 365](https://blogs.msdn.microsoft.com/tzink/2017/11/29/how-to-securely-add-a-sender-to-an-allow-list-in-office-365/).</span></span>
  
<span data-ttu-id="c48be-305">如果您使用這個方法，將略過垃圾郵件和部分網路釣魚篩選，但不會略過惡意程式碼篩選。</span><span class="sxs-lookup"><span data-stu-id="c48be-305">If you use this method, it will skip spam and some of the phish filtering, but not malware filtering.</span></span>
  
<span data-ttu-id="c48be-306">**方法 4 - 連絡寄件者，並要求他們設定電子郵件驗證**</span><span class="sxs-lookup"><span data-stu-id="c48be-306">**Method 4 - Contact the sender and ask them to set up email authentication**</span></span>
  
<span data-ttu-id="c48be-307">有鑑於垃圾郵件和網路釣魚問題，Microsoft 建議所有寄件者設定電子郵件驗證。</span><span class="sxs-lookup"><span data-stu-id="c48be-307">Because of the problem of spam and phishing, Microsoft recommends all senders set up email authentication.</span></span> <span data-ttu-id="c48be-308">如果您知道傳送網域的系統管理員，請連絡他們來設定電子郵件驗證記錄，這樣您就不需要新增任何覆寫設定。</span><span class="sxs-lookup"><span data-stu-id="c48be-308">If you know an administrator of the sending domain, contact them and request that they set up email authentication records so you do not have to add any overrides.</span></span> <span data-ttu-id="c48be-309">如需詳細資訊，請參閱本文稍後的[非 Office 365 客戶的網域系統管理員](#administrators-of-domains-that-are-not-office-365-customers)。</span><span class="sxs-lookup"><span data-stu-id="c48be-309">For more information, see [Administrators of domains that are not Office 365 customers](#administrators-of-domains-that-are-not-office-365-customers)" later in this article.</span></span> 
  
<span data-ttu-id="c48be-310">雖然一開始驗證傳送網域可能會有困難，但隨著時間過去，有越來越多的電子郵件篩選器開始篩選垃圾郵件或甚至拒絕他們的電子郵件，促使他們設定正確記錄以確保更佳的傳遞。</span><span class="sxs-lookup"><span data-stu-id="c48be-310">While it may be difficult at first to get sending domains to authenticate, over time, as more and more email filters start junking or even rejecting their email, it will cause them to set up the proper records to ensure better delivery.</span></span>
  
### <a name="viewing-reports-of-how-many-messages-were-marked-as-spoofed"></a><span data-ttu-id="c48be-311">檢視報告，了解有多少郵件被標示為詐騙郵件</span><span class="sxs-lookup"><span data-stu-id="c48be-311">Viewing reports of how many messages were marked as spoofed</span></span>

<span data-ttu-id="c48be-312">啟用反詐騙原則後，您就可以使用調查和應變功能來得知有多少郵件被標示為網路釣魚郵件。</span><span class="sxs-lookup"><span data-stu-id="c48be-312">Once your anti-spoofing policy is enabled, you can use threat investigation and response capabilities to get numbers around how many messages are marked as phish.</span></span> <span data-ttu-id="c48be-313">若要這麼做，請移至安全性與合規性中心 (SCC)，在 [威脅管理] \> [總管] 下，將 [檢視] 設為 [網路釣魚]，並依 [寄件者網域] 或 [防護狀態] 來群組：</span><span class="sxs-lookup"><span data-stu-id="c48be-313">To do this, go into the Security &amp; Compliance Center (SCC) under Threat Management \> Explorer, set the View to Phish, and group by Sender Domain or Protection Status:</span></span>
  
![檢視有多少郵件被標示為網路釣魚郵件](media/de25009a-44d4-4c5f-94ba-9c75cd9c64b3.jpg)
  
<span data-ttu-id="c48be-315">您可以與各式各樣的報告互動，以查看有多少郵件被標示為網路釣魚郵件，包括被標示為 SPOOF 的郵件。</span><span class="sxs-lookup"><span data-stu-id="c48be-315">You can interact with the various reports to see how many were marked as phishing, including messages marked as SPOOF.</span></span> <span data-ttu-id="c48be-316">若要深入了解，請參閱[Office 365 威脅調查與應變快速入門](get-started-with-ti.md)。</span><span class="sxs-lookup"><span data-stu-id="c48be-316">To learn more, see [Get started with Office 365 Threat investigation and response](get-started-with-ti.md).</span></span>
  
<span data-ttu-id="c48be-317">由於詐騙與其他類型的網路釣魚不同 (一般網路釣魚，網域使用者冒充等)，您還無法拆分哪些郵件被標記。</span><span class="sxs-lookup"><span data-stu-id="c48be-317">You can't yet split out which messages were marked due to spoofing as opposed to other types of phishing (general phishing, domain or user impersonation, and so on).</span></span> <span data-ttu-id="c48be-318">不過，日後您將能透過安全性與合規性中心來完成。</span><span class="sxs-lookup"><span data-stu-id="c48be-318">However, later, you will be able to do this through the Security &amp; Compliance Center.</span></span> <span data-ttu-id="c48be-319">之後，您就可以使用這份報告來辨別因為驗證失敗，導致可能合法但被卻標示為詐騙的傳送網域。</span><span class="sxs-lookup"><span data-stu-id="c48be-319">Once you do, you can use this report as a starting place to identify sending domains that may be legitimate that are being marked as spoof due to failing authentication.</span></span>
  
<span data-ttu-id="c48be-320">下列螢幕擷取畫面是此資料外觀的提議，但發行時可能有所變更：</span><span class="sxs-lookup"><span data-stu-id="c48be-320">The following screenshot is a proposal for how this data will look, but may change when released:</span></span>
  
![依據偵測類型檢視網路釣魚報告](media/dd25d63f-152c-4c55-a07b-184ecda2de81.jpg)
  
<span data-ttu-id="c48be-322">針對非 ATP 和 E5 的客戶，之後可在威脅防護狀態 (TPS) 報告下使用這些報告，但將延遲至少 24 個小時。</span><span class="sxs-lookup"><span data-stu-id="c48be-322">For non-ATP and E5 customers, these reports will be available later under the Threat Protection Status (TPS) reports, but will be delayed by at least 24 hours.</span></span> <span data-ttu-id="c48be-323">當這些客戶整合至安全性與合規性中心之後，這個頁面將會更新。</span><span class="sxs-lookup"><span data-stu-id="c48be-323">This page will be updated as they are integrated into the Security &amp; Compliance Center.</span></span>
  
### <a name="predicting-how-many-messages-will-be-marked-as-spoof"></a><span data-ttu-id="c48be-324">預測有多少郵件被標示為詐騙郵件</span><span class="sxs-lookup"><span data-stu-id="c48be-324">Predicting how many messages will be marked as spoof</span></span>

<span data-ttu-id="c48be-325">當 Office 365 更新其設定，讓您您關閉反詐騙強制措施後，或者啟用基本或高度強制措施，您將能夠查看在不同設定下郵件處置方式的變更。</span><span class="sxs-lookup"><span data-stu-id="c48be-325">Once Office 365 updates its settings to let you turn the anti-spoofing enforcement Off, or on with Basic or High enforcement, you will be given the ability to see how message disposition will change at the various settings.</span></span> <span data-ttu-id="c48be-326">也就是說，如果反詐騙功能原本是關閉的，當您改為基本，您能看到有多少郵件將被偵測為詐騙郵件；或者，如果原本是基本，當您改為高度時，您會看到是否有更多郵件會被偵測為詐騙郵件。</span><span class="sxs-lookup"><span data-stu-id="c48be-326">That is, if anti-spoofing is Off, you will be able to see how many messages will be detected as Spoof if you turn to Basic; or, if it's Basic, you will be able to see how many more messages will be detected as Spoof if you turn it to High.</span></span>
  
<span data-ttu-id="c48be-327">這項功能目前還在開發階段。</span><span class="sxs-lookup"><span data-stu-id="c48be-327">This feature is currently under development.</span></span> <span data-ttu-id="c48be-328">隨著更多詳細資料定義之後，此頁面將更新安全性與合規性中心的螢幕擷取畫面以及 PowerShell範例。</span><span class="sxs-lookup"><span data-stu-id="c48be-328">As more details are defined, this page will be updated both with screenshots of the Security and Compliance Center, and with PowerShell examples.</span></span>
  
![啟用反詐騙的「模擬」報告](media/fdd085ae-02c1-4327-a063-bfe9a32ff1eb.jpg)
  
![用於允許詐騙寄件者可能的 UX](media/53f9f73e-fb01-47f3-9a6d-850c1aef5efe.jpg)
  
### <a name="understanding-how-spam-phishing-and-advanced-phishing-detections-are-combined"></a><span data-ttu-id="c48be-331">了解如何將垃圾郵件、網路釣魚和進階網路釣魚偵測結合</span><span class="sxs-lookup"><span data-stu-id="c48be-331">Understanding how spam, phishing, and advanced phishing detections are combined</span></span>

<span data-ttu-id="c48be-332">使用 Exchange Online (有或沒有ATP) 的組織可以指定當服務將郵件識別為惡意程式碼、垃圾郵件，信賴度高的垃圾郵件、網路釣魚郵件和大量郵件時要採取的動作。</span><span class="sxs-lookup"><span data-stu-id="c48be-332">Organizations that use Exchange Online, with or without ATP, can specify which actions to take when the service identifies messages as malware, spam, high confidence spam, phishing, and bulk.</span></span> <span data-ttu-id="c48be-333">有針對 ATP 客戶的 ATP 防網路釣魚原則、針對 EOP 客戶的防網路釣魚原則策略，再加上郵件可能涉及多種偵測類型 (例如，惡意程式碼、網路釣魚和使用者冒充)，對於該套用哪個原則可能會產生混淆。</span><span class="sxs-lookup"><span data-stu-id="c48be-333">With the ATP Anti-phishing policies for ATP customers, and the Anti-phishing policies for EOP customers, and the fact that a message may hit multiple detection types (for example, malware, phishing, and user-impersonation), there may be some confusion as to which policy applies.</span></span>
  
<span data-ttu-id="c48be-334">一般來說，可從 CAT (Category) 屬性的 X-Forefront-Antispam-Report 標頭中辨識套用於郵件的原則。</span><span class="sxs-lookup"><span data-stu-id="c48be-334">In general, the policy applied to a message is identified in the X-Forefront-Antispam-Report header in the CAT (Category) property.</span></span>
  
|<span data-ttu-id="c48be-335">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="c48be-335">**Priority**</span></span>|<span data-ttu-id="c48be-336">**原則**</span><span class="sxs-lookup"><span data-stu-id="c48be-336">**Policy**</span></span>|<span data-ttu-id="c48be-337">**類別**</span><span class="sxs-lookup"><span data-stu-id="c48be-337">**Category**</span></span>|<span data-ttu-id="c48be-338">**在何處進行管理？**</span><span class="sxs-lookup"><span data-stu-id="c48be-338">**Where managed?**</span></span>|<span data-ttu-id="c48be-339">**適用對象**</span><span class="sxs-lookup"><span data-stu-id="c48be-339">**Applies to**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c48be-340">1</span><span class="sxs-lookup"><span data-stu-id="c48be-340">1</span></span>  <br/> |<span data-ttu-id="c48be-341">惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="c48be-341">Malware</span></span>  <br/> |<span data-ttu-id="c48be-342">MALW</span><span class="sxs-lookup"><span data-stu-id="c48be-342">MALW</span></span>  <br/> |[<span data-ttu-id="c48be-343">惡意程式碼原則</span><span class="sxs-lookup"><span data-stu-id="c48be-343">Malware policy</span></span>](configure-anti-malware-policies.md) <br/> |<span data-ttu-id="c48be-344">所有組織</span><span class="sxs-lookup"><span data-stu-id="c48be-344">All organizations</span></span>  <br/> |
|<span data-ttu-id="c48be-345">2</span><span class="sxs-lookup"><span data-stu-id="c48be-345">2</span></span>  <br/> |<span data-ttu-id="c48be-346">網路釣魚</span><span class="sxs-lookup"><span data-stu-id="c48be-346">Phishing</span></span>  <br/> |<span data-ttu-id="c48be-347">PHSH</span><span class="sxs-lookup"><span data-stu-id="c48be-347">PHSH</span></span>  <br/> |[<span data-ttu-id="c48be-348">設定您的垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="c48be-348">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md) <br/> |<span data-ttu-id="c48be-349">所有組織</span><span class="sxs-lookup"><span data-stu-id="c48be-349">All organizations</span></span>  <br/> |
|<span data-ttu-id="c48be-350">3</span><span class="sxs-lookup"><span data-stu-id="c48be-350">3</span></span>  <br/> |<span data-ttu-id="c48be-351">高信賴度的垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="c48be-351">High confidence spam</span></span>  <br/> |<span data-ttu-id="c48be-352">HSPM</span><span class="sxs-lookup"><span data-stu-id="c48be-352">HSPM</span></span>  <br/> |[<span data-ttu-id="c48be-353">設定您的垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="c48be-353">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md) <br/> |<span data-ttu-id="c48be-354">所有組織</span><span class="sxs-lookup"><span data-stu-id="c48be-354">All organizations</span></span>  <br/> |
|<span data-ttu-id="c48be-355">4</span><span class="sxs-lookup"><span data-stu-id="c48be-355">4</span></span>  <br/> |<span data-ttu-id="c48be-356">詐騙</span><span class="sxs-lookup"><span data-stu-id="c48be-356">Spoofing</span></span>  <br/> |<span data-ttu-id="c48be-357">SPOOF</span><span class="sxs-lookup"><span data-stu-id="c48be-357">SPOOF</span></span>  <br/> |<span data-ttu-id="c48be-358">[防網路釣魚原則](https://go.microsoft.com/fwlink/?linkid=864553)，[詐騙情報](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="c48be-358">[Anti-phishing policy](https://go.microsoft.com/fwlink/?linkid=864553), [Spoof intelligence](learn-about-spoof-intelligence.md)</span></span> <br/> |<span data-ttu-id="c48be-359">所有組織</span><span class="sxs-lookup"><span data-stu-id="c48be-359">All organizations</span></span>  <br/> |
|<span data-ttu-id="c48be-360">5</span><span class="sxs-lookup"><span data-stu-id="c48be-360">5</span></span>  <br/> |<span data-ttu-id="c48be-361">垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="c48be-361">Spam</span></span>  <br/> |<span data-ttu-id="c48be-362">SPM</span><span class="sxs-lookup"><span data-stu-id="c48be-362">SPM</span></span>  <br/> |[<span data-ttu-id="c48be-363">設定您的垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="c48be-363">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md) <br/> |<span data-ttu-id="c48be-364">所有組織</span><span class="sxs-lookup"><span data-stu-id="c48be-364">All organizations</span></span>  <br/> |
|<span data-ttu-id="c48be-365">6</span><span class="sxs-lookup"><span data-stu-id="c48be-365">6</span></span>  <br/> |<span data-ttu-id="c48be-366">大量</span><span class="sxs-lookup"><span data-stu-id="c48be-366">Bulk</span></span>  <br/> |<span data-ttu-id="c48be-367">BULK</span><span class="sxs-lookup"><span data-stu-id="c48be-367">BULK</span></span>  <br/> |[<span data-ttu-id="c48be-368">設定您的垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="c48be-368">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md) <br/> |<span data-ttu-id="c48be-369">所有組織</span><span class="sxs-lookup"><span data-stu-id="c48be-369">All organizations</span></span>  <br/> |
|<span data-ttu-id="c48be-370">7</span><span class="sxs-lookup"><span data-stu-id="c48be-370">7</span></span>  <br/> |<span data-ttu-id="c48be-371">網域冒充</span><span class="sxs-lookup"><span data-stu-id="c48be-371">Domain Impersonation</span></span>  <br/> |<span data-ttu-id="c48be-372">DIMP</span><span class="sxs-lookup"><span data-stu-id="c48be-372">DIMP</span></span>  <br/> |[<span data-ttu-id="c48be-373">設定 Office 365 ATP 防網路釣魚功能及防網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="c48be-373">Set up Office 365 ATP anti-phishing and anti-phishing policies</span></span>](set-up-anti-phishing-policies.md) <br/> |<span data-ttu-id="c48be-374">僅限使用 ATP 的組織</span><span class="sxs-lookup"><span data-stu-id="c48be-374">Organizations with ATP only</span></span>  <br/> |
|<span data-ttu-id="c48be-375">8</span><span class="sxs-lookup"><span data-stu-id="c48be-375">8</span></span>  <br/> |<span data-ttu-id="c48be-376">使用者冒充</span><span class="sxs-lookup"><span data-stu-id="c48be-376">User Impersonation</span></span>  <br/> |<span data-ttu-id="c48be-377">UIMP</span><span class="sxs-lookup"><span data-stu-id="c48be-377">UIMP</span></span>  <br/> |[<span data-ttu-id="c48be-378">設定 Office 365 ATP 防網路釣魚功能及防網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="c48be-378">Set up Office 365 ATP anti-phishing and anti-phishing policies</span></span>](set-up-anti-phishing-policies.md) <br/> |<span data-ttu-id="c48be-379">僅限使用 ATP 的組織</span><span class="sxs-lookup"><span data-stu-id="c48be-379">Organizations with ATP only</span></span> <br/> |

<span data-ttu-id="c48be-380">如果您有多個不同的防網路釣魚原則時，會套用優先順序最高的原則。</span><span class="sxs-lookup"><span data-stu-id="c48be-380">If you have multiple different Anti-phishing policies, the one at the highest priority will apply.</span></span> <span data-ttu-id="c48be-381">例如，假設您有兩個原則：</span><span class="sxs-lookup"><span data-stu-id="c48be-381">For example, suppose you have two policies:</span></span>

|<span data-ttu-id="c48be-382">**原則**</span><span class="sxs-lookup"><span data-stu-id="c48be-382">**Policy**</span></span>|<span data-ttu-id="c48be-383">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="c48be-383">**Priority**</span></span>|<span data-ttu-id="c48be-384">**使用者/網域冒充**</span><span class="sxs-lookup"><span data-stu-id="c48be-384">**User/Domain Impersonation**</span></span>|<span data-ttu-id="c48be-385">**反詐騙**</span><span class="sxs-lookup"><span data-stu-id="c48be-385">**Anti-spoofing**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c48be-386">A</span><span class="sxs-lookup"><span data-stu-id="c48be-386">A</span></span>  <br/> |<span data-ttu-id="c48be-387">1</span><span class="sxs-lookup"><span data-stu-id="c48be-387">1</span></span>  <br/> |<span data-ttu-id="c48be-388">開啟</span><span class="sxs-lookup"><span data-stu-id="c48be-388">On</span></span>  <br/> |<span data-ttu-id="c48be-389">關閉</span><span class="sxs-lookup"><span data-stu-id="c48be-389">Off</span></span>  <br/> |
|<span data-ttu-id="c48be-390">B</span><span class="sxs-lookup"><span data-stu-id="c48be-390">B</span></span>  <br/> |<span data-ttu-id="c48be-391">2</span><span class="sxs-lookup"><span data-stu-id="c48be-391">2</span></span>  <br/> |<span data-ttu-id="c48be-392">關閉</span><span class="sxs-lookup"><span data-stu-id="c48be-392">Off</span></span>  <br/> |<span data-ttu-id="c48be-393">開啟</span><span class="sxs-lookup"><span data-stu-id="c48be-393">On</span></span>  <br/> |

<span data-ttu-id="c48be-394">如果郵件傳入並被識別為詐騙和使用者冒充郵件，而同一組使用者被納入原則 A 和原則 B 的範圍內，則該郵件會被視為詐騙郵件，但由於反詐騙功能已關閉，所以不會採取任何動作，SPOOF 會以比使用者冒充 (8) 更高的優先次序 (4) 執行。</span><span class="sxs-lookup"><span data-stu-id="c48be-394">If a message comes in and is identified as both spoofing and user impersonation, and the same set of users is scoped to Policy A and Policy B, then the message is treated as a spoof but no action is applied since Anti-spoofing is turned off, and SPOOF runs at a higher priority (4) than User Impersonation (8).</span></span>
  
<span data-ttu-id="c48be-395">若要套用其他類型的網路釣魚原則，您必須調整適用不同原則對象的設定。</span><span class="sxs-lookup"><span data-stu-id="c48be-395">To make other types of phishing policy apply, you will need to adjust the settings of who the various policies are applied to.</span></span>
  
### <a name="legitimate-scenarios-to-disable-anti-spoofing"></a><span data-ttu-id="c48be-396">停用反詐騙功能的合法案例</span><span class="sxs-lookup"><span data-stu-id="c48be-396">Legitimate scenarios to disable anti-spoofing</span></span>

<span data-ttu-id="c48be-397">反詐騙功能可提供客戶更堅強的防護，以免受網路釣魚攻擊，因此強烈建議您不要停用反詐騙防護功能。</span><span class="sxs-lookup"><span data-stu-id="c48be-397">Anti-spoofing better protects customers from phishing attacks, and therefore disabling anti-spoofing protection is strongly discouraged.</span></span> <span data-ttu-id="c48be-398">停用後，您可能解決了短期的誤判狀況，但長期下來，您將暴露在更多風險之中。</span><span class="sxs-lookup"><span data-stu-id="c48be-398">By disabling it, you may resolve some short-term false positives, but long term you will be exposed to more risk.</span></span> <span data-ttu-id="c48be-399">在寄件人端設定驗證，或在網路釣魚原則中進行調整的成本通常是一次性事件或僅需要最少的定期維護。</span><span class="sxs-lookup"><span data-stu-id="c48be-399">The cost for setting up authentication on the sender side, or making adjustments in the phishing policies, are usually one-time events or require only minimal, periodic maintenance.</span></span> <span data-ttu-id="c48be-400">但是，從資料洩露或資產受損的網路釣魚攻擊中恢復的成本，卻高得多。</span><span class="sxs-lookup"><span data-stu-id="c48be-400">However, the cost to recover from a phishing attack where data has been exposed, or assets have been compromised is much higher.</span></span>
  
<span data-ttu-id="c48be-401">基於這個原因，比起停用反詐騙防護功能，解決反詐騙誤判情況的益處更大。</span><span class="sxs-lookup"><span data-stu-id="c48be-401">For this reason, it is better to work through anti-spoofing false positives than to disable anti-spoof protection.</span></span>
  
<span data-ttu-id="c48be-402">但是，有一個合法案例反倒應該停用反詐騙功能，也就是在郵件路由中有其他郵件篩選產品，而且 Office 365 不是電子郵件路徑中的第一個躍點：</span><span class="sxs-lookup"><span data-stu-id="c48be-402">However, there is a legitimate scenario where anti-spoofing should be disabled, and that is when there are additional mail-filtering products in the message routing, and Office 365 is not the first hop in the email path:</span></span>
  
![客戶 MX 記錄並非指向 Office 365](media/62127c16-cfb8-4880-9cad-3c12d827c67e.jpg)
  
<span data-ttu-id="c48be-404">另一個伺服器可以是 Exchange 內部部署郵件伺服器、類似 Ironport 的郵件篩選裝置，或其他雲端託管服務。</span><span class="sxs-lookup"><span data-stu-id="c48be-404">The other server may be an Exchange on-premises mail server, a mail filtering device such as Ironport, or another cloud hosted service.</span></span>
  
<span data-ttu-id="c48be-405">如果收件人網域的 MX 記錄未指向 Office 365，則無需停用反詐騙功能，因為 Office 365 會查詢您的接收網域的 MX 記錄，並在其指向其他服務時禁止反詐騙功能。</span><span class="sxs-lookup"><span data-stu-id="c48be-405">If the MX record of the recipient domain does not point to Office 365, then there is no need to disable anti-spoofing because Office 365 looks up your receiving domain's MX record and suppresses anti-spoofing if it points to another service.</span></span> <span data-ttu-id="c48be-406">如果您不知道網域中是否還有其他伺服器，則可以使用類似 MX Toolbox 的網站來查詢 MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="c48be-406">If you don't know if your domain has another server in front, you can use a website like MX Toolbox to look up the MX record.</span></span> <span data-ttu-id="c48be-407">它可能會顯示如下所示的結果：</span><span class="sxs-lookup"><span data-stu-id="c48be-407">It might say something like the following:</span></span>
  
![MX 記錄會指出網域未指向 Office 365](media/d868bb9f-3462-49aa-baea-9447a3ce4877.jpg)
  
<span data-ttu-id="c48be-409">這個網域擁有的 MX 記錄未指向 Office 365，因此 Office 365 不會套用反詐騙強制措施。</span><span class="sxs-lookup"><span data-stu-id="c48be-409">This domain has an MX record that does not point to Office 365, so Office 365 would not apply anti-spoofing enforcement.</span></span>
  
<span data-ttu-id="c48be-410">不過，如果您的收件者網域的 MX 記錄「未」\*\* 指向 Office 365，即使 Office 365 前有其他服務，您也應該停用反詐騙功能。</span><span class="sxs-lookup"><span data-stu-id="c48be-410">However, if the MX record of the recipient domain  *does*  point to Office 365, even though there is another service in front of Office 365, then you should disable anti-spoofing.</span></span> <span data-ttu-id="c48be-411">最常見的範例是使用收件者重寫：</span><span class="sxs-lookup"><span data-stu-id="c48be-411">The most common example is through the use of a recipient rewrite:</span></span> 
  
![收件者重寫的路由圖表](media/070d90d1-50a0-42e4-9fd3-920bc99a7cad.jpg)
  
<span data-ttu-id="c48be-413">網域 contoso.com 的 MX 記錄指向內部部署伺服器，而網域 @office365.contoso.net 的 MX 記錄指向 Office 365，因為其 MX 記錄中包含 \*.protection.outlook.com 或 \*.eo.outlook.com：</span><span class="sxs-lookup"><span data-stu-id="c48be-413">The domain contoso.com's MX record points to the on-premises server, while the domain @office365.contoso.net's MX record points to Office 365 because it contains \*.protection.outlook.com, or \*.eo.outlook.com in the MX record:</span></span>
  
![MX 記錄指向 Office 365，因此可能是收件者重寫](media/4101ad51-ef92-4907-b466-b41d14d344ca.jpg)
  
<span data-ttu-id="c48be-415">請務必區分收件人網域 MX 記錄何時未指向 Office 365，以及何時進行了收件人重寫。</span><span class="sxs-lookup"><span data-stu-id="c48be-415">Be sure to differentiate when a recipient domain's MX record does not point to Office 365, and when it has undergone a recipient rewrite.</span></span> <span data-ttu-id="c48be-416">請務必分辨出這兩種情況之間的差異。</span><span class="sxs-lookup"><span data-stu-id="c48be-416">It is important to tell the difference between these two cases.</span></span>
  
<span data-ttu-id="c48be-417">如果您不確定您的接收網域是否已經過收件人重寫，有時您可以透過查看郵件標頭來判斷。</span><span class="sxs-lookup"><span data-stu-id="c48be-417">If you are unsure whether or not your receiving domain has undergone a recipient-rewrite, sometimes you can tell by looking at the message headers.</span></span>
  
<span data-ttu-id="c48be-418">a) 首先，在 Authentication-Results 標頭中查看收件者網域的郵件標頭：</span><span class="sxs-lookup"><span data-stu-id="c48be-418">a) First, look at the headers in the message for the recipient domain in the Authentication-Results header:</span></span>
  
```
Authentication-Results: spf=fail (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; office365.contoso.net; dkim=fail
  (body hash did not verify) header.d=simple.example.com;
  office365.contoso.net; dmarc=none action=none
  header.from=example.com; compauth=fail reason=001
```

<span data-ttu-id="c48be-419">收件者網域為上面的粗體紅色字中，在本案例為 office365.contoso.net。</span><span class="sxs-lookup"><span data-stu-id="c48be-419">The recipient domain is found in the bold red text above, in this case office365.contoso.net.</span></span> <span data-ttu-id="c48be-420">這可能會跟 To: 標頭中的收件者不同：</span><span class="sxs-lookup"><span data-stu-id="c48be-420">This may be different that the recipient in the To: header:</span></span>
  
<span data-ttu-id="c48be-421">To: Example Recipient \<recipient @ contoso.com\></span><span class="sxs-lookup"><span data-stu-id="c48be-421">To: Example Recipient \<recipient @ contoso.com\></span></span>
  
<span data-ttu-id="c48be-422">針對實際的收件者網域執行 MX 記錄查詢。</span><span class="sxs-lookup"><span data-stu-id="c48be-422">Perform an MX-record lookup of the actual recipient domain.</span></span> <span data-ttu-id="c48be-423">如果其包含 \*.protection.outlook.com、mail.messaging.microsoft.com、\*.eo.outlook.com 或 mail.global.frontbridge.com，則表示 MX 指向 Office 365。</span><span class="sxs-lookup"><span data-stu-id="c48be-423">If it contains \*.protection.outlook.com, mail.messaging.microsoft.com, \*.eo.outlook.com, or mail.global.frontbridge.com, that means that the MX points to Office 365.</span></span>
  
<span data-ttu-id="c48be-424">如果它不包含這些值，則表示 MX 未指向 Office 365。</span><span class="sxs-lookup"><span data-stu-id="c48be-424">If it does not contain those values, then it means that the MX does not point to Office 365.</span></span> <span data-ttu-id="c48be-425">您可以使用 MX Toolbox 這項工具來進行驗證。</span><span class="sxs-lookup"><span data-stu-id="c48be-425">One tool you can use to verify this is MX Toolbox.</span></span>
  
<span data-ttu-id="c48be-426">對於此特定範例，以下內容表示contoso.com (從 To：標頭看起來像收件人網域) 具有指向內部部署伺服器的 MX 記錄點：</span><span class="sxs-lookup"><span data-stu-id="c48be-426">For this particular example, the following says that contoso.com, the domain that looks like the recipient since it was the To: header, has MX record points to an on-prem server:</span></span>
  
![MX 記錄指向內部部署伺服器](media/2444144a-9a90-4319-96b2-d115041f669f.jpg)
  
<span data-ttu-id="c48be-428">不過，實際的收件者是 office365.contoso.net，其 MX 記錄確實指向 Office 365：</span><span class="sxs-lookup"><span data-stu-id="c48be-428">However, the actual recipient is office365.contoso.net whose MX record does point to Office 365:</span></span>
  
![MX 指向 Office 365，必須是收件者重寫](media/10cf3245-9b50-475a-b655-d8a51f99d812.jpg)
  
<span data-ttu-id="c48be-430">因此，這封郵件可能經過收件者重寫。</span><span class="sxs-lookup"><span data-stu-id="c48be-430">Therefore, this message has likely undergone a recipient-rewrite.</span></span>
  
<span data-ttu-id="c48be-431">b) 第二，請務必能分辨收件者重寫的常見使用案例。</span><span class="sxs-lookup"><span data-stu-id="c48be-431">b) Second, be sure to distinguish between common use cases of recipient rewrites.</span></span> <span data-ttu-id="c48be-432">如果您要收件者網域重寫為 \*.onmicrosoft.com，而非重寫為 \*.mail.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="c48be-432">If you are going to rewrite the recipient domain to \*.onmicrosoft.com, instead rewrite it to \*.mail.onmicrosoft.com.</span></span>
  
<span data-ttu-id="c48be-433">當您確定了在另一台伺服器後面路由的最終收件者網域，以及收件者網域的 MX 記錄確實指向 Office 365 (在其 DNS 記錄中發佈) 後，您就可以繼續停用反詐騙功能。</span><span class="sxs-lookup"><span data-stu-id="c48be-433">Once you have identified the final recipient domain that is routed behind another server and the recipient domain's MX record actually points to Office 365 (as published in its DNS records), you may proceed to disable anti-spoofing.</span></span>
  
<span data-ttu-id="c48be-434">請記住，如果路由路徑中的網域的第一個躍點是 Office 365，請不要停用反詐騙功能，請只在 Office 365 位於一或多個服務後才停用。</span><span class="sxs-lookup"><span data-stu-id="c48be-434">Remember, you don't want to disable anti-spoofing if the domain's first hop in the routing path is Office 365, only when it's behind one or more services.</span></span>
  
### <a name="how-to-disable-anti-spoofing"></a><span data-ttu-id="c48be-435">如何停用反詐騙功能</span><span class="sxs-lookup"><span data-stu-id="c48be-435">How to disable anti-spoofing</span></span>

<span data-ttu-id="c48be-436">如果您已建立防網路釣魚原則，請將 EnableAntispoofEnforcement 參數設為 $false：</span><span class="sxs-lookup"><span data-stu-id="c48be-436">If you already have an Anti-phishing policy created, set the EnableAntispoofEnforcement parameter to $false:</span></span>
  
```
$name = "<name of policy>"
Set-AntiphishPolicy -Identity $name -EnableAntiSpoofEnforcement $false

```

<span data-ttu-id="c48be-437">若您不知道要停用的原則 (或多個原則) 的名稱，可以予以顯示：</span><span class="sxs-lookup"><span data-stu-id="c48be-437">If you don't know the name of the policy (or policies) to disable, you can display them:</span></span>
  
```
Get-AntiphishPolicy | fl Name
```

<span data-ttu-id="c48be-438">如果您沒有任何現有的防網路釣魚原則，您可以建立一個然後再停用它 (即使您沒有原則，仍然會套用反詐騙功能；2018 下半年，系統將會為您建立一個預設原則讓您停用，而不需自行建立)。</span><span class="sxs-lookup"><span data-stu-id="c48be-438">If you don't have any existing anti-phishing policies, you can create one and then disable it (even if you don't have a policy, anti-spoofing is still applied; later on in 2018, a default policy will be created for you and you can then disable that instead of creating one).</span></span> <span data-ttu-id="c48be-439">完成此動作需進行多個步驟：</span><span class="sxs-lookup"><span data-stu-id="c48be-439">You will have to do this in multiple steps:</span></span>
  
```
$org = Get-OrganizationConfig
$name = "My first anti-phishing policy for " + $org.Name
# Note: If the name is more than 64 characters, you will need to choose a smaller one
```

```
# Next, create a new anti-phishing policy with the default values
New-AntiphishPolicy -Name $Name
# Select the domains to scope it to
# Multiple domains are specified in a comma-separated list
$domains = "domain1.com, domain2.com, domain3.com"
# Next, create the anti-phishing rule, scope it to the anti-phishing rule
New-AntiphishRule -Name $name -AntiphishPolicy -RecipientDomainIs $domains
# Finally, scope the anti-phishing policy to the domains
Set-AntiphishPolicy -Identity $name -EnableAntispoofEnforcement $false

```

<span data-ttu-id="c48be-440">僅可透過 Cmdlet 停用反詐騙功能 (之後可在安全性與合規性中心中進行)。</span><span class="sxs-lookup"><span data-stu-id="c48be-440">Disabling anti-spoofing is only available via cmdlet (later it will be available in the Security &amp; Compliance Center).</span></span> <span data-ttu-id="c48be-441">如果您沒有 PowerShell 存取權，開立支援票證。</span><span class="sxs-lookup"><span data-stu-id="c48be-441">If you do not have access to PowerShell, create a support ticket.</span></span>
  
<span data-ttu-id="c48be-442">請記住，這應僅適用於傳送到 Office 365 時經過間接路由的網域。</span><span class="sxs-lookup"><span data-stu-id="c48be-442">Remember, this should only be applied to domains that undergo indirect routing when sent to Office 365.</span></span> <span data-ttu-id="c48be-443">請不要因為某些誤判的發生而停用反詐騙功能，從長遠看來，解決誤判所帶來的效益更好。</span><span class="sxs-lookup"><span data-stu-id="c48be-443">Resist the temptation to disable anti-spoofing because of some false positives, it will be better in the long run to work through them.</span></span>
  
### <a name="information-for-individual-users"></a><span data-ttu-id="c48be-444">適用個別使用者的資訊</span><span class="sxs-lookup"><span data-stu-id="c48be-444">Information for individual users</span></span>

<span data-ttu-id="c48be-445">個別使用者在與反詐騙安全提示的互動方式上會受到限制。</span><span class="sxs-lookup"><span data-stu-id="c48be-445">Individual users are limited in how they can interact with the anti-spoofing safety tip.</span></span> <span data-ttu-id="c48be-446">不過，為解決常見案例有幾件事是您可以做的。</span><span class="sxs-lookup"><span data-stu-id="c48be-446">However, there are several things you can do to resolve common scenarios.</span></span>
  
### <a name="common-scenario-1---mailbox-forwarding"></a><span data-ttu-id="c48be-447">常見案例 1 - 信箱轉寄功能</span><span class="sxs-lookup"><span data-stu-id="c48be-447">Common scenario #1 - Mailbox forwarding</span></span>

<span data-ttu-id="c48be-448">如果您使用其他電子郵件服務，然後將電子郵件轉寄給 Office 365 或 Outlook.com，您的電子郵件可能會被標示為詐騙郵件，並收到紅色安全提示。</span><span class="sxs-lookup"><span data-stu-id="c48be-448">If you use another email service and forward your email to Office 365 or Outlook.com, your email may be marked as spoofing and receive a red safety tip.</span></span> <span data-ttu-id="c48be-449">當轉寄站是 Outlook.com、Office 365，Gmail 或使用[ ARC 通訊協定](https://arc-spec.org)的任何其他服務之一時，Office 365 和 Outlook.com 方案會自動解決此問題。</span><span class="sxs-lookup"><span data-stu-id="c48be-449">Office 365 and Outlook.com plan to address this automatically when the forwarder is one of Outlook.com, Office 365, Gmail, or any other service that uses the [ARC protocol](https://arc-spec.org).</span></span> <span data-ttu-id="c48be-450">但是，在部署該修復程式之前，使用者應使用「連結帳戶」功能直接匯入郵件，而不要使用轉寄選項。</span><span class="sxs-lookup"><span data-stu-id="c48be-450">However, until that fix is deployed, users should use the Connected Accounts feature to import their messages directly, rather than using the forwarding option.</span></span>
  
<span data-ttu-id="c48be-451">若要在 Office 365 中設定連結帳戶，請選取 Office 365 Web 介面右上角的齒輪圖示 \> [郵件] \> [郵件] \> [帳戶] \> [連結帳戶]。</span><span class="sxs-lookup"><span data-stu-id="c48be-451">To set up connected accounts in Office 365, select the Gear icon in the top right corner of the Office 365 web interface \> Mail \> Mail \> Accounts \> Connected accounts.</span></span>
  
![Office 365 - 連結帳戶選項](media/e8e841ca-8861-4d83-8506-2a0858c51010.jpg)
  
<span data-ttu-id="c48be-453">在 Outlook.com 中，程序為齒輪圖示 \> [選項] \> [郵件] \> [帳戶] \> [連結帳戶]。</span><span class="sxs-lookup"><span data-stu-id="c48be-453">In Outlook.com, the process is the Gear icon \> Options \> Mail \> Accounts \> Connected accounts.</span></span>
  
### <a name="common-scenario-2---discussion-lists"></a><span data-ttu-id="c48be-454">常見案例 2 - 討論清單</span><span class="sxs-lookup"><span data-stu-id="c48be-454">Common scenario #2 - Discussion lists</span></span>

<span data-ttu-id="c48be-455">已知討論清單存在反詐騙問題，是因為它們轉寄郵件並修改郵件內容，但卻保留原始寄件者地址的方式。</span><span class="sxs-lookup"><span data-stu-id="c48be-455">Discussion lists are known to have problems with anti-spoofing due to the way they forward the message and modify its contents yet retain the original From: address.</span></span>
  
<span data-ttu-id="c48be-456">例如，假設您的電子郵件地址是 user @ contoso.com，您的興趣是賞鳥，然後加入了 birdwatchers @ example.com 這個討論清單。</span><span class="sxs-lookup"><span data-stu-id="c48be-456">For example, suppose your email address is user @ contoso.com, and you are interested in Bird Watching and join the discussion list birdwatchers @ example.com.</span></span> <span data-ttu-id="c48be-457">當您傳送郵件到討論清單時，您可能會以這種方式傳送：</span><span class="sxs-lookup"><span data-stu-id="c48be-457">When you send a message to the discussion list, you might send it this way:</span></span>
  
<span data-ttu-id="c48be-458">**寄件者：** John Doe \<user @ contoso.com\></span><span class="sxs-lookup"><span data-stu-id="c48be-458">**From:** John Doe \<user @ contoso.com\></span></span> 
  
<span data-ttu-id="c48be-459">**收件者：** Birdwatcher's Discussion List \<birdwatchers @ example.com\></span><span class="sxs-lookup"><span data-stu-id="c48be-459">**To:** Birdwatcher's Discussion List \<birdwatchers @ example.com\></span></span> 
  
<span data-ttu-id="c48be-460">**主旨：** 本週雷尼爾山頂</span><span class="sxs-lookup"><span data-stu-id="c48be-460">**Subject:** Great viewing of blue jays at the top of Mt.</span></span> <span data-ttu-id="c48be-461">觀賞藍鳥的絕佳景點</span><span class="sxs-lookup"><span data-stu-id="c48be-461">Rainier this week</span></span> 
  
<span data-ttu-id="c48be-462">有人這週想要上雷尼爾山</span><span class="sxs-lookup"><span data-stu-id="c48be-462">Anyone want to check out the viewing this week from Mt.</span></span> <span data-ttu-id="c48be-463">賞景嗎？</span><span class="sxs-lookup"><span data-stu-id="c48be-463">Rainier?</span></span>
  
<span data-ttu-id="c48be-464">當電子郵件清單收到郵件時，他們會設定郵件格式、修改郵件內容，並將其重送給討論清單上的其餘成員，成員由來自許多不同電子郵件接收者的參與者組成。</span><span class="sxs-lookup"><span data-stu-id="c48be-464">When the email list receives the message, they format the message, modify its contents, and replay it to the rest of the members on the discussion list which is made up of participants from many different email receivers.</span></span>
  
<span data-ttu-id="c48be-465">**寄件者：** John Doe \<user @ contoso.com\></span><span class="sxs-lookup"><span data-stu-id="c48be-465">**From:** John Doe \<user @ contoso.com\></span></span> 
  
<span data-ttu-id="c48be-466">**收件者：** Birdwatcher's Discussion List \<birdwatchers @ example.com\></span><span class="sxs-lookup"><span data-stu-id="c48be-466">**To:** Birdwatcher's Discussion List \<birdwatchers @ example.com\></span></span> 
  
<span data-ttu-id="c48be-467">**主旨：**[賞鳥人士] 本週雷尼爾山頂</span><span class="sxs-lookup"><span data-stu-id="c48be-467">**Subject:** [BIRDWATCHERS] Great viewing of blue jays at the top of Mt.</span></span> <span data-ttu-id="c48be-468">觀賞藍鳥的絕佳景點</span><span class="sxs-lookup"><span data-stu-id="c48be-468">Rainier this week</span></span> 
  
<span data-ttu-id="c48be-469">有人這週想要上雷尼爾山</span><span class="sxs-lookup"><span data-stu-id="c48be-469">Anyone want to check out the viewing this week from Mt.</span></span> <span data-ttu-id="c48be-470">賞景嗎？</span><span class="sxs-lookup"><span data-stu-id="c48be-470">Rainier?</span></span>
  
---
  
<span data-ttu-id="c48be-471">此郵件已傳送給「賞鳥人士」討論清單。</span><span class="sxs-lookup"><span data-stu-id="c48be-471">This message was sent to the Birdwatchers Discussion List.</span></span> <span data-ttu-id="c48be-472">您隨時可以取消訂閱。</span><span class="sxs-lookup"><span data-stu-id="c48be-472">You can unsubscribe at any time.</span></span>
  
<span data-ttu-id="c48be-473">以上重送的郵件具有相同的寄件者地址 (user @ contoso.com)，但原始郵件在主旨列新增了標籤，以及在郵件底部新增頁腳而經過修改。</span><span class="sxs-lookup"><span data-stu-id="c48be-473">In the above, the replayed message has the same From: address (user @ contoso.com) but the original message has been modified by adding a tag to the Subject line, and a footer to the bottom of the message.</span></span> <span data-ttu-id="c48be-474">這種類郵件修改常見於郵寄清單中，且可能會導致誤判。</span><span class="sxs-lookup"><span data-stu-id="c48be-474">This type of message modification is common in mailing lists, and may result in false positives.</span></span>
  
<span data-ttu-id="c48be-475">如果您或組織內部人員是郵寄清單的系統管理員，可以設定它略過反詐騙檢查。</span><span class="sxs-lookup"><span data-stu-id="c48be-475">If you or someone in your organization is an administrator of the mailing list, you may be able to configure it to pass anti-spoofing checks.</span></span>
  
- <span data-ttu-id="c48be-476">請查看 DMARC.org 上的常見問題集：[我操作郵寄清單，並想要與 DMARC 互相操作，該怎麼做？](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F) (英文)</span><span class="sxs-lookup"><span data-stu-id="c48be-476">Check the FAQ at DMARC.org: [I operate a mailing list and I want to interoperate with DMARC, what should I do?](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F)</span></span>

- <span data-ttu-id="c48be-477">閱讀此部落格文章的指示：[郵寄清單操作人員與 DMARC 互相操作以避免失敗的提示](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/) (英文)</span><span class="sxs-lookup"><span data-stu-id="c48be-477">Read the instructions at this blog post: [A tip for mailing list operators to interoperate with DMARC to avoid failures](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/)</span></span>

- <span data-ttu-id="c48be-478">若考慮在郵寄清單伺服器上安裝更新以支援 ARC，請參閱 [https://arc-spec.org](https://arc-spec.org/)</span><span class="sxs-lookup"><span data-stu-id="c48be-478">Consider installing updates on your mailing list server to support ARC, see [https://arc-spec.org](https://arc-spec.org/)</span></span>

<span data-ttu-id="c48be-479">如果您不需要郵寄清單的擁有權：</span><span class="sxs-lookup"><span data-stu-id="c48be-479">If you do not have ownership of the mailing list:</span></span>
  
- <span data-ttu-id="c48be-480">您可以要求郵件清單的維護者採用上述其中一個選項 (他們也應該為郵件清單重送的來源網域設定電子郵件驗證)</span><span class="sxs-lookup"><span data-stu-id="c48be-480">You can request the maintainer of the mailing list to implement one of the options above (they should also have email authentication set up for the domain the mailing list is relaying from)</span></span>

- <span data-ttu-id="c48be-481">您可以在電子郵件用戶端中建立信箱規則，將郵件移動至收件匣。</span><span class="sxs-lookup"><span data-stu-id="c48be-481">You can create mailbox rules in your email client to move messages to the Inbox.</span></span> <span data-ttu-id="c48be-482">您也可以要求組織的系統管理員如「管理傳送未經驗證電子郵件的合法寄件者」一節所討論，設定允許規則或覆寫規則。</span><span class="sxs-lookup"><span data-stu-id="c48be-482">You can also request your organization's administrators to set up allow rules, or overrides as discussed in the section Managing legitimate senders who are sending unauthenticated email</span></span>

- <span data-ttu-id="c48be-483">您可以向 Office 365 開立支援票證，以建立郵寄清單的覆寫，將它視為合法</span><span class="sxs-lookup"><span data-stu-id="c48be-483">You can create a support ticket with Office 365 to create an override for the mailing list to treat it as legitimate</span></span>

### <a name="other-scenarios"></a><span data-ttu-id="c48be-484">其他案例</span><span class="sxs-lookup"><span data-stu-id="c48be-484">Other scenarios</span></span>

1. <span data-ttu-id="c48be-485">如果以上這兩個常見案例皆不適用於您的情況，請向 Microsoft 回報該郵件為誤判。</span><span class="sxs-lookup"><span data-stu-id="c48be-485">If neither of the above common scenarios applies to your situation, report the message as a false positive back to Microsoft.</span></span> <span data-ttu-id="c48be-486">如需詳細資訊，請參閱本文章稍後的[如何向 Microsoft 回報垃圾郵件或非垃圾郵件？](#how-can-i-report-spam-or-non-spam-messages-back-to-microsoft)這一節。</span><span class="sxs-lookup"><span data-stu-id="c48be-486">For more information, see the section [How can I report spam or non-spam messages back to Microsoft?](#how-can-i-report-spam-or-non-spam-messages-back-to-microsoft) later in this article.</span></span> 

2. <span data-ttu-id="c48be-487">您也可以連絡您的電子郵件系統管理員，請他們向 Microsoft 開立支援票證。</span><span class="sxs-lookup"><span data-stu-id="c48be-487">You may also contact your email administrator who can raise it as a support ticket with Microsoft.</span></span> <span data-ttu-id="c48be-488">Microsoft 工程小組會研究該郵件為何會被標示為詐騙郵件。</span><span class="sxs-lookup"><span data-stu-id="c48be-488">The Microsoft engineering team will investigate why the message was marked as a spoof.</span></span>

3. <span data-ttu-id="c48be-489">此外，如果您知道誰是寄件者，並確定他們並非惡意詐騙，您可回覆寄件者，並指出他們從未經過驗證的伺服器傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="c48be-489">Additionally, if you know who the sender is and are confident they are not being maliciously spoofed, you may reply back to the sender indicating that they are sending messages from a mail server that does not authenticate.</span></span> <span data-ttu-id="c48be-490">當您這樣做時，有時原始寄件者會與設定必要電子郵件驗證記錄的 IT 系統管理員連絡。</span><span class="sxs-lookup"><span data-stu-id="c48be-490">This sometimes results in the original sender contacting their IT administrator who will set up the required email authentication records.</span></span>
  
<span data-ttu-id="c48be-491">當有夠多寄件者回覆網域擁有者，他們應該設定電子郵件驗證記錄時，就可促使他們採取動作。</span><span class="sxs-lookup"><span data-stu-id="c48be-491">When enough senders reply back to domain owners that they should set up email authentication records, it spurs them into taking action.</span></span> <span data-ttu-id="c48be-492">雖然 Microsoft 也會與網域擁有者合作發佈所需的記錄，但是當個別使用者提出要求時，助益更大。</span><span class="sxs-lookup"><span data-stu-id="c48be-492">While Microsoft also works with domain owners to publish the required records, it helps even more when individual users request it.</span></span>

4. <span data-ttu-id="c48be-493">此外，還可以將寄件者加入安全寄件者清單。</span><span class="sxs-lookup"><span data-stu-id="c48be-493">Optionally, add the sender to your Safe Senders list.</span></span> <span data-ttu-id="c48be-494">但是請注意，如果網路釣魚者偽造帳戶，郵件就會傳送至您的信箱。</span><span class="sxs-lookup"><span data-stu-id="c48be-494">However, be aware that if a phisher spoofs that account, it will be delivered to your mailbox.</span></span> <span data-ttu-id="c48be-495">因此，請謹慎使用這個選項。</span><span class="sxs-lookup"><span data-stu-id="c48be-495">Therefore, this option should be used sparingly.</span></span>

## <a name="how-senders-to-microsoft-should-prepare-for-anti-spoofing-protection"></a><span data-ttu-id="c48be-496">Microsoft 的寄件者應如何準備反詐騙防護功能</span><span class="sxs-lookup"><span data-stu-id="c48be-496">How senders to Microsoft should prepare for anti-spoofing protection</span></span>

<span data-ttu-id="c48be-497">如果您是系統管理員，目前會將郵件傳送給 Microsoft，不論是傳送到 Office 365 或 Outlook.com，您應該確保您的電子郵件已正確經過驗證，否則它可能會被標示為垃圾郵件或網路釣魚郵件。</span><span class="sxs-lookup"><span data-stu-id="c48be-497">If you are an administrator who currently sends messages to Microsoft, either Office 365 or Outlook.com, you should ensure that your email is properly authenticated otherwise it may be marked as spam or phish.</span></span>
  
### <a name="customers-of-office-365"></a><span data-ttu-id="c48be-498">Office 365 的客戶</span><span class="sxs-lookup"><span data-stu-id="c48be-498">Customers of Office 365</span></span>

<span data-ttu-id="c48be-499">如果您是 Office 365 客戶，而您使用 Office 365 來傳送外寄電子郵件：</span><span class="sxs-lookup"><span data-stu-id="c48be-499">If you are an Office 365 customer and you use Office 365 to send outbound email:</span></span>
  
- <span data-ttu-id="c48be-500">針對您的網域，[在 Office 365 中設定 SPF 以防止詐騙](set-up-spf-in-office-365-to-help-prevent-spoofing.md)</span><span class="sxs-lookup"><span data-stu-id="c48be-500">For your domains, [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)</span></span>

- <span data-ttu-id="c48be-501">針對主要網域，[在 Office 365 中使用 DKIM 以驗證從您的自訂網域傳送的外寄電子郵件](use-dkim-to-validate-outbound-email.md)</span><span class="sxs-lookup"><span data-stu-id="c48be-501">For your primary domains, [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md)</span></span>

- <span data-ttu-id="c48be-502">[請考慮設定 DMARC 記錄](use-dmarc-to-validate-email.md)，讓網域能判斷誰是合法的寄件者</span><span class="sxs-lookup"><span data-stu-id="c48be-502">[Consider setting up DMARC records](use-dmarc-to-validate-email.md) for your domain to determine who are your legitimate senders</span></span>

<span data-ttu-id="c48be-503">Microsoft 不會針對 SPF、DKIM 和 DMARC 提供詳細實作指南。</span><span class="sxs-lookup"><span data-stu-id="c48be-503">Microsoft does not provide detailed implementation guidelines for each of SPF, DKIM, and DMARC.</span></span> <span data-ttu-id="c48be-504">但是，網路上已發佈許多相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c48be-504">However, there is a lot of information published online.</span></span> <span data-ttu-id="c48be-505">也有協力廠商可專門協助您的組織設定電子郵件驗證記錄。</span><span class="sxs-lookup"><span data-stu-id="c48be-505">There are also 3rd party companies dedicated to helping your organization set up email authentication records.</span></span>
  
### <a name="administrators-of-domains-that-are-not-office-365-customers"></a><span data-ttu-id="c48be-506">非 Office 365 客戶的網域系統管理員</span><span class="sxs-lookup"><span data-stu-id="c48be-506">Administrators of domains that are not Office 365 customers</span></span>

<span data-ttu-id="c48be-507">如果您是網域系統管理員，但不是 Office 365 客戶：</span><span class="sxs-lookup"><span data-stu-id="c48be-507">If you are a domain administrator but are not an Office 365 customer:</span></span>
  
- <span data-ttu-id="c48be-508">您應該設定 SPF 來發佈網域的傳送 IP 位址，並一併設定 DKIM (若可用) 來數位簽署郵件。</span><span class="sxs-lookup"><span data-stu-id="c48be-508">You should set up SPF to publish your domain's sending IP addresses, and also set up DKIM (if available) to digitally sign messages.</span></span> <span data-ttu-id="c48be-509">您也可以考慮設定 DMARC 記錄。</span><span class="sxs-lookup"><span data-stu-id="c48be-509">You may also consider setting up DMARC records.</span></span>

- <span data-ttu-id="c48be-510">如果有大量寄件者代表您發送電子郵件，您應該與他們想出一個傳送電子郵件的方式，讓寄件者地址 (如果它屬於您) 中的傳送網域與通過 SPF 或 DMARC 的網域相符。</span><span class="sxs-lookup"><span data-stu-id="c48be-510">If you have bulk senders who are transmitting email on your behalf, you should work with them to send email in a way such that the sending domain in the From: address (if it belongs to you) aligns with the domain that passes SPF or DMARC.</span></span>

- <span data-ttu-id="c48be-511">如果您擁有內部部署郵件伺服器，或從軟體即服務提供者傳送郵件，或從 Microsoft Azure、GoDaddy、Rackspace、Amazon Web Services 這類的雲端託管服務傳送郵件，您應該確保將它們新增至您的 SP F記錄中。</span><span class="sxs-lookup"><span data-stu-id="c48be-511">If you have on-premises mail servers, or send from a Software-as-a-service provider, or from a cloud-hosting service like Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services, or similar, you should ensure that they are added to your SPF record.</span></span>

- <span data-ttu-id="c48be-512">如果您使用由 ISP 主控的小型網域，您應該根據 ISP 提供給您的指示設定 SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="c48be-512">If you are a small domain that is hosted by an ISP, you should set up your SPF record according to the instructions that is provided to you by your ISP.</span></span> <span data-ttu-id="c48be-513">多數 ISP 都會提供這類指示，也可以在該公司的支援頁面上找到。</span><span class="sxs-lookup"><span data-stu-id="c48be-513">Most ISPs provide these types of instructions and can be found on the company's support pages.</span></span>

- <span data-ttu-id="c48be-514">即使您之前從未發佈過電子郵件驗證，郵件系統也運作的十分良好，您仍應發佈電子郵件驗證記錄，以傳送至 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="c48be-514">Even if you have not had to publish email authentication records before, and it worked fine, you must still publish email authentication records to send to Microsoft.</span></span> <span data-ttu-id="c48be-515">這麼做可以幫助防止網路釣魚，並降低您或您的收件方組織收到網路釣魚郵件的機會。</span><span class="sxs-lookup"><span data-stu-id="c48be-515">By doing so, you are helping in the fight against phishing, and reducing the possibility that either you, or organizations you send to, will get phished.</span></span>

### <a name="what-if-you-dont-know-who-sends-email-as-your-domain"></a><span data-ttu-id="c48be-516">如果您不知道誰以您的網域傳送電子郵件，該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="c48be-516">What if you don't know who sends email as your domain?</span></span>

<span data-ttu-id="c48be-517">許多網域不發佈 SPF 記錄的原因是他們不認識所有寄件者。</span><span class="sxs-lookup"><span data-stu-id="c48be-517">Many domains do not publish SPF records because they do not know who all their senders are.</span></span> <span data-ttu-id="c48be-518">沒關係，您並不需要認識所有寄件者。</span><span class="sxs-lookup"><span data-stu-id="c48be-518">That's okay, you do not need to know who all of them are.</span></span> <span data-ttu-id="c48be-519">您反倒應該先發佈您知道的寄件者的 SPF 記錄，特別是公司流量所在位置，並發佈中性 SPF 原則，?all：</span><span class="sxs-lookup"><span data-stu-id="c48be-519">Instead, you should get started by publishing an SPF record for the ones you do know of, especially where your corporate traffic is located, and publish a neutral SPF policy, ?all:</span></span>
  
<span data-ttu-id="c48be-520">example.com IN TXT "v=spf1 include:spf.example.com ?all"</span><span class="sxs-lookup"><span data-stu-id="c48be-520">example.com IN TXT "v=spf1 include:spf.example.com ?all"</span></span>
  
<span data-ttu-id="c48be-521">中性 SPF 原則表示從公司基礎架構傳送的任何電子郵件都將通過所有其他電子郵件接收者的電子郵件驗證。</span><span class="sxs-lookup"><span data-stu-id="c48be-521">The neutral SPF policy means that any email that comes out of your corporate infrastructure will pass email authentication at all other email receivers.</span></span> <span data-ttu-id="c48be-522">來自您不認識的寄件者人的電子郵件將回歸中性，這幾乎與根本不發佈 SPF 記錄相同。</span><span class="sxs-lookup"><span data-stu-id="c48be-522">Email that comes from senders you don't know about will fall back to neutral, which is almost the same as publishing no SPF record at all.</span></span>
  
<span data-ttu-id="c48be-523">傳送到 Office 365 時，來自公司流量的電子郵件將被標示為已經過驗證，但來自您不知道的來源的電子郵件仍可能被標示為詐騙郵件 (取決於 Office 365 是否可以針對它進行隱含驗證)。</span><span class="sxs-lookup"><span data-stu-id="c48be-523">When sending to Office 365, email that comes from your corporate traffic will be marked as authenticated, but the email that comes from sources you don't know about may still be marked as spoof (depending upon whether or not Office 365 can implicitly authenticate it).</span></span> <span data-ttu-id="c48be-524">但是，比起所有電子郵件都被 Office 365 標示為詐騙郵件，這不失為一項改進。</span><span class="sxs-lookup"><span data-stu-id="c48be-524">However, this is still an improvement from all email being marked as spoof by Office 365.</span></span>
  
<span data-ttu-id="c48be-525">當您開始使用具有 ?all 後援原則的 SPF 記錄後，您可以逐漸納入越來越多的傳送基礎結構，然後發佈更嚴格的原則。</span><span class="sxs-lookup"><span data-stu-id="c48be-525">Once you've gotten started with an SPF record with a fallback policy of ?all, you can gradually include more and more sending infrastructure and then publish a stricter policy.</span></span> 
  
### <a name="what-if-you-are-the-owner-of-a-mailing-list"></a><span data-ttu-id="c48be-526">如果您是郵寄清單擁有者，該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="c48be-526">What if you are the owner of a mailing list?</span></span>

<span data-ttu-id="c48be-527">請參閱[常見案例 2 - 討論清單](#common-scenario-2---discussion-lists)這一節。</span><span class="sxs-lookup"><span data-stu-id="c48be-527">See the section [Common scenario #2 - Discussion lists](#common-scenario-2---discussion-lists).</span></span>
  
### <a name="what-if-you-are-an-infrastructure-provider-such-as-an-internet-service-provider-isp-email-service-provider-esp-or-cloud-hosting-service"></a><span data-ttu-id="c48be-528">如果您是網際網路服務提供者 (ISP)、電子郵件服務提供者 (ESP) 或雲端主控服務等基礎結構提供者，該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="c48be-528">What if you are an infrastructure provider such as an Internet Service Provider (ISP), Email Service Provider (ESP), or cloud hosting service?</span></span>

<span data-ttu-id="c48be-529">如果您主控網域的電子郵件，且該網域用來傳送電子郵件，或提供可傳送電子郵件的主控基礎結構，您應該執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="c48be-529">If you host a domain's email, and it sends email, or provide hosting infrastructure that can send email, you should do the following:</span></span>
  
- <span data-ttu-id="c48be-530">確定您的客戶擁有詳細說明如何發佈 SPF 記錄的文件</span><span class="sxs-lookup"><span data-stu-id="c48be-530">Ensure your customers have documentation detailing what to publish in their SPF records</span></span>

- <span data-ttu-id="c48be-531">即使客戶未明確設定 (使用預設網域登入)，仍考慮在外寄電子郵件中簽署 DKIM 簽章。</span><span class="sxs-lookup"><span data-stu-id="c48be-531">Consider signing DKIM-signatures on outbound email even if the customer doesn't explicitly set it up (sign with a default domain).</span></span> <span data-ttu-id="c48be-532">您甚至可以使用 DKIM 簽章對電子郵件進行雙重簽署 (如果已經設定了客戶的網域，則為第一次，第二次使用您公司的 DKIM簽章)</span><span class="sxs-lookup"><span data-stu-id="c48be-532">You can even double-sign the email with DKIM signatures (once with the customer's domain if they have set it up, and a second time with your company's DKIM signature)</span></span>

<span data-ttu-id="c48be-533">即使您對來自您的平台的電子郵件進行驗證，也無法保證Microsoft 的可傳遞性，但至少可保證 Microsoft 不會因為郵件未經過驗證，而將它列為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="c48be-533">Deliverability to Microsoft is not guaranteed even if you authenticate email originating from your platform, but at least it ensures that Microsoft does not junk your email because it is not authenticated.</span></span> <span data-ttu-id="c48be-534">如需 Outlook.com 如何篩選電子郵件的詳細資料，請參閱[Outlook.com Postmaster 頁面](https://postmaster.live.com/pm/postmaster.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c48be-534">For more details around how Outlook.com filters email, see the [Outlook.com Postmaster page](https://postmaster.live.com/pm/postmaster.aspx).</span></span>
  
<span data-ttu-id="c48be-535">如需服務提供者最佳作法的詳細資訊，請參閱[適用服務提供者的 M3AAWG 行動傳訊最佳做法](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf) (英文)。</span><span class="sxs-lookup"><span data-stu-id="c48be-535">For more details on service providers best practices, see [M3AAWG Mobile Messaging Best Practices for Service Providers](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf).</span></span>
  
## <a name="frequently-asked-questions"></a><span data-ttu-id="c48be-536">常見問題集</span><span class="sxs-lookup"><span data-stu-id="c48be-536">Frequently Asked Questions</span></span>

### <a name="why-is-microsoft-making-this-change"></a><span data-ttu-id="c48be-537">Microsoft 為何要進行這項變更？</span><span class="sxs-lookup"><span data-stu-id="c48be-537">Why is Microsoft making this change?</span></span>

<span data-ttu-id="c48be-538">由於網路釣魚攻擊的影響，以及電子郵件驗證已存在超過 15 年，因此 Microsoft 認為若繼續允許未經驗證的電子郵件，其中的風險高於遺失合法電子郵件的風險。</span><span class="sxs-lookup"><span data-stu-id="c48be-538">Because of the impact of phishing attacks, and because email authentication has been around for over 15 years, Microsoft believes that the risk of continue to allow unauthenticated email is higher than the risk of losing legitimate email.</span></span>
  
### <a name="will-this-change-cause-legitimate-email-to-be-marked-as-spam"></a><span data-ttu-id="c48be-539">這項變更會造成合法的電子郵件被標示為垃圾郵件嗎？</span><span class="sxs-lookup"><span data-stu-id="c48be-539">Will this change cause legitimate email to be marked as spam?</span></span>

<span data-ttu-id="c48be-540">一開始會有一些郵件被標示為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="c48be-540">At first, there will be some messages that are marked as spam.</span></span> <span data-ttu-id="c48be-541">但是，一段時間後，寄件者將進行調整，然後對於大多數電子郵件路徑，錯誤標示詐騙的郵件數量可以忽略不計。</span><span class="sxs-lookup"><span data-stu-id="c48be-541">However, over time, senders will adjust and then the amount of messages mislabeled as spoofed will be negligible for most email paths.</span></span>
  
<span data-ttu-id="c48be-542">在將這項功能部署到其他客戶之前的幾週，Microsoft 本身先行採用了此功能。</span><span class="sxs-lookup"><span data-stu-id="c48be-542">Microsoft itself first adopted this feature several weeks before deploying it to the rest of its customers.</span></span> <span data-ttu-id="c48be-543">一開始會出現一些干擾，但慢慢的會減少。</span><span class="sxs-lookup"><span data-stu-id="c48be-543">While there was disruption at first, it gradually declined.</span></span>
  
### <a name="will-microsoft-bring-this-feature-to-outlookcom-and-non-advanced-threat-protection-customers-of-office-365"></a><span data-ttu-id="c48be-544">Microsoft 是否會將此功能提供給 Office 365 的 Outlook.com 和非進階威脅防護客戶？</span><span class="sxs-lookup"><span data-stu-id="c48be-544">Will Microsoft bring this feature to Outlook.com and non-Advanced Threat Protection customers of Office 365?</span></span>

<span data-ttu-id="c48be-545">Microsoft 的反詐騙技術最初部署在具有 Office 365 企業版 E5 訂閱，或已為其訂閱購買 Office 365 進階威脅防護 (ATP) 附加元件的組織中。</span><span class="sxs-lookup"><span data-stu-id="c48be-545">Microsoft's anti-spoofing technology was initially deployed to its organizations that had an Office 365 Enterprise E5 subscription or had purchased the Office 365 Advanced Threat Protection (ATP) add-on for their subscription.</span></span> <span data-ttu-id="c48be-546">自 2018 年 10 月起，我們已將防護擴充至擁有 Exchange Online Protection (EOP) 的組織中。</span><span class="sxs-lookup"><span data-stu-id="c48be-546">As of October, 2018 we've extended the protection to organizations that have Exchange Online Protection (EOP) as well.</span></span> <span data-ttu-id="c48be-547">未來，我們可能會發佈給 Outlook.com 使用。</span><span class="sxs-lookup"><span data-stu-id="c48be-547">In the future, we may release it for Outlook.com.</span></span> <span data-ttu-id="c48be-548">但是，如果我們這樣做，可能會有一些功能不適用，例如報告和自訂覆寫。</span><span class="sxs-lookup"><span data-stu-id="c48be-548">However, if we do, there may be some capabilities that are not applied such as reporting and custom overrides.</span></span>
  
### <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a><span data-ttu-id="c48be-549">如何向 Microsoft 回報垃圾郵件或非垃圾郵件？</span><span class="sxs-lookup"><span data-stu-id="c48be-549">How can I report spam or non-spam messages back to Microsoft?</span></span>

<span data-ttu-id="c48be-550">您可以使用 [Outlook 的回報郵件增益集](https://support.office.com/article/use-the-report-message-add-in-b5caa9f1-cdf3-4443-af8c-ff724ea719d2)，如果未安裝 Outlook，則可[將垃圾郵件，非垃圾郵件和網路釣魚詐騙郵件提交給 Microsoft 進行分析](https://technet.microsoft.com/zh-TW/library/jj200769%28v=exchg.150%29.aspx) (機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="c48be-550">You can either use the [Report Message Add-in for Outlook](https://support.office.com/article/use-the-report-message-add-in-b5caa9f1-cdf3-4443-af8c-ff724ea719d2), or if it isn't installed, [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](https://technet.microsoft.com/zh-TW/library/jj200769%28v=exchg.150%29.aspx).</span></span>
  
### <a name="im-a-domain-administrator-who-doesnt-know-who-all-my-senders-are"></a><span data-ttu-id="c48be-551">我是網域系統管理員，但我不認識所有寄件者！</span><span class="sxs-lookup"><span data-stu-id="c48be-551">I'm a domain administrator who doesn't know who all my senders are!</span></span>

<span data-ttu-id="c48be-552">請參閱[非 Office 365 客戶的網域系統管理員](#administrators-of-domains-that-are-not-office-365-customers)。</span><span class="sxs-lookup"><span data-stu-id="c48be-552">Please see [Administrators of domains that are not Office 365 customers](#administrators-of-domains-that-are-not-office-365-customers).</span></span>
  
### <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization-even-though-office-365-is-my-primary-filter"></a><span data-ttu-id="c48be-553">如果我為組織停用反詐騙防護會發生什麼情況，即使 Office 365 是我的主要篩選器？</span><span class="sxs-lookup"><span data-stu-id="c48be-553">What happens if I disable anti-spoofing protection for my organization, even though Office 365 is my primary filter?</span></span>

<span data-ttu-id="c48be-554">我們不建議這樣做，因為您將會暴露在更多未篩選出的網路釣魚及垃圾郵件中。</span><span class="sxs-lookup"><span data-stu-id="c48be-554">We do not recommend this because you will be exposed to more missed phishing and spam messages.</span></span> <span data-ttu-id="c48be-555">並非所有的網路釣魚都是詐騙，也不是所有詐騙郵件都會遺漏。</span><span class="sxs-lookup"><span data-stu-id="c48be-555">Not all phishing is spoofing, and not all spoofs will be missed.</span></span> <span data-ttu-id="c48be-556">不過，比起啟用反詐騙功能的客戶，您的風險較高。</span><span class="sxs-lookup"><span data-stu-id="c48be-556">However, your risk will be higher than a customer who enables anti-spoofing.</span></span>
  
### <a name="does-enabling-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a><span data-ttu-id="c48be-557">啟用反詐騙防護表示我都不會收到任何網路釣魚郵件嗎？</span><span class="sxs-lookup"><span data-stu-id="c48be-557">Does enabling anti-spoofing protection mean I will be protected from all phishing?</span></span>

<span data-ttu-id="c48be-558">很抱歉，不是這樣，因為網路釣魚者會因應使用其他技術，例如入侵帳戶或設定免費服務的帳戶。</span><span class="sxs-lookup"><span data-stu-id="c48be-558">Unfortunately, no, because phishers will adapt to use other techniques such as compromised accounts, or setting up accounts of free services.</span></span> <span data-ttu-id="c48be-559">但是，防網路釣魚防護在偵測這些其他類型的網路釣魚方法上效果更好，因為 Office 365 的保護層是設計成能相互配合運作，並環環相扣。</span><span class="sxs-lookup"><span data-stu-id="c48be-559">However, anti-phishing protection works much better to detect these other types of phishing methods because Office 365's protection layers are designed work together and build on top of each other.</span></span>
  
### <a name="do-other-large-email-receivers-block-unauthenticated-email"></a><span data-ttu-id="c48be-560">其他大型的電子郵件接收者會封鎖未經驗證的電子郵件嗎？</span><span class="sxs-lookup"><span data-stu-id="c48be-560">Do other large email receivers block unauthenticated email?</span></span>

<span data-ttu-id="c48be-561">幾乎所有的大型的電子郵件接收者都採用傳統的 SPF、DKIM 和 DMARC。</span><span class="sxs-lookup"><span data-stu-id="c48be-561">Nearly all large email receivers implement traditional SPF, DKIM, and DMARC.</span></span> <span data-ttu-id="c48be-562">有些接收者會進行比這些標準更嚴格的其他檢查，但很少會像Office 365 一樣能阻止未經驗證的電子郵件並將其視為詐騙郵件。</span><span class="sxs-lookup"><span data-stu-id="c48be-562">Some receivers have other checks that are more strict than just those standards, but few go as far as Office 365 to block unauthenticated email and treat them as a spoof.</span></span> <span data-ttu-id="c48be-563">不過，因為網路釣魚的問題，大部分產業對於這類特殊電子郵件的控制越來越嚴格。</span><span class="sxs-lookup"><span data-stu-id="c48be-563">However, most of the industry is becoming more and more strict about this particular type of email, particularly because of the problem of phishing.</span></span>
  
### <a name="do-i-still-need-the-advanced-spam-filtering-option-enabled-for-spf-hard-fail-if-i-enable-anti-spoofing"></a><span data-ttu-id="c48be-564">如果已啟用反詐騙功能，是否仍需要為「SPF 驗證失敗」啟用進階垃圾郵件篩選選項？</span><span class="sxs-lookup"><span data-stu-id="c48be-564">Do I still need the Advanced Spam Filtering option enabled for "SPF Hard Fail" if I enable anti-spoofing?</span></span>

<span data-ttu-id="c48be-565">不用，因為反詐騙功能不僅會考慮SPF 驗證失敗，還會考慮更廣泛的標準，所以不需再使用此選項。</span><span class="sxs-lookup"><span data-stu-id="c48be-565">No, this option is no longer required because the anti-spoofing feature not only considers SPF hard fails, but a much wider set of criteria.</span></span> <span data-ttu-id="c48be-566">如果同時啟用反詐騙功能和 SPF 驗證失敗選項，則可能會發生更多誤判。</span><span class="sxs-lookup"><span data-stu-id="c48be-566">If you have anti-spoofing enabled and the SPF Hard Fail option enabled, you will probably get more false positives.</span></span> <span data-ttu-id="c48be-567">我們建議您停用這項功能，因為它幾乎不會增加垃圾郵件或網路釣魚郵件的捕獲率，反而會產生更多誤判。</span><span class="sxs-lookup"><span data-stu-id="c48be-567">We recommend disabling this feature as it would provide almost no additional catch for spam or phish, and instead generate mostly false positives.</span></span>
  
### <a name="does-sender-rewriting-scheme-srs-help-fix-forwarded-email"></a><span data-ttu-id="c48be-568">寄件者重寫機制 (SRS) 是否有助於修復轉寄的電子郵件？</span><span class="sxs-lookup"><span data-stu-id="c48be-568">Does Sender Rewriting Scheme (SRS) help fix forwarded email?</span></span>

<span data-ttu-id="c48be-569">SRS 僅能修正轉寄電子郵件的部分問題。</span><span class="sxs-lookup"><span data-stu-id="c48be-569">SRS only partially fixes the problem of forwarded email.</span></span> <span data-ttu-id="c48be-570">透過重寫 SMTP MAIL FROM，SRS可以確保轉寄郵件能在下一個目的地通過 SPF。</span><span class="sxs-lookup"><span data-stu-id="c48be-570">By rewriting the SMTP MAIL FROM, SRS can ensure that the forwarded message passes SPF at the next destination.</span></span> <span data-ttu-id="c48be-571">但是，由於反詐騙功能會根據寄件者地址以及 MAIL FROM 或 DKIM 簽署網域 (或其他訊號)，因此不足以防止轉寄的電子郵件被標示為詐騙郵件。</span><span class="sxs-lookup"><span data-stu-id="c48be-571">However, because anti-spoofing is based upon the From: address in combination with either the MAIL FROM or DKIM-signing domain (or other signals), it is not enough to prevent forwarded email from being marked as spoofed.</span></span>