---
title: Office 365 來阻止網路釣魚 From 地址的驗證
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/11/2017
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
description: 若要協助防止網路釣魚，Office 365 及 Outlook.com 現在需要的 RFC 規範從： 地址。
ms.openlocfilehash: 562e08aa54cb6544beccb6f0e8760735f67b834b
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526193"
---
# <a name="how-office-365-validates-the-from-address-to-prevent-phishing"></a>Office 365 來阻止網路釣魚 From 地址的驗證

Office 365 和 Outlook.com 電子郵件帳戶收到逐漸大量的網路釣魚攻擊。網路釣客使用的其中一種技術已傳送郵件的 [從具有值： 不符合[RFC 5322](https://tools.ietf.org/html/rfc5322)的地址。From： 地址也稱為 5322.From 地址。若要避免在這種類型的網路釣魚、 Office 365 及 Outlook.com 需要包含符合 RFC 服務所收到的訊息從： 解決本文所述。
  
> [!NOTE]
> 本文中的資訊需要有基本了解一般的電子郵件地址格式。如需詳細資訊，請參閱[RFC 5322](https://tools.ietf.org/html/rfc5322) （特別是章節 3.2.3、 3.4、 及 3.4.1）、 [RFC 5321](https://tools.ietf.org/html/rfc5321)，以及[RFC 3696](https://tools.ietf.org/html/rfc3696)。本文章是關於 5322.From 地址原則強制執行。本文不需 5321.MailFrom 地址。 
  
總是會有一些仍繼續傳送"合法 」 的電子郵件訊息已遺失某些舊版電子郵件伺服器在網際網路上或格式不正確的： 地址。如果定期收到電子郵件中使用這些舊版系統的組織，鼓勵這些組織来更新其遵守摩登的安全性標準部署郵件伺服器。
  
Microsoft 會啟動啟用 on 2017 年 11 月 9，本文中所述的原則強制執行。
  
## <a name="how-office-365-enforces-the-use-of-a-valid-from-address-to-prevent-phishing-attacks"></a>Office 365 如何強制執行從有效使用： 防止網路釣魚攻擊的地址

Office 365 進行變更其強制執行的 [使用的方法： 它會收到以便搭配成效更佳的訊息中的地址會將您免受網路釣魚攻擊。在本文內容：
  
- [所有訊息必須都包含從有效： 地址](how-office-365-validates-the-from-address.md#MustIncludeFromAddress)
    
- [所有訊息必須都包含從有效： 地址](how-office-365-validates-the-from-address.md#MustIncludeFromAddress)
    
- [格式為 [從： 地址如果您未加上的顯示名稱](how-office-365-validates-the-from-address.md#FormatNoDisplayName)
    
- [格式為 [從： 地址如果加上的顯示名稱](how-office-365-validates-the-from-address.md#FormatDisplayName)
    
- [之有效且無效的範例： 地址](how-office-365-validates-the-from-address.md#Examples)
    
- [抑制自動回覆至自訂網域而不會中斷 From： 原則](how-office-365-validates-the-from-address.md#SuppressAutoReply)
    
- [Office 365 從覆寫： 處理強制執行原則](how-office-365-validates-the-from-address.md#Override)
    
- [預防並防止 cybercrimes Office 365 中的其他方法](how-office-365-validates-the-from-address.md#OtherProtection)
    
另一位使用者代表傳送不會受到此變更，如需詳細資訊，請閱讀 Terry Zink 部落格"[不要我們所謂當我們參照 '寄件者 」 的電子郵件？](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)"。
  
### <a name="all-messages-must-include-a-valid-from-address"></a>所有訊息必須都包含從有效： 地址
<a name="MustIncludeFromAddress"> </a>

某些自動化的郵件不包括 From： 解決他們所傳送時。在過去，Office 365 或 Outlook.com 時收到的郵件而不從： 地址服務新增下列預設的從： 才能進行可傳送作業郵件的地址：
  
```
From: <>
```

啟動 2017 年 11 月 9 Office 365 將會啟用變更其資料中心及郵件伺服器以將強制執行新的規則出郵件而不從： 位址就不再接受由 Office 365 或 Outlook.com。而所有 Office 365 所收到的訊息必須已經都包含從有效： 地址。否則，郵件將傳送至 Outlook.com 和 Office 365 中的垃圾電子郵件] 或 [刪除的郵件資料夾。 
  
### <a name="syntax-overview-valid-format-for-the-from-address-for-office-365"></a>語法概觀 （英文): 從有效格式： Office 365 的地址
<a name="SyntaxOverviewFromAddress"> </a>

從值的格式： 跨數個 Rfc 定義地址的詳細資訊。有許多變化位址與項目可能會視為有效或無效。若要保留簡單，Microsoft 建議您使用下列格式和定義：
  
```
From: "displayname " <emailaddress >
```

其中：
  
- （選用） *displayname*是說明擁有人的電子郵件地址的片語。例如，這可能會更容易記住的名稱來描述寄件者比信箱的名稱。使用顯示名稱是選擇性的。不過，如果您選擇使用的顯示名稱、 Microsoft 建議的您一律括住它引號內所示。 
    
- （必要） *emailaddress*是由組成： 
    
  ```
  local-part @domain
  ```

    其中：
    
  - （必要） *本機部分*是一個字串，識別位址相關聯的信箱。這是唯一的網域。通常，信箱擁有者的使用者名稱或 GUID 會當做值為本機組件。 
    
  - （必要） *網域*是主控的電子郵件地址本機組件所識別信箱的郵件伺服器的完整網域名稱 (FQDN)。 
    
### <a name="format-of-the-from-address-if-you-dont-include-a-display-name"></a>格式為 [從： 地址如果您未加上的顯示名稱
<a name="FormatNoDisplayName"> </a>

從正確格式的： 不包含的顯示名稱的地址包含只有單一電子郵件地址包含或不包含角括弧。Microsoft 建議您請勿以空格分開角括弧。此外，不包含任何項目之後的電子郵件地址。
  
下列範例為有效：
  
```
From: sender@contoso.com
```

```
From: <sender@contoso.com>
```

下列範例會為有效，但不是建議使用，因為它包含角括弧括與電子郵件地址之間的空格：
  
```
From: < sender@contoso.com >
```

下列範例中無效，因為它會包含文字後的電子郵件地址：
  
```
From: "Office 365" <sender@contoso.com> (Sent by a process)
```

### <a name="format-of-the-from-address-if-you-include-a-display-name"></a>格式為 [從： 地址如果加上的顯示名稱
<a name="FormatDisplayName"> </a>

針對從： 包括之顯示名稱值的地址，適用下列規則：
  
- 如果寄件者地址包含顯示名稱，並顯示名稱包含逗點，然後顯示名稱必須是引號括。例如：
    
    下列範例會為有效：
    
  ```
  From: "Sender, Example" <sender.example@contoso.com>
  ```

    下列範例不是有效的：
    
  ```
  From: Sender, Example <sender.example@contoso.com>
  ```

    不該顯示名稱如果含有逗點住引號括住的顯示名稱是根據 RFC 5322 無效。
    
    最佳作法是保留的引號括住的顯示名稱是否有是逗號內的顯示名稱。
    
- 如果寄件者地址包含的顯示名稱、 電子郵件地址必須內角括弧括住。
    
    最佳作法是 Microsoft 強烈建議您插入的顯示名稱和電子郵件地址之間的空間。
    
### <a name="additional-examples-of-valid-and-invalid-from-addresses"></a>之有效且無效的範例： 地址
<a name="Examples"> </a>

- 有效：
    
  ```
  From: "Office 365" <sender@contoso.com>
  ```

- 不是正確。電子郵件地址不是以角括弧括：
    
  ```
  From: Office 365 sender@contoso.com
  ```

- 有效，但不是建議使用。顯示名稱不是以括住。最佳作法是一律放入引號括住的顯示名稱：
    
  ```
  From: Office 365 <sender@contoso.com>
  ```

- 不是正確。每個項目括引號，而不只是顯示名稱：
    
  ```
  From: "Office 365 <sender@contoso.com>"
  ```

- 不是正確。沒有繞電子郵件地址的角括弧括：
    
  ```
  From: "Office 365 <sender@contoso.com>" sender@contoso.com
  ```

- 不是正確。沒有顯示名稱] 和 [左的角括弧之間空間：
    
  ```
  From: Office 365<sender@contoso.com>
  ```

- 不是正確。結束 quotation mark 周圍的顯示名稱和左的角括弧之間沒有任何空格。
    
  ```
  From: "Office 365"<sender@contoso.com>
  ```

### <a name="suppress-auto-replies-to-your-custom-domain-without-breaking-the-from-policy"></a>抑制自動回覆至自訂網域而不會中斷 From： 原則
<a name="SuppressAutoReply"> </a>

具有新從： 原則強制執行您無法再使用從： \< \>抑制自動回覆。而被必須設定為 null 的 MX 記錄的自訂網域。
  
郵件交換程式 (MX) 記錄會在識別接收網域的郵件的郵件伺服器的 DNS a 資源記錄。自動回覆 （和所有回覆） 是自然抑制了因為不未回應伺服器可將郵件傳送任何已發佈的位址。
  
當您設定為 null 的 MX 記錄的自訂網域：
  
- 選擇 [網域中的用來傳送訊息不會接受 （接收） 電子郵件。例如，如果您的主要網域是 contoso.com，您可能會選擇 noreply.contoso.com。
    
- 設定您的網域的 null MX 記錄。Null 的 MX 記錄所組成單一的點，例如：
    
  ```
  noreply.contoso.com IN MX .
  ```

如需發佈 null MX 的詳細資訊，請參閱[RFC 7505](https://tools.ietf.org/html/rfc7505)。
  
### <a name="overriding-the-office-365-from-address-enforcement-policy"></a>Office 365 從覆寫： 處理強制執行原則
<a name="Override"> </a>

Roll 超出新原則完成後，您可以僅略過您收到來自 Office 365 使用其中一種方法的內送郵件此原則： 
  
- IP 允許清單
    
- Exchange Online 郵件流程規則
    
Microsoft 強烈建議針對覆寫 From 的強制執行： 原則。覆寫此原則可增加的垃圾郵件的曝光度、 網路釣魚及其他 cybercrimes 貴組織的風險。
  
您不能覆寫此原則您在 Office 365 中傳送的輸出郵件。此外，Outlook.com 不允許覆寫任何類型，甚至是透過支援。 
  
### <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-office-365"></a>預防並防止 cybercrimes Office 365 中的其他方法
<a name="OtherProtection"> </a>

如需有關可增強像網路釣魚 cybercrimes 對貴組織的方式的詳細資訊，垃圾郵件、 資料缺口與其他的威脅，請參閱 ＜ [Security for Office 365 的最佳作法](https://support.office.com/article/9295e396-e53d-49b9-ae9b-0b5828cdedc3)。
  
## <a name="related-topics"></a>相關主題

[非法回應郵件與 EOP](https://technet.microsoft.com/en-us/library/dn499795%28v=exchg.150%29.aspx)
  

