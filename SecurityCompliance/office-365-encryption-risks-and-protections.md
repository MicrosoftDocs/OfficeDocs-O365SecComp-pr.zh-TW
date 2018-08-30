---
title: Office 365 加密風險與保護設定
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
ms.openlocfilehash: 69956c5f32f74a93b2101d2651ef7de03ad1094f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22527359"
---
# <a name="encryption-risks-and-protections"></a>加密風險與防護

Microsoft 接著重在 Office 365 服務以及客戶資料的風險的控制與規範架構。Microsoft 會實作技術和程序為基礎的方法 （稱為控制項） 一大組以減輕這類的風險。識別、 評估和減輕風險透過控制項是連續的程序。實作內各種我們雲端服務，例如設施、 網路、 伺服器、 應用程式、 使用者 （例如 Microsoft 系統管理員） 和資料層控制項的表單深入防禦策略。這項策略的關鍵是以防止相同或類似的風險案例的不同層級實作的許多不同的控制項。此多重分層的方法提供保全保護以防控制項無法因任何原因。以下列出一些風險案例及降低其目前無法加密技術。這些案例是在許多情況下也降低透過 Office 365 中實作其他控制項。

| 加密技術 | 服務 | 金鑰管理 | 風險案例 | 值 |
|----------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|---------------------|------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| BitLocker | Exchange Online、 SharePoint Online、 和 Skype for Business | Microsoft | 磁碟或伺服器中的 Office 365 竊取或不正確地回收。 | BitLocker 提供以防止因為竊或不正確地回收硬體 （伺服器/磁碟） 的資料遺失的保全方法。 |
| 服務加密 | SharePoint Online、 Skype for Business，以及 OneDrive for Business;Exchange Online （位於藍圖） | Microsoft | 內部或外部駭客嘗試存取個別檔案/資料為 blob。 | 將加密的資料無法解密沒有存取權。協助減輕駭客存取資料的風險。 |
| 客戶金鑰 | SharePoint Online、 OneDrive for Business、 Exchange Online 和 Skype for Business | 客戶 | N/A （這項功能的設計為規範功能 ； 沒有任何風險減輕方式）。 | 可協助客戶符合內部法規和規範義務並維持與 Office 365 服務和撤銷 Microsoft 的資料的存取權的能力 |
| Office 365 與用戶端之間的 TLS | Exchange Online、 SharePoint Online、 OneDrive for Business、 Business、 小組及 Yammer Skype | Microsoft、 客戶 | 在中間人或其他攻擊點選網際網路上的 Office 365 與用戶端電腦之間的資料流程。 | 這項實作提供值給 Microsoft 和客戶並為其流向為 Office 365 與用戶端之間可確保資料完整性。 |
| Microsoft 資料中心之間的 TLS | Exchange Online、 SharePoint Online、 OneDrive for Business 和 Skype for Business | Microsoft | 攔截或其他點選位於不同的 Microsoft 資料中心的 Office 365 伺服器之間的客戶資料流的攻擊。 | 這項實作是另一種方法來保護資料針對 Microsoft 資料中心間的攻擊。 |
| Azure 版權管理 （包含在 Office 365 或 Azure 資訊保護） | Exchange Online、 SharePoint Online，and OneDrive for Business | 客戶 | 資料可分為作業的不應有資料的存取權的人員。 | Azure 的資訊保護使用 Azure RMS 以提供值給客戶使用的加密、 identity 及授權的原則說明安全的檔案和電子郵件跨多個裝置。Azure RMS 提供值給其中所有電子郵件來自 Office 365 中符合特定準則 （亦即給特定地址的所有電子郵件） 可以自動加密之前所要取得傳送到另一個收件者的客戶。 |
| S/MIME | Exchange Online | 客戶 | 電子郵件可分為作業的未預定的收件者的人員。 | S/MIME 以確保使用 S/MIME 加密的電子郵件僅解密直接收件者的電子郵件，客戶提供值。 |
| Office 365 郵件加密 | Exchange Online、 SharePoint Online | 客戶 | 電子郵件，包括受保護的附件都屬於作業的人內或外部 Office 365 不是預定的收件者的電子郵件。 | OME 提供值給客戶其中所有電子郵件來自 Office 365 中符合特定準則 （亦即給特定地址的所有電子郵件） 會自動加密之前所要取得傳送至另一個內部或外部收件者。 |
| 與協力廠商組織的 SMTP TLS | Exchange Online | 客戶 | 電子郵件是透過從 Office 365 租用戶至另一個合作夥伴組織的傳送過程中的中間人或其他攻擊的攔截。 | 此案例會提供值給客戶如此他們可以傳送/接收其 Office 365 租用戶和加密的 SMTP 通道內的其合作夥伴電子郵件組織之間的所有電子郵件。 |

