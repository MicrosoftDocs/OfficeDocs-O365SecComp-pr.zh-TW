---
title: Office 365 客戶管理加密功能
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 摘要： 了解 Microsoft Office 365 中的資料恢復能力。
ms.openlocfilehash: e835587e07246154cd700555cc7263370bde8755
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526163"
---
# <a name="customer-managed-encryption-features-in-office-365"></a>在 Office 365 的客戶管理加密功能

受管理的 microsoft Office 365 中的加密技術，以及 Office 365 也適用於其他加密技術可管理和設定，例如：
- [Azure 版權管理](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms)
- [安全多用途網際網路郵件延伸模組](http://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx)
- [Office 365 郵件加密](http://products.office.com/en-us/exchange/office-365-message-encryption)
- [與協力廠商組織的安全郵件流程](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)

也可在[Office 365 服務說明](https://technet.microsoft.com/en-us/library/office-365-service-descriptions.aspx)中找到這些技術的其他資訊。

## <a name="azure-rights-management"></a>Azure 版權管理
[Azure 版權管理](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms)(Azure RMS) 為[Azure 資訊保護](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)所用的保護技術。它會使用加密、 identity 及授權原則來協助保護您的檔案和電子郵件跨多個平台和裝置 — 電話、 平板電腦與 Pc。 資訊可以保護您的組織內外因為保護自行承擔資料。Azure RMS 提供的所有檔案類型的持續性保護、 保護任何位置的檔案、 支援營運商務共同作業及整體範圍的 Windows 和非 Windows 裝置。Azure RMS 保護也可增強[資料外洩防護 (DLP) 原則](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)。如需受應用程式及服務可以使用 Azure 資訊保護 Azure 版權管理服務的詳細資訊，請參閱[應用程式支援 Azure 版權管理服務的方式](https://docs.microsoft.com/information-protection/understand-explore/applications-support)。

Azure RMS 是整合式與 Office 365 且可供所有 Office 365 客戶。若要設定要使用 Azure RMS 的 Office 365，請參閱[設定 IRM 以使用 Azure 版權管理和設定向上資訊版權管理 (IRM) 設定 SharePoint 系統管理中心](https://technet.microsoft.com/en-us/library/dn151475(v=exchg.150).aspx)。如果操作內部部署 Active Directory (AD) RMS 伺服器則您也可以[設定 IRM 以使用內部部署 AD RMS 伺服器](https://docs.microsoft.com/office365/SecurityCompliance/configure-irm-to-use-an-on-premises-ad-rms-server)，但是我們強烈建議您將[移轉至 Azure RMS](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms)與其他使用像安全共同作業的新功能組織。

當您保護以 Azure RMS 的客戶資料時，Azure RMS 使用 2048年位元 RSA 非對稱金鑰與完整性的 256 SHA-1 雜湊演算法加密資料。Office 文件和電子郵件的對稱金鑰 AES 128 位元 （PKCS #7 邊框距離 CBC 模式）。針對每個文件或 Azure RMS 受保護的電子郵件、 Azure RMS 會建立單一 AES 索引鍵 （「 內容索引鍵"），並該機碼內嵌在文件中，而且透過文件的版本。內容索引鍵受到組織的 RSA 金鑰 （"Azure 的資訊保護租用戶金鑰"） 過程中的文件的原則及原則也簽署文件的作者。此租用戶機碼是一般所有文件和由 Azure RMS 保護組織的電子郵件與此機碼只能變更 Azure 資訊保護管理員如果組織使用的是客戶受管理的租用戶金鑰。如需使用 Azure RMS 密碼編譯控制項的詳細資訊，請參閱[Azure RMS 的運作方式？深入解析](https://docs.microsoft.com/information-protection/understand-explore/how-does-it-work)。

在預設 Azure RMS 實作 Microsoft 就會產生，以及管理是唯一的每個租用戶的根目錄機碼。客戶可以使用稱為[將您自己鍵 (BYOK)](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)金鑰管理方法來管理其根圖例符號中搭配 Azure 機碼存放庫 Services Azure RMS 的生命週期） 可讓您在內部部署 Hsm 產生您的金鑰與停留在之後此機碼的控制傳輸到 Microsoft 的 FIPS 140-2 層級 2 驗證 Hsm。 存取的根金鑰不是任何人員授與無法匯出或從保護其硬體安全性模組解壓縮機碼。此外，您可以存取任何時候顯示所有的存取權的根金鑰近即時記錄檔。如需詳細資訊，請參閱[記錄及分析 Azure 版權管理流量](https://docs.microsoft.com/azure/information-protection/log-analyze-usage)。

Azure 版權管理可幫助可以降低威脅如 wire-tapping、 攔截攻擊、 資料竊取及無意違規的組織共用原則。同時，任何未經授權存取權限的客戶資料傳輸中或靜態未經授權的使用者不具有適當的權限無法透過遵循資料，進而減輕下降錯誤在該資料的風險傳遞之一的原則有意或無意及提供資料遺失防護功能。如果使用 Azure 資訊保護的一部分，Azure RMS 也提供資料分類和顯示標籤功能、 內容的標示、 文件存取追蹤及存取撤銷功能。若要深入了解這些功能，請參閱[什麼是 Azure 資訊保護](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)、 [Azure 資訊保護部署藍圖](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap)及[Azure 資訊保護的快速入門教學課程](https://docs.microsoft.com/information-protection/get-started/infoprotect-quick-start-tutorial)。

## <a name="secure-multipurpose-internet-mail-extension"></a>安全多用途網際網路郵件延伸模組
安全/多用途網際網路郵件延伸標準 (S/MIME) 是一種標準公開金鑰加密及數位簽章之 MIME 資料。S/MIME 中定義 Rfc 3369 3370、 3850、 3851，與其他人。它可讓使用者加密電子郵件及數位簽署電子郵件。使用 S/MIME 加密的電子郵件僅使用其私密金鑰]，這是僅供該收件者的電子郵件收件者進行解密。因此，這類電子郵件無法解密的郵件的收件者的電子郵件以外的任何人。

[Microsoft 支援 S/MIME Office 365 中](http://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx)。公用憑證會傳送給客戶的內部部署 Active Directory 並儲存在可以複寫至 Office 365 租用戶的屬性。會對應到公用機碼的私密金鑰保持在內部部署和永不傳送至 Office 365。使用者可以撰寫、 加密、 解密、 讀取、 及數位簽章之間使用 Outlook、 Outlook web 及 Exchange ActiveSync 用戶端在組織中的兩個使用者的電子郵件。如需詳細資訊，請參閱[Office 365 中的 now S/MIME 加密](http://blogs.office.com/2014/02/26/smime-encryption-now-in-office-365/)。

## <a name="office-365-message-encryption"></a>Office 365 郵件加密
[Office 365 郵件加密](https://products.office.com/en-us/exchange/office-365-message-encryption)(OME) 建置上方的[Azure 資訊保護](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)(AIP) 可讓您傳送加密及受權限保護郵件給任何人。OME 可以降低 wire-tapping 等攔截攻擊威脅及其他威脅，例如未經授權存取的資料由未經授權的使用者不具有適當的權限。我們已進行了提供您建置 Azure 資訊保護上方的簡化、 更直覺式、 安全的電子郵件經驗的成本。您可以保護郵件從 Office 365 傳送至您的組織內外的任何人。這些訊息可以檢視整個各式各樣的郵件用戶端使用任何的 identity，包括 Azure Active Directory、 Microsoft 帳戶及 Google 識別碼。如需有關如何組織可以使用加密的郵件的詳細資訊，請參閱[Office 365 郵件加密](https://support.office.com/article/F87CB016-7876-4317-AE3C-9169B311FF8A)。

## <a name="transport-layer-security"></a>傳輸層安全性
如果您想要確保安全與合作夥伴的通訊，您可以使用輸入和輸出連接器來提供安全性和訊息的完整性。您可以設定強制的輸入和輸出 TLS 每一個連接器，使用憑證。使用加密的 SMTP 通道可以防止資料被竊透過攔截攻擊。如需詳細資訊，請參閱[如何 Exchange Online 使用 TLS 來保護電子郵件連線](https://support.office.com/article/How-Exchange-Online-uses-TLS-to-secure-email-connections-in-Office-365-4CDE0CDA-3430-4DC0-B489-F2C0736C929F)。

## <a name="domain-keys-identified-mail"></a>網域金鑰所識別的郵件
Exchange Online Protection (EOP) 和 Exchange Online 支援輸入的驗證網域金鑰所識別信箱 (DKIM) 的郵件。DKIM 是一種方法驗證郵件已傳送從它表示郵件來自網域並不詐騙由其他人。並方式繫結至負責傳送，組織的電子郵件的電子郵件加密的較大架構的一部分。如需此架構的三種組件的詳細資訊，請參閱：
- [在 Office 365 中設定 SPF 以協助防止詐騙](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)
- [使用 DKIM 驗證從您在 Office 365 中的自訂網域傳送的輸出電子郵件](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)
- [使用 DMARC 來驗證 Office 365 電子郵件](https://https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)
