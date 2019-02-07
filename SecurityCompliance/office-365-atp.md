---
title: Office 365 進階威脅防護
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/04/2019
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
description: Office 365 進階威脅保護包含詐騙智慧、 安全的連結、 安全附件及進階的反網路釣魚功能。進階的威脅保護也要延伸至檔案的 SharePoint Online、 OneDrive for Business 和 Microsoft 小組。
ms.openlocfilehash: b483ceb0da53b2f1c216f60d5271781072ebcf17
ms.sourcegitcommit: d6a28c4f6db6a676ca960173e8ff8f17d4aa1c4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2019
ms.locfileid: "29755224"
---
# <a name="office-365-advanced-threat-protection"></a><span data-ttu-id="64996-104">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="64996-104">Office 365 Advanced Threat Protection</span></span>

## <a name="overview-of-office-365-advanced-threat-protection"></a><span data-ttu-id="64996-105">Overview of Office 365 的進階的威脅保護</span><span class="sxs-lookup"><span data-stu-id="64996-105">Overview of Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="64996-106">Office 365 進階威脅保護 (ATP) 有幫助保護您的組織從惡意的攻擊：</span><span class="sxs-lookup"><span data-stu-id="64996-106">Office 365 Advanced Threat Protection (ATP) helps to protect your organization from malicious attacks by:</span></span>
  
- <span data-ttu-id="64996-107">掃描惡意程式碼[ATP 安全](atp-safe-attachments.md)附件的電子郵件的附件</span><span class="sxs-lookup"><span data-stu-id="64996-107">Scanning email attachments for malware with [ATP Safe Attachments](atp-safe-attachments.md)</span></span>
    
