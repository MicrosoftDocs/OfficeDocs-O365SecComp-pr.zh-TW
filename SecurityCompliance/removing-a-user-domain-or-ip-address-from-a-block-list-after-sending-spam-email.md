---
title: 從封鎖清單移除使用者、 網域或 IP 位址傳送垃圾電子郵件之後
ms.author: tracyp
author: MSFTTracyP
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
ms.collection:
- M365-security-compliance
description: 如果使用者持續傳送電子郵件訊息從歸類為垃圾郵件的 Office 365，他們會封鎖傳送任何詳細訊息。
ms.openlocfilehash: 870e5eabca9e799dfca1e99846a5bfe845f65df4
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30275933"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a><span data-ttu-id="5cf0d-103">從封鎖清單移除使用者、 網域或 IP 位址傳送垃圾電子郵件之後</span><span class="sxs-lookup"><span data-stu-id="5cf0d-103">Removing a user, domain, or IP address from a block list after sending spam email</span></span>

<span data-ttu-id="5cf0d-p101">如果使用者持續傳送電子郵件訊息從歸類為垃圾郵件的 Office 365，他們會封鎖傳送任何詳細訊息。使用者將會列在為損壞的撥出寄件者的服務，也會收到未傳遞報告 (NDR) 表示：</span><span class="sxs-lookup"><span data-stu-id="5cf0d-p101">If a user continuously sends email messages from Office 365 that is classified as spam, they will be blocked from sending any more messages. The user will be listed in the service as a bad outbound sender and will receive a Non-Delivery Report (NDR) that states:</span></span>

- <span data-ttu-id="5cf0d-p102">因為未被視為有效的寄件者無法傳遞郵件。最常見原因是您的電子郵件地址可疑的垃圾郵件的傳送和它已不再允許傳送到組織外的郵件。如需協助連絡電子郵件系統。 遠端伺服器傳回 '550 5.1.8 「 拒絕存取 」、 損壞的撥出寄件者 」</span><span class="sxs-lookup"><span data-stu-id="5cf0d-p102">Your message couldn't be delivered because you weren't recognized as a valid sender. The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send messages outside of your organization. Contact your email admin for assistance.  Remote Server returned '550 5.1.8 Access denied, bad outbound sender'</span></span>

<span data-ttu-id="5cf0d-110">租用戶系統管理員也將會收到警告指出受限已傳送任何其他輸出的郵件使用者。</span><span class="sxs-lookup"><span data-stu-id="5cf0d-110">The tenant admins will also receive an alert stating that the user has been restricted from sending any more outbound messages.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5cf0d-111">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="5cf0d-111">What do you need to know before you begin?</span></span>
<span data-ttu-id="5cf0d-112"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="5cf0d-112"></span></span>

