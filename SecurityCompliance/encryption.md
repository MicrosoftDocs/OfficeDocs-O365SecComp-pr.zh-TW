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
search.appverid:
- MET150
- MOE150
ms.assetid: 0a322724-08ca-43db-b69a-afbfa20484cd
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: 使用 Office 365，您的內容加密靜態及在傳輸，使用最強加密、 通訊協定，以及可用的技術。 在 Office 365 中取得加密的概觀。
ms.openlocfilehash: 7a73d3d3b24e28f8795ec93ac05dbc383b525906
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32256671"
---
# <a name="encryption-in-office-365"></a>Office 365 中的加密

加密是檔案保護和資訊保護策略中重要的一部分。 閱讀本篇文章以取得用於所有版本的 Office 365 加密的概觀，並從您的組織的密碼保護的 Office 文件的加密設定取得加密工作的說明。
  
- 如果您正在尋找憑證和技術，例如 TLS 的相關資訊，請參閱[關於 Office 365 中加密的技術參考細節](technical-reference-details-about-encryption.md)。

- 如果您要尋找有關如何設定或組織的加密設定的資訊，請參閱 <<c0>設定 Office 365 企業版中的加密。

## <a name="what-is-encryption-and-how-does-it-work-in-office-365"></a>什麼是加密，以及它如何運作的 Office 365？

在高的層級，加密是編碼 （稱為純文字） 資料的程序到亦無法使用的人員或電腦中，除非和直到解密加密文字。 解密需要授權的使用者擁有的加密金鑰。 加密有助於確保只有授權的收件者才能解密內容，例如電子郵件和檔案。
  
加密本身無法防止內容，例如檔案、 電子郵件、 行事曆項目，等等，進入一面。 加密是您的組織更大的資訊保護策略的一部分。 藉由使用加密，您可以協助確保只應該能夠使用加密的資料的人都能夠。
  
您可以在同一時間，就地有多層的加密。 例如，您可以將加密的電子郵件也經過流向您的電子郵件的通訊通道。 您的資料與 Office 365 加密靜態及在傳輸，使用多個強式的加密通訊協定和技術，包括傳輸層安全性/安全通訊端階層 (TLS/SSL)、 網際網路通訊協定安全性 (IPSec)，以及進階加密標準 (AES)。
  
## <a name="encryption-for-data-at-rest-and-data-in-transit"></a>靜態資料和傳輸中的資料加密

 **靜態資料的範例**包括已上傳至 SharePoint 文件庫、 Project Online 資料、 skype for Business 會議、 電子郵件訊息和附件儲存在您的 Office 365 中的資料夾中已上載的文件的檔案信箱，並上傳到商務用 OneDrive 檔案。 
  
 **傳輸中資料的範例**包括正在正在傳遞的郵件會發生在線上會議中的交談。 在 Office 365 中，資料是在傳輸途中每當使用者的裝置與 Office 365 伺服器通訊，或 Office 365 伺服器通訊與另一部伺服器時。 
  
使用 Office 365，您可以有多個圖層與幾種類型的加密來保護您的資料一起運作。 下表包含一些範例，與其他資訊連結。
  
