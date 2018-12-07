---
title: Office 365 的反詐騙保護
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/06/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d24bb387-c65d-486e-93e7-06a4f1a436c0
description: 本文說明如何 Office 365 可以降低對網路釣魚攻擊用途是寄件者的網域即詐騙的網域。其完成這同樣藉由分析郵件並封鎖過可驗證 neithe 使用標準的電子郵件的驗證方法或其他寄件者信譽技術 （英文）。這項變更被實減少網路釣魚攻擊的 Office 365 組織公開到數目。
ms.openlocfilehash: 95f4995b6447870700bc483f205ca3ff831045f5
ms.sourcegitcommit: 8c5a88433cff23c59b436260808cf3d91b06fdef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/07/2018
ms.locfileid: "27194714"
---
# <a name="anti-spoofing-protection-in-office-365"></a><span data-ttu-id="1cd1b-105">Office 365 的反詐騙保護</span><span class="sxs-lookup"><span data-stu-id="1cd1b-105">Anti-spoofing protection in Office 365</span></span>

<span data-ttu-id="1cd1b-p102">本文說明如何 Office 365 可以降低對網路釣魚攻擊用途是寄件者的網域即詐騙的網域。它而言分析郵件並封鎖不會使用標準的電子郵件的驗證方法或其他寄件者信譽技術 （英文） 驗證的錯誤。這項變更被實減少網路釣魚攻擊客戶公開到數目。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p102">This article describes how Office 365 mitigates against phishing attacks that uses forged sender domains, that is, domains that are spoofed. It accomplishes this by analyzing the messages and blocking the ones that cannot be authenticated using standard email authentication methods, nor other sender reputation techniques. This change is being implemented to reduce the number of phishing attacks customers are exposed to.</span></span>
  
<span data-ttu-id="1cd1b-109">本文也說明為何此變更進行、 客戶如何準備這項變更、 如何檢視會影響的郵件、 如何報告的郵件、 如何減輕誤判，，以及給 Microsoft 的寄件者應如何準備進行這變更。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-109">This article also describes why this change is being made, how customers can prepare for this change, how to view messages that will be affected, how to report on messages, how to mitigate false positives, as well as how senders to Microsoft should prepare for this change.</span></span>
  
<span data-ttu-id="1cd1b-p103">Microsoft 的反詐騙技術最初已部署給其組織有的 Office 365 企業版 E5 訂閱或鎖購買其訂閱的 Office 365 進階威脅保護 (ATP) 附加元件。年 10 月、 2018年我們已擴充至組織的 Exchange Online Protection (EOP)，以及保護。此外，因此我們篩選的所有了解從彼此的方式，Outlook.com 使用者可能會影響。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p103">Microsoft's anti-spoofing technology was initially deployed to its organizations that had an Office 365 Enterprise E5 subscription or had purchased the Office 365 Advanced Threat Protection (ATP) add-on for their subscription. As of October, 2018 we've extended the protection to organizations that have Exchange Online Protection (EOP) as well. Additionally, because of the way all of our filters learn from each other, Outlook.com users may also be affected.</span></span>
  
## <a name="how-spoofing-is-used-in-phishing-attacks"></a><span data-ttu-id="1cd1b-113">在網路釣魚攻擊的詐騙使用方式</span><span class="sxs-lookup"><span data-stu-id="1cd1b-113">How spoofing is used in phishing attacks</span></span>

<span data-ttu-id="1cd1b-p104">來保護其使用者而言，Microsoft 嚴重採用網路釣魚的威脅。其中一個垃圾郵件和網路釣客常使用的技術在詐騙，這當寄件者為是，及源自從某人或某處以外的實際來源會出現的訊息。這項技術通常用於在網路釣魚活動設計用來取得使用者認證。Microsoft 的反詐騙技術特別檢查的冒名 '從： 標頭' 是 like Outlook 電子郵件用戶端中會顯示一個。當 Microsoft 具有高度信賴的 From： 詐騙標頭，它會識別身分詐騙郵件。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p104">When it comes to protecting its users, Microsoft takes the threat of phishing seriously. One of the techniques that spammers and phishers commonly use is spoofing, which is when the sender is forged, and a message appears to originate from someone or somewhere other than the actual source. This technique is often used in phishing campaigns designed to obtain user credentials. Microsoft's Anti-spoof technology specifically examines forgery of the 'From: header' which is the one that shows up in an email client like Outlook. When Microsoft has high confidence that the From: header is spoofed, it identifies the message as a spoof.</span></span>
  
<span data-ttu-id="1cd1b-119">詐騙郵件都有真實生活使用者的兩個負面影響：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-119">Spoofing messages have two negative implications for real life users:</span></span>
  
### <a name="1-spoofed-messages-deceive-users"></a><span data-ttu-id="1cd1b-120">1.詐騙郵件惡作劇使用者</span><span class="sxs-lookup"><span data-stu-id="1cd1b-120">1. Spoofed messages deceive users</span></span>
  
<span data-ttu-id="1cd1b-p105">首先，詐騙的郵件可能誘騙使用者按下連結及放棄其認證、 下載惡意程式碼、 或回覆有機密內容 （後者都稱為商務電子郵件危害） 的郵件。例如，以下是 msoutlook94@service.outlook.com 的網路釣魚詐騙寄件者訊息：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p105">First, a spoofed message may trick a user into clicking a link and giving up their credentials, downloading malware, or replying to a message with sensitive content (the latter of which is known as Business Email Compromise). For example, the following is a phishing message with a spoofed sender of msoutlook94@service.outlook.com:</span></span>
  
![網路釣魚郵件模擬 service.outlook.com](media/1a441f21-8ef7-41c7-90c0-847272dc5350.jpg)
  
<span data-ttu-id="1cd1b-p106">在上述並非真的來自 service.outlook.com，但改用已使其看起來像是它 phisher 詐騙。它會嘗試誘騙使用者按一下訊息中的連結。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p106">The above did not actually come from service.outlook.com, but instead was spoofed by the phisher to make it look like it did. It is attempting to trick a user into clicking the link within the message.</span></span>
  
<span data-ttu-id="1cd1b-126">下一個範例詐騙 contoso.com:</span><span class="sxs-lookup"><span data-stu-id="1cd1b-126">The next example is spoofing contoso.com:</span></span>
  
![網路釣魚訊息-商業電子郵件危害](media/da15adaa-708b-4e73-8165-482fc9182090.jpg)
  
<span data-ttu-id="1cd1b-p107">郵件會尋找合法，但事實上詐騙。此網路釣魚訊息是一種商業電子郵件危害這是網路釣魚之子類別。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p107">The message looks legitimate, but in fact is a spoof. This phishing message is a type of Business Email Compromise which is a subcategory of phishing.</span></span>
    
### <a name="2-users-confuse-real-messages-for-fake-ones"></a><span data-ttu-id="1cd1b-130">2.使用者將混淆實際假的錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="1cd1b-130">2. Users confuse real messages for fake ones</span></span>
  
<span data-ttu-id="1cd1b-p108">第二個、 詐騙郵件建立不確定使用者了解網路釣魚郵件，但無法判斷實際的郵件和詐騙的其中一個之間的差異。例如，以下是密碼的實際重設從 Microsoft 安全性帳戶的電子郵件地址的範例：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p108">Second, spoofed messages create uncertainty for users who know about phishing messages but cannot tell the difference between a real message and spoofed one. For example, the following is an example of an actual password reset from the Microsoft Security account email address:</span></span>
  
![Microsoft 合法的密碼重設](media/58a3154f-e83d-4f86-bcfe-ae9e8c87bd37.jpg)
  
<span data-ttu-id="1cd1b-p109">上述的郵件沒有來自 Microsoft、 但同時，使用者會用來取得網路釣魚訊息可能誘騙使用者按下連結及放棄其認證、 下載惡意程式碼、 或回覆有機密內容的郵件。因為很難告訴實際密碼重設與 fake 一個之間的差異，許多使用者略過這些訊息、 它們回報為垃圾郵件或整天郵件後向 Microsoft 報告為未接的網路釣魚詐騙。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p109">The above message did come from Microsoft, but at the same time, users are used to getting phishing messages that may trick a user into clicking a link and giving up their credentials, downloading malware, or replying to a message with sensitive content. Because it is difficult to tell the difference between a real password reset and a fake one, many users ignore these messages, report them as spam, or unnecessarily report the messages back to Microsoft as missed phishing scams.</span></span>
    
<span data-ttu-id="1cd1b-p110">若要停止詐騙、 電子郵件篩選產業已開發[SPF](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)、 [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)及[DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)等的電子郵件驗證通訊協定。DMARC 防止詐騙檢查郵件寄件者層的使用者會看到其電子郵件用戶端中 （在上述範例中，這是 service.outlook.com、 outlook.com，以及 accountprotection.microsoft.com）-與 SPF 或 DKIM 傳遞的網域。也就是使用者看到的網域已驗證與因此未詐騙。如需更完整的討論，請參閱區段"*瞭解為何電子郵件驗證不一定足夠停止詐騙"* 更新版本文件中。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p110">To stop spoofing, the email filtering industry has developed email authentication protocols such as [SPF](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing), [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email), and [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email). DMARC prevents spoofing examining a message's sender - the one that the user sees in their email client (in the examples above, this is service.outlook.com, outlook.com, and accountprotection.microsoft.com) - with the domain that passed SPF or DKIM. That is, the domain that the user sees has been authenticated and is therefore not spoofed. For a more complete discussion, see the section "*Understanding why email authentication is not always enough to stop spoofing"*  later on in this document.</span></span> 
  
<span data-ttu-id="1cd1b-p111">不過，問題是記錄是選擇性的不需要該電子郵件驗證。因此時使用強式驗證原則的網域 like, microsoft.com 和 skype.com 受到來自詐騙網域的所有發佈弱的驗證原則或沒有原則] 是針對正在詐騙的目標。年 3 月 2018年僅 9%Fortune 500 在公司網域的發佈強式電子郵件驗證原則。可能會由 phisher 詐騙其餘 91%和除非電子郵件篩選器會偵測使用其他原則可能會傳遞至使用者欺騙它們：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p111">However, the problem is that email authentication records are optional, not required. Therefore, while domains with strong authentication policies like microsoft.com and skype.com are protected from spoofing, domains that publish weaker authentication policies, or no policy at all, are targets for being spoofed.As of March 2018, only 9% of domains of companies in the Fortune 500 publish strong email authentication policies. The remaining 91% may be spoofed by a phisher, and unless the email filter detects it using another policy, may be delivered to an end user and deceive them:</span></span>
  
![DMARC 的 Fortune 500 公司的原則](media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)
  
<span data-ttu-id="1cd1b-144">是小型-中等大小公司的比例不在發佈強式電子郵件驗證原則 Fortune 500 為較小、 和小仍 「 北美地區 」 及西歐外的網域。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-144">The proportion of small-to-medium sized companies that are not in the Fortune 500 that publish strong email authentication policies is smaller, and smaller still for domains that are outside of North America and western Europe.</span></span>
  
<span data-ttu-id="1cd1b-145">這會是大問題是因為網路釣客企業版可能不知道電子郵件的驗證運作方式，而不要了解並善加利用缺乏。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-145">This is a big problem because while enterprises may not be aware of how email authentication works, phishers do understand and take advantage of the lack of it.</span></span>
  
<span data-ttu-id="1cd1b-146">設定 SPF、 DKIM，以及 DMARC 上的資訊，請參閱區段"更新版本文件中*的 Office 365" 的客戶*。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-146">For information on setting up SPF, DKIM, and DMARC, see the section "*Customers of Office 365"*  later on in this document.</span></span> 
  
## <a name="stopping-spoofing-with-implicit-email-authentication"></a><span data-ttu-id="1cd1b-147">停止詐騙隱含的電子郵件的驗證</span><span class="sxs-lookup"><span data-stu-id="1cd1b-147">Stopping spoofing with implicit email authentication</span></span>

<span data-ttu-id="1cd1b-p112">由於網路釣魚和矛網路釣魚問題，並因強式電子郵件驗證原則限制採用 Microsoft 繼續投資來保護其客戶的功能。因此，Microsoft 事先移動*隱含的電子郵件驗證*-如果網域不會進行驗證，請 Microsoft 會將它視為其有發佈電子郵件的驗證記錄並且將它視為據以如果它不會傳遞。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p112">Because phishing and spear phishing is such a problem, and because of the limited adoption of strong email authentication policies, Microsoft continues to invest in capabilities to protect its customers. Therefore, Microsoft is moving ahead with  *implicit email authentication* - if a domain doesn't authenticate, Microsoft will treat it as if it had published email authentication records and treat it accordingly if it doesn't pass.</span></span> 
  
<span data-ttu-id="1cd1b-p113">若要完成這個工作，Microsoft 具有內建許多延伸至一般電子郵件驗證包括寄件者信譽、 寄件者/收件者歷程記錄、 行為上有無分析和其他進階技術 （英文）。寄件者的網域，不會發佈電子郵件的驗證訊息將標記為詐騙除非它包含其他訊號表示是合法。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p113">To accomplish this, Microsoft has built numerous extensions to regular email authentication including sender reputation, sender/recipient history, behavioral analysis, and other advanced techniques. A message sent from a domain that doesn't publish email authentication will be marked as spoof unless it contains other signals to indicate that it is legitimate.</span></span>
  
<span data-ttu-id="1cd1b-152">依照此一般使用者可信賴電子郵件傳送給他們不被詐騙、 寄件者可以有信心有空模擬其網域與 Office 365 的客戶可以提供更好防護例如模擬保護。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-152">By doing this, end users can have confidence that an email sent to them has not been spoofed, senders can be confident that nobody is impersonating their domain, and customers of Office 365 can offer even better protection such as Impersonation protection.</span></span>
  
<span data-ttu-id="1cd1b-153">若要查看 Microsoft 的一般宣告，請參閱[海藻的 Phish 第 2 部分-Office 365 中增強的反詐騙](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209)。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-153">To see Microsoft's general announcement, see [A Sea of Phish Part 2 - Enhanced Anti-spoofing in Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).</span></span>
  
## <a name="identifying-that-a-message-is-classified-as-spoofed"></a><span data-ttu-id="1cd1b-154">用於識別郵件被分類當成詐騙</span><span class="sxs-lookup"><span data-stu-id="1cd1b-154">Identifying that a message is classified as spoofed</span></span>

### <a name="composite-authentication"></a><span data-ttu-id="1cd1b-155">複合式驗證</span><span class="sxs-lookup"><span data-stu-id="1cd1b-155">Composite authentication</span></span>

