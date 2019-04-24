---
title: 調整 Office 365 中的反網路釣魚保護
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: 系統管理員可以了解如何識別通過，理由和方式了網路釣魚郵件的原因，以及如何在未來防止多個網路釣魚郵件提交的項目。
ms.openlocfilehash: c3025267ad8e01c18de618c85127dfe1077a16aa
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32264315"
---
# <a name="tune-anti-phishing-protection-in-office-365"></a><span data-ttu-id="4d004-103">調整 Office 365 中的反網路釣魚保護</span><span class="sxs-lookup"><span data-stu-id="4d004-103">Tune anti-phishing protection in Office 365</span></span>

<span data-ttu-id="4d004-104">雖然 Office 365 隨附各種依預設而啟用的反網路釣魚功能，可能是透過，仍然無法將某些網路釣魚郵件取得您的信箱。</span><span class="sxs-lookup"><span data-stu-id="4d004-104">Although Office 365 comes with a variety of anti-phishing features that are enabled by default, it's possible that some phishing messages could still get through to your mailboxes.</span></span> <span data-ttu-id="4d004-105">本主題說明可以怎麼做以探索通過，了網路釣魚郵件的原因以及可以怎麼做以調整反網路釣魚設定在您 Exchange Online 組織_不小心讓事情更糟_。</span><span class="sxs-lookup"><span data-stu-id="4d004-105">This topic describes what you can do to discover why a phishing message got through, and what you can do to adjust the anti-phishing settings in your Exchange Online organization _without accidentally making things worse_.</span></span>

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a><span data-ttu-id="4d004-106">第一件事第一個： 處理任何危害帳戶，並請確定您封鎖來自透過取得任何多個網路釣魚郵件</span><span class="sxs-lookup"><span data-stu-id="4d004-106">First things first: deal with any compromised accounts and make sure you block any more phishing messages from getting through</span></span>

<span data-ttu-id="4d004-107">如果收件者的帳戶遭到盜用了因為網路釣魚郵件，請依照下列[回應中 Office 365 遭入侵電子郵件帳戶](responding-to-a-compromised-email-account.md)中的步驟。</span><span class="sxs-lookup"><span data-stu-id="4d004-107">If a recipient's account was compromised as a result of the phishing message, follow the steps in [Responding to a compromised email account in Office 365](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="4d004-108">如果您的訂閱包括進階威脅防護 (ATP)，您可以使用[Office 365 威脅情報](office-365-ti.md)來識別其他也已收到網路釣魚郵件的使用者。</span><span class="sxs-lookup"><span data-stu-id="4d004-108">If your subscription includes Advanced Threat Protection (ATP), you can use [Office 365 Threat Intelligence](office-365-ti.md) to identify other users who also received the phishing message.</span></span> <span data-ttu-id="4d004-109">您可以封鎖網路釣魚郵件的其他選項：</span><span class="sxs-lookup"><span data-stu-id="4d004-109">You have additional options to block phishing messages:</span></span>

- [<span data-ttu-id="4d004-110">ATP 安全連結</span><span class="sxs-lookup"><span data-stu-id="4d004-110">ATP Safe Links</span></span>](set-up-atp-safe-links-policies.md)

- [<span data-ttu-id="4d004-111">ATP 安全附件</span><span class="sxs-lookup"><span data-stu-id="4d004-111">ATP Safe Attachments</span></span>](set-up-atp-safe-attachments-policies.md)

