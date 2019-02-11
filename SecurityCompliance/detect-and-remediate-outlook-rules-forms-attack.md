---
title: 偵測與修復 Outlook 規則和自訂表單資料隱碼攻擊攻擊的 Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/23/2018
ms.audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- Strat_O365_IP
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
description: 了解如何將能辨識和修復 Outlook 規則和 Office 365 中的自訂表單資料隱碼攻擊攻擊
ms.openlocfilehash: 1067d7c791217c146fedea839754e45f76ef5d8e
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2019
ms.locfileid: "29603754"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks-in-office-365"></a>偵測並修復 Office 365 中 Outlook 規則與自訂表單資料隱碼攻擊

**摘要**了解如何辨識及修復 Outlook 規則與 Office 365 中的自訂表單資料隱碼攻擊攻擊。

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a>什麼是 Outlook 規則和自訂表單資料隱碼攻擊？
攻擊者已達到帳戶在租用並取得之後，那里要嘗試並建立能夠在停留在或能夠在得到他們會發現並移除之後。這會呼叫建立持續性機制。他們可以執行此作業的兩種方式是由利用 Outlook 規則或插入到 Outlook 的自訂表單。在這兩種情況下，規則] 或 [表單是從同步處理至桌面用戶端的雲端服務讓完整格式和重新安裝用戶端軟體不消除插入機制。這是因為 Outlook 用戶端軟體重新連線至雲端信箱時它將重新下載規則及從雲端的表單。一旦規則和表單已備妥、 攻擊者會使用這些項目的執行遠端或自訂程式碼，通常是在本機電腦上安裝惡意程式碼。惡意程式碼再重新竊取認證或執行其他非法活動。好消息是如果您保留為最新版修補時將用戶端，您不容易受到威脅為目前的 Outlook 用戶端預設封鎖這兩個機制。 

攻擊通常會遵循下列模式：

規則攻擊
1. 攻擊者竊取使用者名稱和密碼的其中一個使用者。
2. 攻擊者再登入該使用者的 Exchange 信箱。信箱可以是在 Exchange online 或 Exchange 內部部署。
3. 攻擊者接著會轉接規則建立的信箱會收到電子郵件符合規則的準則時所觸發的信箱。規則的條件以及觸發程序電子郵件的內容是特製彼此的。
4. 攻擊者通常使用他們的信箱使用者所傳送的觸發電子郵件。
5. 接收電子郵件、 時就會觸發規則。規則的動作通常是要啟動遠端 (WebDAV) 伺服器應用程式。
6. 應用程式通常惡意程式碼、 [Powershell 帝國](https://www.powershellempire.com/)，例如在本機上安裝使用者的電腦。
7. 惡意程式碼可讓攻擊者重新竊取使用者的使用者名稱及密碼或其他認證從本機電腦與執行其他惡意的活動。

表單攻擊
1. 攻擊者竊取使用者名稱和密碼的其中一個使用者。
2. 攻擊者再登入該使用者的 Exchange 信箱。信箱可以是在 Exchange online 或 Exchange 內部部署。
3. 攻擊者然後會建立自訂郵件表單範本，並將它插入到使用者的信箱。 信箱會收到要求載入自訂表單的信箱的電子郵件時就會觸發自訂表單。自訂表單和電子郵件的格式是針對彼此特製。
4. 攻擊者通常使用他們的信箱使用者、 所傳送的觸發電子郵件。
5. 載入表單時接收電子郵件、 時。表單啟動遠端 (WebDAV) 伺服器應用程式。
6. 應用程式通常惡意程式碼、 [Powershell 帝國](https://www.powershellempire.com/)，例如在本機上安裝使用者的電腦。
7. 惡意程式碼可讓攻擊者重新竊取使用者的使用者名稱及密碼或其他認證從本機電腦與執行其他惡意的活動。


## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a>哪些規則和自訂表單資料隱碼攻擊可能看起來 Office 365？

這些保存性機制可能性注意到您的使用者所造成，在某些情況下甚至可能看不到它們。 本文將告訴您如何尋找任何七個告示牌 （危害指標） 下面所列。如果您發現任何這些，您需要採取的補救步驟。

- 規則的指標危害
    - 規則動作是要啟動的應用程式。
    - 規則會參照 EXE、 ZIP 或 URL。
    - 在本機機器，尋找源自 Outlook PID 的新程序開始。
- 自訂表單的指標危害 
    - 自訂表單存在儲存為他們自己的郵件類別。
    - 郵件類別包含可執行程式碼。
    - 通常儲存在個人表單檔案庫] 或 [收件匣] 資料夾中。
    - 表單是名為 IPM。附註。[自訂名稱]。

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a>尋找的此跡象並確認它的步驟
您可以使用下列兩種方法之一來確認攻擊。
- 手動檢查規則和每個信箱使用 Outlook 用戶端的表單。 這個方法是充分的認知，但只能用來檢查信箱使用者一次可以是很耗時如果您有許多使用者檢查。 它也會導致破壞您正在執行中的] 核取的電腦。
- 使用[Get AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell 指令碼來自動傾印在租用轉寄規則和自訂表單的所有使用者的所有郵件。這是最快和最安全的方法與最少量的額外負荷。


### <a name="confirm-the-rules-attack-using-the-outlook-client"></a>確認規則攻擊使用 Outlook 用戶端
1. 開啟使用者的 Outlook 用戶端為使用者。 使用者可能需要您在檢查其信箱上的規則的說明。
2. 請參閱[電子郵件訊息使用規則管理](https://support.office.com/article/manage-email-messages-by-using-rules-c24f5dea-9465-4df4-ad17-a50704d66c59#ID0EAABAAA=2010)文章如何開啟規則介面的 Outlook 2007、 2010年或 2013年版本中的程序。
3. 尋找規則未建立使用者，或任何未預期的規則或規則可疑的名稱。
4. 規則動作的規則描述中尋找該 start 和應用程式或參照。EXE、。ZIP 檔案，或啟動 URL。
5. 尋找新的處理序開始使用 Outlook 程序識別碼。 請參閱[尋找的程序識別碼](https://docs.microsoft.com/windows-hardware/drivers/debugger/finding-the-process-id)。

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a>步驟以確認使用 Outlook 用戶端表單攻擊
1. 開啟使用者的 Outlook 用戶端為使用者。
2. 遵循 Outlook 使用者版本的步驟，請在[顯示 [開發人員] 索引標籤](https://support.office.com/article/show-the-developer-tab-e1192344-5e56-4d45-931b-e5fd9bea2d45)。
3. 在 Outlook 中開啟 [立即可見的開發人員] 索引標籤，按一下 [**設計表單**。
4. 從 [**搜尋]** 清單中選取**收件匣**。尋找任何自訂表單。 自訂表單是罕見的所有有任何自訂表單，如果值得更深入的外觀。
5. 調查特別標示為隱藏任何自訂表單。
6. 開啟任何自訂表單，並在 [**表單**] 群組中按一下 [**檢視程式碼**來查看項目執行載入表單時。

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a>步驟以確認使用 PowerShell 規則和表單攻擊
若要驗證規則的最簡單方式或自訂表單攻擊是執行[Get AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell 指令碼。 此指令碼連線至您的租用戶中的每個信箱的所有規則會將傾都印和表單至兩個.csv 檔案。

#### <a name="pre-requisites"></a>先決條件
您必須執行指令碼，因為指令碼會連接至租用讀取規則及表單中每個信箱的全域系統管理員權限。

1. 登入您要執行指令碼從本機系統管理員的權限的機器。
2. 下載或從 GitHub 取得 AllTenantRulesAndForms.ps1 指令碼複製至會從中執行它的資料夾。 指令碼會建立這個資料夾、 MailboxFormsExport-yyyy-公釐-dd.csv，與 MailboxRulesExport yyyy-公釐 dd.csv 兩個日期戳記檔。
3. 開啟 [以系統管理員身分的 PowerShell 執行個體，並開啟儲存指令碼的資料夾。
4. 執行此 PowerShell 命令列，如下所示`.\Get-AllTenantRulesAndForms.ps1`.\Get-AllTenantRulesAndForms.ps1

#### <a name="interpreting-the-output"></a>解譯輸出

MailboxRulesExport-*-yyyy-mm-dd*.csv – 包含應用程式] 或 [可執行檔的巨集指令的條件，檢查 （一個資料列） 的規則。
- ActionType (欄 A –) 如果您看到值"ID_ACTION_CUSTOM"的規則是可能遭到惡意。
- IsPotentiallyMalicious （資料行 D）-如果此值為"TRUE"，規則會有可能遭到惡意。
- ActionCommand （資料行 G） – 這會列出應用程式或任何檔案與.exe、.zip 副檔名或的 URL，不應該是有、 參照的項目規則是否有可能遭到惡意。

MailboxFormsExport-*-yyyy-mm-dd*.csv – 一般會使用自訂表單的情況很少見。 如果您發現任何活頁簿中，您會開啟該使用者的信箱並檢查表單本身。 如果貴組織沒有不將它有刻意、 很有可能遭到惡意。



## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a>如何停止及修復 Outlook 規則和表單攻擊
如果您發現任何的其中一個這些攻擊證據、 補救簡單，只從信箱中刪除規則] 或 [表單。您可以使用 Outlook 用戶端或使用遠端 PowerShell 來移除規則來這麼做。

### <a name="using-outlook"></a>使用 Outlook
1. 識別使用者使用 outlook 的所有裝置。 他們將所有需要清除潛在的惡意程式碼。 不允許使用者登入並使用電子郵件之前要清除所有的裝置。
2. 請依照每個裝置中[刪除規則](https://support.office.com/article/Delete-a-rule-2F0E7139-F696-4422-8498-44846DB9067F)的步驟。
3. 如果您不確定關於其他惡意程式碼的狀態，您可以格式化，並重新安裝在裝置上的所有軟體。 行動裝置的您可以遵循原廠圖像重設之裝置的製造商步驟。
4. 安裝 Outlook 的最新版本。 請記住目前的 Outlook 版本會封鎖預設此攻擊的這兩種類型。
5. 一旦已經移除所有的離線複本的信箱，重設使用者密碼 （使用的高品質一個），並遵循中[的 Office 365 使用者的設定多重要素驗證](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6)的步驟如果 MFA 不已經啟用。這可確保使用者的認證未公開透過其他方式 （例如網路釣魚或密碼重複使用）。

### <a name="using-powershell"></a>使用 PowerShell
有兩個遠端 PowerShell 指令程式可用來移除或停用危險的規則。只是遵循的步驟。
 
Exchange server 上之信箱的步驟

1. Exchange server 使用遠端 PowerShell 連線。遵循[連線到 Exchange 伺服器使用遠端 PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell?view=exchange-ps)中的步驟。
2. 如果您想要完全移除單一規則、 多個規則或所有規則信箱使用[移除收件匣規則指令程式](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Remove-InboxRule?view=exchange-ps)-使用此選項可完全移除一個、 多個、 或所有規則從信箱。
3. 如果您想要保留規則和其內容的進一步調查使用[Disable-inboxrule 指令程式](https://technet.microsoft.com/en-us/library/dd298120(v=exchg.160).aspx)。 

在 Exchange Online 信箱的步驟
1. 遵循[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)中的步驟。
2.  如果您想要完全移除單一規則、 多個規則或從信箱的所有規則會使用[移除收件匣規則指令程式](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Remove-InboxRule?view=exchange-ps)。
3.  如果您想要保留規則和其內容的進一步調查使用[Disable-inboxrule 指令程式](https://technet.microsoft.com/en-us/library/dd298120(v=exchg.160).aspx)。 

## <a name="how-to-minimize-future-attacks"></a>如何減少未來的攻擊

### <a name="first-protect-your-accounts"></a>第一個： 保護您的帳戶

之後他們有竊取或達到您的使用者帳戶的其中一個規則和表單惡意只適用於由攻擊。因此，若要防止對您的組織這些惡意使用您第一個步驟是積極地保護您的使用者帳戶。 某些帳戶已達到的常見方法是透過網路釣魚或[密碼噴射](http://www.dabcc.com/microsoft-defending-against-password-spray-attacks/)攻擊。



保護您的使用者帳戶和特別是在系統管理員帳戶的最佳方式是[設定多重要素驗證 Office 365 使用者](https://support.office.com/article/set-up-multi-factor-authentication-for-office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6)。 您也應該：
<ol>
    <li>監視<a href="https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports">存取及使用</a>您的使用者帳戶使用方式。您可能無法防止初始的破壞，但是您將會由提前偵測縮短持續時間和破壞的影響。您可以使用這些： <a href="https://support.office.com/article/overview-of-office-365-cloud-app-security-81f0ee9a-9645-45ab-ba56-de9cbccab475">Office 365 雲端應用程式安全性原則</a>，以監視您的帳戶及提醒上不尋常的活動。<ol type="a">
            <li><b>多個失敗的登入嘗試次數</b>此原則設定檔環境與觸發程序提醒使用者在相應的學基準，可能表示嘗試的破壞單一工作階段中執行多個失敗的登入活動時。</li>
            <li><b>Impossible 旅行社</b>-此原則設定檔環境及活動會從不同位置的相同使用者偵測到的兩個位置之間的預期的旅行時間較短的期間內時觸發提醒。這可能表示不同的使用者使用相同的認證。偵測這個異常行為必須初始學習的七天內的期間它可學習新使用者的活動圖樣。</li>
            <li><b>不尋常模擬活動 （由使用者）</b>-此原則設定檔環境和使用者在執行時多個模擬的活動單一工作階段相對於基線學會，這可能表示嘗試的破壞觸發提醒。</li>
        </ol>
    </li>
    <li>利用<a href="https://securescore.office.com/">Office 365 安全分數</a>管理帳戶的安全性組態與行為類似的工具。 
    </li>
</ol> 

### <a name="second-keep-your-outlook-clients-current"></a>第二個： Outlook 用戶端維持最新狀態
完全更新及修補狀態版本的 Outlook 2013 和 2016年根據預設停用的 「 啟動應用程式 」 規則/表單巨集指令。 如此可確保即使攻擊者破壞帳戶、 規則及表單動作將會封鎖。 您可以安裝最新的更新和安全性修補程式[安裝 Office 更新](https://support.office.com/article/Install-Office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5)中的步驟。

以下是 Outlook 2013 和 2016年用戶端的修補程式版本：
- Outlook 2013: 15.0.4937.1000 大於或等於
- Outlook 2016: 16.0.4534.1001 大於或等於

如需有關個別安全性修補程式的詳細資訊，請參閱：

- [Outlook 2013 安全性修補程式](https://support.microsoft.com/en-us/help/3191938) 
- [Outlook 2016 安全性修補程式](https://support.microsoft.com/en-us/help/3191883)

### <a name="third-monitor-your-outlook-clients"></a>第三個： 監視 Outlook 用戶端
請注意即使有的修補程式和已安裝更新，它可能的攻擊者變更本機電腦設定，以重新啟用 「 啟動應用程式 」 行為。您可以使用[進階群組原則管理](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/)來監視及強制執行您的用戶端上的本機電腦原則。  
您可以查看如果 「 啟動應用程式 」 已重新啟用透過登錄中覆寫使用[如何檢視使用 64 位元版本的 Windows 系統登錄](https://support.microsoft.com/en-us/help/305097/how-to-view-the-system-registry-by-using-64-bit-versions-of-windows)中的資訊。 檢查下列子機碼： 

- Outlook 2016: HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\
- Outlook 2013: HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\

尋找 EnableUnsafeClientMailRules 的索引鍵。如果它有且設為 1，Outlook 安全性修補程式已覆寫與電腦是遭受表單/規則攻擊。如果值為 0，已停用的 「 啟動應用程式 」 巨集指令。 如果已安裝的 Outlook 更新及修補狀態版本，而且此登錄機碼不存在，則系統不會受到攻擊。

內部部署 Exchange 安裝客戶應考慮封鎖較舊版本的 Outlook 沒有可用的修補程式。可以[設定 Outlook 用戶端封鎖](https://technet.microsoft.com/en-us/library/dd335207(v=exchg.150).aspx)」 文件中找到此程序的詳細資訊。

## <a name="secure-office-365-like-a-cybersecurity-pro"></a>安全 like cybersecurity 專業人員的 Office 365
您的 Office 365 訂閱隨附一組功能強大的安全性功能可用來保護您的資料與您的使用者。 使用[Office 365 安全性藍圖： 最常用的優先順序的前 30 天 90 天和超過](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352)實作 Microsoft 建議的最佳作法保護您的 Office 365 租用戶。
- 若要完成工作前 30 天的工作。 這些包含立即影響且為 low 影響您的使用者。
- 若要完成 90 天的工作。這些需要規劃和實作但大幅改善了安全性狀態的更多時間。
- 超過 90 天。您在第一個 90 天工作建立這些增強功能。

## <a name="see-also"></a>另請參閱：
- [惡意 Outlook 規則](https://silentbreaksecurity.com/malicious-outlook-rules/)的相關規則向量 SilentBreak 安全性文章提供如何詳細的檢閱 Outlook 規則。 
- 關於 Mailrule Pwnage Sensepost 部落格上的[MAPI over HTTP 和 Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/)討論稱為可讓您利用信箱透過 Outlook 規則的尺規輔助工具。
- [Outlook 表單與殼層](https://sensepost.com/blog/2017/outlook-forms-and-shells/)關於表單威脅向量 Sensepost 部落格上。 
- [尺規程式碼基底](https://github.com/sensepost/ruler)
- [尺規指標的危害](https://github.com/sensepost/notruler/blob/master/iocs.md)