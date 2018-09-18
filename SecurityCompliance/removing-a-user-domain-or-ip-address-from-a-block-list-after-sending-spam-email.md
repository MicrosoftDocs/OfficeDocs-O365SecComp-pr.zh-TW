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
ms.openlocfilehash: 6665c405c62f75b77e7898419ebcfbc1c8c20f4c
ms.sourcegitcommit: 7b85c22fc85ec19e4b44a07e91bfa9ade768185a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2018
ms.locfileid: "23998607"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a><span data-ttu-id="87d10-103">從封鎖清單移除使用者、 網域或 IP 位址傳送垃圾電子郵件之後</span><span class="sxs-lookup"><span data-stu-id="87d10-103">Removing a user, domain, or IP address from a block list after sending spam email</span></span>

<span data-ttu-id="87d10-p101">如果使用者持續傳送電子郵件訊息從歸類為垃圾郵件的 Office 365，他們會封鎖傳送任何詳細訊息。使用者將會列在為損壞的撥出寄件者的服務，也會收到未傳遞報告 (NDR) 表示：</span><span class="sxs-lookup"><span data-stu-id="87d10-p101">If a user continuously sends email messages from Office 365 that is classified as spam, they will be blocked from sending any more messages. The user will be listed in the service as a bad outbound sender and will receive a Non-Delivery Report (NDR) that states:</span></span>

- <span data-ttu-id="87d10-p102">因為未被視為有效的寄件者無法傳遞郵件。最常見原因是您的電子郵件地址可疑的垃圾郵件的傳送和它已不再允許傳送到組織外的郵件。如需協助連絡電子郵件系統。 遠端伺服器傳回 '550 5.1.8 「 拒絕存取 」、 損壞的撥出寄件者 」</span><span class="sxs-lookup"><span data-stu-id="87d10-p102">Your message couldn't be delivered because you weren't recognized as a valid sender. The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send messages outside of your organization. Contact your email admin for assistance.  Remote Server returned '550 5.1.8 Access denied, bad outbound sender'</span></span>

<span data-ttu-id="87d10-p103">您可以設定您的輸出垃圾郵件原則設定，讓您在 Office 365 使用者禁止傳送電子郵件時收到通知。與使用者的信箱問題已解決之後，您可以移除該寄件者在區塊。</span><span class="sxs-lookup"><span data-stu-id="87d10-p103">You can configure your outbound spam policy settings so that you get a notification when an Office 365 user is blocked from sending email. After the problem with the user's mailbox is resolved, you can remove the block on that sender.</span></span>
  
## <a name="unblock-a-blocked-office-365-email-account"></a><span data-ttu-id="87d10-112">解除封鎖封鎖的 Office 365 電子郵件帳戶</span><span class="sxs-lookup"><span data-stu-id="87d10-112">Unblock a blocked Office 365 email account</span></span>

