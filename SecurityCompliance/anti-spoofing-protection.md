---
title: Office 365 的反詐騙保護
ms.author: tracyp
author: MSFTtracyp
manager: laurawi
ms.date: 3/6/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: d24bb387-c65d-486e-93e7-06a4f1a436c0
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: 本文說明 Office 365 如何減少抵禦網路釣魚攻擊使用偽造地址寄件者的網域，亦即詐騙的網域。 它這樣的優勢分析郵件，並封鎖該組可驗證不使用標準的電子郵件的驗證方法或其他寄件者信譽技術。 這項變更所實作，以減少要公開在 Office 365 組織的網路釣魚攻擊的數目。
ms.openlocfilehash: 377bc75e7538dacab1180045ddfdeb1a2ac32a65
ms.sourcegitcommit: 5eb664b6ecef94aef4018a75684ee4ae66c486bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/08/2019
ms.locfileid: "30492872"
---
# <a name="anti-spoofing-protection-in-office-365"></a>Office 365 的反詐騙保護

本文說明 Office 365 如何減少抵禦網路釣魚攻擊使用偽造地址寄件者的網域，亦即詐騙的網域。 完成其這分析郵件，並封鎖不能使用標準的電子郵件的驗證方法或其他寄件者信譽技術驗證項目。 這項變更所實作，以減少要公開在 Office 365 組織的網路釣魚攻擊的數目。
  
本文也說明為何要進行此變更，客戶可以如何準備，這項變更、 如何檢視將會受到影響的郵件、 如何報告的郵件、 如何減輕誤判，，以及給 Microsoft 的寄件者應如何準備進行這變更。
  
Microsoft 的反詐騙技術最初部署給其組織有 Office 365 企業版 E5 訂閱，或有購買其訂閱的 Office 365 進階威脅防護 (ATP) 附加元件。 2018 年 10 月日起我們延伸也有 Exchange Online Protection (EOP) 的組織的保護。 此外，因為我們的篩選器的所有要深入了解從彼此的方式，Outlook.com 使用者可能會影響。
  
## <a name="how-spoofing-is-used-in-phishing-attacks"></a>在 [網路釣魚攻擊的詐騙使用方式

保護其使用者時，Microsoft 會嚴重採用網路釣魚的威脅。 濫發垃圾郵件者和網路釣客常使用的技術的其中一個在詐騙，這當寄件者為偽造地址，且郵件似乎來自是由其他人或地方以外的實際的來源。 這個方法通常用於網路釣魚活動設計用來取得使用者認證。 Microsoft 的反詐騙技術特別會檢查冒名的 '從： 標頭' 也就是在類似 Outlook 電子郵件用戶端中會顯示一個。 當 Microsoft 具有高信賴度的 From： 標頭為冒名，它會識別為詐騙郵件。
  
詐騙郵件影響兩個負的實際使用者：
  
### <a name="1-spoofed-messages-deceive-users"></a>1.冒名郵件惡作劇使用者
  
首先，冒名的郵件可能誘騙使用者按一下連結及放棄其認證、 下載惡意程式碼，或回覆郵件具有敏感內容 （後者的一種稱為 「 商務電子郵件危害）。 例如，以下是 msoutlook94@service.outlook.com 冒名寄件者的網路釣魚郵件：
  
![模擬 service.outlook.com 網路釣魚郵件](media/1a441f21-8ef7-41c7-90c0-847272dc5350.jpg)
  
上述並非真的來自 service.outlook.com，但改為已讓它看起來像它並未 phisher 詐騙。 它會嘗試誘騙使用者按一下郵件中的連結。
  
下一個範例詐騙 contoso.com:
  
![網路釣魚郵件-商業電子郵件遭到入侵](media/da15adaa-708b-4e73-8165-482fc9182090.jpg)
  
郵件看起來合法的但事實上詐騙。 此網路釣魚郵件是一種商業電子郵件危害也就是網路釣魚的子類別。

### <a name="2-users-confuse-real-messages-for-fake-ones"></a>2.使用者混淆假的實際的郵件
  
第二個、 詐騙郵件建立不確定使用者了解網路釣魚郵件，但無法判斷實際的郵件和詐騙的一之間的差異。 例如，以下是從 Microsoft 安全性帳戶的電子郵件地址重設實際密碼的範例：
  
![Microsoft 合法的密碼重設](media/58a3154f-e83d-4f86-bcfe-ae9e8c87bd37.jpg)
  
上述的訊息沒有來自 Microsoft，但在此同時，使用者會用來取得網路釣魚郵件可能誘騙使用者按一下連結及放棄其認證、 下載惡意程式碼，或回覆郵件具有敏感內容。 因為很難分辨實際的密碼重設與假的一個之間的差異，許多使用者略過這些郵件、 它們回報為垃圾郵件，或不必要地回向 Microsoft 回報郵件為未接的網路釣魚詐騙。

若要停止詐騙，電子郵件篩選產業已開發的電子郵件的驗證通訊協定，例如[SPF](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)， [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)、 [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)。 DMARC 可防止詐騙檢查郵件的寄件者的使用者會看到其電子郵件用戶端中的一個 （在上述範例中，這是 service.outlook.com、 outlook.com 和 accountprotection.microsoft.com）-通過 SPF 或 DKIM 的網域。 也就是說，使用者會看到的網域已經過驗證，因此不詐騙郵件。 如需更完整的討論，請參閱一節 「*了解為什麼電子郵件驗證不一定足以停止詐騙 」* 本文稍後。
  
不過，這個問題是記錄是選擇性的不需要該電子郵件驗證。 因此，當網域嚴密的驗證原則與 like microsoft.com 和 skype.com 保護來自詐騙網域的所有發佈弱的驗證原則或任何原則、 為詐騙的目標。截至年 3 月 2018年僅 9%的網域的公司中 Fortune 500 發佈強式電子郵件驗證原則。 剩餘 91%可能遭到假冒的 phisher 和除非電子郵件篩選器偵測到使用其他原則，它可能會傳遞至使用者欺騙它們：
  
![Fortune 500 公司的 DMARC 原則](media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)
  
小型至中型大小公司的比例不在發佈強式電子郵件驗證原則 Fortune 500 為較小，和小仍為 「 北美地區 」 及西歐外的網域。
  
因為網路釣客雖然企業可能不知道電子郵件驗證的運作方式，執行了解，並利用缺乏，這會是大的問題。
  
設定 SPF，DKIM、 DMARC 的詳細資訊，請參閱 [] 區段中 「 更新版本文件中的*客戶的 Office 365 」* 。 
  
## <a name="stopping-spoofing-with-implicit-email-authentication"></a>停止使用隱含的電子郵件驗證詐騙

因為網路釣魚和矛網路釣魚這類問題，且強式電子郵件驗證原則限制的採用，因為 Microsoft 會繼續投入來保護其客戶的功能。 因此，Microsoft 向前移動使用*隱含的電子郵件驗證*-如果網域不會驗證，Microsoft 會將它視為它有發佈電子郵件驗證記錄並且將它視為據此如果它不會傳遞。 
  
