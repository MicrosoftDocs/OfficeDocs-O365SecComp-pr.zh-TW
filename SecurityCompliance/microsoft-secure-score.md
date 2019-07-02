---
title: Microsoft 安全分數
description: 說明 microsoft 365 安全性中心內的 Microsoft 安全分數、如何計算詳細資料, 以及安全性系統管理員可以預期使用何種方式。
keywords: 安全性、惡意程式碼、Microsoft 365、M365、安全分數、安全性中心、改進動作
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 27a9d137bde0dd23be8824d94a25364f89706563
ms.sourcegitcommit: b9d8a43cb3afcdc8820bc9470c5707eff8fc6616
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/11/2019
ms.locfileid: "34852777"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="4a63a-104">Microsoft 安全分數</span><span class="sxs-lookup"><span data-stu-id="4a63a-104">Microsoft Secure Score</span></span>

>[!IMPORTANT]
><span data-ttu-id="4a63a-105">某些資訊與 prereleased 產品相關, 可能會在正式發行之前充分修改。</span><span class="sxs-lookup"><span data-stu-id="4a63a-105">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="4a63a-106">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="4a63a-106">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="4a63a-107">透過 microsoft 365 安全中心的 Microsoft 安全分數, 您可以更深入地瞭解及控制組織的安全性狀況。</span><span class="sxs-lookup"><span data-stu-id="4a63a-107">With Microsoft Secure Score in the Microsoft 365 security center, you can have increased visibility and control over your organization’s security posture.</span></span> <span data-ttu-id="4a63a-108">您可以從集中式儀表板監視和改善 Microsoft 365 身分識別、資料、應用程式、裝置及基礎結構的安全性。</span><span class="sxs-lookup"><span data-stu-id="4a63a-108">From a centralized dashboard you can monitor and improve the security for your Microsoft 365 identities, data, apps, devices, and infrastructure.</span></span>

<span data-ttu-id="4a63a-109">Microsoft 安全分數為您提供穩健的視覺效果、與其他 Microsoft 產品的整合、與其他公司的分數比較、依類別篩選, 以及更多。</span><span class="sxs-lookup"><span data-stu-id="4a63a-109">Microsoft Secure Score gives you robust visualizations, integration with other Microsoft products, comparison of your score with other companies, filtering by category, and much more.</span></span> <span data-ttu-id="4a63a-110">透過工具, 您可以在組織內完成安全性改進動作, 並追蹤分數的歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="4a63a-110">With the tool, you can complete security improvement actions within your organization and track the history of your score.</span></span> <span data-ttu-id="4a63a-111">分數也可以反映協力廠商解決方案如何解決建議的改進動作。</span><span class="sxs-lookup"><span data-stu-id="4a63a-111">The score can also reflect when third-party solutions have addressed recommended improvement actions.</span></span>  

## <a name="how-it-works"></a><span data-ttu-id="4a63a-112">運作方式</span><span class="sxs-lookup"><span data-stu-id="4a63a-112">How it works</span></span>

<span data-ttu-id="4a63a-113">您可以指定點來設定建議的安全性功能、執行安全性相關工作 (例如查看報表), 或使用協力廠商應用程式或軟體來解決改善動作。</span><span class="sxs-lookup"><span data-stu-id="4a63a-113">You are given points for configuring recommended security features, performing security-related tasks (such as viewing reports), or addressing the improvement action with a third-party application or software.</span></span> <span data-ttu-id="4a63a-114">部分完成的某些動作會分數, 例如為您的使用者啟用多重要素驗證 (MFA)。</span><span class="sxs-lookup"><span data-stu-id="4a63a-114">Some actions are scored for partial completion, like enabling multi-factor authentication (MFA) for your users.</span></span> <span data-ttu-id="4a63a-115">安全性應始終與可用性平衡, 而不是每個建議適用于您的環境。</span><span class="sxs-lookup"><span data-stu-id="4a63a-115">Security should always be balanced with usability, and not every recommendation will work for your environment.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="4a63a-116">必要的權限</span><span class="sxs-lookup"><span data-stu-id="4a63a-116">Required permissions</span></span>

<span data-ttu-id="4a63a-117">目前, 若要查看 Microsoft 安全分數, 您必須在 Azure Active Directory 中指派下列其中一個角色:</span><span class="sxs-lookup"><span data-stu-id="4a63a-117">Currently, to view Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory:</span></span>

