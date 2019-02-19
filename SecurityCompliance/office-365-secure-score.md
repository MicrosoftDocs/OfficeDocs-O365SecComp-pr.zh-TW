---
title: Office 365 安全分數
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/13/2019
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c9e7160f-2c34-4bd0-a548-5ddcc862eaef
description: 屬於不知道如何安全您的組織是這麼 in Office 365？安全的分數以下是可協助。安全的分數分析您的組織安全性根據規則活動和 Office 365 中的安全性設定並指派分數。
ms.openlocfilehash: cf272869981dd73e1ceb4bd7180cc16acaed0516
ms.sourcegitcommit: 24659bdb09f49d0ffed180a4b80bbb7c45c2d301
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2019
ms.locfileid: "29992357"
---
# <a name="office-365-secure-score"></a><span data-ttu-id="c98af-105">Office 365 安全分數</span><span class="sxs-lookup"><span data-stu-id="c98af-105">Office 365 Secure Score</span></span>

<span data-ttu-id="c98af-p102">**摘要**屬於不知道如何安全您的組織是這麼 in Office 365？安全的分數以下是可協助。安全的分數分析您的組織安全性根據規則活動和 Office 365 中的安全性設定並指派分數。請閱讀本篇文章以取得安全分數和使用它的概觀。</span><span class="sxs-lookup"><span data-stu-id="c98af-p102">**Summary** Ever wonder how secure your organization really is in Office 365? Secure Score is here to help. Secure Score analyzes your organization's security  based on your regular activities and security settings in Office 365, and assigns a score. Read this article to get an overview of Secure Score and how you can use it.</span></span>
  
## <a name="how-to-get-to-secure-score"></a><span data-ttu-id="c98af-110">如何取得至安全的分數</span><span class="sxs-lookup"><span data-stu-id="c98af-110">How to get to Secure Score</span></span>

