---
title: Office 365 的反詐騙保護
ms.author: tracyp
author: MSFTtracyp
manager: laurawi
ms.date: 3/6/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: d24bb387-c65d-486e-93e7-06a4f1a436c0
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: 本文說明 Office 365 如何減少抵禦網路釣魚攻擊使用偽造地址寄件者的網域，亦即詐騙的網域。 它這樣的優勢分析郵件，並封鎖該組可驗證不使用標準的電子郵件的驗證方法或其他寄件者信譽技術。 這項變更所實作，以減少要公開在 Office 365 組織的網路釣魚攻擊的數目。
ms.openlocfilehash: 377bc75e7538dacab1180045ddfdeb1a2ac32a65
ms.sourcegitcommit: 5eb664b6ecef94aef4018a75684ee4ae66c486bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/08/2019
ms.locfileid: "30492872"
---
# <a name="anti-spoofing-protection-in-office-365"></a><span data-ttu-id="15813-105">Office 365 的反詐騙保護</span><span class="sxs-lookup"><span data-stu-id="15813-105">Anti-spoofing protection in Office 365</span></span>

<span data-ttu-id="15813-106">本文說明 Office 365 如何減少抵禦網路釣魚攻擊使用偽造地址寄件者的網域，亦即詐騙的網域。</span><span class="sxs-lookup"><span data-stu-id="15813-106">This article describes how Office 365 mitigates against phishing attacks that use forged sender domains, that is, domains that are spoofed.</span></span> <span data-ttu-id="15813-107">完成其這分析郵件，並封鎖不能使用標準的電子郵件的驗證方法或其他寄件者信譽技術驗證項目。</span><span class="sxs-lookup"><span data-stu-id="15813-107">It accomplishes this by analyzing the messages and blocking the ones that cannot be authenticated using standard email authentication methods, nor other sender reputation techniques.</span></span> <span data-ttu-id="15813-108">這項變更所實作，以減少要公開在 Office 365 組織的網路釣魚攻擊的數目。</span><span class="sxs-lookup"><span data-stu-id="15813-108">This change was implemented to reduce the number of phishing attacks to which organizations in Office 365 are exposed.</span></span>
  
<span data-ttu-id="15813-109">本文也說明為何要進行此變更，客戶可以如何準備，這項變更、 如何檢視將會受到影響的郵件、 如何報告的郵件、 如何減輕誤判，，以及給 Microsoft 的寄件者應如何準備進行這變更。</span><span class="sxs-lookup"><span data-stu-id="15813-109">This article also describes why this change is being made, how customers can prepare for this change, how to view messages that will be affected, how to report on messages, how to mitigate false positives, as well as how senders to Microsoft should prepare for this change.</span></span>
  
<span data-ttu-id="15813-110">Microsoft 的反詐騙技術最初部署給其組織有 Office 365 企業版 E5 訂閱，或有購買其訂閱的 Office 365 進階威脅防護 (ATP) 附加元件。</span><span class="sxs-lookup"><span data-stu-id="15813-110">Microsoft's anti-spoofing technology was initially deployed to its organizations that had an Office 365 Enterprise E5 subscription or had purchased the Office 365 Advanced Threat Protection (ATP) add-on for their subscription.</span></span> <span data-ttu-id="15813-111">2018 年 10 月日起我們延伸也有 Exchange Online Protection (EOP) 的組織的保護。</span><span class="sxs-lookup"><span data-stu-id="15813-111">As of October, 2018 we extended the protection to organizations that have Exchange Online Protection (EOP) as well.</span></span> <span data-ttu-id="15813-112">此外，因為我們的篩選器的所有要深入了解從彼此的方式，Outlook.com 使用者可能會影響。</span><span class="sxs-lookup"><span data-stu-id="15813-112">Additionally, because of the way all of our filters learn from each other, Outlook.com users may also be affected.</span></span>
  
## <a name="how-spoofing-is-used-in-phishing-attacks"></a><span data-ttu-id="15813-113">在 [網路釣魚攻擊的詐騙使用方式</span><span class="sxs-lookup"><span data-stu-id="15813-113">How spoofing is used in phishing attacks</span></span>

<span data-ttu-id="15813-114">保護其使用者時，Microsoft 會嚴重採用網路釣魚的威脅。</span><span class="sxs-lookup"><span data-stu-id="15813-114">When it comes to protecting its users, Microsoft takes the threat of phishing seriously.</span></span> <span data-ttu-id="15813-115">濫發垃圾郵件者和網路釣客常使用的技術的其中一個在詐騙，這當寄件者為偽造地址，且郵件似乎來自是由其他人或地方以外的實際的來源。</span><span class="sxs-lookup"><span data-stu-id="15813-115">One of the techniques that spammers and phishers commonly use is spoofing, which is when the sender is forged, and a message appears to originate from someone or somewhere other than the actual source.</span></span> <span data-ttu-id="15813-116">這個方法通常用於網路釣魚活動設計用來取得使用者認證。</span><span class="sxs-lookup"><span data-stu-id="15813-116">This technique is often used in phishing campaigns designed to obtain user credentials.</span></span> <span data-ttu-id="15813-117">Microsoft 的反詐騙技術特別會檢查冒名的 '從： 標頭' 也就是在類似 Outlook 電子郵件用戶端中會顯示一個。</span><span class="sxs-lookup"><span data-stu-id="15813-117">Microsoft's Anti-spoof technology specifically examines forgery of the 'From: header' which is the one that shows up in an email client like Outlook.</span></span> <span data-ttu-id="15813-118">當 Microsoft 具有高信賴度的 From： 標頭為冒名，它會識別為詐騙郵件。</span><span class="sxs-lookup"><span data-stu-id="15813-118">When Microsoft has high confidence that the From: header is spoofed, it identifies the message as a spoof.</span></span>
  
<span data-ttu-id="15813-119">詐騙郵件影響兩個負的實際使用者：</span><span class="sxs-lookup"><span data-stu-id="15813-119">Spoofing messages have two negative implications for real life users:</span></span>
  
### <a name="1-spoofed-messages-deceive-users"></a><span data-ttu-id="15813-120">1.冒名郵件惡作劇使用者</span><span class="sxs-lookup"><span data-stu-id="15813-120">1. Spoofed messages deceive users</span></span>
  
<span data-ttu-id="15813-121">首先，冒名的郵件可能誘騙使用者按一下連結及放棄其認證、 下載惡意程式碼，或回覆郵件具有敏感內容 （後者的一種稱為 「 商務電子郵件危害）。</span><span class="sxs-lookup"><span data-stu-id="15813-121">First, a spoofed message may trick a user into clicking a link and giving up their credentials, downloading malware, or replying to a message with sensitive content (the latter of which is known as Business Email Compromise).</span></span> <span data-ttu-id="15813-122">例如，以下是 msoutlook94@service.outlook.com 冒名寄件者的網路釣魚郵件：</span><span class="sxs-lookup"><span data-stu-id="15813-122">For example, the following is a phishing message with a spoofed sender of msoutlook94@service.outlook.com:</span></span>
  
![模擬 service.outlook.com 網路釣魚郵件](media/1a441f21-8ef7-41c7-90c0-847272dc5350.jpg)
  
<span data-ttu-id="15813-124">上述並非真的來自 service.outlook.com，但改為已讓它看起來像它並未 phisher 詐騙。</span><span class="sxs-lookup"><span data-stu-id="15813-124">The above did not actually come from service.outlook.com, but instead was spoofed by the phisher to make it look like it did.</span></span> <span data-ttu-id="15813-125">它會嘗試誘騙使用者按一下郵件中的連結。</span><span class="sxs-lookup"><span data-stu-id="15813-125">It is attempting to trick a user into clicking the link within the message.</span></span>
  
<span data-ttu-id="15813-126">下一個範例詐騙 contoso.com:</span><span class="sxs-lookup"><span data-stu-id="15813-126">The next example is spoofing contoso.com:</span></span>
  
![網路釣魚郵件-商業電子郵件遭到入侵](media/da15adaa-708b-4e73-8165-482fc9182090.jpg)
  
<span data-ttu-id="15813-128">郵件看起來合法的但事實上詐騙。</span><span class="sxs-lookup"><span data-stu-id="15813-128">The message looks legitimate, but in fact is a spoof.</span></span> <span data-ttu-id="15813-129">此網路釣魚郵件是一種商業電子郵件危害也就是網路釣魚的子類別。</span><span class="sxs-lookup"><span data-stu-id="15813-129">This phishing message is a type of Business Email Compromise which is a subcategory of phishing.</span></span>

### <a name="2-users-confuse-real-messages-for-fake-ones"></a><span data-ttu-id="15813-130">2.使用者混淆假的實際的郵件</span><span class="sxs-lookup"><span data-stu-id="15813-130">2. Users confuse real messages for fake ones</span></span>
  
<span data-ttu-id="15813-131">第二個、 詐騙郵件建立不確定使用者了解網路釣魚郵件，但無法判斷實際的郵件和詐騙的一之間的差異。</span><span class="sxs-lookup"><span data-stu-id="15813-131">Second, spoofed messages create uncertainty for users who know about phishing messages but cannot tell the difference between a real message and spoofed one.</span></span> <span data-ttu-id="15813-132">例如，以下是從 Microsoft 安全性帳戶的電子郵件地址重設實際密碼的範例：</span><span class="sxs-lookup"><span data-stu-id="15813-132">For example, the following is an example of an actual password reset from the Microsoft Security account email address:</span></span>
  
![Microsoft 合法的密碼重設](media/58a3154f-e83d-4f86-bcfe-ae9e8c87bd37.jpg)
  
<span data-ttu-id="15813-134">上述的訊息沒有來自 Microsoft，但在此同時，使用者會用來取得網路釣魚郵件可能誘騙使用者按一下連結及放棄其認證、 下載惡意程式碼，或回覆郵件具有敏感內容。</span><span class="sxs-lookup"><span data-stu-id="15813-134">The above message did come from Microsoft, but at the same time, users are used to getting phishing messages that may trick a user into clicking a link and giving up their credentials, downloading malware, or replying to a message with sensitive content.</span></span> <span data-ttu-id="15813-135">因為很難分辨實際的密碼重設與假的一個之間的差異，許多使用者略過這些郵件、 它們回報為垃圾郵件，或不必要地回向 Microsoft 回報郵件為未接的網路釣魚詐騙。</span><span class="sxs-lookup"><span data-stu-id="15813-135">Because it is difficult to tell the difference between a real password reset and a fake one, many users ignore these messages, report them as spam, or unnecessarily report the messages back to Microsoft as missed phishing scams.</span></span>

<span data-ttu-id="15813-136">若要停止詐騙，電子郵件篩選產業已開發的電子郵件的驗證通訊協定，例如[SPF](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)， [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)、 [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)。</span><span class="sxs-lookup"><span data-stu-id="15813-136">To stop spoofing, the email filtering industry has developed email authentication protocols such as [SPF](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing), [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email), and [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email).</span></span> <span data-ttu-id="15813-137">DMARC 可防止詐騙檢查郵件的寄件者的使用者會看到其電子郵件用戶端中的一個 （在上述範例中，這是 service.outlook.com、 outlook.com 和 accountprotection.microsoft.com）-通過 SPF 或 DKIM 的網域。</span><span class="sxs-lookup"><span data-stu-id="15813-137">DMARC prevents spoofing examining a message's sender - the one that the user sees in their email client (in the examples above, this is service.outlook.com, outlook.com, and accountprotection.microsoft.com) - with the domain that passed SPF or DKIM.</span></span> <span data-ttu-id="15813-138">也就是說，使用者會看到的網域已經過驗證，因此不詐騙郵件。</span><span class="sxs-lookup"><span data-stu-id="15813-138">That is, the domain that the user sees has been authenticated and is therefore not spoofed.</span></span> <span data-ttu-id="15813-139">如需更完整的討論，請參閱一節 「*了解為什麼電子郵件驗證不一定足以停止詐騙 」* 本文稍後。</span><span class="sxs-lookup"><span data-stu-id="15813-139">For a more complete discussion, see the section "*Understanding why email authentication is not always enough to stop spoofing"*  later on in this article.</span></span>
  
<span data-ttu-id="15813-140">不過，這個問題是記錄是選擇性的不需要該電子郵件驗證。</span><span class="sxs-lookup"><span data-stu-id="15813-140">However, the problem is that email authentication records are optional, not required.</span></span> <span data-ttu-id="15813-141">因此，當網域嚴密的驗證原則與 like microsoft.com 和 skype.com 保護來自詐騙網域的所有發佈弱的驗證原則或任何原則、 為詐騙的目標。截至年 3 月 2018年僅 9%的網域的公司中 Fortune 500 發佈強式電子郵件驗證原則。</span><span class="sxs-lookup"><span data-stu-id="15813-141">Therefore, while domains with strong authentication policies like microsoft.com and skype.com are protected from spoofing, domains that publish weaker authentication policies, or no policy at all, are targets for being spoofed.As of March 2018, only 9% of domains of companies in the Fortune 500 publish strong email authentication policies.</span></span> <span data-ttu-id="15813-142">剩餘 91%可能遭到假冒的 phisher 和除非電子郵件篩選器偵測到使用其他原則，它可能會傳遞至使用者欺騙它們：</span><span class="sxs-lookup"><span data-stu-id="15813-142">The remaining 91% may be spoofed by a phisher, and unless the email filter detects it using another policy, may be delivered to an end user and deceive them:</span></span>
  
![Fortune 500 公司的 DMARC 原則](media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)
  
<span data-ttu-id="15813-144">小型至中型大小公司的比例不在發佈強式電子郵件驗證原則 Fortune 500 為較小，和小仍為 「 北美地區 」 及西歐外的網域。</span><span class="sxs-lookup"><span data-stu-id="15813-144">The proportion of small-to-medium sized companies that are not in the Fortune 500 that publish strong email authentication policies is smaller, and smaller still for domains that are outside of North America and western Europe.</span></span>
  
<span data-ttu-id="15813-145">因為網路釣客雖然企業可能不知道電子郵件驗證的運作方式，執行了解，並利用缺乏，這會是大的問題。</span><span class="sxs-lookup"><span data-stu-id="15813-145">This is a big problem because while enterprises may not be aware of how email authentication works, phishers do understand and take advantage of the lack of it.</span></span>
  
<span data-ttu-id="15813-146">設定 SPF，DKIM、 DMARC 的詳細資訊，請參閱 [] 區段中 「 更新版本文件中的*客戶的 Office 365 」* 。</span><span class="sxs-lookup"><span data-stu-id="15813-146">For information on setting up SPF, DKIM, and DMARC, see the section "*Customers of Office 365"*  later on in this document.</span></span> 
  
## <a name="stopping-spoofing-with-implicit-email-authentication"></a><span data-ttu-id="15813-147">停止使用隱含的電子郵件驗證詐騙</span><span class="sxs-lookup"><span data-stu-id="15813-147">Stopping spoofing with implicit email authentication</span></span>

<span data-ttu-id="15813-148">因為網路釣魚和矛網路釣魚這類問題，且強式電子郵件驗證原則限制的採用，因為 Microsoft 會繼續投入來保護其客戶的功能。</span><span class="sxs-lookup"><span data-stu-id="15813-148">Because phishing and spear phishing is such a problem, and because of the limited adoption of strong email authentication policies, Microsoft continues to invest in capabilities to protect its customers.</span></span> <span data-ttu-id="15813-149">因此，Microsoft 向前移動使用*隱含的電子郵件驗證*-如果網域不會驗證，Microsoft 會將它視為它有發佈電子郵件驗證記錄並且將它視為據此如果它不會傳遞。</span><span class="sxs-lookup"><span data-stu-id="15813-149">Therefore, Microsoft is moving ahead with  *implicit email authentication* - if a domain doesn't authenticate, Microsoft will treat it as if it had published email authentication records and treat it accordingly if it doesn't pass.</span></span> 
  
<span data-ttu-id="15813-150">若要這麼做，Microsoft 已內建許多一般的電子郵件的驗證，包括寄件者信譽、 寄件者/收件者歷程記錄、 行為分析和其他進階的技術擴充功能。</span><span class="sxs-lookup"><span data-stu-id="15813-150">To accomplish this, Microsoft has built numerous extensions to regular email authentication including sender reputation, sender/recipient history, behavioral analysis, and other advanced techniques.</span></span> <span data-ttu-id="15813-151">寄件者不會發佈電子郵件驗證網域的郵件會被標示為詐騙除非它包含其他信號表示它是合法。</span><span class="sxs-lookup"><span data-stu-id="15813-151">A message sent from a domain that doesn't publish email authentication will be marked as spoof unless it contains other signals to indicate that it is legitimate.</span></span>
  
<span data-ttu-id="15813-152">如此一來，使用者可的結束電子郵件傳送給它們不被冒名的信賴度，寄件者可以放心人模擬其網域和 Office 365 客戶可以提供更好的防護，如模擬保護。</span><span class="sxs-lookup"><span data-stu-id="15813-152">By doing this, end users can have confidence that an email sent to them has not been spoofed, senders can be confident that nobody is impersonating their domain, and customers of Office 365 can offer even better protection such as Impersonation protection.</span></span>
  
