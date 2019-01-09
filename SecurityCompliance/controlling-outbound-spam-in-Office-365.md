---
title: 控制 Office 365 的輸出垃圾郵件
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 09/18/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
description: 如果您的組織傳送大量大宗郵件標記為垃圾郵件，您無法取得封鎖，禁止傳送電子郵件與 Office 365。請閱讀本篇文章以深入了解發生的原因以及可以怎麼有關它。
ms.openlocfilehash: 2d198bc1b61da429f45f0d1f54c63876d59d890f
ms.sourcegitcommit: 03e64ead7805f3dfa9149252be8606efe50375df
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2019
ms.locfileid: "27769807"
---
# <a name="controlling-outbound-spam-in-office-365"></a><span data-ttu-id="924e0-104">控制 Office 365 的輸出垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="924e0-104">Controlling outbound spam in Office 365</span></span>

<span data-ttu-id="924e0-p102">我們採用嚴重因為我們的共用的服務管理輸出垃圾郵件。 有許多客戶背後的其中一個客戶傳送輸出垃圾郵件，如果它可能會降低服務的輸出 IP 信譽及影響其他客戶的電子郵件成功既的資源共用集區。它則公平至客戶的客戶 B spams 和各種 3rd 方 IP blocklists 清單它會使用的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="924e0-p102">We take managing outbound spam seriously because ours is a shared service.  There are many customers behind a shared pool of resources, where if one customer sends outbound spam, it can degrade the outbound IP reputation of the service and affects the successful deliverability of email for other customers. It is unfair to Customer A if Customer B spams and various 3rd party IP blocklists list the IP address that it uses.</span></span>

## <a name="what-admins-can-do-to-control-outbound-spam"></a><span data-ttu-id="924e0-108">系統管理員可以執行控制輸出垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="924e0-108">What admins can do to control outbound spam</span></span>

