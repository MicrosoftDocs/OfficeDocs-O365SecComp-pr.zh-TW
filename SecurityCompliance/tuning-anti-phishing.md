---
title: 調整 Office 365 中的反網路釣魚保護
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: 系統管理員可以了解如何識別通過，理由和方式了網路釣魚郵件的原因，以及如何在未來防止多個網路釣魚郵件提交的項目。
ms.openlocfilehash: b17cdc6ec6cfc07642a6a40657009b46b83f1559
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156345"
---
# <a name="tune-anti-phishing-protection-in-office-365"></a>調整 Office 365 中的反網路釣魚保護

雖然 Office 365 隨附各種依預設而啟用的反網路釣魚功能，可能是透過，仍然無法將某些網路釣魚郵件取得您的信箱。 本主題說明可以怎麼做以探索通過，了網路釣魚郵件的原因以及可以怎麼做以調整反網路釣魚設定在您 Exchange Online 組織_不小心讓事情更糟_。

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>第一件事第一個： 處理任何危害帳戶，並請確定您封鎖來自透過取得任何多個網路釣魚郵件

如果收件者的帳戶遭到盜用了因為網路釣魚郵件，請依照下列[回應中 Office 365 遭入侵電子郵件帳戶](responding-to-a-compromised-email-account.md)中的步驟。

如果您的訂閱包括進階威脅防護 (ATP)，您可以使用[Office 365 威脅情報](office-365-ti.md)來識別其他也已收到網路釣魚郵件的使用者。 您可以封鎖網路釣魚郵件的其他選項：

- [ATP 安全連結](set-up-atp-safe-links-policies.md)

- [ATP 安全附件](set-up-atp-safe-attachments-policies.md)

- [ATP 防網路釣魚原則](set-up-anti-phishing-policies.md)。 附註您可以暫時增加中的 [**進階網路釣魚臨界值**從**標準****加強**、**更積極**，或**最不積極**的原則。

確認這些 ATP 功能已開啟。

## <a name="report-the-phishing-message-to-microsoft"></a>向 Microsoft 回報網路釣魚郵件

回報網路釣魚郵件是有幫助的調整用來保護 Office 365 中的所有客戶的篩選器。

網路釣魚郵件_附件形式_傳送給**phish@office365.microsoft.com**新，否則空訊息中。 不只是轉寄原始郵件。否則，我們無法檢查的原始郵件標頭。 或者，您可以使用[報告訊息](https://docs.microsoft.com/office365/securitycompliance/enable-the-report-message-add-in)增益集在 Outlook 或網頁 （原先稱為 Outlook Web App）。

如需詳細資訊，請參閱[提交垃圾郵件、 非垃圾郵件和網路釣魚詐騙郵件提交給 Microsoft 進行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)。

## <a name="inspect-the-message-headers"></a>檢查郵件標頭

您可以檢查以查看是否有任何項目，您可以執行您自己，防止多個網路釣魚郵件即將網路釣魚郵件的標頭。 換句話說，檢查郵件標頭可協助您找出您的組織中負責允許中的網路釣魚郵件的任何設定。

具體而言，您應該檢查**X Forefront-反垃圾郵件報告**標頭欄位中的指示略過垃圾郵件或釣魚程式篩選的垃圾郵件篩選 Verdict (SFV) 值的郵件標頭。 略過篩選的郵件會有的項目`SCL:-1`，這表示您的設定值的其中一個允許此郵件通過藉由覆寫已由 「 服務垃圾郵件或釣魚程式結果。 如需如何取得郵件標頭和所有可用的反垃圾郵件和反釣魚程式郵件標頭的完整清單的詳細資訊，請參閱 <<c0>反垃圾郵件郵件標頭。

## <a name="best-practices-to-stay-protected"></a>若要保持受保護的最佳作法

- 在 [每月付款，執行[安全分數](microsoft-secure-score.md)」 來評估您的 Office 365 組織的安全性設定。

- 定期檢閱[詐騙智慧報表](learn-about-spoof-intelligence.md)及**隔離**可疑的郵件，而不是將其傳遞給使用者的垃圾郵件] 資料夾可[啟用反網路釣魚原則中的反詐騙保護](learn-about-spoof-intelligence.md#configuring-the-anti-spoofing-policy)。

- 定期檢閱[威脅保護狀態報表](view-reports-for-atp.md#threat-protection-status-report)。

- 有些客戶不小心讓網路釣魚郵件通過，以允許寄件者或在反垃圾郵件原則的允許網域清單中放置他們自己的網域。 如果您選擇若要這麼做，您必須小心謹慎。 雖然此組態會讓某些合法郵件通過，它也會允許惡意通常會由 Office 365 垃圾郵件及/或釣魚程式篩選器封鎖的郵件。

  處理合法郵件所封鎖的 Office 365 （誤判） 牽涉到您的網域中寄件者的最佳方式是完整且完整設定 SPF，DKIM、 DMARC 記錄，在 DNS 中的_所有_的 Office 365 中電子郵件網域：

  - 確認您的 SPF 記錄會識別您的網域中的寄件者的電子郵件的_所有_來源 （別忘了協力廠商服務 ！）。

  - 使用完全未通過 (\-) 以確保未經授權寄件者所拒絕的電子郵件系統的設定若要這麼做。 [詐騙智慧](https://docs.microsoft.com/office365/securitycompliance/learn-about-spoof-intelligence)可用來協助識別正在使用您的網域，以便您可以在您的 SPF 記錄中包含 [已授權的第三方寄件者的寄件者。

  設定指示，請參閱：
  
  - [在 Office 365 中設定 SPF 以協助防止詐騙](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [使用 DKIM 驗證從您在 Office 365 中的自訂網域傳送的輸出電子郵件](use-dkim-to-validate-outbound-email.md)

  - [使用 DMARC 來驗證 Office 365 中的電子郵件](use-dmarc-to-validate-email.md)

- 可能的話，我們建議您網域傳送的電子郵件，直接向 Office 365。 換句話說，您的 Office 365 網域的 MX 記錄指向 Office 365。 Exchange Online Protection (EOP) 是可提供最佳保護您的雲端使用者，當他們的郵件都會直接傳送到 Office 365。 如果您必須使用前面 EOP 的協力廠商電子郵件檢疫系統，請確定您遵循指引[以下](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud)。

- 多重要素驗證 (MFA) 是以防止遭入侵的帳戶其實好方法。 您強烈應該考慮啟用 MFA 的所有使用者。 階段式方法中，如啟動 （系統管理員、 主管等），您最機密的使用者啟用 MFA 的所有人啟用 MFA 之前。 如需相關指示，請參閱 <<c0>設定多重要素驗證。

- 攻擊者通常用轉寄規則，外部收件者來擷取資料。 使用**檢閱信箱轉寄規則**中的資訊[Microsoft 安全分數](microsoft-secure-score.md)若要尋找並即使防止外部收件者轉寄規則。 如需詳細資訊，請參閱[減輕用戶端外部轉寄規則與安全分數](https://blogs.technet.microsoft.com/office365security/mitigating-client-external-forwarding-rules-with-secure-score/)。