* <span data-ttu-id="4a63a-118">全域管理員</span><span class="sxs-lookup"><span data-stu-id="4a63a-118">Global Administrator</span></span>
* <span data-ttu-id="4a63a-119">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="4a63a-119">Security Administrator</span></span>
* <span data-ttu-id="4a63a-120">安全性讀取器</span><span class="sxs-lookup"><span data-stu-id="4a63a-120">Security Reader</span></span>

## <a name="rich-experiences--additional-security-recommendations"></a><span data-ttu-id="4a63a-121">豐富的體驗 & 其他安全性建議</span><span class="sxs-lookup"><span data-stu-id="4a63a-121">Rich experiences & additional security recommendations</span></span>

<span data-ttu-id="4a63a-122">在 Microsoft 安全分數中, 我們已新增 Azure AD、Intune 和 Cloud App 安全性的建議, 並提供來自 Azure Security Center 和 Microsoft Defender ATP 的建議。</span><span class="sxs-lookup"><span data-stu-id="4a63a-122">In Microsoft Secure Score, we’ve added recommendations from Azure AD, Intune, and Cloud App Security, with recommendations from Azure Security Center and Microsoft Defender ATP coming soon.</span></span> <span data-ttu-id="4a63a-123">我們也新增更多 Office 365 安全性建議。</span><span class="sxs-lookup"><span data-stu-id="4a63a-123">We've also added even more Office 365 security recommendations.</span></span> <span data-ttu-id="4a63a-124">深入瞭解更多的 Microsoft 產品和服務集合, 讓您能夠自信地報告您組織的安全性健康情況的管理。</span><span class="sxs-lookup"><span data-stu-id="4a63a-124">With additional insights and more visibility into a broader set of Microsoft products and services, you can feel confident reporting up to management about your organization’s security health.</span></span> <span data-ttu-id="4a63a-125">您也可以使用[Microsoft GRAPH API](https://docs.microsoft.com/graph/api/resources/securescores?view=graph-rest-beta)取得分數。</span><span class="sxs-lookup"><span data-stu-id="4a63a-125">You can also get your score using the [Microsoft Graph API](https://docs.microsoft.com/graph/api/resources/securescores?view=graph-rest-beta).</span></span>

<span data-ttu-id="4a63a-126">為了協助您更快速地瞭解所需的資訊, Microsoft 建議會組織成群組:</span><span class="sxs-lookup"><span data-stu-id="4a63a-126">To help you the information you need more quickly, Microsoft recommendations are organized into groups:</span></span>

* <span data-ttu-id="4a63a-127">身分識別 (您的 Azure AD 帳戶和角色的保護狀態)</span><span class="sxs-lookup"><span data-stu-id="4a63a-127">Identity (protection state of your Azure AD accounts and roles)</span></span>
* <span data-ttu-id="4a63a-128">資料 (Office 365 檔的保護狀態)</span><span class="sxs-lookup"><span data-stu-id="4a63a-128">Data (protection state of your Office 365 documents)</span></span>
* <span data-ttu-id="4a63a-129">裝置 (您的裝置的保護狀態;Microsoft Defender ATP 改進動作即將推出)</span><span class="sxs-lookup"><span data-stu-id="4a63a-129">Device (protection state of your devices; Microsoft Defender ATP improvement actions coming soon)</span></span>
* <span data-ttu-id="4a63a-130">應用程式 (您的電子郵件和雲端應用程式的保護狀態)</span><span class="sxs-lookup"><span data-stu-id="4a63a-130">App (protection state of your email and cloud apps)</span></span>
* <span data-ttu-id="4a63a-131">基礎結構 (您的 Azure 資源的保護狀態; 即將推出)</span><span class="sxs-lookup"><span data-stu-id="4a63a-131">Infrastructure (protection state of your Azure resources; coming soon)</span></span>

