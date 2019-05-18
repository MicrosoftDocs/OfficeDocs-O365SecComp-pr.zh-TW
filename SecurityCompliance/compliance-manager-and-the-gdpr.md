---
title: Microsoft Compliance Manager 和 GDPR
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft Compliance Manager 是在 Microsoft 服務信任入口網站中的可用工作流程為基礎的風險評估工具。 合規性管理員可讓您追蹤、 指派及驗證與 Microsoft 雲端服務相關的法規合規性活動。
ms.openlocfilehash: a082d069aced13aa9260a1a856d942c4feb7dd4b
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152088"
---
# <a name="microsoft-compliance-manager-and-the-gdpr"></a><span data-ttu-id="52f2d-104">Microsoft Compliance Manager 和 GDPR</span><span class="sxs-lookup"><span data-stu-id="52f2d-104">Microsoft Compliance Manager and the GDPR</span></span>

<span data-ttu-id="52f2d-105">一般資料保護規定 (GDPR) 准許歐盟所可以影響您的合規性策略，並且託管管理使用者與使用合規性管理員中的客戶資訊所需的動作。</span><span class="sxs-lookup"><span data-stu-id="52f2d-105">The General Data Protection Regulation (GDPR) enacted by the European Union can impact your compliance strategy and mandate actions needed to manage user and customer information used in Compliance Manager.</span></span>

## <a name="user-privacy-settings"></a><span data-ttu-id="52f2d-106">使用者隱私權設定</span><span class="sxs-lookup"><span data-stu-id="52f2d-106">User Privacy settings</span></span>

<span data-ttu-id="52f2d-107">某些法規要求的組織必須能夠刪除使用者歷程記錄資料。</span><span class="sxs-lookup"><span data-stu-id="52f2d-107">Certain regulations require that an organization must be able to delete user history data.</span></span> <span data-ttu-id="52f2d-108">合規性管理員提供可讓系統管理員的**使用者隱私權設定**功能：</span><span class="sxs-lookup"><span data-stu-id="52f2d-108">Compliance Manager provides **User Privacy Settings** functions that allow administrators to:</span></span>
  
