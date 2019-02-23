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
description: Exchange Online Protection 掃描內送電子郵件訊息時加以插入**X Forefront-反垃圾郵件報告**標題每則訊息。
ms.openlocfilehash: 4851c05f4db8d120eb54b9c22025fe2972e1e515
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223582"
---
# <a name="anti-spam-message-headers"></a>反垃圾郵件訊息標頭

Exchange Online Protection 掃描內送電子郵件訊息時加以插入**X Forefront-反垃圾郵件報告**標題每則訊息。此標頭中的欄位可協助系統管理員提供郵件以及處理方式的資訊。**X-Microsoft 反垃圾郵件**標頭中的欄位會提供大量郵件和網路釣魚的其他資訊。除了這些兩個標頭，Exchange Online Protection 也**驗證結果**標頭中插入它處理每封郵件的電子郵件驗證結果。
  
> [!TIP]
> 如需如何在各種電子郵件用戶端中檢視的電子郵件訊息標頭資訊，請參閱 ＜[郵件標頭 Analyzer](https://go.microsoft.com/fwlink/p/?LinkId=306583)。您可以複製並貼入[訊息標頭 Analyzer](https://testconnectivity.microsoft.com/?tabid=mha)工具的郵件標頭的內容。當您選取一則訊息隔離區中的 Exchange 系統管理中心時，**檢視郵件標頭**連結也容易可讓您複製並貼到此工具的郵件標頭文字。一次在郵件標頭 Analyzer 工具] 按一下 [**分析標頭**以擷取標頭的相關資訊。
  
## <a name="x-forefront-antispam-report-message-header-fields"></a>X Forefront-反垃圾郵件報告郵件標頭欄位
<a name="sectionSection0"> </a>

存取郵件標頭資訊之後，搜尋**X Forefront-反垃圾郵件**報告和則尋找這些欄位。此標頭的其他欄位可用專供 Microsoft 反垃圾郵件小組進行診斷之用。

|**標頭欄位**|**描述**|
|:-----|:-----|
|CIP：[IP 位址]|連線的 IP 位址。若要建立的連線篩選的 IP 允許清單或 IP 封鎖清單時指定此 IP 位址。如需詳細資訊，請參閱[設定連線篩選原則](configure-the-connection-filter-policy.md)。|
|CTRY|郵件連線到服務的來源國家。這是由連線的 IP 位址來判斷，這可能與原始傳送的 IP 位址不同。|
|LANG|撰寫郵件所用的語言，如國碼所指定 (例如，ru_RU 代表俄文)。|
|SCL|郵件的垃圾郵件信賴等級 (SCL) 值。如需解譯這些值的詳細資訊，請參閱[Spam confidence levels](spam-confidence-levels.md)。|
|PCL|網路釣魚信賴等級 (PCL) 值的郵件。 |
|SRV:BULK|郵件已被識別為大量電子郵件訊息。如果已啟用**封鎖所有大量電子郵件訊息進階垃圾郵件篩選選項**都，它將會標示為垃圾郵件。如果未啟用，它只時才會標示為垃圾郵件篩選規則的其餘部分決定郵件為垃圾郵件。|
|SFV:SFE|已略過篩選作業並允許郵件傳入是因為它從個人的安全寄件者清單上的地址傳送。|
|SFV:BLK|已略過篩選和封鎖該郵件是因為它從個人的封鎖寄件者清單上的地址傳送。  <br/> **提示**： 如需如何使用者建立安全及封鎖的寄件者清單的詳細資訊，請參閱[封鎖或允許 （垃圾郵件設定）](https://go.microsoft.com/fwlink/p/?LinkId=294862) (在 web 上的 Outlook) 和[垃圾郵件篩選工具的概觀](https://go.microsoft.com/fwlink/p/?LinkId=270065)(Outlook)。|
|IPV:CAL|因為 IP 位址指定於連線篩選的 [IP 允許] 清單中，所以已透過垃圾郵件篩選允許郵件。|
|IPV:NLI|IP 位址不被列在任何 IP 信譽清單中。|
|SFV:SPM|內容篩選已將郵件標記為垃圾郵件。|
|SFV:SKS|內容篩選在處理郵件前，已將郵件標記為垃圾郵件。這包括符合傳輸規則因此自動標記為垃圾郵件，因而略過所有其他篩選的郵件。|
|SFV:SKA|郵件略過篩選，且因為符合垃圾郵件篩選原則，例如 [**寄件者允許**] 清單中的 [允許] 清單已傳遞至收件匣。|
|SFV:SKB|已將郵件標記為垃圾郵件因為符合在垃圾郵件篩選器原則中，例如**寄件者封鎖**清單封鎖清單。|
|SFV:SKN|郵件已標示為非垃圾郵件之前所處理的內容篩選器。這包括其中郵件符合傳輸規則來自動將其標示為非垃圾郵件和略過所有其他篩選的郵件。|
|SFV:SKI|與 SFV:SKN 類似；郵件基於其他原因 (例如，因為是租用戶內的組織內部電子郵件) 而略過篩選。|
|SFV:SKQ|郵件已從隔離區釋出，並傳送給預定的收件者。|
|SFV:NSPM|郵件標記為非垃圾郵件，並傳送給預定的收件者。|
|H:[helostring]|連線郵件伺服器的 HELO 或 EHLO 字串。|
|PTR:[ReverseDNS]|PTR 記錄或指標記錄，傳送的 IP 位址，也稱為反向 DNS 位址。|
|SFTY|郵件已識別為網路釣魚和也會標示為具有下列值之一： <br/>• 9.1： 預設值。包含網路釣魚 URL、 可能包含其他網路釣魚內容，或可能已標示為網路釣魚由如 Exchange Server 的內部部署版本的另一個郵件篩選器之前轉送至 Office 365 郵件的郵件。 <br/>• 9.11： 郵件無法反詐騙檢查其中的傳送端網域中寄： 標頭相同，或是配合，或屬於相同組織為接收網域。這表示內 org 詐騙 safety 提示將會新增到郵件。 <br/>• 9.19： 郵件無法傳送端網域嘗試模擬接收器所擁有的網域] 或 [受保護的反網路釣魚原則影響的自訂網域的網域模擬檢查。這表示模擬 safety 提示將會新增到郵件，如果啟用透過反 Phishig 原則。 <br/>• 9.20： 郵件無法使用者模擬檢查出傳送的使用者嘗試模擬接收器組織內的使用者或自訂使用者受到反網路釣魚原則。這表示模擬 safety 提示將會新增到郵件，如果啟用透過反 Phishig 原則。 <br/>• 9.21： 郵件無法反詐騙檢查和在 [從的傳送端網域： 標頭不驗證和來自外部網域。一起 CompAuth （請參閱驗證結果）。 <br/>• 9.22： 相同 9.21，不同之處在於使用者具有安全的寄件者已覆寫的。 <br/>• 9.23： 相同 9.22，不同之處在於組織有允許寄件者或已覆寫的網域。 <br/>• 9.24： 相同 9.23，不同之處在於使用者具有已覆寫 Exchange 郵件流程規則。|
|X-CustomSpam：[ASFOption]|郵件符合進階垃圾郵件篩選選項。例如， **X-customspam： 遠端站台連結的圖像**表示已符合**遠端站台的影像連結**ASF] 選項。若要找出哪些 x-header 文字新增每個特定 ASF 選項，請參閱[進階垃圾郵件篩選選項](advanced-spam-filtering-asf-options.md)。|
   
## <a name="x-microsoft-antispam-message-header-fields"></a>X-Microsoft 反垃圾郵件郵件標頭欄位
<a name="sectionSection1"> </a>

下表說明**X-Microsoft 反垃圾郵件**的郵件標頭中的實用欄位。此標頭的其他欄位可用專供 Microsoft 反垃圾郵件小組進行診斷之用。
  
|**標頭欄位**|**描述**|
|:-----|:-----|
|BCL|大量抱怨層級 (BCL) 的郵件。如需詳細資訊，請參閱[大量抱怨層級的值](bulk-complaint-level-values.md)。|
|PCL|網路釣魚信賴等級 (PCL) 會指出是否詐騙郵件的郵件。此狀態可以傳回成下列的數字值之一：<br/>• [ **0-3**： 郵件的內容不太可能是網路釣魚。 <br/>• [ **4-8**： 郵件的內容是可能是網路釣魚。 <br/>• **-9990**: (Exchange Online Protection 僅) 郵件的內容是可能是網路釣魚。  <br/>  值可用來判斷您的電子郵件用戶端的郵件採取的動作。例如，Outlook 會使用 PCL 戳記封鎖的可疑郵件的內容。如需網路釣魚及 Outlook 如何處理網路釣魚郵件的詳細資訊，請參閱[開啟或關閉電子郵件訊息中的連結](https://support.office.com/article/2D79B907-93B6-4774-82E6-1F0385CF20F8)。|
   
## <a name="authentication-results-message-header"></a>驗證結果的郵件標頭
<a name="sectionSection2"> </a>

針對 SPF、 DKIM，以及 DMARC 檢查的結果記錄，或是由 Office 365 中**驗證結果**的郵件標頭時信箱伺服器接收電子郵件訊息上戳記。
  
### <a name="check-stamp-syntax-and-examples"></a>檢查戳記語法和範例
<a name="referenceSPFstamp"> </a>

下列的語法範例顯示的文字部分"戳記"Office 365 適用於每個程電子郵件驗證] 核取時由郵件伺服器接收的電子郵件的郵件標頭。戳記新增至**驗證結果**標頭。
  
 **下列的語法： SPF] 核取戳記**
  
針對 SPF，適用於下列的語法。
  
```
spf=<pass (IP address)|fail (IP address)|softfail (reason)|neutral|none|temperror|permerror> smtp.mailfrom=<domain>
```

 **範例： SPF] 核取戳記**
  
```
spf=pass (sender IP is 192.168.0.1) smtp.mailfrom=contoso.com
spf=fail (sender IP is 127.0.0.1) smtp.mailfrom=contoso.com
```

 **下列的語法： DKIM] 核取戳記**
  
針對 DKIM，適用於下列的語法。
  
```
dkim=<pass|fail (reason)|none> header.d=<domain>
```

 **範例： DKIM] 核取戳記**
  
