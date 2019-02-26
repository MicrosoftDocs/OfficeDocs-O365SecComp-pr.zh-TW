---
title: 安全性儀表板概觀 （英文)
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/07/2019
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fe0b9b8f-faa9-44ff-8095-4d1b2f507b74
ms.collection:
- M365-security-compliance
description: 使用新的安全性儀表板檢閱 Office 365 威脅保護狀態及檢視以及對安全性提醒。
ms.openlocfilehash: 7a4535a0cc02a6ad046cadb99b8ebb94df5fd9fe
ms.sourcegitcommit: 1c73c2f83703af0a30a5b0633db00d8e0e6b39b5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/25/2019
ms.locfileid: "30241885"
---
# <a name="security-dashboard"></a>安全性儀表板

## <a name="overview"></a>概觀

[安全性&amp;規範中心](go-to-the-securitycompliance-center.md)可讓您管理資料保護與規範的組織。假設您具備必要的權限，安全性儀表板可讓您檢閱您威脅的保護狀態，以及檢視與對安全性提醒。 
  
觀賞影片，以取得概觀 （英文）、，然後閱讀本篇文章以深入了解。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/3540b1f8-62d2-47fa-a07d-d7ad76f55b0f?autoplay=false]
  
根據組織的 Office 365 訂閱的包括、 安全性儀表板包含數個 widget，例如 Threat Management 摘要、 威脅保護狀態、 全域每週的威脅偵測、 惡意程式碼、 及詳細資訊，如下所述下列各節。
  
