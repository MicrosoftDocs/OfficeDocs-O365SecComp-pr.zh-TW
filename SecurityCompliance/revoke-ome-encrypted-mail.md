---
title: 撤銷由 Office 365 郵件加密所加密的電子郵件
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
description: Office 365 系統管理員身分您可以撤銷已加密的 Office 365 郵件加密特定電子郵件。
ms.openlocfilehash: 018f12105e19382372a8a4b3a91248bb60b228be
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2019
ms.locfileid: "29696237"
---
# <a name="office-365-message-encryption-email-revocation"></a>Office 365 郵件加密的電子郵件撤銷

本文屬於較大的一系列有關[Office 365 郵件加密](ome.md)的文章。現在右、 加密的電子郵件撤銷處於預覽。我們繼續提升我們可以如預期更新和變更功能和內容。

您可能會發現需要撤銷已送出之電子郵件。如果已加密的電子郵件使用 Office 365 郵件加密，而且您的 Office 365 系統管理員，您可以這麼做以在某些情況下電子郵件。本文說明 [這是可行何種情況和執行方式。
  
## <a name="encrypted-emails-that-you-can-revoke"></a>您可以撤銷的加密電子郵件

如果收件者收到連結型、 具有品牌形象的加密的電子郵件，可以撤銷已加密的電子郵件。如果收件者收到的原生內嵌體驗中支援的 Outlook 用戶端，不會撤銷這些電子郵件。

收件者會收到連結型經驗還是內嵌經驗取決於收件者的身分識別類型： Office 365 及 Microsoft 帳戶收件者 （例如 outlook.com 使用者） 取得中支援的 Outlook 用戶端的內嵌經驗。所有其他收件者類型，例如 Gmail 收件者] 取得連結為基礎的體驗。

即將推出的組織必須強制不論收件者的身分識別的連結型經驗的能力。如此一來，所有收件者會取得加上品牌的電子郵件與其中他們將能夠讀取和回覆加密的電子郵件的 Office 365 郵件加密入口網站的連結。將可撤銷之所有這類加密的電子郵件。
  
## <a name="recipient-experience-for-revoked-encrypted-emails"></a>撤銷已加密的電子郵件的收件者經驗

收件者之後已被撤銷電子郵件，將會在嘗試透過 Office 365 郵件加密入口網站存取加密的電子郵件時收到的錯誤： 「 寄件者，郵件已被撤銷"。

![這個螢幕擷取畫面顯示撤銷加密的電子郵件。](media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a>若要撤銷加密的電子郵件的方式

### <a name="step-1-obtain-the-message-id-of-the-email"></a>步驟 1。取得電子郵件訊息識別碼

您可以撤銷已加密的郵件之前您必須收集郵件訊息識別碼。MessageId 通常是之格式的：

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

有多個方法來尋找您想要撤銷的電子郵件訊息識別碼。本節說明一些選項，但是您可以使用任何方法可提供 [識別碼]。

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a>若要找出您想要撤銷安全性使用郵件追蹤電子郵件訊息識別碼&amp;規範中心

1. 搜尋由寄件者或收件者使用[新的 Message Trace in Office 365 安全性 & 規範中心](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)的電子郵件。
2. 一旦您已經找到電子郵件選取其相反的**郵件追蹤詳細資料**窗格。依序展開 [**更多的資訊**來找出郵件的識別碼。

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a>若要找出您想要撤銷安全性中使用 Office 郵件加密報告的電子郵件訊息識別碼&amp;規範中心

1. 安全性&amp;規範中心瀏覽至 [**郵件加密報告**。
2. 選擇 [**檢視詳細資料**] 表格，並找出您想要撤銷的訊息。
3. 按兩下 [檢視詳細資料] 包含郵件識別碼的訊息

### <a name="step-2-verify-that-the-mail-is-revocable"></a>步驟 2。確認便可撤銷之電子郵件

若要確認可以撤銷特定電子郵件訊息，請完成下列步驟。

1. 使用 Office 365 組織中具有全域系統管理員權限的工作或學校帳戶，請啟動 Windows PowerShell 工作階段並連線至 Exchange Online。指示，請參閱[Connect to Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 執行設定 OMEMessageStatus 指令程式，如下所示：
     ```powershell
     Get-OMEMessageStatus -MessageId "<messagieid>" | ft -a  Subject, IsRevocable
     ```

   這會傳回郵件以及是否可撤銷之郵件的主旨。例如，

     ```text
     Subject IsRevocable
     ------- -----------
     “Test message”  True
     ```

### <a name="step-3-revoke-the-mail"></a>步驟 3。撤消郵件  

一旦您知道您想要撤銷權限、 電子郵件訊息識別碼，並確認郵件可撤銷之，您可以使用組 OMEMessageRevocation 指令程式撤銷電子郵件。

1. [連線至 Exchange Online PowerShell](https://aka.ms/exopowershell) (機器翻譯)。

2. 執行設定 OMEMessageRevocation 指令程式，如下所示：

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. 若要檢查是否已遭撤銷電子郵件，如下執行 Get OMEMessageStatus cmdlet：

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```  
    如果撤銷成功，指令程式會傳回下列結果：  

    `Revoked: True`
