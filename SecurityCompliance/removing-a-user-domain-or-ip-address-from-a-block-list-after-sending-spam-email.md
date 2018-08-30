---
title: 從封鎖清單移除使用者、 網域或 IP 位址傳送垃圾電子郵件之後
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/20/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
description: 如果使用者持續傳送電子郵件訊息從歸類為垃圾郵件的 Office 365，他們會封鎖傳送任何詳細訊息。
ms.openlocfilehash: 87b7083fe1345a15ea582f12a5b0d417bbe6b568
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002590"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a><span data-ttu-id="c9a28-103">從封鎖清單移除使用者、 網域或 IP 位址傳送垃圾電子郵件之後</span><span class="sxs-lookup"><span data-stu-id="c9a28-103">Removing a user, domain, or IP address from a block list after sending spam email</span></span>

<span data-ttu-id="c9a28-104">如果使用者持續傳送電子郵件訊息從歸類為垃圾郵件的 Office 365，他們會封鎖傳送任何詳細訊息。</span><span class="sxs-lookup"><span data-stu-id="c9a28-104">If a user continuously sends email messages from Office 365 that is classified as spam, they will be blocked from sending any more messages.</span></span> 
  
<span data-ttu-id="c9a28-105">當封鎖寄件者時傳送電子郵件訊息時，他們會收到未傳遞報告 （NDR 或無法將郵件傳送的電子郵件），提供有解除封鎖本身所採取的步驟的特定資訊。</span><span class="sxs-lookup"><span data-stu-id="c9a28-105">When a sender is blocked from sending emails messages, they receive a Non-Delivery Report (NDR or email failed to send message) that provides specific information about the steps that they have to take to unblock themselves.</span></span>
  