<span data-ttu-id="c98af-111">如果您的組織有包含[Office 365 企業版](https://docs.microsoft.com/office365/enterprise/)、 [Microsoft 365 商務](https://docs.microsoft.com/microsoft-365/business/)或 Office 365 企業進階版訂閱且您具有[必要權限](#required-permissions)，您可以檢視您組織的安全分數造訪[https://securescore.office.com](https://securescore.office.com).</span><span class="sxs-lookup"><span data-stu-id="c98af-111">If your organization has a subscription that includes [Office 365 Enterprise](https://docs.microsoft.com/office365/enterprise/), [Microsoft 365 Business](https://docs.microsoft.com/microsoft-365/business/), or Office 365 Business Premium, and you have the [necessary permissions](#required-permissions), you can view your organization's secure score by visiting [https://securescore.office.com](https://securescore.office.com).</span></span> 

<span data-ttu-id="c98af-112">或者，您可以瀏覽安全性 & 規範中心 ([https://protection.office.com](https://protection.office.com)) 中，您將在此找到您目前的分數可提供安全分數 widget。</span><span class="sxs-lookup"><span data-stu-id="c98af-112">Alternatively, you can visit the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), where you'll find a Secure Score widget that provides you with your current score.</span></span>

![安全的分數 widget](media/SecureScoreWidget-o365.png)

<span data-ttu-id="c98af-114">Widget 包含安全分數儀表板的連結。</span><span class="sxs-lookup"><span data-stu-id="c98af-114">The widget includes a link to your Secure Score dashboard.</span></span>

![安全的分數儀表板](media/SecureScore-WelcomeScreen.png)
  
## <a name="how-it-works"></a><span data-ttu-id="c98af-116">運作方式</span><span class="sxs-lookup"><span data-stu-id="c98af-116">How it works</span></span>

<span data-ttu-id="c98af-p103">安全的分數會決定為何您再使用 （例如 OneDrive、 SharePoint 及 Exchange） 的 Office 365 服務比較您的設定和由 Microsoft 建立的基線的活動。您將取得如何為基礎的分數妥善對齊貴組織會使用安全性的最佳作法。您也將取得建議上以提升您的組織分數所能採取的步驟。</span><span class="sxs-lookup"><span data-stu-id="c98af-p103">Secure Score determines what Office 365 services you're using (such as OneDrive, SharePoint, and Exchange) then compares your settings and activities to a baseline established by Microsoft. You'll get a score based on how well aligned your organization is with security best practices. You'll also get recommendations on steps you can take to improve your organization's score.</span></span> 
  
![在 Office 365 安全分數工具動作佇列](media/SecureScore-ActionsToTake.png)
  
<span data-ttu-id="c98af-p104">安全的分數計算您根據您所購買的服務的分數。例如，如果只有購買 Exchange Online 計劃，您將不會計分 SharePoint Online 的安全性功能。分數的分母為套用到您所購買的產品控制項的所有比較基準的總和。分子是的總和的所有控制項的已完成，或部分完成，以滿足該控制項的動作。</span><span class="sxs-lookup"><span data-stu-id="c98af-p104">Secure Score calculates your score based on the services you purchased. For example, if you only purchased an Exchange Online plan, you won't be scored for SharePoint Online security features. The denominator of the score is the sum of all the baselines for the controls that apply to the products you purchased. The numerator is the sum of all the controls for which you completed, or partially completed, the actions to fulfill that control.</span></span>

<span data-ttu-id="c98af-125">依序展開 [要了解功能所需，它將會協助保護您的威脅步驟並多少指引您分數會增加之後遵循建議的動作。</span><span class="sxs-lookup"><span data-stu-id="c98af-125">Expand an action to learn about what steps to take, the threats it'll help protect you from, and how many points your score will increase once you follow the recommendation.</span></span>
  
![在 Office 365 安全分數工具擴充巨集指令](media/SecureScore-DetailedActionToTake.png)
  
<span data-ttu-id="c98af-127">若要查看您的動作的影響在貴組織的安全性，選取 [**分數分析**] 索引標籤和檢閱您的歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="c98af-127">To see the impact of your actions on your organization's security, select the **Score Analyzer** tab and review your history.</span></span> 
  
![Office 365 安全分數工具的分數分析] 索引標籤](media/SecureScore-ScoreAnalyzer-7days.png)
  
<span data-ttu-id="c98af-129">圖表下方您將了依類別排列的分數和動作的清單。</span><span class="sxs-lookup"><span data-stu-id="c98af-129">Below the chart, you'll see a list of scores and actions by category.</span></span> 
  
![顯示所選取的資料點分數分析] 索引標籤上的圖形](media/SecureScore-Analyzer-breakdownbelowchart.png)
 
<span data-ttu-id="c98af-131">您的組織，可以執行會標示為 **[不計分]** 是類的動作，但因為他們未連線至安全的分數，不計分。</span><span class="sxs-lookup"><span data-stu-id="c98af-131">Actions that are labeled as **[Not Scored]** are ones you can perform for your organization, but because they are not connected to Secure Score, they are not scored.</span></span>  

<span data-ttu-id="c98af-p105">**分數分析器**頁面上，按一下 [資料點特定的工作日的然後向下若要深入了解應那天的已完成並不完整動作已變更，請參閱捲動。分數的計算每天一次 (筆 1:00 AM PST)。如果您變更測量巨集指令，分數會自動更新的後一天。延長最多達 48 小時變更，以便反映在您的分數。</span><span class="sxs-lookup"><span data-stu-id="c98af-p105">On the **Score Analyzer** page, click a data point for a specific day, then scroll down to see the completed and incomplete actions for that day to find out what changed. The score is calculated once per day (around 1:00 AM PST). If you make a change to a measured action, the score will automatically update the next day. It takes up to 48 hours for a change to be reflected in your score.</span></span>

<span data-ttu-id="c98af-p106">安全的分數不 express 絕對的量值的方式有可能您所要取得達到。它來表示您要採用功能可以位移要達到的風險的程度。沒有服務可確保您將無法達到、 和安全分數不應該解譯成保證郵件以任何方法。</span><span class="sxs-lookup"><span data-stu-id="c98af-p106">Secure Score does not express an absolute measure of how likely you are to get breached. It expresses the extent to which you have adopted features that can offset the risk of being breached. No service can guarantee that you will not be breached, and the Secure Score should not be interpreted as a guarantee in any way.</span></span>
 
## <a name="how-secure-score-helps"></a><span data-ttu-id="c98af-139">如何協助保護分數</span><span class="sxs-lookup"><span data-stu-id="c98af-139">How Secure Score helps</span></span>

<span data-ttu-id="c98af-p107">使用安全的分數，有助於提高貴組織的安全性狀態 （其中有許多已附加元件購買，但可能不知道） 的 Office 365 中使用的內建的安全性功能。深入了解這些功能可協助提供和平的記住您正在進行保護您的組織從威脅右邊的步驟。</span><span class="sxs-lookup"><span data-stu-id="c98af-p107">With Secure Score, you can help improve your organization's security posture by using the built-in security features in Office 365 (many of which you already purchased but might not be aware of). Learning more about these features can help give you peace of mind that you're taking the right steps to protect your organization from threats.</span></span>
  
<span data-ttu-id="c98af-p108">但是不只是我們 word 針對它。使用安全分數的客戶看過增加五次以上客戶不使用其分數。（其分數增加對應於目前用於組織的安全性功能）。</span><span class="sxs-lookup"><span data-stu-id="c98af-p108">But don't just take our word for it. Customers who are using Secure Score have seen their score increase five times more than customers who aren't using it. (The increase in their score corresponds with the security features being used in their organizations.)</span></span>
  
> [!NOTE]
> <span data-ttu-id="c98af-p109">安全的分數不 express 絕對的量值的方式有可能您所要取得達到。它來表示您要採用控制項可以位移要達到的風險的程度。沒有服務可確保您將無法達到、 和安全分數不應該解譯成保證郵件以任何方法。</span><span class="sxs-lookup"><span data-stu-id="c98af-p109">Secure Score does not express an absolute measure of how likely you are to get breached. It expresses the extent to which you have adopted controls which can offset the risk of being breached. No service can guarantee that you will not be breached, and Secure Score should not be interpreted as a guarantee in any way.</span></span> 
  
## <a name="required-permissions"></a><span data-ttu-id="c98af-148">必要權限</span><span class="sxs-lookup"><span data-stu-id="c98af-148">Required permissions</span></span>

<span data-ttu-id="c98af-149">若要檢視及使用安全分數儀表板，您必須指派一個[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)中的下列角色：</span><span class="sxs-lookup"><span data-stu-id="c98af-149">In order to view and use your Secure Score dashboard, you must be assigned one of the following roles in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles):</span></span>
- <span data-ttu-id="c98af-150">全域管理員</span><span class="sxs-lookup"><span data-stu-id="c98af-150">Global Administrator</span></span>
- <span data-ttu-id="c98af-151">計費管理員</span><span class="sxs-lookup"><span data-stu-id="c98af-151">Billing Administrator</span></span>
- <span data-ttu-id="c98af-152">使用者系統管理員</span><span class="sxs-lookup"><span data-stu-id="c98af-152">User Administrator</span></span>
- <span data-ttu-id="c98af-153">密碼管理員</span><span class="sxs-lookup"><span data-stu-id="c98af-153">Password Administrator</span></span>
- <span data-ttu-id="c98af-154">安全性管理員</span><span class="sxs-lookup"><span data-stu-id="c98af-154">Security Administrator</span></span>
- <span data-ttu-id="c98af-155">安全性讀者</span><span class="sxs-lookup"><span data-stu-id="c98af-155">Security Reader</span></span>
- <span data-ttu-id="c98af-156">Exchange 系統管理員</span><span class="sxs-lookup"><span data-stu-id="c98af-156">Exchange Administrator</span></span>
- <span data-ttu-id="c98af-157">SharePoint 管理員</span><span class="sxs-lookup"><span data-stu-id="c98af-157">SharePoint Administrator</span></span>

 <span data-ttu-id="c98af-158">未指派的管理角色的使用者將無法存取 Secure 分數。</span><span class="sxs-lookup"><span data-stu-id="c98af-158">Users who aren't assigned an admin role won't be able to access Secure Score.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c98af-159">相關主題</span><span class="sxs-lookup"><span data-stu-id="c98af-159">Related topics</span></span>

[<span data-ttu-id="c98af-160">安全性儀表板概觀 （英文)</span><span class="sxs-lookup"><span data-stu-id="c98af-160">Security dashboard overview</span></span>](security-dashboard.md)

[<span data-ttu-id="c98af-161">我有何種訂閱？</span><span class="sxs-lookup"><span data-stu-id="c98af-161">What subscription do I have?</span></span>](https://docs.microsoft.com/office365/admin/admin-overview/what-subscription-do-i-have?view=o365-worldwide)
