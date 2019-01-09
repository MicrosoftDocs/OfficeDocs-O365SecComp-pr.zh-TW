---
title: Office 365 的反詐騙保護
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/06/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d24bb387-c65d-486e-93e7-06a4f1a436c0
description: 本文說明如何 Office 365 可以降低對網路釣魚攻擊用途是寄件者的網域即詐騙的網域。其完成這同樣藉由分析郵件並封鎖過可驗證 neithe 使用標準的電子郵件的驗證方法或其他寄件者信譽技術 （英文）。這項變更被實減少網路釣魚攻擊的 Office 365 組織公開到數目。
ms.openlocfilehash: 19e7ea957592a486a559dac222a51139bf79b574
ms.sourcegitcommit: 03e64ead7805f3dfa9149252be8606efe50375df
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2019
ms.locfileid: "27769857"
---
# <a name="anti-spoofing-protection-in-office-365"></a>Office 365 的反詐騙保護

本文說明如何 Office 365 可以降低對網路釣魚攻擊用途是寄件者的網域即詐騙的網域。它而言分析郵件並封鎖不會使用標準的電子郵件的驗證方法或其他寄件者信譽技術 （英文） 驗證的錯誤。這項變更被實減少網路釣魚攻擊客戶公開到數目。
  
本文也說明為何此變更進行、 客戶如何準備這項變更、 如何檢視會影響的郵件、 如何報告的郵件、 如何減輕誤判，，以及給 Microsoft 的寄件者應如何準備進行這變更。
  
Microsoft 的反詐騙技術最初已部署給其組織有的 Office 365 企業版 E5 訂閱或鎖購買其訂閱的 Office 365 進階威脅保護 (ATP) 附加元件。年 10 月、 2018年我們已擴充至組織的 Exchange Online Protection (EOP)，以及保護。此外，因此我們篩選的所有了解從彼此的方式，Outlook.com 使用者可能會影響。
  
## <a name="how-spoofing-is-used-in-phishing-attacks"></a>在網路釣魚攻擊的詐騙使用方式

來保護其使用者而言，Microsoft 嚴重採用網路釣魚的威脅。其中一個垃圾郵件和網路釣客常使用的技術在詐騙，這當寄件者為是，及源自從某人或某處以外的實際來源會出現的訊息。這項技術通常用於在網路釣魚活動設計用來取得使用者認證。Microsoft 的反詐騙技術特別檢查的冒名 '從： 標頭' 是 like Outlook 電子郵件用戶端中會顯示一個。當 Microsoft 具有高度信賴的 From： 詐騙標頭，它會識別身分詐騙郵件。
  
詐騙郵件都有真實生活使用者的兩個負面影響：
  
### <a name="1-spoofed-messages-deceive-users"></a>1.詐騙郵件惡作劇使用者
  
首先，詐騙的郵件可能誘騙使用者按下連結及放棄其認證、 下載惡意程式碼、 或回覆有機密內容 （後者都稱為商務電子郵件危害） 的郵件。例如，以下是 msoutlook94@service.outlook.com 的網路釣魚詐騙寄件者訊息：
  
![網路釣魚郵件模擬 service.outlook.com](media/1a441f21-8ef7-41c7-90c0-847272dc5350.jpg)
  
在上述並非真的來自 service.outlook.com，但改用已使其看起來像是它 phisher 詐騙。它會嘗試誘騙使用者按一下訊息中的連結。
  
下一個範例詐騙 contoso.com:
  
![網路釣魚訊息-商業電子郵件危害](media/da15adaa-708b-4e73-8165-482fc9182090.jpg)
  
郵件會尋找合法，但事實上詐騙。此網路釣魚訊息是一種商業電子郵件危害這是網路釣魚之子類別。
    
### <a name="2-users-confuse-real-messages-for-fake-ones"></a>2.使用者將混淆實際假的錯誤訊息
  
第二個、 詐騙郵件建立不確定使用者了解網路釣魚郵件，但無法判斷實際的郵件和詐騙的其中一個之間的差異。例如，以下是密碼的實際重設從 Microsoft 安全性帳戶的電子郵件地址的範例：
  
![Microsoft 合法的密碼重設](media/58a3154f-e83d-4f86-bcfe-ae9e8c87bd37.jpg)
  
上述的郵件沒有來自 Microsoft、 但同時，使用者會用來取得網路釣魚訊息可能誘騙使用者按下連結及放棄其認證、 下載惡意程式碼、 或回覆有機密內容的郵件。因為很難告訴實際密碼重設與 fake 一個之間的差異，許多使用者略過這些訊息、 它們回報為垃圾郵件或整天郵件後向 Microsoft 報告為未接的網路釣魚詐騙。
    
若要停止詐騙、 電子郵件篩選產業已開發[SPF](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)、 [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)及[DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)等的電子郵件驗證通訊協定。DMARC 防止詐騙檢查郵件寄件者層的使用者會看到其電子郵件用戶端中 （在上述範例中，這是 service.outlook.com、 outlook.com，以及 accountprotection.microsoft.com）-與 SPF 或 DKIM 傳遞的網域。也就是使用者看到的網域已驗證與因此未詐騙。如需更完整的討論，請參閱區段"*瞭解為何電子郵件驗證不一定足夠停止詐騙"* 更新版本文件中。 
  
不過，問題是記錄是選擇性的不需要該電子郵件驗證。因此時使用強式驗證原則的網域 like, microsoft.com 和 skype.com 受到來自詐騙網域的所有發佈弱的驗證原則或沒有原則] 是針對正在詐騙的目標。年 3 月 2018年僅 9%Fortune 500 在公司網域的發佈強式電子郵件驗證原則。可能會由 phisher 詐騙其餘 91%和除非電子郵件篩選器會偵測使用其他原則可能會傳遞至使用者欺騙它們：
  
![DMARC 的 Fortune 500 公司的原則](media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)
  
是小型-中等大小公司的比例不在發佈強式電子郵件驗證原則 Fortune 500 為較小、 和小仍 「 北美地區 」 及西歐外的網域。
  
這會是大問題是因為網路釣客企業版可能不知道電子郵件的驗證運作方式，而不要了解並善加利用缺乏。
  
設定 SPF、 DKIM，以及 DMARC 上的資訊，請參閱區段"更新版本文件中*的 Office 365" 的客戶*。 
  
## <a name="stopping-spoofing-with-implicit-email-authentication"></a>停止詐騙隱含的電子郵件的驗證

由於網路釣魚和矛網路釣魚問題，並因強式電子郵件驗證原則限制採用 Microsoft 繼續投資來保護其客戶的功能。因此，Microsoft 事先移動*隱含的電子郵件驗證*-如果網域不會進行驗證，請 Microsoft 會將它視為其有發佈電子郵件的驗證記錄並且將它視為據以如果它不會傳遞。 
  
