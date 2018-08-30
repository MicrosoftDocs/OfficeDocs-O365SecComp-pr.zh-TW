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
# <a name="how-office-365-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="e41a9-103">Office 365 來阻止網路釣魚 From 地址的驗證</span><span class="sxs-lookup"><span data-stu-id="e41a9-103">How Office 365 validates the From address to prevent phishing</span></span>

<span data-ttu-id="e41a9-p101">Office 365 和 Outlook.com 電子郵件帳戶收到逐漸大量的網路釣魚攻擊。網路釣客使用的其中一種技術已傳送郵件的 [從具有值： 不符合[RFC 5322](https://tools.ietf.org/html/rfc5322)的地址。From： 地址也稱為 5322.From 地址。若要避免在這種類型的網路釣魚、 Office 365 及 Outlook.com 需要包含符合 RFC 服務所收到的訊息從： 解決本文所述。</span><span class="sxs-lookup"><span data-stu-id="e41a9-p101">Office 365 and Outlook.com email accounts receive an increasingly large number of phishing attacks. One technique phishers use is to send messages that have values for the From: address that are not compliant with [RFC 5322](https://tools.ietf.org/html/rfc5322). The From: address is also called the 5322.From address. To help prevent this type of phishing, Office 365 and Outlook.com require messages received by the service to include an RFC-compliant From: address as described in this article.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e41a9-p102">本文中的資訊需要有基本了解一般的電子郵件地址格式。如需詳細資訊，請參閱[RFC 5322](https://tools.ietf.org/html/rfc5322) （特別是章節 3.2.3、 3.4、 及 3.4.1）、 [RFC 5321](https://tools.ietf.org/html/rfc5321)，以及[RFC 3696](https://tools.ietf.org/html/rfc3696)。本文章是關於 5322.From 地址原則強制執行。本文不需 5321.MailFrom 地址。</span><span class="sxs-lookup"><span data-stu-id="e41a9-p102">The information in this article requires you to have a basic understanding of the general format of email addresses. For more information, see [RFC 5322](https://tools.ietf.org/html/rfc5322) (particularly sections 3.2.3, 3.4, and 3.4.1), [RFC 5321](https://tools.ietf.org/html/rfc5321), as well as [RFC 3696](https://tools.ietf.org/html/rfc3696). This article is about policy enforcement for the 5322.From address. This article is not about the 5321.MailFrom address.</span></span> 
  
<span data-ttu-id="e41a9-p103">總是會有一些仍繼續傳送"合法 」 的電子郵件訊息已遺失某些舊版電子郵件伺服器在網際網路上或格式不正確的： 地址。如果定期收到電子郵件中使用這些舊版系統的組織，鼓勵這些組織来更新其遵守摩登的安全性標準部署郵件伺服器。</span><span class="sxs-lookup"><span data-stu-id="e41a9-p103">Unfortunately, there are still some legacy email servers on the Internet that continue to send "legitimate" email messages that have a missing or malformed From: address. If you regularly receive email from organizations that use these legacy systems, encourage those organizations to update their mail servers to comply with modern security standards.</span></span>
  
<span data-ttu-id="e41a9-114">Microsoft 會啟動啟用 on 2017 年 11 月 9，本文中所述的原則強制執行。</span><span class="sxs-lookup"><span data-stu-id="e41a9-114">Microsoft will start rolling out enforcement of the policies described in this article on November 9, 2017.</span></span>
  
## <a name="how-office-365-enforces-the-use-of-a-valid-from-address-to-prevent-phishing-attacks"></a><span data-ttu-id="e41a9-115">Office 365 如何強制執行從有效使用： 防止網路釣魚攻擊的地址</span><span class="sxs-lookup"><span data-stu-id="e41a9-115">How Office 365 enforces the use of a valid From: address to prevent phishing attacks</span></span>

<span data-ttu-id="e41a9-p104">Office 365 進行變更其強制執行的 [使用的方法： 它會收到以便搭配成效更佳的訊息中的地址會將您免受網路釣魚攻擊。在本文內容：</span><span class="sxs-lookup"><span data-stu-id="e41a9-p104">Office 365 is making changes to the way it enforces the use of the From: address in messages it receives in order to better protect you from phishing attacks. In this article:</span></span>
  
- [<span data-ttu-id="e41a9-118">所有訊息必須都包含從有效： 地址</span><span class="sxs-lookup"><span data-stu-id="e41a9-118">All messages must include a valid From: address</span></span>](how-office-365-validates-the-from-address.md#MustIncludeFromAddress)
    
- [<span data-ttu-id="e41a9-119">所有訊息必須都包含從有效： 地址</span><span class="sxs-lookup"><span data-stu-id="e41a9-119">All messages must include a valid From: address</span></span>](how-office-365-validates-the-from-address.md#MustIncludeFromAddress)
    
- <span data-ttu-id="e41a9-120">[格式為 [從： 地址如果您未加上的顯示名稱](how-office-365-validates-the-from-address.md#FormatNoDisplayName)</span><span class="sxs-lookup"><span data-stu-id="e41a9-120">[Format of the From: address if you don't include a display name](how-office-365-validates-the-from-address.md#FormatNoDisplayName)</span></span>
    
- <span data-ttu-id="e41a9-121">[格式為 [從： 地址如果加上的顯示名稱](how-office-365-validates-the-from-address.md#FormatDisplayName)</span><span class="sxs-lookup"><span data-stu-id="e41a9-121">[Format of the From: address if you include a display name](how-office-365-validates-the-from-address.md#FormatDisplayName)</span></span>
    
- [<span data-ttu-id="e41a9-122">之有效且無效的範例： 地址</span><span class="sxs-lookup"><span data-stu-id="e41a9-122">Additional examples of valid and invalid From: addresses</span></span>](how-office-365-validates-the-from-address.md#Examples)
    
- [<span data-ttu-id="e41a9-123">抑制自動回覆至自訂網域而不會中斷 From： 原則</span><span class="sxs-lookup"><span data-stu-id="e41a9-123">Suppress auto-replies to your custom domain without breaking the From: policy</span></span>](how-office-365-validates-the-from-address.md#SuppressAutoReply)
    
- [<span data-ttu-id="e41a9-124">Office 365 從覆寫： 處理強制執行原則</span><span class="sxs-lookup"><span data-stu-id="e41a9-124">Overriding the Office 365 From: address enforcement policy</span></span>](how-office-365-validates-the-from-address.md#Override)
    
- [<span data-ttu-id="e41a9-125">預防並防止 cybercrimes Office 365 中的其他方法</span><span class="sxs-lookup"><span data-stu-id="e41a9-125">Other ways to prevent and protect against cybercrimes in Office 365</span></span>](how-office-365-validates-the-from-address.md#OtherProtection)
    
<span data-ttu-id="e41a9-126">另一位使用者代表傳送不會受到此變更，如需詳細資訊，請閱讀 Terry Zink 部落格"[不要我們所謂當我們參照 '寄件者 」 的電子郵件？](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)"。</span><span class="sxs-lookup"><span data-stu-id="e41a9-126">Sending on behalf of another user is not affected by this change, for more details, read Terry Zink's blog "[What do we mean when we refer to the 'sender' of an email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)".</span></span>
  
### <a name="all-messages-must-include-a-valid-from-address"></a><span data-ttu-id="e41a9-127">所有訊息必須都包含從有效： 地址</span><span class="sxs-lookup"><span data-stu-id="e41a9-127">All messages must include a valid From: address</span></span>
<span data-ttu-id="e41a9-128"><a name="MustIncludeFromAddress"> </a></span><span class="sxs-lookup"><span data-stu-id="e41a9-128"></span></span>

<span data-ttu-id="e41a9-p105">某些自動化的郵件不包括 From： 解決他們所傳送時。在過去，Office 365 或 Outlook.com 時收到的郵件而不從： 地址服務新增下列預設的從： 才能進行可傳送作業郵件的地址：</span><span class="sxs-lookup"><span data-stu-id="e41a9-p105">Some automated messages don't include a From: address when they are sent. In the past, when Office 365 or Outlook.com received a message without a From: address, the service added the following default From: address to the message in order to make it deliverable:</span></span>
  
```
From: <>
```

<span data-ttu-id="e41a9-p106">啟動 2017 年 11 月 9 Office 365 將會啟用變更其資料中心及郵件伺服器以將強制執行新的規則出郵件而不從： 位址就不再接受由 Office 365 或 Outlook.com。而所有 Office 365 所收到的訊息必須已經都包含從有效： 地址。否則，郵件將傳送至 Outlook.com 和 Office 365 中的垃圾電子郵件] 或 [刪除的郵件資料夾。</span><span class="sxs-lookup"><span data-stu-id="e41a9-p106">Starting November 9, 2017, Office 365 will be rolling out changes to its datacenters and mail servers which will enforce a new rule where messages without a From: address will no longer be accepted by Office 365 or Outlook.com. Instead, all messages received by Office 365 must already contain a valid From: address. Otherwise, the message will be sent to either the Junk Email or Deleted Items folders in Outlook.com and Office 365.</span></span> 
  
### <a name="syntax-overview-valid-format-for-the-from-address-for-office-365"></a><span data-ttu-id="e41a9-134">語法概觀 （英文): 從有效格式： Office 365 的地址</span><span class="sxs-lookup"><span data-stu-id="e41a9-134">Syntax overview: Valid format for the From: address for Office 365</span></span>
<span data-ttu-id="e41a9-135"><a name="SyntaxOverviewFromAddress"> </a></span><span class="sxs-lookup"><span data-stu-id="e41a9-135"></span></span>

<span data-ttu-id="e41a9-p107">從值的格式： 跨數個 Rfc 定義地址的詳細資訊。有許多變化位址與項目可能會視為有效或無效。若要保留簡單，Microsoft 建議您使用下列格式和定義：</span><span class="sxs-lookup"><span data-stu-id="e41a9-p107">The format for the value of the From: address is defined in detail across several RFCs. There are many variations on addressing and what may be considered valid or invalid. To keep it simple, Microsoft recommends that you use the following format and definitions:</span></span>
  
```
From: "displayname " <emailaddress >
```

<span data-ttu-id="e41a9-139">其中：</span><span class="sxs-lookup"><span data-stu-id="e41a9-139">Where:</span></span>
  
- <span data-ttu-id="e41a9-p108">（選用） *displayname*是說明擁有人的電子郵件地址的片語。例如，這可能會更容易記住的名稱來描述寄件者比信箱的名稱。使用顯示名稱是選擇性的。不過，如果您選擇使用的顯示名稱、 Microsoft 建議的您一律括住它引號內所示。</span><span class="sxs-lookup"><span data-stu-id="e41a9-p108">(Optional)  *displayname*  is a phrase that describes the owner of the email address. For example, this might be a more user-friendly name to describe the sender than the name of the mailbox. Using a display name is optional. However, if you choose to use a display name, Microsoft recommends that you always enclose it within quotation marks as shown.</span></span> 
    
- <span data-ttu-id="e41a9-144">（必要） *emailaddress*是由組成：</span><span class="sxs-lookup"><span data-stu-id="e41a9-144">(Required)  *emailaddress*  is made up of:</span></span> 
    
  ```
  local-part @domain
  ```

    <span data-ttu-id="e41a9-145">其中：</span><span class="sxs-lookup"><span data-stu-id="e41a9-145">Where:</span></span>
    
  - <span data-ttu-id="e41a9-p109">（必要） *本機部分*是一個字串，識別位址相關聯的信箱。這是唯一的網域。通常，信箱擁有者的使用者名稱或 GUID 會當做值為本機組件。</span><span class="sxs-lookup"><span data-stu-id="e41a9-p109">(Required)  *local-part*  is a string that identifies the mailbox associated with the address. This is unique within the domain. Often, the mailbox owner's username or GUID is used as the value for the local-part.</span></span> 
    
  - <span data-ttu-id="e41a9-149">（必要） *網域*是主控的電子郵件地址本機組件所識別信箱的郵件伺服器的完整網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="e41a9-149">(Required)  *domain*  is the fully-qualified domain name (FQDN) of the mail server that hosts the mailbox identified by the local-part of the email address.</span></span> 
    
### <a name="format-of-the-from-address-if-you-dont-include-a-display-name"></a><span data-ttu-id="e41a9-150">格式為 [從： 地址如果您未加上的顯示名稱</span><span class="sxs-lookup"><span data-stu-id="e41a9-150">Format of the From: address if you don't include a display name</span></span>
<span data-ttu-id="e41a9-151"><a name="FormatNoDisplayName"> </a></span><span class="sxs-lookup"><span data-stu-id="e41a9-151"></span></span>

<span data-ttu-id="e41a9-p110">從正確格式的： 不包含的顯示名稱的地址包含只有單一電子郵件地址包含或不包含角括弧。Microsoft 建議您請勿以空格分開角括弧。此外，不包含任何項目之後的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="e41a9-p110">A properly formatted From: address that does not include a display name includes only a single email address with or without angle brackets. Microsoft recommends that you do not separate the angle brackets with spaces. In addition, don't include anything after the email address.</span></span>
  
<span data-ttu-id="e41a9-155">下列範例為有效：</span><span class="sxs-lookup"><span data-stu-id="e41a9-155">The following examples are valid:</span></span>
  
```
From: sender@contoso.com
```

```
From: <sender@contoso.com>
```

<span data-ttu-id="e41a9-156">下列範例會為有效，但不是建議使用，因為它包含角括弧括與電子郵件地址之間的空格：</span><span class="sxs-lookup"><span data-stu-id="e41a9-156">The following example is valid but not recommended because it contains spaces between the angle brackets and the email address:</span></span>
  
```
From: < sender@contoso.com >
```

<span data-ttu-id="e41a9-157">下列範例中無效，因為它會包含文字後的電子郵件地址：</span><span class="sxs-lookup"><span data-stu-id="e41a9-157">The following example is invalid because it contains text after the email address:</span></span>
  
```
From: "Office 365" <sender@contoso.com> (Sent by a process)
```

### <a name="format-of-the-from-address-if-you-include-a-display-name"></a><span data-ttu-id="e41a9-158">格式為 [從： 地址如果加上的顯示名稱</span><span class="sxs-lookup"><span data-stu-id="e41a9-158">Format of the From: address if you include a display name</span></span>
<span data-ttu-id="e41a9-159"><a name="FormatDisplayName"> </a></span><span class="sxs-lookup"><span data-stu-id="e41a9-159"></span></span>

<span data-ttu-id="e41a9-160">針對從： 包括之顯示名稱值的地址，適用下列規則：</span><span class="sxs-lookup"><span data-stu-id="e41a9-160">For From: addresses that include a value for the display name, the following rules apply:</span></span>
  
- <span data-ttu-id="e41a9-p111">如果寄件者地址包含顯示名稱，並顯示名稱包含逗點，然後顯示名稱必須是引號括。例如：</span><span class="sxs-lookup"><span data-stu-id="e41a9-p111">If the sender address includes a display name, and the display name includes a comma, then the display name must be enclosed within quotation marks. For example:</span></span>
    
    <span data-ttu-id="e41a9-163">下列範例會為有效：</span><span class="sxs-lookup"><span data-stu-id="e41a9-163">The following example is valid:</span></span>
    
  ```
  From: "Sender, Example" <sender.example@contoso.com>
  ```

    <span data-ttu-id="e41a9-164">下列範例不是有效的：</span><span class="sxs-lookup"><span data-stu-id="e41a9-164">The following example is not valid:</span></span>
    
  ```
  From: Sender, Example <sender.example@contoso.com>
  ```

    <span data-ttu-id="e41a9-165">不該顯示名稱如果含有逗點住引號括住的顯示名稱是根據 RFC 5322 無效。</span><span class="sxs-lookup"><span data-stu-id="e41a9-165">Not enclosing the display name in quotation marks if that display name includes a comma is invalid according to RFC 5322.</span></span>
    
    <span data-ttu-id="e41a9-166">最佳作法是保留的引號括住的顯示名稱是否有是逗號內的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="e41a9-166">As a best practice, put quote marks around the display name regardless of whether or not there is a comma within the display name.</span></span>
    
- <span data-ttu-id="e41a9-167">如果寄件者地址包含的顯示名稱、 電子郵件地址必須內角括弧括住。</span><span class="sxs-lookup"><span data-stu-id="e41a9-167">If the sender address includes a display name, then the email address must be enclosed within angle brackets.</span></span>
    
    <span data-ttu-id="e41a9-168">最佳作法是 Microsoft 強烈建議您插入的顯示名稱和電子郵件地址之間的空間。</span><span class="sxs-lookup"><span data-stu-id="e41a9-168">As a best practice, Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>
    
### <a name="additional-examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="e41a9-169">之有效且無效的範例： 地址</span><span class="sxs-lookup"><span data-stu-id="e41a9-169">Additional examples of valid and invalid From: addresses</span></span>
<span data-ttu-id="e41a9-170"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="e41a9-170"></span></span>

- <span data-ttu-id="e41a9-171">有效：</span><span class="sxs-lookup"><span data-stu-id="e41a9-171">Valid:</span></span>
    
  ```
  From: "Office 365" <sender@contoso.com>
  ```

- <span data-ttu-id="e41a9-p112">不是正確。電子郵件地址不是以角括弧括：</span><span class="sxs-lookup"><span data-stu-id="e41a9-p112">Invalid. The email address is not enclosed with angle brackets:</span></span>
    
  ```
  From: Office 365 sender@contoso.com
  ```

- <span data-ttu-id="e41a9-p113">有效，但不是建議使用。顯示名稱不是以括住。最佳作法是一律放入引號括住的顯示名稱：</span><span class="sxs-lookup"><span data-stu-id="e41a9-p113">Valid, but not recommended. The display name is not in quotes. As a best practice, always put quotation marks around the display name:</span></span>
    
  ```
  From: Office 365 <sender@contoso.com>
  ```

- <span data-ttu-id="e41a9-p114">不是正確。每個項目括引號，而不只是顯示名稱：</span><span class="sxs-lookup"><span data-stu-id="e41a9-p114">Invalid. Everything is enclosed within quotation marks, not just the display name:</span></span>
    
  ```
  From: "Office 365 <sender@contoso.com>"
  ```

- <span data-ttu-id="e41a9-p115">不是正確。沒有繞電子郵件地址的角括弧括：</span><span class="sxs-lookup"><span data-stu-id="e41a9-p115">Invalid. There are no angle brackets around the email address:</span></span>
    
  ```
  From: "Office 365 <sender@contoso.com>" sender@contoso.com
  ```

- <span data-ttu-id="e41a9-p116">不是正確。沒有顯示名稱] 和 [左的角括弧之間空間：</span><span class="sxs-lookup"><span data-stu-id="e41a9-p116">Invalid. There is no space between the display name and left angle bracket:</span></span>
    
  ```
  From: Office 365<sender@contoso.com>
  ```

- <span data-ttu-id="e41a9-p117">不是正確。結束 quotation mark 周圍的顯示名稱和左的角括弧之間沒有任何空格。</span><span class="sxs-lookup"><span data-stu-id="e41a9-p117">Invalid. There is no space between the closing quotation mark around the display name and the left angle bracket.</span></span>
    
  ```
  From: "Office 365"<sender@contoso.com>
  ```

### <a name="suppress-auto-replies-to-your-custom-domain-without-breaking-the-from-policy"></a><span data-ttu-id="e41a9-185">抑制自動回覆至自訂網域而不會中斷 From： 原則</span><span class="sxs-lookup"><span data-stu-id="e41a9-185">Suppress auto-replies to your custom domain without breaking the From: policy</span></span>
<span data-ttu-id="e41a9-186"><a name="SuppressAutoReply"> </a></span><span class="sxs-lookup"><span data-stu-id="e41a9-186"></span></span>

<span data-ttu-id="e41a9-p118">具有新從： 原則強制執行您無法再使用從： \< \>抑制自動回覆。而被必須設定為 null 的 MX 記錄的自訂網域。</span><span class="sxs-lookup"><span data-stu-id="e41a9-p118">With the new From: policy enforcement, you can no longer use From: \<\> to suppress auto-replies. Instead, you need to set up a null MX record for your custom domain.</span></span>
  
<span data-ttu-id="e41a9-p119">郵件交換程式 (MX) 記錄會在識別接收網域的郵件的郵件伺服器的 DNS a 資源記錄。自動回覆 （和所有回覆） 是自然抑制了因為不未回應伺服器可將郵件傳送任何已發佈的位址。</span><span class="sxs-lookup"><span data-stu-id="e41a9-p119">The mail exchanger (MX) record is a resource record in DNS that identifies the mail server that receives mail for your domain. Auto-replies (and all replies) are naturally suppressed because there is no published address to which the responding server can send messages.</span></span>
  
<span data-ttu-id="e41a9-191">當您設定為 null 的 MX 記錄的自訂網域：</span><span class="sxs-lookup"><span data-stu-id="e41a9-191">When you set up a null MX record for your custom domain:</span></span>
  
- <span data-ttu-id="e41a9-p120">選擇 [網域中的用來傳送訊息不會接受 （接收） 電子郵件。例如，如果您的主要網域是 contoso.com，您可能會選擇 noreply.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="e41a9-p120">Choose a domain from which to send messages that doesn't accept (receive) email. For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>
    
- <span data-ttu-id="e41a9-p121">設定您的網域的 null MX 記錄。Null 的 MX 記錄所組成單一的點，例如：</span><span class="sxs-lookup"><span data-stu-id="e41a9-p121">Set up the null MX record for your domain. A null MX record consists of a single dot, for example:</span></span>
    
  ```
  noreply.contoso.com IN MX .
  ```

<span data-ttu-id="e41a9-196">如需發佈 null MX 的詳細資訊，請參閱[RFC 7505](https://tools.ietf.org/html/rfc7505)。</span><span class="sxs-lookup"><span data-stu-id="e41a9-196">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>
  
### <a name="overriding-the-office-365-from-address-enforcement-policy"></a><span data-ttu-id="e41a9-197">Office 365 從覆寫： 處理強制執行原則</span><span class="sxs-lookup"><span data-stu-id="e41a9-197">Overriding the Office 365 From: address enforcement policy</span></span>
<span data-ttu-id="e41a9-198"><a name="Override"> </a></span><span class="sxs-lookup"><span data-stu-id="e41a9-198"></span></span>

<span data-ttu-id="e41a9-199">Roll 超出新原則完成後，您可以僅略過您收到來自 Office 365 使用其中一種方法的內送郵件此原則：</span><span class="sxs-lookup"><span data-stu-id="e41a9-199">Once roll out of the new policy is complete, you can only bypass this policy for inbound mail you receive from Office 365 by using one of the following methods:</span></span> 
  
- <span data-ttu-id="e41a9-200">IP 允許清單</span><span class="sxs-lookup"><span data-stu-id="e41a9-200">IP allow lists</span></span>
    
- <span data-ttu-id="e41a9-201">Exchange Online 郵件流程規則</span><span class="sxs-lookup"><span data-stu-id="e41a9-201">Exchange Online mail flow rules</span></span>
    
<span data-ttu-id="e41a9-p122">Microsoft 強烈建議針對覆寫 From 的強制執行： 原則。覆寫此原則可增加的垃圾郵件的曝光度、 網路釣魚及其他 cybercrimes 貴組織的風險。</span><span class="sxs-lookup"><span data-stu-id="e41a9-p122">Microsoft strongly recommends against overriding the enforcement of the From: policy. Overriding this policy can increase your organization's risk of exposure to spam, phishing, and other cybercrimes.</span></span>
  
<span data-ttu-id="e41a9-p123">您不能覆寫此原則您在 Office 365 中傳送的輸出郵件。此外，Outlook.com 不允許覆寫任何類型，甚至是透過支援。</span><span class="sxs-lookup"><span data-stu-id="e41a9-p123">You cannot override this policy for outbound mail you send in Office 365. In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span> 
  
### <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-office-365"></a><span data-ttu-id="e41a9-206">預防並防止 cybercrimes Office 365 中的其他方法</span><span class="sxs-lookup"><span data-stu-id="e41a9-206">Other ways to prevent and protect against cybercrimes in Office 365</span></span>
<span data-ttu-id="e41a9-207"><a name="OtherProtection"> </a></span><span class="sxs-lookup"><span data-stu-id="e41a9-207"></span></span>

<span data-ttu-id="e41a9-208">如需有關可增強像網路釣魚 cybercrimes 對貴組織的方式的詳細資訊，垃圾郵件、 資料缺口與其他的威脅，請參閱 ＜ [Security for Office 365 的最佳作法](https://support.office.com/article/9295e396-e53d-49b9-ae9b-0b5828cdedc3)。</span><span class="sxs-lookup"><span data-stu-id="e41a9-208">For more information on how you can strengthen your organization against cybercrimes like phishing, spamming, data breaches, and other threats, see [Security best practices for Office 365](https://support.office.com/article/9295e396-e53d-49b9-ae9b-0b5828cdedc3).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e41a9-209">相關主題</span><span class="sxs-lookup"><span data-stu-id="e41a9-209">Related Topics</span></span>

[<span data-ttu-id="e41a9-210">非法回應郵件與 EOP</span><span class="sxs-lookup"><span data-stu-id="e41a9-210">Backscatter messages and EOP</span></span>](https://technet.microsoft.com/en-us/library/dn499795%28v=exchg.150%29.aspx)
  

