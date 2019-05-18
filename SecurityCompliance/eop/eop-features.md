---
title: EOP 功能
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 599b8048-1056-457b-aae4-c063138fd319
description: 下表提供可在 Exchange Online Protection (EOP) 託管式電子郵件篩選服務中使用的功能清單。
ms.openlocfilehash: 9d408aed63027915b6d2ff3466bc629fa2a51236
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34150345"
---
# <a name="eop-features"></a>EOP 功能

下表提供可在 Exchange Online Protection (EOP) 託管式電子郵件篩選服務中使用的功能清單。 
  
> [!TIP]
> [適用於商務藍圖的 Office 365](https://office.microsoft.com/en-us/products/office-365-roadmap-FX104343353.aspx) 是很好的資源，可找出即將推出之新功能的相關資訊。如需深入了解不同的 EOP 訂閱方案可提供什麼功能，請參閱 [Exchange Online Protection 服務描述](https://go.microsoft.com/fwlink/p/?LinkId=320619)。 
  
|||
|:-----|:-----|
|**功能**|**描述**|
|**反垃圾郵件保護**||
|輸入垃圾郵件偵測|輸入反垃圾郵件保護永遠啟用，而且無法停用。您可以透過連線篩選和內容篩選原則來進行自訂設定。  <br/> 為 EOP 獨立版客戶： 根據預設，EOP 內容篩選將偵測到垃圾郵件的郵件傳送至每個收件者的垃圾郵件] 資料夾。 不過，為了協助確保 [**移至垃圾郵件] 資料夾的郵件**] 動作將會使用內部部署信箱，您必須設定兩個 Exchange 郵件流程規則 （也稱為傳輸規則） 上您的內部部署伺服器，以偵測新增的垃圾郵件標頭透過 EOP。 如需詳細資訊，請參閱[確定垃圾郵件路由傳送至每一個使用者的垃圾郵件資料夾](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。|
|輸出垃圾郵件偵測|如果您使用服務傳送輸出電子郵件，藉此幫助保護使用服務的組織和其預期的收件者，一定會啟用輸出反垃圾郵件保護。 和輸入篩選相似，輸出垃圾郵件篩選由連線篩選和內容篩選組成。 輸出垃圾郵件篩選設定無法進行設定，但是有輸出垃圾郵件原則，可讓您用來設定可疑和已封鎖輸出郵件的系統管理員通知。 如需詳細資訊，請參閱 <<c0>設定輸出垃圾郵件原則。|
|NDR 退信攻擊保護|如需有關 NDR backscatter 的詳細資訊，請參閱 < 的 NDR backscatter 設定<b0>進階垃圾郵件篩選選項</b0>，以及<b1>退信攻擊郵件與 EOP</b1>中。|
|大宗郵件篩選|EOP 已經增強偵測方法來識別大宗的電子郵件。 您可以透過使用者介面將服務設定為標記大宗電子郵件。 您也可以建立郵件流程規則，以更積極地篩選大量郵件所搜尋的大量郵件郵件標頭戳記。 如需有關大量電子郵件的詳細資訊，請參閱[垃圾郵件和大量電子郵件之間的差異為何？](../what-s-the-difference-between-junk-email-and-bulk-email.md)和其相關子主題。|
|惡意 URL 封鎖清單|EOP 使用數個幫助偵測郵件中已知惡意連結的 URL 封鎖清單。|
|反網路釣魚保護|EOP 包括 750000 個已知濫發垃圾郵件者的網域。|
|**垃圾郵件管理**||
|設定連線篩選 IP 允許清單與 IP 封鎖清單的功能|在連線篩選中指定的 IP 位址會遵守單一 IP 位址及 CIDR IP 位址範圍。 服務也支援 IPv6 位址。 如需詳細資訊，請參閱[設定連線篩選原則](../configure-the-connection-filter-policy.md)。|
|自訂每個使用者、群組或網域之內容篩選原則的功能|如需進行更為精細的篩選，您可以建立自訂內容篩選原則，並將它們套用至組織中的指定使用者、群組或網域。 自訂原則一律優先於預設原則，但您可以變更自訂原則的優先順序 (亦即執行順序)。 如需詳細資訊，請參閱[設定您的垃圾郵件篩選原則](../configure-your-spam-filter-policies.md)。|
|設定要對經過內容篩選的郵件所採取的動作之功能|有多個可設定的動作。 例如，您可以刪除經過內容篩選的郵件，或將它們傳送到垃圾電子郵件資料夾或隔離。 如需詳細資訊，請參閱[設定您的垃圾郵件篩選原則](../configure-your-spam-filter-policies.md)。|
|設定進行嚴苛垃圾郵件篩選之進階選項的功能|如需詳細資訊，請參閱[設定垃圾郵件篩選原則](../configure-your-spam-filter-policies.md)（也就是在您設定的位置） 和[進階垃圾郵件篩選選項](../advanced-spam-filtering-asf-options.md)（可提供關於每個選項之作用的特定詳細資料）。|
|國際垃圾郵件篩選|您可以將 EOP 設定為篩選以特定語言撰寫的郵件，或是從特定國家或地區傳送的電子郵件。 您可以設定高達 86 種不同語言和 250 個不同地區。 此服務會對高信賴度垃圾郵件套用設定的動作。 如需詳細資訊，請參閱[設定您的垃圾郵件篩選原則](../configure-your-spam-filter-policies.md)。|
|透過 Outlook 或網頁 （原先稱為 Outlook Web App） 管理垃圾郵件|系統管理員和使用者可以建立安全的寄件者清單以及封鎖的寄件者清單。 如需詳細資訊：  <br/> 在 web 上的 outlook： 請參閱[封鎖或允許 （垃圾郵件設定）](https://go.microsoft.com/fwlink/p/?LinkId=294862)。  <br/> Outlook：請參閱[垃圾郵件篩選概觀](https://go.microsoft.com/fwlink/p/?LinkId=270065)。  <br/> 如果您正在使用 EOP 來協助保護在內部部署信箱，請務必使用目錄同步作業協助確保這些設定會同步至服務。 若需設定目錄同步作業的詳細資訊，請參閱 [管理 EOP 中的郵件使用者](manage-mail-users-in-eop.md) 中的「使用目錄同步作業來管理郵件使用者」。|
|透過 Microsoft Office Outlook 的垃圾郵件回報增益集提交垃圾郵件|您可以下載增益集到 Outlook，讓您提交垃圾郵件給 Microsoft 進行分析。 如需下載和使用此工具的詳細資訊，請參閱 <<c0>啟用報告訊息增益集。  <br/> 如果您正在使用 Exchange Server 2013 或更新版本與 EOP，您可以也以滑鼠右鍵按一下 outlook 網頁版以提交垃圾郵件[回報垃圾郵件](../report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)和網路釣魚詐騙網頁型 Outlook 中的所述。|
|透過電子郵件別名提交垃圾郵件和非垃圾郵件|您可以透過電子郵件提交垃圾郵件 (垃圾) 和非垃圾郵件 (非垃圾) 給 Microsoft。 如需詳細資訊，請參閱[提交垃圾郵件、 非垃圾郵件和網路釣魚詐騙郵件提交給 Microsoft 進行分析](../submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)。|
|垃圾郵件和非垃圾郵件提交透過垃圾郵件回報網頁型 Outlook|您可以提交垃圾郵件和非垃圾郵件提交給 Microsoft 垃圾郵件回報網頁型 Outlook 透過。 如需詳細資訊，請參閱[回報垃圾郵件和網路釣魚詐騙網頁型 Outlook 中](../report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)。  <br/> 此功能目前適用於 Outlook web 客戶其 Exchange Server 2013 SP1 或更新版本的信箱會透過 EOP 篩選。 Exchange Online Outlook web 客戶在不久的將來也有這項功能。|
|使用者垃圾郵件隔離通知|使用者可以釋出其自己的垃圾隔離郵件，並選擇性透過使用者垃圾郵件通知郵件來回報這些郵件不是垃圾郵件。 這些通知電子郵件必須設定及啟用由系統管理員，[設定使用者垃圾郵件通知中 Exchange Online](../configure-end-user-spam-notifications-in-exchange-online.md)或[EOP 中的設定使用者垃圾郵件通知](../configure-end-user-spam-notifications-in-eop.md)中所述。|
|使用者垃圾郵件隔離通知頻率|此頻率預設為 3 天，可設定為 1 到 15 天。|
|讓系統管理員設定使用者垃圾郵件隔離通知語言的功能|此功能適用於使用者及系統管理員。如需詳細資訊，請參閱 [Find and release quarantined messages as an administrator](../find-and-release-quarantined-messages-as-an-administrator.md) 或 [Find and Release Quarantined Messages as an End User](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx)。  |
|透過網頁存取和管理隔離區中的郵件|此功能適用於使用者及系統管理員。如需詳細資訊，請參閱 [Find and release quarantined messages as an administrator](../find-and-release-quarantined-messages-as-an-administrator.md) 或 [Find and Release Quarantined Messages as an End User](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx)。  |
|搜尋隔離的功能|在隔離區中搜尋特定垃圾郵件的功能，適用於系統管理員和使用者。如需詳細資訊，請參閱 [Find and release quarantined messages as an administrator](../find-and-release-quarantined-messages-as-an-administrator.md) 或 [Find and Release Quarantined Messages as an End User](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx)。  |
|從 Exchange 系統管理中心檢視垃圾郵件隔離郵件標頭|檢視隔離中的郵件標題之後，您也可以複製郵件標頭文字並將它貼到[郵件標頭分析器](https://testconnectivity.microsoft.com/?tabid=mha)，可提供資訊說明郵件發生了什麼事。|
|**反惡意程式碼保護**||
|多重引擎反惡意程式碼保護|多重的反惡意程式碼引擎可協助隨時自動保護我們的客戶。|
|停用惡意程式碼篩選的選項|您無法停用惡意程式碼篩選，因為我們會對透過服務來路由傳送的所有電子郵件強制進行反惡意程式碼掃描。我們相信，所有客戶協助提供一致且嚴密的保護層級，是協助保護您電子郵件環境時所需的深度防禦策略中很重要的一部份。因此，系統會自動為所有客戶啟用惡意程式碼篩選。|
|郵件內文及附件的惡意程式碼檢查|此服務會檢查郵件本文和所有郵件附件中的使用中裝載是否有惡意程式碼。|
|預設或自訂惡意程式碼警示通知|您可以選擇在偵測到郵件有惡意程式碼而未傳遞時，將通知電子郵件傳送給寄件者或系統管理員。 刪除整封郵件時，只會傳送這些通知。 如需詳細資訊，請參閱 <<c0>設定反惡意程式碼原則。|
|偵測到惡意程式碼時移除附件的選項|系統管理員可以選擇是否要刪除整個郵件或要移除附件，並將自訂的郵件傳送給收件者。 如需詳細資訊，請參閱 <<c0>設定反惡意程式碼原則。|
|反間諜軟體保護|反惡意程式碼保護內含防毒保護和反間諜軟體保護。|
|自訂每個使用者、群組或網域之惡意程式碼篩選原則的功能|如需進行更為精細的篩選，您可以建立自訂惡意程式碼篩選原則，並將它們套用至組織中的指定使用者、群組或網域。 自訂原則一律優先於預設的全公司原則，但您可以變更自訂原則的優先順序 (亦即執行順序)。 如需詳細資訊，請參閱 <<c0>設定反惡意程式碼原則。|
|**郵件路由和連接器**||
|條件式郵件路由|如需詳細資訊，請參閱[Create Connectors for Conditional Mail Routing](http://technet.microsoft.com/library/905dc235-1d2b-487e-a65a-516d92e88347.aspx)。|
|隨機或強制 TLS|隨機或強制 TLS 可供連接器使用。 隨機 TLS 會嘗試 TLS 連線，但是如果 TLS 連線失敗時會使用 SMTP 連線。 強制 TLS 會強制使用 TLS 連線，這表示如果 TLS 連線失敗，就會拒絕郵件。 如需 TLS、安全性和連接器的詳細資訊，請參閱[Set up connectors for secure mail flow with a partner organization](http://technet.microsoft.com/library/1ce4d6a4-41ba-4d1e-9ca9-e826252c1041.aspx)。|
|地區路由 (流向特定地區的郵件流程限制)|如需詳細資訊，請參閱 [Exchange Online Protection 概觀](exchange-online-protection-overview.md) 中的「EOP 資料中心」一節。|
|SMTP 連線檢查程式工具|如需使用此工具測試郵件流程的詳細資訊，請參閱 [Test Mail Flow with the Remote Connectivity Analyzer](http://technet.microsoft.com/library/6c8c2964-d553-4329-8166-6e508dd63fa0.aspx)。|
|符合子網域|如需關於啟用公認的網域之子網域的雙向郵件流程的詳細資訊，請參閱[啟用 EOP 中子網域的電子郵件流程](http://technet.microsoft.com/library/b5684042-dadc-4111-95b3-c2fd06e368bf.aspx)。|
|**郵件流程規則**||
|原則式篩選和動作|自訂原則乃是根據 Exchange 郵件流程規則。 您可以透過網域、關鍵字、檔案名稱、檔案類型、主旨列、郵件內文、寄件者、收件者、標頭和 IP 位址進行篩選。 如需詳細資訊，請參閱[郵件流程規則 （傳輸規則） 在 [Exchange Online Protection](mail-flow-rules-transport-rules-0.md)。|
|依據文字模式篩選|郵件流程規則可以使用陣列或規則運算式來比對文字。 您也可以使用單一字串或字串陣列來比對許多郵件屬性，例如地址、主旨、內文或附件名稱。 如需詳細資訊，請參閱[郵件流程規則 （傳輸規則） 在 [Exchange Online Protection](mail-flow-rules-transport-rules-0.md)|
|自訂字典|郵件流程規則可以包含較長的文字和關鍵字，提供自訂字典相同的功能清單。|
|以網域為基礎的原則規則|郵件流程規則的範圍可以進行自訂以符合寄件者或收件者的網域名稱、 IP 位址範圍、 地址關鍵字或模式、 群組成員資格和其他條件。|
|掃描附件|您可以建立規則來掃描檔案名稱、副檔名以及附件的內容。|
|將原則規則通知傳送給寄件者|您可以透過「 **拒絕此郵件並包含說明**」或「 **拒絕其增強型狀態碼為此的郵件**」動作，來拒絕郵件並將未傳遞回報 (NDR) 傳送給寄件者。 如需詳細資訊，請參閱[郵件流程規則動作](http://technet.microsoft.com/library/f8621ecb-a177-4025-9011-a6569999746a.aspx)。|
|將郵件傳送至固定位址 (例如將郵件重新導向或複製到特定的位址)|郵件流程規則可以重新導向、 新增副本或密件副本收件者、 僅新收件者，以及其他選項。 如需詳細資訊，請參閱[郵件流程規則動作](http://technet.microsoft.com/library/f8621ecb-a177-4025-9011-a6569999746a.aspx)。|
|輕易跨多個規則調整規則優先順序的功能|使用 Exchange 系統管理員中心來變更規則的處理順序。|
|篩選郵件然後變更郵件之路由或屬性的功能|您可以根據各種條件來篩選郵件，然後將一連串的動作套用至每封郵件。 如需詳細資訊，請參閱[郵件流程規則 （傳輸規則） 在 [Exchange Online Protection](mail-flow-rules-transport-rules-0.md)。|
|根據規則變更郵件的垃圾郵件信賴等級。|您可以檢查傳輸中的郵件，並根據您選擇的準則，將垃圾郵件信賴等級指派給它。 如需詳細資訊，請參閱 <<c0>使用郵件流程規則來設定郵件中的垃圾郵件信賴等級 (SCL)。|
|檢查郵件附件|您可以檢查附件的內容或附加檔案的特性，並定義根據檢查結果所要採取的動作。 如需詳細資訊，請參閱 <<c0>使用郵件流程規則檢查郵件附件。|
|**系統管理**||
|Web 式管理|EOP 系統管理員可以透過 Exchange 管理中心 (EAC) 介面 (支援 60 種語言) 來管理服務。 如需詳細資訊，請參閱[Exchange 系統管理中心在 Exchange Online Protection ](../exchange-admin-center-in-exchange-online-protection-eop.md)。|
|目錄同步處理|目錄同步作業可透過 Azure Active Directory 同步處理工具 使用。如需詳細資訊，請參閱 [管理 EOP 中的郵件使用者](manage-mail-users-in-eop.md) 中的「使用目錄同步作業管理郵件使用者」一節。  |
|目錄架構邊緣封鎖 (DBEB)|DBEB 功能可讓您在服務網路的周邊處拒絕無效收件者的郵件。DBEB 可讓系統管理員將已啟用郵件的收件者新增至 Office 365，並封鎖所有傳送的目標電子郵件地址沒有顯示在 Office 365 中的郵件。如需設定 DBEB 的詳細資訊，請參閱 [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx)。  |
|遠端 Windows PowerShell 存取|透過遠端 Windows PowerShell 可使用完整的 EOP 功能。如需詳細資訊，請參閱 [Exchange Online Protection 中的 PowerShell](http://technet.microsoft.com/library/f7918a88-774a-405e-945b-bc2f5ee9f748.aspx)。  |
|**回報和記錄**||
|郵件追蹤|郵件追蹤功能在電子郵件通過服務時，讓您以系統管理員的身分追蹤電子郵件。它可以協助您判斷服務是否已接收、拒絕、延遲或傳遞目標電子郵件。此舉可讓您有效回答使用者的問題、疑難排解郵件流程問題、驗證原則變更，並減少連絡技術支援尋求協助的需求。如需詳細資訊，請參閱 [Trace an Email Message](http://technet.microsoft.com/library/0c83cde6-5b09-4106-8587-c200cdc59094.aspx)。  |
|Web 式報告|在 Microsoft 365 系統管理中心的郵件保護報告提供郵件資料。 例如，您可以監視多少垃圾郵件和惡意程式碼偵測到或您的郵件流程規則程度。 透過這些互動式報告，您可以快速取得摘要資料的視覺報告，並深入查看個別郵件的詳細資料，最多可回溯 90 天。 如需詳細資訊，請參閱 [Use mail protection reports in Office 365 to view data about malware, spam, and rule detections](http://technet.microsoft.com/library/bcef7984-4bfa-4ca8-9fa5-a65af8618f5d.aspx)。|
|透過 Excel 報告活頁簿提供詳細報告|另也有 Excel 2013 報告活頁簿形式的電子郵件保護報告。 不過，我們建議您改為使用系統管理中心的報告。 Excel 2013 報告活頁簿預計將在未來被取代。|
|稽核記錄|系統管理員角色群組報告和系統管理員稽核記錄可供 EOP 系統管理員使用。如需詳細資訊，請參閱 [EOP 中的稽核報告](auditing-reports-in-eop.md)。  |
|**服務等級協定 (SLA) 和支援**||
|垃圾郵件有效性 SLA|\>99%|
|誤判率 SLA|\<1:250,000|
|病毒偵測和封鎖 SLA|100% 已知病毒|
|每月執行時間 SLA|99.999%|
|電話和 web 技術支援，每天 24 小時，每週七天|如需 EOP 協助和支援選項的詳細資訊，請參閱 [EOP 的說明和支援](help-and-support-for-eop.md)。|
|**其他功能**||
|異地備援的伺服器全域網路|EOP 執行於資料中心的全球性網路，這些資料中心的設計目的是協助提供最佳的可用性。如需詳細資訊，請參閱 [Exchange Online Protection 概觀](exchange-online-protection-overview.md) 中的「EOP 資料中心」一節。  |
|內部部署伺服器無法接收郵件時，將郵件加入佇列|在延期中的郵件會留在我們佇列中 2 天。郵件重試次數乃是根據我們從收件者的郵件系統所取回的錯誤。平均而言，郵件會每隔 5 分鐘重試一次。如需詳細資訊，請參閱 [EOP 排入佇列、延後和退回的訊息常見問題集](eop-queued-deferred-and-bounced-messages-faq.md)。  |
|Office 365 郵件加密可以作為附加元件服務使用|如需詳細資訊，請參閱 [Office 365 中的加密](https://technet.microsoft.com/en-us/library/dn569286.aspx)。|
   