<span data-ttu-id="5cf0d-113">預估完成時間：5 分鐘</span><span class="sxs-lookup"><span data-stu-id="5cf0d-113">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="5cf0d-p103">您必須獲得權限才能執行此程序或程序。若您需要哪些權限，請參閱 「 反垃圾郵件項目[Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主題中。</span><span class="sxs-lookup"><span data-stu-id="5cf0d-p103">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Anti-spam entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span>

<span data-ttu-id="5cf0d-p104">您也可以透過遠端 PowerShell 執行下列程序。使用 Get BlockedSenderAddress 指令程式來取得受限制的使用者和 Remove-BlockedSenderAddress 若要移除限制的清單。若要了解如何使用 Windows PowerShell 連線至 Exchange Online，請參閱[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="5cf0d-p104">The following procedure can also be performed via remote PowerShell. Use the Get-BlockedSenderAddress cmdlet to get the list of restricted users and Remove-BlockedSenderAddress to remove the restriction. To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

## <a name="remove-restrictions-for-a-blocked-office-365-email-account"></a><span data-ttu-id="5cf0d-119">移除封鎖的 Office 365 電子郵件帳戶的限制</span><span class="sxs-lookup"><span data-stu-id="5cf0d-119">Remove restrictions for a blocked Office 365 email account</span></span>

<span data-ttu-id="5cf0d-p105">您完成這項工作的 Office 365 安全性 & 規範中心 」 (SCC)。如需詳細資訊 SCC [[移至 Office 365 安全性 & 規範中心](go-to-the-securitycompliance-center.md)]。您必須是**組織管理**或**安全性管理員**角色群組中，才能執行這些功能。如需詳細資訊 SCC 角色群組的 [[移至 Office 365 安全性 & 規範中心中的權限](permissions-in-the-security-and-compliance-center.md)]。</span><span class="sxs-lookup"><span data-stu-id="5cf0d-p105">You complete this task in the Office 365 Security & Compliance Center (SCC). [Go to the Office 365 Security & Compliance Center](go-to-the-securitycompliance-center.md) for more details about SCC. You need to be in the **Organization Management** or the **Security Administrator** role group in order to perform these functions. [Go to Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) for more details about SCC role groups.</span></span>

1. <span data-ttu-id="5cf0d-124">使用工作或學校的帳戶具備 Office 365 全域管理員權限，登入 Office 365 安全性和規範中心及在左側清單中，依序展開 [ **Threat Management**，並選擇 [**檢閱**，然後選擇 [**限制使用者**。</span><span class="sxs-lookup"><span data-stu-id="5cf0d-124">Using a work or school account that has Office 365 global administrator privileges, sign into the Office 365 Security and Compliance Center and in the list on the left, expand **Threat Management**, choose **Review**, and then choose **Restricted Users**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="5cf0d-125">若要直接移至**受限制的使用者**] 頁面 （前身為巨集指令中心） 安全性&amp;規範中心使用下列 URL： >[https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span><span class="sxs-lookup"><span data-stu-id="5cf0d-125">To go directly to the **Restricted Users** page (formerly known as the Action Center) in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span></span>

2. <span data-ttu-id="5cf0d-p106">此頁面可包含被封鎖傳送郵件給組織外的使用者清單。 尋找您想要移除限制上，然後按一下 [**解除**的使用者。</span><span class="sxs-lookup"><span data-stu-id="5cf0d-p106">This page will contain the list of users that have been blocked from sending mail to outside of your organization.  Find the user you wish to remove restrictions on and then click on **Unblock**.</span></span>

3. <span data-ttu-id="5cf0d-128">按一下 [**是]** 確認變更。</span><span class="sxs-lookup"><span data-stu-id="5cf0d-128">Click **Yes** to confirm the change.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="5cf0d-p107">有限制的帳戶可以解除封鎖承租人管理員的次數如果已超過此限制的使用者，就會出現錯誤訊息。然後您必須連絡支援人員以解除封鎖使用者。</span><span class="sxs-lookup"><span data-stu-id="5cf0d-p107">There's a limit to the number of times that an account can be unblocked by the tenant admin. If the limit for a user has been exceeded, an error message appears. You will then need to contact Support to unblock the user.</span></span><br/><br/> <span data-ttu-id="5cf0d-131">可能需要多達 1 小時之前使用者不封鎖。</span><span class="sxs-lookup"><span data-stu-id="5cf0d-131">It may take up to 1 hour before the user is unblocked.</span></span>
  
## <a name="third-party-block-lists"></a><span data-ttu-id="5cf0d-132">協力廠商封鎖清單</span><span class="sxs-lookup"><span data-stu-id="5cf0d-132">Third-party block lists</span></span>

<span data-ttu-id="5cf0d-p108">Exchange Online Protection 也會使用第三方封鎖清單來提升決策的垃圾郵件篩選。使用者、 網站、 網域及 IP 位址可以新增要封鎖只是為了垃圾郵件訊息中出現的清單。為 Office 365 系統管理員應該嘗試取得如果所屬您移除的協力廠商清單提供者從這些物件。</span><span class="sxs-lookup"><span data-stu-id="5cf0d-p108">Exchange Online Protection also uses third-party block lists to help make decisions in spam filtering. Users, websites, domains, and IP addresses can be added to block lists just for appearing in a spam message. As the Office 365 admin, you should try to get these objects removed from the third-party list providers if they belong to you.</span></span>

> [!NOTE]
> <span data-ttu-id="5cf0d-p109">如果 Office 365 外的某個人無法將郵件傳送至您的 Office 365 帳戶，其帳戶可能會在外部封鎖的寄件者清單。Office 365 外部的使用者可以嘗試使用[自助取消列出的入口網站](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis)中移除其本身。</span><span class="sxs-lookup"><span data-stu-id="5cf0d-p109">If someone outside Office 365 cannot send messages to your Office 365 account, their account may be on the external blocked senders list. Users outside Office 365 can try to remove themselves by using the [self-service delisting portal](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis).</span></span> 

## <a name="for-more-information"></a><span data-ttu-id="5cf0d-138">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="5cf0d-138">For more information</span></span>

[<span data-ttu-id="5cf0d-139">回應洩漏電子郵件帳戶</span><span class="sxs-lookup"><span data-stu-id="5cf0d-139">Responding to a compromised email account</span></span>](responding-to-a-compromised-email-account.md)

[<span data-ttu-id="5cf0d-140">設定輸出垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="5cf0d-140">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="5cf0d-141">外寄郵件的高風險傳遞集區</span><span class="sxs-lookup"><span data-stu-id="5cf0d-141">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="5cf0d-142">在 Office 365 安全性 & 規範中心的權限</span><span class="sxs-lookup"><span data-stu-id="5cf0d-142">Permissions in the Office 365 Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

  

