---
title: Office 365 進階威脅防護
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/08/2019
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
ms.collection:
- M365-security-compliance
description: Office 365 進階威脅保護包含詐騙智慧、 安全的連結、 安全的附件、 進階的反網路釣魚功能及威脅智慧。
ms.openlocfilehash: 4899073247f4b39e7cda39f8f35544c436c0b2d7
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995214"
---
# <a name="office-365-advanced-threat-protection"></a><span data-ttu-id="71595-103">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="71595-103">Office 365 Advanced Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71595-p101">本文適用於企業客戶的。如果您是家庭使用者尋找關於在 Outlook 中的安全連結的資訊，請參閱[進階 Outlook.com 安全性](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="71595-p101">This article is intended for business customers. If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

## <a name="overview-of-office-365-advanced-threat-protection"></a><span data-ttu-id="71595-106">Overview of Office 365 的進階的威脅保護</span><span class="sxs-lookup"><span data-stu-id="71595-106">Overview of Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="71595-107">Office 365 進階威脅保護 (ATP) 有幫助保護您的組織從惡意的攻擊：</span><span class="sxs-lookup"><span data-stu-id="71595-107">Office 365 Advanced Threat Protection (ATP) helps to protect your organization from malicious attacks by:</span></span>
  
- <span data-ttu-id="71595-108">掃描惡意程式碼[ATP 安全](atp-safe-attachments.md)附件的電子郵件的附件</span><span class="sxs-lookup"><span data-stu-id="71595-108">Scanning email attachments for malware with [ATP Safe Attachments](atp-safe-attachments.md)</span></span>
    
