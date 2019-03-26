---
title: 使用中的安全性威脅總管&amp;合規性中心
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/21/2019
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
ms.openlocfilehash: 202898873bb9611c747aed335d295c749c7cd0fa
ms.sourcegitcommit: a56128c7be5d59e976851c27301031e19fa1997d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/21/2019
ms.locfileid: "30732256"
---
# <a name="use-threat-explorer-in-the-security-amp-compliance-center"></a>使用中的安全性威脅總管&amp;合規性中心

如果您的組織有[Office 365 進階威脅防護計劃 2](office-365-ti.md)，而且您具有必要權限，您可以使用威脅總管來識別和分析潛在威脅。 例如，您可以識別並刪除惡意電子郵件已傳遞，或請參閱 Office 365 安全性功能所攔截惡意程式碼。 威脅總管 （也稱為 Explorer）] 是功能強大的接近即時的工具，以協助調查及回應安全性威脅的安全性作業小組&amp;合規性中心。
  
![移至威脅管理，\>總管](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
若要使用檔案總管中，安全性&amp;合規性中心，移至**威脅管理** \> **總管**。

> [!IMPORTANT]
> Office 365 威脅情報現在是 Office 365 進階威脅防護計劃 2，以及其他威脅保護功能。 若要深入了解，請參閱[Office 365 進階威脅防護方案和價格](https://products.office.com/exchange/advance-threat-protection)和[Office 365 進階威脅防護服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。
      
## <a name="explorer-overview"></a>Explorer 概觀

如果您的組織有[Office 365 威脅調查及回應功能](office-365-ti.md)（隨附於 ATP 計劃 2），而且您具有必要權限，您可以使用威脅總管 （也稱為總管） 來識別和分析潛在威脅。 (安全性&amp;合規性中心，移至**威脅管理** \> **總管**。)

![移至威脅管理，\>總管](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

本文說明您可以運用檔案總管的一些事項 （有許多更多的可能性）：

- [請參閱電子郵件中偵測到惡意程式碼何種](#see-malware-detected-in-email-by-technology)，和威脅防護技術 (反惡意程式碼防護，ATP 安全附件，等等。)

- [檢視關於網路釣魚連結 (Url) 的資料](#view-data-about-phishing-urls-and-click-verdict)，且哪些按一下 [結果 (Url 封鎖、 允許，或造訪儘管警告)

- [檢閱電子郵件訊息，已回報為垃圾郵件，不是垃圾郵件或網路釣魚](#review-email-messages-reported-by-users)，並識別任何趨勢 (例如 a 大於郵件報告為釣魚程式的一般數目) 

## <a name="see-malware-detected-in-email-by-technology"></a>請參閱技術電子郵件中偵測到的惡意程式碼

假設您想要查看電子郵件，並在 Office 365 技術偵測到的惡意程式碼。 若要這麼做，請使用檔案總管的[電子郵件 > 惡意程式碼](threat-explorer-views.md#email--malware)檢視。

1. 在 Office 365 安全性 & 合規性中心 ([https://protection.office.com](https://protection.office.com))，選擇 [**威脅管理** > **總管**。
2. 在 [**檢視**] 功能表中，選擇 [**電子郵件** > **惡意程式碼**。<br/>![瀏覽器的 [檢視] 功能表](media/ExplorerViewEmailMalwareMenu.png)<br/>
3. 按一下 [**寄件者**，，然後選擇 [**基本** > **偵測技術**。<br/>偵測技術現在可做為報表的篩選。<br/>![惡意程式碼偵測技術](media/ExplorerEmailMalwareDetectionTech.png)<br/> 
4. 選取一個選項，，，然後按一下 [重新整理] 按鈕，以套用該篩選器。<br/>![選取的偵測技術](media/ExplorerEmailMalwareDetectionTechATP.png)<br/> 

若要顯示在電子郵件，使用您所選取的技術選項中偵測到的結果惡意程式碼會重新整理報表。 從這裡開始，您可以進行進一步分析。

## <a name="view-data-about-phishing-urls-and-click-verdict"></a>檢視網路釣魚 Url 相關資料，並按一下 verdict

假設您想要查看網路釣魚電子郵件，包括允許、 封鎖，並覆寫的 Url 清單中嘗試透過 Url。 若要這麼做，請使用檔案總管的[電子郵件 > 釣魚程式](threat-explorer-views.md#email--phish)檢視。

1. 在 Office 365 安全性 & 合規性中心 ([https://protection.office.com](https://protection.office.com))，選擇 [**威脅管理** > **總管**。
2. 在 [**檢視**] 功能表中，選擇 [**電子郵件** > **釣魚程式**。<br/>![瀏覽器的 [檢視] 功能表](media/ExplorerViewEmailPhishMenu.png)<br/>
3. 按一下 [**寄件者**，，然後選擇 [ **Url** > **按一下 verdict**。
4. 選取一或多個選項，例如**封鎖**及**封鎖覆寫**]，然後按一下 [**重新整理**] 按鈕，以套用該篩選器。<br/>![Url 並按一下 [結果](media/ThreatExplorerEmailPhishClickVerdictOptions.png)<br/>

報表會重新整理以顯示已封鎖 （或 [瀏覽儘管警告） 的電子郵件中偵測到的網路釣魚 Url 以及電子郵件傳遞狀態。 從這裡開始，您可以進行進一步分析。 例如，下方圖表，您可以看到貴組織的電子郵件遭到封鎖的上層 Url。 

![已封鎖的檔案總管 Url](media/ExplorerPhishClickVerdictURLs.png) 

選取要檢視的詳細的資訊的 URL。

## <a name="review-email-messages-reported-by-users"></a>檢閱報告的使用者的電子郵件訊息

假設您想要查看您組織中的使用者會回報的電子郵件為垃圾郵件、 不是垃圾郵件或網路釣魚使用[報告訊息增益集以進行 Outlook 和 outlook 網頁版](enable-the-report-message-add-in.md)。 若要這麼做，請使用[電子郵件 > 使用者回報](threat-explorer-views.md#email--user-reported)檔案總管檢視。

1. 在 Office 365 安全性 & 合規性中心 ([https://protection.office.com](https://protection.office.com))，選擇 [**威脅管理** > **總管**。
2. 在 [**檢視**] 功能表中，選擇 [**電子郵件** > **使用者報告**。<br/>![瀏覽器的 [檢視] 功能表](media/ExplorerViewMenuEmailUserReported.png)<br/>
3. 按一下 [**寄件者**，，然後選擇 [**基本** > **報表類型**。
4. 選取一個選項，例如**釣魚程式**，，然後按一下 [**重新整理**] 按鈕。 <br/>![使用者報告的釣魚程式](media/EmailUserReportedReportType.png)<br/> 

報表會重新整理以顯示您組織中的人員已回報為網路釣魚嘗試的電子郵件的相關資料。 您可以使用此資訊來進一步進行分析，並如有必要，調整您的[ATP 防網路釣魚原則](set-up-anti-phishing-policies.md)。

## <a name="theres-more"></a>沒有更多 ！

除了本文中所述的三個案例，您有許多報告案例隨附於瀏覽器。 以下是幾個例子：

- [尋找並調查傳送的惡意電子郵件](investigate-malicious-email-that-was-delivered.md)

- [檢視 SharePoint Online、 OneDrive 及 Microsoft Teams 中偵測到的惡意檔案](malicious-files-detected-in-spo-odb-or-teams.md)

- [在威脅總管] 中，取得檢視的概觀](threat-explorer-views.md)

## <a name="how-to-get-explorer"></a>如何取得總管

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

若要深入了解，請參閱下列資源：

- [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)

- [Exchange Online 中的功能權限](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
  
## <a name="related-topics"></a>相關主題

- [自動化的調查及回應 （空調）](automated-investigation-response-office.md)

- [威脅總管檢視](threat-explorer-views.md)

- [檢視 Office 365 進階威脅防護報告](view-reports-for-atp.md)
