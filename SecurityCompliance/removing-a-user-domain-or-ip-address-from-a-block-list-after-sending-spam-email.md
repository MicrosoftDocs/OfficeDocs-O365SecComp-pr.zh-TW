---
title: 從封鎖清單移除使用者、 網域或 IP 位址傳送垃圾電子郵件之後
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/01/2018
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
ms.openlocfilehash: 0f58f9f2270c8be38b3ea2ea81f04656eb10e7fb
ms.sourcegitcommit: 83406a3258e722020e46a82bbf4bc9d5d8a326ca
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/01/2018
ms.locfileid: "25899654"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a><span data-ttu-id="31501-103">從封鎖清單移除使用者、 網域或 IP 位址傳送垃圾電子郵件之後</span><span class="sxs-lookup"><span data-stu-id="31501-103">Removing a user, domain, or IP address from a block list after sending spam email</span></span>

<span data-ttu-id="31501-p101">如果使用者持續傳送電子郵件訊息從歸類為垃圾郵件的 Office 365，他們會封鎖傳送任何詳細訊息。使用者將會列在為損壞的撥出寄件者的服務，也會收到未傳遞報告 (NDR) 表示：</span><span class="sxs-lookup"><span data-stu-id="31501-p101">If a user continuously sends email messages from Office 365 that is classified as spam, they will be blocked from sending any more messages. The user will be listed in the service as a bad outbound sender and will receive a Non-Delivery Report (NDR) that states:</span></span>

- <span data-ttu-id="31501-p102">因為未被視為有效的寄件者無法傳遞郵件。最常見原因是您的電子郵件地址可疑的垃圾郵件的傳送和它已不再允許傳送到組織外的郵件。如需協助連絡電子郵件系統。 遠端伺服器傳回 '550 5.1.8 「 拒絕存取 」、 損壞的撥出寄件者 」</span><span class="sxs-lookup"><span data-stu-id="31501-p102">Your message couldn't be delivered because you weren't recognized as a valid sender. The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send messages outside of your organization. Contact your email admin for assistance.  Remote Server returned '550 5.1.8 Access denied, bad outbound sender'</span></span>

<span data-ttu-id="31501-p103">您可以設定您的輸出垃圾郵件原則設定，讓您在 Office 365 使用者禁止傳送電子郵件時收到通知。與使用者的信箱問題已解決之後，您可以移除該寄件者在區塊。</span><span class="sxs-lookup"><span data-stu-id="31501-p103">You can configure your outbound spam policy settings so that you get a notification when an Office 365 user is blocked from sending email. After the problem with the user's mailbox is resolved, you can remove the block on that sender.</span></span>
  
## <a name="unblock-a-blocked-office-365-email-account"></a><span data-ttu-id="31501-112">解除封鎖封鎖的 Office 365 電子郵件帳戶</span><span class="sxs-lookup"><span data-stu-id="31501-112">Unblock a blocked Office 365 email account</span></span>

<span data-ttu-id="31501-p104">您完成此工作中的 Office 365 的安全性與規範中心 」 (SCC)。如需詳細資訊 SCC [[移至 [Office 365 安全性及規範中心](go-to-the-securitycompliance-center.md)]。</span><span class="sxs-lookup"><span data-stu-id="31501-p104">You complete this task in the Office 365 Security & Compliance Center (SCC). [Go to the Office 365 Security & Compliance Center](go-to-the-securitycompliance-center.md) for more details about SCC.</span></span>

1. <span data-ttu-id="31501-115">使用工作或學校的帳戶具備 Office 365 全域管理員權限，登入 Office 365 安全性和規範中心及在左側清單中，依序展開 [ **Threat Management**，並選擇 [**檢閱**，然後選擇 [**限制使用者**。</span><span class="sxs-lookup"><span data-stu-id="31501-115">Using a work or school account that has Office 365 global administrator privileges, sign into the Office 365 Security and Compliance Center and in the list on the left, expand **Threat Management**, choose **Review**, and then choose **Restricted Users**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="31501-116">若要直接移至**受限制的使用者**] 頁面 （前身為巨集指令中心） 安全性&amp;規範中心使用此 URL: >[https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span><span class="sxs-lookup"><span data-stu-id="31501-116">To go directly to the **Restricted Users** page (formerly known as the Action Center) in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span></span>

2. <span data-ttu-id="31501-p105">此頁面可包含被封鎖傳送郵件給組織外的使用者清單。 尋找您想要移除限制上，然後按一下 [**解除**的使用者。</span><span class="sxs-lookup"><span data-stu-id="31501-p105">This page will contain the list of users that have been blocked from sending mail to outside of your organization.  Find the user you wish to remove restrictions on and then click on **Unblock**.</span></span>

3. <span data-ttu-id="31501-119">按一下 [**是]** 確認變更。</span><span class="sxs-lookup"><span data-stu-id="31501-119">Click **Yes** to confirm the change.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="31501-p106">有限制的帳戶可以解除封鎖承租人管理員的次數如果已超過此限制的使用者，就會出現錯誤訊息。然後您必須連絡支援人員以解除封鎖使用者。</span><span class="sxs-lookup"><span data-stu-id="31501-p106">There's a limit to the number of times that an account can be unblocked by the tenant admin. If the limit for a user has been exceeded, an error message appears. You will then need to contact Support to unblock the user.</span></span></br></br> <span data-ttu-id="31501-122">可能需要多達 1 小時之前使用者不封鎖。</span><span class="sxs-lookup"><span data-stu-id="31501-122">It may take up to 1 hour before the user is unblocked.</span></span>
  
## <a name="third-party-block-lists"></a><span data-ttu-id="31501-123">協力廠商封鎖清單</span><span class="sxs-lookup"><span data-stu-id="31501-123">Third-party block lists</span></span>

<span data-ttu-id="31501-p107">Exchange Online Protection 也會使用第三方封鎖清單來提升決策的垃圾郵件篩選。使用者、 網站、 網域及 IP 位址可以新增要封鎖只是為了垃圾郵件訊息中出現的清單。為 Office 365 系統管理員應該嘗試取得如果所屬您移除的協力廠商清單提供者從這些物件。</span><span class="sxs-lookup"><span data-stu-id="31501-p107">Exchange Online Protection also uses third-party block lists to help make decisions in spam filtering. Users, websites, domains, and IP addresses can be added to block lists just for appearing in a spam message. As the Office 365 admin, you should try to get these objects removed from the third-party list providers if they belong to you.</span></span>

> [!NOTE]
> <span data-ttu-id="31501-p108">如果 Office 365 外的某個人無法將郵件傳送至您的 Office 365 帳戶，其帳戶可能會在外部封鎖的寄件者清單。Office 365 外部的使用者可以嘗試使用[自助取消列出的入口網站](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis)中移除其本身。</span><span class="sxs-lookup"><span data-stu-id="31501-p108">If someone outside Office 365 cannot send messages to your Office 365 account, their account may be on the external blocked senders list. Users outside Office 365 can try to remove themselves by using the [self-service delisting portal](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis).</span></span> 

## <a name="for-more-information"></a><span data-ttu-id="31501-129">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="31501-129">For more information</span></span>

[<span data-ttu-id="31501-130">回應洩漏電子郵件帳戶</span><span class="sxs-lookup"><span data-stu-id="31501-130">Responding to a compromised email account</span></span>](responding-to-a-compromised-email-account.md)

[<span data-ttu-id="31501-131">設定輸出垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="31501-131">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="31501-132">外寄郵件的高風險傳遞集區</span><span class="sxs-lookup"><span data-stu-id="31501-132">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

  

  

