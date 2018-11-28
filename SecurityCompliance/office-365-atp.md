---
title: Office 365 進階威脅防護
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 11/27/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
description: Office 365 進階威脅保護包含詐騙智慧、 安全的連結、 安全附件及進階的反網路釣魚功能。進階的威脅保護也要延伸至檔案的 SharePoint Online、 OneDrive for Business 和 Microsoft 小組。
ms.openlocfilehash: c147fde4e470b998a66a2cb456be71f635db25d7
ms.sourcegitcommit: 2cf7f5bb282c971d33e00f65d9982a3f14aec74e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/27/2018
ms.locfileid: "26706307"
---
# <a name="office-365-advanced-threat-protection"></a><span data-ttu-id="ec80a-104">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="ec80a-104">Office 365 Advanced Threat Protection</span></span>

## <a name="overview"></a><span data-ttu-id="ec80a-105">概觀</span><span class="sxs-lookup"><span data-stu-id="ec80a-105">Overview</span></span>

<span data-ttu-id="ec80a-106">Office 365 進階威脅保護 (ATP) 有幫助保護您的組織從惡意的攻擊：</span><span class="sxs-lookup"><span data-stu-id="ec80a-106">Office 365 Advanced Threat Protection (ATP) helps to protect your organization from malicious attacks by:</span></span>
  
- <span data-ttu-id="ec80a-107">掃描惡意程式碼[ATP 安全](atp-safe-attachments.md)附件的電子郵件的附件</span><span class="sxs-lookup"><span data-stu-id="ec80a-107">Scanning email attachments for malware with [ATP Safe Attachments](atp-safe-attachments.md)</span></span>
    
