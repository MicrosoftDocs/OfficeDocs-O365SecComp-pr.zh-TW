---
title: 自動化的調查及回應 （空調） 與 Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/22/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 了解 Office 365 進階威脅防護中的自動化調查及回應功能。
ms.openlocfilehash: c6cfc03588e580382f673b2e9be8543bfcaf9ac1
ms.sourcegitcommit: f6073deec39a18581ed12abef18728417a52cdf4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/22/2019
ms.locfileid: "30747559"
---
# <a name="automated-investigation-and-response-air-with-office-365"></a>自動化的調查及回應 （空調） 與 Office 365

自動化調查及回應 （空調） （即將推出[Office 365 威脅調查](office-365-ti.md)及回應功能） 可讓您執行自動化的調查並修復已知存在於今天的威脅。 閱讀本篇文章以取得的空調，以及如何可幫助您的組織和安全性作業小組降低威脅，更有效率地概觀。 若要深入了解當空調中的其他功能會變成可用，請參閱[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)。

## <a name="alerts"></a>警示

[提醒](alert-policies.md#viewing-alerts)代表觸發程序的事件回應安全性作業小組工作流程。 排列優先順序的調查，同時確保沒有威脅 unaddressed 提醒右集是一項挑戰。 時以手動方式執行提醒到調查，安全性作業小組必須搜尋，並與實體 （例如： 內容、 裝置及使用者） 相互關聯威脅的風險。 這類任務及工作流程相當耗時且牽涉到多個工具和系統。 與空調、 調查及回應會自動完成到主要安全性和威脅管理警報自動觸發您安全性回應 playbooks。 

在下列的單一事件所產生的警示的空調年 4 月 2019年中的初始版本中的警示原則會自動調查。 

1. 偵測到有潛在的惡意 URL 點擊
2. 報告的釣魚程式 * 作為使用者的電子郵件
3. 電子郵件包含惡意程式碼傳遞 * 後移除
4. 電子郵件訊息包含傳遞 * 後移除的釣魚程式 Url

* 附註： 這些警示有已指派 」 提示資訊 」 嚴重性在安全性與合規性中心內的個別警示原則中關閉的電子郵件通知。 這些可以開啟透過警示原則設定。

若要檢視提醒，在 Office 365 安全性 & 合規性中心中，選擇 [**提醒** > **檢視警示**。 選取警示若要檢視其詳細資料，並從該處，使用的**檢視調查**連結移至對應的[調查](#investigation-graph)。

![連結至調查的提醒](media/air-alerts-page-details.png) 


## <a name="security-playbooks"></a>安全性 playbooks

安全性 playbooks 所面臨的自動化 Microsoft 威脅防護中的核心的後端原則。 常見的真實世界的安全性案例根據空調中提供安全性 playbooks。 當組織內就會觸發警示時，就會自動啟動安全性 playbook。 之後會觸發警示，自動執行相關聯的 playbook。 Playbook 執行和調查] 中，查看所有關聯的中繼資料 （包括電子郵件、 使用者、 主旨、 寄件者等等），並根據其所發現的錯誤、 建議的動作，以控制並降低可以採取貴組織的安全性小組威脅。 

您會看到與空調安全性 playbooks 專為今天處理最常見的威脅該組織圖像。 他們根據安全性作業和事件回應小組，包括協助防禦 Microsoft 和我們的客戶資產的輸入。

### <a name="security-playbooks-are-rolling-out-in-phases"></a>安全性 playbooks 已推出階段

航空的一部分，安全性 playbooks 已推出階段

- **階段 1 (年 4 月 2019)**: Playbooks 包含建議的安全性管理員檢閱和核准的動作。 

- **階段 2 (年 6 月 2019)**: 安全性系統管理員必須設定安全性 playbooks 不需要管理互動，自動採取動作的選項。

階段 1 將會包含下列 playbooks:
- 使用者報告的釣魚程式訊息
- URL 按一下 verdict 變更 
- 偵測到的惡意程式碼後傳遞 （惡意程式碼時能量光束）
- 釣魚程式偵測到後續傳遞 ZAP （Phish 時能量光束）
- 手動的電子郵件調查 （使用威脅總管）

數個其他 playbooks 計劃階段 2 中。

### <a name="playbooks-include-investigation-and-recommendations"></a>Playbooks 包括調查與建議

每個 playbook 包括： 
- 根和調查]， 
- 識別並對應其他潛在威脅，所採取的步驟和 
- 建議的威脅修復動作。

每個高階步驟包括提供深層、 詳細又詳盡回應威脅時所執行的許多子步驟。

## <a name="example-user-reported-phish-message"></a>範例： 使用者回報的釣魚程式訊息

當您組織中的使用者送出的電子郵件訊息，並向 Microsoft 報告所使用的[報告訊息增益集以進行 Outlook 或 Outlook Web Access](enable-the-report-message-add-in.md)。 這樣會觸發系統架構資訊性警示，自動啟動 [調查 playbook。

在根調查階段中，會評估的電子郵件的各個層面。 這些包括：
- 可能需有哪些類型的威脅它決定;
- 寄件者; 它
- 其中電子郵件寄件地 （傳送基礎結構）;
- 電子郵件的其他執行個體是否已傳遞或封鎖;
- 從我們分析師; 評估
- 是否任何已知的行銷活動; 相關聯的電子郵件
- 等等。

根調查完成後，playbook 會提供建議採取的動作清單。
  
接下來，數個威脅調查並狩獵步驟執行：

- 要搜尋其他電子郵件叢集中的類似電子郵件訊息。
- 其他平台，例如[Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)可共用接收的訊號。
- 決定在任何使用者是否按下透過任何可疑的電子郵件訊息中的連結。
- 檢查完成跨 Office 365 Exchange Online Protection ([EOP]) (eop/exchange-線上-保護-eop.md) 和 Office 365 進階 Therat 保護 ([ATP]) (office-365-atp.md) 若要查看是否有任何其他類似的訊息所報告的使用者。
- 若要查看是否使用者已遭洩露完成查核。 這項檢查跨[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)和[Azure Active Directory](https://docs.microsoft.com/azure/active-directory)，相互關聯任何相關的使用者活動異常運用訊號。 

狩獵階段風險和威脅指派給各種狩獵步驟。  

修復為 playbook 的最後一個階段。 在這個階段，採取補救步驟為止，根據 theinvestigation 和狩獵階段。  

## <a name="getting-started"></a>快速入門

若要為 Office 365 全域系統管理員、 安全性系統管理員或安全性讀取者存取您調查，移至 Office 365 安全性 & 合規性中心 ([https://protection.office.com](https://protection.office.com))，並登入。 接著執行下列其中一項作業：

- 在左導覽中，移至 [**威脅管理** > **調查**。

    或

- 威脅管理儀表板，請造訪 (在 [安全性 & 合規性中心，移至 [**威脅管理** > **儀表板**)。

![空調 widget](media/air-widgets.png)

[安全性儀表板](security-dashboard.md)的上方會出現您航空 widget。 選取 [開始] 小工具。

您也可能會存取 invesitgation 直接從的相關警示。

### <a name="automated-investigations"></a>自動化的調查

[自動化的調查] 頁面上顯示貴組織的調查和其目前狀態。

![空調主要調查頁面](media/air-maininvestigationpage.png) 
  
您可以：
- 直接前往調查 （選取**調查識別碼**）。
- 套用篩選。 選擇 [從**調查類型**、**時間範圍**、**狀態**或這些項目的組合。
- 將資料匯出至 CSV 檔案。

### <a name="investigation-graph"></a>調查圖

當您開啟特定調查時，您會看到 [調查 graph] 頁面。 此頁面會顯示所有不同的實體： 電子郵件、 使用者 （和其活動），以及已自動調查一部分警示所觸發的裝置。

![空調調查 graph 頁面](media/air-investigationgraphpage.png)

您可以：
- 取得目前調查的視覺化概觀。
- 檢視調查計時的摘要。
- 若要檢視該節點的詳細資料視覺效果中選取節點。
- 若要檢視該索引標籤的詳細資訊，在頂端選取] 索引標籤。

### <a name="alert-investigation"></a>警示調查

調查的 [**提醒**] 索引標籤中，您可以看到與調查有關的提醒。 詳細資料包含觸發調查警示和其他警示，例如風險登入，大量下載等的相互關聯的調查。 此頁面上，從安全性分析師也可以檢視其他詳細資料上獲取個別警示。

![產生提醒] 頁面上](media/air-investigationalertspage.png)

您可以：
- 取得目前的觸發警示和任何相關聯的警示的視覺化概觀。
- 若要開啟 [顯示完整警示的詳細資訊的飛出視窗頁面清單中，選取 [警示。

### <a name="email-investigation"></a>電子郵件調查

在調查的**電子郵件**] 索引標籤中，您可以看到識別為調查的一部分的所有電子郵件叢集。 

指定大量的電子郵件組織中的使用者傳送和接收的程序 
- 根據類似的屬性，從郵件標頭、 內文、 URL 和附件; 叢集的電子郵件 
- 從良好的電子郵件; 分隔惡意電子郵件和 
- 對惡意電子郵件採取的動作 

可能需要多個小時。 空調現在會自動執行此程序，儲存您的組織安全性小組時間和精力。 

做為範例，請考慮下列案例。 三個電子郵件的第一個叢集已被視為是釣魚程式。 類似郵件具有相同的 IP 和主旨的另一個叢集已找到，而且視為惡意，有些已識別為釣魚程式初始偵測期間。 

![空調電子郵件調查] 頁面](media/air-investigationemailpage.png)

您可以：
- 取得目前的叢集結果和威脅找到的視覺化概觀。
- 按一下 [叢集實體或威脅清單] 以開啟飛出視窗] 頁面上顯示的完整警示的詳細資料。

![空調調查的電子郵件與彈出式詳細資料](media/air-investigationemailpageflyoutdetails.png)

* 附註： 在電子郵件的內容，您可能會看到大量異常威脅表面調查的一部分。 磁碟區異常指出相較於舊版項調查事件時間前後的類似電子郵件中的特殊圖文集。 此特殊圖文集的特性類似的電子郵件流量 (例如主旨] 和 [寄件者的網域，本文相似性和寄件者 IP) 是一般的電子郵件行銷活動或攻擊的開始。 不過，大量和 spom 電子郵件行銷活動時間也共用這些特性。 磁碟區異常代表潛在威脅，並據此可能少數嚴重相較惡意程式碼或釣魚程式的威脅，用來識別的防毒引擎、 爆炸或惡意的信譽。

### <a name="user-investigation"></a>使用者調查

在 [**使用者**] 索引標籤中，您可以看到識別為調查的一部分的所有使用者。 

例如，在下列映像，空調已識別危害和異常根據新的收件匣規則所建立的指標。 調查的其他詳細資料 （辨識項） 可透過此危害的指標] 索引標籤內的詳細檢視，而且異常也可包含從[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)的異常偵測。

![空調調查的使用者] 頁面](media/air-investigationuserspage.png)

您可以：
- 取得已識別的使用者結果與風險找到的視覺化概觀。
- 選取使用者，若要開啟 [飛出視窗] 頁面上顯示的完整警示的詳細資料。

### <a name="machine-investigation"></a>機器調查

**機器**索引標籤上，您可以看到識別為調查的一部分的所有機器。 

![空調調查機器頁面](media/air-investigationmachinepage.png)

調查的一部分，空調相互關聯至裝置的電子郵件威脅。 例如，調查傳遞檔案之間的雜湊到[Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)調查。 這可讓您的使用者相關機器的自動化調查，而且可協助確保已解決威脅，同時在雲端和在裝置。 

您可以：
- 取得目前機器和威脅找到的視覺化概觀。
- 選取 [若要開啟 [檢視電腦，到 Windows Defender ATP 安全中心相關的[Windows Defender ATP 調查](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/automated-investigations-windows-defender-advanced-threat-protection)。

### <a name="entity-investigation"></a>實體調查

在 [**實體**] 索引標籤上，您可以看到識別為調查的一部分的所有機器。 

在這裡，您可以看到 investigated 的實體。 您可以檢視類型的實體，例如電子郵件、 叢集、 IP 位址、 使用者和更多詳細資料。 您也可以查看多少實體進行分析，且威脅，與每個相關聯。 

![空調調查實體] 頁面上](media/air-investigationentitiespage.png)

您可以：
- 取得調查實體和威脅找到的視覺化概觀。
- 選擇要開啟的飛出視窗頁面會顯示相關的實體詳細資料的實體。

![空調調查實體詳細資料](media/air-investigationsentitiespagedetails.png)

### <a name="playbook-log"></a>Playbook 記錄檔

在 [**記錄**] 索引標籤中，您可以看到調查期間所發生的所有 playbook 步驟。 記錄檔擷取由 Office 365 自動調查功能完成空調一部分的所有動作的完整詳細目錄。 它本身、 描述及的實際工期提供清楚的所有所採取的步驟，包括巨集指令檢視從開始到完成。 

![空調調查記錄頁面](media/air-investigationlogpage.png)

您可以：
- 取得看到所採取的 playbook 步驟的視覺化概觀。
- 將結果匯出至 CSV 檔案。
- 篩選的檢視。

### <a name="recommended-actions"></a>建議的動作

在 [**動作**] 索引標籤中，您可以看到建議的修復後調查已完成的所有 playbook 動作。 

動作擷取 Microsoft 建議您採取調查結尾處的步驟。 您可以藉由選取一或多個動作採取以下修復動作。 按一下 [**核准**可讓修復以開始。 （適當的權限將會需要。 例如，安全性讀取者可以檢視動作，但不是核准。）  

![空調調查動作] 頁面上](media/air-investigationactionspage.png)

您可以：
- 取得 playbook 建議動作的視覺化概觀。
- 選取單一動作或多個動作。
- 核准或拒絕建議的動作與註解。
- 將結果匯出至 CSV 檔案。
- 篩選的檢視。

## <a name="how-to-get-air"></a>如何取得航空

目前，Office 365 空調是在預覽中。 Office 365 航空將包含在下列訂閱：

- Microsoft 365 企業版 E5
- Office 365 企業版 E5
- Microsoft 威脅防護
- Office 365 進階的威脅保護計劃 2

若要深入了解可用的功能，請造訪[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)。
