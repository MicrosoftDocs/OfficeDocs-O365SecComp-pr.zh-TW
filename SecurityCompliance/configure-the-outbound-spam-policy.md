---
title: 設定輸出垃圾郵件原則
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 11/10/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
description: 如果您使用該服務來傳送輸出電子郵件，便會一律啟用輸出垃圾郵件篩選功能，從而保護使用該服務的組織及其預期的收件者。
ms.openlocfilehash: af48962879dd4ee1e5bbbe832f221e88900faa75
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/20/2019
ms.locfileid: "30692802"
---
# <a name="configure-the-outbound-spam-policy"></a><span data-ttu-id="66b81-103">設定輸出垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="66b81-103">Configure the outbound spam policy</span></span>

<span data-ttu-id="66b81-p101">如果您使用該服務來傳送輸出電子郵件，便會一律啟用輸出垃圾郵件篩選功能，從而保護使用該服務的組織及其預期的收件者。與輸入篩選類似，輸出垃圾郵件篩選也包括連線篩選和內容篩選，但是輸出篩選器設定不可設定。如果輸出郵件被判定為垃圾郵件，就會透過較高風險傳遞集區路由傳送，以降低正常輸出 IP 集區被加入封鎖清單的可能性。如果客戶繼續透過服務傳送輸出垃圾郵件，則會被封鎖而無法傳送郵件。雖然您無法停用或變更輸出垃圾郵件篩選，但您可透過預設的輸出垃圾郵件原則，設定數個全公司適用的輸出垃圾郵件設定。</span><span class="sxs-lookup"><span data-stu-id="66b81-p101">Outbound spam filtering is always enabled if you use the service for sending outbound email, thereby protecting organizations using the service and their intended recipients. Similar to inbound filtering, outbound spam filtering is comprised of connection filtering and content filtering, however the outbound filter settings are not configurable. If an outbound message is determined to be spam, it is routed through the higher risk delivery pool, which reduces the probability of the normal outbound-IP pool being added to a block list. If a customer continues to send outbound spam through the service, they will be blocked from sending messages. Although outbound spam filtering cannot be disabled or changed, you can configure several company-wide outbound spam settings via the default outbound spam policy.</span></span> 
  
<span data-ttu-id="66b81-109">下列影片顯示如何設定輸出垃圾郵件原則：</span><span class="sxs-lookup"><span data-stu-id="66b81-109">The following video shows how to configure the outbound spam policy:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/1f20d655-0d3d-4141-9cae-e57f5a6cffe8?autoplay=false]
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="66b81-110">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="66b81-110">What do you need to know before you begin?</span></span>
<span data-ttu-id="66b81-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="66b81-111"></span></span>

