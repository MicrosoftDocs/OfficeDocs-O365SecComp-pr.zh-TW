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
description: 如果使用者持續傳送電子郵件從 Office 365 歸類為垃圾郵件，他們將會傳送任何更多的郵件限制。
ms.openlocfilehash: 7a44ff7f2bcf88f2132ee4c372cc11b9657dd16a
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34157245"
---
# <a name="removing-a-user-from-the-restricted-users-portal-after-sending-spam-email"></a><span data-ttu-id="9f523-103">傳送垃圾電子郵件之後，從限制的使用者入口網站移除使用者</span><span class="sxs-lookup"><span data-stu-id="9f523-103">Removing a user from the Restricted Users portal after sending spam email</span></span>

<span data-ttu-id="9f523-104">如果使用者持續傳送電子郵件從 Office 365 歸類為垃圾郵件，他們會被限制傳送輸出任何更多的郵件。</span><span class="sxs-lookup"><span data-stu-id="9f523-104">If a user continuously sends emails from Office 365 that are classified as spam, they will be restricted from sending any more messages outbound.</span></span> <span data-ttu-id="9f523-105">使用者會列在 [為不正確的輸出寄件者的服務，並將會收到未傳遞回報 (NDR) 表示：</span><span class="sxs-lookup"><span data-stu-id="9f523-105">The user will be listed in the service as a bad outbound sender and will receive a Non-Delivery Report (NDR) that states:</span></span>

- <span data-ttu-id="9f523-106">無法傳遞郵件，因為未辨識為有效的寄件者。</span><span class="sxs-lookup"><span data-stu-id="9f523-106">Your message couldn't be delivered because you weren't recognized as a valid sender.</span></span> <span data-ttu-id="9f523-107">最常見原因是您的電子郵件地址可疑的傳送垃圾郵件，且不再具有允許傳送組織以外的郵件。</span><span class="sxs-lookup"><span data-stu-id="9f523-107">The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send messages outside of your organization.</span></span> <span data-ttu-id="9f523-108">請連絡您的電子郵件系統管理員以尋求協助。</span><span class="sxs-lookup"><span data-stu-id="9f523-108">Contact your email admin for assistance.</span></span> <span data-ttu-id="9f523-109">遠端伺服器傳回 550 5.1.8 拒絕存取，不正確的輸出寄件者 」</span><span class="sxs-lookup"><span data-stu-id="9f523-109">Remote Server returned '550 5.1.8 Access denied, bad outbound sender'</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9f523-110">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="9f523-110">What do you need to know before you begin?</span></span>
<span data-ttu-id="9f523-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="9f523-111"></span></span>

<span data-ttu-id="9f523-112">預估完成時間：5 分鐘</span><span class="sxs-lookup"><span data-stu-id="9f523-112">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="9f523-113">您必須已獲指派權限，才能執行此程序或這些程序。</span><span class="sxs-lookup"><span data-stu-id="9f523-113">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="9f523-114">若要查看您需要哪些權限，請參閱 「 反垃圾郵件中的項目[Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主題。</span><span class="sxs-lookup"><span data-stu-id="9f523-114">To see what permissions you need, see the "Anti-spam entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span>

<span data-ttu-id="9f523-115">您也可以透過遠端 PowerShell 執行下列程序。</span><span class="sxs-lookup"><span data-stu-id="9f523-115">The following procedure can also be performed via remote PowerShell.</span></span> <span data-ttu-id="9f523-116">使用 Get-BlockedSenderAddress 指令程式來取得受限的使用者和移除 BlockedSenderAddress 若要移除限制的清單。</span><span class="sxs-lookup"><span data-stu-id="9f523-116">Use the Get-BlockedSenderAddress cmdlet to get the list of restricted users and Remove-BlockedSenderAddress to remove the restriction.</span></span> <span data-ttu-id="9f523-117">若要了解如何使用 Windows PowerShell 連線到 Exchange Online，請參閱[連線到 Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="9f523-117">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

## <a name="remove-restrictions-for-a-blocked-office-365-email-account"></a><span data-ttu-id="9f523-118">移除封鎖的 Office 365 電子郵件帳戶的限制</span><span class="sxs-lookup"><span data-stu-id="9f523-118">Remove restrictions for a blocked Office 365 email account</span></span>

<span data-ttu-id="9f523-119">您完成此工作中的安全性 & 合規性中心 (SCC)。</span><span class="sxs-lookup"><span data-stu-id="9f523-119">You complete this task in the Security & Compliance Center (SCC).</span></span> <span data-ttu-id="9f523-120">如需詳細資訊 SCC [[移至安全性 & 合規性中心](go-to-the-securitycompliance-center.md)]。</span><span class="sxs-lookup"><span data-stu-id="9f523-120">[Go to the Security & Compliance Center](go-to-the-securitycompliance-center.md) for more details about SCC.</span></span> <span data-ttu-id="9f523-121">您必須是在**組織管理**」 或 「**安全性系統管理員**角色群組中，才能執行這些功能。</span><span class="sxs-lookup"><span data-stu-id="9f523-121">You need to be in the **Organization Management** or the **Security Administrator** role group in order to perform these functions.</span></span> <span data-ttu-id="9f523-122">如需詳細資訊 SCC 角色群組的 [[移至安全性 & 合規性中心中的權限](permissions-in-the-security-and-compliance-center.md)]。</span><span class="sxs-lookup"><span data-stu-id="9f523-122">[Go to Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) for more details about SCC role groups.</span></span>

1. <span data-ttu-id="9f523-123">使用公司或學校帳戶具有 Office 365 全域系統管理員權限，登入 Office 365 安全與規範中心和在左側清單中，展開 [**威脅管理**，選擇 [**檢閱**，，然後選擇 [**限制使用者**。</span><span class="sxs-lookup"><span data-stu-id="9f523-123">Using a work or school account that has Office 365 global administrator privileges, sign into the Office 365 Security and Compliance Center and in the list on the left, expand **Threat Management**, choose **Review**, and then choose **Restricted Users**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="9f523-124">若要直接前往**受限的使用者**」 （前身為重要訊息中心） 安全性&amp;合規性中心，使用下列 URL: >[https://protection.office.com/#/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span><span class="sxs-lookup"><span data-stu-id="9f523-124">To go directly to the **Restricted Users** page (formerly known as the Action Center) in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/#/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span></span>

2. <span data-ttu-id="9f523-125">此頁面將包含已封鎖而無法傳送郵件給組織外的使用者清單。</span><span class="sxs-lookup"><span data-stu-id="9f523-125">This page will contain the list of users that have been blocked from sending mail to outside of your organization.</span></span>  <span data-ttu-id="9f523-126">尋找您想要移除限制上，然後按一下**解除封鎖**使用者。</span><span class="sxs-lookup"><span data-stu-id="9f523-126">Find the user you wish to remove restrictions on and then click on **Unblock**.</span></span>

3. <span data-ttu-id="9f523-127">飛出視窗就會進入其傳送屬於受限帳戶的相關詳細資料。</span><span class="sxs-lookup"><span data-stu-id="9f523-127">A fly-out will go into the details about the account whose sending is restricted.</span></span> <span data-ttu-id="9f523-128">您應經過建議，以確定您採取適當的動作，以防帳戶實際上入侵。</span><span class="sxs-lookup"><span data-stu-id="9f523-128">You should go through the recommendations to ensure you're taking the proper actions in case the account is actually compromised.</span></span> <span data-ttu-id="9f523-129">按 [**下一步**完成。</span><span class="sxs-lookup"><span data-stu-id="9f523-129">Click **Next** when done.</span></span>

4. <span data-ttu-id="9f523-130">下一個畫面中有建議，以協助防範未來的危害。</span><span class="sxs-lookup"><span data-stu-id="9f523-130">The next screen has recommendations to help prevent future compromise.</span></span> <span data-ttu-id="9f523-131">啟用多重要素驗證 (MFA) 和變更密碼是很好的防護。</span><span class="sxs-lookup"><span data-stu-id="9f523-131">Enabling multi-factor authentication (MFA) and changing the passwords are a good defense.</span></span> <span data-ttu-id="9f523-132">按一下 **[解除封鎖使用者**完成。</span><span class="sxs-lookup"><span data-stu-id="9f523-132">Click **Unblock user** when done.</span></span>

5. <span data-ttu-id="9f523-133">按一下 [ **]** 確認變更。</span><span class="sxs-lookup"><span data-stu-id="9f523-133">Click **Yes** to confirm the change.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9f523-134">可能需要 30 分鐘，限制會移除前。</span><span class="sxs-lookup"><span data-stu-id="9f523-134">It may take up to 30 minutes before restrictions are removed.</span></span> 

## <a name="making-sure-admins-are-alerted-when-this-happens"></a><span data-ttu-id="9f523-135">確定發生這種情況時，會收到通知系統管理員</span><span class="sxs-lookup"><span data-stu-id="9f523-135">Making sure admins are alerted when this happens</span></span>

<span data-ttu-id="9f523-136">租用戶系統管理員也會收到警告指出受限已傳送任何其他輸出的郵件使用者。</span><span class="sxs-lookup"><span data-stu-id="9f523-136">The tenant admins will also receive an alert stating that the user has been restricted from sending any more outbound messages.</span></span> <span data-ttu-id="9f523-137">它是預設警示，會提供給所有承租人，而列在 SCC 警示原則] 頁面上，標題為 「 限制使用者無法傳送電子郵件 」。</span><span class="sxs-lookup"><span data-stu-id="9f523-137">It is a default alert that is provided for all tenants and is listed in the SCC Alert policies page, titled "User restricted from sending email".</span></span> <span data-ttu-id="9f523-138">請移至[安全性 & 合規性中心中的警示原則](https://docs.microsoft.com/en-us/office365/securitycompliance/alert-policies)如需詳細資訊的警示。</span><span class="sxs-lookup"><span data-stu-id="9f523-138">Go to [Alert policies in the Security & Compliance Center](https://docs.microsoft.com/en-us/office365/securitycompliance/alert-policies) for more information on the alert.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="9f523-139">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="9f523-139">For more information</span></span>

[<span data-ttu-id="9f523-140">回應遭入侵電子郵件帳戶</span><span class="sxs-lookup"><span data-stu-id="9f523-140">Responding to a compromised email account</span></span>](responding-to-a-compromised-email-account.md)

[<span data-ttu-id="9f523-141">了解使用者傳送電子郵件警示限制</span><span class="sxs-lookup"><span data-stu-id="9f523-141">Understanding the User restricted from sending email alert</span></span>](https://docs.microsoft.com/en-us/office365/securitycompliance/alert-policies)

[<span data-ttu-id="9f523-142">高風險傳遞集區的外寄郵件</span><span class="sxs-lookup"><span data-stu-id="9f523-142">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="9f523-143">安全規範中心的權限</span><span class="sxs-lookup"><span data-stu-id="9f523-143">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
