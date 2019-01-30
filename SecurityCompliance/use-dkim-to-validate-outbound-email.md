---
title: 使用 DKIM 驗證從您在 Office 365 中的自訂網域傳送的輸出電子郵件
ms.author: krowley
author: kccross
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.custom: TN2DMC
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
description: 摘要： 本文將告訴您如何使用 DomainKeys 識別郵件 (DKIM) 與 Office 365 以確定目的地的電子郵件系統信任從自訂網域傳送的訊息。
ms.openlocfilehash: b5b28bef60148749e3ea6ac2619358fbc425e36c
ms.sourcegitcommit: 03b9221d9885bcde1cdb5df2c2dc5d835802d299
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2019
ms.locfileid: "29614447"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain-in-office-365"></a>使用 DKIM 驗證從您在 Office 365 中的自訂網域傳送的輸出電子郵件

 **摘要：** 本文將告訴您如何使用 DomainKeys 識別郵件 (DKIM) 與 Office 365 以確定目的地的電子郵件系統信任從自訂網域傳送的訊息。 
  
您應該使用 DKIM 除了 SPF 和 DMARC 避免 spoofers 傳送看起來像它們來自您網域的郵件。DKIM 可讓您將數位簽章新增至郵件標頭中的電子郵件訊息。複雜的聲音，但其確實不是。當您設定 DKIM 時，您授權網域建立關聯，或登入電子郵件訊息使用密碼編譯驗證其名稱。從您的網域接收電子郵件的電子郵件系統可以使用此數位簽章可協助判斷其接收內送電子郵件是否合法。
  
基本上，您可使用私密金鑰來加密您的網域外寄電子郵件中的頁首。您可以發佈公開金鑰接收伺服器可以使用解碼簽章的網域的 DNS 記錄。他們使用公開金鑰來確認訊息會真正來自您並不來自詐騙網域某人。
  
Office 365 自動會設定 DKIM 的初始網域。初始網域是當您使用的服務，例如 contoso.onmicrosoft.com 註冊為您建立 Office 365 的網域。您不需要執行任何動作來設定 DKIM 初始網域。如需網域的詳細資訊，請參閱 ＜[網域常見問題集](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain)。
  
您可以選擇執行任何 DKIM 相關動作的自訂網域。若不要為您的自訂網域設定 DKIM、 Office 365 建立私密與公開金鑰組、 啟用 DKIM 簽署，並設定巡自訂網域的 Office 365 預設原則。雖然這是大部分的 Office 365 客戶的足夠涵蓋範圍，您應該以手動方式設定 DKIM 自訂網域在下列情況：
  
- 您有多個自訂網域在 Office 365
    
- 您要設定 DMARC 太 （建議）
    
- 您想要控制您的私密金鑰
    
- 您要自訂 CNAME 記錄
    
- 您要設定 DKIM 機碼不在協力廠商網域，例如源自的電子郵件如果您使用協力廠商大量郵件處理程式。
    
本文內容：
  
