---
title: 啟用報告訊息增益集
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/26/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: 瞭解如何針對個別使用者或整個組織啟用 Outlook 和 Outlook 網頁版的報告訊息增益集。
ms.openlocfilehash: d74772502f5ffd7e274574075604c2fc0c235f30
ms.sourcegitcommit: 0d5a863f48914eeaaf29f7d2a2022618de186247
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2019
ms.locfileid: "34077949"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="cb305-103">啟用報告訊息增益集</span><span class="sxs-lookup"><span data-stu-id="cb305-103">Enable the Report Message add-in</span></span>

> [!NOTE]
> <span data-ttu-id="cb305-104">Outlook 和 outlook 網頁版的報告郵件增益集與[Outlook 垃圾郵件篩選器](https://support.office.com/article/Overview-of-the-Junk-Email-Filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)並不完全相同, 不過這兩者都可以用來將電子郵件標示為垃圾郵件, 而非垃圾郵件或網路釣魚企圖。</span><span class="sxs-lookup"><span data-stu-id="cb305-104">The Report Message add-in for Outlook and Outlook on the web is not exactly the same thing as the [Outlook Junk Email Filter](https://support.office.com/article/Overview-of-the-Junk-Email-Filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089), although both can be used to mark email as junk, not junk, or a phishing attempt.</span></span> <span data-ttu-id="cb305-105">不同之處在于 Outlook 和 outlook 網頁版的報告訊息增益集會通知 Microsoft 有關 misclassified 電子郵件, 而 Outlook 垃圾郵件篩選器則是用來組織使用者信箱中的電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="cb305-105">The difference is, the Report Message add-in for Outlook and Outlook on the web notifies Microsoft about misclassified email, whereas the Outlook Junk Email Filter is used to organize email messages in a user's mailbox.</span></span> 

## <a name="overview"></a><span data-ttu-id="cb305-106">概觀</span><span class="sxs-lookup"><span data-stu-id="cb305-106">Overview</span></span>

<span data-ttu-id="cb305-107">Outlook 和 Outlook 網頁版的報告訊息增益集可讓使用者輕鬆地向 Microsoft 及其子公司報告 misclassified 電子郵件, 以進行分析。</span><span class="sxs-lookup"><span data-stu-id="cb305-107">The Report Message add-in for Outlook and Outlook on the web enables people to easily report misclassified email, whether safe or malicious, to Microsoft and its affiliates for analysis.</span></span> <span data-ttu-id="cb305-108">Microsoft 會使用這些提交來改善電子郵件保護技術的效能。</span><span class="sxs-lookup"><span data-stu-id="cb305-108">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="cb305-109">此外, 如果您的組織使用的是[Office 365 高級威脅防護計畫 1](office-365-atp.md)或[計畫 2](office-365-ti.md), 則報告郵件增益集會為貴組織的安全小組提供有用的資訊, 供您用來檢查及更新安全性原則。</span><span class="sxs-lookup"><span data-stu-id="cb305-109">In addition, if your organization is using [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) or [Plan 2](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span> 

<span data-ttu-id="cb305-110">例如, 假設使用者將大量的郵件報告為網路釣魚。</span><span class="sxs-lookup"><span data-stu-id="cb305-110">For example, suppose that people are reporting a lot of messages as phishing.</span></span> <span data-ttu-id="cb305-111">[[安全性] 儀表板](security-dashboard.md)和其他報表中的此資訊。</span><span class="sxs-lookup"><span data-stu-id="cb305-111">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="cb305-112">您組織的安全小組可以使用此資訊, 表示可能需要更新反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="cb305-112">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> <span data-ttu-id="cb305-113">或者, 如果人員使用報告郵件增益集來報告大量以垃圾郵件表示為非垃圾郵件的郵件, 您組織的安全小組可能需要調整[反垃圾郵件原則](configure-the-anti-spam-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="cb305-113">Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-the-anti-spam-policies.md).</span></span> 

<span data-ttu-id="cb305-114">報告郵件增益集可與您的 Office 365 訂閱及下列產品搭配使用:</span><span class="sxs-lookup"><span data-stu-id="cb305-114">The Report Message add-in works with your Office 365 subscription and the following products:</span></span>
 - <span data-ttu-id="cb305-115">Outlook 網頁版</span><span class="sxs-lookup"><span data-stu-id="cb305-115">Outlook on the web</span></span>
 - <span data-ttu-id="cb305-116">Outlook 2013 SP1</span><span class="sxs-lookup"><span data-stu-id="cb305-116">Outlook 2013 SP1</span></span>
 - <span data-ttu-id="cb305-117">Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cb305-117">Outlook 2016</span></span>
 - <span data-ttu-id="cb305-118">Mac 版 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cb305-118">Outlook 2016 for Mac</span></span>
 - <span data-ttu-id="cb305-119">Office 365 專業增強版隨附的 Outlook</span><span class="sxs-lookup"><span data-stu-id="cb305-119">Outlook included with Office 365 ProPlus</span></span>

<span data-ttu-id="cb305-120">您現有的網頁瀏覽器應該足以讓報告訊息增益集正常運作;不過, 如果您注意到增益集無法使用或無法如預期般運作, 請嘗試使用不同的瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="cb305-120">Your existing web browser should suffice for the Report Message add-in to work; however, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>
  
<span data-ttu-id="cb305-121">如果您是個人使用者, 您可以[為自己啟用報告訊息增益集](#get-the-report-message-add-in-for-yourself)。</span><span class="sxs-lookup"><span data-stu-id="cb305-121">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span> 
  
<span data-ttu-id="cb305-122">如果您是 Office 365 全域系統管理員或 Exchange Online 系統管理員, 而且已將 Exchange 設定為使用 OAuth 驗證, 您可以[為您的組織啟用報告訊息增益集](#get-and-enable-the-report-message-add-in-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="cb305-122">If you're an Office 365 global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="cb305-123">您現在可以透過[集中式部署](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)來使用報告訊息增益集。</span><span class="sxs-lookup"><span data-stu-id="cb305-123">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span></span>
    
## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="cb305-124">取得自己的報告訊息增益集</span><span class="sxs-lookup"><span data-stu-id="cb305-124">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="cb305-125">在[Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps)中, 搜尋[報告訊息增益集](https://appsource.microsoft.com/product/office/wa104381180)。</span><span class="sxs-lookup"><span data-stu-id="cb305-125">In [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps), search for the [Report Message add-in](https://appsource.microsoft.com/product/office/wa104381180).</span></span>
    
2. <span data-ttu-id="cb305-126">選擇 [**立即取得**]。</span><span class="sxs-lookup"><span data-stu-id="cb305-126">Choose **GET IT NOW**.</span></span><br/><span data-ttu-id="cb305-127">![報告訊息-立即取得](media/ReportMessageGETITNOW.png)</span><span class="sxs-lookup"><span data-stu-id="cb305-127">![Report Message - Get It Now](media/ReportMessageGETITNOW.png)</span></span><br/> 
    
3. <span data-ttu-id="cb305-128">回顧使用條款和隱私權原則。</span><span class="sxs-lookup"><span data-stu-id="cb305-128">Review the terms of use and privacy policy.</span></span> <span data-ttu-id="cb305-129">然後選擇 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="cb305-129">Then choose **Continue**.</span></span> 
    
4. <span data-ttu-id="cb305-130">使用您的工作或學校帳戶 (供商務用) 或您的 Microsoft 帳戶 (供個人使用) 登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="cb305-130">Sign in to Office 365 using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>
    
<span data-ttu-id="cb305-131">安裝並啟用增益集之後, 您會看到下列圖示:</span><span class="sxs-lookup"><span data-stu-id="cb305-131">After the add-in is installed and enabled, you'll see the following icons:</span></span> 

- <span data-ttu-id="cb305-132">在 Outlook 中, 圖示如下所示:</span><span class="sxs-lookup"><span data-stu-id="cb305-132">In Outlook, the icon looks like this:</span></span> <br/> ![報告 Outlook 的郵件增益集圖示](media/OutlookReportMessageIcon.png)<br/>
- <span data-ttu-id="cb305-134">在網頁版 Outlook (先前稱為 Outlook Web App) 中, 圖示看起來像這樣:</span><span class="sxs-lookup"><span data-stu-id="cb305-134">In Outlook on the web (formerly known as Outlook Web App), the icon looks like this:</span></span><br/>![網頁上的 Outlook 報告訊息增益集圖示](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

> [!TIP]
> <span data-ttu-id="cb305-136">下一步, 瞭解如何[使用報告訊息增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。</span><span class="sxs-lookup"><span data-stu-id="cb305-136">As a next step, learn how to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>
  
## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="cb305-137">取得並啟用組織的報告訊息增益集</span><span class="sxs-lookup"><span data-stu-id="cb305-137">Get and enable the Report Message add-in for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cb305-138">您必須是 Office 365 全域管理員或 Exchange Online 系統管理員, 才可完成此工作。</span><span class="sxs-lookup"><span data-stu-id="cb305-138">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task.</span></span> <span data-ttu-id="cb305-139">此外, 必須將 Exchange 設定為使用 OAuth 驗證來深入瞭解, 請參閱[exchange 需求 (增益集的集中式部署)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="cb305-139">In addition, Exchange must be configured to use OAuth authentication To learn more, see [Exchange requirements (Centralized Deployment of add-ins)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span></span> 

1. <span data-ttu-id="cb305-140">移至 Microsoft 365 系統管理中心的 [服務] [ [& 增益集] 頁面](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)。</span><span class="sxs-lookup"><span data-stu-id="cb305-140">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the Microsoft 365 admin center.</span></span><br/><span data-ttu-id="cb305-141">![新 Microsoft 365 系統管理中心的 [服務和增益集] 頁面](media/ServicesAddInsPageNewM365AdminCenter.png)</span><span class="sxs-lookup"><span data-stu-id="cb305-141">![Services and Add-Ins page in the new Microsoft 365 Admin Center](media/ServicesAddInsPageNewM365AdminCenter.png)</span></span><br/> 
    
2. <span data-ttu-id="cb305-142">選擇 [ **+ 部署增益集**]。</span><span class="sxs-lookup"><span data-stu-id="cb305-142">Choose **+ Deploy Add-in**.</span></span><br/><span data-ttu-id="cb305-143">![選擇 [部署增益集]](media/ServicesAddIns-ChooseDeployAddIn.png)</span><span class="sxs-lookup"><span data-stu-id="cb305-143">![Choose Deploy Add-In](media/ServicesAddIns-ChooseDeployAddIn.png)</span></span><br/> 
    
3. <span data-ttu-id="cb305-144">在 [**新增增益集**] 畫面中, 查看資訊, 然後選擇 [**下一步]**。</span><span class="sxs-lookup"><span data-stu-id="cb305-144">In the **New Add-In** screen, review the information, and then choose **Next**.</span></span><br/><span data-ttu-id="cb305-145">![新的增益集詳細資料](media/NewAddInScreen1.png)</span><span class="sxs-lookup"><span data-stu-id="cb305-145">![New Add-In details](media/NewAddInScreen1.png)</span></span><br/>
    
4. <span data-ttu-id="cb305-146">選取 **[我想要從 Office 存放區新增增益集**], 然後選擇 [**下一步]**。</span><span class="sxs-lookup"><span data-stu-id="cb305-146">Select **I want to add an Add-In from the Office Store**, and then choose **Next**.</span></span><br/><span data-ttu-id="cb305-147">![我想要新增增益集](media/NewAddInScreen2.png)</span><span class="sxs-lookup"><span data-stu-id="cb305-147">![I want to add an new Add-In](media/NewAddInScreen2.png)</span></span><br/> 
    
5. <span data-ttu-id="cb305-148">搜尋**報告訊息**, 並在結果清單中的**報告訊息增益集**旁, 選擇 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="cb305-148">Search for **Report Message**, and in the list of results, next to the **Report Message Add-In**, choose **Add**.</span></span><br/><span data-ttu-id="cb305-149">![搜尋報告訊息, 然後選擇 [新增]](media/NewAddInScreen3.png)</span><span class="sxs-lookup"><span data-stu-id="cb305-149">![Search for Report Message and then choose Add](media/NewAddInScreen3.png)</span></span><br/>
    
6. <span data-ttu-id="cb305-150">在 [**報告訊息**] 畫面上, 查看資訊, 然後選擇 [**下一步]**。</span><span class="sxs-lookup"><span data-stu-id="cb305-150">On the **Report Message** screen, review the information, and then choose **Next**.</span></span><br/><span data-ttu-id="cb305-151">![報告訊息詳細資料](media/ReportMessageAdd-InNewScreen4.png)</span><span class="sxs-lookup"><span data-stu-id="cb305-151">![Report Message details](media/ReportMessageAdd-InNewScreen4.png)</span></span><br/>

7. <span data-ttu-id="cb305-152">指定 Outlook 的使用者預設設定, 然後選擇 [**下一步]**。</span><span class="sxs-lookup"><span data-stu-id="cb305-152">Specify the user default settings for Outlook, and  then choose **Next**.</span></span><br/><span data-ttu-id="cb305-153">![報告郵件的預設設定 Outlook](media/ReportMessageOptionsScreen5.png)</span><span class="sxs-lookup"><span data-stu-id="cb305-153">![Report Message default settings for Outlook](media/ReportMessageOptionsScreen5.png)</span></span><br/>

8. <span data-ttu-id="cb305-154">指定誰可以取得報表郵件增益集, 然後選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="cb305-154">Specify who gets the Report Message Add-in, and then choose **Save**.</span></span> <br/><span data-ttu-id="cb305-155">![誰可以取得報表訊息增益集](media/ReportMessageOptionsScreen6.png)</span><span class="sxs-lookup"><span data-stu-id="cb305-155">![Who gets the Report Message add-in](media/ReportMessageOptionsScreen6.png)</span></span><br/>

> [!TIP]
> <span data-ttu-id="cb305-156">建議[您設定規則, 以取得使用者所報告之電子](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users)郵件的副本。</span><span class="sxs-lookup"><span data-stu-id="cb305-156">We recommend [setting up a rule to get a copy of email messages reported by your users](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users).</span></span>

<span data-ttu-id="cb305-157">根據您在設定增益集時所選取的專案 (上述步驟 7-8), 您組織中的人員將會有可用的[報告訊息增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。</span><span class="sxs-lookup"><span data-stu-id="cb305-157">Depending on what you selected when you set up the add-in (steps 7-8 above), people in your organization will have the [Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) available.</span></span> <span data-ttu-id="cb305-158">您組織中的人員會看到下列圖示:</span><span class="sxs-lookup"><span data-stu-id="cb305-158">People in your organization will see the following icons:</span></span> 

- <span data-ttu-id="cb305-159">在 Outlook 中, 圖示如下所示:</span><span class="sxs-lookup"><span data-stu-id="cb305-159">In Outlook, the icon looks like this:</span></span> <br/> ![報告 Outlook 的郵件增益集圖示](media/OutlookReportMessageIcon.png)<br/>
- <span data-ttu-id="cb305-161">在網頁版 Outlook 中, 圖示看起來像這樣:</span><span class="sxs-lookup"><span data-stu-id="cb305-161">In Outlook on the web, the icon looks like this:</span></span><br/>![網頁上的 Outlook 報告訊息增益集圖示](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

> [!TIP]
> <span data-ttu-id="cb305-163">當您通知使用者有關報告訊息增益集時, 請包含[使用報告訊息增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)的連結。</span><span class="sxs-lookup"><span data-stu-id="cb305-163">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users"></a><span data-ttu-id="cb305-164">設定規則以取得使用者所報告的電子郵件的副本</span><span class="sxs-lookup"><span data-stu-id="cb305-164">Set up a rule to get a copy of email messages reported by your users</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cb305-165">您必須是 Exchange Online 系統管理員, 才可執行此工作。</span><span class="sxs-lookup"><span data-stu-id="cb305-165">You must be an Exchange Online Administrator to perform this task.</span></span>
  
<span data-ttu-id="cb305-166">您可以設定規則, 以取得組織中使用者所報告之電子郵件的副本。</span><span class="sxs-lookup"><span data-stu-id="cb305-166">You can set up a rule to get a copy of email messages reported by users in your organization.</span></span> <span data-ttu-id="cb305-167">您可以在下載並啟用組織的報告訊息增益集之後執行此動作。</span><span class="sxs-lookup"><span data-stu-id="cb305-167">You do this after you have downloaded and enabled the Report Message add-in for your organization.</span></span>
  
1. <span data-ttu-id="cb305-168">在 Exchange 系統管理中心中, 選擇 [**郵件流程** \> **規則**]。</span><span class="sxs-lookup"><span data-stu-id="cb305-168">In the Exchange admin center, choose **mail flow** \> **rules**.</span></span> 
    
2. <span data-ttu-id="cb305-169">選擇**+** \> [**建立新規則**]。</span><span class="sxs-lookup"><span data-stu-id="cb305-169">Choose **+** \> **Create a new rule**.</span></span> 
    
3. <span data-ttu-id="cb305-170">在 [**名稱**] 方塊中, 輸入名稱, 例如 [送出]。</span><span class="sxs-lookup"><span data-stu-id="cb305-170">In the **Name** box, type a name, such as Submissions.</span></span>
    
4. <span data-ttu-id="cb305-171">在 [**將此規則**套用至] 清單中, 選擇 [**收件者位址包含 ...**]。</span><span class="sxs-lookup"><span data-stu-id="cb305-171">In the **Apply this rule if** list, choose **The recipient address includes...**.</span></span> 
    
5. <span data-ttu-id="cb305-172">在 [**指定字詞或片語**] 畫面中`junk@office365.microsoft.com` , `phish@office365.microsoft.com`新增和, 然後選擇 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="cb305-172">In the **specify words or phrases** screen, add `junk@office365.microsoft.com` and `phish@office365.microsoft.com`, and then choose **OK**.</span></span><br/><span data-ttu-id="cb305-173">![指定規則的垃圾郵件和網路釣魚電子郵件地址](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)</span><span class="sxs-lookup"><span data-stu-id="cb305-173">![Specify the junk and phish email addresses for the rule](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)</span></span><br/>
  
6. <span data-ttu-id="cb305-174">在 [**執行下列**動作 ...] 清單中, 選擇 [**密件副本郵件為 ...**]。</span><span class="sxs-lookup"><span data-stu-id="cb305-174">In the **Do the following...** list, choose **Bcc the message to...**.</span></span> 
    
7. <span data-ttu-id="cb305-175">新增全域管理員、安全性系統管理員和/或安全性讀者, 其應該會收到每個人員向 Microsoft 報告的電子郵件的副本, 然後選擇 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="cb305-175">Add a global administrator, security administrator, and/or security reader who should receive a copy of each email message that people report to Microsoft, and then choose **OK**.</span></span><br/><span data-ttu-id="cb305-176">![新增全域或安全性系統管理員以接收每個報告的郵件的副本](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)</span><span class="sxs-lookup"><span data-stu-id="cb305-176">![Add a global or security administrator to receive a copy of each reported message](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)</span></span><br/>
  
8. <span data-ttu-id="cb305-177">選取 [**使用嚴重性層級來審核這個規則**], 然後選擇 [**中**]。</span><span class="sxs-lookup"><span data-stu-id="cb305-177">Select **Audit this rule with severity level**, and choose **Medium**.</span></span> 
    
9. <span data-ttu-id="cb305-178">在 **[選擇此規則的模式]** 下, 選擇 [**強制**]。</span><span class="sxs-lookup"><span data-stu-id="cb305-178">Under **Choose a mode for this rule**, choose **Enforce**.</span></span><br/><span data-ttu-id="cb305-179">![設定規則以取得每個報告的郵件的副本](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)</span><span class="sxs-lookup"><span data-stu-id="cb305-179">![Set up a rule to get a copy of each reported message](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)</span></span><br/>
  
10. <span data-ttu-id="cb305-180">選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="cb305-180">Choose **Save**.</span></span> 
    
<span data-ttu-id="cb305-181">使用此規則時, 每當組織中的人員使用報告訊息增益集來報告電子郵件訊息時, 您的全域系統管理員、安全性管理員和/或安全性讀取者都會收到該郵件的複本。</span><span class="sxs-lookup"><span data-stu-id="cb305-181">With this rule in place, whenever someone in your organization reports an email message using the Report Message add-in, your global administrator, security administrator, and/or security reader will receive a copy of that message.</span></span> <span data-ttu-id="cb305-182">此資訊可讓您設定或調整原則, 例如[Office 365 ATP 安全連結](atp-safe-links.md)原則或[反垃圾郵件](anti-spam-protection.md)設定。</span><span class="sxs-lookup"><span data-stu-id="cb305-182">This information can enable you to set up or adjust policies, such as [Office 365 ATP Safe Links](atp-safe-links.md) policies, or your [anti-spam](anti-spam-protection.md) settings.</span></span> 

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="cb305-183">瞭解如何使用報告訊息增益集</span><span class="sxs-lookup"><span data-stu-id="cb305-183">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="cb305-184">請參閱[使用報告訊息增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。</span><span class="sxs-lookup"><span data-stu-id="cb305-184">See [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="cb305-185">檢查或編輯報告郵件增益集的設定</span><span class="sxs-lookup"><span data-stu-id="cb305-185">Review or edit settings for the Report Message add-in</span></span>

<span data-ttu-id="cb305-186">您可以在 [[服務 & 增益集] 頁面](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)上, 查看及編輯 [報告郵件] 增益集的預設設定。</span><span class="sxs-lookup"><span data-stu-id="cb305-186">You can review and edit the default settings for the Report Message add-in on the [Services & Add-Ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="cb305-187">您必須是 Office 365 全域管理員或 Exchange Online 系統管理員, 才可完成此工作。</span><span class="sxs-lookup"><span data-stu-id="cb305-187">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task.</span></span>
    
1. <span data-ttu-id="cb305-188">移至 Microsoft 365 系統管理中心的 [服務] [ [& 增益集] 頁面](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)。</span><span class="sxs-lookup"><span data-stu-id="cb305-188">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the Microsoft 365 admin center.</span></span><br/><span data-ttu-id="cb305-189">![新 Microsoft 365 系統管理中心的 [服務和增益集] 頁面](media/ServicesAddInsPageNewM365AdminCenter.png)</span><span class="sxs-lookup"><span data-stu-id="cb305-189">![Services and Add-Ins page in the new Microsoft 365 Admin Center](media/ServicesAddInsPageNewM365AdminCenter.png)</span></span><br/>

2. <span data-ttu-id="cb305-190">尋找並選取 [報告訊息] 增益集。</span><span class="sxs-lookup"><span data-stu-id="cb305-190">Find and select the Report Message add-in.</span></span><br/>![尋找並選取報告郵件增益集](media/FindReportMessageAddIn.png)<br/> 
    
3. <span data-ttu-id="cb305-192">在 [報告訊息] 畫面上, 視需要查看和編輯您組織的設定。</span><span class="sxs-lookup"><span data-stu-id="cb305-192">On the Report Message screen, review and edit settings as appropriate for your organization.</span></span><br/>![報告郵件增益集的設定](media/EditReportMessageAddIn.png)<br/> 

## <a name="related-topics"></a><span data-ttu-id="cb305-194">相關主題</span><span class="sxs-lookup"><span data-stu-id="cb305-194">Related topics</span></span>

[<span data-ttu-id="cb305-195">使用報告訊息增益集</span><span class="sxs-lookup"><span data-stu-id="cb305-195">Use the Report Message add-in</span></span>](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
  
[<span data-ttu-id="cb305-196">在安全性&amp;與合規性中心中查看電子郵件安全性報告</span><span class="sxs-lookup"><span data-stu-id="cb305-196">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="cb305-197">查看 Office 365 的報告高級威脅防護</span><span class="sxs-lookup"><span data-stu-id="cb305-197">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

[<span data-ttu-id="cb305-198">在安全性&amp;與合規性中心使用 Explorer</span><span class="sxs-lookup"><span data-stu-id="cb305-198">Use Explorer in the Security &amp; Compliance Center</span></span>](use-explorer-in-security-and-compliance.md)
  

