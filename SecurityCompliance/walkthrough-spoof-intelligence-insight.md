---
title: 逐步解說詐騙智慧洞察力
ms.author: krowley
author: kccross
ms.date: 7/30/2018
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
description: 請參閱新詐騙智慧洞察力的運作方式。
ms.openlocfilehash: 83fa1580a0e7c4717581cc5f23b8f525d6b918e0
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220323"
---
# <a name="walkthrough-spoof-intelligence-insight"></a><span data-ttu-id="076b0-103">逐步解說： 詐騙智慧洞察力</span><span class="sxs-lookup"><span data-stu-id="076b0-103">Walkthrough: spoof intelligence insight</span></span>

<span data-ttu-id="076b0-p101">藉由使用詐騙智慧洞察力，您可以快速地決定哪些寄件者的合法傳送未經驗證電子郵件。藉由 documents 它們傳送詐騙的郵件，您可以減少任何誤判移至您的使用者的風險。</span><span class="sxs-lookup"><span data-stu-id="076b0-p101">By using the Spoof Intelligence insight, you can quickly determine which senders are legitimately sending you unauthenticated email. By permitting them to send spoofed messages, you can reduce the risk of any false positives going to your users.</span></span>
  
<span data-ttu-id="076b0-106">此外，您也可以使用詐騙智慧監視及管理提供多一層的安全性及防止不安全的郵件抵達您組織中的允許的網域配對。</span><span class="sxs-lookup"><span data-stu-id="076b0-106">In addition, you can also use Spoof Intelligence monitor and manage permitted domain-pairs to provide an additional layer of security and prevent unsafe messages from arriving in your organization.</span></span>
  
