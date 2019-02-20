---
title: 與 Office 365 威脅智慧及進階威脅保護 SIEM 整合
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
description: 整合您的組織 SIEM server 與 Office 365 威脅智慧及進階威脅保護的 Office 365 活動管理 api。
ms.openlocfilehash: 854f763b72dfac1a5dc1442b1d9d123ed5439257
ms.sourcegitcommit: 8679937354c1d8870ecd41519a59d2d7468c23c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2019
ms.locfileid: "30087242"
---
# <a name="siem-integration-with-office-365-threat-intelligence-and-advanced-threat-protection"></a>與 Office 365 威脅智慧及進階威脅保護 SIEM 整合

如果貴組織要使用安全性事件及事件管理 (SIEM) 伺服器，您可以使用 SIEM server 整合 Office 365 威脅智慧及進階威脅保護。SIEM 整合可讓您檢視的資訊，例如偵測到的 Office 365 進階保護和威脅智慧您 SIEM server 報告中的惡意程式碼。若要設定 SIEM 整合，您可以使用[Office 365 活動管理 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)。 

Office 365 活動管理 API 從您組織的 Office 365 和 Azure Active Directory 活動記錄檔擷取使用者、 管理、 系統及原則動作和事件的相關資訊。[Office 365 進階威脅保護和威脅智慧結構描述](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-intelligence-schema)搭配威脅智慧及/或進階威脅防護，因此如果您的組織有但不是威脅智慧 （反之亦然），進階威脅保護，您可以仍然使用該相同的 API 來進行 SIEM server 的整合。 

SIEM 伺服器或其他類似系統應輪詢 access 偵測事件**audit.general**工作量。若要了解，請參閱[開始使用 Office 365 管理 api （英文）](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)。 

> [!IMPORTANT]
> 您必須是 Office 365 全域管理員或已指派給安全性 & 規範中心來設定與 Office 365 進階威脅保護 SIEM 整合安全性管理員角色。<br/>稽核記錄必須針對 Office 365 環境開啟。若要取得與此說明，請參閱[開啟 Office 365 稽核記錄搜尋開啟或關閉](turn-audit-log-search-on-or-off.md)。

## <a name="related-topics"></a>相關主題

[Office 365 威脅情報](office-365-ti.md)

[Office 365 進階威脅防護](office-365-atp.md)

[智慧報表和 Office 365 安全性前瞻&amp;規範中心](reports-and-insights-in-security-and-compliance.md)
  
[Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)
  

