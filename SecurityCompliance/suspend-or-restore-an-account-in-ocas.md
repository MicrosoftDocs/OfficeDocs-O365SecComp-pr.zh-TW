---
title: 暫停或還原 Office 365 雲端 App 安全性中的使用者帳戶
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/26/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5f02d20f-b9aa-4b2f-ad2d-506a4a3c4540
description: '與 Office 365 雲端應用程式安全性]，可採取的控管動作會暫停或 unsuspend 的使用者帳戶。 '
ms.openlocfilehash: a5c75edefc6ddb87b5676c4253aafe04817f6a1d
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526346"
---
# <a name="suspend-or-restore-a-user-account-in-office-365-cloud-app-security"></a><span data-ttu-id="7747c-103">暫停或還原 Office 365 雲端 App 安全性中的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="7747c-103">Suspend or restore a user account in Office 365 Cloud App Security</span></span>

<span data-ttu-id="7747c-104">Office 365 進階安全性管理現在是 Office 365 雲端應用程式安全性。</span><span class="sxs-lookup"><span data-stu-id="7747c-104">Office 365 Advanced Security Management is now Office 365 Cloud App Security.</span></span>
  
|<span data-ttu-id="7747c-105">評估 * *\>**</span><span class="sxs-lookup"><span data-stu-id="7747c-105">****Evaluation** \>**</span></span>|<span data-ttu-id="7747c-106">規劃 * *\>**</span><span class="sxs-lookup"><span data-stu-id="7747c-106">****Planning** \>**</span></span>|<span data-ttu-id="7747c-107">部署 * *\>**</span><span class="sxs-lookup"><span data-stu-id="7747c-107">****Deployment** \>**</span></span>|<span data-ttu-id="7747c-108">使用率 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="7747c-108">****Utilization****</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="7747c-109">啟動評估</span><span class="sxs-lookup"><span data-stu-id="7747c-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="7747c-110">開始規劃</span><span class="sxs-lookup"><span data-stu-id="7747c-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="7747c-111">開始部署</span><span class="sxs-lookup"><span data-stu-id="7747c-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="7747c-112">您在此處 ！</span><span class="sxs-lookup"><span data-stu-id="7747c-112">You are here!</span></span>  <br/> [<span data-ttu-id="7747c-113">後續步驟</span><span class="sxs-lookup"><span data-stu-id="7747c-113">Next steps</span></span>](suspend-or-restore-an-account-in-ocas.md#nextsteps) <br/> |
   
<span data-ttu-id="7747c-p101">假設您收到警示 for Office 365 組織的使用者帳戶的其中一個已遭洩露。或者，假設您已收到警示，指出有問題的使用者帳戶。與 Office 365 雲端應用程式安全性]，可以暫停的使用者帳戶，而稍後將其還原後已經調查您會收到通知。</span><span class="sxs-lookup"><span data-stu-id="7747c-p101">Suppose that you receive an alert that one of your organization's user accounts for Office 365 has been compromised. Or, suppose that you've received an alert that indicates something is wrong with a user account. With Office 365 Cloud App Security, you can suspend a user account and later restore it after you have investigated the alerts you receive.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7747c-p102">在 Office 365 企業版 E5 中使用 office 365 雲端應用程式安全性。如果貴組織要使用另一個 Office 365 企業版訂閱，可做為附加元件購買 Office 365 雲端應用程式安全性。(全域管理員在 Office 365 系統管理中心中，選擇 [**計費** \> **新增訂閱**。)如需詳細資訊，請參閱[Office 365 平台服務說明： Office 365 安全性&amp;規範中心](https://technet.microsoft.com/en-us/library/dn933793.aspx)和[購買或編輯企業版的 Office 365 的附加元件](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6)。</span><span class="sxs-lookup"><span data-stu-id="7747c-p102">Office 365 Cloud App Security is available in Office 365 Enterprise E5. If your organization is using another Office 365 Enterprise subscription, Office 365 Cloud App Security can be purchased as an add-on. (As a global administrator, in the Office 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://technet.microsoft.com/en-us/library/dn933793.aspx) and [Buy or edit an add-on for Office 365 for business](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span></span> 
  
## <a name="to-suspend-a-user-account-in-office-365-cloud-app-security"></a><span data-ttu-id="7747c-120">若要在 Office 365 雲端應用程式安全性擱置的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="7747c-120">To suspend a user account in Office 365 Cloud App Security</span></span>

