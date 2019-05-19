---
title: Office 365 客戶加密箱要求
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解客戶加密箱要求可讓您控制如何 Microsoft 支援工程師可以存取您的資料時所遇到的問題。
ms.openlocfilehash: 2f15201cb4c49a22d7789ffafcdd94b5266bcdd4
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153835"
---
# <a name="customer-lockbox-in-office-365"></a><span data-ttu-id="41170-103">Office 365 中的客戶加密箱</span><span class="sxs-lookup"><span data-stu-id="41170-103">Customer Lockbox in Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="41170-104">本文提供一種功能，是目前僅適用於 Microsoft 365 E5、 Office 365 E5、 資訊保護和合規性或進階合規性的附加元件訂閱的組織的部署和設定指導。</span><span class="sxs-lookup"><span data-stu-id="41170-104">This article provides deployment and configuration guidance for a feature that is currently available only for organizations that have a Microsoft 365 E5, Office 365 E5, Information Protection and Compliance, or Advanced Compliance add-on subscription.</span></span>

<span data-ttu-id="41170-105">客戶加密箱能確保 Microsoft 無法存取您的內容，若要執行服務作業不需要明確的核准。</span><span class="sxs-lookup"><span data-stu-id="41170-105">Customer Lockbox ensures that Microsoft cannot access your content to perform a service operation without your explicit approval.</span></span> <span data-ttu-id="41170-106">客戶加密箱帶入您存取您的內容要求的核准工作流程。</span><span class="sxs-lookup"><span data-stu-id="41170-106">Customer Lockbox brings you into the approval workflow for requests to access your content.</span></span>

<span data-ttu-id="41170-107">有時候，Microsoft 工程師協助疑難排解並修正客戶報告的支援程序中的問題。</span><span class="sxs-lookup"><span data-stu-id="41170-107">Occasionally, Microsoft engineers help troubleshoot and fix customer reported issues in the support process.</span></span> <span data-ttu-id="41170-108">通常，透過廣泛的遙測修正問題，且偵錯工具 Microsoft 就地其服務。</span><span class="sxs-lookup"><span data-stu-id="41170-108">Usually, issues are fixed through extensive telemetry and debugging tools Microsoft has in place for its services.</span></span> <span data-ttu-id="41170-109">不過，某些情況下需要 Microsoft 工程師存取客戶內容，來判定其根本原因並修正問題。</span><span class="sxs-lookup"><span data-stu-id="41170-109">However, some cases require a Microsoft engineer to access customer content to determine the root cause and fix the issue.</span></span> <span data-ttu-id="41170-110">客戶加密箱要求工程師的客戶的存取要求核准工作流程中的最後一個步驟。</span><span class="sxs-lookup"><span data-stu-id="41170-110">Customer Lockbox requires the engineer to request access from the customer as a final step in the approval workflow.</span></span> <span data-ttu-id="41170-111">這可讓組織來核准或拒絕這些要求，並提供給客戶的直接存取控制選項。</span><span class="sxs-lookup"><span data-stu-id="41170-111">This gives organizations the option to approve or deny these requests, and provide direct access control to the customer.</span></span>

### <a name="customer-lockbox-overview-video"></a><span data-ttu-id="41170-112">客戶加密箱概觀影片</span><span class="sxs-lookup"><span data-stu-id="41170-112">Customer Lockbox overview video</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/8fecf10b-1f03-4849-8b67-76d3d2a43f26?autoplay=false]

