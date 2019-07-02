---
title: 撤銷由 Office 365 進階郵件加密所加密的電子郵件
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: 作為 Office 365 系統管理員, 您可以使用 Office 365 高級郵件加密來撤銷某些已加密的電子郵件。
ms.openlocfilehash: e55129f68c7add589bd973b36f069d7cdbf631cf
ms.sourcegitcommit: 5a93c2f3df35d06a59a7fbaff5c91f7afde11781
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/11/2019
ms.locfileid: "34857613"
---
# <a name="revoke-email-encrypted-by-office-365-advanced-message-encryption"></a>撤銷由 Office 365 進階郵件加密所加密的電子郵件

電子郵件撤銷是以 Office 365 高級郵件加密的一部分提供。 Office 365 高級郵件加密可在特定訂閱中的 Office 365 郵件加密上使用。 [Microsoft 365 企業版](https://www.microsoft.com/microsoft-365/enterprise/home)e5、Office 365 企業版 E5 和 Office 365 教育版 A5 包含先進的郵件加密。 如果您的組織有 Office 365 訂閱, 但未包含 Office 365 的高級郵件加密, 您可以使用 advanced 合規性 SKU 的 E5 規範, 以附加元件形式購買高級郵件加密。

本文是更多有關[Office 365 郵件加密](ome.md)的文章系列的一部分。

如果郵件是使用 Office 365 高級郵件加密進行加密, 而且您是 Office 365 系統管理員, 您可以在特定情況下撤銷郵件。 本文說明可進行撤銷的情況及其執行方式。
  
## <a name="encrypted-emails-that-you-can-revoke"></a>您可以撤銷的加密電子郵件

如果收件者收到以連結為基礎且署名的加密電子郵件, 您可以撤銷加密的電子郵件。 如果收件者在支援的 Outlook 用戶端中收到本機內嵌體驗, 則無法撤銷這些電子郵件。

收件者是否收到連結式經驗或內嵌經驗取決於收件者的身分識別類型: Office 365 和 Microsoft 帳戶收件者 (例如, outlook.com 使用者) 在支援的 Outlook 用戶端中取得內嵌體驗。 所有其他收件者類型 (例如 Gmail 收件者) 都會取得連結式體驗。

## <a name="recipient-experience-for-revoked-encrypted-emails"></a>撤銷加密電子郵件的收件者體驗

一旦電子郵件遭到吊銷, 當收件者透過 Office 365 郵件加密入口網站存取加密的電子郵件時, 會收到錯誤訊息: 「寄件者已撤銷該郵件」。

![顯示已撤銷加密之電子郵件的螢幕擷取畫面。](media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a>如何撤銷加密的電子郵件

### <a name="step-1-obtain-the-message-id-of-the-email"></a>步驟 1。 取得電子郵件的郵件識別碼

在您可以撤銷已加密的郵件之前, 您會收集郵件的郵件識別碼。 MessageId 的格式通常為:

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

有多種方法可以尋找您要撤銷之電子郵件的郵件識別碼。 本節說明一些選項, 但您可以使用任何提供識別碼的方法。

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a>若要使用安全性&amp;與合規性中心中的郵件追蹤來識別您要撤銷之電子郵件的郵件識別碼

1. 使用[Office 365 安全性 & 規範中心內的新郵件追蹤](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/), 以寄件者或收件者搜尋電子郵件。

2. 一旦您找到電子郵件, 請選取它以顯示 [**郵件追蹤詳細資料**] 窗格。 展開 [**更多資訊**] 以找出郵件識別碼。

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a>使用安全性&amp;與合規性中心中的 Office 郵件加密報告來識別您要撤銷之電子郵件的郵件識別碼

1. 在安全性&amp;與合規性中心內, 流覽至 [**郵件加密] 報告**。 如需此報告的詳細資訊, 請參閱[在&amp;安全性與合規性中心中查看電子郵件安全性報告](view-email-security-reports.md)。

2. 選擇 [**查看詳細資料**] 表格, 並找出您要撤銷的郵件。

3. 連按兩下郵件, 以查看包含郵件識別碼的詳細資料。

### <a name="step-2-verify-that-the-mail-is-revocable"></a>步驟 2。 確認郵件是可撤銷的

若要確認您是否可以撤銷郵件, 請檢查 [安全&amp;規範中心] 的 [**詳細資料**] 表格中的 [吊銷狀態] 欄位是否可見。

若要確認您是否可以使用 Windows Powershell 來撤銷特定的電子郵件, 請完成下列步驟。

1. 使用在 Office 365 組織中具有全域系統管理員許可權的公司或學校帳戶, 啟動 Windows PowerShell 會話, 並聯機至 Exchange Online。 如需相關指示, 請參閱[Connect To Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 請執行 OMEMessageStatus 指令程式, 如下所示:

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   這會傳回郵件的主旨, 以及郵件是否可撤銷。 For example,

     ```text
     Subject IsRevocable
     ------- -----------
     “Test message”  True
     ```

### <a name="step-3-revoke-the-mail"></a>步驟 3。 撤銷郵件

一旦您知道想要撤銷之電子郵件的郵件識別碼, 並確認該郵件是可撤銷的, 您就可以使用安全性&amp;合規性中心或 Windows Powershell 來撤銷電子郵件。

使用安全性&amp;與合規性中心撤銷郵件

若要撤銷安全性&amp;合規性中心內的電子郵件, 請在加密報告的 [**詳細資料**] 表格中, 選擇 **[撤銷郵件]**。

您可以使用 OMEMessageRevocation 指令程式, 透過使用 Windows Powershell 來撤銷電子郵件。

1. [連線至 Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 請執行 OMEMessageRevocation 指令程式, 如下所示:

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. 若要檢查電子郵件是否已被撤銷, 請執行 OMEMessageStatus 指令程式, 如下所示:

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    如果撤銷成功, Cmdlet 會傳回下列結果:  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a>有關 Office 365 高級郵件加密的詳細資訊

- [Office 365 進階郵件加密](ome-advanced-message-encryption.md)

- [Office 365 高級郵件加密-電子郵件到期](ome-advanced-expiration.md)

- [郵件原則及符合性服務說明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
