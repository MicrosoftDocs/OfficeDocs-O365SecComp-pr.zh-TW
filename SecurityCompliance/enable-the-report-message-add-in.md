---
title: 啟用報告訊息增益集
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/18/2019
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
description: 了解如何啟用報表訊息增益集 Outlook 和 Outlook web 針對個別使用者或整個組織。
ms.openlocfilehash: 013145813e8feb3e7389f6248ee26195c1df3d08
ms.sourcegitcommit: 1169a5759b9c2336fbc89d4651daf29e556f62fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/18/2019
ms.locfileid: "28727867"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="9cfb4-103">啟用報告訊息增益集</span><span class="sxs-lookup"><span data-stu-id="9cfb4-103">Enable the Report Message add-in</span></span>

## <a name="overview"></a><span data-ttu-id="9cfb4-104">概觀</span><span class="sxs-lookup"><span data-stu-id="9cfb4-104">Overview</span></span>

<span data-ttu-id="9cfb4-p101">報告訊息的增益集 Outlook 和 Outlook web 上的啟用人員輕鬆地回報被歸類電子郵件是否安全或惡意、 Microsoft 及分析及其子公司。Microsoft 使用這些送出改善電子郵件保護技術的有效性。此外，如果您的組織會使用[Office 365 進階威脅保護](office-365-atp.md)或[Office 365 威脅智慧](office-365-ti.md)、 報告郵件增益集提供實用的資訊可用於檢閱及更新您的組織安全性小組安全性原則。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-p101">The Report Message add-in for Outlook and Outlook on the web enables people to easily report misclassified email, whether safe or malicious, to Microsoft and its affiliates for analysis. Microsoft uses these submissions to improve the effectiveness of email protection technologies. In addition, if your organization is using [Office 365 Advanced Threat Protection](office-365-atp.md) or [Office 365 Threat Intelligence](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span> 