若要檢視中的 [安全性儀表板[Office 365 安全性&amp;規範中心](go-to-the-securitycompliance-center.md)、 移至 [ **Threat management** \> **儀表板**。
  
> [!NOTE]
> 您必須是 Office 365 全域管理員、 安全性系統管理員或安全性讀者檢視安全性儀表板。某些 widget 需要檢視的其他權限。若要深入了解，請參閱[Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。 
  
## <a name="threat-management-summary"></a>Threat Management 摘要

Threat Management 摘要 widget 會告訴您一眼如何組織已保護免受威脅過去七個 （7） 天。

![安全性儀表板-Threat Management 摘要 widget](media/SecDash-ThreatMgmtSummary.png)

您會看見 Threat Management 摘要中的資訊取決於您的訂閱所包含的項目。下表說明包含 Office 365 企業版 E3 和 Office 365 企業版 E5 知道的資訊。


|Office 365 Enterprise E3  |Office 365 企業版 E5  |
|---------|---------|
|封鎖的惡意程式碼郵件<br/>封鎖網路釣魚郵件<br>使用者所報告的郵件<br><br><br><br> |封鎖的惡意程式碼郵件<br>封鎖網路釣魚郵件<br>使用者所報告的郵件<br>零時差惡意程式碼封鎖<br>偵測到的進階網路釣魚郵件<br>惡意 Url 封鎖 |

若要檢視或存取 Threat Management 摘要 widget，您必須具備檢視進階威脅保護報告的權限。若要深入了解，請參閱[檢視 ATP 報表所需的權限吗？](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports)。 

## <a name="threat-protection-status"></a>威脅保護狀態

威脅保護狀態 widget 顯示威脅保護效益與 phish 和惡意程式碼的趨勢和詳細資料檢視。 

![威脅保護狀態 widget](media/tpswidget.png)

詳細資料取決於是否在 Office 365 訂閱包括[Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP) 使用或不[Office 365 進階威脅保護](office-365-atp.md)(ATP)。


|您的訂閱若包含...] |您會看見下列詳細資料 |
|---------|---------|
|EOP，但不是 Office 365 ATP     |偵測到並已封鎖透過 EOP 的惡意電子郵件<br> 請參閱[威脅保護狀態報表 (EOP)](view-email-security-reports.md#threat-protection-status-report)。| |
|Office 365 ATP |惡意的內容及惡意電子郵件偵測和封鎖的 EOP 與 Office 365 ATP<br>彙總的數唯一的電子郵件與反惡意程式碼引擎、[零小時自動清除](zero-hour-auto-purge.md)，與 ATP 功能 （包括[安全連結](atp-safe-links.md)、[安全的附件](atp-safe-attachments.md)及[ATP 反網路釣魚](atp-anti-phishing.md)） 所封鎖的惡意內容的詳細資訊。<br>請參閱[威脅保護狀態報表 (ATP)](view-reports-for-atp.md#threat-protection-status-report)。 | 

若要檢視或存取威脅保護狀態 widget，您必須具備檢視進階威脅保護報告的權限。若要深入了解，請參閱[檢視 ATP 報表所需的權限吗？](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports)。 

## <a name="global-weekly-threat-detections"></a>通用每週的威脅偵測
 
通用每週的威脅偵測 widget 顯示多少威脅所電子郵件訊息中偵測到過去七個 （7） 天。

![通用每週的威脅偵測 widget](media/globalweeklythreatdetections.png)

評量的計算方式如下表所述：

|計量單位  |計算方式  |
|---------|---------|
|掃描的郵件 |掃描電子郵件數目乘以收件者數目 |
|停止的威脅  |電子郵件會被識別為包含惡意程式碼收件者數目乘以數目 |
|封鎖[ATP](office-365-atp.md) |封鎖的收件者數目乘以 ATP 的電子郵件數目 |
|移除傳送後 |[零小時自動清除](zero-hour-auto-purge.md)收件者數目乘以由此指令程式移除的訊息數目 |

## <a name="malware"></a>惡意程式碼

惡意程式碼 widget 顯示過去 7 （7） 天惡意程式碼趨勢及惡意程式碼系列類型的詳細資料。

![惡意程式碼趨勢和系列類型](media/malwarewidgetatpe5.png)
 
## <a name="insights"></a>深入資訊

前瞻不只表面您應該檢閱的重要事項，他們也包含要考量的建議及動作。 

![智慧前瞻](media/smartinsights.png)

例如，您可能會看到網路釣魚電子郵件會被傳遞因為某些使用者是否已停用其垃圾郵件] 選項。若要深入了解觀點的運作方式，請參閱[報告與 Office 365 安全性前瞻&amp;規範中心](reports-and-insights-in-security-and-compliance.md)。
  
## <a name="threat-intelligence"></a>威脅智慧

如果您的組織訂閱包括[威脅智慧功能](office-365-ti.md)，安全性儀表板具有**威脅智慧**] 區段中包含進階的工具。貴組織的安全性小組可以使用本節中的資訊來了解新行銷活動、 調查威脅及管理事件。 
  
![威脅智慧可協助您了解攻擊的目標設為您的組織](media/threatintelwidget.png)
  
  
## <a name="trends"></a>趨勢

安全性儀表板的底端接近會摘要說明為貴組織的電子郵件流程趨勢**趨勢**] 區段。報告提供電子郵件分類為 「 垃圾郵件、 惡意程式碼、 網路釣魚嘗試及良好的電子郵件的相關資訊。按一下 [並排顯示在報告中檢視的詳細的資訊。 
  
![[趨勢] 區段中彙總組織的電子郵件流程趨勢](media/trends.png)
  
與如果貴組織的 Office 365 訂閱包括[威脅智慧功能](office-365-ti.md)，您也必須**最近 threat management 提醒**報表本節可讓您檢視和採取動作的安全性小組高優先順序安全性提醒。 

若要檢視或存取已傳送與接收電子郵件 widget，您必須具備檢視進階威脅保護報告的權限。若要深入了解，請參閱[檢視 ATP 報表所需的權限吗？](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports)。 

若要檢視或存取最近 Threat Management 提醒 widget，您必須具備檢視提醒的權限。若要深入了解，請參閱[檢視提醒所需的 RBAC 權限](alert-policies.md#rbac-permissions-required-to-view-alerts)。
  
## <a name="related-topics"></a>相關主題

[在 [安全性] 中檢視電子郵件安全性報表&amp;規範中心](view-email-security-reports.md)
  
[Office 365 進階威脅保護的檢視報告](view-reports-for-atp.md)
  
[Office 365 進階威脅防護](office-365-atp.md)
  
[Office 365 威脅情報](office-365-ti.md)
  