<span data-ttu-id="4a63a-132">在 [Microsoft 安全分數總覽] 頁面中, 您可以看到各群組之間的分割點, 以及可用的點數。</span><span class="sxs-lookup"><span data-stu-id="4a63a-132">In the Microsoft Secure Score overview page, you can see how points are split between these groups and what points are available.</span></span> <span data-ttu-id="4a63a-133">[總覽] 頁面也是取得整體分數、安全分數與基準比較的歷史趨勢, 以及可用於改善分數的優先順序改進動作的完整視圖的位置。</span><span class="sxs-lookup"><span data-stu-id="4a63a-133">The overview page is also the place to get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span> <span data-ttu-id="4a63a-134">您可以使用此資料來採取動作, 並對安全性狀況產生很大的差異。</span><span class="sxs-lookup"><span data-stu-id="4a63a-134">You can use this data to act and make big differences in your security posture.</span></span>  

<span data-ttu-id="4a63a-135">![M365 首頁](./media/secure-score/homepage-original.png)
*圖 1: Microsoft 安全分數概覽頁面*</span><span class="sxs-lookup"><span data-stu-id="4a63a-135">![M365 homepage](./media/secure-score/homepage-original.png)
*Figure 1: Microsoft Secure Score overview page*</span></span>

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="4a63a-136">採取動作以提升分數</span><span class="sxs-lookup"><span data-stu-id="4a63a-136">Take action to improve your score</span></span>

<span data-ttu-id="4a63a-137">[改進動作] 索引標籤會列出所有適用于租使用者的安全性建議及其狀態 (已完成、未完成、透過協力廠商解決, 以及被忽略)。</span><span class="sxs-lookup"><span data-stu-id="4a63a-137">The improvement actions tab lists all the security recommendations applicable to your tenant along with their status (completed, not completed, resolved through third party, and ignored).</span></span> <span data-ttu-id="4a63a-138">您可以搜尋、篩選及群組所有控制項。</span><span class="sxs-lookup"><span data-stu-id="4a63a-138">You can search, filter, and group all the controls.</span></span>  <span data-ttu-id="4a63a-139">排名是以 Microsoft 評估安全性價值和完成工作為基礎。</span><span class="sxs-lookup"><span data-stu-id="4a63a-139">Ranking is based on Microsoft’s evaluation of both security value and effort to complete.</span></span>

<span data-ttu-id="4a63a-140">Microsoft 安全分數不會追蹤標為 [未計分] 的動作。</span><span class="sxs-lookup"><span data-stu-id="4a63a-140">Actions labeled as [Not Scored] are not tracked by Microsoft Secure Score.</span></span> <span data-ttu-id="4a63a-141">您仍然可以採取動作, 但完成它們不會影響您的分數。</span><span class="sxs-lookup"><span data-stu-id="4a63a-141">You can still take action but completing them will not affect your score.</span></span> <span data-ttu-id="4a63a-142">如果在未來的 Microsoft 安全分數會追蹤某個動作, 而且您已經完成, 您的安全分數就會自動反映所做的變更。</span><span class="sxs-lookup"><span data-stu-id="4a63a-142">If an action becomes tracked by Microsoft Secure Score in the future and you have already completed it, your secure score will automatically reflect the change.</span></span>

<span data-ttu-id="4a63a-143">當您按一下 [改善動作] 時, 會顯示 [飛出] 動作。</span><span class="sxs-lookup"><span data-stu-id="4a63a-143">When you click on an improvement action, a fly out appears.</span></span> <span data-ttu-id="4a63a-144">若要完成此動作, 您有幾個選項:</span><span class="sxs-lookup"><span data-stu-id="4a63a-144">To complete the action, you have a few options:</span></span>

1. <span data-ttu-id="4a63a-145">選取 [**查看設定**], 以移至 [設定] 畫面並進行變更。</span><span class="sxs-lookup"><span data-stu-id="4a63a-145">Select **View settings** to go the configuration screen and make the change.</span></span> <span data-ttu-id="4a63a-146">接著, 您將會看到需要採取動作的點, 會在飛出的頂端顯示。最多可能需要24小時才能更新點數。</span><span class="sxs-lookup"><span data-stu-id="4a63a-146">You will then gain the points that the action is worth, visible at the top of the fly out. Points may take up to 24 hours to update.</span></span>

