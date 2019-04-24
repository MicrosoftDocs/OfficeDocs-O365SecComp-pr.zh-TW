---
title: Office 365 的安全性最佳做法
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 5/22/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- BCS160
- MET150
ms.assetid: 9295e396-e53d-49b9-ae9b-0b5828cdedc3
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: 降低資料外洩或遭入侵的帳戶可能有遵循這些建議的最佳作法。
ms.openlocfilehash: bd4b911cd5972b7d6dc9b55c17e375d326b1d571
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32264635"
---
# <a name="security-best-practices-for-office-365"></a><span data-ttu-id="63077-103">Office 365 的安全性最佳做法</span><span class="sxs-lookup"><span data-stu-id="63077-103">Security best practices for Office 365</span></span>

<span data-ttu-id="63077-104">降低資料外洩或遭入侵的帳戶可能有遵循這些建議的最佳作法。</span><span class="sxs-lookup"><span data-stu-id="63077-104">Minimize the potential of a data breach or a compromised account by following these recommended best practices.</span></span>
  
<span data-ttu-id="63077-105">本文包含快速清單的最佳作法。</span><span class="sxs-lookup"><span data-stu-id="63077-105">This article contains a quick list of best practices.</span></span> <span data-ttu-id="63077-106">如需深入分析和安全性設定的詳細資訊，請參閱[Office 365 安全性藍圖： 前的 30 天、 前 90 天及過後](security-roadmap.md)。</span><span class="sxs-lookup"><span data-stu-id="63077-106">For more in-depth analysis and information on setting up security, see [Office 365 security roadmap: Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md).</span></span> <span data-ttu-id="63077-107">在該文中，您會發現資訊根據真實的攻擊的調查，我們上方的 Microsoft Office 365 cybersecurity 專家會提供指導評估風險及實作最重要的安全性、 規範和資訊的方式保護來保護您的 Office 365 租用戶的控制項。</span><span class="sxs-lookup"><span data-stu-id="63077-107">In that article, you'll find information based on investigations of real-world attacks, where our top Microsoft Office 365 cybersecurity experts provide coaching on how to assess risk and implement the most critical security, compliance, and information protection controls to protect your Office 365 tenant.</span></span> <span data-ttu-id="63077-108">您將了解如何設定優先順序威脅、 威脅轉化技術的策略，，然後採取實作功能和控制項的 [系統化的方法。</span><span class="sxs-lookup"><span data-stu-id="63077-108">You'll learn how to prioritize threats, translate threats into technical strategy, and then take a systematic approach to implementing features and controls.</span></span>
  
## <a name="use-office-365-secure-score"></a><span data-ttu-id="63077-109">使用 Office 365 安全分數</span><span class="sxs-lookup"><span data-stu-id="63077-109">Use Office 365 Secure Score</span></span>

<span data-ttu-id="63077-110">安全分數是種安全性分析工具，建議您能夠如何進一步降低風險。</span><span class="sxs-lookup"><span data-stu-id="63077-110">Secure Score is a security analytics tool that recommends what you can do to further reduce risk.</span></span> <span data-ttu-id="63077-111">安全分數會查看您的 Office 365 設定和活動，並比較它們，由 Microsoft 所建立的基線。</span><span class="sxs-lookup"><span data-stu-id="63077-111">Secure Score looks at your Office 365 settings and activities and compares them to a baseline established by Microsoft.</span></span> <span data-ttu-id="63077-112">您會看到如何對齊您使用最佳安全性作法為基礎的分數。</span><span class="sxs-lookup"><span data-stu-id="63077-112">You'll get a score based on how aligned you are with best security practices.</span></span> <span data-ttu-id="63077-113">如需如何取得安全分數，並使用它來增加您的 Office 365 組織的安全性的詳細資訊，請參閱[介紹 Office 365 安全分數](office-365-secure-score.md)。</span><span class="sxs-lookup"><span data-stu-id="63077-113">For more information about how to get Secure Score and use it to increase the security of your Office 365 organization, see [Introducing the Office 365 Secure Score](office-365-secure-score.md).</span></span>
  
