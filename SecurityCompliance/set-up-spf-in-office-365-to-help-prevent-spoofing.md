---
title: 在 Office 365 中設定 SPF 以協助防止詐騙
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 2/19/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 71373291-83d2-466f-86ea-fc61493743a6
ms.collection:
- M365-security-compliance
description: 摘要： 本文說明如何更新網域名稱服務 (DNS) 記錄，使您可以在 Office 365 內的自訂網域中使用寄件者原則架構 (SPF)。 使用 SPF 協助驗證自您自訂網域傳送的輸出電子郵件。
ms.openlocfilehash: 15472900986a367e084c6126580cef85d286a94b
ms.sourcegitcommit: 33c8e9c16143650ca443d73e91631f9180a9268e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/25/2019
ms.locfileid: "35854787"
---
# <a name="set-up-spf-in-office-365-to-help-prevent-spoofing"></a>在 Office 365 中設定 SPF 以協助防止詐騙

 **摘要：** 本文說明如何更新網域名稱服務 (DNS) 記錄，使您可以在 Office 365 內的自訂網域中使用寄件者原則架構 (SPF)。使用 SPF 協助驗證自您自訂網域傳送的輸出電子郵件。 
  
如要使用自訂網域，Office 365 要求您將寄件者原則架構 (SPF) TXT 記錄新增至您的 DNS 記錄以協助防止詐騙。SPF 會識別哪些郵件伺服器可以代表您傳送郵件。基本上，SPF 以及 DKIM、DMARC 和其他 Office 365 所支援的技術可以協助防止詐騙和網路釣魚。SPF 會新增為 TXT 記錄，DNS 用來識別哪些郵件伺服器可以代表您的網域傳送郵件。收件者郵件系統參考 SPF TXT 記錄，以判斷您自訂網域的郵件是否來自授權的郵件伺服器。
  
例如，假設您的自訂網域 contoso.com 是使用 Office 365。您新增了 SPF TXT 記錄，而該記錄將 Office 365 訊息伺服器列為您的網域的合法郵件伺服器。當接收郵件伺服器是從 joe@contoso.com 取得訊息時，伺服器就會查閱 contoso.com 的 SPF TXT 記錄，並且找出訊息是否有效。如果接收伺服器發現訊息來自 SPF 記錄中所列的 Office 365 訊息伺服器以外的伺服器，接收郵件伺服器可以選擇將訊息當作垃圾郵件拒絕。
  
此外，如果您的自訂網域沒有 SPF TXT 記錄，某些接收伺服器可能會拒絕徹底訊息。這是因為接收伺服器無法驗證訊息是來自授權的訊息伺服器。
  
如果您已經設定 Office 365 的郵件，然後您已經在 DNS 中包含 Microsoft 的訊息伺服器作為 SPF TXT 記錄。不過，在某些情況下，您可能需要在 DNS 中更新您的 SPF TXT 記錄。例如：
  
- 以往，如果您是使用 SharePoint Online，您需要新增不同的 SPF TXT 記錄至您的自訂網域。你不再需要這樣做。此變更會降低 SharePoint Online 通知訊息被置於「垃圾電子郵件」資料夾的機率。如果您達到 10 次查閱限制，且收到錯誤，表示「超出查閱限制」和「太多躍點」，請更新您的 SPF TXT 記錄。
    
- 如果您有 Office 365 與 Exchange 內部部署的混合式環境。
    
- 您想要設定 DKIM 和 DMARC (建議選項)。
    
## <a name="updating-your-spf-txt-record-for-office-365"></a>更新 Office 365 的 SPF TXT 記錄

在 DNS 中更新 TXT 記錄之前，您需要收集一些資訊，並判斷記錄的格式。這有助於防止產生 DNS 錯誤。如需進階範例、有關支援的 SPF 語法的更詳細討論，請參閱 [若要防止詐騙及 Office 365 中的網路釣魚 SPF 的運作方式](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks)。
  
收集這項資訊：
  