<span data-ttu-id="1cd1b-p114">雖然 SPF、 DKIM，以及 DMARC 本身並都很有用，他們不在事件訊息中有沒有明確驗證記錄通訊足夠的驗證狀態。因此，Microsoft 已經開發將多個信號結合成單一值的簡短呼叫複合式驗證] 或 [compauth 演算法。在 Office 365 的客戶有 compauth 值將郵件標頭中的*驗證結果*標頭上戳記。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p114">While SPF, DKIM, and DMARC are all useful by themselves, they don't communicate enough authentication status in the event a message has no explicit authentication records. Therefore, Microsoft has developed an algorithm that combines multiple signals into a single value called Composite Authentication, or compauth for short. Customers in Office 365 have compauth values stamped into the *Authentication-Results* header in the message headers.</span></span> 
  
```
Authentication-Results:
  compauth=<fail|pass|softpass|none> reason=<yyy>

```

|<span data-ttu-id="1cd1b-159">**CompAuth 結果**</span><span class="sxs-lookup"><span data-stu-id="1cd1b-159">**CompAuth result**</span></span>|<span data-ttu-id="1cd1b-160">**描述**</span><span class="sxs-lookup"><span data-stu-id="1cd1b-160">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1cd1b-161">失敗</span><span class="sxs-lookup"><span data-stu-id="1cd1b-161">fail</span></span>|<span data-ttu-id="1cd1b-162">郵件無法明確驗證 （傳送網域發佈記錄明確地在 DNS 中） 或隱含驗證 （傳送網域並未未發行記錄在 DNS 中，因此 Office 365 插結果好像並已發佈的記錄）。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-162">Message failed explicit authentication (sending domain published records explicitly in DNS) or implicit authentication (sending domain did not publish records in DNS, so Office 365 interpolated the result as if it had published records).</span></span>|
|<span data-ttu-id="1cd1b-163">傳遞</span><span class="sxs-lookup"><span data-stu-id="1cd1b-163">pass</span></span>|<span data-ttu-id="1cd1b-164">郵件傳遞明確驗證 （郵件傳遞 DMARC 或[最佳猜測傳遞 DMARC](https://blogs.msdn.microsoft.com/tzink/2015/05/06/what-is-dmarc-bestguesspass-in-office-365)） 或具有高度信賴隱含驗證 （傳送網域未發行電子郵件的驗證記錄，但 Office 365 強式的後端信號指出郵件很有可能合法)。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-164">Message passed explicit authentication (message passed DMARC, or [Best Guess Passed DMARC](https://blogs.msdn.microsoft.com/tzink/2015/05/06/what-is-dmarc-bestguesspass-in-office-365)) or implicit authentication with high confidence (sending domain does not publish email authentication records, but Office 365 has strong backend signals to indicate the message is likely legitimate).</span></span>|
|<span data-ttu-id="1cd1b-165">softpass</span><span class="sxs-lookup"><span data-stu-id="1cd1b-165">softpass</span></span>|<span data-ttu-id="1cd1b-166">郵件傳遞隱含的驗證與低-中型信賴 （傳送網域未發行電子郵件的驗證、 但 Office 365 表示郵件合法但接收的訊號強度弱的後端訊號）。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-166">Message passed implicit authentication with low-to-medium confidence (sending domain does not publish email authentication, but Office 365 has backend signals to indicate the message is legitimate but the strength of the signal is weaker).</span></span>|
|<span data-ttu-id="1cd1b-167">無</span><span class="sxs-lookup"><span data-stu-id="1cd1b-167">none</span></span>|<span data-ttu-id="1cd1b-168">未先驗證訊息] （或其未進行驗證，但沒有對齊） 但因為寄件者信譽或其他因素而不會套用複合驗證。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-168">Message did not authenticate (or it did authenticate but did not align), but composite authentication not applied due to sender reputation or other factors.</span></span>|
   
|||
|:-----|:-----|
|<span data-ttu-id="1cd1b-169">**原因**</span><span class="sxs-lookup"><span data-stu-id="1cd1b-169">**Reason**</span></span>|<span data-ttu-id="1cd1b-170">**描述**</span><span class="sxs-lookup"><span data-stu-id="1cd1b-170">**Description**</span></span>|
|<span data-ttu-id="1cd1b-171">0xx</span><span class="sxs-lookup"><span data-stu-id="1cd1b-171">0xx</span></span>|<span data-ttu-id="1cd1b-172">郵件無法複合式驗證。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-172">Message failed composite authentication.</span></span><br/><span data-ttu-id="1cd1b-p115">**000**表示郵件無法 DMARC 與拒絕或隔離區的動作。                   -001 表示郵件無法隱含的電子郵件的驗證。這表示的傳送端網域沒有電子郵件驗證記錄發佈，或如果初採取了幾，他們有弱的失敗原則 (SPF 軟體失敗或 neutral、 DMARC 原則的 p = none)。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p115">**000** means the message failed DMARC with an action of reject or quarantine.                    - 001 means the message failed implicit email authentication. This means that the sending domain did not have email authentication records published, or if they did, they had a weaker failure policy (SPF soft fail or neutral, DMARC policy of p=none).  </span></span><br/><span data-ttu-id="1cd1b-176">**002**表示組織有組明確禁止傳送詐騙的電子郵件的寄件者/網域的原則，以系統管理員手動設定此設定。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-176">**002** means the organization has a policy for the sender/domain pair that is explicitly prohibited from sending spoofed email, this setting is manually set by an administrator.</span></span>  <br/><span data-ttu-id="1cd1b-177">**010**表示郵件無法拒絕或隔離的動作與 DMARC 及傳送端網域是其中一個貴組織的公認的網域 (這是以自我自我或組織內部的一部分詐騙)。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-177">**010** means the message failed DMARC with an action of reject or quarantine, and the sending domain is one of your organization's accepted-domains (this is part of self-to-self, or intra-org, spoofing).</span></span>  <br/><span data-ttu-id="1cd1b-178">**011**表示郵件無法隱含的電子郵件驗證及傳送端網域是其中一個貴組織的公認的網域 (這是以自我自我或組織內部的一部分詐騙)。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-178">**011** means the message failed implicit email authentication, and the sending domain is one of your organization's accepted domains (this is part of self-to-self, or intra-org, spoofing).</span></span>|
|<span data-ttu-id="1cd1b-179">所有其他代碼 （1xx、 2xx、 3xx、 4xx、 5xx）</span><span class="sxs-lookup"><span data-stu-id="1cd1b-179">All other codes (1xx, 2xx, 3xx, 4xx, 5xx)</span></span>|<span data-ttu-id="1cd1b-180">將郵件傳遞隱含驗證或有無驗證但採取任何動作所套用的原因會對應到的各種內部代碼。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-180">Corresponds to various internal codes for why a message passed implicit authentication, or had no authentication but no action was applied.</span></span>|
   
<span data-ttu-id="1cd1b-181">透過查看之郵件標頭，系統管理員或甚至是使用者可以決定如何 Office 365 抵達寄件者可能詐騙結論。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-181">By looking at the headers of a message, an administrator or even an end user can determine how Office 365 arrives at the conclusion that the sender may be spoofed.</span></span>
  
### <a name="differentiating-between-different-types-of-spoofing"></a><span data-ttu-id="1cd1b-182">區別不同類型的詐騙</span><span class="sxs-lookup"><span data-stu-id="1cd1b-182">Differentiating between different types of spoofing</span></span>

<span data-ttu-id="1cd1b-183">Microsoft 區分兩種不同類型的詐騙郵件：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-183">Microsoft differentiates between two different types of spoofing messages:</span></span>
  
 <span data-ttu-id="1cd1b-184">**內 org 詐騙**</span><span class="sxs-lookup"><span data-stu-id="1cd1b-184">**Intra-org spoofing**</span></span>
  
<span data-ttu-id="1cd1b-185">也稱為自我-自我詐騙、 發生此情況時在 [從網域： 地址相同，或是配合收件者的網域 （如果收件者的網域是其中一個貴組織的[公認的網域](https://technet.microsoft.com/en-us/library/jj945194%28v=exchg.150%29.aspx)）;或時在 [從網域： 地址屬於相同組織。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-185">Also known as self-to-self spoofing, this occurs when the domain in the From: address is the same as, or aligns with, the recipient domain (when recipient domain is one of your organization's [Accepted Domains](https://technet.microsoft.com/en-us/library/jj945194%28v=exchg.150%29.aspx)); or, when the domain in the From: address is part of the same organization.</span></span>
  
<span data-ttu-id="1cd1b-p116">例如，下列寄件者和收件者從具有相同的網域 (contoso.com)。空格插入可防止 spambot 蒐集此頁面上的電子郵件地址）：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p116">For example, the following has sender and recipient from the same domain (contoso.com). Spaces are inserted into the email address to prevent spambot harvesting on this page):</span></span>
  
<span data-ttu-id="1cd1b-188">從： 寄件者 @ contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cd1b-188">From: sender @ contoso.com</span></span>
  
<span data-ttu-id="1cd1b-189">： 收件者 @ contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cd1b-189">To: recipient @ contoso.com</span></span>
  
<span data-ttu-id="1cd1b-190">下列具有與組織的網域 (fabrikam.com) 對齊寄件者和收件者的網域：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-190">The following has the sender and recipient domains aligning with the organizational domain (fabrikam.com):</span></span>
  
<span data-ttu-id="1cd1b-191">從： 寄件者 foo.fabrikam.com @</span><span class="sxs-lookup"><span data-stu-id="1cd1b-191">From: sender @ foo.fabrikam.com</span></span>
  
<span data-ttu-id="1cd1b-192">： 收件者 bar.fabrikam.com @</span><span class="sxs-lookup"><span data-stu-id="1cd1b-192">To: recipient @ bar.fabrikam.com</span></span>
  
<span data-ttu-id="1cd1b-193">下列寄件者和收件者的網域皆不同 （microsoft.com 和 bing.com），但他們屬於相同組織 （亦即同時是組織的公認的網域的一部分）：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-193">The following sender and recipient domains are different (microsoft.com and bing.com), but they belong to the same organization (that is, both are part of the organization's Accepted Domains):</span></span>
  
<span data-ttu-id="1cd1b-194">從： 寄件者 @ microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1cd1b-194">From: sender @ microsoft.com</span></span>
  
<span data-ttu-id="1cd1b-195">： 收件者 bing.com @</span><span class="sxs-lookup"><span data-stu-id="1cd1b-195">To: recipient @ bing.com</span></span>
  
<span data-ttu-id="1cd1b-196">失敗內 org 詐騙的郵件包含標頭中的下列值：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-196">Messages that fail intra-org spoofing contain the following values in the headers:</span></span>
  
<span data-ttu-id="1cd1b-197">X Forefront-反垃圾郵件報告：...]CAT:SPM/HSPM/PHSH;...]SFTY:9.11</span><span class="sxs-lookup"><span data-stu-id="1cd1b-197">X-Forefront-Antispam-Report: ...CAT:SPM/HSPM/PHSH;...SFTY:9.11</span></span>
  
<span data-ttu-id="1cd1b-198">CAT is 之郵件的類別和通常為 SPM （垃圾郵件） 上戳記但有時可能是 HSPM （高信賴垃圾郵件） 或 PHISH （網路釣魚） 取決於哪些其他類型的模式發生訊息中。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-198">The CAT is the category of the message, and it is normally stamped as SPM (spam), but occasionally may be HSPM (high confidence spam) or PHISH (phishing) depending upon what other types of patterns occur in the message.</span></span>
  
<span data-ttu-id="1cd1b-199">SFTY 是之郵件的安全層級、 第一個數字 (9) 表示郵件是網路釣魚，而第二組的數字之後點 (11) 表示它是內 org 詐騙。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-199">The SFTY is the safety level of the message, the first digit (9) means the message is phishing, and second set of digits after the dot (11) means it is intra-org spoofing.</span></span>
  
<span data-ttu-id="1cd1b-200">沒有特定原因程式碼內 org 詐騙、 的複合會加上戳記 2018 （尚未定義時間表） 後述的驗證。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-200">There is no specific reason code for Composite Authentication for intra-org spoofing, that will be stamped later in 2018 (timeline not yet defined).</span></span>
  
 <span data-ttu-id="1cd1b-201">**跨網域詐騙**</span><span class="sxs-lookup"><span data-stu-id="1cd1b-201">**Cross-domain spoofing**</span></span>
  
<span data-ttu-id="1cd1b-p117">發生此動作時的傳送端網域中寄： 地址是接收組織外部的網域。由於跨網域詐騙失敗複合式驗證的郵件包含標頭中的下列值：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p117">This occurs when the sending domain in the From: address is an external domain to the receiving organization. Messages that fail Composite Authentication due to cross-domain spoofing contain the following values in the headers:</span></span>
  
<span data-ttu-id="1cd1b-p118">驗證結果:...compauth = 失敗原因 = 000/001</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p118">Authentication-Results: … compauth=fail reason=000/001</span></span>
  
<span data-ttu-id="1cd1b-206">X Forefront-反垃圾郵件報告：...]CAT:SPOOF;...]SFTY:9.22</span><span class="sxs-lookup"><span data-stu-id="1cd1b-206">X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.22</span></span>
  
<span data-ttu-id="1cd1b-207">在這兩種情況下，下列的紅色 safety 提示會加上戳記郵件，或對等資格專為收件者的信箱語言：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-207">In both cases, the following red safety tip is stamped in the message, or an equivalent that is customized to the recipient mailbox's language:</span></span>
  
![紅色 safety 提示-詐騙的偵測](media/a366156a-14e8-4c14-bfe5-2031b21936f8.jpg)
  
<span data-ttu-id="1cd1b-209">僅使用查看 From： 地址和了解收件者電子郵件的功能，或依照檢查，就能區分內 org 及跨網域詐騙的電子郵件標頭。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-209">It's only by looking at the From: address and knowing what your recipient email is, or by inspecting the email headers, that you can differentiate between intra-org and cross-domain spoofing.</span></span>
  
## <a name="how-customers-of-office-365-can-prepare-themselves-for-the-new-anti-spoofing-protection"></a><span data-ttu-id="1cd1b-210">如何 Office 365 的客戶可以準備自己的新反詐騙保護</span><span class="sxs-lookup"><span data-stu-id="1cd1b-210">How customers of Office 365 can prepare themselves for the new anti-spoofing protection</span></span>

### <a name="information-for-administrators"></a><span data-ttu-id="1cd1b-211">系統管理員的資訊</span><span class="sxs-lookup"><span data-stu-id="1cd1b-211">Information for administrators</span></span>

<span data-ttu-id="1cd1b-212">在 Office 365 組織的系統管理員身分有您應該要知道的資訊的數個重要部分。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-212">As an administrator of an organization in Office 365, there are several key pieces of information you should be aware of.</span></span>
  
### <a name="understanding-why-email-authentication-is-not-always-enough-to-stop-spoofing"></a><span data-ttu-id="1cd1b-213">了解為何電子郵件驗證不一定足夠停止詐騙</span><span class="sxs-lookup"><span data-stu-id="1cd1b-213">Understanding why email authentication is not always enough to stop spoofing</span></span>

