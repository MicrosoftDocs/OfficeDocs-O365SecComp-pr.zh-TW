---
title: 取消登錄的網域電子郵件
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 10/17/2018
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: 如果傳送大量取消登錄的網域電子郵件，則會執行快速封鎖電子郵件的風險。請閱讀本篇文章以深入了解。
ms.openlocfilehash: 8120bd147da2a7aab41ae14c444d2fe57242199e
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30276223"
---
# <a name="unregistered-domain-email-what-you-need-to-know"></a>取消登錄的網域電子郵件： 您需要知道什麼

Office 365 允許以轉送某些郵件透過 Exchange Online Protection (EOP) 的租用戶。當使用者擁有的 Office 365 信箱與外部有人傳送電子郵件給其但電子郵件轉寄設定使其回到使用者的外部信箱，就是一個受支援的範例。這是最常見其中學生要利用其個人電子郵件介面但仍屬學校相關的電子郵件的教育環境中。另一個例子是當客戶混合式案例，且已傳送電子郵件移出 EOP 的內部伺服器。

## <a name="problems-with-unregistered-domains"></a>取消登錄的網域的問題

內部部署伺服器取得危害和最後轉送大量的垃圾郵件移出 EOP 時問題。在幾乎所有的情況下，右連接器已設定但從取消登錄、 也稱為取消提供這項、 網域傳送電子郵件。Office 365 沒有可合理的郵件來自取消登錄的網域]，但應在您計劃傳送出的每個網域系統管理中心設定公認的網域。

一旦危害，承租人會禁止傳送輸出郵件取消登錄的網域。使用者會收到未傳遞報告 (NDR) 表示：

- 550 5.7.750 服務無法使用。傳送取消登錄的網域從封鎖的用戶端

## <a name="unblocking-tenant-in-order-to-send-again"></a>若要一次傳送解除封鎖租用戶

有您需要執行如果您要取得封鎖來自取消登錄的網域傳送的一些事項：

1. 請確定所有的網域註冊 Office 365 系統管理中心中。您可以找到更多的資訊[如下](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。

2. 尋找不尋常的連接器。惡意執行者通常會在您的 Office 365 租用戶傳送垃圾郵件中建立新的輸入的連接器。在檢查您的連接器的詳細資訊可以找到[以下](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps)。 

3. 鎖定的內部伺服器和確認他們不遭到入侵。

> [!TIP]
> 有許多因素相關這裡，特別是如果這些是協力廠商伺服器。無論如何，您將需要能夠確認離開伺服器的所有郵件都是否合法。

4. 一旦完成，您必須連絡 Microsoft 支援並要求要取得您一次傳送來自取消登錄的網域解除封鎖的租用戶。 提供錯誤碼相當有用，但是您將需要證明您的環境安全且不會在一次傳送垃圾郵件。開啟支援案例的詳細資訊可以找到[以下](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online)。
  
## <a name="for-more-information"></a>如需詳細資訊

[Office 365 電子郵件的反垃圾郵件保護](anti-spam-protection.md)

[Office 365 中的電子郵件未傳遞回報](https://support.office.com/article/email-non-delivery-reports-in-office-365-51daa6b9-2e35-49c4-a0c9-df85bf8533c3)

[設定信箱的電子郵件轉寄功能](https://docs.microsoft.com/en-us/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[如何將多功能裝置或應用程式設定為使用 Office 365 傳送電子郵件](https://support.office.com/en-us/article/How-to-set-up-a-multifunction-device-or-application-to-send-email-using-Office-365-69f58e99-c550-4274-ad18-c805d654b4c4)

[管理公認的網域在 Exchange Online](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。