> [!NOTE]
> <span data-ttu-id="41170-113">客戶加密箱支援要求，以存取 Exchange Online、 SharePoint Online 和商務用 OneDrive 中的資料。</span><span class="sxs-lookup"><span data-stu-id="41170-113">Customer Lockbox supports requests to access data in Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="41170-114">若要建議的其他 Office 365 服務的支援，請將要求提交在[Office 365 UserVoice](https://office365.uservoice.com/)。</span><span class="sxs-lookup"><span data-stu-id="41170-114">To recommend support for other Office 365 services, please submit a request at [Office 365 UserVoice](https://office365.uservoice.com/).</span></span>

## <a name="customer-lockbox-workflow"></a><span data-ttu-id="41170-115">客戶加密箱工作流程</span><span class="sxs-lookup"><span data-stu-id="41170-115">Customer Lockbox workflow</span></span>

<span data-ttu-id="41170-116">下列步驟概述的一般工作流程，客戶加密箱要求由 Microsoft 工程師起始時：</span><span class="sxs-lookup"><span data-stu-id="41170-116">The following steps outline the typical workflow when a Customer Lockbox request is initiated by a Microsoft engineer:</span></span>

1. <span data-ttu-id="41170-117">某人在組織都有其 Office 365 信箱發生問題。</span><span class="sxs-lookup"><span data-stu-id="41170-117">Someone at an organization has an issue with their Office 365 mailbox.</span></span>

2. <span data-ttu-id="41170-118">使用者疑難排解問題，但無法修正問題之後，他們會使用 Microsoft 支援服務開啟支援要求。</span><span class="sxs-lookup"><span data-stu-id="41170-118">After the user troubleshoots the issue, but can't fix it, they open a support request with Microsoft Support.</span></span>

3. <span data-ttu-id="41170-119">支援工程師檢閱服務要求，並決定需要存取客戶的 Exchange Online 內容才能修復問題。</span><span class="sxs-lookup"><span data-stu-id="41170-119">A support engineer reviews the service request and determines a need to access customer’s Exchange Online content to repair the issue.</span></span>

4. <span data-ttu-id="41170-120">支援工程師登入客戶加密箱要求工具，並藉由指定客戶的租用戶名稱、 服務要求編號和資料存取所需的估計的工期進行資料存取要求。</span><span class="sxs-lookup"><span data-stu-id="41170-120">The support engineer logs into the Customer Lockbox request tool and makes a data access request by specifying the customer's tenant name, service request number, and the estimated duration for which access to the data is needed.</span></span>

5. <span data-ttu-id="41170-121">Microsoft 支援服務管理員核准要求之後，客戶加密箱傳送客戶組織在指定的核准者暫止的存取要求有關的電子郵件通知 microsoft。</span><span class="sxs-lookup"><span data-stu-id="41170-121">After a Microsoft Support manager approves the request, Customer Lockbox sends the designated approver at the customer's organization an email notification about the pending access request from Microsoft.</span></span>

    ![客戶加密箱電子郵件通知的範例](media/CustomerLockbox1.png)

   > [!NOTE]
   > <span data-ttu-id="41170-123">獲指派 Microsoft 365 系統管理中心中的[客戶加密箱存取核准者](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)系統管理員角色的任何人都可以核准客戶加密箱要求。</span><span class="sxs-lookup"><span data-stu-id="41170-123">Anyone who is assigned the [Customer Lockbox access approver](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) admin role in Microsoft 365 admin center can approve Customer Lockbox requests.</span></span>

7. <span data-ttu-id="41170-124">核准者登入 Microsoft 365 系統管理中心，並核准要求。</span><span class="sxs-lookup"><span data-stu-id="41170-124">The approver signs in to the Microsoft 365 admin center and approves the request.</span></span> <span data-ttu-id="41170-125">此步驟會觸發可用的稽核記錄的建立，藉由搜尋 Office 365 稽核記錄檔。</span><span class="sxs-lookup"><span data-stu-id="41170-125">This step triggers the creation of an audit record available by searching the Office 365 audit log.</span></span> <span data-ttu-id="41170-126">如需詳細資訊，請參閱[稽核客戶加密箱要求](#auditing-customer-lockbox-requests)一節。</span><span class="sxs-lookup"><span data-stu-id="41170-126">For more information, see the [Auditing Customer Lockbox requests](#auditing-customer-lockbox-requests) section.</span></span>

   <span data-ttu-id="41170-127">如果客戶會拒絕要求或 12 小時內未獲核准要求，要求過期並沒有存取權授與 Microsoft 工程師。</span><span class="sxs-lookup"><span data-stu-id="41170-127">If the customer rejects the request or the request isn’t approved within 12 hours, the request expires and no access is granted to the Microsoft engineer.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="41170-128">Microsoft 不包含客戶加密箱電子郵件通知要求您登入 Office 365 中的任何連結。</span><span class="sxs-lookup"><span data-stu-id="41170-128">Microsoft does not include any links in Customer Lockbox email notifications requiring you to sign in to Office 365.</span></span>

8. <span data-ttu-id="41170-129">客戶核准要求之後，Microsoft 工程師接收核准訊息、 登入 Exchange Online 中，並修正客戶的問題。</span><span class="sxs-lookup"><span data-stu-id="41170-129">After the customer approves the request, the Microsoft engineer receives the approval message, logs into Exchange Online, and fixes the customer's issue.</span></span> <span data-ttu-id="41170-130">Microsoft 工程師已修正問題之後，自動撤銷存取權的要求持續時間。</span><span class="sxs-lookup"><span data-stu-id="41170-130">Microsoft engineers have the requested duration to fix the issue after which the access is automatically revoked.</span></span>

> [!NOTE]
> <span data-ttu-id="41170-131">在 Office 365 稽核記錄檔會記錄所有由 Microsoft 工程師執行的動作。</span><span class="sxs-lookup"><span data-stu-id="41170-131">All actions performed by a Microsoft engineer are logged in the Office 365 audit log.</span></span> <span data-ttu-id="41170-132">您可以搜尋並檢閱這些稽核記錄和可以搜尋並檢閱。</span><span class="sxs-lookup"><span data-stu-id="41170-132">You can search for and review these audit record and can be searched for and reviewed.</span></span>

## <a name="turn-customer-lockbox-requests-on-or-off"></a><span data-ttu-id="41170-133">開啟或關閉客戶加密箱要求</span><span class="sxs-lookup"><span data-stu-id="41170-133">Turn Customer Lockbox requests on or off</span></span>

<span data-ttu-id="41170-134">Office 365 系統管理員可以開啟的 Microsoft 365 系統管理中心中的客戶加密箱控制項。</span><span class="sxs-lookup"><span data-stu-id="41170-134">An Office 365 administrator can turn on Customer Lockbox controls in the Microsoft 365 admin center.</span></span> <span data-ttu-id="41170-135">客戶加密箱開啟時，Microsoft 必須先取得組織的核准，然後再存取任何其內容。</span><span class="sxs-lookup"><span data-stu-id="41170-135">When Customer Lockbox is turned on, Microsoft is required to obtain an organization’s approval before accessing any of their content.</span></span>

> [!NOTE]
> <span data-ttu-id="41170-136">若要執行下列程序，您必須是全域系統管理員在您的 Microsoft 365 或 Office 365 組織，或獲指派 「**客戶加密箱存取核准者**系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="41170-136">To perform the following procedure, you must be a global administrator in your Microsoft 365 or Office 365 organization, or be assigned the **Customer Lockbox access approver** admin role.</span></span>

1. <span data-ttu-id="41170-137">移至 [[https://admin.microsoft.com](https://admin.microsoft.com)並以您的公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="41170-137">Go to [https://admin.microsoft.com](https://admin.microsoft.com) and sign in with your work or school account.</span></span>

2. <span data-ttu-id="41170-138">按一下 [**設定 > 安全性 & 隱私權**]。</span><span class="sxs-lookup"><span data-stu-id="41170-138">Click **Settings > Security & privacy**.</span></span>

    ![編輯客戶加密箱設定在系統管理中心](media/CustomerLockbox2.png)

3. <span data-ttu-id="41170-140">在**客戶加密箱**並排顯示，按一下 [**編輯**]，然後將切換以**開啟**或**關閉**若要開啟或關閉此功能。</span><span class="sxs-lookup"><span data-stu-id="41170-140">On the **Customer Lockbox** tile, click **Edit**, and then move the toggle to **On** or **Off** to turn the feature on or off.</span></span>

    ![Require approval for Customer Lockbox](media/CustomerLockbox4.png)

## <a name="approve-or-deny-a-customer-lockbox-request"></a><span data-ttu-id="41170-142">核准或拒絕客戶加密箱要求</span><span class="sxs-lookup"><span data-stu-id="41170-142">Approve or deny a Customer Lockbox request</span></span>

> [!NOTE]
> <span data-ttu-id="41170-143">若要執行下列程序，您必須是全域系統管理員在您的 Microsoft 365 或 Office 365 組織，或獲指派 「**客戶加密箱存取核准者**系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="41170-143">To perform the following procedure, you must be a global administrator in your Microsoft 365 or Office 365 organization, or be assigned the **Customer Lockbox access approver** admin role.</span></span>

1. <span data-ttu-id="41170-144">移至 [[https://admin.microsoft.com](https://admin.microsoft.com)並以您的公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="41170-144">Go to [https://admin.microsoft.com](https://admin.microsoft.com) and sign in with your work or school account.</span></span>

2. <span data-ttu-id="41170-145">按一下 [**支援 > 客戶加密箱要求**。</span><span class="sxs-lookup"><span data-stu-id="41170-145">Click **Support > Customer Lockbox Requests**.</span></span>

    ![按一下 [支援]，然後按一下 [客戶加密箱要求](media/CustomerLockbox5.png)

    <span data-ttu-id="41170-147">客戶加密箱要求清單隨即顯示。</span><span class="sxs-lookup"><span data-stu-id="41170-147">A list of Customer Lockbox requests is displayed.</span></span>

    ![清單中的客戶加密箱要求](media/CustomerLockbox6.png)

3. <span data-ttu-id="41170-149">選取客戶加密箱要求，，然後按一下 [**核准**或**拒絕**。</span><span class="sxs-lookup"><span data-stu-id="41170-149">Select a Customer Lockbox request, and then click **Approve** or **Deny**.</span></span>

    ![核准或拒絕客戶加密箱要求](media/CustomerLockbox7.png)

    <span data-ttu-id="41170-151">會顯示一則有關的客戶加密箱要求核准的確認訊息。</span><span class="sxs-lookup"><span data-stu-id="41170-151">A confirmation message about the approval of the Customer Lockbox request is displayed.</span></span>

    ![核准或拒絕客戶加密箱要求](media/CustomerLockbox8.png)

## <a name="auditing-customer-lockbox-requests"></a><span data-ttu-id="41170-153">稽核客戶加密箱要求</span><span class="sxs-lookup"><span data-stu-id="41170-153">Auditing Customer Lockbox requests</span></span> 

<span data-ttu-id="41170-154">會對應到客戶加密箱要求的稽核記錄登入 Office 365 稽核記錄檔，並可使用 Office 365 安全性 & 合規性中心中的 [[稽核記錄搜尋工具](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance)。</span><span class="sxs-lookup"><span data-stu-id="41170-154">Audit records that correspond to the Customer Lockbox requests are logged in the Office 365 audit log and can be accessed by using the [Audit log search tool](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance) in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="41170-155">在 Office 365 稽核記錄檔會記錄與客戶接受或拒絕客戶加密箱要求和 （當核准存取要求），由 Microsoft 工程師執行的動作相關的動作。</span><span class="sxs-lookup"><span data-stu-id="41170-155">Actions related to a customer accepting or denying a Customer Lockbox request and actions performed by Microsoft engineers (when access requests are approved) are logged in the Office 365 audit log.</span></span> <span data-ttu-id="41170-156">您可以搜尋並檢閱這些稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="41170-156">You can search for and review these audit records.</span></span>

> [!NOTE]
> <span data-ttu-id="41170-157">您必須獲指派 「 僅檢視稽核記錄檔] 或 [稽核記錄檔角色在 Exchange Online 來搜尋 Office 365 稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="41170-157">You have to be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online to search the Office 365 audit log.</span></span> <span data-ttu-id="41170-158">如需詳細資訊，請參閱 <<c0>的搜尋稽核記錄中 Office 365 安全性 &amp; 合規性中心。</span><span class="sxs-lookup"><span data-stu-id="41170-158">For more information, see [Search the audit log in the Office 365 Security & Compliance Center](https://docs.microsoft.com/en-us/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#before-you-begin).</span></span>

### <a name="search-the-audit-log-for-activity-related-to-customer-lockbox-requests"></a><span data-ttu-id="41170-159">搜尋與客戶加密箱要求相關的活動的稽核記錄檔</span><span class="sxs-lookup"><span data-stu-id="41170-159">Search the audit log for activity related to Customer Lockbox requests</span></span>

<span data-ttu-id="41170-160">以下是如何建立稽核記錄搜尋查詢來傳回與客戶加密箱相關的稽核記錄：</span><span class="sxs-lookup"><span data-stu-id="41170-160">Here's how to create an audit log search query to return audit records related to Customer Lockbox:</span></span>

1. <span data-ttu-id="41170-161">移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="41170-161">Go to [https://protection.office.com](https://protection.office.com).</span></span>
  
2. <span data-ttu-id="41170-162">使用公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="41170-162">Sign in to Office 365 using your work or school account.</span></span>

3. <span data-ttu-id="41170-163">在安全性 & 合規性中心的左窗格中，按一下 [**搜尋 & 調查** > **稽核記錄搜尋**。</span><span class="sxs-lookup"><span data-stu-id="41170-163">In the left pane of the Security & Compliance Center, click **Search & investigation** > **Audit log search**.</span></span>

    <span data-ttu-id="41170-164">會顯示 [**稽核記錄搜尋**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="41170-164">The **Audit log search** page is displayed.</span></span>

    ![稽核記錄搜尋] 頁面](media/auditlogsearch1.png)
  
4. <span data-ttu-id="41170-166">設定下列搜尋準則：</span><span class="sxs-lookup"><span data-stu-id="41170-166">Configure the following search criteria:</span></span>

    <span data-ttu-id="41170-167">a.</span><span class="sxs-lookup"><span data-stu-id="41170-167">a.</span></span> <span data-ttu-id="41170-168">**活動**-離開此欄位空白，讓搜尋傳回的所有活動的稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="41170-168">**Activities** - Leave this field blank so that the search returns audit records for all activities.</span></span> <span data-ttu-id="41170-169">這是必要傳回任何與客戶加密箱要求相關的稽核記錄和相對應執行由 Microsoft 工程師的活動。</span><span class="sxs-lookup"><span data-stu-id="41170-169">This is necessary to return any audit records related to Customer Lockbox requests and corresponding activity performed by Microsoft engineers.</span></span>

    <span data-ttu-id="41170-170">b.</span><span class="sxs-lookup"><span data-stu-id="41170-170">b.</span></span> <span data-ttu-id="41170-171">**開始日期**和**結束日期**-選取的日期和時間範圍以顯示該期間內發生的事件。</span><span class="sxs-lookup"><span data-stu-id="41170-171">**Start date** and **End date** - Select a date and time range to display the events that occurred within that period.</span></span>

    <span data-ttu-id="41170-172">c.</span><span class="sxs-lookup"><span data-stu-id="41170-172">c.</span></span> <span data-ttu-id="41170-173">**使用者**-離開此欄位空白。</span><span class="sxs-lookup"><span data-stu-id="41170-173">**Users** - Leave this field blank.</span></span>

    <span data-ttu-id="41170-174">d.</span><span class="sxs-lookup"><span data-stu-id="41170-174">d.</span></span> <span data-ttu-id="41170-175">**檔案、 資料夾或網站**-離開此欄位空白。</span><span class="sxs-lookup"><span data-stu-id="41170-175">**File, folder, or site** - Leave this field blank.</span></span>

5. <span data-ttu-id="41170-176">按一下 [**搜尋**] 以執行使用您的搜尋準則的 [搜尋]。</span><span class="sxs-lookup"><span data-stu-id="41170-176">Click **Search** to run the search using your search criteria.</span></span> 

    <span data-ttu-id="41170-177">載入的搜尋結果時，在幾分鐘之後他們底下會顯示及**結果**在**稽核記錄搜尋**] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="41170-177">The search results are loaded, and after a few moments they are displayed under **Results** on the **Audit log search** page.</span></span>

6. <span data-ttu-id="41170-178">在搜尋結果頁面上，按一下 [**篩選結果**並執行下列其中一個下列事項：</span><span class="sxs-lookup"><span data-stu-id="41170-178">Click **Filter results** on the search results page, and do one of the following things:</span></span>

   - <span data-ttu-id="41170-179">若要顯示在您的組織核准或拒絕客戶加密箱要求核准者與相關的稽核記錄： 中] 底下的 [**活動**] 欄中，輸入**組 AccessToCustomerDataRequest**。</span><span class="sxs-lookup"><span data-stu-id="41170-179">To display audit records related to an approver in your organization approving or denying a Customer Lockbox request: In the box under the **Activity** column, type **Set-AccessToCustomerDataRequest**.</span></span>

   - <span data-ttu-id="41170-180">若要顯示在 「 已核准的客戶加密箱要求的回應中執行動作的 Microsoft 工程師與相關的稽核記錄： 在 [**使用者**] 資料行] 方塊中輸入**Microsoft 運算子**。</span><span class="sxs-lookup"><span data-stu-id="41170-180">To display audit records related to a Microsoft engineer performing actions in response to an approved Customer Lockbox request: In the box under the **User** column, type **Microsoft Operator**.</span></span> <span data-ttu-id="41170-181">請注意，工程師所執行的動作顯示的 int [**活動**] 欄位。</span><span class="sxs-lookup"><span data-stu-id="41170-181">Note that the action performed by the engineer is displayed int the **Activity** column.</span></span>

      ![篩選要顯示的稽核記錄的 「 Microsoft 運算子 」](media/CustomerLockbox10.png)

7. <span data-ttu-id="41170-183">在結果清單中，按一下 [將它顯示稽核記錄]。</span><span class="sxs-lookup"><span data-stu-id="41170-183">In the list of results, click an audit record to display it.</span></span>

### <a name="audit-record-for-a-customer-lockbox-access-request"></a><span data-ttu-id="41170-184">客戶加密箱存取要求的稽核記錄</span><span class="sxs-lookup"><span data-stu-id="41170-184">Audit record for a Customer Lockbox access request</span></span>

<span data-ttu-id="41170-185">當您的組織中的人員核准或拒絕客戶加密箱要求時，稽核記錄會記錄在 Office 365 稽核記錄檔中。</span><span class="sxs-lookup"><span data-stu-id="41170-185">When a person in your organization approves or denies a Customer Lockbox request, an audit record is logged in the Office 365 audit log.</span></span> <span data-ttu-id="41170-186">此記錄會包含下列資訊。</span><span class="sxs-lookup"><span data-stu-id="41170-186">This record contains the following information.</span></span> 

| <span data-ttu-id="41170-187">稽核記錄屬性</span><span class="sxs-lookup"><span data-stu-id="41170-187">Audit record property</span></span>| <span data-ttu-id="41170-188">描述</span><span class="sxs-lookup"><span data-stu-id="41170-188">Description</span></span>|
|:---------- |:----------|
| <span data-ttu-id="41170-189">日期</span><span class="sxs-lookup"><span data-stu-id="41170-189">Date</span></span>       | <span data-ttu-id="41170-190">日期和時間時核准或拒絕客戶加密箱要求。</span><span class="sxs-lookup"><span data-stu-id="41170-190">The date and time when the Customer Lockbox request was approved or denied.</span></span>
| <span data-ttu-id="41170-191">IP 位址</span><span class="sxs-lookup"><span data-stu-id="41170-191">IP address</span></span> | <span data-ttu-id="41170-192">電腦的 IP 位址的核准者用來核准或拒絕要求。</span><span class="sxs-lookup"><span data-stu-id="41170-192">The IP address of the machine the approver used to approve or deny a request.</span></span> |
| <span data-ttu-id="41170-193">使用者</span><span class="sxs-lookup"><span data-stu-id="41170-193">User</span></span>       | <span data-ttu-id="41170-194">服務帳戶 BOXServiceAccount @\[customerforest\]。 prod.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="41170-194">The service account BOXServiceAccount@\[customerforest\].prod.outlook.com.</span></span>            |
| <span data-ttu-id="41170-195">活動</span><span class="sxs-lookup"><span data-stu-id="41170-195">Activity</span></span>   | <span data-ttu-id="41170-196">設定 AccessToCustomerDataRequest;這是當您核准或拒絕客戶加密箱要求時，會記錄稽核活動。</span><span class="sxs-lookup"><span data-stu-id="41170-196">Set-AccessToCustomerDataRequest; this is the auditing activity that is logged when you approve or deny a Customer Lockbox request.</span></span>                                |
| <span data-ttu-id="41170-197">項目</span><span class="sxs-lookup"><span data-stu-id="41170-197">Item</span></span>       | <span data-ttu-id="41170-198">客戶加密箱要求的 Guid</span><span class="sxs-lookup"><span data-stu-id="41170-198">The Guid of the Customer Lockbox request</span></span>                             |

<span data-ttu-id="41170-199">下列螢幕擷取畫面顯示稽核記錄的記錄，會對應至已核准的客戶加密箱要求範例。</span><span class="sxs-lookup"><span data-stu-id="41170-199">The following screenshot shows an example of an audit log record that corresponds to an approved Customer Lockbox request.</span></span> <span data-ttu-id="41170-200">如果客戶加密箱要求遭到拒絕， **ApprovalDecision**參數的值會被**拒絕**。</span><span class="sxs-lookup"><span data-stu-id="41170-200">If a Customer Lockbox request was denied, then the value of **ApprovalDecision** parameter would be **Deny**.</span></span>

![稽核記錄已核准的客戶加密箱要求](media/CustomerLockbox9.png)

> [!TIP]
> <span data-ttu-id="41170-202">若要在稽核記錄中顯示的詳細的資訊，請按一下 [**詳細資訊**。</span><span class="sxs-lookup"><span data-stu-id="41170-202">To display more detailed information in an audit record, click **More information**.</span></span>

### <a name="audit-record-for-an-action-performed-by-a-microsoft-engineer"></a><span data-ttu-id="41170-203">由 Microsoft 工程師執行動作的稽核記錄</span><span class="sxs-lookup"><span data-stu-id="41170-203">Audit record for an action performed by a Microsoft engineer</span></span>

<span data-ttu-id="41170-204">如先前所述，在稽核記錄檔會記錄之後核准客戶加密箱要求 （和，可能會導致存取客戶內容），由 Microsoft 工程師執行的動作。</span><span class="sxs-lookup"><span data-stu-id="41170-204">As previously explained, the actions performed by a Microsoft engineer after a Customer Lockbox request is approved (and that may result in accessing customer content) are logged in the audit log.</span></span> <span data-ttu-id="41170-205">這些記錄包含下列資訊。</span><span class="sxs-lookup"><span data-stu-id="41170-205">These records contain the following information.</span></span>

| <span data-ttu-id="41170-206">稽核記錄屬性</span><span class="sxs-lookup"><span data-stu-id="41170-206">Audit record property</span></span>| <span data-ttu-id="41170-207">描述</span><span class="sxs-lookup"><span data-stu-id="41170-207">Description</span></span>|
|:---------- |:----------|
| <span data-ttu-id="41170-208">日期</span><span class="sxs-lookup"><span data-stu-id="41170-208">Date</span></span>       | <span data-ttu-id="41170-209">日期時間時所執行的動作。</span><span class="sxs-lookup"><span data-stu-id="41170-209">Date time when the action was performed.</span></span> <span data-ttu-id="41170-210">請注意的客戶加密箱要求受到核准時 4 小時內，將會執行此動作的時間。</span><span class="sxs-lookup"><span data-stu-id="41170-210">Note that the time that this action was performed will be within 4 hours of when the Customer Lockbox request was approved.</span></span>              |
| <span data-ttu-id="41170-211">IP 位址</span><span class="sxs-lookup"><span data-stu-id="41170-211">IP address</span></span> | <span data-ttu-id="41170-212">使用機器 Microsoft 工程師 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="41170-212">The IP Address of the machine Microsoft engineer used.</span></span> |
| <span data-ttu-id="41170-213">使用者</span><span class="sxs-lookup"><span data-stu-id="41170-213">User</span></span>       | <span data-ttu-id="41170-214">Microsoft 運算子;這個值表示此記錄與客戶加密箱要求。</span><span class="sxs-lookup"><span data-stu-id="41170-214">Microsoft Operator; this value indicates that this record is related to a Customer Lockbox request.</span></span>                                  |
| <span data-ttu-id="41170-215">活動</span><span class="sxs-lookup"><span data-stu-id="41170-215">Activity</span></span>   | <span data-ttu-id="41170-216">由 Microsoft 工程師執行活動的名稱。</span><span class="sxs-lookup"><span data-stu-id="41170-216">Name of the activity performed by the Microsoft engineer.</span></span>|
| <span data-ttu-id="41170-217">項目</span><span class="sxs-lookup"><span data-stu-id="41170-217">Item</span></span>       | <span data-ttu-id="41170-218">\<空白\></span><span class="sxs-lookup"><span data-stu-id="41170-218">\<empty\></span></span>                                             |


## <a name="frequently-asked-questions"></a><span data-ttu-id="41170-219">常見問題集</span><span class="sxs-lookup"><span data-stu-id="41170-219">Frequently asked questions</span></span>

#### <a name="which-office-365-services-does-customer-lockbox-apply-to"></a><span data-ttu-id="41170-220">若要將客戶加密箱套用在 Office 365 服務？</span><span class="sxs-lookup"><span data-stu-id="41170-220">Which Office 365 services does Customer Lockbox apply to?</span></span>

<span data-ttu-id="41170-221">客戶加密箱目前支援在 Exchange Online、 SharePoint Online 和商務用 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="41170-221">Customer Lockbox is currently supported in Exchange Online, SharePoint Online, and OneDrive for Business.</span></span>

#### <a name="is-customer-lockbox-available-to-all-office-365-customers"></a><span data-ttu-id="41170-222">是客戶加密箱可供所有 Office 365 客戶？</span><span class="sxs-lookup"><span data-stu-id="41170-222">Is Customer Lockbox available to all Office 365 customers?</span></span>

<span data-ttu-id="41170-223">客戶加密箱隨附的 Microsoft 365 或 Office 365 E5 訂閱，並可以新增到其他計劃與資訊保護和法規或進階合規性附加元件訂閱。</span><span class="sxs-lookup"><span data-stu-id="41170-223">Customer Lockbox is included with the Microsoft 365 or Office 365 E5 subscriptions and can be added to other plans with an Information Protection and Compliance or an Advanced Compliance add-on subscription.</span></span> <span data-ttu-id="41170-224"> [方案和價格](https://products.office.com/business/office-365-enterprise-e5-business-software)，請參閱 如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="41170-224">Please see [Plans and pricing](https://products.office.com/business/office-365-enterprise-e5-business-software) for more information.</span></span>

#### <a name="what-is-customer-content"></a><span data-ttu-id="41170-225">什麼是客戶內容？</span><span class="sxs-lookup"><span data-stu-id="41170-225">What is customer content?</span></span>

<span data-ttu-id="41170-226">客戶內容是由 Office 365 服務和應用程式的使用者所建立的資料。</span><span class="sxs-lookup"><span data-stu-id="41170-226">Customer content is the data created by users of Office 365 services and applications.</span></span> <span data-ttu-id="41170-227">客戶內容的範例包括：</span><span class="sxs-lookup"><span data-stu-id="41170-227">Examples of customer content include:</span></span>

- <span data-ttu-id="41170-228">電子郵件內文或電子郵件附件</span><span class="sxs-lookup"><span data-stu-id="41170-228">Email body or email attachments</span></span>

- <span data-ttu-id="41170-229">SharePoint 網站內容</span><span class="sxs-lookup"><span data-stu-id="41170-229">SharePoint site contents</span></span>

- <span data-ttu-id="41170-230">SharePoint 檔案的內文中的資訊</span><span class="sxs-lookup"><span data-stu-id="41170-230">Information in the body of a SharePoint file</span></span>

- <span data-ttu-id="41170-231">Skype 商務簡報檔案內文</span><span class="sxs-lookup"><span data-stu-id="41170-231">Skype for Business presentation file body</span></span>

- <span data-ttu-id="41170-232">立即訊息 (IM) 或語音交談</span><span class="sxs-lookup"><span data-stu-id="41170-232">Instant messages (IM) or voice conversations</span></span>

- <span data-ttu-id="41170-233">客戶所產生的 blob 或結構化的儲存資料 （例如，SQL 容器）</span><span class="sxs-lookup"><span data-stu-id="41170-233">Customer-generated blob or structured storage data (for example, SQL Containers)</span></span>

- <span data-ttu-id="41170-234">客戶自有的安全性資訊 （例如，憑證、 加密金鑰和密碼）</span><span class="sxs-lookup"><span data-stu-id="41170-234">Customer-owned security information (for example, certificates, encryption keys, and passwords)</span></span>

- <span data-ttu-id="41170-235">推斷，以及所有後續推斷，如果客戶內容會留</span><span class="sxs-lookup"><span data-stu-id="41170-235">Inferences, and all subsequent inferences, if customer content remains</span></span>

<span data-ttu-id="41170-236">如需有關 Office 365 中的客戶內容的詳細資訊，請參閱 < 在<b0>Office 365 信任中心</b0>。</span><span class="sxs-lookup"><span data-stu-id="41170-236">For additional information about customer content in Office 365, see the [Office 365 Trust Center](https://products.office.com/en-US/business/office-365-trust-center-privacy/).</span></span>

#### <a name="who-is-notified-when-there-is-a-request-to-access-my-content"></a><span data-ttu-id="41170-237">要求存取我的內容時，人員會收到通知？</span><span class="sxs-lookup"><span data-stu-id="41170-237">Who is notified when there is a request to access my content?</span></span>

<span data-ttu-id="41170-238">全域系統管理員，且所有人都指派存取核准者系統管理員角色會收到通知客戶加密箱。</span><span class="sxs-lookup"><span data-stu-id="41170-238">Global administrators and anyone assigned the Customer Lockbox access approver admin role are notified.</span></span> <span data-ttu-id="41170-239">這些也是相同的使用者可核准的客戶加密箱要求。</span><span class="sxs-lookup"><span data-stu-id="41170-239">These are also the same users who can approve for Customer Lockbox requests.</span></span>

#### <a name="who-can-approve-or-reject-these-requests-in-my-organization"></a><span data-ttu-id="41170-240">誰可以核准或拒絕這些要求在我的組織中？</span><span class="sxs-lookup"><span data-stu-id="41170-240">Who can approve or reject these requests in my organization?</span></span>

<span data-ttu-id="41170-241">全域系統管理員，且所有人都指派給客戶加密箱存取核准者系統管理員角色可以核准客戶加密箱要求。</span><span class="sxs-lookup"><span data-stu-id="41170-241">Global administrators and anyone assigned the Customer Lockbox access approver admin role can approve Customer Lockbox requests.</span></span> <span data-ttu-id="41170-242">客戶控制項在其組織中的這些角色指派。</span><span class="sxs-lookup"><span data-stu-id="41170-242">Customers control these role assignments in their organizations.</span></span>

#### <a name="how-do-i-opt-in-to-customer-lockbox"></a><span data-ttu-id="41170-243">如何我選擇集客戶加密箱？</span><span class="sxs-lookup"><span data-stu-id="41170-243">How do I opt-in to Customer Lockbox?</span></span>

<span data-ttu-id="41170-244">全域系統管理員可以啟用並設定 Microsoft 365 或 Microsoft 365 系統管理中心中的客戶加密箱。</span><span class="sxs-lookup"><span data-stu-id="41170-244">A global administrator can enable and configure Customer Lockbox in the Microsoft 365 or Microsoft 365 admin center.</span></span>

#### <a name="if-i-approve-a-customer-lockbox-request-what-can-the-engineer-do-and-how-will-i-know-what-the-microsoft-engineer-did"></a><span data-ttu-id="41170-245">如果我核准客戶加密箱要求時，可以工程師與什麼如何知道 Microsoft 工程師嗎？</span><span class="sxs-lookup"><span data-stu-id="41170-245">If I approve a Customer Lockbox request, what can the engineer do and how will I know what the Microsoft engineer did?</span></span>

<span data-ttu-id="41170-246">核准客戶加密箱要求之後，Microsoft 工程師授與這些必要的權限，以使用預先核准指令程式來存取客戶內容。</span><span class="sxs-lookup"><span data-stu-id="41170-246">After you approve a Customer Lockbox request, the Microsoft engineer granted these necessary privileges to access customer content by using pre-approved cmdlets.</span></span> <span data-ttu-id="41170-247">客戶加密箱要求的回應中的 Microsoft 工程師所採取的動作會記錄，並可在 Office 365 安全性 & 合規性中心的稽核記錄檔可存取。</span><span class="sxs-lookup"><span data-stu-id="41170-247">Actions taken by Microsoft engineers in response to Customer Lockbox requests are logged and accessible in the audit log in the Office 365 Security & Compliance Center.</span></span>

#### <a name="how-do-i-know-that-microsoft-follows-the-approval-process"></a><span data-ttu-id="41170-248">如何知道，Microsoft 會遵循核准程序？</span><span class="sxs-lookup"><span data-stu-id="41170-248">How do I know that Microsoft follows the approval process?</span></span>

<span data-ttu-id="41170-249">您可以將電子郵件核准通知傳送給系統管理員和組織中的 Microsoft 365 系統管理中心中的客戶加密箱要求歷程記錄的核准者交互參照。</span><span class="sxs-lookup"><span data-stu-id="41170-249">You can cross-reference the email approval notifications sent to admins and approvers in your organization with the Customer Lockbox request history in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="41170-250">Customer Lockbox 隨附於[SOC 1 SSAE 16 稽核報告](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports)的最新。</span><span class="sxs-lookup"><span data-stu-id="41170-250">Customer Lockbox is included in the latest [SOC 1 SSAE 16 audit report](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports).</span></span> <span data-ttu-id="41170-251">如需詳細資訊，您可以在[Microsoft 服務信任入口網站](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports)找到最新的報表。</span><span class="sxs-lookup"><span data-stu-id="41170-251">For more details, you can find the latest reports in the [Microsoft Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports).</span></span>

#### <a name="can-microsoft-modify-the-list-of-approvers-for-my-tenant-if-not-how-is-it-prevented"></a><span data-ttu-id="41170-252">Microsoft 可以修改我的租用戶的核准者的清單嗎？</span><span class="sxs-lookup"><span data-stu-id="41170-252">Can Microsoft modify the list of approvers for my tenant?</span></span> <span data-ttu-id="41170-253">如果沒有，如何避免？</span><span class="sxs-lookup"><span data-stu-id="41170-253">If not, how is it prevented?</span></span>

<span data-ttu-id="41170-254">全域系統管理員在組織中的可以指定誰可以核准客戶加密箱要求。</span><span class="sxs-lookup"><span data-stu-id="41170-254">Only a global administrator in your organization can specify who can approve Customer Lockbox requests.</span></span> <span data-ttu-id="41170-255">這表示僅在 Azure Active Directory 全域系統管理員群組的成員可以指定誰可以核准邀請。</span><span class="sxs-lookup"><span data-stu-id="41170-255">That means only the members of the Global administrator group in Azure Active Directory can specify who can approve request.</span></span> <span data-ttu-id="41170-256">僅由組織管理 Azure Active Directory 中的全域系統管理員群組的成員資格。</span><span class="sxs-lookup"><span data-stu-id="41170-256">Membership of the Global administrator group in Azure Active Directory is managed only by your organization.</span></span>

#### <a name="what-if-i-need-more-information-about-a-content-access-request-to-approve-it"></a><span data-ttu-id="41170-257">如果我需要核准其內容的存取要求的詳細資訊嗎？</span><span class="sxs-lookup"><span data-stu-id="41170-257">What if I need more information about a content access request to approve it?</span></span>

<span data-ttu-id="41170-258">每個客戶加密箱要求都會包含 Office 365 服務要求數。</span><span class="sxs-lookup"><span data-stu-id="41170-258">Each Customer Lockbox request contains an Office 365 service request number.</span></span> <span data-ttu-id="41170-259">您可以連絡 Microsoft 支援服務及參照此服務數目，以取得有關之要求的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="41170-259">You can contact Microsoft Support and reference this service number to get more information about the request.</span></span>

#### <a name="when-a-customer-lockbox-request-is-approved-how-long-are-the-permissions-valid"></a><span data-ttu-id="41170-260">當客戶加密箱要求獲得核准時，多久是有效的權限？</span><span class="sxs-lookup"><span data-stu-id="41170-260">When a Customer Lockbox request is approved, how long are the permissions valid?</span></span>

<span data-ttu-id="41170-261">目前的存取權限授與 Microsoft 工程師的最大期間為 4 小時。</span><span class="sxs-lookup"><span data-stu-id="41170-261">Currently, the maximum period for the access permissions granted to the Microsoft engineer is 4 hours.</span></span> <span data-ttu-id="41170-262">Microsoft 工程師也可以要求較短的期間。</span><span class="sxs-lookup"><span data-stu-id="41170-262">The Microsoft engineer can also request a shorter period.</span></span>

#### <a name="how-can-i-get-a-history-of-all-customer-lockbox-requests"></a><span data-ttu-id="41170-263">如何取得所有客戶加密箱要求的歷程記錄？</span><span class="sxs-lookup"><span data-stu-id="41170-263">How can I get a history of all Customer Lockbox requests?</span></span>

<span data-ttu-id="41170-264">在 Microsoft 365 系統管理中心檢視所有客戶加密箱要求。</span><span class="sxs-lookup"><span data-stu-id="41170-264">All Customer Lockbox requests are viewed in the Microsoft 365 admin center.</span></span>

#### <a name="how-do-i-correlate-the-content-access-requests-with-the-related-audit-logs"></a><span data-ttu-id="41170-265">如何建立內容的存取權要求關聯與相關的稽核記錄檔？</span><span class="sxs-lookup"><span data-stu-id="41170-265">How do I correlate the content access requests with the related audit logs?</span></span>

<span data-ttu-id="41170-266">合規性中心活動摘要包含記錄活動的客戶加密箱。</span><span class="sxs-lookup"><span data-stu-id="41170-266">The Compliance Center Activity Feed contains log activities of Customer Lockbox.</span></span> <span data-ttu-id="41170-267">客戶可以交互參照的活動摘要所收到的電子郵件要求對客戶加密箱記錄活動。</span><span class="sxs-lookup"><span data-stu-id="41170-267">Customers can cross-reference the Customer Lockbox log activities from the activity feed against the email request they receive.</span></span>

#### <a name="what-happens-when-a-customer-doesnt-respond-to-a-customer-lockbox-request"></a><span data-ttu-id="41170-268">客戶不會回應客戶加密箱要求時，會發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="41170-268">What happens when a customer doesn't respond to a Customer Lockbox request?</span></span>

<span data-ttu-id="41170-269">客戶加密箱要求有預設的持續時間是 12 小時。</span><span class="sxs-lookup"><span data-stu-id="41170-269">Customer Lockbox requests have a default duration of 12 hours.</span></span> <span data-ttu-id="41170-270">如果您未在 12 小時內回應要求，要求將會過期。</span><span class="sxs-lookup"><span data-stu-id="41170-270">If you don't respond to a request within 12 hour, the request expires.</span></span>

#### <a name="what-does-microsoft-when-a-customer-rejects-a-customer-lockbox-request"></a><span data-ttu-id="41170-271">當客戶拒絕客戶加密箱要求時，用途 Microsoft？</span><span class="sxs-lookup"><span data-stu-id="41170-271">What does Microsoft when a customer rejects a Customer Lockbox request?</span></span>

<span data-ttu-id="41170-272">如果客戶拒絕客戶加密箱要求，則會發生任何客戶內容存取權。</span><span class="sxs-lookup"><span data-stu-id="41170-272">If a customer rejects a Customer Lockbox request, no access to customer content occurs.</span></span> <span data-ttu-id="41170-273">如果貴組織中的使用者持續體驗需要存取客戶內容，若要解決此問題： Microsoft 的服務問題，然後服務問題可能會保存與 Microsoft 將會通知使用者有關此。</span><span class="sxs-lookup"><span data-stu-id="41170-273">If a user in your organization continues to experience a service issue requiring Microsoft to access customer content to resolve the issue, then the service issue might persist and Microsoft will inform the user about this.</span></span>

#### <a name="does-customer-lockbox-protect-against-data-requests-from-law-enforcement-agencies-or-other-third-parties"></a><span data-ttu-id="41170-274">客戶加密箱 atp 保護針對執法機構資料要求或其他協力廠商？</span><span class="sxs-lookup"><span data-stu-id="41170-274">Does Customer Lockbox protect against data requests from law enforcement agencies or other third parties?</span></span>

<span data-ttu-id="41170-275">否。</span><span class="sxs-lookup"><span data-stu-id="41170-275">No.</span></span> <span data-ttu-id="41170-276">Microsoft 會嚴重採用客戶資料的第三方的要求。</span><span class="sxs-lookup"><span data-stu-id="41170-276">Microsoft takes third-party requests for customer data seriously.</span></span> <span data-ttu-id="41170-277">為雲端服務提供者，Microsoft 一律是代表客戶資料的隱私權。</span><span class="sxs-lookup"><span data-stu-id="41170-277">As a cloud service provider, Microsoft always advocates for the privacy of customer data.</span></span> <span data-ttu-id="41170-278">事件中我們取得傳票，Microsoft 會一直嘗試將協力廠商重新導向至客戶取得的資訊。</span><span class="sxs-lookup"><span data-stu-id="41170-278">In the event we get a subpoena, Microsoft always attempts to redirect the third party to the customer to obtain the information.</span></span> <span data-ttu-id="41170-279">(讀取將 Smith 的部落格: [ Protecting 客戶資料從政府側錄](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/))。</span><span class="sxs-lookup"><span data-stu-id="41170-279">(Read Brad Smith's blog: [Protecting customer data from government snooping](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)).</span></span> <span data-ttu-id="41170-280">我們會定期發佈有關 Microsoft 收到法律強制執行要求的[詳細的資訊](https://www.microsoft.com/en-us/corporate-responsibility/lerr)。</span><span class="sxs-lookup"><span data-stu-id="41170-280">We periodically publish [detailed information](https://www.microsoft.com/en-us/corporate-responsibility/lerr) about the law enforcement requests that Microsoft receives.</span></span>

<span data-ttu-id="41170-281">請參閱[Microsoft 信任中心](https://www.microsoft.com/en-us/trustcenter/default.aspx)有關協力廠商資料要求與[線上服務條款](https://www.microsoft.com/Licensing/product-licensing/products.aspx)] 如需詳細資訊中的 「 外洩的客戶的資料 」 一節。</span><span class="sxs-lookup"><span data-stu-id="41170-281">See the [Microsoft Trust Center](https://www.microsoft.com/en-us/trustcenter/default.aspx) regarding third-party data requests and the "Disclosure of Customer Data" section in the [Online Services Terms](https://www.microsoft.com/Licensing/product-licensing/products.aspx) for more information.</span></span>

#### <a name="how-does-microsoft-ensure-that-a-member-of-its-staff-doesnt-have-standing-access-to-customer-content-in-office-365-applications"></a><span data-ttu-id="41170-282">Microsoft 如何確保其人員的成員都不會有客戶內容常設存取 Office 365 應用程式中？</span><span class="sxs-lookup"><span data-stu-id="41170-282">How does Microsoft ensure that a member of its staff doesn't have standing access to customer content in Office 365 applications?</span></span>

<span data-ttu-id="41170-283">Microsoft 會實作廣泛的預防措施，透過訪問控制系統和偵查措施，以識別和解決規避這些訪問控制系統的嘗試。</span><span class="sxs-lookup"><span data-stu-id="41170-283">Microsoft implements extensive preventive measures through access control systems, and detective measures to identify and address attempts to circumvent these access control systems.</span></span> <span data-ttu-id="41170-284">Office 365 運作時所用的最低權限與剛時間存取原則。</span><span class="sxs-lookup"><span data-stu-id="41170-284">Office 365 operates with the principles of least privilege and just-in-time access.</span></span> <span data-ttu-id="41170-285">因此，沒有 Microsoft 人員需要存取持續的客戶內容的權限。</span><span class="sxs-lookup"><span data-stu-id="41170-285">Therefore, no Microsoft personnel have permission to access customer content on an ongoing basis.</span></span> <span data-ttu-id="41170-286">如果授與權限時，它是有限的持續時間。</span><span class="sxs-lookup"><span data-stu-id="41170-286">If permission is granted, it is for a limited duration.</span></span> 

<span data-ttu-id="41170-287">Office 365 會使用稱為*Lockbox*的存取控制系統，以處理要求的權限，授與執行服務內的作業及系統管理功能的能力。</span><span class="sxs-lookup"><span data-stu-id="41170-287">Office 365 uses an access control system called *Lockbox* to process requests for permissions that grant the ability to perform operational and administrative functions within the service.</span></span> <span data-ttu-id="41170-288">Operator 必須要求存取使用 Lockbox，然後需要採取動作的要求第二個人員的客戶內容 （例如，核准該） 存取權授與之前。</span><span class="sxs-lookup"><span data-stu-id="41170-288">An operator must request access to customer content using Lockbox, which then requires a second person to take action on the request (e.g., approve it) before access is granted.</span></span> <span data-ttu-id="41170-289">該第二個人員無法要求者，且必須指定為核准客戶內容存取權。</span><span class="sxs-lookup"><span data-stu-id="41170-289">That second person can't be the requestor and must be designated to approve access to customer content.</span></span> <span data-ttu-id="41170-290">只有當要求核准運算子並未取得暫時客戶內容存取權。</span><span class="sxs-lookup"><span data-stu-id="41170-290">Only if the request is approved does the operator acquire temporary access to customer content.</span></span> <span data-ttu-id="41170-291">提高權限時間逾期之後，加密箱會撤銷存取權。</span><span class="sxs-lookup"><span data-stu-id="41170-291">After the elevation period expires, Lockbox revokes access.</span></span>

<span data-ttu-id="41170-292">請參閱[線上服務條款](https://www.microsoft.com/licensing/product-licensing/products)] 如需詳細資訊 Microsoft 一般安全性作法。</span><span class="sxs-lookup"><span data-stu-id="41170-292">Please refer to the [Online Services Terms](https://www.microsoft.com/licensing/product-licensing/products) for more details about Microsoft general security practices.</span></span>

#### <a name="under-what-circumstances-do-microsoft-engineers-need-access-to-my-content"></a><span data-ttu-id="41170-293">何種情況下 Microsoft 工程師需要存取我的內容？</span><span class="sxs-lookup"><span data-stu-id="41170-293">Under what circumstances do Microsoft engineers need access to my content?</span></span>

<span data-ttu-id="41170-294">客戶提出要求進行存取的疑難排解支援要求時最常見的案例，在 Microsoft 工程師需要存取的客戶內容。</span><span class="sxs-lookup"><span data-stu-id="41170-294">The most common scenario where Microsoft engineers need access customer content is when the customer makes a support request requiring access for troubleshooting.</span></span> <span data-ttu-id="41170-295">Office 365 的置於原則是服務運作沒有 Microsoft 客戶內容存取權。</span><span class="sxs-lookup"><span data-stu-id="41170-295">A foundational principle of Office 365 is that the service operates without Microsoft access to customer content.</span></span> <span data-ttu-id="41170-296">幾乎所有由 Microsoft 執行的服務作業會完全自動化，並人類參與高度控制和抽象化開客戶內容。</span><span class="sxs-lookup"><span data-stu-id="41170-296">Nearly all service operations performed by Microsoft are fully automated and human involvement is highly controlled and abstracted away from customer content.</span></span> <span data-ttu-id="41170-297">Office 365 的目標是客戶核准的 Microsoft access 的特定要求之前，不需要為支援服務的客戶內容存取權。</span><span class="sxs-lookup"><span data-stu-id="41170-297">The goal for Office 365 is access to customer content to support the service isn't needed until the customer approves a specific request for Microsoft access.</span></span>

#### <a name="i-already-thought-my-data-was-secure-with-the-microsoft-cloud-so-why-do-i-need-customer-lockbox"></a><span data-ttu-id="41170-298">我已經以為我的資料是安全與 Microsoft 雲端，因此我為什麼需要客戶加密箱？</span><span class="sxs-lookup"><span data-stu-id="41170-298">I already thought my data was secure with the Microsoft cloud, so why do I need Customer Lockbox?</span></span>

<span data-ttu-id="41170-299">客戶加密箱藉由提供客戶能夠提供服務作業的明確的存取授權提供額外的控制項。</span><span class="sxs-lookup"><span data-stu-id="41170-299">Customer Lockbox provides an extra layer of control by offering customers the ability to give explicit access authorization for service operations.</span></span> <span data-ttu-id="41170-300">透過示範程序都可供明確資料的存取授權，客戶加密箱也可協助客戶符合 HIPAA 等 FEDRAMP 特定合規性責任。</span><span class="sxs-lookup"><span data-stu-id="41170-300">By demonstrating that procedures are in place for explicit data access authorization, Customer Lockbox also helps customers meet certain compliance obligations such as HIPAA and FEDRAMP.</span></span>
