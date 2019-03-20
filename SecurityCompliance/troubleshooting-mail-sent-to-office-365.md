---
title: 將疑難排解郵件傳送艮 Office 365
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 5/2/2016
ms.audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
ms.collection:
- M365-security-compliance
description: 本文提供寄件者嘗試傳送電子郵件給 Office 365 和 Office 365 客戶的大量郵件的最佳作法中的收件匣時遇到問題的疑難排解資訊。
ms.openlocfilehash: ac465e7ef42b9cfeb2587481202fab1b5adb5f75
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/20/2019
ms.locfileid: "30692102"
---
# <a name="troubleshooting-mail-sent-to-office-365"></a>將疑難排解郵件傳送艮 Office 365

本文提供寄件者嘗試傳送電子郵件給 Office 365 和 Office 365 客戶的大量郵件的最佳作法中的收件匣時遇到問題的疑難排解資訊。
  
## <a name="troubleshooting-common-problems-with-mail-delivery-to-office-365"></a>疑難排解郵件傳遞到 Office 365 的常見問題

選擇 [從下列其中一個這些常遇到的問題。
  
- [您管理您的 IP 和網域的傳送信譽嗎？](troubleshooting-mail-sent-to-office-365.md#ManageRep)
    
- [從新的 IP 位址是您傳送電子郵件？](troubleshooting-mail-sent-to-office-365.md#NewIPs)
    
- [確認您的 DNS 設定正確](troubleshooting-mail-sent-to-office-365.md#ConfirmDNSsetup)
    
- [確定，您不要未通告自行為非可路由的 IP](troubleshooting-mail-sent-to-office-365.md#NoReverseDNS)
    
- [您收到未傳遞回報 (NDR) 時傳送電子郵件給 Office 365 中的使用者](troubleshooting-mail-sent-to-office-365.md#NDRInbound)
    
- [我的電子郵件進入 EOP 中的收件者的垃圾郵件資料夾中](troubleshooting-mail-sent-to-office-365.md#JunkMailBox)
    
- [從我的 IP 位址的流量節流透過 EOP](troubleshooting-mail-sent-to-office-365.md#AllowEOPIPs)
    
### <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a>您管理您的 IP 和網域的傳送信譽嗎？
<a name="ManageRep"> </a>

EOP 篩選技術被設計來提供 Microsoft Office 365，以及 Exchange Server、 Microsoft Office Outlook 及 Windows Live Mail 等其他 Microsoft 產品的反垃圾郵件保護。 我們也會利用 SPF，DKIM、 DMARC;電子郵件驗證技術，可協助解決問題的詐騙和網路釣魚藉由驗證傳送電子郵件的網域有權執行這項操作。 EOP 篩選會受到許多因素相關的傳送端 IP、 網域、 驗證、 清單正確性、 抱怨率、 內容等等。 這些項目，其中一個主要因素，向寄件者信譽下主導及其能夠傳送電子郵件是垃圾郵件抱怨比率。 
  
### <a name="are-you-sending-email-from-new-ip-addresses"></a>從新的 IP 位址是您傳送電子郵件？
<a name="NewIPs"> </a>

IP 位址不先前用來傳送電子郵件通常不需要在我們的系統，建置任何信譽。 因此，從新 Ip 的電子郵件會更有可能發生傳遞問題。 一旦 IP 具有內建信譽不傳送垃圾郵件，EOP 通常會允許較佳的電子郵件傳遞經驗。
  
新增的網域的一般驗證下現有的 SPF 記錄的新 Ip 體驗繼承的網域的傳送信譽一些的好處。 如果您的網域有良好傳送信譽新 Ip 可能會遇到的時間更需要費時。 新的 IP 可以預期會完全 ramped 幾週或更快速地根據磁碟區、 清單正確性和垃圾郵件抱怨率。
  
### <a name="confirm-that-your-dns-is-set-up-correctly"></a>確認您的 DNS 設定正確
<a name="ConfirmDNSsetup"> </a>

如需如何建立及維護 DNS 記錄，其中包括郵件路由，所需的 MX 記錄指示您必須連絡您的 DNS 主機服務提供者。
  
### <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a>確定，您不要未通告自行為非可路由的 IP
<a name="NoReverseDNS"> </a>

我們可能不會接受來自失敗反向 DNS 查閱寄件者的電子郵件。 在某些情況下，合法的寄件者通知本身不正確地為非網際網路可路由傳送 IP 嘗試開啟的連線至 EOP 時。 IP 位址，則保留給私人 （非可路由） 的網路功能包括：
  
- 192.168.0.0/16 (或 192.168.0.0-192.168.255.255)
    
- 10.0.0.0/8 (或 10.0.0.0-10.255.255.255)
    
- 172.16.0.0/11 (或 172.16.0.0-172.31.255.255)
    
### <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a>您收到未傳遞回報 (NDR) 時傳送電子郵件給 Office 365 中的使用者
<a name="NDRInbound"> </a>

某些傳遞問題是由 Microsoft 遭到封鎖的寄件者的 IP 位址的結果，或是因為使用者帳戶視為禁用的寄件者，因為先前的垃圾郵件活動。 如果您有收到錯誤 NDR，先遵循解決問題，請將 NDR 訊息的指示進行。 
  
在您收到的錯誤的詳細資訊，請參閱中[的 Dsn 和 Ndr 內部部署 Exchange 2013 和 Office 365 中](http://technet.microsoft.com/library/8e91de84-76fa-49b2-898c-c5eface76560.aspx)的 SMTP 錯誤碼的完整清單。
  
 例如，如果您收到下列 NDR，它表示傳送端 IP 位址已封鎖的 Microsoft。 
  
 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`
  
若要要求從此清單時移除，您可以[使用取消列出入口網站將您自己從 Office 365 封鎖寄件者清單移除](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)。
  
### <a name="my-email-landed-in-the-recipients-junk-folder-in-eop"></a>我的電子郵件進入 EOP 中的收件者的垃圾郵件資料夾中
<a name="JunkMailBox"> </a>

如果郵件被誤判為垃圾郵件透過 EOP，您可以使用收件者送出此誤判郵件給 Microsoft 垃圾郵件分析小組，小組會評估和分析此郵件。 我們可以根據分析的結果調整全服務的垃圾郵件內容篩選規則，以便允許郵件通行。 您可以使用電子郵件來提交郵件提交給 Microsoft，不應歸類為垃圾郵件。 這麼做時，請務必使用下列程序中的步驟。
  
### <a name="to-use-email-to-submit-false-positive-messages-to-the-microsoft-spam-analysis-team"></a>若要使用電子郵件來提交誤判的郵件給 Microsoft 垃圾郵件分析小組

1. 儲存您想要當作非垃圾郵件提交的郵件。
    
2. 建立新的空白郵件，然後在其中附加非垃圾郵件。
    
    如有需要您可以附加多個非垃圾郵件。
    
3. 複製原始郵件的主旨行並貼到新郵件的主旨行中。
    
    > [!IMPORTANT]
    > 將新郵件的內文保留空白。 
  
4. 將新郵件傳送到 [not_junk@office365.microsoft.com](mailto:not_junk@office365.microsoft.com)。
    
### <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a>從我的 IP 位址的流量節流透過 EOP
<a name="AllowEOPIPs"> </a>

如果您收到 NDR，以指出 EOP 從您的 IP 位址會受到節流透過 EOP，例如：
  
 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`
  
因為已偵測到可疑活動來自 IP 位址，而且它已暫時限制正在深入評估時，您會收到 NDR。 如果透過評估清除懷疑，則會立刻得以實現這項限制。
  
### <a name="i-cant-receive-email-from-senders-in-office-365"></a>我無法接收電子郵件從 Office 365 中的寄件者
<a name="AllowEOPIPs"> </a>

 若要從我們的使用者接收郵件，請確定您的網路允許來自 EOP 使用我們的資料中心 IP 位址的連線。 如需詳細資訊，請參閱 < <b0>Exchange Online Protection IP 位址</b0>。 
  
## <a name="best-practices-for-bulk-emailing-to-office-365-users"></a>大量以電子郵件傳送給 Office 365 使用者的最佳做法
<a name="BulkMailer"> </a>

如果您經常進行大量電子郵件行銷活動，Office 365 使用者，而且想要確保您的電子郵件送達安全即時而可靠的方式，請遵循本節中的提示。
  
### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a>確定 [從： 名稱會反映出誰傳送給郵件

查看郵件的簡短摘要是關於，和郵件內文應清楚且簡潔地指出供應項目、 服務或產品為何有關，應該是主旨。 例如：
  
修正
  
 ` From: marketing@shoppershandbag.com `
  
 `Subject: Updated catalog for the Christmas season!`
  
不正確
  
 `From: someone@outlook.com`
  
 `Subject: Catalogs`
  
更容易讓其他人知道您是誰，而您所執行的動作、 較少的困難度您傳遞到大部分的垃圾郵件篩選器。
  
### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a>一律包含活動電子郵件中的 [取消訂閱選項

行銷電子郵件，尤其是新聞稿、 應該一律包含取消訂閱未來的電子郵件的方式。 例如：
  
 `This email was sent to example@contoso.com by sender@fabrikam.com.`
  
 `Update Profile/Email Address | Instant removal with SafeUnsubscribe™ | Privacy Policy`
  
某些寄件者藉由要求收件者傳送一封電子郵件給特定別名與 「 取消訂閱 「 主旨中包含此選項。 這不是優先於按一下上述範例中。 如果您選擇需要收件者傳送郵件，確保當他們按一下連結時，所有必要的欄位會預先填入。
  
### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a>用於行銷電子郵件或電子報註冊雙重加入確認程序集選項

如果貴公司需要或鼓勵使用者註冊其連絡人資訊才可存取您的產品或服務，建議使用這個業界最佳作法。 某些公司使其作法是自動註冊其使用者行銷電子郵件或 e-電子報期間註冊程序，但這會被視為可疑行銷作法是在世界中的電子郵件篩選。
  
註冊過程中，如果的"為 [是]，請傳送您的新聞稿給我 」 或 「 為 [是]，請傳送給我特別優惠"] 核取方塊已選取預設，不請密切注意的使用者可能會不小心註冊行銷電子郵件或不是這樣的電子報要接收。
  
 我們建議雙重加入確認程序集選項相反地，這表示行銷電子郵件或電子報的核取方塊會依預設已取消核取。 此外，一旦註冊表單已送出，驗證電子郵件傳送給使用者，並讓他們能確認其決策，以接收行銷電子郵件的 URL。 
  
 這有助於確保，僅限的使用者想要接收行銷電子郵件已註冊之電子郵件，隨後清除任何可疑的電子郵件行銷作法傳送公司。 
  
### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a>確保電子郵件訊息內容是透明和追蹤

同樣重要會傳送電子郵件的方式是所包含的內容。 當建立電子郵件內容，請使用下列最佳作法以確保您的電子郵件未標示的電子郵件篩選服務：
  
- 當電子郵件訊息要求收件者加入通訊錄中的寄件者，它應該清楚狀態，這類巨集指令並不保證郵件的傳遞。
    
- 郵件內文中包含的重新導向應該類似和一致，且不多，具有不同。 在此上下文中重新導向是指開訊息，例如連結與文件的任何值。 如果您有很多廣告或取消訂閱連結或更新設定檔的連結，請他們應該所有指向相同的網域。 例如：
    
    修正
    
     `unsubscribe.bulkmailer.com`
    
     `profile.bulkmailer.com`
    
     `options.bulkmailer.com`
    
    不正確
    
     `unsubscribe.bulkmailer.com`
    
     `profiles.excite.com`
    
     `options.yahoo.com`
    
- 避免使用大型影像和附件，或是察覺組成映像的郵件內容。
    
- 您的公眾隱私權或 P3P 設定應該清楚狀態追蹤像素 （web bug 或指標） 的目前狀態。
    
### <a name="remove-incorrect-email-aliases-from-your-databases"></a>從資料庫移除不正確的電子郵件別名

在您建立退回後的資料庫中的任何電子郵件別名不是必要的並透過電子郵件篩選服務將外寄的電子郵件放在進一步審查的風險。 請確定您的電子郵件資料庫是最新狀態。
  