<span data-ttu-id="7747c-p103">當您暫止的使用者帳戶時，您防止使用者再次登入。它是編輯直接在 Office 365 登入將狀態設定為**封鎖的登入**的使用者帳戶相同。</span><span class="sxs-lookup"><span data-stu-id="7747c-p103">When you suspend a user account, you prevent the user from signing in again. It's the same as editing the user account directly in Office 365 to set the Sign-in status to **Sign-in blocked**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7747c-p104">如果您封鎖的使用者登入 Office 365 中，透過這些擱置或編輯其登入狀態，請注意它可能需要一小時或賣才會生效的所有使用者的裝置和用戶端 （[編輯或變更 Office 365 中的使用者](https://support.office.com/article/42BB3F17-8F9D-4182-B434-5F1C8024E614#SingleUserPreview)） 上。如果使用者登入 Office 365 時，封鎖每當 Office 365 要求他們登入一次將會生效。</span><span class="sxs-lookup"><span data-stu-id="7747c-p104">If you block a user from signing in to Office 365, either by suspending them or by editing their sign-in status, be aware that it can take an hour or so to take effect on all of the user's devices and clients ([Edit or change a user in Office 365](https://support.office.com/article/42BB3F17-8F9D-4182-B434-5F1C8024E614#SingleUserPreview)). If the user is signed in to Office 365, the block will take effect whenever Office 365 requires them to sign in again.</span></span> 
  
1. <span data-ttu-id="7747c-p105">以[全域管理員或安全性管理員](permissions-in-the-security-and-compliance-center.md)，請移至[https://protection.office.com](https://protection.office.com)並使用您工作或學校的帳戶登入。(這會引導您安全性&amp;規範中心。)</span><span class="sxs-lookup"><span data-stu-id="7747c-p105">As a [global administrator or security administrator](permissions-in-the-security-and-compliance-center.md), go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account. (This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="7747c-127">安全性&amp;規範中心選擇**提醒** \> **管理進階提醒**。</span><span class="sxs-lookup"><span data-stu-id="7747c-127">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="7747c-128">選擇 [**移至 Office 365 的雲端應用程式安全性**]。</span><span class="sxs-lookup"><span data-stu-id="7747c-128">Choose **Go to Office 365 Cloud App Security**.</span></span>
    
    ![安全性&amp;規範中心選擇管理進階警告移至 Office 365 雲端應用程式安全性](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)
  
4. <span data-ttu-id="7747c-130">在不同螢幕頂端導覽列中，選擇 [**提醒**]。</span><span class="sxs-lookup"><span data-stu-id="7747c-130">In the navigation bar across the top of the screen, choose **Alerts**.</span></span>
    
5. <span data-ttu-id="7747c-131">在 [**提醒**] 欄中，連按兩下 [通知，特定的使用者帳戶的。</span><span class="sxs-lookup"><span data-stu-id="7747c-131">In the **Alert** column, double-click an alert that pertains to a specific user account.</span></span> 
    
6. <span data-ttu-id="7747c-132">[**帳戶**] 下的 [**狀態**] 欄中，選擇 [設定![設定] 圖示](media/e01b75cc-b28f-4b83-8f86-b1b13dc27ab2.png) \> **暫停使用者**。</span><span class="sxs-lookup"><span data-stu-id="7747c-132">Under **Accounts**, in the **Status** column, choose Settings ![settings icon](media/e01b75cc-b28f-4b83-8f86-b1b13dc27ab2.png) \> **Suspend user**.</span></span>
    
## <a name="to-restore-a-user-account"></a><span data-ttu-id="7747c-133">若要還原的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="7747c-133">To restore a user account</span></span>

<span data-ttu-id="7747c-134">請參閱[還原 Office 365 中的使用者](https://support.office.com/article/2c261e42-5dd1-48b0-845f-2a016d29cfc1)</span><span class="sxs-lookup"><span data-stu-id="7747c-134">See [Restore a user in Office 365](https://support.office.com/article/2c261e42-5dd1-48b0-845f-2a016d29cfc1)</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="7747c-135">後續步驟</span><span class="sxs-lookup"><span data-stu-id="7747c-135">Next steps</span></span>

- [<span data-ttu-id="7747c-136">檢閱並對 Office 365 雲端 App 安全性中的警示採取動作</span><span class="sxs-lookup"><span data-stu-id="7747c-136">Review and take action on alerts in Office 365 Cloud App Security</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="7747c-137">使用 Office 365 雲端 App 安全性管理 App 權限</span><span class="sxs-lookup"><span data-stu-id="7747c-137">Manage app permissions using Office 365 Cloud App Security</span></span>](manage-app-permissions-in-ocas.md)
    
- <span data-ttu-id="7747c-138">檢閱您[的 Office 365 雲端應用程式安全性使用率活動](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="7747c-138">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    