- 您網域的目前 SPF TXT 記錄。如需相關指示，請參閱[收集建立 Office 365 DNS 記錄所需的資訊](https://support.office.microsoft.com/en-us/article/Gather-the-information-you-need-to-create-Office-365-DNS-records-77f90d4a-dc7f-4f09-8972-c1b03ea85a67)。
    
- 所有內部部署訊息伺服器的 IP 位址。例如， **192.168.0.1**。
    
- 要使用的網域名稱，針對您需要包含在 SPF TXT 記錄中的所有協力廠商網域。某些大量郵件提供者已設定要用於他們的客戶的子網域。例如，公司 MailChimp 已設定 **servers.mcsv.net**。
    
- 決定您想要對 SPF TXT 記錄使用何種強制執行規則。我們建議 **-all**。如需其他語法選項的詳細資訊，請參閱 [Office 365 的 SPF TXT 記錄語法](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365)。
    
### <a name="to-add-or-update-your-spf-txt-record"></a>若要新增或更新 SPF TXT 記錄

1. 如果您還未做這樣的處理，請使用下表中的語法以形成 SPF TXT 記錄︰
    
||**如果您正在使用...**|**對 Office 365 客戶通用？**|**新增此...**|
|:-----|:-----|:-----|:-----|
|1  <br/> |任何電子郵件系統 (必要項)  <br/> |通用。以此值開頭的所有 SPF TXT 記錄  <br/> |v=spf1  <br/> |
|2  <br/> |Exchange Online  <br/> |通用  <br/> |include:spf.protection.outlook.com  <br/> |
|3  <br/> |僅限 Exchange Online 專用  <br/> |不通用  <br/> |ip4:23.103.224.0/19 ip4:206.191.224.0/19 ip4:40.103.0.0/16 include: spf.protection.outlook.com  <br/> |
|4  <br/> |僅限 Office 365 德國、Microsoft Cloud 德國  <br/> |不通用  <br/> |include:spf.protection.outlook.de  <br/> |
|5  <br/> |協力廠商電子郵件系統  <br/> |不通用  <br/> |包括：\<網域名稱\>  <br/> 其中網域名稱是協力廠商電子郵件系統的網域名稱。  <br/> |
|6  <br/> |內部部署郵件系統例如，Exchange Online Protection 加上另一個郵件系統  <br/> |不通用  <br/> | 對每個額外郵件系統使用其中一個︰  <br/>  ip4：\<  _IP address_\>  <br/>  ip6：\<  _IP address_\>  <br/>  包括︰\<  _domain name_\>  <br/>  其中 \<  _IP address_\> 的值是其他郵件系統的 IP 位址，\< _domain name_\> 是代表您的網域傳送郵件的其他郵件系統的網域名稱。  <br/> |
|7  <br/> |任何電子郵件系統 (必要項)  <br/> |通用。以此值結束的所有 SPF TXT 記錄  <br/> |\< _enforcement rule_\>  <br/> 這可以是數個值其中之一。建議您使用 **-all**。  <br/> |
   
1.1，例如，如果您是完全裝載於 Office 365，也就是您有任何內部郵件伺服器上，您的 SPF TXT 記錄會包含 1、 2 和 7 的資料列和看起來像這樣：
    
  ```
   v=spf1 include:spf.protection.outlook.com -all
  ```

1.2 這是最常見的 Office 365 SPF TXT 記錄。 此記錄適用於幾乎所有人，不論是否您 Office 365 資料中心位於美國，或在歐洲 （包括德國），或在另一個位置。
    
1.3 不過，如果您已購買 Office 365 Germany，組件的 Microsoft Cloud 德國，您應該使用從第 4 行的 include 陳述式而不是第 2 行。 例如，如果您是完全裝載於 Office 365 Germany，也就是您有任何內部郵件伺服器上，您的 SPF TXT 記錄會包含 1、 4 和 7 的資料列和看起來像這樣：
    
  ```
   v=spf1 include:spf.protection.outlook.de -all
  ```

1.4 如果您已部署 Office 365 中並已設定您的 SPF TXT 記錄的自訂網域，而且您即將移轉至 Office 365 Germany，您需要更新您的 SPF TXT 記錄。 若要這麼做，請變更**include: spf.protection.outlook.com**為**include:spf.protection.outlook.de**。
    
2. 一旦您已形成 SPF TXT 記錄，您必須更新 dns 記錄。 您只能有一個網域的 SPF TXT 記錄。 如果 SPF TXT 記錄存在，而不是新增新的記錄，您需要更新現有的記錄。 移到[建立 Office 365 的 DNS 記錄](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider?view=o365-worldwide)，，然後按一下 [您的 DNS 主機的連結。 
    
3. 測試您的 SPF TXT 記錄。
    
## <a name="more-information-about-spf"></a>關於 SPF 的詳細資訊

如需進階範例、有關支援的 SPF 語法、詐騙、疑難排解，以及 Office 365 如何支援 SPF 的更詳細討論，請參閱 [若要防止詐騙及 Office 365 中的網路釣魚 SPF 的運作方式](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks)。
  
## <a name="next-steps-after-you-set-up-spf-for-office-365"></a>後續步驟：為 Office 365 設定 SPF 之後

無法使用您的 SPF TXT 記錄嗎?請參閱[疑難排解： 的 SPF Office 365 中的最佳作法](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot)。
  
 SPF 是設計來協助防止詐騙，但是有 SPF 無法防護的詐騙技術。為了防止這些項目，設定 SPF 之後，您也應該為 Office 365 設定 DKIM 和 DMARC。若要開始使用，請參閱 [使用 DKIM 驗證從您在 Office 365 中的自訂網域傳送的輸出電子郵件](use-dkim-to-validate-outbound-email.md)。接下來，請參閱[使用 DMARC 來驗證 Office 365 電子郵件](use-dmarc-to-validate-email.md)。
  

