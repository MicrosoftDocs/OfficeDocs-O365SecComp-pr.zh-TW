---
title: 設定全新的 Office 365 郵件加密功能
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
description: 以 Azure 資訊保護，您的組織內建的功能可以使用新的 Office 365 郵件加密保護與組織內外的人員的電子郵件通訊。 全新的 OME 功能與其他 Office 365 組織、 Outlook.com、 Gmail，以及其他電子郵件服務搭配使用。
ms.openlocfilehash: fd237e537aa1ff961d2d975b3b30f4a51744ba7c
ms.sourcegitcommit: e24f70699021c4f4ba56508ad0afb6f65010c357
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/05/2019
ms.locfileid: "31479649"
---
# <a name="set-up-new-office-365-message-encryption-capabilities"></a>設定全新的 Office 365 郵件加密功能

新的 Office 365 郵件加密 (OME) 功能讓組織能與任何裝置上的任何人共用受保護的電子郵件。 使用者可以交換與其他 Office 365 組織，以及使用 Outlook.com、 Gmail，以及其他電子郵件服務的非 Office 365 客戶受保護的郵件。


>[!NOTE]
>本文適用於系統管理員和 IT 專業人員。 如果您是使用者，請參閱在[Office 365 郵件加密 (OME)](ome.md)中的適當的解決方案的文章的清單。

請遵循下列步驟來確保新的 OME 功能可用的 Office 365 租用戶中。

## <a name="verify-azure-rights-management-arm-is-active"></a>確認 Azure 版權管理 (ARM) 正在使用中

>[!NOTE]
>全新的 OME 功能利用[Azure 資訊保護](https://docs.microsoft.com/en-us/azure/information-protection/what-is-information-protection)， [Azure 版權管理 (ARM)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms)所使用的技術中的保護功能。

使用全新的 OME 功能僅必要條件是[Azure 版權管理 (ARM)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms)必須先啟動 Office 365 租用戶中。 如果是，Office 365 會自動啟動全新的 OME 功能，而且不需要執行任何動作。

ARM 便也會自動啟動最合格的方案，因此您可能不需要執行任何動作在這方面可以。 如需詳細資訊，請參閱[啟用 Azure Rights Management](https://docs.microsoft.com/en-gb/azure/information-protection/activate-service) 。

>[!IMPORTANT]
>如果您使用 Active Directory Rights Management 服務 (AD RMS) 與 Exchange Online，您需要移轉[至 Azure 資訊保護](https://docs.microsoft.com/en-us/azure/information-protection/migrate-from-ad-rms-to-azure-rms)之後才能使用全新的 OME 功能。 AD RMS 不相容於 ARM。  

如需詳細資訊，請參閱：

- [我需要使用全新的 OME 功能何種訂閱？](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities)若要查看您的訂閱計劃是否包含 Azure 資訊保護 （其中包含 ARM）。
- 如需購買合格的訂閱的[Azure 資訊保護](https://azure.microsoft.com/en-us/services/information-protection/)。  

### <a name="manually-activating-arm"></a>手動啟動 ARM

如果您停用 ARM，或如果它不會自動啟動因任何原因，您可以啟動它以手動方式在:

- **Office 365 系統管理中心**： 如需相關指示，請參閱[How to 啟用從 Office 365 系統管理中心的 Azure Rights Management](https://docs.microsoft.com/en-us/azure/information-protection/activate-office365) 。
- **Azure 入口網站**： 如需相關指示，請參閱[How to 啟動 Azure Rights Management，從 Azure 入口網站](https://docs.microsoft.com/en-gb/azure/information-protection/activate-azure)。

## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a>設定您的 Azure 資訊保護租用戶金鑰管理

這是選用的步驟。 允許 Microsoft，以管理 Azure 資訊保護根機碼是預設設定，並針對大多數的 Office 365 租用戶的建議最佳作法。 如果是這樣，您不需要執行任何動作。

有許多原因，例如動作，可能必須產生您的合規性需求及管理自己根機碼 （也稱為攜帶您自己的金鑰 (BYOK)）。 如果是這樣，建議您在設定全新的 OME 功能之前完成所需的步驟。 如需詳細資訊，請參閱[規劃及實作 Azure 資訊保護您的租用戶金鑰](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)。

## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a>確認 Exchange Online PowerShell 中的新 OME 組態

您可以驗證您的 Office 365 租用戶正確設定為使用[Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)中的全新的 OME 功能。
  
1. 使用 Office 365 租用戶中的全域系統管理員權限的帳戶[連線到 Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) 。

2. 執行 Test-irmconfiguration 指令程式使用下列語法：

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   **範例**：

     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```

     - 提供的寄件者電子郵件是選擇性的但會強制執行的額外檢查系統。 使用 Office 365 租用戶中的任何使用者的電子郵件地址。 

     您的結果應該會類似：

     ```text
    Results : Acquiring RMS Templates ...
                - PASS: RMS Templates acquired.  Templates available: Contoso  - Confidential View Only, Contoso  - Confidential, Do Not 
            Forward.
            Verifying encryption ...
                - PASS: Encryption verified successfully.
            Verifying decryption ...
                - PASS: Decryption verified successfully.
            Verifying IRM is enabled ...
                - PASS: IRM verified successfully.

            OVERALL RESULT: PASS
    ```

   - Office 365 組織的名稱將會取代*Contoso*。

   - 預設範本名稱可能不同顯示上方。 如需詳細資訊，請參閱[Azure 資訊保護的設定和管理範本](https://docs.microsoft.com/en-us/azure/information-protection/configure-policy-templates)。

3. 執行 Remove-pssession cmdlet，從 Rights Management 服務中斷連線。

     ```powershell
     Remove-PSSession $session
     ```

## <a name="update-mail-flow-rules-to-use-new-ome-capabilities"></a>更新郵件流程規則來使用全新的 OME 功能

如果您的 Office 365 租用戶中有先前設定的[郵件流程規則來加密電子郵件](define-mail-flow-rules-to-encrypt-email.md)，您需要更新這些現有的規則，以使用全新的 OME 功能。 針對新的部署，此步驟是不需要在此階段。   

>[!Note]
>郵件流程規則定義的電子郵件加密郵件，以及何時應移除加密的條件。 如需詳細資訊，請參閱[定義郵件流規則以加密 Office 365 中的電子郵件](define-mail-flow-rules-to-encrypt-email.md)。

若要更新現有的規則，以使用全新的 OME 功能：

1. 在 Office 365 系統管理中心中，移至**系統置 > Exchange**。

2. 在 Exchange 系統管理中心，移至 [**郵件流程 > 規則**。 
3. 每個規則，以**執行下列動作**：
    - 選取 [**修改郵件安全性**]。
    - 選取 [**適用於 Office 365 郵件加密和權限保護**。
    - 從清單中選取的 RMS 範本。
    - 選取**儲存**。
    - 選取 [確定]****。
  
>[!IMPORTANT]
>如果您沒有更新現有的郵件流程規則，您的使用者將會繼續收到加密的郵件使用先前的 HTML 附件格式，而不是全新的 OME 功能。
