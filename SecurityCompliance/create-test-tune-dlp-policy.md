---
title: 建立、測試及調整 DLP 原則
ms.author: deniseb
author: denisebmsft
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.NewPolicyFromTemplate
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
ms.assetid: 59414438-99f5-488b-975c-5023f2254369
description: '要開始使用 DLP 原則，最簡單且最常見方式是使用 Office 365 所包含的其中一個範本。 '
ms.openlocfilehash: 32b0b4baa058fda031a58681e107b01bf207da55
ms.sourcegitcommit: 0d5a863f48914eeaaf29f7d2a2022618de186247
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2019
ms.locfileid: "34077959"
---
# <a name="create-test-and-tune-a-dlp-policy"></a>建立、測試及調整 DLP 原則

**主體作者** <br/>
Paul Cunningham, Microsoft MVP <br/>
[實際365](https://practical365.com/) <br/>
[@Practical365](https://twitter.com/practical365)<br/>
__________________________________________________

資料遺失防護是 Office 365 的符合性功能, 其設計目的是協助您的組織防止故意或意外暴露敏感資訊給不需要的各方。 DLP 在 Exchange Server 和 Exchange Online 中有其根目錄, 也適用于 SharePoint Online 和商務用 OneDrive。

DLP 會使用內容分析引擎來檢查電子郵件和檔案的內容, 以尋找敏感資訊, 例如信用卡號碼和個人身分識別資訊 (PII)。 機密資訊通常不是以電子郵件傳送, 或是包含在檔中, 而不需要額外的步驟, 例如加密電子郵件訊息或檔案。 您可以使用 DLP 來偵測敏感資訊, 並採取下列動作:

- 記錄事件以供審計之用
- 向傳送電子郵件或共用檔案的使用者顯示警告
- 主動封鎖電子郵件或檔案共用發生

有時客戶會因為不考慮需要保護的資料類型而關閉 DLP。 假設敏感性資料 (例如醫療記錄或財務資訊) 只存在於健康護理或執行線上存放區的公司。 但是任何公司都可以定期處理機密資訊, 即使他們不認識。 員工姓名和出生日期的試算表, 就像是客戶名稱和信用卡詳細資料的試算表一樣。 而這類資訊往往會圍繞您預期的方式來浮動, 因為員工不需要從系統中匯出 CSV 檔案, 並以電子郵件傳送給某人。 您也可能會驚訝于員工傳送包含信用卡或銀行詳細資料的電子郵件的頻率, 不會考慮結果。

## <a name="how-sensitive-information-is-detected-by-dlp"></a>DLP 如何偵測到敏感資訊

機密資訊會以正則運算式 (RegEx) 模式比對來識別, 並與其他指標 (例如特定關鍵字接近于相符的模式) 相結合。 這是信用卡號碼的範例。 簽證信用卡號碼有16位數位。 不過, 這些數位可以以不同的方式撰寫, 例如1111-1111-1111-1111、1111 1111 1111 1111 或1111111111111111。

任何16位數的字串不一定是信用卡號碼, 它可以是服務台系統的票據號碼, 或是硬體的序號。 若要說明信用卡號碼和無害16位字串之間的差異, 會執行計算 (checksum), 以確認號碼符合各種信用卡品牌的已知模式。

此外, 像是 "簽證" 或 "AMEX" 之類的關鍵字相近, 也有可能是信用卡到期日的最接近日期值, 也會被視為決定資料是否為信用卡號碼。

換句話說, DLP 通常會非常聰明, 以識別電子郵件中這兩種文字之間的差異:

- 「您可以定購新的膝上型電腦。 使用我的簽證號碼 1111-1111-1111-1111, 到期 11/22, 並在您有它的預估傳遞日期時傳送給我。
- 「我的膝上型電腦序號碼是 2222-2222-2222-2222, 且是在11/2010 上購買。 順便說一下, 我的旅行社是否已核准？

[保留書簽] 的良好參考是本主題說明如何偵測每種資訊類型的[敏感資訊類型](what-the-sensitive-information-types-look-for.md)。

## <a name="where-to-start-with-data-loss-prevention"></a>從資料遺失防護開始的位置

當資料洩漏風險完全不明顯時, 就很難完成應該從執行 DLP 開始的地方。 幸運的是, DLP 原則可以在「測試模式」中執行, 讓您在開啟之前測量它們的效能和準確性。

您可以透過 Exchange 系統管理中心來管理 Exchange Online 的 DLP 原則。 不過, 您可以透過安全性 & 合規性中心設定所有工作負載的 DLP 原則, 如此將會在本文中用來進行示範。 在安全性 & 規範中心中, 您會在**資料遺失防護** > **原則**下找到 DLP 原則。 按一下 [**建立要啟動的原則**]。

Office 365 提供一系列[dlp 原則範本](what-the-dlp-policy-templates-include.md), 您可以用來建立 dlp 原則。 假設您是澳大利亞的商務版。 您可以篩選原則範本, 只顯示與澳大利亞相關的原則範本, 其屬於財務、醫療和健康情況和隱私權的一般類別。

![選擇國家或地區的選項](media/DLP-create-test-tune-choose-country.png)

在這個示範中, 我將選擇澳大利亞個人身分識別資訊 (PII) 資料, 其中包含澳大利亞稅檔號碼 (TFN) 和駕駛執照號碼的資訊類型。

![選擇原則範本的選項](media/DLP-create-test-tune-choose-policy-template.png)

提供新的 DLP 原則名稱。 預設名稱會符合 DLP 原則範本, 但是您應該選擇更具描述性的名稱, 因為可以從相同的範本建立多個原則。

![用來命名原則的選項](media/DLP-create-test-tune-name-policy.png)

選擇原則將套用至的位置。 DLP 原則可套用至 Exchange Online、SharePoint Online 和商務用 OneDrive。 我要將此原則設定為套用至所有位置。

![選擇所有位置的選項](media/DLP-create-test-tune-choose-locations.png)

在第一個**原則設定**步驟中, 立即接受預設值。 在 DLP 原則中有很多您可以執行的自訂, 但預設值是一個不錯的起點。

![自訂要保護的內容類型的選項](media/DLP-create-test-tune-default-customization-settings.png)

按 **[下一步]** 後, 就會出現額外的 [**原則設定**] 頁面, 其中包含更多自訂選項。 對於您剛測試的原則, 以下是您可以開始進行一些調整的位置。

- 我現在已關閉原則提示, 如果您只是測試專案, 而不想要對使用者顯示任何專案, 則需要採取合理的步驟。 原則提示會對即將違反 DLP 原則的使用者顯示警告。 例如, Outlook 使用者會看到一則警告, 指出他們所附加的檔案包含信用卡號碼, 並將拒絕其電子郵件。 原則提示的目標是在發生之前先停止不相容的行為。
- 我也將實例數從10減少為 1, 因此此原則會偵測任何共用的澳大利亞 PII 資料, 而不只是大量共用資料。
- 我也已將另一位收件者新增至附隨報告電子郵件。

![其他原則設定](media/DLP-create-test-tune-more-policy-settings.png)

最後, 我已將此原則設定為先在測試模式中執行。 請注意, 在測試模式中也有一個選項可停用原則提示。 這可讓您靈活地在原則中啟用原則提示, 但接著決定要在測試期間顯示或隱藏它們。

![先測試原則的選項](media/DLP-create-test-tune-test-mode.png)

在最終的 [審閱] 畫面上, 按一下 [**建立**] 以完成建立原則。

## <a name="test-a-dlp-policy"></a>測試 DLP 原則

新的 DLP 原則會在大約1小時內開始生效。 您可以坐下來, 等待正常的使用者活動觸發, 也可以嘗試自行觸發。 更早的連結到此[主題的敏感資訊類型](what-the-sensitive-information-types-look-for.md), 可提供有關如何觸發 DLP 相符的資訊。

例如, 我為本文所建立的 DLP 原則會偵測到澳大利亞稅收檔編號 (TFN)。 根據檔, 相符項是以下列準則為基礎。

![澳大利亞稅務檔案編號的檔](media/DLP-create-test-tune-Australia-Tax-File-Number-doc.png)
 
若要以較相近的方式示範 TFN 偵測, 您可以在不發生任何問題的情況下, 使用包含 "稅收 file number" 一詞的電子郵件和接近接近的9位數位符串來進行 sail。 不觸發 DLP 原則的原因是, 9 位數的字串必須通過校驗和, 表示它是有效的 TFN, 而不只是一種無害的數位字串。

![未通過校驗和的澳大利亞稅務檔案編號](media/DLP-create-test-tune-email-test1.png)

相比之下, 如果電子郵件包含 "稅收 file number" 一詞, 而傳遞校驗和的有效 TFN 會觸發該原則。 在這裡的記錄中, 所使用的 TFN 是從產生有效但不是正版 TFNs 的網站取得。 有類似的網站會產生[有效但虛假的信用卡號碼](http://www.fakecreditcardgenerator.net/)。 這類網站非常有用, 因為測試 DLP 原則時最常見的錯誤之一, 是使用不正確虛設號碼, 而且不會傳遞校驗和 (因此不會觸發原則)。

![傳遞校驗和的澳大利亞稅務檔案編號](media/DLP-create-test-tune-email-test2.png)

[附隨報告] 電子郵件包括偵測到的敏感資訊類型、偵測到的實例數目, 以及偵測的信賴等級。

![顯示已偵測到稅務檔案號碼的附隨報告](media/DLP-create-test-tune-email-incident-report.png)

如果您在測試模式中保留 DLP 原則, 並分析附隨報告電子郵件, 您可以開始瞭解 DLP 原則的準確性, 以及強制執行的有效程度。 除了附隨報告之外, 您還可以[使用 DLP 報告](view-the-dlp-reports.md)來查看整個租使用者中原則相符專案的匯總視圖。

## <a name="tune-a-dlp-policy"></a>調整 DLP 原則

當您分析原則擊中時, 您可能會想要對原則的行為進行一些調整。 簡單的範例是, 您可能會判斷一封電子郵件中的一個 TFN 不是問題 (我認為它仍然是, 但為了示範, 讓我們繼續瞭解), 但有兩個以上的實例是問題。 多個實例可能是一種危險的案例, 例如員工從 HR 資料庫將 CSV 匯出至外部通訊錄 (例如, 外部會計服務) 的電子郵件。 確實是您想要偵測及封鎖的專案。

在安全性 & 合規性中心內, 您可以編輯現有原則以調整行為。

![編輯原則的選項](media/DLP-create-test-tune-edit-policy.png)
 
您可以調整位置設定, 讓原則僅套用至特定的工作負載, 或套用至特定的網站和帳戶。

![選擇特定位置的選項](media/DLP-create-test-tune-edit-locations.png)

您也可以調整原則設定, 並編輯規則, 以更符合您的需求。

![編輯規則的選項](media/DLP-create-test-tune-edit-rule.png)

在 DLP 原則內編輯規則時, 您可以變更:

- 條件, 包括將觸發規則之敏感性資料的實例類型和數目。
- 採取的動作, 例如限制存取內容。
- 使用者通知, 也就是在電子郵件客戶程式或網頁瀏覽器中顯示給使用者的原則提示。
- 使用者覆寫, 可決定使用者是否可以選擇繼續進行電子郵件或檔案共用。
- 附隨報告, 以通知系統管理員。

![編輯規則部分的選項](media/DLP-create-test-tune-editing-options.png)

在這個示範中, 我已將使用者通知新增至原則 (在沒有足夠的使用者意識訓練的情況下, 請小心), 並允許使用者以業務理由覆寫原則, 或將它標記為 false 陽性。 請注意, 如果您想要包含組織原則的任何其他資訊, 也可以自訂電子郵件和原則提示文字, 或者, 如果有任何問題, 則提示使用者與支援人員聯繫。

![使用者通知和覆寫的選項](media/DLP-create-test-tune-user-notifications.png)

原則包含兩個處理高容量和低容量的規則, 因此請務必使用您想要的動作來編輯。 這是視案例的特性而異的方式。 例如, 您可能會允許覆寫較低的磁片, 但不允許對高大量違規的覆寫。

![一種適用于高容量的規則和一種低容量的規則](media/DLP-create-test-tune-two-rules.png)

此外, 如果您想要實際封鎖或限制違反原則的內容存取, 您必須設定規則上的動作以執行此動作。

![限制存取內容的選項](media/DLP-create-test-tune-restrict-access-action.png)

將這些變更儲存至原則設定後, 我也必須回到原則的 [主要設定] 頁面, 並啟用當原則處於測試模式時, 向使用者顯示原則提示的選項。 這是一種有效的方式, 可以將 DLP 原則引入您的使用者, 並進行使用者認知訓練, 而不會有太多影響其生產力的誤報。

![在測試模式中顯示原則提示的選項](media/DLP-create-test-tune-show-policy-tips.png)

在伺服器端 (或您想要的雲端端) 上, 變更可能不會立即生效, 因為有各種處理間隔。 如果您要進行 DLP 原則變更, 以將新的原則提示顯示給使用者, 使用者可能不會看到其 Outlook 用戶端中的變更會立即生效, 這會檢查每24小時的原則變更。 如果您想要加快測試的速度, 您可以使用此登錄修補程式,[從 PolicyNudges 機碼清除最後下載的時間戳記](https://support.microsoft.com/en-au/help/2823261/changes-to-a-data-loss-prevention-policy-don-t-take-effect-in-outlook?__hstc=18650278.46377037dc0a82baa8a30f0ef07a7b2f.1538687978676.1538693509953.1540315763430.3&__hssc=18650278.1.1540315763430&__hsfp=3446956451)。 Outlook 會在您下次重新開機時下載最新的原則資訊, 並開始撰寫電子郵件。

如果您已啟用原則提示, 使用者將會開始看到 Outlook 中的秘訣, 而且在發生時可以向您報告錯誤。

![原則提示, 具有報告 false 正值的選項](media/DLP-create-test-tune-policy-tip-in-outlook.png)

## <a name="investigate-false-positives"></a>調查誤報

DLP 原則範本不會完全直接從盒中取出。 您可能會發現環境中有一些誤報, 這就是為什麼很重要的原因是讓您更容易進入 DLP 部署, 讓您花時間來充分測試和調整原則。

以下是 false 陽性的範例。 此電子郵件相當無害。 使用者將他們的行動電話號碼提供給某人, 並包含他們的電子郵件簽章。

![顯示 false 正值資訊的電子郵件](media/DLP-create-test-tune-false-positive-email.png)
 
但使用者會看到原則提示, 警告他們電子郵件包含敏感資訊, 特別是澳大利亞司機的授權號碼。

![在原則提示中報告 false 陽性的選項](media/DLP-create-test-tune-policy-tip-closeup.png)

使用者可以報告假肯定, 系統管理員可以查看其發生的原因。 在附隨報告電子郵件中, 會將電子郵件標示為 false 陽性。

![顯示 false 正值的附隨報告](media/DLP-create-test-tune-false-positive-incident-report.png)

此驅動程式的授權案例是深入瞭解的一個很好的範例。 發生這種錯誤的原因是, 任何9位數的字串 (甚至是10位數位符串的一部分) 將會觸發 "澳大利亞 Driver the License" 類型, 這些字元會在300字元接近于關鍵字 "悉尼 nsw" (不區分大小寫)。 因此, 它是由電話號碼和電子郵件簽章觸發, 只是因為使用者在悉尼。

有趣的是, 如果 "悉尼, NSW" 有逗點, 則不會觸發 DLP 原則。 我不知道為什麼逗號會在這裡產生任何差異, 而且澳大利亞的其他城市和狀態不會包含在澳大利亞駕照的授權資訊類型的關鍵字中, 但您可以在這裡找到。 那麼, 我們可以怎麼做呢？ 有幾個選項。

其中一個選項是從原則移除澳大利亞司機的授權資訊類型。 因為它是 DLP 原則範本的一部分, 但不會強制您使用它。 如果您只對稅務檔案編號, 而不是對驅動程式的授權感興趣, 您可以只將它移除。 例如, 您可以從原則的 [低容量] 規則中移除它, 但將它保留在 [高容量規則] 中, 讓多個驅動程式的清單仍可偵測到。

![從規則刪除敏感資訊類型的選項](media/DLP-create-test-tune-delete-low-volume-rule.png)
 
另一個選項是簡單地增加實例計數, 因此只有當有多個實例時, 才會偵測到低容量的驅動程式授權。

![編輯實例計數的選項](media/DLP-create-test-tune-edit-instance-count.png)

除了變更實例計數之外, 您也可以調整相符精確性 (或信賴等級)。 如果您的機密資訊類型有多個模式, 您可以調整規則中的相符準確度, 讓您的規則只符合特定模式。 例如, 為了協助減少誤報, 您可以設定規則的相符準確度, 使其只符合具有最高信賴等級的模式。 瞭解信賴等級的計算方式有點棘手 (超出此文章的範圍), 但以下是[如何使用信賴等級調整規則](https://docs.microsoft.com/en-us/office365/securitycompliance/data-loss-prevention-policies#match-accuracy)的好說明。

最後, 如果您想要更深入地取得, 您可以自訂任何敏感資訊類型--例如, 您可以從[澳大利亞駕照](https://docs.microsoft.com/en-us/office365/securitycompliance/what-the-sensitive-information-types-look-for#australia-drivers-license-number)的關鍵字清單中移除 "悉尼 NSW", 以消除上述假正向觸發。 若要瞭解如何使用 XML 和 PowerShell 來執行這項作業, 請參閱本主題關於[自訂內建的敏感資訊類型](customize-a-built-in-sensitive-information-type.md)。

## <a name="turn-off-a-dlp-policy"></a>關閉 DLP 原則

當您很高興, 您的 DLP 原則會正確且有效地偵測敏感資訊類型, 而您的使用者已準備好處理所需的原則, 您就可以啟用該原則。

![開啟原則的選項](media/DLP-create-test-tune-turn-on-policy.png)
 
如果您要查看原則何時生效, 請連線[至安全性 & 規範中心 PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps) , 並執行[DlpCompliancePolicy 指令程式](https://docs.microsoft.com/en-us/powershell/module/exchange/policy-and-compliance-dlp/get-dlpcompliancepolicy?view=exchange-ps), 以查看 DistributionStatus。

![在 PowerShell 中執行 Cmdlet](media/DLP-create-test-tune-PowerShell.png)

開啟 DLP 原則之後, 您應該對自己執行一些最終測試, 以確保預期的原則動作正在進行中。 如果您嘗試測試像是信用卡資料之類的內容, 則網站會有有關如何產生範例信用卡或其他個人資訊的資訊, 這些資訊會透過校驗和觸發您的原則。

允許使用者覆寫的原則會將該選項呈現給使用者, 成為原則提示的一部分。

![允許使用者覆寫的原則提示](media/DLP-create-test-tune-override-option.png)

限制內容的原則會將警告傳送給使用者, 成為原則提示的一部分, 並防止他們傳送電子郵件。

![內容受限的原則提示](media/DLP-create-test-tune-restrict-warning.png)

## <a name="summary"></a>摘要

資料遺失防護原則對所有類型的組織都很有用。 測試某些 DLP 原則是因為您對原則提示、使用者覆寫及附隨報告等專案所做的控制, 造成的風險很低。 您可以以安靜模式測試某些 DLP 原則, 以查看組織中已發生的違規類型, 然後使用低 false 正值來製作原則, 並對您的使用者提供允許且不允許的專案, 然後將 DLP 原則推出至公司.
