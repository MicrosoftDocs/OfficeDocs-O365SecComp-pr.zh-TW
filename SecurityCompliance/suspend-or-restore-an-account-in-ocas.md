---
title: 暫停或還原 Office 365 雲端 App 安全性中的使用者帳戶
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/03/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5f02d20f-b9aa-4b2f-ad2d-506a4a3c4540
description: 'Office 365 雲端 App 安全性，您可以採取的控管動作有擱置或 unsuspend 的使用者帳戶。 '
ms.openlocfilehash: d162be9d4e5382c6c03c63ae1b30043edbf0295b
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32260304"
---
# <a name="suspend-or-restore-a-user-account-in-office-365-cloud-app-security"></a><span data-ttu-id="b71f6-103">暫停或還原 Office 365 雲端 App 安全性中的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="b71f6-103">Suspend or restore a user account in Office 365 Cloud App Security</span></span>

|<span data-ttu-id="b71f6-104">評估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="b71f6-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="b71f6-105">規劃 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="b71f6-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="b71f6-106">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="b71f6-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="b71f6-107">使用率 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="b71f6-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="b71f6-108">啟動評估</span><span class="sxs-lookup"><span data-stu-id="b71f6-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="b71f6-109">開始規劃</span><span class="sxs-lookup"><span data-stu-id="b71f6-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="b71f6-110">開始部署</span><span class="sxs-lookup"><span data-stu-id="b71f6-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="b71f6-111">您在此處 ！</span><span class="sxs-lookup"><span data-stu-id="b71f6-111">You are here!</span></span>  <br/> [<span data-ttu-id="b71f6-112">後續步驟</span><span class="sxs-lookup"><span data-stu-id="b71f6-112">Next steps</span></span>](#next-steps)<br/> |
   
<span data-ttu-id="b71f6-113">假設您收到警示的 Office 365 組織的使用者帳戶的其中一個已遭洩露。</span><span class="sxs-lookup"><span data-stu-id="b71f6-113">Suppose that you receive an alert that one of your organization's user accounts for Office 365 has been compromised.</span></span> <span data-ttu-id="b71f6-114">或者，假設您收到警示，指出有問題的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="b71f6-114">Or, suppose that you've received an alert that indicates something is wrong with a user account.</span></span> <span data-ttu-id="b71f6-115">與 Office 365 雲端 App 安全性，您可以暫停的使用者帳戶，並稍後再將它還原後已經調查您收到的警示。</span><span class="sxs-lookup"><span data-stu-id="b71f6-115">With Office 365 Cloud App Security, you can suspend a user account and later restore it after you have investigated the alerts you receive.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b71f6-116">Office 365 雲端 App 安全性是在 Office 365 企業版 E5。</span><span class="sxs-lookup"><span data-stu-id="b71f6-116">Office 365 Cloud App Security is available in Office 365 Enterprise E5.</span></span> <span data-ttu-id="b71f6-117">如果您的組織要使用另一個 Office 365 企業版訂閱，能以附加元件形式購買 Office 365 雲端 App 安全性。</span><span class="sxs-lookup"><span data-stu-id="b71f6-117">If your organization is using another Office 365 Enterprise subscription, Office 365 Cloud App Security can be purchased as an add-on.</span></span> <span data-ttu-id="b71f6-118">(以全域管理員，在 Microsoft 365 系統管理中心中，選擇 [**計費** \> **新增訂閱**。)如需詳細資訊，請參閱[Office 365 平台服務說明： Office 365 安全性&amp;合規性中心](https://technet.microsoft.com/en-us/library/dn933793.aspx)並[購買或編輯商務用 Office 365 的附加元件](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6)。</span><span class="sxs-lookup"><span data-stu-id="b71f6-118">(As a global administrator, in the Microsoft 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://technet.microsoft.com/en-us/library/dn933793.aspx) and [Buy or edit an add-on for Office 365 for business](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span></span> 
  
## <a name="to-suspend-a-user-account-in-office-365-cloud-app-security"></a><span data-ttu-id="b71f6-119">若要擱置 Office 365 雲端 App 安全性中的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="b71f6-119">To suspend a user account in Office 365 Cloud App Security</span></span>

