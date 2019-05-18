---
title: 設定舊版 Office 365 郵件加密的 Azure 版權管理
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: 舊版的 Office 365 郵件加密取決於 Microsoft Azure 版權管理 （先前稱為 Windows Azure Active Directory Rights Management）。
ms.openlocfilehash: 84922a57c6245cf3214f17ba922417b5e025b796
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34158495"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-office-365-message-encryption"></a>設定舊版 Office 365 郵件加密的 Azure 版權管理

本主題說明您所須才能啟動並再將設定備份 Azure 版權管理 (RMS)，與舊版 Office 365 郵件加密 (OME) 搭配使用的組件的 Azure 資訊保護，請依照下列步驟。

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a>本文僅適用於舊版 OME
如果您尚未尚未將您的 Office 365 組織移動到全新的 OME 功能，但您已部署 OME，本文資訊適用於您的組織。 Microsoft 建議您先將移至全新的 OME 功能，只要是合理的貴組織的計劃。 如需相關指示，請參閱 <<c0>設定新的 Office 365 郵件加密功能。 如果您想要深入了解新功能的運作方式第一次，請參閱[Office 365 郵件加密](ome.md)。 本文的其餘部分指的是全新的 OME 功能的發行前 OME 行為。

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a>使用舊版的 Office 365 郵件加密的必要條件
<a name="warmprereqs"> </a>

Office 365 郵件加密 (OME)，包括 IRM，取決於 Azure 版權管理 (Azure RMS)。 Azure RMS 是使用 Azure 資訊保護來保護技術。 若要使用 OME，Office 365 組織必須包含 Exchange Online 或 Exchange Online Protection，接著，包含訂閱的 Azure Rights Management 訂閱。
  
- 如果您不確定您的訂閱所包含的內容，請參閱[訊息原則、 復原和法規遵循](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx)的 Exchange Online 服務說明。

- 如果您不需要 Azure RMS 訂閱 Exchange Online 或 Exchange Online Protection，您必須購買訂閱，並先啟動它。

    如需購買 Azure Rights management 訂閱資訊，請參閱 < <b0>Azure Rights Management</b0>。 下節提供啟動 Azure Rights Management 的資訊。

- 如果您有 Azure Rights Management，但它未設定 Exchange Online 或 Exchange Online Protection，這篇文章說明如何啟用 Azure Rights Management，然後說明設定 OME，以使用 Azure 版權管理的最佳方式。

- 如果您已經設定好 OME 能搭配 Azure 版權管理 Exchange Online 或 Exchange Online Protection，根據您如何設定它，您可能會準備好開始使用 OME 與新功能，其立即。 本文說明如何判斷是否您已設定 OME 正確，如果您要變更您的設定，該怎麼辦以及如果您選擇不要變更您的設定，會發生什麼事。 例如，若要使用的新功能，您必須使用 Azure RMS OME。 您不能搭配內部部署 Active Directory RMS 的新功能。

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a>前一版本的 Office 365 中的 OME 啟動 Azure Rights Management

您要啟用 Azure Rights Management，以便您組織中的使用者可以將資訊保護套用至他們傳送的郵件，並開啟郵件和已受 Azure 版權管理服務的檔案。 如需相關指示，請參閱 <<c0>啟動 Azure Rights Management。 當您完成在啟動時，以下傳回，並繼續執行本文中的工作。
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a>設定舊版的 OME 使用 Azure RMS 匯入受信任發行網域 (Tpd)

TPD 是 XML 檔案，其中包含貴組織的版權管理設定的相關資訊。 例如，將 TPD 包含用來簽署及加密憑證和授權的伺服器授權人憑證 (SLC) 的相關資訊、 Url 用於授權和發行，依此類推。 您使用 Windows PowerShell 將 TPD 匯入 Office 365 組織。
  