- [<span data-ttu-id="52f2d-109">使用者搜尋</span><span class="sxs-lookup"><span data-stu-id="52f2d-109">Search for a user</span></span>](#search-for-a-user)
- [<span data-ttu-id="52f2d-110">匯出帳戶資料歷程記錄的報告</span><span class="sxs-lookup"><span data-stu-id="52f2d-110">Export a report of account data history</span></span>](#export-a-report-of-account-data-history)
- [<span data-ttu-id="52f2d-111">刪除使用者資料歷程記錄</span><span class="sxs-lookup"><span data-stu-id="52f2d-111">Delete user data history</span></span>](#delete-user-data-history)
  
## <a name="search-for-a-user"></a><span data-ttu-id="52f2d-112">搜尋使用者</span><span class="sxs-lookup"><span data-stu-id="52f2d-112">Search for a user</span></span>

<span data-ttu-id="52f2d-113">若要搜尋使用者帳戶：</span><span class="sxs-lookup"><span data-stu-id="52f2d-113">To search for a user account:</span></span>
  
1. <span data-ttu-id="52f2d-114">輸入使用者的電子郵件別名 (左邊的資訊 @ 符號)，然後從右邊的網域尾碼清單中選擇的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="52f2d-114">Enter the user email alias (the information to the left of the @ symbol) and choose the domain name from the  domain suffix list on the right.</span></span> <span data-ttu-id="52f2d-115">組織具有多個已註冊的網域，重複檢查，確認它是正確的網域名稱尾碼。</span><span class="sxs-lookup"><span data-stu-id="52f2d-115">For organizations with multiple registered domains, double check the domain name suffix to ensure that it is correct.</span></span>

2. <span data-ttu-id="52f2d-116">當您已輸入正確的使用者名稱時，選取**搜尋**。</span><span class="sxs-lookup"><span data-stu-id="52f2d-116">When you have the username correctly entered, select **Search**.</span></span>

3. <span data-ttu-id="52f2d-117">不會傳回的使用者帳戶，'找不到使用者' 會顯示在頁面上。</span><span class="sxs-lookup"><span data-stu-id="52f2d-117">For user accounts not returned, 'User not found' is displayed on the page.</span></span> <span data-ttu-id="52f2d-118">檢查使用者的電子郵件地址資訊並進行修正為必要。</span><span class="sxs-lookup"><span data-stu-id="52f2d-118">Check the user's email address information and make corrections as necessary.</span></span> <span data-ttu-id="52f2d-119">若要重試，選取**搜尋**。</span><span class="sxs-lookup"><span data-stu-id="52f2d-119">To retry, select **Search**.</span></span>

4. <span data-ttu-id="52f2d-120">使用者帳戶傳回，從**搜尋**按鈕變更，以**純**文字。</span><span class="sxs-lookup"><span data-stu-id="52f2d-120">For user accounts returned, the text of the button changes from **Search** to **Clear**.</span></span> <span data-ttu-id="52f2d-121">這表示傳回的使用者帳戶是其他函數的作業系統內容，這些函數套用到此使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="52f2d-121">This indicates that the returned user account is the operating context for the additional functions and that these functions apply to this user account.</span></span>

5. <span data-ttu-id="52f2d-122">若要清除搜尋結果，並搜尋不同的使用者，請選取 [**清除**]。</span><span class="sxs-lookup"><span data-stu-id="52f2d-122">To clear search results and search for a different user, select **Clear**.</span></span>

## <a name="export-a-report-of-account-data-history"></a><span data-ttu-id="52f2d-123">匯出帳戶資料歷程記錄的報告</span><span class="sxs-lookup"><span data-stu-id="52f2d-123">Export a report of account data history</span></span>

<span data-ttu-id="52f2d-124">識別每個使用者帳戶，您可能會產生報告的相依性連結到此帳戶。</span><span class="sxs-lookup"><span data-stu-id="52f2d-124">For each user account identified, you can generate a report of dependencies linked to this account.</span></span> <span data-ttu-id="52f2d-125">此資訊可讓您重新指派開啟動作項目或確保先前上傳的辨識項的存取。</span><span class="sxs-lookup"><span data-stu-id="52f2d-125">This information allows you to reassign open Action Items or ensure access to previously uploaded evidence.</span></span>
  
 <span data-ttu-id="52f2d-126">若要產生並匯出報告：</span><span class="sxs-lookup"><span data-stu-id="52f2d-126">To generate and export a report:</span></span>
  
1. <span data-ttu-id="52f2d-127">選取 [產生，並下載合規性管理員控制項動作項目目前指派給傳回的使用者帳戶，並由該使用者上傳的文件清單的報表的 [**匯出**]。</span><span class="sxs-lookup"><span data-stu-id="52f2d-127">Select **Export** to generate and download a report of the Compliance Manager control Action Items currently assigned to the returned user account, and the list of documents uploaded by that user.</span></span> <span data-ttu-id="52f2d-128">如果沒有指派的動作或上傳的文件，錯誤訊息指出 「 沒有為此使用者的資料 」。</span><span class="sxs-lookup"><span data-stu-id="52f2d-128">If there are no assigned actions or uploaded documents, an error message states "No data for this user".</span></span>

2. <span data-ttu-id="52f2d-129">報表的作用中瀏覽器視窗背景中下載-如果您沒有看到下載快顯功能表，您想要檢查您的瀏覽器下載記錄。</span><span class="sxs-lookup"><span data-stu-id="52f2d-129">The report downloads in the background of the active browser window — if you don't see a download popup that you want to check your browser download history.</span></span>

3. <span data-ttu-id="52f2d-130">開啟文件以檢視報告資料。</span><span class="sxs-lookup"><span data-stu-id="52f2d-130">Open the document to review the report data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="52f2d-131">這並不會保留並顯示動作項目指派歷程記錄的狀態變更的歷程報告。</span><span class="sxs-lookup"><span data-stu-id="52f2d-131">This is not a historical report that retains and displays state changes to Action Item assignment history.</span></span> <span data-ttu-id="52f2d-132">產生的報告是控制項動作項目指派報告執行的時間 （寫入至報表的日期和時間戳記） 的快照。</span><span class="sxs-lookup"><span data-stu-id="52f2d-132">The generated report is a snapshot of the control Action Items assigned at the time that the report is run (date and time stamp written into the report).</span></span> <span data-ttu-id="52f2d-133">例如，動作項目任何後續重新指派不同的快照集報表資料如果導致相同的使用者再次產生此報告。</span><span class="sxs-lookup"><span data-stu-id="52f2d-133">For example, any subsequent reassignment of Action Items result in different snapshot report data if this report is generated again for the same user.</span></span>
  
## <a name="delete-user-data-history"></a><span data-ttu-id="52f2d-134">刪除使用者資料歷程記錄</span><span class="sxs-lookup"><span data-stu-id="52f2d-134">Delete user data history</span></span>

<span data-ttu-id="52f2d-135">設定所有控制項動作項目指派為 「 未分派' 所傳回的使用者。</span><span class="sxs-lookup"><span data-stu-id="52f2d-135">Sets all control Action Items assigned to the returned user to 'unassigned'.</span></span> <span data-ttu-id="52f2d-136">會設定任何由 '使用者移除' 所傳回使用者上傳的文件的**上傳的**值。</span><span class="sxs-lookup"><span data-stu-id="52f2d-136">Sets the **uploaded by** value for any documents uploaded by the returned user to 'user removed'.</span></span>
  
<span data-ttu-id="52f2d-137">若要刪除的使用者帳戶動作項目和文件上傳記錄：</span><span class="sxs-lookup"><span data-stu-id="52f2d-137">To delete the user account Action Item and document upload history:</span></span>
  
1. <span data-ttu-id="52f2d-138">選取 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="52f2d-138">Select **Delete**.</span></span>

    <span data-ttu-id="52f2d-139">會顯示確認對話方塊中，「*這將會移除所有控制項動作項目指派與所選使用者的文件上傳歷程記錄。此巨集指令是永久性動作。您是否確定要繼續？*」</span><span class="sxs-lookup"><span data-stu-id="52f2d-139">A confirmation dialog is displayed, "*This removes all control Action Item assignments and the document upload history for the selected user. This action is permanent. Are you sure you want to continue?*"</span></span>

2. <span data-ttu-id="52f2d-140">若要選取 [**確定]** 繼續，否則請選擇**取消**。</span><span class="sxs-lookup"><span data-stu-id="52f2d-140">To continue select **OK**, otherwise select **Cancel**.</span></span>