2. <span data-ttu-id="4a63a-147">選取 [**透過協力廠商解析**], 因為已由協力廠商應用程式或軟體解決 [改善] 動作。</span><span class="sxs-lookup"><span data-stu-id="4a63a-147">Select **Resolve through third party** because the improvement action has already been addressed by a third-party application or software.</span></span> <span data-ttu-id="4a63a-148">您可以取得該動作值得的要點, 讓您的安全分數更清楚反映整體安全性狀況。</span><span class="sxs-lookup"><span data-stu-id="4a63a-148">You will gain the points that the action is worth, so your secure score better reflects your overall security posture.</span></span> <span data-ttu-id="4a63a-149">如果協力廠商不再涵蓋該控制項, 您可以將 [改善] 動作標示為 [未完成]。</span><span class="sxs-lookup"><span data-stu-id="4a63a-149">If a third party no longer covers the control, you can mark the improvement action as not complete.</span></span> <span data-ttu-id="4a63a-150">請記住, 如果 [改善] 動作被標示為透過協力廠商解決, 則 Microsoft 將無法看到分數需求是否符合。</span><span class="sxs-lookup"><span data-stu-id="4a63a-150">Please keep in mind, Microsoft will have no visibility into whether the score requirements have been met if the improvement action is marked as resolved through third party.</span></span>

3. <span data-ttu-id="4a63a-151">選取 [**略**過], 因為您已決定接受風險, 而不會制定改進動作。</span><span class="sxs-lookup"><span data-stu-id="4a63a-151">Select **Ignore** because you have decided to accept the risk and not enact the improvement action.</span></span> <span data-ttu-id="4a63a-152">一旦您略過 [改善] 動作, 您可以達到的安全分數點總數將會降低。</span><span class="sxs-lookup"><span data-stu-id="4a63a-152">Once you ignore an improvement action, the total number of secure score points you can achieve will be reduced.</span></span> <span data-ttu-id="4a63a-153">您可以在 [歷程記錄] 中查看此動作或隨時復原。</span><span class="sxs-lookup"><span data-stu-id="4a63a-153">You can view this action in history or undo it at any time.</span></span>

4. <span data-ttu-id="4a63a-154">選取 [**審閱**], 因為 [改善] 動作需要您定期檢查環境的一部分, 以取得和保留點數。</span><span class="sxs-lookup"><span data-stu-id="4a63a-154">Select **Review** because the improvement action requires you to regularly review a part of your environment to gain and retain points.</span></span> <span data-ttu-id="4a63a-155">例如, 應每週檢查信箱轉寄規則, 以確保資料不會從您的網路進行挾帶。</span><span class="sxs-lookup"><span data-stu-id="4a63a-155">For example, mailbox forwarding rules should be reviewed on a weekly basis to make sure data is not being exfiltrated from your network.</span></span> <span data-ttu-id="4a63a-156">您不需要進行任何變更, 但是需要執行一項動作。</span><span class="sxs-lookup"><span data-stu-id="4a63a-156">You do not need to make any changes, but an action will need to be performed.</span></span> <span data-ttu-id="4a63a-157">如果您定期查看規則, 您會收到點數。</span><span class="sxs-lookup"><span data-stu-id="4a63a-157">If you regularly review the rules, you will receive the points.</span></span> <span data-ttu-id="4a63a-158">如果不是, 分數會降低。</span><span class="sxs-lookup"><span data-stu-id="4a63a-158">If not, the score will be reduced.</span></span>

![M365 首頁](./media/secure-score/secure-score1x450.png) ![M365 首頁](./media/secure-score/secure-score2x450.png)

<span data-ttu-id="4a63a-161">*圖 2 & 3: 改進動作 flyouts*</span><span class="sxs-lookup"><span data-stu-id="4a63a-161">*Figures 2 & 3: Improvement action flyouts*</span></span>

## <a name="monitor-improvements-over-time"></a><span data-ttu-id="4a63a-162">監視一段時間的改進</span><span class="sxs-lookup"><span data-stu-id="4a63a-162">Monitor improvements over time</span></span>

<span data-ttu-id="4a63a-163">您可以在 [歷程**記錄**] 索引標籤中, 在一段時間內, 查看組織分數的圖形。此視圖包含全域平均、行業平均和類似的座位元數目, 以及所選時間範圍內採取的所有動作。</span><span class="sxs-lookup"><span data-stu-id="4a63a-163">You can view a graph of your organization's score over time in the **History** tab. This view includes the global average, industry average, and similar seat count, along with all the actions taken in the selected time range.</span></span> <span data-ttu-id="4a63a-164">您也可以自訂日期範圍和依類別篩選。</span><span class="sxs-lookup"><span data-stu-id="4a63a-164">You can also customize a date range and filter by category.</span></span>

