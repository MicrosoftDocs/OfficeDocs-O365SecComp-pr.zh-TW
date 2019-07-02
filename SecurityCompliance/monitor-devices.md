---
title: Microsoft 365 安全中心的裝置監視與報告
description: 說明如何讓您的裝置在組織中保持安全、最新和找出潛在威脅
keywords: 安全性、惡意程式碼、Microsoft 365、M365、security center、monitor、report、devices
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: 44fd28a0ba2ec72d999c89d183d85ccb496903ec
ms.sourcegitcommit: b9d8a43cb3afcdc8820bc9470c5707eff8fc6616
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/11/2019
ms.locfileid: "34852867"
---
# <a name="device-monitoring-and-reporting-in-microsoft-365-security-center"></a>Microsoft 365 安全中心的裝置監視與報告

在 Microsoft 365 安全中心中, 讓您的裝置安全、最新和找出潛在威脅。

## <a name="view-device-alerts"></a>查看裝置警示

從 Microsoft Defender ATP 取得裝置上有關違規活動及其他威脅的最新通知 (可使用 E5 授權)。 Microsoft 365 安全中心使用您喜歡的工作流程, 以較高的層次來監視這些警示。

### <a name="monitor-high-impact-alerts"></a>監視高影響警示

每個 Microsoft Defender ATP 警示都有相對應的嚴重性 (高、中、低或資訊), 指出對您的網路可能造成的影響 (如果不是自動)。  

使用**裝置警示嚴重度**卡片, 特別是針對更嚴重且可能需要立即回應的提醒。 您可以從這個卡片來查看 Microsoft Defender 安全中心入口網站上的詳細資訊。

