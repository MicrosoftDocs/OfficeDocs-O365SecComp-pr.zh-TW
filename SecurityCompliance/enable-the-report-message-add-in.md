---
title: 啟用報告訊息增益集
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/26/2019
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: 了解如何啟用報告訊息增益集以進行 Outlook 和 Outlook 個別使用者的 web 應用程式或整個組織。
ms.openlocfilehash: 3c476a6e097307b1aabc3580b598bb91a4407731
ms.sourcegitcommit: a79eb9907759d4cd849c3f948695a9ff890b19bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/26/2019
ms.locfileid: "30866339"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="81df6-103">啟用報告訊息增益集</span><span class="sxs-lookup"><span data-stu-id="81df6-103">Enable the Report Message add-in</span></span>

> [!NOTE]
> <span data-ttu-id="81df6-104">報告訊息增益集以進行 Outlook 和 outlook 網頁版並不完全相同的動作為[Outlook 垃圾郵件篩選器](https://support.office.com/article/Overview-of-the-Junk-Email-Filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)中，雖然兩者都可以用來將電子郵件標示為垃圾郵件、 非垃圾郵件或網路釣魚嘗試。</span><span class="sxs-lookup"><span data-stu-id="81df6-104">The Report Message add-in for Outlook and Outlook on the web is not exactly the same thing as the [Outlook Junk Email Filter](https://support.office.com/article/Overview-of-the-Junk-Email-Filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089), although both can be used to mark email as junk, not junk, or a phishing attempt.</span></span> <span data-ttu-id="81df6-105">差異在於，報告訊息增益集以進行 Outlook 和 outlook 網頁版通知 Microsoft 有關誤分類電子郵件，而 Outlook 垃圾郵件篩選器用來將組織中使用者信箱的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="81df6-105">The difference is, the Report Message add-in for Outlook and Outlook on the web notifies Microsoft about misclassified email, whereas the Outlook Junk Email Filter is used to organize email messages in a user's mailbox.</span></span> 

## <a name="overview"></a><span data-ttu-id="81df6-106">概觀</span><span class="sxs-lookup"><span data-stu-id="81df6-106">Overview</span></span>

<span data-ttu-id="81df6-107">報告訊息增益集以進行 Outlook 和網頁型 Outlook 讓人員能輕鬆地報告誤分類電子郵件是否安全或惡意，Microsoft 並分析其關係企業。</span><span class="sxs-lookup"><span data-stu-id="81df6-107">The Report Message add-in for Outlook and Outlook on the web enables people to easily report misclassified email, whether safe or malicious, to Microsoft and its affiliates for analysis.</span></span> <span data-ttu-id="81df6-108">Microsoft 使用這些提交來改善電子郵件保護技術的有效性。</span><span class="sxs-lookup"><span data-stu-id="81df6-108">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="81df6-109">此外，如果您的組織使用[Office 365 進階威脅防護方案 1](office-365-atp.md)或[計劃 2](office-365-ti.md)，報告訊息增益集提供有用的資訊可用於檢視並更新安全性原則與貴組織的安全性小組。</span><span class="sxs-lookup"><span data-stu-id="81df6-109">In addition, if your organization is using [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) or [Plan 2](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span> 

<span data-ttu-id="81df6-110">例如，假設人員會回報為網路釣魚郵件許多。</span><span class="sxs-lookup"><span data-stu-id="81df6-110">For example, suppose that people are reporting a lot of messages as phishing.</span></span> <span data-ttu-id="81df6-111">[安全性儀表板](security-dashboard.md)和其他報表中此資訊表面。</span><span class="sxs-lookup"><span data-stu-id="81df6-111">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="81df6-112">貴組織的安全性小組可以使用這項資訊作為反網路釣魚原則可能需要更新指示。</span><span class="sxs-lookup"><span data-stu-id="81df6-112">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> <span data-ttu-id="81df6-113">或者，如果人員所報告的郵件已標示為垃圾郵件為不是垃圾郵件報告訊息增益集使用很多，貴組織的安全性小組可能需要調整[反垃圾郵件原則](configure-the-anti-spam-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="81df6-113">Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-the-anti-spam-policies.md).</span></span> 

<span data-ttu-id="81df6-114">報告訊息增益集的運作方式與您的 Office 365 訂閱和下列產品：</span><span class="sxs-lookup"><span data-stu-id="81df6-114">The Report Message add-in works with your Office 365 subscription and the following products:</span></span>
 - <span data-ttu-id="81df6-115">Outlook 網頁版</span><span class="sxs-lookup"><span data-stu-id="81df6-115">Outlook on the web</span></span>
 - <span data-ttu-id="81df6-116">Outlook 2013 SP1</span><span class="sxs-lookup"><span data-stu-id="81df6-116">Outlook 2013 SP1</span></span>
 - <span data-ttu-id="81df6-117">Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="81df6-117">Outlook 2016</span></span>
 - <span data-ttu-id="81df6-118">Mac 版 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="81df6-118">Outlook 2016 for Mac</span></span>
 - <span data-ttu-id="81df6-119">隨附於 Office 365 專業增強版的 outlook</span><span class="sxs-lookup"><span data-stu-id="81df6-119">Outlook included with Office 365 ProPlus</span></span>

<span data-ttu-id="81df6-120">您現有的網頁瀏覽器應該足以讓報告訊息增益集運作;不過，如果您注意到增益集無法使用或無法如預期般運作，請嘗試在不同的瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="81df6-120">Your existing web browser should suffice for the Report Message add-in to work; however, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>
  
<span data-ttu-id="81df6-121">如果您是個別使用者，您可以[啟用報告訊息增益集以進行自己](#get-the-report-message-add-in-for-yourself)。</span><span class="sxs-lookup"><span data-stu-id="81df6-121">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span> 
  
<span data-ttu-id="81df6-122">如果您是 Office 365 全域管理員或 Exchange Online 的系統管理員，而且 Exchange 設定為使用 OAuth 驗證，您可以[啟用報告訊息增益集以進行組織](#get-and-enable-the-report-message-add-in-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="81df6-122">If you're an Office 365 global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="81df6-123">報告訊息增益集目前已提供透過[集中式部署](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="81df6-123">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span></span>
    
## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="81df6-124">取得報告訊息增益集自行</span><span class="sxs-lookup"><span data-stu-id="81df6-124">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="81df6-125">在[Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps)，搜尋[報告訊息增益集](https://appsource.microsoft.com/product/office/wa104381180)。</span><span class="sxs-lookup"><span data-stu-id="81df6-125">In [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps), search for the [Report Message add-in](https://appsource.microsoft.com/product/office/wa104381180).</span></span>
    
2. <span data-ttu-id="81df6-126">選擇 [**取得現在 IT**。</span><span class="sxs-lookup"><span data-stu-id="81df6-126">Choose **GET IT NOW**.</span></span><br/><span data-ttu-id="81df6-127">![報告訊息-立即取得](media/ReportMessageGETITNOW.png)</span><span class="sxs-lookup"><span data-stu-id="81df6-127">![Report Message - Get It Now](media/ReportMessageGETITNOW.png)</span></span><br/> 
    
3. <span data-ttu-id="81df6-128">檢閱使用和隱私權原則中的條款。</span><span class="sxs-lookup"><span data-stu-id="81df6-128">Review the terms of use and privacy policy.</span></span> <span data-ttu-id="81df6-129">然後選擇 [**繼續]**。</span><span class="sxs-lookup"><span data-stu-id="81df6-129">Then choose **Continue**.</span></span> 
    
4. <span data-ttu-id="81df6-130">登入 Office 365 中，使用您的工作或學校帳戶 （適用於商業用途） 或 Microsoft 帳戶 （供個人使用）。</span><span class="sxs-lookup"><span data-stu-id="81df6-130">Sign in to Office 365 using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>
    
<span data-ttu-id="81df6-131">增益集已安裝並啟用之後，您會看到下列圖示：</span><span class="sxs-lookup"><span data-stu-id="81df6-131">After the add-in is installed and enabled, you'll see the following icons:</span></span> 

- <span data-ttu-id="81df6-132">在 Outlook 中，圖示看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="81df6-132">In Outlook, the icon looks like this:</span></span> <br/> ![報告訊息增益集的 Outlook 圖示](media/OutlookReportMessageIcon.png)<br/>
- <span data-ttu-id="81df6-134">在 Outlook 中網頁 （原先稱為 Outlook Web App） 上，圖示看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="81df6-134">In Outlook on the web (formerly known as Outlook Web App), the icon looks like this:</span></span><br/>![Outlook 網頁報告訊息增益集] 圖示](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

> [!TIP]
> <span data-ttu-id="81df6-136">下一個步驟中，以了解如何[使用報告訊息增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。</span><span class="sxs-lookup"><span data-stu-id="81df6-136">As a next step, learn how to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>
  
## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="81df6-137">取得並啟用報告訊息增益集為您的組織</span><span class="sxs-lookup"><span data-stu-id="81df6-137">Get and enable the Report Message add-in for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="81df6-138">您必須是 Office 365 全域系統管理員或 Exchange Online 系統管理員，才能完成此工作。</span><span class="sxs-lookup"><span data-stu-id="81df6-138">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task.</span></span> <span data-ttu-id="81df6-139">此外，Exchange 必須設定為使用 OAuth 驗證來了解更多，請參閱[Exchange 需求 （的增益集的集中式部署）](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="81df6-139">In addition, Exchange must be configured to use OAuth authentication To learn more, see [Exchange requirements (Centralized Deployment of add-ins)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span></span> 

1. <span data-ttu-id="81df6-140">移至 Microsoft 365 系統管理中心中的[服務 & 增益集] 頁面](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)。</span><span class="sxs-lookup"><span data-stu-id="81df6-140">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the Microsoft 365 admin center.</span></span><br/><span data-ttu-id="81df6-141">![服務與增益集] 頁面中新的 Microsoft 365 系統管理中心](media/ServicesAddInsPageNewM365AdminCenter.png)</span><span class="sxs-lookup"><span data-stu-id="81df6-141">![Services and Add-Ins page in the new Microsoft 365 Admin Center](media/ServicesAddInsPageNewM365AdminCenter.png)</span></span><br/> 
    
2. <span data-ttu-id="81df6-142">選擇 [ **+ 部署增益集**]。</span><span class="sxs-lookup"><span data-stu-id="81df6-142">Choose **+ Deploy Add-in**.</span></span><br/><span data-ttu-id="81df6-143">![選擇 [部署增益集](media/ServicesAddIns-ChooseDeployAddIn.png)</span><span class="sxs-lookup"><span data-stu-id="81df6-143">![Choose Deploy Add-In](media/ServicesAddIns-ChooseDeployAddIn.png)</span></span><br/> 
    
3. <span data-ttu-id="81df6-144">在 [**新增益集**] 畫面中，請先檢閱資訊，，然後選擇 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="81df6-144">In the **New Add-In** screen, review the information, and then choose **Next**.</span></span><br/><span data-ttu-id="81df6-145">![新的增益集詳細資料](media/NewAddInScreen1.png)</span><span class="sxs-lookup"><span data-stu-id="81df6-145">![New Add-In details](media/NewAddInScreen1.png)</span></span><br/>
    
4. <span data-ttu-id="81df6-146">選取 [**我想要將增益集從 Office 市集**，，然後選擇 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="81df6-146">Select **I want to add an Add-In from the Office Store**, and then choose **Next**.</span></span><br/><span data-ttu-id="81df6-147">![我想要將新增益集](media/NewAddInScreen2.png)</span><span class="sxs-lookup"><span data-stu-id="81df6-147">![I want to add an new Add-In](media/NewAddInScreen2.png)</span></span><br/> 
    
5. <span data-ttu-id="81df6-148">搜尋**報告郵件**，並在旁的**報告訊息增益集**的結果清單中，選擇 [**新增]**。</span><span class="sxs-lookup"><span data-stu-id="81df6-148">Search for **Report Message**, and in the list of results, next to the **Report Message Add-In**, choose **Add**.</span></span><br/><span data-ttu-id="81df6-149">![搜尋報告的郵件，然後選擇 [新增]](media/NewAddInScreen3.png)</span><span class="sxs-lookup"><span data-stu-id="81df6-149">![Search for Report Message and then choose Add](media/NewAddInScreen3.png)</span></span><br/>
    
6. <span data-ttu-id="81df6-150">在**報告郵件**畫面上，檢閱的詳細資訊，，然後選擇 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="81df6-150">On the **Report Message** screen, review the information, and then choose **Next**.</span></span><br/><span data-ttu-id="81df6-151">![報告訊息詳細資料](media/ReportMessageAdd-InNewScreen4.png)</span><span class="sxs-lookup"><span data-stu-id="81df6-151">![Report Message details](media/ReportMessageAdd-InNewScreen4.png)</span></span><br/>

7. <span data-ttu-id="81df6-152">指定 Outlook 使用者預設設定，然後選擇 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="81df6-152">Specify the user default settings for Outlook, and  then choose **Next**.</span></span><br/><span data-ttu-id="81df6-153">![報告適用於 Outlook 的郵件預設設定](media/ReportMessageOptionsScreen5.png)</span><span class="sxs-lookup"><span data-stu-id="81df6-153">![Report Message default settings for Outlook](media/ReportMessageOptionsScreen5.png)</span></span><br/>

8. <span data-ttu-id="81df6-154">指定誰的報告訊息增益集] 中，然後選擇 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="81df6-154">Specify who gets the Report Message Add-in, and then choose **Save**.</span></span> <br/><span data-ttu-id="81df6-155">![誰可以取得報告訊息增益集](media/ReportMessageOptionsScreen6.png)</span><span class="sxs-lookup"><span data-stu-id="81df6-155">![Who gets the Report Message add-in](media/ReportMessageOptionsScreen6.png)</span></span><br/>

> [!TIP]
> <span data-ttu-id="81df6-156">我們建議您[設定 「 可取得一份報告，讓使用者的電子郵件訊息的規則](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users)。</span><span class="sxs-lookup"><span data-stu-id="81df6-156">We recommend [setting up a rule to get a copy of email messages reported by your users](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users).</span></span>

<span data-ttu-id="81df6-157">根據您選取的項目當您設定 「 增益集 (步驟 7-8 上方)，您組織中的人員會有[報告訊息增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)可用。</span><span class="sxs-lookup"><span data-stu-id="81df6-157">Depending on what you selected when you set up the add-in (steps 7-8 above), people in your organization will have the [Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) available.</span></span> <span data-ttu-id="81df6-158">在您的組織中的人會看到下列圖示：</span><span class="sxs-lookup"><span data-stu-id="81df6-158">People in your organization will see the following icons:</span></span> 

- <span data-ttu-id="81df6-159">在 Outlook 中，圖示看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="81df6-159">In Outlook, the icon looks like this:</span></span> <br/> ![報告訊息增益集的 Outlook 圖示](media/OutlookReportMessageIcon.png)<br/>
- <span data-ttu-id="81df6-161">在 web 上 Outlook 中，圖示看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="81df6-161">In Outlook on the web, the icon looks like this:</span></span><br/>![Outlook Web 報告訊息增益集] 圖示](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

> [!TIP]
> <span data-ttu-id="81df6-163">當您通知使用者有關的報告訊息增益集時，包括[使用報告訊息增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)的連結。</span><span class="sxs-lookup"><span data-stu-id="81df6-163">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users"></a><span data-ttu-id="81df6-164">設定規則，以取得一份報告，讓使用者的電子郵件</span><span class="sxs-lookup"><span data-stu-id="81df6-164">Set up a rule to get a copy of email messages reported by your users</span></span>

> [!IMPORTANT]
> <span data-ttu-id="81df6-165">您必須是 Exchange Online 系統管理員可執行此工作。</span><span class="sxs-lookup"><span data-stu-id="81df6-165">You must be an Exchange Online Administrator to perform this task.</span></span>
  
<span data-ttu-id="81df6-166">您可以設定規則，以取得一份報告的組織中使用者的電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="81df6-166">You can set up a rule to get a copy of email messages reported by users in your organization.</span></span> <span data-ttu-id="81df6-167">下載及組織啟用報告訊息增益集之後，您可以這麼做。</span><span class="sxs-lookup"><span data-stu-id="81df6-167">You do this after you have downloaded and enabled the Report Message add-in for your organization.</span></span>
  
1. <span data-ttu-id="81df6-168">在 Exchange 系統管理中心中，選擇 [**郵件流程** \> **規則**。</span><span class="sxs-lookup"><span data-stu-id="81df6-168">In the Exchange admin center, choose **mail flow** \> **rules**.</span></span> 
    
2. <span data-ttu-id="81df6-169">選擇 [ **+** \> **建立新的規則**。</span><span class="sxs-lookup"><span data-stu-id="81df6-169">Choose **+** \> **Create a new rule**.</span></span> 
    
3. <span data-ttu-id="81df6-170">在 [**名稱**] 方塊中，輸入名稱，例如提交。</span><span class="sxs-lookup"><span data-stu-id="81df6-170">In the **Name** box, type a name, such as Submissions.</span></span>
    
4. <span data-ttu-id="81df6-171">在 [**套用此規則情況**] 清單中，選擇 [**收件者的地址包含...**]。</span><span class="sxs-lookup"><span data-stu-id="81df6-171">In the **Apply this rule if** list, choose **The recipient address includes...**.</span></span> 
    
5. <span data-ttu-id="81df6-172">在 [**指定單字或片語**] 畫面中，新增`junk@office365.microsoft.com`和`phish@office365.microsoft.com`，然後選擇 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="81df6-172">In the **specify words or phrases** screen, add `junk@office365.microsoft.com` and `phish@office365.microsoft.com`, and then choose **OK**.</span></span><br/><span data-ttu-id="81df6-173">![指定規則的垃圾郵件及釣魚程式電子郵件地址](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)</span><span class="sxs-lookup"><span data-stu-id="81df6-173">![Specify the junk and phish email addresses for the rule](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)</span></span><br/>
  
6. <span data-ttu-id="81df6-174">在**執行下列動作...** ] 清單中，選擇 [ **[密件副本郵件到...**。</span><span class="sxs-lookup"><span data-stu-id="81df6-174">In the **Do the following...** list, choose **Bcc the message to...**.</span></span> 
    
7. <span data-ttu-id="81df6-175">新增全域系統管理員、 安全性系統管理員和/或安全性讀取者應該接收人員回報給 Microsoft，每個電子郵件訊息的複本，然後選擇 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="81df6-175">Add a global administrator, security administrator, and/or security reader who should receive a copy of each email message that people report to Microsoft, and then choose **OK**.</span></span><br/><span data-ttu-id="81df6-176">![新增的全域或安全性管理員，才能接收的每個報告的郵件複本](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)</span><span class="sxs-lookup"><span data-stu-id="81df6-176">![Add a global or security administrator to receive a copy of each reported message](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)</span></span><br/>
  
8. <span data-ttu-id="81df6-177">選取 [**此規則使用嚴重性層級的稽核**，然後選擇 [**中等**。</span><span class="sxs-lookup"><span data-stu-id="81df6-177">Select **Audit this rule with severity level**, and choose **Medium**.</span></span> 
    
9. <span data-ttu-id="81df6-178">在 [**選擇此規則的模式**，選擇 [**強制執行**]。</span><span class="sxs-lookup"><span data-stu-id="81df6-178">Under **Choose a mode for this rule**, choose **Enforce**.</span></span><br/><span data-ttu-id="81df6-179">![設定規則，以取得每個報告的郵件的副本](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)</span><span class="sxs-lookup"><span data-stu-id="81df6-179">![Set up a rule to get a copy of each reported message](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)</span></span><br/>
  
10. <span data-ttu-id="81df6-180">選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="81df6-180">Choose **Save**.</span></span> 
    
<span data-ttu-id="81df6-181">使用就地此規則，每當您的組織中的人員報告電子郵件訊息的報告訊息增益集，使用您全域系統管理員、 安全性系統管理員和/或安全性讀取者會收到該郵件的副本。</span><span class="sxs-lookup"><span data-stu-id="81df6-181">With this rule in place, whenever someone in your organization reports an email message using the Report Message add-in, your global administrator, security administrator, and/or security reader will receive a copy of that message.</span></span> <span data-ttu-id="81df6-182">這項資訊可以讓您設定或調整原則，例如[Office 365 ATP 安全連結](atp-safe-links.md)原則或您的[反垃圾郵件](anti-spam-protection.md)設定。</span><span class="sxs-lookup"><span data-stu-id="81df6-182">This information can enable you to set up or adjust policies, such as [Office 365 ATP Safe Links](atp-safe-links.md) policies, or your [anti-spam](anti-spam-protection.md) settings.</span></span> 

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="81df6-183">了解如何使用報告訊息增益集</span><span class="sxs-lookup"><span data-stu-id="81df6-183">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="81df6-184">請參閱 <<c0>使用報告訊息增益集。</span><span class="sxs-lookup"><span data-stu-id="81df6-184">See [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="81df6-185">檢視或編輯報告訊息增益集的設定</span><span class="sxs-lookup"><span data-stu-id="81df6-185">Review or edit settings for the Report Message add-in</span></span>

<span data-ttu-id="81df6-186">您可以檢閱並編輯報告訊息增益集[服務 & 增益集] 頁面](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)上的預設設定。</span><span class="sxs-lookup"><span data-stu-id="81df6-186">You can review and edit the default settings for the Report Message add-in on the [Services & Add-Ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="81df6-187">您必須是 Office 365 全域系統管理員或 Exchange Online 系統管理員，才能完成此工作。</span><span class="sxs-lookup"><span data-stu-id="81df6-187">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task.</span></span>
    
1. <span data-ttu-id="81df6-188">移至 Microsoft 365 系統管理中心中的[服務 & 增益集] 頁面](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)。</span><span class="sxs-lookup"><span data-stu-id="81df6-188">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the Microsoft 365 admin center.</span></span><br/><span data-ttu-id="81df6-189">![服務與增益集] 頁面中新的 Microsoft 365 系統管理中心](media/ServicesAddInsPageNewM365AdminCenter.png)</span><span class="sxs-lookup"><span data-stu-id="81df6-189">![Services and Add-Ins page in the new Microsoft 365 Admin Center](media/ServicesAddInsPageNewM365AdminCenter.png)</span></span><br/>

2. <span data-ttu-id="81df6-190">尋找和選取的報告訊息增益集。</span><span class="sxs-lookup"><span data-stu-id="81df6-190">Find and select the Report Message add-in.</span></span><br/>![尋找和選取的報告訊息增益集](media/FindReportMessageAddIn.png)<br/> 
    
3. <span data-ttu-id="81df6-192">報告郵件在畫面上，檢閱並編輯最適合貴組織的設定。</span><span class="sxs-lookup"><span data-stu-id="81df6-192">On the Report Message screen, review and edit settings as appropriate for your organization.</span></span><br/>![設定的報告訊息增益集](media/EditReportMessageAddIn.png)<br/> 

## <a name="related-topics"></a><span data-ttu-id="81df6-194">相關主題</span><span class="sxs-lookup"><span data-stu-id="81df6-194">Related topics</span></span>

[<span data-ttu-id="81df6-195">使用報告訊息增益集</span><span class="sxs-lookup"><span data-stu-id="81df6-195">Use the Report Message add-in</span></span>](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
  
[<span data-ttu-id="81df6-196">檢視安全性中的電子郵件安全性報告&amp;合規性中心</span><span class="sxs-lookup"><span data-stu-id="81df6-196">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="81df6-197">檢視 Office 365 進階威脅防護報告</span><span class="sxs-lookup"><span data-stu-id="81df6-197">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

[<span data-ttu-id="81df6-198">使用檔案總管中的安全性&amp;合規性中心</span><span class="sxs-lookup"><span data-stu-id="81df6-198">Use Explorer in the Security &amp; Compliance Center</span></span>](use-explorer-in-security-and-compliance.md)
  

