---
title: 傳送垃圾電子郵件之後，從限制的使用者入口網站移除使用者
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 03/12/2019
audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: 如果使用者持續傳送的電子郵件來自 Office 365, 其分類為垃圾郵件, 則會限制傳送更多郵件。
ms.openlocfilehash: 3e05b250d5a3cdca79c7cf494b84be02ce3ecdc9
ms.sourcegitcommit: 5a93c2f3df35d06a59a7fbaff5c91f7afde11781
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/11/2019
ms.locfileid: "34857623"
---
# <a name="removing-a-user-from-the-restricted-users-portal-after-sending-spam-email"></a><span data-ttu-id="edd53-103">傳送垃圾電子郵件之後，從限制的使用者入口網站移除使用者</span><span class="sxs-lookup"><span data-stu-id="edd53-103">Removing a user from the Restricted Users portal after sending spam email</span></span>

<span data-ttu-id="edd53-104">如果使用者持續傳送的電子郵件被分類為來自 Office 365 的垃圾郵件, 它們將會受到限制, 無法傳送電子郵件, 但仍然可以接收電子郵件。</span><span class="sxs-lookup"><span data-stu-id="edd53-104">If a user continuously sends emails that are classified as spam from Office 365, they will be restricted from sending email, but will still be able to receive it.</span></span> <span data-ttu-id="edd53-105">使用者會被列為錯誤的輸出寄件者, 且會收到未傳遞回報 (NDR), 其狀態為:</span><span class="sxs-lookup"><span data-stu-id="edd53-105">The user will be listed in the service as a bad outbound sender and will receive a Non-Delivery Report (NDR) that states:</span></span>