<span data-ttu-id="076b0-p102">您可以使用詐騙智慧洞察力安全性&amp;規範中心如果工作或學校帳戶具有已授與 Office 365 全域管理員、 安全性管理員或安全性讀取權限。如需詳細資訊，請參閱[Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="076b0-p102">You can use the spoof intelligence insight in the Security &amp; Compliance Center if your work or school account has been given Office 365 global administrator, security administrator, or security reader permissions. For more information, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="076b0-109">如果您是新[報告與 Office 365 安全性前瞻&amp;規範中心](reports-and-insights-in-security-and-compliance.md)，它可能會說明若要查看如何您可以輕鬆地瀏覽儀表板至洞察力及建議的動作。</span><span class="sxs-lookup"><span data-stu-id="076b0-109">If you're new to [reports and insights in the Office 365 Security &amp; Compliance Center](reports-and-insights-in-security-and-compliance.md), it might help to see how you can easily navigate from a dashboard to an insight and recommended actions.</span></span>
  
<span data-ttu-id="076b0-p103">您可以檢視多個儀表板詐騙智慧洞察力安全性&amp;規範中心。不論您正在查看哪些儀表板、 洞察力提供相同的詳細資訊與可讓您快速地執行的相同工作。</span><span class="sxs-lookup"><span data-stu-id="076b0-p103">You can view the spoof intelligence insight from more than one dashboard in the Security &amp; Compliance Center. Regardless of which dashboard you're looking at, the insight provides the same details and allows you to quickly perform the same tasks.</span></span>
  
<span data-ttu-id="076b0-p104">這是一個安全性的數個逐步解說&amp;規範中心。若要瀏覽提供及報告，請參閱 [相關的主題] 區段中的逐步解說。</span><span class="sxs-lookup"><span data-stu-id="076b0-p104">This is one of several walkthroughs for the Security &amp; Compliance Center. To about navigating reports and insights, see the walkthroughs in the Related topics section.</span></span>
  
## <a name="getting-to-the-spoof-intelligence-insight-in-the-security-amp-compliance-center"></a><span data-ttu-id="076b0-114">易於存取安全性詐騙智慧洞察力&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="076b0-114">Getting to the spoof intelligence insight in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="076b0-115">若要開始，您將需要[移至 [安全性&amp;規範中心](go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="076b0-115">To get started, you'll need [go to the Security &amp; Compliance Center](go-to-the-securitycompliance-center.md).</span></span>
    
2. <span data-ttu-id="076b0-116">安全性&amp;規範管理中心，移至**Threat Management** \> **儀表板。**</span><span class="sxs-lookup"><span data-stu-id="076b0-116">In the Security &amp; Compliance Center, go to **Threat Management** \> **Dashboard.**</span></span>
    
3. <span data-ttu-id="076b0-p105">在 [**前瞻**] 列中，尋找詐騙智慧洞察力。如果您已啟用詐騙智慧則洞察力即資格**Spoofed 網域的失敗的過去 30 天的驗證**。如果尚未啟用詐騙保護，然後據會提示您可以使用標題**啟用詐騙保護**來進行。</span><span class="sxs-lookup"><span data-stu-id="076b0-p105">In the **Insights** row, look for the spoof intelligence insight. If you have enabled spoof intelligence, then the insight is entitled **Spoofed domains that failed authentication of the past 30 days**. If you haven't enabled spoof protection, then the insight will prompt you to do so by using the title **Enable Spoof Protection**.</span></span> 
    
## <a name="about-the-insight-on-the-dashboard"></a><span data-ttu-id="076b0-120">關於儀表板上洞察力</span><span class="sxs-lookup"><span data-stu-id="076b0-120">About the insight on the dashboard</span></span>

<span data-ttu-id="076b0-121">在儀表板上的洞察力會顯示類似的資訊。</span><span class="sxs-lookup"><span data-stu-id="076b0-121">The insight on the dashboard shows you information like this.</span></span>
  
![詐騙智慧洞察力的螢幕擷取畫面](media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)
  
<span data-ttu-id="076b0-123">此洞察力有兩種模式：</span><span class="sxs-lookup"><span data-stu-id="076b0-123">This insight has two modes:</span></span>
  
 <span data-ttu-id="076b0-p106">**洞察力模式**。如果您有啟用任何詐騙原則，然後據顯示我們詐騙智慧功能所影響多少信箱過去 30 天。</span><span class="sxs-lookup"><span data-stu-id="076b0-p106">**Insight mode**. If you have any spoof policy enabled, then the insight shows you how many mails were impacted by our spoof intelligence capabilities over the past 30 days.</span></span> 
  
 <span data-ttu-id="076b0-p107">**怎麼辦模式**。如果您沒有任何已啟用的詐騙原則，然後據顯示多少信箱*會*有已受到我們詐騙智慧功能過去 30 天。</span><span class="sxs-lookup"><span data-stu-id="076b0-p107">**What if mode**. If you do not have any spoof policy enabled, then the insight shows you how many mails  *would*  have been impacted by our spoof intelligence capabilities over the past 30 days.</span></span> 
  
<span data-ttu-id="076b0-p108">無論如何，顯示在洞察力詐騙的網域分成兩個類別 ；可疑網域配對和非可疑網域組。這些類別會進一步細分為三個不同的 bucket 您檢閱。</span><span class="sxs-lookup"><span data-stu-id="076b0-p108">Either way, the spoofed domains displayed in the insight are separated into two categories; suspicious domain pairs and non-suspicious domain pairs. These categories are further subdivided into three different buckets for you to review.</span></span> 
  
<span data-ttu-id="076b0-130">*網域配對*是組合"從:"地址及傳送基礎結構。</span><span class="sxs-lookup"><span data-stu-id="076b0-130">A  *domain pair*  is a combination of the "From:" address and the sending infrastructure.</span></span> 
  
- <span data-ttu-id="076b0-p109">"From"地址是由您的郵件應用程式顯示 From 地址的地址。這個位址會識別作者的電子郵件。也就是人員或系統負責撰寫郵件的信箱。這有時稱為 5322.From 地址。</span><span class="sxs-lookup"><span data-stu-id="076b0-p109">The "From" address is the address displayed as the From address by your mail application. This address identifies the author of the email. That is, the mailbox of the person or system responsible for writing the message. This is sometimes called the 5322.From address.</span></span>
    
- <span data-ttu-id="076b0-p110">傳送基礎結構、 或寄件者為組織網域的傳送端 IP 位址的 PTR 記錄。如果傳送的 IP 位址已無的 PTR 記錄，則寄件者與 255.255.255.0 識別所傳送的 IP 子網路遮罩中 CIDR 註解 （/ 24）。例如，如果的 IP 位址為 192.168.100.100 寄件者的完整 IP 位址則 192.168.100.100/24。</span><span class="sxs-lookup"><span data-stu-id="076b0-p110">The sending infrastructure, or sender, is the organizational domain of the PTR record of the sending IP address. If the sending IP address has no PTR record, then the sender is identified by the sending IP with the 255.255.255.0 subnet mask in CIDR notation (/24). For example, if the IP address is 192.168.100.100 then the complete IP address of the sender is 192.168.100.100/24.</span></span>
    
 <span data-ttu-id="076b0-138">**可疑網域配對**包括：</span><span class="sxs-lookup"><span data-stu-id="076b0-138">**Suspicious domain pairs** include:</span></span> 
  
- <span data-ttu-id="076b0-p111">**高信賴詐騙**。Office 365 接收強式信號這些網域所可疑，根據歷程記錄傳送模式和網域信譽分數。Office 365 是高度有信心網域詐騙及這些網域傳送的訊息是較不可能是合法。</span><span class="sxs-lookup"><span data-stu-id="076b0-p111">**High-confidence spoof**. Office 365 received strong signals that these domains are suspicious, based on the historical sending patterns and the reputation score of the domains. Office 365 is highly confident that the domains are spoofing and that messages sent from these domains are less likely to be legitimate.</span></span> 
    
- <span data-ttu-id="076b0-p112">**中等信賴詐騙**。Office 365 接收中等信號這些網域所可疑，根據歷程記錄傳送模式和網域信譽分數。Office 365 是溫和有信心網域詐騙及這些網域傳送的訊息是合法。此 bucket 有更大的包含誤判 (FPs) 較高信賴詐騙 bucket 機會。</span><span class="sxs-lookup"><span data-stu-id="076b0-p112">**Moderate confidence spoof**. Office 365 received moderate signals that these domains are suspicious, based on historical sending patterns and the reputation score of the domains. Office 365 is moderately confident that the domains are spoofing and that messages sent from these domains are legitimate. This bucket has a greater chance of containing false positives (FPs) than the high-confidence spoof bucket.</span></span> 
    
 <span data-ttu-id="076b0-p113">**非可疑網域配對**包括**人詐騙**。救回的詐騙都無法明確驗證檢查 ( [SPF](https://docs.microsoft.com/office365/SecurityCompliance/how-office-365-uses-spf-to-prevent-spoofing)、 [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)、 [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)) 但傳遞我們延伸的驗證檢查的網域。因為這、 Office 365 人代替您撥打電話郵件和反詐騙採取任何動作已的郵件。</span><span class="sxs-lookup"><span data-stu-id="076b0-p113">**Non-suspicious domain pairs** include **rescued spoof**. Rescued spoof are domains that have failed the explicit authentication checks ( [SPF](https://docs.microsoft.com/office365/SecurityCompliance/how-office-365-uses-spf-to-prevent-spoofing), [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email), [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)) but passed our extended authentication checks. As a result of this, Office 365 rescued the mail on your behalf and no anti-spoofing action was taken on the mail.</span></span> 
  
## <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a><span data-ttu-id="076b0-149">檢視來自詐騙智慧洞察力可疑網域成對的詳細的資訊</span><span class="sxs-lookup"><span data-stu-id="076b0-149">View detailed information about suspicious domain pairs from the spoof intelligence insight</span></span>

1. <span data-ttu-id="076b0-150">在詐騙智慧洞察力中，按一下 [任何網域配對 （高、 中級或救回）。</span><span class="sxs-lookup"><span data-stu-id="076b0-150">On the spoof intelligence insight, click any of the domain pairs (high, moderate, or rescued).</span></span>
  
<span data-ttu-id="076b0-p114">**詐騙智慧洞察力**] 頁面上會出現顯示的已傳送至您的組織未經過驗證的郵件的寄件者清單。在此頁面上的資訊可協助您判斷是否詐騙的郵件已獲得授權，或未或如果您需要進一步採取動作。您可以排序資訊的郵件計數上次偵測到詐騙、 日期及其他。（按一下欄標題，例如**訊息計數**或**上次呈現**，例如）。</span><span class="sxs-lookup"><span data-stu-id="076b0-p114">The **Spoof Intelligence Insight** page appears showing you a list of senders that are sending unauthenticated mail into your organization. The information on this page helps you determine whether spoofed messages are authorized or not or if you need to take further action. You can sort the information by message count, the date the spoof was last detected, and more. (Click column headings, such as **Message count** or **Last seen**, for example.)</span></span> 
    
2. <span data-ttu-id="076b0-p115">若要開啟 [詳細資料] 窗格包含網域一組豐富的資訊表格中選取項目，包括為什麼我們攔截這，您需要做些什麼，網域摘要、 WhoIs 資料相關的寄件者和類似我們討論過在您的租用戶從相同的寄件者的電子郵件。從這裡，您也可以選擇新增或移除**AllowedToSpoof**安全寄件者清單中的網域組的名稱。</span><span class="sxs-lookup"><span data-stu-id="076b0-p115">Select an item in the table to open a details pane that contains rich information about the domain pair, including why we caught this, what you need to do, a domain summary, WhoIs data about the sender, and similar emails we have seen in your tenant from the same sender. From here, you can also choose to add or remove the domain pair from the **AllowedToSpoof** safe sender list.</span></span> 
  
![詐騙智慧洞察力詳細資料窗格中的網域的螢幕擷取畫面](media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)
  
## <a name="add-or-remove-a-domain-from-the-allowedtospoof-safe-sender-list"></a><span data-ttu-id="076b0-158">新增或移除 AllowedToSpoof 安全寄件者清單中的網域</span><span class="sxs-lookup"><span data-stu-id="076b0-158">Add or remove a domain from the AllowedToSpoof safe sender list</span></span>

<span data-ttu-id="076b0-p116">您新增或移除 AllowedToSpoof 安全寄件者清單中的網域，時檢閱詐騙智慧洞察力網域組詳細資料窗格中。只是據此設定切換。</span><span class="sxs-lookup"><span data-stu-id="076b0-p116">You add or remove a domain from the AllowedToSpoof safe sender list while reviewing the domain pair in the details pane of the spoof intelligence insight. Simply set the toggle accordingly.</span></span>
  
<span data-ttu-id="076b0-p117">這會修改詐騙的網域和傳送基礎結構的唯一的網域配對組合，而不提供涵蓋範圍的整個詐騙的網域] 或 [隔離傳送基礎結構。例如，如果 'AllowedToSpoof' 寄件者新增下列網域對允許清單：*詐騙網域*"gmail.com"和*傳送基礎結構*"tms *。 mx.com"，* 則只能從該網域配對的郵件仍可詐騙。其他的寄件者嘗試詐騙"gmail.com"和"tms.mx.com"嘗試詐騙會繼續詐騙智慧會受到其他網域。</span><span class="sxs-lookup"><span data-stu-id="076b0-p117">This modifies the unique domain pair combination of the spoofed domain and the sending infrastructure and does not provide coverage for the entire spoofed domain or the sending infrastructure in isolation. For example, if you add the following domain pair to the 'AllowedToSpoof' sender allow list:  *Spoofed Domain*  "gmail.com" and  *Sending Infrastructure*  "tms  *.mx.com",*  then only mail from that domain pair will be allowed to spoof. Other senders attempting to spoof "gmail.com", and other domains that "tms.mx.com" attempt to spoof will continue to be protected by spoof intelligence.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="076b0-164">相關主題</span><span class="sxs-lookup"><span data-stu-id="076b0-164">Related topics</span></span>

[<span data-ttu-id="076b0-165">深入了解詐騙情報</span><span class="sxs-lookup"><span data-stu-id="076b0-165">Learn more about spoof intelligence</span></span>](learn-about-spoof-intelligence.md)
  
[<span data-ttu-id="076b0-166">Office 365 的反詐騙保護</span><span class="sxs-lookup"><span data-stu-id="076b0-166">Anti-spoofing protection in Office 365</span></span>](anti-spoofing-protection.md)
  
[<span data-ttu-id="076b0-167">逐步解說 - 從儀表板到深入解析</span><span class="sxs-lookup"><span data-stu-id="076b0-167">Walkthrough - From a dashboard to an insight</span></span>](from-a-dashboard-to-an-insight.md)
  
[<span data-ttu-id="076b0-168">逐步解說 - 從詳細報告到深入解析</span><span class="sxs-lookup"><span data-stu-id="076b0-168">Walkthrough - From a detailed report to an insight</span></span>](from-a-detailed-report-to-an-insight.md)
  
[<span data-ttu-id="076b0-169">逐步解說 - 從深入解析到詳細報告</span><span class="sxs-lookup"><span data-stu-id="076b0-169">Walkthrough - From an insight to a detailed report</span></span>](from-an-insight-to-a-detailed-report.md)
  