<span data-ttu-id="b71f6-120">當您暫停的使用者帳戶時，您會防止使用者再次登入。</span><span class="sxs-lookup"><span data-stu-id="b71f6-120">When you suspend a user account, you prevent the user from signing in again.</span></span> <span data-ttu-id="b71f6-121">它是與編輯直接在若要將登入狀態設為**登入已封鎖**的 Office 365 中的使用者帳戶相同。</span><span class="sxs-lookup"><span data-stu-id="b71f6-121">It's the same as editing the user account directly in Office 365 to set the Sign-in status to **Sign-in blocked**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b71f6-122">如果您封鎖使用者登入 Office 365，以暫停它們或編輯其登入狀態，請注意，可能需要一小時或動作才能生效的所有使用者的裝置和用戶端 （[編輯或變更 Office 365 中的使用者](https://support.office.com/article/42BB3F17-8F9D-4182-B434-5F1C8024E614#SingleUserPreview)） 上。</span><span class="sxs-lookup"><span data-stu-id="b71f6-122">If you block a user from signing in to Office 365, either by suspending them or by editing their sign-in status, be aware that it can take an hour or so to take effect on all of the user's devices and clients ([Edit or change a user in Office 365](https://support.office.com/article/42BB3F17-8F9D-4182-B434-5F1C8024E614#SingleUserPreview)).</span></span> <span data-ttu-id="b71f6-123">如果使用者登入 Office 365 時，封鎖就會生效，每當 Office 365 需要再次登入。</span><span class="sxs-lookup"><span data-stu-id="b71f6-123">If the user is signed in to Office 365, the block will take effect whenever Office 365 requires them to sign in again.</span></span> 
  
1. <span data-ttu-id="b71f6-124">以[全域管理員或安全性系統管理員](permissions-in-the-security-and-compliance-center.md)，請移至[https://protection.office.com](https://protection.office.com)並使用您的公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="b71f6-124">As a [global administrator or security administrator](permissions-in-the-security-and-compliance-center.md), go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account.</span></span> <span data-ttu-id="b71f6-125">(這會帶您前往安全性&amp;合規性中心。)</span><span class="sxs-lookup"><span data-stu-id="b71f6-125">(This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="b71f6-126">安全性&amp;合規性中心，選擇 [**提醒** \> **管理進階提醒**。</span><span class="sxs-lookup"><span data-stu-id="b71f6-126">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="b71f6-127">選擇 [**移至 Office 365 雲端 App 安全性**。</span><span class="sxs-lookup"><span data-stu-id="b71f6-127">Choose **Go to Office 365 Cloud App Security**.</span></span><br><span data-ttu-id="b71f6-128">![安全性&amp;合規性中心，選擇 [管理進階提醒移至 Office 365 雲端 App 安全性](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span><span class="sxs-lookup"><span data-stu-id="b71f6-128">![In the Security &amp; Compliance Center, choose Manage Advanced Alerts to go to Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span></span><br>
  
4. <span data-ttu-id="b71f6-129">在跨螢幕頂端導覽列中，選擇 [**提醒**]。</span><span class="sxs-lookup"><span data-stu-id="b71f6-129">In the navigation bar across the top of the screen, choose **Alerts**.</span></span>
    
5. <span data-ttu-id="b71f6-130">在 [**提醒**] 欄中，連按兩下 [適用於特定的使用者帳戶的警示。</span><span class="sxs-lookup"><span data-stu-id="b71f6-130">In the **Alert** column, double-click an alert that pertains to a specific user account.</span></span> 
    
6. <span data-ttu-id="b71f6-131">**帳戶**] 下的 [在 [**狀態**] 欄中，選擇 [設定![設定] 圖示](media/e01b75cc-b28f-4b83-8f86-b1b13dc27ab2.png) \> **暫停使用者**。</span><span class="sxs-lookup"><span data-stu-id="b71f6-131">Under **Accounts**, in the **Status** column, choose Settings ![settings icon](media/e01b75cc-b28f-4b83-8f86-b1b13dc27ab2.png) \> **Suspend user**.</span></span>
    
## <a name="to-restore-a-user-account"></a><span data-ttu-id="b71f6-132">若要還原的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="b71f6-132">To restore a user account</span></span>

<span data-ttu-id="b71f6-133">請參閱[還原 Office 365 中的使用者](https://support.office.com/article/2c261e42-5dd1-48b0-845f-2a016d29cfc1)</span><span class="sxs-lookup"><span data-stu-id="b71f6-133">See [Restore a user in Office 365](https://support.office.com/article/2c261e42-5dd1-48b0-845f-2a016d29cfc1)</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="b71f6-134">後續步驟</span><span class="sxs-lookup"><span data-stu-id="b71f6-134">Next steps</span></span>

- [<span data-ttu-id="b71f6-135">檢閱並對 Office 365 雲端 App 安全性中的警示採取動作</span><span class="sxs-lookup"><span data-stu-id="b71f6-135">Review and take action on alerts in Office 365 Cloud App Security</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="b71f6-136">使用 Office 365 雲端 App 安全性管理 OAuth 應用程式</span><span class="sxs-lookup"><span data-stu-id="b71f6-136">Manage OAuth apps using Office 365 Cloud App Security</span></span>](manage-app-permissions-in-ocas.md)
    
- <span data-ttu-id="b71f6-137">檢閱您[的 Office 365 雲端 App 安全性的使用率活動](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="b71f6-137">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

