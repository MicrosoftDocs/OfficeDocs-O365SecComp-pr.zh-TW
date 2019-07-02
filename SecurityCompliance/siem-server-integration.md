---
title: SIEM server 與 Microsoft 365 的整合
ms.author: deniseb
author: denisebmsft
manager: laurawi
audience: ITPro
ms.topic: article
ms.date: 06/17/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: '摘要: 閱讀本文以取得與 Microsoft 365 的 SIEM server 整合的總覽。'
ms.openlocfilehash: 9138cbc395b90f50fa60bf545066c17cf26d7edf
ms.sourcegitcommit: f2798d46acfbd56314e809cd3fe0350be807e420
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2019
ms.locfileid: "35014762"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a>SIEM server 與 Microsoft 365 服務和應用程式的整合

## <a name="overview"></a>概觀

如果您的組織使用安全性資訊和事件管理 (SIEM) 伺服器, 或是您打算很快取得 SIEM 伺服器, 您可能會想知道該如何與 Microsoft 365 (包括 Office 365 E5) 整合。 您是否需要 SIEM 伺服器取決於許多因素, 例如組織的安全性需求。 Microsoft 365 提供各種安全性功能;不過, 如果您的組織在內部部署和雲端中有內容和應用程式 (如同混合雲端部署的情況), 您可能會考慮新增 SIEM 伺服器以進行額外保護。 或者, 如果您的組織擁有特別嚴格的安全性需求, 您可能會考慮將 SIEM 伺服器新增至您的環境。

## <a name="siem-server-integration-microsoft-365"></a>SIEM server integration Microsoft 365

SIEM 伺服器可以接收各種 Microsoft 365 服務和應用程式的資料。 下表列出數個 Microsoft 365 服務和應用程式, 以及 SIEM 伺服器的輸入, 以及深入瞭解 SIEM server 整合的資訊。 

| Microsoft 365 服務或應用程式 | SIEM 伺服器輸入 | 要深入瞭解的資源 |
| --- | --- | --- |
| [Office 365 進階威脅防護](office-365-atp.md) <br/>或<br/>[Office 365 威脅情報](office-365-ti.md) | 稽核記錄 | [SIEM 與 Office 365 高級威脅防護的整合](siem-integration-with-office-365-ti.md) |
| [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | 記錄整合 | [SIEM 與 Microsoft Cloud App Security 的整合](https://docs.microsoft.com/cloud-app-security/siem) |
| [Microsoft 威脅防護](https://docs.microsoft.com/windows/security/threat-protection/) | 記錄整合 | [將提醒提取到您的 SIEM 工具](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem) |
| [Azure 安全中心](https://docs.microsoft.com/azure/security-center/security-center-intro)(威脅防護和威脅偵測) | 警示 | [Azure 安全性資料匯出至 SIEM-管線設定-預覽](https://docs.microsoft.com/azure/security-center/security-center-export-data-to-siem) |
|[Azure Advanced 威脅分析](https://docs.microsoft.com/azure/security/azure-threat-detection) | Azure 監視器 | [發表使用 Azure 監視器整合 SIEM 工具](https://azure.microsoft.com/blog/use-azure-monitor-to-integrate-with-siem-tools) |
|[Azure Active Directory 身分識別保護](https://docs.microsoft.com/azure/active-directory/identity-protection/overview) |記錄整合 |[將 Microsoft Graph 安全性 API 警示與 SIEM 整合](https://docs.microsoft.com/graph/security-siemintegration) |


## <a name="audit-logging-must-be-turned-on"></a>必須開啟審核記錄

在設定 SIEM server integration 之前, 請確定已開啟 audit 記錄。 

- 若為 SharePoint Online、商務用 OneDrive 和 Azure Active Directory, 則[會在安全性 & 規範中心內開啟 audit 記錄](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off)。

- 針對 Exchange Online,[會使用 Windows PowerShell 開啟審核記錄](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing)功能。
 
## <a name="see-also"></a>另請參閱

[雲端採用和混合式解決方案](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
[雲端採用測試實驗室指南 (TLG)](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)


