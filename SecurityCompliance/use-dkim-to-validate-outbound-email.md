---
title: 使用 DKIM 在 Office 365 中的自訂網域中的電子郵件
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.custom: TN2DMC
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
ms.collection:
- M365-security-compliance
description: 摘要： 本文將告訴您如何使用 DomainKeys Identified Mail (DKIM) 與 Office 365 來確保目的地電子郵件系統信任自您自訂網域傳送的郵件。
ms.openlocfilehash: 8792f41ade704c7742445646b3cb965561994d02
ms.sourcegitcommit: b688d67935edb036658bb5aa1671328498d5ddd3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2019
ms.locfileid: "30670678"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain-in-office-365"></a>使用 DKIM 驗證從您在 Office 365 中的自訂網域傳送的輸出電子郵件

 **摘要：** 本文將告訴您如何使用 DomainKeys Identified Mail (DKIM) 與 Office 365 來確保目的地電子郵件系統信任自您自訂網域傳送輸出郵件。 
  
您應該使用 DKIM 除了 SPF 和 DMARC，協助防範 spoofers 傳送看起來就來自您網域的郵件。 DKIM 可讓您在郵件標頭中將數位簽章新增到電子郵件訊息中。 聲音很複雜，但實際上不是。 當您設定 DKIM 時，您授權您的網域建立關聯，或登入，它使用密碼編譯驗證電子郵件訊息的名稱。 接收來自您網域的電子郵件的電子郵件系統可以使用此數位簽章，以協助您判斷所接收內送電子郵件是否合法。
  
基本上，您可以使用私人金鑰來加密您的網域外寄電子郵件中的標頭。 您可以發佈公開金鑰接收伺服器可以再使用解碼簽章的網域的 DNS 記錄。 他們使用公開金鑰，驗證郵件真的來自您然後不來自詐騙網域的人員。
  
Office 365 會自動設定 dkim 初始網域。 當您使用的服務，例如，contoso.onmicrosoft.com 註冊 Office 365 建立您的網域為初始網域。 您不需要執行任何動作來為初始網域設定 dkim。 如需網域的詳細資訊，請參閱[網域的常見問題集](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain)。
  
您可以選擇執行任何關於 DKIM 動作的自訂網域。 如果您未執行的自訂網域設定 dkim，Office 365 建立私密與公開金鑰組、 啟用 DKIM 簽章，並設定您的自訂網域的 Office 365 預設原則。 雖然這是對於大多數的 Office 365 客戶的足夠涵蓋範圍，您應該手動設定 DKIM 您自訂的網域，在下列情況：
  
- 您有 Office 365 中的多個自訂網域
    
- 您要太設定 DMARC （建議使用）
    
- 您想要控制您的私密金鑰
    
- 您想要自訂您的 CNAME 記錄
    
- 您想要設定 DKIM 機碼超出協力廠商網域，例如原始的電子郵件，如果您使用協力廠商大量郵件寄件者。
    
本文內容：
  
