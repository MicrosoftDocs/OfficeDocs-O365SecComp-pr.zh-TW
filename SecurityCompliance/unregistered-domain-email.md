---
title: 未註冊的網域的電子郵件
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 10/17/2018
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: 如果您傳送大量的未註冊的網域的電子郵件，則會執行您取得封鎖的電子郵件的風險。 閱讀本篇文章以了解更多。
ms.openlocfilehash: 207b71ab7e144af9709e7485d61c936e07271a11
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156295"
---
# <a name="unregistered-domain-email-what-you-need-to-know"></a>未註冊的網域電子郵件： 您要知道什麼

Office 365 允許轉送某些郵件透過 Exchange Online Protection (EOP) 的租用戶。 當使用者擁有 Office 365 信箱和外部的人員傳送他們電子郵件，但使其回到使用者的外部信箱設定電子郵件轉寄功能，就是一個支援的範例。 這是最常見的學生，想要利用其個人電子郵件介面，但仍取得電子郵件與學校相關的教育版環境中。 另一個例子是客戶在混合式案例，並有傳送超出 EOP 的電子郵件的內部部署伺服器時。

## <a name="problems-with-unregistered-domains"></a>問題未註冊的網域

問題時，內部部署伺服器取得危害和最終轉送大量超出 EOP 垃圾郵件。 在大多數情況下，右連接器已設定，但未註冊，也就是取消提供這項，網域從要傳送電子郵件。 Office 365，並讓合理的郵件來自未註冊的網域，但應在您計劃傳送出的每個網域的系統管理中心中設定公認的網域。

一旦危害，租用戶就禁止傳送未註冊的網域的輸出郵件。 使用者會收到未傳遞回報 (NDR) 表示：

- 550 5.7.750 服務無法使用。 封鎖來自未註冊的網域傳送的用戶端

## <a name="unblocking-tenant-in-order-to-send-again"></a>若要重新傳送解除封鎖租用戶

有您不必執行如果您要取得封鎖來自未註冊的網域傳送的一些事項：

1. 請確定您網域的所有註冊 Microsoft 365 系統管理中心。 詳細資訊，請參閱[以下](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。

2. 尋找不尋常的連接器。 惡意動作項目通常會傳送垃圾郵件您 Office 365 租用戶中建立新的輸入的連接器。 檢查您的連接器的詳細資訊可以找到[以下](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps)。 

3. 鎖定您的內部部署伺服器，並確定他們沒有遭到盜用。

> [!TIP]
> 有許多因素所涉及在這裡，尤其是協力廠商的伺服器。 無論如何，您將需要能夠確認是合法的所有郵件離開您的伺服器。

4. 完成時，您必須連絡 Microsoft 支援服務，並要求以取得您的租用戶解除封鎖再次傳送來自未註冊的網域。  提供錯誤碼很有幫助，但您想要證明您的環境受到保護，且不會在一次傳送垃圾郵件。 在開啟支援案例的詳細資訊可以找到[以下](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online)。
  
## <a name="for-more-information"></a>如需詳細資訊

[Office 365 電子郵件的反垃圾郵件保護](anti-spam-protection.md)

[Office 365 中的電子郵件未傳遞回報](https://support.office.com/article/email-non-delivery-reports-in-office-365-51daa6b9-2e35-49c4-a0c9-df85bf8533c3)

[設定信箱的電子郵件轉寄功能](https://docs.microsoft.com/en-us/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[如何將多功能裝置或應用程式設定為使用 Office 365 傳送電子郵件](https://support.office.com/en-us/article/How-to-set-up-a-multifunction-device-or-application-to-send-email-using-Office-365-69f58e99-c550-4274-ad18-c805d654b4c4)

[管理公認的網域在 Exchange Online](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。
