---
title: 對抗垃圾郵件傳送給 Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 5fd7d05b-96db-456f-81d6-1ac0e5bff530
description: Microsoft 的電子郵件 safety 藍圖涉及不相符的跨產品方法。Exchange Online Protection (EOP) 反垃圾郵件和反網路釣魚篩選技術套用跨整個網路的創新的最新反垃圾郵件和反網路釣魚的工具與提供使用者的 Microsoft 的電子郵件平台。EOP 的目標是了解提供可協助偵測及保護使用者免於垃圾郵件、 詐騙的電子郵件威脅 （網路釣魚） 和惡意程式碼的完整及可用狀態電子郵件服務。
ms.openlocfilehash: dafcb827a323461936eadcd00c37fabd43005a80
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026350"
---
# <a name="fighting-junk-email-sent-to-office-365"></a>對抗垃圾郵件傳送給 Office 365

Microsoft 的電子郵件 safety 藍圖涉及不相符的跨產品方法。Exchange Online Protection (EOP) 反垃圾郵件和反網路釣魚篩選技術套用跨整個網路的創新的最新反垃圾郵件和反網路釣魚的工具與提供使用者的 Microsoft 的電子郵件平台。EOP 的目標是了解提供可協助偵測及保護使用者免於垃圾郵件、 詐騙的電子郵件威脅 （網路釣魚） 和惡意程式碼的完整及可用狀態電子郵件服務。
  
## <a name="the-challenge"></a>挑戰

電子郵件已經成為重要通訊工具的取用者不僅上月、 支援人員、 銷售組織及所有規模的企業。如已增加至電子郵件使用，所以有電子郵件不當使用。不受監控的垃圾郵件可以午前收件匣和網路、 影響使用者滿意度與阻礙效益的合法電子郵件通訊。這就是為什麼 Microsoft 反垃圾郵件技術投資會繼續。簡單來說，啟動由包含和篩選垃圾郵件。 
  
## <a name="our-efforts"></a>我們的努力

EOP 提供數項步驟來減少垃圾郵件對我們使用者的電子郵件體驗的負面影響。
  
### <a name="exchange-online-protection-technology"></a>Exchange Online Protection 技術

若要協助減少垃圾郵件，EOP 會包括垃圾郵件保護使用專屬的 EOP 篩選技術螢幕電子識別及隔開合法電子郵件的垃圾郵件。從已知的垃圾郵件和網路釣魚威脅及使用者意見反應從我們取用者平台，Outlook.com 可學習 EOP 內容篩選器。這些資料型別的協助訓練 EOP 技術來辨識合法電子郵件及垃圾郵件和是將寄件者信譽的索引鍵輸入。進行中的意見反應 EOP 中的使用者垃圾郵件分類程式有助於確保 EOP 技術會持續經過訓練和改良。
  
#### <a name="how-does-eop-work"></a>EOP 的運作方式

當外部使用者傳送的電子郵件至 EOP 使用者時，EOP 篩選技術評估郵件的內容及分級給郵件根據郵件為垃圾郵件的機率。此評等會儲存為呼叫本身的郵件內垃圾郵件信賴等級 (SCL) message 屬性。Scl 保持訊息傳送到 EOP 內其他反垃圾郵件保護層級如下。 
  
設定 EOP 內的規則來處理附有各種 SCL 評等的電子郵件訊息。如果郵件未 scl 高於特定臨界值，它會被視為垃圾郵件。將隔離或傳遞給使用者的垃圾郵件資料夾根據系統管理員如何設定垃圾郵件的傳遞選項的郵件。
  
#### <a name="eop-filters"></a>EOP 篩選器

除了反垃圾郵件篩選技術 EOP 也讓系統管理員可以設定篩選層級進一步自訂電子郵件傳送至其使用者帳戶。管理員可以輕易地新增寄件者或網域名稱的安全寄件者和網域清單以便從該寄件者或網域的電子郵件永遠不會被視為垃圾郵件的內容不論。資訊，請參閱[安全寄件者和封鎖寄件者清單在 Exchange Online](safe-sender-and-blocked-sender-lists-faq.md)。
  