<span data-ttu-id="1cd1b-p119">新的反詐騙保護依賴 （SPF、 DKIM、 和 DMARC） 不標示郵件為詐騙的電子郵件驗證。傳送端網域具有永遠不會發佈 SPF 記錄時的一般的範例。如果不有任何 SPF 記錄或他們不正確地設定，已傳送的訊息將標記為詐騙除非 Microsoft 有指出郵件是合法的後端智慧。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p119">The new anti-spoofing protection relies on email authentication (SPF, DKIM, and DMARC) to not mark a message as spoofing. A common example is when a sending domain has never published SPF records. If there are no SPF records or they are incorrectly set up, a sent message will be marked as spoofed unless Microsoft has back-end intelligence that says the message is legitimate.</span></span>
  
<span data-ttu-id="1cd1b-217">例如前反-詐騙正在部署、 訊息可能看起來不 SPF 記錄、 沒有 DKIM 的記錄，與沒有 DMARC 記錄下列：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-217">For example, prior to anti-spoofing being deployed, a message may have looked like the following with no SPF record, no DKIM record, and no DMARC record:</span></span> 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```
<span data-ttu-id="1cd1b-218">之後反詐騙如果您有 Office 365 企業版 E5、 EOP 或 ATP、 compauth 值會加上戳記：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-218">After anti-spoofing, if you have Office 365 Enterprise E5, EOP, or ATP, the compauth value is stamped:</span></span>
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com; compauth=fail reason=001
From: sender @ example.com
To: receiver @ contoso.com