- <span data-ttu-id="ec80a-108">掃描的網頁位址 (Url) 中的電子郵件及 Office 文件的[ATP 安全連結](atp-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="ec80a-108">Scanning web addresses (URLs) in email messages and Office documents with [ATP Safe Links](atp-safe-links.md)</span></span>
    
- <span data-ttu-id="ec80a-109">識別和封鎖與[SharePoint、 OneDrive 及 Microsoft 小組 ATP](atp-for-spo-odb-and-teams.md)線上文件庫中的惡意檔案</span><span class="sxs-lookup"><span data-stu-id="ec80a-109">Identifying and blocking malicious files in online libraries with [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md)</span></span>
    
- <span data-ttu-id="ec80a-110">檢查未經授權詐騙[詐騙智慧](learn-about-spoof-intelligence.md)與電子的郵件</span><span class="sxs-lookup"><span data-stu-id="ec80a-110">Checking email messages for unauthorized spoofing with [spoof intelligence](learn-about-spoof-intelligence.md)</span></span>
    
- <span data-ttu-id="ec80a-111">偵測當某人嘗試模擬您的使用者與您的組織與[Office 365 的 ATP 反網路釣魚功能](atp-anti-phishing.md)的自訂網域</span><span class="sxs-lookup"><span data-stu-id="ec80a-111">Detecting when someone attempts to impersonate your users and your organization's custom domains with [ATP anti-phishing capabilities in Office 365](atp-anti-phishing.md)</span></span>
    
<span data-ttu-id="ec80a-p102">**透過 Office 365 ATP 保護會由貴組織的安全性小組的安全連結、 安全附件及反網路釣魚定義的原則**。請務必定期檢閱並修改原則來保留其最新及才會加到服務的新功能的優點。[提供報告所](view-reports-for-atp.md)要顯示 ATP 組織的運作方式。這些報告也可顯示您您可能需要重新檢閱並更新您的原則的區域。而且，如果您有都會標記為惡意程式碼的不應該是相同網域或檔案您想要檢查的 Microsoft 的檔案，您可以[提交給 Microsoft 進行分析的檔案](#submit-a-suspicious-file-to-microsoft-for-analysis)。</span><span class="sxs-lookup"><span data-stu-id="ec80a-p102">**Protection through Office 365 ATP is determined by policies that your organization's security team defines for Safe Links, Safe Attachments, and Anti-Phishing**. It's important to periodically review and revise your policies to keep them up to date and to take advantages of new features that are added to the service. [Reports are available](view-reports-for-atp.md) to show how ATP is working for your organization. These reports can also show you areas where you might need to review and update your policies. And, if you have files that are marked as malware that shouldn't be, or files you'd like Microsoft to examine, you can [submit a file to Microsoft for analysis](#submit-a-suspicious-file-to-microsoft-for-analysis).</span></span>

## <a name="new-features-are-continually-being-added-to-atp"></a><span data-ttu-id="ec80a-117">ATP 持續所加入的新功能</span><span class="sxs-lookup"><span data-stu-id="ec80a-117">New features are continually being added to ATP</span></span>

<span data-ttu-id="ec80a-p103">我們會繼續新增至 Office 365 的新功能並包含 ATP。以下是一些新功能，其中有些呼叫在檢閱和更新 ATP 原則的清單。若要深入了解傳入 ATP （或在一般的 Microsoft 365） 的新功能，請造訪[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)。</span><span class="sxs-lookup"><span data-stu-id="ec80a-p103">We are continuing to add new features to Office 365, and that includes ATP. Below is a list of several new features, some of which call for an ATP policy to be reviewed and updated. To learn more about new features coming to ATP (or Microsoft 365 in general), visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=O365).</span></span>
  
- <span data-ttu-id="ec80a-p104">從開始落後年 10 月 2017年，ATP 安全連結保護會延伸至 Url 中電子郵件時的 Url 是以套用至 Office 365 ProPlus 的文件，例如 Word、 Excel、 PowerPoint 及 Visio 在 Windows，以及 Office iOS 及 Android 裝置上的應用程式。（請確定您使用[Office 的現代驗證](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)）。</span><span class="sxs-lookup"><span data-stu-id="ec80a-p104">Beginning in late October 2017, ATP Safe Links protection is extended to apply to URLs in email as well as URLs in Office 365 ProPlus documents, such as Word, Excel, PowerPoint, and Visio on Windows, as well as Office apps on iOS and Android devices. (Make sure you're using [Modern Authentication for Office](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).)</span></span>
    
- <span data-ttu-id="ec80a-p105">從開始年 3 月 2018年，ATP 安全連結保護會延伸至套用至組織內的人員之間所寄送的電子郵件。（請務必[檢閱](set-up-atp-safe-links-policies.md)並編輯 ATP 安全連結原則）。</span><span class="sxs-lookup"><span data-stu-id="ec80a-p105">Beginning in March 2018, ATP Safe Links protection is extended to apply to email sent between people within an organization. (Make sure to [review and edit your ATP Safe Links policies](set-up-atp-safe-links-policies.md).)</span></span>

- <span data-ttu-id="ec80a-125">開始在落後 5 2018、 安全性[隔離](quarantine-email-messages.md)功能&amp;規範中心會被擴充至[ATP 的 SharePoint Online、 OneDrive for Business 和 Microsoft 小組](atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="ec80a-125">Beginning in late May 2018, [quarantine](quarantine-email-messages.md) capabilities in the Security &amp; Compliance Center are being extended to [ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>
 
- <span data-ttu-id="ec80a-p106">從開始 2018年第二個半，ATP 安全連結保護會延伸至套用至 Office Online （線上 Word、 Excel Online、 PowerPoint Online 和 OneNote Online） 和 Office 365 ProPlus mac 上的 Url（請務必[檢閱](set-up-atp-safe-links-policies.md)並編輯 ATP 安全連結原則）。</span><span class="sxs-lookup"><span data-stu-id="ec80a-p106">Beginning in the second half of 2018, ATP Safe Links protection is extended to apply to URLs in Office Online (Word Online, Excel Online, PowerPoint Online, and OneNote Online) and Office 365 ProPlus on Mac. (Make sure to [review and edit your ATP Safe Links policies](set-up-atp-safe-links-policies.md).)</span></span>

- <span data-ttu-id="ec80a-128">開始在 9 月 2018年、 [Office 365 ATP 警告頁面](atp-safe-links-warning-pages.md)] 功能的新的色彩配置、 詳細資訊及能夠繼續而不管網站授與警告和建議。</span><span class="sxs-lookup"><span data-stu-id="ec80a-128">Beginning in September 2018, [Office 365 ATP warning pages](atp-safe-links-warning-pages.md) feature a new color scheme, more details, and the ability to continue to a site despite given warnings and recommendations.</span></span> 
 
- <span data-ttu-id="ec80a-p107">開始在年 10 月 2018年及後續的幾個月內啟用，當使用者使用 Outlook Web 應用程式 (OWA) 或 Outlook、 ATP 安全連結轉譯原始 Url 不會修正 Url。（我們呼叫此原生連結可見性）。</span><span class="sxs-lookup"><span data-stu-id="ec80a-p107">Beginning in October 2018 and rolling out over the next several months, when people are using Outlook Web Application (OWA) or Outlook, ATP Safe Links renders original URLs, not rewritten URLs. (We call this native link visibility.)</span></span>

      
## <a name="get-office-365-atp"></a><span data-ttu-id="ec80a-131">取得 Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="ec80a-131">Get Office 365 ATP</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ec80a-p108">Office 365 ATP 隨附於訂閱，例如 Microsoft 365 企業版、 Office 365 企業版 E5、 Office 365 教育版 A5，以及[Microsoft 365 Business](https://docs.microsoft.com/en-us/microsoft-365/business/security-features)。如果您的組織有不包含 Office 365 ATP Office 365 訂閱，可能可以做為附加元件購買 ATP。如需詳細資訊，請參閱[Office 365 進階威脅 Protection 服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="ec80a-p108">Office 365 ATP is included in subscriptions, such as Microsoft 365 Enterprise, Office 365 Enterprise E5, Office 365 Education A5, and [Microsoft 365 Business](https://docs.microsoft.com/en-us/microsoft-365/business/security-features). If your organization has an Office 365 subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on. For more information, see [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> 

1. <span data-ttu-id="ec80a-135">為通用或安全性管理員，請移至[https://portal.office.com](https://portal.office.com)和登入 Office 365 您工作或學校的帳戶。</span><span class="sxs-lookup"><span data-stu-id="ec80a-135">As a global or security administrator, go to [https://portal.office.com](https://portal.office.com) and sign in with your work or school account for Office 365.</span></span> 
    
2. <span data-ttu-id="ec80a-136">選擇 [**管理** \> **帳務**查看您目前的訂閱所包含的內容。</span><span class="sxs-lookup"><span data-stu-id="ec80a-136">Choose **Admin** \> **Billing** to see what your current subscription includes.</span></span> <br/><span data-ttu-id="ec80a-137">![全域管理員身分登入在 portal.office.com 並移至 [系統管理\>計費](media/18a3546c-bd1f-4f49-82ec-0184909b42c2.png)</span><span class="sxs-lookup"><span data-stu-id="ec80a-137">![As a global admin, sign in at portal.office.com and go to Admin \> Billing](media/18a3546c-bd1f-4f49-82ec-0184909b42c2.png)</span></span>
  
3. <span data-ttu-id="ec80a-138">如果您看到**Office 365 企業版 E5**、 **Office 365 教育版 A5**或**Microsoft 365 Business**，您的組織有 ATP。</span><span class="sxs-lookup"><span data-stu-id="ec80a-138">If you see **Office 365 Enterprise E5**, **Office 365 Education A5**, or **Microsoft 365 Business**, then your organization has ATP.</span></span> <br/><span data-ttu-id="ec80a-p109">如果您看到不同的訂閱，例如**Office 365 企業版 E3**或**Office 365 企業版 E1**，請考慮新增 ATP。若要這樣做，選擇 [ **+ 新增訂閱**。</span><span class="sxs-lookup"><span data-stu-id="ec80a-p109">If you see a different subscription, such as **Office 365 Enterprise E3** or **Office 365 Enterprise E1**, consider adding ATP. To do that, choose **+ Add subscription**.</span></span>
    
<span data-ttu-id="ec80a-141">您有 ATP 下, 一步是為您的安全性小組來定義原則。</span><span class="sxs-lookup"><span data-stu-id="ec80a-141">Once you have ATP, the next step is for your security team to define policies.</span></span> 
  
## <a name="define-policies-for-atp"></a><span data-ttu-id="ec80a-142">為 ATP 定義原則</span><span class="sxs-lookup"><span data-stu-id="ec80a-142">Define policies for ATP</span></span>

- <span data-ttu-id="ec80a-143">**[設定 Office 365 中的 ATP 反網路釣魚原則](set-up-anti-phishing-policies.md)** 包括模擬型攻擊以防止傳送電子郵件訊息的攻擊者顯示可從信任的人員或網域</span><span class="sxs-lookup"><span data-stu-id="ec80a-143">**[Set up ATP anti-phishing policies in Office 365](set-up-anti-phishing-policies.md)** including impersonation-based attacks to protect against attackers who send email messages that appear to be from trusted people or domains</span></span> 

- <span data-ttu-id="ec80a-144">**[設定 Office 365 中的 ATP 安全連結原則](set-up-atp-safe-links-policies.md)** 包括您的組織[自訂封鎖的 Url 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)和[自訂 「 未修正"Url 清單](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)</span><span class="sxs-lookup"><span data-stu-id="ec80a-144">**[Set up ATP Safe Links policies in Office 365](set-up-atp-safe-links-policies.md)** including your organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md) and [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)</span></span>
    
- <span data-ttu-id="ec80a-145">**[設定 Office 365 中的 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)** 可以包含[動態傳遞和預覽](dynamic-delivery-and-previewing.md)</span><span class="sxs-lookup"><span data-stu-id="ec80a-145">**[Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md)** that can include [Dynamic Delivery and previewing](dynamic-delivery-and-previewing.md)</span></span>
  
## <a name="see-how-atp-is-working-by-viewing-reports"></a><span data-ttu-id="ec80a-146">請參閱 ATP 檢視報告的運作方式</span><span class="sxs-lookup"><span data-stu-id="ec80a-146">See how ATP is working by viewing reports</span></span>

<span data-ttu-id="ec80a-147">ATP 原則已備妥之後，就有一個報表可用來顯示服務運作的方式。</span><span class="sxs-lookup"><span data-stu-id="ec80a-147">After your ATP policies are in place, reports are available to show how the service is working.</span></span>

<span data-ttu-id="ec80a-148">[![安全性&amp;規範中心儀表板可協助您看到其用於進階威脅保護](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)](view-reports-for-atp.md)</span><span class="sxs-lookup"><span data-stu-id="ec80a-148">[![The Security &amp; Compliance Center dashboard can help you see where Advanced Threat Protection is working](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)](view-reports-for-atp.md)</span></span>
  
1. <span data-ttu-id="ec80a-p110">請確定您是 Office 365 全域管理員、 安全性管理員或安全性讀者。(請參閱[中的 Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。)</span><span class="sxs-lookup"><span data-stu-id="ec80a-p110">Make sure that you are an Office 365 global administrator, security administrator, or security reader. (See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).)</span></span>
    
2. <span data-ttu-id="ec80a-151">[進階威脅保護的檢視報告](view-reports-for-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="ec80a-151">[View reports for Advanced Threat Protection](view-reports-for-atp.md).</span></span>
    
3. <span data-ttu-id="ec80a-p111">是否需要進行調整您的安全性原則。請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="ec80a-p111">If needed, make adjustments to your security policies. See the following resources:</span></span>

  - [<span data-ttu-id="ec80a-154">Office 365 中的 ATP 反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="ec80a-154">ATP anti-phishing policies in Office 365</span></span>](set-up-anti-phishing-policies.md)
    
  - [<span data-ttu-id="ec80a-155">Office 365 中的 ATP 安全連結原則</span><span class="sxs-lookup"><span data-stu-id="ec80a-155">ATP Safe Links policies in Office 365</span></span>](set-up-atp-safe-links-policies.md)
    
  - [<span data-ttu-id="ec80a-156">Office 365 中的 ATP 安全附件原則</span><span class="sxs-lookup"><span data-stu-id="ec80a-156">ATP Safe Attachments policies in Office 365</span></span>](set-up-atp-safe-attachments-policies.md)
    
    
## <a name="submit-a-suspicious-file-to-microsoft-for-analysis"></a><span data-ttu-id="ec80a-157">提交給 Microsoft 進行分析可疑的檔案</span><span class="sxs-lookup"><span data-stu-id="ec80a-157">Submit a suspicious file to Microsoft for analysis</span></span>

- <span data-ttu-id="ec80a-p112">如果您收到您懷疑可能是惡意程式碼檔案，您可以提交給 Microsoft 進行分析該檔案。請造訪[Windows 防禦者安全性智慧提交入口網站](https://go.microsoft.com/fwlink/?linkid=857185)。</span><span class="sxs-lookup"><span data-stu-id="ec80a-p112">If you get a file that you suspect could be malware, you can submit that file to Microsoft for analysis. Visit the [Windows Defender Security Intelligence submission portal](https://go.microsoft.com/fwlink/?linkid=857185).</span></span>

- <span data-ttu-id="ec80a-160">如果您要取得您想要提交給 Microsoft 進行分析的電子郵件訊息 （使用或不含附件），請使用[報告郵件增益集](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="ec80a-160">If you get an email message (with or without an attachment) that you'd like to submit to Microsoft for analysis, use the [Report Message add-in](enable-the-report-message-add-in.md).</span></span> 
  

