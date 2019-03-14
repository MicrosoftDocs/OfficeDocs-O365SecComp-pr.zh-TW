---
title: 將 SIEM 伺服器與 Office 365 雲端 App 安全性整合
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: dd6d2417-49c4-4de6-9294-67fdabbf8532
description: 您可以使用 Office 365 雲端 App 安全性整合 SIEM 伺服器。 閱讀本篇文章以取得其運作方式，以及如何設定它的概觀。
ms.openlocfilehash: 82b5e0e6467bd42acba3c40d67e4e0363a7e0f72
ms.sourcegitcommit: 4abcc03497478abf1ae7fc84792f44360d8e59c1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/12/2019
ms.locfileid: "30548583"
---
# <a name="integrate-your-siem-server-with-office-365-cloud-app-security"></a>將 SIEM 伺服器與 Office 365 雲端 App 安全性整合
  
|評估 * *\>**|規劃 * *\>**|部署 * *\>**|使用率 * * *|
|:-----|:-----|:-----|:-----|
|[啟動評估](office-365-cas-overview.md) <br/> |[開始規劃](get-ready-for-office-365-cas.md) <br/> |您在此處 ！  <br/> [下一步](utilization-activities-for-ocas.md) <br/> |[開始使用](utilization-activities-for-ocas.md) <br/> |
   
## <a name="overview-and-prerequisites"></a>概觀與必要條件

您可以將[Office 365 雲端 App 安全性](get-ready-for-office-365-cas.md)整合與您的安全性資訊和事件管理 (SIEM) 伺服器，以啟用集中式監視的提醒。 這是特別有用的組織使用雲端服務，而且在內部伺服器應用程式。 您可以將整合到 SIEM 伺服器從 Office 365 雲端 App 安全性提取警示和活動 SIEM 伺服器。 與 SIEM 伺服器整合可讓您更妥善地保護您的 Office 365 應用程式同時維護您的一般安全性工作流程，自動化特定安全性程序和雲端式之間相互關聯的安全性小組與內部事件。  
  
當您第一次將 SIEM 伺服器整合與 Office 365 雲端 App 安全性時，從過去兩天的提醒轉寄給 SIEM 伺服器上，為所有警示從 then 上 （根據您選取任何篩選條件）。 此外，如果您停用此功能一段，當您重新啟用，它會將轉寄過去兩天的提醒，然後所有警示從然後起。

### <a name="siem-integration-architecture"></a>SIEM 整合架構

SIEM 代理程式是設定在貴組織的網路。 SIEM 代理程式時部署和設定，提取所設定的資料類型 （警示） 使用 Office 365 雲端 App 安全性 RESTful Api。 透過連接埠 443 上的加密 HTTPS 通道然後傳送流量。
  
當 SIEM 代理程式會擷取資料，從 Office 365 雲端 App 安全性時，它會將 Syslog 郵件傳送至本機 SIEM 伺服器使用 （TCP 或 UDP 與自訂連接埠） 的安裝期間所提供的網路組態中。

![SIEM 及雲端 App 安全性架構](media/siem-architecture.png)

### <a name="supported-siem-servers"></a>支援的 SIEM 伺服器

Office 365 雲端 App 安全性目前支援下列的 SIEM 伺服器：
- 微焦點討論 ArcSight
- 一般 CEF

### <a name="prerequisites"></a>必要條件

- 您必須是全域系統管理員或安全性系統管理員可執行本文所述的工作。 請參閱[中的 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)

- 您必須擁有[Office 365 雲端 App 安全性啟用](turn-on-office-365-cas.md)您的組織。

- 必須開啟[稽核記錄](turn-audit-log-search-on-or-off.md)，Office 365