<span data-ttu-id="63077-114">要嘗試安全分數嗎？</span><span class="sxs-lookup"><span data-stu-id="63077-114">Want to try out Secure Score?</span></span>
  
<span data-ttu-id="63077-115">使用已被指派 Office 365[關於 Office 365 系統管理員角色](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)的角色，[登入 Office 365](https://www.office.com/signin)工作或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="63077-115">Using a work or school account that has been assigned the Office 365 [About Office 365 admin roles](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) role, [sign in to Office 365](https://www.office.com/signin).</span></span>
  
<span data-ttu-id="63077-116">存取安全分數在[https://SecureScore.office.com](https://SecureScore.office.com)。</span><span class="sxs-lookup"><span data-stu-id="63077-116">Access Secure Score at [https://SecureScore.office.com](https://SecureScore.office.com).</span></span>
  
## <a name="use-multi-factor-authentication-mfa"></a><span data-ttu-id="63077-117">使用多重要素驗證 (MFA)</span><span class="sxs-lookup"><span data-stu-id="63077-117">Use multi-factor authentication (MFA)</span></span>

<span data-ttu-id="63077-118">MFA 會藉由要求使用者確認電話、 文字訊息或其智慧型手機上的應用程式通知正確輸入其密碼之後，將額外的保護層級新增至強式密碼策略。</span><span class="sxs-lookup"><span data-stu-id="63077-118">MFA adds an additional layer of protection to a strong password strategy by requiring users to acknowledge a phone call, text message, or an app notification on their smart phone after correctly entering their password.</span></span> <span data-ttu-id="63077-119">透過就地 MFA，Office 365 使用者帳戶仍受到防止未經授權存取即使危害使用者的密碼。</span><span class="sxs-lookup"><span data-stu-id="63077-119">With MFA in place, Office 365 user accounts are still protected against unauthorized access even if a user's password is compromised.</span></span> <span data-ttu-id="63077-120">因為未授與存取直到帳戶之後未滿足其他挑戰，帳戶會受到保護。</span><span class="sxs-lookup"><span data-stu-id="63077-120">Accounts are protected because access is not granted to an account until after the additional challenge has been satisfied.</span></span> <span data-ttu-id="63077-121">遭入侵或被竊密碼不足夠。</span><span class="sxs-lookup"><span data-stu-id="63077-121">A compromised or stolen password is not enough.</span></span>
  
- [<span data-ttu-id="63077-122">規劃 Office 365 部署多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="63077-122">Plan for multi-factor authentication for Office 365 Deployments</span></span>](https://support.office.com/article/043807b2-21db-4d5c-b430-c8a6dee0e6ba)

- [<span data-ttu-id="63077-123">設定 Office 365 使用者的多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="63077-123">Set up multi-factor authentication for Office 365 users</span></span>](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)

## <a name="use-office-365-cloud-app-security"></a><span data-ttu-id="63077-124">使用 Office 365 雲端 App 安全性</span><span class="sxs-lookup"><span data-stu-id="63077-124">Use Office 365 Cloud App Security</span></span>

<span data-ttu-id="63077-125">設定原則根據您追蹤異常的活動，並對它的業務需求。</span><span class="sxs-lookup"><span data-stu-id="63077-125">Set up policies based on your business needs to track anomalous activity and act on it.</span></span> <span data-ttu-id="63077-126">設定與 Office 365 雲端 App 安全性的提醒，以系統管理員可以檢閱不尋常或高風險使用者活動，例如下載大量的資料，多次失敗登入嘗試次數或從未知或危險的 IP 位址的登入。</span><span class="sxs-lookup"><span data-stu-id="63077-126">Set up alerts with Office 365 Cloud App Security so that admins can review unusual or risky user activity, such as downloading large amounts of data, multiple failed sign-in attempts, or sign-ins from an unknown or dangerous IP address.</span></span> <span data-ttu-id="63077-127">對使用 Office 365 企業版 E5 方案的組織而言，您可以開始使用 Office 365 雲端 App 安全性立即。</span><span class="sxs-lookup"><span data-stu-id="63077-127">For organizations with an Office 365 Enterprise E5 plan, you can start using Office 365 Cloud App Security right away.</span></span> <span data-ttu-id="63077-128">如果您有不同的企業版方案，您可以以附加元件形式購買 Office 365 雲端 App 安全性。</span><span class="sxs-lookup"><span data-stu-id="63077-128">If you have a different enterprise plan, you can purchase Office 365 Cloud App Security as an add-on.</span></span>
  
- [<span data-ttu-id="63077-129">O365 雲端 App 安全性概觀</span><span class="sxs-lookup"><span data-stu-id="63077-129">Overview of O365 Cloud App Security</span></span>](office-365-cas-overview.md)

- [<span data-ttu-id="63077-130">開啟 Office 365 雲端 App 安全性</span><span class="sxs-lookup"><span data-stu-id="63077-130">Turn on Office 365 Cloud App Security</span></span>](turn-on-office-365-cas.md)

## <a name="secure-mail-flow"></a><span data-ttu-id="63077-131">安全郵件流程</span><span class="sxs-lookup"><span data-stu-id="63077-131">Secure mail flow</span></span>

<span data-ttu-id="63077-132">實作豐富型功能設定 Exchange Online Protection 中的獲得更大的保證關於每個電子郵件，寄件者的身分識別和防護未知惡意程式碼、 病毒及透過電子郵件傳輸的惡意 Url。</span><span class="sxs-lookup"><span data-stu-id="63077-132">Implement the rich feature set in Exchange Online Protection and gain greater assurance about the identity of the sender of each email message, and protect against unknown malware, viruses, and malicious URLs transmitted through emails.</span></span>
  
- <span data-ttu-id="63077-133">設定您組織的[Office 365 電子郵件反垃圾郵件保護](anti-spam-protection.md)原則。</span><span class="sxs-lookup"><span data-stu-id="63077-133">Configure [Office 365 Email Anti-Spam Protection](anti-spam-protection.md) policies for your organization.</span></span>

- <span data-ttu-id="63077-134">了解，然後使用 [[安全附件和安全連結的進階的威脅防護](https://technet.microsoft.com/library/mt148491.aspx)。</span><span class="sxs-lookup"><span data-stu-id="63077-134">Learn about and then use [Advanced threat protection for safe attachments and safe links](https://technet.microsoft.com/library/mt148491.aspx).</span></span>

- <span data-ttu-id="63077-135">[新增至您的組織的反惡意程式碼保護](https://technet.microsoft.com/en-us/library/jj200669%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="63077-135">[Add anti-malware protection to your organization](https://technet.microsoft.com/en-us/library/jj200669%28v=exchg.150%29.aspx).</span></span>

- <span data-ttu-id="63077-136">了解並為您的使用者啟用[Office 365 中的電子郵件訊息中的安全提示](safety-tips-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="63077-136">Learn about and enable [Safety tips in email messages in Office 365](safety-tips-in-office-365.md) for your users.</span></span>

- <span data-ttu-id="63077-137">如果您正在使用您的組織在 Office 365 中的自訂網域，設定 SPF，DKIM，然後 DMARC 以驗證您的組織所傳送的郵件，並協助防止詐騙：</span><span class="sxs-lookup"><span data-stu-id="63077-137">If you're using a custom domain for your organization in Office 365, set up SPF, DKIM, and then DMARC to validate mail sent by your organization and to help prevent spoofing:</span></span>

  - <span data-ttu-id="63077-138">[設定 spf 以協助防止詐騙的 Office 365 中](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)。</span><span class="sxs-lookup"><span data-stu-id="63077-138">[Set up SPF in Office 365 to help prevent spoofing](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing).</span></span>

  - <span data-ttu-id="63077-139">[使用 DKIM 驗證從您在 Office 365 中的自訂網域傳送的外寄電子郵件](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)。</span><span class="sxs-lookup"><span data-stu-id="63077-139">[Use DKIM to validate outbound email sent from your custom domain in Office 365](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing).</span></span>

  - <span data-ttu-id="63077-140">[使用 DMARC 來驗證 Office 365 中的電子郵件](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="63077-140">[Use DMARC to validate email in Office 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).</span></span>

## <a name="enable-mailbox-audit-logging"></a><span data-ttu-id="63077-141">啟用信箱稽核記錄</span><span class="sxs-lookup"><span data-stu-id="63077-141">Enable mailbox audit logging</span></span>

<span data-ttu-id="63077-142">某些啟用稽核記錄會自動為您在 Office 365;不過，信箱稽核記錄預設無法開啟。</span><span class="sxs-lookup"><span data-stu-id="63077-142">Some audit logging is automatically enabled for you in Office 365; however, mailbox audit logging is not turned on by default.</span></span> <span data-ttu-id="63077-143">使用 Exchange Online PowerShell 開啟 Office 365 中的所有使用者信箱的稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="63077-143">You turn on audit logging for all user mailboxes in Office 365 by using Exchange Online PowerShell.</span></span> <span data-ttu-id="63077-144">如詳細資訊，請參閱 <<c0>啟用 Office 365 中的稽核的信箱。</span><span class="sxs-lookup"><span data-stu-id="63077-144">For information, see [Enable mailbox auditing in Office 365](https://go.microsoft.com/fwlink/p/?LinkID=626109).</span></span>
  
<span data-ttu-id="63077-145">稽核記錄您啟用後可以[搜尋稽核記錄以在 Office 365 安全性&amp;合規性中心](search-the-audit-log-in-security-and-compliance.md)以找出誰已登入您的使用者信箱，傳送訊息，以及其他信箱擁有者，委派的使用者所執行的活動或系統管理員。</span><span class="sxs-lookup"><span data-stu-id="63077-145">After you've enabled audit logging you can [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md) to find out who has logged into your user mailboxes, sent messages, and other activities performed by the mailbox owner, a delegated user, or an administrator.</span></span> <span data-ttu-id="63077-146">如需隨附於 Office 365 信箱活動的清單依預設稽核記錄，請參閱[Exchange 信箱活動](search-the-audit-log-in-security-and-compliance.md#exchange-mailbox-activities)。</span><span class="sxs-lookup"><span data-stu-id="63077-146">For a list of mailbox activities that are included in the Office 365 audit log by default, see [Exchange mailbox activities](search-the-audit-log-in-security-and-compliance.md#exchange-mailbox-activities).</span></span>
  
<span data-ttu-id="63077-147">如需其他動作的資訊您可以執行與稽核記錄檔，例如變更的項目儲存在稽核記錄檔中的時間量，請參閱[信箱稽核記錄中 Exchange 2016](https://technet.microsoft.com/en-us/library/ff459237%28v=exchg.160%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="63077-147">For information about other actions you can perform with the audit log, such as changing the amount of time to save entries in the audit log, see [Mailbox audit logging in Exchange 2016](https://technet.microsoft.com/en-us/library/ff459237%28v=exchg.160%29.aspx).</span></span>
  
## <a name="configure-data-loss-prevention-dlp"></a><span data-ttu-id="63077-148">設定資料外洩防護 (DLP)</span><span class="sxs-lookup"><span data-stu-id="63077-148">Configure Data Loss Prevention (DLP)</span></span>

<span data-ttu-id="63077-149">DLP 可讓您識別敏感資料，並建立原則，以協助防止使用者意外或故意共用資料。</span><span class="sxs-lookup"><span data-stu-id="63077-149">DLP allows you to identify sensitive data and create policies that help prevent your users from accidentally or intentionally sharing the data.</span></span> <span data-ttu-id="63077-150">DLP 的運作方式，讓您的使用者可以符合規範，而不中斷其工作流程包括 Exchange Online、 SharePoint Online 和 OneDrive 的 Office 365。</span><span class="sxs-lookup"><span data-stu-id="63077-150">DLP works across Office 365 including Exchange Online, SharePoint Online, and OneDrive so that your users can stay compliant without interrupting their workflow.</span></span> <span data-ttu-id="63077-151">如需詳細資訊，請參閱[資料外洩防護原則概觀](data-loss-prevention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="63077-151">For more information, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
## <a name="use-customer-lockbox"></a><span data-ttu-id="63077-152">使用客戶加密箱</span><span class="sxs-lookup"><span data-stu-id="63077-152">Use Customer Lockbox</span></span>

<span data-ttu-id="63077-153">身為 Office 365 系統管理員，您可以使用 Customer Lockbox 控制 Microsoft 技術支援工程師如何在協助工作階段期間存取您的資料。</span><span class="sxs-lookup"><span data-stu-id="63077-153">As an Office 365 admin, you can use Customer Lockbox to control how a Microsoft support engineer accesses your data during a help session.</span></span> <span data-ttu-id="63077-154">在工程師需要存取您的資料來排解及修正問題的情況下，Customer Lockbox 可讓您核准或拒絕存取要求。</span><span class="sxs-lookup"><span data-stu-id="63077-154">In cases where the engineer requires access to your data to troubleshoot and fix an issue, Customer Lockbox allows you to approve or reject the access request.</span></span> <span data-ttu-id="63077-155">如果您核准，工程師就可以存取的資料。</span><span class="sxs-lookup"><span data-stu-id="63077-155">If you approve it, the engineer can access the data.</span></span> <span data-ttu-id="63077-156">每個要求都有到期時間，問題一旦解決，就會關閉要求並撤銷存取權。</span><span class="sxs-lookup"><span data-stu-id="63077-156">Each request has an expiration time, and once the issue is resolved, the request is closed and access is revoked.</span></span> <span data-ttu-id="63077-157">Customer Lockbox 隨附於 Office 365 企業版 E5 方案，或您可以購買與任何其他 Office 365 企業版方案個別的訂閱。</span><span class="sxs-lookup"><span data-stu-id="63077-157">Customer Lockbox is included in the Office 365 Enterprise E5 plan, or you can purchase a separate subscription with any other Office 365 enterprise plan.</span></span> <span data-ttu-id="63077-158">如需資訊，請參閱 < <b0>Office 365 客戶加密箱要求</b0>。</span><span class="sxs-lookup"><span data-stu-id="63077-158">For information, see [Office 365 Customer Lockbox Requests](https://support.office.com/article/36f9cdd1-e64c-421b-a7e4-4a54d16440a2).</span></span>
  
## <a name="try-it-yourself"></a><span data-ttu-id="63077-159">自己試試看</span><span class="sxs-lookup"><span data-stu-id="63077-159">Try it yourself</span></span>
<span data-ttu-id="63077-160"><a name="SecureScore"> </a></span><span class="sxs-lookup"><span data-stu-id="63077-160"></span></span>

<span data-ttu-id="63077-161">請參閱這些安全性功能之前在生產環境中採用這些 Office 365 試用版訂閱中運作。</span><span class="sxs-lookup"><span data-stu-id="63077-161">See these security features working in an Office 365 trial subscription prior to adopting them in production.</span></span>
  
- [<span data-ttu-id="63077-162">建立 Office 365 試用訂閱</span><span class="sxs-lookup"><span data-stu-id="63077-162">Create an Office 365 trial subscription</span></span>](https://technet.microsoft.com/library/mt736406.aspx)

- [<span data-ttu-id="63077-163">設定及測試使用者帳戶的 MFA</span><span class="sxs-lookup"><span data-stu-id="63077-163">Configure and test MFA for a user account</span></span>](https://technet.microsoft.com/library/mt492459.aspx)

- [<span data-ttu-id="63077-164">設定並測試 Office 365 雲端 App 安全性來通知您的全域系統管理員活動</span><span class="sxs-lookup"><span data-stu-id="63077-164">Configure and test Office 365 Cloud App Security to notify you of global admin activity</span></span>](https://technet.microsoft.com/library/mt757250.aspx)

- [<span data-ttu-id="63077-165">設定及測試 ATP 可疑的電子郵件</span><span class="sxs-lookup"><span data-stu-id="63077-165">Configure and test ATP for suspicious email</span></span>](https://technet.microsoft.com/library/mt490479.aspx)

- <span data-ttu-id="63077-166">檢查每個以上步驟您試用版訂閱[Office 365 安全分數](https://securescore.office.com/)</span><span class="sxs-lookup"><span data-stu-id="63077-166">Check the [Office 365 Secure Score](https://securescore.office.com/) for your trial subscription for each of the above steps</span></span>