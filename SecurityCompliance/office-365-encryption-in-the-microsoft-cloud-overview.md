---
title: Microsoft Cloud 中的加密
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
description: Microsoft 雲端中加密的概觀。
ms.openlocfilehash: b8dee7ca7a791878763b885ada40a1d87f074e8e
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22527171"
---
# <a name="encryption-in-the-microsoft-cloud"></a>Microsoft Cloud 中的加密

Microsoft 的企業雲端服務內的客戶資料會受到各種技術和處理程序，包括各種形式的加密。(此文件中的 office 365 客戶資料包括 Exchange Online 信箱內容 (電子郵件內文、 行事曆項目及電子郵件附件的內容及如果有的話，Skype 商務內容)、 SharePoint Online 網站內容及檔案內儲存網站及檔案上傳至 OneDrive 商務或 Skype for Business。）Microsoft 會使用多個加密方法、 通訊協定及 cipher 跨其產品和服務來提供旅行社透過我們雲端服務，並協助保護內儲存的客戶資料的機密性的客戶資料的安全路徑我們雲端服務。Microsoft 會使用一些可用來提供障礙對抗未經授權存取權的客戶資料的最強、 最安全的加密通訊協定。適當的金鑰管理也是必要元素的加密最佳作法，以及 Microsoft 適用於以確保正確保護所有 Microsoft 管理加密金鑰。

不論客戶設定儲存在 Microsoft 的企業雲端服務中的客戶資料使用的加密的一或多個表單保護。（多個協力廠商 auditors 單獨檢定的我們加密的原則和其強制執行驗證和[服務信任入口網站](https://aka.ms/stp)上可用的那些稽核報告）。

Microsoft 提供服務端加密靜態及傳送過程中的客戶資料的技術。例如，靜態的客戶資料，Microsoft Azure 使用[BitLocker](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview)和[性資料採擷窖](https://en.wikipedia.org/wiki/Dm-crypt)，與 Microsoft Office 365 使用 BitLocker、 [Azure Storage Service 加密](https://azure.microsoft.com/documentation/articles/storage-service-encryption/)、[分散式金鑰管理員](https://support.office.com/article/989ba10c-f73f-4efb-ad1b-af3322e5f376)(DKM) 及 Office 365 服務加密。傳送過程中的客戶資料、 Azure、 Office 365、 Microsoft 商業支援、 Microsoft Dynamics 365、 Microsoft Power BI、 及 Visual Studio Team Services 使用業界標準安全傳輸通訊協定，例如網際網路通訊協定安全性 (IPsec) 和Microsoft 資料中心之間及使用者裝置與 Microsoft 資料中心間傳輸層安全性 (TLS)。

除了 Microsoft 提供的密碼編譯安全性的基準層級，我們雲端服務也包含可管理的其他密碼編譯選項。例如，您可以啟用加密其 Azure 虛擬機器 (Vm) 和其使用者之間的流量。搭配[Azure 虛擬網路](https://azure.microsoft.com/services/virtual-network/)，您可以使用的業界標準 IPsec 通訊協定來加密之間您公司的 VPN 閘道和 Azure 也例如在 Vm 位於虛擬網路之間的流量。此外，此外， [Office 365 郵件加密的新功能](set-up-new-message-encryption-capabilities.md)可讓您將加密的郵件傳送給任何人。

「 公用金鑰基礎結構運作安全性標準，這是[Microsoft 安全性原則](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5868ecc8-50b7-4f91-b43f-640e2b99e86e&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ%20and%20White%20Papers)元件、 Microsoft 如何運用 Windows 作業系統的憑證中所含的密碼編譯功能和驗證機制，其中包含使用符合美國政府[美國聯邦資訊處理標準](http://csrc.nist.gov/publications/PubsFIPS.html)(FIPS) 140-2 標準的密碼編譯模組。（如 Microsoft 相關 NIST 憑證號碼可找到http://csrc.nist.gov/groups/STM/cmvp/documents/140-1/1401vend.htm.)

> [記事]若要存取當成資源的 Microsoft 安全性原則，您必須使用登入工作或學校帳戶。如果您不需要訂閱尚未，[您可以註冊免費的試用版](https://servicetrust.microsoft.com/Home/TrialSubscriptions)。

FIPS 140-2 是特別為驗證產品模組中實作密碼編譯而不是使用這些產品設計的標準。密碼編譯服務內實作的模組可以認證作為會議雜湊強度、 金鑰管理和類似的需求。密碼編譯功能會採用保護機密性、 完整性或 Microsoft cloud services] 中的資料的可用性任何時候模組和 cipher 用符合 FIPS 140-2 標準。

Microsoft 需要認證中每個新版本的 Windows 作業系統與我們雲端服務所使用的基礎密碼編譯模組：
- Azure 及 Azure 美國政府
- Dynamics 365 和 Dynamics 365 美國政府
- Office 365、 Office 365 美國政府和 Office 365 美國政府防禦

Office 365 客戶靜態資料的加密所提供多個服務端技術，包括 BitLocker、 DKM、 Azure Storage Service 加密，以及服務加密在 Exchange Online、 Skype for Business、 OneDrive for Business 和 SharePoint線上。Office 365 服務加密包含使用 Azure 機碼存放庫中所儲存的客戶管理加密金鑰] 選項。此客戶 managed 金鑰] 選項，呼叫[Office 365 客戶機碼](https://support.office.com/article/f2cd475a-e592-46cf-80a3-1bfb0fa17697)，為適用於 Exchange Online、 SharePoint Online、 Skype for Business 及 OneDrive for Business。

客戶資料傳送過程中，Office 365 的所有伺服器會都交涉安全安全客戶資料與用戶端機器使用 TLS 預設的工作階段。 這適用於用戶端，例如 Skype for Business、 Outlook 和 Outlook web、 行動用戶端和網頁瀏覽器上的使用任何裝置上的通訊協定。

（客戶使用的所有伺服器預設會都交涉 TLS 1.2 至但我們也支援交涉下的較低的標準，如有需要）。

## <a name="related-links"></a>相關的連結

- [Azure 中的加密](office-365-azure-encryption.md)
- [BitLocker 與 Distributed Key Manager (DKM) 的加密](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)
- [Office 365 服務加密](office-365-service-encryption.md)
- [Skype for Business、 OneDrive for Business、 SharePoint Online、 and Exchange Online 的 office 365 加密](office-365-encryption-for-skype-onedrive-sharepoint-and-exchange.md)
- [傳輸中資料的加密](office-365-encryption-for-data-in-transit.md)
- [客戶管理加密功能](office-365-customer-managed-encryption-features.md)
- [加密風險與防護](office-365-encryption-risks-and-protections.md)
- [Microsoft Dynamics 365 中的加密](office-365-encryption-in-microsoft-dynamics-365.md)