---
title: Office 365 的安全性最佳做法
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/22/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MBS150
- BCS160
- MET150
ms.assetid: 9295e396-e53d-49b9-ae9b-0b5828cdedc3
description: 儘量減少資料破壞或洩漏的帳戶可能會遵循下列建議的最佳作法。
ms.openlocfilehash: 0d3dc30a9975f2ed8fe6d524b4fc67918b34e51d
ms.sourcegitcommit: 49b565f6a57febe53f331b2605d6a06d11e2d0be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2018
ms.locfileid: "25637997"
---
# <a name="security-best-practices-for-office-365"></a><span data-ttu-id="6506a-103">Office 365 的安全性最佳做法</span><span class="sxs-lookup"><span data-stu-id="6506a-103">Security best practices for Office 365</span></span>

<span data-ttu-id="6506a-104">儘量減少資料破壞或洩漏的帳戶可能會遵循下列建議的最佳作法。</span><span class="sxs-lookup"><span data-stu-id="6506a-104">Minimize the potential of a data breach or a compromised account by following these recommended best practices.</span></span>
  
<span data-ttu-id="6506a-p101">本文包含最佳作法快速的清單。如需深入的分析和安全性設定的詳細資訊，請參閱[Office 365 安全性藍圖： 最常用的優先順序的前 30 天 90 天和超過](security-roadmap.md)。在該文章，您會發現調查的真實世界攻擊為基礎的資訊我們上方的 Microsoft Office 365 cybersecurity 專家提供指導如何評估風險及實作最重要的安全性、 規範、 及資訊若要保護您的 Office 365 租用戶保護控制項。您將了解如何將優先順序威脅、 威脅翻譯成技術的策略，並實作功能與控制項採取適用於系統化方法。</span><span class="sxs-lookup"><span data-stu-id="6506a-p101">This article contains a quick list of best practices. For more in-depth analysis and information on setting up security, see [Office 365 security roadmap: Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md). In that article, you'll find information based on investigations of real-world attacks, where our top Microsoft Office 365 cybersecurity experts provide coaching on how to assess risk and implement the most critical security, compliance, and information protection controls to protect your Office 365 tenant. You'll learn how to prioritize threats, translate threats into technical strategy, and then take a systematic approach to implementing features and controls.</span></span>
  
## <a name="use-office-365-secure-score"></a><span data-ttu-id="6506a-109">使用 Office 365 安全分數</span><span class="sxs-lookup"><span data-stu-id="6506a-109">Use Office 365 Secure Score</span></span>

<span data-ttu-id="6506a-p102">安全的分數是建議可以怎麼做以進一步減少風險的安全性分析工具。安全的分數會查看您的 Office 365 設定和活動，並與比較 Microsoft 所建立的基準。您將取得如何對齊的最佳安全性作法為基礎的分數。如需如何取得安全分數並使用 Office 365 組織的安全性的詳細資訊，請參閱[簡介 Office 365 安全分數](office-365-secure-score.md)。</span><span class="sxs-lookup"><span data-stu-id="6506a-p102">Secure Score is a security analytics tool that recommends what you can do to further reduce risk. Secure Score looks at your Office 365 settings and activities and compares them to a baseline established by Microsoft. You'll get a score based on how aligned you are with best security practices. For more information about how to get Secure Score and use it to increase the security of your Office 365 organization, see [Introducing the Office 365 Secure Score](office-365-secure-score.md).</span></span>
  
<span data-ttu-id="6506a-114">想要試用安全分數嗎？</span><span class="sxs-lookup"><span data-stu-id="6506a-114">Want to try out Secure Score?</span></span>
  