- [DKIM 優於 SPF 單獨以避免遭到惡意詐騙 Office 365 中運作的方式](use-dkim-to-validate-outbound-email.md#HowDKIMWorks)
    
- [您需要手動設定 Office 365 中的 DKIM 執行動作](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)
    
- [若要設定多個自訂網域在 Office 365 DKIM](use-dkim-to-validate-outbound-email.md#DKIMMultiDomain)
    
- [停用 DKIM 簽署 Office 365 中的自訂網域原則](use-dkim-to-validate-outbound-email.md#DisableDKIMSigningPolicy)
    
- [DKIM 與 Office 365 的預設行為](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)
    
- [設定 DKIM 才能讓協力廠商服務可傳送] 或詐騙代表自訂網域的電子郵件](use-dkim-to-validate-outbound-email.md#SetUp3rdPartyspoof)
    
- [後續步驟： 您針對 Office 365 設定 DKIM 之後](use-dkim-to-validate-outbound-email.md#DKIMNextSteps)
    
## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing-in-office-365"></a>DKIM 優於 SPF 單獨以避免遭到惡意詐騙 Office 365 中運作的方式
<a name="HowDKIMWorks"> </a>

SPF 將資訊新增至郵件信封，但 DKIM 真的要加密的郵件標頭中的簽章。當您將郵件轉寄時，部分的郵件信封可以是已除去離開轉接伺服器。由於數位簽章保持電子郵件訊息由於電子郵件標頭的一部分，適用於 DKIM 即使當郵件已轉寄如下列範例所示。
  
![流程圖顯示當 SPF 檢查不通過時，轉送的訊息會傳遞 DKIM 驗證](media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)
  
在這個範例中，如果您僅有發佈的 SPF TXT 記錄您網域的收件者的郵件伺服器可能已標記為垃圾電子郵件並產生 false 正值的結果。在此案例中加入 DKIM 減少 false 正數垃圾郵件報告。因為 DKIM 依賴公開金鑰加密來驗證並不只是 IP 位址、 DKIM 會被視為多更有力表單驗證的 SPF 比。我們建議使用 SPF 並 DKIM，以及 DMARC 部署中。
  
講述至今： DKIM 使用的私密金鑰來加密的簽章插入郵件標頭。簽署網域或輸出網域插入的值為**d =** 在標頭] 欄位。確認網域，] 或 [收件者的網域，然後使用**d =** 從 DNS 查閱公開金鑰及驗證郵件] 欄位。如果已驗證的訊息，會傳遞 DKIM] 核取。 
  
## <a name="what-you-need-to-do-to-manually-set-up-dkim-in-office-365"></a>您需要手動設定 Office 365 中的 DKIM 執行動作
<a name="SetUpDKIMO365"> </a>

若要設定 DKIM，您將會完成下列步驟：
  
- [在 DNS 中發佈兩個自訂網域的 CNAME 記錄](use-dkim-to-validate-outbound-email.md#Publish2CNAME)
    
- [啟用 DKIM 簽署的自訂網域在 Office 365](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)
    
### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a>在 DNS 中發佈兩個自訂網域的 CNAME 記錄
<a name="Publish2CNAME"> </a>

您要將 DKIM 簽章新增在 DNS 中每個的網域，您需要將發佈兩個 CNAME 記錄。CNAME 記錄的 DNS 用以指定網域的正式名稱是其他網域名稱的別名。 
  
 Office 365 執行自動使用您所建立的兩個記錄的重要旋轉角度。如果您已佈建除了初始網域在 Office 365 中的自訂網域，您必須發佈兩個每個其他網域的 CNAME 記錄。因此，如果您有兩個網域，您必須發佈兩個額外的 CNAME 記錄，等等。
  
使用下列格式的 CNAME 記錄。

> [!IMPORTANT]
> 如果您是其中一個我們 GCC 高的客戶，我們計算_domainGuid_不同 ！而不是查閱計算_domainGuid_您_initialDomain_的 MX 記錄，但是我們計算它直接從自訂的網域。例如，如果您的自訂的網域為"contoso.com"您 domainGuid 會變成"contoso com"、 任何期間已取代為虛線。

如此，不論什麼 MX 記錄您 initialDomain 指向，您將一律使用上述方法來計算 CNAME 記錄中使用 domainGuid。

  
```
Host name:          selector1._domainkey
Points to address or value: selector1-<domainGUID>._domainkey.<initialDomain> 
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: selector2-<domainGUID>._domainkey.<initialDomain> 
TTL:                3600
```

其中：
  
- Office 365 選取器一律是"selector1"或"selector2"。 
    
- _domainGUID_是在自訂 MX 記錄的自訂網域出現之前 mail.protection.outlook.com _domainGUID_相同。例如，在網域 contoso.com 的下列 MX 記錄， _domainGUID_是 contoso com: 
    
    ```
    contoso.com.  3600  IN  MX   5 contoso-com.mail.protection.outlook.com
    ```

- _initialDomain_是註冊 Office 365 時所使用的網域。在 onmicrosoft.com 一律結束初始網域。如需決定在初始網域的資訊，請參閱 ＜[網域常見問題集](https://support.office.com/article/1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain)。
    
例如，如果您有 cohovineyardandwinery.onmicrosoft.com、 初始網域和兩個自訂網域 cohovineyard.com cohowinery.com，就必須設定兩個總共四個 CNAME 記錄的每個其他網域的 CNAME 記錄。
  
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

### <a name="enable-dkim-signing-for-your-custom-domain-in-office-365"></a>啟用 DKIM 簽署的自訂網域在 Office 365
<a name="EnableDKIMinO365"> </a>

一旦您已經在 DNS 中發佈的 CNAME 記錄，您就可以啟用 DKIM 簽署透過 Office 365。透過 Office 365 系統管理中心或使用 PowerShell 您可以這麼做。
  
#### <a name="to-enable-dkim-signing-for-your-custom-domain-through-the-office-365-admin-center"></a>若要啟用 DKIM 簽署的自訂網域透過 Office 365 系統管理中心

1. 使用您的 公司或學校帳戶[登入 Office 365](https://support.office.microsoft.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4)。 
    
2. 選取左上角的應用程式啟動器圖示，然後選擇 [管理員]****。
    
3. 左下瀏覽窗格中展開 [**系統管理**，並選擇 [ **Exchange**。
    
4. 移至 [**保護** \> **dkim**。
    
5. 選取您要啟用 DKIM，然後**登 DKIM 簽章與這個網域的郵件**，選擇 [**啟用**的網域。針對每個自訂網域重複此步驟。
    
#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a>若要啟用 DKIM 簽署的自訂網域透過 PowerShell

1. [連線至 Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289.aspx) (機器翻譯)。
    
2. 執行下列命令：
    
    ```
    New-DkimSigningConfig -DomainName <domain> -Enabled $true
    ```

   其中_網域_是您想要啟用 DKIM 簽署的自訂網域名稱。 
    
   例如，網域 contoso.com 的：
    
    ```
    New-DkimSigningConfig -DomainName contoso.com -Enabled $true
    ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-office-365"></a>若要確認 DKIM 簽署的設定正確的 Office 365

等候幾分鐘時間才能遵循這些步驟以確認您已正確設定 DKIM。這可讓散佈整個網路網域的 DKIM 資訊的時間。
  
- 將郵件從內啟用 Office 365 DKIM 的網域帳戶傳送到如 outlook.com 或還是其他電子郵件帳戶。
    
- 請勿使用 aol.com 帳戶針對測試用途。AOL 可能會略過 DKIM 檢查如果通過 SPF] 核取。這將會進行造成測試。
    
- 開啟郵件並查看標頭。檢視郵件標頭指示目視郵件用戶端。如需在 Outlook 中檢視郵件標頭的指示，請參閱 ＜[檢視的電子郵件訊息標頭](https://support.office.com/article/CD039382-DC6E-4264-AC74-C048563D212C)。

  DKIM 簽署郵件會包含的主機名稱與您定義發佈 CNAME 項目時的網域。郵件的外觀類似此範例會如下： 
    
    ```
    From: Example User <example@contoso.com> 
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed; 
        s=selector1; d=contoso.com; t=1429912795; 
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type; 
        bh=<body hash>; 
        b=<signed field>;
    ```

- 尋找驗證結果標頭。雖然每個接收服務使用內送郵件加上戳記稍有不同的格式，其結果應該包含類似如下**DKIM = 傳遞**或**DKIM = 確定**。 
    
## <a name="to-configure-dkim-for-more-than-one-custom-domain-in-office-365"></a>若要設定多個自訂網域在 Office 365 DKIM
<a name="DKIMMultiDomain"> </a>

如果在某些未來您決定要新增另一個自訂的網域且您想要啟用 DKIM 為新的網域，您必須完成本文中的每個網域中的步驟。尤其是完成中[必須執行手動設定 DKIM Office 365 中](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)的所有步驟。
  
## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain-in-office-365"></a>停用 DKIM 簽署 Office 365 中的自訂網域原則
<a name="DisableDKIMSigningPolicy"> </a>

停用簽署原則不會不會完全停用 DKIM。在一段時間內，Office 365 會自動套用預設的 Office 365 原則為您的網域。如需詳細資訊，請參閱[預設 DKIM 與 Office 365 的行為](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)。
  
### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a>若要停用 DKIM 簽署原則使用 Windows PowerShell

1. [連線至 Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289.aspx) (機器翻譯)。
    
2. 執行下列命令為您要停用 DKIM 簽署每個網域。
    
    ```
    $p=Get-DkimSigningConfig -identity <domain>
    $p[0] | set-DkimSigningConfig -enabled $false
    ```

   例如：
    
    ```
    $p=Get-DkimSigningConfig -identity contoso.com
    $p[0] | set-DkimSigningConfig -enabled $false
    ```

   或者
    
    ```
    Set-DkimSigningConfig -identity $p[<number>].identity -enabled $false
    ```

    其中_號碼_是原則的索引。例如： 
    
    ```
    Set-DkimSigningConfig -identity $p[0].identity -enabled $false
    ```

## <a name="default-behavior-for-dkim-and-office-365"></a>DKIM 與 Office 365 的預設行為
<a name="DefaultDKIMbehavior"> </a>

如果您不要啟用 DKIM、 Office 365 會自動建立 1024年位元 DKIM 公開金鑰的自訂網域和相關聯的私密金鑰的我們內部儲存在我們的資料中心。根據預設，Office 365 使用簽署備妥沒有原則的網域設定為預設。這表示如果您不需要設定 DKIM 自行、 Office 365 將會使用其預設原則和以啟用 DKIM 網域建立的機碼。
  
此外，如果您停用 DKIM 簽署之後，啟用一段時間之後，Office 365 將自動套用您網域的 Office 365 預設原則。
  
在下列範例中，假設已啟用為 fabrikam.com 的 DKIM 時由 Office 365 中，而不是依之網域的系統管理員。這表示需要的 Cname 不要在 DNS 中存在。從這個網域的電子郵件的 DKIM 簽章看起來會類似：
  
```
From: Second Example <second.example@fabrikam.com> 
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed; 
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795; 
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type; 
    bh=<body hash>; 
    b=<signed field>;
```

在此範例中的主機名稱與網域包含要 CNAME 會指向如果 fabrikam.com DKIM 簽署鎖網域系統管理員所啟用的值。最後，從 Office 365 傳送每一個單一訊息將會 DKIM 簽署。如果您自行啟用 DKIM，網域將會在 [從網域相同： 位址，在此案例的 fabrikam.com。如果您未將不會對齊並將改用貴組織的初始網域。如需決定在初始網域的資訊，請參閱 ＜[網域常見問題集](https://support.office.com/article/1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain)。
  
## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a>設定 DKIM 才能讓協力廠商服務可傳送] 或詐騙代表自訂網域的電子郵件
<a name="SetUp3rdPartyspoof"> </a>

某些大量電子郵件服務提供者或軟體為-a-服務提供者可讓您設定電子郵件來自其服務 DKIM 機碼。這需要自行與協力廠商之間協調才能設定所需的 DNS 記錄。沒有兩個組織必須進行完全相同的方式。而是程序取決於整個組織。
  
顯示為 contoso.com 和 bulkemailprovider.com 正確設定的 DKIM 範例訊息可能看起來如下：
  
```
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

在這個範例中，以達到此結果：
  
1. 大量電子郵件供應商授與 Contoso DKIM 公開金鑰。
    
2. Contoso 發佈 DKIM 金鑰及其 DNS 記錄。
    
3. 時傳送電子郵件、 大量電子郵件供應商簽署金鑰與對應的私密金鑰。如此一來，大量電子郵件供應商附加 DKIM 簽章的郵件標頭。
    
4. 接收的電子郵件系統來執行 DKIM] 核取驗證 DKIM 簽章 d =\<網域\>針對在 [從網域的值： (5322.From) 之郵件的地址。在此範例中的值符合：
    
    寄件者 @**contoso.com**
    
    d =**contoso.com**
    
## <a name="next-steps-after-you-set-up-dkim-for-office-365"></a>後續步驟： 您針對 Office 365 設定 DKIM 之後
<a name="DKIMNextSteps"> </a>

雖然 DKIM 專門設計來協助防止詐騙、 DKIM 適用於更妥善地 SPF 和 DMARC。一旦您已設定好 DKIM，如果您已經不已經設定 SPF 您應達成。快速介紹 SPF 以及要取得其快速地設定，請參閱[Set up SPF 避免詐騙的 Office 365 中](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。更深入了解 Office 365 如何使用 SPF，或者例如混合部署的疑難排解或非標準部署開始使用[Office 365 如何使用寄件者原則架構 (SPF) 若要防止詐騙](how-office-365-uses-spf-to-prevent-spoofing.md)。接下來，請參閱[使用 DMARC 來驗證 Office 365 中的電子郵件](use-dmarc-to-validate-email.md)。[反垃圾郵件郵件標頭](anti-spam-message-headers.md)包含 DKIM 檢查 Office 365 所使用的語法和標頭欄位。 
  

