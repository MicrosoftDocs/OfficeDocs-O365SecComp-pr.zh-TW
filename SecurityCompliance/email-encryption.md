---
title: Office 365 中的電子郵件加密
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c0d87cbe-6d65-4c03-88ad-5216ea5564e8
description: 比較 Office 365 包括 Office 郵件加密 (OME)、 S/MIME、 資訊版權管理 (IRM) 中的加密方式並了解傳輸層安全性 (TLS)。
ms.openlocfilehash: a6db6c9cf6af180fe84e955613fb6b1175ee0747
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995354"
---
# <a name="email-encryption-in-office-365"></a>Office 365 中的電子郵件加密

本文會比較 Office 365 包括 Office 郵件加密 (OME)、 S/MIME、 資訊版權管理 (IRM) 中的加密選項並介紹傳輸層安全性 (TLS)。
  
Office 365 提供可協助您滿足業務需求的電子郵件安全性的多個加密選項。本文提供三種方式來加密 Office 365 中的電子郵件。若要深入了解 Office 365 中的所有安全性功能，請造訪[Office 365 信任中心](http://go.microsoft.com/fwlink/p/?LinkID=282470)。本文介紹加密說明 Office 365 中的安全電子郵件的 Office 365 管理員可使用三種類型：
  
- Office 郵件加密 (OME)。
    
- 安全多用途網際網路郵件延伸 (S/MIME)。
    
- 資訊版權管理 (IRM)。
    
## <a name="what-is-email-encryption-and-how-does-office-365-use-it"></a>什麼是電子郵件加密？Office 365 如何使用它？

加密是資訊的編碼僅授權的收件者可以解碼和取用資訊的程序。Office 365 使用加密兩種方式： 在服務] 並當做客戶控制項。在服務] 中加密預設會使用在 Office 365;您不需要設定的任何項目。例如，Office 365 使用傳輸層安全性 (TLS) 來加密的連線或兩部伺服器之間工作階段。 
  
以下是電子郵件加密通常的運作方式：
  
- 加密，或當郵件傳送過程中將無法讀取加密文字、 寄件者的電腦上或是由中央伺服器轉換純文字郵件時。
    
- 為傳送過程中以防止以防攔截郵件所讀取時郵件仍會保留在加密文字。
    
- 一旦收件者收到郵件時，會以下列兩種方式之一將郵件轉換回可閱讀的純文字：
    
  - 收件者的電腦會使用金鑰解密郵件，或
    
  - 中央伺服器解密的郵件收件者，代表後驗證收件者的身分識別。
    
如需有關 Office 365 保護伺服器之間的通訊的安全的詳細資訊，例如組織內 Office 365 或 Office 365 與 Office 365 外部信任的業務合作夥伴之間[如何 Exchange Online，請參閱使用 TLS 安全的電子郵件在 Office 365 的連線](exchange-online-uses-tls-to-secure-email-connections.md)。
  
