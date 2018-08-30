---
title: 防止被標記為 Office 365 和 Exchange Online Protection 中的垃圾電子郵件
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 74aaade0-efc0-46ac-b949-f2d1d59256fa
description: 若要防止良好的電子郵件的 Office 365 系統管理員的秘訣標示為垃圾郵件阻止傳送至隔離為誤判。自訂安全清單和其他選項可防止良好的電子郵件標示為垃圾郵件。
ms.openlocfilehash: 42b27d237592e95e6d175ab335959bc82269c0f7
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526239"
---
# <a name="prevent-email-from-being-marked-as-spam-in-office-365-and-exchange-online-protection"></a>防止被標記為 Office 365 和 Exchange Online Protection 中的垃圾電子郵件

使用適當的存取權認證的 Exchange Online 或 Exchange Online Protection (EOP) 系統管理員可以使用下列步驟以協助確保出差透過此服務的電子郵件不標示為垃圾郵件。
  
它可以是什麼有合法、 良好電子郵件隔離或已封鎖為垃圾郵件和登陸隔離區資料夾中。您可以使用安全的寄件者清單] 或 [郵件流程規則略過垃圾郵件篩選並防止良好的電子郵件快速標示為垃圾郵件。當訊息不正確地標記為垃圾郵件的垃圾郵件篩選，它已呼叫誤判。Office 365 垃圾郵件篩選器也提供一般使用者可自訂以協助防止誤判一些選項。
  
如果您正在尋找 false 負 mail 之類的說明也就是垃圾郵件訊息的時發生它不應該、 取出[封鎖](block-email-spam-to-prevent-false-negatives.md)電子郵件垃圾郵件與 Office 365 垃圾郵件篩選避免 false 負問題的秘訣。
  
## <a name="eop-only-customers-use-directory-synchronization"></a>僅限 EOP 的客戶： 使用目錄同步處理

EOP 會為雲端式電子郵件篩選服務，可協助保護您的組織垃圾郵件和惡意程式碼。如果您已在 Office 365 中的信箱，他們將自動受到保護 eop 因為它是服務的一部分。 
  
如果您是僅限 EOP 的客戶，也就是與您的內部部署 Exchange Server 訂閱使用 EOP 服務，您應該使用目錄同步作業同步處理與服務的使用者設定。如此一來確保您清單會原樣複製到 eop 的安全寄件者。如需詳細資訊，請參閱[Manage Mail Users in EOP](https://go.microsoft.com/fwlink/?LinkId=534098)中的 「 使用目錄同步作業管理郵件使用者 」。
  
## <a name="prevent-false-positive-email-by-using-the-connection-filters-ip-allow-list"></a>防止 false 正數電子郵件使用連線篩選的 IP 允許清單

如果您找出寄件者的電子郵件一律移至您的組織之垃圾郵件資料夾、 您可以將電子郵件寄件者的 IP 位址新增至您的連線篩選 IP 允許清單。一般而言，這可防止 false 正數回應這個組織內的所有收件者的寄件者。使用者啟用選項時的例外狀況"安全只列出： 只在安全的寄件者清單或安全的收件者清單上的人員或網域的郵件將傳送到收件匣"在 Outlook 中並不會將該寄件者新增到安全的寄件者清單。如需覆寫該選項，請參閱[疑難排解： 訊息之後會結束安裝垃圾郵件] 資料夾中即使 EOP 標示為非垃圾郵件](prevent-email-from-being-marked-as-spam-0.md#TroubleshootingJunkEOPNonSpam)。
  
 **若要將 IP 位址新增至您的連線篩選的 IP 允許清單**
  
1. 取得您想要允許寄件者所傳送的郵件的標頭。您可以這麼做從您的郵件用戶端如 Outlook 或 Outlook Web 上的[郵件標頭 Analyzer](https://go.microsoft.com/fwlink/p/?LinkId=306583)中所述。
    
2. 以手動方式搜尋追蹤 CIP 標籤 X Forefront-反垃圾郵件報告標頭或使用[遠端連線分析程式](https://testconnectivity.microsoft.com/?tabid=mha)的**訊息分析**] 索引標籤的 IP 位址。
    
3. 新增 IP 至 IP 位址所"使用 EAC 編輯預設連線篩選原則 」 中的步驟允許清單中[設定連線篩選原則](https://go.microsoft.com/fwlink/?LinkId=534132)。
    
## <a name="prevent-false-positive-email-by-configuring-spam-filter-policies"></a>設定垃圾郵件篩選器原則，以避免 false 正數電子郵件

您可以新增網域或個別的電子郵件地址的 [允許] 清單來[設定您的垃圾郵件篩選器原則](https://go.microsoft.com/fwlink/?LinkID=534136)中的步驟。
  
## <a name="review-your-advanced-spam-filter-policies"></a>檢閱您的進階垃圾郵件篩選器原則

如果您有特殊的限制設定垃圾郵件篩選器原則中，例如，如果您已封鎖的整個網域，您應該檢閱檢查如果他們可能原因包括誤判。請參閱[設定垃圾郵件篩選器原則](https://go.microsoft.com/fwlink/?LinkId=534136)，並關閉其他[進階垃圾郵件篩選選項](https://go.microsoft.com/fwlink/?LinkId=534137)可能會造成標示為垃圾郵件的郵件。 
  
## <a name="help-your-end-users-create-a-safe-sender-list-to-prevent-good-email-from-being-marked-as-spam"></a>協助您建立安全的寄件者清單，並防止良好的電子郵件被標記為垃圾郵件的使用者
<a name="BKMK_email-user-help-safelist"> </a>

告訴您的使用者將從他們信任至其安全的寄件者] 清單中[Outlook](https://go.microsoft.com/fwlink/p/?LinkId=270065)或[Outlook Web 上](https://go.microsoft.com/fwlink/p/?LinkId=294862)的寄件者地址。若要開始在 Web 上的 Outlook 中，選擇 [**設定**![ConfigureAPowerBIAnalysisServicesConnector_settingsIcon](media/24bd5467-c8d2-4936-9c37-a179bd0e21ec.png) \> **選項** \> **封鎖或允許**。下圖顯示範例將某個項目新增至安全的寄件者清單。
  
![在 Outlook Web App 中新增安全的寄件者](media/8de6b24e-429e-4e8f-8ce8-53ba659cbfcb.png)
  
EOP 會受限於使用者的安全寄件者和收件者，但不是安全的網域。這是不論是在 Web 上 Outlook 透過加入還是在 Outlook 中新增網域，則為 true 並同步處理使用目錄同步作業。
  
## <a name="troubleshooting-a-message-ends-up-in-the-junk-folder-even-though-eop-marked-the-message-as-non-spam"></a>疑難排解： 郵件會結束垃圾郵件] 資料夾中即使 EOP 標示為非垃圾郵件
<a name="TroubleshootingJunkEOPNonSpam"> </a>

如果您的使用者可以啟用在 Outlook 中"安全只列出： 僅安全的寄件者清單或安全的收件者清單上的人員或網域的郵件將傳送到收件匣 」，則所有電子郵件會移至 [垃圾資料夾的寄件者除非寄件者位於 recipient 的安全寄件者清單。將會發生此不論是否 EOP 會標示為非垃圾郵件或標示為非垃圾郵件設定 EOP 中的規則。
  
您可以停用 [僅安全的清單] 選項的 Outlook 使用者中的指示[Outlook： 若要停用垃圾電子郵件使用者介面的原則設定及篩選機制](https://support.microsoft.com/en-us/kb/2180568)。
  
如果您在網路上的 Outlook 檢視郵件，則將會指出因為寄件者無法在收件者的安全寄件者清單上的 [垃圾郵件] 資料夾中郵件為黃色 safety 提示。
  
如果您在查看之郵件標頭，它可能會加上戳記： skn （IP 允許或 ETR 允許） 或 SFV:NSPM （非垃圾郵件），但郵件仍處於使用者的垃圾資料夾。沒有在郵件標頭中會指出使用者具有 「 安全清單只"啟用。這是因為使用者在 Outlook 中設定 「 安全清單只"選項會覆寫 [EOP] 設定。 
  
 **若要確認為什麼從安全的寄件者的訊息會標記為非垃圾郵件的郵件標頭，但仍結尾使用者的垃圾郵件] 資料夾中**
  
1. 若要了解如何連線至 Exchange Online PowerShell，請參閱[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554)。 
    
2. 執行下列命令以檢視使用者的垃圾郵件組態設定：
    
  ```
  Get-MailboxJunkEmailConfiguration example@contoso.com | fl TrustedListsOnly,ContactsTrusted,TrustedSendersAndDomains
  ```

    如果 TrustedListsOnly 設為 True，就表示會啟用此設定。如果 ContactsTrusted 設為 True，就表示使用者信任連絡人和安全的寄件者。TrustedSendersAndDomains 列出使用者的安全寄件者清單的內容。
    
## <a name="still-need-help"></a>仍然需要說明嗎？
<a name="TroubleshootingJunkEOPNonSpam"> </a>

[![從 Office 365 社群論壇取得協助](media/12a746cc-184b-4288-908c-f718ce9c4ba5.png)](https://go.microsoft.com/fwlink/p/?LinkId=518605)
  
[![系統管理員：登入並建立服務要求](media/10862798-181d-47a5-ae4f-3f8d5a2874d4.png)]( https://go.microsoft.com/fwlink/p/?LinkId=519124)
  
[![系統管理員：呼叫支援](media/9f262e67-e8c9-4fc0-85c2-b3f4cfbc064e.png)](https://go.microsoft.com/fwlink/p/?LinkID=518322)
  
## <a name="see-also"></a>另請參閱
<a name="TroubleshootingJunkEOPNonSpam"> </a>

[垃圾郵件篩選器的概觀](https://support.office.com/article/5AE3EA8E-CF41-4FA0-B02A-3B96E21DE089)
  
[封鎖或允許 （垃圾郵件設定）](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46)
  
[利用 Office 365 垃圾郵件篩選器封鎖電子郵件垃圾郵件以避免誤判正常](block-email-spam-to-prevent-false-negatives.md)