<span data-ttu-id="15813-153">若要查看 Microsoft 的一般宣告，請參閱 < <b0>Sea 的 Phish 第 2 部分-Office 365 中增強反詐騙</b0>。</span><span class="sxs-lookup"><span data-stu-id="15813-153">To see Microsoft's general announcement, see [A Sea of Phish Part 2 - Enhanced Anti-spoofing in Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).</span></span>
  
## <a name="identifying-that-a-message-is-classified-as-spoofed"></a><span data-ttu-id="15813-154">識別郵件分類為詐騙</span><span class="sxs-lookup"><span data-stu-id="15813-154">Identifying that a message is classified as spoofed</span></span>

### <a name="composite-authentication"></a><span data-ttu-id="15813-155">複合驗證</span><span class="sxs-lookup"><span data-stu-id="15813-155">Composite authentication</span></span>

<span data-ttu-id="15813-156">雖然 SPF，DKIM、 DMARC 自行都很有用，它們不在事件訊息有無明確驗證記錄通訊不足，無法驗證狀態。</span><span class="sxs-lookup"><span data-stu-id="15813-156">While SPF, DKIM, and DMARC are all useful by themselves, they don't communicate enough authentication status in the event a message has no explicit authentication records.</span></span> <span data-ttu-id="15813-157">因此，Microsoft 已開發的演算法，將多個訊號結合成複合式驗證或 compauth 呼叫簡稱為單一值。</span><span class="sxs-lookup"><span data-stu-id="15813-157">Therefore, Microsoft has developed an algorithm that combines multiple signals into a single value called Composite Authentication, or compauth for short.</span></span> <span data-ttu-id="15813-158">在 Office 365 的客戶有 compauth 值戳印在郵件標頭中的*Authentication-results*標頭。</span><span class="sxs-lookup"><span data-stu-id="15813-158">Customers in Office 365 have compauth values stamped into the *Authentication-Results* header in the message headers.</span></span> 
  
```
Authentication-Results:
  compauth=<fail|pass|softpass|none> reason=<yyy>

```

|<span data-ttu-id="15813-159">**CompAuth 結果**</span><span class="sxs-lookup"><span data-stu-id="15813-159">**CompAuth result**</span></span>|<span data-ttu-id="15813-160">**描述**</span><span class="sxs-lookup"><span data-stu-id="15813-160">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="15813-161">失敗</span><span class="sxs-lookup"><span data-stu-id="15813-161">fail</span></span>|<span data-ttu-id="15813-162">郵件無法明確驗證 （傳送網域發佈記錄明確地在 DNS 中） 或隱含驗證 （傳送網域沒有不發佈記錄在 DNS 中，讓 Office 365 內插結果好像它已發佈的記錄）。</span><span class="sxs-lookup"><span data-stu-id="15813-162">Message failed explicit authentication (sending domain published records explicitly in DNS) or implicit authentication (sending domain did not publish records in DNS, so Office 365 interpolated the result as if it had published records).</span></span>|
|<span data-ttu-id="15813-163">傳遞</span><span class="sxs-lookup"><span data-stu-id="15813-163">pass</span></span>|<span data-ttu-id="15813-164">郵件傳遞明確驗證 （郵件通過 DMARC 或[最佳猜測通過 DMARC](https://blogs.msdn.microsoft.com/tzink/2015/05/06/what-is-dmarc-bestguesspass-in-office-365)） 或具有高信賴度隱含驗證 （傳送網域不會發佈電子郵件驗證記錄，但 Office 365 具有強式的後端訊號，以指出郵件為可能合法)。</span><span class="sxs-lookup"><span data-stu-id="15813-164">Message passed explicit authentication (message passed DMARC, or [Best Guess Passed DMARC](https://blogs.msdn.microsoft.com/tzink/2015/05/06/what-is-dmarc-bestguesspass-in-office-365)) or implicit authentication with high confidence (sending domain does not publish email authentication records, but Office 365 has strong backend signals to indicate the message is likely legitimate).</span></span>|
|<span data-ttu-id="15813-165">softpass</span><span class="sxs-lookup"><span data-stu-id="15813-165">softpass</span></span>|<span data-ttu-id="15813-166">郵件傳遞隱含的驗證與低-中型信賴 （傳送網域不會發佈電子郵件驗證，但 Office 365 後端訊號，以指出郵件為合法但弱的訊號的強度）。</span><span class="sxs-lookup"><span data-stu-id="15813-166">Message passed implicit authentication with low-to-medium confidence (sending domain does not publish email authentication, but Office 365 has backend signals to indicate the message is legitimate but the strength of the signal is weaker).</span></span>|
|<span data-ttu-id="15813-167">無</span><span class="sxs-lookup"><span data-stu-id="15813-167">none</span></span>|<span data-ttu-id="15813-168">未先驗證訊息 （或未驗證，但未對齊），但由於寄件者信譽或其他因素而不會套用複合驗證。</span><span class="sxs-lookup"><span data-stu-id="15813-168">Message did not authenticate (or it did authenticate but did not align), but composite authentication not applied due to sender reputation or other factors.</span></span>|
   
|||
|:-----|:-----|
|<span data-ttu-id="15813-169">**原因**</span><span class="sxs-lookup"><span data-stu-id="15813-169">**Reason**</span></span>|<span data-ttu-id="15813-170">**描述**</span><span class="sxs-lookup"><span data-stu-id="15813-170">**Description**</span></span>|
|<span data-ttu-id="15813-171">0xx</span><span class="sxs-lookup"><span data-stu-id="15813-171">0xx</span></span>|<span data-ttu-id="15813-172">複合驗證失敗訊息。</span><span class="sxs-lookup"><span data-stu-id="15813-172">Message failed composite authentication.</span></span><br/><span data-ttu-id="15813-173">**000**表示郵件無法以拒絕或隔離] 動作的 DMARC。</span><span class="sxs-lookup"><span data-stu-id="15813-173">**000** means the message failed DMARC with an action of reject or quarantine.</span></span>  <br/><span data-ttu-id="15813-174">**001**表示郵件無法隱含的電子郵件驗證。</span><span class="sxs-lookup"><span data-stu-id="15813-174">**001** means the message failed implicit email authentication.</span></span> <span data-ttu-id="15813-175">這表示在傳送網域沒有不會發佈，電子郵件驗證記錄或者一樣，如果他們有弱的失敗原則 (SPF fail 或 neutral，DMARC 原則的 p = 無)。</span><span class="sxs-lookup"><span data-stu-id="15813-175">This means that the sending domain did not have email authentication records published, or if they did, they had a weaker failure policy (SPF soft fail or neutral, DMARC policy of p=none).</span></span>  <br/><span data-ttu-id="15813-176">**002**表示該組織有明確禁止傳送冒名的電子郵件的寄件者/網域組的原則，系統管理員手動設定此設定。</span><span class="sxs-lookup"><span data-stu-id="15813-176">**002** means the organization has a policy for the sender/domain pair that is explicitly prohibited from sending spoofed email, this setting is manually set by an administrator.</span></span>  <br/><span data-ttu-id="15813-177">**010**表示郵件無法使用拒絕或隔離，巨集指令的 DMARC，並在傳送網域是下列其中一個貴組織的公認的網域 (這是 self-self 或組織內部的一部分詐騙)。</span><span class="sxs-lookup"><span data-stu-id="15813-177">**010** means the message failed DMARC with an action of reject or quarantine, and the sending domain is one of your organization's accepted-domains (this is part of self-to-self, or intra-org, spoofing).</span></span>  <br/><span data-ttu-id="15813-178">**011**表示郵件無法通過隱含的電子郵件的驗證，並在傳送網域是下列其中一個貴組織的公認的網域 (這是 self-self 或組織內部的一部分詐騙)。</span><span class="sxs-lookup"><span data-stu-id="15813-178">**011** means the message failed implicit email authentication, and the sending domain is one of your organization's accepted domains (this is part of self-to-self, or intra-org, spoofing).</span></span>|
|<span data-ttu-id="15813-179">所有其他代碼 （1xx、 2xx、 3xx、 4xx、 5xx）</span><span class="sxs-lookup"><span data-stu-id="15813-179">All other codes (1xx, 2xx, 3xx, 4xx, 5xx)</span></span>|<span data-ttu-id="15813-180">對應至各種內部代碼的郵件傳遞隱含驗證，或不有任何驗證，但沒有巨集指令所套用的原因。</span><span class="sxs-lookup"><span data-stu-id="15813-180">Corresponds to various internal codes for why a message passed implicit authentication, or had no authentication but no action was applied.</span></span>|
   
<span data-ttu-id="15813-181">查看郵件的標頭，以系統管理員或甚至是使用者可以決定 Office 365 到達結束時可能遭到假冒寄件者的方式。</span><span class="sxs-lookup"><span data-stu-id="15813-181">By looking at the headers of a message, an administrator or even an end user can determine how Office 365 arrives at the conclusion that the sender may be spoofed.</span></span>
  
### <a name="differentiating-between-different-types-of-spoofing"></a><span data-ttu-id="15813-182">區別不同類型的詐騙</span><span class="sxs-lookup"><span data-stu-id="15813-182">Differentiating between different types of spoofing</span></span>

<span data-ttu-id="15813-183">Microsoft 區分兩種不同類型的詐騙郵件：</span><span class="sxs-lookup"><span data-stu-id="15813-183">Microsoft differentiates between two different types of spoofing messages:</span></span>
  
 <span data-ttu-id="15813-184">**組織內部詐騙**</span><span class="sxs-lookup"><span data-stu-id="15813-184">**Intra-org spoofing**</span></span>
  
<span data-ttu-id="15813-185">也稱為自助-自助詐騙，發生這種情況時的網域，在 [從： 地址相同，或是配合收件者網域 （當收件者網域是下列其中一個貴組織的[公認的網域](https://technet.microsoft.com/en-us/library/jj945194%28v=exchg.150%29.aspx)）;或者，當在 [從網域： 地址是相同的組織的一部分。</span><span class="sxs-lookup"><span data-stu-id="15813-185">Also known as self-to-self spoofing, this occurs when the domain in the From: address is the same as, or aligns with, the recipient domain (when recipient domain is one of your organization's [Accepted Domains](https://technet.microsoft.com/en-us/library/jj945194%28v=exchg.150%29.aspx)); or, when the domain in the From: address is part of the same organization.</span></span>
  
<span data-ttu-id="15813-186">例如，下列寄件者和收件者從具有相同的網域 (contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="15813-186">For example, the following has sender and recipient from the same domain (contoso.com).</span></span> <span data-ttu-id="15813-187">空格插入可防止特色收集在此頁面上的電子郵件地址）：</span><span class="sxs-lookup"><span data-stu-id="15813-187">Spaces are inserted into the email address to prevent spambot harvesting on this page):</span></span>
  
<span data-ttu-id="15813-188">從： 寄件者 @ contoso.com</span><span class="sxs-lookup"><span data-stu-id="15813-188">From: sender @ contoso.com</span></span>
  
<span data-ttu-id="15813-189">收件者： 收件者 @ contoso.com</span><span class="sxs-lookup"><span data-stu-id="15813-189">To: recipient @ contoso.com</span></span>
  
<span data-ttu-id="15813-190">下列具有對齊與組織的網域 (fabrikam.com) 的寄件者和收件者網域：</span><span class="sxs-lookup"><span data-stu-id="15813-190">The following has the sender and recipient domains aligning with the organizational domain (fabrikam.com):</span></span>
  
<span data-ttu-id="15813-191">從： 寄件者 @ foo.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="15813-191">From: sender @ foo.fabrikam.com</span></span>
  
<span data-ttu-id="15813-192">收件者： 收件者 @ bar.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="15813-192">To: recipient @ bar.fabrikam.com</span></span>
  
<span data-ttu-id="15813-193">下列的寄件者和收件者網域是不同 （microsoft.com 和 bing.com），但他們都屬於相同的組織 （亦即，同時屬於組織的公認的網域）：</span><span class="sxs-lookup"><span data-stu-id="15813-193">The following sender and recipient domains are different (microsoft.com and bing.com), but they belong to the same organization (that is, both are part of the organization's Accepted Domains):</span></span>
  
<span data-ttu-id="15813-194">從： 寄件者 @ microsoft.com</span><span class="sxs-lookup"><span data-stu-id="15813-194">From: sender @ microsoft.com</span></span>
  
<span data-ttu-id="15813-195">收件者： 收件者 @ bing.com</span><span class="sxs-lookup"><span data-stu-id="15813-195">To: recipient @ bing.com</span></span>
  
<span data-ttu-id="15813-196">無法通過組織內部詐騙郵件包含標頭中的下列值：</span><span class="sxs-lookup"><span data-stu-id="15813-196">Messages that fail intra-org spoofing contain the following values in the headers:</span></span>
  
<span data-ttu-id="15813-197">X Forefront-反垃圾郵件報告:...]CAT:SPM/HSPM/PHSH;...]SFTY:9.11</span><span class="sxs-lookup"><span data-stu-id="15813-197">X-Forefront-Antispam-Report: ...CAT:SPM/HSPM/PHSH;...SFTY:9.11</span></span>
  
<span data-ttu-id="15813-198">CAT is 的郵件類別和它通常加上戳記，做為 SPM （垃圾郵件），但有時會是 HSPM （高信賴度垃圾郵件） 或釣魚程式 （網路釣魚） 取決於哪些其他類型的模式中可能發生郵件。</span><span class="sxs-lookup"><span data-stu-id="15813-198">The CAT is the category of the message, and it is normally stamped as SPM (spam), but occasionally may be HSPM (high confidence spam) or PHISH (phishing) depending upon what other types of patterns occur in the message.</span></span>
  
<span data-ttu-id="15813-199">SFTY 是郵件的安全層級、 第一個數字 (9) 表示郵件是網路釣魚，而第二組數字後點 (11) 表示它是組織內部詐騙。</span><span class="sxs-lookup"><span data-stu-id="15813-199">The SFTY is the safety level of the message, the first digit (9) means the message is phishing, and second set of digits after the dot (11) means it is intra-org spoofing.</span></span>
  
<span data-ttu-id="15813-200">沒有特殊原因程式碼的組織內部詐騙，將會加上戳記稍後 2018 （時間表尚未定義） 的複合驗證。</span><span class="sxs-lookup"><span data-stu-id="15813-200">There is no specific reason code for Composite Authentication for intra-org spoofing, that will be stamped later in 2018 (timeline not yet defined).</span></span>
  
 <span data-ttu-id="15813-201">**跨網域詐騙**</span><span class="sxs-lookup"><span data-stu-id="15813-201">**Cross-domain spoofing**</span></span>
  
<span data-ttu-id="15813-202">發生這種情況時傳送的網域，在 [從： 地址是在接收組織外部網域。</span><span class="sxs-lookup"><span data-stu-id="15813-202">This occurs when the sending domain in the From: address is an external domain to the receiving organization.</span></span> <span data-ttu-id="15813-203">由於跨網域詐騙失敗複合驗證的訊息包含標頭中的下列值：</span><span class="sxs-lookup"><span data-stu-id="15813-203">Messages that fail Composite Authentication due to cross-domain spoofing contain the following values in the headers:</span></span>
  
<span data-ttu-id="15813-204">驗證結果:...]</span><span class="sxs-lookup"><span data-stu-id="15813-204">Authentication-Results: …</span></span> <span data-ttu-id="15813-205">compauth = 失敗原因 = 000/001</span><span class="sxs-lookup"><span data-stu-id="15813-205">compauth=fail reason=000/001</span></span>
  
<span data-ttu-id="15813-206">X Forefront-反垃圾郵件報告:...]CAT:SPOOF;...]SFTY:9.22</span><span class="sxs-lookup"><span data-stu-id="15813-206">X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.22</span></span>
  
<span data-ttu-id="15813-207">在這兩種情況下，下列的紅色的安全提示中加上訊息或自訂收件者的信箱語言為對等項目：</span><span class="sxs-lookup"><span data-stu-id="15813-207">In both cases, the following red safety tip is stamped in the message, or an equivalent that is customized to the recipient mailbox's language:</span></span>
  
![紅色的安全提示-詐騙偵測](media/a366156a-14e8-4c14-bfe5-2031b21936f8.jpg)
  