請觀看此影片簡介[Office 365 中的加密](https://www.youtube.com/watch?v=KmfxCd5ublI)。
  
## <a name="comparing-email-encryption-options-available-in-office-365"></a>比較 Office 365 中提供的電子郵件加密選項

||        ![OME 的說明概念圖](media/2bf27b5e-bbb3-46d1-95bf-884dc27a746c.png)                 |        ![IRM 的說明概念圖](media/9c0cc444-9448-40c6-b244-8fcc593a64e0.png)                 |        ![SMIME 的說明概念圖](media/ae4613a8-c17e-47e1-8e13-12e891e43744.png)                |
|:-----|:-----|:-----|:-----|
|這是什麼？  <br/> |Office 365 郵件加密 (OME) 是內建於 Azure 版權管理 (Azure RMS) 的服務，可讓您將加密的電子郵件傳送給組織內部或外部的人，無論目的地電子郵件地址為何 (Gmail、Yahoo! Mail、Outlook.com 等)。  <br/> 身為管理員，您可以設定用以定義加密條件的傳輸規則。當使用者傳送符合規則的郵件時，會自動套用加密。  <br/> 若要檢視加密的郵件，收件者可以取得單次密碼、 登入 Microsoft 帳戶或登入工作或學校與 Office 365 相關聯的帳戶。收件者也可以傳送加密的回覆。它們不需要檢視加密的郵件或傳送回覆加密的 Office 365 訂閱。  <br/> |IRM 是加密解決方案，也可對電子郵件套用使用限制。這有助於防止敏感資訊被未經授權的人員列印、轉寄或複製。  <br/> Office 365 中的 IRM 功能使用 Azure 版權管理 (Azure RMS)。 
  <br/> |S/MIME 是一種憑證型加密解決方案可讓您加密及數位簽署的訊息。訊息加密有助於確保只有預定的收件者可以開啟及讀取郵件。數位簽章可協助收件者驗證寄件者的身分識別。  <br/> 數位簽章和郵件加密之所以可行，皆因為使用了唯一數位憑證，此憑證包含用於驗證數位簽章及加密或解密郵件的金鑰。  <br/> 若要使用 S/MIME，您必須公用金鑰檔案上每個收件者。收件者必須維持必須保持安全自己私人機碼。如果收件者的私密金鑰遭到洩漏，收件者必須以取得新的私密金鑰和轉散佈給所有可能的寄件者的公開金鑰。  <br/> |
|能做什麼？  <br/> | OME：  <br/>  將傳送給內部或外部收件者的郵件加密。  <br/>  可讓使用者將加密的郵件傳送至任何電子郵件地址，包括 Outlook.com、Yahoo!Mail 和 Gmail。  <br/>  可讓您，以系統管理員，以自訂檢視入口網站以反映您的組織品牌的電子郵件。  <br/>  Microsoft 安全地管理並儲存機碼，因此您不需要。  <br/>  只要可以在瀏覽器中開啟加密的郵件 (以 HTML 附件傳送)，就不需要任何特殊的用戶端軟體。  <br/> | IRM：  <br/>  利用加密和使用限制為電子郵件和附件提供線上和離線保護。  <br/>  可讓身為管理員的您能夠設定傳輸規則或 Outlook 保護規則，以自動將 IRM 套用至選取的郵件。  <br/>  可讓使用者以手動方式在 Outlook 或 Outlook Web App 中套用範本。  <br/> |S/MIME 以數位簽章解決寄件者驗證，以加密解決郵件機密性。  <br/> |
|不能做什麼？  <br/> |OME 不會讓您將流量限制套用至郵件。例如，您無法使用它來停止轉寄或列印加密的郵件的收件者。  <br/> |某些應用程式可能無法支援 IRM 電子郵件的所有裝置上。如需這些結構元件及其他產品支援 IRM 電子郵件的詳細資訊，請參閱[用戶端裝置功能](https://technet.microsoft.com/library/dn655136.aspx#BKMK_ClientCapabilities)。<br/> |S/MIME 不允許惡意程式碼、 垃圾郵件或原則掃描加密的郵件。  <br/> |
|建議和範例案例  <br/> | 我們建議使用 OME 當您想要將機密的商務資訊傳送至您的組織外部人員不論是消費者或其他企業版。例如：  <br/>  銀行員工將信用卡帳單傳送給客戶  <br/>  將醫療記錄傳送給病患府 office  <br/>  律師將機密的法律資訊傳送給其他律師  <br/> | 當您想要套用使用限制以及加密時，我們建議使用 IRM。例如：  <br/>  將機密的詳細資訊傳送至其小組需一項新產品經理適用於"不要轉寄 」] 選項。  <br/>  行政人員需要與其他公司共用投標提案，其中一個附件是由使用 Office 365 的夥伴提供，電子郵件和附件皆需要受到保護。  <br/> | 我們建議使用 S/MIME 組織或收件者的組織需要則為 true 的對等加密時發生。  <br/>  S/MIME 最常用於下列情況：  <br/>  政府機構與其他政府機關通訊  <br/>  企業與政府機構通訊  <br/> |
   
## <a name="what-encryption-options-are-available-for-my-office-365-subscription"></a>我的 Office 365 訂閱有哪些加密選項？

如需 Office 365 郵件加密選項訂閱請參閱[Exchange Online 服務說明](https://technet.microsoft.com/en-us/library/exchange-online-service-description.aspx)。這裡，您可以找到下列加密功能的相關資訊：
  
- Azure RMS，包括 IRM 功能和 OME
    
- S/MIME
    
- TLS
    
- 靜態資料的加密 (透過 BitLocker)
    
## <a name="what-about-encryption-for-data-at-rest"></a>靜態資料的加密呢？

「 靜態資料 」 指的是不是主動傳輸的資料。Office 365 中靜態電子郵件資料是使用 BitLocker 磁碟加密來加密。BitLocker 加密 Office 365 提供增強型的理想的未經授權存取的資料中心的硬碟。若要深入了解，請參閱[BitLocker 概觀 （英文）](https://go.microsoft.com/fwlink/p/?LinkId=394737)。
  
## <a name="more-information-about-email-encryption-options-in-office-365"></a>Office 365 中的電子郵件加密選項的相關資訊

如需本文中電子郵件加密選項以及 TLS 的詳細資訊，請參閱這些文件：
  
 **OME**
  
[Office 365 郵件加密 (OME)](ome.md)
  
 **IRM**
  
[Exchange Online 中的資訊版權管理](https://technet.microsoft.com/en-us/library/jj983436%28v=exchg.150%29.aspx)
  
[Azure 版權管理新功能](https://technet.microsoft.com/library/jj585026)
  
 **S/MIME**
  
[可用於訊息簽署和加密的 S/MIME](https://technet.microsoft.com/library/dn626158)
  
[了解 S/MIME](https://technet.microsoft.com/library/aa995740%28v=exchg.65%29.aspx)
  
[了解公用密碼編譯](https://technet.microsoft.com/library/aa998077%28v=exchg.65%29.aspx)
  
 **TLS**
  
[Office 365 中使用連接器來設定自訂郵件流程](https://technet.microsoft.com/en-us/library/jj723138%28v=exchg.150%29.aspx)
  

