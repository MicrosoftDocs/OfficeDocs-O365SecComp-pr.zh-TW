---
title: 監督報告
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 5/12/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2a762db5-e1c9-4c09-aa8e-bef49ce97209
description: 使用以查看哪些電子郵件需要規範檢閱監督報表以及誰應該執行它。
ms.openlocfilehash: e18d083c0aad8be945c628516e593462da8e3898
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526351"
---
# <a name="supervision-reports"></a><span data-ttu-id="97285-103">監督報告</span><span class="sxs-lookup"><span data-stu-id="97285-103">Supervision reports</span></span>

<span data-ttu-id="97285-p101">監督原則定義其組織中的通訊需要規範、 檢閱及誰可以執行這些檢閱 （英文）。若要查看檢閱活動層級原則和檢閱者使用監督報告。每個原則，您也可以檢閱活動的目前狀態檢視 live 的統計資料。[解更多關於監督原則](configure-supervision-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="97285-p101">Supervision policies define which communications in your organization need review for compliance, and who will perform those reviews. Use the supervision reports to see the review activity at the policy and reviewer level. For each policy, you can also view live statistics on the current state of review activity. [Learn more about supervision policies ](configure-supervision-policies.md) .</span></span> 
  
> [!NOTE]
> <span data-ttu-id="97285-p102">使用監督原則您的組織需要的 Office 365 E5 訂閱。如果您不具有該對應並想要嘗試監督，您還可以[註冊 Office 365 企業版 E5 的試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="97285-p102">Using supervision policies requires an Office 365 E5 subscription for your organization. If you don't have that plan and want to try supervision, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="97285-110">您可以使用監督報告：</span><span class="sxs-lookup"><span data-stu-id="97285-110">You can use the supervision reports to:</span></span>
  
- <span data-ttu-id="97285-111">確認您的原則運作如您預期。</span><span class="sxs-lookup"><span data-stu-id="97285-111">Verify that your policies are working as you intended.</span></span> 
    
- <span data-ttu-id="97285-112">深入了解多少電子郵件會被識別出供檢閱。</span><span class="sxs-lookup"><span data-stu-id="97285-112">Find out how many emails are being identified for review.</span></span>
    
- <span data-ttu-id="97285-p103">了解如何許多電子郵件不相容與哪些已通過檢閱。這項資訊可協助您決定是否要調整成您的原則或變更檢閱者的數目。</span><span class="sxs-lookup"><span data-stu-id="97285-p103">Find out how many emails aren't compliant and which ones are passing review. This information can help you decide whether to fine-tune your policies or change the number of reviewers.</span></span>
    
## <a name="view-the-supervision-report"></a><span data-ttu-id="97285-115">檢視監督報告</span><span class="sxs-lookup"><span data-stu-id="97285-115">View the Supervision report</span></span>

1. <span data-ttu-id="97285-116">登入[安全性&amp;規範中心](https://protection.office.com/)使用 Office 365 組織中的檢視監督報告的權限的管理帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="97285-116">Sign into the [Security &amp; Compliance Center](https://protection.office.com/) using the credentials for an admin account in your Office 365 organization that has permissions to view supervision reports..</span></span> 
    
2. <span data-ttu-id="97285-p104">移至 [**報表** \> **儀表板**。您會看見的監督報告 widget 及其他報告具有存取權。</span><span class="sxs-lookup"><span data-stu-id="97285-p104">Go to **Reports** \> **Dashboard**. You'll see a reporting widget for supervision and other reports you have access to.</span></span>
    
3. <span data-ttu-id="97285-119">按一下 [以開啟 [詳細資料報告] 頁面上的**監督**widget。</span><span class="sxs-lookup"><span data-stu-id="97285-119">Click the **Supervision** widget to open the detailed report page.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="97285-p105">如果您不可以存取 [**報告**] 頁面上，核取您正在監督檢閱角色群組的成員，[讓組織中可用的監督](configure-supervision-policies.md#SRavailable)所述。要包含在此角色群組可讓您建立及管理監督原則並執行報表。</span><span class="sxs-lookup"><span data-stu-id="97285-p105">If you aren't able to access the **Reports** page, check that you're a member of the Supervisory Review role group, as described in [Make supervision available in your organization](configure-supervision-policies.md#SRavailable). Being included in this role group lets you create and manage supervision polices and run the report.</span></span> 
  
## <a name="how-to-use-the-report"></a><span data-ttu-id="97285-122">如何使用報告</span><span class="sxs-lookup"><span data-stu-id="97285-122">How to use the report</span></span>

<span data-ttu-id="97285-p106">當監督原則識別檢閱的電子郵件時、 電子郵件會傳遞至檢閱者監督資料夾中 Outlook 和 Outlook web app。這份報告會列出每個原則的名稱及通訊數目檢閱程序中的每一階段。</span><span class="sxs-lookup"><span data-stu-id="97285-p106">When a supervision policy identifies an email for review, the email is delivered to the reviewer's Supervision folder in Outlook and Outlook web app. This report lists each policy's name and the number of communications at each stage in the review process.</span></span>
  
<span data-ttu-id="97285-125">使用報告：</span><span class="sxs-lookup"><span data-stu-id="97285-125">Use the report to:</span></span>
  
- <span data-ttu-id="97285-126">檢視資料的所有或特定的原則。</span><span class="sxs-lookup"><span data-stu-id="97285-126">View data for all or specific policies.</span></span>
    
- <span data-ttu-id="97285-127">檢視資料標籤類型分組 （例如符合標準、 Questionable 等等）、 檢閱者或訊息類型。</span><span class="sxs-lookup"><span data-stu-id="97285-127">View data grouped by tag type (such as Compliant, Questionable, etc.), reviewer, or message type.</span></span>
    
- <span data-ttu-id="97285-128">將資料匯出為 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="97285-128">Export data to a CSV file.</span></span>
    
- <span data-ttu-id="97285-129">篩選根據檢閱活動日期、 標記類型、 檢閱、 郵件類型的資料。</span><span class="sxs-lookup"><span data-stu-id="97285-129">Filter data based on review activity date, tag type, reviewer, message type.</span></span>
    
<span data-ttu-id="97285-130">以下是分解您可能會看到 [**標記類型**] 欄中的值。</span><span class="sxs-lookup"><span data-stu-id="97285-130">Here's a breakdown of the values you might see in the **Tag type** column.</span></span> 
  
|<span data-ttu-id="97285-131">**標記類型**</span><span class="sxs-lookup"><span data-stu-id="97285-131">**Tag type**</span></span>|<span data-ttu-id="97285-132">**其意思**</span><span class="sxs-lookup"><span data-stu-id="97285-132">**What it means**</span></span>|
|:-----|:-----|
|<span data-ttu-id="97285-133">不檢閱</span><span class="sxs-lookup"><span data-stu-id="97285-133">Not Reviewed</span></span>  <br/> |<span data-ttu-id="97285-p107">尚未檢視的電子郵件數目。這些電子郵件送交檢閱者監督 Outlook 資料夾中的檢閱。</span><span class="sxs-lookup"><span data-stu-id="97285-p107">The number of emails that have not been reviewed yet. These emails are awaiting review in the reviewer's supervision folder in Outlook.</span></span>  <br/> |
|<span data-ttu-id="97285-136">相容</span><span class="sxs-lookup"><span data-stu-id="97285-136">Compliant</span></span>  <br/> |<span data-ttu-id="97285-p108">檢閱並標示為相容的電子郵件數目。需要進一步的動作。</span><span class="sxs-lookup"><span data-stu-id="97285-p108">The number of emails reviewed and marked as compliant. No further action is needed.</span></span>  <br/> |
|<span data-ttu-id="97285-139">問題</span><span class="sxs-lookup"><span data-stu-id="97285-139">Questionable</span></span>  <br/> |<span data-ttu-id="97285-p109">檢閱並標示問題的電子郵件數目。這可以做為標幟 ；其他檢閱者可協助檢查電子郵件是否需要將正在調查規範。</span><span class="sxs-lookup"><span data-stu-id="97285-p109">The number of emails reviewed and marked questionable. This acts as a flag; other reviewers can help check whether an email needs investigation for compliance.</span></span>  <br/> |
|<span data-ttu-id="97285-142">非相容 （使用中）</span><span class="sxs-lookup"><span data-stu-id="97285-142">Non-Compliant (Active)</span></span>  <br/> |<span data-ttu-id="97285-143">非相容的目前調查檢閱者的電子郵件數目。</span><span class="sxs-lookup"><span data-stu-id="97285-143">The number of non-compliant emails that reviewers are currently investigating.</span></span>  <br/> |
|<span data-ttu-id="97285-144">非相容 （解析）</span><span class="sxs-lookup"><span data-stu-id="97285-144">Non-Compliant (Resolved)</span></span>  <br/> |<span data-ttu-id="97285-145">檢閱者調查並解決非相容電子郵件數目。</span><span class="sxs-lookup"><span data-stu-id="97285-145">The number of non-compliant emails that reviewers investigated and resolved.</span></span>  <br/> |
   
## <a name="more-details"></a><span data-ttu-id="97285-146">更多詳細資料</span><span class="sxs-lookup"><span data-stu-id="97285-146">More details</span></span>

- <span data-ttu-id="97285-147">監督原則必須先佈建才會出現在此報告。</span><span class="sxs-lookup"><span data-stu-id="97285-147">Supervision policies must first be provisioned before they will appear in this report.</span></span>
    
- <span data-ttu-id="97285-p110">如果會刪除原則，仍會顯示歷程資料。不過，它們指定為 「 非存在原則、"並**匯出**函數無法使用。</span><span class="sxs-lookup"><span data-stu-id="97285-p110">If policies are deleted, historical data is still shown. However, they're indicated as a "Non-existent policy", and the **Export** function isn't available.</span></span> 
    
- <span data-ttu-id="97285-p111">如果報表沒有預設顯示的任何資料，則可能是因為目前的日期範圍沒有顯示任何資料。在下列情況下，使用**篩選器**控制項變更的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="97285-p111">If the report doesn't show any data by default, it might be because the current date range doesn't have any data to show. In these cases, use the **Filters** control to change the date range.</span></span> 
    

