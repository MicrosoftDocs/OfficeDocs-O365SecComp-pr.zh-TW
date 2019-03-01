---
title: 使用 DMARC 來驗證 Office 365 電子郵件
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.custom: TN2DMC
ms.assetid: 4a05898c-b8e4-4eab-bd70-ee912e349737
ms.collection:
- M365-security-compliance
description: 了解如何設定網域型郵件驗證，Reporting，and Conformance (DMARC)，以驗證從您的 Office 365 組織傳送的訊息。
ms.openlocfilehash: d224acaf6b1d53cdf9ababca87c5880a5499c613
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341574"
---
# <a name="use-dmarc-to-validate-email-in-office-365"></a>使用 DMARC 來驗證 Office 365 電子郵件

網域型郵件驗證、 報告和符合性聲明 ([DMARC](https://dmarc.org)) 適用於寄件者原則架構 (SPF) 和 DomainKeys Identified Mail (DKIM) 若要驗證郵件寄件者，並確保目的地電子郵件系統信任寄件者的郵件您的網域。實作 DMARC 搭配 SPF 和 DKIM 提供額外保護，防範詐騙和網路釣魚電子郵件。DMARC 可協助接收方郵件系統決定如何處理郵件會從您網域傳送未通過 SPF 或 DKIM 檢查。
  
## <a name="how-do-spf-and-dmarc-work-together-to-protect-email-in-office-365"></a>SPF 和 DMARC 如何共同運作以保護 Office 365 的電子郵件？
<a name="SPFandDMARC"> </a>

 電子郵件訊息可能包含多個建立者或寄件者地址。這些地址可用於不同用途。例如以下地址： 
  
- **「 郵件者] 地址**： 識別寄件者，並指定要傳送回傳通知訊息，例如未傳遞通知傳遞發生任何問題的位置。這會出現在電子郵件訊息的信封部分，而且通常不會顯示您的電子郵件應用程式。這有時稱為 5321.MailFrom 地址或反向路徑地址。
    
- **「 從 」 地址**： 您的郵件應用程式所顯示自地址的地址。此地址可識別電子郵件的作者。亦即人員或系統負責撰寫郵件的信箱。這有時稱為 5322.From 地址。
    
SPF 會針對指定的網域使用 DNS TXT 記錄來提供授權的傳送 IP 位址清單。一般而言，SPF 檢查只會針對 5321.MailFrom 地址執行。這表示當您單獨使用 SPF 時不會驗證 5322.From 地址。這會導致使用者收到的郵件可能通過 SPF 檢查，但卻具有冒名的 5322.From 寄件者地址。例如，請看以下 SMTP 文字記錄：
  
```
S: Helo woodgrovebank.com
S: Mail from: phish@phishing.contoso.com
S: Rcpt to: astobes@tailspintoys.com
S: data
S: To: "Andrew Stobes" <astobes@tailspintoys.com>
S: From: "Woodgrove Bank Security" <security@woodgrovebank.com>
S: Subject: Woodgrove Bank - Action required
S:
S: Greetings User,
S: 
S: We need to verify your banking details.
S: Please click the following link to verify that we have the right information for your account.
S: 
S: http://short.url/woodgrovebank/updateaccount/12-121.aspx
S:
S: Thank you,
S: Woodgrove Bank
S: .
```

在此文字記錄中，寄件者地址如下：
  
- 郵件寄件者地址 (5321.MailFrom): phish@phishing.contoso.com
    
- 寄件者地址 (5322.From): security@woodgrovebank.com
    
如果您設定了 SPF，接收方伺服器會針對郵件寄件者地址 phish@phishing.contoso.com 執行檢查。如果郵件是來自網域 phishing.contoso.com 的有效來源，則 SPF 檢查會通過。由於電子郵件用戶端只會顯示寄件者地址，使用者會看到此郵件是來自 security@woodgrovebank.com。如果單獨使用 SPF，則一律不會驗證 woodgrovebank.com 的有效性。
  
若您使用 DMARC，則接收方伺服器也會針對寄件者地址執行檢查。在上述案例中，如果有 woodgrovebank.com 的 DMARC TXT 記錄，則針對寄件者地址的檢查不會通過。
  
## <a name="what-is-a-dmarc-txt-record"></a>什麼是 DMARC TXT 記錄？
<a name="WhatisDMARC"> </a>

如同 SPF 的 DNS 記錄，DMARC 的記錄是 DNS 文字 (TXT) 記錄，其有助於防止詐騙和網路釣魚。您在 DNS 中發佈 DMARC TXT 記錄。DMARC TXT 記錄會根據宣稱為傳送網域的擁有者來驗證電子郵件作者的 IP 位址，藉以驗證電子郵件訊息的原始位置。 DMARC TXT 記錄可識別已獲授權的輸出電子郵件伺服器。目的地電子郵件系統接著會驗證收到的郵件是否來自於已獲授權的輸出電子郵件伺服器。
  
Microsoft 的 DMARC TXT 記錄看起來如下：
  
```
_dmarc.microsoft.com.   3600    IN      TXT     "v=DMARC1; p=none; pct=100; rua=mailto:d@rua.agari.com; ruf=mailto:d@ruf.agari.com; fo=1" 
```

Microsoft 會將其 DMARC 報告傳送給協力廠商 [Agari](https://agari.com)。 Agari 會收集並分析 DMARC 報告。
  
## <a name="implement-dmarc-for-inbound-mail"></a>為輸入郵件實作 DMARC
<a name="implementDMARCinbound"> </a>

您不需要為 Office 365 中收到的郵件執行任何動作來設定 DMARC。我們已經為您處理好所有事項。如果想了解未通過 DMARC 檢查的郵件將會如何，請參閱 [Office 365 如何處理未通過 DMARC 的輸入電子郵件](use-dmarc-to-validate-email.md#inbounddmarcfail)。
  
## <a name="implement-dmarc-for-outbound-mail-from-office-365"></a>為 Office 365 的輸出郵件實作 DMARC
<a name="implementDMARCoutbound"> </a>

如果您使用 Office 365 但未使用自訂網域，也就是您使用的是 onmicrosoft.com，則您不需要執行任何動作來為組織設定或實作 DMARC。已為您設定 SPF，且 Office 365 會自動產生輸出郵件的 DKIM 簽章。如需有關此簽章的詳細資訊，請參閱 [DKIM 與 Office 365 的預設行為](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)。
  
 如果您有自訂網域，或除了 Office 365 還有使用內部部署 Exchange 伺服器，您需要為輸出郵件手動實作 DMARC。為您的自訂網域實作 DMARC 包含下列步驟： 
  
- [步驟 1：找出您網域的郵件有效來源](use-dmarc-to-validate-email.md#IdentifyValidSources)
    
- [步驟 2：為 Office 365 中的網域設定 SPF](use-dmarc-to-validate-email.md#ConfigSPF)
    
- [步驟 3：為 Office 365 中的自訂網域設定 DKIM](use-dmarc-to-validate-email.md#ConfigDKIM)
    
- [步驟 4：為 Office 365 中的網域形成 DMARC TXT 記錄](use-dmarc-to-validate-email.md#CreateDMARCRecord)
    
### <a name="step-1-identify-valid-sources-of-mail-for-your-domain"></a>步驟 1：找出您網域的郵件有效來源
<a name="IdentifyValidSources"> </a>

如果您已設定 SPF，則已完成此步驟。不過，針對 DMARC 還有其他考量。在識別您網域的郵件來源時，有兩個必須回答的問題：
  
- 哪些 IP 位址會從我的網域傳送郵件？
    
- 針對由第三方代表我所傳送的郵件，5321.MailFrom 和 5322.From 網域相符嗎？
    
### <a name="step-2-set-up-spf-for-your-domain-in-office-365"></a>步驟 2：為 Office 365 中的網域設定 SPF
<a name="ConfigSPF"> </a>

現在您有所有有效寄件者的清單，您可以按照步驟到 [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。
  
例如，假設 contoso.com 從 Exchange Online 傳送郵件，其為 IP 位址為 192.168.0.1 的內部部署 Exchange 伺服器和 IP 位址為 192.168.100.100 的 Web 應用程式，則 SPF TXT 記錄呈現如下：
  
```
contoso.com  IN  TXT  " v=spf1 ip4:192.168.0.1 ip4:192.168.100.100 include:spf.protection.outlook.com -all"
```

最佳作法是，請確定 SPF TXT 記錄包括第三方寄件者。
  
### <a name="step-3-set-up-dkim-for-your-custom-domain-in-office-365"></a>步驟 3：為 Office 365 中的自訂網域設定 DKIM
<a name="ConfigDKIM"> </a>

設定好 SPF 後，您需要設定 DKIM。DKIM 可讓您在郵件標頭中將數位簽章新增到電子郵件訊息中。如果您未設定 DKIM 而讓 Office 365 為您的網域使用預設 DKIM 設定，DMARC 可能會失敗。這是因為預設 DKIM 設定會使用初始的 onmicrosoft.com 網域作為 5322.From 地址，而不是您的自訂網域。這會導致所有從您的網域傳送的電子郵件中 5321.MailFrom 與 5322.From 地址不相符。
  
如果有代表您傳送郵件的第三方寄件者，且其傳送的郵件中 5321.MailFrom 和 5322.From 地址不相符，則該電子郵件的 DMARC 將會失敗。若要避免此問題，您必須特別針對第三方寄件者設定網域 DKIM。這可讓 Office 365 驗證來自此第三方服務的電子郵件。 不過，這也讓 Yahoo、Gmail 和 Comcast 等信箱可以驗證由第三方傳送給他們的電子郵件，如同由您所傳送的電子郵件。這樣的好處在於，它能讓客戶對您的網域建立信任，無論客戶的信箱位於何處，同時 Office 365 不會因詐騙而將郵件標示為垃圾郵件，因為郵件已通過您網域的驗證檢查。
  
有關為網域設定 DKIM 的相關指示，包括如何為第三方寄件者設定 DKIM 以避免詐騙網域，請參閱 [使用 DKIM 驗證從您在 Office 365 中的自訂網域傳送的輸出電子郵件](use-dkim-to-validate-outbound-email.md)。
  
### <a name="step-4-form-the-dmarc-txt-record-for-your-domain-in-office-365"></a>步驟 4：為 Office 365 中的網域形成 DMARC TXT 記錄
<a name="CreateDMARCRecord"> </a>

雖然還有其他此處未提及的語法選項，以下是 Office 365 最常使用的選項。以下列格式為您的網域形成 DMARC TXT 記錄：
  
```
_dmarc.domain  TTL  IN  TXT  "v=DMARC1; pct=100; p=policy"
```

其中：
  
- *網域*是您想要保護的網域。根據預設，記錄會保護網域及所有子網域的郵件。例如，如果您指定\_dmarc.contoso.com，然後 DMARC 會保護的郵件網域和所有子網域，例如 housewares.contoso.com 或 plumbing.contoso.com。 
    
- *TTL*一律應該是相當於一小時。TTL，無論是小時 （1 小時），所使用的單位分鐘 （60 分鐘），或秒 （3600 秒），而有所不同您的網域註冊機構。 
    
- *pct = 100*指出這項規則應用於電子郵件的 100%。
    
- *原則*會指定要接收方伺服器遵循若 DMARC 失敗時哪些原則。您可以將原則設為 none、 隔離或拒絕。 
    
如需使用選項的相關資訊，請參閱[在 Office 365 中實作 DMARC 的最佳作法](use-dmarc-to-validate-email.md#DMARCbestpractices)以熟悉概念。
  
範例：
  
- 原則設為 [無]
  
    ```
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=none"
    ```

- 原則設為 [隔離]
  
    ```
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=quarantine"
    ```

- 原則設為 [拒絕]
  
    ```
    _dmarc.contoso.com  3600 IN  TXT  "v=DMARC1; p=reject"
    ```

一旦您已形成記錄，您需要在網域註冊機構中更新記錄。如需將 DMARC TXT 記錄新增至 Office 365 的 DNS 記錄之相關指示，請參閱[在管理 DNS 記錄時建立 Office 365 的 DNS 記錄](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23)。
  
## <a name="best-practices-for-implementing-dmarc-in-office-365"></a>在 Office 365 中實作 DMARC 的最佳作法
<a name="DMARCbestpractices"> </a>

您可以逐步實作 DMARC，而不影響郵件流程的其餘部分。建立和實作首度發行計劃，並依照下列步驟進行。首先在子網域執行這些步驟，然後是其他子網域，最後是組織中的頂層網域，再移至下一個步驟。
  
1. 監控實作 DMARC 的影響
    
    從簡易的監視模式記錄開始，其可用於子網域或要求 DMARC 接收器向您傳送使用該網域的郵件相關統計資料之網域。監視模式記錄是已將原則設為無 (p=無) 的 DMARC TXT 記錄。許多公司發佈 p=無的 DMARC TXT 記錄，是由於不確定發佈限制較嚴格的 DMARC 原則可能會損失多少電子郵件。 
    
    即使在您實作 SPF 或 DKIM 於郵件基礎結構之前，您即可這麼做。不過，如此將無法有效使用 DMARC 來隔離或拒絕郵件，直到您也同時實作 SPF 和 DKIM。當您引入 SPF 和 DKIM，透過 DMARC 所產生的報告會提供通過這些檢查的郵件以及未通過的數量和來源。您可以輕鬆查看有多少合法傳輸被其涵蓋或未涵蓋，並對問題進行疑難排解。您也會開始看到詐騙郵件送出的數量，及其從何處而來。
    
2. 要求外部郵件系統隔離未通過 DMARC 的郵件
    
    當您相信您所有或大部分的合法傳輸都受到 SPF 及 DKIM 的保護，且您了解實作 DMARC 的影響後，您可以實作隔離原則。隔離原則是已將原則設為隔離 (p=隔離) 的 DMARC TXT 記錄。執行此動作即是要求 DMARC 接收器將來自您網域中未通過 DMARC 的郵件放至本機相等於垃圾郵件的資料夾，而不是客戶的收件匣。
    
3. 要求外部郵件系統不接受未通過 DMARC 的郵件
    
    最後一個步驟是實作拒絕原則。拒絕原則是已將原則設為拒絕 (p=拒絕) 的 DMARC TXT 記錄。執行此動作即是要求 DMARC 接收器不接受未通過 DMARC 檢查的郵件。 
    
## <a name="how-office-365-handles-outbound-email-that-fails-dmarc"></a>Office 365 如何處理未通過 DMARC 的輸出電子郵件
<a name="outbounddmarcfail"> </a>

如果郵件是從 Office 365 部署的輸出，而未通過 DMARC，而且您已將原則設定為 p = 隔離或 p = 拒絕，[高風險傳遞集區的外寄郵件](high-risk-delivery-pool-for-outbound-messages.md)路由傳送郵件。沒有外寄電子郵件不可覆寫。
  
如果您發佈 DMARC 拒絕原則 (p=拒絕)，Office 365 中的其他客戶將無法詐騙您的網域，因為透過服務轉送輸出郵件時，郵件無法通過您網域的 SPF 或 DKIM。 不過，如果您確實發佈 DMARC 拒絕原則，但未透過 Office 365 驗證所有電子郵件，某些輸入電子郵件可能會被標示為垃圾郵件 (如上所述)，或如果您未發佈 SPF 並嘗試透過服務轉送輸出，則郵件會被拒絕。 例如，在形成 DMARC TXT 記錄時，如果您忘記包含某些代表您網域傳送郵件的伺服器及應用程式之 IP 位址，就會發生這種情況。
  
## <a name="how-office-365-handles-inbound-email-that-fails-dmarc"></a>Office 365 如何處理未通過 DMARC 的輸入電子郵件
<a name="inbounddmarcfail"> </a>

如果傳送伺服器的 DMARC 原則是 p=拒絕，則 EOP 會將郵件標示為垃圾郵件，而不是拒絕此郵件。換句話說，針對輸入電子郵件，Office 365 會以相同方式處理 p=拒絕和 p=隔離。
  
Office 365 如此設定，是因為某些合法的電子郵件可能無法通過 DMARC。比方說，如果郵件傳送至郵寄清單，然後再將郵件轉送至清單中的所有參與者，則此郵件可能無法通過 DMARC。如果 Office 365 拒絕這些郵件，可能會遺失合法的電子郵件，而且無法再擷取回來。 相反地，這些郵件仍無法通過 DMARC，但其會標示為垃圾郵件而不會被拒絕。如有需要，使用者仍可在收件匣中透過下列方法取得這些郵件：
  
- 使用者使用電子郵件用戶端來個別新增安全寄件者
    
- 系統管理員為允許這些特定寄件者的郵件的所有使用者建立 Exchange 郵件流程規則 （也稱為傳輸規則）。 
    
## <a name="troubleshooting-your-dmarc-implementation"></a>對 DMARC 實作進行疑難排解
<a name="dmarctroubleshoot"> </a>

如果您已設定網域的 MX 記錄，其中 EOP 並非第一個項目，則不會針對您的網域強制 DMARC 失敗。 
  
如果您是 Office 365 的客戶，且您網域的主要 MX 記錄並未指向 EOP，則您不會取得 DMARC 的效益。比方說，如果您將 MX 記錄指向內部部署郵件伺服器，並使用連接器將電子郵件路由傳送至 EOP，則不適用 DMARC。在此案例中，接收方網域是您其中一個公認的網域，但 EOP 不是主要的 MX。例如，假設 contoso.com 將其 MX 指向本身，並使用 EOP 作為次要 MX 記錄，contoso.com 的 MX 記錄會如下所示：
  
```
contoso.com     3600   IN  MX  0  mail.contoso.com
contoso.com     3600   IN  MX  10 contoso-com.mail.protection.outlook.com
```

由於它是主要的 MX，然後郵件會取得路由傳送到 EOP，所有或大部分的電子郵件首先會路由至 mail.contoso.com。在某些情況下，您可能甚至不完全將 EOP 列為 MX 記錄，並只要接上連接器來路由傳送您的電子郵件。EOP 可能沒有 DMARC 驗證，以完成的第一個項目。當我們無法確定所有在-內部部署/非-O365 伺服器將會執行操作 DMARC 檢查，它只可確保驗證。 DMARC 是合格客戶的網域 （非伺服器） 強制執行時設定的 DMARC TXT 記錄，但自行接收方伺服器真正執行強制執行。 如果您設定為接收伺服器的 EOP 時，EOP 會執行 DMARC 強制執行。
  
## <a name="for-more-information"></a>如需詳細資訊
<a name="sectionSection8"> </a>

需要 DMARC 的相關資訊？下列資源可以幫些忙。
  
- [反垃圾郵件訊息標頭](anti-spam-message-headers.md) 包含 Office 365 針對 DMARC 檢查所使用的語法及標頭欄位。 
    
- 從 M[3](https://www.m3aawg.org/activities/training/dmarc-training-series)AAWG (傳訊、惡意程式碼、行動裝置反不當使用工作群組) 參與 <sup>DMARC 訓練系列課程</sup>。
    
- 在 [dmarcian](https://space.dmarcian.com/deployment/) 使用檢查清單。
    
- 直接前往來源 [DMARC.org](https://dmarc.org)。
    
## <a name="see-also"></a>See also
<a name="sectionSection8"> </a>

[Office 365 如何使用寄件者原則架構 (SPF) 來防範詐騙](how-office-365-uses-spf-to-prevent-spoofing.md)
  
[在 Office 365 中設定 SPF 以協助防止詐騙](set-up-spf-in-office-365-to-help-prevent-spoofing.md)
  
[使用 DKIM 驗證從您在 Office 365 中的自訂網域傳送的輸出電子郵件](use-dkim-to-validate-outbound-email.md)

