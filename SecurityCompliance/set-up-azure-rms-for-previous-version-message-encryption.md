---
title: 設定舊版的 Office 365 郵件加密的 Azure Rights Management
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: 舊版的 Office 365 郵件加密取決於 Microsoft Azure Rights Management （先前稱為 Windows Azure Active Directory Rights Management）。
ms.openlocfilehash: 994364fd74881e40f97daa3c2d12e31282b421fd
ms.sourcegitcommit: 1c00bba6ddcdd7ead6cc0153c8a2c20de05262ba
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/20/2018
ms.locfileid: "27382924"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-office-365-message-encryption"></a>設定舊版的 Office 365 郵件加密的 Azure Rights Management

本主題說明您必須遵循以啟動，然後設定 [向上 Azure 版權管理 (RMS)、 一部分 Azure 資訊保護，先前版本的 Office 365 郵件加密 (OME) 搭配使用的步驟。

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a>本文僅適用於 OME 的前一版
如果您尚未尚未移動 Office 365 組織到新的 OME 功能，但您已部署 OME，本文資訊適用於您組織。Microsoft 建議您將移至新的 OME 功能一旦是組織的合理的計劃。指示，請參閱[Set up Office 365 郵件加密的新功能](set-up-new-message-encryption-capabilities.md)。如果您想要了解更多有關的新功能如何運作前，請參閱[Office 365 郵件加密](ome.md)。本文的其餘部分是指 OME 行為的新 OME 功能發行前。

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a>使用舊版的 Office 365 郵件加密的必要條件
<a name="warmprereqs"> </a>

Office 365 郵件加密 (OME)，包括 IRM，取決於 Azure 版權管理 (Azure RMS)。Azure RMS 是 Azure 資訊保護所用的保護技術。若要使用 OME，Office 365 組織必須包含 Exchange Online 或 Exchange Online Protection，接著，包含訂閱 Azure 版權管理訂閱。
  
- 如果您不確定您的訂閱所包含的內容，請參閱[訊息原則、 復原及規範](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx)的 Exchange Online 服務說明。

- 如果您沒有 Azure RMS 訂閱的 Exchange Online 或 Exchange Online Protection，您必須購買訂閱和先加以啟動。

    如需購買 Azure 版權管理訂閱，請參閱[Azure Rights Management](https://portal.office.com/Signup/MainSignUp15.aspx?&amp;OfferId=9DF77AF9-DAAE-4d51-8E0E-EEEADD4866B8&amp;dl=RIGHTSMANAGEMENT)。下一步] 區段可讓您啟動 Azure 版權管理的相關資訊。

- 如果您有 Azure Rights Management，但它未設定 Exchange Online 或 Exchange Online Protection，本文說明如何啟動 Azure Rights Management 並加上 then 說明 OME 設為使用 Azure 版權管理的最佳方式。

- 如果您已經設定 OME 使用 Azure 版權管理 Exchange Online 或 Exchange Online Protection，根據您如何設定它，您可能即可開始使用 OME 及新功能，其立即。本文說明如何決定是否您已設定 OME 正確，如果您需要變更您的安裝程式，該怎麼辦以及如果您選擇不要變更您的安裝程式會發生什麼事。例如，才可使用的新功能，您必須使用 Azure RMS 與 OME。您不能搭配內部部署 Active Directory RMS 的新功能。

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a>啟動先前版本的 Office 365 中的 OME Azure Rights Management

您必須啟用 Azure 版權管理組織中的使用者可以將資訊保護套用到傳送時的訊息和開啟郵件與具備已受到 Azure 版權管理服務的檔案。指示，請參閱[啟動 Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=525775)。一旦您已經完成啟用，此處傳回並繼續執行本文中的工作。
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a>設定 OME 的前一版使用 Azure RMS 匯入信任的發行網域 (TPDs)

TPD 是 XML 檔案包含您的組織版權管理設定的相關資訊。例如，TPD 包含用於簽署和加密憑證和授權的伺服器授權人憑證 (SLC) 的相關資訊、 Url 用於授權和發佈、 等等。使用 Windows PowerShell TPD 匯 Office 365 組織中。
  
> [!IMPORTANT]
> 之前，您可以選擇從 Active Directory Rights Management service (AD RMS) TPDs 匯入至您的 Office 365 組織。不過，這麼會防止使用新的 OME 功能並不建議使用。如果您的組織是目前的 Office 365 設定如此一來，Microsoft 建議您建立從您的內部部署 Active Directory RMS 移轉至雲端式 Azure 資訊保護計劃。如需詳細資訊，請參閱 ＜ [Migrating from AD RMS 以 Azure 資訊保護](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)。您無法使用新的 OME 功能直到您完成移轉至 Azure 資訊保護。
  
 **若要從 Azure RMS 匯入 TPDs**
  
1. [連線至 Exchange Online 使用遠端 PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)。

2. 選擇金鑰共用 URL 對應至 Office 365 組織的地理位置：

|**位置**|**金鑰共用位置 URL**|
|:-----|:-----|
|北美  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|歐盟  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|亞洲  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|南美洲  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Office 365 for Government (政府社群雲端)  <br/> 此 RMS 金鑰共用位置保留供已購買 Office 365 for Government Sku 的客戶。  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
   
3. 設定金鑰共用位置執行[Set-irmconfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx)指令程式，如下所示： 
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
  ```

    例如，若要設定金鑰共用位置若您的組織位於 「 北美地區 」：
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
  ```

4. 使用 Azure Rights Management 從匯入 TPD-RMSOnline 參數執行[Import-rmstrustedpublishingdomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx)指令程式： 
    
  ```
  Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
  ```

    您想要用於 TPD *TPDName*所在的名稱。例如，"Contoso 北美地區 TPD"。 
    
5. 若要確認您已順利設定 Office 365 組織使用 Azure 版權管理服務，執行[Test-irmconfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx)指令程式搭配-RMSOnline 參數，如下所示： 
    
  ```
  Test-IRMConfiguration -RMSOnline
  ```

    除此之外，此指令程式會檢查使用 Azure Rights Management service 的連線、 下載 TPD，並檢查其有效性。
    
6. 執行[Set-irmconfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx)指令程式，如下所示停用來在網頁伺服器和 Outlook 在 Outlook 中可用的 Azure Rights Management 範本： 
    
  ```
  Set-IRMConfiguration -ClientAccessServerEnabled $false
  ```

7. 執行[Set-irmconfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx)指令程式，如下所示的雲端架構電子郵件組織啟用 Azure Rights Management 並將它設定成使用 Office 365 郵件加密的 Azure Rights Management： 
    
  ```
  Set-IRMConfiguration -InternalLicensingEnabled $true
  ```

8. 若要確認您已成功匯入 TPD 並啟用 Azure Rights Management，請使用 Test-irmconfiguration 指令程式來測試 Azure 版權管理功能。如需詳細資訊，請參閱[Test-irmconfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx)中的 「 範例 1"。
    
## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a>我必須設定與 Active Directory Rights Management 未 Azure 資訊保護 OME 的前一版，該怎麼辦吗？
<a name="importTPDs"> </a>

您可以繼續使用現有的 Office 365 郵件加密郵件流程規則具有 Active Directory Rights Management，但您無法設定或使用新的 OME 功能。而您需要移轉至 Azure 資訊保護。如需移轉與這表示您的組織資訊，請參閱 ＜ [Migrating from AD RMS 以 Azure 資訊保護](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms)。
  
## <a name="next-steps"></a>後續步驟
<a name="importTPDs"> </a>

如果您想要啟用新的 OME 功能，請參閱完成 Azure 版權管理安裝後[設定新的 Office 365 郵件加密功能建置於 Azure 資訊保護之上。](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e)
  
您已設定您的組織使用的新 OME 功能之後，您準備好[定義郵件流程規則來保護電子郵件訊息與 OME 的新功能](define-mail-flow-rules-to-encrypt-email.md)。
  
## <a name="related-topics"></a>相關主題
<a name="importTPDs"> </a>

[Office 365 中的加密](encryption.md)
  
[關於 Office 365 中加密的技術參考細節](technical-reference-details-about-encryption.md)
  
[Azure 版權管理新功能](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)
  