- 您必須符合下列需求才能設定 SIEM 伺服器整合的標準伺服器：
    - 作業系統： Windows 或 Linux （這可以是虛擬機器）
    - CPU: 2
    - 磁碟空間： 20 GB
    - RAM: 2 GB
    - 安裝[Oracle Java 8](http://www.oracle.com/technetwork/java/javase/downloads/index.html)
    - 設定[網路需求](https://docs.microsoft.com/cloud-app-security/network-requirements)所述的防火牆

- 您必須具有 「**遠端 syslog 主機**」 和 「 **Syslot 連接埠號碼**的相關詳細資料。 網路系統管理員或安全性系統管理員應該能夠協助您找出該資訊。 

- 若要下載[JAR 檔案](https://go.microsoft.com/fwlink/?linkid=838596)需要整合 SIEM 伺服器，您必須同意[軟體授權](https://go.microsoft.com/fwlink/?linkid=862491)條款。
 
## <a name="step-1-set-it-up-a-siem-agent-in-office-365-cloud-app-security"></a>步驟 1： 設定 Office 365 雲端 App 安全性中的 SIEM 代理程式

1. 移至 Cloud App Security 入口網站 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com))，並登入。
  
2. 按一下 [**設定** \> **安全性延伸模組**]，然後選擇 [SIEM 代理程式。<br/>
![選擇 [設定 > 安全性延伸模組](media/Settings-SecurityExtensions.png)

3. 選擇 [**新增 SIEM 代理程式**。<br/>![選擇 [新增 SIEM 代理程式。](media/SIEMAgents.png)
    
4. 選擇 [**啟動精靈**]。<br/>![取得協助，或啟動精靈](media/HelpOrWizard.png) 
    
5. 在**一般**步驟中，指定名稱，然後**選取 [SIEM 格式**並設定任何**進階設定]** 相關的格式。 然後選擇 [**下一步**。<br/>![指定的名稱和類型](media/ChooseAgentTypeAndName.png)
    
6. 在 [**遠端 Syslog** ] 步驟中，指定 IP 位址] 或 [**遠端 syslog 主機**」 和 「 **Syslog 連接埠號碼**的主機名稱。 為遠端 Syslog 通訊協定，選取 [TCP] 或 [UDP。 （您可以使用您的網路系統管理員或安全性系統管理員以取得這些詳細資料，如果您未安裝它們。）然後選擇 [**下一步**。<br/>![指定遠端 Syslog 詳細資料](media/ArcSightS1Syslog.png)
  
7. 在 [**資料類型**] 步驟中，執行下列其中一項，然後按一下 [**下一步**：
    - 保留預設設定的**所有提醒**<br/>或
    - 按一下 [**所有警示**，，，然後選擇**特定篩選器**。 定義篩選器以選取您想要傳送給 SIEM 伺服器的提醒的類型。
<br/>![在精靈的資料類型步驟](media/ArcSightS1ExportOptions.png)
  
8. 在 [恭喜] 畫面中，將複製的權杖，並將其儲存供之後參考。<br/>![SIEM 建立代理程式畫面](media/SIEMAgentFinished.png) 

> [!IMPORTANT]
> 此時，您已設定好 Office 365 雲端 App 安全性中的 SIEM 代理程式，但尚未完成您 SIEM 伺服器整合。 請繼續下一個步驟以繼續執行您 SIEM 伺服器整合。

按一下 [關閉]，並保留精靈中，在 [安全性 extensions 畫面上之後，您可以看到您在資料表中新增的 SIEM 代理程式。 它會顯示**建立**] 狀態，直到它稍後連線。

![建立的 SIEM 代理程式](media/SIEMAgentCreated.png)
    
## <a name="step-2-download-a-jar-file-and-run-it-on-your-siem-server"></a>步驟 2： 下載糖檔案，並在 SIEM 伺服器上執行

1. 下載[Microsoft 雲端 App 安全性 SIEM 代理程式](https://go.microsoft.com/fwlink/?linkid=838596)，並將解壓縮的資料夾。 （您必須同意[軟體授權合約](https://go.microsoft.com/fwlink/?linkid=862491)才能繼續執行。） 
    
2. .Jar 檔案解壓縮 zip 的資料夾，並在 SIEM 伺服器上執行它。
    
3. 之後執行檔案，請執行下列命令： 命令：<br/>
  ```
  java -jar mcas-siemagent-0.87.20-signed.jar [--logsDirectory DIRNAME] [--proxy ADDRESS[:PORT]] --token TOKEN
  ```
### <a name="important-notes"></a>重要注意事項

- 檔案名稱可能有所不同 SIEM 代理程式的版本。 

- 我們建議您在伺服器安裝期間執行 SIEM 伺服器上的糖檔案。

    - **Windows**： 執行當做排程工作，並確認其設定**不論使用者登入與否均執行**工作，並清除**停止工作，只有在執行時間超過**] 選項。

    - **Linux**： 新增執行的命令**&** 至`rc.local`檔案。 <br/>範例：<br/> 
    ```
    java -jar mcas-siemagent-0.87.20-signed.jar [--logsDirectory DIRNAME] [--proxy ADDRESS[:PORT]] --token TOKEN &
    ```

- 參數在方括是選擇性的而且只有相關應該使用。 使用下列變數：

    - **DIRNAME**是您想要用於本機代理程式偵錯記錄檔之目錄的路徑。

    - **地址 [: 連接埠]** 是伺服器用來連線到網際網路的連接埠與 proxy 伺服器位址。

    - **語彙基元**是您在第一個程序中複製的 SIEM 代理程式語彙基元。

    - 若要取得協助，請輸入`-h`。 
  
## <a name="step-3-validate-that-the-siem-agent-is-working"></a>步驟 3： 驗證 SIEM 代理程式正常運作

1. 請確定 SIEM 代理程式在 Office 365 雲端 App 安全性入口網站中的狀態不會顯示為**連線錯誤**或**中斷連線**，而且有無代理程式的通知。<br/>例如，我們可以看到 SIEM 伺服器連線：<br/>![SIEM 伺服器連線](media/siem-connected.png)<br/>然後，在這裡，我們可以看到 SIEM 伺服器已中斷連線：<br/>![未連接的 SIEM 伺服器](media/siem-not-connected.png) 
  
2. 在 Syslog/SIEM 伺服器，請確定您看到提醒已從 Office 365 雲端 App 安全性抵達。
  
## <a name="what-the-logfiles-look-like"></a>記錄檔的外觀

以下是可能會傳送至 SIEM 伺服器提醒的記錄檔範例：

```
2017-07-15T20:42:30.531Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|myPolicy|3|externalId=596a7e360c204203a335a3fb start=1500151350531 end=1500151350531 msg=Activity policy ''myPolicy'' was triggered by ''admin@box-contoso.com'' suser=admin@box-contoso.com destinationServiceName=Box cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596a7e360c204203a335a3fb cs2Label=uniqueServiceAppIds cs2=APPID_BOX cs3Label=relatedAudits cs3=1500151288183_acc891bf-33e1-424b-a021-0d4370789660 cs4Label=policyIDs cs4=59f0ab82f797fa0681e9b1c7

2017-07-16T09:36:26.550Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy|3|externalId=596b339b0c204203a33a51ae start=1500197786550 end=1500197786550 msg=Activity policy ''test-activity-policy'' was triggered by ''user@contoso.com'' suser=user@contoso.com destinationServiceName=Salesforce cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b339b0c204203a33a51ae cs2Label=uniqueServiceAppIds cs2=APPID_SALESFORCE cs3Label=relatedAudits cs3=1500197720691_b7f6317c-b8de-476a-bc8f-dfa570e00349 cs4Label=policyIDs cs4=

2017-07-16T09:17:03.361Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy3|3|externalId=596b2fd70c204203a33a3eeb start=1500196623361 end=1500196623361 msg=Activity policy ''test-activity-policy3'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Office 365 cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b2fd70c204203a33a3eeb cs2Label=uniqueServiceAppIds cs2=APPID_O365 cs3Label=relatedAudits cs3=1500196549157_a0e01f8a-e29a-43ae-8599-783c1c11597d cs4Label=policyIDs cs4=

2017-07-16T09:17:15.426Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy|3|externalId=596b2fd70c204203a33a3eec start=1500196635426 end=1500196635426 msg=Activity policy ''test-activity-policy'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Microsoft Office 365 admin center cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b2fd70c204203a33a3eec cs2Label=uniqueServiceAppIds cs2=APPID_O365_PORTAL cs3Label=relatedAudits cs3=1500196557398_3e102b20-d9fa-4f66-b550-8c7a403bb4d8 cs4Label=policyIDs cs4=59f0ab35f797fa9811e9b1c7

2017-07-16T09:17:46.290Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy4|3|externalId=596b30200c204203a33a4765 start=1500196666290 end=1500196666290 msg=Activity policy ''test-activity-policy4'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Microsoft Exchange Online cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b30200c204203a33a4765 cs2Label=uniqueServiceAppIds cs2=APPID_OUTLOOK cs3Label=relatedAudits cs3=1500196587034_a8673602-7e95-46d6-a1fe-c156c4709c5d cs4Label=policyIDs cs4=

2017-07-16T09:41:04.369Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy2|3|externalId=596b34b10c204203a33a5240 start=1500198064369 end=1500198064369 msg=Activity policy ''test-activity-policy2'' was triggered by ''user2@test15-adallom.com'' suser=user2@test15-adallom.com destinationServiceName=Google cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b34b10c204203a33a5240 cs2Label=uniqueServiceAppIds cs2=APPID_33626 cs3Label=relatedAudits cs3=1500197996117_fd71f265-1e46-4f04-b372-2e32ec874cd3 cs4Label=policyIDs cs4=
```

而以下是另一個範例中，這次 CEF 格式：


|CEF 欄位名稱  | 說明  |
|---------|---------|
|啟動     | 警示的時間戳記        |
|結束     | 警示的時間戳記        |
|rt     | 警示的時間戳記        |
|msg     | 在 Office 365 雲端 App 安全性入口網站中所示警示描述        |
|suser     | 警示的主體使用者        |
|destinationServiceName     | 源自應用程式，例如 Office 365、 SharePoint 或 OneDrive 的警示        |
|csLabel     | 而有所不同 （標籤會有不同的意義）。 一般而言，標籤是自我闡明的例如 targetObjects。        |
|cs     | 對應到標籤 （例如依標籤範例警示的目標使用者） 的資訊        |

## <a name="additional-tasks-as-needed"></a>其他工作 （視需要）

您已設定 SIEM 伺服器，且已整合與 Office 365 雲端 App 安全性後，您可能需要重新產生的語彙基元，編輯 SIEM 代理程式，或刪除的 SIEM 代理程式。 下列各節說明如何執行這些工作。

### <a name="regenerate-a-token"></a>重新產生的語彙基元

如果您遺失您的權杖，您就可以將一個重新產生。 

1. 在 Office 365 雲端 App 安全性入口網站 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com))，選擇 [**設定** > **安全性延伸模組**。

2. 在表格中，找出 SIEM 代理程式的列。 

3. 按一下省略符號，然後再選擇 [**重新產生語彙基元**。<br/>![重新產生的語彙基元 SIEM 代理程式按一下省略符號](media/04de368a-b88e-4a9c-a830-58025cb98db6.png)
  
### <a name="edit-a-siem-agent"></a>編輯 SIEM 代理程式

1. 在 Office 365 雲端 App 安全性入口網站 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com))，選擇 [**設定** > **安全性延伸模組**。

2. SIEM 代理程式，找出資料列。 

3. 按一下省略符號，然後再選擇 [**編輯**。 （如果您編輯 SIEM 代理程式時，您不需要重新執行.jar 檔案; 它會自動更新）。 <br/>![若要編輯您的 SIEM 代理程式，選擇省略符號，，，然後選擇 [編輯]。](media/96d0b362-3e0c-4dff-b2b4-d7af5b1bfb91.png)
  
### <a name="delete-a-siem-agent"></a>刪除 SIEM 代理程式

1. 在 Office 365 雲端 App 安全性入口網站 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com))，選擇 [**設定** > **安全性延伸模組**。

2. SIEM 代理程式，找出資料列。 

3. 按一下省略符號，然後再選擇 [**刪除**。<br/>![若要刪除的 SIEM 代理程式，選擇省略符號，，然後選擇 [刪除]。](media/540b5bdf-5574-4ecc-a7b0-92a499a387d7.png)

  
## <a name="next-steps"></a>後續步驟

- [推出 Office 365 雲端 App 安全性後的使用活動](utilization-activities-for-ocas.md)
    
- [檢閱並採取相應動作提醒](review-office-365-cas-alerts.md)
    
- [您的 IP 位址，以簡化管理群組](group-your-ip-addresses-in-ocas.md)
    

