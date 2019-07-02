---
title: Office 365 中的監督原則
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
description: 深入瞭解 Office 365 中的監督原則
ms.openlocfilehash: d802fb0e17894a769fb330aa5f080fbd6151b44e
ms.sourcegitcommit: 3699da2cad6e6a2002083e2884e32393dacab0ca
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2019
ms.locfileid: "34694707"
---
# <a name="supervision-policies-in-office-365"></a>Office 365 中的監督原則

Office 365 中的監督原則可讓您透過指定的檢閱者來捕獲員工的通訊以進行檢查。 您可以在組織中定義用來捕獲內部和外部電子郵件、Microsoft 小組或協力廠商通訊的特定原則。 然後, 檢閱者可以檢查郵件, 以確保它們符合您組織的郵件標準, 並使用分類類型加以解決。 

這些原則也可協助您克服許多現代化的規範挑戰, 包括:

- 監視日益增加的通訊通道類型
- 不斷增加的郵件資料量
- 法規強制執行 & 罰款的風險

在某些組織中, 可能會將 IT 支援與規範管理群組之間的責任分開。 Office 365 支援在監督原則功能設定與已捕獲通訊原則的設定之間的分隔。 例如, 組織的 IT 群組可能負責設定角色許可權和群組, 以支援由組織的合規性小組設定和管理的監督原則。

