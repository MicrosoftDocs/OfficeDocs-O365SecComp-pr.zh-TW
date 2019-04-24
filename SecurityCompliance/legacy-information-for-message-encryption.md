---
title: Office 365 郵件加密的舊版資訊
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 1/4/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.assetid: 5986b9e1-c824-4f8f-9b7d-a2b0ae2a7fe9
ms.collection:
- M365-security-compliance
description: 如果您尚未尚未將您的 Office 365 組織移動到全新的 OME 功能，但您已部署 OME，本文資訊適用於您的組織。 Microsoft 建議您先將移至全新的 OME 功能，只要是合理的貴組織的計劃。 如需相關指示，請參閱 < Set up 以 Azure 資訊保護基礎所建置的全新 Office 365 郵件加密功能。 如果您想要深入了解新功能的運作方式第一次，請參閱 Office 365 郵件加密。 本文的其餘部分指的是全新的 OME 功能的發行前 OME 行為。
ms.openlocfilehash: 03e2cb9c1f7d447f2fcf222382fcc2366faf0658
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32252067"
---
# <a name="legacy-information-for-office-365-message-encryption"></a>Office 365 郵件加密的舊版資訊

如果您尚未尚未將您的 Office 365 組織移動到全新的 OME 功能，但您已部署 OME，本文資訊適用於您的組織。 Microsoft 建議您先將移至全新的 OME 功能，只要是合理的貴組織的計劃。 如需相關指示，請參閱[設定以 Azure 資訊保護基礎所建置的全新 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)。 如果您想要深入了解新功能的運作方式第一次，請參閱[Office 365 郵件加密](ome.md)。 本文的其餘部分指的是全新的 OME 功能的發行前 OME 行為。
  
使用 Office 365 郵件加密，組織可以傳送和接收您組織內部和外部的人員之間的加密的電子郵件訊息。 Office 365 郵件加密的運作與 Outlook.com、 Yahoo、 Gmail，以及其他電子郵件服務。 電子郵件訊息加密有助於確保只有預定的收件者可以檢視郵件內容。
  
以下為一些範例：
  
- 銀行員工將信用卡帳單傳送給客戶
    
- 保險公司代表將提供原則的詳細資訊給客戶
    
- 抵押仲介要求客戶貸款申請的財務資訊
    
- 醫療服務提供者將醫療資訊傳送給病患
    
- 律師將機密資訊傳送給客戶或其他律師
    
## <a name="how-office-365-message-encryption-works-without-the-new-capabilities"></a>Office 365 郵件加密沒有的新功能的運作方式

Office 365 郵件加密是 Microsoft Azure 版權管理 (Azure RMS) 做為基礎的線上服務。 使用 Azure RMS，系統管理員可以定義至判斷加密條件的郵件流程規則。 例如，規則可能需要加密的所有郵件傳送給特定收件者。
  
觀看這個簡短的影片，請參閱 Office 365 郵件加密沒有的新功能的運作方式。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c55540e7-f7f0-42f5-b254-4b2d2fbb1d63?autoplay=false]
  
當某人傳送電子郵件訊息在 Exchange Online 符合加密規則時，具有 HTML 附件傳送郵件。 收件者開啟 HTML 附件，並遵循指示，以在 Office 365 郵件加密入口網站上檢視加密的郵件。 收件者可以選擇以登入 Microsoft 帳戶或工作或學校 Office 365，相關聯，或使用一次性密碼檢視訊息。 這兩個選項可協助確保只有預定的收件者可以檢視加密的郵件。 此程序是非常不同的全新的 OME 功能。
  
下圖摘要說明透過加密和解密程序電子郵件訊息傳送過程。
  
![顯示加密電子郵件路徑的圖表](media/O365-Office365MessageEncryption-Concept.png)
  
如需詳細資訊，請參閱 <<c0>的舊版 Office 365 郵件加密，全新的 OME 功能的發行前服務資訊。
  
