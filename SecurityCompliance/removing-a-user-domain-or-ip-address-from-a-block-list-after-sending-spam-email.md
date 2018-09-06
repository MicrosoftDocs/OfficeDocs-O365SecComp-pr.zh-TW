---
title: 從封鎖清單移除使用者、 網域或 IP 位址傳送垃圾電子郵件之後
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 09/05/2018
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
ms.openlocfilehash: 3f3130bec3cde4cdc1343a0140a9013deacfc519
ms.sourcegitcommit: d85fc77cba3a17d5ddf215e2f506f61b499e0cda
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/06/2018
ms.locfileid: "23839107"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a><span data-ttu-id="3454c-103">從封鎖清單移除使用者、 網域或 IP 位址傳送垃圾電子郵件之後</span><span class="sxs-lookup"><span data-stu-id="3454c-103">Removing a user, domain, or IP address from a block list after sending spam email</span></span>

<span data-ttu-id="3454c-104">如果使用者持續傳送電子郵件訊息從歸類為垃圾郵件的 Office 365，他們會封鎖傳送任何詳細訊息。</span><span class="sxs-lookup"><span data-stu-id="3454c-104">If a user continuously sends email messages from Office 365 that is classified as spam, they will be blocked from sending any more messages.</span></span> 
  
<span data-ttu-id="3454c-105">當封鎖寄件者時傳送電子郵件訊息時，他們會收到未傳遞報告 （NDR 或無法將郵件傳送的電子郵件），提供有解除封鎖本身所採取的步驟的特定資訊。</span><span class="sxs-lookup"><span data-stu-id="3454c-105">When a sender is blocked from sending emails messages, they receive a Non-Delivery Report (NDR or email failed to send message) that provides specific information about the steps that they have to take to unblock themselves.</span></span>
  
