---
title: 控制 Office 365 的輸出垃圾郵件
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 09/18/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
description: 如果您的組織傳送大量大宗郵件標記為垃圾郵件，您無法取得封鎖，禁止傳送電子郵件與 Office 365。請閱讀本篇文章以深入了解發生的原因以及可以怎麼有關它。
ms.openlocfilehash: c5baf12b9b54e46e3863e33172cfb7339227e309
ms.sourcegitcommit: 122646e570bb13e93d4fdc5090bdd25ed65d1997
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2018
ms.locfileid: "23998972"
---
# <a name="controlling-outbound-spam-in-office-365"></a>控制 Office 365 的輸出垃圾郵件

我們採用嚴重因為我們的共用的服務管理輸出垃圾郵件。 有許多客戶背後的其中一個客戶傳送輸出垃圾郵件，如果它可能會降低服務的輸出 IP 信譽及影響其他客戶的電子郵件成功既的資源共用集區。它則公平至客戶的客戶 B spams 和各種 3rd 方 IP blocklists 清單它會使用的 IP 位址。

## <a name="what-admins-can-do-to-control-outbound-spam"></a>系統管理員可以執行控制輸出垃圾郵件

- **啟用帳戶傳送垃圾郵件或關閉時的通知**。系統管理員可以取得之密件副本接收者每當郵件已標示為 「 輸出垃圾郵件和傳送到高風險集區。藉由監視這個信箱，系統管理員可以偵測如果其網路中有洩漏的帳戶或垃圾郵件篩選已遭標示為垃圾郵件的電子郵件。 在設定輸出垃圾郵件原則的詳細資訊可以找到[以下](configure-the-outbound-spam-policy.md)。
 
- **手動檢閱 [垃圾郵件客訴來自 3rd 方電子郵件提供者**。如 Outlook.com、 Yahoo 和 AOL 許多 3rd 方電子郵件服務提供意見反應迴圈其中其服務中的任何使用者會標示為垃圾郵件我們服務的電子郵件，如果郵件是封裝而對我們傳送以供檢閱。若要深入了解 Outlook.com 的寄件者支援，請按一下[這裡](https://sendersupport.olc.protection.outlook.com/pm/services.aspx)。

## <a name="what-eop-does-to-control-outbound-spam"></a>EOP 沒有控制輸出垃圾郵件 

1. **將 Ip 的個別集區的輸出流量的區隔**。客戶傳送輸出透過服務每封郵件會掃描的垃圾郵件。如果郵件為垃圾郵件，它會路由傳送到高風險傳遞集區。此 IP 集區會包含非可傳送作業的狀態通知和垃圾郵件。傳遞至預定的收件者不保證為許多第三方將不會接受電子郵件因為它會發出的電子郵件的品質。</br></br>分割流量這種方式可確保較低品質電子郵件 （垃圾郵件、 非法回應 Ndr） 不會不拖曳下信譽之規則的外寄電子郵件集區。雖然這不是通用高風險集區通常是在網際網路周圍的許多接收器具有低信譽。 

2. **監控的 IP 信譽**。Office 365 查詢各種 3rd 方 IP blocklists 並如果我們輸出 Ip 的任何已列在這些通知就會產生。這可讓我們時垃圾郵件具有造成來降低我們信譽快速回應。時就會產生警示，我們有內部文件外圍取得 delisted 所採取的步驟。 

3. **停用的違規帳戶傳送太多的電子郵件時已標記為垃圾郵件**。即使我們隔離我們垃圾郵件和非垃圾郵件至兩個不同輸出 IP 集區、 電子郵件帳戶不能無限期傳送垃圾郵件。我們監視哪些帳戶已傳送垃圾郵件與帳戶如果超過保密的限制，禁止傳送垃圾郵件。</br></br>單一郵件標記為垃圾郵件可能是垃圾郵件引擎，又稱為誤判 misclassification。我們傳送透過將其命名的移出; 機會高風險集區不過，大量的簡短時間圖文框中的訊息表示問題以及時，會發生，我們封鎖從傳送任何更多的電子郵件帳戶。有不同存在個別電子郵件帳戶，以及如彙總整個承租人所示的臨界值。

4. **停用的違規帳戶傳送太多太短時間圖文框中的電子郵件時**。除了上述的外觀比例標示為垃圾郵件的限制，也有封鎖帳戶達到不論將郵件標示為垃圾郵件整體限制時的限制。此限制存在的原因是因為洩漏的帳戶無法傳送垃圾郵件篩選器所未接的零時差垃圾郵件。因為很難，如果沒有之前，有時告知合法的大量郵寄行銷活動及大規模的垃圾郵件 campaign 之間的差異，這些限制會啟用限制任何潛在的傷害。

> [!NOTE]
> #3 與 #4 我們未通告的確切限制。 這是以防止垃圾郵件傳送者從遊戲系統並確定我們可以時我們需要變更限制。限制是損害的不夠高如此平均商務使用者永遠不會瀏覽其和低它包含大部分的垃圾郵件的用途。 

## <a name="recommended-workarounds-for-customers-who-want-to-send-outbound-a-lot-of-email-through-eop"></a>對於要傳送輸出許多的電子郵件到 EOP 的客戶的建議解決方法

很難將客戶想要傳送大量電子郵件和比較防止入侵的帳戶和大量 emailers 與不良清單取得作法的服務之間的平衡。同樣地，輸出 IP 登陸 3rd 的廠商封鎖清單上的成本是高於封鎖客戶傳送輸出電子郵件。[Exchange Online 服務說明](https://technet.microsoft.com/library/exchange-online-limits.aspx#RecipientLimits)所述，使用 EOP 來傳送大量電子郵件不支援使用的服務與只允許"最佳投入比 」 為基礎。要傳送大量電子郵件的客戶，我們建議下列項目：

1. **傳送到其本身的內部部署郵件伺服器的大量電子郵件**。這表示客戶必須維護自己電子郵件的基礎結構這種類型的電子郵件。

2. **使用第 3 協力廠商對大量 emailer 傳送大量的通訊**。有數個 3rd 廠商大量 emailers 要事業很傳送大量電子郵件。它們可搭配客戶確認他們具有良好電子作法擁有專用於強制執行它的資源。 

通訊、 行動、 惡意程式碼反不當使用工作群組 (MAAWG) 發佈其成員資格名冊[此處](http://www.maawg.org/about/roster)。數個大量電子郵件提供者清單上與名為負責網際網路市民。 
  
## <a name="for-more-information"></a>如需詳細資訊

[當封鎖寄件者時傳送輸出垃圾郵件的範例通知](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md)

[Office 365 電子郵件的反垃圾郵件保護](anti-spam-protection.md)

[Office 365 的反詐騙保護](anti-spoofing-protection.md)

[垃圾郵件信賴等級](spam-confidence-levels.md)