### <a name="phishing-protection"></a>網路釣魚保護

網路釣魚 （明顯"釣魚"） 會形式的身分識別竊取另一個網際網路上的速度最快成長威脅。您通常可以識別詐騙郵件時該要求個人或財務資訊或包含要求這類資訊的網站的連結。EOP 提供網路釣魚保護專屬的 EOP 篩選技術的一部分。EOP 篩選技術分析可協助偵測詐騙連結或可協助保護使用者免於這些類型的線上詐騙詐騙的網域的電子郵件。
  
#### <a name="how-does-phishing-protection-work"></a>網路釣魚保護如何運作？

通常的網路釣魚電子郵件將傳送包含連結，一次點選連結將使用者重新導向至詐騙網站以顯示有效 （例如您的年金融機構或線上服務）。此網路釣魚網站通常會提示使用者輸入使用者名稱、 密碼和社會安全編號的個人資訊。您輸入網路釣魚網站的任何資訊可協助竊取您的身分 phisher。藉由使用已知受信任的品牌名稱及標誌、 網路釣客就能夠看起來像是合法的。網路釣魚篩選技術提供在 EOP 檢查的電子郵件中的潛在網路釣魚特性。如果找到電子郵件移至 [垃圾郵件] 資料夾。
  
Microsoft 已將其反網路釣魚技術的努力著重在兩個正面： 先以協助防止網路釣魚電子郵件即將達到我們的使用者與第二個協助去除使用者正在 deceived 由詐騙的電子郵件與網站的可能性。 
  
> [!TIP]
> Internet Explorer 版本 7 及高於會封鎖或警告使用者他們造訪已知或潛在網路釣魚網站使其不誘騙提供個人資訊時。[請確定您具有最新版本的 Internet Explorer](https://www.microsoft.com/windows/ie/default.mspx)。 
  
#### <a name="authentication"></a>驗證

詐騙網域是一種模仿合法電子郵件地址進行詐騙看起來合法的電子郵件。詐騙用以惡意的個人或組織的網路釣魚詐騙誘人員 divulging 機密的個人資訊。識別竊取和其他類型詐騙的可能會導致此類資訊的揭露。
  
若要確認郵件是來自這些宣告來自網域 EOP 使用寄件者保護 Framework (SPF)、 DomainKeys 識別郵件 (DKIM) 和網域式訊息驗證、 報告和符合性 (DMARC) 和其他隱含的驗證.我們建議所有寄件者以防止垃圾郵件和網路釣魚詐騙其收件者使用 SPF 和 DKIM。建議的寄件者，請考慮發佈 DMARC 拒絕或隔離從未經授權的寄件者傳送的郵件。
  
- 若要深入了解 SPF，請參閱[RFC 7208](https://tools.ietf.org/html/rfc7208)和[寄件者原則架構](http://www.openspf.org/)。
    
- 若要深入了解 DKIM，請參閱[RFC 6376](https://tools.ietf.org/html/rfc6376)和[DKIM.org](http://dkim.org/)。
    
- 若要深入了解 DMARC，請參閱[DMARC.org](https://dmarc.org/)。
    
### <a name="legislation"></a>立法

在 Microsoft，我們認為開發的新技術與自我法規需要有效政府原則及法律架構的支援。全世界的垃圾郵件激增具有刺激管理商業電子郵件的許多國家立法本文。許多國家/地區現在已經備妥的垃圾郵件對抗法。美國聯邦及狀態法管理垃圾郵件，而且這個互補方法協助縮減同時啟用至繁榮的合法電子商務網路侵入垃圾郵件。可以垃圾郵件動作會展開可用 curbing 詐騙和詐騙電子郵件訊息的工具。
  