下表摘要說明在 Office 365 的多重租用戶和政府雲端社群環境中可用的加密技術。

| 加密技術 | 由實作 | 金鑰交換演算法和強度 | 金鑰管理 * | FIPS 140-2 驗證 |
|----------------------------------------------------------------------------------|-------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------|
| BitLocker | Exchange Online | AES 128 位元 + | AES 外部索引鍵儲存在密碼安全和 Exchange 伺服器的登錄中。秘密安全是需要高層級的權限提高及核准存取的安全存放庫。Access 可以要求並核准只能透過使用呼叫 Lockbox 內部工具。AES 外部索引鍵是也儲存在信任的平台模組中的伺服器。48 位數數字密碼會儲存在 Active Directory，並且受到 Lockbox。 | 是，使用之伺服器 AES 256 位元 * * |
|  | SharePoint Online | AES 256 位元 | AES 外部索引鍵儲存在密碼安全。秘密安全是需要高層級的權限提高及核准存取的安全存放庫。Access 可以要求並核准只能透過使用呼叫 Lockbox 內部工具。AES 外部索引鍵是也儲存在信任的平台模組中的伺服器。48 位數數字密碼會儲存在 Active Directory，並且受到 Lockbox。 | 是 |
|  | 商務用 Skype | AES 256 位元 | AES 外部索引鍵儲存在密碼安全。秘密安全是需要高層級的權限提高及核准存取的安全存放庫。Access 可以要求並核准只能透過使用呼叫 Lockbox 內部工具。AES 外部索引鍵是也儲存在信任的平台模組中的伺服器。48 位數數字密碼會儲存在 Active Directory，並且受到 Lockbox。 | 是 |
| 服務加密 | SharePoint Online | AES 256 位元 | 用來加密 blob 的機碼儲存在 SharePoint Online 內容資料庫。SharePoint Online 內容資料庫會受到資料庫的存取控制及靜態加密。使用 TDE Azure SQL 資料庫中執行加密。在 SharePoint Online、 不在租用戶層級的服務層級都是這些機密資料。（有時稱為主索引鍵） 這些機密資料儲存在稱為 「 機碼儲存在個別安全儲存機制。TDE 提供在作用中的資料庫和資料庫備份和交易記錄檔的其餘部分的安全性。當客戶提供選擇性的機碼時，客戶機碼儲存在 Azure 機碼存放庫，並服務使用按鍵來加密租用戶金鑰，這用來加密網站金鑰，然後用來加密檔案層級索引鍵。基本上時客戶提供金鑰, 已導入新的金鑰階層。 | 是 |
|  | 商務用 Skype | AES 256 位元 | 使用不同的隨機產生的 256 位元金鑰加密資料的每一個小細節。加密金鑰已儲存在相對應的中繼資料 XML 檔的也要加密以每個會議的主要金鑰。一次每次會議也會隨機產生主要金鑰。 | 是 |
|  | Exchange Online | AES 256 位元 | 使用資料加密原則使用控制由 Microsoft （位於藍圖） 或客戶 （當客戶機碼是） 的加密金鑰加密每個信箱。 | 是 |
| Office 365 與用戶端/協力廠商之間的 TLS | Exchange Online | [支援多個編碼器套件的隨機 TLS](https://technet.microsoft.com/en-us/library/mt163898.aspx) | Exchange Online (outlook.office.com) 的 TLS 憑證是由巴爾的摩 CyberTrust 根發出 2048年位元 SHA256RSA 憑證。 | [是]、 具有 256 位元加密強度的 TLS 1.2 時 |
|  |  |  | Exchange Online 的 TLS 根憑證是由巴爾的摩 CyberTrust 根發出 2048年位元 SHA1RSA 憑證。 |  |
|  | SharePoint Online | 使用 AES 256 TLS 1.2 版 | SharePoint Online 的 TLS 憑證 (*。 sharepoint.com) 是由巴爾的摩 CyberTrust 根發出 2048年位元 SHA256RSA 憑證。 | 是 |
|  |  | [商務用 OneDrive 和 SharePoint Online 中的資料加密](https://technet.microsoft.com/en-us/library/dn905447.aspx) (英文) | SharePoint Online 的 TLS 根憑證是由巴爾的摩 CyberTrust 根發出 2048年位元 SHA1RSA 憑證。 |  |
|  | 商務用 Skype | [TLS 進行 SIP 通訊和 PSOM 資料共用工作階段](https://support.office.com/article/Set-up-your-network-for-Skype-for-Business-Online-d21f89b0-3afc-432e-b735-036b2432fdbf) | Skype for Business 的 TLS 憑證 (*。 建立與 lync.com) 是由巴爾的摩 CyberTrust 根發出 2048年位元 SHA256RSA 憑證。 | 是 |
|  |  |  | Skype for Business 的 TLS 根憑證是由巴爾的摩 CyberTrust 根發出 2048年位元 SHA256RSA 憑證。 |  |
|  | Microsoft Teams | 使用 AES 256 TLS 1.2 版 | （teams.microsoft.com、 edge.skype.com） 的 Microsoft 小組的 TLS 憑證是由巴爾的摩 CyberTrust 根發出 2048年位元 SHA256RSA 憑證。 | 是 |
|  |  | [常見問題集相關的 Microsoft 小組 – 系統說明](https://docs.microsoft.com/MicrosoftTeams/teams-overview) | Microsoft 小組的 TLS 根憑證是由巴爾的摩 CyberTrust 根發出 2048年位元 SHA256RSA 憑證。 |  |
| Microsoft 資料中心之間的 TLS | 所有的 Office 365 服務 | 使用 AES 256 TLS 1.2 版 | Microsoft 會使用內部受管理及部署的憑證授權單位的 Microsoft 資料中心間的伺服器對伺服器通訊。 | 是 |
|  |  | 安全即時傳輸通訊協定 (SRTP) |  |  |
| Azure 版權管理 （包含在 Office 365 或 Azure 資訊保護） | Exchange Online | 支援[密碼編譯模式 2](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))、 更新及增強 RMS 密碼編譯實作。它支援 RSA 2048 簽章和加密，並且 SHA-1 256 中簽章的雜湊。 | [受管理的 microsoft](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。 | 是 |
|  | SharePoint Online | 支援[密碼編譯模式 2](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))、 更新及增強 RMS 密碼編譯實作。它支援 RSA 2048 的簽章和加密，以及 SHA-1 256 個簽章。 | [受管理的 microsoft](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)，這是預設的設定 ；或 | 是 |
|  |  |  | 這是 Microsoft managed 金鑰另一種替代客戶管理。具有受 IT 管理 Azure 訂閱的組織可以使用 BYOK 並記錄在沒有額外收費及其使用方式。如需詳細資訊，請參閱 ＜[將您自己的金鑰的實作](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。在此組態中，Thales Hsm 來保護您的機碼。如需詳細資訊，請參閱[Thales Hsm 和 Azure RMS](http://www.thales-esecurity.com/msrms/cloud)。 |  |
| S/MIME | Exchange Online | 密碼編譯訊息語法標準 1.5 (PKCS #7) | 客戶管理公開金鑰基礎結構部署而定。金鑰管理由客戶、 執行和 Microsoft 永遠不會有權存取私密金鑰用於簽署及解密。 | 是，設定來加密 3DES 或 AES256 的外寄郵件時 |
| Office 365 郵件加密 | Exchange Online | Azure RMS ([密碼編譯模式 2](https://technet.microsoft.com/en-us/library/dn569290.aspx) -簽章和加密的 RSA 2048 和 SHA-1 256 個簽章) 相同 | 使用 Azure 資訊保護做為其加密基礎結構。使用的加密方法取決於您用來取得用來加密和解密的郵件的 RMS 金鑰。 | 是 |
| 與協力廠商組織的 SMTP TLS | Exchange Online | 使用 AES 256 TLS 1.2 版 | Exchange Online (outlook.office.com) 的 TLS 憑證是由巴爾的摩 CyberTrust 根發出 2048年位元 SHA256RSA 憑證。 | [是]、 具有 256 位元加密強度的 TLS 1.2 時 |
|  |  |  | Exchange Online 的 TLS 根憑證是由巴爾的摩 CyberTrust 根發出 2048年位元 SHA1RSA 憑證。 |  |

**此表格中所參照的 TLS 憑證是為 US 資料中心;非 US 資料中心也會使用 2048年位元 SHA256RSA 憑證。*

***Exchange Online 的多租用戶環境中大部分的伺服器已部署與 BitLocker AES 256 位元加密。使用 AES 128 位元的伺服器已被淘汰。*

| 加密技術 | 由實作 | 金鑰交換演算法和強度 | 金鑰管理 * | FIPS 140-2 驗證 |
|---------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------|
| BitLocker | Exchange Online | AES 256 位元 | AES 外部索引鍵儲存在密碼安全和 Exchange 伺服器的登錄中。秘密安全是需要高層級的權限提高及核准存取的安全存放庫。Access 可以要求並核准只能透過使用呼叫 Lockbox 內部工具。AES 外部索引鍵是也儲存在信任的平台模組中的伺服器。48 位數數字密碼會儲存在 Active Directory，並且受到 Lockbox。 | 是 |
|  | SharePoint Online | AES 256 位元 | AES 外部索引鍵儲存在密碼安全。秘密安全是需要高層級的權限提高及核准存取的安全存放庫。Access 可以要求並核准只能透過使用呼叫 Lockbox 內部工具。AES 外部索引鍵是也儲存在信任的平台模組中的伺服器。48 位數數字密碼會儲存在 Active Directory，並且受到 Lockbox。 | 是 |
|  | 商務用 Skype | AES 256 位元 | AES 外部索引鍵儲存在密碼安全。秘密安全是需要高層級的權限提高及核准存取的安全存放庫。Access 可以要求並核准只能透過使用呼叫 Lockbox 內部工具。AES 外部索引鍵是也儲存在信任的平台模組中的伺服器。48 位數數字密碼會儲存在 Active Directory，並且受到 Lockbox。 | 是 |
| 服務加密 | SharePoint Online | AES 256 位元 | 用來加密 blob 的機碼儲存在 SharePoint Online 內容資料庫。SharePoint Online 內容資料庫會受到資料庫的存取控制及靜態加密。使用 TDE Azure SQL 資料庫中執行加密。在 SharePoint Online、 不在租用戶層級的服務層級都是這些機密資料。（有時稱為主索引鍵） 這些機密資料儲存在稱為 「 機碼儲存在個別安全儲存機制。TDE 提供在作用中的資料庫和資料庫備份和交易記錄檔的其餘部分的安全性。當客戶提供選擇性的機碼時，客戶機碼儲存在 Azure 機碼存放庫，並服務使用按鍵來加密租用戶金鑰，這用來加密網站金鑰，然後用來加密檔案層級索引鍵。基本上時客戶提供金鑰, 已導入新的金鑰階層。 | 是 |
|  | 商務用 Skype | AES 256 位元 | 使用不同的隨機產生的 256 位元金鑰加密資料的每一個小細節。加密金鑰已儲存在相對應的中繼資料 XML 檔的也要加密以每個會議的主要金鑰。一次每次會議也會隨機產生主要金鑰。 | 是 |
|  | Exchange Online | AES 256 位元 | 使用資料加密原則使用控制由 Microsoft 或客戶 （當客戶機碼是） 的加密金鑰加密每個信箱。 | 是 |
| Office 365 與用戶端/協力廠商之間的 TLS | Exchange Online | [支援多個編碼器套件的隨機 TLS](https://technet.microsoft.com/en-us/library/mt163898.aspx) | Exchange Online (outlook.office.com) 的 TLS 憑證是由巴爾的摩 CyberTrust 根發出 2048年位元 SHA256RSA 憑證。 | [是]、 具有 256 位元加密強度的 TLS 1.2 時 |
|  |  |  | Exchange Online 的 TLS 根憑證是由巴爾的摩 CyberTrust 根發出 2048年位元 SHA1RSA 憑證。 |  |
|  | SharePoint Online | 使用 AES 256 TLS 1.2 版 | SharePoint Online 的 TLS 憑證 (*。 sharepoint.com) 是由巴爾的摩 CyberTrust 根發出 2048年位元 SHA256RSA 憑證。 | 是 |
|  |  |  | SharePoint Online 的 TLS 根憑證是由巴爾的摩 CyberTrust 根發出 2048年位元 SHA1RSA 憑證。 |  |
|  | 商務用 Skype | TLS 進行 SIP 通訊和 PSOM 資料共用工作階段 | Skype for Business 的 TLS 憑證 (*。 建立與 lync.com) 是由巴爾的摩 CyberTrust 根發出 2048年位元 SHA256RSA 憑證。 | 是 |
|  |  |  | Skype for Business 的 TLS 根憑證是由巴爾的摩 CyberTrust 根發出 2048年位元 SHA256RSA 憑證。 |  |
|  | Microsoft Teams | [常見問題集相關的 Microsoft 小組 – 系統說明](https://docs.microsoft.com/MicrosoftTeams/teams-overview) | （teams.microsoft.com ； edge.skype.com） 的 Microsoft 小組的 TLS 憑證是由巴爾的摩 CyberTrust 根發出 2048年位元 SHA256RSA 憑證。 | 是 |
|  |  |  | Microsoft 小組的 TLS 根憑證是由巴爾的摩 CyberTrust 根發出 2048年位元 SHA256RSA 憑證。 |  |
| Microsoft 資料中心之間的 TLS | Exchange Online、 SharePoint Online、 Skype for Business | 使用 AES 256 TLS 1.2 版 | Microsoft 會使用內部受管理及部署的憑證授權單位的 Microsoft 資料中心間的伺服器對伺服器通訊。 | 是 |
|  |  | 安全即時傳輸通訊協定 (SRTP) |  |  |
| Azure 版權管理服務 | Exchange Online | 支援[密碼編譯模式 2](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))、 更新及增強 RMS 密碼編譯實作。它支援 RSA 2048 簽章和加密，並且 SHA-1 256 中簽章的雜湊。 | [受管理的 microsoft](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。 | 是 |
|  | SharePoint Online | 支援[密碼編譯模式 2](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))、 更新及增強 RMS 密碼編譯實作。它支援 RSA 2048 簽章和加密，並且 SHA-1 256 中簽章的雜湊。 | [受管理的 microsoft](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)，這是預設的設定 ；或 | 是 |
|  |  |  | 客戶 managed (亦即 BYOK) 這是 Microsoft managed 金鑰的替代方式。具有受 IT 管理 Azure 訂閱的組織可以使用 BYOK 並記錄在沒有額外收費及其使用方式。如需詳細資訊，請參閱 ＜[將您自己的金鑰的實作](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。 |  |
|  |  |  | 在 BYOK 案例中，Thales Hsm 可用來保護您的機碼。如需詳細資訊，請參閱[Thales Hsm 和 Azure RMS](http://www.thales-esecurity.com/msrms/cloud)。 |  |
| S/MIME | Exchange Online | 密碼編譯訊息語法標準 1.5 (PKCS #7) | 公開金鑰基礎結構部署而定。 | 是，設定來加密 3DES 或 AES 256 的外寄郵件時。 |
| Office 365 郵件加密 | Exchange Online | Azure RMS ([密碼編譯模式 2](https://technet.microsoft.com/en-us/library/dn569290.aspx) -簽章和加密的 RSA 2048 和 SHA-1 256 的簽章的雜湊) 相同 | 使用 Azure RMS 做為其加密基礎結構。使用的加密方法取決於您用來取得用來加密和解密的郵件的 RMS 金鑰。 | 是 |
|  |  |  | 如果您使用 Microsoft Azure RMS 取得金鑰，則會使用密碼編譯模式 2。如果您使用 Active Directory (AD) RMS 取得金鑰時，會使用密碼編譯模式 1 或密碼編譯模式 2。使用的方法取決於您內部部署 AD RMS 部署。原始的 AD RMS 密碼編譯實作密碼編譯模式 1。它可用於簽章和加密支援 RSA 1024 和支援 sha-1 的簽章。此模式會繼續以 RMS，但不包括使用 Hsm 的 BYOK 設定的所有目前的版本都受到支援。 |  |
| 與協力廠商組織的 SMTP TLS | Exchange Online | 使用 AES 256 TLS 1.2 版 | Exchange Online (outlook.office.com) 的 TLS 憑證是由巴爾的摩 CyberTrust 根發出 2048年位元 SHA256RSA 憑證。 | 是 |
|  |  |  | Exchange Online 的 TLS 根憑證是由巴爾的摩 CyberTrust 根發出 2048年位元 sha1RSA 憑證。 |  |
|  |  |  | *請注意基於安全性理由，我們憑證不要變更的時候。* |  |

**此表格中所參照的 TLS 憑證是為 US 資料中心;非 US 資料中心也會使用 2048年位元 SHA256RSA 憑證。*