## <a name="defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities"></a>定義不使用全新的 OME 功能的 Office 365 郵件加密的郵件流程規則

若要啟用 Office 365 郵件加密沒有的新功能，Exchange Online 和 Exchange Online Protection 系統管理員會定義 Exchange 郵件流程規則。 這些規則可決定在哪些條件電子郵件訊息應該加密，以及移除郵件加密的條件。 當規則設定的加密巨集指令時，任何符合規則條件的郵件加密之前，他們所傳送。
  
郵件流程規則有彈性，讓您合併條件，因此您可以符合單一規則中的特定安全性需求。 例如，您可以建立規則以加密包含指定的關鍵字，而且寄送到外部收件者的所有郵件。 Office 365 郵件加密也會加密回覆加密電子郵件的收件者，您可以建立解密這些回覆的電子郵件使用者方便的規則。 如此一來，您組織中的使用者不必登入加密入口網站以檢視回覆。
  
如需如何建立 Exchange 郵件流程規則的詳細資訊，請參閱 < <b0>Define Rules for Office 365 Message Encryption</b0>。
  
## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>傳送、 檢視和回覆加密的電子郵件訊息

使用 Office 365 郵件加密，電子郵件加密，自動根據管理員定義的規則。 天堂加密的郵件的電子郵件會送達收件者的收件匣與附加的 HTML 檔案。
  
收件者遵循指示來開啟附件並驗證所使用的 Microsoft 帳戶或工作或學校 Office 365 相關聯的訊息。 如果收件者沒有任一帳戶，他們正在導向建立的 Microsoft 帳戶，讓他們登入以檢視加密的郵件。 此外，收件者可以選擇以取得次傳遞驗證碼，以檢視郵件。 登入或之後使用一次性密碼，收件者可以檢視已解密的郵件，並傳送加密的回覆。
  
## <a name="customize-encrypted-messages-with-office-365-message-encryption"></a>自訂 Office 365 郵件加密的加密的郵件

以 Exchange Online 和 Exchange Online Protection 系統管理員身分，您可以自訂您的加密的郵件。 例如，您可以新增公司的品牌和標誌、 指定需簡介，並新增免責聲明文字中加密的郵件和收件者檢視加密的郵件的其中入口網站中。 您可以使用 Windows PowerShell 指令程式，自訂以下方面的加密電子郵件收件者視覺體驗：
  
- 包含加密訊息的電子郵件簡介文字
    
- 包含加密訊息的電子郵件免責聲明文字
    
- 將會出現在訊息檢視入口網站的入口網站文字
    
- 將會出現在電子郵件和檢視入口網站的標誌
    
您也可以隨時回復為預設的外觀與風格。
  
下列範例顯示 ContosoPharma 在電子郵件附件中的自訂標誌：
  
![已加密郵件頁面的檢視範例](media/TA-OME-3attachment2.jpg)
  
 **若要自訂加密電子郵件和加密入口網站與貴組織的品牌**
  
1. 連線到 Exchange Online，使用遠端 PowerShell[連線到 Exchange Online Using Remote PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated)中所述。
    