> [!IMPORTANT]
> 之前，您可以選擇從 Active Directory Rights Management 服務 (AD RMS) 將 Tpd 匯入到 Office 365 組織。 不過，這樣會使您無法使用全新的 OME 功能並不建議使用。 如果您的組織是目前的 Office 365 設定如此一來，Microsoft 建議您建立計劃從您的內部部署 Active Directory RMS 移轉至雲端式 Azure 資訊保護。 如需詳細資訊，請參閱 <<c0>從 AD RMS 進行 Azure 資訊保護。 您無法使用全新的 OME 功能，直到您已經完成移轉至 Azure 資訊保護。
  
 **若要從 Azure RMS 匯入 Tpd**
  
1. [連線至 Exchange Online 使用遠端 PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)。

2. 選擇金鑰共用 URL 對應至 Office 365 組織的地理位置：

|**位置**|**金鑰共用位置的 URL**|
|:-----|:-----|
|北美  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|歐盟  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|亞  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|南美洲  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Office 365 for Government (政府社群雲端)  <br/> 此 RMS 金鑰共用位置被保留給客戶已購買 Office 365 for Government Sku。  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
   
3. 設定金鑰共用位置執行[Set-irmconfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx)指令程式，如下所示： 
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
  ```

    例如，若要設定的金鑰共用位置，如果您的組織位於 「 北美地區 」:
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
  ```

4. 執行[Import-rmstrustedpublishingdomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx)指令程式搭配-RMSOnline 參數，以匯入 TPD 從 Azure 版權管理： 
    
  ```
  Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
  ```

    您想要用於 TPD *TPDName*所在的名稱。 例如，「 Contoso 北美地區 TPD 」。 
    
5. 若要確認您成功設定 Office 365 組織要使用 Azure 版權管理服務，請執行[Test-irmconfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx)指令程式搭配-RMSOnline 參數，如下所示： 
    
  ```
  Test-IRMConfiguration -RMSOnline
  ```

    除此之外，這個 cmdlet 會檢查以 Azure 版權管理服務的連線、 下載 TPD，並檢查其有效性。
    
6. 執行[Set-irmconfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx)指令程式，如下所示來停用不會出現在網頁伺服器與 Outlook 上的 Outlook 中的 Azure Rights Management 範本： 
    
  ```
  Set-IRMConfiguration -ClientAccessServerEnabled $false
  ```

7. 執行[Set-irmconfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx)指令程式，如下所示為雲端式電子郵件組織啟用 Azure Rights Management，並將其用於 Office 365 郵件加密的 Azure 版權管理設定： 
    
  ```
  Set-IRMConfiguration -InternalLicensingEnabled $true
  ```

8. 若要確認您已成功匯入 TPD 並啟用 Azure Rights Management，請使用 Test-irmconfiguration 指令程式來測試 Azure 版權管理功能。 如需詳細資訊，請參閱[Test-irmconfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx)中的 「 範例 1 」。
    
## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a>我有舊版的 OME 設定與 Active Directory Rights Management Azure 資訊保護，我該怎麼辦？
<a name="importTPDs"> </a>

您可以繼續使用現有的 Office 365 郵件加密郵件流程規則與 Active Directory Rights Management，但您無法設定或使用全新的 OME 功能。 相反地，您需要移轉至 Azure 資訊保護。 移轉和這對您的組織相關資訊，請參閱[從 AD RMS 進行 Azure 資訊保護](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms)。
  
## <a name="next-steps"></a>後續步驟
<a name="importTPDs"> </a>

當您完成 Azure 版權管理設定] 中，如果您想要啟用全新的 OME 功能，請參閱[設定以 Azure 資訊保護基礎所建置的全新 Office 365 郵件加密功能。](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e)
  
您已設定您的組織使用全新的 OME 功能之後，就可以[定義郵件流程](define-mail-flow-rules-to-encrypt-email.md)規則來保護電子郵件訊息與全新的 OME 功能。
  
## <a name="related-topics"></a>相關主題
<a name="importTPDs"> </a>

[Office 365 中的加密](encryption.md)
  
[關於 Office 365 中加密的技術參考細節](technical-reference-details-about-encryption.md)
  
[什麼是 Azure 版權管理？](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)
  