```
dkim=pass (signature was verified) header.d=contoso.com
dkim=fail (body hash did not verify) header.d=contoso.com
```

 **下列的語法： DMARC] 核取戳記**
  
針對 DMARC，適用於下列的語法。
  
```
dmarc=<pass|fail|bestguesspass|none> action=<permerror|temperror|oreject|pct.quarantine|pct.reject> header.from=<domain>
```

 **範例： DMARC] 核取戳記**
  
```
dmarc=pass action=none header.from=contoso.com
dmarc=bestguesspass action=none header.from=contoso.com
dmarc=fail action=none header.from=contoso.com
dmarc=fail action=oreject header.from=contoso.com
```

### <a name="authentication-results-message-header-fields-used-by-office-365-email-authentication"></a>驗證結果郵件使用 Office 365 電子郵件驗證標頭欄位
<a name="referenceSPFstamp"> </a>

此表說明的欄位及每個電子郵件的驗證檢查的可能值。
  
|**標頭欄位**|**描述**|
|:-----|:-----|
|spf|說明郵件 SPF 檢查的結果。可能的值包括：<br/>• [**傳遞 （IP 位址）**： 指出傳送之郵件的 SPF] 核取，並包含寄件者的 IP 位址。用戶端有權傳送或轉送代表寄件者的網域的電子郵件。<br/>•**失敗 （IP 位址）**： 指出失敗之郵件的 SPF] 核取，並包含寄件者的 IP 位址。這有時稱為_完全未通過]_。<br/>• **softfail （原因）**： 表示 SPF 記錄已指定主機為不允許傳送，但在轉換。 <br/>•**中性**： 指出的 SPF 記錄已明確指定的無法判斷是否已授權的 IP 位址。 <br/>•**無**： 指出網域沒有 SPF 記錄或 SPF 記錄不會評估為結果。 <br/>• **temperror**： 指出已發生錯誤，可能會暫時的性質，例如的 DNS 錯誤。嘗試再次稍後可能會成功無須執行任何系統管理員的動作。<br/>• **permerror**： 指出永久錯誤發生。會發生這種情況時，例如網域具有格式錯誤的 SPF 記錄。|
|smtp.mailfrom|包含從中傳送郵件的來源網域。任何錯誤是關於此電子郵件將傳送至郵件管理員或網域負責的實體。這有時候會呼叫 5321.MailFrom 反向路徑位址或在郵件信封。|
|dkim|說明郵件 DKIM 檢查的結果。可能的值包括：<br/>• [**傳遞**： 指出 DKIM] 核取傳遞郵件。 <br/>•**失敗 （原因）**： 表示失敗的訊息 DKIM 檢查及為何。例如，如果郵件未簽署或未驗證簽章。<br/>•**無**： 指出郵件未經簽章。這可能有或可能不會指出或 DKIM 記錄不會評估為結果、 僅限此訊息未簽署之網域的 DKIM 記錄。|
|header.d|如果有任何 DKIM 簽章中所識別的網域。這是查詢的公開金鑰的網域。|
|dmarc|說明郵件 DMARC 檢查的結果。可能的值包括：<br/>• [**傳遞**： 指出 DMARC] 核取傳遞郵件。 <br/>•**失敗**： 指出 DMARC] 核取針對失敗的郵件。 <br/>• **bestguesspass**： 指出網域沒有 DMARC TXT 記錄存在，但如果其中有已存在於，就已經過郵件 DMARC 檢查。這是因為 5321.MailFrom 地址的網域符合 5322.From 地址的網域。<br/>•**無**： 表示沒有 DKIM TXT 記錄存在的 DNS 中的傳送端網域。|
|巨集指令|會指出 DMARC 檢查的結果為基礎的垃圾郵件篩選器所採取的動作。例如：<br/>• **permerror**: DMARC 評估期間發生永久錯誤例如遇到錯誤組成的 DMARC TXT 記錄在 DNS 中。嘗試重新傳送此郵件不是可能結尾的不同的結果。但是，您可能需要連絡網域的擁有者以解決問題。<br/>• **temperror**: DMARC 評估期間發生暫時性錯誤。您可以要求寄件者 resend 更新版本才能正確處理的電子郵件訊息。<br/>• **oreject**或**o.reject**： 單獨的覆寫拒絕。在本案例 Office 365 使用此巨集指令收到一則訊息，失敗 DMARC 時檢查其 DMARC TXT 記錄具有 p 之原則的網域從 = 拒絕。刪除或拒絕郵件，而非 Office 365 會將郵件標示為垃圾郵件。為什麼要選擇 Office 365 設定這種方式的詳細資訊，請參閱[輸入電子郵件的失敗 DMARC 如何 Office 365 控點](use-dmarc-to-validate-email.md#inbounddmarcfail)。<br/>• **pct.quarantine**： 表示百分比小於 100%沒有傳遞任何 DMARC 的郵件會繼續傳遞。這表示郵件無法 DMARC 和原則設為 [隔離、 但 pct 欄位不設為 100%且系統隨機決定不要套用的 DMARC 巨集指令，如同指定的網域原則。<br/>• **pct.reject**： 表示百分比小於 100%沒有傳遞任何 DMARC 的郵件會繼續傳遞。這表示郵件無法 DMARC 和原則設為 [拒絕，但 pct 欄位不設為 100%且系統隨機決定不要套用的 DMARC 巨集指令，如同指定的網域原則。|
|header.from|在電子郵件訊息標頭中 From 地址的網域。這有時稱為_5322.From_地址。|
|compauth|複合式驗證結果。使用 Office 365 來結合多種如 SPF、 DKIM、 DMARC 或任何其他組件以決定要驗證郵件訊息的驗證類型。使用 [從： 網域為基礎的評估。|
|變更理由|變更理由複合式驗證通過或失敗。原因的值是由三個數字組成：<br/>• **000**： 郵件明確無法驗證。例如，郵件接收與動作的隔離區] 或 [拒絕 DMARC 失敗。<br/>• **001**： 郵件隱含無法驗證，並傳送端網域並未不發佈驗證原則。例如，p DMARC 原則 = none。<br/>• **1xx**： 郵件傳遞驗證。第二個兩位數是 Office 365 所使用的內部代碼。<br/>• **2xx**： 訊息虛傳遞驗證。第二個兩位數是 Office 365 所使用的內部代碼。<br/>• **3xx**： 複合式驗證已不檢查郵件。 <br/>• **4xx**： 略過複合驗證的郵件。第二個兩位數是 Office 365 所使用的內部代碼。|
