---
title: Office 365 客戶管理加密功能
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 摘要： 了解 Microsoft Office 365 中的資料復原。
ms.openlocfilehash: 7c4817a2982733bc1d292117811cb21aa5278972
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262915"
---
# <a name="customer-managed-encryption-features-in-office-365"></a>Office 365 中的客戶管理加密功能

Microsoft 受管理的 Office 365 中的加密技術，以及 Office 365 也可用於其他加密技術可以讓您管理和設定，例如：
- [Azure 版權管理](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms)
- [安全多用途網際網路郵件延伸模組](http://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx)
- [Office 365 郵件加密](http://products.office.com/en-us/exchange/office-365-message-encryption)
- [為夥伴組織的安全郵件流程](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)

也可在[Office 365 服務說明](https://technet.microsoft.com/en-us/library/office-365-service-descriptions.aspx)中找到這些技術的其他資訊。

## <a name="azure-rights-management"></a>Azure 版權管理
[Azure 版權管理](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms)(Azure RMS) 是使用[Azure 資訊保護](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)來保護技術。 它會使用加密、 identity 及授權原則來協助保護您的檔案及跨多個平台和裝置的電子郵件-電話、 平板及電腦。 資訊可以保護您的組織內外因為與資料持續保護。 Azure RMS 提供持續性的保護所有檔案類型、 會保護任何一處的檔案，可支援企業對企業共同作業、 整個範圍的 Windows 和非 Windows 裝置。 Azure RMS 保護也可以增強[資料外洩防護 (DLP) 原則](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)。 如相關的應用程式與服務可以使用 Azure 資訊保護 Azure 版權管理服務的詳細資訊，請參閱 <<c0>如何應用程式都支援 Azure 版權管理服務。

Azure RMS 是與 Office 365 整合且可供所有 Office 365 客戶。 若要設定 Office 365，以使用 Azure RMS，請參閱[將 IRM 設定為使用 Azure 版權管理和設定設定資訊版權管理 (IRM) 設定 SharePoint 管理中心裡](https://technet.microsoft.com/en-us/library/dn151475(v=exchg.150).aspx)。 如果您經營內部部署 Active Directory (AD) RMS 伺服器，則您也可以[將 IRM 設定為使用內部部署 AD RMS 伺服器](https://docs.microsoft.com/office365/SecurityCompliance/configure-irm-to-use-an-on-premises-ad-rms-server)，但我們強烈建議您[移轉至 Azure RMS](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms)與其他使用新的功能，例如安全的共同作業組織。

當您保護含有 Azure RMS 的客戶資料時，Azure RMS 會使用完整性的 sha-256 雜湊演算法與 2048年位元的 RSA 非對稱金鑰來加密資料。 Office 文件和電子郵件的對稱金鑰 AES 128 位元 （PKCS #7 填補 CBC 模式）。 每個文件或受保護的 Azure RMS 的電子郵件，Azure RMS 會建立單一 AES 鑰匙 （在 「 內容 」），並該機碼內嵌在文件，並透過文件的版本仍然存在。 內容索引鍵受到組織的 RSA 金鑰 （「 Azure 資訊保護租用戶金鑰 」） 作為一部分文件中的原則和原則也簽署文件的作者。 此租用戶機碼是通用的所有文件和 Azure RMS 來保護組織的電子郵件，而此機碼可以只由 Azure 資訊保護系統管理員變更，如果組織使用是客戶管理租用戶金鑰。 如需 Azure RMS，所使用的密碼編譯控制項的詳細資訊，請參閱[Azure RMS 的運作方式？扣](https://docs.microsoft.com/information-protection/understand-explore/how-does-it-work)。

在預設的 Azure RMS 實作中，Microsoft 會產生並管理而言是唯一的每個承租人根機碼。 客戶可以使用一個稱為[攜帶您自己金鑰 (BYOK)](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)的金鑰管理方法來管理 Azure Key Vault 服務與 Azure RMS 中其根機碼的生命週期），可讓您在內部部署 Hsm 產生您的金鑰，並保持之後此機碼的控制轉接至 Microsoft 的 FIPS 140-2 層級 2 驗證 Hsm。 根機碼的存取不提供給任何人員無法匯出或進行保護硬體安全性模組從擷取的機碼。 此外，您可以存取 near 的即時記錄檔，以隨時顯示根機碼的所有存取。 如需詳細資訊，請參閱[記錄及分析的 Azure Rights Management 使用狀況](https://docs.microsoft.com/azure/information-protection/log-analyze-usage)。

Azure 版權管理可協助減少 wire-tapping、 等攔截攻擊、 資料遭竊的組織的共用原則預期違規的威脅。 在此同時，客戶資料的任何未經授權的存取傳輸中或未經授權的使用者不具備靜態將適當的權限無法透過原則資料，藉此降低風險的該資料落入錯誤傳遞下列一項巨集中接續有意或無意，並且提供資料遺失防護功能。 若使用 Azure 資訊保護的一部分，Azure RMS 也會提供資料的分類和標籤功能、 內容標示、 文件存取追蹤及存取撤銷功能。 若要深入了解這些功能，請參閱[什麼是 Azure 資訊保護](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)， [Azure 資訊保護部署藍圖](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap)和[Azure 資訊保護的快速入門教學課程](https://docs.microsoft.com/information-protection/get-started/infoprotect-quick-start-tutorial)。

## <a name="secure-multipurpose-internet-mail-extension"></a>安全多用途網際網路郵件延伸模組
安全多用途網際網路郵件延伸 (S/MIME) 是一種標準公開金鑰加密和 MIME 資料的數位簽章。 S/MIME 都會定義於 Rfc 3369 3370，3850、 3851，和其他應用程式。 它可讓使用者加密電子郵件，並以數位方式簽署電子郵件。 使用 S/MIME 加密的電子郵件僅可由使用其私密金鑰，也就是僅供該收件者的電子郵件的收件者。 如此之電子郵件無法解密的電子郵件的收件者以外的任何人。

[Microsoft 支援 Office 365 中的 S/MIME](http://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx)。 公用憑證會發佈到客戶的內部部署 Active Directory，而儲存在可以複寫至 Office 365 租用戶的屬性。 會對應至公開金鑰私密金鑰會保持內部部署，並永遠不會傳送至 Office 365。 使用者可以撰寫、 加密、 解密、 讀取、 並以數位方式簽署兩個使用者在組織中使用 Outlook、 Outlook web 和 Exchange ActiveSync 用戶端之間的電子郵件。 如需詳細資訊，請參閱 <<c0>現在在 Office 365 中的 S/MIME 加密。

## <a name="office-365-message-encryption"></a>Office 365 郵件加密
[Office 365 郵件加密](https://products.office.com/en-us/exchange/office-365-message-encryption)您可以傳送加密和權限保護郵件給任何人以[Azure 資訊保護](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)(AIP) 可讓基礎所建置 (OME)。 OME 減少 wire-tapping 等攔截攻擊威脅與其他威脅，例如未經授權的存取權之沒有適當的權限的未經授權使用者的資料。 我們已經以 Azure 資訊保護基礎所建置的簡單、 更具直覺性、 安全的電子郵件經驗為您提供的投資。 您可以保護從 Office 365 傳送給組織內外的任何人的郵件。 跨一套多樣化的郵件用戶端使用任何的身分識別，包括 Azure Active Directory、 Microsoft 帳戶及 Google 識別碼都能檢視這些郵件。 如需有關如何組織可以使用加密的郵件的詳細資訊，請參閱 < <b0>Office 365 郵件加密</b0>。

## <a name="transport-layer-security"></a>傳輸層安全性   
如果您想要確保與夥伴的安全通訊，您可以使用輸入和輸出連接器來提供安全性和訊息完整性。 您可以設定強制的輸入和輸出 TLS，每個連接器上使用憑證。 使用加密的 SMTP 通道可防止資料透過攔截攻擊遭竊取。 如需詳細資訊，請參閱[如何 Exchange Online 使用 TLS 來保護電子郵件連線](https://support.office.com/article/How-Exchange-Online-uses-TLS-to-secure-email-connections-in-Office-365-4CDE0CDA-3430-4DC0-B489-F2C0736C929F)。

## <a name="domain-keys-identified-mail"></a>網域金鑰所識別郵件
Exchange Online Protection (EOP) 和 Exchange Online 支援輸入的驗證的網域金鑰 Identified Mail (DKIM) 郵件。 DKIM 會驗證郵件已傳送從它說來自網域並不詐騙由其他人的方法。 它會繫結負責傳送它，組織將電子郵件訊息和電子郵件加密的較大典範的一部分。 如需有關此架構的三個部分的詳細資訊，請參閱：
- [在 Office 365 中設定 SPF 以協助防止詐騙](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)
- [使用 DKIM 驗證從您在 Office 365 中的自訂網域傳送的輸出電子郵件](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)
- [使用 DMARC 來驗證 Office 365 中的電子郵件](https://https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)
