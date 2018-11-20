---
title: 建立、測試及調整 DLP 原則
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.NewPolicyFromTemplate
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_IP
search.appverid:
- MET150
ms.assetid: 59414438-99f5-488b-975c-5023f2254369
description: '若要開始使用 DLP 原則的最簡單的、 最常見方式是使用其中一個包含在 Office 365 中的範本。 '
ms.openlocfilehash: 1d4697811a5d8dd426fed80d3d60bcd2fbea6335
ms.sourcegitcommit: 42c7ad69f95fc4d2de13293b39cc44931b9f82e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/14/2018
ms.locfileid: "26522785"
---
# <a name="create-test-and-tune-a-dlp-policy"></a>建立、測試及調整 DLP 原則

**主要作者** </br>
Paul Cunningham、 Microsoft MVP </br>
[實用 365](https://practical365.com/) </br>
[@Practical365](https://twitter.com/practical365)</br>
__________________________________________________

資料外洩防護是專門設計來協助防止有意或意外的敏感資訊公開給不想要對象貴組織的 Office 365 的符合性功能。DLP 有其不在 Exchange Server 與 Exchange Online 中的根目錄，也適用於 SharePoint Online 和 OneDrive for Business。

DLP 使用內容分析引擎来檢查的電子郵件及檔案內容尋找敏感資訊例如信用卡號碼和個人識別資訊 (PII)。敏感資訊通常不應該以電子郵件、 傳送或包含在文件，但不進行例如加密電子郵件訊息或檔案的其他步驟。您可以使用 DLP 偵測敏感資訊並例如採取動作：

- 記錄的事件稽核用途
- 顯示一則警告訊息給使用者傳送電子郵件或共用檔案
- 主動封鎖的電子郵件或檔案共用中發生

有時客戶解除 DLP 因為它們不考慮自己有需要保護的資料類型。假設為機密資料，例如醫療記錄或財務資訊僅存在 like 醫療保健產業或執行線上存放區的公司。但是任何商務可以處理敏感資訊經常，即使其不知道該。在試算表的員工名稱及出生的日期是為客戶名稱和信用卡的詳細資訊的試算表為機密。與此類型的資訊與不同浮動周圍超過可能預期，如員工以安靜模式前往其日常性工作，以為 nothing 匯出 CSV 檔案從系統並以電子郵件傳送給其他人。您也可能對頻率員工傳送電子郵件而不考慮後果包含信用卡或銀行業詳細資料。

## <a name="how-sensitive-information-is-detected-by-dlp"></a>DLP 會偵測敏感資訊的方式

可識別敏感資訊的規則運算式 (RegEx) 中的模式比、 組合與其他例如鄰近的指標與特定關鍵字]，以比對的模式。此範例是信用卡號。因為撰寫信用卡號有 16 個位數。不過，這些數字可以寫入以不同的方式，例如 1111年-1111年-1111年-1111、 1111年 1111年 1111年 1111，或 1111111111111111。

任何 16 位數字串不一定是信用卡號、 它可能是從說明服務台系統或序號為硬體一段的票證數字。若要告訴信用卡號及無害 16 位數字字串之間的差異，計算會執行 （總和檢查碼） 若要確認號碼符合各種信用卡品牌來自已知的模式。

此外，例如"因為撰寫"或"AMEX"、 接近度以及可能是信用卡到期日期的日期值的關鍵字的鄰近會也被視為關於資料是否是信用卡號的決策。

換句話說，DLP 為智慧通常不夠辨識電子郵件中的下列兩個敘述性文字之間的差異：

- "可以您訂購我新膝上型電腦。使用我因為撰寫號碼 」 層 1111年-1111年-1111 1111、 到期 11/22 and 傳送我有時的估計的傳遞日期"。
- "我筆記型電腦序號 2222年 2222年-2222年 2222年，而且它已購買 11/2010年上。順便一提，是我旅行因為撰寫尚未？] 核准

保留書籤的良好參考會說明如何偵測到每種資訊類型本[主題敏感資訊類型](what-the-sensitive-information-types-look-for.md)。

## <a name="where-to-start-with-data-loss-prevention"></a>要從何處開始與資料外洩防護

當資料外洩的風險不完全明顯時，很難出其中完全應開始實作 DLP 運作。幸運地是，DLP 原則可以在 「 測試模式 」，讓您若要量測其有效性和正確性您開啟之前執行。

可透過 Exchange 系統管理中心中管理 Exchange Online 的 DLP 原則。但是您可以設定透過 [安全性及規範中心的所有工作負載的 DLP 原則讓我將使用此文章中示範的。在 [安全性及規範中心您會發現**資料外洩防護**底下的 DLP 原則 > **原則**。按一下 [在**建立原則**來啟動。

Office 365 提供的[DLP 原則範本](what-the-dlp-policy-templates-include.md)可用來建立 DLP 原則的範圍。假設您已準備澳大利亞商務。您可以當做篩選可分為三大類別的財務、 醫療和健康情況及隱私權原則範本以顯示只澳大利亞，相關。

![若要選擇國家或地區的選項](media/DLP-create-test-tune-choose-country.png)

此示範而言我將會選擇澳大利亞個人識別資訊 (PII) 的資料，包括澳洲稅檔案數 (TFN) 和駕照編號資訊類型。

![若要選擇的原則範本] 選項](media/DLP-create-test-tune-choose-policy-template.png)

提供新的 DLP 原則的名稱。預設的名稱會符合 DLP 原則範本，但因為可以從相同的範本建立多個原則您應選擇自己的其他描述性名稱。

![選項來命名您的原則](media/DLP-create-test-tune-name-policy.png)

選擇 [原則將會套用至的位置。DLP 原則可套用至 Exchange Online、 SharePoint Online 和 OneDrive for Business。我正在移至保留此原則的設定套用至所有位置。

![若要選擇的所有位置選項](media/DLP-create-test-tune-choose-locations.png)

在 [第一個**原則設定**步驟只接受預設值現在。有很多用途 DLP 原則中的自訂，但預設值是不錯的起點。

![若要自訂要保護的內容類型的選項](media/DLP-create-test-tune-default-customization-settings.png)

按一下 [**下一步**] 之後將出現與其他的**原則設定**] 頁面上使用多個自訂選項。針對您要測試的原則，以下是您可以開始進行一些調整。

- 我已關閉的現在，這是如果您剛正在測試取出的事項並不想要的任何尚未顯示給使用者的合理步驟的原則提示。原則提示對它們即將違反 DLP 原則的使用者顯示警告。例如 Outlook 使用者會看到它們已附加的檔案包含信用卡號警告和會使其電子郵件給被拒絕。原則提示的目標在於它發生前停止非相容的行為。
- 我也已降低的執行個體介於 10 到 1，使此原則會偵測任何共用澳大利亞 PII 資料，不只是大量資料的共用。
- 我還已新增附隨報告電子郵件的另一個收件者。

![其他原則設定](media/DLP-create-test-tune-more-policy-settings.png)

最後，我已設定最初在測試模式中執行此原則。請注意也會停用在測試模式中的原則提示的以下的選項。這可讓您已啟用原則的原則提示，但稍後決定是否要顯示或隱藏它們在測試期間的彈性。

![若要先測試出原則選項](media/DLP-create-test-tune-test-mode.png)

在最後檢閱畫面上按一下 [**建立**完成建立原則。

## <a name="test-a-dlp-policy"></a>測試 DLP 原則

新的 DLP 原則會開始約為 1 小時內生效。您可以坐並等待其透過標準使用者活動觸發或您可以嘗試自行觸發。稍早我連結到此[主題敏感資訊類型](what-the-sensitive-information-types-look-for.md)，可提供讓您如何觸發 DLP 符合項目的相關資訊。

例如，我建立本文的 DLP 原則將會偵測澳洲稅檔案數字 (TFN)。根據文件、 相符項目根據下列準則。

![文件等澳洲稅籍編號](media/DLP-create-test-tune-Australia-Tax-File-Number-doc.png)
 
而是鈍方式示範 TFN 偵測、 單字"稅籍編號"電子郵件並關閉鄰近 9 的數字字串會帶到處透過沒有任何問題。不會觸發 DLP 原則的原因是 9 數字字串必須通過指出它是有效的 TFN 而不只是數字的無害字串總和檢查碼。

![不會傳遞總和檢查碼的澳洲稅籍編號](media/DLP-create-test-tune-email-test1.png)

在比較，單字"稅籍編號"電子郵件與通過總和檢查碼有效 TFN 就會觸發該原則。針對以下記錄使用嗎 TFN 取自產生的網站有效，但不是正版 TFNs。沒有類似的網站所產生[有效但假信用卡號](http://www.fakecreditcardgenerator.net/)。因為其中一個最常見的錯誤測試 DLP 原則時使用的假數字不是有效將不會傳遞總和檢查碼 （與因此將不會觸發該原則） 這類網站是非常有用的。

![澳洲稅籍編號傳遞總和檢查碼](media/DLP-create-test-tune-email-test2.png)

附隨報告電子郵件包括偵測到的敏感資訊類型、 偵測多少個執行個體，並偵測信賴等級。

![偵測到附隨報告顯示稅籍編號](media/DLP-create-test-tune-email-incident-report.png)

如果您在測試模式中保留 DLP 原則並分析附隨報告電子郵件，您可以啟動取得風格的 DLP 原則，以及如何有效它時就會強制執行的正確性。除了附隨報告，您還可以[使用 DLP 報告](view-the-dlp-reports.md)查看原則符合項目的彙總的檢視您的租用戶之間。

## <a name="tune-a-dlp-policy"></a>調整的 DLP 原則

當您分析可能會想要之原則的行為方式有些調整您原則是落在圖形。為簡單的範例中，您可能會決定電子郵件中的一個 TFN 不 （I 認為它仍是，但開始吧與其這是因為示範） 的問題，但兩個或多個執行個體未發生問題。多個執行個體可能是例如員工從 HR 資料庫 CSV 匯出至外部廠商，例如外部的會計服務以電子郵件傳送 risky 案例。必定為某些項目您偏好偵測和封鎖。

在 [安全性及規範中心您可以編輯現有的原則以調整行為。

![若要編輯原則] 選項](media/DLP-create-test-tune-edit-policy.png)
 
您可以調整的位置設定使則會套用原則僅為特定的工作量或特定站台和帳戶。

![若要選擇特定位置的選項](media/DLP-create-test-tune-edit-locations.png)

您也可以調整的原則設定和編輯規則，以使它更符合您的需求。

![若要編輯規則的選項](media/DLP-create-test-tune-edit-rule.png)

編輯 DLP 原則內的規則時您可以變更：

- 條件包括類型及數目會觸發規則的機密資料的執行個體。
- 例如限制存取內容所採取的動作。
- 使用者通知會顯示給電子郵件用戶端或網頁瀏覽器中的使用者的原則提示。
- 使用者會覆寫，判斷使用者是否可選擇將其電子郵件或檔案共用仍繼續執行。
- 附隨報告，以通知系統管理員。

![若要編輯之規則的組件的選項](media/DLP-create-test-tune-editing-options.png)

此示範而言我已加入 user 通知 （請小心沒有足夠的使用者認識訓練這麼做的） 的原則，並允許使用者覆寫原則使用業務上理由或透過標幟為誤判。請注意您也可以自訂電子郵件和原則提示文字是否您想要包含任何貴組織的原則] 中的其他資訊或提示使用者如果有問題連絡支援人員。

![使用者通知和覆寫的選項](media/DLP-create-test-tune-user-notifications.png)

原則都包含大量和低量的處理這兩個規則，因此請務必編輯兩者與您想要的動作。這是將以不同方式視其特性的情況下有機會。例如，您可能會允許低量違規的覆寫但不是允許大量違規的覆寫。

![高容量與低量的一項規則的規則](media/DLP-create-test-tune-two-rules.png)

此外，如果您要真的封鎖或限制存取權是違反原則的內容，您需要設定要這樣的規則動作。

![若要限制存取內容的選項](media/DLP-create-test-tune-restrict-access-action.png)

後將那些變更儲存至原則設定，也需要傳回主要設定] 頁面上的原則並啟用要顯示給使用者的原則提示此原則會在測試模式時的選項。這是一個有效的方式來將您的使用者，引進 DLP 原則及使用者認識訓練、 執行而不影響到太多誤判造成影響其產能。

![若要在測試模式中顯示原則提示] 選項](media/DLP-create-test-tune-show-policy-tips.png)

在伺服器端 （或如果您偏好雲端側）、 變更可能不會立即生效，因為各種處理間隔。如果您正在進行會向使用者顯示新的原則提示的 DLP 原則變更，使用者可能不會看到所做的變更會在其 Outlook 用戶端，會每隔 24 小時檢查原則的變更立即生效。如果您想要延展測試的速度加快，您可以使用此登錄修正程式[清除 PolicyNudges 機碼從上次下載時間戳記](https://support.microsoft.com/en-au/help/2823261/changes-to-a-data-loss-prevention-policy-don-t-take-effect-in-outlook?__hstc=18650278.46377037dc0a82baa8a30f0ef07a7b2f.1538687978676.1538693509953.1540315763430.3&__hssc=18650278.1.1540315763430&__hsfp=3446956451)。Outlook 會下載最新的原則資訊下次您重新啟動並開始撰寫電子郵件訊息。

如果您有啟用的原則提示，使用者會開始請參閱在 Outlook 中的提示，並可以報告誤判您時所發生。

![使用報告誤判選項的原則提示](media/DLP-create-test-tune-policy-tip-in-outlook.png)

## <a name="investigate-false-positives"></a>調查誤判

DLP 原則範本不完美官方現成可用。很有可能您會發現發生在環境中，也就是為何不那麼重要 DLP 部署到簡化您的方式，某些誤判花費的時間來充分測試及調整您的原則。

以下是範例為誤判。此電子郵件會有太問題。使用者為其行動電話號碼提供給某人，並包括其電子郵件簽章。

![顯示 false 正數資訊的電子郵件](media/DLP-create-test-tune-false-positive-email.png)
 
使用者收到下列警告電子郵件包含敏感資訊原則提示，但尤其是澳洲駕照編號。

![以原則提示中的報告誤判] 選項](media/DLP-create-test-tune-policy-tip-closeup.png)

使用者可以報告誤判，並系統管理員可以尋找到它已經發生的原因。附隨報告電子郵件中的電子郵件會被標記為誤判。

![附隨報告顯示誤判](media/DLP-create-test-tune-false-positive-incident-report.png)

這個驅動程式授權案例是以深入探究良好的範例。此誤判發生在於"澳洲駕照"類型會觸發 （即使有一個是 10 位數字串的一部分）、 任何 9 數字字串關鍵字"雪梨 nsw"300 個字元距離的原因 （不區分大小寫）。讓它就會觸發的電話號碼和電子郵件簽章，僅因為使用者處於雪梨的變化。

有趣的是，如果"雪梨、 NSW"有逗號，就不會觸發 DLP 原則。我有任何想法為何逗點會使任何差異 here 也為何澳洲駕授權資訊類型、 關鍵字中不含其他城市 （英文） 和 states 在澳洲但是那里您前往。如此，可以我們怎麼其相關資訊？有幾個選項。

其中一個選項是從原則移除澳洲駕授權資訊類型。由於 DLP 原則範本的一部分是在該處但我們不強制使用它。如果您只是興趣稅檔案號碼和不驅動程式的授權，您可以只移除。例如，您可以移除低量原則中的規則，但保留在 [大量規則使仍偵測到的多個驅動程式授權的清單。

![若要刪除規則的敏感資訊類型的選項](media/DLP-create-test-tune-delete-low-volume-rule.png)
 
另一個作法是只要增加的執行個體計數，使駕授權低量僅偵測到如有多個執行個體。

![若要編輯的執行個體計數] 選項](media/DLP-create-test-tune-edit-instance-count.png)

除了變更的執行個體計數，您也可以調整的相符項目正確性 （或信賴等級）。如果您的敏感資訊類型具有多個模式，您可以使您的規則比對只特定模式調整 [您的規則上的相符項目精準度。例如，若要協助減少誤判，您可以設定您的規則比對正確性使其符合最高的信賴等級的圖樣。了解信賴等級的計算方式是有點 （和超過此文章範圍），但以下是[如何使用以調整規則的信賴等級](https://docs.microsoft.com/en-us/office365/securitycompliance/data-loss-prevention-policies#match-accuracy)的理想說明。

最後，如果您想要取得甚至更進階選項，您可以自訂任何敏感資訊類型--例如，您可以"雪梨 NSW"從清單中移除之關鍵字[澳洲駕照](https://docs.microsoft.com/en-us/office365/securitycompliance/what-the-sensitive-information-types-look-for#australia-drivers-license-number)，以避免誤判觸發上方。若要了解如何使用 XML 和 PowerShell 執行這項作業，請參閱[自訂內建的敏感資訊類型](customize-a-built-in-sensitive-information-type.md)本主題。

## <a name="turn-off-a-dlp-policy"></a>關閉 DLP 原則

當您很高興的 DLP 原則正確且有效偵測敏感資訊類型，並確認您的使用者準備好要如何處理正在進行中的原則，然後您可以啟用此原則。

![若要開啟 [原則] 選項](media/DLP-create-test-tune-turn-on-policy.png)
 
如果您正在等待原則會生效，[連線至 Office 365 的安全性與規範中心 PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)並執行[Get DlpCompliancePolicy 指令程式](https://docs.microsoft.com/en-us/powershell/module/exchange/policy-and-compliance-dlp/get-dlpcompliancepolicy?view=exchange-ps)，請參閱 DistributionStatus 時。

![在 PowerShell 中執行指令程式](media/DLP-create-test-tune-PowerShell.png)

之後忘記 DLP 原則，您應該執行一些最終測試您進行自己的確定預期的原則動作會發生。如果您嘗試測試之類的信用卡資料、 有網站線上如何產生範例信用卡資訊或其他個人資訊將傳遞總和檢查碼並觸發您的原則。

允許使用者覆寫原則將會呈現該選項給使用者的原則提示的一部分。

![允許使用者覆寫原則提示](media/DLP-create-test-tune-override-option.png)

限制內容的原則會呈現給使用者的警告一部分的原則提示，並防止傳送電子郵件。

![僅限於該內容的原則提示](media/DLP-create-test-tune-restrict-warning.png)

## <a name="summary"></a>摘要

資料外洩防護原則是適用於組織之所有類型。測試一些 DLP 原則是因為勝過之類的原則提示、 使用者覆寫及附隨報告控制低風險練習。以安靜模式可以測試以查看您的組織中已經發生何種類型的違規一些 DLP 原則然後並特殊功能原則和低 false 誤判率、 教育使用者 what's 允許並不允許，然後導入 DLP 原則至組織。