- <span data-ttu-id="71595-109">掃描的網頁位址 (Url) 中的電子郵件及 Office 文件的[ATP 安全連結](atp-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="71595-109">Scanning web addresses (URLs) in email messages and Office documents with [ATP Safe Links](atp-safe-links.md)</span></span>
    
- <span data-ttu-id="71595-110">識別和封鎖與[SharePoint、 OneDrive 及 Microsoft 小組 ATP](atp-for-spo-odb-and-teams.md)線上文件庫中的惡意檔案</span><span class="sxs-lookup"><span data-stu-id="71595-110">Identifying and blocking malicious files in online libraries with [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md)</span></span>
    
- <span data-ttu-id="71595-111">檢查未經授權詐騙[詐騙智慧](learn-about-spoof-intelligence.md)與電子的郵件</span><span class="sxs-lookup"><span data-stu-id="71595-111">Checking email messages for unauthorized spoofing with [spoof intelligence](learn-about-spoof-intelligence.md)</span></span>
    
- <span data-ttu-id="71595-112">偵測當某人嘗試模擬您的使用者與您的組織與[Office 365 的 ATP 反網路釣魚功能](atp-anti-phishing.md)的自訂網域</span><span class="sxs-lookup"><span data-stu-id="71595-112">Detecting when someone attempts to impersonate your users and your organization's custom domains with [ATP anti-phishing capabilities in Office 365](atp-anti-phishing.md)</span></span>
    
<span data-ttu-id="71595-p102">**透過 Office 365 ATP 保護會由貴組織的安全性小組的安全連結、 安全附件及反網路釣魚定義的原則**。務必可以定義原則，並定期檢閱並修改這些原則保持其最新並採取加到服務的新功能的優點。</span><span class="sxs-lookup"><span data-stu-id="71595-p102">**Protection through Office 365 ATP is determined by policies that your organization's security team defines for Safe Links, Safe Attachments, and Anti-Phishing**. It's important to define policies, and to periodically review and revise those policies to keep them up to date and to take advantages of new features that are added to the service.</span></span> 

<span data-ttu-id="71595-p103">[提供報告所](view-reports-for-atp.md)要顯示 ATP 組織的運作方式。這些報告也可顯示您您可能需要重新檢閱並更新您的原則的區域。而且，如果您有都會標記為惡意程式碼的不應該是相同網域或檔案您想要檢查的 Microsoft 的檔案，您可以[提交給 Microsoft 進行分析的檔案](#submit-a-suspicious-file-to-microsoft-for-analysis)。</span><span class="sxs-lookup"><span data-stu-id="71595-p103">[Reports are available](view-reports-for-atp.md) to show how ATP is working for your organization. These reports can also show you areas where you might need to review and update your policies. And, if you have files that are marked as malware that shouldn't be, or files you'd like Microsoft to examine, you can [submit a file to Microsoft for analysis](#submit-a-suspicious-file-to-microsoft-for-analysis).</span></span>

## <a name="new-features-are-continually-being-added-to-atp"></a><span data-ttu-id="71595-118">ATP 持續所加入的新功能</span><span class="sxs-lookup"><span data-stu-id="71595-118">New features are continually being added to ATP</span></span>

<span data-ttu-id="71595-p104">我們會繼續新增至 Office 365 的新功能並包含 ATP。以下是一些新功能，其中有些呼叫在檢閱和更新 ATP 原則的清單。若要深入了解傳入 ATP （或在一般的 Microsoft 365） 的新功能，請造訪[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)。</span><span class="sxs-lookup"><span data-stu-id="71595-p104">We are continuing to add new features to Office 365, and that includes ATP. Below is a list of several new features, some of which call for an ATP policy to be reviewed and updated. To learn more about new features coming to ATP (or Microsoft 365 in general), visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=O365).</span></span>


|<span data-ttu-id="71595-122">功能更新</span><span class="sxs-lookup"><span data-stu-id="71595-122">Feature updates</span></span>  |<span data-ttu-id="71595-123">動作項目</span><span class="sxs-lookup"><span data-stu-id="71595-123">Action items</span></span>  |
|---------|---------|
|<span data-ttu-id="71595-p105">開始在年 2 月 2019年和後續的幾個月內啟用、 威脅智慧功能會被新增至 ATP。此外，如果您的組織目前沒有 ATP，您必須考量，新的選項包括 ATP 計劃 1 和 ATP 計劃 2。若要深入了解，請參閱[Office 365 進階威脅保護計劃和價格](https://products.office.com/exchange/advance-threat-protection)與[Office 365 進階威脅 Protection 服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="71595-p105">Beginning in February 2019 and rolling out over the next several months, Threat Intelligence capabilities are being added to ATP. In addition, if your organization does not currently have ATP, you'll have new options to consider, including ATP Plan 1 and ATP Plan 2. To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> |<span data-ttu-id="71595-127">檢閱您的組織訂閱及如果需要[購買或編輯的附加元件](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on)。</span><span class="sxs-lookup"><span data-stu-id="71595-127">Review your organization's subscription, and if needed, [Buy or edit an add-on](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on).</span></span>  |
|<span data-ttu-id="71595-p106">開始在年 10 月 2018年及後續的幾個月內啟用，當使用者使用 Outlook 或 Outlook Web 應用程式 (OWA)、 ATP 安全連結轉譯原始 Url 不會修正 Url。（我們呼叫此原生連結轉譯）。</span><span class="sxs-lookup"><span data-stu-id="71595-p106">Beginning in October 2018 and rolling out over the next several months, when people are using Outlook or Outlook Web Application (OWA), ATP Safe Links renders original URLs, not rewritten URLs. (We call this native link rendering.)</span></span><br><span data-ttu-id="71595-130">當原生連結轉譯為可供您的組織時，這項功能將 Outlook 365 （按一下 [隨選） 和 OWA 中運作。</span><span class="sxs-lookup"><span data-stu-id="71595-130">When native link rendering is available for your organization, this feature will work in Outlook 365 (Click-to-Run) and OWA.</span></span>|<span data-ttu-id="71595-131">無</span><span class="sxs-lookup"><span data-stu-id="71595-131">None</span></span>         |
|<span data-ttu-id="71595-132">開始在 9 月 2018年、 [Office 365 ATP 警告頁面](atp-safe-links-warning-pages.md)] 功能的新的色彩配置、 詳細資訊及能夠繼續而不管網站授與警告和建議。</span><span class="sxs-lookup"><span data-stu-id="71595-132">Beginning in September 2018, [Office 365 ATP warning pages](atp-safe-links-warning-pages.md) feature a new color scheme, more details, and the ability to continue to a site despite given warnings and recommendations.</span></span> |<span data-ttu-id="71595-133">無</span><span class="sxs-lookup"><span data-stu-id="71595-133">None</span></span>         |
|<span data-ttu-id="71595-134">從開始 2018年第二個半，ATP 安全連結保護會延伸至套用至 Office Online （線上 Word、 Excel Online、 PowerPoint Online 和 OneNote Online） 和 Office 365 ProPlus mac 上的 Url</span><span class="sxs-lookup"><span data-stu-id="71595-134">Beginning in the second half of 2018, ATP Safe Links protection is extended to apply to URLs in Office Online (Word Online, Excel Online, PowerPoint Online, and OneNote Online) and Office 365 ProPlus on Mac.</span></span>   |[<span data-ttu-id="71595-135">檢閱並編輯 ATP 安全連結原則</span><span class="sxs-lookup"><span data-stu-id="71595-135">Review and edit your ATP Safe Links policies</span></span>](set-up-atp-safe-links-policies.md)  |
|<span data-ttu-id="71595-136">開始在落後 5 2018、 安全性[隔離](quarantine-email-messages.md)功能&amp;規範中心會被擴充至[ATP 的 SharePoint Online、 OneDrive for Business 和 Microsoft 小組](atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="71595-136">Beginning in late May 2018, [quarantine](quarantine-email-messages.md) capabilities in the Security &amp; Compliance Center are being extended to [ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span> |[<span data-ttu-id="71595-137">檢閱並編輯 ATP 安全附件原則</span><span class="sxs-lookup"><span data-stu-id="71595-137">Review and edit your ATP Safe Attachments policies</span></span>](set-up-atp-safe-attachments-policies.md) |
|<span data-ttu-id="71595-138">從開始年 3 月 2018年，ATP 安全連結保護會延伸至套用至組織內的人員之間所寄送的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="71595-138">Beginning in March 2018, ATP Safe Links protection is extended to apply to email sent between people within an organization.</span></span> |[<span data-ttu-id="71595-139">檢閱並編輯 ATP 安全連結原則</span><span class="sxs-lookup"><span data-stu-id="71595-139">Review and edit your ATP Safe Links policies</span></span>](set-up-atp-safe-links-policies.md) |
|<span data-ttu-id="71595-140">從開始落後年 10 月 2017年，ATP 安全連結保護會延伸至 Url 中電子郵件時的 Url 是以套用至 Office 365 ProPlus 的文件，例如 Word、 Excel、 PowerPoint 及 Visio 在 Windows，以及 Office iOS 及 Android 裝置上的應用程式。</span><span class="sxs-lookup"><span data-stu-id="71595-140">Beginning in late October 2017, ATP Safe Links protection is extended to apply to URLs in email as well as URLs in Office 365 ProPlus documents, such as Word, Excel, PowerPoint, and Visio on Windows, as well as Office apps on iOS and Android devices.</span></span>  |<span data-ttu-id="71595-141">請確定您使用[Office 的現代驗證](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)</span><span class="sxs-lookup"><span data-stu-id="71595-141">Make sure you're using [Modern Authentication for Office](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)</span></span> |


      
## <a name="get-office-365-atp"></a><span data-ttu-id="71595-142">取得 Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="71595-142">Get Office 365 ATP</span></span>

<span data-ttu-id="71595-p107">Office 365 ATP 隨附於訂閱，例如[Microsoft 365 企業版](https://www.microsoft.com/microsoft-365/enterprise/home)、 [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)、 Office 365 企業版 E5，以及 Office 365 教育版 A5。如果您的組織有不包含 Office 365 ATP Office 365 訂閱，可能可以做為附加元件購買 ATP。如需詳細資訊，請參閱[Office 365 進階威脅保護計劃和價格](https://products.office.com/exchange/advance-threat-protection)和[Office 365 進階威脅 Protection 服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="71595-p107">Office 365 ATP is included in subscriptions, such as [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, and Office 365 Education A5. If your organization has an Office 365 subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on. For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> 

## <a name="define-policies-for-atp"></a><span data-ttu-id="71595-146">為 ATP 定義原則</span><span class="sxs-lookup"><span data-stu-id="71595-146">Define policies for ATP</span></span>

<span data-ttu-id="71595-147">若要定義 （或編輯） ATP 原則，您必須具有角色如下表所示的其中一個：</span><span class="sxs-lookup"><span data-stu-id="71595-147">To define (or edit) ATP policies, you must be assigned one of the roles described in the following table:</span></span>

|<span data-ttu-id="71595-148">角色</span><span class="sxs-lookup"><span data-stu-id="71595-148">Role</span></span>  |<span data-ttu-id="71595-149">Where/如何指派</span><span class="sxs-lookup"><span data-stu-id="71595-149">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="71595-150">Office 365 全域管理員</span><span class="sxs-lookup"><span data-stu-id="71595-150">Office 365 Global Administrator</span></span> |<span data-ttu-id="71595-p108">若要購買 Office 365 設定簽署者為預設的全域系統管理員。（請參閱若要深入了[解 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)）。</span><span class="sxs-lookup"><span data-stu-id="71595-p108">The person who signs up to buy Office 365 is a global admin by default. (See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="71595-153">安全性管理員</span><span class="sxs-lookup"><span data-stu-id="71595-153">Security Administrator</span></span> |<span data-ttu-id="71595-154">Azure Active Directory 系統管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="71595-154">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="71595-155">Exchange Online 組織管理</span><span class="sxs-lookup"><span data-stu-id="71595-155">Exchange Online Organization Management</span></span> |<span data-ttu-id="71595-156">Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="71595-156">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="71595-157">或</span><span class="sxs-lookup"><span data-stu-id="71595-157">or</span></span> <br>  <span data-ttu-id="71595-158">PowerShell cmdlet (請參閱[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span><span class="sxs-lookup"><span data-stu-id="71595-158">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span></span> |

> [!TIP]
> <span data-ttu-id="71595-159">若要深入了解角色和權限，請參閱[Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="71595-159">To learn more about roles and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="71595-160">有數種 ATP 原則來定義並定期檢閱。</span><span class="sxs-lookup"><span data-stu-id="71595-160">There are several kinds of ATP policies to define and periodically review.</span></span>

1. <span data-ttu-id="71595-161">**[設定 Office 365 中的 ATP 反網路釣魚原則](set-up-anti-phishing-policies.md)** 包括模擬型攻擊以防止攻擊者傳送電子郵件訊息的顯示可從信任的人員或網域。</span><span class="sxs-lookup"><span data-stu-id="71595-161">**[Set up ATP anti-phishing policies in Office 365](set-up-anti-phishing-policies.md)** including impersonation-based attacks to protect against attackers who send email messages that appear to be from trusted people or domains.</span></span> 

2. <span data-ttu-id="71595-162">**[設定 Office 365 中的 ATP 安全連結原則](set-up-atp-safe-links-policies.md)** 包括您的組織[自訂封鎖的 Url 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)和[自訂 「 未修正"Url 清單](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="71595-162">**[Set up ATP Safe Links policies in Office 365](set-up-atp-safe-links-policies.md)** including your organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md) and [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
    
3. <span data-ttu-id="71595-163">**[設定 Office 365 中的 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)** 選擇 [從[動態傳遞和預覽](dynamic-delivery-and-previewing.md)數個選項。</span><span class="sxs-lookup"><span data-stu-id="71595-163">**[Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md)** and choose from several options, such as [Dynamic Delivery and previewing](dynamic-delivery-and-previewing.md).</span></span>
  
## <a name="see-how-atp-is-working-by-viewing-reports"></a><span data-ttu-id="71595-164">請參閱 ATP 檢視報告的運作方式</span><span class="sxs-lookup"><span data-stu-id="71595-164">See how ATP is working by viewing reports</span></span>

<span data-ttu-id="71595-p109">ATP 原則已備妥之後，就有一個報表可用來顯示服務運作的方式。(在 Office 365 安全性 & 規範中心中，移至**報表** > **儀表板**。)</span><span class="sxs-lookup"><span data-stu-id="71595-p109">After your ATP policies are in place, reports are available to show how the service is working. (In the Office 365 Security & Compliance Center, go to **Reports** > **Dashboard**.)</span></span>

<span data-ttu-id="71595-167">[![安全性&amp;規範中心儀表板可協助您看到其用於進階威脅保護](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)](view-reports-for-atp.md)</span><span class="sxs-lookup"><span data-stu-id="71595-167">[![The Security &amp; Compliance Center dashboard can help you see where Advanced Threat Protection is working](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)](view-reports-for-atp.md)</span></span>
  
1. <span data-ttu-id="71595-168">為 Office 365 全域管理員、 安全性系統管理員或安全性讀者，移至[https://protection.office.com](https://protection.office.com)並登入。</span><span class="sxs-lookup"><span data-stu-id="71595-168">As an Office 365 global administrator, a security administrator, or a security reader, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span>
    
2. <span data-ttu-id="71595-p110">移至 [**報表** > **儀表板**。（若要取得這些報告的說明，請參閱[進階威脅保護的檢視報告](view-reports-for-atp.md)）。</span><span class="sxs-lookup"><span data-stu-id="71595-p110">Go to **Reports** > **Dashboard**. (To get help with these reports, see [View reports for Advanced Threat Protection](view-reports-for-atp.md).)</span></span>
    
3. <span data-ttu-id="71595-p111">是否需要進行調整您的安全性原則。若要取得與此說明，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="71595-p111">If needed, make adjustments to your security policies. To get help with this, see the following resources:</span></span>
      - [<span data-ttu-id="71595-173">Office 365 中的 ATP 反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="71595-173">ATP anti-phishing policies in Office 365</span></span>](set-up-anti-phishing-policies.md)
      - [<span data-ttu-id="71595-174">Office 365 中的 ATP 安全連結原則</span><span class="sxs-lookup"><span data-stu-id="71595-174">ATP Safe Links policies in Office 365</span></span>](set-up-atp-safe-links-policies.md)
      - [<span data-ttu-id="71595-175">Office 365 中的 ATP 安全附件原則</span><span class="sxs-lookup"><span data-stu-id="71595-175">ATP Safe Attachments policies in Office 365</span></span>](set-up-atp-safe-attachments-policies.md)
    
    
## <a name="submit-a-suspicious-file-to-microsoft-for-analysis"></a><span data-ttu-id="71595-176">提交給 Microsoft 進行分析可疑的檔案</span><span class="sxs-lookup"><span data-stu-id="71595-176">Submit a suspicious file to Microsoft for analysis</span></span>

- <span data-ttu-id="71595-p112">如果您收到您懷疑可能是惡意程式碼檔案，您可以提交給 Microsoft 進行分析該檔案。請造訪[Windows 防禦者安全性智慧提交入口網站](https://go.microsoft.com/fwlink/?linkid=857185)。</span><span class="sxs-lookup"><span data-stu-id="71595-p112">If you get a file that you suspect could be malware, you can submit that file to Microsoft for analysis. Visit the [Windows Defender Security Intelligence submission portal](https://go.microsoft.com/fwlink/?linkid=857185).</span></span>

- <span data-ttu-id="71595-179">如果您要取得您想要提交給 Microsoft 進行分析的電子郵件訊息 （使用或不含附件），請使用[報告郵件增益集](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="71595-179">If you get an email message (with or without an attachment) that you'd like to submit to Microsoft for analysis, use the [Report Message add-in](enable-the-report-message-add-in.md).</span></span> 
  