<span data-ttu-id="4a63a-165">分數每日計算一次 (大約 1:00 AM PST)。</span><span class="sxs-lookup"><span data-stu-id="4a63a-165">The score is calculated once per day (around 1:00 AM PST).</span></span> <span data-ttu-id="4a63a-166">如果您變更已測量的動作, 分數將會自動更新到下一天。</span><span class="sxs-lookup"><span data-stu-id="4a63a-166">If you make a change to a measured action, the score will automatically update the next day.</span></span> <span data-ttu-id="4a63a-167">另外請注意, 其他一些入口網站會顯示部分的 Microsoft 安全分數 (如 Microsoft Defender 安全中心)。</span><span class="sxs-lookup"><span data-stu-id="4a63a-167">It is also important to note that some other portals show parts of the Microsoft Secure Score (like Microsoft Defender Security Center).</span></span> <span data-ttu-id="4a63a-168">如果您完成改進動作, 而這些入口網站的得分增加, 最多可能需要24小時才會在 Microsoft 365 安全中心顯示更新的分數。</span><span class="sxs-lookup"><span data-stu-id="4a63a-168">If you complete an improvement action and the score is increased in those portals, it may take up to 24 hours for the updated score to display in Microsoft 365 security center.</span></span>  

## <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="4a63a-169">改進動作的計分方式</span><span class="sxs-lookup"><span data-stu-id="4a63a-169">How improvement actions are scored</span></span>

<span data-ttu-id="4a63a-170">大部分都是以二進位方式計分-當您執行 [改善] 動作時, 會取得 100% 的點數, 例如建立新的原則或開啟特定的設定。</span><span class="sxs-lookup"><span data-stu-id="4a63a-170">Most are scored in a binary fashion - you get 100% of the points if you implement the improvement action, like creating a new policy or turning on a specific setting.</span></span> <span data-ttu-id="4a63a-171">對於其他改進動作, 會以占總設定的百分比來指定點數。</span><span class="sxs-lookup"><span data-stu-id="4a63a-171">For other improvement actions, points are given as a percentage of the total configuration.</span></span> <span data-ttu-id="4a63a-172">例如, 如果您使用多重要素驗證來保護所有使用者, 且僅有5個100的使用者受到保護, 則會有30個分數。您會獲得2點的部分分數 (5 個受保護的/100 總計 \* 30 個最大值 = 2)。 分數部分分數)。</span><span class="sxs-lookup"><span data-stu-id="4a63a-172">For example, if the improvement action states you’ll get 30 points if you protect all your users with multi-factor authentication and you only have 5 of 100 total users protected, you would be given a partial score of around 2 points (5 protected / 100 total \* 30 max pts = 2 pts partial score).</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="4a63a-173">風險感知</span><span class="sxs-lookup"><span data-stu-id="4a63a-173">Risk awareness</span></span>

<span data-ttu-id="4a63a-174">Microsoft 安全分數是根據系統設定、使用者行為及其他安全性相關測量的安全性狀況的數位摘要;這不是您的系統或資料會遭到破壞的絕對測量。</span><span class="sxs-lookup"><span data-stu-id="4a63a-174">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior and other security related measurements; it is not an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="4a63a-175">相反地, 它代表您在 Microsoft 環境中採用安全性控制的程度, 可協助抵消違反風險。</span><span class="sxs-lookup"><span data-stu-id="4a63a-175">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment which can help offset the risk of being breached.</span></span> <span data-ttu-id="4a63a-176">任何線上服務都無法防止安全性違規, 而且安全分數不應該解釋為以任何方式防範安全性違規。</span><span class="sxs-lookup"><span data-stu-id="4a63a-176">No online service is completely immune from security breaches, and secure score should not be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="4a63a-177">我們想要聽到您的來信</span><span class="sxs-lookup"><span data-stu-id="4a63a-177">We want to hear from you</span></span>

<span data-ttu-id="4a63a-178">如果您有任何問題, 請在[安全性、隱私權 & 合規性](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)社區中張貼, 讓我們知道。</span><span class="sxs-lookup"><span data-stu-id="4a63a-178">If you have any issues, please let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="4a63a-179">我們正在監視社區, 並提供協助。</span><span class="sxs-lookup"><span data-stu-id="4a63a-179">We're monitoring the community and will provide help.</span></span>