- <span data-ttu-id="4d004-112">[ATP 防網路釣魚原則](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="4d004-112">[ATP anti-phishing policies](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="4d004-113">附註您可以暫時增加中的 [**進階網路釣魚臨界值**從**標準\*\*\*\*加強**、**更積極**，或**最不積極**的原則。</span><span class="sxs-lookup"><span data-stu-id="4d004-113">Note that you can temporarily increase the **Advanced phishing thresholds** in the policy from **Standard** to **Aggressive**, **More aggressive**, or **Most aggressive**.</span></span>

<span data-ttu-id="4d004-114">確認這些 ATP 功能已開啟。</span><span class="sxs-lookup"><span data-stu-id="4d004-114">Verify these ATP features are turned on.</span></span>

## <a name="report-the-phishing-message-to-microsoft"></a><span data-ttu-id="4d004-115">向 Microsoft 回報網路釣魚郵件</span><span class="sxs-lookup"><span data-stu-id="4d004-115">Report the phishing message to Microsoft</span></span>

<span data-ttu-id="4d004-116">回報網路釣魚郵件是有幫助的調整用來保護 Office 365 中的所有客戶的篩選器。</span><span class="sxs-lookup"><span data-stu-id="4d004-116">Reporting phishing messages is helpful in tuning the filters that are used to protect all customers in Office 365.</span></span>

<span data-ttu-id="4d004-117">網路釣魚郵件_附件形式_傳送給**phish@office365.microsoft.com**新，否則空訊息中。</span><span class="sxs-lookup"><span data-stu-id="4d004-117">Send the phishing message _as an attachment_ in a new, otherwise empty message to **phish@office365.microsoft.com**.</span></span> <span data-ttu-id="4d004-118">不只是轉寄原始郵件。否則，我們無法檢查的原始郵件標頭。</span><span class="sxs-lookup"><span data-stu-id="4d004-118">Don't just forward the original message; otherwise, we can't examine the original message headers.</span></span> <span data-ttu-id="4d004-119">或者，您可以使用[報告訊息](https://docs.microsoft.com/office365/securitycompliance/enable-the-report-message-add-in)增益集在 Outlook 或網頁 （原先稱為 Outlook Web App）。</span><span class="sxs-lookup"><span data-stu-id="4d004-119">Or, you can use the [Report Message](https://docs.microsoft.com/office365/securitycompliance/enable-the-report-message-add-in) add-in in Outlook or Outlook on the web (formerly known as Outlook Web App).</span></span>

<span data-ttu-id="4d004-120">如需詳細資訊，請參閱[提交垃圾郵件、 非垃圾郵件和網路釣魚詐騙郵件提交給 Microsoft 進行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)。</span><span class="sxs-lookup"><span data-stu-id="4d004-120">For more information, see [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).</span></span>

## <a name="inspect-the-message-headers"></a><span data-ttu-id="4d004-121">檢查郵件標頭</span><span class="sxs-lookup"><span data-stu-id="4d004-121">Inspect the message headers</span></span>

<span data-ttu-id="4d004-122">您可以檢查以查看是否有任何項目，您可以執行您自己，防止多個網路釣魚郵件即將網路釣魚郵件的標頭。</span><span class="sxs-lookup"><span data-stu-id="4d004-122">You can examine the headers of the phishing message to see if there's anything that you can do yourself to prevent more phishing messages from coming through.</span></span> <span data-ttu-id="4d004-123">換句話說，檢查郵件標頭可協助您找出您的組織中負責允許中的網路釣魚郵件的任何設定。</span><span class="sxs-lookup"><span data-stu-id="4d004-123">In other words, examining the messages headers can help you identify any settings in your organization that were responsible for allowing the phishing messages in.</span></span>

<span data-ttu-id="4d004-124">具體而言，您應該檢查**X Forefront-反垃圾郵件報告**標頭欄位中的指示略過垃圾郵件或釣魚程式篩選的垃圾郵件篩選 Verdict (SFV) 值的郵件標頭。</span><span class="sxs-lookup"><span data-stu-id="4d004-124">Specifically, you should check the **X-Forefront-Antispam-Report** header field in the message headers for indications of skipped spam or phish filtering in the Spam Filtering Verdict (SFV) value.</span></span> <span data-ttu-id="4d004-125">略過篩選的郵件會有的項目`SCL:-1`，這表示您的設定值的其中一個允許此郵件通過藉由覆寫已由 「 服務垃圾郵件或釣魚程式結果。</span><span class="sxs-lookup"><span data-stu-id="4d004-125">Messages that skip filtering will have an entry of `SCL:-1`, which means one of your settings allowed this message through by overriding the spam or phish verdicts that were determined by the service.</span></span> <span data-ttu-id="4d004-126">如需如何取得郵件標頭和所有可用的反垃圾郵件和反釣魚程式郵件標頭的完整清單的詳細資訊，請參閱 <<c0>反垃圾郵件郵件標頭。</span><span class="sxs-lookup"><span data-stu-id="4d004-126">For more details on how to get message headers and the complete list of all available anti-spam and anti-phish message headers, see [Anti-spam message headers](https://docs.microsoft.com/office365/SecurityCompliance/anti-spam-message-headers).</span></span>

## <a name="best-practices-to-stay-protected"></a><span data-ttu-id="4d004-127">若要保持受保護的最佳作法</span><span class="sxs-lookup"><span data-stu-id="4d004-127">Best practices to stay protected</span></span>

- <span data-ttu-id="4d004-128">在 [每月付款，執行[Office 365 安全分數](office-365-secure-score.md)」 來評估您的 Office 365 組織的安全性設定。</span><span class="sxs-lookup"><span data-stu-id="4d004-128">On a monthly basis, run [Office 365 Secure Score](office-365-secure-score.md) to assess your Office 365 organization's security settings.</span></span>

- <span data-ttu-id="4d004-129">定期檢閱[詐騙智慧報表](learn-about-spoof-intelligence.md)及**隔離**可疑的郵件，而不是將其傳遞給使用者的垃圾郵件] 資料夾可[啟用反網路釣魚原則中的反詐騙保護](learn-about-spoof-intelligence.md#configuring-the-anti-spoofing-policy)。</span><span class="sxs-lookup"><span data-stu-id="4d004-129">Periodically review the [Spoof intelligence report](learn-about-spoof-intelligence.md) and [enable anti-spoofing protection in the anti-phishing policy](learn-about-spoof-intelligence.md#configuring-the-anti-spoofing-policy) to **quarantine** suspicious messages instead of delivering them to the user's Junk Email folder.</span></span>

- <span data-ttu-id="4d004-130">定期檢閱[威脅保護狀態報表](view-reports-for-atp.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="4d004-130">Periodically review the [Threat Protection Status report](view-reports-for-atp.md#threat-protection-status-report).</span></span>

- <span data-ttu-id="4d004-131">有些客戶不小心讓網路釣魚郵件通過，以允許寄件者或在反垃圾郵件原則的允許網域清單中放置他們自己的網域。</span><span class="sxs-lookup"><span data-stu-id="4d004-131">Some customers inadvertently allow phishing messages through by putting their own domains in the Allow sender or Allow domain list in anti-spam policies.</span></span> <span data-ttu-id="4d004-132">如果您選擇若要這麼做，您必須小心謹慎。</span><span class="sxs-lookup"><span data-stu-id="4d004-132">If you choose to do this, you must use extreme caution.</span></span> <span data-ttu-id="4d004-133">雖然此組態會讓某些合法郵件通過，它也會允許惡意通常會由 Office 365 垃圾郵件及/或釣魚程式篩選器封鎖的郵件。</span><span class="sxs-lookup"><span data-stu-id="4d004-133">Although this configuration will allow some legitimate messages through, it will also allow malicious messages that would normally be blocked by the Office 365 spam and/or phish filters.</span></span>

  <span data-ttu-id="4d004-134">處理合法郵件所封鎖的 Office 365 （誤判） 牽涉到您的網域中寄件者的最佳方式是完整且完整設定 SPF，DKIM、 DMARC 記錄，在 DNS 中的_所有_的 Office 365 中電子郵件網域：</span><span class="sxs-lookup"><span data-stu-id="4d004-134">The best way to deal with legitimate messages that are blocked by Office 365 (false positives) that involve senders in your domain is to fully and completely configure the SPF, DKIM, and DMARC records in DNS for _all_ of your email domains in Office 365:</span></span>

  - <span data-ttu-id="4d004-135">確認您的 SPF 記錄會識別您的網域中的寄件者的電子郵件的_所有_來源 （別忘了協力廠商服務 ！）。</span><span class="sxs-lookup"><span data-stu-id="4d004-135">Verify that your SPF record identifies _all_ sources of email for senders in your domain (don't forget third-party services!).</span></span>

  - <span data-ttu-id="4d004-136">使用完全未通過 (\-) 以確保未經授權寄件者所拒絕的電子郵件系統的設定若要這麼做。</span><span class="sxs-lookup"><span data-stu-id="4d004-136">Use hard fail (\-) to ensure that unauthorized senders are rejected by email systems that are configured to do so.</span></span> <span data-ttu-id="4d004-137">[詐騙智慧](https://docs.microsoft.com/office365/securitycompliance/learn-about-spoof-intelligence)可用來協助識別正在使用您的網域，以便您可以在您的 SPF 記錄中包含 [已授權的第三方寄件者的寄件者。</span><span class="sxs-lookup"><span data-stu-id="4d004-137">You can use [spoof intelligence](https://docs.microsoft.com/office365/securitycompliance/learn-about-spoof-intelligence) to help identify senders that are using your domain so that you can include authorized third-party senders in your SPF record.</span></span>

  <span data-ttu-id="4d004-138">設定指示，請參閱：</span><span class="sxs-lookup"><span data-stu-id="4d004-138">For configuration instructions, see:</span></span>
  
  - [<span data-ttu-id="4d004-139">在 Office 365 中設定 SPF 以協助防止詐騙</span><span class="sxs-lookup"><span data-stu-id="4d004-139">Set up SPF in Office 365 to help prevent spoofing</span></span>](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [<span data-ttu-id="4d004-140">使用 DKIM 驗證從您在 Office 365 中的自訂網域傳送的輸出電子郵件</span><span class="sxs-lookup"><span data-stu-id="4d004-140">Use DKIM to validate outbound email sent from your custom domain in Office 365</span></span>](use-dkim-to-validate-outbound-email.md)

  - [<span data-ttu-id="4d004-141">使用 DMARC 來驗證 Office 365 中的電子郵件</span><span class="sxs-lookup"><span data-stu-id="4d004-141">Use DMARC to validate email in Office 365</span></span>](use-dmarc-to-validate-email.md)

- <span data-ttu-id="4d004-142">可能的話，我們建議您網域傳送的電子郵件，直接向 Office 365。</span><span class="sxs-lookup"><span data-stu-id="4d004-142">Whenever possible, we recommend that you deliver email for your domain directly to Office 365.</span></span> <span data-ttu-id="4d004-143">換句話說，您的 Office 365 網域的 MX 記錄指向 Office 365。</span><span class="sxs-lookup"><span data-stu-id="4d004-143">In other words, point your Office 365 domain's MX record to Office 365.</span></span> <span data-ttu-id="4d004-144">Exchange Online Protection (EOP) 是可提供最佳保護您的雲端使用者，當他們的郵件都會直接傳送到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="4d004-144">Exchange Online Protection (EOP) is able to provide the best protection for your cloud users when their mail is delivered directly to Office 365.</span></span> <span data-ttu-id="4d004-145">如果您必須使用前面 EOP 的協力廠商電子郵件檢疫系統，請確定您遵循指引[以下](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud)。</span><span class="sxs-lookup"><span data-stu-id="4d004-145">If you must use a third-party email hygiene system in front of EOP, ensure you have followed the guidance [here](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud).</span></span>

- <span data-ttu-id="4d004-146">多重要素驗證 (MFA) 是以防止遭入侵的帳戶其實好方法。</span><span class="sxs-lookup"><span data-stu-id="4d004-146">Multi factor authentication (MFA) is a really good way to prevent compromised accounts.</span></span> <span data-ttu-id="4d004-147">您強烈應該考慮啟用 MFA 的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="4d004-147">You should strongly consider enabling MFA for all of your users.</span></span> <span data-ttu-id="4d004-148">階段式方法中，如啟動 （系統管理員、 主管等），您最機密的使用者啟用 MFA 的所有人啟用 MFA 之前。</span><span class="sxs-lookup"><span data-stu-id="4d004-148">For a phased approach, start by enabling MFA for your most sensitive users (admins, executives, etc.) before you enable MFA for everyone.</span></span> <span data-ttu-id="4d004-149">如需相關指示，請參閱 <<c0>設定多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="4d004-149">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

- <span data-ttu-id="4d004-150">攻擊者通常用轉寄規則，外部收件者來擷取資料。</span><span class="sxs-lookup"><span data-stu-id="4d004-150">Forwarding rules to external recipients are often used by attackers to extract data.</span></span> <span data-ttu-id="4d004-151">用於[Office 365 安全分數](office-365-secure-score.md)的**轉寄規則的檢閱信箱**資訊來找出並即使防止外部收件者轉寄規則。</span><span class="sxs-lookup"><span data-stu-id="4d004-151">Use the **Review mailbox forwarding rules** information in [Office 365 Secure Score](office-365-secure-score.md) to find and even prevent forwarding rules to external recipients.</span></span> <span data-ttu-id="4d004-152">如需詳細資訊，請參閱[減輕用戶端外部轉寄規則與安全分數](https://blogs.technet.microsoft.com/office365security/mitigating-client-external-forwarding-rules-with-secure-score/)。</span><span class="sxs-lookup"><span data-stu-id="4d004-152">For more information, see [Mitigating Client External Forwarding Rules with Secure Score](https://blogs.technet.microsoft.com/office365security/mitigating-client-external-forwarding-rules-with-secure-score/).</span></span>