2. 使用 Set-omeconfiguration 指令程式，如所述這裡： [Set-omeconfiguration](http://technet.microsoft.com/en-us/3ef0aec0-ce28-411d-abe8-7236f082af1b)或使用下表取得指引。 
    
   **加密自訂選項**

|**若要自訂此加密經驗功能**|**請使用這些 Windows PowerShell 命令**|
|:-----|:-----|
|加密電子郵件隨附的預設文字  <br/> 預設文字會出現在檢視加密郵件的指示上方。  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<string of up to 1024 characters>"` <br/> **範例：**`Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system"` <br/> |
|包含加密訊息之電子郵件中的免責聲明  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<your disclaimer statement, string of up to 1024 characters>"` <br/> **範例：**`Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText "This message is confidential for the use of the addressee only"` <br/> |
|出現在加密郵件檢視入口網站上方的文字  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<text for your portal, string of up to 128 characters>"` <br/> **範例：**`Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal"` <br/> |
|商標  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **範例：**`Set-OMEConfiguration -Identity "OME configuration" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> 支援的檔案格式：.png、.jpg、.bmp 或 .tiff  <br/> 標誌檔案的最佳大小：小於 40 KB  <br/> 標誌影像的最佳大小：170x70 像素  <br/> |
   
 **若要移除的商標自訂加密電子郵件和加密入口網站**
  
1. 連線到 Exchange Online，使用遠端 PowerShell[連線到 Exchange Online Using Remote PowerShell](http://technet.microsoft.com/en-us/library/jj984289%28v=exchg.150%29.aspx)中所述。
    
2. 使用 Set-omeconfiguration 指令程式，如所述這裡： [Set-omeconfiguration](http://technet.microsoft.com/3ef0aec0-ce28-411d-abe8-7236f082af1b)。 若要移除您組織的品牌自訂項目從 DisclaimerText，EmailText，和 PortalText 值，將值設定為空字串， `""`。 針對所有影像值，例如標誌，將值設為`"$null"`。
    
   **加密自訂選項**

|**將加密體驗的這項功能回復為預設文字和影像**|**請使用這些 Windows PowerShell 命令**|
|:-----|:-----|
|加密電子郵件隨附的預設文字  <br/> 預設文字會出現在檢視加密郵件的指示上方。  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **範例：**`Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""` <br/> |
|包含加密訊息之電子郵件中的免責聲明  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **範例：**`Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""` <br/> |
|出現在加密郵件檢視入口網站上方的文字  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **回復為預設值的範例：**`Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""` <br/> |
|商標  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **回復為預設值的範例：**`Set-OMEConfiguration -Identity "OME configuration" -Image $null` <br/> |
   
## <a name="service-information-for-legacy-office-365-message-encryption-prior-to-the-release-of-the-new-ome-capabilities"></a>舊版 Office 365 郵件加密之前發行的全新的 OME 功能的服務資訊
<a name="LegacyServiceInfo"> </a>

下表提供 Office 365 郵件加密服務發行以前的全新的 OME 功能的技術詳細資料。
  
|**服務詳細資料**|**描述**|
|:-----|:-----|
|用戶端裝置需求  <br/> |可以在任何用戶端裝置，檢視加密的郵件，只要可以在支援 「 表單張貼 」 的現代瀏覽器中開啟 HTML 附件。  <br/> |
|加密演算法和聯邦資訊處理標準 (FIPS) 相容性  <br/> |Office 365 郵件加密使用相同的加密金鑰與 Windows Azure 資訊版權管理 (IRM)，並支援 sha-1 系統密碼編譯模式 2 （2 K 金鑰 RSA） 和 256 位元金鑰。 如需詳細的基礎的 IRM 密碼編譯模式的詳細資訊，請參閱 < <b0>AD RMS 密碼編譯模式</b0>。  <br/> |
|支援的訊息類型  <br/> |Office 365 郵件加密只支援包含**IPM 訊息類別識別碼的項目。附註**。 如需詳細資訊，請參閱[項目類型和郵件類別](https://msdn.microsoft.com/library/office/ff861573.aspx)。  <br/> |
|郵件大小限制  <br/> |Office 365 郵件加密可以加密郵件的最多 25 mb。 如需郵件大小限制的詳細資訊，請參閱 < <b0>Exchange Online 限制</b0>。  <br/> |
|Exchange Online 電子郵件保留原則  <br/> |Exchange Online 不會儲存加密的郵件。  <br/> |
|Office 365 郵件加密的語言支援  <br/> | Office 365 郵件加密支援 Office 365 語言，如下所示：  <br/>  內送電子郵件和附加的 HTML 檔案會當地語系化根據寄件者的語言設定。  <br/>  檢視入口網站會根據收件者的瀏覽器設定進行當地語系化。  <br/>  加密郵件的本文 （內容） 不進行當地語系化。  <br/> |
|OME 入口網站與 OME 檢視器應用程式的隱私權資訊  <br/> |[Office 365 Messaging Encryption Portal 隱私權聲明](protected-message-viewer-portal-privacy-statement.md)提供哪些 Microsoft 會以及不會運用您私人資訊的詳細的資訊。  <br/> |
   
## <a name="frequently-asked-questions-about-legacy-ome"></a>常見問題集關於舊版 OME
<a name="LegacyServiceInfo"> </a>

有關於 Office 365 郵件加密的問題嗎？ 以下是一些解答。 如果您找不到您的需要請在[Office 365 社群](http://community.office365.com/en-us/forums/default.aspx)的 Office 365 社群論壇。
  
 **問： 我的使用者傳送加密的電子郵件給我們在組織外的收件者。是否有任何外部收件者必須以閱讀和回覆加密與 Office 365 郵件加密的電子郵件？**
  
組織外部的收件者收到以 Office 365 加密的電子郵件時，可以這兩種方式檢視郵件：
  
- 登入 Microsoft 帳戶或 Office 365 相關聯的公司或學校帳戶。
    
- 使用一次性密碼
    
 **問：Office 365 加密郵件是儲存於雲端或 Microsoft 伺服器上嗎？**
  
否，加密的郵件會保留在收件者的電子郵件系統上，且當收件者開啟郵件時，會暫時張貼的 Office 365 伺服器上的檢視。 郵件並不會儲存於該處。
  
 **問：我可以使用自己的品牌自訂加密電子郵件嗎？**
  
是。 您可以使用 Windows PowerShell Cmdlet 自訂加密電子郵件頂端顯示的預設文字、免責聲明文字，及要用於電子郵件和加密入口網站的標誌。 如需詳細資訊，請參閱[Add branding to encrypted messages](add-your-organization-brand-to-encrypted-messages.md)。
  
 **問：我組織內每位使用者是否皆需備有服務授權？**
  
組織中傳送加密電子郵件的每位使用者皆需有授權。
  
 **問：外部收件者需要訂閱嗎？**
  
否，外部收件者不需要訂閱即可讀取或回覆加密郵件。 
  
 **問： 如何為 Office 365 郵件加密不同從 Rights Management Services (RMS)？**
  
RMS 提供組織內部的電子郵件的資訊版權保護功能提供內建的範本，例如： 不要轉寄 」 和 「 公司機密。 Office 365 郵件加密支援傳送至外部收件者和內部收件者之郵件的電子郵件加密。
  
 **問： 如何為 Office 365 郵件加密 S/MIME 與不同？**
  
S/MIME 基本上是一種用戶端加密技術，需要複雜的憑證管理與發佈基礎結構。 Office 365 郵件加密使用郵件流程規則 （也稱為傳輸規則），並不會根據憑證發佈。
  
 **問：我可以透過行動裝置閱讀加密郵件嗎？**
  
是，您也可以從[Google Play 儲存](http://go.microsoft.com/fwlink/?LinkID=525995&amp;clcid=0x409)和[Apple 應用程式存放區](http://go.microsoft.com/fwlink/?LinkID=525996&amp;clcid=0x409)下載 OME 檢視器應用程式，以檢視郵件在 Android 和 iOS 上。 在 OME 檢視器應用程式中開啟 HTML 附件，然後依照指示開啟加密的郵件。 對其他行動裝置而言，只要郵件用戶端支援表單張貼，您便能夠開啟 HTML 附件。
  
 **問：回覆和轉寄郵件皆會加密嗎？**
  
是的。在整個執行緒期間都會對回應持續加密。
  
 **問： Office 365 郵件加密提供當地語系化嗎？**
  
內送電子郵件和 HTML 內容均依據寄件者電子郵件設定進行當地語系化。檢視入口網站會依據收件者的瀏覽器設定進行當地語系化。不過，加密郵件的實際內文 (內容) 不會進行當地語系化。
  
 **問： 什麼加密方法用於 Office 365 郵件加密？**
  
Office 365 郵件加密使用 Rights Management Services (RMS) 作為其加密基礎結構。 使用的加密方法取決於您在哪裡取得用來加密及解密郵件的 RMS 金鑰。
  
- 如果您使用 Microsoft Azure RMS 來取得金鑰時，會使用密碼編譯模式 2。 密碼編譯模式 2 是已更新並增強的 AD RMS 密碼編譯實作。 它支援使用 RSA 2048 進行簽章和加密，也支援使用 SHA-256 進行簽章。
    
- 如果您使用 Active Directory (AD) RMS 來取得金鑰，則會使用密碼編譯模式 1 或密碼編譯模式 2。使用的方法取決於內部部署 AD RMS 部署。密碼編譯模式 1 是原始的 AD RMS 密碼編譯實作。它支援使用 RSA 1024 進行簽章和加密，也支援使用 SHA-1 進行簽章。這個模式會繼續受到 RMS 所有目前的版本支援。
    
如需詳細資訊，請參閱[AD RMS 密碼編譯模式](http://go.microsoft.com/fwlink/p/?LinkId=398616)。
  
 **問：為什麼某些加密的訊息指出其來自 Office365@messaging.microsoft.com？**
  
從加密入口網站或透過 OME 檢視器應用程式傳送加密的回覆時，傳送方的電子郵件地址會設為 Office365@messaging.microsoft.com，因為加密的郵件是透過 Microsoft 端點傳送。這有助於避免加密的郵件被標示為垃圾郵件。因為有此標示，加密入口網站中顯示的電子郵件名稱和地址不會變更。此外，此標示只會套用到透過入口網站傳送的郵件，而不會套用到透過任何其他電子郵件用戶端傳送的郵件。
  
 **問： 我是 Exchange Hosted Encryption (EHE) 訂閱者。何處可深入了解有關升級至 Office 365 郵件加密？**
  
所有 EHE 客戶都已升級至 Office 365 郵件加密。 如需詳細資訊，請造訪[Exchange 託管加密升級中心](http://go.microsoft.com/fwlink/p/?LinkID=511077)。
  
 **問： 我需要的開啟任何 Url、 IP 位址，或在 [我的組織防火牆連接埠以支援 Office 365 郵件加密？**
  
是。 您必須將 Url 的 Exchange Online 新增至允許清單中，為您的組織若要啟用 Office 365 郵件加密所加密的郵件的驗證。 如需 Exchange Online URL 的清單，請參閱 [Office 365 URLs and IP Address Ranges](https://support.office.com/article/f57e35b7-0a45-42f0-855e-11aa5e7f13fd.aspx)。
  
 **問：我可以將 Office 365 加密郵件傳送給多少位收件者？**
  
加密郵件的收件者限制根據郵件的**截止**] 欄位中的字元數。 合併後 (在展開通訊群組清單之後)，[收件者]**** 欄位中的收件者地址不得超過 11,980 個字元。 因為電子郵件地址的字元長度而異，沒有單一已加密郵件的標準收件者限制。 
  
 **問：是否可以撤銷傳送給特定收件者的郵件？**
  
否。 傳送之後，您無法撤銷特定人員所要的訊息。
  
 **問：是否可以檢視已接收和讀取的加密郵件的報表？**
  
沒有顯示報告，如果已檢視加密的郵件，但有 Office 365 報告提供您可以運用這些功能，來判斷符合特定的郵件流程規則 （也稱為傳輸規則），例如郵件數目。
  
 **問：Microsoft 會如何利用透過 OME 入口網站和 OME 檢視器應用程式所取得我的資訊？**
  
[Office 365 Messaging Encryption Portal 隱私權聲明](protected-message-viewer-portal-privacy-statement.md)提供哪些 Microsoft 會以及不會運用您私人資訊的詳細的資訊。 
  