<span data-ttu-id="9cfb4-p102">例如，假設人員會報告為網路釣魚許多的郵件。此資訊以循[安全性儀表板](security-dashboard.md)和其他報表中。貴組織的安全性小組可以使用這項資訊以反網路釣魚原則可能需要更新的指示。或者，如果人員所報告的郵件已標示為垃圾郵件郵件不是垃圾郵件報告增益集使用許多組織的安全性小組可能需要調整[反垃圾郵件原則](configure-the-anti-spam-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-p102">For example, suppose that people are reporting a lot of messages as phishing. This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports. Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated. Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-the-anti-spam-policies.md).</span></span> 

<span data-ttu-id="9cfb4-112">報告郵件增益集的運作方式與您的 Office 365 訂閱及下列產品：</span><span class="sxs-lookup"><span data-stu-id="9cfb4-112">The Report Message add-in works with your Office 365 subscription and the following products:</span></span>
 - <span data-ttu-id="9cfb4-113">Outlook 網頁版</span><span class="sxs-lookup"><span data-stu-id="9cfb4-113">Outlook on the web</span></span>
 - <span data-ttu-id="9cfb4-114">Outlook 2013 SP1</span><span class="sxs-lookup"><span data-stu-id="9cfb4-114">Outlook 2013 SP1</span></span>
 - <span data-ttu-id="9cfb4-115">Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9cfb4-115">Outlook 2016</span></span>
 - <span data-ttu-id="9cfb4-116">Mac 版 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9cfb4-116">Outlook 2016 for Mac</span></span>
 - <span data-ttu-id="9cfb4-117">Office 365 ProPlus 所含的 outlook</span><span class="sxs-lookup"><span data-stu-id="9cfb4-117">Outlook included with Office 365 ProPlus</span></span>

> [!NOTE]
> <span data-ttu-id="9cfb4-p103">報告訊息的增益集 Outlook 和 Outlook web 上的是不完全相同兩回事[Outlook 垃圾郵件篩選](https://support.office.com/article/Overview-of-the-Junk-Email-Filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)，但兩者都可以用來將電子郵件標示為垃圾郵件、 未垃圾郵件或網路釣魚嘗試。報告訊息的增益集 Outlook 和 Outlook web 上的而 Outlook 垃圾郵件篩選工具用來將組織中使用者信箱的電子郵件會被歸類電子郵件的相關通知 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-p103">The Report Message add-in for Outlook and Outlook on the web is not exactly the same thing as the [Outlook Junk Email Filter](https://support.office.com/article/Overview-of-the-Junk-Email-Filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089), although both can be used to mark email as junk, not junk, or a phishing attempt. The Report Message add-in for Outlook and Outlook on the web notifies Microsoft about misclassified email, whereas the Outlook Junk Email Filter is used to organize email messages in a user's mailbox.</span></span> 
  
<span data-ttu-id="9cfb4-120">如果您是個別使用者，您還可以[讓報表訊息的增益集自己](#get-the-report-message-add-in-for-yourself)。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-120">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span> 
  
<span data-ttu-id="9cfb4-p104">如果您是 Office 365 全域管理員或 Exchange Online 管理員，而 Exchange 設定為使用 OAuth 驗證，您可以[啟用報表訊息增益集的組織](#get-and-enable-the-report-message-add-in-for-your-organization)。報告郵件增益集現在已可透過[集中式部署](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-p104">If you're an Office 365 global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization). The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span></span>
    
## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="9cfb4-123">您要報告郵件取得增益集</span><span class="sxs-lookup"><span data-stu-id="9cfb4-123">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="9cfb4-124">在[Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps)、 搜尋[報告郵件增益集](https://appsource.microsoft.com/product/office/wa104381180)。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-124">In [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps), search for the [Report Message add-in](https://appsource.microsoft.com/product/office/wa104381180).</span></span>
    
2. <span data-ttu-id="9cfb4-125">選擇 [**取得 IT 現在**。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-125">Choose **GET IT NOW**.</span></span><br/><span data-ttu-id="9cfb4-126">![報告訊息-立即取得](media/ReportMessageGETITNOW.png)</span><span class="sxs-lookup"><span data-stu-id="9cfb4-126">![Report Message - Get It Now](media/ReportMessageGETITNOW.png)</span></span><br/> 
    
3. <span data-ttu-id="9cfb4-p105">檢閱使用及隱私權原則的字詞。然後選擇 [**繼續]**。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-p105">Review the terms of use and privacy policy. Then choose **Continue**.</span></span> 
    
4. <span data-ttu-id="9cfb4-129">登入 Office 365 中，使用您的工作或學校帳戶 （供商務使用） 或 Microsoft 帳戶 （適用於個人使用）。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-129">Sign in to Office 365 using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>
    
<span data-ttu-id="9cfb4-130">增益集已安裝並啟用之後，您會看到下列圖示：</span><span class="sxs-lookup"><span data-stu-id="9cfb4-130">After the add-in is installed and enabled, you'll see the following icons:</span></span> 

- <span data-ttu-id="9cfb4-131">在 Outlook 中，圖示外觀類似如下：</span><span class="sxs-lookup"><span data-stu-id="9cfb4-131">In Outlook, the icon looks like this:</span></span> <br/> ![報告郵件增益集的 Outlook 圖示](media/OutlookReportMessageIcon.png)<br/>
- <span data-ttu-id="9cfb4-133">在 Outlook Web App （或 [網路上的 Outlook） 圖示外觀類似如下：</span><span class="sxs-lookup"><span data-stu-id="9cfb4-133">In Outlook Web App (or Outlook on the web), the icon looks like this:</span></span><br/>![Outlook 郵件報告增益集的 web 圖示](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

> [!TIP]
> <span data-ttu-id="9cfb4-135">下一個步驟中，以了解如何[使用報告郵件增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-135">As a next step, learn how to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>
  
## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="9cfb4-136">取得並啟用報表訊息增益集的組織</span><span class="sxs-lookup"><span data-stu-id="9cfb4-136">Get and enable the Report Message add-in for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9cfb4-p106">您必須是 Office 365 全域管理員或 Exchange Online 管理員，才可完成此工作。另外，Exchange 必須設定為使用 OAuth 驗證來深入了解，請參閱[Exchange 需求 （增益集的集中式部署）](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins&view=o365-worldwide#exchange-requirements)。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-p106">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task. In addition, Exchange must be configured to use OAuth authentication To learn more, see [Exchange requirements (Centralized Deployment of add-ins)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins&view=o365-worldwide#exchange-requirements).</span></span> 

1. <span data-ttu-id="9cfb4-139">前往 Microsoft 365 系統管理中心[服務 & 增益集] 頁面](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-139">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the Microsoft 365 admin center.</span></span><br/><span data-ttu-id="9cfb4-140">![在新的 Microsoft 365 系統管理中心服務與增益集] 頁面上](media/ServicesAddInsPageNewM365AdminCenter.png)</span><span class="sxs-lookup"><span data-stu-id="9cfb4-140">![Services and Add-Ins page in the new Microsoft 365 Admin Center](media/ServicesAddInsPageNewM365AdminCenter.png)</span></span><br/> 
    
2. <span data-ttu-id="9cfb4-141">選擇 [ **+ 部署增益集**。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-141">Choose **+ Deploy Add-in**.</span></span><br/><span data-ttu-id="9cfb4-142">![選擇部署增益集](media/ServicesAddIns-ChooseDeployAddIn.png)</span><span class="sxs-lookup"><span data-stu-id="9cfb4-142">![Choose Deploy Add-In](media/ServicesAddIns-ChooseDeployAddIn.png)</span></span><br/> 
    
3. <span data-ttu-id="9cfb4-143">在**新增益集**] 畫面上，檢閱資訊，並再選擇 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-143">In the **New Add-In** screen, review the information, and then choose **Next**.</span></span><br/><span data-ttu-id="9cfb4-144">![新的增益集詳細資料](media/NewAddInScreen1.png)</span><span class="sxs-lookup"><span data-stu-id="9cfb4-144">![New Add-In details](media/NewAddInScreen1.png)</span></span><br/>
    
4. <span data-ttu-id="9cfb4-145">選取 [**我想要新增增益集來自 Office 市集**、，然後選擇 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-145">Select **I want to add an Add-In from the Office Store**, and then choose **Next**.</span></span><br/><span data-ttu-id="9cfb4-146">![我想要新增新增益集](media/NewAddInScreen2.png)</span><span class="sxs-lookup"><span data-stu-id="9cfb4-146">![I want to add an new Add-In](media/NewAddInScreen2.png)</span></span><br/> 
    
5. <span data-ttu-id="9cfb4-147">搜尋**報表訊息**，並的結果旁的**報表訊息增益集**清單中，選擇 [**新增]**。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-147">Search for **Report Message**, and in the list of results, next to the **Report Message Add-In**, choose **Add**.</span></span><br/><span data-ttu-id="9cfb4-148">![搜尋報告的郵件，然後選擇 [新增]](media/NewAddInScreen3.png)</span><span class="sxs-lookup"><span data-stu-id="9cfb4-148">![Search for Report Message and then choose Add](media/NewAddInScreen3.png)</span></span><br/>
    
6. <span data-ttu-id="9cfb4-149">在**報表訊息**] 畫面上，檢閱資訊，然後選擇 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-149">On the **Report Message** screen, review the information, and then choose **Next**.</span></span><br/><span data-ttu-id="9cfb4-150">![報告郵件詳細資料](media/ReportMessageAdd-InNewScreen4.png)</span><span class="sxs-lookup"><span data-stu-id="9cfb4-150">![Report Message details](media/ReportMessageAdd-InNewScreen4.png)</span></span><br/>

7. <span data-ttu-id="9cfb4-151">指定 Outlook 使用者預設設定，然後選擇 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-151">Specify the user default settings for Outlook, and  then choose **Next**.</span></span><br/><span data-ttu-id="9cfb4-152">![報告 for Outlook 訊息預設設定](media/ReportMessageOptionsScreen5.png)</span><span class="sxs-lookup"><span data-stu-id="9cfb4-152">![Report Message default settings for Outlook](media/ReportMessageOptionsScreen5.png)</span></span><br/>

8. <span data-ttu-id="9cfb4-153">指定誰取得報表訊息增益集] 中，然後選擇 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-153">Specify who gets the Report Message Add-in, and then choose **Save**.</span></span> <br/><span data-ttu-id="9cfb4-154">![誰可以取得報表訊息增益集](media/ReportMessageOptionsScreen6.png)</span><span class="sxs-lookup"><span data-stu-id="9cfb4-154">![Who gets the Report Message add-in](media/ReportMessageOptionsScreen6.png)</span></span><br/>

> [!TIP]
> <span data-ttu-id="9cfb4-155">建議您[設定要取得一份報告的使用者的電子郵件的規則](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users)。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-155">We recommend [setting up a rule to get a copy of email messages reported by your users](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users).</span></span>

<span data-ttu-id="9cfb4-p107">根據您選取的項目設定時的增益集 (步驟 7-8 上方)、 人員在組織中的有[報表訊息增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)提供。在組織中的人員會看到下列圖示：</span><span class="sxs-lookup"><span data-stu-id="9cfb4-p107">Depending on what you selected when you set up the add-in (steps 7-8 above), people in your organization will have the [Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) available. People in your organization will see the following icons:</span></span> 

- <span data-ttu-id="9cfb4-158">在 Outlook 中，圖示外觀類似如下：</span><span class="sxs-lookup"><span data-stu-id="9cfb4-158">In Outlook, the icon looks like this:</span></span> <br/> ![報告郵件增益集的 Outlook 圖示](media/OutlookReportMessageIcon.png)<br/>
- <span data-ttu-id="9cfb4-160">在 Outlook Web App （或 [網路上的 Outlook） 圖示外觀類似如下：</span><span class="sxs-lookup"><span data-stu-id="9cfb4-160">In Outlook Web App (or Outlook on the web), the icon looks like this:</span></span><br/>![在 [網頁報表訊息增益集] 圖示上的 outlook](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

> [!TIP]
> <span data-ttu-id="9cfb4-162">當您通知使用者有關郵件報告增益集時，包含要[使用的報表訊息增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)的連結。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-162">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users"></a><span data-ttu-id="9cfb4-163">若要取得一份報告的使用者的電子郵件設定的規則</span><span class="sxs-lookup"><span data-stu-id="9cfb4-163">Set up a rule to get a copy of email messages reported by your users</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9cfb4-164">您必須是 Exchange Online 管理員，才能執行這項工作。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-164">You must be an Exchange Online Administrator to perform this task.</span></span>
  
<span data-ttu-id="9cfb4-p108">您可以設定以取得一份報告的組織中使用者的電子郵件的規則。下載並啟用的報告訊息增益集組織之後，您可以這麼做。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-p108">You can set up a rule to get a copy of email messages reported by users in your organization. You do this after you have downloaded and enabled the Report Message add-in for your organization.</span></span>
  
1. <span data-ttu-id="9cfb4-167">在 Exchange 系統管理中心中，選擇 [**郵件流程** \> **規則**。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-167">In the Exchange Admin Center, choose **mail flow** \> **rules**.</span></span> 
    
2. <span data-ttu-id="9cfb4-168">選擇 [ **+** \> **建立新的規則**。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-168">Choose **+** \> **Create a new rule**.</span></span> 
    
3. <span data-ttu-id="9cfb4-169">在 [**名稱**] 方塊中輸入名稱，例如送出。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-169">In the **Name** box, type a name, such as Submissions.</span></span>
    
4. <span data-ttu-id="9cfb4-170">**如果套用此規則**] 清單中選擇 [**收件者的地址包含...**]。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-170">In the **Apply this rule if** list, choose **The recipient address includes...**.</span></span> 
    
5. <span data-ttu-id="9cfb4-171">在 [**指定單字或片語**] 畫面中，新增`junk@office365.microsoft.com`和`phish@office365.microsoft.com`，然後選擇 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-171">In the **specify words or phrases** screen, add `junk@office365.microsoft.com` and `phish@office365.microsoft.com`, and then choose **OK**.</span></span><br/><span data-ttu-id="9cfb4-172">![指定之規則的垃圾郵件] 及 [phish 電子郵件地址](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)</span><span class="sxs-lookup"><span data-stu-id="9cfb4-172">![Specify the junk and phish email addresses for the rule](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)</span></span><br/>
  
6. <span data-ttu-id="9cfb4-173">在**執行下列動作...** ] 清單中，選擇 [ **[密件副本郵件到...**。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-173">In the **Do the following...** list, choose **Bcc the message to...**.</span></span> 
    
7. <span data-ttu-id="9cfb4-174">新增全域管理員、 安全性管理員及/或安全性讀者應該接收人員向 Microsoft 報告每個電子郵件訊息的複本並再選擇 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-174">Add a global administrator, security administrator, and/or security reader who should receive a copy of each email message that people report to Microsoft, and then choose **OK**.</span></span><br/><span data-ttu-id="9cfb4-175">![新增全域或安全性管理員接收每個報告的郵件的複本](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)</span><span class="sxs-lookup"><span data-stu-id="9cfb4-175">![Add a global or security administrator to receive a copy of each reported message](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)</span></span><br/>
  
8. <span data-ttu-id="9cfb4-176">選取 [**此規則使用嚴重性層級的稽核**，然後選擇 [**中等**。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-176">Select **Audit this rule with severity level**, and choose **Medium**.</span></span> 
    
9. <span data-ttu-id="9cfb4-177">[**選擇此規則模式**] 下選擇 [**強制執行**。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-177">Under **Choose a mode for this rule**, choose **Enforce**.</span></span><br/><span data-ttu-id="9cfb4-178">![設定規則，以取得每個報告的郵件的複本](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)</span><span class="sxs-lookup"><span data-stu-id="9cfb4-178">![Set up a rule to get a copy of each reported message](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)</span></span><br/>
  
10. <span data-ttu-id="9cfb4-179">選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-179">Choose **Save**.</span></span> 
    
<span data-ttu-id="9cfb4-p109">與備妥此規則，每當您組織中某人報告電子郵件訊息的報告訊息 」 增益集，使用您全域管理員、 安全性管理員及/或安全性讀取者會收到該郵件的複本。這項資訊可讓您設定或調整原則，例如[Office 365 ATP 安全連結](atp-safe-links.md)原則或[反垃圾郵件](anti-spam-protection.md)設定。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-p109">With this rule in place, whenever someone in your organization reports an email message using the Report Message add-in, your global administrator, security administrator, and/or security reader will receive a copy of that message. This information can enable you to set up or adjust policies, such as [Office 365 ATP Safe Links](atp-safe-links.md) policies, or your [anti-spam](anti-spam-protection.md) settings.</span></span> 

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="9cfb4-182">了解如何使用報告郵件增益集</span><span class="sxs-lookup"><span data-stu-id="9cfb4-182">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="9cfb4-183">請參閱[使用報告郵件增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-183">See [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="9cfb4-184">檢閱或編輯報表訊息增益集設定</span><span class="sxs-lookup"><span data-stu-id="9cfb4-184">Review or edit settings for the Report Message add-in</span></span>

<span data-ttu-id="9cfb4-185">您可以檢閱並編輯報表訊息增益集在[服務 & 增益集] 頁面上](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)的預設設定。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-185">You can review and edit the default settings for the Report Message add-in on the [Services & Add-Ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="9cfb4-186">您必須是 Office 365 全域管理員或 Exchange Online 管理員，才可完成此工作。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-186">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task.</span></span>
    
1. <span data-ttu-id="9cfb4-187">前往 Microsoft 365 系統管理中心[服務 & 增益集] 頁面](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-187">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the Microsoft 365 admin center.</span></span><br/><span data-ttu-id="9cfb4-188">![在新的 Microsoft 365 系統管理中心服務與增益集] 頁面上](media/ServicesAddInsPageNewM365AdminCenter.png)</span><span class="sxs-lookup"><span data-stu-id="9cfb4-188">![Services and Add-Ins page in the new Microsoft 365 Admin Center](media/ServicesAddInsPageNewM365AdminCenter.png)</span></span><br/>

2. <span data-ttu-id="9cfb4-189">尋找並選取 [郵件報告增益集。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-189">Find and select the Report Message add-in.</span></span><br/>![尋找並選取 [郵件報告增益集](media/FindReportMessageAddIn.png)<br/> 
    
3. <span data-ttu-id="9cfb4-191">在報表訊息] 畫面上，檢閱並編輯設定最適合您的組織。</span><span class="sxs-lookup"><span data-stu-id="9cfb4-191">On the Report Message screen, review and edit settings as appropriate for your organization.</span></span><br/>![設定報表訊息增益集 (英文）](media/EditReportMessageAddIn.png)<br/> 
  
## <a name="related-topics"></a><span data-ttu-id="9cfb4-193">相關主題</span><span class="sxs-lookup"><span data-stu-id="9cfb4-193">Related topics</span></span>

[<span data-ttu-id="9cfb4-194">使用報告郵件增益集</span><span class="sxs-lookup"><span data-stu-id="9cfb4-194">Use the Report Message add-in</span></span>](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
  
<span data-ttu-id="9cfb4-195">[在 [安全性] 中檢視電子郵件安全性報表&amp;規範中心](view-email-security-reports.md)</span><span class="sxs-lookup"><span data-stu-id="9cfb4-195">[View email security reports in the Security &amp; Compliance Center](view-email-security-reports.md)</span></span>

[<span data-ttu-id="9cfb4-196">Office 365 進階威脅保護的檢視報告</span><span class="sxs-lookup"><span data-stu-id="9cfb4-196">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

[<span data-ttu-id="9cfb4-197">使用瀏覽器安全性&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="9cfb4-197">Use Explorer in the Security &amp; Compliance Center</span></span>](use-explorer-in-security-and-compliance.md)
  

