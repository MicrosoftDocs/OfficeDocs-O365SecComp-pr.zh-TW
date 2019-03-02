---
title: Microsoft 365 的 SIEM 伺服器整合
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.date: 10/29/2018
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: 摘要： 閱讀本篇文章以取得 Microsoft 365 的 SIEM 伺服器整合的概觀。
ms.openlocfilehash: 3f906fb082ec2c1a026940d2b5701a3d1fbec393
ms.sourcegitcommit: 7adfd8eda038cf25449bdf3df78b5e2fcc1999e7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/01/2019
ms.locfileid: "30357494"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a>Microsoft 365 服務和應用程式的 SIEM 伺服器整合

## <a name="overview"></a>概觀

如果您的組織使用的安全性資訊和事件管理 (SIEM) 伺服器，或如果您計劃要推出取得 SIEM 伺服器，您可能想知道如何，將您的 Microsoft 365，包括 Office 365 企業版與整合。您是否需要 SIEM 伺服器取決於許多因素，例如貴組織的安全性需求。Microsoft 365 提供各種不同的安全性功能;不過，如果您的組織有內容和應用程式內部部署和雲端 （如混合式雲端部署的大小寫） 中，您可能會考慮新增額外的保護 SIEM 伺服器。或者，如果您的組織有必須符合的特別嚴格的安全性需求，您可以考慮將 SIEM 伺服器新增至您的環境。

## <a name="siem-server-integration-microsoft-365"></a>SIEM 伺服器整合 Microsoft 365

SIEM 伺服器可以接收來自各種不同的 Microsoft 365 服務和應用程式的資料。下表列出數個 Microsoft 365 服務和應用程式以及 SIEM 伺服器的輸入和移至深入了解 SIEM 伺服器整合的位置。 

| Microsoft 365 服務或應用程式 | SIEM 伺服器輸入 | 若要了解更多的資源 |
| --- | --- | --- |
| [Office 365 進階威脅防護](office-365-atp.md) <br/>   或   <br/>[Office 365 威脅情報](office-365-ti.md) | 稽核記錄 | [Office 365 威脅情報和進階威脅防護的 SIEM 整合](siem-integration-with-office-365-ti.md) |
| [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | 記錄整合 | [Microsoft Cloud App Security 的 SIEM 整合](https://docs.microsoft.com/cloud-app-security/siem) |
| [Office 365 雲端 App 安全性](office-365-cas-overview.md) | 記錄整合 | [將 SIEM 伺服器與 Office 365 雲端 App 安全性整合](integrate-your-siem-server-with-office-365-cas.md) |
| [Windows Defender 進階威脅防護](https://docs.microsoft.com/windows/security/threat-protection/) | 記錄整合 | [提取提醒您 SIEM 工具](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-siem-windows-defender-advanced-threat-protection) |
| [Azure 資訊安全中心](https://docs.microsoft.com/azure/security-center/security-center-intro)（威脅保護和威脅偵測） | 警示 | [Azure 安全性資料匯出至 SIEM-管線組態-預覽](https://docs.microsoft.com/azure/security-center/security-center-export-data-to-siem) |
| [Azure Active Directory 身分識別保護](https://docs.microsoft.com/azure/active-directory/identity-protection/overview) | 稽核記錄 | [整合 Azure Active Directory 稽核記錄](https://docs.microsoft.com/azure/security/security-azure-log-integration-ad) |
| [Azure 的進階的威脅分析](https://docs.microsoft.com/azure/security/azure-threat-detection) | 記錄整合 | [ATA SIEM 記錄檔參考](https://docs.microsoft.com/advanced-threat-analytics/cef-format-sa) |

## <a name="audit-logging-must-be-turned-on"></a>必須先開啟稽核記錄

請確定您在設定 SIEM 伺服器整合之前，開啟稽核記錄。 

- OneDrive for Business 和 Azure Active Directory[稽核記錄安全性 & 合規性中心中開啟](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off)SharePoint online，版本。

- 針對 Exchange Online、[使用 Windows PowerShell 開啟稽核記錄](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing)。
 
## <a name="see-also"></a>另請參閱

[雲端採用和混合式解決方案](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
[雲端採用測試實驗室指南 (TLG)](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)