|**種類的內容**|**加密技術**|**若要了解更多的資源**|
|:-----|:-----|:-----|
|在裝置上的檔案。 這可以包含的資料夾，儲存在電腦、 平板電腦或手機上的 Office 文件或資料儲存至 Microsoft 雲端中儲存的電子郵件訊息。  <br/> |在 Microsoft 資料中心中的 BitLocker。 BitLocker 也可用於用戶端機器，例如 Windows 電腦和平板電腦  <br/> 在 Microsoft 資料中心中的分散式金鑰管理員 (DKM)  <br/> Office 365 的客戶金鑰  <br/> |[Windows IT 中心： BitLocker](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview) <br/> [Microsoft 信任中心： 加密](https://www.microsoft.com/en-us/TrustCenter/Security/Encryption) <br/> [雲端安全性控制系列： 靜態加密資料](https://blogs.microsoft.com/microsoftsecure/2015/09/10/cloud-security-controls-series-encrypting-data-at-rest) <br/> [Exchange Online 如何保護您的電子郵件機密資料](exchange-online-secures-email-secrets.md) <br/> [使用客戶金鑰控制 Office 365 中的資料](controlling-your-data-using-customer-key.md) <br/> |
|在使用者間傳輸的檔案。 這可以包含 Office 文件或使用者之間共用的 SharePoint 清單項目。  <br/> |TLS 傳輸中的檔案  <br/> |[商務用 OneDrive 和 SharePoint Online 中的資料加密](data-encryption-in-odb-and-spo.md) (英文) <br/> [線上商務用 Skype： 安全性和封存](https://technet.microsoft.com/library/skype-for-business-online-security-and-archiving.aspx) <br/> |
|收件者之間傳送的電子郵件。 這包括 Exchange online 託管的電子郵件。  <br/> |Azure 版權管理、 S/MIME 與 TLS 傳輸中的電子郵件的 office 365 郵件加密  <br/> |[Office 365 郵件加密 (OME)](ome.md) <br/> [Office 365 中的電子郵件加密](email-encryption.md) <br/> [Exchange Online 如何使用 TLS 來保護 Office 365 中的電子郵件連線](exchange-online-uses-tls-to-secure-email-connections.md) <br/> |

## <a name="what-if-i-need-more-control-over-encryption-to-meet-security-and-compliance-requirements"></a>如果我需要更多控制加密以符合安全性與合規性需求？

Microsoft 受管理的磁碟區加密、 檔案加密，以及 Office 365 中的信箱加密解決方案，除了客戶管理選項可用來符合更嚴格的安全性與合規性需求。 這類解決方案會使用與 Office 365 的 Azure 版權管理 (Azure RMS)。
  
請參閱若要了解更多的下列資源：
  
- [什麼是 Azure 版權管理？](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)

- [在 Office 365 系統管理中心啟動版權管理](https://support.office.com/article/5b6d3ac7-b1ac-428e-b03e-50e882f85a6e)

- [Set up Information Rights Management (IRM) in SharePoint admin center](set-up-irm-in-sp-admin-center.md)

## <a name="how-do-i"></a>我要如何...

|**若要此工作**|**請參閱這些資源**|
|:-----|:-----|
|設定我的組織的加密  <br/> |[設定 Office 365 企業版中的加密](set-up-encryption.md) <br/> |
|在 Office 365 中檢視詳細資料的憑證、 技術及 TLS 加密套件  <br/> |[關於 Office 365 中加密的技術詳細資料](technical-reference-details-about-encryption.md) <br/> |
|使用行動裝置上的已加密郵件  <br/> |[在 Android 裝置上檢視加密的郵件](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> [在 iPhone 或 iPad 上檢視加密的郵件](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |
|加密文件使用密碼保護  <br/><br/>  目前，在 Office Online 中不支援密碼保護。 使用桌上型版本的 Word、 Excel 及 PowerPoint 的密碼保護。           |[文件、 活頁簿或簡報中新增或移除保護](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826)（選擇 [**新增保護**] 區段中，並再查看 [**以密碼加密]** ）  <br/> |
|移除文件的加密  <br/> |[文件、 活頁簿或簡報中新增或移除保護](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826)（選擇**移除保護**] 區段中，並再查看 [**移除密碼加密**）  <br/> |

## <a name="related-topics"></a>相關主題

[規劃 Office 365 安全性和資訊保護功能](https://support.office.com/article/3d4ac4a1-3920-4ff9-918f-011f3ce60408)
  
[安全性與合規性 Office 365 商務版-系統管理說明](https://support.office.com/article/7fe448f7-49bd-4d3e-919d-0a6d1cf675bb)
  