- <span data-ttu-id="64996-108">掃描的網頁位址 (Url) 中的電子郵件及 Office 文件的[ATP 安全連結](atp-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="64996-108">Scanning web addresses (URLs) in email messages and Office documents with [ATP Safe Links](atp-safe-links.md)</span></span>
    
- <span data-ttu-id="64996-109">識別和封鎖與[SharePoint、 OneDrive 及 Microsoft 小組 ATP](atp-for-spo-odb-and-teams.md)線上文件庫中的惡意檔案</span><span class="sxs-lookup"><span data-stu-id="64996-109">Identifying and blocking malicious files in online libraries with [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md)</span></span>
    
- <span data-ttu-id="64996-110">檢查未經授權詐騙[詐騙智慧](learn-about-spoof-intelligence.md)與電子的郵件</span><span class="sxs-lookup"><span data-stu-id="64996-110">Checking email messages for unauthorized spoofing with [spoof intelligence](learn-about-spoof-intelligence.md)</span></span>
    
- <span data-ttu-id="64996-111">偵測當某人嘗試模擬您的使用者與您的組織與[Office 365 的 ATP 反網路釣魚功能](atp-anti-phishing.md)的自訂網域</span><span class="sxs-lookup"><span data-stu-id="64996-111">Detecting when someone attempts to impersonate your users and your organization's custom domains with [ATP anti-phishing capabilities in Office 365](atp-anti-phishing.md)</span></span>
    
<span data-ttu-id="64996-p102">**透過 Office 365 ATP 保護會由貴組織的安全性小組的安全連結、 安全附件及反網路釣魚定義的原則**。務必可以定義原則，並定期檢閱並修改這些原則保持其最新並採取加到服務的新功能的優點。</span><span class="sxs-lookup"><span data-stu-id="64996-p102">**Protection through Office 365 ATP is determined by policies that your organization's security team defines for Safe Links, Safe Attachments, and Anti-Phishing**. It's important to define policies, and to periodically review and revise those policies to keep them up to date and to take advantages of new features that are added to the service.</span></span> 

<span data-ttu-id="64996-p103">[提供報告所](view-reports-for-atp.md)要顯示 ATP 組織的運作方式。這些報告也可顯示您您可能需要重新檢閱並更新您的原則的區域。而且，如果您有都會標記為惡意程式碼的不應該是相同網域或檔案您想要檢查的 Microsoft 的檔案，您可以[提交給 Microsoft 進行分析的檔案](#submit-a-suspicious-file-to-microsoft-for-analysis)。</span><span class="sxs-lookup"><span data-stu-id="64996-p103">[Reports are available](view-reports-for-atp.md) to show how ATP is working for your organization. These reports can also show you areas where you might need to review and update your policies. And, if you have files that are marked as malware that shouldn't be, or files you'd like Microsoft to examine, you can [submit a file to Microsoft for analysis](#submit-a-suspicious-file-to-microsoft-for-analysis).</span></span>

## <a name="new-features-are-continually-being-added-to-atp"></a><span data-ttu-id="64996-117">ATP 持續所加入的新功能</span><span class="sxs-lookup"><span data-stu-id="64996-117">New features are continually being added to ATP</span></span>

<span data-ttu-id="64996-p104">我們會繼續新增至 Office 365 的新功能並包含 ATP。以下是一些新功能，其中有些呼叫在檢閱和更新 ATP 原則的清單。若要深入了解傳入 ATP （或在一般的 Microsoft 365） 的新功能，請造訪[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)。</span><span class="sxs-lookup"><span data-stu-id="64996-p104">We are continuing to add new features to Office 365, and that includes ATP. Below is a list of several new features, some of which call for an ATP policy to be reviewed and updated. To learn more about new features coming to ATP (or Microsoft 365 in general), visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=O365).</span></span>


|<span data-ttu-id="64996-121">功能更新</span><span class="sxs-lookup"><span data-stu-id="64996-121">Feature updates</span></span>  |<span data-ttu-id="64996-122">動作項目</span><span class="sxs-lookup"><span data-stu-id="64996-122">Action items</span></span>  |
|---------|---------|
|<span data-ttu-id="64996-p105">開始在年 10 月 2018年及後續的幾個月內啟用，當使用者使用 Outlook 或 Outlook Web 應用程式 (OWA)、 ATP 安全連結轉譯原始 Url 不會修正 Url。（我們呼叫此原生連結轉譯）。</span><span class="sxs-lookup"><span data-stu-id="64996-p105">Beginning in October 2018 and rolling out over the next several months, when people are using Outlook or Outlook Web Application (OWA), ATP Safe Links renders original URLs, not rewritten URLs. (We call this native link rendering.)</span></span><br><span data-ttu-id="64996-125">當原生連結轉譯為可供您的組織時，這項功能將 Outlook 365 （按一下 [隨選） 和 OWA 中運作。</span><span class="sxs-lookup"><span data-stu-id="64996-125">When native link rendering is available for your organization, this feature will work in Outlook 365 (Click-to-Run) and OWA.</span></span>|<span data-ttu-id="64996-126">無</span><span class="sxs-lookup"><span data-stu-id="64996-126">None</span></span>         |
|<span data-ttu-id="64996-127">開始在 9 月 2018年、 [Office 365 ATP 警告頁面](atp-safe-links-warning-pages.md)] 功能的新的色彩配置、 詳細資訊及能夠繼續而不管網站授與警告和建議。</span><span class="sxs-lookup"><span data-stu-id="64996-127">Beginning in September 2018, [Office 365 ATP warning pages](atp-safe-links-warning-pages.md) feature a new color scheme, more details, and the ability to continue to a site despite given warnings and recommendations.</span></span> |<span data-ttu-id="64996-128">無</span><span class="sxs-lookup"><span data-stu-id="64996-128">None</span></span>         |
|<span data-ttu-id="64996-129">從開始 2018年第二個半，ATP 安全連結保護會延伸至套用至 Office Online （線上 Word、 Excel Online、 PowerPoint Online 和 OneNote Online） 和 Office 365 ProPlus mac 上的 Url</span><span class="sxs-lookup"><span data-stu-id="64996-129">Beginning in the second half of 2018, ATP Safe Links protection is extended to apply to URLs in Office Online (Word Online, Excel Online, PowerPoint Online, and OneNote Online) and Office 365 ProPlus on Mac.</span></span>   |[<span data-ttu-id="64996-130">檢閱並編輯 ATP 安全連結原則</span><span class="sxs-lookup"><span data-stu-id="64996-130">Review and edit your ATP Safe Links policies</span></span>](set-up-atp-safe-links-policies.md)  |
|<span data-ttu-id="64996-131">開始在落後 5 2018、 安全性[隔離](quarantine-email-messages.md)功能&amp;規範中心會被擴充至[ATP 的 SharePoint Online、 OneDrive for Business 和 Microsoft 小組](atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="64996-131">Beginning in late May 2018, [quarantine](quarantine-email-messages.md) capabilities in the Security &amp; Compliance Center are being extended to [ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span> |[<span data-ttu-id="64996-132">檢閱並編輯 ATP 安全附件原則</span><span class="sxs-lookup"><span data-stu-id="64996-132">Review and edit your ATP Safe Attachments policies</span></span>](set-up-atp-safe-attachments-policies.md) |
|<span data-ttu-id="64996-133">從開始年 3 月 2018年，ATP 安全連結保護會延伸至套用至組織內的人員之間所寄送的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="64996-133">Beginning in March 2018, ATP Safe Links protection is extended to apply to email sent between people within an organization.</span></span> |[<span data-ttu-id="64996-134">檢閱並編輯 ATP 安全連結原則</span><span class="sxs-lookup"><span data-stu-id="64996-134">Review and edit your ATP Safe Links policies</span></span>](set-up-atp-safe-links-policies.md) |
|<span data-ttu-id="64996-135">從開始落後年 10 月 2017年，ATP 安全連結保護會延伸至 Url 中電子郵件時的 Url 是以套用至 Office 365 ProPlus 的文件，例如 Word、 Excel、 PowerPoint 及 Visio 在 Windows，以及 Office iOS 及 Android 裝置上的應用程式。</span><span class="sxs-lookup"><span data-stu-id="64996-135">Beginning in late October 2017, ATP Safe Links protection is extended to apply to URLs in email as well as URLs in Office 365 ProPlus documents, such as Word, Excel, PowerPoint, and Visio on Windows, as well as Office apps on iOS and Android devices.</span></span>  |<span data-ttu-id="64996-136">請確定您使用[Office 的現代驗證](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)</span><span class="sxs-lookup"><span data-stu-id="64996-136">Make sure you're using [Modern Authentication for Office](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)</span></span> |
  
## <a name="get-office-365-atp"></a><span data-ttu-id="64996-137">取得 Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="64996-137">Get Office 365 ATP</span></span>

<span data-ttu-id="64996-p106">Office 365 ATP 隨附於訂閱，例如[Microsoft 365 企業版](https://www.microsoft.com/microsoft-365/enterprise/home)、 [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)、 Office 365 企業版 E5，以及 Office 365 教育版 A5。如果您的組織有不包含 Office 365 ATP Office 365 訂閱，可能可以做為附加元件購買 ATP。如需詳細資訊，請參閱[Office 365 進階威脅 Protection 服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="64996-p106">Office 365 ATP is included in subscriptions, such as [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, and Office 365 Education A5. If your organization has an Office 365 subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on. For more information, see [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> 

## <a name="define-policies-for-atp"></a><span data-ttu-id="64996-141">為 ATP 定義原則</span><span class="sxs-lookup"><span data-stu-id="64996-141">Define policies for ATP</span></span>

<span data-ttu-id="64996-142">若要定義 （或編輯） ATP 原則，您必須具有角色如下表所示的其中一個：</span><span class="sxs-lookup"><span data-stu-id="64996-142">To define (or edit) ATP policies, you must be assigned one of the roles described in the following table:</span></span>

|<span data-ttu-id="64996-143">角色</span><span class="sxs-lookup"><span data-stu-id="64996-143">Role</span></span>  |<span data-ttu-id="64996-144">Where/如何指派</span><span class="sxs-lookup"><span data-stu-id="64996-144">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="64996-145">Office 365 全域管理員</span><span class="sxs-lookup"><span data-stu-id="64996-145">Office 365 Global Administrator</span></span> |<span data-ttu-id="64996-p107">若要購買 Office 365 設定簽署者為預設的全域系統管理員。（請參閱若要深入了[解 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)）。</span><span class="sxs-lookup"><span data-stu-id="64996-p107">The person who signs up to buy Office 365 is a global admin by default. (See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="64996-148">安全性管理員</span><span class="sxs-lookup"><span data-stu-id="64996-148">Security Administrator</span></span> |<span data-ttu-id="64996-149">Azure Active Directory 系統管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="64996-149">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="64996-150">Exchange Online 組織管理</span><span class="sxs-lookup"><span data-stu-id="64996-150">Exchange Online Organization Management</span></span> |<span data-ttu-id="64996-151">Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="64996-151">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="64996-152">或</span><span class="sxs-lookup"><span data-stu-id="64996-152">or</span></span> <br>  <span data-ttu-id="64996-153">PowerShell cmdlet (請參閱[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span><span class="sxs-lookup"><span data-stu-id="64996-153">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span></span> |

> [!TIP]
> <span data-ttu-id="64996-154">若要深入了解角色和權限，請參閱[Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="64996-154">To learn more about roles and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="64996-155">有數種 ATP 原則來定義並定期檢閱。</span><span class="sxs-lookup"><span data-stu-id="64996-155">There are several kinds of ATP policies to define and periodically review.</span></span>

1. <span data-ttu-id="64996-156">**[設定 Office 365 中的 ATP 反網路釣魚原則](set-up-anti-phishing-policies.md)** 包括模擬型攻擊以防止攻擊者傳送電子郵件訊息的顯示可從信任的人員或網域。</span><span class="sxs-lookup"><span data-stu-id="64996-156">**[Set up ATP anti-phishing policies in Office 365](set-up-anti-phishing-policies.md)** including impersonation-based attacks to protect against attackers who send email messages that appear to be from trusted people or domains.</span></span> 

2. <span data-ttu-id="64996-157">**[設定 Office 365 中的 ATP 安全連結原則](set-up-atp-safe-links-policies.md)** 包括您的組織[自訂封鎖的 Url 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)和[自訂 「 未修正"Url 清單](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="64996-157">**[Set up ATP Safe Links policies in Office 365](set-up-atp-safe-links-policies.md)** including your organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md) and [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
    
3. <span data-ttu-id="64996-158">**[設定 Office 365 中的 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)** 選擇 [從[動態傳遞和預覽](dynamic-delivery-and-previewing.md)數個選項。</span><span class="sxs-lookup"><span data-stu-id="64996-158">**[Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md)** and choose from several options, such as [Dynamic Delivery and previewing](dynamic-delivery-and-previewing.md).</span></span>
  
## <a name="see-how-atp-is-working-by-viewing-reports"></a><span data-ttu-id="64996-159">請參閱 ATP 檢視報告的運作方式</span><span class="sxs-lookup"><span data-stu-id="64996-159">See how ATP is working by viewing reports</span></span>

<span data-ttu-id="64996-p108">ATP 原則已備妥之後，就有一個報表可用來顯示服務運作的方式。(在 Office 365 安全性 & 規範中心中，移至**報表** > **儀表板**。)</span><span class="sxs-lookup"><span data-stu-id="64996-p108">After your ATP policies are in place, reports are available to show how the service is working. (In the Office 365 Security & Compliance Center, go to **Reports** > **Dashboard**.)</span></span>

<span data-ttu-id="64996-162">[![安全性&amp;規範中心儀表板可協助您看到其用於進階威脅保護](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)](view-reports-for-atp.md)</span><span class="sxs-lookup"><span data-stu-id="64996-162">[![The Security &amp; Compliance Center dashboard can help you see where Advanced Threat Protection is working](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)](view-reports-for-atp.md)</span></span>
  
1. <span data-ttu-id="64996-163">為 Office 365 全域管理員、 安全性管理員或安全性讀者移至[https://protection.office.com](https://protection.office.com)並登入。</span><span class="sxs-lookup"><span data-stu-id="64996-163">As an Office 365 global administrator, security administrator, or security reader, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span>
    
2. <span data-ttu-id="64996-p109">移至 [**報表** > **儀表板**。（若要取得這些報告的說明，請參閱[進階威脅保護的檢視報告](view-reports-for-atp.md)）。</span><span class="sxs-lookup"><span data-stu-id="64996-p109">Go to **Reports** > **Dashboard**. (To get help with these reports, see [View reports for Advanced Threat Protection](view-reports-for-atp.md).)</span></span>
    
3. <span data-ttu-id="64996-p110">是否需要進行調整您的安全性原則。若要取得與此說明，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="64996-p110">If needed, make adjustments to your security policies. To get help with this, see the following resources:</span></span>
      - [<span data-ttu-id="64996-168">Office 365 中的 ATP 反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="64996-168">ATP anti-phishing policies in Office 365</span></span>](set-up-anti-phishing-policies.md)
      - [<span data-ttu-id="64996-169">Office 365 中的 ATP 安全連結原則</span><span class="sxs-lookup"><span data-stu-id="64996-169">ATP Safe Links policies in Office 365</span></span>](set-up-atp-safe-links-policies.md)
      - [<span data-ttu-id="64996-170">Office 365 中的 ATP 安全附件原則</span><span class="sxs-lookup"><span data-stu-id="64996-170">ATP Safe Attachments policies in Office 365</span></span>](set-up-atp-safe-attachments-policies.md)
    
    
## <a name="submit-a-suspicious-file-to-microsoft-for-analysis"></a><span data-ttu-id="64996-171">提交給 Microsoft 進行分析可疑的檔案</span><span class="sxs-lookup"><span data-stu-id="64996-171">Submit a suspicious file to Microsoft for analysis</span></span>

- <span data-ttu-id="64996-p111">如果您收到您懷疑可能是惡意程式碼檔案，您可以提交給 Microsoft 進行分析該檔案。請造訪[Windows 防禦者安全性智慧提交入口網站](https://go.microsoft.com/fwlink/?linkid=857185)。</span><span class="sxs-lookup"><span data-stu-id="64996-p111">If you get a file that you suspect could be malware, you can submit that file to Microsoft for analysis. Visit the [Windows Defender Security Intelligence submission portal](https://go.microsoft.com/fwlink/?linkid=857185).</span></span>

- <span data-ttu-id="64996-174">如果您要取得您想要提交給 Microsoft 進行分析的電子郵件訊息 （使用或不含附件），請使用[報告郵件增益集](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="64996-174">If you get an email message (with or without an attachment) that you'd like to submit to Microsoft for analysis, use the [Report Message add-in](enable-the-report-message-add-in.md).</span></span> 
  