![裝置警示嚴重卡](./media/security-docs/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a>瞭解警示的來源

Microsoft Defender ATP 會利用各種安全性感應器和智慧來源中的資料, 來產生警示。 例如, 它可以從 Windows Defender 防病毒和協力廠商反惡意程式碼使用偵測資訊, 以及透過 web 服務 API 提供的自訂威脅情報。

**裝置警示偵測**的來源卡片顯示依來源進行的警示散佈。 這張卡片可協助您追蹤與特定來源相關的活動, 特別是自訂來源。 您也可以使用此功能, 將來自未設定為自動封鎖惡意活動或元件之感應器的警示集中在。

![裝置警示偵測來源卡](./media/security-docs/device-alert-detection-sources.png)

您可以從這個卡片來查看 Microsoft Defender 安全中心入口網站上的詳細資訊。

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a>瞭解觸發警示的威脅類型

Microsoft Defender ATP 會將每個警示排序為一個類別, 代表攻擊鏈中的特定階段或威脅元件類型。 例如, 偵測到的威脅活動可能會分類為「側向移動」, 以表示活動企圖到達網路上的其他裝置, 且有可能在攻擊者取得初始 foothold 之後發生。 偵測到威脅元件時, 可能會被視為「惡意軟體」, 或更特別是「勒索軟體」、「認證竊取」或其他類型的惡意或不需要的軟體。

**裝置威脅類別**卡片會將提醒分散至這些類別。 您可以使用此資訊來識別威脅活動, 例如認證竊取時的嘗試, 這可能會比社交工程的嘗試更明顯的影響。 您也可以使用此程式來監視勒索軟體之類的潛在破壞性威脅。

![裝置威脅類別卡片](./media/security-docs/device-threat-categories.png)

### <a name="monitor-active-alerts"></a>監視使用中的警示

**裝置警示狀態**卡指出尚未解決且可能需要注意的警示數目。 您可以從這個卡片來查看 Microsoft Defender 安全中心入口網站上的詳細資訊。

![裝置警示狀態卡片](./media/security-docs/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a>監視已解析警示的分類

當您解決 Microsoft Defender ATP 警示時, 您的安全性員工可以指定警示是否已驗證為:

* 真正的警示, 識別實際的違規活動或威脅元件
* 偵測到正常活動的錯誤警示

**裝置警示分類**卡片會顯示您解決的警示是否已分類為 true 或 false 警示。 您可以從這個卡片來查看 Microsoft Defender 安全中心入口網站上的詳細資訊。

附注: 在某些情況下, 特定警示無法使用分類資訊。

![裝置警示分類卡片](./media/security-docs/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a>監視已解決之警示的決定

除了將警示設為 true 或 false 時, 您的安全性人員還可以提供判斷, 指出驗證警示時所找到之正常或惡意活動的類型。

**裝置警示決定**卡顯示針對每個警示所提供的決定, 特別是:

* **APT** – advanced persistent 威脅, 表示偵測到的活動或威脅元件是複雜破壞的一部分, 其設計是為了在受影響的網路中取得 foothold  
* **惡意**代碼-惡意檔案或程式碼
* **安全性人員**–安全性人員所執行的一般活動
* **安全性測試**–旨在模擬實際威脅並預期觸發安全性感應器及產生警示的活動或元件
* 不**需要的軟體**–應用程式和其他不被視為惡意的軟體, 但違反原則或可接受的使用標準
* **其他**–不屬於所提供類型的任何其他決定

您可以從這個卡片來查看 Microsoft Defender 安全中心的詳細資訊。

![裝置警示確定卡](./media/security-docs/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a>瞭解哪些裝置面臨風險

**裝置保護**顯示裝置的風險層級。 風險等級是以裝置上警示的類型和嚴重性之類的因素為基礎。

![裝置保護卡](./media/security-docs/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a>監視及報告 Intune 管理裝置的狀態

下列報告包含已在 Intune 中註冊裝置的資料。 Unenrolled 裝置中的資料不包含在內。 只有全域系統管理員才能查看這些卡片。

Intune 註冊的裝置資料包括:

* 裝置合規性
* 具有主動惡意程式碼的裝置
* 裝置上的惡意程式碼類型
* 裝置上的惡意程式碼
* 包含惡意軟體偵測的裝置
* 包含惡意軟體偵測的使用者

### <a name="monitor-device-compliance"></a>監視裝置合規性

**裝置合規性**顯示已在 Intune 中註冊的裝置, 符合設定原則。

![裝置合規性卡](./media/security-docs/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a>探索含有惡意軟體偵測的裝置

**裝置惡意軟體**偵測提供的 Intune 註冊裝置數目尚未因擱置的動作而未完全解決 (重新開機、完整掃描或手動使用者動作), 或修復動作未順利完成。

![裝置惡意軟體偵測卡](./media/security-docs/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a>瞭解偵測到的惡意程式碼類型

**裝置上的惡意程式碼類型**顯示在 Intune 上註冊的裝置上偵測到的不同類型惡意程式碼。 您可以在 Microsoft 365 安全中心中調查每種類型。

![裝置卡上的惡意程式碼類型](./media/security-docs/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a>瞭解在您的裝置上偵測到的特定惡意程式碼

**裝置上的惡意**代碼會提供在您的裝置上偵測到之特定惡意程式碼的清單。

![裝置卡上的惡意程式碼](./media/security-docs/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a>瞭解哪些裝置的惡意程式碼最多

**包含惡意**代碼的裝置會顯示哪些裝置的惡意軟體偵測最多。 在 Microsoft 365 安全性中心, 您可以調查惡意程式碼是使用中的, 誰會使用裝置, 以及其在 Intune 中的管理狀態。

![包含惡意軟體偵測卡的裝置](./media/security-docs/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a>瞭解哪些使用者具有最具惡意程式碼的裝置

**使用惡意軟體**偵測的使用者會顯示具有最多惡意程式碼偵測之裝置的使用者。 在 Microsoft 365 安全性中心, 您可以查看每個使用者所指派的裝置數目, 以及每個裝置和惡意軟體類型的詳細資訊。

![具有惡意軟體偵測卡的使用者](./media/security-docs/users-with-malware-detections.png)

## <a name="monitor-and-manage-asr-rule-deployment-and-detections"></a>監視及管理 ASR 規則部署和偵測

[攻擊面減少 (ASR) 規則](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard)可協助防止由 exploit 搜尋所使用的動作和應用程式, 以感染電腦。 這些規則會控制可執行檔的執行時間和執行方式。 例如, 您可以防止 JavaScript 或 VBScript 啟動下載的可執行檔、封鎖來自 Office 宏的 WIN32 API 呼叫, 或封鎖從 USB 磁片磁碟機執行的程式。

![攻擊面縮減卡](./media/security-docs/attack-surface-reduction-rules.png)

**攻擊面減少規則**卡片概述如何在您的裝置上部署規則。

卡片上的頂端列顯示在下列部署模式中的裝置總數:

* **封鎖模式**–至少有一個規則設定為封鎖偵測活動的裝置
* **核查模式**–未設定規則的裝置, 以封鎖偵測到的活動, 但至少有一個規則集來審核偵測到的活動  
* **Off** -關閉所有 ASR 規則的裝置

此卡片的下方部分會依規則顯示裝置上的設定。 每個條碼會指出設定為封鎖或審核偵測或已完全關閉規則的裝置數目。

### <a name="view-asr-detections"></a>查看 ASR 偵測

若要在您的網路中查看 ASR 規則偵測的詳細資訊, 請選取 [在**攻擊面減少規則**卡上**查看**偵測]。 將**** 會開啟 [詳細報告] 頁面中的 [偵測] 索引標籤。

![偵測索引標籤](./media/security-docs/detections-tab.png)

頁面頂端的圖表會顯示已封鎖或已審核的時間堆疊偵測偵測偵測。 底部的表格列出最近的偵測。 請在資料表上使用下列資訊, 瞭解偵測的本質:

* 偵測**到**檔案–檔案 (通常是腳本或檔, 其內容會觸發置疑的攻擊活動)
* **規則**名稱, 描述規則設計所要攔截的攻擊活動。 閱讀關於現有 ASR 規則的資訊
* **來源應用**程式–載入或執行內容觸發可疑攻擊活動的應用程式。 這可能是合法的應用程式, 例如網頁瀏覽器、Office 應用程式, 或像是 PowerShell 的系統工具。
* **Publisher** –發行來源應用程式的廠商

### <a name="review-device-asr-rule-settings"></a>檢查裝置 ASR 規則設定

在 [**攻擊面減少規則**報告] 頁面中, 移**** 至 [設定] 索引標籤, 以查看個別裝置的規則設定。 選取裝置以取得每個規則在封鎖模式、稽核模式或完全關閉時的詳細資訊。

![設定索引標籤](./media/security-docs/configuration-tab.png)

Microsoft Intune 提供您 ASR 規則的管理功能。 如果您想要更新您的設定, **** 請選取 [在] 索引標籤中的 [**設定裝置**], 以開啟 Intune 上的裝置管理。

### <a name="exclude-files-from-asr-rules"></a>從 ASR 規則排除檔案

Microsoft 365 security center[會收集您可能想](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/troubleshoot-asr#add-exclusions-for-a-false-positive)要因攻擊面減少規則而從偵測中排除的檔案名。 透過排除檔案, 您可以減少 false 肯定偵測, 並更自信地在區塊模式中部署攻擊面減少規則。

排除專案是在 Microsoft Intune 上管理, 但 Microsoft 365 security center 會提供分析工具, 以協助您瞭解檔案。 若要開始收集要排除的檔案, 請移至 [**攻擊面減少規則**報告] 頁面中的 [**新增排除**] 索引標籤。

>[!NOTE]  
>此工具會依據所有攻擊面減少規則來分析偵測, 但[只有部分規則支援排除](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules)。

![新增排除] 索引標籤](./media/security-docs/add-exclusions-tab.png)

此表格列出攻擊面減少規則所偵測到的所有檔案名。 您可以選取檔案, 以查看排除這些檔案的影響:

* 偵測數目減少
* 最少的裝置報告偵測

若要取得所選檔案的完整路徑以進行排除的清單, 請選取 [**取得排除路徑**]。

**從 Windows 本機安全性授權子系統 (lsass.exe) 偷竊**的 ASR 規則封鎖認證的記錄檔, 會將來源應用程式**lsass.exe**(如偵測到的檔案) 捕獲為標準的系統檔案。 因此, 產生的排除路徑清單會包含此檔案。 若要排除觸發此規則的檔案, 而不是**lsass.exe**, 請使用來源應用程式的路徑, 而不要使用偵測到的檔案。

若要尋找來源應用程式, 請針對此特定規則執行下列[高級搜尋查詢](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting)(由規則識別碼 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2):

```MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| where AdditionalFields contains "9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2"
| project InitiatingProcessFolderPath, InitiatingProcessFileName
```

#### <a name="check-files-for-exclusion"></a>檢查檔案是否有排除
從 ASR 排除檔案之前, 建議您檢查檔案, 以判斷它是否確實不是惡意的。

若要查看檔案, 請使用 Microsoft Defender 安全中心上的 [檔案[資訊] 頁面](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files)。 此頁面提供傳播資訊, 以及 VirusTotal 防病毒偵測比率。 您也可以使用頁面提交檔案進行深入分析。

若要在 Microsoft Defender 安全中心找到偵測到的檔案, 請使用下列高級搜尋查詢搜尋所有 ASR 偵測:

```MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| project FolderPath, FileName, SHA1, InitiatingProcessFolderPath, InitiatingProcessFileName, InitiatingProcessSHA1
```

在結果中使用**SHA1**或**InitiatingProcessSHA1** , 以使用 Microsoft Defender 安全中心的通用搜尋列來搜尋檔案。
