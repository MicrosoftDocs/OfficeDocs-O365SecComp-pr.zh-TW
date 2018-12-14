---
title: 新的 Office 365 郵件加密原則敏感資訊
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 12/13/2018
ROBOTS: NOINDEX, NOFOLLOW
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 摘要： 新 Office 365 郵件加密的原則機密資訊。
ms.openlocfilehash: 180050d1bf9303f6d29bc126e66ac53211c2fb34
ms.sourcegitcommit: 3aae959ea1ac5ef61a9942c681d334831e6b6038
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/14/2018
ms.locfileid: "27271089"
---
# <a name="new-office-365-message-encryption-policy-for-sensitive-information"></a>新的 Office 365 郵件加密原則敏感資訊

我們會建立新的自動原則將會套用至所有電子郵件包含敏感資訊及的寄往組織外部的 Office 365 郵件加密的 Office 365 租用戶中。這個新的 Exchange 郵件流程規則將會自動建立 Office 365 租用戶中使預設會保護您的組織。

## <a name="how-will-this-work"></a>如何將這項工作？

您的組織會收到通知在 Office 365 郵件內通知您將在您的租用戶中建立此自動的原則所在的日期。會提供您至少 30 天的通知，您還必須加入確認程序擴充的選項。您可能想可能會選擇退出分析的藍本是如果您有機密類型已掃描的第 3 廠商資料外洩防護解決方案。

## <a name="new-policy-details"></a>新原則的詳細資訊

將會自動加密不必與組織外部的電子郵件在組織中建立新的 Exchange 郵件流程規則*只加密*如果它們包含以下敏感資訊類型的原則：

- 阿拉巴馬州路由號碼
- 信用卡號
- 藥物強制執行機構 (DEA) 編號
- 美國 / 英國護照號碼
- 美國銀行帳戶號碼
- 美國個別納稅人身分識別碼 (ITIN)
- 美國社會安全編號 (SSN)

> [!Note]
> 完全機密類型依您組織的地區設定而異和會傳達給訊息中心通知中。

## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>我需要如何準備，這項變更？

您沒有更新或修改這個新的變更之前的任何現有 Office 365 組態設定。不過，您可能要更新任何適用的使用者文件及準備，這項變更組織中的人員的訓練教材。

## <a name="how-will-this-change-be-represented-in-the-audit-log"></a>此變更會表示在稽核記錄檔的方式？

此活動您可以稽核和客戶使用。 作業是 'New-transportrule' 和程式碼片段的稽核記錄檔中搜尋的安全性與規範中心範例稽核項目是下方：

|     |
| --- |
| *{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345"，"RecordType": 1、"ResultStatus":"True"、"UserKey":"Microsoft 運算子"，"UserType": 3、 [版本]： 1、"工作量":"Exchange"、"ClientIP":"123.456.147.68:17584"，"ObjectId"：""，"UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"的組織"，"值":"123456 221 d-12346"{"Name":"ApplyRightsProtectionTemplate"，"值":"加密"}，{"Name":"Name"，"值":"加密外寄機密電子郵件 （不在] 方塊中的規則）"}，{"Name":"MessageContainsDataClassifications"等。*
 |

## <a name="how-do-i-opt-out"></a>如何我選擇延展？

如果您想要選擇加入延展這項變更，請遵循下列步驟：

1. 以全域管理員角色的使用者身分連線至[Exchange Online PowerShell](https://aka.ms/exopowershell) 。
2.  在驗證後執行下列程式碼：

    ```
    Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
    ```

## <a name="how-do-i-disable-the-automatic-policy"></a>如何停用自動原則？

如果您沒有選擇出這項變更與 Exchange 郵件規則已建立，您可以[停用規則](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule)移至 [**郵件流程** > **規則**中 Exchange admin center (EAC) 並停用"*輸出加密的規則機密的電子郵件 （不在] 方塊中的規則）*"。
