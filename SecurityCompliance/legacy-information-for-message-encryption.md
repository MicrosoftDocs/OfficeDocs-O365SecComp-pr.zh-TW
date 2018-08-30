---
title: Office 365 郵件加密的舊版資訊
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/4/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: None
search.appverid:
- MET150
ms.assetid: 5986b9e1-c824-4f8f-9b7d-a2b0ae2a7fe9
description: 如果您尚未尚未移動 Office 365 組織到新的 OME 功能，但您已部署 OME，本文資訊適用於您組織。Microsoft 建議您將移至新的 OME 功能一旦是組織的合理的計劃。指示，請參閱 ＜ Set up 新建置上方的 Azure 資訊保護的 Office 365 郵件加密功能。如果您想要了解更多有關的新功能如何運作前，請參閱 Office 365 郵件加密。本文的其餘部分是指 OME 行為的新 OME 功能發行前。
ms.openlocfilehash: d5b21cbe0004ca7bda38085bd5d8ef5f2a22b04e
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526839"
---
# <a name="legacy-information-for-office-365-message-encryption"></a>Office 365 郵件加密的舊版資訊

如果您尚未尚未移動 Office 365 組織到新的 OME 功能，但您已部署 OME，本文資訊適用於您組織。Microsoft 建議您將移至新的 OME 功能一旦是組織的合理的計劃。指示，請參閱[設定新的 Office 365 郵件加密功能建置於 Azure 資訊保護](set-up-new-message-encryption-capabilities.md)。如果您想要了解更多有關的新功能如何運作前，請參閱[Office 365 郵件加密](ome.md)。本文的其餘部分是指 OME 行為的新 OME 功能發行前。
  
與 Office 365 郵件加密，您的組織可以傳送和接收組織內外的人員之間的加密電子郵件訊息。Office 365 郵件加密適用於 Outlook.com、 Yahoo、 Gmail、 及其他電子郵件服務。電子郵件訊息加密有助於確保只有預定的收件者可以檢視郵件內容。
  
以下為一些範例：
  
- 銀行員工將信用卡帳單傳送給客戶
    
- 保險公司代表將細節提供給客戶原則的詳細資訊
    
- 抵押仲介要求之客戶的意見貸款申請的財務資訊
    
- 醫療服務提供者將醫療資訊傳送給病患
    
- 律師將機密資訊傳送給客戶或其他律師
    
## <a name="how-office-365-message-encryption-works-without-the-new-capabilities"></a>Office 365 郵件加密而的新功能的運作方式

Office 365 郵件加密是一種線上服務的內建 Microsoft Azure 版權管理 (Azure RMS)。以 Azure RMS 系統管理員可以定義郵件流程規則來決定加密的條件。例如，規則可能需要所有寄給特定收件者的郵件的加密。
  
觀看這段短片查看 Office 365 郵件加密而的新功能的運作方式。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c55540e7-f7f0-42f5-b254-4b2d2fbb1d63?autoplay=false]
  
當有人傳送電子郵件訊息在 Exchange Online 符合加密規則時，會傳送郵件具有 HTML 附件。收件者開啟 HTML 附件，並遵循指示來檢視加密的郵件上的 Office 365 郵件加密入口網站。收件者可以選擇檢視郵件登入 Microsoft 帳戶或工作或學校相關聯與 Office 365 或使用一次性複雜的程式碼。這兩個選項可協助確保只有預定的收件者可以檢視加密的郵件。此程序的新 OME 功能非常不同。
  
下表摘要說明透過加密和解密程序傳送電子郵件的過程。
  
![顯示加密電子郵件路徑的圖表](media/O365-Office365MessageEncryption-Concept.png)
  
