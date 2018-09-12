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
ms.openlocfilehash: 8dcd6c8f55d867e1c2e249ec71a3a5c6b78ac76a
ms.sourcegitcommit: d89c24258123a3ffde574a391d59afd3aea8470d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/12/2018
ms.locfileid: "23955435"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a><span data-ttu-id="3f95d-103">從封鎖清單移除使用者、 網域或 IP 位址傳送垃圾電子郵件之後</span><span class="sxs-lookup"><span data-stu-id="3f95d-103">Removing a user, domain, or IP address from a block list after sending spam email</span></span>

<span data-ttu-id="3f95d-p101">如果使用者持續傳送電子郵件訊息從歸類為垃圾郵件的 Office 365，他們會封鎖傳送任何詳細訊息。使用者將會列在為損壞的撥出寄件者的服務，也會收到未傳遞報告 （NDR 或無法將郵件傳送的電子郵件），提供有解除封鎖本身所採取的步驟的特定資訊。</span><span class="sxs-lookup"><span data-stu-id="3f95d-p101">If a user continuously sends email messages from Office 365 that is classified as spam, they will be blocked from sending any more messages. The user will be listed in the service as a bad outbound sender and will receive a Non-Delivery Report (NDR or email failed to send message) that provides specific information about the steps that they have to take to unblock themselves.</span></span>

<span data-ttu-id="3f95d-p102">您可以設定您的輸出垃圾郵件原則設定，讓您在 Office 365 使用者禁止傳送電子郵件時收到通知。與使用者的信箱問題已解決之後，您可以移除該寄件者在區塊。</span><span class="sxs-lookup"><span data-stu-id="3f95d-p102">You can configure your outbound spam policy settings so that you get a notification when an Office 365 user is blocked from sending email. After the problem with the user's mailbox is resolved, you can remove the block on that sender.</span></span>
  
## <a name="unblock-a-blocked-office-365-email-account"></a><span data-ttu-id="3f95d-108">解除封鎖封鎖的 Office 365 電子郵件帳戶</span><span class="sxs-lookup"><span data-stu-id="3f95d-108">Unblock a blocked Office 365 email account</span></span>

