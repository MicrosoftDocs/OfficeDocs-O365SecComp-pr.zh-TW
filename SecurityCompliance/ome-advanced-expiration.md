---
title: 為由 Office 365 進階郵件加密所加密的電子郵件設定到期日
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
description: 在 Office 365 郵件加密 (OME) 頂端有 Office 365 高級郵件加密功能時, 您可以透過自訂的署名範本來設定電子郵件的到期日, 以擴充您的電子郵件安全性。
ms.openlocfilehash: 7c4ad1fb4a91bd62569edc5db9042dfbd2dbd9fe
ms.sourcegitcommit: b9d8a43cb3afcdc8820bc9470c5707eff8fc6616
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/11/2019
ms.locfileid: "34852757"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a>為由 Office 365 進階郵件加密所加密的電子郵件設定到期日

Office 365 高級郵件加密可在特定訂閱中的 Office 365 郵件加密上使用。 [Microsoft 365 企業版](https://www.microsoft.com/microsoft-365/enterprise/home)e5、Office 365 企業版 E5 和 Office 365 教育版 A5 包含先進的郵件加密。 如果您的組織有 Office 365 訂閱, 但未包含 Office 365 的高級郵件加密, 您可以使用 advanced 合規性 SKU 的 E5 符合性, 以附加元件形式購買高級郵件加密。

您可以在電子郵件上使用郵件到期, 您的使用者傳送給使用 OME 入口網站來存取加密電子郵件的外部收件者。 您可以利用在 Windows Powershell 中指定到期日的自訂署名範本, 讓收件者使用 OME 入口網站來查看和回復組織所傳送的加密電子郵件。

作為 O365 全域系統管理員, 當您套用公司品牌以自訂 Office 365 組織的電子郵件訊息的外觀時, 您也可以指定這些電子郵件的到期日。 透過 Office 365 高級郵件加密, 您可以為源于您組織的加密電子郵件建立多個範本。 您可以使用範本, 控制收件者存取使用者所傳送之郵件的時間長度。

當使用者收到到期日期設定的郵件時, 使用者會看到包裝電子郵件中的到期日。 如果使用者嘗試開啟過期的郵件, OME 入口網站中就會出現錯誤。

您只能將電子郵件的到期日期設定為外部收件者。

Office 365 高級郵件加密: 只要您套用自訂品牌, Office 365 就會將包裝套用至符合您套用範本的郵件流程規則的電子郵件。 此外, 如果您使用自訂品牌, 您只能使用到期時間。

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a>使用 PowerShell 建立自訂品牌範本以強制郵件到期

1. 使用在您的 Office 365 組織中具有全域系統管理員許可權的帳戶, 連線[至 Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) 。

2. 執行 Set-omeconfiguration Cmdlet。

     ```powershell
     New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
     ```

其中：

- `Identity`是自訂範本的名稱。

- `ExternalMailExpiryInDays`識別收件者在到期之前可以保留郵件的天數。 您可以使用1–730天之間的任何值。

## <a name="more-information-about-office-365-advanced-message-encryption"></a>有關 Office 365 高級郵件加密的詳細資訊

- [Office 365 進階郵件加密](ome-advanced-message-encryption.md)

- [撤銷由 Office 365 進階郵件加密所加密的電子郵件](revoke-ome-encrypted-mail.md)

- [郵件原則及符合性服務說明](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
