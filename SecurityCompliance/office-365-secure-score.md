---
title: Office 365 安全分數
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/13/2019
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c9e7160f-2c34-4bd0-a548-5ddcc862eaef
description: 屬於不知道如何保護您的組織確實是在 Office 365？ 安全分數以下是可幫助。 安全分數分析根據您的日常活動和 Office 365 中的安全性設定貴組織的安全性，並為其打分數。
ms.openlocfilehash: dd0dc87910853eba9f2ec3ec6752e857462b46e5
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262443"
---
# <a name="office-365-secure-score"></a><span data-ttu-id="d3eef-105">Office 365 安全分數</span><span class="sxs-lookup"><span data-stu-id="d3eef-105">Office 365 Secure Score</span></span>

<span data-ttu-id="d3eef-106">**摘要**屬於不知道如何保護您的組織確實是在 Office 365？</span><span class="sxs-lookup"><span data-stu-id="d3eef-106">**Summary** Ever wonder how secure your organization really is in Office 365?</span></span> <span data-ttu-id="d3eef-107">安全分數以下是可幫助。</span><span class="sxs-lookup"><span data-stu-id="d3eef-107">Secure Score is here to help.</span></span> <span data-ttu-id="d3eef-108">安全分數分析根據您的日常活動和 Office 365 中的安全性設定貴組織的安全性，並為其打分數。</span><span class="sxs-lookup"><span data-stu-id="d3eef-108">Secure Score analyzes your organization's security  based on your regular activities and security settings in Office 365, and assigns a score.</span></span> <span data-ttu-id="d3eef-109">閱讀本篇文章以取得安全分數，以及您如何使用它的概觀。</span><span class="sxs-lookup"><span data-stu-id="d3eef-109">Read this article to get an overview of Secure Score and how you can use it.</span></span>
  
## <a name="how-to-get-to-secure-score"></a><span data-ttu-id="d3eef-110">如何取得安全分數</span><span class="sxs-lookup"><span data-stu-id="d3eef-110">How to get to Secure Score</span></span>