<span data-ttu-id="87d10-p104">您完成此工作中的 Office 365 的安全性與規範中心 」 (SCC)。如需詳細資訊 SCC [[移至 [Office 365 安全性及規範中心](go-to-the-securitycompliance-center.md)]。</span><span class="sxs-lookup"><span data-stu-id="87d10-p104">You complete this task in the Office 365 Security & Compliance Center (SCC). [Go to the Office 365 Security & Compliance Center](go-to-the-securitycompliance-center.md) for more details about SCC.</span></span>

1. <span data-ttu-id="87d10-115">使用工作或學校的帳戶具備 Office 365 全域管理員權限，登入 Office 365 安全性和規範中心及在左側清單中，依序展開 [ **Threat Management**，並選擇 [**檢閱**，然後選擇 [**限制使用者**。</span><span class="sxs-lookup"><span data-stu-id="87d10-115">Using a work or school account that has Office 365 global administrator privileges, sign into the Office 365 Security and Compliance Center and in the list on the left, expand **Threat Management**, choose **Review**, and then choose **Restricted Users**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="87d10-116">若要直接移至 [**限制使用者**頁面的安全性&amp;規範中心使用此 URL: >[https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span><span class="sxs-lookup"><span data-stu-id="87d10-116">To go directly to the **Restricted Users** page in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span></span>

2. <span data-ttu-id="87d10-p105">此頁面可包含被封鎖傳送郵件給組織外的使用者清單。 尋找您想要移除限制上，然後按一下 [**解除**的使用者。</span><span class="sxs-lookup"><span data-stu-id="87d10-p105">This page will contain the list of users that have been blocked from sending mail to outside of your organization.  Find the user you wish to remove restrictions on and then click on **Unblock**.</span></span>

3. <span data-ttu-id="87d10-119">按一下 [**是]** 確認變更。</span><span class="sxs-lookup"><span data-stu-id="87d10-119">Click **Yes** to confirm the change.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="87d10-p106">有限制的帳戶可以解除封鎖承租人管理員的次數如果已超過此限制的使用者，就會出現錯誤訊息。然後您必須連絡支援人員以解除封鎖使用者。</span><span class="sxs-lookup"><span data-stu-id="87d10-p106">There's a limit to the number of times that an account can be unblocked by the tenant admin. If the limit for a user has been exceeded, an error message appears. You will then need to contact Support to unblock the user.</span></span>
  
## <a name="third-party-block-lists"></a><span data-ttu-id="87d10-122">協力廠商封鎖清單</span><span class="sxs-lookup"><span data-stu-id="87d10-122">Third-party block lists</span></span>

<span data-ttu-id="87d10-p107">Exchange Online Protection 也會使用第三方封鎖清單來提升決策的垃圾郵件篩選。使用者、 網站、 網域及 IP 位址可以新增要封鎖只是為了垃圾郵件訊息中出現的清單。為 Office 365 系統管理員應該嘗試取得如果所屬您移除的協力廠商清單提供者從這些物件。使用中的連結來連絡每個協力廠商，然後依照其指示表格的下方。</span><span class="sxs-lookup"><span data-stu-id="87d10-p107">Exchange Online Protection also uses third-party block lists to help make decisions in spam filtering. Users, websites, domains, and IP addresses can be added to block lists just for appearing in a spam message. As the Office 365 admin, you should try to get these objects removed from the third-party list providers if they belong to you. Use the links in the below table to contact each third party and then follow their instructions.</span></span>

|<span data-ttu-id="87d10-127">**清單名稱**</span><span class="sxs-lookup"><span data-stu-id="87d10-127">**List Name**</span></span>|<span data-ttu-id="87d10-128">**取消列出的入口網站**</span><span class="sxs-lookup"><span data-stu-id="87d10-128">**Delisting Portal**</span></span>|<span data-ttu-id="87d10-129">**相關資訊**</span><span class="sxs-lookup"><span data-stu-id="87d10-129">**For more information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="87d10-130">URIBL</span><span class="sxs-lookup"><span data-stu-id="87d10-130">URIBL</span></span>  <br/> |[https://admin.uribl.com/?section=lookup](https://admin.uribl.com/?section=lookup) <br/> |[<span data-ttu-id="87d10-131">URIBL 網站</span><span class="sxs-lookup"><span data-stu-id="87d10-131">URIBL website </span></span>](https://uribl.com/) <br/> |
|<span data-ttu-id="87d10-132">SURBL</span><span class="sxs-lookup"><span data-stu-id="87d10-132">SURBL</span></span>  <br/> |[http://www.surbl.org/surbl-analysis](http://www.surbl.org/surbl-analysis) <br/> |[<span data-ttu-id="87d10-133">SURBL URI 信譽資料簡介</span><span class="sxs-lookup"><span data-stu-id="87d10-133">Introducing SURBL URI reputation data</span></span>](http://www.surbl.org/) <br/> |
|<span data-ttu-id="87d10-134">Spamhaus</span><span class="sxs-lookup"><span data-stu-id="87d10-134">Spamhaus</span></span>  <br/> |[https://www.spamhaus.org/lookup/](https://www.spamhaus.org/lookup/) <br/> |[<span data-ttu-id="87d10-135">了解 DNSBL 篩選</span><span class="sxs-lookup"><span data-stu-id="87d10-135">Understanding DNSBL Filtering</span></span>](https://www.spamhaus.org/whitepapers/dnsbl_function/) <br/> |
|<span data-ttu-id="87d10-136">invaluement</span><span class="sxs-lookup"><span data-stu-id="87d10-136">invaluement</span></span>  <br/> |[http://dnsbl.invaluement.com/lookup/](http://dnsbl.invaluement.com/lookup/) <br/> |[<span data-ttu-id="87d10-137">invaluement 反垃圾郵件清單</span><span class="sxs-lookup"><span data-stu-id="87d10-137">invaluement anti-spam list</span></span>](http://dnsbl.invaluement.com/) <br/> |
|<span data-ttu-id="87d10-138">Phishtank</span><span class="sxs-lookup"><span data-stu-id="87d10-138">Phishtank</span></span>  <br/> |[https://www.phishtank.com/](https://www.phishtank.com/) <br/> |[<span data-ttu-id="87d10-139">PhishTank 常見問題集</span><span class="sxs-lookup"><span data-stu-id="87d10-139">PhishTank FAQ</span></span>](https://www.phishtank.com/faq.php) <br/> |

> [!NOTE]
> <span data-ttu-id="87d10-p108">如果 Office 365 外的某個人無法將郵件傳送至您的 Office 365 帳戶，其帳戶可能會在外部封鎖的寄件者清單。Office 365 外部的使用者可以嘗試使用[自助取消列出的入口網站](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis)中移除其本身。</span><span class="sxs-lookup"><span data-stu-id="87d10-p108">If someone outside Office 365 cannot send messages to your Office 365 account, their account may be on the external blocked senders list. Users outside Office 365 can try to remove themselves by using the [self-service delisting portal](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis).</span></span> 

## <a name="for-more-information"></a><span data-ttu-id="87d10-142">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="87d10-142">For more information</span></span>

[<span data-ttu-id="87d10-143">回應洩漏電子郵件帳戶</span><span class="sxs-lookup"><span data-stu-id="87d10-143">Responding to a compromised email account</span></span>](responding-to-a-compromised-email-account.md)

[<span data-ttu-id="87d10-144">設定輸出垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="87d10-144">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="87d10-145">外寄郵件的高風險傳遞集區</span><span class="sxs-lookup"><span data-stu-id="87d10-145">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

  

  