- <span data-ttu-id="924e0-p103">**啟用帳戶傳送垃圾郵件或關閉時的通知**。系統管理員可以取得之密件副本接收者每當郵件已標示為 「 輸出垃圾郵件和傳送到高風險集區。藉由監視這個信箱，系統管理員可以偵測如果其網路中有洩漏的帳戶或垃圾郵件篩選已遭標示為垃圾郵件的電子郵件。 在設定輸出垃圾郵件原則的詳細資訊可以找到[以下](configure-the-outbound-spam-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="924e0-p103">**Enable notifications when an account is sending spam or shut down**. Administrators can get bcc’ed whenever a message is marked as outbound spam and sent through the High Risk pool. By monitoring this mailbox, an admin can detect if they have a compromised account in their network or if the spam filter is mistakenly marking their email as spam.  More information on setting up the outbound spam policy can be found [here](configure-the-outbound-spam-policy.md).</span></span>
 
- <span data-ttu-id="924e0-p104">**手動檢閱 [垃圾郵件客訴來自 3rd 方電子郵件提供者**。如 Outlook.com、 Yahoo 和 AOL 許多 3rd 方電子郵件服務提供意見反應迴圈其中其服務中的任何使用者會標示為垃圾郵件我們服務的電子郵件，如果郵件是封裝而對我們傳送以供檢閱。若要深入了解 Outlook.com 的寄件者支援，請按一下[這裡](https://sendersupport.olc.protection.outlook.com/pm/services.aspx)。</span><span class="sxs-lookup"><span data-stu-id="924e0-p104">**Manually review spam complaints from 3rd party email providers**. Many 3rd party email services like Outlook.com, Yahoo and AOL provide a Feedback Loop where if any user in their service marks an email from our service as spam, the message is packaged up and sent back to us for review. To learn more about sender support for Outlook.com, click [here](https://sendersupport.olc.protection.outlook.com/pm/services.aspx).</span></span>

## <a name="what-eop-does-to-control-outbound-spam"></a><span data-ttu-id="924e0-116">EOP 沒有控制輸出垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="924e0-116">What EOP does to control outbound spam</span></span> 

1. <span data-ttu-id="924e0-p105">**將 Ip 的個別集區的輸出流量的區隔**。客戶傳送輸出透過服務每封郵件會掃描的垃圾郵件。如果郵件為垃圾郵件，它會路由傳送到高風險傳遞集區。此 IP 集區會包含非可傳送作業的狀態通知和垃圾郵件。傳遞至預定的收件者不保證為許多第三方將不會接受電子郵件因為它會發出的電子郵件的品質。</span><span class="sxs-lookup"><span data-stu-id="924e0-p105">**Segregation of outbound traffic into separate pools of IPs**. Every message that customers send outbound through the service is scanned for spam. If the message is spam, it is routed through the High Risk Delivery pool. This IP pool contains non-deliverable status notifications and spam. Delivery to the intended recipient is not guaranteed as many third parties will not accept email because the quality of email it emits.</span></span><br/><br/><span data-ttu-id="924e0-p106">分割流量這種方式可確保較低品質電子郵件 （垃圾郵件、 非法回應 Ndr） 不會不拖曳下信譽之規則的外寄電子郵件集區。雖然這不是通用高風險集區通常是在網際網路周圍的許多接收器具有低信譽。</span><span class="sxs-lookup"><span data-stu-id="924e0-p106">Splitting the traffic this way ensures that the lower quality email (spam, backscatter NDRs) does not drag down the reputation of the regular outbound email pools. The high risk pool typically has low reputation at many receivers around the Internet, although this is not universal.</span></span> 

2. <span data-ttu-id="924e0-p107">**監控的 IP 信譽**。Office 365 查詢各種 3rd 方 IP blocklists 並如果我們輸出 Ip 的任何已列在這些通知就會產生。這可讓我們時垃圾郵件具有造成來降低我們信譽快速回應。時就會產生警示，我們有內部文件外圍取得 delisted 所採取的步驟。</span><span class="sxs-lookup"><span data-stu-id="924e0-p107">**Monitoring of IP reputation**. Office 365 queries various 3rd party IP blocklists and generates alerts if any of our outbound IPs are listed on them. This allows us to react quickly when spam has caused our reputation to degrade. When an alert is generated, we have internal documentation outlying what steps to take to get delisted.</span></span> 

3. <span data-ttu-id="924e0-p108">**停用的違規帳戶傳送太多的電子郵件時已標記為垃圾郵件**。即使我們隔離我們垃圾郵件和非垃圾郵件至兩個不同輸出 IP 集區、 電子郵件帳戶不能無限期傳送垃圾郵件。我們監視哪些帳戶已傳送垃圾郵件與帳戶如果超過保密的限制，禁止傳送垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="924e0-p108">**Disabling of offending accounts when they send too much email marked as spam**. Even though we segregate our spam and non-spam into two separate outbound IP pools,  the email accounts cannot send spam indefinitely. We monitor which accounts are sending spam and if it exceeds an undisclosed limit, the account is blocked from sending spam.</span></span><br/><br/><span data-ttu-id="924e0-p109">單一郵件標記為垃圾郵件可能是垃圾郵件引擎，又稱為誤判 misclassification。我們傳送透過將其命名的移出; 機會高風險集區不過，大量的簡短時間圖文框中的訊息表示問題以及時，會發生，我們封鎖從傳送任何更多的電子郵件帳戶。有不同存在個別電子郵件帳戶，以及如彙總整個承租人所示的臨界值。</span><span class="sxs-lookup"><span data-stu-id="924e0-p109">A single message marked as spam may be a misclassification by the spam engine and also known as a false positive. We send it through the High Risk pool to give it a chance of going out; however, a large number of messages in a short time frame is indicative of a problem and when that occurs, we block the account from sending any more email. There are different thresholds that exist for individual email accounts as well as in aggregate for the entire tenant.</span></span>

4. <span data-ttu-id="924e0-p110">**停用的違規帳戶傳送太多太短時間圖文框中的電子郵件時**。除了上述的外觀比例標示為垃圾郵件的限制，也有封鎖帳戶達到不論將郵件標示為垃圾郵件整體限制時的限制。此限制存在的原因是因為洩漏的帳戶無法傳送垃圾郵件篩選器所未接的零時差垃圾郵件。因為很難，如果沒有之前，有時告知合法的大量郵寄行銷活動及大規模的垃圾郵件 campaign 之間的差異，這些限制會啟用限制任何潛在的傷害。</span><span class="sxs-lookup"><span data-stu-id="924e0-p110">**Disabling of offending accounts when they send too much email in too short a time frame**. In addition to the limits above that look for a proportion of messages marked as spam, there are also limits that block accounts when they reach an overall limit regardless of whether or not the messages are marked as spam. The reason this limit exists is because a compromised account could send zero-day spam that is missed by the spam filter. Because it is difficult, if not impossible, to sometimes tell the difference between a legitimate mass mailing campaign and a massive spam campaign, these limits activate to limit any potential damage.</span></span>

> [!NOTE]
> <span data-ttu-id="924e0-p111">#3 與 #4 我們未通告的確切限制。 這是以防止垃圾郵件傳送者從遊戲系統並確定我們可以時我們需要變更限制。限制是損害的不夠高如此平均商務使用者永遠不會瀏覽其和低它包含大部分的垃圾郵件的用途。</span><span class="sxs-lookup"><span data-stu-id="924e0-p111">For both #3 and #4, we do not advertise the exact limits.  This is to prevent spammers from gaming the system and to ensure that we can change the limits when we need to. The limits are high enough such that an average business user will never hit them and low enough that it contains most of the damage a spammer can do.</span></span> 

## <a name="recommended-workarounds-for-customers-who-want-to-send-outbound-a-lot-of-email-through-eop"></a><span data-ttu-id="924e0-141">對於要傳送輸出許多的電子郵件到 EOP 的客戶的建議解決方法</span><span class="sxs-lookup"><span data-stu-id="924e0-141">Recommended workarounds for customers who want to send outbound a lot of email through EOP</span></span>

<span data-ttu-id="924e0-p112">很難將客戶想要傳送大量電子郵件和比較防止入侵的帳戶和大量 emailers 與不良清單取得作法的服務之間的平衡。同樣地，輸出 IP 登陸 3rd 的廠商封鎖清單上的成本是高於封鎖客戶傳送輸出電子郵件。[Exchange Online 服務說明](https://technet.microsoft.com/library/exchange-online-limits.aspx#RecipientLimits)所述，使用 EOP 來傳送大量電子郵件不支援使用的服務與只允許"最佳投入比 」 為基礎。要傳送大量電子郵件的客戶，我們建議下列項目：</span><span class="sxs-lookup"><span data-stu-id="924e0-p112">It is difficult to strike a balance between customers who want to send a large volume of email vs. protecting the service from compromised accounts and bulk emailers with poor list acquisition practices. Again, the cost of an outbound IP landing on a 3rd party blocklist is higher than blocking a customer from sending outbound email. As described in the [Exchange Online Service Description](https://technet.microsoft.com/library/exchange-online-limits.aspx#RecipientLimits), using EOP to send bulk email is not a supported use of the service and is only permitted on a “best-effort” basis. For customers who do want to send bulk email, we recommend the following:</span></span>

1. <span data-ttu-id="924e0-p113">**傳送大量電子郵件到其本身的內部部署郵件伺服器**。這表示客戶必須維護自己電子郵件的基礎結構這種類型的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="924e0-p113">**Send the bulk email through its own on-premises mail servers**. This means that the customer will have to maintain its own email infrastructure for this type of email.</span></span>

2. <span data-ttu-id="924e0-p114">**使用第 3 協力廠商對大量 emailer 傳送大量的通訊**。有數個 3rd 廠商大量 emailers 要事業很傳送大量電子郵件。它們可搭配客戶確認他們具有良好電子作法擁有專用於強制執行它的資源。</span><span class="sxs-lookup"><span data-stu-id="924e0-p114">**Use a 3rd party bulk emailer to send the mass communication**. There are several 3rd party bulk emailers whose sole business it is to send bulk email. They can work with customers to ensure that they have good emailing practices and they have resources dedicated to enforcing it.</span></span> 

<span data-ttu-id="924e0-p115">通訊、 行動、 惡意程式碼反不當使用工作群組 (MAAWG) 發佈其成員資格名冊[此處](http://www.maawg.org/about/roster)。數個大量電子郵件提供者清單上與名為負責網際網路市民。</span><span class="sxs-lookup"><span data-stu-id="924e0-p115">The Messaging, Mobile, Malware Anti-Abuse Working Group (MAAWG) publishes its membership roster [here](http://www.maawg.org/about/roster). Several bulk email providers are on the list and are known to be responsible Internet citizens.</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="924e0-153">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="924e0-153">For more information</span></span>

[<span data-ttu-id="924e0-154">當封鎖寄件者時傳送輸出垃圾郵件的範例通知</span><span class="sxs-lookup"><span data-stu-id="924e0-154">Sample notification when a sender is blocked sending outbound spam</span></span>](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md)

[<span data-ttu-id="924e0-155">Office 365 電子郵件的反垃圾郵件保護</span><span class="sxs-lookup"><span data-stu-id="924e0-155">Office 365 email anti-spam protection</span></span>](anti-spam-protection.md)

[<span data-ttu-id="924e0-156">Office 365 的反詐騙保護</span><span class="sxs-lookup"><span data-stu-id="924e0-156">Anti-spoofing protection in Office 365</span></span>](anti-spoofing-protection.md)

[<span data-ttu-id="924e0-157">垃圾郵件信賴等級</span><span class="sxs-lookup"><span data-stu-id="924e0-157">Spam confidence levels</span></span>](spam-confidence-levels.md)