<span data-ttu-id="15813-209">它是只透過查看 [從： 地址和知道您收件者的電子郵件的，或藉由檢查的電子郵件標頭，就能區分組織內部及跨網域詐騙。</span><span class="sxs-lookup"><span data-stu-id="15813-209">It's only by looking at the From: address and knowing what your recipient email is, or by inspecting the email headers, that you can differentiate between intra-org and cross-domain spoofing.</span></span>
  
## <a name="how-customers-of-office-365-can-prepare-themselves-for-the-new-anti-spoofing-protection"></a><span data-ttu-id="15813-210">如何的 Office 365 客戶可以自行為準備新的反詐騙保護</span><span class="sxs-lookup"><span data-stu-id="15813-210">How customers of Office 365 can prepare themselves for the new anti-spoofing protection</span></span>

### <a name="information-for-administrators"></a><span data-ttu-id="15813-211">系統管理員的資訊</span><span class="sxs-lookup"><span data-stu-id="15813-211">Information for administrators</span></span>

<span data-ttu-id="15813-212">以在 Office 365 組織的系統管理員身分，有數個關鍵您應該要知道的資訊。</span><span class="sxs-lookup"><span data-stu-id="15813-212">As an administrator of an organization in Office 365, there are several key pieces of information you should be aware of.</span></span>
  
### <a name="understanding-why-email-authentication-is-not-always-enough-to-stop-spoofing"></a><span data-ttu-id="15813-213">了解為什麼電子郵件驗證不一定足以停止詐騙</span><span class="sxs-lookup"><span data-stu-id="15813-213">Understanding why email authentication is not always enough to stop spoofing</span></span>

<span data-ttu-id="15813-214">新的反詐騙保護依賴電子郵件驗證 （SPF、 DKIM 和 DMARC） 未將郵件標記為詐騙。</span><span class="sxs-lookup"><span data-stu-id="15813-214">The new anti-spoofing protection relies on email authentication (SPF, DKIM, and DMARC) to not mark a message as spoofing.</span></span> <span data-ttu-id="15813-215">常見的範例時，傳送網域永遠不會發佈 SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="15813-215">A common example is when a sending domain has never published SPF records.</span></span> <span data-ttu-id="15813-216">如果沒有任何 SPF 記錄或者他們不正確地設定，已傳送的郵件會被標示為冒名除非 Microsoft 具有指出郵件為合法的後端智慧。</span><span class="sxs-lookup"><span data-stu-id="15813-216">If there are no SPF records or they are incorrectly set up, a sent message will be marked as spoofed unless Microsoft has back-end intelligence that says the message is legitimate.</span></span>
  
<span data-ttu-id="15813-217">例如之前反詐騙要部署，, 郵件可能會看起來與沒有 SPF 記錄，沒有 DKIM 的記錄，並無的 DMARC 記錄下列：</span><span class="sxs-lookup"><span data-stu-id="15813-217">For example, prior to anti-spoofing being deployed, a message may have looked like the following with no SPF record, no DKIM record, and no DMARC record:</span></span> 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```
<span data-ttu-id="15813-218">之後反詐騙，如果您有 Office 365 企業版 E5、 EOP 或 ATP，compauth 值會加上戳記：</span><span class="sxs-lookup"><span data-stu-id="15813-218">After anti-spoofing, if you have Office 365 Enterprise E5, EOP, or ATP, the compauth value is stamped:</span></span>
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com; compauth=fail reason=001
From: sender @ example.com
To: receiver @ contoso.com

```

<span data-ttu-id="15813-219">如果 example.com 會修正這藉由設定 SPF 記錄，但不是 DKIM 記錄，這就會通過複合驗證，因為傳遞 SPF 網域對齊的網域，在 [從： 地址：</span><span class="sxs-lookup"><span data-stu-id="15813-219">If example.com fixed this by setting up an SPF record but not a DKIM record, this would pass composite authentication because the domain that passed SPF aligned with the domain in the From: address:</span></span> 
  
```
Authentication-Results: spf=pass (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

<span data-ttu-id="15813-220">或者，如果他們設定 DKIM 記錄，但不是 SPF 記錄，這會同時傳遞複合驗證因為傳遞 DKIM 簽章中的網域對齊的網域，在 [從： 地址：</span><span class="sxs-lookup"><span data-stu-id="15813-220">Or, if they set up a DKIM record but not an SPF record, this would also pass composite authentication because the domain in the DKIM-Signature that passed aligned with the domain in the From: address:</span></span> 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.example.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

<span data-ttu-id="15813-221">不過，phisher 可能也設定 SPF 和 DKIM 和登入自己的網域的郵件，但指定不同的網域，在 [從： 地址。</span><span class="sxs-lookup"><span data-stu-id="15813-221">However, a phisher may also set up SPF and DKIM and sign the message with their own domain, but specify a different domain in the From: address.</span></span> <span data-ttu-id="15813-222">SPF 和 DKIM 都不需要以符合在 [從網域的網域： 地址，所以除非 example.com 發佈 DMARC 的記錄，這會將標示為使用 DMARC 詐騙：</span><span class="sxs-lookup"><span data-stu-id="15813-222">Neither SPF nor DKIM requires the domain to align with the domain in the From: address, so unless example.com published DMARC records, this would not be marked as a spoof using DMARC:</span></span> 
  
```
Authentication-Results: spf=pass (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```

<span data-ttu-id="15813-223">在 [電子郵件用戶端 (Outlook web 應用程式或任何其他電子郵件用戶端上的 Outlook)，只能從： 網域，則不在 SPF 或 DKIM，且網域可以到思考郵件是來自 example.com，但實際上是來自 maliciousDomain.com 誤導使用者.</span><span class="sxs-lookup"><span data-stu-id="15813-223">In the email client (Outlook, Outlook on the web, or any other email client), only the From: domain is displayed, not the domain in the SPF or DKIM, and that can mislead the user into thinking the message came from example.com, but actually came from maliciousDomain.com.</span></span>
  
![已驗證的訊息但從： 網域未對齊項目通過 SPF 或 DKIM](media/a9b5ab2a-dfd3-47c6-8ee8-e3dab2fae528.jpg)
  
<span data-ttu-id="15813-225">基於這個理由，Office 365 的所需的網域，在 [從： 地址配合 SPF 或 DKIM 簽章中的網域，且如果它不支援，包含一些其他內部訊號，指出郵件合法。</span><span class="sxs-lookup"><span data-stu-id="15813-225">For that reason, Office 365 requires that the domain in the From: address aligns with the domain in the SPF or DKIM signature, and if it doesn't, contains some other internal signals that indicates that the message is legitimate.</span></span> <span data-ttu-id="15813-226">否則，郵件就是 compauth 失敗。</span><span class="sxs-lookup"><span data-stu-id="15813-226">Otherwise, the message would be a compauth fail.</span></span> 
  
```
Authentication-Results: spf=none (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: sender@contoso.com
To: someone@example.com
```

<span data-ttu-id="15813-227">因此，Office 365 反詐騙保護未驗證的網域，但檢查設定驗證，但不符合針對在 [從網域的網域： 地址，也就是一，使用者會看到並相信是郵件的寄件者。</span><span class="sxs-lookup"><span data-stu-id="15813-227">Thus, Office 365 anti-spoofing protects against domains with no authentication, and against domains who set up authentication but mismatch against the domain in the From: address as that is the one that the user sees and believes is the sender of the message.</span></span> <span data-ttu-id="15813-228">這是這兩個組織外部的網域，以及組織內的網域，則為 true。</span><span class="sxs-lookup"><span data-stu-id="15813-228">This is true both of domains external to your organization, as well as domains within your organization.</span></span>
  
<span data-ttu-id="15813-229">因此，如果您曾經收到複合驗證失敗，並標示為冒名，即使郵件通過 SPF 和 DKIM 的訊息，它會是因為通過 SPF 和 DKIM 網域不一致的網域，在 [從： 地址。</span><span class="sxs-lookup"><span data-stu-id="15813-229">Therefore, if you ever receive a message that failed composite authentication and is marked as spoofed, even though the message passed SPF and DKIM, it's because the domain that passed SPF and DKIM are not aligned with the domain in the From: address.</span></span>
  
### <a name="understanding-changes-in-how-spoofed-emails-are-treated"></a><span data-ttu-id="15813-230">了解如何冒名的電子郵件中的變更會被視為</span><span class="sxs-lookup"><span data-stu-id="15813-230">Understanding changes in how spoofed emails are treated</span></span>

<span data-ttu-id="15813-231">目前，針對所有的組織中 Office 365-ATP 和非-ATP-郵件使用拒絕或隔離原則 DMARC 就會標示為垃圾郵件和通常需要 [高信賴度垃圾郵件] 動作，或有時一般的垃圾郵件動作的失敗 (根據其他垃圾郵件規則先加以識別為垃圾郵件）。</span><span class="sxs-lookup"><span data-stu-id="15813-231">Currently, for all organizations in Office 365 - ATP and non-ATP - messages that fail DMARC with a policy of reject or quarantine are marked as spam and usually take the high confidence spam action, or sometimes the regular spam action (depending on whether other spam rules first identify it as spam).</span></span> <span data-ttu-id="15813-232">組織內部詐騙偵測採取垃圾郵件規則。</span><span class="sxs-lookup"><span data-stu-id="15813-232">Intra-org spoof detections take the regular spam action.</span></span> <span data-ttu-id="15813-233">此行為不需要啟用，也可以停用它。</span><span class="sxs-lookup"><span data-stu-id="15813-233">This behavior does not need to be enabled, nor can it be disabled.</span></span>
  
<span data-ttu-id="15813-234">不過，跨網域詐騙郵件，這項變更之前他們會經過一般的垃圾郵件、 釣魚程式和惡意程式碼檢查與如果篩選器的其他組件 」 將其識別為可疑，將他們分別標示為垃圾郵件、 釣魚程式或惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="15813-234">However, for cross-domain spoofing messages, before this change they would go through regular spam, phish, and malware checks and if other parts of the filter identified them as suspicious, would mark them as spam, phish, or malware respectively.</span></span> <span data-ttu-id="15813-235">使用新的跨網域詐騙保護，無法進行驗證的任何郵件將根據預設，採取的動作中反網路釣魚定義\>反詐騙的原則。</span><span class="sxs-lookup"><span data-stu-id="15813-235">With the new cross-domain spoofing protection, any message that can't be authenticated will, by default, take the action defined in the Anti-phishing \> Anti-spoofing policy.</span></span> <span data-ttu-id="15813-236">如果其中一個未定義，它將會移至使用者的垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="15813-236">If one is not defined, it will be moved to a users Junk Email folder.</span></span> <span data-ttu-id="15813-237">在某些情況下，更可疑的郵件也會有紅色的安全提示新增到郵件。</span><span class="sxs-lookup"><span data-stu-id="15813-237">In some cases, more suspicious messages will also have the red safety tip added to the message.</span></span>
  
<span data-ttu-id="15813-238">這可能會導致先前已標示為垃圾郵件仍被標示為垃圾郵件，但現在也有紅色的安全提示; 某些郵件在其他情況下，新增先前已標示為非垃圾郵件會開始被標示為垃圾郵件 (CAT:SPOOF) 具有紅色安全提示的郵件。</span><span class="sxs-lookup"><span data-stu-id="15813-238">This may result in some messages that were previously marked as spam still getting marked as spam but will now also have a red safety tip; in other cases, messages that were previously marked as non-spam will start getting marked as spam (CAT:SPOOF) with a red safety tip added.</span></span> <span data-ttu-id="15813-239">在仍其他情況下，已移動所有垃圾郵件及釣魚程式至隔離區的客戶會立即看到它們移至 [垃圾郵件] 資料夾 （此行為，可以變更，請參閱[變更您的反詐騙設定](#changing-your-anti-spoofing-settings)）。</span><span class="sxs-lookup"><span data-stu-id="15813-239">In still other cases, customers that were moving all spam and phish to the quarantine would now see them going to the Junk Mail Folder (this behavior can be changed, see [Changing your anti-spoofing settings](#changing-your-anti-spoofing-settings)).</span></span>
  
<span data-ttu-id="15813-240">有多個不同的方式可以假冒 （請參閱本文稍早的[不同類型的詐騙之間 Differentiating](#differentiating-between-different-types-of-spoofing) ） 一則訊息，但截至 2018 年 3 月，Office 365 會將這些郵件的方法不尚未整合。</span><span class="sxs-lookup"><span data-stu-id="15813-240">There are multiple different ways a message can be spoofed (see  [Differentiating between different types of spoofing](#differentiating-between-different-types-of-spoofing) earlier in this article) but as of March 2018 the way Office 365 treats these messages is not yet unified.</span></span> <span data-ttu-id="15813-241">下表是快速摘要] 中，使用跨網域詐騙保護被新的行為：</span><span class="sxs-lookup"><span data-stu-id="15813-241">The following table is a quick summary, with Cross-domain spoofing protection being new behavior:</span></span> 
  
|<span data-ttu-id="15813-242">**詐騙的類型**</span><span class="sxs-lookup"><span data-stu-id="15813-242">**Type of spoof**</span></span>|<span data-ttu-id="15813-243">**類別**</span><span class="sxs-lookup"><span data-stu-id="15813-243">**Category**</span></span>|<span data-ttu-id="15813-244">**新增安全提示？**</span><span class="sxs-lookup"><span data-stu-id="15813-244">**Safety tip added?**</span></span>|<span data-ttu-id="15813-245">**適用於**</span><span class="sxs-lookup"><span data-stu-id="15813-245">**Applies to**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="15813-246">DMARC 失敗 （隔離或拒絕）</span><span class="sxs-lookup"><span data-stu-id="15813-246">DMARC fail (quarantine or reject)</span></span>  <br/> |<span data-ttu-id="15813-247">HSPM （預設值），也可能 SPM 或 PHSH</span><span class="sxs-lookup"><span data-stu-id="15813-247">HSPM (default), may also be SPM or PHSH</span></span>  <br/> |<span data-ttu-id="15813-248">否 （尚未）</span><span class="sxs-lookup"><span data-stu-id="15813-248">No (not yet)</span></span>  <br/> |<span data-ttu-id="15813-249">所有 Office 365 客戶 Outlook.com</span><span class="sxs-lookup"><span data-stu-id="15813-249">All Office 365 customers, Outlook.com</span></span>  <br/> |
|<span data-ttu-id="15813-250">自助-自助</span><span class="sxs-lookup"><span data-stu-id="15813-250">Self-to-self</span></span>  <br/> |<span data-ttu-id="15813-251">SPM</span><span class="sxs-lookup"><span data-stu-id="15813-251">SPM</span></span>  <br/> |<span data-ttu-id="15813-252">是</span><span class="sxs-lookup"><span data-stu-id="15813-252">Yes</span></span>  <br/> |<span data-ttu-id="15813-253">所有 Office 365 組織 Outlook.com</span><span class="sxs-lookup"><span data-stu-id="15813-253">All Office 365 organizations, Outlook.com</span></span>  <br/> |
|<span data-ttu-id="15813-254">跨網域</span><span class="sxs-lookup"><span data-stu-id="15813-254">Cross-domain</span></span>  <br/> |<span data-ttu-id="15813-255">詐騙</span><span class="sxs-lookup"><span data-stu-id="15813-255">SPOOF</span></span>  <br/> |<span data-ttu-id="15813-256">是</span><span class="sxs-lookup"><span data-stu-id="15813-256">Yes</span></span>  <br/> |<span data-ttu-id="15813-257">Office 365 進階威脅防護和 E5 客戶</span><span class="sxs-lookup"><span data-stu-id="15813-257">Office 365 Advanced Threat Protection and E5 customers</span></span>  <br/> |

### <a name="changing-your-anti-spoofing-settings"></a><span data-ttu-id="15813-258">變更您的反詐騙設定</span><span class="sxs-lookup"><span data-stu-id="15813-258">Changing your anti-spoofing settings</span></span>

<span data-ttu-id="15813-259">若要建立或更新 （跨網域） 反詐騙設定，瀏覽至 [防網路釣魚\>威脅管理] 下的反詐騙設定\>安全性原則] 索引標籤&amp;合規性中心。</span><span class="sxs-lookup"><span data-stu-id="15813-259">To create or update your (cross-domain) anti-spoofing settings, navigate to the Anti-phishing \> Anti-spoofing settings under the Threat Management \> Policy tab in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="15813-260">如果您從未建立任何反網路釣魚的設定，您必須建立一個：</span><span class="sxs-lookup"><span data-stu-id="15813-260">If you have never created any anti-phishing settings, you will need to create one:</span></span>
  
![反網路釣魚-建立新的原則](media/9337ec91-270e-4fa7-9dfa-a51a2d1eb95e.jpg)
  
<span data-ttu-id="15813-262">如果您已經建立一個，您可以選取要對其進行修改：</span><span class="sxs-lookup"><span data-stu-id="15813-262">If you've already created one, you can select it to modify it:</span></span>
  
![反網路釣魚-修改現有的原則](media/75457a7c-882e-4984-80d1-21a12b42c53a.jpg)
  
<span data-ttu-id="15813-264">選取您剛剛建立，並繼續執行步驟，[了解詐騙情報多個](learn-about-spoof-intelligence.md)所述的原則。</span><span class="sxs-lookup"><span data-stu-id="15813-264">Select the policy you just created and proceed through the steps as described in [Learn more about spoof intelligence](learn-about-spoof-intelligence.md).</span></span>
  
![啟用或停用反詐騙](media/c49e2147-c954-443c-9144-1cbd139e1166.jpg)
  
![啟用或停用反詐騙安全提示](media/eec7c407-31fc-4f73-8325-307d82d1fb53.jpg)
  
<span data-ttu-id="15813-267">若要使用 PowerShell 建立新的原則：</span><span class="sxs-lookup"><span data-stu-id="15813-267">To create a new policy by using PowerShell:</span></span> 
  
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

<span data-ttu-id="15813-268">然後，您可能會修改使用 PowerShell，下列[設定 AntiphishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy?view=exchange-ps)文件的防網路釣魚原則參數。</span><span class="sxs-lookup"><span data-stu-id="15813-268">You may then modify the anti-phishing policy parameters using PowerShell, following the documentation at [Set-AntiphishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy?view=exchange-ps).</span></span> <span data-ttu-id="15813-269">您可能會當做參數指定 $name:</span><span class="sxs-lookup"><span data-stu-id="15813-269">You may specify the $name as a parameter:</span></span>
  
```powershell
Set-AntiphishPolicy -Identity $name <fill in rest of parameters>
```

<span data-ttu-id="15813-270">稍後 2018，而不是您不必建立一個預設原則，其中會加以建立，因此您不需要以手動方式指定範圍限定為您組織中的所有收件者 （以下螢幕擷取畫面受限於最終實作之前變更）。</span><span class="sxs-lookup"><span data-stu-id="15813-270">Later in 2018, rather than you having to create a default policy, one will be created for you that is scoped to all the recipients in your organization so you don't have to specify it manually (the screenshots below are subject to change before the final implementation).</span></span>
  
![預設的反網路釣魚原則](media/1f27a0bf-e202-4e12-bbac-24baf013c8f9.jpg)
  
<span data-ttu-id="15813-272">不同於您所建立的原則，您無法刪除預設原則，修改它的優先順序，或選擇將範圍至哪一個使用者、 網域或群組。</span><span class="sxs-lookup"><span data-stu-id="15813-272">Unlike a policy that you create, you cannot delete the default policy, modify its priority, or choose which users, domains, or groups to scope it to.</span></span>
  
![反網路釣魚預設原則的詳細資訊](media/30c21ceb-df52-4c93-aa65-f44a55dc1009.jpg)
  
<span data-ttu-id="15813-274">若要使用 PowerShell 來設定預設保護：</span><span class="sxs-lookup"><span data-stu-id="15813-274">To set up your default protection by using PowerShell:</span></span>
  
```powershell
$defaultAntiphishPolicy = Get-AntiphishPolicy | ? {$_.IsDefault -eq $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement <$true|$false>
```

<span data-ttu-id="15813-275">您應該僅停用反詐騙保護如果您有另一部信箱伺服器或在 Office 365 前方的伺服器 （請參閱合法的案例，以停用反詐騙如需詳細資訊）。</span><span class="sxs-lookup"><span data-stu-id="15813-275">You should only disable anti-spoofing protection if you have another mail server or servers in front of Office 365 (see Legitimate scenarios to disable anti-spoofing for more details).</span></span>
  
```powershell
$defaultAntiphishPolicy = Get-AntiphishiPolicy | ? {$_.IsDefault $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement $false 

```
> [!IMPORTANT]
> <span data-ttu-id="15813-276">如果您的電子郵件路徑中的第一個躍點是 Office 365，並收到太多合法電子郵件標示為詐騙，您應該先設定您允許將冒名的電子郵件傳送到您網域的寄件者 （請參閱節 *」 管理合法寄件者所傳送 unauthenticated 電子郵件 」* )。</span><span class="sxs-lookup"><span data-stu-id="15813-276">If the first hop in your email path is Office 365, and you are getting too many legitimate emails marked as spoof, you should first set up your senders that are allowed to send spoofed email to your domain (see the section  *"Managing legitimate senders who are sending unauthenticated email"*  ).</span></span> <span data-ttu-id="15813-277">如果您仍收到太多誤判 （也就是合法郵件標示為詐騙），我們不建議停用反詐騙保護夾雜在一起。</span><span class="sxs-lookup"><span data-stu-id="15813-277">If you are still getting too many false positives (that is, legitimate messages marked as spoof), we do NOT recommend disabling anti-spoofing protection altogether.</span></span> <span data-ttu-id="15813-278">相反地，我們建議您選擇基本而不最高保護。</span><span class="sxs-lookup"><span data-stu-id="15813-278">Instead, we recommend choosing Basic instead of High protection.</span></span> <span data-ttu-id="15813-279">最好是透過誤判比至公開最後意來得高成本的長期詐騙電子郵件組織運作。</span><span class="sxs-lookup"><span data-stu-id="15813-279">It is better to work through false positives than to expose your organization to spoofed email which could end up imposing significantly higher costs in the long term.</span></span>

### <a name="managing-legitimate-senders-who-are-sending-unauthenticated-email"></a><span data-ttu-id="15813-280">管理合法的寄件者所傳送未驗證的電子郵件</span><span class="sxs-lookup"><span data-stu-id="15813-280">Managing legitimate senders who are sending unauthenticated email</span></span>

<span data-ttu-id="15813-281">記錄傳送者誰未經驗證的電子郵件至您的組織的 office 365。</span><span class="sxs-lookup"><span data-stu-id="15813-281">Office 365 keeps track of who is sending unauthenticated email to your organization.</span></span> <span data-ttu-id="15813-282">如果服務認為不合法寄件者，它會將它標記為*compauth*失敗。</span><span class="sxs-lookup"><span data-stu-id="15813-282">If the service thinks the sender is not legitimate, it will mark it as a *compauth* failure.</span></span> <span data-ttu-id="15813-283">這會歸類為詐騙，雖然這取決於您已套用至郵件的反詐騙原則。</span><span class="sxs-lookup"><span data-stu-id="15813-283">This will be classified as SPOOF although it depends on your anti-spoofing policy that was applied to the message.</span></span>
  
<span data-ttu-id="15813-284">不過，身為管理員，您可以指定哪些寄件者允許傳送冒名的電子郵件，覆寫 Office 365 的決策。</span><span class="sxs-lookup"><span data-stu-id="15813-284">However, as an administrator, you can specify which senders are permitted to send spoofed email, overriding Office 365's decision.</span></span>
  
<span data-ttu-id="15813-285">**方法 1-如果您的組織擁有的網域、 設定電子郵件的驗證**</span><span class="sxs-lookup"><span data-stu-id="15813-285">**Method 1 - If your organization owns the domain, set up email authentication**</span></span>
  
<span data-ttu-id="15813-286">此方法可以用來解決組織內部詐騙和跨網域詐騙在您擁有或互動的情況下使用多重租用戶。</span><span class="sxs-lookup"><span data-stu-id="15813-286">This method can be used to resolve intra-org spoofing, and cross-domain spoofing in cases where you own or interact with multiple tenants.</span></span> <span data-ttu-id="15813-287">它也可以協助解決跨網域詐騙您傳送給其他 Office 365 內的客戶，也裝載於其他提供者的第三方。</span><span class="sxs-lookup"><span data-stu-id="15813-287">It also helps resolve cross-domain spoofing where you send to other customers within Office 365, and also third parties that are hosted in other providers.</span></span>
  
<span data-ttu-id="15813-288">如需詳細資訊，請參閱 < <b0>Office 365 的客戶</b0>。</span><span class="sxs-lookup"><span data-stu-id="15813-288">For more details, see [Customers of Office 365](#customers-of-office-365).</span></span>

<span data-ttu-id="15813-289">**方法 2-設定未驗證的電子郵件的允許寄件者使用詐騙智慧**</span><span class="sxs-lookup"><span data-stu-id="15813-289">**Method 2 - Use Spoof intelligence to configure permitted senders of unauthenticated email**</span></span>
  
<span data-ttu-id="15813-290">您也可以使用[詐騙智慧](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf)允許未經驗證的郵件傳輸至貴組織的寄件者。</span><span class="sxs-lookup"><span data-stu-id="15813-290">You can also use [Spoof Intelligence](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf) to permit senders to transmit unauthenticated messages to your organization.</span></span> 
  
<span data-ttu-id="15813-291">外部網域，如詐騙的使用者是中的 From 地址的網域傳送基礎結構時傳送端 IP 位址 (分成/24 CIDR 範圍)，或組織的網域的 PTR 記錄 （在以下的螢幕擷取畫面，傳送 IP 可能是的 PTR 記錄是 outbound.mail.protection.outlook.com，131.107.18.4，而且這會顯示為 [傳送基礎結構的 outlook.com）。</span><span class="sxs-lookup"><span data-stu-id="15813-291">For external domains, the spoofed user is the domain in the From address, while the sending infrastructure is either the sending IP address (divided up into /24 CIDR ranges), or the organizational domain of the PTR record (in the screenshot below, the sending IP might be 131.107.18.4 whose PTR record is outbound.mail.protection.outlook.com, and this would show up as outlook.com for the sending infrastructure).</span></span>
  
<span data-ttu-id="15813-292">若要允許此寄件者傳送未驗證的電子郵件，變更為 [ **]** 的**否]** 。</span><span class="sxs-lookup"><span data-stu-id="15813-292">To permit this sender to send unauthenticated email, change the **No** to a **Yes**.</span></span>
  
![設定反詐騙的允許寄件者](media/d4334921-d820-4334-8217-788279701e94.jpg)
  
<span data-ttu-id="15813-294">您也可以使用 PowerShell 以允許特定寄件者偽造您的網域：</span><span class="sxs-lookup"><span data-stu-id="15813-294">You can also use PowerShell to allow specific sender to spoof your domain:</span></span>
  
```powershell
$file = "C:\My Documents\Summary Spoofed Internal Domains and Senders.csv"
```

```powershell
Get-PhishFilterPolicy -Detailed -SpoofAllowBlockList -SpoofType External | Export-CSV $file
```

![從 Powershell 取得詐騙的寄件者](media/0e27ffcf-a5db-4c43-a19b-fa62326d5118.jpg)
  
<span data-ttu-id="15813-296">在上圖中額外的分行符號已新增若要讓這個螢幕擷取畫面配合。</span><span class="sxs-lookup"><span data-stu-id="15813-296">In the previous image, additional line breaks have been added to make this screenshot fit.</span></span> <span data-ttu-id="15813-297">一般而言，所有的值會出現在單一行上。</span><span class="sxs-lookup"><span data-stu-id="15813-297">Normally, all the values would appear on a single line.</span></span>
  
<span data-ttu-id="15813-298">編輯檔案並尋找對應至 outlook.com 和 bing.com，那一行，AllowedToSpoof 項目變更為 [是] 否從：</span><span class="sxs-lookup"><span data-stu-id="15813-298">Edit the file and look for the line that corresponds to outlook.com and bing.com, and change the AllowedToSpoof entry from No to Yes:</span></span>
  
![在 Powershell 中的 [是] 允許設定詐騙](media/62340452-62d3-4958-9ce9-afe5275a870d.jpg)
  
<span data-ttu-id="15813-300">儲存檔案，然後再執行：</span><span class="sxs-lookup"><span data-stu-id="15813-300">Save the file, and then run:</span></span>
  
```powershell
$UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
```

<span data-ttu-id="15813-301">現在，這樣可讓傳送未驗證的電子郵件從 bing.com \*。 outlook.com。</span><span class="sxs-lookup"><span data-stu-id="15813-301">This will now allow bing.com to send unauthenticated email from \*.outlook.com.</span></span>

<span data-ttu-id="15813-302">**方法 3-建立寄件者/收件者對允許項目**</span><span class="sxs-lookup"><span data-stu-id="15813-302">**Method 3 - Create an allow entry for the sender/recipient pair**</span></span>
  
<span data-ttu-id="15813-303">您也可以選擇略過所有的垃圾郵件篩選特定寄件者。</span><span class="sxs-lookup"><span data-stu-id="15813-303">You can also choose to bypass all spam filtering for a particular sender.</span></span> <span data-ttu-id="15813-304">如需詳細資訊，請參閱 < <b0>How to： 安全地新增到 Office 365 中的 [允許] 清單寄件者</b0>。</span><span class="sxs-lookup"><span data-stu-id="15813-304">For more details, see [How to securely add a sender to an allow list in Office 365](https://blogs.msdn.microsoft.com/tzink/2017/11/29/how-to-securely-add-a-sender-to-an-allow-list-in-office-365/).</span></span>
  
<span data-ttu-id="15813-305">如果您使用此方法時，它會略過垃圾郵件與部分的釣魚程式篩選，但卻不惡意程式碼篩選。</span><span class="sxs-lookup"><span data-stu-id="15813-305">If you use this method, it will skip spam and some of the phish filtering, but not malware filtering.</span></span>
  
<span data-ttu-id="15813-306">**方法 4-連絡寄件者，並請他們設定電子郵件的驗證**</span><span class="sxs-lookup"><span data-stu-id="15813-306">**Method 4 - Contact the sender and ask them to set up email authentication**</span></span>
  
<span data-ttu-id="15813-307">因為垃圾郵件和網路釣魚的問題，Microsoft 建議您設定電子郵件驗證所有寄件者。</span><span class="sxs-lookup"><span data-stu-id="15813-307">Because of the problem of spam and phishing, Microsoft recommends all senders set up email authentication.</span></span> <span data-ttu-id="15813-308">如果您知道傳送網域的系統管理員，請連絡它們並要求將它們設定成電子郵件驗證記錄使您不需要加任何覆寫。</span><span class="sxs-lookup"><span data-stu-id="15813-308">If you know an administrator of the sending domain, contact them and request that they set up email authentication records so you do not have to add any overrides.</span></span> <span data-ttu-id="15813-309">如需詳細資訊，請參閱 <<c0>的網域都不是 Office 365 客戶的系統管理員」 本文稍後的。</span><span class="sxs-lookup"><span data-stu-id="15813-309">For more information, see [Administrators of domains that are not Office 365 customers](#administrators-of-domains-that-are-not-office-365-customers)" later in this article.</span></span> 
  
<span data-ttu-id="15813-310">時可能很難在第一次取得傳送網域來進行驗證，經過一段時間，為越來越多電子郵件篩選器啟動 junking 或甚至拒絕他們的電子郵件時，就會造成這些設定的適當的記錄，以確保較佳的傳遞。</span><span class="sxs-lookup"><span data-stu-id="15813-310">While it may be difficult at first to get sending domains to authenticate, over time, as more and more email filters start junking or even rejecting their email, it will cause them to set up the proper records to ensure better delivery.</span></span>
  
### <a name="viewing-reports-of-how-many-messages-were-marked-as-spoofed"></a><span data-ttu-id="15813-311">檢視多少郵件已標示為冒名的報告</span><span class="sxs-lookup"><span data-stu-id="15813-311">Viewing reports of how many messages were marked as spoofed</span></span>

<span data-ttu-id="15813-312">一旦啟用您的反詐騙政策，您可以使用威脅情報來讓周圍多少訊息標示為釣魚程式的數字。</span><span class="sxs-lookup"><span data-stu-id="15813-312">Once your anti-spoofing policy is enabled, you can use Threat Intelligence to get numbers around how many messages are marked as phish.</span></span> <span data-ttu-id="15813-313">若要這麼做，請移至安全性&amp;合規性中心 (SCC) 威脅管理下\>總管] 中，將檢視設定釣魚程式，以及群組所寄件者網域] 或 [保護狀態：</span><span class="sxs-lookup"><span data-stu-id="15813-313">To do this, go into the Security &amp; Compliance Center (SCC) under Threat Management \> Explorer, set the View to Phish, and group by Sender Domain or Protection Status:</span></span>
  
![檢視多少訊息標示為釣魚程式](media/de25009a-44d4-4c5f-94ba-9c75cd9c64b3.jpg)
  
<span data-ttu-id="15813-315">您可以與各種不同的報告，以查看多少被標示為網路釣魚，包括郵件標示為詐騙互動。</span><span class="sxs-lookup"><span data-stu-id="15813-315">You can interact with the various reports to see how many were marked as phishing, including messages marked as SPOOF.</span></span> <span data-ttu-id="15813-316">若要深入了解，請參閱[Office 365 威脅情報快速入門](get-started-with-ti.md)。</span><span class="sxs-lookup"><span data-stu-id="15813-316">To learn more, see [Get started with Office 365 Threat Intelligence](get-started-with-ti.md).</span></span>
  
<span data-ttu-id="15813-317">您還不能分割哪一個郵件已標示為因為詐騙而非其他類型的網路釣魚 （一般網路釣魚、 網域或使用者模擬，等等）。</span><span class="sxs-lookup"><span data-stu-id="15813-317">You can't yet split out which messages were marked due to spoofing as opposed to other types of phishing (general phishing, domain or user impersonation, and so on).</span></span> <span data-ttu-id="15813-318">不過，更新版本中，您將能夠執行這項操作透過安全性&amp;合規性中心。</span><span class="sxs-lookup"><span data-stu-id="15813-318">However, later, you will be able to do this through the Security &amp; Compliance Center.</span></span> <span data-ttu-id="15813-319">一旦您這麼做，您可以使用的起始位置為這份報告來識別可能合法的會被標示為因為失敗的驗證詐騙的寄送網域。</span><span class="sxs-lookup"><span data-stu-id="15813-319">Once you do, you can use this report as a starting place to identify sending domains that may be legitimate that are being marked as spoof due to failing authentication.</span></span>
  
<span data-ttu-id="15813-320">下列螢幕擷取畫面會提案，此資料的看起來，但發行時可能會變更：</span><span class="sxs-lookup"><span data-stu-id="15813-320">The following screenshot is a proposal for how this data will look, but may change when released:</span></span>
  
![檢視網路釣魚報告偵測類型](media/dd25d63f-152c-4c55-a07b-184ecda2de81.jpg)
  
<span data-ttu-id="15813-322">非 ATP 和 E5 客戶，這些報告可稍後下威脅保護狀態 (TPS) 報告，請使用，但將至少 24 小時的延遲。</span><span class="sxs-lookup"><span data-stu-id="15813-322">For non-ATP and E5 customers, these reports will be available later under the Threat Protection Status (TPS) reports, but will be delayed by at least 24 hours.</span></span> <span data-ttu-id="15813-323">將更新此頁面上，因為它們已整合至安全性&amp;合規性中心。</span><span class="sxs-lookup"><span data-stu-id="15813-323">This page will be updated as they are integrated into the Security &amp; Compliance Center.</span></span>
  
### <a name="predicting-how-many-messages-will-be-marked-as-spoof"></a><span data-ttu-id="15813-324">預測解決方案能夠提供多少郵件會被標示為詐騙</span><span class="sxs-lookup"><span data-stu-id="15813-324">Predicting how many messages will be marked as spoof</span></span>

<span data-ttu-id="15813-325">一旦 Office 365 更新其設定，以讓您在關閉反詐騙強制執行，或在與基本或高強制執行，您將能夠查看如何在各種設定變更郵件處理的能力。</span><span class="sxs-lookup"><span data-stu-id="15813-325">Once Office 365 updates its settings to let you turn the anti-spoofing enforcement Off, or on with Basic or High enforcement, you will be given the ability to see how message disposition will change at the various settings.</span></span> <span data-ttu-id="15813-326">也就是說，如果反詐騙已關閉，您將能夠看到多少訊息將會被偵測為詐騙，如果您開啟為 Basic;或者，如果是 Basic，您將能夠看到多少更多的郵件會被偵測為詐騙，如果您開啟為 [高]。</span><span class="sxs-lookup"><span data-stu-id="15813-326">That is, if anti-spoofing is Off, you will be able to see how many messages will be detected as Spoof if you turn to Basic; or, if it's Basic, you will be able to see how many more messages will be detected as Spoof if you turn it to High.</span></span>
  
<span data-ttu-id="15813-327">此功能目前是在開發。</span><span class="sxs-lookup"><span data-stu-id="15813-327">This feature is currently under development.</span></span> <span data-ttu-id="15813-328">已定義的詳細資訊，與螢幕擷取畫面的安全性與合規性中心，並以 PowerShell 範例，將會更新此頁面。</span><span class="sxs-lookup"><span data-stu-id="15813-328">As more details are defined, this page will be updated both with screenshots of the Security and Compliance Center, and with PowerShell examples.</span></span>
  
![「 如果 」 報告啟用反詐騙](media/fdd085ae-02c1-4327-a063-bfe9a32ff1eb.jpg)
  
![允許詐騙的寄件者可能 UX](media/53f9f73e-fb01-47f3-9a6d-850c1aef5efe.jpg)
  
### <a name="understanding-how-spam-phishing-and-advanced-phishing-detections-are-combined"></a><span data-ttu-id="15813-331">了解如何垃圾郵件、 網路釣魚，以及偵測會結合的進階網路釣魚</span><span class="sxs-lookup"><span data-stu-id="15813-331">Understanding how spam, phishing, and advanced phishing detections are combined</span></span>

<span data-ttu-id="15813-332">使用 Exchange Online 中，或者沒有 ATP，組織可以指定服務判別為惡意程式碼、 垃圾郵件、 高信賴度垃圾郵件、 網路釣魚及大量郵件時要採取的動作。</span><span class="sxs-lookup"><span data-stu-id="15813-332">Organizations that use Exchange Online, with or without ATP, can specify which actions to take when the service identifies messages as malware, spam, high confidence spam, phishing, and bulk.</span></span> <span data-ttu-id="15813-333">ATP 客戶的 ATP 防網路釣魚原則和 EOP 客戶的防網路釣魚原則與訊息可能會叫用多個偵測類型 （例如，惡意程式碼、 網路釣魚，與使用者模擬） 的事實，可能會有哪些某些混淆會套用原則。</span><span class="sxs-lookup"><span data-stu-id="15813-333">With the ATP Anti-phishing policies for ATP customers, and the Anti-phishing policies for EOP customers, and the fact that a message may hit multiple detection types (for example, malware, phishing, and user-impersonation), there may be some confusion as to which policy applies.</span></span>
  
<span data-ttu-id="15813-334">一般而言，在 CAT （類別） 屬性中的 X Forefront-反垃圾郵件報告標頭中識別套用至郵件的原則。</span><span class="sxs-lookup"><span data-stu-id="15813-334">In general, the policy applied to a message is identified in the X-Forefront-Antispam-Report header in the CAT (Category) property.</span></span>
  
|<span data-ttu-id="15813-335">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="15813-335">**Priority**</span></span>|<span data-ttu-id="15813-336">**原則**</span><span class="sxs-lookup"><span data-stu-id="15813-336">**Policy**</span></span>|<span data-ttu-id="15813-337">**類別**</span><span class="sxs-lookup"><span data-stu-id="15813-337">**Category**</span></span>|<span data-ttu-id="15813-338">**其中管理？**</span><span class="sxs-lookup"><span data-stu-id="15813-338">**Where managed?**</span></span>|<span data-ttu-id="15813-339">**適用於**</span><span class="sxs-lookup"><span data-stu-id="15813-339">**Applies to**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="15813-340">1</span><span class="sxs-lookup"><span data-stu-id="15813-340">1</span></span>  <br/> |<span data-ttu-id="15813-341">惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="15813-341">Malware</span></span>  <br/> |<span data-ttu-id="15813-342">MALW</span><span class="sxs-lookup"><span data-stu-id="15813-342">MALW</span></span>  <br/> |[<span data-ttu-id="15813-343">惡意程式碼原則</span><span class="sxs-lookup"><span data-stu-id="15813-343">Malware policy</span></span>](configure-anti-malware-policies.md) <br/> |<span data-ttu-id="15813-344">所有的組織</span><span class="sxs-lookup"><span data-stu-id="15813-344">All organizations</span></span>  <br/> |
|<span data-ttu-id="15813-345">2</span><span class="sxs-lookup"><span data-stu-id="15813-345">2</span></span>  <br/> |<span data-ttu-id="15813-346">網路釣魚</span><span class="sxs-lookup"><span data-stu-id="15813-346">Phishing</span></span>  <br/> |<span data-ttu-id="15813-347">PHSH</span><span class="sxs-lookup"><span data-stu-id="15813-347">PHSH</span></span>  <br/> |[<span data-ttu-id="15813-348">設定您的垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="15813-348">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md) <br/> |<span data-ttu-id="15813-349">所有的組織</span><span class="sxs-lookup"><span data-stu-id="15813-349">All organizations</span></span>  <br/> |
|<span data-ttu-id="15813-350">3</span><span class="sxs-lookup"><span data-stu-id="15813-350">3</span></span>  <br/> |<span data-ttu-id="15813-351">高信賴度垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="15813-351">High confidence spam</span></span>  <br/> |<span data-ttu-id="15813-352">HSPM</span><span class="sxs-lookup"><span data-stu-id="15813-352">HSPM</span></span>  <br/> |[<span data-ttu-id="15813-353">設定您的垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="15813-353">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md) <br/> |<span data-ttu-id="15813-354">所有的組織</span><span class="sxs-lookup"><span data-stu-id="15813-354">All organizations</span></span>  <br/> |
|<span data-ttu-id="15813-355">4</span><span class="sxs-lookup"><span data-stu-id="15813-355">4</span></span>  <br/> |<span data-ttu-id="15813-356">詐騙</span><span class="sxs-lookup"><span data-stu-id="15813-356">Spoofing</span></span>  <br/> |<span data-ttu-id="15813-357">詐騙</span><span class="sxs-lookup"><span data-stu-id="15813-357">SPOOF</span></span>  <br/> |<span data-ttu-id="15813-358">[反網路釣魚原則](https://go.microsoft.com/fwlink/?linkid=864553)，[詐騙智慧](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="15813-358">[Anti-phishing policy](https://go.microsoft.com/fwlink/?linkid=864553), [Spoof intelligence](learn-about-spoof-intelligence.md)</span></span> <br/> |<span data-ttu-id="15813-359">所有的組織</span><span class="sxs-lookup"><span data-stu-id="15813-359">All organizations</span></span>  <br/> |
|<span data-ttu-id="15813-360">5</span><span class="sxs-lookup"><span data-stu-id="15813-360">5</span></span>  <br/> |<span data-ttu-id="15813-361">垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="15813-361">Spam</span></span>  <br/> |<span data-ttu-id="15813-362">SPM</span><span class="sxs-lookup"><span data-stu-id="15813-362">SPM</span></span>  <br/> |[<span data-ttu-id="15813-363">設定您的垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="15813-363">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md) <br/> |<span data-ttu-id="15813-364">所有的組織</span><span class="sxs-lookup"><span data-stu-id="15813-364">All organizations</span></span>  <br/> |
|<span data-ttu-id="15813-365">6</span><span class="sxs-lookup"><span data-stu-id="15813-365">6</span></span>  <br/> |<span data-ttu-id="15813-366">大量</span><span class="sxs-lookup"><span data-stu-id="15813-366">Bulk</span></span>  <br/> |<span data-ttu-id="15813-367">大量</span><span class="sxs-lookup"><span data-stu-id="15813-367">BULK</span></span>  <br/> |[<span data-ttu-id="15813-368">設定您的垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="15813-368">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md) <br/> |<span data-ttu-id="15813-369">所有的組織</span><span class="sxs-lookup"><span data-stu-id="15813-369">All organizations</span></span>  <br/> |
|<span data-ttu-id="15813-370">7</span><span class="sxs-lookup"><span data-stu-id="15813-370">7</span></span>  <br/> |<span data-ttu-id="15813-371">網域模擬</span><span class="sxs-lookup"><span data-stu-id="15813-371">Domain Impersonation</span></span>  <br/> |<span data-ttu-id="15813-372">DIMP</span><span class="sxs-lookup"><span data-stu-id="15813-372">DIMP</span></span>  <br/> |[<span data-ttu-id="15813-373">設定 Office 365 ATP 防網路釣魚和防網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="15813-373">Set up Office 365 ATP anti-phishing and anti-phishing policies</span></span>](set-up-anti-phishing-policies.md) <br/> |<span data-ttu-id="15813-374">僅限組織的 ATP</span><span class="sxs-lookup"><span data-stu-id="15813-374">Organizations with ATP only</span></span>  <br/> |
|<span data-ttu-id="15813-375">8</span><span class="sxs-lookup"><span data-stu-id="15813-375">8</span></span>  <br/> |<span data-ttu-id="15813-376">使用者模擬</span><span class="sxs-lookup"><span data-stu-id="15813-376">User Impersonation</span></span>  <br/> |<span data-ttu-id="15813-377">UIMP</span><span class="sxs-lookup"><span data-stu-id="15813-377">UIMP</span></span>  <br/> |[<span data-ttu-id="15813-378">設定 Office 365 ATP 防網路釣魚和防網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="15813-378">Set up Office 365 ATP anti-phishing and anti-phishing policies</span></span>](set-up-anti-phishing-policies.md) <br/> |<span data-ttu-id="15813-379">僅限組織的 ATP</span><span class="sxs-lookup"><span data-stu-id="15813-379">Organizations with ATP only</span></span> <br/> |

<span data-ttu-id="15813-380">如果您有多個不同的防網路釣魚原則時，會套用在最高優先順序的一個。</span><span class="sxs-lookup"><span data-stu-id="15813-380">If you have multiple different Anti-phishing policies, the one at the highest priority will apply.</span></span> <span data-ttu-id="15813-381">例如，假設您有兩個原則：</span><span class="sxs-lookup"><span data-stu-id="15813-381">For example, suppose you have two policies:</span></span>

|<span data-ttu-id="15813-382">**原則**</span><span class="sxs-lookup"><span data-stu-id="15813-382">**Policy**</span></span>|<span data-ttu-id="15813-383">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="15813-383">**Priority**</span></span>|<span data-ttu-id="15813-384">**使用者/網域模擬**</span><span class="sxs-lookup"><span data-stu-id="15813-384">**User/Domain Impersonation**</span></span>|<span data-ttu-id="15813-385">**反詐騙**</span><span class="sxs-lookup"><span data-stu-id="15813-385">**Anti-spoofing**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="15813-386">A</span><span class="sxs-lookup"><span data-stu-id="15813-386">A</span></span>  <br/> |<span data-ttu-id="15813-387">1</span><span class="sxs-lookup"><span data-stu-id="15813-387">1</span></span>  <br/> |<span data-ttu-id="15813-388">開啟</span><span class="sxs-lookup"><span data-stu-id="15813-388">On</span></span>  <br/> |<span data-ttu-id="15813-389">Off</span><span class="sxs-lookup"><span data-stu-id="15813-389">Off</span></span>  <br/> |
|<span data-ttu-id="15813-390">B</span><span class="sxs-lookup"><span data-stu-id="15813-390">B</span></span>  <br/> |<span data-ttu-id="15813-391">2</span><span class="sxs-lookup"><span data-stu-id="15813-391">2</span></span>  <br/> |<span data-ttu-id="15813-392">Off</span><span class="sxs-lookup"><span data-stu-id="15813-392">Off</span></span>  <br/> |<span data-ttu-id="15813-393">開啟</span><span class="sxs-lookup"><span data-stu-id="15813-393">On</span></span>  <br/> |

<span data-ttu-id="15813-394">如果郵件有而識別為詐騙與使用者模擬，並組相同的使用者範圍的原則和原則 B，然後郵件會被視為詐騙，但沒有動作會套用自反詐騙已關閉並詐騙執行於優先順序較高 (4) 與使用者模擬 (8)。</span><span class="sxs-lookup"><span data-stu-id="15813-394">If a message comes in and is identified as both spoofing and user impersonation, and the same set of users is scoped to Policy A and Policy B, then the message is treated as a spoof but no action is applied since Anti-spoofing is turned off, and SPOOF runs at a higher priority (4) than User Impersonation (8).</span></span>
  
<span data-ttu-id="15813-395">若要讓其他類型的網路釣魚原則套用，您將需要調整的各種不同的原則套用到使用者的設定。</span><span class="sxs-lookup"><span data-stu-id="15813-395">To make other types of phishing policy apply, you will need to adjust the settings of who the various policies are applied to.</span></span>
  
### <a name="legitimate-scenarios-to-disable-anti-spoofing"></a><span data-ttu-id="15813-396">若要停用反詐騙合法案例</span><span class="sxs-lookup"><span data-stu-id="15813-396">Legitimate scenarios to disable anti-spoofing</span></span>

<span data-ttu-id="15813-397">從網路釣魚攻擊更妥善地反詐騙保護客戶，因此停用的反詐騙保護強烈建議不要。</span><span class="sxs-lookup"><span data-stu-id="15813-397">Anti-spoofing better protects customers from phishing attacks, and therefore disabling anti-spoofing protection is strongly discouraged.</span></span> <span data-ttu-id="15813-398">藉由停用它，您可能會解決某些短期誤判，但您將會公開給更大的風險的長詞彙。</span><span class="sxs-lookup"><span data-stu-id="15813-398">By disabling it, you may resolve some short-term false positives, but long term you will be exposed to more risk.</span></span> <span data-ttu-id="15813-399">設定驗證等寄件者，或在網路釣魚原則 」，進行調整的成本通常是一次性事件或需要僅最少，定期維護。</span><span class="sxs-lookup"><span data-stu-id="15813-399">The cost for setting up authentication on the sender side, or making adjustments in the phishing policies, are usually one-time events or require only minimal, periodic maintenance.</span></span> <span data-ttu-id="15813-400">不過，若要從網路釣魚攻擊，其中具有已公開的資料，復原成本或資產已遭到盜用是更高。</span><span class="sxs-lookup"><span data-stu-id="15813-400">However, the cost to recover from a phishing attack where data has been exposed, or assets have been compromised is much higher.</span></span>
  
<span data-ttu-id="15813-401">基於這個理由，最好是透過反詐騙誤判比若要停用反詐騙保護運作。</span><span class="sxs-lookup"><span data-stu-id="15813-401">For this reason, it is better to work through anti-spoofing false positives than to disable anti-spoof protection.</span></span>
  
<span data-ttu-id="15813-402">不過，沒有合法的案例，其中應該停用反詐騙，而且是時有額外的郵件篩選中的郵件路由，和 Office 365 產品不是在電子郵件路徑中的第一個躍點：</span><span class="sxs-lookup"><span data-stu-id="15813-402">However, there is a legitimate scenario where anti-spoofing should be disabled, and that is when there are additional mail-filtering products in the message routing, and Office 365 is not the first hop in the email path:</span></span>
  
![客戶 MX 記錄未指向 Office 365](media/62127c16-cfb8-4880-9cad-3c12d827c67e.jpg)
  
<span data-ttu-id="15813-404">Exchange 內部部署郵件伺服器，篩選裝置 Ironport，例如郵件或其他雲端託管的服務，可能是另一部伺服器。</span><span class="sxs-lookup"><span data-stu-id="15813-404">The other server may be an Exchange on-premises mail server, a mail filtering device such as Ironport, or another cloud hosted service.</span></span>
  
<span data-ttu-id="15813-405">如果收件者網域的 MX 記錄未指向 Office 365，然後便不需要停用反詐騙因為 Office 365 會接收網域的 MX 記錄，並隱藏反詐騙如果它指向另一個服務。</span><span class="sxs-lookup"><span data-stu-id="15813-405">If the MX record of the recipient domain does not point to Office 365, then there is no need to disable anti-spoofing because Office 365 looks up your receiving domain's MX record and suppresses anti-spoofing if it points to another service.</span></span> <span data-ttu-id="15813-406">如果您不知道如果您的網域可在前面有另一部伺服器，您可以使用像是 MX 工具箱網站來查閱 MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="15813-406">If you don't know if your domain has another server in front, you can use a website like MX Toolbox to look up the MX record.</span></span> <span data-ttu-id="15813-407">它可能會說如下所示：</span><span class="sxs-lookup"><span data-stu-id="15813-407">It might say something like the following:</span></span>
  
![MX 記錄指示網域不是指向 Office 365](media/d868bb9f-3462-49aa-baea-9447a3ce4877.jpg)
  
<span data-ttu-id="15813-409">此網域有未指向 Office 365，讓 Office 365 不會套用反詐騙強制執行的 MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="15813-409">This domain has an MX record that does not point to Office 365, so Office 365 would not apply anti-spoofing enforcement.</span></span>
  
<span data-ttu-id="15813-410">不過，如果*沒有*的收件者網域的 MX 記錄指向 Office 365，即使沒有在 Office 365 前方的另一個服務，然後您應該停用反詐騙。</span><span class="sxs-lookup"><span data-stu-id="15813-410">However, if the MX record of the recipient domain  *does*  point to Office 365, even though there is another service in front of Office 365, then you should disable anti-spoofing.</span></span> <span data-ttu-id="15813-411">最常見的範例是透過收件者修正：</span><span class="sxs-lookup"><span data-stu-id="15813-411">The most common example is through the use of a recipient rewrite:</span></span> 
  
![收件者修正路由圖表](media/070d90d1-50a0-42e4-9fd3-920bc99a7cad.jpg)
  
<span data-ttu-id="15813-413">網域 contoso.com 的 MX 記錄指向內部部署伺服器，雖然網域 @office365.contoso.net 的 MX 記錄指向 Office 365 因為它包含\*。 protection.outlook.com，或\*。 eo.outlook.com MX 記錄中：</span><span class="sxs-lookup"><span data-stu-id="15813-413">The domain contoso.com's MX record points to the on-premises server, while the domain @office365.contoso.net's MX record points to Office 365 because it contains \*.protection.outlook.com, or \*.eo.outlook.com in the MX record:</span></span>
  
![MX 記錄指向 Office 365，因此可能收件者修正](media/4101ad51-ef92-4907-b466-b41d14d344ca.jpg)
  
<span data-ttu-id="15813-415">請務必區別當收件者網域的 MX 記錄未指向 Office 365，以及當它已經過收件者修正。</span><span class="sxs-lookup"><span data-stu-id="15813-415">Be sure to differentiate when a recipient domain's MX record does not point to Office 365, and when it has undergone a recipient rewrite.</span></span> <span data-ttu-id="15813-416">請務必告知這兩種情況之間的差異。</span><span class="sxs-lookup"><span data-stu-id="15813-416">It is important to tell the difference between these two cases.</span></span>
  
<span data-ttu-id="15813-417">如果您不確定您接收網域已經過收件者修正，有時候您可以告訴可以查看郵件標頭。</span><span class="sxs-lookup"><span data-stu-id="15813-417">If you are unsure whether or not your receiving domain has undergone a recipient-rewrite, sometimes you can tell by looking at the message headers.</span></span>
  
<span data-ttu-id="15813-418">） 第一次，查看的 Authentication-results 標頭中的收件者網域的郵件標頭：</span><span class="sxs-lookup"><span data-stu-id="15813-418">a) First, look at the headers in the message for the recipient domain in the Authentication-Results header:</span></span>
  
```
Authentication-Results: spf=fail (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; office365.contoso.net; dkim=fail
  (body hash did not verify) header.d=simple.example.com;
  office365.contoso.net; dmarc=none action=none
  header.from=example.com; compauth=fail reason=001
```

<span data-ttu-id="15813-419">粗體紅色的文字上方，在此案例的 office365.contoso.net 中找到的收件者的網域。</span><span class="sxs-lookup"><span data-stu-id="15813-419">The recipient domain is found in the bold red text above, in this case office365.contoso.net.</span></span> <span data-ttu-id="15813-420">這可能會不同，在 [至收件者： 標頭：</span><span class="sxs-lookup"><span data-stu-id="15813-420">This may be different that the recipient in the To: header:</span></span>
  
<span data-ttu-id="15813-421">收件者： 範例收件者\<@ contoso.com 收件者\></span><span class="sxs-lookup"><span data-stu-id="15813-421">To: Example Recipient \<recipient @ contoso.com\></span></span>
  
<span data-ttu-id="15813-422">執行實際的收件者網域的 MX 記錄查閱。</span><span class="sxs-lookup"><span data-stu-id="15813-422">Perform an MX-record lookup of the actual recipient domain.</span></span> <span data-ttu-id="15813-423">如果它包含\*。 protection.outlook.com、 mail.messaging.microsoft.com， \*。 eo.outlook.com 或 mail.global.frontbridge.com，表示 MX 指向 Office 365。</span><span class="sxs-lookup"><span data-stu-id="15813-423">If it contains \*.protection.outlook.com, mail.messaging.microsoft.com, \*.eo.outlook.com, or mail.global.frontbridge.com, that means that the MX points to Office 365.</span></span>
  
<span data-ttu-id="15813-424">如果它不包含這些值，就表示 MX 未指向 Office 365。</span><span class="sxs-lookup"><span data-stu-id="15813-424">If it does not contain those values, then it means that the MX does not point to Office 365.</span></span> <span data-ttu-id="15813-425">您可以使用來驗證這項工具是 MX 工具箱。</span><span class="sxs-lookup"><span data-stu-id="15813-425">One tool you can use to verify this is MX Toolbox.</span></span>
  
<span data-ttu-id="15813-426">針對此特定的範例，下列指出該 contoso.com，看起來像收件者，因為它至網域： 標頭中，有 MX 記錄指向內部部署伺服器：</span><span class="sxs-lookup"><span data-stu-id="15813-426">For this particular example, the following says that contoso.com, the domain that looks like the recipient since it was the To: header, has MX record points to an on-prem server:</span></span>
  
![MX 記錄指向內部部署伺服器](media/2444144a-9a90-4319-96b2-d115041f669f.jpg)
  
<span data-ttu-id="15813-428">不過，實際的收件者是的 office365.contoso.net 其 MX 記錄並未指向 Office 365:</span><span class="sxs-lookup"><span data-stu-id="15813-428">However, the actual recipient is office365.contoso.net whose MX record does point to Office 365:</span></span>
  
![MX 指向 Office 365，必須是收件者修正](media/10cf3245-9b50-475a-b655-d8a51f99d812.jpg)
  
<span data-ttu-id="15813-430">因此，此郵件可能已經過收件者修正。</span><span class="sxs-lookup"><span data-stu-id="15813-430">Therefore, this message has likely undergone a recipient-rewrite.</span></span>
  
<span data-ttu-id="15813-431">b） 第二，請務必區分的收件者重的一般使用案例。</span><span class="sxs-lookup"><span data-stu-id="15813-431">b) Second, be sure to distinguish between common use cases of recipient rewrites.</span></span> <span data-ttu-id="15813-432">如果您要重新寫入收件者的網域，以\*。.onmicrosoft.com，改為寫入至\*。 mail.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="15813-432">If you are going to rewrite the recipient domain to \*.onmicrosoft.com, instead rewrite it to \*.mail.onmicrosoft.com.</span></span>
  
<span data-ttu-id="15813-433">一旦您已識別背後另一部伺服器路由傳送的最後一個收件者網域和收件者網域的 MX 記錄實際上會指向 Office 365 （如發佈在其 DNS 記錄），您可能會繼續進行若要停用反詐騙。</span><span class="sxs-lookup"><span data-stu-id="15813-433">Once you have identified the final recipient domain that is routed behind another server and the recipient domain's MX record actually points to Office 365 (as published in its DNS records), you may proceed to disable anti-spoofing.</span></span>
  
<span data-ttu-id="15813-434">請記住，您不想停用反詐騙如果網域的路由路徑中的第一個躍點時，Office 365 中，只是一或多個服務背後。</span><span class="sxs-lookup"><span data-stu-id="15813-434">Remember, you don't want to disable anti-spoofing if the domain's first hop in the routing path is Office 365, only when it's behind one or more services.</span></span>
  
### <a name="how-to-disable-anti-spoofing"></a><span data-ttu-id="15813-435">如何停用反詐騙</span><span class="sxs-lookup"><span data-stu-id="15813-435">How to disable anti-spoofing</span></span>

<span data-ttu-id="15813-436">如果您已經建立反網路釣魚原則，請將 EnableAntispoofEnforcement 參數設定為 $false:</span><span class="sxs-lookup"><span data-stu-id="15813-436">If you already have an Anti-phishing policy created, set the EnableAntispoofEnforcement parameter to $false:</span></span>
  
```
$name = "<name of policy>"
Set-AntiphishPolicy -Identity $name -EnableAntiSpoofEnforcement $false

```

<span data-ttu-id="15813-437">如果您不知道要停用的原則 （或原則） 的名稱，則可以將它們顯示：</span><span class="sxs-lookup"><span data-stu-id="15813-437">If you don't know the name of the policy (or policies) to disable, you can display them:</span></span>
  
```
Get-AntiphishPolicy | fl Name
```

<span data-ttu-id="15813-438">如果您沒有任何現有的防網路釣魚原則，您可以建立一個並再將其關閉 （即使您不需要原則反詐騙是仍套用; 稍後在 2018年、 將為您建立的預設原則，可以再停用，而不是建立一個）.</span><span class="sxs-lookup"><span data-stu-id="15813-438">If you don't have any existing anti-phishing policies, you can create one and then disable it (even if you don't have a policy, anti-spoofing is still applied; later on in 2018, a default policy will be created for you and you can then disable that instead of creating one).</span></span> <span data-ttu-id="15813-439">您必須在多個步驟中執行這項操作：</span><span class="sxs-lookup"><span data-stu-id="15813-439">You will have to do this in multiple steps:</span></span>
  
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

<span data-ttu-id="15813-440">停用反詐騙只有透過指令程式 (稍後將會出現在 [安全性&amp;合規性中心)。</span><span class="sxs-lookup"><span data-stu-id="15813-440">Disabling anti-spoofing is only available via cmdlet (later it will be available in the Security &amp; Compliance Center).</span></span> <span data-ttu-id="15813-441">如果您不具備 PowerShell 存取權，建立支援票證。</span><span class="sxs-lookup"><span data-stu-id="15813-441">If you do not have access to PowerShell, create a support ticket.</span></span>
  
<span data-ttu-id="15813-442">請記住，這只應該套用到經歷間接路由傳送至 Office 365 時的網域。</span><span class="sxs-lookup"><span data-stu-id="15813-442">Remember, this should only be applied to domains that undergo indirect routing when sent to Office 365.</span></span> <span data-ttu-id="15813-443">抵禦若要停用反詐騙 」，因為某些誤判誘惑，它會是比較好的作法，長期透過其運作。</span><span class="sxs-lookup"><span data-stu-id="15813-443">Resist the temptation to disable anti-spoofing because of some false positives, it will be better in the long run to work through them.</span></span>
  
### <a name="information-for-individual-users"></a><span data-ttu-id="15813-444">針對個別使用者的資訊</span><span class="sxs-lookup"><span data-stu-id="15813-444">Information for individual users</span></span>

<span data-ttu-id="15813-445">個別使用者僅限於它們如何互動的反詐騙安全提示使用。</span><span class="sxs-lookup"><span data-stu-id="15813-445">Individual users are limited in how they can interact with the anti-spoofing safety tip.</span></span> <span data-ttu-id="15813-446">不過，有幾件事，您可以解決常見的案例。</span><span class="sxs-lookup"><span data-stu-id="15813-446">However, there are several things you can do to resolve common scenarios.</span></span>
  
### <a name="common-scenario-1---mailbox-forwarding"></a><span data-ttu-id="15813-447">常見的案例 #1-信箱轉寄功能</span><span class="sxs-lookup"><span data-stu-id="15813-447">Common scenario #1 - Mailbox forwarding</span></span>

<span data-ttu-id="15813-448">如果您使用另一個電子郵件服務，並將您的電子郵件轉寄給 Office 365 或 Outlook.com，您的電子郵件可能會標示為詐騙和接收的紅色的安全提示。</span><span class="sxs-lookup"><span data-stu-id="15813-448">If you use another email service and forward your email to Office 365 or Outlook.com, your email may be marked as spoofing and receive a red safety tip.</span></span> <span data-ttu-id="15813-449">Office 365 和 Outlook.com 計劃自動解決這個問題時轉寄站是下列其中一個 Outlook.com、 Office 365、 Gmail 或任何其他服務，會使用[弧度通訊協定](https://arc-spec.org)。</span><span class="sxs-lookup"><span data-stu-id="15813-449">Office 365 and Outlook.com plan to address this automatically when the forwarder is one of Outlook.com, Office 365, Gmail, or any other service that uses the [ARC protocol](https://arc-spec.org).</span></span> <span data-ttu-id="15813-450">不過，直到部署修正的目標，則使用者應該使用連接的帳戶功能直接匯入他們的郵件，而不是使用 [轉寄] 選項。</span><span class="sxs-lookup"><span data-stu-id="15813-450">However, until that fix is deployed, users should use the Connected Accounts feature to import their messages directly, rather than using the forwarding option.</span></span>
  
<span data-ttu-id="15813-451">若要設定已連線的帳戶，在 Office 365 中，選取 [齒輪圖示中右上角的 Office 365 web 介面\>郵件\>郵件\>帳戶\>連線的帳戶。</span><span class="sxs-lookup"><span data-stu-id="15813-451">To set up connected accounts in Office 365, select the Gear icon in the top right corner of the Office 365 web interface \> Mail \> Mail \> Accounts \> Connected accounts.</span></span>
  
![Office 365-連接帳戶] 選項](media/e8e841ca-8861-4d83-8506-2a0858c51010.jpg)
  
<span data-ttu-id="15813-453">在 Outlook.com 中的程序是齒輪圖示\>選項\>郵件\>帳戶\>連線的帳戶。</span><span class="sxs-lookup"><span data-stu-id="15813-453">In Outlook.com, the process is the Gear icon \> Options \> Mail \> Accounts \> Connected accounts.</span></span>
  
### <a name="common-scenario-2---discussion-lists"></a><span data-ttu-id="15813-454">常見的案例 #2-討論區清單</span><span class="sxs-lookup"><span data-stu-id="15813-454">Common scenario #2 - Discussion lists</span></span>

<span data-ttu-id="15813-455">討論區清單已知會有問題的反詐騙方式因為它們轉寄訊息和修改其內容仍保留從原始： 地址。</span><span class="sxs-lookup"><span data-stu-id="15813-455">Discussion lists are known to have problems with anti-spoofing due to the way they forward the message and modify its contents yet retain the original From: address.</span></span>
  
<span data-ttu-id="15813-456">例如，假設您的電子郵件地址使用者 @ contoso.com，且您感興趣小鳥監控並加入 @ example.com 討論區清單 birdwatchers。</span><span class="sxs-lookup"><span data-stu-id="15813-456">For example, suppose your email address is user @ contoso.com, and you are interested in Bird Watching and join the discussion list birdwatchers @ example.com.</span></span> <span data-ttu-id="15813-457">當您將郵件傳送至討論區清單時，您可能會傳送其這種方式：</span><span class="sxs-lookup"><span data-stu-id="15813-457">When you send a message to the discussion list, you might send it this way:</span></span>
  
<span data-ttu-id="15813-458">**從：** John Doe \<@ contoso.com 的使用者\></span><span class="sxs-lookup"><span data-stu-id="15813-458">**From:** John Doe \<user @ contoso.com\></span></span> 
  
<span data-ttu-id="15813-459">**至：** Birdwatcher 的討論區清單\<birdwatchers @ example.com\></span><span class="sxs-lookup"><span data-stu-id="15813-459">**To:** Birdwatcher's Discussion List \<birdwatchers @ example.com\></span></span> 
  
<span data-ttu-id="15813-460">**Subject:** 絕佳檢視的藍色 jays 周頂端</span><span class="sxs-lookup"><span data-stu-id="15813-460">**Subject:** Great viewing of blue jays at the top of Mt.</span></span> <span data-ttu-id="15813-461">火山本週</span><span class="sxs-lookup"><span data-stu-id="15813-461">Rainier this week</span></span> 
  
<span data-ttu-id="15813-462">任何人都要取出檢視從周本週</span><span class="sxs-lookup"><span data-stu-id="15813-462">Anyone want to check out the viewing this week from Mt.</span></span> <span data-ttu-id="15813-463">火山嗎？</span><span class="sxs-lookup"><span data-stu-id="15813-463">Rainier?</span></span>
  
<span data-ttu-id="15813-464">當電子郵件清單接收郵件時，它們格式化郵件、 修改它的內容，並重播其餘部分所組成的參與者許多不同的電子郵件接收器討論區清單上的成員。</span><span class="sxs-lookup"><span data-stu-id="15813-464">When the email list receives the message, they format the message, modify its contents, and replay it to the rest of the members on the discussion list which is made up of participants from many different email receivers.</span></span>
  
<span data-ttu-id="15813-465">**從：** John Doe \<@ contoso.com 的使用者\></span><span class="sxs-lookup"><span data-stu-id="15813-465">**From:** John Doe \<user @ contoso.com\></span></span> 
  
<span data-ttu-id="15813-466">**至：** Birdwatcher 的討論區清單\<birdwatchers @ example.com\></span><span class="sxs-lookup"><span data-stu-id="15813-466">**To:** Birdwatcher's Discussion List \<birdwatchers @ example.com\></span></span> 
  
<span data-ttu-id="15813-467">**Subject:**[BIRDWATCHERS]絕佳檢視的藍色 jays 周頂端</span><span class="sxs-lookup"><span data-stu-id="15813-467">**Subject:** [BIRDWATCHERS] Great viewing of blue jays at the top of Mt.</span></span> <span data-ttu-id="15813-468">火山本週</span><span class="sxs-lookup"><span data-stu-id="15813-468">Rainier this week</span></span> 
  
<span data-ttu-id="15813-469">任何人都要取出檢視從周本週</span><span class="sxs-lookup"><span data-stu-id="15813-469">Anyone want to check out the viewing this week from Mt.</span></span> <span data-ttu-id="15813-470">火山嗎？</span><span class="sxs-lookup"><span data-stu-id="15813-470">Rainier?</span></span>
  
---
  
<span data-ttu-id="15813-471">此訊息已傳送至 Birdwatchers 討論區清單。</span><span class="sxs-lookup"><span data-stu-id="15813-471">This message was sent to the Birdwatchers Discussion List.</span></span> <span data-ttu-id="15813-472">您可以隨時取消訂閱。</span><span class="sxs-lookup"><span data-stu-id="15813-472">You can unsubscribe at any time.</span></span>
  
<span data-ttu-id="15813-473">在上述，重新執行的郵件已經從相同： 地址 （@ contoso.com 的使用者） 但原始郵件，已由將標記新增至 [主旨] 行中和郵件底端頁尾中進行修改。</span><span class="sxs-lookup"><span data-stu-id="15813-473">In the above, the replayed message has the same From: address (user @ contoso.com) but the original message has been modified by adding a tag to the Subject line, and a footer to the bottom of the message.</span></span> <span data-ttu-id="15813-474">這種類型的訊息修改在郵件清單中很常見，而可能導致誤判。</span><span class="sxs-lookup"><span data-stu-id="15813-474">This type of message modification is common in mailing lists, and may result in false positives.</span></span>
  
<span data-ttu-id="15813-475">如果您或貴組織中的人員郵寄清單的管理員，您可以將它設定成通過反詐騙檢查。</span><span class="sxs-lookup"><span data-stu-id="15813-475">If you or someone in your organization is an administrator of the mailing list, you may be able to configure it to pass anti-spoofing checks.</span></span>
  
- <span data-ttu-id="15813-476">檢查 dmarc.org 常見問題集：[我操作郵寄清單我想要與 DMARC 交互操作，我該怎麼辦？](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F)</span><span class="sxs-lookup"><span data-stu-id="15813-476">Check the FAQ at DMARC.org: [I operate a mailing list and I want to interoperate with DMARC, what should I do?](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F)</span></span>

- <span data-ttu-id="15813-477">閱讀此部落格文章的指示：[使用 DMARC 來避免失敗交互操作的郵寄清單運算子提示](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/)</span><span class="sxs-lookup"><span data-stu-id="15813-477">Read the instructions at this blog post: [A tip for mailing list operators to interoperate with DMARC to avoid failures](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/)</span></span>

- <span data-ttu-id="15813-478">請考慮支援弧線中點，請參閱郵寄清單伺服器上安裝更新[https://arc-spec.org](https://arc-spec.org/)</span><span class="sxs-lookup"><span data-stu-id="15813-478">Consider installing updates on your mailing list server to support ARC, see [https://arc-spec.org](https://arc-spec.org/)</span></span>

<span data-ttu-id="15813-479">如果您不需要的郵件清單的擁有權：</span><span class="sxs-lookup"><span data-stu-id="15813-479">If you do not have ownership of the mailing list:</span></span>
  
- <span data-ttu-id="15813-480">您可以要求郵寄清單維護的程式，來實作其中一個選項上述 （他們應該也會有電子郵件驗證為郵寄清單轉送從網域設定）</span><span class="sxs-lookup"><span data-stu-id="15813-480">You can request the maintainer of the mailing list to implement one of the options above (they should also have email authentication set up for the domain the mailing list is relaying from)</span></span>

- <span data-ttu-id="15813-481">您可以在您的電子郵件用戶端，將郵件移至收件匣中建立信箱規則。</span><span class="sxs-lookup"><span data-stu-id="15813-481">You can create mailbox rules in your email client to move messages to the Inbox.</span></span> <span data-ttu-id="15813-482">您也可以要求您的組織系統管理員設定允許規則，或一節中討論覆寫為管理合法寄件者所傳送未驗證的電子郵件</span><span class="sxs-lookup"><span data-stu-id="15813-482">You can also request your organization's administrators to set up allow rules, or overrides as discussed in the section Managing legitimate senders who are sending unauthenticated email</span></span>

- <span data-ttu-id="15813-483">您可以使用 Office 365，以建立要把它當成合法郵寄清單覆寫建立支援票證</span><span class="sxs-lookup"><span data-stu-id="15813-483">You can create a support ticket with Office 365 to create an override for the mailing list to treat it as legitimate</span></span>

### <a name="other-scenarios"></a><span data-ttu-id="15813-484">其他案例</span><span class="sxs-lookup"><span data-stu-id="15813-484">Other scenarios</span></span>

1. <span data-ttu-id="15813-485">如果這兩個以上的常見案例適用於您的情況，郵件，則為 false 正數後向 Microsoft 報告郵件。</span><span class="sxs-lookup"><span data-stu-id="15813-485">If neither of the above common scenarios applies to your situation, report the message as a false positive back to Microsoft.</span></span> <span data-ttu-id="15813-486">如需詳細資訊，請參閱一節[方式可以我回報垃圾郵件或非垃圾郵件給 Microsoft？](#how-can-i-report-spam-or-non-spam-messages-back-to-microsoft)本文稍後。</span><span class="sxs-lookup"><span data-stu-id="15813-486">For more information, see the section [How can I report spam or non-spam messages back to Microsoft?](#how-can-i-report-spam-or-non-spam-messages-back-to-microsoft) later in this article.</span></span> 

2. <span data-ttu-id="15813-487">您也可以連絡可以引發為與 Microsoft 支援票證您電子郵件系統管理員。</span><span class="sxs-lookup"><span data-stu-id="15813-487">You may also contact your email administrator who can raise it as a support ticket with Microsoft.</span></span> <span data-ttu-id="15813-488">Microsoft 工程團隊將調查為何郵件被標示為詐騙。</span><span class="sxs-lookup"><span data-stu-id="15813-488">The Microsoft engineering team will investigate why the message was marked as a spoof.</span></span>

3. <span data-ttu-id="15813-489">此外，如果您知道誰寄件者且有自信它們不被惡意會遭到詐騙，您可能會回覆回到寄件者指出他們會從不會驗證郵件伺服器傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="15813-489">Additionally, if you know who the sender is and are confident they are not being maliciously spoofed, you may reply back to the sender indicating that they are sending messages from a mail server that does not authenticate.</span></span> <span data-ttu-id="15813-490">這有時會導致連絡其 IT 系統管理員，就會設定必要的電子郵件驗證記錄原始寄件者。</span><span class="sxs-lookup"><span data-stu-id="15813-490">This sometimes results in the original sender contacting their IT administrator who will set up the required email authentication records.</span></span>
  
<span data-ttu-id="15813-491">當足夠的寄件者回覆回到網域擁有者，他們應該設定電子郵件驗證記錄時，它 spurs 它們採取的動作。</span><span class="sxs-lookup"><span data-stu-id="15813-491">When enough senders reply back to domain owners that they should set up email authentication records, it spurs them into taking action.</span></span> <span data-ttu-id="15813-492">雖然 Microsoft 也可用於發佈所需的記錄的網域擁有者，它可以協助更為個別使用者要求時才。</span><span class="sxs-lookup"><span data-stu-id="15813-492">While Microsoft also works with domain owners to publish the required records, it helps even more when individual users request it.</span></span>

4. <span data-ttu-id="15813-493">（選用），將寄件者新增至您的安全寄件者清單。</span><span class="sxs-lookup"><span data-stu-id="15813-493">Optionally, add the sender to your Safe Senders list.</span></span> <span data-ttu-id="15813-494">然而，請注意，如果 phisher 假裝該帳戶，它將會傳遞至您的信箱。</span><span class="sxs-lookup"><span data-stu-id="15813-494">However, be aware that if a phisher spoofs that account, it will be delivered to your mailbox.</span></span> <span data-ttu-id="15813-495">因此，應該謹慎使用此選項。</span><span class="sxs-lookup"><span data-stu-id="15813-495">Therefore, this option should be used sparingly.</span></span>

## <a name="how-senders-to-microsoft-should-prepare-for-anti-spoofing-protection"></a><span data-ttu-id="15813-496">Microsoft 的寄件者應如何準備反詐騙保護</span><span class="sxs-lookup"><span data-stu-id="15813-496">How senders to Microsoft should prepare for anti-spoofing protection</span></span>

<span data-ttu-id="15813-497">如果您是系統管理員及目前將郵件傳送給 Microsoft 的 Office 365 或 Outlook.com 中，您應該確定已正確地驗證您的電子郵件可能將它標示為垃圾郵件或釣魚程式的否則。</span><span class="sxs-lookup"><span data-stu-id="15813-497">If you are an administrator who currently sends messages to Microsoft, either Office 365 or Outlook.com, you should ensure that your email is properly authenticated otherwise it may be marked as spam or phish.</span></span>
  
### <a name="customers-of-office-365"></a><span data-ttu-id="15813-498">Office 365 的客戶</span><span class="sxs-lookup"><span data-stu-id="15813-498">Customers of Office 365</span></span>

<span data-ttu-id="15813-499">如果您是 Office 365 客戶，而且您使用 Office 365 來傳送外寄電子郵件：</span><span class="sxs-lookup"><span data-stu-id="15813-499">If you are an Office 365 customer and you use Office 365 to send outbound email:</span></span>
  
- <span data-ttu-id="15813-500">為您的網域，[以協助防止詐騙的 Office 365 中設定 spf](set-up-spf-in-office-365-to-help-prevent-spoofing.md)</span><span class="sxs-lookup"><span data-stu-id="15813-500">For your domains, [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)</span></span>

- <span data-ttu-id="15813-501">為您主要的網域，[使用 DKIM 驗證從您在 Office 365 中的自訂網域傳送的外寄電子郵件](use-dkim-to-validate-outbound-email.md)</span><span class="sxs-lookup"><span data-stu-id="15813-501">For your primary domains, [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md)</span></span>

- <span data-ttu-id="15813-502">[考慮 DMARC 的記錄設定](use-dmarc-to-validate-email.md)為您的網域至判斷誰是您合法的寄件者</span><span class="sxs-lookup"><span data-stu-id="15813-502">[Consider setting up DMARC records](use-dmarc-to-validate-email.md) for your domain to determine who are your legitimate senders</span></span>

<span data-ttu-id="15813-503">Microsoft 並不提供詳細的實作指導方針的每個 SPF、 DKIM 和 DMARC。</span><span class="sxs-lookup"><span data-stu-id="15813-503">Microsoft does not provide detailed implementation guidelines for each of SPF, DKIM, and DMARC.</span></span> <span data-ttu-id="15813-504">不過，有很多線上發佈的資訊。</span><span class="sxs-lookup"><span data-stu-id="15813-504">However, there is a lot of information published online.</span></span> <span data-ttu-id="15813-505">也有 3rd 廠商公司致力於協助您設定電子郵件驗證記錄的組織。</span><span class="sxs-lookup"><span data-stu-id="15813-505">There are also 3rd party companies dedicated to helping your organization set up email authentication records.</span></span>
  
### <a name="administrators-of-domains-that-are-not-office-365-customers"></a><span data-ttu-id="15813-506">不是 Office 365 客戶的網域的系統管理員</span><span class="sxs-lookup"><span data-stu-id="15813-506">Administrators of domains that are not Office 365 customers</span></span>

<span data-ttu-id="15813-507">如果您是網域系統管理員，但不是 Office 365 客戶：</span><span class="sxs-lookup"><span data-stu-id="15813-507">If you are a domain administrator but are not an Office 365 customer:</span></span>
  
- <span data-ttu-id="15813-508">您應該設定 spf 以發佈您的網域傳送的 IP 位址和也設定 dkim （如果有的話） 來數位簽署的郵件。</span><span class="sxs-lookup"><span data-stu-id="15813-508">You should set up SPF to publish your domain's sending IP addresses, and also set up DKIM (if available) to digitally sign messages.</span></span> <span data-ttu-id="15813-509">您也可能會考慮設定 DMARC 的記錄。</span><span class="sxs-lookup"><span data-stu-id="15813-509">You may also consider setting up DMARC records.</span></span>

- <span data-ttu-id="15813-510">如果您有大量的寄件者傳輸代表您的電子郵件，您應該使用它們來傳送電子郵件的方式，在 [從的傳送端網域： 地址 （如果它屬於您） 配合通過 SPF 或 DMARC 的網域。</span><span class="sxs-lookup"><span data-stu-id="15813-510">If you have bulk senders who are transmitting email on your behalf, you should work with them to send email in a way such that the sending domain in the From: address (if it belongs to you) aligns with the domain that passes SPF or DMARC.</span></span>

- <span data-ttu-id="15813-511">如果您有內部部署郵件伺服器，或傳送從軟體為-服務提供者，或從雲端主控服務，例如 Microsoft Azure、 GoDaddy、 Rackspace Amazon Web 服務，或類似，您應該確定他們已新增至您的 SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="15813-511">If you have on-premises mail servers, or send from a Software-as-a-service provider, or from a cloud-hosting service like Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services, or similar, you should ensure that they are added to your SPF record.</span></span>

- <span data-ttu-id="15813-512">如果您的 ISP 所裝載的小型網域，您應該設定您的 SPF 記錄根據指示您的 ISP 所提供給您。</span><span class="sxs-lookup"><span data-stu-id="15813-512">If you are a small domain that is hosted by an ISP, you should set up your SPF record according to the instructions that is provided to you by your ISP.</span></span> <span data-ttu-id="15813-513">大部分的 Isp 提供這些類型的指示，以及可以找到該公司支援頁面上。</span><span class="sxs-lookup"><span data-stu-id="15813-513">Most ISPs provide these types of instructions and can be found on the company's support pages.</span></span>

- <span data-ttu-id="15813-514">即使尚未發佈電子郵件之前，先驗證記錄和它的正常運作，您仍然必須發佈電子郵件驗證記錄傳送給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="15813-514">Even if you have not had to publish email authentication records before, and it worked fine, you must still publish email authentication records to send to Microsoft.</span></span> <span data-ttu-id="15813-515">如此一來，您會在網路釣魚，對抗幫助，並降低您傳送給，組織會收到 phished。</span><span class="sxs-lookup"><span data-stu-id="15813-515">By doing so, you are helping in the fight against phishing, and reducing the possibility that either you, or organizations you send to, will get phished.</span></span>

### <a name="what-if-you-dont-know-who-sends-email-as-your-domain"></a><span data-ttu-id="15813-516">如果您不知道誰做為您網域傳送電子郵件？</span><span class="sxs-lookup"><span data-stu-id="15813-516">What if you don't know who sends email as your domain?</span></span>

<span data-ttu-id="15813-517">許多網域不要發行 SPF 記錄，因為它們不知道其所有寄件者屬於。</span><span class="sxs-lookup"><span data-stu-id="15813-517">Many domains do not publish SPF records because they do not know who all their senders are.</span></span> <span data-ttu-id="15813-518">沒關係，您不需要知道誰全都是。</span><span class="sxs-lookup"><span data-stu-id="15813-518">That's okay, you do not need to know who all of them are.</span></span> <span data-ttu-id="15813-519">相反地，您應該開始發佈您知道，尤其是您公司的流量的所在位置，和發佈中性 SPF 原則] 中，為的 SPF 記錄？ 所有：</span><span class="sxs-lookup"><span data-stu-id="15813-519">Instead, you should get started by publishing an SPF record for the ones you do know of, especially where your corporate traffic is located, and publish a neutral SPF policy, ?all:</span></span>
  
<span data-ttu-id="15813-520">example.com IN TXT 」 v = spf1 include:spf.example.com？ 所有 」</span><span class="sxs-lookup"><span data-stu-id="15813-520">example.com IN TXT "v=spf1 include:spf.example.com ?all"</span></span>
  
<span data-ttu-id="15813-521">中性 SPF 原則表示任何有超出您公司的基礎結構的電子郵件會傳送電子郵件驗證所有其他電子郵件接收器。</span><span class="sxs-lookup"><span data-stu-id="15813-521">The neutral SPF policy means that any email that comes out of your corporate infrastructure will pass email authentication at all other email receivers.</span></span> <span data-ttu-id="15813-522">來自您不了解寄件者的電子郵件將會回復為 neutral、 幾乎相同，所有發佈沒有 SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="15813-522">Email that comes from senders you don't know about will fall back to neutral, which is almost the same as publishing no SPF record at all.</span></span>
  
<span data-ttu-id="15813-523">傳送到 Office 365 時，將會是來自您公司的流量的電子郵件標示為通過驗證，但來自您不了解的來源電子郵件仍可能會標示為詐騙 （取決於 Office 365 可以以隱含方式來驗證它）。</span><span class="sxs-lookup"><span data-stu-id="15813-523">When sending to Office 365, email that comes from your corporate traffic will be marked as authenticated, but the email that comes from sources you don't know about may still be marked as spoof (depending upon whether or not Office 365 can implicitly authenticate it).</span></span> <span data-ttu-id="15813-524">不過，這仍然是從所有電子郵件被標示為詐騙由 Office 365 改進。</span><span class="sxs-lookup"><span data-stu-id="15813-524">However, this is still an improvement from all email being marked as spoof by Office 365.</span></span>
  
<span data-ttu-id="15813-525">一旦您已取得入門的後援原則與 SPF 記錄？ 所有，您可以逐步包含更傳送基礎結構，並再將發佈更嚴格的原則。</span><span class="sxs-lookup"><span data-stu-id="15813-525">Once you've gotten started with an SPF record with a fallback policy of ?all, you can gradually include more and more sending infrastructure and then publish a stricter policy.</span></span> 
  
### <a name="what-if-you-are-the-owner-of-a-mailing-list"></a><span data-ttu-id="15813-526">如果要擁有者的郵件清單？</span><span class="sxs-lookup"><span data-stu-id="15813-526">What if you are the owner of a mailing list?</span></span>

<span data-ttu-id="15813-527">請參閱[常見的案例 #2-討論區清單](#common-scenario-2---discussion-lists)一節。</span><span class="sxs-lookup"><span data-stu-id="15813-527">See the section [Common scenario #2 - Discussion lists](#common-scenario-2---discussion-lists).</span></span>
  
### <a name="what-if-you-are-an-infrastructure-provider-such-as-an-internet-service-provider-isp-email-service-provider-esp-or-cloud-hosting-service"></a><span data-ttu-id="15813-528">如果您是基礎結構提供者，例如網際網路服務提供者 (ISP)、 電子郵件服務提供者 (ESP) 或雲端託管服務？</span><span class="sxs-lookup"><span data-stu-id="15813-528">What if you are an infrastructure provider such as an Internet Service Provider (ISP), Email Service Provider (ESP), or cloud hosting service?</span></span>

<span data-ttu-id="15813-529">如果裝載網域的電子郵件，且其傳送電子郵件，或提供主控的基礎結構，可以傳送電子郵件，您應該執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="15813-529">If you host a domain's email, and it sends email, or provide hosting infrastructure that can send email, you should do the following:</span></span>
  
- <span data-ttu-id="15813-530">確保客戶擁有細部要在其 SPF 記錄中發佈的文件</span><span class="sxs-lookup"><span data-stu-id="15813-530">Ensure your customers have documentation detailing what to publish in their SPF records</span></span>

- <span data-ttu-id="15813-531">請考慮登入外寄電子郵件的 DKIM 簽章，即使客戶不會明確設定它 （符號與預設網域）。</span><span class="sxs-lookup"><span data-stu-id="15813-531">Consider signing DKIM-signatures on outbound email even if the customer doesn't explicitly set it up (sign with a default domain).</span></span> <span data-ttu-id="15813-532">您可以偶數雙登 （一次與客戶的網域，如果他們有設定它，第二次與貴公司的 DKIM 簽章） 的 DKIM 簽章的電子郵件</span><span class="sxs-lookup"><span data-stu-id="15813-532">You can even double-sign the email with DKIM signatures (once with the customer's domain if they have set it up, and a second time with your company's DKIM signature)</span></span>

<span data-ttu-id="15813-533">即使您驗證電子郵件來自您的平台，但至少它可確保 Microsoft 不會不垃圾電子郵件因為它不會驗證，請務必遵循傳送給 Microsoft 並不保證。</span><span class="sxs-lookup"><span data-stu-id="15813-533">Deliverability to Microsoft is not guaranteed even if you authenticate email originating from your platform, but at least it ensures that Microsoft does not junk your email because it is not authenticated.</span></span> <span data-ttu-id="15813-534">周圍 Outlook.com 如何篩選電子郵件的詳細資訊，請參閱[Outlook.com 郵件管理員] 頁面](https://postmaster.live.com/pm/postmaster.aspx)。</span><span class="sxs-lookup"><span data-stu-id="15813-534">For more details around how Outlook.com filters email, see the [Outlook.com Postmaster page](https://postmaster.live.com/pm/postmaster.aspx).</span></span>
  
<span data-ttu-id="15813-535">如需詳細的服務提供者最佳作法的詳細資訊，請參閱 < <b0>M3AAWG 行動通訊的最佳作法服務提供者</b0>。</span><span class="sxs-lookup"><span data-stu-id="15813-535">For more details on service providers best practices, see [M3AAWG Mobile Messaging Best Practices for Service Providers](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf).</span></span>
  
## <a name="frequently-asked-questions"></a><span data-ttu-id="15813-536">常見問題集</span><span class="sxs-lookup"><span data-stu-id="15813-536">Frequently Asked Questions</span></span>

### <a name="why-is-microsoft-making-this-change"></a><span data-ttu-id="15813-537">為什麼 Microsoft 正在進行這項變更？</span><span class="sxs-lookup"><span data-stu-id="15813-537">Why is Microsoft making this change?</span></span>

<span data-ttu-id="15813-538">由於影響的網路釣魚攻擊，和電子郵件驗證已繞 15 年，因為 Microsoft 會認為，繼續允許未經驗證的電子郵件的風險是高於遺失合法電子郵件的風險。</span><span class="sxs-lookup"><span data-stu-id="15813-538">Because of the impact of phishing attacks, and because email authentication has been around for over 15 years, Microsoft believes that the risk of continue to allow unauthenticated email is higher than the risk of losing legitimate email.</span></span>
  
### <a name="will-this-change-cause-legitimate-email-to-be-marked-as-spam"></a><span data-ttu-id="15813-539">這項變更會導致合法的電子郵件被標示為垃圾郵件？</span><span class="sxs-lookup"><span data-stu-id="15813-539">Will this change cause legitimate email to be marked as spam?</span></span>

<span data-ttu-id="15813-540">首先，會有一些標示為垃圾郵件的郵件。</span><span class="sxs-lookup"><span data-stu-id="15813-540">At first, there will be some messages that are marked as spam.</span></span> <span data-ttu-id="15813-541">不過，經過一段時間，會自動調整寄件者，然後誤標為冒名郵件數量將會極小大部分的電子郵件路徑。</span><span class="sxs-lookup"><span data-stu-id="15813-541">However, over time, senders will adjust and then the amount of messages mislabeled as spoofed will be negligible for most email paths.</span></span>
  
<span data-ttu-id="15813-542">Microsoft 本身先採用這項功能數週，再將其部署至其客戶的其餘部分。</span><span class="sxs-lookup"><span data-stu-id="15813-542">Microsoft itself first adopted this feature several weeks before deploying it to the rest of its customers.</span></span> <span data-ttu-id="15813-543">第一次中斷時，它會逐漸拒絕。</span><span class="sxs-lookup"><span data-stu-id="15813-543">While there was disruption at first, it gradually declined.</span></span>
  
### <a name="will-microsoft-bring-this-feature-to-outlookcom-and-non-advanced-threat-protection-customers-of-office-365"></a><span data-ttu-id="15813-544">將 Microsoft 將帶到 Outlook.com 和非-進階威脅防護的客戶，Office 365 的這項功能嗎？</span><span class="sxs-lookup"><span data-stu-id="15813-544">Will Microsoft bring this feature to Outlook.com and non-Advanced Threat Protection customers of Office 365?</span></span>

<span data-ttu-id="15813-545">Microsoft 的反詐騙技術最初部署給其組織有 Office 365 企業版 E5 訂閱，或有購買其訂閱的 Office 365 進階威脅防護 (ATP) 附加元件。</span><span class="sxs-lookup"><span data-stu-id="15813-545">Microsoft's anti-spoofing technology was initially deployed to its organizations that had an Office 365 Enterprise E5 subscription or had purchased the Office 365 Advanced Threat Protection (ATP) add-on for their subscription.</span></span> <span data-ttu-id="15813-546">截至 2018 年 10 月，我們已擴充，也有 Exchange Online Protection (EOP) 的組織保護。</span><span class="sxs-lookup"><span data-stu-id="15813-546">As of October, 2018 we've extended the protection to organizations that have Exchange Online Protection (EOP) as well.</span></span> <span data-ttu-id="15813-547">在未來，我們可能會對 Outlook.com 釋出它。</span><span class="sxs-lookup"><span data-stu-id="15813-547">In the future, we may release it for Outlook.com.</span></span> <span data-ttu-id="15813-548">不過，如果我們這麼做，可能會有一些功能，例如報告不會套用及自訂會覆寫。</span><span class="sxs-lookup"><span data-stu-id="15813-548">However, if we do, there may be some capabilities that are not applied such as reporting and custom overrides.</span></span>
  
### <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a><span data-ttu-id="15813-549">我如何可以回報垃圾郵件或非垃圾郵件給 Microsoft？</span><span class="sxs-lookup"><span data-stu-id="15813-549">How can I report spam or non-spam messages back to Microsoft?</span></span>

<span data-ttu-id="15813-550">您可以使用此[報告訊息增益集以進行 Outlook](https://support.office.com/article/use-the-report-message-add-in-b5caa9f1-cdf3-4443-af8c-ff724ea719d2)，或如果它不是安裝，[提交垃圾郵件、 非垃圾郵件和網路釣魚詐騙郵件提交給 Microsoft 進行分析](https://technet.microsoft.com/en-us/library/jj200769%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="15813-550">You can either use the [Report Message Add-in for Outlook](https://support.office.com/article/use-the-report-message-add-in-b5caa9f1-cdf3-4443-af8c-ff724ea719d2), or if it isn't installed, [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](https://technet.microsoft.com/en-us/library/jj200769%28v=exchg.150%29.aspx).</span></span>
  
### <a name="im-a-domain-administrator-who-doesnt-know-who-all-my-senders-are"></a><span data-ttu-id="15813-551">我不知道我所有的寄件者屬於網域管理員 ！</span><span class="sxs-lookup"><span data-stu-id="15813-551">I'm a domain administrator who doesn't know who all my senders are!</span></span>

<span data-ttu-id="15813-552">請[系統管理員的網域都不是 Office 365 客戶](#administrators-of-domains-that-are-not-office-365-customers)，參閱。</span><span class="sxs-lookup"><span data-stu-id="15813-552">Please see [Administrators of domains that are not Office 365 customers](#administrators-of-domains-that-are-not-office-365-customers).</span></span>
  
### <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization-even-though-office-365-is-my-primary-filter"></a><span data-ttu-id="15813-553">發生什麼事我停用反詐騙保護我的組織，即使 Office 365 是我主要的篩選條件？</span><span class="sxs-lookup"><span data-stu-id="15813-553">What happens if I disable anti-spoofing protection for my organization, even though Office 365 is my primary filter?</span></span>

<span data-ttu-id="15813-554">我們不建議這因為您將會公開給更多未接的網路釣魚和垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="15813-554">We do not recommend this because you will be exposed to more missed phishing and spam messages.</span></span> <span data-ttu-id="15813-555">並非所有網路釣魚詐騙，並將未接並非所有詐騙。</span><span class="sxs-lookup"><span data-stu-id="15813-555">Not all phishing is spoofing, and not all spoofs will be missed.</span></span> <span data-ttu-id="15813-556">不過，您的風險會高於可讓反詐騙的客戶。</span><span class="sxs-lookup"><span data-stu-id="15813-556">However, your risk will be higher than a customer who enables anti-spoofing.</span></span>
  
### <a name="does-enabling-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a><span data-ttu-id="15813-557">啟用反詐騙保護意思我將會從所有網路釣魚保護？</span><span class="sxs-lookup"><span data-stu-id="15813-557">Does enabling anti-spoofing protection mean I will be protected from all phishing?</span></span>

<span data-ttu-id="15813-558">不幸的是，否，因為網路釣客會調整以使用其他技術，例如： 遭到盜用的帳戶或設定的可用服務的帳戶。</span><span class="sxs-lookup"><span data-stu-id="15813-558">Unfortunately, no, because phishers will adapt to use other techniques such as compromised accounts, or setting up accounts of free services.</span></span> <span data-ttu-id="15813-559">不過，反網路釣魚保護因為 Office 365 的保護層級會一起設計工作將這些偵測其他類型的網路釣魚方法，並建置彼此運作更好。</span><span class="sxs-lookup"><span data-stu-id="15813-559">However, anti-phishing protection works much better to detect these other types of phishing methods because Office 365's protection layers are designed work together and build on top of each other.</span></span>
  
### <a name="do-other-large-email-receivers-block-unauthenticated-email"></a><span data-ttu-id="15813-560">其他大型的電子郵件接收器封鎖未驗證的電子郵件？</span><span class="sxs-lookup"><span data-stu-id="15813-560">Do other large email receivers block unauthenticated email?</span></span>

<span data-ttu-id="15813-561">幾乎所有大型的電子郵件接收器實作傳統 SPF、 DKIM 和 DMARC。</span><span class="sxs-lookup"><span data-stu-id="15813-561">Nearly all large email receivers implement traditional SPF, DKIM, and DMARC.</span></span> <span data-ttu-id="15813-562">某些接收器有其他檢查比只是這些標準，但較少移為 Office 365，以封鎖未驗證的更嚴格的電子郵件並將它們視為詐騙。</span><span class="sxs-lookup"><span data-stu-id="15813-562">Some receivers have other checks that are more strict than just those standards, but few go as far as Office 365 to block unauthenticated email and treat them as a spoof.</span></span> <span data-ttu-id="15813-563">不過，大部分的產業變得更嚴格有關此特定類型的電子郵件，尤其是因網路釣魚的問題。</span><span class="sxs-lookup"><span data-stu-id="15813-563">However, most of the industry is becoming more and more strict about this particular type of email, particularly because of the problem of phishing.</span></span>
  
### <a name="do-i-still-need-the-advanced-spam-filtering-option-enabled-for-spf-hard-fail-if-i-enable-anti-spoofing"></a><span data-ttu-id="15813-564">仍是否需要啟用 「 SPF 硬失敗 」 如果啟用反詐騙的進階垃圾郵件篩選選項？</span><span class="sxs-lookup"><span data-stu-id="15813-564">Do I still need the Advanced Spam Filtering option enabled for "SPF Hard Fail" if I enable anti-spoofing?</span></span>

<span data-ttu-id="15813-565">否，此選項已不再需要因為 SPF 硬失敗，但更多組準則的不只會考慮的反詐騙的功能。</span><span class="sxs-lookup"><span data-stu-id="15813-565">No, this option is no longer required because the anti-spoofing feature not only considers SPF hard fails, but a much wider set of criteria.</span></span> <span data-ttu-id="15813-566">如果您有反詐騙啟用，且已啟用 [SPF 硬失敗] 選項，可能就會更多的誤判。</span><span class="sxs-lookup"><span data-stu-id="15813-566">If you have anti-spoofing enabled and the SPF Hard Fail option enabled, you will probably get more false positives.</span></span> <span data-ttu-id="15813-567">我們建議您停用此功能，因為它會提供幾乎沒有其他 catch 垃圾郵件或釣魚程式，並改為產生大部分誤判。</span><span class="sxs-lookup"><span data-stu-id="15813-567">We recommend disabling this feature as it would provide almost no additional catch for spam or phish, and instead generate mostly false positives.</span></span>
  
### <a name="does-sender-rewriting-scheme-srs-help-fix-forwarded-email"></a><span data-ttu-id="15813-568">沒有寄件者修正配置 (SRS)，協助修正轉寄電子郵件？</span><span class="sxs-lookup"><span data-stu-id="15813-568">Does Sender Rewriting Scheme (SRS) help fix forwarded email?</span></span>

<span data-ttu-id="15813-569">SRS 只有部分修正問題的轉寄電子郵件。</span><span class="sxs-lookup"><span data-stu-id="15813-569">SRS only partially fixes the problem of forwarded email.</span></span> <span data-ttu-id="15813-570">修正 SMTP 郵件從，SRS 能確保，在下一個目的地轉寄的郵件通過 SPF。</span><span class="sxs-lookup"><span data-stu-id="15813-570">By rewriting the SMTP MAIL FROM, SRS can ensure that the forwarded message passes SPF at the next destination.</span></span> <span data-ttu-id="15813-571">不過，因為反詐騙根據 From： 地址搭配 [MAIL FROM 或 DKIM 簽章的網域 （或其他信號），它不是足夠，防止轉寄電子郵件被標示為詐騙。</span><span class="sxs-lookup"><span data-stu-id="15813-571">However, because anti-spoofing is based upon the From: address in combination with either the MAIL FROM or DKIM-signing domain (or other signals), it is not enough to prevent forwarded email from being marked as spoofed.</span></span>