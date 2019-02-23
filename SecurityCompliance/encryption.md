---
title: Office 365 中的加密
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/3/2018
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.assetid: 0a322724-08ca-43db-b69a-afbfa20484cd
description: Office 365 的靜態及傳輸，使用最強大的加密、 通訊協定及可用的技術加密您的內容。取得 Office 365 加密的概觀。
ms.openlocfilehash: 6371bc7fabfccfca30d1e8fec94d4f22c1c6f492
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223662"
---
# <a name="encryption-in-office-365"></a>Office 365 中的加密

加密是檔案的保護和資訊保護策略中重要的一部分。閱讀本篇文章以取得所有版本的 Office 365 所都使用的加密的概觀及取得從您的組織密碼保護的 Office 文件的加密設定的加密工作的說明。
  
- 如果您正在尋找憑證與 TLS 技術的資訊，請參閱[Office 365 中加密的相關的技術參考 （英文） 詳細資料](technical-reference-details-about-encryption.md)。
    
- 如果您要尋找有關如何設定或組織的加密設定的資訊，請參閱[Office 365 企業版中的加密設定](set-up-encryption.md)。
    
## <a name="what-is-encryption-and-how-does-it-work-in-office-365"></a>什麼是加密，以及它的運作方式在 Office 365？

在高層級中，加密是編碼 （稱為純文字） 資料的程序將無法在除非及解密加密文字前人員或電腦所使用的加密文字。解密需要授權的使用者擁有的加密金鑰。加密有助於確保僅授權的收件者可以解密您的內容，例如電子郵件和檔案。
  
加密本身不防止內容，例如檔案、 電子郵件、 行事曆項目等等錯誤送到快速。加密是您的組織更大的資訊保護策略的一部分。使用加密有助於確保只應該能夠使用加密的資料的人能夠。
  
您可以已經備妥的多層的加密在同一時間。例如，您可以將加密的電子郵件以及透過電子郵件流程的通訊通道。您的資料與 Office 365 加密靜態及傳輸，使用數個強式加密通訊協定及包括傳輸層安全性/安全通訊端階層 (TLS/SSL)、 網際網路通訊協定安全性 (IPSec) 和進階加密的技術標準 (AES)。
  
## <a name="encryption-for-data-at-rest-and-data-in-transit"></a>靜態資料和傳輸的資料的加密

 **靜態資料的範例**包括已上傳至 SharePoint 文件庫、 Project Online 資料、 商務會議、 電子郵件訊息與儲存在您的 Office 365 中的資料夾中的附件 Skype 中已上載的文件的檔案mailbox 及上傳至 OneDrive for Business 的檔案。 
  
 **傳輸的資料的範例**包括正在會傳遞的郵件訊息或進行線上會議中的交談。Office 365 中的資料是傳送過程中每當使用者裝置與 Office 365 伺服器通訊，或 Office 365 伺服器與另一部伺服器通訊時。 
  
與 Office 365，您可以有多個層級和種類的加密來保護您的資料一起使用。下表包含一些範例，並提供其他資訊連結。
  
|**種類的內容**|**加密技術**|**若要深入了解的資源**|
|:-----|:-----|:-----|
|在裝置上的檔案。它可以包含儲存在資料夾、 Office 文件儲存在電腦上、 平板電腦或電話或資料儲存至 Microsoft 雲端中的電子郵件訊息。  <br/> |在 Microsoft 資料中心中的 BitLocker。BitLocker 也可以使用用戶端機器，例如 Windows 電腦與平板電腦上  <br/> 在 Microsoft 資料中心中的分散式金鑰管理員 (DKM)  <br/> Office 365 的客戶機碼  <br/> |[Windows IT 中心： BitLocker](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview) <br/> [Microsoft 信任中心： 加密](https://www.microsoft.com/en-us/TrustCenter/Security/Encryption) <br/> [雲端安全性控制 series： 靜態加密資料](https://blogs.microsoft.com/microsoftsecure/2015/09/10/cloud-security-controls-series-encrypting-data-at-rest) <br/> [Exchange Online 如何保護您的電子郵件機密資料](exchange-online-secures-email-secrets.md) <br/> [使用客戶金鑰控制 Office 365 中的資料](controlling-your-data-using-customer-key.md) <br/> |
|部署使用者之間傳送過程中的檔案。它可以包含 Office 文件或使用者之間共用的 SharePoint 清單項目。  <br/> |TLS 傳送過程中的檔案  <br/> |[商務用 OneDrive 和 SharePoint Online 中的資料加密](data-encryption-in-odb-and-spo.md) (英文) <br/> [Skype for Business 線上： 安全性和封存](https://technet.microsoft.com/library/skype-for-business-online-security-and-archiving.aspx) <br/> |
|電子郵件收件者之間傳送過程中。這包括主控的 Exchange Online 電子郵件。  <br/> |Azure 版權管理、 S/MIME 與 TLS 的電子郵件傳送過程中的 office 365 郵件加密  <br/> |[Office 365 郵件加密 (OME)](ome.md) <br/> [Office 365 中的電子郵件加密](email-encryption.md) <br/> [Exchange Online 如何使用 TLS 來保護 Office 365 中的電子郵件連線](exchange-online-uses-tls-to-secure-email-connections.md) <br/> |
   
## <a name="what-if-i-need-more-control-over-encryption-to-meet-security-and-compliance-requirements"></a>如果需要更多控制透過加密以符合安全性及規範需求吗？

除了 Microsoft 管理解決方案的磁碟區加密、 檔案加密，以及 Office 365 中的信箱加密客戶管理選項可用來符合更嚴格的安全性及規範需求。這類解決方案會使用與 Office 365 搭配 Azure 版權管理 (Azure RMS)。
  
請參閱下列資源以深入了解：
  
- [Azure 版權管理新功能](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)
    
- [在 Office 365 系統管理中心啟動版權管理](https://support.office.com/article/5b6d3ac7-b1ac-428e-b03e-50e882f85a6e)
    
- [Set up Information Rights Management (IRM) in SharePoint admin center](set-up-irm-in-sp-admin-center.md)
    
## <a name="how-do-i"></a>How do I...]

|**若要這項工作**|**請參閱下列資源**|
|:-----|:-----|
|設定 「 我的組織的加密  <br/> |[設定 Office 365 企業版中的加密](set-up-encryption.md) <br/> |
|Office 365 中檢視詳細的憑證、 技術及 TLS 加密套件  <br/> |[關於 Office 365 中加密的技術詳細資料](technical-reference-details-about-encryption.md) <br/> |
|在行動裝置上使用加密的郵件  <br/> |[Android 裝置上檢視加密的郵件](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> [在 iPhone 或 iPad 上檢視加密的郵件](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |
|加密使用密碼保護的文件  <br/><br/>  目前 Office Online 中不支援密碼保護。使用桌面版本的 Word、 Excel 及 PowerPoint 的密碼保護。           |[文件、 活頁簿或簡報中新增或移除保護](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826)（選擇 [**新增保護**] 區段中，且會看到 [**以密碼加密]** ）  <br/> |
|移除文件的加密  <br/> |[文件、 活頁簿或簡報中新增或移除保護](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826)（選擇**移除保護**] 區段中，且會看到 [**移除密碼加密**）  <br/> |
   
## <a name="related-topics"></a>相關主題

[規劃 Office 365 安全性和資訊保護功能](https://support.office.com/article/3d4ac4a1-3920-4ff9-918f-011f3ce60408)
  
[安全性與 Office 365 中的商務-Admin 說明規範](https://support.office.com/article/7fe448f7-49bd-4d3e-919d-0a6d1cf675bb)
  

