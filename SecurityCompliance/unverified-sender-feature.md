---
title: 識別 Outlook.com 和網頁型 Outlook 中的可疑郵件
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 04/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 若要防止網路釣魚郵件送達您的信箱，Outlook.com 和網頁型 Outlook 確認寄件者是誰他們說他們且可疑的郵件標示為垃圾郵件。
ms.openlocfilehash: edba30bb2ac0f9dc6ebc12db957a518de0c1b543
ms.sourcegitcommit: 9907bebc5f225032f681c4952de0b0be2df278ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/26/2019
ms.locfileid: "33345888"
---
# <a name="identify-suspicious-messages-in-outlookcom-and-outlook-on-the-web"></a>識別 Outlook.com 和網頁型 Outlook 中的可疑郵件

若要防止網路釣魚郵件送達您的信箱，Outlook.com 和網頁型 Outlook 確認寄件者是誰他們說他們且可疑的郵件標示為垃圾郵件。

> [!IMPORTANT]
> 當郵件標示為網路釣魚詐騙、 Outlook.com 和 Outlook 網頁顯示一則警告] 頁面頂端，但仍然可以開啟任何郵件中的連結。

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a>如何識別我的收件匣中的可疑的郵件？

Outlook.com 和網頁型 Outlook 顯示指標，當郵件的寄件者也無法識別或其身分識別為不同於從地址中看到的內容。

### <a name="you-see-a--in-the-sender-image"></a>您會看到 '？ ' 中的寄件者影像

當 Outlook.com 和網頁型 Outlook 無法驗證使用電子郵件驗證技術的寄件者的身分識別時，他們會顯示 '？ ' 中的寄件者相片。

![郵件未通過驗證](media/message-did-not-pass-verification.jpg)

若要驗證失敗不是每個訊息是惡意。 不過，您應該謹慎互動與未驗證如果您不能辨識寄件者的郵件。 或者，如果您辨識通常沒有寄件者 '？ ' 寄件者的影像，但您突然開始看到它，可能會登寄件者詐騙。

### <a name="the-senders-address-is-different-than-what-appears-in-the-from-address"></a>寄件者地址是不同的 From 地址中顯示的內容

通常，您看到訊息中的電子郵件地址是不同於從地址中看到的內容。 有時網路釣客會嘗試誘騙寄件者是其他人以外人員它們確實是的想法。

當 Outlook.com 和 outlook 網頁版偵測寄件者的實際地址與寄地址的地址之間的差異時，它們會顯示實際寄件者，並使用透過標記，這會加上底線。

![未驗證的寄件者的替代文字](media/unverified-sender-feature1.png)

在這個範例中，在傳送網域`suspicious.com`通過驗證，但寄件者放`unknown@contoso.com`From 地址。

不是每個郵件透過標記為可疑。 不過，如果您不能辨識郵件透過標記，您應該謹慎與其互動。

在 Outlook.com 和新網頁型 Outlook 中，您可以將游標停留寄件者的名稱或郵件清單中，查看他們的電子郵件地址，而不需要開啟該郵件的地址。

![開始使用 OneDrive](media/get-started-with-onedrive-message.png)

如何知道是否您使用新的 Outlook web 上？ 請參閱下列的範例：

![Outlook 與 Office 365](media/outlook-vs-outlook365.png)

## <a name="frequently-asked-questions"></a>常見問題集

### <a name="what-criteria-does-outlookcom-and-outlook-on-the-web-use-to-add-the--and-the-via-properties"></a>查看準則沒有 Outlook.com 和網頁型 Outlook 使用新增 '？ ' 和 '透過' 屬性？

為 '？ ' 中的寄件者影像： Outlook.com 需要郵件通過 SPF 或 DKIM 驗證。 如需詳細資訊，請參閱[設定 spf 以協助防止詐騙的 Office 365 中](set-up-spf-in-office-365-to-help-prevent-spoofing.md)和[使用 DKIM 驗證從您在 Office 365 中的自訂網域傳送的外寄電子郵件](use-dkim-to-validate-outbound-email.md)。

針對透過標記： Outlook.com 中自地址的網域不同網域的 DKIM 簽章或 SMTP MAIL FROM 中時，顯示在兩個欄位 （偏好的 DKIM 簽章） 的其中一個網域。

### <a name="can-i-override-these-properties-with-ip-allows-exchange-transport-rule-allows-or-safe-senders"></a>可以覆寫這些屬性與 IP 允許、 Exchange 傳輸規則可讓，或安全的寄件者？

您不能覆寫這些屬性。

### <a name="how-do-i-remove-these-properties"></a>如何移除這些內容？

為 '？ ' 中的寄件者影像： 為寄件者，您應該驗證與 SPF 或 DKIM 郵件。

針對透過標記： 為寄件者，您應該確定是在 DKIM 簽章的網域或 SMTP 郵件從相同，或是的在 [從地址的網域子網域。

### <a name="does-outlookcom-and-outlook-on-the-web-show-this-for-every-message-that-doesnt-pass-authentication"></a>Outlook.com 和 Outlook 網頁顯示執行此動作不會通過驗證每個郵件嗎？

不是一定。 Outlook.com 和網頁型 Outlook 可能已驗證寄件者的郵件內的其他屬性。

## <a name="related-topics"></a>相關主題

[協助保護您的 Outlook.com 電子郵件帳戶](https://support.office.com/article/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[處理濫用、 網路釣魚，或在 Outlook.com 中詐騙](https://support.office.com/article/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[篩選垃圾電子郵件和網頁型 Outlook 中的垃圾郵件](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)
