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
description: 內建置於 Azure 資訊保護、 貴組織的功能可以使用新的 Office 365 郵件加密受保護的電子郵件通訊與組織內外的人。與其他 Office 365 組織、 Outlook.com、 Gmail、 及其他電子郵件服務搭配使用的新 OME 功能。
ms.openlocfilehash: 90247a7e3cd7e5978eb144a2b6f66a9de21a8f96
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296186"
---
# <a name="set-up-new-office-365-message-encryption-capabilities"></a>設定全新的 Office 365 郵件加密功能

新的 Office 365 郵件加密 (OME) 功能允許與任何裝置上的任何人共用受保護的電子郵件組織。使用者可以交換受保護的訊息與其他 Office 365 組織以及非 Office 365 客戶使用 Outlook.com、 Gmail，以及其他電子郵件服務。


>[!NOTE]
>本文適用於系統管理員及 IT 專業人員的。如果您是使用者，請參閱[Office 365 郵件加密 (OME)](ome.md)中的適當解決方案的文章的清單。

請遵循下列步驟來確保您的 Office 365 租用戶中可用的新 OME 功能。 

## <a name="verify-azure-rights-management-arm-is-active"></a>確認已啟用 Azure 版權管理 (ARM)

>[!NOTE]
>新的 OME 功能利用[Azure 資訊保護](https://docs.microsoft.com/en-us/azure/information-protection/what-is-information-protection)、 [Azure 版權管理 (ARM)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms)所用的技術中的保護功能。

使用新的 OME 功能僅必要條件是[Azure 版權管理 (ARM)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms)必須要啟動 Office 365 租用戶中。如果它是 Office 365 會自動啟動新的 OME 功能和您不需要執行任何動作。 

ARM 也啟動自動最合格的計劃，因此您可能不需要執行任何動作在這方面也。如需詳細資訊，請參閱[啟動 Azure 版權管理](https://docs.microsoft.com/en-gb/azure/information-protection/activate-service)。

>[!IMPORTANT]
>如果您使用 Active Directory Rights Management service (AD RMS) 與 Exchange Online 時，您需要移轉[至 Azure 資訊保護](https://docs.microsoft.com/en-us/azure/information-protection/migrate-from-ad-rms-to-azure-rms)才能使用新的 OME 功能。AD RMS 不相容於 ARM。  

如需詳細資訊，請參閱：

- [我需要使用新的 OME 功能何種訂閱？](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities)若要檢查您的訂閱計劃是否包含 Azure 資訊保護 （其中包括 ARM）。   
-  如需購買合格的訂閱資訊[Azure 資訊保護](https://azure.microsoft.com/en-us/services/information-protection/)。  

### <a name="manually-activating-arm"></a>手動啟動 ARM

如果您停用 ARM，或如果它尚未自動啟動任何原因，您可以啟動其以手動方式：

- **Office 365 系統管理中心**： 了解[如何啟用 Azure 版權管理 Office 365 系統管理中心中](https://docs.microsoft.com/en-us/azure/information-protection/activate-office365)的指示
- **Azure 入口網站**： 了解[如何啟動 Azure Rights Management 從 Azure 入口網站](https://docs.microsoft.com/en-gb/azure/information-protection/activate-azure)的指示。 


## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a>設定管理 Azure 資訊保護承租人索引鍵

這是選用的步驟。允許 Microsoft Azure 資訊保護管理根機碼是預設設定與大部分的 Office 365 租用戶的建議最佳作法。如果是這樣，您不需要執行任何動作。 

有許多原因，例如規範需求，也許您產生及管理自己根 （也稱為將您自己的金鑰 (BYOK)） 的索引鍵。如果是這樣，建議您設定的新 OME 功能之前完成的必要的步驟。如需詳細資訊，請參閱[規劃及實作您 Azure 資訊保護租用戶金鑰](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)。 


## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a>確認 Exchange Online PowerShell 中的新 OME 組態

您可以驗證您的 Office 365 租用戶正確設定為在[Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)中使用的新 OME 功能。
  
1. [Connect to Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)使用的帳戶具有您的 Office 365 租用戶中的全域系統管理員權限。

2. 執行 Test-irmconfiguration 指令程式使用下列語法：

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   **範例**： 
   
     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```
     
     - 提供的寄件者電子郵件是選擇性的但會強制執行其他檢查系統。在您的 Office 365 租用戶中使用之任何使用者的電子郵件地址。 
     
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

   - 預設範本名稱可能會不同顯示上方。如需詳細資訊，請參閱[Azure 資訊保護的設定及管理範本](https://docs.microsoft.com/en-us/azure/information-protection/configure-policy-templates)。

3. 執行 Remove-pssession cmdlet 來中斷與版權管理服務的連線。
    
     ```powershell
     Remove-PSSession $session
     ```

## <a name="update-mail-flow-rules-to-use-new-ome-capabilities"></a>若要使用 OME 的新功能的郵件流程規則更新

如果您的 Office 365 租用戶中有先前已設定的[來加密電子郵件的郵件流程規則](define-mail-flow-rules-to-encrypt-email.md)，您需要更新下列現有的規則來使用新的 OME 功能。新部署的這個步驟是不需要此階段。   

>[!Note]
>郵件流程規則定義的電子郵件訊息會經過加密，以及何時應該移除加密的條件。如需詳細資訊，請參閱[定義郵件流程規則來加密 Office 365 中的電子郵件訊息](define-mail-flow-rules-to-encrypt-email.md)。

若要更新現有規則，以使用新的 OME 功能：

1. 在 Office 365 系統管理中心，移至**系統中心 > Exchange**。

2. 在 Exchange 系統管理中心，移至 [**郵件流程 > 規則**。 
3. 針對每個規則中**執行下列動作**：
    - 選取 [**修改郵件安全性**]。
    - 選取**適用於 Office 365 郵件加密和權限保護**。
    - 從清單中選取的 RMS 範本
    - 選取 **[儲存]**。
    - 選取 [確定]****。
  
>[!IMPORTANT]
>如果您未更新現有的郵件流程規則，您的使用者會繼續接收加密的郵件而不是新的 OME 功能使用先前的 HTML 附件格式。