若要這麼做，Microsoft 已內建許多一般的電子郵件的驗證，包括寄件者信譽、 寄件者/收件者歷程記錄、 行為分析和其他進階的技術擴充功能。 寄件者不會發佈電子郵件驗證網域的郵件會被標示為詐騙除非它包含其他信號表示它是合法。
  
如此一來，使用者可的結束電子郵件傳送給它們不被冒名的信賴度，寄件者可以放心人模擬其網域和 Office 365 客戶可以提供更好的防護，如模擬保護。
  
若要查看 Microsoft 的一般宣告，請參閱 < <b0>Sea 的 Phish 第 2 部分-Office 365 中增強反詐騙</b0>。
  
## <a name="identifying-that-a-message-is-classified-as-spoofed"></a>識別郵件分類為詐騙

### <a name="composite-authentication"></a>複合驗證

雖然 SPF，DKIM、 DMARC 自行都很有用，它們不在事件訊息有無明確驗證記錄通訊不足，無法驗證狀態。 因此，Microsoft 已開發的演算法，將多個訊號結合成複合式驗證或 compauth 呼叫簡稱為單一值。 在 Office 365 的客戶有 compauth 值戳印在郵件標頭中的*Authentication-results*標頭。 
  
```
Authentication-Results:
  compauth=<fail|pass|softpass|none> reason=<yyy>

```

|**CompAuth 結果**|**描述**|
|:-----|:-----|
|失敗|郵件無法明確驗證 （傳送網域發佈記錄明確地在 DNS 中） 或隱含驗證 （傳送網域沒有不發佈記錄在 DNS 中，讓 Office 365 內插結果好像它已發佈的記錄）。|
|傳遞|郵件傳遞明確驗證 （郵件通過 DMARC 或[最佳猜測通過 DMARC](https://blogs.msdn.microsoft.com/tzink/2015/05/06/what-is-dmarc-bestguesspass-in-office-365)） 或具有高信賴度隱含驗證 （傳送網域不會發佈電子郵件驗證記錄，但 Office 365 具有強式的後端訊號，以指出郵件為可能合法)。|
|softpass|郵件傳遞隱含的驗證與低-中型信賴 （傳送網域不會發佈電子郵件驗證，但 Office 365 後端訊號，以指出郵件為合法但弱的訊號的強度）。|
|無|未先驗證訊息 （或未驗證，但未對齊），但由於寄件者信譽或其他因素而不會套用複合驗證。|
   
|||
|:-----|:-----|
|**原因**|**描述**|
|0xx|複合驗證失敗訊息。<br/>**000**表示郵件無法以拒絕或隔離] 動作的 DMARC。  <br/>**001**表示郵件無法隱含的電子郵件驗證。 這表示在傳送網域沒有不會發佈，電子郵件驗證記錄或者一樣，如果他們有弱的失敗原則 (SPF fail 或 neutral，DMARC 原則的 p = 無)。  <br/>**002**表示該組織有明確禁止傳送冒名的電子郵件的寄件者/網域組的原則，系統管理員手動設定此設定。  <br/>**010**表示郵件無法使用拒絕或隔離，巨集指令的 DMARC，並在傳送網域是下列其中一個貴組織的公認的網域 (這是 self-self 或組織內部的一部分詐騙)。  <br/>**011**表示郵件無法通過隱含的電子郵件的驗證，並在傳送網域是下列其中一個貴組織的公認的網域 (這是 self-self 或組織內部的一部分詐騙)。|
|所有其他代碼 （1xx、 2xx、 3xx、 4xx、 5xx）|對應至各種內部代碼的郵件傳遞隱含驗證，或不有任何驗證，但沒有巨集指令所套用的原因。|
   
查看郵件的標頭，以系統管理員或甚至是使用者可以決定 Office 365 到達結束時可能遭到假冒寄件者的方式。
  
### <a name="differentiating-between-different-types-of-spoofing"></a>區別不同類型的詐騙

Microsoft 區分兩種不同類型的詐騙郵件：
  
 **組織內部詐騙**
  
也稱為自助-自助詐騙，發生這種情況時的網域，在 [從： 地址相同，或是配合收件者網域 （當收件者網域是下列其中一個貴組織的[公認的網域](https://technet.microsoft.com/en-us/library/jj945194%28v=exchg.150%29.aspx)）;或者，當在 [從網域： 地址是相同的組織的一部分。
  
例如，下列寄件者和收件者從具有相同的網域 (contoso.com)。 空格插入可防止特色收集在此頁面上的電子郵件地址）：
  
從： 寄件者 @ contoso.com
  
收件者： 收件者 @ contoso.com
  
下列具有對齊與組織的網域 (fabrikam.com) 的寄件者和收件者網域：
  
從： 寄件者 @ foo.fabrikam.com
  
收件者： 收件者 @ bar.fabrikam.com
  
下列的寄件者和收件者網域是不同 （microsoft.com 和 bing.com），但他們都屬於相同的組織 （亦即，同時屬於組織的公認的網域）：
  
從： 寄件者 @ microsoft.com
  
收件者： 收件者 @ bing.com
  
無法通過組織內部詐騙郵件包含標頭中的下列值：
  
X Forefront-反垃圾郵件報告:...]CAT:SPM/HSPM/PHSH;...]SFTY:9.11
  
CAT is 的郵件類別和它通常加上戳記，做為 SPM （垃圾郵件），但有時會是 HSPM （高信賴度垃圾郵件） 或釣魚程式 （網路釣魚） 取決於哪些其他類型的模式中可能發生郵件。
  
SFTY 是郵件的安全層級、 第一個數字 (9) 表示郵件是網路釣魚，而第二組數字後點 (11) 表示它是組織內部詐騙。
  
沒有特殊原因程式碼的組織內部詐騙，將會加上戳記稍後 2018 （時間表尚未定義） 的複合驗證。
  
 **跨網域詐騙**
  
發生這種情況時傳送的網域，在 [從： 地址是在接收組織外部網域。 由於跨網域詐騙失敗複合驗證的訊息包含標頭中的下列值：
  
驗證結果:...] compauth = 失敗原因 = 000/001
  
X Forefront-反垃圾郵件報告:...]CAT:SPOOF;...]SFTY:9.22
  
在這兩種情況下，下列的紅色的安全提示中加上訊息或自訂收件者的信箱語言為對等項目：
  
![紅色的安全提示-詐騙偵測](media/a366156a-14e8-4c14-bfe5-2031b21936f8.jpg)
  