```

<span data-ttu-id="1cd1b-219">如果 example.com 修正此設定 SPF 記錄，但不是 DKIM 記錄，這會因為傳遞 SPF 網域對齊在從網域傳遞複合式驗證： 地址：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-219">If example.com fixed this by setting up an SPF record but not a DKIM record, this would pass composite authentication because the domain that passed SPF aligned with the domain in the From: address:</span></span> 
  
```
Authentication-Results: spf=pass (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

<span data-ttu-id="1cd1b-220">或者，如果它們設定 DKIM 記錄，但不是 SPF 記錄，這會也存取複合式驗證因為傳遞 DKIM 簽章的網域對齊在從網域： 地址：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-220">Or, if they set up a DKIM record but not an SPF record, this would also pass composite authentication because the domain in the DKIM-Signature that passed aligned with the domain in the From: address:</span></span> 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.example.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

<span data-ttu-id="1cd1b-p120">不過，phisher 可能也設定 SPF 和 DKIM 和登入他們自己的網域的郵件但指定不同網域中寄： 地址。SPF 皆 DKIM 需要以符合在 [從網域的網域： 處理，因此除非 example.com 發佈 DMARC 記錄，這就不會標示為使用 DMARC 詐騙：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p120">However, a phisher may also set up SPF and DKIM and sign the message with their own domain, but specify a different domain in the From: address. Neither SPF nor DKIM requires the domain to align with the domain in the From: address, so unless example.com published DMARC records, this would not be marked as a spoof using DMARC:</span></span> 
  
```
Authentication-Results: spf=pass (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```

<span data-ttu-id="1cd1b-223">在電子郵件用戶端 (Outlook web 或任何其他電子郵件用戶端上的 Outlook)、 僅限 From： 顯示網域、 不在 SPF 或 DKIM，且網域可以將思考郵件是來自 example.com，但實際上是來自 maliciousDomain.com 誤導使用者.</span><span class="sxs-lookup"><span data-stu-id="1cd1b-223">In the email client (Outlook, Outlook on the web, or any other email client), only the From: domain is displayed, not the domain in the SPF or DKIM, and that can mislead the user into thinking the message came from example.com, but actually came from maliciousDomain.com.</span></span>
  
![已驗證的訊息但從： 網域未對齊什麼傳遞 SPF 或 DKIM](media/a9b5ab2a-dfd3-47c6-8ee8-e3dab2fae528.jpg)
  
<span data-ttu-id="1cd1b-p121">有該原因 Office 365 需要的來源中的網域： 地址對齊 SPF 或 DKIM 簽署] 中的網域和它不會，包含一些其他內部信號表示郵件是否合法。否則，訊息就是 compauth 失敗。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p121">For that reason, Office 365 requires that the domain in the From: address aligns with the domain in the SPF or DKIM signature, and if it doesn't, contains some other internal signals that indicates that the message is legitimate. Otherwise, the message would be a compauth fail.</span></span> 
  
```
Authentication-Results: spf=none (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: sender@contoso.com
To: someone@example.com
```

<span data-ttu-id="1cd1b-p122">即得出 Office 365 反詐騙會保護對網域無驗證] 並針對設定驗證但不符針對在 [從網域的網域： 地址，也就是一個使用者會看到與認為是郵件的寄件者。這是都可以在您的組織外部的網域以及在組織內的網域，則為 true。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p122">Thus, Office 365 anti-spoofing protects against domains with no authentication, and against domains who set up authentication but mismatch against the domain in the From: address as that is the one that the user sees and believes is the sender of the message. This is true both of domains external to your organization, as well as domains within your organization.</span></span>
  
<span data-ttu-id="1cd1b-229">因此，如果您曾經收到郵件複合式驗證失敗且標記為詐騙，即使郵件傳遞 SPF 和 DKIM，它會是因為在 [從網域不符合傳遞 SPF 和 DKIM 的網域： 地址。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-229">Therefore, if you ever receive a message that failed composite authentication and is marked as spoofed, even though the message passed SPF and DKIM, it's because the domain that passed SPF and DKIM are not aligned with the domain in the From: address.</span></span>
  
### <a name="understanding-changes-in-how-spoofed-emails-are-treated"></a><span data-ttu-id="1cd1b-230">了解如何詐騙的電子郵件中的變更被視為</span><span class="sxs-lookup"><span data-stu-id="1cd1b-230">Understanding changes in how spoofed emails are treated</span></span>

<span data-ttu-id="1cd1b-p123">目前所有組織中 Office 365-ATP 和非 ATP-訊息以拒絕或隔離原則 DMARC 都會標記為垃圾郵件和通常需要高信賴垃圾郵件動作，或有時正常的垃圾郵件動作，無法 (根據其他垃圾郵件規則先其識別為垃圾郵件）。內 org 詐騙的偵測採取正常的垃圾郵件。若要啟用，不需要此表現方式也不可以加以停用。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p123">Currently, for all organizations in Office 365 - ATP and non-ATP - messages that fail DMARC with a policy of reject or quarantine are marked as spam and usually take the high confidence spam action, or sometimes the regular spam action (depending on whether other spam rules first identify it as spam). Intra-org spoof detections take the regular spam action. This behavior does not need to be enabled, nor can it be disabled.</span></span>
  
<span data-ttu-id="1cd1b-p124">不過的跨網域詐騙郵件這項變更之前就會經歷正常的垃圾郵件、 phish、 及惡意程式碼檢查且篩選條件的其他組件會被識別其為可疑，如果將它們分別標示為垃圾郵件、 phish、 或惡意程式碼。使用新的跨網域詐騙的保護，無法驗證任何訊息將，根據預設，採取的動作中反網路釣魚定義\>反詐騙的原則。未定義一個項目，則它要移至使用者的垃圾郵件] 資料夾。在某些情況下，更可疑郵件同時也會新增至訊息的紅色 safety 提示。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p124">However, for cross-domain spoofing messages, before this change they would go through regular spam, phish, and malware checks and if other parts of the filter identified them as suspicious, would mark them as spam, phish, or malware respectively. With the new cross-domain spoofing protection, any message that can't be authenticated will, by default, take the action defined in the Anti-phishing \> Anti-spoofing policy. If one is not defined, it will be moved to a users Junk Email folder. In some cases, more suspicious messages will also have the red safety tip added to the message.</span></span>
  
<span data-ttu-id="1cd1b-p125">這可能會導致某些先前已標記為垃圾郵件仍快速標示為垃圾郵件，但現在也必須為紅色 safety 提示; 的郵件在其他情況下，新增先前已標記為非垃圾郵件會在啟動快速標示為垃圾郵件 (CAT:SPOOF) 以紅色 safety 提示的郵件。在仍其他情況下，已移動所有垃圾郵件與 phish 至隔離區的客戶就會立即看見他們路垃圾郵件資料夾 （此表現方式可以變更，請參閱[變更您的反詐騙設定](#changing-your-anti-spoofing-settings)）。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p125">This may result in some messages that were previously marked as spam still getting marked as spam but will now also have a red safety tip; in other cases, messages that were previously marked as non-spam will start getting marked as spam (CAT:SPOOF) with a red safety tip added. In still other cases, customers that were moving all spam and phish to the quarantine would now see them going to the Junk Mail Folder (this behavior can be changed, see [Changing your anti-spoofing settings](#changing-your-anti-spoofing-settings)).</span></span>
  
<span data-ttu-id="1cd1b-p126">有多個不同的方式可以 （請參閱本文稍早的[不同類型詐騙之間 Differentiating](#differentiating-between-different-types-of-spoofing) ） 詐騙一則訊息，但年 3 月 2018 Office 365 來說這些訊息的方式不尚未整合。下表是快速摘要，與跨網域詐騙保護正在新的行為：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p126">There are multiple different ways a message can be spoofed (see  [Differentiating between different types of spoofing](#differentiating-between-different-types-of-spoofing) earlier in this article) but as of March 2018 the way Office 365 treats these messages is not yet unified. The following table is a quick summary, with Cross-domain spoofing protection being new behavior:</span></span> 
  
|<span data-ttu-id="1cd1b-242">**詐騙的類型**</span><span class="sxs-lookup"><span data-stu-id="1cd1b-242">**Type of spoof**</span></span>|<span data-ttu-id="1cd1b-243">**類別**</span><span class="sxs-lookup"><span data-stu-id="1cd1b-243">**Category**</span></span>|<span data-ttu-id="1cd1b-244">**新增安全性提示？**</span><span class="sxs-lookup"><span data-stu-id="1cd1b-244">**Safety tip added?**</span></span>|<span data-ttu-id="1cd1b-245">**適用於**</span><span class="sxs-lookup"><span data-stu-id="1cd1b-245">**Applies to**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1cd1b-246">DMARC 失敗 （隔離或拒絕）</span><span class="sxs-lookup"><span data-stu-id="1cd1b-246">DMARC fail (quarantine or reject)</span></span>  <br/> |<span data-ttu-id="1cd1b-247">HSPM （預設值），也可能 SPM 或 PHSH</span><span class="sxs-lookup"><span data-stu-id="1cd1b-247">HSPM (default), may also be SPM or PHSH</span></span>  <br/> |<span data-ttu-id="1cd1b-248">否 （尚未）</span><span class="sxs-lookup"><span data-stu-id="1cd1b-248">No (not yet)</span></span>  <br/> |<span data-ttu-id="1cd1b-249">所有的 Office 365 客戶、 Outlook.com</span><span class="sxs-lookup"><span data-stu-id="1cd1b-249">All Office 365 customers, Outlook.com</span></span>  <br/> |
|<span data-ttu-id="1cd1b-250">自我-自我</span><span class="sxs-lookup"><span data-stu-id="1cd1b-250">Self-to-self</span></span>  <br/> |<span data-ttu-id="1cd1b-251">SPM</span><span class="sxs-lookup"><span data-stu-id="1cd1b-251">SPM</span></span>  <br/> |<span data-ttu-id="1cd1b-252">是</span><span class="sxs-lookup"><span data-stu-id="1cd1b-252">Yes</span></span>  <br/> |<span data-ttu-id="1cd1b-253">所有的 Office 365 組織、 Outlook.com</span><span class="sxs-lookup"><span data-stu-id="1cd1b-253">All Office 365 organizations, Outlook.com</span></span>  <br/> |
|<span data-ttu-id="1cd1b-254">跨網域</span><span class="sxs-lookup"><span data-stu-id="1cd1b-254">Cross-domain</span></span>  <br/> |<span data-ttu-id="1cd1b-255">詐騙</span><span class="sxs-lookup"><span data-stu-id="1cd1b-255">SPOOF</span></span>  <br/> |<span data-ttu-id="1cd1b-256">是</span><span class="sxs-lookup"><span data-stu-id="1cd1b-256">Yes</span></span>  <br/> |<span data-ttu-id="1cd1b-257">Office 365 進階威脅保護和 E5 客戶</span><span class="sxs-lookup"><span data-stu-id="1cd1b-257">Office 365 Advanced Threat Protection and E5 customers</span></span>  <br/> |
   
### <a name="changing-your-anti-spoofing-settings"></a><span data-ttu-id="1cd1b-258">變更您的反詐騙設定</span><span class="sxs-lookup"><span data-stu-id="1cd1b-258">Changing your anti-spoofing settings</span></span>

<span data-ttu-id="1cd1b-p127">若要建立或更新您 （跨網域） 反詐騙設定，請瀏覽至 [反網路釣魚\>之下 Threat Management 反詐騙設定\>安全性原則] 索引標籤&amp;規範中心。如果您先前已建立任何反網路釣魚設定，您必須建立 web 應用程式：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p127">To create or update your (cross-domain) anti-spoofing settings, navigate to the Anti-phishing \> Anti-spoofing settings under the Threat Management \> Policy tab in the Security &amp; Compliance Center. If you have never created any anti-phishing settings, you will need to create one:</span></span>
  
![反網路釣魚-建立新的原則](media/9337ec91-270e-4fa7-9dfa-a51a2d1eb95e.jpg)
  
<span data-ttu-id="1cd1b-262">如果您已經建立一個，您可以選取要修改其：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-262">If you've already created one, you can select it to modify it:</span></span>
  
![反網路釣魚-修改現有的原則](media/75457a7c-882e-4984-80d1-21a12b42c53a.jpg)
  
<span data-ttu-id="1cd1b-264">選取您剛建立的原則和上所述的步驟繼續[了解更多關於詐騙智慧。](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf)</span><span class="sxs-lookup"><span data-stu-id="1cd1b-264">Select the policy you just created and proceed through the steps as described on [Learn More about Spoof Intelligence.](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf)</span></span>
  
![啟用或停用 antispoofing](media/c49e2147-c954-443c-9144-1cbd139e1166.jpg)
  
![啟用或停用 antispoofing safety 祕訣](media/eec7c407-31fc-4f73-8325-307d82d1fb53.jpg)
  
<span data-ttu-id="1cd1b-267">若要建立新的原則透過 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-267">To create a new policy via PowerShell:</span></span> 
  
```
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

<span data-ttu-id="1cd1b-p128">然後您可能會修改使用 PowerShell 中追蹤的文件[組 AntiphishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy?view=exchange-ps)在反網路釣魚原則參數。您可以指定 $name 做為參數：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p128">You may then modify the anti-phishing policy parameters using PowerShell, following the documentation at [Set-AntiphishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy?view=exchange-ps). You may specify the $name as a parameter:</span></span>
  
```
Set-AntiphishPolicy -Identity $name <fill in rest of parameters>
```

<span data-ttu-id="1cd1b-270">後面的 2018，而不是您不必建立的預設原則，其中會為您建立可讓您不需要以手動方式指定範圍設為在組織中的所有收件者 （下列螢幕擷取畫面如有變更恕前的最後一個實作）。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-270">Later in 2018, rather than you having to create a default policy, one will be created for you that is scoped to all the recipients in your organization so you don't have to specify it manually (the screenshots below are subject to change before the final implementation).</span></span>
  
![反網路釣魚的預設原則](media/1f27a0bf-e202-4e12-bbac-24baf013c8f9.jpg)
  
<span data-ttu-id="1cd1b-272">不同於您建立的原則，您無法刪除預設原則、 修改其優先順序，或選擇範圍以哪一個使用者、 網域或群組。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-272">Unlike a policy that you create, you cannot delete the default policy, modify its priority, or choose which users, domains, or groups to scope it to.</span></span>
  
![反網路釣魚預設原則的詳細資訊](media/30c21ceb-df52-4c93-aa65-f44a55dc1009.jpg)
  
<span data-ttu-id="1cd1b-274">若要設定預設保護您透過 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-274">To set up your default protection via PowerShell:</span></span>
  
```
$defaultAntiphishPolicy = Get-AntiphishPolicy | ? {$_.IsDefault -eq $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement <$true|$false>
```

<span data-ttu-id="1cd1b-275">您應該僅停用反詐騙保護如果您有其他郵件伺服器或伺服器在 Office 365 前方 （請參閱合法情況來停用反詐騙如需詳細資訊）。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-275">You should only disable anti-spoofing protection if you have another mail server or servers in front of Office 365 (see Legitimate scenarios to disable anti-spoofing for more details).</span></span> 
  
```
$defaultAntiphishPolicy = Get-AntiphishiPolicy | ? {$_.IsDefault $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement $false 

```
> [!IMPORTANT]
> <span data-ttu-id="1cd1b-p129">如果您的電子郵件路徑中的第一個躍點是 Office 365 與您所取得太多標示為詐騙的合法電子郵件，您應該先設定您可以將詐騙的電子郵件傳送至您的網域的寄件者 （請參閱節 *"管理合法寄件者所傳送 unauthenticated 電子郵件"* )。如果您仍會取得太多誤判 （例如合法標示為詐騙郵件），不建議完全停用反詐騙保護。而是建議您選擇 [基本而不高保護。                   最好是透過誤判比以公開其無法最後的長期意大幅較高成本詐騙電子郵件組織運作。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p129">If the first hop in your email path is Office 365, and you are getting too many legitimate emails marked as spoof, you should first set up your senders that are allowed to send spoofed email to your domain (see the section  *"Managing legitimate senders who are sending unauthenticated email"*  ). If you are still getting too many false positives (e.g., legitimate messages marked as spoof), we do NOT recommend disabling anti-spoofing protection altogether. Instead, we recommend choosing Basic instead of High protection.                    It is better to work through false positives than to expose your organization to spoofed email which could end up imposing significantly higher costs in the long term.</span></span>

### <a name="managing-legitimate-senders-who-are-sending-unauthenticated-email"></a><span data-ttu-id="1cd1b-280">管理合法的寄件者所傳送未經過驗證的電子郵件</span><span class="sxs-lookup"><span data-stu-id="1cd1b-280">Managing legitimate senders who are sending unauthenticated email</span></span>

<span data-ttu-id="1cd1b-p130">持續誰會將未經過驗證的電子郵件傳送至您的組織追蹤的 office 365。如果服務認為不合法寄件者，它會將其標示為*compauth*失敗。這將會歸類為詐騙雖然它取決於您反詐騙的原則套用至郵件。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p130">Office 365 keeps track of who is sending unauthenticated email to your organization. If the service thinks the sender is not legitimate, it will mark it as a *compauth* failure. This will be classified as SPOOF although it depends on your anti-spoofing policy that was applied to the message.</span></span> 
  
<span data-ttu-id="1cd1b-284">不過，以系統管理員身分，您可以指定哪些寄件者會允許傳送詐騙的電子郵件、 覆寫 Office 365 的決策。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-284">However, as an administrator, you can specify which senders are permitted to send spoofed email, overriding Office 365's decision.</span></span>
  
<span data-ttu-id="1cd1b-285">**1-如果您的組織擁有的網域設定電子郵件的驗證方法**</span><span class="sxs-lookup"><span data-stu-id="1cd1b-285">**Method 1 - If your organization owns the domain, set up email authentication**</span></span>
  
<span data-ttu-id="1cd1b-p131">此方法可用來解析內 org 詐騙、 及跨網域詐騙在您擁有或互動的情況下使用多個承租人。它也可協助解決跨網域詐騙其中您傳送至其他 Office 365 中的客戶及也都架設在其他提供者的第三方。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p131">This method can be used to resolve intra-org spoofing, and cross-domain spoofing in cases where you own or interact with multiple tenants. It also helps resolve cross-domain spoofing where you send to other customers within Office 365, and also third parties that are hosted in other providers.</span></span>
  
<span data-ttu-id="1cd1b-288">如需詳細資訊，請參閱[Office 365 的客戶](#customers-of-office-365)。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-288">For more details, see [Customers of Office 365](#customers-of-office-365).</span></span> 
 
<span data-ttu-id="1cd1b-289">**方法 2-使用詐騙智慧設定允許寄件者的未經過驗證的電子郵件**</span><span class="sxs-lookup"><span data-stu-id="1cd1b-289">**Method 2 - Use Spoof intelligence to configure permitted senders of unauthenticated email**</span></span>
  
<span data-ttu-id="1cd1b-290">您也可以使用[詐騙智慧](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf)允許寄件者未經過驗證的郵件傳輸至您的組織。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-290">You can also use [Spoof Intelligence](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf) to permit senders to transmit unauthenticated messages to your organization.</span></span> 
  
<span data-ttu-id="1cd1b-291">針對外部網域詐騙的使用者是從地址的網域的傳送端 IP 位址傳送基礎結構時 (分成/24 CIDR 範圍)，或組織的網域的 PTR 記錄 （在以下的螢幕擷取畫面，傳送端 IP 可能是的 131.107.18.4 的 PTR 記錄是 outbound.mail.protection.outlook.com，而且這會顯示為傳送基礎結構的 outlook.com。）</span><span class="sxs-lookup"><span data-stu-id="1cd1b-291">For external domains, the spoofed user is the domain in the From address, while the sending infrastructure is either the sending IP address (divided up into /24 CIDR ranges), or the organizational domain of the PTR record (in the screenshot below, the sending IP might be 131.107.18.4 whose PTR record is outbound.mail.protection.outlook.com, and this would show up as outlook.com for the sending infrastructure).</span></span>
  
<span data-ttu-id="1cd1b-292">若要允許此傳送未經過驗證的電子郵件的寄件者，變更**否]** 為 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-292">To permit this sender to send unauthenticated email, change the **No** to a **Yes**.</span></span>
  
![設定 antispoofing 允許寄件者](media/d4334921-d820-4334-8217-788279701e94.jpg)
  
<span data-ttu-id="1cd1b-294">您也可以使用 PowerShell 允許特定寄件者詐騙網域：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-294">You can also use PowerShell to allow specific sender to spoof your domain:</span></span> 
  
```
$file = "C:\My Documents\Summary Spoofed Internal Domains and Senders.csv"
```

```
Get-PhishFilterPolicy -Detailed -SpoofAllowBlockList -SpoofType External | Export-CSV $file
```

![快速詐騙的寄件者透過 Powershell](media/0e27ffcf-a5db-4c43-a19b-fa62326d5118.jpg)
  
<span data-ttu-id="1cd1b-296">在上一個影像中，進行此螢幕擷取畫面配合，但實際上所有的值就會出現在單一行上已經新增額外的分行符號。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-296">In the previous image, additional line breaks have been added to make this screenshot fit, but in actuality all the values would appear on a single line.</span></span>
  
<span data-ttu-id="1cd1b-297">編輯檔案看起來會對應至 outlook.com 和 bing.com、 線條和 AllowedToSpoof 項目變更從 [否] 為 [是]：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-297">Edit the file and look for the line that corresponds to outlook.com and bing.com, and change the AllowedToSpoof Entry from No to Yes:</span></span>
  
![設定詐騙允許為 [是] 透過 Powershell](media/62340452-62d3-4958-9ce9-afe5275a870d.jpg)
  
<span data-ttu-id="1cd1b-299">儲存檔案，然後執行：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-299">Save the file, and then run:</span></span> 
  
```
$UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
```

<span data-ttu-id="1cd1b-300">這將會立即允許傳送未經過驗證的電子郵件從 bing.com \*。 outlook.com。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-300">This will now allow bing.com to send unauthenticated email from \*.outlook.com.</span></span>

<span data-ttu-id="1cd1b-301">**方法 3-建立寄件者/收件者對允許項目**</span><span class="sxs-lookup"><span data-stu-id="1cd1b-301">**Method 3 - Create an allow entry for the sender/recipient pair**</span></span>
  
<span data-ttu-id="1cd1b-p132">您也可以選擇略過所有的垃圾郵件篩選特定的寄件者。如需詳細資訊，請參閱 ＜[如何將安全地新增至 Office 365 中的 [允許] 清單的寄件者](https://blogs.msdn.microsoft.com/tzink/2017/11/29/how-to-securely-add-a-sender-to-an-allow-list-in-office-365/)。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p132">You can also choose to bypass all spam filtering for a particular sender. For more details, see [How to securely add a sender to an allow list in Office 365](https://blogs.msdn.microsoft.com/tzink/2017/11/29/how-to-securely-add-a-sender-to-an-allow-list-in-office-365/).</span></span>
  
<span data-ttu-id="1cd1b-304">如果您使用此方法，則會略過垃圾郵件與部分 phish 篩選，但卻不惡意程式碼篩選。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-304">If you use this method, it will skip spam and some of the phish filtering, but not malware filtering.</span></span>
  
<span data-ttu-id="1cd1b-305">**方法 4-連絡寄件者，他設定電子郵件的驗證**</span><span class="sxs-lookup"><span data-stu-id="1cd1b-305">**Method 4 - Contact the sender and ask them to set up email authentication**</span></span>
  
<span data-ttu-id="1cd1b-p133">垃圾郵件和網路釣魚的問題，因為 Microsoft 建議設定電子郵件驗證所有寄件者。如果您知道的傳送端網域管理員，請連絡它們與這些設定電子郵件驗證記錄，所以您不需要加任何覆寫的要求。如需詳細資訊，請參閱 ＜[系統管理員的網域，是不是 Office 365 客戶](#administrators-of-domains-that-are-not-office-365-customers)"本文稍後的。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p133">Because of the problem of spam and phishing, Microsoft recommends all senders set up email authentication. If you know an administrator of the sending domain, contact them and request that they set up email authentication records so you do not have to add any overrides. For more information, see [Administrators of domains that are not Office 365 customers](#administrators-of-domains-that-are-not-office-365-customers)" later in this article.</span></span> 
  
<span data-ttu-id="1cd1b-309">時可能會很難在先取得傳送驗證的網域，一段時間，以更電子郵件篩選器啟動 junking 或甚至拒絕的電子郵件，它會使它們設定適當的記錄，以確保較佳的傳遞。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-309">While it may be difficult at first to get sending domains to authenticate, over time, as more and more email filters start junking or even rejecting their email, it will cause them to set up the proper records to ensure better delivery.</span></span>
  
### <a name="viewing-reports-of-how-many-messages-were-marked-as-spoofed"></a><span data-ttu-id="1cd1b-310">檢視報告多少郵件已標示成詐騙</span><span class="sxs-lookup"><span data-stu-id="1cd1b-310">Viewing reports of how many messages were marked as spoofed</span></span>

<span data-ttu-id="1cd1b-p134">啟用您反詐騙的原則後，您可以使用威脅智慧周圍多少訊息將標記為 phish 取得數字。若要這樣做，請移至 [安全性]&amp;規範中心 (SCC) 底下 Threat Management\>總管]、 [檢視設定 Phish、 和群組的寄件者的網域] 或 [保護狀態：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p134">Once your anti-spoofing policy is enabled, you can use Threat Intelligence to get numbers around how many messages are marked as phish. To do this, go into the Security &amp; Compliance Center (SCC) under Threat Management \> Explorer, set the View to Phish, and group by Sender Domain or Protection Status:</span></span>
  
![檢視多少訊息將標記為 phish](media/de25009a-44d4-4c5f-94ba-9c75cd9c64b3.jpg)
  
<span data-ttu-id="1cd1b-p135">您可以查看多少已標示為網路釣魚，包括郵件標示為詐騙各種不同的報告與互動。若要深入了解，請參閱[Office 365 威脅智慧快速入門](https://support.office.com/article/get-started-with-office-365-threat-intelligence-38e9b67f-d188-490f-bc91-a1ae4b270441)。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p135">You can interact with the various reports to see how many were marked as phishing, including messages marked as SPOOF. To learn more, see [Get started with Office 365 Threat Intelligence](https://support.office.com/article/get-started-with-office-365-threat-intelligence-38e9b67f-d188-490f-bc91-a1ae4b270441).</span></span>
  
<span data-ttu-id="1cd1b-p136">您不能尚未分割出其郵件已標示為因為詐騙相對於其他類型的網路釣魚 （一般網路釣魚、 網域或使用者模擬等等）。不過，稍後的 2018，您將能夠執行這項作業透過安全性&amp;規範中心。之後，您可以使用開始進行此報告來識別可能是合法的要標示為因失敗的驗證詐騙的傳送端網域。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p136">You cannot yet split out which messages were marked due to spoofing vs. other types of phishing (general phishing, domain or user impersonation, and so on). However, later in 2018, you will be able to do this through the Security &amp; Compliance Center. Once you do, you can use this report as a starting place to identify sending domains that may be legitimate that are being marked as spoof due to failing authentication.</span></span>
  
<span data-ttu-id="1cd1b-319">下列螢幕擷取畫面會針對此資料的外觀相同，但發行時可能會變更提案：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-319">The following screenshot is a proposal for how this data will look, but may change when released:</span></span>
  
![檢視網路釣魚報表所偵測類型](media/dd25d63f-152c-4c55-a07b-184ecda2de81.jpg)
  
<span data-ttu-id="1cd1b-p137">非 ATP 及 E5 客戶，這些報告會提供更新版本中的威脅保護狀態 (TPS) 報告] 下的 2018年但是將至少 24 小時的延遲。此頁面會在更新功能整合安全性&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p137">For non-ATP and E5 customers, these reports will be available later in 2018 under the Threat Protection Status (TPS) reports, but will be delayed by at least 24 hours. This page will be updated as they are integrated into the Security &amp; Compliance Center.</span></span>
  
### <a name="predicting-how-many-messages-will-be-marked-as-spoof"></a><span data-ttu-id="1cd1b-323">預測多少訊息將標記為詐騙</span><span class="sxs-lookup"><span data-stu-id="1cd1b-323">Predicting how many messages will be marked as spoof</span></span>

<span data-ttu-id="1cd1b-p138">稍後的 2018、 Office 365 一次更新其設定可讓您關閉反詐騙強制執行，或上具有 [基本] 或 [高強制執行，您將獲得查看如何在各種設定變更郵件處理的能力。也就是反詐騙已關閉，如果您將能看到多少訊息將會視為詐騙 basic ； 如果或者，如果是 Basic，您將能看到多少的詳細訊息將會視為詐騙若您開啟以高。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p138">Later in 2018, once Office 365 updates its settings to let you turn the anti-spoofing enforcement Off, or on with Basic or High enforcement, you will be given the ability to see how message disposition will change at the various settings. That is, if anti-spoofing is Off, you will be able to see how many messages will be detected as Spoof if you turn to Basic; or, if it's Basic, you will be able to see how many more messages will be detected as Spoof if you turn it to High.</span></span>
  
<span data-ttu-id="1cd1b-p139">此功能目前的狀態下開發。當所定義的詳細資訊，與螢幕擷取畫面的安全性和規範中心及以 PowerShell 範例將會更新此頁面。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p139">This feature is currently under development. As more details are defined, this page will be updated both with screenshots of the Security and Compliance Center, and with PowerShell examples.</span></span>
  
!["怎麼辦"啟用 antispoofing 的報表](media/fdd085ae-02c1-4327-a063-bfe9a32ff1eb.jpg)
  
![可能 UX 的允許詐騙的寄件者](media/53f9f73e-fb01-47f3-9a6d-850c1aef5efe.jpg)
  
### <a name="understanding-how-spam-phishing-and-advanced-phishing-detections-are-combined"></a><span data-ttu-id="1cd1b-330">了解如何垃圾郵件、 網路釣魚及進階網路釣魚結合偵測</span><span class="sxs-lookup"><span data-stu-id="1cd1b-330">Understanding how spam, phishing, and advanced phishing detections are combined</span></span>

<span data-ttu-id="1cd1b-p140">使用或不 ATP，使用 Exchange Online 的組織可以指定服務識別為惡意程式碼、 垃圾郵件、 高信賴垃圾郵件、 網路釣魚、 及大量郵件時要採取的動作。ATP 客戶 ATP 反網路釣魚原則和 EOP 客戶的反網路釣魚原則與訊息可能會瀏覽多種偵測類型 （例如惡意程式碼、 網路釣魚、 與使用者模擬） 事實，可能是一些不確定其原則可套用。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p140">Organizations that use Exchange Online, with or without ATP, can specify which actions to take when the service identifies messages as malware, spam, high confidence spam, phishing, and bulk. With the ATP Anti-phishing policies for ATP customers, and the Anti-phishing policies for EOP customers, and the fact that a message may hit multiple detection types (for example, malware, phishing, and user-impersonation), there may be some confusion as to which policy applies.</span></span> 
  
<span data-ttu-id="1cd1b-333">一般而言，CAT （類別） 屬性中的 X Forefront-反垃圾郵件報告標頭中所識別套用至郵件的原則。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-333">In general, the policy applied to a message is identified in the X-Forefront-Antispam-Report header in the CAT (Category) property.</span></span> 
  
|<span data-ttu-id="1cd1b-334">**Priority (優先順序)**</span><span class="sxs-lookup"><span data-stu-id="1cd1b-334">**Priority**</span></span>|<span data-ttu-id="1cd1b-335">**原則**</span><span class="sxs-lookup"><span data-stu-id="1cd1b-335">**Policy**</span></span>|<span data-ttu-id="1cd1b-336">**類別**</span><span class="sxs-lookup"><span data-stu-id="1cd1b-336">**Category**</span></span>|<span data-ttu-id="1cd1b-337">**其中 managed？**</span><span class="sxs-lookup"><span data-stu-id="1cd1b-337">**Where managed?**</span></span>|<span data-ttu-id="1cd1b-338">**適用於**</span><span class="sxs-lookup"><span data-stu-id="1cd1b-338">**Applies to**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1cd1b-339">1 </span><span class="sxs-lookup"><span data-stu-id="1cd1b-339">1</span></span>  <br/> |<span data-ttu-id="1cd1b-340">惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="1cd1b-340">Malware</span></span>  <br/> |<span data-ttu-id="1cd1b-341">MALW</span><span class="sxs-lookup"><span data-stu-id="1cd1b-341">MALW</span></span>  <br/> |[<span data-ttu-id="1cd1b-342">惡意程式碼原則</span><span class="sxs-lookup"><span data-stu-id="1cd1b-342">Malware policy</span></span>](https://technet.microsoft.com/en-us/library/jj200745%28v=exchg.150%29.aspx) <br/> |<span data-ttu-id="1cd1b-343">所有組織</span><span class="sxs-lookup"><span data-stu-id="1cd1b-343">All organizations</span></span>  <br/> |
|<span data-ttu-id="1cd1b-344">2 </span><span class="sxs-lookup"><span data-stu-id="1cd1b-344">2</span></span>  <br/> |<span data-ttu-id="1cd1b-345">網路釣魚</span><span class="sxs-lookup"><span data-stu-id="1cd1b-345">Phishing</span></span>  <br/> |<span data-ttu-id="1cd1b-346">PHSH</span><span class="sxs-lookup"><span data-stu-id="1cd1b-346">PHSH</span></span>  <br/> |[<span data-ttu-id="1cd1b-347">主控的內容篩選原則</span><span class="sxs-lookup"><span data-stu-id="1cd1b-347">Hosted content filter policy</span></span>](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |<span data-ttu-id="1cd1b-348">所有組織</span><span class="sxs-lookup"><span data-stu-id="1cd1b-348">All organizations</span></span>  <br/> |
|<span data-ttu-id="1cd1b-349">3 </span><span class="sxs-lookup"><span data-stu-id="1cd1b-349">3</span></span>  <br/> |<span data-ttu-id="1cd1b-350">高度信賴垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="1cd1b-350">High confidence spam</span></span>  <br/> |<span data-ttu-id="1cd1b-351">HSPM</span><span class="sxs-lookup"><span data-stu-id="1cd1b-351">HSPM</span></span>  <br/> |[<span data-ttu-id="1cd1b-352">主控的內容篩選原則</span><span class="sxs-lookup"><span data-stu-id="1cd1b-352">Hosted content filter policy</span></span>](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |<span data-ttu-id="1cd1b-353">所有組織</span><span class="sxs-lookup"><span data-stu-id="1cd1b-353">All organizations</span></span>  <br/> |
|<span data-ttu-id="1cd1b-354">4 </span><span class="sxs-lookup"><span data-stu-id="1cd1b-354">4</span></span>  <br/> |<span data-ttu-id="1cd1b-355">詐騙</span><span class="sxs-lookup"><span data-stu-id="1cd1b-355">Spoofing</span></span>  <br/> |<span data-ttu-id="1cd1b-356">詐騙</span><span class="sxs-lookup"><span data-stu-id="1cd1b-356">SPOOF</span></span>  <br/> |<span data-ttu-id="1cd1b-357">[反網路釣魚原則](https://go.microsoft.com/fwlink/?linkid=864553)、[詐騙智慧](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf)</span><span class="sxs-lookup"><span data-stu-id="1cd1b-357">[Anti-phishing policy](https://go.microsoft.com/fwlink/?linkid=864553),          [Spoof intelligence](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf)</span></span> <br/> |<span data-ttu-id="1cd1b-358">所有組織</span><span class="sxs-lookup"><span data-stu-id="1cd1b-358">All organizations</span></span>  <br/> |
|<span data-ttu-id="1cd1b-359">5 </span><span class="sxs-lookup"><span data-stu-id="1cd1b-359">5</span></span>  <br/> |<span data-ttu-id="1cd1b-360">垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="1cd1b-360">Spam</span></span>  <br/> |<span data-ttu-id="1cd1b-361">SPM</span><span class="sxs-lookup"><span data-stu-id="1cd1b-361">SPM</span></span>  <br/> |[<span data-ttu-id="1cd1b-362">主控的內容篩選原則</span><span class="sxs-lookup"><span data-stu-id="1cd1b-362">Hosted content filter policy</span></span>](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |<span data-ttu-id="1cd1b-363">所有組織</span><span class="sxs-lookup"><span data-stu-id="1cd1b-363">All organizations</span></span>  <br/> |
|<span data-ttu-id="1cd1b-364">6 </span><span class="sxs-lookup"><span data-stu-id="1cd1b-364">6</span></span>  <br/> |<span data-ttu-id="1cd1b-365">大量</span><span class="sxs-lookup"><span data-stu-id="1cd1b-365">Bulk</span></span>  <br/> |<span data-ttu-id="1cd1b-366">大量</span><span class="sxs-lookup"><span data-stu-id="1cd1b-366">BULK</span></span>  <br/> |[<span data-ttu-id="1cd1b-367">主控的內容篩選原則</span><span class="sxs-lookup"><span data-stu-id="1cd1b-367">Hosted content filter policy</span></span>](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |<span data-ttu-id="1cd1b-368">所有組織</span><span class="sxs-lookup"><span data-stu-id="1cd1b-368">All organizations</span></span>  <br/> |
|<span data-ttu-id="1cd1b-369">7 </span><span class="sxs-lookup"><span data-stu-id="1cd1b-369">7</span></span>  <br/> |<span data-ttu-id="1cd1b-370">網域模擬</span><span class="sxs-lookup"><span data-stu-id="1cd1b-370">Domain Impersonation</span></span>  <br/> |<span data-ttu-id="1cd1b-371">DIMP</span><span class="sxs-lookup"><span data-stu-id="1cd1b-371">DIMP</span></span>  <br/> |[<span data-ttu-id="1cd1b-372">反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="1cd1b-372">Anti-phishing policy</span></span>](https://go.microsoft.com/fwlink/?linkid=864553) <br/> |<span data-ttu-id="1cd1b-373">僅限具有 ATP 組織</span><span class="sxs-lookup"><span data-stu-id="1cd1b-373">Organizations with ATP only</span></span>  <br/> |
|<span data-ttu-id="1cd1b-374">8 </span><span class="sxs-lookup"><span data-stu-id="1cd1b-374">8</span></span>  <br/> |<span data-ttu-id="1cd1b-375">使用者模擬</span><span class="sxs-lookup"><span data-stu-id="1cd1b-375">User Impersonation</span></span>  <br/> |<span data-ttu-id="1cd1b-376">UIMP</span><span class="sxs-lookup"><span data-stu-id="1cd1b-376">UIMP</span></span>  <br/> |[<span data-ttu-id="1cd1b-377">反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="1cd1b-377">Anti-phishing policy</span></span>](https://go.microsoft.com/fwlink/?linkid=864553) <br/> |<span data-ttu-id="1cd1b-378">僅限具有 ATP 組織</span><span class="sxs-lookup"><span data-stu-id="1cd1b-378">Organizations with ATP only</span></span> <br/> |
   
<span data-ttu-id="1cd1b-p141">如果您有多個不同的反網路釣魚原則，將套用一個在最高優先順序。例如，假設您有兩個原則：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p141">If you have multiple different Anti-phishing policies, the one at the highest priority will apply. For example, suppose you have two policies:</span></span>
  
|<span data-ttu-id="1cd1b-381">**原則**</span><span class="sxs-lookup"><span data-stu-id="1cd1b-381">**Policy**</span></span>|<span data-ttu-id="1cd1b-382">**Priority (優先順序)**</span><span class="sxs-lookup"><span data-stu-id="1cd1b-382">**Priority**</span></span>|<span data-ttu-id="1cd1b-383">**使用者/網域模擬**</span><span class="sxs-lookup"><span data-stu-id="1cd1b-383">**User/Domain Impersonation**</span></span>|<span data-ttu-id="1cd1b-384">**反詐騙**</span><span class="sxs-lookup"><span data-stu-id="1cd1b-384">**Anti-spoofing**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1cd1b-385">A</span><span class="sxs-lookup"><span data-stu-id="1cd1b-385">A</span></span>  <br/> |<span data-ttu-id="1cd1b-386">1 </span><span class="sxs-lookup"><span data-stu-id="1cd1b-386">1</span></span>  <br/> |<span data-ttu-id="1cd1b-387">On</span><span class="sxs-lookup"><span data-stu-id="1cd1b-387">On</span></span>  <br/> |<span data-ttu-id="1cd1b-388">Off</span><span class="sxs-lookup"><span data-stu-id="1cd1b-388">Off</span></span>  <br/> |
|<span data-ttu-id="1cd1b-389">B</span><span class="sxs-lookup"><span data-stu-id="1cd1b-389">B</span></span>  <br/> |<span data-ttu-id="1cd1b-390">2 </span><span class="sxs-lookup"><span data-stu-id="1cd1b-390">2</span></span>  <br/> |<span data-ttu-id="1cd1b-391">Off</span><span class="sxs-lookup"><span data-stu-id="1cd1b-391">Off</span></span>  <br/> |<span data-ttu-id="1cd1b-392">On</span><span class="sxs-lookup"><span data-stu-id="1cd1b-392">On</span></span>  <br/> |
   
<span data-ttu-id="1cd1b-393">如果訊息有和識別身分詐騙與使用者模擬與相同的一組使用者範圍的原則及原則 B 則郵件會被視為詐騙但採取任何動作套用自反詐騙已關閉並詐騙執行在較高的優先順序 (4) 與使用者模擬 (8)。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-393">If a message comes in and is identified as both spoofing and user impersonation, and the same set of users is scoped to Policy A and Policy B, then the message is treated as a spoof but no action is applied since Anti-spoofing is turned off, and SPOOF runs at a higher priority (4) than User Impersonation (8).</span></span>
  
<span data-ttu-id="1cd1b-394">若要讓其他類型的網路釣魚原則套用，您將需要調整的各種原則套用至人員設定。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-394">To make other types of phishing policy apply, you will need to adjust the settings of who the various policies are applied to.</span></span>
  
### <a name="legitimate-scenarios-to-disable-anti-spoofing"></a><span data-ttu-id="1cd1b-395">若要停用反詐騙的合法案例</span><span class="sxs-lookup"><span data-stu-id="1cd1b-395">Legitimate scenarios to disable anti-spoofing</span></span>

<span data-ttu-id="1cd1b-p142">反詐騙更妥善地保護從網路釣魚攻擊的客戶與因此停用反詐騙保護不鼓勵。藉由停用它，就可能會解決某些短期誤判，但長期您將會公開給更大的風險。設定驗證寄件者兩側或網路釣魚原則中進行調整的成本通常是單次事件或是需要僅限最小、 定期維護。不過，其中具有已公開的資料、 網路釣魚攻擊復原成本或資產已危害是更高。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p142">Anti-spoofing better protects customers from phishing attacks, and therefore disabling anti-spoofing protection is strongly discouraged. By disabling it, you may resolve some short-term false positives, but long term you will be exposed to more risk. The cost for setting up authentication on the sender side, or making adjustments in the phishing policies, are usually one-time events or require only minimal, periodic maintenance. However, the cost to recover from a phishing attack where data has been exposed, or assets have been compromised is much higher.</span></span>
  
<span data-ttu-id="1cd1b-400">此原因，最好是透過反詐騙誤判比若要停用反詐騙保護運作。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-400">For this reason, it is better to work through anti-spoofing false positives than to disable anti-spoof protection.</span></span>
  
<span data-ttu-id="1cd1b-401">但是，有其中反詐騙應停用，而這是有其他郵件篩選的合法案例中的郵件路由、 與 Office 365 產品不是電子郵件路徑中的第一個躍點：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-401">However, there is a legitimate scenario where anti-spoofing should be disabled, and that is when there are additional mail-filtering products in the message routing, and Office 365 is not the first hop in the email path:</span></span>
  
![客戶 MX 記錄未指向 Office 365](media/62127c16-cfb8-4880-9cad-3c12d827c67e.jpg)
  
<span data-ttu-id="1cd1b-403">另一部伺服器可能是 Exchange 內部部署郵件伺服器，篩選裝置 Ironport，例如郵件或其他雲端託管服務。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-403">The other server may be an Exchange on-premise mail server, a mail filtering device such as Ironport, or another cloud hosted service.</span></span>
  
<span data-ttu-id="1cd1b-p143">如果收件者的網域的 MX 記錄未指向 Office 365，然後有不需要在停用反詐騙因為 Office 365 查詢接收網域的 MX 記錄並隱藏反詐騙如果其指向另一個服務。如果您不知道您的網域是否在前端具有記憶體另一部伺服器，您可以使用 MX 工具箱類似的網站来查詢的 MX 記錄。它可能之後類似以下的某個項目：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p143">If the MX record of the recipient domain does not point to Office 365, then there is no need to disable anti-spoofing because Office 365 looks up your receiving domain's MX record and suppresses anti-spoofing if it points to another service. If you don't know if your domain has another server in front, you can use a website like MX Toolbox to look up the MX record. It might say something like the following:</span></span>
  
![MX 記錄會指出網域未指向 Office 365](media/d868bb9f-3462-49aa-baea-9447a3ce4877.jpg)
  
<span data-ttu-id="1cd1b-408">此網域都未指向 Office 365 讓 Office 365 不會套用反詐騙強制執行的 MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-408">This domain has an MX record that does not point to Office 365, so Office 365 would not apply anti-spoofing enforcement.</span></span>
  
<span data-ttu-id="1cd1b-p144">不過，如果*沒有*的收件者的網域的 MX 記錄指向 Office 365 中，即使在 Office 365 前方的另一個服務，然後您應該停用反詐騙。最常見的範例是透過收件者修正：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p144">However, if the MX record of the recipient domain  *does*  point to Office 365, even though there is another service in front of Office 365, then you should disable anti-spoofing. The most common example is through the use of a recipient rewrite:</span></span> 
  
![收件者修正路由圖表](media/070d90d1-50a0-42e4-9fd3-920bc99a7cad.jpg)
  
<span data-ttu-id="1cd1b-412">網域 contoso.com 的 MX 記錄指向內部部署伺服器上，當網域 @office365.contoso.net MX 記錄指向 Office 365 因為包含\*。 protection.outlook.com，或\*。 eo.outlook.com MX 記錄中的：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-412">The domain contoso.com's MX record points to the on-premise server, while the domain @office365.contoso.net's MX record points to Office 365 because it contains \*.protection.outlook.com, or \*.eo.outlook.com in the MX record:</span></span>
  
![MX 記錄指向 Office 365，因此可能收件者修正](media/4101ad51-ef92-4907-b466-b41d14d344ca.jpg)
  
<span data-ttu-id="1cd1b-p145">請務必區分及它上有收件者修正時的收件者的網域的 MX 記錄未指向 Office 365。請務必告知下列兩種情況下之間的差異。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p145">Be sure to differentiate when a recipient domain's MX record does not point to Office 365, and when it has undergone a recipient rewrite. It is important to tell the difference between these two cases.</span></span>
  
<span data-ttu-id="1cd1b-416">如果您不確定接收網域上有收件者修正，有時您可以分清 \\servername\share\spbr 郵件標頭。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-416">If you are unsure whether or not your receiving domain has undergone a recipient-rewrite, sometimes you can tell by looking at the message headers.</span></span>
  
<span data-ttu-id="1cd1b-417">） 首先，查看的驗證結果標頭中的收件者的網域的郵件標頭：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-417">a) First, look at the headers in the message for the recipient domain in the Authentication-Results header:</span></span> 
  
```
Authentication-Results: spf=fail (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; office365.contoso.net; dkim=fail
  (body hash did not verify) header.d=simple.example.com;
  office365.contoso.net; dmarc=none action=none
  header.from=example.com; compauth=fail reason=001
```

<span data-ttu-id="1cd1b-p146">收件者的網域是粗體紅色的文字上方，在此案例的 office365.contoso.net 中找到。這可能是不同的 [收件者在收件者： 標頭：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p146">The recipient domain is found in the bold red text above, in this case office365.contoso.net. This may be different that the recipient in the To: header:</span></span>
  
<span data-ttu-id="1cd1b-420">： 範例收件者\<@ contoso.com 收件者\></span><span class="sxs-lookup"><span data-stu-id="1cd1b-420">To: Example Recipient \<recipient @ contoso.com\></span></span>
  
<span data-ttu-id="1cd1b-p147">執行實際收件者的網域的 MX 記錄查閱。如果它包含\*。 protection.outlook.com、 mail.messaging.microsoft.com、 \*。 eo.outlook.com 或 mail.global.frontbridge.com，這表示 MX 點至 Office 365。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p147">Perform an MX-record lookup of the actual recipient domain. If it contains \*.protection.outlook.com, mail.messaging.microsoft.com, \*.eo.outlook.com, or mail.global.frontbridge.com, that means that the MX points to Office 365.</span></span>
  
<span data-ttu-id="1cd1b-p148">如果它不包含這些值，就表示 MX 未指向 Office 365。您可以使用來確認這項工具是 MX 工具箱]。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p148">If it does not contain those values, then it means that the MX does not point to Office 365. One tool you can use to verify this is MX Toolbox.</span></span>
  
<span data-ttu-id="1cd1b-425">針對特定本例中為下列指出該 contoso.com，因為它是 [收件者起來收件者的網域： 標頭] 有 MX 記錄指向在 prem 伺服器：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-425">For this particular example, the following says that contoso.com, the domain that looks like the recipient since it was the To: header, has MX record points to an on-prem server:</span></span>
  
![MX 記錄指向在 prem 伺服器](media/2444144a-9a90-4319-96b2-d115041f669f.jpg)
  
<span data-ttu-id="1cd1b-427">不過，實際的收件者是的 office365.contoso.net 其 MX 記錄未指向 Office 365：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-427">However, the actual recipient is office365.contoso.net whose MX record does point to Office 365:</span></span>
  
![MX 點至 Office 365 必須收件者修正](media/10cf3245-9b50-475a-b655-d8a51f99d812.jpg)
  
<span data-ttu-id="1cd1b-429">因此，此訊息可能上有收件者修正。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-429">Therefore, this message has likely undergone a recipient-rewrite.</span></span>
  
<span data-ttu-id="1cd1b-p149">b） 第二，請務必區分的收件者將一般使用案例。若要修正的收件者網域\*。 onmicrosoft.com，但是修正其\*。 mail.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p149">b) Second, be sure to distinguish between common use cases of recipient rewrites. If you are going to rewrite the recipient domain to \*.onmicrosoft.com, instead rewrite it to \*.mail.onmicrosoft.com.</span></span>
  
<span data-ttu-id="1cd1b-432">一旦您識別背後的另一部伺服器路由傳送的最後一個收件者網域和收件者的網域的 MX 記錄實際指向 Office 365 （如其 DNS 記錄中發佈），您可能會繼續停用反詐騙。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-432">Once you have identified the final recipient domain that is routed behind another server and the recipient domain's MX record actually points to Office 365 (as published in its DNS records), you may proceed to disable anti-spoofing.</span></span>
  
<span data-ttu-id="1cd1b-433">請記住，您不需要若停用反詐騙網域的路由路徑中的第一個躍點是 Office 365、 僅限時，它會背後的一或多個服務。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-433">Remember, you don't want to disable anti-spoofing if the domain's first hop in the routing path is Office 365, only when it's behind one or more services.</span></span>
  
### <a name="how-to-disable-anti-spoofing"></a><span data-ttu-id="1cd1b-434">如何停用反詐騙</span><span class="sxs-lookup"><span data-stu-id="1cd1b-434">How to disable anti-spoofing</span></span>

<span data-ttu-id="1cd1b-435">如果您已建立反網路釣魚原則，將 $false EnableAntispoofEnforcement 參數：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-435">If you already have an Anti-phishing policy created, set the EnableAntispoofEnforcement parameter to $false:</span></span> 
  
```
$name = "<name of policy>"
Set-AntiphishPolicy -Identity $name -EnableAntiSpoofEnforcement $false 

```

<span data-ttu-id="1cd1b-436">如果您不知道要停用的原則 （或原則） 的名稱，您可以將其顯示：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-436">If you don't know the name of the policy (or policies) to disable, you can display them:</span></span> 
  
```
Get-AntiphishPolicy | fl Name
```

<span data-ttu-id="1cd1b-p150">如果您沒有任何現有的反網路釣魚原則，您可以建立 web 應用程式並再加以停用 （即使您不需要將原則、 反詐騙仍套用 ； 在 2018年後面上、 將為您建立的預設原則且可以然後停用，而不是建立一個）.您必須在多個步驟中執行這項作業：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p150">If you don't have any existing anti-phishing policies, you can create one and then disable it (even if you don't have a policy, anti-spoofing is still applied; later on in 2018, a default policy will be created for you and you can then disable that instead of creating one). You will have to do this in multiple steps:</span></span> 
  
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
# Finally, scope the antiphishing policy to the domains
Set-AntiphishPolicy -Identity $name -EnableAntispoofEnforcement $false 

```

<span data-ttu-id="1cd1b-p151">停用反詐騙只有透過指令程式 (在 Q2 2018 稍後才會出現 [安全性]&amp;規範中心)。如果您沒有 PowerShell 存取、 建立支援票證。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p151">Disabling anti-spoofing is only available via cmdlet (later in Q2 2018 it will be available in the Security &amp; Compliance Center). If you do not have access to PowerShell, create a support ticket.</span></span>
  
<span data-ttu-id="1cd1b-p152">請記住，這應僅套用至、 經歷間接路由傳送至 Office 365 時的網域。抵禦因一些誤判停用反詐騙誘惑、 就較好的作法長期透過其運作。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p152">Remember, this should only be applied to domains that undergo indirect routing when sent to Office 365. Resist the temptation to disable anti-spoofing because of some false positives, it will be better in the long run to work through them.</span></span>
  
### <a name="information-for-individual-users"></a><span data-ttu-id="1cd1b-443">針對個別使用者的資訊</span><span class="sxs-lookup"><span data-stu-id="1cd1b-443">Information for individual users</span></span>

<span data-ttu-id="1cd1b-p153">個別使用者限制在他們可以互動的反詐騙 safety 提示。但是，有幾個的部分要怎麼做才能解決常見的案例。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p153">Individual users are limited in how they can interact with the anti-spoofing safety tip. However, there are several things you can do to resolve common scenarios.</span></span>
  
### <a name="common-scenario-1---mailbox-forwarding"></a><span data-ttu-id="1cd1b-446">常見案例 #1-信箱轉寄</span><span class="sxs-lookup"><span data-stu-id="1cd1b-446">Common scenario #1 - Mailbox forwarding</span></span>

<span data-ttu-id="1cd1b-p154">如果您使用其他電子郵件服務，將您的電子郵件轉寄至 Office 365 或 Outlook.com 的電子郵件可能會標示為詐騙及接收紅色 safety 提示。Office 365 和 Outlook.com 規劃地址這自動轉寄時 Outlook.com、 Office 365、 Gmail 或任何其他使用[弧線通訊協定](https://arc-spec.org)的服務之一。不過，部署該修正，直到使用者應使用連線帳戶功能匯入其訊息直接，而不是使用 [轉接] 選項。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p154">If you use another email service and forward your email to Office 365 or Outlook.com, your email may be marked as spoofing and receive a red safety tip. Office 365 and Outlook.com plan to address this automatically when the forwarder is one of Outlook.com, Office 365, Gmail, or any other service that uses the [ARC protocol](https://arc-spec.org). However, until that fix is deployed, users should use the Connected Accounts feature to import their messages directly, rather than using the forwarding option.</span></span>
  
<span data-ttu-id="1cd1b-450">若要設定 Office 365 的連線的帳戶，選取 [齒輪圖示的右上角的 Office 365 web 介面\>郵件\>郵件\>帳戶\>連線的帳戶。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-450">To set up connected accounts in Office 365, select the Gear icon in the top right corner of the Office 365 web interface \> Mail \> Mail \> Accounts \> Connected accounts.</span></span>
  
![Office 365-連線帳戶選項](media/e8e841ca-8861-4d83-8506-2a0858c51010.jpg)
  
<span data-ttu-id="1cd1b-452">在 Outlook.com、 程序是齒輪圖示\>選項\>郵件\>帳戶\>連線的帳戶。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-452">In Outlook.com, the process is the Gear icon \> Options \> Mail \> Accounts \> Connected accounts.</span></span>
  
### <a name="common-scenario-2---discussion-lists"></a><span data-ttu-id="1cd1b-453">常見案例 #2-討論區清單</span><span class="sxs-lookup"><span data-stu-id="1cd1b-453">Common scenario #2 - Discussion lists</span></span>

<span data-ttu-id="1cd1b-454">討論區清單已知有問題反-詐騙方式因為它們轉寄郵件和修改其內容仍保留從原始： 地址。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-454">Discussion lists are known to have problems with anti-spoofing due to the way they forward the message and modify its contents yet retain the original From: address.</span></span>
  
<span data-ttu-id="1cd1b-p155">例如，假設您的電子郵件地址為 user @ contoso.com，而且您感興趣的小鳥監控以及加入討論區清單 birdwatchers，@ example.com。當您將訊息傳送至討論區清單時，您可能會傳送這種方式：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p155">For example, suppose your email address is user @ contoso.com, and you are interested in Bird Watching and join the discussion list birdwatchers @ example.com. When you send a message to the discussion list, you might send it this way:</span></span>
  
<span data-ttu-id="1cd1b-457">**從：** John Doe \<@ contoso.com 的使用者\></span><span class="sxs-lookup"><span data-stu-id="1cd1b-457">**From:** John Doe \<user @ contoso.com\></span></span> 
  
<span data-ttu-id="1cd1b-458">**至：** Birdwatcher 的討論區清單\<birdwatchers @ example.com\></span><span class="sxs-lookup"><span data-stu-id="1cd1b-458">**To:** Birdwatcher's Discussion List \<birdwatchers @ example.com\></span></span> 
  
<span data-ttu-id="1cd1b-p156">**Subject:** 更好的檢視周 Rainier 頂端的藍色 jays 本週</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p156">**Subject:** Great viewing of blue jays at the top of Mt. Rainier this week</span></span> 
  
<span data-ttu-id="1cd1b-p157">任何人都要取出檢視從周 Rainier 本週吗？</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p157">Anyone want to check out the viewing this week from Mt. Rainier?</span></span>
  
<span data-ttu-id="1cd1b-463">當電子郵件清單接收郵件時，他們格式化郵件、 修改其內容和重播其餘部分的這由組成參與者從許多不同的電子郵件接收器討論區清單的成員。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-463">When the email list receives the message, they format the message, modify its contents, and replay it to the rest of the members on the discussion list which is made up of participants from many different email receivers.</span></span>
  
<span data-ttu-id="1cd1b-464">**從：** John Doe \<@ contoso.com 的使用者\></span><span class="sxs-lookup"><span data-stu-id="1cd1b-464">**From:** John Doe \<user @ contoso.com\></span></span> 
  
<span data-ttu-id="1cd1b-465">**至：** Birdwatcher 的討論區清單\<birdwatchers @ example.com\></span><span class="sxs-lookup"><span data-stu-id="1cd1b-465">**To:** Birdwatcher's Discussion List \<birdwatchers @ example.com\></span></span> 
  
<span data-ttu-id="1cd1b-p158">**Subject:**[BIRDWATCHERS]更好的檢視周 Rainier 頂端的藍色 jays 本週</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p158">**Subject:** [BIRDWATCHERS] Great viewing of blue jays at the top of Mt. Rainier this week</span></span> 
  
<span data-ttu-id="1cd1b-p159">任何人都要取出檢視從周 Rainier 本週吗？</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p159">Anyone want to check out the viewing this week from Mt. Rainier?</span></span>
  
---
  
<span data-ttu-id="1cd1b-p160">此訊息傳送至 Birdwatchers 討論區清單。您可以隨時取消訂閱。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p160">This message was sent to the Birdwatchers Discussion List. You can unsubscribe at any time.</span></span>
  
<span data-ttu-id="1cd1b-p161">在上述重新執行的郵件已從相同： 已將標籤新增至主旨行及訊息的底部頁尾修改地址 （使用者 @ contoso.com），但原始郵件。這種類型的郵件修改常見郵寄清單中，且可能會導致誤判。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p161">In the above, the replayed message has the same From: address (user @ contoso.com) but the original message has been modified by adding a tag to the Subject line, and a footer to the bottom of the message. This type of message modification is common in mailing lists, and may result in false positives.</span></span>
  
<span data-ttu-id="1cd1b-474">如果您或組織中某人郵寄清單的管理員，您可以將它設定成通過反詐騙檢查。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-474">If you or someone in your organization is an administrator of the mailing list, you may be able to configure it to pass anti-spoofing checks.</span></span>
  
- <span data-ttu-id="1cd1b-475">檢查在 DMARC.org 常見問題集：[我操作郵寄清單與我想要與 DMARC 交互操作，該怎麼辦？](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F)</span><span class="sxs-lookup"><span data-stu-id="1cd1b-475">Check the FAQ at DMARC.org: [I operate a mailing list and I want to interoperate with DMARC, what should I do?](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F)</span></span>
    
- <span data-ttu-id="1cd1b-476">閱讀此部落格文章 /kb/2261507/zh-tw 中的指示：[可避免失敗 DMARC 與交互操作郵寄清單運算子的提示](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/)</span><span class="sxs-lookup"><span data-stu-id="1cd1b-476">Read the instructions at this blog post: [A tip for mailing list operators to interoperate with DMARC to avoid failures](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/)</span></span>
    
- <span data-ttu-id="1cd1b-477">請考慮支援弧線，請參閱郵寄清單伺服器上安裝更新[https://arc-spec.org](https://arc-spec.org/)</span><span class="sxs-lookup"><span data-stu-id="1cd1b-477">Consider installing updates on your mailing list server to support ARC, see [https://arc-spec.org](https://arc-spec.org/)</span></span>
    
<span data-ttu-id="1cd1b-478">如果您沒有郵寄清單的擁有權：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-478">If you do not have ownership of the mailing list:</span></span>
  
- <span data-ttu-id="1cd1b-479">您可以要求之郵寄清單維護程式實作其中一個選項上述 （他們也應該有設定郵寄清單來自網域的電子郵件驗證）</span><span class="sxs-lookup"><span data-stu-id="1cd1b-479">You can request the maintainer of the mailing list to implement one of the options above (they should also have email authentication set up for the domain the mailing list is relaying from)</span></span>
    
- <span data-ttu-id="1cd1b-p162">您可以在您的電子郵件用戶端若要將郵件移至收件匣中建立信箱規則。您也可以要求您組織的系統管理員可以設定允許規則或一節中討論覆寫做為管理合法寄件者所傳送未經過驗證的電子郵件</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p162">You can create mailbox rules in your email client to move messages to the Inbox. You can also request your organization's administrators to set up allow rules, or overrides as discussed in the section Managing legitimate senders who are sending unauthenticated email</span></span>
    
- <span data-ttu-id="1cd1b-482">您可以建立 Office 365 來建立以將它視為合法郵寄清單覆寫支援票證</span><span class="sxs-lookup"><span data-stu-id="1cd1b-482">You can create a support ticket with Office 365 to create an override for the mailing list to treat it as legitimate</span></span>
    
### <a name="other-scenarios"></a><span data-ttu-id="1cd1b-483">其他案例</span><span class="sxs-lookup"><span data-stu-id="1cd1b-483">Other scenarios</span></span>

1. <span data-ttu-id="1cd1b-p163">若上述的常見案例的情況現況，郵件為 false 的正數後向 Microsoft 報告。如需詳細資訊，請參閱區段[方式可以我回報垃圾郵件或非垃圾郵件訊息給 Microsoft？](#how-can-i-report-spam-or-non-spam-messages-back-to-microsoft)在本文後面。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p163">If neither of the above common scenarios applies to your situation, report the message as a false positive back to Microsoft. For more information, see the section [How can I report spam or non-spam messages back to Microsoft?](#how-can-i-report-spam-or-non-spam-messages-back-to-microsoft) later in this article.</span></span> 
    
2. <span data-ttu-id="1cd1b-p164">您也可以連絡電子郵件管理員可以引發為與 Microsoft 支援票證。Microsoft 工程小組會調查郵件已標示為詐騙的原因。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p164">You may also contact your email administrator who can raise it as a support ticket with Microsoft. The Microsoft engineering team will investigate why the message was marked as a spoof.</span></span>
    
3. <span data-ttu-id="1cd1b-p165">此外，如果您知道有寄件者是及健全他們不被惡意詐騙，您可能會回覆回到表示他們會從未驗證的郵件伺服器傳送郵件寄件者。這有時候會導致連絡設定必要的電子郵件驗證記錄，將其 IT 系統管理員的原始寄件者。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p165">Additionally, if you know who the sender is and are confident they are not being maliciously spoofed, you may reply back to the sender indicating that they are sending messages from a mail server that does not authenticate. This sometimes results in the original sender contacting their IT administrator who will set up the required email authentication records.</span></span>
  
<span data-ttu-id="1cd1b-p166">當足夠的寄件者回覆回網域擁有者所應設定電子郵件的驗證記錄時，它 spurs 它們到採取動作。雖然 Microsoft 也適用於具有網域擁有者發佈所需的記錄，它可協助更為個別使用者要求時才。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p166">When enough senders reply back to domain owners that they should set up email authentication records, it spurs them into taking action. While Microsoft also works with domain owners to publish the required records, it helps even more when individual users request it.</span></span>
    
4. <span data-ttu-id="1cd1b-p167">（選用） 將寄件者新增至安全的寄件者清單。不過，請注意如果 phisher 假裝該帳戶，它會傳遞至您的信箱。因此，應謹慎使用此選項。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p167">Optionally, add the sender to your Safe Senders list. However, be aware that if a phisher spoofs that account, it will be delivered to your mailbox. Therefore, this option should be used sparingly.</span></span>
    
## <a name="how-senders-to-microsoft-should-prepare-for-anti-spoofing-protection"></a><span data-ttu-id="1cd1b-495">給 Microsoft 的寄件者應如何準備反詐騙保護</span><span class="sxs-lookup"><span data-stu-id="1cd1b-495">How senders to Microsoft should prepare for anti-spoofing protection</span></span>

<span data-ttu-id="1cd1b-496">如果您是系統管理員目前將郵件傳送至 Microsoft Office 365 或 Outlook.com 中，您必須確定已正確地驗證您的電子郵件為垃圾郵件或 phish 否則可能會標示為。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-496">If you are an administrator who currently sends messages to Microsoft, either Office 365 or Outlook.com, you should ensure that your email is properly authenticated otherwise it may be marked as spam or phish.</span></span> 
  
### <a name="customers-of-office-365"></a><span data-ttu-id="1cd1b-497">Office 365 的客戶</span><span class="sxs-lookup"><span data-stu-id="1cd1b-497">Customers of Office 365</span></span>

<span data-ttu-id="1cd1b-498">如果您是 Office 365 客戶與您使用 Office 365 傳送輸出電子郵件：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-498">If you are an Office 365 customer and you use Office 365 to send outbound email:</span></span>
  
- <span data-ttu-id="1cd1b-499">為您[設定 SPF 避免詐騙的 Office 365 中](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)的網域</span><span class="sxs-lookup"><span data-stu-id="1cd1b-499">For your domains, [Set up SPF in Office 365 to help prevent spoofing](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)</span></span>
    
- <span data-ttu-id="1cd1b-500">主要網域，[使用 DKIM 驗證從您在 Office 365 中的自訂網域傳送的輸出電子郵件](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)</span><span class="sxs-lookup"><span data-stu-id="1cd1b-500">For your primary domains, [Use DKIM to validate outbound email sent from your custom domain in Office 365](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)</span></span>
    
- <span data-ttu-id="1cd1b-501">[請考慮 DMARC 記錄設定](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)為您的網域來判斷誰合法的寄件者</span><span class="sxs-lookup"><span data-stu-id="1cd1b-501">[Consider setting up DMARC records](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email) for your domain to determine who are your legitimate senders</span></span> 
    
<span data-ttu-id="1cd1b-p168">Microsoft 不提供每個 SPF、 DKIM，以及 DMARC 詳細的實作指導方針。但是，有許多的線上發佈的資訊。也有 3rd 廠商公司專用協助組織設定電子郵件的驗證記錄。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p168">Microsoft does not provide detailed implementation guidelines for each of SPF, DKIM, and DMARC. However, there is a lot of information published online. There are also 3rd party companies dedicated to helping your organization set up email authentication records.</span></span>
  
### <a name="administrators-of-domains-that-are-not-office-365-customers"></a><span data-ttu-id="1cd1b-505">系統管理員的不是 Office 365 客戶的網域</span><span class="sxs-lookup"><span data-stu-id="1cd1b-505">Administrators of domains that are not Office 365 customers</span></span>

<span data-ttu-id="1cd1b-506">如果您是網域系統管理員，但不是 Office 365 客戶：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-506">If you are a domain administrator but are not an Office 365 customer:</span></span>
  
- <span data-ttu-id="1cd1b-p169">您應該將發佈您的網域傳送的 IP 位址設定 SPF and 也 set up DKIM （如果有的話） 來數位簽署的郵件。您也可能會考慮 DMARC 記錄設定。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p169">You should set up SPF to publish your domain's sending IP addresses, and also set up DKIM (if available) to digitally sign messages. You may also consider setting up DMARC records.</span></span>
    
- <span data-ttu-id="1cd1b-509">如果您有大量寄件者傳輸代替您撥打電話的電子郵件，您應該進行處理的方式傳送電子郵件如此來源中的傳送端網域： 地址 （如果它是屬於您） 配合通過 SPF 或 DMARC 的網域。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-509">If you have bulk senders who are transmitting email on your behalf, you should work with them to send email in a way such that the sending domain in the From: address (if it belongs to you) aligns with the domain that passes SPF or DMARC.</span></span>
    
- <span data-ttu-id="1cd1b-510">如果您有內部部署郵件伺服器，或傳送軟體為-a-服務提供者或從雲端主控像 Microsoft Azure、 機構 GoDaddy、 Rackspace、 Amazon Web 服務、 服務或類似，您應該確認他們會新增至 SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-510">If you have on-premise mail servers, or send from a Software-as-a-service provider, or from a cloud-hosting service like Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services, or similar, you should ensure that they are added to your SPF record.</span></span>
    
- <span data-ttu-id="1cd1b-p170">如果您是主控的 ISP 小型網域，您應設定的指示 SPF 記錄您的 ISP 所提供給您。大部分 Isp 提供這些類型的指示並收錄公司支援頁面上。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p170">If you are a small domain that is hosted by an ISP, you should set up your SPF record according to the instructions that is provided to you by your ISP. Most ISPs provide these types of instructions and can be found on the company's support pages.</span></span>
    
- <span data-ttu-id="1cd1b-p171">即使尚未發佈前，電子郵件驗證記錄和它的可正常運作，您仍必須發佈電子郵件驗證記錄傳送給 Microsoft。如此一來，您在網路釣魚、 對抗協助，降低，或組織傳送至，將會取得 phished 其中。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p171">Even if you have not had to publish email authentication records before, and it worked fine, you must still publish email authentication records to send to Microsoft. By doing so, you are helping in the fight against phishing, and reducing the possibility that either you, or organizations you send to, will get phished.</span></span>
    
### <a name="what-if-you-dont-know-who-sends-email-as-your-domain"></a><span data-ttu-id="1cd1b-515">如果您不知道誰以您網域傳送電子郵件？</span><span class="sxs-lookup"><span data-stu-id="1cd1b-515">What if you don't know who sends email as your domain?</span></span>

<span data-ttu-id="1cd1b-p172">因為它們不知道其所有寄件者屬於許多網域請勿發佈 SPF 記錄。這是外觀是否可以、 您不必知道誰成效。但是，您應該開始發佈過您不要知道的特別是貴公司的流量所在，並發佈中性 SPF 原則的 SPF 記錄吗？ 所有：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p172">Many domains do not publish SPF records because they do not know who all their senders are. That's okay, you do not need to know who all of them are. Instead, you should get started by publishing an SPF record for the ones you do know of, especially where your corporate traffic is located, and publish a neutral SPF policy, ?all:</span></span>
  
<span data-ttu-id="1cd1b-519">example.com IN TXT"v = spf1 include:spf.example.com 吗？ 所有"</span><span class="sxs-lookup"><span data-stu-id="1cd1b-519">example.com IN TXT "v=spf1 include:spf.example.com ?all"</span></span>
  
<span data-ttu-id="1cd1b-p173">中性 SPF 原則表示任何而言不在您公司的基礎結構的電子郵件將傳送電子郵件驗證所有其他電子郵件接收器。來自您不知道相關的寄件者的電子郵件會改為使用 neutral、 幾乎相同所有發佈沒有 SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p173">The neutral SPF policy means that any email that comes out of your corporate infrastructure will pass email authentication at all other email receivers. Email that comes from senders you don't know about will fall back to neutral, which is almost the same as publishing no SPF record at all.</span></span>
  
<span data-ttu-id="1cd1b-p174">傳送至 Office 365、 時將會是來自您公司的流量的電子郵件標示成驗證，但來自的來源您不知道相關的電子郵件仍會標示為身分詐騙 （取決於 Office 365 可以隱含驗證它）。但是，這是仍要標示為詐騙 Office 365 的所有電子郵件從改進。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p174">When sending to Office 365, email that comes from your corporate traffic will be marked as authenticated, but the email that comes from sources you don't know about may still be marked as spoof (depending upon whether or not Office 365 can implicitly authenticate it). However, this is still an improvement from all email being marked as spoof by Office 365.</span></span>
  
<span data-ttu-id="1cd1b-524">一旦您是否已得到入門後援原則 SPF 記錄吗？ 所有，您可以逐步包含更傳送基礎結構，然後發佈較嚴密的原則。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-524">Once you've gotten started with an SPF record with a fallback policy of ?all, you can gradually include more and more sending infrastructure and then publish a stricter policy.</span></span> 
  
### <a name="what-if-you-are-the-owner-of-a-mailing-list"></a><span data-ttu-id="1cd1b-525">如果您是郵寄清單的擁有者吗？</span><span class="sxs-lookup"><span data-stu-id="1cd1b-525">What if you are the owner of a mailing list?</span></span>

<span data-ttu-id="1cd1b-526">請參閱[常見案例 #2-討論列出](#common-scenario-2---discussion-lists)一節。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-526">See the section [Common scenario #2 - Discussion lists](#common-scenario-2---discussion-lists).</span></span> 
  
### <a name="what-if-you-are-an-infrastructure-provider-such-as-an-internet-service-provider-isp-email-service-provider-esp-or-cloud-hosting-service"></a><span data-ttu-id="1cd1b-527">如果您是例如網際網路服務提供者 (ISP)、 電子郵件服務提供者 (ESP) 或雲端裝載服務基礎結構提供者吗？</span><span class="sxs-lookup"><span data-stu-id="1cd1b-527">What if you are an infrastructure provider such as an Internet Service Provider (ISP), Email Service Provider (ESP), or cloud hosting service?</span></span>

<span data-ttu-id="1cd1b-528">如果主機網域的電子郵件和其傳送電子郵件，或提供託管可以傳送電子郵件的基礎結構，您應該執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="1cd1b-528">If you host a domain's email, and it sends email, or provide hosting infrastructure that can send email, you should do the following:</span></span>
  
- <span data-ttu-id="1cd1b-529">確定您的客戶有細部要在其 SPF 記錄中發佈的文件</span><span class="sxs-lookup"><span data-stu-id="1cd1b-529">Ensure your customers have documentation detailing what to publish in their SPF records</span></span>
    
- <span data-ttu-id="1cd1b-p175">請考慮 DKIM 簽章簽署外寄電子郵件上，即使客戶不會明確地設定它 （符號與預設網域）。您可以偶數雙登使用 DKIM （一次使用他們有設定它，如果在客戶的網域和第二個時間與您的公司 DKIM 簽章） 的簽章的電子郵件</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p175">Consider signing DKIM-signatures on outbound email even if the customer doesn't explicitly set it up (sign with a default domain). You can even double-sign the email with DKIM signatures (once with the customer's domain if they have set it up, and a second time with your company's DKIM signature)</span></span>
    
<span data-ttu-id="1cd1b-p176">向 Microsoft 既不保證即使您驗證電子郵件來自您的平台，但至少它可確保 Microsoft 不會不垃圾電子郵件因為未通過驗證。如需周圍 Outlook.com 如何篩選電子郵件的詳細資訊，請參閱[Outlook.com 郵件管理員] 頁面](https://postmaster.live.com/pm/postmaster.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p176">Deliverability to Microsoft is not guaranteed even if you authenticate email originating from your platform, but at least it ensures that Microsoft does not junk your email because it is not authenticated. For more details around how Outlook.com filters email, see the [Outlook.com Postmaster page](https://postmaster.live.com/pm/postmaster.aspx).</span></span>
  
<span data-ttu-id="1cd1b-534">如需服務提供者的最佳作法的詳細資訊，請參閱[M3AAWG 行動訊息的最佳作法服務提供者](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf)。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-534">For more details on service providers best practices, see [M3AAWG Mobile Messaging Best Practices for Service Providers](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf).</span></span>
  
## <a name="frequently-asked-questions"></a><span data-ttu-id="1cd1b-535">常見問題集</span><span class="sxs-lookup"><span data-stu-id="1cd1b-535">Frequently Asked Questions</span></span>

### <a name="why-is-microsoft-making-this-change"></a><span data-ttu-id="1cd1b-536">Microsoft 進行這項變更的為何？</span><span class="sxs-lookup"><span data-stu-id="1cd1b-536">Why is Microsoft making this change?</span></span>

<span data-ttu-id="1cd1b-537">由於網路釣魚的影響攻擊，與電子郵件驗證已繞 15 年，因為 Microsoft 相信的風險繼續允許未經驗證的電子郵件是高於遺失合法電子郵件的風險。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-537">Because of the impact of phishing attacks, and because email authentication has been around for over 15 years, Microsoft believes that the risk of continue to allow unauthenticated email is higher than the risk of losing legitimate email.</span></span>
  
### <a name="will-this-change-cause-legitimate-email-to-be-marked-as-spam"></a><span data-ttu-id="1cd1b-538">此變更會導致合法電子郵件標示為垃圾郵件吗？</span><span class="sxs-lookup"><span data-stu-id="1cd1b-538">Will this change cause legitimate email to be marked as spam?</span></span>

<span data-ttu-id="1cd1b-p177">在第一筆、 會有一些標示為垃圾郵件的郵件。不過，一段時間的寄件者將會調整，以及然後誤標身分詐騙的訊息數量微乎其微大部分的電子郵件路徑。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p177">At first, there will be some messages that are marked as spam. However, over time, senders will adjust and then the amount of messages mislabeled as spoofed will be negligible for most email paths.</span></span>
  
<span data-ttu-id="1cd1b-p178">Microsoft 本身先採用這項功能再將其部署至其客戶的其餘部分的幾週。第一次中斷時，它會逐漸拒絕。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p178">Microsoft itself first adopted this feature several weeks before deploying it to the rest of its customers. While there was disruption at first, it gradually declined.</span></span>
  
### <a name="will-microsoft-bring-this-feature-to-outlookcom-and-non-advanced-threat-protection-customers-of-office-365"></a><span data-ttu-id="1cd1b-543">將 Microsoft 提到這項功能 Outlook.com 和非進階威脅保護的 Office 365 的客戶吗？</span><span class="sxs-lookup"><span data-stu-id="1cd1b-543">Will Microsoft bring this feature to Outlook.com and non-Advanced Threat Protection customers of Office 365?</span></span>

<span data-ttu-id="1cd1b-p179">Microsoft 的反詐騙技術最初已部署給其組織有的 Office 365 企業版 E5 訂閱或鎖購買其訂閱的 Office 365 進階威脅保護 (ATP) 附加元件。年 10 月、 2018年我們已擴充至組織的 Exchange Online Protection (EOP)，以及保護。未來，我們可能如 Outlook.com 釋出其。不過，如果我們執行動作時，可能不會套用等報告某些功能及自訂會覆寫。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p179">Microsoft's anti-spoofing technology was initially deployed to its organizations that had an Office 365 Enterprise E5 subscription or had purchased the Office 365 Advanced Threat Protection (ATP) add-on for their subscription. As of October, 2018 we've extended the protection to organizations that have Exchange Online Protection (EOP) as well. In the future, we may release it for Outlook.com. However, if we do, there may be some capabilities that are not applied such as reporting and custom overrides.</span></span>
  
### <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a><span data-ttu-id="1cd1b-548">我如何可以回報垃圾郵件或非垃圾郵件訊息給 Microsoft？</span><span class="sxs-lookup"><span data-stu-id="1cd1b-548">How can I report spam or non-spam messages back to Microsoft?</span></span>

<span data-ttu-id="1cd1b-549">您可以使用[報表訊息增益集 outlook](https://support.office.com/article/use-the-report-message-add-in-b5caa9f1-cdf3-4443-af8c-ff724ea719d2)，如果未安裝或、[提交垃圾郵件、 非垃圾郵件和網路釣魚詐騙郵件訊息給 Microsoft 進行分析](https://technet.microsoft.com/en-us/library/jj200769%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-549">You can either use the [Report Message Add-in for Outlook](https://support.office.com/article/use-the-report-message-add-in-b5caa9f1-cdf3-4443-af8c-ff724ea719d2), or if it isn't installed, [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](https://technet.microsoft.com/en-us/library/jj200769%28v=exchg.150%29.aspx).</span></span>
  
### <a name="im-a-domain-administrator-who-doesnt-know-who-all-my-senders-are"></a><span data-ttu-id="1cd1b-550">我已經不知道所有 「 我的寄件者屬於網域管理員 ！</span><span class="sxs-lookup"><span data-stu-id="1cd1b-550">I'm a domain administrator who doesn't know who all my senders are!</span></span>

<span data-ttu-id="1cd1b-551">請參閱[之網域的是不是 Office 365 客戶的系統管理員](#administrators-of-domains-that-are-not-office-365-customers)。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-551">Please see [Administrators of domains that are not Office 365 customers](#administrators-of-domains-that-are-not-office-365-customers).</span></span>
  
### <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization-even-though-office-365-is-my-primary-filter"></a><span data-ttu-id="1cd1b-552">如果發生什麼事我停用 「 我的組織，反詐騙保護即使 Office 365 是主要的篩選條件？</span><span class="sxs-lookup"><span data-stu-id="1cd1b-552">What happens if I disable anti-spoofing protection for my organization, even though Office 365 is my primary filter?</span></span>

<span data-ttu-id="1cd1b-p180">不建議這因為您將會公開給其他未接的網路釣魚和垃圾郵件。並非所有網路釣魚詐騙，並不是所有詐騙將未都接。不過，您的風險會高於啟用反詐騙的客戶。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p180">We do not recommend this because you will be exposed to more missed phishing and spam messages. Not all phishing is spoofing, and not all spoofs will be missed. However, your risk will be higher than a customer who enables anti-spoofing.</span></span>
  
### <a name="does-enabling-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a><span data-ttu-id="1cd1b-556">啟用反詐騙保護意義我將會從所有網路釣魚保護吗？</span><span class="sxs-lookup"><span data-stu-id="1cd1b-556">Does enabling anti-spoofing protection mean I will be protected from all phishing?</span></span>

<span data-ttu-id="1cd1b-p181">不過，否，因為網路釣客將能否例如使用其他技術危害帳戶或設定可用服務的帳戶。不過，反網路釣魚保護偵測這些其他類型的網路釣魚方法因為 Office 365 保護層級會一起設計工時及建置彼此運作更好。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p181">Unfortunately, no, because phishers will adapt to use other techniques such as compromised accounts, or setting up accounts of free services. However, anti-phishing protection works much better to detect these other types of phishing methods because Office 365's protection layers are designed work together and build on top of each other.</span></span>
  
### <a name="do-other-large-email-receivers-block-unauthenticated-email"></a><span data-ttu-id="1cd1b-559">其他大量電子郵件接收器封鎖未經過驗證的電子郵件吗？</span><span class="sxs-lookup"><span data-stu-id="1cd1b-559">Do other large email receivers block unauthenticated email?</span></span>

<span data-ttu-id="1cd1b-p182">幾乎所有的大量電子郵件接收器實作傳統 SPF、 DKIM，以及 DMARC。某些接收器有其他檢查比只是這些標準，但較少移時若要封鎖的 Office 365 未經驗證的更嚴格的電子郵件和視為詐騙。不過，大部分的業界變得更嚴格有關此特定類型的電子郵件、 特別是因為網路釣魚問題。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p182">Nearly all large email receivers implement traditional SPF, DKIM, and DMARC. Some receivers have other checks that are more strict than just those standards, but few go as far as Office 365 to block unauthenticated email and treat them as a spoof. However, most of the industry is becoming more and more strict about this particular type of email, particularly because of the problem of phishing.</span></span>
  
### <a name="do-i-still-need-the-advanced-spam-filtering-option-enabled-for-spf-hard-fail-if-i-enable-anti-spoofing"></a><span data-ttu-id="1cd1b-563">仍然需要啟用"SPF 硬失敗"如果啟用反詐騙的進階垃圾郵件篩選選項吗？</span><span class="sxs-lookup"><span data-stu-id="1cd1b-563">Do I still need the Advanced Spam Filtering option enabled for "SPF Hard Fail" if I enable anti-spoofing?</span></span>

<span data-ttu-id="1cd1b-p183">否，此選項不再需要因為 SPF 硬失敗，但是更廣泛組準則的不只會考慮反詐騙功能。如果您有反詐騙啟用並已啟用 [SPF 硬失敗] 選項，您將可能取得更多的誤判。建議您停用此功能，它會為垃圾郵件或 phish，不提供幾乎任何其他 catch 並而產生多半誤判。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p183">No, this option is no longer required because the anti-spoofing feature not only considers SPF hard fails, but a much wider set of criteria. If you have anti-spoofing enabled and the SPF Hard Fail option enabled, you will probably get more false positives. We recommend disabling this feature as it would provide almost no additional catch for spam or phish, and instead generate mostly false positives.</span></span>
  
### <a name="does-sender-rewriting-scheme-srs-help-fix-forwarded-email"></a><span data-ttu-id="1cd1b-567">沒有協助修正轉寄電子郵件寄件者修正配置 (SRS) 吗？</span><span class="sxs-lookup"><span data-stu-id="1cd1b-567">Does Sender Rewriting Scheme (SRS) help fix forwarded email?</span></span>

<span data-ttu-id="1cd1b-p184">SRS 只部分修正此問題的轉寄電子郵件。由修正 SMTP MAIL FROM，SRS 可以確保在下一個目的地在轉寄的郵件通過 SPF。不過，因為反詐騙根據 From： 地址與 MAIL FROM 或 DKIM 簽署網域 （或其他信號） 組合，它不是足夠，防止轉寄電子郵件被標示成詐騙。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-p184">SRS only partially fixes the problem of forwarded email. By rewriting the SMTP MAIL FROM, SRS can ensure that the forwarded message passes SPF at the next destination. However, because anti-spoofing is based upon the From: address in combination with either the MAIL FROM or DKIM-signing domain (or other signals), it is not enough to prevent forwarded email from being marked as spoofed.</span></span>
  