<span data-ttu-id="66b81-112">預估完成時間：5 分鐘</span><span class="sxs-lookup"><span data-stu-id="66b81-112">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="66b81-113">您必須已獲指派權限，才能執行此程序或這些程序。</span><span class="sxs-lookup"><span data-stu-id="66b81-113">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="66b81-114">若要查看您需要哪些權限，請參閱 「 反垃圾郵件中的項目[Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主題。</span><span class="sxs-lookup"><span data-stu-id="66b81-114">To see what permissions you need, see the "Anti-spam entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span> 
  
<span data-ttu-id="66b81-115">如需適用於此主題中程序的快速鍵相關資訊，請參閱 **Keyboard shortcuts in Exchange 2013**。</span><span class="sxs-lookup"><span data-stu-id="66b81-115">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
  
<span data-ttu-id="66b81-116">您也可以透過遠端 PowerShell 執行下列程序。</span><span class="sxs-lookup"><span data-stu-id="66b81-116">The following procedure can also be performed via remote PowerShell.</span></span> <span data-ttu-id="66b81-117">使用[Get-hostedoutboundspamfilterpolicy](http://technet.microsoft.com/library/8f15c83c-c10a-4d9d-b135-35321430bdc2.aspx) cmdlet 來檢閱您的設定，以及[Set-hostedoutboundspamfilterpolicy](http://technet.microsoft.com/library/665d1b04-d4b5-4a0e-811a-4e37096ccbfd.aspx)編輯您的輸出垃圾郵件原則設定。</span><span class="sxs-lookup"><span data-stu-id="66b81-117">Use the [Get-HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/8f15c83c-c10a-4d9d-b135-35321430bdc2.aspx) cmdlet to review your settings, and the [Set-HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/665d1b04-d4b5-4a0e-811a-4e37096ccbfd.aspx) to edit your outbound spam policy settings.</span></span> <span data-ttu-id="66b81-118">若要了解如何使用 Windows PowerShell 來連接至 Exchange Online Protection，請參閱[Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290)。</span><span class="sxs-lookup"><span data-stu-id="66b81-118">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290).</span></span> <span data-ttu-id="66b81-119">若要了解如何使用 Windows PowerShell 連線到 Exchange Online，請參閱[連線到 Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="66b81-119">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
  
## <a name="use-the-eac-to-edit-the-default-outbound-spam-policy"></a><span data-ttu-id="66b81-120">使用 EAC 編輯預設輸出垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="66b81-120">Use the EAC to edit the default outbound spam policy</span></span>
<span data-ttu-id="66b81-121"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="66b81-121"></span></span>

<span data-ttu-id="66b81-122">使用下列程序編輯預設輸出垃圾郵件原則：</span><span class="sxs-lookup"><span data-stu-id="66b81-122">Use the following procedure to edit the default outbound spam policy:</span></span>
  
### <a name="to-configure-the-default-outbound-spam-policy"></a><span data-ttu-id="66b81-123">設定預設輸出垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="66b81-123">To configure the default outbound spam policy</span></span>

1. <span data-ttu-id="66b81-124">在 Exchange 系統管理中心 (EAC) 中，瀏覽至 **[保護]** \> **[輸出垃圾郵件]**，然後連按兩下預設原則。</span><span class="sxs-lookup"><span data-stu-id="66b81-124">In the Exchange admin center (EAC), navigate to **Protection** \> **Outbound spam**, and then double-click the default policy.</span></span>
    
2. <span data-ttu-id="66b81-125">選取 **[輸出垃圾郵件喜好設定]** 功能表選項。</span><span class="sxs-lookup"><span data-stu-id="66b81-125">Select the **Outbound spam preferences** menu option.</span></span> 
    
3. <span data-ttu-id="66b81-126">選取輸出郵件的下列附屬核取方塊，然後在隨附的輸入方塊中指定關聯的電子郵件地址 (如果它們解析為有效的 SMTP 目的地，則這可以是通訊群組清單)：</span><span class="sxs-lookup"><span data-stu-id="66b81-126">Select the following check boxes pertaining to outbound messages, and then specify an associated email address or addresses in the accompanying input box (these can be distribution lists if they resolve as valid SMTP destinations):</span></span>
    
1. <span data-ttu-id="66b81-p104">**傳送所有可疑輸出電子郵件的副本至下列一或多個電子郵件地址**。這些是被篩選器標示為垃圾郵件的郵件 (不管其 SCL 分級)。篩選器不會拒絕這些郵件，而是會透過較高風險傳遞集區路由傳送這些郵件。請以分號分隔多個地址。請注意，指定的收件者會當作密件副本 (Bcc) 地址收到郵件 ([寄件者] 和 [收件者] 欄位為原始寄件者和收件者)。</span><span class="sxs-lookup"><span data-stu-id="66b81-p104">**Send a copy of all suspicious outbound email messages to the following email address or addresses**. These are messages that are marked as spam by the filter (regardless of the SCL rating). They are not rejected by the filter but are routed through the higher risk delivery pool. Separate multiple addresses with a semicolon. Note that the recipients specified will receive the messages as a Blind carbon copy (Bcc) address (the From and To fields are the original sender and recipient).</span></span>
    
2. <span data-ttu-id="66b81-p105">**當寄件者被封鎖無法傳送輸出垃圾郵件，傳送通知至下列電子郵件地址**。請以分號分隔多個地址。</span><span class="sxs-lookup"><span data-stu-id="66b81-p105">**Send a notification to the following email address when a sender is blocked sending outbound spam**. Separate multiple addresses with a semicolon.</span></span>
    
    <span data-ttu-id="66b81-134">當特定使用者發出大量垃圾郵件時，該使用者會被停用且無法再傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="66b81-134">When a significant amount of spam is originating from a particular user, the user is disabled from sending email messages.</span></span> <span data-ttu-id="66b81-135">網域的系統管理員 (使用此設定指定) 會收到通知，告知已封鎖該使用者的輸出郵件。</span><span class="sxs-lookup"><span data-stu-id="66b81-135">The administrator for the domain, who is specified using this setting, will be informed that outbound messages are blocked for this user.</span></span> <span data-ttu-id="66b81-136">若要查看此通知的外觀，請參閱[當封鎖寄件者時傳送輸出垃圾郵件的範例通知](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md)。</span><span class="sxs-lookup"><span data-stu-id="66b81-136">To see what this notification looks like, see [Sample notification when a sender is blocked sending outbound spam](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md).</span></span> <span data-ttu-id="66b81-137">如需加以重新啟用的詳細資訊，請參閱 <<c0>移除使用者、 網域或 IP 位址從封鎖清單傳送過垃圾。</span><span class="sxs-lookup"><span data-stu-id="66b81-137">For information about getting re-enabled, see [Removing a user, domain, or IP address from a block list after sending spam email](http://technet.microsoft.com/library/712cfcc1-31e8-4e51-8561-b64258a8f1e5.aspx).</span></span>
    
4. <span data-ttu-id="66b81-138">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="66b81-138">Click **save**.</span></span> <span data-ttu-id="66b81-139">預設原則設定的摘要隨即出現在右側窗格中。</span><span class="sxs-lookup"><span data-stu-id="66b81-139">A summary of your default policy settings appears in the right pane.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="66b81-140">相關資訊</span><span class="sxs-lookup"><span data-stu-id="66b81-140">For more information</span></span>
<span data-ttu-id="66b81-141"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="66b81-141"></span></span>

[<span data-ttu-id="66b81-142">高風險傳遞集區的外寄郵件</span><span class="sxs-lookup"><span data-stu-id="66b81-142">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)
  
[<span data-ttu-id="66b81-143">反垃圾郵件保護常見問題集</span><span class="sxs-lookup"><span data-stu-id="66b81-143">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
  

