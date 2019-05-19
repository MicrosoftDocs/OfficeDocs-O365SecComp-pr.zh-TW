---
title: Office 365 中的電子郵件加密
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c0d87cbe-6d65-4c03-88ad-5216ea5564e8
ms.collection:
- M365-security-compliance
description: 比較包括 Office 郵件加密 (OME)、 S/MIME、 資訊版權管理 (IRM) 的 Office 365 中的加密選項取得並了解傳輸層安全性 (TLS)。
ms.openlocfilehash: 4a39bee76346bb46a53ab752d2fac31316c0258f
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154785"
---
# <a name="email-encryption-in-office-365"></a>Office 365 中的電子郵件加密

本文會比較包括 Office 郵件加密 (OME)、 S/MIME、 資訊版權管理 (IRM) 的 Office 365 中的加密選項，並介紹傳輸層安全性 (TLS)。
  
Office 365 提供可協助您符合您的業務需求的電子郵件安全性的多個加密選項。 本文提供三種方式可以加密在 Office 365 中的電子郵件。 如果您想要深入了解 Office 365 中的所有安全性功能，請造訪[Office 365 信任中心](http://go.microsoft.com/fwlink/p/?LinkID=282470)。 本文介紹適用於 Office 365 系統管理員，以協助 Office 365 中的安全電子郵件加密的三種類型：
  
- Office 郵件加密 (OME)。
    
- 安全/多用途網際網路郵件延伸 (S/MIME)。
    
- 資訊版權管理 (IRM)。
    
## <a name="what-is-email-encryption-and-how-does-office-365-use-it"></a>什麼是電子郵件加密，以及如何沒有 Office 365 使用它？

加密是依據資訊已編碼以便只有授權的收件者可以解碼，並使用資訊的程序。 Office 365 會使用加密兩種方式： 在服務中，並做為客戶的控制項。 在服務中，加密使用 Office 365 中的預設值;您不需要進行任何設定。 例如，Office 365 會使用傳輸層安全性 (TLS) 加密的連線或工作階段中的，兩個伺服器之間。 
  
以下是電子郵件加密一般的運作：
  
- 郵件加密，或在傳輸郵件時，從純文字轉換成無法讀取加密文字，寄件者在機器上，或在中央伺服器。
    
- 當以防止其被讀取以防攔截郵件傳輸時，郵件仍會保留在加密文字。
    
- 一旦收件者收到郵件時，會將郵件轉換回可讀取的純文字，下列兩種方式之一：
    
  - 收件者的電腦使用金鑰將郵件解密，或
    
  - 在中央伺服器會將代表收件者，將郵件解密後驗證收件者的身分識別。
    
如需有關 Office 365 如何保護伺服器之間的通訊的詳細資訊，例如組織內 Office 365 或 Office 365 和 Office 365 外部信任的商業夥伴之間[如何 Exchange Online，請參閱使用 TLS 來保護電子郵件Office 365 中的連線](exchange-online-uses-tls-to-secure-email-connections.md)。
  
請觀看此影片如簡介[Office 365 中的加密](https://www.youtube.com/watch?v=KmfxCd5ublI)。
  
## <a name="comparing-email-encryption-options-available-in-office-365"></a>比較 Office 365 中可用的電子郵件加密選項

||![OME 的說明概念圖](media/2bf27b5e-bbb3-46d1-95bf-884dc27a746c.png)|![IRM 的說明概念圖](media/9c0cc444-9448-40c6-b244-8fcc593a64e0.png)|![SMIME 的說明概念圖](media/ae4613a8-c17e-47e1-8e13-12e891e43744.png)|
|:-----|:-----|:-----|:-----|
|這是什麼？|Office 365 郵件加密 (OME) 是內建於 Azure 版權管理 (Azure RMS)，可讓您將加密的電子郵件傳送給您的組織，無論目的地電子郵件地址 （Gmail、 yahoo ！ 內外的人員的服務 Mail、 Outlook.com 等）。  <br/> 身為系統管理員，您可以設定定義加密條件的傳輸規則。 當使用者傳送符合規則的郵件時，會自動套用加密。  <br/> 若要檢視加密的郵件，收件者可以取得一次性密碼，登入 Microsoft 帳戶或登入公司或學校帳戶與 Office 365 相關聯。 收件者也可以傳送加密的回覆。 則不需要 Office 365 訂用帳戶檢視加密的郵件，或傳送加密的回覆。|IRM 是也適用於電子郵件流量限制加密解決方案。 它可以協助防止使用者列印、 轉寄或未經授權的人員所複製的敏感資訊。  <br/> Office 365 中的 IRM 功能使用 Azure 版權管理 (Azure RMS)。|S/MIME 是一種憑證型加密解決方案，可讓您同時加密，並以數位方式簽署郵件時。 訊息加密有助於確保只有預定的收件者可以開啟和讀取該郵件。 數位簽章可協助收件者驗證寄件者的身分識別。  <br/> 數位簽章與郵件加密之所以可行，透過包含驗證數位簽章及加密或解密訊息的索引鍵的唯一數位憑證。  <br/> 若要使用 S/MIME，您必須擁有公開金鑰檔每個收件者。 收件者必須維護自己私用的機碼，必須保持安全。 如果收件者的私密金鑰遭到洩漏，收件者必須取得新的私用金鑰並重新分散到所有可能的寄件者的公開金鑰。|
|能做什麼？|OME:  <br/>  加密郵件傳送給內部或外部收件者。  <br/>  可讓使用者將加密的郵件傳送至任何電子郵件地址，包括 Outlook.com、 yahoo ！ Mail 和 Gmail。  <br/>  可讓您，身為系統管理員，以自訂電子郵件檢視入口網站，以反映貴組織的品牌。  <br/>  Microsoft 安全地管理並儲存金鑰，因此您不需要。  <br/>  只要可以在瀏覽器中開啟加密的郵件 （HTML 附件形式傳送），就不需要任何特殊的用戶端軟體。|IRM:  <br/>  使用加密和使用限制的電子郵件和附件提供線上和離線保護。  <br/>  可讓您，身為系統管理員，來設定傳輸規則或 Outlook 保護規則自動套用至選取的郵件的 IRM 功能。  <br/>  可讓使用者以手動方式套用在 Outlook 或網頁 （先前稱為 Outlook Web App） 中的範本。|S/MIME 地址寄件者驗證數位簽章，與使用加密解決郵件機密性。|
|不能做什麼？|OME 不會讓您將流量限制套用到郵件。 例如，您無法使用它來停止轉寄或列印加密的郵件的收件者。|某些應用程式可能不支援 IRM 電子郵件的所有裝置上。 如需這些與其他支援 IRM 電子郵件的產品的詳細資訊，請參閱 <<c0>用戶端裝置的功能。|S/MIME 不允許加密的郵件，可以掃描惡意程式碼、 垃圾郵件或原則。|
|建議和範例案例|我們建議使用 ome 一次，當您要將機密的商務資訊傳送到您組織外的人員，不論是消費者或其他企業。 例如：  <br/>  銀行員工將信用卡帳單傳送給客戶  <br/>  診所將醫療記錄傳送給病患  <br/>  律師將機密的法律資訊傳送給其他律師|我們建議使用 IRM，當您想要套用流量限制，以及加密。 例如：  <br/>  將機密的詳細資訊傳送給組員關於新產品的管理員會套用 「 不要轉寄 」 選項。  <br/>  行政人員需要與其他公司，其中包含從協力廠商正在使用 Office 365 的附件，共用投標提案，且需要電子郵件和附件受到保護。|我們建議您的組織或收件者的組織需求，則為 true 的端對端加密時，使用 S/MIME。  <br/>  S/MIME 最常用於下列情況：  <br/>  政府機構與其他政府機關通訊  <br/>  企業與政府機構通訊|
   
## <a name="what-encryption-options-are-available-for-my-office-365-subscription"></a>適用於 「 我的 Office 365 訂閱有哪些加密選項？

如需 Office 365 訂用帳戶的電子郵件加密選項的詳細資訊請參閱 < <b0>Exchange Online 服務說明</b0>。 在這裡，您可以找到下列加密功能的相關資訊：
  
- Azure RMS，包括 IRM 功能和 OME
    
- S/MIME
    
- TLS
    
- 靜態 （透過 BitLocker) 資料的加密
    
## <a name="what-about-encryption-for-data-at-rest"></a>靜態資料的加密呢？

「 靜態資料 」 指的是不是目前正在傳輸中的資料。 在 Office 365 中，電子郵件靜態資料的加密方式是 BitLocker 磁碟機加密。 BitLocker 會加密硬碟中 Office 365 資料中心，以提供增強的防範未經授權的存取。 若要深入了解，請參閱〈[BitLocker 概觀](https://go.microsoft.com/fwlink/p/?LinkId=394737)〉。
  
## <a name="more-information-about-email-encryption-options-in-office-365"></a>Office 365 中的電子郵件加密選項的詳細資訊

如需在此文章以及 TLS 的電子郵件加密選項的詳細資訊，請參閱下列文章：
  
 **OME**
  
[Office 365 郵件加密 (OME)](ome.md)
  
 **IRM**
  
[Exchange Online 中的資訊版權管理](https://technet.microsoft.com/en-us/library/jj983436%28v=exchg.150%29.aspx)
  
[什麼是 Azure 版權管理？](https://technet.microsoft.com/library/jj585026)
  
 **S/MIME**
  
[可用於訊息簽署和加密的 S/MIME](https://technet.microsoft.com/library/dn626158)
  
[瞭解 S/MIME](https://technet.microsoft.com/library/aa995740%28v=exchg.65%29.aspx)
  
[瞭解公開金鑰加密](https://technet.microsoft.com/library/aa998077%28v=exchg.65%29.aspx)
  
 **TLS**
  
[在 Office 365 中使用連接器來設定自訂郵件流程](https://technet.microsoft.com/en-us/library/jj723138%28v=exchg.150%29.aspx)
  