如需監督原則的快速流覽, 請參閱[Microsoft 機械通道](https://www.youtube.com/user/OfficeGarageSeries)上的[監督原則影片](https://youtu.be/C3Y8WZ7o_dI)。

若要深入瞭解未來的監督功能的改善與可用性, 請參閱[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)。

## <a name="scenarios-for-supervision-policies"></a>監督原則的案例

監督原則可協助您在多個方面監視組織中的通訊:

- **公司原則**

    員工必須遵守其所有商務相關通訊中可接受的使用、道德標準及其他公司原則。 監督原則可偵測原則違規, 並協助您採取糾正動作, 協助緩解這些類型的事件。 例如, 您可以監視貴組織是否有潛在的人力資源違規, 例如騷擾或在員工通訊中使用不適當或攻擊性的語言。

- **風險管理**

    組織負責所有在其基礎結構與公司網路系統之間分散的通訊。 使用監督原則來協助識別和管理潛在的法律暴露和風險, 可協助降低風險, 使其無法損毀公司的運作。 例如, 您可以針對機密專案 (如即將進行的收購、合併、收入披露、reorganizations 或領導小組變更), 監視您的組織是否有未經授權的通訊。

- **規範合規性**

    大部分的組織必須遵守某種類型的法規規範標準, 作為其正常運作程式的一部分。 這些法規通常會要求組織對其行業所適用的訊息執行某種類型的監督或監督程式。 金融產業規章機關 (FINRA) 規則3110是一種很好的需求, 組織負責制定主管程式, 以監視其員工的活動, 以及參與的公司類型。 另一個範例可能是需要監視組織中的經紀人轉銷商, 以防止潛在的金錢 laundering、內幕交易、collusion 或 bribery 活動。 監督原則可提供監視和報告公司通訊的程式, 協助您的組織符合這些需求。

## <a name="components"></a>零件

### <a name="supervision-policy"></a>監督原則

您可以在規範中心建立監督原則。 這些原則定義您組織中要審查的通訊和使用者、定義通訊必須符合的自訂條件, 以及指定應該執行評論的人員。 包含在主管審查角色群組中的使用者可以設定原則, 以及已指派此角色的任何人都可以存取規範中心內的監督頁面。

### <a name="supervised-users"></a>監督的使用者

開始使用監督之前, 您必須決定誰需要查看其通訊。 在原則中, 使用者的電子郵件地址會識別要監督的個別或一組人員。 這些群組的部分範例包括 Office 365 群組、Exchange 式通訊群組清單和 Microsoft 小組通道。 您也可以從監督的群組或群組清單中排除特定的使用者或群組。

> [!IMPORTANT]
> 監督原則所監視的使用者必須擁有 Microsoft 365 E5 合規性授權、Office 365 企業版 E3 授權與高級合規性附加元件, 或包含在 Office 365 企業版 E5 訂閱中。
如果您沒有現有的企業版 E5 計畫, 而且想要嘗試監督, 您可以[註冊 Office 365 企業版 e5 的試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。

### <a name="reviewers"></a>檢閱者

當您建立監督原則時, 您必須決定誰將對被監督使用者的郵件進行檢查。 在原則中, 使用者電子郵件地址會識別個人或一群人員, 以查看監督的通訊。 所有檢閱者都必須擁有 Exchange Online 上的信箱。

### <a name="groups-for-supervised-users-and-reviewers"></a>監督使用者和檢閱者的群組

若要簡化您的設定, 請為需要查看其通訊的人員建立群組, 並針對審閱這些通訊的人員進行群組。 如果您使用的是群組, 您可能需要數個。 例如, 如果您想要監視兩個不同的人員群組之間的通訊, 或是您想要指定未監督的群組。

### <a name="supported-communication-types"></a>支援的通訊類型

透過監督原則, 您可以選擇在下列一或多個通訊平臺中監視郵件:

- **Exchange 電子郵件:** 在 Exchange Online 上主控的信箱, 作為 Office 365 訂閱的一部分, 皆符合郵件監督的資格。 電子郵件和附件符合監督原則條件可立即供監控和監督報告。 支援的監督附件類型與[Exchange 郵件流程規則內容檢查所支援的檔案類型](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)相同。

- **Microsoft 團隊:** 公開和私人 Microsoft 小組通道和個別交談中的聊天通訊和相關聯的附件都會受到監督。 小組聊天比對監督原則條件每24小時處理一次, 然後即可用於監控和監督報告。 使用下列群組管理設定來監督個別使用者聊天和小組中的通道通訊:

    - **對於小組聊天監督:** 指派個別使用者或將[通訊群組](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE)指派給監督原則。 這適用于1對1或一對多的使用者/聊天關係。
    - **對於小組通道通訊:** 將您想要監視且包含特定使用者的每個 Microsoft 小組通道或 Office 365 群組指派給監督原則。 如果您將相同的使用者新增至其他 Microsoft 小組通道或 Office 365 群組, 請務必將這些新的通道和群組新增至監督原則。

- **商務用 Skype Online:** 您可以監督商務用 Skype Online 中的聊天通訊和相關聯的附件。 商務用 Skype Online 研討符合監督原則條件, 每24小時就會處理一次, 然後即可監視和監督報告。 受監督的交談對話源于[先前在商務用 Skype Online 中所儲存的交談](https://support.office.com/article/Find-a-previous-Skype-for-Business-conversation-18892eba-5f18-4281-8c87-fd48bd72e6a2)。  在商務用 Skype Online 中使用下列群組管理設定來監督使用者聊天通訊:

    - **針對商務用 Skype Online 聊天室監督:** 指派個別使用者或將[通訊群組](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE)指派給監督原則。 這適用于1對1或一對多的使用者/聊天關係。

- **協力廠商來源:** 您可以監督協力廠商來源 (例如 Facebook 或 DropBox) 的通訊, 以用於匯入組織中的 Office 365 信箱中的資料。 [瞭解如何將協力廠商資料匯入 Office 365](https://docs.microsoft.com/office365/securitycompliance/archiving-third-party-data)。

依預設, 每個原則在這些平臺上捕獲的通訊會保留七年, 即使使用者離開貴組織及其信箱也是如此。

### <a name="policy-settings"></a>原則設定

#### <a name="direction"></a>方向

依預設, 會顯示**方向為**[條件], 且無法移除。 原則中的通訊方向設定會個別或一起選擇:

- **輸入**: 您可以選擇 [**輸入**], 以查看傳送**給**您選擇要透過**** 未包含在該原則中的人員進行監督的通訊。
- **輸出**: 如果您想要查看**從**您選擇要監督給未包含在原則中的人員**** 傳送的通訊, 您可以選擇 [**輸出**]。
- **內部**: 您可以選擇 [**內部**], 以查看您在原則中識別的人員**之間**所傳送的通訊。

#### <a name="sensitive-information-types"></a>敏感資訊類型

您可以選擇在監督原則中包含敏感資訊類型。 敏感資訊類型是預先定義或自訂的資料類型, 可協助識別及保護信用卡號碼、銀行帳戶號碼、護照號碼等等。 作為 Office 365[資料遺失防護 (DLP)](data-loss-prevention-policies.md)的一部分, 敏感資訊設定可以使用模式、字元接近度、信賴等級, 甚至是自訂資料類型, 以協助識別和標示可能是敏感的內容。 預設的機密資訊類型如下:

- 財務
- 醫療和健康情況
- 隱私權
- 自訂資訊類型

若要深入瞭解機密資訊的詳細資料以及預設類型中包含的模式, 請參閱[何種敏感資訊類型的外觀](what-the-sensitive-information-types-look-for.md)。

#### <a name="custom-keyword-dictionaries"></a>自訂關鍵字字典

設定自訂關鍵字字典 (或字典), 以提供您組織或行業特有的簡單關鍵字管理。 關鍵字字典支援每個字典最多100000個字詞。 如有需要, 您可以將多個自訂關鍵字字典套用至單一原則, 或將單一關鍵字字典套用至每個原則。 這些字典是在監督原則中指派, 可以從檔案 (例如 .csv 或 .txt 清單), 或是從[規範中心匯入](create-a-keyword-dictionary.md)的清單中。

#### <a name="offensive-language"></a>攻擊性語言

在您的組織中監視已傳送或接收的電子郵件, 以取得攻擊性的語言。 模型使用機器學習、人工智慧和關鍵字的組合, 來識別不適當的電子郵件, 作為反騷擾和網路霸淩監視需求的一部分。 若要防止或封鎖組織中其他通訊的攻擊性語言, 請建立使用攻擊性字詞[自訂關鍵字字典](create-a-keyword-dictionary.md)的[資料遺失防護原則](create-test-tune-dlp-policy.md)。

攻擊性語言模型目前支援英文關鍵字, 並監視電子郵件的本文。 攻擊性語言模型會監視與下列語言類型相關聯的 sentiment 電子郵件:

|**類型**|**描述**|
|:-----|:-----|
| **Profanities** | 不適當且 embarrass 大多數人員的運算式。 |
| **Slurs** | 攻擊區域性和 ethnicities 的運算式。 |
| **Taunts** | Taunt、condemn 及 ridicule 的運算式。 |
| **Handicaps 的參照** | 瞄準實體或精神 handicaps 的運算式。 |
| **Squalid 語言** | Cleanliness 的色情興趣和實體狀態的運算式。 |
| **Homophobia** | 以 [色情喜好設定] 的運算式。 |
| **Racism** | 目標為種族和 ethnicity 的運算式。 |
| **Extremism** | 瞄準宗教和政治 ideologies 的運算式。 |
| **偽裝** | 含義或發音與另一個更具冒犯性字詞相同的運算式。 |
| **Provocative 語言** | 可能導致 anger 或暴力的運算式。 |
| **Taboo** | 運算式在禮貌的 societal 通訊中通常不正確。 |
| **Unrefined 語言** | 沒有禮貌 manners, 且可能會對和強制的運算式。 |

#### <a name="conditional-settings"></a>條件式設定

您針對原則所選擇的條件, 會套用到您組織中的電子郵件和協力廠商來源的通訊 (例如 Facebook 或 DropBox)。

下表說明每個條件的詳細資訊。
  
|**條件**|**如何使用此條件**|
|:-----|:-----|
| **從這些網域接收郵件**  <br><br> **不是從這些網域接收郵件** | 套用原則, 以在收到的郵件中包含或排除特定網域或電子郵件地址。 輸入每個網域或電子郵件地址, 並以逗號分隔多個網域或電子郵件地址。 每個輸入的網域或電子郵件地址都是單獨套用的, 只有一個網域或電子郵件地址必須套用至郵件的原則。 <br><br> 如果您想要監視特定網域中的所有電子郵件, 但想要排除不需要審閱的郵件 (電子報、宣告等), 您必須設定兩個條件: <br> -從任何定義網域 ("contoso.com") 的**網域條件中收到郵件**, 並 <br> -**不會從任何**排除電子郵件地址 ("newsletter@contoso.com") 的網域條件中收到郵件。 |
| **郵件會傳送至這些網域中的任何一個**  <br><br> **郵件不會傳送至這些網域中的任何一個** | 套用原則, 以在已傳送郵件中包含或排除特定網域或電子郵件地址。 輸入每個網域或電子郵件地址, 並以逗號分隔多個網域或電子郵件地址。 每個網域或電子郵件地址都是分開套用, 只有一個網域或電子郵件地址必須套用至該郵件的原則。 <br><br> 如果您想要監視所有傳送至特定網域的電子郵件, 但想要排除不需要審閱的已傳送郵件, 您必須設定兩個條件: <br> -**會將郵件傳送至任何**定義網域 ("contoso.com") 的網域條件, 並 <br> -**不會將郵件傳送至任何**排除電子郵件地址 ("subscriptions@contoso.com") 的網域條件。 |
| **郵件會以這些標籤中的任何一項進行分類**  <br><br> **郵件未使用下列任何一種標籤進行分類** | 在郵件中包含或排除特定保留標籤時套用原則。 保留標籤必須個別設定, 且已設定的標籤是此條件的一部分。 您選擇的每個標籤都是單獨套用的 (只有其中一個標籤必須套用至郵件)。 如需設定保留標籤的詳細資訊, 請參閱[保留標籤](https://docs.microsoft.com/office365/securitycompliance/labels)。|
| **郵件包含其中任何文字**  <br><br> **郵件未包含這些字詞** | 若要在郵件中包含或排除特定字詞或片語時套用原則, 請在個別的行上輸入每個單字或片語。 您輸入的每一行文字都會被個別套用 (這些行中只有一列必須適用于原則套用至郵件)。 如需輸入字詞或片語的詳細資訊, 請參閱下一節比[對電子郵件或附件的文字和片語](supervision-policies.md#Matchwords)。|
| **附件包含其中任何文字**  <br><br> **附件不包含任何文字** | 若要在郵件附件 (例如 Word 檔) 中包含或排除特定字詞或片語時套用原則, 請在個別的行上輸入每個單字或片語。 您輸入的每一行文字都是分開套用 (只有一條線必須套用至該原則, 才能套用至附件)。 如需輸入字詞或片語的詳細資訊, 請參閱下一節比[對電子郵件或附件的文字和片語](supervision-policies.md#Matchwords)。|
| **附件是下列其中一種檔案類型**  <br><br> **附件不屬於這些檔案類型** | 若要監督包含或排除特定類型附件的通訊, 請輸入副檔名 (例如 .exe 或 .pdf)。 如果您想要包含或排除多個副檔名, 請在不同的行上輸入這些副檔名。 要套用的原則只有一個附件副檔名必須符合。|
| **郵件大小大於**  <br><br> **郵件大小不大於** | 若要查看以特定大小為基礎的郵件, 請使用這些條件來指定郵件在受到審閱之前的最大或最小大小。 例如, 如果您指定的**郵件大小大於** \> **1.0 mb**, 則所有 1.01 MB 和更大的郵件都會受到審查。 您可以選擇 [位元組]、[kb]、[mb] 或 [gb] 的條件。|
| **附件大於**  <br><br> **附件不大於** | 若要根據附件的大小來查看郵件, 請指定郵件之前可以有的附件大小上限或最小值。 例如, 如果您指定的**附件** \>大於**2.0 mb**, 則所有具有2.01 附件的郵件都是可供審查的郵件。 您可以選擇 [位元組]、[kb]、[mb] 或 [gb] 的條件。|
   
##### <a name="matching-words-and-phrases-to-emails-or-attachments"></a>比對電子郵件或附件的字詞和片語
<a name="Matchwords"></a>您輸入的每一行文字都會分開套用 (原則條件必須套用一條字, 才能套用至電子郵件或附件)。 例如, 讓我們使用條件,**郵件包含其中的任何字**, 並在不同的行上加上 "銀行家" 和 "內幕交易" 關鍵字。 此原則會套用至任何包含「銀行家」或「「內幕交易」一詞的郵件。 若要套用此原則條件, 只必須有其中一個字或片語。 郵件或附件中的文字必須完全符合您的輸入。
  
##### <a name="enter-multiple-conditions"></a>輸入多個條件

如果您輸入多個條件, Office 365 會同時使用所有條件, 以決定何時將原則套用至通訊專案。 當您設定多個條件時, 必須符合原則套用的所有條件, 除非您輸入例外狀況。 例如, 如果郵件包含 "商貿" 一詞, 且大於 2 MB, 您就需要套用原則。 不過, 如果郵件也包含「由 Contoso 財務核准核准」的文字, 則不應該套用該原則。 因此, 在此情況下, 三個條件如下:
  
- **郵件包含其中的任何字**, 關鍵字為 "商貿"

- **郵件大小大於**, 值為 2 MB

- **郵件不包含這些文字**, 並使用關鍵字「由 Contoso 財務小組核准」

#### <a name="review-percentage"></a>考核百分比

如果您想要減少要查看的內容量, 您可以指定監督原則所管理之所有通訊的百分比。 即時、隨機的內容樣本, 會從符合所選原則條件的內容總百分比選取。 如果您想要檢閱者審閱所有專案, 您可以在監督原則中輸入**100%** 。

## <a name="monitor--manage"></a>監視 & 管理

很容易監視監督原則的結果, 並套用解決標記。 您可以快速查看:

- 已檢查項目的狀態
- 監督的使用者和群組
- 指定為檢閱者的使用者和群組

### <a name="supervision-policy-dashboard"></a>監督原則儀表板

使用 [監督原則] 儀表板來管理監督原則結果, 並解決未完成的專案。 此儀表板可讓檢閱者查看需要審閱的專案、對專案採取動作, 以及查看每個監督原則先前已查看和已解決專案的結果。 您可以在「規範中心」中存取 [監管原則] 儀表板, 以在**監督** > *您的自訂原則* > 時**開啟**。

#### <a name="dashboard-home"></a>儀表板首頁

儀表板**首頁**有數個區段, 可協助您快速地對您的監督原則採取動作。 您可以在這裡進行下列動作:

- 快速查看周的擱置和解決的亮點
- 查看所選原則的已監督使用者和監督群組清單
- 查看所選原則的檢閱者和審查小組清單
- 查看哪些通訊平臺在監督原則下有內容

#### <a name="review-tab"></a>[審閱] 索引標籤

[**回顧**] 索引標籤是檢閱者分類及解析所選取原則所識別的專案。 您可以在這裡進行下列動作:

- 依擱置、相容、不相容和有疑問的專案進行篩選。
- 將單一專案標記為相容、不相容或不值得懷疑。 您也可以記錄專案的批註, 以協助澄清所採取的標記動作。
- 將多個專案大量標記為相容、不相容或不值得懷疑。 您也可以錄製包含多個專案的批註, 以協助澄清所採取的標記動作。
- 針對單一專案, 查看標記的歷程記錄。 包含解決專案的人員、動作的日期和時間、解決標記, 以及任何包含的批註。
- 將先前檢查過的專案重新分類為相容、不相容或有疑問。 您也可以錄製包含一或多個專案的批註, 以協助澄清所採取的重新分類動作。

#### <a name="resolved-items-tab"></a>已解析的專案索引標籤

[**已解決的專案**] 索引標籤是指檢閱者可以在其中查看所選原則的所有先前已解析專案。 您可以在這裡進行下列動作:

- 快速查看和排序所解決專案的主旨、寄件者和日期
- 查看任何選取專案的分類和批註記錄

## <a name="reports"></a>報表

使用監督報告來查看原則和檢閱者層級的 [審閱] 活動。 您也可以針對每個原則, 查看目前 [回顧] 活動狀態的即時統計資料。 您可以使用監督報告來:
  
- 確認您的原則運作正常。
- 找出需要檢查的通訊數目。
- 找出不相容的通訊數目, 以及哪些通訊已通過審閱。 此資訊可協助您決定是否要微調原則, 或變更檢閱者的人數。

### <a name="view-the-supervision-report"></a>查看監督報告

1. 使用具有查看監督報告許可權的系統管理員帳號憑證, 登入[規範中心](https://compliance.microsoft.com)。
2. 移至 [**報告** \> ]**儀表板**或 [**監督**], 以查看監督報告小工具, 以取得目前監督原則活動的摘要。
3. 選取**監督**小工具以開啟 [詳細報告] 頁面。

> [!NOTE]
> 如果您無法存取 [**報告**] 頁面, 請檢查您是否為主管審查角色群組的成員, 如組織中提供的[監督](configure-supervision-policies.md)所述。 包含在這個角色群組中, 可讓您建立及管理監督原則並執行報告。
  
### <a name="how-to-use-the-report"></a>如何使用報表

此報告會列出每個原則以及在審閱程式中每個階段的通訊數目。 使用報表來:
  
- 查看所有或特定原則的資料。
- 查看依標記類型、檢閱者或訊息類型分組的資料。
- 根據活動日期、原則及檢閱者活動, 將資料匯出至 CSV 檔案。
- 根據活動日期、標記類型、檢閱者和郵件類型篩選資料。

以下是顯示 [**標記類型**] 欄的值的細目。
  
|**標記類型**|**含義**|
|:-----|:-----|
| **未檢查** | 尚未審閱的電子郵件數目。 這些電子郵件在 [Office 365 監督] 儀表板中等候審閱。
| **Compliant** | 已檢查並標示為合規性的電子郵件數目。 這些訊息仍然需要解決。 |
| **有疑問的** | 已檢查並標示為可疑的電子郵件數目。 做為其他檢閱者的旗標, 以協助檢查電子郵件是否需要調查合規性。 這些訊息仍然需要解決。 |
| **不相容 (使用中)** | 檢閱者目前正在調查的不相容電子郵件數目。 |
| **不相容 (已解析)** | 檢閱者所調查和解析的不相容電子郵件數目。 |
| **擊中原則** | Exchange、小組及協力廠商資料來源中符合監督原則中所定義之條件的郵件總數 (每日) |
| **在 Purview** | 由監督原則掃描之 Exchange、小組及協力廠商資料來源的郵件總數 |
| **Resolved** | 分類為**已解析**的 Exchange、小組及協力廠商資料來源的郵件總數|

> [!NOTE]
> 必須先布建監督原則, 才會顯示在報告中。 如果刪除原則, 仍會顯示歷史資料。 不過, 它們會表示為「不存在的原則」, 而**Export**功能無法使用。

## <a name="audit"></a>審計

在某些情況下, 您必須提供資訊給法規或合規性審計員, 以證明員工活動和通訊的監督。 這可能是所有與已定義原則或任何監督原則變更相關的主管活動摘要。 監督原則具有內建的核查追蹤, 可以完成內部或外部審計的完整準備。 監督原則所監視之每個動作的詳細審計記錄, 都提供監督程式的證明。

在整合的 Office 365 audit 記錄檔中, 會審核並提供下列監督原則活動:

|**活動**|**相關命令**|
|:-----|:-----|
| **建立原則** | [SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewpolicyv2) <br> [SupervisoryReviewRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewrule) |
| **編輯原則** | [SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewpolicyv2) <br> [SupervisoryReviewRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewrule) |
| **刪除原則** | [SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/remove-supervisoryreviewpolicyv2) |

在統一的 audit log 或使用[UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) PowerShell Cmdlet 來查看審計活動。

例如, 下列範例會傳回所有主管審查活動 (原則和規則) 的活動, 並列出每個專案的詳細資訊:

```
Search-UnifiedAuditLog -StartDate 3/1/2019 -EndDate ([System.DateTime]::Now) -RecordType DataGovernance -ResultSize 5000 | Where-Object {$_.Operations -like "*SupervisoryReview*"}  | fl CreationDate,Operations,UserIds,AuditData
```

除了監督報告及記錄檔中提供的資訊之外, 您還可以使用[SupervisoryReviewActivity](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewactivity?view=exchange-ps) PowerShell Cmdlet 來傳回所有監督原則活動的完整詳細清單。

## <a name="ready-to-get-started"></a>準備好要開始了嗎？

若要為您的組織設定監督原則, 請參閱[設定監督原則](configure-supervision-policies.md)。