<span data-ttu-id="3454c-p101">不僅可以個別使用者被封鎖服務，但特定網站、 網域及也也會遭到封鎖的 IP 位址。在某些情況下，網域或網站可以新增至封鎖清單只是因為它們顯示在垃圾郵件訊息。身為 Office 365 管理員，您可以嘗試取得使用者、 網站、 網域及從協力廠商封鎖清單中移除的 IP 位址。使用本主題底部表格中的連結來連絡每個協力廠商，然後依照指示。如果 Office 365 外的某個人無法將郵件傳送至您的 Office 365 帳戶，其帳戶可能已結束外部封鎖的寄件者清單上。Office 365 外部的使用者可以嘗試使用[自助取消列出的入口網站](https://technet.microsoft.com/library/mt661881%28v=exchg.150%29.aspx)從封鎖的寄件者清單中移除其本身。</span><span class="sxs-lookup"><span data-stu-id="3454c-p101">Not only can individual users be blocked by the service, but specific websites, domains, and IP addresses can also be blocked. In some cases, domains or websites can be added to a block list just because they appear in a spam message. As the Office 365 admin, you can try to get users, websites, domains, and IP addresses removed from third-party block lists. Use the links in the table at the bottom of this topic to contact each third party, and then follow the instructions. If someone outside Office 365 cannot send messages to your Office 365 account, their account may have ended up on the external blocked senders list. Users outside Office 365 can try to remove themselves from the blocked senders list by using the [self-service delisting portal](https://technet.microsoft.com/library/mt661881%28v=exchg.150%29.aspx).</span></span>
  
<span data-ttu-id="3454c-p102">您可以設定輸出垃圾郵件，讓您取得 anotification 時的 Office 365 使用者禁止傳送電子郵件被分類為垃圾郵件。與使用者的信箱問題已解決之後，您可以移除該寄件者在區塊。</span><span class="sxs-lookup"><span data-stu-id="3454c-p102">You can configure outbound spam settings so that you get anotification when an Office 365 user is blocked from sending email that's classified as spam. After the problem with the user's mailbox is resolved, you can remove the block on that sender.</span></span>
  
## <a name="unblock-a-blocked-office-365-email-account"></a><span data-ttu-id="3454c-114">解除封鎖封鎖的 Office 365 電子郵件帳戶</span><span class="sxs-lookup"><span data-stu-id="3454c-114">Unblock a blocked Office 365 email account</span></span>

<span data-ttu-id="3454c-p103">您完成此工作中的 Office 365 的安全性與規範中心 」 (SCC)。如需詳細資訊 SCC [[移至 [Office 365 安全性及規範中心](go-to-the-securitycompliance-center.md)]。</span><span class="sxs-lookup"><span data-stu-id="3454c-p103">You complete this task in the Office 365 Security & Compliance Center (SCC). [Go to the Office 365 Security & Compliance Center](go-to-the-securitycompliance-center.md) for more details about SCC.</span></span>

1. <span data-ttu-id="3454c-117">使用工作或學校的帳戶具備 Office 365 全域管理員權限，登入 Office 365 安全性和規範中心及在左側清單中，依序展開 [ **Threat Management**，並選擇 [**檢閱**，然後選擇 [**限制使用者**。</span><span class="sxs-lookup"><span data-stu-id="3454c-117">Using a work or school account that has Office 365 global administrator privileges, sign into the Office 365 Security and Compliance Center and in the list on the left, expand **Threat Management**, choose **Review**, and then choose **Restricted Users**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="3454c-118">若要直接移至 [**限制使用者**頁面的安全性&amp;規範中心使用此 URL: >[https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span><span class="sxs-lookup"><span data-stu-id="3454c-118">To go directly to the **Restricted Users** page in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span></span>

2. <span data-ttu-id="3454c-p104">此頁面可包含被封鎖傳送郵件給組織外的使用者清單。 尋找您想要移除限制，然後按一下 [**解除**從中。</span><span class="sxs-lookup"><span data-stu-id="3454c-p104">This page will contain the list of users that have been blocked from sending mail to outside of your organization.  Find the user(s) you wish to remove restrictions and then click on **Unblock**.</span></span>

3. <span data-ttu-id="3454c-121">按一下 [**是]** 確認變更。</span><span class="sxs-lookup"><span data-stu-id="3454c-121">Click **Yes** to confirm the change.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="3454c-p105">有限制的帳戶可以解除封鎖承租人管理員的次數如果已超過此限制的使用者，就會出現錯誤訊息。然後您必須連絡支援人員以解除封鎖使用者。</span><span class="sxs-lookup"><span data-stu-id="3454c-p105">There's a limit to the number of times that an account can be unblocked by the tenant admin. If the limit for a user has been exceeded, an error message appears. You will then need to contact Support to unblock the user.</span></span> 
  
## <a name="third-party-block-lists"></a><span data-ttu-id="3454c-124">協力廠商封鎖清單</span><span class="sxs-lookup"><span data-stu-id="3454c-124">Third-party block lists</span></span>

|<span data-ttu-id="3454c-125">**清單名稱**</span><span class="sxs-lookup"><span data-stu-id="3454c-125">**List Name**</span></span>|<span data-ttu-id="3454c-126">**取消列出的入口網站**</span><span class="sxs-lookup"><span data-stu-id="3454c-126">**Delisting Portal**</span></span>|<span data-ttu-id="3454c-127">**相關資訊**</span><span class="sxs-lookup"><span data-stu-id="3454c-127">**For more information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3454c-128">URIBL</span><span class="sxs-lookup"><span data-stu-id="3454c-128">URIBL</span></span>  <br/> |[https://admin.uribl.com/?section=lookup](https://admin.uribl.com/?section=lookup) <br/> |[<span data-ttu-id="3454c-129">URIBL 網站</span><span class="sxs-lookup"><span data-stu-id="3454c-129">URIBL website </span></span>](https://uribl.com/) <br/> |
|<span data-ttu-id="3454c-130">SURBL</span><span class="sxs-lookup"><span data-stu-id="3454c-130">SURBL</span></span>  <br/> |[http://www.surbl.org/surbl-analysis](http://www.surbl.org/surbl-analysis) <br/> |[<span data-ttu-id="3454c-131">SURBL URI 信譽資料簡介</span><span class="sxs-lookup"><span data-stu-id="3454c-131">Introducing SURBL URI reputation data</span></span>](http://www.surbl.org/) <br/> |
|<span data-ttu-id="3454c-132">Spamhaus</span><span class="sxs-lookup"><span data-stu-id="3454c-132">Spamhaus</span></span>  <br/> |[https://www.spamhaus.org/lookup/](https://www.spamhaus.org/lookup/) <br/> |[<span data-ttu-id="3454c-133">了解 DNSBL 篩選</span><span class="sxs-lookup"><span data-stu-id="3454c-133">Understanding DNSBL Filtering</span></span>](https://www.spamhaus.org/whitepapers/dnsbl_function/) <br/> |
|<span data-ttu-id="3454c-134">invaluement</span><span class="sxs-lookup"><span data-stu-id="3454c-134">invaluement</span></span>  <br/> |[http://dnsbl.invaluement.com/lookup/](http://dnsbl.invaluement.com/lookup/) <br/> |[<span data-ttu-id="3454c-135">invaluement 反垃圾郵件清單</span><span class="sxs-lookup"><span data-stu-id="3454c-135">invaluement anti-spam list</span></span>](http://dnsbl.invaluement.com/) <br/> |
|<span data-ttu-id="3454c-136">Phishtank</span><span class="sxs-lookup"><span data-stu-id="3454c-136">Phishtank</span></span>  <br/> |[https://www.phishtank.com/](https://www.phishtank.com/) <br/> |[<span data-ttu-id="3454c-137">PhishTank 常見問題集</span><span class="sxs-lookup"><span data-stu-id="3454c-137">PhishTank FAQ</span></span>](https://www.phishtank.com/faq.php) <br/> |
   
> [!NOTE]
> <span data-ttu-id="3454c-138">Exchange Online Protection 也會使用第三方封鎖清單的垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="3454c-138">Exchange Online Protection also uses third-party block lists for spam filtering.</span></span> 
   
## <a name="for-more-information"></a><span data-ttu-id="3454c-139">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="3454c-139">For more information</span></span>

[<span data-ttu-id="3454c-140">設定輸出垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="3454c-140">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="3454c-141">外寄郵件的高風險傳遞集區</span><span class="sxs-lookup"><span data-stu-id="3454c-141">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="3454c-142">使用取消列出入口網站，將您自己從 Office 365 封鎖寄件者清單中移除</span><span class="sxs-lookup"><span data-stu-id="3454c-142">Use the delist portal to remove yourself from the Office 365 blocked senders list</span></span>](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)
  

  