若要完成這個工作，Microsoft 具有內建許多延伸至一般電子郵件驗證包括寄件者信譽、 寄件者/收件者歷程記錄、 行為上有無分析和其他進階技術 （英文）。寄件者的網域，不會發佈電子郵件的驗證訊息將標記為詐騙除非它包含其他訊號表示是合法。
  
依照此一般使用者可信賴電子郵件傳送給他們不被詐騙、 寄件者可以有信心有空模擬其網域與 Office 365 的客戶可以提供更好防護例如模擬保護。
  
若要查看 Microsoft 的一般宣告，請參閱[海藻的 Phish 第 2 部分-Office 365 中增強的反詐騙](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209)。
  
## <a name="identifying-that-a-message-is-classified-as-spoofed"></a>用於識別郵件被分類當成詐騙

### <a name="composite-authentication"></a>複合式驗證

雖然 SPF、 DKIM，以及 DMARC 本身並都很有用，他們不在事件訊息中有沒有明確驗證記錄通訊足夠的驗證狀態。因此，Microsoft 已經開發將多個信號結合成單一值的簡短呼叫複合式驗證] 或 [compauth 演算法。在 Office 365 的客戶有 compauth 值將郵件標頭中的*驗證結果*標頭上戳記。 
  
```
Authentication-Results:
  compauth=<fail|pass|softpass|none> reason=<yyy>

```

|**CompAuth 結果**|**描述**|
|:-----|:-----|
|失敗|郵件無法明確驗證 （傳送網域發佈記錄明確地在 DNS 中） 或隱含驗證 （傳送網域並未未發行記錄在 DNS 中，因此 Office 365 插結果好像並已發佈的記錄）。|
|傳遞|郵件傳遞明確驗證 （郵件傳遞 DMARC 或[最佳猜測傳遞 DMARC](https://blogs.msdn.microsoft.com/tzink/2015/05/06/what-is-dmarc-bestguesspass-in-office-365)） 或具有高度信賴隱含驗證 （傳送網域未發行電子郵件的驗證記錄，但 Office 365 強式的後端信號指出郵件很有可能合法)。|
|softpass|郵件傳遞隱含的驗證與低-中型信賴 （傳送網域未發行電子郵件的驗證、 但 Office 365 表示郵件合法但接收的訊號強度弱的後端訊號）。|
|無|未先驗證訊息] （或其未進行驗證，但沒有對齊） 但因為寄件者信譽或其他因素而不會套用複合驗證。|
   
|||
|:-----|:-----|
|**原因**|**描述**|
|0xx|郵件無法複合式驗證。<br/>**000**表示郵件無法 DMARC 與拒絕或隔離區的動作。                   -001 表示郵件無法隱含的電子郵件的驗證。這表示的傳送端網域沒有電子郵件驗證記錄發佈，或如果初採取了幾，他們有弱的失敗原則 (SPF 軟體失敗或 neutral、 DMARC 原則的 p = none)。<br/>**002**表示組織有組明確禁止傳送詐騙的電子郵件的寄件者/網域的原則，以系統管理員手動設定此設定。  <br/>**010**表示郵件無法拒絕或隔離的動作與 DMARC 及傳送端網域是其中一個貴組織的公認的網域 (這是以自我自我或組織內部的一部分詐騙)。  <br/>**011**表示郵件無法隱含的電子郵件驗證及傳送端網域是其中一個貴組織的公認的網域 (這是以自我自我或組織內部的一部分詐騙)。|
|所有其他代碼 （1xx、 2xx、 3xx、 4xx、 5xx）|將郵件傳遞隱含驗證或有無驗證但採取任何動作所套用的原因會對應到的各種內部代碼。|
   
透過查看之郵件標頭，系統管理員或甚至是使用者可以決定如何 Office 365 抵達寄件者可能詐騙結論。
  
### <a name="differentiating-between-different-types-of-spoofing"></a>區別不同類型的詐騙

Microsoft 區分兩種不同類型的詐騙郵件：
  
 **內 org 詐騙**
  
也稱為自我-自我詐騙、 發生此情況時在 [從網域： 地址相同，或是配合收件者的網域 （如果收件者的網域是其中一個貴組織的[公認的網域](https://technet.microsoft.com/en-us/library/jj945194%28v=exchg.150%29.aspx)）;或時在 [從網域： 地址屬於相同組織。
  
例如，下列寄件者和收件者從具有相同的網域 (contoso.com)。空格插入可防止 spambot 蒐集此頁面上的電子郵件地址）：
  
從： 寄件者 @ contoso.com
  
： 收件者 @ contoso.com
  
下列具有與組織的網域 (fabrikam.com) 對齊寄件者和收件者的網域：
  
從： 寄件者 foo.fabrikam.com @
  
： 收件者 bar.fabrikam.com @
  
下列寄件者和收件者的網域皆不同 （microsoft.com 和 bing.com），但他們屬於相同組織 （亦即同時是組織的公認的網域的一部分）：
  
從： 寄件者 @ microsoft.com
  
： 收件者 bing.com @
  
失敗內 org 詐騙的郵件包含標頭中的下列值：
  
X Forefront-反垃圾郵件報告：...]CAT:SPM/HSPM/PHSH;...]SFTY:9.11
  
CAT is 之郵件的類別和通常為 SPM （垃圾郵件） 上戳記但有時可能是 HSPM （高信賴垃圾郵件） 或 PHISH （網路釣魚） 取決於哪些其他類型的模式發生訊息中。
  
SFTY 是之郵件的安全層級、 第一個數字 (9) 表示郵件是網路釣魚，而第二組的數字之後點 (11) 表示它是內 org 詐騙。
  
沒有特定原因程式碼內 org 詐騙、 的複合會加上戳記 2018 （尚未定義時間表） 後述的驗證。
  
 **跨網域詐騙**
  
發生此動作時的傳送端網域中寄： 地址是接收組織外部的網域。由於跨網域詐騙失敗複合式驗證的郵件包含標頭中的下列值：
  
驗證結果:...compauth = 失敗原因 = 000/001
  
X Forefront-反垃圾郵件報告：...]CAT:SPOOF;...]SFTY:9.22
  
在這兩種情況下，下列的紅色 safety 提示會加上戳記郵件，或對等資格專為收件者的信箱語言：
  
![紅色 safety 提示-詐騙的偵測](media/a366156a-14e8-4c14-bfe5-2031b21936f8.jpg)
  
僅使用查看 From： 地址和了解收件者電子郵件的功能，或依照檢查，就能區分內 org 及跨網域詐騙的電子郵件標頭。
  
## <a name="how-customers-of-office-365-can-prepare-themselves-for-the-new-anti-spoofing-protection"></a>如何 Office 365 的客戶可以準備自己的新反詐騙保護

### <a name="information-for-administrators"></a>系統管理員的資訊

在 Office 365 組織的系統管理員身分有您應該要知道的資訊的數個重要部分。
  
### <a name="understanding-why-email-authentication-is-not-always-enough-to-stop-spoofing"></a>了解為何電子郵件驗證不一定足夠停止詐騙