> <span data-ttu-id="edd53-106">[您的郵件無法傳遞, 因為您未被識別為有效的寄件者。</span><span class="sxs-lookup"><span data-stu-id="edd53-106">"Your message couldn't be delivered because you weren't recognized as a valid sender.</span></span> <span data-ttu-id="edd53-107">最常見的原因是您的電子郵件地址可能會傳送垃圾郵件, 而且不再允許傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="edd53-107">The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send email.</span></span>  <span data-ttu-id="edd53-108">請洽詢您的電子郵件系統管理員以取得協助。</span><span class="sxs-lookup"><span data-stu-id="edd53-108">Contact  your email admin for assistance.</span></span> <span data-ttu-id="edd53-109">遠端伺服器傳回 ' 550 5.1.8 拒絕存取, 錯誤的輸出寄件者」。</span><span class="sxs-lookup"><span data-stu-id="edd53-109">Remote Server returned '550 5.1.8 Access denied, bad outbound sender."</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="edd53-110">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="edd53-110">What do you need to know before you begin?</span></span>
<span data-ttu-id="edd53-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="edd53-111"></span></span>

<span data-ttu-id="edd53-112">預估完成時間：5 分鐘</span><span class="sxs-lookup"><span data-stu-id="edd53-112">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="edd53-113">您必須已獲指派權限，才能執行此程序或這些程序。</span><span class="sxs-lookup"><span data-stu-id="edd53-113">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="edd53-114">若要查看您需要的許可權, 請參閱[Exchange Online 中的功能許可權](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主題中的「反垃圾郵件」專案。</span><span class="sxs-lookup"><span data-stu-id="edd53-114">To see what permissions you need, see the "Anti-spam entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span>

<span data-ttu-id="edd53-115">您也可以透過遠端 PowerShell 執行下列程式。</span><span class="sxs-lookup"><span data-stu-id="edd53-115">The following procedure can also be performed via remote PowerShell.</span></span> <span data-ttu-id="edd53-116">使用 BlockedSenderAddress 指令程式來取得受限制的使用者清單, 並移除-BlockedSenderAddress 以移除限制。</span><span class="sxs-lookup"><span data-stu-id="edd53-116">Use the Get-BlockedSenderAddress cmdlet to get the list of restricted users and Remove-BlockedSenderAddress to remove the restriction.</span></span> <span data-ttu-id="edd53-117">若要了解如何使用 Windows PowerShell 連線到 Exchange Online，請參閱[連線到 Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="edd53-117">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

## <a name="remove-restrictions-for-a-blocked-office-365-email-account"></a><span data-ttu-id="edd53-118">移除封鎖的 Office 365 電子郵件帳戶限制</span><span class="sxs-lookup"><span data-stu-id="edd53-118">Remove restrictions for a blocked Office 365 email account</span></span>

<span data-ttu-id="edd53-119">您可以在安全性 & 規範中心 (SCC) 中完成這項工作。</span><span class="sxs-lookup"><span data-stu-id="edd53-119">You complete this task in the Security & Compliance Center (SCC).</span></span> <span data-ttu-id="edd53-120">[請移至安全性 & 合規性中心](go-to-the-securitycompliance-center.md), 以取得有關 SCC 的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="edd53-120">[Go to the Security & Compliance Center](go-to-the-securitycompliance-center.md) for more details about SCC.</span></span> <span data-ttu-id="edd53-121">您必須在「**組織管理**」或「**安全性系統管理員**」角色群組中, 才能執行這些功能。</span><span class="sxs-lookup"><span data-stu-id="edd53-121">You need to be in the **Organization Management** or the **Security Administrator** role group in order to perform these functions.</span></span> <span data-ttu-id="edd53-122">[請移至安全性 & 規範中心的許可權](permissions-in-the-security-and-compliance-center.md), 以取得 SCC 角色群組的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="edd53-122">[Go to Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) for more details about SCC role groups.</span></span>

1. <span data-ttu-id="edd53-123">使用具有 Office 365 全域系統管理員許可權的公司或學校帳戶, 登入 Office 365 安全性和合規性中心, 並在左清單中, 展開 [**威脅管理**], 選擇 [**檢查**], 然後選擇 [限制]。 **使用者**。</span><span class="sxs-lookup"><span data-stu-id="edd53-123">Using a work or school account that has Office 365 global administrator privileges, sign into the Office 365 Security and Compliance Center and in the list on the left, expand **Threat Management**, choose **Review**, and then choose **Restricted Users**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="edd53-124">若要直接移至安全性&amp;與合規性中心中的 [**受限制的使用者**] 頁面 (先前稱為「重要訊息中心」), 請使用下列 URL: >[https://protection.office.com/#/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span><span class="sxs-lookup"><span data-stu-id="edd53-124">To go directly to the **Restricted Users** page (formerly known as the Action Center) in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/#/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span></span>

2. <span data-ttu-id="edd53-125">此頁面將包含已封鎖的使用者清單, 而這些使用者已被封鎖傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="edd53-125">This page will contain the list of users that have been blocked from sending email.</span></span>  <span data-ttu-id="edd53-126">找出您想要移除限制的使用者, 然後選取 [**解除封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="edd53-126">Find the user you wish to remove restrictions from, and select **Unblock**.</span></span>

3. <span data-ttu-id="edd53-127">飛出將會進入限制傳送之帳戶的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="edd53-127">A fly-out will go into the details about the account whose sending is restricted.</span></span> <span data-ttu-id="edd53-128">您應該仔細瞭解建議, 以確保當帳戶實際受到危害時, 您會採取適當的動作。</span><span class="sxs-lookup"><span data-stu-id="edd53-128">You should go through the recommendations to ensure you're taking the proper actions in case the account is actually compromised.</span></span> <span data-ttu-id="edd53-129">完成後按 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="edd53-129">Click **Next** when done.</span></span>

4. <span data-ttu-id="edd53-130">下一個畫面有協助防止未來受到危害的建議。</span><span class="sxs-lookup"><span data-stu-id="edd53-130">The next screen has recommendations to help prevent future compromise.</span></span> <span data-ttu-id="edd53-131">啟用多重要素驗證 (MFA) 和變更密碼是一種很好的防護措施。</span><span class="sxs-lookup"><span data-stu-id="edd53-131">Enabling multi-factor authentication (MFA) and changing the passwords are a good defense.</span></span> <span data-ttu-id="edd53-132">按一下 [**解除封鎖使用者**完成時]。</span><span class="sxs-lookup"><span data-stu-id="edd53-132">Click **Unblock user** when done.</span></span>

5. <span data-ttu-id="edd53-133">按一下 **[是]** 以確認變更。</span><span class="sxs-lookup"><span data-stu-id="edd53-133">Click **Yes** to confirm the change.</span></span>

    > [!NOTE]
    > <span data-ttu-id="edd53-134">在移除限制之前, 可能需要30分鐘或更多時間。</span><span class="sxs-lookup"><span data-stu-id="edd53-134">It may take 30 minutes or more before restrictions are removed.</span></span> 

## <a name="making-sure-admins-are-alerted-when-this-happens"></a><span data-ttu-id="edd53-135">確保系統管理員在發生這種情況時收到警告</span><span class="sxs-lookup"><span data-stu-id="edd53-135">Making sure admins are alerted when this happens</span></span>

<span data-ttu-id="edd53-136">在 [Office 365 安全性 & 合規性警示原則] 頁面下, 以原則提供「限制傳送電子郵件的使用者」警示。</span><span class="sxs-lookup"><span data-stu-id="edd53-136">A "User restricted from sending email" alert is available as a policy under the Office 365 Security & Compliance Alert policies page.</span></span> <span data-ttu-id="edd53-137">這是先前的輸出垃圾郵件原則, 但現在是 Office 365 警示平臺的本機。</span><span class="sxs-lookup"><span data-stu-id="edd53-137">This was formerly the outbound spam policy but is now native to the Office 365 alerting platform.</span></span> <span data-ttu-id="edd53-138">請移至[安全性 & 合規性中心內的警示原則](alert-policies.md), 以取得警告的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="edd53-138">Go to [Alert policies in the Security & Compliance Center](alert-policies.md) for more information on alerts.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="edd53-139">若要讓警示正常運作, 必須開啟 audit log search。</span><span class="sxs-lookup"><span data-stu-id="edd53-139">For alerts to work, audit log search must to be turned on.</span></span> <span data-ttu-id="edd53-140">如需詳細資訊, 請參閱如何[開啟或關閉 Office 365 的審核記錄搜尋](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="edd53-140">See how to [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md) for more information.</span></span>

<span data-ttu-id="edd53-141">此警示的原則是預設值, 並隨附每個 Office 365 租使用者, 而且不需要設定。</span><span class="sxs-lookup"><span data-stu-id="edd53-141">The policy for this alert is a default one and comes with every Office 365 tenant and does not need to be set up.</span></span> <span data-ttu-id="edd53-142">當使用者限制傳送郵件時, 會將此警告視為高嚴重性警示, 並將電子郵件傳送給已設定的 TenantAdmins 群組。</span><span class="sxs-lookup"><span data-stu-id="edd53-142">It is considered a High severity alert and will email the configured TenantAdmins group when the alert is fired whenever a user has been restricted from sending mail.</span></span> <span data-ttu-id="edd53-143">系統管理員可以使用 SCC 入口網站的警示來更新群組, > 警示 > 警示原則, > 使用者限制傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="edd53-143">Admins can update the group notified when this alert happens by going to the alert under the SCC portal > Alerts > Alert policies > Users restricted from sending email.</span></span>

<span data-ttu-id="edd53-144">您可以將警示編輯為:</span><span class="sxs-lookup"><span data-stu-id="edd53-144">You will be able to Edit the alert to:</span></span>
- <span data-ttu-id="edd53-145">開啟/關閉電子郵件通知</span><span class="sxs-lookup"><span data-stu-id="edd53-145">Turn email notifications On/Off</span></span>
- <span data-ttu-id="edd53-146">傳送所需收件者的電子郵件</span><span class="sxs-lookup"><span data-stu-id="edd53-146">Email the required recipients</span></span>
- <span data-ttu-id="edd53-147">限制您每天取得的通知</span><span class="sxs-lookup"><span data-stu-id="edd53-147">Limit the notifications you get per day</span></span>

## <a name="for-more-information"></a><span data-ttu-id="edd53-148">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="edd53-148">For more information</span></span>

[<span data-ttu-id="edd53-149">回應受損的電子郵件帳戶</span><span class="sxs-lookup"><span data-stu-id="edd53-149">Responding to a compromised email account</span></span>](responding-to-a-compromised-email-account.md)

[<span data-ttu-id="edd53-150">瞭解使用者限制傳送電子郵件警示</span><span class="sxs-lookup"><span data-stu-id="edd53-150">Understanding the User restricted from sending email alert</span></span>](https://docs.microsoft.com/en-us/office365/securitycompliance/alert-policies)

[<span data-ttu-id="edd53-151">輸出郵件的高風險傳遞集區</span><span class="sxs-lookup"><span data-stu-id="edd53-151">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="edd53-152">安全規範中心的權限</span><span class="sxs-lookup"><span data-stu-id="edd53-152">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

[<span data-ttu-id="edd53-153">安全性 & 合規性中心內的警示原則</span><span class="sxs-lookup"><span data-stu-id="edd53-153">Alert policies in the Security & Compliance Center</span></span>](https://docs.microsoft.com/en-us/office365/securitycompliance/alert-policies)
