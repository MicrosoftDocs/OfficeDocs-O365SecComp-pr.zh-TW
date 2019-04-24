---
title: 敏感資訊的 office 365 郵件加密原則
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/31/2019
ROBOTS: NOINDEX, NOFOLLOW
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 摘要： Office 365 郵件加密原則適用於立即可用的敏感資訊類型。
ms.openlocfilehash: 99cb7a9f94c9cf4036c11b74a5208ddf0e819ceb
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32261261"
---
# <a name="office-365-message-encryption-policy-for-sensitive-information"></a>敏感資訊的 office 365 郵件加密原則

更新 (1/30/19): 年 10 月 2018 年，我們合作以了解是否我們可以簡化保護自動加密，以根據特定的敏感資訊類型的敏感電子郵件客戶一小部分範例。 我們根據正從這個範例的意見反應，決定要展開 2018 年 12 月中的 [在更多樣化的設定檔中的租用戶。 之後通訊下一步推行選取租用戶，我們聆聽您的意見反應，並決定較複雜的環境具有客戶想要更謹慎執行規則，並且因此，我們會調整我們計劃。

如果您的組織所選推行開始 2019 年 1 月 15 日，我們會不推出的自動原則。 相反地，我們提供本文中的指示在如何在您完成推行自己。 繼續閱讀以了解如何。

||
|:-----|
|本文屬於較大的一連串的 Office 365 郵件加密的相關文章。 本文適用於系統管理員和 ITPros。 如果您只是正在尋找的資訊傳送或接收的加密的訊息，請參閱在[Office 365 郵件加密 (OME)](ome.md)中的文章的清單，並找出最適合您需求的文章。 |
||

## <a name="how-to-create-the-sensitive-information-type-policy-for-your-tenant"></a>如何建立您的租用戶的敏感資訊類型原則

若要建立的敏感資訊類型原則，您可以使用 [Exchange 郵件流程規則] 或 [Office 365 資料外洩防護 (DLP)。 若要建立 Exchange 郵件流程規則，您可以使用 Exchange 系統管理中心 (EAC) 或 PowerShell。

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a>若要建立原則在 EAC 中使用郵件流程規則

登入 Exchange 系統管理中心 (EAC)，並移至 [**郵件流程** > **規則**。 那里，建立適用於 Office 365 郵件加密根據例如目前狀態的特定關鍵字或郵件或附件中的敏感資訊類型的條件規則。

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a>若要建立原則藉由使用 PowerShell 中的郵件流程規則

使用 Office 365 組織中具有全域系統管理員權限的工作或學校帳戶，請啟動 Windows PowerShell 工作階段，並連線至 Exchange Online。 如需相關指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。 使用 Set-irmconfiguration 和新增 TransporRule 指令程式來建立原則。

### <a name="example-mail-flow-rule-created-with-powershell"></a>使用 PowerShell 建立範例郵件流程規則

執行下列 PowerShell 命令建立 Exchange 郵件流程規則會自動加密移與組織外部的電子郵件*加密唯讀*原則如果電子郵件或其附件包含下列機密資訊類型：

- 阿拉巴馬州銀行路由號碼
- 信用卡號碼
- 藥物執法機構 (DEA) 編號
- 美國 / 英國 護照號碼
- 美國銀行帳戶號碼
- 美國個別 Taxpayer 識別號碼 (ITIN)
- 美國社會安全號碼 (SSN)

```powershell
Set-IRMConfiguration -DecryptAttachmentsForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

## <a name="how-recipients-access-attachments"></a>收件者存取附件的方式

一旦加密郵件時，收件者將不受限制存取附件之後他們存取，並開啟其加密的電子郵件。

## <a name="to-prepare-for-this-change"></a>若要準備進行這項變更

若要更新任何適用的使用者文件和訓練資料準備，這項變更您組織中的人員。 視您的使用者與共用這些 Office 365 郵件加密的資源：

- [傳送、 檢視和回覆加密郵件的電腦版 Outlook 中](https://support.office.com/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [Office 365 基本版影片： Office 郵件加密](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a>稽核記錄中檢視這些變更

這項活動會稽核並可供 Office 365 系統管理員。 這項操作是 'New-transportrule' 和程式碼片段範例稽核項目，從 [稽核記錄中搜尋的安全性 & 合規性中心的低於：

|     |
| --- |
| *{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 」、 「 RecordType 」: 1，「 ResultStatus":"True"，"UserKey 」: 「 Microsoft 操作員 」、 「UserType 」: 3，「 版本 」: 1 日的 「 工作負載 」: 「 Exchange 」、 「 ClientIP 「: 」 123.456.147.68:17584 」、 「 ObjectId 「: 」 」、 「 UserId 」: 「 Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters 」: {「 名稱 」: 「 組織 」、 「 值 」:"123456 221 d-12346"{「 名稱 」: 「 ApplyRightsProtectionTemplate 」、 「 值 」: 「 加密 」}，{「 名稱 」: 「 名稱 」、 「 值 」: 」 （超出方塊規則） 的輸出機密電子郵件加密 」}，{「 名稱 」: 」MessageContainsDataClassifications 」...]等。* |
| |

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a>若要停用或自訂的敏感資訊類型原則

一旦您已經建立 Exchange 郵件流程規則，您可以[停用或編輯規則](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule)移至 [**郵件流程** > **規則**在 Exchange 系統管理中心 (EAC) 和停用的規則 「*加密外寄機密電子郵件 （超出方塊規則）*」。