它是只透過查看 [從： 地址和知道您收件者的電子郵件的，或藉由檢查的電子郵件標頭，就能區分組織內部及跨網域詐騙。
  
## <a name="how-customers-of-office-365-can-prepare-themselves-for-the-new-anti-spoofing-protection"></a>如何的 Office 365 客戶可以自行為準備新的反詐騙保護

### <a name="information-for-administrators"></a>系統管理員的資訊

以在 Office 365 組織的系統管理員身分，有數個關鍵您應該要知道的資訊。
  
### <a name="understanding-why-email-authentication-is-not-always-enough-to-stop-spoofing"></a>了解為什麼電子郵件驗證不一定足以停止詐騙

新的反詐騙保護依賴電子郵件驗證 （SPF、 DKIM 和 DMARC） 未將郵件標記為詐騙。 常見的範例時，傳送網域永遠不會發佈 SPF 記錄。 如果沒有任何 SPF 記錄或者他們不正確地設定，已傳送的郵件會被標示為冒名除非 Microsoft 具有指出郵件為合法的後端智慧。
  
例如之前反詐騙要部署，, 郵件可能會看起來與沒有 SPF 記錄，沒有 DKIM 的記錄，並無的 DMARC 記錄下列： 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```
之後反詐騙，如果您有 Office 365 企業版 E5、 EOP 或 ATP，compauth 值會加上戳記：
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com; compauth=fail reason=001
From: sender @ example.com
To: receiver @ contoso.com

```

如果 example.com 會修正這藉由設定 SPF 記錄，但不是 DKIM 記錄，這就會通過複合驗證，因為傳遞 SPF 網域對齊的網域，在 [從： 地址： 
  
```
Authentication-Results: spf=pass (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

或者，如果他們設定 DKIM 記錄，但不是 SPF 記錄，這會同時傳遞複合驗證因為傳遞 DKIM 簽章中的網域對齊的網域，在 [從： 地址： 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.example.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

不過，phisher 可能也設定 SPF 和 DKIM 和登入自己的網域的郵件，但指定不同的網域，在 [從： 地址。 SPF 和 DKIM 都不需要以符合在 [從網域的網域： 地址，所以除非 example.com 發佈 DMARC 的記錄，這會將標示為使用 DMARC 詐騙： 
  
```
Authentication-Results: spf=pass (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```

在 [電子郵件用戶端 (Outlook web 應用程式或任何其他電子郵件用戶端上的 Outlook)，只能從： 網域，則不在 SPF 或 DKIM，且網域可以到思考郵件是來自 example.com，但實際上是來自 maliciousDomain.com 誤導使用者.
  
![已驗證的訊息但從： 網域未對齊項目通過 SPF 或 DKIM](media/a9b5ab2a-dfd3-47c6-8ee8-e3dab2fae528.jpg)
  
基於這個理由，Office 365 的所需的網域，在 [從： 地址配合 SPF 或 DKIM 簽章中的網域，且如果它不支援，包含一些其他內部訊號，指出郵件合法。 否則，郵件就是 compauth 失敗。 
  
```
Authentication-Results: spf=none (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: sender@contoso.com
To: someone@example.com
```

因此，Office 365 反詐騙保護未驗證的網域，但檢查設定驗證，但不符合針對在 [從網域的網域： 地址，也就是一，使用者會看到並相信是郵件的寄件者。 這是這兩個組織外部的網域，以及組織內的網域，則為 true。
  
因此，如果您曾經收到複合驗證失敗，並標示為冒名，即使郵件通過 SPF 和 DKIM 的訊息，它會是因為通過 SPF 和 DKIM 網域不一致的網域，在 [從： 地址。
  
### <a name="understanding-changes-in-how-spoofed-emails-are-treated"></a>了解如何冒名的電子郵件中的變更會被視為

目前，針對所有的組織中 Office 365-ATP 和非-ATP-郵件使用拒絕或隔離原則 DMARC 就會標示為垃圾郵件和通常需要 [高信賴度垃圾郵件] 動作，或有時一般的垃圾郵件動作的失敗 (根據其他垃圾郵件規則先加以識別為垃圾郵件）。 組織內部詐騙偵測採取垃圾郵件規則。 此行為不需要啟用，也可以停用它。
  
不過，跨網域詐騙郵件，這項變更之前他們會經過一般的垃圾郵件、 釣魚程式和惡意程式碼檢查與如果篩選器的其他組件 」 將其識別為可疑，將他們分別標示為垃圾郵件、 釣魚程式或惡意程式碼。 使用新的跨網域詐騙保護，無法進行驗證的任何郵件將根據預設，採取的動作中反網路釣魚定義\>反詐騙的原則。 如果其中一個未定義，它將會移至使用者的垃圾郵件] 資料夾。 在某些情況下，更可疑的郵件也會有紅色的安全提示新增到郵件。
  
這可能會導致先前已標示為垃圾郵件仍被標示為垃圾郵件，但現在也有紅色的安全提示; 某些郵件在其他情況下，新增先前已標示為非垃圾郵件會開始被標示為垃圾郵件 (CAT:SPOOF) 具有紅色安全提示的郵件。 在仍其他情況下，已移動所有垃圾郵件及釣魚程式至隔離區的客戶會立即看到它們移至 [垃圾郵件] 資料夾 （此行為，可以變更，請參閱[變更您的反詐騙設定](#changing-your-anti-spoofing-settings)）。
  
有多個不同的方式可以假冒 （請參閱本文稍早的[不同類型的詐騙之間 Differentiating](#differentiating-between-different-types-of-spoofing) ） 一則訊息，但截至 2018 年 3 月，Office 365 會將這些郵件的方法不尚未整合。 下表是快速摘要] 中，使用跨網域詐騙保護被新的行為： 
  
|**詐騙的類型**|**類別**|**新增安全提示？**|**適用於**|
|:-----|:-----|:-----|:-----|
|DMARC 失敗 （隔離或拒絕）  <br/> |HSPM （預設值），也可能 SPM 或 PHSH  <br/> |否 （尚未）  <br/> |所有 Office 365 客戶 Outlook.com  <br/> |
|自助-自助  <br/> |SPM  <br/> |是  <br/> |所有 Office 365 組織 Outlook.com  <br/> |
|跨網域  <br/> |詐騙  <br/> |是  <br/> |Office 365 進階威脅防護和 E5 客戶  <br/> |

### <a name="changing-your-anti-spoofing-settings"></a>變更您的反詐騙設定

若要建立或更新 （跨網域） 反詐騙設定，瀏覽至 [防網路釣魚\>威脅管理] 下的反詐騙設定\>安全性原則] 索引標籤&amp;合規性中心。 如果您從未建立任何反網路釣魚的設定，您必須建立一個：
  
![反網路釣魚-建立新的原則](media/9337ec91-270e-4fa7-9dfa-a51a2d1eb95e.jpg)
  
如果您已經建立一個，您可以選取要對其進行修改：
  
![反網路釣魚-修改現有的原則](media/75457a7c-882e-4984-80d1-21a12b42c53a.jpg)
  
選取您剛剛建立，並繼續執行步驟，[了解詐騙情報多個](learn-about-spoof-intelligence.md)所述的原則。
  
![啟用或停用反詐騙](media/c49e2147-c954-443c-9144-1cbd139e1166.jpg)
  
![啟用或停用反詐騙安全提示](media/eec7c407-31fc-4f73-8325-307d82d1fb53.jpg)
  
若要使用 PowerShell 建立新的原則： 
  
```powershell
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

然後，您可能會修改使用 PowerShell，下列[設定 AntiphishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy?view=exchange-ps)文件的防網路釣魚原則參數。 您可能會當做參數指定 $name:
  
```powershell
Set-AntiphishPolicy -Identity $name <fill in rest of parameters>
```

稍後 2018，而不是您不必建立一個預設原則，其中會加以建立，因此您不需要以手動方式指定範圍限定為您組織中的所有收件者 （以下螢幕擷取畫面受限於最終實作之前變更）。
  
![預設的反網路釣魚原則](media/1f27a0bf-e202-4e12-bbac-24baf013c8f9.jpg)
  
不同於您所建立的原則，您無法刪除預設原則，修改它的優先順序，或選擇將範圍至哪一個使用者、 網域或群組。
  
![反網路釣魚預設原則的詳細資訊](media/30c21ceb-df52-4c93-aa65-f44a55dc1009.jpg)
  
若要使用 PowerShell 來設定預設保護：
  
```powershell
$defaultAntiphishPolicy = Get-AntiphishPolicy | ? {$_.IsDefault -eq $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement <$true|$false>
```

您應該僅停用反詐騙保護如果您有另一部信箱伺服器或在 Office 365 前方的伺服器 （請參閱合法的案例，以停用反詐騙如需詳細資訊）。
  
```powershell
$defaultAntiphishPolicy = Get-AntiphishiPolicy | ? {$_.IsDefault $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement $false 

```
> [!IMPORTANT]
> 如果您的電子郵件路徑中的第一個躍點是 Office 365，並收到太多合法電子郵件標示為詐騙，您應該先設定您允許將冒名的電子郵件傳送到您網域的寄件者 （請參閱節 *」 管理合法寄件者所傳送 unauthenticated 電子郵件 」* )。 如果您仍收到太多誤判 （也就是合法郵件標示為詐騙），我們不建議停用反詐騙保護夾雜在一起。 相反地，我們建議您選擇基本而不最高保護。 最好是透過誤判比至公開最後意來得高成本的長期詐騙電子郵件組織運作。

### <a name="managing-legitimate-senders-who-are-sending-unauthenticated-email"></a>管理合法的寄件者所傳送未驗證的電子郵件

記錄傳送者誰未經驗證的電子郵件至您的組織的 office 365。 如果服務認為不合法寄件者，它會將它標記為*compauth*失敗。 這會歸類為詐騙，雖然這取決於您已套用至郵件的反詐騙原則。
  
不過，身為管理員，您可以指定哪些寄件者允許傳送冒名的電子郵件，覆寫 Office 365 的決策。
  
**方法 1-如果您的組織擁有的網域、 設定電子郵件的驗證**
  
此方法可以用來解決組織內部詐騙和跨網域詐騙在您擁有或互動的情況下使用多重租用戶。 它也可以協助解決跨網域詐騙您傳送給其他 Office 365 內的客戶，也裝載於其他提供者的第三方。
  
如需詳細資訊，請參閱 < <b0>Office 365 的客戶</b0>。

**方法 2-設定未驗證的電子郵件的允許寄件者使用詐騙智慧**
  
您也可以使用[詐騙智慧](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf)允許未經驗證的郵件傳輸至貴組織的寄件者。 
  
外部網域，如詐騙的使用者是中的 From 地址的網域傳送基礎結構時傳送端 IP 位址 (分成/24 CIDR 範圍)，或組織的網域的 PTR 記錄 （在以下的螢幕擷取畫面，傳送 IP 可能是的 PTR 記錄是 outbound.mail.protection.outlook.com，131.107.18.4，而且這會顯示為 [傳送基礎結構的 outlook.com）。
  
若要允許此寄件者傳送未驗證的電子郵件，變更為 [ **]** 的**否]** 。
  
![設定反詐騙的允許寄件者](media/d4334921-d820-4334-8217-788279701e94.jpg)
  
您也可以使用 PowerShell 以允許特定寄件者偽造您的網域：
  
```powershell
$file = "C:\My Documents\Summary Spoofed Internal Domains and Senders.csv"
```

```powershell
Get-PhishFilterPolicy -Detailed -SpoofAllowBlockList -SpoofType External | Export-CSV $file
```

![從 Powershell 取得詐騙的寄件者](media/0e27ffcf-a5db-4c43-a19b-fa62326d5118.jpg)
  
在上圖中額外的分行符號已新增若要讓這個螢幕擷取畫面配合。 一般而言，所有的值會出現在單一行上。
  
編輯檔案並尋找對應至 outlook.com 和 bing.com，那一行，AllowedToSpoof 項目變更為 [是] 否從：
  
![在 Powershell 中的 [是] 允許設定詐騙](media/62340452-62d3-4958-9ce9-afe5275a870d.jpg)
  
儲存檔案，然後再執行：
  
```powershell
$UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
```

現在，這樣可讓傳送未驗證的電子郵件從 bing.com \*。 outlook.com。

**方法 3-建立寄件者/收件者對允許項目**
  
您也可以選擇略過所有的垃圾郵件篩選特定寄件者。 如需詳細資訊，請參閱 < <b0>How to： 安全地新增到 Office 365 中的 [允許] 清單寄件者</b0>。
  
如果您使用此方法時，它會略過垃圾郵件與部分的釣魚程式篩選，但卻不惡意程式碼篩選。
  
**方法 4-連絡寄件者，並請他們設定電子郵件的驗證**
  
因為垃圾郵件和網路釣魚的問題，Microsoft 建議您設定電子郵件驗證所有寄件者。 如果您知道傳送網域的系統管理員，請連絡它們並要求將它們設定成電子郵件驗證記錄使您不需要加任何覆寫。 如需詳細資訊，請參閱 <<c0>的網域都不是 Office 365 客戶的系統管理員」 本文稍後的。 
  
時可能很難在第一次取得傳送網域來進行驗證，經過一段時間，為越來越多電子郵件篩選器啟動 junking 或甚至拒絕他們的電子郵件時，就會造成這些設定的適當的記錄，以確保較佳的傳遞。
  
### <a name="viewing-reports-of-how-many-messages-were-marked-as-spoofed"></a>檢視多少郵件已標示為冒名的報告

一旦啟用您的反詐騙政策，您可以使用威脅情報來讓周圍多少訊息標示為釣魚程式的數字。 若要這麼做，請移至安全性&amp;合規性中心 (SCC) 威脅管理下\>總管] 中，將檢視設定釣魚程式，以及群組所寄件者網域] 或 [保護狀態：
  
![檢視多少訊息標示為釣魚程式](media/de25009a-44d4-4c5f-94ba-9c75cd9c64b3.jpg)
  
您可以與各種不同的報告，以查看多少被標示為網路釣魚，包括郵件標示為詐騙互動。 若要深入了解，請參閱[Office 365 威脅情報快速入門](get-started-with-ti.md)。
  
您還不能分割哪一個郵件已標示為因為詐騙而非其他類型的網路釣魚 （一般網路釣魚、 網域或使用者模擬，等等）。 不過，更新版本中，您將能夠執行這項操作透過安全性&amp;合規性中心。 一旦您這麼做，您可以使用的起始位置為這份報告來識別可能合法的會被標示為因為失敗的驗證詐騙的寄送網域。
  
下列螢幕擷取畫面會提案，此資料的看起來，但發行時可能會變更：
  
![檢視網路釣魚報告偵測類型](media/dd25d63f-152c-4c55-a07b-184ecda2de81.jpg)
  
非 ATP 和 E5 客戶，這些報告可稍後下威脅保護狀態 (TPS) 報告，請使用，但將至少 24 小時的延遲。 將更新此頁面上，因為它們已整合至安全性&amp;合規性中心。
  
### <a name="predicting-how-many-messages-will-be-marked-as-spoof"></a>預測解決方案能夠提供多少郵件會被標示為詐騙

一旦 Office 365 更新其設定，以讓您在關閉反詐騙強制執行，或在與基本或高強制執行，您將能夠查看如何在各種設定變更郵件處理的能力。 也就是說，如果反詐騙已關閉，您將能夠看到多少訊息將會被偵測為詐騙，如果您開啟為 Basic;或者，如果是 Basic，您將能夠看到多少更多的郵件會被偵測為詐騙，如果您開啟為 [高]。
  
此功能目前是在開發。 已定義的詳細資訊，與螢幕擷取畫面的安全性與合規性中心，並以 PowerShell 範例，將會更新此頁面。
  
![「 如果 」 報告啟用反詐騙](media/fdd085ae-02c1-4327-a063-bfe9a32ff1eb.jpg)
  
![允許詐騙的寄件者可能 UX](media/53f9f73e-fb01-47f3-9a6d-850c1aef5efe.jpg)
  
### <a name="understanding-how-spam-phishing-and-advanced-phishing-detections-are-combined"></a>了解如何垃圾郵件、 網路釣魚，以及偵測會結合的進階網路釣魚

使用 Exchange Online 中，或者沒有 ATP，組織可以指定服務判別為惡意程式碼、 垃圾郵件、 高信賴度垃圾郵件、 網路釣魚及大量郵件時要採取的動作。 ATP 客戶的 ATP 防網路釣魚原則和 EOP 客戶的防網路釣魚原則與訊息可能會叫用多個偵測類型 （例如，惡意程式碼、 網路釣魚，與使用者模擬） 的事實，可能會有哪些某些混淆會套用原則。
  
一般而言，在 CAT （類別） 屬性中的 X Forefront-反垃圾郵件報告標頭中識別套用至郵件的原則。
  
|**優先順序**|**原則**|**類別**|**其中管理？**|**適用於**|
|:-----|:-----|:-----|:-----|:-----|
|1  <br/> |惡意程式碼  <br/> |MALW  <br/> |[惡意程式碼原則](configure-anti-malware-policies.md) <br/> |所有的組織  <br/> |
|2  <br/> |網路釣魚  <br/> |PHSH  <br/> |[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md) <br/> |所有的組織  <br/> |
|3  <br/> |高信賴度垃圾郵件  <br/> |HSPM  <br/> |[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md) <br/> |所有的組織  <br/> |
|4  <br/> |詐騙  <br/> |詐騙  <br/> |[反網路釣魚原則](https://go.microsoft.com/fwlink/?linkid=864553)，[詐騙智慧](learn-about-spoof-intelligence.md) <br/> |所有的組織  <br/> |
|5  <br/> |垃圾郵件  <br/> |SPM  <br/> |[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md) <br/> |所有的組織  <br/> |
|6  <br/> |大量  <br/> |大量  <br/> |[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md) <br/> |所有的組織  <br/> |
|7  <br/> |網域模擬  <br/> |DIMP  <br/> |[設定 Office 365 ATP 防網路釣魚和防網路釣魚原則](set-up-anti-phishing-policies.md) <br/> |僅限組織的 ATP  <br/> |
|8  <br/> |使用者模擬  <br/> |UIMP  <br/> |[設定 Office 365 ATP 防網路釣魚和防網路釣魚原則](set-up-anti-phishing-policies.md) <br/> |僅限組織的 ATP <br/> |

如果您有多個不同的防網路釣魚原則時，會套用在最高優先順序的一個。 例如，假設您有兩個原則：

|**原則**|**優先順序**|**使用者/網域模擬**|**反詐騙**|
|:-----|:-----|:-----|:-----|
|A  <br/> |1  <br/> |開啟  <br/> |Off  <br/> |
|B  <br/> |2  <br/> |Off  <br/> |開啟  <br/> |

如果郵件有而識別為詐騙與使用者模擬，並組相同的使用者範圍的原則和原則 B，然後郵件會被視為詐騙，但沒有動作會套用自反詐騙已關閉並詐騙執行於優先順序較高 (4) 與使用者模擬 (8)。
  
若要讓其他類型的網路釣魚原則套用，您將需要調整的各種不同的原則套用到使用者的設定。
  
### <a name="legitimate-scenarios-to-disable-anti-spoofing"></a>若要停用反詐騙合法案例

從網路釣魚攻擊更妥善地反詐騙保護客戶，因此停用的反詐騙保護強烈建議不要。 藉由停用它，您可能會解決某些短期誤判，但您將會公開給更大的風險的長詞彙。 設定驗證等寄件者，或在網路釣魚原則 」，進行調整的成本通常是一次性事件或需要僅最少，定期維護。 不過，若要從網路釣魚攻擊，其中具有已公開的資料，復原成本或資產已遭到盜用是更高。
  
基於這個理由，最好是透過反詐騙誤判比若要停用反詐騙保護運作。
  
不過，沒有合法的案例，其中應該停用反詐騙，而且是時有額外的郵件篩選中的郵件路由，和 Office 365 產品不是在電子郵件路徑中的第一個躍點：
  
![客戶 MX 記錄未指向 Office 365](media/62127c16-cfb8-4880-9cad-3c12d827c67e.jpg)
  
Exchange 內部部署郵件伺服器，篩選裝置 Ironport，例如郵件或其他雲端託管的服務，可能是另一部伺服器。
  
如果收件者網域的 MX 記錄未指向 Office 365，然後便不需要停用反詐騙因為 Office 365 會接收網域的 MX 記錄，並隱藏反詐騙如果它指向另一個服務。 如果您不知道如果您的網域可在前面有另一部伺服器，您可以使用像是 MX 工具箱網站來查閱 MX 記錄。 它可能會說如下所示：
  
![MX 記錄指示網域不是指向 Office 365](media/d868bb9f-3462-49aa-baea-9447a3ce4877.jpg)
  
此網域有未指向 Office 365，讓 Office 365 不會套用反詐騙強制執行的 MX 記錄。
  
不過，如果*沒有*的收件者網域的 MX 記錄指向 Office 365，即使沒有在 Office 365 前方的另一個服務，然後您應該停用反詐騙。 最常見的範例是透過收件者修正： 
  
![收件者修正路由圖表](media/070d90d1-50a0-42e4-9fd3-920bc99a7cad.jpg)
  
網域 contoso.com 的 MX 記錄指向內部部署伺服器，雖然網域 @office365.contoso.net 的 MX 記錄指向 Office 365 因為它包含\*。 protection.outlook.com，或\*。 eo.outlook.com MX 記錄中：
  
![MX 記錄指向 Office 365，因此可能收件者修正](media/4101ad51-ef92-4907-b466-b41d14d344ca.jpg)
  
請務必區別當收件者網域的 MX 記錄未指向 Office 365，以及當它已經過收件者修正。 請務必告知這兩種情況之間的差異。
  
如果您不確定您接收網域已經過收件者修正，有時候您可以告訴可以查看郵件標頭。
  
） 第一次，查看的 Authentication-results 標頭中的收件者網域的郵件標頭：
  
```
Authentication-Results: spf=fail (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; office365.contoso.net; dkim=fail
  (body hash did not verify) header.d=simple.example.com;
  office365.contoso.net; dmarc=none action=none
  header.from=example.com; compauth=fail reason=001
```

粗體紅色的文字上方，在此案例的 office365.contoso.net 中找到的收件者的網域。 這可能會不同，在 [至收件者： 標頭：
  
收件者： 範例收件者\<@ contoso.com 收件者\>
  
執行實際的收件者網域的 MX 記錄查閱。 如果它包含\*。 protection.outlook.com、 mail.messaging.microsoft.com， \*。 eo.outlook.com 或 mail.global.frontbridge.com，表示 MX 指向 Office 365。
  
如果它不包含這些值，就表示 MX 未指向 Office 365。 您可以使用來驗證這項工具是 MX 工具箱。
  
針對此特定的範例，下列指出該 contoso.com，看起來像收件者，因為它至網域： 標頭中，有 MX 記錄指向內部部署伺服器：
  
![MX 記錄指向內部部署伺服器](media/2444144a-9a90-4319-96b2-d115041f669f.jpg)
  
不過，實際的收件者是的 office365.contoso.net 其 MX 記錄並未指向 Office 365:
  
![MX 指向 Office 365，必須是收件者修正](media/10cf3245-9b50-475a-b655-d8a51f99d812.jpg)
  
因此，此郵件可能已經過收件者修正。
  
b） 第二，請務必區分的收件者重的一般使用案例。 如果您要重新寫入收件者的網域，以\*。.onmicrosoft.com，改為寫入至\*。 mail.onmicrosoft.com。
  
一旦您已識別背後另一部伺服器路由傳送的最後一個收件者網域和收件者網域的 MX 記錄實際上會指向 Office 365 （如發佈在其 DNS 記錄），您可能會繼續進行若要停用反詐騙。
  
請記住，您不想停用反詐騙如果網域的路由路徑中的第一個躍點時，Office 365 中，只是一或多個服務背後。
  
### <a name="how-to-disable-anti-spoofing"></a>如何停用反詐騙

如果您已經建立反網路釣魚原則，請將 EnableAntispoofEnforcement 參數設定為 $false:
  
```
$name = "<name of policy>"
Set-AntiphishPolicy -Identity $name -EnableAntiSpoofEnforcement $false

```

如果您不知道要停用的原則 （或原則） 的名稱，則可以將它們顯示：
  
```
Get-AntiphishPolicy | fl Name
```

如果您沒有任何現有的防網路釣魚原則，您可以建立一個並再將其關閉 （即使您不需要原則反詐騙是仍套用; 稍後在 2018年、 將為您建立的預設原則，可以再停用，而不是建立一個）. 您必須在多個步驟中執行這項操作：
  
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
# Finally, scope the anti-phishing policy to the domains
Set-AntiphishPolicy -Identity $name -EnableAntispoofEnforcement $false

```

停用反詐騙只有透過指令程式 (稍後將會出現在 [安全性&amp;合規性中心)。 如果您不具備 PowerShell 存取權，建立支援票證。
  
請記住，這只應該套用到經歷間接路由傳送至 Office 365 時的網域。 抵禦若要停用反詐騙 」，因為某些誤判誘惑，它會是比較好的作法，長期透過其運作。
  
### <a name="information-for-individual-users"></a>針對個別使用者的資訊

個別使用者僅限於它們如何互動的反詐騙安全提示使用。 不過，有幾件事，您可以解決常見的案例。
  
### <a name="common-scenario-1---mailbox-forwarding"></a>常見的案例 #1-信箱轉寄功能

如果您使用另一個電子郵件服務，並將您的電子郵件轉寄給 Office 365 或 Outlook.com，您的電子郵件可能會標示為詐騙和接收的紅色的安全提示。 Office 365 和 Outlook.com 計劃自動解決這個問題時轉寄站是下列其中一個 Outlook.com、 Office 365、 Gmail 或任何其他服務，會使用[弧度通訊協定](https://arc-spec.org)。 不過，直到部署修正的目標，則使用者應該使用連接的帳戶功能直接匯入他們的郵件，而不是使用 [轉寄] 選項。
  
若要設定已連線的帳戶，在 Office 365 中，選取 [齒輪圖示中右上角的 Office 365 web 介面\>郵件\>郵件\>帳戶\>連線的帳戶。
  
![Office 365-連接帳戶] 選項](media/e8e841ca-8861-4d83-8506-2a0858c51010.jpg)
  
在 Outlook.com 中的程序是齒輪圖示\>選項\>郵件\>帳戶\>連線的帳戶。
  
### <a name="common-scenario-2---discussion-lists"></a>常見的案例 #2-討論區清單

討論區清單已知會有問題的反詐騙方式因為它們轉寄訊息和修改其內容仍保留從原始： 地址。
  
例如，假設您的電子郵件地址使用者 @ contoso.com，且您感興趣小鳥監控並加入 @ example.com 討論區清單 birdwatchers。 當您將郵件傳送至討論區清單時，您可能會傳送其這種方式：
  
**從：** John Doe \<@ contoso.com 的使用者\> 
  
**至：** Birdwatcher 的討論區清單\<birdwatchers @ example.com\> 
  
**Subject:** 絕佳檢視的藍色 jays 周頂端 火山本週 
  
任何人都要取出檢視從周本週 火山嗎？
  
當電子郵件清單接收郵件時，它們格式化郵件、 修改它的內容，並重播其餘部分所組成的參與者許多不同的電子郵件接收器討論區清單上的成員。
  
**從：** John Doe \<@ contoso.com 的使用者\> 
  
**至：** Birdwatcher 的討論區清單\<birdwatchers @ example.com\> 
  
**Subject:**[BIRDWATCHERS]絕佳檢視的藍色 jays 周頂端 火山本週 
  
任何人都要取出檢視從周本週 火山嗎？
  
---
  
此訊息已傳送至 Birdwatchers 討論區清單。 您可以隨時取消訂閱。
  
在上述，重新執行的郵件已經從相同： 地址 （@ contoso.com 的使用者） 但原始郵件，已由將標記新增至 [主旨] 行中和郵件底端頁尾中進行修改。 這種類型的訊息修改在郵件清單中很常見，而可能導致誤判。
  
如果您或貴組織中的人員郵寄清單的管理員，您可以將它設定成通過反詐騙檢查。
  
- 檢查 dmarc.org 常見問題集：[我操作郵寄清單我想要與 DMARC 交互操作，我該怎麼辦？](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F)

- 閱讀此部落格文章的指示：[使用 DMARC 來避免失敗交互操作的郵寄清單運算子提示](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/)

- 請考慮支援弧線中點，請參閱郵寄清單伺服器上安裝更新[https://arc-spec.org](https://arc-spec.org/)

如果您不需要的郵件清單的擁有權：
  
- 您可以要求郵寄清單維護的程式，來實作其中一個選項上述 （他們應該也會有電子郵件驗證為郵寄清單轉送從網域設定）

- 您可以在您的電子郵件用戶端，將郵件移至收件匣中建立信箱規則。 您也可以要求您的組織系統管理員設定允許規則，或一節中討論覆寫為管理合法寄件者所傳送未驗證的電子郵件

- 您可以使用 Office 365，以建立要把它當成合法郵寄清單覆寫建立支援票證

### <a name="other-scenarios"></a>其他案例

1. 如果這兩個以上的常見案例適用於您的情況，郵件，則為 false 正數後向 Microsoft 報告郵件。 如需詳細資訊，請參閱一節[方式可以我回報垃圾郵件或非垃圾郵件給 Microsoft？](#how-can-i-report-spam-or-non-spam-messages-back-to-microsoft)本文稍後。 

2. 您也可以連絡可以引發為與 Microsoft 支援票證您電子郵件系統管理員。 Microsoft 工程團隊將調查為何郵件被標示為詐騙。

3. 此外，如果您知道誰寄件者且有自信它們不被惡意會遭到詐騙，您可能會回覆回到寄件者指出他們會從不會驗證郵件伺服器傳送郵件。 這有時會導致連絡其 IT 系統管理員，就會設定必要的電子郵件驗證記錄原始寄件者。
  
當足夠的寄件者回覆回到網域擁有者，他們應該設定電子郵件驗證記錄時，它 spurs 它們採取的動作。 雖然 Microsoft 也可用於發佈所需的記錄的網域擁有者，它可以協助更為個別使用者要求時才。

4. （選用），將寄件者新增至您的安全寄件者清單。 然而，請注意，如果 phisher 假裝該帳戶，它將會傳遞至您的信箱。 因此，應該謹慎使用此選項。

## <a name="how-senders-to-microsoft-should-prepare-for-anti-spoofing-protection"></a>Microsoft 的寄件者應如何準備反詐騙保護

如果您是系統管理員及目前將郵件傳送給 Microsoft 的 Office 365 或 Outlook.com 中，您應該確定已正確地驗證您的電子郵件可能將它標示為垃圾郵件或釣魚程式的否則。
  
### <a name="customers-of-office-365"></a>Office 365 的客戶

如果您是 Office 365 客戶，而且您使用 Office 365 來傳送外寄電子郵件：
  
- 為您的網域，[以協助防止詐騙的 Office 365 中設定 spf](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

- 為您主要的網域，[使用 DKIM 驗證從您在 Office 365 中的自訂網域傳送的外寄電子郵件](use-dkim-to-validate-outbound-email.md)

- [考慮 DMARC 的記錄設定](use-dmarc-to-validate-email.md)為您的網域至判斷誰是您合法的寄件者

Microsoft 並不提供詳細的實作指導方針的每個 SPF、 DKIM 和 DMARC。 不過，有很多線上發佈的資訊。 也有 3rd 廠商公司致力於協助您設定電子郵件驗證記錄的組織。
  
### <a name="administrators-of-domains-that-are-not-office-365-customers"></a>不是 Office 365 客戶的網域的系統管理員

如果您是網域系統管理員，但不是 Office 365 客戶：
  
- 您應該設定 spf 以發佈您的網域傳送的 IP 位址和也設定 dkim （如果有的話） 來數位簽署的郵件。 您也可能會考慮設定 DMARC 的記錄。

- 如果您有大量的寄件者傳輸代表您的電子郵件，您應該使用它們來傳送電子郵件的方式，在 [從的傳送端網域： 地址 （如果它屬於您） 配合通過 SPF 或 DMARC 的網域。

- 如果您有內部部署郵件伺服器，或傳送從軟體為-服務提供者，或從雲端主控服務，例如 Microsoft Azure、 GoDaddy、 Rackspace Amazon Web 服務，或類似，您應該確定他們已新增至您的 SPF 記錄。

- 如果您的 ISP 所裝載的小型網域，您應該設定您的 SPF 記錄根據指示您的 ISP 所提供給您。 大部分的 Isp 提供這些類型的指示，以及可以找到該公司支援頁面上。

- 即使尚未發佈電子郵件之前，先驗證記錄和它的正常運作，您仍然必須發佈電子郵件驗證記錄傳送給 Microsoft。 如此一來，您會在網路釣魚，對抗幫助，並降低您傳送給，組織會收到 phished。

### <a name="what-if-you-dont-know-who-sends-email-as-your-domain"></a>如果您不知道誰做為您網域傳送電子郵件？

許多網域不要發行 SPF 記錄，因為它們不知道其所有寄件者屬於。 沒關係，您不需要知道誰全都是。 相反地，您應該開始發佈您知道，尤其是您公司的流量的所在位置，和發佈中性 SPF 原則] 中，為的 SPF 記錄？ 所有：
  
example.com IN TXT 」 v = spf1 include:spf.example.com？ 所有 」
  
中性 SPF 原則表示任何有超出您公司的基礎結構的電子郵件會傳送電子郵件驗證所有其他電子郵件接收器。 來自您不了解寄件者的電子郵件將會回復為 neutral、 幾乎相同，所有發佈沒有 SPF 記錄。
  
傳送到 Office 365 時，將會是來自您公司的流量的電子郵件標示為通過驗證，但來自您不了解的來源電子郵件仍可能會標示為詐騙 （取決於 Office 365 可以以隱含方式來驗證它）。 不過，這仍然是從所有電子郵件被標示為詐騙由 Office 365 改進。
  
一旦您已取得入門的後援原則與 SPF 記錄？ 所有，您可以逐步包含更傳送基礎結構，並再將發佈更嚴格的原則。 
  
### <a name="what-if-you-are-the-owner-of-a-mailing-list"></a>如果要擁有者的郵件清單？

請參閱[常見的案例 #2-討論區清單](#common-scenario-2---discussion-lists)一節。
  
### <a name="what-if-you-are-an-infrastructure-provider-such-as-an-internet-service-provider-isp-email-service-provider-esp-or-cloud-hosting-service"></a>如果您是基礎結構提供者，例如網際網路服務提供者 (ISP)、 電子郵件服務提供者 (ESP) 或雲端託管服務？

如果裝載網域的電子郵件，且其傳送電子郵件，或提供主控的基礎結構，可以傳送電子郵件，您應該執行下列動作：
  
- 確保客戶擁有細部要在其 SPF 記錄中發佈的文件

- 請考慮登入外寄電子郵件的 DKIM 簽章，即使客戶不會明確設定它 （符號與預設網域）。 您可以偶數雙登 （一次與客戶的網域，如果他們有設定它，第二次與貴公司的 DKIM 簽章） 的 DKIM 簽章的電子郵件

即使您驗證電子郵件來自您的平台，但至少它可確保 Microsoft 不會不垃圾電子郵件因為它不會驗證，請務必遵循傳送給 Microsoft 並不保證。 周圍 Outlook.com 如何篩選電子郵件的詳細資訊，請參閱[Outlook.com 郵件管理員] 頁面](https://postmaster.live.com/pm/postmaster.aspx)。
  
如需詳細的服務提供者最佳作法的詳細資訊，請參閱 < <b0>M3AAWG 行動通訊的最佳作法服務提供者</b0>。
  
## <a name="frequently-asked-questions"></a>常見問題集

### <a name="why-is-microsoft-making-this-change"></a>為什麼 Microsoft 正在進行這項變更？

由於影響的網路釣魚攻擊，和電子郵件驗證已繞 15 年，因為 Microsoft 會認為，繼續允許未經驗證的電子郵件的風險是高於遺失合法電子郵件的風險。
  
### <a name="will-this-change-cause-legitimate-email-to-be-marked-as-spam"></a>這項變更會導致合法的電子郵件被標示為垃圾郵件？

首先，會有一些標示為垃圾郵件的郵件。 不過，經過一段時間，會自動調整寄件者，然後誤標為冒名郵件數量將會極小大部分的電子郵件路徑。
  
Microsoft 本身先採用這項功能數週，再將其部署至其客戶的其餘部分。 第一次中斷時，它會逐漸拒絕。
  
### <a name="will-microsoft-bring-this-feature-to-outlookcom-and-non-advanced-threat-protection-customers-of-office-365"></a>將 Microsoft 將帶到 Outlook.com 和非-進階威脅防護的客戶，Office 365 的這項功能嗎？

Microsoft 的反詐騙技術最初部署給其組織有 Office 365 企業版 E5 訂閱，或有購買其訂閱的 Office 365 進階威脅防護 (ATP) 附加元件。 截至 2018 年 10 月，我們已擴充，也有 Exchange Online Protection (EOP) 的組織保護。 在未來，我們可能會對 Outlook.com 釋出它。 不過，如果我們這麼做，可能會有一些功能，例如報告不會套用及自訂會覆寫。
  
### <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>我如何可以回報垃圾郵件或非垃圾郵件給 Microsoft？

您可以使用此[報告訊息增益集以進行 Outlook](https://support.office.com/article/use-the-report-message-add-in-b5caa9f1-cdf3-4443-af8c-ff724ea719d2)，或如果它不是安裝，[提交垃圾郵件、 非垃圾郵件和網路釣魚詐騙郵件提交給 Microsoft 進行分析](https://technet.microsoft.com/en-us/library/jj200769%28v=exchg.150%29.aspx)。
  
### <a name="im-a-domain-administrator-who-doesnt-know-who-all-my-senders-are"></a>我不知道我所有的寄件者屬於網域管理員 ！

請[系統管理員的網域都不是 Office 365 客戶](#administrators-of-domains-that-are-not-office-365-customers)，參閱。
  
### <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization-even-though-office-365-is-my-primary-filter"></a>發生什麼事我停用反詐騙保護我的組織，即使 Office 365 是我主要的篩選條件？

我們不建議這因為您將會公開給更多未接的網路釣魚和垃圾郵件。 並非所有網路釣魚詐騙，並將未接並非所有詐騙。 不過，您的風險會高於可讓反詐騙的客戶。
  
### <a name="does-enabling-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>啟用反詐騙保護意思我將會從所有網路釣魚保護？

不幸的是，否，因為網路釣客會調整以使用其他技術，例如： 遭到盜用的帳戶或設定的可用服務的帳戶。 不過，反網路釣魚保護因為 Office 365 的保護層級會一起設計工作將這些偵測其他類型的網路釣魚方法，並建置彼此運作更好。
  
### <a name="do-other-large-email-receivers-block-unauthenticated-email"></a>其他大型的電子郵件接收器封鎖未驗證的電子郵件？

幾乎所有大型的電子郵件接收器實作傳統 SPF、 DKIM 和 DMARC。 某些接收器有其他檢查比只是這些標準，但較少移為 Office 365，以封鎖未驗證的更嚴格的電子郵件並將它們視為詐騙。 不過，大部分的產業變得更嚴格有關此特定類型的電子郵件，尤其是因網路釣魚的問題。
  
### <a name="do-i-still-need-the-advanced-spam-filtering-option-enabled-for-spf-hard-fail-if-i-enable-anti-spoofing"></a>仍是否需要啟用 「 SPF 硬失敗 」 如果啟用反詐騙的進階垃圾郵件篩選選項？

否，此選項已不再需要因為 SPF 硬失敗，但更多組準則的不只會考慮的反詐騙的功能。 如果您有反詐騙啟用，且已啟用 [SPF 硬失敗] 選項，可能就會更多的誤判。 我們建議您停用此功能，因為它會提供幾乎沒有其他 catch 垃圾郵件或釣魚程式，並改為產生大部分誤判。
  
### <a name="does-sender-rewriting-scheme-srs-help-fix-forwarded-email"></a>沒有寄件者修正配置 (SRS)，協助修正轉寄電子郵件？

SRS 只有部分修正問題的轉寄電子郵件。 修正 SMTP 郵件從，SRS 能確保，在下一個目的地轉寄的郵件通過 SPF。 不過，因為反詐騙根據 From： 地址搭配 [MAIL FROM 或 DKIM 簽章的網域 （或其他信號），它不是足夠，防止轉寄電子郵件被標示為詐騙。