如需詳細資訊，請參閱[服務舊版 Office 365 郵件加密之前版本的新 OME 功能](legacy-information-for-message-encryption.md#LegacyServiceInfo)。
  
## <a name="defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities"></a>定義不使用新的 OME 功能的 Office 365 郵件加密的郵件流程規則

若要啟用 Office 365 郵件加密的新功能而，Exchange Online 和 Exchange Online Protection 系統管理員會定義 Exchange 郵件流程規則。這些規則決定下何種條件電子郵件訊息應加密，以及移除郵件加密的條件。當加密巨集指令設定規則時，任何符合的規則條件的郵件加密之前他們正在傳送。
  
郵件流程規則具有彈性，讓您可以讓您可以符合特定安全性需求中單一規則合併條件。例如，您可以建立加密包含指定的關鍵字和定址給外部收件者的所有郵件的規則。Office 365 郵件加密也會從加密的電子郵件的收件者的回覆，您可以建立規則以解密那些回覆的電子郵件使用者的方便。如此一來，您的組織中的使用者不會有登入加密入口網站檢視回覆。
  
如需如何建立 Exchange 郵件流程規則的詳細資訊，請參閱[Define Rules for Office 365 Message Encryption](define-mail-flow-rules-to-encrypt-email.md)。
  
## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>傳送、檢視和回覆加密的電子郵件

與 Office 365 郵件加密、 電子郵件訊息會經過加密自動根據管理員定義規則。收件者的收件匣會進入附加 HTML 檔案天堂加密的郵件的電子郵件。
  
收件者遵循在開啟附件，並使用 Microsoft 帳戶或工作或學校相關聯與 Office 365 進行驗證的訊息中的指示。如果收件者沒有其中一個帳戶，他們正在導向建立檢視加密的郵件讓它們的帳戶登入 Microsoft。或者，收件者可以選擇以取得檢視郵件單次複雜程式碼。登入或之後使用一次性複雜的程式碼，收件者可以檢視已解密的郵件和傳送加密的回覆。
  
## <a name="customize-encrypted-messages-with-office-365-message-encryption"></a>自訂 Office 365 郵件加密的加密的郵件

身為 Exchange Online 與 Exchange Online Protection 的管理員，您可以自訂加密的郵件。例如，您可以新增公司的品牌和商標、 指定簡介，並新增免責聲明文字中加密的郵件和入口網站中的收件者所在檢視加密的郵件。使用 Windows PowerShell cmdlet，您可以自訂下列部分的加密的電子郵件的收件者的檢視經驗：
  
- 包含加密訊息的電子郵件簡介文字
    
- 包含加密訊息的電子郵件免責聲明文字
    
- 將會出現在訊息檢視入口網站的入口網站文字
    
- 將會出現在電子郵件和檢視入口網站的標誌
    
您也可以隨時回復為預設的外觀與風格。
  
下列範例顯示 ContosoPharma 在電子郵件附件中的自訂標誌：
  
![已加密郵件頁面的檢視範例](media/TA-OME-3attachment2.jpg)
  
 **來自訂加密電子郵件和加密入口網站使用您的組織的商標**
  
1. 連線至 Exchange Online 使用遠端 PowerShell[連線至 Exchange Online Using Remote PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated)中所述。
    
2. 使用 Set-omeconfiguration 指令程式，如下所述這裡： [Set-omeconfiguration](http://technet.microsoft.com/en-us/3ef0aec0-ce28-411d-abe8-7236f082af1b)或使用下表取得指引。 
    
   **加密自訂選項**

|**若要自訂此加密經驗功能**|**請使用這些 Windows PowerShell 命令**|
|:-----|:-----|
|加密電子郵件隨附的預設文字  <br/> 預設文字會出現在檢視加密郵件的指示上方。  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<string of up to 1024 characters>"` <br/> **範例：**`Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system"` <br/> |
|包含加密訊息之電子郵件中的免責聲明  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<your disclaimer statement, string of up to 1024 characters>"` <br/> **範例：**`Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText "This message is confidential for the use of the addressee only"` <br/> |
|出現在加密郵件檢視入口網站上方的文字  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<text for your portal, string of up to 128 characters>"` <br/> **範例：**`Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal"` <br/> |
|標誌  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **範例：**`Set-OMEConfiguration -Identity "OME configuration" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> 支援的檔案格式：.png、.jpg、.bmp 或 .tiff  <br/> 標誌檔案的最佳大小：小於 40 KB  <br/> 標誌影像的最佳大小：170x70 像素  <br/> |
   
 **若要移除的商標自訂加密電子郵件和加密入口網站**
  
1. 連線至 Exchange Online 使用遠端 PowerShell[連線至 Exchange Online Using Remote PowerShell](http://technet.microsoft.com/en-us/library/jj984289%28v=exchg.150%29.aspx)中所述。
    
2. 使用 Set-omeconfiguration 指令程式，如下所述這裡： [Set-omeconfiguration](http://technet.microsoft.com/3ef0aec0-ce28-411d-abe8-7236f082af1b)。若要移除您組織的加商標的自訂項目從 DisclaimerText、 EmailText、 和 PortalText 值將值設定為空字串， `""`。如所有圖像值，例如標誌，將值設定為`"$null"`。
    
   **加密自訂選項**

|**將加密體驗的這項功能回復為預設文字和影像**|**請使用這些 Windows PowerShell 命令**|
|:-----|:-----|
|加密電子郵件隨附的預設文字  <br/> 預設文字會出現在檢視加密郵件的指示上方。  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **範例：**`Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""` <br/> |
|包含加密訊息之電子郵件中的免責聲明  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **範例：**`Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""` <br/> |
|出現在加密郵件檢視入口網站上方的文字  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **回復為預設的範例：**`Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""` <br/> |
|標誌  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **回復為預設的範例：**`Set-OMEConfiguration -Identity "OME configuration" -Image $null` <br/> |
   
## <a name="service-information-for-legacy-office-365-message-encryption-prior-to-the-release-of-the-new-ome-capabilities"></a>舊版 Office 365 郵件加密之前版本的新 OME 功能的服務資訊
<a name="LegacyServiceInfo"> </a>

下表提供 Office 365 郵件加密服務之前版本的新 OME 功能的技術詳細資料。
  
|**服務詳細資料**|**描述**|
|:-----|:-----|
|用戶端裝置需求  <br/> |只要可以在支援「表單張貼」的現代瀏覽器中開啟 HTML 附件，就可以在任何用戶端裝置上檢視加密郵件。  <br/> |
|加密演算法和聯邦資訊處理標準 (FIPS) 相容性  <br/> |Office 365 郵件加密使用相同的加密金鑰以 Windows Azure 資訊版權管理 (IRM)，並支援密碼編譯模式 2 （2 K 金鑰 RSA） 和 256 位元金鑰 sha-1 系統。如需基礎的 IRM 密碼編譯模式的詳細資訊，請參閱[AD RMS 密碼編譯模式](http://technet.microsoft.com/library/hh867439%28WS.10%29.aspx)。<br/> |
|支援的訊息類型  <br/> |Office 365 郵件加密僅支援包含**IPM 訊息類別識別碼的項目。請注意**。如需詳細資訊，請參閱[項目類型和郵件類別](https://msdn.microsoft.com/library/office/ff861573.aspx)。<br/> |
|郵件大小限制  <br/> |Office 365 郵件加密可以加密郵件的最多 25 mb。如需詳細資訊的郵件大小限制，請參閱[Exchange Online 限制](http://technet.microsoft.com/library/exchange-online-limits.aspx)。<br/> |
|Exchange Online 電子郵件保留原則  <br/> |Exchange Online 不會儲存加密的郵件。  <br/> |
|Office 365 郵件加密的語言支援  <br/> | Office 365 郵件加密支援 Office 365 語言，如下所示：  <br/>  內送電子郵件和附加的 HTML 檔案會進行當地語系化根據寄件者的語言設定。  <br/>  檢視入口網站是根據收件者的瀏覽器設定進行當地語系化。  <br/>  加密郵件的本文 (內容) 則不會進行當地語系化。  <br/> |
|OME 入口網站與 OME 檢視器應用程式的隱私權資訊  <br/> |[Office 365 Messaging Encryption Portal privacy statement](protected-message-viewer-portal-privacy-statement.md) 提供 Microsoft 如何處理您私人資訊的詳細資訊。  <br/> |
   
## <a name="frequently-asked-questions-about-legacy-ome"></a>常見問題集舊版 OME 的相關
<a name="LegacyServiceInfo"> </a>

取得 Office 365 郵件加密的相關問題嗎？以下是一些常見問題的解答。如果您找不到您的需要，檢查[Office 365 社群](http://community.office365.com/en-us/forums/default.aspx)在 Office 365 社群論壇。
  
 **問我的使用者傳送加密的電子郵件給我們組織外部收件者。是否有任何外部收件者已執行動作以閱讀和回覆加密與 Office 365 郵件加密的電子郵件吗？**
  
組織外部的收件者收到以 Office 365 加密的電子郵件時，可以這兩種方式檢視郵件：
  
- 登入 Microsoft 帳戶或 Office 365 相關聯的工作或學校帳戶。
    
- 使用 [一次性傳遞的程式碼。
    
 **問：Office 365 加密郵件是儲存於雲端或 Microsoft 伺服器上嗎？**
  
否，加密的郵件會在收件者的電子郵件系統，並當收件者開啟郵件時，會暫時張貼的 Office 365 的伺服器上的檢視。郵件未那里儲存。
  
 **問：我可以使用自己的品牌自訂加密電子郵件嗎？**
  
可以。您可以使用 Windows PowerShell Cmdlet 自訂加密電子郵件頂端顯示的預設文字、免責聲明文字，及要用於電子郵件和加密入口網站的標誌。如需詳細資訊，請參閱[Add branding to encrypted messages](add-your-organization-brand-to-encrypted-messages.md)。
  
 **問：我組織內每位使用者是否皆需備有服務授權？**
  
組織中傳送加密電子郵件的每位使用者皆需有授權。
  
 **問：外部收件者需要訂閱嗎？**
  
否，外部收件者不需要訂閱即可讀取或回覆加密郵件。 
  
 **問如何為 Office 365 郵件加密不同從 Rights Management Services (RMS)？**
  
RMS 提供組織內部電子郵件的資訊權限保護功能來提供內建的範本，例如： 不要轉寄和公司機密。Office 365 郵件加密支援電子郵件加密的郵件傳送至外部收件者為內部收件者。
  
 **問如何為 Office 365 郵件加密 S/MIME 與不同？**
  
S/MIME 基本上是一種用戶端加密技術，需要複雜的憑證管理與發佈基礎結構。Office 365 郵件加密使用傳輸規則，不需要憑證發佈。
  
 **問：我可以透過行動裝置閱讀加密郵件嗎？**
  
是，您可以在 Android 和 iOS 上檢視郵件可透過從[Google 播放儲存](http://go.microsoft.com/fwlink/?LinkID=525995&amp;clcid=0x409)和[Apple 應用程式存放區](http://go.microsoft.com/fwlink/?LinkID=525996&amp;clcid=0x409)下載 OME 檢視器應用程式。在 OME 檢視器應用程式中開啟 HTML 附件，然後遵循指示來開啟加密的郵件。其他行動裝置，您可以開啟 HTML 附件只要郵件用戶端支援 「 表單張貼。
  
 **問：回覆和轉寄郵件皆會加密嗎？**
  
是的。在整個執行緒期間都會對回應持續加密。
  
 **問：Office 365 郵件加密是否提供當地語系化？**
  
內送電子郵件和 HTML 內容均依據寄件者電子郵件設定進行當地語系化。檢視入口網站會依據收件者的瀏覽器設定進行當地語系化。不過，加密郵件的實際內文 (內容) 不會進行當地語系化。
  
 **問：Office 365 郵件加密使用何種加密方法？**
  
Office 365 郵件加密使用 Rights Management Services (RMS) 做為其加密基礎結構。使用的加密方法取決於您在哪裡取得用來加密及解密郵件的 RMS 金鑰。
  
- 如果您使用 Microsoft Azure RMS 取得金鑰，則會使用密碼編譯模式 2。密碼編譯模式 2 是更新及增強 AD RMS 密碼編譯實作。它支援 RSA 2048 簽章和加密，並支援 SHA-1 256 個簽章。
    
- 如果您使用 Active Directory (AD) RMS 來取得金鑰，則會使用密碼編譯模式 1 或密碼編譯模式 2。使用的方法取決於內部部署 AD RMS 部署。密碼編譯模式 1 是原始的 AD RMS 密碼編譯實作。它支援使用 RSA 1024 進行簽章和加密，也支援使用 SHA-1 進行簽章。這個模式會繼續受到 RMS 所有目前的版本支援。
    
如需詳細資訊，請參閱[AD RMS 密碼編譯模式](http://go.microsoft.com/fwlink/p/?LinkId=398616)。
  
 **問：為什麼某些加密的訊息指出其來自 Office365@messaging.microsoft.com？**
  
從加密入口網站或透過 OME 檢視器應用程式傳送加密的回覆時，傳送方的電子郵件地址會設為 Office365@messaging.microsoft.com，因為加密的郵件是透過 Microsoft 端點傳送。這有助於避免加密的郵件被標示為垃圾郵件。因為有此標示，加密入口網站中顯示的電子郵件名稱和地址不會變更。此外，此標示只會套用到透過入口網站傳送的郵件，而不會套用到透過任何其他電子郵件用戶端傳送的郵件。
  
 **問 I am Exchange Hosted Encryption (EHE) 訂閱者。讓瞭解更多有關升級至 Office 365 郵件加密資訊？**
  
所有的 EHE 客戶都已升級至 Office 365 郵件加密。如需詳細資訊，請造訪[Exchange 託管加密升級中心](http://go.microsoft.com/fwlink/p/?LinkID=511077)。
  
 **問： 我需要的開啟任何 Url、 IP 位址，或在我的組織防火牆連接埠以支援 Office 365 郵件加密吗？**
  
是的。您必須將 Exchange Online 的 URL 新增到您組織的允許清單中，才能為 Office 365 郵件加密所加密的郵件啟用驗證。如需 Exchange Online URL 的清單，請參閱 [Office 365 URLs and IP Address Ranges](https://support.office.com/article/f57e35b7-0a45-42f0-855e-11aa5e7f13fd.aspx)。
  
 **問：我可以將 Office 365 加密郵件傳送給多少位收件者？**
  
加密郵件的收件者限制為基礎的**郵件] 欄位**中的字元數。當合併 （之後通訊群組清單延伸），在**欄位中**的收件者地址不應該超過 11,980 字元。因為的字元長度變化多端電子郵件地址，有不標準的收件者限制為單一加密郵件。 
  
 **問：是否可以撤銷傳送給特定收件者的郵件？**
  
[否]。您不能撤銷權限給特定人員訊息之後傳送中。
  
 **問：是否可以檢視已接收和讀取的加密郵件的報表？**
  
沒有顯示報告，如果已經檢視加密的郵件，但有 Office 365 報告提供您可以運用來決定符合特定傳輸規則，例如的訊息數。
  
 **問：Microsoft 會如何利用透過 OME 入口網站和 OME 檢視器應用程式所取得我的資訊？**
  
[Office 365 郵件加密入口網站隱私權聲明](protected-message-viewer-portal-privacy-statement.md)提供 Microsoft 與目的沒有透過私人資訊的詳細的資訊。 
  

