---
title: EOP 功能
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 599b8048-1056-457b-aae4-c063138fd319
description: 下表提供可在 Exchange Online Protection (EOP) 託管式電子郵件篩選服務中使用的功能清單。
ms.openlocfilehash: 62d37f0faa45551c2932b415fdd691aecc2df1d4
ms.sourcegitcommit: 06d6e63225f912d0f3c6bb836c61eb11c1dbe97a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/22/2019
ms.locfileid: "30206656"
---
# <a name="eop-features"></a>EOP 功能

下表提供可在 Exchange Online Protection (EOP) 託管式電子郵件篩選服務中使用的功能清單。 
  
> [!TIP]
> [適用於商務藍圖的 Office 365](https://office.microsoft.com/en-us/products/office-365-roadmap-FX104343353.aspx) 是很好的資源，可找出即將推出之新功能的相關資訊。如需深入了解不同的 EOP 訂閱方案可提供什麼功能，請參閱 [Exchange Online Protection 服務描述](https://go.microsoft.com/fwlink/p/?LinkId=320619)。 
  
|||
|:-----|:-----|
|**功能**|**描述**|
|**反垃圾郵件保護**||
|輸入垃圾郵件偵測|輸入反垃圾郵件保護永遠啟用，而且無法停用。您可以透過連線篩選和內容篩選原則來進行自訂設定。  <br/> 如 EOP 獨立版客戶： 根據預設，EOP 內容篩選器將垃圾郵件偵測到的郵件傳送至每個收件者的垃圾郵件] 資料夾。不過，為了幫助確保 [**移至 [垃圾郵件] 資料夾的郵件**] 動作將會使用內部部署信箱，您必須設定兩個 Exchange 傳輸規則來偵測垃圾郵件標頭新增 EOP 的內部部署伺服器上。如需詳細資訊，請參閱[確定垃圾郵件會路由傳送至每位使用者的垃圾郵件] 資料夾](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。|
|輸出垃圾郵件偵測|如果您使用服務來傳送外寄電子郵件，進而協助保護組織所使用的服務和與其預定的收件者一律啟用輸出的反垃圾郵件保護。類似於輸入篩選輸出垃圾郵件篩選 」 包含下列連線篩選的內容篩選。輸出垃圾郵件篩選設定未設定，但有輸出垃圾郵件原則設定可以用來設定通知系統管理員的可疑及封鎖的外寄郵件。如需詳細資訊，請參閱 ＜ [Configure 輸出垃圾郵件原則](../configure-the-outbound-spam-policy.md)。|
|NDR 退信攻擊保護|如需 NDR 非法回應的詳細資訊，請參閱 ＜ 設定[進階垃圾郵件篩選選項](../advanced-spam-filtering-asf-options.md)以以及[非法回應郵件與 EOP](../backscatter-messages-and-eop.md)NDR 非法回應。|
|大宗郵件篩選|EOP 已經加強偵測方法用來識別大量電子郵件訊息。您可以設定標記透過使用者介面的大量電子郵件服務。您也可以建立更積極地篩選大量郵件的傳輸規則的大量郵件郵件標頭戳記搜尋。如需大量電子郵件的詳細資訊，請參閱[垃圾郵件與大量電子郵件之間的差異為何吗？](../what-s-the-difference-between-junk-email-and-bulk-email.md)與它相關聯的副主題。|
|惡意 URL 封鎖清單|EOP 使用數個幫助偵測郵件中已知惡意連結的 URL 封鎖清單。|
|反網路釣魚保護|EOP 包括 750000 個已知濫發垃圾郵件者的網域。|
|**垃圾郵件管理**||
|設定連線篩選 IP 允許清單與 IP 封鎖清單的功能|連線篩選器中指定的 IP 位址適用於單一 IP 位址和 CIDR IP 位址範圍。服務也支援 IPv6 位址。如需詳細資訊，請參閱[設定連線篩選原則](../configure-the-connection-filter-policy.md)。|
|自訂每個使用者、群組或網域之內容篩選原則的功能|Rlo，針對您可以建立自訂內容篩選原則與您組織中套用至指定的使用者、 群組或網域。自訂原則優先順序一律優於預設原則，但您可以變更您的自訂原則的優先順序 （亦即執行順序）。如需詳細資訊，請參閱[設定垃圾郵件篩選器原則](../configure-your-spam-filter-policies.md)。|
|設定要對經過內容篩選的郵件所採取的動作之功能|有多個可設定的動作。例如，您可以刪除經過內容篩選的郵件或將它們傳送至 [垃圾郵件] 資料夾或隔離區。如需詳細資訊，請參閱[設定垃圾郵件篩選器原則](../configure-your-spam-filter-policies.md)。|
|設定進行嚴苛垃圾郵件篩選之進階選項的功能|如需詳細資訊，請參閱[設定垃圾郵件篩選器原則](../configure-your-spam-filter-policies.md)（這是您設定的位置） 和[進階垃圾郵件篩選選項](../advanced-spam-filtering-asf-options.md)（以提供每個選項的作用的特定詳細資料）。|
|國際垃圾郵件篩選|您可以設定 EOP 篩選郵件以特定語言編寫或寄自特定國家或地區。您可以設定最多 86 不同語言和 250 不同的區域。此服務會套用高信賴垃圾郵件設定] 動作。如需詳細資訊，請參閱[設定垃圾郵件篩選器原則](../configure-your-spam-filter-policies.md)。|
|透過 Outlook 或 Outlook web （前身為 Outlook Web App） 上的管理垃圾郵件|系統管理員和使用者可以建立安全的寄件者清單以及封鎖的寄件者清單。如需詳細資訊：  <br/> 在 web 上的 outlook： 請參閱[封鎖或允許 （垃圾郵件設定）](https://go.microsoft.com/fwlink/p/?LinkId=294862)。  <br/> Outlook：請參閱[垃圾郵件篩選概觀](https://go.microsoft.com/fwlink/p/?LinkId=270065)。  <br/> 如果您使用 EOP 來保護內部部署信箱，請務必以協助確保這些設定會同步處理至服務使用目錄同步處理。如需設定目錄同步作業的詳細資訊，請參閱在[EOP 中的管理郵件使用者](manage-mail-users-in-eop.md)的 「 使用目錄同步作業管理郵件使用者 」。|
|透過 Microsoft Office Outlook 的垃圾郵件回報增益集提交垃圾郵件|您可以下載增益集可讓您提交給 Microsoft 進行分析的垃圾郵件的 outlook。如需下載並使用這項工具的詳細資訊，請參閱[啟用報表訊息增益集](https://support.office.com/article/4250c4bc-6102-420b-9e0a-a95064837676)。<br/> 如果您使用 Exchange Server 2013 或更新版本與 EOP，您可以也以滑鼠右鍵按一下在網路上的 Outlook 重新提交垃圾郵件[報告垃圾郵件和網路釣魚詐騙在網路上的 Outlook](../report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)中所述。|
|透過電子郵件別名提交垃圾郵件和非垃圾郵件|您可以提交垃圾郵件 （垃圾） 和非垃圾郵件 （不是垃圾郵件） 透過電子郵件給 Microsoft。如需詳細資訊，請參閱[提交垃圾郵件、 非垃圾郵件和網路釣魚詐騙郵件訊息給 Microsoft 進行分析](../submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)。|
|垃圾郵件和非垃圾郵件提交透過 Outlook 垃圾郵件回報網路上|您可以提交垃圾郵件和非垃圾郵件訊息給 Microsoft 透過 Outlook 垃圾郵件回報網路上。如需詳細資訊，請參閱[報表垃圾郵件和網路釣魚詐騙在網路上的 Outlook](../report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)。<br/> 此功能目前無法在網頁客戶的 outlook 其 Exchange Server 2013 SP1 或更新版本的信箱透過 EOP 篩選。Exchange Online Outlook web 客戶上也會在不久的將來有這項功能。|
|使用者垃圾郵件隔離通知|使用者可以釋出自己被當成垃圾郵件隔離的郵件並選擇性報告這些郵件不是垃圾郵件透過使用者垃圾郵件通知訊息。必須設定及[設定使用者垃圾郵件通知在 Exchange Online](../configure-end-user-spam-notifications-in-exchange-online.md)或[在 EOP 中的設定使用者垃圾郵件通知](../configure-end-user-spam-notifications-in-eop.md)中所述啟用系統管理員，這些電子郵件通知。|
|使用者垃圾郵件隔離通知頻率|此頻率預設為 3 天，可設定為 1 到 15 天。|
|讓系統管理員設定使用者垃圾郵件隔離通知語言的功能|此功能適用於使用者及系統管理員。如需詳細資訊，請參閱 [Find and release quarantined messages as an administrator](../find-and-release-quarantined-messages-as-an-administrator.md) 或 [Find and Release Quarantined Messages as an End User](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx)。  |
|透過網頁存取和管理隔離區中的郵件|此功能適用於使用者及系統管理員。如需詳細資訊，請參閱 [Find and release quarantined messages as an administrator](../find-and-release-quarantined-messages-as-an-administrator.md) 或 [Find and Release Quarantined Messages as an End User](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx)。  |
|搜尋隔離的功能|在隔離區中搜尋特定垃圾郵件的功能，適用於系統管理員和使用者。如需詳細資訊，請參閱 [Find and release quarantined messages as an administrator](../find-and-release-quarantined-messages-as-an-administrator.md) 或 [Find and Release Quarantined Messages as an End User](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx)。  |
|從 Exchange 系統管理中心檢視垃圾郵件隔離郵件標頭|檢視隔離中的郵件標題之後，您也可以複製郵件標頭文字並將它貼到[郵件標頭分析器](https://testconnectivity.microsoft.com/?tabid=mha)，可提供資訊說明郵件發生了什麼事。|
|**反惡意程式碼保護**||
|多重引擎反惡意程式碼保護|多重的反惡意程式碼引擎可協助隨時自動保護我們的客戶。|
|停用惡意程式碼篩選的選項|您無法停用惡意程式碼篩選，因為我們會對透過服務來路由傳送的所有電子郵件強制進行反惡意程式碼掃描。我們相信，所有客戶協助提供一致且嚴密的保護層級，是協助保護您電子郵件環境時所需的深度防禦策略中很重要的一部份。因此，系統會自動為所有客戶啟用惡意程式碼篩選。|
|郵件內文及附件的惡意程式碼檢查|此服務會檢查郵件本文和所有郵件附件中的使用中裝載是否有惡意程式碼。|
|預設或自訂惡意程式碼警示通知|您必須時要傳送通知電子郵件的寄件者或系統管理員訊息偵測到惡意程式碼為與未傳送選項。刪除整個郵件時只會傳送這些通知。如需詳細資訊，請參閱[設定反惡意程式碼原則](../configure-anti-malware-policies.md)。|
|偵測到惡意程式碼時移除附件的選項|系統管理員可以選取是否要刪除整個郵件或刪除附件並將自訂的訊息傳送給收件者。如需詳細資訊，請參閱[設定反惡意程式碼原則](../configure-anti-malware-policies.md)。|
|反間諜軟體保護|反惡意程式碼保護內含防毒保護和反間諜軟體保護。|
|自訂每個使用者、群組或網域之惡意程式碼篩選原則的功能|針對 rlo，您可以建立自訂惡意程式碼篩選原則與您組織中套用至指定的使用者、 群組或網域。自訂原則優先順序一律優於預設原則，但您可以變更您的自訂原則的優先順序 （亦即執行順序）。如需詳細資訊，請參閱[設定反惡意程式碼原則](../configure-anti-malware-policies.md)。|
|**郵件路由和連接器**||
|條件式郵件路由|如需詳細資訊，請參閱[Create Connectors for Conditional Mail Routing](http://technet.microsoft.com/library/905dc235-1d2b-487e-a65a-516d92e88347.aspx)。|
|隨機或強制 TLS|連接器與使用隨機或強制 TLS。隨機 TLS 嘗試 TLS 連線，但不成功的 TLS 連線時使用的 SMTP 連線。強制 TLS 強制 TLS 連線，這表示郵件遭拒的 TLS 連線的失敗時。如需 TLS、 安全性及連接器的詳細資訊，請參閱 ＜ [Set up 與協力廠商組織的安全郵件流程的連接器](http://technet.microsoft.com/library/1ce4d6a4-41ba-4d1e-9ca9-e826252c1041.aspx)。|
|地區路由 (流向特定地區的郵件流程限制)|如需詳細資訊，請參閱 [Exchange Online Protection 概觀](exchange-online-protection-overview.md) 中的「EOP 資料中心」一節。|
|SMTP 連線檢查程式工具|如需使用此工具測試郵件流程的詳細資訊，請參閱 [Test Mail Flow with the Remote Connectivity Analyzer](http://technet.microsoft.com/library/6c8c2964-d553-4329-8166-6e508dd63fa0.aspx)。|
|符合子網域|如需關於啟用公認的網域之子網域的雙向郵件流程的詳細資訊，請參閱[啟用 EOP 中子網域的電子郵件流程](http://technet.microsoft.com/library/b5684042-dadc-4111-95b3-c2fd06e368bf.aspx)。|
|**傳輸規則**||
|原則式篩選和動作|自訂原則根據 Exchange 傳輸規則。您可以篩選的網域、 關鍵字、 檔案名稱、 檔案類型、 主旨行、 郵件內文、 寄件者、 收件者、 標頭及 IP 位址。如需詳細資訊，請參閱[Mail flow 規則 （傳輸規則） 在 [Exchange Online Protection](mail-flow-rules-transport-rules-0.md)。|
|依據文字模式篩選|傳輸規則可以使用陣列或規則運算式來比對文字。您也可以使用單一字串或字串陣列來比對許多郵件屬性，例如地址、主旨、內文或附件名稱。如需詳細資訊，請參閱[Transport Rule Conditions (Predicates)](http://technet.microsoft.com/library/04edeaba-afd4-4207-b2cb-51bcc44e483c.aspx)。|
|自訂字典|傳輸規則可以包含較長的文字和關鍵字清單，提供和自訂字典相同的功能。|
|以網域為基礎的原則規則|傳輸規則的範圍可自訂以比對寄件者或收件者網域名稱、IP 位址範圍、地址關鍵字或模式、群組成員資格和其他條件。如需詳細資訊，請參閱[Transport Rule Conditions (Predicates)](http://technet.microsoft.com/library/04edeaba-afd4-4207-b2cb-51bcc44e483c.aspx)。  |
|掃描附件|您可以建立規則來掃描檔案名稱、副檔名以及附件的內容。|
|將原則規則通知傳送給寄件者|您可以透過「**拒絕此郵件並包含說明**」或「**拒絕其增強型狀態碼為此的郵件**」動作，來拒絕郵件並將未傳遞回報 (NDR) 傳送給寄件者。如需詳細資訊，請參閱 [Transport rule actions](http://technet.microsoft.com/library/f8621ecb-a177-4025-9011-a6569999746a.aspx)。 |
|將郵件傳送至固定位址 (例如將郵件重新導向或複製到特定的位址)|傳輸規則可以重新導向、新增副本或密件副本收件者、僅新增收件者，以及其他選項。如需詳細資訊，請參閱[Transport rule actions](http://technet.microsoft.com/library/f8621ecb-a177-4025-9011-a6569999746a.aspx)。|
|輕易跨多個規則調整規則優先順序的功能|使用 Exchange 系統管理員中心來變更規則的處理順序。如需詳細資訊，請參閱[Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx)。  |
|篩選郵件然後變更郵件之路由或屬性的功能|您可以根據各種不同的條件篩選郵件，然後套用至每封郵件的 [一系列的動作。如需詳細資訊，請參閱[Mail flow 規則 （傳輸規則） 在 [Exchange Online Protection](mail-flow-rules-transport-rules-0.md)。|
|根據規則變更郵件的垃圾郵件信賴等級。|您可以檢查中傳輸訊息並指派給它根據您選擇的準則的垃圾郵件信賴等級。如需詳細資訊，請參閱[使用郵件流程規則將郵件中的垃圾郵件信賴等級 (SCL)](../use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。|
|檢查郵件附件|您可以檢查附件的內容或附加檔案的特性，並定義根據檢查結果所要採取的動作。如需詳細資訊，請參閱[Using transport rules to inspect message attachments](http://technet.microsoft.com/library/874d1c78-a8ec-4938-b388-d3208c2fa971.aspx)。  |
|**系統管理**||
|Web 式管理|EOP 系統管理員可以管理透過支援 60 種語言中的 Exchange 系統管理中心 (EAC) 介面的服務。如需詳細資訊，請參閱[Exchange 系統管理中心在 Exchange Online Protection ](../exchange-admin-center-in-exchange-online-protection-eop.md)。|
|目錄同步處理|目錄同步作業可透過 Azure Active Directory 同步處理工具 使用。如需詳細資訊，請參閱 [管理 EOP 中的郵件使用者](manage-mail-users-in-eop.md) 中的「使用目錄同步作業管理郵件使用者」一節。  |
|目錄架構邊緣封鎖 (DBEB)|DBEB 功能可讓您在服務網路的周邊處拒絕無效收件者的郵件。DBEB 可讓系統管理員將已啟用郵件的收件者新增至 Office 365，並封鎖所有傳送的目標電子郵件地址沒有顯示在 Office 365 中的郵件。如需設定 DBEB 的詳細資訊，請參閱 [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx)。  |
|遠端 Windows PowerShell 存取|透過遠端 Windows PowerShell 可使用完整的 EOP 功能。如需詳細資訊，請參閱 [Exchange Online Protection 中的 PowerShell](http://technet.microsoft.com/library/f7918a88-774a-405e-945b-bc2f5ee9f748.aspx)。  |
|**回報和記錄**||
|郵件追蹤|郵件追蹤功能在電子郵件通過服務時，讓您以系統管理員的身分追蹤電子郵件。它可以協助您判斷服務是否已接收、拒絕、延遲或傳遞目標電子郵件。此舉可讓您有效回答使用者的問題、疑難排解郵件流程問題、驗證原則變更，並減少連絡技術支援尋求協助的需求。如需詳細資訊，請參閱 [Trace an Email Message](http://technet.microsoft.com/library/0c83cde6-5b09-4106-8587-c200cdc59094.aspx)。  |
|Web 式報告|Office 365 系統管理員中心裡的郵件保護報告會提供郵件資料。例如，您可以監視偵測到多少垃圾郵件和惡意程式碼，或符合傳輸規則的程度。透過這些互動式報告，您可以快速取得摘要資料的視覺報告，並深入查看個別郵件的詳細資料，最多可回溯 90 天。如需詳細資訊，請參閱 [Use mail protection reports in Office 365 to view data about malware, spam, and rule detections](http://technet.microsoft.com/library/bcef7984-4bfa-4ca8-9fa5-a65af8618f5d.aspx)。  |
|透過 Excel 報告活頁簿提供詳細報告|另也有 Excel 2013 報告活頁簿形式的電子郵件保護報告。不過，建議您改為使用增強型 Office 365 系統管理中心報告。Excel 2013 報告活頁簿預計將在未來被取代。|
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
   

