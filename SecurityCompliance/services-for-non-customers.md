---
title: 服務的非客戶傳送郵件到 Office 365
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 5/2/2016
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 19fd3e0f-8dbf-4049-a810-2c8ee6cefd48
ms.collection:
- M365-security-compliance
description: 若要協助維護使用者的電子郵件使用中的信任，Microsoft 已放置就地各種不同的原則和技術，以協助保護我們的使用者。
ms.openlocfilehash: 540610fc3d1b53692688c729b714c839bf436e24
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32260871"
---
# <a name="services-for-non-customers-sending-mail-to-office-365"></a>服務的非客戶傳送郵件到 Office 365
  
電子郵件濫用、 垃圾郵件和詐騙電子郵件 （網路釣魚） 繼續 burden 整個電子郵件生態系統。 若要協助維護使用者的電子郵件使用中的信任，Microsoft 已放置就地各種不同的原則和技術，以協助保護我們的使用者。 不過，Microsoft 了解合法電子郵件不應該造成負面的影響。 因此，我們已建立服務，以協助改善其能夠傳遞電子郵件給 Office 365 使用者藉由主動管理其傳送信譽寄件者的套件。
  
本概觀提供即使您不是 Office 365 客戶，我們提供給您的組織優點的相關資訊。
  
## <a name="sender-solutions"></a>寄件者的解決方案
<a name="sectionSection0"> </a>

|**服務**|**效益**|
|:-----|:-----|
|此線上說明內容  <br/> | 提供：  <br/>  傳遞至 EOP 使用者的通訊與相關的任何問題起點  <br/>  包含簡單的線上指南與我們的原則和需求  <br/>  垃圾郵件篩選器與 Microsoft 所採用的驗證技術概觀  <br/> |
|[Microsoft 支援](services-for-non-customers.md#AboutSupport) <br/> |提供自助和呈報支援傳遞問題。  <br/> |
|[Office 365 反垃圾郵件 IP 取消列出入口網站](services-for-non-customers.md#DelistPortal) <br/> |一套工具來送出 IP 取消列出要求。 送出這個要求之前是以確保來自 IP 有問題的任何進一步郵件不是沒有不當或惡意寄件者的責任。  <br/> |
|[濫用和垃圾郵件報告源自於 Exchange Online 的垃圾電子郵件](services-for-non-customers.md#ReportOurJunk) <br/> |會不斷垃圾郵件和其他的垃圾郵件防止傳送從 Exchange Online 和雜亂網際網路和您的郵件系統。  <br/> |
   
## <a name="microsoft-support"></a>Microsoft 支援
<a name="AboutSupport"> </a>

Microsoft 提供了數個人員無法傳送郵件到 Office 365 收件匣的支援選項。 我們建議您：
  
- 請遵循您會收到任何未傳遞回報中的指示進行。
    
- 請參閱[疑難排解郵件傳送到 Office 365](troubleshooting-mail-sent-to-office-365.md)中的非客戶會遇到最常見的問題。
    
- 用於[Office 365 取消列出入口網站](https://sender.office.com)將要求提交至已從封鎖寄件者清單中移除您 IP。 
    
- 閱讀[Microsoft 社群論壇](https://community.office365.com/en-us/f/)。
    
- 請連絡您嘗試使用另一種方法的電子郵件，並請他們連絡 Microsoft 支援服務，並開啟支援票證代替您 Office 365 客戶。 在某些情況下，基於法規因素而，Microsoft 支援服務必須彼此直接寄件者擁有遭到封鎖的 IP 空間。 不過，非客戶通常無法開啟支援票證。
    
     如需 Office 365 連絡 Microsoft 技術支援的詳細資訊，請參閱 <<c0>支援>。
    
## <a name="office-365-anti-spam-ip-delist-portal"></a>Office 365 反垃圾郵件 IP 取消列出入口網站
<a name="DelistPortal"> </a>

這是您可以使用您自己從 Office 365 封鎖寄件者清單中移除自助入口網站。 如果您是您收到錯誤訊息，當您嘗試傳送電子郵件給其電子郵件地址是在 Office 365 中的收件者，而您不認為您此入口網站應使用。 如需詳細資訊，請參閱[使用取消列入入口網站，將自己從 Office 365 的已封鎖寄件者清單中移除](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)。
  
## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a>濫用和垃圾郵件報告源自於 Exchange Online 的垃圾電子郵件
<a name="ReportOurJunk"> </a>

有時 Office 365 是由協力廠商用來傳送垃圾郵件中的我們字詞的使用與原則違規情形。 如果您收到任何垃圾電子郵件從 Office 365，您可以報告這些郵件到[junk@office365.microsoft.com](mailto:junk@office365.microsoft.com)。 請附加違規的郵件，包括完整的郵件標頭中，以 RFC 5322 或 ARF 格式。 Outlook web 使用者可以使用回報垃圾郵件的內建工具。 如詳細資訊，請參閱[報告垃圾郵件和網路釣魚詐騙網頁型 Outlook 中](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)。
  

