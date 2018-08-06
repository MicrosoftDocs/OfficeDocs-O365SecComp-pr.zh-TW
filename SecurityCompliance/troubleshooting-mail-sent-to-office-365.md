---
title: 疑難排解郵件傳送給 Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/2/2016
ms.audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
description: 本文提供寄件者嘗試傳送電子郵件給收件匣中 Office 365 與大量郵件給 Office 365 客戶的最佳作法時所發生問題的疑難排解的資訊。
ms.openlocfilehash: 29c30787f493c69eb7d42b8025b25c86acddfff9
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026410"
---
# <a name="troubleshooting-mail-sent-to-office-365"></a>疑難排解郵件傳送給 Office 365

本文提供寄件者嘗試傳送電子郵件給收件匣中 Office 365 與大量郵件給 Office 365 客戶的最佳作法時所發生問題的疑難排解的資訊。
  
## <a name="troubleshooting-common-problems-with-mail-delivery-to-office-365"></a>疑難排解 Office 365 的郵件傳遞的常見問題

選擇其中一個這些常遇到的問題。
  
- [您管理 IP 和網域的已傳送信譽吗？](troubleshooting-mail-sent-to-office-365.md#ManageRep)
    
- [是您傳送電子郵件從新的 IP 位址吗？](troubleshooting-mail-sent-to-office-365.md#NewIPs)
    
- [確認您的 DNS 設定正確](troubleshooting-mail-sent-to-office-365.md#ConfirmDNSsetup)
    
- [請確定該您不要未通告自行為非路由傳送的 IP](troubleshooting-mail-sent-to-office-365.md#NoReverseDNS)
    
- [您收到未傳遞回報 (NDR) 時傳送電子郵件給 Office 365 的使用者](troubleshooting-mail-sent-to-office-365.md#NDRInbound)
    
- [在 EOP 中的收件者垃圾資料夾中的 「 我的電子郵件登陸](troubleshooting-mail-sent-to-office-365.md#JunkMailBox)
    
- [從我的 IP 位址的流量會由 EOP 節流的處理](troubleshooting-mail-sent-to-office-365.md#AllowEOPIPs)
    
### <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a>您管理 IP 和網域的已傳送信譽吗？
<a name="ManageRep"> </a>

EOP 篩選技術的設計被用來提供的 Microsoft Office 365 與 Exchange Server、 Microsoft Office Outlook 和 Windows Live Mail 像其他 Microsoft 產品的反垃圾郵件保護設定。我們也運用 SPF、 DKIM，以及 DMARC;電子郵件詐騙和網路釣魚問題說明地址的驗證技術來確認網域傳送的電子郵件有權執行這項操作。數目相關的傳送端 IP、 網域、 驗證、 清單正確性、 抱怨率、 內容及其他因素會影響 EOP 篩選。這些，其中一個主要因素下寄件者信譽主導和其能夠傳送電子郵件是其垃圾郵件抱怨速率。 
  
### <a name="are-you-sending-email-from-new-ip-addresses"></a>是您傳送電子郵件從新的 IP 位址吗？
<a name="NewIPs"> </a>

IP 位址不先前用來傳送電子郵件通常不需要我們系統中的內建任何信譽。因此，從新的 Ip 的電子郵件是很可能會遇到傳遞問題。一旦 IP 具有內建未傳送垃圾郵件的聲譽、 EOP 通常會允許較佳的電子郵件傳遞經驗。
  
通常會驗證在現有 SPF 記錄下方的網域新增的新 Ip 體驗新增的繼承網域的傳送端信譽的一些優點。如果您的網域具有良好傳送信譽新 Ip 可能會遇到速度較快費時。新的 IP 將能感受到完全 ramped 內幾週或更早根據磁碟區、 清單正確性和垃圾郵件抱怨率。
  
### <a name="confirm-that-your-dns-is-set-up-correctly"></a>確認您的 DNS 設定正確
<a name="ConfirmDNSsetup"> </a>

如需如何建立及維護 DNS 記錄，其中包括所需的郵件路由、 MX 記錄的指示您必須連絡您的 DNS 主機供應商。
  
### <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a>請確定該您不要未通告自行為非路由傳送的 IP
<a name="NoReverseDNS"> </a>

我們可以不接受電子郵件的寄件者失敗反向 DNS 查閱。在某些情況下，合法的寄件者 advertise 其本身不正確地為非網際網路路由傳送 IP 嘗試開啟的連線至 EOP 時。保留供私人 （非可路由） 網路的 IP 位址包括：
  
- 192.168.0.0/16 (或 192.168.0.0-192.168.255.255)
    
- 10.0.0.0/8 (或 10.0.0.0-10.255.255.255)
    
- 172.16.0.0/11 (或 172.16.0.0-172.31.255.255)
    
### <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a>您收到未傳遞回報 (NDR) 時傳送電子郵件給 Office 365 的使用者
<a name="NDRInbound"> </a>

一些傳遞問題是由 Microsoft 遭封鎖的寄件者的 IP 位址的結果或因為的使用者帳戶識別為由於上述的垃圾郵件活動而禁用寄件者。如果您有收到錯誤 NDR，先遵循解決問題的 NDR 郵件中的任何指示。 
  
在您收到的錯誤的詳細資訊，請參閱中[的 Dsn 和 Ndr 內部部署 Exchange 2013 和 Office 365 中](http://technet.microsoft.com/library/8e91de84-76fa-49b2-898c-c5eface76560.aspx)的 SMTP 錯誤碼的完整清單。
  
 例如，如果您收到下列 NDR，即表示傳送端 IP 位址已封鎖 microsoft。 
  
 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`
  
若要要求從這份清單的 [移除]，您可以[使用 delist 入口網站來將自己從 Office 365 封鎖的寄件者清單中移除](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)。
  
### <a name="my-email-landed-in-the-recipients-junk-folder-in-eop"></a>在 EOP 中的收件者垃圾資料夾中的 「 我的電子郵件登陸
<a name="JunkMailBox"> </a>

如果透過 EOP 錯誤訊息識別為垃圾郵件，您可以使用送出這個誤判郵件給 Microsoft 垃圾郵件分析小組，將評估和分析之郵件的收件者。根據此分析結果，整個服務的垃圾郵件內容篩選規則可能會調整以允許透過訊息。您可以使用電子郵件來提交給 Microsoft 的不應歸類為垃圾郵件的郵件。時這麼做，請務必使用下列程序中的步驟。
  
### <a name="to-use-email-to-submit-false-positive-messages-to-the-microsoft-spam-analysis-team"></a>若要使用電子郵件來提交誤判的郵件到 Microsoft 垃圾郵件分析小組

1. 儲存您想要當作非垃圾郵件提交的郵件。
    
2. 建立新的空白郵件，然後在其中附加非垃圾郵件。
    
    您可以在必要時附加多個非垃圾郵件。
    
3. 複製原始郵件的主旨行並貼到新郵件的主旨行中。
    
    > [!IMPORTANT]
    > 將新郵件的內文保留空白。 
  
4. 將新郵件傳送到 [not_junk@office365.microsoft.com](mailto:not_junk@office365.microsoft.com)。
    
### <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a>從我的 IP 位址的流量會由 EOP 節流的處理
<a name="AllowEOPIPs"> </a>

如果您收到 NDR 中指出的 EOP IP 位址是正在會由節流處理 EOP，例如：
  
 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`
  
您會收到 NDR 是因為已偵測到可疑活動來自 IP 位址和它已暫時受到限制時所要進一步評估。如果透過評估清除懷疑，則會不久消除這個限制。
  
### <a name="i-cant-receive-email-from-senders-in-office-365"></a>我無法接收電子郵件從 Office 365 中的寄件者
<a name="AllowEOPIPs"> </a>

 若要從我們使用者接收郵件，請確定您的網路允許來自 EOP 會使用在我們的資料中心的 IP 位址的連線。如需詳細資訊，請參閱[Exchange Online Protection IP 位址](eop/exchange-online-protection-ip-addresses.md)。記錄的所有 IP 位址已新增、 變更，或在過去一年中已被取代，請參閱[EOP IP 位址的變更通知](eop/change-notification-for-eop-ip-addresses.md)。
  
## <a name="best-practices-for-bulk-emailing-to-office-365-users"></a>大量以電子郵件傳送至 Office 365 使用者的最佳作法
<a name="BulkMailer"> </a>

如果您經常進行大量電子郵件活動至 Office 365 使用者並想要確保您的電子郵件送達安全與即時的方式，請遵循本節中的秘訣。
  
### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a>確定 [自： 名稱會反映誰傳送郵件

主旨應何種郵件的簡短摘要是關於、 與郵件內文應該清楚且簡潔地指出可以、 服務或產品功能的相關。例如：
  
更正
  
 ` From: marketing@shoppershandbag.com `
  
 `Subject: Updated catalog for the Christmas season!`
  
不正確
  
 `From: someone@outlook.com`
  
 `Subject: Catalogs`
  
變得容易讓它知道您屬於人員與您所執行的動作、 較少的難度會有傳遞到大部分的垃圾郵件篩選器。
  
### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a>一律包含 campaign 電子郵件中的 [取消訂閱選項

行銷電子郵件、 特別新聞稿一律應該包含未來的電子郵件從取消訂閱的方式。例如：
  
 `This email was sent to example@contoso.com by sender@fabrikam.com.`
  
 `Update Profile/Email Address | Instant removal with SafeUnsubscribe™ | Privacy Policy`
  
某些寄件者包含這個選項需要特定別名與 「 取消訂閱"主旨中傳送電子郵件的收件者。這是不試試至單鍵上例中。如果您選擇不要需要傳送郵件的收件者，請確定當他們按一下 [連結] 時所需的所有欄位都會預先填入。
  
### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a>使用雙重加入確認程序中選項的行銷電子郵件或電子報註冊

如果公司需要或鼓勵使用者將其連絡人資訊登錄才可存取您的產品或服務，建議此業界最佳作法。有些公司讓它自動註冊行銷電子郵件使用者的作法或 e-新聞稿期間註冊程序，但這會被視為在電子郵件篩選的世界的問題行銷作法。
  
註冊程序期間如果的"Yes，請將您的電子報傳送我"或"Yes，請傳送我特別優惠"] 核取方塊已選取 [依預設，使用者不會關閉注意所可能不小心註冊行銷電子郵件或不一樣的新聞稿想要接收。
  
 我們建議雙重加入確認程序中選項而這表示行銷郵件或新聞稿的核取方塊會依預設未核取。此外之後已送出註冊表單，, 驗證電子郵件傳送給 url 以允許他們確認其決策接收行銷郵件使用者。 
  
 這有助於確保只有那些使用者想要接收行銷電子郵件簽署的電子郵件後續清除行銷作法任何問題電子郵件的傳送端的公司。 
  
### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a>確認電子郵件訊息內容透明且便於追蹤

同樣重要會傳送電子郵件的方式就網址中包含的內容。當建立電子郵件的內容，請使用下列最佳作法以確保您的電子郵件未標示的電子郵件篩選服務：
  
- 當電子郵件要求收件者將寄件者新增至通訊錄、 它應該清楚狀態的這類動作不保證郵件傳遞。
    
- 重新導向郵件的內文中包含應類似和一致的並不多與具有不同。在此上下文中重新導向是指引從郵件，例如連結和文件的任何項目。如果您有許多的廣告或取消訂閱連結或更新設定檔連結，他們應該所有指向相同的網域。例如：
    
    更正
    
     `unsubscribe.bulkmailer.com`
    
     `profile.bulkmailer.com`
    
     `options.bulkmailer.com`
    
    不正確
    
     `unsubscribe.bulkmailer.com`
    
     `profiles.excite.com`
    
     `options.yahoo.com`
    
- 避免使用大的影像和附件，或是察覺組成映像的郵件內容。
    
- 您的公眾隱私權或 P3P 設定應該清楚狀態追蹤像素 （web bug 或指標） 其目前狀態。
    
### <a name="remove-incorrect-email-aliases-from-your-databases"></a>從資料庫移除不正確的電子郵件別名

在您建立彈跳後的資料庫中任何電子郵件別名是不必要然後您外寄電子郵件風險的進一步無法在電子郵件篩選服務。請確定您的電子郵件資料庫是最新狀態。
  

