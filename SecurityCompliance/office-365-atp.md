---
title: Office 365 進階威脅防護
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/20/2019
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
description: Office 365 進階威脅保護包含安全附件、 安全的連結進階的反網路釣魚工具、 報告和威脅智慧功能。
ms.openlocfilehash: 5db4c5ff5ae7e536bba1f8730c724d151f367b54
ms.sourcegitcommit: 32cb896aef370764ec6e8f8278ebaf16f1c5ff37
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/20/2019
ms.locfileid: "30123924"
---
# <a name="office-365-advanced-threat-protection"></a><span data-ttu-id="60dd2-103">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="60dd2-103">Office 365 Advanced Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="60dd2-p101">本文適用於 Office 365 企業版客戶的。如果您使用 Outlook.com、 Office 365 首頁] 或 [Office 365 個人，而且您要尋找在 Outlook 中的安全連結的相關資訊，請參閱[進階 Outlook.com 安全性](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="60dd2-p101">This article is intended for Office 365 Enterprise customers. If you are using Outlook.com, Office 365 Home, or Office 365 Personal, and you're looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

## <a name="overview"></a><span data-ttu-id="60dd2-106">概觀</span><span class="sxs-lookup"><span data-stu-id="60dd2-106">Overview</span></span>

<span data-ttu-id="60dd2-p102">Office 365 進階威脅保護 (ATP) 保護惡意設電子郵件、 連結 (Url) 和共同作業工具所產生的威脅對貴組織。ATP 包括：</span><span class="sxs-lookup"><span data-stu-id="60dd2-p102">Office 365 Advanced Threat Protection (ATP) safeguards your organization against malicious threats posed by email messages, links (URLs) and collaboration tools. ATP includes:</span></span>