<span data-ttu-id="3f95d-p103">您完成此工作中的 Office 365 的安全性與規範中心 」 (SCC)。如需詳細資訊 SCC [[移至 [Office 365 安全性及規範中心](go-to-the-securitycompliance-center.md)]。</span><span class="sxs-lookup"><span data-stu-id="3f95d-p103">You complete this task in the Office 365 Security & Compliance Center (SCC). [Go to the Office 365 Security & Compliance Center](go-to-the-securitycompliance-center.md) for more details about SCC.</span></span>

1. <span data-ttu-id="3f95d-111">使用工作或學校的帳戶具備 Office 365 全域管理員權限，登入 Office 365 安全性和規範中心及在左側清單中，依序展開 [ **Threat Management**，並選擇 [**檢閱**，然後選擇 [**限制使用者**。</span><span class="sxs-lookup"><span data-stu-id="3f95d-111">Using a work or school account that has Office 365 global administrator privileges, sign into the Office 365 Security and Compliance Center and in the list on the left, expand **Threat Management**, choose **Review**, and then choose **Restricted Users**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="3f95d-112">若要直接移至 [**限制使用者**頁面的安全性&amp;規範中心使用此 URL: >[https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span><span class="sxs-lookup"><span data-stu-id="3f95d-112">To go directly to the **Restricted Users** page in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span></span>

2. <span data-ttu-id="3f95d-p104">此頁面可包含被封鎖傳送郵件給組織外的使用者清單。 尋找您想要移除限制上，然後按一下 [**解除**的使用者。</span><span class="sxs-lookup"><span data-stu-id="3f95d-p104">This page will contain the list of users that have been blocked from sending mail to outside of your organization.  Find the user you wish to remove restrictions on and then click on **Unblock**.</span></span>

3. <span data-ttu-id="3f95d-115">按一下 [**是]** 確認變更。</span><span class="sxs-lookup"><span data-stu-id="3f95d-115">Click **Yes** to confirm the change.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="3f95d-p105">有限制的帳戶可以解除封鎖承租人管理員的次數如果已超過此限制的使用者，就會出現錯誤訊息。然後您必須連絡支援人員以解除封鎖使用者。</span><span class="sxs-lookup"><span data-stu-id="3f95d-p105">There's a limit to the number of times that an account can be unblocked by the tenant admin. If the limit for a user has been exceeded, an error message appears. You will then need to contact Support to unblock the user.</span></span>
  
## <a name="third-party-block-lists"></a><span data-ttu-id="3f95d-118">協力廠商封鎖清單</span><span class="sxs-lookup"><span data-stu-id="3f95d-118">Third-party block lists</span></span>

<span data-ttu-id="3f95d-p106">Exchange Online Protection 也會使用第三方封鎖清單來提升決策的垃圾郵件篩選。使用者、 網站、 網域及 IP 位址可以新增要封鎖只是為了垃圾郵件訊息中出現的清單。為 Office 365 系統管理員應該嘗試取得如果所屬您移除的協力廠商清單提供者從這些物件。使用中的連結來連絡每個協力廠商，然後依照其指示表格的下方。</span><span class="sxs-lookup"><span data-stu-id="3f95d-p106">Exchange Online Protection also uses third-party block lists to help make decisions in spam filtering. Users, websites, domains, and IP addresses can be added to block lists just for appearing in a spam message. As the Office 365 admin, you should try to get these objects removed from the third-party list providers if they belong to you. Use the links in the below table to contact each third party and then follow their instructions.</span></span>

|<span data-ttu-id="3f95d-123">**清單名稱**</span><span class="sxs-lookup"><span data-stu-id="3f95d-123">**List Name**</span></span>|<span data-ttu-id="3f95d-124">**取消列出的入口網站**</span><span class="sxs-lookup"><span data-stu-id="3f95d-124">**Delisting Portal**</span></span>|<span data-ttu-id="3f95d-125">**相關資訊**</span><span class="sxs-lookup"><span data-stu-id="3f95d-125">**For more information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3f95d-126">URIBL</span><span class="sxs-lookup"><span data-stu-id="3f95d-126">URIBL</span></span>  <br/> |[https://admin.uribl.com/?section=lookup](https://admin.uribl.com/?section=lookup) <br/> |[<span data-ttu-id="3f95d-127">URIBL 網站</span><span class="sxs-lookup"><span data-stu-id="3f95d-127">URIBL website </span></span>](https://uribl.com/) <br/> |
|<span data-ttu-id="3f95d-128">SURBL</span><span class="sxs-lookup"><span data-stu-id="3f95d-128">SURBL</span></span>  <br/> |[http://www.surbl.org/surbl-analysis](http://www.surbl.org/surbl-analysis) <br/> |[<span data-ttu-id="3f95d-129">SURBL URI 信譽資料簡介</span><span class="sxs-lookup"><span data-stu-id="3f95d-129">Introducing SURBL URI reputation data</span></span>](http://www.surbl.org/) <br/> |
|<span data-ttu-id="3f95d-130">Spamhaus</span><span class="sxs-lookup"><span data-stu-id="3f95d-130">Spamhaus</span></span>  <br/> |[https://www.spamhaus.org/lookup/](https://www.spamhaus.org/lookup/) <br/> |[<span data-ttu-id="3f95d-131">了解 DNSBL 篩選</span><span class="sxs-lookup"><span data-stu-id="3f95d-131">Understanding DNSBL Filtering</span></span>](https://www.spamhaus.org/whitepapers/dnsbl_function/) <br/> |
|<span data-ttu-id="3f95d-132">invaluement</span><span class="sxs-lookup"><span data-stu-id="3f95d-132">invaluement</span></span>  <br/> |[http://dnsbl.invaluement.com/lookup/](http://dnsbl.invaluement.com/lookup/) <br/> |[<span data-ttu-id="3f95d-133">invaluement 反垃圾郵件清單</span><span class="sxs-lookup"><span data-stu-id="3f95d-133">invaluement anti-spam list</span></span>](http://dnsbl.invaluement.com/) <br/> |
|<span data-ttu-id="3f95d-134">Phishtank</span><span class="sxs-lookup"><span data-stu-id="3f95d-134">Phishtank</span></span>  <br/> |[https://www.phishtank.com/](https://www.phishtank.com/) <br/> |[<span data-ttu-id="3f95d-135">PhishTank 常見問題集</span><span class="sxs-lookup"><span data-stu-id="3f95d-135">PhishTank FAQ</span></span>](https://www.phishtank.com/faq.php) <br/> |

> [!NOTE]
> <span data-ttu-id="3f95d-p107">如果 Office 365 外的某個人無法將郵件傳送至您的 Office 365 帳戶，其帳戶可能會在外部封鎖的寄件者清單。Office 365 外部的使用者可以嘗試使用[自助取消列出的入口網站](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis)中移除其本身。</span><span class="sxs-lookup"><span data-stu-id="3f95d-p107">If someone outside Office 365 cannot send messages to your Office 365 account, their account may be on the external blocked senders list. Users outside Office 365 can try to remove themselves by using the [self-service delisting portal](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis).</span></span> 

## <a name="for-more-information"></a><span data-ttu-id="3f95d-138">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="3f95d-138">For more information</span></span>

[<span data-ttu-id="3f95d-139">回應洩漏電子郵件帳戶</span><span class="sxs-lookup"><span data-stu-id="3f95d-139">Responding to a compromised email account</span></span>](responding-to-a-compromised-email-account.md)

[<span data-ttu-id="3f95d-140">設定輸出垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="3f95d-140">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="3f95d-141">外寄郵件的高風險傳遞集區</span><span class="sxs-lookup"><span data-stu-id="3f95d-141">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

  

  