<span data-ttu-id="c9a28-p101">不僅可以個別使用者被封鎖服務，但特定網站、 網域及也也會遭到封鎖的 IP 位址。在某些情況下，網域或網站可以新增至封鎖清單只是因為它們顯示在垃圾郵件訊息。身為 Office 365 管理員，您可以嘗試取得使用者、 網站、 網域及從協力廠商封鎖清單中移除的 IP 位址。使用本主題底部表格中的連結來連絡每個協力廠商，然後依照指示。如果 Office 365 外的某個人無法將郵件傳送至您的 Office 365 帳戶，其帳戶可能已結束外部封鎖的寄件者清單上。Office 365 外部的使用者可以嘗試使用[自助取消列出的入口網站](https://technet.microsoft.com/library/mt661881%28v=exchg.150%29.aspx)從封鎖的寄件者清單中移除其本身。</span><span class="sxs-lookup"><span data-stu-id="c9a28-p101">Not only can individual users be blocked by the service, but specific websites, domains, and IP addresses can also be blocked. In some cases, domains or websites can be added to a block list just because they appear in a spam message. As the Office 365 admin, you can try to get users, websites, domains, and IP addresses removed from third-party block lists. Use the links in the table at the bottom of this topic to contact each third party, and then follow the instructions. If someone outside Office 365 cannot send messages to your Office 365 account, their account may have ended up on the external blocked senders list. Users outside Office 365 can try to remove themselves from the blocked senders list by using the [self-service delisting portal](https://technet.microsoft.com/library/mt661881%28v=exchg.150%29.aspx).</span></span>
  
<span data-ttu-id="c9a28-p102">您可以設定輸出垃圾郵件，讓您取得 anotification 時的 Office 365 使用者禁止傳送電子郵件被分類為垃圾郵件。與使用者的信箱問題已解決之後，您可以移除該寄件者在區塊。</span><span class="sxs-lookup"><span data-stu-id="c9a28-p102">You can configure outbound spam settings so that you get anotification when an Office 365 user is blocked from sending email that's classified as spam. After the problem with the user's mailbox is resolved, you can remove the block on that sender.</span></span>
  
## <a name="unblock-a-blocked-office-365-email-account"></a><span data-ttu-id="c9a28-114">解除封鎖封鎖的 Office 365 電子郵件帳戶</span><span class="sxs-lookup"><span data-stu-id="c9a28-114">Unblock a blocked Office 365 email account</span></span>

<span data-ttu-id="c9a28-p103">您完成這項工作在 Exchange 系統管理中心 (EAC) 中。如需詳細資訊 EAC 檢查出[admin center in Exchange Online Protection Exchange](exchange-admin-center-in-exchange-online-protection-eop.md) 。</span><span class="sxs-lookup"><span data-stu-id="c9a28-p103">You complete this task in the Exchange admin center (EAC). Check out [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md) for details about the EAC.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c9a28-117">除非您是在 Exchange Online 的 EAC 就無法看到動作中心。</span><span class="sxs-lookup"><span data-stu-id="c9a28-117">You won't see the action center unless you're in the EAC for Exchange Online.</span></span> 
  
1. <span data-ttu-id="c9a28-118">在 EAC 中，瀏覽至 [**保護** \> **動作中心**。</span><span class="sxs-lookup"><span data-stu-id="c9a28-118">In the EAC, navigate to **protection** \> **action center**.</span></span>
    
    ![瀏覽至 Exchange 系統管理員中心的重要訊息中心 。](media/9bbf0844-7b34-4a86-a2b7-8c7e9c8519a3.png)
  
2. <span data-ttu-id="c9a28-120">選取 [**搜尋**] 圖示，然後輸入 [封鎖的使用者的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="c9a28-120">Select the **Search** icon, and then enter the SMTP address of the blocked user.</span></span> 
    
    ![搜尋重要訊息中心中封鎖的使用者](media/f931b5a0-7115-4d95-9f6f-b403436031ba.png)
  
3. <span data-ttu-id="c9a28-122">在 [描述] 窗格中按一下**解除封鎖的帳戶**。</span><span class="sxs-lookup"><span data-stu-id="c9a28-122">Click **Unblock Account** in the description pane.</span></span> 
    
    ![解除封鎖重要訊息中心中的使用者](media/c5d5b1b9-8416-45aa-9631-881e94d1d056.png)
  
4. <span data-ttu-id="c9a28-124">按一下 [**是]** 確認變更。</span><span class="sxs-lookup"><span data-stu-id="c9a28-124">Click **Yes** to confirm the change.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="c9a28-p104">有限制的帳戶可以解除封鎖承租人管理員的次數如果已超過此限制的使用者，就會出現錯誤訊息。連絡支援人員以解除封鎖使用者。</span><span class="sxs-lookup"><span data-stu-id="c9a28-p104">There's a limit to the number of times that an account can be unblocked by the tenant admin. If the limit for a user has been exceeded, an error message appears. Contact Support to unblock the user.</span></span> 
  
## <a name="third-party-block-lists"></a><span data-ttu-id="c9a28-127">協力廠商封鎖清單</span><span class="sxs-lookup"><span data-stu-id="c9a28-127">Third-party block lists</span></span>

|<span data-ttu-id="c9a28-128">**清單名稱**</span><span class="sxs-lookup"><span data-stu-id="c9a28-128">**List Name**</span></span>|<span data-ttu-id="c9a28-129">**取消列出的入口網站**</span><span class="sxs-lookup"><span data-stu-id="c9a28-129">**Delisting Portal**</span></span>|<span data-ttu-id="c9a28-130">**相關資訊**</span><span class="sxs-lookup"><span data-stu-id="c9a28-130">**For more information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c9a28-131">URIBL</span><span class="sxs-lookup"><span data-stu-id="c9a28-131">URIBL</span></span>  <br/> |[https://admin.uribl.com/?section=lookup](https://admin.uribl.com/?section=lookup) <br/> |[<span data-ttu-id="c9a28-132">URIBL 網站</span><span class="sxs-lookup"><span data-stu-id="c9a28-132">URIBL website </span></span>](https://uribl.com/) <br/> |
|<span data-ttu-id="c9a28-133">SURBL</span><span class="sxs-lookup"><span data-stu-id="c9a28-133">SURBL</span></span>  <br/> |[http://www.surbl.org/surbl-analysis](http://www.surbl.org/surbl-analysis) <br/> |[<span data-ttu-id="c9a28-134">SURBL URI 信譽資料簡介</span><span class="sxs-lookup"><span data-stu-id="c9a28-134">Introducing SURBL URI reputation data</span></span>](http://www.surbl.org/) <br/> |
|<span data-ttu-id="c9a28-135">Spamhaus</span><span class="sxs-lookup"><span data-stu-id="c9a28-135">Spamhaus</span></span>  <br/> |[https://www.spamhaus.org/lookup/](https://www.spamhaus.org/lookup/) <br/> |[<span data-ttu-id="c9a28-136">了解 DNSBL 篩選</span><span class="sxs-lookup"><span data-stu-id="c9a28-136">Understanding DNSBL Filtering</span></span>](https://www.spamhaus.org/whitepapers/dnsbl_function/) <br/> |
|<span data-ttu-id="c9a28-137">invaluement</span><span class="sxs-lookup"><span data-stu-id="c9a28-137">invaluement</span></span>  <br/> |[http://dnsbl.invaluement.com/lookup/](http://dnsbl.invaluement.com/lookup/) <br/> |[<span data-ttu-id="c9a28-138">invaluement 反垃圾郵件清單</span><span class="sxs-lookup"><span data-stu-id="c9a28-138">invaluement anti-spam list</span></span>](http://dnsbl.invaluement.com/) <br/> |
|<span data-ttu-id="c9a28-139">Phishtank</span><span class="sxs-lookup"><span data-stu-id="c9a28-139">Phishtank</span></span>  <br/> |[https://www.phishtank.com/](https://www.phishtank.com/) <br/> |[<span data-ttu-id="c9a28-140">PhishTank 常見問題集</span><span class="sxs-lookup"><span data-stu-id="c9a28-140">PhishTank FAQ</span></span>](https://www.phishtank.com/faq.php) <br/> |
   
> [!NOTE]
> <span data-ttu-id="c9a28-141">Exchange Online Protection 也會使用第三方封鎖清單的垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="c9a28-141">Exchange Online Protection also uses third-party block lists for spam filtering.</span></span> 
   
## <a name="for-more-information"></a><span data-ttu-id="c9a28-142">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="c9a28-142">For more information</span></span>

[<span data-ttu-id="c9a28-143">設定輸出垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="c9a28-143">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="c9a28-144">外寄郵件的高風險傳遞集區</span><span class="sxs-lookup"><span data-stu-id="c9a28-144">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="c9a28-145">使用取消列出入口網站，將您自己從 Office 365 封鎖寄件者清單中移除</span><span class="sxs-lookup"><span data-stu-id="c9a28-145">Use the delist portal to remove yourself from the Office 365 blocked senders list</span></span>](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)
  

  

