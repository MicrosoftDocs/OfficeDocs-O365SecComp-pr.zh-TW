---
title: Microsoft 365 SIEM server 整合
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.date: 10/29/2018
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- SIEM
- M365-security-compliance
description: 摘要： 閱讀本篇文章以取得 Microsoft 365 SIEM server 整合的概觀。
ms.openlocfilehash: 56ac1b244bc7bfc62bd6edb097a733e8477baa26
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215653"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a>SIEM server 與 Microsoft 365 服務及應用程式的整合

## <a name="overview"></a>概觀

如果您的組織使用的安全性資訊及事件管理 (SIEM) 的伺服器，或如果打算推出取得 SIEM 伺服器，您可能會想要知道如何會將包含 Office 365 企業版的 Microsoft 365 與整合。您是否需要 SIEM 伺服器取決於許多因素，例如貴組織的安全性需求。Microsoft 365 外部提供各種安全性功能 ；但是，如果組織有內容和應用程式在內部部署和雲端 （如所示的混合式雲端部署的大小寫） 中，您可能會考慮新增額外的保護 SIEM 伺服器。或者，如果您的組織必須符合的特別嚴苛安全性需求，您可能會考慮將 SIEM 伺服器新增至您的環境。

## <a name="siem-server-integration-microsoft-365"></a>SIEM 伺服器整合 Microsoft 365

SIEM 伺服器可以接收資料從各種不同的 Microsoft 365 服務及應用程式。下表列出數個 Microsoft 365 服務及應用程式以及 SIEM server 的輸入和位置移至 [深入了解 SIEM 伺服器整合。 

| Microsoft 365 Service 或應用程式 | SIEM 伺服器輸入 | 若要深入了解的資源 |
| --- | --- | --- |
| [Office 365 進階威脅防護](office-365-atp.md) <br/>   或   <br/>[Office 365 威脅情報](office-365-ti.md) | 稽核記錄 | [與 Office 365 威脅智慧及進階威脅保護 SIEM 整合](siem-integration-with-office-365-ti.md) |
| [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | 記錄檔的整合 | [Microsoft 雲端應用程式安全性 SIEM 整合](https://docs.microsoft.com/cloud-app-security/siem) |
| [Office 365 雲端 App 安全性](office-365-cas-overview.md) | 記錄檔的整合 | [將 SIEM 伺服器與 Office 365 雲端 App 安全性整合](integrate-your-siem-server-with-office-365-cas.md) |
| [Windows Defender 進階威脅防護](https://docs.microsoft.com/windows/security/threat-protection/) | 記錄檔的整合 | [提取提醒 SIEM 工具](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-siem-windows-defender-advanced-threat-protection) |
| [Azure 安全性中心](https://docs.microsoft.com/azure/security-center/security-center-intro)（threat 保護和威脅偵測） | 警報 | [Azure 安全性資料匯出至 SIEM-管線組態-預覽](https://docs.microsoft.com/azure/security-center/security-center-export-data-to-siem) |
| [Azure Active Directory 識別保護](https://docs.microsoft.com/azure/active-directory/identity-protection/overview) | 稽核記錄 | [整合 Azure Active Directory 稽核記錄](https://docs.microsoft.com/azure/security/security-azure-log-integration-ad) |
| [Azure 進階的威脅分析](https://docs.microsoft.com/azure/security/azure-threat-detection) | 記錄檔的整合 | [ATA SIEM 記錄參考 （英文)](https://docs.microsoft.com/advanced-threat-analytics/cef-format-sa) |

## <a name="audit-logging-must-be-turned-on"></a>必須開啟稽核記錄

請務必再設定 SIEM 伺服器整合稽核記錄已開啟。 

- 針對 SharePoint Online OneDrive for Business 和 Azure Active Directory、[稽核記錄在安全性 & 規範中心已開啟](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off)。

- 針對 Exchange Online，[稽核記錄已開啟 Windows powershell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing)。
 
## <a name="see-also"></a>另請參閱

[雲端採用和混合式解決方案](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
[雲端採用測試實驗室指南 (TLG)](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)


