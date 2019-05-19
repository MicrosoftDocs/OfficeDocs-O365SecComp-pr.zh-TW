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
description: 了解 Office 365 中的監督原則
ms.openlocfilehash: 2948cc0440bf481e3f0e90e76a23392233d81cc8
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156475"
---
# <a name="supervision-policies-in-office-365"></a>Office 365 中的監督原則

Office 365 中的監督原則可讓您擷取員工通訊，指定檢閱者檢查。 您可以定義擷取內部和外部的電子郵件、 Microsoft Teams 或在組織中的第 3 廠商通訊的特定原則。 檢閱者就可以檢查以確定其符合您組織的郵件標準，並加以解決與分類類型的郵件。 

這些原則也可以協助您克服許多新式規範挑戰，包括：

- 監視增加類型的通訊通道
- 增加磁碟區的郵件資料
- 法規強制執行 & 罰鍰等的風險

在某些組織中，可能會有職責劃分 IT 支援與 [規範管理] 群組之間的區隔。 Office 365 支援監督原則功能設定和原則的設定之間的分隔擷取通訊。 例如，組織的 IT 群組可能會負責設定要支援監督原則設定及管理組織的規範小組的角色權限及群組。

監督原則的簡要概觀，請參閱[Microsoft 機制通道](https://www.youtube.com/user/OfficeGarageSeries)上的[視訊的監督原則](https://youtu.be/C3Y8WZ7o_dI)。

若要深入了解即將來臨的監督功能改良和可用性，請參閱[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)。

## <a name="scenarios-for-supervision-policies"></a>監督原則的案例

監督原則可協助您的組織中多個範圍中的監視通訊：

- **公司原則**

    員工必須遵守可接受的使用、 道德標準，以及其他公司原則中的所有其業務相關通訊。 監督原則可以偵測違反原則，並協助您採取更正動作，以協助減輕這些類型的事件。 例如，您可以監視潛在的人力資源違規，例如騷擾或使用不當禁止或冒犯的語言，在員工通訊的組織。

- **風險管理**

    組織負責散發到整個其基礎結構與公司網路系統的所有通訊。 使用監督原則來協助識別和管理潛在合法的曝光度與風險，可協助他們可能危害公司作業之前，將風險降到最低。 例如，您可以監視未經授權的通訊機密的專案，例如即將來臨的收購、 併購、 獲利揭露、 重新組織或領導團隊變更您的組織。

- **法規合規性**

    大多數的組織必須遵守某些類型的法規合規性標準，其標準作業程序的一部分。 這些規定通常需要組織實作某種類型的主管或負責監督進行通訊，僅適用於其產業。 財務產業法規機構 (FINRA) 規則 3110 是很好的範例，來監視其員工的活動備妥主管的程序的組織需求的以及其凝聚的企業的類型。 另一個範例可能需要對監視代理人-協會貴組織中以防止潛在的金額 laundering、 測試人員貿易、 夥伴或賄賂活動。 監督原則可協助組織符合這些需求，監視及公司通訊報告提供的程序。

## <a name="components"></a>零件

### <a name="supervision-policy"></a>監督原則

您可以建立監督原則與合規性中心。 這些原則定義哪些通訊和使用者會受到檢閱您組織中，定義自訂條件通訊必須符合，並指定誰應該執行的檢閱。 主管檢閱角色群組中包含的使用者可以設定原則，並擁有此角色指派給任何人可以存取合規性中心中的 [監督] 頁面。

### <a name="supervised-users"></a>監督的使用者

在您開始使用監督之前，您必須決定誰需要檢閱其通訊。 在原則中，個人或群組的人員来監管，找出使用者電子郵件地址。 這些群組的一些範例包括 Office 365 群組、 Exchange 型的通訊群組清單和 Microsoft Teams 通道。 您也可以排除特定使用者或群組監督監督的群組或群組的清單。

> [!IMPORTANT]
> 受到監督原則的使用者必須擁有可以是 Microsoft 365 E5 合規性授權 Office 365 企業版 E3 授權來搭配進階合規性的附加元件，或包含在 Office 365 企業版 E5 訂閱。
如果您未擁有現有的企業版 E5 方案，以及要嘗試監督，您可以[註冊 Office 365 企業版 E5 的試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。

### <a name="reviewers"></a>檢閱者

當您建立的監督原則時，您必須決定誰可以執行檢閱的監督使用者的郵件。 在原則中，使用者電子郵件地址來識別的個人或群組的人員檢閱監督的通訊。 所有檢閱者必須擁有 Exchange Online 上主控的信箱。

### <a name="groups-for-supervised-users-and-reviewers"></a>監督的使用者和檢閱者群組

為了簡化您的設定，建立之人員需要檢閱其通訊群組和群組的檢閱這些通訊的人。 如果您使用的群組，您可能需要數個選項。 例如，如果您想要監視的人員，兩個不同的群組之間的通訊，或如果您想要指定不指導的群組。

### <a name="supported-communication-types"></a>支援的通訊類型

監督原則，您可以選擇要監視中一或多個下列通訊平台的郵件：

- **Exchange 電子郵件：** Exchange Online 上主控的 Office 365 訂閱一部分的信箱是所有合格的訊息監督。 電子郵件和附件符合監督原則條件會立即可用來監視及監督報告中。 支援的附件類型的監督和是相同[的 Exchange 郵件流程規則內容檢查支援的檔案類型](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)。
- **Microsoft Teams:** 可以指導聊天室的通訊和公用和私人 Microsoft Teams 通道和個別的聊天室中相關聯的附件。 比對監督原則條件的小組聊天處理一次，每隔 24 小時，則可用來監視及監督報告中。 使用下列群組管理設定監管個別使用者聊天室和 microsoft Teams 中的通道通訊：

    - **的小組聊天監督：** 指派個別使用者或[通訊群組](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE)指派的監督原則。 這是對於 1-1 或 1 對多使用者/聊天室的關係。
    - **的小組通道通訊：** 指派每個 Microsoft 小組通道，或您想要監視的 Office 365 群組包含特定使用者的監督原則。 如果您將相同的使用者新增至其他 Microsoft Teams 通道或 Office 365 群組時，請務必也將這些新通道和群組新增至監督原則。

- **協力廠商來源：** 您可以監管資料匯入至您組織中的 Office 365 信箱的第三方來源 （類似從 Facebook 或投寄箱） 的通訊。 [了解如何將 Office 365 的第 3 廠商資料匯入](https://docs.microsoft.com/office365/securitycompliance/archiving-third-party-data)。

擷取這些平台上的通訊會保留每個原則七年依預設，即使使用者離開您的組織，且其信箱已刪除。

### <a name="policy-settings"></a>原則設定

#### <a name="direction"></a>方向

根據預設，**方向是**條件會顯示，且無法加以移除。 在原則中的通訊方向設定都已選取個別或一起：

- **輸入**： 您可以選擇**輸入**所傳送的通訊**來**檢閱您選擇要監管**從**人員不包含在原則中的人員。
- **輸出**： 您可以選擇**從**傳送**輸出**如果您想要檢閱通訊您選擇要監管**至**人員不包含在原則中的人員。
- **Internal**： 您可以選擇要檢閱傳送的通訊**之間**的**內部**您指定的人員在原則中。

#### <a name="sensitive-information-types"></a>敏感資訊類型

您可以選擇包含敏感資訊類型為監督原則的一部分。 敏感資訊類型是可以協助識別及保護信用卡號碼、 銀行帳戶號碼、 護照號碼等任一種預先定義或自訂的資料類型。 作為 Office 365[資料外洩防護 (DLP)](data-loss-prevention-policies.md)的一部分，敏感資訊設定可以使用模式，字元近似值、 信賴等級，即使自訂的資料類型來協助識別並加上旗標，可能是敏感內容。 預設的敏感資訊類型如下：

- 財務
- 醫療和健康情況
- 隱私權
- 自訂的資訊類型

若要深入了解敏感資訊的詳細資訊，包含在預設類型的模式，請參閱[敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。

#### <a name="custom-keyword-dictionaries"></a>自訂的關鍵字字典

設定自訂的關鍵字字典 （lexicons） 來提供簡單管理的組織或產業特定的關鍵字。 關鍵字字典支援最多 100000 的字詞，每個字典。 如有需要您可以將多個自訂的關鍵字字典套用到單一原則，或有單一關鍵字字典每個原則。 這些字典會指派監督原則中，而且可以源自檔案 （例如.csv 或.txt 清單），或從清單中您可以[在 「 規範中心中匯入](create-a-keyword-dictionary.md)。

#### <a name="offensive-language"></a>冒犯的語言

監視器或傳送電子郵件訊息送達您的組織不良的語言。 模型會使用機器學習、 人工地智慧組合和關鍵字]，以識別不當的電子郵件反騷擾與網路凌監控需求的一部分。 若要防止或封鎖您組織中其他通訊冒犯語言，建立使用[自訂的關鍵字字典](create-a-keyword-dictionary.md)冒犯性字詞的[資料外洩防護原則](create-test-tune-dlp-policy.md)。

冒犯模型目前支援英文關鍵字，並監視的電子郵件內文。 冒犯模型監視舉動下列幾種語言相關聯的電子郵件：

|**類型**|**描述**|
|:-----|:-----|
| **Profanities** | 運算式，並不適用，並讓大部分的人員。 |
| **Slurs** | 文化特性和 ethnicities 來進行攻擊的運算式。 |
| **嘲諷** | 嘲諷、 condemn，以及 ridicule 的運算式。 |
| **障礙的參照** | 目標身體或心理障礙的運算式。 |
| **Squalid 語言** | 性別興趣和實體 cleanliness 狀態為目標的運算式。 |
| **Homophobia** | 目標性別喜好設定的運算式。 |
| **Racism** | 競爭和 ethnicity 為目標的運算式。 |
| **Extremism** | 宗教和政治 ideologies 為目標的運算式。 |
| **偽裝** | 意義與發音的另一個更冒犯性字詞相同的運算式。 |
| **挑逗語言** | 可能會造成憤怒或暴力的運算式。 |
| **Taboo** | 通常不是適當禮貌 societal 通訊中的運算式。 |
| **類似的語言** | 運算式，缺少禮貌最節省和，且可能強光 」 粗略。 |

#### <a name="conditional-settings"></a>條件式設定

您選擇的原則的條件套用至通訊來源電子郵件和第 3 廠商組織 （類似從 Facebook 或投寄箱） 中。

下表說明更多關於每個條件。
  
|**條件**|**如何使用這種情況**|
|:-----|:-----|
| **從任何這些網域接收郵件**  <br><br> **從任何這些網域不接收郵件** | 若要將原則套用特定的網域是包含或排除在收到的郵件時，輸入每個網域，並以逗號分隔多個網域。 您輸入的每個網域會分別套用 （只有一個這些網域必須套用的原則套用至郵件）。 |
| **訊息會傳送至這些網域的任何**  <br><br> **郵件不會傳送給任何這些網域** | 若要將原則套用特定的網域是包含或排除在傳送郵件時，輸入每個網域，並以逗號分隔多個網域。 您輸入的每個網域會分別套用 （只有一個這些網域必須套用的原則套用至郵件）。 |
| **郵件被分類與任何這些標籤**  <br><br> **訊息不使用任何這些標籤的分類** | 若要將原則套用時內含或排除在郵件中特定保留標籤。 保留標籤必須個別設定，並設定的標籤所選為此條件的一部分。 您選擇每個標籤分別套用 （只有一個這些標籤必須套用的原則套用至郵件）。 如需設定保留標籤的詳細資訊，請參閱 < <b0>Overview of 保留標籤</b0>。|
| **郵件會包含任何這些字詞**  <br><br> **郵件會包含任何這些字詞** | 若要包含或排除在郵件中特定單字或片語時，請套用原則，請輸入每個單字或片語的個別行上。 您輸入的文字的每一行會分別套用 （只有一個這些行必須套用的原則套用至郵件）。 如需輸入單字或片語的詳細資訊，請參閱 [下一步] 區段中[比對單字和片語的電子郵件或附件](supervision-policies.md#Matchwords)。|
| **附件包含任何這些字詞**  <br><br> **附件包含任何這些字詞的項目** | 若要包含或排除 （例如 Word 文件） 的郵件附件中特定單字或片語時，請套用原則，請輸入每個單字或片語的個別行上。 您輸入的文字的每一行會分別套用 （只有一列必須套用的原則套用至附件）。 如需輸入單字或片語的詳細資訊，請參閱 [下一步] 區段中[比對單字和片語的電子郵件或附件](supervision-policies.md#Matchwords)。|
| **附件是任何這些檔案類型**  <br><br> **附件為 none 這些檔案類型** | 若要監管通訊，包括或排除特定類型的附件，請輸入副檔名 （例如.exe 或.pdf）。 如果您想要包含或排除多個副檔名，請輸入這些在不同行。 只有一個附件副檔名必須符合要套用的原則。|
| **郵件大小大於**  <br><br> **郵件大小不大於** | 若要檢閱根據特定大小的郵件，使用這些條件來指定它受到檢閱之前，可以將郵件的最大值或最小大小。 例如，如果您指定**的郵件大小大於** \> **1.0 MB**，所有郵件，1.01 MB，而較大為受到檢閱。 您可以選擇位元組、 kb、 （mb） 或 gb 這個狀況。|
| **附件大於**  <br><br> **附件不大於** | 若要檢閱根據其附件的大小的郵件，指定附件的最大值或最小大小可再將郵件和其附件會受到檢閱。 例如，如果您指定**附件大於** \> **2.0 MB**，所有郵件附件 2.01 MB，超過為受到檢閱。 您可以選擇位元組、 kb、 （mb） 或 gb 這個狀況。|
   
##### <a name="matching-words-and-phrases-to-emails-or-attachments"></a>比對單字和片語，以電子郵件或附件
<a name="Matchwords"></a>分別套用每一行的您輸入的字數 （只有一列必須套用原則條件套用至電子郵件或附件）。 例如，讓我們使用的條件，**郵件會包含任何這些字詞**，關鍵字 」 也 」 與 「 測試人員貿易 」 在不同行。 原則已套用到任何包含單字"也 」 或片語 「 測試人員貿易 」 的郵件。 僅是其中一個這些單字或片語必須發生以套用此原則條件。 郵件或附件中的文字必須完全符合您的輸入。
  
##### <a name="enter-multiple-conditions"></a>輸入多個條件

如果您輸入多個條件，Office 365 使用的所有條件一起來決定何時要將原則套用至通訊項目。 當您設定多個條件時，它們必須全部符合將原則套用，除非您輸入的例外狀況。 例如，您需要建立一個原則，如果郵件包含 「 貿易 」 這個字，並大於 2 MB 時套用。 不過，如果郵件也會包含文字 「 Contoso 財務由已核准 」，應該不會套用原則。 因此，在此例中的三個條件就是，如下所示：
  
- **郵件會包含任何這些字詞**，包含關鍵字 「 貿易 」

- **郵件大小大於**，使用值 2 MB

- **郵件會包含任何這些字詞**，包含關鍵字 「 Contoso 財務團隊核准 」

#### <a name="review-percentage"></a>檢閱百分比

如果您想要減少要檢閱的內容量，您可以指定百分比由監督原則的所有通訊。 內容即時、 隨機範例會選取從內容符合原則條件中選擇的總百分比。 如果您想要檢閱者的所有項目，您可以輸入監督原則中的**100%** 。

## <a name="monitor--manage"></a>監視 & 管理

很容易監視結果的監督原則並套用解析度標記。 您可以快速查看檢閱過的項目、 使用者和群組下監督，與使用者和群組指定為檢閱者的狀態。

### <a name="supervision-policy-dashboard"></a>監督原則儀表板

管理監督原則結果，以及解決待處理項目，請使用監督原則儀表板。 這個儀表板可以讓檢閱者檢視項目需要檢閱，採取動作的項目，並檢閱每個監督原則的先前已檢閱並解析項目的結果。 您可以存取合規性中心，在**監督**監督原則儀表板 > *您的自訂原則* > **開啟**。

#### <a name="dashboard-home"></a>儀表板首頁

**儀表板的首頁**] 頁面有幾個區段，以協助您快速採取監督原則中的動作。 以下是您可以：

- 檢閱擱置中及已解決快速日當週會醒目提示
- 請參閱監督的使用者及群組清單的監督針對選取的原則
- 請參閱 < 的檢閱者的清單並檢閱小組針對選取的原則
- 查看哪些通訊平台具有下監督原則內容

#### <a name="review-tab"></a>檢閱] 索引標籤

[**檢閱**] 索引標籤是其中的檢閱者分類及解決項目識別所選取的原則。 以下是您可以：

- 篩選擱置相容、 不相容，並有疑問的項目。
- 標記為相容、 不相容，或有疑問的單一項目。 您也可以記錄與項目，有助於釐清標記採取的動作的註解。
- 大量標記為相容、 不相容，或有疑問的多個項目。 您也可以記錄含有多個項目，有助於釐清標記採取的動作的註解。
- 檢視歷程記錄的單一項目的標記。 這包括誰解析項目、 日期和時間巨集指令、 解析度標記，以及任何包含註解。
- 將重新分類為相容、 不相容，或有問題的先前已檢閱項目。 您也可以記錄與單一或多個項目，有助於釐清採取重新分類巨集指令的註解。

#### <a name="resolved-items-tab"></a>解析項目] 索引標籤

**解析項目**] 索引標籤是其中的檢閱者可以檢視所有先前已解析項目選取原則。 以下是您可以：

- 快速檢視和主旨、 寄件者和解析項目的日期排序
- 檢視所有選取的項目分類和註解歷程記錄

## <a name="reports"></a>報表

使用監督報告來查看層級原則和檢閱者檢閱活動。 針對每個原則中，您也可以檢閱活動的目前狀態，以檢視即時的統計資料。 您可以使用監督報告：
  
- 確認您的原則，如您預期般運作。
- 了解多少通訊需要檢閱。
- 了解多少 communications 不相容，並哪些項目會傳遞給檢閱。 此資訊可協助您決定是否要微調原則或變更的檢閱者數目。

### <a name="view-the-supervision-report"></a>檢視監督報告

1. 若要檢視監督報告的權限您組織中系統管理員帳戶登入[合規性中心](https://compliance.microsoft.com)與認證。
2. 移至 [**報告** \> **儀表板**或**監督**，若要檢視報告與目前的監督原則活動摘要] 小工具監督。
3. 選取 [若要開啟 [詳細資料報告] 頁面上的 [**監督**] 小工具。

> [!NOTE]
> 如果您不能存取 [**報告**] 頁面上，請檢查您所主管檢閱角色群組的成員，[讓組織中可用的監督](configure-supervision-policies.md)所述。 納入此角色群組可讓您建立及管理監督原則，並執行報告。
  
### <a name="how-to-use-the-report"></a>如何使用報告

這份報告列出每個原則，以及通訊數目，每個階段中檢閱程序。 使用報告：
  
- 檢視所有的資料或特定的原則。
- 依標記類型、 檢閱者或如果郵件類型分組檢視資料。
- 將資料匯出至 CSV 檔案根據活動日期] 原則，以及由檢閱者活動。
- 篩選資料，根據活動的日期，標記類型、 檢閱者、 郵件類型。

以下是 [值的明細顯示**標記類型**] 欄中的色彩。
  
|**標記類型**|**其意思**|
|:-----|:-----|
| **不檢閱** | 不檢閱尚未的電子郵件數目。 這些電子郵件會等候 Office 365 監督儀表板中的檢視。
| **Compliant** | 檢閱及標記為相容的電子郵件數目。 這些郵件仍需要解決方法。 |
| **有疑問的** | 檢閱及標示可疑的電子郵件數目。 這可協助其他檢閱者的旗標作為檢查電子郵件是否需要調查的合規性。 這些郵件仍需要解決方法。 |
| **不相容 （作用中）** | 不相容目前正在調查的檢閱者的電子郵件數目。 |
| **不相容 （解析）** | 不相容的檢閱者調查並解決電子郵件數目。 |
| **瀏覽原則** | 總數 （每日） 來自 Exchange、 小組及協力廠商資料來源符合監督原則中定義的一或多個條件的郵件 |
| **在 [Purview** | 總數 （每日） 來自 Exchange、 小組，並掃描由監督原則的協力廠商資料來源 |
| **Resolved** | 從 Exchange、 小組及歸類為**已解決**的協力廠商資料來源的訊息總數|

> [!NOTE]
> 監督原則必須先佈建之前它們會出現在此報告中。 此外，如果刪除原則，仍會顯示歷程資料。 不過，它們指定為 「 非存在原則 」，並**匯出**函數無法使用。

## <a name="audit"></a>稽核

在某些情況下，您必須提供資訊給法規或規範稽核員證明監督的員工活動和通訊。 這可能是定義的原則或隨時隨地監督原則的變更相關聯的所有主管活動的摘要。 監督原則必須為內部或外部稽核完成整備的內建的稽核線索。 受到監督原則的每個動作詳細的稽核歷程記錄提供證明主管的程序。

下列的監督原則活動的稽核和可用的整合的 Office 365 稽核記錄檔中：

|**活動**|**相關聯的命令**|
|:-----|:-----|
| **建立原則** | [新 SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewpolicyv2) <br> [新 SupervisoryReviewRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewrule) |
| **編輯原則** | [Set-supervisoryreviewpolicyv2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewpolicyv2) <br> [Set-supervisoryreviewrule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewrule) |
| **刪除原則** | [Remove-supervisoryreviewpolicyv2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/remove-supervisoryreviewpolicyv2) |
| **檢視原則** | [取得 SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-supervisoryreviewpolicyv2) |

檢視稽核活動整合的稽核記錄檔中，或使用[Search-unifiedauditlog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) PowerShell cmdlet。

例如，下列範例會傳回所有主管檢閱活動 （原則和規則） 的活動，並列出每個的詳細的資訊：

```
Search-UnifiedAuditLog -StartDate 3/1/2019 -EndDate ([System.DateTime]::Now) -RecordType DataGovernance -ResultSize 5000 | Where-Object {$_.Operations -like "*SupervisoryReview*"}  | fl CreationDate,Operations,UserIds,AuditData
```

除了監督報告和記錄檔中所提供的資訊，您也可以使用[Get-SupervisoryReviewActivity](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewactivity?view=exchange-ps) PowerShell cmdlet 可傳回完整詳細的清單，所有監督原則的活動。

## <a name="ready-to-get-started"></a>準備好要開始了嗎？

若要開始設定您組織的監督原則，請參閱 < <b0>Configure 監督原則</b0>。