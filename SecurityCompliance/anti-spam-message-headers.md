---
title: 反垃圾郵件訊息標頭
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2e3fcfc5-5604-4b88-ac0a-c5c45c03f1db
ms.collection:
- M365-security-compliance
description: Exchange Online Protection 掃描內送電子郵件訊息時它插入**X Forefront-反垃圾郵件報告**標頭每封郵件。
ms.openlocfilehash: fa14d32f06d07bf7c5131e9c417e9baa0720fcdd
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341734"
---
# <a name="anti-spam-message-headers"></a>反垃圾郵件訊息標頭

Exchange Online Protection 掃描內送電子郵件訊息時它插入**X Forefront-反垃圾郵件報告**標頭每封郵件。此標頭中的欄位可協助系統管理員提供相關資訊的郵件及其處理方式。**X-Microsoft 反垃圾郵件**標頭中的欄位提供大宗郵件和網路釣魚的其他資訊。除了這些兩個標頭，Exchange Online Protection 也**authentication-results**標頭中插入處理每一封郵件的電子郵件驗證結果。
  
> [!TIP]
> 如需如何在各種電子郵件用戶端中檢視電子郵件訊息標頭資訊，請參閱 <<c0>郵件標頭分析器。您可以複製並貼入<b1>郵件標頭分析器</b1>工具中的郵件標頭的內容。當您選取隔離區中的郵件在 Exchange 系統管理中心時，<b2>檢視郵件標頭</b2>連結輕鬆也可讓您複製並貼入工具中的郵件標頭文字。一次在郵件標頭分析器工具中，按一下 [<b3>分析標頭</b3>以便擷取標頭的相關資訊。
  
## <a name="x-forefront-antispam-report-message-header-fields"></a>X Forefront-反垃圾郵件報告郵件標頭欄位
<a name="sectionSection0"> </a>

存取郵件標頭資訊之後，搜尋**X Forefront-反垃圾郵件報告**，然後尋找這些欄位。此標頭中的其他欄位專供 Microsoft 反垃圾郵件小組進行診斷之用。

|**標頭欄位**|**描述**|
|:-----|:-----|
|CIP：[IP 位址]|連接的 IP 位址。若要指定這個 IP 位址，在 [連線篩選器建立 IP 允許清單或 IP 封鎖清單時。如需詳細資訊，請參閱 < <b0>Configure the connection filter policy </b0>。|
|CTRY|郵件連線到服務的來源國家。這是由連線的 IP 位址來判斷，這可能與原始傳送的 IP 位址不同。|
|LANG|撰寫郵件所用的語言，如國碼所指定 (例如，ru_RU 代表俄文)。|
|SCL|郵件的垃圾郵件信賴等級 (SCL) 值。如需有關如何解譯這些值的詳細資訊，請參閱 <<c0>垃圾郵件信賴等級。|
|PCL|郵件的網路釣魚信賴等級 (PCL) 值。 |
|SRV:BULK|郵件被視為大量電子郵件訊息。如果已啟用**封鎖所有大量電子郵件訊息的進階垃圾郵件篩選選項**都，它會被標示為垃圾郵件。如果未啟用，它會只被標示為垃圾郵件篩選規則的其餘部分判斷為垃圾郵件。|
|SFV:SFE|已略過篩選，因為它已傳送從個人的安全寄件者清單上的地址，將已讓通過的郵件。|
|SFV:BLK|已略過篩選，因為它已傳送從個人的封鎖寄件者清單上的地址，已封鎖郵件。  <br/> **秘訣**： 如需使用者如何建立安全及封鎖的寄件者清單的詳細資訊，請參閱[封鎖或允許 （垃圾郵件設定）](https://go.microsoft.com/fwlink/p/?LinkId=294862) （outlook 網頁版） 和[垃圾郵件篩選器概觀](https://go.microsoft.com/fwlink/p/?LinkId=270065)(Outlook)。|
|IPV:CAL|因為 IP 位址指定於連線篩選的 [IP 允許] 清單中，所以已透過垃圾郵件篩選允許郵件。|
|IPV:NLI|IP 位址不被列在任何 IP 信譽清單中。|
|SFV:SPM|內容篩選已將郵件標記為垃圾郵件。|
|SFV:SKS|郵件已標示為垃圾郵件，再由內容篩選器進行處理。這包括的郵件郵件符合郵件流程規則 （也稱為傳輸規則） 的位置，自動將它標記為垃圾郵件，並略過所有其他篩選。|
|SFV:SKA|郵件會略過篩選，並已傳遞至收件匣] 中，因為它符合垃圾郵件篩選原則，例如**寄件者允許**清單中的 [允許] 清單。|
|SFV:|郵件已標示為垃圾郵件，因為它符合垃圾郵件篩選原則，例如**寄件者封鎖**清單中的封鎖清單。|
|SFV:SKN|郵件已標示為非垃圾郵件之前會由內容篩選器進行處理。這包括在郵件符合郵件流程規則，以自動將它標記為非垃圾郵件，並略過所有其他篩選的郵件。|
|SFV:SKI|與 SFV:SKN 類似；郵件基於其他原因 (例如，因為是租用戶內的組織內部電子郵件) 而略過篩選。|
|SFV:SKQ|郵件已從隔離區釋出，並傳送給預定的收件者。|
|SFV:NSPM|郵件標記為非垃圾郵件，並傳送給預定的收件者。|
|H:[helostring]|連線郵件伺服器的 HELO 或 EHLO 字串。|
|PTR:[ReverseDNS]|PTR 記錄或指標記錄，傳送端 IP 位址，也稱為反向 DNS 位址。|
|SFTY|郵件已識別為網路釣魚，並使用下列其中一個下列值，也會標示： <br/>• 9.1： 預設值。包含網路釣魚 URL、 可能包含其他網路釣魚的內容，或可能已標示為網路釣魚由另一個郵件篩選器，例如內部部署版本的 Exchange 伺服器之前轉送郵件至 Office 365 的郵件。 <br/>• 9.11： 郵件未通過反詐騙檢查其中的傳送端網域，在 [從： 標頭相同，或對齊，或屬於相同的組織接收方網域。這表示組織內部詐騙安全提示將會新增到郵件。 <br/>• 9.19： 無法在傳送網域嘗試模擬接收者，所擁有的網域或自訂的網域由反網路釣魚原則保護的網域模擬檢查的郵件。這表示模擬安全提示將會新增到郵件，如果啟用透過反網路釣魚原則。 <br/>• 9.20： 郵件無法傳送的使用者嘗試模擬接收器組織內的使用者，或自訂的使用者受到反網路釣魚原則的使用者模擬檢查。這表示模擬安全提示將會新增到郵件，如果啟用透過反網路釣魚原則。 <br/>• 9.21： 無法反詐騙檢查，在 [從在傳送網域的郵件： 標頭不會驗證及來自外部網域。搭配 CompAuth （請參閱驗證結果）。 <br/>• 9.22： 相同 9.21，不同之處在於使用者擁有安全的寄件者覆寫。 <br/>• 9.23： 相同 9.22，不同之處在於組織具有的允許寄件者或網域，已覆寫。 <br/>• 9.24： 相同 9.23，不同之處在於使用者擁有 Exchange 郵件流程規則覆寫。|
|X-CustomSpam：[ASFOption]|郵件符合進階垃圾郵件篩選選項。例如， <b0>X-customspam： 遠端站台連結的圖像</b0>表示已符合<b1>遠端站台的影像連結</b1>ASF 選項。若要了解哪些 X 標頭文字加入每個特定 ASF 選項，請參閱 <<c2>進階垃圾郵件篩選選項。|
   
## <a name="x-microsoft-antispam-message-header-fields"></a>X-Microsoft 反垃圾郵件郵件標頭欄位
<a name="sectionSection1"> </a>

下表說明有用**X-Microsoft 反垃圾郵件**郵件標頭中的欄位。此標頭中的其他欄位專供 Microsoft 反垃圾郵件小組進行診斷之用。
  
|**標頭欄位**|**描述**|
|:-----|:-----|
|BCL|大量抱怨層級 (BCL) 的郵件。如需詳細資訊，請參閱[大量抱怨層級的值](bulk-complaint-level-values.md)。|
|PCL|網路釣魚信賴等級 (PCL) 的訊息，指出是否是網路釣魚郵件。此狀態可以傳回為下列其中一個下列數值：<br/>• **0-3**： 郵件的內容不可能是網路釣魚。 <br/>• **4-8**： 郵件的內容很可能是網路釣魚。 <br/>• **-9990**: (Exchange Online Protection 僅) 郵件的內容很可能是網路釣魚。  <br/>  值用來判斷您的電子郵件用戶端對郵件採取什麼動作。例如，Outlook 會使用 PCL 戳記來封鎖可疑郵件的內容。如需有關網路釣魚及 Outlook 處理網路釣魚郵件的方式的詳細資訊，請參閱[開啟或關閉電子郵件訊息中的連結](https://support.office.com/article/2D79B907-93B6-4774-82E6-1F0385CF20F8)。|
   
## <a name="authentication-results-message-header"></a>驗證結果的郵件標頭
<a name="sectionSection2"> </a>

針對 SPF，DKIM、 DMARC 檢查的結果會記錄，或加上戳記，當我們郵件伺服器收到的電子郵件的**驗證結果**郵件標頭中的 Office 365。
  
### <a name="check-stamp-syntax-and-examples"></a>檢查戳記語法和範例
<a name="referenceSPFstamp"> </a>

下列的語法範例顯示的文字部分 」 戳記 」 的 Office 365 適用於每個正文電子郵件的驗證檢查，當我們郵件伺服器所接收的電子郵件的郵件標頭。戳記會新增至的**Authentication-results**標頭。
  
 **語法： SPF 檢查戳記**
  
Spf，適用於下列語法。
  
```
spf=<pass (IP address)|fail (IP address)|softfail (reason)|neutral|none|temperror|permerror> smtp.mailfrom=<domain>
```

 **範例： SPF 檢查戳記**
  
```
spf=pass (sender IP is 192.168.0.1) smtp.mailfrom=contoso.com
spf=fail (sender IP is 127.0.0.1) smtp.mailfrom=contoso.com
```

 **語法： DKIM 檢查戳記**
  
對於 DKIM，會套用下列語法。
  
```
dkim=<pass|fail (reason)|none> header.d=<domain>
```

 **範例： DKIM 檢查戳記**
  
```
dkim=pass (signature was verified) header.d=contoso.com
dkim=fail (body hash did not verify) header.d=contoso.com
```

 **語法： DMARC 檢查戳記**
  
針對 DMARC，適用於下列語法。
  
```
dmarc=<pass|fail|bestguesspass|none> action=<permerror|temperror|oreject|pct.quarantine|pct.reject> header.from=<domain>
```

 **範例： DMARC 檢查戳記**
  
```
dmarc=pass action=none header.from=contoso.com
dmarc=bestguesspass action=none header.from=contoso.com
dmarc=fail action=none header.from=contoso.com
dmarc=fail action=oreject header.from=contoso.com
```

### <a name="authentication-results-message-header-fields-used-by-office-365-email-authentication"></a>驗證結果的郵件 Office 365 電子郵件驗證所使用的標頭欄位
<a name="referenceSPFstamp"> </a>

此表說明的欄位及可能的值為每個電子郵件的驗證檢查。
  
|**標頭欄位**|**描述**|
|:-----|:-----|
|spf|說明郵件 SPF 檢查的結果。可能值包括：<br/>•**傳遞 （IP 位址）**： 指出傳遞郵件的 SPF 檢查，並包含寄件者的 IP 位址。用戶端授權來傳送或轉送代表寄件者網域的電子郵件。<br/>•**失敗 （IP 位址）**： 會指出失敗郵件的 SPF 檢查，並包含寄件者的 IP 位址。這有時稱為_完全未通過]_。<br/>• **softfail （原因）**： 表示 SPF 記錄已指定主機為不允許傳送，但在轉換。 <br/>•**中性**： 指出的 SPF 記錄有明確指定，它不判斷是否已授權的 IP 位址。 <br/>• **none**： 表示網域沒有 SPF 記錄或 SPF 記錄不會評估的結果。 <br/>• **temperror**： 指出錯誤發生，可能是暫時性的性質，例如，DNS 錯誤。嘗試稍後再可能會成功並無任何系統管理員動作。<br/>• **permerror**： 指出發生永久性錯誤。發生這種情況，例如，網域有格式錯誤的 SPF 記錄。|
|smtp.mailfrom|包含從中傳送郵件的來源網域。任何錯誤是關於此電子郵件將傳送給郵件管理員或負責網域的實體。這有時稱為 5321.MailFrom 地址或反向路徑地址在郵件信封。|
|dkim|說明郵件 DKIM 檢查的結果。可能值包括：<br/>•**傳遞**： 指出郵件傳遞 DKIM 檢查。 <br/>•**失敗 （原因）**： 會指出失敗郵件的 DKIM 檢查和原因。例如，如果未簽署的郵件，或未驗證簽章。<br/>• **none**： 表示郵件已不帶正負號。這可能有或可能不會指出網域有 DKIM 記錄或 DKIM 記錄不會評估的結果，只有這封郵件已不帶正負號。|
|header.d|如果有的話的 DKIM 簽章中所識別網域。這是查詢的公開金鑰的網域。|
|dmarc|說明郵件 DMARC 檢查的結果。可能值包括：<br/>•**傳遞**： 指出郵件通過 DMARC 檢查。 <br/>•**失敗**： 指出失敗郵件的 DMARC 檢查。 <br/>• **bestguesspass**： 表示在網域沒有 DMARC TXT 記錄存在，但如果其中一個已存在，就能傳遞郵件的 DMARC 檢查。這是因為中 5321.MailFrom 地址的網域符合 5322.From 地址的網域。<br/>• **none**： 表示沒有 DKIM TXT 記錄都存在的傳送中的網域 DNS。|
|巨集指令|會指出 DMARC 檢查的結果為基礎的垃圾郵件篩選器所採取的動作。例如：<br/>• **permerror**: DMARC 評估期間發生永久性錯誤例如遇到錯誤的 DMARC TXT 記錄在 DNS 中。嘗試重新傳送此郵件不可能結尾不同的結果。相反地，您可能需要連絡網域的擁有者以解決問題。<br/>• **temperror**: DMARC 評估期間發生暫時性錯誤。您可能會要求寄件者重新傳送更新版本才能正確地處理電子郵件訊息。<br/>• <b0>oreject</b0>或<b1>o.reject</b1>： 待命的覆寫拒絕。在此案例 Office 365 會使用此巨集指令收到未通過 DMARC 的郵件時檢查其 DMARC TXT 記錄具有 p 的原則的網域中 = 拒絕。而不是刪除或拒絕郵件，Office 365 會將郵件標示為垃圾郵件。如需有關 Office 365 為什麼設定這種方式的詳細資訊，請參閱 < <b2>Office 365 如何處理內送電子郵件，未通過 DMARC</b2>。<br/>• **pct.quarantine**： 表示百分比小於 100%的未通過 DMARC 的郵件將會繼續傳遞。這表示郵件無法 DMARC 和原則設為隔離，但 pct 欄位未設定為 100%和系統隨機決定不適用 DMARC 動作]，依指定的網域原則。<br/>• **pct.reject**： 表示百分比小於 100%的未通過 DMARC 的郵件將會繼續傳遞。這表示郵件無法 DMARC 和原則設為 [拒絕，但 pct 欄位未設定為 100%和系統隨機決定不適用 DMARC 動作]，依指定的網域原則。|
|header.from|在電子郵件訊息標頭之 From 地址網域。這有時稱為_5322.From_地址。|
|compauth|複合驗證結果。Office 365 所用來結合多個例如 SPF、 DKIM、 DMARC 或任何其他的一部分來判斷已驗證郵件訊息的驗證類型。使用 [從： 評估的基礎的網域。|
|原因|原因的複合驗證成功或失敗。三位數是由原因的值所組成：<br/>• **000**： 郵件明確無法驗證。例如，收到郵件的隔離或拒絕動作 DMARC 失敗。<br/>• **001**： 郵件以隱含方式無法驗證，並且在傳送網域沒有發行驗證原則。例如，DMARC 原則的 p = 無。<br/>• **1xx**： 將郵件傳遞驗證。第二個兩位數是由 Office 365 的內部代碼。<br/>• **2xx**： 訊息虛傳遞驗證。第二個兩位數是由 Office 365 的內部代碼。<br/>• **3xx**： 郵件已不檢查複合驗證。 <br/>• **4xx**： 郵件略過複合驗證。第二個兩位數是由 Office 365 的內部代碼。|