- [DKIM 優於單獨以防止 Office 365 中的惡意詐騙的 SPF 運作的方式](use-dkim-to-validate-outbound-email.md#HowDKIMWorks)
    
- [必須執行手動設定 dkim Office 365 中的項目](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)
    
- [若要為 Office 365 中的多個自訂網域設定 DKIM](use-dkim-to-validate-outbound-email.md#DKIMMultiDomain)
    
- [停用的 DKIM 簽章原則在 Office 365 中的自訂網域](use-dkim-to-validate-outbound-email.md#DisableDKIMSigningPolicy)
    
- [DKIM 與 Office 365 的預設行為](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)
    
- [使第三方服務可以傳送或詐騙，代表您的自訂網域的電子郵件設定 dkim](use-dkim-to-validate-outbound-email.md#SetUp3rdPartyspoof)
    
- [後續步驟： 為 Office 365 設定 dkim 之後](use-dkim-to-validate-outbound-email.md#DKIMNextSteps)
    
## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing-in-office-365"></a>DKIM 優於單獨以防止 Office 365 中的惡意詐騙的 SPF 運作的方式
<a name="HowDKIMWorks"> </a>

SPF 會將資訊新增到郵件信封，但實際上 DKIM 加密的郵件標頭中的簽章。 當您將郵件轉寄時，該訊息的信封部分可以是轉送伺服器離開附件。 數位簽章保持電子郵件訊息，因為它是電子郵件標頭的一部分，因為適用於 DKIM，即使當郵件已轉寄在下列範例所示。
  
![流程圖顯示當 SPF 檢查不通過時，轉送的訊息會傳遞 DKIM 驗證](media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)
  
在這個範例中，如果您僅有發佈的 SPF TXT 記錄為您的網域，收件者的郵件伺服器可能已標示為您的電子郵件為垃圾郵件，並產生，則為 false 正值的結果。 在此案例中額外的 DKIM 可降低，則為 false 正數垃圾郵件報告。 DKIM 依賴公開金鑰加密來驗證和不只是 IP 位址，因為 DKIM 會被視為更強形式的驗證 SPF 比。 我們建議使用 SPF 和 DKIM，以及您在部署中的 DMARC。
  
講述至今： DKIM 使用私人金鑰來加密的簽章插入郵件標頭。 簽署的網域或撥出的網域，會插入的值為**d =** 在標頭] 欄位。 驗證網域] 或 [收件者的網域，然後使用**d =** 從 DNS 查閱的公開金鑰，並驗證郵件] 欄位。 如果郵件驗證，會傳遞 DKIM 檢查。 
  
## <a name="what-you-need-to-do-to-manually-set-up-dkim-in-office-365"></a>必須執行手動設定 dkim Office 365 中的項目
<a name="SetUpDKIMO365"> </a>

若要設定 DKIM，您將完成下列步驟：
  
- [在 DNS 中發佈自訂網域的兩筆 CNAME 的記錄](use-dkim-to-validate-outbound-email.md#Publish2CNAME)
    
- [啟用 DKIM 簽章的 Office 365 中的自訂網域](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)
    
### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a>在 DNS 中發佈自訂網域的兩筆 CNAME 的記錄
<a name="Publish2CNAME"> </a>

針對您想要新增的 DKIM 簽章在 DNS 中每個網域，您需要發佈兩筆 CNAME 記錄。 CNAME 記錄是由 DNS 用來指定網域的正式名稱是另一個網域名稱的別名。 CNAME 記錄應建立公開提供的 DNS 伺服器，為您自訂的網域上。 在您的 DNS 中的 CNAME 記錄會指向已存在於記錄 DNS 中建立 Microsoft DNS 伺服器上的 Office 365。
  
 Office 365 會執行自動索引鍵的旋轉角度，使用您建立兩筆記錄。 如果您有佈建除了 Office 365 中的初始網域的自訂網域，您必須發佈其他每個網域的兩筆 CNAME 記錄。 因此，如果您有兩個網域，您必須發佈兩個額外 CNAME 記錄，依此類推。
  
使用下列格式的 CNAME 記錄。

> [!IMPORTANT]
> 如果您是下列其中一個我們 GCC 高的客戶，我們計算_domainGuid_不同 ！ 而不是查閱的 MX 記錄，來計算_domainGuid_您_initialDomain_ ，改為我們加以計算直接從自訂的網域。 例如，如果您自訂的網域是 「 contoso.com 」 您 domainGuid 會變成 「 contoso com 」，任何期間取代連字號。 因此，不論何種 MX 記錄您 initialDomain 指向，您將一律使用上述方法來計算筆 CNAME 記錄中使用 domainGuid。

  
```
Host name:          selector1._domainkey
Points to address or value: selector1-<domainGUID>._domainkey.<initialDomain> 
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: selector2-<domainGUID>._domainkey.<initialDomain> 
TTL:                3600
```

其中：
  
- 針對 Office 365 中，選取器一定會 「 selector1 」 或 「 selector2 」。 
    
- _domainGUID_是_domainGUID_自訂 MX 記錄的自訂網域出現之前 mail.protection.outlook.com 中相同。 例如，在網域 contoso.com 的下列 MX 記錄， _domainGUID_是 contoso com: 
    
    ```
    contoso.com.  3600  IN  MX   5 contoso-com.mail.protection.outlook.com
    ```

- _initialDomain_是您的 Office 365 註冊時所用的網域。 初始網域一律以.onmicrosoft.com 如需決定初始網域資訊，請參閱[網域的常見問題集](https://support.office.com/article/1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain)。
    
例如，如果您有 cohovineyardandwinery.onmicrosoft.com，初始網域和兩個自訂網域 cohovineyard.com cohowinery.com，您必須設定其他每個網域，總共四筆 CNAME 記錄的兩筆 CNAME 記錄。
  
```
Host name:          selector1._domainkey
Points to address or value: **selector1-cohovineyard-com**._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: **selector2-cohovineyard-com**._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:          selector1._domainkey
Points to address or value: **selector1-cohowinery-com**._domainkey.cohovineyardandwinery.onmicrosoft.com 
TTL:                3600
 
Host name:          selector2._domainkey
Points to address or value: **selector2-cohowinery-com**._domainkey.cohovineyardandwinery.onmicrosoft.com 
TTL:                3600
```

### <a name="enable-dkim-signing-for-your-custom-domain-in-office-365"></a>啟用 DKIM 簽章的 Office 365 中的自訂網域
<a name="EnableDKIMinO365"> </a>

一旦您已經在 DNS 中發佈的 CNAME 記錄，您準備好要啟用 DKIM 簽署透過 Office 365。 您可以透過 Microsoft 365 系統管理中心或使用 PowerShell 來執行這項操作。
  
#### <a name="to-enable-dkim-signing-for-your-custom-domain-through-the-admin-center"></a>若要啟用 DKIM 簽章的自訂網域透過系統管理中心

1. 使用您的 公司或學校帳戶[登入 Office 365](https://support.office.microsoft.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4)。 
    
2. 選取左上角的應用程式啟動器圖示，然後選擇 [管理員]****。
    
3. 左下導覽中，依序展開 [**系統管理員**，並選擇 [ **Exchange**]。
    
4. 移至 [**保護** \> **dkim**。
    
5. 選取您要啟用 DKIM，然後為**此網域的 DKIM 簽章簽署郵件**，選擇 [**啟用**的網域。 針對每個自訂網域重複此步驟。
    
#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a>若要啟用 DKIM 簽章的自訂網域，藉由使用 PowerShell

1. [連線至 Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289.aspx) (機器翻譯)。
    
2. 執行下列命令：
    
    ```
    New-DkimSigningConfig -DomainName <domain> -Enabled $true
    ```

   其中_網域_是您想要啟用 DKIM 簽章的自訂網域名稱。 
    
   例如，針對 contoso.com 網域：
    
    ```
    New-DkimSigningConfig -DomainName contoso.com -Enabled $true
    ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-office-365"></a>若要確認的 DKIM 簽章已正確設定為 Office 365

請稍候幾分鐘時間才能遵循這些步驟來確認您已正確設定 DKIM。 這可讓散佈到整個網路網域的 DKIM 資訊的時間。
  
- 從傳送訊息內啟用 Office 365 DKIM 的網域帳戶到另一個電子郵件帳戶，例如 outlook.com 或 Hotmail.com。
    
- 請勿 aol.com 帳戶為了進行測試。 AOL 可能會略過 DKIM 檢查如果 SPF 檢查會通過。 這將會進行造成您的測試。
    
- 開啟的郵件，然後查看 [標頭。 檢視郵件的標頭指示會視您的郵件用戶端而異。 如需在 Outlook 中檢視郵件標頭指示，請參閱 <<c0>檢視電子郵件訊息標頭。

  DKIM 簽章的郵件會包含主機名稱與網域您定義當您發佈的 CNAME 項目。 郵件看起來如下列範例： 
    
    ```
    From: Example User <example@contoso.com> 
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed; 
        s=selector1; d=contoso.com; t=1429912795; 
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type; 
        bh=<body hash>; 
        b=<signed field>;
    ```

- 尋找 Authentication-results 標頭。 雖然每個接收服務會使用稍有不同的格式，內送郵件加上戳記，結果應該包含類似**DKIM = 傳遞**或**DKIM = 確定**。 
    
## <a name="to-configure-dkim-for-more-than-one-custom-domain-in-office-365"></a>若要為 Office 365 中的多個自訂網域設定 DKIM
<a name="DKIMMultiDomain"> </a>

如果有些時候您決定在未來新增另一個自訂的網域，而且您想要啟用 DKIM 的新網域，您必須完成本文的每個網域中的步驟。 具體而言，完成所有步驟，[必須執行手動設定 dkim Office 365 中的項目](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)。
  
## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain-in-office-365"></a>停用的 DKIM 簽章原則在 Office 365 中的自訂網域
<a name="DisableDKIMSigningPolicy"> </a>

停用簽章原則不完全停用 DKIM。 在一段時間，Office 365 會自動套用預設的 Office 365 原則，為您的網域。 如需詳細資訊，請參閱[預設 DKIM 與 Office 365 的行為](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)。
  
### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a>若要停用的 DKIM 簽章原則使用 Windows PowerShell

1. [連線至 Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289.aspx) (機器翻譯)。
    
2. 執行下列其中一個您想要停用 DKIM 簽章的每個網域的下列命令。
    
    ```
    $p=Get-DkimSigningConfig -identity <domain>
    $p[0] | set-DkimSigningConfig -enabled $false
    ```

   例如：
    
    ```
    $p=Get-DkimSigningConfig -identity contoso.com
    $p[0] | set-DkimSigningConfig -enabled $false
    ```

   或
    
    ```
    Set-DkimSigningConfig -identity $p[<number>].identity -enabled $false
    ```

    _數字_所在之原則的索引。 例如： 
    
    ```
    Set-DkimSigningConfig -identity $p[0].identity -enabled $false
    ```

## <a name="default-behavior-for-dkim-and-office-365"></a>DKIM 與 Office 365 的預設行為
<a name="DefaultDKIMbehavior"> </a>

如果您不啟用 DKIM，Office 365 會自動建立的自訂網域的 1024年位元 DKIM 公用金鑰] 和 [關聯的私密金鑰我們在內部儲存在我們的資料中心。 根據預設，Office 365 會使用預設的簽章的網域的就地沒有原則設定。 這表示，如果您沒有設定 dkim 自行，Office 365 會使用其預設原則，才能啟用您的網域的 DKIM，它會建立的機碼。
  
此外，如果您停用 DKIM 簽署後，啟用在一段時間後，Office 365 會自動套用您網域的 Office 365 預設原則。
  
在下列範例中，假設為 fabrikam.com 的 DKIM 已啟用 Office 365，而不是依網域的系統管理員。 這表示，所需的 Cname 不存在於 DNS。 從這個網域的電子郵件的 DKIM 簽章看起來像這樣：
  
```
From: Second Example <second.example@fabrikam.com> 
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed; 
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795; 
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type; 
    bh=<body hash>; 
    b=<signed field>;
```

在這個範例中，網域與主機名稱包含要 CNAME 會指向如果 DKIM 簽章為 fabrikam.com 有網域管理員所啟用的值。 最後，從 Office 365 傳送每封郵件將會 DKIM 簽章。 如果您自行啟用 DKIM，網域將會在 [從網域相同： 地址，在此案例的 fabrikam.com。 如果您不等待，它會對齊，並會改用貴組織的初始網域。 如需決定初始網域資訊，請參閱[網域的常見問題集](https://support.office.com/article/1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain)。
  
## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a>使第三方服務可以傳送或詐騙，代表您的自訂網域的電子郵件設定 dkim
<a name="SetUp3rdPartyspoof"> </a>

某些大量電子郵件服務提供者或軟體為-服務提供者，可讓您設定 DKIM 機碼來自其服務的電子郵件。 這需要您自己和協力廠商之間協調才能設定必要的 DNS 記錄。 沒有兩個組織中進行這完全相同的方式。 相反地，處理程序取決於整個組織。
  
顯示 contoso.com 和 bulkemailprovider.com 正確設定的 DKIM 範例郵件看起來可能如下：
  
```
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

在這個範例中，以達到此結果：
  
1. 大量電子郵件供應商 Contoso 公開金鑰 DKIM。
    
2. Contoso 發佈至其 DNS 記錄的 DKIM 機碼。
    
3. 時傳送電子郵件，大量電子郵件提供者會在具有相對應之私密金鑰的機碼。 如此一來，大量電子郵件提供者會附加到郵件標頭的 DKIM 簽章。
    
4. 接收的電子郵件系統來執行 DKIM 檢查驗證 DKIM 簽章 d =\<網域\>根據在 [從網域值: (5322.From) 地址的郵件。 在這個範例中，兩個值相符：
    
    寄件者 @**contoso.com**
    
    d =**contoso.com**
    
## <a name="next-steps-after-you-set-up-dkim-for-office-365"></a>後續步驟： 為 Office 365 設定 dkim 之後
<a name="DKIMNextSteps"> </a>

雖然 DKIM 設計來協助防止詐騙，DKIM 更妥善地運作搭配 SPF 和 DMARC。 一旦您已設定 DKIM，如果您還沒有已設定好 SPF 應執行此作業。 快速介紹 SPF，並讓其快速設定，請參閱[設定 spf 以協助防止詐騙的 Office 365 中](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。 如需更深入了解的 Office 365 如何使用 SPF，或疑難排解或非標準的部署，例如混合式部署，啟動與[Office 365 如何使用寄件者原則架構 (SPF)，來防止詐騙](how-office-365-uses-spf-to-prevent-spoofing.md)。 接下來，請參閱[使用 DMARC 來驗證 Office 365 電子郵件](use-dmarc-to-validate-email.md)。 [反垃圾郵件郵件標頭](anti-spam-message-headers.md)包含針對 DKIM 檢查 Office 365 所使用的語法及標頭欄位。 
  