新的反詐騙保護依賴 （SPF、 DKIM、 和 DMARC） 不標示郵件為詐騙的電子郵件驗證。傳送端網域具有永遠不會發佈 SPF 記錄時的一般的範例。如果不有任何 SPF 記錄或他們不正確地設定，已傳送的訊息將標記為詐騙除非 Microsoft 有指出郵件是合法的後端智慧。
  
例如前反-詐騙正在部署、 訊息可能看起來不 SPF 記錄、 沒有 DKIM 的記錄，與沒有 DMARC 記錄下列： 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```
之後反詐騙如果您有 Office 365 企業版 E5、 EOP 或 ATP、 compauth 值會加上戳記：
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com; compauth=fail reason=001
From: sender @ example.com
To: receiver @ contoso.com

```

如果 example.com 修正此設定 SPF 記錄，但不是 DKIM 記錄，這會因為傳遞 SPF 網域對齊在從網域傳遞複合式驗證： 地址： 
  
```
Authentication-Results: spf=pass (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

或者，如果它們設定 DKIM 記錄，但不是 SPF 記錄，這會也存取複合式驗證因為傳遞 DKIM 簽章的網域對齊在從網域： 地址： 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.example.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

不過，phisher 可能也設定 SPF 和 DKIM 和登入他們自己的網域的郵件但指定不同網域中寄： 地址。SPF 皆 DKIM 需要以符合在 [從網域的網域： 處理，因此除非 example.com 發佈 DMARC 記錄，這就不會標示為使用 DMARC 詐騙： 
  
```
Authentication-Results: spf=pass (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```

在電子郵件用戶端 (Outlook web 或任何其他電子郵件用戶端上的 Outlook)、 僅限 From： 顯示網域、 不在 SPF 或 DKIM，且網域可以將思考郵件是來自 example.com，但實際上是來自 maliciousDomain.com 誤導使用者.
  
![已驗證的訊息但從： 網域未對齊什麼傳遞 SPF 或 DKIM](media/a9b5ab2a-dfd3-47c6-8ee8-e3dab2fae528.jpg)
  
有該原因 Office 365 需要的來源中的網域： 地址對齊 SPF 或 DKIM 簽署] 中的網域和它不會，包含一些其他內部信號表示郵件是否合法。否則，訊息就是 compauth 失敗。 
  
```
Authentication-Results: spf=none (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: sender@contoso.com
To: someone@example.com
```

即得出 Office 365 反詐騙會保護對網域無驗證] 並針對設定驗證但不符針對在 [從網域的網域： 地址，也就是一個使用者會看到與認為是郵件的寄件者。這是都可以在您的組織外部的網域以及在組織內的網域，則為 true。
  
因此，如果您曾經收到郵件複合式驗證失敗且標記為詐騙，即使郵件傳遞 SPF 和 DKIM，它會是因為在 [從網域不符合傳遞 SPF 和 DKIM 的網域： 地址。
  
### <a name="understanding-changes-in-how-spoofed-emails-are-treated"></a>了解如何詐騙的電子郵件中的變更被視為

目前所有組織中 Office 365-ATP 和非 ATP-訊息以拒絕或隔離原則 DMARC 都會標記為垃圾郵件和通常需要高信賴垃圾郵件動作，或有時正常的垃圾郵件動作，無法 (根據其他垃圾郵件規則先其識別為垃圾郵件）。內 org 詐騙的偵測採取正常的垃圾郵件。若要啟用，不需要此表現方式也不可以加以停用。
  
不過的跨網域詐騙郵件這項變更之前就會經歷正常的垃圾郵件、 phish、 及惡意程式碼檢查且篩選條件的其他組件會被識別其為可疑，如果將它們分別標示為垃圾郵件、 phish、 或惡意程式碼。使用新的跨網域詐騙的保護，無法驗證任何訊息將，根據預設，採取的動作中反網路釣魚定義\>反詐騙的原則。未定義一個項目，則它要移至使用者的垃圾郵件] 資料夾。在某些情況下，更可疑郵件同時也會新增至訊息的紅色 safety 提示。
  
這可能會導致某些先前已標記為垃圾郵件仍快速標示為垃圾郵件，但現在也必須為紅色 safety 提示; 的郵件在其他情況下，新增先前已標記為非垃圾郵件會在啟動快速標示為垃圾郵件 (CAT:SPOOF) 以紅色 safety 提示的郵件。在仍其他情況下，已移動所有垃圾郵件與 phish 至隔離區的客戶就會立即看見他們路垃圾郵件資料夾 （此表現方式可以變更，請參閱[變更您的反詐騙設定](#changing-your-anti-spoofing-settings)）。
  
有多個不同的方式可以 （請參閱本文稍早的[不同類型詐騙之間 Differentiating](#differentiating-between-different-types-of-spoofing) ） 詐騙一則訊息，但年 3 月 2018 Office 365 來說這些訊息的方式不尚未整合。下表是快速摘要，與跨網域詐騙保護正在新的行為： 
  
|**詐騙的類型**|**類別**|**新增安全性提示？**|**適用於**|
|:-----|:-----|:-----|:-----|
|DMARC 失敗 （隔離或拒絕）  <br/> |HSPM （預設值），也可能 SPM 或 PHSH  <br/> |否 （尚未）  <br/> |所有的 Office 365 客戶、 Outlook.com  <br/> |
|自我-自我  <br/> |SPM  <br/> |是  <br/> |所有的 Office 365 組織、 Outlook.com  <br/> |
|跨網域  <br/> |詐騙  <br/> |是  <br/> |Office 365 進階威脅保護和 E5 客戶  <br/> |
   
### <a name="changing-your-anti-spoofing-settings"></a>變更您的反詐騙設定

若要建立或更新您 （跨網域） 反詐騙設定，請瀏覽至 [反網路釣魚\>之下 Threat Management 反詐騙設定\>安全性原則] 索引標籤&amp;規範中心。如果您先前已建立任何反網路釣魚設定，您必須建立 web 應用程式：
  
![反網路釣魚-建立新的原則](media/9337ec91-270e-4fa7-9dfa-a51a2d1eb95e.jpg)
  
如果您已經建立一個，您可以選取要修改其：
  
![反網路釣魚-修改現有的原則](media/75457a7c-882e-4984-80d1-21a12b42c53a.jpg)
  
選取您剛建立的原則和上所述的步驟繼續[了解更多關於詐騙智慧。](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf)
  
![啟用或停用 antispoofing](media/c49e2147-c954-443c-9144-1cbd139e1166.jpg)
  
![啟用或停用 antispoofing safety 祕訣](media/eec7c407-31fc-4f73-8325-307d82d1fb53.jpg)
  
若要建立新的原則透過 PowerShell： 
  
```
$org = Get-OrganizationConfig
$name = "My first anti-phishing policy for " + $org.Name
# Note: The name should not exclude 64 characters, including spaces.
# If it does, you will need to pick a smaller name.
# Next, create a new anti-phishing policy with the default values
New-AntiphishPolicy -Name $Name
# Select the domains to scope it to
# Multiple domains are specified in a comma-separated list
$domains = "domain1.com, domain2.com, domain3.com"
# Next, create the anti-phishing rule, scope it to the anti-phishing rule
New-AntiphishRule -Name $name -AntiphishPolicy $name -RecipientDomainIs $domains
```

然後您可能會修改使用 PowerShell 中追蹤的文件[組 AntiphishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy?view=exchange-ps)在反網路釣魚原則參數。您可以指定 $name 做為參數：
  
```
Set-AntiphishPolicy -Identity $name <fill in rest of parameters>
```

後面的 2018，而不是您不必建立的預設原則，其中會為您建立可讓您不需要以手動方式指定範圍設為在組織中的所有收件者 （下列螢幕擷取畫面如有變更恕前的最後一個實作）。
  
![反網路釣魚的預設原則](media/1f27a0bf-e202-4e12-bbac-24baf013c8f9.jpg)
  
不同於您建立的原則，您無法刪除預設原則、 修改其優先順序，或選擇範圍以哪一個使用者、 網域或群組。
  
![反網路釣魚預設原則的詳細資訊](media/30c21ceb-df52-4c93-aa65-f44a55dc1009.jpg)
  
若要設定預設保護您透過 PowerShell：
  
```
$defaultAntiphishPolicy = Get-AntiphishPolicy | ? {$_.IsDefault -eq $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement <$true|$false>
```

您應該僅停用反詐騙保護如果您有其他郵件伺服器或伺服器在 Office 365 前方 （請參閱合法情況來停用反詐騙如需詳細資訊）。 
  
```
$defaultAntiphishPolicy = Get-AntiphishiPolicy | ? {$_.IsDefault $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement $false 

```
> [!IMPORTANT]
> 如果您的電子郵件路徑中的第一個躍點是 Office 365 與您所取得太多標示為詐騙的合法電子郵件，您應該先設定您可以將詐騙的電子郵件傳送至您的網域的寄件者 （請參閱節 *"管理合法寄件者所傳送 unauthenticated 電子郵件"* )。如果您仍會取得太多誤判 （例如合法標示為詐騙郵件），不建議完全停用反詐騙保護。而是建議您選擇 [基本而不高保護。                   最好是透過誤判比以公開其無法最後的長期意大幅較高成本詐騙電子郵件組織運作。

### <a name="managing-legitimate-senders-who-are-sending-unauthenticated-email"></a>管理合法的寄件者所傳送未經過驗證的電子郵件

持續誰會將未經過驗證的電子郵件傳送至您的組織追蹤的 office 365。如果服務認為不合法寄件者，它會將其標示為*compauth*失敗。這將會歸類為詐騙雖然它取決於您反詐騙的原則套用至郵件。 
  
不過，以系統管理員身分，您可以指定哪些寄件者會允許傳送詐騙的電子郵件、 覆寫 Office 365 的決策。
  
**1-如果您的組織擁有的網域設定電子郵件的驗證方法**
  
此方法可用來解析內 org 詐騙、 及跨網域詐騙在您擁有或互動的情況下使用多個承租人。它也可協助解決跨網域詐騙其中您傳送至其他 Office 365 中的客戶及也都架設在其他提供者的第三方。
  
如需詳細資訊，請參閱[Office 365 的客戶](#customers-of-office-365)。 
 
**方法 2-使用詐騙智慧設定允許寄件者的未經過驗證的電子郵件**
  
您也可以使用[詐騙智慧](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf)允許寄件者未經過驗證的郵件傳輸至您的組織。 
  
針對外部網域詐騙的使用者是從地址的網域的傳送端 IP 位址傳送基礎結構時 (分成/24 CIDR 範圍)，或組織的網域的 PTR 記錄 （在以下的螢幕擷取畫面，傳送端 IP 可能是的 131.107.18.4 的 PTR 記錄是 outbound.mail.protection.outlook.com，而且這會顯示為傳送基礎結構的 outlook.com。）
  
若要允許此傳送未經過驗證的電子郵件的寄件者，變更**否]** 為 **[是]**。
  
![設定 antispoofing 允許寄件者](media/d4334921-d820-4334-8217-788279701e94.jpg)
  
您也可以使用 PowerShell 允許特定寄件者詐騙網域： 
  
```
$file = "C:\My Documents\Summary Spoofed Internal Domains and Senders.csv"
```

```
Get-PhishFilterPolicy -Detailed -SpoofAllowBlockList -SpoofType External | Export-CSV $file
```

![快速詐騙的寄件者透過 Powershell](media/0e27ffcf-a5db-4c43-a19b-fa62326d5118.jpg)
  
在上一個影像中，進行此螢幕擷取畫面配合，但實際上所有的值就會出現在單一行上已經新增額外的分行符號。
  
編輯檔案看起來會對應至 outlook.com 和 bing.com、 線條和 AllowedToSpoof 項目變更從 [否] 為 [是]：
  
![設定詐騙允許為 [是] 透過 Powershell](media/62340452-62d3-4958-9ce9-afe5275a870d.jpg)
  
儲存檔案，然後執行： 
  
```
$UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
```

這將會立即允許傳送未經過驗證的電子郵件從 bing.com \*。 outlook.com。

**方法 3-建立寄件者/收件者對允許項目**
  
您也可以選擇略過所有的垃圾郵件篩選特定的寄件者。如需詳細資訊，請參閱 ＜[如何將安全地新增至 Office 365 中的 [允許] 清單的寄件者](https://blogs.msdn.microsoft.com/tzink/2017/11/29/how-to-securely-add-a-sender-to-an-allow-list-in-office-365/)。
  
如果您使用此方法，則會略過垃圾郵件與部分 phish 篩選，但卻不惡意程式碼篩選。
  
**方法 4-連絡寄件者，他設定電子郵件的驗證**
  
垃圾郵件和網路釣魚的問題，因為 Microsoft 建議設定電子郵件驗證所有寄件者。如果您知道的傳送端網域管理員，請連絡它們與這些設定電子郵件驗證記錄，所以您不需要加任何覆寫的要求。如需詳細資訊，請參閱 ＜[系統管理員的網域，是不是 Office 365 客戶](#administrators-of-domains-that-are-not-office-365-customers)"本文稍後的。 
  
時可能會很難在先取得傳送驗證的網域，一段時間，以更電子郵件篩選器啟動 junking 或甚至拒絕的電子郵件，它會使它們設定適當的記錄，以確保較佳的傳遞。
  
### <a name="viewing-reports-of-how-many-messages-were-marked-as-spoofed"></a>檢視報告多少郵件已標示成詐騙

啟用您反詐騙的原則後，您可以使用威脅智慧周圍多少訊息將標記為 phish 取得數字。若要這樣做，請移至 [安全性]&amp;規範中心 (SCC) 底下 Threat Management\>總管]、 [檢視設定 Phish、 和群組的寄件者的網域] 或 [保護狀態：
  
![檢視多少訊息將標記為 phish](media/de25009a-44d4-4c5f-94ba-9c75cd9c64b3.jpg)
  
您可以查看多少已標示為網路釣魚，包括郵件標示為詐騙各種不同的報告與互動。若要深入了解，請參閱[Office 365 威脅智慧快速入門](https://support.office.com/article/get-started-with-office-365-threat-intelligence-38e9b67f-d188-490f-bc91-a1ae4b270441)。
  
您不能尚未分割出其郵件已標示為因為詐騙相對於其他類型的網路釣魚 （一般網路釣魚、 網域或使用者模擬等等）。不過，稍後的 2018，您將能夠執行這項作業透過安全性&amp;規範中心。之後，您可以使用開始進行此報告來識別可能是合法的要標示為因失敗的驗證詐騙的傳送端網域。
  
下列螢幕擷取畫面會針對此資料的外觀相同，但發行時可能會變更提案：
  
![檢視網路釣魚報表所偵測類型](media/dd25d63f-152c-4c55-a07b-184ecda2de81.jpg)
  
非 ATP 及 E5 客戶，這些報告會提供更新版本中的威脅保護狀態 (TPS) 報告] 下的 2018年但是將至少 24 小時的延遲。此頁面會在更新功能整合安全性&amp;規範中心。
  
### <a name="predicting-how-many-messages-will-be-marked-as-spoof"></a>預測多少訊息將標記為詐騙

稍後的 2018、 Office 365 一次更新其設定可讓您關閉反詐騙強制執行，或上具有 [基本] 或 [高強制執行，您將獲得查看如何在各種設定變更郵件處理的能力。也就是反詐騙已關閉，如果您將能看到多少訊息將會視為詐騙 basic ； 如果或者，如果是 Basic，您將能看到多少的詳細訊息將會視為詐騙若您開啟以高。
  
此功能目前的狀態下開發。當所定義的詳細資訊，與螢幕擷取畫面的安全性和規範中心及以 PowerShell 範例將會更新此頁面。
  
!["怎麼辦"啟用 antispoofing 的報表](media/fdd085ae-02c1-4327-a063-bfe9a32ff1eb.jpg)
  
![可能 UX 的允許詐騙的寄件者](media/53f9f73e-fb01-47f3-9a6d-850c1aef5efe.jpg)
  
### <a name="understanding-how-spam-phishing-and-advanced-phishing-detections-are-combined"></a>了解如何垃圾郵件、 網路釣魚及進階網路釣魚結合偵測

使用或不 ATP，使用 Exchange Online 的組織可以指定服務識別為惡意程式碼、 垃圾郵件、 高信賴垃圾郵件、 網路釣魚、 及大量郵件時要採取的動作。ATP 客戶 ATP 反網路釣魚原則和 EOP 客戶的反網路釣魚原則與訊息可能會瀏覽多種偵測類型 （例如惡意程式碼、 網路釣魚、 與使用者模擬） 事實，可能是一些不確定其原則可套用。 
  
一般而言，CAT （類別） 屬性中的 X Forefront-反垃圾郵件報告標頭中所識別套用至郵件的原則。 
  
|**Priority (優先順序)**|**原則**|**類別**|**其中 managed？**|**適用於**|
|:-----|:-----|:-----|:-----|:-----|
|1  <br/> |惡意程式碼  <br/> |MALW  <br/> |[惡意程式碼原則](https://technet.microsoft.com/en-us/library/jj200745%28v=exchg.150%29.aspx) <br/> |所有組織  <br/> |
|2  <br/> |網路釣魚  <br/> |PHSH  <br/> |[主控的內容篩選原則](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |所有組織  <br/> |
|3  <br/> |高度信賴垃圾郵件  <br/> |HSPM  <br/> |[主控的內容篩選原則](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |所有組織  <br/> |
|4  <br/> |詐騙  <br/> |詐騙  <br/> |[反網路釣魚原則](https://go.microsoft.com/fwlink/?linkid=864553)、[詐騙智慧](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf) <br/> |所有組織  <br/> |
|5  <br/> |垃圾郵件  <br/> |SPM  <br/> |[主控的內容篩選原則](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |所有組織  <br/> |
|6  <br/> |大量  <br/> |大量  <br/> |[主控的內容篩選原則](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |所有組織  <br/> |
|7  <br/> |網域模擬  <br/> |DIMP  <br/> |[反網路釣魚原則](https://go.microsoft.com/fwlink/?linkid=864553) <br/> |僅限具有 ATP 組織  <br/> |
|8  <br/> |使用者模擬  <br/> |UIMP  <br/> |[反網路釣魚原則](https://go.microsoft.com/fwlink/?linkid=864553) <br/> |僅限具有 ATP 組織 <br/> |
   
如果您有多個不同的反網路釣魚原則，將套用一個在最高優先順序。例如，假設您有兩個原則：
  
|**原則**|**Priority (優先順序)**|**使用者/網域模擬**|**反詐騙**|
|:-----|:-----|:-----|:-----|
|A  <br/> |1  <br/> |On  <br/> |Off  <br/> |
|B  <br/> |2  <br/> |Off  <br/> |On  <br/> |
   
如果訊息有和識別身分詐騙與使用者模擬與相同的一組使用者範圍的原則及原則 B 則郵件會被視為詐騙但採取任何動作套用自反詐騙已關閉並詐騙執行在較高的優先順序 (4) 與使用者模擬 (8)。
  
若要讓其他類型的網路釣魚原則套用，您將需要調整的各種原則套用至人員設定。
  
### <a name="legitimate-scenarios-to-disable-anti-spoofing"></a>若要停用反詐騙的合法案例

反詐騙更妥善地保護從網路釣魚攻擊的客戶與因此停用反詐騙保護不鼓勵。藉由停用它，就可能會解決某些短期誤判，但長期您將會公開給更大的風險。設定驗證寄件者兩側或網路釣魚原則中進行調整的成本通常是單次事件或是需要僅限最小、 定期維護。不過，其中具有已公開的資料、 網路釣魚攻擊復原成本或資產已危害是更高。
  
此原因，最好是透過反詐騙誤判比若要停用反詐騙保護運作。
  
但是，有其中反詐騙應停用，而這是有其他郵件篩選的合法案例中的郵件路由、 與 Office 365 產品不是電子郵件路徑中的第一個躍點：
  
![客戶 MX 記錄未指向 Office 365](media/62127c16-cfb8-4880-9cad-3c12d827c67e.jpg)
  
Exchange 內部部署郵件伺服器，篩選裝置 Ironport，例如郵件或其他雲端託管服務可能是另一部伺服器。
  
如果收件者的網域的 MX 記錄未指向 Office 365，然後有不需要在停用反詐騙因為 Office 365 查詢接收網域的 MX 記錄並隱藏反詐騙如果其指向另一個服務。如果您不知道您的網域是否在前端具有記憶體另一部伺服器，您可以使用 MX 工具箱類似的網站来查詢的 MX 記錄。它可能之後類似以下的某個項目：
  
![MX 記錄會指出網域未指向 Office 365](media/d868bb9f-3462-49aa-baea-9447a3ce4877.jpg)
  
此網域都未指向 Office 365 讓 Office 365 不會套用反詐騙強制執行的 MX 記錄。
  
不過，如果*沒有*的收件者的網域的 MX 記錄指向 Office 365 中，即使在 Office 365 前方的另一個服務，然後您應該停用反詐騙。最常見的範例是透過收件者修正： 
  
![收件者修正路由圖表](media/070d90d1-50a0-42e4-9fd3-920bc99a7cad.jpg)
  
網域 contoso.com 的 MX 記錄指向內部部署伺服器上，當網域 @office365.contoso.net MX 記錄指向 Office 365 因為包含\*。 protection.outlook.com，或\*。 eo.outlook.com MX 記錄中的：
  
![MX 記錄指向 Office 365，因此可能收件者修正](media/4101ad51-ef92-4907-b466-b41d14d344ca.jpg)
  
請務必區分及它上有收件者修正時的收件者的網域的 MX 記錄未指向 Office 365。請務必告知下列兩種情況下之間的差異。
  
如果您不確定接收網域上有收件者修正，有時您可以分清 \\servername\share\spbr 郵件標頭。
  
） 首先，查看的驗證結果標頭中的收件者的網域的郵件標頭： 
  
```
Authentication-Results: spf=fail (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; office365.contoso.net; dkim=fail
  (body hash did not verify) header.d=simple.example.com;
  office365.contoso.net; dmarc=none action=none
  header.from=example.com; compauth=fail reason=001
```

收件者的網域是粗體紅色的文字上方，在此案例的 office365.contoso.net 中找到。這可能是不同的 [收件者在收件者： 標頭：
  
： 範例收件者\<@ contoso.com 收件者\>
  
執行實際收件者的網域的 MX 記錄查閱。如果它包含\*。 protection.outlook.com、 mail.messaging.microsoft.com、 \*。 eo.outlook.com 或 mail.global.frontbridge.com，這表示 MX 點至 Office 365。
  
如果它不包含這些值，就表示 MX 未指向 Office 365。您可以使用來確認這項工具是 MX 工具箱]。
  
針對特定本例中為下列指出該 contoso.com，因為它是 [收件者起來收件者的網域： 標頭] 有 MX 記錄指向在 prem 伺服器：
  
![MX 記錄指向在 prem 伺服器](media/2444144a-9a90-4319-96b2-d115041f669f.jpg)
  
不過，實際的收件者是的 office365.contoso.net 其 MX 記錄未指向 Office 365：
  
![MX 點至 Office 365 必須收件者修正](media/10cf3245-9b50-475a-b655-d8a51f99d812.jpg)
  
因此，此訊息可能上有收件者修正。
  
b） 第二，請務必區分的收件者將一般使用案例。若要修正的收件者網域\*。 onmicrosoft.com，但是修正其\*。 mail.onmicrosoft.com。
  
一旦您識別背後的另一部伺服器路由傳送的最後一個收件者網域和收件者的網域的 MX 記錄實際指向 Office 365 （如其 DNS 記錄中發佈），您可能會繼續停用反詐騙。
  
請記住，您不需要若停用反詐騙網域的路由路徑中的第一個躍點是 Office 365、 僅限時，它會背後的一或多個服務。
  
### <a name="how-to-disable-anti-spoofing"></a>如何停用反詐騙

如果您已建立反網路釣魚原則，將 $false EnableAntispoofEnforcement 參數： 
  
```
$name = "<name of policy>"
Set-AntiphishPolicy -Identity $name -EnableAntiSpoofEnforcement $false 

```

如果您不知道要停用的原則 （或原則） 的名稱，您可以將其顯示： 
  
```
Get-AntiphishPolicy | fl Name
```

如果您沒有任何現有的反網路釣魚原則，您可以建立 web 應用程式並再加以停用 （即使您不需要將原則、 反詐騙仍套用 ； 在 2018年後面上、 將為您建立的預設原則且可以然後停用，而不是建立一個）.您必須在多個步驟中執行這項作業： 
  
```
$org = Get-OrganizationConfig
$name = "My first anti-phishing policy for " + $org.Name
# Note: If the name is more than 64 characters, you will need to choose a smaller one
```

```
# Next, create a new anti-phishing policy with the default values
New-AntiphishPolicy -Name $Name
# Select the domains to scope it to
# Multiple domains are specified in a comma-separated list
$domains = "domain1.com, domain2.com, domain3.com"
# Next, create the anti-phishing rule, scope it to the anti-phishing rule
New-AntiphishRule -Name $name -AntiphishPolicy -RecipientDomainIs $domains
# Finally, scope the antiphishing policy to the domains
Set-AntiphishPolicy -Identity $name -EnableAntispoofEnforcement $false 

```

停用反詐騙只有透過指令程式 (在 Q2 2018 稍後才會出現 [安全性]&amp;規範中心)。如果您沒有 PowerShell 存取、 建立支援票證。
  
請記住，這應僅套用至、 經歷間接路由傳送至 Office 365 時的網域。抵禦因一些誤判停用反詐騙誘惑、 就較好的作法長期透過其運作。
  
### <a name="information-for-individual-users"></a>針對個別使用者的資訊

個別使用者限制在他們可以互動的反詐騙 safety 提示。但是，有幾個的部分要怎麼做才能解決常見的案例。
  
### <a name="common-scenario-1---mailbox-forwarding"></a>常見案例 #1-信箱轉寄

如果您使用其他電子郵件服務，將您的電子郵件轉寄至 Office 365 或 Outlook.com 的電子郵件可能會標示為詐騙及接收紅色 safety 提示。Office 365 和 Outlook.com 規劃地址這自動轉寄時 Outlook.com、 Office 365、 Gmail 或任何其他使用[弧線通訊協定](https://arc-spec.org)的服務之一。不過，部署該修正，直到使用者應使用連線帳戶功能匯入其訊息直接，而不是使用 [轉接] 選項。
  
若要設定 Office 365 的連線的帳戶，選取 [齒輪圖示的右上角的 Office 365 web 介面\>郵件\>郵件\>帳戶\>連線的帳戶。
  
![Office 365-連線帳戶選項](media/e8e841ca-8861-4d83-8506-2a0858c51010.jpg)
  
在 Outlook.com、 程序是齒輪圖示\>選項\>郵件\>帳戶\>連線的帳戶。
  
### <a name="common-scenario-2---discussion-lists"></a>常見案例 #2-討論區清單

討論區清單已知有問題反-詐騙方式因為它們轉寄郵件和修改其內容仍保留從原始： 地址。
  
例如，假設您的電子郵件地址為 user @ contoso.com，而且您感興趣的小鳥監控以及加入討論區清單 birdwatchers，@ example.com。當您將訊息傳送至討論區清單時，您可能會傳送這種方式：
  
**從：** John Doe \<@ contoso.com 的使用者\> 
  
**至：** Birdwatcher 的討論區清單\<birdwatchers @ example.com\> 
  
**Subject:** 更好的檢視周 Rainier 頂端的藍色 jays 本週 
  
任何人都要取出檢視從周 Rainier 本週吗？
  
當電子郵件清單接收郵件時，他們格式化郵件、 修改其內容和重播其餘部分的這由組成參與者從許多不同的電子郵件接收器討論區清單的成員。
  
**從：** John Doe \<@ contoso.com 的使用者\> 
  
**至：** Birdwatcher 的討論區清單\<birdwatchers @ example.com\> 
  
**Subject:**[BIRDWATCHERS]更好的檢視周 Rainier 頂端的藍色 jays 本週 
  
任何人都要取出檢視從周 Rainier 本週吗？
  
---
  
此訊息傳送至 Birdwatchers 討論區清單。您可以隨時取消訂閱。
  
在上述重新執行的郵件已從相同： 已將標籤新增至主旨行及訊息的底部頁尾修改地址 （使用者 @ contoso.com），但原始郵件。這種類型的郵件修改常見郵寄清單中，且可能會導致誤判。
  
如果您或組織中某人郵寄清單的管理員，您可以將它設定成通過反詐騙檢查。
  
- 檢查在 DMARC.org 常見問題集：[我操作郵寄清單與我想要與 DMARC 交互操作，該怎麼辦？](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F)
    
- 閱讀此部落格文章 /kb/2261507/zh-tw 中的指示：[可避免失敗 DMARC 與交互操作郵寄清單運算子的提示](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/)
    
- 請考慮支援弧線，請參閱郵寄清單伺服器上安裝更新[https://arc-spec.org](https://arc-spec.org/)
    
如果您沒有郵寄清單的擁有權：
  
- 您可以要求之郵寄清單維護程式實作其中一個選項上述 （他們也應該有設定郵寄清單來自網域的電子郵件驗證）
    
- 您可以在您的電子郵件用戶端若要將郵件移至收件匣中建立信箱規則。您也可以要求您組織的系統管理員可以設定允許規則或一節中討論覆寫做為管理合法寄件者所傳送未經過驗證的電子郵件
    
- 您可以建立 Office 365 來建立以將它視為合法郵寄清單覆寫支援票證
    
### <a name="other-scenarios"></a>其他案例

1. 若上述的常見案例的情況現況，郵件為 false 的正數後向 Microsoft 報告。如需詳細資訊，請參閱區段[方式可以我回報垃圾郵件或非垃圾郵件訊息給 Microsoft？](#how-can-i-report-spam-or-non-spam-messages-back-to-microsoft)在本文後面。 
    
2. 您也可以連絡電子郵件管理員可以引發為與 Microsoft 支援票證。Microsoft 工程小組會調查郵件已標示為詐騙的原因。
    
3. 此外，如果您知道有寄件者是及健全他們不被惡意詐騙，您可能會回覆回到表示他們會從未驗證的郵件伺服器傳送郵件寄件者。這有時候會導致連絡設定必要的電子郵件驗證記錄，將其 IT 系統管理員的原始寄件者。
  
當足夠的寄件者回覆回網域擁有者所應設定電子郵件的驗證記錄時，它 spurs 它們到採取動作。雖然 Microsoft 也適用於具有網域擁有者發佈所需的記錄，它可協助更為個別使用者要求時才。
    
4. （選用） 將寄件者新增至安全的寄件者清單。不過，請注意如果 phisher 假裝該帳戶，它會傳遞至您的信箱。因此，應謹慎使用此選項。
    
## <a name="how-senders-to-microsoft-should-prepare-for-anti-spoofing-protection"></a>給 Microsoft 的寄件者應如何準備反詐騙保護

如果您是系統管理員目前將郵件傳送至 Microsoft Office 365 或 Outlook.com 中，您必須確定已正確地驗證您的電子郵件為垃圾郵件或 phish 否則可能會標示為。 
  
### <a name="customers-of-office-365"></a>Office 365 的客戶

如果您是 Office 365 客戶與您使用 Office 365 傳送輸出電子郵件：
  
- 為您[設定 SPF 避免詐騙的 Office 365 中](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)的網域
    
- 主要網域，[使用 DKIM 驗證從您在 Office 365 中的自訂網域傳送的輸出電子郵件](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)
    
- [請考慮 DMARC 記錄設定](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)為您的網域來判斷誰合法的寄件者 
    
Microsoft 不提供每個 SPF、 DKIM，以及 DMARC 詳細的實作指導方針。但是，有許多的線上發佈的資訊。也有 3rd 廠商公司專用協助組織設定電子郵件的驗證記錄。
  
### <a name="administrators-of-domains-that-are-not-office-365-customers"></a>系統管理員的不是 Office 365 客戶的網域

如果您是網域系統管理員，但不是 Office 365 客戶：
  
- 您應該將發佈您的網域傳送的 IP 位址設定 SPF and 也 set up DKIM （如果有的話） 來數位簽署的郵件。您也可能會考慮 DMARC 記錄設定。
    
- 如果您有大量寄件者傳輸代替您撥打電話的電子郵件，您應該進行處理的方式傳送電子郵件如此來源中的傳送端網域： 地址 （如果它是屬於您） 配合通過 SPF 或 DMARC 的網域。
    
- 如果您有內部部署郵件伺服器，或傳送軟體為-a-服務提供者或從雲端主控像 Microsoft Azure、 機構 GoDaddy、 Rackspace、 Amazon Web 服務、 服務或類似，您應該確定他們已新增至 SPF 記錄。
    
- 如果您是主控的 ISP 小型網域，您應設定的指示 SPF 記錄您的 ISP 所提供給您。大部分 Isp 提供這些類型的指示並收錄公司支援頁面上。
    
- 即使尚未發佈前，電子郵件驗證記錄和它的可正常運作，您仍必須發佈電子郵件驗證記錄傳送給 Microsoft。如此一來，您在網路釣魚、 對抗協助，降低，或組織傳送至，將會取得 phished 其中。
    
### <a name="what-if-you-dont-know-who-sends-email-as-your-domain"></a>如果您不知道誰以您網域傳送電子郵件？

因為它們不知道其所有寄件者屬於許多網域請勿發佈 SPF 記錄。這是外觀是否可以、 您不必知道誰成效。但是，您應該開始發佈過您不要知道的特別是貴公司的流量所在，並發佈中性 SPF 原則的 SPF 記錄吗？ 所有：
  
example.com IN TXT"v = spf1 include:spf.example.com 吗？ 所有"
  
中性 SPF 原則表示任何而言不在您公司的基礎結構的電子郵件將傳送電子郵件驗證所有其他電子郵件接收器。來自您不知道相關的寄件者的電子郵件會改為使用 neutral、 幾乎相同所有發佈沒有 SPF 記錄。
  
傳送至 Office 365、 時將會是來自您公司的流量的電子郵件標示成驗證，但來自的來源您不知道相關的電子郵件仍會標示為身分詐騙 （取決於 Office 365 可以隱含驗證它）。但是，這是仍要標示為詐騙 Office 365 的所有電子郵件從改進。
  
一旦您是否已得到入門後援原則 SPF 記錄吗？ 所有，您可以逐步包含更傳送基礎結構，然後發佈較嚴密的原則。 
  
### <a name="what-if-you-are-the-owner-of-a-mailing-list"></a>如果您是郵寄清單的擁有者吗？

請參閱[常見案例 #2-討論列出](#common-scenario-2---discussion-lists)一節。 
  
### <a name="what-if-you-are-an-infrastructure-provider-such-as-an-internet-service-provider-isp-email-service-provider-esp-or-cloud-hosting-service"></a>如果您是例如網際網路服務提供者 (ISP)、 電子郵件服務提供者 (ESP) 或雲端裝載服務基礎結構提供者吗？

如果主機網域的電子郵件和其傳送電子郵件，或提供託管可以傳送電子郵件的基礎結構，您應該執行下列動作：
  
- 確定您的客戶有細部要在其 SPF 記錄中發佈的文件
    
- 請考慮 DKIM 簽章簽署外寄電子郵件上，即使客戶不會明確地設定它 （符號與預設網域）。您可以偶數雙登使用 DKIM （一次使用他們有設定它，如果在客戶的網域和第二個時間與您的公司 DKIM 簽章） 的簽章的電子郵件
    
向 Microsoft 既不保證即使您驗證電子郵件來自您的平台，但至少它可確保 Microsoft 不會不垃圾電子郵件因為未通過驗證。如需周圍 Outlook.com 如何篩選電子郵件的詳細資訊，請參閱[Outlook.com 郵件管理員] 頁面](https://postmaster.live.com/pm/postmaster.aspx)。
  
如需服務提供者的最佳作法的詳細資訊，請參閱[M3AAWG 行動訊息的最佳作法服務提供者](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf)。
  
## <a name="frequently-asked-questions"></a>常見問題集

### <a name="why-is-microsoft-making-this-change"></a>Microsoft 進行這項變更的為何？

由於網路釣魚的影響攻擊，與電子郵件驗證已繞 15 年，因為 Microsoft 相信的風險繼續允許未經驗證的電子郵件是高於遺失合法電子郵件的風險。
  
### <a name="will-this-change-cause-legitimate-email-to-be-marked-as-spam"></a>此變更會導致合法電子郵件標示為垃圾郵件吗？

在第一筆、 會有一些標示為垃圾郵件的郵件。不過，一段時間的寄件者將會調整，以及然後誤標身分詐騙的訊息數量微乎其微大部分的電子郵件路徑。
  
Microsoft 本身先採用這項功能再將其部署至其客戶的其餘部分的幾週。第一次中斷時，它會逐漸拒絕。
  
### <a name="will-microsoft-bring-this-feature-to-outlookcom-and-non-advanced-threat-protection-customers-of-office-365"></a>將 Microsoft 提到這項功能 Outlook.com 和非進階威脅保護的 Office 365 的客戶吗？

Microsoft 的反詐騙技術最初已部署給其組織有的 Office 365 企業版 E5 訂閱或鎖購買其訂閱的 Office 365 進階威脅保護 (ATP) 附加元件。年 10 月、 2018年我們已擴充至組織的 Exchange Online Protection (EOP)，以及保護。未來，我們可能如 Outlook.com 釋出其。不過，如果我們執行動作時，可能不會套用等報告某些功能及自訂會覆寫。
  
### <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>我如何可以回報垃圾郵件或非垃圾郵件訊息給 Microsoft？

您可以使用[報表訊息增益集 outlook](https://support.office.com/article/use-the-report-message-add-in-b5caa9f1-cdf3-4443-af8c-ff724ea719d2)，如果未安裝或、[提交垃圾郵件、 非垃圾郵件和網路釣魚詐騙郵件訊息給 Microsoft 進行分析](https://technet.microsoft.com/en-us/library/jj200769%28v=exchg.150%29.aspx)。
  
### <a name="im-a-domain-administrator-who-doesnt-know-who-all-my-senders-are"></a>我已經不知道所有 「 我的寄件者屬於網域管理員 ！

請參閱[之網域的是不是 Office 365 客戶的系統管理員](#administrators-of-domains-that-are-not-office-365-customers)。
  
### <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization-even-though-office-365-is-my-primary-filter"></a>如果發生什麼事我停用 「 我的組織，反詐騙保護即使 Office 365 是主要的篩選條件？

不建議這因為您將會公開給其他未接的網路釣魚和垃圾郵件。並非所有網路釣魚詐騙，並不是所有詐騙將未都接。不過，您的風險會高於啟用反詐騙的客戶。
  
### <a name="does-enabling-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>啟用反詐騙保護意義我將會從所有網路釣魚保護吗？

不過，否，因為網路釣客將能否例如使用其他技術危害帳戶或設定可用服務的帳戶。不過，反網路釣魚保護偵測這些其他類型的網路釣魚方法因為 Office 365 保護層級會一起設計工時及建置彼此運作更好。
  
### <a name="do-other-large-email-receivers-block-unauthenticated-email"></a>其他大量電子郵件接收器封鎖未經過驗證的電子郵件吗？

幾乎所有的大量電子郵件接收器實作傳統 SPF、 DKIM，以及 DMARC。某些接收器有其他檢查比只是這些標準，但較少移時若要封鎖的 Office 365 未經驗證的更嚴格的電子郵件和視為詐騙。不過，大部分的業界變得更嚴格有關此特定類型的電子郵件、 特別是因為網路釣魚問題。
  
### <a name="do-i-still-need-the-advanced-spam-filtering-option-enabled-for-spf-hard-fail-if-i-enable-anti-spoofing"></a>仍然需要啟用"SPF 硬失敗"如果啟用反詐騙的進階垃圾郵件篩選選項吗？

否，此選項不再需要因為 SPF 硬失敗，但是更廣泛組準則的不只會考慮反詐騙功能。如果您有反詐騙啟用並已啟用 [SPF 硬失敗] 選項，您將可能取得更多的誤判。建議您停用此功能，它會為垃圾郵件或 phish，不提供幾乎任何其他 catch 並而產生多半誤判。
  
### <a name="does-sender-rewriting-scheme-srs-help-fix-forwarded-email"></a>沒有協助修正轉寄電子郵件寄件者修正配置 (SRS) 吗？

SRS 只部分修正此問題的轉寄電子郵件。由修正 SMTP MAIL FROM，SRS 可以確保在下一個目的地在轉寄的郵件通過 SPF。不過，因為反詐騙根據 From： 地址與 MAIL FROM 或 DKIM 簽署網域 （或其他信號） 組合，它不是足夠，防止轉寄電子郵件被標示成詐騙。
  