<span data-ttu-id="6506a-115">使用已指派的 Office 365[有關 Office 365 系統管理員角色](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)的角色，[登入 Office 365](https://www.office.com/signin)工作或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="6506a-115">Using a work or school account that has been assigned the Office 365 [About Office 365 admin roles](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) role, [sign in to Office 365](https://www.office.com/signin).</span></span>
  
<span data-ttu-id="6506a-116">存取安全分數在[https://SecureScore.office.com](https://SecureScore.office.com)。</span><span class="sxs-lookup"><span data-stu-id="6506a-116">Access Secure Score at [https://SecureScore.office.com](https://SecureScore.office.com).</span></span>
  
## <a name="use-multi-factor-authentication-mfa"></a><span data-ttu-id="6506a-117">使用多重要素驗證 (MFA)</span><span class="sxs-lookup"><span data-stu-id="6506a-117">Use multi-factor authentication (MFA)</span></span>

<span data-ttu-id="6506a-p103">MFA 將額外的保護層級新增至強式密碼策略所需確認撥打的電話、 文字訊息或應用程式上的通知他們的智慧型手機之後正確地輸入其密碼的使用者。備妥 MFA，與 Office 365 使用者帳戶仍受到對抗未經授權存取即使危害使用者的密碼。帳戶會受到保護，因為沒有授與存取直到帳戶之後已滿足其他的挑戰。洩漏或竊密碼不足夠。</span><span class="sxs-lookup"><span data-stu-id="6506a-p103">MFA adds an additional layer of protection to a strong password strategy by requiring users to acknowledge a phone call, text message, or an app notification on their smart phone after correctly entering their password. With MFA in place, Office 365 user accounts are still protected against unauthorized access even if a user's password is compromised. Accounts are protected because access is not granted to an account until after the additional challenge has been satisfied. A compromised or stolen password is not enough.</span></span>
  
- [<span data-ttu-id="6506a-122">規劃 Office 365 部署的多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="6506a-122">Plan for multi-factor authentication for Office 365 Deployments</span></span>](https://support.office.com/article/043807b2-21db-4d5c-b430-c8a6dee0e6ba)
    
- [<span data-ttu-id="6506a-123">設定 Office 365 使用者的多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="6506a-123">Set up multi-factor authentication for Office 365 users</span></span>](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)
    
## <a name="use-office-365-cloud-app-security"></a><span data-ttu-id="6506a-124">使用 Office 365 雲端應用程式安全性</span><span class="sxs-lookup"><span data-stu-id="6506a-124">Use Office 365 Cloud App Security</span></span>

<span data-ttu-id="6506a-p104">設定您的業務需求，以追蹤異常活動及對其為基礎的原則。設定與 Office 365 雲端應用程式安全性提醒，讓系統管理員可以檢閱不尋常或 risky 使用者活動，例如下載大量的資料，多無法登入嘗試次數或從未知或危險的 IP 位址的登入。對於 Office 365 企業版 E5 計劃的組織而言，您可以啟動立即使用 Office 365 雲端應用程式安全性。如果您有不同的企業計劃時，您可以做為附加元件購買 Office 365 雲端應用程式安全性。</span><span class="sxs-lookup"><span data-stu-id="6506a-p104">Set up policies based on your business needs to track anomalous activity and act on it. Set up alerts with Office 365 Cloud App Security so that admins can review unusual or risky user activity, such as downloading large amounts of data, multiple failed sign-in attempts, or sign-ins from an unknown or dangerous IP address. For organizations with an Office 365 Enterprise E5 plan, you can start using Office 365 Cloud App Security right away. If you have a different enterprise plan, you can purchase Office 365 Cloud App Security as an add-on.</span></span>
  
- [<span data-ttu-id="6506a-129">O365 雲端應用程式安全性概觀</span><span class="sxs-lookup"><span data-stu-id="6506a-129">Overview of O365 Cloud App Security</span></span>](office-365-cas-overview.md)
    
- [<span data-ttu-id="6506a-130">開啟 Office 365 雲端 App 安全性</span><span class="sxs-lookup"><span data-stu-id="6506a-130">Turn on Office 365 Cloud App Security</span></span>](turn-on-office-365-cas.md)
    
## <a name="secure-mail-flow"></a><span data-ttu-id="6506a-131">安全郵件流程</span><span class="sxs-lookup"><span data-stu-id="6506a-131">Secure mail flow</span></span>

<span data-ttu-id="6506a-132">透過電子郵件傳輸的實作豐富型功能集 in Exchange Online Protection 和時會有關每個電子郵件之郵件的寄件者的身分識別的更保證並防止未知的惡意程式碼、 病毒、 及惡意 Url。</span><span class="sxs-lookup"><span data-stu-id="6506a-132">Implement the rich feature set in Exchange Online Protection and gain greater assurance about the identity of the sender of each email message, and protect against unknown malware, viruses, and malicious URLs transmitted through emails.</span></span>
  
- <span data-ttu-id="6506a-133">設定[Office 365 電子郵件反垃圾郵件保護](anti-spam-protection.md)您的組織的原則。</span><span class="sxs-lookup"><span data-stu-id="6506a-133">Configure [Office 365 Email Anti-Spam Protection](anti-spam-protection.md) policies for your organization.</span></span> 
    
- <span data-ttu-id="6506a-134">了解，然後使用 [[進階的威脅保護安全附件及安全的連結](https://technet.microsoft.com/library/mt148491.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6506a-134">Learn about and then use [Advanced threat protection for safe attachments and safe links](https://technet.microsoft.com/library/mt148491.aspx).</span></span>
    
- <span data-ttu-id="6506a-135">[新增您組織的反惡意程式碼保護](https://technet.microsoft.com/en-us/library/jj200669%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6506a-135">[Add anti-malware protection to your organization](https://technet.microsoft.com/en-us/library/jj200669%28v=exchg.150%29.aspx).</span></span>
    
- <span data-ttu-id="6506a-136">了解並為使用者啟用[Safety 秘訣 （英文） Office 365 中的電子郵件訊息中](safety-tips-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="6506a-136">Learn about and enable [Safety tips in email messages in Office 365](safety-tips-in-office-365.md) for your users.</span></span> 
    
- <span data-ttu-id="6506a-137">如果您組織在 Office 365 中使用自訂的網域，設定 SPF、 DKIM，然後 DMARC 來驗證您的組織所傳送的郵件，並協助防止詐騙：</span><span class="sxs-lookup"><span data-stu-id="6506a-137">If you're using a custom domain for your organization in Office 365, set up SPF, DKIM, and then DMARC to validate mail sent by your organization and to help prevent spoofing:</span></span>
    
  - <span data-ttu-id="6506a-138">[設定 SPF 避免詐騙的 Office 365 中](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)。</span><span class="sxs-lookup"><span data-stu-id="6506a-138">[Set up SPF in Office 365 to help prevent spoofing](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing).</span></span>
    
  - <span data-ttu-id="6506a-139">[使用 DKIM 驗證從您在 Office 365 中的自訂網域傳送的輸出電子郵件](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)。</span><span class="sxs-lookup"><span data-stu-id="6506a-139">[Use DKIM to validate outbound email sent from your custom domain in Office 365](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing).</span></span>
    
  - <span data-ttu-id="6506a-140">[使用 DMARC 來驗證 Office 365 中的電子郵件](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6506a-140">[Use DMARC to validate email in Office 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).</span></span>
    
## <a name="enable-mailbox-audit-logging"></a><span data-ttu-id="6506a-141">啟用信箱稽核記錄</span><span class="sxs-lookup"><span data-stu-id="6506a-141">Enable mailbox audit logging</span></span>

<span data-ttu-id="6506a-p105">某些啟用稽核記錄會自動為您在 Office 365;不過，信箱稽核記錄不會開啟預設。您使用 Exchange Online PowerShell 開啟的 Office 365 中的所有使用者信箱的稽核記錄功能。資訊，請參閱[啟用信箱稽核 Office 365 中](https://go.microsoft.com/fwlink/p/?LinkID=626109)。</span><span class="sxs-lookup"><span data-stu-id="6506a-p105">Some audit logging is automatically enabled for you in Office 365; however, mailbox audit logging is not turned on by default. You turn on audit logging for all user mailboxes in Office 365 by using Exchange Online PowerShell. For information, see [Enable mailbox auditing in Office 365](https://go.microsoft.com/fwlink/p/?LinkID=626109).</span></span>
  
<span data-ttu-id="6506a-p106">稽核記錄您是否已啟用之後可以[Office 365 安全性搜尋稽核記錄&amp;規範中心](search-the-audit-log-in-security-and-compliance.md)了解誰登入您的使用者信箱，傳送訊息及其他信箱擁有者、 委派的使用者所執行的活動或系統管理員。如需 Office 365 中隨附的信箱活動的清單依預設稽核記錄，請參閱[Exchange 信箱的活動](search-the-audit-log-in-security-and-compliance.md#exchange-mailbox-activities)。</span><span class="sxs-lookup"><span data-stu-id="6506a-p106">After you've enabled audit logging you can [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md) to find out who has logged into your user mailboxes, sent messages, and other activities performed by the mailbox owner, a delegated user, or an administrator. For a list of mailbox activities that are included in the Office 365 audit log by default, see [Exchange mailbox activities](search-the-audit-log-in-security-and-compliance.md#exchange-mailbox-activities).</span></span>
  
<span data-ttu-id="6506a-147">如需資訊其他動作您可使用稽核記錄，例如變更的項目儲存在稽核記錄檔的時間執行的[信箱稽核記錄中 Exchange 2016](https://technet.microsoft.com/en-us/library/ff459237%28v=exchg.160%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6506a-147">For information about other actions you can perform with the audit log, such as changing the amount of time to save entries in the audit log, see [Mailbox audit logging in Exchange 2016](https://technet.microsoft.com/en-us/library/ff459237%28v=exchg.160%29.aspx).</span></span>
  
## <a name="configure-data-loss-prevention-dlp"></a><span data-ttu-id="6506a-148">設定資料遺失防護 (DLP)</span><span class="sxs-lookup"><span data-stu-id="6506a-148">Configure Data Loss Prevention (DLP)</span></span>

<span data-ttu-id="6506a-p107">DLP 可讓您識別機密資料，並建立原則，協助使用者無法從有意或無意之間共用資料。DLP 的運作方式不同 Office 365 包括 Exchange Online、 SharePoint Online 和 OneDrive，讓使用者能停留相容而不會中斷其工作流程。如需詳細資訊，請參閱 ＜[資料外洩防護原則的概觀](data-loss-prevention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="6506a-p107">DLP allows you to identify sensitive data and create policies that help prevent your users from accidentally or intentionally sharing the data. DLP works across Office 365 including Exchange Online, SharePoint Online, and OneDrive so that your users can stay compliant without interrupting their workflow. For more information, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
## <a name="use-customer-lockbox"></a><span data-ttu-id="6506a-152">使用客戶 Lockbox</span><span class="sxs-lookup"><span data-stu-id="6506a-152">Use Customer Lockbox</span></span>

<span data-ttu-id="6506a-p108">為 Office 365 系統管理員，您可以使用客戶 Lockbox 控制 Microsoft 支援工程師說明工作階段期間所存取的資料。在其中工程師需要存取資料的疑難排解並修正問題的情況下，客戶 Lockbox 可讓您核准或拒絕存取要求。若加以核准、 工程師可以存取資料。每次要求有到期時間，並解決問題之後要求已關閉撤銷存取權。客戶 Lockbox 隨附的 Office 365 企業版 E5 計劃或可購買與任何其他 Office 365 企業版方案的不同訂閱。資訊，請參閱[Office 365 客戶 Lockbox 要求](https://support.office.com/article/36f9cdd1-e64c-421b-a7e4-4a54d16440a2)。</span><span class="sxs-lookup"><span data-stu-id="6506a-p108">As an Office 365 admin, you can use Customer Lockbox to control how a Microsoft support engineer accesses your data during a help session. In cases where the engineer requires access to your data to troubleshoot and fix an issue, Customer Lockbox allows you to approve or reject the access request. If you approve it, the engineer can access the data. Each request has an expiration time, and once the issue is resolved, the request is closed and access is revoked. Customer Lockbox is included in the Office 365 Enterprise E5 plan, or you can purchase a separate subscription with any other Office 365 enterprise plan. For information, see [Office 365 Customer Lockbox Requests](https://support.office.com/article/36f9cdd1-e64c-421b-a7e4-4a54d16440a2).</span></span>
  
## <a name="try-it-yourself"></a><span data-ttu-id="6506a-159">試試看</span><span class="sxs-lookup"><span data-stu-id="6506a-159">Try it yourself</span></span>
<span data-ttu-id="6506a-160"><a name="SecureScore"> </a></span><span class="sxs-lookup"><span data-stu-id="6506a-160"></span></span>

<span data-ttu-id="6506a-161">請參閱使用 Office 365 試用版訂閱之前在生產環境中採用這些這些安全性功能。</span><span class="sxs-lookup"><span data-stu-id="6506a-161">See these security features working in an Office 365 trial subscription prior to adopting them in production.</span></span>
  
- [<span data-ttu-id="6506a-162">建立 Office 365 試用版訂閱</span><span class="sxs-lookup"><span data-stu-id="6506a-162">Create an Office 365 trial subscription</span></span>](https://technet.microsoft.com/library/mt736406.aspx)
    
- [<span data-ttu-id="6506a-163">設定和測試 MFA 使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="6506a-163">Configure and test MFA for a user account</span></span>](https://technet.microsoft.com/library/mt492459.aspx)
    
- [<span data-ttu-id="6506a-164">設定及測試 Office 365 雲端應用程式安全性來通知您的全域管理員活動</span><span class="sxs-lookup"><span data-stu-id="6506a-164">Configure and test Office 365 Cloud App Security to notify you of global admin activity</span></span>](https://technet.microsoft.com/library/mt757250.aspx)
    
- [<span data-ttu-id="6506a-165">設定和測試 ATP 可疑的電子郵件</span><span class="sxs-lookup"><span data-stu-id="6506a-165">Configure and test ATP for suspicious email</span></span>](https://technet.microsoft.com/library/mt490479.aspx)
    
- <span data-ttu-id="6506a-166">檢查[Office 365 安全分數](https://securescore.office.com/)的每個以上步驟您試用訂閱</span><span class="sxs-lookup"><span data-stu-id="6506a-166">Check the [Office 365 Secure Score](https://securescore.office.com/) for your trial subscription for each of the above steps</span></span> 
    