<span data-ttu-id="d3eef-111">如果您的組織有包含[Office 365 企業版](https://docs.microsoft.com/office365/enterprise/)、 [Microsoft 365 商務版](https://docs.microsoft.com/microsoft-365/business/)或 Office 365 商務進階版訂閱，且您具有[必要權限](#required-permissions)，您可以造訪檢視貴組織的安全分數[https://securescore.office.com](https://securescore.office.com).</span><span class="sxs-lookup"><span data-stu-id="d3eef-111">If your organization has a subscription that includes [Office 365 Enterprise](https://docs.microsoft.com/office365/enterprise/), [Microsoft 365 Business](https://docs.microsoft.com/microsoft-365/business/), or Office 365 Business Premium, and you have the [necessary permissions](#required-permissions), you can view your organization's secure score by visiting [https://securescore.office.com](https://securescore.office.com).</span></span> 

<span data-ttu-id="d3eef-112">或者，您可以造訪安全性 & 合規性中心 ([https://protection.office.com](https://protection.office.com))，您可以在其中找到您目前的分數為您提供安全分數小工具。</span><span class="sxs-lookup"><span data-stu-id="d3eef-112">Alternatively, you can visit the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), where you'll find a Secure Score widget that provides you with your current score.</span></span>

![安全分數小工具](media/SecureScoreWidget-o365.png)

<span data-ttu-id="d3eef-114">[] 小工具包括安全分數儀表板的連結。</span><span class="sxs-lookup"><span data-stu-id="d3eef-114">The widget includes a link to your Secure Score dashboard.</span></span>

![安全分數儀表板](media/SecureScore-WelcomeScreen.png)
  
## <a name="how-it-works"></a><span data-ttu-id="d3eef-116">運作方式</span><span class="sxs-lookup"><span data-stu-id="d3eef-116">How it works</span></span>

<span data-ttu-id="d3eef-117">安全分數會決定您接著使用 （例如 OneDrive、 SharePoint 和 Exchange） 哪些 Office 365 服務比較您的設定與 Microsoft 所建立的基線的活動。</span><span class="sxs-lookup"><span data-stu-id="d3eef-117">Secure Score determines what Office 365 services you're using (such as OneDrive, SharePoint, and Exchange) then compares your settings and activities to a baseline established by Microsoft.</span></span> <span data-ttu-id="d3eef-118">您會看到如何為基礎的分數也對齊您的組織是安全性最佳做法。</span><span class="sxs-lookup"><span data-stu-id="d3eef-118">You'll get a score based on how well aligned your organization is with security best practices.</span></span> <span data-ttu-id="d3eef-119">您也會收到建議改善貴組織的分數時可採取的步驟。</span><span class="sxs-lookup"><span data-stu-id="d3eef-119">You'll also get recommendations on steps you can take to improve your organization's score.</span></span> 
  
![在 Office 365 安全分數工具中的動作佇列](media/SecureScore-ActionsToTake.png)
  
<span data-ttu-id="d3eef-121">安全分數會計算您根據您購買服務的分數。</span><span class="sxs-lookup"><span data-stu-id="d3eef-121">Secure Score calculates your score based on the services you purchased.</span></span> <span data-ttu-id="d3eef-122">例如，如果您只是購買 Exchange Online 計劃，您將不會計分 SharePoint Online 的安全性功能。</span><span class="sxs-lookup"><span data-stu-id="d3eef-122">For example, if you only purchased an Exchange Online plan, you won't be scored for SharePoint Online security features.</span></span> <span data-ttu-id="d3eef-123">分數的分母是適用於您購買的產品的控制項的所有基準線的總和。</span><span class="sxs-lookup"><span data-stu-id="d3eef-123">The denominator of the score is the sum of all the baselines for the controls that apply to the products you purchased.</span></span> <span data-ttu-id="d3eef-124">分數之分子是加總的所有控制項的已完成，或部分完成，以滿足該控制項的動作。</span><span class="sxs-lookup"><span data-stu-id="d3eef-124">The numerator is the sum of all the controls for which you completed, or partially completed, the actions to fulfill that control.</span></span>

<span data-ttu-id="d3eef-125">依序展開 [要深入了解哪些步驟來執行，它將會協助保護您的潛在威脅及多少指向您的分數會增加一旦您遵循建議的動作。</span><span class="sxs-lookup"><span data-stu-id="d3eef-125">Expand an action to learn about what steps to take, the threats it'll help protect you from, and how many points your score will increase once you follow the recommendation.</span></span>
  
![Office 365 安全分數工具展開巨集指令](media/SecureScore-DetailedActionToTake.png)
  
<span data-ttu-id="d3eef-127">若要查看您的動作影響貴組織的安全性，選取 [**分數 Analyzer** ] 索引標籤，檢閱您的歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="d3eef-127">To see the impact of your actions on your organization's security, select the **Score Analyzer** tab and review your history.</span></span> 
  
![Office 365 安全分數工具分數 Analyzer] 索引標籤](media/SecureScore-ScoreAnalyzer-7days.png)
  
<span data-ttu-id="d3eef-129">下方圖表中，您會看到分數和動作的清單依類別。</span><span class="sxs-lookup"><span data-stu-id="d3eef-129">Below the chart, you'll see a list of scores and actions by category.</span></span> 
  
![圖形顯示所選取的資料點分數 Analyzer] 索引標籤上](media/SecureScore-Analyzer-breakdownbelowchart.png)
 
<span data-ttu-id="d3eef-131">您可以執行動作，會標示為 **[不計分]** 的和為您的組織，但未連線到安全分數，因為它們不會被記錄。</span><span class="sxs-lookup"><span data-stu-id="d3eef-131">Actions that are labeled as **[Not Scored]** are ones you can perform for your organization, but because they are not connected to Secure Score, they are not scored.</span></span>  

<span data-ttu-id="d3eef-132">在**分數分析器**] 頁面上，按一下 [資料點的特定一天，然後向下若要找出該日的已完成且未完成動作變更，請參閱捲動。</span><span class="sxs-lookup"><span data-stu-id="d3eef-132">On the **Score Analyzer** page, click a data point for a specific day, then scroll down to see the completed and incomplete actions for that day to find out what changed.</span></span> <span data-ttu-id="d3eef-133">分數的計算一次每日 (大約 1:00 AM PST)。</span><span class="sxs-lookup"><span data-stu-id="d3eef-133">The score is calculated once per day (around 1:00 AM PST).</span></span> <span data-ttu-id="d3eef-134">如果您變更測量的巨集指令，分數會自動更新的下一天。</span><span class="sxs-lookup"><span data-stu-id="d3eef-134">If you make a change to a measured action, the score will automatically update the next day.</span></span> <span data-ttu-id="d3eef-135">花費最多在 48 小時內的變更會反映在您的分數。</span><span class="sxs-lookup"><span data-stu-id="d3eef-135">It takes up to 48 hours for a change to be reflected in your score.</span></span>

<span data-ttu-id="d3eef-136">安全分數不 express 絕對的量值的方式可能您是要取得外洩。</span><span class="sxs-lookup"><span data-stu-id="d3eef-136">Secure Score does not express an absolute measure of how likely you are to get breached.</span></span> <span data-ttu-id="d3eef-137">它來表示您要採用可以位移正在外洩的風險的功能範圍。</span><span class="sxs-lookup"><span data-stu-id="d3eef-137">It expresses the extent to which you have adopted features that can offset the risk of being breached.</span></span> <span data-ttu-id="d3eef-138">您將不會外洩，以及安全分數不應該解譯成保證郵件可以以任何方法，可確保沒有任何服務。</span><span class="sxs-lookup"><span data-stu-id="d3eef-138">No service can guarantee that you will not be breached, and the Secure Score should not be interpreted as a guarantee in any way.</span></span>
 
## <a name="how-secure-score-helps"></a><span data-ttu-id="d3eef-139">安全分數如何協助</span><span class="sxs-lookup"><span data-stu-id="d3eef-139">How Secure Score helps</span></span>

<span data-ttu-id="d3eef-140">安全分數，您可以協助提升貴組織的安全性狀態 （其中有許多您已購買，但可能不知道） 的 Office 365 中使用的內建安全性功能。</span><span class="sxs-lookup"><span data-stu-id="d3eef-140">With Secure Score, you can help improve your organization's security posture by using the built-in security features in Office 365 (many of which you already purchased but might not be aware of).</span></span> <span data-ttu-id="d3eef-141">深入了解這些功能可協助讓您和平您要將正確的步驟來防止威脅保護您的組織的想法。</span><span class="sxs-lookup"><span data-stu-id="d3eef-141">Learning more about these features can help give you peace of mind that you're taking the right steps to protect your organization from threats.</span></span>
  
<span data-ttu-id="d3eef-142">但不只需要為其我們 word。</span><span class="sxs-lookup"><span data-stu-id="d3eef-142">But don't just take our word for it.</span></span> <span data-ttu-id="d3eef-143">使用安全分數客戶過增加共進行五次超過不使用它的客戶其分數。</span><span class="sxs-lookup"><span data-stu-id="d3eef-143">Customers who are using Secure Score have seen their score increase five times more than customers who aren't using it.</span></span> <span data-ttu-id="d3eef-144">（其分數增加對應於其組織中正在使用的安全性功能）。</span><span class="sxs-lookup"><span data-stu-id="d3eef-144">(The increase in their score corresponds with the security features being used in their organizations.)</span></span>
  
> [!NOTE]
> <span data-ttu-id="d3eef-145">安全分數不 express 絕對的量值的方式可能您是要取得外洩。</span><span class="sxs-lookup"><span data-stu-id="d3eef-145">Secure Score does not express an absolute measure of how likely you are to get breached.</span></span> <span data-ttu-id="d3eef-146">它來表示您要採用可以位移正在外洩的風險的控制項的程度。</span><span class="sxs-lookup"><span data-stu-id="d3eef-146">It expresses the extent to which you have adopted controls which can offset the risk of being breached.</span></span> <span data-ttu-id="d3eef-147">您將不會外洩，以及安全分數不應該解譯成保證郵件可以以任何方法，可確保沒有任何服務。</span><span class="sxs-lookup"><span data-stu-id="d3eef-147">No service can guarantee that you will not be breached, and Secure Score should not be interpreted as a guarantee in any way.</span></span> 
  
## <a name="required-permissions"></a><span data-ttu-id="d3eef-148">必要的權限</span><span class="sxs-lookup"><span data-stu-id="d3eef-148">Required permissions</span></span>

<span data-ttu-id="d3eef-149">若要檢視和使用安全分數儀表板，您必須獲指派其中一個[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)中的下列角色：</span><span class="sxs-lookup"><span data-stu-id="d3eef-149">In order to view and use your Secure Score dashboard, you must be assigned one of the following roles in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles):</span></span>
- <span data-ttu-id="d3eef-150">全域管理員</span><span class="sxs-lookup"><span data-stu-id="d3eef-150">Global Administrator</span></span>
- <span data-ttu-id="d3eef-151">計費系統管理員</span><span class="sxs-lookup"><span data-stu-id="d3eef-151">Billing Administrator</span></span>
- <span data-ttu-id="d3eef-152">使用者系統管理員</span><span class="sxs-lookup"><span data-stu-id="d3eef-152">User Administrator</span></span>
- <span data-ttu-id="d3eef-153">密碼管理員</span><span class="sxs-lookup"><span data-stu-id="d3eef-153">Password Administrator</span></span>
- <span data-ttu-id="d3eef-154">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="d3eef-154">Security Administrator</span></span>
- <span data-ttu-id="d3eef-155">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="d3eef-155">Security Reader</span></span>
- <span data-ttu-id="d3eef-156">Exchange 系統管理員</span><span class="sxs-lookup"><span data-stu-id="d3eef-156">Exchange Administrator</span></span>
- <span data-ttu-id="d3eef-157">SharePoint 系統管理員</span><span class="sxs-lookup"><span data-stu-id="d3eef-157">SharePoint Administrator</span></span>

 <span data-ttu-id="d3eef-158">不會被指派系統管理員角色的使用者將無法存取安全分數。</span><span class="sxs-lookup"><span data-stu-id="d3eef-158">Users who aren't assigned an admin role won't be able to access Secure Score.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d3eef-159">相關主題</span><span class="sxs-lookup"><span data-stu-id="d3eef-159">Related topics</span></span>

[<span data-ttu-id="d3eef-160">安全性儀表板概觀</span><span class="sxs-lookup"><span data-stu-id="d3eef-160">Security dashboard overview</span></span>](security-dashboard.md)

[<span data-ttu-id="d3eef-161">我有何種訂閱？</span><span class="sxs-lookup"><span data-stu-id="d3eef-161">What subscription do I have?</span></span>](https://docs.microsoft.com/office365/admin/admin-overview/what-subscription-do-i-have?view=o365-worldwide)