- <span data-ttu-id="60dd2-109">[威脅保護原則](#configure-atp-policies)： 定義威脅保護原則保護組織的適當層級的設定。</span><span class="sxs-lookup"><span data-stu-id="60dd2-109">[Threat protection policies](#configure-atp-policies): Define threat-protection policies to set the appropriate level of protection for your organization.</span></span> 

- <span data-ttu-id="60dd2-110">[報表](#view-atp-reports)： 檢視即時監視組織中的 ATP 效能報告。</span><span class="sxs-lookup"><span data-stu-id="60dd2-110">[Reports](#view-atp-reports): View real-time reports to monitor ATP performance in your organization.</span></span> 

- <span data-ttu-id="60dd2-111">[威脅智慧功能](#utilize-threat-intelligence-capabilities)： 運用調查、 了解、 模擬，並防止威脅的領導 edge 工具。</span><span class="sxs-lookup"><span data-stu-id="60dd2-111">[Threat intelligence capabilities](#utilize-threat-intelligence-capabilities): Utilize leading-edge tools to investigate, understand, simulate, and prevent threats.</span></span> 
 

## <a name="configure-atp-policies"></a><span data-ttu-id="60dd2-112">設定 ATP 原則</span><span class="sxs-lookup"><span data-stu-id="60dd2-112">Configure ATP policies</span></span>

<span data-ttu-id="60dd2-113">Office 365 ATP 提供許多工具來設定適當的層級的貴組織保護。</span><span class="sxs-lookup"><span data-stu-id="60dd2-113">Office 365 ATP provides numerous tools to set an appropriate level of protection for your organization.</span></span> 

<span data-ttu-id="60dd2-p103">貴組織的安全性小組必須定義原則的每個 ATP 工具在 Office 365 安全性 & 規範中心。移至 [ **Threat management** > **原則**來存取原則選項。</span><span class="sxs-lookup"><span data-stu-id="60dd2-p103">Your organization's security team must define policies for each ATP tool in the Office 365 Security & Compliance Center. Go to **Threat management** > **Policy** to access policy options.</span></span> 

<span data-ttu-id="60dd2-p104">針對您組織所定義的原則決定預先定義的威脅的行為與保護層級。原則選項是極具彈性。例如，貴組織的安全性小組可以設定微調威脅保護使用者、 組織、 收件者和網域層級。請務必定期檢閱您的原則因為新威脅與挑戰出現 [每日。</span><span class="sxs-lookup"><span data-stu-id="60dd2-p104">The policies that are defined for your organization determine the behavior and protection level for predefined threats. Policy options are extremely flexible. For example, your organization's security team can set fine-grained threat protection at the user, organization, recipient, and domain level. It is important to review your policies regularly because new threats and challenges emerge daily.</span></span>  

- <span data-ttu-id="60dd2-p105">[ATP 安全附件](atp-safe-attachments.md)： 提供零時差保護來保護您的訊息系統檢查惡意內容的電子郵件附件。並路由傳送所有郵件及附件不含病毒/惡意程式碼簽章特殊環境中，然後使用機器學習與分析的技術來偵測惡意的用途。如果不找到任何可疑的活動，就會將郵件轉接至信箱。若要深入了解，請參閱[Set up Office 365 ATP 安全附件的原則](set-up-atp-safe-attachments-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="60dd2-p105">[ATP Safe Attachments](atp-safe-attachments.md): Provides zero-day protection to safeguard your messaging system, by checking email attachments for malicious content. It routes all messages and attachments that do not have a virus/malware signature to a special environment, and then uses machine learning and analysis techniques to detect malicious intent. If no suspicious activity is found, the message is forwarded to the mailbox. To learn more, see [Set up Office 365 ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md).</span></span>

- <span data-ttu-id="60dd2-p106">[ATP 安全連結](atp-safe-links.md)： 提供之 Url 的時間按一下 [驗證電子郵件訊息和 Office 檔案中。保護會持續與套用您的通訊和 Office 環境。連結的每個 click 掃描： 安全的連結會保持存取和動態封鎖惡意的連結。若要深入了解，請參閱[Set up Office 365 ATP 安全連結原則](https://docs.microsoft.com/en-us/office365/securitycompliance/set-up-atp-safe-links-policies)。</span><span class="sxs-lookup"><span data-stu-id="60dd2-p106">[ATP Safe Links](atp-safe-links.md): Provides time-of-click verification of URLs in emails messages and Office files. Protection is ongoing and applies across your messaging and Office environment. Links are scanned for each click: safe links remain accessible and malicious links are dynamically blocked. To learn more, see [Set up Office 365 ATP Safe Links policies](https://docs.microsoft.com/en-us/office365/securitycompliance/set-up-atp-safe-links-policies).</span></span> 

- <span data-ttu-id="60dd2-p107">[SharePoint、 OneDrive 及 Microsoft 小組 ATP](atp-for-spo-odb-and-teams.md)： 當使用者共同作業及來識別共用檔案、 而封鎖惡意檔案小組網站及文件庫會保護您的組織。若要深入了解，請參閱[開啟 Office 365 ATP for SharePoint、 OneDrive 及 Microsoft 小組](turn-on-atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="60dd2-p107">[ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md): Protects your organization when users collaborate and share files, by identifying and blocking malicious files in team sites and document libraries. To learn more, see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span> 

- <span data-ttu-id="60dd2-p108">[ATP 反網路釣魚保護](atp-anti-phishing.md)： 偵測嘗試模擬使用者和自訂的網域。它會套用機器學習模型和進階的模擬偵測演算法來說明網路釣魚攻擊。若要深入了解，請參閱[Set up Office 365 ATP 反網路釣魚和反網路釣魚原則](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="60dd2-p108">[ATP anti-phishing protection](atp-anti-phishing.md): Detects attempts to impersonate your users and custom domains. It applies machine learning models and advanced impersonation-detection algorithms to avert phishing attacks. To learn more, see [Set up Office 365 ATP anti-phishing and anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

## <a name="view-atp-reports"></a><span data-ttu-id="60dd2-133">檢視 ATP 報告</span><span class="sxs-lookup"><span data-stu-id="60dd2-133">View ATP reports</span></span>

<span data-ttu-id="60dd2-p109">Office 365 ATP 包括進階[報表的儀表板](view-reports-for-atp.md)監視 ATP 效能。您可以在**報表 > 儀表板**存取它的安全性 & 規範中心。</span><span class="sxs-lookup"><span data-stu-id="60dd2-p109">Office 365 ATP includes an advanced [reporting dashboard](view-reports-for-atp.md) to monitor your ATP performance. You can access it at **Reports > Dashboard** in the Security & Compliance Center.</span></span> 

<span data-ttu-id="60dd2-p110">更新中的報告即時，提供最新的觀點。這些報告也會提供的建議及提醒您即將威脅。預先定義的報告包含[威脅保護狀態報表](view-reports-for-atp.md#threat-protection-status-report)、 [ATP 檔案類型的報告](view-reports-for-atp.md#atp-file-types-report)、 [ATP 郵件處理報告](view-reports-for-atp.md#atp-message-disposition-report)及其他。</span><span class="sxs-lookup"><span data-stu-id="60dd2-p110">Reports update in real-time, providing you with the latest insights. These reports also provide recommendations and alert you to imminent threats. Predefined reports include the [Threat Protection Status report](view-reports-for-atp.md#threat-protection-status-report), [ATP File Types report](view-reports-for-atp.md#atp-file-types-report), [ATP Message Disposition report](view-reports-for-atp.md#atp-message-disposition-report) and more.</span></span> 

## <a name="utilize-threat-intelligence-capabilities"></a><span data-ttu-id="60dd2-139">運用威脅智慧功能</span><span class="sxs-lookup"><span data-stu-id="60dd2-139">Utilize threat intelligence capabilities</span></span>

<span data-ttu-id="60dd2-140">Office 365 ATP 包含適合的類別[威脅智慧工具](office-365-ti.md)可讓您組織的安全性小組預期、 了解，並防止惡意的攻擊。</span><span class="sxs-lookup"><span data-stu-id="60dd2-140">Office 365 ATP includes best-of-class [threat intelligence tools](office-365-ti.md) that enable your organization's security team to anticipate, understand, and prevent malicious attacks.</span></span> 

- <span data-ttu-id="60dd2-p111">[威脅追蹤者](threat-trackers.md)提供最新智慧主流 cybersecurity 問題。例如，您可以檢視最新惡意程式碼的相關資訊及之前它會變成實際的潛在威脅對組織必須執行因應對策。可追蹤者包括[值得注意的追蹤者](threat-trackers.md#noteworthy-trackers)、 [[趨勢追蹤者](threat-trackers.md#trending-trackers)、[追蹤查詢](threat-trackers.md#tracked-queries)和[Saved 查詢](threat-trackers.md#saved-queries)。</span><span class="sxs-lookup"><span data-stu-id="60dd2-p111">[Threat trackers](threat-trackers.md) provide the latest intelligence on prevailing cybersecurity issues. For example, you can view information about the latest malware, and take countermeasures before it becomes an actual threat to your organization. Available trackers include [Noteworthy trackers](threat-trackers.md#noteworthy-trackers), [Trending trackers](threat-trackers.md#trending-trackers), [Tracked queries](threat-trackers.md#tracked-queries), and [Saved queries](threat-trackers.md#saved-queries).</span></span>

- <span data-ttu-id="60dd2-p112">[瀏覽器](use-explorer-in-security-and-compliance.md)（也稱為威脅 Explorer） 是可讓您識別和分析最近威脅即時報告。您可以設定的自訂週期] 會將資料顯示的瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="60dd2-p112">[Explorer](use-explorer-in-security-and-compliance.md) (also referred to as Threat Explorer) is a real-time report that allows you to identify and analyze recent threats. You can configure Explorer to show data for custom periods.</span></span>

- <span data-ttu-id="60dd2-p113">[攻擊模擬器](attack-simulator.md)可讓您識別 vulnerabilites 組織中執行真實感化的攻擊案例。模擬目前類型的攻擊可用，包括[顯示名稱矛網路釣魚攻擊](attack-simulator.md#display-name-spear-phishing-attack)、[密碼噴灑攻擊](attack-simulator.md#password-spray-attack)、[暴力密碼攻擊](attack-simulator.md#brute-force-password-attack)，等等。</span><span class="sxs-lookup"><span data-stu-id="60dd2-p113">[Attack Simulator](attack-simulator.md) allows you to run realistic attack scenarios in your organization to identify vulnerabilites. Simulations of current types of attacks are available, including a [display name spear-phishing attack](attack-simulator.md#display-name-spear-phishing-attack), a [password-spray attack](attack-simulator.md#password-spray-attack), a [brute-force password attack](attack-simulator.md#brute-force-password-attack), and more.</span></span>
    
## <a name="permissions-required-to-use-atp-features"></a><span data-ttu-id="60dd2-148">使用 ATP 功能所需的權限</span><span class="sxs-lookup"><span data-stu-id="60dd2-148">Permissions required to use ATP features</span></span>

<span data-ttu-id="60dd2-p114">若要存取的安全性 & 規範中心 ATP 功能，您必須指派適當的角色。下表包含一些範例：</span><span class="sxs-lookup"><span data-stu-id="60dd2-p114">To access ATP features in the Security & Compliance Center, you must be assigned an appropriate role. The following table includes some examples:</span></span>

|<span data-ttu-id="60dd2-151">角色或角色群組</span><span class="sxs-lookup"><span data-stu-id="60dd2-151">Role or role group</span></span>  |<span data-ttu-id="60dd2-152">若要深入了解的資源</span><span class="sxs-lookup"><span data-stu-id="60dd2-152">Resources to learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="60dd2-153">Office 365 全域管理員</span><span class="sxs-lookup"><span data-stu-id="60dd2-153">Office 365 Global Administrator</span></span> |[<span data-ttu-id="60dd2-154">關於 Office 365 系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="60dd2-154">About Office 365 admin roles</span></span>](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|<span data-ttu-id="60dd2-155">安全性管理員</span><span class="sxs-lookup"><span data-stu-id="60dd2-155">Security Administrator</span></span> |[<span data-ttu-id="60dd2-156">Azure Active Directory 中的系統管理員角色權限</span><span class="sxs-lookup"><span data-stu-id="60dd2-156">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="60dd2-157">Exchange Online 組織管理</span><span class="sxs-lookup"><span data-stu-id="60dd2-157">Exchange Online Organization Management</span></span> |[<span data-ttu-id="60dd2-158">Exchange Online 中的權限</span><span class="sxs-lookup"><span data-stu-id="60dd2-158">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/en-us/exchange/permissions-exo/permissions-exo) <br><span data-ttu-id="60dd2-159">和</span><span class="sxs-lookup"><span data-stu-id="60dd2-159">and</span></span><br> [<span data-ttu-id="60dd2-160">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="60dd2-160">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|

<span data-ttu-id="60dd2-161">另請參閱：</span><span class="sxs-lookup"><span data-stu-id="60dd2-161">See also:</span></span>
- [<span data-ttu-id="60dd2-162">在 Office 365 安全性 & 規範中心的權限</span><span class="sxs-lookup"><span data-stu-id="60dd2-162">Permissions in the Office 365 Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md) 

- [<span data-ttu-id="60dd2-163">讓使用者能夠存取 Office 365 安全性 & 規範中心</span><span class="sxs-lookup"><span data-stu-id="60dd2-163">Give users access to the Office 365 Security & Compliance Center</span></span>](grant-access-to-the-security-and-compliance-center.md)

## <a name="get-office-365-atp"></a><span data-ttu-id="60dd2-164">取得 Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="60dd2-164">Get Office 365 ATP</span></span>

<span data-ttu-id="60dd2-p115">Office 365 ATP 隨附於 Office 365 企業版 E5、 Office 365 教育版 A5、 及 Microsoft 365 Business。如果您的訂閱不包括 Office 365 ATP，則您可能可以購買 ATP 做為附加元件。若要深入了解，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="60dd2-p115">Office 365 ATP is included in Office 365 Enterprise E5, Office 365 Education A5, and Microsoft 365 Business. If your subscription does not include Office 365 ATP, you can potentially purchase ATP as an add-on. To learn more, see the following resources:</span></span>

- <span data-ttu-id="60dd2-168">請參閱[Office 365 進階威脅保護 (ATP) 可用性](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability)包括 ATP 計劃的訂閱的清單。</span><span class="sxs-lookup"><span data-stu-id="60dd2-168">See [Office 365 Advanced Threat Protection (ATP) availability](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability) for a list of subscriptions that include ATP plans.</span></span>

- <span data-ttu-id="60dd2-169">計劃 1 和 2 中所包含的功能清單中看到[不同進階威脅保護 (ATP) 計劃中可用的功能](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。</span><span class="sxs-lookup"><span data-stu-id="60dd2-169">See [Feature availability across Advanced Threat Protection (ATP) plans](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans) for a list of features included in Plan 1 and 2.</span></span>

- <span data-ttu-id="60dd2-170">請參閱比較計劃及購買 Office 365 ATP[取得 Office 365 進階威脅保護右邊](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content)。</span><span class="sxs-lookup"><span data-stu-id="60dd2-170">See [Get the right Office 365 Advanced Threat Protection](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content) to compare plans and purchase Office 365 ATP.</span></span>

## <a name="new-features-in-office-365-atp"></a><span data-ttu-id="60dd2-171">Office 365 ATP 中的新功能</span><span class="sxs-lookup"><span data-stu-id="60dd2-171">New features in Office 365 ATP</span></span>

<span data-ttu-id="60dd2-p116">新功能會需要經常新增至 Office 365 ATP。若要深入了解，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="60dd2-p116">New features are added to Office 365 ATP continually. To learn more, see the following resources:</span></span>

- <span data-ttu-id="60dd2-174">[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)提供開發及啟用新功能的清單。</span><span class="sxs-lookup"><span data-stu-id="60dd2-174">The [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) provides a list of new features in development and rolling out.</span></span>

- <span data-ttu-id="60dd2-175">[Office 365 進階威脅 Protection 服務說明](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)說明不同 ATP 計劃的功能與可用性。</span><span class="sxs-lookup"><span data-stu-id="60dd2-175">The [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp) describes features and availability across ATP plans.</span></span>
