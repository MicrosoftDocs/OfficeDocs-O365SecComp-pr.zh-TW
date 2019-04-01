---
title: 使用中的安全性威脅總管&amp;合規性中心
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/31/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
description: 了解 （也稱為威脅總管） 的瀏覽器安全性&amp;合規性中心。
ms.openlocfilehash: c782e5962164b7d35947befe526c20f7dc0943d5
ms.sourcegitcommit: 691370682825a7601bd4b77d0a8c4b51ed15682f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2019
ms.locfileid: "31014012"
---
# <a name="use-threat-explorer-in-the-security-amp-compliance-center"></a>使用中的安全性威脅總管&amp;合規性中心

如果您的組織有[Office 365 進階威脅防護計劃 2](office-365-ti.md) (ATP)，而且您具有必要權限，您可以使用威脅總管 （也稱為總管） 來識別和分析潛在威脅。 (使用檔案總管中，安全性&amp;合規性中心，移至**威脅管理** \> **總管**。)

![移至威脅管理，\>總管](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

瀏覽器是功能強大，接近即時的工具，以協助調查及回應安全性威脅的安全性作業小組&amp;合規性中心。 以下是一些您可以執行的事項：
- [請參閱 Office 365 安全性功能所偵測到的惡意程式碼](#see-malware-detected-in-email-by-technology)
- [檢視網路釣魚 Url 相關資料，並按一下 verdict](#view-data-about-phishing-urls-and-click-verdict)
- [從瀏覽器中檢視啟動自動的調查及回應程序](#start-automated-investigation-and-response)
- ...[以及更多](#more-ways-to-use-explorer)！

## <a name="see-malware-detected-in-email-by-technology"></a>請參閱技術電子郵件中偵測到的惡意程式碼

假設您想要查看電子郵件，並在 Office 365 技術偵測到的惡意程式碼。 若要這麼做，請使用檔案總管的[電子郵件 > 惡意程式碼](threat-explorer-views.md#email--malware)檢視。

1. 在安全性 & 合規性中心 ([https://protection.office.com](https://protection.office.com))，選擇 [**威脅管理** > **總管**。
2. 在 [**檢視**] 功能表中，選擇 [**電子郵件** > **惡意程式碼**。<br/>![瀏覽器的 [檢視] 功能表](media/ExplorerViewEmailMalwareMenu.png)<br/>
3. 按一下 [**寄件者**，，然後選擇 [**基本** > **偵測技術**。<br/>偵測技術現在可做為報表的篩選。<br/>![惡意程式碼偵測技術](media/ExplorerEmailMalwareDetectionTech.png)<br/> 
4. 選取一個選項，，，然後按一下 [重新整理] 按鈕，以套用該篩選器。<br/>![選取的偵測技術](media/ExplorerEmailMalwareDetectionTechATP.png)<br/> 

若要顯示在電子郵件，使用您所選取的技術選項中偵測到的結果惡意程式碼會重新整理報表。 從這裡開始，您可以進行進一步分析。

## <a name="view-data-about-phishing-urls-and-click-verdict"></a>檢視網路釣魚 Url 相關資料，並按一下 verdict

假設您想要查看網路釣魚電子郵件，包括允許、 封鎖，並覆寫的 Url 清單中嘗試透過 Url。  識別已按下的 Url 需要[ATP 安全連結](atp-safe-links.md)。 (請確定您已設定並套用至您的使用者，按一下 [時間的[ATP 安全連結原則](set-up-atp-safe-links-policies.md)保護和記錄按一下由 ATP 安全連結的結果。)若要檢閱郵件及釣魚程式訊息中的按 Url 中的釣魚程式 Url，請使用檔案總管的[電子郵件 > 釣魚程式](threat-explorer-views.md#email--phish)檢視。

1. 在安全性 & 合規性中心 ([https://protection.office.com](https://protection.office.com))，選擇 [**威脅管理** > **總管**。
2. 在 [**檢視**] 功能表中，選擇 [**電子郵件** > **釣魚程式**。<br/>![瀏覽器的 [檢視] 功能表](media/ExplorerViewEmailPhishMenu.png)<br/>
3. 按一下 [**寄件者**，，然後選擇 [ **Url** > **按一下 verdict**。
4. 選取一或多個選項，例如**封鎖**及**封鎖覆寫**]，然後按一下 [**重新整理**] 按鈕，以套用該篩選器。<br/>![Url 並按一下 [結果](media/ThreatExplorerEmailPhishClickVerdictOptions.png)<br/>

報表會重新整理以顯示兩個不同的 URL 資料表上的 [URL] 索引標籤下：
1. **Top Url**是 Url 包含在郵件中您有篩選向下，和電子郵件傳遞巨集指令會計算每個 URL。 在釣魚程式的電子郵件檢視中，這份清單通常會包含合法的 Url。 攻擊者嘗試以協助他們傳遞，其郵件中包括混合的良好且不正確的 Url，但會進行更有趣的使用者按一下惡意連結。 總數的電子郵件計數排序表格的 Url (請注意： 此資料行不會顯示以簡化檢視)。
2. **按一下頂端**是安全連結進行三重包裝 Url 所按下，排序總計按一下的計數 （此資料行也不會顯示以簡化檢視）。 依欄的總計數指出安全連結按一下 verdict 計數的每個已按選的 URL。 在釣魚程式的電子郵件檢視中，這些會更常是可疑或惡意連結，但可能包含位於釣魚程式的郵件，即會發生的全新 Url。 這裡不會顯示 URL 按包裝的連結。

兩個 Url 資料表網路釣魚電子郵件中顯示上方的 Url 所傳遞狀態，以及他們顯示 URL 點選已封鎖 （或瀏覽儘管警告） 連結，讓您可以了解哪些可能會損毀使用者收到且使用者互動。 從這裡開始，您可以進行進一步分析。 比方說，下方圖表，您可以看到已封鎖您組織的環境中的電子郵件中的頂端 Url。 

![已封鎖的檔案總管 Url](media/ExplorerPhishClickVerdictURLs.png) 

選取要檢視的詳細的資訊的 URL。 請注意，在 URL 彈出式視窗] 對話方塊中，以顯示您環境中的 URL 的曝光度的完整檢視會移除在電子郵件篩選。 這可讓您篩選下電子郵件中檔案總管和擔心，找出潛在威脅，然後展開 （透過 URL 的詳細資料] 對話方塊） 環境中的 URL 公開您了解，而不必新增 URL 篩選器以特定 Url總管檢視本身。

## <a name="review-email-messages-reported-by-users"></a>檢閱報告的使用者的電子郵件訊息

假設您想要查看您組織中的使用者會回報的電子郵件為垃圾郵件、 不是垃圾郵件或網路釣魚使用[報告訊息增益集以進行 Outlook 和 outlook 網頁版](enable-the-report-message-add-in.md)。 若要這麼做，請使用[電子郵件 > 使用者回報](threat-explorer-views.md#email--user-reported)檔案總管檢視。

1. 在安全性 & 合規性中心 ([https://protection.office.com](https://protection.office.com))，選擇 [**威脅管理** > **總管**。
2. 在 [**檢視**] 功能表中，選擇 [**電子郵件** > **使用者報告**。<br/>![瀏覽器的 [檢視] 功能表](media/ExplorerViewMenuEmailUserReported.png)<br/>
3. 按一下 [**寄件者**，，然後選擇 [**基本** > **報表類型**。
4. 選取一個選項，例如**釣魚程式**，，然後按一下 [**重新整理**] 按鈕。 <br/>![使用者報告的釣魚程式](media/EmailUserReportedReportType.png)<br/> 

報表會重新整理以顯示您組織中的人員已回報為網路釣魚嘗試的電子郵件的相關資料。 您可以使用此資訊來進一步進行分析，並如有必要，調整您的[ATP 防網路釣魚原則](set-up-anti-phishing-policies.md)。

## <a name="start-automated-investigation-and-response"></a>啟動自動化的調查及回應

（新 ！）[自動化調查及回應](automated-investigation-response-office.md)，最近新增至 ATP 計劃 2，可以儲存您的安全性作業小組很多時間和精力中調查，並減輕網路攻擊。 除了設定可以觸發安全性 playbook 的提醒，您可以從瀏覽器中檢視啟動自動的調查及回應程序。 

如需這的詳細資訊，請參閱[範例： 安全性系統管理員會觸發從威脅總管調查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。

## <a name="more-ways-to-use-explorer"></a>若要使用檔案總管的更多方法

除了本文中所述的案例，您有許多詳細報告選項隨附於瀏覽器。 
- [尋找並調查傳送的惡意電子郵件](investigate-malicious-email-that-was-delivered.md)
- [檢視 SharePoint Online、 OneDrive 及 Microsoft Teams 中偵測到的惡意檔案](malicious-files-detected-in-spo-odb-or-teams.md)
- [在威脅總管] 中，取得檢視的概觀](threat-explorer-views.md)

## <a name="required-licenses-and-permissions"></a>所需的授權和權限

Explorer 隨附於[Office 365 進階威脅防護計劃 2](office-365-ti.md)。 

若要檢視並使用檔案總管，您必須具有適當的權限，例如授與安全性系統管理員或安全性讀取者。 

- Security&amp;合規性中心，您必須有一個指派的下列角色：
    - 組織管理
    - 安全性系統管理員 (這可以在 Azure Active Directory 系統管理中心中指派 ([https://aad.portal.azure.com](https://aad.portal.azure.com)))
    - 安全性讀取者

- 若是 Exchange Online 中，您必須安裝下列其中一個在 Exchange 系統管理中心中指派下列角色 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) 或使用 PowerShell cmdlet (請參閱[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):
    - 組織管理
    - 僅檢視組織管理
    - 僅檢視收件者角色
    - 合規性管理

若要深入了解角色和權限，請參閱下列資源：

- [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)

- [Exchange Online 中的功能權限](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
  
